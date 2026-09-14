
# 实战 Java：助你掌握 Java 生态系统

```
public class Java17TextBlocks {

    public static void main(String[] args) {

        String data = """
            Apple,Fruit
            Banana,Fruit
            Potato,Vegetable
            """;

        String formatted = String.format("*%s*", data);
        System.out.println(formatted);
    }
}
```

这输出了以下四行：

```
*Apple,Fruit
Banana,Fruit
Potato,Vegetable
*
```

**表 3.4**: 特殊操作符

你还可以使用通配符（`*`）进行部分匹配。例如，此查询查找所有摘要以 `improvement` 开头的 `jiras`：

```
summary ~ "improvement*"
```

你可以使用特殊字符 `d` 表示天，`h` 表示小时等，如此查询所示，查找在过去三天内解决的所有 `jiras`：

```
status = resolved>= -3d
```

括号可用于分组，以控制逻辑操作符的作用范围。此查询查找 `Value Mark` 项目中处于 `Unresolved` 状态、分配给当前登录用户且优先级为 `High` 或 `Critical` 的 `jiras`：

```
project = "Value Mark" and assignee = currentUser() AND resolution = Unresolved
```

## 批量更改

`JQL` 允许用户根据选定的标准进行操作。例如，在每日站会期间，团队成员可能会在人之间流转，询问你昨天完成了什么，今天将要做什么工作，以及是否有任何阻塞因素。当轮到你时，如果能只显示你的 `jiras` 并隐藏所有其他任务，不是很方便吗？这就是过滤器的用处。

过滤器可以配置为按用户过滤，或者实际上通过 `JQL` 根据你的 `jiras` 的任何其他属性或多个属性进行过滤，我们将在接下来的章节中看到这一点。

## 查看我的问题

通过选择 `Filters/My Open Issues`（参见图 3.31），你可以查看跨所有看板和待办列表的所有问题。

在同一个屏幕上，你可以点击 `Switch To JQL` 来输入 `JQL` 查询。

![Jira 软件窗口的截图。选项卡包括项目、过滤器、仪表板、团队和计划。在过滤器选项卡中，光标位于标题为“最近”的菜单的“我的打开问题”选项上。](img/c03f031.png)

**图 3.31**: 查看我的问题

## 使用 JQL 进行查询

`Jira 查询语言`（`JQL`）允许任何用户根据选定的标准选择 `jiras`。它是一种简单的语言；你只需指定一个或多个字段以及这些字段的值，以及一个 `order by` 子句。

一个 `JQL` 查询由一个或多个字段选择子句后跟一个 `order by` 子句组成。字段选择子句由 `AND` 或 `OR` 分隔，并可以使用括号进行分组。

字段选择子句由一个字段、一个操作符和一个值组成。表 3.2、3.3 和 3.4 显示了有效的操作符。

| OPERATOR | DESCRIPTION |
| --- | --- |
| `=` | 字段值等于指定的值 |
| `!=` | 不等于 |
| `<` | 小于 |
| `>` | 大于 |
| `<=` | 小于或等于 |
| `>=` | 大于或等于 |
| `IN` | 在值列表中 |
| `NOT IN` | 不在值列表中 |
| `IS` | 等于指定的值 |
| `IS NOT` | 不等于指定的值 |
| `WAS` | 过去具有指定的值 |
| `WAS IN` | 过去在值列表中 |
| `WAS NOT IN` | 过去不在值列表中 |
| `CHANGED` | 字段已更改为指定的值 |
| `BY` | 字段由指定的用户更改 |
| `AFTER` | 日期字段在指定日期或时间之后 |
| `BEFORE` | 日期字段在指定日期或时间之前 |
| `DURING` | 日期字段发生在特定的日期范围内 |

**表 3.2**: 比较操作符

| OPERATOR | DESCRIPTION |
| --- | --- |
| `AND` | 逻辑 AND |
| `OR` | 逻辑 OR |
| `NOT` | 逻辑 NOT |

**表 3.3**: 逻辑操作符

子句可以使用关键字 `AND`、`OR` 和 `NOT` 分隔。要按一个或多个字段进行排序，你可以用 `ORDER BY` 和字段名结束查询。你可以用 `ASC` 或 `DESC` 控制排序顺序。

| OPERATOR | DESCRIPTION |
| --- | --- |
| `EMPTY` | 字段值为空。 |
| `NOT EMPTY` | 字段值不为空。 |
| `NULL` | 字段具有空值。 |
| `NOT NULL` | 字段不为空。 |
| `~` | 匹配正则表达式。 |
| `~*` | 匹配正则表达式，不区分大小写。 |
| `!~` | 不匹配正则表达式。 |
| `!~*` | 不匹配正则表达式，不区分大小写。 |
| `CURRENTUSER` | 当前用户。 |
| `currentUser` | 与 `CURRENTUSER` 相同，但不区分大小写。 |

**表 3.4**: 特殊操作符

你还可以使用通配符（`*`）进行部分匹配。例如，此查询查找所有摘要以 `improvement` 开头的 `jiras`：

```
summary ~ "improvement*"
```

你可以使用特殊字符 `d` 表示天，`h` 表示小时等，如此查询所示，查找在过去三天内解决的所有 `jiras`：

```
status = resolved>= -3d
```

括号可用于分组，以控制逻辑操作符的作用范围。此查询查找 `Value Mark` 项目中处于 `Unresolved` 状态、分配给当前登录用户且优先级为 `High` 或 `Critical` 的 `jiras`：

```
project = "Value Mark" and assignee = currentUser() AND resolution = Unresolved
```

要创建你自己的 Confluence 云版本，请访问 `https://www.atlassian.com/software/confluence`。

Confluence 分为 `spaces`（空间），代表不同的团队。空间可以设置权限，规定谁可以查看、编辑和创建空间内的页面。在一个空间内可以对单个页面进行更细粒度的限制，例如，如果你正在协作某个页面但尚未准备好共享它，你可以只赋予该页面工作组权限，并限制其他人。

点击 `Create`（创建）按钮并选择合适的模板即可创建一个新页面。为页面输入标题，然后按 Tab 键或点击标题下方的内容框。

现在你可以在内容框中自由输入，也可以按 `/` 键从许多选项中选择，如 `Image`（图像）、`Table`（表格）或 `Code snippet`（代码片段）。如果其他人与你同时编辑，Confluence 将显示一个带有他们姓名首字母的小旗帜，标记他们的位置。

要插入图像，你可以从文件系统将图像文件拖放到 Confluence 页面上，也可以从剪贴板复制并粘贴图像，或者点击 `/` 并选择 `Image`（图像）、`Video`（视频）或 `File`（文件），然后选择图像文件。

你可以通过拖动边界来调整图像大小。当你点击图像时，图像下方会出现额外的编辑选项，用于边框、图像对齐等等。图 3.35 显示了如何插入图像。

选择 `Table`（表格）插入一个新表格。你可以选择单个单元格、多个单元格、整行、整列或整个表格。当你进行选择时，单元格右上角会出现一个小箭头。点击箭头可以展开上下文菜单，其中包含更改背景或添加或删除行或列的选项。图 3.36 显示了如何插入表格。

![一张 Confluence 窗口的截图。Valve Mark Financial Advisory Service 海报被插入到新入职页面内容中。](img/c03f035.png)

**图 3.35**: 插入图像

![窗口截图，显示表格插入在海报下方。右侧点击表格会显示背景颜色、添加行列以及删除行列的选项。](img/c03f036.png)

**图 3.36**: 插入表格

表格 3.5 显示了一些实用的宏，让你了解一下这些功能。你可以根据自己的心情随时尝试它们。

在使用 Confluence 时，你将学习到有趣的优化技巧，例如输入 `{note}` 创建备注框，或粘贴 `Jira` URL 自动将工单连接到页面，并包含页面渲染时的状态！

| 操作算符 | 描述 |
| --- | --- |
| Table | 创建表格 |
| Code Snippet | 创建格式化的代码 |
| Note/Tip/Success/Warning/Error Panel | 创建带有适当图标的文本以引起注意 |
| Heading 1, 2, 3, 等. | 创建大纲 |
| Table of Contents | 在目录中显示标题以便导航 |
| Expand | 显示一个可以展开以显示更多细节的链接 |
| Excel | 嵌入电子表格页 |

**表格 3.5**: 选择的 Confluence 宏

## 进一步参考

*   [`https://git-scm.com/docs`](https://git-scm.com/docs)
    完整的 Git 参考文档
*   [`https://nvie.com/posts/a-successful-git-branching-model`](https://nvie.com/posts/a-successful-git-branching-model)
    Vincent Driessen 写的原始 Gitflow 文章
*   [`https://www.atlassian.com/software/jira`](https://www.atlassian.com/software/jira)
    Jira 文档
*   [`https://www.atlassian.com/software/confluence`](https://www.atlassian.com/software/confluence)
    Confluence 文档

## 总结

在本章中，我们查看了一些企业协作中最常用的工具。

*   `Git` 用于代码协作
*   `Jira` 用于流程协作
*   `Confluence` 用于企业知识管理

# 4 使用 Maven、Gradle 和 Jenkins 自动化你的 CI/CD 构建

到目前为止，你已经从第 2 章“了解你的 IDE：成功的秘密”中学习了如何在机器上编写代码，并在第 3 章“通过 Git、Jira 和 Confluence 进行跨企业协作”中与他人分享。在本章中，你将看到如何使用 `Maven` 和 `Gradle` 构建并打包代码。

虽然在自己的电脑上运行 `Jenkins` 是可能的，但公司通常将其运行在远程服务器上，就像版本控制系统运行在远程服务器一样。这确保了构建是干净的，不依赖于单一开发者的环境。它还允许 `Jenkins` 通过不与开发者竞争计算机资源来运行更快。此外，构建服务器永远不需要睡觉或休息！

## 使用 Maven 构建

构建服务器本身并不真正构建东西，至少在没有帮助的情况下。相反，它们协调 `Maven` 或 `Gradle` 等工具进行构建、测试和部署。虽然 `Maven` 可以并且经常管理项目的构建、报告和文档需求，但它通常被简称为构建工具。

`Maven` 的原则之一是“约定优于配置”。这意味着许多配置属性都是假设的（尽管如有需要可以覆盖它们）。这种应用合理默认设置的方法让开发者能够轻松在项目之间切换，因为它们通常具有相同的默认设置。

例如，大多数 `Maven` 项目使用图 4.1 所示的目录结构，项目根目录下的 `src` 目录包含一个用于打包的 `main` 目录，以及一个用于测试代码的 `test` 目录。第 7 章“使用自动化测试工具测试你的代码”将介绍如何使用 `test` 目录。`java` 子目录意不用说地包含 Java 源代码，`resources` 子目录用于文本文件，例如数据库配置和其他应用程序属性。`target` 目录是存放构建结果的地方。

让我们从构建一个简单的 Maven 项目开始，然后深入研究 Maven 的某些特性。每个 Maven 项目都都有一个 `pom.xml` 文件。POM 代表项目对象模型（Project Object Model），是一个包含项目构建信息的 XML 文件。关于 XML 的更多信息，请参阅附录 中的“XML 和 JSON”。最短的 `pom.xml` 文件看起来如下：

```
1:  <?xml version="1.0" encoding="UTF-8"?>
2:
3:  <project xmlns="http://maven.apache.org/POM/4.0.0"
4:     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
5:     xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
6:     https://maven.apache.org/xsd/maven-4.0.0.xsd">
7:
8:     <modelVersion>4.0.0</modelVersion>
9:
10:    <groupId>com.wiley.realworldjava.maven</groupId>
11:    <artifactId>basic-pom</artifactId>
12:    <version>1.0.0-SNAPSHOT</version>
13: </project>
```

第 1–8 行是样板代码，你会在每个 POM 文件中放入这些代码。它们声明此 XML 文件旨在被解析为 Maven POM。通常情况下，当你创建一个新项目时，IDE 会为你生成这些代码。或者，你也可以从另一个 Maven 项目复制/粘贴这些样板代码。

第 10–12 行是指定你的 Maven 项目坐标的地方。`group id` 通常映射到包名或包名的前缀。它创建了一个命名空间，以避免与其他 Maven 制品（artifacts）冲突。`artifact id` 代表 `group id` 下的特定项目名称。最后，`version` 标签允许你为每次构建分配版本号，以便你随着时间的推移查看和引用之前的版本。在代码发布之前，你会为版本分配 `SNAPSHOT` 后缀，这告诉 Maven 这不是最终的“发布”（release）版本。（你将在后续章节中学习关于更多的信息）。这三个标签合称为项目的 GAV（group id, artifact id, version）坐标。

要在命令行中运行构建，可以在包含 `pom.xml` 文件的目录下执行 `mvn verify`，这将执行以下所有操作：

1. 下载构建所需的任何依赖并将其存储在你的 Maven 缓存中。
2. 将 `src/main/resources` 中的的任何文件复制到 `target/classes`。
3. 编译 `src/main/java` 中的任何代码，并将结果存储在 `target/classes`。
4. 将 `src/test/resources` 的任何文件复制到 `target/test-classes`。
5. 编译 `src/test/java` 中的任何代码，并将结果存储在 `target/test-classes`。
6. 运行单元测试形式的检查，以验证构建有效并符合某些质量标准。
7. 创建一个名为 `<artifactId>-<version>.jar` 的 JAR 文件（在此例中为 `basic-pom-1.0.0-SNAPSHOT.jar`），包含现在 `target/classes` 中的文件，并将其存储在 `target` 中。

对于一个只有 13 行（大部分是样板代码）的 POM 来说，这些工作非常多。这就是“约定优于配置”（convention over configuration）的力量。由于我们没有另说明，Maven 假设了默认值：我们想要编译并测试代码，并将结果存储在 JAR 文件中！

### 理解 Maven 仓库和依赖

Maven 构建执行的第一件事是寻找依赖。这些是构建运行所需需要下载的库。依赖有两种类型。有些是你的项目专门需要的，并在 POM 中指定。你很快就会看到它们。另一些是 Maven 本身需要的。就像你在第 2 章中看到的 IDE 一样，Maven 使用插件来提供功能。第一次运行 Maven 构建时，它会下载这些插件。这可能需要一些时间；事实上，有一个笑话说 Maven 需要“下载互联网”。

默认情况下，Maven 从一个名为 Maven Central 的仓库下载它需要的所有内容。与你在第 3 章中看到的源码仓库 GitHub 不同，Maven Central 是一个二进制仓库。它的主要用途是存放你无法用文本编辑器打开的制品，例如 JAR 文件！

以下显示了 Maven 下载某一个插件的输出：

```
Downloading from central: https://repo.maven.apache.org/maven2/
org/apache/maven/plugins/maven-compiler-plugin/3.11.0/
maven-compiler-plugin-3.11.0.pom
Downloaded from central: https://repo.maven.apache.org/maven2/
```



`org/apache/maven/plugins/maven-compiler-plugin/3.11.0/`

`maven-compiler-plugin-3.11.0.pom` (9.8 kB at 28 kB/s)

Downloading from central: `https://repo.maven.apache.org/maven2/`

`org/apache/maven/plugins/maven-compiler-plugin/3.11.0/`

`maven-compiler-plugin-3.11.0.jar`

Downloaded from central: `https://repo.maven.apache.org/maven2/`

`org/apache/maven/plugins/maven-compiler-plugin/3.11.0/`

`maven-compiler-plugin-3.11.0.pom` (66 kB at 28 kB/s)

| `integration-test` | `package` + 运行任何集成测试（参见第 7 章）。 |
| `verify` | `integration-test` + 确认包有效。 |
| `install` | `verify` + 将包安装到本地 Maven 仓库，以供其他构建使用。 |
| `deploy` | `install` + 将包发布到你的机器之外。 |

**表 4.1**: Maven 默认生命周期阶段

与 `verify` 成为好朋友吧，因为它是你机器上运行的最常用的 Maven 阶段。如果你正在处理多个相互关联的项目，你将需要使用 `install`，但它不应该是你的“首选”，因为它的运行时间更长，而且通常不需要。

## 探索 POM

在本节中，你将学习在 POM 中可以使用的的许多功能。

### 使用属性 (Properties)

在 Java 代码中，在类中硬编码“魔术数字”（没有上下文的值）不是一个好主意。相反，使用命名常量更好。同样，在 POM 中，将版本号和其他配置数据放在属性中是常见的，你通常会将它们包含在 POM 文件的顶部。它还允许你在多个需要保持相同版本的依赖之间共享版本号。以下内容与之前的 POM 等效，只是它将版本号提取到了属性中：

```xml
<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>with-properties</artifactId>
<version>1.0.0-SNAPSHOT</version>
<properties>
   <eclipse.collections.version>11.1.0</eclipse.collections.version>
</properties>
<dependencies>
   <dependency>
      <groupId>org.eclipse.collections</groupId>
      <artifactId>eclipse-collections</artifactId>
      <version>${eclipse.collections.version}</version>
   </dependency>
</dependencies>
```

你可以在 `<properties>` 标签中定义任意数量的属性。在这种情况下，有一个名称为 `eclipse.collections.version` 值为 `11.1.0` 的属性。要使用该属性，请在 `${}` 占位符内部引用变量名，Maven 将自动用属性值替换占位符。

### 指定项目信息

如前所述，Maven 追求尽可能地管理你的项目信息。虽然不是详无不尽，但这个示例可以让你了解可以包含的信息类型。

```xml
11: <groupId>com.wiley.realworldjava.maven</groupId>
12: <artifactId>project-info</artifactId>
13: <version>1.0.0-SNAPSHOT</version>
14: <name>Project Info Test</name>
15: <description>此项目展示了使用更多标签 
16:    不仅仅是 GAV 来描述项目</description>
17: <url>https://www.wiley.com/en-us/Real+World+Java%3A+Helping+
18:    You+Navigate+the+Java+Ecosystem-p-9781394275724</url>
19: <inceptionYear>2024</inceptionYear>
20:
21: <properties>
22:    <git.url>https://github.com/realworldjava/Ch04-CICD</git.url>
23: </properties>
24:
25: <scm>
26:    <connection>scm:git:h${git.url}.git</connection>
27:    <developerConnection>scm:git:${git.url}.git</developerConnection>
28:    <url>${git.url}</url>
29:    <tag>HEAD></tag>
30: </scm>
```

第 14–15 行提供了显示名称和关于项目的详细信息，可以供其他工具使用。第 17 行列出了有关项目更多细节 URL，在这种情况下是书籍的 URL。第 19 行显示了项目的启动年份。

某些插件需要额外信息。例如，第 25–30 行显示了指定 GitHub URL 的格式，在发布时使用。它还方便地展示了定义属性的好处；这一个被使用了三次！

POM 中可以包含的其他信息还包括指向 Jira 项目的链接以及项目上所有开发者的联系方式。

### 理解版本号

在编写代码时，你使用类似 `1.0.0-SNAPSHOT` 的 `SNAPSHOT` 版本。一旦准备好发布，`SNAPSHOT` 后缀就会被删除，变为 `1.0.0`。

你可能注意到版本号由由点分隔的三个部分组成。Maven 制品通常遵循语义版本化（semantic versioning）。第一个数字随主版本递增，这可能会引入新的应用程序接口 (API) 或破坏性功能。第二个数字用于次要版本，通常是兼容的、可能经过改进的版本。第三部分通常用于修复错误。

并不是所有项目都遵循这种命名规范，但大多数项目遵循其变体，例如在名称末尾添加 `.beta` 或 `.release` 以提供更多信息。

此外，低于 1.0.0 的数字通常意味着预发布。因此，`0.2.6` 可能意味着项目尚未准备好完全的初始发布。

理解这一点很重要，因此请考虑表 4.2 所示的事件序列。

## 使用常用插件

如你之前看到的，插件赋予了 Maven 功能性。在接下来的章节中，你将学习如何使用它们。

### 配置插件

让我们来看编译器插件。使用你最喜欢的搜索，查找 [`https://maven.apache.org/plugins/compiler-plugin`](https://maven.apache.org/plugins/compiler-plugin)，它将带你进入文档。

| VERSION | 含义示例 |
| --- | --- |
| `0.0.1-SNAPSHOT` | 开始初始工作。 |
| `0.0.1` | 准备给测试人员。 |
| `0.0.2-SNAPSHOT` | 哎。我们发现了一个 bug。正在修复 bug。 |
| `0.0.2` | bug 已修复。准备好给测试人员。 |
| `1.0.0-SNAPSHOT` | 准备好黄金时期。为 1.0 做准备。 |
| `1.0.0` | 准备好发布 1.0。 |
| `1.0.1-SNAPSHOT` | 哎。另一个 bug。正在修复 bug。 |
| `1.0.1` | bug 已修复。这次我们搞定了。 |
| `1.1.1-SNAPSHOT` | 准备好进行次要改进。 |
| `1.1.1` | 准备好发布次要改进。 |
| `2.0.0-SNAPSHOT` | 正在下一个主版本发布 |

**表 4.2**: 版本号示例

![Maven 文档首页的截图。在侧边栏中选中了简介。右侧显示了 Apache Maven 编译器插件的目标和用法。](img/c04f002.png)

**图 4.2**: Maven 首页

插件文档页面列出了插件包含的任何目标，在本例中为 `compiler:compile` 和 `compiler:testCompile`。它还会告诉你它们自动绑定到生命周期的阶段。这些目标分别绑定到 `compile` 和 `test-compile` 阶段。插件不需要绑定到特定阶段，你可以显式地调用它们。然而在本章中，所有插件都已绑定。第 7 章 展示了使用代码将 `integration-tests` 绑定到生命周期阶段的示例，以便它们在构建期间自动运行。

插件文档页面的左导航包含以下菜单选项：

*   **Goals (目标)**：包含的任何目标的详细信息，重点关注必需和可选参数
*   **Usage (用法)**：展示如何在 POM 中包含该插件
*   **Examples (示例)**：一个或多个显示如何配置常见场景的链接

此示例展示了如何配置编译器插件以使用 Java 21：

```xml
<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>compile</artifactId>
<version>1.0.0-SNAPSHOT</version>
<properties>
   <java.version>21</java.version>
</properties>
<build>
   <plugins>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
         <version>3.13.0</version>
         <configuration>
            <source>${java.version}</source>
            <target>${java.version}</target>
         </configuration>
      </plugin>
   </plugins>
</build>
```

请注意 `configuration` 标签。那是“目标（goals）”文档中参数所在。在这种情况下，它指定了你想同时使用 Java 21 来进行编译和生成字节码。

文档中的示例之一是关于如何“传递编译器参数（Pass Compiler Arguments）”，如下所示：

```xml
<project>
   [...]
   <build>
      [...]
      <plugins>
         <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.13.0</version>
            <configuration>
               <compilerArgs>
                  <arg>-verbose</arg>
                  <arg>-Xlint:all,-options,-path</arg>
               </compilerArgs>
            </configuration>
         </plugin>
      </plugins>
      [...]
   </build>
   [...]
</project>
```

将此示例与上一个相比，你可以看到 `configuration` 部分包含了编译器参数。文档使用 `[...]` 来表示在你的 POM 的这些位置可能还有其他代码。

## 识别常用插件

现在你已经了解了如何阅读插件的文档，我们可以介绍其他常用插件。每个插件都有自定义的配置选项，你可以在项目中使用它们时查阅这些选项。以下常用插件属于组 ID `org.apache.maven.plugins`：

- `maven-assembly-plugin`：为文件组合创建 zip 文件。当部署到具有不同设置的多个环境时非常有用。
- `maven-compiler-plugin`：编译你的代码。
- `maven-dependency-plugin`：用于依赖的各种目标，如列出或解包它们。
- `maven-deploy-plugin`：将生成的产物上传到二进制仓库。
- `maven-enforcer-plugin`：如果你的 POM 不符合指定规则，则构建失败。
- `maven-failsafe-plugin`：运行集成测试。详情请参阅第 7 章。
- `maven-install-plugin`：用生成的产物更新本地仓库。
- `maven-jar-plugin`：创建 JAR 文件产物。
- `maven-javadoc-plugin`：为项目创建 Javadoc HTML 页面。
- `maven-release-plugin`：发布软件的各种目标，包括标记仓库和更新 POM 版本号。
- `maven-resources-plugin`：将源和测试资源复制到输出目录。
- `maven-shade-plugin`：创建一个包含你的类以及所有依赖项类的巨型 JAR（uber-jar）。
- `maven-site-plugin`：生成包含当前项目信息的 HTML 页面，如 Javadoc 和发布说明。
- `maven-source-plugin`：创建包含项目源代码的 JAR 文件。
- `maven-surefire-plugin`：运行单元测试。详情请参阅第 7 章。

并不是所有插件都在同一个组 ID 中。某些是由其他组织提供的。例如，静态分析工具 Sonar 提供了一个插件。它的组 ID 为 `org.sonarsource.scanner.maven`，制品 ID 为 `sonar-maven-plugin`。你可以从组 ID 看出它是由 SonarSource 而非 Apache 提供的。

## 使用父 POM

正如你在 Java 中了解的那样，每个类都有一个超类。同样，在 Maven 中，每个 POM 都有一个父 POM。在 Java 中，共同祖先是 `java.lang.Object`，即使没有指定 `extends`。同样，如果未指定父级，Maven 有一个继承的超 POM。这个超 POM 是指定“约定优于配置”默认值（如 `src/main/java` 目录）的地方。你可以在“进一步参考”中找到超 POM 的链接。或者，你可以从项目目录运行 `mvn help:effective-pom` 来查看有效 POM，它包含了你的配置以及它从超 POM 继承的所有内容。

### 创建你自己的父 POM

在企业中，在公司、部门和/或团队级别拥有自定义 POM 是常见的。这允许本地标准集中在一个地方。

父 POM 使用打包类型 `pom`。这告诉 Maven 不要期望有 Java 代码，而是只发布 POM 文件。这是一个示例：

```xml
<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>parent</artifactId>
<version>1.0.0-SNAPSHOT</version>
<packaging>pom</packaging>
```

`packaging` 标签中可以放置不同的值。例如，`jar` 是默认值，表示构建 JAR。相反，当你构建父 POM 时，会指定 `pom`。父 POM 可以像任何其他 POM 一样包含属性和插件。

子 POM 通过使用 GAV 来指定它想要使用的父级：

```xml
<artifactId>child</artifactId>
<version>1.0.0-SNAPSHOT</version>
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
</parent>
```

注意子 POM 没有指定 `groupId`。如果父级和子具有相同的 `groupId`，此标签是可选的。

### 继承父 POM

父 POM 只有在它包含内容时才有用！看看这个父 POM，它引入了两个新部分：`dependencyManagement` 和 `pluginManagement`：

```xml
<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>parent</artifactId>
<version>1.0.0-SNAPSHOT</version>
<packaging>pom</packaging>
<properties>
    <java.version>21</java.version>
    <eclipse.collections.version>11.1.0</eclipse.collections.version>
    <compiler.plugin.version>3.13.0</compiler.plugin.version>
</properties>
<dependencyManagement>
```



首先注意到在`properties`部分定义了几个属性，以便可以使用它们，而不是在 POM 的其他部分硬编码数字。这种技术允许子 POM 使用默认值，但也允许它们覆盖任何属性。这就像 Java 中超类中的`protected`变量。能够独立地更改这些值的任何一个而无需切换到不同的父 POM 或依赖另一个项目进行更改是非常有用的。

接下来是`dependencyManagement`部分。其内容看起来像普通 POM 中的`dependencies`。关键区别在于，`dependencyManagement`中的制品在被子 POM 引用之前，实际上不会被加载。同样，`pluginManagement`在子 POM 使用这些插件时对插件进行配置。

子 POM 如何指定它想要使用某个依赖或插件？查看使用此父 POM 的子 POM：

```xml
<artifactId>child</artifactId>
<version>1.0.0-SNAPSHOT</version>
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
</parent>
<dependencies>
   <dependency>
      <groupId>org.eclipse.collections</groupId>
      <artifactId>eclipse-collections</artifactId>
   </dependency>
</dependencies>
<build>
   <plugins>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
      </plugin>
   </plugins>
</build>
```

注意这些配置是极简的。版本号和配置不需要指定；所有这些都来自父 POM。

假设你不想想要父 POM 中的`eclipse-collections`依赖。没问题——只需在子 POM 中省略该依赖即可，它就会被忽略：

```xml
<artifactId>child-without-dependency</artifactId>
<version>1.0.0-SNAPSHOT</version>
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
</parent>
<build>
   <plugins>
      <plugin>
         <groupId>org.apache.maven.plugins</groupId>
         <artifactId>maven-compiler-plugin</artifactId>
      </plugin>
   </plugins>
</build>
```

其他更改也很简单。如果你想使用不同版本的`eclipse-collections`或`maven-compiler-plugin`，可以在子 POM 中覆盖版本属性，这会覆盖来自父 POM 的版本。或者，你也可以直接添加一个显式的版本标签，而不是继承它。

## 与多模块项目一起工作

到本章为止，我们每次运行 Maven 构建时，它运行的都是一个`pom.xml`。有时你有一组相关的项目。当这种情况这种情况时，你可以创建一个多模块项目。仍然有一个父 POM，但在多模块项目中，所有子模块都在子目录中。例如，目录结构如下：

```
module-parent
|- pom.xml
|- module-services
|  |- pom.xml
|- module-util
    |- pom.xml
```

首先，让我们看看父 POM：

```xml
<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>module-parent</artifactId>
<version>1.0.0-SNAPSHOT</version>
<packaging>pom</packaging>
<modules>
   <module>module-services</module>
   <module>module-util</module>
</modules>
```

POM 包含一个新的新的`modules`部分，其中包含了项目子目录中应该包含在构建中的模块列表。模块列出的顺序并不一定是它们被构建的顺序。

一个子模块可以在其依赖列表中包含另一个模块。在我们的示例中，`module-services`将依赖于`module-util`。Maven 足够智能，根据依赖关系确定构建子模块的正确顺序。

接下来，我们将查看`module-util` POM，它非常简单，只引用了父项目：

```xml
<artifactId>module-util</artifactId>
<version>1.0.0-SNAPSHOT</version>
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>module-parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
</parent>
```

`module-service` POM 执行了相同的操作，但也指定了一个依赖：

```xml
<artifactId>module-services</artifactId>
<version>1.0.0-SNAPSHOT</version>
<parent>
   <groupId>com.wiley.realworldjava.maven</groupId>
   <artifactId>module-parent</artifactId>
   <version>1.0.0-SNAPSHOT</version>
</parent>
<dependencies>
   <dependency>
      <groupId>com.wiley.realworldjava.maven</groupId>
      <artifactId>module-util</artifactId>
      <version>1.0.0-SNAPSHOT</version>
   </dependency>
</dependencies>
```

由于在这个示例中所有内容都包含在一个项目中，你可以在`module-parent`级别运行`mvn clean verify`。输出包含了已构建的模块列表以及它们是否成功。

```
[INFO] --------------------------------------------------------
[INFO] Reactor Summary for module-parent 1.0.0-SNAPSHOT:
[INFO] 
[INFO] module-parent ………………… SUCCESS [  0.077 s]
[INFO] module-util ………………….. SUCCESS [  0.571 s]
[INFO] module-services ………………. SUCCESS [  0.040 s]
[INFO] --------------------------------------------------------
```

注意 Maven 最后运行了`module-services`，因为它依赖于`module-util`。

## 使用其他 Maven 功能

虽然 Maven 有很多功能，但本节涵盖了你可能会遇到的几个功能，包括设置系统属性、使用材料清单（BOM）以及发布你的项目。

### 设置系统属性

Java 系统属性是可选的命令行参数，用于更改构建行为。你可以在调用 Maven 时传递它们，例如：

```
mvn -Dproject.sourceEncoding=UTF-8 clean verify
```

你可以在 POM 的插件配置中指定系统属性：

```xml
<configuration>
   <systemProperty>myPropertyValue</systemProperty>
</configuration>
```

### 使用材料清单 (Bill of Materials)

材料清单（BOM）是一个特殊的 POM 文件，用于指定可选依赖。当你引入大量依赖且它们之间相互相关时，它非常有用。使用 BOM 的常见方法是在你的 POM 的`dependencyManagement`中指定它：

```xml
<groupId>com.wiley.realworldjava.maven</groupId>
<artifactId>using-bom</artifactId>
<version>1.0.0-SNAPSHOT</version>
<properties>
   <jackson.bom.version>2.17.0</jackson.bom.version>
</properties>
<dependencyManagement>
   <dependencies>
      <dependency>
         <groupId>com.fasterxml.jackson</groupId>
         <artifactId>jackson-bom</artifactId>
         <version>${jackson.bom.version}</version>
         <scope>import</scope>
         <type>pom</type>
      </dependency>
   </dependencies>
</dependencyManagement>
```

注意`scope`是`import`，这只在`type`为`pom`时才允许。这种作用会扩展导入依赖的值，就像你直接将它们包含在`dependencyManagement`中一样。

### 发布你的项目

在某个时刻，你完成了对项目的初始工作，并准备好发布它。`maven-release-plugin`有许多目标（goals）。你像运行`mvn verify`一样从 Maven 命令运行它们。最有用的四个：

- `release-clean`：清理之前发布的中间文件。
- `release-prepare`：检查项目是否处于发布状态。例如，POM 不能引用`SNAPSHOT`依赖，因为那样无法创建重复的发布。`release-prepare`还会更新 POM 中的版本号。
- `release-perform`：在版本控制中标记代码并将制品存储在二进制仓库中。
- `release-rollback`：从失败的`prepare`中恢复 POM 文件。

## 在 IDE 中了解 Maven

正如你在第 2 章所看到的，使用集成开发环境（IDE）可以比从命令行运行要高效得多。由于运行构建是一个如此基础的操作，我们在三个主流的 IDE 中都展示了它。

### 使用 IntelliJ

当你有一个 Maven 项目时，右侧边栏中有一个代表`Maven`的小写“m”图标。点击它可以展开`Maven`窗口。如图 4.3 所示，展开`Lifecycle`选项。你可以双击所需的目标（例如`verify`）来运行构建，或者右键单击查看更多选项。

![“一个标题为 Maven 的窗口截图。右侧边栏中有一个代表 Maven 的小写“m”图标。点击它可以展开 Maven 窗口。”](img/c04f003.png)

**图 4.3**：在 IntelliJ 中运行 Maven

IntelliJ 还为`Maven`提供了其他选项。例如，有效 POM（effective POM）对于查看在应用了所有继承设置后你的`POM`看起来样的有用。图 4.4 显示，你可以通过右键点击项目并选择`Maven`菜单找到此选项。

![一个窗口截图显示了右键点击项目 Maven 并选择 Maven 菜单。显示高了有效 P O M 选项。](img/c04f004.png)

**图 4.4**：在 IntelliJ 中查看有效 POM

如果你的项目有很多依赖项，你可能会发现在`Maven`边栏中右键点击项目并选择`Analyze Dependencies`（分析依赖）很有用。在列表中，你可以点击任何依赖项并查看它的来源，即使它是传递依赖。

### 使用 Eclipse

在 Eclipse 中，你通过在`Package Explorer`中右键点击项目并选择`Run`菜单来运行`Maven`构建。图 4.6 显示了此菜单，你可以在其中点击选择要运行的目标。

Eclipse 还允许你通过打开`pom.xml`文件来查看有效 POM 和依赖层次结构。如图 4.7 所示，编辑器为这两者都有标签页。

### 使用 VS Code

在 VS Code 中，你在左下角有一个“Maven”折叠菜单。展开它后，你就会看到图 4.8 所示的目标。你可以右键点击其中任何一个目标来运行你的`Maven`构建。

要查看有效 POM，右键点击`pom.xml`文件并在菜单中选择`Maven`。然后点击`Show Effective POM`（显示有效 POM），如图 4.9 所示。

![截图显示了通过右键点击运行命令时的以下运行配置下拉菜单：Maven build, maven clean, maven install, maven test 和 maven verify。](img/c04f006.png)

### 图表列表（摘要）

**图 4.3**：在 IntelliJ 中运行 Maven

![一个窗口截图显示了右键点击项目 Maven 并选择 Maven 菜单。显示高了有效 P O M 选项。](img/c04f004.png)

**图 4.4**：在 IntelliJ 中查看有效 POM

**图 4.6**：Eclipse 菜单

![一个窗口截图显示了右键点击项目 Maven 并选择 Maven 菜单。显示高了有效 P O M 选项。](img/c04f004.png)

**图 4.7**：在 Eclipse 中查看有效 POM

![一个窗口截图显示了右键点击项目 Maven 并选择 Maven 菜单。显示高了有效 P O M 选项。](img/c04f004.png)

**图 4.8**：VS Code 目标

![一个窗口截图显示了右键点击项目 Maven 并选择 Maven 菜单。显示高了有效 P O M 选项。](img/c04f004.png)

**图 4.9**：VS Code 有效 POM

![截图显示了通过右键点击运行命令时的以下运行配置下拉菜单：Maven build, maven clean, maven install, maven test 和 maven verify。](img/c04f006.png)

要在命令行中运行构建，请在包含`build.gradle`的目录下执行`./gradlew build`。

这将在屏幕上产生大量的动态输出。Gradle 不会像 Maven 那样顺序记录所有输出，而是动态更新控制台输出以显示当前的构建进度。最后，它会显示结果摘要：

```
Starting a Gradle Daemon (subsequent builds will be faster)
> Task :compileJava
> Task :processResources
> Task :classes
> Task :jar
> Task :assemble
> Task :compileTestJava
```



> Task :processTestResources

> Task :testClasses

> Task :test NO-SOURCE

> Task :check UP-TO-DATE

> Task :build

BUILD SUCCESSFUL in 0s

5 actionable tasks: 5 executed

此输出中列出的任务看起来与 Maven 的输出相似。它们会编译项目、运行任何测试并创建产物。创建的文件位于以下位置：

- `build/lib`：包含`basic-gradle-1.0.0.jar`文件。
- `build/classes`：包含编译生成的类文件。它们被分离到`build/classes/java/main`和`build/classes/java/test`。
- `build/resources`：包含资源的副本，并分离到`build/resources/main`和`build/resources/test`。

### 了解 Gradle 本地仓库和依赖

与 Maven 类似，Gradle 在本地存储下载的产物。在你的用户目录下，有一个`.gradle`子目录。在 Windows 上，这是`C:\Users\<your id>\.gradle`。在 Linux 和 Mac 上，它是`/Users/<your id>/.gradle`。

为了让构建更快，Gradle 存储的内容远比产物多。下载的依赖存储在目录`.gradle/caches/modules-2/files-2.1`。

例如，为`eclipse-collections`下载的文件在此目录下：

```
.gradle/caches/modules-2/files-2.1/org.eclipse.collections/

   eclipse-collections/11.1.0/
```

该目录有一个以哈希命名的子目录，这确认了文件已下载成功。该子目录包含了实际的 JAR 文件。

要在 Groovy 中指定此依赖，请将其添加到`build.gradle`文件的依赖部分。

```groovy
dependencies {

   implementation group: 'org.eclipse.collections', 

      name: 'eclipse-collections', version: '11.1.0'
}
```

这些是你之前在 Maven 中看到的相同坐标。`implementation`指定了它是最常见的依赖类型——用于编译的依赖。注意，当你需要区分产物时，也允许使用`classifier`。

Gradle 还支持使用单个值通过简写来指定依赖的完整组 ID、名称和版本：

```groovy
dependencies {

   implementation 'org.eclipse.collections:eclipse-collections:11.1.0'
}
```

在这种语法中，坐标位于由冒号分隔的单个字符串中。

对应的 Kotlin 语法将如下包含在`build.gradle.kts`文件中：

```kotlin
dependencies {

   implementation("org.eclipse.collections:eclipse-collections:11.1.0")
}
```

这一次，`implementation`调用看起来像一个方法。这三种方法都清晰地指定了组 ID、名称和版本，以便 Gradle 知道你正在寻找什么。

### 指定变量

由于 Gradle 构建文件实际上是 Groovy 或 Kotlin 代码，你可以在代码中指定变量。例如，这段 Groovy 代码声明了一个变量：

```groovy
def collVersion = "11.1.0"

dependencies {

   implementation 

   "org.eclipse.collections:eclipse-collections:${collVersion}"
}
```

Groovy 使用`def`来声明变量。`${}`语法告诉 Gradle 替换变量值。你需要使用双引号才能使该扩展生效。在 Groovy 中，单引号字符串不支持此功能。

相比之下，Kotlin 构建文件也可以使用变量：

```kotlin
val collVersion = "11.1.0"

dependencies {

   implementation 

   "org.eclipse.collections:eclipse-collections:${collVersion}"
}
```

两者之间的唯一区别是 Groovy 使用`def`声明变量，而 Kotlin 使用`val`声明不可变变量，使用`var`声明可变变量。由于版本在构建文件中声明一次且保持不变，此示例使用了`val`。

### 使用 Java 插件

在 Maven 中，你看到许多插件，如`maven-compiler-plugin`、`maven-surefire-plugin`和`maven-jar-plugin`。在 Gradle 中，Java 插件包含了其中大部分功能。Java 插件文档链接位于“进一步参考”（Further References）部分。它记录了你可以进行哪些自定义。例如，接例的示例设置了要使用的 Java 版本：

```groovy
java {

   toolchain {

      languageVersion = JavaLanguageVersion.of(21)
   }
}
```

你可能注意到我们没有说明这是 Groovy 示例还是 Kotlin 示例。它两者都是！这段特定的代码在两种语言中具有相同的语法。

Java 插件页面包含了针对测试、Javadoc 和打包的配置。它还包含了对配置任何默认值（如源目录）更改的描述。

### 在 IDE 中认识 Gradle

与 Maven 类似，在三个主流 IDE 中运行 Gradle 构建都很简单。

在 IntelliJ 中，Gradle 项目在右侧边栏有一个大象图标。这是 Gradle 的标志。一旦识别出该标志，按照以下步骤运行 Gradle 构建：

1. 点击标志展开 Gradle 窗口。
2. 展开`Tasks`。
3. 展开`Build`。
4. 右键点击你需要的任务（如`Build`）并选择运行。

在 Eclipse 中，从屏幕底部的 Gradle Tasks 视图开始。然后按照以下步骤运行 Gradle 构建：

1. 展开项目。
2. 展开`Build`。
3. 右键点击`Build`并选择运行。

在 VS Code 中，Maven 扩展包含在 Java 扩展包中。对于 Gradle，你需要安装扩展。前往市场并安装 Gradle for Java 扩展。

一旦安装了扩展并打开了 Gradle 项目，你将在左侧导航中看到大象标志。然后按照以下步骤运行 Gradle 构建：

1. 展开`Gradle Projects`。
2. 展开你的项目名称。
3. 展开`Tasks`。
4. 展开`Build`。
5. 右键点击`Build`并选择 Run Task。

### 查找依赖

无论使用 Maven 还是 Gradle，你经常需要查找 Maven Central 中项目的坐标。找到它们的方法是访问`https://central.sonatype.com`并搜索你的产物。结果页面提供了 Maven 和 Gradle 的变体，以便你复制/粘贴到你的构建文件中。

然而，有一种更快速的方法。如果你在你喜欢的搜索引擎中搜索“maven central”和构件名称，第一个搜索结果很可能来自`https://mvnrepository.com`。例如，搜索“maven central eclipse collections”会带你进入`https://mvnrepository.com/artifact/org.eclipse.collections/eclipse-collections`。Maven 仓库由一位西班牙开发者构建，它拥有与 Maven Central 相同的信息。在本书书中提到 URL 时，我们使用`mvnrepository.com`，因为它的搜索引擎优化效果更好。

图 4.14 显示了当你点击构件特定版本时可用的选项。

在期间，我们为本章的示例选择了 Eclipse Collections 版本`11.1.0`。注意，还有一个更高的版本`12.0.0.M3`。`M3`代表“里程碑 3（milestone 3）”。里程碑发布是一个用于测试新功能的公开版本，发布在最终版本之前。由于在生产代码中并不常见使用里程碑依赖项，我们选择了最新发布的版本。

在图 4.14 中，在关于更高版本的警告下方，有许多构建系统的选项卡。选择你的构建系统，复制依赖信息，并将其粘贴到你的`POM`或`Gradle`构建文件中。

![一个标题为 eclipse collections main library 的查找依赖窗口的截图。它显示了 Gradle 部分的许可证、类别、标签、文件、日期、排名、发布者、备注和新版本等信息。](img/c04f014.png)

`图 4.14`：查找依赖项

# 与 JENKINS 集成

Jenkins 自称为一个“开源自动化服务器”，实际上，Jenkins 可以自动化几乎所有的工作。然而，大多数人将其视为持续集成/持续部署（CI/CD）服务器，因为它的重点是构建和部署。

Jenkins 是开源且免费的。Cloudbees 销售一个带有专有内容和支持的版本，但它位于 Cloudbees 网站而非 Jenkins 网站，因此没有混淆的风险。

在本节中，你将学习如何安装 Jenkins、应该安装哪些常用插件以及如何运行构建。

## 安装 Jenkins

要安装 Jenkins，你可以前往“进一步参考”中的下载页面。你会发现该页面上有许多选择。

首先决定你想要稳定版还是每周发布版。稳定包每月发布一次，Jenkins 会在一段时间内对它们应用安全修复和 Bug 修复。每三个月，其中一个稳定版本将成为长期支持（LTS）版本。在家里运行时，任何版本都可以。企业通常会选择 LTS 版本或由供应商支持的版本。我们将在示例中使用最新的稳定版。

接下来，你必须决定 Jenkins 下载的格式。一种方案是获取 Web 应用程序归档（`WAR`）文件以运行在如`Tomcat`等 Web 应用服务器上。或者，你可以获取操作系统包以安装为二进制文件或`Docker`镜像。我们在本章中使用`Docker`镜像作为示例。下载`Docker`的链接也在“进一步参考”部分。不过，在个人机器上尝试 Jenkins 时，这些选项中的任何一个都可以。

对于`Docker`，首先打开“Docker Desktop”应用程序以确保`Docker`运行在你的机器上。然后打开命令行并运行以下命令下载最新的稳定 Jenkins 版本：

```
docker pull jenkins/jenkins
```

输出将类似于所示，其中`Docker`镜像中的每一层都在被下载：

```
Using default tag: latest
latest: Pulling from jenkins/jenkins
60bdaf986dbe: Pull complete 
dfad4ee37376: Pull complete 
206558d801c7: Pull complete 
a5c2ffb5ffef: Pull complete 
f0c0bc8bfcc6: Pull complete 
064531224ab4: Pull complete 
96aa304ced3c: Pull complete 
056f1f47a471: Pull complete 
ac5fc7f80726: Pull complete 
8a59881e61b3: Pull complete 
361281efe43a: Pull complete 
aa0d9cfb3420: Pull complete 
Digest: sha256:d4f805f9c225ee72c6ac8684d635eb8ec236569977f4cd6f9acd7c24a5d56985
Status: Downloaded newer image for jenkins/jenkins:latest
docker.io/jenkins/jenkins:latest
```

接下来你运行`Docker`容器：

```
docker run --name jenkins -p 8080:8080 jenkins/jenkins
```

此命令为你的`Docker`容器命名为`jenkins`，以便以后引用。它还暴露了端口`8080`，以便你可以在浏览器中访问它。如果该端口在你的机器上被占用，请随意使用其他。

控制台输出将包含类似下面的消息：

```
Jenkins initial setup is required.
An admin user has been created. Please use this password to proceed.
This may also be found at: /var/jenkins_home/secrets/initialPassword
```

任务是由`triggers`（触发器）启动的。一种流行的触发器类型是源代码提交。毕竟，只有当你自动化构建以便在每次发生变化时启动构建时，持续集成才能发挥作用。或者你也可以使用基于时间的触发器，它根据指定的计划启动。例如，你可能想在深夜运行耗缓慢的测试。你可以让一个任务触发另一个任务，这是链接不同任务类型的有用策略。最后，你可以通过 API 让 Jenkins 外部的事件触发任务。

`dashboard`（仪表板）列出了你所有的任务。你可以将它们组织在`folders`（文件夹）中。事实上，你可以嵌套任意层级的文件夹。你还可以创建`views`（视图）来控制你看到的内容。

Jenkins 在`workspace`（工作空间）中存储构建文件。构建文件的示例包括从 Git 检出的文件，以及来自你的 Maven 或 Gradle 构建的目标或构建目录。构建创建的项目被称为`artifacts`（产物）。产物可以被`archived`（存档），这样即使工作空间被删除，你也可以在 Jenkins 中看到它们。

### 创建任务

在接下来的章节中，你将学习如何创建三种任务：

*   一个简单的自由风格任务
*   一个运行 Maven 的任务
*   一个运行 Gradle 和流水线（pipeline）的任务

自由风格任务要求你使用 Jenkins 用户界面指定你的构建配置。自由风格方法的学习曲线比流水线更容易，并且适用于大多数情况。自由风格任务让你通过左侧导航栏中的链接查看工作空间。

流水线（Pipelines）允许你使用代码表示你的构建。它们还允许你将构建拆分为多个阶段（stages）。

流水线有两种类型：脚本式（scripted）和声明式（declarative）。在本书中，我们对 Maven 使用脚本流水线，对 Gradle 使用声明式流水线，以便你可以看到每种示例。流水线任务在特定构建上提供工作空间链接，而不是在任务级别。

#### 创建简单的自由风格任务

要创建一个任务，请按照以下步骤操作：

1. 点击左侧导航栏中的`New Item`（新建项目）。
2. 给它一个名称（在示例中为`freestyle-timer`）。
3. 选择任务类型`Freestyle Project`（自由风格项目）。
4. 点击`OK`。

Jenkins 将创建任务并自动带你进入配置界面。任务中有几个配置部分，如图 4.15 所示。

![Jenkins 窗口的截图。左侧显示配置，包括常规、源码管理、构建触发器、构建环境、构建步骤和构建后操作。选中了 general 选项。右侧显示了标题为 general 的描述框和两个复选框。](img/c04f015.png)

`图 4.15` 所示：

```
H * * *
```

图 4.15：Jenkins 自由风格部分

General（常规）包含供选择选项的复选框。例如，你可以控制 Jenkins 保存多少个旧构建，或者在当前构建正在运行时是否运行另一个构建。

Source Code Management（源码管理）允许你指定你正在使用的版本控制系统。Git 包含在推荐插件中。如果你使用不同的 VCS，可以从 Jenkins Plugin Manager 页面为它安装插件。还有仓库 URL 和连接所需的任何凭据的字段。

Build Triggers（构建触发器）是你选择什么触发构建的地方。在这个示例中，我们将使用`Build Periodically`（定期构建）来展示如何使用计划。还有 GitHub 提交触发器和轮询仓库的选项。告诉 GitHub 启动构建的触发器被称为`push`。相比之下，`polling`（轮询）请求仓库定期检查是否有更改，如果有，则执行构建。

Build Environment（构建环境）允许你配置有关 Jenkins 应该如何行为的信息。例如，你可以让 Jenkins 为每个日志条目添加时间戳，或者你可以设置 Jenkins 何时应该杀死长时间运行的构建的策略。

Build Steps（构建步骤）是实际的构建，你可以在此处配置运行的一个或多个构建步骤。例如，你可以让 Jenkins 从命令行运行命令，或者你可以配置它。

Post-build Actions（构建后操作）允许你处理构建后的结果。现在你了解了自由风格任务可以做什么，让我们创建一个每小时运行一次的任务。如图 4.15 所示：

```
H * * *
```



图 4.15：Jenkins 自由风格部分

`General`（常规）包含供你选择选项的复选框。例如，你可以控制 Jenkins 保存多少个旧构建，或者在当前构建正在运行时是否运行另一个构建。

`Source Code Management`（源码管理）允许你指定你正在使用的版本控制系统。Git 包含在推荐插件中。如果你使用不同的 VCS，可以从 Jenkins Plugin Manager 页面为它安装插件。还有仓库 URL 和连接所需的任何凭据的字段。

`Build Triggers`（构建触发器）是你选择什么触发构建的地方。在这个示例中，我们将使用 `Build Periodically`（定期构建）来展示如何使用计划。还有 GitHub 提交触发器和轮询仓库的选项。告诉 GitHub 启动构建的触发器被称为 `push`。相比之下，`polling`（轮询）请求仓库定期检查是否有更改，如果有，则执行构建。

`Build Environment`（构建环境）允许你配置有关 Jenkins 应该如何行为的信息。例如，你可以让 Jenkins 为每个日志条目添加时间戳，或者你可以设置 Jenkins 何时应该杀死长时间运行的构建的策略。

`Build Steps`（构建步骤）是实际的构建，你可以在此处配置运行的一个或多个构建步骤。例如，你可以让 Jenkins 从命令行运行命令，或者你可以配置它。

`Post-build Actions`（构建后操作）允许你处理构建后的结果。现在你了解了自由风格任务可以做什么，让我们创建一个每小时运行一次的任务。如图 4.15 所示：

```
H * * *
```

任务是由 `triggers`（触发器）启动的。一种流行的触发器类型是源代码提交。毕竟，只有当你自动化构建以便在每次发生变化时启动构建时，持续集成才能发挥作用。或者你也可以使用基于时间的触发器，它根据指定的计划启动。例如，你可能想在深夜运行耗缓慢的测试。你可以让一个任务触发另一个任务，这是链接不同任务类型的有用策略。最后，你可以通过 API 让 Jenkins 外部的事件触发任务。

`dashboard`（仪表板）列出了你所有的任务。你可以将它们组织在 `folders`（文件夹）中。事实上，你可以嵌套任意层级的文件夹。你还可以创建 `views`（视图）来控制你看到的内容。

Jenkins 在 `workspace`（工作空间）中存储构建文件。构建文件的示例包括从 Git 检出的文件，以及来自你的 Maven 或 Gradle 构建的目标或构建目录。构建创建的项目被称为 `artifacts`（产物）。产物可以被 `archived`（存档），这样即使工作空间被删除，你也可以在 Jenkins 中看到它们。

### 创建任务

在接下来的章节中，你将学习如何创建三种任务：

*   一个简单的自由风格任务
*   一个运行 Maven 的任务
*   一个运行 Gradle 和流水线（pipeline）的任务

自由风格任务要求你使用 Jenkins 用户界面指定你的构建配置。自由风格方法的学习曲线比流水线更容易，并且适用于大多数情况。自由风格任务让你通过左侧导航栏中的链接查看工作空间。

流水线（Pipelines）允许你使用代码表示你的构建。它们还允许你将构建拆分为多个阶段（stages）。

流水线有两种类型：脚本式（scripted）和声明式（declarative）。在本书中，我们对 Maven 使用脚本流水线，对 Gradle 使用声明式流水线，以便你可以看到每种示例。流水线任务在特定构建上提供工作空间链接，而不是在任务级别。

#### 创建简单的自由风格任务

要创建一个任务，请按照以下步骤操作：

1.  点击左侧导航栏中的 `New Item`（新建项目）。
2.  给它一个名称（在示例中为 `freestyle-timer`）。
3.  选择任务类型 `Freestyle Project`（自由风格项目）。
4.  点击 `OK`。

Jenkins 将创建任务并自动带你进入配置界面。任务中有几个配置部分，如图 4.15 所示。

![Jenkins 窗口的截图。左侧显示配置，包括常规、源码管理、构建触发器、构建环境、构建步骤和构建后操作。选中了 general 选项。右侧显示了标题为 general 的描述框和两个复选框。](img/c04f015.png)

`图 4.15` 所示：

```
H * * *
```

### 图 4.18: Maven 工具配置

企业中的仓库需要身份验证。

除了指定仓库外，你还需要指定分支。分支规格符字段默认为认为 `*/master`，这是旧版本 Git 在将其更改为 `main` 之前用于默认分支的名称。将其更改为 `*/main` 或你的主分支名称。

下一步是告诉自由风格作业（freestyle job）运行 Maven。为此，请创建一个类型为 `Invoke top-level Maven targets`（调用顶层 Maven 目标）的构建步骤。从下拉列表中选择你之前创建的 Maven 版本，并在目标中输入 `clean verify`。此仓库使用子文件夹而不是在根目录下放置 `pom.xml` 文件；点击“高级”（Advanced），并在 POM 处输入 `maven/with-dependency/pom.xml`。图 4.19 显示了该作业的配置。

![一个 git 窗口的截图。它要求仓库、URL 以及要构建的分支，并使用提到的版本和目标调用顶层 maven 目标。](img/c04f019.png)

### 图 4.19: Maven 自由风格作业配置

## 创建 Gradle 自由风格作业

与 Maven 不同，你不需要设置 Gradle 工具配置即可开始。Gradle 执行文件已经存在于 Gradle 项目仓库中了。

与 Maven 类似，你创建一个自由风格作业并设置源码管理。使用与 Maven 相同的 URL 和分支。下一步是告诉自由风格作业运行 Gradle。你创建一个类型为 `Invoke Gradle script`（调用 Gradle 脚本）的构建步骤。选择 Gradle Wrapper 并将包装位置设置为 `gradle/groovy/with-dependency`。

然后为任务输入 `build`。最后，点击“高级”（Advanced），并在根构建脚本处输入 `gradle/groovy/with-dependency`。图 4.20 显示了该作业配置的 Gradle 部分。

![一个调用 gradle script 作业配置窗口的截图。它描绘了两个标记为 invoke gradle 和 use gradle wrapper 的选项。选中了 gradle wrapper 选项。它要求包装位置、任务和根构建脚本。](img/c04f020.png)

### 图 4.20: Gradle 自由风格作业配置

## 创建 Maven 流水线

Pipeline Maven Integration 插件让使用 Maven 的流水线变得更加简单，因此在创建流水线之前安装它：

1. 点击左侧导航中的“Manage Jenkins”（管理 Jenkins）。
2. 点击“Plugins”（插件）。
3. 点击左侧导航栏中的“Available Plugins”（可用插件）。
4. 在搜索栏中输入 `Pipeline Maven` 以过滤可用插件列表。
5. 点击该插件名称左侧的复选框。
6. 点击“Install”（安装）。
7. 勾选“在安装完成且没有作业运行时重启 Jenkins”左侧的复选框。

这将导致 Jenkins 重启。现在你已经有了插件，就可以创建流水线了。在创建作业时，选择“Pipeline”（流水线）而不是“Freestyle Project”（自由风格项目）。

流水线作业允许你选择将流水线直接包含在作业配置中，或从仓库获取。对于前者，在 Definition 标签下选择“Pipeline Script”（流水线脚本）。然后在下方的文本区域中粘贴你的流水线，如图 4.21 所示。

![一个标题为 definition 的窗口截图。两个子标题是 pipeline script 和 script。在该脚本中，输入了 11 行程序。尝试使用窗口右侧显示的示例流水线选项。](img/c04f021.png)

### 图 4.21: Maven 流水线脚本

```
node {

   stage('Source Control') {

      git branch: 'main', url: 'https://github.com/realworldjava/Ch04-CICD'

   }

   stage('Build') {

      withMaven(maven: 'Maven 3.9') {

         sh "\$MVN_CMD -f maven/with-dependency clean verify"

      }

   }

}
```

此脚本化流水线有两个阶段：`Source Control` 和 `Build`。第一个拉取仓库的主分支。后者使用 `withMaven` 的功能来设置 Maven 环境。在该上下文中，它在操作系统 shell 中调用 Maven 命令。如果你在 Windows 上运行，请使用 `bat` 代替 `sh`。

或者，你可以按照以下步骤将流水线本身存储在源码控制中，如图 4.22 所示：

1. 在 Definition 标签下从 SCM 选择“Pipeline script”（流水线脚本）。
2. 为 SCM 选择 Git。
3. 输入仓库 URL，例如 [`https://github.com/realworldjava/Ch04-CICD`](https://github.com/realworldjava/Ch04-CICD)。
4. 将 Branch Specifier 更改为 `*/main`。
5. 将 Script Path 更改为 `maven/using-jenkinsfile/Jenkinsfile`。

![描绘来自 SCM 的 maven 流水线的窗口截图。它要求提供详细信息：定义、分支规格符和脚本路径。](img/c04f022.png)

### 图 4.22: 来自 SCM 的 Maven 流水线

## 创建 Gradle 流水线

与 Maven 不同，你不需要设置 Gradle 工具配置即可开始。Gradle 执行文件已经存在于 Gradle 项目仓库中了。

```
pipeline {

   agent any

   stages {

      stage('Source Control') {

         steps {

           git branch: 'main', url: 'https://github.com/realworldjava/Ch04-CICD'

         }

      }

      stage('Build') {

        steps {

          sh "\$MVN_CMD -f maven/with-dependency clean verify"

        }

      }

   }

}
```

## 理解 Jenkins 其他功能

当你使用 Jenkins 时，你会发现有很多内容可以探索。在本节中，我们将简要介绍 Jenkins 可以执行的功能类型。

#### 组织作业

当你选择 New Item（新建项目）时，不仅限于作业。你还可以创建文件夹。Jenkins 文件夹的工作就像电脑上的文件夹一样。你可以将文件夹嵌套在其他文件夹中，以帮助组织作业。

你还可以创建 `views`（视图）作为查看作业的另一种方式。点击作业列表上方的加号（`+`）创建一个视图。默认情况下，有一个可配置的 `list view`（列表视图）。你可以手动选择要放入视图的作业，或者提供一个正则表达式来指定模式。第 10 章，“使用正则表达式进行模式匹配”将涵盖如何通用使用正则表达式。列表视图还让你控制显示哪些列。视图还可以遍历文件夹。

Dashboard View 插件提供了强大多的视图类型。它允许你选择小部件（portlets）并将其锚在 Jenkins 屏幕的顶部、底部、左侧和右侧。你可以在每个区域放置任意数量的小部件，实现良好的布局控制。部件包含许多统计数据，如构建、作业和测试。你甚至可以将你的仪表板设为全屏视图，隐藏内置的 Jenkins 导航栏。

### 通知用户

如果没有人知道，失败的作业将无法修复！默认情况下，Jenkins 在构建失败时提供电子邮件通知。你可以提供一个或多个电子邮件地址，并指定是希望在每次未通过的构建时发送邮件，还是仅在第一次发送。此外，你还可以包含导致构建失败的提交者。

可编辑的电子邮件通知（editable email notification）提供了更多的控制。你可以指定邮件、主题和内容模板的字段。你还有附加构建日志文件的选项。该插件的强大功能之一是它为你提供了对发送邮件时机的细粒度控制。你可以选择成功和失败的任何组合，甚至为不同情况向不同的人发送通知。

除了电子邮件通知外，Jenkins 还通过插件支持许多其他通知类型。例如，SMS 插件可以在发生故障时发送短信。Notify-Events 插件支持 Skype、Telegram、语音通话等。针对 Slack 或 Amazon SNS 主题，还有专门的通知器。

如果这些主动/推送式通知器不能满足你的需求，你可以使用被动/拉取方法。Jenkins 通过 `/rssAll`、`/rssFailed` 和 `/rssLatest` 馈送支持 RSS。

无论你选择哪种通知器，请确保它是能够引起人们注意的。毕竟，修复构建是高优先级任务，除非有人知道它坏了，否则这不会发生！

### 查看更改

每个 Jenkins 作业在左侧导航中都有一个 `Changes`（更改）链接。它告诉你自上次构建以来存储库中发生了变化。这是一个示例：

```
#8 (2024 年 5 月 7 日, 下午 9:36:22)

add jenkinsfile — jeanne / githubweb
```



这条消息告诉你该作业的第 8 次构建是在 5 月 7 日运行的。它提供了提交注释、用户 ID 以及指向 Git 提交的链接，你可以在那里查看详情。当你的构建失败时，此功能非常有用，你可以确切看到发生了什么变化。

## 使用 SONAR 进行扫描

Jenkins 是你 CI/CD 构建的中心，但许多其他工具通常会与之集成。检出/源码控制、构建/编译和单元测试阶段完全在 Jenkins 上进行。相比之下，Jenkins 执行质量检查，这通常使用 SonarQube，如接下来所述。其他工具用于检查依赖项。

让我们更详细地查看 SonarQube。SonarQube 由一家名为 SonarSource 的厂商制造。它有商业版本和免费开源版本。它是一个静态分析工具，这意味着 SonarQube 在不运行代码的情况下识别代码中的问题。此外，SonarQube 静态分析扫描将成为你自由风格作业（freestyle job）的一个步骤。

SonarQube 带有许多规则，适用于你可以想象的几乎每种编程语言。甚至用于验证 XML 和 JSON 的工具（参见附录）也被包含在！这些规则检查各种问题，包括常见的错误、性能问题和安全问题。

SonarQube 还允许你配置质量门（quality gate）。如果高优先级规则通过或测试失败，质量门将失败。你还可以设置代码覆盖率百分比等条件。如果你查看在 Jenkins 构建期间生成的 SonarQube 报告，你会发现你的项目代码有了大幅改进。

SonarQube 执行静态分析且不运行你的代码。尽管如此，它会摄取来自 Jenkins 构建的 JUnit 测试和代码覆盖率报告，这使得 SonarQube 能够生成显示代码质量和代码覆盖率的优秀报告。

## 解释 CI/CD 实践

Jenkins 是一个 CI/CD 工具，因此你需要了解一些 CI/CD 实践才能有效使用它。

* **版本控制：** 团队中的每个人都必须向同一个存储库提交，并应该定期提交。
* **自动化构建：** 构建必须是全自动化且可复的。仅仅在某一个开发者的机器上运行是不够的。
* **触发：** 每次提交都必须触发构建并运行自动化测试，以快速发现失败。
* **修复损坏的构建是最高优先级：** 在提交更多更改之前，必须修复损坏的构建。
* **增量更改：** 频繁进行小更改并频繁提交。
* **保持 CI 构建运行快速：** 构建应该尽可能快地运行。像 Sonar 这样较慢的步骤可以在不是每次提交都运行的流水线中运行。例如，它可能在夜间运行。
* **可见性：** 团队中的所有人和所有利益相关者都必须能够看到构建状态。
* **自动化测试：** 测试必须始终通过，以确保代码已准备好进行部署。
* **自动化部署：** 部署不能需要人工干预。

## 进一步参考

* *Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment* (Addison-Wesley, 2020), [`https://maven.apache.org/guides/index.html`](https://maven.apache.org/guides/index.html)
* Maven 指南, [`https://maven.apache.org/download.cgi`](https://maven.apache.org/download.cgi)
* Maven super POM, [`https://maven.apache.org/ref/3.9.6/model-builder/super-pom.xml`](https://maven.apache.org/ref/3.9.6/model-builder/super-pom.xml)
* Gradle 指南, [`https://docs.gradle.org/current/userguide/userguide.html`](https://docs.gradle.org/current/userguide/userguide.html)
* Gradle 插件, [`https://docs.gradle.org/current/userguide/java_plugin.html`](https://docs.gradle.org/current/userguide/java_plugin.html)
* Gradle 安装, [`https://gradle.org/install`](https://gradle.org/install)
* 下载 Docker, [`https://docs.docker.com/engine/install`](https://docs.docker.com/engine/install)
* 下载 Jenkins, [`https://www.jenkins.io/download`](https://www.jenkins.io/download)
* Jenkins 流水线文档, [`https://www.jenkins.io/doc/book/pipeline`](https://www.jenkins.io/doc/book/pipeline)
* Jenkins 插件, [`https://plugins.jenkins.io`](https://plugins.jenkins.io)
* SonarSource, [`https://www.sonarsource.com`](https://www.sonarsource.com)

## 总结

在本章中，你学习了 CI/CD。关键概念包括：

* 使用 Maven `pom.xml` 构建
* 使用 Groovy 的 Gradle `build.gradle` 构建
* 使用 Kotlin 的 Gradle `build.gradle.kts` 构建
* 创建 Jenkins 风格作业和流水线作业
* SonarQube（静态分析工具）的作用
* 关键 CI/CD 原则

# 5

使用日志框架捕获应用程序状态

当你开始学习 Java 编程时，你可能使用 `System.out.println` 输出信息，用于排查代码为何没有按预期工作的原因。例如：

```
public void run(int count) {
   System.out.println("count=" + count);
   // 在此处运行逻辑
}
```

随着你 Java 职业的成熟，是时候将那些 `System.out.println` 调用替换为日志框架了。在本章中，你将学习日志框架的益处，学习如何使用最常用的日志框架，并比较这些日志框架以选择最适合你的一种种。由于许多日志框架的很多概念是相同的，即使你打算在工作中使用不同的日志框架，也请先阅读“使用 Java 实用程序日志（Java Util Logging）”部分。此外，每个日志框架都有许多功能。本章涵盖了最常用的功能，但如果你有更特殊的需求，请检查相关文档。例如，所有的日志框架都允许你通过 Java 代码设置日志配置，而不是通过更常用的外部文件方式。

你可能会看到人们使用“日志库”（logging libraries）而不是“日志框架”（logging frameworks）。本章使用 `framework`（框架）一词，但我们的意思一样。

## 需要超越打印（Needing to Move Beyond Print）

有许多理由说明你应该选择使用日志框架而不是 `println` 方法调用。原因之一是你能够控制日志的量。虽然在排错时你可能想输出 `count` 的值，但一旦你的应用程序有很多用户，这只会让日志变得混乱！日志框架允许你在代码中保留这些日志语句，但允许你指定一个日志级别，从而在每个环境中只打印你真正想要记录的日志。

使用日志框架的另一个原因是方便输出的去向。`System.out` 和 `System.err` 在控制台中会混杂在一起。如果你使用日志框架，可以分离你的日志输出，使其更易理解。此外，你还增加了安全性，因为有时操作系统的人会有访问 `System.out` 的权限，而他们并不是你希望访问你最私密日志信息的人。

此外，你可能需要两套日志：排错日志（troubleshooting logs）和审计日志（audit logs）。审计日志用于查看谁在什么时候做了或访问了什么。这种级别的控制由主要（主要的）日志框架提供。

日志框架可以通过存储消息进行异步日志，使你的应用程序运行更快，而不是让你的应用程序等待缓慢的 I/O 输出操作实时完成。最后，日志框架可以处理日志文件的轮转，这样你就有最新的日志可用，而不是让磁盘空间不断增加。

## 使用 Java Util Logging

Java Util Logging（Java 实用程序日志）内置在 Java 中；不需要通过 `Maven` 或 `Gradle` 引入依赖。事实上，Java Util Logging 自 Java 1.4 起就已经被包含了！以下显示了一个简单的日志示例：

```
1:  package com.wiley.realworldjava.logging.jul;
2:  import java.util.logging.Logger;
3:
4:  public class BasicLogging {
5:     private static final Logger LOGGER =
6:        Logger.getLogger(BasicLogging.class.getName());
7:
8:     public static void main(String[] args) {
9:        LOGGER.severe("Something bad happened!");
10:    }
11: }
```

第 5 行和第 6 行创建了 `Logger`。`Logger.getLogger()` 调用是一个工厂。这种设计模式用于为 API 提供的比直接调用构造函数更多的许多控制权。

在第 6 行中，我们可以调用等效代码：

```
Logger.getLogger("com.wiley.realworldjava.logging.jul.BasicLogging");
```

但如果你进行重构并更改了类名，就会有过时的风险。更好的方法是使用 `class.getName()`，这会导致类在重命名时日志器的名称也自动重命名。

第 9 行是日志语句。Java Util Logging 中的 `severe()` 告诉日志器使用最高优先级的日志级别。运行此代码输出如下：

```
Feb 11, 2024 9:16:22 PM com.wiley.realworldjava.logging.jul.BasicLogging main
SEVERE: Something bad happened!
```

默认情况下，此输出包含来自日志发生地的以下信息：

* 日期和时间
* 全限定类名
* 方法名
* 日志级别（`SEVERE`）
* 日志消息

在后续章节，你将看到更多关于使用 Java Util Logging 的细节。

### 比较日志级别

理解日志级别的概念是非常重要的。可以作为环境变量或启动属性为程序设置日志级别。假设程序被设置为使用 `WARNING` 日志级别。（在下一节中，你将学习如何设置日志级别。）让我们看看以下三个日志语句的输出：

```
private static final Logger LOGGER = 
   Logger.getLogger(BasicConfig.class.getName());

public static void main(String[] args) {
   LOGGER.severe("this is bad");
   LOGGER.warning("be careful");
   LOGGER.info("just to let you know");
}
```

输出仅包含两条日志消息！发生了什么？

```
Feb 11, 2024 9:25:48 PM com.wiley.realworldjava.logging.jul.BasicConfig main
SEVERE: this is bad
Feb 11, 2024 9:25:48 PM com.wiley.realworldjava.logging.jul.BasicConfig main
WARNING: be careful
```

注意 `severe()` 和 `warning()` 调用是如何记录的，但 `info()` 调用没有被记录。Java Util Logging 只记录目标日志级别或更高级请求。

Java Util Logging 有七个级别。表 5.1 显示了日志级别及其用途。

| 日志级别 | 预期用途 |
| :--- | :--- |
| `SEVERE` | 严重失败。 |
| `WARNING` | 潜在问题。 |
| `INFO` | 信息消息。 |
| `CONFIG` | 配置消息。 |
| `FINE` | 追踪消息。 |
| `FINER` | 更详细的追踪消息。 |
| `FINEST` | 最详细的追踪消息。 |
| `ALL` | 所有消息。 |
| `OFF` | 指定不日志。 |

假设日志级别被设置为 `INFO`。表 5.2 显示了哪些方法调用会被记录。

| 日志级别 | `SEVERE()` | `WARNING()` | `INFO()` | `FINE()` | `FINER()` | `FINEST()` |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `SEVERE` | 是 | 是 | 是 | 是 | 是 | 是 |
| `WARNING` | 否 | 是 | 是 | 是 | 是 | 是 |
| `INFO` | 否 | 否 | 是 | 是 | 是 | 是 |
| `FINE` | 否 | 否 | 否 | 是 | 是 | 是 |
| `FINER` | 否 | 否 | 否 | 否 | 是 | 是 |
| `FINEST` | 否 | 否 | 否 | 否 | 否 | 是 |
| `ALL` | 是 | 是 | 是 | 是 | 是 | 是 |
| `OFF` | 否 | 否 | 否 | 否 | 否 | 否 |

### 格式化值

通常，你想记录变量值而不仅仅是静态消息。内置的 `String.format` 方法为 Java Util Logging 格式化值。例如：

```
LOGGER.severe(String.format("%s: %.1f is %d/%d", "Division", 1.5, 3, 2));
```

此输出的消息部分如下：

```
SEVERE: Division: 1.5 is 3/2
```

此示例使用了常用的格式化占位符：`%s`（字符串）、`%f`（浮点数）和 `%d`（整数）。这些占位符会被随后的值替换。它们还显示了如何指定浮点数小数点后所需的数字位数。此代码没有显式地调用 `Formatter` 类，但它是由 `String.format` 在底层调用的。除了之前提到的，还有许多其他占位符，请参阅 Javadoc `Formatter` 类。

### 传递基础配置

Java Util Logging 带有默认配置，因此你可以开始记录日志而无需提供任何外部配置。但你很快就会使用自己的配置来定制它。

默认配置文件位于你 Java 目录下的 `conf` 文件夹中，文件名为 `logging.properties`。例如，在 Windows 上，路径可能如下：

```
c:\Program Files\Java\jdk21\conf\logging.properties
```

在 Mac 上，结构更深层级，并且如下所示：

```
/Library/Java/JavaVirtualMachines/jdk-21.jdk/Contents/
   Home/conf/logging.properties
```

由于该文件位于 `Java` 目录中，你不应该修改它的内容。更好的做法是为你的日志属性指定一个自定义位置。例如，项目中的 `src/main/resources` 是一个常用位置，因为该文件会与你的项目一起存储在版本控制中。该位置还会导致 Maven 或 Gradle 将文件自动放置在与编译后的源文件相同的位置。因此，它在运行时可以作为类路径（classpath）资源可用，你无需进行任何额外工作即可访问它。

首先，设置一个基础日志配置文件。这个文件显示了 表 5.2 中使用的 `WARNING` 级别：

```
.level= WARNING
handlers= java.util.logging.ConsoleHandler
```

要让 Java 使用此文件，你需要设置 `java.util.logging.config.file` 系统属性。实现此操作的方法一种是在命令行。

```
java -Djava.util.logging.config.file=src/main/resources/
   logging-warning.properties src/main/java/com/wiley/realworldjava/
   logging/jul/BasicConfigCommandLine.java
```

要学习如何使用这些工具设置系统属性，请参见第 2 章“了解你的 IDE：成功的秘诀”；第 4 章“使用 Maven、Gradle 和 Jenkins 自动化你的 CI/CD 构建”以及第 6 章“了解 Spring Framework”。

另一种设置系统属性的方法是在代码中设置。这在实际代码中并不是常见方法。通常不推荐这种方法，因为更改位置需要重新编译。然而，本章的仓库使用了这种方法来方便使用各种属性文件。

由于属性必须在实例化 `Logger` 之前设置，因此它是在 `static` 中完成的。

```java
import java.util.logging.Logger;

public class BasicConfig {
```



默认配置文件位于你 Java 目录下的 `conf` 文件夹中，文件名为 `logging.properties`。例如，在 Windows 上，路径可能如下：

```
c:\Program Files\Java\jdk21\conf\logging.properties
```

在 Mac 上，结构更深层级，并且如下所示：

```
/Library/Java/JavaVirtualMachines/jdk-21.jdk/Contents/
   Home/conf/logging.properties
```

由于该文件位于 `Java` 目录中，你不应该修改它的内容。更好的做法是为你的日志属性指定一个自定义位置。例如，项目中的 `src/main/resources` 是一个常用位置，因为该文件会与你的项目一起存储在版本控制中。该位置还会导致 Maven 或 Gradle 将文件自动放置在与编译后的源文件相同的位置。因此，它在运行时可以作为类路径（classpath）资源可用，你无需进行任何额外工作即可访问它。

首先，设置一个基础日志配置文件。这个文件显示了 表 5.2 中使用的 `WARNING` 级别：

```
.level= WARNING
handlers= java.util.logging.ConsoleHandler
```

要让 Java 使用此文件，你需要设置 `java.util.logging.config.file` 系统属性。实现此操作的方法一种是在命令行。

```
java -Djava.util.logging.config.file=src/main/resources/
   logging-warning.properties src/main/java/com/wiley/realworldjava/
   logging/jul/BasicConfigCommandLine.java
```

要学习如何使用这些工具设置系统属性，请参见第 2 章“了解你的 IDE：成功的秘诀”；第 4 章“使用 Maven、Gradle 和 Jenkins 自动化你的 CI/CD 构建”以及第 6 章“了解 Spring Framework”。

另一种设置系统属性的方法是在代码中设置。这在实际代码中并不是常见方法。通常不推荐这种方法，因为更改位置需要重新编译。然而，本章的仓库使用了这种方法来方便使用各种属性文件。

由于属性必须在 `Logger` 实例化之前设置，因此它是在 `static` 块中完成的。

```java
import java.util.logging.Logger;

public class BasicConfig {
   static { System.setProperty("java.util.logging.config.file",
      "src/main/resources/logging-warning.properties"); };

   private static final Logger LOGGER = 
      Logger.getLogger(BasicConfig.class.getName());

   public static void main(String[] args) {
      LOGGER.severe("this is bad");
      LOGGER.warning("be careful");
      LOGGER.info("just to let you know");
   }
}
```

### 设置日志输出目标

到为止，示例都使用了 `ConsoleHandler`。以下是最常用的处理器：

* `ConsoleHandler`: 写入 `System.err`
* `FileHandler`: 写入文件，可选地进行轮转
* `SocketHandler`: 写入到远程计算机的端口

以下配置显示了如何使用 `FileHandler` 的基本功能：

```
1: .level= WARNING
2: handlers=java.util.logging.FileHandler
3: 
4: java.util.logging.FileHandler.pattern = java-log-%u.log
5: java.util.logging.FileHandler.limit = 100
6: java.util.logging.FileHandler.count = 2
```

第 4 行指定了日志文件的去向。在这个示例中，它们位于代码的根目录下。在实际应用程序中，绝对路径是最常见的。`%u` 表示使用唯一数字。每个文件获得一个数字以避免命名冲突。

第 5 行说明了每个文件应该包含多少字节。通常这个数字会大得多，例如 100,000，但为了演示，我们使用了一个较小的数字。一旦超过这个数字，将自动开始一个新文件。如果你省略了 `FileHandler.limit` 属性，文件将没有上限，可能导致产生无法管理的大型文件。

第 6 行指定了最多两个日志文件。针对一个产生大量数据的程序运行此配置会创建两个文件：

```
java-log-0.log0
java-log-0.log1
```

其余的数据就丢失了。这就是*日志轮转*（log rotation）的含义；旧数据会被轮换并被最新数据替换。注意，如果你漏掉了第 6 行，Java Util Logging 将不断生成文件，可能会耗尽你磁盘上的所有空间！通常你会在磁盘上保留一周或一个月的日志，但这很大程度上取决于你的团队和你的应用程序。

每个文件包含类似以下的内容。这种格式被称为可扩展标记语言（eXtensible Markup Language, XML）。有关 XML 的更多细节，请参见附录“读取和写入 XML、JSON 和 YAML”。每个处理器都有一个默认格式。`ConsoleHandler` 使用文本格式。`FileHandler` 使用 XML。

```xml
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!DOCTYPE log SYSTEM "logger.dtd">
<log>
<record>
   <date>2024-02-14T00:00:00</date>
   <level>INFO</level>
   <ms>123456</ms>
   <class>com.example.Example</class>
   <thread>main</thread>
   <message>example message</message>
</record>
</log>
```

`SimpleFormatter` 类的 Javadoc 提供了更多细节。

以下示例创建了一个我们恰恰命名为 `com.wiley.realworldjava.logging.jul.MultipleLevelsLogging` 的日志器：

```java
package com.wiley.realworldjava.logging.jul;

import java.util.logging.Logger;
import com.wiley.realworldjava.logging.jul.child.ChildLogging;

public class MultipleLevelsLogging {
   private static final Logger LOGGER = 
     Logger.getLogger(MultipleLevelsLogging.class.getName());

   public static void main(String[] args) {
      LOGGER.severe("Parent logging");
      LOGGER.warning("Parent logging");
      log();
   }
}
```

Java Util Logging 会查找它能找到的最特定的记录器（logger）。在这种情况下，它是 `com.wiley.realworldjava.logging.jul` 记录器，因此使用了 `SEVERE` 且 `Parent logging` 仅为 `MultipleLevelsLogging` 记录一次。相比之下，接下来的类使用了 `com.wiley.realworldjava.logging.jul.child` 记录器，我们之前将其配置为记录 `WARNING` 级别日志，因此导致 `Child logging` 被打印两次，一次针对 `SEVERE`，一次针对 `WARNING`：

```java
package com.wiley.realworldjava.logging.jul.child;

import java.util.logging.Logger;

public class ChildLogging {
   private static final Logger LOGGER = Logger
      .getLogger(ChildLogging.class.getName());

   public static void log() {
      LOGGER.severe("Child logging");
      LOGGER.warning("Child logging");
   }
}
```

当没有其他匹配的记录器时，会使用根记录器（root logger）。如果我们创建了一个名称为 `com.wiley` 的记录器，它将使用级别为 `INFO` 的根记录器。

你也可以对不反映应用程序包和类名称的记录器名称使用继承关系。在下面的示例中，你可以看到三个级别的记录器：根记录器、`custom` 和 `custom.child`：

```properties
.level= INFO
```



`custom.level= SEVERE`

`custom.child.level= WARNING`

`handlers=java.util.logging.ConsoleHandler`

这一次，记录器是使用记录器的名称（`custom` 和 `custom.child`）创建的，而不是包和类名。父/子关系仍然存在。事实上，两个记录器都用于同一个类中！

```java
public class MultipleLevelsLoggingWithManualHierarchy {

   public static void main(String[] args) {

      Logger parentLogger = Logger.getLogger("custom");

      Logger childLogger = Logger.getLogger("custom.child");

      parentLogger.severe("Parent logging");

      parentLogger.warning("Parent logging");

      childLogger.severe("Child logging");

      childLogger.warning("Child logging");

   }

}
```

所有的日志框架都有以这种方式工作的继承机制，因此本节仅提到 Java Util Logging，因为在该章节中首先涵盖了它。

## 使用 LOG4J

Log4j 是最老的 Java 日志框架之一，甚至早于 Java Util Logging。在多年里，它接受了许多更新并被广泛使用。

你可能在新闻中读过关于 Log4j 的报道。2021 年 12 月 9 日，公布了一个名为 Log4Shell 的重大安全漏洞，它允许攻击者在应用程序中运行任意代码。天哪！只要你使用的是 Log4j 2.17.2 或更高版本，就不必担心这个问题。

要在你的 Maven 或 Gradle 构建中使用 Log4j，请前往 Maven Central [`https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core`] 并找到适用于你构建工具的最新版本号。表 5.3 显示了在本文期间每种配置的情况。注意，你同时需要 API 和 Core 依赖。API 是接口，而 core 是实现。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-api</artifactId>
    <version>2.22.1</version>
</dependency>
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-core</artifactId>
    <version>2.22.1</version>
</dependency>
``` |
| Gradle (Groovy) | ```groovy
implementation group: 'org.apache.logging.log4j',
    name: 'log4j-api, version: '2.22.1'
implementation group: 'org.apache.logging.log4j',
    name: 'log4j-core', version: '2.22.1'
``` |
| Gradle (Kotlin) | ```kotlin
implementation("org.apache.logging.log4j:log4j-api:2.22.1")
implementation("org.apache.logging.log4j:log4j-core:2.22.1")
``` |

**[表 5.3]**：指定 Log4j 为依赖

获取适用于你构建工具的相应语法并将其包含在依赖中。以下是一个使用 Log4j 的简单程序：

```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class BasicLogging {

   private static final Logger LOGGER = LogManager.getLogger();

   public static void main(String[] args) {

      LOGGER.fatal("this is fatal");

   }

}
```

这两条日志语句的消息部分如下：

```
Division: 1.5 is 3/2
```

在第一个版本中，你使用 `{}` 作为你想要包含在输出中的每个值的占位符。`Log4j` 会自动识别类型并使用逻辑格式。注意 `1.5` 是如何被打印的，而无需指定在小数点后保留多少位数字。`Log4j` 提供了非常有用的逻辑默认值。

第二个版本使用了 `formatter` 日志器，它的语法与 `String.format` 相同。构建它更加耗时，但对格式提供了更大的控制力。

通常情况下，除非你有更细粒度的格式化需求，否则应该使用 `getLogger()`。如果你发现 `getLogger()` 在大多数情况下都用，只有在极少数情况下需要那种细粒度的控制，可以使用 `Logger.printf()` 仅在这些调用中使用格式化值语法，如下所示：

```java
import org.apache.logging.log4j.Level;
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class LoggingWithPrintf {

    private static final Logger LOGGER = LogManager.getLogger();

    public static void main(String[] args) {

        LOGGER.printf(Level.FATAL, "%s: %.1f is %d/%d", "Division", 1.5, 3, 2);

    }

}
```

`printf()` 方法代表“格式化打印”（print formatted），这是从 C 语言借用的知名构造。通过在你的日志器上调用 `printf()`，你可以传递格式化符号，而无需先创建一个 `formatter` 日志器。缺点是你必须将日志级别作为参数指定，而不是调用如 `fatal()` 这样与级别相关的方法。因此，我们建议仅在日志需求很少或完全不需要格式化时才使用它。否则，使用格式化日志器会让你的代码更简洁。

### 传递基础配置

`Log4j` 识别各种配置文件格式。如果发现多个文件，`Log4j` 会指定一个使用哪个文件的查找顺序。它首先查找系统属性 `log4j.configurationFile`。为了本章的简单起见，我们使用了系统属性的方法。在实际应用程序中，文件配置更为常见。

如果没有设置 `log4j.configurationFile`，`Log4j` 将按照列表中指定的顺序在类路径中搜索找到的配置文件：

- `log4j2-test.properties`
- `log4j2-test.yaml`
- `log4j2-test.yml`
- `log4j2-test.json`
- `log4j2-test.jsn`
- `log4j2-test.xml`
- `log4j2.properties`
- `log4j2.yaml`
- `log4j2.yml`
- `log4j2.json`
- `log4j2.jsn`
- `log4j2.xml`

配置文件方法是最常见的，因为将文件放在类路径中（通常在 `src/main/resources` 下）就足够了。

下一节描述了不同格式之间的区别。注意，列出的每个格式文件都有带有“test”和不带“test”的版本。如果你将文件放置在 `src/test/resources`，你的 JUnit 测试将拾取带有“test”的版本，这允许你的自动化测试轻松地使用与应用程序本身不同的日志配置。

最后，如果没有找到配置，`Log4j` 将使用默认的 `ERROR` 日志级别，将所有输出发送到控制台。要覆盖该默认设置，请将系统属性 `org.apache.logging.log4j.level` 设置为所需的级别：`INFO`、`DEBUG` 等。

### 比较配置文件格式

每种配置文件格式都可以用于表示相同的信息。以下示例都展示了如何将根级别（即默认级别）设置为 `ERROR`，同时将 `com.wiley.realworldjava` 及其子包的日志设置为 `INFO` 级别。由于它们的功能相同，你可以轻松地比较这些格式。第一个示例使用了 `log4j2.xml`：

```xml
1:  <?xml version="1.0" encoding="UTF-8"?>
2:  <Configuration status="WARN">
3:     <Appenders>
4:        <Console name="Console" target="SYSTEM_OUT">
5:           <PatternLayout pattern="%m%n"/>
6:        </Console>
7:     </Appenders>
8:     <Loggers>
9:        <Logger name="com.wiley.realworldjava" 
10:          level="info" additivity="false">
11:          <AppenderRef ref="Console"/>
12:       </Logger>
13:       <Root level="error">
14:          <AppenderRef ref="Console"/>
15:       </Root>
16:    </Loggers>
17: </Configuration>
```

在第 2 行，文件将日志级别设置为 `WARN`，用于记录有关配置错误的警告。随后第 4–6 行创建了一个的控制台 appender，模式为 `"%m%n"`，用于包含消息并跟换换行。第 8–16 行创建了两个日志器。第一个（第 9–12 行）使用控制台日志器将 `com.wiley.realworldjava` 日志器设置为 `INFO` 级别。

`.json`/`.jsn` 和 `.yaml`/`.yml` 版本的配置需要你向项目中添加一些额外的依赖项。它们都使用了来自流行的 Jackson 库的不同 API 进行解析。这些 API 并没有包含在 Log4j 本身的传递依赖中，因为它们是可选依赖，只有在你使用 JSON 或 YAML 时才需要，而属性或 XML 格式不需要。

要使用 Log4j2，请在 Maven Central 上查找依赖项：[`https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind`](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind) 和 [`https://mvnrepository.com/artifact/com.fasterxml.jackson.dataformat/jackson-dataformat-yaml`](https://mvnrepository.com/artifact/com.fasterxml.jackson.dataformat/jackson-dataformat-yaml)。为你的构建工具找到最新的版本号。请参阅表 5.5](#c05.xhtml_c05-tbl-0005) 和表 5.6](#c05.xhtml_c05-tbl-0006)分别获取 JSON 和 YAML 所需的额外依赖（使用的是本文写作时的最新版本号）。请注意，这两个依赖都会作为你所指定项的传递依赖项引入 `jackson-core`。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>2.16.1</version>
</dependency>
``` |
| Gradle (Groovy) | ```groovy
implementation group: 'com.fasterxml.jackson.core',
   name: 'jackson-databind', version: '2.16.1'
``` |
| Gradle (Kotlin) | ```kotlin
implementation(
  "com.fasterxml.jackson.core:jackson-databind:2.16.1")
``` |

#### 表 5.5 (#c05.xhtml_R_c05-tbl-0005): 指定 JSON 所需的 Jackson 依赖项 Log4j

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
    <groupId>com.fasterxml.jackson.dataformat</groupId>
    <artifactId>jackson-dataformat-yaml</artifactId>
    <version>2.16.1</version>
</dependency>
``` |
| Gradle (Groovy) | ```groovy
implementation group: 'com.fasterxml.jackson.dataformat',
   name: 'jackson-dataformat-yaml', version: '2.16.1'
``` |
| Gradle (Kotlin) | ```kotlin
implementation("com.fasterxml.jackson.dataformat:"
  + "jackson-dataformat-yaml:2.16.1")
``` |

#### 表 5.6 (#c05.xhtml_R_c05-tbl-0006): 指定 YAML 所需的 Jackson 依赖项 Log4j

以下显示了用 JSON 格式表示之前示例中的配置。Log4j 支持 `.json` 和 `.jsn` 文件扩展名。文件内容相同。

```json
{
  "configuration": {
    "status": "warn",
    "appenders": {
      "Console": {
        "name": "STDOUT",
        "PatternLayout": {
          "pattern": "%m%n"
        }
      }
    },
    "loggers": {
      "logger": {
        "name": "com.wiley.realworldjava",
        "level": "info",
        "additivity": "false",
        "AppenderRef": {
          "ref": "STDOUT"
        }
      },
      "root": {
        "level": "error",
        "AppenderRef": {
          "ref": "STDOUT"
        }
      }
    }
  }
}
```

最后，YAML 的配置如下。Log4j 支持 `.yaml` 和 `.yml` 文件扩展名，这两种都是 YAML 文件常用的接受文件类型。

```yaml
Configuration:
  status: warn
  appenders:
    Console:
      name: STDOUT
      target: SYSTEM_OUT
      PatternLayout:
        Pattern: "%m%n"
  Loggers:
    logger:
      -
        name: com.wiley.realworldjava
        level: info
        additivity: false
        AppenderRef:
          ref: STDOUT
    Root:
      level: error
      AppenderRef:
        ref: STDOUT
```



JSON 和 YAML 示例使用了与 XML 示例相同的概念。唯一的区别是语法。任何一种格式都可以作为配置。你可以选择你或你的团队偏好的任何一种。

## 设置日志目标

到目前为止，Log4j 示例一直使用控制台 appender 将所有输出记录到系统控制台。还有其他的 appender，最常见的包括以下：

- `Console`：根据配置写入 `System.out` 或 `System.err`。
- `File`：写入文件。
- `RollingFile`：写入一个具有文件轮转功能的文件。
- `RollingRandomAccessFile`：写入一个具有文件轮转和缓冲功能的文件。
- **以及许多更多：** Log4j 包含了超过 25 种 appender。

```json
{
   "configuration": {
      "status": "warn",
      "appenders": {
         "RollingFile": {
            "name":"FILE",
            "fileName":"java-log.log",
            "filePattern":"java-log-%d{yyyy-MM-dd}-%i.log.gz",
            "PatternLayout": {
               "pattern":"%m%n"
            },
            "Policies": {
               "TimeBasedTriggeringPolicy" : {},
               "SizeBasedTriggeringPolicy": {
                  "size":"1 MB"
               }
            },
           "DefaultRolloverStrategy": {
             "max":"3"
           }
       }
    },
    "loggers": {
      "root": {
        "level": "error",
        "AppenderRef": {
          "ref": "FILE"
        }
      }
    }
  }
}
```

最后，这里是 YAML 版本：

```yaml
Configuration:
   status: warn
   appenders:
      RollingFile:
        - name: FILE
          fileName: $java-log.log
          filePattern: java-log-%d{yyyy-MM-dd}-%i.log.gz
          PatternLayout:
             pattern: "%m%n"
          Policies:
             TimeBasedTriggeringPolicy:
             SizeBasedTriggeringPolicy:
               size: 1 MB
           DefaultRollOverStrategy:
             max: 3
   Loggers:
      Root:
         level: error
         AppenderRef:
           ref: FILE
```

## 选择日志输出格式

本节中的许多示例都使用了模式 `%m%n`，它仅表示消息和换行符。在实际日志中，这通常是不够的；你可能希望获得更细粒度的控制。首先为你的日志输出选择一种布局。常见的布局包括：

- `CSV`：逗号分隔值，用于自动化解析或 Excel 分析
- `JSON`：Java 标准对象表示法，通常用于自动化解析
- `Pattern`：默认使用的文本格式
- `XML`：可扩展标记语言，通常用于自动化解析
- `YAML`：另一种标记语言，通常用于自动化解析

日志可以被读取到其他系统或存储以便稍后手动读取。如果你将日志摄入另一个系统，请选择易于消费系统读取的布局。如果你是自己读取，`CSV` 或 `Pattern` 布局最佳。

`Pattern` 布局有许多特殊的格式字符。以下是文档中常用的一个示例：

```
%d %p %c{1.} [%t] %m%n
```

以下是每个部分的含义：

- `%d`：使用默认日期格式的日期。
- `%p`：日志级别（例如，`INFO`）。
- `%c{1.}`– 显示多少内容的完全限定类名。括号中的部分提供了期望的格式。在此示例中，`%c` 表示类名，`{1.}` 表示显示一个完全展开的项，即类名本身以及包名中每个部分的首字母，结果为 `c.w.r.l.l.LoggingWithPropertiesConfig`。
- `[%t]`：大括号中的方法名。
- `%m`：日志消息。
- `%n`：换行符。

## 惰性日志

Log4j 的惰性日志与 Java Util Logging 类似。你使用 lambda 表达式来组合日志消息。只有当日志级别需要记录消息时，lambda 才会被执行：

```
public static void main(String[] args) {
   LOGGER.error(() -> generateMessage());
}

private static String generateMessage() {
   return "This is an expensive message";
}
```

## 使用 SLF4J

SLF4J 代表 Simple Logging Façade for Java（Java 简单门面）。你已经看到每个日志框架在你的 Java 代码中需要不同的 API 调用。这使得切换日志库变得困难。SLF4J 来救你了！SLF4J 旨在作为一个包装器，以便你可以更轻松地切换。

前往 Maven Central 的 [`https://mvnrepository.com/artifact/org.slf4j/slf4j-api`](https://mvnrepository.com/artifact/org.slf4j/slf4j-api) 并为你的构建工具查找最新版本号。表 5.7 显示了依赖关系，使用了本文编写时的最新版本号。

| 工具 | 语法 |
| --- | --- |
| Maven |  |

```
<dependency>
    <groupId>org.slf4j</groupId>
    <artifactId>slf4j-api</artifactId>
    <version>2.0.12</version>
</dependency>
```

 |
| Gradle (Groovy) |  |

```
implementation group: 'org.slf4j',
    name: 'slf4j-api', version: '2.0.12'
```

 |
| Gradle (Kotlin) |  |

```
implementation("org.slf4j:slf4j-api:2.0.12")
```

 |

**表 5.7**：指定 SLF4J 为依赖项

在接下来的章节，我们将介绍使用 SLF4J 的基础知识以及如何配置它使用不同的底层日志框架。

### 省略日志框架

在下面的示例中，唯一指定的依赖是 `slf4j-api`。这足够编译，但无法进行实际日志记录：

```
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class UnderlyingImplementation {
   private static Logger LOGGER = LoggerFactory.getLogger(UnderlyingImplementation.class);

   public static void main(String[] args) {
      LOGGER.info("just to know");
   }
}
```

然而，运行此代码会产生：

```
[main] ERROR com.wiley.realworldjava.logging.SLF4JBinder - No SLF4J providers were found.
```

由于 SLF4J 不知道使用哪个日志框架，它默认不操作。要修复这个问题，必须指定一个提供者。

### 指定 SLF4J 为 Simple

`slf4j-simple` 是 SLF4J 的默认日志实现。将 `slf4j-simple` 作为依赖重新运行现在得到了所需的输出：

```
[main] ERROR com.wiley.realworldjava.logging.SLF4JSimple
   - just to let you know
```

通常会将 SLF4J 与其他日志框架而不是 `slf4j-simple`，正如你将在后面的章节中看到的。在此之前，让我们涵盖如何使用 SLF4J 本身。

### 比较日志级别

SLF4J 有五个日志级别。表 5.9 显示了日志级别及其用途。你可以看到这些理念与你为止看到的其他日志框架是相同的。你可能会注意到没有 `FATAL` 或 `SEVERE` 的对应物。如果你需要表达 `FATAL` 或 `SEVERE` 级别，请使用 `ERROR`。

| 日志级别 | 用途 |
| --- | --- |
| `ERROR` | 记录严重的错误。 |
| `WARN` | 记录可能变成错误的事件。 |
| `INFO` | 记录信息性事件。 |
| `DEBUG` | 记录调试信息。 |
| `TRACE` | 记录细粒度消息，通常显示应用程序流。 |

**表 5.9**: SLF4J 日志级别

### 格式化

与 Log4j 类似，SLF4J 支持使用 `{}` 语法作为带有逻辑默认格式的占位符。如果你需要 `String.format()` 更细粒度的控制，可以直接调用它。这里都使用了这两种方法：

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class Slf4jWithParameters {
   private static final Logger LOGGER = LoggerFactory
      .getLogger(Slf4jWithParameters.class);

   public static void main(String[] args) {
      LOGGER.error("{}: {} is {}/{}", "Division", 1.5, 3, 2);
      LOGGER.error(String.format("%s: %.1f is %d/%d", "Division", 1.5, 3, 2));
   }
}
```

这两条日志语句的消息消息部分如下：

```
Division: 1.5 is 3/2
```

通常情况下，你应该使用 `{}`，除非你发现它无法满足你的需求，此时再针对那些需要更多控制的特定调用使用 `String.format()`。

### 延迟日志

在 SLF4J 中，延迟日志比 Java Util Logging 或 Log4j 提供了更多控制。你仍然使用 lambda，它只有在日志级别需要记录消息时才会被执行。但是，有独立的方法来指定要记录的消息以及每个日志参数。

```java
public static void main(String[] args) {
   LOGGER.atDebug()
      .setMessage(() -> generateMessage())
      .addArgument(() -> generateParameterToFillInMessage())
      .log();
}

private static String generateMessage() {
   return "This is an expensive message with parameter: {}";
}

private static String generateParameterToFillInMessage() {
   return "This is an expensive parameter";
}
```

这种链式调用的方法被称为流式 API（fluent API）。你链式想要调用的方法，最后调用 `log()` 来表示完成。记住在末尾调用 `log()`，否则将没有任何内容被记录！

通过流式 API，你可以选择对任何开销较大的操作使用 lambda。例如：

```java
LOGGER.atDebug()
   .setMessage("Message with expensive parameter {}")
   .addArgument(() -> generateParameterToFillInMessage())
   .log();
```

由于消息的生成开销不大，因此没有必要对它使用 lambda。任何方法都可以独立地选择是否使用延迟操作。同样，当你有多个参数时，每个 `addArgument()` 调用都拥有相同的相同的延迟操作选择权。

### 传递基础配置

正如我们之前提到的，`slf4j-simple` 并不常用。然而，如果你有简单的需求，可以将 `slf4j-simple` 作为独立的日志框架使用。`SimpleLogger` 类的 Javadoc 中包含了十几个可以配置以控制行为系统属性。以下是最有用的：

- `org.slf4j.simpleLogger.logFile`
- `org.slf4j.simpleLogger.defaultLogLevel`
- `org.slf4j.simpleLogger.dateTimeFormat`
- `org.slf4j.simpleLogger.showShortLogName`

配置 SLF4J 使用具有更高级功能的外部日志框架要常见得多。下一节将展示如何操作。

### 将与其他日志框架配合使用 SLF4J

SLF4J 通过检查类路径中的依赖来选择使用的日志框架作为提供者。这就是为什么添加 `slf4j-simple` 作为依赖会导致即使在没有其他配置的情况下它也会被使用。在旧版本的 SLF4J 中，提供者被称为绑定（bindings），因此你可能在旧版文档中看到这种说法。

为了展示切换是多么简单，我们将创建一个使用 Java Util Logging 作为提供者的示例，然后切换到 Log4j。你需要三个 JAR 文件：

- SLF4J 本身
- 日志框架
- 连接日志框架到 SLF4J 的提供者

每个日志框架都有自己的 SLF4J 提供者依赖。要找到 Java Util Logging 依赖，请访问 Maven Central [`https://mvnrepository.com/artifact/org.slf4j/slf4j-jdk14`](https://mvnrepository.com/artifact/org.slf4j/slf4j-jdk14) 并为你的构建工具查找最新版本号。表 5.10 列出了常用构建工具的提供者依赖，以及本文编写时的最新版本号。注意 `jdk14` 出现在名称中是因为那是 Java Util Logging 引入的时间。即使对于现代版本的 Java，这仍然是制品名称。

| TOOL | SYNTAX |
| --- | --- |
| Maven | ```xml
<dependency>
    <groupId>org.slf4j</groupId>
    <artifactId>slf4j-jdk14</artifactId>
    <version>2.0.12</version>
</dependency>
``` |
| Gradle (Groovy) | ```groovy
implementation group: 'org.slf4j',
    name: 'slf4j-jdk14', version: '2.0.12'
``` |
| Gradle (Kotlin) | ```kotlin
implementation("org.slf4j:slf4j-jdk14:2.0.12")
``` |

**表 5.11**：将 Log4j 作为依赖指定为 SLF4J 提供者

更新 `pom.xml` 后，下一步是为 Log4j 创建日志配置：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="WARN">
   <Appenders>
      <Console name="Console" target="SYSTEM_OUT">
         <PatternLayout pattern="%d [%p] %m%n"/>
      </Console>
   </Appenders>
   <Loggers>
      <Logger name="com.wiley.realworldjava" 
         level="warn" additivity="false">
         <AppenderRef ref="Console"/>
      </Logger>
      <Root level="error">
         <AppenderRef ref="Console"/>
      </Root>
   </Loggers>
</Configuration>
```



此时，项目的结构如图 5.3 所示。

注意现在配置中使用了 Log4j 使用的`warn`，而不是 Java Util Logging 的`WARNING`。关键在于所有的更改都在依赖和配置文件中，而不是 Java 代码中。现在在没有任何更改的情况下运行 Java 代码，输出如下：

```
2024-02-18 12:32:17,719 [ERROR] uh oh
2024-02-18 12:32:17,721 [WARN] be careful
```

你可以看到格式已经发生了变化，日志级别现在是 Log4j 使用的级别。

作为清理，你可以从 Java 文件中删除旧的属性文件和系统属性引用。或者如果你能够来切换，也可以将其保留在那里。切换非常简单；只需将依赖更改你想使用的那个即可！

![Log4J 日志的 Maven 结构截图。它包含了以下相互嵌套的文件夹：Src, main, java, com. wiley, resources 以及外部库的扩展。](img/c05f003.png)

# 图 5.3：Log4J 的 Maven 结构

## 使用 LOGBACK

本章的最后一个日志框架是 Logback。Log4j 和 Logback 都是今天企业中流行的选择。Logback 的设计旨在改进 Log4j，例如提高性能。Logback 实际上原生使用 SLF4J，而不是提供单独的 API。事实上，Logback 的创始人 Ceki Gülcü 也是 SLF4J 的创始人！这意味着你在上一节中学习的所有内容都适用。

要开始使用，你需要`slf4j-api`和两个 Logback 特定的文件。访问 Maven Central 的 [`https://mvnrepository.com/artifact/ch.qos.logback/logback-classic`](https://mvnrepository.com/artifact/ch.qos.logback/logback-classic) 和 [`https://mvnrepository.com/artifact/ch.qos.logback/logback-core`](https://mvnrepository.com/artifact/ch.qos.logback/logback-core)。找到适用于你的构建工具的最新版本号，并将其替换为表 5.12 所示。

| 工具 | 语法 |
| --- | --- |
| Maven |  

```
<dependency>
  <groupId>ch.qos.logback</groupId>
  <artifactId>logback-classic</artifactId>
  <version>1.5.0</version>
</dependency>
```

 |
| Gradle (Groovy) |  

```
implementation group: 'ch.qos.logback',
    name: 'logback-classic', version: '1.5.0'
implementation group: 'ch.qos.logback',
    name: 'logback-core', version: '1.5.0'
```

 |
| Gradle (Kotlin) |  

```
implementation("ch.qos.logback:logback-core:1.5.0")
implementation("ch.qos.logback:logback-classic:1.5.0")
```

 |

# 表 5.12：将 Logback 作为依赖指定

注意，`logback-core`是主要的日志代码。`logback-classic`增加了额外的功能，包括作为 SLF4J 提供者。在使用 Logback 时，你应该始终包含这两个依赖项。由于 Logback 使用 SLF4J API，你可以参考 SLF4J 章节来处理完全相同的内容，例如格式化值。

一个使用 Logback 的简单程序看起来和之前的 SLF4J 示例一样：

```
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class BasicLogging {
   private static final Logger LOGGER = LoggerFactory
     .getLogger(BasicLogging.class);

   public static void main(String[] args) {
      LOGGER.info("just to let you know");
   }
}
```

此示例输出以下内容：

```
13:05:05.034 [main] ERROR com.wiley.realworldjava.logging.log4j
   .BasicLogging – just to let you know
```

输出使用了 Logback 的默认设置。在后续章节中，你将看到更多关于使用 Logback 的细节。

### 比较日志级别

Logback 具有与 SLF4J 相同的日志级别以及两个特殊选项。表 5.13 显示了日志级别及其预期用途。到这时，你应该意识到不同框架之间的日志级别是相似的，这使得很容易理解。

| 日志级别 | 预期用途 |
| --- | --- |
| `ERROR` | 记录最严重的错误。 |
| `WARN` | 记录警告。 |
| `INFO` | 记录信息信息。 |
| `DEBUG` | 记录调试信息。 |
| `TRACE` | 记录细粒度的追踪信息，显示应用流。 |
| `ALL` | 记录所有消息。 |
| `OFF` | 指定不记录日志。 |

# 表 5.13：Logback 日志级别

### 基础配置

与 Log4j 类似，Logback 指定了查找顺序。首先是列表中的：

*   `logback-test.xml`
*   `logback.xml`

Logback 会遍历文件，并在找到后停止。因此，如果`logback-test.xml`在你的`test`文件夹中，它将在测试时加载，而`logback.xml`将在标准运行时加载。最后，如果没有找到配置，Logback 使用默认的`DEBUG`级别日志并输出到控制台。注意与 Log4j 不同，Logback 只支持 XML 配置。在此示例中，使用`logback.xml`文件记录我们的包的`INFO`级别，其他所有内容记录`ERROR`级别并输出到控制台。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE configuration>
<configuration>
   <import class="ch.qos.logback.classic.encoder.PatternLayoutEncoder"/>
   <import class="ch.qos.logback.core.ConsoleAppender"/>
   <appender name="STDOUT" class="ConsoleAppender">
      <encoder class="PatternLayoutEncoder">
         <pattern>%msg%n</pattern>
      </encoder>
   </appender>
   <logger name="com.wiley.realworldjava.logging" level="info"/>
   <root level="error">
      <appender-ref ref="STDOUT"/>
   </root>
</configuration>
```

### 设置日志目的地

之前的示例使用了控制 appender。以下是常见的 appender 类：

*   `ConsoleAppender`: 写入`System.out`（可以更改为`System.err`）。
*   `FileAppender`: 写入文件。
*   `RollingFileAppender`: 带有文件轮的写入文件。
*   **更多**：许多可以记录到数据库或队列。甚至有针对 Gmail 等提供者的电子邮件 appender。

现在你将学习如何使用`RollingFileAppender`类。

每个 appender 都有若干属性来控制行为。请参阅章节末尾以获取完整列表的链接。对于轮转文件，这控制名称、格式、如何处理轮转以及何时清理旧文件。

此示例在一天后（默认）或达到 10 KB 后轮转文件，以先到者为准：

```xml
<configuration>
   <appender name="ROLLING" 
      class="ch.qos.logback.core.rolling.RollingFileAppender">
      <file>java-log.log</file>
      <rollingPolicy 
         class="ch.qos.logback.core.rolling.SizeAndTimeBasedRollingPolicy">
         <fileNamePattern>java-log-%d{yyyy-MM-dd}.%i.gz</fileNamePattern>
         <maxFileSize>10KB</maxFileSize>
         <maxHistory>3</maxHistory>
         <totalSizeCap>2GB</totalSizeCap>
      </rollingPolicy>
      <encoder>
         <pattern>%msg%n</pattern>
      </encoder>
   </appender>
   <root level="DEBUG">
       <appender-ref ref="ROLLING"/>
   </root>
</configuration>
```

与 Log4j 类似，该配置指定了正在记录日志的文件名，以及滚动文件的命名约定。由于`fileNamePattern`以`.gz`结尾，它会被进行压缩。

我们在这里将最大文件大小设置为 10 KB，这比我们为 Log4j 设置的 1 MB 要小。原因是 Logback 每隔 60 秒才会检查一次文件大小是否超过限制，而 Log4j 检查文件大小的频率更高。因此，我们在示例中设置了较小的尺寸，以便你不需要等待很久就能看到文件的滚动。

在运行使用此配置记录了 100 条大语句的程序后，会有两个文件：活动文件和一个归档文件：

```
java-log-2024-02-18.0.gz
java-log.log
```

由于测试时日志密集且运行时间短，这两个文件的大小都超过了配置的 10 KB。

### 选择日志输出格式

本节中的示例使用了`%msg%n`，它仅表示消息和换行符。幸运的是，Logback 支持多种选项。首先，你必须选择想要使用的布局（layout）。以下是常见的布局类：

*   `PatternLayout`: 纯文本格式字符串，如`%msg%n`，用于指定你想包含的内容
*   `HTMLLayout`: 使用模式和 CSS 的 HTML 格式
*   `XMLLayout`: 使用 Log4j XML 格式

或者，你可以创建一个自定义格式。

`PatternLayout`通常是最好的，因为它有很多特殊的格式化字符。以下是文档中常用的一个示例：

```
%d{dd MMM yyyy:HH:mm:ss.SSS} [%method] %level - %msg%n
```

以下是每个部分的含义：

*   `%d`: 日期/时间后跟任何格式符号
*   `[%method]`: 花括号中的方法名
*   `%level`: 日志级别
*   `%msg`: 日志消息
*   `%n`: 换行符

章节末尾引文档中有许多其他选项。例如，你可以记录应用程序运行的毫秒数。

## 日志更多

无论你使用哪种日志框架，有些是你需要考虑的。节涵盖了其中的五个关键点。

### 决定编码标准

在本章中，我们定义的日志都是`private static final`常量。有些人倾向于将日志设置为实例变量。你应该检查你的团队是否有任何规则或约定，并遵循这些规则。

### 为性能进行设计

日志涉及输入/输出（I/O），因此它比计算和其他操作要慢。你要确保日志记录不会减慢你的应用程序！如果你将日志记录到远程源（例如数据库），你将需要更加小心。

首先要考虑的是日志级别。当你首次测试应用程序时，你可能需要更详尽的日志。同样，你可能希望在测试或 QA 环境中记录比在生产环境中更多的日志。毕竟，真实应用程序将有更高的使用量，因此细粒度日志对性能的影响会被放大。

此外，在记录日志时有许多可选设置。过于频繁地滚动日志文件会产生很多文件，使它们难以使用。某些日志框架允许你控制输出是否在内存中缓冲，有些则允许你进行异步记录，以便你的应用程序可以继续执行功能行为。

### 为日志选择语言

在为用户编写应用程序时，你可能会读到关于国际化（i18n）和本地化（l10n）的内容。国际化允许你自定义行为，例如文本是用英语还是西班牙语（或任何其他语言）显示。本地化允许你选择特定区域的行为，例如即使在英文文本中也使用美元或英镑（或其他货币）。相比之下，日志是在一种语言中发生的：即你团队使用的语言。

### 防止日志篡改

日志非常重要，因为它们代表了应用程序中发生情况的记录。某些日志用于解决问题。另一些用于审计活动。在这两种情况下，你都需要它们是准确的。

然而，恶意方可能想要破坏日志。他们可能是想要隐藏自己所做坏事的内部员工。他们也可能是想要损害你公司利益的外部人员。

`log injection`（日志注入）指的是恶意方通过包含你未预料的文本来破坏你的日志。考虑这条日志语句：

```
LOGGER.info("Invalid name: {}", name);
```



如果 `name` 来自用户输入，它可能包含任何内容。这种恶意的示例被称为 `log forging`（日志伪造），是一种渗透技术，黑客向变量中注入特殊字符，向你的日志中添加伪造的数据。

### 聚合与转发日志

公司通常将多个应用程序的日志副本存储在一个处以便分析，例如更容易检测模式、运行查询并提供支持。他们还希望日志发送到特定位置，以便于搜索和监控。被称为转发器（forwarders）的工具类专门为了将本地日志移动到中心位置而存在。

- [`docs.oracle.com/en/java/javase/21/docs/api/java.logging/java/util/logging/FileHandler.html`](https://docs.oracle.com/en/java/javase/21/docs/api/java.logging/java/util/logging/FileHandler.html): 用于配置文件日志
- [`docs.oracle.com/en/java/javase/21/docs/api/java.logging/java/util/logging/SimpleFormatter.html`](https://docs.oracle.com/en/java/javase/21/docs/api/java.logging/java/util/logging/SimpleFormatter.html): 用于自定义日志消息格式
- [`docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Formatter.html`](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Formatter.html): 格式化语法

### Log4j

- [`logging.apache.org/log4j/2.x/javadoc/log4j-api/index.html`](https://logging.apache.org/log4j/2.x/javadoc/log4j-api/index.html): Log4j 文档
- [`logging.apache.org/log4j/2.x/manual/appenders.html`](https://logging.apache.org/log4j/2.x/manual/appenders.html): Appender 的完整文档
- [`logging.apache.org/log4j/2.x/manual/layouts.html`](https://logging.apache.org/log4j/2.x/manual/layouts.html): Layout 的完整文档

### SLF4J

- [`www.SLF4J.org/manual.html`](https://www.slf4j.org/manual.html): SLF4J 文档
- [`www.SLF4J.org/api/org/slf4j/simple/SimpleLogger.html`](https://www.slf4j.org/api/org/slf4j/simple/SimpleLogger.html): 如果想配置 `slf4j-simple` 的系统属性

### Logback

- [`logback.qos.ch/manual`](https://logback.qos.ch/manual): Logback 文档
- [`logback.qos.ch/manual/appenders.html`](https://logback.qos.ch/manual/appenders.html): Appender 的完整文档
- [`logback.qos.ch/manual/layouts.html`](https://logback.qos.ch/manual/layouts.html): Layout 的完整文档

## 总结

- Java Util Logging 是内置于 Java 的。
- Log4j 和 Logback 是直接的日志框架。
- SLF4J 是其他日志框架（如 Java Util Logging、Log4j 和 Logback）的门/封装。
- 日志框架提供了文件配置选项，用于指定日志级别、格式、目的地等。

# 6: 了解 Spring 框架

Spring，我如何如何爱你？让我来数数你的方式。引用伊丽莎白·巴蕾特·勃宁（Elizabeth Barrett Browning）著名的十四行诗完美地捕捉了我们如何喜爱 Spring 框架。Spring 框架诞生于 2003 年，它对 Java 生态系统的意义已就像 Java 本身一样重要。

Spring 非常庞大，全面涵盖需要许多厚头大书。在本章中，我们将介绍你在日常企业生活中上手并运行所需的功能。

Spring 提供了注解，你可以在其中配置 `beans`、`components`、`services` 和 `repositories`——这些都是“Spring 管理的实例”的华丽名称。

在它的发展过程中，Spring 引入了一些重要的改进，所有这些范式目前仍被广泛使用，因此，让我们研究一下它的演变吧。Spring 是围绕着 Spring `bean` 的概念构建的。Bean 仅仅是由 Spring 框架管理的 Java 类实例。

在 Spring 早期，你必须在 XML 文件中配置 beans，告诉 Spring 应该管理哪些类以及哪些属性。然后 Spring 引入了 `Configuration` 类，即通过标记了 `@Configuration` 或其他特定注解的普通 Java 类，它们告诉 Spring 框架这些类配置了应用程序中使用的 Spring bean 实例。

还有一种更简洁的方法，只需通过在你的配置类上添加 `@ComponentScan` 注解来定义 beans，正如我们将看到的那样。

随后 Spring 引入了改变规则的 Spring Boot 框架。大多数框架都有一定的学习曲线，而 Spring Boot 实际上具有负向学习曲线！Spring Boot 提供了“带有偏好的”`starter 依赖`，每个依赖都包含了许多用例所需的所有依赖，包括 Web 应用程序、关系型和 NoSQL 数据库、安全、日志等。你只需要将 starter 依赖添加到你的 Maven POM 或 Gradle 构建文件中，Spring Boot 就会加载支持这些用例所需的所有配置和库。一旦你构建了 Spring Boot 应用程序，它会自动生成一个可自执行的 JAR 包，你只需双击即可启动应用程序，或者调用：

```
java -jar <jar-name>.jar
```

企业正在大量迁移到 Spring Boot，但在我们开始之前，让我们先从一个经典的 Spring 示例开始，可以在那里学习一些基础 Spring 概念，包括`组件扫描`和 DI（依赖注入）。然后我们将跳转到 Spring Boot，看看它是如何极大简化这些。

## 配置 Spring

在本节中，你将通过构建一个基础项目来领略 Spring。首先你将看到一个示例应用程序，然后你会看到如何使用 XML 和 Java 注解方法来配置它。然后你将在组件扫描的 Java 方法的基础上进行构建。

我们的应用程序是一个简单的贷款计算器，你可以输入本金、利率和年限，并获得每月还款额。Spring 提供了注解，你可以在其中配置 `beans`、`components`、`services` 和 `repositories`——这些都是“Spring 管理的实例”的华丽名称。

在本节中，你将通过构建一个基础项目来领略 Spring。首先你将看到一个示例应用程序，然后你会看到如何使用 XML 和 Java 注解方法来配置它。然后你将在组件扫描的 Java 方法的基础上进行构建。

我们的应用程序是一个简单的贷款计算器，你可以输入本金、利率和年限，并获得每月还款额。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="
       http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd">
    <!-- 定义 MortgageCalculatorService bean -->
    <bean id="mortgageCalculatorService"
      class="com.wiley.realworldjava.service.MortgageCalculatorServiceImpl"/>
    <!-- 定义 Main 类的 bean -->
    <bean id="app" class="com.wiley.realworldjava.App">
       <constructor-arg ref="mortgageCalculatorService"/>
    </bean>
</beans>
```

此 XML 引用了两个 bean（记住，`bean` 是 Spring 对 Spring 管理的 Java 类的术语）。第 9 行引用了上一节中定义的 `MortgageCalculatorServiceImpl`。第 13 行引用了名为 `App` 的类，我们很快就会介绍它。这两个类的 `id` 属性就像你之后可以引用的变量名。例如，第 14 行使用 `ref` 来引用这样一个 `id`。

Spring 暴露了一个 `ApplicationContext` 类实例，它包含了对所有 bean 的引用，以及其他重要的 Spring 信息，例如 `active profile`（激活配置），我们很快就会介绍它。

要初始化 `ApplicationContext` 实例并告诉它使用该 xml 文件，你需要调用：

```java
ApplicationContext context
= new ClassPathXmlApplicationContext("applicationContext.xml");
```

我们定义了一个 `App` 类来初始化上下文并启动进程。

```java
public class App {
    private final MortgageCalculatorService calculatorService;

    public App(MortgageCalculatorService calculatorService) {
       this.calculatorService = calculatorService;
    }

    public static void main(String[] args) {
       ApplicationContext context
          = new ClassPathXmlApplicationContext("applicationContext.xml");
       // 通过 applicationContext.xml 中指定的 id 访问 bean
       App app = (App) context.getBean("app");
       // 或者，你也可以通过类类型来访问它
       //    App app = context.getBean(App.class);
       double principal = 250_000;
       double annualInterestRate = 6.5;
       int termInYears = 30;
       double payment = app.calculatorService.payment(principal,
          annualInterestRate, termInYears);
       // 显示结果，保留 2 位小数和千分位分隔符
       System.out.printf("Monthly Payment: $%,.2f%n", payment);
    }
}
```

第 16 行和 17 行创建了一个你可以使用的 `ApplicationContext`。第 19 行和 20 行显示你可以通过名称或类型查找 bean。

### 使用 Java 配置

最近，Spring 引入了一种使用 Java 类定义 bean 的方法。与其使用 XML 文件，你可以在类上使用 `@Configuration` 注解，并使用 `@Bean` 定义方法。

```java
@Configuration
public class AppConfig {
    @Bean
    public MortgageCalculatorService mortgageCalculatorService() {
        return new MortgageCalculatorServiceImpl();
    }

    @Bean
    public App app(MortgageCalculatorService mortgageCalculatorService) {
        return new App(mortgageCalculatorService);
    }
}
```

注意第 19 行，我们如何从 `ApplicationContext` 获取 `App` 实例。尽管 `App` 的构造函数需要一个 `MortgageCalculatorService` 实例，但 Spring 会通过注入提供该实例。或者，我们可以移除构造函数参数，并在 `calculatorService` 上使用 `@Autowired` 注解。使用那种方法，Spring 会自动注入 bean：

```java
@Autowired
private final MortgageCalculatorService calculatorService;
```

是否获得相同的实例取决于其作用范围（scope）。然而，构造器注入允许你将字段声明为 `final`。

此示例的完成代码位于 Git 分支 `component-scan`。由于我们的应用程序是一个简单的服务，因此我们将为 `MortgageCalculatorServiceImpl` 类添加 `@Service` 注解，以指示我们的计算器正在执行服务。我们还为 `App` 标记了 `@Component` 注解，告诉 Spring 我们希望以 bean 的形式访问此类。

现在，我们可以从 `AppConfig` 类中移除 bean 声明，只需添加要扫描的包：

```
6: @Configuration
7: @ComponentScan(basePackages = "com.wiley.realworldjava")
8: public class AppConfig {
9: }
```

要使用这种方法，请将 `App` 类中第 17 和 18 行的 `ApplicationContext` 初始化器替换为以下内容，并传入配置类名：

```
ApplicationContext context = 
   new AnnotationConfigApplicationContext(AppConfig.class);
```

甚至可以完全删除 `Configuration` 类，只需将要扫描的包名传递给 `ApplicationContext` 初始化器：

```
ApplicationContext context
       = new AnnotationConfigApplicationContext("com.wiley.realworldjava");
```

## 使用属性自定义 Spring 应用程序

你知道，在代码中硬编码配置参数通常被认为是一种坏实践，以免在每次更改配置时都必须修改代码。

Spring 允许你在资源文件中定义属性，并在特定 profile 的文件中引入特定环境的修改。在标准的 Spring 应用中，这需要一些简单的脚手架。在 Spring Boot 应用中，所有脚手架工作都在后台完成，因此你不需要做任何事情。在接下来的章节中，你将看到如何注入属性，以及如何配置环境特定的属性。

要查看本节的完成品，请查看仓库中名为 `profiles` 的分支。

### 注入属性

要将属性值注入到变量中，请在 `src/main/resources` 文件夹中创建一个名为 `application.properties` 的文件，这是 Spring 期望定义资源文件的默认位置。该文件包含应用程序特定的属性，以键值对的形式表示。你也可以使用 YAML 文件，这是一种等效的方法，只是使用了 YAML，但在本书中使用属性文件。有关 YAML 的更多信息，请参阅本书的附录。

对于抵押贷款计算器，让我们添加以下属性：

```
default.interestRate=3.5
preferred.mortgage.holder=ABC Mortgage, Inc.
country=United States
```

在 `@Configuration` 类（或任何 Spring 管理的类）中，在类名上方添加 `@PropertySource` 注解，并传入属性文件名。例如：

```
@Configuration
@PropertySource("classpath:application.properties")
public class AppConfig {
```



现在，`application.properties` 中指定的所有属性对你的应用程序可用。

有几种方法可以将这些值注入到 Java 应用程序中。一种方法是在 Java 代码中的变量上使用 `@Value` 注解，并传入带有属性名的占位符（格式为 `"${property.name}"`）。Spring 将自动将 `application.properties` 中指定的该名称属性注入到该变量中。

例如，要将之前 `application.properties` 中的 `default.interestRate` 注入到名为 `defaultInterestRate` 的 `double` 类型变量中，你可以在任何 Spring 管理的类中如下声明该变量：

```
@Value("${default.interestRate}")
private double defaultInterestRate;
```

该变量可以是任何 Java 类型，例如 `String`、`int`、`Integer`、`double` 等。只要值对于该数据类型是合法的，Spring 将为你完成从 `String` 到类型的转换。（换句话说，不要尝试为 `double` 类型的变量分配字母值！）

或者，你也可以将该占位符作为构造函数参数。例如，让我们如下所示包含默认利率占位符：

```java
public MortgageCalculatorServiceImpl(
   @Value("${default.interestRate}")
   double defaultInterestRate) {
   this.defaultInterestRate = defaultInterestRate;
}
```

## 使用 Spring Profiles 配置环境特定属性

在上一节中，我们说硬编码值是坏实践。那么，你如何注入环境特定的值呢，即随环境变化而变化的值？为了实现这一点，Spring 有 profiles 的概念，它允许你创建环境特定的变量。

例如，假设你的应用程序根据环境具有不同的数据库属性，或调用不同的 REST 端点 URL。你可以创建环境特定的属性文件。例如，为 dev 环境创建一个属性文件，命名为 `application-dev.properties`。为 prod 创建另一个，命名为 `application-prod.properties`。将所有这些属性保留在 resources 文件夹中。然后在你的 `@Configuration` 类中添加 `@PropertySource` 注解，指定 profile 占位符，如下：

```
@Configuration
@PropertySource("classpath:application.properties")
@PropertySource(
   "classpath:application-${spring.profiles.active}.properties")
public class AppConfig {
```

现在我们指定了两个属性，因此 Spring 将使用来自 `application.properties` 文件和环境特定属性文件的属性。如果存在冲突，环境特定的将胜出。

要告诉 Spring 使用哪个 profile，你可以在 IntelliJ 中直接设置 profile，如图 6.2 所示。

![名为“Change active spring profiles”的对话框覆盖了窗口屏幕。此框包含 profiles 栏，其中文本类型被高亮。下方是 Cancel 和 apply 选项。](img/c06f002.png)

**图 6.2**: 在 IntelliJ 中设置 profile

或者，你可以通过编辑启动配置来设置 profile 名称，如图 6.3 所示。

![运行和调试配置窗口的截图。侧边栏包含 application 和 spring 文件夹。右侧显示了 run-on、name 和环境变量。](img/c06f003.png)

**图 6.3**: 在启动配置中设置 profile

你也可以直接从命令行传递 profile 名称，如下：

```
-Dspring.profiles.active=dev
```

对于我们目前的用途，我们将活动 profile 设置为 `dev`，导致 Spring 使用 `application-dev.properties` 中的属性，此外还包含 `application.properties` 中的默认属性。

运行该代码，你会看到此输出：

```
Profiles:[dev]
Preferred mortgage holder:ABC Mortgage, Inc.
Company home:United States
Loading Dev datasource
Monthly Payment: $1122.61
```

现在将活动 profile 改为 `prod` 并再次运行。

```
Profiles:[prod]
Preferred mortgage holder:ABC Mortgage, Inc.
Company home:UK
Loading Prod datasource
Monthly Payment: $1531.17
```

区别在于在 dev 中，我们没有在 `application-dev.properties` 中指定默认利率，因此程序获取了 `application.properties` 中的默认值。

```
default.interestRate=3.5
```

然而，对于 prod profile，程序看到了 `application-prod.properties` 中被覆盖的属性，因此在计算中使用了该值。

```
default.interestRate=6.2
```

注意当存在冲突时，环境特定的版本胜出。

## 使用 Spring Boot 加速开发

Spring Boot 是一个非常方便的框架，它消除了 Spring 应用所需的许多脚手架和设置。

它使用了“启动器依赖”（starter-dependencies）的概念，即 Maven/Gradle 物清单（BOM）依赖，这意味着它们会为其特定的用例引入所有所需的依赖。你可以通过查看名称大致判断该启动器的用途，例如，`spring-boot-starter-web` 用于构建 Spring MVC Web 应用程序，而 `spring-starter-security` 用于通过身份验证和授权为你的应用程序提供安全保护。

一图胜于千言，所以让我们把我们的房贷贷款计算器提升一个层级：暴露一个 Web 层并添加一些 Web URL。

## 使用 Spring Initializr 初始化 Spring Boot 项目

Spring 提供了一个名为 Initializr 的网站（注意它们的拼写方式！），你可以在那里选择依赖项，并让 Spring 生成完整的应用程序骨架，其中所有内容都各就其位，包括一个包含所有所需属性和依赖的 Maven `POM` 或 Gradle 构建文件。Initializr 同样集成到了主流的 IDE 中，我们将看到如何使用 Initializr 网站以及 IDE 的集成功能。

若要使用 Initializr 网站，请从你喜爱的浏览器访问 [`https://start.spring.io`](https://start.spring.io/)，选择你的构建工具（在本例中为 Maven）、语言（Java）、Spring Boot 版本（在本文期间，3.3.3 是最新的稳定版本；请注意企业倾向于避免里程碑发布版本，因为它们仍在开发中），并如图 6.4 所示输入你的项目元数据（Group、Artifact、Name、Description 等）。

![spring initializer 窗口的截图。它包含了以下标题的选选项：Project（项目）、spring boot 和 language（语言）。下方提供了 Generate（生成）、explore（探索）和 share（共享）选项。](img/c06f004.png)

**图 6.4**：在 Spring Initializr 中配置你的项目

接下来，在屏幕右侧点击“Add dependencies”（添加依赖）按钮，选择你想要包含在项目中的所有依赖项。在本例中，我们将仅为 Web 应用程序使用 Spring Web。最后，点击“Generate”（生成）按钮，这将产生一个 zip 文件（`mtgcalc.zip`），你可以解压并在 IDE 中打开。

## 使用 IntelliJ Initializr 集成

你也可以使用 IDE 为你完成所有工作，这是我们首选的方法。本节的完整代码位于 `spring-boot` 分支中。

让我们开始一个项目，查看如何使用 IntelliJ IDEA 内置的 Initializr 支持来生成 Spring Boot 项目。要生成新的 Spring Boot 项目，选择 File ➪ New ➪ Project 并选择 Spring Boot。（旧版本的 IntelliJ 显示的是 Spring Initializr 而不是 Spring Boot，所以如果你使用的是旧版本，可能仍然看到它。）

这将打开一个与 Initializr 网站类似的界面，你可以在那里输入你的项目详情（参见图 6.5）。

![新项目窗口的截图。侧边栏选中了 spring boot。右侧显示了相关信息，包括 server URL、location、name、language、type、group、artifact、package name、save 和 packing。下方提供了 Next（下一步）和 cancel（取消）按钮。](img/c06f005.png)

**图 6.5**：在 IntelliJ 中配置你的 Spring Boot 项目

点击 Next 选择你所有所需的依赖项。在本例中，选择 Spring Web，如图 6.6 所示。

最后，点击 Create（创建）生成模块。你可以在 IDE 中看到新模块。打开 `pom.xml` 文件，你会发现 Spring Boot 生成了对 Spring Boot 父项目的引用。

```
<parent>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-parent</artifactId>
   <version>3.3.3</version>
   <relativePath/> <!-- 从仓库查找父项目 -->
</parent>
```

`spring-boot-starter-parent` 是所有 Spring Boot 项目的父项目，它为所有依赖和插件提供了默认版本，位于 `dependencyManagement` 和 `pluginManagement` 标签下，并为每个支持的项目提供了引用。Maven 会查看这些 `Management` 引用，并仅引入在你的 `POM` 中被显式引用的项。当你在 `dependencies` 或 `plugins` 部分中指定依赖项时，Spring 会从父 POM 的 `management` 部分拉取版本，因此你不需要指定版本。这样，当你将 `POM` 升级到最新版本时，你的项目依赖也将自动升级。如果你在自己的 `POM` 中显式指定版本，它将覆盖父项目中的版本。

![新模块窗口的截图。spring boot 输入了 3.3.3。依赖项有一个搜索框，在其中搜索了 web。在 web 内部选中了 spring web 选项。右侧显示了详情和添加的依赖。下方提供了 Previous（上一个）、create（创建）和 cancel（取消）选项。](img/c06f006.png)

**图 6.6**：在 IntelliJ 中选择依赖

`POM` 还包含对 `spring-boot-starter-web`（因为你选择了 Spring Web）以及始终包含的 `spring-boot-starter-test` 的引用。

通过以下命令启动应用程序：

```
java -jar target/mtgcalc-0.0.1-SNAPSHOT.jar
```

如果默认服务器端口 8080 未被释放，你将收到错误。让我们通过在 `application.properties` 中输入 `server.port=8081` 将服务器端口从默认的 8080 改为 8081，如图 6.7 所示。如果你在 IntelliJ 中进行此操作，自动补全将显示 8080 的默认值。你只需在该处输入 `8081`，即可将其设置为我们的 Web 应用监听的端口。如果 8081 未空闲，请选择一个空闲端口。

重新构建并启动应用程序，你应该能看到如图 6.8 所示的输出。注意应用程序名称在所有日志输出中是如何显示的。还要观察显示的端口，以及我们的“Hello, Mortgage Calculator”消息。

![一张截图显示了一个 Spring Boot 应用，重点关注定义服务器端口设置。 ](img/c06f007.png)

**图 6.7**: 指定服务器端口

![一个窗口截图显示了 Spring Boot 启动的输出。某些文本使用矩形框高亮。 ](img/c06f008.png)

**图 6.8**: Spring Boot 启动输出

我们之前看到 Spring 允许你指定一个激活配置（profile），可以使用它来创建特定环境的属性。例如，要指定当前为 dev，请传入 JVM 参数 `--Dspring.profiles.active=dev`。这告诉 Spring 在默认的 `application.properties` 之外，还要在 `application-dev.properties` 中查找属性。如果存在重叠属性，dev 将优先。

## 使用 Spring MVC

让我们为项目添加一些包。我们将执行脏活累活的计算类保留在 `service` 包下。Web 应用端点定义在 Spring `Controller` 类中（稍后定义），因此我们将将其放在 `controller` 包中。所以，让我们创建 `com.wiley.realworldjava.mtgcalc.service` 和 `com.wiley.realworldjava.mtgcalc.controller` 包。你可以简单地将原始项目中的两个类 `MortgageCalculatorService` 和 `MortgageCalculatorServiceImpl` 复制粘贴到新的 Spring Boot `mtgcalc` 项目中。要添加 Web 功能，我们需要添加控制器类。这是一个带有 `@RestController` 注解的类。在 `com.wiley.realworldjava.mtgcalc.controller` 包中创建 `MortgageController` 类。为该类添加方法并用 `@GetRequest("/my-endpoint")` 注解它们；只需将 `/my-endpoint` 重命名为你希望在调用该方法时引用的 URL 端点。让我们通过实现一个简单的“Hello, World”端点来尝试：

```
@RestController
public class MortgageController {
   @GetMapping("/hello")
   public String hello(){
      return LocalDateTime.now() + ": Hello, World ";
   }
}
```

重新构建并启动，然后在浏览器中访问 URL：

```
http://localhost:8081/hello
```

你应该在浏览器中看到日期、时间和快乐的“Hello, World”！现在我们处于良好的位置，来实现实际的贷款计算。让我们使用*构造函数注入*将 `MortgageCalculator` 自动注入到控制器类中。当 Spring 看到像 `MortgageCalculatorService` 这样的 *bean* 类被用作构造函数参数时，它会自动创建该 bean 的实例并将其注入到构造函数。

```
@RestController
public class MortgageController {
   private final MortgageCalculatorService mortgageCalculator;

   public MortgageController(MortgageCalculatorService mortgageCalculator) {
      this.mortgageCalculator = mortgageCalculator;
   }
```

为了告诉 Spring `MortgageCalculator` 是一个 bean，请在你的实现上使用 `@Component`、`@Service` 等注解之一，正如我们在之前的“使用组件扫描”部分讨论的那样。由于这是一个服务类，我们将使用 `@Service`。

```
@Service
public class MortgageCalculatorServiceImpl 
implements MortgageCalculatorService {
```

为了让我们的计算器有用，我们需要为用户提供一种传递所需参数的方法，在这种情况下是本金、年限和利率。我们可以通过在 `MortgageController` 中对方法参数使用 `@RequestParam` 注解来实现：

```
@GetMapping("payment")public String calculateMonthlyPayment(
   @RequestParam double principal,
   @RequestParam int years,
   @RequestParam double interest) {
   double payment = mortgageCalculator.payment(principal, interest, years);
```



`String rval = String.format("Principal:%,.2f<br>Interest: %.2f<br>" + "Years: %d<br>Monthly Payment:%.2f", principal, interest, years, payment);`

`return rval;`

注意我们在输出中插入了 `<br>`。这是在输出行之间插入换行符的 HTML 语法。现在重新构建。运行并在浏览器中调用以下：

```
http://localhost:8081/payment?principal=100000&years=30&interest=6.5
```

我们的查询字符串参数名称与方法变量名匹配，因此 Spring MVC 将它们进行映射并愉快地返回格式化结果。

```
Principal:100,000.00
Interest: 6.50
Years: 30
Monthly Payment:632.07
```

注意，我们目前为止实现的调用都是 GET 请求，这是你从浏览器调用 URL 时的默认 HTTP 方法。如果你想为 POST 或 PUT 等 HTTP 方法创建端点，请使用相应的注解 `@PostMapping` 或 `@PutMapping`。所有可能的 HTTP 方法都有对应的注解，包括 GET、POST、PUT、PATCH、DELETE 等用于设计良好的面向资源的架构（ROA）RESTful Web 服务。根据 ROA 原则，记录被称为*资源*。GET 请求查询资源或资源列表。POST 请求创建资源。PUT 用于替换整个资源，PATCH 更新资源字段。DELETE 删除资源。要了解更多关于 RESTful 服务的信息，请参阅“进一步参考”部分。

```
@GetMapping("/payment")
public ResponseEntity<String> calculateMonthlyPayment(
   @RequestParam double principal,
   @RequestParam int years, @RequestParam double interest) {
   double payment = mortgageCalculator.payment(principal, interest, years);
   String rval = String.format("Principal:%,.2f<br>Interest: %.2f<br>" +
      "Years: %d<br>Monthly Payment:%.2f", principal, interest, years, payment);
   HttpHeaders headers = new HttpHeaders();
   headers.add("Request time", "Call for payment at " + LocalDateTime.now());
   return new ResponseEntity<>(rval, headers, HttpStatus.OK); }
```

如果你从命令行执行该调用，你将看到响应头。使用 `curl -i`（使用 `curl` 调用 URL 并用 `-i` 显示响应体和头），如图 6.9 所示所示![带有 curl 命令的矩形框。](img/c06f009.png)

**图 6.9**: 获取响应和头部的 `curl` 命令

你应该能看到响应：

```
HTTP/1.1 200
Request time: Call for payment at 2024-08-25T15:45:59.834954700
Content-Type: text/plain;charset=UTF-8
Content-Length: 77
Date: Sun, 25 Aug 2024 19:46:03 GMT
Principal:100,000.00<br>Interest: 6.70<br>Years: 30
   <br>Monthly Payment:645.28
```

这就是执行 GET 请求的方法。现在，传统的资源导向架构强制使用 GET 请求进行只读数据访问请求，并使用 POST 请求来更新数据。PUT 请求用于更改数据但具有`等幂性`（idempotent）的操作。等幂请求是指在初始请求后不会更改任何底层数据的调用。

对于读取请求，我们希望使用 GET；然而，GET 请求通常不接受正体，而且对于 URL 查询字符串中的数据量是有限制的。因此，对于查询复杂的负载（例如任意大小的数据列表），企业通常即使是只读查询也会使用 POST 请求。

POST 请求支持复杂的正体，例如 JSON 对象。让我们学习一些 Spring 的魔术，看看 Spring 如何自动将 JSON 转换为 Java 对象，反之亦然。

我们将创建一个 POST 请求端点，该端点将接受一个由任意数量的贷款计算组成的 JSON 列表。然后，我们将 JSON 对象作为请求体提供给该端点。

首先，让我们创建一个名为 `com.wiley.realworld.java.mtgcalc.domain` 的新包，并为其添加三个新类：`User`、`Mortgage` 和 `Response`：

```
public class User {
  private String name;
  private String location;
  // getters and setters go here
}

public class Mortgage {
  private double principal;
  private int years;
  private double interest;
  private User user;
  private double payment; // 结果每月还额
  // getters and setters go here
}

public class Response {
  private final List<Mortgage> mortgages;
  private final LocalDateTime now; 
  public Response(List<Mortgage> mortgages, LocalDateTime now) {
    this.mortgages = mortgages;
    this.now = now;
  }
  // getters go here
}
```

这是控制器类：

```
28: @PostMapping("/payment")
29: public ResponseEntity<Response> calculateMonthlyPayment(
30:    // Spring 将 JSON 列表转换为 Java List 
31:    @RequestBody List<Mortgage> mortgages) {
32:    
33:    for(Mortgage mortgage:mortgages) {
34:       double principal = mortgage.getPrincipal();
35:       double rate = mortgage.getInterest();
36:       int years = mortgage.getYears();
37:       double payment = mortgageCalculator.payment(
38:          principal, rate, years);
39:       mortgage.setPayment(payment);
40:    }
41:    HttpHeaders headers = new HttpHeaders();
42:    headers.add("Total items", String.valueOf(mortgages.size()));
43:    return new ResponseEntity<>(new Response(mortgages, 
44:       LocalDateTime.now()), headers, HttpStatus.OK);
45: }
```

第 28 行将此方法声明为 POST 请求并将其绑定到端点 `/payment`。注意这与我们的 GET 端点是同一个 URL。当你作为 POST 调用调用 `/payment` 时，它将调用新方法；但当你作为 GET 调用调用相同的 URL 时，它将调用原始方法。

在第 31 行中，注解 `@RequestBody` 通知 Spring 将 JSON 负载转换为参数类型，在这种情况下是 `Mortgage` 对象的 Java `List`。请参阅关于 JSON 的附录以了解更多关于底层如何从 JSON 反序列化为 Java 对象的信息。

第 33 到 40 行遍历列表并对每个元素执行贷款计算。第 41 行创建了一个 `HttpHeaders`。第 43 行创建了一个新的 `Response`，它包含 `headers` 和 `HttpStatus.OK`。

然后，通过在类上添加 `@ControllerAdvice` 注解并为异常实现方法来创建全局异常处理器；在这种情况下，我们只实现了一个名为 `handleException` 的方法。该方法必须带有 `@ExceptionHandler` 注解，并且必须接受要处理的异常作为唯一的方法参数。

```
@ControllerAdvice
public class GlobalExceptionHandler {
   @ExceptionHandler
   public ResponseEntity<ErrorResponse> handleException(
      MortgageException exception) {
   ErrorResponse errorResponse =
      ErrorResponse.builder(exception, HttpStatusCode.valueOf(400),
      exception.getMessage()).build();
      return new ResponseEntity<>(errorResponse, HttpStatus.BAD_REQUEST);
  }
}
```

最后，修改服务实现以抛出策略性异常：

```
@Override
public double payment(double principal,
                      double annualInterestRate, int termInYears) {
  if(termInYears <=0) {
    throw new MortgageException("Years must be positive");
  }
  double monthlyInterestRate = annualInterestRate / 12 / 100;
  int numberOfPayments = termInYears * 12;
  // mortgage formula: P * R * [(1+R)^N] / [(1+R)^N - 1]
  return principal * (monthlyInterestRate
     * Math.pow(1 + monthlyInterestRate, numberOfPayments))
     / (Math.pow(1 + monthlyInterestRate, numberOfPayments) - 1);
}
```

重新构建并启动代码，像以前一样从浏览器调用 GET 请求，一切运行正常。但现在通过以下调用将 `years` 改为 `-30`：

```
http://localhost:8081/mtg/payment?principal=100000&years=-30&interest=6.7
```

这返回了如图 6.10 所示的响应。

![程序窗口截图显示了返回响应。程序中的标题、状态和正文详情被高亮显示。](img/c06f010.png)

图 6.10: 来自 ControllerAdvice 的响应

## 使用 ACTUATOR 检查你的应用程序

Actuator 是你在基于 Spring 的应用程序中想要使用的有用插件。它暴露了一些标准的端点，可以提供有关应用程序的丰富信息。这些端点被 Prometheus、Grafana 和其他可观测应用工具使用。（我们在第 12 章“监控你的应用程序：Java 生态中的可观测性”中涵盖了可观测性。）本节的代码位于 `actuator` 分支。

以下是你看到的一些常用端点：

* `/actuator`：显示所有 actuator 端点的列表。
* `/actuator/health`：此有用端点以 JSON 响应的形式提供应用程序健康信息，属性 `{"status":"ok"}`。你可以直接调用此端点，但它的主要价值是供监控工具检查应用程序的健康状况。
* `/actuator/info`：显示标准和定制（自定义）应用程序信息。
* `/actuator/metrics`：显示当前应用程序指标名称列表。
* `/actuator/metrics/<metric name>`：显示命名指标的当前值。例如，`http://localhost:8081/actuator/metrics/disk.free` 返回可用磁盘空间。
* `/actuator/loggers`：显示应用程序中所有日志器的配置。
* `/actuator/env`：暴露 Spring 环境中的属性。
* `/actuator/beans`：显示应用程序中每个 Spring Bean 的列表。

例如，对 `http://localhost:8081/actuator` 的 GET 调用返回的响应以如下内容开头：

```
{
   "_links": {
      "self": {
         "href": "http://localhost:8081/actuator",
         "templated": false
      },
      "beans": {
         "href": "http://localhost:8081/actuator/beans",
         "templated": false
      },
      "caches-cache": {
         "href": "http://localhost:8081/actuator/caches/{cache}",
         "templated": true
      },
      "caches": {
         "href": "http://localhost:8081/actuator/caches",
         "templated": false
      },
      "health": {
         "href": "http://localhost:8081/actuator/health",
         "templated": false
      },
      "health-path": {
         "href": "http://localhost:8081/actuator/health/{path}",
      },
      "metrics-requiredMetricName": {
         "href": "http://localhost:8081/actuator/metrics/{name}",
         "templated": true
      },
      "metrics": {
         "href": "http://localhost:8081/actuator/metrics",
         "templated": false
   }
}
```

向应用程序添加 Actuator 实际上非常简单。首先，添加 actuator starter。

```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

`actuator/health` 端点默认可用的，但其他端点需要启用。要这样做，在 `application.properties` 中添加以下逗号分隔的端点列表：

```
management.endpoints.web.include=info,metrics
```

要暴露所有端点，提供值 `*`：

```
management.endpoints.web.include=*
```

现在，如果你调用 `http://localhost:8081/actuator/metrics`，它将返回支持的指标列表。替换指标名称以查看该指标的值。例如，调用 `http://localhost:8081/actuator/metrics/jvm.info` 返回关于当前 JVM 的信息：

```
{
   "name": "jvm.info",
   "description": "JVM version",
   "measurements": [
      {
         "statistic": "VALUE",
         "value": 1.0
      }
   ],
   "availableTags": [
      {
         "tag": "vendor",



"values": [

   "Oracle Corporation"

]

},

{

   "tag": "runtime",

   "values": [

      "Java(TM) SE Runtime Environment"

   ]

},

{

   "tag": "version",

   "values": [

      "21.0.1+12-LTS-29"

   ]

}

]

}

```

## 使用 SPRING SECURITY 保护你的应用程序

安全是任何严肃的企业应用程序最重要的非功能性需求之一。Spring 提供了强大的安全支持。首先，我们将介绍术语，然后进入 Spring 代码。

### 学习安全术语

首先让我们熟悉一些术语。

* **窃听者 (Eavesdropper)**：秘密获取网络传输数据的个人或程序。
* **加密 (Encryption)**：对数据进行编码以防止未经授权访问的过程。
   * **对称加密**：发送者和接收者使用相同的密钥进行加密解密。如果密钥被窃听者发现，则存在风险。
   * **非对称加密**：使用公钥加密数据，但只能使用服务器的私钥解密。这确保了窃听者无法解密数据。同样，可以使用私钥加密并使用公钥解密。这样做是为了确保数据确实是由已知发送者发送。
* **证书 (Certificate)**：包含公钥以及颁发证书机构名称等信息的数字文档。
* **证书颁发机构 (Certificate Authority)**：发布和维护证书的信任组织。
* **安全套接层 (SSL)**：一种在互联网上传输加密数据的协议。使用由证书颁发机构颁发的证书。
* **传输层安全 (TLS)**：SSL 的下一代、更安全的版本。
* **超文本传输协议 (HTTP)**：一种用于 Web 客户端和 Web 服务器之间传输数据的开放协议。默认使用 80 端口，但可以轻松修改。
* **HTTPS**：使用 SSL 的 HTTP 安全版本。默认使用 443 端口。
* **身份验证 (Authentication)**：验证你的身份。例如，你可以输入用户名和密码，应用程序会以安全的方式检查这些凭据。
* **授权 (Authorization)**：验证通过身份验证的用户是否有权查看其尝试访问的资源。

这些是你在常见的安全对话中会听到的通用安全相关术语。现在，让我们看看 Spring 如何整合这些功能来保护你的应用程序。

### 理解 Spring Security 处理机制

Spring Security 使用 `filters`（更准确地说是“servlet 过滤器”）来处理身份验证和授权。过滤器是小型程序，它们按照预定义的顺序拦截并增强传入的请求或导出的响应。每个过滤器执行其处理，然后将结果传递给过滤器链中的下一个过滤器，直到请求最终到达端点实现。

本节开始使用 `spring-boot-security-basic` 分支。以下是 Spring MVC 应用中身份验证流程的描述。你可以在图 6.11 中看到此过程的插图。

![工作流图包含以下区块：1. 请求。2. 身份验证过滤器。3. 身份验证管理器。4. 身份验证提供者。5. 用户详情服务。6. 密码编码器。7. 安全上下文持有器。交互使用箭头线表示。](img/c06f011.png)

**图 6.11：Spring Security 过滤器交互**

该过程从用户发起请求时开始。servlet 过滤器拦截请求并开始处理。链中的第一个过滤器是 `AuthenticationFilter`，它从传入的请求中提取登录凭据并将其传递给 `AuthenticationManager`。过滤器产生一个 `Authentication` 令牌并传递给 `AuthenticationManager`。然后，`AuthenticationManager` 将令牌传递给 `AuthenticationProvider`，后者使用 `UserDetailsService` 和 `PasswordEncoder` 接口对其进行验证。如果凭据有效，它将创建一个包含令牌的 `SecurityContext` 并将其存储在 `SecurityContextHolder` 中，随后后续过滤器就可以访问它。应用程序随后可以访问 `Authentication` 令牌来检查授权。

请求处理完成后，Spring Security 会清空 `SecurityContextHolder` 以防止重用。

Spring Security 默认使用`基于会话的身份验证`(session-based authentication)。在该方案中，会话 ID 保留在 cookie 中并随每次请求一起发送，允许服务器检索会话和相关的 `SecurityContext`。通过这种方式，登录将一直有效直到超时或会话结束，因此不需要每个请求都重新登录。

应用程序也可以选择使用`基于令牌的身份验证`(token-based authentication)。在这种情况下，会生成一个包含用户信息的 JWT 令牌，并在每个请求的请求头中传递该令牌。同样，这允许登录在令牌有效期内或会话终止前一直保持有效。

让我们在应用程序中实现基础身份验证 (Basic Authentication)。提醒一下，这需要用户 ID 和密码才能进入我们的端点。通常此类凭据存储在数据库或 LDAP 中。

现在重新构建并启动应用程序，尝试调用该端点。在浏览器中，系统会提示输入凭据。如果你运行此 `curl` 命令，你将看到 401 HTTP 返回码，这意味着未经过授权。

```
curl -X POST -H "Content-Type: application/json" -d @request.json
--fail --silent --show-error  http://localhost:8081/mtg/payment
```

要解决这个问题，我们必须在请求中添加基础身份认证（Basic Authentication）。这要求你在请求的 `Authorization` 标头中传递有效的用户名和密码。在浏览器中，这很简单。你只需要在提示时输入 `user` 和 `password`（这些是我们示例中使用的值）。

对于 `POST` 请求，你需要创建一个由 `user:password` 组成的字符串，然后对这整个字符串进行 Base64 编码。你可以轻松地访问 [`https://www.base64encode.org`](https://www.base64encode.org) 并粘贴 `user:password`，注意不要留下任何多余的字符或空格，然后点击编码按钮。这将返回 `dXNlcjpwYXNzd29yZA==`，这就是进入城堡的钥匙。创建一个名为 `Authorization` 的新标头，并提供值为 `Basic dXNlcjpwYXNzd29yZA==`，如下：

```
Authorization: Basic dXNlcjpwYXNzd29yZA==
Content-Type: application/json
```

在 `curl` 中，你现在可以运行：

```
curl -X POST -H "Content-Type: application/json" 
-H "Authorization: Basic dXNlcjpwYXNzd29yZA==" 
-d @request.json http://localhost:8081/mtg/payment
```

这一次你应该应该得到一个成功的响应了。

# 探索 Spring 项目

本章将让你领略 Spring 提供的功能。表 6.1 列出了一些示例。还有更多示例。如果你正在处理 AI、GraphQL 或几乎任何其他技术，请查看 Spring 是否有相应的项目可以让你的生活变得更轻松！

| 项目 | 描述 |
| --- | --- |
| Spring Framework | Spring 的核心，包括依赖注入、Web 应用、消息传递等。有关 Spring Framework 的更多功能，请参阅第 7 章“使用自动化测试工具测试你的代码”；第 9 章“使用 Java 并发实现应用程序并行”；第 11 章“面向面向的方式编码”。 |
| Spring Batch | 用于批处理应用程序。 |
| Spring Boot | 让你的应用程序快速运行。 |
| Spring Cloud | 支持云和微服务。 |
| Spring Data | 用于处理数据库。 |
| Spring Integration | 支持流行的企业集成模式。 |
| Spring Security | 添加授权和身份验证支持。 |
| Spring WebFlux | 为 Web 和 REST 端点提供响应式能力（基于 Project Reactor）。 |

**表 6.1**：Spring 项目示例

## 进一步参考

* [`http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm`](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
   * Roy Fielding 关于 REST 的原始论文
* [`https://start.spring.io`](https://start.spring.io)
   * Initializr
* [`https://docs.spring.io/spring-framework/reference/index.html`](https://docs.spring.io/spring-framework/reference/index.html)
   * Spring Framework 文档
* [`https://www.base64encode.org`](https://www.base64encode.org)
   * Base 64 编码器
* *RESTful Web Services* (O'Reilly 2007)
* *Spring in Action* (Manning, 2022)

## 总结

在本章中，你学习了许多熟悉 Spring 所需要的知识。Spring 框架非常大，包含了与各种想象得到的框架的集成。你学习了如何使用 XML 和 Java 配置 Bean。然后你学习了如何使用组件扫描（component scan）使代码更简洁。你学习了如何结合 Spring Boot 和 Initializr 使用属性（properties）和配置文件（profiles）。接着你学习了如何处理错误以及处理安全问题。但最重要的是，你发现了 Spring 有很多令人喜爱的地方。还有非常多需要学习的内容，如果你的企业使用了特定功能，你将需要阅读那些功能的文档。

# 7 使用自动化测试工具测试你的代码

我确定你一定思考过这个世纪伟大的哲学问题：如何知道你的代码运行结果符合预期？在编程生涯的早期，你可能尝试通过添加打印语句或日志语句来回答这个问题，以查看代码行为是否符合预期。然后，你可能学会了使用调试器来单步执行代码。在付出了努力之后，你很有信心自己写出了一些可以运行的代码。现在，你只需要一种方法来确保它一直正常运行！

在第 4 章“使用 Maven、Gradle、Jenkins 自动化你的 CI/CD 构建”中，你已经了如何在每次将更改推送到版本控制时运行构建。通过在这些构建中包含自动化测试来实现。

## 理解基础

在本节中，你将学习如何组织测试，以及如何使用 Maven 和 Gradle 编写简单的单元测试。你还将看到*测试驱动开发*（TDD）的示例，即在编写代码之前先编写测试

### 组织测试目录

Maven 和 Gradle 都采用约定俗的方式进行构建。它们期望一个标准的目录结构来存放主代码和测试代码。幸运的是，它们共享相同的结构，这对于你快速切换构建系统非常有帮助。

图 7.1 显示了在该结构中如何组织目录，这在第 4 章](#c04.xhtml) 中看起来应该。`src/main/java` 目录包含应用程序的 Java 代码，`src/main/resources` 目录包含非 Java 资源，如 XML 和属性文件。`src/main` 目录结构中的所有代码都用于生产。

相比之下，`src/test` 目录结构用于确保 `src/main` 中的代码按预期工作。与 `src/main` 类似，`src/test` 也存在 `java` 和 `resources` 子目录，以区分 Java 代码与其他文件。这种并行的目录结构很快就会变成直觉。

我们的项目包含一个名为 `Bingo` 的类。你会发现 `Bingo` 有*两个*测试类。`BingoTest` 是单元测试，而 `BingoIT` 是集成测试。是的，`IT` 代表*集成测试*，它测试系统中两个或多个部分之间的交互。集成测试通常会与 REST API 或数据库交互，或者利用文件系统，而单元测试则通过模拟（mocks）来抽象这些细节，你将在本章后面的部分看到这些。

你可以在 Maven Central ([https://mvnrepository.com/artifact/org.junit/junit-bom]) 上查找 JUnit 的最新版本，在本文写作时，该版本为 `5.10.2`。这既是物料清单 (BOM)也是 `junit-jupiter` 构件本身的版本。如果你需要回顾什么是 BOM 或依赖管理是如何工作的，请查看第 4 章。

```
<properties>
   <junit5.version>5.10.2</junit5.version>
</properties>

<dependencyManagement>
   <dependencies>
      <dependency>
         <groupId>org.junit</groupId>
         <artifactId>junit-bom</artifactId>
         <version>${junit5.version}</version>
         <type>pom</type>
         <scope>import</scope>
      </dependency>
    </dependencies>
</dependencyManagement>

<dependencies>
    <dependency>
       <groupId>org.junit.jupiter</groupId>
       <artifactId>junit-jupiter</artifactId>
       <scope>test</scope>
    </dependency>
</dependencies>
```

JUnit Jupiter 是 JUnit 5 的英文名称。你在 JUnit 测试中使用的导入语句中也包含 `jupiter`。BOM 是一个例外，它使用 `org.junit`（不包含 `jupiter`）作为组 ID。`junit-jupiter` 依赖的范围是 `test`，因此它对测试可用，但对主代码无效。

为了实际运行测试，Maven 使用 `Surefire` 插件运行单元测试，使用 `Failsafe` 插件运行集成测试。这些插件的版本号始终保持同步，因此你可以在 Maven Central 的 [`https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-surefire-plugin`](https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-surefire-plugin) 上查找其中一个的最新版本。该版本号放在 POM 的属性部分：

```
<surefire.version>3.2.5</surefire.version>
```

要告诉 Maven 运行测试，你需要在 Maven POM 文件的 `<build>` 部分添加 `maven-surefile-plugin` 和 `maven-failsafe-plugin`。示例例如：

```
<plugin>
   <groupId>org.apache.maven.plugins</groupId>
   <artifactId>maven-surefire-plugin</artifactId>
   <version>${surefire.version}</version>
</plugin>

<plugin>
   <groupId>org.apache.maven.plugins</groupId>
   <artifactId>maven-failsafe-plugin</artifactId>
   <!-- use same version as surefire -->
   <version>${surefire.version}</version>
   <executions>
      <execution>
         <goals>
            <goal>integration-test</goal>
            <goal>verify</goal>
         </goals>
      </execution>
   </executions>
</plugin>
```



`maven-surefire-plugin` 的配置只需将其包含在 `pom.xml` 的 `build` 部分中即可。这将确保每当你运行任何包含 `verify` 生命周期阶段的 Maven 构建时，都会自动运行单元测试。作为回顾，`verify`、`install` 和 `deploy` 阶段是包含测试常见的阶段。

相比之下，`maven-failsafe-plugin` 需要显式配置才能作为 `verify` 的一部分运行。该执行注册了集成测试映射到 `verify` 的意图。之所以存在差异是因为集成测试通常需要其他资源来运行，因此 Maven 希望你声明它们是可用的意图。

运行 `verify` 时，输出将包含类似的内容：

```
[INFO] --- surefire:3.2.5:test (default-test) @ junit5-maven ---
[INFO] Using auto detected provider 
org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.wiley.realworldjava.testing.BingoTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.020 s 
-- in com.wiley.realworldjava.testing.BingoTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ junit5-maven ---
[INFO] Building jar: /path/real-world-code-repos/Ch07-Testing/junit5-maven/target/junit5-maven-0.0.1-SNAPSHOT.jar
[INFO] 
[INFO] --- failsafe:3.2.5:integration-test (default) @ junit5-maven ---
[INFO] Using auto detected provider 
org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.wiley.realworldjava.testing.BingoIT
```

```
dependencies {

    testImplementation(platform('org.junit:junit-bom:5.10.2'))

    testImplementation('org.junit.jupiter:junit-jupiter')

    testRuntimeOnly('org.junit.platform:junit-platform-launcher')

}
```

如你所见，此示例与 Maven 项目使用了相同的 BOM。它还允许 `test` 中的代码通过 `junit-jupiter` 依赖引用 JUnit 类。`junit-platform-launcher` 依赖是新的，用于你的构建工具以挂钩正在运行的 JUnit。该依赖在过去是可选的，因此你可能在旧的文档中看不到它。

以下 Gradle 代码使用 Groovy 语法告诉 Gradle 运行所有的 JUnit 单元测试和集成测试：

```
test {

    useJUnitPlatform()

    testLogging {

       events "passed", "skipped", "failed"

       exceptionFormat "full"

    }

}
```

`useJUnitPlatform()` 的调用由 Gradle 内置代码启动你的测试。`testLogging` 代码是你告诉 Gradle 列出更多关于测试细节的方式。默认情况下，Gradle 只列出失败的测试，但不会包含失败信息。但通过此配置，所有测试方法都会被记录，无论它们是通过、被跳过还是失败，包括任何断言失败。使用 Groovy 的 Kotlin 语法，我们可以如下 true 表达式：

```
tasks.test {

   useJUnitPlatform()

   testLogging {

      events("passed", "skipped", "failed")

      exceptionFormat = org.gradle.api.tasks.testing.logging.

         TestExceptionFormat.FULL

   }

}
```

当运行 `build` 时，输出包含以下内容：

```
> Task :test FAILED

BingoIT> fromDatabase() PASSED

BingoIT> connectivityTest() FAILED

   org.opentest4j.AssertionFailedError: database not available

   at app//org.junit.jupiter.api.AssertionUtils.fail(AssertionUtils.java:38)

   at app//org.junit.jupiter.api.Assertions.fail(Assertions.java:138)

   at app//com.wiley.realworldjava.testing.BingoIT.connectivityTest(

      BingoIT.java:26)

BingoTest> math() PASSED

3 tests completed, 1 failed

FAILURE: Build failed with an exception.
```

该输出显示了运行的两个测试类：`BingoIT` 和 `BingoTest`。它还显示了 `connectivtyTest()` 失败的细节。

与 Maven 一样，完整的 Gradle 测试结果在文件系统中可用，这次是在 `build` 目录下，正如图 7.3 所示。这次，人类可读的文件是 HTML，并位于 `reports/tests` 下。XML 文件旨在用于 `test-results/test` 下的机器读取。此外，像 Maven 一样，你可以在构建文件中控制测试的配置。

![截图显示了 gradle Junit 输出。它包含了以下嵌套的文件夹：Build, classes, generated, reports, tests, 以及测试结果的展开](img/c07f003.png)

图 7.3: Gradle 中的 JUnit 输出

### 使用测试驱动开发探索测试

现在你已经知道了如何组织测试并查看结果，是时候编写测试的时间了。对于这个示例，我们将使用测试驱动开发（TDD）。

在这个示例中，我们将使用测试驱动开发创建一个简单的测试。在使用 TDD 编写代码时，你编写代码的分段比你习惯的要小得多，因为只有在你编写的测试代码要求这样做时，你才编写主代码。

这种方法确保你所有的代码都经过了测试。它还帮助你在编写每个部分之前考虑代码的行为。由于你是一次一个测试用例地编写代码，你会发现发自己在编写过程中需要重构。这是预之中的！测试让重构变得安全，因为你保证拥有完整的测试覆盖。`red-green-refactor`（红-绿-重构）这个词被用来总结 TDD 过程。

1. **红 (Red):** 编写测试。在早期阶段，测试应该失败（或代码应该有编译错误）。我们称之为“红色”，但某些 IDE 用黄色显示失败而不是红色。尽管如此，它仍然是一个错误或失败，流程仍然适用。
2. **绿 (Green):** 让测试通过。添加所有使测试通过的代码。
3. **重构 (Refactor):** 进行任何必要的更改，使代码更整洁、更易理解。
4. **从新测试重新开始。**

如果需要，可以通过添加测试的一部分并在完成测试之前使其通过编译来增加细粒度。或者，你可以只添加一个断言而不是整个测试。

让我们开始吧。想象你正在为构建重量不能超过特定数量的机器人设计软件。在这个示例中，你将设计一个提供简单机器人信息的类。第一步是通过在 `src/test/java` 中创建一个类来开始编写测试。

```
1:  package com.wiley.realworldjava.testing;
2:
3:  import org.junit.jupiter.api.BeforeEach;
4:  import org.junit.jupiter.api.Test;
5:  import static org.junit.jupiter.api.Assertions.assertEquals;
6:
7:  class FirstRobotTest {
8:
9:     private FirstRobot robot;
10:
11:    @BeforeEach
12:    void setUp() {
13:        robot = new FirstRobot();
14:    }
15:
16:    @Test
17:    void name() {
18:        assertEquals("Izzy", robot.toString());
19:    }
20:}
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`。

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



```java
new Object[] { "cat", 3 },

new Object[] { "doggy", 5 });

}
```

`@ParameterizedTest`

`@MethodSource("fetchTestData")`

```java
void values(String value, int expected) {
   assertEquals(expected, value.length(), "# chars");
}
```

在这种情况下，JUnit 调用`fetchTestData()`方法来发现参数化测试的期望参数对。如果你要调用以获取参数化数据的方法在另一个类中，你可以使用`@MethodSource`的长形式。

```java
@MethodSource(
   "com.wiley.realworldjava.testing.ParameterizedTests#fetchTestData")
```

注意这次使用了完全限定的类名。此外，在该类中调用的方法出现在`#`之后。无论目标方法位于何处，它必须是静态的才能被`@MethodSource`调用。

## 使用常用的测试库

JUnit 生态系统包含许多开源库。本节涵盖了其中一些。

### 使用 AssertJ 编码

AssertJ 是一个包含许多“流式”断言的库。要在 Maven 或 Gradle 中使用 AssertJ，请访问 Maven Central（[`mvnrepository.org/artifact/assertj-core`](https://mvnrepository.org/artifact/assertj-core)）并找到最新版本构建。表 7.2 显示了它们的编写方式。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
   <groupId>org.assertj</groupId>
   <artifactId>assertj-core</artifactId>
   <version>3.25.2</version>
   <scope>test</scope>
</dependency>
``` |
| Gradle (Groovy) | `testImplementation group: 'org.assertj', name: 'assertj-core', version: '3.25.2'` |
| Gradle (Kotlin) | `testImplementation("org.assertj:assertj-core:3.25.2")` |

以下展示了编写原本需要更多逻辑的单行断言：

```java
package com.wiley.realworldjava.testing.assertj;

import org.junit.jupiter.api.Test;

import static org.assertj.core.api.Assertions.assertThat;

class AssertThatTest {
   @Test
   void spaces() {
      assertThat("cat").isEqualToIgnoringWhitespace("c a t");
   }
}
```

使用 AssertJ 时，你从`assertThat()`开始并提供要测试的参数。它允许链式调用，以便编写如下更简洁的代码：

```java
assertThat("cat")
   .startsWith("c")
   .endsWith("t");
```

AssertJ 拥有针对字符串、列表、文件等的许多自定义断言。这里有几个：

- `isSubstringOf()`
- `isUpperCase()`
- `matches()`

大多数时候，输入`assertThat()`并使用 IDE 的自动补全将显示所有断言方法。“进一步参考”部分中的指南和 Javadoc 告诉了你可以在哪里找到更多内容。这还只是`assertj-core`！对于更特殊的需求还有特定的 AssertJ 库。

除了`assertThat()`的自定义断言外，AssertJ 还提供了软断言（soft assertions），你可以轻松地收集多个断言失败并在测试失败时一次列出它们。这对于端端端集成测试或监控测试特别有用，因为你可以一次性获取所有问题。

这是编写软断言的基本方法：

```java
@Test
void callingAssertAll() {
   SoftAssertions softly = new SoftAssertions();

   softly.assertThat("robot").isEqualTo("izzy");
   softly.assertThat(126).isLessThanOrEqualTo(125);

   softly.assertAll();
}
```

此测试有两个失败的条件。如果你使用简单的断言，测试将在第一个断言后失败。使用软断言（soft assertions），测试将由于两个问题都存在而失败，而不仅仅是第一个。输出包含以下内容：

```text
org.assertj.core.error.AssertJMultipleFailuresError:

Multiple Failures (2 failures)

-- failure 1 --

expected: "izzy"

but was: "robot"

at SoftAssertionsTest.callingAssertAll(SoftAssertionsTest.java:14)

-- failure 2 --

Expecting actual:

  126

to be less than or equal to:

  125

at SoftAssertionsTest.callingAssertAll(SoftAssertionsTest.java:15)
```

有一个注意事项：你必须在断言链的末尾调用`assertAll()`，尽管有多种方法可以避免忘记要调用`assertAll()`。请参阅“进一步参考”中的[`Selikoff.net`](http://Selikoff.net)博客文章获取示例。

### 使用 JUnit Pioneer 特性进行编码

JUnit Pioneer 库包含了许多 JUnit 5 的有用扩展。某些功能甚至有一天可能会进入 JUnit 5。

要在你的 Maven 或 Gradle 构建中使用 JUnit Pioneer 库，请前往 Maven Central（[`https://mvnrepository.com/artifact/org.junit-pioneer/junit-pioneer`](https://mvnrepository.com/artifact/org.junit-pioneer/junit-pioneer)）并找到适用于构建工具的最新版本号。表 7.3 显示了在本文写作时每个工具对应的写法。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
    <groupId>org.junit-pioneer</groupId>
    <artifactId>junit-pioneer</artifactId>
    <version>2.2.0</version>
    <scope>test</scope>
</dependency>
``` |
| Gradle (Groovy) | `testImplementation group: 'org.junit-pioneer', name: 'junit-pioneer', version: '2.2.0'` |
| Gradle (Kotlin) | `testImplementation("org.junit-pioneer:junit-pioneer:2.2.0")` |

**表 7.3**：指定 JUnit Pioneer 为依赖

在本节中，你将看到三个功能，以便直观了解项目的功能。

#### 禁用直到某个日期

第一个功能解决了`@Disabled`的局限性。禁用测试时的一个常见问题是忘记重新启用它。JUnit Pioneer 提供了一个注解，可以让你在测试在到期前一直保持禁用状态。

如果你忘记了这个测试，它将在过期日期后自动重新启用。你会“突然”收到一个失败并回起该测试的存在，此时你可以决定是否延长过期日期，或者决定现在是时候修复该测试了。又或许测试可能在不费吹力的情况下通过了，因为你设置的过期时间某些环境条件会被修复的时间。这段代码展示了如何使用该注解：

```java
@Test
@DisabledUntil(
   date = "2030-01-01",
   reason = "Need our partner service to be ready")
void waitingForServiceAvailability() {
   // 刻意留空
}
```

`reason`是可选的，但建议提供，以便你记住为何禁用该测试。当日期在未来时，测试将像使用`@Disabled`一样跳过。如果日期在过去，测试将运行，并输出一条不再被禁用的消息。

```text
timestamp = 2024-03-24T09:40:36.068881, DisabledUntilExtension = The `date`
2024-03-24, DisabledUntilExtension = The `date`
2024-03-24, DisabledUntilExtension = The `date`
```

#### 重试测试

有时测试依赖于不稳定的操作。JUnit Pioneer 提供了一个注解，让你在失败时进行重试。

```java
@Retrying(10)
void flakeyTest() {
```

重试机制会在测试失败时重新执行测试。如果所有尝试都失败，它会重试最多 10 次。

```java
@Retrying(10)
void flakeyTest() {
   Random random = new Random();

   if (random.nextInt(100) < 75) {
      fail("too high");
   }
}
```

#### 处理系统属性

Java 有全局系统属性，测试起来比较棘手。一种方法是使用`System.setProperty()`设置你想要的值，然后在测试结束时恢复它。

```java
@Test
@ClearSystemProperty(key = "JAVA_HOME")
void clearProperty() {
   assertNull(System.getProperty("JAVA_HOME"));
}

@Test
@SetSystemProperty(key = "JAVA_HOME", value = "c:/java8")
void setProperty() {
   assertEquals("c:/java8", System.getProperty("JAVA_HOME"));
}
```

#### 使用笛卡尔测试

`CartesianTest`注解允许你指定多个参数来生成测试用例。多个列表通过`@Values`提供。

```java
class SomeCartesianTest {
   @CartesianTest
   void cartesianTest(
      @Values({1, 2}) int time,
      @Values({3, 4}) int tide) {
      // 实现
   }
}
```

在此示例中，`cartesianTest`方法将为`time`和`tide`的每种组合执行。也就是说，它将针对`(1, 3)`、`(1, 4)`、`(2, 3)`和`(2, 4)`执行。

#### 了解其他功能

除了本节的功能外，其他实用的 JUnit 5 功能还包括：

- `@JsonSource`：为`@ParameterizedTest`提供 JSON 字符串。
- `@JsonClasspathSource`：为`@ParameterizedTest`提供 JSON 文件路径。
- `@IntRangeSource`：为参数化测试提供数字范围。除了增量值外，你还可以指定最小值和值。
- `@DefaultLocale`：让你在特定的区域（如国家或语言）运行测试，而不是依赖系统默认设置。
- `@DefaultTimeZone`：让你在特定的时区运行测试，而不是依赖系统默认设置。

## 模拟对象

不言说，你希望单元测试是快速且独立的，这样就可以提供快速反馈并确保你正在隔离测试逻辑。但当你的代码需要访问数据库、REST API 调用或另一个网络调用时，该怎么办？这些操作都可能是缓慢或不可用的，且结果可能会有所不同。或者，你想调用一个尚未编写实现的接口？模拟对象通过提供你可以从测试内部控制的默认实现，来对此类调用进行存桩。

模拟对象是测试双胞（test double）的一种，其中使用了真实类以外的对象。

- **哑对象（Dummy）**：传递到方法签名但从未被使用的对象。提供它们仅仅是为了满足方法签名。
- **Fake（伪造对象）**：具有某些工作实现，但比它们所模拟的服务简单的对象。
- **Stubs（存桩）**：对预期的调用提供伪造响应的对象。
- **Spy（间谍）**：合并了真实世界行为和模拟行为，并/或验证关于调用次数信息的对象。
- **Mocks（模拟对象）**：预先编程以验证某些期望的对象，例如某个方法是否被调用了`n`次。

Mock 框架提供了创建所有这些对象的 API。在本章中，我们将介绍一些最流行的 Mock 框架：`Mockito`、`EasyMock`和`Spring MockMvc`。

### 使用 Mockito 进行 Mock

Mockito 是一个在许多应用程序中流行的 Mock 框架。Mockito 将许多 Mock 类型整合到一个单一的`mock`注解中。它还有`spy`的概念，这是一种混合类型，默认使用真实的类实现，但允许你对某些方法进行 stub 处理。

要在 Maven 或 Gradle 构建中使用 Mockito，你需要包含两个依赖。第一个依赖是库本身，即`mockito-core`。此外，`mockito-junit-jupiter`提供了集成支持。访问 Maven Central（`https://mvnrepository.com/artifact/org.mockito/mockito-core`）和（`https://mvnrepository.com/artifact/org.mockito/mockito-junit-jupiter`）并找到适用于你构建工具的最新版本号。表 7.4 显示了在本书时每个工具的具体写法。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-core</artifactId>
    <version>5.11.0</version>
    <scope>test</scope>
</dependency>

<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-junit-jupiter</artifactId>
    <version>5.11.0</version>
    <scope>test</scope>
</dependency>
``` |
| Gradle (Groovy) | `testImplementation group: 'org.mockito', name: 'mockito-core', version: '5.11.0'` `testImplementation group: 'org.mockito', name: 'mockito-junit-jupiter', version: '5.11.0'` |
| Gradle (Kotlin) | `testImplementation("org.mockito:mockito-core:5.11.0")` `testImplementation("org.mockito:mockito-junit-jupiter:5.11.0")` |

**表 7.4**：指定 Mockito 为依赖项

现在让我们来看一个例子来理解 Mockito 如何工作。假设你有一个获取分数的接口。

```java
public interface ScoreService {
   int retrieveScore(int matchNumber);
}
```

现在，你想单元测试一个名为`Dashboard`的类，该类使用了名为`ScoreService`的接口。

```java
public class Dashboard {
   private ScoreService service;

   public Dashboard(ScoreService service) {
      this.service = service;
   }

   public List<Integer> getScores(int maxMatch) {
      return IntStream.range(1, maxMatch + 1)
         .map(n -> service.retrieveScore(n))
         .toList();
   }
}
```



注意构造函数接收的是一个接口。`Dashboard` 类并不知道也不在乎使用的是哪种 `ScoreService` 的实现。这是一个良好的实践，因为它使得代码具有测试性，因为允许你对实现进行 mock。

```java
@ExtendWith(MockitoExtension.class)
public class DashboardTest {

   private Dashboard dashboard;

   @Mock
   private ScoreService scoreService;

   @BeforeEach
   void setUp() {
      dashboard = new Dashboard(scoreService);
   }

   @Test
   void getScores() {
      when(scoreService.retrieveScore(1)).thenReturn(76);
      when(scoreService.retrieveScore(2)).thenReturn(91);

      List<Integer> expected = List.of(76, 91);
      List<Integer> actual = dashboard.getScores(2);

      assertEquals(expected, actual);
      verify(scoreService, times(2)).retrieveScore(anyInt());
   }
}
```

检查你预期的方法是否真的被调用通常很有用。如果你对一个 mock 调用设置了存桩（stub），但在被测试代码中从未进行过该调用，Mockito 默认会认为执行失败。你可以通过以下方式告诉 Mockito 在此类情况下不要失败：

```java
@Mock(strictness = Mock.Strictness.LENIENT)
```

独立地，你可以显式地验证代码中的任何或所有调用。以下是一些示例：

```java
verify(scoreServiceMock).retrieveScore(1);
verify(scoreServiceMock, times(1)).retrieveScore(1);
verify(scoreServiceMock, atLeast(1)).retrieveScore(1);
verify(scoreServiceMock, atMost(1)).retrieveScore(1);
verify(scoreServiceMock, atMostOnce()).retrieveScore(1);
verify(scoreServiceMock, never()).retrieveScore(9);
```

上代码块中的第一行和第二行是告诉 Mockito 验证 `retrieveScore()` 调用恰好执行了一次的等方式。（因为验证某事恰好发生一次是最常见的，因此它是默认的。）可选的验证模式允许你轻松指定带有给定参数的 mock 调用应该发生几次。此外，你可以使用前一节中的匹配器（matchers）。例如，以下代码表示验证恰好有一个带有任何 `int` 参数的调用：

```java
verify(scoreServiceMock, times(1)).retrieveScore(anyInt());
```

### Mock 具体类

上一步的示例使用了接口。然而，并不是所有的类都有接口，你不应该仅仅为了测试而添加接口。

这次你有一个新类 `DashboardViewer`。它使用了 `Dashboard` 类。

```java
public class DashboardViewer {

   private Dashboard dashboard;

   public DashboardViewer(Dashboard dashboard) {
      this.dashboard = dashboard;
   }

   public String getFormattedData(int maxMatch) {
      List<Integer> scores = dashboard.getScores(maxMatch);
      return scores.stream()
         .map(s -> "-> " + s)
         .collect(Collectors.joining("\n"));
   }
}
```

要对这进行单元测试，你不必进入 `Dashboard` 的实现并担心 `ScoreService`。幸运的是，你不需要这样做。通过对具体的 `Dashboard` 类进行 mock，你可以孤立地对 `DashboardViewer` 进行单元测试。

```java
1:  @ExtendWith(MockitoExtension.class)
2:  public class DashboardViewerTest {
3:
4:     private DashboardViewer viewer;
5:
6:     @Mock
7:     private Dashboard dashboardMock;
8:
9:     @BeforeEach
10:    void setUp() {
11:       viewer = new DashboardViewer(dashboardMock);
12:    }
13:
14:    @Test
15:    void scores() {
16:       when(dashboardMock.getScores(3)).thenReturn(List.of(69, 23, 106));
17:       String expected = """
18:          -> 69
19:          -> 23
20:          -> 106""";
21:       String actual = viewer.getFormattedData(3);
22:
23:       assertEquals(expected, actual, "data");
24:    }
25: }
```

通过 Mockito 的流程与之前 mock 接口的示例相似。第 6-7 行注入了一个 mock，这次是一个具体类而不是接口。第 16 行声明了预期的调用和返回值。第 21 行调用了测试代码。`DashboardViewer` 类请求 mock 获取 scores。通过断言数据格式正确结束。这里不需要可选的 `verify()` 调用。如果 mock 没有被调用，第 21 行将无法获得正确的数据。注意 `DashboardViewer` 和 `DashboardViewerTest` 都不知道 `Dashboard` 的真实实现！

### Mock 静态方法

注入实例变量或参数的效果良好，但如果你想 mock 一个静态方法呢？由于静态方法直接位于测试代码中，无法简单地注入对象。幸运的是，你仍然可以使用 Mockito 来 mock！

假设 `DashboardViewer` 有一个需要测试的方法：

```java
public String header() {
   return LocalDate.now().toString();
}
```

测试此内容需要为 `LocalDate.now()` 静态方法请求一个 mock。

```java
@Test
void header() {
   LocalDate testDate = LocalDate.of(2024, Month.NOVEMBER, 15);
   try (MockedStatic<LocalDate> localDateMock = 
      Mockito.mockStatic(LocalDate.class)) {
      localDateMock.when(LocalDate::now).thenReturn(testDate);
      String expected = "2024-11-15";
      String actual = viewer.header();
      assertEquals(expected, actual, "header");
   }
}
```

`mockStatic()` 方法创建了一个在 `try with resources` 块内的 mock。`when/thenReturn` 结构与非静态 mock 相同，因此现在看起来应该熟悉。

### 使用 EasyMock

Mockito 和 EasyMock 之间的概念是相似的。学会两者将让你很快上手。

要使用 EasyMock，请向你的项目添加以下依赖项。表 7.5 显示了本书时每个者的写法。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
    <groupId>org.easymock</groupId>
    <artifactId>easymock</artifactId>
    <version>5.2.0</version>
    <scope>test</scope>
</dependency>
``` |
| Gradle (Groovy) | `testImplementation 'org.easymock:easymock:5.2.0'` |
| Gradle (Kotlin) | `testImplementation("org.easymock:easymock:5.2.0")` |

查看 `Dashboard` 的单元测试，你应该看到一些熟悉的概念。

```java
1:  @ExtendWith(MockitoExtension.class)
2:  public class DashboardTest {
3:
4:     private Dashboard dashboard;
5:
6:     @Mock
7:     private ScoreService serviceMock;
8:
9:     @BeforeEach
10:    void setUp() {
11:       dashboard = new Dashboard(serviceMock);
12:    }
13:
14:    @Test
15:    void getScores() {
16:       expect(serviceMock.retrieveScore(1)).andReturn(76);
17:       expect(serviceMock.retrieveScore(2)).andReturn(91);
18:
19:       replay(serviceMock);
20:
21:       List<Integer> expected = List.of(76, 91);
22:       List<Integer> actual = dashboard.getScores(2);
23:       assertEquals(expected, actual, "scores");
24:
25:       verify(serviceMock);
26:    }
27: }
```

就像 Mockito 一样，第 1 行有一个 `@ExtendWith` 注解让 mock 框架控制测试执行。第 6 行有一个 `@Mock` 注解注入 mock 对象。第 16 行和 17 行设置了调用 `retrieveScore()` 方法时的返回值。虽然方法名与 Mockito 不同，但概念是相同的。

EasyMock 有更多功能。正如你从与 Mockito 的相似性所示，一旦学会了一个，学习另一个 mock 框架是非常容易！

### 使用 Spring MockMVC

你在第 6 章“了解 Spring 框架”中学习了 Spring。Spring 提供了一个库来方便测试。它的核心功能之一是可以在没有服务器的情况下测试 Spring 控制器这比之前几节的 mock 级别更高。

Spring 的 MockMvc 属于 Spring Test。将其安装到你的 Spring 项目中的最简单方法是指定 `spring-boot-starter` 依赖，它将下载所有需要的依赖。表 7.6 显示了本书时每个者的写法。

#### Maven

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <version>3.2.4</version>
    <scope>test</scope>
</dependency>
```

#### Gradle (Groovy)

`testImplementation group: 'org.springframework.boot', name: 'spring-boot-starter-test', version: '3.2.4'`

#### Gradle (Kotlin)

`testImplementation("org.springframework.boot" + ":spring-boot-starter-test:3.2.4")`

**表格 7.6**: 指定 Spring Boot Starter Test 为依赖项

首先，我们将创建三个示例类，展示如何使用 `MockMvc` 来测试控制器（controller）。该示例是一个比赛跟踪器服务，用于获取比赛中当前的场次。第一个类是应用程序的一部分，无论你编写了多少个测试类，它都只存在一次。

```java
@SpringBootApplication
public class DashboardApp {
    public static void main(String[] args) {
        SpringApplication.run(DashboardApp.class, args);
    }
}
```

如果我们在运行它，`SpringBootApplication` 将启动真实的应用程序。尽管这只是一个测试，但它需要存在，`MockMvc` 才能判断你的 Spring 应用程序是否能够工作。接下来是控制器将引 `MatchTrackerService`：

```java
@Service
public class MatchTrackerService {
   private int matchNumber = 0;

   public void startMatch() {
      matchNumber++;
   }

   public int getCurrentMatchNumber() {
      return matchNumber;
   }
}
```

该服务的实现非常基础，但这并不重要，因为你很快就会对其进行 mock（模拟）了！

最后是使用该服务的控制器。

```java
@RestController
public class DashboardController {

   private MatchTrackerService tracker;

   public DashboardController(MatchTrackerService tracker) {
      this.tracker = tracker;
   }

   @GetMapping("/match")
   public @ResponseBody String displayCurrentMatch() {
      return "In match %s".formatted(tracker.getCurrentMatchNumber());
   }
}
```

这个简单的控制器使用了依赖注入（正如你在第 6 章中所学习到的）来获取 `MatchTrackerService`。它使用服务返回的数据来格式化出一个良好的显示。你可能认为你可以直接使用 Mockito 或 EasyMock 测试 `DashboardController` 类，你是正确的！你可以直接注入依赖并测试 `displayCurrentMatch()` 的逻辑。但 `MockMvc` 增加的功能是可以使用 REST 调用来测试你的端点，并让 Spring 完成所有的依赖注入和测试，以确保你的注解和 Spring 配置是正确的。

```java
1:  @SpringBootTest
2:  @AutoConfigureMockMvc
3:  class DashboardControllerTest {
4:
5:     @Autowired
6:     MockMvc mockMvc;
7:
8:     @MockBean
9:     MatchTrackerService trackerMock;
10:
11:    @Test
12:    void matchNumber() throws Exception {
13:       when(trackerMock.getCurrentMatchNumber()).thenReturn(35);
14:
15:       mockMvc.perform(get("/match"))
16:          .andExpect(status().isOk())
17:          .andExpect(content().string(containsString("In match 35")));
18:
```



19:       `verify(trackerMock, times(1)).getCurrentMatchNumber();`

20:    }

21: }

```

第 1 行和第 2 行告诉 JUnit 使用 Spring MockMvc 进行测试。第 5 行和第 6 行自动装配 `mockMvc`。第 8 行和第 9 行将 `MatchTrackerService` 注入为 mock Bean。

第 11 行和第 12 行定义了 `matchNumber` 方法。第 13 行设置 `trackerMock.getCurrentMatchNumber()` 返回 35。

第 15 行到第 17 行执行 `mockMvc.perform(get("/match"))`，并期望状态为 OK，且内容包含 "In match 35"。

第 19 行验证 `trackerMock` 被调用了 1 次 `getCurrentMatchNumber()`。

一旦你运行了一个或多个带覆盖率的测试，你可以在两个位置查看结果。首先是覆盖率报告。图 7.7 显示 IntelliJ 的 `JaCoCo` 报告，而图 7.8 显示 Eclipse 的 `JaCoCo` 报告。注意，即使底层的计算器是相同的，IDE 也以不同的方式对结果进行分类。

![一个窗口截图显示了 IntelliJ 的 `JaCoCo` 报告。提到一个表头为 `elements`、`class`、`method`、`line` 和 `branch` 的表格。](img/c07f007.png)

**图 7.7**: 代码覆盖 IntelliJ 报告

![一个窗口截图显示了 Eclipse 的 `JaCoCo` 报告。提到一个表头为 `elements`、`coverage`、`covered instructions`、`missed instructions` 和 `total instructions` 的表格。](img/c07f008.png)

**图 7.8**: 代码覆盖 Eclipse 报告

你可以查看覆盖率的另一个位置是编辑器本身。每一行都用颜色标记，这样你可以在查看代码时直接看到结果，并快速识别未测试的代码。颜色例如下：

*   **红色：**该行完全没有被测试。
*   **黄色：**该行至少有一个分支没有被测试。
*   **绿色：**该行的所有分支都已测试。

### 在构建中运行覆盖率

对于 Maven，生成覆盖率报告的第一步是从 Maven Central 找到所需的插件 [`https://mvnrepository.com/artifact/org.jacoco/jacoco-maven-plugin`](https://mvnrepository.com/artifact/org.jacoco/jacoco-maven-plugin)。

然后，你将插件添加到 POM 文件的 `<build>` 部分。

```
<plugin>
   <groupId>org.jacoco</groupId>
   <artifactId>jacoco-maven-plugin</artifactId>
   <version>${jacoco.version}</version>
   <executions>
      <execution>
         <goals>
            <goal>prepare-agent</goal>
            <goal>report</goal>
         </goals>
      </execution>
   </executions>
</plugin>
```

运行 Maven 构建会在 target 目录中创建一个 `jacoco.exec` 文件。`.exec` 文件扩展使其很容易识别该文件来自 `JaCoCo`。它包含了如果你在开启覆盖率运行项目中的所有测试时 IDE 会生成的相同数据。事实上，`jacoco.exec` 文件可以被你的 IDE 读取以直接在类文件中显示覆盖率，或者被 Sonar 与你的其他 Sonar 报告一起显示覆盖率结果。

对于 Gradle，设置更短。只需在 `plugins` 部分添加 ID `jacoco`。构建时，将创建一个 `jacoco` 目录，其中包含一个 `test.exec` 文件。

## 使用 IntelliJ 优化你的测试

虽然所有的 IDE 都有处理测试的功能，但 IntelliJ 拥有最全的 set。在接下来的章节中，你将探索这些功能。

### 查看断言消息

假设你有一个失败的测试：

```
@Test
void diff() {
   String expected = """
      winter
      spring
      summer
      fall
      """;
   String actual = """
      winter
      spring
      summer
      autumn
      """;
   assertEquals(expected, actual, "seasons");
}
```

该测试在 IntelliJ 中的输出如下：

```
org.opentest4j.AssertionFailedError: seasons ==> 
<Click to see difference>
```

图 7.9 显示了当你点击查看差异时看到的内容。高亮的文本是预期值和实际值之间的差异。IntelliJ 向你显示每个值的完整文本，以便更容易理解失败上下文。

![一个窗口截图显示了预期的实际的气候。两者之间的差异显示在第四行并被高亮。 ](img/c07f009.png)

**图 7.9**:在 IntelliJ 中比较预期和实际值

### 探索测试运行

当在 IntelliJ 中运行测试时，会出现一个窗口，提供查看结果、重新运行测试、处理失败测试等更多选项。（参见图 7.10）。

![一个窗口截图显示了在 IntelliJ 中运行测试时，查看结果、重新运行测试、处理失败测试等更多选项。](img/c07f010.png)

**图 7.10**:JUnit IntelliJ 选项

使用此窗口，有多种方法可以重新运行测试。

*   右键点击特定类可以获得运行类中所有测试的选项。
*   右键点击特定测试方法可以获得运行该测试的选项。
*   点击顶部导航栏中的第一个图标运行输出中的所有测试。
*   点击顶部导航栏中的第二个图标仅运行输出中的失败测试。

行为驱动开发 (BDD) 是一种测试实践，它使用源自用户群的一种种自然语言语法。测试使用以下格式结构化：

```
Given that a customer wants to enable multi factor authentication
When the customer logs in
Then an option to call or text should appear.
```

`given`、`when` 和 `then` 是 BDD 的标准用语。如果你要表达的内容超过了一个短语的容纳范围，可以使用多个 `and` 或 `but` 子句来开始新行。

有许多支持 BDD 的测试库。

*   `Cucumber`: 最常用的 BDD 库，使用 Ruby 编写
*   `Cucumber-JVM`: Cucumber 的扩展，使用 Java 编写
*   `JBehave`: 使用 Java 编写，专注于将 given/when/then 故事视为一系列步骤

### 合约测试 (Testing Contracts)

对 API、HTTP 调用或微服务的合约进行测试非常有用。消费者驱动的合约测试 (CDC) 允许你独立地测试组件，同时确保组件符合合约要求。

一个合约有两个双方：`provider`（提供者）提供 API，而 `consumer`（消费者）调用该 API。双方都需要遵守合约，否则会导致测试将失败。

要使用 CDC，你需要创建一个合约，它可以生成提供者和客户端存根（stubs）。例如，你可以指定一个 HTTP 请求并编码预期的状态、标头和响应。这代表了消费者和提供者之间的协议或“契约”（pact）。

管理 CDC 的流行框架有 Spring Cloud Contract 和 Pact。Spring Cloud Contract 使用 Groovy 或 YAML 编写合约并生成测试来验证合约。Spring Cloud Contract 也可以集成 Pact。在第 6 章 中，我们介绍了 Spring Cloud Contract。

### 理解黄金大师模式 (Golden Master Pattern)

有时，你希望确保使用固定输入运行程序所得到的结果不会随时间而改变。这在程序生成文件或长/复杂的字符串时特别有用。例如，假设你想测试以下方法，它接受一个字符串元素数组并产生包含每个原始字符串及其长度的字符串。

```
public static String create(String… names) {
   return Arrays.stream(names)
      .map(s -> "%s,%d".formatted(s, s.length()))
      .collect(Collectors.joining("\n"));
}
```

这种测试的一种方法是使用一组断言（asserts）。

```
@Test
void testWithAssertions() {
   String actual = CsvGenerator.create("izzy", "sienna", "gabriel");
   String[] lines = actual.split("\n");
   assertEquals("izzy,4", lines[0], "first line");
   assertEquals("sienna,6", lines[1], "second line");
   assertEquals("gabriel,7", lines[2], "third line");
}
```

虽然这种方法可行，但它的可读性没有所需的那么好。它也是脆弱的。如果我们对预期输出进行修改以重新排序行和增加另一列，我们必须修改多处代码。

`黄金大师`（golden master）模式为断言粒度细节提供了替代方案。下面的示例演示了这种模式的使用。注意，你根据结果的长短将预期结果存储在变量或文件中，然后与进行进行比较：

```
@Test
void testWithGoldenMaster() {
   String expected = """
      izzy,4
      sienna,6
      gabriel,7""";
   String actual = CsvGenerator.create("izzy", "sienna", "gabriel");
   assertEquals(expected, actual, "data");
}
```

现在如果测试失败，你可以使用 IDE 的断言比较窗口在一个处看到所有的差异和上下文。然后你再决定该更改是否是故意的。如果不是，你就知道代码坏了！如果更改是有意为之，你可以从比较窗口复制整个新字符串并将其粘贴到文本块或文件中。现在，该字符串就是新的“黄金大师”，未来的代码将与它进行偏差比较。

### 变异测试 (Testing Mutations)

早些你已经了解到代码覆盖率并不足以判断测试的好坏。确保良好测试的一种方法是进行代码审查。另一种方法是`变异测试`（mutation testing）。当你运行变异测试时，变异测试库会插入微小的更改并运行你的测试。如果测试失败，那是好事。这意味着测试检测到了变化。如果测试仍然通过，说明它们不够彻底。

例如，变异测试可能会删掉一个 `if` 语句，或者可能会将 `<` 改为 `<=`。由于存在大量可能的变异，变异测试库会自动为你处理这些。在 Java 中，`PIT` (`PITest`) 框架会生成变异并报告结果。PIT 曾代表并行隔离测试（Parallel Isolated Test）。随着它的演变（或变异），该缩写已不再适用，但名称保留了下来。

### 在 DRY 与 DAMP 之间做出决策

在开发中，我们学习编写 DRY 代码：“不要重复你自己”（don't repeat yourself）。其核心思想是代码不应该有重复，重复可能会导致维护问题，使得当一处发生变化而另一处未更改时，代码不同步。

这对于通用代码来说是一个重要原则，但测试的可读性更为重要。因此，对于测试来说，“描述性且有意义的短语”（DAMP）通常会发挥作用。这并不意味着你应该忽略测试中的重复。这意味着你应该学会识别什么时候重复是可以接受的。

假设你想测试这个类：

```
public final class Shift {
   public static record Coords(int x, int y){
   public static Coords moveUp(Coords original) {
      return Coords(original.x, original.y + 1);
   }
   public static Coords moveDown(Coords original) {
      return Coords(original.x, original.y - 1);
   }
}
```

以 DAMP 方式测试时，你可以编写如下代码：

```
@Test
void moveUp() {
   Coords original = new Coords(4, 7);
   Coords actual = Shift.moveUp(original);
   assertEquals(4, actual.x());
   assertEquals(8, actual.y());
}

@Test
void moveDown() {
   Coords original = new Coords(4, 7);
   Coords actual = Shift.moveDown(original);
   assertEquals(4, actual.x());
   assertEquals(6, actual.y());
}
```

注意代码非常相似。然而，所有的逻辑都是内联的，非常容易阅读。将其重构为 DRY 会得到：

```
private static final int X = 4;

private void assertCoords(Coords actual, int expectedX, int expectedY) {
   assertEquals(expectedX, actual.x());
   assertEquals(expectedY, actual.y());
}

@Test
void moveUp() {
   Coords original = new Coords(X, 7);
   Coords actual = Shift.moveUp(original);
   assertCoords(actual, X, 8);
}

@Test
void moveDown() {
   Coords original = new Coords(X, 7);
   Coords actual = Shift.moveDown(original);
   assertCoords(actual, X, 6);
}
```



首先，注意预期值 `4` 不再在测试中重复，因为它是一个常量。其次，重复被抽象到了名为 `assertCoords()` 的公共方法中。判断这些选择更清晰是主观的。测试的关键是确保你不要以牺牲可读性的代价来避免重复。有些重复是可以接受的！

## 参考文献

*   [`junit.org/junit5/docs/current/user-guide`](https://junit.org/junit5/docs/current/user-guide) — JUnit 5 用户指南
*   [`github.com/junit-team/junit5-samples`](https://github.com/junit-team/junit5-samples) — 按构建工具分类的示例
*   [`assertj.github.io/doc`](https://assertj.github.io/doc) — AssertJ 文档
*   [`www.javadoc.io/doc/org.assertj/assertj-core/latest/org/assertj/core/api/Assertions.html`](http://www.javadoc.io/doc/org.assertj/assertj-core/latest/org/assertj/core/api/Assertions.html) — AssertJ 断言 Javadoc
*   [`https://www.selikoff.net/2024/03/23/multiple-ways-of-using-soft-asserts-in-junit-5`](https://www.selikoff.net/2024/03/23/multiple-ways-of-using-soft-asserts-in-junit-5) — 在不调用 `assertAll()` 的情况下使用 Soft Assertion 的多种方法
*   [`https://junit-pioneer.org/docs`](https://junit-pioneer.org/docs) — JUnit Pioneer 文档
*   [`https://javadoc.io/doc/org.mockito/mockito-core/latest/org/mockito/Mockito.html`](https://javadoc.io/doc/org.mockito/mockito-core/latest/org/mockito/Mockito.html) — Mockito 文档
*   [`https://easymock.org/user-guide.html`](https://easymock.org/user-guide.html) — EasyMock 文档
*   [`https://docs.spring.io/spring-framework/reference/testing/spring-mvc-test-framework.html`](https://docs.spring.io/spring-framework/reference/testing/spring-mvc-test-framework.html) — Spring MockMvc 文档
*   [`www.eclemma.org/userdoc/index.html`](http://www.eclemma.org/userdoc/index.html) — JaCoCo 文档
*   [`https://openclover.org/documentation`](https://openclover.org/documentation) — Clover 文档
*   [`https://docs.pact.io`](https://docs.pact.io) — Pact 文档
*   [`https://spring.io/projects/spring-cloud-contract`](https://spring.io/projects/spring-cloud-contract) — Spring Cloud Contract 文档
*   [`https://pitest.org/quickstart`](https://pitest.org/quickstart) — PIT 文档

## 总结

在本章中，你学习了如何使用 Java 编写测试。关键概念包括以下：

*   使用 `JUnit` 进行断言和测试流
*   使用 `Mockito`、`EasyMock` 和 `Spring MockMvc` 创建 mock 对象
*   测量测试覆盖率以识别缺失的测试
*   测试类型

# 8 使用 Project Lombok 的注解驱动代码

Project Lombok 是生活中的一种小巧便利。Lombok 使用简单的注解来消除大量的样板代码，例如 getters 和 setters、日志记录、`equals` 和 `hashCode`，以及其他可能掩盖 Java 代码库的脚架代码。Lombok 通过字节码*重织*（*reweaving*）的魔法实现了这一点，该过程在不修改你的源文件的情况下，通过添加所需的代码来重写 `.class` 文件。

你可能会担心这会使调试和日志记录变得复杂，因为源代码的行号将与修改后的类不匹配。但实际上，Lombok 在执行代码中调整了这一点，而且主要的集成开发环境（IDE）也能优雅地处理它。诚然，在复杂的调试会话期间，进入生成的代码可能会很困难，或者出现晦涩的日志信息，例如，如果异常是从不在你代码库中的代码中抛出的！

其中某些内容听起来可能像 Java 14 引入的 Java “记录”（records）。对于需要不可变数据对象的情况，records 通常是更好的选择。但 Lombok 提供了更广泛的功能，许多企业开发团队都在使用它。对于那些使用它的团队来说，它添加了巨大的价值。

你可能还在想可以使用代码生成来创建 getter、setter、equals 等。代码生成的问题是，你拥有需要维护的代码，并且存在不同步的风险。此外，代码覆盖率工具将显示这些生成的代码的覆盖率很低。

作为一个冷知识，Lombok 是以印度尼西亚的一个岛屿命名的，该岛位于大爪哇岛（Java）以东约一天车程的地方。

在本章中，我们将涵盖 Project Lombok 最重要的部分，包括安装 Project Lombok 以及使用所有主要的注解，例如 `@Data`、`@ToString`、`@Log` 等。

## 为 Lombok 准备环境（PREPARING YOUR ENVIRONMENT FOR LOMBOK）

在使用 Lombok 之前，你可能希望让你的开发环境有所预期。这意味着你需要按照本节所述将 Lombok 安装到你的 IDE 中。你还需要告诉你的构建工具它。

### 在 IntelliJ 中安装

从 IntelliJ 2020.3 版本开始，Lombok 已经内置了，因此不需要做太多。当你第一次使用 Lombok 时，IntelliJ 会提示你启用注解处理，但你可以主动在 IntelliJ 中操作，进入 Settings ➪ Build, Execution, Deployment ➪ Compiler ➪ Annotation Processors，如图 8.1 所示。

![一张设置窗口的截图。从侧边栏选中了注解处理器。右侧的详细信息包含一个标记为“enable annotation processing”的复选框，已选中并高亮显示。](img/c08f001.png)

**图 8.1**](#c08.xhtml_R_c08-fig-0001): 勾选 Enable Annotation Processing 复选框。

为了确保万无，如果你在构建中包含了 Lombok 的 `JAR`，即使没有插件代码也可以编译。但如果没有插件，IDE 会认为对 Lombok 生成的 getters、setters 等任何调用都是错误，因为 IDE 不会在代码库中看到这些代码。在较早的 IntelliJ 版本中，开发者需要安装 Lombok 插件。但现在，Lombok 已经包含在内，因此不再需要。

### 在 Eclipse 中安装

要在 Eclipse 中安装，请按照以下步骤操作：

1.  前往[`https://lombok.org/download`](https://lombok.org/download) 并下载最新版本的 Lombok。
2.  点击 Install/Update 按钮安装 Lombok。
3.  重启 Eclipse，就可以使用了。

![一张设置窗口的截图。从侧边栏选中了注解处理器。右侧的详细信息包含一个标记为“enable annotation processing”的复选框，已选中并高亮显示。](img/c08f001.png)

**图 8.2**](#c08.xhtml_R_c08-fig-0001): 安装 Eclipse

### 在 VS Code 安装

VS Code 的两个主要的 Java 扩展（Oracle 和 Microsoft）都包含了 Lombok 支持。有一个来自 Microsoft 的旧扩展名为“Lombok's Annotation Support”。

### 在 Maven 或 Gradle

要在构建工具中包含 Lombok，请找到“lombok”的最新版本号。在写作期间，表 8.1 显示了每种配置的写法。

| 工具 | 语法 |
| --- | --- |
| Maven |  

```xml
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.18.30</version>
    <scope>provided</scope>
</dependency>
``` |
| Gradle (Groovy) |  

```groovy
compileOnly group: 'org.projectlombok', name: 'lombok', version: '1.18.30'
``` |
| Gradle (Kotlin) |  

```kotlin
compileOnly("org.projectlombok:lombok:1.18.30")
``` |

**表 8.1**](#c08.xhtml_R_c08-tbl-0001): 将 Lombok 作为依赖

学习 Lombok 注解的最佳方法是观察它们是如何工作的。让我们从一个示例开始，创建一个名为 `User` 的类，它包含用户 ID、名称、地址以及可能存在的其他实例变量。首先，我们将使用传统的旧方法，不使用 Lombok。

该类有三个成员：`userID`、`name` 和 `address`。

```java
public class User {
   // userID 无法编译。我们将其设置为 final 是为了演示构造函数。请关注！
   private final int userID;
   private String name;
   private String address;
}
```

但是为了让这个类变得有用，需要大量的模板代码。添加 getters、 setters、`toString()` 和 `hashCode()` 会让原本整洁的 `User` 类变成这个臃肿的“庞兽”：

```java
import java.util.Objects;

public class User {
   private final int userID;
   private String name;
   private String address;

   public int getUserID() {
      return userID;
   }

   public String getName() {
      return name;
   }

   public void setName(String name) {
      this.name = name;
   }

   public String getAddress() {
      return address;
   }

   public void setAddress(String address) {
      this.address = address;
   }

   public User(int userID, String name, String address) {
      this.userID = userID;
      this.name = name;
      this.address = address;
   }

   @Override
   public boolean equals(Object o) {
      if(this==o) return true;
      if(o==null) return false;
      return o instanceof User user
         && getUserID()==user.getUserID()
         && Objects.equals(getName(), user.getName())
         && Objects.equals(getAddress(), user.getAddress());
   }

   @Override
   public int hashCode() {
      return Objects.hash(getUserID(), getName(), getAddress());
   }

   @Override
   public String toString() {
      return "User{" +
      "userID=" + userID +
      ", name='" + name + '\'' +
      ", address='" + address + '\'' +
      '}';
   }
}
```

## 使用 Lombok 方式转换

注解是 Lombok 的核心。在本节中，我们将通过用更少的代码重写之前的示例来介绍每个注解！

### 使用 @Data：包含所有内容的注解

再次从基础类开始，但这次添加 `@Data` 注解（记得导入 `lombok.Data` 注解）。

```java
import lombok.Data;

@Data
public class User {
   private final int userID;
   private String name;
   private String address;
}
```

这段代码看起来和原始代码相似！但如果你在 IDE 中跟着操作，你会发现 final `userID` 下的红色下划线消失了，因为现在会自动生成一个构造函数。Lombok 的 `@Data` 注解会自动向你的类中生成字节码，实现以下功能：

* `toString()`
* `equals()`
* `hashCode()`
* 所有字段的 Getters
* 所有非 final 字段的 Setters
* 必需参数构造函数，包含未赋值的 final、非静态、非空实例变量
* `canEquals()`，用于特殊情况（例如，如果你需要为继承重新定义等效性）

Lombok 不会触动你的源代码；它只是在编译后将模板代码织入到你的字节码中。

你很快就会发现，这些方法都可以可以通过更具体的注解单独重新织入以进行更细粒度的控制：`@ToString`、`@EqualsAndHashCode`、`@Getter`、`@Setter` 和 `@RequiredArgsConstructor`。

### 自动生成 @Getter 和 @Setter 方法

已经所示你可以在类名上标记 `@Data` 来自动生成构造函数以及所有的 getters, setters 等。但有时你想要覆盖自动生成的行为；例如，你可能想将访问级别从默认的 `public` 更改为限制性更大的 `protected`。或者你可能不想让类成为一个 `Data` 类，但确实想要一些 getters 和 setters。这时你可以使用 `@Getter` 和/或 `@Setter` 注解。

例如，假设我们有一个没有注解的类。

```java
public class Automobile {
   private String model;
}
```

为了为此自动生成 getter 和或 setter，我们可以应用 `@Getter` 和 `@Setter` 注解。

```java
import lombok.Getter;
import lombok.Setter;

public class Automobile {
   @Getter @Setter
   private String model;
}
```

这将织入生成类的字节码以添加方法。

```java
public void setModel(String model) 
public String getModel()
```

我们可以独立使用这些注解。例如，如果我们需要 getter 而不需要 setter，则只使用 `@Getter`。它会自动遵循 Java 规范。例如，如果实例变量是布尔类型：

```java
import lombok.Getter;

public class Automobile {
  @Getter
  private boolean used;
}
```

生成的 getter 将如下：

```java
public boolean isUsed()
```



默认情况下，自动生成的 `getters` 和 `setters` 具有 `public` 访问权限，但你可以通过指定访问方法属性来更改。以下代码表示生成一个私有的 `Setter`：

```java
import lombok.AccessLevel;
import lombok.Getter;
import lombok.Setter;

public class Automobile {
   @Getter @Setter(AccessLevel.PRIVATE) private String model;
}
```

这将生成：

```java
public String getModel();
private void setModel(String model);
```

你也可以通过对类名应用 `@Getter` 和 `@Setter` 注解为整个类自动生成 `getters` 和 `setters`。该类可以是标准类，也可以是内部类。

```java
import lombok.Getter;
import lombok.Setter;

@Getter @Setter
public class Automobile {
   private String manufacturer;
   private String make;
   private String model;
}
```

这将为所有实例变量生成 `public` `getters` 和 `setters`。如果你想更改特定字段的访问级别，可以对这些字段单独标记注解，这将覆盖默认行为。你也可以指定 `AccessLevel.NONE` 来防止生成该访问器。

```java
import lombok.AccessLevel;
import lombok.Getter;
import lombok.Setter;

@Getter @Setter
public class Automobile {
   // 为 manufacturer 生成一个保护的 setter
   // 生成方法：protected setManufacturer(String m)
   @Setter(AccessLevel.PROTECTED) private String manufacturer;

   // 类 @Setter 和 @Getter 注解将为 make 生成
   //  getter 和 setter
   private String make;

   // 不为 model 生成 setter
   @Setter(AccessLevel.NONE) private String model;
}
```

以下是支持的访问级别：

* `AccessLevel.NONE`: 不生成访问器方法。
* `AccessLevel.PACKAGE`: 生成默认访问方法。
* `AccessLevel.PRIVATE`: 生成 `private` 访问方法。
* `AccessLevel.PROTECTED`: 生成 `protected` 访问方法。
* `AccessLevel.PUBLIC`: 生成 `public` 访问方法。（这是默认值，可以省略。）

还有一个 `AccessLevel.MODULE`，但它已不再使用。

### 使用 @ToString

你可以在任何类上标记 `@ToString` 注解，它将生成一个 `public String toString()` 方法，包含所有非静态字段。

一些可选开关允许你格式化 `String` 输出，例如它的详细程度。我们在这里不会提到所有的开关；请参阅 Lombok 网站 [`https://projectlombok.org/`](https://projectlombok.org/) 获取完整文档。然而，我们将提到的一个常用功能是控制包含哪些字段。默认情况下，每个非静态字段都会包含。你可以通过对字段标记 `@ToString.Exclude` 来声明式地排除字段；例如在下面的代码中，`address` 字段被排除了。你可以从执行代码的打印输出看到该字段在输出中被省略了。

```java
import lombok.AllArgsConstructor;
import lombok.ToString;

@AllArgsConstructor @ToString
public class User {
   private final int userID;
   private String name;
   @ToString.Exclude private String address;

   public static void main(String[] args) {
      User user = new User(123, "Joe", "123 Main");
      System.out.println(user);
   }
}
```

这会输出以下：

```
User (userID=123, name=Joe)
```

对于 `Collections`，`@ToString` 注解会生成深度渲染。例如，在下面的代码中，`toString()` 方法将包含列表 `friends` 的所有成员，正如你在执行该代码后看到的 `toString()` 方法的输出所所示。

```java
import lombok.AllArgsConstructor;
import lombok.ToString;
import java.util.List;

@AllArgsConstructor @ToString
public class User {
   private final int userID;
   private String name;
   @ToString.Exclude private String address;
   private List<String> friends;

   public static void main(String[] args) {
      User user = new User(123, "John Jones", "123 Main",
         List.of("William", "Alok", "Heather"));
      System.out.println(user);
   }
}
```

这会输出以下：

```
User (userID=123, name=John Jones, friends=[William, Alok, Heather]
```

### 使用 @EqualsAndHashCode

Java 编程的基本准规则之一是 `equals()` 和 `hashCode()` 方法必须保持一致；即任何 `equals()` 为真的对象都必须返回相同的 `hashCode()`。此外，我们希望不同的实例产生不同的哈希值。

我们可以通过在类上使用 `@EqualsAndHashCode` 注解来实现这一点，它会对对象实例的所有非静态（`nonstatic`）、非瞬态（`nontient`）字段应用素数哈。

你可以通过在排除的字段上标记 `@EqualsAndHashCode.Exclude` 来将特定字段从 `hashCode` 和 `equals` 中排除，这与我们在 `@ToString` 中看到的方式类似。

```java
import lombok.AllArgsConstructor;
import lombok.EqualsAndHashCode;

@AllArgsConstructor
@EqualsAndHashCode
public class Automobile {
   private String make;
   private String model;
   @EqualsAndHashCode.Exclude
   private String color;

   public static void main(String[] args) {
      Automobile car1 = new Automobile("Tesla", "Model 3", "Gray");
      Automobile car2 = new Automobile("Tesla", "Model 3", "Red");
      Automobile car3 = new Automobile("Tesla", "Model Y", "Red");

      System.out.println(car1.equals(car2)); // true
      System.out.println(car1.equals(car3)); // false
   }
}
```

你可以看到 `color` 被从 `equals` 和 `hashCode` 方法中排除了。因此，`car1` 和 `car2` 是相等的，因为它们仅在颜色上不同。然而，`car2` 和 `car3` 不相等，因为它们在 `Model` 上不同。

### 使用 @AllArgsConstructor、@RequiredArgsConstructor 和 @NoArgsConstructor 注解生成构造函数

构造函数是常见的样板代码，任何需要实例化的类中都是必需的。如果你在类中有 `final`、非静态的实例字段，它们必须在构造函数中赋值。

在类上使用 `@AllArgsConstructor` 注解来生成一个构造函数，该构造将包含类中所有非静态、非 `final` 实例变量的赋值。

在类上使用 `@RequiredArgsConstructor` 注解来生成一个构造函数，该构造将包含类中所有未赋值的 `final` 实例变量的赋值。此外，你可以在实例变量上标记 `@NonNull`，使其包含在 `@RequiredArgsConstructor` 注解中。

在类上使用 `@NoArgsConstructor` 注解来生成一个无参数构造函数。如果存在任何未赋值的 `final` 实例变量，这将导致编译错误。为了解决这个问题，请使用 `@NoArgsConstructor(force=true)`。这将创建一个无参数构造函数，其实现将为任何未赋值的 `final` 实例变量分配 `null`、`zero` 或 `false`。

你可以在类上使用任何一个或所有的构造函数注解。这里有一个示例：

```java
import lombok.AllArgsConstructor;
import lombok.NoArgsConstructor;
import lombok.RequiredArgsConstructor;
import lombok.ToString;

@RequiredArgsConstructor @AllArgsConstructor @NoArgsConstructor(force = true)
@ToString
public class User {
   private final int userID;
   private String name;
   private String address;
}
```

这生成了三个构造函数。

```java
// 来自 NoArgsConstructor
public User()

// 来自 RequiredArgsConstructor
public User(int userID) 

// 来自 AllArgsConstructor
public User(int userID, String name, String address)
```

### 使用 @Log 及更多注解将日志记录器织入你的代码库

在第 5 章 “使用日志框架捕捉应用状态”中，你已经了 Java 世界中一些常见的日志框架。坦率地说，Project Lombok 为创建所有常见的日志器提供了注解，以及许多不常用的日志器甚至自定义日志器，这样你就可以直接开始记录日志，而无需用创建日志器的工厂方法来弄乱代码。

你只需通过在类上标记表 8.2 中的任意一个注解，就会自动为你创建日志器。在任何情况下，日志记录器默认会被赋值给名为 `log` 的变量。你不需要显式导入日志器；你的 IDE 会插入适当的导入。

例如，下面的代码段将使用 `Slf4j` 写入适当的消息。

```java
import lombok.extern.slf4j.Slf4j;

@Slf4j
public class Lombok {
   public static void main(String[] args) {
      log.debug("Starting");
      log.info("Hello, Words");
      log.debug("Goodbye");
   }
}
```

| 注解 | 生成的代码 |
| --- | --- |
| `@CommonsLog` | `private static final org.apache.commons.logging.Log log = org.apache.commons.logging.LogFactory.getLog(MyClass.class);` |
| `@Flogger` | `private static final com.google.common.flogger.FluentLogger log = com.google.common.flogger.FluentLogger.forEnclosingClass();` |
| `@JBossLog` | `private static final org.jboss.logging.Logger log = org.jboss.logging.Logger.getLogger(MyClass.class);` |
| `@Log` | `private static final java.util.logging.Logger log = java.util.logging.Logger.getLogger(MyClass.getName());` |
| `@Log4j` | `private static final org.apache.log4j.Logger log = org.apache.log4j.Logger.getLogger(MyClass.class);` |
| `@Log4j2` | `private static final org.apache.logging.log4j.Logger log = org.apache.logging.log4j.LogManager.getLogger(MyClass.class);` |
| `@Slf4j` | `private static final org.slf4j.Logger log = org.slf4j.LoggerFactory.getLogger(MyClass.class);` |
| `@XSlf4j` | `private static final org.slf4j.ext.XLogger log = org.slf4j.ext.XLoggerFactory.getXLogger(MyClass.class);` |
| `@CustomLog` | `private static final com.foo.your.Logger log = com.foo.your.LoggerFactory.createYourLogger(MyClass.class);` 此选项需要你在 `lombok.config` 文件中添加配置以指定 `@CustomLog` 的行为。 |

**表 8.2: Project Lombok 支持的日志注解**

`Slf4j` 是任何日志实现的封装。Lombok `@Slf4j` 注解默认使用的日志器是 Logback，但你可以通过在 `pom.xml` 或 `build.gradle` 文件中包含你偏好的日志框架的依赖来覆盖它。

此外，你可以在 `lombok.config` 文件中进行许多微调来覆盖 Lombok 的默认值。只需将 `lombok.config` 包含在 Java 源码根目录或其子目录下即可。该配置文件将适用于该目录及其子目录下的所有源文件。

例如，假设你想将默认的 `log` 变量名更改为 `logger`。你可以在 `lombok.config` 文件中指定以下配置：

```
lombok.log.fieldName=logger
```

或者考虑日志器被创建为静态的这一事实。但假设你想将它们更改为非静态，例如为了避免与同一类的不同实例产生竞争。那么你可以在 `lombok.config` 中包含以下内容：

```
lombok.log.fieldIsStatic=false
```

要查看带有描述的 `lombok.config` 配置键完整列表，请使用以下命令：

```
java -jar lombok.jar config -g ---verbose
```

或者查看 Lombok 在线文档 [`https://projectlombok.org/features/configuration`](https://projectlombok.org/features/configuration)。

# 从你的代码库中移除 Lombok (DELOMBOKING)

有时你可能想查看 Lombok 织入你类中的代码，例如当出现问题时，你想更仔细地检查问题代码。Delombok 是包含在 `lombok.jar` 中的一个工具，它会递归地“delombok”你提供的源路径中的每个 `.java` 文件，并在你提供的目录中创建一个“delomboked”版本。例如，以下是在 Windows 上如何使用它的方法：

```
java -jar .\lombok.jar delombok .\src\ -d src-no-lombok
```

在 Mac 上使用它的方法如下：

```
java -jar lombok.jar delombok src -d src-no-lombok
```



你也可以为某些 IDE 安装 Delombok 插件。例如，IntelliJ 提供了命名恰当的 Delombok 插件。安装后，可以在构建（Build）菜单中添加“Delombok Project”选项，并与你的 `src` 目录并行创建一个 `delombok` 文件夹。

## 更多参考

* [`https://projectlombok.org`](https://projectlombok.org)
  关于 Lombok 安装、特性和社区的完整指南。

## 总结

在本章中，你查看了 Project Lombok 提供的用于消除大量样板代码最重要的注解，了解了如何覆盖默认行为，并学习了如何对你的代码进行“Delombok”。还有更多的注解，以及一些配置开关可以修改你所看到的注解的行为，因此请参考优秀的 Project Lombok 文档：[`projectlombok.org`](http://projectlombok.org)。

具体来说，你学习了以下注解：

* `@Data`: 在你的字节码中注入（织入）`toString`、`equals` 和 `hashCode`，以及所有字段的 getter、所有非 final 字段的 setter，以及一个必需参数构造函数。
* `@Getter` 和 `@Setter`: 在你的字节码中织入 getter 和 setter 方法。
* `@ToString`: 根据部分或所有实例变量的值织入 `toString` 方法。
* `@EqualsAndHashCode`: 根据你喜好的部分或所有实例变量的值织入 `equals` 和 `hashCode` 方法。
* `@NoArgsConstructor`、`@RequiredArgsConstructor` 和 `@AllArgsConstructor`: 在你的字节码中织入构造函数。
* `@Log`、`@Slf4j`、`@Log4j2` 等：创建一个静态日志类变量。

# 9 使用 Java 并发处理你的应用程序

直说吧：并发是很困难的。并发之所以困难是因为人类习惯于以同步的方式进行思考。但对于高性能的用例，我们希望执行这些请求，等待所有请求完成，然后返回合并后的结果。但如果有许多线程在运行，它们在完成后如何汇合呢？一种方法是让每个线程在完成后通知主线程，但我们如何做到这一点呢？

处理这种情况的一种方法是为线程提供一个*回调方法*（callback method）。回调方法是线程完成后执行的方法。当线程数量较小时，回调方法并不糟糕，但有时你有许多线程在运行，这些线程反过来又调用更多线程，导致难以读的回调网，俗称为*回调地狱*（callback hell），但在 Java 21 出现之前，这是 Java 开发者必须接受的。

但随后 Java 21 引入了*虚拟线程*（virtual threads），整个线程子系统被重写以支持它们。传统的平台线程绑定到操作系统，而虚拟线程被挂载到和卸载自平台线程（我们称之为*载体线程*，carrier thread）以进行执行。当虚拟线程等待任何阻塞操作（例如 I/O 操作）时，Java 会将其*挂起*（parks）直到它准备就绪，然后将其从平台线程中卸载，释放它为另一个进程执行更多工作。当虚拟线程准备好继续时（例如睡眠操作完成或 I/O 套接返回了字节数据时），Java 将该虚拟线程重新挂载到可用的平台线程（可能与原始线程不同）上。这种安排极大简化了高性能线程操作的创建和管理。虚拟线程为你处理线程管理，允许你消除回调方法并以更舒适、同步的方式进行编程。

## 理解并发基础

传统上，所有线程都是平台线程，由操作系统管理。线程提供了并发执行操作的能力。当线程竞争共享资源时，复杂性就产生了。例如，想象你的应用程序接收到一个请求，假设你想发送一个请求。但如果我们每小时有数千个请求，我们需要让应用程序保持高效，就需要执行这些任务。在本章中，我们将回顾一些底层基础知识，然后是高级别的工具。

在线程中运行任务有几种方法。最少的方法是重写 `Thread` 中的 `run` 方法：

```java
new Thread() {
   @Override
   public void run() {
      doSomeWork();
   }
}.start();
```

另一种常见的方法是向线程提供一个 `Runnable` 实例（在我们的例子中 `doSomeWork()` 是一个执行某些任务的方法）：

```java
// 创建一个定义要执行任务的 Runnable：
Runnable someRunnable = new Runnable() {
   @Override
   public void run() {
      doSomeWork();
   }
};

// 将 Runnable 分配给线程并启动运行：
new Thread(someRunnable).start();
```

你可以通过将 `Runnable` 定义为 lambda 表达式来消除一些样板代码。以下代码与之前的代码等效：

```java
new Thread(()-> doSomeWork()).start();
```

一种更现代、更方便的创建和启动线程的方法是使用 Java 21 中引入的 `Thread` 类的某个工厂方法之一。这些方法使用*流式*（fluent）构建器模式来配置、启动并返回线程。

```java
Thread thread = Thread
   .ofPlatform()
   .start(() -> doSomeWork());
```

使用这种语法，你可以在一条命令中创建新线程、以 `Runnable` 函数式接口的形式提供功能（代码为 `()-> doSomeWork()`）并启动它。

你可以使用构建器语法可选地配置线程名称、线程组、守护状态、优先级等属性，如下所示：

```java
Thread thread = Thread.ofPlatform()
   .name("Some meaningful name")
   .priority(Thread.NORM_PRIORITY+1)
   .group(new ThreadGroup("Some thread group"))
   .daemon(false)
   .start(() -> doSomeWork());
```

要创建一个线程但不启动它，请使用 `.unstarted()` 代替 `.start()`。

```java
Thread thread = Thread.ofPlatform()
   .name("Some meaningful name")
   .priority(Thread.NORM_PRIORITY+1)
   .group(new ThreadGroup("Some thread group"))
   .daemon(false)
   .unstarted(() -> doSomeWork());
```

你可以以后使用 `.start()` 启动该线程。

```java
thread.start();
```

你可以使用类似的语法来启动虚拟线程，我们将在本章稍后的“介绍虚拟线程”部分中介绍这一点。

你将在后续关于 `ExecutorService` 和 `CompletableFuture` 的章节中看到其他创建和启动线程的方法。每一种都为处理常见的特殊用例提供了功能。

### 处理线程竞争

处理线程竞争的挑战通过经典的命中计数器（Hit Counter）问题说明得最好。在这个问题中，你有一个带有命中计数器的网站，每当请求进来时，计数器就应该加 1，如图 9.1

**图 9.1**: 命中计数器的正常路径

在正常路径下，一个用户请求在 Thread 1 上进入，我们更新命中计数器。假设当请求进来时，命中计数器已经达到了 34 次。它处理请求的过程如下：

*   **步骤 1**：Thread 1 用户读取命中计数器的值，看到值 = 34。
*   **步骤 2**：Thread 1 将值增加到 35。
*   **步骤 3**：Thread 1 将增加后的值写回命中计数器，现在它的值为 35。一切正常。

但现在让我们看看图 9.2 中不幸运的路径，其中 Thread 1 和 Thread 2 都在同时尝试更新命中计数器。

![示意图并排显示了三个块，分别标记为 thread 1、hit counter 和 thread 2。thread 1 和 thread 2 读取命中计数器中的值。它们在互不知道对方的情况下将值增加到 35 并写入命中计数器。该过程用箭头表示。](img/c09f002.png)

**图 9.2**: 存在竞态条件的命中计数器

*   **步骤 1**：Thread 1 读取命中计数器，看到值 = 34。
*   **步骤 2**：在 Thread 1 有机会将命中计数器更新为 35 之前，Thread 2 读取了命中计数器并看到 34。
*   **步骤 3**：Thread 1 在不知道 Thread 2 的情况下，将其 34 增加到 35。
*   **步骤 4**：正此时，Thread 2 也将它的 34 增加到 35。
*   **步骤 5**：Thread 1 将它的 35 写回命中计数器。
*   **步骤 6**：Thread 2 将它的 35 写回命中计数器。你看，两个线程都更新了命中计数器，但由于不幸的交错执行，只记录了一次命中。这可不妙。这就是所谓的*竞态条件*（race condition），我们的任务是在多线程代码中防止这种情况发生。

我们通过以下代码演示了这种竞态条件：

```java
5:  public class HitCounter {
6:     public static final int HITS = 10_000;
7:     private static int hitCounter = 0;
8:     private static AtomicInteger atomicHitCounter = new AtomicInteger(0);
9:     public static void main(String[] args) throws InterruptedException {
10:       Runnable incrementTask = () -> {
11:          for(int i = 0; i < HITS; i++) {
12:             incrementHitCounter(i);
13:          }
14:       };
15:       Thread thread1 = Thread.ofPlatform().start(incrementTask);
16:       Thread thread2 = Thread.ofPlatform().start(incrementTask);
17:       thread1.join();
18:       thread2.join();
19:
20:       System.out.println("Final hit counter value was: " + hitCounter 
21:          + ". Expected " + (2*HITS));
22:       System.out.println("Final atomic hit counter value was: " 
23:          + atomicHitCounter + ". Expected " + (2*HITS));
24:    }
25:    private static void incrementHitCounter(int i) {
26:       
27:       int temp = hitCounter;
28:       if(i % 1000==0) {
29:          System.out.println(Thread.currentThread() + " incrementing " 
30:             + temp + ". AtomicCounter:" + atomicHitCounter);
31:       }
32:       // 模拟一些延迟
33:       try {
34:          Thread.sleep(0, 1); // 小延迟
35:       } catch(InterruptedException e) {
36:          Thread.currentThread().interrupt();
37:       }
38:       hitCounter = temp + 1;
39:       atomicHitCounter.incrementAndGet();
40:    }
41: }
```

### 编写原子操作

一些规则——Java 保证所有对象的赋值和访问都是原子的，但 long 和 double 的 *get* 和 *set* 除外。这意味着当你获取或设置任何对象（如 String、List 或 Array）以及大多数基本类型时，这些操作是原子的，不会出现某个线程看到半设置的结果。

long 和 double 是例外，它们不提供此类保证。这些是 64 位值，由两个 32 位字组成。`long` 或 `double` 变量完全可能返回完全不一致的数据，如图 9.3 所示，其中 `Thread 1` 正在设置一个 64 位值 `AAAABBBB`，而 `Thread 2` 正在设置 `CCCCCDDDDD`。结果是高字中来自 `Thread 1` 的部分值 `AAAA`，低字中来自 `Thread 2` 的 `DDDD`，产生了一个任何线程都未设置过的混合值。

![一个示意图，包含三个块。块 1 中的 Thread 1 包含高、低变量，块 2 中的 thread 2 包含高、低变量。thread 1 的高变量和 thread 2 的低变量被写入块 3 中。](img/c09f003.png)

**图 9.3**: 每个线程设置变量的一半，导致了意料之外的混合结果。

### 使用 volatile 关键字

为了确保变量字段的读取者写入者是原子的，你可以将该字段声明为 `volatile`。

但 `volatile` 的意义不仅仅是原子性操作。

你会发现，操作系统为每个 CPU 核心以及每个线程分配了它们自己的内存区域。一个核心访问另一个核心的内存寄存器可能会减慢你的程序速度，因此 Java 的设计者赋予了每个线程自由，通过从“黄金源”（即官方值）读取值到其自己的本地缓存中来优化。此后，该线程可以引用该本地值，尽管在此期间另一个线程可能已经更改了黄金源。当你不担心共享访问时，这是一个极大的优化。然而，当多个线程对同一个变量进行读写操作时，你将希望确保所有线程都能从相同的位置看到相同的值。这就是 `volatile` 的工作。`volatile` 关键字告诉 Java：“这个值是 `volatile` 的（意味着‘频繁变化’）；请务必始终从主位置访问最新值。”

只要变量被标记为 `volatile`，对该变量的任何获取（gets）或设置（sets）都将来自主位置，而不是 CPU 缓存。此外（注意这里），如果任何 `volatile` 变量在任何时候对某个线程可见，那么即使是非 `volatile` 变量的任何获取或设置也将保证将从黄金源刷新。

但还有更多内容，而且这与 Java 内存模型有关。

在 Java 中，编译器和运行时都有重排（`reorder`）操作的。例如，在以下代码的第 11 行和第 12 行，`count` 和 `total` 是独立的，因此 Java 可以通过重排它们的计算并并行执行它们来优化性能。然而，第 13 行依赖于这两者，因此第 13 行必须按照定义的顺序执行。这被称为 `happens-before`（发生于）逻辑。任何给定的线程都保证看到其变量的顺序与它们发生的顺序是不可区分的。

```java
10: double value = 10.0;
11: double count = value + 1;
12: public void updateValue(double score) {
13:    double total = value + score;
14:    value = total / count;
15: }
```

然而，另一个查看这些变量的线程可能会按照它们实际计算的顺序看到它们，这可能会产生出人意的结果。

`volatile` 关键字在这方面也有帮助。当你将一个变量标记为 `volatile` 时，你确保了对该线程可见的所有变量都将被所有线程按照它们指定的顺序被看到。这被称为 `happens-before` 语义。将之前的代码更改为如下内容可以确保所有线程按照接收到的顺序看到变量：

```java
10: volatile double value = 10.0;
11: volatile double count = value + 1;
12: public void updateValue(double score) {
13:    double total = value + score;
14:    value = total / count;
15: }
```



### 线程状态的转换

线程始终与后续章节描述的线程状态相关。阅读本节时，请参考图 9.4。

#### NEW
`NEW` 用于已初始化但尚未启动的线程。

#### RUNNABLE
`RUNNABLE` 是线程正在运行或能够在处理器释放资源后立即运行的线程状态。当调用 `start()` 时，线程从 `NEW` 转换到 `RUNNABLE`。同样，当线程不再处于等待或阻塞状态时，它会变回 `RUNNABLE`，为下一次运行做准备。

#### BLOCKED
`BLOCKED` 是线程等待共享锁以进入或重新进入 `synchronized` 块/方法的线程状态，你将在下一节中看到它。

#### WAITING
`WAITING` 是线程等待共享锁的线程状态。线程会调用 `wait()` 或 `join()`（不带超时）进入 `WAITING` 状态。

#### TIMED_WAITING
`TIMED_WAITING` 是等待指定时间通过的线程状态。线程会调用 `sleep(long)`、`join(long)` 或带有超时时间的 `wait(long)` 进入 `TIMED_WAITING` 状态。

#### TERMINATED
`TERMINATED` 是线程执行完毕的线程状态。

#### 总结线程状态
总结来说，如果线程尚未启动，则为 `NEW`；一旦启动，就是 `RUNNABLE`。如果它尝试进入一个由另一个线程拥有的同步块，它将进入 `BLOCKED` 状态；如果它调用了 `wait()`，它进入 `WAITING` 状态；如果它调用了 `wait(long)` 或 `sleep(long)`，它将进入 `TIMED_WAITING` 状态。

一旦等待线程被另一个线程通知，它将转换到 `BLOCKED` 状态，直到锁的所有者退出同步块并释放锁，此时线程调度器会随机选择另一个等待线程变为 `RUNNABLE` 并进入代码块。

如果你在面试中遇到“阻塞线程和等待线程的区别是什么？”的问题，一个答案是除了另一个线程释放锁之外，没有办法停止阻塞线程。另一个答案是，等待线程会抛出一个你必须捕获（或在方法签名中抛出）的 `InterruptedException`，而阻塞线程不会声明该异常，因为它无法。

### 同步
作为防止竞态条件的辅助手段，Java 允许在代码块之前调用 `synchronized(someObject)`。该代码块将只允许一个线程获取锁实例。事实上，任何以这种方式锁定的代码块将阻止除所有线程外的其他线程访问。任何等待线程将处于 `BLOCKED` 状态，并在锁的所有者退出同步块释放锁后才能继续执行。

有一个例外。当线程处于 `synchronized` 块中时，它可以对锁调用 `wait`。当该线程处于 `WAITING` 状态（如果它调用了 `someObject.wait(long)`，则处于 `TIMED_WAITING` 状态）时，另一个线程可以进入锁定同一个锁实例的 `synchronized` 块。通过这种方式，许多线程可以获取同一个锁实例并在锁上调用 `wait`，实际上所有线程都在同一个锁上等待。最后，另一个线程可以通过 `synchronized(someObject)` 获取 `someObject` 锁，然后调用 `someObject.notify()` 来唤醒一个随机线程，或调用 `someObject.notifyAll()` 来唤醒所有等待的线程。嗯，现在会有许多线程拥有同一个锁吗？并不是。被“唤醒”的线程实际上会转换到 `BLOCKED` 状态，并等待 `RUNNING` 线程退出 `synchronized` 块以释放锁，此时，线程调度器将选择一个等待线程并将其转换为 `RUNNING` 状态。

通过这种方式，你可以让一个线程设置某些状态然后调用 `notifyAll()` 并退出 `synchronized` 块。然后，所有等待的线程将获得机会唤醒、检查状态并采取相应的行动，或者返回等待。首先，假设你有一个对象用于锁定：

```java
final Object lock = new Object(); // 可以是任何类类型
```

以下是进入 `WAITING` 状态的语法：

```java
synchronized(lock) {
   lock.wait();
}
```

以下是线程通知一个 `WAITING` 线程唤醒的语法：

```java
synchronized(lock){
   lock.notify();
}
```

以下是线程通知所有 `WAITING` 线程唤醒的语法。请记住，只有一个线程可以在 `RUNNING` 状态下处于同步块中，因此线程调度器将按随机顺序唤醒每个等待的线程。

```java
synchronized(lock){
   lock.notifyAll();
}
```

有两种不同的同步语法。首先，我们同步整个方法：

```java
public synchronized void someMethod(){
   // ... 执行一些操作 ...
}
```

接下来，我们对一个对象进行同步：

```java
private final Object LOCK = new Object();

public void someMethod(){
   // ... 执行一些操作 ...
   synchronized(LOCK){
      // ... 执行更多操作，此块受保护
   }
}
```

当你同步一个方法时，你是在包含该方法的对象实例上进行同步。

当然，`Object` 类是所有其他类的祖先。这些线程间通信方法定义在 `Object` 类中：

- `wait(time)` 其中 `time` 是一个 `long`
- `wait(time,nanos)` 其中 `time` 是 `long` 且 `nanos` 是 `int`
- `notify()`
- `notifyAll()`

`synchronized` 的缺点是，当一个 `RUNNABLE` 线程拥有同步锁时，任何尝试获取相同锁的线程都将被阻塞，即被强制等待，且没有好的方法可以取消它。当我们查看一些高级别的并发组件（如 `ReentrantLock`）时，我们将看到可以取消的锁的方法。

### 探索堆、栈和元空间（Metaspace）

在 Java 中，内存被分为三个主要区域：堆（heap）、栈（stack）和元空间（Metaspace）。

`heap` 是一个非常大的内存块，所有对象都分配在其中。在 Java 的早期版本中，Strings 会分配在“PermGen”区域中且永远不会被垃圾回收。然而，在现代 Java 版本中，Strings 分配在字符串池中，字符串池位于堆上，当所有引用都被移除时，它们就可以被垃圾回收。

`stack` 是与线程关联的后进先出数据结构。当线程执行一个方法时，每当在该方法中进行赋值，该方法中的变量就会推入栈中。如果方法调用了更深层的方法，那么深层的方法将将其变量推入栈中。当深层方法返回时，与该方法相关的栈变量将从栈中弹出。

当调用方法时，方法中创建的任何非原始值都分配在堆上，栈将包含指向堆上该对象的指针。当方法退出时，引用将从栈中弹出，但它所指的实例将留在堆上，直到它被垃圾回收。

`Metaspace` 是如果对象的生命周期需要与 VM 生命周期一致时存放的地方。例如，类对象和静态引用永远不会被垃圾回收，因此它们在元空间中创建。

## 介绍并发集合

Java 的标准数据结构（如 `HashMap`、`ArrayList` 等）在并发使用下的表现并不一定良好。例如，如果一个线程在迭代 `HashMap` 的同时另一个线程正在更新它，读取器将抛出 `ConcurrentModificationException`。

`ConcurrentHashMap` 是一个线程安全的 `Map` 实现，允许并发读取和写入者。它实现了 `ConcurrentMap` 接口，该接口具有与 `Map` 接口相同的方法，但默认方法的实现有所不同。因此，你可以像使用 `HashMap` 一样完全使用 `put()`、`get()`、`computeIfAbsent()` 等，不同之处是，当有许多并发读取和写入线程时，它的表现非常良好。

`BlockingQueue` 作用类似于任何后进先出的队列，但一旦达到容量，放入数据的线程（putter threads）将被阻塞，而如果没有条目，获取线程（getter threads）将被阻塞。要向队列中插入数据，可以调用 `add(data)`，如果队列满了将抛出 `IllegalStateException`。同样，`offer(data)` 会插入数据并在空间可用时返回 true。`put(data)` 方法将等待空间可用。要从队列获取数据，请使用相应的访问器：`remove()`，如果没有可用数据则抛出 `IllegalStateException`；`poll(long, TimeUnit)` 在必要时等待指定的时间并返回头部；以及 `take()`，移除头部并无限等待直到数据可用。

`ConcurrentSkipListMap` 是另一个由跳表（Skip List）数据结构支持的 `ConcurrentMap` 实现。跳表使用有趣的算法来查找所需数据（参见“引用”部分）。

`CopyOnWriteArrayList` 是一种并发 `List`，其工作原理是确保写入者在原始数组的副本上写入，在写入操作完成之前不会返回给读取者，之后原始会被丢弃。它实现了 `List` 接口，因此你可以像使用任何 `List` 实现一样使用 `add(data)`、`get()` 等。

## 在 Java Stream 中内置并发支持

对于处理集合的数据流，Java 提供了 `parallelStream()` 方法。这与 `stream()` 方法相似，不同在于它将底层集合拆分成更小的块并进行并发处理，然后将生成的线程合并以产生单个结果。

例如，以下代码使用并行流将输入列表中的单词转换为大写。然而，我们对结果 `List` 不太感兴趣，而对处理每个片段的线程更感兴趣。

```java
List<String> words = List.of("It", "was", "the", "best", "of", "times",
   "it", "was", "the", "worst", "of", "times");

List<String> collect = words.parallelStream().peek(name -> {
   try {
      System.out.println("Thread: " + Thread.currentThread().getName()
      + " processing: " + name);
      Thread.sleep(100);
   } catch(InterruptedException e) {
      throw new RuntimeException(e);
   }
}).map(String::toUpperCase).toList();

System.out.println(collect);
```

这段代码显示如下：

```
Thread: main processing: was
Thread: ForkJoinPool.commonPool-worker-1 processing: best
Thread: ForkJoinPool.commonPool-worker-4 processing: it
Thread: ForkJoinPool.commonPool-worker-2 processing: of
Thread: ForkJoinPool.commonPool-worker-5 processing: times
Thread: ForkJoinPool.commonPool-worker-3 processing: was
Thread: ForkJoinPool.commonPool-worker-6 processing: of
Thread: ForkJoinPool.commonPool-worker-7 processing: It
Thread: main processing: the
Thread: ForkJoinPool.commonPool-worker-1 processing: worst
Thread: ForkJoinPool.commonPool-worker-2 processing: times
Thread: ForkJoinPool.commonPool-worker-3 processing: the
[IT, WAS, THE, BEST, OF, TIMES, IT, WAS, THE, WORST, OF, TIMES]
```



你可以从列表中看到，有八个线程用于处理此请求：`worker-1` 到 `worker-7` 以及主线程。这八个线程对应于该机器上的核心数量。

## 使用并发组件降低复杂性

Java 为许多常见的并发用例提供了高层组件，使得并发编程变得更容易上手。在本节中，我们将介绍几个常用的组件，包括：

* `ReentrantLock`
* `Phaser`
* `Runnable`、`Callable` 和 `Future`
* `ExecutorService`
* `CompletableFuture`
* 虚拟线程（Virtual threads）

我们将首先介绍这些概念，并在章节的后半部分查看一些代码示例。

### 使用 ReentrantLock 锁

`ReentrantLock` 提供了一个组件化的同步方案，解决了与同步相关的一些挑战。在使用虚拟线程时，它也至关重要，正如你在“介绍虚拟线程”部分中看到的。

`ReentrantLock` 实现了 `Lock` 接口，该接口包含以下方法：

* `void lock()`：请求锁，如有必要则等待锁变为可用。
* `void lockInterruptibly()`：行为与 `lock()` 类似，但如果另一个线程在请求线程等待时中断它，它将抛出 `InterruptedException` 并取消对锁的请求。
* `boolean tryLock()`：获取锁，如果锁可用则返回 `true`。否则返回 `false`。
* `tryLock(long, TimeUnit)`：行为与 `tryLock()` 相同，但在等待指定时间后会取消对锁的请求。
* `void unlock()`：释放锁。
* `Condition newCondition()`：允许对线程通信进行更细粒度的控制。

`Condition` 有自己的 API，与 `Lock` 协同工作。最常用的有：

* `void await()`：等待当前线程被唤醒或中断。
* `void signal()`：唤醒等待此锁的线程。在运行的线程释放锁之前，该线程不会真正唤醒。
* `void signalAll()`：唤醒所有等待的线程。这些线程不会立即唤醒；相反，它们必须等待运行的线程释放锁，即使如此，它们也会在每个线程释放锁时一个一个唤醒。

你可能记得我们之前提到过，如果一个线程尝试获取一个被另一个线程持有的同步锁（synchronized lock），没有办法让被阻塞的线程退回。从方法签名可以清楚看出——它不会抛出 `InterruptedException`，因此没有方法中断它！

`ReentrantLock` 通过提供 `lockInterruptibly()` 方法解决了这个问题，该方法会抛出 `InterruptedException`。如果你在一个正在等待 `lockInterruptibly()` 用的线程上调用 `interrupt()`，它会被中断并退回。

`ReentrantLock` 还解决了 `synchronized` 块的另一个问题。如果你有许多线程在同一个同步锁上等待，假设你想根据某些条件（例如集合为空）唤醒其中一个，并根据其他条件（例如集合已满）唤醒另一个。使用 `synchronized` 锁，你需要调用 `notifyAll()` 来唤醒这两个线程，并让它们都去检查自己的条件。

`ReentrantLock` 通过 `newCondition()` 方法提供了更好的解决方案。当一个线程锁住一个 `ReentrantLock` 时，它可以在该锁上调用 `newCondition()`。许多线程可以执行相同的操作。

然后，当某个检测器观察到某个条件并想要信号某个特定线程来处理该条件时，它只需要调用 `condition.signal()`，只有等待该条件的线程会被唤醒。我们将在本章后的 `PingNetPong` 代码中看到这个示例。

### 使用 Phaser 控制线程访问

在学习 `Phaser` 之前，我们简简要提到两个旧的 API：`CyclicBarrier` 和 `CountdownLatch`。

`CyclicBarrier` 用于你有多个线程需要执行一个函数，然后等待所有其他线程都就绪。就像来到起跑线的马一样，在所有马到达之前，比赛无法开始。

`CountdownLatch` 类似，不同之处在于有一组一个或多个线程在等待另一组线程完成后再开始。一个例子可能是一个在所有缓存填充之前无法提供请求服务的网站。有许多线程正在填充缓存，网站必须等待所有线程完成才能开始处理请求。

我们不会深入探讨这些 API，因为 `Phaser` 结合了这些功能。你通过提供数量许可（permits）来创建一个 `Phaser`。你可以通过调用 `arriveAndAwait()` 使用 `Phaser` 代替 `CyclicBarrier`。注意 `awaitAdvance` 中的参数指的是阶段（phase）。Phaser 可以重用，每当它耗尽许可时，就会启动一个新的阶段。

我们将在本章后的 `PingNetPong` 代码中使用 `Phaser` 作为倒计时计数器。

### 使用 Runnable, Callable 和 Future

在构建并发应用程序时，有三个重要的接口可以使用：`Runnable`、`Callable` 和 `Future`。

我们在本章早期已经讨论过 `Runnable`。`Runnable` 是原始的 Java 接口，你通过实现 `run` 方法来定义线程执行的功能。`Runnable` 的局限性在于它不返回任何结果，也不声明任何异常。

`Callable` 的后期引入是为了弥补这些缺陷。`Callable` 有一个 `call` 方法，可以返回泛型结果并抛出异常。

但如果线程是异步执行的，启动线程的进程如何获取它产生的任何结果？一种干净的方法是通过 `Future` 接口。`Future` 提供了检查计算是否完成以及获取结果的方法。它还具有强制 future 在带或不带异常的情况下完成的方法。

| `TimeUnit unit)` | 可以告诉线程将其结果返回给 `Future`，其他线程将等待该结果。 |
| --- | --- |

表 9.1: 并发接口

根据我们描述的内容，`Future` 似乎是一个非常有用的结构，但我们如何获取它呢？一种方法是向 `ExecutorService` *提交*一个 `Runnable` 或 `Callable`。

### 与 ExecutorService 协作

`ExecutorService` 是一个用于创建和管理线程池的接口。它扩展了 `Executor` 接口，该接口只有一个 `execute()` 命令。有多种类型的 `ExecutorService`，最常见的是用于创建固定大小线程池、创建调度线程池以及创建虚拟线程的实现。它提供了许多方法，用于作为 `Future` 获取结果、等待所有线程终止，以及在所有线程完成之后（甚至在此之前）强制关闭。

`ExecutorService` 实例通常使用 `Executors` 类中的 `static` 工厂方法来创建。让我们看看如何使用最常用的 `ExecutorService`，即固定线程池 `ThreadPoolExecutor`。然后，我们将访问其他一些 `ExecutorService` 实现，它们具有相似的 API 但语义略有不同。

#### 使用固定数量线程池

平台线程的创建相对昂贵，并且会占用堆内存空间，因此如果能创建一次线程并保留它们以便复用，那就太棒了。此外，线程过多可能会导致系统资源饥饿，因此限制应用程序创建的线程数量也是很有用的。这就是固定 `ThreadPoolExecutor` 的目的；它创建固定数量的线程，然后将这些线程分配用于运行你的任务。如果所有线程都在忙，后续对 `ExecutorService` 的调用将导致调用者等待，直到线程被释放或等待超时。

要创建一个固定 `ThreadPoolExecutor`，请传入线程数，如下：

```
ExecutorService executor = Executors.newFixedThreadPool(10);
```

使用 `ExecutorService` 执行线程本质上有三种方法。你可以调用 `execute(Runnable)`，它返回 `void`。或者你可以调用 `submit(Runnable r)` 或 `submit(Callable c)`，它们返回一个 `Future`。或者，你可以调用其中一个 `invoke` 方法，它们接受 `Callable` 实例集合。`invokeAll()` 返回 `Future` 实例的 `List`，而 `invokeAny()` 则一直等待到可用值然后返回该值（而不是 `Future`）。

`ExecutorService` 接口扩展了 `AutoCloseable`，因此可以使用 try-with-resources 块来创建它。一旦所有活动线程已返回线程池，且线程池中没有线程等待可用线程，`ExecutorService` 就会终止，try-with-resources 块也将退出。因此实际上，try-with-resources 确保了所有线程在继续执行之前都会完成。

`Executors.newSingleThreadExecutor()` 返回一个仅包含一个线程的线程池。这相当于调用带有一个线程的 `Executors.newThreadPoolExecutor(1)`。我们需要为它创建一个特殊的执行器，而不是直接创建一个只有一个线程的固定 `ThreadPoolExecutor` 呢？因为它保证了顺序，这在你需要确保任务按顺序执行时非常有用，例如在控制按钮按下等事件的 UI 事件分发线程中。此外，更重要的是，如果这些线程之一在执行期间由于某些异常而终止，将创建一个新线程来取代它。

#### 使用 ExecutorService 进行调度

`ScheduledExecutorService` 是 `ExecutorService` 的扩展，它可以调度任务按固定的间隔执行一次或多次。`schedule()` 方法接受一个 `Runnable` 或 `Callable`，以及一个初始延迟。`scheduleAtFixedRate()` 方法接受一个 `Runnable`、初始延迟（可以为 0）、重复延迟周期和一个 `TimeUnit` 实例。所有这些方法都返回一个 `ScheduledFuture` 实例。在 `scheduleAtFixedRate()` 方法的情况下，`ScheduledFuture` 不返回任何有用信息，但你可以调用它的 `cancel()` 方法来取消调度的任务。

要创建一个 `ScheduledThreadPoolExecutor`，请传入池大小，如下：

```
ScheduledExecutorService executor = Executors.newScheduledThreadPool(10);
```

还有一个单线程版本：

```
ScheduledExecutorService executor = 
   Executors.newSingleThreadScheduledExecutor();
```

每个任务一个虚拟线程执行器是一种特殊的执行器，它在虚拟线程上运行其任务。（目前将虚拟线程看作普通线程即可，只是轻量得多。）

为虚拟线程创建 `ExecutorService` 与创建任何其他 `ExecutorService` 一样简单。只需调用此：

```
ExecutorService executor = Executors. newVirtualThreadPerTaskExecutor();
```

该方法不接受池大小参数，因为正如我们所说，我们从不池化虚拟线程。

虚拟线程没有调度执行器，但通过向 `newScheduledThreadPool()` 方法提供一个虚拟 `ThreadFactory`（一个可选参数），可以轻松地拼凑出一个：

```
ThreadFactory factory = Thread.ofVirtual().factory();
ScheduledExecutorService x = Executors.newScheduledThreadPool(2, factory);
AtomicInteger counter = new AtomicInteger(0);
x.scheduleAtFixedRate(()-> logger.info(counter.incrementAndGet()),
   0, 1, TimeUnit.SECONDS);
```

你通常需要小心将调度执行器放在 try-with-resources 块中，因为该块一旦任务启动就会退出，从而终止执行器。

### 使用 CompletableFuture 构建响应式代码

`CompletableFuture` 是一个方便的并发工具，可以启动线程、组合线程结果以及后续操作。

#### CompletableFuture 使用的函数接口

`CompletableFuture` 使用了几个你希望熟悉的函数接口。这些接口名称可能并不直观，因此在深入研究 `CompletableFuture` 版本之前，让我们先回顾它们的同步示例。

本节的所有示例在章节仓库的 `FunctionalInterfaceTests` 类中都有对应的测试器。注意我们使用 Lambda 表达式来定义这些实现。

##### Runnable 接口

*   类名：`java.lang.Runnable`
*   方法：`void run()`
*   无参数且不返回结果；`Runnable` 通常提供供给 `Thread` 的功能。

##### Supplier<T> 接口

*   类名：`java.util.function.Supplier`
*   方法：`T get()`
*   无参数，执行某些过程并产生结果。例如，这段代码定义了一个产生 100 到 200 之间随机整数的 `Supplier`。

```
@Test
public void testSupplierGet(){
   Random random = new Random();
   // 创建一个 100 到 200 之间随机整数的 Supplier
   Supplier<Integer> random100To200 = () -> random.nextInt(100,200);
   for(int i =0; i < 5; i++){
      Integer value = random100To200.get();
      System.out.println("Next random: " + value);
   }
}
```

运行之前的代码时，它输出了以下内容（由于生成值是随机的，你的结果会有不同）：

```
Next random:118
Next random:194
Next random:153
Next random:165
Next random:182
```

这里重要的是，我们的 `Supplier` 不接受输入参数并返回值。

##### Consumer<T> 接口

*   类名：`java.util.function.Consumer`
*   方法：`void accept(T t)`
*   接受单个参数；不返回结果。例如，这段代码定义了一个接受可变 Integer 列表的 `Consumer`，并在原地将每个值翻倍：

```
@Test
public void testConsumerAccept(){
   // 定义一个 Consumer，接收一个可变的 Integer 列表，
   //并将每个值替换为其值的两倍
   Consumer<List<Integer>> twoTimes = 
      list-> list.replaceAll(value -> value * 2);
   List<Integer> ints = new ArrayList<>(List.of(10, 20, 30, 40));
   twoTimes.accept(ints);
   System.out.println(ints);
}
```

之前的代码将打印此：

```
[20, 40, 60, 80]
```

这里需要注意的是的是，我们的 `Consumer` 接受一个输入参数但没有返回值；它只是在原地修改了输入。`Consumer` 的其他用途可能是打印计算结果或将结果存储到数据库中，而实际上并不向调用者返回任何内容。

有时，你可能想要链式调用多个 `Consumer`，以便在同一个输入上执行多个操作。`Consumer` 支持 `andThen(Consumer after)` 方法，该方法会产生一个新的 `Consumer`，它先执行第一个动作，然后执行 `after` 动作。例如：

```
@Test
public void testConsumerAndThen() {
   // printMessage Consumer 打印提供的值
   Consumer<String> printMessage = message ->
      System.out.println("Message: " + message);
   // upperCaseMessage Consumer 将提供的值转换为大写
   Consumer<String> uppercaseMessage = message ->
      System.out.println("Uppercase: " + message.toUpperCase());
   // printAndUppercase 使用 andThen 链式调用两个 consumers
   // 以产生一个新的 consumer
   Consumer<String> printAndUppercase = printMessage.andThen(uppercaseMessage);
   // 将链式 consumer 应用于消息
   printAndUppercase.accept("Hello, World! ");
}
```

运行之前的代码将打印此：



## Message

`Hello, World!`

## Uppercase

`HELLO, WORLD!`

## 接口：`Function<T, R>`

`T` 是参数类型；`R` 是返回类型。

- 包：`java.util.function.Function`
- 结合了 `Supplier` 和 `Consumer`；接受一个输入并返回一个结果。它包含额外的方法用于链式调用多个 `Function` 以产生一个新的 `Function`。例如，让我们定义一个接受 `Integer` 值并将其翻倍的函数：

```java
@Test
public void testFunctionApply() {
   // SquareIt 函数对提供的值值平方
   Function<Integer, Integer> SquareIt = value -> value * value;

   for (int i = 1; i <= 5; i++) {
      System.out.println("2^" + i + " = " + SquareIt.apply(i));
   }
}
```

执行之前的代码将打印此：

```text
2¹ = 1
2² = 4
2³ = 9
2⁴ = 16
2⁵ = 25
```

`andThen` 方法用于根据两个现有的函数组合新函数。在下面的示例中，我们定义了一个名为 `personToFullName` 的 `Function`。然后我们使用 `personToFullName` 的 `andThen` 与 `String` 的 `toUpperCase()` 组合成一个新的 `Function`。当这个新组合的函数被调用时，它会将人员实例转换为其全名的大写值。

```java
@Test
public void testFunctionAndThen() {
   // 创建一个简单的 Person 类。一个 record 根据构造函数参数
   // 定义了一个不可变类。
   record Person(String firstName, String lastName) { }

   // Function 接受 Person 作为输入并产生表示
   // 其全名的 String
   Function<Person, String> personToFullName = (Person p) ->
      p.firstName + " " + p.lastName;

   // 组合 Function，返回大写的写的全名
   Function<Person, String> personToUpperCaseFullName =
      personToFullName.andThen(String::toUpperCase);

   // 创建一个新的 Person 对象
   Person person = new Person("Mary", "Jones");

   // 应用链式函数
   String upperCaseFullName = personToUpperCaseFullName.apply(person);

   // 打印结果
   System.out.println(upperCaseFullName);
}
```

执行之前的代码将打印此：

```text
MARY JONES
```

我们只是想再次强调，调用 `andThen` 方法的函数声明（在此例中为 `personToUpperCaseFullName`）并没有对输入参数执行任何操作。相反，它组合了一个新的 `Function`，该函数在应用于其输入参数时，会执行基础函数（在我们的例子中为 `personToFullName`），然后将该调用的结果传递给 `andThen` 函数（在我们的例子中为 `String` 类的 `toUpperCase` 函数）。

类似于 `andThen` 有 `compose` 方法，它的工作方式与 `andThen` 仅相反；使用 `compose`，函数参数先被应用，然后是基础函数。例如，我们可以使用 `compose` 如下重写之前的 `andThen` 代码：

```java
@Test
public void testFunctionCompose() {
   record Person(String firstName, String lastName) { }

   // Function 接受 Person 作为输入并产生表示
   // 其全名的 String
   Function<Person, String> personToFullName = (Person p) ->
      p.firstName + " " + p.lastName;

   // 组合 Function，返回大写的全名
   Function<String, String> toUpperCase = String::toUpperCase;

   Function<Person, String> personToUpperCaseFullName =
      toUpperCase.compose(personToFullName);

   // 创建一个新的 Person 对象
   Person person = new Person("Mary", "Jones");

   // 应用链式函数
   String upperCaseFullName = personToUpperCaseFullName.apply(person);

   // 打印结果
   System.out.println(upperCaseFullName);
}
```

## 接口：`BiFunction<T, U, R>`

`T` 和 `U` 是参数类型；`R` 是返回类型。

- 包：`java.util.function.BiFunction`
- 接受两个输入并返回一个结果。例如，让我们定义一个 `BiFunction`，它接受直角三角形的两边（`a` 和 `b`）并使用勾股定理计算第三边（`c`）。

```java
@Test
public void testBiFunction() {
   BiFunction<Double, Double, Double> Hypotenuse =
      (a, b) -> Math.sqrt(a * a + b * b);

   Double c;

   c = Hypotenuse.apply(3.0, 4.0);
   System.out.println(c); // 输出 5.0

   // 因为 3,4,5 是勾股三角形
   c = Hypotenuse.apply(5.0, 12.0);
   System.out.println(c); // 输出 13.0

   // 因为 5,12,13 是勾股三角形
}
```

## `CompletionStage`

`CompletableFuture` 实现了 `CompletionStage` 接口，该接口包含了用于供应和链式调用异步计算的方法。

### `CompletionStage` 方法包括

- `thenAccept(Consumer)`
- `thenApply(Function)`
- `thenRun(Runnable)`
- `thenCompose(Function, CompletionStage)`
- `thenCombine(CompletionStage, BiFunction)`

这些是同步形式，每个都有异步版本，例如 `thenAcceptAsync()` 和 `thenApplyAsync()`。

## 使用 `CompletableFuture` 整合一切

`CompletableFuture` 是 Java 对响应式代码的首次原生尝试。响应式代码意味着异步运行但通过信号另一个进程已完成来立即做出反应，从而通知该进程处理结果。

在下面的代码中，第 15 行是使用 `CompletableFuture.supplyAsync()` 方法启动并发的标准方法，该方法接受一个 `Supplier` 实例。回想之前关于 `Supplier` 接口的章节，`Supplier` 不接受参数并产生结果。使用 Java 线程，没有方法可以询问线程在完成后提供结果；相反，你必须自己实现一种信号机制。`CompletableFuture` 解决了这个问题。正如你在第 46 行所示，当线程调用 `completableFuture.get()` 方法时，线程将等待直到结果计算完毕然后立即获取结果。

你会注意到我们没有需要创建或启动 `Thread` 实例，也没有需要提供 `ExecutorService`。相反，`CompletableFuture` 在后台为我们完成了这一切。

接下来，我们想告诉 `CompletableFuture`，一旦它计算出结果，就应该接受（`thenAccept()`）一个 `Consumer`。记住，`Consumer` 接口接受一个参数，执行一个过程并且不返回结果。这对于我们的情况非常完美，因为我们只需要打印某些内容，而不是返回任何内容。

现在，如果我们希望在继续执行之前等待 `thenAccept()` 完成，可以将 `thenAccept()` 赋值给新的 `CompletableFuture` 实例。在之前显示的第一个 `CompletableFuture` 中，我们调用了 `get()` 方法来等待结果，直到结果就绪。我们不能在 `thenAccept()` 的 `CompletableFuture` 上调用 `get()`，因为它是一个 `Consumer`，所以它不产生任何结果。对于此类情况，你可以调用 `completableFuture.join()`，它将等待直到消费者完成处理而无需期望任何结果。

```java
7:  @Log4j2
8:  public class CompletableFutureTests {
9:     @Test
10:    public void testCompletableFutureThenAccept() {
11:       try {
12:          // 创建一个 CompletableFuture，在延迟后
13:          // 完成结果
14:          CompletableFuture<String> future1 =
15:             CompletableFuture.supplyAsync(() -> {
16:             try {
17:                log.info("supplyAsync called");
18:                // 模拟耗时计算
19:                Thread.sleep(5_000);
20:                log.info("supplyAsync complete");
21:                return "Hello";
22:             } catch (InterruptedException e) {
23:                throw new RuntimeException(e);
24:             }
25:          });

26:          // 为 CompletableFuture 挂载 thenAccept 回调
27:          CompletableFuture<Void> future2 = future1.thenAccept(result -> {
28:             log.info("Computation complete. thenAccept sees result:" +
29:                " " + result);
30:             log.info("thenAccept performing another operation. " +
31:                "Result: " + (result + ", World"));
32:             try {
33:                log.info("thenAccept sleeping");
34:                Thread.sleep(5_000);
35:                log.info("thenAccept waking");
36:             } catch (InterruptedException e) {
37:                throw new RuntimeException(e);
38:             }
39:          });

40:          // 在 CompletableFuture 运行时执行其他工作
41:          log.info("Main thread continuing with other work…");

42:          // 等待 CompletableFuture 完成
43:          String result1 = future1.get();
44:          log.info("CompletableFuture #1 is complete. Result:" + result1);
45:          future2.join();
46:          log.info("CompletableFuture #2 is complete.");
47:       } catch (InterruptedException e) {
48:          Thread.currentThread().interrupt();
49:       } catch (ExecutionException e) {
50:          throw new RuntimeException(e);
51:       }
52:    }
53: }
```

这里是输出结果。注意每次调用的时间。

```text
2024-07-23 17:35:31 [main]
   INFO  c.w.r.c.C - Main thread continuing with other work…

2024-07-23 17:35:31 [ForkJoinPool.commonPool-worker-1]
   INFO  c.w.r.c.C - supplyAsync called

2024-07-23 17:35:36 [ForkJoinPool.commonPool-worker-1]
   INFO  c.w.r.c.C - supplyAsync complete

2024-07-23 17:35:36 [main]
   INFO  c.w.r.c.C - CompletableFuture #1 is complete. Result:Hello

2024-07-23 17:35:36 [ForkJoinPool.commonPool-worker-1]
   INFO  c.w.r.c.C - Computation complete. thenAccept sees result: Hello

2024-07-23 17:35:36 [ForkJoinPool.commonPool-worker-1]
   INFO  c.w.r.c.C - thenAccept performing another operation.
   Result: Hello, World

2024-07-23 17:35:36 [ForkJoinPool.commonPool-worker-1]
   INFO  c.w.r.c.C - thenAccept sleeping

2024-07-23 17:35:41 [ForkJoinPool.commonPool-worker-1]
   INFO  c.w.r.c.C - thenAccept waking

2024-07-23 17:35:41 [main]
   INFO  c.w.r.c.C - CompletableFuture #2 is complete.
```

当虚拟线程执行时，它在后台会被分配到一个平台线程（platform thread）。你可以在图 9.6 第 590 行看到，当它被挂起时会调用 `sleepNanos()`，这基本上告诉线程调度器将其挂起（即从载体线程上卸载），然后取消挂起；即将其分配给 JVM 线程池中可用的平台线程。因此，单个平台线程可以执行许多虚拟线程。

如果写一些代码创建一些线程，让它们唤醒和睡眠几次，并每次捕获它们的载体线程以观察它们的变化，将会非常有趣。

让我们写一些示例代码来实现这一目标。

```java
13: @Slf4j
14: public class VirtualThreadStatesTests {
15:    private final Map<String, Set<String>> carrierMappings
16:       = new ConcurrentHashMap<>();

18:    @Test
19:    public void getCarriers() {
20:       // 一些线程，让它们每个旋转百万次
21:       // 次，并将载体收集到 map 中。
22:       // 然后睡眠一会儿以查看载体的卸载。
23:       // 重复几次并捕获结果。
24:       int threadCount = 4;
25:       // 增加一个 AtomicInteger，仅为了
26:       // 线程可以完成某些操作
27:       AtomicInteger atomicInteger = new AtomicInteger();
```



28:       try(`ExecutorService executorService`

29:          = `Executors.newVirtualThreadPerTaskExecutor()`){
30:          for(int i = 0; i < threadCount; i++){
31:             `executorService.submit(() -> {`
32:                // 获取此虚拟线程的 ID 用于映射
33:                `Thread current = Thread.currentThread();`
34:                `String virtualID = ThreadUtils.getVirtual(current);`
35:                // 运行然后睡眠，几次
36:                for(int loopCount = 0; loopCount < 10; loopCount++){
37: // 注消以同步，显示锁定（pinning）
38: //                `synchronized(this)`
39:                   {
40:                      `String carrierID = ThreadUtils.getCarrier(current);`
41:                      `Set<String> carriers =`
42:                         `carrierMappings.computeIfAbsent(`
43:                          `virtualID, x -> new HashSet<>());`
44:                      `carriers.add(carrierID);`
45:                      for(int j = 0; j < 1_000_000; j++){
46:                         `atomicInteger.incrementAndGet();`
47:                      }
48:                      try{
49:                         // 短暂进入阻塞状态，
50:                         // 并看看我们唤醒时会发生什么
51:                         `Thread.sleep(10);`
52:                      } catch(`InterruptedException e`){
53:                         `current.interrupt();`
54:                      }
55:                   }
56:                }
57:             });
58:          }
59:       }
60: 
61:       // 随时间打印所有虚拟线程和所有载体的摘要
62:       `log.info("\n\nSummary");`
63:       `carrierMappings.forEach((key, value) -> {`
64:          `log.info(key + ": Carriers:");`
65:          `value.forEach(log::info);`
66:          // 在虚拟线程之间留一个空行
67:          `System.out.println();`
68:       });
69:    }
70: }

```

在这个示例中，我们创建了四个虚拟线程（第 30 行）。每个线程循环 10 次（第 36 行），每次向 map 中添加一个条目，该条目捕获当时映射该虚拟线程（第 40–44 行），然后执行一些工作（第 45–47 行）并睡眠（第 51 行）。最后，当所有线程完成后，try-with-resources 块退出，它将显示每个虚拟线程的名称以及在该程序运行期间承载该虚拟线程的所有载体线程名称（第 61–68 行）。

该程序的输出显示了每个虚拟线程的 ID，随后是承载它的平台线程列表。你可以看到过程中有四个平台线程，每个虚拟线程在其生命周期内都被三个或四个平台线程承载：

```
Summary

2024-07-23 18:14:59 [main]

   INFO  c.w.r.c.VTS - VirtualThread[#26]: Carriers:

2024-07-23 18:14:59 [main]

   INFO  c.w.r.c.VTS - ForkJoinPool-1-worker-1

2024-07-23 18:14:59 [main]

   INFO  c.w.r.c.VTS - ForkJoinPool-1-worker-4

2024-07-23 18:14:59 [main]

   INFO  c.w.r.c.VTS - ForkJoinPool-1-worker-2
```

```
Summary

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - VirtualThread[#26]: Carriers:

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - ForkJoinPool-1-worker-7

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - VirtualThread[#25]: Carriers:

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - ForkJoinPool-1-worker-4

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - VirtualThread[#24]: Carriers:

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - ForkJoinPool-1-worker-3

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - VirtualThread[#22]: Carriers:

2024-07-23 18:20:41 [main]

   INFO  c.w.r.c.VTS - ForkJoinPool-1-worker-1
```

钉住（Pinning）不会破坏你的代码；它仍然会执行。然而，它会阻止你获得虚拟线程带来的益处。为了防止线程钉住，请将所有的 `synchronized` 锁替换为 `ReentrantLock` 实例。

如果你正在将应用程序迁移到虚拟线程，这一点非常重要。代码使用 `synchronized` 锁仍然可以工作，但除非你进行这些更改，否则它无法提供你预期的性能收益。

我们还有很多未在此涵盖的组件。但我们建议你意识到它们的存在，并在需要时学习如何使用它们。这些包括以下内容：

- `Semaphore`：类似于 `Lock`，区别在于你可以指定在阻塞之前允许进入的线程数量。
- `ReadWriteLock`：为了在读多少的应用程序中维护数据一致性，`ReadWriteLock` 允许在没有写入者的情况下无限数量的读取者。一旦写入线程获取锁，所有读取者必须等待其完成后才能允许更多读取者。只要有写入者在等待，读取者就会被阻塞。
- `StampedLock`：类似于 `ReadWriteLock`，但还提供了乐观锁场景。
- `TransferQueue`：`BlockingQueue` 的扩展，用于生产者线程将其内容传递给消费者。生产者将等待直到有消费者线程接受其内容，同样，消费者在必要时也会等待数据可用。
- `CompletionService`：当你有许多线程产生内容且我们不在乎顺序时，这是一个非常有用的组件；我们只需要在每个结果可用时对其进行处理。

### 线程间通信

并发中的一个常见问题是线程间通信，即组中的每个线程必须完成某些工作，然后信号下一个线程执行后续操作。

Java 为线程间通信提供了原生支持。许多线程可以在同一个锁上进行同步并等待。

一个简单的例子将有助于理解这一概念。你正在编写一个乒乓球程序。你有三个线程，第一个只说“Ping”，第二个说“Over the net”，第三个只说“Pong”。你希望它们交替进行，使得第一个线程打印 `Ping`，然后信号 `Over the net` 打印，然后信号 `Pong`，再回到 `Over the net`，最后回到 Ping 线程，以此类推，直到达到指定的来数。让我们在输出前加上回合数，例如 `1 Ping`、`1 Over the net`、`1 Pong`、`1 Over the net`、`2 Ping`、`2 Over the net`、`2 Pong`、`2 Over the net` 等，持续进行 N 次迭代。

代码如下：

```
10: public class PingNetPong{
11:    public static void main(String[] args){
12:       new PingNetPong().playPingPong(3);
13:    }
14: 
15:    public void playPingPong(int volleys){
16:       ReentrantLock lock = new ReentrantLock();
17:       Condition ping = lock.newCondition();
18:       Condition overTheNet = lock.newCondition();
19:       Condition pong = lock.newCondition();
20:       boolean[] pingOrPong = {true};
21:       try(ExecutorService executor
22:          = Executors.newVirtualThreadPerTaskExecutor()){
23:          Phaser phaser = new Phaser(3);
24: 
25:          executor.submit(() -> {
26:             lock.lock();
27:             IntStream.rangeClosed(1, volleys).forEach((i) -> {
28:                try{
29:                   phaser.arrive();
30:                   ping.await();
31:                   System.out.println(i + " Ping");
32:                   overTheNet.signal();
33:                }
34:             });
35:             });
36:             lock.unlock();
37:                     });
38: 
39:          executor.submit(() -> {
40:             lock.lock();
41:             IntStream.rangeClosed(1, volleys).forEach((i) -> {
42:                try{
43:                   phaser.arrive();
44:                   overTheNet.await();
45:                   System.out.println(i + " Over the net");
46:                   pingOrPong[0] = !pingOrPong[0];
47:                   if(pingOrPong[0]){
48:                      ping.signal();
49:                   }else{
50:                      pong.signal();
51:                   }
52:                } catch(InterruptedException e){
53:                   e.printStackTrace();
54:                }
55:             });
56:             lock.unlock();
57:          });
58: 
59:          executor.submit(() -> {
60:             lock.lock();
61:             IntStream.rangeClosed(1, volleys).forEach((i) -> {
62:                try{
63:                   phaser.arrive();
64:                   pong.await();
65:                   System.out.println(i + " Pong");
66:                   overTheNet.signal();
67:                } catch(InterruptedException e){
68:                   e.printStackTrace();
69:                }
70:             });
71:             lock.unlock();
72:          });
73: 
74:          phaser.await(0);
75:          lock.lock();
76:          ping.signal();
77:          lock.unlock();
78:       }
79:    }
80: }
```

### 在 Spring 框架中学习并发支持

如果你的项目使用了 Spring 框架，那么你可以使用一些组件和注解来方便地提供并发支持。在使用这些或任何其他 Spring 注解时，有一些需要注意的事项。

- 被注解的类必须由 Spring 管理。这意味着该实例必须是一个 bean，或者是一个标记了 `@Component`、`@Service` 等注解的类。
- 它必须使用 `@Autowired` 或构造函数注入等方式进行注入。
- 带有 `@Async` 注解的方法如果从同一个类内的另一个方法直接调用，它将不会在单独的线程中执行。这是因为如果你从同一个类内部调用该方法，你并不是在调用一个 Spring 管理的方法。

现在，让我们来看主要的 Spring 并发注解。

### 使用 @Async/@EnableAsync

Spring 提供了 `@Async` 注解，它可以应用于任何方法签的上方，这样当该方法被调用时，它将立即返回，并在单独的线程中处理其功能。要使用 `@Async` 注解，你必须告诉 Spring 启用异步处理。你可以通过在任何由 Spring 管理的类（通常是 Spring Boot Application 类，或者可能是某些 `@Configuration` 类，或者包含 `@Async` 的类）上加上 `@EnableAsync` 注解来实现。

在任何由 Spring 管理的类中，你都可以对方法使用 `@Async` 注解以使其异步执行。

此类方法可以返回 `void` 以实现“触发后遗忘”，在这种情况下，它们将立即返回，而任务将在后台执行。或者它们可以返回一个 `Future` 或 `CompletableFuture`，这些可以封装一个可序列化的值。对于 Spring MVC 端点，你可以返回 `void` 来触发后遗忘，或者返回 `CompletableFuture<ResponseEntity>`，让调用者等待调用结果的计算并返回。

请注意，如果 `@Async` 方法返回除 `void` 或 `Future` 之外的任何内容，该方法可能不会异步执行，并将导致意料之外的行为。

在我们的 `AsyncDemo` 类中，我们将以下方法标记为 `@Async`：`void performHeads(String message)` 和 `void performTails(String message)`。这些方法将分别显示三次 `message + " Heads"` 和 `message + " Tails"`。我们将让这些线程并发运行，因此消息可以帮助我们识别哪个是哪个。

首先，我们用错误的方法来做。你能看出 `AsyncDemo` 类中这段代码的问题所在吗？

```java
public void incorrectAsync(){
  performHeads("Incorrect");
  performTails("Incorrect");
}
```

输出看起来像这样：

```
2024-07-1 12:07:28 [restartedMain]

   INFO  c.w.r.concurrency.AD - Incorrect Heads
```



2024-07-1 12:07:29 [restartedMain]

   INFO  c.w.r.concurrency.AD - Incorrect Heads

2024-07-1 12:07:30 [restartedMain]

   INFO  c.w.r.concurrency.AD - Incorrect Heads

2024-07-1 12:07:31 [restartedMain]

   INFO  c.w.r.concurrency.AD - Incorrect Tails

2024-07-1 12:07:32 [restartedMain]

   INFO  c.w.r.concurrency.AD - Incorrect Tails

2024-07-1 12:07:33 [restartedMain]

   INFO  c.w.r.concurrency.AD - Incorrect Tails

从输出判断，我们看到 heads 在 tails 开始之前全部执行完毕，而且我们看到它们都在同一个 `restartedMain` 线程中执行。显然，这两个调用是顺序执行的，而不是并行执行的，但为什么呢？

答案是异步方法是从类本身调用的。正如我们所说，异步方法必须以 Spring 管理的方式调用，而不是作为直接方法调用。

为了修复这个问题，让我们从我们的 `@SpringBootApplication` 类中调用这些方法，在我们的案例中它是 `ConcurrencyApplication`。运行此应用程序并注意 `AsyncDemo` 实例被注入到变量 `asyncDemo` 中。`run` 方法随后进行了以下调用：

```java
log.info("Starting perform heads and perform tails");
asyncDemo.performHeads("Correct");
ayncDemo.performTails("Correct");
```

由于这些方法是在 Spring 管理的类上调用的，它产生了预期的交错输出而不是顺序输出，我们看到了两个线程 `taskExecutor-1` 和 `taskExecutor-2`，表明这两个方法正在并发执行。

```
2024-07-21 12:07:34 [taskExecutor-2]
   INFO  c.w.r.concurrency.AD - Correct Tails
2024-07-21 12:07:34 [taskExecutor-1]
   INFO  c.w.r.concurrency.AD - Correct Heads
2024-07-21 12:07:35 [taskExecutor-2]
   INFO  c.w.r.concurrency.AD  - Correct Tails
2024-07-21 12:07:35 [taskExecutor-1]
   INFO  c.w.r.concurrency.AD - Correct Heads
2024-07-21 12:07:36 [taskExecutor-1]
   INFO  c.w.r.concurrency.AD - Correct Heads
2024-07-21 12:07:36 [taskExecutor-2]
   INFO  c.w.r.concurrency.AD - Correct Heads
```

## 使用 @Async/@EnableAsync

Spring 提供了 `@Async` 注解，它可以应用于任何方法签的上方，这样当该方法被调用时，它将立即返回并在单独的线程中处理其功能。要使用 `@Async` 注解，你必须告诉 Spring 启用异步处理。你可以通过在任何由 Spring 管理的类（通常是 Spring Boot Application 类，或者可能是某些 `@Configuration` 类，或者包含 `@Async` 的类）上加上 `@EnableAsync` 注解来实现。

在任何由 Spring 管理的类中，你都可以对方法使用 `@Async` 注解以使其异步执行。

此类方法可以返回 `void` 以实现“触发后遗忘”，在这种情况下，它们将立即返回，而任务将在后台执行。或者它们可以返回一个 `Future` 或 `CompletableFuture`，这些可以封装一个可序列化的值。对于 Spring MVC 端点，你可以返回 `void` 来触发后遗忘，或者返回 `CompletableFuture<ResponseEntity>`，让调用者等待调用结果的计算并返回。

请注意，如果 `@Async` 方法返回除 `void` 或 `Future` 之外的任何内容，该方法可能不会异步执行，并将导致意料之外的行为。

在我们的 `AsyncDemo` 类中，我们将以下方法标记为 `@Async`：`void performHeads(String message)` 和 `void performTails(String message)`。这些方法将分别显示三次 `message + " Heads"` 和 `message + " Tails"`。我们将让这些线程并发运行，因此消息可以帮助我们识别哪个是哪个。

首先，我们用错误的方法来做。你能看出 `AsyncDemo` 类中这段代码的问题所在吗？

```java
public void incorrectAsync(){
  performHeads("Incorrect");
  performTails("Incorrect");
}
```

输出看起来像这样：

```
2024-07-1 12:07:28 [restartedMain]
   INFO  c.w.r.concurrency.AD - Incorrect Heads
2024-07-1 12:07:29 [restartedMain]
   INFO  c.w.r.concurrency.AD - Incorrect Heads
2024-07-1 12:07:30 [restartedMain]
   INFO  c.w.r.concurrency.AD - Incorrect Heads
2024-07-1 12:07:31 [restartedMain]
   INFO  c.w.r.concurrency.AD - Incorrect Tails
2024-07-1 12:07:32 [restartedMain]
   INFO  c.w.r.concurrency.AD - Incorrect Tails
2024-07-1 12:07:33 [restartedMain]
   INFO  c.w.r.concurrency.AD - Incorrect Tails
```

从输出判断，我们看到 heads 在 tails 开始之前全部执行完毕，而且我们看到它们都在同一个 `restartedMain` 线程中执行。显然，这两个调用是顺序执行的，而不是并行执行的，但为什么呢？

答案是异步方法是从类本身调用的。正如我们所说，异步方法必须以 Spring 管理的方式调用，而不是作为直接方法调用。

为了修复这个问题，让我们从我们的 `@SpringBootApplication` 类中调用这些方法，在我们的案例中它是 `ConcurrencyApplication`。运行此应用程序并注意 `AsyncDemo` 实例被注入到变量 `asyncDemo` 中。`run` 方法随后进行了以下调用：

```java
log.info("Starting perform heads and perform tails");
asyncDemo.performHeads("Correct");
ayncDemo.performTails("Correct");
```

由于这些方法是在 Spring 管理的类上调用的，它产生了预期的交错输出而不是顺序输出，我们看到了两个线程 `taskExecutor-1` 和 `taskExecutor-2`，表明这两个方法正在并发执行。

```
2024-07-21 12:07:34 [taskExecutor-2]
   INFO  c.w.r.concurrency.AD - Correct Tails
2024-07-21 12:07:34 [taskExecutor-1]
   INFO  c.w.r.concurrency.AD - Correct Heads
2024-07-21 12:07:35 [taskExecutor-2]
   INFO  c.w.r.concurrency.AD  - Correct Tails
2024-07-21 12:07:35 [taskExecutor-1]
   INFO  c.w.r.concurrency.AD - Correct Heads
2024-07-21 12:07:36 [taskExecutor-1]
   INFO  c.w.r.concurrency.AD - Correct Heads
2024-07-21 12:07:36 [taskExecutor-2]
   INFO  c.w.r.concurrency.AD - Correct Heads
```

## 使用 @Async/@EnableAsync

Spring 提供了 `@Async` 注解，它可以应用于任何方法签的上方，这样当该方法被调用时，它将立即返回，并在单独的线程中处理其功能。要使用 `@Async` 注解，你必须告诉 Spring 启用异步处理。你可以通过在任何由 Spring 管理的类（通常是 Spring Boot Application 类，或者可能是某些 `@Configuration` 类，或者包含 `@Async` 的类）上加上 `@EnableAsync` 注解来实现。

在任何由 Spring 管理的类中，你都可以对方法使用 `@Async` 注解以使其异步执行。

此类方法可以返回 `void` 以实现“触发后遗忘”，在这种情况下，它们将立即返回，而任务将在后台执行。或者它们可以返回一个 `Future` 或 `CompletableFuture`，这些可以封装一个可序列化的值。对于 Spring MVC 端点，你可以返回 `void` 来触发后遗忘，或者返回 `CompletableFuture<ResponseEntity>`，让调用者等待调用结果的计算并返回。

请注意，如果 `@Async` 方法返回除 `void` 或 `Future` 之外的任何内容，该方法可能不会异步执行，并将导致意料之外的行为。

在我们的 `AsyncDemo` 类中，我们将以下方法标记为 `@Async`：`void performHeads(String message)` 和 `void performTails(String message)`。这些方法将分别显示三次 `message + " Heads"` 和 `message + " Tails"`。我们将让这些线程并发运行，因此消息可以帮助我们识别哪个是哪个。

## 使用 @Scheduled/@EnableScheduling

你也可以告诉 Spring *调度* 一个任务，从指定的时间开始（默认是现在），并每隔指定的毫秒数运行一次。

一个例子在我们 `AsyncDemo` 类中，方法 `fixedRateTest()`，它定义为：

```java
@Scheduled(initialDelay = 20000, fixedRate = 1000)
public void fixedRateTest(){
   log.info("Fixed rate");
}
```



`initialDelay` 参数是可选的，在我们的案例中它表示在应用程序启动 20 秒后开始（给我们的其他测试留出显示输出的时间），然后每 1000 MS（每秒）运行一次。功能每秒显示一次 `Fixed rate`。更有用的用例是文件转换操作，必须以固定间隔读取文件，例如市场数据文件或销售报告文件，并将其处理到某些控制系统中。你需要通过在任何由 Spring 管理的类（通常是 Spring Boot Application 类，或者可能是某些 `@Configuration` 类，或者包含 `@Scheduled` 的类）上加上 `@EnableScheduling` 注解来告诉 Spring 你的应用程序使用了调度。

### 使用 ThreadPoolTaskExecutor 启动线程

通过注入 `TaskExecutor`，你可以对 Spring 使用的执行器获得更细粒度的控制并提供更细粒度的配置。

我们的 `AsyncDemo` 类自动注入了一个 `TaskExecutor` 实例，该实例被用于 `useTaskExecutor()` 方法以并行执行 `performHeads()` 和 `performTails()` 方法。

```java
@Autowired
TaskExecutor taskExecutor;

. . .

public void useTaskExecutor() {
    taskExecutor.execute(() -> performHeads("using TaskExecutor"));
    taskExecutor.execute(() -> performTails("using TaskExecutor"));
}
```

你可以从交错输出和日志中的两个线程名称看到，这两个方法正在并行调用：

```
2024-07-21 12:44:05 [task-1]
    INFO  c.w.r.concurrency.AD - using TaskExecutor Heads

2024-07-21 12:44:05 [task-2]
    INFO  c.w.r.concurrency.AD - using TaskExecutor Tails

2024-07-21 12:44:06 [task-1]
    INFO  c.w.r.concurrency.AD - using TaskExecutor Heads

2024-07-21 12:44:06 [task-2]
    INFO  c.w.r.concurrency.AD - using TaskExecutor Tails

2024-07-21 12:44:07 [task-1]
    INFO  c.w.r.concurrency.AD - using TaskExecutor Heads

2024-07-21 12:44:08 [task-2]
    INFO  c.w.r.concurrency.AD - using TaskExecutor Tails
```

### 理解 `@Transactional`

虽然 `@Transactional` 并不是一个专门的并发注解，但在我们微服务驱动的世界中，它对于管理事务和确保数据一致性至关重要，我们至少提到它。在编程世界中，当我们说一个多部分调用是一个事务时，我们的意思是这些部分要么全部完成，要么全部回滚。

例如，假设你有一个订单录入应用程序，它会向购物车中添加物品、减少库存并收取信用卡费用。现在，如果这些步骤中的每一个都是并行调用的会发生什么？如果信用卡被拒绝、购物车超过了我们的限制或库存不可用，而其他方法都已经被调用了呢？整个事务必须回滚。`@Transactional` 注解接受一个 `rollbackFor` 参数，用于指定发生事务异常时必须调用的补偿方法。

## 进一步参考

- *Java Concurrency in Practice* (Addison-Wesley, 2006)
- *Concurrent Programming in Java* (Addison-Wesley, 1999)
- Java Concurrent Animated，一个演示了 Java 内置大多数并发工具的 Swing 应用
  - [`https://github.com/vgrazi/JavaConcurrentAnimatedReboot.git`](https://github.com/vgrazi/JavaConcurrentAnimatedReboot.git)
- 跳表算法的说明
  - [`https://en.wikipedia.org/wiki/Skip_list`](https://en.wikipedia.org/wiki/Skip_list)

## 总结

在本章中，你学习了 Java 是最早将并发作为原生功能引入的语言之一，并学习了它如何演进以管理多线程编程的复杂性。你学习了原子性、同步、线程状态以及线程间通信等基本概念。你看到了用于管理并发的并发集合和数据结构。你学习了 `CompletableFuture` 如何帮助你构建响应式程序，以及虚拟线程如何让你的多线程应用程序扩展。最后，你还学习了 Spring 框架提供的并发支持。

# 第 10 章：使用正则表达式进行模式匹配

正则表达式是搜索文本字符串的强大工具。它们也被简称为正则（regex），并由正则表达式引擎进行处理。

你可能已经对模式匹配有一定的经验了。例如，当你搜索一个文件时，你可能会输入 `dir R*.pdf` 或 `ls R*.pdf` 来获取任何以 R 开头且类型为 pdf 的文件列表。正则表达式是一种更强大的匹配系统，具有完全不同的语法。

想象你有一组 URI 序列，例如：

```
http://spring.io/projects/spring-cloud-contract

https://www.infoq.com/articles/Living-Matrix-Bytecode-Manipulation/

file:///C:/Documents/happy_birthday_sis.pdf
```

想象你想要从每个 URI 中解析出协议（`http`、`https`、`file`）、网站或目录以及特定路径。

你可以使用困难的方法，使用 `string.indexOf()` 来搜索非空字符串，后面跟着一个冒号和两个或多个斜杠，然后是一连串字符直到遇到斜杠，然后是其他所有内容，最后使用 `string.substring()` 解析出相关文本。正则表达式让这变得简单得多，你将在章的后面再次看到这个示例。

正则表达式的语法以简洁且难以阅读而闻名，但事实上，它是你工具库中需要的这种强大工具。在本章中，你将学习如何构建正则表达式，以及如何在 Java 中使用它们来处理你在企业开发中会遇到的大多数解析需求。我们还将回顾一些你可能从正则表达式中受益的工具和框架。

## 引入正则表达式

假设你正在阅读一本电子书或博客文章，遇到了一个带有 ASCII 艺术计算机的精彩代码示例。你将其复制并粘贴到 IDE 中。遗憾的是，复制的文本中包含了行号。现在你必须删除所有 20 个行号。这听起来很麻烦。如果你很懒，可以编辑文本并删除数字和冒号，但删除 20 行工作量太大了，如果行数远多于此呢？正则表达式来救场了！

假设你有如下所示 `.txt` 文件。如果你在跟着操作，它是仓库中的 `src/main/resources/TextBlock.txt`。

```java
1:  public class TextBlock {

2:     public static void main(String[] args) {

3:       String computer = """

4:        +---------------+

5:        |               |

6:        |               |

7:        |               |

8:        |               |

9:        +---------------+

10:      +----------------+

11:                   |------------.|

12:                   ||            

13:                   / /============ \\

14:                 / /============== \\

15:                 /____________________

16:                 """;

17:       System.out.println(computer);

18:   }

19: }
```

在 IntelliJ 中，这里是去掉行号的方法：

1. 按下 `Ctrl+R`/`Cmd+R` 打开顶部的替换。
2. 按下 `Alt+X`/`Option+X` 开启正则表达式模式。
3. 在搜索框中，在查找框中输入 `\d+:`，替换框留空。确保包含冒号！
4. 点击全部替换。

图 10.1 显示了正则表达式前后的效果。

![一个文本块窗口的截图。正则表达式斜杠加被高亮。替换和全部替换选项在右侧。全部替换选项被高亮。](img/c10f001.png)

**图 10.1**](#c10.xhtml_R_c10-fig001 使用正则表达式进行替换

等等。`\d+:` 魔法是什么？这是我们在章中看到的第一个正则表达式。`\d` 意味着匹配任何数字。`+` 匹配 `\d` 的一次或多次。因此，`\d+` 匹配一个或多个数字。冒号就是字面上的冒号（`:`）字符。你告诉 IntelliJ 删除紧跟冒号的一个或多个数字。有趣的事情开始了！你将在本章中学习更多的正则表达式。

搜索（和替换）是正则表达式的常见用法。验证数据和解析数据也是常见的用例。这些这些共同点是什么？它们涉及处理文本数据并匹配模式。

如果你以前没有使用过正则表达式，语法需要一点时间适应。但一旦掌握了它，你就能高效地执行搜索和字符串处理任务。

## 学习基础正则表达式语法

在将正则表达式添加到 Java 代码之前，你需要熟悉正则表达式语法。在开发正则表达式时，随手准备一个正则表达式测试器。网上有很多此类工具。我们喜欢 [`https://regex101.com`](https://regex101.com)，它提供了对所有正则功能的完整支持。

正则表达式在不同的编程语言和环境中是相似的，但它们并不总是完全相同。在 `Regex101` 网站上，你可以在左侧导航栏中选择 `Java` 变体，以获取 `Java` 的精确语法和选项。图 10.2 显示了该网站上的 `\d+:` 示例。

![正则表达式窗口的截图。在变体菜单中，选择了 java 68。正则表达式输入在给定的栏中。解释显示在右侧。](img/c10f002.png)

**图 10.2**](#c10.xhtml_R_c10-fig-0002): Regex101

让我们回顾一下 `Regex101` 的布局。在顶部的文本框中，你将输入正则表达式模式。你会注意到正则表达式右侧有一个小的 `gm`。`g`（全局）和 `m`（多行）是你可以关闭的标志，它们告诉正则解析器将你的“测试字符串”中的每一行视为一个独立的输入字符串，而不是一个长字符串。我们将在本章稍后介绍这些和其他标志。正则表达式下方是你输入一行或多行的地方，用于测试它们与正则表达式模式的匹配。

在右上角，网站会解释你的正则表达式。它告诉你是模式是 `greedy`（贪婪的），我们将在本章稍后也会解释。它还提醒你正则表达式是区分大小写的（除非另有指定）。

解释区域下方是匹配结果，相应的匹配项在“测试字符串”（Test String）区域被高亮。在我们的示例中，前两行匹配我们的模式，因为它们是数字后跟着冒号。第三行缺少冒号，第四行缺少数字，所以那两行不匹配。

在接下来的章节中，你将学习如何编写基础正则表达式，随着章节的进行，我们将涵盖更高级的情况。

### 指定常用量词

最简单的正则表达式只是代表一个或多个字符的字面量序列，表示精确匹配。因此，模式 `org` 将在 `organization`、`fictive` 和 `cyborg` 中被找到。

量词是放置在文本模式后的运算符，用于指定匹配某些内容的次数。表 10.1 向你展示了最常用的量词运算符。在本章稍后讨论懒量量和占有量词时，你将看到更多。

| 代码 | 匹配多少次？ | 解释 |
| --- | --- | --- |
| `R?` | 字母 `R` 出现零次或一次。 | 模式 `BR?AKE` 将匹配 `BRAKE` 或 `BAKE`。 |
| `L*` | 字母 `L` 出现零次或多次。 | 模式 `JOL*Y` 匹配 `JOLLY` 和 `JOY`。 |
| `L+` | 字母 `L` 出现一次或多次。 | 模式 `MARVEL+ED` 匹配 `MARVELED` 或 `MARVELLED`。 |
| `!{3}` | 精确出现三次 `!`。 | 模式 `TERRIFIC!{3}` 匹配 `TERRIFIC!!!` 但不匹配 `TERRIFIC!!`。 |
| `!{3,}` | `!` 出现三次或多次。 | 模式 `TERRIFIC!{3,}` 匹配 `TERRIFIC!!!` 和 `TERRIFIC!!!!!`。 |
| `!{3,5}` | `!` 出现三次、四次或五次。 | 模式 `TERRIFIC!{2,4}` 匹配 `TERRIFIC!!`、`TERRIFIC!!!` 和 `TERRIFIC!!!!`。 |

**表 10.1**](#c10.xhtml_R_c10-tbl-0001): 量词

当你编写正则表达式时，可能会发现有多种方法表达相同的内容，因此要力清晰。以下是寻找一个或多个 `x` 的正则模式。思考你认为哪一个最清晰。

```
x+
x{1,}
xx?*
x{1}x*
x{1,1}x*
xx{0,}
```

我们希望你说 `x+` 是最清晰的。这个呢？

```
xx+
x{2,}
xxx*
x{1}x+
x{2,}x*
xxx{0,}
```

这些都匹配字母 `x` 的两次或多次。我们认为你会同意 `xx+`（`x` 后跟一个或多个 `x`）是最清晰的。

花一点时间理解集合中的每一个为何等价。这个练习将帮助你记住所有量词的语法。虽然你不想在同一个正则表达式中使用所有它们，但了解它们是有用的。

### 匹配基础边界

除了匹配字符外，你还可以匹配字符之间的区域。为了理解这些含义，假设你有一个字符串 `A GEEK` 并寻找边界。图 10.3，字符之前、之间和之后的数字是边界位置。

如果你想从预定义的字符集中选择一个零或多个字符的序列，那么字符类非常用。但如果你想匹配一个字符序列或另一个字符序列呢？你可以使用 `|`（管道符号）字符来提供选择。例如，你可以通过这种方式决定午餐吃什么：

```
tuna|turkey
```

正如你所想象的，这将匹配 `tuna` 或 `turkey`。如果你想在后面添加单词 `sandwich` 会发生什么呢？这样做是行的：

```
tuna sandwich|turkey sandwich
```

这种写法也是行的：

```
(tuna|turkey) sandwich
```

后一种版本使用括号来指定备选项。然后它会无条件地在后面匹配 `sandwich`。这种方法可以使正则表达式更加清晰，因为它避免了 `sandwich` 的重复，并显示了只有三明治的类型（括号内）是变化的。

### 字符转义

在处理字符串时，你应该熟悉字符转义的概念。例如，如果你想在字符串中包含双引号，你必须使用反斜杠对其进行转义（`escape it`），如下所示：

```java
String escapeQuote = "\"Java is Great\"";
```

同样，你使用另一个反斜杠来转义反斜杠：

```java
String escapeBackslash = "\\";
```

在正则表达式中，你使用反斜杠来指示其后的字符应该被视为字面量，而不是应用正则表达式的含义。例如，假设你想写一个正则表达式来匹配两个数字相加的模式。其中一种写法是这样的：

```java
String addition = "\\d \\+ \\d";
```

这看起来有很多反斜杠，所以让我们花一点时间解析一下。数字的正则表达式语法是 `\d`。然而，反斜杠在 Java 中已经有含义，所以你需要额外添加一个反斜杠，使其变成 `\\d`。接下来是一个空格。这很直观；它匹配一个空格。

之后，我们要匹配字面量加号（`+`）。但你不能直接写 `+`，因为正如我们看到的，它代表一个量词，意味着上一个字符一次或多次。要匹配字面量加号，你必须添加反斜杠来转义 `+`。但猜怎么着？在 Java 字符串中包含反斜杠，你需要对其进行转义，所以反斜杠需要被转义，给你 `\\+`。完成我们的正则表达式，我们需要另一个空格，然后是另一个 `\\d` 组合。

如果你想避免反斜杠，可以将字符放在字符类中。例如，以下两种方式都匹配单个字面量点（`.`）：

```java
String escapePeriod1 = "[.]";
String escapePeriod2 = "\\.";
```

## 在 Java API 中使用正则表达式

到此，你已经掌握了足的正则表达式语法知识，可以开始在 Java 中使用它们。某些方法可以直接在 `String` 对象上调用，而另一些方法则需要 `Pattern` 类，这是一种用于创建可重用正则模式的特殊 Java 类。

### 调用 String 方法

在本节中，你将看到如何使用正则表达式来匹配、替换和分割字符串。所有这些方法都是直接在 `String` 类上用的，就像 `contains()` 和 `length()` 等常用方法一样。

#### 查找匹配项

`matches()` 方法接受正则表达式作为参数，并返回该正则表达式是否与 `String` 实例形成完整（`complete`）匹配。我们特意使用了“完整匹配”这个短语。如果文本中存在额外的字符，即使正则表达式可能匹配文本的某些部分，`matches()` 也会返回 `false`。让我们来看几个例子：



之前的正则表达式尝试匹配单个元音。虽然文本中有元音，但也有其他字符，所以它不是完整匹配。要修复这个问题，你需要指定元音之前或之后可以是任何字符。

```java
String text = "java book";
System.out.println(text.matches(".*[aeiou].*")); // true
```

为了更清楚地表示整个正则表达式需要匹配，你可以选择性地包含开头（`^`）和结尾（`$`）锚点。

```java
String text = "java book";
System.out.println(text.matches("^.*[aeiou].*$")); // true
```

再举一个例子，你理解为什么以下匹配吗？

```java
String text = "java book";
System.out.println(text.matches("\\w+\\s\\w+")); // true
```

这个模式有三个部分。`\\w+` 匹配“一个或多个”单词字符。`\\s` 匹配单个空白字符。最后，`\\w+` 再次匹配“一个或多个”单词字符。很多人发现这很难读。幸运的是，它可以用更清晰的方式编写。

```java
String text = "java book";
String word = "\\w+";
String space = "\\s";
String regex = word + space + word;
System.out.println(text.matches(regex)); // true
```

注意正则表达式是如何用通俗英语定义的。显然，该正则表达式匹配两个由空格分隔的单词。`word` 和 `space` 变量也更容易理解，因为它们有清晰的名字。例如，一个或多个单词字符组成一个单词是合逻辑的。假设你写了错字，写成了“零或多个单词字符”的模式，而不是“一个或多个”。

## 替换值

有两种方法可以替换匹配正则表达式的 `String` 部分。`replaceAll()` 方法替换每个匹配的子串。`replaceFirst()` 方法只替换第一个匹配项。

```java
String text = "java book";
System.out.println(text.replaceAll("[aeiou]", "_"));   // j__k
System.out.println(text.replaceFirst("[aeiou]", "_")); // jva book
```

注意 `replaceAll()` 替换了所有的元音，而 `replaceFirst()` 只替换了第一个。现在让我们尝试匹配多个字符。

```java
String text = "java book";
System.out.println(text.replaceAll("\\w+", "[word]")); // [word] [word]
```

`\\w+` 查找“一个或多个”单词字符。替换结果是六字符字符串 `[word]`。

最后，你可以使用 `$` 符号在替换中使用原始文本中的匹配部分，如下：

```java
String text = "java book";
System.out.println(text.replaceAll(  // book java
   "(\\w+)\\s(\\w+)", "$2 $1"));
```

模式中的括号创建了*捕获组*，你可以在替换模式中通过 `$1`、`$2` 等引用它们。在这种情况下，有两个括号，所以有两个可用的组。通过在替换模式中反转它们，代码反转了它们在替换字符串中的顺序，从而输出 `book java`。

### 分割

你对 `String` 类可以进行的最后一个正则表达式操作是分割为 `String[]`。使用 `split()` 的常用方法是使用表示单个分隔符（如空格）的正则表达式。

```java
String text = "java book";
String[] words = text.split(" ");
System.out.println(words.length);          // 2
System.out.println(Arrays.asList(words));  // [java, book]
```

分割字符（在这种情况下是空格）被称为*定界符（delimiter）*。当然，你可以使用更复杂的正则表达式，如下：

```java
String text = "123 - 456 - 789";
String[] words = text.split("[- ]+");
System.out.println(words.length);         // 3
System.out.println(Arrays.asList(words));  // [123, 456, 789]
```

此模式匹配由一个或多个相邻的连字符和空格组成的分符。在使用 `split()` 方法时，请注意确保你的分隔符不会匹配零字符字符串，否则你将得到一序列单个字符，如例所示：

```java
String text = "123 - 456 - 789";
String[] words = text.split("[- ]*"); // 匹配零或多个字符
System.out.println(words.length);         // 11
System.out.println(Arrays.asList(words)); // [1, 2, 3,, 4, 5, 6,, 7, 8, 9]
```

“那里发生了什么？”你问道。正则表达式匹配了每个字符之间的位置，因此它们都被分离到数组中，甚至空格也是如此。除非你的本意确实如此，否则请小心正则表达式不要匹配空字符串！

如果正则表达式匹配了文本的开头或结尾，你可能会感到惊讶。在下面的用例中，它同时匹配了两者：

```java
String text = "- 123 - 456 - 789 -";
String[] words = text.split("[- ]+");
System.out.println(words.length);         // 4
System.out.println(Arrays.asList(words)); // [, 123, 456, 789]
```

注意数组中的第一个元素是一个空字符串，但最后一个不是。这种差异是 Java 选择实现 `split()` 方法的方式。

虽然 `split()` 最常用的调用方式是只传入一个正则表达式参数，但存在一个接受两个参数的变体。第二个参数是一个数字 `limit`，用于自定义 `split()` 的行为。虽然这个带有第二个参数的版本不那么常用，但了解它是有好的。以下示例展示了这些差异：

```java
String text = "- 123 - 456 - 789 -";
String[] limit0 = text.split("[- ]+", 0);
System.out.println(limit0.length); // 4
System.out.println(Arrays.asList(limit0)); // [, 123, 456, 789]

String[] limit3 = text.split("[- ]+", 3);
System.out.println(limit3.length); // 3
System.out.println(Arrays.asList(limit3)); // [, 123, 456 - 789 -]

String[] limitNegative = text.split("[- ]+", -1);
System.out.println(limitNegative.length); // 5
System.out.println(Arrays.asList(limitNegative)); // [, 123, 456, 789, ]
```

从第一次调用中可以看出，当 `limit` 为 0 时，输出结果与不传递 `limit` 就调用 `split()` 相同。实际上，在幕后，`split(regex)` 方法调用了 `split(regex, 0)`。

传递一个正数作为 `limit` 更有趣；它将结果数组的最大长度限制为该数字数量的元素个数。如果有更多的匹配项，只有前 `n-1` 个（其中 `n` 是 `limit` 值）会被分割，超出部分的任何内容将合并为最后一个项。在第二次调用中，我们提供的 `limit` 是 3。由于以分隔符开头，第一个元素是空字符串，第二个元素是 `123`，第三个元素则是字符串的剩余所有部分。

传递任何负 `int` 返回的结果与传递零 `limit` 相同，不同之处在于如果末尾有空匹配，它会被包含在内。在示例中，这会在数组中多出一个元素。

最后，Java 21 增加了另一个名为 `splitWithDelimiters()` 的方法。它的行为与带有正 `limit` 值的 `split()` 相同，但它还将匹配的分隔符作为返回数组的元素。这些分隔符元素不计入 `limit` 计数。例如：

```java
String text = "- 123 - 456 - 789 -";
String[] limit3 = text.splitWithDelimiters("[- ]+", 3);
System.out.println(limit3.length); // 3
System.out.println(Arrays.asList(limit3)); // [, - , 123,  - , 456 - 789 -]
```

如果你调用的是 `split()`，它将返回一个包含三个元素的数组。注意单个连字符是如何位于 `limit3[1]` 和 `limit3[3]` 的。这些就是分隔符。

### 使用模式 (Patterns)

我们在上一节中看到的 `String` 类的所有方法在幕后都使用了 `Pattern` 和 `Matcher` 类。这些类也可以直接供你使用并提供了额外的方法以提供更强大的功能和更高的性能。

#### 查找匹配项

`String` 类上的 `matches()` 方法告诉你正则表达式是否匹配了整个目标。然而，通常你可能想要匹配不是整个目标，而是想扫描文本以找到匹配特定正则表达式的所有部分。你可以使用 `matcher.find()` 方法来实现，如下：

```java
11: String text = "java book";
12: Pattern pattern = Pattern.compile("\\w+");
13: Matcher matcher = pattern.matcher(text);
14: while (matcher.find()) {
15:    System.out.println(matcher.group());
16: }
```

这输出：

```
java
book
```

第 11 行创建了 `text`。第 12 行编译了 `Pattern`。第 13 行创建了 `Matcher`。第 14 行在 `matcher.find()` 为真时循环。第 15 行打印了 `group()`。

```java
String text = "Real World Java";
String twoAdjacentChars = "(\\w)(\\w)";
Pattern pattern = Pattern.compile(twoAdjacentChars);
Matcher matcher = pattern.matcher(text);
while (matcher.find()) {
   String chars = "%s%s".formatted(matcher.group(1), matcher.group(2));
   System.out.println(chars);
}
```

注意 `world` 中的 `d` 是如何被忽略的，因为它并不是字符对的一部分（`d` 之后的字符是空格）。组索引根据括号 `group(1)` 和 `group(2)` 编号。

与其通过数字引用组，你还可以为组命名并通过名称引用。这在有大量组时特别有用。要命名组，在组的第一个条目添加组命名指定符。获取与该组关联的匹配文本使用 `matcher.group(name)`，例如：

```java
String text = "Real World Java";
Pattern pattern = Pattern.compile("(?<first>\\w)(?<second>\\w)");
Matcher matcher = pattern.matcher(text);
while (matcher.find()) {
   String chars = "%s %s".formatted(matcher.group("first"),
      matcher.group("second"));
   System.out.println(chars);
}
```

你觉得数字组还是命名组更清晰，取决于个人喜好以及你正在编写的代码。

#### 替换值

`String` 方法 `replaceFirst()` 和 `replaceAll()` 在你想要替换第一个匹配项或所有匹配项时非常有用。但如果你想要更具体的替换逻辑呢；例如，假设你想替换每隔匹配项。幸运的是，你也可以用 `Pattern` 和 `Matcher` 实现这一点。这个有趣的方法会将每隔单词（由一个或多个字母组成）转为大写：

```java
20: String text = "-->The---quick---brown---fox---jumped!!";
21: StringBuffer buffer = new StringBuffer();
22: Pattern pattern = Pattern.compile("\\w+");
23: Matcher matcher = pattern.matcher(text);
24: boolean flip = false;
25: for(int i = 0; matcher.find(); i++) {
26:    String group = matcher.group();
27:    flip = !flip;
28:    if(flip) {
29:       group = group.toUpperCase();
30:    }
31:    matcher.appendReplacement(buffer, group);
32:    System.out.println(i + "." + buffer);
33: }
34: matcher.appendTail(buffer);
35: System.out.println(buffer);
```

输出结果如下：

```
0.-->THE
1.-->THE---quick
2.-->THE---quick---BROWN
3.-->THE---quick---BROWN---fox
4.-->THE---quick---BROWN---fox---JUMPED
-->THE---quick---BROWN---fox---JUMPED!!
```

第 20 到 30 行看起来非常熟悉；我们只是在循环遍历正则表达式的匹配项。第 21 行的 `StringBuffer` 工作方式类似于 `StringBuilder`，不同在于它是线程安全的。虽然在这里你不需要线程安全，但在正则表达式添加到 Java 之前，`StringBuilder` 并不存在，因此 API 使用了 `StringBuffer`。

`appendReplacement()` 和 `appendTail()` 方法是新的方法；它们将替换文本附加到 `StringBuffer` 中。`appendReplacement()` 会将上一个匹配项之后、当前匹配项之前的任何字符，加上替换文本本身（在本例中，是匹配项的大写版本）。`appendTail()` 方法则附加从最后一个匹配项到输入字符串末尾的所有剩余字符。为了确保你理解了这一点，让我们过一遍示例的流程：

1. 在循环的第一次迭代中，`group` 包含 `The`。
2. `appendReplacement()` 首先将匹配项之前的文本（在本例中为 `-->`）追加 `buffer`，然后将替换文本（`THE`）追加到 `buffer`。
3. 在循环的第二次迭代中，`group` 包含 `quick`。
4. `appendReplacement()` 方法将匹配项之前的文本（`--`）追加 `buffer`，然后将替换文本（`quick`）追加到 `buffer`。
5. 它继续查找并大写每隔单词，直到最后，`appendTail()` 将匹配项后的剩余文本（`!!`）追加到 `buffer`。

尝试另一个例子，你认为它是干什么的？

```java
String text = "java book";
StringBuffer buffer = new StringBuffer();
Pattern pattern = Pattern.compile("(\\w)(\\w)(\\w)(\\w)");
Matcher matcher = pattern.matcher(text);
while (matcher.find()) {
   matcher.appendReplacement(buffer, "$1 $2 $3 $4\n");
}
matcher.appendTail(buffer);
System.out.println(buffer);
```

它的输出如下：

```
j a v a
 b o o k
```

正则表达式匹配四个连续的单词字符，每个字符在一个捕获组中。`appendReplacement()` 方法提供了相同的四个字符，并在字符之间添加了空格。由于原始字符串中的空格，`b` 被缩进了一个字符。

如果你想在替换中包含某些正则命令字符的字面值（例如反斜杠或美元符号）怎么办？`quoteReplacement()` 方法告诉 Java 使用字面值而不是它们的特殊含义。例如：



```java
String text = "java book";
StringBuffer buffer = new StringBuffer();
Pattern pattern = Pattern.compile("(\\w)(\\w)(\\w)(\\w)");
Matcher matcher = pattern.matcher(text);
while (matcher.find()) {
   // 包含字面量的 \ 和 $
   String replacement = Matcher.quoteReplacement("\\$1.00");
   matcher.appendReplacement(buffer, replacement);
}
matcher.appendTail(buffer);
System.out.println(buffer);
```

这次的输出如下：

```
\$1.00 \$1.00
```

注意 `$` 如何被理解为字面文本，而不是 `$` 的正常正则含义（`$` 通常是匹配输入开始位置的锚点）。同样，反斜杠被视为字面量反斜杠，而不是对 `$` 的转义。

## 作为流进行分割

`Pattern` 提供了一个有用的分割方法，该方法在 `String` 上无法直接使用。通过 `Pattern`，你可以创建一个 `Stream<String>` 而不是 `String[]`。例如：

```java
String text = "- 123 - 456 - 789 -";
Pattern pattern = Pattern.compile("[- ]+");
Stream<String> stream = pattern.splitAsStream(text);
stream.forEach(a -> System.out.println("*" + a + "*"));
```

这段代码输出如下：

```
**
*123*
*456*
*789*
```

这与 `string.split()` 产生相同的四个匹配项，但它将分割结果作为 `String` 的 `Stream` 而不是数组。

## 使用标志控制行为

在编译 `Pattern` 时，你可以可选地向 `compile` 方法传递标志，以微调正则表达式的行为。

| 常量名 | 嵌入标志值 | 描述 |
| --- | --- | --- |
| `CASE_INSENSITIVE` | `(?i)` | 匹配时忽略大小写。 |
| `DOTALL` | `(?s)` | 启用单行模式，允许 `.` 匹配换行符。 |
| `MULTILINE` | `(?m)` | 启用多行模式，使 `^` 和 `$` 匹配行的开头和结尾，而不是整个字符串的开头结尾。 |
| `UNICODE_CASE` | `(?u)` | 使用 Unicode 字符处理大小写而不是 ASCII。 |
| `UNICODE_CLASS` | `(?U)` | 预定义类包含 Unicode 字符。 |

以下示例使用了前两个标志：

```java
String text = """
   Real-World Java: Helping You Navigate the Ecosystem
   Victor Grazi
   Jeanne Boyarsky""";

Pattern pattern = Pattern.compile("real.*sky", Pattern.CASE_INSENSITIVE | Pattern.DOTALL);
Matcher matcher = pattern.matcher(text);

if (matcher.find()) {
   System.out.println("I got this book!");
}
else {
   System.out.println("I should have gotten this book!");
}
```

在之前的代码中，位运算符（`|`）组合了这两个标志。`CASE_INSENSITIVE` 标志将正则表达式中的小写 `r` 匹配输入中的大写 `R`。`DOTALL` 将字符串中的换行符视为任何字符。

与其将这些标志作为参数传递给 `compile` 方法，你可以将它们直接嵌入正则表达式。当你将正则传递给 `String.matches()` 方法时，这特别有用，因为该方法没有接受单独标志的版本。

之前的示例可以用如下嵌入标志编写：

```java
String text = """
   Real-World Java: Helping You Navigate the Ecosystem
   Victor Grazi
   Jeanne Boyarsky""";
if (text.matches("(?i)(?s)real.*sky")) {
   System.out.println("I got this book!");
}
else {
   System.out.println("I should have gotten this book!");
}
```

虽然嵌入标志更短且更有表现力，但并不一定更清晰，请谨慎选择。

我们在这里展示的另一个标志是 `MULTILINE`。

```java
String text = """
   Real-World Java: Helping You Navigate the Ecosystem
   Victor Grazi
   Jeanne Boyarsky""";
Pattern pattern = Pattern.compile(".*[iy]$", Pattern.MULTILINE);
Matcher matcher = pattern.matcher(text);
while (matcher.find()) {
   System.out.println(matcher.group());
}
```

该正则匹配以 *i* 或 *y* 结尾任意字符。由于处于 `MULTILINE` 模式，它将找到所有以 *i* 或 *y* 结尾的行。这段代码输出：

```
Victor Grazi
Jeanne Boyarsky
```

`MULTILINE` 标志将每个换行符匹配为 `$`。由于 Victor Grazi 和 Jeanne Boyarsky 分别以 `i` 和 `y` 结尾，因此两行都会输出。如果没有该标志，只有 Jeanne 的那行会被输出，因为此时 `$` 将仅匹配 `String` 的结尾。

# 探索高级正则表达式语法

你到为止所看到的都是基础正则表达式语法。现在，让我们通过查看更细粒度控制的语法来更上一层楼。

首先，我们将查看正向和负向的先行断（look-ahead）和后行断（look-behind）。这些语法允许你根据相邻文本来改变匹配内容。之后，你将看到如何指定贪婪、懒惰和独占的量符。

## 查看相邻文本

到目前为止，本章中的正则表达式直接匹配输入文本。但如果你想相对于输入内容中的其他文本来查找匹配项呢？针对这种场景有四种类型的结构。假设你有文本 `dev.java/playground` 并想匹配 `java`。然而，你只想在上下文中的某些条件满足时才进行匹配。这四种方法如下：

*   **正向先行断 (Positive look-ahead):** 检查某个模式是否紧随其后。例如，“只有当 `g` 紧跟单词 `play` 时才匹配字母 `g`。”

*   **负向先行断 (Negative look-ahead):** 检查某个模式是否没有紧随其后。例如，“只有在单词 `java` 后面没有小写字母时才匹配。”

*   **正向后行断 (Positive look-behind):** 检查某个模式是否紧邻其前。例如，“只有在 `java` 前面有一个点时才匹配。”

*   **负向后行断 (Negative look-behind):** 检查某个模式是否没有紧邻其前。例如，“只有在 `java` 前面没有数字时才匹配。”

正向先行断使用语法 `(?=X)`，其中 `X` 是用于用于先行断的正则表达式。正向后行断在语法中添加了 `<`，变为 `(?<=X)`。你可以记住这一点，因为小于符号指向左侧，即“之前”的方向。负向先行断和后行断在 `?` 之后使用 `!` 而不是 `=` 来表示否定。

Table 10.5 回顾了这些构造结构的语法。对于后行断，注意 `java` 位于括号中。这表示我们要查看整个单词 `java` 之前，而不仅仅是最后一个字母 `a` 之前。

| NAME | SYNTAX | EXAMPLE | DESCRIPTION |
| --- | --- | --- | --- |
| Positive look-ahead | `(?=X)` | `play(?=g)` | 如果后面跟着 `g`，则匹配单词 `play`。 |
| Negative look-ahead | `(?!X)` | `java(?![a-z])` | 如果后面不是小写字母，则匹配单词 `java`。 |
| Positive look-behind | `(?<=X)` | `(?<=[.])java` | 如果前面是一个点号，则匹配单词 `java`。 |
| Negative look-behind | `(?<!X)` | `(?<![0-9])java` | 如果前面不是数字，则匹配单词 `java`。 |

TABLE 10.5: 正向/负向先行断/后行断模式

让我们来看另一个例子。假设你有以下文本：

```
once upon a time
```

让我们看看某些模式是如何匹配的：

*   `on`: 这个示例（不带先行断或后行断）匹配字母 `on` 且没有进一步限制，它匹配了两个各两个字母的实例：`on`ce up`on` a time。

*   `on(?=ce)`: 这个正向先行断示例匹配后面跟着 `ce` 字母的 `on`，结果匹配了两个字母 `on`ce upon a time`。

*   `on(?!ce)`: 这个负向先行断示例匹配后面*不是* `ce` 字母的 `on`，结果匹配了两个字母 `once up``on` a time`。

*   `(?<=up)on`: 这个正向后行断只有在字母 `on` 紧跟在字母 `up` 之后时才匹配它们，结果匹配了两个字母 `once up``on` a time`。

*   `(?<!up)on`: 这个负向后行断除非字母 `on` 紧跟在字母 `up` 之后，否则就会匹配它们，结果匹配了两个字母 `on`ce upon a time`。

## 区分量符

在章节早期，你学习了量符。Table 10.1 列出了最常见的量符。但还有很多，Table 10.6 提供了完整的列表。注意，懒惰量符添加了 `?`，而独占量符添加了 `+`。让我们来理解这些意味着什么。

| DESCRIPTION | GREEDY | RELUCTANT | POSSESSIVE |
| --- | --- | --- | --- |
| Zero or one | `J?` | `J??` | `J?+` |
| Zero or more | `J*` | `J*?` | `J*+` |
| One or more | `J+` | `J++` | `J++` |
| Exactly three | `J{3}` | `J{3}?` | `J{3}+` |
| Three or more | `J{3,}` | `J{3,}?` | `J{3,}+` |
| Three, four, or five | `J{3,5}` | `J{3,5}?` | `J{3,5}+` |

如果你移动空格以形成这种模式，事情变得更有趣：

```
(row)*+ your boat
```

所有有量符首先捕获了文本的前三个字母：`row`。由于输入的第四个字符是空格，且后面没有跟着 `your boat`，因此它不可能是匹配，所以这三个字符被忽略了。接着考虑下一个单词 `row`。这次它后面跟着一个空格和 `your boat`。破译！所有有量符版本找到了匹配项。

```
row row your boat
```

## 识别常见错误

在第 4 章“使用 Maven、Gradle 和 Jenkins 自动化你的 CI/CD 构建”中，你学习了 `SonarQube` 是一种常见的静态分析工具。它还有一个名为 `SonarLint` 的 IDE 插件。`Sonar` 非常擅长识别正则表达式中的常见问题，以及 Java 代码本身的问题。

表 10.7 显示了一些要点。理解这些常见错误也将帮助你更好地理解如何编写正则表达式。

| 代码 | 错误在哪里 |
| --- | --- |
| `[ab]&#124;a` | `a` 是多余的；`[ab]` 实现了相同的功能。 |
| `x = x` `.replaceAll("\\.\\.\\...", "\";")` | 完全不需要正则表达式。这样做的效果相同且更易读：`x = x` `.replace("…", "");` |
| `<.+?>` | 这会产生无谓的回溯。一个更具体的正则表达式可以避免这种回溯：`<[^>]+>` |
| `$[a-z]^` | 锚点反反了。它应该是：`^[a-z]$`。作为记忆辅助，`^` 指向上指向开头。`$` 代表钱，即底线。 |
| `(?=a)b` | 这是不可能的。你已经知道下一个字符是 `b`，所以对 `a` 的正向先行断总是为假的。因此，单独的 `b` 就能匹配相同的结果。 |
| `a++abc` | 这是不可能的。由于 `a++` 是所有有的，它会耗尽所有连续的 `a` 实例，所以后面不能有另一个了。 |

**表 10.7**](#c10.xhtml_R_c10-tbl-0007): 正则表达式错误示例

`SonarQube` 还有一条规则确保你的正则表达式不要太复杂。正则表达式是你工具箱里的一种工具，而不是用于每项任务的工具！

## 使用正则表达式编写代码

在本章开头，你看到了三个 URI 和一个声明，即正则表达式可以轻松分离协议、网站或目录以及特定路径。现在是学习如何做了。考虑以下代码：

```
10: String uris = """
11:    http://spring.io/projects/spring-cloud-contract
12:    https://www.infoq.com/articles/Living-Matrix-Bytecode-Manipulation/
13:    file:///C:/Documents/happy_birthday_sis.pdf
14: """;
15:
16: String twoOrMoreSlashes = "/{2,}";
17: String matchAny = "(.+)";
18: String matchAnythingButSlash = "([^/]+)";
19: String regex = matchAny + ":" + twoOrMoreSlashes 
20:    + matchAnythingButSlash + "/" + matchAny;
21:
22: Pattern pattern = Pattern.compile(regex, Pattern.MULTILINE);
23: Matcher matcher = pattern.matcher(uris);
24: while (matcher.find()) {
25:    String protocol = matcher.group(1);
26:    String websiteOrDirectory = matcher.group(2);
27:    String specificPath = matcher.group(3);
28:    String formatted = "%s\t%s\t%s".formatted(protocol, 
29:       websiteOrDirectory, specificPath);
30:    System.out.println(formatted);
31: }
```

该程序的输出正是要求的要求的。

```
httpspring.ioprojects/spring-cloud-contract
httpswww.infoq.comarticles/Living-Matrix-Bytecode-Manipulation/
fileC:Documents/happy_birthday_sis.pdf
```

第 10–14 行创建了一个我们想要测试的 URI 的文本块。第 16–19 行使用自文档变量清晰地解释了我们想要匹配的内容。第 16 行为匹配两个或多个斜杠字符提供了英文描述。第 17 行匹配一个或多个字符，捕获结果以供以后匹配。第 18 行匹配除斜杠以外的多个字符，同样捕获结果。

第 19–20 行将这些子表达式组合成最终的正则表达式。第 22–23 行创建了 `Pattern` 和 `Matcher`。最后，第 24–27 行遍历三个匹配的 URI 中的每一个，并获取所需信息的匹配组。

作为另一个例子，在之前一章中，你需要解析关于虚拟线程的信息。使用正则表达式实现此点的有两种良好方法。一种是使用与之前示例类似的方法，使用 `Pattern` 和 `Matcher`。

```
String text = "VirtualThread[#22]/runnable@ForkJoinPool";
```

JUnit Pioneer 库也支持正则表达式。例如，你可以根据显示名称（display name）禁用测试。在这种情况下，代码禁用了任何名称较长的月份测试：



```
static List<String> months() {
   return List.of("January", "February", "March", "April", "May",
      "June", "July", "August", "September", "October",
      "November", "December");
   }

@DisableIfDisplayName(matches = "^Month: \\w{6,}$")
@ParameterizedTest(name = "Month: {0}")
@MethodSource("months")
void shortMonths(String reason) {
    // test short month name
}
```

### 为 Log4j 编写正则表达式

有时，你需要超越日志级别来限制 Log4J 记录的内容。一种称为 `filters`（过滤器）的功能允许你根据消息中的值来自定义记录的内容。假设你的审计部门不允许你记录 `secret` 单词。你可以在应用渲染器（appender）上设置一个过滤器，按如下方式跳过整行：

```
<RegexFilter regex=".* secret .*" onMatch="DENY" onMismatch="ACCEPT"/>
```

上面的代码告诉 Log4J 跳过任何包含两边带有空格的 `secret` 的消息。

### 为 Bean Validation 编写正则表达式

Bean 验证框架提供了许多验证器来检查 JavaBean 是否具有预期的值。

其中一个验证器之一是 `@Pattern`，它使用正则表达式：

```
import jakarta.validation.constraints.Pattern;

public class Bean {

    @Pattern(regexp = "[A-Z]+")
    private String uppercaseLetters;

    public String getUppercaseLetters() {
        return uppercaseLetters;
    }

    public void setUppercaseLetters(String uppercaseLetters) {
        this.uppercaseLetters = uppercaseLetters;
    }
}
```

在这个示例中，如果 `uppercaseLetters` 包含小写字母或任何非字母字符，验证将失败。

### 为 Spring 编写正则表达式

Spring 在 Spring MVC 中使用正则表达式来帮助获取 URL 的部分并将其转换为变量。例如，在这个控制器中，一组数字被匹配并赋值给变量 `bookId`：

```
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class TheController {

   @RequestMapping("/book/{bookId:[0-9]+}")
   public String getBookById(@PathVariable("bookId") String bookId) {
      String result = // build return value
      return result;
   }
}
```

在前面的代码中，Spring 获取类似 `/books/469` 的 URL 并将 469 存储在 `bookId` 参数中。使用正则表达式可以让你在指定应该匹配的格式时具有很大的灵活性。

## 进一步参考

* [`https://www.pluralsight.com/courses/playbook-regular-expressions-java-fundamentals`](https://www.pluralsight.com/courses/playbook-regular-expressions-java-fundamentals)

    * Victor 在 Pluralsight 正则表达式课程

* [`https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/regex/Pattern.html`](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/regex/Pattern.html)

    * Java Pattern 文档

* [`https://regex101.com`](https://regex101.com)

    * Regular Expression Tester

* [`https://commons.apache.org/proper/commons-csv`](https://commons.apache.org/proper/commons-csv)

    * Apache Commons CSV

* [`https://opencsv.sourceforge.net`](https://opencsv.sourceforge.net)

    * Open CSV

* [`https://commons.apache.org/proper/commons-validator`](https://commons.apache.org/proper/commons-validator)

    * Apache Commons Validator

* [`https://regexcrossword.com`](https://regexcrossword.com)

    * 用于更好地学习正则表达式的交叉字谜。

* *Introducing Regular Expressions* (O'Reilly, 2012)

* *Regular Expressions Cookbook* (O'Reilly, 2012)

## 总结

在本章中，你学习了如何编写正则表达式。要点包括以下：

* 字符类是一种简写，这样你就不逐个列出感兴趣的每一个字符。

* 贪婪、懒惰和迟疑的量词允许你改变匹配行为。

* 正向和负向的前瞻和后向断言允许你根据周围的文本限制匹配。

* 内置的 Java API 支持正则表达式。

* 正则表达式也用于库中。

# 11

## 以面向切面的方式编码

并不是你所有的 Java 代码都写在你的 Java 代码中。虽然这个悖论听起来像某个禅公案，但它有效地为本章关于 `aspects`（切面）编码的章节奠定了基础，切面是正交函数，当满足某些条件时可以触发执行。我们将展示切面的益处以及如何编写你自己的切面。

## 理解切面的必要性

想象一下以下场景——你收到一个新需求，修改每个 REST 端点，使其从捕获开始时间并记录消息开始，以记录调用时间结束。

```java
public void someEndpoint(){
   long start = System.currentTimeMillis();
   log.info("Starting someEndpoint");

   // 执行一些操作

   long duration = System.currentTimeMillis() - start;
   log.info("Completed someEndpoint. Execution duration:{}ms", duration);
}
```

现在，你可以将代码复制粘贴到每个端点，但没有人会因为这种编码而获得奖励。你能在一个地方完成吗？你可以使用面向切面编程（AOP）来实现这一点！在本章中，我们将介绍 Spring AOP。AspectJ 更强大，但 Spring AOP 适用于大多数企业场景。

主意是创建一个切点（pointcut），即描述哪些成员将被修改的模式。

在继续之前，让我们先涵盖一些术语。

* **Advice（建议）：** 定义到达连接点时要执行的操作。

* **Join point（连接点）：** 代码中插入切面的实际点。

* **Pointcut（切点）：** 定义匹配位置模式的表达式。

以下是建议的类型：

* `@Before`: 在方法开始之前执行。

* `@AfterReturning`: 在方法成功完成后执行。

* `@AfterThrowing`: 在方法抛出异常后执行。

* `@After`: 在方法完成（无论成功还是异常）后执行。

* `@Around`: 能够完全控制何时调用方法以及返回什么的调用。

一个例子胜过千言万语。让我们创建一个带有几个端点的 Spring Boot MVC 项目。我们将使其成为产品目录。

## 创建我们的第一个示例

老板来到你的办公桌带回一个新需求：“你知道我们一直在编写的产品控制器吗？我们希望在每次调用 `addProduct` 方法时都记录一条消息。” 现在这个需求看起来简单，但他还告诉我们，所有的端点都有类似的需求。然后我们得知日志将变得有点复杂，因此复制粘贴不是解决方案。而且，我们想要整洁的代码，所以我们绝对不想在每个方法中仅仅复制和粘贴日志。

原始代码如下：

```java
@RestController
public class ProductController {

   private final Map<String, Product> productMap = new HashMap<>();

   @PostMapping("/product")
   public void addProduct(@RequestBody Product product) {
      productMap.put(product.getStyleNum(), product);
   }

   @DeleteMapping("/product")
   public Product removeProduct(String styleNumber){
      return productMap.remove(styleNumber);
   }

   @GetMapping("/product")
   public Collection<Product> listProducts(){
      return productMap.values();
   }
}
```

让我们利用 Spring AOP 的魔法来添加老板要求的日志记录。第一步是创建一个 `aspect`（切面）组件，它定义了描述要拦截方法的切入点（pointcut）模式，以及在命中切入点时提供执行代码的通知（advice）实现。切面类就是一个标准的 Java 类，同时标记了 `@Aspect` 和 `@Component` 注解。记得在你的类中导入这些包：

```
import org.aspectj.lang.JoinPoint;
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Before;
import org.springframework.stereotype.Component;
```

然后我们有这样一个类：

要运行应用程序，请使用 Postman 或 `curl`。（记得查看 `README.md` 文件中的完整说明。）使用此处显示的参数进行 `POST` 调用。

### 端点 (Endpoint):

```
POST localhost:8081/product
```

### 请求体 (`Application/Json`):

```
{
    "styleNum": "123",
    "description": "IPhone"
}
```

运行应用程序并触发该端点以添加产品；你将看到包含日志消息的输出：

```
===============> called addProduct
```

这是一个简单的示例，但它展示了切面的美之处。你可以拦截对代码的调用并采取行动，而无需接触被插桩的代码！

### 这里发生了什么？让我们查看图 11.1 中的序列图。

![一个序列图包含行排的四个块，标记如下：1. 消费者应用程序。2. AOP 代理。3. AOP 通知。4. 目标应用程序。块之间的请求和响应用箭头线表示。](img/c11f001.png)

[图 11.1: 序列图

Spring 看到了你的 `@Aspect` 注解并引入了一个不可见的 AOP 代理类。该代理类评估接点点（join point）并委托给适当的通知。通知被触发，并在过程中调用了目标方法。

此外，关于列表 11.1 中之前的切面，还有一些重要的点需要观察。

*   `@Before` 注解告诉运行时在调用方法*之前*（before）调用此代码。

*   要调用的方法体 `logAddOperations()` 被称为 `advice`（通知）。

*   以 `execution` 开头的部分定义了切入点：用于匹配方法的模式（匹配的方法称为 `join point` 即接点），以应用此 `advice`。

这就是 AOP 的通用流程。让我们仔细查看这些 API。你会发现 `JoinPoint` 类有几个非常有用的访问器。这里显示的是 `getSignature().getName()`。让我们看看其他 API 如 `getArgs()`。

*   返回一个包含所有参数的 `Object[]`。例如：

    ```
    Product{styleNum='123', description='IPhone'}]
    ```

*   `getKind()`：返回调用类型的 `String` 字符串表示形式。例如：

    ```
    method-execution
    ```

*   `getThis()` 和 `getTarget()`：返回包含被插桩方法的类的实例 `toString()`。例如：

    ```
    com.wiley.realworldjava.aop.product.ProductController@29b5747 
    - 被插桩的实例
    ```

*   `toLongString()`：返回切入点的完整表示。例如：

    ```
    execution(public com.wiley.realworldjava.aop.product.Product com.wiley
    .realworldjava.aop.product.ProductController.addProduct(com.wiley
    .realworldjava.aop.product.Product))
    ```

*   `toShortString()`：返回切入点的短格式表示形式。例如：

    ```
    execution(ProductController.addProduct(..))
    ```

*   `toString()`：返回切入点的中间 `String` 表示形式。例如：

    ```
    execution(Product com.wiley.realworldjava.aop.product.
    ProductController.addProduct(Product))
    ```

*   `getSignature()`：`Signature` 是一个包含更多调用详细信息的类。例如：

    ```
    Product com.wiley.realworldjava.aop.product.ProductController
    .addProduct(Product)
    ```

*   `getStaticPart()`：`StaticPart` 仅包含关于接点的静态信息。例如：

    ```
    execution(Product com.wiley.realworldjava.aop.product.
    ProductController.addProduct(Product))
    ```

一个重要的陷阱是，Spring AOP 只会对 Spring 管理的类进行插桩，例如 `Component`、`Bean`、`Service` 等。如果这些数据是参数或返回值，你的通知可以引用未受 Spring 管理的其他数据。你很快就会看到一些示例，但切入点必须引用 Spring 管理的方法。

## 探索切入点表达式语言

现在示例中的切入点表达式看起来像头可怕的猛兽，但一旦你了解它，它其实非常温顺。

让我们在图 11.2 中更仔细地观察它。

*   `@Before("execution(`：告诉切面匹配任何方法。

*   `public`：返回类型。

*   `com.wiley.realworldjava.aop.product.ProductController`：全限定类名。

*   `.addProduct`：方法名。

*   `(..)`：参数列表。

![切入点表达式包含以下参数。执行前调用通知、仅匹配公共方法、返回类型、全限定类名、方法名和参数列表。](img/c11f002.png)

[图 11.2: 切入点表达式

### 通配符

可以使用 `*` 作为通配符匹配方法、类或包名中的任意范围。例如：

*   方法通配符：`execution(* add*(..))` 匹配以 `add` 开头的任何方法。

*   包通配符：`execution(* com.wiley.realjava..())` 匹配 `com.wiley.realjava` 或其任何子包。



### 类名通配符

`execution(* your.package.name.*Controller*(..))` 匹配类名中包含 `Controller` 的任何方法。

同样你可以在返回类型中指定 `*`。

例如，以下内容将匹配任何以 `Pr` 开头并以 `ct` 结尾的 `ProductController` 方法。因此，它将匹配 `Product`、`Prospect` 和 `Predict`！

```
com.wiley.realworldjava.aop.product.Pr*ct com.wiley.realworldjava.aop.
product.ProductController.addProduct(..)
```

### `..` 通配符

你已经知道如何使用 `(..)` 匹配方法参数列表中的一个或多个参数。你也可以使用该符号匹配包或其任何子包中的任何方法。通常，`..` 表示指定位置上的零或多个元素。

例如，以下内容匹配 `com.wiley.realworldjava.aop.product` 包或其任何子包中的任何方法：

```
execution(* com.wiley.realworldjava.aop.product..*Controller*()) 
```

### 使用 `@AfterReturning`

`@AfterReturning` 在方法成功返回（即没有抛出异常）后执行。这对于日志记录等情况非常有用，但当你想要对方法处理的数据进行后处理时，它特别有用。

按照你已经学会的方法开始编写执行切入点，只需将其标记为 `@AfterReturning` 即可。

```
@AfterReturning(pointcut =   "execution(public * com.wiley.realworldjava.aop.product."
   +"ProductController.addProduct(com.wiley.realworldjava.aop.product.Product))")
public void logAfterReturning(JoinPoint joinPoint){
   logger.info("=====> called after returning {}",       joinPoint.getSignature().getName());
}
```

`addProduct()` 的调用会显示在日志中。

```
=====> called after returning addProduct
```

这将允许你执行日志记录等操作，但如果你需要返回值怎么办？

为此，你可以对切入点应用一些“签名魔法”来包含返回值，如下所示：

```
@AfterReturning("execution(public * com.wiley.realworldjava.aop.product."
  + "ProductController.addProduct(com.wiley.realworldjava.aop.product.Product))",   returning = "product")
public void logAfterReturning(JoinPoint joinPoint, Product product){
   logger.info("===> called after returning {}  returned:{}", 
      joinPoint.getSignature().getName(), product);
}
```

现在 `addProduct()` 的调用会显示在日志中。

```
 ===> called after returning addProduct  returned:Product{styleNum=’123’, 
  description=’IPhone’}
```

`@AfterReturning` 建议允许你调整返回值并将调整后的值返回给用户。例如，假设需求是返回大写形式的描述。该建议可以写如下所示：

```
@AfterReturning (value = 
   "execution(public * com.wiley.realworldjava.aop.product."
   + "ProductController.addProduct(com.wiley.realworldjava.aop.product.Product))",
   returning = "product")
public void descriptionToUpperCase(JoinPoint joinPoint, Product product){
   logger.info("===> called after returning {}. Returned {}.",
      joinPoint.getSignature().getName(), product) ;
   product.setDescription(product.getDescription().toUpperCase());
}
```

### 使用 `@AfterThrowing`

该建议仅在被监控的方法通过抛出异常异常结束结束时被触发。你可以通过在方法调用中使用 `throwing` 参数并添加异常来捕获它。

让我们向 `ProductController` 类中添加以下内容以模拟异常。调用 `/products-exception` 端点将始终抛出一个 `IOException`。

```
 @GetMapping("/products-exception")
   public Collection<Product> listProductsWithException() throws IOException {
      throw new IOException("An IOException to handle");
   }
```

现在，在你的 `LoggingAspect1` 类中添加以下切入点：

```
 @AfterThrowing(value = "execution(public * com.wiley.realworldjava.aop.product."
      + "ProductController.listProductsWithException())", throwing = "cause")
   public void logAfterReturning(JoinPoint joinPoint, Throwable cause){
      logger.info("===> called after throwing {}. Throwing:{}",
         joinPoint.getSignature().toShortString(),cause) ;
   }
```

在这种情况下，我们在方法中捕获了 `Throwable` 引起。使用 Postman 向我们的新端点发送一个 `GET` 调用。

```
localhost:8081/products-exception
```

你将在日志中（堆栈跟踪之前看到以下内容：

```
===> called after throwing ProductController.listProductsWithException().
   Throwing: java.io.IOException: An IOException to handle
```

### 使用 `@After`

`@After` 类似于 `@AfterReturning` 和 `@AfterThrowing`，区别在于你无法访问结果或任何抛出的异常。它适用于通用的方法结束清理、日志记录或可观测性捕获等场景。

### 使用 `@Around`

`@Around` 为被监控的方法提供了更细粒度的访问。通过 `@Around`，你可以在方法调用之前和之后进行织入，修改任何结果，处理或修改任何异常，甚至完全跳过目标调用。

这的一个很有用用例是为方法提供缓存。假设我们有一个方法，其结果是懒加载的（这意味着结果在第一次调用时计算并保存到缓存中供后续使用）。例如一个与多个数据库通信的应用程序，我们希望懒加载不会改变的连接信息。

让我们在 `ProductController` 中添加一个名为 `/connection` 的新 `POST` 端点。

```
 @PostMapping("/connection")
   public Connection getDbConnection(@RequestBody Properties config) 
      throws SQLException, ClassNotFoundException {

      Connection connection = createDBConnection(config.getProperty("driver"), 
         config.getProperty("url"), config.getProperty("username"), 
         config.getProperty("password"));

      return connection;
   }
```

该思路是使用包含如下连接信息的 JSON 负载负载调用此端点：

```
{
    "driver": "com.mysql.cj.jdbc.Driver",
    "url":"jdbc:mysql://localhost:3306/products",
    "username":"vgrazi",
    "password":"pa55w0rd"
}
```

原始实现将为每次调用创建一个新连接，这是一种资源密集型设计。

让我们用 AOP 纠正这一点，使用 `@Around` 建议，在每组 `Properties` 第一次调用该方法时懒加载相应的连接，然后将其保存到缓存中供后续调用。

```
 1:  private final Map<String, Connection> connectionCache = new HashMap<>();
 2:
 @Around("execution(public * com.wiley.realworldjava.aop.product."
      + "ProductController.getDbConnection(Properties))")
 3:  public Connection cacheConnection(ProceedingJoinPoint joinPoint) 
 4:     throws Throwable {
 5:     Object[] args = joinPoint.getArgs();
 6:     Properties properties = (Properties) args[0];
 7:     Connection connection = connectionCache.get(properties.getProperty("url"));
 8:     if(connection==null) {
 9:        logger.info("Nothing cached. Aspect proceeds with the original call!");
 10:       try {
 11:           connection = (Connection) joinPoint.proceed();
 12:           logger.info("Aspect caches the connection for future calls");
 13:           connectionCache.put(properties.getProperty("url"), connection);
 14:       } catch(Throwable throwable) {
 15:          logger.error("cacheConnection threw exception", throwable);
 16:          throw throwable;
 17:       }
 18:    } else {
 19:       logger.info("Aspect got connection from cache!");
 20:    }
 21:    return connection;
 22: }
```

在第 1 行，我们创建了一个本地缓存供建议使用。注意此实例对 `ProductController` 是不可知的。

在第 3 行，我们为 `getDbConnection` 方法创建了一个标准的切入点表达式。注意我们使用了 `@Around` 建议。在第 5 行的方法签名中，我们返回与目标调用相同的类型，在此例中为 `Connection`。此外注意我们将常用的 `JoinPoint` 实例替换为了 `ProceedingJoinPoint`。这对于 `@Around` 是必须的，以便我们可以调用 `proceed` 方法来执行目标方法。

在第 5 行，我们拦截了调用参数，使用它们来检查缓存中是否存在实例，我们在第 7 行中这样做。

在第 8 行，如果缓存为空，我们在第 9 行记录一条信息“没有缓存。建议继续执行原始调用！”。在第 10 行，我们进入 `try` 块，在第 11 行通过调用 `joinPoint.proceed()` 执行目标方法。这会触发目标方法。我们在第 12 行记录“建议缓存该连接”，并在第 13 行将该连接存入缓存。在第 14 行，如果目标方法抛出任何异常，它将在 `catch` 块中被捕获并在第 16 行将其抛回给调用者。

在第 18 行，如果缓存中存在连接，我们在第 19 行记录“建议从缓存中获取连接！”。最后，在第 21 行，我们返回该连接。

但你应该谨慎地使用它。如果你的开发团队没有意识到这一点，他们可能会浪费大量沮丧的开发周期，试图理解为什么他们的产品描述被转换成了大写、为什么断点（breakpoints）没有触发，或者为什么他们的方法调用是从缓存中读取的而不是运行它们的实现！

### 使用 `@Pointcut`

现在是讨论复用的好时机了。假设你想创建一个用于日志的 `@Before` 建议、一个用于记录时间的 `@After` 建议，以及一个用于缓存的 `@Around` 建议。你必须重复编写三次执行切入点！最糟糕的是，如果你想对切入点进行微小的更改，你需要记住所有需要修改的地方。这时 `@Pointcut` 注解登场了。`@Pointcut` 允许你为切点表达式指定一个短名称，然后使用该名称来代替切点表达式。

如果你正在跟着代码操作，你会注意到我们一直在使用 `LoggingAspect1` 类。为了继续示例，请注释掉 `LoggingAspect1` 第 16 行的 `@Aspect` 建议。

```
16: //@Aspect
17: @Component
18: public class LoggingAspect1 {
19:    private final Logger logger = LoggerFactory.getLogger(LoggingAspect1.class);
```

然后取消 `LoggingAspect2` 第 15 行中 `@Aspect` 建议的注释。

```
15: @Aspect
16: @Component
17: public class LoggingAspect2 {
```

这种注释/取消注释的操作会将 `LoggingAspect1` 中的 AOP 代理替换为 `LoggingAspect2` 中的修订版本，以便你继续跟随。以下代码行引用 `LoggingAspect2`。

让我们回顾一下之前 `@AfterReturning` 部分的切点表达式。

该表达式如下：

```
@AfterReturning(value = "execution(public * com.wiley.realworldjava.aop.product."
"ProductController.addProduct(com.wiley.realworldjava.aop.product.Product))")
)
public void logAfterReturning(JoinPoint joinPoint, Product product){
   System.out.println("=============> called after returning " +   
     joinPoint.getSignature().getName());
}
```

你可以使用 `@Pointcut` 注解来标注一个定义执行的方法，然后在任何需要的地方引用该方法，以代替实际的 `execution` 切入点。

这种范式如下：不要在建议注解中指定执行，，而在一个空方法上指定执行。该方法不会被执行，但它仍然很重要，因为现在该方法名可以用来代替显式的执行表达式。

在下面的示例中，原始的 `execution` 表达式被移动到 `addProductPointcut` 方法中。因此，之前的代码段将更改为以下同名切点：

```
// 定义一个名为 "addProductPointcut" 的空切点方法
@Pointcut(value = "execution(public * com.wiley.realworldjava.aop.product."
   + "ProductController.addProduct(com.wiley.realworldjava.aop.product.Product))")
public void addProductPointcut() {}

// 我们的建议方法 (@AfterReturning) 现在可以引用空切点方法，
// 而不是内联执行
@AfterReturning(value = "addProductPointcut()", returning = "product")
public void logAfterReturning(JoinPoint joinPoint, Product product){
    . . .
}
```



接的 REST 端点将触发该建议：

```
@PostMapping("/product")
public Product addProduct(@RequestBody Product product) {
   logger.info("Adding product {}", product);
   productMap.put(product.getStyleNum(), product);
   return product;
}
```

现在你可以复用该切入点来重新定义你的 `@AfterThrowing` 和 `@After` 建议。

```
@AfterReturning(value = "addProductPointcut()", returning = "product")
public void logAfterReturningWithReturningValue(JoinPoint joinPoint,    Product product) {
   logger.info("=====> called after returning {}  returned:{}",
     joinPoint.getSignature().getName(), product);
}

@AfterThrowing(value = "addProductPointcut()", throwing = "cause")
public void logAfterReturningWithException(JoinPoint joinPoint, Throwable cause) {
   logger.info("=====> called after throwing {}. Throwing:",      joinPoint.getSignature().toShortString(), cause);
}
```

## 组合切点

既然你已经知道切点可以命名，你就可以通过`&&`（与）、`||`（或）和`!`（非）运算符组合切点来做一些有趣的事情。

假设你定义了方法`pointcutA()`和`pointcutB()`。你可以使用`||`（或）运算符将它们组合成单一建议，如果匹配到`pointcutA()`或`pointcutB()`中的任何一个，它就会被调用。

例如：

```
@Pointcut(pointcutA() || pointcutB())
public void combinedOrPointcut() {
    // 如果 pointcutA() 或 pointcutB() 任一匹配，则被调用
}
```

同样，你可以使用`&&`（与）运算符，仅当两个切点都匹配时才调用。

```
@Pointcut(pointcutA() && pointcutB())
public void combinedAndPointcut() {
    // 当 pointcutA() 和 pointcutB() 都匹配时，被调用
}
```

或者你可以在`pointcutB()`不匹配时调用`pointcutA()`。

```
@Pointcut(pointcutA() && !pointcutB())
public void NotPointcut() {
    // 当 pointcutA() 匹配且 pointcutB() 不匹配时，被调用
}
```

### 基于注解的切点

你是否想过 Spring 的“魔法”配置是如何工作的？根据你所学，Spring、Lombok、JCache 以及许多其他框架在后台使用 AOP。但你从未见过这样的切点表达式。相反，它们使用自己的注解。我们如何做到这一点？

答案是你可以使用`@annotation`切点来创建注解。

例如，假设我们要重写建议以供任何需要缓存的调用复用。创建一个名为`@Cache`的新注解。第一步是创建注解类。

```java
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Cache {
}
```

接下来，将新的`@Cache`注解与切点关联。

```java
@Pointcut("@annotation(com.wiley.realworldjava.aop.Cache)")
public void cacheAnnotationMethod(){
}
```

然后，提供一个被调用的建议。

```java
@Around("cacheAnnotationMethod()")
public Object cacheMethodResults(ProceedingJoinPoint joinPoint) throws Throwable {
   // 每个唯一的参数组合都将单独缓存。
   // 创建代表参数的 MultiKey
   // (MultiKey 允许定义任意数量的组件):
   Object[] args = joinPoint.getArgs();
   Object[] argsLong = new Object[args.length + 1];
   System.arraycopy(args, 0, argsLong, 1, args.length);
   // 我们希望单独缓存不同的方法，
   // 所以将方法和签名作为数组的第一个元素添加到 MultiKey 中：
   argsLong[0] = joinPoint.toLongString();
   MultiKey key = new MultiKey(argsLong);

   Object result = methodCache.get(key);
   if(result==null) {
      logger.info("无缓存。Aspect 执行原始调用!");
      try {
         result = joinPoint.proceed();
         logger.info("Aspect 缓存了后续调用的连接");
         methodCache.put(key, result);
      } catch(Throwable throwable) {
         throw throwable;
      }
   }
   else {
      logger.info("Aspect 从缓存中获取了连接!");
   }
   return result;
}

// 并创建 Map 来捕获缓存结果
private final Map<String, Object> methodCache = new HashMap<>();
```

最后，在你任何想要调用它的的地方应用新的注解。

```java
@Cache
@PostMapping("/connection")
public Connection getDbConnection(@RequestBody Properties config) 
   throws SQLException, ClassNotFoundException {
   Connection connection = createDBConnection(config.getProperty("driver"),
   config.getProperty("url"), config.getProperty("username"),
   config.getProperty("password"));
   return connection;
}
```

现在调用`getDbConnection()`将在第一次调用时创建一个新连接，并在后续调用中返回缓存版本。

尝试使用以下 Postman `POST` 请求体进行测试：

```json
{
    "driver": "com.mysql.cj.jdbc.Driver",
    "url":"jdbc:mysql://localhost:3306/products",
    "username":"vgrazi",
    "password":"pa55w0rd"
}
```

让我们来看`@Around`的另一个常见示例。我们将定义一个名为`@Timing`的注解，它将记录标记了`@Timing`的方法调用的执行时间。

```java
@Pointcut("@annotation(com.wiley.realworldjava.aop.aspects.Timing)")
public void timingAnnotationMethod(){
}

@Around("timingAnnotationMethod()")
public Object cacheTimingResults(ProceedingJoinPoint joinPoint) throws Throwable {
   // 获取开始时间
   long start = System.currentTimeMillis();
   // 执行目标方法…
   Object result = joinPoint.proceed();
   // 获取结束时间
   long end = System.currentTimeMillis();
   // 记录计时信息
   logger.info(">>>> Call to {} took {} ms.", joinPoint.toString(), end-start);
   // 返回调用结果
   return result;
}
```

注意，此方法返回了一个结果。如果它被应用于`void`方法会怎样？答案是`joinPoint.proceed()`调用将返回`null`，最终的返回结果调用也将返回`null`，调用者会忽略它，因为他们期望的是`void`返回值。

## 进一步参考

* [`https://docs.spring.io/spring-framework/reference/core/aop.html`](https://docs.spring.io/spring-framework/reference/core/aop.html)

    Spring AOP 的完整文档

* [`https://eclipse.dev/aspectj`](https://eclipse.dev/aspectj)

    AspectJ 的文档，一个更广泛的、适用于非 Spring 项目的切面框架

## 总结

以下是本章的核心要点：

* 切面（Aspects）允许你指定切入点（pointcut），描述要拦截哪些方法以及在拦截方法调用时采取什么操作。

* 接入点（join point）是代码插入的地方。

* 切入点可以命名以便重用，并可以使用`&&`、`||`和`!`进行组合。

* 主要通知类型有`@After`、`@AfterReturning`、`@AfterThrowing`、`@Around`和`@Pointcut`。

# 12 监控你的应用程序：Java 生态可观测性

在生产系统中，问题总会发生。当问题发生时，你希望尽早发现……越早越好！监控你的应用程序对于确保用户获得良好且有益的体验至关重要。你需要了解应用程序内部运行机制以理解发生了什么，而某些工具正是为了提供这种可见性设计的。

在本章中，我们将探索一些流行的开源工具。

## 介绍可观测性

监控只是可观测性的一个组成部分。什么是可观测性？在本章中，我们将探索该领域一些流行的开源工具。为了明确起，可观测性涉及以下关键组件：

* **指标（Metrics）**：用于量化事件的数据单元。

* **告警（Alerting）**：当阈值被值时的自动通知。

* **仪表板（Dashboarding）**：指标的实时可视化。

* **日志（Logging）**：中心化的日志消息。

* **追踪（Tracing）**：跨服务的请求流。

收集指标有两种方法：推送（pushing）和抓取（scraping）。*推送*意味着应用程序配置为将指标发送到数据库。*抓取*是一种拉取技术，由 Prometheus 询问端点。

## 上手 Prometheus

在本章中，我们将介绍使用抓取模式的 Prometheus。如果你已经有了访问 Prometheus 的权限，可以尝试，但我们强烈建议你安装它。

### 启动测试应用程序

本章的仓库包含一个 Spring Boot 测试应用程序`ObservabilityApplication`。要启动它，请运行以下：

```bash
mvn clean verify
java -jar observability-0.0.1-SNAPSHOT.jar
```

你可以通过访问此 URL 来验证它正在运行：

`http://localhost:8081/actuator/prometheus`

该应用程序的 POM 文件包含`micrometer-registry-prometheus`依赖。此依赖会自动暴露以下端点：

`http://localhost:8081/actuator/prometheus`

访问到此 URL 查看暴露给 Prometheus 的完整指标列表。

### 安装导出器（Exporter）

Prometheus 有各种导出器，这些插件与你的应用程序、中间件和基础设施协同工作，以暴露相关指标供 Prometheus 抓取。流行的例子包括适用于 Linux/Mac 系统的 Node Exporter 以及适用于 Windows 的 Windows Exporter。在开发企业级应用程序时，你可能需要在想要监控的计算机/服务器上运行导出器，而该机器通常不是运行程序本身的实例。

这些导出器被配置为监控节点，从节点中捕获指标并以 Prometheus 可以抓取的格式暴露它们。有数百个这样的指标，包括 CPU 利用率、磁盘占用、内存消耗等等。

虽然你可以直接安装在计算机上，但我们在本章中使用了一个 Docker 容器，以确保读者的设置保持一致。如果你想复习 Docker 的使用，请参见第 4 章的 Jenkins 部分。

在本节中，我们将使用 Docker 和 Linux 镜像设置 Node Exporter。启动 Docker Desktop 后，可以执行以下命令拉取镜像：

```bash
docker pull prom/node-exporter
```

不过这并不是严格要求的。`run`命令会在镜像不存在时自动拉取。要运行 node exporter 容器，请调用以下：

```bash
docker run --name=node_exporter -p 9100:9100 prom/node-exporter
```

Node Exporter 默认运行在端口`9100`上。要验证导出器是否正在运行，请访问`http://localhost:9100`。你会看到一个包含版本号的网页，如下：

```
Version: (version=1.8.2, branch=HEAD,
revision=f1e0e8360aa60b6cb5e5cc1560bed348fc2c1895)
```

URL `http://localhost:9100/metrics`暴露了导出器导出的所有指标。如果这看起来像是一堆乱码，不要担心；那是 Prometheus 的抓取格式，我们很快就会对其进行解释。

## 安装 Prometheus

Prometheus 二进制文件跟踪指标并包含一个用于查询的 UI。

首先，运行以下命令：

```
docker pull prom/prometheus
```

从 第 12 章 仓库的根目录将`prometheus.yml`文件复制到你的工作目录。我们将在下一节解释这个文件。在 Windows 上运行以下命令：

```bash
docker run --name prometheus -p 9090:9090 -v .\prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus
```

或者对应 Mac/Linux 的命令：

```bash
docker run --name prometheus -p 9090:9090 -v ./prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus
```

Docker 的`-v`标志代表卷（volume）。它允许你将本地计算机上的 Docker 文件或目录映射到 Docker 容器。在这种情况下，它允许你提供自己的`prometheus.yml`文件。我们从 Prometheus 发行版中复制了它并进行了一些修改。

Prometheus 默认运行在端口`9090`。你可以访问`http://localhost:9090`来确认 Prometheus 已正确启动。正如你想象，初始启动之后你应该运行`docker start prometheus`。

## 配置抓取

在上一节中，你引用了 YAML 配置文件`prometheus.yml`。（关于 YAML 的更多信息，请参阅附录）。该文件配置你的 Prometheus 以识别你的导出器和其他应用程序，以便它知道去抓取它们。

在`prometheus.yml`的`scrape_configs`下，你可以看到由 Prometheus 提供的以下代码。我们添加了粗体行。



```
21: scrape_configs:
22:    # job 名称作为标签 `job=<job_name>` 添加
23:    # 到任何从此配置抓取的时间时间序数据中。
24:    - job_name: "prometheus"
25:
26:      # metrics_path 默认为 '/metrics'
27:      # scheme 默认为 'http'
28:
29:      static_configs:
30:         - targets: ["localhost:9090"]
31:
32:    - job_name: "node_exporter"
33:      static_configs:
34:         - targets: ["host.docker.internal:9100" ]
35:
36:
37:    - job_name: "mtg-calc"
38:      static_configs:
39:         - targets: ["host.docker.internal:8081" ]
40:      metrics_path: '/actuator/prometheus'
```

第 24 行的第一个抓取配置任务名为 `prometheus`。Prometheus 是自感知的，因此它导出自己的指标，这就是我们配置 Prometheus 抓取自己的地方。

第 32–34 行配置 Prometheus 抓取 `node_exporter`，第 37–40 行告诉它抓取 Spring Boot。第 34 行和 39 行使用 `host.docker.internal`，这是 Docker 引用主机机器的方式。否则，它将在 Prometheus 容器内部查找端点。

让我们探索 Prometheus 界面。从浏览器窗口启动 `http://localhost:9090` 上的 Prometheus Web。选择 Status（状态）➪ Configuration（配置）以查看此实例中配置的所有抓取任务，如图 12.1 所示。注意我们在之前的 YAML 中配置的两个 job 名称都在此截图中。

![一个名为 Prometheus 的窗口截图。标签页包括 alerts、graphs、status 和 help。status 标签被选中。出现下拉菜单。配置选项被高亮显示。](img/c12f001.png)

图 12.1: Prometheus 配置标签页

选择 Status ➪ Targets（目标）以查看抓取目标的健康状况，如图 12.2 所示。

![prometheus 界面截图，显示了三个目标：mtg-calc、node_exporter 和 prometheus，每个目标都有其端点、状态、标签、最后抓取时间和时长。所有目标都标记为 UP，表示它们健康且运行正常。](img/c12f002.png)

图 12.2: Prometheus 目标标签页

## 介绍 PromQL：Prometheus 查询语言

Prometheus 的持久化层是一个时间序数据库，你可以使用名为 PromQL 的语言对其进行查询。

Prometheus 查询语言 (PromQL) 允许用户进行查询。

Prometheus 查询语言 (PromQL) 允许用户进行查询。

Prometheus 的持久化层是一个时间序数据库，你可以使用名为 PromQL 的语言对其进行查询。

Prometheus 查询语言 (PromQL) 允许用户进行查询。

Prometheus 的持久化层是一个时间序数据库，你可以使用名为 PromQL 的语言对其进行查询。

Prometheus 查询语言 (PromQL) 允许用户进行查询。

Prometheus 的持久化层是一个时间序数据库，你可以使用名为 PromQL 的语言对其进行查询。

Prometheus 查询语言 (PromQL) 允许用户进行查询。

Prometheus 的持久化层是一个时间序数据库，你可以使用名为 PromQL 的语言对其进行查询。

Prometheus 查询语言 (PromQL) 允许用户进行查询。

Prometheus 的持久化层是一个时间序数据库，你可以使用名为 PromQL 的语言对其进行查询。

这些名称通常符合以下格式：

*   **前缀**: 指示应用实体，例如 `node`
*   **指标名称**: 描述性名称，例如 `cpu`
*   **后缀**: 单位，例如 `seconds`
*   **聚合指标**: 将具有 `total`

让我们通过运行一些查询来感受。回到浏览器窗口，在搜索框中输入 `node_cpu_seconds_total`，然后点击执行。你会看到图 12.3。

![prometheus 查询截图。显示了各种模式的秒。](img/c12f003.png)

图 12.3: 抓取单个指标

结果集包含每个模式的一行。注意每个指标都在括号中注释。你可以通过在括号中添加标签来查询特定标签。输入多个标签，以逗号分隔的 `key="value"` 对的形式指定它们。例如，让我们将查询限制为仅“idle” CPU 时间，通过添加标签 `{mode="idle"}`。

这就是你如何在 Prometheus 中查询任何指标的方法。如果你需要帮助，可以输入几个字符，自动补全将引导你。

从图 12.4 继续，在第一个查询下方开启一个新查询并输入以下内容：

```bash
node_cpu_seconds_total{mode="idle"}
```

结果类似于图 12.4。通过将其与图 12.3 进行比较，你可以看到现在我们只显示 `mode="idle"` 标签。

![显示 模式查询的截图。结果显示了多个实例和任务的 CPU 秒。](img/c12f004.png)

图 12.4: 指定标签

从图 12.4 中的 `node_cpu_seconds_total{mode="idle"}` 查询继续，点击查询下方的 Graph 按钮查看 CPU 空闲时间的图表，如图 12.5 所示。

![Prometheus 中随时间变化的空闲模式 CPU 秒数图。数据点形成了一条向向上倾斜的直线，表示空闲 CPU 时间正在增加。](img/c12f005.png)

图 12.5: 显示 CPU 空闲时间的图表

`instance vector`（实例向量，即在给定时间指标所有标签的列表，在本例中为 `node_cpu_seconds_total`）显示在图下方。你可以通过点击列表中的项来取消选择或重新选择实例。默认情况下，Prometheus 显示过去一小时的数据，但你可以通过点击图表左侧时间选择器周围的 `–` 和 `+` 来进行更改。

Prometheus 支持广泛的函数，包括聚合函数、变化率计算、数值调整等。

例如，我们可以使用指标 `node_cpu_seconds_total{mode="idle"}` 来计算 CPU 利用率。时间窗口内的 CPU 利用率定义为 CPU 在该时间窗口内忙碌（即非空闲）的时间占百分比。

`rate` 函数计算在指定时间窗口内 `range vector`（范围向量）每秒变化率。范围向量本质上是跨越时间范围的一系列实例向量。从数学角度上讲，它是一个矩阵。例如，`node_cpu_seconds_total{mode="idle"}[5m]` 是一个范围向量，代表过去 5 分钟内所有的实例向量。

`rate(node_cpu_seconds_total{mode="idle"}[5m])` 计算每个五分钟窗口开始和结束之间空闲时间的变化率。这代表空闲时间比例，该值永远不会大于 1，表示 CPU 完全处于空闲状态。从 1 减去该结果即可得到 CPU 利用率。将其乘以 100 以转换为百分比利用率，得出以下公式：

```
(1-rate(node_cpu_seconds_total{mode="idle"}[5m]))*100
```

这将产生每个逻辑核心的 CPU 利用率图表，如图 12.6 所示。这台笔记本电脑有四个核心，你可以通过点击想要显示的项并取消其他项来查看每个核心的利用率。

![一张显示 Prometheus 中随时间变化的空闲 CPU 秒数的折线图。多个黑色时间序列显示了波动，标签指示了监控的不同实例和作业。](img/c12f006.png)

图 12.6: 每个核心的 CPU 利用率图表

要获取所有 CPU 的平均值，请使用聚合函数 `avg`。聚合函数汇聚每个时间点的所有实例向量。因此，`avg` 函数产生所有核心的平均值。

```
(1 - avg(rate(node_cpu_seconds_total{mode="idle"}[5m])))*100
```

你可以看到图 12.7 中的图表与图 12.6 类似，区别在于只有一条趋势线，显示了所有核心的平均 CPU 利用率。

![Prometheus 查询界面的截图显示了 CPU 空闲时间指标。图表描绘了在指定时间范围内空闲 CPU 秒数的剧下降。](img/c12f007.png)

图 12.7: 所有核心的平均 CPU 利用率

在这些每情况中，我们都展示了实例向量随时间变化的图表。如果你回到 Table（表格）标签页，你将看到向量中每个实例的最新值。你可以通过指定范围将其更改范围向量，例如 `node_cpu_seconds_total{mode="idle"}[5m]` 显示在指定范围（在本例中为五分钟）内，每 15 秒（Prometheus 默认）每个核心的 CPU 空闲时间，如图 12.8 所示。

![Prometheus 查询界面的截图，显示了空闲模式的 CPU 秒统计数据。表格列出了带有时间戳以及相关实例和作业的值。](img/c12f008.png)

图 12.8: CPU 范围向量

我们已经见过范围向量的单位 `m` 和 `h`。范围向量单位的全集如下：

- `ms`: 毫秒
- `s`: 秒
- `m`: 分钟
- `h`: 小时
- `d`: 天
- `w`: 周
- `y`: 年

Prometheus 将仅显示实例向量的图表而不显示范围向量。我们已经见过一些算术运算符，如 `–` 和 `*`。算术运算符的全列表如下：

- `+`: 加法
- `-`: 减法
- `*`: 乘法
- `/`: 除法
- `%`: 取模
- `^`: 幂

你也可以使用二进制运算符：

- `==`: 等于
- `!=`: 不等于
- `>`: 大于
- `<`: 小于
- `>=`: 大于等于
- `<=`: 小于

我们看到了聚合函数 `avg`。以下是其他聚合函数：

- `avg`: 实例平均值。
- `count`: 实例向量成员的数量。
- `max`: 实例向量的最大值。
- `min`: 实例向量的最小值。
- `sum`: 实例向量的和。
- `values`: 实例向量中值的计数。
- `topk`: 实例向量前 K 个值。
- `bottomk`: 实例向量后 K 个值。
- `stddev`: 实例向量的标准差。
- `stdvar`: 实例向量的方差。

### 使用 Prometheus API

还有更高级的调用不仅用于查询指标，还用于获取标签、目标等，更多信息请查阅文档。

执行查询返回实例的值。例如，输入 [`localhost:9090/v1/query`](http://localhost:9090/v1/query)。

类似于查询，查询范围接受开始和结束时间并返回范围内的所有内容。例如：[`localhost:9090/v1/query_range?query=up&start=2024-09-28T00:00:00Z&end=2024-09-30T00:00:00Z&step=60m`](http://localhost:9090/v1/query_range?query=up&start=2024-09-28T00:00:00Z&end=2024-09-30T00:00:00Z&step=60m)。记得更改开始结束日期以包含当前日期。示例输出如下：

```json
{"status":"success","data":{"resultType":"matrix","result":[{"metric":{"__name__":"up","instance":"host.docker.internal:8081","job":"mtg-calc"},"values":[[1728943200,"1"]]}}}
```

注意 Prometheus 返回的是时间戳（即 Unix 时间，或自 1970 年 1 月 1 日起的毫秒数）。你可以在查询中使用 Unix 格式指定时间范围，或者可以使用 ISO 8601 格式（`yyyy-MM-ddThh:mm:ssZ`），正如我们所。“Z”代表 UTC。要使用不同的时区，请指定偏移量。例如，对于 EDT 你可能使用 `2024-09-28T00:00:00-04:00`。

#### Micrometer 和 Actuator

在示例项目中，我们包含了 Micrometer 和 Spring Boot Actuator，这是导出应用程序标准指标的两个依赖。让我们了解它们的作用。

**Micrometer** 是一个收集并导出各种监控系统指标的库。它开箱提供了数十种标准指标，但它也是可定制的，你可以创建自己的指标并将其导出到 Prometheus。

**Spring Boot Actuator** 暴露了各种端点来监控应用程序，例如 `/health`、`/metrics`、`/info` 等。它还与 Micrometer 集以提供更详细的指标。

通过包含这些工具，你可以监控应用程序指标，以累积指标并获取有关应用程序性能和健康状况的洞察。

## Micrometer 和 Actuator 的依赖

如你在示例应用程序所示，这些依赖已包含在 POM 中：

```
<dependency>
   <groupId>io.micrometer</groupId>
   <artifactId>micrometer-core</artifactId>
</dependency>
<dependency>
   <groupId>io.micrometer</groupId>
   <artifactId>micrometer-registry-prometheus</artifactId>
</dependency>
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

你还需要通过向 `application.properties` 添加以下属性来告诉 Spring 允许访问这些管理端点：

```
management.endpoints.web.exposure.include=*
management.prometheus.metrics.export.enabled=true
```

访问 [`http://localhost:9090`](http://localhost:9090)，输入查询语句 `{job="mtg-calc"}` 即可查看应用程序导出的所有指标。

## 创建自定义指标

正如我们所见，你只需向项目添加 Micrometer 和 Actuator 依赖，即可导出丰富的应用程序指标。但在某些情况下，你可能想要自定义指标，例如特定的命中次数、性能指标等。

让我们为 GET 支付端点实现一个命中计数器。首先，你需要之前定义的 `micrometer-registry-prometheus` 依赖。

指标分为四类：

- **计数器 (Counters)**：递增的指标；除非且直到重置，否则会持续增长。
- **测量器 (Gauges)**：自由变化的指标。
- **直方图 (Histograms)**：指标的分布范围。
- **摘要 (Summaries)**：指标的计数和总和。

### 使用 Micrometer Counter 统计结果

为了计数，Prometheus 使用 Micrometer 命中计数器。让我们统计一下访问 GET 端点的命中次数：



```java
23: private Counter hitCounter;

37: public MortgageController(MeterRegistry meterRegistry) {
38:    this.hitCounter = Counter.builder("payments_get_counter")
39:       .description("GET payment counter")
40:       .register(meterRegistry);
                     . . .
59: }

91: @GetMapping("/payment")
92: public ResponseEntity<String> calculateMonthlyPayment(
93:    @RequestParam double principal, @RequestParam int years,
94:    @RequestParam double interest) {
95:    hitCounter.increment();
96:    double payment = mortgageCalculator.payment(
97:       principal, interest, years);
98:    String rval = String.format("Principal:%,.2f<br>Interest: %.2f<br>" +
99:       "Years: %d<br>Monthly Payment:%.2f", principal, interest,
100:       years, payment);
101:    HttpHeaders headers = new HttpHeaders();
102:    headers.add("Request time", "Call for payment at " 
103:       + LocalDateTime.now());
104:    return new ResponseEntity<>(rval, headers, HttpStatus.OK);
105: }
```

在第 38–40 行中，我们创建了`hitCounter`，它是一个 Micrometer `Counter`。在第 54 行中，我们增加了计数器的值。

通过浏览器（或像第 6 章那样使用 Postman 或 curl）调用几次此`/payment`端点：[`http://localhost:8081/mtg/payment?principal=100000&years=30&interest=6.1`](http://localhost:8081/mtg/payment?principal=100000&years=30&interest=6.1)。然后在 Prometheus ([`http://localhost:9090`](http://localhost:9090)) 中输入指标`payments_get_counter_total`并点击 Execute 查看增长情况。尝试在 Prometheus 的 Table 标签和 Graph 标签页中查看。

## 捕捉波动值

计数器非常适合捕捉稳定增长的值，但它不能用于捕捉波动值，例如查询时间、CPU 利用率等性能指标。Micrometer gauge 专为捕捉此类波动指标而设计。让我们创建一个 gauge 来捕捉 POST 端点的查询时间。

```java
43: Gauge.builder("payments_query_duration_gauge", this::getDuration)
44:    .description("Duration of payment queries in seconds.")
45:    .register(meterRegistry);
```

就像我们对计数器所做的那样，调用`builder()`方法并指标名称（在此例中为`payments_query_duration_gauge`），然后注册到 meter registry 实例中。与计数器不同，gauge 绑定到一个 getter 方法，在此例中为`getDuration()`。

当你在 Micrometer 中创建 gauge 时，必须提供一个返回指标当前值的 getter 方法引用。然后，每当 Prometheus 抓取（scrape）应用程序端点时，它都会调用此 getter 方法来获取当前值。

我们将在下一节展示完整代码，但当我们调用几次`mtg/payments` POST 端点时，它会生成图 12.9 所示的图表。

![prometheus 查询界面显示了支付请求的执行时长。](img/c12f009.png)

## 使用直方图和摘要对值分桶

你也可以告诉 Prometheus 将值分到不同的范围内，然后这些范围可以在 Grafana 等工具中显示。让我们使用`Timer`来捕捉查询时间。稍后我们会学习更多关于直方图（histograms）的知识。

```java
47: this.histogramTimer = Timer.builder("payments_duration_seconds")
48:    .serviceObjectives(
49:       Duration.of(500, ChronoUnit.MILLIS),
50:       Duration.of(1000, ChronoUnit.MILLIS),
51:       Duration.of(1500, ChronoUnit.MILLIS),
52:       Duration.of(2000, ChronoUnit.MILLIS),
53:       Duration.of(3000, ChronoUnit.MILLIS),
54:       Duration.of(5000, ChronoUnit.MILLIS)
55:    ) // 根据需要调整桶
56:    .publishPercentHistogram()
57:    .register(meterRegistry);
```

通常，我们在第 47 行使用`builder()`方法创建并命名指标，在此例中为`payments_duration_seconds`。在第 49–55 行中设置桶。注意 Prometheus 的桶是累积的。第 49 行表示小于等于 500 毫秒。第 50 行表示小于等于 1000 毫秒。因此，如果某个操作耗时 400 毫秒，它会被包含两个桶中。

要将值记录到直方图中，将值传递给`record`方法：

```java
histogramTimer.record(time, TimeUnit.SECONDS);
```

这里是代码：

（此处代码块已在原文中未翻译）

这是来自第 6 章的 POST 请求，添加了代码用于捕获指标。在第 65 行我们获取开始时间，并将用它来计算调用时间。在第 77 行和第 79 行，我们添加了 1 到 4 秒的人为延迟，以便我们可以看到直方图的运行。在第 82 行，我们捕获调用计时，在第 87 行，我们将其记录在`Micrometer`中，随后它将由`Prometheus`抓取。注意，我们在第 49–55 行创建了毫秒级的桶（buckets）。我们使用毫秒而不是秒是为了捕捉秒级的数据（因为参数必须是长整型），但我们以秒记录了指标（在第 87 行）。`Micrometer`会为我们处理转换。

调用`mtg/payments` POST 端点几次。`Prometheus`默认每 15 秒抓取一次，因此在每次调用之间留出足够的时间。你的`payments_query_duration_seconds` `Prometheus`图表应该看起来像图 12.10。

![一张 prometheus 图表的截图显示了支付查询执行持续时间随时间的变化。折线图具有几条处于不同高度的水平线，代表不同的查询持续时间桶。](img/c12f010.png)

图 12.10: 直方图图形

## 添加 Alert Manager

`Alert Manager`是相对于`Prometheus`的独立安装版本。它与`Prometheus`集成，允许你配置规则，当配置的指标在可配置的时间范围内突破某些指定的边界时发送通知。可以通过电子邮件和/或短信和/或任何使用 Web Hook 的其他方式发送。

首先运行以下命令拉取`Alert Manager`。你将在后的章节运行它。

```bash
docker pull quay.io/prometheus/alertmanager
```

在运行`Alert Manager`之前，你必须对其进行配置。章节仓库根目录下有一个`alertmanager.yml`文件，如下所示。如果你有 SMTP 服务器信息，请替换它。

```yaml
global:
  smtp_smarthost: 'smtp server'         #  SMTP 服务器
  smtp_from: 'sender@my_company.com'    # 你的电子邮件
  smtp_auth_username: 'username'        # 你的用户名
  smtp_auth_password: 'pa55w0rd'        # SMTP 密码 

route:
  # 默认接收器（下方定义）用于发送告警
  receiver: 'email-receiver'

receivers:
  - name: 'email-receiver'
    email_configs:
      - to: 'notifications@my_company.com'

# 可选添加抑制规则以防止重复告警
inhibit_rules:
  - source:match:
      severity: 'critical'
    target_match:
      severity: 'warning'
    equal: ['instance', 'alertname']
```

该文件包含发送通知的配置。之前的示例包含了发送者的 SMTP 配置和接收者的电子邮件地址。

接下来让我们创建一个规则。一个真实的例子是我们的平均 CPU 利用率（跨所有核心）在 5 分钟内超过 80%。利用我们对`PromQL`查询的知识，我们可以编写查询。如果空闲 CPU 指标是`node_cpu_seconds_total{mode="idle"}`，那么我们需要捕获非空闲时间大于 80% 的。表达式如下：

```promql
 1 - avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m]))> .8
```

仓库还包含一个名为`alert.rules.yml`的文件，如下：

```yaml
10: groups:
11:   - name: windows-alerts
12:     rules:
13:      - alert: HighCpuUsage
14:        expr: 1-avg by (instance)(rate(node_cpu_seconds_total
    {mode="idle"}[5m]))>.8
15:        for: 5m
16:       labels:
17:          severity: critical
18:        annotations:
19:          summary: "High CPU usage detected on instance
   {{ $labels.instance }}"
20:          description: "CPU usage on instance {{ $labels.instance }}
    is over 80%"
```

每个规则都获得一个命名的告警，其中`expr`条目定义了规则触发，`for`条目定义了突破所需的持续时间。标签（labels）和注解（annotations）用于组合通知。

我们需要告诉`Prometheus`关于我们的`Alert Manager`和规则，以及检查突破的频率。`prometheus-with-alerts.yml`在`global`紧下方且在相同的缩进级别上添加了`alerting`部分。

```yaml
### Alertmanager 配置
global:
  # 将抓取间隔设置为 15 秒。默认是 1 分钟。
  scrape_interval: 15s
  # 每 15 秒评估一次规则。默认是 1 分钟。
  evaluation_interval: 15s

alerting:
  alertmanagers:
    - static_configs:
       - targets:
          - alertmanager:9093 # AlertManager IP/端口，惯例为 9093

# 加载规则并每隔 'evaluation_interval' 评估一次。
rule_files:
  - "alert.rules.yml"
```

如果你有 SMTP 服务器，你可以运行以下命令启动`Alert Manager`并将其指向我们之前定义的`alertmanager.yml`配置文件：

```bash
docker run --name alertmanager -p 9093:9093
-v ./alert.rules.yml:/etc/alertmanager/alert.rules.yml 
-v ./alertmanager.yml:/etc/alertmanager/alertmanager.yml
quay.io/prometheus/alertmanager
--config.file=/etc/alertmanager/alertmanager.yml 
```

这应该会在你的命令行 shell 中启动`Alert Manager`。

无论你是否配置了 SMTP，你都可以在`Prometheus`中看到规则。在 Docker Desktop 中，删除现有的`Prometheus`容器并运行以下命令：

```bash
docker run --name prometheus -p 9090:9090
-v ./prometheus-with-alerts.yml:/etc/prometheus/prometheus-with-alerts.yml 
-v ./alert.rules.yml:/etc/prometheus/alert.rules.yml prometheus
--config.file=/etc/prometheus/prometheus-with-alerts.yml
```

访问 [`localhost:9090/alerts`](http://localhost:9090/alerts)。你应该能看到该规则。

## 使用 Grafana 添加仪表板

`Grafana`是一个独立的可视化工具，集成了许多数据源，包括`Prometheus`。开箱即用，`Grafana`提供了大量的图表可供选择。

前往 Grafana 下载网站 [`grafana.com/grafana/download`](https://grafana.com/grafana/download)，下载并安装适用于你平台的安装包。`Grafana`是一个浏览器应用程序，默认运行在端口 3000 上。要启动它，进入`bin`目录并运行以下命令：

```bash
grafana server
```

登录后，你需要添加`Prometheus`集成。在左侧导航中，点击`Data Sources`并`Add Data Source`。在 URL 输入`http://localhost:9090`，然后一直滚动到部点击`Save & Test`。图 12.12 显示了此配置。

![prometheusheus 数据源设置的截图显示了配置字段，服务器 URL 设置为 http://localhost:9090，且必填字段标记清晰。](img/c12f012.png)

然后点击添加新仪表板的选项。仪表板由行组成，行由可视化元素组成。可视化元素是`Grafana`闻名的图表、仪表和表格。

让我们开始一个新的仪表板，点击齿轮，设置标题和描述，并接受其余的默认值，如图 12.13 所示。

![标题为 "real world Java" 的 Prometheus 面板面板设置界面截图，显示了描述、标签、文件夹选择、编辑选项和时区设置字段。](img/c12f013.png)

保存并返回到可以添加可视化内容的页面。点击`Add`并添加行；将其命名为`Infrastructure`。我们将为该行添加可视化内容，以显示基础设施性能指标。

悬停在“Row title”（行标题）上会显示一个齿轮图标，点击它可以为您的行命名，如图 12.14 所示。

![仪表板界面中行选项对话框的截图，允许用户将标题设置为 infrastructure。它包含一个标记为“Repeat for”（重复用于）的下拉菜单，以及“Cancel”（取消）和“Update”（更新）的按钮。](img/c12f014.png)

**图 12.14**: 添加行标题

接下来选择`Add`（添加） ➪ `Visualization`（可视化）。在右上角，你可以选择可视化类型。我们将使用默认的时间序列，并给面板命名为`CPU`。图表下方是输入 PromQL 查询的地方。点击`Code`并使用以下查询：

```promql
100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100) 
```

这是 CPU 利用率的公式。然后点击查询表达式上方的`Run Queries`（运行查询）。你应该看到一个与图 12.15 类似的图表。

![Prometheus 仪表板中标题为 CPU 的图表面板，显示了随时间变化的 CPU 使用数据。界面左侧包含查询、数据转换和告警设置选项，右侧为面板配置选项。](img/c12f015.png)

**图 12.15**: 添加图表面板



保存，并点击顶部的`Real World Java`返回仪表板。从标题栏抓取该图表并将其拖入`Infrastructure`行中。

同样地，添加一个名为`Memory,`的新可视化，并输入以下查询：

```
100 - (avg by (instance) (rate(node_memory_MemAvailable_bytes [5m])) 
/ avg by (instance) (node_memory_MemAvailable_bytes
) * 100)
```

然后保存面板并将其拖动到`CPU`图表的右侧。你应该看到类似图 12.16 的内容。

![仪表板截图显示了 host.docker.internal:9100 随时间变化的 CPU 和内存使用情况。CPU 图表在 08:00 处出现峰值，而内存图在 95% 到 98% 之间波动。](img/c12f016.png)

**图 12.16**: 添加第二个图表面板

时间选择器默认为六小时，但你可以通过选择不同的时间范围来尝试。

时间序列只是可用许多图表类型之一。我们鼓励你通过编辑图表并选择各种类型来尝试其他的类型。然后尝试不同的指标并得出你自己的结论。

## 日志与追踪 (LOGGING AND TRACING)

分布式日志和追踪密切相关，并在企业级系统中非常流行，特别是在现代的基于微服务的架构中。

分布式日志是指为所有日志提供一个公共位置，以便你可以在一个地方过滤、聚合并从所有应用程序的日志中提取指标。

分布式追踪最简单的层面是指为与单个请求相关的所有调用保持一个公共 trace ID（跟踪 ID），并将该 trace ID 包含所有的分布式日志消息中，无论是由哪个服务执行的记录。还有框架允许你视觉化与调用相关的跳转。

### 介绍日志记录

分布式日志领域的关键参与者有 Elasticsearch（ELK 栈中的“E”）、Splunk 和 Loki。Splunk 和 Elasticsearch 最受欢迎，其中 Elasticsearch 在较小的公司中更为常见。Loki 是该领域的最新入场者，得益于它与 Grafana 的无缝集成以及类似于 Prometheus 的`PromQL`的`LogQL`语言，它拥有大量的粉丝。

无论你的企业使用哪种方案，分布式日志都是任何基于服务的企业的关键组件。我们提到的所有选择都是可扩展且高可用的。

`Logstash`是一个转发服务，可以过滤、转换并传输策略性日志消息到 Elasticsearch。`Kibana`是 Elasticsearch 的分析和可视化组件，你可以在其中无缝地探索数据，这些工具（Elasticsearch, Kibana, Logstash）构成了“ELK”栈。

Elasticsearch 是一个 Java 应用程序，其下载发行版自带了 Java 运行时。

数据是近乎实时的。你可以在 Elasticsearch 中进行搜索；结果是经过信息的且与你提供的搜索查询相关的。

在 Elasticsearch 中，索引（index）是存储的基本单元。它大致对应关系型数据库中的表，因为它存储了相关的文档。

为了收集数据，Elasticsearch 提供了`Logstash`工具，即 ELK 中的 L。`Logstash`是一个`ETL`工具，用于收集、过滤和转换源数据并将其转发到 Elasticsearch。

`Logstash`流线由三个阶段组成：

* **Input（输入）**：从配置的源收集数据，利用广泛的可用输入插件。
* **Filter（过滤）**：这是转换阶段，数据使用过滤器插件进行转换。
* **Output（输出）**：这是转发阶段，将数据移动到目的地。

你可以通过在`Logstash`中指定输入、过滤和输出阶段来配置数据流。

Elasticsearch 提供了自己的分析和仪表板工具`Kibana`，即 ELK 中的 K。默认情况下，`Kibana`监听 5601 端口，因此通过`localhost:5601`访问。我们选择了“Choose your own”（选择你自己的）进行集成，并在图 12.17 中看到了屏幕。`Kibana`现在已连接到位于端口 9200 的 Elasticsearch。

![Elastic 欢迎界面截图，包含可观测性、安全分析部分。页面提供了开始处理数据的选项，如添加集成、尝试示例数据或上传文件](img/c12f017.png)

**图 12.17**: Kibana 落地页

`Kibana`提供了一些示例数据供你在首页“Try sample data”（尝试示例数据）。标记为“Other sample data sets”（其他示例数据集）的下拉菜单包含如“示例电子商务订单”等的数据。

与分布式日志的概念类似，*分布式追踪* 是一种在分布式系统的不同组件中跟踪请求路径的技术。在现代微服务中，一个请求可能会由许多服务处理，如果出现问题，我们需要一种方法来查看与失败请求相关的所有日志。追踪工具可以在请求流过系统时提供实时的视觉化。

#### 追踪的关键概念

追踪的基本单元 *span*（跨）是与单个请求和单个服务相关的唯一 ID。每个`span`捕获与该请求和服务相关的关联数据，例如服务名称和执行时间。*trace*（追踪）是组成管理给定请求的所有 span 的集合。

自行协调这些将非常困难，因为你的追踪工具需要拦截每个请求和响应，以确保跨跳转之间应用公共 trace id。此外，日志和指标需要使用工具分配的 trace ID 进行标记。

`OpenTelemetry`是一套广泛采用的可观测性规范，也是一个用于通过所有流行语言 API 管理指标（metrics）、日志（logs）和追踪（traces）的开源实现。其他流行的实现包括`Jaeger`和`Zipkin`，它们可以收集、存储、可视化并分析你的日志和指标。

### 在 Spring Boot 中实现链路追踪

`Micrometer Tracing`是一个可以添加到 Spring Boot 应用程序中的开源插件，它可以拦截传入和传出的调用，以确保管理请求的所有服务共享一个公共 trace ID。

只需将`micrometer-tracing`端点作为`Maven`或`Gradle`依赖项添加即可。截至本文编写，该依赖项为`io.micrometer:micrometer-tracing:1.3.5`，它与 Spring Boot 3 及更高版本兼容。早版本的 Spring Boot 使用`Spring Cloud Sleuth`来相同目的。这些工具的奇之处在于，一旦你包含了该依赖项，就不需要更改任何代码。

## 更多引用

* `Prometheus`
  * [`https://prometheus.io/docs/introduction/overview`](https://prometheus.io/docs/introduction/overview): Prometheus 文档
  * [`https://prometheus.io/download`](https://prometheus.io/download): Prometheus 和 Linux Node Exporter
  * [`https://github.com/prometheus-community/windows_exporter/releases`](https://github.com/prometheus-community/windows_exporter/releases): Windows Exporter
  * [`https://github.com/prometheus/node_exporter`](https://github.com/prometheus/node_exporter): Node Exporter 标记
  * [`https://github.com/prometheus-community/windows_exporter/blob/master/README.md`](https://github.com/prometheus-community/windows_exporter/blob/master/README.md): Windows Exporter 标记
  * [`https://prometheus.io/download/#alertmanager`](https://prometheus.io/download/#alertmanager): Alert Manager
* 其他工具
  * [`https://docs.docker.com/engine/install`](https://docs.docker.com/engine/install): 下载 Docker
  * [`https://grafana.com/grafana/download`](https://grafana.com/grafana/download): Grafana
  * [`https://www.elastic.co/downloads/elasticsearch`](https://www.elastic.co/downloads/elasticsearch): Elastic Search
  * [`https://www.elastic.co/downloads/logstash`](https://www.elastic.co/downloads/logstash): Logstash
  * [`https://www.elastic.co/downloads/kibana`](https://www.elastic.co/downloads/kibana): Kibana
  * [`https://www.7-zip.org/download.html`](https://www.7-zip.org/download.html): 7-Zip
  * [`https://opentelemetry.io`](https://opentelemetry.io): OpenTelemetry 文档
  * [`https://docs.micrometer.io/tracing/reference/index.html`](https://docs.micrometer.io/tracing/reference/index.html): Micrometer tracing
  * [`https://www.jaegertracing.io`](https://www.jaegertracing.io): Jaeger 文档
  * [`https://zipkin.io`](https://zipkin.io): Zipkin

## 总结

在本章中，你学习了可观测性、指标、日志和链路追踪。你还学习了如何使用`OpenTelemetry`、`Jaeger`和`Zipkin`。你学习了如何使用`Micrometer Tracing`在 Spring Boot 应用程序中实现追踪。

## 性能

假设你发现代码中的某一段运行很慢。可能因为它消耗了大量的 CPU 导致你的机器达到极限。或者它正在按顺序执行操作，而这些操作本是可以并行运行的。*基准测试*（Benchmarking）允许你测量运行特定代码部分所需的时间。在进行更改前后运行基准测试，可以让你看到是否让程序运行更快。你将看到使用内置 Java API 进行基准测试的示例，然后将学习如何使用库来获得更准确的结果。

### 使用内置 Java API 进行基准测试

斐波那契数列是自然界和计算机科学中广为人知的数列。它从 0，1 开始，之后每一项都是前两项之和：0,1,1,2,3,5,8,.....

以下示例展示了计算斐波那契数列中特定位置数值的一种低效方法。在这个示例中，如果你传入`6`，它将返回`8`，因为那是数列中的第六项。由于每个项都是通过将前两个数字相加得出的，这种低效算法会反复计算前两个数字并将它们相加。它通过递归的方式执行操作，这会导致重复计算相同的信息。

```
public static void main(String[] args) {

   final int nanosPerSecond = 1_000_000_000;
   long start = System.nanoTime();
   long recursive = fibonacci(50);
   long end = System.nanoTime();

   System.out.println(recursive);
   System.out.printf("Took %d seconds", (end-start)/nanosPerSecond);
}
public static long fibonacci(int number) {
   if (number <= 1) return number;

   return fibonacci(number - 1) + fibonacci(number - 2);
}
```

我们其中一次运行结果的代码输出如下：

```
12586269025
Took 36 seconds
```

三十六秒计算出一个结果是一个很长的时间。幸运的是，解决这个问题不需要递归。让我们不使用递归重写这段代码并比较性能：

```
public static void main(String[] args) {

   final int nanosPerSecond = 1_000_000_000;
   long start = System.nanoTime();
   long recursive = fibonacci(50);
   long end = System.nanoTime();

   System.out.println(recursive);
   System.out.printf("Took %d seconds", (end-start)/nanosPerSecond);
}
public static long fibonacci(int number) {
   long previous = 0, current = 1;
   long result = 0;

   for (int i = 1; i < number; i++) {
      result = previous + current;
      previous = current;
      current = result;
   }
   return result;
}
```

这次的输出不到一秒。完成相同任务的速度快得多！我们从这个例子可以看出，虽然有许多方法可以完成任务，但某些方法的性能可能比其他方法更好。始终仔细思考你的方法。虽然递归适用于许多情况，但在这种情况下它是错误的方法，因为它反复重新计算相同的中间结果。

```
12586269025
Took 0 seconds
```

### 微基准测试 (Microbenchmarking)

上一个示例中的代码效率非常低，我们不需要详细的基准测试就能看到时间的改进。但在现实生活中，我们经常必须定位并调整具有微小改进的代码部分。`Microbenchmarking`（微基准测试）衡量小型、隔离代码部分性能的行为。

编写精确且良好的基准测试非常困难。你必须确保没有竞争性任务（如日志记录、垃圾回收等）同时发生，否则可能会影响基准测试。你还必须确保`JVM`对代码的优化不会导致你的基准测试失效。例如，应用程序可能有产生未使用结果的代码部分。`JVM`可能将这些部分视为死代码并将其优化掉使其不运行！此外，`JVM`会尽可能优化代码，因此在循环中，后期的运行速度可能比早期运行得更快。或者`JIT`编译器可能会将字节码转换为本地代码。所有这些因素都会极大偏斜在优化生效之前生成的任何基准测试。

幸运的是，有 Java Microbenchmark Harness (`JMH`)，所以你不需要担心此类优化，只需专注于测量你的代码。`JMH`的维护者建议使用`JMH`模板`jmh-java-benchmark-archetype`来生成新项目。你可以将项目作为依赖项添加，以便运行你的代码：

```
mvn archetype:generate
   -DinteractiveMode=false
   -DarchetypeGroupId=org.openjdk.jmh
   -DarchetypeArtifactId=jmh-java-benchmark-archetype
   -DgroupId=com.wiley.realworldjava.jmh
   -DartifactId=jmh-benchmark
   -Dversion=1.0.0
```

这运行`archetype:generate`目标以使用指定的 Maven 模板生成新项目。第一个`-D`系统属性仅表示不提示确认。接两个属性指定了`JMH`模板。最后三个用于为你的项目分配 GAV（组 ID、构件 ID 和版本）。

生成的代码是一个 Maven 项目。该模板创建了一个名为`MyBenchmark.java`的 Java 类，包含一个空方法。让我们用以下代码替换它，该代码包含对上一个示例中缓慢的`fibonacci()`实现方法签名的调用：



`package com.wiley.realworldjava.jmh;`

`import org.openjdk.jmh.annotations.Benchmark;`
`import org.openjdk.jmh.infra.Blackhole;`

`public class MyBenchmark {`

```
   @Benchmark
   public static void benchmark(Blackhole blackhole) {
      long result = fibonacci(50);
      blackhole.consume(result);
   }
   public static long fibonacci(int number) {
      long previous = 0, current = 1;
      long result = 0;

      for (int i = 1; i < number; i++) {
         result = previous + current;
         previous = current;
         current = result;
      }
      return result;
   }
}
```

```
# Run progress: 80.00% complete, ETA 00:01:40
# Fork: 5 of 5
# Warmup Iteration   1: 3080887445.320 ops/s
# Warmup Iteration   2: 3086292064.630 ops/s
# Warmup Iteration   3: 3088137264.756 ops/s
# Warmup Iteration   4: 3089568664.300 ops/s
# Warmup Iteration   5: 3084161269.692 ops/s
Iteration   1: 3097137124.647 ops/s
Iteration   2: 3080164130.908 ops/s
Iteration   3: 3095501587.777 ops/s
Iteration   4: 3088198606.124 ops/s
Iteration   5: 3084219015.220 ops/s

Result "com.wiley.realworldjava.jmh.MyBenchmark.benchmark":
   3054970163.963 ±(99.9%) 129045935.961 ops/s [Average]
(min, avg, max) = (2229602431.413, 3054970163.963, 3110210135.698),
   stdev = 172272632.473
  CI (99.9%): [2925924228.001, 3184016099.924] (assumes normal distribution)

# Run complete. Total time: 00:08:21

Benchmark               Mode  Cnt           Score           Error  Units
MyBenchmark.benchmark  thrpt   25  3054970163.963 ± 129045935.961  ops/s
```

首先，请注意基准测试运行的时间要短得多，在不到 9 分钟内完成，而不是 30 分钟。此外，你可以看到使用更快的代码每秒的操作次数要多得多！

你可能会好奇运行单个基准测试多花了多久。毕竟，每秒 3,054,970,163 次操作是一个很大的数字，但并不是容易处理的。幸运的是，你可以配置 `JMH` 输出更易读的结果。你可以通过在 `@Benchmark` 注解中添加属性来调整输出：

```
@Benchmark @BenchmarkMode(Mode.AverageTime)
 @OutputTimeUnit(TimeUnit.MICROSECONDS)
```

这一次你将分别为较慢和较快的实现获得如下所示的输出：

```
Iteration   1: 35172416.167 µs/op
Iteration   1: ≈ 10-3 µs/op
```

输出单位是 `μs/op`，这意味着每次操作所需的微秒。对于较快的代码，你可以看到输出使用了科学计数法，因为结果远小于一微秒。对于慢代码，你看到的则是每次操作所需的微秒的一个很大的数字。

作为开发者，选择适用于你所测量代码的模式和单位取决于你的决定。表 13.1 显示了 `Mode` 的选项，而 表 13.2 显示了 `TimeUnit` 的选项。如果不指定，将使用 `Mode.Throughput` 和 `TimeUnit.SECONDS`。

| @BENCHMARKMODE | 描述 |

| --- | --- |

| `Mode.Throughput` | 单位时间内执行的操作数 |

| `Mode.AverageTime` | 单次操作的平均时间 |

| `Mode.SampleTime` | 最小、最大和平均时间 |

| `Mode.SingleShotTime` | 无预热的单次运行时间 |

| `Mode.All` | 包含以上所有项 |

表 13.1: JMH 基准测试模式

| @OUTPUTTIMEUNIT | 描述 |

| --- | --- |

| `TimeUnit.NANOSECONDS` | 微秒的千分之一 |

| `TimeUnit.MICROSECONDS` | 毫秒的千分之一 |

| `TimeUnit.MILLISECONDS` | 秒的千分之一 |

| `TimeUnit.SECONDS` | 秒为单位 |

| `TimeUnit.MINUTES` | 分为单位 |

| `TimeUnit.HOURS` | 小为单位 |

| `TimeUnit.DAYS` | 天为单位 |

表 13.2: JMH 输出时间单位

## 调整 JVM 设置

现在我们将介绍你可以控制的 `JVM` 设置。在应用这些之前，请记住“过早优化是一切恶的根源”。

### 配置内存

在本节中，你将学习如何控制内存设置。有一些你可以控制的 `JVM` 设置。在应用这些之前，请记住“过早优化是一切恶的根源”。

### 设置大小

| @BENCHMARKMODE | 描述 |

| --- | --- |

| `Mode.Throughput` | 单位时间内执行的操作数 |

| `Mode.AverageTime` | 单次操作的平均时间 |

| `Mode.SampleTime` | 最小、最大和平均时间 |

| `Mode.SingleShotTime` | 无预热的单次运行时间 |

| `Mode.All` | 包含以上所有项 |

表 13.1: JMH 基准测试模式

### 时间单位

| @OUTPUTTIMEUNIT | 描述 |

| --- | --- |

| `TimeUnit.NANOSECONDS` | 微秒的千分之一 |

| `TimeUnit.MICROSECONDS` | 毫秒的千分之一 |

| `TimeUnit.MILLISECONDS` | 秒的千分之一 |

| `TimeUnit.SECONDS` | 秒为单位 |

| `TimeUnit.MINUTES` | 分为单位 |

| `TimeUnit.HOURS` | 小为单位 |

| `TimeUnit.DAYS` | 天为单位 |

表 13.2: JMH 输出时间单位

### 回收垃圾

你可能对垃圾回收（`GC`）的概念熟悉。Java 在对象不再被引用时运行 `GC` 来回收内存。你无法直接控制 `GC` 何时运行或持续多久。正如你所看到的，有一些可以配置的设置会影响频率和时长。

当你创建新对象时，通常它们在分配后就不可能再次使用。因此，尽早取消引用以防占用内存。为了减少垃圾回收的影响，Java 将内存划分为代。年轻代由 Eden 区和两个幸存区（S0 和 S1）组成。对象最初在 Eden 区分配。当 Eden 区充满时会执行 *Minor GC*。在 Minor GC 期间，大多数对象被发现未被引用并清理。Minor GC 的幸存者移动到活跃的幸存区（例如 S0）。在下次 Minor GC 时，Eden 中的未引用对象移动到另一个幸存区（S1），S0 的幸存者也会移动到 S1。S0 被回收，S1 变成活跃的幸存区，依此类推。在 S0 和 S1 之间经过可配置的次数后，幸存对象会被提升到老年代。

还有一个元空间（Metaspace），用于静态数据和类对象，这些对象在程序的生命周期内必须保持可用。

以下是一些常用的标志：

| 标志 | 别名 | 描述 |

| --- | --- | --- |

| `-Xms` | `XX:InitialHeapSize` | 堆的初始大小 |

| `-Xmx` | `XX:MaxHeapSize` | 堆的最大大小 |

| `-Xss` | `XX:ThreadStackSize` | 线程栈的大小 |

无论使用哪种垃圾回收器，都可以配置某些大小：

- `-Xmn`: 新一代（Eden + Survivor 空间）的初始和最大大小。如果此数字太小，垃圾回收可能会发生过于频繁。如果它太大，垃圾回收可能会变慢且频率降低。Oracle 建议该范围为堆大小的 25% 到 50%。或者，如果你想为初始新生代和最大新生代大小配置单独的值，可以使用 `-XX:NewSize` 和 `-XX:MaxNewSize`。

- `-XX:MaxMetaspaceSize`: 元空间（Metaspace）必须保持可用的最大大小。

- `-XX:MetaspaceSize`: 元空间的初始大小。当它第一次填满时，将运行一次垃圾回收。

- `-XX:MaxTenuringThreshold`: 对象在晋升到老代之前在 S0 和 S1 之间切换的次数。

特定的垃圾回收器有你可以调优的自定义设置。如果你发现自己正在调优垃圾回收器，请查看 Java 文档页面上的高级垃圾回收部分获取详情。

## 使用串行垃圾回收 (Serial Garbage Collection)

串行垃圾回收是一种旧的类型，在当前实践中很少使用。然而，在学习其他类型之前了解它是很有好的。

使用串行垃圾回收器时，当一个线程执行垃圾回收时，整个应用程序都会停止。这被称为 `stop-the-world`（停止世界）。在某些应用程序中，这种暂停是可以接受的。然而，对于性能有要求的应用程序，这是不可接受的！

Oracle 的文档说串行垃圾回收器适用于小型简单的应用程序。然而，在如今的多核机器时代，即使是小型应用程序也可以另一种类型。如果你确实想使用串行垃圾回收器，请使用选项 `-XX:+UseSerialGC`。

## 使用并行垃圾回收 (Parallel Garbage Collection)

并行垃圾回收器也是一种停顿世界的垃圾回收器。然而，它比串行垃圾回收器更快，因为它使用多个线程进行垃圾回收工作。

同样，它在执行垃圾回收时会停止所有工作。如果你确实需要并行垃圾回收器，请使用选项 `-XX:+UseParallelGC`。

## 使用 G1GC

垃圾优先收集器 (G1GC) 为具有大量可用内存的多核服务器设计。它通过将堆拆分为逻辑区域来工作，这允许 G1GC 同时逐节清理所有代。结果是暂停是稀见的，stop-the-world 并不是问题。

虽然仍然存在 Eden、幸存和老年代区域，但它们位于整个堆中的不同逻辑区域。结果是，G1GC 对于大堆来说是一个更好的算法。

你可能认为这听起来很棒，并奇怪为什么 G1GC 没有一直被使用。主要原因是它需要大量的 RAM。G1GC 建议堆大小为 6GB 或更高。如果你没有在处理大内存空间，并行回收可能更适合你。

Oracle/Open JDK 默认使用 G1GC。然而，如果你依赖这种垃圾回收器，你仍然应该指定选项 `-XX:+UseG1GC`。

## 使用 JMETER 进行测试

JMeter 是一个流行的开源负载测试工具。负载测试意味着在高并发的流量下测试你的应用程序。我们创建了一个基础示例应用程序来展示如何使用 JMeter。它是一个单页应用程序，允许用户在休闲中心借用和归体育设备。如图 13.1 所示，共有四种可以参加的运动。篮球和皮球球拍目前正处于借出状态，但乒乓球拍和排球可以租借。在本节中，我们将使用 JMeter 测试我们的应用程序，看看如果我们的小型休闲中心在短时间内收到大量请求，表现将会如何！

![侧边栏菜单的截图显示了体育设备的借用状态。它包含一个可用物品列表（如排球和乒乓球拍）以及当前借出的物品，并有借用或归设备的选项。](img/c13f001.png)

**图 13.1**: 示例应用程序

简而言之，使用 JMeter 进行测试是一个三步过程。首先，你使用图形化用户界面创建测试计划。然后，你在命令行或直接在工具内部运行测试。最后，你分析结果。接下来的章节将展示这些步骤。

### 创建测试计划

使用 JMeter 的第一步是下载 JMeter 二进制文件。请参见“进一步参考”部分获取下载链接。下载包包含了测试 Web 应用程序或 REST API 所需的一切。如果你计划测试 Java 数据库连接 (JDBC) 或 Java 消息服务 (JMS)，你需要额外的软件。请参见第 14 章“了解更多生态系统”获取关于这些技术的更多。

一旦下载并解压 JMeter，你将获得名为 `apache-jmeter-x.y.z` 的目录。（我们测试的是 JMeter 5.6.3 版本。）打开命令行并导航到 `bin` 目录。然后在 Windows 上运行 `jmeter.bat` 或在 Mac 上运行 `jmeter.sh`。

给你的测试计划起一个名字。你可以看到“Rec Center”是我们的测试计划名称。你可以输入可选的注释来表示测试目的。

接下来创建一个*线程组* (thread group)，它定义了模拟用户的数量、他们向你的应用程序发送请求的频率以及他们总共应该发送多少请求。右键点击你的测试计划，然后选择 Add (添加) ➪ Threads (线程)。

给线程组起一个名字。你可以看到“Rec Center”是我们的测试计划名称。你可以输入可选的注释来表示测试目的。你可以为线程组设置一个名称并配置选项。例如，在图 13.2 中，你可以看到该线程组包含 5 个用户，启动时间（ramp-up）为 1 秒，循环次数为无限。

![线程组配置面板的截图，标题为 borrowers，显示了 5 个线程、1 秒的启动时间、无限循环，以及针对采样器错误的选项。](img/c13f002.png)

**图 13.2**: JMeter 线程组

现在有了线程组，是时候告诉它要做什么了！右键点击线程组并选择 Add (添加) ➪ Sampler (采样器) ➪ HTTP Request (HTTP 请求)。

在图 13.3 中，你可以看到以下默认值的更改：

![HTTP 配置面板的截图，标题为 status，显示了连接服务器的设置。它指定协议为 HTTP，服务器为 localhost，端口号为 8080，对 /status 路径进行 GET 请求。](img/c13f003.png)

**图 13.3**: JMeter HTTP GET 请求

- **Name (名称)**：请求的显示名称，在我们的例子中是“View status”。

- **Server name or IP (服务器名称或 IP)**：我们使用了 localhost，因为测试在笔记本电脑上运行。可以使用服务器名称或 DNS 别名。

- **Port number (端口号)**：我们使用了 8080，对应示例 Web 应用程序使用的默认端口。

- **HTTP request (HTTP 请求)**：我们选择 GET，通常用于查询数据的 HTTP 方法。

- **Path (路径)**：URL 的剩余部分。确保以斜杠开头，在本例中为 `/status`。

对更新操作进行负载测试也是常见的，所以让我们创建另一个 HTTP 请求，如图 13.4 所示。像 GET 示例一样，有一个名称、服务器名称和端口号。这次 HTTP 请求是 POST，因为我们正尝试更改借用物品的状态。URL 再次以斜杠开始：`/borrowItem`。这次我们在底部提供了 `itemId` 参数 `basketball`，这是我们的 POST 请求要求的。

对于本次测试，我们将再次创建一个名为 `/returnItem` 的 POST 端点。其配置与图 13.4 相同，只是 URL 不同。

![一张标题为 borrow 的 HTTP 请求配置面板截图，设置为向本地 8080 端口的 localhost 发送 POST 请求。它包含了借用物品的参数，其中项目 ID 指定为 basketball。](img/c13f004.png)

**图 13.4**: JMeter HTTP POST 请求

由于你想查看结果，我们需要通过点击线程组并选择 `Add ➪ Listener` 来添加一个或多个监听器。此菜单项为你提供了多种输出格式。例如，本示例使用了“汇总报告”（Summary Report）并将输出文件名设置为 `summary.csv`。

现在你已经有了一个测试计划，可以通过进入 `File ➪ Save Test Plan As` 将其保存为 Java 管理扩展（JMX）文件，并在保存前输入所需的文件名和位置。

`.jmx` 文件保存在仓库的 `src/main/resources` 中。你可以打开 JMeter 界面并选择 `File ➪ Open` 来查看此书中使用的所有设置。

JMX 文件是一个 XML 文件。你将将在附录 中的“读取和写入 XML、JSON 和 YAML”中学习 XML 知识。现在，只需知道 XML 是一种结构化文本格式，如果你对其中的内容感兴趣，可以使用文本编辑器打开该文件。

### 运行负载测试

在执行负载测试之前，请确保你的应用程序（在本例中为 Spring Boot 应用程序 `RecCenterApplication`）正在运行。点击绿色箭头运行测试。一旦你确认它们运行正常，就可以配置测试，使其能够从命令行界面运行。



在启动 JMeter 之前，请记住将 JMeter 的 `bin` 目录添加到你的路径（path）中并运行此命令：

```
jmeter -n -t RecCenter.jmx
```

`-n` 选项表示非 GUI，即 CLI 模式（否则 JMeter 将启动其 UI）。`-t` 选项表示测试文件，后面应接你的 JMX 文件名。这里还有许多其他选项；例如，`-l` 指定日志文件名，`-o` 指定输出目录。如果你需要代理服务器访问互联网，`-H` 指定代理主机，`-P` 指定代理端口。还有许多其他选项，请查阅文档。

JMeter 会自动创建一个 `jmeter.log` 文件。输出包含了关于每个线程的信息，包括名称（`Borrowers`）、线程组和数字（`1-2` 等）。在本例中，只有一个线程组，所有数字都以 `1-` 开头。共有五个线程，因此第二个数字的范围从一到五：

```
INFO o.a.j.t.JMeterThread: Thread started: Borrowers 1-1
INFO o.a.j.t.JMeterThread: Thread started: Borrowers 1-2
INFO o.a.j.t.JMeterThread: Thread is done: Borrowers 1-1
INFO o.a.j.t.JMeterThread: Thread finished: Borrowers 1-1
INFO o.a.j.t.JMeterThread: Thread started: Borrowers 1-3
INFO o.a.j.t.JMeterThread: Thread is done: Borrowers 1-3
INFO o.a.j.t.JMeterThread: Thread finished: Borrowers 1-3
INFO o.a.j.t.JMeterThread: Thread started: Borrowers 1-4
INFO o.a.j.t.JMeterThread: Thread is done: Borrowers 1-4
INFO o.a.j.t.JMeterThread: Thread finished: Borrowers 1-4
INFO o.a.j.t.JMeterThread: Thread started: Borrowers 1-5
INFO o.a.j.t.JMeterThread: Thread is done: Borrowers 1-5
INFO o.a.j.t.JMeterThread: Thread finished: Borrowers 1-5
```

在本示例中，测试计划指定使用五个线程。看到某些线程已完成而其他线程已启动，我们可以得出结论它们并非在同一时间启动的。你可能会注意到“done”的出现。在 JMeter 中，“done”意味着成功。相反，“finished”意味着线程已停止。线程总是完成的，但并非所有线程都成功通过。此外，输出还包含请求耗时、最大值、最小值和平均值的摘要。

## 分析结果

`summary.csv` 文件默认包含许多列。结果如下：

```
timeStamp,elapsed,label,responseCode,threadName
1715856000000,1014,POST,200,Borrowers 1-1
1715856000500,1015,POST,200,Borrowers 1-2
1715856001000,1014,POST,200,Borrowers 1-3
1715856001500,1014,POST,200,Borrowers 1-4
1715856002000,1015,POST,200,Borrowers 1-5
```

```
timeStamp,elapsed,label,responseCode,threadName
1.7228E+12,196,View status,200,Borrowers 1-1
1.7228E+12,29,View status,200,Borrowers 1-2
1.7228E+12,8,View status,200,Borrowers 1-3
1.7228E+12,16,View status,200,Borrowers 1-4
1.7228E+12,12,View status,200,Borrowers 1-5
1.7228E+12,1018,Borrow,200,Borrowers 1-1
1.7228E+12,5445,Borrow,200,Borrowers 1-5
1.7228E+12,10641,Borrow,200,Borrowers 1-4
1.7228E+12,15858,Borrow,200,Borrowers 1-3
1.7228E+12,10006,Return,200,Borrowers 1-4
1.7228E+12,21030,Borrow,200,Borrowers 1-2
1.7228E+12,20013,Return,200,Borrowers 1-1
1.7228E+12,5003,Return,200,Borrowers 1-3
1.7228E+12,15010,Return,200,Borrowers 1-5
```

开发者很快意识到这不是一个好的改动。`Borrow` 操作现在变慢得多，而且性能问题也扩散到了 `Return` 操作。我们建议这段代码的作者重新阅读第 9 章以更好地理解并发！尽管如此，这是对 JMeter 的一个很好的演示。

## 使用 JDK 工具

JDK 安装包附带了许多帮助定位性能热点的工具。我们将在接下来的章节中介绍这些工具。你可以在负载测试时将其与 JMeter 结合使用，也可以直接对你的应用程序运行它们以定位已知问题的来源。

本节中的示例展示了当访问中心应用程序中的 URL [`http://localhost:8080/emailSummary`](http://localhost:8080/emailSummary) 时应用程序的行为。该端点会生成一份每月接收邮件数量的报告。图 13.5 显示了加载此页面的输出。从报告来看，我们可以假设六月份（第 6 个月）有很多垃圾邮件！我们故意让此端点使用非常低效的算法，该算法每次访问页面时都会调用。算法读取一个文件并与之前加载的文件进行比较。代码第一次运行不到一秒，随后的运行大约需要 19 秒。更糟糕的是，它还浪费内存。本章的最后一节将展示如何改善这种情况。现在，让我们来看看工具本身。

![一个标题为按月调用的表格，显示了每个月的调用次数。它列出了 12 个月以及相应的调用量，突出了六月有 54,129 次调用的显著峰值。](img/c13f005.png)

**图 13.5**：邮件摘要页面

现在让我们来看一些调查性能问题的工具。

### 使用 Java Flight Recorder

Java Flight Recorder (JFR) 是一个 JVM 监控工具。JFR 主要关注测量三种类型的事件：

* **Instant（瞬时）**：一旦发生指定的活动，立即记录
* **Duration（持续时间）**：如果活动超过指定的长度，则记录
* **Sample（采样）**：周期性捕获活动

Java Flight Recorder 将事件记录名为 `flight.jfr` 的文件。你可以通过从命令行执行 `jfr` 命令来生成文本报告，也可以在 Java Mission Control 中直接以可视化格式查看结果。下一节将介绍 Java Mission Control。

Java 不会自动运行 Java Flight Recorder；你必须手动开启它。有多种方法开启它。一种方法是在启动应用程序时传递 `-XX:StartFlightRecording` 选项。例如，`-XX:StartFlightRecording=delay=5s,maxSize=1G` 忽略程序前五秒的任何数据，并将文件大小限制为 1GB，之后文件将循环。`java` 工具的文档页面提供了完整的选项列表。

或者，你可以使用 `jcmd` 程序告诉正在运行的 JVM 应用程序使用 Java Flight Recorder 对其进行剖析。这种方法接受进程 ID (PID) 或 Java 程序名称作为输入。例如，如果我们的应用程序以进程 ID 14020 运行，那么以下两个命令就是使用 JFR 对其进行剖析的等效方式：

```
jcmd RecCenterApplication JFR.start filename=flight.jfr
jcmd 14020 JFR.start filename=flight.jfr
```

当你从命令行启动 Flight Recorder 时，它会贴心地显示一条命令，你稍后运行该命令可以将所有输出导出到文件。你可以随时启动该转储命令，将所有输出导出到文件。

在左侧导航栏中，你可以看到任务控制器的其他报告，例如：

* **文件 I/O (File I/O)**：列出在输入/输出操作上花费
* **锁实例 (Lock Instances)**：列出等待显示器的进程
* **方法分析 (Method Profiling)**：显示使用 CPU 最多方法调用的堆栈跟踪
* **线程转储 (Thread Dumps)**：显示不同时间点运行的线程
* **垃圾回收 (Garbage Collection)**：包括使用了哪个垃圾回收器，以及显示停顿和可用堆内存的图表
* **进程 (Processes)**：显示 JVM 之外使用大量 CPU 的其他进程

![内存面板截图，显示了类使用情况，包括各种类的最大大小、存活大小和总分配的数据，并突出了它们的消耗情况。]

### 使用 JConsole 进行监控

在加载 Java Flight Recorder 文件后，Mission Control 会为你提供应用程序的数据。相比之下，`jconsole` 让你看到运行中应用程序的实时指标。要启动 `jconsole`，只需传递进程 ID 即可。

```
jconsole 5045
```

JConsole 概览。你可以看到此应用程序使用了大量堆内存且内存持续增加，这不是你希望看到的模式。相比之下，CPU 在执行工作时会飙升，在操作完成后会下降。内存（Memory）标签允许你查看堆上每个代的内存图表，并显示垃圾回收的影响。线程（Threads）标签有助于检测死锁。摘要（Summary）标签提供统计信息，如使用的线程数和堆的大小（包括每个部分的最大值）。类（Classes）和 MBeans 标签不常用。



![性能监控仪表板截图，显示了四个图表。它显示了堆内存使用情况、峰值为 31,253 个加载类的线程指标，以及剩余的 CPU 使用率。]

### 使用 VisualVM

与 Java Mission Control 类似，VisualVM 最初是随 JDK 一起发布的。它最初名为`visualvm`，现在作为独立工具可用，你可以从“进一步参考”链接中下载。要启动 VisualVM，在 Windows 上调用`visualvm.exe`或在 Linux/Mac 上调用`visualvm`。注意，你不需要传递进程 ID；VisualVM 会在左侧导航栏中自动提供它能找到的所有进程。只需双击你想要信息的进程即可。

与 JConsole 一样，VisualVM 可以对你的进程提供实时监控，如图 13.9 所示。你可以在此标签上的堆（Heap）和元空间（Metaspace）图表之间切换。点击堆转储（Heap Dump）可以点击查看哪些类最占用内存。线程（Threads）标签提供 CPU 使用和等待时间的信息。采样器（Sampler）标签向你随时间变化的 CPU 和内存使用详情。分析器（Profiler）标签允许你深入了解应用程序。除了分析运行中的程序外，你还可以加载 JFR 文件或在命令行生成的转储文件。

你可能注意到本章中的某些工具存在重叠。VisualVM 通常用于初始或快速分析，且启动最快。如果这还不足以找到问题，你通常会发现转向 Java Flight Recorder/Java Mission Control 或其他分析器是值得花费时间的。

![应用程序监控面板截图，显示了 CPU 使用率和堆内存趋势。它显示了 43 秒的运行时间，以及 CPU、堆、元空间、加载类和线程的指标。]

### 使用 JStat 报告

虽然`jconsole`提供了垃圾回收的图表，但`jstat`命令以文本形式为你提供这些信息。例如，以下命令传递了进程 ID 以监控内存使用和垃圾回收。它每秒打印两次（即每 500 毫秒一次），并持续 20 次。

```
jstat -gcutil 5045 500 20
  S0     S1     E
     - 100.00   8.57
     - 100.00   8.57
     - 100.00  11.43
     - 100.00  11.43
     - 100.00  11.43
```

上一个示例显示了垃圾回收统计中前三列（许多列中的）的输出。前两列是垃圾回收后的幸存空间（Survivor space）。在应用程序启动期间，第一列为空白。第三列是 Eden 区的大小，它是对象初始分配的地方。你可以看到它随着程序的运行而增加。

`GCUtil`还显示了关于运行垃圾回收所需时间的信息，以及关于元空间（Metaspace）使用的信息。`jstat`命令有很多关于类加载器、堆和垃圾回收的选项。如果你发现自己需要实时信息，`jstat`的文档页面涵盖了所有选项。

## 优化你的应用程序

无论你已经使用本章描述的工具识别了性能问题，还是只是想让你的代码性能更高，这一节都将提供帮助。

第一个问题出现在第 14 行，我们每当用户请求报告时都会读取该文件。该文件包含去年的数据，它不会改变。I/O 和网络操作通常是应用程序中最昂贵的部分。考虑是否可以缓存数据或批量处理操作通常会对你的性能有所帮助。在这种情况下，文件只需要读取一次。如果文件发生变化，你可以检查时间戳，或者让另一个进程使缓存失效，以避免每次读取。

即使我们有比较文件内容的需求，`numberOfEmailsChangedSinceLastRead()`的实现也是一种非常糟糕的方法，因为它的比较的内容太多了。整个方法可以写如下：

```
return numberOfEmails.equals(fileData);
```

使用内置方法而不是自己编写方法可能更快，因为库提供者花费时间对它们进行了优化。在这种情况下，`numberOfEmailsChangedSinceLastRead()`包含嵌套循环，速度比需要的要慢得多。

下一个问题是该程序浪费了内存。文件中有一百万行数据。然而算法只需要一个摘要。存储计算结果比存储原始数据更好，因为数据仅用于这一个目的。

最后，`calculateTotals()`将`String`转换为`int`，然后将其装箱（box）为`Integer`。这本身并不是一个问题。然而，结果仅用于计数，那么还不如保持为`String`。许多编译器足够智能，可以消除这种低效性。但是，如果你从一开始就能避免不必要的工作会更好。

以下是更高效版本的代码：

```
10: private Map<String, Long> emailSummary = getEmailSummary();
11: 
12: @GetMapping("/emailSummary")
13: public String emailSummary(Model model) {
14:    model.addAttribute("byMonth", emailSummary);
15:    return "emailSummary";
16: }
17: private Map<String, Long> getEmailSummary() {
18:    Path path = Path.of("src/main/resources/lastYear.txt");
19:    List<String> fileData;
20:    try {
21:       fileData = Files.readAllLines(path);
22:    } catch (IOException e) {
23:       throw new UncheckedIOException(e);
24:    }
25:    return fileData.stream()
26:       .collect(Collectors.groupingBy(Function.identity(),
27:       TreeMap::new, Collectors.counting()));
28: }
```

这段代码不仅更快，而且更短、更清晰！

### 使用 SonarQube

正如你在第 4 章“使用 Maven、Gradle 和 Jenkins 自动化你的 CI/CD 构建”中所学习的那样，你可以在 IDE 中运行 SonarLint，或者在构建中运行 SonarQube。它们都提供了一组标记为`performance`的规则。表 13.4 显示了它可以检测出的某些规则示例。

| 规则 | 原因 |
| --- | --- |
| 不应在循环中使用`+`拼接字符串。 | `StringBuilder`更高效。 |
| 当同时需要键和值时，应该遍历`entrySet()`。 | 使用`entrySet()`比持续调用`get()`稍微快一点。 |
| 不应使用同步类`Vector`、`Hashtable`、`Stack`和`StringBuffer`。 | 这些 API 在访问任何内容时都会锁定整个集合。它们在很久以前就被更高效的版本取代了。 |
| 在持有锁时，应使用`wait(...)`而不是`Thread.sleep(...)`。 | 可能导致可扩展性问题和潜在的死锁。优先使用响应式的`wait()`，因为它一旦被通知就会唤醒，而`sleep()`必须完成它的睡眠时间。 |

**表 13.4**：Sonar 性能规则示例

### 考虑性能

当你进行性能调优时，可能会发现问题出在少数领域之一。本节提供了一个清单，当你使用性能分析器确定原因后，可以利用它来思考每个瓶颈需要考虑的内容。

#### 网络/带宽

* 批量/减少网络调用次数
* 避免返回不必要的数据
* 缓存数据

#### CPU

* 使用更高效的算法
* 使用并行化（参见第 9 章）
* 尽可能异步执行工作

#### 内存

* 使用更高效的数据结构
* 仅在需要时保存数据
* 增加分配的内存

#### I/O

* 缓存数据
* 使用日志记录代替`printlns`（参见第 5 章“使用日志框架捕获应用程序状态”）
* 如果使用数据库，使用连接池

## 进一步参考

* Java Performance (O'Reilly, 2020)
* [`https://github.com/openjdk/jmh`](https://github.com/openjdk/jmh)
    JMH
* [`https://docs.oracle.com/en/java/javase/21/docs/specs/man/java.html`](https://docs.oracle.com/en/java/javase/21/docs/specs/man/java.html)
    `java.html`

# 14

了解更多生态系统

正如我们在引言中提到的，这本书向你介绍了许多在你作为 Java 工程师职业生涯中可能会遇到的最常见技术。Java 生态系统是庞大的，无法一次性涵盖或学习所有内容！

本章对你可能在某个时刻听过或处理过的许多技术进行了高层次概述。了解它们的用途将帮助你跟上对话，并知道在你准备使用它们时何时回来查看进一步参考。

## WR JAVADOC

当你学习 Java API 时（例如第 9 章“使用 Java 并发性实现应用程序并行”中的`Executors`），你会检查 Javadoc 以获取有关可用方法、参数等信息。你可能会好奇该文档是如何创建的。

在下面的示例中，代码带有特殊的 Javadoc 注释，如下所示：

```java
 /**
  * 一个包含关于读者
  * 可能想要学习的主题信息的对象。
  *
  * <p><<b> 还有更多内容可以学习！</b>>
  * 使用方法：
  * {@snippet lang = java:
  *      Learning learning = new Learning();
  *      learning.addTopic("Docker");
  * }</p>
  */
  public class Learning {
    private Set<String> topics;
    /**
      * 创建一个新的 Learning 对象
      */
    public Learning() {
       topics = new HashSet<>();
    }
    /**
      * 存储读者想要学习的主题。
      *
      * @param topic 要学习的主题名称
      * @return 如果此主题未被存储则返回 {@code true}
      */
    public boolean addTopic(String topic) {
       return topics.add(topic);
    }
 }
```

第 4–14 行、17–19 行和 23–28 行展示了三个 Javadoc 注释。如从第 8 行所示，Javadoc 注释可以包含一组有限的 HTML 标签。第 10–13 行展示了 Java 18 中添加的功能，它允许你的 IDE 和其他生成的文档使用 Java 和其他特定语言的代码示例来格式化 Javadoc 部分。第 26 和第 27 行展示了`@param`和`@return`注解，它们提供了关于方法参数和返回类型的信息。Javadoc 还有许多其他功能，例如额外的包级文档。关于编写 Javadoc 的更多信息，请参见“进一步引用”。

你可以在构建过程中生成 Javadoc。例如，在`<reporting>`标签中使用`maven-javadoc-plugin`会导致在运行`maven site`时创建 Javadoc。

## 比较 JVM 语言

本书重点关注了 Java，正如你可能推断的那样，它是 JVM 上最流行的语言，因为这些字母代表“Java Virtual Machine”（Java 虚拟机）。还有许多其他运行在 JVM 上的语言。在接下来的章节中，你将尝试三种 JVM 语言：Kotlin、Groovy 和 Scala。还有许多其他语言，包括用于纯函数编程的 Clojure、允许 Ruby 应用程序运行在 JVM 上的 JRuby，以及为 JVM 提供 Python 实现的 Jython。

### 采样 Kotlin

Kotlin 是一种用于编写 Android 应用程序流行语言，并正成为 Java 的流行替代方案。Java 代码可以调用 Kotlin 代码，反亦然。Kotlin 允许你编写更简洁的代码，并提供了许多方便的功能，例如在编译时而不是运行时捕获空指针错误。接下来的示例展示了一些 Kotlin 特性：

```kotlin
1:  package com.wiley.realworldjava.more
2:
3:  class Destination(val city: String, val state: String)
4:
5:  fun countCitiesInCalifornia(cities: List<Destination>): Int {
6:     return cities.count { it.state == "California" }
7:  }
8:
9:  fun main() {
10:    val cities = listOf(Destination("Atlanta", "Georgia"),
11:       Destination("San Jose", "California"),
12:       Destination("Denver", "Colorado"),
13:       Destination("San Diego", "California"))
14: 
15:    val californiaCityCount = countCitiesInCalifornia(cities)
16:    print("Visited ${cities.size} cities " +
17:       "starting with ${cities.first().city}");
18:    println(" including $californiaCityCount in California")
19: }
```

与 Java 一样，第 1 行的包语句（package statement）是可选的。第 3 行展示了如何创建一个数据类（data class）。这些与 Java records 类似，只需一行即可创建一个简单的数据结构。参数声明中的`val`意味着数据类型是不可变的，与之相反，`var`是可变的。与 Java 不同的是，类型声明`String`位于参数名之后。

第 5–6 行展示了如何在 Kotlin 中创建函数；此处的接收接受一个名为`cities`的单个`List`参数并返回一个`Int`。实现使用了一个简洁的函数式编程语句来计算`state`为 California 的`Destination`值的数量。与 Java 类似，使用了 lambda 表达式来封装匹配逻辑。然而，它比 Java 更简洁。不需要 lambda 变量，因为`it`是默认提供的。

第 9 行声明了一个`main`方法，它比所有 Java 程序员都熟悉的`public static void main(String[] args)`要短得多。`args`参数是可选的，由于没有使用它，我们省略了它。第 10–13 行使用`listOf()`函数创建了一个不可变列表。注意在实例化`Destination`对象时没有使用`new`关键字。

第 16–18 行展示了用于输出的简洁代码。打印时省略了`System.out`。此外，使用了`$`，这意味着变量在字符串中通过带有`$`声明（例如`$californiaCityCount`）时会被求值。此外，可以在`${}`内配置代码，允许直接在字符串内部调用方法。最后，注意使用的是`size`而不是`size()`，因为 Kotlin 将`size`提供了一个属性。

### 采样 Groovy

Groovy 是一种脚本语言，这意味着你不需要编译。与许多其他语言一样，Groovy 不需要指定类型。以下是将上述 Kotlin 示例翻译为 Groovy 的代码：



```groovy
1:  class Destination {
2:     String city
3:     String state
4: 
5:     Destination(String city, String state) {
6:        this.city = city
7:        this.state = state
8:     }
9:  }
10:
11: private static int countCitiesInCalifornia(List<Destination> cities) {
12:    cities.count { it.state == "California" }
13: }
14: 
15: def cities = [
16:    new Destination("Atlanta", "Georgia"),
17:    new Destination("San Jose", "California"),
18:    new Destination("Denver", "Colorado"),
19:    new Destination("San Diego", "California")
20: ]
21:
22: def californiaCityCount = countCitiesInCalifornia(cities)
23: print "Visited ${cities.size()} cities " +
24:    "starting with ${cities.first().city}"
25: println " including $californiaCityCount in California"
```

在 Groovy 中，包声明也是可选的。第 1–9 行创建了一个类。虽然可以根据实例变量使用属性，但必须编写构造函数才能被调用。

第 11–13 行使用在 Java 中看起来熟悉的签名声明了一个函数。其实现与 Kotlin 版本匹配，但缺少了 `return` 关键字，尽管该方法有返回值。如果你省略了 `return`，Groovy 会自动返回函数中最后一个语句产生的值。

注意第 15–20 行使用括号 `[]` 包裹内容创建一个可变列表。与 Kotlin 不同，注意创建对象实例时需要 `new` 关键字。

第 22 行展示了当你不想编写变量类型时，Groovy 使用 `def`。第 23–25 行与 Kotlin 相同，但 `size()` 必须使用方法名。

## 采样 Scala

Scala 是一种编译语言，设计初衷是为了高效处理大量数据，以及用于分布式系统。此外，Scala 内置了对许多函数式编程模式的支持。

```scala
1:  package com.wiley.realworldjava.more
2:
3:  case class Destination(city: String, state: String)
4:
5:  object Travel {
6:
7:     private def countCitiesInCalifornia(
8:        cities: List[Destination]): Int = {
9:        cities.count(_.state == "California")
10:    }
11:
12:    def main(args: Array[String]): Unit = {
13:       val cities = List(
14:          Destination("Atlanta", "Georgia"),
15:          Destination("San Jose", "California"),
16:          Destination("Denver", "Colorado"),
17:          Destination("San Diego", "California")
18:       )
19:
20:       val californiaCityCount = countCitiesInCalifornia(cities)
21:       print(s"Visited ${cities.size} cities" +
22:          s"starting with ${cities.head.city}")
23:       println(s" including $californiaCityCount in California")
24:    }
25: }
```

你可以看到不同的 JVM 语言具有一些共同元素。Scala 创建函数时像 Groovy 一样使用 `def`。`val` 声明和 `Int` 返回值类似于 Kotlin。

也有一些独特的元素。第 3 行显示了 `case` 类，这是一种用于生成不可变数据结构的类。虽然它支持泛型，但在 Java 使用 `<` 和 `>` 的地方 Scala 使用方括号，如你在第 8 行的 `List[Destination]` 类型声明中看到的那样。这种实现看起来与 Groovy 很像，但 `_` 被用作默认的 lambda 变量。

第 12 行使用了 `Unit`，它是 Java 中 `void` 的 Scala 等物。在第 21–23 行，你可以看到 `s` 位于字符串之前，告诉运行时使用字符串插值。第 22 行还显示提供了 `head` 而不是使用 `first()` 来获取第一个元素。

## 探索 Jakarta EE

正如我们在第 1 章中提到的“我们是如何到达这里的：Java 简史”，Jakarta EE（企业版）是企业级应用 Spring 的替代方案。Jakarta EE 在开源之前被称为 Java EE。

你在 Spring 中看到的一些概念依赖于 Jakarta EE。例如，在第 6 章“直解 Spring 框架”中，你学习了过滤器（filters）也称为 servlet 过滤器（servlet filters）。Servlet 是一个处理请求并返回响应的子类。最常见的类型是 `jakarta.servlet.http.HttpServlet`，用于处理 Web 请求和响应。

Jakarta EE 被组织成各种规范，你可以只使用需要的部分。例如，核心配置文件（core profile）用于微服务，而 Web 描述文件（web profile）用于 Web 应用程序。

表 14.1 中列出的 Spring 项目多。这是因为 Jakarta EE 项目的粒度更细。Jakarta EE 和 Spring 是极佳的竞争对手，并提供了你预期的绝大部分常用功能。你所属的机构可能有某种偏好，所以你应该使用那一个！

| 项目 | 描述 |
| --- | --- |
| Jakarta EE Platform | Jakarta EE 最常用部分的伞型项目，包括核心配置文件和 Web 配置文件 |
| Jakarta Batch | 用于批处理应用程序 |
| Jakarta Enterprise Java Beans | 企业级组件的架构 |
| Jakarta Faces | 提供一个 MVC 框架 |
| Jakarta Mail | 用于发送电子邮件 |
| Jakarta Messaging | 用于 Java 消息服务 (JMS) |
| Jakarta Persistence | 支持对象关系映射 |
| Jakarta RESTful Web Services | 用于创建 REST Web 服务 |
| Jakarta Security | 添加授权和身份验证支持 |
| Jakarta Transactions | 支持跨多个数据存储的事务 |
| Jakarta XML Binding | 映射 Java 对象和 XML（Jackson 的竞争对手，曾用于附录“读写 XML、JSON 和 YAML”） |

表 14.1：Jakarta EE 项目示例

## 比较数据库类型

本书中的应用程序要么在内存中完成所有操作，要么从文件中读取数据。在现实世界中，你将希望处理更有组织化的信息源。

### 理解关系型数据库

关系型数据库以行和列的形式存储数据。图 14.1

图 14.1：关系型数据库

关系型数据库使用名为 SQL（结构化查询语言）的语言处理数据。有四种主要操作构成了常用的 CRUD（创建、读取、更新、删除）。表 14.2：

| ```INSERT INTO exhibits (name, num_acres) VALUES ('Asian Elephant', 3.5);``` | 向定义的列插入新行 |
| ```SELECT * FROM exhibits WHERE ID = 3;``` | 带 WHERE 子句从表中读取数据 |
| ```UPDATE exhibits SET num_acres = num_acres + .5 WHERE name = 'Asian Elephant';``` | 带 WHERE 子句设置列的值 |
| ```DELETE FROM exhibits WHERE name = 'Asian Elephant';``` | 带 WHERE 子句删除行 |

表 14.2：SQL 关键字

使用 SQL 的替代方案是使用对象关系映射（ORM）框架，它在背后为你将数据库映射到 Java 对象。Hibernate、Spring 和 Java 持久体系（JPA）都是 ORM 的选择。

### 理解 NoSQL 数据库

NoSQL 数据库用于存储非结构化或部分结构化的数据，此时行和列可能不是最佳选择。正如你所想象的，它们使用 SQL 进行查询。以下是流行的 NoSQL 类型：

*   **文档**：以 JSON 文档存储数据，允许每条数据具有不同的属性。Couchbase 和 MongoDB 是最常见的实现。
*   **图**：以节点和关系的图存储数据。Neo4J 是最流行的实现。
*   **键值**：像映射一样以键值对存储数据。Redis 是最流行的实现。
*   **时间序列**：按时间存储数据。InfluxDB 是最流行的实现。
*   **宽列存储**：按列而非行存储数据。Cassandra 是最流行的实现。

## 了解集成

除了数据库，还有许多 Java 应用集成的常用技术。本节将解释 JMS、LDAP 和 EJBs 是如何融入 Java 世界的。

Java Message Service (JMS) 用于系统和进程之间的异步通信。消息被放置在队列中。单个接收者可以稍后通过某种模式获取该消息进行处理。或者，你可以设置一个系统将消息投递给许多接收者。

轻量级目录访问协议 (LDAP) 用于查找用户信息。它通常用于确定某人属于哪些组以及他们拥有哪些访问权限。此外，还可以提供有关用户的信息，例如部门 ID 或开始日期。

Enterprise Java Beans (企业 Java Beans) 代表 Jakarta EE 中的组件，可以为它们添加事务和安全等服务。它们是 Spring 的替代方案，Spring 提供了相同的功能但更具灵活性。以下是 EJB 的类型：

- 无状态会话豆（Stateless session beans）：用于提供服务，无需在不同访问之间记住用户信息。
- 有状态会话豆（Stateful session beans）：用于提供需要记住用户数据的服务。这种类型较常见，因为用户数据通常存储在应用程序的其他层中。
- 单例会话豆（Singleton session beans）：用于整个应用程序共享的数据。
- 消息驱动豆（Message-driven beans）：用于处理 JMS 消息。

在过去，实体豆（entity beans）被用于处理数据。行业已经转向了 JPA 和其他对象关系映射框架。

# 部署 Java

在本书中，所有的开发都在你的计算机上完成，并且你在命令行中启动了一些应用程序。这与企业级软件形成对比，企业级软件运行在用户可以访问的地方，而那里绝不是你的电脑。本节描述了用于托管你的应用程序的主要类别。

## 区分 Web 服务器和应用服务器

在向用户提供静态内容（如 HTML、CSS 和 JavaScript）时，你可能会遇到 Web 服务器。虽然 Web 服务器也可以提供动态语言，但它们仅限于运行 Python 和 Ruby 等脚本语言。最常见的 Web 服务器是 Apache HTTP Server 和 nginx。

应用服务器能够运行封装为 WAR（Web 档）或 EAR（企业归档）的 Java 代码。WAR 文件由 JAR 文件以及一个带有处理 Web 请求细节的 Web 目录结构组成。EAR 文件可以包含 WAR 文件、JAR 文件和 Enterprise Java Beans (EJBs)。

常见的应用服务器包括 Apache Tomcat、Glassfish、JBoss、Papaya 和 IBM WebSphere。Spring Boot MVC 应用程序运行嵌入的 Apache Tomcat。

### 使用容器

无论你运行的是什么应用程序，无论是简单的独立应用程序、某些 Spring Boot 应用程序还是高流量 Web 服务器，你都需要一台带有操作系统的机器来运行它。在大型组织中，另一个团队负责该操作系统的维护和补丁。为了避免意外，许多团队使用类似 Docker 的容器。容器是可执行的包，不仅包含你的应用程序，还包含操作系统及其依赖的任何软件。容器镜像被打包并托管，你只需要下载并运行它即可，无需安装或配置。

在分发软件供他人运行时，供应商对环境有更多的控制权，从而降低了支持成本。例如，在第 4 章“使用 Maven、Gradle 和 Jenkins 自动化你的 CI/CD 构建”中，安装 Jenkins 仅需运行两个命令：

```
docker pull jenkins/jenkins
docker run --name jenkins -p 8080:8080 jenkins/jenkins
```

`pull` 命令下载了镜像，`run` 命令设置了初始配置。通过以下操作后续安装更加简单：

```
docker start jenkins
```

由于名称和端口已经设置好，你只需要执行 `start`。

与 Java 构物的 Maven Central 类似，Docker 使用了一个名为 DockerHub 的仓库，地址位于 [`https://hub.docker.com`](https://hub.docker.com)。配置包含在一个名为 `Dockerfile` 的文件中。适用于 Alpine Linux 的 Jenkins `Dockerfile` 开头如下：

```
1:  ARG ALPINE_TAG=3.20.3
2:
3:  FROM alpine:"${ALPINE_TAG}" AS jre-build
4:
5:  ARG JAVA_VERSION=17.0.12_7
6:
7:  SHELL ["/bin/ash", "-o", "pipefail", "-c"]
8:
9:  COPY jdk-download-url.sh /usr/bin/jdk-download-url.sh
10: COPY jdk-download.sh /usr/bin/jdk-download.sh
11:
12: RUN apk add --no-cache \
13:    ca-certificates \
14:    jq \
15:    curl \
16:    && rm -fr /var/cache/apk/* \
17:    && /usr/bin/jdk-download.sh alpine
18:
19: ENV PATH="/opt/jdk-${JAVA_VERSION}/bin:${PATH}"
```

此 `Dockerfile` 中的粗体字是指令。示例中使用的指令如下：

- `ARG`：定义一个本地变量，该变量仅在 `Dockerfile` 中，不能在镜像中引用。
- `FROM`：从基础镜像构建新镜像，在本例中为 Alpine Linux。基础镜像可以是操作系统或你想要添加的另一个 `Dockerfile`。
- `SHELL`：在 Linux/Mac 上，你可以选择在命令行操作中使用哪个 shell。
- `COPY`：将运行构建的机器的文件复制到镜像中。
- `RUN`：运行操作系统命令。通常运行多个用 `&&` 连接的命令。
- `ENV`：设置环境变量。

### 发布到云端

目前讨论的服务器和容器可以部署到由他人拥的数据中心。云计算是指数据中心由他人拥有的。Amazon Web Services (AWS)、Microsoft Azure 和 Google Cloud 是三个常见的云环境。

每个云提供者使用不同的术语，如表 14.3 所示。

| 技术 | AWS | AZURE | GOOGLE CLOUD |
| --- | --- | --- | --- |
| 服务器—为应用程序提供操作系统 | Elastic Compute Cloud (EC2) | Azure Virtual Machine | Google Compute Engine (GCE) |
| Kubernetes 支持 | Elastic Kubernetes Service (EKS) | Azure Kubernetes Service (AKS) | Google Kubernetes Engine (GKE) |
| 无服务器计算—用于短运行应用程序 | Lambda | Azure Functions | Google Cloud Functions |
| 平台服务—用于 Web 应用程序 | Elastic Beanstalk | Azure App Services | Google Application Engine (GAE) |
| SQL 数据库 | Relational Database (RDS) Aurora—无服务器替代 | Azure SQL Database | Cloud SQL |
| 提供静态内容 | Simple Storage Service (S3) | Azure Blob Storage | Google Cloud Storage (GCS) |
| 内容分发网络 (CDN)—缓存数据 | CloudFront | Azure CDN | Cloud CDN |



| 网络 | 虚拟私有云 (VPC) | AWS 虚拟专用网络 (VPN) | Google Cloud Networking Services |
| --- | --- | --- | --- |
| 电子邮件/短信报警 | Simple Networking Service (SNS) | Azure Notification Hubs | Firebase Cloud Messaging |
| 消息队列 | Simple Queue Services (SQS) | Azure Service Bus Azure Storage Queues | Google Cloud Pub/Sub |
| 访问管理 | 身份和访问管理 (IAM) | Azure AD | Cloud Identity |

## 构建 REST API

表述状态转移 (REST) 是 Java 创建 Web 服务最常用的 API。以下是最常见的操作：

- `GET`：获取资源(s)
- `DELETE`：删除资源
- `POST`：创建资源
- `PUT`：更新资源
- `PATCH`：部分更新资源

根据 API 的功能，通常只会实现 `PUT` 或 `PATCH` 之一，而不是两者都实现。

### 创建 Web 服务

正如你在第 6 章中看到的那样，Spring 让你轻松地创建一个 REST API。以下显示了一个包含两个 `GET`、一个 `POST` 和一个 `DELETE` 动作的 `@RestController`：

```java
@RestController
@RequestMapping("/api")
public class CitiesController {

    private List<Destination> cities = new ArrayList<>();

    @GetMapping("/cities")
    public List<Destination> cities() {
        return cities;
    }

    @GetMapping("/citiesByState/{state}")
    public List<Destination> citiesByState(
            @PathVariable("state") String state) {
        return cities.stream()
                .filter(c -> c.state().equals(state))
                .toList();
    }

    @PostMapping("/add")
    public void add(@RequestParam(name="city") String city,
                    @RequestParam(name="state") String state) {
        cities.add(new Destination(city, state));
    }

    @DeleteMapping("/delete")
    public void delete(@RequestParam(name="city") String city,
                       @RequestParam(name="state") String state) {
        Destination dest = new Destination(city, state);
        cities.remove(dest);
    }
}
```

第 7–10 行定义了一个 `GET` 所有定义城市的方法。可以如下所示调用：

```bash
curl http://localhost:8080/api/cities
```

由于 `Jackson` 是 `POM` 中的一个依赖，Spring 会自动将 Java 应用程序转换为 JSON。当应用程序首次启动时，结果为 `[]`，因为列表是空的。如果你想查看 JSON 语法的描述，请参附录。添加城市后，它看起来像这样：

```json
[{"city":"New York","state":"NY"}]
```

第 11–17 行显示另一个 `GET`。这次使用了 URL 参数，以便传递州名称。例如：

```bash
curl http://localhost:8080/api/citiesByState/NY
```

第 18–29 行声明了 `POST` 和 `DELETE` 方法。每个方法都从请求体中的 JSON 接收参数，并如下所示调用：

```bash
curl -d city='New York&state=NY' http://localhost:8080/api/add
curl -X "DELETE" -d city='New York&state=NY' 
   http://localhost:8080/api/delete
```

### API 文档化

Swagger 将文档与在浏览器中实际运行 REST API 的结合。使用 group ID 为 `org.springdoc` 且 artifact ID 为 `openapi-starter-webmvc-ui` 的依赖可以轻松地添加到 Spring 应用中。虽然你可以使用 `curl` 访问 REST API 而无需构建，但 Swagger 确实需要构建并启动。在 `rest-apis` 目录下运行以下命令：

```bash
mvn clean verify
java -jar target/rest-api-0.0.1-SNAPSHOT.jar
```

一旦应用程序启动，在浏览器中访问[`http://localhost:8080/swagger-ui/index.html`](http://localhost:8080/swagger-ui/index.html) 即可打开 Swagger。如你在图 14.2 所示，所有四个 REST API 都会自动显示，无需任何额外工作。

![城市控制器 OpenAPI 定义的截图，包含可用的 API 端点。它包含了用于管理城市数据的 POST、GET 和 DELETE 方法，服务器 URL 设置为 localhost 的 8080 端口。](img/c14f002.png)

`图 14.2`: Swagger REST APIs

要运行 API，展开你感兴趣的项并点击“Try it out”（尝试运行）。在添加任何所需的参数后，点击“Execute”（执行）。如你在图 14.3 所示，系统也生成了城市和州参数的输入字段。

![添加城市的 API 请求面板截图，包含两个必填参数：城市设置为 New York，州设置为 NY，以及执行或清除输入的选项。](img/c14f003.png)

`图 14.3`: 执行 API

系统会自动生成一个 `curl` 命令，如果你想在命令行中进行测试，这非常有帮助。此外，由于 REST API 调用成功，将返回 200 响应码。

## 选择虚拟机

有许多 Java 虚拟机可以下载。以下列表让你对这些选项有一个大致的了解：

- `Open JDK`：由 Oracle 与一组其他机构共同开发的免费 JDK。许多供应商分发基于 `Open JDK` 的构建版本，包括 `Amazon Corretto`、`Eclipse Temurin (Adoptium)`、`Microsoft Open JDK` 和 `Red Hat Open JDK`。
- `Oracle JDK`：Oracle 的免费 JDK。基于 `Open JDK` 的分发构建版本包括 `Amazon Corretto`、`Eclipse Temurin (Adoptium)`、`Microsoft Open JDK` 和 `Red Hat Open JDK`。
- `Azul`：Oracle 的免费 JDK，由一组机构共同开发。
- `Graal VM`：Oracle 的免费 JDK，由一组机构共同开发。

## 库的选择

Java 生态系统非常庞大，有很多库可以帮助你更快速地编写。表 14.4 列出了我们喜欢的一些。

| 库 | 描述 | 是否免费 |
| --- | --- | --- |
| `Akka` | 并发和分布式系统。 | Free |
| `Apache Commons` | 许多功能的父项目，如 CSV 读写。 | Free |
| `Apache Kafka` | 用于实时数据的事件流框架。 | Free |
| `Apache PDF Box` | 读取和写入 PDF。 | Free |
| `Apache POI` | 读取和写入 Word 和 Excel 格式。 | Free |
| `Eclipse Collections` | `Collections` 接口的扩展。 | Free |
| `Google Guava` | 流行的集合库。 | Free |
| `iText` | 读取和写入 PDF。 | Free（在有限条件下） |
| `RxJava` | 异步和基于事件程序。 | Free |

## 应用程序安全

安全对于你的任何项目都是重要的。在构建应用程序时，你应该从 OWASP Top 10 中寻找灵感。

### 探索 OWASP Top 10

开放 Web 安全项目（OWASP）Top 10 是构建应用程序时应考虑的关键安全指南。在本节中，你将看到 Web 和移动端的 Top 10 并理解它们的重要性。

OWASP Top 10 每隔几年更新一次；本书出版时的最新版本是 2021 版。（下一次更新预计在 2025 年上半年）。还有一个我们未涵盖的移动版本。

以下是每个项目的概述。OWASP 网站（参见“参考文献”）提供了关于每个项目的详细信息。

1. `访问控制失效`：用户只能看到其权限允许的数据或执行的操作。
2. `加密问题`：数据在静态存储（例如在数据库中）和传输过程中应受到保护。
3. `注入`：所有数据必须经过清理（理想情况下针对“白名单”），以确保用户提供的数据符合预期类型且不会更改任何查询或输出的含义。
4. `不安全的设计`：此项目涉及设计和架构中缺乏安全控制。
5. `安全配置错误`：应考虑所有框架的默认设置，并在需要更合适的值时进行更改。所有设置都应安全配置。
6. `脆弱和过时的组件`：应尽可能升级有漏洞的库并移除未使用的库。几年前，新闻中出现了关于流行的 `Log4J` 日志框架的安全漏洞。而现在，多年以后，仍有应用程序在使用该版本！
7. `身份与授权失效`：不应允许用户冒充其他用户或拦截/重用他们的凭据。
8. `安全与数据完整性失效`：所有下载内容都应经过验证以确保其合法性。
9. `安全日志与监控失效`：应该对数据进行记录和监控，以便尽早检测攻击。
10. `服务器请求伪造 (SSRF)`：应用程序不应能够向意外的目标发送数据。

### 比较安全工具类型

有很多类工具可以保护你的应用程序。以下是需要了解的缩写：

- `静态应用安全测试 (SAST)`：通过查看源代码尝试寻找漏洞的工具。来自第四章的 `SonarQube` 就是一个 `SAST` 工具。
- `动态应用安全测试 (DAST)`：在应用程序运行时尝试向其注入漏洞的工具。
- `交互式应用安全测试 (IAST)`：在运行的应用程序内部放置代理以在非生产环境中进行测试。
- `运行时应用保护 (RASP)`：在生产环境中运行的应用程序内部放置代理以寻找攻击的工具。

## 关注变化

技术是有趣的，因为它变化频繁。这意味着阅读并保持更新至关重要。本节建议了可以跟进学习的阅读渠道。

如果你使用社交媒体，[`https://javabubble.org`](https://javabubble.org) 是一个极佳的地方，可以让你在 Twitter/X、Mastodon 和 LinkedIn 上找到值得关注的人，在其他平台上也有较少的人选。

对于文章和博客帖子，以下网站是非常棒的：

- [`https://dev.java`](https://dev.java)
- [`https://www.infoq.com`](https://www.infoq.com)
- [`https://foojay.io`](https://foojay.io)
- [`https://dzone.com`](https://dzone.com)

## 更多参考

- `Javadoc`
  - [`https://docs.oracle.com/en/java/javase/21/docs/api/index.html:`](https://docs.oracle.com/en/java/javase/21/docs/api/index.html:) Java 21 `Javadoc`
  - [`https://docs.oracle.com/en/java/javase/21/javadoc/javadoc.html:`](https://docs.oracle.com/en/java/javase/21/javadoc/javadoc.html:) 包含新代码片段功能的 `Javadoc`指南
  - [`https://www.oracle.com/technical-resources/articles/java/javadoc-tool.html:`](https://www.oracle.com/technical-resources/articles/java/javadoc-tool.html:) 如何编写 `Javadoc`
- `JVM 语言`
  - [`https://dev.java/playground:`](https://dev.java/playground:) 在线运行 Java 代码
  - [`https://kotlinlang.org/docs/getting-started.html:`](https://kotlinlang.org/docs/getting-started.html:) Kotlin 文档
  - [`https://play.kotlinlang.org`](https://play.kotlinlang.org): 在线运行 Kotlin 代码
  - [`https://groovy-lang.org/documentation.html:`](https://groovy-lang.org/documentation.html:) Groovy 文档
  - [`https://groovyide.com/playground:`](https://groovyide.com/playground:) 在线运行 Groovy 代码
  - [`https://docs.scala-lang.org`](https://docs.scala-lang.org): Scala 文档
  - [`https://scastie.scala-lang.org`](https://scastie.scala-lang.org): 在线运行 Scala 代码
- `Jakarta EE`
  - [`https://projects.eclipse.org/projects/ee4j.jakartaee-platform:`](https://projects.eclipse.org/projects/ee4j.jakartaee-platform:) `Jakarta EE` 主要部分的伞型项目
  - [`https://jakarta.ee/projects:`](https://jakarta.ee/projects:) 项目完整列表
  - [`https://javadoc.io`](https://javadoc.io): 搜索 ID `Jakarta` 以查看每个项目的 `Javadoc`
- `容器`
  - [`https://hub.docker.com`](https://hub.docker.com): DockerHub
  - [`https://kubernetes.io/docs/home:`](https://kubernetes.io/docs/home:) Kubernetes
- `云`
  - [`https://docs.aws.amazon.com`](https://docs.aws.amazon.com): AWS
  - [`https://learn.microsoft.com/en-us/azure:`](https://learn.microsoft.com/en-us/azure:) Azure
  - [`https://cloud.google.com/docs:`](https://cloud.google.com/docs:) Google Cloud
- `库`
  - [`https://akka.io`](https://akka.io): Akka
  - [`https://commons.apache.org`](https://commons.apache.org): Apache Commons
  - [`https://pdfbox.apache.org`](https://pdfbox.apache.org): Apache PDF Box
  - [`https://poi.apache.org`](https://poi.apache.org): Apache POI
  - [`https://eclipse.dev/collections:`](https://eclipse.dev/collections:) Eclipse Collections
  - [`https://guava.dev`](https://guava.dev): Guava



- [`https://itext.com`](https://itext.com) iText
- [`https://github.com/RxJava`](https://github.com/RxJava) RxJava

## 总结

在本章中，你学习了生态系统中的各种技术。`Javadoc` 用于记录 Java API，而 `Kotlin`、`Groovy` 和 `Scala` 只是许多 JVM 语言之一。`Jakarta EE` 是 Spring 的竞争者，拥有许多满足需求的项目。事实上，Java 有许多可以下载的库。最后，你学习了一些安全原则以及如何跟上潮流。

# 附录：读取和写入 XML、JSON 和 YAML

当你思考时，一个 Java 对象由数据和功能组成。如果你可以通过某种方式提取数据、保存它们，然后将其与功能重新结合，你实际上实现了序列化。在本书中，我们在许多示例中使用了 XML、JSON 和 YAML。这三种格式都可以包含配置数据，也可以用于序列化数据，即将 Java 实例转换为可以存储在磁盘上或传输的格式。反之，反序列化是将这些文件还原为 Java 实例的过程。这些格式是非常重要的，因为它们频繁出现。

本附录将帮助你了解这些格式的基础，以及从程序读取和写入这些文件的方法。注意，我们涵盖的库具有许多功能。这些示例提供了基础知识，我们鼓励你探索这些库提供的优质在线文档。

## 处理 XML

XML 代表**扩展标记语言**。XML 文件使用 `.xml` 作为文件扩展名。书中几乎所有的章节在仓库中都有 XML 文件，因为我们大量使用 Maven，而 Maven 使用 `pom.xml` 文件来配置项目构建。REST API 和 RSS 馈也使用 XML。

*标记语言*是一种基于文本的语法，用于表示文档中标记之间的关系。HTML 和 GitHub 的 Markdown 语言都是其他标记语言。例如，在 HTML 中，你可以在段落中加粗文本；在 Markdown 中，你可以创建一个符号列表。

### 学习 XML 格式

与 HTML 和 Markdown 不同，XML 没有固定的元素集，但你可以根据需要创建自己的元素。这就是为什么它被称为“可扩展的”：虽然语法是定义良好的，但你可以通过自己的标签和属性以树形结构来扩展它。例如：

```xml
<book title="Real World Java">
   <edition>1</edition>
   <!-- multiple authors -->
   <authors>
      <author>Victor Grazi</author>
      <author>Jeanne Boyarsky</author>
   </authors>
   <paperback />
</book>
```

XML `element`（元素）是一个由起始 `tag`（标签）和相应的结束标签包围的部分。起始标签是由 `<` 和 `>` 包围的名称。结束标签是由 `</` 和 `>` 包围的相同名称。XML 中的元素必须嵌套，以确保起始标签和结束标签都是平衡的。每个 XML 文档都以一个根标签开始，在本例中是 `book`。标签可以用一个或多个 `attributes`（属性）来增强；其中的引号标签包含在起始标签内部。示例中的 `book` 标签有一个名为 `title` 的属性。

第三行是一个注释，由 `<!--` 和 `-->` 包围。注释允许跨行。

XML 文档的大部分结构为一系列嵌套的元素。在本例中，元素名称为 `book`、`edition`、`authors`、`author` 和 `paperback`。注意，除了 `paperback` 使用了简写外，每个元素都有起始标签和结束标签。对于没有任何内容的标签，这两种格式是等价的：

```xml
<paperback/>
<paperback></paperback>
```

第一个被称为空元素。第二个有起始标签和结束标签，中间没有任何内容。

XML 文件必须是 `well formed`（格式良好的），这意味着它们遵循所有这些规则：

- 标签和属性名区分大小写。`<paperback>` 和 `<Paperback>` 是不同的。
- 除非使用空标签，否则起始标签和结束标签都是必须的。
- 根元素之外的所有标签都必须嵌套在父标签下。
- 标签必须正确嵌套，这意味着子元素必须在其父元素之前关闭。

如果你看到过我们的任何 Maven POM 文件，可能会注意到 `pom.xml` 文件以此内容开头：

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

这是一个名为 `XML prolog`（XML 声明）的可选功能，用于指定字符编码。例如，UTF-8 在美国最常见。

你可能还注意到每个 `pom.xml` 文件开头有更多代码：

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
   xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance
   xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
   https://maven.apache.org/xsd/maven-4.0.0.xsd">
```

`xmlns` 属性代表“XML 命名空间”。命名空间是列出 XML 文件中允许元素的标准方法。此外，命名空间允许指定版本号。

其余部分指定 XML 架构定义的位置，在本例中是该数据的实际文件位置。如果你需要使用 XML 命名空间或架构定义，数据的作者将为你为你提供。对于常见的项，如 Maven POM），它是自动生成的。

### 使用 Jackson 读取 XML

Jackson 是一个用于程序化读取（反序列化）和写入（序列化）XML 的流行库。Jackson 最初作为一个 JSON 库，因此你会在代码中看到对 JSON 的引用。正如你想象的，你会在 JSON 部分再次看到 Jackson！

在你的 Maven 或 Gradle 构建中使用 Jackson，请访问 Maven Central 的 [`https://mvnrepository.com/artifact/com.fasterxml.jackson.dataformat/jackson-dataformat-xml`](https://mvnrepository.com/artifact/com.fasterxml.jackson.dataformat/jackson-dataformat-xml)，并为你的构建工具找到最新版本号。表 A.1 显示了在编写时每种配置的样子。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml
<dependency>
   <groupId>com.fasterxml.jackson.dataformat</groupId>
   <artifactId>jackson-dataformat-xml</artifactId>
   <version>2.17.2</version>
</dependency>
``` |
| Gradle (Groovy) | `implementation group: 'com.fasterxml.jackson.dataformat', name: 'jackson-dataformat-xml', version: '2.17.2'` |
| Gradle (Kotlin) | `implementation("com.fasterxml.jackson.dataformat:jackson-dataformat-xml:2.17.2")` |

表 A.1：将 Jackson 指定为依赖

要将 Jackson 引入你的项目，请获取适用于你构建工具的语法并将其包含在依赖中。（第 4 章，“使用 Maven、Gradle 和 Jenkins 自动化 CI/CD 构建”）中介绍了构建工具。）

要读取文件，创建一个 `ObjectMapper` 并使用它导航树形结构。

```java
10: File file = Path.of("src/main/resources/book.xml").toFile();
11: ObjectMapper mapper = new XmlMapper();
12: JsonNode root = mapper.readTree(file);
13:
14: System.out.println("Title: " + root.get("title").asText());
15: System.out.println("Title: " + root.get("title").asText());
```

```java
@JsonIgnore
public boolean isPaperbackBook() {
   return paperback != null;
}
```

`@JsonIgnore` 注解告诉 Jackson 不要包含该字段。尽管这是一个 XML 解析器，但注解中使用了 `JSON` 一词。请记住，该库同时处理 XML 和 `JSON`，因此许多代码是共享的。

此外，你可以通过以下方式告诉 Jackson 在生成的 XML 文件中将 `book` 标签设为小写：

```java
@JacksonXmlRootElement(localName = "book")
public class Book {
```

现在映射已经完成，让我们编写代码来使用除作者之外所有标签的默认值。

```java
Book book = new Book();
book.setAuthors(List.of("Victor & Jeanne"));

ObjectMapper mapper = new XmlMapper();

String xml = mapper
   .writer()
   .withDefaultPrettyPrinter()
   .writeValueAsString(book);
System.out.println(xml);
```

代码从开头像之前的示例一样创建了一个 mapper。然后，它使用 mapper 的 `writer()` 方法告诉 Jackson 它想要写入。`withDefaultPrettyPrinter()` 表示对输出使用“美化”格式。如果你不使用美化打印器，所有的 XML 将生成在一行。代码随后写入 XML 并将其存储在名为 `xml` 的变量中。输出如下：

```xml
<book>
   <title/>
   <edition>0</edition>
   <paperback/>
   <authors>
      <author>Victor & Jeanne</author>
   </authors>
</book>
```

注意，对于未设置值的文本字段使用了空标签，因为它们是 `null`。相比之下，`edition` 是一个 `int` 类型，由于我们没有在类实例中提供值，它分配了 `int` 的默认值 `0`。同样注意 `&` 被转义为 `&amp;`，因为 `&` 是 XML 留的转义字符，程序会尽力避免使用它。

你也可以通过程序在没有 mapper 对象的情况下编写 XML 文件。这通常更复杂且不那么灵活。例如，你无法通过这种方法添加属性。但你会遇到这类代码：

```java
20: ObjectMapper mapper = new XmlMapper();
21:
22: ObjectNode root = mapper.createObjectNode();
23: root.put("edition", "1");
24:
25: String xml = mapper
26:    .writer()
27:    .withRootName("book")
28:    .writeValueAsString(root);
29: System.out.println(xml);
```

第 20 行创建普通的 mapper。第 22 行创建一个新的未命名的 XML 节点。它在第 27 行被命名，写入时将使用它。在第 23 行，`put()` 方法创建了一个名为 `edition` 的子 XML 节点。在这个示例中，我们省略了美化打印，你可以看到输出在单行上的样子。

```xml
<book><edition>1</edition></book>
```

### 使用 DOM 读写 XML

文档对象模型 (DOM) 是 Jackson 的替代方案，它是 Java 用于 XML 处理 (JAXP) API 的一部分，直接在 JDK 中可用。这些类位于 `javax.xml.parsers` 包中。

DOM API 提供了直接导航 XML 树的方法。它比 Jackson 更冗长，所以如果你使用它，你会发现自己需要创建一些便捷方法。这个示例读取了与之前 Jackson 示例相同的 XML 文件：

```java
File file = Path.of("src/main/resources/book.xml").toFile();

// 要开始解析，DOM 需要一个 DocumentBuilder。获取步骤如下：
DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
DocumentBuilder builder = factory.newDocumentBuilder();
Document doc = builder.parse(file);

Node root = doc.getElementsByTagName("book").item(0);
System.out.println(
   root.getAttributes().getNamedItem("title").getNodeValue());
System.out.println(
   doc.getElementsByTagName("edition").item(0).getTextContent());

System.out.println("Paperback? " + (doc.getElementsByTagName(
   "paperback").getLength() != 0));

NodeList authors = doc.getElementsByTagName("author");
for (int i = 0; i < authors.getLength(); i++) {
   System.out.println(authors.item(i).getTextContent());
}
```

如你所示，有一个 API 可以获取带有特定标签的所有元素。从元素中，你可以获取属性或标签之间的文本数据。你还可以遍历节点的所有子节点。

通过 DOM 写入文件包含大量的模板代码。

```java
DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
DocumentBuilder builder = factory.newDocumentBuilder();
Document doc = builder.newDocument();

Element root = doc.createElement("book");
doc.appendChild(root);

Element edition = doc.createElement("edition");
edition.appendChild(doc.createTextNode("1"));
root.appendChild(edition);

DOMSource source = new DOMSource(doc);
StreamResult result = new StreamResult(System.out);

TransformerFactory transformerFactory = TransformerFactory.newInstance();
Transformer transformer = transformerFactory.newTransformer();
transformer.setOutputProperty(OutputKeys.INDENT, "yes");
transformer.setOutputProperty(OutputKeys.OMIT_XML_DECLARATION, "yes");
transformer.transform(source, result);
```

在这里你可以看到 `createElement()` 用于创建标签，`createTextNode()` 用于添加标签内的文本。`Transformer` 用于设置。最后，`transform()` 方法写入 XML。

### 使用 SAX 读取 XML

JAXP 还包含了简单 XML API (SAX)，这是一种事件驱动的方法。由于 SAX 在读取时处理数据，因此不需要将整个文件加载到内存中，使其成为大文件的良好选择。注意 SAX 仅用于读取；你无法使用 SAX 写文件。

解析文件的第一步是创建一个处理器。对于简单的情况，处理器可以很短。



```java
class BookSaxHandler extends DefaultHandler {
   private boolean inTagText = false;
   private boolean paperback;

   @Override
   public void startElement(String uri, String localName,
         qualifiedName, Attributes attributes) {
      switch (qualifiedName) {
         case "edition", "author" -> inTagText = true;
         case "paperback" -> paperback = true;
         case "authors" ->
            System.out.println("Paperback? " + paperback);
         case "book" ->
            System.out.println(attributes.getValue("title"));
      }
   }

   @Override
   public void endElement(String uri, String localName,
         String qualifiedName) {
      inTagText = false;
   }

   @Override
   public void characters(char[] chars, int start, int length) {
      if (inTagText) {
         String text = new String(chars, start, length);
         System.out.println(text);
      }
   }
}
```

接下来是`startElement()`方法的覆盖，它使用`switch`根据标签执行不同的操作。请注意，`localName`仅在处理命名空间时才相关，因此此代码使用了`qualifiedName`。第 21 行在标签为`edition`或`author`时设置一个`boolean`。这是在`characters()`方法中使用的`boolean`。第 22 行记录是否看到了`paperback`标签，第 23–24 行在获取`authors`标签时打印是否看到过`paperback`。第 25–26 行在处理`book`标签时会打印属性`title`。

现在你已经有了处理器，实际读取起来就很简单了。

```java
File file = Path.of("src/main/resources/book.xml").toFile();

SAXParserFactory factory = SAXParserFactory.newInstance();
SAXParser parser = factory.newSAXParser();
BookSaxHandler handler = new BookSaxHandler();

parser.parse(file, handler);
```

这里发生的事情只有创建对象和调用`parse()`。所有的逻辑都在处理器类中。

### 比较 XML 库

有很多 XML 库。以下列出了一些较流行的库：

- **Faster XML Jackson**：该库提供了本章早些所示的多种读取和写入数据的方法。XML 和 JSON 的代码相似，这通常使得它成为一个很好的选择。
- **Java API for XML Processing (JAXP)**：你之前看到的 DOM 和 SAX 示例就是 JAXP。这些库适用于简单的用途，或者当你已经有在使用它们现有代码时。它们是内置在 JDK 中的。
- **Document Object Model for Java (DOM4J)**：该库比 JAXP 的 DOM 不那么冗长。对于大型 XML 文件，它的运行速度更快，内存效率也更高。
- **Xerces**：该库提供了比 JAXP 备选且更快的 DOM 和 SAX 实现。许多开源和商业产品在底层都使用了 Xerces。

## 处理 JSON

JSON（读音为“jay-sawn”或“jay-sahn”）代表 **J**ava**S**cript **O**bject **N**otation。与 XML 一样，它是指定数据的一种。JSON 的示例包括处理 REST API 和配置库（如日志记录）。JSON 文件最常用`.json`扩展，也可以使用`.jsn`。

### 学习 JSON 格式

让我们考虑如何将书籍 XML 文件转换为 JSON 格式：

```json
{
  "title": "Real World Java",
  "edition": 1,
  "authors": ["Victor Grazi", "Jeanne Boyarsky"],
  "paperback": true
}
```

数据由键/值对组成。在我们的示例中有四个键：`title`、`edition`、`authors`和`paperback`，它们代表 XML 示例中的四个元素。

代码显示值可以是各种数据类型，包括字符串、数字、数组和布尔值。JSON 是嵌套的，例如，为了给每个作者添加更多细节，可以将`authors`数组扩展为：

```json
"authors": [
  {
    "name": "Victor Grazi",
    "first": true
  },
  {
    "name": "Jeanne Boyarsky",
    "first": false
  }
],
```

JSON 文件必须遵守规则才能有效。特别是：

- 键对大小写敏感。
- 键必须用双引号括。
- 字符串必须用双引号括。
- 如果使用嵌套，它必须格式良好。
- 数据由逗号分隔。
- 最后一个键/值对之后没有逗号。

与 XML 不同，JSON 不支持注释。

JSON schema 是描述预期 JSON 数据形状的可选方式。有很多用于处理和查询 JSON 的工具，包括`jq`。

### 使用 Jackson 读取 JSON

还记得上一节中的 Jackson 吗？将 Jackson 用于 JSON 与使用它处理 XML 类似，这意味着这段代码看起来会很熟悉。我们会在每段代码之后强调差异，而不是从头开始解释。

如果你正在跟着操作，不需要添加依赖项，因为`jackson-databind`是`jackson-dataformat-xml`的传递性依赖。如果你是从零开始并想在 Maven 或 Gradle 构建中为 JSON 使用 Jackson，请前往 Maven Central 的`https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind`查找你构建工具的最新版本号。表 A.2 显示了在本文写作时每种配置的情况。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml<br><dependency><br>   <groupId>com.fasterxml.jackson.core</groupId><br>   <artifactId>jackson-databind</artifactId><br>   <version>2.17.2</version><br></dependency><br>``` |
| Gradle (Groovy) | `implementation group: 'com.fasterxml.jackson.core', name: 'jackson-databind', version: '2.17.2'` |
| Gradle (Kotlin) | `implementation("com.fasterxml.jackson.core:jackson-databind:2.17.2")` |

```java
ObjectMapper mapper = new JsonMapper();

ObjectNode root = mapper.createObjectNode();
root.put("edition", "1");

String json = mapper
   .writer()
   .writeValueAsString(root);
System.out.println(json);
```

再次，`mapper`和变量名现在指代 JSON。此外，设置根节点名称的方法调用已经消失了，因为 JSON 没有具命名根节点的概念。输出如下：

```json
{"edition":"1"}
```

### 使用 Gson 读写 JSON

Gson 是 Google 编写的一个轻量级 JSON 库。虽然我们建议在新项目中使用 Jackson，但 Gson 也被广泛使用。查看相似的基本操作是如何实现的也会很有帮助。这将帮助你在遇到其他库时更快地学会它们。

要在你的 Maven 或 Gradle 构建中使用 Gson，请前往 Maven Central 的[`https://mvnrepository.com/artifact/com.google.code.gson/gson`](https://mvnrepository.com/artifact/com.google.code.gson/gson)并找到适用于你构建工具的最新版本号。表 A.3 显示了在本书期间每种配置的情况。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml<br><dependency><br>   <groupId>com.google.code.gson</groupId><br>   <artifactId>gson</artifactId><br>   <version>2.11.0</version><br></dependency><br>``` |
| Gradle (Groovy) | `implementation group: 'com.google.code.gson', name: 'gson', version: '2.11.0'` |
| Gradle (Kotlin) | `implementation("com.google.code.gson:gson:2.11.0")` |

**表 A.3**：指定 Gson 作为依赖

获取适用于你构建工具的语法并将其包含在依赖中。

首先你创建`Book`类。

```java
public class Book {
   private String title;
   private int edition;

   @SerializedName("paperback")
   private boolean paperbackBook;
   private List<String> authors;
   // 为了节省空间省略了 getters 和 setters
}
```

注意与 Jackson 的唯一区别是 Gson 使用`@SerializedName`，它用于将 JSON 字段名映射到不同的 Java 字段名。创建`Book`实例的 Gson 惯用法如下：

```java
Gson gson = new Gson();
Book book = gson.fromJson(new FileReader(file), Book.class);
```

这种思路与 Jackson 类似。创建一个类来工作并调用 API（这次是`fromJson()`）来创建`Book`实例。以下是等效写入代码：

```java
Book book = new Book();
book.setAuthors(List.of("Victor & Jeanne"));

Gson gson = new Gson();
System.out.println(gson.toJson(book));
```

这段代码调用了`toJson()`，因为它是在写入 JSON，而不是用于读取的`fromJson()`。输出结果如下：

```json
{"edition":0,"authors":["Victor \u0026 Jeanne"]}
```

但那个`\u0026`是什么？那是一个 Unicode 转义序列；默认情况下，Gson 会使输出符合 HTML 安全。虽然这是合法的 JSON，但它可能不是你预期的结果。你可以使用`GsonBuilder`来关闭此行为：

```java
Gson gson = new GsonBuilder().disableHtmlEscaping().create();
```

### 比较 JSON 库

有很多 JSON 库。以下列表列出一些比较流行的库：

- **Jackson**：该库提供了多种读取和写入数据的方法，如本章前面所示。对于 XML 和 JSON，代码是的，这通常使其成为一个很好的选择。
- **Gson**：这是 Google 的轻量级库，在本章中也被使用。
- **JSON.Java**：该库也称为`org.json`，它是作为参考实现构建的，但仍在更新。
- **JSON-P**和**JSON-B**：这些是 Jakarta 的解析和绑定规范。

## 处理 YAML

YAML（发音与 camel 同样）最初代表 **Y**et **A**nother **M**arkup **L**anguage（又一种标记语言），但后来重命名为 **Y**AML **A**in't **M**arkup **L**anguage（YAML 不是标记语言）。在不纠结标记语言定义的情况下，YAML 用缩进取代了标签和括号，是指定数据和配置的一种简洁方式。

YAML 的示例包括配置 Spring Cloud Security 或日志框架等库。许多 CI/CD 系统甚至允许你使用 YAML 指定你的构建流水线。YAML 文件可以使用`.yaml`或`.yml`扩展名。

### 学习 YAML 格式

让我们回到我们的书籍文件，这次使用 YAML：

```yaml
---
title: "Real World Java"
edition: 1
# 多个作者
authors:
  - Victor Grazi
  - Jeanne Boyarsky
paperback: true
```

与 XML 和 JSON 不同，YAML 中的缩进非常重要。使用空格来显示缩进层级。每层缩进使用多少空格并不重要，只要你每一层始终使用相同数量的空格即可。不允许使用制表符，因为 IDE 处理它们的方式不同，并且会干扰空白计数。

顶部的三个连字符开始文档，是可选的。YAML 允许你在同一个文件中放置多个 YAML 文档，因此这三个连字符表示开始。

```yaml
---
title: null
edition: 0
authors:
  - "Victor & Jeanne"
paperback: false
```

同样地，写入特定字段使用`put`方法，正如我们之前在 XML 和 JSON 示例所示的那样。

```java
ObjectMapper mapper = new YAMLMapper();

ObjectNode root = mapper.createObjectNode();

root.put("edition", 1);

String yaml = mapper
   .writer()
   .writeValueAsString(root);

System.out.println(yaml);
```

输出只显示一个字段，因为只设置了那一个。

```yaml
---
edition: 1
```

## 使用 SnakeYAML 进行读写

SnakeYAML 是一个用于处理 YAML 的流行库。它对于简单操作易于使用，并为高级用户提供了强大的自定义功能。要在你的 Maven 或 Gradle 构建中使用它，请前往 Maven Central 的[`https://mvnrepository.com/artifact/org.yaml/snakeyaml`](https://mvnrepository.com/artifact/org.yaml/snakeyaml)适用于你构建工具的最新版本号。表 A.5 显示了本文编写时每个配置的样式。

| 工具 | 语法 |
| --- | --- |
| Maven | ```xml<br><dependency><br>    <groupId>org.yaml</groupId><br>    <artifactId>snakeyaml</artifactId><br>    <version>2.3</version><br></dependency><br>``` |
| Gradle (Groovy) | `implementation group: 'org.yaml', name: 'snakeyaml', version: '2.3'` |
| Gradle (Kotlin) | `implementation("org.yaml:snakeyaml:2.3")` |

**表 A.5**：指定 SnakeYAML 为依赖

获取适用于你构建工具的相应语法并将其包含在依赖中。

### 导航 YAML

首先，你将看到导航 YAML 的代码。

```java
File file = Path.of("src/main/resources/book.yaml").toFile();

Yaml yaml = new Yaml();

Map<String, Object> map = yaml.load(new FileReader(file));

System.out.println(map.get("title"));
```



`System.out.println(map.get("edition"));`

`System.out.println("Paperback? " + map.get("paperback"));`

`List<String> authors = (List<String>) map.get("authors");`

`for (String author : authors) {`

   `System.out.println(author);`

`}`

如你所见，构造了一个 `Yaml` 对象并用它加载数据。SnakeYAML 的优势是数据被加载到 `Map` 中，你可以打印出来查看查看读取的内容。缺点是，对于任何想要赋值给变量的数据（例如将 `authors` 为 `List<String>`），都必须进行类型转换。

```java
File file = Path.of("src/main/resources/book.yaml").toFile();

Constructor constructor = new Constructor(Book.class, new LoaderOptions());

Yaml yaml = new Yaml(constructor);

Book book = yaml.load(new FileReader(file));

System.out.println(book.getTitle());

System.out.println(book.getEdition());

System.out.println(book.isPaperback());

System.out.println(book.getAuthors());
```

要将数据加载到 Java 对象中，你需要创建一个 `Constructor` 类，然后创建一个 `Yaml` 对象。虽然这对于基础类有效，但如果你想更改来自 YAML 的名称或指定泛型类型，就会变得困难。

### 从 Map 写入 YAML

从 `Map` 创建并写入 YAML 是直观的。

```java
Map<String, String> map = new HashMap<>();

map.put("edition", "1");

DumperOptions options = new DumperOptions();

options.setDefaultFlowStyle(DumperOptions.FlowStyle.BLOCK);

Yaml yaml = new Yaml(options);

String output = yaml.dump(map);

System.out.println(output);
```

调用 `dump()` 会创建带有指定值的 YAML：

```yaml
edition: '1'
```

### 从对象写入 YAML

相比之下，从对象写入 YAML 文件更为复杂，因为默认设置可能并不直观。

```java
11: Book book = new Book();
12: book.setAuthors(List.of("Victor & Jeanne"));
13:
14: DumperOptions options = new DumperOptions();
15: options.setDefaultFlowStyle(DumperOptions.FlowStyle.BLOCK);
16:
17: Representer representer = new Representer(options);
18: representer.addClassTag(Book.class, Tag.MAP);
19:
20: Yaml yaml = new Yaml(representer, options);
21:
22: String output = yaml.dump(book);
23: System.out.println(output);
```



在第 11 行和第 12 行，我们创建一个 `Book` 实例。接下来，我们创建一个 `DumperOptions` 实例来配置 YAML。在这个示例中，流样式被设置为 `BLOCK`，这导致 `Victor & Jeanne` 在连字符后显示，因为它是一个 `List`。如果你不指定 `BLOCK`，YAML 会输出一种更简洁的备选样式。

第 17 和 18 行定义了 `Representer`。由于 SnakeYAML 会自动输出类名的标签，因此对 `Representer` 进行配置使其不包含该标签。

# A

- Akka, 391
- Alert Manager, 341–344, 349
- alerting, 326
- `ALL` 日志级别, 132, 140, 156
- `@AllArgsConstructor` 注解, 244–245
- “始终绿色,” 36
- 基于注解的切入点, 321–323
- 注解驱动的代码。参阅 Lombok
- Apache Commons, 309, 391
- Apache Commons Validator, 306, 309
- Apache HTTP Server, 385
- Apache Kafka, 391
- Apache PDF Box, 391
- Apache POI, 391
- Apache Tomcat, 385
- APIs, 文档化, 389–390
- `appendReplacement()` 方法, 296–297
- `appendTail()` 方法, 296–297
- 应用服务器, 385
    - 使用 Actuator 检查, 185–187
    - 优化, 372–375
    - 并行化参阅 Java concurrency
    - 安全性, 391–393
    - 使用 Spring security 加固, 187–192
- `@Around` 类型, 317–319
- Jenkins 中的产物, 116
- *计算机程序设计* (Knuth), 351
- `@Aspect` 注解, 314
- AspectJ, 323
    - 面向切面编程
    - 关于, 311
    - 创建示例, 312–314
    - 对切面的需求, 311–312
    - 切入点表达式语言, 315–323
- 断言消息, 228–229
- `assertAll()` 方法, 212
- `assertEquals()` 方法, 208
- 断言, 363
- AssertJ, 211–212, 234
- `assertNotEquals()` 方法, 208
- `assertThat()` 方法, 211–212
- `assertThrows()` 方法, 209
- assume 方法，用于验证条件, 209–210
- 非对称加密, 187
- `@Async` 注解, 278–280
- 原子操作操作, 编码, 254–255
- 属性 (XML), 396
- 认证, 188
- 授权, 188
- 代码的自动格式化, 32
- 自动化测试
    - 关于, 195–196
    - 断言逻辑, 207–209
    - 行为驱动开发, 231
    - 计算覆盖率, 225–226
    - 编码
        - 使用 JUnit 特性, 212–214
        - 使用 AssertJ, 211–212
    - 通用测试库, 211–214
    - 配置
        - Gradle 构建中的 JUnit, 200–202
        - Maven 构建中的 JUnit, 197–200
    - 使用 TestMe 创建测试模板, 230
    - 使用 DAMP 实现 DRY, 232–233
    - 黄金模式, 231–232
    - JUnit, 205–211
    - 测量测试覆盖率, 225–228
    - 模拟
        - 使用 EasyMock, 221–222
        - 使用 Mockito, 215–222
        - 对象, 215–225
        - 使用 Spring MockMvc, 222–225
    - 导航测试, 229–230
    - 使用 IntelliJ 优化测试, 228–230
    - 参数化测试, 210
    - 在构建中运行覆盖率, 227–228
    - 跳过测试, 207
    - 阶段 `test` 目录, 196–197
    - 测试流, 205–207
    - 测试运行, 229
    - 测试
        - 基础, 196–205
        - 合约, 231
        - 变异, 232
    - 使用测试驱动开发, 202–205
    - 使用 assume 逻辑验证条件, 209–210
    - 查看
        - 断言消息, 228–229
        - IDE 中的代码覆盖率, 226–227

## B

- Azul, 390
- 待压工作区, 76
- 回溯, 302
- 基础认证, 188
- BDD (行为驱动开发), 231
- Bean 周期，通过 Spring 作用域管理, 167
- Bean 验证，编写正则表达式, 307
- Beck, Kent (作者)
    - *重构：改进现有代码的设计,* 40
- `@BeforeAll` 方法, 205–207
- `@BeforeEach` 方法, 205–207
- 行为，通过标志控制, 298–299
- 行为驱动开发 (BDD), 231
- 基准测试
    - 关于, 352
    - 使用内置的 Java API, 353
    - 微基准测试, 354
    - `Function` 接口, 268
    - 大 O 符号, 373
    - 材料清单 (BOM), 102
    - 位运算符 (`|`), 299
    - Confluence 中的空白页面, 84
    - `BLOCKED`, 257
    - Confluence 中的博客文章, 84
- Blue Ocean 插件, 125
- 与看板配合, 76
- 材料清单 (BOM), 102
- `boolean tryLock()` 方法, 261–262
- Borland JBuilder, 12
- 瓶颈, 352
- 边界匹配, 287
- Git 中的分支, 43, 53
- 修复, 8
- 构建失败分析器插件, 125
- Jenkins 中的构建步骤, 116
- 构建工具, 88
- `builder()` 方法, 340
- 内置并发支持 Java 流, 260–261
- Burd, Barry (作者)
    - *Java 指南,* 1

## C

- 缓存, 352
- `Callable` 接口, 262–263
- 回调方法, 250
- 调用 `String` 方法, 291–294
- 调用验证, 219
- Jenkins 中的功能, 126
- 捕获组, 292–293
- 载体线程, 250, 271
- JUnit Pioneer 中的笛卡尔测试, 214
- `CASE-INSENSITIVE` 标志, 298
- 证书, 187
- 证书颁发机构, 187
- 认证, 重命名, 8
- 更改
    - 批量修改, 82–83
    - 原则, 8–9
    - 在 Jenkins 中读取, 126
- 字符类, 288–290
- 字符, 转义, 290–291
- 樱桃挑选 (cherry-picking), 60
- CI/CD. 参见 持续集成/持续交付 (CI/CD)
- Claim 插件, 125
- `clean` 阶段, 93
- 克隆, 通过 SSH, 47–48
- 云, 386–387, 394
- Clover, 233
- 代码
    - 注解驱动 (参见 Lombok)
    - 自动重格式化, 32–34
    - 计算覆盖率, 225–226
    - 比较, 34
    - 调试 (参见 调试代码)
    - 重复的, 26–30
    - 重构 (参见 重构代码)
    - 用于 Bean 校验的正则表达式, 307
    - 重新排序, 20–21
    - 在构建中运行覆盖率, 227–228
    - 测试中的代码, 204
    - 在 IDE 中查看覆盖率, 226–227
- 代码库, 导航, 19–20
- 编码
    - 原子操作, 254–255
    - 结合 Java 的函数式编程, 8, 4–5
    - Java 中的泛型, 5, 4
    - 结合 JUnit Pioneer 特性, 212–214
- Java 模块, 11, 5–6
    - 正则表达式
        - 用于 Apache Commons Validator, 306
        - 用于 JUnit, 306–307
        - 用于 Log4j, 307
        - 用于 Spring, 308
    - 结合正则表达式, 304–306
    - 标准, 159
    - 使用 Java 的文本块和记录, 17, 6–7
    - 使用 AssertJ, 211–212
- 协作
    - 关于, 41–42
    - 结合 Confluence, 83–86
    - 结合 Git, 42–72
    - 结合 Jira, 72–83
- 集合, 并, 259–260
- 列模式, 34–35
- 在 Jira 中添加列, 78–79
- 逗号分隔值 (CSV) 文件, 148
- 提交哈希, 43
- 提交窗口, 63
- 提交, 43
- 常见漏洞与暴露 (CVE), 392
- `@CommonsLog` 注解, 246
- 比较操作符, 81
- `compile` 阶段, 92
- `compileOnly`, 110
- 从 javadoc 编译, 239
- 创建响应式代码 `CompletableFuture`, 265–271
- `CompletionService`, 275
- `CompletionStage` 接口, 268–269
- 组件扫描, 169–170
- 具体类, 模拟, 220–221
- 并发集合, 259–260
- Java 并发编程 (Lea), 281
- `newCondition()` 方法, 261–262
- `CONFIG` 级别, 132
- 配置
    - Jenkins 中的凭据, 120–121
    - 结合 Spring profiles 的环境属性, 171–173
    - JUnit
        - 在 Gradle 构建中, 200–202
        - 在 Maven 构建中, 197–200
    - Maven 设置, 106
    - 内存设置, 357–358
    - 传递
        - 在 Java Logging 中, 133–134
        - 在 Log4j 中, 141
    - 插件, 94–97
    - 爬取, 328–330
    - Spring 框架, 164–170
    - `then()` 方法, 218–219
    - `when()` 方法, 218–219
- Confluence, 83–86
- 将 Jira 连接到 Git, 83
- `Console` 渲染器, 145
- 控制台日志器, 142
- `ConsoleAppender` 类, 157
- 构造函数注入, 179
- 构造函数
    - 生成, 244–245
    - 多个, 217
- `Consumer` 接口, 266
- 容器, 385–386, 394
- 持续交付：通过构建、测试和部署自动化实现可靠发布 (Humble and Farley), 128
- 持续集成/持续交付 (CI/CD)
    - 关于, 87–88
    - 构建
        - 结合 Gradle, 106–112
        - 结合 Maven, 88–106
    - 查找依赖, 112–114
    - 与 Jenkins 集成, 120–121
    - 实践, 126
    - 使用 Sonar 扫描, 127
    - 合约, 测试, 231
    - 复制和粘贴, 键盘快捷键, 20
    - `CountLatch` API, 261–262
    - 创建、读取、更新 (CRUD), 383
    - CSV (逗号分隔值) 文件, 148
    - 自定义认证, 188
    - `@CustomLog` 注解, 246
    - 结合 Spring properties 的自定义, 171–173
    - 常见漏洞与暴露 (CVE), 392
    - `CyclicBarrier` API, 262

## D

- 守护线程, 251
- DAMP (描述性良好的短语), 232–233
- `Dashboard` 类, 220–221
- Dashboard 插件, 125, 126
- 仪表盘化
    - 关于, 326
    - 结合 Grafana, 344–347
    - 在 Jenkins 中, 116
- DAST (动态应用安全测试), 393
- 数据库, 类型的比较, 382–384
- `@Data` 注解, 240–241
- `DEBUG` 级别, 140, 150, 156
- 调试代码
    - 关于, 22
    - 程序, 22–23
    - 正则表达式, 303
    - 远程, 25
    - 加速, 24
    - 结合 Hot Swap, 26
- 延迟执行, 4–5
- 依赖
    - 查找, 112–114
    - Gradle, 109–110
- Maven, 90–92
- 用于 Micrometer 和 Actuator, 337
- 依赖图, 104
- 依赖注入 (DI), 164
- `deploy` 阶段, 92
- 部署 Java, 384–387
- 废弃, 7–8
- 描述性且意义的短语 (DAMP), 232–233
- 反序列化, 395
- 性能设计, 159
- develop 分支, 71
- DI (依赖注入), 164
- diff-viewer 窗口, 64–69
- 摘要身份认证, 188
- 在 JUnit Pioneer 中禁用, 213
- 分布式追踪, 348
- Docker, 128, 328, 350
- 文档类型定义 (DTD), 397
- Confluence 中的文档页面, 84
- 文档 API, 389–390
- 使用 DOM 读写 XML, 401–402
- 领域特定语言 (DSL), 108
- 不要重复自己 (DRY), 232–233
- 点 (.), 136, 290
- Driessen, Vincent, 86
- DRY (不要重复自己), 232–233
- DSL (领域特定语言), 108
- DTD (文档类型定义), 397
- 哑对象, 215
- 避免重复代码, 26–30
- 动态应用安全测试 (DAST), 393

## E

- 使用 EasyMock 进行 mock, 221–222
- 倾听者, 187
- Eclipse
    - 关于, 12–13, 36–37
    - IDE 集成, 225
    - 在 Eclipse 中安装 Lombok, 237
    - 使用, 104
    - 网站, 40
- Eclipse Collections, 91, 391
- 生态系统
    - 关于, 377–378
    - 构建 REST APIs, 387–390
    - 选择虚拟机, 390
    - 比较
        - 数据库类型, 382–384
        - JVM 语言, 379–381
    - 部署 Java, 384–387
    - 集成, 384
    - Jakarta EE, 381–382
    - 库, 390–391
    - 监控变化, 393
    - 应用安全, 391–393
    - 编写 Javadoc, 378–379
    - 编辑器利用, 32–35
    - Elastic Search, 350
    - XML 元素, 396
    - `@EnableAsync` 注解, 278–280
    - 使用 `@EnableScheduling`, 280
    - 加密, 187
    - `endElement()` 方法, 403
    - 使用 Jira 进行企业协作, 72–83
    - 环境
        - 为 Lombok 准备, 236–239
        - 设置变量, 177
    - 喜欢 epics, 75
    - `eq()` 方法, 219
    - `equals()` 方法, 208
    - `@EqualsAndHashCode` 注解, 244
    - Spring 框架中的错误处理, 183–185
    - `ERROR` 日志级别, 140, 150, 156
    - 转义字符, 290–291
    - ETL (提取、转换和加载), 347
    - 评估频率, 343
    - 断言异常, 208–209
    - 与 `ExecutorService` 协调, 263–265
    - 导出器安装, 327
    - 可扩展标记语言 (XML)
        - 关于, 135, 148, 396
        - 比较库, 403
        - 格式, 396–397
        - 读取读取
            - 使用 DOM, 401–402
            - 使用 Jackson, 397–399
            - 使用 SAX, 402–403
        - 使用配置文件, 165–167
        - 网站, 412–413
        - 写入
            - 使用 DOM, 401–402
            - 使用 Jackson, 399–401
    - 可扩展样式表语言转换 (XSLT), 397
- 提取、转换和加载 (ETL), 347
- 极端编程, 72

## F

- 伪对象, 215
- Farley, David (作者)
    - *Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation,* 128
- `FATAL` 日志级别, 140
- 特性分支, 70
- Git 中的获取, 51
- `fetch()` 方法, 210
- Field, Roy, 193
- `File` 附加器, 145
- `FileAppender` 类, 157
- 过滤器, 80
- `FINE` 日志级别, 132
- `FIN` 日志级别, 140
- `FINEST` 日志级别, 132
- 固定数量线程池, 263
- 标志控制, 298
- Jira 文件夹, 16
- 格式
    - 用于 JSON, 404
    - 用于 XML, 396
    - 用于 YAML, 408
- 格式化值
    - 在 Logging 中, 132
    - 在 Log4j 中, 140
    - 在 SL4J 中, 151
- 表单认证, 188
- 日志转发, 160
- Fowler, Martin
    - *Refactoring: Improving the Design of Existing Code,* 40
- 使用正则表达式的框架, 306–308
- 自由风格任务
    - 在 Gradle 中, 122
    - 在 Jenkins 中, 16, 117
    - 在 Maven 中, 119–121
- `Function` 接口, 267–268
- `CompletableFuture` 使用的函数式接口, 265–268
- 使用 Java 进行函数式编程, 8, 4–5
- `Future` 接口, 262–263

## G

- G1GC (垃圾垃圾回收), 360
- 垃圾回收, 259, 358–360
- Garbage First Collection (G1GC), 360
- 泛型, Java 中的编码, 5, 4
- `getArgs()` API, 314
- `getCarriers()` 方法, 275
- `getFormatted()` 方法, 226
- `getKind()` API, 314
- `getSignature()` API, 314
- `getStaticPart()` API, 314
- `getTarget()` API, 314
- `@Getter` 方法, 自动生成, 241–242
- `getThis()` API, 314
- `@Flogger` 注解, 246

## Git

- 关于, 42
- 分支, 43, 53–54
- 择挑选 (cherry-picking), 60
- 将 Jira 连接到, 83
- 使用 Markdown 语言创建 README 文件, 69–70
- 区分提交, 43
- 显示 `git status`, 43
- 获取 (fetching), 51–52
- 安装, 45
- 核心概念, 42–43
- 合并, 44, 51–52
- 使用 IDE 支持进行优化, 61–69
- 拉取 (pulling), 51–52
- 读取日志, 44
- 变基 (rebasing), 57–59
- 重置 (resetting), 60–61
- 解决合并冲突, 54–55
- 撤回 (reverting), 60–61
- 暂存更改 (staging changes), 44–45
- 打标签 (tagging), 43
- 使用 `git log` 命令, 56–57
- 使用 Gitflow 进行协作, 70–72
- 使用拉取请求/合并请求, 55
- 示例工作流, 45–51
- `git add` 命令, 44–45
- `git cherry-pick` 命令, 60
- `git fetch` 命令, 51–52
- `git log` 命令, 44, 56–57
- `git merge` 命令, 51–52
- `git pull` 命令, 52
- `git reset` 命令, 60–61
- `git revert` 命令, 60–61
- `git status` 命令, 43
- `GitDemo` 类, 53–54
- Gitflow, 用于协作, 70–72
- GitHub, 22
- Goetz, Brian (作者)
    - *Java Concurrency in Practice,* 281
- 黄金主模式 (golden master pattern), 231–232
- Google Guava 集合, 391
- Gosling, James (Java 创造者), 2
- Goyvaerts, Jan (作者)
    - *Regular Expressions Cookbook,* 309
- Graal VM, 390
- Gradle
    - 关于, 106
    - 使用构建基础项目, 107–109
    - 在其中配置 JUnit, 200–202
    - 依赖, 109–10
    - 在其中包含 Lombok, 238
    - 在集成环境 (IDE) 中, 111–112
    - 本地仓库, 109–10
    - 设置系统属性, 150
    - 指定
        - 将 AssertJ 作为依赖, 211
        - 将 EasyMock 作为依赖, 221
        - 将 Gson 作为依赖, 407
        - 将 Jackson 作为依赖, 398, 405, 409
        - 将 JUnit Pioneer 作为依赖, 212
        - 将 Log4j 作为依赖, 138, 144
        - 将 Logback 作为依赖, 155
        - 将 Lombok 作为依赖, 238
        - 将 Mockito 作为依赖, 216
        - 将 SLF4J 作为依赖, 149, 152
        - 将 SnakeYAML 作为依赖, 411
        - 将 Spring Boot Starter 作为依赖, 223
        - 变量, 110
    - 使用 Java 插件, 110–111
    - 网站, 128
    - Grafana, 344–350
    - Groovy, 108, 138, 144, 149, 150, 152, 155, 211, 212, 216, 221, 223, 238, 380, 398, 405, 407, 409, 411
    - `group()` 方法, 295
    - 使用 Gson 写入 JSON, 407–408

## H

- *Java First, 3rd Edition,* 1
- 堆 (heap), 259
- 直方图 (histograms), 339–341
- 水平扩展性 (horizontal scalability), 352
- 热点 (hot spot), 352
- 使用 Hot Swap, 26
- `HTMLL` 类, 158
- `HTTP` (协议), 88
- `HTTPS`, 88
- Humble, Jez (作者)
    - *Continuous Delivery: Reliable Software through Build, Test, and,* 128

## I

- IAST (交互式应用测试), 393
- 等等 (idempotent requests), 81
- `import`, 110
- `imports`, 92
- `INFO` 级别, 132, 140, 150, 156
- `input/output`, 159
- `install` 阶段, 92
- 安装
    - 导出器, 327
    - Git, 45
    - Jenkins, 114–116
    - 集成环境 (IDE)
        - 关于, 11
        - 比较, 39–40
        - 创建运行配置, 16–18
        - 调试代码, 22–26
        - Eclipse, 36–37
        - 扩展编辑器, 32–35
        - 扩展, 35–36
        - 在 Gradle 中, 111–112
        - 历史, 12–13
        - JSON 和, 404
        - 快捷键, 18–22
        - 在 Maven 中, 103–106
        - 使用进行优化, 61–69
        - 重构代码, 26–32
        - 开始新项目, 13–16
        - 查看代码覆盖率查看, 226–227
        - Visual Studio (VS) Code, 37–39
        - XML 和, 396
        - YAML 和, 409
    - 实例向量 (instance vector), 332
- 集成, 114–126, 384
- 集成测试, 197, 198
- `integration-test` 阶段, 92
- IntelliJ
    - 关于, 13, 14, 36
    - IDE 集成, 225
    - 在...中安装 Lombok, 236–237
    - 使用...优化测试, 228–230
    - 分析器, 371
    - Spring-178 Initializer, 173
    - 使用, 103–104
- IntelliJ IDEA, 40
- 交互式应用测试 (IAST), 393
- 线程间通信, 276–278
- 引入正则表达式, 309
- 控制反转 (IoC), 164
- I/O (输入/输出), 159
- IoC (控制反转), 164
- 在 Jira 中的问题, 74–75, 80
- iText, 391

## J

- Jackson
    - 读取
        - 使用...读取 JSON, 405–406
        - 使用...读取 XML, 397–399
        - 使用...读取 YAML, 409–410
    - 写入
        - 使用...写入 JSON, 406–407
        - 使用...写入 XML, 399–401
        - 使用...写入 YAML, 410
- JaCoCo (Java 代码覆盖率), 225, 233
- Jakarta EE, 8, 381–382, 394
- JAR (Java 归档), 5
- Java
    - 关于, 1
    - APIs
        - 使用 Java 内置进行基准测试, 353–354
        - 在...中使用正则表达式, 291–299
    - 流中的内置并发支持, 260–261
    - 并发
        - 关于, 249–252
        - `@Async` 注解, 278–280
        - 使用 `CompletableFuture` 构建响应式代码, 265–271
        - `Callable` 接口, 262–263
        - 编写原子操作, 254–255
        - Spring 框架中的并发支持, 278–281
        - 并发集合, 259–260
        - 使用 `Phaser` 控制线程访问, 262
        - 与 `ExecutorService` 协调, 263–265
        - `@EnableAsync` 注解, 278–280
        - `@nableScheduling` 注解, 280
        - `Future` 接口, 262
        - 堆, 259
        - 线程间通信, 276–278
        - 使用 `ReentrantLock` 加锁, 261–262
        - 元空间 (metaspace), 259
        - `Runnable` 接口, 262–263
        - `@Scheduled` 注解, 280
        - 栈 (stack), 259
        - 同步化, 257–259
        - 线程竞争, 252
        - `ThreadPoolExecutor`, 280
        - `@Transactional` 注解, 281
        - 状态转换, 256–257
        - 流中的内置并发支持, 260–261
        - 使用并发降低复杂性, 261–278
        - 使用 `volatile` 关键字, 255–256
        - 虚拟线程, 271–275
    - 部署, 384–387
    - 管理, 2
    - 版本, 4–7
- Java 归档 (JAR), 5
- Java 代码覆盖率 (JaCoCo), 225, 233
- Java 并发实践 (Goetz), 281
- Java 并发, 281
- Java 配置类, 167–169
- Java 数据库连接 (JDBC), 360
- Java 增强提案 (JEPs), 9
- Java 企业版 (JEE), 307
- Java 飞行记录器 (JFR), 366–368
- Java 入门 (Burd), 1
- Java 消息服务 (JMS), 384
- Java 微基准框架 (JMH), 354
- Java 任务控制, 368–369, 376
- Java 性能, 375
- Java 平台模块系统 (JPMS), 5
- Java 插件, 110–111
- Java 规范请求 (JSRs), 9
- Java 工具日志 (Java Util Logging)
    - 关于, 130–131
    - 与其他日志框架对比, 160
    - 日志级别对比, 131–132
    - 值格式化, 132–133
    - 日志记录继承, 136–137
    - 懒性日志, 135
    - 传递基础配置, 133–134
    - 设置日志目标, 134–135
    - 网站, 161
- Java VisualVM, 376
- Javadoc
    - 关于, 393
    - 从...编译, 239
    - 插件, 125
- JavaScript 对象表示 (JSON)
    - 关于, 148
    - 库对比, 408
    - ...的格式, 404
        - 使用...读取 JSON, 405–406
        - 使用...读取 XML, 397–399
        - 使用...读取 YAML, 409–410
    - 写入
        - 使用...写入 JSON, 406–407
        - 使用...写入 XML, 399–401
        - 使用...写入 YAML, 410
    - 网站, 413
- Java 模块系统 (Par), 9
- JConsole, 监控, 369–370
- JDK 工具
    - 关于, 365
    - Java 飞行记录器 (JFR), 366–368
    - 使用 JConsole 报告, 370
    - 使用 `jstat` 命令, 371
    - 使用 VisualVM, 370
    - 在 Java Mission Control 中可视化, 368
- JEE (Java 企业版), 307
- Jenkins
    - 关于, 114
    - 功能, 126
    - 在...中配置凭据, 120–121
    - 创建任务, 116–125
    - 安装, 114–116
    - 术语, 116
    - 网站, 128
- JEPs (Java 增强提案), 9
- JFR (Java 飞行记录器), 366–368
- Jira
    - 关于, 72
    - 添加
        - 列, 78–79
        - 用户, 78
    - 连接到 Git, 83
    - 创建
        - 问题, 74–75
        - 项目, 73–74
- 冲刺（sprints），76–78
- 入门，72–73
- 链接到史诗（epics），75
- 批量修改, 82–83
- 插件, 125
- 使用 Jira 查询语言 (JQL) 查询, 80–82
- 使用过滤器, 80
- 查看问题, 80
- 使用看板（boards），76
- Jira 查询语言 (JQL), 查询, 80–82
- JIT（即时编译）, 352
- JMeter, 360–365, 375, 376
- JMH (Java Microbenchmark Harness), 354
- JMS (Java Message Service), 384
- `@JBossLog` 注解, 246
- Jenkins 中的作业（jobs）
    - 在 Jenkins 中创建, 116–126
- JPMS (Java 平台模块系统 ), 5
- JQL (Jira 查询语言), 查询, 80–82
- JSON. 参见 JavaScript 对象表示 (JSON)
- JSON Web Token (JWT) 认证, 188
- JSRs (Java 规范请求), 9
- `jstat` 命令的报告, 371–372
- JUnit
    - 断言逻辑, 207–209
    - 编码
        - 使用 Pioneer 特性, 212–214
        - 正则表达式, 306–307
    - 配置
        - 在 Gradle 构建中, 200–202
        - 在 Maven 构建中, 197–200
    - 测试参数化, 210
    - 跳过测试, 207
    - 测试流, 205–207
    - 使用 assume 方法验证条件, 209–210
    - 网站, 233
- JUnit Pioneer, 233
- 即时编译 (JIT), 352
- JVM 语言
    - 比较, 379–381
    - 网站, 393–394
- JVM 设置, 357–360
- JWT (JSON Web Token) 认证, 188

## K

- Kanban (看板管理), 72
- 快捷键
    - 关于, 18–19, 21–22
    - 复制和粘贴, 20
    - 代码库导航, 19–20
    - 代码重排, 20–21
- Kibana, 348, 350
- Kira, 72
- Knuth, Donald
    - 《编程之艺术》 351
- Kotlin, 108, 138, 144, 149, 150, 152, 155, 211, 212, 216, 221, 223, 238, 379–380, 398, 405, 407, 409, 411
- Kubernetes, 386

## L

- 日志语言选择, 159
- 延迟, 352
- 懒性日志 (lazy logging)
    - 在 Java Logging 中, 135
    - 在 Log4j 中, 148
    - 在 SLF4J 中, 151
- LDAP (轻量级目录访问协议) 认证, 188
- Lea, Doug
    - Java 并发编程, 281
- Levithan, Steven
    - 《正则表达式入门》 309
- 库, 211–214, 390–391, 394
- 生命周期阶段区分, 92–93
- 链接到 Jira 中的史诗, 75
- Linux Node Exporter, 349
- 监听器, 363
- `listOf()` 函数, 379
- 负载测试运行, 363–364
- `localName` 属性, 399
- 日志伪造 (log forging), 159
- 日志注入 (log injection), 159
- 日志滚动, 26
- 防止日志篡改, 159
- Log4j
    - 关于, 138–139
    - 日志输出格式, 148
    - 正则表达式使用, 307
    - 常见漏洞与披露 (CVE), 392
        - 配置格式, 142
        - 日志级别, 139
        - 其他日志框架, 160
    - 格式化, 140
    - 懒性日志, 148
    - 配置, 141
    - 目标设置, 145
- Logback
    - 关于, 155–156
    - 日志输出格式, 158–159
        - 日志级别, 155
        - 其他日志框架, 160
    - 配置, 156–157
    - 目标设置, 157–158
- Logstash, 350
- 日志框架
    - 关于, 129–130
    - 聚合日志, 160
    - 日志语言选择, 159
    - 与 `println` 方法比较, 130, 160
    - 性能设计, 159
    - 确定编码标准, 159
    - 转发日志, 160
    - 省略日志, 149
    - 防止日志篡改, 159
    - 使用 Java Logging, 130–137
    - 使用 Log4j, 138–148
    - 使用 Logback, 155–159
    - 使用 SLF4J, 139–155
    - 与其他框架一起使用 SLF4J, 152–155
- 日志到代码库, 247–246
- Lombok
    - 关于, 233–234
    - 自动生成 `@Getter` 和 `@Setter` 方法, 241–242
    - 从 `javac` 编译, 239
    - 转换为, 240–246
    - 从代码库移除 Lombok, 247
    - 使用 `@AllArgsConstructor`、`@RequiredArgsConstructor` 和 `@NoArgsConstructor` 注解生成构造函数, 244–245
    - 实现, 239–240
    - 在 Maven 或 Gradle 中包含, 238

## 安装

- 安装
    - 在 VS Code 中, 237
    - 在 Eclipse 中, 237
    - 在 IntelliJ 中, 236–237
- 准备环境, 236–239
- 使用 `@Data` 注解, 240–241
- 使用 `@EqualsAndHashCode`, 244
- 使用 `@ToString`, 243
- 使用 `@Log` 将日志器织入代码库, 245–246
- 网站, 243, 247

## 长期支持 (LTS), 3, 114

## M

- 宏 (Confluence), 86
- Markdown 语言, 创建 README 文件使用, 69–70
- 匹配, 查找, 291–292, 295–296
- `matches()` 方法, 291–292, 295–296
- Maven
    - 关于, 88
    - 依赖清单 (BOM), 102–103
    - 构建基础项目使用, 89–90
    - 常用插件, 94–97
    - 配置
        - 在 JUnit 中, 197–200
        - 设置, 106
    - 创建流水线, 122–124
    - 依赖, 90–92
    - 区分生命周期阶段, 92–93
    - 特性, 102–103
    - 在自由式任务中, 119–121
    - 在项目中包含 Lombok, 238
    - 在集成开发环境 (IDE) 中, 103–106
    - 父级 POM, 98–102
    - POM, 93–94
    - 发布项目, 103
    - 仓库, 90–92
    - 设置系统属性, 102, 150
    - 指定
        - 将 AssertJ 作为依赖, 211
        - 将 EasyMock 作为依赖, 221
        - 将 Gson 作为依赖, 407
        - 将 Jackson 作为依赖, 398, 405, 409
        - 将 JUnit Pioneer 作为依赖, 212
        - 将 Log4j 作为依赖, 138, 144
        - 将 Logback 作为依赖, 155
        - 将 Lombok 作为依赖, 238
        - 将 Mockito 作为依赖, 215
        - 将 SLF4J 作为依赖, 149, 152
        - 将 SnakeYAML 作为依赖, 411
        - 将 Spring Boot Starter 作为依赖, 223
    - 网站, 128
- 会议笔记, 在 Confluence 中, 84
- 成员, 重命名, 31
- 内存泄漏, 352
- 内存设置, 357
- 在 Git 中合并, 44, 51, 54
- 元空间, 259
- 指标, 326, 337
- 微基准, 354–357
- Micrometer, 336, 350
- 微服务, 388
- Microsoft Visual++, 12
- Mock 对象
    - 关于, 215
    - 模拟
        - 使用 EasyMock, 221–222
        - 使用 Mockito, 215–221
        - 使用 Spring MockMvc, 222–225
    - 使用 Mockito 模拟, 215–221
    - `mockStatic()` 方法, 221
- 模块
    - 添加到现有项目, 16
    - 从 Java 编码, 11, 5–6
    - 使用 JConsole 监控, 369–370
- `MULTILINE` 标志, 298
- 多行字符串. 参见文本块
- 多模块项目 (POM), 100–102
- 变异测试, 232

## N

- 日志器名称, 131
- 负向前瞻/后视, 300
- 网络延迟, 352
- `NEW`, 256
- 节点导出器, 327
- no-ff 合并, 52
- `@NoArgsConstructor` 注解, 244–245
- NoSQL 数据库, 384
- 在 Jenkins 中通知用户, 126

## O

- OAuth2, 188
- 可观测性
    - 关于, 325–326
    - 添加 Alert Manager, 341–344
    - 配置抓取, 328–330
    - 创建自定义指标, 337–341
    - 使用 Grafana 仪表板, 344–347
    - 从 Prometheus 开始, 326–341
    - 安装
        - 导出器, 327
        - Prometheus, 328–330
    - 日志, 347–349
    - 启动应用, 326
    - 追踪, 349
    - 使用 HTTP API, 336–337
- `OFF` 级别, 132, 140, 156
- 偏移量, 333
- Open CSV, 309
- Open JDK, 390
- Open Application Security Project (OWASP) Top 10, 391
- OpenID Connect, 188
- OpenTelemetry, 349, 350
- 操作符, 81, 82
- 选项, 290

## P

- `package` 阶段, 92
- Pact, 233
- 并行垃圾回收, 359–360
- 并行应用. 参见 Java 并发
- `parallelStream()` 方法, 260–261
- 参数, 32, 219
- 父级 POM, 98–100
- Parlog, Nicolai
    - *Java 模块系统,* 9
- `parse()` 方法, 403
- 传递
    - 基础配置
        - 在 Log4j 中, 141
        - 在 Logback 中, 156–157
        - 在 SLF4J 中, 152
    - Java 志日志配置, 133–134
- 补丁, 66
- 模式文件, 148
- 模式匹配, 使用正则表达式, 283–308
- `PatternLayout` 类, 158
- 模式, 工作, 294–298
- 性能
    - 关于, 351–352
    - 微基准测试, 352–357
    - 概念和术语, 352
    - 考虑因素, 375
- 定义, 352
- 设计, 159
- JVM 设置, 357–360
- 优化应用程序, 372–375
- 使用 JMeter 测试, 360–365
- 使用 JDK 工具, 365–372
- `Phaser`，用其控制线程访问, 262
- Jenkins 中的流水线任务, 116
- 流水线
    - Gradle, 124–125
    - Maven, 122–124
- 平台线程, 250
- 插件
    - 配置, 94–97
    - Java, 110–111
    - Jenkins, 125
- 加号 (`+`), 291
- 切入点表达式语言
    - `..` 通配符, 316
    - `*` 通配符, 315–316
    - 关于, 315
    - 基于注解的切入点, 321–323
    - 合并切入点, 320–321
    - 使用 `@After`, 317
    - 使用 `@AfterReturning`, 316–317
    - 使用 `@AfterThrowing`, 317
    - 使用 `@Around`, 317–319
    - 使用 `@Pointcut`, 319–320
- `@Pointcut` 类型, 319–320
- 切入点
    - 基于注解的, 321–323
    - 合并, 320–321
    - 定义, 312
- POM
    - 多模块项目, 100–102
    - 父项目, 98–102
    - 属性, 93
    - 指定项目信息, 93–94
    - 版本号, 94
- 正向先行/后后断言, 300
- 主键, 382
- 变更原则, 8–9
- `printf()` 方法, 141
- `println()` 方法, 130
- 私有方法的测试, 218
- 分析器, 352
- 程序的调试, 22–23
- 项目
    - 添加
        - 向现有项目添加模块, 16
        - 添加到版本控制中, 15
    - 创建
        - 从现有源码创建, 14
        - 在 Jira 中创建, 73–74
        - 从零创建, 13–14
        - 从版本控制创建, 15
        - 使用 Gradle, 107–109
        - 使用 Maven, 89–90
        - 在 Maven 中发布, 103
        - 指定信息, 93–94
        - 开始新项目, 13–16
        - 工作流, 76
    - Prometheus, 327–328, 349
    - Prometheus HTTP APIs, 336–337
    - Prometheus 查询语言 (`PromQL`), 330–336
    - 属性
        - 使用框架自定义, 170–173
        - 注入, 170–171
        - POM, 93
        - 原型作用域, 167
    - `provided`, 92
    - 作用域, 238
    - 在 Git 中拉取, 51
    - 拉取/合并请求, 55
    - 推送, 326

## Q

- 量词
    - 区分, 301–303
    - 指定常用的, 286–287
    - 查询, 332
    - 使用 Jira 语言查询 (`JQL`), 80–82

## R

- 竞态条件, 253
- 范围向量, 333
- RASP (运行时应用防护), 393
- 读取
    - Jenkins 中的更改, 126
    - git 日志, 44
    - JSON
        - 使用 Gson, 407–408
        - 使用 Jackson, 405–406
    - XML
        - 使用 DOM, 401–402
        - 使用 Jackson, 397–399
        - 使用 SAX, 402–403
    - YAML
        - 使用 Jackson, 409–410
        - 使用 SnakeYAML, 410–412
- 使用 Markdown 语言创建 README 文件, 69–70
- `readTree()` 方法, 399
- `readValue()` 方法, 399
- `ReadWriteLock`, 275
- 在 Git 中变基, 57–59
- 使用 Java 编写 records, 17, 6–7
- 红绿重构, 202
- `ReentrantLock`, 261–262
- 重构代码
    - 关于, 26
    - 避免重复代码, 26–30
    - 更改签名, 32
    - 联联, 31
    - 重命名成员, 31
- *Refactoring: Improving the Design of Existing Code* (Beck), 40
- 代码的格式化, 32
- 回归测试, 195
- 正则表达式
    - 关于, 283–285
    - 调用 `String` 方法, 291–294
    - 选择选项, 290
    - 编码
        - 使用框架, 304–306
        - 使用 Apache, 306–307
        - 使用 bean, 307–308
        - 使用 JUnit, 306–307
        - 使用 Log4j, 307–308
        - 使用 Spring, 308
    - 使用标志控制行为, 298–299
    - 调试, 303
    - 区分量词, 301–303
    - 转义字符, 290–291
    - 识别常见错误, 304–306
    - 匹配边界, 287–288
    - 邻近文本, 300–301
    - 模式匹配, 283–308
    - 指定常用的量词, 286–287
    - 语法, 290–291, 300–303
    - 使用
        - 使用框架和工具, 306–308
        - 使用 Java APIs, 291–299
    - 使用
        - 常用字符类, 288–290
        - 模式, 294–298
- *Regular Expressions Cookbook* (Goyvaerts and Levithan), 309
- 关系型数据库, 382–383
- 发布分支, 7–10
- 远程调试, 25
- 重命名, 识别, 8
- 重命名
    - 认证, 8
    - 成员, 31
- 重排序
    - 代码, 20–21
    - 操作, 255
- `replace()` 方法, 293
- `replaceAll()` 方法, 296–297
- `replaceFirst()` 方法, 292–293, 296–297
- 仓库
    - 在 Git 中, 42
- `Gradle`, 109–110
- `Maven`, 90–92
- 表现层状态转移 (REST)。查看 REST APIs
- 请求范围 (request scope), 167
- `@RequestParam`, 180
- `@RequiredArgsConstructor` 注解, 244–245
- Git 中的重置 (resetting), 60–61
- 响应时间, 352
- 创建 REST APIs, 387–390
- RESTful Web 服务, 193
- 退休 (retirement), 7–8
- 在 JUnit Pioneer 中重试测试, 213
- Git 中的回滚 (reverting), 60–61
- 基于角色的授权策略插件, 125
- `RollingFile` 记录器, 145
- `RollingFileAppender` 类, 157
- `RollingRandomAccessFile` 记录器, 145
- 创建运行配置, 16–18
- `RUNNABLE`, 256
- `Runnable` 接口, 262–263, 265
- `runtime`, 92
- 运行时应用安全防护 (RASP), 393
- `runtimeOnly`, 110
- RxJava, 391

## S

- SACMJD (太阳认证 Java 开发者), 8
- SAST (静态应用安全测试), 393
- Scala, 381
- 使用 Sonar 扫描, 127
- `schedule()` 方法, 264–265
- `scheduleAtFixedRate()` 方法, 264–265
- 使用 `@Scheduled` 调度, 280
- 调度
    - 使用 `ExecutorService`, 264–265
    - 使用 `@Scheduled`/`@EnableScheduling`, 280
- SCJA (太阳认证 Java 关联工程师), 8
- SCJP (太阳认证 Java 专业业师), 8
- `scope` 标签, 91–92
- 使用 Spring 管理 Bean 的生命周期, 167
- 配置爬虫 (scrapes), 328–330
- 爬取 (scraping), 326
- Scrum, 72
- 通过 Secure Shell (SSH) 进行克隆, 47–48
- 安全套接层 (SSL), 187
- 应用安全, 187–192, 391–393
- 安全 (security), 394
- 语义版本化, 94
- `Semaphore`, 275
- 序列垃圾收集, 359
- 服务帐户, 120
- servlet 过滤器, 188
- 会话范围 (session scope), 167
- 基于会话的认证, 189
- 自动生成 `@Setter` 方法, 241–242
- `setTie()` 方法, 226
- 7-Zip, 350
- `SEVERE` 日志级别, 132
- 签名 (signatures), 32
- 使用 Simple API for XML (SAX), 402–403
- Simple Logging Facade for Java (SLF4J)
    - 概述, 149
    - 与日志框架的对比, 160
    - 日志级别的对比, 150
    - 格式化值, 151
    - 懒性日志, 151
    - 忽略日志框架, 149–150
    - 基础配置, 152
    - 指定, 150
    - 使用其他日志框架, 152–155
    - 网站, 161
- 单例范围 (singleton scope), 167
- Skip List 算法, 281
- 跳过测试, 207
- `@Slf4j` 注解, 246
- 使用 SnakeYAML 读写, 410–412
- 使用 Sonar 扫描, 127
- SonarQube, 127, 128, 374
- 特殊操作符, 82
- `split()` 方法, 293–294
- 拆分 (splitting), 293–294, 298
- Spring AOP, 323
- Spring Boot 在应用中的追踪, 349
- Spring Boot Actuator, 336–337
- Spring framework
    - 概述, 163–164
    - 用于编写的正则表达式, 308
    - 并发支持, 278–281
    - 配置, 164–170
    - 使用属性自定义, 170–173
    - 错误处理, 183–185
    - 使用 Spring Boot 改进开发, 173–178
    - 使用 Spring initializer 初始化 Spring Boot 项目, 173–174
    - 使用 Actuator 检查应用, 185–187
    - 项目, 192
    - 使用 Spring security 安全应用, 187–192
    - Spring MVC, 178–183, 222–222
    - 使用组件扫描, 169–170
    - 使用 IntelliJ Initializer, 173–174
    - 使用 Java 类, 167–169
    - 使用 XML 文件, 165–167
    - 网站, 193
- 在 JUnit Pioneer 中，214
- Maven 中的设置，102
- `System.currentTimeInMillis()`, 354
- `System.nanoTime()`, 354

## T

- Git 中的标签（tag），43
- TDD (测试驱动开发)，196
- 模板 URL，186
- `TERMINATED`, 257
- Jenkins 术语，116
- `test`, 92
- 暂存的 `test` 目录，196
- 测试双胞（test double），215
- `test` 阶段，92
- 测试驱动开发 (TDD)，196, 202–205
- `testImplementation`, 110
- 测试
    - 使用 JMeter，360–365
    - 用于工具（参见 自动化测试工具）
- 使用 TestMe 创建测试模板代码，230
- TestNG，195
- Java 文本块，从 Java 编码 17, 6–7
- 配置 `then()` 方法，218–219
- 使用 `Phaser` 控制线程访问，262
- 线程竞争，252–254
- 线程组，361, 363
- 线程优先级，251
- 线程状态，256–257
- 使用 `ThreadPoolTaskExecutor` 启动线程，280–281
- 使用 `ThreadPoolTaskExecutor` 启动线程，280–281
- 吞吐量，352
- `TIMED_WAITING`, 257
- 定计时，363
- TLS (传输层安全)，188
- 基于令牌的认证，189
- 生成令牌，120
- `toLongString()` API，314
- 工具化，349
- 使用正则表达式的工具，306–308
- `toShortString()` API，314
- `toString()` API，314
- `@ToString` 注解，243
- `TRACE` 日志级别，140, 150, 156
- 追踪，326, 348–349
- `@Transactional`,281
- `TransferQueue`,275
- 传递性依赖，90
- 传输层安全 (TLS)，188
- Jenkins 中的触发器，116
- 主干分支开发，70
- `tryLock()` 方法，261–262

## U

- `UNICODE_CASE` 标记，298
- `UNICODE_CHARACTER_CLASS` 标记，298
- 统一资源标识符 (URI)，47
- 解包，33
- 统一资源标识符 (URI)，47
- Jira 中的用户，78, 126

## V

- `validate` 阶段，92
- 值
    - 分桶，339–341
    - 捕获，338–339
    - 格式化
        - Java Logging 中，132–133
        - Log4j 中，140–141
        - SLF4J 中，151
    - 替换，292–293, 296
- 指定变量，110
- VCS (版本控制系统),42
- `verify` 阶段，92
- 验证
    - 调用，219
    - 使用假设逻辑，209–210
- 版本控制
    - 添加项目到，15
    - 从创建项目，15
- 版本控制系统 (VCS)，42
- 版本号 (POM)，94
- 版本，4
- 垂直扩展性，352
- Victor 在 Pluralsight 上的正则表达式，308
- 在 Jira 中查看问题，80
- Jenkins 中的视图，126
- 选择虚拟机，390
- 虚拟线程，7, 250, 271–275
- Visual Studio (VS) Code
    - 关于，37–39
    - IDE 集成，225
    - 在中安装 Lombok，237
    - 使用，104–106
    - 网站，40
- VisualVM，370–371
- `void await()` 方法，261–262
- `void lock()` 方法，261–262
- `void lockInterruptibility()` 方法，261–262
- `void signal()` 方法，261–262
- `void signalAll()` 方法，261–262
- `void unlock()` 方法，261–262
- `volatile` 关键字，255
- `volatile` (参见 Visual Studio)

## W

- `TIMED_WAITING`,257
- 定计时，363
- TLS (传输层安全)，188
- 基于令牌的认证，189
- 生成令牌，120
- `toLongString()` API，314
- 工具化，349
- 使用正则表达式的工具，306–308
- `toShortString()` API，314
- `toString()` API，314
- `@ToString` 注解，243
- `TRACE` 日志级别，140, 150, 156
- 追踪，326, 348–349
- `@Transactional`,281
- `TransferQueue`,275
- 传递性依赖，90
- 传输层安全 (TLS)，188
- Jenkins 中的触发器，116
- 主干分支开发，70
- `tryLock()` 方法，261–262

## U

- `UNICODE_CASE` 标记，298
- `UNICODE_CHARACTER_CLASS` 标记，298
- 统一资源标识符 (URI)，47
- 解包，33
- 统一资源标识符 (URI)，47
- Jira 中的用户，78, 126

## V

- `validate` 阶段，92
- 值
    - 分桶，339–341
    - 捕获，338–339
    - 格式化
        - Java Logging 中，132–133
        - Log4j 中，140–141
        - SLF4J 中，151
    - 替换，292–293, 296
- 指定变量，110
- VCS (版本控制系统),42
- `verify` 阶段，92
- 验证
    - 调用，219
    - 使用假设逻辑，209–210
- 版本控制
    - 添加项目到，15
    - 从创建项目，15
- 版本控制系统 (VCS)，42
- 版本号 (POM)，94
- 版本，4
- 垂直扩展性，352
- Victor 在 Pluralsight 上的正则表达式，308
- 在 Jira 中查看问题，80
- Jenkins 中的视图，126
- 选择虚拟机，390
- 虚拟线程，7, 250, 271–275
- Visual Studio (VS) Code
    - 关于，37–39
    - IDE 集成，225
    - 在中安装 Lombok，237
    - 使用，104–106
    - 网站，40
- VisualVM，370–371
- `void await()` 方法，261–262
- `void lock()` 方法，261–262
- `void lockInterruptibility()` 方法，261–262
- `void signal()` 方法，261–262
- `void signalAll()` 方法，261–262
- `void unlock()` 方法，261–262
- `volatile` 关键字，255
- `volatile` (参见 Visual Studio)

## X

- XML. (参见 eXtensible Markup Language (XML))
- XML Path Language (XPath),397
- XML Query (XQuery),397
- XML Schema Definition (XSD),397
- `XMLLayout` class，158
- XPath (XML Path Language),397
- XQuery (XML Query),397
- XSD (XML Schema Definition),397
- `@Xslf4j` annotation，246
- XSLT (eXtensible Stylesheet Language Transformation),397

## Y

- Yet Another Markup Language (YAML)
    - 关于，148, 408
    - 比较库，412
    - 格式用于，408–409
    - 阅读
- 使用 `Jackson`409–410
- 使用 `SnakeYAML`410–412
- 网站，413
- 写入
    - 使用 `Jackson`410
    - 使用 `SnakeYAML`410–412

## Z

- `Zipkin`350

版权 © 2025 John Wiley & Sons, Inc. 保留所有权利，包括文本和数据挖掘、AI 训练及类似技术。

由 John Wiley & Sons, Inc. 出于新泽西霍霍肯。
在加拿大和英国同时出版。

ISBN: `9781394275724` (平装本), `9781394275748` (ePDF), `9781394275731` (ePub)

本出版物的任何部分均不得复制、存储在检索系统中或以任何形式和任何手段（电子、机械、复印、录制、扫描或其他方式）传输，除非符合 1976 年《美国版权法》第 107 条或 108 条的规定，或获得出版者的事先书面许可，或通过向 Copyright Clearance Center, Inc. 支付适当的副本费用（222 Rosewood Drive, Danvers, MA 01923, (978) 750-8400,  fax (978) 750-4470）或在网站 `www.copyright.com` 上授权。向出版者申请许可请联系：John Wiley & Sons, Inc., 许可部门，111 River Street, Hoboken, NJ 07030, (201) 748-6011, 传真 (201) 748-6008，或在线访问 `www.wiley.com/go/permission`。

商标：`WILEY` 和 Wiley 标志是 John Wiley & Sons, Inc. 及其/关联公司在美国和其他国家的商标或注册商标，未经书面许可不得使用。`Java` 是 Oracle America, Inc. 的商标或注册商标。所有其他商标均为其各自所有者的财产。John Wiley & Sons, Inc. 与书中提到的任何产品或供应商均无。

责任限制/免责声明：尽管出版商和作者在准备本书时已尽到最大努力，但他们对本书内容的准确性或完整性不作任何陈述或保证，并特别否认任何关于畅销性或特定用途适用性的暗示保证。销售代表或书面销售材料可能创建或扩展任何保证。此书中包含的建议和策略可能不适用于您的情况。在适当的情况下应咨询专业人士。此外，读者应注意，本书中列出的网站在本书编写期间到阅读期间可能已经更改或消失。出版者和作者均不对任何利润损失或任何其他商业损害（包括但不限于特殊、间接、后果性或其他损害）承担责任。

有关有关我们其他产品和服务的通用信息，请联系我们的美国客户服务部门：(800) 762- 2974；美国境外：(317) 572- 3993。有关产品技术支持，您可以在 `https://support.wiley.com` 查找常见问题或通过在线聊天与我们联系。

如果您认为书中有错误，请通过电子邮件联系我们的读者支持团队 `wileysupport@wiley.com`，主题为“Possible Book Errata Submission（可能的书籍勘误提交）”。

Wiley 以多种电子格式出版书籍。印刷版中出现的某些内容可能在电子格式中不可。有关 Wiley 产品的更多信息，请访问我们的网站 `www.wiley.com`。

美国国会图书馆控制号：2024934523
封面图片：© CSA-Printstock/Getty Images
封面设计：Wiley

*致 Java 社区，感谢你们如此开放地帮助人们学习*。

—VICTOR & JEANNE

# 作者简介

**VICTOR GRAZI** 是一位好学的学习者，他在 1996 年听闻了这种被称为“互联网”的新技术，以及一种让互联网蓬勃发展的新技术 `Java`。他于 2012 年入选 Java 冠军，担任 Java 社区进程执行委员会成员，领导一项 `JSR`，曾担任 InfoQ 杂志的 Java 首席编辑，并走遍世界宣扬 `Java`。他是 `Java Concurrent Animated` 的作者，该应用程序帮助数千名开发者将 Java 并发模型可视化。

**JEANNE BOYARSKY** 对出版这本书（她的第 10 本书）感到非常兴奋。她于 2019 年被选为 Java 冠军，是 NYJavaSIG 的领导者。她在纽约市的一家银行担任了 22 多年的 Java 开发人员，在在那里负责开发、指导和开展培训。业余之余，她是 `CodeRanch.com` 的高级版主，并负责该论坛的代码库工作。Jeanne 还指导一个 FIRST 机器人小组的编程部门，在那里与刚接触 `Java` 的学生们合作。她还经常进行演讲。

# 技术编辑

**VICTOR GRAZI** 是一位渴求知识的学习者，他在 1996 年听闻了这种被称为“互联网”的新技术，以及一种让互联网蓬勃发展的新技术 `Java`。他于 2012 年入选 Java 冠军，担任 Java 社区进程执行委员会成员，领导一项 `JSR`，曾担任 InfoQ 杂志的 Java 首席编辑，并走遍世界宣扬 `Java`。他是 `Java Concurrent Animated` 的作者，该应用程序帮助数千名开发者将 Java 并发模型可视化。

**JEANNE BOYARSKY** 对出版这本书（她的第 10 本书）感到非常兴奋。她于 2019 年被选为 Java 冠军，是 NYJavaSIG 的领导者。她在纽约市的一家银行担任了 22 多年的 Java 开发人员，在在那里负责开发、指导和开展培训。业余之余，她是 `CodeRanch.com` 的高级版主，并负责该论坛的代码库工作。Jeanne 还指导一个 FIRST 机器人小组的编程部门，在那里与刚接触 `Java` 的学生们合作。她还经常进行演讲。

# 技术编辑

**RODRIGO GRACIO** 是一位资深软件工程师、Java 倡导者和技术负责人。他拥有巴西 UNILALLE 的计算机科学学士学位，自 2006 年起一直致力于 `Java`。他是纽约州用户小组的活跃成员，并积极组织该小组的活动。他经常在南美、美国和欧洲的科技会议上演讲，分享他对 Java 语言及其最佳实践的热情。目前他在 BNY 担任工程总监。由于对 Java 社区的贡献，Rodrigo 在 2022 年被提名为 Java 冠军。

# 技术校读者

**BARRY BURD** 是新泽西州德鲁大学数学系和计算机科学系的教授。他是 Garden State Java User Group 的主管，并与 Jeanne 一起担任 NYJavaSIG 的领导者。他是多本 Java 书籍的作者，包括《Java For Dummies》（即将出版第 9 版）。他最近的著作是 Packt 出版的 `Quantum Computing Algorithms`。在 2020 年，他荣幸被授予 Java 冠军。

# 致谢

感谢许多对本书做出贡献的人。感谢 Patrick Walsh 和 Archana Pragash 指导我们完成过程并在许多方面改进了本书。感谢 Rodrigo Graciano 担任我们的技术编辑，感谢 Barry Burd 担任我们的技术校读者。他们在许多方面改进了本书。特别感谢我们的文字编辑 Kim Wimpsett 发现了我们（包括我们自己！）错过的细微错误。这本书的出版离不开 Wiley 的许多人员，包括 Kenyon Brown、Pete Gaughan、Ashirvad Moses 等。

Victor 特别想感谢他的妻子 Victoria，感谢她为了让我写这本书而牺牲了所有的约会时间。他每天都向她学习，并对她的愿景感到震撼。他还想感谢他的父母 Jack 和 Claudie Grazi 对他所投入的一切。最后，他怀念已故的布鲁克林中学数学教授 Isadore Glaubiger，这位教授启发了他并教会他思考。并特别感谢 Jeanne 的组织能力和对细节的关注。如果没有 Jeanne，他说他可能连第一页都写不完。

Jeanne 在与书籍写作重叠的艰难月份里，亲自感谢 Dani、Janeice、Kim、Norm、Scott 和 Shweta。她还感谢 Scott 的耐心等待，因为 Jeanne 同时在撰写两本书（本书和 *Oracle Certified Professional Java 21 Developer Study Guide*）。非常感谢 Victor，他构思了这本书的想法，并作为一位非常出色的合著者将其付诸现实。最后，Jeanne 想要感谢 [`CodeRanch.com`](http://coderanch.com) 上的所有新晋程序员，以及 FIRST 机器人团队 FRC 694 和 FTC 310/479，感谢他们不断提醒她新程序员的思维方式。

# WILEY 终端用户许可协议

请访问 [www.wiley.com/go/eula](http://www.wiley.com/go/eula) 以访问 Wiley 的电子书用户许可协议 (EULA)。
