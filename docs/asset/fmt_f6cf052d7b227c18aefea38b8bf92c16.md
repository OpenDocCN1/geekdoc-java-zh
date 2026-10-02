
使用 UTF-8 编码处理所有 HTML 文件以支持国际字符。

你的 JavaScript 代码符合我们的编码指南⁰，并使用 JSHint¹¹ 检查其样式（例如，与其使用不安全的 `==` 等值测试，必须始终使用严格的 `===` 等值测试）。

如果你对如何执行后续项目有任何疑问，可以在我们的讨论论坛²提问。

### 31.1.1 项目 1 – 管理电影信息

要开发的应用目的是管理电影信息。该应用只处理一种对象类型：`Movie`（电影），如下类图所示：

| Movie |
| :--- |
| `movieId: Integer` |
| `title: String` |
| `releaseDate: Date` |

注意，在 `Movie` 类中有一个属性 `Date`，它是一种特殊数据类型，在第 3 章中讨论过。你可以使用表 3.2 中的示例数据用于你的应用。

| Movie ID | Title | Release |
| :--- | :--- | :--- |
| 1 | Pulp Fiction | 1994 |
| 2 | Star Wars | 1977 |
| 3 | Casablanca | 1943 |
| 4 | The Godfather | 1972 |

### 31.1.2 项目 2 – 管理国家信息

要开发的应用目的是管理国家信息。该应用只处理一种对象类型：`Country`（国家），如下图所示：

```
Country
name: String
population: Integer
lifeExpectancy: Decimal
```

你可以使用表 3.3 中的示例数据用于你的应用。

| Name | Population | Life expectancy |
| :--- | :--- | :--- |
| Germany | 80,854 | 80 |
| France | 66,536 | 81 |
| Russia | 142,223 | 70 |
| Monaco | 30,535 | 89 |

## 4.1 Java 基础 59

一个数据管理应用需要什么？有四种标准的用例必须被应用支持：

- **创建（Create）**一个新的书籍记录，允许用户输入书籍数据并将其添加到存储的书籍集合中。
- **检索（Retrieve）**（或读取）数据存储器中的所有书籍并以列表的形式显示。
- **更新（Update）**书籍记录的数据。
- **删除（Delete）**书籍记录。

这四个标准用例以及对应的数据管理操作，通常借助计算机的键盘和屏幕来总结。为了通过键盘输入数据，我们使用 **HTML 表单**，它为 Web 应用程序提供了**用户界面**技术。

对于任何数据管理应用，我们都需要一种技术，允许数据存储在辅助存储设备（如硬盘或 SSD）的持久记录中。JPA 使用了大量不同的数据技术，包括许多 SQL 数据库管理系统（DBMS），如 Oracle、MySQL 和 PostgreSQL。切换存储技术时，我们不需要更改应用程序代码。只需向 Java 运行时添加正确的驱动程序实现，正确设置 DBMS 并更改数据库访问配置，通常就是我们需要做的一切。在我们的示例应用中，我们将解释如何为 MySQL 设置 JPA 配置。

## 4.1 Java 基础

与 JavaScript 相比，Java 有何不同？我们列出了一些观察结果：

- **没有类就没有程序**：任何 Java 程序必须包含一个类。
- **Java 是强类型的**：属性、参数和变量必须声明某种类型。
- **没有全局变量、全局过程**：在 Java 中，变量、过程和函数必须定义在类的范围内，类为我们提供了命名空间。
- **数组是静态的**：数组具有固定的大小，在运行时无法更改。
- **没有类就没有对象**：为了创建对象，必须使用类（或为之定义类）来定义对象槽位的属性，并定义可以应用于对象（以及实例化该类的其他对象）的方法和函数。
- **类**、属性和方法通过**可见性**级别（`public`、`protected` 或 `private`）进行定义，这限制了它们的访问权限性。

# 4 使用 Java EE 通过七个步骤构建最小化应用

- 类型参数：类和复杂数据结构（如列表）可以借助类型参数进行定义。例如，参见 Oracle 的泛型教程⁵。
- Java 程序在执行之前必须经过编译。
- 速度：Java 的速度大约是优化过的 JavaScript 的倍。

在 Java 中，可见性级别用于定义可能的访问级别：

表 4.2 Java 可见性级别

| 类 | 包 | 子类 | 世界 |
| --- | --- | --- | --- |
| `public` | y | | y |
| `protected` | y | y | n |
| 无修饰符 | y | y | n |
| `private` | y | n | n | n |

通常情况下，属性被定义为 `private`，因为它们只能通过公共的 setter 进行赋值，这允许控制并可能记录属性值的任何变化。遗憾的是，Java 不允许只保护写访问而不允许读访问。因此，即使不需要，我们也必须定义带有 setter 的 getter。

Bean 类（或简单地称为 bean 类）是一个带有无参数构造函数的 Java 类，其中所有属性都具有 get 和 set 方法（也称为 "getter" 和 "setter"）。Java bean 是通过 bean 类创建的对象。

JPA 实体类（或简单称为实体类）是带有 `@Entity` 注解的 Java bean 类，这意味着 Java EE 运行时（例如由 Tomcat PLUS Web 服务器提供的）将负责其实例的持久化存储。

JPA 是用于管理 Java 中持久数据的 Java API。它使用持久查询语言（JQL）。JPA 查询表达式基于 SQL。JQL 查询表达式看起来与 SQL 查询表达式非常相似，但在 JPA 实体对象的环境中执行。

JSF 是一种用于为 Web 应用程序构建组件用户界面的 Java 规范。它的当前版本 JSF 2 默认使用 Facelets 作为视图技术。相比之下，JSF 1 使用服务器页面（JSP）作为默认视图技术。

JSF facelet 是一个基于 XML 的模板，结合了静态 UI 内容项和数据变量，以生成 XHTML 用户界面。

## 4.2 第一步 – 设置文件夹结构

在第一步中，我们为应用程序代码设置文件夹结构。应用名称为 "Public Library"，因此使用相应的文件夹名称 "PublicLibrary" 是自然的，但我们倾向于使用 Minimal-App。然后我们创建应用程序结构。有很多方法可以实现，例如使用 Eclipse 开发环境（创建并配置动态 Web 项目）。在本章中，我们展示如何手动完成，因此不需要使用特殊工具。为了方便起见，我们还提供了一个 ANT 脚本（下载链接见指南），允许自动创建 Web 应用程序的文件夹结构，将其编译为 Web 应用程序包（WAR）文件并部署到 Tomcat 服务器上执行。应用程序结构（与 Eclipse 的动态 Web 项目结构兼容，因此可以导入）：

```
MinimalApp
src
  pl
  m
  c
META-INF
  persistence.xml
WebContent
resources
media
img
views
books
WEB-INF
templates
faces-config.xml
web.xml
```

该文件夹结构包含以下部分：

- `src` 文件夹包含应用代码 `pl`（作为 'public library'），以及带有文件的 `META-INF` 文件夹：
  - 应用代码 `pl` 包含模型 `m` 和控制器 `c`，而视图相关的代码位于 Web 文件夹中；
  - 最重要的配置文件是 `persistence.xml`。它包含了数据库连接。
- `WebContent` 文件夹包含各种 Web 资源，包括模板文件和自定义视图文件：
  - `resources` 文件夹用于存储文档、图像或视频。
  - `views` 文件夹包含我们的应用程序自定义视图文件，它代表了 MVC 范式的 View 部分。请注意，并不强制命名为 "views"，但这样做非常有意义，因为这就是该文件夹所代表的。
  - `WEB-INF` 文件夹包含项目库（位于 `lib` 子文件夹中的 jar 文件，如果不需要此类库）、UI 页面文件（作为 `templates` 子文件夹的一部分）、`faces-config.xml` 文件以及用于运行应用程序的 Tomcat 服务器的 `web.xml` 配置。

为应用程序创建一个 "主菜单" 页面，因此我们在 `views` 文件夹中添加了 `index.xhtml` 文件，内容如下：

```xhtml
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml"
xmlns:h="http://java.sun.com/jsf/html">
<head>
  <meta charset="UTF-8" />
  <title>Minimal App with Java and JSF</title>
</head>
<body>
  <header>
    <h1>Public Library</h1>
    <h2>Minimal App with Java and JSF</h2>
  </header>
  <main>
    <menu>
      <li><h:button value="Create" outcome="create" /> 创建新书籍</li>
      <li><h:button value="Retrieve" outcome="retrieveAndListAll" /> 列出所有书籍</li>
      <li><h:button value="Update" outcome="update" /> 更新书籍</li>
      <li><h:button value="Delete" outcome="delete" /> 删除书籍</li>
    </menu>
    <hr />
    <form>
      <menu>
        <li><h:commandButton value="Clear"
action="#{bookCtrl.clearData()}" /> 清空数据库</li>
        <li><h:commandButton value="Generate"
action="#{bookCtrl.generateTestData()}" /> 生成测试数据</li>
      </menu>
    </form>
  </main>
</body>
</html>
```

## 4.3 第 2 步 – 编写模型代码

```html
<!-- copyright text -->
</footer>
<body>
</html>
```

该代码由 HTML 元素和 JSF 元素组成，下将对其进行讨论。

## 4.3 第 2 步 – 编写模型代码

在第二步中，我们为应用程序创建模型类，为每个模型类使用独立的 Java 源代码文件（扩展后缀为 `.java`）。在上方图 4.1 所示的信息设计模型中，只有一个类，代表对象类型 `Book`。因此，我们在 `src/pl/m` 文件夹中创建一个 `Book.java` 文件，代码内容如下：

```java
package plm;

@Entity @Table(name="books")
public class Book {
    @Id private String isbn;
    private String title;
    private int year;
    // 默认构造函数（实体类所需的）
    public Book() {}
    // 构造函数
    public Book(String isbn, String title, int year) {
        this.setIsbn(isbn);
        this.setTitle(title);
        this.setYear(year);
    }
    // getter 和 setter 方法
}
```

注意，模型类 `Book` 被编码为 JPA 实体类，它是一个带有以下 JPA 注解的 JavaBean：

- `@Entity` 注解将类指定为实体类，意味着该类的实例将被持久化存储。
- `@Table(name="books")` 注解指定了用于存储 `Book` 实体的数据库表名称。该注解是可选的，默认表名与类相同但全小写（也就是说，在我们的用例中是 `book`）。
- `@Id` 注解标记标准标识属性，意味着底层 SQL 数据库表中相应的列被指定为主键（PRIMARY KEY）。在我们的示例中，`isbn` 被用作标识属性，`books` 表中对应的 `isbn` 列存储了主键值。

在实体类 `Book` 中，我们还定义了以下静态（类级）方法：

- `Book.create` 用于创建新的 `Book` 实例。
- `Book.retrieveAll` 用于从持久化数据存储中检索所有 `Book` 实例。
- `Book.retrieve` 用于通过标准标识符从持久化数据存储中检索特定的 `Book` 实例。
- `Book.update` 用于更新实体 `Book` 实例。
- `Book.delete` 用于删除 `Book` 实例。
- `Book.generateTestData` 用于创建一些示例记录作为测试数据。
- `Book.clearData` 用于清除 `Book` 数据库表。

这些方法的签名在接下来的小节中将详细讨论，显示在下面的程序列表中：

```java
// getter 和 setter 方法
public String getIsbn() { return isbn; }
public void setIsbn(String isbn) { this.isbn = isbn; }
public String getTitle() { return title; }
public void setTitle(String title) { this.title = title; }
public int getYear() { return year; }
public void setYear(int year) { this.year = year; }
// CRUD 数据管理方法
public static void create() { }
public static List<Book> retrieveAll() { }
public static Book retrieve() { }
public static void update() { }
public static void delete() { }
public static void clearData() { }
public static void generateTestData() { }
```

用于数据管理和对象存储映射的 JPA 架构基于实体管理器（entity manager）的概念，它提供了数据管理方法：`persist` 用于保存新创建或更新的实体，`find` 用于检索实体，`remove` 用于删除实体。

由于管理器的数据库访问操作是在事务环境中执行的，我们的数据管理方法有一个类型为 `UserTransaction` 的参数。在管理器调用数据库写入方法 `persist` 之前，需要通过 `ut.begin()` 事务。在执行所有写入（以及状态更改）操作后，通过 `ut.commit()` 完成事务（提交所有更改）。

### 4.3.1 将 Book 对象存储在数据库表 books 中

我们实体类 `Book` 的实例是代表 "实体"（或业务对象）的 Java 对象，它们可以被序列化，换句话说，可以转换为数据库表的记录（或行），如表 4.1 所示。

结构查询语言（SQL）由 20 世纪 70 年代初 Donald D. Chamberlin 和 Raymond F. Boyce 创建，是一种基于 Edgar F. Codd 关系数据库模型的 ISO 标准，它定义了：

- 数据定义语言（基于 `CREATE TABLE` 语句），用于创建包含原始数据的数据库；
- 数据操纵语言（基于 `INSERT`、`UPDATE` 和 `DELETE` 语句），用于创建、更新和删除数据库表的内容；
- 查询语言（基于 `SELECT` 语句），用于检索存储在数据库表中的信息。

SQL 广泛应用于数据库管理系统（DBMS）和用于持久化数据的编程语言中。尽管存在 SQL 标准，但每个 DBMS 都有自己的 SQL 方言。因此，在实践中如果没有调整，SQL 代码在不同的 DBMS 之间是不完全通用的。

数据库应用程序使用的存储技术是 MySQL，用于创建数据库表 `books` 的 SQL 代码如下：

```sql
CREATE TABLE IF NOT EXISTS books (
  isbn VARCHAR(10) NOT NULL PRIMARY KEY,
  title VARCHAR(128),
  year SMALLINT
);
```

虽然可以通过上述方法手动创建数据库架构，但我们展示了如何通过 JPA 生成数据库架构。在这两种情况下，在应用程序连接之前，必须手动完成数据库架构的设置，包括创建、更新等。

### 4.3.2 创建并存储 Book 对象

为了存储新对象，调用实体管理器的 `persist` 方法。它负责将新创建的实体保存到数据库。

### 4.3.3 检索所有实例

实体类 `Book` 的实例通过 Java 持久语言（JPQL）从数据库检索，这些查询类似于 SQL。在 `Book.retrieve` 方法中，创建一个请求所有实例的查询并将其赋值给 `List` 变量。
