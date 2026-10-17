
## 9.1 用于持久数据管理和约束验证的 Java 注解

```java
CREATE TABLE IF NOT EXISTS items (
itemCode varchar(10) NOT NULL PRIMARY KEY,
quantity int(11) NOT NULL
)
```

## 9.2 Bean Validation 注解

在 Java EE 验证方法中，Java 运行时验证可以以后放在属性、方法或类上的 Bean 验证注解的形式定义。

表 9.1 属性的 Bean Validation 注解

| 约束类型 | 注解 | 示例 |
|---|---|---|
| 字符串长度约束 | `@Size` | `@Size(min=8, max=80) String message;` |
| 基数约束（针对数组、集合和映射） | `@Size` | `@Size(min=2, max=3) List<Member> coChairs;` |
| 强制性值约束 | `@NotNull` | `@NotNull String name` |
| 数值型属性的范围约束 | `@Digits` | `@Digits(integer=6, fraction=2) BigDecimal price;` |
| 整数值属性的间隔约束 | `@Min` 和 `@Max` | `@Min(5) int teamSize` |
| 小数值属性的间隔约束 | `@DecimalMin` 和 `@DecimalMax` | `@DecimalMax("30.00") double voltage` |
| 模式约束 | `@Pattern` | `@Pattern(regexp="\\d(10)\\\") String isbn;` |

此外，还有一些注解要求日期值在未来（`@Future`）或过去（`@Past`）。

所有 Bean Validation 注解都有一个可选的 `message` 属性，用于定义自定义错误消息。在下文中，我们为 JPA 约束注解添加了两个带有消息的 `@NotNull` 注解和一个 `@Min` 注解。`@NotNull` 注解约束 `itemId` 和 `quantity` 属性为强制，而 `@Min` 注解约束 `quantity` 属性的最小值为 0：

```java
@Entity(name="items")
public class Item {
    @Id Column(length=8)
    @NotNull(message="An item code is required")
    @Size(min=8, max=8)
    private String itemCode;
    @Column(nullable=false)
    @NotNull(message="A quantity is required!")
    @Min(0)
    private int quantity;
}
```

注意，在这个示例中我们需要一些重复逻辑，因为相同的约束可能定义两次：一次作为 JPA 约束，一次作为 Bean Validation 约束。例如，对于像 `quantity` 这样的强制属性，我们既有 `@Column(nullable=false)` JPA 约束注解，又有 `@NotNull` Bean Validation 注解。

## 9.2 新问题

与第 4 章讨论的最小应用程序² 相比，我们必须处理许多新问题：

1. 在模型层中，我们必须为每个属性添加约束，在允许记录保存到数据库之前必须进行检查。
2. 在用户界面（视图）中，我们必须处理表单验证，当表单中输入的数据无效时向用户提供反馈。

在用户界面上对用户输入进行约束检查对于为用户提供即时反馈很重要。使用 JSF 和 Bean Validation 需要在执行验证检查之前提交表单。理想做法是仅在模型类中定义验证检查，并在表单提交前在用户界面中使用它们，而不需要在 JSF Facet 中重复验证逻辑。然而，目前 JSF 不支持这一点，验证仅在表单提交后才执行。

在 JSF Facet 使用 HTML5 验证属性在提交表单之前强制执行 HTML5 验证会导致不希望的验证逻辑重复。这种重复的影响会导致验证代码的重复维护，一次在模型类中，另一次在用户界面中。对于像我们的示例应用这样的简单应用程序，这是可行的，但在较大的应用程序中这很快就会变成维护噩梦。

> 2 http://web-engineering.info/tech/JavaJsfApp/MinimalApp/index.html

## 9.3 创建一个实体类模型

以图 7.2 所示的信息设计模型为起点，我们创建一个带有 getter/setter 和对应 Java 数据类型的**实体类模型**。

![](img/42f1421051423f5b9e022255ae58c362_180_0.png)

图 9.1 从信息设计模型派生实体类模型

图 9.1 右侧所示的实体类模型为所有属性定义了 getter 和 setter，并包含以下属性约束：

1. 使用 `@Id` 和 `@NotNull`，`isbn` 属性被声明为标准标识符，意味着它是**强制的**且**唯一**的。
2. 使用 `@NotNull` 和 `@Size(max=50)`，`isbn` 属性具有**模式**约束，要求其值必须匹配 ISBN-10 格式（简化为 10 位字符串的情况）。
3. 使用 `@NotNull`，`title` 属性是**强制的**，且字符串长度最大为 50 个字符。
4. 使用 `@NotNull`、`@Min(1459)` 和自定义注解 `@UpToNextYear`，`year` 属性是**强制的**，并具有**间隔约束**，这是一种特殊形式，最大值不是固定的，而是由实现日历算术函数 `nextYear()` 的自定义注解提供的。

由于没有预定义的用于年份唯一性的注解，我们在第 6 节为该约束定义了自定义注解。

## 9.4 在 Java EE Web 应用中实现验证

## 9.4 编写模型代码

在本节中，我们为属性添加 JPA 约束注解和 Bean Validation 注解。我们首先根据下表映射平台无关的类型。

表 9.2 类型到 Java

| 平台无关类型 | Java 类型 |
|---|---|
| String | `String` |
| Integer | `long` |
| Decimal | `Double` |
| Boolean | `Boolean` |
| Date | `Date` |

对于小数的精确计算，对应的数据类型需要第二次映射：

表 9.3 类型到 MySQL

| 平台无关类型 | MySQL 数据类型 |
|---|---|
| String | `VARCHAR` |
| Integer | `INT` |
| Decimal | `DECIMAL` |
| Boolean | `BOOL` |
| Date | `DATETIME` or `TIMESTAMP` |

## 9.4.1 使用注解编码约束

在以下类中使用 JPA 注解和 Bean Validation 编码完整性约束：

```java
@Entity(table="books")
@ManagedBean(name="book")
public class Book {
    @Id(length=10)
    @NotNull(message="ISBN value is required!")
    @Pattern(regexp="\\d(10)\\\", message="The ISBN must be a 10-digit string!")
    private String isbn;
    @Column(nullable=false)
    @NotNull(message="A title is required!")
    @Size(max=255)
    private String title;
    @Column(nullable=false)
    @NotNull(message="A year is required!")
    @Min(value=1459, message="The year must not be before 1459!")
    private Integer year;

    // 构造函数、setter 和 getter

    public static Book getObjectById(...) {...}
    public static List<Book> getAllObjects(...) {...}
    public static void create(...) throws Exception {...}
    public static void update(...) throws Exception {...}
    public static void delete(...) throws Exception {...}
}
```

注意，对于 `year` 属性，使用了 Java `Integer` 包装类而不是原始 `int` 数据类型。这对于使用 JSP 和 JPA 是必要的，因为如果在创建或更新表单中提交了空输入字段的值，通过 `setYear` 方法传递给 `year` 属性的值将是 null（详情见第 4.5 节“要求非空字符串”），这对于 Java 的原始数据类型是不允许的。

# 9 在 Java EE Web 应用中实现约束校验

我们仅提供方法的概述。更多详细信息，请参阅第 4 章。

## 9.4.3 检查唯一性约束

为了避免重复的 Book（书籍）记录，我们必须检查 `isbn` 值是唯一的。在数据库层面，由于 `isbn` 列是主键，这已经通过检查，DBMS 会确保其值的唯一性。然而，我们希望在数据传递给 DBMS 之前在 Java 程序中进行此检查。遗憾的是，没有用于此功能的 Bean Validation 注解，而且并不清楚如何通过自定义验证注解来实现。我们需要编写一个静态方法 `Book.checkIsbnAid` 来检查 `isbn` 属性的值是否唯一。该方法可以由控制器在创建新的 Book 记录之前对任何 `isbn` 属性进行验证。`Book.checkIsbnAid` 方法所示：

```java
public static void checkIsbnAid(EntityManager em, String isbn)
throws UniquenessConstraintViolation,
MandatoryValueConstraintViolation {
    if (isbn == null) {
        throw new MandatoryValueConstraintViolation(
            "An ISBN is required!");
    } else {
        Book book = Book.retrieve(em, isbn);
        // book was found, uniqueness constraint validation failed
        if (book != null) {
            throw new UniquenessConstraintViolation(
                "There is already a book record with this ISBN!");
        }
    }
}
```

如果为给定的 `isbn` 值找到了 Book 记录，该方法将抛出 `UniquenessConstraintViolation` 异常。可以捕获该异常并在 UI 中显示相应的错误消息。在本章的后续部分，我们将展示如何定义验证方法并通知 JS facelets 必须使用它来校验 `isbn` 表单输入。

请注意，在这种情况下，我们还需要检查 `isbn` 值并拒绝空值，因为 `@NotNull` 校验只有稍后触发（即当 Book 的 `isbn` 属性被设置时），因此在此时我们可能会从 `Book.retrieve` 方法得到 `NullPointerException`。

## 9.4.4 处理与模型相关的异常

上一个小节讨论的 `Book.checkIsbnAsId` 方法设计用于结合控制器使用，以便用户在尝试重复 Book 记录时（即如果 `isbn` 值已在现有记录中使用）能够收到错误消息。然而，如果直接使用 `Book.create` 方法（例如通过其他代码段，其中没有通过调用 `Book.checkIsbnAsId` 执行唯一性校验），则唯一性校验可能会失败。让我们来看 `Book.create` 的代码：

```java
public static void create(EntityManager em, UserTransaction ut,
String isbn, String title, int year)
throws UnsupportedException, SystemException,
IllegalStateException, SecurityException,
HuristicMixedException, HeuristicRollbackException,
ExistsException {
    Book book = new Book(isbn, title, year);
    em.persist(book);
    ut.commit();
}
```

该方法在尝试运行 `persist` 或 `commit` 方法时可能会抛出多个异常。其中一个异常（即 `EntityExistsException`）是由 `ut.commit` 抛出的。调用 `Book.create` 的方法可以捕获此异常并执行特定操作，例如回滚事务。在我们的情况下，`Book.create` 是由 `create` action 调用的，执行的操作是在 Controller 类和控制台中显示异常堆栈跟踪，并调用 `ut.rollback`，后者负责取消当前事务执行的任何数据库更改。其余异常由其父类（即 `Exception`）捕获，异常堆栈跟踪显示在控制台中。

```java
public String create(String isbn, String title, int year) {
    try {
        Book.create(em, ut, isbn, title, year);
    } catch (EntityExistsException e) {
        try {
            ut.rollback();
        } catch (Exception e) {
            e.printStackTrace();
        }
        e.printStackTrace();
    } catch (Exception e) {
        e.printStackTrace();
    }
    return "create";
}
```

注意：`EntityExistsException` 是 `javax.persistence` 包的一部分（即 `javax.persistence.EntityExistsException`）。TomEE 使用 Apache OpenJPA 的 JPA API 实现，这使得 `EntityExists` 类（以及其他异常类）成为 `org.apache.jpa.persistence` 包的一部分。因此，在我们的代码中使用此异常需要导入 `org.apache.persistence.EntityExistsException` 而不是 `import javax.persistence.EntityExistsException`，并将 `openjpa-xxx.jar`（位于 TomEE 安装文件夹的 lib 子文件夹中）添加到 Java 类路径中，以便能够使用 Eclipse 或其他 IDE 工具编译代码。

## 9.4.5 要求非空字符串

通常，像 `title` 这样的强制性字符串值属性需要非空字符串，这在我们的模型中通过范围 `NonEmptyString` 表示。为了将字符串视为无值，必须在 `web.xml` 中 `javax.faces.INTERPRET_EMPTY_STRING_SUBMITTED_VALUES_AS_NULL` 的上下文路径为 `true`：

```xml
<context-param>
    <param-name>javax.faces.INTERPRET_EMPTY_STRING_SUBMITTED_VALUES_AS_NULL</param-name>
    <param-value>true</param-value>
</context-param>
```

此外，对于验证逻辑，我们还需要处理以下代码片段中的条件检查：

```java
if (name === undefined) {
    return "A name is required!";
} else if (typeof name !== "string" || name.trim() == "") {
    return "Name must be a non-empty string!";
} else if (age !== undefined) {
    if (!Number.isInteger(age) || age < 0) {
        return "age must be a non-negative integer!";
    }
}
return ""; // no error
```

以及：

```java
} else if (age !== undefined) {
    if (!Number.isInteger(age) || age < 0) {
        return "age must be a non-negative integer!";
    }
}
return ""; // no error
```

1 http://docs.oracle.com/javaee/7/tutorial/doc/bean-validation001.htm#GIRCZ

## 162 — 9 在 Java EE Web 应用中实现约束验证
