
当用户在更新值后最终点击保存按钮时，所有的表单控件值（包括出版者单选控件的值）都会被复制到`slots`记录的相应槽位中，该记录将在所有值通过有效性检查后作为调用`update`方法的参数。在调用`update`之前，根据`classList`值从关联的作者选择组件中记录的更新，创建一个待添加作者 ID 引用列表和另一个待删除作者 ID 引用列表（分别在`authorIdRefsToAdd`和`authorIdRefsToRemove`槽位中），如下程序所示：

## 3.6 如何运行应用并获取代码

```javascript
handleSaveButtonClickEvent: function () {
  const formEl = document.querySelector("#Book-U> form"),
    selectBookEl = formEl.selectBook,
    selectAuthorsWidget = formEl.querySelector(".MultiChoiceWidget"),
    multiChoiceListEl = selectAuthorsWidget.firstElementChild;

  const slots = {
    isbn: formEl.isbn.value,
    title: formEl.title.value,
    year: formEl.year.value,
    publisher_id: formEl.selectPublisher.value
  };

  // // 为响应式验证添加监听器
  // ...

  // // 仅当所有字段值有效时才提交更新
  if (formEl.checkValidity()) {
    // // 从关联列表构建 authorIdsToAdd/ToRemove
    let authorRefsToAdd = [], authorRefsToRemove = [];

    for (let mclListItemEl of multiChoiceListEl.children) {
      if (mclListItemEl.classList.contains("removed")) {
        authorRefsToRemove.push(mclListItemEl.getAttribute("data-value"));
      }
      if (mclListItemEl.classList.contains("added")) {
        authorRefsToAdd.push(mclListItemEl.getAttribute("data-value"));
      }
    }

    // // 如果添加/删除列表非空则创建相应的槽位
    if (authorRefsToRemove.length > 0) {
      slots.authorRefsToRemove = authorRefsToRemove;
    }
    if (authorRefsToAdd.length > 0) {
      slots.authorRefsToAdd = authorRefsToAdd;
    }

    // Book.update(slots);
    // // 更新书籍选择列表的选项元素
    selectBookEl[selectBookEl.selectedIndex].text = slots.title;
  }
}
```

## 3.6 如何运行应用并获取代码

你可以从我们的服务器运行示例应用并将其作为 ZIP 压缩包下载。

## 3.7 注意事项

我们仍然在模型层中为每个类和每个属性保留了重复的代码结构（称为样板代码），用于约束验证（检查和设置器），并为每个类编写了数据存储管理方法（添加、更新和删除）。虽然为了学习应用开发而编写几次这些代码是有好处的，但在处理实际项目时，你不希望一遍又一遍地编写它们。为了避免重复的样板代码，需要这些方法的通用形式，以便它们可以在应用的所有模型类中复用。例如，`cCLASSjs`库就提供了这种方法。

# 4 使用 Java EE 实现单向功能关联

单向功能关联可以是一对一或多对一的。在这两种情况下，这种关联都是通过一个单值引用属性来表示或实现的。

在本章中，我们将展示：

1. 如何从具有表示单向功能关联的单值引用属性的 OO 类模型推导出 Java 实体类模型；
2. 如何以实体类（实现模型类）的形式编写 Java 实体类模型；
3. 如何基于实体类编写视图和控制器代码。

## 4.1 在 Java 中实现单值引用属性

单值引用属性（例如`Book`对象类型的出版者）允许存储对另一种类型对象（如`Publisher`）的内部引用。在创建新对象时，构造函数需要一个参数来为引用属性赋值。在 Java 等编程语言中，我们可能需要决定该值预期是对象引用还是 ID。使用 JPA 技术，我们在实体类中处理对象引用的方式如下：

```java
@Entity
@Table(name="books")
public class Book {
    private Publisher publisher;

    public Book() {}

    public void setPublisher(Publisher publisher) {
        this.publisher = publisher;
    }
}
```

## 4.2 创建 Java 实体模型

创建 Java 实体类的起点是如所示的 OO 类模型。我们通过以下步骤获取 Java 实体类：(1) 将所有属性设为私有，(2) 使用适当的类型，(3) 添加 getter 和 setter，(4) 添加 toString 函数，(5) 添加用于检索、更新和删除的类级方法：

| Java 实体 |  |
| :--- | :--- |
| `Book` |  |
| `isbn` | `String` (id) |
| `title` | `String` |
| `year` | `Integer` |
| `publisher` | `Publisher` (manyToOne) |
| `checkISBNAsId(String, EntityManager)` | `ConstraintViolation` |
| `toString()` | `String` |
| `retrieveAll(EntityManager)` | `List<Book>` |
| `retrieve(EntityManager, String)` | `Publisher` |
| `create(EntityManager, String, Integer, Publisher)` | `void` |
| `update(EntityManager, String, Integer, Publisher)` | `void` |
| `delete(EntityManager, String)` | `void` |

## 4.3 新问题

与之前讨论的单类应用相比，我们必须处理许多新问题：

1. 在模型代码中，我们现在需要处理引用属性：
   1. 使用合适的 JPA 注解定义完整性约束；
   2. 考虑到引用属性扩展创建、更新和删除方法的代码；
   3. 在序列化和反序列化操作中转换（内部）对象引用和（外部）ID 引用的方法。
2. 在用户界面（视图）代码中，我们现在需要处理：
   1. 在检索/列出所有的用例中显示有关关联对象的信息；
   2. 在创建对象和更新对象的用例中，允许从目标类的所有现有实例列表中选择关联对象。

## 4.4 编写模型代码

可以直接编写 Java 实体类以获取我们 Java 后端应用的模型层代码。

### 4.4.1 总结

1. 将 Java 实体类中的每个类编码为相应的实体类。
2. 使用 JPA 注解`@Id`编写属性修饰符。
3. 为引用属性的功能类型的属性修饰符（如`[manyToOne]`）编写 JPA 注解，如`@ManyToOne`。
4. 使用 Java Bean 验证注解（或自定义验证注解）对模型中指定的完整性约束编写代码。
5. 编写 getter 和 setter。
6. 作为类级方法编写创建、检索、更新和删除存储操作。

### 4.4.2 为实体模型中的每个类编写代码

Java 实体类模型中的每个类都被编码为一个带注解的 Bean 类，名称为`C`，它具有一个默认构造函数（无参数）以及一个带有实体创建参数的构造函数。

例如，来自实体类中的`Book`类是以以下方式编码的：

```java
@Entity @Table(name="books")
@ViewScopedBean(name="book")
public class Book {
    @Id @NotNull(message="An ISBN is required")
    private String isbn;

    @Column(nullable=false)
    @NotNull(message="A title is required!")
    private String title;
}
```

`publisher`上的`@ManyToOne`注解用于指定`Book`与`Publisher`之间关联的功能类型（由引用属性`publisher`表示），因为它认为一本书对应有一个出版社，而一个出版社有许多本书。该注解还允许通过参数指定获取类型，该参数可以取以下两个值之一：

- `FetchType.EAGER`：意味着检索实体时包含检索该实体属性引用的关联实体。在我们的示例中，这意味着当检索一个`Book`实体时，由书的`publisher`属性引用的`Publisher`实体也会被检索。这种行为非常有用，当要检索的数据可以在主内存中处理时，应该使用它。

- `FetchType.LAZY`：意味着在检索时不会自动检索引用的实体。在我们的示例中，这意味着引用的`Publisher`不随引用实体一起检索，导致`publisher`属性的值为`null`。通过这种获取行为，引用的实体是在事务范围内通过调用引用属性的 getter（在我们的示例中是通过调用`getPublisher`）单独检索的。

对于标有`@OneToOne`或`@ManyToOne`注解的单值引用属性（表示功能性关联），其默认值为`FetchType.EAGER`，因此引用的实体会与引用实体一起获取；而在非功能性关联（使用`@OneToMany`或`@ManyToMany`）的情况下，默认值为`FetchType.LAZY`，因此引用的实体不会与引用实体一起获取，如果需要，必须单独检索。

作为 JPA 注解的结果，将生成以下用于创建表的 SQL 表创建语句：

```sql
CREATE TABLE IF NOT EXISTS `books` (
  `ISBN` varchar(10) NOT NULL,
  `TITLE` varchar(255) NOT NULL,
  `YEAR` int(11) NOT NULL,
  `PUBLISHER_NAME` varchar(255) DEFAULT NULL,
  FOREIGN KEY (`PUBLISHER_NAME`) REFERENCES `publishers` (`NAME`)
);
```

### 4.4.3 编写约束

请确保实体类模型中指定的所有属性约束都使用合适的 Bean Validation 注解进行了正确编码。例如，对于属性名称，我们必须使用 JPA 注解`@Id`来指定该属性对应于映射的数据库表的主键列，并使用 Bean Validation 注解`@NotNull`来定义强制性值约束，该约束在实体保存到数据库之前会进行检查。

在`address`属性的情况下，我们必须以两种形式定义强制性值约束：使用 JPA 注解`@Column(nullable=false)`对应表列，以及使用 Bean Validation 注解`@NotNull`对应属性。

```java
@Id
@NotNull(message="A name is required!")
private String name;

@Column(nullable=false)
@NotNull(message="An address is required!")
private String address;
```

注意，遗憾的是，目前的 Java EE 技术要求定义两次相同的约束：一次是以 JPA 注解的形式针对数据库，另一次是以 Bean Validation 注解的形式针对 Java 应用。

### 4.4.4 编写 Getter 和 Setter

编写 setter 操作（实例级）方法。setter 仅负责赋值且不执行任何验证，因为属性约束仅由 Java EE 执行环境在`save`之前进行检查。getter 则简单地返回属性的实际值。

### 4.4.5 实现删除策略

对于任何引用属性，我们需要在事务上下文中实现删除策略。在我们的示例中，我们需要在以下两者之间选择：

- 删除出版社
- 删除包含所有书籍的出版社

我们选择删除所有书籍的出版社，这在`delete`方法中的实现所示：

```java
public static void delete(EntityManager em, UserTransaction ut, String name) {
  ut.begin();
  Publisher publisher = em.find(Publisher.class, name);
  Query query = em.createQuery(
    "SELECT b FROM Book b WHERE b.publisher = :name");
  query.setParameter("name", name);
  List<Book> books = query.getResultList();
  for (Book b : books) {
    b.setPublisher(null);
  }
  em.remove(publisher);
  ut.commit();
}
```

### 4.4.6 序列化与反序列化

根据 JPA 注解，配合合适的转换器类，序列化（从 Java 对象到表行）以及相应的反序列化（从表列到 Java 对象）将自动完成。

## 4.5 视图与控制器层

用户界面（UI）由导航到管理页面的起始页以及每个对象类型的管理页面组成。所有 UI 页面以 JSF 文件的形式定义在`views`子目录下。我们在`WebContent/views`中创建主页`index.xhtml`，内容如下：

```xml
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:ui="http://java.sun.com/jsf/facelets"
      xmlns:f="http://java.sun.com/jsf/core">
  <ui:composition template="/WEB-INF/templates/page.xhtml">
    <ui:define name="content">
      <h2>Public Library</h2>
      <h:button value="Manage publishers" outcome="/views/publishers/index" />
      <h:button value="Manage books" outcome="/views/books/index" />
      <h:form>
        <h:commandButton value="Clear database"
          action="#{appCtrl.clearData()}" />
        <h:commandButton value="Create test data"
          action="#{appCtrl.createTestData()}" />
      </h:form>
    </ui:define>
  </ui:composition>
</html>
```

此外，我们需要创建一个相应的`AppController`类，负责测试数据的创建和删除。该控制器用于整合`Publisher.createTestData`、`Book.createTestData`以及`Publisher.clearData`方法如下：

```java
@ManagedBean(name="appCtrl")
@SessionScoped
public class AppController {
    @PersistenceContext(unitName="UnidirAssocApp")
    private EntityManager em;

    @Resource
    UserTransaction ut;

    public String clearData() {
        try {
            Book.clearData(em, ut);
            Publisher.clearData(em, ut);
        } catch (Exception e) {
            e.printStackTrace();
        }
        return "index";
    }

    public String createTestData() {
        try {
            Publisher.createTestData(em, ut);
            Book.createTestData(em, ut);
        } catch (Exception e) {
            e.printStackTrace();
        }
        return "index";
    }
}
```
