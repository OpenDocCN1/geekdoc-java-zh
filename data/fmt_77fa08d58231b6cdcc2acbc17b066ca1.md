
```java
@Entity @Table(name="books")
@ViewScoped @ManagedBean (name="book")
public class Book {
    .

    @ManyToOne (fetch=FetchType.EAGER)
    private Set<Author> authors;

    public Book() {}
    public Book(String isbn, String title, Integer year,
    Publisher publisher, Set<Author> authors) { . . }
    .
    public Set<Author> getAuthors() { return this.authors; }
    public void setAuthors(Set<Author> authors) { this.authors=authors; }
}
```

JPA 注解 `@ManyToMany` 允许指定 `Book` 和 `Author` 之间的多对多关系。使用了参数 `FetchType.EAGER`，因此当创建 `Book` 实例时，作者列表会被相应的 `Author` 实例填充。

## 5.4 编写模型代码 — 71

由于此注解的作用，会创建一个 `Book` 和 `Author` 之间的关系表，生成的 SQL 如下：

```sql
CREATE TABLE IF NOT EXISTS books_author (
  `ISBN` varchar(10) NOT NULL,
  `personID` int NOT NULL
);
```

# 使用 Java EE 的 5 种单向非功能关联

### 5.5 编写用户界面代码

#### 5.5.1 在“检索/列出所有”中显示关联对象的信息

为了在检索/列出所有用例中显示书籍作者，HTML 表格中对应的单元格必须填充所有作者名称的列表。为此，我们在 `Book` 类中实现了一个方法，返回序列化的作者名称列表（格式为 `authorName_1, authorName_2, ..., authorName_n`）：

```java
public String getAuthorNames() {
  String result = "";
  int i = 0, n = 0;
  if (this.authors != null) {
    n = this.authors.size();
    for (Author author : this.authors) {
      result += author.getName();
      if (i< n-1) {
        result += ",";
      }
      i++;
    }
  }
  return result;
}
```

在 `WebContent/views/books/` 文件夹下的 `retrieveAndListAll.xhtml` 文件中，该方法在“Authors”列的 JSF 表达式中调用：

```xml
<ui:composition template="WEB-INF/templates/page.xhtml">
  <ui:define name="content">
    <h:dataTable value="#{bookController.books}" var="b">
      <h:column>
        <f:facet name="header">Publisher</f:facet>
        #{b.publisher.name}
      </h:column>
      <h:column>
        <f:facet name="header">Authors</f:facet>
        #{b.authorNames}
      </h:column>
    </h:dataTable>
```

```xml
<h:button value="Back" outcome="index" />
</ui:define>
</ui:composition>
```

回想使用 `b.authorNames` 会导致调用给定 `b` 对象上名为 `getAuthor` 的方法。

#### 5.5.2 在“创建”中允许选择关联对象

为了在创建书籍用例中允许选择多个作者与书籍关联，需要一个多选择列表（带有 `multiple="multiple"` 的 select 元素），如 facet 列所示，它由关联对象类型的实例填充。以下代码是 `WebContent/views/` 文件夹下 `create.xhtml` 视图文件的部分：

```xml
<ui:template template="WEB-INF/templates/page.xhtml">
<ui:define name="content">
<h:form id="createBookForm">
  <h:panelGrid columns="3">
  <h:outputLabel for="authors" value="Authors"/>
  <h:selectManyListBox id="authors" value="#{book.authors}">
    <f:selectItems value="#{authorController.authors}" var="a"
      itemLabel="#{a.name}" itemValue="#{a}"/>
    <f:converter converterId="AuthorConverter"/>
  </h:selectManyListBox>
  <h:message for="authors" error="error"/>
</h:panelGrid>
<h:commandButton value="Create" action="#{authorController.create(book.isbn, book.title, book.year, book.publisher, book.authors)}"/>
<h:button value="Back" outcome="index" />
</h:form>
</ui:define>
</ui:composition>
```

记住我们必须为 `Author` 模型类添加 `equals` 方法。在我们的案例，如果两个作者的 `personId` 属性值相等，则认为他们是“同一个”：

```java
@Override
public boolean equals(Object obj) {
    if (obj instanceof Author) {
        Author author = (Author) obj;
        return (this.personId.equals(author.personId));
    } else return false;
}
```

与 `Publisher` 的情况一样，使用 JSF 转换器类将对象序列化为显示字符串（当填充选择列表时），并在调用 `BookController` 的 `create` 方法时（用户点击“Create”按钮时）转换回对象。`BookController.create` 方法扩展了一个新参数：作者列表：

```java
public String create(String isbn, String title, Integer year,
    Publisher publisher, Set<Author> authors) {
    try {
        Book.create(em, ut, isbn, title, publisher, authors);
        // 在创建 Book 记录后强制清空表单
        FacesContext facesContext = FacesContext.getCurrentInstance();
        facesContext.getContext().getRequestMap().remove("book");
        try {
            ut.rollback();
        } catch (Exception e1) {
            e1.printStackTrace();
        }
        e.printStackTrace();
    } catch (Exception e) {
        e.printStackTrace();
    }
    return "create";
}
```

更新书籍用例与创建书籍用例类似。

## 5.6 运行应用并获取代码

运行你的应用，你可能需要先停止 Tomcat/TomEE 服务器（Windows 使用 `bin/shutdown.bat`，Linux 使用 `bin/shutdown.sh`）。接下来，下载并解压包含应用所有源码的 ZIP 包，以及

## 5.7 引用属性的值：Set 与有序 Set

你需要编辑的 ANT 脚本文件（修改 `server.folder` 属性值）。

现在，在控制台或终端中执行部署命令：

```bash
ant deploy -Dappname=UnidirectionalAssociationApp
```

最后，启动你的 Tomcat 服务器（Windows 使用 `bin/shutdown.bat`，Linux 使用 `bin/shutdown.sh`）。这可能需要一些时间，当控制台显示以下内容时即为就绪：Initializing [some library versions...]。最后，打开浏览器访问：http://localhost:8080/UnidirectionalAssociationApp/WebContent/views/index.xhtml

### 引用属性的值：Set 与有序 Set

`Set` 是无序集合且元素是唯一的，而 `List` 是有序集合且允许重复元素。当关联是有序的，如图 5.1 中的 `authors`，这意味着其的范围需要是一个有序集合类型，例如 `SortedSet` 或 `List`。

| Book | authored | Author |

| --- | --- | --- |

| isbn : String | | personid: Integer |

| title : String | | name: String |

| year : Integer | | |

| | (ordered) | |

从理论上讲，集合属性应该使用 `Set<T>` 定义（例如将 `Set<Book>` 作为 `authored` 的范围），而有序集合属性应该使用 `SortedSet<T>` 定义（例如将 `SortedSet<Author>` 作为 `authors` 的范围）。Java 类型通常由 `HashSet` 实现，而 `SortedSet` 通常由 `TreeSet` 实现。

然而，如果不担心重复元素，集合属性和有序集合属性都可以使用泛型接口 `List<T>` 定义其范围，其通常由 `ArrayList` 实现。

# 6 单向关联练习项目

所有项目都包含以下任务：

1. 根据给定的设计模型建立类模型。提示：将关联替换为相应的引用属性。

2. 根据类模型建立 JavaScript 类模型或 Java Entity 模型。提示：添加 getter 和 setter 方法。

3. 按照指南编写你的 JS 类模型或 Java Entity 模型。

确保你的页面符合 HTML5 的 XML 语法，且 JavaScript 代码符合指南并经过 JSHint 检查。

### 6.1 为电影分配导演和演员

此项目基于下方所示的信息设计模型。需要扩展之前的应用，增加管理电影演员和导演数据的功能。这通过添加 `Person` 模型类以及 `Movie` 与 `Person` 之间的两个单向关联来实现：

1. 多对一关联，分配恰好一个人作为电影导演；以及

2. 多对多关联，分配零或多个个人作为电影的演员。

![](img/64ab58e459ff4b56e7fc22fe3998651a_95_0.png)

你可以使用以下示例数据来测试你的应用程序：

| 电影 ID | 标题 | 上映日期 | 导演 | 演员 |

| --- | --- | --- | --- | --- |

| 1 | 《低俗小说》 | 1994-05-12 | 3 | 4, 5 |

| 2 | 星战 | 1977-05-25 | 2 | 6, 7 |

| 3 | 危险的关系 | 1988-12-16 | 1 | 8, 4 |

| 人员 ID | 姓名 |

| --- | --- |

| 1 | Stephen Frears |

| 2 | George Lucas |

| 3 | Quentin Tarantino |

| 4 | Uma Thurman |

| 5 | John Travolta |

| 6 | Ewan McGregor |

| 7 | Natalie Portman |

| 8 | Keanu Reeves |

更多电影数据可以在 IMDb 网站找到。

## 6.2 为国家分配城市和首都，为组织分配成员

该项目基于下方所示的信息设计模型。之前作业中的相应应用程序将通过扩展，增加管理国际组织（及其成员）以及作为首都和总部地的城市数据的功能。这是通过添加相应的模型类 `InternationalOrganization` 和 `City`，以及以下内容实现的：

1. `InternationalOrganization` 与 `Country` 之间的多对多关联，将零或多个国家分配为国际组织的成员；以及

2. `Country` 与 `City` 之间的一一关联，将恰好一个城市分配为国家的首都；

3. `Country` 与 `City` 之间的一对多关联，将城市分配给国家。

![](img/64ab58e459ff4b56e7fc22fe3998651a_97_0.png)

你可以使用以下示例数据来测试你的应用程序：

| 缩写 | 名称 | 成员 |

|---|---|--|

| UN | 联合国 | 德国、法国、俄罗斯 |

| WHO | 世界卫生组织 | 德国、法国、俄罗斯 |

| NATO | 北西洋公约组织 | 德国、法国 |

| 名称 | 首都 | 城市 |

|---|---|--|

| 法国 | 巴黎 | 马赛、里昂、巴黎 |

| 德国 | 柏林 | 柏林、汉堡、法兰克福 |

| 俄罗斯 | 莫斯科 | 莫斯科、新西伯利亚 |

| 名称 |

|---|

| 柏林 |

| 法兰克福 |

| 汉堡 |

（上上）

| 城市 |

| --- |

| 里昂 |

| 马赛 |

| 莫斯科 |

| 新西伯利亚 |

| 巴黎 |

更多关于国家的数据可以在 CIA 世界事实库中找到。

# 7 双向关联

在面向对象建模和编程中，双向关联是指表示为一对互反引用属性的关联，它允许在两个方向上进行“导航”（对象访问）。

下方图 7.1 所示的模型（关于出版社、书籍及其作者）作为我们的运行示例。请注意，它包含了两个双向关联，如关联两端的所有权点所示。

| 出版社 | 出版书籍 | 书籍 | 编写书籍 | 作者 |

| --- | --- | --- | --- | --- |

| name : String (id) | | isbn : String (id) | * | personid : Integer (id) |

| address : String | 0.1 | * | year : Integer | * | name : String |

图 7.1: 具有两个双向关联的出版社-书籍-作者信息设计模型。

## 7 反向引用属性

为了能够轻松检索由俱乐部成员担任或共同主席的委员会，我们在 `Committee-ClubMember` 示例中添加了两个引用属性：成员担任委员会主席的属性（`ClubMember::chairedCommittee`）和成员担任委员会共同主席的属性（`ClubMember::coChairedCommittee`）最多可以担任一个委员会（这里的析关系是非排他的）。因此，我们得到了如下模型：

| 委员会 | 俱乐部成员 |

| --- | --- |

| name : String | chairedCommittee[0..] : Committee |

| chair : ClubMember | coChairedCommittee[0..] : Committee |

注意，`Committee::chair` 和 `ClubMember::chairedCommittee` 这两个引用属性之间存在密切对应关系。它们是互反的：当俱乐部成员 Tom 是预算委员会主席时（用元组 ("budget committee", "Tom") 表示），那么该预算委员会由俱乐部成员 Tom 主持（用反向元组 ("Tom", "budget committee") 表示）。为了在图中表示这种反向对应关系，我们在 `ClubMember::chairedCommittee` 属性的声明中添加了大括号括起来的反向约束 `inverse of chair`，并在 `Committee::chair` 属性中添加类似的约束，如下图所示：

| 委员会 | 俱乐部成员 |

|--- |--- |

| name : String | chairedCommittee[0..1] : Committee |

| chair : ClubMember (inverse of chairedCommittee) | coChairedCommittee[0..1] : Committee |

使用面向对象语言的引用路径表示，用 `c` 引用 `Committee` 对象，我们得到方程：

```
c.chair.chairedCommittee = c (7.1)
```
