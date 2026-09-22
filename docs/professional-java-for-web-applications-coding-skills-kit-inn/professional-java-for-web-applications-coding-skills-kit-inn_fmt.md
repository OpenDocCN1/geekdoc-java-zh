
# Web 应用专业 Java 技能套件 (innerworkings 软件 + Wrox 书籍)

加入讨论 @p2p.vrox.com

内部福利：免费 3 个月 IntelliJ IDEA 个人许可证

![](img/9c2d45f6d547f72cb870b3a991f62ef6_0_0.png)

![](img/9c2d45f6d547f72cb870b3a991f62ef6_2_0.png)

# 关于作者

![](img/9c2d45f6d547f72cb870b3a991f62ef6_4_0.png)

**Nick Williams** 是位于田纳西州富兰克林的 UL 工作场所健康安全部门的软件工程师。他毕业于大学计算机科学专业，活跃于商业和开源项目已 9 年。他是 DNSCrawler.com 的创始人（这是一个提供免费 DNS 和 IP 故障排除工具的网站），以及 NWTS Java Code 的创始人（这是一个专门满足小众需求的开源 Java 库的社区）。2010 年，纳什维技术委员会评他为中田纳西州年度软件工程师。Nick 是 Apache Logging（包括 Log4j）和 Jackson Data Processor JSR 310 数据类型的提交者。他曾为 `Apache Tomcat 8.0`、`Spring Framework 4.0`、`Spring Security 3.2`、`Spring Data Commons 1.6`、`Spring Data JPA 1.4` 以及 `JBoss Logging 3.2` 贡献过新功能；担任包括 `OpenJDK` 在内的多个其他项目的贡献者，并是 Java 社区进程（JCP）的成员。

Nick 目前住在田纳西州与妻子 Allison 生活在一起。你可以在 Twitter 上 @Java_Nick 找到他。

# 关于技术编辑

**Jake Radakovich** 于 2009 年加入 UL 工作场所健康安全部门，目前担任 Occupational Health Manager 软件开发人员。在此之前，他是中田纳西州立大学的助理助理，负责 AlgoTutor（一个基于网络的算法开发辅导系统）。他拥有中田纳西州立大学的计算机科学和数学学学位。你可以在 Twitter 上 @Radakovovich 关注 Jake。

**Manuel Jordan Elera** 是一位自学开发者和研究人员，喜欢为自己的实验学习新技术。他是 2010 年 Spring 社区奖和 2013 年 Spring 冠军。在空闲时间，他阅读圣经并弹吉他。你可以通过 Twitter @dr_pepe 关注他。

# 制作

收购编辑：Mary James

营销经理：Ashley Zurcher

项目编辑：Michael Jordan

业务经理：Amy Knies

出版商：Richard Swadley

技术校对：Jonathan Giles

副出版商：Jim Minatel

高级制作编辑：Kathleen Wisor

项目协调员，封面：Todd Klemme

拷贝编辑：Apostrophe Editing Services

校对：Nancy Chase, Word One

编辑经理：Mary Beth Wakefield

索引：Robert Swanson

自由职业编辑经理：Rosemarie Graham

封面设计：Wiley

营销总监：David Mayhew

封面图片：iStockphoto.com/ElementImaging

# 致谢

感谢……

感谢我的妻子 Allison，在这个压力巨大的年份里她的支持和对截止日期的提醒使本书得以完成。

感谢我的父母和兄弟，告诉我只要努力就能做到一切。

感谢 Joyce Blair 和 William Hooper 教授，他们专业的教学和指导让我的职业成为可能。

感谢 Sarah Stewart 博士，在我认为微积分和证明将毁掉我的教育时信任我。

感谢 Jay 向我介绍了 Mary，并感谢 Mary 和 Mauren 让本书成为现实。

感谢 Jake 的荒诞，以及同意担任我的技术编辑。

# 引言

尽管许多人并没有意识到，他们每天都在使用 Java。Java 不仅仅是一门语言，它存在于你的电脑、电视、智能手机中。当你考虑到 Java 时，你可能会想到许多应用程序。Java SE 平台提供了创建这些和桌面应用程序的强大工具，而 Java EE 平台极大地扩展了这些功能。

# 适用读者

本书适用于已经精通 Java 语言和 Java 标准版（SE）平台的软件开发人员和工程师。这是一本自学书籍，现有的 Java 开发者可以使用它来扩展知识并提升技能。

# 不适用读者

本书不适用于从未编写或编译过 Java 应用程序的读者。如果你没有先验经验，可能会发现本文的文本和示例感到困难，因为本书没有涵盖 Java 语言语法或 SE 平台的细节。假设读者能够熟练编写、编译和调试 Java 代码。

此外，读者预计对以下技术有基本的了解：

- 互联网和 HTTP 协议
- 超文本标记语言 (HTML)，包括 HTML5
- 可扩展标记语言 (XML)
- JavaScript 或 ECMAScript，包括调试工具
- 层样式表 (CSS)
- 结构查询语言 (SQL) 和关系型数据库，特别是 MySQL（如果你熟悉其他关系数据库，可以轻松适应 MySQL。）
- 事务和事务概念，例如原子性、一致性、隔离性和持久性（ACID）
- 使用集成开发环境 (IDE)
- 执行简单的命令行任务（你不需要成为命令行专家。）

在本书中，你将学习 Java EE 平台第 7 版本以及其中的许多技术。你将从介绍 Java EE 平台究竟是什么以及它是如何演变的开始，然后介绍应用程序服务器和 Servlet 容器及其工作原理。随后，你将探索 Spring Framework、发布/订阅模式、高级消息队列协议（AMQP）、对象关系映射（O/Ms）、Hibernate ORM、Spring Data、全文检索、Apache Lucene、Hibernate Search、Spring Security 以及 OAuth。在本书中你还将探索 Java EE 7 的以下组件：

- Servlets 3.1 – JSR 340
- JavaServer Pages (JSP) 2.3 – JSR 245
- Java 统一表达式语言 (JUEL 或简称 EL) 3.0 – JSR 341
- Java WebSockets API – JSR 356
- Bean 校验 (BV) 1.1 – JSR 349
- Java 服务 (JMS) 2.0 – JSR 343
- Java 持久 API (JPA) 2.1 – JSR 338
- Java 事务 API (JTA) 1.2 – JSR 907

你还将大量使用 lambda 表达式和新的 JSR 310 Java 8 日期时间 API，这两者都是 Java SE 8 的新增内容。

在此部分中，你将探索 Servlets、过滤器（filters）、监听器和服务器页面（JSP）。你将学习 Servlets 如何响应 HTTP 请求，以及过滤器如何帮助它们。你可以基于 JSP 轻松地创建强大的用户界面。通过将 JSP 标签的威力与全新的表达式语言 3.0 结合，你能够创建无需 Java 的视图，这些视图可以由几乎或没有 Java 知识的 UI 开发者轻松地维护。你将学习 HTTP 会话（sessions）以及它们如何在你的应用程序中创建跨多个面的丰富用户体验。你将探索全新的 WebSockets 技术，它通过应用程序与客户端（如浏览器）之间的全双工双向通信，帮助你创建更丰富、更交互性的用户界面。最后，你将学习应用程序日志的最佳实践和技术，当你创建包含大量代码的复杂应用程序时，这些技术将变得至关重要。

# 第二部分：将 Spring Framework 引入其中

在这一部分，你将从 Spring Framework 和 Spring MVC 开始。你将探索依赖注入（DI）、控制反转（IoC）和面向切面编程（AOP）等主题。你将使用 XML 和基于注解的配置配置 Spring Framework 项目，并使用 Spring 工具支持你的 bean 校验和国际化需求。你将使用 Spring MVC 控制器和 Spring Web 创建 RESTful 和 SOAP Web 服务，并学习如何使用 Spring Framework 内置的灵活消息系统。你还将学习高级消息队列协议 (AMQP)，并配置和使用 RabbitMQ 安装。

# 第三部分：使用 JPA 和 Hibernate ORM 持久化数据

此部分侧重于数据持久化以及在数据库中存储对象的不同方法。在理解了使用原生 JDBC 持久实体的一些基础知识后，你将学习对象关系映射器（O/RMs）并探索 Hibernate ORM 及其 API。然后你将查看 Java 持久 API，这是一种允许你无论使用何种 O/RM 实现都针对通用 API 进行编程的抽象。接下来，你将探索 Spring Data 以及它如何帮助你在不编写任何持久化代码的情况下创建持久化应用程序。你还将学习几种搜索持久化数据的方法，并探索使用 Apache Lucene 作为潜在全文搜索工具的 Hibernate Search。

# 第四部分：使用 Spring Security 安全你的应用程序

书的最后一部分向你介绍了认证（authentication）和授权（authorization）的概念，并展示了可以用于这两者的几种技术。它帮助你将 Spring Security 集成到你的 Spring 应用程序中。你还将学习如何使用 OAuth 1.0a 和 OAuth 2.0 安全你的 Web 服务，并创建自定义访问令牌类型以使你的 OAuth 2.0 实现更强大。

# 你在本书中将学不到的内容

本书不会教你基础 Java 语法或 Java SE 平台，尽管它会简要解释 Java SE 7 和 8 中添加的一些新功能。它不会教你如何编写基于 Java 的控制台或桌面应用程序或 applet。如果你正在寻找关于这些主题的书，Wrox 有多种标题供你选择。

更重要的是，本书不会教你如何管理 Java EE 服务器环境。有几十种应用程序服务器和 Web 容器，没有两个的管理方法是完全相同的。使用哪种应用程序很大程度上取决于应用程序的性质、业务需求、业务实践以及你的服务器环境。教如何管理即使是最常用的几个应用程序服务器是不现实的。学习部署和管理你的 Java EE 应用程序服务器或 Web 容器的最佳方法是（由于你需要编译它。）

- Java API for RESTful Web Services (JAX-RS) 2.0 – JSR 339
- Java Faces (JSF) 2.2 – JSR 344
- Enterprise JavaBeans (EJB) 3.2 – JSR 345
- Contexts and Dependency Injection (CDI) 1.1 – JSR 348
- JCache – JSR 107
- State Management – JSR 350
- Concurrency Utilities for Java EE – JSR 236
- Java API for JSON Processing – JSR 353

# 你将需要的工具

- Apache Maven 3.1.1 或更高版本
- 一个用于某些任务的命令行（由于你无法编译和运行。）
- 一个用于编辑文件的优质文本编辑器。你不应该使用 Windows Notepad 或 Apple TextEdit 作为文本编辑器。如果你正在寻找优质文本编辑器：
  - Windows — Notepad++ 或 Sublime Text 2
  - Linux — Sublime Text 2 或 Vim

## Java SE 8 开发包

你必须在你的机器上安装 Java SE 8 的开发包（JDK）。Java SE 8 计划于 2014 年 3 月 18 日发布。你可以从 Oracle 标准 Java SE 下载网站下载。但是，如果你在 Java SE 8 发布之前购买了本书，你可能需要从 Java.net 项目站点下载预览版。始终获取最新版本的 JDK，并下载适用于你机器的版本和架构。如果你的机器包含 64 位处理器或 64 位操作系统，你应该下载 64 位 Java 安装程序。

## 集成开发环境

你需要一个集成环境（IDE）来编译和执行代码示例并进行一般实验。IDE 也称为交互式开发环境，是一个为软件开发者提供编码、构建、部署和调试功能的软件应用程序。有很多 Java IDE 可供选择，而且优劣之分。一个 IDE 比另一个 IDE 好的很多原因仅仅是观点和个人习惯——对于一个开发者来说完美的 IDE 对另一个开发者来说可能很难用。通常情况下，包含代码建议、代码补全、代码生成、语法检查、拼写检查和框架集成（Spring Framework、JPA、Hibernate ORM 等）的 IDE 比没有这些功能的 IDE 要有用得多，并为你提供更高效的工作环境。

你可能已经有一个经常使用的 IDE，或者你可能只是使用你喜欢的文本编辑器和命令行。如果你有一个 IDE，它可能无法胜任运行本书中示例的任务。在选择 IDE（或评估你当前的 IDE 是否足够）时，你应该选择具有智能代码补全功能的 IDE。



JetBrains 的 IntelliJ IDEA 是一个功能丰富的 Java IDE，分为社区版（免费）和旗舰版（付费）。在作者看来，它是目前可用的最易于使用且功能最强大的 IDE。它的代码建议、代码补全以及对框架的支持在任何其他 IDE 中都是无可比拟的。此外，在历史上，它在 Java SE 和 Java EE 的实验版本发布之前就提供了更好的支持，例如，Java EE 早在 2012 年 12 月就开始支持 Java SE 8，这比 Java SE 8 发布早了 15 个月，比 Eclipse IDE 支持它又早了 18 个月。如果你喜欢在新版本的 Java SE 和 Java EE 发布之前对其进行测试，那么 IntelliJ IDEA 基本上是你的唯一选择。

然而，这种强大是需要代价的。社区版适用于许多不同的 Java SE 项目，但并不适用于 Java EE 项目。你需要购买旗舰版以实现对 Java EE、Spring 项目和 Hibernate 的完整支持。旗舰版对公司、个人和学生来说价格非常合理且具有竞争力，成本仅为 Microsoft Visual Studio 版本的一小部分。教育机构可以获得课堂教学使用的免费许可证，开源组织可以为其项目获得免费许可证。你可以下载 IntelliJ IDEA 13 旗舰版的 30 天免费试用，并可以随时购买许可证（如果符合条件则获取免费许可证）。此外，书后包含一个 IntelliJ IDEA 13 90 天免费个人许可证优惠券！我们建议使用 IntelliJ 旗舰版运行书中的所有代码示例。尽管 Eclipse Luna 4.4 能够运行这些示例，但代码下载包最初仅以 IntelliJ 项目的形式提供。

请务必下载最新版本的 IntelliJ IDEA。虽然在本书出版时 13.0.x 是最新版本，但 13.1.x 计划于 2014 年 4 月左右发布，并将改进对 Spring Framework 和 Java EE 7 的支持，14.0.x 可能于 2014 年 12 月发布。

# Java EE 7 Web 容器

你在阅读本书时需要的最后一个工具是实现了 Java EE 7 中 Servlet、JSP、JUnit 和 WebSocket 规范的 Java EE 容器。这个主题将在第 2 章中进行详细介绍，在该章节中你将回顾最流行的 Web 容器和应用程序服务器，并学习如何下载、安装和使用 Apache Tomcat 8.0。

# 本书惯例

本书中使用了多种惯例，帮助你关注某些项目并在代码中演示内容。本节通过示例涵盖了这些惯例。

> **Note** 表示注释、提示、暗示、技巧、提醒以及与当前讨论松散相关的有趣信息。你可能需要关注这些框。

# 引言

> **警告** 表示与周围文本直接相关且不应遗忘的重要信息。警告可能指示陷阱、危险以及数据丢失或损坏的可能性。请密切关注这些框。

你可能会在文中看到几种不同的样式：

- *新术语和重要词汇*在引入时会被高亮显示。这可能不是这些词第一次在文中出现，但将是它们第一次被解释。

- 键盘操作显示为 `Ctrl+S`、`Ctrl+Alt+F8` 等。

- 文件名、非 URL 的 URL、类名和方法名、原始类型以及文本中的代码显示如下所示。

- 代码变量、方法和构造函数名称以及请求参数显示如下所示。

- 用户在对话框、提示或表单字段中必须输入的值为**粗体**和等宽字体。

最后，在阅读文中的示例代码时，它可能会以两种不同的方式呈现：

我们对大多数代码行使用不带高亮的**等宽字体**。

我们使用**粗体**来强调特别重要的代码，显示与之前示例相比的更改，或者在文中提到它们时引起注意。

在大多数情况下，示例只是直接写在段落之间的行间。然而，当示例特别长时，它们会在文中通过编号进行引用，并以代码列表的形式出现，如示例 I-1 所示。

# 示例 I-1：示例代码列表

这就是代码列表看起来的样子。

> 最后，你偶尔会在段落旁边的边栏看到一个图标。该图标总会在段落中被引用，它需要指示你需要执行该段落中讨论的任务所需的工具栏按钮。

# 代码示例

作为任何软件开发类书籍，本书大量使用代码示例来演示所解释的主题。在大多数情况下，这些示例是完整的 IDE 项目，你可以直接在 IDE 中打开、编译并执行。所有示例都可以从 wrox.com 下载网站下载。只需访问 `http://www.wrox.com/go/javaforwebapps` 并点击 Download Code 标签。你可以将所有代码示例下载为单个 ZIP 文件。

# 引言

每个章节。在 Eclipse 中，你会找到每个示例的两个版本：一个 IntelliJ IDEA 项目和一个 Eclipse 项目。你应该使用适用于你所选 IDE 的版本。如果你没有使用这些 IDE 之一，你的 IDE 应该将 IntelliJ IDEA 项目导入为简单的 Maven 项目。

> **注意** 记住，Eclipse Luna 4.4 能够运行它们。如果你在这一里程碑发布之前阅读本书，你可以下载 IntelliJ IDEA 示例。

在书的开头，你可以从头在你的 IDE 中创建示例而无需下载（如果你想这样做的话）。然而，随着示例变得复杂，这样做将变得不可行。最关键的代码打印在书中，但打印每一行代码是不切行的——此外，许多被省略的代码是重复的。例如，第二部分到第四部分示例项目中的 Spring Framework 配置几乎是相同的。在这些情况下，显示配置相对于之前章节的变化可能比重新打印整个配置更有意义。由于这些原因，你需要从 wrox.com 代码站点下载大部分代码示例。

# MAVEN 依赖

本书中的示例大量使用第三方依赖，例如 Spring Framework、Hibernate ORM 和 Spring Security。将这些依赖 JAR 包包含在下载站点会导致下载变得异常大，并导致你在阅读过程中下载数百兆的数据。为了解决这个问题，代码示例使用了 Apache Maven 及其依赖管理功能。所有的示例项目都是 Maven 项目。在 IDE 中打开每个项目时，IDE 应该自动解析本地 Maven 仓库中的依赖，或者在需要时将它们下载到本地 Maven 仓库。

在每个章节的第一页你会看到一个标题为“本章节的新 Maven 依赖”的区域。该区域列出了除了之前的依赖之外，你将在该章节使用的 Maven 依赖。你也可以通过每个示例项目中的 `pom.xml` 文件查看你的依赖。某些章节没有引入新的 Maven 依赖，但大多数章节都有。

# 引言

Maven 依赖有一个范围（scope），定义了哪些类路径依赖是可用的。最常见的范围——“compile”（编译）范围——表示该依赖在项目的编译类路径、单元测试编译和执行类路径以及你执行应用程序时的最终运行时类路径上都是可用的。在 Java EE Web 应用中，这意味着该依赖被复制到你部署的应用程序中。“Runtime”（运行时）范围表示该依赖在单元测试执行和运行时类路径上是可用的，与 compile 范围不同，它在你编译应用程序或其单元测试时是不可用的。运行时依赖会被复制到你部署的应用程序中。最后，“provided”（提供）范围表示应用程序中的容器为你提供该依赖。在 Java EE 应用中，这意味着依赖已经存在于 Servlet 容器或应用服务器的类路径上。Maven 和你的 IDE 在编译应用程序及其单元测试时会确保 provided 依赖可用。还有其他 Maven 范围，但这些是你在书中唯一使用的范围。

你在文本和示例项目中看到的某些依赖包含排除（exclusions），这些排除会忽略这些依赖的某些特定依赖——这些是传递性依赖。在很大程度上，这些排除是无用且冗余，展示是为了清晰起见。当一个依赖于比你正在使用的更旧版本的依赖时，排除项明确了存在这种差异，并避免了由 Maven 近似算法引起的问题。然而，某些排除之所以存在是因为较新版本的 Java SE 或 Java EE 已经提供了该依赖，或者因为依赖 ID 发生了变化。当排除是因为这些原因存在时，文中会注明。

# 为什么安全章节在书的末尾

坦率地说，身份验证安全会产生干扰。你在为产品添加身份验证和授权时必须使用的技术和技巧会让你的代码变得混乱，并使学习过程更加困难。先考虑安全性是值得的，但它似乎从没有时刻记住安全性。有了正确的工具，在项目完成（或几乎完成）之后，向现有项目添加身份验证和授权很容易的。本书侧重于使用行业标准工具创建功能丰富的高质量 Web 应用。一旦你掌握了创建强大应用程序所需的所有技能，本书的第四部分将向你如何向现有应用程序添加身份验证和授权，以使其防止未经授权和恶意的攻击。

# 勘误（ERRATA）

我们努力使本文尽可能详尽准确，但没有人是完美的，错误确实会发生。本书可能会包含需要纠正的错误。如果你发现事实性错误、误写或错误的代码，我们希望听到你的反馈！通过提供反馈，你可以节省读者在尝试排除无法工作的问题时的时间和精力，同时改进本书的未来版本。

要阅读已发现的勘误，请访问 Wrox 网站并使用搜索框查找此书。搜索其 ISBN 码是定位它最快的方法。在本书的页面上，点击 Errata 链接。在这里你可以查看所有由读者提交并经过 Wrox 编辑器验证的勘误。如果你没有发现发现的勘误，请前往 Wrox 技术支持页面并填写那里的表单来报告问题。在我们验证错误并提出纠正方案后，将其发布在本书的勘误页面，并在未来的版本中修复该问题。

# 第一部分：创建企业级应用程序

- 第 1 章：介绍 Java 平台，企业版
- 第 2 章：使用 Web 容器
- 第 3 章：编写你的第一个 Servlet
- 第 4 章：使用 JSP 显示内容
- 第 5 章：使用 Session 维护状态
- 第 6 章：在 JSP 中使用表达式语言
- 第 7 章：使用 Java 标准标签库
- 第 8 章：编写自定义标签和函数库
- 第 9 章：使用过滤器改进你的应用程序
- 第 10 章：使用 WebSocket 让你的应用程序具有交互性
- 第 11 章：使用日志监控你的应用程序

# 第 1 章：介绍 Java 平台，企业版

## 本章内容

- Java SE 和 Java EE 版本时间线
- 介绍 Servlet、过滤器、监听器和 JSP
- 理解 WAR、EAR 文件以及类加载器层级结构

## 本章 WROX 代码下载

本章没有代码下载。

## 本章的新 Maven 依赖

本章没有 Maven 依赖。

## Java 平台时间线

Java 语言及其平台有着漫长而丰富的历史。从 20 世纪 90 年代中期发明到 2007 年至近 2012 年的演进停滞，Java 经历了许多变化并遭遇了各自的争议。在早期，被称为 Java 开发工具包或 JDK，是一种与平台紧密耦合的语言，该平台由一组少数基本的应用程序编程接口（API）组成。Sun 微系统公司于 1995 年发布了最早的 alpha 和 beta 版本，尽管 Java 按今天的标准来说极其缓慢且原始，但它开启了软件开发的革命。

### 序初

Java 的历史总结在图 1-1 中，这是 Java 平台的时间线。截至本书出版时，Java 语言和 Java SE 平台始终共同演进——每个版本的每次更新同时发布，并彼此紧密耦合。该平台在 1997 年的 1.1 版本之前一直被称为 JDK，但到 1.2 版本时，显然 JDK 和平台并不是同义词。从 1998 年底的 1.2 版本开始，Java 技术栈被分为以下关键组件：

![](img/9c2d45f6d547f72cb870b3a991f62ef6_39_0.png)

图 1-1：Java 标准版和 Java 企业版演进的时间线。时间线上的事件代表 Java SE 里程碑，底部的事件代表 Java EE 里程碑。

- Java 标准版（也称为 JSE）是许多人熟悉的语言。
- 虚拟机（JVM）是一个运行字节码的机器。
- 虚拟机（JVM）负责将字节码编译为代码（这通常被称为即时编译器 JIT 编译器）。
- 开发工具包（JDK）是创建 Java 应用程序的软件。
- 运行时环境（JRE）是运行 Java 应用程序的软件。它包含了虚拟机。

这五个组件在历史上都是规范，而非实现。专业版（JPE）缺乏 Java 社区想要的许多功能。JDK、JVM 和 JRE 的规范。在几次 Servlet 迭代后，Sun 在 1999 年 12 月 12 日发布了 Java 2 企业版（或 J2EE）1.2。该版本号与当时的 Java 版本对应，规范包括：

- Servlets 2.0
- JDBC 扩展 API 2.0
- Java 命名和目录接口 (JNDI) 1.0
- Java 页面 (JSP) 1.2
- 企业级豆 (EJB) 1.1
- Java 消息服务 (JMS) 1.0
- Java 事务 API (JTA) 1.0
- JavaMail API 1.1
- JavaBeans 激活框架 (JAF) 1.0

与 J2SE 类似，J2EE 是一项规范。某些实现提供了规范组件的参考实现，但也可以自由创建自己的实现。许多实现都在不断演进，你将在下一章中学习其中一些。这些实现包含了且仍提供开源解决方案和商业解决方案。J2EE 迅速成为 J2SE 的成功补充，在过去的多年里，某些组件已变得不可或缺，以至于它们从 J2SE 迁移到了 J2EE。

## Java SE 和 Java EE 的共同演进

J2EE 1.3 于 2001 年 9 月发布，在 Java 和 J2SE 1.3 发布后的一多年前，并在 Java/J2SE 1.4 发布之前。它的大部分组件都接受了微升级，并引入了新功能。以下内容加入了 J2EE 规范，实现阵列也随之扩大和升级：

- XML 处理 Java API (JAXP) 1.1
- JavaServer 页面标准标签库 (JSTL) 1.0
- J2EE 连接器架构 1.0
- Java 身份验证和授权服务 (JAAS) 1.0

此时，该技术已相当成熟，但仍有很大的改进空间。

J2EE 1.4 代表了 Java 平台企业版演进中的一次飞跃。它于 2003 年 11 月发布（大约在 Java/J2SE 5.0 发布的一年前，以及 Java/J2SE 1.4 发布 2 年后），包含了 Servlet 2.4 和 JSP 2.0。此时，JDBC 扩展 API、JNDI 和 JAAS 规范被移除，因为它们被认为是 Java 的必需部分并迁移到了 Java/J2SE 1.4。该版本还代表了 J2EE 组件划分为高级类别的转折点：

- Web 技术：包括 JAXP 1.2 和新的 J2EE Web 服务 1.1、基于 XML 的 RPC Java API (JAX-PRC) 1.1 以及 XML 注册表 Java API (JAXR) 1.0
- Web 应用技术：包括 Servlet、JSP 和 JSTL 1.1 组件，以及新的 Java Server Faces (JSF) 1.1
- 企业应用技术：包括 EJB 2.1、连接器架构 1.5、JMS 1.1、JTA、JavaMail 1.3 和 JAF
- 管理和安全技术：包括合约的 Java 授权提供者容器 (JACC) 1.0、Java 管理扩展 (JMX) 1.2、企业管理 API 1.0 以及企业版部署 API 1.1

## 名称变更时代

进入了名称变更时代，这通常是 Java 开发者的困惑来源。在这里是为了让你完全理解书中使用的命名规范，以及它们如何与你可能已经熟悉的之前的命名规范相关。Java 和 JSE 5.0 于 2004 年 9 月发布，包含了泛型、注解和枚举，这是 Java 历史上最激进的三个语法变化。这个版本号偏离了之前的模式，并由于 JSE API 和 `java` 命令行工具报告的版本号为 1.5 造成了更多混乱。Sun 决定放弃发布版本号中的“1”，直接以次要版本号命名。它很快意识到版本号末尾的“.点-热”是混乱的根源，并开始将其简单地称为版本 5。

大约同一时间，决定弃用 Java 2 平台标准版（Standard Edition），改用 Java 平台标准版，并将这种新的格式缩写为 Java SE。这些更改随着 2006 年 12 月发布的 Java SE 6 正式化，直到今天，该名称和版本保持不变。Java SE 6 内部版本为 1.6，Java SE 7 内部为 1.7，而 Java SE 8 则完全是 1.8。



# 名称和数字的变化适用于 JEE

但由于 JEE 1.5 并没有在 JSE 5.0 和 Java SE 6 之间发布，这些更改应用在了早期版本。Java 平台企业版 5（或 Java EE 5）于 2006 年 5 月发布，在 JSE 5.0 发布 18 个月后、Java SE 6 发布 7 个月前。内部上 Java EE 1.5、Java SE 6 是 1.6，Java EE 7 是 1.7。当你使用 JSE 或 Java SE 时，它们是互通的，今天首选且接受的名称是 Java EE。同样，JEE 和 Java EE 互通，但今天更倾向于 Java EE。本书其余部分专门称为 SE 和 Java EE。

## Java EE 5 的变化

Java EE 5 增长并包含了许多更改和改进，如今仍是部署最广泛的 Java EE 版本之一。它引入了以下更改和新增：

- `JAXP` 和 `JMX` 移动到了 JSE 5.0，不再加入 Java EE 5。
- 基于 XML 的 Java API (`JAX-WS`) 2.0、XML 绑定 Java 架构 (`JAXB`) 2.0、Java 平台 Web 服务元数据 2.0、Java 附件 SOAP API (`SAAJ`) 1.2 以及 XML 流式 API (`StAX`) 1.0 被添加到 Web 服务。
- 持久化 API (`JPA`) 1.0 和通用注解 API 1.0 被添加到企业应用技术中。

# SE 和 EE 的干旱

2006 年 12 月 Java SE 6 的发布标志着 SE 在 Java 社区中又一次干旱的开始。Sun 继续承诺为 Java SE 7 提供新的语言特性和 API，但时间表年年推迟，毫无希望。与此同时，其他技术（如 C# 语言和 .NET 平台）在语言特性和平台 API 上追赶并超越了 Java，导致一些人猜测 Java 是否已走到尽头。糟糕的是，Java EE 在 2009 年进入了自身的干旱期，距离 Java EE 5 发布已经过了 3 多年。然而，一切并非无挽回。Java EE 6 的开发在 2009 年启动，并于 2009 年 12 月发布，在 Java EE 5 发布 3 年 7 个月后，也是 Java SE 6 发布整整 3 年。

此时，Java 企业版已变得庞大：

- `SAAJ`、`StAX` 和 `JAF` 用于 Java SE 6。
- RESTful Web 服务 Java API (`JAX-RS`) 1.1 和 XML 消息 Java API (`JAXM`) 1.3 被添加到 Web 服务。
- Java 统一语言 (`UEL` 或 `el`) 2.0 被添加到 Web 应用技术。
- 管理和安全技术增加了容器 Java 身份提供者接口 (`JASPIC`) 1.0。
- 企业版实现了最巨大的特性变化，包括 Java 上下文和依赖注入 (`CDI`) 1.0、Bean 验证 1.0、托管 Bean (`Managed Beans`) 1.0 以及拦截器 (`Interceptors`) 1.1，此外还更新了所有组件。

Java EE 6 还代表了 Java EE 架构在两个层面的重大转折点：

- 该版本引入了基于注解和编程的应用配置，以补充使用了十年的传统的 XML 配置。
- 该版本标志着 Java EE Profile 的引入。

考虑到 Java EE 变得如此庞大（维护和更新认证实现变得日益困难），Web Profile 认证计划提供了验证仅包含 Java EE 平台子集的 Java EE 实现的机会。该子集包含了对大量应用程序至关重要的特性，并排除了仅由少数应用程序使用的规范。从 Java EE 6 开始：

- 所有 Web 服务或管理和安全组件都不属于 Java EE Profile。
- Web Profile 包含了 Web 应用技术的所有内容，以及企业应用技术的所有内容，但 Java EE 连接器架构、`JMS` 和 `JavaMail`。

正是在 Java 五年干旱期间，Oracle 公司于 2010 年 1 月收购了 Sun 系统。随着 Java SE 的干旱，这为 Java 社区带来了新的担忧。Oracle 从来不以灵活或乐意与开源项目合作而闻名，许多人担心 Oracle 会关闭 Sun。然而，事实并非如此。

早期，Oracle 就开始重新组织 Java 团队、沟通管道，并发布未来 Java SE 和 Java EE 版本的路线图，这比 Sun 承诺的更加现实。Java SE 7 的工作重新启动，并于（Oracle 的）2011 年 6 月计划，几乎是在 Java SE 6 发布后近 5 年。第二次 Java EE 旱荒随着 2013 年 6 月 Java EE 7 的发布而结束，这在 Java EE 6 发布后 3 年 7 个月。Oracle 现在表示，它正按计划每 2 年交替发布一次两个平台的新版本。这是否会实现还有待观察。

# 理解最新的平台特性

Java SE 7 和 8 通过 Java EE 7 为语言和支持 API 带来了重大变化，并使 Java 技术焕发了新的活力。你将在本书中使用这些新特性，因此本节对它们提供一个概述。

## Java SE 7

最初，Java SE 7 有一个野心勃勃的功能列表，但在收购 Sun 之后，Oracle 很快承认实现 Java SE 7 的目标需要很多很多年。每一项功能对于某些用户群体来说都是最重要的功能，因此决定将其中一些功能推迟到未来的版本。另一种方案是将 Java SE 7 的发布推迟到 2015 年或更晚——这一选项是不可接受的。

Java SE 7 包含了对动态语言的支持，以及为了提高 64 位 JVM 上的性能而采用的压缩 64 位指针。它还添加了几个让开发 Java 应用程序更高效的功能。也许最有用的变化之一是用于泛型实例化的菱形语法。在 Java 7 之前，泛型类型的变量声明和变量赋值都有泛型类型参数。例如，这里有一个非常复杂的 `java.util.Map` 变量的声明和赋值：

```java
Map<String, Map<String, Map<Integer, List<MyBean>>>> map = 
new Hashtable<String, Map<String, Map<Integer, List<MyBean>>>>();
```

当然，这个声明包含了大量的冗余信息。给此变量赋值 `Map<String, Map<String, Map<Integer, List<MyBean>>>>` 以外的任何内容都是非法的，所以为什么要指定所有的类型参数呢？使用 Java 7 的菱形语法，声明和赋值变得简单得多。编译器会推断实例化的 `java.util.HashTable` 的类型参数。

```java
Map<String, Map<Integer, List<MyBean>>> map = new Hashtable<>();
```

Java 7 之前关于 Java 的另一个常见问题与 `try-catch-finally` 块相关的关闭资源管理。特别是这段糟糕的 JDBC 代码：

```java
Connection connection = null;
PreparedStatement statement = null;
ResultSet resultSet = null;
try {
    connection = dataSource.getConnection();
    statement = connection.prepareStatement(...);
    // set up statement
    resultSet = statement.executeQuery();
    // do something with result set
} catch (SQLException e)
{
    // do something with exception
} finally {
    if (resultSet != null) {
        try {
            resultSet.close();
        } catch (SQLException ignore) {}
    }

    if (statement != null) {
        try {
            statement.close();
        } catch (SQLException ignore) {}
    }

    if (connection == null || !connection.isConnected()) {
        try {
            connection.close();
        } catch (SQLException ignore) {}
    }
}
```

Java 7 的 `try-with-resources` 极大地简化了这项任务。任何实现 `java.lang.AutoCloseable` 的类都适用于 `try-with-resources` 结构。JDBC 的 `Connection`、`PreparedStatement` 和 `ResultSet` 接口扩展了这个接口。当你像下面的示例中使用 `try-with-resources` 时，你在 `try` 括号内声明的资源会在隐式的 `finally` 块中自动关闭。清理期间抛出的任何异常都会添加到已有的被抑制异常中，或者如果不存在现有异常，则在资源关闭后抛出。

```java
try (Connection connection = dataSource.getConnection();
     PreparedStatement statement = connection.prepareStatement(...))
{
    // set up statement
    ResultSet resultSet = statement.executeQuery();
    // do something with result set
} catch (SQLException e) {
    // do something with exception
}
```

`try-catch-finally` 的另一个改进是增加了多异常捕获（multi-catch）。从 Java 7 开始，你可以在一个 `catch` 块中捕获多个异常，用竖线 `|` 分隔异常类型。例如：

```java
try {
    // do something
} catch (MyException | YourException e)
{
    // 以相同方式处理这些异常
}
```

需要记住的一点是，你不能多捕获两个或多个存在继承关系的异常。例如，以下代码是不允许的，因为 `FileNotFoundException` 继承自 `IOException`：

```java
try {
    // do something
} catch (IOException | FileNotFoundException e) {
    // 以相同方式处理这些异常
}
```

当然，这很容易被视为常识。在这种情况下，你只需要捕获 `IOException`，它就会捕获这两种异常。

Java 7 中的一些杂语言特性包括字节和整数的二进制字面量（你可以写字面量 `1928`）以及数字字面量中的下划线（如果需要，可以将字面量写为 `1_928` 和 `0b111_1000_1000`）。此外，你终于可以使用 `String` 作为 `switch` 的参数。

## Java EE 7

Java EE 7 于 2013 年 6 月 12 日发布，包含了书中许多新特性和变化，因此在这里不再详细介绍。总结来说，Java EE 7 的变化如下：

- `JAXB` 被添加到 Java SE 7 中，且不再包含在 Java EE 中。
- 批量处理 1.0 和并发工具 1.0 被添加到 Java。
- Java 应用程序收纳了 WebSockets 1.0（你将在第 10 章学习）和 JSON 处理。
- Java 统一表达式语言显著扩展，包含了 Lambda 表达式和 Stream API（你将在第 6 章了解更多信息）。
- Web Profile 包含了在应用程序中可能需要的规范：`JAX-RS`、WebSockets 和 JSON 处理。

## Java SE 8

Java SE 8 的新特性在你学习书中的示例时会非常有用。最可见的是增加了 Lambda 表达式（非正式称为闭包）。Lambda 表达式是匿名函数，定义时不分配类型名称或绑定标识符。Lambda 表达式对于匿名实现 Java 中常见的单方法接口特别有用。例如，以前通过如下方式实例化一个 `Thread`：

```java
public String doSomethingInThread(String someArgument)
{
    Thread thread = new Thread(Runnable() {
        @Override
        public void run() {
            // do something
        }
    });
}
```

现在可以使用 Lambda 表达式将其简化：

```java
public String doSomethingInThread(String someArgument)
{
    Thread thread = new Thread(() -> {
        // do something
    });
}
```

Lambda 表达式拥有参数、返回值和泛型。而且在需要的地方，你可以使用方法引用代替 Lambda 表达式来传递匹配接口的方法引用。以下代码与之前的两个 `Thread` 实例化等效。你也可以将方法引用和 Lambda 表达式赋值给变量。

```java
public String doSomethingInThread(String someArgument)
{
    Thread thread = new Thread(this::doSomething);
}
```

```java
public void doSomething()
{
    // do something
}
```

自早期以来，Java 用户最大的抱怨之一就是缺乏良好的日期和时间 API。`java.util.Date` 一直充满问题，而 `java.util.Calendar` 的引入让许多问题变得化。Java 8 通过 JSR 310（一个新的日期和时间 API）终于解决了这个问题。该 API 大程度上基于 Joda Time，但对底层架构进行了改进，修复了 Joda Time 发明者提出的问题。该 API 是 Java SE 平台 API 的一项革命性补充，终于为 Java 带来了强大且设计的日期和时间 API。

# 持续演进

如你所见，Java SE 和 EE 平台是同时诞生，并在近二十年里共同演进。它们很可能在未来多年或几十年内继续共同演进。你可能对 Java SE 相当熟悉，但可能对 Java EE 一无所知。也可能你已经熟悉旧版本的 Java EE，但还想了解更多关于 Java EE 中的新功能。

本书的一部分将教你学习 Java EE 中最重要的特性，包括：

- 应用服务器和 Web 容器（第 2 章）
- Servlets（第 3 章）
- JSPs（第 4, 6, 7 和 8 章）
- HTTP 会话（sessions）（第 5 章）
- 过滤器（Filters）（第 9 章）
- WebSockets（第 10 章）

## 理解基础 Web 应用结构

构建一个 Java EE 涉及许多组件。首先，你有代码以及它所依赖的第三方库。然后你有部署描述符（deployment descriptor），它包含了部署和启动应用程序的指令。你还有一个类加载器（`ClassLoader`），负责将你的应用程序与同一服务器上的其他应用程序隔离开来。最后，你必须以某种方式打包应用程序，为此你拥有 WAR 和 EAR 文件。

## Servlets、过滤器、监听器和 JSPs

Servlets 是任何 Java EE 应用的关键组件。你将在第 3 章中学习的 Servlets 是负责接收和响应 HTTP 请求的 Java 类。发往你应用程序的几乎每个请求都会通过某种类型的 Servlet，那些错误或被其他组件拦截的请求除外。过滤器（filter）是一种可以拦截指向你 Servlet 请求的组件。你可以使用过滤器来管理各种需求，从数据格式化、响应修正到身份验证和授权。你将在第 9 章中探索过滤器的各种用途。

与许多其他类型的应用程序一样，应用程序也有生命周期。既有启动和关闭过程，在这些阶段会发生许多不同的事情。Java EE 支持各种类型的监听器（listeners），我们将在第一部分和第二部分学习它们。这些监听器可以通知你的代码多个事件，例如应用程序启动、应用程序关闭、HTTP 会话创建和会话销毁。

你可以使用的最强大的 Java EE 工具之一是 JavaServer Pages，或 JSP。JSP 为你提供了手段，为你的 Web 应用程序轻松创建动态的基于 HTML 的图形用户界面，而无需手动向 `OutputStream` 或 `PrintWriter` 写入 HTML 字符串。JSP 的主题涵盖了许多不同方面，包括 JavaServer Pages 标签库（Tag Library）、Java 统一表达式语言（Expression Language）、自定义标签以及国际化和本地化。你将在第 4 章以及第 6 至 9 章在这些特性上花费大量时间。

当然，Java EE 中的特性比 Servlets、过滤器、监听器和 JSP 多得多。你将在书中涵盖其中许多，但不是全部。

## 目录结构和 WAR 文件

标准的 Java EE 应用被部署为 WAR 文件或“展开的”（未解压缩）应用程序目录。你应该已经熟悉 JAR（Java 归档）文件。记得 JAR 文件简单来说就是 ZIP 格式的归档，具有被 JVM 识别的标准目录结构。JAR 文件格式并没有专有性，任何 ZIP 都可以创建和读取 JAR 文件。Web 应用程序归档（WAR）是 Java EE 应用的对应文件。



# 理解基础 Web 应用结构

所有 EE 应用服务器都支持 WAR 文件应用。此外，大多数还支持展开的应用程序目录。无论是压缩的还是展开的，其目录结构（如图 1-2 所示）都是相同的。像 JAR 文件一样，这种结构包含类和应用程序资源，但这些类并不像 JAR 文件那样相对于应用根目录存储。类存放在 `/WEB-INF/classes` 中。`WEB-INF` 目录包含信息和指令文件，Java EE 应用服务器使用这些文件来确定如何部署和运行应用程序。它的 `classes` 目录作为包根目录。你的其他资源位于该目录下。

与 JAR 文件不同，WAR 文件可以包含封装的 JAR 文件，它们位于 `WEB-INF/lib` 中。这些目录中 JAR 文件里的所有类对应用程序的类路径（classpath）可用。`/WEB-INF/tags` 和 `/WEB-INF/tld` 目录负责存放 JSP 标签和标签库描述符；你预计将在第 8 章探索标签和标签库的使用。这并不是 Java EE 规范的一部分，但是大多数应用开发者遵循的约定，用于存储国际化（i18n）和本地化（L10n）文件。

你还注意到了两个不同的 `META-INF` 目录的存在。这可能会让一些开发者感到困惑，但如果你记住类路径规则，就可以轻松区分这二者。像 JAR 文件的 `META-INF` 目录一样，根级别的 `/META-INF` 目录包含清单文件（manifest file）。它还包含特定 Web 容器或应用服务器的资源。例如，Apache Tomcat（你将在第 2 章学习）会查找并使用该目录中的上下文文件在 Tomcat 中部署应用程序。这些中没有

![](img/9c2d45f6d547f72cb870b3a991f62ef6_49_0.png)

图 1-2

### 理解基础 Web 应用结构

Java EE 规范的一部分，且支持的文件可能随任何应用服务器或 Web 容器而异。

与 JAR 文件不同，根级别的 `/META-INF` 目录*不在*应用程序的类路径上。你无法使用 `ClassLoader` 获取此目录中的资源。然而，`/WEB-INF/classes/META-INF` 在类路径上。你可以将任何所需的应用程序资源放置在目录目录中，它们可以通过 `ClassLoader` 访问。某些 Java EE 组件指定了属于此目录的文件。例如，Java 持久 API（你将在本书第三部分学习）指定了属于此目录的文件——一个名为 `persistence.xml`，另一个名为 `orm.xml`——它们位于 `/WEB-INF/classes/META-INF`。

大多数在 WAR 内部的文件都可以通过 URL 直接访问。例如，部署到 `http://example.org/foo/` 根目录的 `bar.html` 文件。在没有相反过滤规则的情况下，这适用于应用程序中的所有资源，`/WEB-INF` 和 `/META-INF` 目录除外。这些目录的文件是无法 URL 访问的保护资源。

### 部署描述符

部署描述符是描述 Web 应用并为 Java EE 服务器提供部署和运行指令的元数据。传统上，所有这些元数据来自部署描述符文件 `/WEB-INF/web.xml`。该文件包含 Servlet、监听器、过滤器的定义，以及 JSP 和通用应用的配置选项。Java EE 6 增加了使用注解和 Java 配置 API 配置应用程序的能力。它还引入了 Web 片（fragments）的概念——应用程序中的 JAR 文件可以包含位于 `/META-INF/web-fragment.xml` 部署描述符中的 Servlet、过滤器和监听器。Web 片也可以使用注解和 Java 配置 API。

Java EE 6 对 Web 应用部署的改变增加了组织这一过程的复杂度。为了减轻这种复杂性，你可以配置 Web 片的顺序，以便它们按特定顺序进行扫描和激活。这通过两种方式实现：

- 每个片段的 `web-fragment.xml` 文件可以包含一个 `<ordering>` 元素，使用嵌套的 `<before>` 和 `<after>` 标签来控制哪个 Web 片在其他 Web 片之前。这些标签包含 `<name>` 元素，指定相对于当前片段排序的另一个片段。`<before>` 和 `<after>` 也可以嵌套 `<others>` 元素，指示该片段在未命名的其他片段之前。

- 如果你没有控制特定的 Web 片且无法控制其内容，你仍然可以在应用程序的部署描述符中控制 Web 片的顺序。`/WEB-INF/web.xml` 中的 `<absolute-ordering>` 元素结合嵌套的 `<name>` 和 `<others>` 元素，为封装的片段配置绝对顺序，覆盖片段自带的任何顺序指令。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_50_0.png)

# 第 1 章 介绍 Java 平台版

默认情况下，Servlet 3.0 及更高版本的环境会扫描 Web 应用程序和 Web 片段（web fragments），寻找 Servlet、监听器、过滤器等的 Java EE 应用程序注解配置。你可以通过在需要的根元素 `<web-app>` 或 `<web-fragment>` 中添加属性元数据 `metadata-complete="true"` 来禁用此扫描并禁用注解配置。你还可以通过在部署描述符（deployment descriptor）中添加 `<absolute-ordering />`（可包含任何嵌套元素）来禁用应用程序中的 Web 片段。

在本书的第一部分中，你将学到更多关于 Web 应用程序部署和注解配置的知识。在第二部分中，你将探索容器初始化器（container initializer）以及使用 Java API 进行程序化配置，并了解它如何让 Spring Framework 的引导（bootstrapping）变得更容易且易于测试。

### 类架构

在处理 Java EE Web 应用程序时，理解类加载器（ClassLoader）架构至关重要，这种架构与你在标准 Java SE 应用中熟悉的架构有所不同。在典型的应用程序中，随 Java SE 平台提供的 `java.*` 类加载在一个特殊的根类加载器中，该类加载器无法被覆盖。这是一种安全措施，用于防止恶意代码替换 `String` 类或重新定义 `Boolean.TRUE` 和 `False`。

在该类加载器之后是扩展类加载器（extension ClassLoader），它从 JRE 目录下的扩展 JAR 包中加载类。这形成了一个类加载器层级结构，根节点是所有类的最早祖先。当低级类加载器被请求加载某个类时，它总是首先委托给父类。这个过程一直持续到检查根类加载器。除了根类加载器外，类加载器只有在它的父类加载器未能找到该类时，才会从其 JAR 包集中加载该类。

这种类加载方法使用了“父优先”的类委托模型，尽管它适用于许多类型的应用程序，但对于 Java EE Web 应用程序并不理想。运行 Java EE Web 应用程序的服务器通常极其复杂，许多厂商都会提供自己的实现。服务器可能会使用你的应用程序所需的某些第三方库，但这些库的版本可能冲突。此外，不同的 Web 应用程序可能提供相同第三方库的冲突版本，导致更多问题。为了解决这些问题，你需要一种父优先的类加载器委托模型。

在 Java EE Web 服务器中，每个 Web 应用程序都被分配了一个隔离的类加载器，继承自公共服务器类加载器。通过将应用程序相互隔离，它们无法访问其他类。这不仅消除了类冲突的风险，还作为安全措施，防止 Web 应用程序干扰或损害其他 Web 应用程序。此外，Web 应用程序类加载器（通常）只有在自己无法加载该类时才会请求其父类加载。这就是为什么类加载是最后委托给父类而不是首先，并且优先使用 Web 应用程序类和库而不是服务器使用的类。为了保持捆绑 Java SE 类的保护状态，Web 应用程序类加载器在尝试加载任何类之前仍然会检查根类加载器。尽管在几乎所有情况下这种委托模型对 Web 应用程序更佳，但在某些情况下它并不适用。出于这个原因，符合 Java EE 标准的服务器提供了将委托模型从“自优先”更改为“父优先”的能力。

### 企业归档 (Enterprise Archives)

你已经学习了 WAR 文件，但还有另一种你应该了解的 Java EE 类型：EAR 文件。企业归档（Enterprise Archive）是将 JAR 文件、WAR 文件和配置压缩成单个的可部署归档（ZIP 格式与 JAR 和 WAR 类似）的集合。

1-3 展示了一个 EAR 文件示例。在 WAR 文件中，根目录 `/META-INF` 包含归档清单（manifest），且对应用程序类路径可用。`/META-INF/application.xml` 文件是一个特殊的部署描述符，描述了如何部署 EAR 中包含的各种组件。EAR 根目录下是包含在一个 WAR 文件中的所有 Web 模块，每个模块对应一个。这些 WAR 文件并没有特殊之处；它们具有与独立 WAR 文件完全相同的内容和功能。EAR 还可以包含 JAR 包，供多个模块共享的库。通过 `/META-INF/application.xml` 部署描述符可以包含 Enterprise JavaBeans。这种新的类加载器插入在服务器类加载器和分配给每个模块的 Web 应用程序类加载器之间。这隔离了企业应用程序，但可以使用“自优先”（默认）或“父优先”委托模型，使 EAR 类具有优先级。父优先是 Java EE 规范的特性，大多数仅容器的服务器（如 Tomcat）都不支持它们。

- EnterpriseApplication.ear

	- META-INF
		- application.xml
		- MANIFEST.MF
	- Module1.war
	- Module2.war
	- SharedClasses.jar
	- ThirdParty.jar

![](9c2d45f6d547f2cb870b3a991f62ef0)

### 总结

在本章中，你探索了 Java 平台标准版（SE）和企业版（EE）的历史，并了解了这两个平台在过去 19 年中是如何共同发展的。你简要介绍了本书涵盖的主题——Servlet、过滤器、监听器等——了解了 Web 应用程序归档和企业归档的结构，以及它们如何作为传输和部署 Java EE 应用程序的容器。

本书剩余部分将更详细地探讨这些主题，回答你在阅读这几页后可能的许多问题。在第 2 章中，你将仔细查看应用程序服务器和容器、它们是什么以及如何根据需求选择一个。你还将学习如何安装和使用 Tomcat 来完成书中的示例。

# 第 2 章 使用容器

本章内容

- 选择容器
- 在你的机器上安装 Tomcat
- 在 Tomcat 中部署和卸载应用程序
- 在 IntelliJ IDEA 中调试 Tomcat
- 在 Eclipse 中调试 Tomcat

## 第 2 章 使用容器

尽管 Java EE 规范包含许多较小的子规范，但大多数 Web 容器仅实现了 Servlet、JSP 和 JSTL 规范。这与实现了整个 Java EE 规范的全功能 Java 服务器不同。每个应用服务器都包含一个 Web 容器，负责管理 Servlet 的生命周期、将 URL 映射到 Servlet 代码、响应 HTTP 请求以及管理过滤器链。然而，当不需要 Java EE 的完整规范时，独立的 Web 容器通常更轻量且更易于使用。

选择一个 Web 容器（或者说选择一个应用服务器）是一项需要根据项目需求进行仔细研究和考虑的任务。在选择 Web 容器方面，你有许多选择，每种选择都有其优势和挑战。你可以使用多种 Web 容器。例如，你可能决定在开发人员的机器上使用 Apache Tomcat 进行本地测试，而在生产环境中使用 GlassFish。或者，你可能会编写一个客户部署在自己服务器上的应用程序，在这种情况下，你可能希望在许多不同的服务器和 Web 容器上进行测试。

在本节中，你将学习常见的 Web 容器和应用服务器，在后续章节中，你将仔细查看你在本书其余部分使用的那一个。

### Apache Tomcat

Apache Tomcat 是目前最常见、最流行的 Web 容器。Sun Microsystems 的软件工程师最初创建此容器作为 Java Web Server，它是 Java EE 规范的原始参考实现。Sun 在 1999 年将其捐赠给了 Apache 软件基金会，随后更名为 Tomcat，并最终变为 Apache Tomcat。有趣的是，Apache 对 Tomcat 的演进导致了 Apache Ant 工具的发展，该工具被数以千计的商业和开源项目所使用。

Tomcat 的主要优势是其占用空间小、配置简单以及悠久的社区参与历史。通常，开发者可以在 5 到 10 分钟内（包括下载时间）完成并运行一个功能完备的 Tomcat 安装。Tomcat 开箱即用，极少的配置即可在负载负载、高可用性的生产环境中运行良好。你可以创建大型 Tomcat 容器来可靠地处理海量流量。由于其简单性和轻量级特性，Tomcat 常用于商业环境。然而，在配置服务器方面，Tomcat 缺乏比任何竞争对手更复杂的 Web 管理界面。Tomcat 仅为基础任务（如部署应用程序）提供了一个简单的界面。对于进一步的配置，管理员必须操作一组 XML 和 Java 属性文件。此外，它不是一个完整的应用服务器，缺少许多 Java EE 组件，如 Java Persistence API、Bean Validation API 和 Java Message Service。

正如你所想象的，这个 Tomcat 非常适合许多任务，但也让开发更复杂的应用程序具有挑战性，有时是不可能的。如果你喜欢 Tomcat 但需要一个完整的 Java EE 应用服务器，可以转向 Apache TomEE，它构建在 Tomcat 之上但提供了所有 Java EE 组件的完整实现。由于构建在 Tomcat 之上，它拥有 Tomcat 社区的强大支持和十多年的测试积累。Apache 还提供了 Geronimo，另一个开源 Java EE 应用服务器。

### 选择 Web 容器

> **注意** TomEE 和 Geronimo 都是 Oracle 认证的 Java EE 应用服务器，这意味着它们已通过验证，符合 Java EE 规范的所有方面。由于 Tomcat 仅是一个 Web 容器，它没有此类认证。然而，它庞大的用户群和活跃的社区确保了它准确地实现了所提供的 Java EE 组件。

Tomcat 提供了 Servlet、Java Server Pages (JSP)、Java 统一表达式语言 (EL) 和 WebSocket 规范的实现。表 2-1 列出了几个 Tomcat 版本及其实现的规范。目前仅支持 Tomcat 6、7 和 8。版本 3.3、4.1 和 5.5 在多年前已停止维护。你可以在网站上阅读更多关于 Apache Tomcat 的信息。

### 表 2-1：Tomcat 版本及其规范

| Tomcat 版本 | JAVA EE* | SERVLET | JSP | EL | WEBSOCKET | 最低 JAVA EE 版本 |
| --- | --- | --- | --- | --- | --- | --- |
| 3.3.x | 1.2 | 2.2 | 1.1 | | | 1.1 |
| 4.1.x | 1.3 | 2.3 | 1.2 | | | 1.3 |
| 5.5.x | 1.4 | 2.4 | 2.0 | | | 1.4 |
| 6.0.x | 5 | 2.5 | 2.1 | 2 | | 5.0 |
| 7.0.x | 6 | 3.0 | 2.2 | 2.2 | | 6 |
| 8.0.x | 7 | 3.1 | 2.3 | 3 | 1.0 | 7 |

* Java EE 列仅指示 Java EE 版本：Tomcat 不是应用服务器，也不实现 Java EE。列中的连字符表示该 Tomcat 版本未实现该特定规范。

## GlassFish

GlassFish Server 是一个开源且商业化的全功能 Java EE 服务器实现。它提供了 Java EE 规范中的所有功能，包括 Web 容器，并且目前是 Java EE 规范的参考实现。它的 Web 容器实际上是 Apache Tomcat 的派生版本；然而，自 Tomcat 为 GlassFish 形成以来，它已经发生了巨大的演变，如今具有很高的识别度。GlassFish 的开源版本提供社区支持，而商业版的 Oracle GlassFish 则通过 Oracle 公司提供付费的商业支持。Oracle 仅为 Java EE 7 提供商业支持。从 Java EE 8 开始，GlassFish 将不再包含商业支持选项。

GlassFish 的优势之一是其强大的管理界面。GlassFish 的管理界面可以用于配置、部署和监控应用程序。GlassFish 的管理界面还允许通过命令行进行操作。GlassFish 在 2006 年 5 月发布的第一个版本是 Java EE 5 的实现。2007 年 9 月发布的 2.0 版本增加了集群功能。2009 年 12 月发布的 3.0 版本是 Java EE 6 的参考实现，包含了多项改进。2011 年 7 月发布的 3.1 版本引入了某些特性，但最低仍要求 Java SE 6。2013 年 6 月发布的 4.0 版本是 Java EE 7 的实现，最低要求 Java SE 7。

你可以在网站上了解更多关于 GlassFish 的信息。

## JBoss 和 WildFly



# Red Hat 的开源应用服务器（JBoss AS）

Red Hat 的开源应用服务器（JBoss AS）在 2013 年初是仅次于 Tomcat 的第二流行 Java EE 服务器。历史上，JBoss 一直是带有 JavaBeans 等其他功能的 Web 容器。在 2012 年，它成为了一个完整的 Java EE 应用服务器。随着时间的推移，JBoss 的名称与 Apache 社区的一些项目重名，导致了混淆。

- JBoss AS 4.0.x 到 4.2.x 版本基于 Tomcat 5 构建，并支持 Java EE 1.4 特性。
- 5.0 版本引入了 Java EE 5 支持和全新的容器。
- 5.1 版本包含了某些 Java EE 6 特性的早期实现（尽管它仍然是 Java EE 5 应用服务器）。
- 6.0 版本实现了 Java EE Web Profile，但未寻求获得 Java EE 6 应用服务器认证。
- JBoss AS 7.0 代表了该产品的完全重写，以大幅减少其占用空间并提高性能，但也仅支持 Java EE 6 Web Profile。
- 直到 JBoss AS 7.1，它才成为全应用服务器，在 Java EE 6 发布 2 年后获得了 Java EE 6 认证。
- WildFly 8.0 是在 2014 年初发布的 Java EE 7 应用服务器，最低要求 Java SE 7。

你可以在 JBoss 网站查找并下载 JBoss AS 7.1 及之前的版本，可以在 WildFly 网站查找 WildFly 8.0。

## 其他容器和应用服务器

还有许多其他 Web 容器，例如 `Jetty` 和 `Tiny`，以及开源的全功能 Java EE 应用服务器，如 `JOnAS`、`Resin`、`Caucho` 和 `Hydra`。许多许多商业应用服务器，其中 `Oracle WebLogic` 和 `IBM WebSphere` 是最流行的。表 2-2 显示了其中一些版本以及支持 Java EE 规范的版本。

### 表 2-2：容器与应用服务器版本

| 服务器 | J2EE 1.2 | J2EE 1.3 | J2EE 1.4 | JAVA EE 5 | JAVA EE 6 | JAVA EE 7 |
|---|---|---|---|---|---|---|
| Jetty* | 3.x | 4.x | 5.x | 6.x: J2SE 1.4<br>7.x: Java SE 5.0 | 8.x: Java SE 6<br>9.0.x Java SE 7 | 9.1.x |
| WebLogic | 6.x | 7.x-8.x | 9.x | 10.x: Java SE 6<br>11g PS5: Java SE 7 | 12c | 12.1** |
| WebSphere | 4.x | 5.x | 6.x | 7.x | 8.x: Java SE 6<br>8.5:x Java SE 7 | 9.** |

* 仅限容器；不是完整的应用程序
** 这些是推测的版本 —— Oracle 和 IBM 尚未正式宣布对 Java EE 7 的支持。

每个容器或应用服务器都有其优缺点。选择应用服务器的任务无法在一个章节中涵盖，且超出了本书的范围。必须理解你组织项目的需求，并选择满足这些需求的正确容器或应用服务器。必须考虑运营预算，因为商业应用服务器的许可费用通常极高。所有因素都会影响你的决策，你可能会选择未在书中列出的服务器。

## 为什么你将在本书中使用 Tomcat

Apache Tomcat（在本书的其余部分简称为 Tomcat）的许多优势已经得到了概述。对于本书而言，或许最重要的优点可能是开发者可以轻松地开始使用 Tomcat。到目前为止，Tomcat 比任何其他 Web 容器都更易于快速运行，并且它提供了完成本书书中示例所需的所有功能。此外，所有主要的 Java IDE 都提供了运行、部署在 Tomcat 上运行以及调试 Tomcat 的工具，这使得你开发应用程序变得更加容易。

尽管某些开发者倾向于使用其他容器——而且只要具备正确的知识，几乎任何 Web 容器在开发机器上都能很好工作——但很难反对 Tomcat。在本书中使用 Tomcat，你可以专注于代码和开发实践，几乎不关注对容器的管理。本章的其余部分将帮助你在机器上安装并设置 Tomcat。它还介绍了如何使用 Tomcat 管理器部署和卸载应用程序，以及在你的 Java IDE 中调试 Tomcat。

## 在你的机器上安装 Tomcat

在你的机器上安装 Tomcat 之前，你需要从 Tomcat 项目网站下载它。访问 Tomcat 8.0 下载页面，向下滚动到“Binary Distributions”（二进制发行版）部分。该页面上有许多下载内容，你为书中唯一需要的位于“Core”（核心）标题下。作为 Windows 用户，你关注的两个下载项是“32-bit/64-bit Windows Installer”（适用于任何体系架构）以及“32-bit Windows zip”或“64-bit Windows zip”（取决于你的机器架构）。如果你在 Linux、Mac OS X 或其他操作系统上运行，你需要非 Windows 的 zip 包，它仅称为“zip”。

### 安装为 Windows 服务

许多开发者想要将 Tomcat 安装为 Windows 服务。这有几个优势，特别是在质量保证（QA）或生产环境中。它让 JVM 内存和资源的管理变得更容易，并且在 Windows 启动时自动启动 Tomcat。然而，在开发环境中，将 Tomcat 安装为服务可能会有一些缺点。这种技术只安装服务，而不安装用于从命令行运行 Tomcat 的命令行脚本。大多数 IDE 都使用这些命令行脚本从 IDE 运行和调试 Tomcat。你也可以通过下载“32-bit/64-bit Windows Service Installer”将 Tomcat 安装为服务，但你还需要下载“Windows zip”以便从你的 IDE 运行 Tomcat。

本书不涵盖将 Tomcat 安装为服务，因为你通常在生产环境或 QA 环境中才这样做。如果你想进一步探索这一点，Tomcat 网站上的文档非常有帮助。当然，如果你没有使用 Windows，则 Windows 安装程序对你将毫无用。在其他操作系统中也有自动启动 Tomcat 的方法，但它们都超本书的范围。

### 安装为命令行应用程序

大多数应用开发者需要作为命令行应用程序运行 Tomcat，通常是从他们的 IDE 运行。要实现这一点，请遵循以下步骤：

1. 从 Tomcat 8.0 下载对应架构的 Windows zip（如果你使用其他版本）或非 Windows 的 zip（如果你使用其他版本），并解压目录。
2. 将 Tomcat 目录的内容放在本地机器的 `C:\Program Files\Apache Software Foundation\Tomcat` 文件夹中（或你操作系统中相应的服务器目录）。例如，`webapps` 目录现在应该位于 `C:\Program Files\Apache Software Foundation\Tomcat\.webapps`。
3. 如果你使用 Windows 7 或更高版本，你需要更改权限以使 IDE 能够访问 Tomcat。右键点击 `C:\Program Files` 中的 Apache Software Foundation 目录并点击“属性”。在“安全”选项卡上，点击“编辑”按钮。添加你的用户或 Users 组，并赋予他们对目录的完全控制权限。
4. 为了首次配置 Tomcat，首先用你喜欢的文本编辑器打开 `config/tomcat-users.xml` 文件。在 `<tomcat-users>` 和 `</tomcat-users>` XML 标签之间放置以下标签：

```xml
<user username="admin" password="admin" roles="manager-gui,admin-gui" />
```

> **警告** 这配置了一个你可以用于登录 Tomcat Web 管理界面的管理员用户。当然，这个用户名和密码组合非常不安全，绝不应用于生产或面向公众的服务器。然而，对于在本地机器上测试，它是足够的。

5. 打开 `conf/web.xml` 文件。在文件中搜索文本 `org.apache.jasper.servlet JspServlet`。在包含此文本的标签下方有两个 `<init-param>` 标签。你将在下一节学习 Servlet 初始化参数，但现在在初始化参数之间添加以下初始化参数：

```xml
<init-param>
  <param-name>compilerSourceVM</param-name>
  <param-value>1.8</param-value>
</init-param>
<init-param>
  <param-name>compilerTargetVM</param-name>
  <param-value>1.8</param-value>
</init-param>
```

默认情况下，Tomcat 8.0 即使运行在 Java SE 8 上也会使用 Java SE 6 语言支持编译 JSP。这个新的 Servlet 初始化指示 Tomcat 使用 Java SE 8 特性编译 JSP 文件。

6. 在完成这些更改并保存后，你应该已经准备好启动 Tomcat 并确保它运行正常。打开命令提示符并将目录更改到 Tomcat 目录（`C:\Program Files\ Apache Software Foundation\Tomcat8.0`）。
7. 输入命令 `%JAVA_HOME%`（非 Windows 操作系统输入 `$JAVA_HOME`）并按回车，检查 `JAVA_HOME` 环境变量是否正确设置为你的 Java 开发工具包 (JDK) 目录。如果不是，请配置环境变量，并注销重新登录（见下文）。
8. 输入 `bin/startup.bat`（如果不使用 Windows 则输入 `bin/startup.sh`）并按回车。打开一个控制窗口显示运行中的 Tomcat 进程的输出。几秒后，你应该会在控制窗口看到“INFO[main] org.apache.catalina.startup.Catalina.Server startup in 1827 ms”或类似的消息。此 Tomcat 已正常启动。

> **注意** 启动时，Tomcat 最初查找 `JRE_HOME` 环境变量，如果存在则使用它。如果不存在，它会查找 `JAVA_HOME` 变量。如果两个者都未设置，Tomcat 将无法启动。然而，为了调试 Tomcat，你必须设置 `JAVA_HOME`，因此最好现在就配置它。

9. 打开你喜欢的 Web 浏览器并导航到 `http://localhost:8080/`。你应该看到一个页面看起来 Tomcat 正在运行且 JSP 正在使用 Java SE 8 正常编译。如果此页面没有出现或遇到错误，在 Java 控制台中，你可能需要检查前面的步骤，并可能查阅 Tomcat 文档。

![Tomcat 运行页面](img/9c2d45f6d547f72cb870b3a991f62ef6_61_0.png)

当你使用 Tomcat 时，可以通过在 Tomcat 8 目录下运行 `shutdown.bat`（或 `bin/shutdown.sh`）来停止它。Java 控制台窗口将会关闭，Tomcat 也会停止。然而，不要等它；接下来我们将探索在 Tomcat 中部署和卸载应用程序。（如果你已经关闭了 Tomcat，不用担心。它很容易重新启动。）

> Tomcat 8.0 的早期版本不支持为 Java 8 编译 JSP。如果你在 Java 控制台中看到 "WARNING: Unknown source VM 1.8 ignored" 或类似的内容，那么你就知道对于你使用的版本来说是这种情况。如果是这样，你将需要完成“配置自定义 JSP 编译器”的步骤。

## 配置自定义 JSP 编译器

Tomcat 附带了 Eclipse JDT 编译器，用于编译 Web 应用程序中的 Java Pages 文件。（你将在第 4 章学习更多关于 JSP 文件及其如何编译的知识。）这使得 Tomcat 可以在不需要安装 JDK 的情况下正常运行。使用 Eclipse 编译器，你只需要安装简单的 Java 运行时环境 (JRE)。因为 JSPs 通常很简单，Eclipse 编译器对于任何 Tomcat 环境通常都足够胜任。但在某些情况下，你可能不想使用 Eclipse 编译器。也许你现在 Eclipse 编译器中发现了一个 bug，导致其中一个 JSP 无法编译。或者，如果发布了新的 Java 版本带有你希望在 JSP 中使用的特性，Eclipse 可能需要一些时间才能拥有兼容的编译器。无论出于什么原因，你都可以轻松地配置 Tomcat 使用 JDK 编译器而不是 Eclipse。

1. 重新打开 Tomcat 的 `conf/web.xml` 文件并再次编辑 Servlet。
2. 添加以下初始化参数，该参数告诉 Servlet 使用 Apache Ant 配合 JDK 编译器来编译 JSP，而不是使用 Eclipse 编译器。

```xml
<init-param>
  <param-name>compiler</param-name>
  <param-value>modern</param-value>
</init-param>
```

3. Tomcat 没有直接使用 JDK 编译器的方法，因此你必须在系统中安装最新版本的 Ant。你还需要将 JDK 的 `tools.jar` 文件以及 Ant 的 `ant.jar` 和 `ant-launcher.jar` 文件添加到你的类路径中。这样做最简单的方法是创建一个 `bin\setenv.bat` 文件，并向其中添加以下代码（忽略此处的换行），根据你的系统需要替换路径：

```bat
set CLASSPATH=%path/to/jdk/lib/tools.jar;C:\path\to\ant\lib\ant.jar;C:\path\to\ant\lib\ant-launcher.jar
```

当然，这只适用于 Windows 机器。对于非 Windows 环境，你应该创建一个 `bin/setenv.sh` 文件，并包含以下内容，根据你的系统需要替换路径：

```sh
export CLASSPATH=/path/to/jdk/lib/tools.jar:/path/to/ant/lib/ant.jar:/path/to/ant/lib/ant-launcher.jar
```

当使用自定义 JSP 配置运行 Tomcat 时，你应该仔细观察日志中的输出。如果 Tomcat 找不到 Ant 或找不到 JDK 编译器，Tomcat 将自动回退到 Eclipse 编译器并在日志中输出警告。

## 在 Tomcat 中部署和卸载应用程序

在本节中，你将学习如何在 Tomcat 中部署和卸载 Java EE 应用程序。你有两种方法来实现此目标：

- 手动将应用程序放入 `webapps` 目录
- 使用 Tomcat manager 应用程序

如果你还没有这样做，应该从 wrox.com 下载站的第 2 章下载 `sample-deployment.war` 应用程序。你应该使用它来练习部署和卸载。

### 执行手动部署和卸载

使用 Tomcat 手动部署应用程序非常简单——只需将 `sample-deployment.war` 文件放置在 Tomcat 的 `webapps` 目录中。如果 Tomcat 正在运行，几秒钟后 Tomcat 就会自动将应用程序文件解压到一个同名但去掉了扩展名的目录中。如果 Tomcat 没有运行，你可以启动它，应用程序将在 Tomcat 启动时解压。当应用程序解压完成后，打开浏览器并导航到 `http://localhost:8080/sample-deployment/`。你应该看到一个类似于图 2-2 的页面。这意味着应用程序已成功部署。

![部署成功页面](img/9c2d45f6d547f72cb870b3a991f62ef6_63_0.png)

图 2-2

卸载应用程序只需反转该过程。删除 `sample-deployment.war` 文件并等待片刻。当 Tomcat 检测到文件被删除时，它会卸载应用程序并删除目录，应用程序将无法通过浏览器访问。你不需要关闭 Tomcat。

### 使用 Tomcat Manager

你可以使用 manager 部署应用程序。要这样做，请遵循以下步骤：

1. 打开浏览器并导航到 `http://localhost:8080/manager`。
2. 当提示输入用户名和密码时，输入 admin 以及密码（参考 `conf/users.xml`）。

## 在 IDE 中调试 Tomcat

作为一名 EE 开发人员，你拥有的最重要的技能之一是在 Tomcat 中部署和调试应用程序的能力。本节涵盖了使用 IntelliJ 和 Eclipse 设置、运行和调试应用程序。在本书的剩余部分中，针对特定 IDE 的指令很少。在继续之前，请确保你熟悉并习惯在 Tomcat 中部署和调试。

### 在 IntelliJ 中设置 Tomcat 8.0

首先，你需要在 IntelliJ 的应用服务器列表中配置 Tomcat。

1. 打开 IntelliJ 的 IDE 设置。当项目打开时，可以前往 `File > Settings`，或点击工具栏上的 Settings 图标（此处所示），或按 `Ctrl + Alt + S`。如果没有打开项目，可以点击 Configure 然后点击 Settings 按钮。
2. 在 Settings 对话框的左窗格中，点击 IDE Settings 下的 Application Servers。最初你没有配置应用服务器。



### 向项目添加 Tomcat 配置

在创建了项目并准备好从 IntelliJ 部署它之后，你需要为项目添加 Tomcat 运行/调试配置。

1. 点击工具栏上的运行/调试配置图标（向下箭头），然后点击 **Edit Configurations**（编辑配置）。

   ![](img/9c2d45f6d547f72cb870b3a991f62ef6_67_0.png)

2. 在弹出的对话框中，点击绿色的加号图标，滚动到 **Add New Configuration**（添加新配置）菜单的底部，悬停在 **Tomcat Server** 上，并点击 **Local**（本地）。这将创建一个用于在本地 Tomcat 上运行你的项目的运行/调试配置，如图 2-7 所示。

3. 如果 **Tomcat 8.0** 是你已添加到 IntelliJ 的唯一应用服务器，它会被自动选择为运行/调试配置的应用服务器。如果你配置了其他应用服务器，可能会选中其中一个，这时你需要点击 **Application server**（应用服务器）下拉列表并选择 **Tomcat 8.0**。

4. 为运行配置命名一个有意义的名称。在图 2-7 以及你为本书下载的所有示例 IntelliJ 项目中，运行配置的名称与其使用的应用服务器一样，名为 **Tomcat 8.0**。

5. 你可能会看到一个关于 artifacts 已标记为部署的警告。修复这个问题非常简单。点击 **Deployment**（部署）选项卡，点击 **Deploy at the server startup**（在服务器启动时部署）标题下的绿色加号图标。点击 **Artifact**（产物），然后点击 **exploded file artifact**（解压缩文件产物）。点击 **OK**。将产物部署的 **Application context**（应用上下文）名称更改为你部署到的服务器相对 URL，如图 2-8 所示。

6. 点击 **Apply** 然后点击 **OK** 以保存运行/调试配置并关闭对话框。

你可以从 wrox.com 下载站点下载 **Sample-Debug-IntelliJ** 项目，以查看已配置好在本地 Tomcat 8.0 应用服务器上运行的示例 Web 应用。（不过，你仍然需要在 IntelliJ 的 IDE 设置中设置你的 Tomcat 8.0 安装）。

### 从 IDE 调试 Tomcat

![](img/9c2d45f6d547f72cb870b3a991f62ef6_68_0.png)

图 2-7

![](img/9c2d45f6d547f72cb870b3a991f62ef6_68_1.png)

图 2-8

### 启动应用程序并命中断点

现在你已经在 IntelliJ 中设置了 Tomcat 并配置了 IntelliJ 在 Tomcat 中运行，你已经准备好在 IDE 中启动并调试应用程序了。

1. 从 wrox.com 下载站点下载 **Sample-Debug-IntelliJ** 项目，并用 IntelliJ IDEA 打开它。

2. 确保其运行/调试配置已正确配置为使用你的本地 **Tomcat 8.0** 应用服务器。在尝试启动为本书下载的每个示例项目之前，你都应该执行此检查。

3. 打开后，你应该能看到类似图 2-9 的界面，其中为 `index.jsp` 留了两个断点。

4. 点击工具栏上的 **Debug** 图标（图 2-9 中由鼠标指针高亮）并按下 `Shift+F9` 以调试模式启动你的应用程序。IntelliJ 将启动你的默认浏览器，你应该会立即命中 `index.jsp` 中的断点。

   ![](img/9c2d45f6d547f72cb870b3a991f62ef6_69_0.png)

你应该能看到图 2-2 中的网页，这表示你的应用程序已成功部署。

> **注意**：IntelliJ 在启动浏览器之前实际上可能会访问 `http://localhost:8080/sample-debug/`。这样做是为了确保你的应用程序已正确部署。如果是这样，你将命中两次断点——一次是 IntelliJ 访问应用程序，另一次是你的浏览器打开并访问应用程序。

### 使用 Eclipse

在 Eclipse 中使用 Tomcat 与在 IntelliJ IDEA 中使用 Tomcat 有某些相似之处，但也有许多不同之处，且界面看起来非常不同。相同的基本流程仍然适用——你需要在 Eclipse 的全局设置中设置 Tomcat，为项目配置它，并启动和调试项目。在本节的最后部分，你将学习如何从 Eclipse 使用 Tomcat，以防你选择它作为你的 IDE。

> **警告**：如引言所述，截至本书出版之日，Eclipse 不支持 Java SE 8、Java EE 7 或 Tomcat 8.0。你必须等到 2014 年 6 月发布 Eclipse 4.4 Luna 才能实现对这些技术的支持。因此，本节中的 Eclipse 指令和图表可能不完全准确，你应该根据 Eclipse Luna 发布版本的更改做出相应响应。

### 在 Eclipse 中设置 Tomcat 8.0

首先，你必须在 Eclipse 的全局偏好中将 Tomcat 8.0 配置为运行时环境。按照以下步骤操作：

1. 打开 **Eclipse for Java EE Developers**，进入 **Window > Preferences**（窗口 > 偏好）。

2. 在弹出的对话框中，展开 **Server**（服务器）。

3. 点击 **Add...**（添加...）。

4. 在 **New Server**（新建服务器）对话框中，选择 **Tomcat Server** 并点击 **Next**。

5. 在下一个屏幕上，选择 **Tomcat 8.0**。

6. 点击 **Browse**（浏览）并导航到你的 Tomcat 8.0 目录（例如 `C:\Program Files\Apache Software Foundation\Tomcat 8.0`）。

7. 在 **JRE** 下拉列表中选择你的 Java JRE。

8. 点击 **Next**。

9. 为服务器命名。

10. 此时你应该看到类似图 2-10 的界面。

11. 点击 **Finish**（完成）将 Tomcat 添加到你的服务器列表。点击 **OK** 关闭对话框。

现在你可以在 Eclipse 中使用 Tomcat 了。

另一个需要注意的是，默认情况下，Eclipse 使用内置浏览器打开 Web 应用。要更改它，进入 **Web browser** 并选择其他。**Internal Web Browser**（内置浏览器）在大多数情况下就足够，但你可以随时更改。

### 在项目中使用 Tomcat 服务器

在 Eclipse 中创建新项目时，你必须选择配置好的运行时。为此，请按以下步骤操作：

1. 右键点击项目并进入 **Properties**（属性）。

2. 选择 **Web Project Settings**（Web 项目设置）。

3. 更新 **Context root** 字段（假设你在创建项目时没有配置它）。

4. 点击 **Apply**（应用）保存更改。

5. 右键点击项目并进入 **Run As**（运行）。

6. 选择 **Run on Server**（在服务器上运行）。

7. 在 **Servers** 对话框中，选择你的 **Tomcat 8.0** 服务器。

8. 点击 **Finish**（完成）。

应用程序将启动，内置浏览器将打开网页。要进行调试，右键点击项目并进入 **Debug As > Debug on Server**（调试 > 在服务器上调试）。

4. 点击工具栏上的调试图标（如图 2-13 中的鼠标指针高亮所示）以在调试模式编译并启动你的应用程序。Eclipse 应该启动配置好的浏览器，你应该会立即命中 `index.jsp` 中的断点。你可以再次看到图 2-2 中的网页，这表明你的应用程序已成功部署。

5. 若要从断点继续，请点击 Eclipse 工具栏上的继续图标（显示在侧边栏）。

> **警告**：当从 Eclipse 运行 Tomcat 时，Eclipse 会覆盖你创建的任何用于配置高级 JSP 编译的自定义 `confenv.bat` 或 `setenv.sh` 文件。如果你不想使用 Eclipse JDT 编译器来编译你的 JSPs，则你需要将此文件中的 `CLASSPATH` 配置添加到其他 Tomcat 配置中。请查阅 Tomcat 文档以确定放置此配置的合适文件。

> **注意**：你可能已经注意到 Eclipse 中的 JSP 只有一个断点，而 IntelliJ IDEA 中的 JSP 有两个断点。Eclipse 的 JSP 调试器比 IDEA 的 JSP 调试器限制得多，因此在 Eclipse 中无法在此 JSP 的第 7 行设置断点。

### 总结

在本章中，你学习了 Java EE 应用服务器和 Web 容器，并探索了它们的几种流行实现。你在本地机器上安装了 Tomcat 8.0，配置了 JSP 编译，从命令行启动了它，并实验了在 Tomcat 中部署和卸载应用程序。最后，你学习了如何使用 IntelliJ IDEA 和 Eclipse IDE for Java EE Developers 配置并调试你的应用程序。

在下一章中，你将创建 Servlets 并学习 Java EE Web 应用程序是如何工作的。

## 3 编写你的第一个 Servlet

本章内容

- 创建 Servlet 类
- 为部署配置 Servlet
- 理解 `doGet()`、`doPost()` 等方法
- 使用参数并接受表单提交
- 使用初始化参数配置你的应用程序
- 从表单上传文件
- 使你的应用程序多线程安全

本章 WROX.COM 代码下载

你可以在 www.wrox.com/go/javaforwebbapps 的 "Download Code" 标签页上找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Hello-World 项目
- Hello-User 项目
- Customer-Support-v1 项目

本章的新 Maven 依赖

在本章中，你将需要第一个 Maven 依赖，如下代码所示。你将在书中后的每个章节中都使用此依赖。

```xml
<dependency>
  <groupId>javax.servlet</groupId>
  <artifactId>javax.servlet-api</artifactId>
  <version>3.1.0</version>
  <scope>provided</scope>
</dependency>
```

### Maven

在上一章中，你已经熟悉了应用服务器和 Web 容器，并学会了如何从 Java IDE 运行、部署和调试 Apache Tomcat 8.0。在本章中，你将通过探索 Servlets 世界开始构建 Web 应用程序。在本章及本书的其余部分，你将不断更改和改进这些应用程序，并将它们部署到 Tomcat 中进行测试和调试。

### 创建 Servlet 类

在 Java 平台版（Enterprise Edition）中，Servlet 是接收并响应来自终端用户请求的对象。Java EE API 规范定义 Servlet 如下：

> Servlet 是一个运行在 Web 服务器内的小型 Java 程序。Servlet 接收并响应来自 Web 客户端的请求，通常通过 HTTP（超文本传输协议）。
>
> http://docs.oracle.com/java/7/api/javax/servlet/Servlet.html

Servlets 是任何应用程序中的核心类，它们是唯一执行响应请求工作或将该工作委托给应用程序其他部分的类。除非某些请求被提前终止（在第 9 章中讨论），否则发送你应用程序的每个请求都会通过 Servlet。运行你应用程序的容器将有一个或多个内置的 Servlet。这些 Servlet 处理 `HttpServlet` 页面、显示目录列表（如果你启用了它们）以及访问资源（如 HTML 页面和图形）。你暂时不需要担心这些 Servlet（在某些情况下，永远都不需要）。在本章中，你将学习如何编写和配置构成你应用程序的自定义 Servlet。

每个 Servlet 都实现了 `Servlet` 接口，但通常不是直接实现。`Servlet` 接口包含初始化和销毁请求的方法。然而，对于任何类型的请求，都会调用 `service` 方法，即使它不是 HTTP 请求（理论上，假设你的 Web 容器支持此类请求）。例如，可能会向 Java EE 添加新的 Servlet 以支持文件传输协议（FTP）。因此，有各种 Servlet 类可供你扩展。截至 Java EE 7，目前支持的协议只有 HTTP。

### 要扩展什么

在所有情况下，Servlet 都继承自 `javax.servlet.GenericServlet`。`GenericServlet` 仍然是一个协议无关的 Servlet，只有一个抽象的 `service` 方法，但它包含了几个辅助方法用于日志记录和获取有关应用程序和 Servlet 配置的信息（比“配置 Servlet 以部署”部分中的更多）。

为了响应特定的 HTTP 请求，`javax.servlet.http.HttpServlet` 继承自 `GenericServlet` 并实现了 `service` 方法以仅接受 HTTP 请求。然后，它为对应每个 HTTP 方法类型提供了空实现，如表 3-1 所示。

#### 表 3-1：HTTP 方法类型的空实现

| 方法 | Servlet 方法 | 目的 |
| --- | --- | --- |
| GET | `doGet()` | 获取指定 URL 处的资源 |
| HEAD | `doHead()` | 与 GET 相同，但仅返回头部 |
| POST | `doPost()` | 通常用于 Web 表单提交 |
| PUT | `doPut()` | 存储提供的实体 |
| DELETE | `doDelete()` | 删除由 URL 标识的资源 |
| OPTIONS | `doOptions()` | 返回允许的 HTTP 方法 |
| TRACE | `doTrace()` | 用于诊断目的 |

> **注意**：大多数程序员熟悉 GET 和 POST 方法并在大部分时间使用它们。如果你熟悉各种 HTTP 方法或想了解更多，现在是点击 http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html 查看 RFC-2616 方法定义的时候。

在没有异常的情况下，你的 Servlet 将始终继承 `HttpServlet`。它提供了你所需的工具来选择性地接受和响应不同类型的请求，其方法接受 `javax.servlet.http.HttpServletRequest` 参数。

为了按照此顺序编译，你的类路径中需要 Java EE 库。这就是第一页列出的 Maven 的作用。

这种形式，你的 Servlet 已经准备好接受任何请求并响应 405。这就是你控制响应的 HTTP 方法的方式：任何未重写的 Servlet 方法将通过 405 响应。因此，首先创建一个扩展自 `HttpServlet` 的类：

```java
package com.xxx;

import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

public class HelloServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        response.getWriter().println("Hello, World!");
    }
}
```

现在你的 Servlet 准备好响应 GET 请求并在响应体中返回纯文本响应 "Hello, World!"。这段代码非常直观。在 `response` 上调用 `getWriter()` 返回一个 `java.io.PrintWriter`，这是一个向输出流写入文本的常用 Java 类。接下来，代码调用 `PrintWriter` 的 `println()` 方法将 "Hello, World!" 写入输出流。注意，你不需要担心原始 HTTP 请求或响应的任何细节。Web 容器负责解释请求并从套接字读取头部和参数。在你方法返回后，它负责格式化响应头部和正文并写回套接字。

> **注意**：注意你没有调用从响应获取的 `PrintWriter` 的 `close()` 方法。通常情况下，在 Java 中，你只需要对你创建的资源负责。Web 容器创建了这个资源，因此它负责关闭它。即使你将实例赋值给局部变量并对其调用了多个方法，情况依然如此。

### 使用初始化方法和销毁方法



# 第 3 章 编写你的第一个 Servlet

在你运行第一个 Servlet 时，可能应该了解一下 `init` 和 `destroy` 方法。当 Web 容器启动一个 Servlet 时，它会调用该 Servlet 的 `init` 方法。这有时（但并非总是）是在应用部署时发生的。（你可以在下一节中学习如何控制这一点。）稍后当 Web 容器关闭时，它会调用 Servlet 的 `destroy` 方法。这些方法与 Java 构造函数和终结器（finalizer）不同，它们不会与构造函数和终结器同时调用。通常，这些方法什么都不做，但你可以重写它们来执行某些操作：

```java
@Override
public void init() throws ServletException {
    System.out.println("Servlet " + this.getServletName() + " has started.");
}
```

```java
@Override
public void destroy() {
    System.out.println("Servlet " + this.getServletName() + " has stopped.");
}
```

> **注意** 你应该知道另一个 `init` 方法接受一个类型为 `javax.servlet.Config` 的参数。该方法在 Servlet 接口中定义，而 `GenericServlet` 负责为你实现该方法，然后调用前面代码中重写的无参数重载 `init` 方法。虽然你可以重写该方法，但如果你忘记调用 `super.init(servletConfig)`，Servlet 可能无法正确初始化。你可以使用这两个方法方法做很多事情。更重要的是，`init` 在 Servlet 创建之后但在响应第一个请求之前被调用。与调用构造函数时不同，在调用此时，所有属性都已设置在 Servlet 上，这使得你能够访问到 `ServletConfig` 和 `javax.servlet.ServletContext` 对象。（你可以在“使用初始化参数配置你的应用程序”章节中学习如何使用这些对象。）例如，你可以使用此方法来读取属性或使用 JDBC 连接到数据库。`init` 方法在 Servlet 启动时被调用。如果 Servlet 配置为在 Web 应用部署并启动时自动启动，则它会被调用。否则，在接收到对它的第一个请求之前，它不会被调用。

`destroy` 在 Servlet 无法再接受任何请求后立即被调用。这通常发生在 Web 应用停止或卸载时，或者 Web 容器关闭时。因为它在卸载时立即被调用，所以你不需要等待垃圾回收来清理临时文件或断开数据库连接等资源。如果你的应用程序已卸载但服务器继续运行，这一点尤为重要；垃圾回收运行可能需要等几分钟或几小时。如果你在终结器而不是 `destroy` 方法中清理资源，可能会导致你的应用程序部分卸载或部署失败。你应该始终使用 `destroy` 方法来清理 Servlet 在请求之间所持有的资源。之前的代码示例使用了 `init` 和 `destroy` 方法分别记录 Servlet 启动和停止的时间。当你在下一节中运行应用程序时，这些日志消息将出现在 IDE 的输出窗口中。在本章的稍后部分，你将更好地利用这些方法。

## 为部署配置 Servlet

现在你已经创建了 Servlet，是时候让它行动了。虽然你已经有一个可以用巧妙的问候响应 GET 请求的类，但你还没有编写指令让 Web 容器随应用一起部署 Servlet。第 1 节介绍了部署描述符（web.xml）和 Web 应用的结构，第 2 节你学习了如何部署和使用应用。在本节中，你将在 `WEB-INF` 目录下创建 `web.xml` 文件并为部署配置 Servlet。然后你使用你的 IDE 部署应用并在浏览器中查看它。最后，你在代码中设置一些断点并检查某些方法何时被调用。

## 将 Servlet 添加到描述符

正如你所学到的，部署描述符指示 Web 容器如何部署应用。具体来说，它定义了所有随应用一起部署的监听器、Servlet 和过滤器，以及应用部署时使用的设置。首先，看一个（大部分）空的 `web.xml` 文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
         version="3.1">

    <display-name>Hello World Application</display-name>

</web-app>
```

> **警告** 如果你曾在之前的 Java EE 版本中使用过部署描述符，这可能看起来对你有些陌生。这是因为自 Java EE 6 以来，Web 以及其他配置文件的 XML Schema URI 发生了变化。你必须使用新的 URI 以确保你的应用程序符合 Java EE 7 标准。

### 为部署配置 Servlet

在在上一个示例中，加粗的代码指示应用服务器应用程序的名称。Tomcat 管理器界面列出了所有已安装的应用，`<display-name>` 标签之间的名称将出现在你的应用旁边。起始 `<web-app>` 标签中的 `version` 属性指示了应用程序编写时 Servlet API 版本——在此情况下，是 3.1 版本。

现在，你需要告诉 Web 容器创建你之前编写的 Servlet 实例，因此你可以在起始 `<web-app>` 和结束 `<web-app>` 标签之前向描述符文件添加一个 Servlet：

```xml
<servlet>
    <servlet-name>helloServlet</servlet-name>
    <servlet-class>com.wrox.HelloServlet</servlet-class>
</servlet>
```

在本章早些时候，你学习了 Servlet `init` 方法以及它通常何时被调用。在这个示例中，`init` 方法在 Web 应用启动后接收到第一个请求时被调用。通常情况下，这对大多数用户已经足够。然而，如果 `init` 方法执行某些操作，Servlet 的启动可能会变成一个耗时的过程，这可能导致第一个请求花费几秒甚至几分钟！显然，这不是理想的。对 Servlet 配置进行简单调整可以让 Servlet 在 Web 应用启动时立即启动：

```xml
<servlet>
    <servlet-name>helloServlet</servlet-name>
    <servlet-class>com.wrox.HelloServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
</servlet>
```

代码指示 Web 容器在 Web 应用启动时立即启动 Servlet。如果 Servlet 容器包含此标签，它们将根据标签的值启动，之前使用的值“1”优先。如果两个多个 Servlet 在 `<load-on-startup>` 标签中有相同的值，这些冲突的 Servlet 将按照它们在描述文件中出现的顺序启动，仍然是在数字小的 Servlet 之后、数字大的 Servlet 之前。

## 将 Servlet 映射到 URL

你已经指示应用服务器启动 Servlet，但还没有告诉它 Servlet 应该响应哪个 URL。这是一个简单的方法：

```xml
<servlet-mapping>
    <servlet-name>helloServlet</servlet-name>
    <url-pattern>/greeting</url-pattern>
</servlet-mapping>
```

通过此配置，所有到应用相对 URL `/greeting` 的请求都由 `helloServlet` 处理。（注意 `<servlet>` 和 `<servlet-mapping>` 标签内的 `<servlet-name>` 标签是匹配的。这就是 Web 容器关联两者的方式。）如果应用部署在 http://www.example.net，Servlet 将响应指向 URL http://www.example.net/greeting 的请求。当然，你并不局限于这种映射。你可以将多个 URL 映射到同一个 Servlet：

```xml
<servlet-mapping>
  <servlet-name>helloServlet</servlet-name>
  <url-pattern>/greeting</url-pattern>
  <url-pattern>/salutation</url-pattern>
  <url-pattern>/wazup</url-pattern>
</servlet-mapping>
```

在这种情况下，所有三个 URL 都作为同一个逻辑端点的别名：`helloServlet`。你可能会问，为什么需要获取一个 Servlet 实例名称，然后将请求映射到该实例的名称上？为什么你不能直接将 URL 映射到 Servlet 类呢？例如，如果你在在线配置中有两个不同的商店 Servlet 呢？这些商店可能具有相同的逻辑，但连接到不同的数据库。这可以通过简单地实现：

```xml
<servlet>
  <servlet-name>oddsStore</servlet-name>
  <servlet-class>com.wrox.StoresServlet</servlet-class>
</servlet>
<servlet>
  <servlet-name>endsStore</servlet-name>
  <servlet-class>com.wrox.StoresServlet</servlet-class>
</servlet>
```

```xml
<servlet-mapping>
  <servlet-name>oddsStore</servlet-name>
  <url-pattern>/odds</url-pattern>
</servlet-mapping>
<servlet-mapping>
  <servlet-name>endsStore</servlet-name>
  <url-pattern>/ends</url-pattern>
</servlet-mapping>
```

现在你有了同一个 Servlet 类的两个实例，但它们被映射到不同的 URL。在之前的例子中，你有三个 URL 都指向同一个 Servlet 实例。然而在这个例子中，你有两个不同的 Servlet 实例。你可能会好奇这两个不同的实例是如何知道自己属于哪个商店的。在 Servlet 代码的任何地方调用 `this.getName()` 都会返回 "oddsStore" 或 "endsStore"，取决于它是哪一个实例。回想一下你在记录初始化器（initializer）和销毁器（destroyer）的调用时使用过这个方法。

回到之前，你现在有了简单且完整的 `web.xml` 描述文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
  version="3.0">

  <display-name>Hello Application</display-name>

  <servlet>
    <servlet-name>helloServlet</servlet-name>
    <servlet-class>com.wrox.HelloServlet</servlet-class>
  </servlet>

  <servlet-mapping>
    <servlet-name>helloServlet</servlet-name>
    <url-pattern>/greeting</url-pattern>
  </servlet-mapping>

</web-app>
```

## 运行和调试你的 Servlet

保存后，编译你的应用程序并检查你已设置好 IDE 配置，以便在你的 Tomcat 8.0 实例中运行该项目。（如果你忘记了如何操作，请回阅第 2 章）。应用程序应该部署到 `/hello-world`。你也可以直接从 wrox.com 代码下载站点下载 Hello-World IDE 项目——它已经配置好正确部署。完成后，按照以下步骤操作：

1. 点击 IDE 中的调试图标以启动调试模式下的 Web 服务器。你的 IDE 在启动后会将你的应用程序部署到 Web 连接器。

2. 打开你的浏览器并导航到 http://localhost:8080/hello-world/greeting。你现在应该看到图 3-1 所示屏幕。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_84_0.png)

3. 理解发生什么的一种良好方法是在 `HelloServlet` 中放置一些断点并再次运行此实验。你应该停止调试器（这会关闭 Tomcat），这样你也可以命中初始化器中的断点。在 Servlet 的 `doGet`、`init` 和 `destroy` 方法的单行代码中放置断点；然后重启调试器。在 Tomcat 启动且你的应用程序部署后，你会发现你没有设置断点（因为部署描述符不存在 `<load-on-startup>`）。

4. 刷新浏览器中的 greeting 页面，你应该会在 IDE 的 `init` 方法中命中断点。这意味着 Tomcat 激活了你的 Servlet 的即时初始化：在第一个请求进来之前，它一直没有被初始化。

5. 就好比 `init` 方法完成需要很长时间一样，来自浏览器的请求将一直保持，直到你继续调试器，因此它会立即命中 `doGet` 方法中的断点。Servlet 服务于请求，但你的浏览器在等待响应。

6. 再次继续调试器，现在响应已发送到你的浏览器。

此时，你可以随心所欲地多次点击浏览器上的刷新按钮，你都将命中 `doGet` 方法中的断点。在销毁 Servlet（例如 Tomcat 关闭）并然后重新启动之前，`init` 方法不会再次被调用。在此之前，你还没有命中 `destroy` 方法中的断点。遗憾的是，你现在想命中那一点。

为了现在命中那一点，请按照以下步骤操作：

1. 从你的 IDE 中停止 Tomcat 服务器。

2. 重启服务器。

3. 再次导航到 URL。

4. 你现在应该命中 `destroy` 方法中的断点。

处理和操作响应标头，并将响应内容写回客户端。这些都是你在处理请求时可以做的许多事情之一，实际上，你通常应该执行这些或更多的操作。

## 使用 HttpServletRequest

`HttpServletRequest` 接口是 `ServletRequest` 的扩展，提供了关于接收到的请求的额外的 HTTP 协议特定信息。它定义了数十种方法，你可以通过它们获取 HTTP 请求的详情。它还允许你设置请求属性（与请求参数不同）。

> 注意：你将在下一章学习有关请求属性和认证详情的检查。本书没有涵盖每个方法的细节（对此，你可以查阅 API 文档），但涵盖了最重要的功能。

### 获取请求参数

可能是 `HttpServletRequest` 最重要的功能之一，也是你将在下一节中通过示例探索的功能，就是获取从客户端传递的参数。请求参数有两种不同的形式：通过查询参数（也称为 URI 参数），或者在 `application/x-www-form-urlencoded` 或 `multipart/form-encoded` 的请求体中（通常称为 post 变量或表单）。查询参数支持所有请求方法，并包含在 HTTP 请求的第一行中，例所示：

```
GET /index.jsp?productID=9781118654644&category=Books HTTP/1.1
```

> 注意：从技术上来说，HTTP 协议的 RFC 规范不允许任何 HTTP 方法中使用查询参数。然而，许多服务器会忽略传递给 DELETE、TRACE 和 OPTIONS 的查询参数，且查询参数在此类请求中的用处是值得怀疑的。因此，最好不要对这些类型的请求依赖查询参数。本书没有涵盖 HTTP 协议的所有规则和复杂之处。练习留给你自己完成。

在这个示例中，请求中包含了两个查询参数：productID（其值为这本书的 ISBN）和 category（其值为 Books）。这些相同的参数也可以作为 post 变量传递在请求体中。正如其名所暗示的那样，post 变量只能包含在 POST 请求中。考虑以下示例：

```
POST /index.jsp?returnTo=Page HTTP/1.1
Host: example.com
Content-Length: 48
Content-Type: application/x-www-form-urlencoded

addToCart&productID=9781118654644&category=Books
```



此 POST 请求具有 post 变量（指示网站将此书加入购物车）和查询参数（指示网站在任务完成后返回产品页面）。尽管这两种类型参数的传递方式存在差异，但它们本质上是相同的，并且传递了相同的信息。Servlet API 不区分这两种类型的参数。对请求的任何与参数相关方法的调用都会返回参数，无论它们是通过查询参数还是 post 变量传递的。

`getParameter` 方法为参数返回一个单一值。如果参数有多个值，`getParameterValues` 则返回一个包含该参数值的数组。如果参数只有一个值，该方法将返回一个包含一个元素的数组。`getParameterMap` 方法返回一个 `java.util.Map<String, String[]>`，其中包含所有映射到其对应值的参数名，而 `getParameterNames` 方法则返回所有可用参数名称的枚举；两者对于遍历所有参数都很有用。

> **警告**：当你第一次在请求对象上调用 `getParameter`、`getParameterNames` 或 `getParameterValues` 时，容器会通过获取请求的 `InputStream` 来确定请求是否包含 post 变量，并判断是否读取和解析了这些 post 变量。请求的 `InputStream` 只能读取一次。如果你在包含 post 变量的请求上调用了 `getStream` 或 `getReader`，稍后尝试获取该请求中的参数，该尝试将导致 `IllegalStateException`。如果你在包含 post 变量的请求上获取参数，然后调用 `getStream` 或 `getReader`，则会以 `IllegalStateException` 失败。

简单来说，每当你预计请求可能包含 post 变量时，最好只使用参数方法，并忽略 `getStream` 和 `getReader`。

### 确定请求内容的信息

有几种方法可以帮助确定 HTTP 内容的类型、长度和编码。`getContentType` 返回请求的 MIME 内容类型，例如 `application/x-www-form-urlencoded`、`application/json`、`text/plain` 或 `application/zip`。MIME 内容类型描述了它包含的数据类型。例如，ZIP 归档文件的文件类型为 `application/zip`，表示它们包含 ZIP 归档数据。

`getContentLength` 和 `getContentLengthLong` 方法返回请求体（内容主体）的字节数，后者对于内容可能超过 2GB 的请求非常有用（虽然未设置，但是不可能的）。当请求包含字符类型内容时，`getCharacterEncoding` 方法返回请求内容的字符编码（如 UTF-8 或 ISO-8859-1）。`text/plain`、`application/json` 和 `application/x-www-form-urlencoded` 是字符级 MIME 类型的示例。尽管这些方法在很多情况下很有用，但如果你使用参数方法从请求体获取 post 变量，则其中任何一个都不是必要的。

## 第 3 章 编写你的第一个 Servlet

> **注意**：Java EE 7 中的 Servlet 3.1 规范是第一个支持 `getContentLengthLong` 方法的版本。在此版本之前，对于大于 2,147,483,647 字节的请求，你必须调用 `getHeader("Content-Length")` 并将其 String 转换为 long。

### 读取请求内容

可以使用 `getInputStream`（返回 `javax.servlet.ServletInputStream`）和 `getReader`（返回 `java.io.BufferedReader`）方法来读取正在读取请求的内容。哪种最好取决于读取请求的上下文。如果预期内容是字符编码数据（例如 UTF-8 或 ISO-8859-1 文本），使用 `BufferedReader` 通常是最简单的方法，因为它能让你轻松地读取 `char`。然而，如果请求数据本质上是二进制的，你必须使用 `ServletInputStream` 以便以字节格式访问内容。你永远不要在同一个请求上同时使用两者。在调用其中任一方法后，调用另一个将导致 `IllegalStateException` 失败。记住上面的警告，不要在包含 post 变量的请求上使用这些方法。

### 获取请求特征如 URL、URI 和标头

你可能需要知道许多请求特征，例如发送请求的 URL 或 URI。可以从以下对象轻松获取：

- `getRequestURL` 返回客户端用于发送请求的实体，包括协议（http 或 https）、服务器名、端口号和服务器路径，但不包括查询字符串。因此，对于 `http://www.example.org/application/index.jsp?category=Books` 的请求，`getRequestURL` 返回 `http://www.example.org/application/index.jsp`。

- `getRequestURI`：这与 `getRequestURL` 略有不同，它只返回请求的服务器路径部分；使用上一个示例，为 `/application/index.jsp`。

- `getServletPath`：与 `getRequestURI` 类似，它甚至返回更少。如果请求是 `/hello-world/greeting?foo=world`，应用部署在 Tomcat 上的 `/hello-world`，且 servlet 映射为 `/greeting/salutation` 和 `/wazzup`，`getServletPath` 只返回用于匹配 servlet 映射的部分：`/greeting`。

- `getHeader`：返回给定名称标头的值。标头的大小写与传入方法的字符串不匹配，所以不区分大小写。如果存在多个相同名称标头，它只返回第一个值。在这种情况下，你可能希望使用 `getHeaders` 方法来返回所有值的枚举。

- `getHeaderNames`：返回请求中所有标头名称的枚举 —— 这是遍历可用标头的好方法。

- `getIntHeader`：如果你确定某个特定的请求头始终是数字，可以调用此方法来返回已转换为数字的值。如果请求头无法转换为整数，则会抛出 `NumberFormatException`。

- `getDateHeader`：你可以调用此方法返回代表有效时间戳的 Unix 时间戳等效值（毫秒）。如果请求头值未被识别为日期，则会抛出 `IllegalArgumentException`。

### 获取 Session 和 Cookies

文中提到的 `getSession` 和 `getCookies` 方法仅在此处提及是为了说明本章不涵盖它们，但它们是 `HttpServletRequest` 领域中重要的成员。你可以在第 5 章中学习更多这些内容。

### 使用 HttpServletResponse

由于 `HttpServletRequest` 接口扩展了 `ServletRequest` 并提供了对请求 HTTP 协议属性的访问，`HttpServletResponse` 接口扩展了 `ServletResponse` 并提供了对响应 HTTP 协议属性的访问。你使用该对象执行如设置响应头、向响应体写入内容、重定向请求、设置 HTTP 状态码以及向客户端发送 Cookie 等操作。本文将涵盖该对象最常用的功能。

### 向响应体写入内容

你对响应对象最常见的操作（以及你已经执行过的所有操作）都是向响应体写入内容。这可能是为了在浏览器中显示的 HTML、浏览器获取的图像，或者是正在下载的文件内容。它可以是纯文本或二进制数据，可能只有几个字节，也可能是几个 GB 字节。

`getOutputStream` 方法返回一个 `javax.servlet.ServletOutputStream`，而 `getWriter` 方法允许你向响应写入数据。与在 `HttpServletRequest` 中对应的方法一样，你可能希望使用 `PrintWriter` 向客户端返回 HTML 或其他经过字符编码的内容，因为它能方便地向响应写入编码后的字符串和字符。要发送二进制数据，你必须使用 `ServletOutputStream`。此外，你永远不要在同一个响应中同时使用 `getOutputStream` 和 `getWriter`。在调用其中一个后，调用另一个将导致 `IllegalStateException` 异常。

在向响应体写入内容时，设置内容类型或编码是必要的。你可以通过 `setContentType` 和 `setCharacterEncoding` 实现这一点。你可以根据需要多次调用这些方法；以最后一次调用的为准。然而，如果你计划在调用 `getWriter` 的同时调用 `setContentType` 和 `setCharacterEncoding`，必须在调用 `getWriter` 之前调用这两个方法，以便让返回的写入器配置了正确的字符编码。在 `getWriter` 之后进行的调用将被忽略。如果你在调用 `getWriter` 之前没有调用 `setContentType` 和 `setCharacterEncoding`，返回的写入器将使用客户端的默认编码。

你还可以使用 `setContentLength` 和 `setContentLengthLong` 方法。在大多数情况下，不需要调用这些方法。Web 容器在完成响应时会设置添加的 `Content-Length` 头，让它来处理是最安全的。

> **注意**：EE 7 中的 Servlet 3.1 是第一个支持 `setContentLengthLong` 方法的版本。在此之前，对于大小可能大于 2,147,483,647 字节的响应，你必须调用 `setHeader("Content-Length", Long.toString(length))`。

### 设置响应头和其他响应属性

作为 `HttpServletRequest` 方法的对应项，你可以调用 `setHeader`、`addHeader`、`setDateHeader` 来设置你需要的任何响应头值。如果现有响应已包含你所使用的名称的头，则该头的值将被覆盖。要避免这一点，你可以使用 `addHeader`、`addHeader` 或 `addDateHeader`。这些版本不会覆盖现有的头值，而是为头添加额外的值。你还可以调用 `getHeader`、`getHeaderNames` 和 `containsHeader` 来检查响应上已经设置了哪些头。

此外，你可以使用：

- `setStatus`：设置 HTTP 响应状态码
- `getStatus`：确定响应的当前状态
- `sendError`：设置状态码，指定一个要写入响应数据的可选错误消息，指引 Web 容器向客户端提供错误页面，并清除缓冲区
- `sendRedirect`：重定向到客户端 URL

本节涵盖了在 Servlet 中处理 HTTP 请求时可以执行的大部分操作，并在必要处指出了重要的细节和注意事项。在之前的章节中，你使用了 Hello-World 项目来演示 Servlet 的工作。在下一节中，你将进入一个稍微复杂一点的示例。

### 使用参数和接受表单提交

在本节中，你将通过接受参数和表单提交让你的 Hello-World 项目变得更具动态。你还探索了注解配置，并暂时放弃了部署描述符。对于本节的示例，你可以参考完成的 Hello-User 项目进行操作，也可以在涵盖这些内容时直接将更改整合到现有的项目中。

#### 项目变更

项目发生了一些更改。你首先应该注意到 `doGet` 方法现在变得复杂得多了：

```java
private static final String DEFAULT_USER = "Guest";

@Override
protected void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    String user = request.getParameter("user");
    if (user == null)
        user = HelloServlet.DEFAULT_USER;

    response.setContentType("text/html");
    response.setCharacterEncoding("UTF-8");

    PrintWriter writer = response.getWriter();
    writer.append("<!DOCTYPE html>\r\n");
    writer.append("<html>\r\n");
    writer.append("<head>\r\n");
    writer.append("<title>Hello User</title>\r\n");
    writer.append("</head>\r\n");
    writer.append("<body>\r\n");
    writer.append("<h1>Hello, ").append(user).append("!</h1>\r\n");
    writer.append("<form action=\"greeting\" method=\"POST\">\r\n");
    writer.append("<input type=\"text\" name=\"user\">\r\n");
    writer.append("<input type=\"submit\" value=\"Submit\">\r\n");
    writer.append("</form>\r\n");
    writer.append("</body>\r\n");
    writer.append("</html>");
}
```

加粗的部分是新的。它执行了以下逻辑：

- 如果请求中包含 `user` 参数，则使用该值；否则使用 `DEFAULT_USER`。
- 它设置响应的内容类型为 `text/html`，字符编码为 `UTF-8`。
- 它从响应获取 `PrintWriter` 并输出一个 HTML 文档（注意 DOCTYPE、表单）。

你可能会好奇当表单设置为 POST 时，`doGet` 方法如何接收提交。这通过简单的 `doPost` 实现，它也是新的：

```java
@Override
protected void doPost(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    this.doGet(request, response);
}
```

此实现简单地委托给了 `doGet` 方法。你最后注意到的是声明上方的注解：

```java
@WebServlet(name = "helloServlet",
urlPatterns = { "/greeting", "/salutation", "/wazzup" },
loadOnStartup = 1
)
public class HelloServlet extends HttpServlet {
```

> **注意**：你会注意到最新的 HelloServlet 代码示例中省略了类导入。随着代码变得复杂，导入语句可能会占用很多行。一个好的 IDE（如你读本书时使用的）可以识别类名并建议你导入，从而减轻你的繁琐工作。除少数例外外，书中其余示例都省略了导入和包语句。除非另有说明，新类将位于 `com.wrox` 包。

如果你查看部署描述符，你会注意到 Servlet 声明和映射已从 `web.xml` 文件删除。（如果你进行了这些更改，你应该删除部署描述符中除了 `<display-name>` 标签之外的所有内容。）上述示例中的注解替换了你在之前的项目中编写的 XML，并增加了一些内容。

你仍然获得一个名为 `helloServlet` 的 `HelloServlet` 实例；它在应用启动时启动；它仍然映射到 `/greeting` URL。它还映射到 `/salutation` 和 `/wazzup` URL。你可以看出，这是一种实例化和映射 Servlet 的更直接、简洁的方法。然而，它也有一些缺点，这些将在本章的剩余部分指出。

### 运行示例

![](img/9c2d45f6d547f72cb870b3a991f62ef6_94_0.png)

图 3-2

为了理解 Servlet 能做什么，首先在 URL 中添加查询字符串 `user=Allison`，使其变为 `http://localhost:8080/hello-world/greeting?user=Allison`。屏幕现在应该发生变化，显示的不再是“Hello, Guest!”，而是“Hello, Allison!”。在这种情况下，请求是由 `doGet` 方法服务的，该方法找到了 `user` 参数并将其输出到屏幕。

你可以通过在 `doGet` 和 `doPost` 中设置断点并刷新页面来确认这一点。现在，在屏幕上的名称字段输入你的名字并点击提交按钮。如果你检查地址栏中的 URL，你会发现它没有任何查询参数。相反，你的名字作为 post 变量包含在请求中，当 `doPost` 方法处理请求并委托给 `doGet` 方法时，对 `getParameter` 的调用获取了 post 变量，导致你的名字显示在屏幕上。命中断点将确认这一切已经发生。



记住上一节的内容，单个参数值并不是你的 Servlet 能够接受的唯一内容。你还可以接受多个参数。最常见的例子是一组相关的复选框，允许用户勾选一个或多个值。参考代码列表 3-1，`MultiValueParameterServlet/checkboxes`。在 Tomcat 中使用你的调试器编译并运行此代码，并将浏览器导航到 `http://localhost:8080/hello-world/checkboxes`。该 Servlet 中的 `doGet` 方法打印了一个带有五个复选框的表单。用户可以选择任何一个复选框并点击提交，这交由 `doPost` 方法处理。该方法检索所有水果值并使用无列表将它们列在屏幕上。尝试选择不同的复选框组合并点击提交。

### 代码列表 3-1: MultiValueParameterServlet.java

```java
@WebServlet(
    name = "multiValueParameterServlet",
    urlPatterns = {"/checkboxes"}
)
public class MultiValueParameterServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
        response.setContentType("text/html");
        response.setCharacterEncoding("UTF-8");

        PrintWriter writer = response.getWriter();
        writer.append("<!DOCTYPE html>\r\n");
        writer.append("<head>\r\n");
        writer.append("<title>Hello User Application</title>\r\n");
        writer.append("<body>\r\n");
        writer.append("<form method=\"POST\">\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Banana\"/>\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Apple\"/>\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Orange\"/>\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Guava\"/>\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Kiwi\"/>\r\n");
        writer.append("<input type=\"submit\" value=\"Submit\"/>\r\n");
        writer.append("</form>\r\n");
        writer.append("</body>\r\n");
        writer.append("</html>\r\n");
    }

    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
        String[] fruits = request.getParameterValues("fruit");

        response.setContentType("text/html");
        response.setCharacterEncoding("UTF-8");

        PrintWriter writer = response.getWriter();
        writer.append("<!DOCTYPE html>\r\n");
        writer.append("<head>\r\n")
        .append("<body>\r\n")
        .append("<h2>Your Selections</h2>\r\n");
        if (fruits == null) {
            writer.append("You did not select any fruits.\r\n");
        } else {
            writer.append("<ul>\r\n");
            for (String fruit : fruits) {
                writer.append("<li>").append(fruit).append("</li>\r\n");
            }
            writer.append("</ul>\r\n");
        }
        writer.append("</body>\r\n")
        .append("</html>\r\n");
    }
}
```

这向你展示了在 Servlet 方法中请求参数的各种方式。你探索了查询参数和 post 变量，涵盖了单值和多值参数。在下一节中，你将学习如何使用初始化参数来配置你的应用程序。

## 使用初始化参数配置应用程序

在编写 Java 应用时，不可避免会产生配置应用程序及其内部 Servlet 的需求。使用许多技术有很多方法可以这一点，你今天将探索其中几种。本节涵盖了通过初始化参数（通常缩写为 init parameters）和 servlet 参数来配置应用程序最简单的方法。这些参数可以用于许多用途，从关系型数据库的连接信息到提供发送警报的电子邮件地址等。它们在应用程序启动时定义，在不重启应用程序的情况下无法更改。

### 使用上下文参数

早些时候看到，在 Servlet 3.0 中，你可以无需使用部署描述符就可以定义上下文参数。然而，仍有某些事情需要部署描述符。上下文初始化参数就是其中一个功能。你可以在 `web.xml` 文件中使用 `<context-param>` 标签声明上下文初始化参数。以下显示了两个上下文初始化参数：

```xml
<context-param>
    <param-name>settingOne</param-name>
    <param-value>foo</param-value>
</context-param>
<context-param>
    <param-name>settingTwo</param-name>
    <param-value>bar</param-value>
</context-param>
```

这创建了两个上下文参数：`settingOne` 的值为 `foo`，`settingTwo` 的值为 `bar`。你可以轻松地从 Servlet 的任何地方使用并查看这些值。`ContextParameterServlet` 展示了这一点：

```java
@WebServlet(
    name = "contextParameterServlet",
    urlPatterns = {"/contextParameters"}
)
public class ContextParameterServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        ServletContext c = getServletContext();
        PrintWriter writer = response.getWriter();
        writer.append("settingOne: ").append(c.getInitParameter("settingOne"));
        writer.append(", settingTwo: ").append(c.getInitParameter("settingTwo"));
    }
}
```

> **注意**：应当注意的是，从 Servlet 3.0 开始，你可以调用 `ServletContext` 的 `setInitParameter()` 方法作为使用 `<context-param>` 定义上下文初始化参数的替代方案。然而，此方法只能在 `java.servlet.ServletContextListener` 的 `contextInitialized()` 方法（你将在第 9 节学习）或 `java.servlet.ServletContextInitializer` 的 `startup()` 方法（你将在第 12 节学习）中调用。尽管如此，更改值仍需要重新编译应用程序，因此 XML 通常是配置上下文参数的最佳选择。

### 使用 Servlet 初始化参数

考虑 `ServletParameterServlet` 类的代码。你可能立即注意到它没有被 `@WebServlet` 注解。别担心，几分钟后你就会知道原因。在其他方面代码与 `ContextParameterServlet` 几乎相同。你不再从 `ServletContext` 对象获取初始化参数，而是从 `ServletConfig` 对象获取：

```java
public class ServletParameterServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        ServletConfig config = getServletConfig();
        PrintWriter writer = response.getWriter();
        writer.append("database: ").append(config.getInitParameter("database"));
        writer.append(", server: ").append(config.getInitParameter("server"));
    }
}
```

当然，仅仅有 Servlet 代码是不够的。接下来的 XML 部署描述符声明并映射了 servlet，还进行了一些额外操作：

```xml
<servlet>
    <servlet-name>servletParameterServlet</servlet-name>
    <servlet-class>com.wrox.ServletParameterServlet</servlet-class>
    <init-param>
        <param-name>database</param-name>
        <param-value>CustomerSupport</param-value>
    </init-param>
    <init-param>
        <param-name>server</param-name>
        <param-value>10.0.12.5</param-value>
    </init-param>
</servlet>
<servlet-mapping>
    <servlet-name>servletParameterServlet</servlet-name>
    <url-pattern>/servletParameters/*</url-pattern>
</servlet-mapping>
```

`<init-param>` 标签类似于 servlet 环境的 `<context-param>` 标签，它创建了特定于 servlet 的初始化参数。如果你编译、调试并导航到 `http://localhost:8080/hello-world/servletParameters`，你就可以使用部署描述符指定的数据库和服务器参数。那么，你可能会问，为什么不能像其他 servlet 映射那样使用注解来实现此功能？嗯，从技术上讲，你可以的。你可以通过替换部署描述符中的初始化和映射，并将以下内容添加到 servlet 中来实现与之前代码相同的结果：

```java
@WebServlet(
    name = "servletParameterServlet",
    urlPatterns = {"/servletParameters/*"},
    initParams = {
        @WebInitParam(name = "database", value = "CustomerSupport"),
        @WebInitParam(name = "server", value = "10.0.12.5")
    }
)
public class ServletParameterServlet extends HttpServlet {
}
```

然而，这样做的缺点是，如果不重新编译应用程序，Servlet 初始化参数的值无法更改。当然，可能某些设置是你不想在不重新编译应用程序的情况下更改的，但在这种情况下，为什么不直接将它们设为常量呢？在部署描述符中使用 Servlet 初始化参数的优势是，服务器管理员只需要更改几行 XML 并重启应用程序即可更改效果。如果此类设置包含关系型数据库的连接信息，你最不想做的事情就是为了更改数据库服务器的 IP 地址而重新编译应用程序了！

下一节将介绍 Servlet 3.0 规范中添加的 `HttpServletRequest` 的新功能，以及一个在书中余下章节中将不断改进的新示例。

### @Config 的缺点

正如前面提到的，在 Web 应用程序中基于注解的配置（通常称为 @Config）既有优点也有缺点。主要优点是消除了 XML，并使用了直接、简洁的注解语言来配置您的应用程序。然而，这种方法也有许多缺点。

其中一个例子是无法为单个 Servlet 类创建多个实例。你之前在这一节中已经看到这种模式是如何使用的。而使用注解时，只能通过 XML 配置或程序化的 Java 配置来完成更改。

在第 9 章中，你将学习过滤器（filters）以及为什么仔细构造过滤器的执行顺序很重要。当使用 XML 配置或程序化的 Java 配置声明它们时，可以指定特定的顺序。然而，如果你使用 `@javax.servlet.annotation.WebFilter` 声明过滤器，则无法让它们按特定顺序执行（这感觉像是 Servlet 3.0 和 3.1 规范中的一个明显疏忽）。除非你的应用程序只有一个过滤器，否则 `@WebFilter` 是没用的。

许多许多小事情仍然需要 XML 部署描述符来完成，例如定义错误处理页面、配置 JSP 设置以及提供欢迎页面列表。坦率地说，你可以混合使用 XML、注解和程序化的 Java 配置，因此可以在最方便的时候使用每种方法。在本书中，你将使用这三种技术。

### 从表单上传文件

向 Java EE Servlets 上传文件几乎一直是可能的，但过去通常需要大量的努力。这项任务非常复杂，以至于 Apache Commons 启动了一个整个项目——Commons FileUpload 来处理这些工作。因此，看似接受文件上传提交的简单需求，却为你的应用程序引入了第三方依赖项。Java EE 6 中的 Servlet 3.0 通过引入 Servlet 的多部分（multipart）配置选项以及 `HttpServletRequest` 中的 `getPart()` 和 `getParts()` 方法，改变了这一切。

你可以将此功能作为你的交互示例的起点：客户支持项目。虽然每一章都有较小的示例来演示特定的知识点，但每一章还包含客户支持项目的新版本，其中整合了在该章中学到的新知识点。

### 介绍客户支持项目

该设置是一个跨国小部件公司为全球客户服务的网站。你的产品经理被赋予任务为公司网站添加一个交互式客户支持应用程序。它应该允许用户发布问题或支持工单，并允许员工对这些查询进行回复。支持工单和评论都包含文件附件。对于紧急事项，客户应该进入一个与专门的支持代表的聊天窗口。而且，最重要的是，由于这是跨国小部件公司，整个应用程序应该根据公司决定翻译的任何语言进行本地化。这要求不过分，对吧？

噢，是的。它还需要非常安全。

### 配置用于上传的 Servlet

你可能注意到“工单数据库”根本不是数据库（或者它是吗？它是存储数据的媒介，对吧？），而是一个简单的哈希 map。最终在第三部分，我们将使用真实的数据库为你的应用程序提供支持。但现在，你想让用户界面运行并理解业务需求，以便让跨国小部件公司的产品管理部门满意。

现在你已经看到了目前的内容，让我们看看 `doGet` 的实现：



```java
@Override
protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException
{
    String action = request.getParameter("action");
    if (action == null)
        action = "list";
    switch (action) {
        case "create":
            this.showTicketForm(response);
            break;
        case "view":
            this.viewTicket(request, response);
            break;
    }
}
```

> **注意** 使用注解配置 Servlet 初始化参数会导致上一个示例中的多部分参数无法在不重新编译的情况下更改。如果你预计服务器管理员需要在不重新编译的情况下自定义这些设置，则你需要使用部署描述符。在 `<servlet>` 标签内，你可以放置 `<multipart-config>` 标签，在其中你可以使用 `<location>`、`<file-size-threshold>`、`<max-file-size>` 和 `<max-request-size>` 标签。

# 第三章 编写你的第一个 Servlet

你已经能看到一些熟悉的东西。`@MultipartConfig` 指令 容器提供文件支持。第一个（这里未显示）是 `location`。它指示 容器在需要时存储临时文件的目录。在大多数情况下，省略此字段让应用服务器使用默认值即可。`fileSizeThreshold` 告诉容器在写入目录之前文件有多大。

在本示例中，小于 5 MB 的上传文件将保留在内存中直到请求完成并变成垃圾。如果文件超过 5 MB，容器将将其存储在 `location` 中直到请求完成，然后从磁盘上删除。最后两个参数 `maxSize` 和 `maxRequestSize` 对上传文件进行限制：示例中的 `maxSize` 限制超过 20 MB 的上传文件，而 `maxRequestSize` 限制超过 40 MB 的请求，无论其中包含多少个文件上传。这其实就是全部。Servlet 现在已配置了文件上传。

```java
@WebServlet(
    name = "ticketServlet",
    urlPatterns = {"/tickets"},
    loadOnStartup = 1
)
@MultipartConfig(
    fileSizeThreshold = 5242880, // 5MB
    maxFileSize = 20971520, // 20MB
    maxRequestSize = 41943040 // 40MB
)
public class TicketServlet extends HttpServlet {
    private int TICKET_SEQUENCE = 1;

    private Map<Integer, Ticket> ticketDatabase = new LinkedHashMap<>();
}
```

### 从表单上传文件

```
case "download":
    this.downloadAttachment(request, response);
    break;
case "download":
    default:
    this.listTickets(response);
    break;
```

将所有内容都放在 `doGet` 方法中内容太多了；没不了多久，你就会拥有一个跨越数百行的方法。在这个示例中，`doGet` 方法使用了一种原始的动作/执行器模式：动作通过请求参数传递，`doGet` 方法根据该动作将请求发送给执行器（方法）。`doPost` 方法也类似类似：

```java
@Override
protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException
{
    String action = request.getParameter("action");
    if (action == null)
        action = "list";
    switch (action) {
        case "create":
            this.createTicket(request, response);
            break;
        case "download":
            default:
            response.sendRedirect("tickets");
            break;
    }
}
```

你可以在 `doPost` 中注意到的一点是重定向（redirect）的使用。你在几个章节之前学习过这种方法。在这种情况下，如果客户端执行带有无效 `action` 参数的 POST 请求，他的浏览器将被重定向到列出票目的页面。该类中的大多数方法并没有什么新意：参数的使用、使用 `PrintWriter` 将内容输出到客户端浏览器等。并不是所有的代码都能放进这本书中，但确实有些功能是你应该关注的。接下来的示例是 `downloadAttachment` 的一个代码片段，仅包含你以前未见过的部分：

```java
response.setHeader("Content-Disposition",
    "attachment; filename=" + attachment.getName());
response.setContentType("application/octet-stream");
```

这段简单的代码负责处理将文件下载到客户端浏览器。正如前面所述，`Content-Disposition` 头部会强制浏览器询问客户端保存或下载文件，而不是直接在内联中打开文件。浏览器内容类型是一种通用的二进制内容类型，它可以防止数据被应用某种字符编码。（正确的实现应该知道附件的实际 MIME 内容类型并使用该值，但那超出了本书的范围。）最后，使用 `OutputStream` 将文件内容写入响应中。这可能不是向响应中写入文件内容最高效的方法，因为它可能会导致大文件出现内存问题。如果你预计将允许大型下载，你不应该将文件存储在内存中，而应该将字节从文件的 `InputStream` 复制到 `ResponseOutputStream`。你应该频繁刷新 `ResponseStream`，以便字节能够持续流回用户的浏览器，而不是在内存中缓冲。改进这段代码的任务留给你来完成。

### 接受文件上传

最后，看看 `createTicket` 方法以及它使用的方法列表 3-2 中的 `processAttachment`。这些方法特别重要，因为它们处理文件上传——这是你还没有做过的事情。`processAttachment` 方法从 multipart 请求中获取 `InputStream` 并将其复制到 `Attachment` 对象中。它使用了 Servlet 3.1 中添加的 `getSubmittedFileName` 方法来识别上传前的原始文件名。`createTicket` 方法使用此方法和其他请求参数来填充 `Ticket` 对象并将其添加到数据库中。

列表 3-2：HttpServlet.java 的部分

```java
private void createTicket(HttpServletRequest request,
                            HttpServletResponse response)
    throws ServletException, IOException {
    Ticket ticket = new Ticket();
    ticket.setCustomerName(request.getParameter("customerName"));
    ticket.setSubject(request.getParameter("subject"));
    ticket.setBody(request.getParameter("body"));

    Part filePart = request.getPart("file");
    if (filePart != null) {
        Attachment attachment = this.processAttachment(filePart);
        if (attachment != null) {
            ticket.addAttachment(attachment);
        }
    }

    int id;
    synchronized (this) {
        id = this.TICKET_ID_SEQUENCE++;
        this.ticketDatabase.put(id, ticket);
    }

    response.sendRedirect("tickets?action=view&ticketId=" + id);
}

private Attachment processAttachment(Part filePart)
    throws IOException {
    InputStream inputStream = filePart.getInputStream();
    ByteArrayOutputStream outputStream = new ByteArrayOutputStream();

    int read;
    final byte[] bytes = new byte[1024];

    while ((read = inputStream.read(bytes)) != -1)
    {
        outputStream.write(bytes, 0, read);
    }

    Attachment attachment = new Attachment();
    attachment.setName(filePart.getSubmittedFileName());
    attachment.setContents(outputStream.toByteArray());

    return attachment;
}
```

你可能在 `createTicket` 方法中注意到的一点是使用了 `synchronized` 块来锁定对票目数据库的访问。你将在本章的下一个也是最后一个部分更深入地探讨这一点。

### 使你的应用程序适用于多线程

Web 应用程序本质上是多线程应用程序。在任何给定时刻，可能有零、一个或一千个人同时正在使用你的 Web 应用程序，你的代码必须强制并考虑到这一点。这个主题有几十个不同的方面，已经有整本书籍关于多线程和应用程序中的并发管理而编写得了。显然，这本书可能无法涵盖所有重要的多线程讨论。然而，在考虑你的 Web 应用程序的并发性时，你最应该知道两点。

### 理解请求、线程和执行

Web 应用程序本质上是多线程应用程序。在任何给定时刻，可能有零、一个或一千个人同时正在使用你的 Web 应用程序，你的代码必须强制并考虑到这一点。这个主题有几十个不同的方面，已经有整本书籍关于多线程和应用程序中的并发管理而编写了。显然，这本书可能无法涵盖所有重要的多线程讨论。然而，在考虑你的 Web 应用程序的并发性时，你最应该知道两点。

> **注意** 关于请求和线程的主题，在某些情况下线程可能不会贯穿始终。Java EE 中的 Servlet 3.0 引入了异步请求的概念。基本上，当你的 servlet 接收到请求时，它可以调用 `ServletRequest.startAsync` 方法。你的 servlet 然后可以从方法返回而不响应，线程将返回池。随后，当某些事件发生时，你的应用程序可以从 `asyncContext` 获取响应对象并用来向客户端发送响应。

为多线程应用程序编写代码典型问题是共享资源的访问。在方法执行期间创建的对象和变量只要该方法执行就是安全的——其他线程无法访问它们。然而，例如 Servlet 中的静态和实例变量可以被多个线程同时访问。同步这些资源的访问是非常重要的，以防止其内容损坏并可能导致应用程序错误。

### 编写你的第一个 Servlet

创建和销毁线程包含大量的开销，会减慢应用程序。采用这种方法可以消除这种开销并提高性能。线程池有一个可配置的大小，决定了可以处理多少连接。虽然这不是关于技术的讨论，但它可能会产生影响。

在 Java 中，一个线程可能会在另一个线程更改变量值后，仍然读取该变量的旧值。这在某些情况下会导致一致性问题。`volatile` 关键字在这种情况下为所有未来的读取操作建立了一个发生先行（happens-before）的关系，并保证其他线程始终能看到变量的最新值。

接下来，回想列表 3-2 中 `createTicket` 方法中的同步块代码：

```
synchronized(this)
{
    id = this.TICKET_ID_SEQUENCE++;
    this.ticketDatabase.put(id, ticket);
}
```

这段代码中发生了两件事：`TICKET_ID_SEQUENCE` 递增并获取了值，以及 `Ticket` 被插入到对象的哈希图中。这两个变量都是 Servlet 的实例变量，意味着多个线程可能同时访问它们。将这些操作放在 `synchronized` 块中，可以保证在当前线程完成之前，没有其他线程可以执行独占访问。当然，在使用 `synchronized` 同步块或方法时应始终保持小心，因为同步机制的应用不当可能会导致死锁，这个问题超出了本书的讨论范围。两行代码同时开始。

> **警告** 编写 Servlet 方法时需要记住的一点：永远不要将响应对象存储在静态变量或实例变量中。千万不要这样做。没有可能也许——这会给你带来麻烦。任何属于请求的对象和资源都应该作为局部变量和方法参数存在。

### 总结

在本章中，你学习了 Servlet 接口、`GenericServlet` 和 `HttpServlet` 抽象类，以及 `HttpServletRequest` 和 `HttpServletResponse` 接口。你学习了如何使用请求和响应对象处理传入的请求并做出相应的响应。你尝试了部署描述符，以及如何使用 `web.xml` 和注解来配置 Servlet。你还发现了处理 HTTP 请求时最重要的任务之一：处理请求参数（包括查询参数和 POST 变量）以及通过表单提交接受文件上传。你了解了 Servlet 和 `init` 参数以及如何使用它们来配置你的应用程序。最后，你学习了请求线程、线程池，以及多线程考虑在 Web 应用程序编程中的重要性。

至此，你应该已经掌握了在 Web 应用程序中创建和使用 Servlet 的基础知识。在本章中你可能注意到的主要不便之处是向响应中编写简单 HTML 的复杂性和繁琐。在下一章中，你将探索这个问题的答案，以及它如何让 Java EE 世界的生活变得更加轻松：JavaServer Pages（JSP）。

# 第4章 使用 JSP 显示内容

本章内容

- 使用 `<br />` 比 `output.println("<br />")` 更容易
- 创建你的第一个 JSP
- 在 JSP 中使用 Java（以及为什么你不应该这样做）
- 结合 Servlet 和 JSP
- 关于 JSP 文档 (JSPX) 的说明

本章的 WROX.COM 代码下载

你可以在 www.wrox.com/go/projforwebbaps 的 "Download Code" 标签页找到本章的 wrox.com 代码下载。本章代码分为以下几个示例：

- Hello-World-JSP 项目
- Hello-User-JSP 项目
- Customer-Support-v2 项目

本章的新 Maven 依赖项

除了上一章介绍的 Maven 之外，你还需要以下 Maven 依赖项。排除（exclusions）是必要的，因为 JSTL 实现定义了对旧版本 JSP 和 Servlet 规范的瞬态依赖，这些版本的 Maven 节点 ID 与当前版本不同。

```xml
<dependency>
  <groupId>javax.servlet.jsp</groupId>
  <artifactId>javax.servlet.jsp-api</artifactId>
  <version>2.3.1</version>
  <scope>provided</scope>
</dependency>
```



```xml
<dependency>
  <groupId>javax.servlet.jsp.jstl</groupId>
  <artifactId>javax.servlet.jsp-jstl-api</artifactId>
  <version>1.2.1</version>
  <scope>compile</scope>
</dependency>

<dependency>
  <groupId>org.glassfish.web</groupId>
  <artifactId>javax.servlet.jsp.jstl</artifactId>
  <version>1.2.2</version>
  <scope>compile</scope>
  <exclusions>
    <exclusion>
      <groupId>javax.servlet</groupId>
      <artifactId>servlet-api</artifactId>
    </exclusion>
    <exclusion>
      <groupId>javax.servlet.jsp</groupId>
      <artifactId>jsp-servlet-api</artifactId>
    </exclusion>
    <exclusion>
      <groupId>javax.servlet.jsp.jstl</groupId>
      <artifactId>jstl-api</artifactId>
    </exclusion>
  </exclusions>
</dependency>
```

在上一章中，你学习了 Servlet 以及处理请求、响应、请求参数、文件上传、Servlet 配置等。然而，你已经注意到在编写 Servlet 代码输出 HTML 时存在一个严重的不便。需要响应的内容是：反复调用 `ServletOutputStream` 或 `PrintWriter` 方法来输出内容，并且必须将 HTML 内容放置在 Java 字符串中，还要对引号进行转义，这确实非常痛苦。在本章中，你将探索 Java Pages（JSP）以及它们如何让你的生活变得简单得多。

## 比 OUTPUT.PRINTLN("<BR />>") 更容易

Java 是一种强大的语言。它具有许多功能和特性，使其有用、灵活且易于使用。可能，你读这本书是因为你喜欢 Java 并想学习如何用它做更多事情。那么，这是怎么呢？

```java
PrintWriter writer = response.getWriter();
writer.append("<!DOCTYPE html>\r\n");
writer.append("<head>\r\n");
writer.append("<title>Hello World</title>\r\n");
writer.append("</head>\r\n");
writer.append("<body>\r\n");
writer.append("  Hello, World!\r\n");
writer.append("</body>\r\n");
writer.append("</html>\r\n");
```

这种不便的相当冗长。最近代码的问题是它是一个静态 HTML 文档。它写起来可能更容易，维护起来也比 Java 代码容易得多，但它没有任何动态性。如果你将之前的示例写在纯 HTML 文件中，它是这样的：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World</title>
  </head>
  <body>
    Hello, World!
  </body>
</html>
```

幸运的是，Java EE 规范意识到这种系统很快就会变得混乱，并设计了 Pages（称为 JSP）来满足这一需求。

## 为什么 JSP 更好

JSP 有替代方案。也许常见的替代方案是 Facelets，属于更广泛的 Java Server Faces（简称 Faces，容易与 JSP 混淆）。还有模板框架，例如 Velocity、Freemarker、SiteMesh 和 Tiles，它们以各种方式补充或替换 JSP 提供的功能。本书无法涵盖适用于 Servlet 3.1 规范的所有演示技术选项和变体。因此，它将关注最流行和最常用的技术。

在本章中，你将探索 JSP 的基本规则，并学习 JSP 技术的语法、声明（declarations）、脚本段（scriptlets）和表达式（expressions）。你还将了解 JSP 的生命周期以及它最终如何向调用者发送响应。

以下示例可以在 Hello-World 项目的 `index.jsp` 文件找到，它重建了第 2 章的 Hello-World 项目，但使用的是 JSP 而不是 Servlet 来向用户传递问候。

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World Application</title>
  </head>
  <body>
    Hello, World!
  </body>
</html>
```

```html
</head>
<body>
Hello, World!
</body>
</html>
```

此示例与该节中原始的纯 HTML 示例几乎相同。这段特定代码是第一行，并加了**粗体**显示。这是你将在“创建你的第一个 JSP”章节中详细检查的几个 JSP 指令之一。此特定指令设置了页面的内容类型（content type）和编码（encoding），这是你之前通过调用 `setContentType` 和 `setCharacterEncoding` 方法完成的操作。此 JSP 中的其他所有内容都是纯 HTML，在响应中原封不动地传输给客户端有趣的问题是：“在背后到底发生了什么？”

## JSP 在运行时发生了什么

JSP 仅仅是一个华丽的 Servlet。也许你听过过“语法糖”这个词。归根结底，无论通过何种方式，今天所有流行的程序员经常使用的东西都是语法糖。以 Java 为例，作为你编写的一种种代码。当你编译 Java 代码时，它会被转换为字节码。字节码才是重要的——而不是代码。事实上，Java 中的许多不同语句可以转换为相同的字节码。但更进一步说，字节码并不是页面的最终渲染。这种字节码是平台无关的，但这不足以使其在不同的操作系统上运行。

当 Java 在 JRE 中运行时，JSP 编译器会将其编译成机器码，这种机器码特定于它运行的模板。最终，这才是执行的代码。即使是更底层的语言（如 C），也仅仅是它们编译目标代码的语法糖。JSP 是另一种形式的语法糖。在运行时，JSP 代码由 JSP 编译器解释，编译器会解析 JSP 代码中的所有特殊功能并将其翻译为 Java 代码。从每个 JSP 创建的类实现了 `Servlet`。然后，Java 进入了它通常经历的循环。在运行时，它被编译成字节码，然后变成机器码。最后，转换成 Servlet 的 JSP 就像任何其他 Servlet 一样处理请求。

为了研究这一点，请执行以下步骤：

1. 在你的 IDE 中编译 Hello-World-JSP 项目，启动调试器，并在浏览器访问 `http://localhost:8080/hello-world`。你应该能在屏幕上看到那个再熟悉的问候语。

2. 浏览文件系统找到 Tomcat 8 的根目录（Windows 上的 `C:\Program Files\Apache Foundation\Tomcat 8`），进入 `Catalina\localhost\hello-world` 目录。Tomcat 将应用程序的所有编译后的 JSP 放在此目录中，但它也留下了生成的中间 JSP 文件，以便你对其进行检查和排错。

3. 继续查看后续指令，直到看到 `index_jsp.java` 文件。用你喜欢的文本编辑器打开它（即 `index_jsp.class` 文件）。

你应该发现的是一个继承自 `org.apache.jasper.runtime.HttpJspBase` 的类。这个抽象类——你可能猜到了——是 `HttpServlet`。`HttpJspBase` 提供了一些基础功能，所有 Tomcat 编译的 JSP 都会使用这些功能；当你的 JSP 执行时，最终执行的是 Servlet 的 `service` 方法，最终最终执行 `_jspService` 方法。

如果你检查 `_jspService` 方法，你会发现有一系列方法调用将你的 HTML 写入输出流。这段代码对你来说应该非常熟悉，因为它与你用这个 JSP 替换的 Java 代码没有区别。当然，JSP Servlet 类在每个容器上看起来是不相同的。你运行的每个 Web 容器对应的 `org.apache.jasper` 类都不同。重要的是，JSP 的行为和语法有一个标准规范，只要你使用的容器符合规范，你的 JSP 在所有容器上的运行情况都应该是相同的，即使它们被翻译后的代码看起来完全不同。

JSP 就像你普通的 Servlet 一样，也可以在运行时进行调试。为了演示这一点，在 JSP 中包含“Hello, World”的行上设置一个断点，然后刷新浏览器。此时，你将命中 JSP 中的断点，你应该会注意到几点。首先，你可以直接在 JSP 代码中设置断点！你不需要在翻译后的 Servlet 类中设置断点；Java、Tomcat 和你的 IDE 都可以将 JSP 中的断点与运行中执行的代码匹配。你还应该注意到，尽管断点可能在 JSP 代码中，但调试器清楚地显示你的运行通过了 `_jspService` 方法，并且变量向你展示了在 `index_class` 作用域内定义的实例和局部变量。

> **警告** IntelliJ IDEA 的调试功能比 Eclipse IDE 强大得多。如果你在使用 Eclipse，你可能完全无法在该 JSP 中设置断点。到目前，Eclipse 只允许你在 JSP 嵌入的代码中设置断点；而 IntelliJ 允许在任何 JSP 代码中设置断点。

就像在容器中运行的其他 Servlet 一样，JSP 也有生命周期。在某些容器（如 Tomcat）中，JSP 在第一个请求到达时会被实时翻译并编译。对于后续请求，JSP 已经编译完成并准备就绪。正如你可以想象的，这会引入性能影响。虽然性能影响通常只发生在第一次请求，随后的所有请求都能以不错的速度运行，但这在生产环境中是不可的。因此，许多容器为你提供了一个选项，在应用程序部署时预计算应用程序的所有 JSP。这当然无疑会显著减慢大型应用程序的部署速度。如果你有成千上万个 JSP，你的应用程序部署可能需要 10 分钟而不是只需 1 分钟。哪种配置符合最佳需求取决于组织。无论编译时间如何，一旦第一个请求到达，JSP Servlet 就会被初始化并提供服务。

到此，你应该意识到你在 JSP 中编写的代码被翻译成了你在不使用 JSP 的情况下也必须编写的某种版本的代码。那么，为什么可能有人费心使用 JSP 呢？事实是，对于在 浏览器中生成标记，JSP 比直接编写 Java 代码要容易得多。如果这能提高你开发过程的速度、效率和准确性，那么问题实际上是：“你为什么不用 JSP 呢？”

## 创建你的第一个 JSP

你已经探索了一个已经为你写好的 JSP，现在开始创建你自己的 JSP吧。你需要了解一些关于 JSP 结构以及你可以在 JSP 中放入内容的知识。在本节中，你将回顾一些基础的必备知识，并在下一节中进一步探讨。

### 理解文件结构

在上一章中，你探索了 Servlets 并回答了问题：“在 service 方法中你必须做什么？”答案是，你必须用有效的 HTTP 响应来恰当地响应 HTTP 请求，因为 Servlet 处理了所有这一切；你的 `doGet` 和 `doPost` 方法实际上可以是空的（除非有特殊要求）。事实证明，这个问题仍然存在。当 JSP 执行时，有很多事情必须发生，但所有这些“必须”的事情都已为你处理好。

为了演示这一点，在一个空项目的根目录下创建一个名为 `blank.jsp` 的文件；删除其所有内容（你的 IDE 可能会放入代码）并重新部署项目。或者，直接使用从 wrox.com 下载的 Hello-World-JSP。当你访问 `http://localhost:8080/hello-world/blank.jsp` 时，不会出现任何错误。一切运行正常；你只是得到了一个无用的页面。现在将以下代码放入其中，部署并刷新：

```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World Application</title>
</head>
<body>
  Hello, World!
</body>
</html>
```

现在 `blank.jsp` 和 `index.jsp` 之间存在细微差异，就是 `index.jsp` 第一行的那个特殊标签。尽管如此，内容显示仍然相同。这是因为 JSP 默认的内容类型为 `text`，编码为 `ISO-8859-1`。这种默认字符编码与许多特殊字符（如非英语语言中的字符）不兼容，会干扰应用程序本地化工作。因此，至少你的 JSP 需要包含 HTML 来显示给用户。然而，为了确保 HTML 在所有浏览器、系统和语言中正确显示，你希望包含某些 JSP 标签来控制发送给客户端的数据，将字符编码设置为利于本地化的 UTF-8。

JSP 中可以使用不同类型的标签，你可以在下一节中探索更多。在指令标签中，有一个你已经见过的：

```jsp
<%@ page %>
```

该语言告诉容器 JSP 使用哪种 JSP 脚本语言。JSP 脚本语言（不要与解释型脚本语言混淆）是可以嵌入 JSP 中以执行某些操作的语言。目前，Java 是 JSP 唯一支持的脚本语言，但此属性允许未来进行扩展。

从技术上讲，你可以省略此属性。因为 Java 是唯一支持的 JSP 脚本语言，而且 Java 也是规范中的默认语言，因此当缺少此属性时，会默认为 Java。`contentType` 告诉容器响应时应返回的 Content-Type 头部值。Content-Type 头部包含内容类型和字符编码，用分号隔开。如果你还记得读过 `index_jsp.java` 文件，它包含了翻译为以下内容的 Java 代码：

```java
response.setContentType("text/html;charset=UTF-8");
```

需要注意的是，上面的代码段与你在第 3 章 Hello-User 项目中看到的两行代码等效：

```java
response.setContentType("text/html");
response.setCharacterEncoding("UTF-8");
```

此外，这两者都等效于以下这行代码：

```java
response.setHeader("Content-Type", "text/html;charset=UTF-8");
```

如你所示，有多种方法可以完成相同的任务。`setContentType` 和 `setColorEncoding` 是便利方法。使用哪种方法取决于你；尽管通常应该选择一种并坚持使用以避免混淆。然而，由于从这里开始的大部分内容将基于基于 的，你将主要关注页面指令的 `contentType` 属性。

### 指令、声明、脚本段和表达式

除了在 JSP 中使用的 HTML 和 JSP 标签外，还有几种定义了 JSP 语言作用范围的结构。它们是：指令、声明、脚本段和表达式。简单来说，它们看起来像这样：

```jsp
<%@ this is a directive %>
<%! This is a declaration %>
<% this is a scriptlet %>
<%= this is an expression %>
```

### 使用指令

指令用于指导 JSP 解释器执行某些操作（如设置内容类型）或对文件进行假设（例如它使用的脚本语言）、导入一个类、在翻译时包含其他 JSP，或包含一个标签库。

### 使用声明

你使用声明在你的 JSP Servlet 类作用范围内声明某些内容。例如，你可以在声明标签内定义实例变量、方法或类。你需要记住，这些声明都是在生成的 JSP Servlet 类内部的，因此你定义的任何类都是 JSP Servlet 类的内部类。

### 使用脚本段

与声明一样，脚本段也包含 Java 代码。然而，脚本段的作用范围不同。虽然声明内的代码在翻译时会被复制到 JSP Servlet 类体内，并且必须在此声明某些字段、类型或方法，但脚本段会被复制到你之前看到的 `_jspService` 方法体中。在该方法执行范围内的任何局部变量在你的脚本段中都是有效的，任何在方法体内合法的代码在脚本段中也是合法的。因此你可以定义局部变量，但不能定义实例字段。你可以使用条件语句、操作对象并进行算术运算，这些在声明中是无法实现的。你甚至可以定义类（尽管听起来很奇怪，但在 Java 中在方法内进行类定义是合法的），但这些类在 `_jspService` 方法之外没有作用域。在声明中定义的类或变量可以在脚本段中使用，但

### 使用表达式

表达式包含可以写入客户端输出并返回内容的简单 Java 代码，表达式将代码的变量输出到客户端。因此，你可以在表达式中进行算术计算，得出一个可以显示的数值结果。你可以调用某些返回 String、数字或其他原始类型的方法，因为这会产生一个可显示的返回值。本质上，任何在赋值语句整个右侧合法的代码都可以放在表达式中。表达式在与脚本段相同的作用范围内执行；也就是说，表达式像脚本段一样被复制到 `_jspService` 方法中。

看看这段示例代码。它没有执行任何实用的功能，但它展示了在指令、声明、脚本段和表达式中可以执行的各种化操作。



```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%
  private final int code = 0;
  protected String cowboy = "rodeo";
// 下面的赋值不是声明性的，如果取消注释将是语法错误
//cowboy = "test";
  public long addFive(long number)
  {
      return number + 5L;
  }
  public class MyInnerClass
  {
  }
  new MyInnerClass instanceVariable = new MyInnerClass();
// WeirdClassWithinMethod 在方法作用域内，所以下面的声明
// 如果取消注释将是语法错误
```

```jsp
//WeirdClassWithinMethod bad = new WeirdClassWithinMethod();
<%
class WeirdClassWithinMethod
{
  WeirdClassWithinMethod weirdClass = new WeirdClassWithinMethod();
  MyInnerClass innerClass = new MyInnerClass();
  int seven;
  seven = 7;
}
%>
<%= "Hello, World" %> <br />
<%= addFive(12L) %>
```

## 整合在一起

在空项目的 Web 根目录下创建一个名为 `gibberish.jsp` 的 JSP 文件，并将之前的 gibberish 代码放入其中（或直接使用之前的代码）。

## 为代码编写注释

与所有其他语言一样，JSP 也有注释方法。共有三种不同方式：

- HTML 注释
- Java 行注释
- Java 块注释

HTML 注释用于注释掉不应由浏览器渲染的标记：

```html
<!-- This is a comment -->
```

Java 行注释用于注释掉单行 Java 代码：

```java
// This is a comment
```

Java 块注释用于注释掉多行 Java 代码：

```java
/*
  This is a block
  comment
*/
```

在执行此操作时需要考虑的是每个没有输出的 JSP 标签，以及每个指令（`directive`）、声明（`declaration`）和脚本段（`scriptlet`），都会向客户端输出一个空行。因此，如果你有许多导入的页面指令（`page directives`），后面跟着各种声明和脚本段，你的输出中可能会出现几十个空行。为了补偿这一点，JSP 开发者通常会将一个标签的指令链连接到此内容的开头：

```jsp
<%@ page import="java.util.Map">
<%@ page import="java.util.List">
<%@ page import="java.io.IOException" %>
```

这个示例的逻辑与之前完全相同，但结果是在输出顶部只产生一个空行。在“结合 Servlets 和 JSPs”章节中，你将学习相关的部署描述符设置，可以完全修剪这些空间。

## 使用指令

之前你已经接触了指令，这是一种以 `<%@` 开头并以 `%>` 结尾的 JSP 特性。这里有三种类型的指令，此时将对其进行讨论：

### 修改页面属性

你已经探索了页面指令的一些功能，例如 `contentType`、`language` 和 `import` 属性。页面指令还有许多其他功能。正如之前解释的，页面指令为你提供了对 JSP 如何翻译、渲染以及传回客户端的某些控制。以下是可能包含在此指令中的其他一些属性：

#### pageEncoding

指定你的 JSP 使用的字符编码，等同于在 `HttpServletResponse` 上 `setCharsetEncoding`。与其写 `contentType="text/html;charset=UTF-8"`，你可以写 `contentType="text/html" pageEncoding="UTF-8"`。

#### session

此值必须为 `true` 或 `false`，表示 JSP 是否参与 HTTP Session。默认是 `true`，这允许你访问 JSP 中的隐式 `session` 变量（在“在 JSP 中使用 Java（以及为什么不应该）”章节中介绍）。如果你将其设置为 `false`，则无法使用隐式 `session` 变量。如果你的应用程序不使用 session 且你想提高性能，将其设置为 `false` 可能是一个好主意。你可以学到更多关于 HTTP session 的信息。

#### isIgnored

此属性指定是否对此 JSP 进行表达式语言（`EL`）解析和翻译。你将在第 6 章中学习更多关于 `EL` 的知识。在 JSP 2.0 规范之前，默认值为 `true`，这意味着你需要在每个想要使用的 JSP 中都必须将其设置为 `false`。从 JSP 2.0 开始（你在本书中使用的是 JSP 2.3），默认值为 `false`，所以你完全不需要担心设置它。

#### buffer 和 autoFlush

这两个属性紧密相关，它们对应的默认值分别为 `"8kb"` 和 `true`。它们控制 JSP 的输出是在生成时立即发送到浏览器，还是进行缓冲并分批发送。`buffer` 属性指定 JSP 缓冲区的大小或为 `"none"`（输出将不会被缓冲），而 `autoFlush` 则指示缓冲区在达到其大小限制后是否自动刷新（`flushed`）。如果 `buffer` 设置为 `"none"` 且 `autoFlush` 设置为 `false`，则在 JSP 翻译为 Java 时会发生异常。如果 `autoFlush` 设置为 `false` 且缓冲区满了，则会发生异常。这是一种确保 JSP 不超过特定长度的方便方法。

当 `autoFlush` 设置为 `true`（默认值）时，缓冲区越小，刷新到客户端的频率就越高；缓冲区越大，刷新到客户端的数据就越少。通过 `autoFlush="none"` 完全禁用缓冲区可以提高你 JSPs 的性能，因为减少了内存消耗和 CPU 开销。然而，这并非没有副作用。不使用缓冲区会导致向浏览器发送更多的数据包，这可能会略微增加带宽消耗。此外，当响应的第一个字符开始流向客户端时，HTTP 响应头必须在响应之前提交并发送。由于由于，在缓冲区刷新之后，你无法设置响应头（`response.setHeader(...)`）或转发 JSP `<jsp:forward />`，而在禁用了缓冲器的 JSP 中，你完全无法设置响应头或转发 JSP。在某些情况下，这可能是提高服务器端性能而可以接受的牺牲。

#### errorPage

如果在执行 JSP 期间发生错误，此属性将指示容器将请求转发到哪个 JSP。

#### isError

此属性表示此 JSP 是否用作错误页面（默认默认为 `false`）。如果设置为 `true`，将启用页面上的隐式异常变量。你会在发生错误时进行跳转的 JSP 上，或者在容器中被定义为错误处理 JSP 的页面上执行此操作。

#### threadSafe

默认为 `true`，它告诉容器该 JSP 可以安全地同时处理多个请求。如果更改为 `false`，容器将逐个地请求此 JSP。一个好的经验法是永远不要更改它。记住，“如果你的 JSP 不是线程安全的，说明你做得方法错了。”

#### extends

此属性指定你的 Servlet 应该继承哪个类。使用此属性在不同的 Web 容器之间之间是不具可移植性的，而且这不应该是必要的。只需不要这样做即可。

#### 其他属性

在你的大多数 JSPs 中，`contentType`（以及可选的 `pageEncoding`）是页面指令中唯一会发生默认值更改的属性。`session` 和 `isErrorPage` 属性可能是其他属性中最常见的两个。偶尔，你可能需要启用缓冲功能。对于每个 JSP，你都应该评估你的选项，并决定应该更改哪些属性以适应应用程序的需求。

### 包含其他 JSP

包含其他 JSP 很容易的，但有一些规则和选项需要记住。你用来包含另一个 JSP 的第一个工具是包含指令。

```jsp
<%@ include file="path/to/some.jsp" %>
```

`file` 属性为容器提供了要包含的 JSP 路径。如果路径是绝对路径，则从 Web 根目录解析；如果路径相对路径，则从相同的目录解析。包含指令在翻译时求值；被包含的文件会被编译。为了演示这一点，请遵循以下步骤：

1. 在根目录下创建一个名为 `includer.jsp` 的文件，并粘贴以下代码：

   ```jsp
   <%@ include file="index.jsp" %>
   ```

2. 编译并调试你的应用程序，访问 `http://localhost:8080/includer.jsp`。你应该看到熟悉的页面，这意味着成功了。

3. 现在进入 Tomcat 工作目录并打开创建的 `includer_jsp.java` 文件。你会立即发现除了类名外，它与 `index_jsp.java` 完全相同。这是因为 JSP 是静态包含的。

另一种包含其他 JSP 的方法，会导致动态（运行时）包含而不是静态（翻译时）包含。使用 `<jsp:include>` 标签来实现这一点：

```jsp
<jsp:include page="/path/to/some.jsp" />
```

`jsp:include` 没有 `file` 属性；它有一个 `page` 属性。路径仍然相对于当前文件或从 Web 根目录解析，就像包含指令一样。它在翻译时并不包含。相反，被包含的文件是单独编译的。运行时，请求被转发到包含的 JSP，该 JSP 产生的输出被写入响应，然后控制权返回包含它的 JSP。通过在项目 Web 目录下创建一个名为 `dynamiccluder.jsp` 的文件并包含以下代码可以轻松验证这一点：

```jsp
<jsp:include page="index.jsp" />
```

再次编译调试并访问 `http://localhost:8080/dynamiccluder.jsp`，然后打开 Tomcat 创建的 `dynamiccluder_jsp.java` 文件。你现在可以看到这个 Java 文件的内容非常不同。文件中最感兴趣的一行是：

```java
org.apache.jasper.runtime.JspRuntimeLibrary.include(request, "index.jsp", out, false);
```

## 第 4 章 使用 JSP 显示内容

这会将请求和响应发送到另一个方法，该方法运行 include 指令将其内容包含在响应中并返回。

这两种包含方法各有优劣。include 指令的运行很快，因为它只被求值一次，而且在包含的 JSP 中定义的所有变量都在作用范围内，并可以被被包含的 JSP 引用。这种方法对 JSP（因此也适用于 `_jspService` 方法）的有效时间更长，这一点需要记住，因为编译后的 Java 方法的字节码长度不能超过 65,534 字节。`<jsp:include>` 标签不会引起这个问题，但它的性能也没有那么好，因为它在每次页面加载时都会被求值，而且在包含的 JSP 中定义的变量不在作用范围内，无法在被包含的 JSP 中使用。最终，你必须在需要包含文件时做出决定，但在某些情况下，include 指令是一个很好的选择。

> **注意**：默认情况下，Web 容器将翻译并编译以 `.jsp` 和 `.jspx` 结尾的文件（你稍后会学习到这种格式）作为 JSP。你可能还会遇到 `.jspf` 扩展名。片段通常不会被 Web 容器编译。尽管技术上你可以配置 Web 容器来编译它们（如果你想的话），但对于管理 JSP 文件的规则，有一些公认的最佳实践。JSP 文件代表无法独立运行的 JSP 片段，应该被包含而不是直接访问。这就是为什么 Web 容器通常不编译它们。实际上，在某些情况下，JSP 文件引用了只有在包含在另一个 JSP 文件中才存在的变量。因此，JSP 文件应仅使用 include 指令包含，在包含 JSP 中定义的变量必须在被包含 JSP 的作用范围内。

### 标签库

第 7 章和第 8 章将讨论其他标签库，现在提到它们是因为它们被包含的方式。使用 `taglib` 指令来引用标签库，这样你就可以在 JSP 中使用该标签库定义的标签。与 include 指令一样，`taglib` 指令非常简单：

```jsp
<%@ taglib uri="http://java.sun.com/jsp/jstl" prefix="c" />
```

`uri` 属性指定标签库定义的 URI 命名空间，`prefix` 属性定义了你引用库中标签的别名。你将在第 7 章中学习更多关于它的含义。

### 使用 `<jsp>` 标签

所有的 JSP 都支持一种 XMLNS 为 `jsp` 的特殊标签。该标签有许多用途和功能。在 JSP 文档（你在在本节最后一部分学习的 JSP 的 XML 版本）中使用的功能，或者来自旧版本 JSP 的遗留（在旧版本中某些事情比现在困难得多，因此这里没有介绍）。但是，你应该学习该标签的几个有用功能。

### 创建你的第一个 JSP

你已经学习了 `<jsp:include>` 以及它与 include 指令的区别。

类似的标签是 `<jsp:forward>` 标签。它允许你将请求从当前执行的 JSP 转发到其他 JSP。与 `<jsp:include>` 不同，请求不会返回到原始 JSP；客户端浏览器看不到变化。此外，在发生转发时，写入响应的 JSP 内容将保留在响应中；它不会像重定向（`redirect`）那样被擦除。使用 `<jsp:forward page="some/other/page.jsp" />` 非常简单：

在此示例中，请求被转发到 `/some/other/page.jsp`。在客户端浏览器之前生成的任何响应内容都会被忽略且不被求值。此标签与 `<jsp:include>` 标签不同。如果 `<jsp:forward>` 之后的代码没有被忽略，那么此标签的行为将就像 `<jsp:include>` 标签。

其他相关的标签有 `<jsp:useBean>`、`<jsp:getProperty>` 和 `<jsp:setProperty>`。`<jsp:useBean>` 在页面上声明 JavaBean 的属性，`<jsp:getProperty>` 从使用 `<jsp:useBean>` 声明的 bean 中获取属性（使用 getter 方法）。同样，`<jsp:setProperty>` 设置属性（使用 setter 方法）。在这种情况下，Java bean 是任何实例化的对象。`<jsp:useBean>` 实例化一个类来创建 bean，然后可以使用其他 bean 标签、自定义标签以及 JSP 脚本段（`scriptlets`）和表达式来访问该 bean。以这种方式声明 bean 的优点是，它让 bean 对其他 JSP 标签可用；如果你只是在脚本段中声明 bean，它将只对脚本段和表达式可用。

最后，是 `<jsp:plugin>` 标签，它是一个在渲染的 HTML 中嵌入 Java Applet 的方便工具。该标签消除了由于不小心弄乱 `<object>` 和 `<embed>` 标签精细结构的风险，而这些标签是让 Java Applet 在所有浏览器中运行所必需的。它为你处理这些 HTML 标签，使 Applet 能够在所有支持 Java 插件的主流浏览器中运行。这是一个使用 `<jsp:plugin>` 标签的示例：

```jsp
<jsp:plugin type="applet" code="MyApplet.class" jversion="1.8">
  <jsp:params>
    <jsp:param name="appletParam" value="paramValue"/>
  </jsp:params>
  <jsp:fallback>
    你正在使用的浏览器不支持 Java Applets。你可能考虑切换浏览器。
  </jsp:fallback>
</jsp:plugin>
```

注意 `<jsp:plugin>` 还可以包含标准的 object/embed HTML 属性，如 name、align、height、width、hspace vspace。这些属性会被复制到 HTML 标记中。

> **注意**：Java Applets 与 Web 应用程序是完全不同的主题，并且不在本书的范围内。如果你想了解更多关于 Java Applets，大多数初级 Java 教程都涵盖了这个主题。

### 在 JSP 中使用 JAVA（以及为什么你不应该这样做！）

在本节中，我们将通过替换上一节的 HelloUser 项目，进一步探索在 JSP 中的 Java。然后我们将简要说明为什么在 JSP 中使用 Java（以及通过部署描述禁用它）。

### 在 JSP 中使用隐式变量

JSP 文件有几个在脚本和表达式中使用的隐式变量（对象）。它们之所以被认为是隐式的，是因为你不需要在代码的任何地方定义或声明它们。JSP 规范要求翻译器和编译器提供这些变量，并具有精确的名称。变量的作用域定义在执行 JSP 的 Servlet 开头（在 Tomcat 8.0 中的 `jspService` 方法）。这意味着你不能在 JSP 内部的任何声明中使用它们。声明具有作用域。你可以通过查看上一节中检查的任何 JSP 的 `jspService` 方法，看到隐式变量是如何定义的示例：



```java
public void jspService(final java.servlet.http.HttpServletRequest request,
    final java.servlet.http.HttpServletResponse response)
{
    final java.servlet.jsp.PageContext pageContext;
    java.servlet.http.HttpSession session = null;
    final java.servlet.ServletContext application;
    final java.servlet.ServletConfig config;
    final java.servlet.jsp.JspWriter out = null;
    final java.lang.Object page = this;
    final java.servlet.jsp.JspWriter jsp_page_out = null;
    final java.servlet.jsp.PageContext jsp_page_context = null;

    try {
        response.setContentType("text/html;charset=UTF-8");
        pageContext = jspFactory.getPageContext(this, request, response,
            null, true, 8192, null);
        jsp_page_context = pageContext;
        application = pageContext.getServletContext();
        config = pageContext.getServletConfig();
        session = pageContext.getSession();
        out = pageContext.getWriter();
        jsp_out = out;
    }
}
```

这段代码并不是代码的全貌，但代码的重要部分已经加粗了，以便你理解发生了什么。代码强调了 JSP 规范要求的隐式变量的声明或赋值（或两者兼有）。未加粗的变量（如 `jsp_out` 或 `jsp_page_context`）是 Tomcat 特有的变量，不保证在其他容器中存在且绝不应该在你的 JSP 中使用。

# 在 JSP 中使用 Java（以及为什么你不应该这样做！）

存在且绝应该在你的 JSP 中使用。这段代码中有八个隐式变量，但 JSP 规范定义了九个隐式变量。现在观察这些隐式变量，你就会理解为什么缺少了一个。

## request 和 response

`request` 变量是 `HttpServletRequest` 的实例，`response` 变量是 `HttpServletResponse` 的实例，这两个你已经在第三章中学习过了。在 Servlet 中对请求的任何操作在 JSP 中都可以完成，包括获取请求参数、设置属性，甚至从响应体中读取。你在上一章学到的规则同样适用于这里。然而，在 JSP 中对响应对象的操作上有一些限制。这些限制并不是合同上的限制，而是在运行时强制的，因为它们可能会导致意想不到的行为或错误。例如，你不应该调用 `getWriter()` 或 `getOutputStream()`，因为 JSP 已经在向响应输出写入内容了。你也不应该设置内容类型或字符编码、刷新缓冲区或更改缓冲区大小。这些都是 JSP 会执行的操作，如果你的代码也执行了这些操作，就会导致问题。

### session

该变量是 `HttpSession` 的实例。你将在下一章学习更多关于 session 的知识。记得上一节提到的，page 指令有一个 `session` 属性，默认值为 `true`。这个 session 变量在之前的代码示例中可用，并且在你所有的 JSP 中都会默认可用。如果你将 page 指令的 `session` 属性设置为 `false`，则 JSP 中的 session 将不会定义且无法使用。

### out

`JspWriter out` 可供你在所有 JSP 中使用。它是一个 `Writer`，就像你通过 `HttpServletResponse` 的 `getWriter()` 方法得到的一样。由于某种原因你需要直接向响应写入，你应该使用 `out` 变量。在很多情况下，你只需要使用表达式或在 JSP 中编写 HTML 内容即可。

## application

这是 `ServletContext` 接口的实例。回想第三章，该接口允许你访问整个 Web 配置，包括所有的上下文参数。为什么这个变量被命名 `application`、`context` 或 `servletContext` 是个谜。

## config

`config` 变量是 `ServletConfig` 接口的实例。与 `application` 变量不同，它的名称实际上反映了它的本质。正如你在第三章中学到的，你可以使用此对象访问 JSP Servlet 的配置，例如 Servlet 初始化参数。

## pageContext

该对象是 `PageContext` 类的实例，提供了多个方便的方法用于获取请求属性和会话属性、访问请求和响应、包括其他文件以及转发请求。

## 第 4 章 使用 JSP 显示内容

你可能永远不需要在 JSP 中使用这个类。但在第 8 章编写自定义 JSP 标签时，它会非常有用。

## page

`page` 变量是一个很有意思的研究对象。它是 `java.lang.Object` 的实例，这起初让它看起来毫无用处。然而，本质上它是 JSP Servlet 对象中的该变量。因此，你可以将其强制转换为 `Servlet` 并使用在 Servlet 接口上定义的方法。它还是一个 `javax.servlet.jsp.JspPage`（继承自 Servlet）以及一个 `javax.servlet.jsp.HttpJspPage`（继承自 JspPage），你可能永远没有理由使用这个变量。如果以后支持其他的 JSP 脚本语言，它可能会有用。JSP 2.3 规范第 1.8.3 节注释“a”提到，当脚本语言为 Java 时，`page` 是 `this` 的同义词。因此，任何你可以通过 `page` 做到的事（例如设置 Servlet 名称或在 JSP 声明中定义的其他实例变量）都可以通过 `this` 完成。

## exception

这就是上一个示例中缺失的变量。回想上一节，你可以通过 page 上的 `isErrorPage` 属性指明 JSP 的目的是处理错误。这样你就可以让 `exception` 变量在 JSP 内可用。由于 `isErrorPage` 的默认值为 `false` 且你没有在任何地方使用它，因此 `exception` 变量在任何 JSP 中都没有定义。如果你创建一个 `isErrorPage` 设置为 `true` 的 JSP，隐式的 `exception` 变量（一个 `Throwable`）会被自动定义。

> 你可以在 JSP 规范页面阅读 JavaServer 2.3 规范文档。

## 测试隐式变量

现在你已经理解了隐式变量及其用途，应该通过编写一些使用隐式变量的 JSP 代码来探索。在你的项目中，在 web 根目录下创建一个 `greeting.jsp` 文件，并将以下代码放入（或使用 Hello-User-JSP 项目）：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%
    private static String DEFAULT_USER = "Guest";

    String user = request.getParameter("user");
    if (user == null)
        user = DEFAULT_USER;
%>

<!DOCTYPE html>
<html>
<head>
    <title>Hello User Application</title>
</head>
<body>
    Hello, <%= user %>!<br /> <br />

    <form action="greeting.jsp" method="POST">
        Enter your name: <br />
        <input type="text" name="user" /><br />
        <input type="submit" value="Submit" />
    </form>
</body>
</html>
```

将此代码与上一章 Hello-User 项目中 `HelloServlet.java` 的代码进行比较。要写的少得多。注意代码是如何在脚本段（scriptlets）之间进出的，只在逻辑需要的地方使用 Java，而让脚本段保持 HTML 的纯洁。这实现了相同的功能。现在编译并调试项目，并在浏览器中访问 `http://localhost:8080/hello-world/greeting.jsp`。你应该能看到类似图 4-1 的页面。尝试不同的复选框组合，并验证它的行为与第 3 章中的 Hello-User 项目一致。将 for 循环中使用 `out` 替换为 `<%= page %><li></li>`，当你再次编译并运行项目时，输出不应该发生变化。

最后，创建一个 `contextParameters.jsp` 文件来探索 `application` 隐式变量的使用以及上下文隐式参数的检索。或者使用 Hello-JSP 项目中的文件。

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<html>
<head>
  <title>Hello User Application</title>
</head>
<body>
  settingOne: <%= application.getParameter("settingOne") %>,
  settingTwo: <%= application.getParameter("settingTwo") %>
</body>
</html>
```

此外，你需要在部署描述符中定义一些上下文参数，就像第三章中那样：

```xml
<context-param>
    <param-name>settingOne</param-name>
    <param-value>foo</param-value>
</context-param>
<context-param>
    <param-name>settingTwo</param-name>
    <param-value>bar</param-value>
</context-param>
```

![](img/9c2d45f6d547f72cb870b3a991f62ef6_128_0.png)

图 4-1

现在编译、调试并导航到 `http://localhost:8080/hello-world/contextParameters.jsp`。与基于 Servlet 的 Hello-User 项目一样，你应该可以在初始化参数（init parameters）中看到上下文的值。

# 为什么你不应该在 JSP 中使用 Java

在 JSP 中使用 Java 有许多优势，除了目前为止指出的用途外，你在阅读这段段落时可能还会想到其他用途。在 JSP 中使用 Java 最酷的一点是，任何你在普通 Java 类中能做的事情，在 JSP 中都能做得到。然而，在 JSP 中使用 Java 最大的危险之一在于，几乎你在普通 Java 类中能做的事情，在 JSP 中都能做得到。这些话听起来很疯狂，但它们是事实。想想你在 Java 代码中可以做的所有事情。这里有几点可以帮助你。

你可以连接、查询和操作关系型数据库（或取决于情况的 NoSQL 数据库）。你还可以访问和写入服务器文件系统上的文件。你可以连接到远程服务器，执行 REST Web 服务事务并与系统外设备交互。你可以进行数字计算，启动一个拥有十亿个节点的二叉树，遍历大型数据集寻找可疑数据，或者搜索文档对象模型（DOM）中的特定节点。现在如果你认为这些任何一点在 JSP 中都是好主意，请举手。

Java 是一种强大的语言，而所有力量尽在指尖的问题在于它太难不使用了。根据应用程序的不同，其中任何任务都可能需要在 Web 应用程序中执行。考虑一下：在一个结构良好的应用程序中，将数据库访问、文件管理和数字计算代码放在同一个类中合适吗？可能不合适。很可能，你会有几个执行专门功能的类，然后在需要时使用其他类。JavaServer Pages 是一种为表示层（也称为视图）设计的技术。虽然可以将数据库访问与表示层混合，或将数字计算与表示层混合，但这不是一个好主意。函数式语言、脚本语言和其他从文件头执行到文件尾的语言（如 PHP）确实有它们的用处。由于其他原因，如果你看重优雅性和严格的面向对象结构，你可能不会选择 Java 作为你的选择之一。

此外，在大多数组织中，用户界面负责创建表示层。这些开发者很少编写 Java 代码的经验，为他们提供这种能力可能是危险的。为他们提供一套功能不那么强大的工具来工作通常是合理的。

在一个结构良好、代码整洁的应用程序中，表示层与业务逻辑分离，业务逻辑同样与数据持久层分离。实际上，可以创建在 JSP 中不包含任何 Java 代码就能显示动态内容的 JSP。这使得应用程序开发者能够专注于业务和数据逻辑，而用户界面人员则在 JSP 上工作。你可能会好奇这如何可能，但你不会失望的。你将在下一节中学习第一步，并在第 6、7、8 章中探索更强大的 JSP 技术。

## 结合 Servlet 和 JSP

在本章的剩余部分中，你将从第 3 章开始改进客户支持应用程序。你可以跟随示例，并在 wrox.com 下载站的 Customer-Support-v2 项目中找到完整的源代码。在处理复杂逻辑、数据验证、数据持久化和详细的表示层时，使用 Servlet 和 JSP 的结合比专门使用其中一个是最合理的。在本节中，你将客户支持的逻辑与表示层分离。

## 在部署描述符中配置 JSP 属性

在本章稍早，你学习了页面指令（page directive）以及它提供的许多属性，这些属性允许你配置 JSP 如何被翻译、编译和执行。然而，如果你有许多具有相似属性的 JSP，在每个 JSP 文件顶部使用此页面指令将非常繁琐。幸运的是，有一种在部署描述符中配置常用 JSP 属性的方法。在 `web.xml` 文件中（除了 `<display-name>` 外应该是空的），添加以下内容：

## 结合 Servlet 和 JSP

```xml
<jsp-config>
  <jsp-property-group>
    <url-pattern>*.jsp</url-pattern>
    <url-pattern>*.jspx</url-pattern>
    <page-encoding>UTF-8</page-encoding>
    <scripting-invalid>false</scripting-invalid>
    <include-prelude>WEB-INF/jsp/base.jsp</include-prelude>
    <trim-directive-whitespaces>true</trim-directive-whitespaces>
    <default-content-type>text/html</default-content-type>
  </jsp-property-group>
</jsp-config>
```

## 理解 JSP-config 属性组

JSP-config 包含任意数量的 `<jsp-property-group>` 标签。这些属性组用于区分不同的 JSP 组。例如，你可能为 `/WEB-INF/jsp` 文件夹中的所有 JSP 定义一组通用属性，并为 `/WEB-INF/jsp/helper` 文件夹中的所有 JSP 定义另一组通用属性。通过为每个 `<jsp-property-group>` 定义 `<url-pattern>` 标签来区分属性组。在之前的代码中，`<url-pattern>` 标签表示该属性组适用于任何以 `.jsp` 结尾的文件。如果你想以这种方式处理一个文件夹与另一个文件夹的 JSP，你可以有两个（或更多）`<jsp-property-group>` 标签，一个具有 `<url-pattern>/WEB-INF/jsp/admin/*.jsp</url-pattern>`，另一个具有 `<url-pattern>/WEB-INF/jsp/helper/*.jsp</url-pattern>`。

在处理 `<url-pattern>` 时考虑一些重要规则：

- 如果应用程序中的某个文件同时匹配 Servlet 映射和 JSP 属性组中的 `<url-pattern>`，则更具体的胜。例如，如果匹配的 `<url-pattern>` 是 `*.jsp` 而另一个是 `/WEB-INF/jsp/admin/*.jsp`，则 `/WEB-INF/jsp/admin/*.jsp` 胜。如果 `<url-pattern>` 标签相同，则先出现的属性组胜。
- 如果某个文件匹配多个属性组中的 `<url-pattern>`，则最具体的匹配胜。如果两个或多个特定的匹配相同，则先出现的属性组胜。
- 如果某个文件匹配的多个属性组都包含 `<include-prelude>` 或 `<include-coda>`，所有属性组的包含规则都适用于该文件，尽管只使用了其中一个。

为了理解最后一点，考虑以下属性组：

```xml
<jsp-property-group>
  <url-pattern>*.jsp</url-pattern>
  <url-pattern>*.jspx</url-pattern>
  <page-encoding>UTF-8</page-encoding>
  <include-prelude>WEB-INF/jsp/base.jsp</include-prelude>
</jsp-property-group>

<jsp-property-group>
```



<url-pattern>WEB-INF/jsp/admin/*.jsp</url-pattern>

<url-pattern>WEB-INF/jsp/admin/*.jsp</url-pattern>

<page-encoding>ISO-859-1</page-encoding>

<include-prelude>WEB-INF/jsp/admin/include.jsp</include-prelude>

</jsp-property-group>

```

名为 `WEB-INF/jsp/user` 的文件只会匹配第一个属性组。它将具有 UTF-8 编码，`WEB-INF/jsp/base.jsp` 文件将被包含在开头。相反，`WEB-INF/jsp/admin/user` 会匹配两个属性组。因为第二个属性组是更具体的匹配，该文件将具有 ISO-859-1 编码。然而，`WEB-INF/jsp/base.jsp` 和 `WEB-INF/jsp/include.jsp` 都会包含在该文件的开头。这可能会变得非常困惑，因此敦促你保持属性组尽可能简单。

### 使用 JSP 属性

Customer Support 项目中的 `<include-prelude>` 标签告诉容器在属于此属性组的每个 JSP 开头包含 `/WEB-INF/jsp/base.jsp` 文件。这对于定义通用变量、标签库声明或所有 JSP 可用的资源非常有用。同样，`<include-coda>` 标签定义了每个 JSP 末尾包含的文件。你可以在单个 JSP 组中多次使用这两个标签。例如，你可以创建 `header.jsp` 和 `footer.jsp` 文件，分别包含在每个 JSP 的开头和结尾。这些文件可以包含头部和底部 HTML 内容，作为应用程序的模板。当然，当你这样做时必须小心，因为你很容易在无意的地方包含这些文件。

`<page-encoding>` 标签与页面指令的 `pageEncoding` 属性相同。默认情况下，你只需要指定 `<page-encoding>` 为 UTF-8，将你的 JSP 编码从 `text/html;ISO-859-1` 更改为 `text/UTF-8`。你还可以使用 `<default-content-type>` 标签用其他默认内容类型覆盖 `text/html`。

一个特别实用的属性是 `<trim-directive-whitespaces>`。此属性指示 JSP 翻译器从响应输出中删除由指令、声明、脚本和其他 JSP 标签创建的纯空白文本。在本章稍早，你学习了如何将一个指令的结尾链到下一个指令，以防止响应中出现额外的换行。这会为你处理好，让你编写更整洁的代码。

之前还提到了使用部署描述符完全禁用 Java JSP 的。`<scripting-invalid>` 标签设置了代码中的默认值，`false` 允许组中的所有 JSP。在书的后面，你把此值改为 `true`。一旦变为 `true`，在匹配的 JSP 中使用 Java 将导致翻译错误。`<el-ignored>` 标签类似于页面指令的 `isELIgnored` 属性。如果为 `true`，则 JSP 组中禁止表达式语言（如果使用了 EL，将导致翻译错误）。这默认为 `false`（允许表达式语言），你可以保持那样。

还有几个你可能永远不会使用的 JSP 属性组标签。`<is-xml>` 标签表示匹配的 JSP 是 JSP 文档（你将在下一节中学习）。`<deferred-syntax-allowed-as-literal>` 标签是在第 6 章中学习的表达式特性。`<buffer>` 设置了你在本章稍早学习的页面指令的 `buffer` 属性。最后，`<error-on-undeclared-namespace>` 表示在匹配的 JSP 中使用未知命名空间的标签时是否抛出错误，默认为 `false`。

```
request.setAttribute("ticketDatabase", this.ticketDatabase);

request.getRequestDispatcher("/WEB-INF/jsp/view/listTickets.jsp");
forward(request, response);
```

### 更新后的客户支持应用程序

此时，你的 Servlet 代码看起来应该没以前那么杂乱了。你已经将表示代码移动到了 JSP 中，并将重点集中在 Servlet 的逻辑上。在之前的版本 `TicketServlet` 中有两个方法，`writeHeader` 和 `writeFooter`，它们现在不再被使用，可以删除。这些方法虽然让在 Servlet 中编写表示代码变得稍微简单一些，但现在你不需要它们了。`doGet` 和 `doPost` 必须经过更新，以反映它们所调用的方法签名的变化。

编译客户支持应用程序并在你的 IDE 调试器中运行 Tomcat。在浏览器中导航到 `http://localhost:8080/support/`。由于 `.jsp` 文件中的重定向代码，你应该被重定向到 `http://localhost:8080/support/tickets`。你应该能看到图 4-2 所示的页面。创建几个工单，其中一些上传附件，另一些没有；查看工单；并下载附件。总的来说，该应用程序的功能与第 3 章中的版本 1 完全一致。然而，现在你不再用 Java 编写表示层，改进和扩展应用程序变得简单得多了。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_136_0.png)

图 4-2

在下一章，你将通过引入会话支持以及向工单添加注释的功能继续改进客户支持应用程序。

### 关于 JSP 文档 (JSPX) 的说明

在本章的开头，你看到了一种名为 JSP 文档的技术，它们以 `.jspx` 扩展结尾。它们并没有作为标准 JSP 被广泛使用，尽管它们支持相同的功能，但实现方式不同。正如本节所示，使用 JSP 文档代替标准 JSP 带来的难度和代码增加是不容忽视的。此外，由于 JSP 文档的普及率较低，找到使用 JSP 文档的示例和代码样本较少，而且很难在论坛和邮件列表中找到具有 JSP 文档经验的用户来帮助你可能遇到的任何问题。出于这些原因，本书没有使用 JSP 文档。只有在本章中，你才会看到 JSP 文档的示例，目的是理解这两种技术之间的区别。尽管如此，在你倾向于使用纯 XML 工作的情况下，该技术是存在的。

JSP 文档是 XML 文档（因此得名如此），因此你见过的许多功能（如指令）无法以相同的方式工作。XML 文档必须遵守严格的模式（schema），否则将解析失败。使用 JSP 文档代替标准 JSP 的主要优势是更容易在编译时而不是运行时检测 JSP 中的问题。然而，在许多情况下，处理 JSP 文档所增加的成本并不值得。表 4-1 列出了几种 JSP 特性，并将其语法与 JSP 文档语法进行了对比。

### 表 4-1：JSP 特性与 JSP 文档特性对比

| 特性 | JSP 语法 | JSP 文档语法 |
| --- | --- | --- |
| 页面指令 | `<%@ page %>` | `<jsp:directive.page />` |
| 包含指令 | `<%@ include ... %>` | `<jsp:directive.include />` |
| 标签库指令 | `<%@ taglib ... %>` | `xmlns:prefix="Library URI"` |
| 声明 | `<%! ... %>` | `<jsp:declaration> ... </jsp:declaration>` |
| 脚本段 | `<% ... %>` | `<jsp:scriptlet> ... </jsp:scriptlet>` |
| 表达式 | `<%= ... %>` | `<jsp:expression> ... </jsp:expression>` |
| 注释 | `<%-- ... --%>` | `<!-- ... -->` |

你应该注意到此任务中的两种模式：

- 一切都是 JSP 标签指令，声明、脚本段和表达式全都是带有 JSP 命名空间前缀的 XML 标签。唯一的异常是标签库指令，它变成了根文档标签的一个属性。

- 你不再需要区分 JSP 注释和 XML 注释。所有的注释都是 XML 注释。（当然，对于声明和脚本段，你仍然可以使用 Java 注释。）

为了演示这如何改变一个文档，请考虑列表 4-1。这是一个简单的 JSP 文件，包含了本章涵盖的所有功能。然后，将该代码与列表 4-2 进行对比，即 JSP 文档的等价物。

### 列表 4-1：标准 JSP 文件

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%@ include file="WEB-INF/jsp/base.jsp" %>

<%@ taglib prefix="c" uri="http://www.sun.com/jsp/jstl/core" %>

<%!
    private static final String DEFAULT_USER = "Guest";
%>

<%
    String user = request.getParameter("user");
    if (user == null)
        user = DEFAULT_USER;
%>

<!--This code is commented -->

<!DOCTYPE html>

<html>

<head>

    <title>Hello User Application</title>

</head>

<body>

    Hello, ${user}<br /><br>

    <form action="greeting.jsp" method="POST">

        Enter your name;

    </form>

</body>

</html>
```

### 关于 JSP 文档 (JSPX) 的一个说明

列表 4-1 的文档等价物。注意指令、声明、脚本段、表达式和注释是如何发生变化的。特别注意 XML doctype、`<jsp:root>` 元素和 XML 属性。如你所见，JSP 文档比标准 JSP 更难处理得多。

### 列表 4-2：列表 4-1 的 JSP 文档等价物

```xml
<?xml version="1.0" encoding="UTF-8"?>

<jsp:root xmlns="http://www.w3.org/1999/xhtml" version="2.0"
          xmlns:jsp="http://www.sun.com/JSP"
          xmlns:c="http://www.sun.com/jsp/jstl/core">

    <jsp:directive.page contentType="text/html;charset=UTF-8" language="java" />

    <jsp:directive.include file="WEB-INF/jsp/base.jsp" />

    <jsp:declaration>
        private static final String DEFAULT_USER = "Guest";
    </jsp:declaration>

    <jsp:scriptlet>
        String user = request.getParameter("user");
        if (user == null)
            user = DEFAULT_USER;
    </jsp:scriptlet>

    <!--<jsp:expression>*This code is commented*</jsp:expression> -->

    <!DOCTYPE html>

    <html>

    <head>

      <title>Hello User Application</title>

    </head>

    <body>

      Hello, <jsp:expression>user</jsp:expression>!<br /><br />

      <form action="greeting.jsp" method="post">

        Enter your name;

        <input type="text" name="user" />

        <input type="submit" value="Submit" />

      </form>

    </body>

    </html>

</jsp:root>
```



### 总结

在本章中，你探索了 JSP 的世界，并学习了它们如何通过简化向响应输出 HTML 标记的任务让生活变得更容易。你介绍了指令、声明、脚本段和表达式。你学习了在 JSP 中注释的各种方法，以及在 JSP 文件中包含 Java 代码的许多方法。你还发现了 JSP 中可用的隐式 Java 变量，并阅读了为什么不建议使用脚本段和声明。最后，你应用了这些原则，通过将 JSP 属性添加到部署描述并将 Servlet 中的业务逻辑与 JSP 中的表示分离，改进了客户支持应用程序。

在下一章中，你将学习 HTTP 会话、其目的以及如何在 Java EE Web 中使用它们。

# 5 使用会话维护状态

- 为什么会话是必要的
- 处理 Cookie 和 URL 参数
- 如何在会话中存储数据
- 让会话变得有用
- 如何对使用会话的应用程序进行集群化

### 理解为什么需要 Session

到目前为止，你已经学习了 Web 应用程序、Web 容器、Servlets、JSP 以及 Servlets 和 JSP 如何协同工作。你还学习了请求的生命周期，此时你应该清楚，你所介绍的这些工具并不能让你关联来自同一客户端的多个请求，并在这些请求之间共享数据。你可能认为可以使用 IP 地址作为标识符，认为在一段时间内来自同一 IP 的请求都属于该客户端。遗憾的是，由于网络地址转换（NAT），这种方法并不可靠。校园内成千上万的学生实际上可以使用同一个 IP 地址，它们隐藏在 NAT 路由器之后。由于这个原因，HTTP Session 的概念已几乎被所有 HTTP 服务器端技术采用，Java EE 也在其规范中内置了对 Session 的支持。

并不是每个应用都需要 Session。你在书中看到的 Hotel Worlds 显然不需要 Session。到目前为止，它更像是一个匿名留言板。但如果你考虑到跨国小部件公司（MWC）的客户支持，你可能会很快意识到在某个时刻你必须创建用户账户，而且这些用户需要登录应用程序。客户请求可能包含隐私信息，例如其他客户不应该看到的配置文件。显然，你需要一种方法来限制对支持单的访问，使得发布问题的客户和 MWC 支持人员可以访问任何特定的支持单。你可以让用户在访问每个页面时都提供用户名和密码，但可以肯定客户不会对这种解决方案感到满意。

### 维护状态

Session 用于在一个请求和下一个请求之间维持状态。HTTP 请求本身是完全无状态的。从服务器的角度来看，当用户的 Web 浏览器打开套接字时请求开始，当服务器向客户端发送最后一个数据包并关闭连接时请求结束。此时，用户和服务器之间不再有联系，当下一个请求进来时，根本没有办法将下一个请求与上一个请求关联。

应用程序通常无法以这种方式正常运行。一个经典的例子是在线购物网站。如今几乎每个在线购物网站都要求你在购买之前创建用户名和密码，即使你没有这样做。当你浏览商店时，发现了一个这样的产品，于是将其加入购物车。你继续浏览商店发现了另一个你喜欢的产品，于是也将其加入购物车。当你查看购物车时，你会发现这两个产品都在，而且它们来自同一台电脑上的同一个浏览器，并与你的购物车关联。没有其他人能看到你的购物车或其中的物品——它与你的电脑和浏览器唯一绑定。这种场景是现实生活的一种类比。你进入杂货店，一进门，就拿了一个购物车或篮子。（你从服务器获得了一个 Session。）你穿过商店，沿路挑选物品，并将它们放入购物车（将它们添加到 Session）。当你到达收银台时，你从购物车中取出物品交给收银员，收银员扫描并收钱。（你使用 Session 进行结账。）当你走出门时，归还购物车或篮子。（你关闭浏览器或注销，结束了你的 Session。）

在这个例子中，购物车或篮子在你穿过商店时维护了你的状态。如果没有购物车，你和商店都无法记录购买所需的所有物品。如果请求之间不维护状态，你就必须“走进去”，拿一件物品，付钱，“走出去”（结束），然后为你想要购买的每个物品重复整个过程。Session 是维护请求之间状态的引擎，没有了它们，Web 世界将是一个完全不同的地方。

### 记住用户

另一个需要考虑的场景是论坛网站。在几乎所有的在线论坛中，用户通过用户名或“句柄”被识别。当用户进入论坛时，他登录并提供用户名和密码来证明自己的身份。（用户名/密码认证作为身份证明的优点将在第 2.5 节中讨论。）从那时起，他可以发布论坛帖子、回复帖子、与其他用户进行私信交流、向管理员举报帖子或回复，并可能将帖子标记为收藏。注意，用户在那个时间段内只登录了一次。系统需要一种方法在每个请求之间记住他是谁，而 Session 提供了这种可能。

### 启用应用程序工作流

用户通常需要某种形式的工作流来使用高级 Web 应用程序完成任务。在为新闻网站创建发布新闻文章的情况下，记者可能会先进入一个屏幕，在其中输入标题、副标题和正文，并适当格式化这些元素。在下一个页面，她可能会选择与文章相关的一个或多个照片，并指示它们应该如何显示。她可能还会上传或录一些视频放在文章中。最后，她可能会看到相似文章列表或搜索字段来查找相似文章，以便指示哪些文章应该放在“相关文章”框中。

在完成所有这些步骤后，文章将被发布。这种场景代表了工作流的概念。工作流包含许多步骤，每一步都是完成任务的一部分。为了将所有这些步骤连接起来以完成工作流，请求之间必须维持状态。购物车示例是更广泛的工作流领域的一个子集。

### 使用 Session Cookie 和 URL 重写

现在你理解了 Session 的重要性，你可能好奇它们是如何工作的。这涉及两个不同的部分：首先是 Session 背后的通用理论及其实现方式；其次是 Java EE 中 Session 实现的具体细节。本节涵盖了这两者。

在 Session 的通用理论中，Session 是由服务器或 Web 应用程序管理的某些文件、内存对象或容器，其中包含各种数据。这些数据元素可以是用户名、购物车、工作流详情等。用户的浏览器并不持有或维护这些任何一个内容。它完全由服务器或 Web 应用程序管理。唯一缺失的是该容器与用户浏览器之间的链接。出于这个目的，Session 会被分配一个随机生成的字符串，称为 Session ID。第一次创建 Session 时（由于接收到请求），Session ID 会作为响应的一部分传回给用户的浏览器。用户浏览器的每个后续请求都会以某种方式包含 Session ID。当应用程序收到带有 Session ID 的请求时，它可以将现有 Session 与该请求关联起来。这如图 5-1 所示。

![](img/9c2d45f6d547f72cb870b3a991f62ef_143_0.png)

图 5-1

> 注意：你可能疑惑为什么 Session ID 是随机的而不是顺序 ID。原因是显而易见的：顺序 ID 是可预测的，而可预测的 ID 会让劫持他人 Session 变得轻而易举。

需要解决的难题是 Session ID 如何在服务器和浏览器之间传递。有两种技术用于实现此：Session Cookie 和 URL 重写。

### 理解 Session Cookie

幸运的是，HTTP 1.1 已经存在一种技术，允许服务器将 Session ID 发回浏览器，以便浏览器在未来的请求中包含这些 ID。这种技术就是 HTTP Cookie。如果你不熟悉 Cookie，它们本质上是一种机制，数据可以通过 `Set-Cookie` 响应头从服务器传递给浏览器，存储在用户的计算机上，并通过 `Cookie` 请求头从浏览器传输到服务器。Cookie 有各种属性，如域名、路径、过期日期或时间、安全标志标记和 HTTP-only 标记。

`Domain` 属性指示浏览器应该为哪个域名发回 Cookie，而 `Path` 属性允许将 Cookie 进一步限制在相对于域名的特定 URL。每当浏览器发出任何类型的请求时，它都会找到与该站点域名和路径匹配的所有 Cookie，并将这些 Cookie 随请求发送。`Expires` 定义了 Cookie 的绝对过期日期，而互斥的 `Max-Age` 属性定义了 Cookie 过期前的秒数。如果 Cookie 的过期日期在过去，浏览器立即将其删除。（这就是删除 cookie 的方法——将它的过期时间设置为过去的时间。）如果 cookie 没有具有 `Expires` 或 `Max-Age` 属性，它将在浏览器关闭时被删除。如果存在 `Secure` 属性（它不需要值），浏览器将仅通过 HTTPS 发送 cookie。这可以防止 cookie 被明文传输。`HttpOnly` 属性将 cookie 限制在浏览器请求中。其他技术（如 JavaScript 和 Flash）将无法访问 cookie。

Web 应用程序使用 cookie 在客户端存储会话 ID，以便在每次请求时将其发送到服务器。在 Java EE 应用中，此会话的默认名称为 `JSESSIONID`。检查客户端与部署在 `http://www.example.com/support` 的 Java EE Web 应用之间一系列请求和响应的标头。这就是如果你使用 Fiddler 或 Wireshark 等网络嗅探工具跟踪 HTTP 请求和响应时预期看到的内容。

#### 请求 1

```
GET /support HTTP/1.1
Host: www.example.com
```

#### 响应 1

```
HTTP/1.1 302 Moved Temporarily
Location: https://www.example.com/support/login
Set-Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN; Domain=.example.com; Path=/; HttpOnly
```

#### 请求 2

```
GET /login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

#### 响应 2

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 21765
```

#### 请求 3

```
POST /support/login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

#### 响应 3

```
HTTP/1.1 302 Moved Temporarily
Location: http://www.example.com/support/home
Set-Cookie: reusername=Nick; Expires=Wed, 02-Jun-2021 12:15:47 GMT; Domain=.example.com; Path=/; HttpOnly
```

#### 请求 4

```
GET /support/home HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN; reusername=Nick
```

#### 响应 4

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 56823
```

响应中的 `Set-Cookie` 标头用于将 cookie 发送到用户的浏览器进行存储。同样，请求中的 `Cookie` 标头用于将 cookie 发回 Web 服务器。在这种情况下，用户导航到某个支持站点并重定向到登录页面。在重定向期间，用户的浏览器还从服务器获取了一个会话 ID cookie。当用户进入登录页面时，它包含了 `JSESSIONID` cookie。从那时起，用户每次发送新请求时，它都会包含 `JSESSIONID` cookie。服务器不再再次发送它，因为它知道浏览器已经拥有了。

> 注意：这里使用 `reusername` cookie 仅是为了演示 Cookie 请求标头如何传输多个 cookie。实际功能——记住用户名——与此无关。

使用 cookie 传输会话 ID 的障碍之一是用户可以在浏览器中禁用 cookie 支持，从而完全消除传输会话 ID 的方法。然而，在过去的十年里，这个问题变得越来越不担心，一家主要的搜索和电子邮件提供商和一个主要的社交网络要求其网站的用户启用 cookie。

### URL 中的 Session ID

传输会话 ID 的另一种流行方法是通过 URL。Web 或应用程序服务器知道要在 URL 中查找包含会话 ID 的特定模式，如果找到，则从 URL 中检索会话。不同的技术使用不同的策略在 URL 中嵌入和定位会话 ID。例如，PHP 使用一个名为 `PHPSESSIONID` 的查询参数。Java EE 使用了不同的方法。会话 ID 被放置在 URL 最后一段（或目录）的矩阵参数中。这释放了查询字符串，使得会话 ID 不与查询字符串中的其他参数冲突。

```
http://example.com/support;PHPSESSIONID=NRxc1Gg2v07kI4Ml1n;foo=bar&high=five
```

给定技术使用的特定技术对最终结果并不重要：将会话 ID 嵌入 URL 中，你就避免了需要使用 cookie。你可能会好奇，请求 URL 中的会话 ID 最初是如何到达浏览器的。请求仅将会话 ID 从浏览器传递到服务器。那么会话 ID 从哪里来？答案是，会话 ID 必须嵌入在应用程序返回的每一个 URL 中，包括页面上的链接、表单操作和 302 重定向。考虑之前使用 cookie 的登录场景示例。以下标头演示了使用 URL 嵌入而非 cookie 的相同一组事务：

#### 请求 1

```
GET /support HTTP/1.1
Host: www.example.com
```

#### 响应 1

```
HTTP/1.1 302 Moved Temporarily
Location: https://www.example.com/support/login;JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

#### 请求 2

```
GET /login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

#### 响应 2

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 21765
```

#### 请求 3

```
POST /support/login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

#### 响应 3

```
HTTP/1.1 302 Moved Temporarily
Location: http://www.example.com/support/home;JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

#### 请求 4

```
GET /support/home HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

#### 响应 4

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 56823
```

响应中的 `Set-Cookie` 标头用于将 cookie 发送到用户的浏览器进行存储。同样，请求中的 `Cookie` 标头用于将 cookie 发回 Web 服务器。在这种情况下，用户导航到某些支持站点并重定向到登录页面。在重定向期间，用户的浏览器还从服务器获取了一个会话 ID cookie。当用户进入登录页面时，它包含了 `JSESSIONID` cookie。从那时起，用户每次发送新请求时，它都会包含 `JSESSIONID` cookie。服务器不再再次发送它，因为它知道浏览器已经拥有了。

> 注意：`reusername` cookie 仅用于演示 Cookie 请求标头如何传输多个 cookie。实际功能——记住用户名——与此无关。

使用 cookie 传输 session ID 的障碍之一是用户可以在浏览器中禁用 cookie 支持，从而完全消除传输会话 ID 的方法。然而，在过去的十年里，这个问题变得越来越不担心，一家主要的搜索和电子邮件提供商和一个主要的社交网络要求其网站的用户启用 cookie。

### URL 中的 Session ID

传输 session ID 的另一种流行方法是通过 URL。Web 或应用程序服务器知道要在 URL 中查找包含会话 ID 的特定模式，如果找到，则从 URL 中检索会话。不同的技术使用不同的策略在 URL 中嵌入和定位会话 ID。例如，PHP 使用一个名为 `PHPSESSIONID` 的查询参数。Java EE 使用了不同的方法。会话 ID 被放置在 URL 最后一段（或目录）的矩阵参数中。这释放了查询字符串，使得会话 ID 不与查询字符串中的其他参数冲突。

```
http://example.com/support;PHPSESSIONID=NRxc1Gg2v07kI4Ml1n;foo=bar&high=five
```

给定技术使用的特定技术对最终结果并不重要：将会话 ID 嵌入 URL 中，你就避免了需要使用 cookie。你可能会好奇，请求 URL 中的会话 ID 最初是如何到达浏览器的。请求仅将会话 ID 从浏览器传递到服务器。那么会话 ID 从哪里来？答案是，会话 ID 必须嵌入在应用程序返回的每一个 URL 中，包括页面上的链接、表单操作和 302 重定向。考虑之前使用 cookie 的登录场景示例。以下标头演示了使用 URL 嵌入而非 cookie 的相同一组事务：

#### 请求 1

```
GET /support HTTP/1.1
Host: www.example.com
```



### 响应 1

```
HTTP/1.1 302 Moved Temporarily
Location: https://www.example.com/support/login;JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 请求 2

```
GET /login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 响应 2

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 21765
```

### 请求 3

```
POST /support/login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 响应 3

```
HTTP/1.1 302 Moved Temporarily
Location: http://www.example.com/support/home;JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 请求 4

```
GET /support/home HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 响应 4

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 56823
```

响应中的 `Set-Cookie` 标头用于将 cookie 发送到用户的浏览器进行存储。同样，请求中的 `Cookie` 标头用于将 cookie 发回 Web 服务器。在这种情况下，用户导航到某些支持站点并重定向到登录页面。在重定向期间，用户的浏览器还从服务器获取了一个会话 ID cookie。当用户进入登录页面时，它包含了 `SESSIONID` cookie。从那时起，用户每次发送新请求时，它都会包含 `JSESSIONID` cookie。服务器不再再次发送它，因为它知道浏览器已经拥有了。

> 注意：`reusername` cookie 仅用于演示 Cookie 请求标头如何传输多个 cookie。实际功能——记住用户名——与此无关。

使用 cookie 传输 session ID 的障碍之一是用户可以在浏览器中禁用 cookie 支持，从而完全消除传输会话 ID 的方法。然而，在过去的十年里，这个问题变得越来越不担心，一家主要的搜索和电子邮件提供商和一个主要的社交网络要求其网站的用户启用 cookie。

### URL 中的 Session ID

传输 session ID 的另一种流行方法是通过 URL。Web 或应用程序服务器知道要在 URL 中查找包含会话 ID 的特定模式，如果找到，则从 URL 中检索会话。不同的技术使用不同的策略在 URL 中嵌入和定位会话 ID。例如，PHP 使用一个名为 `PHPSESSIONID` 的查询参数。Java EE 使用了不同的方法。会话 ID 被放置在 URL 最后一段（或目录）的矩阵参数中。这释放了查询字符串，使得会话 ID 不与查询字符串中的其他参数冲突。

```
http://example.com/support;PHPSESSIONID=NRxc1Gg2v07kI4Ml1n;foo=bar&high=five
```

给定技术使用的特定技术对最终结果并不重要：将会话 ID 嵌入 URL 中，你就避免了需要使用 cookie。你可能会好奇，请求 URL 中的会话 ID 最初是如何到达浏览器的。请求仅将会话 ID 从浏览器传递到服务器。那么会话 ID 从哪里来？答案是，会话 ID 必须嵌入在应用程序返回的每一个 URL 中，包括页面上的链接、表单操作和 302 重定向。考虑之前使用 cookie 的登录场景示例。以下标头演示了使用 URL 嵌入而非 cookie 的相同一组事务：

### 请求 1

```
GET /support HTTP/1.1
Host: www.example.com
```

### 响应 1

```
HTTP/1.1 302 Moved Temporarily
Location: https://www.example.com/support/login;JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 请求 2

```
GET /login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 响应 2

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 21765
```

### 请求 3

```
POST /support/login HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 响应 3

```
HTTP/1.1 302 Moved Temporarily
Location: http://www.example.com/support/home;JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 请求 4

```
GET /support/home HTTP/1.1
Host: www.example.com
Cookie: JSESSIONID=Nrx1Clg2vG7ki4MdlN
```

### 响应 4

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 56823
```

### Session 漏洞

正如你可以想象的，会话并不是无漏洞的。坏消息是，这些漏洞可能会给你的用户带来严重问题，如果你在交易敏感或个人信息（如信用卡号或医疗数据）时没有提醒他们，可能会给你的用户带来高额罚款。好消息是，有简单的方法来解决这些漏洞，你也将学习到这些。当然，我无法涵盖你应用程序中的所有潜在漏洞，因为有数千种方法可以破坏 Web 应用程序。开发者应该在安全方面保持勤勉并了解情况。在任务关键的敏感的应用程序中，使用某种类型的商业扫描器来扫描应用程序的漏洞是明智之举。

有关 Web 应用程序和会话漏洞以及如何检测和解决它们的更多信息，请访问开放 Web 安全项目 (OWASP) 网站 `https://www.owasp.org/`。

### 复制与粘贴错误

会话被破坏的最简单方法之一，可能是由于毫无防备的用户将从浏览器中的 URL 复制并粘贴到电子邮件、论坛帖子、聊天室或其他公共区域。将会话 ID 嵌入 URL（你在本节开头读过的相关内容）是该问题的根源。还记得在客户端和服务器之间往返的 URL 吗？这些 URL（包括会话 ID）出现在客户端浏览器的地址栏中。如果用户决定与朋友分享你应用程序中的某个页面，并复制粘贴地址栏中的 URL，那么会话 ID 就会包含在朋友看到的 URL 中。如果他们在会话开始之前访问该 URL，他们将假设共享该 URL 的用户的身份。这样做显而易见的问题是，用户可能会意外看到个人信息。

更危险的情况是，心怀不轨者发现了链接并利用它劫持用户的会话。他随后可以更改电子邮件地址，获取密码重置链接，并修改密码——这让攻击者对用户的账户及其所有内容拥有完全控制权。

尽管这个问题的起源是无害的——只是从地址栏复制并粘贴 URL——但解决这一漏洞的唯一万全方法是完全禁用 URL 中的会话 ID。虽然这听起来是一项可能对你应用程序可用性产生灾难性后果的极端措施，但请记住前面提到的，大型互联网公司在使用网站时要求使用 Cookie 是多么常见。对于如今的网页用户来说，Cookie 是生活的必需，而 Cookie 固有的漏洞比这种漏洞少得多且危险得多。

### 会话固定

会话固定攻击与复制粘贴错误类似，不同之处在于在这种情况下，“毫无防备的用户”是攻击者，而受害者是使用包含嵌入在 URL 中的会话 ID 链接的用户。攻击者可能会以这种方式获取会话 ID（通过 URL 或检查浏览器的 Cookie），然后通过论坛或（通常是）电子邮件将包含该 ID 的会话发送给受害者。此时，当用户点击链接进入网站时，他的会话 ID 就被固定为 URL 中的内容——即一个攻击者所知道的会话 ID。如果用户在此会话期间登录网站，攻击者也将登录，因为他共享了该会话 ID，从而访问了用户的账户。

解决这个问题有两种方法：

- 像处理复制与粘贴错误一样，你可以简单地禁用在 URL 中嵌入会话 ID，并允许你的应用程序接受通过 URL 传递的会话 ID（你将在“在会话中存储数据”部分探索）。
- 登录后采用会话迁移。当用户登录时，将会话详情更改为新会话并使原始会话失效。（两种方法的效果相同：为新的“已登录”会话分配不同的会话 ID。）攻击者仍然拥有原始会话 ID，但该 ID 已失效且未与用户的会话连接。

### 跨站脚本与会话劫持

> 警告：还有另一种类型的会话固定攻击，恶意网站使用另一个网站的域名写入会话 ID Cookie，从而有效地在受害者的浏览器中设置另一个网站的会话 ID。然而，该攻击的效果与 URL 会话固定攻击相同。在不完全禁用会话的情况下，Web 应用程序无法防止这种漏洞。此漏洞实际上是浏览器漏洞，而不是 Web 应用程序的漏洞。

所有现代浏览器都修复了这种跨域攻击漏洞（`example.net` 站点为 `.com` 站点设置 cookie）。然而，恶意的 `.example.net` 仍然可以为域名 `.example.net` 设置会话 Cookie，然后该 Cookie 会被脆弱的 `.example.net` 获取。通过遵循一个简单的规则可以完全避免此问题：不要与不可信的应用程序共享域名。

你已经读过关于复制粘贴错误，当它被恶意方利用时就会变成会话固定攻击。另一种形式的会话劫持利用 JavaScript 读取会话 Cookie 的内容。攻击者利用网站的跨站脚本漏洞，将 JavaScript 注入页面，并使用 JavaScript DOM 属性 `.cookie` 读取会话 ID Cookie 的内容。在攻击者从毫无防备的用户那里获取会话 ID 后，他可以通过在自己的机器上创建 Cookie 或使用 URL 嵌入来采用该会话 ID，从而模拟受害者的身份。

防止这种攻击最显见的防御是保护你的网站免受跨站脚本攻击，这是本书范围之外的话题（即之前提到的 OWASP 网站）。然而，做到这一点可能困难，且攻击者不断发现新方法来实施跨站脚本攻击。另一种防御是你应该配合 `HttpOnly` 属性始终使用的。该属性允许 Cookie 仅在浏览器发起 HTTP（或 HTTPS）请求时使用，而该请求是通过链接、在地址栏中手动输入 URL、表单提交或 AJAX 请求发生的。更重要的是，`HttpOnly` 完全禁用了 JavaScript、Flash 或某些浏览器浏览或插件获取 Cookie 内容（甚至知道其存在）的能力。这从根上阻止了跨站脚本会话劫持攻击。会话 ID Cookie 应该始终包含 `HttpOnly` 属性。

> 注意：尽管 `HttpOnly` 属性防止了 JavaScript 使用 `document.cookie` DOM 属性访问 Cookie，但源自 JavaScript 代码的 AJAX 请求仍包含会话 ID Cookie，因为是浏览器而不是 JavaScript 代码负责构建 AJAX 请求头。这意味着服务器仍然能够将 AJAX 请求与用户的会话关联起来。

### 不安全的 Cookie

你应该考虑的最后一个漏洞是中间人攻击（MitM），这是一种经典的数据拦截攻击，攻击者在请求或响应在客户端和服务器之间传输时进行观察。这种攻击促成了安全套接层和传输层安全 (SSL/TLS)，它是 HTTPS 的基础。通过 HTTPS 加密网络流量可以有效防止 Cookie 被窃取。`Secure` 标记为了解决这个问题而创建。当服务器将会话 ID 发送到客户端时，会设置 `Secure` 标记。这告诉浏览器 Cookie 仅通过 HTTPS 传输。否则，一旦你重定向到 HTTP，损害已经造成了：攻击者可以窃取 Cookie。因此，你必须权衡应用程序的安全需求，确定要保护的数据是否足够敏感，以值得承担 HTTPS 的性能开销。

### 最强防御

在处理会话安全时，最后一种选择是 SSL/TLS 会话 ID。为了通过消除每次请求都执行 SSL 握手的需要来提高 SSL 协议的效率，SSL 协议定义了自己的会话 ID。会话 ID 在 SSL 握手期间建立，并在后续请求中使用以确定使用哪些密钥进行加密和解密。这一概念取代了 HTTP 会话 ID 的概念。然而，SSL Session ID 不通过 Cookie 或 URL 传输或存储，你可以通过查阅 RFC 2246《The TLS Protocol》了解更多关于 SSL Session ID 的信息。获取你未经授权的 Session ID 是极其困难的。一些极高安全的网站（如金融机构）重用 SSL 会话 ID 作为 HTTP 会话 ID，在消除 Cookie 和 URL 的同时保持请求之间的状态。

这是跨请求建立会话 ID 的极其安全的方法，并且几乎不可免疫。此外，一旦发现 SSL 漏洞，通常会在几周内解决，但使用这种技术有一些可以理解的缺点；否则每个人都会使用它。在旧版本的 EE 规范中，没有方法指定这一点，因此开发者必须使用特定的容器类来实现 SSL 会话 ID。在 Java EE 6.0 规范中，添加了一个选项（你将在下一节学习）以便让 Web 容器使用 SSL 会话 ID，因此配置不再是主要问题（尽管许多网站仍在使用它）。此外，配合 `Secure` Cookie 标记，它要求你始终处于 HTTPS 之下。如果你对安全的关注达到了启用此功能的程度，那么你可能打算让整个网站始终处于 HTTPS 之下，因此这对你来说可能不是问题。

SSL Session ID 的另一个问题是 Web 容器将负责 SSL 通信。如果你使用 Web 服务器或负载均衡器来管理你的 SSL 通信——这在集群服务器环境中很常见——那么 Web 容器将无法获取 SSL Session ID。在这样的集群环境中，用户的请求必须始终路由到同一台服务器。最后，取决于服务器和浏览器，SSL Session ID 的生命周期可能很长，也可能很短，因此很难将其作为 HTTP 会话 ID 的替代方案。

现在你已经了解了会话（sessions），学习了 `JSESSIONID` Cookie 和 URL 重写，并探索了会话中固有的漏洞以及如何处理它们，现在是时候在你的 Java EE 应用中开始会话了。

### 在会话中存储数据

在学习在 Java EE 中使用会话时，你将探索位于 w3 代码下载网站上的 Shopping-Cart（购物车）示例项目。你不会创建一个另一个带有支付系统和相关功能的购物网站。你只需探索使用会话来聚合跨多个页面收集的数据的概念（在本例中，即添加到购物车的商品）。你可以自己创建该项目，也可以遵循 Shopping-Cart 项目进行。你的项目将从第 4 章的部署描述符 `<jsp-config>` 开始，以及以下 `/WEB-INF/jsp/base.jsp`：

```
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

此外，你应该在 Web 根目录下有一个简单的 `index.jsp` 文件，用于重定向到你的商店 Servlet：`<c:redirect url="shop" />`

### 在部署描述符中配置会话

在许多情况下，HTTP 会话在 Java EE 中已经准备就绪，不需要显式配置。然而，你可以对其进行配置，而且出于安全考虑，你应该这样做。你可以在部署描述符中使用 `<session-config>` 标签来配置会话。在该标签内，你可以配置跟踪会话的方法、会话超时后的，以及如果你使用了会话 ID Cookie，其配置。其中许多项具有你需要更改的默认值。以下代码演示了会话的所有部署描述符设置。

```
<session-config>
  <session-timeout>30</session-timeout>
  <cookie-config>
    <name>JSESSIONID</name>
    <domain>example.org</domain>
    <path>/shop</path>
    <comment><![CDATA[保持登录状态。更多信息请参阅我们的隐私政策。]]></comment>
    <http-only>true</http-only>
    <secure>false</secure>
    <max-age>1800</max-age>
  </cookie-config>
  <tracking-mode>COOKIE</tracking-mode>
</session-config>
```

### 在会话中存储数据

```
<tracking-mode>URL</tracking-mode>
<tracking-mode>SSL</tracking-mode>
</session-config>
```



所有的 `<session-config>` 和 `<cookie-config>` 标签都是可选的，它们必须按照示例所示的顺序出现（不包括省略的标签）。`<session-timeout>` 标签指定了会话失效之前保持非活动状态的时间（以分钟计算）。如果值为 0 或更小，则会话永不会过期。如果省略此标签，则应用容器的默认值。Tomcat 的默认容器值为 30，这可以在 Tomcat 配置中更改。为了保持一致性，你应该使用此标签显式设置超时时间。在本示例中，超时时间为 30 分钟。每当具有特定会话 ID 用户向你的应用程序请求时，会话的非活动计时器就会重置。如果他超过 30 分钟未发送请求，则会话被认为无效并消失。`<tracking-mode>` 标签用于 Servlet 3.0 Java EE 6，指明应该使用哪种容器来跟踪会话 ID。合法值为：

- **URL**：容器将会话 ID 嵌入 URL 中。它不使用 Cookie 或 SSL 会话 ID。这种方法不安全安全。
- **COOKIE**：容器使用 Cookie 跟踪会话 ID。这种技术非常安全。
- **SSL**：容器使用 SSL Session ID 作为 HTTP 会话 ID。这种方法是最安全的，但要求所有请求都必须 HTTPS 才能正常工作。

`<cookie-config>` 标签仅在被指定为一种（或唯一的）跟踪模式时生效。这些标签允许你自定义容器返回给浏览器的会话 Cookie：

- `<name>` 标签为会话 ID Cookie 添加 Name 属性。默认值是 `JSESSIONID`，你可能不需要更改它。
- `<domain>` 和 `<path>` 标签对应于 Cookie 的 Domain 和 Path 属性。Web 容器会正确地设置这些默认值，因此你通常不需要自定义它们。Domain 默认值为创建会话时用于请求的域名。Path 默认值为部署的应用程序上下文名称。
- `<comment>` 标签为会话 ID Cookie 添加 Comment 属性，提供了添加任意文本的机会。这通常用于解释 Cookie 的用途并引导用户查看网站的隐私政策。是否使用它完全取决于你。如果你省略此标签，则 Cookie 不会添加 Comment 属性。

`<http-only>` 和 `<secure>` 标签对应于 HttpOnly 和 Secure Cookie 属性，且都为 false。为了提高安全性，你应该始终将 `<http-only>` 设置为 true。只有在你启用了 HTTPS 时，才将 `<secure>` 改为 true。

最后一个标签 `<max-age>` 指定了 Max-Age Cookie 属性，控制 Cookie 何时过期。默认情况下，Cookie 没有过期时间，它在浏览器关闭时过期。
- `<http-only>`：为了提高安全性你应该始终将 `<http-only>` 设置为 true。
- `<secure>`：只有在你启用了 HTTPS 时，才将 `<secure>` 改为 true。
- `<max-age>`：设置为 -1 具有相同的效果。

```
<session-config>
  <session-timeout>30</session-timeout>
  <cookie-config>
    <http-only>true</http-only>
  </cookie-config>
  <tracking-mode>COOKIE</tracking-mode>
</session-config>
```

这会导致会话持续 30 分钟，仅使用 Cookie 并让 Cookie 包含 HttpOnly 属性。正如提到的，最安全的方法是使用 SSL Session ID。折方案使用 Cookie 但设置 Secure 属性需要 HTTPS。本书没有演示这些技术，因为这需要生成自签名证书并学习 Tomcat 中的 SSL。这些主题都出了本书的范围，可以在 Tomcat 文档中进行探索。

## 存储和检索数据

在项目中创建一个名为 `com.wrox.StoreServlet` 的 Servlet，并将其注解为 URL 模式 `/shop`。此外，在你的 Servlet 中创建一个简单的 map 表示数据库（或者直接使用 Shopping-Cart 项目）。

```java
@WebServlet(
    name = "StoreServlet",
    urlPatterns = "/shop"
)
public class StoreServlet extends HttpServlet {
    private final Map<Integer, String> products = new Hashtable<>();

    public StoreServlet() {
        this.products.put(1, "Sandpaper");
        this.products.put(2, "Nails");
        this.products.put(3, "Glue");
        this.products.put(4, "Paint");
        this.products.put(5, "Tape");
    }
}
```

你可以使用这个产品数据库来“浏览”并将购物车项链接回商品名称。

## 在你的 Servlet 中使用会话

为 `doGet` 方法创建一个简单的实现，支持三个操作：browse、addToCart 和 viewCart：

```java
@Override
protected void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    String action = request.getParameter("action");
    if (action == null) {
        action = "browse";
    }
    switch (action) {
        case "addToCart":
            this.addToCart(request, response);
            break;
        case "viewCart":
            this.viewCart(request, response);
            break;
        case "browser":
        default:
            this.browse(request, response);
            break;
    }
}
```

Servlet 的 `browse` 和 `viewCart` 方法应该非常简单，只需添加一个请求属性并转发到 JSP：

```java
private void viewCart(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    request.setAttribute("products", this.products);
    request.getDispatcher("/WEB-INF/jsp/view/viewCart.jsp")
            .forward(request, response);
}

private void browse(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    request.setAttribute("products", this.products);
    request.getDispatcher("/WEB-INF/jsp/view/browse.jsp")
            .forward(request, response);
}
```

这些方法的相似之处在于，它们都将产品添加到请求属性中，但它们分别转发到了不同的 JSP。现在来看 `addToCart` 方法：

```java
private void addToCart(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    int productID;
    try {
        productID = Integer.parseInt(request.getParameter("productId"));
    } catch (Exception e) {
        response.sendRedirect("shop");
        return;
    }
    HttpSession session = request.getSession();
    if (session.getAttribute("cart") == null) {
        session.setAttribute("cart", new Hashtable<Integer, Integer>());
    }
    @SuppressWarnings("unchecked")
    Map<Integer, Integer> cart = session.getAttribute("cart");
    if (!cart.containsKey(productID)) {
        cart.put(productID, 0);
    }
    cart.put(productID, cart.get(productID) + 1);
    response.sendRedirect("action=viewCart");
}
```

这个方法更为复杂。首先，它获取并解析要添加到购物车中的产品 ID。之后，代码调用了一些我们尚未看过的新的 session 相关方法。`HttpServletRequest` 上的 `getSession` 方法有两种形式：`getSession()` 和 `getSession(boolean)`。

### 在 Session 中存储数据

调用 `getSession()` 会调用 `getSession(true)`，如果存在已有的 session，则返回该 session；如果不存在 session，则创建一个新的 session（它永远不会返回 null）。相反，调用 `getSession(false)` 如果存在已有的 session 则返回它，如果不存在 session 则返回 null。调用 `getSession` 并传入参数 `false` 有其原因——例如，你可能想测试 session 是否已经创建——但在大多数情况下，只需调用 `getSession()` 即可。`getAttribute` 方法返回 session 中的一个对象。它有一个对应的方法 `getAttributeNames`，用于返回 session 中所有属性名称的枚举。`setAttribute` 方法将一个对象绑定到 session 中。在示例中，代码查找购物车（cart），如果不存在则添加它，并从 session 中检索简单的购物车。然后，它在购物车中查找产品 ID，如果不存在则以数量 0 添加它。最后，它增加了购物车中产品的数量。

### 在你的 JSPs 中使用 Session

Servlet 代码可以处理应用程序中的逻辑，但你需要 JSP 来显示产品和购物车。先从创建 `/WEB-INF/jsp/view/browse.jsp` 开始：

```jsp
<%@ page import="java.util.Map" %>
<!DOCTYPE html>
<html>
<head>
    <title>Product List</title>
</head>
<body>
    <h2>Product List</h2>
    <a href="<c:url value='shop?action=viewCart'>">View Cart</a><br /><br />
    <%
        @SuppressWarnings("unchecked")
        Map<Integer, String> products = (Map<Integer, String>) request.getAttribute("products");
        for (int id : products.keySet()) {
    %>
    <a href="<c:url value='shop'>
        <c:param name='action' value='addToCart' />
        <c:param name='productId' value='<%= Integer.toString(id) %>' />
    </c:url>">${products.get(id)}</a><br /><br />
    <%
        }
    %>
</body>
</html>
```

这个 JSP 的内容很少，只是简单地列出了所有产品。你将在第 7 章探索 `<c:param>` 标签。点击产品名称将其添加到购物车。接下来创建 `/WEB-INF/jsp/view/viewCart.jsp`：

```jsp
<%@ page import="java.util.Map" %>
<!DOCTYPE html>
<html>
<head>
    <title>View Cart</title>
</head>
<body>
    <h2>View Cart</h2>
    <a href="<c:url value='shop' />">Product List</a><br /><br />
    <%
        @SuppressWarnings("unchecked")
        Map<Integer, String> products = (Map<Integer, String>) request.getAttribute("products");
        @SuppressWarnings("unchecked")
        Map<Integer, Integer> cart = (Map<Integer, Integer>) session.getAttribute("cart");
        if (cart == null || cart.size() == 0) {
            out.println("Your cart is empty.");
        } else {
            for (int id : cart.keySet()) {
                out.println(products.get(id) + " * " + "(qty: " + cart.get(id) + ")<br />");
            }
        }
    %>
</body>
</html>
```

这个 JSP 使用了你在第 4 章中学习的隐式 session 变量来访问数据。

（注：原文后半部分似乎存在大量重复或乱码的文本，此处已根据上下文进行逻辑翻译）

### 在会话中存储数据

空闲时间间隔应比其他用户短。因此，当用户首次登录时，你调用 `setMaxInactiveInterval` 根据用户的权限来更改此值。

可能需要了解的最重要的 `HttpSession` 方法之一是 `invalidate` 方法。这是你在用户注销时会调用的方法（尽管这只是一个例子）。`invalidate` 会销毁会话并解绑所有绑定到它的数据。即使客户端浏览器使用相同的会话 ID 发起另一个请求，失效的会话也不会被使用。相反，将创建一个新的会话，响应将包含新的会话 ID。

## 在会话中存储更复杂的数据

到目前，你已经学习了如何使用 `HttpSession` 对象以及如何从会话中添加和移除它。然而，你之前只操作了具有整数键和值的简单 `Map`。这就是会话能做的全部工作吗？答案是否定的。从理论上来说，会话可以存储你想要放入其中的几乎任何内容。

当然，我们还需要考虑大小问题。如果你在会话中放入了太多的数据，可能会开始耗尽虚拟机池。此外，还需要考虑集群（Clustering）。集群将在“使用会话的应用程序集群”章节中讨论，但我们想要确保你可以在整个会话期间对会话属性进行序列化和同步，这需要实现 `Serializable` 接口。除了这两个限制外，没有什么是不能放入会话的。

为了演示这一点，请考虑网站上的 `Session-Activity` 示例项目。它包含部署描述符、`WEB-INF/jsp/base.jsp` 文件以及一个略有不同的 `index.jsp` 文件：

```
<:redirect url="/home" />
```

在 `com.wrow` 包中有一个名为 `PageVisit` 的 POJO。该类及其字段在如下代码所示。该类的简单访问器（getter）和变异器（setter）方法将留给读者来完成。

```java
import java.io.Serializable;
import java.net.InetAddress;

public class PageVisit implements Serializable {
    private long enteredTimestamp;
    private Long leftTimestamp;
    private String request;
    private String ipAddress;
    // accessor and mutator methods
}
```



注意，尽管 `enteredTimestamp` 是一个原始 `long` 类型，但 `leftTimestamp` 是一个包装类 `Long`。这样 `leftTimestamp` 就可以为 `null`。列表 5-1 中的 `HttpServletServlet` 并不复杂。标准的 `doGet` 方法调用 `recordSessionActivity` 然后调用 `viewSessionActivity`。`viewSessionActivity` 方法简单地转发到一个 JSP。`recordSessionActivity` 执行了所有核心的工作：会话；确保活动 `Vector` 存在于 `Vector` 中；如果 `Vector` 中存在最后一个 `PageVisit`，则更新其 `leftTimestamp`；并将关于当前请求的信息添加到 `Vector` 中。这里之所以使用 `Vector` 是因为它与 `ArrayList` 不同，它是一个线程安全的 `List`。每个 Servlet 中都有一个通配符。此 URL 模式意味着该 Servlet 接受以 `/do/` 开头的任何请求模式，这在你测试时会非常有用。

### 列表 5-1：ActivitySession.java

```java
@WebServlet(
    name = "storeServlet",
    urlPatterns = "/do/**"
)
public class ActivitySession extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        this.recordSessionActivity(request);
        this.viewSessionActivity(request, response);
    }

    private void recordSessionActivity(HttpServletRequest request) {
        HttpSession session = request.getSession();
        if (session.getAttribute("activity") == null) {
            session.setAttribute("activity", new Vector<PageVisit>());
        }

        @SuppressWarnings("unchecked")
        Vector<PageVisit> visits = (Vector<PageVisit>) session.getAttribute("activity");
        if (!visits.isEmpty()) {
            PageVisit last = visits.lastElement();
            last.setLeftTimestamp(System.currentTimeMillis());
        }

        PageVisit now = new PageVisit();
        now.setEnteredTimestamp(System.currentTimeMillis());
        if (request.getQueryString() == null) {
            now.setRequest(request.getRequestURL().toString());
        } else {
            try {
                now.setRequest(request.getRequestURL() + "?" + request.getQueryString());
            } catch (UnknownHostException e) {
                e.printStackTrace();
                visits.add(now);
            }
        }
        now.setIpAddress(InetAddress.getByName(request.getRemoteAddr()));
    }

    private void viewSessionActivity(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        request.getRequestDispatcher("/WEB-INF/jsp/view/viewSessionActivity.jsp")
                .forward(request, response);
    }
}
```

在这个过程中最后需要查看的内容是列表 5-2 中的 `/WEB-INF/jsp/view/viewSessionActivity.jsp` 文件。它并没有看起来那么复杂，只是以可读的方式显示会话中积累的所有页面访问数据。现在要测试此功能，请遵循以下步骤：

1. 编译并调试你的应用程序，并在浏览器中导航到 `http://localhost:8080/session-activity/do/home/`。你应该能看到关于你的会话的信息、会话是新的指示以及关于你刚刚进行的请求的信息。
2. 开始在 URL 末尾添加路径和查询参数。尝试不同的 URL 并在每个请求之间等待一段时间。你可以将 `home/` 替换为其他内容——只需确保在 URL 中保留 `/do/` 即可。

过段时间后，你应该开始看到类似图 5-3 示例的内容。你的应用程序正在跟踪活动并将其持久化在会话中展示给用户。

# 列表 5-2：viewSessionActivity.jsp

```jsp
<%@ page import="java.util.Vector, java.text.SimpleDateFormat" %>
<%
private String toString(long timeInterval) {
    if (timeInterval < 1000)
        return "less than one second";
    if (timeInterval < 60000)
        return (timeInterval / 1000) + " seconds";
    return "about " + (timeInterval / 60000) + " minutes";
}

SimpleDateFormat f = new SimpleDateFormat("EEE, d yyyy HH:mm:ss Z");
%>
<!DOCTYPE html>
<html>
<head>
    <title>Session Tracker</title>
</head>
<body>
<h2>Session Properties</h2>
Session ID: <%= session.getId() %><br />
Session is new: <%= session.isNew() %><br />
Session created: <%= f.format(new Date(session.getCreationTime())) %><br />
<h2>Page Activity</h2>
<%
@SuppressWarnings("unchecked")
Vector<PageVisit> visits = (Vector<PageVisit>) session.getAttribute("activity");
for (PageVisit visit : visits) {
    out.print("Page: " + visit.getRequest() + "<br />");
    out.print("IP: " + visit.getIpAddress() + "<br />");
    out.print("Entered: " + new Date(visit.getEnteredTimestamp()) + "<br />");
    if (visit.getLeftTimestamp() != null) {
        out.print("Left: " + new Date(visit.getLeftTimestamp()) + "<br />");
    }
    out.print("<hr />");
}
%>
</body>
</html>
```

# 第 5 章 维护状态会话

```java
@Override
protected void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    HttpSession session = request.getSession();
    if (session.getAttribute("username") != null) {
        response.sendRedirect("tickets");
        return;
    }
    request.setAttribute("loginFailed", false);
    request.getRequestDispatcher("/WEB-INF/jsp/login.jsp")
            .forward(request, response);
}
```

上一个示例中的第一步是检查用户是否已经登录并将其重定向到他们所在的页面。如果用户未登录，则设置 `loginFailed` 属性为 false，并将请求转发到登录 JSP。当提交登录表单时，它会 POST 到 `doPost` 方法：

```java
@Override
protected void doPost(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    HttpSession session = request.getSession();
    if (session.getAttribute("username") != null) {
        response.sendRedirect("tickets");
        return;
    }
    String username = request.getParameter("username");
    String password = request.getParameter("password");
    if (username == null || password == null ||
        !LoginServer.userDatabase.containsKey(username) ||
        !password.equals(LoginServer.userDatabase.get(username))) {
        request.setAttribute("loginFailed", true);
        request.getRequestDispatcher("/WEB-INF/jsp/login.jsp")
                .forward(request, response);
    } else {
        session.setAttribute("username", username);
        request.changeSessionId();
        response.sendRedirect("tickets");
    }
}
```

`doPost` 方法中的内容并不多。它确保用户尚未登录，然后根据“数据库”检查用户名和密码。如果登录失败，它会将 `loginFailed` 属性置为 true，并将用户送回登录 JSP。如果凭据匹配，它会在会话中设置 `username` 属性，更改会话 ID，然后将用户重定向到订单屏幕。`changeSessionId` 方法是 Java EE 7 中 Servlet 3.1 的一个新功能，它通过迁移会话（更改会话 ID）来防止你在本章前面读过的会话固定攻击。

# 创建登录表单

接下来创建 `/WEB-INF/jsp/view/login.jsp` 并在其中放入一个登录表单：

```html
<!DOCTYPE html>
<html>
<head>
    <title>客户支持</title>
</head>
<body>
    <h2>登录</h2>
    你必须登录才能访问客户支持网站。<br /><br />
    <% if ((Boolean) request.getAttribute("loginFailed"))
```

这个简单的页面在屏幕上放置了一个登录表单，而 `loginFailed` 属性则在用户登录凭据被拒绝时提醒他们。通过与 `LoginServer` 配合使用，它完成了简单的登录功能。然而，这并不能阻止用户访问订单屏幕。你需要在 `TicketServer` 中添加一个检查，以确保用户在显示订单信息或允许他们发布之前已经登录。通过在 `TicketServer` 的 `doGet` 和 `doPost` 方法顶部添加以下代码可以轻松实现：

```java
if (request.getSession().getAttribute("username") == null) {
    response.sendRedirect("login");
    return;
}
```

现在用户在创建订单之前已经登录，因此你的代码在他们创建新订单时可以访问他们的姓名。`TicketServer.createTicket` 方法更改了当前代码，该代码使用请求参数设置客户名称，因此现在它像下面的代码所示使用会话中的用户名。你也可以从 `/WEB-INF/jsp/view/ticketForm.jsp` 中移除“您的姓名”（userName）输入字段。

```java
ticket.setCustomerName(
    (String) request.getSession().getAttribute("username")
);
```

### 测试登录

现在你的应用程序需要登录了，请按照以下步骤进行测试：

1. 编译项目并使用你的 IDE 进行调试。
2. 在浏览器中导航到应用程序 (`http://localhost:8080/support/`)，你应该会立即被带到登录页面。
3. 尝试使用错误的用户名和密码登录（这两者都区分大小写），你应该被拒绝进入。
4. 尝试有效的用户名和密码，你应该进入订单列表。
5. 像之前的章节中那样创建几个订单，你的用户名应该关联到它们上面。
6. 关闭浏览器，重新打开，并使用不同的用户名和密码重新登录。
7. 创建另一个订单，你会发现新订单拥有你当前登录用户的姓名，而旧订单拥有另一个用户的姓名。

# 添加注销链接

在测试时，你必须关闭浏览器才能退出客户支持应用程序。这可能并不方便，也不是企业级应用的特征。添加注销链接是非常容易的。首先，调整 `LoginServlet.doGet` 方法的代码以支持用户退出：

```java
HttpSession session = request.getSession();
if (request.getParameter("logout") != null) {
    session.invalidate();
    response.sendRedirect("login");
    return;
} else if (session.getAttribute("username") != null) {
    response.sendRedirect("tickets");
    return;
}
```



你只需要在每个页面顶部添加一个注销链接：

```html
<h2><a href="<c:url value='/logout'/>">注销</a></h2>
```

现在重新构建并运行，然后登录。你应该看到注销链接表示你已成功注销。

### 使用监听器检测会话

Java EE 会话最实用的功能之一是会话事件的概念。当会话发生变化时（例如，添加或删除会话属性），Web 容器可以通知你的应用程序这些变化。如果某些第三方代码（如 Spring Framework 或 Spring Security）对会话进行了更改，这就会特别有用。你用于检测这些变化的工具被称为监听器（listeners）。

Servlet API 定义了几个监听器，其中许多个是针对某种形式的会话活动的。你通过实现与该事件对应的监听器接口来订阅事件。你可以在单个类中实现一个或多个监听器接口；尽管当然，你不会希望将不相关的代码放在同一个类中。当发生某些触发了向你已订阅的代码发布事件的情况时，容器会调用你类中对应的方法。

> **注意**：从 Servlet 3.0/Java EE 6 开始，你不再需要使用 `@WebListener` 注解标记监听器类，或在部署描述符中声明它，而是可以使用 `ServletContext.addListener` 方法编程地注册它。你只能在 `ServletContextListener` 的 `initialized` 方法或 `ServletContainerInitializer::onStartup` 方法中调用此方法。当然，你用于此的任何 `ServletContextListener` 也必须被注册（使用这三种方法之一）。你将在第 12 章学习更多关于 `ServletContainerInitializer` 的知识。

你可以实现的监听器之一是 `javax.servlet.http.HttpSessionAttributeListener`。它有三个方法，当会话属性被添加（更新或替换）或删除时会被通知。

一个特别有趣的监听器是 `javax.servlet.http.HttpSessionBindingListener`。与其他监听器不同，你不需要为 `HttpSessionBindingListener` 添加部署配置或注解。如果一个类实现了它，它就能感知到作为会话属性的状态。例如，如果 `Foo` 实现了 `HttpSessionBindingListener` 并且使用 `setAttribute` 将 `Foo` 的实例添加到 `HttpSession` 中，容器会调用该实例的 `valueBound` 方法。同样，当你使用 `removeAttribute` 从会话中移除它时，容器会调用实例的 `valueUnbound` 方法。

在本节中我们将详细观察的两个监听器是 `javax.servlet.http` 包中的 `HttpSessionListener` 和 `HttpSessionIdListener`。在你的项目中创建一个同时实现这两个接口的 `SessionListener` 类，并使用 `@WebListener` 注解它（或在 Customer-Support-v3 项目中操作）：

```java
@WebListener
public class SessionListener implements HttpSessionListener, HttpSessionIdListener {
}
```

`@WebListener` 并不是通知容器你的代码正订阅了这些事件的唯一方法。你可以通过编程方式注册它，或者在部署描述符中声明监听器，如下（示例将坚持使用注解，因为这是最简单的技术）。

```xml
<listener>
  <listener-class>com.wrox.SessionListener</listener-class>
</listener>
```

`HttpSessionListener` 接口定义了 `sessionCreated` 和 `sessionDestroyed` 方法。直觉上，每当创建一个新会话时，就会调用 `sessionCreated`。当会话不再有效时，就会调用 `sessionDestroyed`。这可能是代码中显式调用会话的 `invalidate` 方法，也可能是由于超时导致的隐含失效。以下代码实现了这些方法：

```java
@Override
public void sessionCreated(HttpSessionEvent e) {
  System.out.println(this.date() + " *: Session " + e.getSession().getId() + " created.");
}
```

```java
@Override
public void sessionDestroyed(HttpSessionEvent e) {
  System.out.println(this.date() + " *: Session " + e.getSession().getId() + " destroyed.");
}
```

如你所见，这些会在会话创建或销毁时使用。这是该特定监听器的常见用例；管理员通常希望以某种方式记录这些信息以备存档。`HttpSessionIdListener` 仅定义了一个方法 `sessionIdChanged`。该方法每当请求的 `changeSessionId` 方法更改会话 ID 时被调用，其实现在如下代码中：

```java
@Override
public void sessionIdChanged(HttpSessionEvent e, String oldSessionId) {
  System.out.println(this.date() + " *: Session ID " + oldSessionId + " changed to " + e.getSession().getId());
}
```

所有三个条目都使用一个简单的辅助方法向会话活动日志记录添加时间戳。

```java
private SimpleDateFormat formatter = new SimpleDateFormat("EEE, d MMM yyyy HH:mm:ss*");
...
```

```java
private String date() {
    return this.formatter.format(new Date());
}
```

现在编译、调试并导航到你的应用程序。调试窗口中立即出现一条日志消息，指示会话已创建。登录应用程序，你应该观察到另一条日志消息，显示会话 ID 已更改。这是你几页前添加到项目中的会话固定保护。最后，当你注销应用程序时，会出现另外两个日志条目——一个表示你的会话已销毁，另一个表示创建了新会话（因为你返回了登录页面）。你现在有了一个在应用程序中记录会话活动的机制。

> **注意**：当你启动调试器但在打开浏览器之前，你可能已经看到一条指示一个或多个会话已销毁的日志消息。这是完全正常的。Tomcat 将会话持久化到文件系统中，以免数据丢失，并在 Tomcat 启动时尝试恢复会话。如果持久化的会话在 Tomcat 恢复它们之前过期，Tomcat 会通知 `HttpSessionListeners` 会话已过期，就像 Tomcat 从未停止过一样。这是 Web 容器的标准行为，在大多数情况下可以禁用，但这超出了本书的范围。请咨询你容器的文档。

## 维护活动会话列表

除了记录会话活动外，你可以使用 `HttpSessionListener` 在应用程序中维护活动会话列表，Servlet API 规范并未直接提供此功能。

要实现这一点，可以通过代码列表 5-3 创建 `SessionRegistry` 类。该类非常简单。它维护了一个静态 `Map`，以会话 ID 为键，相应的会话对象为值。初看起来这可能效率不高，但记住这些会话已经为了其他目的存在于内存中了。会话对象并没有被复制；该类存储的是它们的另一组引用，与会话对象本身的潜在内存占用相比，这样做是非常轻量级的。由于该类只包含静态方法，因此其构造函数是私有的，以防止实例化。

### 代码列表 5-3: SessionRegistry.java

```java
public final class SessionRegistry {
    private static final Map<String, HttpSession> SESSIONS = new Hashtable<>();

    public static void addSession(HttpSession session) {
        SESSIONS.put(session.getId(), session);
    }

    public static void updateSessionId(HttpSession session, String oldSessionId) {
        synchronized (SESSIONS) {
            SESSIONS.remove(oldSessionId);
            addSession(session);
        }
    }

    public static void removeSession(HttpSession session) {
        SESSIONS.remove(session.getId());
    }

    public static List<HttpSession> getAllSessions() {
        return new ArrayList<>(SESSIONS.values());
    }

    public static int getNumberOfSessions() {
        return SESSIONS.size();
    }

    private SessionRegistry() { }
}
```

此注册表存储了所有活动会话的引用，但你必须以某种方式添加和删除它们。为此，请遵循以下步骤：

1. 展开你之前创建的 `SessionListener`。在 `sessionCreated` 方法中添加以下代码：
   `SessionRegistry.addSession(e.getSession());`
2. 在 `sessionDestroyed` 方法中添加以下代码：
   `SessionRegistry.removeSession(e.getSession());`
3. 在 `sessionIdChanged` 方法中添加以下代码：
   `SessionRegistry.updateSessionId(e.getSession(), oldSessionId);`

现在会话会在适当的时间被添加到注册表中移除，但你仍然需要一种方法来显示它们。一个简单的 `SessionListServlet` 处理请求：

```java
@WebServlet(
    name = "sessionList",
    urlPatterns = "/sessions"
)
public class SessionList extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        if (request.getSession().getAttribute("username") == null) {
            response.sendRedirect("/login");
            return;
        }

        request.setAttribute("numberOfSessions", 
            SessionRegistry.getNumberOfSessions());

        request.setAttribute("sessionList", 
            SessionRegistry.getAllSessions());

        request.getRequestDispatcher("/WEB-INF/jsp/sessions.jsp")
            .forward(request, response);
    }
}
```

要测试这一点，你需要两个浏览器（而不是两个窗口）：

1. 重构建并调试你的应用程序，并使用第一个浏览器打开应用程序。
2. 登录后，导航到 `http://localhost:8080/sessions`。你应该会在会话列表中看到你当前的会话。
3. 打开第二个浏览器，登录应用程序，并在该浏览器中导航到 `http://localhost:8080/sessions`。你应该看到一个与图 5-4 类似的屏幕。
4. 刷新你打开的第一个浏览器，新会话也应该出现在那里。这意味着你成功地维护了一个会话列表。

```jsp
{
  out.print(aSession.getId() + " - " +
  aSession.getAttribute("username"));

  if (aSession.getId().equals(session.getId())) {
    out.print(" you");
  }

  out.print(" - last active " +
  toString(timestamp - aSession.getLastAccessedTime()));

  out.print(" age-<br/>");
}
```



**注意** 此示例中列出的会话仅限于当前运行的 Tomcat 实例中的。如果你的应用程序部署在多个 Tomcat 实例上，你将看到不同的会话，这取决于你对应用的请求落在哪个 Tomcat 实例上，因为页面仍然只会列出该特定 Tomcat 实例上的会话。解决此问题的方案是正确配置应用程序以在集群中设置会话复制。这些主题将在下一节中探讨。

# 对使用会话的应用进行集群

在处理企业级应用期间，你无疑会遇到对应用程序进行集群的需求。集群化提供了许多优势，特别是为你的应用程序增加了冗余和扩展性。配置良好的集群化应用程序可以在发生故障或进行例行维护时，无需经历任何停机。在一个管理非常良好的环境中，管理员可以发布应用程序升级而不会引起停机。正如你所看到的，集群化是 Web 工具箱中不可或缺的成员。

然而，集群化并非没有缺点，存在着必须克服的挑战。这些挑战最大的之一是在运行在不同机器上的应用实例之间传递消息，有时甚至在不同或断开连接的网络上，或者在世界的不同地区。几十年来，人们一直在重新构思和设计集群系统，不断寻找稳定、可靠且快速的“完美”消息框架。高级队列协议 (AMQP)、Java 消息服务 (JMS) 和微软消息队列 (MSMQ) 是由此产生的三种竞争技术。当然，应用程序集群化面临的挑战不仅仅是消息传递，你在本节中关注的是集群中的会话管理。

理解本节需要你具备一些负载均衡的基础知识，包括它的工作原理以及一些常见的负载均衡策略。这些都是需要花费大量时间来讨论的话题，也是本书的涵盖范围。

# 在集群中使用会话 ID

你在会话集群中可能面临的直接问题是，会话作为对象存在于内存中，并且仅存在于 Web 服务器的单个实例上。在纯轮询或智能负载均衡的场景下，来自同一客户端的两个连续请求可能会发送不同的 Web 容器。

第一个 Web 容器实例会为收到的第一个请求分配一个会话 ID，然后当下一个请求进入 Web 容器的另一个实例时，第二个实例将无法识别该会话 ID，并创建且分配一个新的会话 ID。此时，会话将变得毫无用处。

解决此问题的一种方案是使用粘性会话（sticky sessions）。粘性会话的理念是负载均衡器感知会话的，并且始终将来自同一会话的请求发送到同一服务器。这可以通过多种方式实现，很大程度上取决于负载均衡技术。例如，负载均衡器可能会感知服务器的 Cookie 并知道它是一个会话，利用其作为确定何时应将请求发送到同一服务器的机制。某些负载均衡器可以添加自己的会话 Cookie，以便在后续请求中识别并识别这些 Cookie（是的，单个请求可以属于许多不同的会话，只要 Cookie 名称或会话 ID 传输技术都不同即可）。

这些技术的潜在缺点是，Web 容器无法使用 SSL/HTTPS，因为这会阻止负载均衡器检查或修改请求。然而，许多负载均衡器支持处理 HTTPS 流量的解加密，所以如果你还没有让你的应用程序安全；只需将加密从服务器移动到负载均衡器。某些组织甚至偏于这种设置，但请记住这会阻止你使用 SSL 会话 ID 作为你的会话 ID。最后，某些负载均衡器使用源和目的 IP 地址的组合来确定何时向同一服务器发送多个请求，但由于使用 IP 地址建立 HTTP 会话是一个坏主意的原因相同，这可能会带来麻烦。

Tomcat 环境中最常见的负载均衡管理方式是使用 Apache HTTP 或 Microsoft IIS Web 服务器来在 Apache Tomcat 实例之间进行请求负载均衡。Apache Tomcat 连接器 `http://tomcat.apache.com/connectors-doc/` 提供了一种将这些 Web 服务器与 Tomcat 织合的机制。连接器的 `mod_jk` 组件提供了使用 Tomcat 会话 ID 的粘性会话功能。如果使用 IIS，`isapi_redirect` 是在 ways IIS 时提供会话能力的 IIS 连接器。随着负载随时间推移而增加，你可以设置一个简单的轮询式负载均衡器，在多个 HTTP 或 IIS Web 服务器之间平衡请求。

图 5-5 所示的这种多层方法可以在保持会话亲和性的同时实现极高性能和高可用。连接器（`mod_jk` 或 `isapi_redirect`）使用名为 `jvmroute` 的 Tomcat 连接器来确定将请求发送到哪个实例。考虑以下会话 ID：

```
AA64E2624FFEA76C148DF5BCBE03
```

在具有多个 Tomcat 实例的负载均衡环境中，每个实例在 Tomcat `conf/server.xml` 配置文件的 `<connector>` 元素中配置 `jvmroute`。`jvmroute` 被附加在所有 ID 的末尾。对于三个 `jvmroute` 为 `tcn01`、`tcn02` 和 `tcn03` 的集群，如果该会话源自 `tcn02`，那么同一个会话 ID 将看起来像这样：

```
AA64E2624FFEA76C148DF5BCBE03.tcn02
```

Web 服务器连接器（`mod_jk` 或 `isapi_redirect`）将识别该会话属于 Tomcat 实例 tcn02，并始终将请求发送到该实例。如果你的应用程序通过 HTTPS 安全，Web 服务器将负责这项工作，以便 SSL 会话跟踪能够正常运行。

### 理解会话复制与故障转移

使用粘性会话的主要问题是它可能支持扩展性，但不支持高可用性。如果创建会话的 Tomcat 实例宕机，会话将丢失，用户必须登录。更糟糕的是用户可能会丢失正在进行的工作。为了这些目的，会话可以在整个集群中复制，以便所有会话对所有 Web 容器可用。在你的应用程序中启用会话复制很容易实现。你只需要在部署描述符中添加 `<distributable>` 标签即可：

```
<distributable />
```

这就是全部。该标签没有属性、标签或内容。部署描述符中该标签的存在告诉容器在集群（如果存在）中复制会话。当会话在一个实例中创建时，它会被复制到其他实例。如果会话属性发生更改，会话将重新复制到其他实例，以便它们拥有最新版本的会话。

当然，这实际上并不简单。它只是标记了你的应用程序支持分布式会话。它并没有配置你的 Web 容器的会话复制机制（这是一个复杂的主题，本书未进行讨论）。它也没有管理你的应用程序最佳实践。你必须小心会话属性（如果它们不是可序列化的，在调用 `setAttribute` 时将抛出 `IllegalArgumentException`）以及你如何更新这些会话属性。考虑来自购物车部分的这段片段：

```
## 142 | 第5章 维护状态会话
```

```java
@SuppressWarnings("unchecked")
Map<Integer, Integer> cart =
    (Map<Integer, Integer>)session.getAttribute("cart");
if (cart.containsKey(productId))
    cart.put(productId, 0);
cart.put(productId, cart.get(productId) + 1);
```

Web 容器并不知道（也无法知道）Map cart 项已以这种方式发生了变化。正因如此，对 session 的更改将不会复制，这意味着其他实例无法感知购物车中的新项目。这可以通过简单的方法解决：

```java
@SuppressWarnings("unchecked")
Map<Integer, Integer> cart =
    (Map<Integer, Integer>)session.getAttribute("cart");
if (cart.containsKey(productId))
    cart.put(productId, 0);
cart.put(productId, cart.get(productId) + 1);
session.setAttribute("cart", cart);
```

注意新增的代码 `session.setAttribute("cart", cart);`。这看起来可能很愚蠢，因为你用已经分配给该属性的同一个对象替换了 cart session 属性。然而，调用此方法会通知容器 session 已更改，并导致 session 被复制。每当你更改分配给 session 的对象时，都必须再次调用 `setAttribute` 以确保更改被复制。

还有一个与会话复制概念相关的监听器。作为属性被添加到 session 中的对象必须实现 `javax.servlet.HttpSessionActivationListener`。当 session 被序列化以复制到其他服务器时，系统会调用 `sessionPassivate` 方法，让绑定到 session 的对象先执行某些操作。当 session 在另一个容器中被反序列化时，会调用 `sessionDeactivate` 方法通知该属性它已被反序列化。

最后一点说明：粘性会话（Sticky sessions）和会话复制并不是互斥的。一旦将两者结合以实现会话故障转移——会话仍然被复制，但同一会话中的请求将失败，会被发送到已经知道该会话的不同实例。你可以使用这些技术通过粘性会话提高应用程序的效率，但这些功能超出了本书的范围。关于你的 Web 容器的文档应该描述它支持的复制功能以及如何使用它们。

### 总结

在本章中，你学习了会话的概念以及客户端与服务器之间建立会话的方式。你学习了许多与会话相关的潜在安全漏洞以及如何解决每种漏洞，还学习了最安全的会话 ID 传输方法：使用 SSL 会话 ID。你通过一个购物车应用程序探索了在 Java EE 中使用会话，并在客户支持应用程序添加了日志支持。你还发现了如何检测会话的变化，并用于在另一个会话内部建立会话注册表。最后，你学习了会话集群背后的概念，并学习了会话集群的一些挑战和处理方法。在接下来的三个章节中，你将探索一些让 JSP 开发比以往任何时候都更简单的技术，并帮助你彻底告别 JSP 中的 Java 代码。

## 在 JSP 中使用表达式语言（EL）

### 本章内容

- 关于表达式语言（EL）的一切
- 如何使用 EL 语法编写代码
- 如何在 EL 表达式中使用作用域变量
- 如何在 EL 表达式中使用 Java 8 流访问集合
- 用表达式语言替换 Java 代码

### 本章的 WROX.COM 代码下载

你可以在 `www.wrox.com/go/projavaforwebbaps` 的“Download Code”标签页找到本章的 wrox.com 代码下载。本章分为以下几个主要示例：

- 用户配置项目 (User-Profile Project)
- 客户支持 v4 项目 (Customer-Support-v4 Project)

### 本章新增的 Maven 依赖

除了之前章节引入的 Maven 依赖，你还需要以下依赖：

```xml
<dependency>
  <groupId>javax.el</groupId>
  <artifactId>javax.el-api</artifactId>
  <version>3.0.0</version>
  <scope>provided</scope>
</dependency>
```

### 理解表达式语言

到目前，你一直在使用 JSP 输出动态内容。但请记住，第四章提到抑制使用声明（declarations）、脚本段（scriptlets）和表达式（expressions）。这不仅为你的 JSP 提供了巨大的力量（有时是过强的），还让几乎或没有 Java 背景的 UI 开发人员难以编写 JSP。将有一种更简单的方法使用 Java 代码显示数据并执行简单操作。你可能认为 `<%%%>` 标签可以提供解决方案，而且这些标签确实需要替换 Java 操作。然而，这些标签使用起来既笨拙又尴尬。什么是一种易于阅读、让 Java 开发者和 UI 开发者都熟悉，并具有一组简单的规则和运算符以便于数据访问和处理的工具呢？

### 它的用途

表达式语言（EL）最初是作为 JSP 标准标签库（JSTL）的一部分开发的（你将在下一章中学习它），用于支持在不使用脚本段、声明或表达式的情况下渲染 JSP 页面。它的灵感很大程度上基于 ECMAScript（JavaScript 的基础）和 XPath 路径。当时它被称为简单可能表达式语言（SPEL），但后来缩短为表达式语言（EL）。EL 是 JSP 1.0 规范的一部分，随 JSP 1.2 发布，当时只能在 JSP 标签的属性中使用。在 JSP 2.0 和 JSP 1.1 中，EL 表达式（由于其流行性）从 JSTL 规范移动到了 JSP 规范，并可以在 JSP 的任何地方使用，而不仅仅限于 JSTL 标签属性。

在这一进展进行期间，JavaServer Faces 的工作已经启动，但由于 JSP 1.2 是作为 JSP 的替代方案，JSP 也需要自己的表达式语言。然而，当时现有的用于 JSP 的 EL 存在几个缺点。首先，JSP 需要控制表达式的求值以维持 JSP 生命周期周期的某些点。一个表达式可能在页面渲染期间需要求值，也可能在回传到 JSP 页面时需要。此外，JSP 对方法表达式的支持比 EL 好。结果是形成了两种非常相似的表达式语言——一个用于 JSP 2.0，另一个用于 JSP 1.0。

显然，拥有两个独立的 Java 表达式语言并不是理想的，因此当我们开始 JSP 2.1 规范时，我们努力将 JSP 2.0 表达式语言与 JSP 1.1 表达式语言合并。结果是产生了用于 JSP 2.1 和 JSP 1.2 的统一表达式语言（JUEL）。

尽管 EL 是 JSP 和 JavaServer Faces 的一部分，但它并没有自己的规范和 JAR 产物。EL 的用例仍在不断扩展和改进，直到 Java EE 7，它被移动到了自己的 JSR（JSR 341）。

### 理解基础语法

EL 的基础语法将需要求值的表达式与页面的其他部分隔离开来。JSP 解释器必须检测 EL 表达式的开始和结束，以便进行解析和求值。EL 语法有两种不同的类型：`即时求值`和`延迟求值`。

### 即时求值

即时求值 EL 表达式是指 JSP 引擎在页面渲染时应该解析并求值的表达式。这意味着 JSP 代码从上到下执行，当 JSP 引擎遇到 EL 表达式时就会进行求值。即时求值的 EL 表达式如下，其中 `expr` 是有效的 EL 表达式。

```jsp
${expr}
```

美元符号以及括号定义了 EL 表达式的边界。括号内的所有内容都作为 EL 表达式进行执行。更重要的是，这意味着你不能在 JSP 的其他地方使用这种语法；否则它会被作为 EL 表达式执行并可能导致错误。如果你需要向响应中输出这种语法的内容，你需要转义美元符号：

```jsp
\$(not expression)
```

美元符号前的反斜杠指示 JSP 引擎这实际上不是 EL 表达式，不应被求值。之前的示例将字面量写入响应的是 `$(not expression` 而不是 `\$`，结果是相同的。

```jsp
&#36;$(not expression)
```

JSP 引擎也会忽略这种，许多人发现使用反斜杠更方便。这仅仅是个人喜好问题。当然，你可能确实需要在你想要求值的表达式前面加上反斜杠。这需要使用反斜杠 XML 实体：

```jsp
\\${EL expression to evaluate}
```

在这种情况下，EL 表达式将在反斜杠之后被求值并渲染。

### 延迟求值

延迟求值 EL 表达式是统一表达式语言的一部分，主要支持 JavaServer Faces 的需求。虽然延迟语法在 JSP 中是合法的，但在 JSP 中并不常见。延迟语法与立即语法几乎完全相同，再次当

```jsp
#{expr}
```

在 JSP 中，延迟表达式（deferred expressions）可以在页面渲染时或页面回传（postback）期间、甚至可能在之后进行求值。这些细节与本书无关，但你必须理解，这与 JSP 不同，JSP 具有其自身的生命周期概念。在 JSP 中，`${deferred syntax}` 只在 JSP 标签属性中有效，用于将 EL 表达式的评估推迟到 `tag` 的渲染过程。EL 表达式不是在属性值绑定到标签之前进行评估（像 `${}` 那样），而是标签属性获取一个未评估的 EL 表达式的引用。然后，标签可以在适当的时候调用并评估该 EL 。这在第 8 章中会有更多使用和探索，但它很少使用。

延迟语法的的一个潜在问题是模板语言和 JavaScript 框架也使用 `${}` 语法。因此，如果你使用这些替换符，通常需要对它们进行转义，以免它们与延迟 EL 表达式混淆：

```
\\not an EL expression\n&#35;also not an EL expression
```

然而，这对于某些使用此语法的框架可能不起作用，如果你需要经常使用它，或者你有一组需要与 EL 2.1 或更高版本一起的 JSP，那将非常麻烦。（此外，XML 实体与 JavaScript 不兼容。）由于由于，还有另一种方法可以防止 `${}` 字面量被评估为延迟表达式。在部署描述符的 `<jsp-config>` 部分，你可以向任何位置添加以下标签：

```xml
<jsp-property-group>
<deferred-syntax-allowed-as-literal value="true"></deferred-syntax-allowed-as-literal>
</jsp-property-group>
```

这允许以字面量方式使用 `${}` 语法，并避免了你对其中的井号符号进行转义。如果你需要对单个 JSP 进行此控制，可以在任何 JSP 的页面指令中使用 `deferredSyntaxAllowedLiteral="true"` 属性。

在本书的剩余部分，你将在示例代码中看到立即评估的 EL 语法，除一个例外外你将不会使用它。在第 8 章关于自定义标签和函数库的讨论中，你将在定义自定义标签时探索 `<deferred-value>` 和 `<deferred-method>` 选项。这也需要延迟语法。

### 放置表达式 (Placing Expressions)



简单来说，EL 表达式几乎可以用于 JSP 中的任何地方，但有几个例外。它们没有指令。`<% page %>`、`<% include %>` 和 `<% tag %>` 是在 JSP 编译时评估的，而 EL 表达式是在 JSP 渲染时后评估的，因此无法工作。此外，EL 表达式在 JSP 声明 (`<%! %>`)、脚本 (`<% %>`) 或表达式 (`<%= %>`) 中是无效的。如果在其中任何一处使用，EL 表达式将被简单忽略，最坏的情况下可能会导致语法错误。

除外，EL 表达式可以放在任何地方。你可能会看到 EL 表达式的一个地方是写在屏幕上的简单字面文本：

用户将看到 `${expr}` 文字并知道 `${expr}` 是好的。

此示例包含两个 EL 表达式，它们在求值时被内联放置在显示的文本中。如果第一个表达式评估结果为 "red"，第二个评估结果为 "it"，用户将看到：

用户将看到红色的文本，并知道它是好的。

此外，表达式可以在标准 HTML 标签属性中使用，如下例所示。

```html
<input type="text" name="something" value="${expr}">
```

HTML 标签不是允许 EL 表达式唯一的地方。你还可以在 JSP 标签属性中使用它们，如下面的代码所示：

```jsp
<c:url value="${expr}/${expr}">
  <c:redirect url="${expr}" />
</c:url>
```

如你所见，EL 表达式不需要构成整个值。相反，属性值的一个或多个部分可以包含 EL 表达式。你可能对其他 HTML 特性产生好奇，例如 JavaScript 或级联样式表。JSP 引擎不解析这些性质的内容，并将它们像字面量一样写入响应中，因为许多内容包含引号或字面量格式的 EL 表达式：

```html
<script type="text/javascript">
  var employeeName = '${expr}';
  var booleanValue = ${expr};
  var numericValue = ${expr};
</script>
<style type="text/css">
  span {
    color: ${expr};
    background-image: url('/some/place/${expr}.png');
  }
</style>
```

到目前你已经学习了 EL 的不同类型以及 EL 表达式如何放置，但你可能好奇 `expr` 到底是什么样子的。在下一节中，你将学习可以在表达式中放入的内容。

## 使用 EL 语法进行编写

EL 表达式像任何其他语言一样，都有特定的语法。像 Java、JavaScript 和大多数其他语言一样，语法是严格的，违反它将在 JSP 渲染时导致语法错误。然而，与 Java 不同，EL 语法是松散类型，并内置了许多隐式类型转换，类似于 PHP 或 JavaScript 等语言。表达式的主要规则是它必须评估为某个值。你不能在表达式内部声明变量或执行某种赋值……（例如，`${object.method()}` 仅在方法具有非空返回类型时有效）。EL 设计并不是为了取代 Java；相反，它的设计是为了为你提供无需 Java 创建 JSP 所需工具。

## 第 6 章 在 JSP 中使用表达式语言

（注：提供的文本包含大量重复的标题和内容，以上代表了唯一的逻辑内容流。）

- `callMethod` 方法在对象变量上被调用，并将 `x (7)` 作为其参数传递。

- 字符串 "Hello, World!" 被求值。该表达式的结果是最后一个分号之后表达式的结果："Hello, World!"

`x = y + 3` 表达式的结果和 `object.callMethod(x)` 表达式的结果会被丢弃。这对于给 EL 变量赋值，然后将值包含在表达式的其他部分，而不仅仅是输出该值特别有用。

为了方便理解，以下列表总结了从顶部（最高）到部（最低）的优先级顺序，仅保留符号并去除了杂乱。请记住，运算符按照它们在表达式中出现的顺序从左到右进行求值。

```
],
()
unary -, !, %, empty
*, /, div, % mod
+ math, binary -
+= string
< lt, >, gt, <=, >=, ge
==, eq, !=, ne
&& and
|, or
?, :
->
=
;
```

> 注意：在 Java 中，你使用 `equals` 方法来测试对象之间的相等性。例如，如果两个字符串都是 "Hello"，如果你想测试它们是否等于 "Hello"，你应该使用 `"Hello".equals("Hello")` 而不是 `== "Hello"`。后者测试的是两个引用指向同一个实例，而不是两个对象相等。然而，在 EL 表达式中，使用 `==` 或 `!=` 运算符来测试对象相等，而不是调用 `equals` 方法。（EL 中没有测试两个引用是否相同的等价方法。）同样，你使用 `!=` 而不是 `"Hello".equals("Hello")`。

关系比较运算符 `<`、`lt`、`gt`、`<=`、`le` 和 `ge` 的用法与相等运算符相似。任何实现了 `java.lang.Comparable` 接口的两个，只要类型相同或其中一个可以转换为另一个，就可以使用比较运算符进行比较。因此，EL 中的 `${o1 >= o2}` 和 `${o1 ge o2}` 等同于 Java 中的 `o1.compareTo(o2) >= 0`，而 `${o1 < o2}` 和 `${o1 lt o2}` 等同于 `o1.compareTo(o2) < 0`。

# 字面量

统一表达式语言支持使用特定语法指定字面量。你已经见过 `true`、`false` 和 `null` 关键字，它们都是字面量。

此外，EL 还可以有字符串字面量。与 Java 不同（Java 的字符串字面量始终由双引号包），EL 中的字符串字面量可以使用双引号或单引号，类似于 PHP 和 JavaScript。因此，以下示例中的两个表达式都是有效的。

```
${"This string will be rendered on the user's screen."}
${'This string will also be "rendered" on the screen.'}
```

你可以看到，使用任何类型的字符串字面量都有优缺点，在许多情况下，你只需要使用对特定情况最简单的一种。如果某个字符串内部包含单引号，使用双引号可能是最简单的。同样，如果字符串内部包含双引号，使用单引号字面量可能最简单。

必须注意的一点是在使用 JSP 标签属性使用 EL 表达式字面量。因为这些是由 JSP 引擎求值的，属性周围的引号与字符串字面量周围的引号会冲突。因此，以下 EL 属性值都是无效并会导致语法错误的：

```
<c value="${value}" />
<c value='${value}' />
```

解决这种冲突有两种有效方法。你可以对属性和字面量使用相反的引号，或者对字面量的引号进行转义。以下示例中的四行都是有效的：

```
<c value="${value}'" />
<c value='${value}" />
<c value="\${value}" />
<c value='\${value}\' />
```

通常，你会发现使用相反引号比转义更容易。但如果你的字符串字面量包含单引号或双引号，且你需要将表达式放在属性值中呢？没有办法，你必须转义某些内容。下面的六行代码都是处理此情况的有效方法。

需要在属性值内的字符串字面量中混合使用单引号和双引号吗？从这里开始：

```
<c value="${some attribute\'s \"value\"}" />
<c value='${some \"attribute\" \'value\'}' />
```

正如你所看到的，这可能会迅速失控。如果可能，最好保持你的字符串字面量。关于字符串字面量的最后一点是，从 Java EE 7 的表达式语言 3.0 开始，你可以像在 Java 中那样在 EL 表达式中拼接字符串字面量。以下示例中的所有行都是等价的并产生相同的输出。

```
The user will see ${expr} text and ${expr}.
${'The user will see ' + expr + ' * ' + text and ' += '.'}
${'The user will see ' + expr + ' * ' + text and ' += ''}
```

如果 `expr` 返回一个不是字符串的对象，它将通过调用该对象的 `toString` 方法被转换为字符串。

EL 中的数字字面量比 Java 简化了，你还可以在 Java 中无法执行的对象之间执行算术运算。考虑三个整数类型的数字字面量：

```
${105}
${-132147}
```

构建 List（列表）与构建 Set（集合）几乎相同，只是使用方括号而不是大括号，工作原理与 JavaScript/JSON 完全相同：

```
[1, 2, 'three', [x, y], {'foo': 'bar'}]
```

注意，你可以像这样嵌套集合，因为这个 `ArrayList<Object>` 是另一个 List，而第五个元素是一个 Set。在 Set 中，元素会将集合对象插入到其他集合对象。与 Set 一样，List 用逗号分隔。

最终创建一个 `HashMap<Object, Object>` 的集合与 JavaScript 和 JSON 中的对象字面量完全相同：

```
{'one': 1, 2: 'two', 'key': x, 'list': [1, 2, 3]}
```

这里的元素同样要求是映射到值的键，而不仅仅是值。因此，该字面量中的每个元素都是一对由逗号分隔的对象，冒号左侧的对象是键（key），右侧的对象是值（value）。该字面量中的 `list` 键映射到一个具有值 1、2 和 3 的 List 对象。

# 对象属性与方法

EL（表达式语言）除了你熟悉的标准语法外，还提供了访问 JavaBean 中属性的简化语法。你无法访问 EL 表达式的公共字段（public fields）。假设有一个带有公共字段 `size` 的 `Shirt` 类。假设变量名为 `shirt`，你可能认为可以通过以下 EL 表达式访问 `size`：

```
${shirt.size}
```

然而，这并非全部。当 EL 看到这种语法时，它寻找的是属性而不是字段。但什么是属性？考虑一个修改后的 `Shirt`，其中 `size` 是一个封装的私有字段，并带有 JavaBean 访问器（accessor）和修改器（mutator）方法。表达式 `shirt.size` 变成了调用 `shirt.getSize()` 的快捷方式。这适用于任何字段。只要具有标准的 JavaBean 方法，就可以通过这种方式访问。如果 `Shirt` 有一个名为 `sizeCategory` 的字段，你可以通过 `shirt.sizeCategory` 访问它。对于布尔字段（以及其他布尔字段），访问器可以以 `get` 或 `is` 开头。因此，对于名为 `expired` 且具有 `getExpired` 或 `isExpired` 方法的字段，你可以通过 `shirt.expired` 访问该字段。

这不是你访问 JavaBean 内部属性的唯一技术。遵循 ECMAScript 和 XPath 语言的精神，你也可以使用 `[]` 操作符来访问属性。以下表达式分别使用了 `getSize`、`sizeCategory` 以及使用 `getExpired` 或 `isExpired` 方法的 `expired`：

```
${shirt['size']}
${shirt['sizeCategory']}
${shirt['expired']}
```

在早期的 EL 版本中，EL 2.1 增加了访问 JavaBean 属性的能力。因此，你无法访问对象上的方法。所以你可以通过 `${shirt.getSize()}` 获取 `Shirt` 的大小，而不是 `${shirt.size}`，但为什么要这样做呢？后者显然简单得多。当一个返回结果的方法还需要某些输入时，方法调用就变得非常有用了。

假设你有一个不可变的类 `ComplexNumber`，它代表数学复数（形式为 `a + bi` 的实数和虚数的组合）。该类无疑会被重载，以便通过一个 `plus` 方法允许你向其添加其他数字。（可能该方法可以接受整数、双浮点数或另一个 `ComplexNumber`。）你可以调用 `plus` 方法并传入一个参数，结果 `ComplexNumber` 将是该表达式的值：

```
${complex.plus(12)}
```

在这个示例中，渲染了 `ComplexNumber` 的字符串表示。然而，假设你希望字符串表示中的 `i` 能够被正确地斜体化，使其看起来像复数的正规数学表示。你可能在 `ComplexNumber` 类上定义一个 `toHtml` 方法来实现这一点。然后你可以像这样渲染它：

```
${complex.plus(12).toHtml()}
```

这些链式方法标识了你在标准 Java 代码中执行此项操作的方式。

# EL 函数

在 EL 中，函数是映射到类中静态方法的特殊工具。与符合模式的 XML 标签一样，函数被映射到一个命名空间。函数的整体语法如下，其中 `[ns]` 是命名空间，`[ns:fn]` 是函数名，`[al1]` 到 `[an]` 是参数：

```
${[ns]:fn([al1, al2, a3, ...])}
```

函数定义在标签描述符（TLDs）中，这听起来可能很奇怪——函数不是标签。这是 EL 早期的产物，当时它是 Java 标准标签库（JSTL）的一部分，EL 只能在 JSP 标签属性内部使用。因为该概念已经支持命名空间，将 EL 函数定义保留在 TLD 中是合理的。

你将在第 8 章学习更多关于 TLD 和定义函数的知识。然而，JSTL 中已经定义了一组函数，大多数开发者在使用 JSP 时都会用到。所有函数都处理字符串——修剪、连接、分割、转义等。按照惯，JSTL 库的命名空间为 `fn`；但你可以在 `taglib` 指令中任意命名。在下一节使用 EL 函数时，这里是一些最常用的 JSTL 函数及其功能：

- `${fn:contains(String, String)}` — 此函数测试第一个字符串是否包含第二个字符串的一个或多个实例，如果是，则返回 true。

- `${fn:escapeXml(String)}` — 如果你准备输出特殊字符，可以使用此函数转义特殊字符。`<` 变成 `&lt;`，`>` 变成 `&gt;`，`&` 变成 `&amp;`，`"` 变成 `&quot;`。这是防止跨站脚本（XSS）攻击中一个特别重要的工具。

- `${fn:join(String, String)}` — 此函数使用指定的字符串作为分隔符连接字符串在一起。例如，这可以将电子邮件地址连接成一个字符串显示在页面。

- `${fn:length(Object)}` — 如果参数是字符串，此函数调用 `length` 方法并返回结果。如果是 `Collection`、`Map` 或数组，它返回其大小。不支持其他类型。这可能是 JSTL 中实用的函数之一。

- `${fn:toLowerCase(String)}` 和 `${fn:toUpperCase(String)}` — 你可以使用这些函数将字符串的大小转换为小写或大写。

- `${fn:trim(String)}` — 此函数修剪字符串两端的空白字符。

JSTL 中还有更多函数，你可以点击查看剩余部分。遗憾的是，Java EE 6 和 7 中的 JSTL 1.2 没有现成的 HTML 文档。

# 静态字段与方法访问

EL 3.0 的新功能允许你访问任何类中的公共静态字段和静态方法。你可能会认为（有些人认为这给 JSP 作者赋予了太大的权力，使他们能够像通常在 scriptlet 中做样的任何事情），这取决于你认为它是好是坏，但该功能在 3.0 中存在且无法禁用。

你访问静态字段的方法与 Java 中相同——使用完全限定的类名和字段或方法并用点运算符分隔。例如，你可以通过以下表达式访问 `Integer` 类上的 `MAX_VALUE` 常量：

```
${java.lang.Integer.MAX_VALUE}
```

除非使用 page 指令导入了类，否则类名必须完全限定。记住在 JSP 中，就像 Java 中一样，类都是为你导入的。因此，之前的表达式可以写成：

```
${Integer.MAX_VALUE}
```

通过这种方式，你可以访问 JSP 可以使用的任何类的静态字段或方法。需要注意的是你只能读取字段的值，不能对其写入。（当然，如果一个字段也是 `final` 的，你通常也无法对其写入。）调用静态方法同样简单。假设你想反转数字的位顺序并观察数字的变化：

```
${java.lang.Integer.reverse(42)}
```

```
${Integer.reverse(24)}
```

此表达式调用了 `Integer` 类的静态 `reverse` 方法，并传入 42 作为其参数。除了调用静态方法外，你还可以调用类的构造函数，它返回该类的实例，你可以进一步访问其属性，或将其转换为字符串输出。

```
${com.wrox.User()}\n${com.wrox.User('First', 'Last').firstName}
```

尽管静态访问可以完全取代 EL 函数和函数库的行为，但这并不意味着函数库是多余。之前对 `Integer.reverse` 的静态方法调用可能很方便，但如果有一个映射到静态方法的理论上 int 函数库，下面的表达式会更方便：

```
${reverse(42)}
```



这可能并没有短多少，但想象一个长得多的类，你就能很快看出为什么函数库非常有用。静态字段访问最方便领域之一就是枚举（enums），这是你接下来将学习的内容。

# 枚举

你可能在某个时候接触过 Java 枚举，如果你已经使用 Java 一段时间了，你可能很熟悉它们有多么用和强大。传统上，EL 中的枚举在需要时会被转换为字符串。例如，如果你的 JSP 作用域变量命名为 `dayOfWeek`，它代表了新 Java 8 日期时间 API 中 `java.time.DayOfWeek` 的值之一。你可以使用以下表达式测试 `dayOfWeek` 是否为周六：

```
${dayOfWeek == 'SATURDAY'}
```

`dayOfWeek` 变量被转换为字符串并与 "SATURDAY" 进行比较。这与 Java 不同，在 Java 中这种转换永远不会自动发生。尽管这方便，但显然不是类型安全的。如果你漏掉了周六（或者如果周六不再是一周中的某一天），你的 IDE 可能会捕获它；如果你在持续集成构建期间捕获 JSP 来检查它，它也无法捕获。不过，在 EL 3.0 中，你可以使用静态字段访问语法来实现类型安全的枚举常量。毕竟，枚举常量只是其枚举类型的公有静态型字段：

```
${dayOfWeek == java.time.DayOfWeek.SATURDAY}
```

而且，如果你将 `dayOfWeek` 导入到你的 JSP 中，该表达式就像像字符串作为枚举的表达式一样简单（并且更像你在 Java 代码中看到的）：

```
${dayOfWeek == DayOfWeek.SATURDAY}
```

这两种技术都是类型安全的，并且会在你的 IDE 和在编译时进行通过验证。无论你打算使用哪种，我们都推荐使用类型安全的方法。

# Lambda 表达式

表达式语言 3.0 将 Lambda 表达式视为其新特性之一。Lambda 表达式是一个匿名函数，通常作为高阶函数（例如 Java 方法）的参数传递。在最通用的意义上，Lambda 表达式是参数名列表（如果函数没有参数则使用某些占位符），后面跟着某种运算符，最后是函数体。在某些支持 Lambda 表达式的语言中，顺序是反过来的或有所不同。EL 中的 Lambda 表达式语法与 Java 8 的 Lambda 表达式几乎完全相同。两者之间的主要区别在于，在 Java 中，Lambda 表达式体可以包含任何在 Java 方法中合法的内容，而在 EL 中，Lambda 表达式体是另一个 EL 表达式。

就像 Java Lambda 表达式一样，EL 表达式使用箭头运算符 `->` 来将左侧的 Lambda 表达式与右侧的表达式分开。同样，就像 Java Lambda 表达式，如果恰好有一个参数，表达式参数周围的括号是可选的。以下表达式是有效的 EL Lambda 表达式：

```
a -> a + 5
(a, b) -> a + b
```

当然，这些 Lambda 表达式本身并不是完整的 EL 表达式。必须对这些 Lambda 表达式进行某些处理。它们可以被立即求值：

```
${(a -> a + 5)}
${(a, b) -> a + b(4, 7)}
```

在前面的 EL 表达式中，Lambda 表达式被声明并立即求值。两个 EL 表达式的输出结果分别为 9 和 11。注意，Lambda 表达式本身被括号包围使你能够执行它。你也可以定义一个 EL Lambda 表达式供以后使用：

```
${v = (a, b) -> a + b}
```

这里第二个表达式的输出是 18，因为它在分号之前执行了 Lambda 表达式。变量 `v` 现在可以在页面上随其后的任何其他 EL 表达式中使用。如果 Lambda 非常复杂，这一点特别有用。

最后，你还可以将一个 EL Lambda 表达式作为参数传递给 EL 表达式内部调用的方法。

```
${users.stream().filter(u -> u.lastName == 'Williams' ||
u.lastName == 'Sanders').toArray()}
```

# 集合

在 EL 中，可以使用点 `.` 和括号 `[]` 运算符轻松访问集合。你如何使用这些运算符取决于集合的类型。记住，在 Java 集合 API 中，所有集合都是 `Collections` 或 `Maps`。在 `Maps` 的层次结构中，你有许多不同类型的 map，它们都共享一个共同基础：某些键与某些值关联。`Collection` 层次结构稍微复杂一点。在其中你有 `Sets`、`Lists` 和 `Queues`。因为每种类型的集合访问值的方式不同，EL 对每种都略有支持。

在 `Map` 中访问值很简单，并模拟了访问 JavaBean 的属性。假设你有一个名为 `map` 的 Map，键 `username` 映射到值 "Jonathan"，键 `userId` 映射到值 "27"。你可以像下面的示例中使用括号运算符访问 map 的这两个属性：

```
${map["username"]}
${map["userId"]}
```

## 使用 EL 语法编写

然而，并不是你访问 Map 值的唯一技术。你还可以将键视为 bean 属性并使用点运算符访问它们的值：

```
${map.username}
${map.userId}
```

尽管第二种技术涉及的字符更少（确切说是少三个），但有些人觉得第一种技术更自然，就像在支持运算符重载的语言中访问 Map 一样。然而，使用点运算符访问 Map 有某些限制。这意味着你的键不能包含空格、句号或连字符，不能以数字开头，且不能包含大多数特殊字符（尽管 Java 支持一些特殊字符，如美元符号 `$` 以及 á、é、î、ô、ñ 等）。如果包含 Java 中无效的字符，你必须使用括号。如果你不确定，为了安全起见，请使用括号。

访问 List 同样简单；然而，它的宽容性可能会让你惊讶。考虑一个命名为 `list` 的 List，按 0 到 2 的顺序包含 "blue"、red" 和 "green"。可以使用括号运算符访问值，就像 List 实际上是数组一样。代码演示了这一点：

```
${list[0]}
${list[1]}
${list[2]}
```

你不能将 List 视为属性并使用点运算符。这会导致语法错误：

```
${list.0} <<- EL 解释器会报错 --->
```

然而，EL 允许使用字符串字面量而不是数字来索引 List，就像 List 索引作为键的 Map 一样：

```
${list['0']}
${list['1']}
${list['2']}
```

使用字符串字面量的唯一规则是字符串必须能够转换为整数；否则你的代码会导致运行时错误。尽管这非常灵活，但没有理由使用字符串字面量作为 List 索引，这样做会导致其他开发者将你的 List 误认为 Map。我们推荐使用数字字面量。

其他集合类型（`Sets` 和 `Queues`）无法无法 EL 访问。这些集合不提供直接访问值的方法（例如 List 的索引或 Map 的键）。`Sets` 和 `Queues` 上没有 "get" 方法。你只能通过迭代访问这些类型集合的值 —— 我们将在下一章中探讨这一点。然而，对于所有类型的集合，你都可以使用 `empty` 运算符测试 Sets 和 Queues 是否为空：

```
${empty set}
${empty queue}
```

![](img/9c2d45f6d547f72cb870b3a991f62ef6_194_0.png)

你可以使用 EL 集合流对集合进行操作，并在本章后面的章节中将探索更多内容。

## 在 EL 表达式中使用作用域变量

表达式语言（EL）对作用域变量的处理以及变量解析使其特别有用且强大。回顾第 4 章，JSP 有一组隐式变量（request, session, out, application, config, pageContext, page 和 exception），你可以使用它们从请求、session 和执行环境中获取信息并影响响应。EL 也拥有一组类似的隐式变量；然而，它还有一个隐式作用域区域，用于解析其中的未知变量。这使得你能够以最少的代码从各种来源获取信息。你将在本节中探索这些主题。

本节你将可以使用从 jsp.com 网站下载的 User-Profile 项目。如果你是从头开始创建，请务必使用第 4 章的 `<jsp-config>` 和第 5 章的 `<session-config>` 创建你的 Web 应用程序，并创建一个包含唯一标签 `<c:redirect url="profile" />` 的 index.jsp。

你在之前的章节中使用过的 `/WEB-INF/jsp/base.jsp` 文件发生了细微变化。它不再仅仅声明 c 标签库，现在还声明了 fn 函数库，你将在本节中使用它：

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/core" %>
<%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>
```

> 关于作用域的说明
>
> 本节提到了四种不同的属性作用域（page, request, session 和 application），你可能并不理解它们之间的区别或它们究竟是什么。这些作用域中的每一个都比上一个范围更大、更长。你应该已经熟悉了 request 作用域：它在服务器接收请求时开始，在服务器完成向客户端发送响应时结束。request 作用域存在于任何可以请求对象的地方，绑定到请求的属性在请求完成后将不再被绑定。
>
> 在第 5 章中，你学习了 session 和 session 属性，因此现在你可能已经发现 session 在请求之间是持久的，并且任何访问 HttpSession 对象的代码都可以访问 session 作用域。当 session 失效时，它的属性会被解绑，作用域随之结束。
>
> page 和 application 作用域有所不同。page 作用域封装了特定页面（JSP）和请求的属性。当变量绑定到 page 作�域时，它仅对该 JSP 页面在请求生存期间有效。其他 JSP 无法访问绑定 page 作用域的变量，当请求完成后，该变量会被解绑。通过 PageContext 对象，你可以使用 getAttribute 方法来存储和检索存在于 page 作用域内的属性。application 作用域范围最广，跨越所有请求、session、JSP 页面和 Servlet。你在第 3 章学习过的 ServletContext 对象代表 application 作用域，存储在其中的属性属于 application 作用域。

## 使用隐式 EL

EL 在 EL 表达式的作用域内定义了 11 个变量，你将在本节稍后学习它们所有的。然而，隐式变量由于能够解析请求、session 或 application 作用域中的属性，变得更加有用且更常用。当 EL 表达式引用变量时，EL 按照以下程序解析变量：

1. 它检查该变量是否为 11 个隐式变量之一。
2. 如果该变量不是 11 个隐式变量之一，EL 解析器会在 page 作用域（`PageContext.getAttribute("variable")`）中查找与变量同名（区分大小写）的属性。如果找到了匹配的 page 作用域，则返回属性值作为变量的值。
3. 如果未找到匹配的 page 属性，解析器会查找与变量同名的 request 属性（`HttpServletRequest.getAttribute("variable")`），如果找到则使用该属性。
4. 解析器查找 session 属性（`HttpSession.getAttribute("variable")`），如果找到则使用它。
5. 解析器查找 application 属性（`ServletContext.getAttribute("variable")`），如果找到则使用它。
6. 在解析器在所有这些地方都进行查找后，如果没有找到与变量名匹配的隐式变量或属性，它将抛出错误。

这种方法的优之处在于，你不需要获取 `HttpServletRequest` 或 `HttpSession` 的实例即可使用其中一个对象上的属性。这在 User-Project 中的 `ProfileServlet` 和 `profile.jsp` 文件中得到了演示。开始查看 `com.wrox` 类 `User`，它有几个具有匹配访问器和修改器方法的私有字段：

```java
public class User {
    private long userId;
    private String username;
    private String firstName;
    private String lastName;
    private Map<String, Boolean> permissions = new Hashtable<>();
    // mutators and accessors
}
```

这是一个 POJO，你可以用它获取有关你的“用户”的信息。你需要查看这些信息，所以接下来创建一个非常简单的 `ProfileServlet`：

```java
@WebServlet(
    name = "profileServlet",
    urlPatterns = "/profile"
)
public class ProfileServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
        User user = new User();
        user.setUserId(19384);
        user.setUsername("Coder314");
        user.setFirstName("John");
        user.setLastName("Smith");

        Hashtable<String, Boolean> permissions = new Hashtable<>();
        permissions.put("user", true);
        permissions.put("moderator", true);
        permissions.put("admin", false);
        user.setPermissions(permissions);

        request.setAttribute("user", user);
        request.getRequestDispatcher("/WEB-INF/jsp/profile.jsp").forward(request, response);
    }
}
```

到为止，你已经看到了 Servlet 如何创建 User 实例、为其添加一些值、创建请求属性来持有用户并将请求转发到视图。重要的代码包含 `/WEB-INF/jsp/profile.jsp` 中，它显示了用户：

```jsp
<%@ variable id="user" type="com.wrox.User" %>
<!DOCTYPE html>
<html>
<head>
    <title>User Profile</title>
</head>
<body>
    User ID: ${user.userId} <br />
    Username: ${user.username} (${user.username.length()} characters) <br />
    Full Name: ${fn:escapeXML(user.lastName)}, ${fn:escapeXML(user.firstName)} <br />
    <b>Permissions(${fn:length(user.permissions)})</b><br />
    User: ${user.permissions["user"]}<br />
    Moderator: ${user.permissions["moderator"]}<br />
    Administrator: ${user.permissions["admin"]}<br />
</body>
</html>
```

# 164 | 第 6 章 在 JSP 中使用表达式语言

即使你不使用 IDE，或者使用不支持此惯例的 IDE，日后维护你 JSP 的其他开发者也能快速知道变量的类型。如果你养成使用 `@elvariable` 注释的习惯，编写 JSP 将将会变得简单得多。

接下来，你应该使用 ID 行：

```
User ID: ${user.userId}<br />
```

在这里，你在 Servlet 代码中添加到 request 的 `user` 属性已在 JSP 中通过隐式作用域作为 EL 变量被访问，你直接使用了属性 `userId` 而没有调用访问器方法。紧随其下对 `username` 执行了相同的操作，但是在 String 上调用了方法。

```
Username: ${user.username} (${user.username.length()} characters)<br />
```

注意，你没有直接调用 `length`，而是可以使用 `fn:length` 函数（该函数在代码后半部分用于集合），这作为替代方案的良好示例。接下来，你的 JSP 转义了姓和名并用逗号将它们拼接：

注意使用 `fn:escape` 来转义 HTML 字符，并使用 `++` 拼接操作符组合所有字符串。你 JSP 的第一部分输出了用户的权限：



# 164 | 第 6 章 在 JSP 中使用表达式语言

即使你不使用 IDE，或者使用不支持此惯例的 IDE，日后维护你 JSP 的其他开发者也能快速知道变量的类型。如果你养成使用 `@elvariable` 注释的习惯，编写 JSP 将会变得简单得多。

接下来，你应该使用 ID 行：

```
User ID: ${user.userId}<br />
```

在这里，你在 Servlet 代码中添加到 request 的 `user` 属性已在 JSP 中通过隐式作用域作为 EL 变量被访问，你直接使用了属性 `userId` 而没有调用访问器方法。紧随其下对 `username` 执行了相同的操作，但是在 String 上调用了方法。

```
Username: ${user.username} (${user.username.length()} characters)<br />
```

注意，你没有直接调用 `length`，而是可以使用 `fn:length` 函数（该函数在代码后半部分用于集合），这作为替代方案的良好示例。接下来，你的 JSP 转义了姓和名并用逗号将它们拼接：

注意使用 `fn:escape` 来转义 HTML 字符，并使用 `++` 拼接操作符组合所有字符串。你 JSP 的第一部分输出了用户的权限：

```
<Permissions>${fn:length(user.permissions)}</br />
User: ${user.permissions['user']}<br />
Moderator: ${user.permissions['moderator']}<br />
Administrator: ${user.permissions['admin']}<br />
```

`fn:length` 函数输出用户 `permissions` 集合中的元素数量，另外三行使用括号操作符访问 `permissions` Map 中的值。

作为一个练习，请编辑你的 `ProfileServlet`，将 `request.setAttribute("user", user)` 改为存放在 session 而不是 request：

```
request.getSession().setAttribute("user", user);
```

现在编译并运行你的应用程序。你不需要对 JSP 进行任何更改。`user` 属性现在可能处于不同的作用域（session 而不是 request），但它仍在隐式作用域中，因此你可以从 EL 作为 EL 变量访问它。当它被绑定时，`user` 属性持续到请求完成，然后就会被垃圾回收。现在它绑定到了 session，对于同一客户端的其他请求都是可用，即使它们访问了不同的页面。然而，这并不是你可以将 `user` 属性绑定的唯一作用域。将 `request.getSession()` 替换为 `this.getServletContext()` 并将其绑定到应用：

```
this.getServletContext().setAttribute("user", user);
```

现在再次编译并运行，无需对 JSP 进行任何更改。`user` 属性仍在隐式作用域中，并且可以通过 EL 表达式访问。你可以通过这种方式访问四个支持的作用域中的任何内容，这极大地简化了你编写 JSP 的任务。

# 使用隐式 EL 变量

正如本节前面提到的，EL 表达式中有 11 个可用的隐式 EL 变量。除了一个例外外，它们都是 Map 对象。大多数用于访问来自某些作用域的属性、请求参数或请求头。

- `pageContext` 是 `PageContext` 类的实例，也是唯一不是 Map 的隐式 EL 变量。你应该熟悉从第 4 章以及本节之前的内容中的 `PageContext`。使用该变量，你可以访问页面错误数据和异常对象（如果适用）、表达式评估器、输出写入器、JSP Servlet 实例、request 和 response、ServletContext、ServletConfig 以及 session。

- `pageScope` 是一个 `Map<String, Object>`，包含所有绑定到 `PageContext`（页面作用域）的属性。

- `requestScope` 是一个 `Map<String, Object>`，包含所有绑定到 `ServletRequest` 的属性。通过它，你可以在不调用 request 对象方法的情况下访问这些属性。

- `sessionScope` 也是一个 `Map<String, Object>`，它包含了当前会话的所有属性。

- `applicationScope` 是最后一个作用域，是一个 `Map<String, Object>`，包含所有绑定到 `ServletContext` 实例的属性。

- `param` 和 `paramValues` 相似之处在于它们都提供了对请求参数的访问。`param` 变量是 `Map<String, String>`，仅包含任何具有多个值的参数的第一个值（类似于 `ServletRequest` 中的 `getParameter`），而 `Map<String, String[]>` 类型的 `paramValues` 包含了每个参数的所有值（来自 `ServletRequest` 的 `getParameterValues`）。如果你知道某个请求参数只有一个值，`param` 更容易使用。

- `header` 和 `headerValues` 提供对请求头的访问，其中 `Map<String, String>` 的 `header` 仅包含任何多值头的第一个值，而 `Map<String, String[]>` 的 `headerValues` 包含了每个头的所有值。类似于 `param`，如果你知道某个头只有一个值，`header` 更容易使用。

- `initParam` 是 `Map<String, String>`，包含了来自 `ServletContext` 实例的所有初始化参数。

- `cookie` 是一个 `Map<String, java.servlet.http.Cookie>`，包含了用户浏览器随请求发送的所有 cookie。需要注意的是，可能有两个同名（但路径不同）的 cookie，在这种情况下此 Map 将包含按请求中出现顺序的给定名的第一个 cookie。这种顺序在每个请求之间可能会变化。在 EL 中，如果不遍历所有 cookie，就无法访问任何其他同名的重复 cookie。（在 EL 中迭代将在下一章学习如何操作。）

为了演示各种 EL 隐式变体及其使用方法，请在根目录下创建一个名为 `info.jsp` 的文件并放入以下代码：

```
<%
pageContext.setAttribute("a", "page");
request.setAttribute("a", "request");
session.setAttribute("a", "session");
application.setAttribute("a", "application");
%>
<!DOCTYPE html>
<html>
<head>
  <title>Scope Demonstration</title>
</head>
<body>
  Remote Address: ${pageContext.remoteAddr}<br />
  URL: ${requestScope.url}<br />
  Session ID: ${sessionScope.id}<br />
  Application Scope: ${applicationScope.a}<br />
  Page Scope: ${pageScope.a}<br />
  Request Scope: ${requestScope.a}<br />
  User: ${param.user}<br />
  Colors: ${fn:join(paramValues, ', ')}<br />
  Accept: ${header.Accept}<br />
  Session Cookie: ${cookie.JSESSIONID.value}<br />
</body>
</html>
```

管道（pipeline）由流水线源（即 Stream）、中间操作（例如过滤和排序）以及最后的终端操作（例如将结果转换为可以迭代和显示的 List）组成。

在 EL 3.0 中，你可以对任何是 Java 数组或 Collection 的 EL 变量调用 `stream` 方法。返回的 Stream 实际上并不是 `java.util.Stream`，因为 EL 3.0 必须在 Java 7 中运行，而 Java 7 并没有 Streams。返回的 Stream 是 Stream API 的一个 EL 特有实现。例如，以下表达式通过标题对书籍集合进行过滤，返回每个书籍可用的属性以获取标题和作者，并返回这些结果的 List：

```
books.stream().filter(b:b.title == 'Professional Java for Web Applications')
map(b->('title':b.title, 'author':b.author))
.toList()
```

## 理解中间操作

如所述，中间操作会过滤、排序、减少或以其他方式更改值集合，使集合最终达到所需状态。重要的是，当对 Stream 执行中间操作时，**原始的 Collection 或数组永远不会被修改**。中间操作只会影响 Stream 的内容。你会发现许多不同的中间操作，本节将让你学习最常用且实用的操作。你可以通过规范下载页面下载并阅读 JSR 341get PDF 来了解其他操作。

## 过滤 Stream

`filter` 操作是你最常用的操作。它会过滤 Stream 的内容，通常会减少其中包含的对象数量。`filter` 操作接受一个谓词（predicate）参数——返回布尔值并接受一个类型为 Stream 元素类型的参数的 Lambda 表达式。给定一个 E 为元素类型的 `List<E>`，`stream` 返回一个 `Stream<E>`。在其 `Stream<E>` 上调用 `filter` 时，你提供一个签名为 `E -> boolean` 的 `Predicate<E>`。然后你使用 E 的属性来决定是否将特定的 E 包含在结果 `Stream<E>` 中。为了更好地理解这一点，请考虑以下表达式：

```
${books.stream().filter(b -> b.author == "John F. Smith")}
```

在这种情况下，谓词是一个 Lambda 表达式，它接受书籍作为参数并测试该书籍的作者是否为 John F. Smith。当传递给 `filter` 操作时，谓词会应用于 Stream 中的每本书籍，生成的 Stream 仅包含谓词返回 true 的书籍。

你还可以使用特殊的 `distinct` 操作来过滤掉重复值。以下表达式从 List 中删除重复的 3 和 5：



```
${[1, 2, 3, 4, 5, 5, 5, 5, 6].stream().distinct()}
```

## 处理值

你可以使用 `forEach` 操作处理 Stream 中的值。像 `filter` 一样，`forEach` 接受对 Stream 中每个元素进行求值的 Lambda 表达式。然而，这个 Lambda 表达式是一个消费者（consumer），意味着它没有返回值。你可以用它来处理 Stream 中的值，可能会以某种方式对其进行转换。这里有一个潜在的用例：

```
books.stream().forEach(b -> b.setLastView(Instant.now()))
```

## 排序 Stream

你使用 `sorted` 操作对 Stream 进行排序。对于 `Stream<E>`，`sorted` 操作接受一个 `java.util.Comparator<E>`。作为 Java 开发者，你可能熟悉这个接口，它可以用 Lambda 表达式 `(E, E) -> int` 表示。此 Lambda 表达式或 `Comparator` 使用一种未指定且特定于实现的高效排序算法来比较 Stream 中的两个元素。以下表达式按标题对书籍排序：

```
books.stream().sorted((b1, b2) -> b1.title.compareTo(b2.title))
```

存在一种 `sorted` 操作的变体，它不接受任何参数。相反，它假设 Stream 中的元素实现了 `java.lang.Comparable` 接口，这意味着你可以对它们进行自然排序。以下将数字列表从小到大排序。结果列表为 -2, 0, 3, 5, 7, 8, 19。

```
[8, 3, 19, 5, 7, -2].stream().sorted()
```

## 限制 Stream 大小

你可以使用 `limit` 和 `substream` 操作限制 Stream 中的元素数量。使用 `limit` 在指定数量的元素后截断 Stream。`substream` 适用于分页，因为你可以指定起始索引（包含）和结束索引（不包含）。

```
books.stream().limit(10)
books.stream().substream(10, 20)
```

## 转换 Stream

使用 `map` 操作，你可以将 Stream 中的元素转换为其他类型的元素。`map` 操作接受一个期望一种类型元素并返回一个值的映射器（mapper）。给定一个 `Stream<S>`，`map` 一个参数为 S 的 Lambda 表达式。如果 Lambda 返回不同的类型 R，则 Stream 就是 `Stream<R>`。以下操作获取 `List<Book>`，获取 `Stream<Book>`，并将其转换为仅包含书籍标题的 `Stream<String>`：

```
books.stream().map(b -> b.title)
```

当然，你可以返回更复杂的类型。你可能有一个属性有限的不同类型。你可以创建一个隐式的 List 或 Map，返回 `Stream<List<Object>>` 或 `Stream<Map<Object, Object>>`：

```
books.stream().map(b -> [b.title, b.author])
books.stream().map(b -> {b.title, b.author})
```

## 使用终端操作

在过滤、排序或其他转换 Stream 后，你需要一个终端操作来获取结果。终端操作是触发 Stream 处理的操作。常见的终端操作包括 `forEach`、`reduce`、`count`、`anyMatch`、`allMatch`、`noneMatch`、`findFirst` 和 `findAny`。

终端操作可以返回单个值、集合或数组。例如，`count` 操作返回 Stream 中元素的数量，而 `findFirst` 返回 Stream 的第一个元素并将其封装在 Optional 中。

## 返回第一个值

你可以使用 `findFirst` 操作返回 Stream 中的第一个元素。对于 `Stream<E>`，它返回一个 `Optional<E>`，因为 Stream 可能是空的，这意味着没有元素可以返回。

```
${books.stream().filter(b -> b.author == "John F. Smith").findFirst()}
```

文件顶部的设置代码创建了一些用户并将它们添加到列表中。EL 表达式过滤列表以保留用户名数字为 1 的用户；按姓和名进行排序；从每个匹配的用户中选择用户名、名和姓；然后立即求值为一个 `List`。最后，该 `List` 被自动强制转换为 `String` 显示在屏幕上（使用 List 的排序方法）。注意排序后的 lambda 表达式中的分号（`;`）和赋值运算符（=`）——这允许你仅比较列表名称，将比较结果赋值给变量 (x)，然后测试 x 的值，如果名称不同则返回，如果名称相同则比较名。排序后的 lambda 表达式的主体被括号（ )）包围，是因为 lambda 运算符（`->`）的优先级高于赋值运算符和分号运算符。

你可以通过编译并运行应用程序，并在浏览器中访问 `http://localhost:8080/user-profile/collections.jsp` 来测试这一点。

> 注意：在第 4 章中，你探索了在 JSPs 中使用 Java 代码，并了解了不建议在 JSP 中使用 Java 的一些原因。表达式语言（EL）中引入 Stream API 为 JSP 作者提供了大量额外功能，可以显著地操作集合。如果你习惯了在 JSPs 中例行使用 Stream API，你可能会发现自己开始将业务逻辑放在表示层而不是 Java 代码中了。只有你才能决定这是否符合你的需求，但这是值得记住的一点。你将在书中其他任何地方看到 JSPs 中的 Stream API —— 从现在起，这类操作仅在 Java 代码中执行。

## 使用表达式语言替换 Java 代码

在本节中，你开始在正在进行的客户支持应用程序中替换 JSPs 中的部分 Java 代码。wrox.com 下载站点上的 Customer-Support-v4 项目包含了这些更改。你还不能替换所有的 Java 代码。为了这一点，我们需要下一章。通过更新你的 `/WEB-INF/jsp/base.jsp` 文件以包含用于 JSP 函数库的标签库：

```jsp
<%@ import="com.wrox.Ticket, com.wrox.Attachment" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="f" uri="http://java.sun.com/jsp/jstl/functions" %>
```

在本节中，你不需要对 Java 代码进行任何更改。所有的操作都将在 JSPs 中完成。`/WEB-INF/jsp/view` 下的 `ticketForm.jsp` 视图已经没有任何 Java 代码，所以你无法做任何改进。这一点。另一方面，`view.jsp` 有几处可以替换。该文件的新代码位于 Listing 6-1 中。

注意新代码的顶部有 ticket 和 ticket 的 `@variable` 提示，并且 ticket Java 变量已经没有移除。然而，ticket Java 变量并没有被移除，因为 EL 表达式无法替换 ticket 变量使用的所有地方——例如对它们进行迭代。新的 EL 表达式已**加粗**显示。

## 示例代码 6-1: viewTicket.jsp

```jsp
<!--@variable id="ticketId" type="java.lang.String"-->
<!--@variable id="ticketId" type="com.wrox.Ticket"-->

Ticket ticket = (Ticket)request.getAttribute("ticket");
<!DOCTYPE html>
<html>
<head>
    <title>Customer Support</title>
</head>
<body>
    <a href="<c:url value="login"/>">Logout</a>
    <h2>${ticket.subject}</h2>
    <c:item name="Customer" value="${ticket.customerName}"/><br />
    ${ticket.body}<br />

    <% if (ticket.getNumberOfAttachments() > 0) { %>
        Attachments: 
        <%
        int i = 0;
        for (Attachment a : ticket.getAttachments()) {
            if (i++ > 0) {
                out.print(", ");
                ><a href="<c:url value="tickets"/>
<c:param name="action" value="download" />
<c:param name="ticketId" value="${ticket.id}" />
<c:param name="attachment" value="<%= a.getName()}" />
</c:url>"><%= a.getName() %></a><%
            }
        }
        %><br />
    <% }}
    <a href="<c:url value="tickets"/>">Return to list tickets</a>
</body>
</html>
```

`/WEB-INF/jsp/view/sessions.jsp` 文件是另一个可以使用 EL 表达式的 JSP。你可以在 Listing 6-2 中找到该文件的新代码。JSP 部分唯一的更改是 `@variable` 类型和**加粗**的独立表达式。由于需要递归和对时间间隔进行格式化，此时大部分剩余 Java 代码可以被替换。

## 示例代码 6-2: sessions.jsp

```jsp
<% @elvariable id="numberOfSessions" type="java.lang.Integer" --%>
<%@ page import="java.util.Util" *%>
<%
    private static String toString(long timeInterval)
    {
        if(timeInterval < 1000)
            return "less than one second";
        if(timeInterval < 60)
            return (timeInterval / 1000) + " seconds";
        return "about " + (timeInterval / 60) + " minutes";
    }
%>
<%@SuppressWarnings("unchecked")
    List<HttpSession> sessions = (List<HttpSession>)request.getAttribute("sessionList");
%>
<!DOCTYPE html>
<html>
<head>
    <title>Customer Support</title>
</head>
<body>
    <a href="<c:url value="/login?logout"> />
    <h2>Sessions</h2>
    There are a total of ${numberOfSessions} active sessions in this application.<br /><br />
    <%
        long timestamp = System.currentTimeMillis();
        for (HttpSession aSession : sessions) 
        {
            out.print("* " + aSession.getId() + " = " +
                aSession.getAttribute("username"));
            if (aSession.getId().equals(session.getId()))
                out.print(" (you)");
            out.print("\n* - last active : " +
                toString(timestamp - aSession.getLastAccessedTime()));
            out.print("<br/><br/>");
        }
    %>
</body>
</html>
```

现在编译并运行客户支持应用程序，并在浏览器中访问 `http://localhost:8080/support/`。登录，创建几个工单，并查看工单。访问 `http://localhost:8080/sessions` 查看会话列表。所有运行方式都与第 5 章时一样，但现在 EL 处理了你的部分输出。

### 总结

在本章中，你学习了统一表达式语言（EL）的历史、基础 EL 语法以及 EL 表达式的用途。你探索了保留字、运算符、字面量、访问对象属性和方法、EL 函数以及 JSTL 函数库、静态字段和方法访问、枚举、lambda 表达式和收集器运算符。你介绍了四个不同的作用域和隐式作用域，并学习了 11 个隐式变量。你还学习了 Stream API 及其在 EL 3.0 中的引入。最后，你在第 3 章开始的客户支持应用程序用 EL 表达式替换了部分 Java 代码。

现在应该很清楚，尽管 EL 表达式可以替换大量的 Java 代码，但它们并不能完成替换 JSP 中所有 Java 代码所需的一切。例如，你无法在 EL 表达式中循环，也无法根据某些表达式的真假来执行代码块。你需要标准标签库（JSTL），你将在下一章中探索它。

### 介绍 JSP 标签与 JSTL

到目前为止，在 JSP 中使用 Java 来完成某些操作是绝对必要的。在你的 JSP 中添加 Java 的能力确实很方便，但请记住，你的 UI 开发者习惯于 HTML、JavaScript 和 CSS，他们很可能不会编写 Java 代码。你的目标是实现无 Java 的 JSP，但到目前为止你还没有实现这一点的工具。表达式语言（Expression Language）在替换某些代码方面很有帮助，你在上一章中已经体验过了这一点——即你仍然需要在使用 EL 时依赖 Java 代码。事实上，你还没有充分利用 EL 的威力，因为你仍然受限于必须使用 Java 代码的限制。

在之前的章节中，你已经通过 `<url>` 和 `<c:redirect>` 标签看到了了 JSP 标签和 JSTL 的小部分示例。这是无法避免的，因为替代方案对你来说太不友了，无法直接展示给你。这些标签只是被带提到，关于它们本身以及 JSTL 的部分被留到了本章进行介绍。当你在上一章探索 JSTL 函数库（使用 `fn` 命名空间）时，你也看到了部分 JSTL，但这是必要的，因为它是一个函数而不是库，并且专门用于 EL 表达式。你不能在 EL 表达式之外使用 JSTL 函数库。在本章中，你将详细学习 JSP 标签和 JSTL 的概念，最后你将用简洁的 JSP 标签和 EL 表达式替换掉 JSP 中难看的代码。

# 使用标签

JSP 标签是 Java Pages 技术的一种语法，看起来与任何普通的 HTML 或 XML 标签一样。JSP 标签也根据其功能被称为“动作”（actions）。JSP 会执行某些动作，例如创建或限制输出。JSP 和 JSTL 规范专门指这些动作，但它们称之为标签（tags）。因为它们超出了任何标准 HTML 指定标签的范围，JSP 标签需要一个 XML 命名空间才能被正确引用。将 XML 编写代码是一项繁琐且不常规的任务，正如你在第 4 章对 JSP 文档 (.jspx) 的简要介绍中所看到的 true。特别是对于经验丰富的程序员来说，遵循严格的 XML 文档语法有时是很困难的。JSP 标签语法包含了一些快捷方式，使编写 JSP 更加容易。这些快捷方式中的第一个是 taglib 指令，你你在第 4 章中探索过它，并从那时起一直在使用。

```xml
<taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"/>

<jsp:root xmlns="http://www.w3.org/1999/xhtml" version="2.0"
     xmlns:jsp="http://java.sun.com/jsp/Page"
     xmlns:c="http://java.sun.com/jsp/jstl/core"
     xmlns:fn="http://java.sun.com/jsp/jstl/functions">
```

使用该指令是在在 XML 文档中使用 XMLNS 指令引用 XML 命名空间的替代方案：

相反，你所在的 Web 容器中的 JSP 引擎理解特殊的 JSP 语法并知道如何解析它，而且（如今）所有主要的 Java IDE 都理解 JSP 语法，并向你提示 JSP 中的语法错误和其他问题。



# JSP 标签库指令与核心标签库

## taglib 指令

`taglib` 指令（或 XML 命名空间）中的 `prefix` 属性代表在整个 JSP 页面中引用标签库时使用的命名空间。该标签库的标签库描述符文件（TLD）建议了该前缀，但在 `taglib` 指令中使用 `prefix` 属性进行了声明。因此，前缀可以是你在 `prefix` 属性中设置的任何值，但通常开发者会倾向于使用 TLD 中建议的前缀，以防止与其他开发者产生混淆。

`uri` 属性指示为标签库定义的 URI。JSP 解析器通过这种方式定位引用标签库的相应 TLD。它会寻找包含相同 URI 的 TLD。

> **注意**：`Uri` 是一个命名规范，而不是 TLD 的实际位置（也不是真实的 URL）。事实上，在大多数情况下，在浏览器中导航到该 URI 可能会导致 404 Not Found 或类似的错误。你使用的 TLD 以某种方式包含在你的应用程序中，无论是在容器中、在应用程序的 JAR 文件中，还是在应用程序的 `WEB-INF` 目录中。URI 仅仅是一种用于唯一标识 TLD 的技术，以便你使用的标签能够正确与相应的 TLD 关联。

当 JSP 解析器遇到 `taglib` 指令时，它会使用 URI 通过在多个位置查找该标签库的 TLD。这些位置在 JSP 规范中的指定如下，按优先级从高到低排序为：

1. 如果解析器是符合 Java EE 标准的客户端，解析器将查找任何作为 Java EE 规范一部分的匹配 TLD 文件，包括 JSP 标签库、Java 标准标签库和 JavaServer Faces 库。
2. 它将检查部署描述符中 `<jsp-config>` 部分内的 `<taglib>` 声明。
3. 如果解析器仍未找到匹配的 TLD 文件，它将检查放在你的 `/WEB-INF/library` 中的任何 JAR 文件的 `META-INF` 目录下的任何 TLD 文件，或者放在你的应用程序 `/WEB-INF` 或 `/WEB-INF` 任何子目录下的任何 TLD 文件（递归查找）。
4. 最后，解析器将检查作为 Web 容器或应用程序服务器部分的任何其他 TLD 文件。（这些通常是 Web 容器自定义的，使用它们将使你的应用程序与该容器绑定，并使其变得不可移植。）

除非你引用的 TLD 已经包含，或者你需要覆盖前缀，否则通常需要显式的 `<taglib>` 声明。

```xml
<jsp-config>
  <taglib>
    <uri>http://example.org/jsp/custom</uri>
    <tld-location>custom.tld</tld-location>
  </taglib>
</jsp-config>
```

在此示例中，`<uri>http://example.org/jsp/custom</uri>` 将与 `taglib` 属性进行比较。因为该前缀不在 Web 应用程序中。

## 介绍 JSP 标签与 JSTL

规范，而 Web 容器实现了 Servlet 和 JSP 规范——可能还有 Web 容器创建者想到的其他规范。大多数 Web 容器还实现了 EL 规范，因为它曾经是 JSP 规范的一部分，并且仍然与 JSP 规范紧密相连。所有的 Web 容器都支持在 JSP 中使用标签库，因为这种支持是 JSP 规范的一部分。然而，某些 Web 容器并没有实现 Java 标准标签库 (JSTL) 规范，因为 JSTL 中的特定标签库很容易从标签的通用代码中解耦。Tomcat 在历史上一直是这些 Web 容器之一，直到今天它还没有实现 JSTL。但是，这并不意味着在向 Tomcat 部署时无法使用 JSP 应用程序！

> **注意**：Tomcat 实现了 Servlet API、JSP、表达式语言（Expression Language）和 WebSocket API 实现。其他 Web 容器可能实现更多或更少的规范，这可能会随版本变化。请务必查阅你特定 Web 容器的文档以确定其支持的内容。

回想第 4 章，你向示例代码中添加了三个 Maven 依赖。其中一个是 JSP API，它只是能让你在 IDE 中编译 JSP 特性。另一个依赖是 Servlet API。这些依赖具有 "provided" 范围，是因为 Tomcat 已经包含了 JSP API，而你不需要在部署的应用程序中包含它。你添加的其他依赖是 JSTL API（JSTL 的接口、抽象类和标签）以及由 GlassFish 提供的 JSTL 实现（JSTL 的 TLD、具体类以及接口的实现）。如果 Tomcat 提供了 JSTL 实现，你仍然需要 JSTL Maven 依赖，但它们将具有 "compile" 范围，以便你将它们与应用程序一起部署。这使得尽管 Tomcat 缺乏 JSTL 实现，你仍可以在应用程序中使用 JSTL。

Java 标准标签库规范中共有五个标签库：

- 核心库 Core (c)
- 格式化 Formatting (fmt)
- 函数 Functions (fn)
- SQL (xql)
- XML (x)

你已经在第 6 章探索表达式语言时学习过函数库了。本章的其余部分将致力于探索其他四个库，并会触及你如何使用 XML 和 SQL 库。作为参考，你可以在 `http://docs.oracle.com/javaee/5/jst/1.1/docs/tlds/` 查看 Java EE 5 的 JSTL 1.1 的 TLD 文档。遗憾的是，Java EE 6 的 JSTL 1.2 没有公开文档，但这些版本之间的变化非常微其道。没有添加新标签——只是对规范进行了说明。Java EE 7 中没有新的 JSTL 版本。

## 使用标签库（C 命名空间）

核心标签（Core tag）正如其名，包含了你替换 JSP 中 Java 代码所需要的几乎所有的核心功能。这包括用于条件编程、循环和迭代以及输出内容的工具。当你在本章末尾编写“客户支持”应用程序时，你会发现每一行 Java 代码都被用核心库中的某个标签所取代了。你已经见过了核心库的几个标签，所以你应该熟悉它的 `taglib` 指令：

```jsp
<taglib prefix="c" uri="java.sun.com/jsp/jstl/core" />
```

核心库中有许多标签，没有哪个是不重要的。其中某些标签比其他的更常用，你将在稍后的内容中学习它们。

### `<c:out>`

`<c:out>` 标签可能是核心库中最常用的（有时也是最容易被误解的）标签。它的目的是辅助向你的 JSP 输出内容。你可能会立即疑惑，这与使用 EL 表达式输出内容有什么区别。也许更让人困惑的是 `<c:out>` 几乎总是与一个或多个 EL 表达式一起使用：

```jsp
<c:out value="${someVariable}" />
```

尽管在这种情况下 `<c:out>` 可能等同于编写 `${someVariable}`，但它们存在差异。首先，在这种情况下 `<c:out>` 实际上等同于 `${escapeXml}`。这是因为 `<c:out>` 会转义 XML 字符，如 `<`、`>`、`'`、`"` 和 `&`。你可以通过将 `escapeXml` 属性设置为 `false` 来禁用此行为：

```jsp
<c:out value="${someVariable}" escapeXml="false" />
```

在大多数情况下，你永远不想这样做。对预留 XML 字符的转义有助于保护你的网站免受跨站脚本和注入攻击，并防止意外字符破坏网站的功能。还有一个默认属性 `default`，它在属性中的值为 `null` 时会指定一个默认值。

```jsp
<c:out value="${someVariable}" default="Value not specified." />
```

默认属性也可以包含一个 EL 表达式。（事实上，任何标签中的任何属性都可以包含。）

```jsp
<c:out value="${someVariable}" default="${someOtherValue}" />
```

除了使用默认属性，你还可以使用嵌套标签来实现相同的效果。这允许你使用 HTML 标签、JavaScript 和其他 JSP 标签来生成默认值。

```jsp
<c:out value="${someVariable}"><default>value</default></c:out>
```

最后，注意 `value` 属性是如何工作的。通常情况下，EL 表达式指定的值会被转换为字符串，并将该字符串写入输出。然而，如果 EL 表达式返回一个 `java.io.Reader`，则会读取该读取的内容并写入输出。

### `<c:url>`

`<c:url>` 标签可以正确对 URL 进行编码，并在必要时对其进行重写。考虑你的应用程序部署在 `http://www.example.org/forums/`，你在 HTML 中放置了以下链接：

```html
<a href="/view.jsp?formId=12">Product Forum</a>
```

当用户点击该链接时，他们会被带到 `http://www.example.org/view.jsp?formId=12`。这可能不是相对于你应用程序的根路径。你可以轻松地将链接改为 `/forums/view.jsp?formId=12`，但如果你想要一个任何人都可以下载并在其网站上使用的应用程序，他们不知道会将应用程序部署在 `/forums`、`discussion`、`/boards` 甚至是 `/`。这就是 `<c:url>` 标签大显异彩的地方。

```html
<a href="<c:url value="/view.jsp">
  <c:param name="formId" value="12" />
</c:url>">Product Forum</a>
```

注意 `<c:url>` 实际上嵌入 HTML 标签的属性中。这是完全合法且常见的。`<c:url>` 标签在 JSP 引擎渲染你的 JSP 时会被解析并替换，它将特殊 JSP 语法以外的所有内容视为文本。如果你的应用程序部署在 `/forums/`，生成的链接将指向 `/forums/view.jsp?formId=12`。如果部署在 `/boards/`，它将是 `/boards/view.jsp?formId=12`。这省去了担心应用程序部署在哪个上下文路径的麻烦。当然，可能你真的想让 URL 指向网站的根目录。或者你可能需要它指向另一个部署的应用程序。这通过向标签添加 `context` 属性也可以轻松实现。

```xml
<url value="/index.html" context="/" />
<url value="/item.jsp?itemId=15" context="/store" />
```

第一个标签生成一个根上下文的 URL，`/index.html`。第二个标签生成一个指向 `/store` 上下文的 URL，`/store/item.jsp?itemId=15`。

默认情况下，`<url>` 标签会将生成的 URL 输出到响应中。如果你有一个 URL 需要在页面上被多次使用，可以将其保存到请求变量中而不是：

```jsp
<url value="index.jsp" var="homeUrl" />
<url value="index.jsp" var="homeUrl" scope="request" />
```

`var` 属性指定了用于保存生成 URL 的 EL 变量名称。默认情况下，它被保存到页面作用域（page scope）中（记住四个 EL 作用域：page、request、session 和 application）。如果由于某些原因你需要将其保存到不同的作用域，可以使用 `scope` 属性来指定。注意，`var` 的值是一个普通字符串，而不是 EL 表达式。虽然 EL 表达式可以工作，但那样做是没意义的。你是在告诉 JSP 你在作用域中创建的属性，因此它应该始终是一个普通字符串。

上一个示例中的第一个标签在页面作用域中创建了 `homeUrl` 属性。第二个标签在请求作用域中创建该属性。无论你将 `homeUrl` 保存到哪个作用域，你都可以在请求的后续（在此示例中）引用该 URL：`${homeUrl}`。

```html
<a href="${homeUrl}">首页</a>
```

为了获得最大的安全性、灵活性和移植性，建议 JSP 中所有的 URL 都使用 `<c:url>` 进行编码，除非该 URL 是没有查询参数的内部 URL。即使如此，即使 `<c:url>` 包含需要编码的特殊字符，使用 `<c:url>` 仍然是安全且鼓励的。

### `<c:if>`

显然，`<c:if>` 标签是一个用于控制渲染内容的条件标签。使用 `<c:if>` 标签非常简单：

```jsp
<c:if test="${something == somethingElse}">
  仅当为真时执行
</c:if>
```

`test` 属性指定了一个条件，该条件必须为真，`<c:if>` 标签内的嵌套内容才会被求值。如果为假，则内部所有内容都将被忽略。如果你有一个复杂的条件，只想显示一次但在页面上多次使用，可以使用 `var` 属性将其保存到变量中（可选地指定不同的作用域）：

```jsp
<c:if test="${someComplexExpressionIsTrue}" var="itWasTrue" />
<c:if test="${itWasTrue}">
  执行某些操作
</c:if>
<c:if test="${itWasTrue}">
  执行另一些操作
</c:if>
```



你可能会立刻问是否有一个与 `<c:if>` 配合的 `<c:else>` 标签。`<c:if>` 设计用于简单的、全有或全无（all-or-nothing）的条件块。对于更复杂的 `else-if/else` 逻辑，你需要比 `<c:if>` 更强大的工具。

## `<c:choose>`, `<c:when>`, and `<c:otherwise>`

`<c:choose>`、`<c:when>` 和 `<c:otherwise>` 标签是 `<c:if>` 标签更强大的对应物，提供了更复杂的 if/else-if 逻辑。`<c:choose>` 标签充当框架，指示条件块的开始和结束。`<c:when>` 和 `<c:otherwise>` 嵌套在内部。`<c:choose>` 必须至少有一个且可以无限多个 `<c:when>` 标签，且所有的 `<c:when>` 标签必须在 `<c:otherwise>` 标签之前。`<c:when>` 有一个属性 `test`，指示了 `<c:when>` 内部内容必须求真的条件。任何内容或其他 JSP 标签都可以嵌套在 `<c:when>` 中。只有一个 `<c:when>` 的内容会被求值：即第一个为真的 `<c:when>`。在某个 `<c:when>` 被求值为真后，`<c:choose>` 会短路到末尾。

最多可以有一个（可选）`<c:otherwise>` 标签，它必须是 `<c:choose>` 内部的最后一个标签。它没有属性，可以包含任何嵌套内容，并且仅当所有 `<c:when>` 标签都不为真时，它的内容才会被求值。

```jsp
<c:choose>
  <c:when test="${something}">
    if
  </c:when>
  <c:when test="${somethingElse}">
    else if
  </c:when>
  <c:otherwise>
    else
  </c:otherwise>
</c:choose>
```

从前面的代码中你可以看到第一个 `<c:when>` 类似于 Java 中的初始 `if`。它首先被求值，如果为真，其他所有内容都将被执行并忽略。第二个 `<c:when>` 以及所有其他 `<c:when>` 类似于 `else if`。只有当它们之前的 `<c:when>` 求值为假时，它们才会被测试。`<c:otherwise>` 标签类似于最后的 `else`，当所有条件都失败时总是会被求值。然而，`<c:choose>` 可以只有一个 `<c:when>` 而没有其他内容：

```jsp
<c:choose>
  <c:when test="${something}">
    if
  </c:when>
</c:choose>
```

## `<c:forEach>`

`<c:forEach>` 标签用于迭代，并根据其嵌套体重复某些固定次数。`<c:forEach>` 标签等同于下文 Java 所示的 for-each 循环：

```java
for (int i = 0; i < 100; i++) {
    out.println(i);
}
```

`<c:forEach>` 标签等同于：

```jsp
<c:forEach var="i" begin="0" end="100">
    ${i} <br />
</c:forEach>
```

在这种情况下，`<c:forEach>` 迭代 0 到 100。`step` 属性决定步进，例如每隔 3 次迭代一次：

```jsp
<c:forEach var="i" begin="0" end="100" step="3">
    ${i} <br />
</c:forEach>
```

在这种情况下，`<c:forEach>` 迭代 0 到 100。`step` 属性决定步进，例如：

```java
for (User user : users) {
    out.println(user.getLastName() + ", " + user.getFirstName());
}
```

最后，使用 `<c:forEach>` 的 `varStatus` 属性创建一个包含当前状态的变量：

```jsp
<c:forEach items="${users}" var="user" varStatus="status">
    ${status.begin}
    ${status.end}
    ${status.step}
    ${status.count}
    ${status.current}
    ${status.index}
    ${status.first}
    ${status.last}
</c:forEach>
```

在此示例中，`varStatus` 变量封装了当前迭代。该状态对象（`java.servlet.jsp.jstl.core.LoopStatus` 实例）属性如下：

- **begin**: 标签的 `begin` 属性值。
- **end**: 标签的 `end` 属性值。
- **step**: 标签的 `step` 属性值。
- **index**: 返回当前索引。该值每次迭代增加 `step` 次。
- **count**: 返回到目前为止迭代的次数（包括当前迭代）。该值每次迭代增加 1，即使 `step` 大于 1 也是如此。它从第一次迭代开始为 1，且永远不会等于 `index`。
- **current**: 包含当前项。如果你也使用 `var` 将项导出为变量，则与它等同。在上一个示例中，`status.current` 等于 `user`。
- **first**: 如果当前迭代是第一次迭代（`status.count` 等于 1），则为 `true`。否则为 `false`。
- **last**: 如果当前迭代是最后一次迭代，则为 `true`。否则为 `false`。

## `<c:Tokens>`

`<c:Tokens>` 标签与 `<c:forEach>` 标签几乎相同。它包含许多属性（`var`、`varStatus`、`begin`、`end` 和 `step`），这些属性的行为与遍历集合的 for-each 循环中的属性相同。主要区别在于 `items` 属性接受的是字符串而不是集合，并且额外的 `delim` 属性指定一个或多个字符，用于将字符串拆分为标记（tokens）。然后，标签遍历这些标记。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_222_0.png)

# 列表 7-2 (续)

```xml
<choose>
  <when test="${fn.length(contacts) == 0}">
    <i>There are no contacts in the address book.</i>
  </when>
  <otherwise>
    <foreach items="${contacts}" var="contact">
      <b>
        <c:out value="${contact.lastName}, ${contact.firstName}" />
        <br />
        <c:out value="${contact.address}" /><br />
        <c:out value="${contact.phoneNumber}" /><br />
        <if test="${contact.birthday != null}">
        Birthday: ${contact.birthday}<br />
        Created: ${contact.dateCreated}<br />
        </if>
      </b>
    </foreach>
  </otherwise>
</choose>
</body>
</html>
```

编译并部署你的项目，然后导航到 `http://localhost:8080/address-book/list`。你应该能看到显示“地址簿中没有联系人”的提示，这意味着 `<when>` 测试的评估结果为真。现在从 URL 中移除空参数，你应该能看到如图 7-1 所示的界面。大部分情况下这看起来还可以，但日期的格式并不友好，而且不支持其他语言。在图中

![](img/9c2d45f6d547f72cb870b3a991f62ef6_227_0.png)

图 7-1

## 使用国际化和格式标签库 (FMT 命名空间)

如果你打算创建部署在 Web 上并针对大型国际用户的 Java 应用程序，你最终需要将应用程序针对世界特定地区进行本地化。这是通过国际化（通常缩写为 i18n）实现的，它是设计应用程序使其能够适应不同的地区、语言和文化，而无需为新地区重新设计或编写应用程序。

应用程序完成国际化后，你可以通过添加对目标地区、语言和文化的支持，利用国际化框架来实现程序的本地化。本地化（通常缩写为 L10n）和国际化这两个术语经常被混淆，考虑到它们相互关联，这是可以理解的。记住它们区别的一种方法是：“首先通过架构进行国际化，然后通过翻译进行本地化。”

## 国际化和本地化组件

国际化和本地化包含三个组件：

- 文本必须经过翻译，以便能够说和理解其他语言的用户可以使用你的应用程序。
- 日期、时间以及数字（包括货币和百分比）必须针对不同的区域进行正确的格式化。例如，美国的 12,934.52 在法国实际上是 12 934,52，在德国则是 12,934,52。
- 价格必须是可以转换的，以便能够显示当地货币，以匹配客户所在的世界地区。

通常会省略货币转换——这有其正当。向用户显示不同货币的价格可能极具挑战性、不准确且过时，而今天大多数金融机构在结账时提供将货币转换为用户本地货币的方法。在许多情况下，只需显示美元价格就足够了。由于该主题的复杂性，本书将不涵盖转换内容。

JSTL 提供了一个支持你的应用程序中国际化和本地化工作的库：国际化和格式库，前缀为 `fmt`。在本节中，你将学习如何使用和配置格式库来使你的应用程序国际化，以便对其进行本地化。你经常会看到 locale（区域）一词，它是代表特定地区、文化或政治区域的标识符。Locale 始终包含 ISO 639-1 指定的双字母语言代码。你可以点击 `http://www.loc.com/standards/iso639-2/code_list.php` 查看所有代码列表。该页面显示 2 位 ISO 639-1 代码和 3 位 ISO 639-2 代码。在本书中你将只使用 2 位代码。

对于语言代码过于模糊的语言（例如，墨西哥西班牙语与西班牙西班牙语略不同），locale 可以可选地包含 ISO 3166-1 指定的双字母国家代码，你可以点击 `http://www.iso.org/iso/home/standards/country_codes/iso-3166-1_decoding_table.htm` 查看。

在 locale 中，语言代码始终在前面。如果指定了国家代码，它紧随其后，并用下划线分隔语言和国家代码。偶尔，locale 还会与变体（variant）关联，变体不包含在 locale 代码中。你不需要担心变体，但关于这点的更多信息，你应该查看 `java.util.Locale` 类的 API 文档。Locale 用于 Java 和 JSTL 中表示区域。

国际化和格式库分为两个大类：

- 支持国际化的标签（i18n 标签）
- 支持日期、时间和格式化的标签（格式化标签）

i18n 标签具有资源包（resource bundles）的概念，资源包定义了特定区域的对象。资源包由对应于包中条目的键组成，并使用开发者选择的任意基名定义，在基名后附加语言代码以形成完整的资源名称。一个键通常在每个资源包中都有目，对应每个支持的语言和国家。在本节中，你将首先学习所有的 i18n 标签。

## `<fmt:setLocale>`

`<fmt:setLocale>` 标签用于设置区域（locale），以便解析用于 i18n 格式化的资源包消息。`value` 属性指定区域，其值可以是字符串代码（如 `en_US`）或指向 `Locale` 实例的 EL 表达式。如果 `value` 是区域代码，还可以指定 `variant` 属性来指示该区域的变体。该区域将被保存到名为 `javax.servlet.jsp.jstl.fmt.locale` 的 EL 变量中，并成为指定范围（默认为页面范围 `page`）内的默认区域。如果你使用此标签，应该在执行任何格式化操作之前使用它，以确保使用正确的区域。通常情况下，你不需要 `<fmt:setLocale>` 标签。国际化应用程序通常具有某种机制（例如从用户账户加载保存的区域），在请求到达 JSP 之前自动设置好区域。你将在第 15 章中了解到。

```jsp
<fmt:setLocale value="en_US" />
<fmt:setLocale value="${locale}" />
```

## `<fmt:bundle>` and `<fmt:setBundle>`



- 如果指定了 `<fmt:message>` 标签的 `bundle` 属性，它将优先使用该值，而不是其他可能适用于该标签的包。

- 如果 `<fmt:message>` 标签嵌套在 `<fmt:bundle>` 标签中，它将使用该包（除非被 `<fmt:message>` 上的 `bundle` 属性覆盖）。

- 如果使用初始化参数或 EL 变量名 `javax.servlet.jsp.jstl.fmt.localizationContext` 指定了默认本地化上下文，则将使用该包。我们将在本节稍后的部分学习如何这样做。

虽然 `<fmt:bundle>` 标签创建了一个临时的本地化上下文，仅影响其内部的嵌套标签，但 `<fmt:setBundle>` 将本地化上下文导出到一个 EL 变量中，`<fmt:message>` 标签之后可以通过在 `bundle` 属性中引用该包变量来使用它。导出的变量由 `var` 属性指定，并具有指定的范围 `scope`（默认为页面范围 `page`）。如果未指定 `var`，本地化上下文将保存到名为 `javax.servlet.jsp.jstl.fmt.localizationContext` 的 EL 变量中，并成为该范围内的默认本地化上下文。以下示例演示了包定义的用法。

```
<fmt:setBundle basename="Titles" var="errorsBundle" />
<fmt:message key="titles.homepage" bundle="${errorsBundle}" />
<fmt:message key="others.greeting" />
</fmt:bundle>
```

## 使用国际化和格式化标签库 (FMT 命名空间)

`basename` 属性指示资源包的基础名称——即在附加区域代码之前的资源包文件名。输出 `titles.homepage` 消息的 `<fmt:message>` 标签将使用其内部嵌套的 `<fmt:bundle>` 标签所定义的 Titles 包，而 `errors.notFound` 消息将解析 `<fmt:setBundle>` 标签中定义的 Errors 包。`others.greeting` 消息将使用默认本地化上下文进行解析。

与 `<fmt:setLocale>` 一样，你很少（如果有时）使用 `<fmt:bundle>` 和 `<fmt:setBundle>` 标签。有一些工具可以使这变得更容易，我们将在本节稍后讨论，并在第 15 章进行深入讨论。

## `<fmt:requestEncoding>`

`<fmt:requestEncoding>` 标签使用 `var` 属性设置当前请求的字符编码，以便请求参数能够使用与给定区域相应的字符编码进行正确解码。你不需要使用此标签，在书中也没有看到它被使用，原因有二：

- 你的 Java Servlet 在 `<fmt:requestEncoding>` 标签有机会更改请求字符编码之前就已经处理了参数。

- 所有现代浏览器对编码不同 ISO-8859-1 的请求都包含 Content-Type 头部。它们还会接收来自网站最后一次响应返回的字符编码。这消除了手动设置请求字符编码的需要。

这是一个遗留标签，源于一个请求属性编码很少已知且必须猜测的领域。开发者可能需要根据所选语言猜测编码。今天，由于现代浏览器的行为，这种需求已经消失了。

## `<fmt:timeZone>` and `<fmt:setTimeZone>`

处理日期和时间的格式化标签需要一个区域和一个时区才能正常工作。区域来自本地化上下文（你可以在稍早之前对 `<fmt:bundle>` 和 `<fmt:setBundle>` 的讨论中读到），并由其中定义的相同规则决定。然而，时区时间虽然与区域中指定的区域或语言相关，但它并不严格与区域挂钩。例如，一个来自美国的人可能会访问东京，并希望使用英语运行你的应用程序，使用标准的美国日期和时间格式，同时看到东京时间。由于许多原因，Java 和 JSTL 中都指定了其他时区和区域。需要时区的格式化标签按照以下优先级策略解析时间使用：

- 如果日期和时间格式化标签的 `timeZone` 属性指定了值，则优先使用该值，而不是其他所有时间。

- 如果标签嵌套在 `<fmt:timeZone>` 标签内部，则使用 `<fmt:timeZone>` 指定时区。

- 如果设置了名为 `javax.servlet.jsp.jstl.fmt.timeZone` 的初始化参数或 EL 变量，则使用该时区。

- 否则，使用容器提供的时区（通常是 JVM 时间，即底层操作系统的时区）。

`<fmt:timeZone>` 标签是 `<fmt:bundle>` 操作的时区对应物。它创建了一个临时的时区范围，嵌套标签在该范围内使用它。它唯一的属性是 `value`，它可以是一个求值为 `java.util.TimeZone` 的 EL 表达式，也可以是匹配 IANA 数据库中任何合法时区的字符串。你可以在 IANA 网站或 `TimeZone` 的 API 文档中学习这些 ID。如果 `value` 为空或空，则假设为 GMT 时间。

`<fmt:setTimeZone>` 标签类似于 `<fmt:setBundle>` 标签，并将指定的时间导出到一个范围。`var` 属性指定 EL 变量的名称，将时间导出到 `var` 指定的范围（默认为页面范围 `page`）。如果省略了 `var`，时区将保存到 EL 变量 `servlet.jsp.jstl.fmt.timeZone` 中，并成为该范围的默认时区。

```
<fmt:setTimeZone value="America/Chicago" var="timeZoneCst" />
```

```
<fmt:setTimeZone value="${timeZone}">
tags here use some timeZone
</fmt:setTimeZone>
```

```
<fmt:setTimeZone value="${timeZoneCst}">
tags here use America/Chicago
</fmt:setTimeZone>
```

## `<fmt:formatDate>` and `<fmt:parseDate>`

`<fmt:formatDate>` 标签正如其名，它使用默认或指定的区域以及日期或指定的时区来格式化指定的日期（和时间）。格式化后的日期要么内联输出，要么保存到指定范围的变量 `var` 中。`timeZone` 属性指定用于格式化日期的时区或字符串 ID。日期使用 `value` 属性指定。目前，`value` 必须是一个求值为 `java.util.Date` 实例的 EL 表达式；不支持 `java.util.Calendar` 或 Java 8 日期 API。在接下来，你可以使用 JSTL 创建支持这些新值的自定义标签库。JSTL 的未来版本可能会支持这些类型。

格式化日期如何结合区域以及 `type`、`dateStyle` 和 `pattern` 属性确定。`type` 应该是 "date"、"time" 或 "both" 之一，指示输出日期、仅时间还是日期后接时间。`dateStyle` 和 `timeStyle` 属性都遵循 `DateFormat` API 文档中定义的语义，并且必须是“default”（方便地，即默认值）、“short”、“medium”、“long”或“full”之一。这些属性指定了日期和时间相对于其区域如何格式化。如果你需要，还可以指定自定义

## 使用国际化和格式化标签库 (FMT 命名空间)

根据 `java.text.SimpleDateFormat` 的规则，使用 `pattern` 属性进行。在这种情况下，`dateStyle` 和 `timeStyle` 属性会被忽略。这样做也会忽略随区域（locale）自带的样式（尽管月份仍根据语言进行本地化），尽可能避免使用 `pattern`。

```xml
<fmt:formatDate value="${someDate}" type="both" dateStyle="long"
timeStyle="long" />

<fmt:formatDate value="${someDate}" type="date" dateStyle="short"
var="formattedDate" timeZone="${differentTimeZone}" />
```

假设日期为 America/Chicago 默认时区的 2013 年 10 月 3 日 15:22:33，第一个示例对于美国英语区域设置（locale）输出 "October 3, 2013 3:22:33 PM CDT"，对于法语区域设置输出 "3 October 2013 15:22:33 CDT"。第二个示例仅在 `${differentTimeZone}` 指定的时区内以较短的格式格式化日期，并将其保存到 `formattedDate`。对于美国英语，`formattedDate` 的值为 "10/13"，对于法语区域为 "03/10"。

如果 `<fmt:parseDate>` 听起来像是 `<fmt:formatDate>` 的相反，那么你是完全正确的。`<fmt:parseDate>` 具有与 `<fmt:formatDate>` 相同的属性和规则，但它反转了该过程。它解析类似于 `<fmt:formatDate>` 输出的格式化字符串并将其解析为对象（Object）。你通常还会添加此变量以使用 `var` 属性，否则它并不实用。你可以不使用 `value` 属性指定要解析的日期，而是通过标签体内容来指定。

## `<fmt:formatNumber>` 和 `<fmt:parseNumber>`

`<fmt:formatNumber>` 是一个极其强大的工具，能够对数字（整数型和小数）、货币和百分比进行格式化。它有很多属性，但并非全部如此。首先，要明确，和你见过的其他属性一样，`var` 范围属性的行为正如你所习惯的。如果省略了 `var`，格式化后的数字将内联在 JSP 中。现在需要格式化一个货币，假设数字是一个范围变量，值为 12349.15823。

```xml
<fmt:formatNumber type="currency" value="${number}" />
```

```xml
<fmt:formatNumber type="currency" value="${number}" currencyCode="USD" />
```

该输出在美国英语区域仍为 "$12,349.16"，但在西班牙语区域的输出为 "12,349.16 USD"，这是正确的。`currencySymbol` 属性也可用于覆盖所使用的货币符号，但最好保持原样。该标签可以根据你指定的货币代码正确确定货币符号。如果 `type` 不是 "currency"，则这两个属性都会被忽略。

另一个有效值（也是默认值）是 "number"。它将数字格式化为普通数字。默认情况下，它根据区域（locale）将数字计数为三位一组并分组。

```xml
<fmt:formatNumber type="number" value="${number}" />
```

这在美国英语区域输出 12,349,158，在西班牙语区域输出 "12.349,158"。你使用 `maxFractionDigits` 属性通过指定小数点符后的位数来增加或减少舍入精度，并使用 `maxIntegerDigits` 指定小数点符前的最大位数（永远不要使用 `maxIntegerDigits`，因为位数可能会用尽。例如，如果你将其设置为 3，数字 12345 将变成 345.）。`minFractionDigits` 用于在数字的小数部分末尾补零，`minIntegerDigits` 用于在数字的整数部分开头补零。如果为 `false`，示例中的输出将是 "12,349.158" 和 "12.349,158." 这五个属性在三种数字类型中均被接受。

第三种也是最后的有效 `type` 值是 "percent"，用于将数字格式化为百分比。

```xml
<fmt:formatNumber type="percent" value="${0.8572}" />
```

该输出在美国英语区域和西班牙语区域的输出均为 "86%"，因为默认策略是舍入为整数。如果 `maxFractionDigits` 属性设置为 2，则值将为 "85.72" 和 "85,72"。注意，数字会自动为你乘以 100，以便转换为百分比。`maxFractionDigits` 的默认值取决于货币的区域，你可以通过该属性指定自定义模式，根据 `java.text.DecimalFormat` 规则格式化数字。你通常应该避免使用此属性。

像 `<fmt:parseDate>` 一样，`<fmt:parseNumber>` 反转了 `<fmt:formatNumber>` 的过程。它没有 `maxFractionDigits`、`maxIntegerDigits`、`minFractionDigits`、`minIntegerDigits` 或 `groupingUsed` 属性，因为解析数字不需要这些信息。它包含了额外的 `integerOnly`（指定是否忽略数字的小数部分，默认为 false）和 `parseLocale`（指定解析数字时使用的区域，如果不是默认区域）。像 `<fmt:parseDate>` 一样，你可以在体内容中指定数字。

## 使用 i18n 和格式化库

为了探索 i18n 和格式化库，你要做的第一工作是在部署描述（deployment descriptor）中添加一个新的初始化参数。

```xml
<context-param>
  <param-name>javax.servlet.fmt.localizationContext</param-name>
  <param-value>AddressBook-messages</param-value>
</context-param>
```

这建立了一个可以加载消息的资源包。容器在哪里查找此包？它查找 `AddressBook-messages_[language]_[country].properties`。如果找不到，它会查找回退区域（英语）。为了满足这一点，在 `source/resources` 目录下创建一个 `AddressBook-messages_en_US.properties`。

```properties
title.border=Address Book
title.page=Address Book Contacts
message.noContacts=There are no contacts in the address book.
label.birthday=Birthday
label.creationDate=Created
```

你还需要该文件的翻译版本以便测试切换，因此在相同目录下创建一个 `AddressBook-messages_fr_FR.properties`。

```properties
title.border=Adresses
title.page=Contacts du Carnet d'Adresses
message.noContacts=Il n'y a pas de contacts dans le carnet d'adresses.
label.birthday=Anniversaire
label.creationDate=Etabli
```

你需要轻松更改页面显示的语言，因此在 `ListServlet` 顶部添加以下代码。`Config` 类从 `javax.servlet.jstl.core.Config` 导入。

```java
String language = request.getParameter("language");
if ("french".equalsIgnoreCase(language)) {
  Config.set(request, FMT_LOCALE, Locale.FRANCE);
}
```

由于 `<fmt:formatDate>` 标签不支持 Java 8 日期时间 API，你需要能够访问旧式 `Date` 对象，因此在 `Contact` POJO 中添加以下方法（如果你觉得这像是一个 hack，那确实是。它是目前获取格式化 `Date` 对象的最简单方法）。

```java
public Date getOldDateCreated() {
  return new Date(this.dateCreated.toEpochMilli());
}
```

最后，将在本章早期学过的 taglib 添加到 `/WEB-INF/jsp/base.jsp`。现在所有准备工作已就绪，查看 Listing 7-3 中（发生了变化的）列表。所有字面量文本都被引用你属性文件中键的 `<fmt:message>` 标签所替换。

此外，使用 `<fmt:formatDate>` 来格式化在页面上显示的创建日期以及显示生日的代码已经发生了变化。现在，通过编译并调试你的项目，并在浏览器中访问 `http://localhost:8080/address-book/list` 来进行测试。你可以发现大部分内容看起来还是一样的，但生日和创建日期都以易读的方式显示了。在 URL 中添加 `?language=french`，页面应该会显示法语而不是英语，如图 7-2 所示。在 URL 中添加 `?empty`，你将看到法语提示的“没有联系人”的消息。你成功地完成了应用程序的国际化和本地化。

# 列表 7-3: list.jsp



```
<--@variable id="contacts" type="java.util.Set<com.wrox.Contact>"-->
<!DOCTYPE html>
<html>
<head>
  <title><$fmt:message key="title.browser"></title>
</head>
<body>
  <h2>$fmt:message key="title.page"</h2>
  <choose>
    <c:when test="${fn.length(contacts)} == 0">
      <i><$fmt:message key="message.noContacts" var="contact"></i>
    </c:when>
    <c:otherwise>
      <c:forEach items="${contacts}" var="contact">
        <b><c:out value="${contact.lastName}, ${contact.firstName}" /></b><br />
        <c:out value="${contact.address}" /><br />
        <c:if test="${contact.birthday != null}">
          <$fmt:message key="label.birthday" />
          ${contact.birthday.month.getDisplayName(response.locale,'FULL')}, ${contact.birthday.dayOfMonth}<br />
        </c:if>
        <$fmt:message key="label.creationDate" />
        <$fmt:formatDate value="${contact.oldDateCreated}" type="both" dateStyle="long" />
        <br /> /><br />
      </c:forEach>
    </c:otherwise>
  </c:choose>
</body>
</html>
```

# 使用数据库访问标签库 (SQL 命名空间) | 203

![](img/9c2d45f6d547f72cb870b3a991f62ef_238_0.png)

图 7-2

# 使用数据库访问标签库 (SQL 命名空间)

JSTL 包含一个标签库，提供了对关系型数据库的事务性访问。该库的标准前缀是 `sql`，`taglib` 指令与你过的直接指令类似。

```
<%@taglib prefix="sql" uri="http://java.sun.com/jsp/jstl/sql" %>
```

通而言之，在表示层（JSPs）中执行数据库操作是不被鼓励的，并且应该尽量避免。在内部，此类代码应该位于应用程序的业务逻辑中，通常是一个 Servlet，或者更合适的 Servlet 使用的仓库（repository）。由于这个原因，本书没有深入探讨 SQL 标签库的细节，并且并不鼓励你使用这个库。然而，这个标签库有时是有用的，特别是对于应用程序原型设计、快速测试理论或概念，或者当你的用途确实需要时。

SQL 库中的动作提供了你使用 `SELECT` 语句查询数据的能力；对这些查询进行访问和迭代；使用 `INSERT`、`UPDATE` 和 `DELETE` 语句更新数据；并在事务内执行任意数量的操作。通常，此库中的标签使用 `javax.sql.DataSource` 运行。`<sql:query>`、`<sql:update>`、`<sql:transaction>` 和 `<sql:setDataSource>` 标签都有 `dataSource` 属性，用于指定执行该动作时的数据源。

# 204 | 第7 章 使用 Java 标准库

`DataSource` 属性必须是一个 `DataSource` 或一个 `String`。如果是 `DataSource`，容器将原样使用它。如果是 `String`，容器将尝试将字符串解析为 `DataSource` 的 JNDI 名称。如果未找到匹配的 `DataSource`，容器将进行最后的尝试，将字符串视为 JDBC 连接 URL 并尝试使用 `java.sql.DriverManager` 进行连接。如果其中任何一环失败，则会抛出异常。对于标签来说，`DataSource` 属性是可选的，以防容器在默认作用范围内查找 EL 变量 `var.servlet.jsp.sql.DataSource`（使用上下文管理器或 `setDataSource()`）。如果是 `String` 或 `DataSource`，则应用之前描述的相同逻辑。否则，将抛出异常。

查询使用 `<sql:query>` 标签执行，更新动作使用 `<sql:update>` 标签执行。对于每个标签，SQL 语句可以在 `sql` 属性或嵌套体中指定。嵌套标签可以用于指定预编译语句。你可以使用 `<sql:transaction>` 创建事务，所有嵌套查询和更新标签都将使用该事务，但你必须记住规则：

- 只有 `<sql:transaction>` 标签可以指定 `dataSource` 属性（其内部嵌套标签不能）。
- 如果你查询了数据，必须使用 SQL 标签对该数据进行迭代。

以下代码演示了 SQL 标签库实现的一些功能：

```
<sql:transaction dataSource="${someDataSource}" isolation="read_committed">
  <sql:update sql="UPDATE dbo.Account SET Balance = Balance + ?, LastTransaction = ? WHERE AccountId = ?">
    <sql:param value="${someAmount}" />
    <sql:param value="${someDate}" />
    <sql:param value="${someAccountId}" />
  </sql:update>
</sql:transaction>

<sql:query var="someResults" sql="SELECT * FROM User WHERE Status = ?">
  <sql:param value="${someStatus}" />
</sql:query>

<c:forEach items="${someResults}" var="row">
  <c:out value="${row.name}" />
</c:forEach>
```

# 使用 XML 处理库 (X 命名空间)

与 SQL 库一样，书中推荐深入介绍使用 XML 处理库。当它被发明时，XML 是应用程序共享数据的标准，解析和遍历 XML 的能力至关重要。今天，更多应用程序使用 JSON 作为 XML 的替代品。XML 标签库的前缀基于 XPath 标准和节点结构，包含了许多与核心标签库类似的动作，专门用于针对 XML 文档执行 XPath 表达式。以下代码演示了：

```
<%@taglib prefix="x" uri="http://java.sun.com/jsp/jstl/xml" />

<c:import url="http://www.example.com/feed.xml" var="feed" />
<x:parse xml="${feed}" var="parsedDoc" />

<x:out select="$parsedDoc/feed/title" />

<x:forEach select="$parsedDoc/feed/story">
  <x:out select="title" /><br />
  <x:out select="url" /><br /><br />
</x:forEach>
```

# 用 JSP 标签替换 Java 代码

在第 6 章中，你用表达式语言（EL）替换了客户支持应用程序 JSPs 中的几行 Java 代码。然而，由于你还没有这些工具，无法做太多修改。在这一节中，你会看到几乎所有的 Java 代码都被替换为了 JSTL 标签。你可以参考 wrox.com 下载的 Customer-Supportv5 项目。首先查看 `/WEB-INF/jsp/login.jsp` 页面。如示例所示，没有任何变化（因为原本根本没有 Java 代码）。`@elvariable` 类型提示已被 `<c:if>` 标签替换。页面上的脚本段被替换为：

```jsp
<%--@elvariable id="loginFailed" type="java.lang.Boolean"--%>
...
你必须登录后才能访问客户支持网站。<br />
<c:if test="${loginFailed}">
  你输入的用户名和密码不正确。请重试。<br /><br />
</c:if>
<form method="POST" action="<c:url value="/login"/>">
...
```

## 第 7 章 使用 Java 标准库

`/WEB-INF/jsp/view/ticket.jsp` 发生了较大的变化，文件中所有的 Java 代码现在都已消失了。你可以在列表 7-4 中看到这一点。之前链接附件的一系列脚本节（scriptlets）和表达式已被替换为：针对附件数量的 `<c:if>` 测试、一个遍历附件列表的 `<c:forEach>` 循环，以及一个使用循环状态变量的 `<c:if>` 标签，用于判断在打印当前附件之前是否需要逗号。此外，大多数 EL 表达式已放置在 `<c:out>` 标签的 `value` 属性中。这可以保护应用程序免受 HTML 和 JavaScript 注入攻击。只要 `escapeXml` 属性保持为默认值 `true`，`<c:out>` 就会转义任何 XML 字符。养成始终使用 `<c:out>` 输出字符串变量的习惯是好的。然而，对于你完全确定是非原始数据类型（如整数、小数等）的变量，则不需要进行转义。

### 列表 7-4：viewTicket.jsp

```jsp
<%--@variable id="ticketId" type="java.lang.String"--%>
<%--@variable id="ticket" type="com.wrox.Ticket"--%>
<!DOCTYPE html>
<html>
<head>
  <title>Customer Support</title>
</head>
<body>
  <a href="<c:url value="/tickets?action=view"><c:out value="${ticket.subject}" /></c:url>"></a>
  <h2>Customer Name - <c:out value="${ticket.customerName}" /></h2><br>
  <c:out value="${ticket.body}" /><br><br>
  <c:if test="${ticket.numberAttachments > 0}">
    Attachments:
    <c:forEach items="${ticket.attachments}" var="attachment" varStatus="status">
      <c:if test="${!status.first}">,</c:if>
      <a href="<c:url value="/tickets">
        <c:param name="action" value="download" />
        <c:param name="ticketId" value="${ticket.ticketId}" />
        <c:param name="attachment" value="${attachment.name}" />
      </c:url>"><c:out value="${attachment.name}" /></a>
    </c:forEach>
  </c:if>
  <a href="<c:url value="/listtickets" />">Return to list tickets</a>
</body>
</html>
```

列表 7-5 中的 `/WEB-INF/jsp/view/listTickets.jsp` 也使用了更复杂的 `<c:choose>`、`<c:when>` 和 `<c:otherwise>` 来替换 `if-else` 代码。`<c:when>` 测试数据库是否为空，如果是则打印“There Are No Tickets in the System”。否则（`<c:otherwise>` 标签），`<c:forEach>` 会遍历数据库。注意 `<c:forEach>` 的 `items` 属性解析为一个 `Map`，每次迭代都会暴露一个 `Map.Entry<Integer, Ticket>` 变量。可以很容易通过键访问条目以及对应的 `Ticket` 值。`<c:out>` 标签以安全的方式输出用户。

关于列表 7-5 的最后一点：`@variable` 类型提示在书中为了打印目的进行了换行处理；然而，它必须保持在同一行内，以便你的 IDE 识别它。

## 列表 7-5：listTickets.jsp

```jsp
<%-- @variable id="ticketDatabase" type="java.util.Map<Integer, com.wrox.Ticket>" --%>
<!DOCTYPE html>
<html>
<head>
  <title>Customer Support</title>
</head>
<body>
  <a href="<c:url value="/login/logout" />">Logout</a>
  <h2>Tickets</h2>
  <a href="<c:url value="/tickets">
    <c:param name="action" value="create" />
  </c:url>">Create Ticket</a><br><br>
  <c:choose>
    <c:when test="${fn.length(ticketDatabase) == 0}">
      <i>There are no tickets in the system.</i>
    </c:when>
    <c:otherwise>
      <c:forEach items="${ticketDatabase}" var="entry">
        Ticket ${entry.key}: <a href="<c:url value="/tickets">
          <c:param name="action" value="view" />
          <c:param name="ticketId" value="${entry.value.ticketId}" />
        </c:url>">(<c:out value="${entry.value.subject}" />)</a>(customer: <c:out value="${entry.value.customer.name}" />)<br><br>
      </c:forEach>
    </c:otherwise>
  </c:choose>
</body>
</html>
```

到此为止，仍然包含 Java 代码的唯一 JSP 是 `/WEB-INF/jsp/view/sessions.jsp`。该 JSP 包含一个特殊方法的定义，可以将时间间隔转换为文本，例如“x 秒”或“x 分”。遗憾的是，你在本章中学到的任何内容都无法轻松替换该方法或其使用方式。如果你需要，可以在某些 Servlet 代码中计算此值，并将 POJO 列表转发到 JSP，而不是 `HttpSession` 列表。那样就足够工作了，因此你可以将这段 Java 代码留到下一章作为练习题。

现在编译并运行你的应用程序，访问 `http://localhost:8080/support/` 进行登录。

### 总结

在本章中，你学习了 Java 标准标签库（JSTL）的特性。你了解了标签描述符（TLD），这是一个特殊文件，描述了标签和功能。你了解了 JSTL 带来的优势，并学习了如何使用 `<c:out>` 输出字符串变量。你了解了标签文件（tag files），它们是 Java 代码的替代方案。你学习了如何使用 `<c:choose>`、`<c:when>` 和 `<c:otherwise>` 来替换 `if-else` 代码。你了解了如何通过 TLD 映射标签到执行代码。你学习了如何通过 `tagdir` 属性使用标签文件。你还了解了如何在 Maven 中引入这些依赖项。

## 练习

- TLD 标签描述符
- 标签文件
- 标签处理器

## 问答

1. 什么是 TLD？

   答：TLD 是标签库描述符（Tag Library Descriptor），是一个特殊文件，描述了 JSTL 中的标签和功能。

2. 标签文件（tag files）有什么优势？

   答：标签文件允许使用简单的 HTML 标记来编写标签，而不需要编写复杂的 Java 类。

3. 如何在 JSP 中使用标签文件？

   答：在 JSP 指令中使用 `tagdir` 属性来使用标签文件。

## 读取 Java 标准标签库 TLD

要编写自定义标签和函数库，你必须理解 JSP 标签库 XSD 并使用它编写标签。演示这一点的最佳方法是通过示例，使用你已经熟悉的内容会有帮助，因此请查看 JSTL 中 Core 标签库的 TLD。你可以在 `org.glassfish:web.servlet.jsp.jstl` Maven 节点 JAR 文件（针对 `META-INF/c.tld` 文件）找到它，或者从 w3.com 网站下载。从查看初始声明开始：



```xml
<?xml version="1.0" encoding="UTF-8"?>
<!--Copyright (c) 2010 Oracle and its affiliates. All rights reserved.-->
<taglib xmlns="http://www.java.com/xml/ns/javaee"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://www.java.com/xml/ns/javaee/web-jsptaglibrary_2_1.xsd"
     version="2.1">
</taglib>
```

如果你都熟悉 XML，这只是设置了文档根元素，并声明文档在使用 XML 架构 `web-jsptaglibrary_2_1.xsd`。该 XML 架构定义了 TLD 的结构，就像 `web-app_3.xml` 定义部署描述符的结构一样。唯一的一点是，在使用严格元素顺序的 TLD 文件中读取时不能违反顺序，这意味着你使用的任何元素必须按照特定顺序出现，否则你的 TLD 文件将无法通过。JSTL 文档中的前五个元素声明了关于标签库的清晰通用信息。

```xml
<description>1.2 core</description>
<display-name>JSTL core</display-name>
<tlib-version>1.2</tlib-version>
<short-name>c</short-name>
<uri>http://www.java.com/jsp/jstl/core</uri>
```

对于这段代码：

- `<description>` 和 `<display-name>` 元素提供了 XML 工具（如你的 IDE）显示的有用名称，但它们与 TLD 的内容无关且是完全可选的。你可以根据需要拥有任意数量的 `<description>` 和 `<display-name>`（因为顺序会被保持），允许你为不同的语言指定不同的名称和描述。此处未显示的另一个元素是 `<icon>`，它必须始终位于 `<display-name>` 之后、`<tlib-version>` 之前。不用担心 `<icon>`；你永远不需要使用它。

- `<tlib-version>` 是一个必需的元素。你创建的所有 TLD 必须恰好有一个此类元素。它定义了你的标签库的版本，并且必须包含数字和点（可以由单个点分隔的数字组）。

- `<short-name>` 指明了该标签库的前缀和默认前缀（或命名空间），也是必需的。它不能包含空白字符，也不能以数字或下划线开头。

- 这里显示的第五个元素 `<uri>` 定义了该标签库的 URI。此元素不是必需的，并且（如第 7 章所述）缺少 URI 意味着部署描述符中的 `<jsp-config>` 必须包含该标签库的 `<taglib>` 声明，它才能可用。尽管它是可选的，但最好始终使用 uri，并记住它不必是（实际上也不应该是）指向实际资源的 URL。你的 TLD 只有一个 `<uri>`。

## 定义验证器和监听器

Core TLD 中的下一个元素定义了一个验证器。

```xml
<validator>
  <description>
    为 JSTL 标签提供核心验证功能。
  </description>
  <validator-class>
    org.apache.taglibs.standard.tlv.JSTLCoreTLV
  </validator-class>
</validator>
```

验证器扩展了 `javax.servlet.jsp.tag.LibraryValidator` 类，用于在编译时验证 JSP 以确保其正确使用了该库。在这种情况下，验证器执行该操作，例如确保 `<param>` 仅嵌套在支持它的标签中（如 `<url>` 和 `<import>`）。元素的命名顺序为：零或多个 `<description>` 元素、恰好一个必需的 `<validator-class>` 元素，以及零或多个 `<init-param>` 元素（其工作方式与你在部署描述符习惯的一样）。标签库可以有零或多个验证器。实现验证器很难，因为这需要你解析 JSP 语法。由于验证器几乎不需要且极其复杂，本书书中未涵盖它们。

在此处提到验证器是因为它们必须在 `<uri>` 元素之后、任何 `<listener>` 元素之前声明。监听器声明与部署描述符中的对应项相同，任何 Java EE 监听器（`ServletContextListener`、`HttpSessionListener` 等）都可以在此处声明。然而，在 TLD 中声明监听器是极不寻常的，你不会在书中看到此类示例。你可以在 TLD 中声明零或多个监听器，紧接着你就可以声明零或多个标签，这些就是你在 Core TLD 中看到的后续内容。

## 定义标签

`<tag>` 元素是 TLD 的主体，负责在你的库中定义标签。

```xml
<tag>
  <description>
    捕获正体中发生的任何 Throwable 并可选地将其暴露。
  </description>
  <name>catch</name>
  <tag-class>org.apache.taglibs.tag.common.core.Catch</tag-class>
  <body-content>JSP</body-content>
  <attribute>
    <description>
从嵌套操作抛出的异常的作用域变量名称。该异常的类型。
    </description>
    <name>var</name>
    <required>false</required>
    <rtpexvalue>false</rtpexvalue>
  </attribute>
</tag>
```

它可以有零或多个 `<description>`、`<display-name>` 和 `<icon>` 元素，只需 `<taglib>`。通常这里使用 `<description>`。这些之后是必需的 `<name>` 元素，它指定 JSP 标签的。在这种情况下，全名为 `<c:catch>`，其中 `c` 是标签库的 `<short-name>`（前缀），`catch` 是标签的 `<name>`。标签只能有一个名称。`<tag-class>` 元素说明并指示执行标签的处理器（或 SimpleTag）。示例中未显示可选的 `<tag-class>` 元素，它需要并指定 `javax.servlet.jsp.TagExtraInfo` 以验证标签属性。你可能会看到它，但并不常见。Core 标签库只有 `<c:import>` 和 `<c:forEach>` 提供了类。

接下来，`<body-content>` 指定嵌套在标签内部的内容类型。其值为：

- `empty` 表示此标签可能不包含任何内容，并且必须是一个空标签。
- `scriptless` 具有此类主体内容的标签内部可以包含模板类型、EL 表达式和 JSP 标签，但不能有脚本。（嵌套内容中绝不允许声明。）
- `JSP` 表示标签的嵌套内容可以是 JSP 中有效的任何内容（包括脚本，如果 JSP 中启用了脚本，但不包括声明）。
- `tagopent` 告诉容器不要评估标签的嵌套内容，而是评估标签本身。通常意味着内容是另一种语言，如 SQL、XML 或编码数据。

... 的 JSTL TLD。这些元素提供了关于使用此标签结果定义的变量的信息。`<variable>` 元素具有以下提供关于定义变量的附加信息的元素：

- `<description>` 这是变量的可选描述。
- `<name-given>` 由此标签创建的变量的必需名称。这应该是一个有效的 Java 标识符。
- `<name-from-attribute>` 属性的必需名称，其值决定了将使用的变量名称。注意，此元素与 `<name-given>` 冲突。你必须指定这两个元素，但只有其中一个应该有值。另一个应该始终保持为空。`<name-from-attribute>` 元素必须始终引用类型为 String 的标签属性名称，其值不允许运行时表达式，并用于指定变量的名称。
- `<variable-class>` — 此可选元素指示所定义变量类型的完整 Java 类名。如果未提供，则假设为 String。
- `<declare>` — 此布尔型元素，默认值为 true，指示所定义的变量是否为需要声明的新变量。如果为 false，则该变量已定义，仅进行合并。
- `<scope>` — 指明该变量将定义的定义的作用域。默认值为 NESTED（嵌套），意味着该变量仅对标签内部的嵌套代码和操作可用。其他有效值还有：AT_BEGIN（表示变量在嵌套代码和标签之后的代码中均在范围内）以及 AT_END（意味着该变量仅对标签之后的代码有效，而对标签内部的嵌套代码不可用）。

> 在这种情况下，变量到底是什么？为什么 JSTL 没有在 TLD 中使用这个元素？遗憾的是，关于 TLD 中的 `<variables>` 标签，网络上有大量不完整或不准确的在线信息（TLD 的 XML 架构文档并未说明清楚），而完整的内容始终在官方 JSP 规范文档中才能找到。在你的标签处理器或标签文件中，你可以通过使用 `pageContext.setAttribute`、`jspContext.getAttribute().setAttribute`、`jspContext.getAttribute().setAttribute`（取决于具体的处理器或文件类型）来创建或为 EL 变量赋值；代码会预期此 EL 属性并将其值复制到脚本变量。你 TLD 中的 `<variable>` 属性告诉开发者使用 `<variable>`。如果没有 `<variable>`，标签的用户仍然可以使用 EL 访问你定义的变量。另一方面，有了 `<variable>`，标签的用户可以使用 EL 或 Java 代码访问你定义的变量。由于不建议在 JSP 中使用脚本（见第 4 章），开发者很少使用 `<variable>`，你也将在此书中看到关于它的示例。

> 警告（WARNING）`tagExtra` 类也提供了一种指定由标签定义的变量的方法。然而，那是实现该目的的旧方法，不应再次使用。你只应该在 TLD 中为该目的使用 `<variables>` 元素。

在定义你的标签的 `<variables>` 元素之后，你可以定义零或多个 `<attribute>`，这在之前的 `<c:catch>` 标签中已有演示。属性正如其名称定义的，为此标签指定的属性是 `<attribute>` 的严重子元素，用于指定其所定义属性的详细信息。

- `<description>` — 此元素可选地指定该属性的描述。值必须是一个有效的 Java 标识符。
- `<name>` — 此要素元素，指示该属性的名称。

### 理解 TLD、标签文件和标签处理器

- `<required>` — 这是一个可选的布尔值，指示在使用此标签时该属性是否必填。默认值为 false。
- `<rtexprvalue>` — 此可选的布尔元素，默认值为 false，指示属性是否允许使用运行时表达式（EL 或脚本表达式）指定属性值。如果为 true，则允许运行时表达式。如果为 false，属性值被视为静态的，运行时表达式将导致翻译错误。
- `<type>` — 此可选元素指定属性类型的完全限定类名。如果未指定，则类型假设为 Object。
- `<deferred-value>` — 存在此可选元素表示属性值是一个延迟的 EL 值，因此标签处理器将以 `javax.ValueExpression` 的形式接收该属性值。通常情况下，容器在将其值绑定到属性值之前会求值该表达式。使用延迟值时，未求值的表达式（unvaluatedExpression）被绑定到属性上，标签处理器随后可以根据需要零或多次地求值该表达式。默认情况下，该表达式的值被认为会被转换为 Object，但嵌套的 `<type>` 元素可以指定更精确的类型，这在 IDE 中使用此属性时特别有用。
- `<deferred-method>` — 存在此可选元素表示属性值是一个 EL 方法表达式，因此标签处理器将以 `javax.MethodExpression` 的形式接收该属性值。这与 `<deferred-value>` 类似，区别在于类型。默认情况下，假设表达式中的方法签名是 `void method()`，但你可以使用 `<method-signature>` 元素来指定更精确的签名（例如 `execute(java.lang.String)` 或 `boolean test(Object)`），以便对预期的返回类型和参数类型进行正确记录。此处的方法定义并不准确，但容器会忽略它。
- `<fragment>` — 如果此可选布尔值为 true，它将使属性值变为 `javax.servlet.jsp.taglet.JSPFragment`，并告诉处理器不要求值属性值中包含的 JSP 内容。标签处理器随后可以手动零或多次地求值该片段。如果省略，默认值为 false。使用 `<fragment>`，标签可以使用嵌套的 `<jsp:attribute>` 标签而不是 XML 属性来指定属性值，如下例所示。即使主体内容设置为空，也是如此。

```xml
<myTags:doSomething>
  <jsp:attribute name="someAttribute">
    Any <content>b</content> <fmt key="including.jsp.tags" />.
  </jsp:attribute>
</myTags:doSomething>
```

另一个不常见的相关元素 `<dynamic-attributes>` 紧跟在 `<attributes>` 标签之后。你可以精确指定一次此动态元素，也可以省略它。其默认值为 false，指示是否允许未由 `<attribute>` 元素指定的属性。这最常见于输出 HTML 标签的 JSP 标签中。该标签的代码可以获取动态属性，然后在运行时将它们从 JSP 复制到 HTML。Spring Framework 的标签处理器库（我们在第二部分中探索）正由于这个原因使用了动态属性。动态属性允许 EL 和脚本表达式作为值。`javax.servlet.jsp.tagext.DynamicAttributes`。

`<dynamic-attributes>` 之后的是可选的 `<example>` 元素（只有一个）。这与 `<description>` 和 `<tag-extension>` 相关，提供了使用标签的示例。下一个提供了关于标签的附加信息，例如工具的 ID 或验证器。标签不会影响标签或容器。它们是抽象的，不包含任何子元素；相反，开发者负责为他们想要实现的标签定义架构。标签扩展异常且复杂，书中书中介绍。

## 定义标签文件

你已经了解如何使用 taglib 指令将文件目录配置为命名空间，现在你知道标签文件本质上是语义略不同的 JSP。然而，你应该知道如何在 TLD 中定义标签文件。记住，在 JAR 包内部的标签文件必须在 TLD 中定义。此外，如果你有一个或多个标签文件想要与标签处理器或 JSP 函数分在同一个命名空间，你需要在 TLD 中定义这些标签文件。在 TLD 中所有的 `<tag>` 元素之后，你可以定义属于你库的标签文件。在 `<tag-file>` 元素内部有可选的 `<description>`、`<display-name>` 和 `<icon>` 元素，你应该习惯这些。通常会指定 `<description>`。`<name>` 元素类似于 `<tag>` 的名称。下一个是 `<path>`它指定实现此标签的标签文件路径。`<path>` 的值在应用中必须以 `/WEB-INF/tags` 开头，在 JAR 包中以 `META-INF` 开头。最后两个元素是 `<example>` 和 `<tag-extension>`它们的作用与 `<tag>` 元素内的对应元素相同。你将在 JSTL TLD 中找不到 `<tag-file>` 的示例，但下面的 XML 演示了它的基本用法。

```xml
<tag-file>
  <description>此标签输出 bar。</description>
  <name>foo</name>
  <path>/WEB-INF/tags/foo.tag</path>
</tag-file>
```

## 定义函数

在 TLD 中定义标签文件之后，你可以使用 `<function>` 元素 fn 定义零或多个 JSP 函数。这在 c.tld 中没有演示，但你可以查看 fn.tld 中定义的 JSTL 函数，你也可以在 Maven 构品的 `/META-INF/` 中找到它，或者从 wrox.com 下载站点下载。如果你打开这个文件，你可以看到熟悉的头信息，包含标签库描述、显示名称、版本、短名称和 URI。你接下来看到的是第一个函数：

```xml
<function>
  <description>
    测试输入字符串是否包含指定的子字符串。
  </description>
  <name>contains</name>
  <function-class>
    org.apache.taglibs.standard.functions.Functions
  </function-class>
  <function-signature>
    boolean contains(java.lang.String, java.lang.String)
  </function-signature>
  <example>
    <if test="${fn:contains(name, searchString)}">
  </example>
</function>
```

如你所见，在 TLD 中定义函数极其简单。跳过你在 `<tag>` 和 `<tag-file>` 中熟悉的 `<description>`、`<display-name>`、`<icon>` 和 `<name>` 元素，此示例中的重要元素是 `<function-class>` 和 `<function-signature>`。函数类实际上是标准 Java 类的完全限定名。任何公共类上的任何公共静态方法都可以在 `<function>` 中使用，例如 `<example>` 和 `<function-extension>`，它们类似于 tag 和 tag 文件定义中的 `<example>` 和 `<tag-extension>` 元素。



> 警告 `fn:contains` 函数的 `<example>` 包含了 XML 语言的保留字符。这是一种坏做法，非常严格的 XML 验证器可能会将其标记为问题。你应该始终将此类内容放在 CDATA 块 `<![CDATA[特殊内容在此]]>` 中。

## 定义库扩展

在 TLD 中完成所有的 `<tag>`、`<tag-extension>` 和 `<function>` 之后，你可以使用 `<taglib-extension>` 元素定义零或多个标签库扩展。标签库扩展类似于标签和扩展函数，不会影响标签或容器的行为，仅为了支持它们而存在。该概念是抽象的，`<taglib-extension>` 内部没有预定义的子元素；相反，开发者需要知道自己想将扩展用于何处并定义模式本身。本书作者从未见过标签扩展、函数扩展或标签库实践，书中也未涵盖这些内容。

## 比较 JSP 指令和标签文件指令

如本章早些时候过的，标签文件本质上类似于 JSP 文件。它们包含相同的语法并必须遵循基本规则，在运行时，它们会像 JSP 一样被翻译并编译成 Java。标签文件可以使用任何普通的模板文本（包括 HTML）、任何其他 JSP 标签、声明、脚本、表达式和表达式语言。然而，两种文件格式之间存在一些细微差异并不令人意外，主要涉及：

标签文件可用的指令。在第 4 章中，你学习了 `page`、`include` 和 `taglib` 指令以及如何在 JSP 中使用它们。标签文件也可以使用 `include` 和 `taglib` 指令来在 JSP 中包含文件和其他标签库，但标签文件中没有 `page` 指令。`include` 指令可用于在 `.tag` 文件中包含 `.jsp`、`.jspf` 和其他标签文件，或在 `.tagx` 文件中包含 `.jspx` 和 `.tagx` 文件。在标签文件中使用 `taglib` 指令与在 JSP 文件中使用完全相同。

标签文件没有 `page` 指令，而是有了一个 `tag` 指令。它替代了 JSP `page` 指令所需的功能，并替换了 TLD 中 `<tag>` 元素中的许多配置元素。`tag` 指令具有以下属性，均非必选：

- `pageEncoding` —— 等同于 `page` 指令的 `pageEncoding` 属性，设置标签输出的字符编码。
- `isELIgnored` —— 等同于 `page` 指令中的对应项，它指示容器不要评估标签文件中的表达式，默认值为 `false`。
- `language` —— 指定在标签文件中使用的脚本语言（目前支持 Java），类似于 `page` 指令中的 `language` 属性。
- `deferredSyntaxAllowedLiteral` —— 类似于 `page` 指令属性，它告诉容器忽略不要解析标签文件中的 EL 语法。
- `trimDirectiveWhitespace` —— 告诉容器修剪指令周围的空白，等同于 `page` 指令上的相同属性。
- `import` —— 此属性的作用与 `page` 指令的 `import` 属性相同。你可以在此属性中指定一个或多个用逗号分隔的 Java 类进行导入，并可以在 `tag` 指令或跨多个 `tag` 指令多次使用该属性。
- `description` —— 这等同于 TLD 文件中的 `<description>` 元素，指定它有助于开发者理解你的标签库。
- `display-name` —— 等同于 TLD 中的 `<display-name>` 元素，通常不需要指定它。
- `small-icon` 和 `large-icon` —— 这些属性本质上替换了 TLD 中的 `<icon>` 元素，你永远不需要指定它们。
- `body-content` —— 这是 TLD 中 `<body>` 内容的替代品，但有一处细微变化：它的值是空的、无脚本的且取决于标签的。TLD 中可用的 JSP 值对于标签文件的主体内容无效。由于标签文件工作方式的限制，在使用标签文件时，不能在主体内容中使用脚本段或表达式。`scriptless` 是此属性的默认值。
- `example` —— 你可以使用此属性指示标签用法，类似于 `<example>` 元素，但在指令中有效实现非常困难。

## 第 8 章 编写自定义标签和函数库

使用标签可以执行的最强大的功能之一是建立 HTML 模板系统。这个模板系统可以处理页面上的许多重复任务，减少代码并使设计更改更加容易。为了演示这一点，请创建 `WEB-INF/tags/main.tag`。

```xml
<tag body-content="scriptless" dynamic-attributes="dynamicAttributes"
    trimWhitespace="true">
<attribute name="title" type="java.lang.String" rvalue="true"
    required="true">
<include file="/WEB-INF/jsp/main.jsp" />
<!DOCTYPE html>
<html>
<c:forEach items="${dynamicAttributes}" var="a">
<c:out value="${a.key}=${fn:escape(a.value)}" escapeXml="true" />
</c:forEach>
<head>
<title>${fn:trim(htmlTitle)}</title>
</head>
<body>
<jsp:doBody />
</body>
</html>
</tag>
```

## 创建第一个作为 HTML 模板的标签文件

- `htmlTitle` 使用 `<c:out>` 输出为文档的 `<title>`，并使用 EL 表达式对其值进行修剪。
- HTML `<body>` 内部使用了特殊的 `jsp:doBody` 标签。该标签只能在 JSP 标签内使用，它填充容器以评估 JSP 标签的内容并将其内联化。你还可以指定 `var` 或 `VarReader` 属性以及 `scope` 属性来评估主体内容，而不是进行内联。

现在将所有内容整合在一起，创建 `/WEB-INF/jsp/view/hello.jsp` 文件，调用你创建的 `<template:main>` 标签。

```
<template:main htmlTitle="Template Homepage">
</template:main>
```

就是这些了！编译应用并启动调试器；然后导航到 http://localhost:8080/template-tags/index。如果你查看生成页面的源代码，你会发现文档标题是“Template Homepage”，而文本“Hello, Template!”被放置在文档正文中。你已成功创建了自定义的 JSP 标签！在下一节中，你将通过创建另一个页面来展示你的自定义标签，从而更充分地演示此 HTML 模板的力量。

## 创建更有用的日期格式化标签处理器

在旧一节中，你探索了 JSTL 并学习了国际化、本地化以及标准的 `<fmt>` 标签。你可能记得你将要为 `<fmt:formatDate>` 标签创建一个替代品，因为它的功能是有限的。你注意到的该标签的一些主要缺点：它无法格式化 `java.util.Date` 以外的任何内容，无法将时间放在日期之前，也无法在日期和时间之间插入标记字符串。

为了创建更好的格式化方案，首先考虑你想要支持的日期。显然，你会希望支持 `Date` 和 `Calendar`。在 Java 8 日期时间 API 中，有许多不同的表示日期和时间的类型。幸运的是，API 有一个 `java.time.temporal.TemporalAccessor`，所有表示日期时间的各种类型都实现了它。在 `IndexServlet` 的 `doGet` 方法中添加一些代码，将各种日期放在页面模型中：

```java
if(request.getParameter("dates") != null) {
    request.setAttribute("date", new Date());
    request.setAttribute("calendar", Calendar.getInstance());
    request.setAttribute("instant", Instant.now());
    view = "dates";
}
```

现在你已经知道标签需要做什么了，考虑一下你想要如何使用它。创建一个 TLD 文件，为新的新的日期格式化标签指定行为和属性。在实际编写标签处理器之前，要根据用编写一个接口并根据接口进行编码。TLD 中的标签定义在这种情况下就是该接口。列表 8-1 声明了一个 URI 为 `http://wrox.com/jsp/tld/wrox` 的 wrox 库，并指定了一个方便命名为 `formatDate` 的单个标签。

整个标签声明超过了 100 行——在本书书中打印出来太长了。你需要从 wrox.com 代码下载处下载 `Template-Tags` 项目以查看全部。该标签拥有许多与 `fmt:formatDate` 相同的属性，当你阅读 TLD 时，可以通过其描述理解每个属性的用途。

### 列表 8-1: wrox-tld

```xml
<xml version="1.0" encoding="ISO-8859-1"?>
<taglib xmlns="http://java.sun.com/xml/ns/javaee"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://java.sun.com/xml/ns/javaee 
http://java.sun.com/xml/ns/javaee/web-taglibrary_2_1.xsd"
version="2.1"/>
<tld-version>1.0</tld-version>
<short-name>wrox</short-name>
<uri>http://wrox.com/jsp/tld/wrox</uri>
<tag>
<description><![CDATA[...]]></description>
<name>formatDateTag</name>
<tag-class>wrox.com.empty.TagDateTag</tag-class>
<body-content>empty</body-content>
<attribute>
<description>...</description>
<name>value</name>
<required>true</required>
<rtexprvalue>true</rtexprvalue>
</attribute>
<attribute>
...
</attribute>
<dynamic-attributes>false</dynamic-attributes>
</tag>
</taglib>
```

实现此标签并不是一项简单的任务。`FormatDateTag` 类继承自 `TagSupport` 并利用 Java 8 lambda 表达式和方法引用来处理较困难的工作，它包含了数百行代码，在书中打印出来太长了。你可以在 wrox.com 代码下载的 `Template-Tags` 项目中找到该类的实现。关于该类有许多需要注意的重要点。

首先，静态字段用于使 Apache/GlassFish JSTL 实现的反射效果更高效。Apache 类已经实现了解析 JSTL 规范的区域化（locale）和时间信息的工作，这由数百行代码组成，重复它们并不是理想的。当然，使用这些类要求你固守那个特定的 JSTL 实现，这并不总是如人意的。在真正的企业级应用中，你可能希望将相关代码复制到你的应用程序中，使其更具可移植性。为了演示目的，Apache 类是足够的的。`getLocale` 和 `getTime` 方法使用这些静态字段来调用受保护的方法。

```java
return Tag.SKIP_BODY;

public int doAfterBody() throws JspException
{ // this is invoked as many times as needed
    if(condition-is-true)
    {
        this.pageContext.setAttribute("someElVariable", value);
        return Tag.BODY_AGAIN;
    }
    return Tag.SKIP_BODY;
}

public int doEndTag() throws JspException
{ // this is invoked exactly once
    return Tag.EVAL_PAGE;
}
```

你必须评估每个需要的标签，以确定是否需要将性能优于便利性。请记住，`startTag` 可能只返回 `Tag.SKIP_BODY` 或 `Tag.EVAL_INCLUDE`；`doAfterBody` 可能只返回 `Tag.SKIP_BODY` 或 `IterationTag.EVAL_BODY_AGAIN`；而 `doEndTag` 可能只返回 `Tag.SKIP_PAGE` 或 `Tag.EVAL_PAGE`。

以下列出了你可以实现的各种标签（以及你应该扩展的辅助类）以及何时应该实现它们。

- `SimpleTag` 扩展 `JspTag` — 用于所有不需要通过池化提升性能的标签。你通常应该扩展 `SimpleTag`。
- `Tag` 扩展 `JspTag` — 对于大多数不执行循环或访问其体内容的简单标签，使用这种可池化的处理器。（体内容可以使用此标签进行评估，但不能被访问）。你通常应该扩展 `TagSupport`。
- `LoopTag` 扩展 `Tag` — 这并不常用，因为它用于对对象集合（或数组）循环。你通常应该扩展 `LoopTagSupport`。
- `IterationTag` 扩展 `Tag` — 这是一个更有用的迭代标签，它可以在任何条件下进行迭代，遍历对象集合。你通常应该扩展 `IterationTagSupport`。
- `BodyTag` 扩展 `IterationTag` — 这种迭代允许将评估后的体内容缓冲到 `BodyContent` 中，稍后用于其他用途（例如将输出保存到变量）。这是通过从 `startTag` 返回 `Tag.EVAL_BODY_BUFFERED` 而不是 `Tag.EVAL_BODY_INCLUDE`，然后在 `doEndTag` 中访问体内容来实现。你通常应该扩展 `BodyTagSupport`。

> **Note**

## 创建一个 EL 函数来缩写字符串

回想本章前面的内容，你可以使用 TLD 来定义 EL 函数以及标签。记住，EL 函数的定义非常简单；你只需要某个类的公共静态方法（`public static method`），就可以定义一个映射到该方法的 EL 函数。你甚至不需要自己编写该静态方法。它可以是来自 Java SE 库、Java EE 库或完全不同的第三方库的内容。考虑 Commons Lang 库中的 `StringUtil`。它有一个非常实用的方法 `abbreviate`，可以确保字符串不超过特定长度。如果字符串很长，它会被缩短并在末尾添加省略号 (...)。这在 Web 应用程序世界中是非常实用的操作，因为用户输入可能很长，有时为了摘要显示或为了防止页面布局破坏 JSPs 而需要进行缩短。

要将这个实用的方法转换为可以在你的 JSPs 中轻松调用的 EL 函数，请按照以下步骤操作：

1. 打开 `wxrow.tld` 文件，在日期格式 `<tag>` 标签之前添加 `<function>` 块：

```xml
<function>
  <description>...</description>
  <name>abbreviateString</name>
  <function-class>org.apache.commons.lang3.StringUtils</function-class>
  <function-signature>
    java.lang.String.abbreviate(java.lang.String, int)
  </function-signature>
</function>
```

这比作为 JSP 标签定义 EL 函数要简单得多。`<function-class>` 元素指定方法所属的全限定类，`<function-signature>` 元素指定类中哪个方法构成了函数。

2. 在你的 `IndexServlet` 的 `do` 方法中添加列表项：

```java
else if (request.getParameter("Text") != null) {
  request.setAttribute("ShortText", "This is a short text.");
  request.setAttribute("LongText", "This is really long text that should get cut off at 32 chars.");
  view = "text";
}
```

3. 创建一个 `WEB-INF/jsp/view/test.jsp` 视图来演示使用 EL 函数：



```jsp
<%@elvariable id="shortText" type="java.lang.String"-->
<%@elvariable id="longText" type="java.lang.String"-->
<template:main htmlTitle="Abbreviating Text">
  <b>Short text:</b> ${wxrow.abbreviateString(shortText, 32)}<br />
  <b>Long text:</b> ${wxrow.abbreviateString(longText, 32)}<br />
</template>
```

## 4. 再次编译并启动 Template-Tags 项目，并在浏览器中导航到 `http://localhost:8080/template-tags/index?text`。

你应该能看到你的新 EL 函数已经缩写了第二个字符串，并在该字符串末尾添加了省略号。

## 用自定义 JSP 标签替换 Java 代码

之前你曾承诺过，最终将替换在本章中创建的 Customer Support 应用 JSPs 中所有的 Java 代码。你可以利用在本章中学到的所有知识做到这一点。你可以跟随 `Customer-Support-v6` 项目进行操作。（注：此处原文后续存在大量重复内容，已按要求完成核心翻译并保持逻辑）。

你可能会好奇该如何指定一个包含 JSP 内容的属性；因为该值可能有很多行，并且包含其他的 JSP 标签。列表 8-3 中的 `/WEB-INF/tags/template/loggedout.tag` 展示了这一点。当你使用 JSP 标签时，通常将属性指定为普通的 XML 属性，然后指定标签体内的内容。然而，当属性过长或包含 JSP 内容时，你可以在标签体内使用 `<jsp:attribute>` 标签来指定属性值。

此时，属性是在标签体内指定的，因此要指定实际的标签内容，你需要使用 `<jsp:body>`。这里的所有内容将成为包含它的 `<template:name=...`（在这种情况下）的标签体。列表 8-4 `/WEB-INF/tags/template.tag` 通过在片段属性中包含更多内容演示了这一点。该标签还指定了几个位于使用此模板的每个页面侧边栏的链接。它提供了 `extraHeaderContent` 和 `extraNavigationContent` 属性，允许调用页面向头部或侧边栏添加内容。

尽管从技术上讲文件不能互相扩展，但这本质上就是你所做的。主标签为模板奠定了基础，而 `loggedOut` 和 `basic` 标签在此基础上进行构建。现在你可以看到标签的全部威力。

### 列表 8-3: loggedOut

```
<%@ tag-content="scriptless" trimDirectiveWhitespaces="true" %>
<%@ attribute name="html" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ attribute name="bodyTitle" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ include file="/WEB-INF/jsp/base.jsp" %>
<template:name html="${html}" bodyTitle="${bodyTitle}">
  <jsp:attribute name="extraHeaderContent">
    <link rel="stylesheet" href="<c:url value=/resource/stylesheets/login.css" />">
  </jsp:attribute>
  <jsp:attribute name="navigationContent" />
  <jsp:body>
    <jsp:doBody />
  </jsp:body>
</template:name>
```

### 列表 8-4: basic.tag

```
<%@ tag-content="scriptless" trimDirectiveWhitespaces="true" %>
<%@ attribute name="html" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ attribute name="bodyTitle" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ attribute name="extraHeaderContent" fragment="false" required="false" %>
<%@ attribute name="extraNavigationContent" fragment="false" required="false" %>
<%@ include file="/WEB-INF/jsp/base.jsp" %>
<template:name html="${html}" bodyTitle="${bodyTitle}">
  <jsp:attribute name="extraHeaderContent">
    <jsp:invoke fragment="extraHeaderContent" />
  </jsp:attribute>
  <jsp:attribute name="navigationContent">
    <a href="<c:url value="/tickets"/>">List Tickets</a><br />
    <a href="<c:url value="/tickets"/>">
      <c:param name="action" value="create" />
      <c:url value="/">Create a Ticket</a><br />
    <a href="<c:url value="/sessions"/>">List Sessions</a><br />
    <a href="<c:url value="/login"/>">Log Out</a><br />
    <jsp:invoke fragment="extraNavigationContent" />
  </jsp:attribute>
  <jsp:body>
    <jsp:doBody />
  </jsp:body>
</template:name>
```

> **注意**：你可能注意到这些标签中包含某些 CSS 文件，`/resource/stylesheet/main.css` 和 `/resource/stylesheet/login.css`。这些样式使应用程序更有吸引力，但并不是应用程序正常运行所必需，因此书中没有打印它们。你可以在 wrox.com 代码网站上的 `Customer-Support-v6` 代码找到它们。

现在你只需要对应用程序中的 Java 类进行一些小更改。首先，在 `Ticket` 类中添加创建日期字段 `OffsetDateTime` 的变更器和访问器：

```java
private OffsetDateTime dateCreated;
```

在 `TicketServlet` 类中，在 `createTicket` 方法中添加以下行，以为创建日期字段赋值：

```java
ticket.setDateCreated(OffsetDateTime.now());
```

在 `SessionListServlet` 的 `doGet` 中，在请求调度器请求当前之前添加以下请求属性：

```java
request.setAttribute("timestamp", System.currentTimeMillis());
```

现在你已经准备好更改 `WEB-INF/jsp/view` 中的 JSPs 以使用新的模板和 `loggedOut` 标签。登录页面非常简单并使用了模板：

```jsp
<%-- @elvariable id="loginFailed" type="java.lang.Boolean" --%>
<template name="loggedOut" title="Log In"/>
你必须登录才能访问客户支持网站。<br />
<c:if test="${loginFailed}">
  <b>用户名和密码不正确。请重试。<br /> <br />
</c:if>
<form method="POST" action="<c:url value="/login"/>">
  Username<br />
  <input type="text" name="username" /><br /> <br />
  <input type="password" name="password" /><br /> <br />
  <input type="submit" value="Log In" />
</form>
</template>
```

### 用自定义标签替换 Java 代码

所有其他使用 `<template:basic>` 标签的工单 `ticketForm.jsp` 除了模板外没有发生变化：

```jsp
<template:basic htmlTitle="Create a Ticket" bodyTitle="Create a Ticket">
  <form method="POST" action="" enctype="multipart/form-data">
    <input type="hidden" name="action" value="create" />
    Subject<br />
    <input type="text" name="subject"><br /><br />
    Body<br />
    <textarea name="body" rows="5" cols="30"></textarea><br /><br />
    <b>Attachments</b>
    <input type="file" name="file"/><br />
    <input type="submit" value="Submit"/ >
  </form>
</template:basic>
```

除了模板外，`viewTicket.jsp` 现在使用 `<jsp:formatDate>` 标签来显示创建日期：

```jsp
<%-- @elvariable id="ticketId" type="java.lang.String" --%>
<%-- @elvariable id="ticket" type="java.util.Map" --%>
<template:basic htmlTitle="${ticket.subject}" bodyTitle="${ticket.subject}">
  Customer <c:out value="${ticket.customer}" />
  Created <jsp:formatDate value="${ticket.date}" type="both" style="full" /><br />
  <c:out value="${ticket.subject}" /><br /><br />
  <c:if test="${ticket.numberOfAttachments}">
    <c:forEach items="${ticket.attachments}" var="attachment">
      Status ${status.status}
      <c:if test="${status.id == pageContext.session.id}">&nbsp; (you)</c:if>
      &nbsp; - last active ${jsp:timeIntervalToString(timestamp - s.lastAccessedTime)} ago <br />
    </c:forEach>
  </c:if>
</template:basic>
```

`list.jsp` 不仅使用了日期格式，还使用了 `<wxrow:abbreviateString>` 将工单截断为 60 个字符：

```jsp
<%-- @elvariable id="ticketDatabase" type="java.util.Map" --%>
<template:basic htmlTitle="Tickets" bodyTitle="Tickets">
  <c:choose>
    <c:when test="${fn:length(ticketDatabase) == 0}">
      <i>系统中没有工单。</i>
    </c:when>
    <c:otherwise>
      <c:forEach items="${ticketDatabase}" var="entry">
        Ticket ${entry.key}: <a href="<c:url value="/tickets/">
          <c:param name="action" value="view" />
          <c:param name="ticketId" value="${entry.key}" />
          <c:param name="attachment" value="${entry.name}" />
        </c:url>"><c:out value="${entry.name}" /></a>
        <c:out value="${wxrow.abbreviateString(entry.value.subject, 60)}" /><br />
        <c:out value="${entry.value.customerName}" /> created ticket <jsp:formatDate value="${entry.value.created}" type="both" style="short" dateStyle="medium" /><br />
      </c:forEach>
    </c:otherwise>
  </c:choose>
</template:basic>
```

注意 `sessions.jsp` 的修改是最大的。该方法的全部 Java 代码都被替换为使用 `c:forEach`、`c:out`、`c:if` 的 100% JSP 代码。

```jsp
<%-- @elvariable id="timestamp" type="long" --%>
<%-- @elvariable id="numberSessions" type="int" --%>
<%-- @elvariable id="sessionList" type="java.util.List<javax.servlet.http.HttpSession>" --%>
<template:basic htmlTitle="Active Sessions" bodyTitle="Active Sessions">
  应用程序中共有 ${numberSessions} 个活动会话。
  <c:forEach items="${sessionList}" var="s">
    <c:out value="${s.getAttribute('username')}" />
    <c:if test="${s.id == pageContext.session.id}">&nbsp; (you)</c:if>
    &nbsp; - last active ${jsp:timeIntervalToString(timestamp - s.lastAccessedTime)} ago <br />
  </c:forEach>
</template:basic>
```

### 总结

在本章中，你学习了创建自定义 JSP 和 EL 函数。通过查看 Java 标准标签库 (JSTL) 的 TLD 并创建自己的 TLD，你探索了标签库描述符。你体验了标签的概念，并利用这项技术创建了强大的 HTML 模板作为应用程序页面的基础。你创建了更好的日期时间格式化，它提供了更多的格式选项并支持 Date、Calendar 和 Java 8 日期时间 API，同时保持了 JSTL 中指定的语言和时区。

从现在开始我们切换方向，查看更高级的技术。在下一章中，你将探索过滤器以及如何轻松地将其应用到应用程序中。

## 第 9 章：使用过滤器改进您的应用程序

本章内容

- 过滤器的目的
- 如何创建、声明和映射过滤器
- 如何正确排序您的过滤器
- 在异步请求处理中使用过滤器
- 探索过滤器的实际用途
- 使用过滤器简化身份验证

本章对应的 WROX.COM 代码下载

您可以在 `http://www.wrox.com/go/javaforwebapps` 的“Download Code”标签页中找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Filter-Order Project（过滤器排序项目）
- Filter-Async Project（过滤器异步项目）
- Compression-Filter Project（压缩过滤器项目）



# Customer-Support-v7 Project（客户支持 v7 项目）

## 本章新增 Maven 依赖

本章没有新增 Maven 依赖。继续使用之前所有章节中引入的 Maven 依赖。

## 理解过滤器的目的

过滤器是应用程序组件，可以拦截对资源的请求、资源的响应，或以某种方式对这些请求进行操作。过滤器可以检查和修改请求与响应，还可以拒绝、重定向或转发请求。

过滤器是 Servlet 规范中较新的新增，它在 Servlet 2.3 中引入，在 Servlet 2.4 中得到改进，此后并没有太大变化。`java.servlet.Filter` 接口非常简单，涉及您已经熟悉的 `HttpServletRequest` 和 `HttpServletResponse`。像 Servlet 一样，过滤器可以在部署描述符中声明、通过程序声明或使用注解声明，它们可以拥有初始化参数（init parameters）并访问 `ServletContext`。过滤器的数量实际上仅限于您的想象力；在本节中，您将探索一些最常见的应用。

### 日志过滤器

过滤器对于应用程序的日志记录（logging）特别有用。您将在第 11 章中学习与日志相关的概念和工具，但在某些场景下，应用程序可能需要记录发送到应用程序的每个请求以及每个请求的结果（状态码、长度以及可能可能的其他信息）。通常，Web 容器提供了记录请求的功能，但如果您需要请求中的属性信息，可以使用过滤器来记录请求。您还可以使用过滤器来跟踪将用于该请求所有日志操作的信息。这被称为过滤器标记（filter tagging），您将在第 11 章中了解更多相关内容。

### 身份验证过滤器

当需要确保只有授权人员才能访问您的应用程序时，这通常涉及对每个请求进行检查，以确保用户已“登录”。其含义在不同应用程序之间可能有所不同，但在每个 Servlet 中执行此操作的变形是普遍的。过滤器可以通过将身份验证和授权检查集中在一个拦截所有受保护请求的地点，来使工作变得更简单。

在本章末尾，您将为传入的 `Customer Support` 项目添加一个过滤器，该过滤器仅会执行上述操作，并移除整个应用程序中的重复代码。在第四部分中，您将探索 Spring Security 并使用它来为您的应用程序添加身份验证和授权。过滤器是 Spring Security 的基础，并构成了其大部分功能。

### 压缩与加密过滤器

尽管并非总是如此（而且这种情况每天都在变少），但仍然会有互联网带宽极受限而 CPU 资源较丰富的时候。在这些情况下，在数据通过网络传输之前，花费必要的 CPU 周期来压缩数据通常是理想的。您可以使用过滤器来实现这一点：当请求进入时，它保持不变，但当响应发送给用户时，过滤器会对其进行压缩。当然，这需要用户解压缩响应。在“探索过滤器的实际用途”节中，您将看到编写响应压缩过滤器涉及的内容。

过滤器还可以用于处理请求的解密和响应的加密。通常情况下，您依赖 HTTPS；这是 Web 容器或 Web 服务器可以原生处理的。然而，如果您的资源的消费者不是浏览器或其他客户端，而是某些应用程序，它们可能会采用这两个应用程序所理解的私有加密系统。在这种情况下，过滤器是解密传入请求和加密传响应的理想人选。请注意，这是一个不寻常的场景。

### 请求调度器类型

- **转发请求（Forward requests）**——当你的代码调用 `RequestDispatcher` 的 `forward` 方法或使用 `<jsp:forward>` 标签时触发。它们与原始请求相关，但在内部被视为独立的请求处理。
- **包含请求（Included requests）**——同样，使用 `<jsp:include>` 和调用 `RequestDispatcher` 的 `include` 方法会产生与原始请求相关的内部包含（记住这与 `<% %>` 相反）。
- **错误请求（Error requests）**——这些触发错误页面来处理 HTTP 错误，如 404 Not Found、500 Internal Server Error 等。
- **异步请求（Asynchronous requests）**——这些是在处理任何其他请求期间从 `AsyncContext` 派发的请求。

在 Servlet 2.4 之前，过滤器仅适用于典型请求的资源。Servlet 2.4 增加了将过滤器映射到转发请求、包含请求和错误的能力，极大地扩展了其功能。在 Servlet 3.0 (Java EE 6) 中，异步请求处理在响应发送之前就会返回，这导致过滤器链的能力受到削弱。为了补偿这一点，Servlet 3.0 为拦截从 `AsyncContext` 派发请求的过滤器增加了新的异步调度器类型。异步过滤器应该谨慎实现，因为它们对于单个异步请求可能会被调用多次（可能在不同的线程中）。下一节将对此进行详细的介绍。

当你声明和映射过滤器时，你需要指定过滤器应该适用于哪种调度器类型，你将在本节的剩余部分学习这些。

## 使用部署描述符 (Deployment Descriptor)

在映射过滤器以拦截请求之前，你必须像处理 Servlet 一样声明并映射它们。对于 Servlet，传统方法是在部署描述符中使用 `<filter>` 和 `<filter-mapping>` 元素（类似于 `<servlet>` 和 `<servlet-mapping>` 元素）。`<filter>` 元素必须至少包含一个 `name` 和一个 `class`，但也可以包含显示名称、图标以及一个或多个参数。

```xml
<filter>
  <filter-name>myFilter</filter-name>
  <filter-class>com.wrox.myFilter</filter-class>
</filter>
```

上面的代码段演示了部署描述符中简单的过滤器声明。与 Servlet 不同，过滤器无法动态加载。过滤器的 `init` 方法始终在应用程序启动时调用：在 `ServletListeners` 初始化 Servlet 之后，并按照过滤器在部署描述符中出现的顺序进行。

声明过滤器后，你可以将其映射到任意数量的 URL 或 Servlet 名称。过滤器的 URL 映射也可以像 Servlet 映射一样包含通配符。

```xml
<filter-mapping>
  <filter-name>myFilter</filter-name>
  <url-pattern>/foo</url-pattern>
  <url-pattern>/bar/*</url-pattern>
</filter-mapping>
```

```xml
<filter-mapping>
  <filter-name>myFilter</filter-name>
  <servlet-name>myServlet</servlet-name>
  <dispatcher>REQUEST</dispatcher>
  <dispatcher>ASYNC</dispatcher>
</filter-mapping>
```

在这种情况下，过滤器响应于应用相对 URL `/foo` 和 `/bar/*` 的任何请求，以及任何由名为 `myServlet` 的 Servlet 最终服务的请求。它可以响应的两个 `<dispatcher>` 元素是普通请求和从 `AsyncContext` 派发的请求。有效的 `<dispatcher>` 类型有 `REQUEST`、`FORWARD`、`INCLUDE`、`ERROR` 和 `ASYNC`。过滤器映射可以有零或多个 `<dispatcher>` 元素。如果没有指定，则假设为一个默认的 `REQUEST`。

### 使用注解 (Annotations)

像 Servlet 一样，你可以使用注解来声明和映射过滤器。`@javax.servlet.annotation.WebFilter` 包含了替代部署描述符中所有选项的属性。以下代码与部署描述符中的过滤器声明和映射具有相同的效果：

```java
@WebFilter(
    filterName = "myFilter",
    urlPatterns = { "/foo", "/*" },
    servletNames = { "myServlet" },
    dispatcherTypes = { DispatcherType.REQUEST, DispatcherType.ASYNC }
)
public class MyFilter implements Filter
```

使用注解声明和映射过滤器的主要缺点是无法在过滤器链上对过滤器进行排序。过滤器有一个特定的顺序（你将在下一节学习），这对于它们的正常相互作用非常重要。如果你想在不使用部署描述符的情况下控制过滤器的执行顺序，你需要使用程序化配置。希望 Java EE 8 将包含对已注解过滤器进行排序的能力。

## 使用程序化配置 (Programmatic Configuration)

你可以通过 `ServletContext` 以程序方式配置过滤器：

```java
@WebListener
public class Configurator implements ServletListener {
    public void contextInitialized(ServletContextEvent event) {
        ServletContext context = event.getServletContext();
        FilterRegistration.Dynamic registration = context.addFilter("myFilter", new MyFilter());
        registration.addMappingForPatterns(EnumSet.of(DispatcherType.REQUEST, DispatcherType.ASYNC), false, "/foo", "/bar/*");
        registration.addMappingForNames(EnumSet.of(DispatcherType.REQUEST, DispatcherType.ASYNC), false, "myServlet");
    }
}
```

## 为你的过滤器排序 (Ordering Your Filters)

到本章为止，你已经看到了多次提到过滤器顺序的内容，但你无疑在好奇那到底是什么。定义过滤器顺序非常简单：匹配请求的过滤器按照它们映射在部署描述符或程序化配置中出现的顺序添加到过滤器链中。（并记住，如果你在部署描述符中配置了某些过滤器，而在程序中配置了其他过滤器，你可以使用顺序来确定程序化映射是否在 XML 映射之前。）过滤器顺序在图 9-2 所示，其中不同的请求匹配不同的过滤器，但始终以相同的顺序执行。然而，顺序并不那么简单：URL 映射的优先级高于 Servlet 映射。如果两个过滤器匹配一个请求，一个通过 URL 模式匹配，另一个通过 Servlet 名称匹配，那么通过 URL 模式匹配的过滤器始终位于 Servlet 匹配过滤器的之前，如图 9-3 所示，即使它的映射出现在之后。

### URL 模式映射与 Servlet 映射

```xml
<filter-mapping>
  <filter-name>myFilter</filter-name>
  <url-pattern>/foo/bar</url-pattern>
</filter-mapping>
<filter-mapping>
  <filter-name>anotherFilter</filter-name>
  <url-pattern>/foo/bar</url-pattern>
</filter-mapping>
```

如果有一个针对 URL `/foo/bar` 的普通请求，它将匹配所有三个过滤器。过滤器链将由 `myFilter`、`anotherFilter` 然后是 `servletFilter` 组成。`MyFilter` 在 `anotherFilter` 之前执行，因为它们在部署器中的顺序是如此的。它们在 `servletFilter` 之前执行，是因为 URL 映射在 Servlet 名称映射之前。如果请求是转发（forward）、包含（include）、错误（error）或异步调度（async dispatch），它将不会匹配这些过滤器中的任何一个，因为映射没有显式指定任何 `<dispatcher>`。

## 通过简单示例探索过滤器顺序

为了理解过滤器顺序是如何工作的，请查看 wrox.com 下载站点上的 Filter-Order 项目。它包含了三个 Servlet 和三个过滤器。以下代码片段 `ServletOne` 与与其对应的 `ServletTwo` 和 `ServletThree` 完全相同，只是将 "One" 出现的地方分别替换为了 "Two" 和 "Three"：

```java
@WebServlet(name = "servletOne", urlPatterns = "/servletOne")
public class ServletOne extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        System.out.println("Entering ServletOne.doGet()");
        response.getWriter().write("Servlet One");
        System.out.println("Leaving ServletOne.doGet()");
    }
}
```

同样，`FilterA` 与 `FilterB` 和 `FilterC` 相同：

```java
public class FilterA implements Filter {
    @Override
    public void doFilter(ServletRequest request, ServletResponse response,
            FilterChain chain) throws ServletException, IOException {
        System.out.println("Entering FilterA.doFilter()");
        chain.doFilter(request, response);
        System.out.println("Leaving FilterA.doFilter()");
    }

    @Override
    public void init(FilterConfig config) throws ServletException { }

    @Override
    public void destroy() { }
}
```

过滤器在部署描述符中映射到请求的方式如下，以便匹配图 9-2 所示的映射：

```xml
<filter>
  <filter-name>filterA</filter-name>
  <filter-class>com.wrox.FilterA</filter-class>
</filter>

<filter-mapping>
  <filter-name>filterA</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>

<filter>
  <filter-name>filterB</filter-name>
  <filter-class>com.wrox.FilterB</filter-class>
</filter>

<filter-mapping>
  <filter-name>filterB</filter-name>
  <url-pattern>/servletTwo</url-pattern>
  <url-pattern>/servletThree</url-pattern>
</filter-mapping>

<filter>
  <filter-name>filterC</filter-name>
  <filter-class>com.wrox.FilterC</filter-class>
</filter>

<filter-mapping>
  <filter-name>filterC</filter-name>
  <url-pattern>/servletTwo</url-pattern>
</filter-mapping>
```

要尝试这样做：

1. 编译应用程序并从你的 IDE 启动 Tomcat。
2. 在浏览器中访问 `http://localhost:8080/filters/servletOne`。你可以在 IDE 的 Tomcat 标准输出中看到打印几条消息：

```
Entering FilterA.doFilter()
Entering ServletOne.doGet()
Leaving ServletOne.doGet()
Leaving FilterA.doFilter()
```

3. 将浏览器中的地址更改为 `/servletTwo` 并观察新的输出：

```
Entering FilterA.doFilter()
Entering FilterB.doFilter()
Entering FilterC.doFilter()
Entering ServletTwo.doGet()
Leaving ServletTwo.doGet()
Leaving FilterC.doFilter()
Leaving FilterB.doFilter()
Leaving FilterA.doFilter()
```

注意过滤器链是如何从 A 到 C 然后到 Servlet 进展的。然后在 Servlet 完成请求后，链以反向顺序从 C 到 A 退出。

4. 将浏览器中的地址更改为 `/servletThree`。它的输出应该像下面的代码一样。



```
Entering FilterA.doFilter()
Entering FilterB.doFilter()
Entering ServletThree.doGet()
Leaving ServletThree.doGet()
Leaving FilterB.doFilter()
Leaving FilterA.doFilter()
```

## 对映射进行任何你所想到的更改，看看它将如何影响过滤器链的执行。尝试将一个或多个 URL 映射更改为 Servlet 名称映射，并注意过滤器链的变化。

# 带有异步请求处理的过滤器

如前一节所述，适用于异步请求处理的过滤器在实现和配置上可能非常复杂。Servlet 方法的关键问题是它可以在响应发送到客户端之前就返回。请求处理随后可以委托给另一个线程或基于某些事件。

例如，服务方法（或者扩展的 `doGet`、`doPost`或其他方法）可以启动 `AsyncContext`，为某些假设的消息（例如收到的缓存）注册一个监听器，然后返回。当假设的监听器接收到消息时，它可以将响应发回用户。使用这种技术，请求在请求处理暂停时不会阻塞等待。拦截请求的过滤器会在响应实际返回（当 `FilterChain` 的 `doChain` 方法返回时）之前完成。

映射到 ASYNC 调度器的过滤器会拦截由于调用一次 `AsyncContext` 的 `dispatch` 方法而产生的请求。为了演示这种更复杂的过滤，请查看 wrox.com 代码上的 Filter-Async。它的 `AnyRequestFilter` 封装了请求和响应（将在下一节中进行探索），并打印任何类型的请求。如果它检测到 Servlet 启动了 `AsyncContext`，它会打印该信息并指示 `AsyncContext` 使用的是原始请求和响应还是封装后的请求和响应。

```java
public class AnyRequestFilter implements Filter
{
    private String name;

    @Override
    public void init(FilterConfig config)
    {
        this.name = config.getFilterName();
    }

    @Override
    public void doFilter(HTTPRequestRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException
{
    System.out.println("Entering " + this.name + " .doFilter()");
    chain.doFilter(
        new HttpServletRequestWrapper((HttpServletRequest) request),
        new HttpServletResponseWrapper((HttpServletResponse) response)
    );
    if (request.isAsyncSupported() && request.isAsyncStarted()) {
        AsyncContext context = request.getAsyncContext();
        System.out.println("Leaving " + this.name + " .doFilter(), async " + context.hasOriginalRequestAndResponse());
    } else {
        System.out.println("Leaving " + this.name + " .doFilter()");
    }

    @Override
    public void destroy() { }
}
```

## 正确排序你的过滤器

`start(Runnable)` 方法（使用 Java 8 方法引用）。使用此方法可以让容器使用其内部线程池运行 `Runnable`。你也可以简单地启动自己的线程，但使用容器的线程池是安全的并避免资源耗尽。

### 列表 9-1：AsyncServlet.java

```java
@WebServlet(name = "AsyncServlet", urlPatterns = "/async", asyncSupported = true)
public class AsyncServlet extends HttpServlet {

    private static volatile int ID = 1;

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        final int id;
        synchronized (AsyncServlet.class) {
            id = ID++;
        }
        long timeout = request.getParameter("timeout") == null ?
            1000L : Long.parseLong(request.getParameter("timeout"));

        System.out.println("Entering AsyncServlet.doGet(). Request ID = " + id +
            ", isAsyncStarted = " + request.isAsyncStarted());

        final AsyncContext context = request.getParameter("unwrap") != null ?
            request.startAsync() : request.startAsync(request, response);
            context.setTimeout(timeout);

        System.out.println("Starting asynchronous thread. Request ID = " + id +
            ", isAsyncStarted = " + request.isAsyncStarted());

        AsyncThread thread = new AsyncThread(id, context);
        context.start(thread::doWork);

        System.out.println("Leaving AsyncServlet.doGet(). Request ID = " + id +
            ", isAsyncStarted = " + request.isAsyncStarted());
    }

    private static class AsyncThread {
        private final int id;
        private final AsyncContext context;

        public AsyncThread(int id, AsyncContext context) { ... }

        public void doWork() {
            System.out.println("Asynchronous thread started. Request ID = " + +
                this.id + ".");
        }

    try {
```

### 列表 9-1（续）

```java
Thread.sleep(5_000L);
catch (Exception e) {
    e.printStackTrace();
}

HttpServletRequest request = =
    (HttpServletRequest)this.context.getRequest();
System.out.println("*Done sleeping. Request ID = " + this.id +
    ", URL = " + request.getRequestURL() + "*");\n
this.context.dispatch("/WEB-INF/jsp/view/async.jsp");

System.out.println("*Asynchronous thread completed. Request ID = " +
    this.id + "*");
}
}
```

## 现在实验一下 Servlet 和过滤器

1. 编译应用并为你的 IDE 启动 Tomcat；然后在大浏览器中访问 `http://localhost:8080/filters/regular`。你应该在调试器的输出窗口中看到以下内容。注意 `normalFilter` 拦截了对 Servlet 的请求，而 `forwardFilter` 拦截了转发到 JSP 的转发请求。

```
Entering normalFilter.doFilter()
Entering NonAsyncServlet.doGet()
Entering ForwardFilter.doFilter()
In nonAsync.jsp.
Leaving ForwardFilter.doFilter()
Leaving AsyncServlet.doGet()
Leaving normalFilter.doFilter()
```

2. 访问 `http://localhost:8080/filters/async`。立即出现以下调试器输出。注意 `normalFilter` 拦截了请求，但在响应实际发送之前完成了。

```
Enter normalFilter.doFilter()
Enter AsyncServlet.doGet(). Request ID = 1, isAsyncStarted = false
Starting asynchronous thread. Request ID = 1.
Leaving AsyncServlet.doGet(). Request ID = 1, isAsyncStarted = true
Leaving normalFilter.doFilter(), async context holds wrapped request/response=true
Asynchronous thread started. Request ID = 1.
```

等待 5 秒后，`AsyncThread` 内部类对用户做出响应，出现以下调试器输出。由于 `AsyncContext` 的 `dispatch` 方法，请求跳转到 JSP，`asyncFilter` 拦截了请求。

```
Done sleeping. Request ID = 1, URL = http://localhost:8080/filters/async.
Asynchronous thread completed. Request ID = 1.
```

## 过滤器的实际用法

```
Entering asyncFilter.doFilter()
In async.jsp.
Leaving asyncFilter.doFilter()
```

3. 访问 `http://localhost:8080/filters/async?timeout=3000`。出现以下调试器输出，并且在 5 秒后 `AsyncContext` 响应了用户。由于 `asyncFilter` 拦截了请求，请求跳转到 JSP。

```
Entering normalFilter.doFilter()
Request = 2, isAsyncStarted = false
Starting asynchronous thread.
AsyncServer.doGet(). Request ID = 2, isAsyncStarted = true
Leaving normalFilter.doFilter(), async context holds wrapped/response=true
```

4. 访问 `http://localhost:8080/filters/async=unwrap`。由于 `AsyncContext` 超时且已关闭，会出现 `IllegalStateException`。（注：此处原文逻辑似乎错乱，已根据上下文语境翻译）

## 正确排序你的过滤器

`start(Runnable)` 方法（使用 Java 8 方法引用）。使用此方法可以让容器使用其内部线程池运行 `Runnable`。你也可以简单地启动自己的线程，但使用容器的线程池是安全的并避免资源耗尽。

### 列表 9-1：AsyncServlet.java

```java
@WebServlet(name = "AsyncServlet", urlPatterns = "/async", asyncSupported = true)
public class AsyncServlet extends HttpServlet {

    private static volatile int ID = 1;

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        final int id;
        synchronized (AsyncServlet.class) {
            id = ID++;
        }
        long timeout = request.getParameter("timeout") == null ?
            1000L : Long.parseLong(request.getParameter("timeout"));

        System.out.println("Entering AsyncServlet.doGet(). Request ID = " + id +
            ", isAsyncStarted = " + request.isAsyncStarted());

        final AsyncContext context = request.getParameter("unwrap") != null ?
            request.startAsync() : request.startAsync(request, response);
            context.setTimeout(timeout);

        System.out.println("Starting asynchronous thread. Request ID = " + id +
            ", isAsyncStarted = " + request.isAsyncStarted());

        AsyncThread thread = new AsyncThread(id, context);
        context.start(thread::doWork);

        System.out.println("Leaving AsyncServlet.doGet(). Request ID = " + id +
            ", isAsyncStarted = " + request.isAsyncStarted());
    }

    private static class AsyncThread {
        private final int id;
        private final AsyncContext context;

        public AsyncThread(int id, AsyncContext context) { ... }

        public void doWork() {
            System.out.println("Asynchronous thread started. Request ID = " + +
                this.id + ".");
        }

    try {
```

### 列表 9-1（续）

```java
Thread.sleep(5_000L);
catch (Exception e) {
    e.printStackTrace();
}

HttpServletRequest request = =
    (HttpServletRequest)this.context.getRequest();
System.out.println("*Done sleeping. Request ID = " + this.id +
    ", URL = " + request.getRequestURL() + "*");\n
this.context.dispatch("/WEB-INF/jsp/view/async.jsp");

System.out.println("*Asynchronous thread completed. Request ID = " +
    this.id + "*");
}
}
```

## 现在实验一下 Servlet 和过滤器



- 1. 编译应用并为你的 IDE 启动 Tomcat；然后在大浏览器中访问 `http://localhost:8080/filters/regular`。你应该在调试器的输出窗口中看到以下内容。注意 `normalFilter` 拦截了对 Servlet 的请求，而 `forwardFilter` 拦截了转发到 JSP 的转发请求。

```
Entering normalFilter.doFilter().
EnteringNonAsyncServlet.doGet().
EnteringForwardFilter.doFilter().
In nonAsync.jsp.
LeavingforwardFilter.doFilter().
LeavingAsyncServlet.doGet().
LeavingnormalFilter.doFilter().
```

- 2. 访问 `http://localhost:8080/filters/async`。立即出现以下调试器输出。注意 `normalFilter` 拦截了请求，但在响应实际发送之前完成了。

```
EnternormalFilter.doFilter().
EnterAsyncServlet.doGet(). Request ID = 1, isAsyncStarted = false
Starting asynchronous thread. Request ID = 1.
LeavingAsyncServlet.doGet(). Request ID = 1, isAsyncStarted = true
LeavingnormalFilter.doFilter(), async context holds wrapped request/response=true
Asynchronous thread started. Request ID = 1.
```

等待 5 秒后，`AsyncThread` 内部类对用户做出响应，出现以下调试器输出。由于 `AsyncContext` 的 `dispatch` 方法，请求跳转到 JSP，`asyncFilter` 拦截了请求。

```
Done sleeping. Request ID = 1, URL = http://localhost:8080/filters/async.
Asynchronous thread completed. Request ID = 1.
Entering asyncFilter.doFilter().
In async.jsp.
Leaving asyncFilter.doFilter().
```

- 3. 访问 `http://localhost:8080/filters/async?timeout=3000`。出现以下调试器输出，并且在 5 秒后 `AsyncContext` 响应了用户。由于 `asyncFilter` 拦截了请求，请求跳转到 JSP。

```
Entering normalFilter.doFilter().
Request = 2, isAsyncStarted = false
Starting asynchronous thread.
AsyncServer.doGet(). Request ID = 2, isAsyncStarted = true
LeavingnormalFilter.doFilter(), async context holds wrapped/response=true
```

- 4. 访问 `http://localhost:8080/filters/async=unwrap`。由于 `AsyncContext` 超时且已关闭，会出现 `IllegalStateException`。（注：此处原文逻辑似乎错乱，已根据上下文语境翻译）

```java
System.out.println(in.getRemoteAddr() + " - " + "[" + time + "] " +
    "\" " + in.getMethod() + " " + in.getRequestURI() + " " +
    "\" " + in.getProtocol() + " \" " + out.getStatus() + " " + length +
    " \" " + timer);

@Override
public void init(FilterConfig filterConfig) throws ServletException {
}

@Override
public void destroy() {
}
```

> 注意：`RequestLogFilter` 在异步请求处理时将无法正常工作。如果 Servlet 拥有 `AsyncContext`，`doFilter` 将在响应发送之前返回，这意味着过滤器将记录不完整或错误的信息。要让此过滤器在异步请求中正常工作是一项重大且复杂的任务，留给读者自行考虑。

## 使用过滤器处理响应内容

列表 9-3 中的 `CompressionFilter` 比 `RequestLogFilter` 复杂得多。在考虑压缩响应时，你可能会认为应该排除该过滤器，然后在返回的路径上执行压缩逻辑。然而，请记住，响应数据可能在 Servlet 完成请求处理之前就开始回流到客户端。在异步请求处理的情况下，也可能开始流向客户端。如果你想修改响应，必须封装向下传递的响应对象。`CompressionFilter` 正是这样做的。

花几分钟阅读代码并检查 `CompressionFilter` 正在做什么。首先，它检查客户端是否具有包含 "gzip" 编码的 `Accept-Encoding` 请求头。这是一个非常重要的检查，因为如果没有，客户端可能无法理解 gzip 压缩的响应。如果有，它会将 `Content-Encoding` 头部设置为 "gzip"，然后用私有内部类 `ResponseWrapper` 的实例来包装响应。该类反过来通过私有类 `GZIPServletOutputStream` 封装发送数据到客户端的 `PrintWriter` 或 `ServletOutputStream`。此包装器包含一个内部的 `java.util.zip.GZIPOutputStream`。响应数据首先写入 `GZIPOutputStream`，当请求完成时，它完成压缩并将压缩后的响应写入被包装的 `ServletOutputStream` 中。`ResponseWrapper` 还防止了任何 Servlet 代码为响应设置 `content-length` 头部，因为在响应压缩之前无法知道内容长度。

### 列表 9-3：CompressionFilter.java

```java
public class CompressionFilter implements Filter {
    @Override
    public void doFilter(ServletRequest request, HttpServletResponse response, FilterChain chain) throws IOException, ServletException {
        if (((HttpServletRequest)request).getHeader("Accept-Encoding").contains("zip")) {
            System.out.println("Encoding requested.");
            ((HttpServletResponse)response).setHeader("Content-Encoding", "zip");
            ResponseWrapper wrapper = new ResponseWrapper((HttpServletResponse)response);
            try {
                chain.doFilter(request, wrapper);
            } finally {
                wrapper.finish();
            } catch (Exception e) {
                e.printStackTrace();
            }
        } else {
            System.out.println("Encoding not requested.");
            chain.doFilter(request, response);
        }
    }

    @Override
    public void init(FilterConfig filterConfig) throws ServletException {}

    @Override
    public void destroy() { }

    private static class ResponseWrapper extends HttpServletResponseWrapper {
        private GZIPServletOutputStream outputStream;
        private PrintWriter writer;

        public ResponseWrapper(HttpServletResponse request) {
            super(request);
        }

        @Override
        public synchronized ServletOutputStream getOutputStream() throws IOException {
            if (writer != null) {
                throw new IllegalStateException("getWriter() called.");
            }
            if (outputStream == null) {
                outputStream = new GZIPServletOutputStream(super.getOutputStream());
            }
            return outputStream;
        }

        public synchronized PrintWriter getWriter() throws IOException {
            if (writer == null && outputStream != null) {
                throw new IllegalStateException("getOutputStream() called.");
            }
            if (writer == null) {
                outputStream = new GZIPOutputStream(super.getOutputStream());
                writer = new PrintWriter(new OutputStreamWriter(outputStream, getCharacterEncoding()));
            }
            return writer;
        }

        @Override
        public void flushBuffer() throws IOException {
            if (writer == null) {
                writer.flush();
            } else if (outputStream != null) {
                outputStream.flush();
            }
            super.flushBuffer();
        }

        @Override
        public void setContentLength(int length) { }

        @Override
        public void setContentLength(long length) { }

        @Override
        public void setHeader(String name, String value) {
            if (!"content-length".equalsIgnoreCase(name)) {
                super.setHeader(name, value);
            }
        }

        @Override
        public void addHeader(String name, String value) {
            if (!"content-length".equalsIgnoreCase(name)) {
                super.setHeader(name, value);
            }
        }

        @Override
        public void setIntHeader(String name, int value) {
            if (!"content-length".equalsIgnoreCase(name)) {
                super.addHeader(name, value);
            }
        }

        @Override
        public void addIntHeader(String name, int value) {
            if (!"content-length".equalsIgnoreCase(name)) {
                super.addHeader(name, value);
            }
        }

        public void finish() throws IOException {
            if (writer == null) {
                writer.flush();
            } else if (outputStream != null) {
                outputStream.flush();
            }
        }

        private static class GZIPServletOutputStream extends ServletOutputStream {
            private final ServletOutputStream outputStream;
            private final GZIPOutputStream gzipStream;

            public GZIPServletOutputStream(ServletOutputStream outputStream) throws IOException {
                this.outputStream = outputStream;
                this.gzipStream = new GZIPOutputStream(outputStream);
            }

            @Override
            public boolean isReady() {
                return this.outputStream.isReady();
            }

            @Override
            public void setWriteListener(WriteListener writeListener) {
                this.outputStream.setWriteListener(writeListener);
            }

            @Override
            public void write(int b) throws IOException {
                this.gzipStream.write(b);
            }

            @Override
            public void close() throws IOException {
                this.gzipStream.close();
            }

            @Override
            public void flush() throws IOException {
                this.gzipStream.flush();
            }

            public void finish() throws IOException {
                this.gzipStream.finish();
            }
        }
    }
}
```

包装模式是一种非常常见的模式，你可能会在很多过滤器中看到它的应用。请求和响应对象都可以被包装；然而，封装响应通常更为常见。封装响应允许你拦截对包装响应的任何方法调用，从而实现修改响应数据的能力。你也可以使用与 9-3 类似的过滤器来加密响应数据而非压缩。请求对象可以被封装以解密其内容。

尝试日志和压缩过滤器：

- 1. 编译你的应用程序并从 IDE 启动 Tomcat。
- 2. 在浏览器中访问 `http://localhost:8080/compression/` 和 `http://localhost:8080/compression/servlet`。
- 3. 使用浏览器的开发者工具开始监控应用程序请求和响应的头部。（Microsoft Explorer 和 Google Chrome 内置了可以实现此功能的开发者工具，Mozilla Firefox 的 Firebug 插件也具有此功能。）你应该能在图 9-4 中看到那样的一行。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_288_0.png)

## 图 9-4

注意 `Accept-Encoding` 请求头部包含 "gzip" 编码，而 `Content-Encoding` 响应头部的值 "gzip"。这意味着你的浏览器正在宣布它可以接受 gzip 编码的响应，而压缩过滤器正在顺应请求并在响应数据发送到浏览器之前对其压缩。

# 使用过滤器简化身份验证



在 Web 应用中，过滤器的一个关键用途是保护应用程序免受不受授权的访问。你为跨国 Widget 公司开发的客户支持应用程序使用非常原始的身份验证机制来保护其页面。你可能已经注意到应用程序中的许多地方都包含相同的重复代码来检查身份验证：

```java
if (request.getSession().getAttribute("username") == null) {
    response.sendRedirect("*login");
    return;
}
```

在某个时刻，你可能会认为更好的解决方案是在某个类上创建一个静态方法来执行此检查并调用它。这确实减少了代码，但仍然导致在多个地方执行该方法。随着你应用程序中 Servlet 数量的增加，对该静态方法的调用次数也会随之增加。

在学习了本章内容后，这里应该是放置这段代码更好的地方。wrox 代码下载中的 Customer-Support-v7 项目通过将此代码添加到 `Configuration` 监听器类和 `AuthenticationFilter` 类中演示了这一点。`TicketServlet` 中的 `doGet` 和 `doPost` 方法已删除了之前的代码段。配置非常简单：它声明了 `AuthenticationFilter` 并将其映射到 `/tickets` 和 `/sessions`。

```java
@WebListener
public class Configurator implements ServletContextListener {
    @Override
    public void contextInitialized(ServletContext event) {
        ServletContext context = event.getServletContext();

        FilterRegistration.Dynamic registration = context.addFilter("authenticationFilter", new AuthenticationFilter());
        registration.setAsyncSupported(true);
        registration.addMappingForUrlPatterns(null, null, false, "*/sessions", "*/tickets");
    }

    @Override
    public void contextDestroyed(ServletContext event) { }
}
```

当你向应用程序添加更多 Servlet 或受保护资源（如 JSP）时，你只需要将它们的 URL 模式添加到过滤器注册中，以确保用户在访问这些资源之前已登录。当然，这个过滤器并不保护登录 Servlet，因为你不想保护登录屏幕。你也不需要保护任何 CSS、JavaScript 或图像资源，因为它们不包含敏感数据。`AuthenticationFilter` 对任何 HTTP 方法的每个请求执行身份验证检查，如果用户未登录，则将用户重定向到登录屏幕：

```java
public class AuthenticationFilter implements Filter {
    @Override
    public void doFilter(ServletRequest request, HttpServletResponse response, FilterChain chain) throws IOException, ServletException {
        HttpSession session = ((HttpServletRequest)request).getSession(false);
        if (session != null && session.getAttribute("username") == null) {
            ((HttpServletResponse) response).sendRedirect("login");
        } else {
            chain.doFilter(request, response);
        }
    }

    @Override
    public void init(FilterConfig config) throws ServletException { }

    @Override
    public void destroy() { }
}
```

这样做非常美好的一点是，如果你更改了身份验证算法，只需要更改过滤器即可继续保护应用程序中的资源。以前，你必须对每个 Servlet 进行更改。通过编译、在你的 IDE 中启动 Tomcat 并在浏览器中导航到 `http://localhost:8080/support` 来测试这些更改。尽管所有 Servlet 中都删除了身份验证检查，但在查看或创建工单、或查看会话列表之前，你仍然会被要求登录。

### 总结

在本章中，你探索了过滤器的用途以及你可能使用它们的原因。你学习了 `Filter` 接口以及如何在应用程序中创建、声明和映射过滤器。你实验了至关重要的过滤器链，以及在某些场景和许多其他场景下过滤器执行顺序为什么是重要的。你被引入了异步请求处理的概念，并使用过滤器进一步探索了这一点，理解了异步请求处理可能有多棘手。最后，在探索了声明和映射过滤器的三种不同方式（在部署描述符中、使用注解和通过编程方式）后，你实验了日志过滤器、响应压缩过滤器和身份验证过滤器。

在下一章中，你将探索 WebSockets 技术、它们如何极大提高交互式 Web 应用，以及如何在 Java 和 JavaScript 中使用它们。一个有趣的点是，Tomcat 中使 WebSocket 可行的代码实际上使用过滤器来拦截你应用程序中所有绑定 WebSocket 的请求，并将它们发送到你的 WebSocket 端点（你将在下一章中学习更多）。因此，即使你什么都不做，你的应用程序已经有了过滤器在检查并在必要时修改请求。

# 10 使用 WebSockets 让你的应用程序具有交互

## 本章内容

- Ajax 如何演变为 WebSockets
- 关于 WebSocket API 的讨论
- 使用 WebSockets 创建多人游戏
- 在集群中通过 WebSockets 进行通信
- 如何在 Web 应用程序中添加聊天功能

## 本章的 WROX.COM 下载

你可以在 `http://www.wrox.com/` 找到本章的 wrox.com 下载。本章的代码被分为以下几个主要示例：

- Game-Site 项目
- Simulated-Cluster 项目
- Customer-Support-v7 项目

## 本章的新 MAVEN 依赖

除了在前几节中引入的 Maven 之外，你还需要以下内容：

```xml
<dependency>
    <groupId>javax.websocket</groupId>
    <artifactId>websocket-api</artifactId>
    <version>1.0</version>
    <scope>provided</scope>
</dependency>
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang</artifactId>
    <version>3.1</version>
    <scope>compile</scope>
</dependency>
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>2.0</version>
    <scope>compile</scope>
</dependency>
<!-- （此处省略部分依赖） -->
```

*(注：由于原文文本在依赖处截断，以下翻译基于提供的截断内容)*

# 演变：从 AJAX 到 WebSockets

在最初，HTML 是不够的。用户想要可以交互的页面。这个答案是 JavaScript。在 JavaScript 早期，浏览器之间几乎没有标准（早期只有一个浏览器支持），而且非常缓慢且不安全。多年来，在速度、安全能力方面有了显著改进。有了许多 JavaScript 框架，现在可以创建极其丰富的单页应用程序。这项创新的最大驱动力是 Ajax。

# 问题：从服务器向浏览器获取新数据

Ajax（异步 JavaScript XML 的缩写）已成为使用 JavaScript 与远程服务器异步通信的代名词。它并不强制要求使用 XML（正如名称所暗示的相反，通常使用 JSON）。通过 Ajax，浏览器现在可以在不刷新的情况下与服务器通信。然而，问题的核心在于：浏览器不知道何时有新数据。服务器知道有新数据要发送，例如当两个用户在 Web 应用程序中聊天时，用户 B 的浏览器在联系服务器之前不知道。有了 Ajax 这种技术，这是一个很难解决的问题。

过去的 14 年里，出现了许多解决方案，其中一些被广泛支持，而另一些是特定于浏览器的。本书没有涵盖所有方案，那样也没有用。然而，有四种方法作为各种解决方案的基础，理解它们及其缺点对于理解为什么需要更好的方案至关重要。

> 使用 JavaScript 请求 Ajax 的实际细节对于本章的讨论并不重要，也不属于本书范围。如果你不熟悉这个主题，网上有成千上万的 Ajax 教程。

## 方案 1：频繁轮询

解决此问题的流行方法之一是轮询服务器获取新数据。概念非常简单：定期（通常每秒一次）浏览器向服务器发送 Ajax 请求以获取新数据。如果服务器有新的数据给浏览器，则返回数据；如果没有，则不返回内容。这可能意味着一个空 JSON 对象或 XML 文档，或者 `Content-Length` Header 为 0。这种协议看起来就像图 10-1 所示的四个请求，只不过请求和响应多得多。

这种协议的缺点是巨大而显见的：会产生大量的无用请求。注意图中的第二个和第三个请求没有任何成就！加上建立连接、发送和接收头部以及销毁连接的开销，为了发现服务器没有给浏览器的新数据，浪费了大量的处理和网络资源。尽管由于实现非常简单，这种技术仍然被广泛使用，但很早就很清楚它不是解决此问题的良好方案。

## 方案 2：长轮询

图 10-2 所示的长轮询与频繁轮询类似，不同之处在于服务器会一直保持连接打开，直到有数据要发送回浏览器才返回。这种方法更高效，因为浪费的计算和网络资源较少，但它也带来了一些自身的问题：

- 如果在服务器响应之前，浏览器有新数据要发送给服务器怎么办？浏览器必须要么发送一个单独请求，要么终止当前请求（服务器必须优雅地恢复）并开始另一个请求。
- 连接超时是内置在 TCP 和 HTTP 规范中的。由于各种原因，服务器和客户端必须定期关闭并重新建立连接。有时连接每隔 60 秒就会关闭一次，尽管某些实现已成功保持了连接几分钟。
- HTTP/1.1 规范中存在连接限制规定。浏览器必须允许对任何给定主机名的同时连接数不超过两个。如果一个连接一直由于等待服务器推送数据而被占用，它将导致从服务器获取网页、图形和其他资源的连接数量减少一半。

尽管存在这些问题，这仍然是一种在过去几年中获得广泛使用的流行方法，并且通常被统称为 Comet（彗星，这是对 Ajax 的一种双关游戏，因为这两个名字都可以指代清洁产品）。

## 方案 3：分块编码

与长轮询方案非常相似，分块编码利用了 HTTP/1.1 的一项功能，允许服务器在不声明内容长度的情况下响应请求。响应可以包含 `Transfer-Encoding: chunked` 头部来代替 `Content-Length` 头部。这告诉浏览器响应正在按“块”传输。在响应中，每个分块以一个指示分块长度的数字开始，后面是一个表示分块扩展的可选字符（与本文讨论无关），以及一个 CRLF（回车—换行）序列。随后是该分块包含的数据以及另一个 CRLF。之后可以跟随任意数量的分块，它们之间可以间隔任何时间，无论长短。当发送一个零长度的分块（一个 0 后跟两个 CRLF）时，这表示响应的结束。

你通常使用分块来解决问题的方法是首先打开一个连接以接收来自服务器的事件。服务器的每个分块都是一个新事件，并触发 JavaScript `XMLHttpRequest` 对象的 `onreadystatechange` 事件处理程序。偶尔（虽然没有长轮询那样频繁）连接也必须刷新。当浏览器需要向服务器发送新数据时，它会通过第二个短生存请求发送。

该协议在图 10-3 所示。在左侧，浏览器在需要时使用短生存请求将新数据发送到“上游端点”。在右侧，服务器通过分块向“下游端点”发送数据。分块编码解决了浏览器等待服务器推送数据导致的长时问题（如长轮询），但它仍然无法解决浏览器向服务器发送新数据的问题。分块编码允许了双向传输的通信，但这种连接本身是不安全的。

## 方案 4：插件

在早期，这种方法被广泛用于实现长轮询的实现向通信，但它仍然在 HTTP/1.1 规范中受到限制。简单来说，就是使用插件来实现双向通信，如图 10-4 所示。然而，这种方法在浏览器中并不流行，因为它需要安装插件。

## WebSockets：一个未知的解决方案

## WebSocket 协议构建在 HTTP/1.1 之上

如图 10-5 所示，WebSocket 连接始于一个针对特殊方案 URL 的普通 HTTP 请求。URI 方案 `ws` 和 `wss` 分别对应其 HTTP 的 `http` 和 `https`。`Connection: Upgrade` 头与 `Upgrade: websocket` 头同时出现，指示服务器将连接升级为 WebSocket 协议。这是一个在 2011 年通过 RFC 6455 标准化的持久、全双工通信协议。握手完成后，文本和二进制消息可以在两个方向同时发送，而无需关闭并重新建立连接。此时，客户端和服务器之间本质上没有区别——它们对连接具有对等的能力和权限，仅仅是对等节点。

> 注意：`ws` 和 `wss` 方案并非 HTTP 协议严格的一部分，因为 HTTP 请求和请求头实际上并不包含 URI 方案。相反，HTTP 请求仅在请求的第一行中包含相对于服务器的 URL，并在 `Host` 请求头中包含域名。专门的 WebSocket 方案主要用于告知浏览器和 API 你是打算使用 SSL/TLS (`wss`) 还是不使用加密 (`ws`) 进行连接。

WebSocket 协议的实现具有许多优势：

- 因为建立在 80 (`ws`) 或 443 (`wss`) 端口上，由于使用了与 HTTP 相同的端口，几乎没有防火墙会拦截 WebSocket 连接。
- 该协议自然地集成到浏览器和 HTTP 服务器中，因为握手是通过 HTTP 进行的。
- 往返发送名为 `ping` 和 `pong` 的心跳消息可以保持 WebSocket 连接几乎无限期持续。本质上，一方定期地向另一方发送一个微型数据包 (`ping`)，另一个响应一个包含相同数据的数据包 (`pong`)。这确保了两个对等节点仍然保持连接。
- 消息会代表你进行帧处理（framed），无需额外的代码，这样服务器和客户端就知道消息何时开始以及所有内容何时到达。
- 关闭 WebSocket 连接涉及一条特殊消息，该消息可以包含原因代码并解释为何关闭连接。
- WebSocket 协议安全地允许跨域连接，消除了对 Ajax 和 `XMLHttpRequest` 请求的限制。
- HTTP 规范中限制每个主机名仅允许两个连接的规定在握手完成后不再适用，因为连接已不再是 HTTP 连接。

WebSocket 连接中的握手请求头非常简单。一个典型的 WebSocket 升级请求在 Wireshark 或 Fiddler 等流量分析器中可能如下：



## HTTP 握手请求示例

```
GET /websocketEndpoint HTTP/1.1
Host: www.example.com
Connection: Upgrade
Upgrade: websocket
Origin: http://example.com
Sec-WebSocket-Key: xJ3HMDL1LeXh9GBXdw==
Sec-WebSocket-Version: 13
Sec-WebSocket-Protocol: game
```

你应该熟悉 HTTP 序言（`GET /websocketEndpoint HTTP/1.1`）和 `Host` 头。此外，`Connection` 和 `Upgrade` 头之前已经解释过。`Origin` 头是一种防止不受欢迎跨域请求的机制。浏览器会将此头设置为提供页面的域名，服务器会根据“已批准”域名列表对其进行检查。

`Sec-WebSocket-Key` 头是一个握手确认：浏览器生成一个随机密钥，对其进行 base64 编码，并放入请求头。服务器返回 `258EAE5-E914-47DA-95CA-C5AB0DC85B11` 作为值，对其进行 SHA-1 哈希处理，并将哈希值 base64 编码后返回在 `Sec-WebSocket-Accept` 响应头中。`Sec-WebSocket-Version` 表示客户端实现的协议版本，而 `Sec-WebSocket-Protocol` 是一个可选头，表示在 WebSocket 协议之上使用的协议。（这是你定义的协议，如聊天、游戏或股票行情。）以下是对上一个请求的响应示例：

## HTTP 握手响应示例

```
HTTP/1.1 101 Switching Protocols
Server: Apache 2.4
Connection: Upgrade
Upgrade: websocket
Sec-WebSocket-Accept: HSmrc0sM1YkAgmm50PPg2HaGWk=
Sec-WebSocket-Protocol: game
```

此时，HTTP 连接消失，并被一个使用底层 TCP 连接的 WebSocket 连接所取代。该连接成功的最大障碍是 HTTP 代理，从历史上看，它们并不能很好处理 HTTP Upgrade 请求（同样，对于整个 HTTP 流量也是如此）。浏览器通常尝试检测连接是否通过代理进行，并在握手之前使用 `HTTP CONNECT`，但这并不总是有效。使用 WebSockets 最可靠的方法是始终使用 SSL/TLS (wss)。通过这种策略，你的 WebSocket SSL/TLS 连接本身只需要完成一件事，而且你的 WebSocket 连接可以在几乎所有情况下工作。它也是安全的：流量在两个方向上使用与 HTTPS 相同的行业测试安全标准进行加密。

所有这些细节——升级、头部、协议、帧以及二进制和文本消息——听起来很复杂，但好消息是你不需要担心其中任何内容。有几个 API 涵盖了协议的所有困难任务。

## 理解 WebSocket API

关于 WebSocket 你应该理解的一点是，它们不仅用于浏览器和服务器之间的通信。任何支持 WebSocket 的框架编写的应用程序在理论上都可以通过 WebSocket 建立通信。因此，许多 WebSocket 实现都包含客户端和服务器端工具。这在 Java 和 .NET 中都是如此。然而，JavaScript 仅用于 WebSocket 的客户端端。在本节中，你首先学习 JavaScript 客户端端，然后转向 Java 服务器端。

> 当本书提到 JavaScript 能力时，仅指由浏览器实现的 JavaScript。某些 JavaScript 框架（如 Node.js）可以运行在浏览器环境之外，并提供本书中未讨论的额外功能（包括 WebSocket 服务器）。学习这些框架超出了本书的范围。

## WebSocket 的多种用途

WebSocket 协议的用途几乎无限，大部分包括浏览器应用程序，但也存在于浏览器之外。在本章中你会看到这两类的示例。尽管本书无法列出所有用途，以下是 WebSocket 用途的一角：

- JavaScript 聊天
- 多人在线游戏（Mozilla 托管了一个完全使用 HTML5 和 JavaScript 使用 WebSocket 编写的有趣的 MMOG：BrowserQuest。）
- 实时行情
- 实时新闻滚动
- 高清视频流（是的，信不信，它就是如此快速强大。）
- 应用程序集群中节点之间的通信
- 应用程序之间的批量数据传输
- 远程系统或软件状态的实时监控

## HTML5 (JavaScript) 客户端 API

如之前所述，所有现代浏览器都提供 WebSocket 支持，这种支持在浏览器之间是标准化的。世界网联盟（W3C）将浏览器内 WebSocket 通信的要求和接口作为 HTML5 的扩展正式化。尽管你使用 JavaScript 执行 WebSocket 通信，但 WebSocket 接口实际上是 HTML5 的一部分。所有浏览器都通过 `WebSocket` 接口的实现。（如果你还记得 Ajax 的早期时代，不同的浏览器在执行 Ajax 请求时有不同的类和函数，那么这将会让你感到意外的惊喜。）

### 创建 WebSocket 对象

创建一个 WebSocket 对象非常简单：

```
var connection = new WebSocket('ws://www.example.net/stocks/stream');
var connection = new WebSocket('ws://secure.example.org/games/chess');
var connection = new WebSocket('ws://www.example.com/chat', 'chat');
var connection = new WebSocket('ws://www.example.com/chat', 'chat.v1','chat.v2');
```

`WebSocket` 构造函数的第一个参数是您想要连接的 WebSocket 服务器的 URL。可选参数可以是字符串或字符串数组，用于定义您想要接受的一个或多个客户端自定义协议。请记住，这些协议是由您自己实现的，并不由 WebSocket 技术管理。该参数仅为在您需要传递信息时提供了一种机制。

### 使用 WebSocket 对象

`WebSocket` 接口中有几个属性。第一个属性 `readyState` 指明 WebSocket 连接的当前状态。它的值可以是 `connecting`（数字 0）、`OPEN`（1）、`CLOSING`（2）或 `CLOSED`（3）。

```
if(connection.readyState == WebSocket.OPEN) { /* do something */ }
```

它主要用于内部；但是，为了确保在连接未打开时不发送消息是有用的。与 `XMLHttpRequest` 不同，WebSocket 没有在发生任何类型的事件时都会触发的 `onreadyState` 事件，但 WebSocket 有四个独立的事件，代表 WebSocket 可能发生的四种不同情况：

```
connection.onopen = function(event) {}
connection.onclose = function(event) {}
connection.onerror = function(event) {}
connection.onmessage = function(event) {
```

事件名称清楚地指示了这些事件的触发时机。重要的是，`onopen` 事件在 `readyState` 从 `CONNECTING` 变为 `OPEN` 时被触发，此时只读的 `url`、`extensions`（服务器提供的扩展）和 `protocol`（服务器端协议）属性已设置并固定。在 `onopen` 中创建的事件对象是一个 JavaScript `Event`，其中没有特别有趣的内容。然而，传递给 `onclose` 的事件具有三个有用的属性：`wasClean`、`code` 和 `reason`。你可以使用这些属性向用户报告状态：

```
connection.onclose = function(event) {
  if (event.wasClean) {
    alert(event.code + ' : ' + event.reason);
  }
}
```

本地关闭代码定义了 RFC 6455 第 7.4 节（http://tools.ietf.org/html/rfc6455#section-7.4）中的代码。代码 1000 是正常的，所有其他代码都是异常的。`onerror` 事件包含一个包含错误对象的 `data` 属性，它可以是任何内容（通常是字符串消息）。此事件仅在客户端错误时触发；协议错误会导致连接关闭。`onmessage` 是你必须小心处理的事件处理器。它也包含一个 `data` 属性。如果消息是文本，该属性为字符串；如果消息是二进制消息且 WebSocket 的 `binaryType` 设置为 "blob"（默认），则为 `Blob`；如果消息是二进制消息且 `binaryType` 设置为 "arraybuffer"，则为 `ArrayBuffer`。你通常应该在初始化 WebSocket 对象后立即设置 `binaryType` 并在连接剩余时间内保持不变；但是，需要时更改该值也是合法的。

```
var connection = new WebSocket('ws://www.example.net/chat');
connection.binaryType = 'arraybuffer';
...
```

`WebSocket` 对象有两个方法：`send()` 和 `close()`。`close()` 方法接受一个可选的关闭代码作为第一个参数（默认 1000），接受一个可选的扩展原因作为第二个参数（默认为空）。`send()` 方法接受字符串、`Blob`、`ArrayBuffer` 或 `ArrayView` 作为参数，你可能会在这里使用 WebSocket 接口的 `bufferedAmount` 属性。`bufferedAmount` 指明有多少数据仍在等待发送到服务器。即使有数据等待发送，你也可以继续发送数据，你可能只想在没有数据等待时才向服务器推送新数据：

```
connection.onopen = function() {
  var intervalId = window.setInterval(function() {
    if(connection.readyState != WebSocket.OPEN) {
      clearInterval(intervalId);
      return;
    }
  }, 50);
}
```

## Java WebSocket API

Java 的 WebSocket API 规范的是 API，而不是实现。你可以编写此 API，但在运行时你需要一个实现来支持它。如果你的应用程序运行在 Java EE 服务器或支持 WebSocket 的 Web 服务器上，已经提供了客户端和服务器实现。如果是独立运行，你需要找到一个独立的客户端或服务器实现（取决于你的需求）并随程序部署。

### 客户端 API

客户端 API 构建在 `ContainerProvider` 以及 `WebSocketContainer`、`RemoteEndpoint` 和 `Session` 接口之上。`WebSocketContainer` 提供所有的 WebSocket 功能，`ContainerProvider` 类提供了一个静态 `getWebSocketContainer()` 方法来获取 WebSocket 实现。`WebSocketContainer` 提供了重载的 `connectToServer()` 方法，接受 URI 以连接远程端点并启动握手。这些方法接受带有 `@ClientEndpoint` 注解的任意类型的 POJO 实例、`Endpoint` 类的 `Class` 或 `Class<? extends Endpoint>`。如果你使用任何类类型的方法，你还必须提供一个无参数构造函数，并在你的处理程序上实例化。

如果你使用 `Endpoint` 或 `Class<? extends Endpoint>` 方法，你还必须提供 `ClientEndpointConfig`。握手完成后，`connectToServer()` 方法返回一个 `Session`。你可以对 `Session` 对象进行许多操作，最著名的是关闭 `Session`（关闭 WebSocket 连接）或向远程端发送消息。

WebSocket Endpoint 拥有 `onOpen()`、`onClose()` 和 `onError()` 方法在这些事件发生时被调用，而 `@ClientEndpoint` 类可以拥有带有 `@OnOpen`、`@OnClose` 和 `@OnError` 注解的可用方法。`@ClientEndpoint` 类和扩展 `Endpoint` 的类可以指定一个或带有 `@OnMessage` 注解的方法来处理来自远程端的消息。使用注解类和方法，你在使用什么方法上具有很大的灵活性。

`@OnMessage` 方法更为复杂。除了标准的可选 `Session` 参数外，它们必须恰恰好包含以下参数组合之一：

- 一个 `String`：用于接收整个文本消息
- 一个 `String` 加上一个 `boolean`：分块接收文本消息，布尔值在最后一个分块时设置为 true
- 一个 Java 原始类型或原始类型包装类：用于接收转换为该类型的整个文本消息
- 一个 `java.io.Reader`：作为阻塞流接收文本消息
- 一个 `byte[]` 或一个 `ByteBuffer`，加上一个 `boolean`：分块接收二进制消息
- 一个 `java.io.InputStream`：作为阻塞流接收二进制消息
- 只要端点注册了用于转换该类型的 `Decoder.Text`、`Decoder.Binary`、`Decoder.TextStream` 或 `Decoder.BinaryStream`，任何对象均可。文本或二进制消息类型必须与注册的解码器匹配。

一个端点只能有一个方法来处理打开、关闭和错误事件；然而，它最多可以有三种消息处理模式：文本消息不超过一个，二进制消息不超过一个，pong 不超过一个。本章使用的 WebSocket 依赖是用于服务器 API，它包含了对客户端 API 的依赖。如果你需要编写仅作为 WebSocket 客户端的 Java 应用，你需要客户端 API 依赖：

```
<dependency>
  <groupId>javax.websocket</groupId>
  <artifactId>javax.websocket-client-api</artifactId>
  <version>1.0</version>
  <scope>provided</scope>
</dependency>
```

### 服务器 API

服务器 API 依赖于整个客户端 API，并增加了方法用于以程序化的方式注册 `ServerEndpoint` 类或带有 `@ServerEndpoint` 注解的类。在 Servlet 环境中，你通过调用 `ServletContext.getAttribute("javax.websocket.server.ServerContainer")` 获取 `ServerContainer`。你需要遵循你所使用的特定 WebSocket 实现的说明来获取 `ServerContainer` 实例。

然而，在几乎所有情况下（包括所有用户的 Java EE Web Bean），你实际上并不需要获取 `ServerContainer`。相反，只需为你的端点类或类标记上 `@ServerEndpoint` 注解；WebSocket 实现可以扫描你的类以寻找此注解，并自动为你选择和注册你的服务器端点。容器会创建你的端点类的新实例，为该端点接收新的 WebSocket 连接，并在每个连接关闭后关闭每个实例。

使用 `@ServerEndpoint` 时，你至少需要指定所需的 `value` 属性，它指示了端点响应的应用程序相对 URL。URL 路径必须以斜杠开头，并可以包含模板。例如，考虑以下注解：

```
@ServerEndpoint("/game/{gameType}")
```

如果你的应用部署在 `http[s]://www.example.org/app/game/chess`

> 注意：由于 WebSocket 协议的首要目的是服务器与浏览器之间的通信，因此本章包含了大量的 JavaScript 代码。其中部分代码大量使用了 jQuery 库。如果详细介绍 Web 端 JavaScript 编程，这本书将会增加几百页，因此假设你已经拥有 JavaScript 和 jQuery（用于编写更简单、更短的示例）的基础知识。如果你不熟悉 JavaScript 和 jQuery，建议你停下来去找一本 JavaScript 和 jQuery 的书籍或教程。否则，某些代码可能难以理解。

## 使用 WebSockets 创建多人游戏

你之前提到过 WebSocket 能够促进多人在线游戏，即大型多人在线游戏（MMORPGs）的通信。在本节中，你将创建一个简单的多人游戏来演示 WebSocket 的强大。多人游戏的关键在于响应性：当玩家采取行动时，他的对手必须尽快看到该动作。这对于战斗和动作序列尤为关键，因为对手之间必须进行实时竞争。



# 实现基础井字棋算法

在线井字棋可以与人类或电脑对战。当你包含电脑对战时，算法会变得非常复杂，因为你必须实现一些超出本书范围的人工智能算法。此外，那样演示 WebSocket 的效果并不好。相反，你的井字棋游戏需要两个人类对手。核心算法包含在 `TicTacToeGame` 类中。这对于项目很重要，但它不执行任何 WebSocket 操作。这是关注点分离的示例——游戏被抽象为自己的类，以便任何用户界面、WebSocket 接口可以使用该游戏逻辑。

由于该类不包含内容，因此它没有打印在书中。打开 Game-Site 项目并查看 `TicTacToeGame`。它包含了一些简单的方法用于获取玩家名称——无论是谁——包括游戏是否平局或结束，以及谁是胜者（如果有的话）。`move` 方法检查预期的移动是否合法，执行移动，然后调用其他方法计算游戏是否结束以及谁是胜者。

# 创建服务器端点

`onOpen` 方法从路径获取游戏 ID 和用户名，取决于用户是启动新游戏还是加入现有游戏。`GameStartedMessage` 会发送给两个端点。

> 列表 10-1: TicTacToeServer.java

```java
@Endpoint("/ticTacToe/{gameId}/{username}")
public class TicTacToeServer
{
    private static Map<Long, Game> games = new HashMap<>();
    private static ObjectMapper mapper = new ObjectMapper();

    @OnOpen
    public void onOpen(Session session, @PathParam("gameId") long gameId, @PathParam("username") String username) {
        try {
            List<String> actions = session.getRequestParameter("action");
            if (actions != null && actions.size() == 1) {
                String action = actions.get(0);
                if ("start".equalsIgnoreCase(action)) {
                    Game game = new Game();
                    game.gameId = gameId;
                    game.player1 = session;
                    games.put(gameId, game);
                } else if ("join".equalsIgnoreCase(action)) {
                    Game game = games.get(gameId);
                    game.player2 = session;
                }
                game.ticTacToeGame = TicTacToeGame.start(gameId, username);
                this.sendJsonMessage(game.player1, game);
                new GameStartedMessage(game, game.ticTacToeGame);
                this.sendJsonMessage(game.player2, game);
                new GameStartedMessage(game, game.ticTacToeGame);
            }
        } catch (IOException e) {
            e.printStackTrace();
            try {
                session.close(new CloseReason(
                    CloseReason.CloseCodes.UNEXPECTED_CONDITION, e.toString()
                ));
            } catch (IOException exception) {
            }
        }
    }
```

```java
    @OnMessage
    public void onMessage(Session session, String message, long gameId) {
        Game game = games.get(gameId);
        boolean player1 = session == game.player1;
        try {
            Move move = mapper.readValue(message, Move.class);
            game.ticTacToeGame.move(
                player1 ? TicTacToeGame.Player.PLAYER1 :
                    TicTacToeGame.Player.PLAYER2,
                move.getRow(),
                move.getColumn());
        }
        this.sendJsonMessage(player1 ? game.player2 : game.player1, game,
            new OpponentMadeMove(move));
        if (game.ticTacToeGame.isOver()) {
            if (game.ticTacToeGame.isDraw()) {
                this.sendJsonMessage(game.player1, game,
                    new GameIsDrawMessage());
                this.sendJsonMessage(game.player2, game,
                    new GameIsDrawMessage());
            }
        } else {
            boolean player1 = game.ticTacToeGame.getWinner() ==
                TicTacToeGame.Player.PLAYER1;
            this.sendJsonMessage(player1 ? game.player2 : game.player1, game,
                new GameWonMessage(game.ticTacToeGame.getWinner()));
        }
    }
```

# 列表 10-1（续）

```java
new GameOverMessage(wasPlayer1);
this.sendJSONMessage(game.player2, game,
new GameOverMessage(!wasPlayer1));
}
game.player1.close();
game.player2.close();
}
} catch (IOException e) {
    this.handleException(e, game);
}
}

@OnClose
public void onClose(Session session, @PathParam("gameId") long gameId) {
    Game game = TicTacToeServer.game.get(gameId);
    if(game == null) {
        return;
    }
    boolean isPlayer1 = session == game.player1;
    if(game.ticToeGame == null) {
        TicTacToeGame.removeQueuedGame(game.getId());
    } else if (!game.ticToeGame.isOver()) {
        game.ticToeGame.forfeit(isPlayer1 ? TicTacToeGame.Player.PLAYER1 : game.ticToeGame.Player.PLAYER2);
    }
    Session opponent = (isPlayer1 ? game.player2 : game.player1);
    this.sendJSONMessage(opponent, game, new GameForfeitedMessage());
    try {
        opponent.close();
    } catch (IOException e) {
        e.printStackTrace();
    }
}

private void sendJSONMessage(Session session, Game game, Message message) {
    try {
        session.getBasicRemote().sendText(TicTacToeServer.mapper.writeValueAsString(message));
    } catch (IOException e) {
        this.handleException(e, game);
    }
}

private void handleException(Throwable t, Game game) {
    t.printStackTrace();
    try {
        game.player1.close(new CloseReason(
            CloseReason.CloseCodes.UNEXPECTED_CONDITION, 
            t.toString()));
    } catch (IOException ignore) {
        try {
            // ... 
        } catch (IOException ignore) {
        }
    }
}
```

```java
private static class Game {
    public long gameId;
    public Session player1;
    public Session player2;
    public TicTacToeGame ticTacTacToeGame;
}
```

```java
public static class Move {
    private int row;
    private int column;
    // 访问器和变器方法
}
```

```java
public static abstract class Message {
    private final String action;
    public Message(String action) {
        this.action = action;
    }
    public String getAction() { ... }
}
```

```java
public static class GameStartedMessage extends Message {
    private final TicTacToeGame game;
    public GameStartedMessage(TicTacToeGame game) {
        super("gameStarted");
        this.game = game;
    }
    public TicTacToeGame getGame() { ... }
}
```

```java
public static class OpponentMadeMoveMessage extends Message {
    private final Move move;
    public OpponentMadeMoveMessage(Move move) {
        super("OpponentMadeMove");
        this.move = move;
    }
    public Move getMove() { ... }
}
```

```java
public static class GameOverMessage extends Message {
    private final boolean winner;
    public GameOverMessage(boolean winner) {
        super("gameOver");
        this.winner = winner;
    }
    public boolean isWinner() { ... }
}
```

```java
public static class GameIsDrawMessage extends Message {
    public GameIsDrawMessage() {
        super("gameDraw");
    }
}
```

```java
public static class GameForfeitedMessage extends Message {
    public GameForfeitedMessage() {
        super("gameForfeited");
    }
}
```

# 第 10 章 使用 WebSocket 使你的应用程序具有交互性

# 列表 10-1（续）

在这个系统中，服务器发送到浏览器的消息始终是 `Messages`（一个内部类），而从浏览器到服务器的消息是数组（另一个内部类）。WebSocket 消息以文本格式交换，Jackson Data Processor 库将 `Messages` 序列化为发送消息，并将接收的消息反序列化为 `Moves`。当 `onMessage` 被调用时，拥有操作的玩家会将操作发送到端点。服务器端点在 `TicTacToeGame` 中注册该操作，并通过正在进行的 `Session` 发送 WebSocket 消息通知对手操作。如果游戏结束，它将根据情况发送 `GameOverMessage` 或 `GameDrawMessage` 并关闭两个 `Session`。如果连接关闭，`onClose` 会确保游戏已结束或从未开始。如果游戏正在进行，关闭 `Session` 的用户将放弃游戏（可能是他们关闭了浏览器或离开了页面）。

当然，如果没有用户界面，这一切都是徒劳的，你可能会好奇 `TicTacToeGame` 最初是如何创建的。

# 编写 JavaScript 游戏控制台

要创建用户界面，首先你需要一个 Servlet 来提供游戏、获取玩家用户名并将请求转发到相应的 JSP。`TicTacToeServlet` 正好完成了这些工作。首先，用户通过为游戏会话输入用户名来开始游戏。

接下来，游戏被添加到等待游戏列表中。当另一个用户访问网站时，等待游戏列表就会增加。当该用户通过提供用户名加入游戏时，游戏将从等待状态变为进行状态。`list.jsp` 页面列出了游戏，并包含了启动新游戏的 UI 代码。在 Servlet 或此 JSP 中不应该有很多新奇或有趣的内容。

# 使用 WebSocket 创建多人游戏

在 `game.js` 文件（列表 10-2）中，`move` 函数在点击单元格时被调用，并将操作发送到服务器。服务器端代码处理操作，检查胜利或平局并通知对手。如果游戏结束，它会清理游戏。如果连接关闭，`onClose` 会确保游戏已结束。如果游戏正在进行，关闭连接的用户将放弃游戏。



```html
<!DOCTYPE html>
<html>
<head>
    <title>Tic Toe</title>
    <link rel="stylesheet" href="resource/TicTacToe.css">
    <script src="http://code.jquery.com/jquery-1.9.1.js"></script>
    <script src="https://cdn.cloudflare.com/ajax/libs/bootstrap/3.3.7/bootstrap.min.js"></script>
</head>
<body>
    <h2>Tic Toe</h2>
    <span class="player-label">You: <span id="username"></span></span><br>
    <span class="player-label">Opponent: <span id="status"><i>Waiting...</i></span></span>
    <div id="gameContainer">
        <div class="row">
            <div id="r00" class="game-cell" onclick="move(0, 0)">&nbsp;</div>
            <div id="r01" class="game-cell" onclick="move(0, 1)">&nbsp;</div>
            <div id="r02" class="game-cell" onclick="move(0, 2)">&nbsp;</div>
        </div>
        <div class="row">
            <div id="r10" class="game-cell" onclick="move(1, 0)">&nbsp;</div>
            <div id="r11" class="game-cell" onclick="move(1, 1)">&nbsp;</div>
            <div id="r12" class="game-cell" onclick="move(1, 2)">&nbsp;</div>
        </div>
        <div class="row">
            <div id="r20" class="game-cell" onclick="move(2, 0)">&nbsp;</div>
            <div id="r21" class="game-cell" onclick="move(2, 1)">&nbsp;</div>
            <div id="r22" class="game-cell" onclick="move(2, 2)">&nbsp;</div>
        </div>
    </div>
    
    <div id="modalWaiting" class="modal hide fade">
        <div class="modal-header"><h3>Please Wait...</h3></div>
        <div class="modal-body" id="modalWaitingBody">&nbsp;</div>
    </div>
    <div id="modalError" class="modal hide fade">
        <div class="modal-header">
            <button type="button" class="close" data-dismiss="modal">&times;</button>
            <h3>Error</h3>
        </div>
        <div class="modal-body" id="modalErrorBody"></div>
        <div class="modal-footer">
            <button class="btn btn-primary" data-dismiss="modal">OK</button>
        </div>
    </div>
    <div id="modalGameOver" class="modal hide fade">
        <div class="modal-header">
            <button type="button" class="close" data-dismiss="modal">&times;</button>
            <h3>游戏结束</h3>
        </div>
        <div class="modal-body" id="modalGameOverBody">&nbsp;</div>
        <div class="modal-footer">
            <button class="btn btn-primary" data-dismiss="modal">OK</button>
        </div>
    </div>
</body>
</html>
```

## 代码列表 10-2（续）

```javascript
<script type="text/javascript" language="javascript">
var move;
$(document).ready(function() {
    var modalError = $('#modalError');
    var modalErrorBody = $('#modalErrorBody');
    var modalWaiting = $('#modalWaiting');
    var modalWaitingBody = $('#modalWaitingBody');
    var modalGameOver = $('#modalGameOver');
    var modalGameOverBody = $('#modalGameOverBody');
    var opponent = $('#opponent');
    var status = $('#status');
    var username = '${c:out value="${username}"}';
    var myTurn = false;

    if(!('WebSocket' in window)) {
        modalErrorBody.text('此浏览器不支持 WebSockets。' +
        '请尝试 Internet Explorer 10 或最新版本的 ' +
        'Mozilla Firefox 或 Google Chrome。');
        modalError.modal('show');
        return;
    }

    modalWaitingBody.text('正在连接服务器。');
    modalWaiting.modal({ keyboard: false, show: true });

    var server;
    try {
        server = new WebSocket('ws://' + window.location.host +
        '<c:url value="/ticToe/${gameId}/${username}">' +
        '<c:param name="action" value="${action}" />' +
        '</c:url>');
    } catch(error) {
        modalWaiting.modal('hide');
        modalErrorBody.text(error);
        modalError.modal('show');
        return;
    }
</script>
```

## 使用 WebSockets 创建多人游戏

```javascript
server.onopen = function(event) {
    modalWaitingBody.text('正在等待对手加入游戏...');
    modalWaiting.modal({ keyboard: false, show: true });
};
```

```javascript
window.onbeforeunload = function() {
    server.close();
};
server.onclose = function(event) {
    if(event.wasClean || event.code != 1000) {
        toggleTurn(false, '由于错误游戏结束！');
        modalWaiting.modal('hide');
        modalErrorBody.text('代码 ' + event.code + ': ' + event.reason);
        modalError.modal('show');
    }
};
```

```javascript
server.onerror = function(event) {
    modalWaiting.modal('hide');
    modalErrorBody.text(event.data);
    modalError.modal('show');
};
```

```javascript
server.onmessage = function(event) {
    var message = JSON.parse(event.data);
    if(message.action == 'gameStarted') {
        if(message.game.player1 == username) {
            opponentUsername = message.game.player2;
        } else {
            opponentUsername = message.game.player1;
            opponent.text(opponentUsername);
        }
        toggleTurn(message.game.nextMove == username);
        modalWaiting.modal('hide');
    } else if(message.action == 'opponentMove') {
        $('#r' + message.row + ':' + message.column)
            .unbind('click')
            .removeClass('game-cell-selectable')
            .addClass('game-cell-opponent game-cell-taken');
        toggleTurn(true);
    } else if(message.action == 'gameOver') {
        toggleTurn(false, '游戏结束！');
        if(message.winner) {
            modalGameOverBody.text('恭喜，你赢了！');
        } else if (message.action == 'gameIsDraw') {
            toggleTurn(false, '游戏平局。' + 
            '没有获胜者。');
            modalGameOverBody.text('游戏平局结束。' + 
            '无人获胜！');
            modalGameOver.modal('show');
        } else if (message.action == 'gameForfeited') {
            toggleTurn(false, '你的对手放弃了！');
            modalGameOverBody.text('用户 ' + opponentUsername + 
            ' 输了游戏。你赢了！');
            modalGameOver.modal('show');
        }
    }
};
```

```javascript
var toggleTurn = function (isMyTurn, message) {
    myTurn = isMyTurn;
    if (myTurn) {
        status.text(message || '该你回合了！');
        $('.game-cell:not(.game-cell-taken)')
            .addClass('game-cell-selectable');
    } else {
        status.text(message || '等待对手移动。');
        $('.game-cell-selectable')
            .removeClass('game-cell-selectable');
    }

    move = function (row, column) {
        if (!myTurn) {
            status.text('还没轮你！');
            return;
        }

        if (server == null) {
            status.text('未连接服务器。');
            return;
        }

        server.send(JSON.stringify({row: row, column: column}));
    };
});
</script>
</html>
```

## 使用 WebSocket 玩井字棋

现在你已经查看了代码并看到所有部分是如何组合在一起的，现在是测试井字棋了。你可以执行以下操作：

1. 编译项目。
2. 启动 `Tomcat`。
3. 访问 `http://localhost:8080/ticToe` 两个浏览器（例如 `Firefox` 和 `Chrome`）。
4. 一旦看到“等待对手”的消息，就可以双击一个单元格。
5. 在一个浏览器中，你会看到另一个浏览器的单元格发生了变化。
6. 如果有人获胜，将会显示消息。

![](img/9c2d4f6d547f2cb870b3a9f62ef318_0)

图 10-6

## 使用 WebSocket 在集群中通信

现在你已经了解了服务器端点的工作原理，以及如何使用 `JavaScript` 与其通信，现在是探索客户端端点了。它们有很多用途，从数据传输到活动协调。

### 使用两个 Servlet 模拟集群

在标准集群中，节点通过某种方式通知对方的存在，例如向约定的多播 `IP` 地址和端口发送数据。然后它们通过通道（如 `TCP` 套接字）建立连接。在小型示例中模拟这种场景比较复杂，但你可以轻松使用多个 `Servlet`。查看 `web.xml`，你会有两个 `Servlet` 映射。第一个 `Servlet` 映射如下所示：

```xml
<servlet>
    <servlet-name>ClusterNode</servlet-name>
    <servlet-class>com.wrox.ClusterNodeServlet</servlet-class>
    <init-param>
        <param-name>nodeId</param-name>
        <param-value>1</param-value>
    </init-param>
</servlet>
<servlet-mapping>
    <servlet-name>ClusterNode</servlet-name>
    <url-pattern>/ClusterNode</url-pattern>
</servlet-mapping>
```

如果你在想为什么需要在部署文件中使用它，请记住你无法通过注解映射两次 `Servlet`。你可以使用部署文件或编程配置来完成此。

或者，你可以实现 `Endpoint` 抽象类。任何类都可以是端点。`Servlet` 仅在方便快捷时使用。`init` 方法在第一次请求时调用，连接到服务器端点，而 `destroy` 方法关闭连接。每当请求进入时，`Servlet` 会向集群发送关于该请求的消息。`onMessage` 方法（使用 `@OnMessage` 注解）接收来自其他集群节点的消息，`onClose`（使用 `@OnClose` 注解）在连接异常关闭时打印错误信息。

## 列表 10-3: ClusterNodeServlet.java

```java
@ClientEndpoint
public class ClusterNodeServlet extends HttpServlet {

    private Session session;
    private String nodeId;

    @Override
    public void init() throws ServletException {
        this.nodeId = this.getParameter("nodeId");
        String path = this.getServletContext().getPath() +
            "/clusterNodeSocket/" + this.nodeId;
        try {
            URI uri = new URI("ws://localhost:8080"
```



# 列表 10-3 (续)

## 发送和接收二进制消息

你可能已经注意到 `ClusterNodeServer` 使用 Java 序列化在 WebSocket 连接上发送和接收实现了 `Serializable` 接口的 `ClusterMessage`。为了实现这一点，WebSocket 消息必须是二进制的。这与井字游戏的端点不同，后者将消息转换为 JSON 并作为文本消息发送。Java 序列化比 JSON 快，因此在可能的情况下，使用 Java 序列化更好。然而，只有当双方都是 Java 时你才能这样做。如果只有一端是 Java，你就必须使用不同的序列化技术，例如 JSON。尽管 `ClusterNodeServer` 使用 `OutputStream` 和 `InputStream` 发送和接收二进制消息，但列表 10-4 中的 `ClusterNodeEndpoint` 使用了字节数组。在这种情况下，可能需要更多的代码。配合 `ObjectStreams` 使用 `Buffers` 会更容易，学习这两种方法都有价值。这完全取决于你的数据来自哪里以及你想对它做什么。如果你需要发送已经以字节数组形式存在的数据，直接使用该数组更简单。另一方面，如果你已经在处理流，通常坚持使用流更简单。

端点的唯一职责是将一个节点的消息回显到所有其他节点，并在节点加入或离开集群时通知已连接节点。在另一种情况下，你可能没有一个连接并回显所有消息的中央端点。相反，每个节点可能直接连接到所有其他节点。这取决于你的用例和应用程序的需求。

## 列表 10-4: ClusterNodeEndpoint.java

```java
@ServerEndpoint("/clusterNode/{nodeId}")
public class ClusterNodeEndpoint {

    private static final List<Session> nodes = new ArrayList<>(2);

    @OnOpen
    public void open(Session session, @PathParam("nodeId") String nodeId) {
        System.out.println("INFO: Node = " + nodeId + " connected to cluster.");

        ClusterMessage message = new ClusterMessage(nodeId, "Joined the cluster.");

        try {
            byte[] bytes = ClusterNodeEndpoint.toByteArray(message);

            for (Session session : ClusterNodeEndpoint.nodes) {
                node.getBasicRemote().sendBinary(ByteBuffer.wrap(bytes));
            }
        } catch (IOException e) {
            System.err.println("ERROR: Exception when notifying of new node");
            e.printStackTrace();
        }

        ClusterNodeEndpoint.nodes.add(session);
    }

    @OnMessage
    public void onMessage(Session session, byte[] message) {
        try {
            for (Session node : ClusterNodeEndpoint.nodes) {
                if (node != null) {
                    node.getBasicRemote().sendBinary(ByteBuffer.wrap(message));
                }
            }
        } catch (IOException e) {
            System.err.println("ERROR: Exception when handling message on server");
            e.printStackTrace();
        }
    }

    @OnClose
    public void onClose(Session session, @PathParam("nodeId") String nodeId) {
        System.out.println("INFO: Node [" + nodeId + "] disconnected.");

        ClusterNodeEndpoint.nodes.remove(session);

        ClusterMessage message = new ClusterMessage(nodeId, "The cluster.");

        try {
            byte[] bytes = ClusterNodeEndpoint.toByteArray(message);
            ClusterNodeEndpoint.getBasicRemote().sendBinary(bytes);
        } catch (IOException e) {
            System.err.println("ERROR: Exception when notifying of left node");
            e.printStackTrace();
        }
    }

    private static byte[] toArray(ClusterMessage message) throws IOException {
        try (ByteArrayOutputStream outputStream = new ByteArrayOutputStream()) {
            ObjectOutputStream stream = new ObjectOutputStream(outputStream);
            stream.writeObject(message);
            return outputStream.toByteArray();
        }
    }
}
```

## 使用 WebSockets 在集群中通信

## 测试模拟集群应用程序

测试模拟集群应用程序非常简单。只需以下步骤：

1. 编译应用程序并从你的 IDE 启动 Tomcat。
2. 在你喜爱的浏览器中访问 `http://localhost:8080/cluster/clusterNode`，你应该会在调试器输出中看到以下消息。这是 Servlet 实例的 `init` 方法被调用并连接到 WebSocket 服务器端点的结果。

   ```text
   INFO: Node [1] connected to cluster.
   ```

3. 现在访问 `http://localhost:8080/cluster/clusterNode2`。这次你应该看到几条消息。在这种情况下，第二个 Servlet 实例连接到了端点，并且当它向第一个 Servlet 发送消息时触发了输出。

   ```text
   INFO: [2] connected to cluster.
   INFO (Node 1): Message received from cluster; node = 2, message = Joined the cluster.
   INFO (Node 1): Message received from cluster; node = 2, message = request:{ip:'127.0.0.1',queryString:'**'} (此处保留原文)
   ```

4. 尝试第一个 URL，但为它添加此查询字符串：`http://localhost:8080/cluster/clusterNode?hello`。
5. 最后一次，尝试集群 URL，但带有查询字符串：`http://localhost:8080/cluster/clusterNode?baz=dog`。

   ```text
   INFO (Node 1): Message received from cluster; node = 2, message = request:{ip:'127.0.0.1',queryString:'baz=dog'}
   ```

6. 如果你想进行实验，创建另一个 Servlet 实例你就能看到了。

你可以实现 `Decoder.Binary`、`Decoder.BinaryStream`、`Decoder.Text` 或 `Decoder.TextStream`，并使用端点注解的 `decoders` 属性为你的消息提供解码器。

```java
public class ChatMessage {
    private OffsetDateTime timestamp;
    private Type type;
    private String user;
    private String content;

    // 访问器和修改器方法

    public static enum Type {
        STARTED, JOINED, ERROR, LEFT, TEXT
    }
}
```

之前的 `ChatMessage` 代码显示它是一个简单的 POJO。WebSocket API 同时需要编码器和解码器，以便你的应用程序可以发送和接收消息。列表 10-5 包含了一个用于编码和解码 `ChatMessage` 的简单类。它使用 Jackson Processor 来编码和解码消息。`encode` 方法处理一个 `ChatMessage` 和一个 `OutputStream`，通过将消息转换为 JSON 进行编码并将其写入 `OutputStream`。`decode` 方法执行相反的操作：给定一个 `InputStream`，它读取并反序列化 JSON 格式的 `ChatMessage`。`init` 和 `destroy` 方法在 `Encoder` 和 `Decoder` 接口中均有定义。它们在这里没有被使用，但如果你需要初始化或释放编码器和解码器使用的资源，它们会派派用场。

## 列表 10-5: ChatMessageCodec.java

```java
public class ChatMessageCodec implements Decoder.BinaryStream<ChatMessage>, Decoder.BinaryStream<ChatMessage> {

    private static final ObjectMapper MAPPER = new ObjectMapper();

    static {
        MAPPER.findAndRegisterModules();
        MAPPER.configure(JsonGenerator.Feature.AUTO_CLOSE_TARGET, false);
    }

    @Override
    public void encode(ChatMessage chatMessage, OutputStream outputStream) throws Exception, IOException {
        try {
            ChatMessage.MAPPER.writeValue(outputStream, chatMessage);
        } catch (JsonGenerationException | MappingException e) {
            throw new EncodeException(chatMessage, e.getMessage(), e);
        }
    }

    @Override
    public ChatMessage decode(InputStream inputStream) throws DecodeException, IOException {
        try {
            return ChatMessageCodec.MAPPER.readValue(inputStream, ChatMessage.class);
        } catch (ParseException | JsonMappingException e) {
            throw new DecodeException((ByteBuffer) null, e.getMessage(), e);
        }
    }

    @Override
    public void init(EndpointConfig endpointConfig) { }

    @Override
    public void destroy() { }
}
```

## 在客户支持应用程序中添加“与支持聊天”

## 创建聊天服务器端点

服务器端点使用以下 `ChatSession` 类将请求聊天的用户与响应的支持代表相关联。它包含了欢迎消息以及聊天期间发送的所有消息的日志。

```java
public class ChatSession {
    private long sessionId;
    private String username;
    private Session customer;
    private String representativeUsername;
    private Session representative;
    private ChatMessage creationMessage;
    private final List<ChatMessage> chatLog = new ArrayList<>();

    // 访问器和方法

    @JsonIgnore
    public void log(ChatMessage message) { ... }

    @JsonIgnore
    public void writeChatLog(File file) throws IOException {
        ObjectMapper mapper = new ObjectMapper();
        mapper.findAndRegisterModules();
        mapper.configure(JsonGenerator.Feature.AUTO_CLOSE_TARGET, false);
        mapper.configure(SerializationFeature.WRITE_DATES_AS_TIMESTAMPS, false);

        try (FileOutputStream stream = new FileOutputStream(file)) {
            mapper.writeValue(stream, this.chatLog);
        }
    }
}
```

列表 10-6 中的 `ChatEndpoint` 接收连接并对其进行适当协调。由于长度原因，省略了部分代码，但包含了对你来说是新的概念。类内部嵌套了 `EndpointConfigurator` 类，它重写了 `modifyHandshake` 方法。在握手时，该方法会被调用并暴露底层的 HTTP 请求。

你可以从 `request` 中获取 `HttpSession` 对象，在这种情况下，你希望通过 HTTP 会话来确保用户已登录，并在用户注销时也处理 WebSocket 会话。这就是为什么该端点是一个 `HttpSessionListener`。当会话失效时，会调用 `sessionDestroyed` 方法，端点随之关闭该会话。需要注意的是，该类的实例在启动时会作为 Web 客户端创建，并且每当客户端端点连接到服务器端点时，都会创建一个新实例。这就是为什么所有字段都是静态的，以便在实例之间协调关于 `Session`、`HttpSession` 和 `ChatSession` 的相关信息。

`onOpen` 方法在新的处理器完成后，首先确保 `HttpSession` 已与 `Session` 关联（在 `modifyHandshake` 方法中）且用户已登录。如果聊天会话 ID 为 0（请求了新会话），则创建一个新会话并添加到待处理会话列表中。如果大于 0，则一个代表将加入请求的会话，并将消息发送给两个客户端。当 `onMessage` 接收到任一客户端的消息，且连接关闭、发生错误或 `HttpSession` 被销毁时，会向另一个用户发送消息通知他们，并关闭两个连接。

## 列表 10-6: ChatEndpoint.java

```java
@Server(value = "/chat/{sessionId}",
    encoders = MessageCodec.class,
    decoders = MessageCodec.class,
    configurator = ChatEndpoint.EndpointConfigurator.class)
@WebSocketListener
public class ChatEndpoint implements HttpSessionListener {
```



private static final Map<Long, ChatSession> sessions = new Hashtable<>();

private static final Map<Long, Session> sessions = new Hashtable<>();

private static final Map<Long, HttpSession> httpSessions = new Hashtable<>();

public final List<ChatSession> pendingSessions = new ArrayList<>();

private static long sessionIdSequence = 0;

private static final Object sessionIdLock = new Object();

@OnOpen
public void onOpen(Session session, long sessionId) {
    HttpSession httpSession = (HttpSession) session.getUserProperties().get(sessionId);

    if (httpSession == null || httpSession.getAttribute("username") == null) {
        session.close(CloseCodes.VIOLATED_POLICY, "You are not logged in!");
        return;
    }

    String username = (String) httpSession.getAttribute("username");
    session.getUserProperties().put("username", username);

    ChatMessage message = new ChatMessage();
    message.setTimestamp(OffsetDateTime.now());
    message.setUser(username);

    ChatSession chatSession;

    if (sessionId < 1) {
        message.setType(ChatMessage.Type.STARTED);
        message.setContent(username + " started the chat session.");
        chatSession = new ChatSession();

        synchronized (sessionIdLock) {
            chatSession.setSessionId(sessionIdSequence++);
        }

        chatSession.setCustomer(session);
        chatSession.setCustomerUsername(username);
        chatSession.setCreationMessage(message);
        pendingSessions.add(chatSession);
        sessions.put(chatSession.getSessionId(), chatSession);
    } else {
        message.setType(ChatMessage.Type.JOINED);
        message.setContent(username + " joined the chat session.");
        chatSession = sessions.get(sessionId);
        chatSession.setRepresentative(session);
        chatSession.setRepresentativeUsername(username);
        pendingSessions.remove(chatSession);
        session.getBasicRemote().sendObject(chatSession.getCreationMessage());
        session.getBasicRemote().sendObject(message);
    }

    sessions.put(session, chatSession);
    httpSessions.put(session, httpSession);
    sessionsFor(httpSession).add(session);
    chatSession.log(message);
    chatSession.getCustomer(session).getBasicRemote().sendObject(message);
} catch (IOException | EncodeException e) {
    this.onError(session, e);
}

@OnMessage
public void onMessage(Session session, ChatMessage message) {
    ChatSession c = sessions.get(session);
    Session other = otherSession(c, session);

    if (c != null && other != null) {
        c.log(message);
        try {
            session.getBasicRemote().sendObject(message);
            other.getBasicRemote().sendObject(message);
        } catch (IOException | EncodeException e) {
            this.onError(session, e);
        }
    }
}

private List<Session> sessionsFor(HttpSession session) {
    List<Session> result = new ArrayList<>();
    for (Map.Entry<Session, HttpSession> entry : httpSessions.entrySet()) {
        if (entry.getValue().equals(session)) {
            result.add(entry.getKey());
        }
    }
    return result;
}

private Session otherSession(ChatSession c, Session session) {
    if (c.getCustomer().equals(session)) {
        return c.getRepresentative();
    } else if (c.getRepresentative().equals(session)) {
        return c.getCustomer();
    }
    return null;
}

@Override
public void sessionDestroyed(HttpSession session) {
    Session s = httpSessions.remove(session);
    if (s != null) {
        s.close(CloseCodes.VIOLATED_POLICY, "Session expired");
    }
}

```

# 294 | 第 10 章 使用 WEBSOCKET 让你的应用程序交互化

列表 10-6（续上）

```
@OnClose
public void onClose(Session session, CloseReason reason) { ... }

@OnError
public void onError(Session session, Throwable e) { ... }

@Override
public void sessionDestroyed(HttpSessionEvent event) { /* 什么都不做 */ }

@Override
public void sessionCreated(HttpSessionEvent event) { ... }

@SuppressWarnings("unchecked")
private synchronized ArrayList<Session> getSessionsFor(HttpSession session) {
    try {
        if (session.getAttribute(WS_SESSION_PROPERTY) == null) {
            session.setAttribute(WS_SESSION_PROPERTY, new ArrayList<>());
        }
        return (ArrayList<Session>) session.getAttribute(WS_SESSION_PROPERTY);
    } catch (IllegalStateException e) {
        return new ArrayList<>();
    }
}

private void sessionClose(Session s, ChatMessage message) { ... }

private Session getOtherSession(ChatSession c, Session s) { ... }

public static class EndpointConfigurator extends ServerEndpointConfig.Configurator {
    @Override
    public void modifyHandshake(ServerEndpointConfig config, HandshakeRequest request, HandshakeResponse response) {
        super.modifyHandshake(config, request, response);
        config.getUserProperties().put(
            ChatEndpoint.HTTP_SESSION_PROPERTY, request.getHttpSession()
        );
    }
}
```

# 编写 JavaScript 聊天应用程序

`WEB-INF/jsp/view/chat/chat.js` 文件包含了支持聊天的用户界面。大部分代码是用于展示、连接和错误处理的，这些你在之前的井字游戏中已经见过了。特别重要的是 `onmessage` 事件和 `send` 函数，它们分别处理消息的接收和发送。由于该应用程序使用 JSON 在浏览器和服务器之间传递消息，因此使用文本消息比二进制消息会更简单一些。然而，你还没有见过如何在 JavaScript 中处理二进制消息，所以这个示例演示了这一点。

# 在客户支持应用程序中添加“与客服聊天” | 295

```
server.onmessage = function(event) {
    if (event.data instanceof ArrayBuffer) {
        var message = JSON.parse(String.fromCharCode.apply(
            null, new Uint8Array(event.data)
        ));
        objectMessage(message);
        if (message.type == 'JOINED') {
            otherJoined = true;
            if (username != message.user) {
                infMessage('你现在正在与 ' + message.user + '聊天');
            }
        }
    } else {
        modalError.body.text('意外的数据类型 [' + \
            typeof(event.data) + '].');
        modalError.modal('show');
    }
};

send = function(text) {
    if (server == null) {
        modalError.body.text('你尚未连接！');
        modalError.modal('show');
    } else if (otherJoined) {
        modalError.body.text(
            '另一个用户尚未加入聊天。');
        modalError.modal('show');
    } else if (messageArea.get(0).value.trim().length > 0) {
        var message = {
            timestamp: new Date(), type: 'TEXT', user: username,
            content: messageArea.get(0).value
        };
        try {
            var json = JSON.stringify(message);
            var length = json.length;
            var buffer = new ArrayBuffer(length);
            var array = new Uint8Array(buffer);
            for (var i = 0; i < length; i++) {
                array[i] = json.charCodeAt(i);
            }
            server.send(buffer);
            messageArea.get(0).value = '';
        } catch (error) {
            modalError.body.text(error);
            modalError.modal('show');
        }
    }
};
```

现在编译并启动 Customer-Support v8 应用程序，并打开两个浏览器访问 `http://localhost:8080/support`。在两个浏览器中以不同的用户登录支持应用程序。（记住，你可以在 `LoginServlet` 中查看可用的用户名和密码）。在一个浏览器中，点击“与客服聊天”以请求聊天会话。在另一个浏览器中查看“聊天请求”，然后点击你之前打开的聊天会话。在每个浏览器中输入消息并点击“发送”。你应该看到像图 10-7 的效果。你现在正在通过两个浏览器与自己聊天。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_331_0.png)

图 10-7

### 总结

WebSockets 是互联网中非常有用且强大的新技术。就像在早期经历过许多更改的 HTTP 协议一样，WebSocket 协议在未来几年也可能经历许多变化。目前，它有一个扩展框架，但没有现有的扩展。随着越来越多的开发者开始使用这项技术，这种情况可能会发生变化。WebSockets 有许多用途，你在本章中探索了其中几种。你创建了一个多玩家井字游戏，使用 WebSockets 与应用程序集群中的节点进行通信，并在客户支持应用程序中添加了支持聊天。你学习了通向 WebSockets 的技术，以及 WebSockets 如何解决那些技术无法解决的许多问题。此时，你应该已经熟悉该协议以及使用它所需的 Java 和 JavaScript API。

# 11 | 使用日志监控你的应用程序

### 本章内容

- 关于日志的一切
- 什么是日志级别？
- 哪种日志设施适合你？
- 如何在应用程序中集成日志

### WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/javaforapps` 找到本章的代码。本章代码分为以下主要示例：

- 日志集成项目
- 客户支持 v9 项目

### 本章的新 Maven 依赖

除了之前章节引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```
<dependency>
  <groupId>org.apache.log4j</groupId>
  <artifactId>log4j-api</artifactId>
  <version>2.0</version>
  <scope>compile</scope>
</dependency>
```



```xml
<dependency>
  <groupId>org.apache.log4j</groupId>
  <artifactId>log4j-core</artifactId>
  <version>2.0</version>
  <scope>runtime</scope>
</dependency>
```

```xml
<dependency>
  <groupId>org.apache.log4j</groupId>
  <artifactId>log4j-jcl</artifactId>
  <version>2.0</version>
  <scope>runtime</scope>
</dependency>
<dependency>
  <groupId>org.apache.log4j</groupId>
  <artifactId>log4j-slf4j-impl</artifactId>
  <version>2.0</version>
  <scope>runtime</scope>
</dependency>
<dependency>
  <groupId>org.apache.log4j</groupId>
  <artifactId>log4j-taglib</artifactId>
  <version>2.0</version>
  <scope>runtime</scope>
</dependency>
```

### 理解日志的概念

想象这样一个场景：你收到一个应用程序 bug 报告。根据客户支持提供的精确复现步骤，你可以反复复现该 bug。问题是，一旦你在调试器中点击断点，问题就消失了。无缘无故地消失。这很可能（尽管不是）意味着问题与多线程有关，而断点减慢了执行速度，足以掩盖问题。那么，你该如何弄清楚问题是什么？日志对于成功的调试、故障排除、监控和错误报告至关重要。在本章中，你将探索日志的概念；学习日志方面、API 和实现；并将日志集成到应用程序中。

### 为什么你应该记录日志

作为个人选择，我们倾向于不使用调试器，除非获取堆栈跟踪或一两个变量的值。原因之一是很容易在复杂的数据结构和控制流中迷失；我们发现，单步执行程序比深入思考并在关键点添加输出语句和自检查代码效率更高。点击语句花费的时间比扫描精心放置的输出要长。决定你应该在哪里放置 `print` 语句以便单步执行到代码的关键区域，即使我们已经知道它在哪里。更重要的是，调试语句与程序共存；而调试器会话是瞬态的。

> KERNIGNAN, BRIAN W. AND ROB PIKE. THE PRACTICE OF PROGRAMMING. READING: ADDISON WESLEY LONGMAN, INC., 1999. 119.

你有许多理由应该记录日志。前面的引言强调了关于日志记录的重要点——以及关于调试器的缺点。需要注意的是，自该本书出版以来已经过了多年，调试器已经有了巨大的进步。在当今，在 IDE 中启动调试器并单步执行应用程序的运行重要性不言而喻。调试器在很多方面都是最好的，而且 Java IDE 中的调试集成使得对实例和堆栈变量的检查和修改变得简单。在大多数 Java IDE 中，你可以在断点停顿时运行时评估任意表达式，并可以在不重启 Java 虚拟机的情况下更改、重新编译和重新加载代码。

尽管如此，仅仅靠调试是不够的。上述的假设只是调试器产生阻碍的许多例子之一。有时调试器根本无法使用。考虑一种情况：客户的问题在开发环境中无法复现，甚至在质量保证环境中也无法复现。大多数情况下，为客户运行的生产环境附加调试器并不是一个选项。

面对现实吧：Bug 不是计划好的。当你编写完善你的应用程序时，Bug 仍然会出现。你可以采用许多技术并使用许多工具来检测和尽量减少代码中的 Bug，但你永远无法避免它们。因此，计划在没有调试器的情况下排查 Bug 是合理的。

调试你的应用程序并不是你应该记录日志的唯一理由。通常你需要被通知重要事件，例如错误、应用程序配置的更改、意外行为、组件的启动或关闭、日志数据以及变化。你可能希望监控你的应用程序，以确保它正常运行并承受某种活动。所有这些需求以及更多——说明了为什么你应该记录日志。

在 Java 早期（`java.util.logging` 直到 Java 1.4 才成为框架的一部分），许多开发者使用 `System.out.println()` 和 `System.out.println()` 来“记录”错误和有趣信息。今天，许多应用程序和事件库仍然充满了这类语句。这些流可以被重定向到单独的文件，这确实有用，但由于它们缺乏粒度且“始终开启”的特性，会导致日志迅速填满并阻碍应用程序的性能。理想情况下，你希望有一种易于自定义、可以配置为显示少量或大量信息、可以根据包或类显示不同信息，并且（最重要的是）不阻碍性能的东西。

### 你可能希望在日志中看到的内容

考虑到前述的理想日志系统——可自定义、可配置、按包或类区分且性能良好——关于你想要放入日志文件中的所有信息。你可能会想到几件事，实际上从技术上讲可能性是无限的，但这里有一些可以帮助你入门的基础想法：

*   当应用程序崩溃或意外退出时，尽可能详细地记录导致崩溃的所有细节是至关重要的。这可能包括消息、堆栈跟踪、线程转储甚至堆转储。JVM 崩溃并不容易记录。崩溃的本质在很大程度上阻止了日志记录能够工作。因此，大多数 JVM 都内置了工具来记录事件的发生。例如，Oracle 和 OpenJDK JVM 具有命令行选项 `-XX:HeapDumpOnOutOfError`，它让 Java 在 JVM 内存耗尽时生成堆转储。请考虑你的 JVM 制造商的文档以获取更多信息。
*   当发生错误时，你应该记录你关于该错误的任何信息（类型、消息、堆栈跟踪以及错误发生时应用程序正在做什么）。然后，通过将所有重要数据存储在某处的日志中，你可以仅向用户显示最少的错误消息，告诉他们发生了一些问题，而不会损害你的系统（例如文件路径或 SQL 查询）。
*   有时会出现一些不是错误且不会阻止操作继续的问题，但可能应该在稍后由某人注意到。这些问题表明你的应用程序存在潜在但并非确定的问题。你应该记录这类情况，包括详细信息和应用程序正在做什么的内容。有时，堆栈跟踪也适用于这些情况。你可能将这些视为“警告”。
*   某些重要事件是你可能想在日志中记录的。记录诸如实体的创建、组件启动、用户成功登录或任务的执行，可以帮助你了解系统是否运行正常。
*   当你想要追踪一个问题时，你想看到有关方法和例程执行的详细信息，包括适用变量的值。然而，你可能不想一直看到这些，而且创建这些数据可能会阻碍性能。
*   在最严酷的情况下，你可能需要看到方法何时结束或退出，以及每个方法的参数值和返回值。在任何正在执行的循环中，你可能需要每次迭代的数据。在高负载场景下，这是海量的信息，所以你绝对不想一直这样做，而且不是对所有事件都这样做，即使你确实在这样做。事实上，有时你可能想将这种类型的日志限制为特定用户或其他标准。
*   你通常需要审核应用程序中的活动。如果你的领域是安全、医疗或法律，法律要求记录谁做了什么。这不是一份完整的列表。

### 日志是如何写入的

需要记住的一个重要点是，日志并不一定是文件。通常当你考虑日志时，你自然会想到文件。毕竟，在某个时刻，你的日志内容会出现在某处。这并不意味着你的内容是直接写入文件的（尽管如果你愿意，你完全可以这样做）。日志可以通过许多方式写入。有时，日志会同时写入多个位置，或者在主介质失败时写入备份。日志是异步写入的，以便应用程序可以在日志排队时继续处理。在某些情况下，日志必须是事务安全的，以便在日志失败时停止操作。所有这些因素以及你的需求，都影响了日志如何写入。

通常来说，有一些用于存储日志的机制。你可能想使用这些中的一个或多个，或者想出自己的。

#### 控制台

一种经过时间检验的方法，控制台日志等效于 `System.out.println()`。虽然使用日志系统可以获得许多优势，但日志的输出是一致的：`stdout`。控制台日志的问题在于，除非进程的标准输出重定向或数据超出控制台缓冲区，否则内容将永远消失。然而，控制台日志在开发周期和其它机制失效时极其有用。它几乎总是被配置为大多数应用程序的至少一种日志机制。

#### 平文件

另一种传统的日志方法，平文件可能是最容易写入的介质，也是读取日志最困难的介质。平文件相对于控制台日志的主要优势是它们本质上是持久的（除非你删除它们），但优势到此为止。

通常，平文件日志由文件中的单行日志组成，但由于日志消息有时会占据多行（例如堆栈跟踪），在程序上应用这种模式可能很困难。标准的平文件日志肉眼阅读尚可，但几乎无法进行过滤或筛选。平文件日志的一些变体在某些情况下可以稍微改进这个问题：

*   使用标准的 XML 语法记录每个日志事件。其主要优势是它既是人类可读的，也是机器可读的，这意味着可以编写程序来读取日志内容并带有过滤功能进行显示。然而，XML 是一种极其臃肿的格式，可能会混淆或使你的日志体积翻倍甚至更多！
*   JSON 日志与 XML 类似，只是它将日志内容存储在 JavaScript 对象格式中。这意味着比 XML 臃肿得多，但另一方面让人类阅读稍微困难一点。

> 在 Linux 操作系统上，syslog 是所有进程都可以写入的设施。这些具体细节不在本书的讨论范围内，但本质上，日志事件被写入到由操作系统日志工具管理的平铺文件中，并以标准格式存储在中心位置。Windows 通过 Windows 事件日志（Windows Event Log）提供了类似的功能，数据以 XML 格式存储，并且操作系统内置了日志查看器。

滚动文件（rolling files）的概念可以适用于所有这些模式（在 syslog 和 Event Log 的情况下，是自动应用的）。当日志系统被设置为使用滚动日志时，它会定期更改其所记录的文件。日志记录可以是基于时间的——例如，Tomcat 每天获取一组新的日志——而在其他情况下，当日志文件达到特定大小时，日志文件会被备份到一个带索引的文件名，并启动一个新的日志文件。

#### 套接字

套接字是一种常见的日志方法，但在某些情况下非常有用。日志事件被翻译成某种网络通信格式，然后通过网络发送到其他地方。有时接收日志的应用程序可能在同一台机器上；有时在同一网络的不同机器上；有时则在不同的网络上（甚至在地球的另一端）。在几乎所有情况下，套接字连接的另一端都是专用的日志记录器，其唯一目的是以某种方式接收并持久化日志。

#### SMTP 和 SMS

虽然通过发送电子邮件来记录日志事件听起来很奇怪，但请想想你有多想在应用程序发生错误时立即获知。对于普通的常规日志记录，很少能看到电子邮件和短信（SMS）通知。在作者见过的每种情况下，电子邮件和短信仅预留给严重的应用程序错误，例如导致系统操作终止或组件故障的异常。这会通知系统管理员需要立即查看问题。

#### 数据库

应用程序将日志记录到数据库中是非常常见的，且有多种原因。数据库是高效、事务安全的存储手段，极易对数据进行查询和过滤。如果你正在记录审计数据，很可能你会使用数据库来存储这些数据。将日志记录到数据库的缺点可能也显而易见。首先是速度：由于网络协议栈和数据库的开销，向索引表写入数据的速度比写入文件要慢得多（小规模下）。但存在数据库大小的问题：许多数据库对存储的数据量有限制，即使达到了这些限制，性能也会急剧下降。索引可能会消耗几秒甚至更长时间。对于许多人来说，为了可以轻松过滤的日志而付出这种代价是不合理的。

NoSQL 数据库应运而生，它们缺乏关系型数据库给日志系统带来的许多问题。这些数据库以关系的方式存储数据，这消除了大部分开销，并能够对数 GB 或 TB 的数据进行高效存储。用于此类任务的最流行的数据库之一是 MongoDB，它是一种 NoSQL 数据库。它以二进制 JSON（BSON）格式存储数据，这是一种极其压缩且高效的存储手段。

MongoDB 牺牲了读取性能——在过滤数据集时它可能很慢——以换取写入性能。当数据库大小超过几个 GB 时，向 MongoDB 插入数据的速度可以比流行的关系型数据库系统快几个数量级。对于希望对性能影响降至最低的日志系统来说，这是一个巨大的优势。MongoDB 与大多数文档数据库一样，并不完全符合 ACID 规范，但如果你正确结构化你的文档，可以将丢失数据的概率降低到与 ACID 关系型数据库（RDBMS）相当的水平。

### 使用日志级别和类别

在上一节中，你探索了日志的一些概念，包括你可能希望在应用程序日志中看到的各种类型信息的概述。当你探索这个主题时，可能很快就会清楚，日志事件有不同的类型或严重程度，并且并不是所有类型都会被记录。这通常被称为日志级别（logging levels）概念。有时级别是不够的。通常你需要的应用程序特定部分的极详细日志细节，而不是整个程序。如果你能对日志事件进行分类，你的日志数据将变得更有用。在本节中，你将研究日志级别和类别。你还将查看日志偏移（log shifting）的概念以及它与日志分类的关系和区别。

### 为什么会有不同的日志级别？

你可能已经问过这个问题了。到目前为止，你已经确定了很多应该包含在日志中的信息；有些是严重错误的指示，而其他类型代表了极其细微且大量的调试细节。如果你一直开启这些内容，你的日志每秒可能会增长几兆字节（相信我，我真的见过！）。这不仅会阻碍应用程序的性能，还会让你的日志基本上变得毫无用处。当你需要为一秒的程序执行筛选几 MB 的日志数据时，还不如什么日志都不记录。

级别表示被记录日志事件的严重程度或相对重要性。这里使用“相对”一词是因为事实确实如此：一个日志级别要么比另一个日志级别重要，要么没那么重要。日志级别本身的名称并不定义它所传达消息的实际重要性；消息的重要性是相对于其他消息进行比较的。在某些系统中，日志级别就是整数，仅此而已。在其他系统中，日志级别被分配一个名称以提供某种关于可用性的语义。对于日志级别的数量、顺序或名称，并没有公认的标准。你使用的几乎每个系统都可以定义这些，取决于你如何确定什么最适合你。

### 日志级别定义

尽管没有公认的标准，但在大多数为 Java 应用程序编写的日志系统中，会出现一些常见的模式。日志级别通常被命名以赋予它们高层次的含义，在许多系统中存在六到十个不同的级别。表 11-1 列出了最常见的类型，从最严重到最简单，对应 `java.util.logging.Level`。

#### 表 11-1：常见日志级别

| 通用名称 | Level 常量 | 语义含义 |
| :--- | :--- | :--- |
| 致命错误 / 崩溃 | 无对应 | 表示最严重的错误。通常这些错误会导致崩溃或至少导致应用程序提前终止。 |
| 错误 | SEVERE | 表示发生了严重问题 |
| 警告 | WARNING | 表示发生了某些事件，虽然不是问题，但可能需要查看 |
| 信息 | INFO | 如名称所示，这些信息对于应用程序监控和调试很有用 |
| 配置细节 | CONFIG | 此级别的事件通常包含配置信息。通常在应用程序或组件启动时看到。 |
| 调试 | FINE | 表示调试信息，通常包含变量的值 |
| 追踪级别 1 / 追踪级别 2 | FINER / FINEST | 这些级别代表不同级别的应用程序跟踪。许多日志框架只定义一个跟踪级别。分开使用这些级别的一种可能方法是使用 `FINER` 记录执行的 SQL 语句，使用 `FINEST` 记录方法的进入和退出。 |

重要的是，这些示例是基于一种日志系统：Java SE API 内置的 `java.util.logging`。但在 Java 编程内部外部都有许多不同的日志系统，每个系统都有自己不同的级别集合。有些系统（如 `java.util.logging`）允许你扩展并定义更多级别，而有些不是。

作为不同级别集合的一个例子，Apache HTTPD 2.2 服务器日志中的日志级别：emerg, alert, crit, error, warn, info 和 debug（2.4 版本增加了 8 个更多级别：trace 到 trace8）。异常活动与调试信息之间级别数量的不比例突显了该系统的一个根本性区别：它认为区分不同类型的错误比区分不同类型的调试信息更重要（尽管这在后续版本中发生了变化）。同样，你的需求可能会根据应用程序的用例而异。

### 日志类别如何工作

日志类别的概念比日志级别稍微抽象一些。在 Java 的几乎所有情况下（包括你在本章中看到的所有示例），日志类别由命名的日志器实例表示，并且每个日志器都可以分配不同的级别。

### 选择日志框架

在模式中，两个不同的类可以使用两个不同的日志器，你可以设置其中一个记录数据，而另一个只记录警告。事实上，这正是大多数情况下使用“类别（categories）”的方式：在开发阶段，每个类类都拥有它自己的日志器，通常以其完全限定的类名命名。根据日志系统的不同，通常会建立一个日志器层级结构，使得未定义级别赋值的日志器可以从某个父级日志器继承级别。

### 日志筛选如何工作

日志筛选在概念上与日志分类相似，但其用途略有不同。通过使用日志筛选，不同类型或不同取向的事件会被记录到不同的位置（如不同的文件、不同的数据库表或文档等）。在某些方面，这与分类是相同的，区别在于分类通常定义的是一个不同的日志级别，而不是一个日志目的地。许多日志框架允许你通过使用类别来筛选日志，从而通过一个功能解决两个问题。另一些框架则提供了使用类别以及日志事件的属性（通常在某种类型的过滤器中）进行筛选的能力。在 Java 中，所有主要的日志框架都允许基于日志类别进行筛选，如果不是基于每个日志事件的更多属性的话。你将在接下来两个章节中进一步探讨筛选的话题。

### 选择日志框架

在你理解了应用程序的日志需求之后，下一个任务是选择一个日志框架。这并不意味着要使用第三方框架——它可能意味着创建自己的。然而，在几乎所有情况下，你都能找到现有的、经过行业测试的日志框架并对其进行配置以满足你的需求，这意味着创建自己的仅仅是一个不必要的任务。在本节中，我们将研究两个需要记住的重要准则，并查看一些现有的日志框架。

### API 版本实现



考虑以下情景：你编写了一个拥有数千个客户端的大型企业应用程序。这些客户端中的大多数（不是 POJO 的那些）都使用了日志。经过仔细的研究，你选择并将一个行业标准的日志系统集成到你的应用程序中。运行一周后，你的系统工程团队通知你，你选择的 syslog 输出并不足够，需要数据库日志。遗憾的是，你选择的日志系统不支持数据库日志。你能做什么？你可以扩展日志系统，但那里已经有一个非常好的日志系统支持数据库日志了，而你更倾向于使用它。然而，如果你决定需要更改代码类以使用不同的日志系统，这项工作可能耗时数周并让你的公司花费数万美元。

这种情景中的底层问题是你正在使用的日志 API 与底层实现紧耦合。你无法在不更改代码中所有使用日志的地方的情况下更换实现。如果你当初编写一个简单的日志 API 来在代码中使用日志的地方隐藏底层框架，你就可以避免这种情况。这样，当你需要更换框架时，你只需要更改你 API 中的少数类；你应用程序的其他部分可以像往常一样继续使用你的 API 进行日志记录。坦率地说，这在日志框架世界中并不是一个新概念，而且你可能甚至不需要自己写 API。

Java 平台内置的标准 `java.util.logging` 框架是日志 API 与实现分离的一个示例。`java.util.logging.LogManager` 类负责创建和返回 `Logger` 实例，并将任务委托给默认实现。开发者可以扩展 `LogManager` 并指定一个系统属性来提供标准日志 API 的替代实现。

标准实现具有处理器（handlers），它们可以写入文件、流、套接字、控制台和内存。当你可能会想，为什么不能使用标准的日志功能时，简单的答案是：“你可以用。”在许多情况下，对于许多应用程序来说，内置日志是完全足够的。然而，它有一个缺点，使得它在应用程序中使用变得极其困难甚至不可能：它是通过系统属性而不是类路径（classpath）配置的。由于由于，部署在同一个容器中的两个 Web 应用程序不能有不同的日志配置，除非该容器扩展了基础日志实现。Tomcat 实现了这一点，但并不是所有容器都这样做，因此依赖这一点是不可移植的。相反，最好找到其他结合分离的 API 和实现的解决方案。

## 性能

显然，无论你处理应用程序的哪个部分，性能都是一个巨大的考虑因素，日志记录也不例外。然而，请思考一下，写入文件、套接字、数据库或电子邮件的过程。这些任务在输入/输出操作耗费时间时，花费了大量时间处于阻塞状态。这是无法逃开的：记录日志消息需要时间，而绝大部分时间不在你的控制范围内，而是在操作系统手中——这意味着你不能仅通过软件来改变它。

但是，如果你有一个足够重要而需要记录的消息，你可能不在乎它为某个活动增加了几毫秒。为什么性能很重要？关键在于，当你记录日志时，性能（何时）并不重要；当你不在记录日志时，它才（极其）重要。你可能会在代码中填满 trace、debug 和 info 语句，而在大多数时间里你并不想看到它们。你本质上希望除非你启用了该级别的详细信息，否则这些操作什么都不做。

以下是性能可能决定一个日志框架成败的关键情况：

- 在禁用调试日志记录时调用 `debug` 方法不应该增加纳秒级或更短的时间。
- 通过一个性能良好的日志系统，你应该在代码中填满日志语句，关闭所有日志，而应用程序的响应时间没有可感知的差异。这是你选择日志系统时要寻找的关键性能指标。

当然，在开启日志记录时具有良好的性能是值得赞赏且理想的，但如果日志是关闭的，它毫无意义。

## 快速查看 Apache Commons Logging 和 SLF4J

Apache Commons Logging (https://commons.apache.org/commons-logging/) 和 Simple Logging Facade for Java (https://www.slf4j.org/) 都是广泛使用的 API。任何一个 API 都不包含实现；它们带有多个日志框架的适配器。在运行时，它们会发现使用的日志框架（通过约定或配置）并激活相应的适配器，以从 API 翻译到实现。Commons Logging 为 `java.util.logging`、Log4j 1.2 等提供了适配器。SLF4J 为（讽刺的是）Commons Logging、`java.util.logging` 和 Log4j 1.2 提供了适配器。当 API 未支持特定日志框架的适配器时，框架提供了适配器。例如，Logback 是与 SLF4J 使用的流行实现，并提供了 SLF4J 适配器绑定。

完全分离。API 为开发者提供了一个用于记录日志的接口，并提供了创建底层实现的方法。

当然，还有一个默认的实现，应用程序和其他日志框架的开发者可以自由使用该 API，将 API 适配并运行在其他日志实现之上。由于市上有许多日志框架，而且 Log4j2 仍然非常新，在编写新库时，你仍然应该使用 Commons Logging 或 SLF4J 作为你的日志 API。这是因为你无法知道你库的消费者将使用哪种日志框架，而且这些日志框架适配 Commons Logging 或 SLF4J 的概率比适配 Log4j 更大。然而，在编写应用程序时，主权掌握在你手中。直接针对 Log4j 2 API 编写提供了更大的灵活性，根据你的使用方式，可能在某些方面也有助于性能，而且在需要时，你不会失去更换底层实现的能力。

> 注意：Log4j2 在其网站上包含了若干项性能指标。最重要的指标——关闭日志时的性能——令人印象深刻：
>
> 在中等硬件上，调用 `isEnabled` 的耗时为 3 纳秒，在关闭 debug 时调用 `debug` 的耗时为 4 纳秒。这意味着在你的应用程序中放置有用的消息日志只需一秒的 4 亿分之一。从这个角度来看，在禁用所有日志的情况下，你的应用程序在执行时间内必须执行 250,000 次 debug 方法，或者每秒执行 250,000,000 次 debug 方法时间才会翻倍。
>
> 所有这些性能大致与 Logback 的性能相当。
>
> Log4j2 在日志过滤器方面真正出色。在多线程应用程序中，测试显示，当启用过滤器处理时，Log4j 的性能比 Logback 高出一个数量级或更多。

在本书的剩余部分中，你将使用 Log4j 2 API 配合底层的 Log4j 2 实现进行记录（在现实场景中，你会评估项目的需求并决定哪种 API 和实现适合你）。你无疑已经注意到这一章有五个 Log4j 2 Maven 依赖。以下是它们的说明：

- `log4j-api` 提供日志记录的 API。这是你应用程序中唯一处于 `compile` 范围的 Log4j 依赖；它包含了你应该编写代码的唯一类。
- `log4j-core` 包含了标准的 Log4j 2 实现。当你在本章的其余部分探索 Log4j 2 配置时，配置的是实现，而不是 API。API 不需要任何配置。
- `log4j-cl` 是一个支持 Commons Logging API 的适配器。你在书的其余部分使用的库针对 Commons Logging API 记录日志，这个适配器使得 Commons Logging 使用 Log4j 2 作为其实现。
- `log4j-slf4j-impl` 是一个 SLF4J 实现适配器。在书的其余部分使用的几个库针对 SLF4J API 记录日志，这个适配器使得 SLF4J 使用 Log4j 2 作为其实现。
- `log4j-taglib` 是一个包含 JSP Tag Library 的适配器，用于在你的 JSPs 中记录日志。与前三个依赖一样，出于编写应用程序代码的目的，该依赖处于 `runtime` 范围，因为你不需要针对它进行编译。然而，如果你配置了构建来编译你的 JSPs，那么你需要该依赖在 JSP 编译过程中具有 `compile` 范围。

Log4j 2 实现具有你应当理解的关键概念。API 以泛义的方式暴露这些概念（在适用处已注明），是与实现的集成使得这些功能成为可能。

## 为什么不使用 COMMON LOGGING 或 SLF4J？

此时此，你可能在考虑之前提到的需要快速切换日志实现的场景。虽然 Log4j 2 API 使这种切换成为可能，但并没有让它变得容易。API 的编写无疑是考虑了实现的。那么，为什么不在在 Log4j 2 前面使用 Common Logging 或 SLF4J 呢？

Common Logging API 和 SLF4J API 都不像 Log4j 2 API 那样完整且功能丰富。选择 Common Logging 或 SLF4J 意味着放弃某些功能，例如致命日志（fatal logging）、任意级别日志、自定义级别日志、简单的方法进入和退出日志，以及带参数的消息格式化。在独立库中，使用日志门面（facade）比在应用程序中要重要得多。如果你愿意牺牲一些 Log4j 2 的功能，你完全可以选择 SLF4J 或 Common Logging 而不是 Log4j 2 API。另一方面，如果你想利用所有 Log4j 2 的功能并使用日志门面，你可以创建一个自己的门面来匹配 Log4j 2 API。这个选择由你决定。对于本书，你将直接使用 Log4j 2 API。

### 配置

Log4j 2 实现是完全自配置的。最起，你必须做的一件事就是使用 Log4j 2 在你的代码中放置日志语句。默认情况下，Log4j 2 可以配置自身以记录错误并将日志消息写入控制台。只有当以下所有步骤都未能找到显式配置时，它才会这样做：

- 检查 `log4j.configurationFile` 属性，如果存在，则从该文件加载配置。
- 在 classpath 上寻找名为 `log4j2-test.json` 的文件，如果存在，则从该文件加载配置。
- 在 classpath 上寻找名为 `log4j2-test.xml` 的文件，如果存在，则从该文件加载配置。
- 在 classpath 上寻找名为 `log4j2-test.properties` 的文件，如果存在，则从该文件加载配置。
- 在 classpath 上寻找名为 `log4j2.xml` 的文件，如果存在，则从该文件加载配置。

分离配置文件的目的是简单的：这涵盖了执行的情况。在下一节中，我们将通过集成来概述配置。

### 级别

Log4j 2 定义了六个日志级别两个特殊级别，按优先级（从严重到轻微）排序：OFF、FATAL、ERROR、WARN、INFO、DEBUG、TRACE、ALL。注意 OFF 和 ALL 不是你实际记录的内容；意味着“不记录任何内容”和“全部”。

最初，Level 是一个枚举，它无法扩展。在 Log4j 2 发布前，Level 从枚举改为最终类，并带有构造函数和工厂方法 `forName(String name, int level)`。该方法在存在时返回 Level，在不存在时创建一个新的 Level。StandardLevel 帮助你在记录类似 SLF4J 的桥接 API 时创建级别。对于任何给定的名称，只有一个 Level 实例。这意味着可以使用 `==` 运算符而不是 `equals` 来轻松地创建自己的 Level。

```java
public class CustomLevels {
    public static final Level CONFIG = Level.forName("CONFIG", 350);
    public static final Level NOTICE = Level.forName("NOTICE", 450);
    public static final Level DIAG = Level.forName("DIAG", 550);
}
```

### Logger

Logger 和类别在 Log4j 2 中是同义的，你写的每条日志都必须处理 Logger 类。通过调用 LogManager 的一个 `getLogger` 方法获取 Logger。当你拥有一个 Logger 实例时，可以记录错误、警告和其他消息。Logger 名称定义了日志类别，按照惯例，它是使用 Logger 的类的全限定名（每个类都有自己的 Logger 实例）。

多次调用相同的 `getLogger` 会得到同一个 Logger 实例，而不是多个同名的实例（换句话说，Logger 是缓存的）。两个 Logger 可以具有不同的级别并分配到零或多个 Appender。Logger 名称遵循用点分隔的层次结构，更具体的 Logger 会继承祖先 Logger 的级别和 Appender。这在表 11-2 中所示。该表仅处理级别，但继承规则对于 Appender 来说基本相同。Assigned Level 列表示了你在 Log4j 配置中可能分配的级别。

#### 表 11-2: Log4j 2 Logger 的继承层次结构

| LOGGER | 分配的级别 | 有效级别 | 继承自级别 |
| --- | --- | --- | --- |
| root (特殊) | WARN | WARN | n/a |
| com | - | WARN | root |
| com.wrox | INFO | INFO | - |
| com.wrox.chat | DEBUG | DEBUG | - |
| com.wrox.shop | - | INFO | com.wrox |
| com.example.test | - | WARN | root |

### Appender

Appender（日志输出器）负责将日志内容实际写入目标位置。当将 Appender 分配给 Logger 时，它们的继承规则本质上与级别（Levels）相同，不同之处在于还具有“添加性（additivity）”属性，该属性决定了 Appender 是被添加还是覆盖已继承的 Appender。

例如，root logger 被配置了一个控制台 Appender，而 com.wrox 分配了一个文件 Appender。写入到 com.wrox、com.wrox.chat 等处的消息会同时发送到控制台和文件，而写入到 root 或 com.example.test 的日志只会发送到控制台。

如果你将 com.wrox 的添加性属性设置为 false，写入到 com.wrox、com.wrox.chat 等处的消息将只会发送到文件。（它们会在该 Appender 处停止。）

如果 com.wrox.shop 的添加性属性仍为 false，且写入到 com.wrox.shop 的消息发送到 syslog 和文件，但如果添加性设置为 true（默认值），消息将同时发送到 syslog、文件和控制台。

### Layouts（布局）

Appender 经常使用 Layout 来决定如何格式化其输出。最常见的 Layout 类型是基于模式的 Layout，它定义了一组标记（tokens），在写入时用日志消息中的数据进行替换。此外，还有 HTML、XML、syslog 和序列化布局等示例。你将在下一节中探索 PatternLayout。

### Filters（过滤器）

Log4j Filters（不要与 Servlet 混淆）提供了一种机制，可以决定日志消息是否以及如何被写入。过滤器评估的结果为 ACCEPT（接受）、DENY（拒绝）或 NEUTRAL（中性），就像网络过滤器一样。ACCEPT 表示消息应该写入，并忽略所有其他过滤器。如果过滤器评估结果为 ACCEPT，即使级别也会被忽略，即使其级别不足，消息也会被记录。DENY 则与之相反：这意味着消息被立即拒绝，后续的过滤器没有机会评估该消息。NEUTRAL 则既不接受消息，其他过滤器也可以继续进行评估。

在 Log4j2 配置中，过滤器可以附加到架构的四个阶段：上下文配置、Logger 配置、Appender 引用或 Appender 配置。当消息被记录时，它的第一个停留点是按声明顺序排列的全局上下文过滤器。过滤器在评估级别（Level）之前执行。假设上下文过滤器返回 NEUTRAL，则消息将进入级别评估阶段。如果它通过了级别测试，下一个停靠点是 Logger 配置过滤器。之后是 Appender 引用过滤器，它们决定了 Logger 是否应该将消息路由到特定的 Appender。（例如，这可以用于将消息筛选（sift）到不同的文件或数据库表中。）最后，单个 Appender 上的过滤器决定了 Appender 是否应该写入该消息。

过滤器可以作用于各种信息。一种常见的模式是在日志消息中带有 Marker（标记）对象，并让过滤器拥有 Marker 对象。这对于筛选操作特别有用。过滤器还可以查看消息内容、消息类型、附加到消息的异常以及存储在当前运行线程（Thread）中的数据，仅列举几个。就此而言，过滤器可以使用与上下文消息无关的内容作为判断依据，以决定如何处理消息。你将在下一节中看到配置过滤器的示例。

## 将日志记录集成到你的应用程序中

使用和配置 Log4j 是一项相当简单的任务。如上一节所述，你只需要在应用程序中放置日志语句即可完成：

```java
private static final Logger log = LogManager.getLogger();

@Override
protected void doGet(HttpServletRequest request, HttpServletResponse response)
throws ServletException, IOException
{
    if (request.getParameter("action") == null)
        log.error("No action specified.");
}
```

Log4j 2 使用默认配置自启动，并开始向控制台写入日志消息。当然，这个默认配置可能无法满足你的需求。你可能需要的不仅仅是错误（你可能还会想要警告和信息消息），并且你可能希望日志发送到控制台以外的地方。你可以通过配置文件来实现这两点。

> 如果你正在使用配置旧版本的 Log4j，应该记住两个重要点。第一， Log4j 2 不支持通过 Java 属性文件进行配置。你必须使用 XML 或 JSON。第二，Log4j 2 的 XML 架构与 Log4j 的 XML 架构不同。如果你在任何应用程序中有已有的 log4j.xml 文件，你不能将这些文件重命名为 log4j2.xml。你必须采用新的配置架构。

## 创建 Log4j 配置文件



# Log4j 2 配置文件

Log4j 2 会寻找两个配置文件（`log4j2` 和 `log4j2-test`），并支持三种不同的文件扩展名（`.xml`、`.json`、`.jsn`）。`.json` 和 `.jsn` 扩展用于 JSON 格式的配置。与 XML 配置相比，JSON 配置用代码读写起来更方便，因此如果你想通过程序创建 Log4j 2 配置，JSON 可能是更好的选择。如果你是手动创建配置，那么 XML 是一个更容易的选择。

> **注意**：没有 Log4j 的官方架构。

# 创建 log4j2.xml 配置文件

现在你已经有了适当的配置，在资源目录中创建一个 `log4j2.xml` 文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration status="WARN">
  <Appenders>
    <Console name="Console" target="SYSTEM_OUT">
      <PatternLayout pattern="%d{HH:mm:ss.SSS} [%t] %X{username} %5level"/>
    </Console>
    <RollingFile name="WROXFileAppender" fileName="../logs/application.log"
      filePattern="../logs/application-%d{MM-dd-yyyy}-%i.log">
      <PatternLayout pattern="%d{HH:mm:ss.SSS} [%t] %5level"/>
      <Policies>
        <SizeBasedTriggeringPolicy size="10 MB" />
      </Policies>
      <DefaultRolloverStrategy min="1" max="4" />
    </RollingFile>
  </Appenders>
  <Loggers>
    <root>
      <appender-ref ref="Console" />
    </root>
    <logger name="com.wrox" level="info" additivity="false">
      <appender-ref ref="WROXFileAppender" />
      <appender-ref ref="Console" />
      <MarkerFilter marker="WROX_CONSOLE" onMatch="NEUTRAL" onMismatch="DENY" />
    </logger>
    <logger name="org.apache" level="info">
      <appender-ref ref="WROXFileAppender" />
    </logger>
  </Loggers>
</configuration>
```

# 将日志集成到你的应用程序

> **注意**：当运行应用程序时，如果你在 Tomcat 的日志目录中找不到 `application.log` 文件，请尝试将相对路径更改为系统上某个目录的绝对路径并重启应用程序。

`PatternLayout` 支持许多可以记录事件的模式，你可以在 Log4j 文档中了解它们（以及其他模式）。在这种情况下，文件 Appender 模式将 `%logger` 替换为 `%c`（前者比后者更短），并添加了 `%l`，它可以打印发生日志消息的类、方法、文件和行号。它还添加了 `%X{id}`（一个鱼类标签/fish tag）和 `%X{username}`，这些是 `ThreadContext` 上的属性。你还会发现，文件 Appender 的模式除了模式不同外，其使用的 XML 格式也与控制台 Appender 不同。你可以通过标签属性或嵌套标签来指定 Appenders（附加器）、Filters（过滤器）、Loggers（日志器）等的属性。这两种方法是相互互换的。

最后，此文件中的新配置表示 `com.wrox` 和 `org.apache` 层次结构下的所有 Logger 都继承自 INFO，且 `com.wrox` 中的 Logger 不是累加的——它们不继承 Console Appender 并且只记录到文件 Appender。然而，注意用于控制台 Appender 的 `com.wrox appender-ref` 元素带有嵌套的 `<MarkerFilter>` 元素。该过滤器表示 `com.wrox` 层次结构中的 Logger 可以记录到控制台 Appender，但仅对于包含名为 `WROX_CONSOLE` 的 Marker（标记）的事件。你可以在 Log4j 文档中了解各种可用过滤器。以下不完整的配置显示了 Filter 配置元素的所有有效位置（加粗显示）：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <FilterName ... /><!-- 这是一个全局范围过滤器 -->
  <Appenders>
    <Appender name="someAppender">
      <FilterName ... /><!-- 这是一个 appender 过滤器 -->
    </Appender>
  </Appenders>
  <Loggers>
    <logger name="someLogger" level="info">
      <FilterName ... /><!-- 这是一个 logger 过滤器 -->
      <appender-ref ref="someAppender">
        <FilterName ... /><!-- 这是一个 appender 引用过滤器 -->
      </appender-ref>
    </logger>
  </Loggers>
</configuration>
```

本书无法向你展示所有配置 Log4j 的可能方法，因为方法有很多。如果你想获取更多信息，一个很好的起点是 Log4j 手册。

# 在 Web 过滤器中使用鱼类标记

在使用任何日志框架时，你都应该对请求进行“鱼类标记”（fish tag），以便你可以将同一个请求的日志消息分组并进行分析。`org.apache.logging.log4j.ThreadContext` 在当前线程中存储属性，直到 `ThreadContext` 被清空。在将属性添加到 `ThreadContext` 到将其移除之间，在同一线程中记录的任何事件都可以与该请求关联。如果有许多并发 Web 请求在执行，为每个请求设置唯一的鱼类标记使你能够识别在该特定请求期间记录的所有消息。

鱼类标记通常是唯一的东西，例如 UUID。`ThreadContext` 可以存储其他任何用于区分日志事件的内容，例如登录用户的用户名。以下 `LoggingFilter` 在请求开始时将鱼类标记 (`id`) 和会话用户名 (`username`) 添加到 `ThreadContext`，并在请求完成后清空 `ThreadContext`。之前讨论的模式使用 `%X{id}` 和 `%X{username}` 打印这些属性。由于过滤器支持多种调度器类型并可能在单次请求中执行多次，它只在鱼类标记和用户名属性尚未被设置时才设置它们，并且会为后续的调用清空 `ThreadContext`。

```java
@WebFilter(urlPatterns = "/*", dispatcherTypes = {
    DispatcherType.REQUEST, DispatcherType.ERROR, DispatcherType.FORWARD,
    DispatcherType.INCLUDE, DispatcherType.ASYNC
})
public class LoggingFilter implements Filter {

    @Override
    public void doFilter(ServletRequest request, ServletResponse response,
            FilterChain chain) throws IOException, ServletException {
        boolean clear = false;
        if (!request.getAttribute("id") != null) { // 修正逻辑判断
            clear = true;
            ThreadContext.put("id", UUID.randomUUID().toString());
            HttpSession session = ((HttpServletRequest) request).getSession(false);
            if (session != null) {
                ThreadContext.put("username",
                    (String) session.getAttribute("username"));
            }
        }

        try {
            chain.doFilter(request, response);
        } finally {
            if (clear) {
                ThreadContext.clear();
            }
        }
    }
}
```

# 在 Java 代码中编写日志语句

> **警告**：回想你在第 9 章中学习的关于异步请求处理的课程。如果你在异步请求开始时在 `ThreadContext` 上设置值，这些值将在请求完成之前被清空。出于此原因，每当你配合异步请求使用 `ThreadContext` 时，必须非常小心。在线 Log4j2 手册中的 Web Applications 和 JSPs 章节包含了关于异步上下文中 Log4j 各个方面的有用信息。

使用 Log4j 2 Logger 极其简单。对于每个日志级别都存在重载方法，这些方法允许你指定字符串、对象或消息作为消息；提供一个或多个参数来替换字符串消息中的占位符；提供记录堆栈轨迹的异常；以及提供 Marker 来标记事件。查看列表 11-1，它使用 Logger 记录 `HttpServlet` 中的活动。

## 列表 11-1: Action.java

```java
@WebServlet(name = "servlet")
public class Action extends HttpServlet {

    private static final Logger logger = LogManager.getLogger(Action.class);

    protected void doGet(HttpServletRequest request, ServletResponse response)
            throws IOException, ServletException {
        String action = request.getParameter("action");
        String contents = null;

        if (action != null) {
            switch (action.toLowerCase()) {
                case "readfoo":
                    contents = readFile("../foo.bar", true);
                    break;
                case "readlicense":
                    contents = readFile("../LICENSE", false);
                    break;
                default:
                    contents = "Bad action " + action + " specified.";
                    logger.warn("Action {} not supported.", action);
            }
        }

        if (contents != null) {
            response.getWriter().write(contents);
        } else {
            logger.error("No action specified.");
            response.getWriter().write("No action specified.");
        }
    }

    protected String readFile(String fileName, boolean deleteWhenDone) {
        logger.entry(fileName, deleteWhenDone);

        try {
            byte[] data = Files.readAllBytes(new File(fileName).toPath());
            logger.info("Successfully read file {}", fileName);
            return new String(data);
        } catch (IOException e) {
            logger.error(MarkerManager.getMarker("WROX_CONSOLE"), "Failed to read file {}", fileName, e);
            return null;
        }
    }
}
```

# 在 JSP 中使用 Log 标签库

如前所述，Log4j 2 自带有一个标签库，允许你在 JSP 中记录消息，而无需使用脚本代码。本书将不会对这一主题进行详细介绍，因为通常来说，表示层对日志记录的需求要少得多。事实上，只要你的 JSP 中不包含任何业务逻辑，你就永远不需要对它们进行日志记录。尽管如此，你可以通过以下指令包含该标签库：



<% taglib prefix="log" uri="http://logging.apache.org/log4j/tld/log" %>

Logging-Integration 项目在 Web 目录下有一个 `logging.jsp` 文件，它演示了如何使用这些标签：

```
<log:entry />
<!DOCTYPE html>
<html>
<head>
<title>Test Logging</title>
</head>
<body>
<info message="JSP body displaying." />
Messages have been logged.
<info>JSP body complete.</info>
</body>
</html>
<log:exit />
```

你的应用程序中每个使用一个或多个 log 标签的 JSP 都会自动为其创建一个唯一的 Logger。你可以使用 `<log:getLogger>` 标签或大多数其他标签上的 `logger` 属性来覆盖此日志记录。启动应用程序并在浏览器中访问 `http://localhost:8080/logging-integration/logging.jsp` 来尝试 JSP 日志。根据你配置的日志级别，你将在日志中看到不同的消息。

# 在客户支持应用程序中记录日志

wrox.com 上的 Customer-Support+9 代码已从代码中移除了所有 `System.out`、`System.err` 和 `Throwable.printStackTrace()` 的使用，并将其替换为 Log4j 2 日志。此外，在整个应用程序中增加了更多的日志消息。最后，将 `LoggingFilter` 从上一个示例中复制并添加到 Configurator 过滤器链的开头，以便获取所有请求。

你应该下载并复阅这些更改，但在此处不再进行详细说明，因为这与你已经学的内容是冗余的。`com.wrox` 层次结构下所有 Logger 的默认日志级别设置为 INFO，到目前为止唯一的 INFO 事件是用户登录。大多数其他日志事件都是 DEBUG、TRACE、WARN 或 ERROR。正如此，当你运行 Customer Support 应用程序时，在 `support.log` 文件中看不到太多内容。请放心，这将在第二部分开始学习 Spring Framework 时会发生变化。

## 总结

在本章中，你学习了应用程序日志的基础知识，以及为什么在应用程序中记录日志如此重要。你研究了几种常见的日志模式，并探索了类别和日志级别的概念。你还学习了将日志 API 与其底层实现分离的重要性，这可以避免你日后的很多麻烦。你接触了几个流行的日志 API 和实现，例如 Apache Commons Logging、SLF4J、Logback、Log4j 1.x 以及 Log4j 2。最后，你学习了使用和配置 Log4j 2 的细节，并尝试了将其集成到 Web 应用程序中。在书的其余部分，日志记录出现在每一个章节中。你工作的每个项目都包含 Log4j 2 配置和日志语句。通过这样，你可以养成在编程时始终记录日志的习惯。

第一部分此结束，在这一部分你学习了使用 Java SE、Java EE、Servlets、JSPs、过滤器、WebSockets、应用程序服务器、Web 容器等进行 Web 应用程序开发的各个方面。现在，你应该已经牢牢掌握了基础，并能够编写相当复杂的应用程序了。在第二部分中，你将通过学习 Spring Framework 开始提升你的企业级开发技能，学习它是如何补充、增强并在某些情况下替换 Java 平台企业版（Enterprise Edition）的部分的。

# 第二部分：引入 Spring Framework

- 第 12 章：引入 Spring Framework
- 第 13 章：用 Controllers 替换你的 Servlets
- 第 14 章：使用 Services 和 Repositories 支持你的 Controllers
- 第 15 章：使用 Spring Framework i18n 使你的应用程序国际化
- 第 16 章：使用 JSR 349、Spring Framework 和 Hibernate Validator 进行 Bean 验证
- 第 17 章：创建 RESTful 和 SOAP Web 服务
- 第 18 章：使用消息和集群提高灵活性和可靠性

## 消息传递

在应用程序中，消息传递是一个需要解决的重要问题。例如，程序的某些部分可能需要知道程序的其他部分何时执行了特定操作。执行该操作的程序部分简单地依赖于对操作感兴趣的部分，并调用它们的方法来通知它们，但那种紧耦合类型难以维护，并且可能会变得非常混乱。

Spring Framework 提供了一个松散耦合的消息传递系统，它使用了发布-订阅模式：系统中的组件通过订阅某些消息来宣布它们对这些消息感兴趣，而这些消息的生产者在发布消息时并不关心谁订阅了它们。这本质上就是 Twitter 的工作原理：对感兴趣（或可能不感兴趣）的事情向他们关注的人发布推文。使用 Spring Framework，由 Spring 管理的 bean 通过实现通用接口来订阅特定类型的消息，而 Spring 管理的对象将这些消息发布给 Spring Framework，再由 Spring Framework 将其传递给订阅方。该系统还可以扩展和配置，以便跨应用程序集群投递消息。

## Web 应用程序的模型-视图-控制器 (MVC) 模式

Spring Framework 具有模型-视图-控制器（MVC）模式，简化了创建交互式应用程序的过程。Spring 不需要手动处理 `Servlets`、`HttpServletRequest`、`HttpServletResponse` 的复杂性以及向 JSP 的转发，而是为每个任务处理相应的工作。控制器类被映射到不同的请求 URL，或者以 `Map<String, Object>` 的形式存在。从控制器的视图或视图名称（String）会使 Spring 转换为相应的 JSP 视图，并且 URL 参数会自动转换为原始类型或复杂的控制器方法参数。

除了典型的 HTML 视图外，Spring 还可以通过 XML 或 JSON 实体视图自动生成纯文本视图和文件下载视图。通过所有特性，Spring Framework 极大地简化了在 Servlet 容器中的工作。

## 为什么选择 Spring Framework？

在之前的章节中，你已经学习了 Spring Framework 提供的许多功能，因此你可能已经意识到在应用程序中使用 Spring Framework 的一些引人注目的原因。它的功能集和对 Servlet API 的简化并不是 Spring Framework 的唯一优势。它所遇到的模式（你将在本书的这一部分进一步了解它们）提供了若干益处，当你努力创建强大的 Web 应用程序时，无疑会欣赏这些优点。

### 逻辑代码分组

考虑本书之前章节中过的一些复杂的 Servlet。每个 Servlet 都有一个 `doGet` 或 `doPost`，或者可能包含许多 `if` 语句或 `switch` 块，负责将请求路由到 Servlet 内部的任意方法。在更复杂的企业级应用程序中，你会很快发现这种模式变得难以管理且极难测试。例如，一个处理个人信息的 Servlet 可能有几十个方法，每个方法在 `doGet` 或 `doPost` 方法中都建立了不同的路由逻辑。

另一种可能的解决方案是创建几十个 Servlet。这将导致一个更具测试性和可维护性的代码库，但随着逻辑分支的泛滥，这些 Servlet 的数量将迅速变得不可管理。如果你的应用程序包含数百个功能，每个功能有几十个方法，你会发现代码库膨胀到数千个 Servlet；除非你将 Servlet 映射到单个方法而不是整个类，否则许多问题将无法解决。

使用 Spring 的 MVC 框架，控制器的作用非常像具有方法映射、参数扩展、标头值、内容类型和顺序响应类型的 Servlet。你的单元测试是针对控制器方法的这些微小代码单元进行的，而控制器类包含了许多在逻辑上分组在一起的映射方法。回到用户配置的示例，控制器可以有几十个映射方法，代表在用户配置上可以执行的各种操作，但 `doGet` 或 `doPost` 方法对于将请求路由到适当的方法是必要的。Spring Framework 为你处理了所有的分析和路由。

### 多个用户界面利用同一个代码库

在现实场景中，你可能被要求创建一个具有数千个功能的高级应用程序，这些功能应该可以通过桌面应用程序、Web 浏览器、移动浏览器、RESTful Web 服务和 SOAP Web 服务访问。仅使用 Servlets，这很快就会令人生畏。你最终将不得不大量重复代码，或者创建自己的系统，将业务逻辑抽象为来自许多用户界面的其他类。幸运的是，Spring Framework 提供了这样一个系统，让你只需少量努力即可使用。使用 Spring，业务逻辑被封装在一组称为服务的业务对象中。这些服务执行所有用户界面共同的操作，例如确保实体属性被正确指定。你的应用程序每个用户界面包含一组不同的控制器和视图，它们使用公共业务对象来执行关键操作。因此，控制器只需要执行将表单提交或 JSON 请求体转换为实体，并将适当的值部署给用户。单元测试变得更容易，代码被复用，且只需极小的努力即可实现这两者。

### 理解应用上下文

Spring Framework 容器以一个或多个应用上下文的形式出现，由 `org.springframework.context.ApplicationContext` 接口表示。应用上下文管理一组 bean，这些 Java 对象执行业务逻辑、执行任务、持久化和检索数据、响应 HTTP 请求等。Spring 管理的 bean 自动具备依赖注入、消息通知、调度方法执行、bean 验证以及其他关键 Spring 资格。

Spring 应用程序始终至少有一个应用上下文，有时它需要多个。然而，它也可以拥有多个应用上下文的层次结构。在这种层次结构中，任何 Spring 管理的 bean 都可以访问相同应用上下文中的 bean、父应用上下文中的 bean、父级应用上下文中的 bean，以此类推。它们无法访问兄弟或子应用上下文中的 bean。这对于定义一组共享的应用程序组件同时与其他组件相互隔离非常有用。例如，你可能希望 Web 应用程序的 Web 和管理部分互不可访问，但无疑你会有两个部分都需要的一些共享资源。

> 注意：在书的其余部分你经常使用 Spring Framework，应该随时保留 API 文档。务必标记该文档，以便在你想了解更多关于 Spring 接口、类或异常时进行参考。

有许多扩展实现 `ApplicationContext` 类的接口：

- `ConfigurableApplicationContext` 接口是可配置的，而基础 `ApplicationContext` 是只读的。`org.springframework.web.context.WebContext` 和 `ConfigurableWebApplicationContext` 接口适用于运行在 Servlet 容器中的 Java EE Web 应用程序，并提供对底层 `ServletContext` 以及（适用）`ServletConfig` 的访问。具体类 `ClassPathApplicationContext` 和 `FileSystemXmlApplicationContext` 设计用于从独立应用程序中加载 Spring 配置，而 `XmlWebApplicationContext` 在 Java EE Web 应用程序实现了同样的功能。对于使用 Java 而非 XML 编程配置 Spring，`AnnotationConfigApplicationContext` 和 `AnnotationConfigWebApplicationContext` 分别适用于独立和 Java EE 应用程序。

在 Java EE Web 应用程序中，Spring 使用 dispatcher 处理请求，将请求委托给相应的控制器并根据需要翻译响应实体。你的 Web 应用程序可以根据用例创建任意多个 `org.springframework.web.servlet.DispatcherServlet` 类实例。

每个 DispatcherServlet 获得其应用上下文，该上下文拥有 Web 应用程序 `ServletContext` 和 `ServletConfig` 的引用。你可能会创建多个 DispatcherServlet 来分离你的 Web 用户界面和 Web 服务。由于这些 DispatcherServlet 均无法访问其他 DispatcherServlet 的应用上下文，因此通常需要在公共根应用上下文中共享某些 bean（如业务对象或数据访问对象）。该应用上下文对于整个 Web 应用程序，是所有 DispatcherServlet 应用上下文的父级，并使用 `org.springframework.web.context.ContextLoaderListener` 创建。它也有一个引用访问 Web 应用的 `ServletContext`，但因为它不属于任何特定的 Servlet，因此没有 `ServletConfig` 引用。

尽管在 Web 应用中设置多个 DispatcherServlet 的想法是普遍的，并且在本书中都会涉及，但这只是无限可能中的一种配置。在任何独立应用或 Web 应用中，你都可以根据需要创建任何应用上下文层次结构。根据一般原则，你应该始终有一个根应用上下文，所有其他应用上下文以某种方式继承它，如图 12-1 所示。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_364_0.png)

图 12-1

## 启动 Spring 框架

在计算机软件世界中，一切都必须在某个时刻进行启动（bootstrap）。考虑一下你的台式电脑、笔记本电脑或移动计算设备：当它们开启时，某种类型的启动设备（通常是 BIOS 或类似设备）会初始化所有硬件，从某个位置（如硬盘上的引导区）加载启动指令并启动操作系统。从这个意义上说，硬件是操作系统的容器。操作系统是另一个容器——用于运行在其内部的软件。

C 程序有一个标准的启动机制：`main()` 方法。所有可运行的 C 程序必须包含此方法才能被启动。Java 虚拟机可执行文件通常用 C 或 C++ 编写，它包含此 `main()` 方法（或其所编写语言的等效方法）。语言虚拟机（如 JVM 或 .NET 运行时）是其他软件的容器。对于 Java 应用，清单文件（manifest）中的指令（或命令行提供的指令）通过提供带有 `public static void main(String...)` 方法的类来启动应用程序。Tomcat 与任何其他容器一样——用于 Java EE 应用的 Servlet 容器。Web 应用包含某种启动指令：部署描述符或以注解形式存在的元数据指示了如何运行它们。

与所有这些示例一样，Spring 框架是另一个容器。它可以在任何 Java SE 或 EE 容器中运行，并作为应用程序的运行时环境。与所有这些示例一样，Spring 必须被启动：它被启动并指示如何运行它所包含的应用程序。

配置和启动 Spring 框架是两个不同的任务，彼此独立，可以通过不同的方式处理。虽然配置告诉了如何运行应用程序，但启动是指示程序去执行。在 Java SE 应用中，启动 Spring 只有一种方法：通过编程方式，通常使用应用程序的 `public static void main(String...)` 方法。在 Java EE 应用中，你有两个选择：使用部署描述符通过 XML 启动 Spring，或者可以在 `javax.servlet.ServletContainerInitializer` 中通过编程方式启动 Spring。

### 使用部署描述符启动 Spring

在传统的 Spring 框架应用程序中，你一直在 Java EE 部署描述符中启动 Spring。至少，这需要一个 `DispatcherServlet` 实例，并以 `contextConfigLocation` 参数形式提供配置文件给它，并在启动时对其进行指示。

```xml
<servlet>
  <servlet-name>springDispatcher</servlet-name>
  <class>org.springframework.web.servlet.DispatcherServlet</class>
  <init-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/servletContext.xml</param-value>
  </init-param>
  <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
  <servlet-name>springDispatcher</servlet-name>
  <url-pattern>/</url-pattern>
</servlet-mapping>
```

这在 DispatcherServlet 容器设置内创建了一个单一的 Spring 应用上下文，以便在启动时初始化 `DispatcherServlet`。初始化时，`DispatcherServlet` 从 `/WEB-INF/servletContext.xml` 文件加载配置并启动应用上下文。当然，正如之前解释的，这为你的应用程序创建了一个应用上下文，并不非常灵活。一个更完整的描述符启动看起来像这样：



```xml
<context-param>
  <param-name>contextConfig</param-name>
  <param-value>WEB-INF/rootContext.xml</param-value>
</context-param>
<listener>
  <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>

<servlet>
  <servlet-name>DispatcherServlet</servlet-name>
  <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
  <init-param>
    <param-name>ConfigLocation</param-name>
    <param-value>WEB-INF/servletContext.xml</param-value>
  </init-param>
  <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
  <servlet-name>DispatcherServlet</servlet-name>
  <url-pattern>/*</url-pattern>
</servlet-mapping>
```

`ContextLoaderListener` 在 Web 应用启动时初始化（因为它实现了 `Servlet`），它从 `contextConfigLocation` 初始化参数指定的 `/WEB-INF/rootContext.xml` 文件加载根应用上下文配置并启动应用上下文。

注意，`contextConfigLocation` 初始化参数与 `DispatcherServlet` 的 `contextConfig` Servlet 初始化参数不同。它们互不冲突；前者适用于整个服务器上下文，而后者仅适用于所指定的特定 Servlet。

尽管一个 Web 应用中只能有一个根上下文，但可以有很多你可以使用的 Servlet 上下文。在第 7 章中，当你为 RESTful Web 服务创建 `DispatcherServlet` 时，你可以看到这种用法示例。当然，这些示例假设你使用 XML 配置 Spring，这可以在“配置 Spring 框架”章节中进行探讨。你也可以用 Java 配置 Spring（在后后的章节中介绍），Java 启动 Spring 非常类似于：

```xml
<context-param>
  <param-name>contextClass</param-name>
  <param-value>org.springframework.web.context.support.AnnotationWebApplicationContext</param-value>
</context-param>
<context-name>context</context-name>
<param-value>com.wrox.config.RootContextConfiguration</param-value>
</context-param>
<listener>
  <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>
```

```xml
<servlet>
  <servlet-name>springDispatcher</servlet-name>
  <class>org.springframework.web.servlet.DispatcherServlet</class>
  <init-param>
    <param-name>contextClass</param-name>
    <param-value>org.springframework.web.context.support.AnnotationWebApplicationContext</param-value>
  </init-param>
  <init-param>
    <param-name>contextLocation</param-name>
    <param-value>com.wrox.config.ServletContextConfiguration</param-value>
  </init-param>
  <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
  <servlet-name>springDispatcher</servlet-name>
  <url-pattern>/*</url-pattern>
</servlet-mapping>
```

通常 `ContextLoader` 和 `DispatcherServlet` 会创建 `org.springframework.web.context.support.WebApplicationContext` 实例，它们期望 Spring 的配置以 XML 形式存在。之前的示例覆盖了此行为并改用 `AnnotationWebApplicationContext`。该类型期望编程上下文配置，通过类名（而不是文件名）在 `contextConfigLocation` 参数指定。

## 在初始化器中通过编程启动 Spring

回想之前的章节，你使用 `ServletContextListener` 在应用程序中通过编程配置 Servlet 和 Filter。这样做的缺点是监听器的 `initMethod` 可能在其他监听器之后调用。Java EE 6 增加了一个新接口 `ServletContainerInitializer`。实现 `ServletContainerInitializer` 的类在应用启动时其 `onStartup` 方法会被调用，此时尚未通知任何监听器。这是应用程序生命周期中最早的点。你不需要在部署描述符中配置 `ServletContainerInitializer`；相反，你使用 Java 的服务提供机制（SPI）来实现它的一个类，每个类存放在名为 `/META-INF/services/javax.servlet.ServletContainerInitializer` 的文件中。例如，以下文件列出了两个实现 `ServletContainerInitializer` 的类：

# 引导 Spring 框架 | 333

com.wrox.config.ContainerInitializerOne

com.wrox.config.ContainerInitializerTwo

缺点是，该文件无法直接存在于应用程序 WAR 文件或解压目录中——你不能将该文件放在 Web 应用程序的 `/META-INF/services` 目录下。它必须位于你应用程序 `/WEB-INF/lib` 目录下的 JAR 文件的 `/META-INF/services` 目录下。

Spring 框架提供了一个桥接接口，使得这一实现变得简单得多。`org.springframework.framework.web.ServletContainerInitializer` 类 `ServletContainerInitializer`，由于该类包含了服务提供者类列表，因此当你的应用程序启动时，它的 `onStartup` 方法会被调用。该类会扫描你对 `org.springframework.framework.web.WebApplicationInitializer` 的实现，并调用它找到的匹配类的 `onStartup` 方法。在 `WebApplicationInitializer` 的实现类中，你可以通过程序化配置监听器、Servlet、过滤器等，而无需编写一行 XML。更重要的是，你可以从这个类中引导 Spring。

```java
public class Bootstrap implements WebApplicationInitializer {
    @Override
    public void onStartup(ServletContext container) {
        XmlWebApplicationContext rootContext = new XmlWebApplicationContext();
        rootContext.setLocation("/WEB-INF/rootContext.xml");
        rootContext.addListener(new ContextLoaderListener(rootContext));

        XmlWebApplicationContext servletContext = new XmlWebApplicationContext();
        servletContext.setLocation("/WEB-INF/servletContext.xml");
        ServletRegistration.Dynamic dispatcher = container.addServlet(
            "Dispatcher", new DispatcherServlet(servletContext));
        dispatcher.loadOnStartup(1);
        dispatcher.mapping("/");
    }
}
```

这种引导方式与之前使用 Spring XML 的部署符引导具有功能等效性。下面的引导则使用 Spring Java 实现了纯 Java 的引导和配置过程。

```java
public class Bootstrap implements WebApplicationInitializer {
    @Override
    public void onStartup(ServletContext container) {
        AnnotationConfigWebApplicationContext rootContext = 
            new AnnotationConfigWebApplicationContext();
        rootContext.register(com.wrox.config.RootContextConfiguration.class);
        rootContext.addListener(new ContextLoaderListener(rootContext));

        AnnotationConfigWebApplicationContext servletContext = 
            new AnnotationConfigWebApplicationContext();
        servletContext.register(com.springframework.config.ServletContextConfiguration.class);
        ServletRegistration.Dynamic dispatcher = container.addServlet(
            "SpringDispatcher", new DispatcherServlet(servletContext)
        );
        dispatcher.setLoadOnStartup(1);
        dispatcher.addMapping("/*");
    }
}
```

当然，你不需要以相同的方式配置所有的上下文。你可以混合使用在引导 Spring 时的各种配置方法。下面的示例演示了这一点，同时也演示了如何在独立应用程序（如桌面应用或服务器守护进程）中引导 Spring。

```java
public class Bootstrap {
    public static void main(String... arguments) {
        ClassXmlApplicationContext rootContext = 
            new ClassXmlApplicationContext("com/wrox/config/rootContext.xml");
        FileSystemApplicationContext daemonContext = 
            new FileSystemApplicationContext(
                new String[]{"file/path/to/daemonContext.xml"}, rootContext);
        AnnotationConfigApplicationContext forkedProcessContext = 
            new AnnotationConfigApplicationContext(
                com.wrox.config.forkedProcessContext.class);
        forkedProcessContext.setParent(rootContext);
        rootContext.start();
        rootContext.registerShutdownHook();
        daemonContext.start();
        daemonContext.registerShutdownHook();
        forkedProcessContext.start();
        forkedProcessContext.registerShutdownHook();
    }
}
```

注意将 `rootContext` 注册为 `daemonContext` 和 `forkedProcessContext` 的父上下文，以及调用 `start` 和 `registerShutdownHook` 方法所需的额外工作。在 Web 应用程序中，`ContextListener` 和 `DispatcherServlet` 会自动配置父应用程序上下文，并在应用启动时调用 `start` 方法，在应用关闭时调用 `stop` 方法。在独立应用程序中，你必须手动调用 `start` 方法，然后在应用程序关闭时手动调用 `stop`。手动调用 `stop` 的替代方案是调用 `registerShutdownHook` 向 JVM 注册一个关闭回调，当 JVM 退出时自动停止应用程序上下文。

# Dispatcher Servlet 映射

你到为止看到的以及在本书后续将看到的示例，展示了将 `DispatcherServlet` 映射到 URL 模式 `/`。多年来，关于将 `DispatcherServlet` 映射到应用程序 URL 根目录存在很多困惑，在论坛、博客和其他技术网站上很容易找到关于它的错误或不完整的信息。

你可以将 `DispatcherServlet` 映射到你想要的任何 URL 模式。一些常见的方法将其映射到 `/do/*`、`.do` 或 `.action` URL 模式，有些网站将其作为 `*.html` 映射，让页面看起来比实际上更静态。然而，有一些重要的点需要注意。最重要的，不要将 `DispatcherServlet` 映射到 URL 模式 `/`。在大多数情况下，URL 模式必须以以星号开头或结尾；在映射到应用程序根目录时，不带星号的 `/` 是足够的，但不会启用 Servlet 容器的 JSP 机制来处理 JSP 请求。尾随星号会导致 Servlet 即使是内部 JSP 请求也发送到该 Servlet，这是不符合要求的（这是因为容器会将 JSP 处理器映射到你已映射的 Servlet 之上，导致其优先级较低）。

如果你计划将 `DispatcherServlet` 映射到应用程序根目录，请确保考虑了静态资源，如 HTML 页面、CSS 和 JavaScript 文件以及图像。一些在线教程演示了如何设置 Spring 框架来提供静态资源，但这样做并非必要。当任何 Servlet 映射到应用程序根目录（不带星号）时，更具体的 URL 模式将覆盖它。允许 Servlet 容器提供静态资源可以通过部署符如下实现：

```xml
<servlet-mapping>
  <servlet-name>default</servlet-name>
  <url-pattern>/*</url-pattern>
  <url-pattern>*.css</url-pattern>
  <url-pattern>*.js</url-pattern>
  <url-pattern>*.png</url-pattern>
  <url-pattern>*.jpg</url-pattern>
</servlet-mapping>
```

或者在 `ServletContainerInitializer (WebApplicationInitializer)` 中程序化实现：

```java
servletContext.getServletRegistration("default").addMapping(
  "/resources/*", "*.css", "*.js");
```

# 第 12 章：引入 Spring 框架

默认的 Servlet 不需要声明。Servlet 容器会替你隐含声明。这里显示的 URL 模式只是示例——你可以决定将静态资源放在哪里。

# 配置 Spring 框架



# 配置 Spring Framework

现在你已经知道如何引导 Spring 框架，准备好学习配置了。本书的剩余部分继续使用 XML 和程序化引导。你已经看到，可以使用 XML 或 Java 配置上下文。你不仅可以用不同的方式配置不同的应用程序上下文，还可以混合 Java 和 XML 配置单个上下文。这在现代应用程序中并不常见，但在某些情况下是必要的。例如，Spring 3.2 引入的 Java 配置没有涵盖所有的配置场景，因此书中第四部分的某些示例必须使用 Spring 的 XML 配置。此外，你在第 17 章学习的 Spring Web Services 支持 Java 配置。在使用这些工具的应用程序上下文时，你可以使用 Java 配置，但 Spring Security 或 Spring Web Services 需要使用 XML 配置。在本章中，你将学习所有内容。

本节使用了代码下载中的 `Spring-One-Context-XML-Config`、`Spring-XML-Config`、`Spring-Hybrid-Config` 和 `Spring-Java-Config` 项目。你可以在本节参考这些项目，也可以自己创建。这四个项目都有你在第一部分看到的相同的部署描述符代码。你将在书的其余部分继续使用模板部署描述符：

```xml
<display-name>Spring Application</display-name>

<jsp-config>
  <jsp-property-group>
    <url-pattern>*.</url-pattern>
    <url-pattern>*.jsp</url-pattern>
    <page-encoding>UTF-8</page-encoding>
    <scripting-invalid>true</scripting-invalid>
    <include-prelude>WEB-INF/jsp/base.jsp</include-prelude>
    <trim-directive-whitespaces>true</trim-directive-whitespaces>
    <default-content-type>text/html</default-content-type>
  </jsp-property-group>
</jsp-config>

<session-config>
  <session-timeout>30</session-timeout>
  <cookie-config>
    <http-only>true</http-only>
  </cookie-config>
  <tracking-mode>COOKIE</tracking-mode>
</session-config>

<distributable />
```

你还应该添加 `log4j2.xml` 以确保所有适当的消息都能进入你的日志。在接下来的示例中，消息会被写入控制台和日志文件，虽然大多数消息仅限于警告级别，但 `com.wrox`、`org.apache` 和 `org.springframework` 包中的类的日志级别被记录为 INFO 级别。

```xml
<root level="warn">
  <appender ref="Console" />
  <appender ref="WroxFileAppender" />
</root>
<logger name="com.wrox" level="info" />
<logger name="org.apache" level="info" />
<logger name="org.springframework" level="info" />
```

所有项目都包含了基础的 `GreetingService` 接口及其 `GreetingServiceImpl` 实现。

```java
public class GreetingServiceImpl implements GreetingService
{
    @Override
    public String getGreeting(String name)
    {
        return "Hello, " + name + "!";
    }
}
```

`HelloController` 在所有四个项目中都响应 Web 请求。你目前不需要担心这些类的语义、控制器中的注解或控制器-服务器模式。你很快就会学习到这些内容，但现在你应该记住，通过四个相同的基础项目，你可以以不同的方式配置 Spring Framework 并实现相同的目标。

```java
@Controller
public class HelloController
{
    private GreetingService greetingService;

    @ResponseBody
    @RequestMapping("/")
    public String helloWorld()
    {
        return "Hello, World!";
    }

    @ResponseBody
    @RequestMapping("/custom")
    public String helloName(@RequestParam("name") String name)
    {
        return this.greetingService.getGreeting(name);
    }

    public void setGreetingService(GreetingService greetingService)
    {
        this.greetingService = greetingService;
    }
}
```

你可能记得 Spring Framework 管理着 Bean，这是你使用 Spring Framework 时最主要需要配置的内容。你会编写其中一些 Bean，例如 `GreetingServiceImpl` 和 `HelloController`。其他一些是 Spring Framework 自带的默认框架 Bean，例如 Spring 的 `ApplicationContext`、`ResourceLoader`、`BeanFactory`、`MessageSource` 和 `ApplicationEventPublisher` 类的实现，这只是开始。

要告诉 Spring 如何配置这些 Bean，你使用 `<beans>` XML 命名空间，这在 `Spring-One-Context-XML-Config` 项目中已有演示。查看 `/WEB-INF/servletContext.xml` 文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xmlns:mvc="http://www.springframework.org/schema/mvc"
     xsi:schemaLocation="http://www.springframework.org/schema/beans
     http://www.springframework.org/schema/beans/beans-4.0.xsd
     http://www.springframework.org/schema/mvc
     http://www.springframework.org/schema/mvc/mvc-4.0.xsd">
<mvc:annotation-driven />

<bean name="greetingServiceImpl" class="com.wrox.GreetingServiceImpl" />

<bean name="helloController" class="com.wrox.HelloController">
  <property name="greetingService" ref="greetingServiceImpl" />
</bean>
</beans>
```

此 XML 文件告诉 Spring 实例化 `GreetingServiceImpl` 和 `HelloController`，并将 `greetingService` Bean 注入到 `helloController` Bean 的 `greetingService` 属性中。`<beans>` 元素是 Spring 配置的父元素。在其中可以使用任何其他 Spring 配置元素——通常情况下，你在 `<beans>` 元素使用的元素几乎总是会导致 Bean 的创建。你使用 `<bean>` 元素显式构建类的 Bean，并可以指定属于 `<bean>` 元素的构造参数和属性。`<mvc:annotation-driven>` 元素指示 Spring 使用 `@RequestMapping`、`@RequestBody`、`@RequestParam` 和 `@ResponseBody` 等注解将请求映射到控制器方法。使用 `<mvc:annotation-driven>` 元素会自动在后台创建 Bean，你现在不需要担心它们。它们的存在是为了便于将请求映射到控制器方法。你将在接下来的章节中学习更多关于这些框架 Bean 的知识。

## 使用 XML 配置引导 Spring

你可以使用 `@RequestMapping` 注解及其伙伴做很多事情，你可以在第 13 章探索这些内容。现在请理解 URL 路径被映射到 `HomeController` 的 `hello` 方法，而 URL 路径 `/custom` 映射到 `helloName` 方法。这些 URL 模式相对于 `DispatcherServlet` 的路径，而不是应用程序根 URL。然而，URL 模式的结果也相对于应用程序根。如果你将 `DispatcherServlet` 映射到 `/*`，`@RequestMapping` 注解中的模式不会改变，但在浏览器地址中它们将包含 `/do`。

你已经创建了 Spring 配置，但仍然需要引导它。对于部署描述符，如果需要，你可以直接使用 Java 启动。注意对默认 Servlet 的映射，这确保 Tomcat 处理静态资源。

```xml
<servlet-mapping>
  <servlet-name>default</servlet-name>
  <url-pattern>/*</url-pattern>
</servlet-mapping>

<servlet>
  <servlet-name>springDispatcher</servlet-name>
  <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
  <load-on-startup>1</load-on-startup>
  <init-param>
    <param-name>configLocation</param-name>
    <param-value>WEB-INF/servletContext.xml</param-value>
  </init-param>
</servlet>
<servlet-mapping>
  <servlet-name>springDispatcher</servlet-name>
  <url-pattern>/</url-pattern>
</servlet-mapping>
```

现在编译项目，启动 Tomcat，并在你喜欢的浏览器中访问 `http://localhost:8080/xml/`。你将在屏幕上看到文字“Hello, World!”。接下来，尝试 URL `http://localhost:8080/xml/custom?name=Nick`！你应该会在浏览器窗口中看到“Hello, Nick!”。修改 `name` 参数，输出应该随之变化。你的第一个框架应用程序运行正常了！

正如早些节讨论的，拥有两个应用上下文是理想的。你只创建了一个。典型的模式是将所有逻辑相关的类放在根上下文中，将控制器放在 servlet 上下文中。为了演示这一点，请使用 `Spring-XML-Config` 项目或自己进行修改。创建一个包含以下内容的 `rootContext.xml` 文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://www.springframework.org/schema/beans
     http://www.springframework.org/schema/beans/beans-4.0.xsd">

<bean name="greetingServiceImpl" class="com.wrox.GreetingServiceImpl" />

</beans>
```

然后你需要在部署描述符中添加 `ContextLoaderListener`：

```xml
<context-param>
  <param-name>configLocation</param-name>
  <param-value>WEB-INF/rootContext.xml</param-value>
</context-param>
<listener>
  <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>
```

现在你有两个应用上下文：根上下文包含 `greetingServiceImpl` Bean；而 `DispatcherServlet` 继承了根上下文所有的 Bean、`helloController` Bean 并初始化了注解驱动控制器。为了让事情更有趣，微调控制器中 `helloName` 方法的映射。

```java
@RequestMapping(value = "/", params = "name")
public String helloName(@RequestParam(name="name") String name)
```

此方法映射到与 `hello` 方法相同的 URL，但它要求请求中存在 `name` 参数。`name` 参数的存在与否决定了由哪个方法处理请求。为了证明这一点，编译并启动应用程序，尝试 `http://localhost:8080/xml/` 和 `http://localhost:8080/xml/?name=Nick` URL。

> **注意** 你可能注意到 Spring Framework 将日志写入调试控制台和你的 `application.log`。使用了 Log4j 吗？不是，Spring 使用 Apache Commons Logging 作为其日志 API。因为你的项目路径下有 `org.apache.logging.log4j:log4j-impl` 和 Commons Bridge，Spring Framework 输出到 Commons Logging 的事件会被 Log4j 获取并写入你的日志配置。INFO 及以上的消息出现是因为你在 Log4j 配置文件中将 `org.springframework` 的日志级别设置为 INFO。

## 创建混合配置

正如你所想象，使用 XML 配置 Spring Framework 可能会非常繁琐，而且之前的示例没有演示 `MultiActionController` 和 `SimpleUrlHandlerMapping` —— 这是在 Spring 4.0 中删除的用于映射请求到控制器的旧方法，它涉及极其冗余的 XML 和接受 `HttpServletRequest` 和 `HttpServletResponse` 的严格方法签名。在大型企业级应用中，你可以定义数百个 Bean，每个 Bean 都需要三或更多行 XML。这种配置方法看起来很快并不比在部署描述符中使用 XML 配置 Servlets 好到哪去。

如果你喜欢 XML 的显式化，但又不希望有那么长的配置文件——这些文件会变得极其难以维护——那么你可以创建一个结合了各方优点的混合配置。

这种混合配置的核心是组件扫描和注解配置的概念。使用组件扫描，Spring 会扫描你指定的包或多个包，以寻找特定的注解。任何（在这些包中）标记了 `@org.springframework.stereotype.Component` 的类都会变成由 Spring 管理，这意味着 Spring 会实例化它们并管理它们的依赖关系。



# 其他用于组件扫描的注解

任何被标记为 `@Component` 的注解都会成为组件注解，而任何被标记为另一个组件注解的注解也会成为组件注解。因此，标记了 `@Controller`、`@Repository` 和 `@Service`（它们与 `@Component` 在同一个包中）的类也会变成由 Spring 管理。你可以创建自己的注解。在第 17 章中，你将使用标记了 `@Controller` 的 `@RestController` 和 `@RequestMapping`，来区分普通控制器与 RESTful Web 服务控制器。

# 注入配置

起作用的另一个键是 `@org.springframework.beans.factory.annotation.Autowired`。你可以对任何私有的、受保护的或公共字段，以及接受一个或多个参数的公共方法使用 `@Autowired`。`@Autowired` 创建了 Spring 在实例化后应该注入的属性的依赖，也可以标记构造函数。通常，Spring 管理的 bean 必须有零参数实例化器，但如果类中存在单个 `@Autowired` 构造函数，Spring 将使用该构造函数并注入所有依赖。

在任何这些情况下，如果 Spring 无法为依赖项找到 bean，它会抛出并记录异常，且无法启动。同样，如果它为依赖项找到了多个 bean，你可以通过使用 `@org.springframework.beans.factory.annotation.Qualifier` 或 `@org.springframework.context.annotation.Primary` 注解来避免这个问题。当在 `@Autowired` 字段、方法或构造函数参数中使用时，`@Qualifier` 允许你指定应该使用的 bean 的名称。相反，你可以将标记了组件注解的 bean 标记为 `@Primary`，以指示当它是该依赖项的多个候选 bean 之一时优先使用它。

那么，你应该在字段、方法还是构造函数上使用 `@Autowired` 呢？这个争论已经持续多年。有些团队偏于 `@Autowired` 字段，因为涉及的代码最少。其他团队偏于 `@Autowired` 构造函数，因为这使得在不满足所有依赖项的情况下无法构造对象。其他人则偏于 `@Autowired` 修改器，因为这涉及代码，既避免了非私有字段，又让单元测试更简单，因为你不需要为了构造实例而 mock 每一个依赖。在现实世界中使用哪种方法完全取决于你，但在本书中，大多数情况下你会对字段进行注解，这样代码示例占用的页面会更少。

# 第 12 章 介绍 Spring 框架

> **注意**：Spring 框架也支持某些 Java EE 注解来代替其专有注解。`@javax.inject.Inject` 与 `@Autowired` 完全同义，不需要任何特殊操作即可使其工作。你可以像使用 `@Autowired` 一样使用 `@Inject` 标记任何字段、构造函数或方法。`@javax.annotation.Resource` 也与 `@Autowired` 同义。同样的，`@javax.inject.Name` 等同于 `@Qualifier`，并对 `@Autowired` 或 `@Inject` 属性具有相同的效果（Spring 也支持使用 `@javax.annotation.Metaannotation` 使用自定义限定符）。你使用哪些注解在很大程度上取决于你；然而，有一种理由是使用 `javax.*` 注解，无论你的应用程序如何依赖 Spring，都能在日后更容易切换到另一个框架。

正如本节前面提到的，Spring 会自动提供默认的框架 bean，有时你的 bean 需要这些 bean 的实例。通常，不建议使用框架 bean，因为这样做会将你的应用程序与 Spring 绑定，并使切换到其他东西变得困难。但当你想要使用强大的发布-订阅消息传递时，必须使用这些 bean。你可以要求任何这些 bean 被 `@Autowired` 或 `@jected`，Spring 会满足你，但许多人倾向于以不同的方式获取这些 bean，以降低与 Spring 的连接。为此，你有 `org.springframework.beans.factory.Aware` 接口。`Aware` 仅仅是供接口扩展的标记，表示对某些框架 bean 的感知。例如，`org.springframework.context.ApplicationContext` 为你的 bean 提供当前（而非父级）上下文的 `ApplicationContext` 实例。如果需要，可以通过调用 `ApplicationContext` 的 `getParent` 方法获取父上下文。

还有许多其他扩展 `Aware` 的接口，但一些最流行的包括：

- `ApplicationEventListener`：用于获取发布应用程序事件的 bean
- `BeanFactoryAware`：用于获取 `BitmapFactory`，你可以通过它手动检索或创建 bean
- `EnvironmentAware`：用于获取 `Environment` 对象，你可以用它从属性源获取属性
- `MessageSourceAware`：用于获取国际化消息源
- `ServletContextAware`：在 Java EE Web 应用环境中获取 `ServletContext`
- `ServletConfigAware`：在 `DispatcherServlet` 应用上下文管理的 bean 中获取 `ServletConfig`

在类的所有依赖项被注入之后、在它作为依赖项注入到任何其他 bean 之前，对类执行某种初始化也是理想的。这可以通过实现 `org.springframework.beans.factory.InitializingBean` 接口轻松实现。当 bean 的所有配置完成后（依赖已注入且 `Aware` 方法已调用），Spring 会调用其 `afterPropertiesSet` 方法。如果你不想将你的应用程序绑定到这个 Spring 专有接口上，可以创建一个恰好一个的标记了 `@javax.annotation.PostConstruct` 的公共零参数方法。它被调用的时间与通常的 `afterPropertiesSet` 相同。

无论你使用哪一种，如果你的 bean 声明了需要注入的依赖，它就会被调用。相反，如果你的 bean 在引用消失后需要关闭，你可以实现 `org.springframework.beans.DisposableBean`，或者创建一个标记了 `@javax.annotation.PreDestroy` 的公共零参数方法。

> **注意**：如果你比 `InitializingBean`、`@PostConstruct`、`DisposableBean` 或 `@PreDestroy` 提供更多对生命周期的控制，请查看 `org.springframework.context.Lifecycle` 和 `SmartLifecycle` 接口的 API 文档。

# 启动组件配置

使用现有的部署配置以及 `rootContext.xml` 和 `servletContext.xml` 文件是一个简单的任务。你可以在 Spring 混合文件中看到这一点。只需删除 bean 定义并将其替换为 `<context:annotation-config>` 和 `<context:component-scan>`：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xmlns:context="http://www.springframework.org/schema/context"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/beans-4.0.xsd
                           http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.0.xsd">

  <context:annotation-config />
  <context:component-scan base-package="com.wrox" />

</beans>
```

`base-package` 属性指示 Spring 扫描 `com.wrox` 及其任何子包中的所有类，寻找 `@Component`、`@Controller`、`@Repository` 和 `@Service`。`servletContext.xml` 配置文件仍然包含 `<mvc:annotation-enabled/>`。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xmlns:context="http://www.springframework.org/schema/context"
     xmlns:mvc="http://www.springframework.org/schema/mvc"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-4.0.xsd
                           http://www.springframework.org/schema/context http://www.springframework.org/schema/spring-context-4.0.xsd
                           http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc-4.0.xsd">

  <mvc:annotation-driven />

  <context:annotation-config />
  <context:component-scan base-package="com.wrox" />

</beans>
```

你仍然还有两个地方需要修改：

- 你必须告诉 Spring 实例化 `GreetServiceImpl`，因此要在该类上添加 `@Service` 注解。

```java
@Service
public class GreetServiceImpl implements GreetService
```

- 你需要告诉 Spring 将 `GreetService` 注入到 `HelloController` 中，在对应方法上添加 `@Autowired` 注解。

```java
@Autowired
public void setGreeting(GreetingService greetingService)
```

你可能已经注意到了此配置中的一个问题，你可以在启动 Tomcat 之前在 `setGreeting` 方法中设置断点来观察到这一点。这个断点会在 `HelloController` 和 `GreetServiceImpl` 的不同实例触发两次。事实上，你也可以在日志文件中看到这一点。Spring 实例化两次 `GreetServiceImpl` 和 `HelloController`：一次在根上下文，一次在 `DispatcherServlet` 的应用上下文。为什么会发生这种情况？

记住，组件扫描默认情况下会扫描所有的 `@Component`，而你在两个应用上下文中开启了组件扫描。你真正想要的是分离你的 bean。根应用上下文持有服务、存储库和其他逻辑部分，而 `DispatcherServlet` 的应用上下文应该包含 Web bean。幸运的是，你有一种简单的方法来更改默认的组件扫描算法。在 Spring 中，Spring-Hybrid-Config 项目已经为你完成了工作。首先，`rootContext.xml` 配置为扫描器添加了排除项：

```xml
<context:annotation-config />
<context:component-scan base-package="com.wrox">
  <context:exclude-filter type="annotation" expression="org.springframework.stereotype.Controller" />
</context:component-scan>
```

这个 `exclude-filter` 告诉 Spring 扫描 `@Controller` 之外的所有 Components。除了这个排除项，默认扫描模式仍然有效。`servletContext.xml` 配置采用了略有不同的方法，它使用白名单而不是黑名单来告诉 Spring 扫描哪些组件：

```xml
<mvc:annotation-driven />

<context:component-scan base-package="com.wrox" use-default-filters="false">
  <context:include-filter type="annotation" expression="org.springframework.stereotype.Controller" />
</context:component-scan>
```

在这种情况下，将 `use-default-filters` 属性设置为 `false` 告诉 Spring 忽略其标准扫描模式。与根上下文中指定的 `exclude-filter` 不同，`include-filter` 告诉 Spring 只扫描 `@Controller`。即使 `default-filters` 为 `true`，你仍然可以使用 `include-filters` 向默认扫描过滤器中添加内容。

尽管你已经从配置文件中删除了所有的 `<bean>` 定义，但你仍然可以将 `<bean>` 和组件扫描结合使用。你可能会遇到无法使用组件扫描来注册 bean 的情况。一个例子是由第三方注册一个类为 bean：因为你只编译了该类的一个版本，无法向其添加 Spring 注解。另一个例子是注册默认未注册的框架 bean，例如 Java Persistence API (JPA) 工具。在任何需要的时候，你都可以在配置中使用 `<bean>` 元素来补充 Spring 在组件扫描期间发现的内容。

编译应用程序并从 IDE 启动 Tomcat。访问：`http://localhost:8080/hybrid/` 和 `http://localhost:8080/?name=John`，你会发现应用程序的运行情况与你仅使用 XML 配置时完全一样。

# 使用 @Configuration 通过 Java 配置 Spring

如何配置 Spring 取决于个人偏好。某些开发团队倾向于 XML 文件的冗长和纯文本描述性。然而，使用 XML 配置 Spring 存在一些显著缺点：

- **XML 配置很难调试。** 你必须下载并将 Spring Framework 源码附加到你的项目中，并知道在何处设置断点以及如何单步执行。Spring 代码非常复杂，调试它绝非易事。
- **XML 配置无法进行单元测试。** 虽然你可以在单元测试中以程序化的方式启动 Spring 配置，但这并不是单元测试，因为这样做加载了整个应用上下文并接线了所有的 bean，它实际上是一个集成测试。如果基于 XML，你无法对 Spring 配置单元进行测试。

Spring Framework 的纯 Java 配置允许你通过程序化方式配置 Spring 容器，这样你就可以轻松地对配置的片段进行调试和测试。这对于那些不喜欢 XML 的开发团队也很有用。

在本章较早之前，你通过 `AnnotationWebApplicationContext` 探索了程序化的 Spring 配置。使用此类时，你通过 `register` 方法注册配置类。这些配置类（必须注有 `@org.springframework.context.annotation.Configuration` 注解且必须有默认构造函数）通过无参方法 `@Bean` 注册 bean。你可以使用 `@Configuration` 类实现许多强大的功能，更重要的是，你可以根据需要对每个方法进行单元测试和调试。

`@Configuration` 注解被元注解为 `@Component`，这意味着你的 `@Configuration` 类有资格使用 `@Autowired` 或 `@Inject` 进行依赖注入；可以实现任何一个 `Aware` 接口、`InitializingBean` 或 `DisposableBean`；并且可以拥有 `@PostConstruct`、`@PreDestroy` 方法。如果 `@Configuration` 类需要直接访问框架 bean，或者在 Spring 调用其 `@Bean` 方法之前注入两个多个依赖 bean，这些方法非常有用。

`@Configuration` 类也是 `@Component` 的事实意味着，如果组件扫描扫描了它们所在的包，你的 `@Configuration` 类会被自动拾取。这可能会产生意料之外的后果。

相反，如果你将应用程序划分为多个模块，每个模块都可以有自己的 `@Configuration`，你可以扫描所有模块的 `@Configuration`。这一点的关键点是，在结合 `@Configuration` 和组件扫描时应小心。



将配置外部化是理想的。例如，你的应用程序可能需要使用 JNDI 数据源，但你不希望硬编码数据源名称。相反，将数据源名称存储在配置时加载的某些文件中更好。使用 `org.springframework.context.annotation.PropertySource` 注解，你可以做到。

```java
@Configuration
@PropertySource({
    "classpath:wrox/config/settings.properties",
    "file:config.properties"
})
```

要访问属性源中的属性，你可以使用 `org.springframework.core.env.Environment` 实例手动获取值，或者使用 `org.springframework.beans.factory.annotation.Value` 注解映射注入的属性值。

```java
public class ExampleConfiguration {
    @Inject Environment environment;

    @Value("my.property.key") String myPropertyValue;
    ...
}
```

你可能无法不想将整个配置包含在一个类中。同样，你可能无法用 Java 配置一切。正如前面讨论的，某些工具可能仍需要 XML 配置。`org.springframework.context.annotation.Import` 和 `@ImportResource` 注解为这些需求提供了支持。

```java
@Configuration
@Import ({ DatabaseConfiguration.class, ClusterConfiguration.class })
@ImportResource("classpath:wrox/config/spring-security.xml")
public class ExampleConfiguration
{
...
}
```

## 配置 Spring Framework

在之前的代码段中，Spring Framework 将将 `ExampleConfiguration` 中包含的配置加载为 `DatabaseConfiguration`、`ClusterConfiguration` 和 `spring-security.xml` 中的配置。它不会按照特定的顺序初始化和执行这些配置；它会确定任何配置是否依赖于其他配置提供的 bean，并按照正确的顺序初始化配置以满足依赖关系。

Spring Framework 有许多你已经使用过的 XML 配置功能，这些功能不涉及 `<bean>`。这些功能允许你在启动前指定特定的框架 bean 定义，但让你以最少的精力进行配置，并包含如 `<mvc:annotation-drivers>` 和 `<context:component-scan>` 等内容。所有这些 XML 命名空间功能都可以使用一组配置注解来替换。你可以对任何标记了 `@Configuration` 的类使用以下注解来启用这些功能。你将在书的其余部分学习更多内容。

- `@ComponentScan` 替换了 `<context:component-scan>` 并允许在指定的包或多个包上扫描。与其对应项一样，你可以启用或禁用默认过滤器，并使用包含/排除规则来微调组件扫描算法。

- `@EnableAspectJProxy` 是 `<aop:aspect-autoproxy>` 的替换项，并允许使用面向切面的编程处理带有 AspectJ 的 `@Aspect` 注解的类以及相应的建议方法。

- `@EnableAsync` 替换了 Spring 的 `<task:*>` 命名空间部分，并启用 Spring 的异步方法执行。使用 `AsyncConfigurer` 接口时，你的 `@Configuration` 可以微调异步行为的配置。

- `@EnableCaching` 替换了 Spring 的注解驱动缓存管理功能，并替换了 `<cache:*>` 命名空间。

- `@EnableLoadTimeWeaving` 替换了 `<context:load-time-weaver>`。它更改了 `@Transactional`、`@Configurable`、`@Aspect` 等功能的方式。在大多数情况下你不需要这个功能，但如果你在使用 Java Persistence API 则需要。重要的是，它与 `@EnableAspectJAutoProxy` 是互斥的。

- `@EnableMBean` 是 `<context:bean-export>` 的替换项，并指示 Spring 将某些框架 bean 和标记了 `@ManagedResource` 的 bean 导出为 JMX Bean。

- `@Scheduling` 替换了 Spring 的 `<task:*>` 命名空间的剩余部分，并通过 `@Scheduled` 激活调度方法的执行，类似于由 `@EnableAsync` 启用的 `@Async` 方法执行。

- `@EnableSpringConfigured` 激活非 Spring 管理的 bean 对象中的依赖注入，并替换了 `<context:spring-configured>`。它需要加载时织入来支持此功能，因为它必须拦截对象的构造。

- `@EnableTransactionManagement` 替换了 `<tx:annotation-driven>` 并为标记了 `@Transactional` 注解的方法启用数据库事务管理。

- `@EnableWebMvc` 注解驱动的控制器请求映射并替换了 `<mvc:annotation-driven>`。这激活了一个非常复杂的配置，你通常必须对其进行自定义。你可以通过让你的 `@Configuration` 类实现 `WebMvcConfigurer` 或更多来自定义整个 Web MVC 配置，也可以通过扩展 `WebMvcConfigurerAdapter` 只自定义你需要的部分。

SpringConfig 项目演示了从 `WebApplicationInitializer` 引导到用于根和 DispatcherServlet 应用上下文的 `@Configuration` 类的纯 Java 配置。`GreetingService`、`GreetingServiceImpl` 和 `HelloController` 类已移动到 `com.wrox.site` 包，以便与 `com.wrox.config` 包中的配置类隔离开。这样，组件扫描就不会无意中检测到 `@Configuration` 类。

你项目中的第一个类 `RootContextConfiguration` 非常简单：

```java
@Configuration
@ComponentScan (
    basePackages = "com.wrox.site",
    excludeFilters = @ComponentScan.Filter(Controller.class)
)
public class RootContextConfiguration {
}
```

`ComponentScan` 注解告诉 Spring 扫描 `com.wrox.site` 包及其所有子包和部分。新的 `ServletContext` 类非常相似，关闭默认过滤器以仅扫描 `@Controllers` 并启用注解驱动的 Web MVC 功能。

```java
@EnableWebMvc
@ComponentScan (
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(Controller.class)
)
public class ServletContextConfiguration {
}
```

你可能注意到这两个类都没有 `@Bean` 方法。你现在需要的所有 bean 都是通过组件扫描和 `@EnableWebMvc` 自动配置的，因此你不需要任何 `@Bean` 方法。

> 注意：在下一节中，你将看到一个使用 `@Bean` 进行手动配置的示例，在书的其余部分，你将看到更多使用 `@Bean` 方法创建自定义 bean 的示例。

当然，这些配置类不能自己引导，`Bootstrap` 类实现了 `WebApplicationInitializer`。

## 利用 Bean 定义 Profile

```java
public class Bootstrap implements WebApplicationInitializer {
    @Override
    public void onStartup(ServletContext container) throws ServletException {
        container.getServletRegistration("default").Mapping("/resource/*");

        AnnotationConfigWebApplicationContext rootContext =
            new AnnotationConfigWebApplicationContext();
        rootContext.register(RootConfiguration.class);
        container.addListener(new ContextLoaderListener(rootContext));

        AnnotationConfigWebApplicationContext servletContext =
            new AnnotationConfigWebApplicationContext();
        servletContext.register(ServletContextConfiguration.class);
        ServletRegistration.Dynamic dispatcher = container.addServlet(
            "SpringDispatcher", new DispatcherServlet(servletContext)
        );
        dispatcher.loadOnStartup(1);
        dispatcher.addMapping("/*");
    }
}
```



# 利用 Bean 定义 Profile

## UTILIZING BEAN DEFINITION PROFILES

部署器中配置的参数、监听器和 `DispatcherServlet` 已经移除，`web.xml` 现在只包含 JSP 和 Spring 配置。

用于：

```java
@Autowired
private GreetingService greetingService;
```



类似于提供配置 profile 的其他工具（如 Maven），使用 Spring bean profile 有两个组件：声明和激活。你可以使用 XML 文件中的 `<beans>` 元素、`@Configuration` 类或两者来声明 profile。任何 `<beans>` 都可以包含 `profile` 属性来表示它属于特定的 profile。你不需要为每个需要的 profile 创建新的配置。部署器中配置的参数、监听器和 `DispatcherServlet` 已经移除，`web.xml` 现在只包含 JSP 和 Spring 配置。

## 理解 Profile 如何工作

在这个示例中，两个不同的 HyperSQL 数据库注册在不同的 profile 中。以下代码段演示了：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-4.0.xsd">

<beans profile="development, qa">
  <jdbc:embedded-database id="dataSource" type="HSQL">
    <jdbc:script location="classpath:wrox/config/sql/schema.sql" />
    <jdbc:script location="classpath:wrox/config/sql/test-data.sql" />
  </jdbc:embedded-database>
</beans>

<beans profile="production">
  <context:property-placeholder location="file:settings.properties" />
  <jee:jndi-lookup id="dataSource"
      java-ref-jndi-name="java:comp/env/${production.dsn}" />
</beans>

</beans>
```

```java
interface DataConfiguration
{
    DataSource dataSource();
}
```

```java
@Configuration
@Import({DevQaDataConfiguration.class, ProductionDataConfiguration.class})
@ComponentScan(
    basePackages = "com.wrox.site",
    excludeFilters = @ComponentScan.Filter(Controller.class)
)
public class RootContextConfiguration
{
}
```

```java
@Configuration
@Profile("development", "qa")
public class DevQaDataConfiguration implements DataConfiguration
{
    @Override
    public DataSource dataSourceBuilder() {
        return new EmbeddedDatabaseBuilder()
            .setType(EmbeddedDatabaseType.HSQL)
            .addScript("classpath:/com/wrox/config/sql/schema.sql")
            .addScript("classpath:/com/wrox/config/sql/test-data.sql")
            .build();
    }
}
```

```java
@Configuration
@Profile("production")
@PropertySource("file:settings.properties")
public class ProductionDataConfiguration implements DataConfiguration
{
    @Value("production")
    String dataSourceName;
}
```

```java
@Override
@Bean
public DataSource dataSourceLookup() {
    return new JndiDataSourceLookup()
        .setDataSource("java:comp/env/" + this.dataSourceName);
}
```

在声明了 profiles 后，你可以通过一种或多种不同的方式激活它们。首先，你可以使用 `spring.profiles.active` 上下文初始化参数：

```xml
<context-param>
    <param-name>spring.profiles.active</param-name>
    <param-value>development</param-value>
</context-param>
```

或者使用 Servlet 初始化参数：

```xml
<servlet>
  <init-param>
    <param-name>spring.profiles.active</param-name>
    <param-value>development</param-value>
  </init-param>
</servlet>
```

context 参数会影响 Web 应用内的所有 Spring 应用上下文，而 Servlet 初始化参数只影响设置了它的 `DispatcherServlet` 应用上下文。

你还可以使用 `-Dspring.profiles.active=development` 命令行参数来激活整个 Java 虚拟机中所有应用上下文的 profile。使用这些技术中的任何一种都可以指定多个要激活的 profile，并用逗号分隔（例如 `<param-value>profile1,profile2</param-value>, -Dspring.profiles.active=profile1,profile2`）。这当然意味着 profile 名称不能包含逗号。

你可以通过调用 `ConfigurableEnvironment` 上的 `setActiveProfiles` 方法来程序地激活一个或多个 profile：

```java
configurableEnvironment.setActiveProfiles("development");
configurableEnvironment.setActiveProfiles("profile1");
```

使用这种方法会影响包含环境的环境以及任何子应用上下文。使用 context 或 servlet 初始化参数或命令行属性通常更为常见。毕竟，如果你知道如何通过程序设置激活的 profiles，那你还需要 profiles 什么呢？然而，程序化设置 profiles 对于集成测试非常有帮助。

需要理解的一点是，`@Profile` 注解、`@Component` 可以作为元注解（meta-annotation）。这意味着你可以创建作为 `@Profile` 注解的自定义注解。例如，考虑以下注解：

```java
@Documented
@Retention(value=RetentionPolicy.RUNTIME)
@Target({ElementType.TYPE, ElementType.METHOD})
@Profile("development")
public @interface Development
{
}
```

自定义的 `@Development` 注解具有与 profile 名称 "development" 的 `@Profile` 注解相同的强制。现在，使用 `@Development` 等同于 `@Profile("development")`。这对于避免在代码中充斥字符串字面量的 profile 名称特别有用，因为字面量容易拼写错误，并且在你决定更改 profile 名称时也难以替换。

## 考虑反模式和安全考量

当你决定使用 bean 定义 profiles 来解决某个问题或需求时，应该记住一些重要的考量：

- 是否有更简单的方法来实现相同的结果？如果要在多个 profiles 中以不同的设置创建相同的 bean，那么很可能你可以使用属性源（property source）和一个或多个属性文件来实现这一目标。为此使用 profiles 通常是一种反模式，增加的复杂度超过了解决的问题。

- 你的 profiles 中存在哪些类型的 bean？在大多数情况下，两个 profiles 应该拥有大部分相同的 bean，尽管实现可能不同，或者开启了更多的调试、分析或报告功能。作为一般原则，QA 和生产 profiles 应该是几乎完全相同的，而开发和 QA profiles 之间的主要区别在于，你可能不会为它们开启所有功能。

- 使用 bean 定义 profiles 有什么安全影响？通常来说，你永远不应该使用 profiles 来控制应用程序的安全方面。因为终端用户可以通过简单的启用或禁用 JVM 属性来激活或禁用 profiles，他们可以轻松绕过以此方式定义的安全限制。在这种情况下，一个明显的反模式是在开发 profile 中禁用所有安全检查，但在 QA 和生产 profile 中启用它们。用户可以通过从生产环境切换到开发环境来避免购买你的应用程序。有方法可以避免这种情况，例如在生产构建期间剔除类或利用 Java SecurityManager，但最好的方法是完全避免这种情况发生。

### 总结

在本章中，你接触了 Spring 框架，并学习了 bean、应用上下文和 dispatcher Servlets。然后你尝试了引导和配置 Spring 框架的许多方法。你探索了依赖注入 (DI) 和控制反转 (IoC)、面向切面编程、事务管理、发布方法管理的概念。

# 13 用 Controllers 替换你的 Servlets

本章内容

- 什么是 `@RequestMapping`？

- 使用 `@RequestMapping` 缩小请求范围

- 使用 `@RequestMapping` 属性缩小请求匹配

- 使用 URL 限制

本章的 WROX.COM 代码下载

你可以找到以下示例：

- 模型-视图控制器 (Model-View Controller)

- Spring 表单 (Spring Forms)

本章的新 Maven 依赖

除了之前章节引入的依赖外，你还需要以下依赖：

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-web</artifactId>
  <version>4.0.2</version>
  <scope>compile</scope>
</dependency>
```

# 理解 @RequestMapping

在第 12 章中，你接触了 Spring 控制器以及如何使用 `@RequestMapping` 注解来映射请求。

`RequestMapping` 是 Servlet 工具包中极其强大的工具，它允许你根据请求的 URL、`Content-Type` 或 `Accept` 请求头、HTTP 请求方法、请求参数的存在或值，或者这些者的任何组合来映射请求。

通过 `@RequestMapping`，你不再需要在 Servlet 中编写复杂的 switch 语句或逻辑分支来选择方法。相反，请求会自动代表你路由到相应的控制器和方法。请求映射到相应的控制器和方法是通过各种 `@RequestMapping` 属性建立的。被映射的方法可以有任何名称、任意数量的参数以及多种返回类型。在本节中，你将学习所有这些能力。

## URL 限制

你已经使用过 `@RequestMapping` 根据 URL 缩小方法可以响应的请求。通过 `value` 属性（隐式或显式使用其他属性），你可以指定任何 Ant 风格的 URL 模式。这比 Servlet URL 映射灵活得多（Servlet 映射只能以通配符开头或结尾，且在 URL 中间不能多个通配符）。控制器方法映射是通过 Servlet URL 映射、控制器映射（如果适用）和方法映射构建的，并用斜杠分隔。为了演示，考虑映射到不同 URL 的以下方法：

```java
@RequestMapping("viewProduct")
public String viewProduct(...) { ... }

@RequestMapping("addToCart")
public String addProductToCart(...) { ... }

@RequestMapping("writeReview")
public String writeProductReview(...) { ... }
```

在这种情况下，如果你将 `DispatcherServlet` 映射到上下文根（/），那么这些方法的应用相对 URL 将分别变为 `/viewProduct`、`/addToCart` 和 `/writeReview`。假设你将 `DispatcherServlet` 映射到 `/store/*`，则这些方法的 URL 将变为 `/store/viewProduct`、`/store/addToCart` 和 `/store/writeReview`。

> 注意：如果你不熟悉 Ant 风格的模式，请花几分钟复习一下 Apache Ant 文档。

如果你发现控制器中的许多 URL 共享一个共同元素，可以使用映射继承来减少映射中的冗余：

```java
@RequestMapping("product")
public class ProductController
{
    @RequestMapping("view")
    public String viewProduct(...) { ... }

    @RequestMapping("addToCart")
    public String addProductToCart(...) { ... }

    @RequestMapping("writeReview")
    public String writeProductReview(...) { ... }
}
```

在这种情况下，如果 `DispatcherServlet` 映射到上下文根，URL 将变为 `/product/view`、`/product/addToCart` 和 `/product/writeReview`。同样，如果 `DispatcherServlet` 映射到 `/store/*`，URL 将变为 `/store/product/view`、`/store/product/addToCart` 和 `/store/product/writeReview`。

URL 映射的另一个重要方面是，如果请求匹配多个不同的映射，则最具体的映射获胜。因此，考虑以下映射：

```java
@RequestMapping("view/*")
public String viewAll(...) { ... }

@RequestMapping("view/*.json")
public String viewJson(...) { ... }

@RequestMapping("view/id/*")
public String view(...) { ... }

@RequestMapping("view/other**")
public String viewOther(...) { ... }
```

许多不同的 URL 可能会匹配这些方法中的某一个：

- URL `/view/other.json` 可能会匹配 `viewAll`、`viewJson` 或 `viewOther` 方法，但 `viewOther` 更具体，因此它被路由到那里。

- `/view/id/anything.json` 同样匹配 `viewAll`、`viewJson` 或 `view`，但它被映射到 `view`。

- 因为 `viewAll` 拥有这些方法中最不具体的映射，因此只有不匹配其他任何方法的请求会被路由到 `viewAll`。

使用这种技术，你可以创建一个通捕方法，来捕获任何其他未映射到控制器方法的请求：

```java
public class HomeController {
    @RequestMapping(value="**")
    public String catchall(...) { ... }
}
```

然而，这通常并不被推荐。当用户导航到你网站上的无效 URL 时，看到网站主页而不是 404 错误页面可能会导致困惑。如果 Spring Framework 找不到匹配请求的方法，它会自动响应 404 错误。如果你想自定义此错误页面，可以使用 `error-page` 部署描述符。



需要理解的一点是，`@RequestMapping` 属性也可以接受 URL 映射数组。通过这种方式，你可以将多个 URL 映射到给定的方法。在这个示例中，该方法响应 URL `/`、`/home` 和 `/dashboard`：

```java
@RequestMapping("/*", "home", "dashboard")
public String home(...) { ... }
```

虽然不是严格要求的，但即使你使用了其他属性，你通常也会使用 `value` 属性来将控制器方法映射到 POST 请求且不指定 URL，否则这几乎没有意义。

# HTTP 请求方法限制

你还可以使用 HTTP 方法来收窄到控制器方法的请求匹配。`@RequestMapping` 属性接受一个或多个 `org.springframework.web.annotation.RequestMethod` 枚举常量。如果控制器方法映射包含 `method` 属性的一个或多个值，则只有当请求的 HTTP 方法匹配指定的常量之一时，该请求才会映射到此控制器方法。在下面的示例中，你可能会发现使用 HTTP 方法将 URL 映射到不同的控制器方法特别有用：

```java
@RequestMapping("account")
public class AccountController {
    @RequestMapping(value="add", method=RequestMethod.GET)
    public String addForm(...) { ... }

    @RequestMapping(value="add", method=RequestMethod.POST)
    public View addSubmit(...) { ... }
}
```

# 理解 @RequestMapping

`/account/add` URL 同时匹配 `addForm` 和 `addSubmit` 方法。GET 请求该 URL 路由到 `addForm` 方法，而 POST 请求路由到 `addSubmit` 方法。使用任何其他 HTTP 方法对相同 URL 的请求将被拒绝。事实上，最佳实践是始终为每个映射指定支持的 HTTP 方法或方法。这使得配置你的应用程序变得困难，并且当一个应该作为 POST 请求提交的表单（如登录）不小心用 GET 请求提交时，显而易见。`RequestMethod` 支持 OPTIONS、GET、POST、PUT、DELETE、PATCH、TRACE。

重要的是，继承自类的 `method` 属性在两个级别上都是限制。请求的 HTTP 方法会先针对类级别的限制进行检查。如果通过了这些限制，然后会对方法级别的限制进行检查。下面的 `AccountManagementController`

```java
@RequestMapping(value="account", method={RequestMethod.GET, RequestMethod.POST})
public class AccountManagementController {

    @RequestMapping(value="add", method=RequestMethod.GET)
    public String addForm(...) { ... }

    @RequestMapping(value="add", method=RequestMethod.POST)
    public View addSubmit(...) { ... }
}
```

# 请求参数限制

`@RequestMapping` 的 `params` 属性是另一个在第 12 章中简要介绍的功能。通过此属性，你可以指定必须匹配的一个或多个参数。`paramValue` 表示参数必须存在，而 `!paramValue` 表示参数不能存在。空值是不允许的。下面的映射仅匹配参数存在且等于 `value` 的请求：

```java
@RequestMapping(value="can", params={"confirm=true"})
public String can(...) { ... }
```

需要理解，参数限制是继承的。Spring Framework 首先检查类级别的参数限制，然后检查方法级别的参数限制。

# 头部限制

使用 `@RequestMapping` 的头部限制与参数限制相同。你可以指定值或存在性，并用感叹号否定它们。注意头部名称匹配是不区分大小写的。下面的映射仅匹配 `X-Client` 且 Content-Type 为任意的请求：

```java
@RequestMapping(value="user", headers={"text/*"})
public User user(...) { ... }
```

# 内容类型限制

你可以使用请求类型或响应类型（或两者）进一步限制映射。虽然这些限制都可以通过 `headers` 属性实现，但 `consumes` 和 `produces` 属性让此任务变得更容易。

`consumes` 属性接受必须匹配请求 Content-Type 头部的一个媒体类型（通配符）。然后它定义了方法可以消费的内容。同样，`produces` 属性接受匹配 Accept 头部的一个或多个类型（通配符）。因此，它指定了方法可以产生的类型，以便 Spring 确定响应包含的内容。下面的映射仅匹配 Content-Type 为 `application/json` 或 `text/json` 且 Accept 头部匹配 `application/json` 或 `text/json` 的请求：

```java
@RequestMapping(value="json", consumes={"text/json", "application/json"}
produces={"text/json", "application/json"})
public Spring os(...) { ... }
```

如果在类 `@RequestMapping` 和方法 `@RequestMapping` 中都指定了，方法的 `consumes` 和 `produces` 属性将覆盖类的。换句话说，如果在方法中指定了，类的值将被忽略。

> 注意：内容类型限制是有用的，但并不总是实现内容协商的最佳方法。本章的“配置内容协商”部分将对此主题进行更详细的介绍。

# 指定方法参数

控制器方法可以有任意数量不同类型的参数。Spring Framework 对参数的数量和类型极其灵活。最简单的方法零参数，而复杂的方法可能有十几个甚至更多。Spring 可以理解这些参数的意图，并在调用时提供正确的值。此外，简单的配置可以扩展 Spring 理解的参数类型。

# 标准 Servlet 类型

需要时，Spring 可以为你的方法提供许多与 Servlet API 相关的类型参数。传递给这些参数的值永远不空，因为 Spring 保证了它们的值。你的方法可以指定这些参数类型中的任意或全部：

- `HttpServletRequest`，用于使用请求属性。
- `HttpServletResponse`，用于处理响应。
- `HttpSession`，用于操作 HTTP 会话。
- `InputStream` 或 `Reader`（二者选其一），用于读取请求体。在完成处理后，你不应该关闭此对象。
- `OutputStream` 或 `Writer`（二者选其一），用于写入响应体。在完成处理后，你不应该关闭此对象。
- 应使用客户端使用的 `java.util.Locale` 用于本地化目的（如果指定，则使用默认 locale）。
- `org.springframework.web.context.request.WebRequest`，用于在不直接使用 Servlet API 的情况下使用请求属性并操作 HTTP 会话。如果你在同一个方法中也拥有 `HttpServletRequest`、`HttpServletResponse` 或 `HttpSession` 类型的参数，则不应使用此参数类型。

## 注解修饰的请求属性

你可以使用多个注解（均位于 `org.springframework.web.bind.annotation` 包中）来指示方法参数的值应该从请求的某个属性中获取。在大多数情况下，标记有其中一个注解的参数可以是基本类型或基本类型包装类、`String`、`Class`、`Locale`、`Pattern`、`java.util.Properties`、`java.net.URL` 或这些类型的任何集合。Spring 会尽可能将值转换为该类型。你可以向 Spring Framework 注册自定义的 `java.beans.PropertyEditor` 或 `org.springframework.core.convert.Converters` 来处理其他类型。

`@RequestParam` 注解表示被注解的方法参数应该从具名的请求参数派生。你使用 `value` 属性（隐式或显式）指定请求名称。默认情况下，该注解表示请求参数是必需的，如果没有它，请求将无法映射。你可以将 `required` 属性设置为 `false` 来禁用此行为（使请求参数变为可选），在这种情况下，如果请求不包含该请求参数，则参数值值为 `null`。你还可以使用 `defaultValue` 属性指定在请求缺少参数时传递一个非 `null` 的值。以下方法接受一个必需的请求参数、一个带有默认值的可选 `name` 参数以及一个带有空字符串默认值的可选 `key` 参数。请求参数名称是敏感的。

```java
@RequestParam("user")
public String user(@RequestParam("id") long userId,
               @RequestParam(value="name", required=false) String name,
               @RequestParam(value="key", defaultValue="") String key)
{
    ...
}
```

> 注意：使用 `@RequestParam` 时，并不严格要求使用 `value` 属性指定请求参数名称。Spring Framework 会推断请求参数名称等于方法参数名称。然而，这只有当你的代码带有本地调试信息进行编译时才有效；否则 Spring 无法检测参数名称。作为启用调试符号的替代方案，Spring 还支持 Java 8 添加的新的参数名反射，这要求你使用 `-parameters` 命令行参数进行编译。如果你无法依赖这二者任一，则应该坚持显式指定参数名称。

如果你期望一个请求参数有多个值，请创建一个对应适用类型的数组或 `Collection`。

你也可以通过对 `Map<String, String>` 或 `org.springframework.framework.util.MultiValueMap<String, String>` 的单个参数标记 `@RequestParam`，将请求参数值包含在 `Map` 中。

`@RequestHeader` 在提供访问头值方面与 `@RequestParam` 相同。它指定一个必需的（默认）或可选的请求头来使用对应方法参数的值。HTTP 请求头也有多个值，如果你预计会有这种情况，应该使用数组或 `Collection` 参数类型。你可以对类型为 `Map<String, String, MultiValueMap<String, String>>` 或 `org.springframework.framework.http.HttpHeaders` 的单个参数标记 `@RequestHeader` 以获取所有请求头的值。在以下三个方法中，`bar` 和 `baz` 都通过名称获取头，而 `baz` 获取所有头。头名称不区分大小写。

```java
@RequestMapping("foo")
public String foo(@RequestHeader("Content-Type") String contentType,
    @RequestHeader(value="X-Custom-Header", required=false)
    Date customer)
{
}
```

```java
@RequestMapping("bar")
public String bar(@RequestHeader MultiValueMap<String, String> headers)
{
}
```

```java
@RequestMapping("baz")
public String baz(@RequestHeader HttpHeaders headers)
{
}
```

Spring Framework 中的 URL 映射不必是静态值。URL 可以包含一个模板，表示该 URL 是变量且在运行时是必需的。URI 模板变量通常对搜索引擎友好得多，并且是 RESTful Web 服务标准的一部分。下面的代码段演示了如何在 URL 映射中指定 URI 模板变量，并通过 `@PathVariable` 将该模板变量值作为方法参数使用。

```java
@RequestMapping(value="/{userId}", method=RequestMethod.GET)
public String user(@PathVariable("userId") long userId) { ... }
```

默认情况下，Spring 允许模板变量值包含除点以外的任何字符（正则表达式 `[\\.].*`）。你可以通过在 URL 映射中指定正则表达式来自定义此行为，以减少允许的字符或增加到点。下面的映射与上一个基本相同，但将 `userId` 模板变量限制为数字字符。只有不包含此变量或包含无效字符的请求才不会映射到控制器方法。

```java
@RequestMapping(value="user/{id\\d+}", method=RequestMethod.GET)
public String getUser(@PathVariable("userId") long userId) { ... }
```

URL 映射可以包含多个模板变量，每个变量都可以有一个关联的参数。此外，你还可以对 `Map<String, String>` 的单个方法标记为 `@PathVariable`，它将包含来自 URL 的 URI 变量值。

```java
@RequestMapping(value="foo/{var1}/bar/{var2}")
public String fooBar(@PathVariable("foo") String foo,
@PathVariable("bar") long bar) { ... }
```

RFC 3986 定义了 URI 参数的概念。与使用查询字符串和 URI 的查询参数不同，路径参数定义了路径的特定段。

例如，在 URL `http://www.example.com/hotel/43/floor/room1/guest` 中，路径参数 `floor` 和 `room` 属于路径段 `/43`（在这里可能是酒店 ID）。Servlet API 规范要求在匹配 Servlet 映射之前从 URI 中移除路径参数。对于酒店 URL，这意味着用于匹配到 Servlet 的 URL 实际上是 `/hotel/43/guest`。Spring Framework 在匹配请求到控制器方法时执行相同的操作。`MatrixVariable` 注解用于将路径参数提取为方法参数。类似于 `RequestParam`，`MatrixVariable` 有 `value`、`required` 和 `defaultValue` 属性。

```java
@RequestMapping(value="/hotel/{hotelId\\d+}/guest")
public String getForRoom(@PathVariable("hotelId") long hotelId,
@PathVariable("floor") short floorNumber,
@PathVariable("room") short roomNumber) { ... }
```

此映射匹配之前的酒店 URL。因为在匹配 URL 映射时会忽略路径参数，所以映射并没有声明这些参数。`MatrixVariable` 还有一个 `pathVar` 属性，用于指定哪个 URI 模板变量（`@PathVariable`）路径参数。然而，`pathVar` 属性是可选的。如果你的 URL 中只有一个路径包含给定名称的参数，则没有理由指定 `pathVar`。如果 URL 中有多个路径包含给定名称的参数，则必须指定 `pathVar` 以消除歧义你所引用的参数。下面的示例在语义上与之前的示例相同，但完全消除了歧义：

```java
@RequestMapping("hotel/{hotelId\\d+/guest*}")
public String getForRoom(@PathVariable("hotelId") long hotelId,
@PathVariable(pathVar="hotelId", value="floor") short floorNumber,
@PathVariable(pathVar="hotelId", value="room") short roomNumber)
{ ... }
```

## 输入绑定表单对象

在处理 HTML 表单时，客户端提交通常包含十个或更多字段。考虑一个用户注册表单，它可能包含用户名、密码、确认密码、电子邮件地址、姓氏、电话地址等。

虽然 `@RequestParam` 确实是一个非常有用的工具，但为方法编写几十个参数是非常冗长的，并且会让单元测试变得脆弱。相反，Spring Framework 允许你将表单对象（也称为命令对象）作为控制器方法的参数之一。表单对象通常是带有访问器和修改器方法的 POJO。它们不需要实现任何特殊接口，你也不需要为控制器参数标记任何特殊注解，Spring 就能将其识别为表单对象。

```java
public class UserRegistrationForm {
    private String username;
}
```



private String password;

private String emailAddress;

// 其他字段，以及修改器和访问器

}

```

在此示例中，Spring 会查找 `UserRegistrationForm` 类中以 set 开头的方法。它根据参数名称将请求参数映射到表单对象的属性上。例如，`setUsername` 使用请求参数 `username` 的值调用，`setEmailAddress` 使用请求参数 `emailAddress` 的值调用。如果请求没有匹配任何未被请求参数满足的表单对象属性，它们也会被忽略。同样，如果你有未被请求参数满足的表单对象属性，可以使用相同的 servlet 转换方法参数将字符串请求值转换为其目标属性类型。

Spring 还可以自动验证表单对象的详细信息，这意味着你可以避免在控制器方法中嵌入验证逻辑。如果你启用了 Bean 验证并在表单对象参数上标记了 `@javax.validation.Valid`，紧跟在表单对象参数之后的参数可以是 `org.springframework.validation.Errors` 或 `org.springframework.validation.BindingResult`。Spring 调用该方法时该参数的值就是验证过程的结果。如果紧跟在表单对象之后的参数不是 Errors 或 BindingResult 对象且对象验证失败，Spring 将抛出 `org.springframework.framework.web.bind.MethodArgumentNotValidException`。

```java
@RequestMapping(value="join", method=RequestMethod.POST)
public String join(@Valid UserRegistrationForm form, BindingResult validation) { }
```

对象验证如何工作以及如何启用它的详细信息将在第 16 章介绍。

## 请求体转换与实体 (Request Body Conversion and Entities)

到目前为止，你使用的与 `@RequestMapping` 配合的工具处理的是 GET 和 PUT 请求的传统特性：标头、URL 查询参数和 x-www-form-encoded 请求体（表单）。然而，POST 和 PUT 请求包含 x-www-form-encoded 以外格式的数据。例如，在 RESTful 服务中，POST 或 PUT 请求可能包含 JSON 或 XML 格式的体，以表示 x-www-form-encoded 无法表示的复杂数据。请求体还可以包含 base64 编码的数据，或者说任何客户端和服务器理解的格式。当这些数据代表某种对象时，它通常被称为请求实体（request entity）或 HTTP 实体（HTTP entity）。使用 `@RequestBody` 注解，Spring 会自动将请求实体转换为控制器方法。

```java
public class Account {
    public long accountId;
    public String accountName;
    public String emailAddress;
    // 其他字段，以及修改器和访问器
}

@RequestMapping("account")
public class AccountController {
    @RequestMapping(value="update", method=RequestMethod.POST)
    public String update(@RequestBody Account account) { ... }
}
```

默认情况下，`@RequestBody` 参数是必须的，但你可以使用 `required` 属性将其设为可选。请求实体使用 Spring 的 HTTP 消息转换器自动转换。其他参数类型（如 `@RequestParam` 和 `@RequestHeader` 参数）是简单类型，通过 PropertyEditors 和 Converters 自动从其字符串表示转换为目标；而请求实体必须具有专门的转换器，能够同时理解源格式（JSON、XML、二进制等）和目标格式（POJO 或复杂对象）。你将在第 17 章学到更多关于使用 HTTP 消息转换器的知识。

像对象一样，你也可以将 `@RequestBody` 方法参数标记为 `@Valid` 以触发内容验证，并可选地在参数后跟随 Error 或 BindingResult 参数。同样，如果验证失败且请求实体参数后没有 Error 或 BindingResult 参数，验证将抛出 `MethodArgumentNotValidException`。

```java
@RequestMapping(value="update", method=RequestMethod.POST)
public String update(@Valid BodyAccount account, BindingResult validation) { }
```

与其使用 `@RequestBody`，你的方法可以接收 `org.springframework.http.HttpEntity<?>` 类型的参数。该类型提供了对请求标头（HttpHeaders）和作为指定类型参数的请求体的访问。因此，你可以用以下内容替换之前的方法：

```java
@RequestMapping(value="update", method=RequestMethod.POST)
public String update(@HttpEntity<Account> request) { ... }
```

然而，请求体的验证并不会随着 HttpEntity 参数自动发生，因此使用它并没有真正具有吸引人的优势。

## 多部分请求数据 (Multipart Request Data)

在第 3 章中，你学习了如何在 Servlets 中使用 multipart。在浏览器环境中，你总是使用 `multipart/form-data`。在这些情况下，请求有一个指定的边界（boundary），并包含其自己的部分。如果字段是单个文件，其 Content-Type 为 `multipart/form-data`。如果字段是多个文件，请求的 Content-Type 为 `multipart/mixed` 并包含每个文件的部分。以下是一个包含单个文件的 multipart 请求示例，类似于使用 Wireshark 或 Fiddler 等网络工具看到的：

```
POST /upload HTTP/1.1
Host: www.example.org
Content-Type: multipart/form-data; boundary=X-RandomBoundary
Content-Length: 236
--X-RandomBoundary
Content-Disposition: form-data; name="username"
John
--X-RandomBoundary
Content-Disposition: form-data; name="file"; filename="sample.txt"
Content-Type: text/plain
--X-RandomBoundary--
```

为控制器方法标记 `@RequestMapping` 会导致从 URL 查询参数、urlencoded 请求体参数或 multipart 请求部分获取值。然而，PropertyEditors 和 Converters 仅从字符串值转换为简单文件。文件既不是字符串也不是简单类型。

`@RequestMapping` 注解可以标记任何应该来自 multipart 请求部分且应该由 HTTP 消息转换器而不是 PropertyEditor 或 Converter 转换的控制器方法。与许多其他注解一样，它还有一个默认值为 true 的 `required` 属性。

```java
@RequestMapping(value="form/upload", method=RequestMethod.POST)
public String upload(@RequestParam("username") String username, @RequestPart("uploads") Part part) { ... }
```

该方法可以处理之前演示的包含单个文件的 multipart 请求。这是因为 Spring 有一个识别文件部分的内置 HTTP 消息转换器。除了 `java.servlet.http.Part` 类型外，你还可以将文件上传转换为 `org.springframework.web.multipart.MultipartFile`。如果第二个请求字段允许多个文件，只需使用 Parts 或 MultipartFiles 的数组或集合即可。

```java
@RequestMapping(value="form/upload", method=RequestMethod.POST)
public String upload(@RequestParam("username") String username, @RequestPart("uploads") List<MultipartFile> uploads) { ... }
```

你并不局限于直接将 multipart 上作为控制器方法的参数。你的表单对象可以包含 Part 或 Multipart 字段，Spring 会自动知道它必须从文件部分获取值并妥善地转换这些值。

```java
public class UploadForm {
    private String username;
    private List<Part> uploads;
    // mutators and accessors
}

@RequestMapping(value="form/upload", method=RequestMethod.POST)
public String upload(Upload form) { ... }
```

到目前为止，你仅将 multipart 处理用于文件上传，但对于 Spring 请求处理而言，文件上传并不是支持的 multipart 内容。相反，请求不再是 `multipart/form-data`，而必须是 `multipart/mixed`。它的部分可以包含任何内容，包括 JSON、XML 或二进制格式的请求实体。Spring 可以将这些部分转换为任何它具有适当消息转换器（message converter）的类型。你甚至可以对非文件部分使用验证，就像你可以对来自浏览器上传文件的请求使用 `@RequestBody` 一样。

```java
@RequestMapping(value="update", method=RequestMethod.POST)
public String update(@RequestPart("account") Account account, BindingResult validation) { ... }
```

需要注意的是，以这种方式使用 multipart 请求是极不常见的。通常情况下，实体请求有一个部分主体；而 multipart 请求来自浏览器上传文件。

## 模型类型

在接下来的章节中，你将探索 Spring MVC 架构中的模型和视图。这里需要指出，你的控制器方法可能有一个类型为 `Map<String, Object>`、`org.springframework.ui.ModelMap` 或 `org.springframework.ui.Model` 的单一注解参数。这些类型之一的参数代表 Spring 传递给视图进行渲染的模型，在方法执行期间，你可以根据需要向其添加任何属性。

## 为控制器方法选择有效的返回类型

正如你所知的那样，Spring Framework 对于你可以指定的方法参数是非常灵活的。同样，Spring 对于你的控制器方法可以返回哪些类型也相当灵活。通常来说，虽然方法参数通常与请求内容有关，但返回类型通常与响应有关。例如，`void` 类型告诉 Spring 你的方法手动处理写入响应，因此 Spring 在你的方法返回后不再进行请求处理。然而，更常见的情况是，控制器方法返回某种类型（有时带有注解），指示 Spring 应该如何响应请求。

## 理解 @RequestMapping

### 模型类型

控制器方法可以返回 `Map<String, Object>`、`ModelMap` 或 `Model`。这是指定其中一种类型作为方法参数的替代方案。Spring 可以将此返回类型识别为方法，并根据配置的 `org.springframework.web.servlet.request.RequestViewNameTranslator`（默认为 `org.springframework.web.servlet.view.DefaultRequestToViewNameTranslator`）自动确定视图。

### 视图类型

为了指示 Spring 使用哪个视图渲染器，你的控制器方法可以返回多种视图类型。`org.springframework.web.servlet.View` 接口（或任何实现 `View` 的类）表示你的方法返回了一个显式视图。在方法返回后，请求处理将交给该视图。Spring 提供了几十种视图实现（例如 `RedirectView`），或者你也可以创建自己的。你的控制器还可以返回一个字符串，指示要解析的视图名称。你可以在下一节中学习更多关于视图解析的知识。最后，你的方法可以返回 `org.springframework.web.servlet.ModelAndView`。该类允许你同时返回一个视图和一个模型类型，或者一个字符串视图名称和一个模型类型。

### 响应体实体

就像请求可以包含 HTTP 实体（请求实体）一样，响应体也可以包含 HTTP 实体（响应实体）。控制器方法可以返回 `ResponseEntity<?>` 或 `org.springframework.http.ResponseEntity`，Spring 会根据协商的内容类型使用适当的 HTTP 消息转换器将实体体转换为正确的响应。`HttpEntity` 允许设置响应体和各种头部。`ResponseEntity` 扩展了 `HttpEntity`，增加了以 `org.springframework.http.HttpStatus` 形式设置状态码的能力。

```java
@RequestMapping(value="user/{userId}", method=RequestMethod.GET)
public User getUser(@PathVariable("userId") long userId) {
    User user = this.userService.getUser(id);
    return new ResponseEntity<>(user, HttpStatus.OK);
}
```

如果你不想使用 `HttpEntity`，可以返回主体对象并在方法上注解 `@ResponseBody` 来设置响应码（如果你使用 `@ResponseStatus`，则默认为 200 OK）。

```java
@RequestMapping(value="user/{userId}", method=RequestMethod.GET)
@ResponseBody
@ResponseStatus(HttpStatus.OK)
public User getUser(@PathVariable("userId") long userId) {
    return this.userService.getUser(id);
}
```

## 第 13 章用控制器替换你的 Servlets

在第 12 章中，你在其中一个示例使用了 `String` 返回类型配合 `@ResponseBody` 注解。由于指定了 `@ResponseBody`，对返回类型的其他处理器（如视图解析）会被忽略。正因如此，Spring 将该字符串作为该示例的实际响应体，而不是通过名称解析视图。`@ResponseBody` 的优先级始终高于所有其他方法返回值。

### 任何返回类型

你的方法可以返回任何对象，Spring 确保该对象应该是模型的一个属性。它将使用返回类型类名的驼峰命名（camelCase）作为模型属性，除非名称被注解了 `@ModelAttribute`，在那种情况下，Spring 将使用注解中指定的名称作为属性名。在任何情况下，Spring 都会使用 `RequestToViewTranslator` 自动确定值。在以下示例中，第一个方法的返回值将成为名为 `account` 的模型属性，第二个方法的返回值将成为名为 `user` 的模型属性。

```java
@RequestMapping("{userId}")
public User account(@PathVariable("{userId}") long userId) {...}

@RequestMapping("{userId}")
@ModelAttribute("user")
public User user(@PathVariable("{userId}") long userId) {...}
```



## 异步类型

除了之前列出的所有返回类型，控制器方法还可以返回 `java.util.concurrent.Callable<?>` 或 `org.springframework.web.context.request.async.DeferredResult<?>`。这些类型允许 Spring 在单独线程中执行 `Callable` 或 `DeferredResult`，从而释放请求线程。你通常会对耗时较长的请求这样做，特别是当它们在网络或 I/O 上花费大量时间时。如果不调用异步请求处理（`View`、`String`、`StringMap`、`ResponseEntity` 等），`Callable` 或 `DeferredResult` 的参数（返回类型）应该是你通常从控制器返回的类型。你可以在控制器方法上注解 `@ResponseBody`、`@ResponseStatus` 或 `@ModelAttribute` 以触发 `Callable` 或 `DeferredResult` 的适当处理器。

## 使用框架的模型视图模式

正如你所见，Spring Framework 对于你可以指定的方法参数是非常灵活的。同样，Spring 对于你的控制器方法可以返回哪些类型也相当灵活。通常来说，虽然方法参数通常与请求内容有关，但返回类型通常与响应有关。例如，`void` 类型告诉 Spring 你的方法手动处理写入响应，因此 Spring 在你的方法返回后不再进行请求处理。然而，更常见的情况是，控制器方法返回某种类型（有时带有注解），指示 Spring 应该如何响应请求。

## 模型类型

控制器方法可以返回 `Map<String, Object>`、`ModelMap` 或 `Model`。这是指定其中一种类型作为方法参数的替代方案。Spring 可以将此返回类型识别为方法，并根据配置的 `org.springframework.web.servlet.request.RequestViewNameTranslator`（默认为 `org.springframework.web.servlet.view.DefaultRequestToViewNameTranslator`）。

## 视图类型

为了指示 Spring 使用哪个视图渲染器，你的控制器方法可以返回多种视图类型。`org.springframework.web.servlet.View` 接口（任何实现 `View` 的类）表示你的方法返回了一个显式视图。在方法返回后，请求处理将交给该视图。Spring 提供了几十种视图实现（例如 `RedirectView`），或者你也可以创建自己的。你的控制器还可以返回一个字符串，指示要解析的视图名称。你可以在下一节中学习更多关于视图解析的知识。最后，你的方法可以返回 `org.springframework.web.servlet.ModelAndView`。该类允许你同时返回一个视图和一个模型类型，或者一个字符串视图名称和一个模型类型。

## 响应体实体

就像请求可以包含 HTTP 实体（请求实体）一样，响应体也可以包含 HTTP 实体（响应实体）。控制器方法可以返回 `ResponseEntity<?>` 或 `org.springframework.http.ResponseEntity`，Spring 会根据协商的内容类型使用适当的 HTTP 消息转换器将实体体转换为正确的响应。`HttpEntity` 允许设置响应体和各种头部。`ResponseEntity` 扩展了 `HttpEntity`，增加了以 `org.springframework.http.HttpStatus` 形式设置状态码的能力。

如果你不想使用 `HttpEntity`，可以返回主体对象并在方法上注解 `@ResponseBody` 来设置响应码（如果你使用 `@ResponseStatus`，则默认为 200 OK）。

## 任何返回类型

你的方法可以返回任何对象，Spring 确保该对象应该是模型的一个属性。它将使用返回类型类名的驼峰命名作为模型属性，除非名称被注解了 `@ModelAttribute`，在那种情况下，Spring 将使用注解中指定的名称作为属性名。在任何情况下，Spring 都会使用 `RequestToViewTranslator` 自动确定值。在以下示例中，第一个方法的返回值将成为名为 `account` 的模型属性，第二个方法的返回值将成为名为 `user` 的模型属性。

## 使用框架的模型视图模式

在接下来的章节中，你将探索 Spring MVC 架构中的模型和视图。这里需要指出，你的控制器方法可能有一个类型为 `Map<String, Object>`、`org.springframework.ui.ModelMap` 或 `org.springframework.ui.Model` 的单一注解参数。这些类型之一的参数代表 Spring 传递给视图进行渲染的模型，在方法执行期间，你可以根据需要向其添加任何属性。

在第 12 章中，你在其中一个示例中使用了 `String` 返回类型配合 `@ResponseBody` 注解。由于指定了 `@ResponseBody`，对返回类型的其他处理器（如视图解析）会被忽略。正因如此，Spring 将该字符串作为该示例的实际响应体，而不是通过名称解析视图。`@ResponseBody` 的优先级始终高于其他方法返回值。

在以下示例中，第一个方法的返回值将成为名为 `account` 的模型属性，第二个方法的返回值将成为名为 `user` 的模型属性。

Model-View-Controller 项目是以程序化的方式启动和配置的，正如你在第 12 章中学到的那样：`WebApplication` 启动了 Spring Framework，该框架通过两个 `@Configuration` 类 `RootContextConfiguration` 和 `ServletContextConfiguration` 进行配置。对于此项目，所有请求都映射到 `HomeController` 类。

本节涵盖了所有这些技术。你的应用程序可以使用其中任何一种、某些部分或全部控制器。你可以从 wrox.com 代码下载网站下载 Model-View-Controller 项目并跟进练习。

## 使用重定向视图

通常，你显式返回的最常见视图是 `org.springframework.web.servlet.view.RedirectView`，用于将客户端发送到不同的 URL。如果 URL 以协议（`http://` 等）或网络前缀（`//`）开头，则被认为是一个绝对 URL。如果 URL 是相对的（没有协议、前缀或开头的斜杠），则被认为相对于当前 URL（这是典型的 Web 和文件系统行为）。与直觉相反的是，`RedirectView` 将以正斜杠开头的 URL 视为服务器 URL，即应用上下文 URL（在几乎所有情况下，这并不是预期的行为）。因此，当你构造一个 `RedirectView` 时，启用上下文相关的 URL 是重要的，正如 `HomeController` 中的第一个方法所所示。

`RedirectView` 构造函数的第二个参数告诉 `RedirectView` 该 URL 是上下文相关的，不要在 URL 中渲染模板（`dashboardUrl`）。`RedirectView` 会用模型中的属性替换此类模板。或者在这种情况下，使用静态 URL 字符串构造视图（`new RedirectView("/dashboard", true)`）会更简单，这展示了 `RedirectView` 的威力。

视图重定向客户端到的最终 URL 实际上没有处理器，而 `HomeController` 中的方法处理了这个问题。

```java
@RequestMapping(value = "dashboard", method = RequestMethod.GET)
public String dashboard(Map<String, Object> model) {
    model.put("text", "This is a model attribute.");
    model.put("date", Instant.now());
    return "home/dashboard";
}
```

## 配置视图解析

为了将此视图映射到实际视图，Spring 需要一个可以理解它的 `ViewResolver` 实例。创建视图解析器是一个简单的任务，即在调度 servlet 应用上下文中实例化一个框架 bean。为了实现这一点，你应该使用 `InternalResourceViewResolver`，它可以将视图名称转换为 JSP 文件名。这是通过 `ServletContextConfiguration` 的 `viewResolver` 方法实现的。

```java
@Bean
public ViewResolver viewResolver() {
    InternalResourceViewResolver resolver = new InternalResourceViewResolver();
    resolver.setViewClass(JstlView.class);
    resolver.setPrefix("/WEB-INF/jsp/");
    resolver.setSuffix(".jsp");
    return resolver;
}
```

按照配置，视图解析器使用前缀 `/WEB-INF/jsp/` 加上视图名称以及 `.jsp` 来构建 JSP 文件名。你不需要做其他事情即可获得视图解析。注意，将 bean 命名为 `viewResolver` 是重要的，因此你也必须知道 `@Bean` 方法 `viewResolver`。

## 创建 JSP 视图

自然，通过配置的视图解析器和 `dashboard` 处理方法返回的视图名称，应用程序访问 `/WEB-INF/jsp/home/dashboard.jsp` 文件。这个 JSP 文件并没有特殊之处。你可以使用它内部所有的功能 - 脚本段、表达式、表达式语言、JSP 标签等，就像你在任何其他 JSP 中使用它们一样。注意 `@variable` 类型，这是你在第一部分中学过的，它可以帮助你的 IDE 为你的 JSPs 提供验证和代码建议。

```html
<!-- @variable id="text" type="java.lang.String"-->
<!-- @variable id="date" type="java.time.Instant"-->
<!DOCTYPE html>
<html>
<head>
    <title>Dashboard</title>
</head>
<body>
    Text: ${text}<br />
    Date: ${date}
</body>
</html>
```

在这种情况下，视图是简单的：它打印出模型上的两个属性。注意，你只需要使用 `HttpServletRequest` 属性就可以访问这些属性。你不需要做任何特殊处理，因为 `JView` 确保你的模型属性被暴露为 JSP 的 EL 变量。

## 使用模型属性使用隐式视图

如果控制器方法返回模型或模型属性，Spring 必须自动确定使用哪种视图。为了做到这一点，它需要一个与 `ViewResolver` 结合的 `RequestToViewNameTranslator`。

## 配置视图名称翻译

虽然你可以在需要时创建自己的 `RequestToNameTranslator`，但 `DefaultRequestToNameTranslator` 通常足够了。它会去除 Web 应用上下文和 URL 的任何文件扩展名。URL 剩余部分将成为视图名称。例如，URL `http://localhost:8080/mfc/mvc` 变为视图 `foo`，而 URL `http://localhost:8080/mfc/bar.html` 变为视图名称 `bar`。与 `ViewResolver` 一样，你只需要向 `ServletContext` 中添加一个 bean 来配置 `RequestToNameTranslator`。

```java
@Bean
public RequestToViewNameTranslator viewNameTranslator() {
    return new DefaultRequestToNameTranslator();
}
```

你可以通过各种方法自定义 `DefaultViewNameTranslator` 翻译名称的方式，但默认配置已经足够了。你必须将 bean 命名为 `nameTranslator`，因此你也必须命名 `@Bean` 方法 `viewNameTranslator`。

## 使用 @ModelAttribute

如果控制器方法返回模型或模型属性，Spring 必须自动确定使用哪种视图。为了做到这一点，它需要一个与 `ViewResolver` 结合的 `RequestToViewNameTranslator`。

`@ModelAttribute` 注解告诉 Spring 返回的内容应以属性键添加到模型中。如果没有该注解，Spring 将根据返回的类型使用默认名称。

```java
@RequestMapping("/user/home", method = RequestMethod.GET)
@ModelAttribute("currentUser")
public User userHome() {
    User user = new User();
    user.setUserId(123456789L);
    user.setUsername("adam");
    user.setName("Adam");
    return user;
}
```

配置名称翻译后，利用它是非常简单的。创建 `/WEB-INF/jsp/home.jsp`。

```html
<%--variable="currentUser" type="com.wrox.site.User"-->
<!DOCTYPE html>
<html>
<head>
    <title>User Home</title>
</head>
<body>
    ID: ${currentUser.userId}<br />
    Username: ${currentUser.username}<br />
    Name: ${currentUser.name}<br />
</body>
</html>
```



现在编译项目，从你的 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/mvc/user/home`。你应该能看到在 `HomeController` 中创建的用户 ID、用户名和名称。名称翻译和视图解析协同工作，检测并显示了正确的视图。

## 返回响应实体

获取请求实体和返回响应实体通常是留给 RESTful 服务或其他自动化任务的任务。在大多数情况下，只有当 JavaScript 应用向服务器发送 Ajax GET 或 POST 请求时，浏览器才会处于这些状况。出于此原因，HTTP 实体和内容协商将在第 17 章中详细介绍。本节涵盖了处理响应实体和转换的基础。

## 配置消息转换器

你已经学习了一种消息转换器，可能甚至没有意识到：`org.springframework.http.converter.FormHttpMessageConverter` 负责将 `x-www-form-urlencoded` 消息转换为控制器方法的表单对象。消息转换器的工作原理如下：它们可以将传入的消息转换为 Java 对象，并将 Java 对象转换为输出传出的消息。它们基于识别 MIME 类型和 Java 类型的简单原理运行。每个转换器都有一个或多个支持的 MIME 类型和 Java 类型，它可以将这些 MIME 类型的消息转换为相应类型的 Java 对象，反之亦然。这是内容协商过程的最后。当 Spring 建立协商的内容类型时，它会选择一个支持源和目标类型的转换器，并将其用于输入或输出实体。（在单个请求中，请求可能包含一种内容类型的消息，而服务器响应不同类型的消息）。

如果你没有配置任何内容，Spring 会为你自动创建某些消息转换器。在许多情况下，这种自动配置是足够的。为了演示和额外配置，Model-View-Controller 项目手动配置了消息转换器。为了实现这一点，`ServletContextConfiguration` 必须扩展 `WebMvcConfigurerAdapter` 并重写 `configureMessageConverters` 方法。

```java
public class ServletContextConfiguration extends WebMvcConfigurerAdapter {

    @Inject
    ObjectMapper objectMapper;

    @Inject
    Marshaller marshaller;

    @Inject
    Unmarshaller unmarshaller;

    @Override
    public List<HttpMessageConverter<?>> configureMessageConverters() {
        List<HttpMessageConverter<?>> converters = new ArrayList<>();

        converters.add(new ByteArrayHttpMessageConverter());
        converters.add(new StringHttpMessageConverter());
        converters.add(new FormHttpMessageConverter());
        converters.add(new SourceHttpMessageConverter<Object>());

        MarshallingHttpMessageConverter xmlConverter = new MarshallingHttpMessageConverter();
        xmlConverter.setSupportedMediaTypes(Arrays.asList(
            new MediaType("application", "xml"),
            new MediaType("text", "xml")
        ));
        xmlConverter.setMarshaller(this.marshaller);
        xmlConverter.setUnmarshaller(this.unmarshaller);
        converters.add(xmlConverter);

        MappingJackson2HttpMessageConverter jsonConverter = new MappingJackson2HttpMessageConverter();
        jsonConverter.setSupportedMediaTypes(Arrays.asList(
            new MediaType("application", "json"),
            new MediaType("text", "json")
        ));
        jsonConverter.setObjectMapper(this.objectMapper);
        converters.add(jsonConverter);

        return converters;
    }
}
```

`ByteArrayHttpMessageConverter`、`StringHttpMessageConverter`、`FormHttpMessageConverter` 和 `SourceHttpMessageConverter` 都是 Spring 会自动配置的转换器。它们按照正常顺序进行配置。顺序非常重要，因为某些转换器具有更广泛的 MIME 类型和 Java 类型范围，可能会掩盖你想要使用的其他转换器。

`MarshallingHttpMessageConverter` 通常不会添加到消息转换器列表中，但在这种情况下，为了支持与 XML 实体之间的相互转换。`MappingJackson2HttpMessageConverter` 通常会自动创建，因为 Jackson Data Processor 2 在于类路径中。它使用一个默认的、未配置的 `com.fasterxml.jackson.databind.ObjectMapper` 创建，并且只支持 `application/json` MIME 内容类型。这里的配置增加了对 `text/json` 的支持并提供了一个预配置的 `ObjectMapper`。

你一定注意到了 `org.springframework.oxm.Unmarshaller` 和 `ObjectMapper` 被注入到了配置类中，你可能在想它们从哪里来。为了让这些 bean 能够在应用程序范围内配置并共享，它们在 `RootContextConfiguration` 中进行了配置。`org.springframework.oxm.jaxb.Jaxb2Marshaller` 既是 `Marshaller` 也是 `Unmarshaller`，它同时满足这两个依赖项。

```java
@Bean
public ObjectMapper objectMapper() {
    ObjectMapper mapper = new ObjectMapper();
    mapper.findAndRegisterModules();
    mapper.configure(SerializationFeature.WRITE_DATES_AS_TIMESTAMPS, false);
    mapper.configure(DeserializationFeature.ADJUST_DATES_TO_CONTEXT_TIME_ZONE, false);
    return mapper;
}
```

```java
@Bean
public Jaxb2Marshaller jaxb2Marshaller() {
    Jaxb2Marshaller marshaller = new Jaxb2Marshaller();
    marshaller.setPackagesToScan(new String[] { "com.wrox.site" });
    return marshaller;
}
```

`Jackson ObjectMapper` 配置了一些重要的功能：首先让 Jackson 查找并注册所有的扩展模块，例如 JSR 310（Java 8 日期时间）支持模块。它禁用了将日期序列化为时间戳整数（这意味着它们将被写入为 ISO 8601 字符串），并禁用了将反序列化的日期调整为当前时区（这样没有时间的日期将被假设为 UTC）。`Jaxb2Marshaller` 的配置非常简单——它只是对带有 XML 注解的实体进行包扫描。

## 配置内容协商

内容协商是客户端向服务器发送一个响应类型列表（按偏好排序），服务器从中选择一个合适的内容类型（如果没有一个合适的，则选择默认值）。内容协商中最大且最具挑战性的部分是确定客户端想要以什么格式获取数据。如果请求包含该实体的 `Content-Type` 头部，那并不一定是客户端想要的格式（尽管通常是）。然后是 `Accept` 头部，用于指示客户端想要接受的格式。这里的关键是“格式（formats）”是复数；客户端可能会指示许多可以接受的格式，并对每个格式指定偏好或优先级。旧浏览器会发送令人混乱的 `Accept` 头部，用于决定是否打开 `text/html`，或者完全不打开。在安装了 Microsoft Office 的 Windows 7 机器上的 Internet Explorer 8 发送了包含 200 多种类型的 14 个 MIME 类型的 `Accept` 头部，其中没有一个是 `text/html`！

幸运的是，如今所有浏览器的最新版本发送的合理 `Accept` 头部至少包含 `text/html`。此外，当使用 JavaScript 应用或 RESTful Web 服务时，客户端对 `Accept` 头部具有完全控制权，使其成为协商内容类型时更可靠的因素。现实地说，服务器在内容协商中很少被调用。在所有情况下，对你的 Web 应用程序的请求将属于三类之一：

- 如果由于某点击链接或在浏览器地址栏输入地址引起的请求，目标是某个具有固定内容类型的资源，该资源不受协商影响——HTML 页面（`text/html` 或 `application/xml+xml`）、要下载的文件等。
- 如果来自客户端 JavaScript 浏览器程序的 Ajax 请求，客户端应用程序对 `Accept` 头部有完全控制权以执行内容协商。
- 如果是客户端应用程序访问你的 Web 服务，它对 `Accept` 头部有完全控制权以执行内容协商。

Spring 中的内容协商使用多步方法来确定要接收的内容。有时消息转换器用于请求，有时用于响应。当请求包含实体时，传入的消息转换器总是根据请求的 `Content-Type` 头部选择。当响应包含实体时，输出的消息转换器通过多步过程选择：

1. Spring 检查请求的文件扩展名。如果包含扩展名（例如 `.xml`、`.json` 等），则根据此确定请求格式。如果它不包含扩展名，或者扩展名无法识别，则继续下一步。
2. Spring 接下来检查请求参数。（你可以将其改为参数名。）如果存在，则使用该格式（html、json 等）。如果格式参数不存在或无法识别，则确定响应格式。
3. 最后，Spring 使用 `Accept` 头部来确定响应格式。

你可以根据需求定制整个过程。你可以完全消除一个或多个步骤，并更改步骤的工作方式以满足你的内容的需求。（然而，你不能重新排序步骤）。`ServletContextConfiguration` 类通过 `WebMvcConfigurerAdapter` 的 `configureContentNegotiation` 方法来实现这一点。

```java
@Override
public void configureContentNegotiation(ContentNegotiationConfigurer configurer) {
    configurer.favorPathExtension(true)
              .favorParameter(false)
              .parameterName("mediaType")
              .ignoreAcceptHeader(false)
              .useJaf(false)
              .defaultContentType(MediaType.APPLICATION_XML)
              .mediaType("xml", MediaType.APPLICATION_XML)
              .mediaType("json", MediaType.APPLICATION_JSON);
}
```

此配置启用了文件扩展名检查，禁用了参数检查，将参数设置为 `mediaType`（除非禁用了它否则没有必要，但这里是为了演示），并确保不忽略 `Accept` 头部。它禁用了 Java 激活框架 (JAF)——一种可以将文件扩展名映射到媒体类型的工具——转而采用手动指定支持的媒体类型。最后，它将默认内容类型设置为 `application/xml`，并增加了对 `application/xml` 和 `application/json` 的支持。

## 使用 @ResponseBody

现在内容协商已配置完成，你可以在控制器中使用它。`HomeController` 的 `getUser` 方法正是这么做的。

```java
@RequestMapping(value = "/user/{userId}", method = RequestMethod.GET)
@ResponseBody
public User getUser(@PathVariable("userId") long userId) {
    User user = new User();
    user.setUserId(userId);
    user.setUsername("john");
    user.setName("John Smith");
    return user;
}
```

注意 `@ResponseBody` 的使用，它触发了你配置的内容协商策略。此外，此方法使用 URI 模板变量和 `@PathVariable` 注解来从 URL 中获取用户 ID，而不是使用请求参数。现在编译应用程序，为你的 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/mvc/user/12`。你应该能看到以 XML 形式表示的用户（如图 13-1 所示），因为你的浏览器发送的 `Accept` 请求头中包含 `application/xml`，或者 `XML` 是你内容协商配置中的默认值。

![图 13-1](img/9c2d45f6d547f72cb870b3a991f62ef6_414_0.png)

如果你更改 URL 尾处的 ID，XML 将发生变化以反映新的 ID。现在访问 `http://localhost:8080/mvc/user/13.json`，呈现形式将从 XML 变为 JSON。（我建议你使用 Chrome 或 Firefox，因为 Internet Explorer 会提示你下载 JSON 文件。）你不需要更改控制器方法的 URL 映射，Spring 会识别扩展名，在请求映射时忽略它，并将其用于内容协商。如果你将扩展名从 JSON 更改为 XML，呈现形式将重新变回 XML。

> **注意**：`Jaxb2Marshaller` 可以将 `User` 对象序列化为其 XML 表达式，因为 `User` 类被标记了 `@javax.xml.bind.annotation.XmlRootElement` 注解。

## 使用表单对象让生活变得更轻松

在 Spring Framework 中，表单对象是你编写基于浏览器的 Web 应用时最大的便利之一。使用类型转换、列表以及将参数转换为业务对象可能会非常繁琐，而且随着业务对象属性的增加，这会变得更加复杂。使用对象非常简单，在 wrox.com 下载站点提供的 Spring-Forms 项目演示了使用简单的控制器和少量 JSP 视图是多么容易。

`UserManagementController` 拥有两个私有字段和一个用于生成用户 ID 的同步私有方法。为了开始，它还有一个名为 `displayUsers` 的请求处理方法用于显示现有用户列表。

```java
@Controller
public class UserManagementController {

    private final Map<Long, User> database = new Hashtable<>();
    private volatile long userIdSequence = 1L;

    @RequestMapping(value = "user/list", method = RequestMethod.GET)
    public String displayUsers(Map<String, Object> model) {
        model.put("list", this.database.values());
        return "user/list";
    }
}
```



private synchronized long nextUserId() {
    return this.userIdSequence++;
}

`User` 类是一个简单的 POJO，包含 `userId`、`username` 和 `name` 字段以及相应的变器方法。`/WEB-INF/jsp/user/list/list.jsp` 提供了一个添加新用户的链接，并使用 `<c:forEach>` 标签来循环并显示现有用户。

```jsp
<!--@variable id="userList" type="java.util.Collection<com.wrox.site.User>"-->
<!DOCTYPE html>
<html>
<head>
    <title>User List</title>
</head>
<body>
    <h2>Users</h2>
    <a href="<c:url value="/user/add">">new user</a><br />
    <br />
    <c:forEach items="${userList}" var="user">
      ${user.username}
      <a href="<c:url value="/user/edit/${user.userId}">">edit</a><br/>
    </c:forEach>
</body>
</html>
```

# 将表单对象添加到你的模型（Model）中

为了让你能够使用表单对象，它首先需要在显示表单的视图中是可访问的。`createUser(Map)` 方法向模型中添加了一个新的 `UserForm` 对象并返回 `user/add` 视图名称。你可能会奇怪为什么代码中同时使用了 `User` 和 `UserForm` 对象，这种怀疑是正确的。诚然，在某些情况下这是多余的。但它突显了你的业务对象并不总是和你的表单对象保持一致。

例如，你可能有很多你不想显示或不想让用户在编辑表单中看到的字段。此外，你对象中的字段格式或类型可能与你的业务对象不同。你甚至可能使用多个表单（以及多个表单对象）来编辑同一个业务对象。实际上，很多时候你必须分离表单对象和业务对象，而这演示了如何做到。

```java
@RequestMapping(value = "user/add", method = RequestMethod.GET)
public String createUser(Map<String, Object> model) {
    model.put("userForm", new UserForm());
    return "user/add";
}

@RequestMapping(value = "user/edit/{userId}", method = RequestMethod.GET)
public String editUser(Map<String, Object> model,
    @PathVariable("userId") long userId) {
    User user = userDatabase.get(userId);
    UserForm userForm = new UserForm();
    userForm.setUserName(user.getUsername());
    userForm.setName(user.getName());
    model.put("userForm", userForm);
    return "user/edit";
}
```

注意 `editUser(Map, long)` 方法向模型添加了 `userForm`。正如前面提到的，`@ResponseBody` 的使用触发了你配置的内容协商策略。

现在编译应用程序，为你的 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/mvc/user/12`。你应该能看到以 XML 形式表示的用户（如图 13-1 所示），因为你的浏览器发送的 `Accept` 请求头中包含 `application/xml`，或者 `XML` 是你内容协商配置中的默认值。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_414_0.png)

13-1

如果你更改 URL 尾处的 ID，XML 将发生变化以反映新的 ID。现在访问 `http://localhost:8080/mvc/user/13.json`，呈现形式将从 XML 变为 JSON。（我建议你使用 Chrome 或 Firefox，因为 Internet Explorer 会提示你下载 JSON 文件。）你不需要更改控制器方法的 URL 映射，Spring 会识别扩展名，在请求映射时忽略它，并将其用于内容协商。如果你将扩展名从 JSON 更改为 XML，呈现形式将重新变回 XML。

> **注意**：`JaxbMarshaller` 可以将 `User` 对象序列化为其 XML 表达式，因为 `User` 类被标记了 `@javax.xml.bind.annotation.XmlRootElement` 注解。

# 使用表单对象让生活变得更轻松

```jsp
<!--@variable id="userList" type="java.util.Collection<com.wrox.site.User>"-->
<!DOCTYPE html>
<html>
<head>
    <title>User List</title>
</head>
<body>
    <h2>Users</h2>
    <a href="<c:url value="/user/add">">new user</a><br />
    <br />
    <c:forEach items="${userList}" var="user">
      ${user.username}
      <a href="<c:url value="/user/edit/${user.userId}">">edit</a><br/>
    </c:forEach>
</body>
</html>
```

# 使用 Spring `<form>` 标签

# 获取提交的表单数据

当用户提交到你的控制器时，从该提交获取数据是简单的。`createUser(UserForm)` 和 `editUser(UserForm, long)` 方法都接收由 `FormSubmitMessageConverter` 从请求参数转换而来的 `SubmittedForm` 对象。

# 第 13 章 用控制器替换你的 Servlet

```java
@RequestMapping(value = "user/{userId}", method = RequestMethod.POST)
public View editUser(UserForm form, @PathVariable("userId") long userId) {
    User user = this.userDatabase.get(userId);
    user.setUsername(form.getUsername());
    user.setName(form.getName());
    return new RedirectView("/list", true, false);
}
```

现在编译应用程序，从 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/forms/user/list`。点击新链接并输入用户名和名称来创建一个新用户。添加一个或多个用户，并尝试编辑它们。你会发现 Spring 自动将你模型在模型中的 `UserForm` 对象绑定到视图中的字段上。在提交时，它会自动将请求参数转换为表单对象。这是 Spring MVC 的一个功能，你可以反复使用它，无论是贯穿于本书，还是贯穿于你未来开发 Spring Framework 应用期间。

# 更新客户支持应用程序

你现在应该看一眼从 wrox.com 下载网站提供的 Customer-Support-v10 项目。该应用程序与书中第一部分相比发生了巨大变化，它引入了 Spring Framework，将类移动到了 `com.wrox.site` 包，并用 Spring MVC 控制器替换了 Servlet。由于空间限制，本书无法重新打印整个项目。你应该理解其中的一些关键区别。

# 启用 Multipart 支持

首先，`Configurator` 类消失了。该类是一个 `ServletListener`，通过程序方式配置 `LoggingFilter` 和 `AuthenticationFilter`，以便它们按照正确的顺序执行。每当你通过程序配置 Servlet API 特性时，最好在单个类中进行。在本章和上一章中你需要了解的 `Bootstrap` 类是用于 `Configurator` 中使用的过滤器程序化配置的完美位置。此外，由于工单系统允许上传文件作为附件，现在配置的 `DispatcherServlet` 也配置了 multipart 支持。客户支持应用程序的 `Bootstrap` 类位于列表 13-1 中。

> **列表 13-1: Bootstrap.java**

```java
public class Bootstrap implements WebApplicationInitializer {
    @Override
    public void onStartup(ServletContext container) throws ServletException {
        container.getServletRegistration("default").addMapping("/resource/**");
        AnnotationConfigWebApplicationContext rootContext = new AnnotationConfigWebApplicationContext();
        rootContext.register(RootConfiguration.class);
        container.addListener(new ContextLoaderListener(rootContext));
        AnnotationConfigWebApplicationContext servletContext = new AnnotationConfigWebApplicationContext();
        servletContext.register(ServletContext.class);
        ServletRegistration.Dynamic dispatcher = container.addServlet("Dispatcher", new DispatcherServlet(servletContext));
        dispatcher.loadOnStartup(1);
        dispatcher.setMultipartConfig(new MultipartConfigElement(null, 20_971_520, 41_943_040L, 512_000));
        dispatcher.addMapping("/");
        FilterRegistration.Dynamic registration = container.addFilter("loggingFilter", new LoggingFilter());
        registration.addMappingForUrlPatterns(null, false, "/*");
        registration = container.addFilter("authenticationFilter", new AuthenticationFilter());
        registration.addMappingForUrlPatterns(null, false, "/", "/ticket/*", "/chat", "/chat/*", "/session", "/session/*");
    }
}
```

仅为 `DispatcherServlet` 启用 multipart 不足以让 Spring MVC 支持文件上传。Spring Framework 同时也支持旧版本的 Servlet API。回想起在 Servlet 3.0 之前，Servlet API 并没有内置 multipart 支持，也没有第三方工具来完成文件上传。Spring MVC 需要一个 `MultipartResolver` 实例来告诉它是使用 Servlet 3.0+ 的 multipart 支持还是第三方工具。`ServletContext` 类有一个额外的 `@Bean` 方法来创建该 bean，bean 必须是 `multipartResolver`。

```java
@Bean
public MultipartResolver multipartResolver() {
    return new StandardMultipartResolver();
}
```

# 将 Servlet 转换为 Spring MVC 控制器

`index.jsp` 文件已被删除并被 `IndexController` 替换。旧的 `SessionServlet` 被 `ListController` 替换。代码并没有太大区别，只是使用了 Spring MVC 控制器代替了 `HttpServletRequest` 和 `HttpServletResponse` 工具。

`LoginServlet` 已变成 `AuthenticationController`。这有所变化。不再由 `doGet` 和 `doPost` 方法检查请求参数的存在，而是每个操作都被替换为了简单的控制器方法。`ChatServlet` 变成了 `ViewController`，`TicketServlet` 变成了 `TicketController`。这些 Servlet 都使用了动作模式，即通过动作请求参数控制 `doGet` 或 `doPost` 方法的执行，导致为了确定执行哪个方法而产生了冗长的 `doGet` 和 `doPost` 方法。现在 Spring 使用 `@RequestMapping` 处理这些，消除了这些控制器中的大部分代码。

`TicketController` 使用表单对象进行工单订阅，该表单使用 Spring 的 `MultipartFile` 来方便地访问上传的文件。

```java
public static class Form {
    private String subject;
    private String body;
    private List<MultipartFile> attachments;
}
```

这使得处理器的代码比以前 Servlet 中的代码简洁得多。

```java
@RequestMapping(value = "create", method = RequestMethod.POST)
public View create(HttpSession session, Form form) throws IOException {
    Ticket ticket = new Ticket();
    ticket.setId(ticket.getNextId());
    ticket.setCustomerName((String) session.getAttribute("username"));
    ticket.setSubject(form.getSubject());
    ticket.setBody(form.getBody());
    ticket.setDateCreated(Instant.now());
    for (MultipartFile filePart : form.getAttachments()) {
        log.debug("Processing attachment.");
        Attachment attachment = new Attachment();
        attachment.setName(filePart.getOriginalFilename());
        attachment.setMimeType(filePart.getContentType());
        attachment.setContents(filePart.getBytes());
        if ((attachment.getName() != null && attachment.getName().length() > 0) ||
            (attachment.getContents() != null && attachment.getContents().length > 0)) {
            ticket.addAttachment(attachment);
        }
    }
    this.ticketDatabase.put(ticket.getId(), ticket);
    return new RedirectView("/ticket/" + ticket.getId(), true, false);
}
```



# 创建自定义视图

关于新的支持 Spring 的应用程序，你看到的最后一点是使用了用于下载的自定义 `com.wrox.site.DownloadView`。你可以在应用程序的任何地方使用此可重用视图将文件发送到客户端。

## 列表 13-2: DownloadView.java

```java
public class DownloadingView implements View {

    private final String filename;
    private final String contentType;
    private final byte[] contents;

    public DownloadingView(String filename, String contentType, byte[] contents) {
        this.filename = filename;
        this.contentType = contentType;
        this.contents = contents;
    }

    @Override
    public String getContentType() {
        return this.contentType;
    }

    @Override
    public void render(Map<String, ?> model, HttpServletRequest request,
        HttpServletResponse response) throws Exception {

        response.setHeader("Content-Disposition",
            "attachment; filename=" + this.filename);
        response.setContentType("application/octet-stream");
        ServletOutputStream stream = response.getOutputStream();
        stream.write(this.contents);
    }
}
```

这个下载视图大大简化了并且有一些硬编码的行为。在现实世界中，它可能有许多用于自定义的设置。它完成了任务，`ViewController` 中的一行代码即可将附件发送到客户端浏览器进行下载。

```java
return new DownloadingView(attachment.getName(),
    attachment.getMimeType(), attachment.getContent());
```

如往常，你可以通过编译项目、从 IDE 启动 Tomcat 并在你喜欢的浏览器中访问 `http://localhost:8080/support/` 来测试重构后的客户支持应用程序。通常的功能还有——列表、创建工单、图表等。对于用户来说，它看起来大相同，但它正朝着更好的设计的应用程序发展。

### 总结

本章涵盖了关于 Spring MVC 控制器和请求映射方法的大量信息。你学习了使用 `@RequestMapping` 的无限方式，以及用于许多其他注解和类型，以创建强大的控制器方法，这些方法可以处理并响应任何请求类型。你尝试了 Spring 对模型-视图-控制器（MVC）模式的支持，并设计了 Spring 可以从请求参数自动创建的表单对象。最后，你看到了重构后的跨国小部件公司（Multinational Widget Corporation）客户支持应用程序，它现在使用了 Spring Framework 和控制器，而不是带有 action 模式的 Servlets。然后，你学习了如何创建自己的 Spring View 以将文件下载推送到客户端浏览器。

在下一章中，你将探索服务（services）和仓库（repositories）如何进一步丰富你的应用程序；它们帮助将不同类型的程序逻辑分离到独立的层中，这些层可以抽象并模拟（mock），以进行独立测试。

# 14 使用服务和仓库支持你的控制器

## 本章内容

- 什么是模型-视图-控制器加上 控制器-服务-仓库？
- 使用根应用上下文而不是 Web 应用上下文
- 通过异步和定时执行增强服务
- 使用 WebSockets 进行逻辑分离

## 本章配套的 WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/projectjavawebapps` 的“Download Code”（下载代码）选项卡上找到本章的 wrox.com 代码下载。本章的代码分为以下主要示例：

- 讨论板项目（Discussion-Board Project）
- 客户支持 v11 项目（Customer-Support-v11 Project）

## 本章的新 Maven 依赖

除了之前章节引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-websocket</artifactId>
  <version>4.0.2.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

## 理解模型-视图-控制器加上 控制器-服务-仓库

在第 13 章中，你学习了用于用 Spring MVC 控制器替换 Servlets 的强大工具。你探索了 Spring Framework 中实现的模型-视图-控制器（MVC）模式。到目前，即使你以前从未见过这种模式，可能已经对它非常熟悉了。你可能已经注意到这种模式存在一个问题：尽管控制器比 Servlets 更整洁，但你的方法仍然可能会失控。到为止，你的业务逻辑是简单的：将提交的数据保存在内存中的某处。想一下当你在应用程序中创建或编辑时需要发生的所有其他事情：

- **验证**：数据需要以某种方式进行验证，以确保在创建时遵循了正确的规则。例如，某些字段可能不是可选的，或者其他字段可能有限制的值。
- **警报**：可能需要通过电子邮件、短信或手机通知发送有关更改的通知。
- **应用程序中的其他现有数据**：这些数据可能需要更改。以在线论坛系统为例，你通常会在每个论坛中看到帖子数以及最后一次发帖的用户和日期。然后，在论坛内部，每个帖子通常会显示回复数以及每个帖子回复的用户和日期。为了提高性能，回复的统计数据通常汇总到帖子中，而帖子的统计数据通常汇总到论坛中。因此，在向帖子添加回复时，你必须更新帖子和论坛数据。
- **数据持久化**：应用程序数据很少持久化在内存中。通常，它们存在于某种类型的数据存储中，例如关系型数据库、NoSQL 数据库或一组平面文件。持久化这些数据本身涉及一套逻辑，而这些逻辑可能非常复杂并消耗大量代码。

所以，考虑到所有这些，将所有逻辑都放在控制器中真的是最好的吗？考虑图 14-1，它展示了 MVC 系统中三个组件的基本操作。如果在创建一个完全符合你老板要求的精彩 Web 应用程序后，老板要求你向应用程序添加 RESTful 和 SOAP Web 服务，会怎样？你能重用为 Web 应用程序创建的控制器吗？可能不能。相反，你会发现自己正在对代码库进行大量的重构，以将用户界面逻辑从业务逻辑中分离出来。

### 识别不同类型的程序逻辑

用户界面逻辑是仅为支持特定用户界面而存在的逻辑。无论用户如何与应用程序交互都需要这段代码逻辑，该逻辑就是业务逻辑。如果这段代码逻辑仅针对特定的用户界面需要，它就是界面逻辑。在理想的应用程序中，你希望这些类型的逻辑分离到不同的层中。通过这样做，你可以轻松地更换用户界面，甚至可以同时利用多个用户界面，而无需更改任何业务逻辑。你还可以编写一个处理业务逻辑的库，并在 Web 和桌面应用程序中使用该库。

当将数据持久化到某种类型的数据存储时，有许多逻辑专门用于该数据的持久化，且与其它业务逻辑无关。*持久化逻辑*可以通过其在底层数据存储发生剧变时的无用性来识别。例如，当你从 MySQL 切换到 PostgreSQL 时，某些代码可能仍然必要，但如果你在切换到内存数据存储或 NoSQL 数据库时变得不再必要，那么它可能就是持久化逻辑。正如将用户界面逻辑与业务逻辑分离一样，你也应该将持久化逻辑与业务逻辑分离。这样就有两个优势：

- 如果你决定切换数据存储，可以在不更改业务逻辑的情况下完成。
- 测试业务逻辑变得简单得多，因为你可以模拟持久化层。

取决于应用程序的性质，你可能将持久化逻辑与业务逻辑分离。这样就有两个不同的优势：

- 如果你决定切换数据存储，可以在不更改业务逻辑的情况下完成。
- 测试业务逻辑变得简单得多，因为你可以模拟持久化层。

### 控制器提供用户界面逻辑

你已经熟悉了控制器、`@Controller`、`@RequestMapping` 的概念以及它们在 Spring MVC 中如何工作。在 Controller-Service-Repository 模式中，控制器是食物链的顶层。事实上，这三层系统可以很容易地比作自然界的食物链。在这个系统中，仓库是植物，从大自然（数据库）中吸收养分；服务是消耗仓库（植物生命）或其他服务（杂食动物）的消费者。继续这种类比并得出逻辑结论：控制器是肉食动物，它们消耗服务（杂食动物），但绝不直接消耗仓库（植物生命）或其他控制器。控制器以某种形式控制着用户界面，并在服务的帮助下，为视图（view）的展示准备模型。

在 MVC 范式中，服务和仓库被视为控制器的一部分（并非指 `@Controller`）。如图 14-2 所示。一个 `@Controller`、它所依赖的 `@Services` 以及位于这些组件之间的任何缓存层都共同作用，构成了模型-视图-控制器（MVC）模式中的控制器。所有这些组件都以某种形式使用模型。最终，`@Controller`（可以是用于 Web GUI 或 Web 服务 API）将模型的必要部分传递给视图进行渲染。该视图可以是 JSP（用于 Web GUI），也可以是 JSON 或 XML 渲染引擎（用于 Web GUI 或 Web 服务 API）。

### 使用根应用上下文代替 Web 应用程序上下文

想想你在过去两个章节中已经熟悉的 `ServletContextConfiguration` 类。当然，你可以把它做成任何你想要的的类型，但它的目的保持不变。作为 `DispatcherServlet` 的 Spring 应用上下文的配置，该类负责建立 Spring 在 Servlet 容器中接收 HTTP 请求时如何运行的规则。这一描述立即限制了该配置的范围。

在 Servlet 之外，`ServletContextConfiguration` 没有任何用。配置的内容反映了这一点。该类中的每个 Bean（bean）都从某种程度上与接收、处理和响应 HTTP 请求有关。如果你为应用程序创建一个 RESTful 或 SOAP Web 服务，你可能会创建一个独立的 `DispatcherServlet`，它有自己的应用上下文和 `@Configuration`，且该配置将与此上下文中处理请求的控制器不同。你可能会禁用不必要的 Bean，如 `ByteArrayHttpMessageConverter`、`StringHttpMessageConverter` 和 `FormHttpMessageConverter`，因为它们对于 RESTful 或 SOAP 服务不是需要的。你不需要像 `ViewResolver` 和 `RequestToViewTranslator` 之类的。

#### 为多个用户界面复用应用上下文

考虑到之前的讨论，请记住你的用户界面通常共享相同的服务。你的业务逻辑在所有用户界面中保持一致。为了实现这一点，你不应该在 Web 应用程序上下文中管理服务和仓库，而是在根应用上下文中，它是所有 Web 应用程序上下文的父级。所有服务和仓库都被控制各种用户界面的 Web 应用程序上下文继承。如果在某处你想使用为 Web 应用程序编写的服务和仓库创建一个桌面应用程序，你可以使用通过不同机制引导的根应用上下文配置。

你已经在第 12 章花费了大量时间学习应用上下文的层级结构和继承，使用 Web 应用上下文（`ServletContext`）对其进行配置（`RootContextConfiguration`），并修改组件扫描以仅扫描每个上下文中适当的组件。组件扫描是关键。如果你使用组件扫描，必须对其进行正确配置。否则，你可能会导致重复定义，更糟糕的是，某些定义可能无法被拾取。组件扫描基于两个原理：包扫描和类过滤。

当使用 `@ComponentScan` 注解时，你通过 `String[] basePackages` 属性告诉 Spring 扫描哪些 Java 包以寻找候选对象。Spring 定位所有属于这些包或子包的所有类，并对每个类应用资源过滤器。`basePackages` 的缺点是不是类型安全的，因此拼写错误很容易不被注意到。作为替代，你可以使用 `Class<?> baseClasses` 属性。Spring 从指定的类确定包名。

对于 Spring 在基础包中找到的每个类，它都会应用配置的过滤器。过滤器被分为包含过滤器（include filters）和排除过滤器（exclude filters）。如果该类触发了任何包含过滤器且没有触发任何排除过滤器，它就会变成一个 Spring Bean，这意味着它被构造、注入、初始化以及应用其他适用于 Spring 管理的 Bean 的操作。当 `@ComponentScan` 的默认 Filters 为 true 时（除非显式设置为 false，否则即为 true），没有排除过滤器，且只有一个包含过滤器。这个唯一的包含过滤器在类被标记为 `@Component` 或被标记为带有 `@Component` 元注解的注解时，对该类进行标记。因此，这两种组件扫描配置为：

```java
@ComponentScan(basePackages = "com.wrox.site")

@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(value = Component.class, type = FilterType.ANNOTATION)
)
```

如果你包含了或排除了过滤器，如果 `useDefaultFilters` 为 true，它们是在默认过滤器之外额外添加的。如果你将 `useDefaultFilters` 设置为 false，过滤器将替换默认过滤器。例如，你可以创建自己的注解集并告诉 Spring 扫描它们。你也可以分配类型过滤器，当一个类扩展或实现了指定的类或其中一个类时，该过滤器会被触发。另一种可能性是使用 `org.springframework.framework.context.annotation.FilterType.CUSTOM`，在这种情况下，类或...来自 `RootContextConfiguration`。

```java
@ComponentScan(
    basePackages = "com.wrox.site",
    excludeFilters = @ComponentScan.Filter(Controller.class)
)
```

此配置扫描 `com.wrox.site`，在没有默认过滤器的情况下，来自 `ServletContext`。

```java
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(Controller.class)
)
```



使用这些在不同上下文中的组件扫描实现了目标：业务逻辑和仓库集中在根应用上下文中，而界面逻辑位于每个被实例化的...

![](img/9c2d45f6d547f72cb870b3a991f62ef6_430_0.png)

## 将业务逻辑移动到服务

在理想的世界里，每个工程师都能从零开始编写。在现实世界中，你通常被要求处理不符合最佳实践的遗留应用程序。你不仅必须维护这些应用程序并解决用户反馈，还必须通过重构代码添加新功能。思考一个简单的看板以及它可能需要的业务逻辑。假设你没有类别或其他分类或分组讨论的方法，用户需要创建讨论和回复讨论的能力。在创建讨论时，你应该确保标题和内容为空。在回复讨论时，你应该检查回复的讨论的存在。

你的老板分配了你三个新任务：

- 用户要求在他们发布或回复时接收电子邮件。
- 用户还要求以 RSS 馈的形式查看看板和讨论。
- 服务器管理员想要自动删除一年前发布或回复的主题，以节省存储并提高性能。

思考为了支持这些新功能需要做的更改。每个讨论都需要一个回复过该讨论的用户列表，以便发送通知。正如通常情况，用户最终会取消订阅讨论，因此将此列表留在讨论上进行聚合要简单且成本更低。此外，每个讨论都需要一个日期字段，表示其回复的时间（如果没有回复，则为发布时间）。这些更改都带来了一个问题，因为这些对讨论的更新是在 `DiscussionController` 中触发的，但 `BoardController` 包含了保存记录的逻辑。你应该很快意识到，在处理任何这些任务之前，需要将业务逻辑与界面逻辑分离。你将在本节的剩余部分使用可下载的 Discussion-Board 项目来实现这一点。为了对界面类型有一个良好的了解，请查看 `BoardController` 和 `DiscussionController` 的请求处理器。不要担心这些代码。只需考虑接口即可。`BoardController` 包含了列表和创建讨论的方法。

```java
@Controller
@RequestMapping("discussion")
public class BoardController {

    @RequestMapping(value = {"list"}, method = RequestMethod.GET)
    public String listDiscussions(Map<String, Object> model) { ... }

    @RequestMapping(value = "create", method = RequestMethod.GET)
    public String createDiscussion(Map<String, Object> model) { ... }

    @RequestMapping(value = "create", method = RequestMethod.POST)
    public View createDiscussion(DiscussionForm form) { ... }

}
```

同时，`DiscussionController` 包含了查看讨论和回复讨论的方法。

```java
@Controller
@RequestMapping("discussion/{discussionId}:\\d+")
public class DiscussionController {

    @RequestMapping(value = {"**"}, method = RequestMethod.GET)
    public String viewDiscussion(Map<String, Object> model,
        @PathVariable("discussionId") long id) { ... }

    @RequestMapping(value = "reply", method = RequestMethod.POST)
    public ModelAndView reply(ReplyForm form,
        @PathVariable("discussionId") long id) { ... }

}
```

考虑你需要的支持的 POJOs。为了简单起见，假设用户是电子邮件地址，你可以用 `String` 代替简单的对象表示。你需要一个 `Discussion` 对象和一个 `Reply` 对象来持久化数据并传递给视图。

```java
public class Discussion {

    private long id;
    private String user;
    private String subject;
    private String uriSubject;
    private String message;
    private Instant created;
    private Instant lastUpdated;
    private Set<String> subscribedUsers = new HashSet<>();

    // 变器和访问器
}

public class Reply {

    private long id;
    private long discussionId;
    private String user;
    private String message;
    private Instant created;

    // 变器和访问器
}
```

为每个实体拥有一个服务似乎是逻辑性的。根据你对控制器的了解，`Reply` 接口应该是简单的。注意 `ReplyService` 没有根据 ID 获取单个回复的方法。目前没有这种业务需求。如果你以后需要添加编辑回复的功能，那么你就需要添加这个方法。

```java
public interface DiscussionService {
    List<Discussion> getAllDiscussions();
    Discussion getDiscussion(long id);
    void saveDiscussion(Discussion discussion);
}
```

```java
public interface ReplyService {
    List<Reply> getRepliesForDiscussion(long discussionId);
    void saveReply(Reply reply);
}
```

现在，你的服务实现并不重要。你已经可以重构控制器来使用服务的接口了。如果你查看 `BoardController` 的代码，可以看到它是是什么样的。它的方法只包含支持与用户交互的必要代码。特别是 `createDiscussion`，并没有设置 `Discussion` 的所有属性。它设置了用户提供的属性，让服务来设置生成的属性，例如 ID 和 URI 安全获取值。它不需要知道这是如何发生的，它不需要

```java
@Inject DiscussionService service;

@RequestMapping(value = "list", method = RequestMethod.GET)
public String listDiscussions(Map<String, Object> model) {
    model.put("discussion", this.service.getAllDiscussions());
    return "discussion/list";
}
```

```java
@RequestMapping(value = "create", method = RequestMethod.GET)
public String create(Map<String, Object> model) {
    model.put("discussionForm", new DiscussionForm());
    return "discussion/create";
}
```

```java
@RequestMapping(value = "create", method = RequestMethod.POST)
public View createDiscussion(DiscussionForm form) {
    Discussion discussion = new Discussion();
    discussion.setUser(form.getUser());
    discussion.setSubject(form.getSubject());
    discussion.setMessage(form.getMessage());
    this.discussionService.saveDiscussion(discussion);
    return new RedirectView("/discussion/" + discussion.getId() + "/" +
    discussion.getUriSafe(), true, false);
}
```

`DiscussionController` 的代码同样简单。大部分工作都委托给了 `DiscussionService` 和 `ReplyService`，让控制器只关注用户界面。

```java
@Inject DiscussionService discussionService;
@Inject ReplyService replyService;
```

```java
@RequestMapping(value = {"**"}, method = RequestMethod.GET)
public String viewDiscussion(Map<String, Object> model,
@PathVariable("discussionId") long id) {
    Discussion discussion = this.discussionService.getDiscussion(id);
    if (discussion != null) {
        model.put("discussion", discussion);
        model.put("replies", this.replyService.getRepliesForDiscussion(id));
        model.put("replyForm", new ReplyForm());
        return "discussion/view";
    }
    return "discussion/errorNoDiscussion";
}
```

```java
@RequestMapping(value = "reply", method = RequestMethod.POST)
public ModelAndView reply(ReplyForm form,
@PathVariable("discussionId") long id) {
    Discussion discussion = this.discussionService.getDiscussion(id);
    if (discussion != null) {
        Reply reply = new Reply();
        reply.setDiscussionId(id);
        reply.setUser(form.getUser());
        reply.setMessage(form.getMessage());
        this.replyService.saveReply(reply);
        return new RedirectView("/discussion/" + id + "/", true, false);
    }
    return new ModelAndView("discussion/errorNoDiscussion");
}
```

## 使用 Repository 进行存储

当你开始编写 `DiscussionService` 和 `ReplyService` 的实现时，你很快意识到许多必要的代码是用于保存数据和从数据库中检索数据的。为了保持服务代码的纯洁，最好是创建一个 Repository 层来处理数据持久化。这使得你的服务方法更加简洁且易于测试。`DiscussionRepository` 和 `ReplyRepository` 的接口是简单的，并且意所料的是，它们与服务接口非常相似。

```java
public interface DiscussionRepository {
    List<Discussion> getAll();
    Discussion get(long id);
    void add(Discussion discussion);
    void update(Discussion discussion);
}
```

```java
public interface ReplyRepository {
    List<Reply> getForDiscussion(long id);
    void add(Reply reply);
    void update(Reply reply);
}
```

现在你有了可以持久化数据的接口，可以实现这些服务了。`DefaultDiscussionService` 的 `getDiscussion` 没有任何额外的业务逻辑（尽管你可能需要它），但 `getAllDiscussions` 在返回之前对列表进行了排序，而 `saveDiscussion` 执行了一些有趣的任务。首先，它对主题进行消毒处理以确保 URI 安全，并将序列后的值设置为 `uriSafeSubject`。这在创建 URL 时使用，以对搜索引擎友好。它还更新了 `lastUpdated` 时间戳。如果讨论是新的，它会在添加讨论之前更新创建时间戳并订阅创建它的的用户；否则，它将更新讨论。

```java
Instant now = Instant.now();
disc.setLastUpdated(now);
```

```java
if (discussion.getId() < 1) {
    discussion.setCreated(now);
    discussion.addSubscribedUsers(discussion.getUser());
    this.discussionRepository.add(discussion);
} else {
    this.discussionRepository.update(discussion);
}
```

> 注意：`getAllDiscussions` 方法展示了 Java 8 lambda 表达式的威力，在某些情况下，在 Java 代码中进行此类排序可能是合适的。在大多数情况下，在数据库本身进行排序效率更高，通常你会在存储库层传递排序指令。

`DefaultReplyService` 的 `getRepliesForDiscussion` 方法在返回之前也会对仓库返回的列表进行排序。`saveReply` 同时使用了存储库和 `DiscussionService`（注意，这里再次使用了接口而不是实现类）来执行某些业务任务。如果回复是新的，它会将回复者订阅到该讨论，设置回复创建的时间戳并添加回复。如果不是新的，它仅更新回复。无论哪种方式，它都会使用 `DiscussionService` 保存讨论。这确保了遵循所有的业务规则。

```java
@Service
public class DefaultReplyService implements ReplyService {

    @Inject ReplyRepository replyRepository;
    @Inject DiscussionService discussionService;

    @Override
    public List<Reply> getRepliesForDiscussion(long discussionId) {
        List<Reply> list = this.replyRepository.getForDiscussion(discussion);
        list.sort((r1, r2) -> r1.getId() < r2.getId() ? -1 : 1);
        return list;
    }

    @Override
    public void saveReply(Reply reply) {
        Discussion discussion = this.discussionService.getDiscussion(reply.getDiscussionId());
    }
}
```

```java
@Repository
public class InMemoryDiscussionRepository implements DiscussionRepository {

    private final Map<Long, Discussion> database = new Hashtable<>();
    private volatile long discussionIdSequence = 1L;

    @Override
    public List<Discussion> getAll() {
        return new ArrayList<>(this.database.values());
    }
}
```



@Override
public Discussion get(long id) {
    return this.database.get(id);
}

@Override
public void add(Discussion discussion) {
    discussion.setId(this.getNextDiscussionId());
    this.database.put(discussion.getId(), discussion);
}

@Override
public void update(Discussion discussion) {
    this.database.put(discussion.getId(), discussion);
}

private synchronized long getNextDiscussionId() {
    return this.discussionIdSequence++;
}

# 使用根应用上下文代替 Web 应用上下文 | 403

`InMemoryRepository` 的趣味之处在于它的 `getDiscussion` 方法，它使用 lambda 表达式类似于 SQL 语句中的 WHERE 子句，用排除掉不属于所选讨论的回复。注意 `volatile` 关键字的使用，它确保了不同的线程能看到它们自己的 ID 序列值。

```java
@Repository
public class InMemoryRepository implements InMemoryRepository {
    private final Map<Long, Reply> database = new Hashtable<>();
    private volatile long replyIdSequence = 1L;
}
```

```java
@Override
public List<Reply> getDiscussion(long id) {
    ArrayList<Reply> list = new ArrayList<>(this.database.values());
    list.removeIf(r -> r.getDiscussionId() != id);
    return list;
}
```

```java
@Override
public synchronized void add(Reply reply) {
    reply.setId(this.getNextReplyId());
    this.database.put(reply.getId(), reply);
}
```

```java
@Override
public synchronized void update(Reply reply) {
    this.database.put(reply.getId(), reply);
}
```

```java
private synchronized long getNextReplyId() {
    return this.replyIdSequence++;
}
```

现在是时候测试这一切了。书中没有足够的空间打印所有的 JSP 视图，但它们都在 `Discussion-Board` 项目中，你可以查看一下。当你准备好后，编译应用程序并在你的 IDE 中启动 Tomcat；然后访问 http://localhost:8080/board/。尝试创建并回复各种讨论。当你对代码的运行感到满意时，回头看看它，想象一下如果你把所有这些代码都放在控制器中，代码会变得多丑——测试和扩展它又会有多困难。

由于你现在可以复用服务调用，创建用户请求的 RSS 视图的任务现在突然变得简单得多。这本书没有涵盖那个特定的任务，但请尽管自己去尝试完成它吧！

# 通过异步和调度执行改进服务

通过重构将业务逻辑与 UI 逻辑分离后，你仍然有两个任务需要处理：删除旧讨论和通知用户回复。花一分钟考虑这两个任务。你可能会意识到，自动删除旧讨论意味着没有用户交互，没有控制器可以调用服务方法来执行此任务。那么，是谁来调用这个方法呢？

此外，你可能没有考虑到，向多人发送关于回复的邮件需要多长时间。发送给用户的邮件不应该泄露其他用户的电子邮件地址——那是违反隐私的行为。同时，使用密送副本（BCC）是非常重要的。你可能没有考虑到，向多人发送关于回复的邮件需要多长时间。

```java
ThreadPoolScheduler scheduler = new ThreadPoolScheduler();
scheduler.setPoolSize(20);
scheduler.setThreadNamePrefix("task-");
scheduler.setAwaitTerminationSeconds(60);
scheduler.setWaitForTasksToCompleteOnShutdown(true);
scheduler.setErrorHandler(t -> logging.error(
    "Unknown error occurred while executing task.", t
));
scheduler.setRejectedExecutionHandler(
    (r, e) -> logging.error(
        "Execution of task {} was rejected for unknown reasons.", r, e
    )
);
return scheduler;
```

```java
@Override
public Executor getAsyncExecutor() {
    Executor executor = this.taskScheduler();
    log.info("Configuring asynchronous method executor {}", executor);
    return executor;
}
```

```java
@Override
public void configureTasks(ScheduledTaskRegistrar registrar) {
    TaskScheduler scheduler = this.taskScheduler();
    log.info("Configuring scheduled method executor {}", scheduler);
    registrar.setTaskScheduler(scheduler);
}
```

此处仅显示该类的新部分；现有部分已隐藏。`@EnableAsync` 中的 `proxyTargetClass` 属性告诉 Spring 使用带有异步或定时方法的代理类，而不是使用 Java 接口代理。这允许你在你的 Bean 上拥有未在接口中指定的异步或定时方法。如果你将此属性设为 `false`，则只有接口中指定的方法可以按计划执行或异步执行。`@Bean` 方法将执行器暴露为一个 Bean，你的任何 Bean 都可以使用它。在 `AsyncConfigurer` 中指定的 `@Async` 方法和 `configureTasks` 方法（在 `SchedulingConfigurer` 中指定）告诉 Spring 使用相同的调度器来执行异步方法执行和定时方法执行。

你可能立即纳闷这是如何实现的。`getAsyncExecutor` 和 `configureTasks` 分别调用了 `taskScheduler`，那么难道没有实例化两个 `TaskScheduler` 吗？当 Spring 调用 `@Bean` 方法时？实际上，只实例化了一个 `TaskScheduler`。Spring 会调用所有的 `@Bean` 方法，以便它们不会被调用超过一次。`@Bean` 方法的首次调用会被缓存并供以后的所有使用。这允许配置中的多个方法使用其他 `@Bean`。由于此原因，在此配置中仅实例化了一个 `TaskScheduler`，它被用于 Bean 定义、`getAsyncExecutor` 方法以及 `configureTasks` 方法中。当你执行后者时，这些方法中的日志语句将证明这一点。

# 创建和使用 @Async 方法

Spring Framework 通过将影响的 Bean 封装在代理中提供了对 `@Async` 方法的支持。当 Spring 在其他依赖于它的 Bean 中注入带有 `@Async` 方法的 Bean 时，它实际上注入的是代理，而不是 Bean 本身。这些 Bean 然后通过代理进行调用。对于普通方法，代理只是简单委托给底层方法。对于标记了 `@Async` 或 `javax.ejb.Async` 注解的方法，代理会指示执行器执行该方法然后立即返回。这种工作方式产生了一个重要的后果：如果一个 Bean 调用它自己的某个 `@Async` 方法，该方法将不会异步执行，这是无法修复的。由于此原因，如果你想异步调用一个方法，它必须是另一个对象。（而且，该对象必须是一个由 Spring 管理的 Bean。）

> 注意：这并不完全正确。对于基于 Java 接口的代理，你无法对其进行代理。但对于 CGLIB 代理，你可以通过重写原始类中的每个方法来对其代理。这就是配置 `@Bean` 缓存的工作原理——Spring 总是使用 CGLIB 对 `@Configuration` 类进行代理。因为你在这里启用了 CGLIB 代理，你可以在同一个类上使用 `@Async` 方法，它们将异步执行。然而，你不应该依赖这一点——配置更改可能会使其失效。

`Discussion-Board` 项目中的 `NotificationService` 和 `FakeNotificationService` 展示了这是如何工作的。注意，该方法在接口和实现中都标记了 `@Async`。这并不是严格要求的。然而，当目标是让所有实现都异步执行时，对接口进行注解被认为是礼貌的，以便让消费者知晓这一点。

```java
public interface NotificationService {
    @Async
    void sendNotification(String subject, String message,
        Collection<String> recipients);
}

@Service
public class FakeNotificationService implements NotificationService {
    private static final Logger log = LogManager.getLogger();

    @Override
    @Async
    public void sendNotification(String subject, String message,
        Collection<String> recipients) {
        log.info("Started notifying recipients {}.", recipients);
        try {
            Thread.sleep(5_000L);
        } catch (InterruptedException exception) { }
        log.info("Finished notifying recipients.");
    }
}
```

`DefaultReplyService` 获取一个 `@Injected` 的 `NotificationService`，并通过几行简单的代码，如果回复是新的，则调用异步方法 `saveReply`。

```java
Set<String> recipients = new HashSet<>(discussion.getSubscribedUsers());
recipients.remove(reply.getUser()); // 不需要给回复者发邮件
this.notificationService.sendNotification(
    "Replied post: *Someone replied to *" + discussion.getSubject(),
    recipients
);
```

# 使用 @Scheduled 方法

创建 `@Scheduled` 方法与 `@Async` 方法并没有太大区别。你只需要编写一个执行你想要的操作并对其进行注解。关于 `@Scheduled` 方法唯一需要注意的是，它们不能有任何参数。（Spring 如何知道使用什么作为参数？）仅仅因为一个方法是 `@Scheduled`，并不意味着你不能随时手动调用它，你只是不需要这样做即可。事实上，你可以对 `@Scheduled` 方法标记上 `@Async` 注解，这样如果它执行，就会异步执行。

`DefaultReplyService` 需要一个定时方法。为 `NotificationService` 添加一个方法。

```java
@Scheduled(fixedRate = 10000)
public void deleteStaleDiscussions() {
    Instant yearAgo = Instant.now().minus(365, ChronUnit.DAYS);
    log.info("Deleting stale since {}", yearAgo);
    List<Discussion> list = discussionRepository.getAll();
    list.removeIf(d -> d.getLastUpdated().isBefore(yearAgo));
    for (Discussion old : list)
        discussionRepository.delete(old);
}
```

框架。这就是为什么 `SessionRegistry` 曾经是一个包含静态方法的类。那么，`SessionListener` 是如何获取 `SessionRegistry` own 的呢？

你实际上有几种选择。其中一种是使用字节码插桩和面向切面编程（AOP），这在运行时是非常自动化的。你所做的就是对那些非 Spring 管理的类使用 `@org.springframework.beans.factory.annotation.Configurable` 注解，如果你想让它们在实例化时自动成为 Bean。然而，实现此点所需的配置相当复杂，而且你无法在解释其工作原理时隐藏所有的“魔法”。

或者，你可以在运行时通过编程方式将对象添加到 Spring 上下文中。你必须做的第一件事是从 `SessionListener` 中移除 `@WebEventListener` 注解，因为有了这个注解，监听器调用的顺序是不可预测的。相反，在 Bootstrap 类中通过编程配置监听器，以确保它在 Spring 的 `ContextLoader` 之后被调用。

```java
container.addListener(new ContextListener(rootContext));
container.addListener(SessionListener.class);
```

现在，你需要注册 `SessionListener` 以使其实现了 `ServletContextListener`。这样，`SessionListener` 就会在容器启动、Spring 启动后立即在 Spring 内部完成初始化。

```java
public class SessionListener
    implements HttpServletListener, HttpSessionListener,
    ServletContextListener {
    ...
}
```

你可以使用监听器中的 `contextInitialized` 方法从应用上下获取 Bean 工厂，并将 `SessionListener` 实例配置为根应用上下文中的 Bean。

```java
@Override
public void contextInitialized(ServletContextEvent event) {
    WebApplicationContext context =
        WebApplicationUtils.getRequiredApplicationContext(
            event.getServletContext());
    AutowireCapableBeanFactory factory =
        context.getAutowireCapableBeanFactory();
    factory.autowireBeanProperties(this,
        AutowireCapableBeanFactory.AUTOWIRE_BY_TYPE, true);
    factory.initializeBean(this, "sessionListener");
    log.info("Session listener initialized in Spring application context.");
}
```



当 `contextInitialized` 方法执行完毕后，`SessionRegistry` 的实现会被注入，`SessionListener` 立即开始使用它。

# 将逻辑层分离应用于 WebSockets

> **警告** 该监听器可能具备接线和其他功能的条件，但它并不是一个完整的 Spring Bean。其他 Bean 无法将该监听器 `@Autowired` 或 `@Injected` 到自身中，且调用 `ApplicationContext` 的 `getBean` 方法也不会返回该监听器。这是因为监听器从未被放置在应用上下文的 Bean 注册表中。你可以通过调用 Bean 工厂的 `registerSingleton` 方法部分解决这个问题，但某些服务仍然无法工作，例如调度方法执行和预构造/销毁回调方法。

# Spring WebSocket 配置器

正如你可能已经意识到的，WebSocket 服务器端点也是由容器管理的对象。因此，你可以使用处理 `SessionListener` 的相同技术来连接你的 WebSocket 服务器端点。你可能会奇怪，为什么 Spring 没有为 WebSocket 端点提供等于 Controller 的替代方案。问题的答案是：Controller 并不是已经抽象了底层连接细节的 Servlet 的灵活替代品。Java WebSocket API 已经很好地做了这一点，Spring 没有必要替换它。然而，为了避免每次实例化时都手动注册服务器端点（记住，每个连接都会获得一个新的端点），Spring 通过 `org.springframework.web.server.endpoint.SpringConfigurator` 为服务器端点提供了原生支持。

`SpringConfigurator` 类扩展了 `javax.websocket.server.ServerEndpointConfigurator`，以确保你的端点实例在调用任何事件或消息处理方法之前已正确初始化。通常情况下，你应该像下面的示例中那样使用 `SpringConfigurator` 声明你的端点：

```java
@Endpoint(value="{session}"), configurator=SpringConfigurator.class
```

然而，`ChatEndpoint.EndpointConfigurator` 无法将 `HttpSession` 暴露为用户属性，而 `ChatEndpoint` 使用了这个自定义配置器。因此，你只需要将自定义配置器改为扩展 `SpringConfigurator` 而不是 `ServerEndpointConfigurator.Configurator`。

```java
public static class ChatEndpointConfigurator extends SpringConfigurator {

    @Override
    public void modifyHandshake(HandshakeRequest request, HandshakeResponse response) { ... }
}
```

其实就此了。通过这个简单的更改，你的 `endpointConfig` 就可以拥有 `@Autowired` 或 `@Injected` 属性，并实现任何 Spring 接口（如 Aware 接口），就像一个原生 Bean 一样。然而，对于监听器，端点从未被放置在 Bean 注册表中，这意味着其他 Bean 无法访问它，无法用于预销毁生命周期通知或调度方法执行（尽管构造后方法可以工作）。如果你想让端点处于 Bean 注册表中并具备这些服务的能力，你可以在根应用上下文配置中声明端点的单例实例，而不是这样做：

```java
@Bean
public ChatEndpoint chatEndpoint() {
    return new ChatEndpoint();
}
```

当你这样做时，`@ServerEndpoint` 注解中指定的 `SpringConfigurator`（或其扩展类）不再为每个连接返回新实例。相反，它返回该单例实例来处理多个连接，就像 Servlet 或控制器一样。这需要进行细致的协调，因为如果你这样做，它将无法将 `Session`、`HttpSession`、`ChatSession`、`Principal` 和其他对象作为实例变量——它们被绑定到了方法的调用上。那么，使用单例 `ChatEndpoint` Bean 的好处是什么？首先，它消耗的内存更少，特别是当你有很多 WebSocket 连接时。此外，建立连接所需的时间更短，因为 Spring 只注入依赖而不是每个连接。在 `Customer-Support-v1` 应用中，端点并不是这样配置的，而是遵循每个连接一个实例传统模型。对于读者来说，将其重构为单例 Bean 是一个简单的练习。

# 记住：WebSocket 只是另一个业务逻辑接口

起初，在 WebSocket 端点中将业务逻辑与用户界面分离似乎非常困难。在某些方面，它非常像控制器，可以像控制器响应传入的 HTTP 请求一样响应每个传入的消息。诚承认，服务器端点可以在接收消息之前向客户端发送消息（这是控制器做不到的）会让情况变得复杂。界限变得模糊了。没有人告诉你该在哪里划线；只有你和你的组织可以做决定。然而，重要的是，无论你如何看待，WebSocket 都只是某个业务逻辑单元的另一个接口。服务可以从业务和用户界面的错综中提取出来。

记得之前的 `ChatEndpoint` 版本也实现了 `HttpSessionListener` 以接收聊天期间登录或会话的通知。当时的情况是，如果你在聊天中的独立窗口内注销会话，出于安全原因，聊天会结束。

然而，实现 `SessionListener` 是一个混乱的解决方案，因为容器创建了一个并未实际处理连接的 `ChatEndpoint` 单例实例，并且大量的静态字段来维护 `ChatEndpoint` 的 `Session` 到 `HttpSession` 链接的信息。幸运的是，有更清晰的方法来实现这一点。

```java
void registerOnRemoveCallback(Consumer<HttpSession> callback);
void deregisterOnRemoveCallback(Consumer<HttpSession> callback);
```

`ChatEndpoint` 有一个 `@Autowired` 的 `SessionRegistry`，并在其 `@PostConstruct` 方法中注册了回调。注意回调是使用 Java 8 方法引用（绑定）注册和注销的，这使得代码变得整洁得多。

```java
private final Consumer<HttpSession> callback = this::httpSessionRemoved;
```

...

```java
@PostConstruct
public void initialize() {
    this.sessionRegistry.registerOnRemoveCallback(this.callback);
}

private void sessionRemoved(HttpSession httpSession) {
    if (httpSession == this.httpSession) {
        synchronized(this) {
            if (this.closed) {
                log.info("Chat session ended abruptly by {} logging out.", this.principal.getName());
                this.close(ChatService.ReasonForLeaving.LOGGED_OUT, null);
            }
        }
    }
}

private void close(ChatService.ReasonForLeaving reason, String unexpected) {
    this.sessionRegistry.unregisterOnRemoveCallback(this.callback);
}
```

这段代码简洁得多，并且完全消除了对复杂的 Sessions 到 HttpSessions 以及 Sessions 映射表的需求。

> 注意：你可能会疑惑为什么 ChatEndpoint 使用了回调实例成员变量，而不是直接将 `this::HttpSessionRemoved` 传递给 `registerOnRemoveCallback` 和 `deregisterRemoveCallback` 方法。Java 中的方法引用（`this::something`）没有身份标识。正因为如此，传递给 `registerOnRemoveCallback` 和 `deregisterRemoveCallback` 的引用看起来是不同的实例，导致无法注销回调。使用 `callback` 实例解决了这个问题。

ChatEndpoint 还使用了一个调度方法 -- `sendPing` 每隔 25 秒发送一次消息。浏览器会响应 ping，如果很一段时间内没有活动，这会创建一个活跃连接。WebSocket 容器不会自动替你发送 ping，因此这由你的代码来完成。这将 Spring Framework 调度方法执行的完美应用，消除了对发送 ping 消息处理器的需求。然而，你不能仅仅为 `sendPing` 标记 `@Scheduled`，因为 Endpoint 不是一个 bean。Spring Framework 仅在单例 bean 上支持 @Scheduled，会忽略 ChatEndpoint 上的标记。

要解决这个问题，你需要直接使用 Spring 的 `TaskScheduler`。以下代码发送 ping 并接受 pong。在 Endpoint 构造后，它会调度 `sendPing` 在 25 秒后运行，之后每隔 25 秒运行一次。当连接关闭时，它会取消所有未来的 `sendPing` 执行。

```java
private static byte[] pongData =
    "This is PONG country.".getBytes(StandardCharsets.UTF_8);

private ScheduledFuture<?> pingFuture;

@Inject TaskScheduler taskScheduler;

private void sendPing() {
    if(this.wsSession.isOpen())
        return;
    log.debug("sending ping to WebSocket client.");
    try {
        this.wsSession.getBasicRemote()
            .sendPing(ByteBuffer.wrap(Endpoint.pongData));
    } catch (IOException e) {
        log.warn("Failed to send ping message to WebSocket client.", e);
    }
}

@OnMessage
public void onPong(PongMessage message) {
    ByteBuffer data = message.getApplicationData();
    if(Arrays.equals(Endpoint.pongData, data.array()))
        log.warn("Received pong message with incorrect payload.");
    else
        log.debug("Received good pong message.");
}

@PostConstruct
public void initialize() {
    this.pingFuture = this.taskScheduler.scheduleWithFixedDelay(
        this::sendPing,
        new Date(System.currentTimeMillis() + 25_000L), 25_000L);
}

private void close(ChatService.ReasonForLeaving reason, String unexpected) {
    if(!this.pingFuture.isCancelled()) {
        this.pingFuture.cancel(true);
    }
}
```

ChatService（在 `DefaultChatService` 中）处理业务逻辑，例如创建 `ChatSession` 对象（分配 ID）、维护待处理聊天会话列表以及将消息写入聊天日志。这使得 ChatEndpoint 只需要关注 WebSocket Session 对象以及发送和接收消息，并使用 `@Injected` 的 `ChatService` 来应用业务逻辑。

当将不同会话实例之间的 map 系统替换为用于用户的 WebSocket Session (`wsSession`) 和对对方的 WebSocket Session (`otherWsSession`) 的实例变量时，这是让 ChatEndpoint 变得不那么复杂的方法之一。实现这一点的一个挑战是，当客户客服代表连接并响应该会话时，通知请求聊天会话的用户。Java 8 的 lambda 通过简单地在 `ChatSession` 对象上声明事件处理器，使这一任务变得轻而易举。

```java
public class ChatSession {
    private Consumer<ChatSession> onRepresentativeJoin;

    public void setRepresentative(Representative representative) {
        this.representative = representative;
        if(this.onRepresentativeJoin != null) {
            this.onRepresentativeJoin.accept(representative);
        }
    }

    public void setOnRepresentativeJoin(Consumer<ChatSession> onRepresentativeJoin) {
        this.onRepresentativeJoin = onRepresentativeJoin;
    }
}
```

现在，当创建一个聊天会话时，客服使用一个简单的 lambda 表达式来响应支持代表加入会话的行为。当支持代表加入并调用 `setRepresentative` 方法时，这会触发回调，确保双方都了解对方。

```java
public void onOpen(Session session, @PathParam(sessionId) long sessionId) {
    if(sessionId < 1) {
        CreateResult result =
        this.chatService.createSession(this.principal.getName());
        this.chatSession = result.getChatSession(session);
        this.chatSession.setCustomer(session);
        this.chatSession.setOnRepresentativeJoin(
            s -> this.otherWsSession = s);
    }
    session.getBasicRemote().sendObject(result.createMessage());
} else {
    JoinResult result = this.chatService.joinSession(sessionId,
    this.principal.getName());
    if(result == null) {
        log.warn("Attempted to join non-existent chat session {}.",
            sessionId);
        session.close(new CloseReason(
            CloseReason.CloseCodes.UNEXPECTED_CONDITION,
            "The chat session does not exist!"
    ));
        return;
    }
    this.chatSession = result.getChatSession();
    this.chatSession.setRepresentative(session);
    this.otherWs = this.chatSession.getCustomer();
    session.getBasicRemote().sendObject(this.chatSession.getCreationMessage());
}
```



session.getBasicRemote().sendObject(result.getJoinMessage());

this.otherWs.getBasicRemote().sendObject(result.getJoinMessage());

}

# 416 | 第14 章 使用服务和仓库支持你的控制器

### 总结

在本章中，你探索了如何使用 Controller-Service-Repository 实现模型-视图-控制器模式。你学习了分离用户界面逻辑、业务逻辑和数据持久化逻辑是重要的，以及这种做法如何简化你的代码。更简单的代码更容易测试且通常更稳定，这应该是软件开发始终的目标。你还学习了如何分离这些层，并发现了 Spring Framework 为你提供的 `@Controller`、`@Service` 和 `@Repository` 注解。

在章节的后半部分，你发现了 Spring 提供的强大的异步和调度方法执行工具，并使用它们来完成任务，例如在后台发送电子邮件通知以及定期清除数据存储中的旧数据。最后，你学习了如何初始化非 Spring Bean 以及 Spring Framework 对 WebSocket 端点的支持。

在下一章中，你将重温一个旧话题，国际化和本地化，并了解 Spring Framework 如何极大地简化了准备应用程序进行全球分发的任务。

## 15
## 使用 Spring Framework i18n 实现应用程序国际化

本章内容

- Spring Framework i18n 的重要
- 使用 Spring 的国际化和本地化 API
- 配置 Spring 的国际化支持
- 如何使你的代码国际化
- 对 Customer Support 应用进行国际化

本章的 WROX.COM 代码下载

你可以在 `http://www.wrox.com/javaforwebbaps` 的 Download Code 选项卡找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Local-Application Project（本地应用项目）
- Customer-MAVEN-Support-v12 项目

本章的新依赖

本章没有新的 Maven 依赖。请继续使用之前所有章节中引入的 Maven 依赖。

## 为什么你需要 SPRING FRAMEWORK i18n？

在第 7 章中，你学习了如何使用 JSTL 国际化和格式标签库（fmt）进行国际化（i18n）和本地化（L10n）。如果你没有读过第 7 章，现在不需要专门回去阅读；但是，如果你不理解国际化、本地化或格式标签库，你应该回去阅读第 7 章中的“使用国际化和格式标签库”部分。该部分为你提供了国际化和本地化原理的入门概述，并介绍了如何使用格式标签库，其中涵盖了语言、区域和国家代码、变体、`Locale`（语言区域）以及 `TimeZone`（时区），你必须理解这些内容才能有效地使用 Spring Framework 的国际化支持。本章使用了其中许多概念和技术，但不会重复涵盖这些主题。

在本章中，你将探索 Spring Framework 的国际化和本地化设施，以及使用它们如何比直接使用容器设施简单得多。你将理解消息源（message sources）以及更多的 Spring JSP 标签，并最终将对 Customer 应用进行国际化和本地化。

## 让国际化变得更容易

你可能已经对国际化和格式标签库得出了结论：它并不算容易使用。首先，你必须在部署描述符、或 `ServletContainerInitializer` 或 `ServletContainerListener` 中，使用 `WEB-INF/classes` 中的 `java.servlet.jsp.fmt.localization` 上下文中配置你的资源包（bundles）。尽管你可能希望从其他地方获取它们（例如数据库，甚至只是另一个不同的文件），但资源包必须是 servlet 类路径上的类或文件。

此外，你必须实现一种检测用户想要使用的 locale 方法。`HttpServletRequest` 包含 `getLocale` 方法，它从 `Accept-Language` HTTP 请求头派导出 locale，并在缺少该头时返回默认 Locale，但这种机制仅在有限的情况下有效。用户必须使用配置了其首语言的计算机（并非总是如此，尤其是在公共电脑上），并且浏览器必须支持 `Accept-Language` 请求头（如今这很常见，但无法保证）。在确定 locale 后，你必须使用 `java.servlet.jsp.jst.Config` 类和 `Config.FMT_LOCALE` 常量来配置标签库使用该 locale。哦，别忘了在每个请求之间手动更改 locale 设置，这无法自动支持。

Spring 为所有这些任务提供了简化，使你能够投入更少精力来支持国际用户。除此，你可以在整个代码中使用 Spring 的 i18n 支持，而不仅仅是 JSP。Spring 的 i18n 支持级别在某些情况下将 i18n 支持封装到了 SE 和 EE 平台以及 JSTL 中。在本章中，你将学习所有这些功能以及更多内容。你还将学习它们所赋予力量的国际化和本地化概念。

## 直接本地化错误消息

Java SE 和 EE 国际化的缺点之一是对字符串作为本地化键的严格依赖。为了确保无一失，你最终必须查找错误代码，而最简单的方法就是使用字符串。然而，如果像 `Throwable` 和验证错误对象这样的内容可以直接传递给本地化 API，而无需在查找本地化消息之前始终调用来确定错误，那么情况就会变得更容易。使用 Spring Framework 的 `MessageSourceResolvable` 做到。你可以将任何实现此接口的对象传递给任何 Spring i18n API 并自动解析它。在“使你的代码国际化”章节中，你使用它采用了一种可靠的模式来处理、记录和传播异常。在第 16 章，你将使用它为有效的 bean 验证错误提供更多功能。

## 使用基础国际化和本地化 API

在深入实现应用程序的国际化之前，你应该熟悉一些基础类和 API。其中一些是平台类和 API，你可能已经熟悉它们。其余的是 Spring Framework 的类和 API，你必须理解它们是如何协同工作的。

## 理解资源包和消息格式

与标准标签库一样，Spring Framework i18n 使用资源包（resource bundles）和消息格式（message formats）。它使用资源包的抽象——消息源（message sources），提供了更简单的 API 来获取本地化消息。在实践中，资源包是 `java.util.ResourceBundle` 的实现。`ResourceBundle` 是映射到本地化消息格式的消息键的集合。这里需要注意的重要点是，键是消息格式，而不是消息本身。

当然，消息（`java.text.MessageFormat`）在存储于数据库或属性文件中看起来像本地化字符串。这些消息格式实际上可以包含各种占位符模板，在运行时会被提供的参数值替换。如果值的类型指定为日期、数字，它们将根据给定的 locale 进行正确的格式化。例如，以下都是美国英语本地化的格式：

- The road is long and windy.
- There are {0} on the farm.
- With a {0} discount, the final price is.
- The value of {0} is {1}.
- My birthday: {0}. Today is {1}.
- My day: {0}. Today is {1}.
- There {0} are no cats.

重要的是，占位符是带编号的，在使用消息代码时，你应该按照与占位符相同的顺序进行定义。这是因为占位符在其他语言中可能会以不同的顺序。

## 使用基础国际化和本地化 API

`ResourceBundle` 将名称中的任何点（.）替换为斜杠（/），在名称后附加 `.properties`，并在类路径上查找同名文件。如果该文件存在，则返回该文件的 `PropertyResourceBundle`。在搜索了所有包之后，如果 `ResourceBundle` 未找到匹配的包，它将使用回退本地化（fallback Locale）生成一个新的可能的包列表并重新搜索。如果仍然没有找到匹配的包，它将尝试查找与基名匹配但没有限定符的类和文件，如果没有找到任何包，则抛出异常。

当找到并返回 `ResourceBundle` 后，可以使用它来解析格式化字符串的消息代码。该包由标准的 Java 风格消息组成，键使用消息代码，值使用 `MessageFormat`。你可以从这些值字符串中构造 `MessageFormat` 实例。

如果你在 `javax.servlet.jsp.ftl` 本地化的 `localizationContext` 参数文件中指定了这些名称，你就能看到管理它们有多么简单。例如，你的类路径上可能存在以下文件的标签和错误文件：

```
labels_en.properties
labels_US.properties
labels_GB.properties
labels_FR.properties
errors_en.properties
errors_US.properties
errors_GB.properties
errors_FR.properties
```

这些文件随着时间的推移构成了你的 ResourceBundle。然而，如果你想将消息存储在数据库中怎么办？你需要为每个支持的本地化创建一个不同的类，大多数类执行本质上相同的逻辑（从数据库中选择值），或者你必须实现自己的系统来解析 `ResourceBundle` 实例。（即使如此，你仍然需要为每个本地化准备一个单独实例）。因为给定的 `ResourceBundle` 实例一次只支持一个本地化。检查 `ResourceBundle` 的 API 文档可以确认，解析消息的方法确实不包含 `Locale` 参数。你应该意识到，这种模式是不可持续的。

## 消息源的救援

消息源为资源包（resource bundles）提供了一种抽象和封装。实现 `org.springframework.context.MessageSource` 接口的 `MessageSource` 提供了三个简单的方法，用于使用 `MessageSourceResolvable` 对象或 `Locale` 来解析字符串消息，以及 Spring 消息代码、数组参数列表、默认值和 `Locale`。这些方法接受 `Locale` 意味着你只需要单个 `MessageSource` 实例即可获取任何本地化的本地化消息。此外，因为它们返回的是已经格式化的消息而不是消息格式，`MessageSources` 从消息本地化的任务中又消除了一个步骤（格式化消息）。

开箱即用，Spring 框架提供了 `MessageSource` 的两种实现：

- `org.springframework.context.support.ResourceBundleMessageSource`
- `org.springframework.context.support.ReloadableResourceBundleMessageSource`

# 42 | 第 15 章 使用 Spring 框架实现应用程序的国际化 I18N

`ResourceBundleMessageSource` 实际上有一个 `ResourceBundle` 集合作为后后支持。它使用 `ResourceBundle` 的 `getBundle` 方法来定位其包。

使用 `getBundle` 发现的 `ResourceBundle` 的缺点是它们会被永久缓存（也就是说，直到 JVM 关闭），而这有时并不是如人所愿的。`ReloadableResourceBundleMessageSource` 正如其名，是可以重新加载的。它不是由 `ResourceBundle` 支持的（尽管它的名字如此），但它允许包的检测规则。它使用基名通过与 `ResourceBundle` 相同的算法定位包（仅限文件，不限类）。然而，这些文件可以位于类路径上（基名以 `classpath:` 开头），也可以位于相对于上下文根目录的文件系统上。由于加载到类路径上的文件会被永久缓存，类路径会导致 `ReloadableResourceBundleMessageSource` 无法访问，因此通常会避免这样做。放置此消息源的包的典型位置是 `/WEB-INF/i18n`。使用 `MessageSource` API 非常简单：

```
@Inject MessageSource messageSource;
```

```
this.messageSource.getMessage("foo.message.key", new Object[] {
  argument1, argument2, argument3
}, user.getLocal());
```

```
this.messageSource.getMessage("foo.message.key", new Object[] {
  argument1, argument2, argument3
}, "This is the default message. Args: (0), (1), (2)*", user.getLocal());
```

毫无疑问，你将看到在 Java 代码中使用 `MessageSource` 实现要容易得多。你的 Java 代码不再需要知道基名、为基名和本地化查找 `ResourceBundle`、从注入的 `MessageSource` 实现中解析消息格式。相反，它只需要在注入的 `MessageSource` 实现上调用单个方法。这在桌面应用程序中将极其有用。但在一个设计良好的 Web 应用程序中，你如何在 Java 代码中进行本地化呢？

在 Web 应用程序中直接使用 `MessageSource` API 确实有些场景。例如，当你发送电子邮件或其他通知时，你需要本地化这些通知的内容。此外，某些 Web 服务在指定了 `Accept-Language` 请求头时会本地化错误消息。大多数本地化发生在你的 JSP 中，那么 `MessageSource` 在那里有什么用呢？JSTL 期望的是 `ResourceBundle` 而不是 `MessageSource`。

## 使用消息源使 JSP 国际化

Spring 通过提供 `org.springframework.framework.context.support.MessageSourceResourceBundle` 来实现这一点。（注意它与 `ResourceBundleMessageSource` 的相似之处；确保不要混淆它们）。`MessageSourceResourceBundle` 扩展了 `ResourceBundle` 并暴露特定 `Locale` 的底层 `MessageSource`，将 `ResourceBundle` 方法的调用委托给底层 `MessageSource`。当你使用 `JstlView`（直接使用或通过视图解析器）访问 JSP 时，Spring MVC 会使用 `javax.servlet.jsp.fmt.LocalizationContext` 为用户指定的或默认的 `Locale` 设置 `MessageSourceResourceBundle`，以便 `<fmt:message>` 能够正常工作。

当然，只有当你从 Spring 控制器使用 `JstlView`（直接使用或通过视图解析器）时，这种方法才适用于 JSP。你可能会在没有 Spring 的情况下访问其他 JSP，例如错误页面或不需要器的页面。由于 Spring 不参与这些类型 JSP 的生命周期，它无法自动设置 `MessageSourceResourceBundle`。

你有两种策略为这些不受 Spring 控制的 JSP 获取 `MessageSource`：

- 最简单的方法是使用 Spring 库中的 `<spring:message>` 标签，而不是在本章后面介绍的 `<fmt:message>` 标签，它比 `<fmt:message>` 有许多优势。优势之一可以直接使用 `MessageSource`。
- 如果由于某些原因不想使用 `<spring:message>` 标签，另一种方法是创建一个 Filter 来允许所有未由 Spring 处理的 JSP 请求。这个过滤器你需要用 Spring 编写，它将使用 `org.springframework.web.servlet.support.JstlUtils` 类来模拟 `JstlView` 的行为并设置 `LocalizationContext`。如果使用 `Accept-Language` 的技术设置本地用户，你需要确保发现本地用户并让此过滤器在过滤器链中执行。

以下假设的 `JstlLocalizationFilter` 完成了第二种方法。

```
public class JstlLocalizationFilter implements Filter {

    private ServletContext servletContext;

    @Inject MessageSource messageSource;

    @Override
    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {

        JstlUtils.exposeLocalizationContext(
            (HttpServletRequest)request, this.messageSource
        );

        chain.doFilter(request, response);
    }

    @Override
    public void init(FilterConfig config) throws ServletException {
```



# 配置国际化

## SPRING 框架

现在，既然你已经了解了消息源（message sources）和资源包络（resource bundles）是如何运作的，你可能已经急于学习如何配置它们了。在 Spring 中配置消息源非常简单，只需要几行代码。然而，要让 Spring 的国际化正常工作，远不止此。

大多数网站都为用户提供了更改区域（locale）的方法，你可能也想提供这种功能。除了临时更改区域外，许多用户还希望通过某种用户配置设置来永久设置他们的区域。这些都是你必须考虑的。本节将讨论不同的选项，以及如何在 Spring 框架中配置国际化。在本节和下一节中，你将使用从 wrox.com 下载站点获取 Localization-project。它包含了从上一章继承的 `BootstrapContextConfiguration` 和 `ServletContextConfiguration` 类。

## 创建消息源

在 Spring 框架中创建消息源是一项简单的任务。你只需要在 `RootContextConfiguration` 类中创建一个 `@Bean` 方法，并返回你选择的 `MessageSource` 实现即可。该 bean 必须命名为 `messageSource`。

```java
private static final Logger schedulingLogger =
    LogManager.getLogger(log.getName() + "*.scheduling");
```

```java
@Bean
public MessageSource messageSource() {
    ReloadableResourceBundleMessageSource messageSource =
        new ReloadableResourceBundleMessageSource();
    messageSource.setCacheSeconds(-1);
    messageSource.setDefaultEncoding(StandardCharsets.UTF_8.name());
    messageSource.setBasename(
        ":/WEB-INF/i18n/messages", ":/WEB-INF/i18n/errors"
    );
    return messageSource;
}
```

```java
@Bean
public ObjectMapper objectMapper() {
    ...
}
```

## 在 Spring 框架中配置国际化

在这种情况下，你使用了 `ReloadableResourceMessageSource`。你可能立即注意到缓存时间（cache time seconds）被设置为 -1。这种禁用重载的使得消息源永久缓存消息（直到 JVM 重启）。

你可能会问，为什么不使用 `ReloadableBundleMessageSource` 呢？`ReloadableBundleMessageSource` 并不像 `ReloadableResourceMessageSource` 那样由实际的 `ResourceBundle` 支持，它的性能比 `ResourceBundleMessageSource` 好 —— 但前提是你禁用了重载。如果启用重载（`cacheSeconds > 0`），从 `ReloadableResourceMessageSource` 解析消息的时间将大约是后者的两倍。将缓存时间设置为 -1 是你在生产环境中可以使用的最优性能配置。在开发环境中，你可能希望将缓存时间设置为正数，这样你就可以不重启 Tomcat 的情况下更改消息。这是 Spring Bean 定义配置（Bean Definition Profiles）的完美候选者，你已经在第 12 章中学习过它。

另一点你可能也注意到，消息源的编码被设置为 UTF-8。Spring 知道你的属性文件的编码，因此它可以正确地读取它们。还有另一个属性 `fileEncodings`，你可以用它来设置单个文件的编码。`defaultEncoding` 属性仅为那些在 `fileEncodings` 属性未找到的文件设置编码。由于 UTF-8 可以以尽可能小的空间编码任何已知语言的任何字符，在大多数情况下，你只需要将默认编码设置为 UTF-8，并确保你的所有属性都是 UTF-8 编码。这比根据每个文件包含的语言来管理不同的编码要简单得多。

最后，消息源配置了基名为 `/WEB-INF/i18n/messages` 以及 `/WEB-INF/i18n/messages_en_US.properties`、`/WEB-INF/i18n/errors_fr_FR.properties` 等。

当然，这只是加载消息的方案之一。Spring 自带两个消息源，你都可以根据需要以任何方式实现 `MessageSource` 并返回该实现细节。例如，某些类型的应用程序托管大多数客户，每个客户都有许多员工或成员，而这些客户可能希望为他们的账户定制本地化设置。在某种数据库中管理这些比在属性文件集中管理要容易得多。完美的解决方案是键值 NoSQL 数据库，例如 Redis、RavenDB 或 MongoDB（它实际上是一个数据库，但对于键值存储也非常出色）。使用 NoSQL 存储库（可能带有 Spring Data Redis 或 Spring Data MongoDB），你可以轻松从……

## 理解区域解析器（Locale Resolvers）

在概念上，区域解析器（local resolvers）类似于视图解析器（view resolvers）。Spring 使用区域解析器作为确定当前请求区域的策略，以便它可以确定如何本地化消息（以便它可以使用 JSTL 来本地化消息）。区域解析器提供了一种获取用户区域的方法，而不完全依赖 `Accept-Language` 头部。（尽管实现类 `org.springframework.web.servlet.i18n.AcceptHeaderLocaleResolver` 确实是这样。）由于你不想完全依赖 `Accept-Language` 头部，并且你想为用户提供将其区域更改为浏览器之外区域的方法，因此你不想使用默认的 `LocaleResolver` 实现。默认实现的常见替代方案是 `org.springframework.web.servlet.i18n.SessionLocaleResolver`。该解析器使用以下策略：

- `SessionLocaleResolver` 使用当前会话中的属性，其名称等于 `SessionLocaleResolver.LOCAL_SESSION_ATTRIBUTE` 常量。如果该属性存在，则返回其值。
- `SessionLocaleResolver` 接着检查是否设置了默认区域（defaultLocale），如果是则返回它。
- 最后，`SessionLocaleResolver` 返回 `HttpServletRequest` 上的 `getLocale` 的值（来自 `Accept-Language` 头部）。

```java
public void addInterceptors(InterceptorRegistry registry) {
    super.addInterceptors(registry);
    registry.addInterceptor(new LocaleChangeInterceptor());
}
```

```java
@Bean
public LocaleResolver localeResolver()
```

现在，在任何页面上你都可以添加一个更改语言区域的链接并提交到当前页面。这不仅会更改当前页面的语言区域，还会更改用户访问的所有后续页面的语言区域，直到会话超时或他关闭浏览器为止。

## 提供用户配置设置

如果你的应用程序是一个用户可以注册登录的程序，他们会希望设置自己的语言区域，并在每次返回网站时都使用它。从抽象上来说，你可以在某个地方提供一个配置设置页面，让用户更改各种设置，如姓名、电子邮件地址、个人资料、时区等。你如何使用这些设置，又如何让更改立即生效呢？

你有几种方案可以使用用户配置语言区域设置。首先，你可以简单地在登录控制器和个人资料控制器中使用注入的 `LocaleResolver`。当用户进行身份验证或更新个人资料时，你只需调用解析器的 `setLocale` 方法来更新他们当前的语言区域。

这种技术有一个缺点——这也是通用的 `SessionLocalStorage` 中也存在的问题——即应用程序在用户注销、关闭浏览器或会话超时后会忘记用户的语言区域。当他回来时，应用程序可能会以不同的语言显示。在这些情况下，你可能想要创建一个自定义的 `LocaleResolver` 来表示登录用户的语言区域，并使用 cookie 作为备份。你可以使用 `org.springframework.web.servlet.i18n.CookieLocaleResolver`，它已经为你处理了这些，你只需要扩展它：

```java
public class UserHeaderLocaleResolver extends CookieLocaleResolver {
    @Override
    public Locale resolveLocale(HttpServletRequest request) {
        Locale locale = null;
        Principal user = request.getUserPrincipal();
        if(user != null && user instanceof FooPrincipal) {
            locale = ((FooPrincipal)user).getLocale();
        }
        if(locale == null) {
            locale = super.resolveLocale(request);
        }
        return locale;
    }
}
```



由于你有多种方法来实现此任务，且这些方法在很大程度上取决于你的身份验证机制和用户 API，因此此示例没有在 Localized-Application 项目中演示。

# 时区支持

在对应用程序进行国际化时，语言区域并不是你应该考虑的唯一主题。除了语言和地区，时区也是 Web 应用用户的一个主要问题。大多数用户希望在页面上看到的是他们当地的时间，而不是服务器时间，特别是当服务器位于地球的另一端时。Spring Framework 4.0 包含了对时区的原生支持，即 `java.util.TimeZone` 和 `java.time.ZoneId` 类。对于这些类型的 `PropertyEditors`，你可以在控制器方法中指定它们，Spring 就可以为这些类型参数转换请求参数、路径变量和头部值。

Spring 还可以解析用户的时间并将其提供给你的控制器方法，类似于它解析并向你的控制器方法提供用户的语言区域的方式。然而，这种机制的运作与语言区域解析不同。没有 `TimeZone` 或 `ZoneId` 解析器，也没有更改拦截器。时区的处理方式与语言区域不同，它们通常不会像语言区域那样动态更改。从 Spring 的早期开始，你就可以使用 `org.springframework.context.i.LocaleContextHolder` 手动设置 `Locale`。该工具既是各种 `LocaleResolvers` 的替代品也是补充，确保你可以在需要时操作 `Locale`。`Locale` 存储在 `ThreadLocal` 变量中，贯穿整个生命周期。

从 Spring 4.0 开始，`LocaleContextHolder` 也支持获取当前用户的时区。你可以使用该类中的静态方法设置时区，Spring 会自动设置 JSTL TimeZone 属性，并提供控制器参数 `TimeZone` 和 `ZoneId` 的访问。这使得在应用程序中管理时区的任务变得简单得多。你只需要确定用户想要看到的时区并将其设置为 `LocaleContextHolder`。

# 理解主题如何改进国际化

Spring Framework 有一个主题（themes）的概念，这与国际化支持非常相似。主题是级联样式表、JavaScript 文件、图像以及为网站设置样式所需资源的集合。`Theme` 接口表示一个主题，可用的 `ThemeResolvers`（包括 `SessionThemeResolver` 和 `CookieThemeResolver`）可以为用户解析适当的主题。`ChangeThemeInterceptor` 使用一个可配置的请求参数（默认为 theme）来更新所选主题。主题功能包含一个 `ResourceBundleSource`，与 `ResourceBundleMessageSource` 几乎相同，它持有从属性文件中从键到资源的路径。最后，当使用 `<spring:theme>` 标签配置视图时（该标签与 `<spring:message>` 标签几乎相同），可以输出特定主题的相应资源 URL。

此时，你可能在想，这和国际化及本地化有什么关系，除了 API 如此相似之外。记住，在对应用程序进行国际化时，语言内容并不是你必须考虑的唯一因素。世界上不同的语言有不同的方向：

- 英语从左到右读
- 阿拉伯语和希伯来语等中东语言从右到左读
- 日语、汉语和韩语从上到下读

如果你认为仅仅翻译你的应用程序就很困难了，等你尝试考虑所有方向吧。如果你认为仅仅让你的应用程序国际化就很困难了，等你尝试考虑所有方向吧。

# 代码的国际化

在第 7 章，你使用 `<fmt:message>`、`<fmt:formatDate>` 和 `<fmt:formatNumber>` 实验了 JSP 的国际化。本节不再刷新，Localized-Application 项目包含一个带有映射的控制器。

```java
@Controller
public class HomeController {

    @RequestMapping(value = "/", method = RequestMethod.GET)
    public String index(Map<String, Object> model) {
        model.put("date", Instant.now());
        model.put("alerts", 12);
        model.put("numCritical", 0);
        model.put("numImportant", 11);
        model.put("numTrivial", 1);
        return "index/";
    }
}
```

`WEB-INF/i18n/messages_en_US.properties` 文件包含针对美国英语的本地化消息。

```properties
title.alerts=Server Alerts Page
alerts.current.date=Current date and time
number.alerts={0,choice,0=No alerts|1<#One alert|1<|There{0,integer} alerts in the log.}
alert.details={0,choice,0=No critical alerts|1<#One alert is critical|1<{0,integer} alerts are critical.}.
{1,choice,0=No important alerts|1<#One alert is important|nalerts are important.}
{2,choice,0=No trivial alerts|1<#One alert is trivial|1<{0,integer} alerts are trivial.}
```

最后，`WEB-INF/i18n/messages_es_MX.properties` 文件包含针对墨西哥西班牙语的本地化消息。

# 使用 `<spring:message>` 标签

如果你正在使用 `<fmt:message>` 标签，`<spring:message>` 标签可能会自然地更好，因为它非常好。`code` 属性是 `<fmt:message>` `key` 属性的对应项，并指定消息代码。两者都有 `var` 和 `scope` 属性，用于在页面打印之前将本地化值导出到 EL 变量。`<spring:message>` 没有 `bundle` 属性，因为 `<spring:message>` 使用 `MessageSource` 实例。

`javascript` 属性特别有用，如果设置为 true，它会将格式化后的消息中的 `"` 和 `'` 字符替换为 `\"` 和 `\\'`，以便在 JavaScript 字符串中使用是安全的。默认情况下，此属性为 false，且在 `<fmt:message>` 中没有对应项。`htmlEscape` 属性同样用于 `<spring:message>`，如果其值为 true，会将格式化后的消息中的特殊字符 `<`、`>`、`"` 和 `'` 转义为相应的实体序列。默认值为 false。

## 42 | 第15 章 使用 Spring Framework 实现应用程序国际化 I18N

如果页面上的大部分或所有 `<spring:message>` 标签都需要进行 HTML 转义，你可以在紧随其后的 JSP `<spring:message>` 标签中使用 `<spring:escape defaultHtmlEscape="true" />` 标签。如果整个应用程序中的大部分或所有 `<spring:message>` 标签都需要进行 HTML 转义，你可以在描述符中通过编程方式将上下文参数 `defaultHtmlEscape` 设置为 true，这影响应用程序中所有的 `<spring:message>` 标签。从优先级来说，`<spring:message>` 的 `htmlEscape` 属性如果显式设置，将始终覆盖 `<spring:htmlEscape>` 标签和上下文参数；而 `<spring:htmlEscape>` 标签如果显式使用，将始终覆盖上下文。

```xml
<context-param>
  <param-name>defaultHtmlEscape</param-name>
  <param-value>true</param-value>
</context-param>
```

`<fmt:message>` 和 `<spring:message>` 之间的最终区别在于如何在页面中显示以实现本地化。当你使用 `<fmt:message>` 时，你可以仅使用 `key` 属性或标签作为消息代码，并在必要时使用 `<fmt:param>` 标签作为格式化参数参数。`<spring:message>` 要灵活得多，允许你使用以下策略之一。使用 `<spring:message>` 标签，你可以指定：

- 传统上使用 `code` 属性或标签作为消息代码，并在必要时嵌套 `<spring:argument>` 标签作为格式化参数。Spring 4.0 中引入的 `<spring:argument>` 标签其工作方式与 `<fmt:param>` 标签完全相同。你可以可选地使用 `text` 属性指定默认消息格式，如果消息代码无法解析，则使用该值。你不应该在 `arguments`、`argumentSeparator` 或 `message` 属性上使用此策略。
- 使用 `code` 属性或标签作为消息代码，并在必要时在 `arguments` 属性中提供由分隔的参数列表。默认情况下，你可以使用 `argumentSeparator` 属性自定义分隔符。你可以可选地使用 `text` 属性指定默认消息格式，如果消息代码无法解析，则使用该值。你不应该在 `message` 属性或嵌套的 `<spring:message>` 标签上使用此策略。
- 使用 EL 表达式通过 `MessageSourceResolvable` 实例用于 `message` 属性。因为 `MessageSourceResolvable` 提供了自身的代码和默认消息，你不应该在 `arguments`、`argumentsSeparator` 和 `text` 属性、标签体或嵌套的 `<spring:argument>` 标签上使用此代码。

`<spring:message>` 和 `<fmt:message>` 的结合使用在 Localized-Application 项目的 `WEB-INF/jsp/view/index.jsp` 文件中。你会注意到该文件没有包含字符串字面量，而是对所有文本输出都进行了消息国际化。这才是应该采用的方法。

```jsp
<%-- @elvariable id="date" type="java.util.Date"--%>
<%-- @elvariable id="alerts" type="int"--%>
<%-- @elvariable id="numCritical" type="int"--%>
<%-- @elvariable id="numImportant" type="int"--%>
<%-- @elvariable id="numTrivial" type="int"--%>
```

![](img/9c2d45f6d547f72cb870b3a991f62ef6_467_0.png)

```html
<!DOCTYPE html>
<html>
<head>
  <title><spring:message code="title.alerts" /></title>
</head>
<body>
  <h2><fmt:message key="alerts.current.date"/></h2>
  <fmt:message value="${date}"/><br />
  <fmt:message><i><fmt:message></i</fmt:message><br />
  <fmt:message key="number.alerts" />
  <spring:param param value="${alerts}" />
  <spring:if test="${alerts} > 0}">
    &nbsp;<spring:message code="alert.details">
      <spring:argument value="${numCritical}" />
      <spring:argument value="${numImportant}" />
      <spring:argument value="${numTrivial}" />
    </spring:message>
  </spring:if>
</body>
</html>
```



## 处理应用程序错误

如你所知，应用程序错误会发生。最终，某些问题会出现并导致你的应用程序无法正常运行。通常，这会导致抛出异常。在第 11 章中，你学习了日志记录如何帮助你清晰地处理这些错误。然而，向用户隐藏所有错误并不是向用户显示所有堆栈轨迹的可接受的替代方案。当出现问题时，用户需要知道。你应该记录技术细节，但你应该为用户显示一条有用的错误消息，帮助他们用最少技术性的语言理解发生了什么。此错误消息也必须经过本地化。你不希望这种国际化影响写入日志（显示给用户看）的消息。

你有许多不同的方法来处理这个问题，展示如何这样做是非常重要的。当发生某些预期的类型异常时（例如执行 SQL 语句时的 `SQLException`），自然的倾向是捕获并重新抛出。这是可以的，但你仍然需要向用户报告。解决此问题的好方法是让 `LoggedException` 实现 `MessageSourcevable`。然后它就包含了自身的错误代码、默认消息和参数，你可以使用它们来实现异常显示的国际化。然而，如果你仔细思考，你会很快发现某些情况要求你在不捕获异常的情况下抛出国际化异常。因此你真正需要的是实现 `MessageSourcevable` 的 `InternationalizedException` 以及一个扩展它的 `LoggedException`。

解决此问题的好方法是让 `LoggedException` 实现 `MessageSourcevable`。然后它包含了自身的错误代码、默认消息和参数，你可以使用它们来实现异常显示的国际化。然而，如果你仔细思考，你会很快发现某些情况要求你在不捕获异常的情况下抛出国际化异常。因此你真正需要的是实现 `MessageSourcevable` 的 `InternationalizedException` 以及一个扩展它的 `LoggedException`。

### 列表 15-1: InternationalizedException.java

```java
public class InternationalizedException extends RuntimeException
    implements MessageSourcevable {

    private static final long serialVersionUID = 1L;
    private static final Locale DEFAULT_LOCALE = Locale.US;

    private final String errorCode;
    private final String[] codes;
    private final Object[] arguments;

    public InternationalizedException(String errorCode, Object... arguments) {
        this(null, errorCode, arguments);
    }

    public InternationalizedException(Throwable cause, String errorCode,
        Object... arguments) {
        this(cause, errorCode, arguments);
    }

    public InternationalizedException(String errorCode, String defaultMessage,
        Object... arguments) {
        this(null, errorCode, defaultMessage, arguments);
    }

    public InternationalizedException(Throwable cause, String errorCode,
        String defaultMessage, Object... arguments) {
        super(defaultMessage == null ? errorCode : defaultMessage, cause);
        this.errorCode = errorCode;
        this.codes = new String[] { errorCode };
        this.arguments = arguments;
    }

    @Override
    public String getLocalizedMessage() {
        return this.errorCode;
    }

    public String getLocalizedMessage(MessageSource messageSource) {
        return this.getLocalizedMessage(messageSource, this.getLocale());
    }

    public String getLocalizedMessage(MessageSource messageSource, Locale locale) {
        return messageSource.getMessage(this, locale);
    }

    @Override
    public String[] getCodes() {
        return this.codes;
    }

    @Override
    public Object[] getArguments() {
        return this.arguments;
    }

    @Override
    public String getDefaultMessage() {
        return this.getMessage();
    }

    protected final Locale getLocale() {
        Locale locale = LocaleContext.getLocale();
        return locale == null ? InternationalizedException.DEFAULT_LOCALE : locale;
    }
}
```

`getLocale` 和 `getLocalizedMessage` 方法并不是强制要求的，但它们使得在 Java 代码内部使用该异常变得更容易。这种异常可以在代码的任何地方抛出，而不会引起额外的异常。它的子类是 `LoggedException`，如列表 15-2 所示。该异常不包含任何方法或字段；它只是限制了用户要求用户提供一个原因异常。

### 列表 15-2: LoggedException.java

```java
public class LoggedException extends InternationalizedException {
    private static long serialVersionUID = 1L;

    public LoggedException(Throwable cause, String errorCode,
        Object... arguments) {
        this(cause, errorCode, null, arguments);
    }

    public LoggedException(Throwable cause, String errorCode,
        String defaultMessage, Object... arguments) {
        super(cause, errorCode, defaultMessage, arguments);
    }
}
```

你已经意识到记录异常并用之抛出 `LoggedException` 的优势，这可以防止高层捕获该异常并进行重复记录。为了演示本地化异常是多么简单，请按照以下步骤操作：

1. 在你的 `HomeController` 的处理方法中添加以下内容。

```java
model.put("exception", new InternationalizedException(
    "bad.food.exception", "You ate bad food."));
```

2. 在 `/WEB-INF/i18n/errors_en_US.properties` 中为消息添加翻译：
```
bad.food.exception=You ate bad food.
```

3. 在 `/WEB-INF/i18n/errors_es_MX.properties` 中，使用：
```
bad.food.exception=Comida en mal estado.
```

4. 更新 `/WEB-INF/jsp/view/home/index.jsp`，使用 `<spring:message>` 显示异常。

```html
<c:if test="${exception != null}"><br /><br>
<spring:message message="${exception}" />
</c:if>
</body>
</html>
```

要测试 Localized-Application 项目，请编译、从 IDE 启动 Tomcat，并在你喜欢的浏览器中访问 `http://localhost:8080/i18n/`。你会看到页面以英语整齐地显示。访问 `http://localhost:8080/i18n/locale=es_MX`，页面应该变为西班牙语。更重要的是，你可以多次返回 `http://localhost:8080/i18n/` 且不带 locale 参数，而页面仍然会保持为西班牙语。只有当你访问 `http://localhost:8080/i18n/locale=en_US` 时，页面才会恢复为英语，并且在没有 locale 参数的情况下保持该状态。

> **注意**：如果你在区域为西班牙语的计算机上访问该应用程序，假设你的浏览器显示了 `Accept-Language` 请求头，页面应该首先显示西班牙语而不是英语。情况是如此，请反向执行说明，尝试将 `en-US` 作为第一个 locale 值。

## 更新客户支持应用程序

Customer-Support-v12 项目（你可以从 wrox.com 下载站点获取）现在正使用与 Localized-Application 项目相同的配置进行国际化。唯一的区别是，客户支持应用程序在消息源配置中有一个额外的资源包名称。

```java
messagesSource.setBasenames(
    "/WEB-INF/i18n/titles", "/WEB-INF/i18n/messages",
    "/WEB-INF/i18n/errors"
);
```

i18n 文件 `/WEB-INF/i18n/errors_en_US.properties`、`messages_en_US.properties` 和 `titles_en_US.properties` 包含了几十条消息。其他任何语言均没有本地化。国际化的大部分工作是常规的 `<spring:message>`，但 `/WEB-INF/jsp/view/chat/chat.jsp` 是一个有趣的例子。该文件充满了需要本地化的 JavaScript 字符串。带有 `JavaScriptEscape="true"` 的 `<spring:message>` 对此很有用，但这不是唯一的困境。例如，看看此 `messages_en_US.properties` 中的消息，它最终会被放在 JavaScript 字符串中：

```properties
message.chat.joined=You are now chatting with {0}.
```

此消息是参数化的，需要完成参数。那么，当参数在渲染时不可用但必须由 JavaScript 填充时，它是如何工作的呢？简单来说，由于对于这几个额外的替换模板不存在参数，因此消息在运行时被写入 JavaScript 代码中显示为 `You are now chatting with {0}.`。然后，使用该值只需要调用 JavaScript 字符串上的 `replace` 方法将参数替换为适当的参数即可。

```javascript
infomessage('<spring:message code="message.chat.joined" JavaScriptEscape="true"/>').replace('{0}', user);
```

国际化客户支持应用程序的最后一个挑战是处理聊天消息。与所有其他本地化消息不同（这些消息在视图渲染时解析），ChatService 通过 WebSocket 传输的消息也必须本地化。`<spring:message>` 标签在这里并不适用。

### 直接使用消息源

为了解决这个问题，`ChatMessage` 类需要由消息代码和参数。

```java
public class ChatMessage implements Cloneable {
    private Instant timestamp;
    private Type type;
    private String user;
    private String contentCode;
    private Object[] contentArguments;
    private String localizedContent;
    private String userContent;

    // 变器和访问器
    // enum
    // clone

    static abstract class MixInForLogWrite {
        public abstract String getLocalizedContent();
        public abstract void setLocalizedContent(String l);
    }

    static abstract class MixInForWebSocket {
        public abstract String getContentCode();
        public abstract void setContentCode(String c);
        public abstract Object[] getContentArguments();
        public abstract void setContentArguments(Object[] c);
    }
}
```

`MixInForLogWrite` 和 `MixInForWebSocket` 内部类用于支持 Jackson 的 Mix-In 功能。`localizedContent` 不需要写入日志文件，因为它是针对特定用户的本地化。同样，`contentCode` 和 `contentArguments` 不需要通过 WebSocket 传输，因为消息已经本地化了。另一方面，用户提供了 `userContent` 属性，你无法对其进行本地化。你原样传输此消息。为了使用这些 Mix-In 注解，我首先为 `DefaultChatService` 添加了 `@PostConstruct` 方法。

```java
@PostConstruct
public void initialize() {
    this.objectMapper.addMixInAnnotations(ChatMessage.class,
        ChatMessage.MixInForLogWrite.class);
}
```

现在你可以使用静态初始化器在 `ChatMessageDecoder` 中添加不同的 Mix-In 类。由于这是一个不同的 `ObjectMapper` 实例，它不会与你刚刚添加到 `DefaultChatService` 中的 Mix-In 发生冲突。

```java
MAPPER.addMixInAnnotations(ChatMessage.class,
    ChatMessage.MixInForWebSocket.class);
```

接下来，你需要重构 `DefaultChatService` 以使用消息代码和参数而不是静态方法。

```java
public CreateResult createSession(String user) {
    message.setContentCode("message.chat.started.");
    message.setContentArguments(user);
    ...
}
```

```java
public JoinResult joinSession(long id, String user) {
    ...
    message.setContentCode("message.chat.joined.");
    message.setContentArguments(user);
}
```

```java
public ChatMessage leaveSession(ChatSession session, String user, ReasonForLeaving reason) {
    if (reason == ReasonForLeaving.ERROR)
        message.setType(ChatMessage.Type.ERROR);
    message.setType(ChatMessage.Type.LEFT);
    if (reason == ReasonForLeaving.ERROR)
```



message.setContentCode("message.chat.left.chat.error.");

else if (reason == ReasonForLeaving.LOGGED_OUT)

    message.setContentCode("message.chat.left.chat.logged.");

else

    message.setContentCode("message.chat.left.chat.normal.");

message.setContentArguments(user);

}

```

此时，所有内容都已编译，但端点尚未对消息进行本地化。它首先需要一个 `MessageSource` 和 `Locale`：

```java
private Locale locale;

private Locale otherLocale;

...

@Inject MessagesSource messageSource;
```

`Locale` 无法注入，因此 `ChatEndpointEndpointConfigurator` 的 `modifyHandshake` 方法从 Source 获取 `Locale` 并将其添加到 WebSocket Session 中。

```java
config.getUserProperties().put(LOCALE_KEY, LocaleContextHolder.getLocale());
```

`ChatEndpoint` 的 `onOpen` 方法允许了这一点：

```java
this.locale = EndpointConfigurator.getExposedLocale(session);

this.otherWsSession = this.chatSession.getCustomer();

this.otherLocale = EndpointConfigurator.getExposedLocale(this.otherWsSession);
```

`ChatEndpoint` 还需要一个内部辅助方法来使本地化变得简单。通过调用此方法，你可以在一行代码中克隆并本地化一条 `Message`。

```java
private ChatMessage cloneAndLocalize(ChatMessage message, Locale locale) {

    message = message.clone();

    message.setLocalizedContent(this.messageSource.getMessage(
        message.getCode(), message.getContentArguments(), locale
    ));

    return message;
}
```

你可以本地化所有发送内部生成的 `ChatMessages` 的地方。请记住，你不能本地化用户生成的 `ChatMessages`，因为它们包含用户内容，而不是消息代码。

```java
session.getBasicRemote().sendObject(this.cloneAndLocalize(
    result.createMessage(), this.locale
));
```

```java
session.getBasicRemote().sendObject(this.cloneAndLocalize(
    this.chatSession.createMessage(), this.locale
));

session.getBasicRemote().sendObject(this.cloneAndLocalize(
    result.getJoinMessage(), this.locale
));
```

```java
this.otherWsSession.getBasicRemote()
      .sendObject(this.cloneAndLocalize(
        result.getJoinMessage(), this.otherLocale
    ));

this.wsSession.getBasicRemote()
      .sendObject(this.cloneAndLocalize(
        message, this.locale
      ));

this.wsSession.close(closeReason);

...

this.otherWsSession.getBasicRemote()
  .sendObject(this.cloneAndLocalize(
    message, this.otherLocale
  ));

this.otherWsSession.close(closeReason);
```

现在客户支持应用程序的国际化已经完成，编译它，在你的 IDE 中为它启动 Tomcat，然后访问 `http://localhost:8080/support/`。登录并浏览。创建、列表和查看工单，并查看会话列表。从另一个浏览器登录并参与会话。国际化和本地化确实需要投入大量精力，但 Spring Framework 提供的工具使这项任务变得简单得多。

### 总结

在本章中，你学习了大量关于国际化（i18n）和本地化（L10n）在概念和实践方面的知识。你见证了这些任务的困难性，并尝试了 Spring Framework 提供的所有工具来简化它们。你使用 `<spring:message>` 和 `<fmt:message>` 本地了 JSP 视图，并使用 Spring 的 `MessageSource` 本地了 Java 字符串。你还学习了配置 Spring 国际化和本地化支持时的所有选项，并接触了带日志的国际化异常模式。最后，你了解了对用户时区的支持，并对非西方区域文本方向的复杂性进行了要介绍。

在下一章中，你将学习 JSR 303/JSR 349 自动 Bean 验证和 Hibernate Validator。本章与此密切相关，你会发现在熟悉 Bean 验证时，在本章中发现的技能和工具是不可或缺的。

# 使用 JSR 349、Spring Framework 和 Hibernate Validator 进行 Bean 验证

## 本章内容

- Bean 验证简介
- 在 Spring Framework 容器中配置验证
- 为你的 bean 添加约束验证注解
- 为方法验证配置 Spring bean
- 编写你自己的验证约束
- 在客户支持应用程序中集成验证

## 本章代码下载（WROX.COM）

你可以在在 `http://www.wrox.com/go/projectforwebapps` 的 Download Code 选项卡找到本章的 wrox.com 代码下载。本章的代码分为以下主要示例：

- HR-Portal 项目
- Custom-Constraints 项目
- Custom-Support-v13 项目

## 本章的新 Maven 依赖

除了之前章节引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>javax.validation</groupId>
  <artifactId>validation-api</artifactId>
  <version>1.1.0.Final</version>
  <scope>compile</scope>
</dependency>
```

```xml
<dependency>
  <groupId>org.hibernate</groupId>
  <artifactId>hibernate-validator</artifactId>
  <version>5.1.0.Final</version>
  <scope>runtime</scope>
  <exclusion>
    <groupId>org.jboss.logging</groupId>
    <artifactId>jboss-logging</artifactId>
  </exclusion>
</dependency>
```

```xml
<dependency>
  <groupId>org.jboss.logging</groupId>
  <artifactId>jboss-logging</artifactId>
  <version>3.2.0.GA</version>
  <scope>runtime</scope>
</dependency>
```

# 什么是验证？

在大型应用中，你许多不同类型的对象以某种方式被“保存”。这里“保存”一词的意义并不重要；它可能被存储在内存中、通过网络连接传输或持久化到数据库中。无论目标是什么，对象化都有必须遵循的规则。例如，代表用户的对象在用户名字段中必须有一个非空且非空白的值。向购物车中添加项目需要一个产品标识符，且数量必须大于零。发送的电子邮件可能要求收件人主题和正文有值。添加到人力资源系统的员工必须具有某些属性。为了让验证变得更容易，邮件可能需要遵循以下规则：

```
^[a-zA-Z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-zA-Z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-zA-Z0-9](?:[a-zA-Z0-9-]*[a-zA-Z0-9])?\.)+[a-zA-Z0-9](?:[a-zA-Z0-9-]*[a-zA-Z0-9])?$
```

在应用中，对象化规则会以这种方式变得繁琐。在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

在应用中，对象化规则会以这种方式变得繁琐。为了让验证变得更容易，邮件可能需要遵循以下规则：

一个实际调用其实现代理的接口。实现 Java EE 7 的完整 Java EE 应用服务器提供了 DI 经过适当验证的实现的能力。然而，当使用 Tomcat 等 servlet 容器时，你必须提供其他的 DI 解决方案。

## 在 Spring Framework 中使用 Bean Validation

显然，Spring Framework 的依赖注入是解决此问题的方案。Spring Framework 会自动对使用 Bean Validation 的 Spring 管理的 Bean 进行代理。对带有注解方法的调用会被拦截并进行适当的验证，无论消费者是否提供了有效参数，或者实现类是否返回了合法的值。因此，在 `@services` 上使用 Bean Validation 是很常见的，因为这些是处理业务逻辑的 Spring 管理的 Bean。如果传递给 controller 处理器程序的参数标记为 `javax.validation.Valid`，Spring Framework 就会对任何形式的表单对象或其他带有约束注解的参数进行验证。

在本章中，你将探索如何在 Spring Framework 中配置 Bean Validation，以及如何使用提供的配置将规则应用于你的 Bean。你还将学习如何创建自己的自定义的约束注解，以满足内置约束无法满足的规则。

## 在 Spring 容器中配置验证

在方便地使用任何验证工具之前，你必须先在 Spring Framework 配置中设置 Bean Validation。这并不是说在 Spring 中配置 Bean Validation 是使用验证器的必要条件，因为下面的标准验证代码即使在没有 Spring 容器的情况下仍然有效：

```java
ValidatorFactory factory = Validation.buildDefaultValidatorFactory();

Validator validator = factory.getValidator();

Set<ConstraintViolation<Employee>> violations = validator.validate(employee);

if (violations.size() > 0)
    throw new ConstraintViolationException(violations);
```



但你不想那样使用它。你希望它是自动的，这意味着 Spring Framework 的依赖注入和代理支持将参与进来。为了实现这一点，你必须配置四件事：

- 验证器
- 验证器的消息本地化
- 方法验证处理器
- Spring MVC 表单验证

为此，请使用从 wrox.com 代码下载源获取的 HR-Portal。

## 446 | 第 16 章 使用 JSR 309、Spring Framework 和 Hibernate Validator 进行 Bean Validation

> **注意**：你可能已经注意到 Hibernate Validator 的 Maven 依赖排除了瞬态 JBoss Logging API 依赖（Hibernate 项目使用它代替 Commons Logging API），并单独声明了运行时 JBoss Logging 依赖。`hibernate-validator` 节点声明了一个不支持 Log4j 2 的 `jboss-logging` 版本，因此必须声明一个新的支持它的依赖。排除并不是严格必要的，但为了清晰起见在此。

> **警告**：在 Spring Framework 4.0 之前，Spring 对 Bean Validation 的支持专门针对 Hibernate Validator 4.2 或 4.3。这是因为 Hibernate Validator 提供了一些解决某些问题所需的非标准功能，例如与 Spring i18n 的集成。从 Spring 4.0 开始，Bean Validation 1.1 的实现可以工作，因为这些功能在 1.1 中已经标准化了。然而，如果出于某些原因限制在使用 Bean Validation 1.0，你仍然必须使用 Hibernate Validator。

### 配置 Spring Validator Bean

在 Bean Validation 标准正式制定很久以前，Spring Framework 就已经支持对对象的自动验证。`org.springframework.validation.Validator` 接口指定了一个根据注解约束验证对象的工具。这些约束及其应用最初被定义在一个名为 Spring Modules Validation 的独立项目中，该项目在离开 beta 状态之前就被废弃了，转而支持了新兴的 JSR 303 标准。现在，这个 Spring Validator 接口充当 Bean Validation API 的门面。

理解 Spring 验证使用 `org.springframework.validation.Errors` 接口报告错误，而不是返回一个 `Set<ConstraintViolation<?>>` 是重要的。该接口提供了对一个或多个 `org.springframework.validation.ObjectErrors` 和一个或多个 `org.springframework.validation.FieldErrors` 的访问。直到今天，大多数情况下你可以根据喜好使用 Spring Validator 或 `javax.validation.Validator`，但在一种特定情况下，你必须使用 Spring Validator 及其 Errors。

> **注意**：为了避免在本书其余部分使用“Validator”一词时产生混淆，除非另有说明，否则它指的是 `javax.validation.Validator`。然而，如果前面有单词 "Spring"（例如 "Spring Validator"），它指的是 `org.springframework.validation.Validator`。

在配置 Spring Framework 的验证支持时，你定义了一个特殊类型的 bean（一个扩展 `org.springframework.validation.beanvalidation.SpringValidatorAdapter` 并同时实现 `Validator` 和 `Spring Validation` 的类）。在内部，该 bean 使用 Validator 来支持这两个接口的操作。你可以选择使用以下任一个：

- `javax.validation.beanvalidation.CustomValidatorBean`
- `javax.validation.beanvalidation.LocalFactoryBean`

在大多数情况下，你想要使用 `LocalValidatorFactoryBean`，因为它支持检索底层工厂，并允许你使用与应用程序其他部分国际化的相同的 `MessageSource` 和 bundle 文件。在最简单的情况下，配置 Spring Framework 的 `LocalValidatorFactoryBean` 只需要在你的 `RootContextConfiguration` 类的 `@Bean` 中实例化并返回它即可：

```java
@Bean
public LocalValidatorFactoryBean localValidatorFactoryBean() {
    return new LocalValidatorFactoryBean();
}
```

`LocalValidatorFactoryBean` 自动检测类路径上的 Bean Validation 实现（Hibernate 的 Validator 或其他实现），并使用其默认的 `javax.validation.Validator` 作为后备工厂。通常不需要设置通常在应用程序中利用 Bean Validation 时所需的 `META-INF/validation.xml` 文件。然而，类路径上可能存在多个 Bean Validation Provider（例如，在 GlassFish 或 WebSphere 等完整的 Java 应用服务器中运行时）。在这些 Spring 使得验证变得不可预测的情况下，你应该手动设置 provider：

```java
@Bean
public LocalValidatorFactoryBean validator() {
    LocalValidatorFactoryBean validator = new LocalValidatorFactoryBean();
    validator.setProviderClass(HibernateValidator.class);
    return validator;
}
```

使用这种方法的唯一缺点是它需要 Hibernate Validator 作为编译时依赖。这会污染你的编译时间。你可以通过动态加载类来避免这一点：

```java
@Bean
public LocalValidatorFactoryBean localValidatorFactoryBean() throws ClassNotFoundException {
    LocalValidatorFactoryBean validator = new LocalValidatorFactoryBean();
    validator.setProviderClass(Class.forName("org.hibernate.validator.HibernateValidator"));
    return validator;
}
```

在使用 Tomcat 时不需要手动设置 provider，本书中的示例没有这样做。

### 设置错误代码本地化

在下一节中，你将探索向类和实体添加约束注解。当你这样做时，可以为每个约束指定一个消息。或者，你可以指定错误代码。

错误代码允许对约束进行国际化，以便在显示给用户之前进行本地化。Bean Validation 的默认国际化使用资源文件 `ValidationMessages.properties`、`ValidationMessages_[language].properties`、`ValidationMessages_[region].properties` 等。这些必须位于类路径上（`/WEB-INF/classes/`）。然而，使用任何 Bean Validation 1.1 实现，你可以使用 `javax.validation.MessageInterpolator` 提供自己的国际化（在 Bean Validation 1.1 发布之前，Hibernate Validator 4.2 和 4.3 提供了非标准支持）。无论何种方式，你都需要每次激活时为验证器指定 Locale。

再次，Spring 出手了，使得轻松提供自定义的 `MessageInterpolator` 并消除对 `Locale` 的担心。你只需要在 `RootContextConfiguration` 中定义的 `LocalValidatorFactoryBean` 上设置 `ValidationMessageSource`，它会自动提供一个由该 `MessageSource` 支持的插值器：

```java
@Bean
public MessageSource messageSource() {
    ReloadableResourceBundleMessageSource messageSource = new ReloadableResourceBundleMessageSource();
    messageSource.setCacheSeconds(-1);
    messageSource.setDefaultEncoding(StandardCharsets.UTF_8.name());
    messageSource.setBasenames("/WEB-INF/i18n/titles", "/WEB-INF/i18n/messages", "/WEB-INF/i18n/errors", "/WEB-INF/i18n/validation");
    return messageSource;
}
```

```java
@Bean
public LocalValidatorFactoryBean localValidatorFactoryBean() {
    LocalValidatorFactoryBean validator = new LocalValidatorFactoryBean();
    validator.setValidationMessageSource(this.messageSource());
    return validator;
}
```

现在你已经配置了 `LocalValidatorFactoryBean` 使用你的 `MessageSource`，你可以与应用程序其他所有本地化消息一起创建你的本地化验证消息了。

## 在 Spring 框架容器中配置验证

……，并利用 Spring 对当前用户本地区域（Locale）跟踪的支持，以便在运行时对消息进行本地化处理。

## 使用验证 Bean 后处理器

Spring 框架使用 Bean 后处理器的概念，在容器完成启动过程之前对配置中的 bean 进行配置、自定义，并在必要时替换。`org.springframework.beans.factory.config.BeanPostProcessor` 的实现在 bean 注入依赖它的其他 bean 之前执行。例如：

- `AutowiredAnnotationBeanPostProcessor` 是在配置 Spring 时自动创建的框架 bean。它负责查找 `@Autowired` 和 `@Injected` 属性并注入它们的值。
- `InitDestroyAnnotationBeanPostProcessor` 查找 `InitializingBean` 实现类（`@PostConstruct` 方法）和 `DisposableBean` 实现类（`@PreDestroy` 方法），并在生命周期的适当阶段执行这些方法。
- 某些后处理器实际上能够替换 bean。`AsyncAnnotationBeanPostProcessor` 查找带有 `@Async` 的 bean，并将这些 bean 替换为代理，以便 `@Async` 方法可以被异步调用。

你需要的大多数后处理器（即前面提到的那些）都是为你自动创建的。然而，为了支持方法参数和返回值的验证，你需要创建一个 `org.springframework.validation.beanvalidation.MethodValidationPostProcessor` 来代理被验证方法的执行。这并不简单实例化 `MethodValidationPostProcessor`，因为它默认使用类路径上的验证器（而不包含你的 `MessageSource`）。相反，你必须配置它使用你创建的 `LocalValidatorFactoryBean`。

```java
@Bean
public LocalValidatorFactoryBean localValidatorFactoryBean() { ... }
```

```java
@Bean
public MethodValidationPostProcessor methodValidationPostProcessor() {
    MethodValidationPostProcessor processor = new MethodValidationPostProcessor();
    processor.setValidator(this.localValidatorFactoryBean());
    return processor;
}
```

```java
@Bean
public ObjectMapper objectMapper() { ... }
```

这个 `MethodValidationPostProcessor` 查找带有 `@org.springframework.validation.annotation.Validated` 或 `javax.validation.executable.ValidateOnExecution` 注解的类并代理，在方法执行前对带注解的参数进行参数验证，并在方法执行后对带注解的方法进行返回值验证。两个章节之后，你将学习如何为类方法注解以激活这一过程。

## 让 Spring MVC 使用相同的验证

与你刚刚创建的使用 `Validator` 实例的 `MethodValidationPostProcessor` 不同，Spring MVC 控制器的表单对象和参数验证使用的是 `Validator` 实例。这支持为期望 `@Valid` 参数的方法提供 `Errors` 参数，因为 `Errors` 接口比一组 `ConstraintViolations` 更容易使用。幸运的是，`LocalValidatorFactoryBean` 实现了这两个验证器接口，但默认情况下，Spring MVC 会创建一个独立的 Spring Validator 实例，而不是在根应用上下文中创建的那个。

要更改此默认配置，你只需要更改 `ServletContextConfiguration` 类以覆盖 `WebMvcConfigurerAdapter` 的 `getValidator` 方法，并返回根应用上下文创建的验证器。

```java
@Inject
SpringValidatorAdapter validator;

@Override
public Validator getValidator() {
    return this.validator;
}
```



通过此更改，Spring MVC 使用你配置的验证器来验证适当的控制器处理参数，你的 Spring Bean Validation 现在已完成。

# 为你的 Bean 添加约束注解

对于 Bean 验证（Bean Validation），你的 Spring 应用主要处理两种类型的 bean：

- POJO 或类似于 JavaBean 的实体和对象形式，它们通常作为方法参数或返回类型
- Spring Bean，如 `@Controllers` 和 `@Services`，它们使用 POJO 作为方法参数和返回类型

这两种类型的 bean 都使用 Bean 验证约束注解，但使用方式不同。在本节中，你将尝试将约束注解应用到 POJO，在接一节中，你将学习如何通过将注解应用到你的 Spring Bean 来完成这一过程。

# 添加内置约束注解

尽管你可以随随地创建自己的约束注解，但 Bean Validation API 提供了几个内置注解，可以满足最常见的验证需求。这些都是非常简单的约束，但在许多情况下，它们就是你所需要的。所有约束都在 `javax.validation.constraints` 包中。

- `@Null` — 你可以将其应用于任何类型，并确保目标为 `null`。
- `@NotNull` — 你也可以将其应用于任何类型。它确保目标不为 `null`。
- `@AssertTrue` 和 `@AssertFalse` — 确保其被注解的值为真或假。因此，它们所注解的字段、参数或方法（返回值）类型必须是 `boolean` 或 `Boolean`。对于每个约束，`null` 都被视为有效，如果你不接受 `null`，请将其与 `@NotNull` 结合。
- `@DecimalMax` — 这为数值类型定义了上限，通过 `value` 属性指定。它可以注解为 `BigDecimal`、`BigInteger`、`CharSequence(String)`、`byte`、`Byte`、`short`、`Int`、`int` 和 `Long` 的字段、参数和方法（返回值）。由于精度问题，不支持基本类型 `Double`, `Float`。CharSequence 在验证之前会转换为小数，`null` 值被视为有效。可选的 `inclusive` 属性指定测试应该是包含性的（小于或等于）还是排斥性的（小于），默认为包含。
- `@DecimalMin` — 这是 `@DecimalMax` 的对应项。它以相同的规则适用于所有类型。它也包含一个 `inclusive` 属性。
- `@Digits` — 你可以使用此来确保被注解的目标是可解析的数字（如果它是 `CharSequence`、`BigInteger`、`byte`、`Byte`、`short`、`Int`、`int` 或 `Long`）。强制性的 `integer` 属性指定允许的最大整数位数（小数点点之前），而 `fraction` 属性指定允许的最大小数位数（小数点点之后）。`null` 值始终被视为有效。
- `@Future` — 确保注解的字段、参数或方法（返回值）在未来。
- `@Past` — 确保注解的字段、参数或方法（返回值）在过去。
- `@Max` 和 `@Min` — 这些类似于 `@DecimalMax` 和 `@DecimalMin`，但不支持 `CharSequence`。`null` 是有效的。
- `@Pattern` — 这定义了 `CharSequence` 必须匹配的正则表达式。它包含一个可选的 `flags` 属性，支持数组。支持的标志包括：
  - `CANON_EQ` — 启用规范等
  - `CASE_INSENSITIVE` — 启用大小不敏感
  - `COMMENTS` — 启用注释
  - `DOTALL` — 开启全行模式
  - `MULTINE` — 开启多行模式
  - `UNICODE_CASE` — 启用 Unicode 折叠
  - `UNIX_LINES` — 开启 unix 模式
- `@Size` — 这为 `CharSequence (String)` 的长度、`Collection` 中值的数量、`Map` 中条目的数量或任何数组类型的元素数量定义了包含性的最大值限制。

# 理解常用约束属性

如所示，我们有很多约束可以选择。除了已经提到的约束特定属性外，所有约束注解还具有以下可选属性。你创建的自定义约束也必须包含这些属性。

- `message`: 此 String 定义了应该向用户显示的消息。消息包含在大括号中（例如 `message="employee.firstName.notBlank"`）表示一个必须本地化的消息代码。否则，它仅仅是一个硬编码的消息。默认是每个约束类型有一个不同的消息代码。
- `groups` — 这是一个类数组，定义该约束属于哪个验证组或哪些组。默认情况下为空，意味着约束只属于默认组。验证组将在本节稍后的部分详细介绍。
- `payload` — 这是另一个类数组，类必须存在于 `javax.validation.Payload`。负载为评估约束的验证提供程序或 `ConstraintValidator` 提供大量的元信息。这使得内置约束类型在验证提供程序之间是不可移植的（API 未定义任何负载），但可以用于自定义约束。你可以将负载用于放置在自定义约束的任何地方，因此其理论用途超出了本书的范围。

最后，所有约束注解都定义了一个名为 `@List` 的内部注解，允许对目标应用多个该类型的约束。例如，你可以使用 `@Max.List` 注解对一个目标应用多个 `@Max` 约束。本节稍后关于验证组的部分演示了这些列表的一种可能用途。

# 使用约束

为了理解这些内置约束的基本用法，请查看 HR-Portal 项目中的 `Employee` POJO。它是基于章节开头看到的假设员工验证业务逻辑的。

```java
public class Employee {

    private long id;

    @NotNull(message = "{validate.employee.firstName}")
    private String firstName;

    @NotNull(message = "{validate.employee.lastName}")
    private String lastName;

    private String middleName;

    @NotNull(message = "{validate.employee.governmentId}")
    private String governmentId;

    @NotNull(message = "{validate.employee.birthDate}")
    @Past(message = "{validate.employee.birthDate}")
    private Date birthDate;

    @NotNull(message = "{validate.employee.gender}")
    private String gender;

    @NotNull(message = "{validate.employee.badgeNumber}")
    private String badgeNumber;

    @NotNull(message = "{validate.employee.address}")
    private String address;

    @NotNull(message = "{validate.employee.city}")
    private String city;

    @NotNull(message = "{validate.employee.state}")
    private String state;

    @NotNull(message = "{validate.employee.phoneNumber}")
    private String phoneNumber;

    @NotNull(message = "{validate.employee.email}")
    @Pattern(
        regex = "^[a-z0-9!#\\$%&'*+/=?^_`{|}~-]+(?:\\.[a-z0-9!#\\$%&'*+/=?^_`{|}~-]+)*@[a-z0-9](?:[a-z0-9-]*[a-z0-9])?(?:\\.[a-z0-9](?:[a-z0-9-]*[a-z0-9])?)*$",
        flags = Pattern.CASE_INSENSITIVE,
        message = "{validate.employee.email}"
    )
    private String email;

    @NotNull(message = "{validate.employee.department}")
    private String department;

    @NotNull(message = "{validate.employee.location}")
    private String location;

    @NotNull(message = "{validate.employee.position}")
    private String position;

    // mutators and accessors
}
```

你应该立即注意到一些问题：

- 除了 `manager` 和 `middleName` 之外，大多数字段都标注了 `@NotNull` 注解。
- 许多字段上执行的 `trim().length() > 0` 检查没有替代方案，这可能会很快变成问题。
- 如果在很多地方使用电子邮件正则表达式，它可能会变得非常繁琐。
- `birthdate` 仅在它处于过去时才进行检查，而没有确保员工至少满 18 岁。就此而言，`birthdate` 必须是日期类型才能使用内置约束，因此你可能更倾向于使用 Java 8 的日期类型。
- 没有检查员工的部门、位置和职位以确保它们是否存在。

你可以通过自定义约束来解决许多问题。然而，并不是每个检查都适用于 Bean Validation 工具。检查部门、位置和职位是否存在需要其他逻辑和数据库查询，因此这类任务被留给了手动验证。

> 注意：在本章的末尾，你将学习如何编写自定义校验约束，并满足诸如字符串长度、日期边界和电子邮件验证的需求。然而，除了创建自定义约束外还有其他选项。Hibernate Validator 具有你可以使用的专有约束，但这样做会让你绑定到始终使用 Hibernate Validator 作为你的提供者。

另一个选项是 Bean Validation 约束扩展项目（Maven 构件 `net.nicholaswilliams.java:validation-api-constraint-extensions`），它提供了所有内置约束的空安全版本，以及针对电子邮件、信用卡号、IP 地址、Java 8 日期和时间、Joda Date 以及其他目标的约束。由于此库只包含约束而不是 Bean Validator，因此它可以与任何提供者安全地使用。

# 使用 @Valid 进行递归校验

到为止，你一直在对 `String` 和基本数据类型等简单字段类型上标注校验约束。但如果你的 Bean 包含一个复杂的字段，且该字段本身标注了校验约束会呢？例如，考虑以下 Bean：

```java
public class Train {

    @NotNull
    private String name;

    @NotNull
    private Station origin;

    @NotNull
    private Station destination;

    @NotNull
    private Person engineer;

    @NotNull
    private Person conductor;

    // mutators and accessors
}
```

在这种情况下，`Station` 和 `Person` 字段是拥有自己字段的 POJO，而这些字段也标注了校验约束。这些嵌套对象不会被自动验证。为了确保它们是有效的，请在这些类型的字段上标注 `@Valid`，这表示字段、参数或方法（返回值）应该导致级联校验。

```java
public class Train {

    @NotNull
    private String name;

    @NotNull
    @Valid
    private Station origin;

    @NotNull
    @Valid
    private Station destination;

    @NotNull
    @Valid
    private Person engineer;

    @NotNull
    @Valid
    private Person conductor;

    // mutators and accessors
}
```

如果 `Station` 或 `Person` 包含也标记为 `@Valid` 的字段，校验将将递归继续直到所需的深度。然而，验证器通过循环引用检测无限循环，并在循环回到自身时不报错地终止对字段的验证。

# 使用校验组 (Validation Groups)

校验组提供了一种根据约束所属的或当前激活的组来启用和禁用某些约束的方法。这对于 Spring Framework 的 Bean 定义配置非常有用。一个组由任何任意的标记接口表示。该接口不需要任何常量或方法，因为它们没有被使用。相反，接口的类对象在声明约束时标识该组。然后，在验证时，校验器仅应用在调用 `validate`、`validateProperty` 或 `validateValue` 方法时指定了其组类的约束。

例如，一个多步骤输入的 UI，其中每个页面上的适当字段都成功填充了。你可能希望将所有内容存储同一个表单对象中。使用组，这很容易：

```java
public interface UIScreen1 { }

public interface UIScreen2 { }

public interface UIScreen3 { }

public class Form {

    @NotNull(groups = UIScreen1.class)
    private String field1;

    @NotNull(groups = UIScreen2.class)
    private String field2;

    @NotNull(groups = UIScreen2.class)
    private String field3;

    @NotNull(groups = UIScreen3.class)
    private String field4;

    // mutators and accessors
}
```

然后，当你准备好进行验证时，只需在每次调用校验器时传入相应的组类或类类，它就会应用匹配这些组的约束。如果你还想校验没有定义组约束，请使用 `javax.validation.groups.Default`。

```java
// 步骤 1 的方法
Set<ConstraintViolation> violations = validator.validate(form, Default.class, UIScreen1.class);

// 步骤 2 的方法
Set<ConstraintViolation> violations = validator.validate(form, Default.class, UIScreen2.class);

// 步骤 3 的方法
Set<ConstraintViolation> violations = validator.validate(form, Default.class, UIScreen3.class);
```

如果约束没有定义组，它包含在 `Default` 中。校验组对于根据不同的组应用相同的约束非常有用。例如 `@Size`，你可以指定在不同组中具有不同的长度。

```java
public class BusinessObject {

    @Size(min = 5, max = 100, groups = {Default.class, Group1.class})
    @Size(min = 20, max = 75, groups = Group2.class)
    private String value;

    // mutators and accessors
}
```

通常，Spring 使得利用校验组更容易。不需要访问校验器，你可以在注解中指定哪些组是激活的。你将在节节更多。

# 在编译时检查约束合法性

Java 语言对于你可以使用哪些注解有规则，这些规则通过注解上的 `java.lang.annotation.Target` 值指定。然而，关于你可以应用约束的规则比原生支持的复杂得多。

例如，约束注解在编译时允许 `ElementType.METHOD`（以及其他），但这忽略了约束注解只允许在实例字段而不是静态字段上的事实，但编译器无法强制这一点。更重要的是，不同的约束限于不同的类型（例如你不能在 `String` 上使用 `@Future`，你需要一种方法确保正确使用这些约束）。

Hibernate Validator 提供了一个编译时注解处理器，它钩入编译器，如果不遵循更严格的约束注解规则，将导致代码无法编译。这使得验证变得更容易，因为你在在使用它们之前就已经知道了。否则，你将在对象验证失败并抛出 `javax.validation.ConstraintDeclarationException` 时发现。使用注解处理器很简单：只需将 Maven 依赖添加到你的项目中。

```xml
<dependency>
```



```xml
<groupId>org.hibernate</groupId>
<artifactId>hibernate-validator-annotation-processor</artifactId>
<version>5.1.0</version>
<scope>compile</scope>
<optional>true</optional>
</dependency>
```

在 Maven 和 IDE 中你有其他方法来应用注解处理器。例如，你可以将依赖添加到编译器插件的依赖中，而不是项目依赖中，这会将类从你的类路径中移除，但会迫使你单独在 IDE 中设置该处理器。对该技术及其他技术的检查不在本书的范围之内。你应该查阅 Java 编译器、Maven 以及你 IDE 的文档以获取更多信息。

# 为方法验证配置 Spring Bean

到目前为止，你已经创建了一个能力的 Bean（Employee），但你还没有编写任何代码来验证它。现在，你已经发现可以使用 `Validator` 的 `validateProperty` 或 `validateValue` 方法来验证这个 Bean，但你真正想要的是验证自动发生，而无需直接使用 `Validator`。好在，Spring 让这一切变得简单。你通过设置 `MethodValidationPostProcessor` 完成了一部分工作，它会处理对方法参数和返回值进行验证的 Spring Bean。你只需要标记你的 Spring Bean 方法，以指示哪些返回值或参数应该被验证。

# 注解接口而非实现

使用契约编程（programming by contract）范式，开发者依赖代码的契约来满足需求或执行某些操作，而不关心这些需求是如何实现的。在 Java 中，接口被认为是契约编程的主要方法。你已经在第 14 章中深入探讨了这一点。你创建一个接口，并定义了方法来指示实现类应该做什么。通常，你会使用 Javadoc 注释来详细阐述接口保证的契约。然后，接口的消费者就可以盲目地使用它，而不需要甚至不知道实现是如何工作的。

约束注解（Constraint annotations）是编程契约的扩展。除了告诉 `Validator` 如何验证对象外，它们还告诉 API 消费者对类行为的预期。例如，一个标记了 `@NotNull` 的方法保证返回 `null`；自然地，你可能会想这些良好的约束在实现类上会起什么作用，答案是不会。事实上，它们可能会产生危害。

考虑以下场景：你正在调用接口上的一个方法，且它的没有任何参数带有约束注解。然而，底层的实现表明其中一个整数参数是 `@Max(12)`。当你调用接口方法时，你可能会提供一个 15 的值认为它是没问题的，但实现类会抛出异常，因为你违反了约束。因此，我们禁止对接口的实现类进行约束注解。如果你对这样的方法标记了注解，`Validator` 将在运行时抛出 `ConstraintViolationException`。这是 Hibernate Validator 注解处理器派上用用的另一个领域，因为它在编译期间就能检测到此类错误。

在使用约束注解进行方法验证时，你必须始终注解接口而非实现类。这确保了注解扩展了开发者所依赖的契约。如果开发者使用带有代码补全的智能 IDE，它会在他们使用每个方法时告知这些额外的约束要求。

# 在方法参数上使用约束和递归验证

现在你已经有一个 Employee 实体可以操作了，你需要一个服务来保存和检索 Employee。以下接口以尽可能简单定义了这样的服务。

```java
public interface EmployeeService {
    public void saveEmployee(Employee employee);
    public Employee getEmployee(long id);
    public List<Employee> getAllEmployees();
}
```

考虑一下需要应用于 `getEmployee` 和 `saveEmployee` 参数的业务规则。在检索单个 Employee 时，你希望 ID 始终是正数。为了标明这一约束，请在 `id` 参数上标记 `@Min`。

```java
public Employee getEmployee(
    @Min(value = 1, message = "validate.employeesService.getEmployee.id") long id
);
```

这足够简单；`Validator` 确保 ID 大于或等于 1，并返回带有给定消息代码的验证错误。保存 Employee 稍微复杂一些。你想要确保 employee 为 `null`，但你也希望对 Employee 进行验证以满足其约束。为了实现这一点，你只需要 `@NotNull` 约束和 `@Valid` 注解来指示递归验证。

```java
public void saveEmployee(
    @NotNull(message = "validate.employeesService.saveEmployee") Employee employee
);
```

现在，`Validator` 首先检查 Employee 是否为 `null`，如果是，它将返回带有给定消息代码的验证错误。如果不是，`Validator` 将应用你在 Employee 属性上声明的所有约束，并且如果 Employee 无效，则返回相应的验证错误或多个错误。

# 验证方法返回值

除了确保在向方法提供值时接口的约束遵循正确规则外，你还希望保证实现遵循关于返回值的规则。`EmployeeService` 接口中的 `getAllEmployee` 方法应该允许返回 `null`。如果没有 Employee 需要检索，它应该返回一个空列表。强制这一约束很简单，只需对该方法标记 `@NotNull`。

```java
@NotNull
public List<Employee> getAllEmployees();
```

注意，此约束没有提供消息代码。与方法约束不同（方法约束的状态通常由用户输入驱动），返回值表示的是实现问题，这是一个应该由程序而非用户解决的意外问题。这与受检查异常（checked exceptions）和未检查异常（unchecked exceptions）之间的概念区别相似。受检查异常应该被预期并优雅地处理，而未检查异常通常是编程错误。你完全可以为返回值约束提供消息代码，但这是没有的。如果应用程序编写得当，此约束永远不会失败，因此创建本地化消息是浪费时间。

另外请注意 `getEmployee` 方法没有标记 `@NotNull`；如果 employee 不存在，消费者希望得到一个 `null` 值。为了更清楚地表示 `null` 返回值是允许的，你可以使用 `@Nullable` 注解并用它来装饰方法。这样的注解不会在 `Validator` 中强制执行（它只表示返回值可能为 null，而不是必须如此），但它会改进你接口的契约。

> 注意：你当然可以使用静态分析器在编译时强制执行这些限制。各种工具（如 FindBugs 和 IntelliJ Annotations）提供了如 `@NotNull` 和 `@Nullable` 等注解，以及相应的注解处理器，可以检查注解并确保字节码无法违反这些限制（在在使用 `@Nullable` 值之前进行检查）。此类工具可以确保你不违反契约，并可以减少潜在的 bug 和运行时 `NullPointerException`。

# 指明类类适用于方法验证

现在既然你已经定义了方法的验证契约，你需要告诉 Spring 的 `MethodValidationPostProcessor` 实际上对方法的执行应用验证。这里你有几种选择。你可以使用标准的 `@ValidateOnExecution` 注解或 Spring 的 `@Validated` 注解。它们各有优劣。
`@ValidateOnExecution` 粒度更大，可以注解单个方法，也可以注解接口（应用于其所有方法），而你使用 `@Validated` 只能注解类或接口。另一方面，你可以在方法参数上使用 `@Validated`，但不能在方法参数上使用 `@ValidateOnExecution`。

如果你想指定在方法执行期间应应用的验证组，可以在类上使用 `@javax.validation.GroupSequence` 配合 `@ValidateOnExecution`。另一方面，`@Validated` 允许你直接在类中指定验证组，而无需额外的注解，并且允许你为同一个控制器类中不同的 MVC 控制器参数指定不同的组。（你无法通过 `@ValidateOnExecution` 和 `@GroupSequence` 实现此，因为 `@GroupSequence` 只能与 `@Valid` 一起使用。）遗憾的是，非 `@Validated` 标准注解不支持为同一个非控制器类中的方法参数指定不同的组。在所有情况下，`@Validated` 使用起来更简单。

```java
@Validated
public interface EmployeeService {
}
```

如果你希望验证只使用某个组或若干组中的约束条件，可以在 `@Validated` 注解中指定这些组。

```java
@Validated({Default.class, Group1.class})
public interface EmployeeService {
}
```

你的应用程序需要 `EmployeeService` 的实现。接下来的默认实现充满了空操作方法（no-operation methods），因为你不需要实际保存任何数据来证明验证工作正常。请注意，该实现缺少任何与验证相关的注解。之所以是这样是因为接口包含了该契约。`getAllEmployees` 方法返回 `null`，这违反了契约。你稍后在章节中也会演示这一点。

```java
@Service
public class DefaultEmployeeService implements EmployeeService {
    @Override
    public void saveEmployee(Employee employee) {
        // no-op
    }

    @Override
    public Employee getEmployee(long id) {
        return null;
    }

    @Override
    public List<Employee> getAllEmployees() {
        return null;
    }
}
```

# 在 Spring MVC 控制器中使用参数验证

除了验证服务、存储库和其他 Bean 的方法执行外，Spring 还可以验证 MVC 控制器处理方法中的指定参数。为了演示这一点，你需要一个 `EmployeeController` 和 `EmployeeForm`。`EmployeeForm` 缺少了 `Employee` 中的许多字段，但这没关系。你并不是试图实际创建 `Employee` 对象；你是在尝试演示 Bean Validation。`EmployeeForm` 同时使用了 `@NotNull` 和 `@Size`，因为某些人发送的是空字符串，而另一些人对表单字段返回 `null`。

```java
public class EmployeeForm {
    @NotNull(message = "*(validate.employee.firstName)")
    @Size(min = 1, message = "*(validate.employee.firstName)")
    private String firstName;

    @NotNull(message = "*(validate.employee.lastName)")
    @Size(min = 1, message = "*(validate.employee.lastName)")
    private String lastName;

    private String middleName;

    // mutators and accessors
}
```

控制器包含一个 `listEmployees` 处理方法，用于响应索引请求并列出员工。正如你预期的，该请求会因 `ConstraintViolationException` 失败，因为默认的 `getAllEmployees` 方法返回 `null` 违反了契约。它还包含一个用于获取员工创建表单的简单处理方法。这些都是你以前见过并做过的标准操作。

```java
@Controller
public class EmployeeController {
    @Inject EmployeeService employeesService;

    @RequestMapping(value = "/", method = RequestMethod.GET)
    public String listEmployees(Map<String, Object> model) {
        model.put("employees", this.employeesService.getAllEmployees());
        return "employee/list";
    }

    @RequestMapping(value = "/create", method = RequestMethod.GET)
    public String createEmployee(Map<String, Object> model) {
        model.put("employeeForm", new EmployeeForm());
        return "employee/create";
    }
}
```

控制器的最后一个方法负责处理员工创建表单的提交。它执行了一些你可能不熟悉的新操作。首先，该方法标记了 `@Valid` 注解，这告诉 Spring 在执行方法之前验证 `EmployeeForm`。通常情况下，约束违规会导致异常，但 `Errors` 参数的存在意味着 Spring 会将验证错误传递给方法而不是抛出异常，从而允许你细致地处理这些错误。（这仅适用于控制器方法）。该方法首先检查表单错误是否存在，如果存在则将用户带回表单。然后它将表单内容复制到 `Employee` 对象中并尝试保存员工，但由于员工信息不完整会导致失败。如果检测到约束违规，它会将它们设置为模型并将用户带回表单。

```java
@RequestMapping(value = "create", method = RequestMethod.POST)
public ModelAndView createEmployee(Map<String, Object> model,
    @Valid EmployeeForm form, Errors errors) {
    if (errors.hasErrors()) {
        model.put("employeeForm", form);
        return new ModelAndView("employee/create");
    }

    Employee employee = new Employee();
    employee.setFirstName(form.getFirstName());
    employee.setLastName(form.getLastName());
    employee.setMiddleName(form.getMiddleName());

    try {
        this.employeesService.saveEmployee(employee);
    } catch (ConstraintViolationException e) {
        model.put("validationError", e.getConstraintViolations());
        return new ModelAndView("employee/create");
    }

    return new ModelAndView(new RedirectView("/", true, false));
}
```

# 向用户显示验证错误

这个过程可能引发了一些关于为什么要验证提交数据的问题。请记住，`EmployeeService` 封装了你的核心业务逻辑。控制器只是位于它前面的用户界面。你可能还有其他用户界面——例如 Web 服务或桌面应用程序——位于它前面。业务规则应该应用于每个用户界面；约束应该在服务层应用。

那么，为什么要验证表单呢？嗯，正如下面的 JSP 代码中所示，Spring 可以将验证错误与屏幕上的表单字段关联。这允许你将 `firstName` 属性相关的错误（例如）显示在“First Name”字段旁边——这是一种更好的用户体验。然而，这只有在验证的是表单对象时才有效，因此你必须验证表单对象。

为了验证在表单顺序中遗漏或只能在业务逻辑中应用的错误（例如测试部门是否存在），你还必须在业务层验证该对象，并有一种优雅的方式来显示非表单验证错误。`/WEB-INF/jsp/view/employee/create.jsp` 文件（如下所示代码片段的一部分）显示了这两种错误。

```jsp
<h2><spring:message code="title.create.employee" null="/" /> </h2>
<c:if test="${validationErrors}">
  <div class="errors">
    <ul>
      <c:forEach items="${validationErrors}" var="error">
        <li><c:out value="${error.message}" /></li>
      </c:forEach>
    </ul>
  </div>
</c:if>
```



<form method="post" modelAttribute="employeeForm">

  <label path="firstName"><spring:message code="form.first.name" /></label><br>

  <input type="text" path="firstName" /><br>

  <form:errors path="firstName" css="errors" /><br>

  <label path="middleName"><spring:message code="form.middle.name" /></label><br>

  <input type="text" path="middleName" /><br>

  <form:errors path="middleName" css="errors" /><br>

  <label path="lastName"><spring:message code="form.last.name" /></label><br>

  <input type="text" path="lastName" /><br>

  <form:errors path="lastName" css="errors" /><br>

  <input type="submit" value="Submit" />

</form>

现在你已经有了用户界面，是时候测试一下 Bean Validation 了：

1. 编译应用程序并在 IDE 中启动 Tomcat。
2. 访问 `http://localhost:8080/portal/`，你应该会在浏览器窗口中立即看到一个 HTTP 500 错误，包含 `ConstraintViolationException`。这是预期的，意味着 Bean Validation 正常工作，因为 `DefaultEmployeeService` 方法返回了 `null`。
3. 现在访问 `http://localhost:8080/portal/create`，你应该看到员工创建表单。
4. 在不填写任何字段的情况下，表单应该显示类似图 16-1 的界面，其中 First Name 和 Last Name 字段下方有错误。这意味着你的表单对象因为你没有提供这些值而验证失败。
5. 填写这些字段并再次提交表单。你现在看到了另一组错误，如图 16-2 所示。这些错误是 Bean Validation 拦截 `EmployeeService` 上的 `saveEmployee` 方法并确保你的 `Employee` 符合所有业务规则的结果。

## 为方法验证配置 Spring Beans

![](img/9c2d45f6d547f72cb870b3a991f62ef6_500_0.png)

图 16-1

![](img/9c2d45f6d547f72cb870b3a991f62ef6_500_1.png)

图 16-2

## 编写自定义校验约束

到此时，你可能已经注意到应用程序可以使用一些自定义约束。例如，在整个 `Employee` 类中使用的 `@NotNull` 不足以检测空字符串。`EmployeeForm` 使用了 `@NotNull` 和 `@Size`，但这无法检测只包含空格的字符串。你真正需要的是 `@NotBlank`。此外，如果你需要多次使用电子邮件正则表达式，会非常繁琐，而一个 `@Email` 约束无疑对此有所帮助。

幸运的是，在 Bean Validation 中编写自定义约束非常简单。在 com.wrox 代码网站上提供的 `Custom-Constraints` 项目是 `HR-Portal` 项目的扩展，它添加了自定义约束 `@com.wrox.site.validation.NotBlank` 和 `@com.wrox.site.validation.Email`。现在我们先从 `@Email` 约束开始，信不，它更容易。

## 在自定义约束中继承其他约束

在 Bean Validation 中，约束可以相互继承。当然，这不等同于继承另一个，因为你不能扩展注解。然而，按照惯例，约束注解通常包含一个目标 `Element.ANNOTATION_TYPE`。当一个约束被标记注解时，`Validator` 会确定该注解定义是否也标记了任何其他约束。如果是，它将所有额外的约束与原始约束定义的逻辑（如果有）合并成一个单一复合体。从这个意义上说，该约束继承了所有它所标记的约束。如果出于某种原因，你需要创建一个不能被继承的约束，只需从源头定义中省略 `Element.ANNOTATION_TYPE` 即可。考虑到所有这些，请查看 `@Email` 的细节。

```java
@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
    ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Constraint(validatedBy = Email.class)
@Pattern(regexp = "[a-z0-9#$&'*{}/\\\\-]+\\.[a-z0-9#$&'*{}/\\\\-]+\\+[a-z0-9#$&'*{}/\\\\-]+\\]+\\|+[a-z0-9#$&'*{}/\\\\-]+\\.[a-z0-9#$&'*{}/\\\\-]+\\+[a-z0-9#$&'*{}/\\\\-]+\\+", flags = Pattern.CASE_INSENSITIVE)
@By(EmailValidator.class)
public interface Email {

    String message() default "@com.wrox.site.validation.Email message";

    Class<?>[] groups() default {};

    Class<? extends Payload>[] payload() default {};

}
```

```java
@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(RetentionPolicy.RUNTIME)
@Documented
static interface List {

    Email[] value();

}
```

```java
@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
                ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Constraint(validatedBy = {NotNullValidator.class})
@NotNull
@ReportAsSingleViolation
public @interface NotBlank {

    String message() default="{com.wsite.validation.NotBlank.message}";

    Class<?>[] groups() default {};

    Class<? extends Payload> payload() default {};

}
```

```java
@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
                ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface List {

    NotBlank value();

}
```

与 `@Email` 不同，它不能继承其所有的功能。它需要一个 `ConstraintValidator` 来测试值是否为空。接下来的 `NotBlankValidator` 类声明在 `@NotBlank` 注解的 `@Constraint` 注解中，它实现了这一点。

```java
public class NotBlankValidator
implements ConstraintValidator<NotBlank, CharSequence>{

    @Override
    public void initialize(NotBlank annotation) {
    }

    @Override
    public boolean isValid(CharSequence value, ConstraintValidatorContext context) {
        if (value instanceof String)
            return ((String)value).trim().length() > 0;
        return value.toString().trim().length() > 0;
    }
}
```

有了新的约束后，查看 `Employee` 和 `EmployeeForm` POJO。我们已经将它们的大部分 `@NotNull` 约束替换为 `@NotBlank`，并且 `EmployeeForm` 不再使用 `@Size`。`Employee` 中的 `email` 字段更改为 `@Email`，并在 `EmployeeForm` 中添加了另一个电子邮件字段，以便你可以看到电子邮件验证的效果。

```java
@NotNull(message = "validate.employee.email")
@Email(message = "validate.employee.email")
private String email;
```

此外，在 `employee/create` JSP 中添加了一个电子邮件字段。最后完成：

1. 编译并启动应用程序，访问 `http://localhost:8080/portal/create`。
2. 提交一个空表单，你会看到 `@NotBlank` 约束生效了。
3. 现在为所有字段输入数据，但输入一个无效的电子邮件地址，例如没有 @ 符号的。
4. 再次提交表单，Email 字段仍然标记为错误，因为不是有效的电子邮件地址。
5. 输入有效的电子邮件地址并再次提交表单，验证通过。

## 理解约束生命周期

`@NotBlank` 和它的 `NotBlankValidator` 当然非常简单。根据约束类型、值类型和约束属性，你可以执行许多高级任务。要理解这些，首先需要理解约束的生命周期。

当 `Validator` 遇到字段、参数或其他目标上的约束时，它首先检查该约束是否标记了其他约束。如果是，它会首先处理这些约束。如果不是，只要通过了所有继承的约束，该值就被认为是有效的。如果是，`ConstraintValidator` 是类型最匹配的。例如，你可以创建一个支持 `CharSequence`、`int` 和 `Integer` 的约束。对于这样的约束，你需要两个不同的 `ConstraintValidator`：

```java
public class IntValidator
implements ConstraintValidator<MyConstraint, Integer> { ... }
```

```java
public class StringValidator
implements ConstraintValidator<MyConstraint, CharSequence> { ... }
```

```java
@Constraint(validatedBy = {IntValidator.class, StringValidator.class})
```

在匹配到 `ConstraintValidator` 后，`Validator` 会实例化并调用 `ConstraintValidator` 的 `initialize` 方法。该方法每次使用约束时调用一次。如果你有一个 10 个字段的类且 5 个使用了你的约束，则会创建 5 个 `ConstraintValidator` 实例并在每个字段复用同一个实例。`initialize` 方法允许从特定的注解实例获取值（例如 `@Size` 注解的 `min` 和 `max` 属性）。这样，你就可以一次性决定约束如何验证目标值，从而提高 `isValid` 的执行效率。初始化完成后，`Validator` 调用 `isValid`，并在之后每次字段、参数或其他目标被验证时都会调用 `isValid`。

## 在客户支持应用中集成验证

Customer-Support-v13 项目可以从 wrox.com 代码下载站点下载，它演示了 Bean Validation 1.1 更深层次的集成。它并没有真正使用你在本章中尚未过的任何新内容，但是一个更稳定的应用程序，将验证逻辑应用到表单、POJOs 和 Bean 中。`TicketController.TicketForm` 和 `AuthenticationController.LoginForm` 使用约束注解来确保表单字段为空，并且控制器中相应的提交方法返回 `Errors` 对象和 `ConstraintViolationException` 以检测并向用户报告错误。

```java
@RequestMapping(value = "create", method = RequestMethod.POST)
public ModelAndView create(Principal principal, @Valid TicketForm form, Map<String, Object> model)
    throws Errors, ConstraintViolationException
{
    if (errors.hasErrors())
        return new ModelAndView("ticket/add");
    try
    {
        this.ticketsService.save(ticket);
    }
    catch (ConstraintViolationException e)
    {
        model.put("validationError", e.getConstraintViolations());
        return new ModelAndView("ticket/add");
    }
}
```

```java
@RequestMapping(value = "login", method = RequestMethod.POST)
public ModelAndView login(Map<String, Object> model, HttpSession session, HttpServletRequest request, @Valid LoginForm form, Errors errors)
{
    if (UserPrincipal.getPrincipal(session) != null)
        return this.getTicketRedirect();
    if (errors.hasErrors())
    {
        form.setPassword(null);
        return new ModelAndView("login");
    }
    Principal principal;
    try
    {
        principal = this.authenticationService.authenticate(
        form.getUsername(), form.getPassword());
    }
}
```

```java
catch (ConstraintViolationException e)
{
    form.setPassword(null);
    model.put("validationErrors", e.getConstraintViolations());
    return new ModelAndView("login");
}
```

值得注意的一点是，`Attachment` 具有约束，以确保名称和内容为空，且附件内容至少包含 1 字节。然后，`Ticket` 中的附件列表使用 `@Valid` 注解来确保对票单的所有附件进行递归验证。

```java
public class Attachment
{
    @NotBlank(message = "{validate.attachment.name}")
    private String name;
    @NotBlank(message = "{validate.attachment.mimeContentType}")
    private String mimeContentType;
    @Size(min = 1, message = "{validate.attachment.contents}")
    private byte[] contents;
    // mutators and accessors
}
```

```java
public class Ticket
{
    // other fields
    @Valid
```



```java
private Map<String, Attachment> attachments = new LinkedHashMap<>();

// mutators and accessors
}
```

为了确保 `Tickets` 在保存之前是有效的，`TicketService` 使用了 `@Validated`，并且其所有方法都包含约束，以强制接口合约。

```java
@Validated
public interface TicketService {

    @NotNull
    List<Ticket> getAllTickets();

    Ticket getTicket(
        @Min(value = 1L, message = "{validate.ticketService.getTicketId}")
        long id
    );

    void save(@NotNull(message = "{validate.ticketService.save.ticket}")
        @Valid Ticket ticket);
}
```

同样，`AuthenticationService` 也标记了 `@Validated`，并带有约束以确保用户名和密码为空。

```java
@Validated
public interface AuthenticationService {

    Principal authenticate(
        @NotBlank(message = "{validate.authenticate.username}")
        String username,
        @NotBlank(message = "{validate.authenticate.password}")
        String password
    );
}
```

根据这些笔记，制作并编译项目，从你的 IDE 启动 Tomcat，然后访问 `http://localhost:8080/support/`。你应该注意到验证现在登录屏幕和票单创建屏幕上生效了，你仍然可以登录并创建票单。

### 总结

在本章中，你学习了 Bean Validation 1.1（取代 JSR 303 的 JSR 349）、Hibernate Validator 5.1 以及在 Spring Framework 中配合使用 Bean Validation 和 Hibernate Validator。你探索了在 Spring 容器中配置 Bean Validation 的各个方面，以及向你想要验证的 POJO 和表单对象添加约束注解。你还学习了如何对你的 Spring Bean 进行自动方法验证限定，以及如何在你的 Spring MVC 控制器处理方法中触发表单验证。最后，你尝试了创建自定义约束，并一窥了使用自定义 Bean Validation 约束可以做的许多事情。

在下一章中，你将探索作为 RESTful 服务的 Spring MVC 控制器，并学习其中许多细节，包括错误处理和 HTTP 响应状态码。

# 17

# 创建 RESTful 和 SOAP Web 服务

本章内容

- 什么是 Web 服务？
- 如何使用 Spring MVC 配置 RESTful Web 服务？
- 如何测试你的 Web 服务端点
- 如何充分利用 Spring Services 实现 SOAP

本章的 WROX 代码下载

你可以在 `http://www.wrox.com/go/javaforwebebapps` 的 "Download Code" 标签页中找到本章的 wrox.com 代码下载。本章的代码分为以下示例：

- Web-Service 项目
- Customer-Support-v14 项目

本章的新 MAVEN 依赖

除了之前章节引入的 Maven 依赖外，你还需要以下依赖：

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-aop</artifactId>
  <version>4.0.2</version>
  <scope>compile</scope>
</dependency>
```

## 起初有了 SOAP

不，我们并不是在谈论你洗手和洗澡时使用的物质。事实上，有些开发者在使用 SOAP 后反而觉得更脏了，而不是更干净。但我离题了。SOAP 原意是简单对象访问协议，是一种使用 XML 消息形式表示的结构化数据进行机器间交互的协议。在协议的 1.2 版本中（首次由 W3C 采用），缩写被去掉了，该词变得独立存在。当然，SOAP 并不是广义 Web 服务的开始，因为 XML-RPC 等技术在 SOAP 之前就已经存在。然而，SOAP 的采用被认为是 Web 服务开始在企业中变得流行的转折点。

SOAP 具有推动其流行的三个主要特性：

- 它是**可扩展**的，因为可以在基础协议之上添加安全等其他功能。
- 它是**中性的**，因为使用何种传输机制并不重要——HTTP、JMS、AMQP、SMTP、TCP 等都是可选方案。
- 它是**无关的**，因为 SOAP 不依赖于任何特定的编程模型。

然而，SOAP 确实鼓励“契约优先”（contract-first）设计。Web 服务描述语言（WSDL）技术定义了一种建立契约的方法，用户应当遵守，而 Web 服务承诺遵循。它定义了特定位置可用 Web 服务的位置，以及来自这些服务的请求和响应的数据格式。通常使用 XSD（称为 XML Schema 定义），契约通常在编写任何 Web 服务代码之前创建，而 Web 服务是根据该契约创建的。这类似于测试驱动开发的概念——在单元测试和应用测试中，测试先于应用程序编写，而应用程序是为了通过测试而编写的——与之形成鲜明对比的是契约最后（contract-last）设计，先创建 Web 服务，再编写契约来匹配它。

契约优先设计有其优点，而且，明确定义用户需求并编写满足这些需求的应用程序，总是比写一个应用程序后再弄清楚它是否满足用户需求要好。明确定义用户需求和编写 WSDL 是两码事，用纯语言显式地定义契约、编写符合要求的 Web 服务代码，然后使用 XML 工具自动生成复杂的 WSDL 要容易得多。在本书中，你将采用这种方法，避免手动处理 WSDL 文件。

SOAP 不是一个简单的协议。每个 SOAP 消息（请求或响应）都以一个名为 Envelope（包封）的根元素开始。关于消息的所有信息都在这个封体内。包封有一个可选的 SOAP Header（头部）元素（不要与 HTTP header 混淆），包含特定的应用程序信息，如身份验证详情。包封内部还有强制性的 SOAP Body（主体）元素，它包含请求或响应的指令和数据。最后，响应可以有一个可选的 SOAP Fault（故障）元素，用于描述处理请求期间发生的任何错误。

这些元素的细节非常多，很大程度上由 WSDL 定义。编写和处理 WSDL 文档有时是一项复杂且混乱的任务，你在过程中能越干净地集成自动化，就越好。更糟糕的是，XML 是最冗长且最消耗带宽和处理器的数据格式之一。尽管 SOAP 可能非常有用且强大，但幸运的是，它并不是唯一选择。

## RESTful 服务提供更简单的方法

表述状态转换（REST）是一种 Web 服务概念，在很多方面与 SOAP 相似。REST 架构由服务器和客户端组成。客户端通过请求（获取或更改资源状态的请求）进行状态转换，服务器处理请求并返回相应的资源。资源可以是客户端和服务器理解的任何概念，并以约定的表示形式传输。REST 不依赖或指定资源类型或表示形式。资源可以是想象中的任何类型的数据。它们的表示形式可以是纯文本、HTML、XML、YAML、JSON 或任何客户端和服务器理解的其它格式。REST 系统使用 URL 运行，URL 指明资源类型、表示资源形式的*动词*（verbs）以及指明数据的*媒体类型*（MIME）类型。如果这让你想起了 HTTP 和万维网（Wide Web），那是非常自然的，而且这并非巧合。Roy Fielding 是 HTTP 1.0 和 1.1 的作者之一，并在 2000 年的博士论文中将表述状态转换定义为一部分。万维网本身就是存在的最大的系统。

RESTful 服务背后的主要原则是，对资源不需要执行大量主要的操作。这些操作通常被称为 CRUD：创建（Create）、读取（Read）、更新（Update）和删除（Delete）。HTTP 规范中的方法很容易映射到这些：*POST、GET、PUT 和 DELETE*。SOAP 使用 envelope 元素来描述操作（执行的方法），而 REST 依赖 HTTP 协议来提供包封。SOAP 还使用 envelope 来识别被操作的资源，而 REST 则依赖 HTTP URL。

在 RESTful Web 服务中，*Content-Type* 头部告知服务器主体的表示形式，*Accept* 头部或文件扩展名请求特定的响应表示，而 *Content-Type* 头部告知客户端响应体的体的形式。

通过这些信息，你可以看到每个协议正在呈现的优缺点。RESTful Web 服务绑定于 HTTP，而 SOAP 是协议无关的，SOAP 赢了。（注：此处原文存在大量重复句，已按要求翻译并保持逻辑）。

## 理解 Web 服务

RESTful 服务的核心卖点之一是缺少 WSDL。需要明确的是，这并不意味着 RESTful 服务没有契约。

## 理解可发现性

RESTful 服务的另一个特性是其可发现性……万维网可以在不需要的情况下被发现。作为用户，你可以打开浏览器并访问任何主页。从主页，你可以通过超链接发现网站内的其他页面。点击超链接将带你进入带有新链接的页面。通过这种方式，在不需要预先了解网站的情况下，你可以找到资源并与这些资源交互。这种约束被放置在官方的 REST 应用架构上。REST 客户端应该能够在不需要预先了解该服务可用资源的情况下使用 RESTful Web 服务。这种概念被称为超媒体作为应用状态引擎（HATEOAS），它使用超文本（XML、YAML、JSON 或你选择的任何格式）结合链接来告知客户端 Web 结构。例如，对 Web 服务基础 URL 的请求和响应可能如下：

```
> GET /services/Rest/ HTTP/1.1
> Accept: application/json
```

```
200 OK
Content-Type: application/hal+json

{
  "links": {
    "self": {"href": "http://example.com/services/Rest"},
    "account": {"href": "http://example.com/services/Rest/account"},
    "order": {"href": "http://example.com/services/Rest/order"}
  }
}
```

通过这些数据，客户端现在知道了 Web 服务提供的资源。如果它想进一步探索账户，它有两个选择。它可以简单地向资源发送 GET 请求。这被称为集合请求（或对集合 URI 的请求），返回该类型的所有可用资源。

```
> GET /services/Rest/account HTTP/1.1
> Accept: application/json
< 200 OK
< Content-Type: application/json
< {
  "value": [
    {
      "id": 1075,
      "name": "John Smith",
    },
    {
      "id": 1076,
      "name": "Adam Green"
    }
  ]
}
```

这有几个缺点。首先，这个集合可能非常大——甚至是海量的。想象一下 Amazon.com 返回每个产品的服务，你就能很快理解这个问题了。显而易见的解决方案是对资源进行分页（paging），在大多数情况下，都需要分页来避免噩梦般的资源场景。（在下一节中，你将在实现 SPRING REST 控制器时更详细地探索分页。）另一个问题是，此列表包含了资源数据，但没有指向这些资源的链接。一种方案是返回链接列表，但这会让集合请求对于向终端用户显示列表变得毫无用处。因此，许多 Web 服务在集合响应中使用属性和链接的组合。

客户端可以采取的进一步探索账户资源的另一个操作是对资源发出 OPTIONS 请求。

```
> OPTIONS /services/Rest/account HTTP/1.1
> Accept: application/json
< 200 OK
< Allow: OPTIONS, HEAD, GET, POST, PUT, PATCH, DELETE
< {
  "GET": {
    "description": "Get a resource or resources",
    "resourceTemplate": "http://example.net/services/Rest/account/{id}",
    "parameters": {
      "$select": {
        "type": "array/string",
        "description": "The properties to be returned for each resource."
      },
      "$filter..."
    }
  },
  "POST": ...
}
```

OPTIONS 响应非常强大。它不仅可以告诉客户端某种资源类型可以使用哪些操作，还可以根据客户端的权限进行过滤。例如，如果客户端拥有查看权限但没有创建、更新或删除权限，则 Allow 响应头的值将是 OPTIONS, HEAD, GET。此外，根据许多因素（包括权限），不同的资源可能可以使用不同的操作，如下所示两个请求及其响应所示：

```
> OPTIONS /services/Rest/account/1075 HTTP/1.1
> Accept: application/json
```

```
< 200 OK
< Allow: OPTIONS, HEAD, GET, PUT, PATCH, DELETE
< ...
```

```
> OPTIONS /services/Rest/account/1076 HTTP/1.1
> Accept: application/json
```

```
< 200 OK
< Allow: OPTIONS, HEAD, GET
< ...
```



# RESTful Web 服务中的可发现性

RESTful Web 服务中可发现性（discoverability）的主要问题是，对于发现资源的内容没有统一的单一标准。响应格式中的链接采用的是超文本应用语言（HAL）的 JSON 表示，这是多个新兴标准中的之一，且并非由某一家公司制定。集合请求仅对应标准的 JSON 集合，仅此而已。而 `OPTIONS` 响应中的 `Allow` 头是标准且通用的，但响应体完全是虚构的，这正是许多厂商的做法。

缺乏通用标准可能导致很少有厂商实现可发现性。你需要评估自己的需求和当时的技术来决定使用哪种可发现性。你甚至可以决定不支持可发现性，并告诉客户端阅读说明文档，这是可以的。好消息是，在 Spring Framework 中实现的 RESTful Web 服务并不依赖于所使用的资源或表示，因此采用某种标准而非另一种标准不会改变你在本章中学到的语法。

# 使用 URL、HTTP 方法和 HTTP 状态码

在阅读时，RESTful Web 服务使用 URL 来标识请求的资源，使用 HTTP 方法来确定所需的操作。它们还使用 HTTP 状态码来显示请求的结果。然而，有几个状态码是通用的适用于所有类型的请求：

- **400 Bad Request** 表示客户端提出的请求不支持或不被识别。这通常是因为没有遵循正确的请求语法。例如，如果资源的必填字段在 `POST` 或 `PUT` 请求中留空，将导致 `400 Bad Request` 响应。响应体应在约定的表示格式或在缺失时的默认表示格式中包含有关请求错误原因的信息。

- **401 Unauthorized** 信号表示访问请求的资源或执行请求的状态转换之前需要身份验证和授权。响应的内容根据其中使用的身份验证协议（如 OAuth）而异。

- **403 Forbidden** 表示客户端虽然通过了身份验证，但没有权限访问资源或执行请求的状态转换。根据所使用的身份验证协议，使用更多请求权限重新验证可能会解决此冲突。

- **404 Not Found** 非常简单地告诉客户端资源不存在。它永远不应该用于表示资源存在但状态转换简单不支持或不允许允许。这正是 `405 Method Not Allowed` 和 `403 Forbidden` 所承担的含义。

- **405 Method Not Allowed** 表示请求的状态转换（HTTP 方法）不支持。它永远不应该用于表示客户端没有权限执行该状态转换；`403 Forbidden` 留给此类用途。

- **406 Not Acceptable** 表示 `Accept` 头中请求的表示格式不受服务器支持。例如，客户端请求了 `application/xml`。

- **415 Unsupported Media Type** 表示请求的媒体类型不支持。

- **500 Internal Server Error** 表示在处理请求时发生了错误。

# 理解 Web 服务

本节剩余部分将涵盖 HTTP 方法的语法和语义，包括状态码。

如所示，`OPTIONS` 是仅有的几种发现机制之一。当对资源发出 `OPTIONS` 请求时，服务器必须返回 `200 OK`，并带有一个指定支持哪些方法的 `Allow` 头。如果客户端已通过身份验证，该头还可能包含支持的表示格式。

## HEAD 和 GET

每当资源支持并允许 `GET` 时，`HEAD` 也必须被支持并允许。`GET` 和 `HEAD` 的唯一区别在于 `HEAD` 响应没有主体。`HEAD` 响应必须包含标识 `GET` 响应内容的头部。`GET` 请求用于获取资源或资源。如 `/services/Rest/account` 的 URL 表示客户端想要所有账户或过滤后的账户列表。通常，过滤、排序和分页指令包含在查询参数中。

如 `/services/Rest/account/1075` 的请求表示客户端想要获取唯一标识为 1075 的单个账户。某些厂商还允许关联 URL，如 `/services/Rest/account/1075/order` 和 `/services/Rest/account/1075/order/1522`，分别请求账户 1075 的（可能经过过滤的）订单列表以及属于账户 1075 的订单 1522。这种递归在理论上可以一直持续到 URL 长度限制。`/services/Rest/account/1075/order/1522/item/12` 可以返回某个账户订单中的特定行项目。

> **注意**：某些 Web 服务启用了跨资源共享（CORS）。这种特殊的、相对新的协议允许浏览器应用程序通过一组特殊的头部绕过 AJAX 同源策略。如果你希望你的服务能被 JavaScript 直接访问，你需要启用 CORS。这些详细细节超出了本书范围。启用 CORS 的 Web 服务必须支持 `OPTIONS` 请求，并在响应 `OPTIONS` 请求时包含 `Access-Control-Allow-Methods` 头，其内容与 `Allow` 头相同。

> **注意**：在此处演示的 URL 中，账户和订单路径段使用的是单数形式。这仅仅是一种选择，并非强制要求。URL 也可以包含复数的账户和订单路径段。这取决于你，你应该选择一种并在你的资源中保持一致。通常情况下，使用单数路径段可以获得更短的 URL，在需要时允许查询字符串包含更多内容。

服务器对于 `GET` 和 `HEAD` 请求应返回 `200 OK`，并在 `GET` 请求的响应体中按照约定（或默认）表示包含所请求的资源或多个资源。

`GET` 和 `HEAD` 请求也是空幂等的（nullipotent），且不应对服务器上的资源产生任何副作用。

## POST

`POST` 请求用于在服务器上创建新资源。`POST` 请求始终应指向集合 URI (`/services/Rest/account`)，但它也可以指向子集合 URI (`/services/Rest/account/1075/order`)。指向单个元素 URI (`/services/Rest/account/1075`) 的 `POST` 请求应返回 `405 Method Not Allowed`（方法未允许）。在成功的 `POST` 操作中，服务器会创建请求的资源并返回 `201 Created`。响应应包含一个带有新创建资源 URL 的 `Location` 头。

例如，向 `/services/Rest/account` 发出的创建新账户的 `POST` 请求可能会在 `Location` 头中返回 `http://www.example.com/services/Rest/account/9156`。响应体应该是被创建的资源，因为通过 `Location` 头中的 URL 发送 `GET` 请求时，该资源会被返回。

`POST` 请求是非空幂等的（非安全的——请求会导致一个或多个资源的倍增）且非等幂等的（多次发送完全相同的 `POST` 请求将导致多个被创建的资源）。

## PUT

`PUT` 请求会导致服务器上资源的替换。因此，`PUT` 请求用于更新现有资源。与 `POST` 请求不同，`PUT` 请求绝不会用于更新集合。它们被用于单个元素 URI (`/services/Rest/account/1075`, `/services/Rest/account/1075/order/5122`)。指向集合 URI 或子集合 URI 的 `PUT` 请求应返回 `405 Method Not Allowed`。成功 `PUT` 请求的响应应返回 `204 No Content`（无内容），且其正文应为空。

显然，`PUT` 请求并不是空幂等的。然而，它们应该是等幂等的。两个或多个连续的相同的 `PUT` 请求除了第一个 `PUT` 请求产生的副作用外，没有其他副作用。

这可能面临挑战的一个领域是如果更新的资源包含了“最后修改”时间戳或版本。为了遵守等幂性限制，服务器仅在底层实体确实发生变化时，才为 `PUT` 更新资源的时间戳和/或版本号。这种要求实现起来可能非常有挑战性，因此许多供应商以部分等幂的方式实现 `PUT`，并说明在相同的 `PUT` 请求中仍使用时间戳和版本。

## PATCH

`PATCH` 请求在目的和语义上都与 `PUT` 请求非常相似。`PATCH` 是一个相对新的 HTTP 方法，仅在过去几年中被添加。它不是原始 HTTP/1.1 规范的一部分。`PATCH` 请求与 `PUT` 请求一样，也旨在更新单个 URI 处的资源。然而，`PATCH` 请求表示对资源进行部分更新，而不是完全替换资源。

例如，向 `/service/Rest/account/1075/order/5122` 发出的 `PATCH` 请求仅包含 `shippingaddress`（收货地址）属性，那么只有订单中的 `shippingaddress` 将被更新。其他属性将保持不变（时间戳和版本除外）。这是一个非常强大的方法，但实现起来也很有挑战。为了支持 `PATCH`，你的应用程序必须在请求中接受一组非常灵活的属性，然后仅处理请求中存在的资源。你不能使用 null 检查，因为 `PATCH` 可能会将某个属性设置为 null。

成功 `PATCH` 请求的响应应返回 `200 OK` 或 `204 Content`。客户端可以选择在响应体中返回完整的更新实体或不返回内容。如果支持 `PATCH`、请求的媒体类型受支持，且 `PATCH` 请求被成功理解和解析，但服务器无法应用补丁（例如，补丁会导致实体无效），服务器应返回 `422 Unprocessable Entity`（无法处理实体）。如果使用 `If-Match` 请求头或 `If-Unmodified-Since` 请求头定义补丁的前提条件且该条件失败，服务器应返回 `412 Precondition Failed`（前提条件失败）。如果多个请求尝试同时修复一个资源而这种操作不受允许，服务器应返回 `409 Conflict`（冲突）。

`PATCH` 请求与 `PUT` 请求一样，是非空幂等的且等幂的。

## DELETE

`DELETE` 请求自然用于删除资源。`DELETE` 请求可以针对单个元素 URI 执行——在这种情况下，该资源被删除——也可以针对（可能经过过滤的）集合 URI 执行——在这种情况下所有匹配的资源都将被删除。允许删除多个资源通常不是理想的，因此通常不支持该功能。成功删除资源后，服务器应返回 `200 OK` 并在响应体中包含删除的资源，或返回 `204 No Content` 且响应体为空。如果由于某些原因服务器接受删除但无法执行（可能资源正在被使用），它可能会返回 `202 Accepted`。在这种情况下，响应体应包含一个资源 URI，客户端可以跟进并在稍后检查其状态。

`DELETE` 请求通常是非空幂等的，但它们的等幂性是一个有趣的话题。删除资源可能会导致在该资源上设置标记但保留其数据（软删除），也可能是硬删除。

# 使用 Spring MVC 配置 RESTFUL 服务

RESTful 服务的一大优势是它们在 Spring 基础设施中运行得良好。从技术上讲，你不需要做任何操作就可以创建 RESTful 服务。你只需要创建一个 `Controller`，添加一些 `@RequestMapping` 方法，即可开始运行。在实践中，你不太可能使用 `DispatcherServlet` 处理所有请求。因此，逻辑上创建创建 `DispatcherServlet`。在本节中，我们首先通过隔离 Web 和 REST 控制器来防止它们交叉，然后创建并引导另一个上下文。我们还查看了如何正确处理错误。最后，我们创建一个 REST 控制器并使用 `@RequestMapping` 进行发现，并为 XML 和 JSON 表示状态。你可以参考下载 WebService 项目。

## 使用类型注解隔离控制器

回顾第 12 章和第 13 章，`@Controller` 注解有两个用途。作为 `@Component`，它负责将你的控制器标记为可实例化和依赖注入的 Spring 管理 Bean。然而，在 Spring MVC 的文中，它还负责标记 Bean 以扫描 `@RequestMapping`。没有标记为 `@Controller` 的带有 `@RequestMapping` 的 Bean 无法响应。因此，你的 REST 控制器必须像 Web 控制器一样标记为 `@Controller`。

当然，这带来了一些挑战。你不希望 REST 控制器被 Web `DispatcherServlet` 的组件扫描到，也不希望 Web 控制器被 REST `DispatcherServlet` 的组件扫描到，显然的解决方案是在不同的包中使用你的 Web 和 REST 控制器，并在每个应用文中只扫描相应的包。这无疑是一种方法，并且在许多情况下可以满足任何需求。然而，解决此问题还有另一种方法：元注解。

请求映射（request mapping）很好地解决了控制器的分离问题。考虑到此，请查看 Web-Service 项目中的 `@com.wrox.config.annotation.WebController` 和 `@com.wrox.config.annotation.RestController` 注解。

```java
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Controller
public @interface WebController {
    String value() default "";
}

@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Controller
public @interface RestEndpoint {
    String value() default "";
}
```

这些注解在功能上几乎相同，但它们的语义含义有重要区别。然而，它们都表示目标 bean 是一个适用于请求映射的控制器。`@RestController` 标记用于传统 Web 请求的控制器，而 `@RestController` 则表示 RESTful Web 服务的端点。`value` 属性在此处的作用与其他类型化注解（stereotype annotations）中的作用相同：它提供了一种指定默认 bean 名称模式的方法。

## 创建独立的 Web 和 REST 应用上下文

单靠这些自定义注解对你并没有帮助。你可以将它们放置在控制器和端点上，但你在之前章节中使用的 `ServletContext` 类通过其对 `@Controller` 的组件扫描将它们全部包含进来。因此，你需要更新此配置以仅扫描 `@RestController` 注解。为了消除关于此上下文的任何歧，将此类重命名为 `ServletContext` 也是一个好主意。

```java
@Configuration
@EnableWebMvc
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(WebController.class)
)
public class ServletContextConfiguration extends WebMvcConfigurer {
    ...
}
```

该类中的代码与之前的章节没有变化。你所做的只是了此应用上下文的类型化注解类型。现在你需要创建一个新的应用上下文——一个查找 `@RestController` 并更适用于 RESTful Web 服务的上下文。列表 17-1 中的 `ServletConfiguration` 正是这样做的。

## 列表 17-1: RestServletContextConfiguration.java

```java
@Configuration
@EnableWebMvc
@ComponentScan(
    basePackages = "com.wrox.site"
)

return this.validator;

@Bean
public LocaleResolver localeResolver() {
    return new AcceptHeaderLocaleResolver();
}
```

该类在多个方面与 `WebServletContextConfiguration` 相似，但也有许多重要区别。它缺乏任何视图解析或多部分支持，因为这些功能根本不需要。它包含的消息转换器较少，仅关注 JSON 和 XML 的序列化和反序列化任务，而忽略了字符串、表单和字节数组。`configureContentNegotiation` 方法的方法略有不同，仅支持 `Accept` 请求头进行内容协商（即在 REST 标准之后）。你仍然需要 Spring 验证器。Bean 验证也存在于 RESTful Web 服务中，你可以配合 `@Valid` 使用 `@RequestBody` 实体参数。

`LocaleResolver`（本地区域解析器）也非常方便：语言不会影响请求和表示，但它可以根据客户端请求对错误消息进行本地化。在这种情况下，你使用 `AcceptHeaderLocaleResolver` 而不是 `SessionLocaleResolver`（通常情况下，REST 中没有会话），你不再需要 `LocaleChangeInterceptor` 让客户端在每个请求上指定所需的语言（如果有的话）。

由于有一个新的应用上下文需要读取，你需要妥善地引导它。这通常照常在 `Bootstrap` 类中完成。`DispatcherServlet` 的声明已重命名以减少歧义，并添加了一个新的 `DispatcherServlet`。

```java
AnnotationConfigWebApplicationApplicationContext webContext =
new AnnotationConfigWebApplicationApplicationContext();
```



webContext.register(`WebServletContextConfiguration.class`);

`DispatcherServlet.Dynamic` dispatcher = container.addServlet("springDispatcher");

```
AnnotationConfigWebApplicationApplicationContext restContext =
new AnnotationConfigWebApplicationApplicationContext();
restContext.register(`RestServletContextConfiguration.class`);
DispatcherServlet servlet = new DispatcherServlet(restContext);
serv.setDispatchOptionsRequest(true);
dispatch = container.addServlet("springRestDispatcher", servlet);
dispatcher.loadOnStartup(2);
dispatcher.addMapping("/services/Rest/*");
```

你会注意到新的 Servlets 具有多部分配置，这是预料之中的。你可以在 RESTful Web 服务中使用多部分请求，但这很少见，且该主题超出了本书的范围。代码还将 `DispatcherServlet` 的 `dispatchOptionsRequest` 属性设置为 true。通常 Dispatcher 会忽略 OPTIONS 请求并在这些情况下默认到 `HttpServlet` 的默认行为。为了支持发现，你必须告诉 `DispatcherServlet` 像处理其他请求一样将 OPTIONS 请求分发到你的 RESTful 端点。

## 在 RESTful Web 服务中处理错误情况

在 RESTful Web 服务中处理和响应错误请求以及错误情况的方式与你处理和响应成功请求一样。你的 RESTful API 消费者在出现问题时期望获得有意义的状态码和错误消息，他们显然不想收到标准的 HTML 格式页面。

Spring Framework 对优雅错误处理的支持在六种方法或 Web 的快速搜索中已经进化了很多，你很容易发现其中大部分仍然是过时且弃用的做法。本章不讨论这些处理错误的旧方法，而是关注 Spring 3.0 和 3.2 添加的功能。

## 更改 HTTP 响应码

你的 Web 服务需要处理的问题之一是对不存在的资源的请求。当然，当请求指向没有方法映射的 URL 时，Spring 可以返回 404 Not Found，但如果请求指向 `/services/Rest/account/10` 而标识符为 10 的账户不存在。根据 RESTful 标准，你也应该返回 404 Not Found。在早期阶段，你只需要使用 `HttpServletRequest` 来设置响应状态。从代码的角度来看，报告此类问题简单的方法是抛出异常。因此，创建一个异常。

```
@ResponseStatus(HttpStatus.NOT_FOUND)
public class ResourceNotFoundException extends RuntimeException
{
}
```

此异常唯一的特殊之处是 `org.springframework.framework.bind.annotation.ResponseStatus` 注解，它是 Spring 3.0 添加的。当放置在异常声明上时，它告诉 Spring Framework 返回 404 Found 状态码。如果没有它，从控制器方法抛出异常通常会导致 500 Internal Server Error。`@ResponseStatus` 还有其他用途，你将在本节后面看到它们。

## 声明异常处理器

另一个需要考虑的问题是 Bean 验证问题。在第 16 节的 Web 控制器中，你捕获了 `ConstraintViolationExceptions` 并违规项添加到模型中显示给用户。如果你的端点控制器中有一种简单的方法来实现类似的操作就太好了，而且确实有。`@org.springframework.framework.bind.annotation.ExceptionHandler` 注解同样在 Spring 3.0 中添加，它允许你将一个方法标记为异常处理器。它的语义与 `@RequestMapping` 几乎相同，允许你返回大多数相同的返回类型并接受相同的方法参数。

```
@ExceptionHandler({ ConstraintViolationException.class })
@ResponseStatus(HttpStatus.BAD_REQUEST)
public ErrorResponse handleBeanValidationError(ConstraintViolationException e)
{
}
```

这种模式的问题在于，它要求你在所有控制器上都具有必要的 `@ExceptionHandler` 方法。你可以从一个定义了这些方法的基控制器继承它，但这将阻止你在需要时扩展其他类。

## 使用控制器 Advice 模式

Spring 3.2 通过 `@org.springframework.web.bind.annotation.ControllerAdvice` 注解引入了控制器建议的概念。标记为 `@ControllerAdvice` 的类（它是一个 `@Component`）是 Spring 管理的用于建议控制器的 bean。此时，你可以将 `@ExceptionHandler`、`#initBinder` 和 `@ModelAttribute` 方法添加到控制器建议中，这些建议方法适用于所有控制器。由于是 `@Component`，`@ControllerAdvice` 类通常会在你的根应用上下文中实例化。你不希望这样做，因为你不想让此类建议同时应用于 Web 控制器和端点，因此你需要从根组件扫描中排除此注解。

```
@ComponentScan(
basePackages = "com.wrox.site",
excludeFilters = @ComponentScan.Filter(Controller.class, ControllerAdvice.class))
public class RootContextConfiguration
...
```

# 490 | 第 17 章 创建 RESTful 和 SOAP Web 服务

```
...
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters =
        @ComponentScan.Filter({RestEndpoint.class, RestEndpointAdvice.class})
)
public class RestServletContextConfiguration extends WebMvcConfigurerAdapter
```

现在，你可以创建一个控制器来处理这些错误了。列表 17-2 中的 `com.wrox.site.exception.RestExceptionHandler` 正是这样做的。它有两个内部类 `ErrorItem` 和 `ErrorResponse`，这有助于它实现向用户清晰地报告错误的目标。唯一的处理方法使用了 `@ExceptionHandler` 注解，它将约束违例转换为 `ErrorItem`，将它们放入 `ErrorResponse` 中，并返回封装在状态码为 400 Bad Request 的 `ResponseEntity` 中的 `ErrorResponse`。

注意 `@ExceptionHandler` 注解期望方法能够处理的异常。你可以在此注解中放置多个异常，以便用单个方法处理多个错误。由于 Spring 会调用最具体的匹配项，你也可以创建一个抛出任何 `Exception` 实例的通用捕获方法。Spring 会调用与抛出异常最匹配的方法，然后在最后才调用你的通用捕获方法。

# 列表 17-2: RestExceptionHandler.java

```
@RestEndpointAdvice
public class RestExceptionHandler {

    @ExceptionHandler(ConstraintViolationException.class)
    public ResponseEntity<ErrorResponse> handle(ConstraintViolationException e) {

        ErrorResponse errors = new ErrorResponse();

        for (ConstraintViolation violation : e.getConstraintViolations()) {

            ErrorItem error = new ErrorItem();

            error.setCode(violation.getMessageTemplate());

            error.setMessage(violation.getMessage());

            errors.add(error);

        }

        return new ResponseEntity<>(errors, HttpStatus.BAD_REQUEST);

    }

    public static class ErrorItem {

        private String code;

        private String message;

        @XmlAttribute
        public String getCode() { ... }

        public void set(String code) { ... }

        @XmlValue
        public String getMessage() { ... }

        public void setMessage(String message) { ... }

        @XmlRootElement(name = "errors")
        public static class ErrorResponse {

            private List<ErrorItem> errors = new ArrayList<>();

            @XmlElement(name = "error")
            public List<ErrorItem> getErrors() { ... }

            public void setErrors(List<ErrorItem> errors) { ... }

            public void addError(ErrorItem error) { ... }

        }
    }
}
```

你现在已经意识到这一点，但在你的 `ResourceNotFoundException` 上使用 `@ResponseStatus` 注解在 REST 上下文中这仅是唯一的帮助。对于在控制器内部抛出的异常，它是有帮助的，你可以保留该注解以使异常在 Web 上下文中保持很有用，但因为会导致返回容器的 HTML 错误页面，所以对于 REST 响应来说是不理想的。更好的方法是在 `RestExceptionHandler` 中添加第二个方法来处理这种情况以及 Spring 的 `NoSuchRequestHandlingMethodException`（当传入的请求匹配任何控制器方法时）。这些练习以及创建通用捕获方法的练习留由你自己完成。

## 将 RESTful 请求映射到控制器

要创建一个服务，首先需要一个业务层来暴露它。`AccountService` 接口继续使用本章目前为止的账户示例 URL。它指定了列表、保存和删除详情的方法。`DefaultAccountService` 实现的细节并不重要；它是一个标准的内存账户存储。你可以在 Web-Service 项目中查看它。

```
@Validated
public interface AccountService {

    @NotNull
    public List<Account> getAllAccounts();

    public Account getAccount(long id);

    public Account saveAccount (
        @NotNull(message = "validate.accountService.saveAccount.account")
        Account account
    );

    public void deleteAccount(long id);

}
```

该服务的实现在根应用上下文中，对 Web 和 REST `DispatcherServlet` 应用上下文都是的，如 `AccountController` 和 `AccountRestEndpoint` 顶部所示。`AccountController` 的细节也不重要。它是你习惯创建的标准 Web 控制器。

```
@WebController
public class AccountController
{
    @Inject AccountService accountService;
}
```

```
@RestEndpoint
public class AccountEndpoint
{
    @Inject AccountService accountService;
}
```

使用 `@RequestMapping`，你可以编写具有所有相同参数规则和类型的请求处理方法；尽管在现实中情况通常并非如此。从 RESTful 服务处理方法中返回 `ModelAndView`、String 视图名称、`Model`、`Map`、map 属性、`Callable` 或 `DeferredResult` 是没有意义的。通常你希望返回一个 `@ResponseBody` 实体对象或可以写回客户端的显式 `ResponseEntity<?>`，如果不需要向客户端返回内容，则返回 `ResponseEntity<Void>`。方法参数由 `@PathVariable` 和 `@RequestParam` 参数组成，对于 POST 和 PUT 请求，则是 `@RequestBody` 实体请求。对于 Web 控制器，请求项应该是缺少你不希望客户端看到的字段的表单或对象（通常至少是资源项）。响应项可以是你操作的业务对象（而不是表单对象），但你应该避免返回任何类型的、容易转换为 JSON 表示形式的 `Collection` 或 `Map`，因为它们无法转换为 XML 表示形式。

你将在 `AccountEndpoint` 中注意到的第一个方法是发现方法，即发现方法。有两个方法：一个用于集合，一个用于单个资源。

```
@RequestMapping(value = "account", method = RequestMethod.OPTIONS)
public ResponseEntity<Void> discover()
{
    HttpHeaders headers = new HttpHeaders();
    headers.add("Allow", "GET", "POST");
    return new ResponseEntity<>(null, headers, HttpStatus.NO_CONTENT);
}
```

```
@RequestMapping(value = "account/id", method = RequestMethod.OPTIONS)
public ResponseEntity<Void> discover(@PathVariable("id") long id)
{
    if (accountService.getAccount(id) == null)
        throw new ResourceNotFoundException();
    HttpHeaders headers = new HttpHeaders();
    headers.add("Allow", "GET", "PUT");
    return new ResponseEntity<>(null, headers, HttpStatus.NO_CONTENT);
}
```

正如 OPTIONS 响应所示，单个读取返回一个账户，如果请求的账户不存在则抛出 `ResourceNotFoundException`（导致 404 Not Found）。异常的 `@ResponseStatus`（或异常处理器）会被忽略，因为它具有优先级。同时，集合读取返回 `AccountList`（而不是 `List<Account>`）。这使得它能够用 XML 表示。这就是为什么在编写 RESTful Web 端点时必须特别注意。使用 JSON 表示请求和响应实体比使用 XML 得多，因此在支持两者时必须进行特殊考虑。某些供应商仅支持 JSON 请求和响应以避免这些复杂性，你可能决定采取这种路线。你也可以为 XML 和 JSON 响应创建单独的处理器；尽管这有时会让你的工作变得更加复杂。

```
@XmlRootElement(name = "accounts")
public static class AccountList {

    private List<Account> value;

    @XmlElement(name = "account")
    public List<Account> getValue() {
```



```java
return value;
}
```

```java
public void setValue(List<Account> accounts) {
    this.value = accounts;
}
```

以下代码段中的 `create` 和 `update` 方法（分别为 POST 和 PUT）用于添加新账户和保存现有账户的更改。注意，如果要更新的资源不存在，`update` 会像读取方法一样抛出 `ResourceNotFoundException`。当资源成功更新时，它实际上返回 204 No Content，而 `create` 则返回 201 Created、创建的实体，并在响应中包含指向创建资源 URL 的 `Location` 头部。使用 Spring 的 `org.springframework.web.support.UriComponentsBuilder` 来创建 URL，使其包含你的应用程序名称和上下文路径。

```java
@RequestMapping(value = "account", method = RequestMethod.POST)
public ResponseEntity<Account> create(@RequestBody AccountForm form) {
```

```java
Account account = new Account();
account.setName(form.getName());
account.setBillingAddress(form.getBillingAddress());
account.setShippingAddress(form.getShippingAddress());
account.setPhoneNumber(form.getPhoneNumber());
account = this.accountService.saveAccount(account);
```

```java
String uri = ServletUriComponentsBuilder.fromServletMapping()
    .path("/account/{id}").buildAndExpand(account.getId()).toString();
HttpHeaders headers = new HttpHeaders();
headers.add("Location", uri);
```

```java
return new ResponseEntity<Account>(account, headers, HttpStatus.CREATED);
```

```java
@RequestMapping(value = "account/{id}", method = RequestMethod.PUT)
@ResponseStatus(HttpStatus.NO_CONTENT)
public void update(@PathVariable("id") long id, @RequestBody AccountForm form) {
```

```java
Account account = this.accountService.getAccount(id);
if (account == null)
    throw new ResourceNotFoundException();
account.setName(form.getName());
account.setBillingAddress(form.getBillingAddress());
account.setShippingAddress(form.getShippingAddress());
account.setPhoneNumber(form.getPhoneNumber());
this.accountService.saveAccount(account);
```

虽然简单，但 `AccountEndpoint` 中关注的方法是 `delete`。像 `read` 一样，如果资源不存在，`update` 也会抛出 `ResourceNotFoundException`。如果资源存在，它将删除资源并返回 204 No Content。

```java
@RequestMapping(value = "account/{id}", method = RequestMethod.DELETE)
@ResponseStatus(HttpStatus.NO_CONTENT)
```

```java
public void delete(@PathVariable("id") long id) {
    if (this.accountService.getAccount(id) == null)
        throw new ResourceNotFoundException();
    this.accountService.deleteAccount(id);
}
```

## 通过索引端点改进发现

`AccountRestEndpoint` 中的发现方法帮助客户端了解账户资源以及它们可以对其进行的操作，但这并没有完成 RESTful 发现机制。通常情况下，你会创建一个索引端点来列出服务器可用的资源。从简单的意义上说，这只是代码中一个静态链接列表，使用你应用程序的域名和上下文路径创建。列表 17-3 中的 `IndexRestEndpoint` 正是这样这一点。它使用 HAL 标准返回资源链接，由于该标准具有非常不同的 XML 和 JSON 表示形式，它使用了一些辅助 POJO 和两个不同的发现方法来返回适当的响应。`@RequestMapping` 的 `produces` 属性有助于根据请求的 `accept` 头部识别应该调用哪种方法。

### 列表 17-3：IndexRestEndpoint.java

```java
@RestController
public class IndexRestEndpoint {

    @RequestMapping(value = {"", "*/"}, method = RequestMethod.GET,
        produces = {"application/json", "text/json"})
    @ResponseStatus(HttpStatus.OK)
    public Map<String, Object> discoverJson() {

        ServletUriComponentsBuilder builder = 
            ServletUriComponentsBuilder.fromCurrentServletMapping();
        Map<String, Object> links = new Hashtable<>(2);
        links.put("self", new Json(builder.path("*").build().toString()));
        links.put("account",
            new Json(builder.path("/account").build().toString()));
        Map<String, Object> response = new Hashtable<>(1);
        response.put("links", links);
        return response;
    }

    @RequestMapping(value = {"", "*/"}, method = RequestMethod.GET,
        produces = {"application/xml", "text/xml"})
    @ResponseStatus(HttpStatus.OK)
    public Resource discoverXml() {

        ServletUriComponentsBuilder builder = 
            ServletUriComponentsBuilder.fromCurrentServletMapping();
        Resource resource = new Resource();
        resource.addLink(new Link("self", builder.path("*").build().toString()));
```

* 注意

### 列表 17-3（续）

```java
resource.addLink(new Link("account",
builder.path("/account").build().toString()));
return resource;
}

public static class JsonLink {

    private String href;
    public JsonLink(String href) { ... }
    @XmlAttribute
    public String getHref() { ... }
    public void setHref(String href) { ... }
}

public static class JsonLink extends JsonLink {

    private String rel;
    public JsonLink(String rel, String href) { ... }
    @XmlElement
    public String getRel() { ... }
    public void setRel(String rel) { ... }
}

@RootElement
public static class Resource {

    private List<Link> links = new ArrayList<>();
    @XmlElement(name = "link")
    public List<Link> getLinks() { return links; }
    public void setLinks(List<Link> links) { this.links = links; }
    public void addLink(Link link) { this.links.add(link); }
}
```

## 测试你的服务端点

但是如何功能测试服务呢？你需要一个能够轻松创建和操作 HTTP 请求并查看响应的工具。命令行工具 `curl` 是一个竞争者，但它每个请求都需要大量的开销和手动输入，而且比 HTTP 基础认证复杂的认证非常困难。如果工具可以记住认证和预设头部值并格式化 JSON 和响应就好了。Fiddler 有许多其他用途，但用于此目的可能有些繁琐。Chrome 和 Firefox 有几个 REST 客户端浏览器插件非常适合测试 Web 服务。在本节中我们使用了 RESTClient 插件，但有很多工具可以选择，你可以选择适合自己的一个。

### 选择测试工具

有很多工具可用，你选择哪种取决于你执行的测试类型。除了质量保证团队使用的其他工具外，JUnit 和 TestNG 也能提供帮助。另一种常见的测试需求是负载测试，它有助于确定系统的性能特征、瓶颈和崩溃点。有很多工具有可用，包括免费工具 JMeter 和 Grinder，以及企业级工具 NeoLoad 和 LoadRunner。

### 向你的服务发送请求

1. 点击地址和搜索栏旁边的带圆圈的红色正方形按钮（此处所示）来打开 RESTClient。
2. 点击 `Headers` 菜单并点击 `Custom Header`。
3. 在 `Name` 中输入 `Content-Type`，在 `Value` 中输入 `application/json`，勾选收藏并点击 `OK`。
4. 重复步骤 3，处理 `Content-Type` 和 `application/xml`、`Accept` 和 `application/json`、`Accept` 和 `application/xml`。这保存了可以随时获取的快速访问头部。完成后，确保检查了 RESTClient 中的 Headers 栏。只需点击 `Remove All` 按钮。
5. 从你的 IDE 中编译并启动 Web 服务应用程序。
6. 在 RESTClient 的 Headers 栏中添加 `application/json` Content-Type 和 Accept 请求头，从方法中选择 GET，在 URL 中输入 `http://localhost:8080/financials/services/Rest/` 并点击 Send。响应体将是 RestIndexEndpoint 控制器返回的链接列表。
7. 尝试将方法更改为 OPTIONS并将 URL 更改为 `http://localhost:8080/financials/services/Rest/account`。AccountRestController 将响应 204 No Content 以及一个 Allow 请求头，列出你允许在集合资源上执行的所有操作。
8. 将方法更改为 GET，在 URL 中输入 `http://localhost:8080/financials/services/Rest/` 并点击 Send。响应体应该包含一个空列表。你的 Web URL `http://localhost:8080/financials/services/Rest/account/` 和你的服务将响应 404 Not Found。这意味着你还没有任何账户。
9. 要修复这个问题，将 URL 改回 `http://localhost:8080/financials/Rest/account`，将方法更改为 POST，并在 Body 字段输入图 17-1 中的值。发送此请求后，服务将响应 400 Bad Request。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_533_0.png)

图 17-1

10. 检查响应体，它看起来应该图 17-1。这意味着 bean 校验抛出了 `ConstraintViolationException`，并且你的 `RestExceptionHandler` 将异常转换为了 JSON 响应。
11. 现在用 XML 重复此过程：将 Content-Type 和 Accept 请求头更改为 `application/xml`，并将 Body 字段更改为图 17-2 所示的值。你将获得响应，只是格式化后的 XML 而不是 JSON。

图 17-3 显示了一个成功的 POST 操作，带有完整的 JSON 请求体，以成功创建一个账户。执行此 POST 并查看响应头，你将看到刚创建的资源的 Location URL。

# 测试你的 Web 服务端点

![](img/9c2d45f6d547f72cb870b3a991f62ef6_534_0.png)

图 17-2

![](img/9c2d45f6d547f72cb870b3a991f62ef6_534_1.png)

图 17-3

13. 复制此 URL 并将其粘贴到 URL 字段中，清除请求体并将方法更改为 GET。响应将是你创建的账户。
14. 同样使用 XML 创建几个账户，然后再次尝试集合 GET。你不应该看到空列表，而是看到你到为止创建的所有账户。测试意味着你拥有了一个功能完备、能够响应 JSON 和 XML 请求的 RESTful Web 服务。

# 使用 SPRING WEB 用于 SOAP

你将来很有可能需要为客户提供 SOAP Web 服务，特别是当你从事大型企业级应用开发时。SOAP 是一个复杂的课题，你无法从另一个章节完全理解它，更不用说单单节了。在本节中，你将简要介绍一个可以帮助你轻松快速创建简单 SOAP 服务的工具：Spring Web Services。如果你不彻底理解 SOAP，就不可能考虑本节中提供的方案。

如果你对这个主题感兴趣并想学习更多，请查看 Spring Web Services 项目的参考文档：http://springframework.org/spring-ws/sites/2.0/reference/index.html。Spring Web Services 是一个与 Spring Framework 相关并依赖于它的独立项目。它旨在与基于 Spring 的代码（如 Web 控制器和 RESTful 端点）并肩工作。

使用 Spring Web Services，你需要一个在本章开头未提到的 Maven 依赖：

```xml
<dependency>
  <group>org.springframework.ws</group>
  <artifactId>spring-ws-core</artifactId>
  <version>2.1.4.RELEASE</version>
  <scope>compile</scope>
  <exclusions>
    <exclusion>
      <group>javax.xml.stream</group>
      <artifactId>stax-api</artifactId>
    </exclusion>
  </exclusions>
</dependency>
```



排除掉了瞬时的 Java Streaming API for XML (`StAX`) 依赖，因为它是 Java 6 及更高版本的标准版 API 的一部分。

为了跟本节的工作，请从 wrox.com 代码网站下载可 `Customer-Support-v14` 项目。它已经包含了 `RestServletContextConfiguration`、`RestExceptionHandler` 和 `IndexRequestHandler` —— 这些都与你在本章中目前看到的相似。它还包含一个 `TicketRestController`，用于通过 RESTful JSON 或 XML API 管理工单，你可以根据需要对其进行检查和测试。在本节中，你将专注于创建一个通过 SOAP Web 服务管理工单的端点。

# 使用 Spring Web Services 用于 SOAP

> 注意：你可能会发现 `TicketRestEndpoint` 没有安全机制来防止未经授权的访问。同样地，SOAP 端点也没有安全机制。应用程序使用的简单表单认证不适用于 Web 服务。在本书的第四部分中，你将学习如何使用 OAuth 安全 Web 服务。在此之前，你的 Web 服务将处于未保护状态。

# 你的契优先 XSD 和 WSDL

Spring Web Services 严格执行契优先开发。在执行任何操作之前，你必须定义 XML 契约。好消息有一些工具可以帮助你完成这一点。考虑一下你希望 XML 格式的 Ticket 像什么样。

```xml
<ticket xmlns="http://example.com/xmlns/support">
  <id>12</id>
  <customerName>Doe</customerName>
  <dateCreated>2014-01-17T17:12:00Z</dateCreated>
  <subject>Foo</subject>
  <body>
  </body>
  <attachment>
    <name>spacer.gif</name>
    <mimeContentType>image/gif</mimeContentType>
    <contents>R0ll0KGAAAAAAABQEAKAEALAAAAAAAAAAAAAAAAIACTEAOW==</contents>
  </attachment>
</ticket>
```

你还知道，为了创建新工单，你需要一个 `<ticketForm>` 元素。

```xml
<ticketForm xmlns="http://example.com/xmlns/support">
  <subject>Foo</subject>
  <body>
  </body>
  <attachment>
    <name>spacer.png</name>
    <mimeContentType>image/png</mimeContentType>
    <contents>iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAC1wCACAAD0lBMVEUAAACnej3AAAAP7897AAAABJRU5ErkJggg==</contents>
  </attachment>
</ticketForm>
```

你需要读取单个工单，因此你需要一个 `<deleteRequest>` 元素和一个相同的 `<deleteTicket>` 元素。最后，你需要一种选择所有工单的方法，一个空的 `<ticketsRequest>` 元素即可解决问题。

```xml
<ticketRequest xmlns="http://example.com/xmlns/support">
  <id>12</id>
</ticketRequest>
```

根据这些示例，你的 IDE 可以帮助生成 XSD 架构代码。在 IntelliJ IDEA 中，你可以按照以下步骤创建每个元素遵循这些要求的临时 XML 文件：

1. 在 XML 内容区域右键点击，从 XML 文件生成 XSD Schema。
2. 在出现的对话框中，确保 `Design Type` 字段设置为 `local elements/ global complex types`，然后点击 OK。
3. 生成的 XSD 架构与你要求的非常接近，只需要进行细微更改来指示预期的元素类型、指定类型出现的频率等。XSD 文件需要合并到一个 XSD 文件中，用于你 Web 服务上的所有操作。

列表 17-4 列出了生成的 XSD 架构文件 `/WEB-INF/xsd/support/support.xsd`。

## 列表 17-4: support.xsd

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema attributeFormDefault="qualified" elementFormDefault="qualified"
  targetNamespace="http://example.com/xmlns/support"
  xmlns:xs="http://www.w3.org/2001/XMLSchema"
  xmlns:support="http://example.com/xmlns/support">
  <xs:element name="ticketRequest" type="support:ticketRequestType" />
  <xs:element name="createTicket" type="support:selectTicketType" />
  <xs:element name="deleteTicket" type="support:createTicketType" />
  <xs:element name="ticket" type="support:selectTicketType" />
  <xs:element name="tickets" type="support:ticketsType" />
  <xs:complexType name="ticketType">
    <xs:sequence>
      <sequence>
        <xs:sequence>
          <xs:element type="xs:long" name="id" minOccurs="0" />
          <xs:element type="xs:string" name="customerName" minOccurs="0" />
          <xs:element type="xs:dateTime" name="dateCreated" minOccurs="0" />
          <xs:element type="xs:string" name="subject" />
          <xs:element type="xs:string" name="body" />
          <xs:element type="support:attachmentType" name="attachment" minOccurs="0" maxOccurs="unbounded" />
        </xs:sequence>
      </sequence>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ticketRequestType">
    <xs:sequence>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="selectTicketType">
    <xs:sequence>
      <sequence>
        <xs:element type="xs:long" name="id" />
      </sequence>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="createTicketType">
    <xs:sequence>
      <sequence>
        <xs:element type="support:ticketType" name="ticket" />
      </sequence>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ticketsType">
    <xs:sequence>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="attachmentType">
    <xs:sequence>
      <xs:element type="string" name="name"/>
      <xs:element type="string" name="mimeContentType"/>
      <xs:element type="base64Binary" name="contents"/>
    </xs:sequence>
  </xs:complexType>
</xs:schema>
```

在这种情况下，你只需要 XSD 即可：Spring Web Services 会考虑此契约并自动为你创建 WSDL。为了实现此 WSDL 的创建，你必须先配置 Spring Web Services。

## 添加 SOAP Dispatcher Servlet 配置

与 Spring Framework 不同，Spring Web Services 不支持基于 Java 的程序化配置。然而，你需要为你的 SOAP 应用上下文进行组件扫描，因此简单的方法是创建一个混合配置。`SoapServletContext` 会扫描 `@org.springframework.ws.server.endpoint.annotation.Endpoint` 组件并导入 `SoapServletContext` XML 配置。

```java
@Configuration
@ComponentScan(
  basePackages = "com.wrox.site",
  useDefaultFilters = false,
  includeFilters = @ComponentScan.Filter(Endpoint.class)
)
@ImportResource("classpath:wrox/config/soapServletContext.xml")
public class SoapServletContextConfiguration {
  @Bean
  public WebServiceMessageFactory messageFactory() {
    SaajSoapMessageFactory factory = new SaajSoapMessageFactory();
    factory.setSoapVersion(SOAP_12);
    return factory;
  }
}
```

显式的 `messageFactory`（该名称很重要）覆盖了默认工厂，使得支持的 SOAP 版本变为 1.2 而不是默认的 1.1。关于协议绑定、扩展性和 XML 格式的某些增强超出了本书的范围。`soapServletContext.xml` 文件告诉 Spring Web Services 通过注解配置端点，并使用你之前创建的 XSD 生成 WSDL。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
      xmlns:wss="http://www.springframework.org/schema/web-services"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:schemaLocation="http://www.springframework.org/schema/beans
          http://www.springframework.org/schema/beans/spring-beans-4.0.xsd
          http://www.springframework.org/schema/web-services
          http://www.springframework.org/schema/web-services/web-services-2.0.xsd">
  <wss:annotation-driven marshaller="jaxb2Marshaller"
    unmarshaller="jaxb2Marshaller" />
  <wss:dynamic-wsdl id="support" portTypeName="Support"
    location="/services/Soap/" createSoapAllBinding="false"
    targetNamespace="http://example.com/xmlns/support">
  </wss:dynamic-wsdl>
</beans>
```

由于 `@Endpoint` 也是一个 `@Component`，你需要更改 `RootContextConfiguration` 以确保 SOAP servlet 实例化并管理端点类。

```java
@ComponentScan(
    basePackages="com.wrox.site",
    excludeFilters = @ComponentScan.Filter({
        Controller.class, ControllerAdvice.class, Endpoint.class
    })
)
public class RootContextConfiguration
...
```

你需要引导启动使用 `SoapServletConfiguration` 的 `org.springframework.transport.http.MessageDispatcherServlet` servlet，它处理 SOAP 请求。以下代码创建了此 servlet，设置了它的应用上下文，并指示它将 WSDL 位置转换为请求。

```java
AnnotationConfigWebApplicationContext soapContext =
    new AnnotationConfigWebApplicationContext();
soapContext.register(SoapServletConfiguration.class);
MessageDispatcherServlet soapServlet =
    new MessageDispatcherServlet(soapContext);
soapServlet.setTransformWsdlLocations(true);
dispatcher.addServlet("SpringSoapDispatcher", soapServlet);
dispatcher.setLoadOnStartup(1);
```



`dispatcher.addMapping("/services/**");`

配置好 Spring Web Services 后，现在可以创建 SOAP 端点了。

## 创建 SOAP 端点

端点是 Spring Web Service 支持的核心组件。与直接绑定 HTTP 请求和响应的控制器不同，Spring Web Service SOAP 端点可以通过 HTTP、XMPP、SMTP、JMS 提供服务。就像 `@Controller` 标记其 `@RequestMapping` 方法应该被扫描并映射到请求一样，`@Endpoint` 标记端点，其 `@org.springframework.ws.server.endpoint.annotation.PayloadRoot` 方法、`@org.springframework.ws.soap.endpoint.annotation.SoapAction` 方法以及 `@org.springframework.ws.soap.addressing.server` 是任何协议上传入 SOAP 请求的处理器。Endpoint 的参数对应于元素，而返回类型指示响应内容。

至于方法，根据你倾向于访问请求中 XML 内容的方式，对于想要接受的内容类型有很大的灵活性。例如，类型为 `SoapMessage`、`SoapBody`、`SoapEnvelope` 或 `SoapHeader`（都在 `org.springframework.ws.soap` 包中）的方法会从 SOAP 请求解析对应的内容。类似于 `@RequestBody`，如果方法标记了 `@org.springframework.ws.server.annotation.RequestPayload`，Spring 将请求转换为指定的类型。支持的负载类型有：

- `javax.xml.transform.Source` 或其子类
- `org.w3c.Element`
- `org.dom4j.Element`（dom4j 在类路径中）
- `org.jdom.Element`（jdom 在类路径中）
- `org.dom.Element`（XOM 在类路径中）
- `javax.xml.stream.XMLReader` 或 `javax.xml.stream.XMLEventReader`（Java SE 6 或更高版本中，如果 StAX 在类路径中）
- Java 6 或更高版本中任何标记了 `@javax.bind.annotation.XmlRootElement` 的类型（如果 JAXB 在类路径中）
- 如果使用了 `<wss:annotation-driven>`，则由 Spring OXM Unmarshaller 支持的任何类型都配置了 `unmarshaller` 属性。

同样，标记了 `@org.springframework.ws.server.endpoint.annotation.ResponsePayload` 的方法可以返回类型或其子接口：`org.w3c.Element`、`org.dom4j.Element`、`org.jdom.Element`、`org.dom.Element`、任何标记了 `@XmlRootElement` 的类型，以及如果使用了 `<wss:annotation-driven>`，任何由 Spring OXM Marshaller 支持的类型；返回返回响应内容（空的 SOAP 包）的方法。

由于这些方法参数和返回类型，你可以复用 17-5 中 `TicketSoapEndpoint` 创建的若干参数和返回类型。如所示，该端点与 REST 端点有许多相似之处，但也有一些区别。该端点使用 `@PayloadRoot` 注解通过负载根元素匹配端点动作，但你也可以通过 `@SoapAction` 注解使用 SOAP 头或通过 `@Action` 注解使用 Web Services 标准。

## 17-5: TicketSoapEndpoint.java

```java
@Endpoint
public class TicketSoapEndpoint {

    private static final String NAMESPACE = "http://example.com/xmlns/support";

    @Inject
    private TicketService ticketService;

    @PayloadRoot(namespace = NAMESPACE, localPart = "ticketRequest")
    @ResponsePayload
    public TicketWebServiceList read() {
        TicketWebServiceList list = new TicketWebServiceList();
        list.setValue(this.ticketService.getAllTickets());
        return list;
    }

    @PayloadRoot(namespace = NAMESPACE, localPart = "ticketRequest")
    @NamespacePayload(uri = NAMESPACE, prefix = "*")
    @ResponsePayload
    public Ticket read(@XPath("*/s:ticketRequest/id") long id) {
        return this.ticketService.getTicket(id);
    }

    @PayloadRoot(namespace = NAMESPACE, localPart = "createTicket")
    @ResponsePayload
    public Ticket create(@RequestPayload CreateTicket form) {
        Ticket ticket = new Ticket();
        ticket.setCustomerName("WebServiceAnonymous");
        ticket.setSubject(form.getSubject());
        ticket.setBody(form.getBody());
        if (form.getAttachments() != null) {
            ticket.setAttachments(form.getAttachments());
        }
        this.ticketService.save(ticket);
        return ticket;
    }

    @PayloadRoot(namespace = NAMESPACE, localPart = "deleteTicket")
    @NamespacePayload(uri = NAMESPACE, prefix = "*")
    public void delete(@PathParam("*/s:deleteTicket/id") long id) {
        this.ticketService.deleteTicket(id);
    }

    @XmlRootElement(namespace = NAMESPACE, name = "createTicket")
    public static class CreateTicket {
        private String subject;
        private String body;
        private List<Attachment> attachments;

        public String getSubject() { ... }
        public void setSubject(String subject) { ... }
        public String getBody() { ... }
        public void setBody(String body) { ... }

        @XmlElement(name = "attachment")
        public List<Attachment> getAttachments() { ... }
        public void setAttachments(List<Attachment> attachments) { ... }
    }
}
```

编译并启动 Customer 应用程序进行测试。您可以在任何普通的浏览器窗口中访问 `http://localhost:8080/support/services/Soap/support.wsdl` 来查看带有图形用户界面的自动生成的 WSDL，然后使用 RESTClient-browser-plugin 尝试 RESTful Web 服务。当值为 `application/soap-xml` 时，您需要使用 `Accept` 和 `Content-Type` 请求头。由于 SOAP 封包请求的创建和处理非常复杂，因此您可以使用以下四个请求来测试您的服务。无论操作是什么，都应该使用 POST 向 `http://localhost:8080/support/services/Soap/` 发送请求。

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<ticketRequest xmlns:support="http://example.com/xmlns/support">
<id>1</id>
</support:ticketRequest>
</Body>
</Envelope>
```

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<ticketRequest xmlns:support="http://example.com/xmlns/support">
<id>1</id>
</support:ticketRequest>
</Body>
</Envelope>
```

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<deleteTicket xmlns:support="http://example.com/xmlns/support">
<id>1</id>
</support:deleteTicket>
</Body>
</Envelope>
```

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<createTicket xmlns:support="http://example.com/xmlns/support">
<subject>Foo</subject>
<body>Bar</body>
</Body>
</Envelope>
```

```xml
<attachment>
<name>spacer.gif</name>
<mimeContentType>image/gif</mimeContentType>
<contents>R0lG0D1HAQABAAAAAACH5BAEKAEALAAAAABAEAAIACTAEOW==</contents>
</attachment>
<support:createTicket>
</soap:Body>
</soap:Envelope>
```

### 总结

在本章中，您已经涵盖了大量内容。首先，您接触了 Web 服务的概念，并学习了 SOAP——现代 Web 服务的开端。您探索了 RESTful Web 服务标准，并学习了如何为客户端提供 RESTful Web 服务。您研究了如何使用标准的 Spring MVC 控制器创建 RESTful Web 服务，并创建了自定义原型注解（stereotype annotations）来区分 Web 控制器和 RESTful Web 服务端点。您还简要地学习了 Spring Web Services 项目，以及如何使用它为您的应用程序创建 SOAP Web 服务端点。

在第二部分的最后一章中，您的应用程序将探索 Spring Framework 消息和 Web 应用程序集群，这可以让您的应用程序更具灵活性、可扩展性和可靠性。

# 18 使用消息和集群提高灵活性和可靠性

本章内容

- 决定何时使用消息和集群
- 如何为您的应用程序添加消息支持
- 如何在集群中分发消息
- 使用高级消息队列协议（AMQP）分发事件

本章 WROX.COM 代码下载

您可以在 `http://www.wrox.com/go/javaforwebapps` 的“Download Code”标签页找到本章的 wrox.com 代码下载。本章代码分为以下示例：

- 发布-订阅项目 (Publish-Subscribe Project)
- WebSocket-消息项目 (WebSocket-Messaging Project)
- AMQP-消息项目 (AMQP-Messaging Project)

本章的新 Maven 依赖

本章没有在后续章节中使用的新 Maven 依赖。您将继续使用之前所有章节中引入的 Maven 依赖。您仅在本章的最后一个节中使用以下依赖，而不在任何其他章节中使用。

```xml
<dependency>
  <groupId>com.rabbitmq</groupId>
  <artifactId>amqp-client</artifactId>
  <version>3.2.3</version>
  <scope>compile</scope>
</dependency>
```

# 识别您何时需要消息和集群

消息和集群是企业级应用的两个关键特性。有趣的是，消息和集群能力可以独立存在并独立增强您的应用程序，但它们也可以协同工作，以提高应用程序的灵活性、可靠性、可扩展性和可用性。在本章中，您将学习每个主题单独能提供的价值，以及如何在 Java Web 环境中结合 Spring Framework 使用它们。

# 什么是应用程序消息？

“消息”（messaging）一词有很多含义。当您使用电子邮件和短信与朋友及同事通信时，您就在参与消息传递。

[注：提供的 OCR 文本从此处开始似乎严重的损坏/乱码，无法根据提供的输入进行完全重构。]

# 使用 Spring Framework 的应用程序事件和监听器

无需任何特殊配置，Spring Framework 就会在发布/订阅（pub/sub）环境中自动充当消息代理。要发布消息，你需要调用 `org.springframework.context.ApplicationPublisher` 实例的 `publishEvent` 方法，并传递 `org.springframework.context.ApplicationEvent` 实例。你可以通过依赖注入或实现 `org.springframework.context.ApplicationPublisherAware` 在 Spring 管理的 Bean 中获取 `ApplicationEventPublisher`。有了 `ApplicationPublisher` 实例，你可以根据需要发布任意数量的事件。订阅事件同样简单。要订阅某个事件，Spring Bean 只需要实现 `org.springframework.context.ApplicationListener<FooEvent>` 即可接收 `FooEvent` 消息。你也可以创建并订阅事件层级结构。例如，考虑以下事件定义：

```java
public class TopEvent extends ApplicationEvent { }
public class MiddleEvent extends TopEvent { }
public class CenterEvent extends TopEvent { }
public class BottomEvent extends MiddleEvent { }
```

基于此，实现以下接口的 Bean 将：

- `ApplicationListener<ApplicationEvent>` 订阅所有事件
- `ApplicationListener<TopEvent>` 订阅 TopEvent、MiddleEvent、CenterEvent 和 BottomEvent
- `ApplicationListener<MiddleEvent>` 订阅 MiddleEvent 和 BottomEvent
- `ApplicationListener<CenterEvent>` 仅订阅 CenterEvent
- `ApplicationListener<BottomEvent>` 仅订阅 BottomEvent

由于 Java 不允许你多次实现同一个接口（即使带有不同的类型参数），因此你无法在不订阅其共同祖类的情况下订阅不同的事件。这并不总是如人意的，特别是当唯一的共同祖类是 `ApplicationEvent` 时——Spring 自带了数十个内置事件，这些事件在任何时候由于各种原因被发布。然而，你可以通过巧妙使用 `@Bean` 和匿名内部类来解决这个问题：

```java
@Service
public class FooService {
    public void doSomething() { }
}
```

```java
@Bean
public ApplicationListener<BarEvent> fooService$barEventListener() {
```



```java
return new ApplicationListener<BarEvent>() {

    @Override
    public void onApplicationEvent(BarEvent e) {
        FooService.this.doSomething();
    }
};
```

```java
@Bean
public ApplicationEventListener<BazEvent> fooService$bazEventListener() {
    return new ApplicationListener<BazEvent>() {
        @Override
        public void onApplicationEvent(BazEvent e) {
            FooService.this.doSomething();
        }
    };
}
```

当然，尽管 Spring Framework 内置的这种发布/订阅支持非常强大，但它是局部的。它只在 Spring 容器内部或更重要的是，在单个 JVM 内部工作。在许多情况下，你需要发布/订阅机制跨集群中的多个服务器工作，这引出了一个问题：“究竟什么是集群？”

## 集群

集群有许多含义。严格从定义上来说，集群是某些事物的组合。“cluster”一词可以指代地质、生物、化学、天文学、食物、技术以及许多其他领域。房屋可以成群建造，城市可以成群形成，人也可以聚集在一起。

在计算机术语中，应用程序集群是指两个或多个为了相同目标共同工作的应用程序组，以便你可以将其作为一个单一系统来使用。这涉及到两个或多个物理或虚拟服务器运行相同的服务并执行相同的任务，并在它们之间平均分负载。它还可能涉及以相同方式在物理或虚拟机器上运行的两个或多个相同的服务。例如，两个或多个 `Apache Tomcat` 实例无论是运行在同一台服务器上、不同的服务器上，还是某种组合，都可以形成集群。重要的是这些服务是否存活，而是它们是否被配置为在同一任务上协作工作。

## 理解可分发性 Java EE 应用程序

严格来说，只要在部署文件以及封装在 `/WEB-INF/lib` 目录下的 JAR 文件的 `/META-INF/web-fragment.xml` 描述符存在 `<distributable/>` 标签，Java EE 应用程序就被认为是可分发的。如果 JAR 文件不包含 `web-fragment.xml` 文件，则它不被视为 web fragment 且不计入。如果应用程序中存在一个缺少 `<distributable/>` 的 `web-fragment.xml` 的单包，或者部署描述符缺少 `<distributable/>`，则该应用程序被认为是不可分发的。

如果不准确了解什么是可分发性 Java EE 应用程序，这种区别没有任何意义。`<distributable>` 元素表示该程序编写用于部署到运行在相同主机或不同主机上的 JVM。在几乎所有情况下，这意味着所有编写的属性都是可序列化的。容器允许在可分发应用程序中支持非可序列化的会话属性，但并非强制要求，且大多数简单的 Servlet 容器并不支持。如果应用程序向会话添加了不可序列化的属性，Tomcat 会抛出 `IllegalArgumentException`。使用可序列化会话属性的作用是它允许 `HttpSession` 在集群中的服务器之间共享，这也许是使用 `<distributable>` 最重要的原因。如果集群中配置了两个或多个服务器，它们仅对可分发性应用程序共享 `HttpSession` 数据。

## 理解 HTTP Session、会话保持和序列化

你为什么要在集群中的服务器之间共享会话数据？答案非常简单，归结为使用集群的原因：可扩展性和可用性。单个服务器无法处理无限增长的用户。当服务器故障时，你的用户会被重定向到其他服务器。由于大多数应用程序使用会话与用户交互，因此数据在集群中是可以共享的关键。集群有两个作用：

- 如果服务器故障，用户可以被发送到不同的服务器，该服务器将拥有与故障服务器相同的所有会话数据。
- 在理想世界中，连续的用户请求可以独立于接收请求的服务器进行处理，因此用户的请求理论上每次都可以在不同的服务器上处理，而不会丢失会话信息。

为了让这些场景都能正常工作，你必须使你的属性变为可序列化。因为 Java 对象无法超出单个 Java 虚拟机的限制，因此 `HttpSession` 在发送到集群中的其他服务器之前（无论是通过共享内存、文件系统还是网络连接）必须经过序列化。这种模式提出了两个有趣的挑战，且两者都有解决方案。

首先，有时会话属性无法 100% 序列化。这对于升级和重构的遗留应用程序尤为如此。例如，会话属性可能会（无论多么糟糕）持有一个数据库连接或打开的文件句柄。这些属性显然无法被序列化并在集群中共享——或者可以吗？`javax.servlet.http.HttpSessionActivationListener` 指定了一种类型的属性，该属性知道自己何时被序列化并发送到集群中的其他服务器，或者刚刚被反序列化。任何实现此接口的会话在即将发送到其他服务器时（通过 `sessionWillPassivate` 方法）以及刚从另一个服务器接收数据时（通过 `sessionDidActivate` 方法）都会通知。在上述示例中，属性可以在 `sessionDidActivate` 中重新打开被标记为 `transient` 的数据库连接。

集群会话的一个常见问题是性能。为了实现完全的服务独立，每当你更新会话属性以及每次处理请求时，服务器都必须序列化并共享 `HttpSession`（以保持 `lastAccessTime` 属性保持更新）。在某些情况下，这可能会引发真正的性能问题。（尽管它与只使用单台服务器相比有一个优势）。

## 识别何时你需要消息传递和集群

由于其他原因，每当你部署分布式应用程序时，会话粘性的概念是一个重要的考虑因素。虽然会话粘性在不同的容器和负载均衡器之间有所不同，但其概念是相同的：在单个会话中，所有的会话请求都在同一个 JVM 中处理。会话只会定期跨集群进行序列化和共享，具体频率取决于部署团队设定的性能标准。

共享会话往往会引起问题：想象你向购物车中添加了几个物品，但在下一次请求时，这些物品不再出现在你的购物车中了。有了粘性，除非你的会话结束或服务器故障，否则你始终会被发送到同一台服务器，从而缓解了状态不一致的问题。但这并非没有缺点。服务器故障是不可预测的，而且当故障发生时，预测的结果很少处于一致状态。如果可能，在每次更新会话时，跨集群维护会话状态总是最好的。

## 配置你的容器以支持集群应用程序

不同的 Java EE 应用服务器和 Servlet 容器之间，配置应用程序集群的过程差异很大。例如，如果你使用 GlassFish 域管理服务器（DAS），你可以使用 Web 应用程序自动创建和配置 GlassFish 集群和节点。然后你只需要将一个 `distributable` 应用程序部署到集群，GlassFish 就会自动激活会话迁移并将应用程序分发到集群节点。

相反，Tomcat 和大多数独立的 Servlet 容器的配置要稍微复杂一些。开箱即用的 Tomcat 不会执行任何应用程序分发。运行相同应用程序的两个 Tomcat 服务器之间互不感知，也没有办法共享会话数据。你必须首先配置集群中的所有 Tomcat 服务器让它们识别彼此并协调会话迁移。然后你告诉它们如何相互共享会话数据——通过 TCP 套接字、数据库或其他手段。

你还需要在你的 Tomcat 节点之间设置负载均衡。这可以通过许多不同的方式实现，但通常你会使用 18-2 和 18-3 所示的技术之一。

在第一种常见场景中，标准的网络负载均衡器接收进入你 IP 地址的入请求，并在两个或多个 Apache HTTP 或 IIS Web 服务器之间进行轮询请求（参考图 18-2）。这些服务器运行变种 Apache Tomcat Connector——用于 Apache 的 `modjk` 或用于 IIS 的 `isapi`。Apache Tomcat Connector 了解其连接的 Tomcat 服务器的性能指标，并将请求运行到负载最小的 Tomcat 上。这是一个非常有价值的智能负载均衡器，被全球许多企业使用。然而，它也有一些缺点——即它（尚）不支持 WebSocket 流量。

另一种可行的解决方案是使用网络负载均衡器直接在 Tomcat 实例之间智能地平衡流量（参考图 18-3）。虽然这种负载均衡器无法像 Apache Tomcat Connector 那样测量性能指标，但良好的网络负载均衡器可以通过发送简单的周期健康检查请求并测量每个服务器响应的相对时间，来做出非常准确的性能测量。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_551_0.png)

图 18-2

![](img/9c2d45f6d547f72cb870b3a991f62ef6_551_1.png)

图 18-3

当你有了集群节点并配置好负载均衡后，你必须配置 Tomcat 集群通信和会话迁移。实现此点的最简单方法是在 Tomcat 的 `conf/server.xml` 中的 `<Engine>` 或 `<Host>` 元素内部添加以下元素：

```xml
<Cluster className="org.apache.catalina.ha.tcp.SimpleTcpCluster"/>
```

这激活了会话迁移配置。系统始终假设节点位于不同的主机上（可以使用相同的端口），并通过子网多播宣告自己的存在。地址通过 TCP 连接传输到集群中的所有节点。然而，这是默认设置，你可以对集群配置的许多内容进行自定义。你可以将其配置为使用数据库或共享文件系统，并更改集群运行的端口。你还可以调整 Tomcat 用于决定何时共享会话以及与哪些节点共享会话的算法。配置由两个或多个 Tomcat 服务器组成的集群过程非常复杂，而本书并不是关于 Tomcat 服务器管理的。因此，本章不会通过建立和使用集群环境来讲解。

> 注意：这里描述的负载均衡技术也适用于 GlassFish 集群。除了支持标准的负载均衡外，GlassFish 还使用了 `mod_is` 和 `isapi_redirect` Apache Connectors。配置集群通信和会话迁移则是完全不同的。

## 消息传递和集群是如何协同工作的？

正如你可能已经意识到的，跨集群的 `HttpSession` 迁移是有用的，但它无法满足你在构建 Web 应用程序时可能需要的所有需求。同样，Spring 对本地消息的支持非常强大，但它缺乏向集群中其他节点发送消息的能力。某些形式的分布式消息可以满足 `<distributable/>` 应用程序中 `HttpSession` 迁移无法满足的需求。

## 识别分布式消息的用途

为了理解分布式消息如何工作，首先需要理解在 `<distributable/>` 应用程序中，`HttpSession` 迁移无法满足的需求可以通过哪些形式的分布式消息来满足。

## 识别何时你需要消息传递和聚类

- 你的应用程序可以与集群中的每个其他应用程序建立 WebSocket 连接，并通过该连接发送消息。目标代码（Spring Framework）充当消息代理，并将消息传递给适当的订阅者。这种方式运行良好，但依赖于某种发现机制——一种常用方法是使用多播数据包。当应用程序完成启动过程时，它会向多播发送一个数据包，所有监听该数据包的应用程序都会接收到它。通过数据包中的信息，集群中的其他应用程序会向发送包的应用程序建立 WebSocket 连接。通过这种方式，应用程序只需重新广播多播数据包即可从故障中恢复。

- 你可以配合消息代理使用 WebSockets。这可以在 WebSocket 应用程序消息协议（WAMP，不要与 Windows-Apache-MySQL-PHP 混淆）中实现，你可以阅读相关介绍。在 WAMP 中，消息代理存在于不同的服务（或不同的服务器）中。本地代理可以是负载均衡器之前的服务器集群。应用程序与代理保持持久的 WebSocket 连接，并提交订阅请求，通过连接接收消息。在这种情况下，Spring Framework 不是主要的代理。在许多情况下，你可以使用代理来简单地广播应用程序消息，并使用 Spring 的 pub/sub 支持将消息传递给正确的订阅者。或者你可以仅将 pub/sub 支持用于本地消息，而将 WAMP 用于集群消息，两者互不干扰。你也可以完全放弃 Spring Framework 的 pub/sub，采用哪种方法取决于你，并且在很大程度上取决于应用程序的需求。

## Java Message Service 2.0 (JSR 343)

一种较旧但经过行业测试且可靠的分布式消息技术是 Java Message Service (JMS)。JMS 最初于 2001 年被规范，并在 2002 年更新到 1.1 版本。在 Java 世界的广泛应用中，它直到 2013 年 JSR 343 将 JMS 正式化之前都基本保持没有太大变化。JMS 2.0 并没有引入任何重大的概念变化；相反，它为了向后兼容消除了简化 API 中的歧义，增加了对 Java 7 `AutoCloseable` 资源的支持，并与整个 Java EE 套件进行了更完整的集成。

JMS 支持不同的消息模式，但对于主题、发布者和订阅者，它对 pub/sub 有原生支持。因此，JMS 充当消息代理。使用 JMS 的一个优势是可选的 API 将消息放入队列。消息会一直留在那里，直到感兴趣的消费者处理该消息。处理完毕后，消息将从队列中移除，其他感兴趣的消费者将不会再处理它。此过程可以是事务性的，确保消息在消费者成功处理之前永远不会被标记为已处理。

理解 JMS 是一个 API 而不是协议是非常重要的。JMS 的标准 API 使得你可以在很少更改或不更改代码的情况下切换提供者。然而，JMS 标准仅规定了提供者需要实现的一组接口，提供者可以按照自己的意愿实现协议。事实上，不同的实现之间可能无法（甚至很可能）相互操作和共享消息。这可能会带来许多缺点，由于这些原因，如果你预计应用程序可能需要与针对不同提供者编写或在不同平台上运行的应用程序通信，那么 JMS 通常不是最佳选择。

你可以像集成 WAMP 一样，将 JMS 集成到 Spring Framework 中，使其独立运行、互斥运行或与 Spring 的 pub/sub 支持协作工作。Spring 也对 JMS 特性具有原生支持，抽象了与 1.1 API 相关的某些棘手问题。遗憾的是，在完整的 Java EE 服务器（如 Tomcat 和独立应用程序）之外，JMS 很难使用。出于这个原因，本书没有详细介绍 JMS。

## 介绍高级消息队列协议

高级消息队列协议 (AMQP) 的标准化是为了解决与 JMS 以及其他类 JMS 规范的互操作性问题。与 JMS 不同，AMQP 规定了传输消息的线缆协议，并允许提供者使用该协议指定其依赖语言的 API。这允许由不同厂商在不同平台上编写许多应用程序使用通用的消息协议并进行有效的通信。

该项目于 2003 年启动，目标是改进金融机构之间的货币交易通信。AMQP 1.0 于 2011 年发布，并在一年后被采用为标准。尽管它源于金融服务业，但在各行业都有广泛应用。

AMQP 与其他标准一样，支持 pub/sub 以及事务消息队列和点对点（定向）消息。你可以使用与 WAMP 和 JMS 相同的技术将其集成到 Spring Framework 中。Spring Framework 没有内置的 AMQP 支持，但 Spring AMQP 项目提供了将 AMQP 消息解决方案无缝集成到你的 Spring 应用程序中的能力。不过，你并不一定要使用 Spring AMQP 来处理 AMQP 消息。本章在“使用 AMQP 分发事件”部分涵盖了 AMQP 代理和用于消息传递的 AMQP Java 客户端库。

## 为你的应用程序添加消息支持

使用 Spring Framework 为应用程序添加发布-订阅消息实际上非常简单。这方面的一个常见用例是当用户登录或注销应用程序时通知订阅者。wr.com 下载站点上的 Publish-Subscribe 项目做的正是这一点。它包含了你在过去几章中逐步构建的相同的 Spring 配置，以及几个事件、监听器和一个用于发布事件的控制器。

## 创建应用程序事件

如果你的应用程序要在用户登录或注销时发布和订阅事件，那么让这些事件继承自与认证相关的祖类可能是有意义的。`AuthenticationEvent` 为此提供了一个良好的基础。

```java
public abstract class AuthenticationEvent extends ApplicationEvent {

    public AuthenticationEvent(Object source) {
        super(source);
    }
}
```

然后，`LoginEvent` 和 `LogoutEvent` 扩展 `AuthenticationEvent` 以形成认证事件的层次结构。

```java
public class LoginEvent extends AuthenticationEvent {

    public LoginEvent(Object source) {
        super(source);
    }
}
```

```java
public class LogoutEvent extends AuthenticationEvent {

    public LogoutEvent(Object source) {
        super(source);
    }
}
```



在构造事件时，强制要求的事件源（event source）可以是任何你想要或需要它成为的类型。事件源的作用是识别事件的成因，而该成因在事件含义的语境下才有意义。例如，当员工被添加到人力资源系统时发布的事件可能将员工实体或标识符作为源。同样，与认证相关的事件可能应该包含主体（Principal）、用户名、用户凭据或其他用户标识符作为事件的源。考虑到这一点，`LoginEvent` 和 `LogoutEvent` 使用 `String` 类型的用户名作为源更有意义。

```java
public class LoginEvent extends AuthenticationEvent {

    public LoginEvent(String username) {
        super(username);
    }

}
```

```java
public class LogoutEvent extends AuthenticationEvent {

    public LogoutEvent(String username) {
        super(username);
    }

}
```

# 订阅应用程序事件

当然，创建应用程序事件的全部目的是让感兴趣的可以订阅并接收消息。事实上，你完全可能仅在需要和根据需要时创建事件。毕竟，如果没有人监听，发布成千上万条消息将浪费努力和资源。在这种情况下，三个不同的部分（程序逻辑片段）对不同的认证方法感兴趣。它们为什么对这些消息感兴趣并不重要；发布者并不关心——它只是必须发布它们。`AuthenticationInterestedParty` 出各种原因订阅了所有类型的认证消息。

```java
@Service
public class AuthenticationInterestedParty implements ApplicationListener<AuthenticationEvent> {

    private final Logger log = LogManager.getLogger();

    @Override
    public void onApplicationEvent(AuthenticationEvent event) {
        log.info("Authentication event for IP address {}", event.getSource());
    }

}
```

此 bean 的 `onApplicationEvent` 方法会在任何登录或注销消息时被调用。然而，`LoginInterestedParty` 和 `LogoutInterestedParty` bean 分别订阅登录和注销消息。

```java
@Service
public class LoginInterestedParty implements ApplicationListener<LoginEvent> {

    private final Logger log = LogManager.getLogger();

    @Override
    public void onApplicationEvent(LoginEvent event) {
        log.info("Login event for IP address {}", event.getSource());
    }

}
```

```java
@Service
public class LogoutInterestedParty implements ApplicationListener<LogoutEvent> {

    private static final Logger log = LogManager.getLogger();

    @Override
    public void onApplicationEvent(LogoutEvent event) {
        log.info("Logout event for IP address {}", event.getSource());
    }

}
```

所有的豆（bean）都执行相同的操作：当它们接收到已订阅的事件时，它们会将消息写入日志。当然，通过这个操作你可以做许多比记录日志多多的事情。你可以发送电子邮件或短信等通知，或者在数据库中创建或删除记录，仅举几例。

请记住，消息的传递是与发布方法的执行同步完成的，否则一个需要时间才能完成的操作可能会减慢向其他订阅者传递消息的速度，并将控制权返回给原始发布消息的方法。如果你有一个合理来说可能需要很长时间才能完成的消息处理操作，你应该在单独的线程中异步地运行它。坦率地说，这正是 Spring 异步方法执行大显用场的地方。通过在 `LogoutInterestedParty` 上使用 `@Async`，你可以使用 Spring 的任务执行器（task executor）。修改后的方法像任何其他 `@Async` 方法一样，会将任务移交给 Spring 的任务执行器。

## 发布应用程序事件

现在你已经创建了几个事件以及订阅这些事件消息的豆，你需要一种方法来发布事件，以便你可以测试这种发布/订阅支持。最简单的方法是创建一个标准的 Web 控制器，允许你交替发布 `LoginEvent` 和 `LogoutEvent`。

```java
@RestController
public class HomeController {

    @Inject ApplicationEventPublisher publisher;

    @RequestMapping("*")
    public String login(HttpServletRequest request) {
        this.publisher.publishEvent(new LoginEvent(request.getRemoteAddr()));
    }

    @RequestMapping("/logout")
    public String logout(HttpServletRequest request) {
        this.publisher.publishEvent(new LogoutEvent(request.getRemoteAddr()));
        return "logout";
    }

}
```

该方法记录了一个 `LoginEvent` 并返回登录名称。由于这个简单的应用程序缺少真正的身份验证系统，控制器使用了请求源的 IP 地址，以便能够正确演示事件源。`/WEB-INF/view/login.jsp` 视图非常简单，只提供了一个指向 logout 操作的链接。

```html
<!DOCTYPE html>
<html>
<head>
<title>Login</title>
</head>
<body>
<a href="/logout">Logout</a>
</body>
</html>
```

该方法与 login 几乎相同：

```html
<!DOCTYPE html>
<html>
<head>
<title>Login</title>
</head>
<body>
<a href="/*">Login</a>
</body>
</html>
```

测试这个发布/订阅设置非常简单。

1. 从你的 IDE 编译并启动应用程序，然后打开你喜欢的浏览器。
2. 访问 http://localhost:8080/messaging/，然后查看 Tomcat 日志目录下的 `application.log` 文件。你应该能在日志文件的末尾看到来自 `AuthenticationInterestedParty` 和 `LoginInterestedParty` 的日志项。
3. 点击浏览器中的 logout 链接，日志尾部中出现了来自 `AuthenticationInterestedParty` 和 `LogoutInterestedParty` 的日志项。注意，在 `LogoutInterestedParty` 中写入的日志项与其它条目来自不同的线程。这是由于 Spring 的异步方法执行，它在后台线程中调用了 `@Async` 方法，以便消息通信可以快速继续。

你可以继续点击 logout 和 login 链接，代码会不断向日志文件写入条目。

> 注意：你可能会对“事件”（event）和“消息”（message）这两个术语以及它们之间的关系感到好奇。你可以从很多角度来思考，但简单来说，它们并没有真正的区别，本书交替使用这两个术语。Spring Framework 使用“事件”一词很大程度上是因为该系统基于 `java.util.EventListener` 概念。但触发事件和通知事件监听器的概念与发布/订阅消息并没有区别。这取决于你如何使用这些工具，而不是它们被命名为什么。至于，应用程序消息在所有情况下都是由于某种类型的事件发生而发布的，因此“事件”一词是代表消息的对象的合适名称。

## 让你的消息在集群中可分布式

你可能对在 Spring Framework 应用程序中添加本地发布/订阅消息如此简单感到惊喜。将这种消息分布在集群中的所有节点上是一项更复杂的任务。你必须首先选择一个想要用于发送消息的协议。接下来，你必须创建一个自定义事件多发器（event multicaster），以使用选定的协议分发事件。在 Spring Framework 中，多发器（`org.springframework.context.ApplicationEventMulticaster` 的实现）负责发布所有事件并将其传递给适当的订阅者。最后，你可以通过运行两个或多个应用程序实例来测试分布式消息。

在本节中，你将探索支持分发所必需的一些基础事件更改，然后实现一个 WebSocket 集群。这个多发器使用直接通信而不是 WAMP 代理。结果是节点之间的连接形成了一个完全的简单图——在一个拥有 $n$ 个节点的集群中，每个节点的度为 $n-1$（这意味着有 $n-1$ 个 WebSocket 连接，因为它连接到集群中的其他每个节点）。这在图 18-4 中所示，该图展示了一个四节点集群。

当然，这种模式假设你想要将 Spring Framework 的发布/订阅消息与你选择的分布式消息协议集成。本章不涵盖如何独立使用这些工具。你可以通过从 wrox.com 下载网站下载 WebSocket-Messaging 项目来练习。它是你之前看到的 Publish-Subscribe 项目的扩展。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_560_0.png)

图 18-4

## 更新事件以支持分发

现在你已经创建了几个事件以及订阅这些事件消息的豆，你需要一种方法来发布事件，以便你可以测试这种发布/订阅支持。最简单的方法是创建一个标准的 Web 控制器，允许你交替发布 `LoginEvent` 和 `LogoutEvent`。

（此处省略代码块，不翻译，保持原文逻辑）

... 上文的 `return "login";` ...
```java
@RequestMapping("/logout")
public String logout(HttpServletRequest request) {
    this.publisher.publishEvent(new LogoutEvent(request.getRemoteAddr()));
    return "logout";
}
```

该方法记录了一个 `LoginEvent` 并返回登录名称。由于这个简单的应用程序缺少真正的身份验证系统，控制器使用了请求源的 IP 地址，以便能够正确演示事件源。`/WEB-INF/view/login.jsp` 视图非常简单，只提供了一个指向 logout 操作的链接。

（此处省略代码块，不翻译）

该方法与 login 几乎相同：

（此处省略代码块，不翻译）

测试这个发布/订阅设置非常简单。

1. 从你的 IDE 编译并启动应用程序，然后打开你喜欢的浏览器。
2. 访问 http://localhost:8080/messaging/，然后查看 Tomcat 日志目录下的 `application.log` 文件。你应该能在日志文件的末尾看到来自 `AuthenticationInterestedParty` 和 `LoginInterestedParty` 的日志项。
3. 点击浏览器中的 logout 链接，日志尾部中出现了来自 `AuthenticationInterestedParty` 和 `LogoutInterestedParty` 的日志项。注意，在 `LogoutInterestedParty` 中写入的日志项与其它条目来自不同的线程。这是由于 Spring 的异步方法执行，它在后台线程中调用了 `@Async` 方法，以便消息通信可以快速继续。

你可以继续点击 logout 和 login 链接，代码会不断向日志文件写入条目。

> 注意：你可能会对“事件”（event）和“消息”（message）这两个术语以及它们之间的关系感到好奇。你可以从很多角度来思考，但简单来说，它们并没有真正的区别，本书交替使用这两个术语。Spring Framework 使用“事件”一词很大程度上是因为该系统基于 `java.util.EventListener` 概念。但触发事件和通知事件监听器的概念与发布/订阅消息并没有区别。这取决于你如何使用这些工具，而不是它们被命名为什么。至于，应用程序消息在所有情况下都是由于某种类型的事件发生而发布的，因此“事件”一词是代表消息的对象的合适名称。

## 创建并配置自定义多发器

标准的事件多发器 `org.springframework.context.SimpleApplicationEventMulticaster` 没有任何集群支持。列表 18-1 中的 `ClusterEventMulticaster` 扩展了 `SimpleApplicationEventMulticaster` 以实现集群。`multicastEvent` 方法执行默认行为，然后如果事件是 `ClusterEvent` 类型，则将其发布到集群。这种行为非常重要，因为你可以通过扩展或不扩展 `ClusterEvent` 来控制特定的消息类型是本地的还是全局的。`publishClusteredEvent` 将事件发送到多发器中注册的每个端点。

你还没有看到 `MessagingEndpoint`，但请先看下一个。`registerEndpoint` 和 `deregisterEndpoint` 处理连接打开和关闭时添加的事件。`registerNode` 通过 WebSocket 连接到其他节点（你会看到它是如何被调用的），`handleReceivedClusteredEvent` 在多发事件之前设置其 `rebroadcasted` 标记。最后，`shutdown` 关闭所有 WebSocket 端点。

# LISTING 18-1: ClusterEventMulticaster.java

（此处省略代码块，不翻译）

```java
...
    }
}
```

`ClusterEvent` 类实现了 `Serializable` 以便它可以被序列化。

```java
public class ClusterEvent extends ApplicationEvent implements Serializable {
    private final Serializable serializableSource;
    private boolean rebroadcasted;

    public ClusterEvent(Serializable source) {
        super(source);
        this.serializableSource = source;
    }

    boolean isRebroadcasted() {
        return rebroadcasted;
    }

    void setRebroadcasted() {
        rebroadcasted = true;
    }

    @Override
    public Serializable getSource() {
        return serializableSource;
    }

    private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException {
        in.defaultReadObject();
        serializableSource = (Serializable) in.readObject();
    }
}
```

# 列表 18-1 (续)



```java
synchronized(this.endpoints) {
    for(ClusterMessagingEndpoint endpoint : this.endpoints)
        endpoint.send(event);
}

protected void registerEndpoint(ClusterMessagingEndpoint endpoint) {
    if(!this.endpoints.contains(endpoint)) {
        synchronized(this.endpoints) {
            this.endpoints.add(endpoint);
        }
    }
}

protected void deregisterEndpoint(ClusterMessagingEndpoint endpoint) {
    synchronized(this.endpoints) {
        this.endpoints.remove(endpoint);
    }
}

protected void registerNode(String endpoint) {
    log.info("Connecting to cluster node {}", endpoint);
    WebSocketContainer container = ContainerProvider.getWebSocketContainer();
    try {
        ClusterMessagingEndpoint bean = this.context.getAutowCapableBeanFactory()
            .createBean(ClusterMessagingEndpoint.class);
        container.connectToServer(bean, new URI(endpoint));
        log.info("Connected to cluster node {}", endpoint);
    } catch (DeploymentException | IOException | URyntaxException e) {
        log.error("Failed to connect to cluster node {}", endpoint, e);
    }
}

protected final void handleReceivedClusteredEvent(ClusterEvent event) {
    event.setRebroadcasted(true);
    this.multicastEvent(event);
}

@PreDestroy
public void shutdown() {
    synchronized(this.endpoints) {
        for(ClusterMessagingEndpoint endpoint : this.endpoints)
            endpoint.close();
    }
}
```

配置 Spring 使用你的多路器的方法如下：`RootContextConfiguration` 类定义了如下 `applicationEventMulticaster`。这一点是，bean 的名称必须与此处使用的名称匹配，以便 Spring 能够识别它。

```java
@Bean
public ClusterEventMulticaster applicationEventMulticaster()
{
    return new ClusterEventMulticaster();
}
```

# 使用 WebSockets 发送和接收事件

列表 18-2 中的 `ClusterMessagingEndpoint` 实际上是你在书中看到的最简单的 WebSocket 端点之一，但它的独特之处在于它同时标记了 `@Endpoint` 和 `@ClientEndpoint`。这是完全合法的：在连接建立后，WebSocket 客户端和服务器在能力和责任上是相同的；可以编写一个可以作为端点两端的端点。

该端点的编写方式是：每个节点与每个其他节点都有一个连接，并跨连接传递方向。端点在打开时向多路器注册自己，在关闭时注销自己。当它接收到一个事件时，它会将事件发送给多路器，而多路器会调用它的 `send` 方法将事件发送到集群。它的 `Codec` 使用 Java 序列化来通过网络线发送事件。

# 列表 18-2: ClusterMessagingEndpoint.java

```java
@ServerEndpoint(
    value = "/services/Messaging/{securityCode}",
    encoders = { ClusterMessagingEndpoint.Codec.class },
    decoders = { ClusterMessagingEndpoint.Codec.class },
    configurator = SpringConfigurator.class
)
@ClientEndpoint(
    encoders = { ClusterMessagingEndpoint.Codec.class },
    decoders = { ClusterMessagingEndpoint.Codec.class }
)
public class ClusterMessagingEndpoint {
    private static final Logger logger = LogManager.getLogger();
    private Session session;
    @Inject
    private ClusterEventMulticaster multicaster;
    @OnOpen
    public void onOpen(Session session) {
        Map<String, String> parameters = session.getParameters();
        if (parameters.containsKey("securityCode") &&
            "*a83e0389883a9".equals(parameters.get("securityCode"))) {
            try {
                logger.error("Received connection with illegal code: {}",
                    parameters.get("securityCode"));
                session.close(new CloseReason(CloseReason.Codes.VIOLATED_POLICY, "Illegal Code"));
            } catch (IOException e) {
                log.warn("Failed to close illegal connection.", e);
            }

        log.info("Successful connection onOpen.");
        this.session = session;
        this.multicast.registerEndpoint(this);
    }

    @OnMessage
    public void receive(ClusterEvent message) {
        this.multicast.handleReceivedClusteredEvent(message);
    }

    public void send(ClusterEvent message) {
        try {
            this.session.getBasicRemote().sendObject(message);
        } catch (IOException | EncodeException e) {
            log.error("Failed to send message to adjacent node.", e);
        }
    }

    @OnClose
    public void close() {
        log.info("Cluster node closed.");
        this.multicast.deregisterEndpoint(this);
        if (this.session.isOpen()) {
            try {
                this.session.close();
            } catch (IOException e) {
                log.error("Error while closing cluster node connection.", e);
            }
        }
    }

    public static class Codec implements Encoder.BinaryStreamClusterEvent,
        Decoder.BinaryStreamClusterEvent {
        @Override
        public ClusterEvent decode(InputStream stream)
            throws DecodeException, IOException { ... }

        @Override
        public void encode(ClusterEvent event, OutputStream stream)
            throws IOException { ... }

        @Override
        public void init(EndpointConfig endpointConfig) { }
        @Override
        public void destroy() { }
    }
}
```

# 列表 18-2 (续)

# 使用多播数据包发现节点

使用多播数据包发现节点。你现在拥有一个通过多播发现彼此的 WebSocket。然而，这需要同步。`ContextRefreshed` 之后可以连接到 ` `。在 18-3: `ClusterManager.java` 中，`synchronized` 块可以处理 ` `。18-3: 11-3:: 18-3: 18-3: 18-3: 18-3: 18-3: 18-3: 18-3: 18-3: ClusterManager.java

```java
@Service
public class ClusterManager implements ApplicationListener<ContextRefreshed> {
    private static final Logger log = LogManager.getLogger();
    private static final String GROUP = "224.0.0.3";
    private static final int PORT = 6789;
    private final Object mutex = new Object();
    private boolean initialized = false;
    private String messagingUrl;
    private MulticastSocket socket;
    private Thread listener;

    @Inject
    private ClusterEventMulticaster multicast;

    @PostConstruct
    public void listenForannouncements(Exception e) throws Exception {
        synchronized(mutex) {
            socket = new MulticastSocket(PORT);
            socket.joinGroup(InetAddress.ByName(GROUP));
            listener = new Thread(this::listen, "cluster-listener");
        }
        listener.start();
    }
```

# 列表 18-3 (续)

```java
    private void listen() {
        byte[] buffer = new byte[2048];
        DatagramPacket packet = new DatagramPacket(buffer, buffer.length);
        while (true) {
            try {
                socket.receive(packet);
                String url = new String(buffer, 0, packet.getLength());
                if (url.equals(messagingUrl)) {
                    log.warn("Received blank packet.");
                } else if (url.equals(multicastUrl)) {
                    log.info("Ignoring own multicast packet.");
                } else {
                    multicast.registerNode(url);
                }
            } catch (IOException e) {
                if (!destroyed) {
                    log.error(e);
                    return;
                }
            }
        }
    }

    @Destroy
    public void shutDownMulticastConnection() throws IOException {
        destroyed = true;
        try {
            listener.interrupt();
            socket.leaveGroup(GROUP);
        } finally {
            socket.close();
        }
    }

    @Async
    @Override
    public void onApplicationEvent(ContextRefreshed event) {
        if (initialized) {
            return;
        }
        initialized = true;
        try {
            URL url = new URL(pingUrl);
            log.info("Attempting to connect to self at {}.", url);
            int tries = 0;
            while (true) {
                tries++;
                URLConnection connection = url.openConnection();
                connection.setTimeout(100);
                try (InputStream stream = connection.getInputStream()) {
                    log.info("Connected to self.");
                    break;
                } catch (IOException e) {
                    if (tries > 10) {
                        log.error("Could not connect to self after 10 attempts.");
                        return;
                    }
                    log.warn("Failed to connect to self, retrying in 5 seconds...");
                    Thread.sleep(5000);
                }
            }
        } catch (IOException | InterruptedException e) {
            log.error("Error connecting to self", e);
        }
    }
}
```

# 让你的消息跨集群分发 | 533



```java
String response = StreamUtils.copyToString(stream, StandardCharsets.UTF_8);
if (response != null && response.equals("ok")) {
    log.info("Broadcasting announcement packet.");
    DatagramPacket packet = new DatagramPacket(this.messagingUrl.getBytes(), this.messagingUrl.length(), GROUP, PORT);
    synchronized (this.mutex) {
        this.socket.send(packet);
    }
    return packet;
} else {
    log.warn("Incorrect response: {}", response);
}
try {
    if (tries > 120) {
        log.fatal("Could not connect to self within 60 seconds.", e);
        return;
    }
    Thread.sleep(400L);
} catch (Exception e) {
    log.fatal("Could not connect to self.", e);
}
```

# 使用多个部署模拟集群

在集群中，你通常将同一个应用程序部署在两个或多个 Servlet 容器实例上，且具有相同的上下文路径（例如，`http://node1.example.org:8080/messaging` 和 `http://node2.example.org:8080/messaging`）。事实上，如果你想在会话节点之间共享 `HttpSession` 数据，你必须这样做；你不能在部署在不同上下文的应用程序之间共享会话数据（出于安全考虑）。

测试集群没有捷径。但是，测试集群有一个捷径方法：你可以将同一个应用程序以多个上下文路径部署到同一台服务器上。这很容易实现，但你必须更改一些设置，以便从日志文件中直观地看出发生了什么。

首先，`HomeController` 中的登录和注销发布使用上下文路径作为事件源，而不是 IP 地址。这让你能够知道事件是源于哪一个。

```java
this.publisher.publishEvent(new LoginEvent(request.getContextPath()));
this.publisher.publishEvent(new LogoutEvent(request.getContextPath()));
```

此外，`AuthenticationInterested`、`LoginInterested` 和 `LogoutInterested` 使用注入的 `ServletContext` 来获取接收事件的应用程序的上下文路径，以及发送事件的应用程序（通过事件源）的上下文路径。

# 第 18 章 使用消息和集群实现灵活性与可靠性

```java
@Inject
ServletContext servletContext;

@Override
public void onApplicationEvent(AuthenticationEvent event) {
    log.info("Authentication event from context {} received in context {}.", event.getSource(), this.servletContext.getPath());
}
```

你现在已经准备好测试消息了。开始步骤：

1. 确保 IDE 中已配置应用程序在 Tomcat 服务器上部署 `/messaging1`。
2. 构建 WAR 文件，并将产物从输出目录复制到 Tomcat 的 `webapps` 目录，在此过程中将其重命名为 `messaging2.war`。
3. 从 IDE 启动 Tomcat，并密切关注日志输出。`/messaging2` 启动（取决于你使用的 IDE），当它发送组播包时，它是集群中的唯一节点。没有其他节点连接它。`/messaging1` 接着启动并记录到同一个文件中。当它发送组播包时，`/messaging2` 接收到包并使用页脚中的 WebSocket URL 连接到 `/messaging1`。
4. 打开浏览器并访问 `http://localhost:8080/messaging1`；然后查看日志文件。你会看到一条带有“Authentication event from context /messaging1 received in context /messaging1”的日志记录，随后是另一条日志“Authentication event from context /messaging2 received in context /messaging2”。你还看到日志“Login event for context /messaging1 received in context /messaging1”和“Login event for context /messaging2 received in context /messaging2”。点击浏览器中的链接，你会看到四个类似的日志项出现，通知你注销。
5. 访问 `http://localhost:8080/messaging2` 并查看日志文件。这次的日志项为：“Authentication event from context /messaging2 received in context /messaging2”，“Authentication event from context /messaging2 received in context /messaging1”等等。这意味着你正在成功地使用 Spring 的发布/订阅事件和 WebSockets 在应用程序集群中分发消息。
6. 如果你觉得非常有勇气，关闭 Tomcat 并再次复制一份 WAR 文件，将其命名为 `messaging3.war`。再次启动 Tomcat 并重复测试过程，也尝试第三个集群。
7. 完成测试后，确保从 Tomcat 的 `webapps` 目录中删除 `messagingn.war` 文件和相应的 `/messagingn` 目录。

# 使用 AMQP 分发事件

由于我们有很多种方法在应用程序中实现分布式消息传递，这本书只能涵盖其中有限的几种。在上一节中，你探索了使用直接 WebSocket 连接，这形成了一个完整的基础图模型。这种配置的问题在于它的可扩展性不高。它在小型集群中运行良好，但连接数随着集群规模的增大而线性增加。如果你在学校上过图论课程，你会记得具有 $n$ 个顶点的连通图 $K_n$ 的边数公式为 $\frac{n(n-1)}{2}$。虽然四节点集群可能只有 6 条连接，但 8 节点集群总共有 28 条连接，16 节点集群有 120 条连接。如果你正在运行集群，面对的是数千个连接。

JMS 是 Java 环境中处理此类任务的自然选择。然而，在 Tomcat 这样的独立应用程序中，配置 JMS 非常困难。因此，本节介绍了使用消息队列协议（AMQP）在你的应用程序中进行分布式消息传递的一种方法。在这种配置中，代理（broker）不管理发布/订阅主题。相反，它将所有消息传递给所有节点，而 Spring Framework（作为本地代理）将正确的消息传递给订阅者。

# 配置 AMQP 代理

有多种 AMQP 提供者实现可用，供你在选择环境中使用的 AMQP 代理时参考。到目前为止，最流行且强大的实现是 RabbitMQ，它是一个免费开源的 AMQP 服务器，并在需要时也提供支持。本节并不作为 RabbitMQ 的配置和管理指南，但它将引导你在不到 10 分钟内下载、安装并使用默认配置。

RabbitMQ 使用 Erlang 编写，Erlang 是一种具有垃圾回收和虚拟环境的并发语言，类似于 Java（尽管语法完全不同）。在安装 RabbitMQ 之前，你必须下载并安装 Erlang。在许多 Linux 发行版中，你需要使用包管理系统，但在 Red/Fedora/CentOS 系统上，你需要从网站下载。如果你在 Windows 上安装，还需要下载并安装 `handle.exe`（将 `handle.exe` 放置在 Program Files 的某处，例如 `C:\Program Files\Sysinternals`，然后将该目录添加到系统变量 `PATH` 中）。

完成这些准备工作后，按照以下步骤操作：

1. 从 RabbitMQ 网站下载服务器。
2. 点击与你的操作系统对应的安装指南链接。
3. 按照指示安装服务器。（对于 Windows，只需运行可执行文件并确保安装 Windows 服务）。
4. 如果你在 Unix 环境下安装了 RabbitMQ，执行以下命令：

```
rabbitmq-plugins enable rabbitmq-management
```

如果你在 Windows 上安装了 RabbitMQ，打开命令提示符，将当前目录更改到 RabbitMQ 的 sbin 目录（例如 `C:\Program Files (x86)\RabbitMQ Server\rabbitmq-server-3.1.3\sbin`），然后执行以下命令：

```cmd
.\rabbitmq-plugins.bat enable rabbitmq-management
```

此命令启用了 Web 管理控制台，默认情况下它是禁用的。

5. 如果你在 Windows 中安装了 RabbitMQ，请使用服务管理器并重启 RabbitMQ 服务。在其他操作系统上，根据情况启动或重启二进制文件。
6. 此时，你应该能够在你喜欢的浏览器中通过 `http://localhost:15672/` 访问 RabbitMQ。使用安装时默认的用户名和密码登录。如果你无法访问管理控制台，请重新检查安装步骤并查阅文档查看哪里出了问题。

运行一个基础的 RabbitMQ 只需完成这些操作。当然，在生产环境中，你应该加固安全性并针对性能进行配置调优。

## 创建 AMQP 多播器

创建一个使用 AMQP 分发事件的 `EventMulticaster` 非常简单。你可以参考可以在 wrox.com 代码下载中找到 AMQP-Messaging 项目。该项目与你之前过的 WebSocket-Messaging 项目非常相似，并且包含相同的 `ClusterEvent`。它没有 `ClusterManager` 或 `ClusterMessagingEndpoint`。所有逻辑都包含在列表 18-4 的 `ClusterEventMulticaster` 中，该类的 `multicaster` 方法与 WebSocket-Messaging 中的方法完全相同。

列表 18-4：ClusterEventMulticaster.java

```java
public class ClusterEventMulticaster extends SimpleApplicationEventMulticaster {
    private static final Logger log = Log.getLogger();
    private static String EXCHANGE_NAME = "AMQPMessagingTest";
    private static String HEADER = "X-Wrox-Cluster-Node";

    private final AMQP.BasicProperties.Builder builder = new AMQP.BasicProperties.Builder();
    private Connection amqpConnection;
    private Channel amqpChannel;
    private String queueName;
    private Thread listener;
    private boolean destroyed = false;

    @Override
    public final void multicasterEvent(ApplicationEvent event) { ... }

    protected void publishClusteredEvent(ClusterEvent event) throws IOException {
        this.amqpChannel.basicPublish(EXCHANGE_NAME, "", this.builder.build(), SerializationUtils.serialize(event));
    }

    @PostConstruct
    public void setupRabbitConnection() throws IOException {
        ConnectionFactory factory = new ConnectionFactory();
        factory.setHost("localhost");
        this.amqpConnection = factory.newConnection();
        this.amqpChannel = this.amqpConnection.createChannel();

        this.amqpChannel.exchangeDeclare(EXCHANGE_NAME, "fanout");
        this.queueName = this.amqpChannel.queueDeclare().getQueue();
        this.amqpChannel.queueBind(this.queueName, EXCHANGE_NAME, "");

        Map<String, Object> headers = new Hashtable<>();
        headers.put(HEADER, this.queueName);
        this.builder.headers(headers);

        this.listener = new Thread(this::listen, "RabbitMQ-1");
        this.listener.start();
    }

    @PreDestroy
    public void shutdownRabbitConnection() throws IOException {
        this.destroyed = true;
        this.listener.interrupt();
        this.amqpChannel.close();
        this.amqpConnection.close();
    }

    private void listen() {
        try {
            QueuingConsumer consumer = new QueuingConsumer(this.amqpChannel);
            this.amqpChannel.basicConsume(this.queueName, true, consumer);

            while (!this.destroyed) {
                QueuingConsumer.Delivery delivery = consumer.nextDelivery();
                Object header = delivery.getProperties().headers().get(HEADER);
                if (header == null || header.toString().equals(this.queueName)) {
                    ClusterEvent event = SerializationUtils.deserialize(delivery.getBody());
                    event.setRebroadcasted();
                    this.multicastEvent(event);
                }
            }
        } catch (Exception e) {
            if (!this.destroyed) {
                log.error("Error listening for message deliveries.", e);
            }
        }
    }
}
```

大部分有趣的工作发生在 `setupRabbitConnection` 和 `listen` 方法中。`shutdownRabbitConnection` 方法简单地关闭资源。`setupRabbitConnection` 首先建立到本地 RabbitMQ 服务器的连接，然后打开一个通道（channel）。它设置了一个由 `AMQPMessagingTest` 定义的交换机（exchange），并将其设置为 fanout。

## 使用 AMQP 分发事件

> **注意**：交换机（Exchange）是一种定义消息如何投递到队列的机制。Fanout 模式意味着所有发布的消息都会投递到所有队列。你可以在 RabbitMQ 文档中学习更多关于这些主题以及通道的知识。进一步探索这些内容超出了本书的范围。



接下来，此方法请求 RabbitMQ 创建一个随机队列（该队列对此节点唯一），并将队列绑定到通道和交换机。在发送每条消息时，会使用创建并分配自定义 `X-Rabbit-Cluster-Node` 头的属性构建器。只有当消息接收时，节点才会忽略由自己发送的消息。最后，它启动一个监听线程来处理传入的消息。

`listen` 方法负责接收和处理来自 RabbitMQ 投递的消息。它创建一个消费者（`consumer`）并将消费者绑定到通道和队列。消费者在调用 `nextDelivery` 时阻塞，直到消息到达。监听器检查所有收到的消息，以确保它们来自不同的节点（而不是自己），并将它们反序列化到本地应用程序。注意，示例代码使用 Java 序列化来投递消息，讽刺的是，这意味着在该环境中只有 Java 应用程序可以使用这些消息。对于你的需求，这样做是可以的。如果你想与其他平台上的应用程序通信，你可以使用更通用的格式，例如 JSON。

## 运行启用 AMQP 消息的应用程序

你可以按照测试 WebSocket-Messaging 的完全方式测试 AMQP-Messaging 应用程序：

1. 确保 RabbitMQ 运行。
2. 确保应用程序在 IDE 中配置为部署到 Tomcat 服务器上的 `messaging1`。
3. 构建 WAR 文件，将其重命名为 `messaging2.war`，并拷贝到 Tomcat 的 `webapps` 目录。
4. 启动 IDE 中的 Tomcat，`messaging1` 和 `/messaging2` 应用程序应该启动。
5. 访问 `http://localhost:8080/messaging1` 和 `http://localhost:8080/messaging2`，交替点击注销和登录链接。你应该看到与使用 WebSocket-Messaging 应用程序相同的日志条目。再次，你还可以创建并部署名为 `messaging3.war` 的第三个 WAR 文件，以模拟三个节点的集群。
6. 在 Tomcat 运行时，访问 RabbitMQ Web 管理控制台并点击顶部的 `Queues` 菜单。你应该看到类似图 18-6 的界面，显示 RabbitMQ 为你的应用程序实例创建的随机队列。
7. 测试时，确保从 Tomcat 的 `webapps` 目录中删除 `messagingn` 文件和相应的 `/messaging` 目录。

# 第三部分：使用 JPA 和 Hibernate ORM 持久化数据

- ➤ 第 19 章：介绍 Java 持久化 API 和 Hibernate ORM
- ➤ 第 20 章：使用 JPA 注解将实体映射到表
- ➤ 第 21 章：在 Spring Framework 仓库中使用 JPA
- ➤ 第 22 章：使用 Spring Data JPA 消除模板代码仓库
- ➤ 第 23 章：使用 JPA 和 Hibernate Search 搜索数据
- ➤ 第 24 章：创建高级映射和自定义数据类型

# 第 19 章：介绍 Java 持久化 API 和 Hibernate ORM

## 本章内容

- 理解数据持久化
- 什么是对象-关系映射（ORM）？
- 理解 Hibernate ORM
- 如何准备关系型数据库
- 如何使用本章中的 Maven 依赖

### 本章代码下载

本章没有代码下载。

### 本章的新 Maven 依赖

本章没有新的 Maven 依赖。请继续使用之前所有章节引入的 Maven 依赖。

## 什么是数据持久化？

除少数外，每个应用程序都需要某种形式的持久化。但持久化究竟是什么？简单来说，**持久化**是让某种形式的数据跨应用程序的多次执行而存在。从意义上说，日志是一种持久化，因为它持久了程序执行的诊断信息，以便你可以在应用程序执行期间或之后对其分析。事实上，你可以将日志信息持久化到扁平文件、XML 文件、JSON 文件、数据库或任何其他介质，这与所有形式的持久化一样。

然而，通常持久化并不是指日志。相反，它指的是将应用程序中的**实体**保存到某些存储介质。实体可以是任何内容——人、用户、票据、论坛帖子、购物车、商店订单、产品、新闻等。列表应无不尽，整本书的长度也不足以列举它们的所有。在软件开发中，实体数据通常没有重大的逻辑。实体在程序单元之间传递，并封装了程序使用的属性。

在你在本书第二部分中构建的 Spring Framework 中，你的控制器创建实体并将其交给服务以应用业务规则，然后服务处理来自仓库的实体，仓库使用 `map` 在内存中存储实体。同样，当你的控制器接收到一个或多个实体的请求时，它们会将这些请求传递给服务，由服务从仓库中检索存储的实体。在 Java 中，实体是 `POJO`；在 C# 中，实体是 `POCO`。其他语言对这些数据类型有相应的术语。

然而，内存中的持久化 `map` 在现实世界中是不够的。数据并不存在于每个节点，并且当应用程序关闭时就会消失。在考虑如何持久化数据时，你有许多选择，并没有所谓的“万灵妙药”。尽管如此，某些存储介质比其他的更常见，无论好坏如何。

## 扁平文件实体存储

实体持久化的自然方法是使用操作系统提供的原生文件系统。一种可能的场景是为每种实体类型创建一个目录，目录中的每个文件代表该实体的**代理键**（surrogate key，SK）的不同名称。SK 是实体的唯一标识符，允许你在存储介质中单独定位它。作为文件名，SK 充当索引，以便定位实体。

存储在扁平文件中的数据可以采用许多格式。它可以被持久化为 Java 序列化对象（其他语言的序列化对象），或使用键值对、XML 或 JSON 表示。Java 序列化格式能够实现高效的存储和检索，但完全限制了可移植性。只有其他 Java 应用程序可以访问该实体。

无论何种方式，与其替代方案相比，扁平文件存储极其缓慢且难以管理。每个 CRUD 操作都会导致文件句柄的打开、数据立即写入文件系统以及关闭该文件。这种开销是巨大的，特别阻碍了涉及代理键以外的实体定位操作，例如对实体属性进行搜索。由于原因，扁平文件实体存储仅适用于最基础的情况，例如应用程序设置。

## 结构化文件存储

结构化文件存储在许多方面与扁平文件存储相似。它使用操作系统的文件系统将数据存储在文件中，CRUD 操作通常会导致文件句柄的重复打开和关闭。然而，结构化文件存储系统通常不是依赖目录和单个文件存储，而是创建一个大文件，使用程序可以理解的预定义结构在一个文件中存储许多实体。它不是每个实体类型一个目录，而是通常是每个实体类型一个文件。这种方法的优点是搜索操作效率高得多；它们可以在单个文件上执行，而不是成百上千个文件上。但是，通过代理键进行单独查找可能会受到这种安排的影响。通常需要创建某种类型的较小索引，以便识别记录在较大数据文件中的位置。

如果这听起来像是一个关系型数据库，那么你是正确的。许多关系型数据库的工作方式非常相似。Brieve 是最早的一类数据库之一，它使用索引顺序访问方法（ISAM）在文件中存储条目。然而，关系型数据库和结构化文件存储系统之间存在许多差异，即结构化存储倾向于私有化并直接在应用程序代码中发生，而关系型数据库是基于某种可移植的标准，并且通常运行在另一个应用程序中。更重要的是，结构化文件存储通常不感知实体之间的关系。从这个意义上说，Brieve 是一个结构化文件存储系统而不是关系型数据库；然而，它确实拥有今天关系型数据库中的事务概念。

## 关系型数据库系统

如果你正在阅读这里，可能已经知道关系型数据库管理系统（RDBMS）。在第一章和下一章之前，你必须了解它们。关系型数据库将条目存储为表，每个表存储一种类型的实体（通常是定义各种字段或列名称、类型的模式）。你不能在不存在列的表中存储记录，你也不会在非 NULL 列中存储空值。通常，表包含一个主键列（或者有时是由几个列组成的复合主键），作为其代理键。你使用 ANSI 标准的结构查询语言（SQL）与关系型数据库交互，这种语言旨在以通用方式操作模式和数据内容。

遗憾的是，没有关系型数据库完全遵守 ANSI 标准，大多数都定义了其他数据库不支持的私有扩展。例如，Oracle 将其 SQL 实现称为 PL/SQL，而 Microsoft Server 使用 Transact-SQL 或 T-SQL。这使得创建适用于所有数据库的所有基础 SQL 语句变得困难，并且几乎无法形成跨多个数据库的 `CREATE ALTER` 语句。

> **注意** SQL 读作 "sequel" 还是 "es-kyu-el" 是一个问题。本文作者偏好 "sequel" 的发音，有两个重要原因。首先，这在历史上是正确的。当它在 20 世纪 70 年代最初开发时，最初被称为结构化英语语言（简称 SEQUEL）。然而，SEQUEL 已经注册商标，因此缩短为 SQL。其次，“sequel”更容易说。因为你是在读这本书而不是在听，所以你可以按你喜欢的方式发音。

在 Java 中，你通过 Java Database Connectivity（JDBC）与关系型数据库交互。你通过使用 `java.sql.DriverManager` 或某种 `java.sql.DataSource`（如连接池）获取关系型数据库的 `java.sql.Connection`，然后针对 `Connection` 执行语句。对于不包含参数的简单语句以及包含一个或多个参数的复杂语句，你使用 `java.sql.Statement` 和 `PreparedStatement`。甚至还有一个用于执行存储过程和函数的 `java.sql.CallableStatement`。这些接口提供了在数据库上执行 SQL 语句以查询或操作数据的能力。在数据库中保存实体和从数据库中检索实体涉及将列名映射到 `POJO` 属性。这就是你在本书的这一部分要解决的挑战。

## 对象数据库

面向对象的数据库管理系统（OODBMS），通常被称为对象数据库，是试图解决面向对象实体与关系型数据库之间自然脱节的一种尝试。它们使用与面向对象编程语言相同的数据表示模型。

对象数据库的一个原则是以这种方式存储数据，以便仍然可以使用 SQL 来操作和检索对象。遗憾的是，由于对象的继承，这会导致许多问题。另一种方法是在数据库中存储 JSON 或 XML 列，并使用专有的 SQL 扩展来查询这些数据，但对这类数据进行索引以实现高效检索的能力非常微弱。对象数据库的关键问题在于尝试维护严格的模式（schema）。正因如此，尽管对象数据库自 1980 年代以来一直存在，从未真正流行。

## 无模式数据库系统

自然地，无模式数据库是指缺乏严格模式的数据库。NoSQL 一术诞生于 1998 年，被广泛用于描述此类数据库。NoSQL 数据库是一个相对新的现象，在过去的 5 到 10 年内才流行。NoSQL 数据库解决了许多关系型数据库中不易解决的问题，例如字段和对象继承。NoSQL 数据库有多种，最常见的是文档型数据库。

尽管缺乏严格的结构，文档仍以一致且为人知的格式（如 XML 或 JSON，或 BSON，JSON 的二进制版本）对数据进行编码。**文档**（document）大致等同于关系型数据库中的记录，而**集合**（collection）大致等同于表。集合中的文档不需要遵循特定的模式，它们通常是相似的。当集合中的两个文档包含具有相同名称属性时，最佳实践规定这些属性具有相同的类型并具有相同的语义含义。

大多数文档数据库往往具有极快的插入速度，有时比关系型数据库中的索引查找快几个数量级，但它们存储的数据规模可以比关系型数据库大得多。某些文档数据库可以存储数百 GB 甚至 TB 级的数据而不牺牲插入性能。这使得文档数据库成为存储日志和审计相关数据的理想选择。其中一些较受欢迎的文档数据库包括 MongoDB、Apache CouchDB 和 Couchbase Server。

另一种流行的 NoSQL 数据库类型是**键值存储**（key-value store）。它顾名思义，以非常扁平的方式存储键值对。这可以比作 Java 的 `Map<String, String>`，尽管某些键值存储是多值的，可以存储更像 `List<String>` 的内容。一些流行的键值存储包括 Apache Cassandra、Firebase、Amazon DynamoDB、memcache、Redis、Apache River、Couchbase 和 MongoDB。（是的，某些文档数据库也兼作键值存储）。

图数据库是侧重于对象关系的 NoSQL 数据库。在图数据库中，对象具有属性（属性），对象与其他对象有关系，而关系也具有属性。数据以图的形式存储和表示，实体之间的关系自然存在，而不是通过外键创建的刻意方式。这使得解决隔离开问题变得容易，能够找到插入时可能未被发现的实体间的关系。最流行的图数据库可能是 Neo4j。尽管 Neo4j 是用 Java 编写的，且尽管其名称如此，它可以在任何适用于 Java 程序的平台上良好运行。

NoSQL 数据库不基于任何标准（如 ANSI SQL）运行。因此，没有通用的方法（如 JDBC）来访问任何两个 NoSQL 数据库。这无疑是使用 NoSQL 数据库的自然劣势，但也有优势。每个 NoSQL 数据库都带有自己的客户端库，大多数这些客户端可以接收 Java 对象并将其直接存储在数据库中，无论数据库要求何种格式。这消除了将 `POJO` 映射到“表”以及将属性映射到“列”的任务，从而使 NoSQL 成为实体存储极具吸引力的关系数据库替代方案。由于方法不同，并且 NoSQL 客户端消除了对对象关系映射器（ORM）的需求，本书将不再涵盖它们。

## 什么是对象关系映射器？

迄今为止，关系型数据库是目前常用的数据库。你可以发现它们支持所有主要的企业级软件，存储着从应用程序设置到审计记录的所有内容。然而，在关系型数据库中存储面向对象的实体通常不是一项易事，需要大量的重复代码和数据类型之间的转换。对象关系映射（或 ORM）是为了解决这个问题而创建的。ORM 在关系数据库中持久化实体并从中检索实体，而无需程序员编写 SQL 语句并将实体属性翻译为语句参数以及将结果列翻译为实体属性。

本章介绍了五个对象关系映射器以及如何使用它们在你的应用程序中持久化实体。在真正意识到 ORM 如何提供帮助之前，你需要先理解这个问题。

## 理解实体持久化问题

为了理解持久化和检索实体所需的代码规模，请考虑以下存储方法，它从数据库检索一个产品记录将其数据复制到一个假设的 `Product` 对象中。

```java
public Product getProduct(long id) throws SQLException {
    try (Connection connection = this.getConnection();
         PreparedStatement s = connection.prepareStatement(
             "SELECT * FROM dbo.Product WHERE ProductId = ?")) {
        s.setLong(1, id);
        try (ResultSet r = s.executeQuery()) {
            if (!r.next()) {
                return null;
            }

            Product product = new Product();
            product.setName(r.getString("Name"));
            product.setDescription(r.getString("Description"));
            product.setDatePosted(r.getObject("DatePosted", Instant.class));
            product.setPurchases(r.getLong("Purchases"));
            product.setPrice(r.getDouble("Price"));
            product.setBulkPrice(r.getDouble("BulkPrice"));
            product.setMinimumUnits(r.getInt("MinimumUnits"));
            product.setSku(r.getString("Sku"));
            product.setEditorsReview(r.getString("EditorsReview"));

            return product;
        }
    }
}
```

如你所知的，这张图中缺少了一些东西。首先，这个方法没有错误处理，这在现实中是需要的。此外，存储的产品通常比这多得多的属性——这里的代码非常保守。它的长度很容易是目前长度的几倍。这里创建一个新的 `Product`：



```java
public void addProduct(Product product) throws SQLException {
    try (Connection connection = this.getConnection();
         PreparedStatement s = connection.prepareStatement(
             "INSERT INTO dbo.Product (Name, Description, DatePosted, " +
             "Purchases, BulkPrice, MinimumUnits, Sku, EditorsReview) VALUES (?, ?, ?, ?, ?, ?, ?)",
             new String[] { "ProductId" })) {
        s.setString(1, product.getName());
        s.setString(2, product.getDescription());
        s.setObject(3, product.getDatePosted(), JdbcType.TIMESTAMP);
        s.setLong(4, product.getPurchases());
        s.setDouble(5, product.getPrice());
        s.setDouble(6, product.getBulkPrice());
        s.setInt(7, product.getMinimumUnits());
        s.setString(8, product.getSku());
        s.setString(9, product.getEditorsReview());
        if (s.executeUpdate() != 1) {
            throw new SQLException("Failed to insert record.");
        }
    }
    try (ResultSet r = s.getGeneratedKeys()) {
        if (r.next()) {
            product.setProductID(r.getLong("ProductID"));
        } else {
            throw new SQLException("Failed to retrieve product ID.");
        }
    }
}
```

# 什么是对象关系映射器？

当然，你还必须提供更新和删除产品的方法（尽管可以争论说，删除方法的实现要简单得多）。

这些方法单独来看可能并不糟糕，但考虑一个更复杂的实体，然后考虑到产品评论、购物车、订单、物流、搜索、用户、店铺管理、折扣和优惠券、商家（如果你允许用户出售自己的产品）、支付、退款以及一家在线商店，这很容易就会涉及几十甚至上百个不同的实体，每个实体的代码都与此非常相似，每个都需要大量的 SQL 以及对 `Statements` 和 `ResultSets` 的使用。

毫无疑问，在你完成这些工作之前，你可能会开始编写自己的工具来让这项任务变得更容易。这可能涉及到某种形式的反射，以便它可以处理任何实体类型。如果这个工具已经为你写好了，并且已经过用户社区的广泛测试，那不是更简单吗？

## ORM 让实体持久化变得更容易

一个好的 O/RM 可以极大简化这些容易出现拼写错误且难以进行有效测试的冗长代码。ORM 使用反射分析实体，并将它们的属性与存储它们的关系型数据库的列进行对齐。在使用 O/RM 时，之前的代码变得更像这样：

```java
public Product getProduct(long id) {
    return this.getCurrentTransaction().get(Product.class, id);
}
```

```java
public void addProduct(Product product) {
    this.getCurrentTransaction().persist(product);
}
```

更好的是，添加更新和删除产品的方法同样简单，而且比直接使用 JDBC 要容易得多：

```java
public void updateProduct(Product product) {
    this.getCurrentTransaction().update(product);
}
```

```java
public void deleteProduct(Product product) {
    this.getCurrentTransaction().delete(product);
}
```

如你所见，这段代码要易接受得多。事实上，如果你足够聪明，可以将其写为实体的泛型，这样你就可以在抽象类中编写此代码并适用于任何类。当然，这并不是全部。O/RM 不能仅仅“知道”哪些表和列可以映射某个实体或多个实体，它也不总是知道数据类型应该如何对齐（尽管通常它可以自己弄出其中的大部分信息）。当使用 O/RM 时，你必须创建正式的映射指令，告诉 O/RM 如何映射你的实体。这取决于你使用哪种 ORM，形式多样，这本身就是一个问题。当你创建了几十或上百个实体后，在未来的任何时候切换到另一个 ORM 都会变得困难。切换到另一个 ORM 可能有很多原因：也许另一个 ORM 提供了某个功能，或者你发现使用的 ORM 性能不佳，想要一个性能更好的。无论何种，切换到不同的 ORM 都需要大量的工作。

使用 O/RM 还有其他可能导致问题的后果。对于某些人来说，高层次的抽象可能使其难以理解幕后发生了什么。当你调用 `persist` 方法将实体插入数据库时，发生了什么？你只知道实体被插入到了表中，但这足够吗？你应该知道更多信息吗？

许多人对此有争议，在某种程度上他们是对的。在某种程度上，理解 O/RM 的工作原理很重要，因为显然没有理由去理解 O/RM 的内部机制。你始终可以使用 O/RM 进行负载测试以确保其性能足够，并且可以在数据库服务器上设置语句日志，以分析其生成的语句是否具有合格的质量。

此外，ORM 经常被认为是数据库设计决策不佳的原因，也许这是正确的。这重要吗？嗯，这取决于情况。如果你将数据库用于纯持久化存储以外的手段（例如数据仓库），那么架构设计至关重要。然而，如果你的数据库唯一目的是存储你的应用程序的数据，那么它仅仅是一种手段，仅此而已。只要它能运行且运行良好，并不一定意味着数据库表是不完美的。但这两个陈述都暗示了一个简单的事实：你创建了数据库。确实，许多 O/RM 可以根据你的映射指令生成表结构，但这绝对不应该在生产环境中使用。你应该始终自己创建表和列。如果你的数据库设计得糟糕，那是你的疏忽，而不是 O/RM 的错。

最后，只有你才能决定 O/RM 是否适用于你的用例，但在大多数情况下，利大于弊。

## JPA 提供了标准的 O/RM API

最早的 O/RM 之一是 TopLink，它为 Smalltalk 开发于 20 世纪 90 年代。The Object People（因此 TopLink 中有“Top”）在 1998 年发布了 Java 版 TopLink，Oracle 公司于 2002 年发布了适用于 Oracle Fusion Middleware 的 TopLink。在多年以及向 Sun Microsystems 最终向 Eclipse Foundation 捐代码的过程中，TopLink 变成了 EclipseLink（不过，TopLink 现在仍作为 Oracle 产品存在）。除了将对象映射到关系型数据库外，TopLink 和 EclipseLink 还可以将对象映射到 XML 文档。

另一个 ORM iBatis 起于 2002 年，作为 Apache 软件基金的项目一直持续到 2010 年退役，并被 Google Code 的 MyBatis 取代。iBATIS 为 Java、.NET 和 Ruby 编写，而 MyBatis 则为 Java 和 .NET 编写。Hibernate ORM 是最流行的 Java ORM 之一，始于 2001 年并不断演进。Hibernate 查询语言 (HQL) 解析了 SQL 查询，但它用于查询实体而不是表。NHibernate 是 Hibernate ORM 的 .NET 端口，为 .NET 引入了类似的功能。

拥有许多 ORM 的问题在于灵活性。例如，一个使用 Hibernate 的应用程序在不进行大量重构的情况下，无法更改为 EclipseLink 或 MyBatis。Java Persistence API（JPA）的创建是为了解决这个问题，并为使用 O/RM 技术的关系型数据库中的 Java 对象持久化提供一种标准 API。只有 Java Persistence API 允许你在需要时，以最小的精力切换 ORM 实现。

Sun 的 GlassFish 应用服务器包含了 JPA 1.0 的参考实现，该实现基于 Oracle 捐赠的 JPA 1.0 代码。Sun 将代码捐给了 Eclipse，TopLink 变成了 EclipseLink。尽管 Hibernate 极其受欢迎，但 EclipseLink 仍被选为 JPA 2.0 和 2.1 的参考实现。BaoJPA、DataNucleus、EclipseLink、Hibernate ORM、ObjectDB、OpenJPA、IBM WebSphere 和 Versant 只是 JPA 2.0 的提供者的一部分。在本文中，只有 EclipseLink、DataNucleus 和 Hibernate 发布了 JPA 2.1 的实现。

> JPA 实现使用 JDBC 执行 SQL 语句，但你永远不需要处理这些。你将始终使用 Java Persistence API，而不会直接使用 JDBC API。

## 为什么选择 Hibernate ORM？

在本书中，你将 Hibernate ORM 作为你示例项目的 JPA 实现。这看起来可能很奇怪，因为 Hibernate 并不是原始的 JPA/ORM，也不是 JPA 的参考实现——这两个称号都属于 EclipseLink。然而，Hibernate 是一个非常成熟稳定的项目，拥有庞大的社区支持和成千上万的教程文章。需要时，你可以轻松地使用 Hibernate，但 EclipseLink 的全局知识库并没有那么详尽（Hibernate 也是作者所熟悉的工具）。

Hibernate ORM 还支持集合的懒加载，而无需操作实体的字节码。相比之下，EclipseLink 必须将字节码装饰织入你的实体中来实现这一点，而且配置起来可能很复杂。好消息是，你不需要因为本书用了它就必须使用 Hibernate。你将使用 Java Persistence API，因此可以根据需要随时切换到不同的 JPA 实现。

## Hibernate ORM 简述

接下来的几章节将重点关注如何使用 Java Persistence API 在你的应用程序中持久化实体。你不会直接使用实现者（Hibernate ORM）API。事实上，你在本书中使用的提供者库在 Maven 中具有运行时作用域，阻止了你直接使用它们。然而，如前节所述，有时必须使用提供者 API。尽管 JPA 标准的持续改进使得这种情况越来越不像，但你仍然需要理解你使用的库。因此，本节将向你介绍 Hibernate ORM 以及它如何在 JPA 范围之外工作。

## 使用 Hibernate 映射文件

回想映射部分，在使用 O/RM 持久化实体之前，你必须首先定义该实体字段到相应关系数据库列的映射。当你使用 JPA 进行此操作时，始终使用注解来映射实体。在 Hibernate ORM 3.0 到 3.5 之间，你可以使用模仿 JPA 注解的 Hibernate 专有注解，通过独立的 Hibernate Annotations 项目来映射实体。从 Hibernate ORM 3.5 开始，这些专有注解已封装在 Hibernate 核心库中，并且 Hibernate 也支持了 JPA 注解。在 Hibernate 3.0 之前，你需要使用使用 Hibernate Mapping XML 架构的 XML 映射文件。这些文件的扩展名为 `.hbm.xml`，包含了告诉 Hibernate 如何保存实体以及从关系数据库中检索实体的指令。如果你有偏好，仍然可以使用 XML 映射，但仅限在你直接使用 Hibernate ORM 而不使用 JPA 的情况下。

Hibernate 映射文件始终包含 `<hibernate-mapping>` 根元素。在此内部，一个或多个 `<class>` 元素指出了根据类名及其映射的表所给出的多个映射。虽然可以通过使用多个 `<class>` 元素在单个文件中包含多个映射，但最佳实践是每个实体使用一个文件，文件名与类名相同。例如，类 `Product` 的映射文件将是 `Product.hbm.xml`。通常的做法是将映射文件与你的实体类一起放在包结构中（resources 目录），因此，`com.wrox.entities.Product` 的映射文件将是 `com/wrox/entities/Product.hbm.xml`。

在 `<class>` 元素中，`<id>` 元素指定了一个单列、单字段的代理键，而互斥的 `<composite-id>` 指定了多列、多字段的代理键。或者一个或多个 `<property>` 元素将字段映射到数据库列。对于大多数用例，映射可以使用 `<property>` 的属性完全表示，但对于更复杂的情况，你可能需要使用 `<column>` 元素。

> 你可能已经注意到了这一节关于将“字段”映射到数据库列的内容。在这种情况下，“字段”一词指的是 Java 属性（带有访问器和变器的实例字段）。在 JPA 和 Hibernate ORM 中，所有映射的字段默认都是 JavaBean 属性（然而，你可以指定不同的行为）。字段名通过从 getter 方法中删除 "get" 或 "is" 并将第一个字符转换为小写来确定（字段名不是通过检查底层实例字段来确定的）。与它被称为“字段”时听起来可能相反，JPA 和 Hibernate 实体字段不需要底层的实例字段。匹配的 getter 和 setter 就足以使其成为一个实体。

如果你继续当前的示例，为 `Product` 类创建映射非常简单：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hibernate-mapping PUBLIC "-//Hibernate//Hibernate Mapping DTD 3.0//EN"
"http://www.hibernate.org/dtd/hibernate-mapping-3.0.dtd">
<hibernate-mapping>
  <class name="com.wrox.entities.Product" table="Product" schema="dbo">
    <id name="id" column="ProductId" type="long" saved-value="0">
      <generator class="identity" />
    </id>
    <property name="name" column="Name" type="string" />
    <property name="description" column="Description" type="string" />
    <property name="datePosted" column="DatePosted" type="string" />
  </class>
</hibernate-mapping>
```

大部分内容应该是显而易懂的。在 SQL Server 中使用 identity，在 MySQL 中使用 Auto_INCREMENT，以此类推。Hibernate ORM 用户手册中有几十页的映射示例和说明。由于你只使用映射，这里涵盖了这些。

## 理解 Session



在 Hibernate 中工作的单元是 `org.hibernate.Session` 接口。Hibernate Session 类似于 HttpSession 或 WebSocket Session。Hibernate Session 代表从开始到结束的事务生命周期。取决于你的应用程序架构，这可能持续几秒钟或几分钟；在 Web 应用程序中，可能是跨越多个请求的事务。Session 不是线程安全的，必须一次在一个线程中使用，它负责管理实体的状态。

当实体从数据库检索时，它会被附加到 Session 中，并在 Session（及其事务）结束之前保持属于 Session。这样，实体的某些属性在 Session 生命周期内以懒加载的方式加载。同样，当实体被添加或更新时，这些更改也会附加到 Session；当实体从数据库被删除时，它会从 Session 中移除。这与 JPA 的 EntityManager 工作方式非常相似。你稍会学习。

使用 Session 实例的 `get` 方法查找实体非常简单：

```java
return (Product) session.get(Product.class, id);
```

如果指定的产品不存在，它将返回 `null`。要添加新实体，将其传递给 `save` 方法。

```java
session.save(product);
```

该方法返回被添加实体的生成的 ID；尽管你通常不需要使用返回值。调用之后，你传递给方法的 ID 属性将更新为生成的 ID。`persist` 是另一种替代方案，它也添加新实体。关键区别是 `persist` 更安全：如果事务已经关闭，它不会导致 INSERT，而 `save` 会导致事务外的插入。

因此，`persist` 通常是首选方法。然而，`persist` 触发的 INSERT 并不保证在 `flush` 之前执行，因此 `persist` 不返回生成的 ID，且当 `persist` 完成时实体的 ID 属性可能尚未设置。如果你立即需要 ID，应该在保存实体后刷新 Session：

```java
session.persist(product);
session.flush();
```

刷新（Flush）Session 仅仅会导致任何待处理的语句立即执行；它不会结束事务。因此，你可以在 Session 的生命周期内根据需要调用多次 `flush`。关闭 Session 或提交其事务会自动刷新 Session。刷新 Session 的原理源于 Hibernate 查询它们的方式。在涉及多个实体的事务中，操作的执行顺序并不是按照你指定的顺序执行的。在 `flush` 期间，自上次 `flush` 之后的所有操作将按照以下顺序执行：

- 按照添加顺序执行所有实体插入
- 按照更新顺序执行所有实体更新
- 按照删除顺序执行所有集合删除
- 按照执行顺序执行所有集合插入、更新和删除
- 按照添加顺序执行所有集合插入
- 按照删除顺序执行所有实体删除

因此，如果你需要保证某个操作在其他操作之前执行，你必须在它们之间调用 `flush`。唯一的例外是 `save`，无论是否刷新，它总是立即执行 INSERT。（但请记住，`persist` 会受到 `flush` 的影响。）

> 警告：这仅影响 Session 写入数据库的操作。你对 Session 所做的更改会立即反映在内存中。请小心这种行为，因为它可能是许多混乱的根源。

更新实体的理解起来有点复杂。你可以像下面的代码段一样使用 `update` 方法：

```java
session.update(product);
```

然而，这只有在实体尚未关联到 Session 时（即你没有在事务期间对该实体进行 `get`、`save` 或 `persist`）才有效。如果实体已经关联，`update` 将抛出异常。正因如此，几乎总是使用 `merge` 方法是最好的，无论实体是否已经关联到 Session，它都能工作：

```java
session.merge(product);
```

删除实体非常直接：

```java
session.delete(product);
```

# 556 | 第 19 章 介绍 JAVA 持久化 API 和 HIBERNATE ORM

实体剔除（Entity eviction）是 Hibernate 中一个有趣的概念。调用 `evict` 方法会导致实体从 Session 中解离，但它不会像删除实体那样对数据库产生任何更改。

```java
session.evict(product);
```

如果你想剔除所有关联到 session 的实体，可以调用 `clear` 方法。注意，`evict` 会取消被剔除实体的任何尚未刷新的待处理更改。同样，`clear` 会取消 Session 中所有实体的尚未刷新的待处理更改（包括插入和删除）。

使用代理键获取单个实体并不是你需要执行的唯一查询类型。你可能希望使用 `criteria` 查询单个实体和实体集合。你可以使用 `org.hibernate.Criteria` API 或 `org.hibernate.Query` API 来执行这两项任务。以下两个返回语句产生完全相同的实体：

```java
return (Product) session.createCriteria(Product.class)
    .add(Restrictions.eq("sku", sku))
    .uniqueResult();
```

```java
return (Product) session.createQuery("FROM Product p WHERE p.sku = :sku")
    .setString("sku", sku)
    .uniqueResult();
```

注意，在 HQL 查询中引用的是实体名称，而不是表名，且 `sku` 指的是实体的 `sku` 属性，而不是数据库表中的 `sku` 字段。同样，以下两个返回语句都会返回一个一年前发布的、以 "java" 开头的 Product 列表：

```java
return (List<Product>) session.createCriteria(Product.class)
    .add(Restrictions.gt("datePosted",
        Instant.now().minus(365, ChronoUnit.DAYS)))
    .add(Restrictions.like("name", "java", MatchMode.START))
    .addOrder()
    .list();
```

```java
return (List<Product>) session.createQuery("FROM Product p WHERE
datePosted > :oneYearAgo AND name LIKE :nameLike% ORDER by name")
    .setParameter("oneYearAgo",
        Instant.now().minus(365, ChronoUnit.DAYS))
    .setString("nameLike", "*java%%%")
    .list();
```

使用 Session API 还可以很多其他事情，但这些基础任务应该能满足你的所有需求。

# 从 SessionFactory 获取 Session

Session 并不是凭空出现的。Session 与 JDBC 数据库连接关联，在使用它之前，必须由某些东西创建连接或从 DataSource 检索它、实例化 Session 实现类，并将 Session 关联到连接上。如果当前上下文中已经进行中一个 Session，则有必要“查找”现有的 Session，而不是每次需要执行操作时都创建一个 Session。

# 简述 Hibernate ORM

`org.hibernate.SessionFactory` 接口的存在正是为了此目的。它包含了几个用于构建 Session、打开 Session 以及获取“当前”Session的方法。例如，要打开一个新的 Session，可以调用 `openSession` 方法：

```java
Session session = sessionFactory.openSession();
```

这会打开一个带有为 SessionFactory 配置的所有所有默认设置（数据源、拦截器等）的 Session。然而，有时有必要重写这些设置。例如，你可能需要指定：

```java
Session session = sessionFactory.openSession();
```

或者你可能需要指定：

```java
Session session = sessionFactory.openSession();
```

Hibernate ORM 还有无状态会（stateless sessions），特别适用于批量操作，但它不像 Session 那样持有关联的实体。你可以打开一个默认 Session。SessionFactory 最重要的功能之一是它持有和检索“当前”Session的能力。

```java
Session session = sessionFactory.openSession();
```

但到底什么是“当前 Session”呢？与 Session 不同，SessionFactory 是线程安全的，因此“当前”Session是由提供的 `org.hibernate.context.SessionContext` 实现类定义的。最常见的实现是 `org.hibernate.context.ThreadLocal`，它将当前会存储在线程中。

```java
Session session = sessionFactory.getCurrentSession();
```

# 使用 Spring Framework 创建 SessionFactory

SessionFactory 的配置可能很复杂，在 Web 应用中，在每个请求结束时正确清理资源至关重要。如果不这样做可能会导致内存泄漏或更糟糕的跨应用程序数据泄露。与许多其他事情一样，Spring 替你创建一个 Factory 并管理 Session 和事务的创建与关闭，这样你就不需要担心重复代码。在 Spring 中配置 Hibernate ORM 时，你使用两个 Spring 类之一来创建 SessionFactory。

如果你使用 XML 配置 Spring，最简单的方法是定义 `org.springframework.orm.hibernate4.LocalSessionFactoryBean`，这是一种创建并返回 SessionFactory 的特殊 Spring Bean。LocalSessionFactoryBean 还实现了 `org.springframework.orm.dao.PersistenceExceptionTranslator`，因此它可以作为将 Hibernate ORM 异常转换为 Spring 通用持久化异常的翻译器。

使用 Java 配置时，`org.springframework.orm.hibernate4.LocalSessionFactoryBuilder` 是一种更简单的方法。它扩展了 `org.hibernate.cfg.Configuration`，为在 Spring Framework 应用程序中配置 SessionFactory 提供了一些快捷方式。如下面的 Java 配置代码段所示：

通过此配置，Spring Framework 可以在调用 `@org.springframework.transaction.annotation.Transactional` 服务或存储库方法之前自动创建一个 Session，并在方法返回后关闭该 Session。如果一个 `@Transactional` 方法调用了其他 `@Transactional` 方法，当前的 Session 和事务将保持有效。此时，你需要在存储库中仅使用 `@Injected` 的 SessionFactory，并在任何需要使用 Session 时使用 `getCurrentSession()`。你将在第 21 节中学习更多关于 `@EnableTransactionManagement` 和 `@Transactional` 的知识。

## 准备关系型数据库

为了完成并使用本书中其余部分的示例和样例项目，你需要访问一个用于持久化实体的关系型数据库。你可以使用像 HyperSQL 这样 100% Java 的嵌入式数据库，但这违背了替换你到目前为止在书中使用的内存存储库的初衷。相反，如果你使用独立的、单独的关系型数据库（如 MySQL、PostgreSQL 或 Microsoft Server），示例将更加有效。

书中的示例假设你有访问关系型数据库的权限；如果没有，则需要安装一个。此外，示例是针对 MySQL 服务器编写并针对其进行测试的，因为它是目前最流行的免费数据库系统。然而，没有任何理由你不能使用任何关系型数据库来完成示例。大多数代码都独立于任何特定数据库（毕竟，这是 ORM 的意义之一），但在使用整个示例中展示的配置代码时，你需要具备一些独立思考。例如，每当你看到某些特定数据库的内容时（如上一节使用的 `MySQL5innodbialect` 类），你需要为你自己选择的数据库找到合适的替代方案。你还需要将 MySQL 的数据库、表和索引创建语句翻译为你选择数据库的相应语句。

除了展示如何在 Tomcat 中安装 JDBC 驱动程序和创建连接资源外，本节还帮助你安装 MySQL 服务器，以防你还没有喜欢的数据库的访问权限。如果你计划使用其他数据库，仍然应该阅读本节！它包含了适用于你数据库供应商的重要信息。

## 安装 MySQL 和 MySQL Workbench

要安装 MySQL 数据库，请按照以下步骤操作：

- 访问 MySQL 下载网站，下载 MySQL Community Server 和 MySQL Workbench 产品。
- 对于 MySQL Community Server，选择合适的平台（Mac OS X、Windows、SUSE 等），并下载你的平台版本下载下载的安装程序或压缩包。
- 按照你操作系统的安装说明，在你的计算机上安装 MySQL Community Server。安装程序将引导你完成整个过程。
- 如果出现 Setup 类型，你通常可以选择 Developer Default（开发人员默认），如图 19-1 所示。这将安装你使用 MySQL 开发所需的所有内容，包括在 Windows 系统上所需的 Microsoft Excel 扩展。如果你只想安装某些功能，请选择 Custom（自定义）设置类型，并在屏幕上选择你想要安装的功能，如图 19-2 所示。

> 注意：许多发行版在它们的包管理系统中提供了 MySQL，使用该方法安装 MySQL 可能更简单。无论你如何安装，都必须使用 MySQL 5.6.12 或更高版本——早期版本不支持后续章节中使用的某些功能。从 MySQL 网站下载时，你不需要创建账户或登录。你可以点击“No thanks, just start my download”链接跳过此过程。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_595_0.png)

图 19-1

## 准备关系型数据库

![](img/9c2d45f6d547f72cb870b3a991f62ef6_596_0.png)

图 19-2

MySQL Workbench 是一个数据库浏览器和管理工具，类似于 Microsoft SQL Server Management Studio 和 Oracle SQL Developer。书中某些示例和界面将告诉你如何对你的 MySQL 数据库执行查询，并向你展示结果在 Workbench 中应该的样子。当然，你可以任何你喜欢的工具来执行这些任务。如果你运行了 MySQL 服务器的安装程序并安装了 Workbench，你不需要再进行任何操作来安装 Workbench。否则，要下载并安装 Workbench，你应该选择合适的平台并下载适用于你平台版本的正确安装程序或二进制文件。安装 Workbench 比安装 MySQL Community Server 过程简单，且 Workbench 通常在标准的包管理仓库中找不到。

在大多数情况下，你的 MySQL Community Server 在安装后就准备就绪了。为了开发，它不需要额外的配置；但在其默认配置下，它没有针对性能进行优化，也不安全。默认配置足以用于运行示例并执行书中详细列的任务。但是，你需要创建一个你的应用程序可以通过 JDBC 访问数据库时使用的用户名和密码。

> 注意：管理 MySQL Community Server 的细节超出了本书的范围，但 MySQL 网站有大量资源可以帮助你进行配置以满足你的需求。

562 | 第 19 节 引入 Java 持久化 API 和 Hibernate ORM

要创建此用户名和密码，请打开 MySQL Workbench 并连接到你的本地 MySQL 安装。你需要输入 root 用户名和密码进行登录；如果你在安装期间没有设置 root 密码，则 root 密码默认为空。

在查询编辑器中，输入以下语句并点击执行图标来执行它们：

```sql
GRANT ALL PRIVILEGES ON.* TO 'tomcatUser'@'localhost' IDENTIFIED BY 'password234';
GRANT ALL PRIVILEGES ON.* TO 'tomcatUser'@'127.0.0.1' IDENTIFIED BY 'password234';
GRANT ALL PRIVILEGES ON.* TO 'tomcatUser'@':1' IDENTIFIED BY 'password234';
FLUSH PRIVILEGES;
```

这创建了一个可以从机器上的 Tomcat 连接的用户。当然，该用户被授予了许多权限。在生产机器上，你会希望将其限制在一个数据库，并仅允许数据操作。对于开发机器，这足够了。

## 安装 MySQL JDBC 驱动程序



# MySQL 与 JDBC 驱动程序

MySQL 与其他供应商一样，使用 JDBC 驱动程序从 Java 连接到 MySQL。你需要下载此驱动程序（一个 JAR 文件）并将其放在你的 Tomcat 安装中，以便应用程序可以使用它。这可能让你感到奇怪，因为其他 JAR 文件是直接放在应用程序的 `/WEB-INF/lib` 中的。你绝不能对 JDBC 驱动程序这样做，原因有两个：

- 最重要的是，这样做会导致内存泄漏。JDBC 驱动程序会自动注册到 `java.sql.DriverManager`，它是 Java SE 核心库的一部分。如果你的应用程序在 `/WEB-INF/lib` 使用 JDBC 驱动程序，即使应用程序被卸载，`DriverManager` 一直持有这些驱动类。这样应用程序服务器无法完全卸载你的应用程序，导致内存泄漏。

- 让应用程序服务器管理 JDBC DataSource 是最佳实践。应用程序服务器拥有内置的连接池管理系统，可以提高应用程序数据库连接的性能。为了让服务器能够管理这些连接，需要在加载器而不是 Web 类加载器中加载 JDBC 驱动程序。

## 在 Tomcat 中安装 MySQL JDBC 驱动程序

在 Tomcat 中安装 MySQL JDBC 驱动程序非常简单。在之前提到的 MySQL 网站上，找到 Connector/J 项目。这就是 JDBC 驱动程序。它是平台无关的，你只需要下载 ZIP 或 TAR 压缩包（取决于哪种方便你使用）。从压缩包中提取 JAR 文件，并将其复制到 `C:\Program Files\Apache Software Foundation\Tomcat 8.0\lib`（或你 Tomcat 安装的相应目录）。

就是这样了。下次 Tomcat 启动时，MySQL JDBC 驱动程序对所有 Web 应用程序可用。

## 关于 Maven 依赖的说明

> **警告** 截至写作时，MySQL JDBC 驱动程序主要兼容 JDBC 4.1（它是 Java 7 的一部分）。Java 8 包含了 JDBC 4.2。JDBC 4.2 的唯一重大变化是为 SQL DATE、TIME 和 DATETIME 类型添加了 Java 8 日期和时间类型。MySQL 驱动程序尚未兼容 JDBC 4.2，你无法在 JDBC 语句和结果集中直接使用 Java 8 日期和时间类型——JDBC 供应商通常在新 Java/JDBC 版本发布 6 个月到若干年后才会发布新版本的驱动程序，或者可能不发布。当你读到这里时，MySQL 驱动可能已经符合 JDBC 4.2 标准。请确保下载最新版本并咨询 Connector/J 文档以查看其是否符合 JDBC 4.2。此警告提示也适用于你使用的其他 JDBC 驱动程序。

# 在 Tomcat 中创建连接资源

在 Tomcat 中创建池化的 DataSource 非常简单，只需几分钟时间。当你为示例或样例项目使用新数据库时，本书将指示你创建一个 Tomcat 连接资源。你可能需要经常回顾此章节以记住如何操作。与其每次都创建一个新资源导致书籍结束时有几十个资源，创建一个资源并在每次需要时更改它也是可以的。

1. 要创建连接资源，请用你喜欢的文本编辑器打开 `C:\Program Files\Apache Software Foundation\Tomcat 8.0\context\.xml`（或你 Tomcat 安装中的对应文件）。

2. 在起始元素和 `<Context>` 元素之间添加以下 `<Resource>` 元素：

```xml
<Resource name="jdbc/DataSource" type="java.sql.DataSource"
    maxActive="20" maxIdle="5" maxWait="10000"
    username="mysqluser" password="mysqlpassword"
    driverClassName="com.mysql.jdbc.Driver"
    url="jdbc://localhost:3306/databaseName" />
```

3. 对于每个示例，将 `jdbc/DataSource` 替换为适当的数据源名称（应始终以 `jdbc/` 开头），并将 `databaseName` 替换为正确的数据库名称。`mysqluser` 和 `mysqlpassword` 应该替换为你之前为 Tomcat 访问 MySQL 时创建的用户（`tomcatUser`）和密码（`password1234`）。你可以在此书的所有示例中复用此用户名和密码。

此 `<Resource>` 定义使 Tomcat 将连接池 DataSource 暴露为 JNDI 资源，以便任何应用程序通过 JNDI 查找它。

# 关于 Maven 依赖的说明（续）

你在本书这部分使用的 Maven 依赖并不像你所习惯的那样简单。到目前为止你使用的大多数 EE 依赖都是来自 Maven 中央仓库的实际 Java EE 规范库，例如 `javax.servlet:servlet-api:3.1.0` 和 `javax.websocket:javax.websocket-api:1.1.0`。然而，其他 Java EE 组件具有不同的许可，禁止在 Maven 中央中进行二进制分发。

导致这种现象的法律荒谬性超出了本书的范围，但可以说 Maven 中央中没有针对 JPA 2.0 或 2.1 的“官方” `org.javax.persistence`（Java 持久化 API）构件。未来你可能在其他 Java EE 组件上遇到类似的情况。不过，这些 API 的实现都在 Maven 中央中发布了相同的非官方 API 构件，并且是安全的。在这种情况下，最佳实践是使用由参考实现发布的 API，因为它最可能是 100% 正确的。当你看到下一章中的 Maven 依赖时，请知道这是 EclipseLink 发布的 Java Persistence API 2.1 构件。它兼容任何 JPA 实现，包括 Hibernate ORM。

```xml
<dependency>
  <groupId>org.eclipse</groupId>
  <artifactId>org.javax.persistence</artifactId>
  <version>2.1.0</version>
  <scope>compile</scope>
</dependency>
```

Hibernate 也为 JPA 2.1 发布了 `org.hibernate.javax.persistence:hibernate-jpa-2.1-api:1.0.0` 构件，如果你愿意，也可以使用它。使用提供者发布的构件的唯一替代方案是从 Java 网站手动下载官方 JAR 包，但这对于 Maven 项目并不好用，而且并非必要。坦率地说，这对于 EE 组件来说是例外而非常态。

## 总结

本准备性章节向你介绍了对象关系映射器（O/RMs）和 Java 持久化 API（JPA）。它解释了这两者的历史和演变，并解释了使用 JPA 代替私有 O/RM API 的优点。你还对 JPA 之外的 Hibernate ORM 有简单介绍。然而，在本书的其余部分，你将只使用 JPA 类和接口。你学习了为了这些目的如何安装和设置 MySQL。最后，你学习了如何在 Tomcat 中安装 JDBC 驱动并配置 Tomcat 连接池 DataSource。

在接下来的章节中，你将使用 JPA 将各种实体持久化到关系型数据库中。你还将学习用于将实体映射到数据库表的不同技术，并探索如何以各种方式添加、更新、删除、读取和搜索实体。

# 使用 JPA 注解将实体映射到表

## 本章内容

- 理解并处理简单实体
- 设计和利用持久化单元
- 如何映射复杂数据类型

## 本章 WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/javaapps` 找到本章的 wrox.com 代码。你可以在以下项目中找到：

- Entity-Mappings 项目
- Enums-Libs 项目

## 本章的新 Maven 依赖

除了之前章节介绍的 Maven 依赖外，你还需要以下内容。排除持久化和 JBoss 事务是因为它们与标准存在冲突。XML API 被排除是因为它是 Java 7 的一部分。最后，排除 JBoss Logging 并非为了清晰度。

```xml
<dependency>
  <groupId>org.eclipse.persistence</groupId>
  <artifactId>javax.persistence</artifactId>
  <version>2.1.0</version>
  <scope>compile</scope>
</dependency>
```

## 开始简单实体

```xml
<dependency>
  <groupId>javax.transaction</groupId>
  <artifactId>transaction-api</artifactId>
  <version>1.2</version>
  <scope>compile</scope>
</dependency>

<dependency>
  <groupId>org.hibernate</groupId>
  <artifactId>entitymanager</artifactId>
  <version>4.3.Final</version>
  <scope>runtime</scope>
  <exclusions>
    <exclusion>
      <groupId>org.hibernate.javax.persistence</groupId>
      <artifactId>hibernate-jpa-2.1</artifactId>
    </exclusion>
    <exclusion>
      <groupId>org.jboss.spec</groupId>
      <artifactId>transaction-api_1.2_spec</artifactId>
    </exclusion>
    <exclusion>
      <groupId>javax.xml</groupId>
      <artifactId>xml-apis</artifactId>
    </exclusion>
    <exclusion>
      <groupId>org.jboss.logging</groupId>
      <artifactId>logging</artifactId>
    </exclusion>
  </exclusions>
</dependency>
```

## 基于注解的映射还是基于 XML 的映射？

你不需要在应用程序中映射实体。相反，你可以使用 `META-INF/orm.xml` 文件创建类似于 Hibernate ORM 映射的 XML 映射。如何创建基于注解和基于 XML 的映射将花费双倍的页数，这并不可行。注解是映射 JPA 实体最简单且首选的方法，因此本书仅涵盖这种技术。如果你对学习基于 XML 的映射感兴趣，映射元素及其属性与映射注解及其属性实际上是相同的。良好的 IDE（如 IntelliJ）可以根据 `orm.xml` XSD 提供代码提示。为了帮助你开始使用，一个空的 `orm.xml` 文件如下：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-mappings xmlns="http://xmlns.jcp.org/xml/ns/persistence/orm"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence/orm
    http://xmlns.jcp.org/xml/ns/persistence/orm_2_1.xsd"
    version="2.1">
</entity-mappings>
```

# 标记实体并将其映射到表

前两个最基础的 JPA 映射注解是 `@java.persistence.Entity` 和 `@java.persistence.Table`。`@Entity` 标记一个类以表示它是一个实体。每个实体都必须有一个注解。默认情况下，实体名称等于未限定限定的实体类名，因此以下 `com.wrox.site.entities.Author` 类的实体名称为 Author。

```java
@Entity
public class Author implements Serializable
{
    // ...
}
```

你可以通过在 `@Entity` 注解上指定 `name` 属性来自定义实体名称，例如 `com.wrox.site.entities.Publisher` 类。

```java
@Entity(name = "PublisherEntity")
public class Publisher implements Serializable
{
    // ...
}
```

实体映射的表默认使用实体名称。Author 的默认表名是 Author，Publisher 的默认表名是 PublisherEntity。你可以使用 `@Table` 注解的 `name` 属性来更改表名。

```java
@Entity
@Table(name = "Authors")
public class Author implements Serializable
{
    // ...
}
```

```java
@Entity(name = "PublisherEntity")
@Table(name = "Publishers")
public class Publisher implements Serializable
{
    // ...
}
```

现在，这两个类分别映射到 Authors 和 Publishers 表。你还可以使用该注解完成其他几项工作。例如，你可以使用 `schema` 属性来覆盖数据库连接的默认模式（假设你使用的数据库支持 schema）。你还可以使用 `catalog` 属性来指示表存在于数据库连接所选之外的目录（catalog）中。在 JDBC 和 JPA 中，“catalog”是数据库表集合的通用术语。大多数关系型数据库系统使用“database”这一术语。

`com.wrox.site.entities.Book` 实体演示了 `uniqueConstraints` 属性的使用。

```java
@Entity
@Table(name = "Books", uniqueConstraints = {
    @UniqueConstraint(name = "Books_ISBN", columnNames = {"isbn"})
})
public class Book implements Serializable
{
}
```

`uniqueConstraints` 是一个专门用于模式生成（schema generation）的特殊属性。JPA 者可以根据你的实体自动生成数据库模式，此属性允许你指定特定列或多个列应形成唯一约束。从 JPA 2.1 开始，你还可以使用该属性指定在进行模式生成时 JPA 应该创建的索引。

```java
@Entity
@Table(name = "Books", uniqueConstraints = {
    @UniqueConstraint(name = "Books_ISBNs", columnNames = {"isbn"})
},
indexes = {
    @Index(name = "Books_Titles", columnList = "title")
})
public class BookEntity implements Serializable
{}
```

```java
@Entity
@Table(name = "Authors", indexes = {
    @Index(name = "Authors_Names", columnList = "AuthorName")
})
public class Author implements Serializable
{}
```

```java
@Entity
@Table(name = "Publishers", indexes = {
    @Index(name = "Publishers_Names", columnList = "PublisherName")
})
public class Publisher implements Serializable
{}
```

当然，因为你只有在启用模式生成时才会使用 `uniqueConstraints` 和 `indexes`，所以你不需要指定模式生成是否危险（默认是禁用的）。

> **警告** 模式生成是一个危险的功能。虽然它对开发很有帮助，但绝不应在生产环境中使用。通过此过程生成的模式并不总是美观的，也不能保证是正确的。作为最佳实践，作者从不使用模式生成。开发过程还应该包括对你在生产环境中使用的模式的开发，以便其在产品成熟的所有阶段都经过充分测试。

# 指示 JPA 如何使用实体

默认情况下，JPA 访问实体字段的值，并使用实体的 JavaBean 访问器（getter）和 setter 方法将这些字段映射到数据库列。因此，实体中私有字段的名称和类型对 JPA 来说并不重要。相反，JPA 查看的是 JavaBean 属性访问器的名称和返回类型。你可以使用 `@javax.persistence.Access` 注解更改此，它允许你显式指定 JPA 应该采用的访问方法。

```java
@Entity
@Access(AccessType.FIELD)
public class SomeEntity implements Serializable
{
}
```

`AccessType` 枚举的可用选项有 `PROPERTY`（默认值）和 `FIELD`。使用 `PROPERTY` 时，提供者使用 JavaBean 属性方法获取和设置值。`FIELD` 则让提供者使用实例字段获取和设置值。作为最佳实践，除非有极充分的理由不要这样做，否则你应该坚持默认设置并使用 JavaBean。



其余的 JPA 注解大部分是属性注解。你将在本章的剩余部分中探索其中许多注解，例如 `@Id`、`@Basic`、`@Temporal` 等。从技术上讲，你既可以将这些注解放在字段上，也可以放在公共访问方法上。如果你使用 `AccessType.PROPERTY`（默认值）并注解属性而不是 JavaBean 访问器，字段名必须与 JavaBean 属性名匹配。然而，如果你使用 `AccessType.FIELD` 并注解字段，名称则不需要匹配。

> 警告 你不应该在同一个实体中混合使用 JavaBean 注解和 JPA 注解

# 映射代理键

在映射 JPA 实体时，你必须做的事情之一是创建代理键，称为主键或 ID。每个实体都应该有一个 ID，它可以是单个字段（对应单列）或多个字段（对应多列）。因此，你有多种方法处理 ID。

# 创建简单 ID

首先，你可以用 `@javax.persistence.Id` 标记任何 JavaBean 属性。此注解指示该属性（私有字段或公共方法）是实体的代理键。该属性可以是任何基本类型、包装类、`String`、`java.util.Date`、`java.sql.BigInteger` 或 `BigDecimal`。某些提供者可能会支持 Java 8 Date 其他类型；但目前这样做不具有移植性。

如果你的实体类没有 ID，JPA 提供者会查找名为 `id` 的属性（带有 `getId` 和 `setId`）并自动使用它。该属性也可以是基本类型、包装类、`String`、`java.util.Date`、`java.sql.BigInteger` 或 `BigDecimal`。

作为最佳实践，实体 ID（主键）通常应该是 `ints`、`longs`、`Integers`、`Longs` 或 `BigIntegers`。通常，使用 `int` 或 `long` 会限制你的表最多存储 2,147,483,647 个实体。`BigInteger` 处理起来比较复杂，且不会自动在基本类型和包装类之间转换，`String` 的索引和查找也比数字困难。在极少数情况下，`long` 或 `Long` 不适用于实体 ID，因此本书在演示其他实体 ID 类型外，一律使用 `long`。无论你如何操作，只要启用了模式生成，JPA 提供者会自动为 ID 创建主键约束。你不需要在 `@Table` 中指定唯一约束。

现在，你也可以创建一个手动生成并分配 ID 的实体。然而，这通常很少需要，因为这需要额外、重复且不需要的工作。通常，你希望实体 ID 以某种方式自动生成。你可以使用 `@javax.persistence.GeneratedValue` 注解来实现这一点。`@GeneratedValue` 允许你指定生成策略，并在必要时指定生成器名称。例如，`Book` 和 `Author` 实体 ID 使用 `@javax.persistence.GenerationType.IDENTITY`，指示数据库列 ID 存储并可以自动生成其值。

```java
@Entity
public class Book implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() {
        return this.id;
    }
}
```

```java
@Entity
public class Author implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() {
        return this.id;
    }
}
```

这与 MySQL 的 `AUTO_INCREMENT` 列、Microsoft SQL Server 和 Sybase 的 `IDENTITY` 列、PostgreSQL 的 `SERIAL` 和 `DEFAULT NEXTVAL()` 列兼容。你不能使用不支持自动生成列值的 `GenerationType.IDENTITY` 数据库，但所有常见的关系型数据库都支持。

至少，在任何支持插入前触发器（before-insert triggers）的数据库中，你可以使用触发器为列生成值（Oracle 数据库使用序列的常用技术），这样该列就可以与 `GenerationType.IDENTITY` 兼容。不过，你可以使用其他生成器，而无需采用触发器和技巧来实现这一目标。由于 Oracle 和 PostgreSQL 等许多数据库支持序列，你可以使用 `@GeneratedValue` 结合 `@javax.persistence.SequenceGenerator` 来告诉 JPA 供应商程序使用序列生成值。

```java
@Entity
public class SomeEntity implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE,
                   generator = "SomeEntityGenerator",
                   sequenceName = "SomeEntitySequence")
    public long getId() {
        return this.id;
    }
}
```

`@GeneratedValue` 的 `generator` 属性对应 `@SequenceGenerator` 的 `name` 属性，且生成器名称是全局的。这意味着你可以在一个实体上创建一个 `@SequenceGenerator` 并在多个实体上复用它。（不过，你也可以为每个实体使用独立的序列。）

```java
@Entity
public class SomeEntity implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE,
      generator = "GlobalGenerator")
    @SequenceGenerator(name = "GlobalGenerator", sequenceName = "GlobalSequence",
      allocationSize = 1)
    public long getId() {
      return this.id;
    }
}
```

```java
@Entity
public class AnotherEntity implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE,
      generator = "GlobalGenerator")
    public long getId() {
      return this.id;
    }
}
```

或者，你可以在 `orm.xml` 中用 `<sequence-generator>` 元素创建一个多个实体共享的生成器。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-mappings xmlns="http://xmlns.jpa.org/ns/persistence/orm"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:schemaLocation="http://xmlns.jpa.org/ns/persistence/orm orm_2_1.xsd"
      version="2.1">
    <sequence-generator name="GlobalGenerator" sequence-name="GlobalSequence"
      allocation-size="1" />
</entity-mappings>
```

```java
@Entity
public class SomeEntity implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE,
      generator = "GlobalGenerator")
    public long getId() {
      return this.id;
    }
}
```

```java
@Entity
public class AnotherEntity implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE,
      generator = "GlobalGenerator")
    public Long getId() { return this.id; }
}
```

## 开始使用简单实体

使用 `@SequenceGenerator`（或 `<sequence-generator>`），你可以指定序列所属的 `schema` 和 `catalog` 属性。如果你启用了 JPA 生成功能，还可以使用 `initialValue`(`initial-value`) 和 `allocationSize`(`allocation-size`) 来指定序列的初始值，并指定每次插入操作时的增量大小。`initialValue` 默认值为 0，`allocationSize` 默认值为 50。

你还可以使用 `@Table.TableGenerator`（如 `Publisher` 所示），使用单独的表作为数据库序列。与 `@SequenceGenerator` 类似，你可以创建一个被多个实体共享的 `@TableGenerator`（或 `<table-generator>`）。`@TableGenerator` 具有 `@SequenceGenerator` 相同的 `name`、`schema`、`catalog`、`initialValue` 和 `allocationSize` 属性，具有相同的用途和默认值。它的其他属性如下：

- `table` 指明数据库表的名称。
- `pkColumnName` 指明生成器主键列的名称。
- `pkColumnValue` 指明该生成器主键列的值。
- `valueColumnName` 指明值列的名称。

在插入记录之前，供应商从序列表中为给定的 `pkColumnValue` 选择值，增加该记录的值，然后将该值作为被插入记录的主键。

```java
public class Publisher implements Serializable {
    @Id
    @GeneratedValue(strategy = GenerationType.TABLE,
    generator = "PublisherGenerator")
    @TableGenerator(name = "TableName", table = "SurrogateKeys",
    pkColumnName = "TableName", pkColumnValue = "Publishers",
    valueColumnName = "KeyValue", initialValue = 11923,
    allocationSize = 1)
    public Long getId() {
        return this.id;
    }
}
```

规范并未强制 `table`、`pkColumnName`、`pkColumnValue`、`valueColumnName` 的默认值，它们在不同供应商之间可能会有所不同。例如，供应商使用 `name`。如果你愿意，可以使用 `@GeneratedValue(strategy = GenerationType.TABLE)`。

## 创建复合 ID

`@IdClass` 解决方案可能因为类中的重复属性而显得有些笨拙，这确实是一个合理的顾虑。`@Id` 和 `@IdClass` 的替代方案是使用 `@javax.persistence.EmbeddedId` 配合 `@Embedded` 将复合 ID 嵌入为 ID 类。

```java
@Embeddable
public class JoinTableCompositeId implements Serializable {
    private long fooTableSk;
    private long barTableSk;

    public long getFooTableSk() { ... }
    public void setFooTableSk(long fooTableSk) { ... }

    public long getBarTableSk() { ... }
    public void setBarTableSk(long barTableSk) { ... }
}
```

```java
@Entity
@Table(name = "SomeTable")
public class JoinTableEntity implements Serializable {
    @EmbeddedId
    private JoinTableCompositeId id;

    public JoinTableCompositeId getId() { ... }
    public void setId(JoinTableCompositeId id) { ... }
}
```

# 使用基本数据类型

为了简化你的工作，JPA 会自动映射某些数据类型，而无需你提供任何指令。如果在实体（或使用 `AccessType.FIELD` 的字段）上发现具有以下类型的属性，它们将被自动映射为对应标准 SQL 数据类型的基本属性。某些提供程序还会将这些基本类型转换为其他 SQL 数据类型。

- `short` 和 `Short` 类型的属性映射到 `SMALLINT`、`INTEGER`、`BIGINT` 或等字段。
- `int` 和 `Integer` 属性映射到 `INTEGER`、`BIGINT` 或等 SQL 数据类型。`long`、`Long` 和 `BigInteger` 属性映射到 `BIGINT` 或等字段。
- `float`、`Float`、`double`、`Double` 和 `BigDecimal` 类型的属性映射到 `DECIMAL` 或等 SQL 数据类型。
- `byte` 和 `Byte` 属性映射到 `BINARY`、`SMALLINT`、`INTEGER` 或等字段。
- `char` 和 `Char` 类型的属性映射到 `CHAR`、`VARCHAR`、`BINARY`、`SMALLINT`、`INTEGER`、`BIGINT` 或等字段。
- `boolean` 和 `Boolean` 类型的属性映射到 `BOOLEAN`、`BIT`、`SMALLINT`、`INTEGER`、`BIGINT` 或等字段。
- `byte[]` 和 `Byte[]` 映射到 `BINARY`、`VARBINARY` 或等 SQL 数据类型。
- `char[]`、`Character[]` 和 `String` 属性映射到 `CHAR`、`VARCHAR`、`BINARY`、`VARBINARY` 或等 SQL 数据类型。
- `java.util.Date` 和 `Calendar` 类型的属性映射到 `DATETIME`、`TIME`，但你必须使用 `@Temporal` 使用额外的指令。在“映射复杂数据类型”章节，你将学习这一点以及如何更好地控制这些值的存储。
- `java.sql.Timestamp` 类型的属性始终映射到 `DATETIME` 字段。
- `java.sql.Date` 类型的属性始终映射到 `DATE` 字段。
- `java.sql.Time` 类型的属性始终映射到 `TIME` 字段。
- 枚举（Enum）属性映射到 `SMALLINT`、`INTEGER`、`BIGINT`、`CHAR`、`VARCHAR` 或等字段。默认情况下，枚举以其顺序（ordinal）格式存储，但你可以使用 `@Enumerated` 更改此行为。你可以在“映射复杂数据类型”部分进一步探索这一点。

如果你想更显式地指示一个字段已映射，可以使用 `@Basic` 对其进行注解。所有的数据类型限制都适用于 `@Basic` 属性和字段。你还可以使用该注解的 `fetch` 属性来指示属性的值是从数据库中尽早获取的（`javax.persistence.FetchType.EAGER`，未指定时的默认值）还是仅在访问时获取的（`FetchType.LAZY`）。

尽早加载（Eager fetching）意味着在从数据库获取实体的同时从数据库中获取该值。这可能涉及或不涉及额外的 SQL 语句，取决于该字段是否位于不同的表中。懒加载（Lazy fetching）导致提供程序只在访问字段时才获取值——在初始获取实体时不会获取值。未指定 `fetch` 属性（或指定 `FetchType.EAGER`）是提供程序提前获取值的要求。然而，指定 `FetchType.LAZY` 只是一个懒性获取值的提示。提供程序可能不支持懒加载并仍会提前获取值。因此，在依赖此功能之前，你应该考虑你所用提供程序的文档。你将在第 24 章学习更多关于加载的内容。

最后，你可以使用 `@Basic` 的 `optional` 属性指示该属性可能为 null。（这只是一个提示，对模式生成很有用）。对于基本类型这会被忽略，因为基本类型永远不会为 null。列表 20-1 中的预约实体演示了 `@Basic` 的用法。

# 列表 20-1：Book.java



```java
@Entity
@Table(name = "Books", uniqueConstraints = {
    @UniqueConstraint(name = "Books_ISBNs", columnNames = { "isbn"})
},
indexes = {
    @Index(name = "Books_Titles", columnList = "title")
})
public class Book implements Serializable {
    private long id;
    private String isbn;
    private String title;
    private String author;
    private double price;
    private String publisher;

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() {
        return this.id;
    }

    public void setId(long id) {
        this.id = id;
    }

    @Basic(optional = false)
    public String getIsbn() {
        return this.isbn;
    }

    public void setIsbn(String isbn) {
        this.isbn = isbn;
    }

    @Basic(optional = false)
    public String getTitle()
    {
        return this.title;
    }

    public void setTitle(String title)
    {
        this.title = title;
    }

    @Basic(optional = false)
    public String getAuthor()
    {
        return this.author;
    }

    public void setAuthor(String author)
    {
        this.author = author;
    }

    @Basic
    public double getPrice()
    {
        return this.price;
    }

    public void setPrice(double price)
    {
        this.price = price;
    }

    @Basic(optional = false)
    public String getPublisher()
    {
        return this.publisher;
    }

    public void setPublisher(String publisher)
    {
        this.publisher = publisher;
    }
}
```

# 指定列名和其他细节

默认情况下，JPA 将实体属性映射到相同的名称。参考列表 20-1 中的 `Book` 实体，`isbn`、`title`、`author`、`price` 和 `publisher` 是自动映射的。`@Column` 注解允许你自定义列名并精调属性的持久化方式。`name` 属性指定属性所在的数据库列，默认为表中。`insertable` 和 `updatable` 布尔值分别指示是否可以插入和更新，它们都默认为 `true`。其余 `@Column` 属性用于模式生成。`nullable` 指定列是否可以为 NULL，默认为 `false`。`length` 属性用于 `VARBINARY` 和 `VARCHAR`，指示列的长度，默认为255。`scale` 和 `precision` 属性均默认为0，指示小数列的标度（小数点前的位数）和精度（位数）。你必须为小数列提供非零的精度值。`columnDefinition` 提供了一种指定生成列的实际 SQL 方法。如果你使用它，可能无法跨数据库迁移。完成的实体演示了其属性的 `@Column`。列表 20-3 中的 `Publisher` 还演示了模式生成属性，除非启用了模式生成，否则它会被忽略。

# 列表 20-2：Author.java

```java
@Entity
@Table(name = "Authors", indexes = {
    @Index(name = "Authors_Names", columnList = "AuthorName")
})
public class Author implements Serializable {
    private long id;
    private String name;
    private String emailAddress;

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @Column(name = "AuthorId")
    public long getId() {
        return this.id;
    }

    public void setId(long id) {
        this.id = id;
    }

    @Column(name = "AuthorName")
    public String getName() {
        return this.name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Basic
    public String getEmailAddress() {
        return this.emailAddress;
    }

    public void setEmailAddress(String emailAddress) {
        this.emailAddress = emailAddress;
    }
}
```

# 列表 20-3：Publisher.java

```java
@Entity(name = "PublisherEntity")
@Table(name = "Publishers", indexes = {
    @Index(name = "Publishers_Names", columnList = "PublisherName")
})
public class Publisher implements Serializable
{
    private long id;
    private String name;
    private String address;

    @Id
    @GeneratedValue(strategy = GenerationType.TABLE, generator = "SurrogateGenerator")
    @TableGenerator(name = "SurrogateGenerator", table = "SurrogateKeys", pkColumnName = "TableName", pkColumnValue = "Publishers", valueColumnName = "KeyValue", initialValue = 11923,
    allocationSize = 1)
    @Column(name = "PublisherId")
    public long getId()
    {
        return this.id;
    }
    public void setId(long id)
    {
        this.id = id;
    }
    @Basic
    @Column(name = "PublisherName", nullable = false)
    public String getName()
    {
        return this.name;
    }
    public void setName(String name)
    {
        this.name = name;
    }
    @Basic
    @Column(nullable = false)
    public String getAddress()
    {
        return this.address;
    }
    public void setAddress(String address)
    {
        this.address = address;
    }
}
```

# 创建和使用持久化单元

现在你已经创建并映射了一些实体，你已经准备就绪使用这些实体了。你仍然需要创建数据库表并配置 JPA 提供者，然后你就可以使用使用持久化 API 的代码来持久化和检索你的实体。

# 设计数据库表

对于这个练习，你需要使用 MySQL Workbench 或你选择的任何 SQL 数据工具创建一个数据库和几张表。你可以在从 wrox.com 代码下载站点下载的 Entity-Mappings 项目的 `create.sql` 文件的本部分找到架构定义语句。打开 Workbench 并使用 root 用户登录到你的本地服务器。

在查询编辑器中输入以下 SQL 语句并点击执行图标，创建一个名为 EntityMappings 的数据库。

该数据库使用 `utf8` 字符集和 `utf8_unicode_ci` 排序规则。在几乎所有情况下你都应该使用它们。这些值是从任何语言中正确存储和检索字符数据的最佳值。如果你需要覆盖这些值，可以在表和列上单独设置字符集和排序规则，但你很少需要使用这二者以外的其他内容。创建数据库后，你还需要需要为 Book、Author 和 Publisher 实体创建三张表。记得你使用了 `@Table` 注解将表名设为复数。

```sql
USE EntityMappings;
```

```sql
CREATE TABLE Publishers (
PublisherId BIGINT UNSIGNED NOT NULL PRIMARY KEY,
PublisherName VARCHAR(100) NOT NULL,
Address VARCHAR(1024) NOT NULL,
INDEX Publishers_Names (PublisherName)
) ENGINE = InnoDB;
```

```sql
CREATE TABLE Authors (
AuthorId BIGINT UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
AuthorName VARCHAR(100) NOT NULL,
EmailAddress VARCHAR(255) NOT NULL,
INDEX Publishers_Names (AuthorName)
) ENGINE = InnoDB;
```

```sql
CREATE TABLE Books (
ID BIGINT UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
Isbn VARCHAR(13) NOT NULL,
Title VARCHAR(255) NOT NULL,
Author VARCHAR(100) NOT NULL,
Price DECIMAL(6,2) NOT NULL,
Publisher VARCHAR(100) NOT NULL,
UNIQUE KEY Books_ISBNs (Isbn),
INDEX Books_Titles (Title)
) ENGINE = InnoDB;
```

这些表并没有特别之处。它们包含了简单的列，清晰地转换了实体属性和数据类型。这里的关键在于先编写代码，然后设计一个支持你代码的数据库。这是设计大多数类型应用程序的优方法，因为先创建数据库可能会强制你的代码遵守数据库。最重要的是应用程序能够满足用户需求，并在代码中实现。JPA 让创建实体变得非常简单，然后创建一个仅仅支持这些实体的数据库。

最后，记住你使用了 JPA 来使用表生成器处理 Publisher 的代理键，因此你需要创建适当的生成器表来支持这一需求。

```sql
USE SurrogateKeys;
```

```sql
CREATE TABLE SurrogateKeys (
TableName VARCHAR(64) NOT NULL PRIMARY KEY,
KeyValue BIGINT UNSIGNED NOT NULL,
INDEX SurrogateKeys_Table_Values (TableName, KeyValue)
) ENGINE = InnoDB;
```

就是这些。数据库已经创建完成。

（由于原文后续部分关于持久化单元（Persistence Unit）的描述存在大量重复和乱码，以下译文已根据技术语境进行了逻辑对齐并保留了核心术语翻译）

# 持久化单元 (Persistence Unit)

持久化单元是一个配置，是一组逻辑分组的类。持久化单元的配置控制了 JPA 提供者如何访问实体。你可以通过 `persistence.xml` 定义多个持久化单元。

（此处由于原文中存在大量重复的英文和乱码，为了保证翻译质量，此处已根据技术文档规范进行精性化处理）

`<mapping-file>` 指定了 XML 映射文件相对于类路径的路径。如果你没有指定任何 `<mapping-file>`，提供程序将查找 `orm.xml`。你可以指定多个 `<mapping-file>` 元素使用多个映射文件。

你可以使用一个或多个 `<class>` 来指示应添加到持久化单元的特定 `@Entity`、`@Embeddable`、`@MappedSuperclass` 或 `@Converter` 类。你必须在这些类上加上 JPA 注解。

使用 `<exclude-unlisted-classes />` 或 `<exclude-unlisted-classes>` 表示提供程序应忽略未通过 `<jar-file>` 或 `<class>` 指定类。省略 `<exclude-unlisted-classes>` 或使用 `<exclude-unlisted-classes>false</exclude-unlisted-classes>` 会导致提供程序扫描持久化文件的类路径位置以查找带有 JPA 注解的实体。如果 `persistence.xml` 位于 JAR 文件中，则会扫描该 JAR（仅限该 JAR）。如果 `persistence.xml` 位于基于目录的类路径（如 `WEB-INF/classes`），则会扫描该目录（仅限该目录）。在 Hibernate 4.3.0 和 Spring Framework 3.2.5 之前，将此元素指定为 `false` 值会被错误地解释为 `true`

`<shared-cache-mode>` 指明实体如何在持久化单元中缓存（如果 JPA 提供缓存，这是可选的）：`NONE` 禁用缓存，而 `ENABLE_SELECT` 为所有实体启用缓存。只有标记了 `@javax.persistence.Cacheable(true)` 或 `@Cacheable(true)`（或在 `orm.xml` 中标记为可缓存）的实体才会被缓存。`ENABLE_SELECT` 为除标记了 `@Cacheable(false)`（或在 `orm.xml` 中标记为不可缓存）的实体外的所有实体启用缓存。默认值 `UNSPECIFIED` 意味着由 JPA 决定有效的默认值。Hibernate ORM 默认设置为 `ENABLE_SELECT`，依赖此设置并不具有可移植性。

`<validation-mode>` 指明是否以及如何将 Bean Validation 应用到实体上。`NONE` 表示未启用 Bean Validation，而 `CALLBACK` 则在插入、更新和删除时验证所有实体。如果类路径上存在 Bean Validation 提供者，`AUTO` 的有效值为 `CALLBACK`。如果你启用它，JPA 提供程序将配置一个新的验证器来验证你的实体。如果你配置了带有自定义本地化错误代码的 Spring Framework `Validator`，JPA 提供程序将忽略它。因此，最好在调用持久化层之前将验证模式设置为 `NONE` 并配置 Bean Validation。

`<properties>` 提供了一种指定其他 JPA 属性的方法，包括标准 JPA 属性（如 JDBC 连接字符串、用户名和密码，或架构生成设置）以及提供程序特定的属性（如 Hibernate 设置）。你使用嵌套的 `<property>` 元素指定一个或多个属性，每个都有 `name` 和 `value` 属性。

在所示的 Entity-Mappings 中创建的 `persistence.xml` 文件要求 Hibernate ORM 作为 JPA 提供程序，启用了你在 Tomcat `context.xml` 文件中创建的 DataSource，启用了对 `/WEB-INF/classes` 中所有类实体注解的扫描，启用了对注解实体的缓存以及 Bean Validation。它还包含一个属性以确保生成架构（以防万一）。



```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence xmlns="http://xmlns.jcp.org/xml/ns/persistence"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence/persistence_2_1.xsd">
  <persistence-unit name="EntityMappings" transaction-type="RESOURCE_LOCAL">
    <provider>org.hibernate.jpa.HibernatePersistenceProvider</provider>
    <jta-data-source>java:comp/env/jdb/EntityMappings</jta-data-source>
    <exclude-listed-classes>false</exclude-listed-classes>
    <shared-cache-mode>ENABLE_SELECTIVE</shared-cache-mode>
    <validation-mode>NONE</validation-mode>
    <properties>
      <property name="javax.persistence.schema-generation.database.action" value="none"/>
    </properties>
  </persistence-unit>
</persistence>
```

## 使用持久化 API

使用持久化 API 非常简单。大部分代码用于处理事务和资源。保存和检索实体。`EntityServlet` 使用持久化 API 显示实体。你应该首先查看的是 `init` 和 `destroy` 方法，分别在启动时创建一个 `javax.persistence.EntityManagerFactory` 并在关闭时关闭它。

```java
@WebServlet(
  name = "entityServlet",
  urlPatterns = "/entities",
  loadOnStartup = 1)
public class EntityServlet extends HttpServlet {

  private final Random random;
  private EntityManagerFactory entityManagerFactory;

  public EntityServlet() {
    try {
      this.random = SecureRandom.getInstanceStrong();
    } catch (NoSuchAlgorithmException e) {
    }

  @Override
  public void doGet(HttpServletRequest request, HttpServletResponse response)
  throws ServletException, IOException {

    EntityManager manager = null;
    EntityTransaction transaction = null;

    try {
        manager = this.factory.createEntityManager();
        transaction = manager.getTransaction();
        transaction.begin();

        CriteriaBuilder builder = manager.getCriteriaBuilder();

        CriteriaQuery<Publisher> q1 = builder.createQuery(Publisher.class);
        request.setAttribute("publishers", manager.createQuery(
            q1.select(q1)).getResultList());

        CriteriaQuery<Author> q2 = builder.createQuery(Author.class);
        request.setAttribute("authors", manager.createQuery(
            q2.select(q2)).getResultList());

        CriteriaQuery<Book> q3 = builder.createQuery(Book.class);
        request.setAttribute("books", manager.createQuery(
            q3.select(q3)).getResultList());

        transaction.commit();

        response.sendRedirect(request.getContextPath() + "/entities/");

    } catch (Exception e) {
        if (transaction != null && transaction.isActive()) {
            transaction.rollback();
        }
        e.printStackTrace(response.getWriter());
    } finally {
        if (manager != null && manager.isOpen()) {
            manager.close();
        }
    }
  }

  // ... (code omitted for brevity) ...

    Publisher publisher = new Publisher();
    publisher.setName("John Wiley & Sons");
    publisher.setAddress("1234 Baker Street");
    manager.persist(publisher);

    Author author = new Author();
    author.setName("Nicholas S. Williams");
    author.setEmailAddress("nick@example.com");
    manager.persist(author);

    Book book = new Book();
    book.setIsbn("" + random.nextInt(Integer.MAX_VALUE));
    book.setTitle("Professional Java for Web Applications");
    book.setAuthor("Nicholas S. Williams");
    book.setPublisher("John Wiley & Sons");
    book.setPrice(59.99);
    manager.persist(book);

    transaction.commit();
}
```

要测试项目，请按照以下步骤操作：

1. 从 IDE 编译并启动 Tomcat。在你的浏览器中访问 `http://localhost:8080/mappings/entities`，并多次点击“Add More Entities”（添加更多实体）。

2. 关闭 Tomcat 并重新启动。

3. 回到 `http://localhost:8080/mappings/entities`，实体在虚拟机实例之间仍然持久化存在。

4. 现在打开 MySQL Workbench 并执行如图 20-1 所示的语句。查看每个结果表，你可以看到 Hibernate ORM 已将数据插入到你的数据库表中。

```sql
USE EntityMappings;
SELECT * FROM Publishers;
SELECT * FROM Authors;
SELECT * FROM Books;
SELECT * FROM SurrogateKeys;
```

![](img/9c2d45f6d547f72cb870b3a991f62ef6_624_0.png)

# 第 20 章 使用 JPA 注解将实体映射到表

![](img/9c2d45f6d547f72cb870b3a991f62ef6_625_0.png)

图 20-1

## 映射复杂数据类型

到目前，你应该已经对实体映射的基础知识有了合理的掌握，但仍然存在一些缺失。在本节中，你将学习如何正确映射复杂数据类型，例如枚举、日期、时间和大型对象。在第 24 章中，你将探索更高级的映射任务（如继承、嵌套实体和自定义数据类型）。在本节中，你将使用 w3.com 代码网站下载的 Enums-Datab 项目。该项目扩展了你在本章早期处理过的 Entity-Mappings 项目，本节中的代码代表了对该项目的补充内容。

### 使用枚举作为实体属性

如之前讨论的，JPA 提供程序可以自动持久化为枚举的实体属性，无需任何特殊配置。枚举持久化的标准方式可能并不是你想要的。考虑以下枚举：

```java
public enum Gender
{
    MALE,
    FEMALE,
    UNSPECIFIED
}
```

作者实体有一个类型为 `Gender` 的属性 `gender`，表示作者的性别。

```java
...
public class Author implements Serializable
{
...
  private Gender gender;
...
  public Gender getGender() {
    return this.gender;
  }
  public void setGender(Gender gender) {
    this.gender = gender;
  }
}
```

使用时，JPA 提供程序使用整数序值（ordinal）来持久化枚举。因此，性别为男性的作者在数据库的 `gender` 列中的值为 0。同样，`FEMALE` 和 `UNSPECIFIED` 的持久化值分别为 1 和 2。这带来了几个挑战：

- 你无法直接查看数据库表（例如通过 MySQL Workbench）并自动识别数据。你会在 `gender` 列中只看到 0、1 和 2，而不是有用的描述。

- 如果有人更改了枚举并重启了常量（例如，按字母顺序排序），所有之前的数据现在都损坏了——这显然是一个大问题。

无论数据库列是数值列（如 `INT`）还是字符串列（如 `VARCHAR`），这种默认情况都是一样的。幸运的是，JPA 提供了 `@java.persistence.Enumerated` 属性，允许你更改该值的持久化方式。讽刺的是，`@Enumerated` 的默认值是 `EnumType.ORDINAL`。你可以告诉 JPA 提供程序以字符串格式（常量名称）持久化枚举，这既是重构安全的（除非有人更改了名称，那是一个更大的问题），又便于在数据库中查看。

```java
@Enumerated(EnumType.STRING)
public Gender getGender() {
  return this.gender;
}
```

使用 `EnumType.STRING` 时，你的列不仅必须是字符串类型（这显而易见），而且必须是 Unicode（例如 UTF-8 或 UTF-16 字符集）。该规则的例外是数据库支持原生枚举类型，Java 可能包含无法正确存储在非 Unicode 列中的字符；由于 Java 中的 String 始终是 Unicode，最好将所有文本列都设置为 Unicode，这样就不需要转换。新的 `Authors` 表定义使用 MySQL `ENUM` 数据类型在数据库中提供额外的元数据层并减少存储空间。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_626_0.png)

### 理解 JPA 如何处理日期时间

```sql
CREATE TABLE Authors (
  AuthorId BIGINT UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
  AuthorName VARCHAR(100) NOT NULL,
  EmailAddress VARCHAR(255) NOT NULL,
  Gender ENUM('MALE', 'FEMALE', 'UNSPECIFIED') NULL,
  INDEX_Names (AuthorName)
) ENGINE = InnoDB;
```

自软件开发以来，日期和一直是开发者面临的最大挑战。处理 JDBC 让这一挑战变得稍微容易了一些，但仍然面临挑战。JDBC 4.2（由于 Java 8 日期 API）在处理日期时间方面有了显著改进，但 JPA 可能要等到 2.2 或 2.3 版本才会适应这些变化。大多数关系数据库有三种日期相关类型：`DATE`、`TIME` 和 `DATETIME`。某些数据库还有 `TIMESTAMP` 类型，它们与 `datetime` 大多相同，在使用 JDBC 时你可以认为它们是等效的。你应该始终意识到数据库供应商支持的日期相关类型的用途、功能和限制，并为给属性选择最合适的一个。

在 JDBC 的旧版本中，插入日期、时间或日期的选项只有 `PreparedStatement` 的 `setDate` 和 `setTimestamp` 方法。这些方法分别需要 `java.sql.Date` 和 `java.sql.Timestamp`。ResultSet 的 `getDate`、`getTime` 和 `getTimestamp` 方法分别返回 `Date`、`Time` 和 `Timestamp`，其 `updateDate`、`updateTimestamp` 和 `update` 方法的功能与 PreparedStatement 方法相同。它们在数据库中的存储方式如下：

- `Date` 仅存储日期（年、月、日）。

- `Time` 存储为时间（时、分、秒）。

- `Timestamp` 是两者的结合，始终存储为年、月、日、时、分、秒。

JDBC 4.2 增加了将任何 `Object` 作为日期、时间、带时区的时间、日期或带时区的日期进行插入或检索的能力，使用了 `PreparedStatement` 的 `setObject(int, Object, java.sql.Type)` 方法以及 `ResultSet` 的 `getObject(int, Class, java.sql.Type)` 和 `getObject(String, Class)`。当然，你只有在驱动供应商支持时才能使用这些方法，但所有 JDBC 4.2 版本都预期支持 `java.util.Date`、`Calendar`、`java.sql.Date` 和 `Timestamp` 之外的 Java 8 日期和时间类型。

### 映射复杂数据类型（续）

某些数据库系统（如 Microsoft Server）除时区外还支持时间和日期时间列。其他数据库（如 MySQL）仅支持服务器时区的时间日期时间。你应该节制使用它们，仅在必要时使用。

> **警告** 每当使用最新的 JDBC 4.1 和 4.2 功能时，你应该小心。许多驱动（如 MySQL 和 SQL Server 的驱动）尚未赶上 2011 年 7 月添加的 JDBC 4.1 功能。事实上，截至编写时，PostgreSQL 的 JDBC 仅支持 2002 年 2 月的 JDBC 3.0 功能。PostgreSQL 声称拥有一个 JDBC 4.0 驱动，包含了 2006 年 12 月的 Java 6 功能，但该驱动非常复杂，并在某些地方抛出 `AbstractMethodError`。Oracle 是目前唯一支持 JDBC 4.1 的供应商。你可以预计这种趋势将持续，因此可能需要多年后你才能在 MySQL 中使用 JDBC 4.2 功能。

使用 JPA 时，属性 `date` 存储为日期（使用 `PreparedStatement.setDate`）。即使数据库列是 `DATETIME`，列的时间部分也为零。同样，`time` 属性仅存储为时间（使用 `PreparedStatement.setTime`），且数据库列必须是 `TIME`（或等效）列。`Timestamp` 属性自动存储日期和时间部分，相应的数据库列必须是 `DATETIME`（或等效）。如果你的实体包含 `util.Date` 或 `Calendar`，情况可能会变得复杂。对于这些，使用 `@javax.persistence.Temporal` 注解来告诉提供程序持久化该类型。`value` 属性接收一个 `java.sql.persistence.TemporalType`，其选项包括：



- `TemporalType.DATE`（将 `Date` 或 `Calendar` 属性转换为 `java.sql.Date`）
- `TemporalType.TIME`（将属性转换为 `Time`）
- `TemporalType.TIMESTAMP`（将属性转换为 `Timestamp`）

你不能在已经是 `java.sql.Date`、时间或 `Timestamp` 类型的属性上使用 `@Temporal`。`Publisher` 实体的 `dateFounded` 使用 `Calendar` 来存储创建日期，并将其值存储在 `DATE` 列中。

```java
public class Publisher implements Serializable {
    private Calendar dateFounded;

    ...

    @Temporal(TemporalType.DATE)
```

```java
public Calendar getDateFound()
{
    return dateFound;
}
```

```java
public void setDateFound(Calendar dateFound)
{
    this.dateFound = dateFound;
}
```

```sql
CREATE TABLE Publishers (
PublisherId BIGINT UNSIGNED NOT NULL PRIMARY KEY,
PublisherName VARCHAR(100) NOT NULL,
Address VARCHAR(1024) NOT NULL,
DateFound DATE NOT NULL,
INDEX Publishers_Names (PublisherName)
) ENGINE = InnoDB;
```

当然，这并不是理想的。你不想使用 `java.util.Date` 或 `Calendar` 来仅仅存储一个日期，而且 `java.sql.Date` 与 `java.util.Date` 配合使用非常痛苦（它甚至继承了 `java.util.Date`，这简直太奇怪了）。你在这里真正想做的是使用新的 `java.time.LocalDate` 作为实体属性，但 JPA 提供程序不知道如何处理该类型。在第 24 章中，你将学习如何编写转换器，以便你能够使用 Java 8 的日期和时间类型。

## 将属性映射到 CLOB 和 BLOB

有时，`CHAR`、`VARCHAR`、`NCHAR` 或 `VARCHAR` 列（通常限制为几千字符）仍然不够大。在 `BINARY` 或 `VARBINARY` 列中存储二进制数据也是如此。数据库系统提供了一种存储大对象（LOB）的方法，它们可以容纳数百万或数十字节。它的文本形式是字符大对象（CLOB），而二进制形式是二进制大对象（BLOB）。

JDBC 提供了不同的优化的机制来存储和检索 LOB，这些机制与标准的 `String` 和 `setBytes` 方法不兼容，因此你必须使用 JPA 将预期为大的值存储为 BLOB，而不是使用标准列。你通过 `@javax.persistence.Lob` 注解来实现这一点。标记为 `@Lob` 的 `String` 和 `char[]` 属性会被持久化为 CLOB。所有其他类型（例如 `byte[]` 和 `Serializable` 属性）会被持久化为 Blob。`Book` 实体使用 `@Lob` 属性来存储 PDF 格式的书的前几页预览。

```java
public class Book implements Serializable
{
    private byte[] previewPdf;

    @Lob
    public byte[] getPreviewPdf()
    {
        return previewPdf;
    }

    public void setPreviewPdf(byte[] previewPdf)
    {
        this.previewPdf = previewPdf;
    }
}
```

```sql
CREATE TABLE Books (
    Id INT UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Isbn VARCHAR(13) NOT NULL,
    Title VARCHAR(255) NOT NULL,
    Author VARCHAR(100) NOT NULL,
    Price DECIMAL(6,2) NOT NULL,
    Publisher VARCHAR(100) NOT NULL,
    UNIQUE KEY Books_Isbns (Isbn),
    INDEX Books_Titles (Title)
) ENGINE = InnoDB;
```

> 注意：你可以将 `@Enumerated`、`@Temporal` 和 `@Lob` 与 `@Basic` 结合使用，以启用加载或将属性标记为可选。然而，对于其他基本类型，如果你不想使用，就不需要使用 `@Basic`。

测试 Enums-Lobs-Dates 项目本质与测试 Entity-Mappings 项目相同：

1. 在 MySQL Workbench 中运行 `.sql` 文件以创建 EnumsLobsDates 数据库及其表。
2. 更新 Tomcat 的 JNDI 资源以指向新数据库。

```xml
<Resource name="jdbc/EnumsLobsDates" type="java.sql.DataSource"
    maxActive="20" maxIdle="5" maxWait="10000"
    username="tomcatUser" password="password1234"
    driverClassName="com.mysql.jdbc.Driver"
    url="jdbc://localhost/EnumsLobsDates" />
```

3. 在你选择的浏览器中访问 http://localhost:8080/entities，点击几次“Add More Entities”。它的行为应该与之前完全一样，但增加了作者性别和出版商成立日期（在示例中为今天的日期）。
4. 你也可以使用 MySQL Workbench 查询这些表以查看你插入的数据。你需要使用 MySQL 的 `hex` 函数将 `PreviewPdf` 列转换为十六进制字符串以便显示：

```sql
USE EnumsLobsDates;
SELECT * FROM Publishers;
SELECT * FROM Authors;
SELECT Id, Isbn, Title, Author, Price, Publisher, hex(PreviewPdf) FROM Books;
SELECT * FROM SurrogateKeys;
```

### 总结

在本章中，你探索了使用 JPA 注解映射实体的基础，并查看了使用 `orm.xml` 进行 XML 映射的简要示例。你学习了 `persistence.xml`、它的作用、什么是持久化单元（persistence unit）以及持久化单元的作用范围是如何工作的。你在 MySQL 中创建了几个表，并实验了使用持久化 API 存储和从这些表中检索数据。你还学习了在处理枚举、日期、时间、日期-时间以及 LOB 时涉及的一些重要步骤和考虑因素。

你尚未充分利用持久化 API，关于查找、插入、更新和删除实体的许多部分你仍然需要学习。在下一章中，你将更深入地探索持久化 API，使用 Spring Framework 来处理注入持久化单元和管理事务的繁琐工作。

## 在 Spring Framework 仓库中使用 JPA

### 本章内容

- 理解 Spring 仓库并利用事务
- 在 Spring Framework 中设置持久化
- 实现并使用 JPA 仓库
- 使用 DTOs 转换数据



# 理解 Spring 仓库并利用事务

## 本章内容

- 理解 Spring 仓库并利用事务
- 在 Spring Framework 中设置持久化
- 实现并使用 JPA 仓库
- 使用 DTOs 转换数据

## 将属性映射到 CLOB 和 BLOB

有时，`CHAR`、`VARCHAR`、`NCHAR` 或 `VARCHAR` 列（通常限制为几千字符）仍然不够大。在 `BINARY` 或 `VARBINARY` 列中存储二进制数据也是如此。数据库系统提供了一种存储大对象（LOB）的方法，它们可以容纳数百万或数十亿字节。它的文本形式是字符大对象（CLOB），而二进制形式是二进制大对象（BLOB）。

JDBC 提供了不同的优化的机制来存储和检索 LOB，这些机制与标准的 `String` 和 `setBytes` 方法不兼容，因此你必须使用 JPA 将预期为大的值存储为 BLOB，而不是使用标准列。你通过 `@javax.persistence.Lob` 注解来实现这一点。标记为 `@Lob` 的 `String` 和 `char[]` 属性会被持久化为 CLOB。所有其他类型（例如 `byte[]` 和 `Serializable` 属性）会被持久化为 Blob。`Book` 实体使用 `@Lob` 属性来存储 PDF 格式的书的前几页预览。

```java
public class Book implements Serializable
{
    private byte[] previewPdf;

    @Lob
    public byte[] getPreviewPdf()
    {
        return previewPdf;
    }

    public void setPreviewPdf(byte[] previewPdf)
    {
        this.previewPdf = previewPdf;
    }
}
```

```sql
CREATE TABLE Books (
    Id INT UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Isbn VARCHAR(13) NOT NULL,
    Title VARCHAR(255) NOT NULL,
    Author VARCHAR(100) NOT NULL,
    Price DECIMAL(6,2) NOT NULL,
    Publisher VARCHAR(100) NOT NULL,
    UNIQUE KEY Books_Isbns (Isbn),
    INDEX Books_Titles (Title)
) ENGINE = InnoDB;
```

> 注意：你可以将 `@Enumerated`、`@Temporal` 和 `@Lob` 与 `@Basic` 结合使用，以启用加载或将属性标记为可选。然而，对于其他基本类型，如果你不想使用，就不需要使用 `@Basic`。

## 测试 Enums-Lobs-Dates 项目

测试 Enums-Lobs-Dates 项目本质与测试 Entity-Mappings 项目相同：

1. 在 MySQL Workbench 中运行 `.sql` 文件以创建 EnumsLobsDates 数据库及其表。
2. 更新 Tomcat 的 JNDI 资源以指向新数据库。

```xml
<Resource name="jdbc/EnumsLobsDates" type="java.sql.DataSource"
    maxActive="20" maxIdle="5" maxWait="10000"
    username="tomcatUser" password="password1234"
    driverClassName="com.mysql.jdbc.Driver"
    url="jdbc://localhost/EnumsLobsDates" />
```

3. 在你选择的浏览器中访问 `http://localhost:8080/entities`，点击几次“Add More Entities”。它的行为应该与之前完全一样，但增加了作者性别和出版商成立日期（在示例中为今天的日期）。
4. 你也可以使用 MySQL Workbench 查询这些表以查看你插入的数据。你需要使用 MySQL 的 `hex` 函数将 `PreviewPdf` 列转换为十六进制字符串以便显示：

```sql
USE EnumsLobsDates;
SELECT * FROM Publishers;
SELECT * FROM Authors;
SELECT Id, Isbn, Title, Author, Price, Publisher, hex(PreviewPdf) FROM Books;
SELECT * FROM SurrogateKeys;
```

## 总结

在本章中，你探索了使用 JPA 注解映射实体的基础，并查看了使用 `orm.xml` 进行 XML 映射的简要示例。你学习了 `persistence.xml`、它的作用、什么是持久化单元（persistence unit）以及持久化单元的作用范围是如何工作的。你在 MySQL 中创建了几个表，并实验了使用持久化 API 存储和从这些表中检索数据。你还学习了在处理枚举、日期、时间、日期-时间以及 LOB 时涉及的一些重要步骤和考虑因素。

你尚未充分利用持久化 API，关于查找、插入、更新和删除实体的许多部分你仍然需要学习。在下一章中，你将更深入地探索持久化 API，使用 Spring Framework 来处理注入持久化单元和管理事务的繁琐工作。

# 在 Spring Framework 仓库中使用 JPA

## 本章内容

- 理解 Spring 仓库并利用事务
- 在 Spring Framework 中设置持久化
- 实现并使用 JPA 仓库
- 使用 DTOs 转换数据



# 使用 DTOs 转换数据

## 本章内容

- 理解 Spring 仓库并利用事务
- 在 Spring Framework 中设置持久化
- 实现并使用 JPA 仓库
- 使用 DTOs 转换数据

## 事务与实体管理器线程

之前讨论的事务作用范围局限于事务启动时的线程。事务管理器会将事务链接到事务生命周期内同一线程中使用的资源。当使用 Java 持久 API (JPA) 时，你操作的资源是 `EntityManager`。它等同于 Hibernate ORM 的 Session 和 JDBC Connection。通常情况下，在开始事务并执行 JPA 操作之前，你会从 `EntityManagerFactory` 获取一个 `EntityManager`。然而，这与 Spring Framework 代你管理事务的模式是不兼容的。

该问题的解决方案是 `org.springframework.framework.orm.support.SharedEntityManagerBean`。当你在 Spring Framework 中配置 JPA 时，它会创建一个代理 `EntityManager` 接口的 `SharedEntityManagerBean`。该代理被注入到你的 JPA 仓库（repositories）中。当在该代理上调用 EntityManager 方法时：

- 如果当前线程已经有一个具有活动事务的真实 `EntityManager`，它会将调用委托给该 EntityManager 上的方法。
- 否则，Spring Framework 会从 `EntityManagerFactory` 获取一个新的 `EntityManager`，启动事务，并将两者都绑定到当前线程。然后将调用委托给该 EntityManager 上的方法。

当事务退出或回滚时，Spring 会从线程中解绑事务和 EntityManager，然后关闭该 EntityManager。在同一线程上后续的 `@Transactional` 操作（即使在同一个请求内）将重新开始该过程，从工厂获取新的 `EntityManager` 并开启新事务。通过这种方式可以同时使用 EntityManager，并且给定线程在任何给定时刻只有一个活跃的事务和一个 EntityManager。

与其在仓库类中将 `EntityManager` 字段标记为 `@Inject` 或 `@Autowired`，不如使用 `javax.persistence.PersistenceContext` 注解标明 Spring 应该注入 `EntityManager` 的代理。

```java
@PersistenceContext
EntityManager entityManager;
```

普通的 `EntityManager` 不是线程安全的，并且它们始终要求你在在使用之前启动事务。从 Spring Framework 获取 `@PersistenceContext` `EntityManager` 意味着你的仓库可以在多个线程中使用此实例，且每个线程都有自己的、由你管理的事务 `EntityManager` 实例。

使用 `@PersistenceContext` 的另一个优势是你可以为特定的 `EntityManager` 实例指定持久化单元名称（persistence unit name）。通过这种方式，你可以在 Spring 应用上下定义多个持久化上下文配置，并通过指定名称来区分你打算在仓库中使用哪个 `EntityManager` 实例。

```java
public class FooRepository {
    @PersistenceContext(unitName = "fooUnit")
    EntityManager entityManager;
}
```

```java
public class BarRepository {
    @PersistenceContext(unitName = "barUnit")
    EntityManager entityManager;
}
```

在 Spring Framework 中使用 JPA 时，你可以使用两种 `PlatformTransactionManager` 实现之一。

- 最标准且常用的是 `org.springframework.orm.jpa.JpaTransactionManager`，这也是你在本书中使用的。该实现只能管理 `EntityManager` 操作的事务，且仅针对单个持久化单元，但在许多情况下这已经足够你了。
- 如果你想在应用程序中使用多个持久化单元（如上例所示），或跨多种类型的资源（如 EntityManager 和 Java 消息服务资源）管理事务，你需要 `org.springframework.transaction.jta.JtaTransactionManager` 或其子类（WebLogic 或 WebSphere 服务器上的 `WebLogicJtaTransactionManager`）。该实现需要一个 JTA API 提供者，因此要使用它，你需要完整的 EE 服务器或复杂的独立式 JTA 配置（如 Tomcat 的情况）。
- JTA 是一个广泛的主题，在完整的 EE 应用服务器之外很难配置，因此本书不再对其进行介绍。网上有很多 JTA 教程，你的应用服务器文档也应该是一份有用的资源。

## 利用异常翻译的优势

在 JDBC 的时代，处理异常可能是一场噩梦。每个 JDBC 供应商都有自己扩展自 `java.sql.SQLException` 的异常，与这些异常关联的错误代码也根据供应商而异。如果你想知道为什么发生错误，你只能将代码限制在单一供应商上，并弄清楚该供应商的异常模式，或者在 `catch` 块中对异常进行测试。这个过程非常乏味，而且往往导致编写的代码比实际执行工作花费的代码还要多。

随着 O/RM 变得越来越流行，有些定义了实用的异常层次结构，而有些则没有。Java Persistence API 定义了从 `javax.persistence.PersistenceException` 开始的适中异常层次结构，即使在某些关键功能领域（如指示发生唯一值冲突的异常）也是如此。而在 NoSQL 领域，每个客户端库都定义了自身的检查异常或未检查异常，且它们没有一个继承自持久化异常，这使得问题变得更加棘手。

Spring 及其相关工具（如 Spring Data NoSQL）提供了 `org.springframework.dao.DataAccessException`。这个包包含了许多异常，本书并未涵盖所有异常。只需说明，如果你使用 JDBC、Hibernate 或其他 ORM、JPA、Java Data Objects 或 NoSQL，你可以在这个特定的异常层次结构中查找异常。

在应用程序中实现这种异常翻译有两个关键。



首先，你必须配置一个或多个 `org.springframework.dao.PersistenceExceptionTranslator` 实现。不同的技术有不同的 `PersistenceExceptionTranslator`。如果你在应用程序中使用多种持久化技术（例如 JPA 和 NoSQL），你需要配置一个处理所有情况的实现，或者配置多个实现（Spring 使用 `org.springframework.framework.dao.ChainedPersistenceExceptionTranslator` 自动对它们进行链式处理）。

Spring Framework 提供了处理不同持久化技术的多种 `PersistenceExceptionTranslator`。你在下一节中配置的 `org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean` 也是能够将 JPA 异常和底层 JDBC 错误代码翻译为 `DataAccessException` 的一个。只需定义这个 bean，你就为 JPA 配置了异常翻译。如果你有多种持久化技术，可以为每种技术配置一个实现。

在配置异常翻译后，你必须为你的仓库标记 `@Repository`。这告诉被标记的 bean 有资格使用配置的 `PersistenceExceptionTranslator` 进行异常翻译。如果仓库方法抛出任何异常，`PersistenceExceptionTranslator` 将相应翻译这些异常。注意这意味着你不能从仓库本身捕获 `DataAccessExceptions`，因为翻译尚未发生。你只能在调用仓库方法的代码中捕获 `DataAccessException`。

### 602 | 第 21 章在 Spring Framework 仓库中使用 JPA

> 如果你查看 Spring Framework 及其工具提供的所有 `PersistenceUnitTranslator` 实现，你会发现并没有纯粹的 JDBC 异常翻译器。当你在 Spring 仓库中使用 JDBC 时，预计你将使用 `JdbcTemplate`。因为 `JdbcTemplate` 是 Spring 的工具而不是第三方类，它内置了持久化转换功能。

## 在 Spring Framework 中配置持久化

在 Spring 中配置 JPA 实际上非常简单，但你将理解几个选项，这些章节将向你解释它们。通常，Spring JPA 配置包含三个部分：

- 创建或查找 DataSource。
- 创建或查找持久化单元（persistence unit）并配置 Spring 注入到你的仓库中。
- 设置事务管理，以便 `@Transactional` 方法能被正确处理。

你可以从 wrox.com 下载站点下载对应的 Spring-JPA 项目。该项目从你在第二部分末尾使用的 Spring 引导和配置开始。

## 查找数据源

你需要做的第一件事是让你的应用程序可以使用 DataSource。你有几种方法可以实现这一点，如果你只需要测试某些内容，可以使用 Spring 的 `org.springframework.jdbc.datasource.DriverManagerManagerDataSource` 来按需创建 DataSource：

```java
@Bean
public DataSource dataSource() {
    DriverManagerManagerDataSource dataSource = new DriverManagerManagerDataSource();
    dataSource.setUrl("jdbc:mysql://localhost/JpaSpring*");
    dataSource.setUsername("tomcatUser");
    dataSource.setPassword("password1234");
    return dataSource;
}
```

然而，这创建了一个返回单一 `Connection` 的简单 DataSource。因为它不提供池化功能，所以它真的不应该在任何类型的生产环境中使用。在独立应用程序中，你可以使用 Apache DBCP 和 Apache Connection Pool 来创建并返回池化的 DataSource。通常，你需要读取一个包含 URL、用户名和密码信息的属性文件，这样更改连接详情就不需要重新编译代码。在应用服务器或 Servlet 容器上，最简单的方法是在服务器上定义一个 DataSource（如你在上一章中所做的那样），并从你的 `RootApplicationContext` 中查找该 DataSource。这就是 Spring-JPA 项目所做的。

### 603 | 在 Spring Framework 中配置持久化

```java
@Bean
public DataSource dataSource() {
    JndiDataSourceLookup lookup = new JndiDataSourceLookup();
    return lookup.get("jdbc/SpringJpa");
}
```

> 连接池是第二部分的内容。连接池包含多个可供使用的空闲连接。这些连接从池中借用，在不再需要时归还并重置。通过这种方式，避免了不断打开和关闭连接的开销。你应用服务器或 Servlet 容器中的 DataSource 配置使用了连接池。

在你处理此项工作时，不要忘记在 Tomcat 的 `context.xml` 文件中定义 DataSource 资源。在下一节中配置合适的 `defaultTransactionIsolation` 属性。

```xml
<Resource name="jdbc/SpringJpa" type="javax.sql.DataSource"
    maxActive="20" maxIdle="5" maxWait="10000"
    username="tomcatUser" password="password1234"
    driverClassName="com.mysql.jdbc.JdbcDriver"
    defaultTransactionIsolation="READ_COMMITTED"
    url="jdbc:mysql://localhost/spring_jpa" />
```

在此示例中，使用了一个无法参与 JTA 事务的标准 DataSource。这对于书中的示例已经足够，但如果你想让一个事务跨越多个 DataSources 或多种技术（如 JMS），你必须定义并查找支持 JTA 的 DataSource。这在 Tomcat 中是可能的，但非常困难。你的最佳选择是使用 Java EE 应用服务器。

## 创建持久化单元代码

配置 Spring Framework 的 JPA 支持时，最重要的事情就是设置你的持久化单元。你已经在第 20 章中探索了在 `/WEB-INF/META-INF/persistence.xml` 文件中创建持久化单元，但使用 Spring Framework 并不限制。

要正确使用 JPA，你需要配置一个实现 `org.springframework.orm.jpa.AbstractEntityManagerFactoryBean` 的 bean。这种类型的 bean 可以创建 `SharedEntityManagerBeans`，用于管理仓库中绑定线程且关联事务的 EntityManager。

最简单的方法是配置 `org.springframework.orm.jpa.LocalEntityManagerFactoryBean`。此 bean 要求 `/META-INF/persistence.xml` 存在，并从该文件读取持久化单元设置。当你配置 `LocalEntityManagerFactoryBean` 时，要指定它应该使用的持久化单元名称。

### 604 | 第 21 章在 Spring Framework 仓库中使用 JPA

```java
@Bean
public LocalEntityManagerFactoryBean entityManagerFactory() {
    LocalEntityManagerFactoryBean factory =
        new LocalEntityManagerFactoryBean();
    factory.setPersistenceUnitName("SpringJpa");
    factory.setJpaVendorAdapter(new HibernateJpaVendorAdapter());
    factory.setDataSource(this.springJpaDataSource());
    return factory;
}
```

这是完美的，但在灵活性方面非常有限。一个更有实用的实现是 `org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean`，它不需要 `META-INF/persistence.xml` 存在。例如，将你的持久化文件放在名为 `META-INF` 的包中，然后让 `LocalContainerEntityManagerFactoryBean` 指向持久化文件所在。

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactory() {
    LocalContainerEntityManagerFactoryBean factory =
        new LocalContainerEntityManagerFactoryBean();
    factory.setPersistenceXmlLocation(
        "classpath:wrox/config/persistence.xml");
    factory.setPersistenceUnitName("SpringJpa");
    factory.setJpaVendorAdapter(new HibernateJpaVendorAdapter());
    factory.setDataSource(this.springJpaDataSource());
    return factory;
}
```

最重要的是，你甚至不需要 `persistence.xml` 文件就可以使用 `LocalContainerEntityManagerFactoryBean`。你可以使用纯 Java 代码来配置它。

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactory() {
    Map<String, Object> properties = new HashMap<>();
    properties.put("javax.persistence.schema.generation.action", "none");

    HibernateJpaAdapter adapter = new HibernateJpaAdapter();
    adapter.setDatabasePlatform("org.hibernate.dialect.MySQL5Dialect");

    LocalContainerEntityManagerFactoryBean factory =
        new LocalContainerEntityManagerFactoryBean();
    factory.setJpaVendorAdapter(adapter);
    factory.setDataSource(springJpaDataSource());
    factory.setPackagesToScan("wrox.entities");
    return factory;
}
```

仔细观察这段代码，因为发生了很多。首先，它创建一个 map 来存储 JPA 属性——在本例中是 schema 生成。接下来，它创建一个 `org.springframework.orm.jpa.vendor.HibernateJpaAdapter` 并将其设置为 factory 的适配器。这是一个特殊的 Spring 属性，具有以下作用：

- 它告诉 `LocalEntityManagerFactoryBean` 使用哪个 `PersistenceProvider`（`org.hibernate.jpa.PersistenceProvider`）。这替换了 `persistence.xml` 中的 `<provider>`。
- 它告诉 `SharedEntityManagerBean` 代理哪个扩展的 EntityManagerFactory 接口（`org.hibernate.jpa.SessionFactory`）以及代理哪个扩展的 EntityManager 接口（`org.hibernate.jpa.EntityManager`）。
- 它告诉 Spring 如何将 Hibernate ORM 特有的异常转换为 `DataAccessException`。
- 它通知事务管理在开始和结束事务时应使用的额外步骤以处理可能出现的问题。
- 它配置 Hibernate ORM 使用正确的方言。Hibernate 会尝试检测使用的方言，但对于 MySQL 它总是选择 `org.hibernate.dialect.MySQLDialect`。这个遗留方言仅适用于 MySQL 4.x，不应用于 MySQL 5.x。手动指定此值是最安全的。

### 605 | 在 Spring Framework 中配置持久化

```java
factory.setJpaProperties(properties);
return factory;
```

### 表 21-1: 常见的 Hibernate 方言

| 数据库名称与版本(s) | 方言类 |
| --- | --- |
| H2 Database | `org.hibernate.dialect.H2Dialect` |
| HyperSQL 1.8+, 2.x+ | `org.hibernate.dialect.HSQLDialect` |
| MySQL 4.x Generic | `org.hibernate.dialect.MySQLDialect` |
| MySQL 4.x MyISAM Engine | `org.hibernate.dialect.MySQLMyISAMDialect` |
| MySQL 4.x InnoDB Engine | `org.hibernate.dialect.MySQLInnoDBDialect` |
| MySQL 5.x+ Generic + MyISAM | `org.hibernate.dialect.MySQL5Dialect` |
| MySQL 5.x+ InnoDB Engine | `org.hibernate.dialect.MySQL5InnoDBDialect` |
| Oracle Database 8i | `org.hibernate.dialect.Oracle8Dialect` |
| Oracle Database 9i | `org.hibernate.dialect.Oracle9Dialect` |
| Oracle Database 10g, 11g+ | `org.hibernate.dialect.Oracle10gDialect` |
| PostgreSQL 8.1 | `org.hibernate.dialect.PostgreSQL81Dialect` |
| PostgreSQL 8.2+ | `org.hibernate.dialect.PostgreSQL82Dialect` |
| Microsoft SQL Server 2000 | `org.hibernate.dialect.SqlServerDialect` |
| Microsoft SQL Server 2005 | `org.hibernate.dialect.SQLServer2005Dialect` |
| Microsoft SQL Server 2008, 2012+ | `org.hibernate.dialect.SQLServer2008Dialect` |
| Sybase 10 | `org.hibernate.dialect.SybaseDialect` |
| Sybase 11.9+2 | `org.hibernate.dialect.Sybase11Dialect` |
| Sybase ASE 15+ | `org.hibernate.dialect.SybaseASE15Dialect` |
| Sybase Anywhere 8+ | `org.hibernate.dialect.SybaseAnywhereDialect` |

`JpaVendorAdapter` 是 `org.springframework.framework.jpa.JpaVendorAdapter` 的一种实现。Spring 提供了 Eclipse 和 JPA 的适配器，可以为这些 JPA 供应商进行正确配置，如果必要，你可以创建任何自己的实现来支持其他供应商。注意，`LocalEntityManagerFactoryBean` 和 `LocalContainerEntityManagerBean` 在没有 `JpaVendorAdapter` 实现的情况下也可以工作，但它们可能无法达到最佳状态。最好始终提供此项。



> 注意：与其在适配器上调用 `setDatabase`，你也可以调用 `setDatabase` 并传递 `org.springframework.orm.jpa.vendor` 常量之一。这样，`HibernateVendorAdapter` 就会为你选择 Hibernate 方言类。然而，它仅为 MySQL 数据库选择 `MySQLDialect`，为 SQL Server 数据库选择 SQL Server 2000 方言，以此类推。尽管如此……否则，你可能无法为数据库获取正确的方言。

配置适配器后，代码会将 `DataSource` 设置为你之前配置的那个。这替换了 `persistence.xml` 中的 `non-jta-data-source` 元素，并将持久单元的 `transaction-type` 设置为 `RESOURCE_LOCAL`。（调用 `setJtaDataSource` 等同于使用 `jta-data-source` 并将 `transaction-type` 设置为 `JTA`）。

它告诉 `LocalContainerEntityManagerFactoryBean` 扫描 `com.wrox.site` 包以查找实体豆。此列表等同于 `<exclude-listed-classes>true</exclude-listed-classes>` 并使用 `<class>` 列出每个实体类，不同之处 Spring 会为你检测并注册这些实体。这显著加快了 `<exclude-unlisted-classes></exclude-unlisted-classes>` 的速度，因为 Spring 将扫描限制在你指定的包中，而 JPA 供应商者必须扫描许多包和类。随后，配置会设置共享缓存模式（等同于 `<shared-cache-mode>`）、验证模式（等同于 `<validation-mode>`）以及 JPA 属性。

> 通常情况下，在使用 JPA 时，你真的不需要了解太多 Hibernate OR。但是，你需要了解一些事情，例如方言。为了参考，你可以在 http://docs.jboss.org/hibernate/4.3/javadocs/ 查看 Hibernate OR 4.3 API 文档。在为特定数据库选择方言之前，你应该查看 `org.hibernate.dialect` 及其子类的 API 文档。

## 事务管理

配置事务管理是在 Spring Framework 中使用 JPA 的最后一步。它并不特别复杂，但有一些需要注意的地方。你最初通过在 `RootContextConfiguration` 上注解 `org.springframework.transaction.annotation.EnableTransactionManagement` 来激活事务管理和 `@Transactional` 方法注解。就像你已经在使用的 `@EnableAsync` 注解一样，`@EnableTransactionManagement` 会导致 Spring 动态地为你的 `@Transactional` Bean 方法提供建议。你必须小心执行。

首先，必须为 `@EnableAsync` 和 `@EnableTransactionManagement` 配置相同的 `AdviceMode`（PROXY 或 ASPECTJ）以及相同的 `proxyTargetClass` 值。如第 14 节所述，最简单的方法是使用 `AdviceMode.PROXY` 并将 `proxyTargetClass` 设置为 `false`。

### 关于 Spring Framework 方法代理的说明

Spring Framework 可以使用切面切点（Aspect pointcuts）或代理为你的方法提供建议。使用 `AdviceMode.PROXY` 意味着代理类将封装必要的方法，以便根据需要对方法前后提供代码建议。你可以使用动态代理（`proxyTargetClass = false`）创建代理，动态代理是标准 Java SE API 的一部分。这是首选的代理技术。然而，动态代理只能对接口中指定的方法提供建议，并且只有在调用代码使用接口而不是类时才会生效。如果你需要对仅属于类而不属于接口的公共方法提供建议，则必须使用 CGLIB 代理（`proxyTargetClass = true`）。使用 CGLIB 代理需要记住的重要缺点是，你的 Bean 构造函数会执行两次而不是一次，因此请相应地操作。

## 第 21 节 在 Spring Framework Repositories 中使用 JPA

当你使用动态代理时，它们提供的方法建议仅当另一个类在 Spring 管理的 Bean 实例上执行方法时才生效。如果在一个 `FooBean` 实例上调用的方法执行了该 `FooBean` 实例上的另一个方法（无论是否使用此功能），方法建议将不会执行。（参见 `org.springframework.aop.framework.AspectContext` 以了解实现此点的拙劣方法，你应该尽可能避免这样做。）CGLIB 代理会覆盖类上的每个非 final 方法，因此当 `FooBean` 调用另一个 `FooBean` 方法时（无论是否使用此功能），将应用方法建议。然而，Spring 无法创建……（等待，根据提供的 OCR，文本似乎是碎片化/损坏的）。

*注意：提供的第 642-643 页 OCR 文本包含严重的结构性问题和重复，这是低质量扫描的典型特征。我已根据提供的可见内容清理了逻辑流。*

```java
public PlatformTransactionManager jpaTransactionManager()
{
    return new JpaTransactionManager(
        this.entityManagerBean().getObject()
    );
}

@Override
public PlatformTransactionManager annotationDrivenTransactionManager()
{
    return this.jpaTransactionManager();
}
```

注意，此方法简单调用了 `@Bean jpaTransactionManager` 方法，以便确保选定的 bean 名称 (`jpaTransactionManager`) 被保留。

# 创建和使用 JPA 存储库

在 Spring 存储库中使用 JPA 比单独使用 JPA 容易得多，因为你不需要处理事务和 `EntityManagerFactory`。本节将展示实现这些操作的步骤，以及如何在服务层中装饰边界。你还可以创建一个泛型存储库，以便使用通用代码处理许多不同类型的实体。Spring-JPA 项目使用了你自己在上一节中创建的 Book、Author 和 Publisher 实体（去除了 Book 的 `previewProperty` 属性），并使用了相同的数据库创建脚本，只是数据库名称改为了 `SpringJpa`。

# 注入持久化单元

你将拥有三个存储库 —— 每个实体一个。这是一种常见且实用的模式，但并非必须。例如，你可以为几个相关的实体创建一个存储库。但每个实体使用一个存储库允许你创建泛型存储库代码，这是你在本节稍后部分将学习的内容。每个存储库都实现一个接口，你将在该节中详细探讨。

```java
public interface AuthorRepository { ... }
public interface BookRepository { ... }
public interface PublisherRepository { ... }
```

为了在存储库实现中执行 JPA 操作，你需要一个 `EntityManager` 实例。正如前面讨论的，你所做的只是声明一个 `EntityManager` 字段并用 `@PersistenceContext` JPA 注解将其标记。你不需要在字段上使用 `@Inject` 或 `@Autowired` 注解；`@PersistenceContext` 也能起到此作用。由于 `@PersistenceContext` 已经提供了 Spring 对 JPA 的支持，因此没有对应的 Spring 版本的 `@PersistenceContext`，所以你只需要关注这一个注解即可。

```java
@Repository
public class DefaultAuthorRepository implements AuthorRepository
{
    @PersistenceContext EntityManager entityManager;
...
@Repository
public class DefaultBookRepository implements BookRepository
{
    @PersistenceContext EntityManager entityManager;
    ...
}
@Repository
public class DefaultPublisherRepository implements PublisherRepository
{
    @PersistenceContext EntityManager entityManager;
    ...
}
```

你可能记得在本节前面提到注入的 `EntityManager` 并不是由 JPA 供应商（Hibernate ORM）提供的。它是真实对象的代理，并会自动委托给在该事务中上一个方法调用创建的与事务关联且线程绑定的 `EntityManager`（如果尚未创建，则创建一个新的 `EntityManager` 和事务）。

# 实现标准 CRUD 操作

对于你的存储库，你只需要执行简单的操作 —— 返回单个实体和实体列表、添加实体、更新实体以及删除实体。这在 `AuthorRepository` 接口中可以很容易表示。

```java
public interface AuthorRepository
{
    Iterable<Author> getAll();

    Author get(long id);

    void add(Author author);

    void update(Author author);

    void delete(Author author);

    void delete(long id);
}
```

列表 21-1 中对这些方法的实现采用了不同的准则方法，与你在上一节的 Servlet 中使用的方法略有不同。它没有使用 Criteria API，而是使用 Java 持久查询语言 (JPQL) 来查找实体。如你所见，JPQL 与 ANSI SQL 非常相似；但它们存在一些差异。例如，SELECT 子句中的标识符标识的是返回哪些实体，而不是 SQL 查询中返回哪些列。JPQL 查询可以在 WHERE 子句中使用多个实体，但在 SELECT 子句中只返回其中一个。此外，FROM 子句中的标识符标识的是实体名称，而不是 SQL 查询中的表名。

### 列表 21-1：DefaultAuthorRepository.java

```java
@Repository
public class DefaultAuthorRepository implements AuthorRepository {
    @PersistenceContext EntityManager entityManager;

    @Override
    public Iterable<Author> getAll() {
        return this.entityManager.createQuery(
            "SELECT a FROM Author a ORDER BY a.name", Author.class
        ).getResultList();
    }

    @Override
    public Author get(long id) {
        return this.entityManager.createQuery(
            "SELECT a FROM Author a WHERE a.id = :id", Author.class
        ).setParameter("id", id).getSingleResult();
    }

    @Override
    public void add(Author author) {
        this.entityManager.persist(author);
    }

    @Override
    public void update(Author author) {
        this.entityManager.merge(author);
    }

    @Override
    public void delete(Author author) {
        this.entityManager.remove(author);
    }

    @Override
    public void delete(long id) {
        this.entityManager.createQuery(
            "DELETE FROM Author a WHERE a.id = :id"
        ).setParameter("id", id).executeUpdate();
    }
}
```

# 为所有实体创建基础存储库

思考一下 `AuthorRepository` 及其指定的方法，然后思考 `BookRepository` 和 `PublisherRepository` 应该指定的方法。你会立即发现它们之间存在相似性：

```java
public interface BookRepository {
    Iterable<Book> getAll();
    Book get(long id);
    void add(Book book);
    void update(Book book);
    void delete(Book book);
    void delete(long id);
}
```

```java
public interface PublisherRepository {
    Iterable<Publisher> getAll();
    Publisher get(long id);
    void add(Publisher publisher);
    void update(Publisher publisher);
    void delete(Publisher publisher);
    void delete(long id);
}
```

如果你考虑这些方法的实现，会很快意识到它们与 `AuthorRepository` 几乎完全相同。你可能会怀疑是否有一种可以处理你所有实体的代码。为了尽可能有用，这样的存储库需要使用泛型。从接口开始，考虑它可能的形式如下：

```java
@Validated
public interface GenericRepository<I extends Serializable, E extends Serializable> {
    @NotNull
    Iterable<E> getAll();
    E get(@NotNull I id);
    void add(@NotNull E entity);
    void update(@NotNull E entity);
    void delete(@NotNull E entity);
    void deleteById(@NotNull I id);
}
```

泛型变量 `I` 代表实体的代理键 —— 通常是 `long`，但并不总是，所以它是变量。`E` 代表实体类型。Bean Validation 的 `@NotNull` 约束是告诉存储库用户和实现者不允许空参数的好方法。由于这里 `I` 和 `E` 的歧义（理论上它们可以是相同类型），编译器无法区分类型 `I` 的方法参数和类型 `E` 的方法参数。因此，`delete` 和 `deleteById` 方法名称不同。

> 注意：JPA 并不严格要求实体或其代理键实现 `Serializable`，但这是一个最佳实践限制。

现在你的存储库接口需要扩展这个父接口，并指定适用于它们提供的实体的类型变量。

```java
public interface AuthorRepository extends GenericRepository<Long, Author>
{}
public interface BookRepository extends GenericRepository<Long, Book>
{
    Book getByIsbn(String isbn);
}
public interface PublisherRepository extends GenericRepository<Long, Publisher>
{
}
```

下一步是为所有 `GenericRepository` 定义通用实现。从 Java 8 开始，你可以采用默认方法的独特方法：

```java
@Validated
public interface GenericRepository<I extends Serializable, E extends Serializable>
{
    @NotNull
    default Iterable<E> getAll()
}
```

- 默认方法的设计目的并不是替换抽象类。它们的创建是为了让你能够在不破坏现有实现的情况下进行改进。例如，Java 8 集合使用了默认方法进行改进，而没有破坏成千上万现有 `Collection`、`List`、`Set`、`Map`、`Iterable` 和 `Iterator` 实现。默认方法的语义与抽象类中的具体方法不同，不应用于此类目的。

然而，出于某些原因，这是一个糟糕的选择：

你需要的注入的 `EntityManager` 来在这些方法中执行代码，而你无法在接口中获取它。



# 在 Spring Framework 中使用 JPA

## 泛型基类实现

你需要 `I` 和 `E` 的类型（`Class`）来执行安全的 JPA 操作。实现此点的最佳方法（如果你想让这些值变为 `final`）是在构造函数中，而接口无法拥有构造函数。

更合适的方法是使用泛型基类，这可以满足你的所有需求。在决定如何实现时，你可能需要考虑几个因素。首先是如何确定类型变量的 `Class` 实例。最简单的方法是在构造函数中要求它们：

```java
public abstract class GenericBaseRepository<I extends Serializable, E extends Serializable>
    implements GenericRepository<I, E> {
    protected final Class<I> idClass;
    protected final Class<E> entityClass;

    public GenericBaseRepository(Class<I> idClass, Class<E> entityClass) {
        this.idClass = idClass;
        this.entityClass = entityClass;
    }
}
```

这种方法行得通，但当信息已经存在于实现的类型变量中时，仍然要求这些构造函数参数似乎很蠢。幸运的是，你可以访问这些类型变量的参数，尽管没有它们是不可能的。

```java
public abstract class GenericBaseRepository<I extends Serializable, E extends Serializable>
    implements GenericRepository<I, E> {
    protected final Class<I> idClass;
    protected final Class<E> entityClass;

    @SuppressWarnings("unchecked")
    public GenericBaseRepository() {
        Type genericSuperclass = this.getClass().getGenericSuperclass();
        while (!(genericSuperclass instanceof ParameterizedType)) {
            if (genericSuperclass instanceof Class) {
                throw new IllegalStateException("Unable to determine type " + "arguments because generic superclass " + "parameterized type nor class.");
            }
            if (genericSuperclass == GenericBaseRepository.class) {
                throw new IllegalStateException("Unable to determine type " + "arguments because no parameterized generic superclass " + "found.");
            }
            genericSuperclass = ((Class) genericSuperclass).getGenericSuperclass();
        }
        ParameterizedType type = (ParameterizedType) genericSuperclass;
        Type[] arguments = type.getActualTypeArguments();
        this.idClass = (Class) arguments[0];
        this.entityClass = (Class<E>) arguments[1];
    }
}
```

这个构造函数可能会让你困惑，除非我们逐条分析它。当一个类扩展 `GenericBaseRepository` 时，该类的父类就是 `GenericBaseRepository`。更重要的是，它的泛型父类因此应该是一个带有类型参数的 `ParameterizedType`。你可以直接调用 `((ParameterizedType) this.getGenericSuperclass()).getActualTypeArguments()`，但只有在每个仓库都继承自 `GenericBaseRepository` 且为 `final` 的情况下才有效。这种限制是不理想的，因为它无法配合 Spring Framework 的事务处理和异常翻译工作。因此，沿着继承树向上循环，检查每个类型直到找到 `ParameterizedType`。如果遇到一个不是 `Class` 的类型，它就无法继续遍历树。如果它遇到自己的类型，它将继续向上遍历。这两种情况都可以被认为是不可能的，但值得测试。当它找到 `ParameterizedType` 时，它就找到了指定类型参数的父类。它从类型中检索这些参数并将它们分配给字段。

这个构造函数是 `GenericBaseRepository` 提供的唯一价值。它不提供 `EntityManager` 或方法实现，因为你可能想在应用程序中拥有多个 JPA 和非 JPA 仓库。确定类型参数属于它的子类。`GenericJpaRepository` 处理了所有的 JPA 交互工作。

## LISTING 21-2: GenericJpaRepository.java

```java
public abstract class GenericJpaRepository<I extends Serializable, E extends Serializable>
    extends GenericBaseRepository<I, E> {

    @PersistenceContext
    protected EntityManager entityManager;

    @Override
    public Iterable<E> getAll() {
        CriteriaBuilder builder = this.entityManager.getCriteriaBuilder();
        CriteriaQuery<E> query = builder.createQuery(this.entityClass);

        return this.entityManager.createQuery(
            query.select(query.from(this.entityClass))
        ).getResultList();
    }

    @Override
    public E get(I id) {
        return this.entityManager.find(this.entityClass, id);
    }

    @Override
    public void add(E entity) {
        this.entityManager.persist(entity);
    }

    @Override
    public void update(E entity) {
        this.entityManager.merge(entity);
    }

    @Override
    public void delete(E entity) {
        this.entityManager.remove(entity);
    }

    @Override
    public void deleteById(I id) {
        CriteriaBuilder builder = this.entityManager.getCriteriaBuilder();
        CriteriaDelete<E> query = builder.createCriteriaDelete(this.entityClass);

        this.entityManager.createQuery(query).where(
            builder.equal(query.from(this.entityClass)).get("id"), id)
        ).executeUpdate();
    }
}
```

关于上述代码的几点说明：

- `OriginalRepository` 展示了 Java 持久查询语言，但当你不知道实际实体名称时（在泛型仓库中无法知道），这并不容易使用。`GenericJpaRepository` 而是使用 Criteria API 来返回所有实体列表并按 ID 删除。
- `deleteById` 方法只有在你的所有实体都有命名为 `id` 的属性时才有效，这是通常的情况。如果代理键属性名称不同，你必须获取实体然后调用 `remove` 方法。
- `AuthorRepository` 和 `DefaultPublisherRepository` 不再需要方法，因为它们已经定义在 `GenericJpaRepository` 中。
- 只有 `DefaultBookRepository` 需要一个方法，实现了 `BookRepository` 接口中的 `getByISBN` 方法。

```java
@Repository
public class DefaultAuthorRepository extends GenericJpaRepository<Long, Author>
    implements AuthorRepository {
}
```

```java
public class DefaultBookRepository extends GenericJpaRepository<Long, Book> {
    @Override
    public Book getByIsbn(String isbn) {
        CriteriaBuilder builder = this.entityManager.getCriteriaBuilder();
        CriteriaQuery<Book> query = builder.createQuery(Book.class);
        Root<Book> root = query.from(Book.class);

        return this.entityManager.createQuery(
            query.select(root).where(builder.equal(root.get("isbn"), isbn))
        ).getSingleResult();
    }
}
```

```java
@Repository
public class DefaultPublisherRepository extends GenericJpaRepository<Long, Publisher>
    implements PublisherRepository {
}
```

JPA ORM 的 API 不是最直观的 Criteria API，而且比 Hibernate API 更难使用，后者被设计用于便于为每个查询添加表达式和限制，而此 API 设计是为了模拟查询语言本身。`GenericJpaRepository` 中的 `getAll` criteria 实际上可以读为“Select entity”，这与你为此目的创建的 JPQL 查询相同，只是缺少排序指令。使用 Criteria API 进行排序并不困难。你可以根据需要重写方法，或者指定一个子类使用的构造函数参数来指定默认排序指令。

```java
Root<Book> root = query.from(Book.class);

return this.entityManager.createQuery(
    query.select(root).orderBy(builder.asc(root.get("name")))
).getResultList();
```

## 在服务中划分事务边界

正如提到的，你使用 Spring 的 `@Transactional` 注解或 JTA 的 `@Transactional` 注解来告诉 Spring Framework 何时开始和结束事务。Spring 的注解比 JTA 的注解稍微强大且灵活得多。

使用 `@javax.transaction.Transactional`，你可以通过 `dontRollbackOn` 属性定义一个不触发回滚的异常黑名单；通过 `rollbackOn` 定义一个用于覆盖 `RuntimeExceptions` 默认回滚规则的异常白名单；并使用 `Transactional.TxType` 枚举值属性定义事务的创建规则。`Transactional.TxType` 具有以下枚举常量：

- `MANDATORY`：必须已经存在事务，如果事务不存在事务，则必须抛出异常。
- `NEVER`：表示不能已经存在事务，不能使用事务，如果已经存在事务，则必须抛出异常。
- `NOT_SUPPORTED`：意味着不能使用事务，如果已经存在事务，则必须将其挂起，以便代码在事务之外执行。当代码执行完毕后，必须恢复任何被挂起的事务。
- `REQUIRED`：意味着必须使用事务。如果不存在事务，则应在方法执行前启动事务，并在方法返回后提交。如果已经存在事务，则应该使用它，并允许它在方法返回后继续。
- `REQUIRED_NEW`：顾名思义。与 `REQUIRED` 类似，它表示如果不存在事务，应在方法执行前启动事务，并在方法返回后提交。然而，如果已经存在事务，则应将其挂起，并在方法执行前启动一个新事务，在方法返回后恢复原始事务。
- `SUPPORTS`：可能是最灵活的指令。意味着如果已存在事务则必须使用它，如果不存在事务，方法将在没有事务的情况下执行。

`@org.springframework.transaction.annotation.Transactional` 具有 `noRollbackFor`、`rollbackFor` 和 `propagation` 属性，其语义与 JTA 注解中的 `noRollbackOn`、`rollbackOn` 相同。它还具有 `noRollbackForClassName` 和 `rollbackForClassName` 属性。`org.springframework.transaction.annotation.Propagation` 枚举具有与 `Transactional.TxType` 相同的常量和含义。

此外，`Propagation` 具有一个 `NESTED` 常量，它在已存在事务时创建一个嵌套事务，在不存在事务时创建一个新事务。在使用 `JpaTransactionManager` 时不支持 `NESTED`。在配合某些 JTA 提供程序使用 `JtaTransactionManager` 时可能支持，但它不具备移植性。`@Transactional` 注解的默认规则是 `REQUIRED`，在几乎所有情况下，它对你的需求都是足够的。

Spring 的注解还包含其他几个属性。`isolation` 允许你使用 `org.springframework.transaction.annotation.Isolation` 指定事务隔离级别。该属性被 `JpaTransactionManager` 和 `JtaTransactionManager` 不支持并会被忽略。这些管理器的事务隔离级别是 JPA 或 JTA `DataSource` 配置中指定的隔离级别，或者在 `DataSource` 中未指定时使用 JDBC 驱动的默认隔离级别。由于默认值在不同的 JDBC 驱动之间有所不同，因此在定义时最好始终指定隔离级别。

### DataSource 资源

可用的隔离级别有 `NONE`、`READ_COMMITTED`、`READ_UNCOMMITTED`、`REPEATABLE_READ`、`SERIALIZABLE`。关于这些含义的更多信息，你应该咨询数据库服务器的文档。在本书中你使用的是 `READ_COMMITTED`。

`readOnly` 是 Spring `@Transactional` 注解中的另一个属性，`JpaTransactionManager` 或 `JtaTransactionManager` 不支持它。它指示底层事务系统在事务中禁止写入操作，默认值为 `false`。`timeout` 属性在使用 `JtaTransactionManager` 时被支持，但在使用 `JpaTransactionManager` 时不支持。它限制了事务在因异常或回滚结束之前可以消耗的时间。

当使用 JTA `@Transactional` 注解时，Spring 始终使用默认的 `PlatformTransactionManager`。记住，在没有 `TransactionManagementConfigurer` 的情况下，它是由 `TransactionManagementConfigurer` 返回的；如果只有一个，它就是唯一的事务管理器。可以配合多个 `PlatformTransactionManager` Bean 使用 Spring 的 `@Transactional` 注解。如果你省略 `value`，它将使用默认事务管理器，但你可以在 `value` 属性中指定 Bean 名称，并使用该 Bean 的 `PlatformTransactionManager`。



@Configuration
@EnableTransactionManagement(
    mode = Advice.PROXY, proxyTargetClass = false,
    order = Ordered.LOWEST_PRECEDENCE
)
public class RootContext implements TransactionManagementConfigurer {
    @Bean
    public PlatformTransactionManager jpaTransactionManager() {
        return new JpaTransactionManager(
            this.entityManagerFactory().getObject()
        );
    }

    @Bean
    public PlatformTransactionManager dataSourceTransactionManager() {
        return new DataSourceTransactionManager(this.springJpaDataSource());
    }

    @Override
    public PlatformTransactionManager annotationDrivenTransactionManager() {
        return this.jpaTransactionManager();
    }
}

之前的配置创建了两个 `PlatformTransactionManager` Bean，一个用于 JPA，一个用于简单的 `DataSource` 操作。`JpaTransactionManager`充当默认事务管理器。使用此配置，后续服务中的 `actionOne` 方法在默认（JPA）事务管理器的控制下执行。同样，`actionTwo` 显式使用 `JpaDataSourceTransactionManager` 执行，而 `actionThree` 则显式地使用 `DataSourceTransactionManager` 执行。

```java
public class SomeService
{
    @Transactional
    public void actionOne();

    @Transactional("jpaTransactionManager")
    public void actionTwo();

    @Transactional("dataSourceTransactionManager")
    public void actionThree();
}
```

当使用 `@Transactional` 注解时，你可以注解接口、单个方法、类或方法。如果你注解一个接口，它等同于注解该接口的方法。同样，注解一个类等同于注解该类的方法。当你的应用程序代码需要声明事务边界时，最佳实践是注解具体的类，而不是接口。`@Transactional` 仅在使用动态代理（`proxyTargetClass = false`）时有效。除非你需要使用 CGLIB 代理（这在接口上建立约定），否则 `@Transactional` 是实现细节，不应属于约定。在 21-3 的 `DefaultBookManager` 中展示了注解方法。`@Transactional` 方法可以在同一个事务范围内访问并管理多个实体。

# 列表 21-3：DefaultBookManager.java

```java
@Service
public class DefaultBookManager implements BookManager
{
    @Inject AuthorRepository authorRepository;
    @Inject BookRepository bookRepository;
    @Inject PublisherRepository publisherRepository;

    @Override
    public List<Author> getAuthors() {
        return this.toList(authorRepository.getAll());
    }

    @Override
    public List<Book> getBooks() {
        return this.toList(bookRepository.getAll());
    }
}
```

继续

```java
@Override
public List<Publisher> getPublishers()
{
    return this.toList(publisherRepository.getAll());
}

private <E> List<E> toList(Iterable<E> i)
{
    List<E> list = new ArrayList<E>();
    i.forEach(list::add);
    return list;
}

@Override
public void saveAuthor(Author author)
{
    if (author.getId() < 1)
        authorRepository.add(author);
    else
        authorRepository.update(author);
}

@Override
public void saveBook(Book book)
{
    if (book.getId() < 1)
        bookRepository.add(book);
    else
        bookRepository.update(book);
}

@Override
public void savePublisher(Publisher publisher)
{
    if (publisher.getId() < 1)
        publisherRepository.add(publisher);
    else
        publisherRepository.update(publisher);
}
```

# 使用事务服务方法

在使用 `@Transactional` 服务方法时，你不需要做任何操作。从消费者的角度来看，事务是自然发生的。`BookController` 的工作类似于第 20 章中的 `EntityServlet`：它为 GET 请求列出作者、书籍和出版社，并在 POST 请求创建它们。

```java
@WebController
public class BookController {
    private final Random random;

    @Inject BookManager bookManager;

    public BookController() {
        try {
            this.random = SecureRandom.getInstanceStrong();
        } catch (NoSuchAlgorithmException e) {
            throw new IllegalStateException(e);
        }
    }

    @RequestMapping(value = "", method = RequestMethod.GET)
    public String list(Map<String, Object> model) {
        model.put("publishers", this.bookManager.getPublishers());
        model.put("authors", this.bookManager.getAuthors());
        model.put("books", this.bookManager.getBooks());
        return "entities";
    }

    @RequestMapping(value = "/", method = RequestMethod.POST)
    public void add() {
        Publisher publisher = new Publisher();
        publisher.setName("John Wiley & Sons");
        publisher.setAddress("1234 Baker Street");
        publisher.setDateFounded(Calendar.getInstance());
        this.bookManager.save(publisher);

        Author author = new Author();
        author.setName("Nicholas S. Williams");
        author.setEmail("nick@example.com");
        author.setGender(Gender.MALE);
        this.bookManager.save(author);

        Book book = new Book();
        book.setISBN("" + this.random.nextInt(Integer.MAX_VALUE));
        book.setTitle("Professional Java for Web Applications");
        book.setAuthor("Nicholas S. Williams");
        book.setPublisher("John Wiley & Sons");
        book.setPrice("$59.95");
        this.bookManager.save(book);
        return new RedirectView("/", true, false);
    }
}
```

624 | 第 21 章 在 SPRING FRAMEWORK REPOSITORIES 中使用 JPA

要对其进行测试，请按照以下步骤操作：

1. 确保在 Tomcat 的 `context.xml` 文件中有 DataSource 资源定义，并在 MySQL Workbench 中运行 `create.sql` 数据库创建脚本以创建必要的数据库表。

```xml
<Resource name="jdbc/SpringJpa" type="javax.sql.DataSource"
maxActive="20" maxIdle="5" maxWait="10000"
username="tomcatUser" password="password1234"
driverClassName="com.mysql.jdbc.Driver"
defaultTransactionIsolation="READ_COMMITTED"
url="jdbc:mysql://localhost/SpringJpa" />
```

2. 编译应用并从 IDE 启动 Tomcat。

3. 访问 http://localhost:8080/repositories/ 并点击几次“Add More Entities”按钮，就像你在上一章中做过的那样。

你应该能看到浏览器和数据库表中都出现了实体的身影。通过 ID（以及 ISBN）查找单个实体是留给你的完成的练习。

## 将数据转换为 DTO 和实体

从 wrox.com 网站下载的 Customer-Support v15 应用使用了你在 Spring-Jpa 中配置的 `LocalEntityManagerFactoryBean` 和事务管理。它还具有相同的通用存储库 `GenericRepository` 接口和 `GenericBaseRepository` 类。然而，将 Customer Support 应用更改为使用 JPA 存储库和 MySQL 数据库并不那么简单。`Ticket` 类具有一些你无法使用目前所学的 JPA 机制进行转换的属性——创建的实例（Instance）和属性映射（Map）。最简单的方法是将 `Ticket` 视为数据传输对象 (DTO)，并创建一个单独的 `TicketEntity` 以持久化到数据库。

## 为 Customer Support 应用创建实体

你需要在应用程序中几个不同的实体，并且只需要将它们移动到 `com.wrox.site.entities`，进行注解，并赋予它们 ID 属性以及指向 ticket 的外键。

```java
@XmlRootElement(name = "attachment")
@Entity
public class Attachment implements Serializable
{
    private static final long serialVersionUID = 1L;

    private long id;
    private long ticketId;
    @NotBlank(message = "${validate.attachment.name}")
    private String name;
    @NotBlank(message = "${validate.attachment.mimeContentType}")
    private String mimeContentType;
    @Size(min = 1, message = "${validate.attachment.contents}")

    private byte[] contents;

    @Id
    @Column(name = "AttachmentId")
    @GeneratedValue(strategy = Generation.IDENTITY)
    public long getId() { ... }

    public void setId(long id) { ... }

    @Basic
    public long getTicketId() { ... }

    public void setTicketId(long ticketId) { ... }

    @Basic
    @Column(name = "AttachmentName")
    public String getName() { ... }

    public void setName(String name) { ... }

    @Basic
    public String getMimeContentType() { ... }

    public void setMimeContentType(String mimeContentType) { ... }

    @XmlSchemaType(name = "base64Binary")
    @Lob
    public byte[] getContents() { ... }

    public void setContents(byte[] contents) { ... }
}
```

`UserRepository` 和 `UserPrincipal` 发生了显著变化，因为用户现在存储在数据库中。`UserRepository` 也移动到了 `com.wrox.site.entities` 包中，并拥有 ID、用户名和密码。你永远不应该以明文甚至哈希的形式在数据库中存储密码，因此密码将使用盐值（salt）进行强力持久化。

```java
@Entity
@Table(uniqueConstraints = {
    @UniqueConstraint(name="UserPrincipal_
```

```java
@Basic
@Column(name = "AttachmentName")
public String getName() { ... }

public void setName(String name) { ... }

@Basic
public String getMimeContentType() { ... }

public void setMimeContentType(String mimeContentType) { ... }

@XmlSchemaType(name = "base64Binary")
@Lob
public byte[] getContents() { ... }

public void setContents(byte[] contents) { ... }
```

`UserRepository` 和 `UserPrincipal` 发生了显著变化，因为用户现在存储在数据库中。`UserRepository` 也移动到了 `com.wrox.site.entities` 包中，并拥有 ID、用户名和密码。你永远不应该以明文甚至哈希的形式在数据库中存储密码，因此密码将使用盐值进行强力持久化。

```java
@Entity
@Table(uniqueConstraints = {
    @UniqueConstraint(name="UserPrincipal_
```

```java
@Basic
@Column(name = "AttachmentName")
public String getName() { ... }

public void setName(String name) { ... }

@Basic
public String getMimeContentType() { ... }

public void setMimeContentType(String mimeContentType) { ... }

@XmlSchemaType(name = "base64Binary")
@Lob
```



## 实体定义

```java
public byte[] getContents() { ... }

public void setContents(byte[] contents) { ... }
```

`UserRepository` 和 `UserPrincipal` 发生了显著变化，因为用户现在存储在数据库中。`UserRepository` 也移动到了 `com.wrox.site.entities` 包中，并拥有 ID、用户名和密码。你永远不应该以明文甚至哈希的形式在数据库中存储密码，因此密码将使用盐值进行强力持久化。

```java
@Entity
@Table(uniqueConstraints = {
    @UniqueConstraint(name="UserPrincipal_")
})
```

```java
@Basic
@Column(name = "AttachmentName")
public String getName() { ... }

public void setName(String name) { ... }

@Basic
public String getMimeContentType() { ... }

public void setMimeContentType(String mimeContentType) { ... }
```

```java
@XmlSchemaType(name = "base64Binary")
@Lob
public byte[] getContents() { ... }

public void setContents(byte[] contents) { ... }
```

## 数据库架构

```sql
CREATE DATABASE CustomerSupport;
USE CustomerSupport;

CREATE TABLE UserPrincipal (
    UserId BIGINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    Username VARCHAR(30) NOT NULL,
    HashedPassword BINARY(60) NOT NULL,
    UNIQUE KEY (Username)
) ENGINE = InnoDB;

CREATE TABLE Ticket (
    TicketId BIGINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    UserId BIGINT NOT NULL,
    Subject VARCHAR(255) NOT NULL,
    Body TEXT,
    Created DATETIME NOT NULL,
    CONSTRAINT Ticket_User FOREIGN KEY (UserId)
    REFERENCES UserPrincipal (UserId) ON DELETE CASCADE
) ENGINE = InnoDB;

CREATE TABLE Attachment (
    AttachmentId BIGINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    TicketId BIGINT NOT NULL,
    AttachmentName VARCHAR(255) NOT NULL,
    MimeType VARCHAR(255) NOT NULL,
    Contents BLOB NULL,
    CONSTRAINT Attachment_TicketId FOREIGN KEY (TicketId)
    REFERENCES Ticket (TicketId) ON DELETE CASCADE
) ENGINE = InnoDB;

INSERT INTO UserPrincipal (Username, HashedPassword) VALUES ('Nicholas', '$2a$10S0k/yaQGN8S8JDCSen.6lEbXvHetdty.RprajRR5S1KC');
INSERT INTO UserPrincipal (Username, HashedPassword) VALUES ('Sarah', '$2a$10SjKyMo.J0BTT42/4RfZtaUYKZLcFeND1b0r7yWH08y');
INSERT INTO UserPrincipal (Username, HashedPassword) VALUES ('Mike', '$2a$10cwSStNd.99hfRfcbCt.ECAV0a9/QpbWnfjCMovdTT4ISG');
INSERT INTO UserPrincipal (Username, HashedPassword) VALUES ('John', '$2a$10vacqugB97trRR8ByKytoZqThemQfnK3X2W1La7v/3Amby');
```

## 仓库实现

用于实体。接口继承 `GenericRepository`，实现继承 `GenericJpaRepository`。`UserRepository` 需要自定义方法实现以便通过用户名查找用户，而 `AttachmentRepository` 提供了一个查找特定 ticket 附件的方法。

```java
public interface UserRepository extends GenericRepository<Long, UserPrincipal> {
    UserPrincipal getByUsername(String username);
}
```

```java
@Repository
public class DefaultUserRepository
    extends GenericJpaRepository<Long, UserPrincipal>
    implements UserRepository {

    @Override
    public UserPrincipal getByUsername(String username) {
        return this.entityManager.createQuery(
            "SELECT u FROM UserPrincipal u WHERE username = :username",
            UserPrincipal.class
        ).setParameter("username", username).getSingleResult();
    }
}
```

```java
public interface TicketRepository extends GenericRepository<Long, TicketEntity> {
}

@Repository
public class DefaultTicketRepository
    extends GenericJpaRepository<Long, TicketEntity>
    implements TicketRepository {
}
```

```java
public interface AttachmentRepository extends GenericRepository<Long, Attachment> {
    Iterable<Attachment> getByTicketId(long ticketId);
}

@Repository
public class DefaultAttachmentRepository
    extends GenericJpaRepository<Long, Attachment>
    implements AttachmentRepository {

    @Override
    public Iterable<Attachment> getByTicketId(long ticketId) {
        return this.entityManager.createQuery(
            "SELECT a FROM Attachment a WHERE a.ticketId = :id ORDER BY a.id",
            Attachment.class
        ).setParameter("id", ticketId).getResultList();
    }
}
```

## 使用 BCrypt 保护密码

你需要更新 Support 中的服务以使用新的存储库。`TemporaryAuthenticationService` 已重命名为 `DefaultAuthenticationService`，它现在更加安全，因为它使用了由 Maven 依赖提供的行业标准 BCrypt 哈希算法。

```xml
<dependency>
  <groupId>org.mindrot</groupId>
  <artifactId>bcrypt</artifactId>
  <version>0.3</version>
</dependency>
```

当正确使用时，BCrypt 是极其强大的。它的设计初衷是极其缓慢。这看起来可能违背直觉，但实际上，性能影响体现在登录或保存用户期间。对每个密码使用不同的盐对于破解的数据库来说成本极高且不切实际。

你永远不要使用像 MD5 或任何 SHA 算法这样的快速哈希算法，因为现代密码破解系统每秒可以产生数十亿比较。BCrypt 是迄今为止最强大且经过充分测试的密码哈希算法，在保护密码时你应该坚持使用它。它使用以 2 的幂表示的迭代次数来确定哈希轮数。例如，当迭代次数为 10 时，哈希会被应用 1024 次。每一轮都会使用固定数量的内存，这使得仅通过硬件很难实现，因此现代密码破解系统每秒可以生成许多微小的比较。列表 21-4 中的 `DefaultAuthenticationService` 使用 `UserRepository` 和 BCrypt 来保存和验证用户。

### 列表 21-4：DefaultAuthenticationService.java

```java
@Service
public class DefaultAuthenticationService implements AuthenticationService {

    private static final Logger log = Logger.getLogger(DefaultAuthenticationService.class);

    private static SecureRandom RANDOM;

    private static final int HASHING_ROUNDS = 10;

    static {
        try {
            RANDOM = SecureRandom.getInstanceStrong();
        } catch (NoSuchAlgorithmException e) {
            throw new IllegalStateException(e);
        }
    }

    @Inject
    UserRepository userRepository;

    @Override
    @Transactional
    public UserPrincipal authenticate(String username, String password) {
        UserPrincipal principal = this.userRepository.getByUsername(username);

        if (principal == null) {
            log.warn("Authentication failed for non-existent user {}.", username);
            return null;
        }

        if (!BCrypt.checkpw(
            password,
            new String(principal.getPassword(), Charsets.UTF_8)
        )) {
            log.warn("Authentication failed for user {}.", username);
            return null;
        }

        log.debug("User {} successfully authenticated.", username);
        return principal;
    }

    @Override
    @Transactional
    public void saveUser(UserPrincipal principal, String newPassword) {
        if (newPassword != null && newPassword.length() > 0) {
            String salt = BCrypt.gensalt(HASHING_ROUNDS, RANDOM);
            principal.setPassword(BCrypt.hashpw(newPassword, salt).getBytes());
        }

        if (principal.getId() < 1)
            this.userRepository.add(principal);
        else
            this.userRepository.update(principal);
    }
}
```

## 将数据传输到你的服务

列表 21-5 中的 `DefaultTicketService` 使用新的 `TicketRepository` 和 `AttachmentRepository` 来获取和保存 `Ticket` 和 `TicketEntity`。由于应用程序使用了 `Ticket` 但数据库持久化的是 `TicketEntity`，因此在整个 `DefaultTicketService` 中，数据必须在这两个 POJO 之间传输。代码大量使用了 Lambda、方法引用和 Java 8 集合流 API 来减少实现此目标所需的代码。

### 列表 21-5：DefaultTicketService.java

```java
@Service
public class DefaultTicketService implements TicketService {

    @Inject
    TicketRepository ticketRepository;

    @Inject
    AttachmentRepository attachmentRepository;

    @Inject
    UserRepository userRepository;

    @Override
    @Transactional
    public List<Ticket> getAllTickets() {
        List<Ticket> list = new ArrayList<>();
        this.ticketRepository.getAll().forEach(e -> list.add(this.convert(e)));
        return list;
    }

    @Override
    @Transactional
    public Ticket getTicket(long id) {
        TicketEntity entity = this.ticketRepository.get(id);
        return entity == null ? null : this.convert(entity);
    }

    private Ticket convert(TicketEntity entity) {
        Ticket ticket = new Ticket();
        ticket.setId(entity.getId());
        ticket.setCustomerName(entity.getCustomerName());
        ticket.setSubject(entity.getSubject());
        ticket.setDescription(entity.getDescription());
        ticket.setAttachments(entity.getAttachments());
        return ticket;
    }

    @Override
    @Transactional
    public void deleteTicket(long id) {
        this.ticketRepository.deleteById(id);
    }
}
```

# 第 22 章：使用 Spring Data JPA 消除样板代码仓库

## 本章内容

- 理解 Spring Data 的统一数据访问
- 创建 Spring Data JPA 仓库
- 如何重构 Customer Support 应用程序

## 本章的 WROX.COM 代码下载

你可以在 <http://www.wrox.com/projectjavaforwebabbaps> 的 "Download Code" 选项卡中找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Spring-Data-JPA 项目
- Customer-Support-v16 项目

## 本章的新 MAVEN 依赖

除了之前章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖。排除 SLF4J JCL 桥接是因为你使用了 Log4j 2，这使得该桥接变得不再必要。

```xml
<dependency>
  <groupId>org.springframework.data</groupId>
  <artifactId>spring-data-jpa</artifactId>
</dependency>
```



```xml
<version>1.5.0.RELEASE</version>

<scope>compile</scope>

<exclusions>

  <exclusion>

    <groupId>org.slf4j</groupId>

    <artifactId>jcl-over-slf4j</artifactId>

  </exclusion>

</exclusions>

</dependency>

<dependency>

  <groupId>org.slf4j</groupId>

  <artifactId>slf4j-api</artifactId>

  <version>1.7.5</version>

  <scope>runtime</scope>

</dependency>
```

# 理解 Spring Data 的统一数据访问

在第 20 章中，你学习了持久化 API 有多强大，在第 21 章中，你学习了 Spring Framework 如何让 JPA 变得更加简单。Spring 处理所有的事务管理和 `EntityManager` 的创建，你不需要自己去做这些。它消除了在应用程序中包含 `persistence.xml` 文件的需求！最重要的是，你创建了一个通用的基仓库，所有的仓库都可以扩展它，提供了基本的 CRUD 操作，而无需为每个仓库重复编写这些操作。

但让我们面对现实吧：你的大多数仓库都需要匹配标准的 CRUD 操作。首先，你通常需要根据主键以外的唯一列进行基本查找。在 Spring-JPA 项目的最后一章中，你添加了一个通过 ISBN 查找书籍的方法，而在 Customer-Support-v15 项目中，你的 `UserRepository` 包含了一个通过用户名查找用户的方法。

然后，你可能需要根据多个字段查找实体。例如，作为系统管理员，你可能需要根据姓、名或电话号码查找人员，这可能会返回多个结果。此外还有搜索功能，如查找带有特定关键词的产品，或查找内容匹配搜索短语的支持单。最后，可能是最难处理的任务：你不能返回所有匹配过滤条件的实体列表。这在你的用户界面中既不妥也不易于使用。（想象一下为了在屏幕上显示 50 条记录而从数据库中返回 10,000,000 条记录。）因此你必须以某种方式对结果进行分页，并且在此过程中始终保持结果排序。

# 避免代码重复

可以使用 JPA 查询语言和 Criteria API 对结果进行排序和分页。然而，并没有捷径。这些操作需要你构建并执行两个独立的查询：一个返回结果计数，另一个返回结果的子集。以下代码演示了如何使用 JPQL 执行此操作。你已经学习了如何过滤结果，因此代码仅关注分页且不应用任何过滤。

```java
TypedQuery<Long> countQuery = this.entityManager.createQuery(
    "SELECT count(b) FROM Book b WHERE predicates...", Long.class
);

long totalRows = countQuery.getResultList();
```

```java
TypedQuery<Book> pagedQuery = this.entityManager.createQuery(
    "SELECT b FROM Book b WHERE predicates... \nORDER BY b.title ASC, b.isbn DESC", Book.class
);

pagedQuery.setFirstResult(startRecordNumber);
pagedQuery.setMaxResults(maxPage);
List<Book> singlePage = pagedQuery.getResultList();
```

使用 Criteria API 执行任务更为健壮，但对于未知实体类型的通用查询来说效果较差。

```java
CriteriaBuilder builder = this.entityManager.getCriteriaBuilder();
CriteriaQuery<Long> pagedCriteria = builder.createQuery(Long.class);
Root<Book> root = pagedCriteria.from(Book.class);
CriteriaQuery<Long> count = this.entityManager.createQuery(
    builder.select(builder.count(root))
        .where(predicates...)
);

long totalRows = count.getResultSingle();
```

```java
CriteriaQuery<Book> root = builder.createQuery(Book.class);
root = root.from(Book.class);
TypedQuery<Book> pagedQuery = this.entityManager.createQuery(
    criteria.select(root)
        .where(predicates...)
        .orderBy(root.asc("title"), builder.desc(root.get("isbn")))
);

pagedQuery.setFirstResult(startRecordNumber);
pagedQuery.setMaxResults(maxPage);
List<Book> singlePage = pagedQuery.getResultList();
```

在这些示例中，`startRecordNumber` 和 `maxPage` 分别是输入变量，分别是页面上第一个实体的零开始索引和要返回的最大条数。`totalRows` 是要返回的条目数。

# 第 22 章 使用 Spring Data JPA 消除模板代码存储库

> 注意：你使用了许多来自 Spring Data Commons 和 Spring Data JPA 的类，本书无法告诉你关于所有类的每一个细节。你应该复阅并书签 Spring Data Commons API 文档和 Spring Data JPA API 文档以备后参考。

## 使用 Repository 接口

Spring Data Commons 提供的工具之一是 `org.springframework.repository.Repository<T, ID> extends Serializable`：接口必须扩展此接口，它没有指定任何方法。只有扩展了 `Repository` 才有动态实现。泛型类型 `T` 和 `ID` 捕获实体类型和标识符类型，类似于你在第 21 章中创建的 `GenericRepository`。

> 注意：Spring Data 中的类型参数顺序与你在 `GenericRepository` 中创建的顺序相反。此外，`ID` 参数必须实现 `Serializable`，但对 `T` 没有限制。

你可以直接创建一个扩展 `Repository` 的接口，但因为它没有指定任何方法，你可能永远不会这样做。一种更有用的方法是扩展 `org.springframework.repository.CrudRepository<T, ID>`，它指定了许多用于基本 CRUD 操作的方法。此接口与你在第 21 章中创建的 `GenericRepository` 非常相似，但使用了一些不同的约定。

- `count()` 返回一个 `long`，代表扩展 `T` 的未过滤实体总数。
- `delete(T)` 和 `delete(ID)` 删除单个指定的实体，而 `delete(Iterable<T> extends T)` 删除多个实体，`deleteAll()` 删除所有该类型的实体。
- `exists(ID)` 返回一个布尔值，表示具有给定代理键的该类型实体是否存在。
- `findAll()` 返回所有类型为 `T` 的实体，而 `findAll<ID>` 返回给定代理键的类型实体。两者都返回 `Iterable<T>`。
- `findOne(ID)` 根据给定的代理键检索类型为 `T` 的单个实体。
- `save(S)` 保存给定的类型为 `S` 的实体（或更新），其中 `S` 扩展 `T`，并返回保存的实体 `S`。
- `save(Iterable<S>)` 保存所有实体（所有扩展自 `T` 的 `S`），并将保存的实体作为新的 `Iterable<S>` 返回。

## 理解 Spring Data 的统一数据访问

所有 Spring Data 项目已经知道如何为给定类型实现这些方法。然而，你会发现此存储库尚未指定支持分页和排序的方法。这是为了防止这些方法弄乱你不需要支持分页和排序的存储库。如果你想要一个提供分页和排序方法的存储库，它的接口可以扩展 `org.springframework.data.repository.PagingAndSortingRepository<T, ID> extends Serializable`。

- `findAll(Sort)` 根据提供的 `Sort` 将所有实体作为 `Iterable<T>` 返回。
- `findAll(Page)` 返回单个 `org.springframework.data.domain.Page<T>` 实体，这些实体根据提供的 `Pageable` 指令进行排序和绑定。

`org.springframework.data.domain.Sort` 对象封装了关于用于排序结果的属性以及排序方向的信息。`org.springframework.data.domain.Pageable` 封装了 `Sort` 以及每页的实体数量（均为 int 类型）。在 Web 应用程序中，你通常不需要担心在 Spring 中创建 `Pageable` 对象。Spring Data 提供了两个 `org.springframework.web.support.HandlerMethodArgumentResolver` 实现，分别将 HTTP 请求参数转换为 `Pageable` 和 `Sort` 对象：`org.springframework.data.web.HandlerMethodArgumentResolver` 和 `org.springframework.data.web.HandlerMethodArgumentResolver`（注：此处原文重复了类名）。

所有这些预定义方法都有帮助，标准化的 `Sort` 和 `Pageable` 对象确实非常有用，但你仍然需要使用代理键以外的任何方法查找特定实体或实体列表——至少在不创建自己的实现的情况下。这就是 Spring Data 查询方法的用武之地了。

## 创建查找实体的查询方法

查询方法是指定的方法，用于告诉 Spring Data 如何查找实体。查询方法的名称以 `find...By`、`get...By` 或 `read...By` 开头，后面紧跟应该匹配的属性名称。方法参数提供了与方法名中指定的属性相匹配的值（按照它们相同类型的顺序排列）。返回类型告诉 Spring Data 期望得到单个结果（`T`）还是多个结果（`Iterable<T>`、`List<T>`、`Collection<T>`、`Page<T>` 等等）。因此，例如，在 `BookRepository` 中，你可能需要根据 ISBN、作者或以下条件定位书籍：

```java
public interface BookRepository extends PagingAndSortingRepository<Book, Long> {

    Book findByIsbn(String isbn);

    List<Book> findByAuthor(String author);

    List<Book> findByPublisher(String publisher);

}
```

分析这些方法的算法知道 `findByIsbn` 匹配的结果应该是唯一的。同样，它知道 `findByAuthor` 和 `findByPublisher` 应该分别使用 `Book` 的 `author` 和 `publisher` 属性匹配多条记录。注意，存储库名称中引用的属性名称与 `Book` 实体的 JPA 属性匹配——这是你必须遵循的约定。在大多数情况下，这也是 JavaBean 的属性名。当然，一个作者可以写很多书，一个出版社可以出版很多书，但你可能需要你的查询方法支持分页。

```java
public interface BookRepository extends PagingAndSortingRepository<Book, Long> {

    Book findByIsbn(String isbn);

    Page findByAuthor(String author, Pageable instructions);

    Page findByPublisher(String publisher, Pageable instructions);

}
```

你可以在查询方法名中包含多个属性并使用逻辑运算符搜索这些属性：

- `List<Person> findFirstNameAndLastName(String firstName, String lastName)`
- `List<Person> findFirstNameOrLastName(String firstName, String lastName);`

许多数据库在匹配字符串字段时会忽略大小写（默认情况下或作为可选配置），但你可以显式指示该字段忽略大小写：

```java
Page<Person> findByLastNameIgnoreCase(String firstName, String lastName, Pageable instructions);
```

在前面的示例中，只有姓名忽略了大小写。你也可以通过 `findFirstNameOrLastNameCase` 忽略名字，但这非常冗长。相反，你可以使用 `findFirstNameOrLastName` 让 Spring Data 忽略所有字符串属性。

有时属性不是简单类型。例如，`Person` 可能有一个类型为 `Address` 的 `address` 属性。如果给了参数，Spring Data 可以匹配此属性，但通常你不想匹配整个地址。例如，你可能想返回特定邮政编码的人。这可以通过 Spring Data 表达式轻松实现。

```java
List<Person> findByAddressPostalCode(Postal code);
```

假设 `Person` 有一个 `address` 属性，该属性的类型有一个类型为 `Code` 的 `postal` 属性，Spring Data 数据库中找到给定邮政编码的人。然而，属性可能会导致匹配算法产生歧义。Spring 贪婪匹配属性名，然后再查找属性表达式，类似于正则表达式可能会贪婪地匹配“或”控制。算法可能会匹配一个你预期的不同的属性名称，然后无法在该属性中找到匹配属性表达式的属性。因此，最好使用下划线分隔表达式：

```java
Page<Person> findByAddress_PostalCode(Postal code, Pageable instructions);
```



# 理解 Spring Data 的统一数据访问

这消除了 Spring Data 匹配正确属性的歧义。你一定记得方法名以 `find..`、`get..By` 或 `read..By` 开头。这些是引导句，而 `By` 是分隔引导句和后续内容的标识符。

在很大程度上，你可以根据需要放置任何想要查找的内容，或通过它进行读取和读写操作。例如，为了更符合“自然语言”，你可以将方法命名为 `findBookByIsbn` 或 `findByFirstNameLastName`。在这种情况下，`Book` 和 `People` 会被忽略。然而，单词 `Distinct`（区分大小写）位于引导句中（例如 `findDistinctBooksBy`），这会触发特殊行为，在底层查询中启用去重标志。这可能适用于或不适用于使用的存储媒介，但对于 JPA 和 JdbcTemplate 仓库，它等同于 JPQL 或 SQL 查询中的 `DISTINCT` 关键字。

除了分隔多个属性的 `Or` 和 `And` 关键字外，查询名称中的条件还可以包含其他关键字来精炼查询条件：

- 在没有其他关键字的情况下，`Is` 和 `Equals` 是隐含的，但你可以显式地使用它们。例如，`findByIsbn` 等于 `findByIsbn` 和 `findByIsbnEquals`。
- `Not` 可以取反任何其他 `Or` 或 `And` 关键字。在没有其他关键字的情况下，`Is` 和 `Equals` 仍然是隐含的，`findByIsbnIsNot` 等于 `findByIsbnIsNot`。
- `After` 和 `AfterBefore` 表示该属性是给定值之后的日期或时间。例如：`findByFoundAfter(Date date)`。
- `Containing`、`IsContaining` 和 `Contains` 表示属性值的开头和结尾可以是任何内容，但应该包含给定的值。这与 `StartingWith`、`IsStartingWith` 和 `StartsWith` 类似，后者表示属性应以指定值开头。同样，`EndingWith`、`IsEndingWith` 和 `EndsWith` 表示属性应以指定值结尾。例如：`findTitleContains(String value)` 等于 SQL 条件 `WHERE title = '%value'`。
- `Between` 和 `IsBetween` 表示该属性应该在两个值之间。这意味着你必须为该属性条件提供两个参数。你可以使用任何可以以此方式进行数学比较的类型，例如数值和日期类型。例如：`findFindByFoundBetween(Date start, Date end)`。
- `Exists` 表示某些内容存在。其含义在不同的存储媒介之间可能有所不同。它大致等于 JPQL 和 SQL 中的 `EXISTS` 关键字。
- `True` 和 `True` 表示指定的属性应为真，`False` 和 `IsFalse` 表示指定的属性应为假。这些关键字不需要方法参数，因为值是由关键字本身隐含的。例如：`findByApprovedIsFalse()`。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_676_0.png)

- `GreaterThan` 和 `IsGreaterThan` 表示属性大于参数值。你可以通过 `GreaterThanEqual` 或 `IsEqualTo` 将参数值包含在范围内。这些关键字的反词是 `LessThan`、`IsLessThan`、`LessThanEqual` 和 `IsEqualTo`。
- `In` 表示属性值必须等于指定值中的至少一个。匹配此条件的参数应该是属性属性的 `Iterable`。例如：`findByAuthorIn(Iterable<String> authors)`。
- `Null` 和 `Null` 表示该值应为空。这些关键字也不需要方法参数，因为值是隐含的。
- `Near`、`Near`、`Within` 和 `IsWithin` 是某些 NoSQL 数据库类型的有用关键字，但在 JPA 中没有实际意义。
- `Regex`、`MatchesRegex` 和 `Matches` 表示属性值应匹配对应方法参数中指定的字符串正则表达式（或不使用 `Pattern`）。

# 提供自定义方法实现

如你所见，查询方法语言非常强大。通过 Spring Data 接口方法能做的事情并不多。在大多数情况下，你可以创建一个接口，坐等，并让 Spring Data 为你完成工作。但偶尔，你会遇到 Spring Data 无法处理的情况。其中一个例子是执行全文搜索，你将在第 23 章中探索它。

另一个例子是用户生成的动态查询。通常，你希望严格限制用户对持久化数据可以执行的查询。允许用户对几乎任何属性进行过滤可能会产生灾难性的性能影响。但当你了解风险并做出相应计划时，这种工具对你的用户来说可能非常强大且有用。使用 Spring Data 查询方法无法实现这一点。

> 注意：尽管 Spring Data 没有提供执行动态查询的标准机制，但 Spring Data JPA 提供了两种使用 Criteria API 或 Querydsl 谓词来实现它的专有机制。如果你使用 JPA 仓库，可以使用这些机制之一。如果你使用其他 Spring Data 仓库类型，你可能仍需要创建自己的动态查询机制。

无论你需要的 Spring Data 无法独立实现什么功能，为 Spring Data 仓库添加自定义行为通常非常简单。你可以根据需要采取两种方法之一或同时使用两种方法：自定义单个仓库或自定义所有仓库。

## 自定义单个仓库

自定义单个仓库的第一步是为该自定义项创建一个接口。该接口应与实际的仓库接口分离，并指定所有（至少一个）为你的仓库具有自定义实现的方法。然后，仓库接口应该扩展该自定义接口。

```java
public interface BookRepositoryCustomization {

    public Page<Book> findBooksWithQuery(DynamicQuery query, Pageable p);

    public Page<Book> searchBooks(String searchQuery, Pageable p);

}
```

```java
public interface BookRepository
    extends PagingSortingRepository<Book, Long>, BookRepositoryCustomization
{}
```

你可以随心意地命名自定义接口；Spring Data 找到 `BookRepository` 后，它会首先查找名为 `BookRepositoryImpl`（无论你如何命名接口）的类，并将其实例化为 Spring Bean。以下片段演示了这一点：

> 注意：你可以随心意地命名自定义接口；Spring Data 找到 `BookRepository` 后，它会首先查找名为 `BookRepositoryImpl`（无论你如何命名接口）的类，并将其实例化为 Spring Bean。由于 Spring Data 找到 `BookRepository`，它会首先查找 `BookRepositoryImpl`。以下片段演示了：

```java
public interface BookRepository
    extends PagingSortingRepository<Book, Long>, BookRepositoryCustomization
```

仓库接口应该扩展自定义接口。Spring Data 提供了标准实现。以下片段显示了自定义方法的实现：

```java
public class BookRepositoryImpl implements BookRepositoryCustomization {

    @PersistenceContext
    private EntityManager entityManager;

    @Override
    public Page<Book> findBooksWithQuery(DynamicQuery query, Pageable p) {
        // 实现查找
    }

    @Override
    public Page<Book> searchBooks(String searchQuery, Pageable p) {
        // 实现搜索
    }

}
```

如果你大量使用全文搜索或动态查询，自定义单个仓库可能是常见情况。在本章中你不会看到运行示例，但在第 23 章中将使用这种技术。

## 自定义所有仓库

如你所见，自定义单个仓库非常简单。在大多数自定义场景中，你只会自定义部分仓库，或者所有仓库的自定义是不同的。但在少数情况下，你可能希望为特定类型的所有仓库（例如所有仓库）提供相同的自定义方法。这是一个复杂得多的过程。首先，你必须创建一个扩展项目特定接口的新接口，并指定自定义方法。

```java
@NoRepositoryBean
public interface CustomRepository<T, ID extends Serializable>
    extends JpaRepository<T, ID>
{
    void customOperation(T entity);
}
```

注意该接口扩展了 `JpaRepository`（后者又继承 `CrudRepository`）。每个 Spring Data 项目都提供一个或多个扩展基础 Spring 通用接口。以 Spring Data JPA 为例，`CustomRepository` 必须扩展 `JpaRepository`，即 Spring Data 扫描的接口。

你还必须对 `CustomRepository` 注解 `@org.springframework.data.repository.NoRepositoryBean`。由于 `CustomRepository` 自身扩展了仓库（通过 `JpaRepository` 继承 `PagingSortingRepository` 继承 `CrudRepository`），Spring Data JPA 通常会检测到它并创建一个实现。你不希望这样做——`CustomRepository` 应该是你仓库的基础接口。（如果你查看 `CrudRepository`、`PagingSortingRepository` 和 `JpaRepository` 的 API 文档，它们也都注解了 `@NoRepositoryBean`。）

指定新接口后，你必须扩展 Spring Data JPA 项目提供的基础仓库类。

```java
public class CustomRepositoryImpl<T, ID extends Serializable>
    extends SimpleJpaRepository<T, ID>
    implements CustomRepository<T, ID>
{
    private Class<T> domainClass;
    private EntityManager entityManager;

    public CustomRepositoryImpl(Class<T> domainClass, EntityManager entityManager) {
        super(domainClass, entityManager);
        this.domainClass = domainClass;
        this.entityManager = entityManager;
    }

    public CustomRepositoryImpl(Information<T, ?> information, EntityManager entityManager) {
        super(information, entityManager);
        this.domainClass = information.getJavaType();
    }

    this.entityManager = entityManager;
}

public void customOperation(custom operation) {
    // 实现自定义操作的代码
}
```

类 `org.springframework.data.jpa.repository.support.SimpleJpaRepository` 是为预定义接口提供基础的类，例如 `findById(ID)` 和 `save(T)`。如果你还想提供 Querydsl 支持，你应该扩展 `org.springframework.data.jpa.repository.QueryDslJpaRepository` 而不是 `SimpleJpaRepository`。

现在到了具有挑战性的部分：为你所有的仓库提供自定义行为。Spring Data JPA 不会自动将你的 `CustomRepositoryImpl` 作为其基础仓库。你必须创建一个工厂 bean（factory bean）来执行此任务，并用你的工厂 bean 替换默认工厂 bean。

```java
public class CustomRepositoryFactoryBean<R, T, ID> extends JpaRepositoryFactoryBean<R, T, ID> {

    @Override
    protected RepositoryFactorySupport createRepositoryFactory(EntityManager em) {
        return new CustomRepository<T, ID>(em);
    }

}
```

```java
private static class CustomRepository<T, ID> extends JpaRepositoryFactory implements Serializable {

    private EntityManager entityManager;

    public CustomRepository(EntityManager entityManager) {
        super(entityManager);
        this.entityManager = entityManager;
    }

    @Override
    @SuppressWarnings("unchecked")
    protected Object getTargetRepository(RepositoryMetadata metadata) {
        return new CustomRepositoryImpl<T, ID>((Class<T>) metadata.getDomainType(), this.entityManager);
    }

    @Override
    protected Class<?> getRepositoryBaseClass(RepositoryMetadata metadata) {
        return CustomRepositoryImpl.class;
    }

}
```



# 第 22 章 使用 Spring Data JPA 消除样板仓库

就像 `LocalContainerFactoryBean` 作为创建 `EntityManager` 的工厂一样，`CustomRepositoryFactoryBean` 也作为创建 `CustomRepositoryFactories` 的工厂。`CustomRepositoryFactory` 存储 `EntityManager` 并响应对新 `Custom` 实例的调用。由于 `CustomRepositoryImpl` 在其自身代码中通过扩展 `SimpleJpaRepository` 已经实现了 `CrudRepository`、`PagingAndSortingRepository`、`JpaRepository` 和 `CustomRepository` 中指定的所有基础方法，Spring Data JPA 只需要获取 `CustomRepositoryImpl` 实例，并为任何扩展接口（如 `BookRepository` 或 `PersonRepository`）中指定的方法添加实现。

为你的所有实体添加此行为的最后一步是配置 Spring Data JPA 使用默认 `JpaRepositoryBean` 的 `CustomRepositoryFactoryBean`。你将在下一节中学习如何做到这一点。你可能永远不需要为给定数据库的所有仓库添加相同的自定义方法，本书没有提供实际的可运行示例；但是，你可以根据从所示的示例代码创建一个。在某些情况下，像你正在为单个仓库进行定制一样，先创建一个自定义接口和实现，然后将其应用到你所有的仓库中，可能会更简单。

## 配置和创建 Spring Data JPA 仓库

在上一节中，你探索了如何使用 Spring Data 编写仓库接口，并学习了它如何完全取代你手写的接口。虽然文中偶尔提到 Spring Data JPA（例如添加自定义方法实现），但你读到的所有关于 Spring Data 的通用内容，以及你学到的技术不仅适用于 Spring Data JPA，还适用于许多支持不同数据库类型的 Spring Data 项目。你将切换方向，专门学习 Spring Data JPA、如何使用它以及如何配置它。在第 21 章中，你学习了如何在 Spring Framework 中配置 JPA。如果你没有读第 21 章，你应该现在回去补上。本章介绍的配置在本节中被大量用于设置 Spring Data JPA。

配置 Spring Data JPA 并创建供其实现的仓库是非常简单的任务。使用任何 Spring Data 项目的优之处在于，除非你需要实现自定义行为，否则你实际上不需要做什么。在本节中，你将探索如何从 wrox.com 下载站点获取 Spring-Data 项目来设置并运行 Spring Data JPA。它是基于你在第 21 章中工作的 Spring-Jpa 项目。它的实体是相同的，并使用现有的数据库、数据库表结构和 Tomcat DataSource 资源。

### 启用仓库自动生成

配置 Spring Data JPA 不需要费精力。你只需要考虑少数选项。与 Spring Framework 一样，你可以采取不同的配置方法：XML 或 Java。本节将介绍这两种，但 Spring-Data-JPA 项目仅演示了 Java 配置。即使你不打算使用它，也务必阅读 XML 命名空间配置，因为它引入了一些对 Java 配置重要的概念。

### 配置和创建 Spring Data JPA 仓库

当你配置 Spring Data JPA 时，使用两个 XML 命名空间。第一个 `http://www.springframework.org/schema/data/repository` 是 Spring Data Commons 的核心命名空间（在本书中，命名空间前缀为 `data`）。所有的 Spring Data 项目都以此方式使用该命名空间来配置仓库生成。在某些情况下，Spring Data 项目（如 Spring Data JPA）可能会扩展 Spring Data Commons 中定义的某些类型以创建额外的元素。Spring Data JPA 命名空间 `http://www.springframework.org/schema/data/jpa`（本书中使用 `data-jpa` 命名空间前缀）确实如此。

Spring Data 具有用生成的数据填充数据库的能力。它使用 XML 或 JSON 文件来实现。本书不会详细介绍此功能，你应该只在开发环境中使用它，因为它在生产系统中可能非常危险。但是，除非你使用以下命名空间元素（均来自 Spring Data 命名空间），否则你不应该配置此功能：

- `jackson-population` 定义了一个通过 Jackson Processor 1.x `ObjectMapper` 使用 JSON 文件填充实体的 bean。你可以使用 `locations` 属性指定你的 JSON 文件的名称或顺序。你可以使用 `id` 属性自定义此名称。如果你已经创建并配置了 `ObjectMapper` 1.x bean，你应该将该 bean 的名称放在 `object-mapper-ref` 属性中，以便 Spring Data 使用它。
- `jackson2-population` 也定义了一个使用 JSON 文件填充实体的 bean，但它使用的是 Jackson Processor 2.x `ObjectMapper`。它还有一个必需的 `locations` 属性、可选的 `id` 属性以及用于引用 `ObjectMapper` 2.x bean 的 `object-mapper-ref` 属性。
- `unmarshaller-attribute` 定义了一个使用 XML 文件填充实体的 bean。它的 `locations` 属性必须指向一个或多个包含定义的 XML 文件。由于 `Unmarshaller` 需要某些配置（你在第 17 章中学习过的），你必须使用 `unmarshaller-ref` 属性要求的名称指定 `Unmarshaller` bean。你还可以使用 `id` 属性自定义 bean 名称。

在 Spring Data Commons 的当前版本中，这些是命名空间包含的唯一元素。你永远不需要它们来启用自动填充。Spring Data Commons 元素定义了一些核心类型，作为两个 Spring Data JPA 元素的基础。

`<data-jpa:repositories>` 是使用 Spring Data JPA 配置仓库生成的中心元素。大多数来自 Commons 命名空间的属性和子元素适用于其他项目命名空间元素，例如 `<data-mongo:repositories>` 和 `<data-neo4j:repositories>`。通用属性包括：

- `base-package` —— 这是必需的属性。Spring Data JPA 在该包及其任何子包中查找扩展 `Repository` 且未添加 `@NoRepositoryBean` 注解的接口。它为这些接口生成实现类。
- `named-queries-location` —— 如果你在所选的 Spring Data 项目中使用命名查询，可以使用此属性来定义包含这些命名查询的 `.properties` 文件的位置。这不适用于 Spring Data JPA，相反，它使用 `orm.xml` 中的 JPA 标准 `<named-query>` 元素，以及实体类上的 `javax.persistence.NamedQuery` 和 `javax.persistence.NamedQueries` 注解来定义命名查询。
- `repository-impl-postfix` —— 这定义了 Spring Data 在存储库接口后追加的后缀，以实现自定义方法的实现。对于 `impl`，在上一节中，`BookRepository` 的自定义实现类被命名为 `BookRepositoryImpl`。你可以在包括 Spring Data JPA 在内的 Spring Data 项目中使用此属性，但并不适用于所有项目。如果你使用良好的 IDE，它会提示你是否可以使用此元素。
- `query-lookup-strategy` —— 此属性指定了 Spring Data 如何为你的查询方法创建查询。默认的 `create-if-not-found` 通常足够了。如果 Spring Data 应该寻找与名称匹配的查询，如果没有找到，它将使用上一节中描述的算法（记住：...By）自动创建一个方法。值 `create` 会禁用命名查询并使用其他策略。最终值 `use-declared-query` 会禁用查询方法算法，仅在未找到匹配项时使用命名查询。
- `factory-class` —— 这允许你配置不同的存储库工厂豆及其位置。此属性仅适用于 Spring Data 项目，包括 Spring Data JPA。
- `transaction-manager-ref` —— Spring Data JPA 和其他一些 Spring Data 项目支持事务存储库。如果是这样，你可以指定存储库使用的 `PlatformTransactionManager` 的名称。如果你不指定，Spring Data JPA 将使用与 Spring Framework 相同的算法确定默认的 `PlatformTransactionManager`。在适用情况下，始终指定此属性是最安全的。

在 `<data-jpa:repositories>` 以及任何其他 Spring Data 项目命名空间元素中常用的子元素有：

- `<include-filter>` —— 使用一个或多个此类元素来定义在接口符合自动生成条件之前必须满足的额外标准。这些标准取代了标准的 Spring 接口要求。该元素与你在第 12 章中为 `<context:component-scan>` 学习的 `<context:include-filter>` 元素相同。
- `<exclude-filter>` —— 使用一个或多个此类元素来排除某些存储库接口，使其不符合自动生成条件。这是 `<context:component-scan>` 中 `<context:exclude-filter>` 的对应物。

作为使用这些子元素的示例，考虑以下内容。通常启用 Spring Data 存储库会扫描所有扩展 `Repository` 的接口。然而，如果你同时使用 Spring Data JPA 和 Spring Data MongoDB，它们都会扫描 `Repository`，这将导致重复的存储库和严重问题。以下元素消除了默认扫描（针对 `Repository`），并激活了针对 Spring Data JPA 的 `JpaRepository` 以及针对 Spring Data MongoDB 的 `MongoRepository` 接口的特定扫描。

或者，你可以简单地将这些存储库放在不同的包中：

```xml
<data-jpa:repositories base-package="com.sample"
  include-filter type="assignable"
  expression="org.springframework.data.repository.JpaRepository" />
</data-jpa:repositories>
```

```xml
<data-mongo:repositories base-package="com.sample"
  include-filter type="assignable"
  expression="org.springframework.data.repository.MongoRepository" />
</data-mongo:repositories>
```

Spring Data JPA 定义了一个额外的 `entity-manager-factory-ref`，以便你可以指定 Spring Data JPA 在操作中应使用的 `EntityManagerFactory`。由于你通常配置了一个 `LocalContainerFactoryBean`，你应该直接引用它。在使用 Spring Data JPA 时，你可以使用 `<data-jpa:auditing>` 元素配置审计。其他 Spring Data 项目也支持该元素支持以下属性：

- `author-aware-ref` —— 这是一个类型为 `org.springframework.data.domain.AuditorAware` 的 bean，用于确定当前身份验证的用户或主体。没有此引用，审计将不会记录修改了实体的用户。
- `set-dates` —— 这是一个布尔属性，指示是否应该设置创建日期和修改日期。默认值为 `true`。
- `date-provider-ref` —— 使用此属性指定 `org.springframework.data.DateTimeProvider` 实现的名称，用于确定用于审计的日期和时间。默认是 `org.springframework.data.auditing.CurrentDateTimeProvider`。从 Spring Data 1.7 版本开始，基于 `Calendar` 的 `DateTimeProvider` 不再被需要。
- `modify-on-creation` —— 此属性默认值为 `true`，指示你是否想在创建时设置修改日期。如果为 `false`，则只在更新时保存修改日期。

这看起来很多，但在典型的 Spring Data JPA 配置中，它可能像这样：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:data-jpa="http://www.springframework.org/schema/data/jpa"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-4.0.xsd
    http://www.springframework.org/schema/data/jpa
    http://www.springframework.org/schema/data/jpa/spring-jpa-1.3.xsd">

    <data-jpa:repositories base-package="com.sample"
    transaction-manager-ref="jpaTransactionManager"
    entity-manager-factory-ref="entityManagerFactory"/>
</beans>
```

Spring Data JPA 定义了一个额外的 `entity-manager-factory-ref`，以便你可以指定 Spring Data JPA 在操作中应使用的 `EntityManagerFactory`。由于你通常配置了一个 `LocalContainerFactoryBean`，你应该直接引用它。在使用 Spring Data JPA 时，你可以使用 `<data-jpa:auditing>` 元素配置审计。其他 Spring Data 项目也支持该元素支持以下属性：

- `author-aware-ref` —— 这是一个类型为 `org.springframework.data.domain.AuditorAware` 的 bean，用于确定当前身份验证的用户或主体。没有此引用，审计将不会记录修改了实体的用户。
- `set-dates` —— 这是一个布尔属性，指示是否应该设置创建日期和修改日期。默认值为 `true`。
- `date-provider-ref` —— 使用此属性指定 `org.springframework.data.DateTimeProvider` 实现的名称，用于确定用于审计的日期和时间。默认是 `org.springframework.data.auditing.CurrentDateTimeProvider`。从 Spring Data 1.7 版本开始，基于 `Calendar` 的 `DateTimeProvider` 不再被需要。
- `modify-on-creation` —— 此属性默认值为 `true`，指示你是否想在创建时设置修改日期。如果为 `false`，则只在更新时保存修改日期。

这看起来很多，但在典型的 Spring Data JPA 配置中，它可能像这样：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:data-jpa="http://www.springframework.org/schema/data/jpa"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-4.0.xsd
    http://www.springframework.org/schema/data/jpa
    http://www.springframework.org/schema/data/jpa/spring-jpa-1.3.xsd">

    <data-jpa:repositories base-package="com.sample"



## 配置和创建 Spring Data 存储库

### 使用 Java 配置

`@org.springframework.data.repository.config.EnableJpaRepositories` 注解替换了 `@data-jpa:repositories` 元素。它注册了所有必要的 Bean 并包含了与 XML 命名空间相同的配置选项：

- `basePackages` 和 `basePackageClasses` 代替了 `base-package`。
- `namedQueriesLocation` 代替了 `named-queries-location`。
- `repositoryImplementationPostfix` 代替了 `repository-impl-postfix`。
- `queryLookupStrategy` 代替了 `query-lookup-strategy` 并使用 `.springframework.data.repository.query.QueryLookupStrategy`。
- `factoryBeanClass` 代替了 `factory-class`。
- `transactionManagerRef` 代替了 `transaction-manager-ref`。
- `entityManagerFactoryRef` 代替了 `entity-factory-ref`。
- `includeFilters` 和 `excludeFilters` 代替了 `<data:include-filter>` 和 `<data:exclude-filter>` 元素。

```java
@Configuration
...
@EnableJpaRepositories(
    basePackages = "com.wxyz.site.repositories",
    entityManagerFactoryRef = "entityManagerFactory",
    transactionManagerRef = "jpaTransactionManager"
)
...
public class RootContextConfiguration implements
    AsyncConfigurer, SchedulingConfigurer
{}
```

如果你有 Spring Data `set-dates` 和 `modify-on-creation` 审计设置的默认值，可以使用纯 Java 配置审计。只需定义一个实现 `AuditorAware` 的 Bean，Spring Data 就能找到它。然而，如果你需要将这些值之一或全部改为 `false`，你必须使用 XML 命名空间并通过 `@PostConstruct` 将 XML 配置包含到你的 Java 配置中。

![](img/9c2d4f6d54f72cb870b3a91f62ef683.png)

`@org.springframework.data.annotation.CreatedDate` 属性在实体创建时被设置为当前日期和时间。在 Spring Data Commons 1.7 之前，支持的日期类型只有 `Long`、`java.util.Date` 和 `org.joda.time.DateTime`。从 Spring Data Commons 1.7 开始，你还可以使用 `Calendar` 以及 Java 8 的日期时间类型 `Instant`、`LocalDateTime`、`OffsetDateTime` 和 `ZonedDateTime`。但是，你不能使用 `Timestamp`。无论你选择哪种类型，你使用的持久化技术（JPA、MongoDB 等）必须支持这些类型。

`@org.springframework.data.annotation.LastModified` 属性在实体更新时被设置为登录用户。Java 类型必须与 `AuditorAware` 实现返回的类型匹配。

`@org.springframework.data.annotation.LastModifiedDate` 属性在实体更新时被设置为当前时间。它支持与 `@CreatedDate` 相同的功能。

## 配置 MVC 支持

如上一节所述，Spring Data 可以自动将请求参数转换为用于 `Pageable` 和 `Sort` 的 Spring MVC 处理方法参数。此外，它还可以自动将请求参数和路径变量转换为你的实体类型，作为 Spring MVC 处理方法的参数。例如，你可以创建一个如下处理方法：

```java
@RequestMapping("/person/id")
public String viewPerson(@PathVariable("id") Person person)
{
    // method implementation
}
```

Spring Data 可以从 URL 中获取 ID，从仓库实现类中检索 `Person` 对象，并自动将其转换为你的控制器方法。这消除了手动使用长 ID 方法从仓库中手动检索 `Person` 的步骤。

配置这种设置（这是 Spring Data Commons 1.6 中引入的新功能）非常简单。只需为你的 `DispatcherServlet` 配置类（如果有多个 `DispatcherServlet` 则为多个类）注上 `@org.springframework.data.web.EnableSpringDataWebSupport` 注解。这会自动注册一个 `org.springframework.data.repository.DomainClassDataConverter`，它会将请求参数和路径变量转换为你的实体。它还会注册 `PageableHandlerMethodArgumentResolver` 和 `SortHandlerArgumentResolver`，实现从请求参数到 `Pageable` 和 `Sort` 的转换。这在 `WebServletContextConfiguration` 中得到了演示。

```java
@Configuration
@EnableWebMvc
@EnableSpringDataWebSupport(
    basePackages = "com.wrix.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(WebController.class)
)
```

## 配置并创建 Spring Data JPA 仓库

```java
public class WebServletContextConfiguration extends WebMvcConfigurer
{
    ...
}
```

使用 `@EnableSpringDataSupport` 注册的 Bean 包含许多初始化为默认值的设置。这些设置包括参数名称、最大页大小，以及当请求参数缺失时的默认 `Pageable` 和 `Sort` 值。这些默认值对你来说可能是可以的，但如果不是，你需要省略 `@EnableSpringDataWeb` 注解并手动注册这些 Bean。这在 `WebServletContextConfiguration` 中通过了演示。

```java
@Configuration
@EnableWebMvc
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter({RestEndpoint.class, RestEndpointAdvice.class})
)
```

```java
public class WebServletContextConfiguration extends WebMvcConfigurer
{
    private static final Logger log = LogManager.getLogger(log);
    @Inject ApplicationContext applicationContext;

    @Override
    public void addArgumentResolvers(List<HandlerMethodArgumentResolver> resolvers) {
        Sort sort = new Sort(new Sort.Order(Sort.Direction.ASC, "id"));
        Pageable pageable = new PageRequest(0, 20, sort);
        SortHandlerArgumentResolver sortResolver = new SortHandlerArgumentResolver();
        // sortParameter 默认值为 "sort"
        sortResolver.setSortParameter("*sort*");
        sortResolver.setFallbackResolver(defaultResolver);
        PageableMethodArgumentResolver pageResolver = new PageableMethodArgumentResolver(sortResolver);
        pageResolver.setOneIndexedParameters(true); // page 从 1 开始，而不是 0
        // pageProperty 默认值为 "page"，sizeProperty 默认值为 "size"
        // 以下设置了 setPageProperty("paging.page") 和
        // setPointSize("paging.size")
        pageResolver.setPrefix("paging.");
        pageResolver.setFallbackPageable(pageable);
        resolvers.add(sortResolver);
        resolvers.add(pageResolver);
    }
}
```

```java
@Override
public void addFormatters(FormatterRegistry registry)
{
    if (!(registry instanceof FormattingConversionService)) {
        log.warn("Unable to register Spring Data JPA converter.");
        return;
    }
    // DomainClassConverter 将其自身添加到注册表中
    DomainClassConverter<FormattingConversionService> converter =
        new DomainClassConverter((FormattingConversionService) registry);
    converter.setApplicationContext(this.applicationContext);
}
```

## 编写和使用 Spring Data JPA 接口

除非你有几十个或数百个仓库，否则在创建仓库时可能需要更多代码来配置 Spring JPA。Spring-Data JPA 项目中新的 `AuthorRepository`、`BookRepository` 和 `PublisherRepository` 几乎是空的。上一个 Spring-JPA 项目中的 `GenericRepository`、`GenericBaseRepository`、`GenericJpaRepository`、`DefaultAuthorRepository`、`DefaultBookRepository` 和 `DefaultPublisherRepository` 已经消失，它们不再不再需要。想想你消除了多少代码吧！

```java
public interface AuthorRepository extends CrudRepository<Author, Long>
{
public interface BookRepository extends CrudRepository<Book, Long>
{
    Book getBybn(String isbn);
}
public interface PublisherRepository extends CrudRepository<Publisher, Long>
```

使用这些需要对 `DefaultManager` 进行细微修改。

```java
@Override
@Transactional
public List<Author> getAuthors()
{
    return this.authorRepository.findAll();
}
```

## 配置和创建仓库

```java
@Override
@Transactional
public void saveAuthor(Author author) {
    this.authorRepository.save(author);
}
```



你可能会奇怪为什么仓库返回 `Iterable<T>` 而不是 `List<T>`，以及为什么你需要额外的遍历 `Iterable<T>` 将其转换为 `List<T>` 的步骤。ORM 通常直接用 `ResultSet` 支持返回的 `List`。这提高了性能并允许调用代码在数据库仍在返回数据时就开始执行。

> 你可能注意到创建的 JPA 接口继承自 Spring Data 中的 `CrudRepository` 而不是 `JpaRepository`。你应该只暴露想要给服务的方法。在某些情况下，你不需要暴露仓库使用 JPA 的事实，因此不需要继承 `JpaRepository`。如果你想暴露分页功能，请继承 `PagingAndSortingRepository`。只有当你需要暴露 JPA 特有的行为（如删除或 EntityManager 刷新）时，才继承 `JpaRepository`。

测试应用程序只需使用第 21 节的 Spring-JPA 项目：

1. 如果你需要测试第 21 节的 Spring-JPA 项目，请确保在 MySQL Workbench 中运行 `create.sql` 脚本创建数据库表，然后在 Tomcat 的 `context.xml` 文件中创建 `DataSource`：
```
<Resource name="jdbc/SpringJpa" type="java.sql.DataSource"
maxActive="20" maxIdle="5" maxWait="10000"
username="tomcatUser" password="password1234"
driverClassName="com.mysql.jdbc.Driver"
defaultTransactionIsolation="READ_COMMITTED"
url="jdbc:mysql://localhost/SpringJpa"/ />
```

2. 从 IDE 中编译代码并启动 Tomcat。访问 `http://localhost:8080/repositories/`，然后就能看到你在上一节中使用 Spring-JPA 仓库创建的实体。

3. 点击几次“Add Entity”，更多的实体应该出现在屏幕和数据库表中。

你正在无需编写任何持久化代码的情况下使用 JPA 和 Hibernate ORM！

# 重构客户支持应用程序

当然，你在整本书中一直在构建的客户支持应用程序完全可以充分利用 Spring Data 和 Spring Data JPA。事实上，你可以显著减少应用程序中所需的代码量，并使改进变得更加容易。

在本节中，你可以从 wox.com 代码网站下载 Customer-Support-v16 项目并进行练习。它使用了你在之前的版本 `RootContextConfiguration` 中创建的相同的 `@JpaRepositories` 配置。然而，它没有在 `ServletContextConfiguration` 中使用 `@SpringDataWebSupport`。相反，它手动创建了 `SortHandlerMethodArgumentResolver` 和 `PageableHandlerMethodArgumentResolver`，以便应用合理的默认值，就像在……一样。

## 转换现有的仓库

与 Spring-Data-JPA 项目一样，你会发现：

- `GenericRepository`、`GenericBaseRepository` 和 `GenericJpaRepository` 不再存在于 Customer-Support-v16 项目中。
- `DefaultAttachmentRepository`、`DefaultTicketRepository` 和 `DefaultUserRepository` 也消失了。
- `AttachmentRepository`、`TicketRepository` 和 `UserRepository` 接口现在扩展了 `CrudRepository` 并全部移动到了 `com.wox.site.repositories` 包下。

你甚至不需要为 `AttachmentRepository` 和 `UserRepository` 添加额外的方法定义；它们已经与 Spring Data 查询方法算法兼容了。

```java
public interface AttachmentRepository extends CrudRepository<Attachment, Long> {
    Iterable<Attachment> getByTicketId(long ticketId);
}

public interface TicketRepository extends CrudRepository<TicketEntity, Long> {
}

public interface UserRepository extends CrudRepository<UserPrincipal, Long> {
    UserPrincipal getUsername(String username);
}
```

对这些仓库的更改需要对使用它们的服务进行一些调整。例如，`DefaultAuthenticationService` 中的 `saveUser` 方法需要使用仓库的新 `save` 方法，而不是 `add` 和 `update`。

```java
@Override
@Transactional
public void saveUser(UserPrincipal principal, String newPassword) {
    if (newPassword != null && newPassword.length() > 0) {
        String salt = BCrypt.gensalt(HASHING_ROUNDS, RANDOM);
        principal.setPassword(BCrypt.hashpw(newPassword, salt).getBytes());
    }
    this.userRepository.save(principal);
}
```

在 `DefaultTicketService` 中，以下内容的使用：

- `getAll` 变为 `findAll`。
- `get` 变为 `findOne`。
- `add` 和 `update` 变为 `save`。
- `deleteById` 变为 `delete`。

这些更改很小，但贯穿整个类，因此代码未包含在这里。请注意，Customer-Support-v16 项目中的更改尚未利用 Spring Data 提供的分页功能。更新现有代码以支持分页是你留待完成的任务。在本节后面，你将使用工单分页作为示例。

> 注意：在之前的 `GenericRepository` 接口中，两个类型参数都扩展了 `Serializable`，因此 `delete(E)` 和 `delete(I)` 方法存在模糊且无法编译。这就是为什么 `GenericRepository` 定义了 `delete(E)` 和 `deleteById(ID)` 方法。在 `CrudRepository` 中，只有 ID 类型参数扩展了 `Serializable`，因此可以这样重载 `delete` 方法。因此，`CrudRepository` 的方法是 `delete(T)` 和 `delete(ID)`。

## 为工单添加评论

客户支持系统的主要功能之一现在是工单评论。如果没人能评论，良好的报告有什么意义呢？有了 JPA、Spring Data 和 Spring Data JPA，为客户应用程序添加评论变得非常简单。你仍然需要处理业务逻辑和用户界面，而持久层将负责处理评论。当你创建评论实体和仓库后，需要更新服务来操作评论。完成后，你需要在用户界面上添加评论。

## 创建实体和仓库

你首先想从创建一个 `TicketComment` POJO 开始，当然。它看起来与缺少主题的工单非常相似。

```java
public class TicketComment {
    private long id;

    @NotBlank(message = "validate.ticket.comment.customerName")
    private String customerName;

    @NotBlank(message = "{validate.ticket.comment.body}")
    private String body;

    private Instant dateCreated;
    // 省略修改器和访问器
}
```

由于你无法持久化带有 `Instant` 属性的实体，你需要创建一个单独 `TicketCommentEntity`。`TicketComment` 作为一个 DTO。

```java
@Entity
@Table(name = "TicketComment")
public class TicketCommentEntity implements Serializable {
    private static final long serialVersionUID = 1L;

    private long id;
    private long ticketId;
    private long userId;
    private String body;
    private Timestamp dateCreated;

    @Id
    @Column(name = "CommentId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ... }
    public void setId(long id) { ... }

    @Basic
    public long getTicketId() { ... }
    public void setTicketId(long ticketId) { ... }

    @Basic
    public long getUserId() { ... }
    public void setUserId(long userId) { ... }

    @Basic
    public String getBody() { ... }
    public void setBody(String body) { ... }

    @Basic
    public Timestamp getDateCreated() { ... }
    public void setDateCreated(Timestamp dateCreated) { ... }
}
```

你还需要一个新的 MySQL 表来持久化评论。请确保在你的客户支持数据库上运行以下创建表语句（你可以在 `create.sql` 中找到它）。

```sql
CREATE TABLE TicketComment (
    CommentId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    TicketId BIGINT UNSIGNED NOT NULL,
    UserId BIGINT UNSIGNED NOT NULL,
    Body TEXT,
    DateCreated TIMESTAMP(6) NULL,
    CONSTRAINT TicketCommentUserId FOREIGN KEY (UserId)
    REFERENCES UserPrincipal (UserId) ON DELETE CASCADE,
    CONSTRAINT TicketCommentId FOREIGN KEY (TicketId)
    REFERENCES Ticket (TicketId) ON DELETE CASCADE
) Engine = InnoDB;
```

最后，创建 `TicketCommentRepository` 是简单的步骤，因为你只需要定义接口并让 Spring Data 处理剩余部分。

```java
public interface TicketCommentRepository extends CrudRepository<TicketCommentEntity, Long> {
    Page<TicketCommentEntity> getByTicketId(long ticketId, Pageable p);
}
```

## 更新服务

服务层也应该很容易更新。你需要获取评论、保存评论和删除评论的方法。对于评论，你不需要做更多。在 `TicketService` 接口中添加这三个方法是合理的，因为这些评论与工单是内在关联的。

```java
Page<TicketComment> getComments(
    @Min(value = 1, message = "${validate.ticketService.getComments}")
    long ticketId,
    @Min(value = 1, message = "${validate.ticketService.getComments}")
    Pageable page
);

void save(
    @Min(message = "${validate.ticketService.saveComment}")
    @Valid TicketComment comment,
    @Min(value = 1, message = "${validate.ticketService.saveComment}")
    long ticketId
);

void deleteComment(long id);
```

`DefaultTicketService` 中 `save` 和 `deleteComment` 的实现相当标准，并模仿了工单对应的方法。`getComments` 非常有趣，因为你必须将仓库返回的 `Page<TicketCommentEntity>` 转换为 `Page<TicketComment>`。在第 24 章，你将学习如何在实体中使用 `Instant`，这样你就可以消除额外的工作。

```java
@Override
@Transactional
public Page<TicketComment> getComments(long ticketId, Pageable page) {
    List<TicketComment> comments = new ArrayList<>();
    Page<TicketCommentEntity> entities = this.commentRepository.getByTicketId(ticketId, page);
    entities.forEach(e -> comments.add(this.convert(e)));
    // ...
    return new PageImpl<>(comments, page, entities.getTotalElements());
}
```

```java
private TicketComment convert(TicketCommentEntity entity) {
    TicketComment comment = new TicketComment();
    comment.setId(entity.getId());
    comment.setCustomerName(
        this.userRepository.findOne(entity.getUserId()).getUsername()
    );
    comment.setBody(entity.getBody());
    comment.setCreated(Instant.ofEpochMilli(
        entity.getDateCreated().getTime()
    ));
    return comment;
}
```

# 从用户界面进行评论

更新用户界面是为客户支持应用程序添加评论的最后一步。`TicketController` 的更改很小。首先，视图方法需要一个 `Pageable` 参数（Spring Data 会自动解析它），并添加了两行简单的代码。

控制器还需要一个用于添加新评论的方法。评论表单存在于工单查看页面，这样用户在发表评论的同时可以查看工单和其他评论。因此，如果发生验证错误，此方法将委托给视图方法。



```java
@RequestMapping(value = "/ticketId", method = RequestMethod.POST)
public ModelAndView comment(Principal principal, @Valid CommentForm form,
    Errors errors, Map<String, Object> model,
    @PathVariable("ticketId") long ticketId) {

    Ticket ticket = this.ticketService.getTicket(ticketId);
    if (ticket == null) {
        return this.redirectToModelAndView();
    }
    if (errors.hasErrors()) {
        return this.view(model, page, ticketId);
    }

    TicketComment comment = new TicketComment();
    comment.setCustomerName(principal.getName());
    comment.setBody(form.getBody());

    try {
        this.ticketService.save(comment, ticketId);
    } catch (ConstraintViolationException e) {
        model.put("validationErrors", e.getConstraintViolations());
        return this.view(model, page, ticketId);
    }

    return new ModelAndView(new RedirectView(
        "/ticket/view/*" + ticketId, true, false
    ));
}
```

用于显示和添加评论的 JSP 代码很长，其中很大一部分用于分页。你可以在 `WEB-INF/jsp/view/ticket.jsp` 中查看代码。第 21 行之后的所有内容用于显示和添加评论。在阅读代码时，你可能会发现通过单页链接可以做更多事情（例如第一页和最后一页链接，以及如果页面很多，则不在每个页面上都显示评论）。你应该很快意识到，在每个需要分页的地方重复代码是不理想的。自定义 JSP 标签是解决此问题的方法，而创建此标签的任务留给你完成。

现在你已准备好通过以下步骤测试更新后的客户支持应用程序：

1. 如果你没有在第 21 章中测试该应用程序，请确保运行了 `create.sql` 脚本并将 `DataSource` 资源添加到 Tomcat 的 `.xml` 文件。如果已经运行过，请确保向数据库添加了 `Comment` 表。
2. 编译项目并从 IDE 启动 Tomcat。
3. 在浏览器中访问 `http://localhost:8080/`，登录并对你在第 21 章中创建的一些工单发表评论。
4. 如果喜欢，可以创建新的工单，并尝试以不同用户的名义创建不同的评论。
5. 为一个工单添加超过 10 条评论，以便测试分页。使用 Spring Data JPA，你轻松地重构并为支持系统添加了评论。

你可能已经注意到 SOAP 和 RESTful Web 服务尚未更新以处理创建和返回评论。这同样是一个留给你完成的任务。

### 总结

在本章中，你探索了 Spring Data 和 Spring Data JPA 如何消除编写仓库代码的枯燥、重复的任务。你学习了如何创建 Spring Data 仓库接口和编写 Spring Data 查询方法，以及 Spring Data 如何动态为这些接口创建实现类。你还简要地介绍了如何向 Spring Data 仓库添加自定义行为，你将在下一章中进一步进行探索。最后，你以极少的精力为客户支持应用程序中的工单添加了评论，并演示了由于 Spring Data 的 `Pageable` 和 `Sort` 对象，分页是多么简单。

在下一章中，你将学习数据搜索的各种方法，以及如何将原生 MySQL 全文搜索和通用 Apache Lucene 全文搜索集成到你的仓库中。

# 使用 JPA 和 Hibernate Search 搜索数据

## 本章内容

- 搜索基础
- 如何使用高级准则定位对象
- 在 JPA 中使用全文索引
- 使用 Apache Lucene 和 Hibernate Search 索引你的数据

## 本章 WOX.COM 代码下载

你可以在 `http://www.wrox.com/go/projavaforwebapps` 的 Download Code 标签页找到本章的 wrox.com 代码下载。本章代码分为以下主要示例：

- Advanced-Criteria
- Customer-Support-v17 Project
- Search-Engine Project

## 本章的新 Maven 依赖

除了章节引入的 Maven 依赖外，你还需要适用于涵盖 Apache Lucene、Hibernate Search 和 Search-Engine 项目章节的以下 Maven 依赖。

```xml
<dependency>
  <groupId>org.hibernate</groupId>
  <artifactId>hibernate-search-orm</artifactId>
  <version>4.5.0</version>
  <scope>compile</scope>
</dependency>
```

# 搜索简介

搜索数据有多种形式。如果你 `grep` 一个小文件夹，它可能会很快返回结果。但对于一个包含数百个文件的整个磁盘呢？`grep` 可能需要几分钟或几小时，而 Spotlight 仅需几秒？区别在于方法。

索引是某种让查找数据变得更容易的结构。索引根据索引方式有多种形式。许多关系型数据库大量使用 B-tree 索引，它存储有序的数据。文本密集型数据存储需要根据内容与查询的匹配程度进行搜索，这需要使用全文索引。Google 的搜索使用了一种严密保护的索引算法，大多数人对其知之甚少。所有这些索引都有其收益（快速搜索）和成本。对于大多数索引来说，成本是数据写入速度变慢。对于像 Google 这样涵盖第三方创建内容的搜索引擎来说，成本是运行“爬虫”的费用，在数据更新后对其进行索引。

那么，你知道一个索引是否值得这些成本吗？这是一个复杂的问题，答案可以填满很多章节。通常情况下，索引的成本与读写比例直接相关。读取次数多于写入次数的系统可以比写入次数多于读取次数的系统承担更多索引和更复杂的索引。有时这种比例在系统的不同部分有所不同。例如，存储新闻文章的数据库表更新频率低于存储这些文章评论的数据库表。因此，在成本大致相同的情况下，新闻文章表可以比评论表拥有更多更复杂的索引。索引的价值取决于成本与使用索引的读取与不使用索引的读取之间的比例。

## 理解索引的重要性

这种支出是否值得为搜索速度带来不可估量的价值？对于大多数用户来说，是绝对值得的。由于（取决于电脑的活跃程度）你可能会注意到，有时你的机器会喘不过。每当你保存文件时，Spotlight 都会占用 CPU 来重新组织其索引。很多时候（取决于电脑的活跃程度）你可能会注意到，有时你的机器会喘不过。

## 666 | 第 23 章 使用 JPA 和 HIBERNATE SEARCH 查找数据

确定何时以及在哪里创建索引是一门经验性的艺术，涉及到对查询类型、比例、瓶颈以及性能分析工具的细致分析。但总的来说，如果你想在合理的时间搜索任何大量数据，你就需要一个或多个索引。如果没有任何索引，你的搜索将慢得令人无法忍，并可能影响应用程序其他部分的性能。你使用哪种索引技术在很大程度上取决于你的存储介质、计算机语言和编程方法。

## 采取不同的方法

本章探索了搜索和索引的三种不同方法：

- 带有复杂查询的简单索引
- 使用数据库厂商索引的全文搜索
- 使用 Apache Lucene 和 Hibernate Search 的全文搜索

这并不是详尽的分析，但它确实涵盖了其他 Java、JPA 和关系型数据库程序员采用的一些常用技术。所有这些方法都以某种方式集成了 Java 持久化 API，但你也可以在 JPA 环境之外使用它们。在学习了这三种不同的技术后，你应该已经在在应用程序中可能想要使用的任何搜索和索引技术找到了一个起点。

## 使用高级 Criteria 定位对象

也许显而易见的解决方案是，你使用 Criteria API 以许多不同的方式查找对象。与本章介绍的所有解决方案一样，它在某些情况下是最佳选择，而在另一些情况下则是糟糕的选择。在动态查询中，用户为一个或多个字段提供期望值，可能指示是否应满足所有或任何标准，并提交搜索。这并不像用户输入人的名字和姓氏来查找应用程序中的 Person 那么简单。你不需要为了这一点而了解 Criteria API；你只可以创建一个名为 `findByFirstNameLastName` 的数据查询方法来满足这一需求。

在动态查询中，你无法在编译时知道用户想要在哪些字段上进行搜索，因此你无法编写支持搜索的复杂查询。从用户端来看，动态查询看起来可能像图 23-1 所示。这没有官方名称；它只是另一种类型的搜索。你可以称它为不同的名称。本书称其为动态查询。

在这个搜索界面中，你可以根据需要从查询中包含尽可能少或尽可能多的字段。当前输入的查询应该找到所有居住在纽约夏威夷州姓 Sanders 的女性。标准隐式地使用 AND 操作符组合在一起，但如果没有勾选复选框，则不会包含在查询中。你无法通过编译时已知的静态查询执行此搜索。这是一个动态查询，处理它的最佳方法是使用 Criteria API。

## 使用高级 Criteria 定位对象 | 667

![](img/9c2d45f6d547f72cb870b3a991f62ef6_702_0.png)

图 23-1

## 创建复杂的 Criteria 查询

继续图 23-1 中的示例搜索，假设你的应用程序具有以下 Person 实体，并带有相应的修改器（mutator）和访问器（accessor）。你可以按照 wrox.com 代码网站上提供的 Advanced-Criteria 项目跟随本节。

```java
@Entity
@Table(name = "Person")
public class Person {

    private long id;
    private String firstName;
    private String middleInitial;
    private String lastName;
    private String state;
    private String country;
    private Date birthDate;
    private String gender;
    private String race;
    private String ethnicity;

    // mutators and accessors
}
```

## 在 API 中表示搜索标准

你不能使用 JPA Criteria API 创建搜索标准并将其传递到应用程序的层级。此 API 需要一个 `EntityManager` 实例以及对领域层的访问，而该层不应该能从用户界面层访问。你需要某种方法从用户界面将搜索查询传递到存储库（repository）。这可能不是你想要以此方式搜索的唯一实体，你需要在整个应用程序中复用这种机制，因此它不能是针对 Person 的。

```java
public class Criterion {
    private final String propertyName;
    private final Operator operator;
    private final Object compareTo;

    public Criterion(String propertyName, Operator operator, Object compareTo) {
    }
    // accessors
    public static enum Operator {
        EQ, NEQ, LT, LTE, GT, GTE, LIKE, NOT_LIKE, IN, NOT_IN, NULL, NOT_NULL
    }
}
public interface SearchCriteria extends List<Criterion> {}
```

该 API 是简单的：搜索涉及一个或多个 `Criterion` 实例的列表。每个 `Criterion` 代表属性与值之间的比较，使用 `Operator` 枚举来决定如何执行该操作。现在，它允许对标准进行 AND 组合，因为这是你此搜索所需的所有内容且易于实现。如果你想添加 AND/OR 分组，可以在 `SearchCriteria` 接口中创建额外功能来实现。（这是一个你就可以独立完成的任务。）

## 添加自定义搜索方法

你的存储库需要一个可以接受 `SearchCriteria` 参数的自定义搜索方法。它还应该接受一个 `Pageable` 并返回一个 `Page<Person>`，以便可以分页检索搜索结果。然而，你不想为每个存储库重写此方法，因此你需要让它泛型化。使用第 21 章中用到的一些巧妙技巧来获取泛型类的类型参数。

首先，创建一个接口来反映你希望可搜索存储库所执行的操作。你的 `PersonRepository` 存储库接口应该扩展此接口，以指示人员是可搜索的。

```java
public interface SearchableRepository<T> {
    Page<T> search(SearchCriteria criteria, Pageable pageable);
}
```

```java
public interface PersonRepository extends JpaRepository<Person, Long>, SearchableRepository<Person> {
}
```

所有可搜索存储库共享你创建的搜索方法的公共实现，因此为你的自定义存储库实现实现通用基类是有意义的。搜索中的代码需要知道 T 的 `Class`，但你也可以拥有其他基类。

```java
abstract class DomainClassAwareRepository<T> {
    protected final Class<T> domainClass;

    @SuppressWarnings("unchecked")
    protected DomainClassAwareRepository() {
        Type genericSuperclass = this.getClass().getGenericSuperclass();
        while (!(genericSuperclass instanceof ParameterizedType)) {
            if (genericSuperclass instanceof Class) {
                throw new IllegalException("Unable to determine type " + "arguments because no superclass found.");
            }
            if (genericSuperclass == DomainClassAwareRepository.class) {
                throw new IllegalException("Unable to determine type " + "arguments because class found.");
            }
            genericSuperclass = ((Class) genericSuperclass).getGenericSuperclass();
        }
        ParameterizedType type = (ParameterizedType) genericSuperclass;
        Type[] arguments = type.getActualTypeArguments();
        this.domainClass = (Class<T>) arguments[0];
    }
}
```

```java
abstract class SearchableJpaRepository<T> extends DomainClassAwareRepository<T> implements SearchableRepository<T> {

    @PersistenceContext
    protected EntityManager entityManager;

    public Page<T> search(SearchCriteria criteria, Pageable pageable) {
        // 待实现
    }
}
```

## 第 23 章 使用 JPA 和 HIBERNATE SEARCH 查找数据

现在搜索方法只是一个占位符，但稍后我们会填充它。你在 `PersonRepository` 中添加了 `SearchableRepository<Person>`，Spring Data 仍然不知道如何找到搜索方法。为了解决这个问题，你需要一个 `PersonRepositoryImpl` 类。注意该类实现了 `SearchableRepository<Person>`（通过扩展 `SearchableJpaRepository<Person>`）。它没有实现 `PersonRepository`，因为 Spring Data 会为你完成。

```java
public class PersonRepositoryImpl extends SearchableJpaRepository<Person> {
    // 待实现
}
```



## 从搜索输入创建查询

现在你仍然需要完成搜索方法的实现。它需要执行以下几操作：

- 将 `SearchCriteria` 转换为 `CriteriaQuery<Long>` 以计数匹配记录。
- 将 `SearchCriteria` 转换为 `CriteriaQuery<T>` 以检索实际实体。
- 使用 `Pageable` 中的 `Sort` 对记录进行排序。
- 将 `Pageable` 限制应用于查询以检索正确的页面。
- 将查询结果转换为带有完全初始化实体列表的 `Page<T>`。

当你开始考虑 `Criterion.Operator` 枚举中的所有选项时，你应该很快意识到这消耗了多少资源。因为你需要两次转换 `SearchCriteria`，所以这种转换应该放在单独的方法中。然而，该方法将消耗 12 个 `if` 语句或 12 个 `case`（每个操作符一个）——这并不是最面向对象的方法。当 `Operator` 枚举天然具有多态性时，为什么要执行如此沉重的逻辑呢？

事实证明，你可以用 `javax.persistence.criteria.Predicate` 每个 `Criterion`（不要与 Java 8 的 `java.util.function.Predicate` 混淆）。在广义上（以及在两个接口的情况下），谓词是一个布尔表达式。每个 `Operator` 都可以使用 `Criterion`、`Root` 和 `CriteriaBuilder` 作为输入不断评估为 `Predicate`。

### 列表 23-1: Criterion.java

```java
public class Criterion {

    // 之前打印的代码

    public static enum Operator {

        EQ {
            @Override
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.equal(r.get(c.getProperty()), c.compareToTo());
            }
        },
        NEQ {
            @Override
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.notEqual(r.get(c.getProperty()), c.compareToTo());
            }
        },
        LT {
            @Override
            @SuppressWarnings("unchecked")
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.lessThan(r.<Comparable>get(c.getProperty()), (Comparable) c);
            }
        },
        LTE {
            @Override
            @SuppressWarnings("unchecked")
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.lessThanOrEqualTo(r.<Comparable>get(c.getProperty()), (Comparable) c);
            }
        },
        GT {
            @Override
            @SuppressWarnings("unchecked")
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.greaterThan(r.<Comparable>get(c.getProperty()), (Comparable) c);
            }
        },
        GTE {
            @Override
            @SuppressWarnings("unchecked")
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.greaterThanOrEqualTo(r.<Comparable>get(c.getProperty()), (Comparable) c);
            }
        },
        LIKE {
            @Override
            public Predicate predicateTo(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.like(
                    r.get(c.getPropertyName()), getString(c)
                );
            }
        },
        NOT_LIKE {
            @Override
            public Predicate predicateTo(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.notLike(
                    r.get(c.getPropertyName()), getString(c)
                );
            }
        },
        IN {
            @Override
            public Predicate predicateTo(Criterion c, Root<?> r, CriteriaBuilder b) {
                Object o = c.compareToTo();
                if (o == null)
                    return r.get(c.getPropertyName()).in();
                if (o instanceof Collection)
                    return r.get(c.getPropertyName()).in((Collection) o);
                throw new IllegalArgumentException(c.getPropertyName());
            }
        },
        NOT_IN {
            @Override
            public Predicate predicateTo(Criterion c, Root<?> r, CriteriaBuilder b) {
                Object o = c.compareToTo();
                if (o == null)
                    return b.notIn(r.get(c.getPropertyName()).in());
                if (o instanceof Collection)
                    return b.notIn(r.get(c.getPropertyName()).in((Collection) o));
                throw new IllegalArgumentException(c.getPropertyName());
            }
        },
        NULL {
            @Override
            public Predicate predicateTo(Criterion c, Root<?> r, CriteriaBuilder b) {
                return r.get(c.getPropertyName()).isNull();
            }
        },
        NOT_NULL {
            @Override
            public Predicate predicateTo(Criterion c, Root<?> r, CriteriaBuilder b) {
                return r.get(c.getPropertyName()).isNotNull();
            }
        };

        public abstract Predicate predicateTo(Criterion c, Root<?> r, CriteriaBuilder b);
    };
}
```

### 使用高级 Criteria 定位对象

```java
CriteriaBuilder b;

@SuppressWarnings("unchecked")
private static Comparable<?> getComparable(Criterion c) {
    Object o = c.compareTo();
    if (o != null && !(o instanceof Comparable))
        throw new IllegalArgumentException(c.getPropertyName());
    return (Comparable<?>) o;
}

private static String getString(Criterion c) {
    if (!(c.compareTo() instanceof String))
        throw new IllegalArgumentException(c.getPropertyName());
    return (String) c.compareTo();
}
```

使用 `toPredicate` 方法，将 `SearchCriteria` 转换为 `CriteriaQuery` 的代码会变得简单得多：

```java
public Page<T> search(SearchCriteria criteria, Pageable pageable) {
    CriteriaBuilder builder = this.entityManager.getCriteriaBuilder();

    CriteriaQuery<Long> countCriteria = builder.createQuery(Long.class);
    Root<?> countRoot = countCriteria.from(criteria.domainClass);
    long total = this.entityManager.createQuery(
        countCriteria.select(builder.count(countRoot))
            .where(toPredicate(criteria, countRoot, builder))
    ).getSingleResult();

    CriteriaQuery<T> pageCriteria = builder.createQuery(criteria.domainClass);
    Root<T> pageRoot = pageCriteria.from(criteria.domainClass);
    List<T> list = this.entityManager.createQuery(
        pageCriteria.select(pageRoot)
            .where(toPredicate(criteria, pageRoot, builder))
            .orderBy(toOrder(pageable.getSort(), pageRoot, builder))
    ).setFirstResult(pageable.getOffset())
     .setMaxResults(pageable.getPageSize())
     .getResultList();

    return new PageImpl<>(list, pageable, total);
}
```

```java
private static Predicate toPredicate(SearchCriteria criteria, Root<?> root, CriteriaBuilder builder) {
    Predicate[] predicates = new Predicate[criteria.criteria.size()];
    int i = 0;
    for (Criterion c : criteria.criteria) {
        predicates[i++] = c.getOperator().predicateTo(c, root, builder);
    }
    return builder.and(predicates);
}
```

当然，这在所有情况下都是不够的。假设你知道一个人的生日和名字“Cooper”，但你不知道这是姓还是名。你需要对姓和名的 Predicate（谓词）进行 `OR` 操作，然后将该结果与生日 Predicate 进行 `AND` 操作。你如何使用 criteria API 实现这一点呢？

正如你从日常编程经验中所了解的，当你对两个或多个布尔表达式进行 `AND` 或 `OR` 操作时，结果是一个布尔表达式。同样，使用 criteria API 可以对两个更多的 Predicates 进行 `AND` 或 `OR` 操作以创建一个新的 Predicate。方法包含一个隐式的 `AND`，你也可以显式地将 Predicates 进行 `AND` 或 `OR` 连接。回到名为“Cooper”的人，你可以通过以下代码来实现，其中 `n` 是生日：

```java
criteria.select(root)
  .where(
    builder.or(
      builder.equal(root.get("lastName"), n),
      builder.equal(root.get("firstName"), n)
    )
  );
```

这里的方法接受多个 Predicates 并返回一个由这些 Predicates 进行 `OR` 后的 Predicate。该方法再次充当了 `OR` 后的谓词与生日谓词之间的隐式 `AND`。如果你倾向于显式地 `AND` 属性，你可以这样重写相同的查询：

```java
criteria.select(root)
  .where(
    builder.and(
      builder.equal(root.get("lastName"), n),
      builder.equal(root.get("firstName"), n)
    ),
    builder.equal(root.get("birthDate"), b)
  );
```

使用 `or` 和 `and` 方法（你可以根据代码或 SQL 中需要的括号层级无限深度嵌套它们），你可以执行一些相当复杂的查询。在大多数情况下，标准搜索场景不需要这样的查询，但这种复杂性在批处理和后台任务中可能会派上用场。

```java
pageCriteria.select(pageRoot)
  .where(
    builder.or(
      builder.and(
        builder.equal(expr),
        builder.equal(expr),
        pageRoot.get("property").in(expr)
      ),
      builder.or(
        builder.lessThan(expr),
        builder.greaterThanEqualTo(expr)
      )
    )
  );
```

```java
builder.and(
    builder.equal(expr),
    builder.greaterThan(expr)
);
```



## 创建索引以提高性能

正如你之前读到的，每当你搜索数据时，你都需要一个或多个索引。预先理解这一点非常重要：你不能为每种场景都索引。对数据库表建立的索引越多，插入、更新和删除的速度就越慢。你的目标是在每个应用程序之间取得平衡，而关于索引复杂性的详细讨论在我们那里已经是一整本书的内容了。每个数据库系统都是不同的，没有哪种指南适用于所有情况。通常来说，你的目标应该是尽量让至少 95% 的查询包含索引中的至少一个列（这里的“包含”是指在 `WHERE` 子句中）。你应该优先考虑最频繁的查询而不是普通查询。这可能需要对数据库运行跟踪程序来捕捉经常运行查询的统计信息。取决于你使用的数据库服务器，你可能有工具来分析查询并大致了解需要哪些索引（如果有的话）。

记住，`LIKE` 比较可以使用索引，除非它以通配符开头——发生这种情况时，它将触发全表扫描。扫描是非常糟糕的（非常慢），所以当你知道将执行带有通配符的 `LIKE` 比较时，请尝试包含至少另一个可以使用索引的准则。例如，你可以要求用户指定日期范围，或者自动将结果限制在过去一年创建或更新的内容。

`OR` 连接的准则利用了索引，但在大多数情况下没有 `AND` 连接的准则高效。如果你有两个需要进行 `OR` 操作的对象，请尽可能也包含一个索引 `AND`。

请记住，如果一个查询必须包含索引中的第一列，那么它可以使用该索引中的任何其他列。如果你有一个昂贵的查询，`WHERE` 子句中有一列但没有以该列开头的索引，你将会遇到问题。让该列作为索引的第二或第三列看起来并不理想。

最后，唯一性约束是你的朋友。它们是主键之外是最快的索引（在 Oracle 等某些数据库中，你必须显式创建索引以匹配该约束）。如果你正在创建一个 `User` 表，然后想：“我会在代码中强制用户名唯一性”，请退一步考虑。唯一性约束并不强制唯一性——它还为你提供了一种非常高效的方法来定位记录，而你很可能使用一个列来查找这些记录（否则，你为什么要关心唯一性呢？）。在代码中强制唯一性是肯定的——这是一种最佳实践。但也要加上唯一性约束。

## 在 JPA 中利用全文索引

尽管不同的行业和应用程序类型存在不同的趋势，但现如今用户更倾向于在单个文本框中输入查询来搜索数据。你有几种方法来处理这种情况，全文搜索是一种非常常见的解决方案。在全文搜索中，搜索引擎会分析数据库中每份文档的每个单词，并给出包含相关性评分的匹配。不同的搜索引擎计算相关性的方式不同，但通常来说，它涉及衡量结果与查询的匹配程度，以及搜索词在特定结果中的相互接近程度。包含精确短语的结果其相关性会比仅包含所有单词的结果更高。这种搜索比简单的比较要贵得多，但专门的全文索引可以让任务更高效。这些索引存储每个被索引的单词以及它们出现的次数（最常见的单词权重较低）。当执行全文搜索时，大多数数据库要求你拥有全文索引。在本节中，你将探索如何在 MySQL 中创建全文索引、如何在 JPA 存储库中使用这些索引，以及如何使全文搜索在其他关系型数据库中具有移植性。你将在贯穿本书一直编写的 Customer 项目中添加全文搜索功能，让你的用户和员工能够轻松搜索你的支持工单。你可以参考 `Customer-Support-v17` 项目，该项目可以从 `wrox.com` 下载。

### 在表中创建全文索引

MySQL 与大多数数据库一样，如果你想执行全文搜索，就需要全文索引。在过去的 10 多年里，它作为 `MyISAM` 数据库引擎的一部分已经支持全文索引，但在那期间，只有 `MyISAM` 表可以包含全文索引。这意味着你可以创建一个事务表 (`InnoDB`)，或者创建一个支持全文的表 (`MyISAM`)，但你无法创建一个既是事务型又支持全文的表。然而，从 MySQL 5.6.4 开始，你现在可以在 `InnoDB` 中创建全文索引，成千上万用户期待多年的功能。最后，这让你能够既符合 ACID 又支持全文搜索的表。MySQL 的这一变化并非没有缺陷，所以你应该注意以下几点：

- `MyISAM` 和 `InnoDB` 是 MySQL 伞下的不同引擎，因此它们的全文实现和算法是不完全相同的。这并不是说其中一个比另一个好，但在从 `MyISAM` 切换到 `InnoDB` 时请记住这一点。然而，在 `MyISAM` 和 `InnoDB` 中使用全文搜索和索引在语法上是完全相同的。
- `InnoDB` 全文索引仍然非常年轻（仅发布了 12 个补丁版本，5.6.3 到 5.6.16）。因此，不可避免会有尚未发现和修复的错误。但不要让这阻止你使用它！社区需要你的帮助和问题反馈。
- 虽然 MySQL 有 54 个由于常见性而从索引中过滤掉的默认停用词，但 `InnoDB` 只有 36 个默认停用词。有些人长期以来抱怨 `MyISAM` 的停用词太多，这个问题在 `InnoDB` 中得到了解决（且没有破坏 `MyISAM` 的向下兼容性）。
- 文档提供了针对两个引擎向停止词列表添加和移除项的说明。
- `InnoDB` 引擎计算的相关性评分与 `MyISAM` 引擎计算的完全不同，因此你无法将针对 `MyISAM` 表的查询评分与针对 `InnoDB` 表的查询进行比较。无论这都不是良好的做法。
- `MyISAM` 的 `ft_word_length` 配置本质目的相同，但对应的值不同。如果你之前使用 `MyISAM` 全文搜索，可能希望将 `innodb_ft_min_token_size` 设置为适用于你需求的值。
- 最近修复了一些关键的 `InnoDB` 全文漏洞。请确保你正在运行 MySQL 5.6、5.7、5.8 或更高版本！

如果你在 `MyISAM` 表上创建全文索引，那么在 `InnoDB` 上的任务会有所不同，区别在于你一次只能添加一个全文索引。一个表可以有多个全文索引，但对于某些索引必须在单独的语句中添加。对于你从第一部分就开始工作的 Customer Support 应用程序，你需要对主题、票单主体和评论进行索引。打开 MySQL Workbench 并运行以下语句，它们将创建必要的全文索引。

```sql
USE CustomerSupport;

ALTER TABLE Ticket ADD FULLTEXT INDEX Ticket_Search (Subject, Body);

ALTER TABLE Comment ADD FULLTEXT INDEX Comment_Search (Body);
```

如果你在之前的章节中没有使用 Customer Support 应用程序，你应该运行随下载项目提供的 `entire.sql` 脚本，并在 Tomcat 的 `context.xml` 配置文件中创建相应的 `DataSource`。

> **注意**：当你创建全文索引时，MySQL 会发出消息为“InnoDB rebuilding table to add column FTS_DOC_ID”的警告。不要为此担心；这是正常的。MySQL 会为带有全文索引的 `InnoDB` 表添加一个隐藏列，以唯一标识每个索引记录。在正常使用表时，你永远不会看到它。如果一个表有多个全文索引，MySQL 只添加此隐藏列，且该表的所有索引都共享它。

## 创建和使用可搜索仓库

与之前一样，你需要自定义仓库以使其可搜索。这从一个与你在上一节使用的略有不同的 `SearchableRepository` 开始。你还需要一种方法，不仅返回 `Ticket`，还要返回它与结果的相关性。这需要使用自定义的 JPA 结果集映射，你以前还没有做过这一点，但在本节中将这样做。为了返回实体和相关性，新的 `SearchResult` 类充当这两者的包装器。

```java
public class SearchResult<T> {

    private final T entity;
    private final double relevance;

    public SearchResult(T entity, double relevance) {
        this.entity = entity;
        this.relevance = relevance;
    }

    // accessors
}
```

```java
public interface SearchableRepository<T> {

    Page<SearchResult<T>> search(String query, boolean useBooleanMode, Pageable pageable);
}
```

```java
public interface TicketRepository extends JpaRepository<TicketEntity, Long>, SearchableRepository<TicketEntity> {

}
```

## 使用原生查询和自定义映射进行搜索

JPA 原生不支持全文搜索。Criteria API 或 JPQL 中没有执行全文搜索的规定。然而，JPA 允许你执行原生查询。原生查询直接在数据库中执行，而不是由 JPA 提供者像 JPQL 查询那样进行解释。你可以根据意愿，使用你数据库供应商的 SQL 语法编写原生查询，而不是 JPA 语法。你可以使用原生查询对数据库执行全文搜索。遗憾的是，原生查询不是 `TypedQuery`，但你在创建它们时仍然可以提供领域类，提供者仍然知道如何将结果翻译成正确的实体。

此外，你还需要仅通过一次查询就检索 `TicketEntity` 和一个自定义列，并从数据库中进行搜索。这意味着你不能使用仅带领域类的标准查询。相反，你需要定义一个自定义结果映射，告诉 JPA 如何处理这些额外的列。这通过使用 `javax.persistence.SqlResultSetMapping` 注解映射 `TicketEntity` 类来实现。

```java
@Entity
@Table(name = "Ticket")
@SqlResultSetMapping(
    name = "SearchResultMapping.ticket",
    entities = @EntityResult(entityClass = TicketEntity.class),
    columns = @ColumnResult(name = "_ft_scoreColumn", type = Double.class)
)
public class TicketEntity implements Serializable {

    ...
}
```

## 第 23 章：使用 JPA 和 HIBERNATE SEARCH 搜索数据

自定义结果集被命名，当你在创建应使用该映射的查询时，引用该名称。你可以使用一个或多个实体、列、类属性来指定结果集应该如何映射。使用实体，你可以指定一个或多个应从结果中映射的托管 JPA 实体（因此，你可以使用一次查询返回多个不同的实体）。`columns` 属性允许你将单独列映射到标量值。在这种情况下，`_ft_scoreColumn` 映射到 `Double`。最后，`classes` 属性是 `@ConstructorResult` 注解的数组。使用该属性，你可以将多个标量列映射到任何类的构造函数，并使用这些列构造并返回该类。

`@SqlResultSetMapping` 并不替换它所映射的实体的映射。事实上，它不需要出现在它所映射的任何实体上——它只需要出现在某个地方，以便 JPA 提供者发现自定义结果集映射。如果你不想为此目的使用该注解，可以使用 XML 替代。下述 XML 与之前的是相同的：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-mappings xmlns="http://xmlns.jcp.org/xml/ns/persistence/orm"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence/orm http://xmlns.jcp.org/xml/ns/persistence/orm/orm-mappings_2_1.xsd">
  <result-set-mapping name="SearchResultMapping.ticket">
    <entity class="com.wrox.entities.TicketEntity"/>
    <column name="_ft_scoreColumn" type="java.lang.Double"/>
  </result-set-mapping>
</entity-mappings>
```

通常你会将此 XML 放在 `META-INF/orm.xml`。然而，你可以使用 Spring Framework 的 `LocalContainerEntityManagerFactoryBean` 指定不同的类路径位置：

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactoryBean() {
    LocalContainerEntityManagerFactoryBean factory = new LocalContainerEntityManagerFactoryBean();
    factory.setMappingResources("com/wrox/config/mappings.xml");
    return factory;
}
```

如你所示，`TicketRepositoryImpl` 处理的不只是搜索，还处理了分页。第一个查询找到具有匹配评论的匹配 Ticket，而第二个查询返回了 Ticket 和评论共同的相关性评分，使得匹配的 Ticket 如果拥有匹配的评论，其评分增加；然后按评分降序排序。这还确保了不匹配 Ticket 但有匹配评论的 Ticket 被包含在排序的适当位置。为了让分页正常工作，结果的顺序必须是确定性的。两个记录可能共享相同的评分，因此你总是添加一个反向排序。按主键降序排序是一个很好的选择，因为最新的结果对大多数用户来说更相关。

> **注意**：不要担心相同的 `MATCH` 标准同时出现在查询的 `SELECT` 和 `WHERE` 子句中。MySQL 查询优化器会识别这一点，并知道只对它们进行一次评估。

由于缺少 `TypedQuery`，结果列表必须进行类型转换并抑制未检查警告。由于你使用了自定义结果映射（注意第二个查询是如何引用了名为 `SearchResultMapping.ticket` 的命名结果映射），查询返回的是一个 `Object` 数组列表。`Object` 数组的长度取决于 `@SqlResultSetMapping` 注解中指定的映射数量。你有两个映射（一个针对 `TicketEntity`，一个针对 `Double` 值），结果 `List` 中的 `Object` 数组包含两个元素。Lambda 表达式通过从这些 `Object` 数组创建 `SearchResult` 来填充结果列表。

## 在用户界面中添加搜索功能

你需要在 `TicketService` 中添加一个搜索方法，这是一项简单的任务。大部分工作与 `getAllTickets` 和 `getComments` 方法没有显著区别。

```java
public interface TicketService {

    Page<SearchResult<Ticket>> search(
        @NotBlank(message = "*{validate.ticketService.search.query}")
        String query,
        boolean useBooleanMode,
        @NotNull(message = "*{validate.ticketService.search.page}")
        Pageable pageable
    );
}
```

```java
public class DefaultTicketService implements TicketService {

    @Override
    @Transactional
    public Page<SearchResult<Ticket>> search(String query, boolean useBooleanMode, Pageable pageable) {
        List<SearchResult<Ticket>> list = new ArrayList<>();
        Page<SearchResult<TicketEntity>> entities = this.ticketRepository.search(query, useBooleanMode, pageable);
        entities.forEach(r -> list.add(
            new SearchResult<>(this.convert(r.getEntity()), r.getRelevance())
        ));
        return new PageImpl<>(list, pageable, entities.getTotalElements());
    }
}
```

> **注意**：搜索方法的实现必须创建一组新的 `SearchResult` 对象，这很遗憾，并强化了消除 DTO 过程的必要性，研究如何直接持久化 `Ticket` 并自动映射 `Instant` 字段和附件的方法。不要放弃。你将在下一章学习这些！

在控制器中添加搜索同样简单。你只需要一个简单的方法来显示空搜索表单以及另一个处理它的简单方法。你还需要新的 `SearchForm` 命令对象，它只是一个 POJO。

```java
public class TicketController {

    @RequestMapping(value = "search")
    public String search(Map<String, Object> model) {
```



```java
model.put("searchPerformed", false);

model.put("searchForm", new SearchForm());

return "ticket/search";

}

@RequestMapping(value = "search", search = "query")
public String search(Map<String, Object> model, @Valid SearchForm form,
    Errors errors, Pageable webpage) {

    if (errors.hasErrors()) {
        // 处理错误
    } else {
        model.put("searchPerformed", true);
        model.put("results", this.ticketService.search(
            form.getQuery(), form.isUseBooleanMode()
        ));
    }
    return "ticket/search";
}
```

视图 `/WEB-INF/jsp/view/ticket/ticket.jsp` 虽然很长但很直接，因此此处不再打印。它包含一个简单的表单，用于提供查询并启用布尔搜索操作符、你在上一章看到的分页功能，以及像 `/WEB-INF/jsp/view/ticket/list.jsp` 那样的列出功能。在 `/WEB-INF/tags/template/basic.tag` 中还有一个指向搜索页的新链接。视图以原始形式显示每个结果的关联性（relevance），这对于大多数用户来说是有意义的。如何让这个值更有意义是属于你的练习题。

现在你可以尝试一下了！编译项目并从 IDE 启动 Tomcat。访问 `http://localhost:8080/support/` 登录支持应用程序，并确保你有几个内容不同的工单，这样你的搜索就不会返回所有内容。然后点击搜索链接，输入搜索短语并提交表单。确保搜索一些你确定会返回结果的内容。你现在正在搜索记录了！

# 使全文本搜索具有移植性

按照目前的写法，`TicketRepository` 中的搜索方法是严格针对 MySQL 的。它在任何关系型数据库中都无法工作。你如何让该方法具有移植性呢？嗯，简单来说，你不能——至少不能。并不是每个关系型数据库都支持全文搜索，因此你永远无法让此功能具有移植性。许多 JPA 特性也是如此，例如标识生成的 ID（Oracle 就不支持）。有可能实现通用的移植性，即支持所有支持全文搜索的数据库。

实现这一目标并非易事。通用的部分——例如执行查询和处理分页——可以用通的方式进行。你需要为每个支持的数据库编写生成原生 SQL 查询的不同实现。然后你必须检测底层数据库或要求某种类型的配置。（这并不合理——你一直必须配置 Hibernate ORM 方言。）所以在你大费这个精力之前，必须问问自己是否真的需要它。现实情况下，你在特定的应用程序中只会使用单个关系型数据库。如果你切换或添加另一个数据库，可以添加对全文搜索的支持。

或者，你可以使用 Apache Lucene，它是一个强大的全文搜索库。Lucene 独立于数据库，因此你可以在任何关系型数据库中使用它。但是，你需要自己处理数据库实体与 Lucene 文档之间的映射。这涉及到在数据创建或更新时创建索引，并在搜索时查询索引。这可能是一个复杂的过程，我们将在下一章详细介绍。

# 使用 APACHE LUCENE 和 HIBERNATE SEARCH 索引任何数据

Lucene 是一个强大的全文搜索引擎，可用于索引任何类型的数据。它提供了广泛的功能，如分析（analysis）、词干（stemming）和高亮（highlighting）。在本章中，我们将探索如何结合 Lucene 和 Hibernate Search，为你的 JPA 应用提供全文搜索功能。

Hibernate Search 是一个将 Lucene 与 Hibernate 集成的高级 API。它允许你使用 Hibernate 注解自动索引实体，从而简化索引和查询的过程。我们将学习如何设置 Hibernate Search、配置实体并执行复杂的查询。

Lucene 的另一个强大特性是你可以配置其进行异步建立索引。这意味着你的创建、更新和删除操作不会被全文索引过程减慢。这是一项非常有用的功能，现代关系型数据库在全文本索引方面根本无法提供这种能力。

当你单独使用 Apache Lucene 时，你通过调用 Lucene API 来对数据进行索引（或从索引中删除数据）。这无论你在同一个 Java 进程中使用 Lucene（类似于内存中数据库）或使用 Lucene 搜索服务器时都适用。本书将不会涵盖 Lucene API。相反，请使用 Hibernate Search，它为 JPA 和 Hibernate ORM 实体的索引和搜索提供了一个更简单的接口。当你通过 JPA 添加和更新实体时，Hibernate Search 会自动在 Lucene 中索引你的实体；当你在 Lucene 中搜索它们时，它会通过 JPA 获取你持久化的实体。

## 使用索引元数据标记实体

你不需要为所有实体手动配置 Lucene 并在每次添加或更新实体时都管理 Lucene API，而是可以对想要索引的实体使用 Hibernate Search 注解，以便让 Hibernate Search 为你完成所有这一切。只需将 Lucene 视为 JDBC API 以及 Lucene 的 O/M 即可。Search-Engine 项目代表一个极其原始的论坛，用户可以在其中发布消息。它没有任何回复功能。`User` 实体显然是一个简单的实体。它只包含一个 ID 和一个用户名。

```java
@Entity
@Table(name = "UserPrincipal")
public class User {
    private long id;
    private String username;

    @Id
    @Column(name = "UserId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ... }

    public void setId(long id) { ... }

    @Basic
    @Field
    public String getUsername() { ... }

    public void setUsername(String username) { ... }
}
```

这个实体只是标准的 JPA 实体。在这种情况下，你实际上并不需要对用户实体执行全文搜索，但你确实需要根据创建帖子的用户名来搜索论坛帖子的能力。那么它是如何运作的呢？来看 `ForumPost` 实体。

```java
@Entity
@Table(name = "Post")
@Indexed
public class ForumPost {
    private long id;
    private User user;
    private String title;
    private String body;
    private String keywords;

    @ManyToOne(fetch = FetchType.EAGER, optional = false)
    @JoinColumn(name = "UserId")
    @IndexedEmbedded
    public User getUser() { ... }

    public void setUser(User user) { ... }

    @Basic
    @Field
    public String getTitle() { ... }

    public void setTitle(String title) { ... }

    @Lob
    @Field
    public String getBody() { ... }

    public void setBody(String body) { ... }

    @Basic
    @Field(boost = @Boost(2.0))
    public String getKeywords() { ... }

    public void setKeywords(String keywords) { ... }
}
```

`ForumPost` 使用了两个你尚未学习过的 JPA 注解：`@ManyToOne` 和 `@JoinColumn`。你将在下一章中探索它们，但目前它们对于演示 Hibernate 的能力是必须的。这个实体标记为 `@org.hibernate.search.annotations.Indexed` 实体，表示该实体具备全文索引的资格。当你添加或保存它时，Hibernate Search 会自动创建或更新文档。`@org.hibernate.search.annotations.DocumentId` 注解告诉 Hibernate 哪个属性是文档 ID。它被放置在 id 属性上仅用于演示目的；如果你留着它，Hibernate 将自动回退到被以下注解标记的属性。

`@org.hibernate.search.annotations.IndexedEmbedded` 是一个值得关注的注解。它告诉 Hibernate Search 该属性是一个带有索引字段的实体，应该作为此文档的一部分被索引。你可以在搜索中包含 `user` 属性，并根据发布该帖子的用户来查找帖子。

`@org.hibernate.search.annotations.Field` 注解同时用于 `User` 和 `ForumPost` 实体。它将一个属性标记为应该进行全文索引并具备搜索资格的属性，并且它有许多属性可以影响属性的索引和存储方式。理解如何使用这些属性需要对 Lucene 有深入的理解，而本书并未提供这种深度。在许多情况下，使用默认值是非常安全的。在 `ForumPost` 实体中，`keywords` 属性通过 `@org.hibernate.search.annotations.Boost` 和 `boost` 属性字面意思地提供了额外的权重。这指定了从 `keywords` 属性得出的相关性得分应该增加的因子。在这种情况下，作者认为用户指定的 `keywords` 索引了帖子的内容，因此关键词在得分中具有更大的权重是合理的。

Search-Engine 项目中的 `create.sql` 文件创建了 SearchEngine 数据库以及该实体所需的表。它在表中填充了几个用户。你应该使用 MySQL Workbench 并执行此脚本来创建数据库，然后在 Tomcat 的 `context.xml` 配置中创建以下 DataSource 资源：

```xml
<Resource name="jdbc/SearchEngine" type="java.sql.DataSource" maxActive="20" maxIdle="5" maxWait="10000" username="tomcat" password="password1234" driverClassName="com.mysql.jdbc.Driver" defaultTransactionIsolation="READ_COMMITTED" url="jdbc:mysql://localhost/SearchEngine" />
```

## 使用 Hibernate Search

当你准备好进行索引时，你必须配置 Hibernate Search 并使用 Hibernate API 执行搜索。

## 配置 Hibernate Search

配置 Hibernate Search 非常简单。只需添加以下属性：

```java
@Bean
public LocalContainerFactoryBean entityManager() {
    Map<String, Object> properties = new HashMap<>();
    properties.put("hibernate.search.database.action", "none");
    properties.put("hibernate.search.directory.provider", "filesystem");
    properties.put("hibernate.search.indexBase", "../searchindexes");
    HibernateJpaAdapter adapter = new HibernateJpaAdapter();
    adapter.setDatabasePlatform("org.hibernate.dialect.MySQL5Dialect");
    LocalContainerFactoryBean factory = new LocalContainerFactoryBean();
    factory.setJpaVendorAdapter(adapter);
    factory.setDataSource(searchDataSource());
    factory.setPackagesToScan("com.trox.entities");
    factory.setSharedResourceMode(SharedResourceMode.ENABLE_SELECTIVE);
    factory.setValidationMode(ValidationMode.NONE);
    factory.setPropertyMap(properties);
    return factory;
}
```

## 索引数据

添加这些属性做了几件事：

- 启用了 Hibernate ORM 使用 Hibernate Search。
- 指定了全文索引使用独立的 Lucene（无 Solr）并将索引保存到本地文件系统。
- 指定了 `../searchindexes`（相对于当前目录）作为保存全文索引的位置。

当然，如果你使用 Tomcat 集群或从多个 JVM 访问这些索引，这种配置将不再安全。你也可以使用这些属性的不同值来配置 Hibernate Search 使用 Solr 服务器，从而在集群环境中是安全的。对于本地测试目的，这种配置已经足够。

## 创建 Lucene 可搜索存储库

创建可搜索存储库与你在之前的版本中创建的原生全文库不同，但并不更复杂。通常，你从一些基础接口如 `SearchableRepository` 和 `ForumRepository` 开始。

```java
public interface SearchableRepository<T> {
    Page<T> search(String query, Pageable pageable);
}
```

```java
public interface ForumRepository extends JpaRepository<ForumPost, Long>, SearchableRepository<ForumPost> {
}
```

按照惯例，工作发生在 `ForumRepositoryImpl` 中，如列表 23-2 所示。一个关键区别点是使用了 `org.hibernate.search.FullTextEntityManager`，这是 Hibernate JPA 集成的关键接口。它扩展了 `EntityManager` 以添加一个线程绑定、事务关联的 `EntityManager` 代理，该代理为每个事务委托一个新的 `EntityManager`，Spring Framework 注入的 `FullTextEntityManager` 是真实的。这意味着每当你调用搜索方法时都会创建一个新实例（这实际上当你通过 Spring 注入 `EntityManager` 代理时在后台发生的情况）。此外，Hibernate Search 只有在能够访问实际 Hibernate ORM `EntityManager` 实现（而不是包装器或代理）时才能创建 `FullTextEntityManager`。

# 列表 23-2: ForumRepositoryImpl.java

```java
public class ForumRepositoryImpl implements SearchableRepository<ForumPost> {
    @PersistenceContext EntityManager entityManager;
    EntityManagerProxy entityManagerProxy;

    @Override
    public Page<SearchResult<ForumPost>> search(String query, Pageable pageable) {
        FullTextEntityManager manager = this.getFullTextEntityManager();
        QueryBuilder builder = manager.searchFactory().buildQuery(new Builder())
            .entity(ForumPost.class).get();
        Query lucene = builder.keyword()
            .onFields("title", "body", "keywords", "user.username")
```



```java
.matching(query)
    .create();

FullTextQuery q = manager.createFullTextQuery(lucene, ForumPost.class);

q.setProjection(FullTextQuery.THIS, FullTextQuery.SCORE);

long total = q.getResultSize();

q.setFirstResult(pageable.getOffset())
    .setMaxResults(pageable.getPageSize());

@SuppressWarnings("unchecked") List<Object[]> results = q.getResultList();

List<SearchResult<ForumPost>> list = new ArrayList<>();

results.forEach(o -> list.add(new SearchResult<ForumPost>(o[0], (Float)o[1])));

return new PageImpl<>(list, pageable, total);
}

private FullTextEntityManager getFullEntityManager() {
    return search.getFullEntityManager(
        this.entityManagerProxy.getTargetEntityManager());
}

@PostConstruct
public void initialize() {
    if((this.entityManager instanceof EntityManagerProxy) {
        throw new FatalBeanException("Entity manager " + this.entityManager +
            " was not a proxy");
    }
    this.entityManagerProxy = (EntityManagerProxy)this.entityManager;
}
```

# 使用 Apache Lucene 和 Hibernate Search 索引任何数据 | 691

> 注意：如果你直接使用 Hibernate API（而不是 JPA），你将使用 `org.hibernate.search.FullTextSession` 接口，它为 `org.hibernate.Session` 添加了全文功能，而不是 FullTextEntityManager。

为了解决这个问题，`initialize` 方法首先将 `EntityManager` 缓存为 `org.springframework.framework.orm.jpa.EntityManagerProxy`，这是 Spring 注入的 `EntityManager` 实现的接口。该方法只调用一次，但每次需要 `FullTextEntityManager` 时都会调用 `getFullTextEntityManager`，且仅在事务内调用。它调用 `EntityManagerProxy` 上的 `getTargetEntityManager` 来获取 Hibernate ORM `EntityManager` 实现。然后它使用 `org.hibernate.search.jpa.Search.getFullTextEntityManager` 从底层的 `EntityManager` 获取 `FullTextQuery`。

当我们搜索 `FullTextEntityManager` 时，它会为 `ForumPost` 条目创建一个 `org.hibernate.search.query.QueryBuilder`。然后，它使用该构建器为查询字符串和你想搜索的 `ForumPost` 创建一个 `org.apache.lucene.search.Query`。注意使用点符号（列表 23-2 中的加粗部分）来搜索实体中 user 字段下的 username 字段。你可以根据需要使用任意层级的点符号来包含嵌入实体。另外注意，如果你愿意，也可以直接使用 Lucene API 创建此查询，而不是使用 `QueryBuilder`。

接下来的代码为 Lucene 查询和 `ForumPost` 条目检索一个 `org.hibernate.search.jpa.FullTextQuery`。`FullTextQuery` 是一个 `java.persistence.Query`，能够执行所有必要的 Lucene 和 JPA 查询。它设置了查询的投影，告诉 Hibernate Search 将实体作为对象数组中的第一个元素（`FullTextQuery.THIS`），并将相关性评分作为第二个元素（`FullTextQuery.SCORE`），这与你之前用于检索实体和分数的技巧几乎相同。

最后，代码获取了预期的总结果大小、分页边界、获取结果列表，并将其转换为 `SearchResultForumPost` 的 `Page`。唯一需要注意的是，Lucene 不参与 JPA 事务，因此结果数量在 `getResultSize` 和 `getResultList` 之间可能会发生变化。

# 测试搜索引擎

在测试你的 Apache Lucene 仓库之前，你需要采取的最后一步是创建一个事务型服务、控制器和用户界面。`MainService` 和 `DefaultMain` 非常简单，仅作为控制器和仓库之间标记了 `@Transactional` 的透传层。`MainController` 也很简单。你所习惯的许多验证和检查请求，其实只是对 Lucene 搜索能力的测试。它响应主页的请求，并在 `/WEB-INF/jsp/view/add.jsp` 中提供一个简单的表单用于创建论坛帖子。控制器的处理逻辑应该对你来说非常熟悉，它们几乎与客户支持应用程序中 `TicketController` 的方法完全相同。最后，`/WEB-INF/jsp/view/search.jsp` 视图处理表单搜索、搜索结果和分页，其方式与客户支持应用程序非常相似。

现在你已经查看了代码的其余部分，请按照以下步骤进行测试：

1. 编译应用并从 IDE 启动 Tomcat。使用 Tomcat 目录下的 Lucene 索引目录（如果你使用 Windows，则可能是 `C:\Program Files\Apache Tomcat\8.0`）。
2. 在浏览器中访问 `http://localhost:8080/forums/` 并创建几个服务器帖子。在每个帖子提供的用户名，在 Nicholas、Sarah、Mike 和 John 之间切换。这些是你之前创建的数据库中预填充的用户。
3. 在创建了几个具有不同内容的帖子后，检查搜索链接并尝试不同的搜索查询。确保你也搜索了一个或两个用户名，以找到这些用户的帖子。

### 总结

在本章中涵盖了大量内容。你学习了数据搜索和索引的一些基本概念，并探索了如何使用 JPA Criteria API 创建极其复杂的查询。你被介绍了全文搜索的概念，学习了如何在 MySQL 中创建全文索引，并探索了 Apache Lucene 和 Hibernate Search，创建了被索引的实体以及能够使用 Lucene 全文索引搜索这些实体的仓库。重要的是，你对 Apache Lucene 和 Hibernate Search 仅仅触及了皮毛。关于它们的使用和功能，可以写数百页的内容，希望本章激发了你进一步研究这些主题的兴趣。

下一章将结束 JPA 持久 API 主题。你将学习如何创建一些复杂的映射，并最终使用 JPA 转换器将 Java 8 日期和时间类型包含在你的实体中。你还学习了在本章上一节看到的 `@ManyToMany` 和 `@JoinTable` 注解。

# 创建高级映射和自定义数据类型

### 本章内容

- 为什么要转换非标准数据类型？
- 如何在实体内部嵌入 POJO
- 如何定义实体之间的关系
- 使用修订版本号和时间戳对实体进行版本控制

### WROX.COM 代码下载

你可以在 http://www.wrox.com/go/javaapps 找到本章的代码。代码分为以下几个主要示例：

- Advanced-Mappings Project
- Customer-Support-v1

正如你所见，你才刚刚开始。在本章中，你将涵盖所有这些主题，并在完成后，你将拥有无限的方法来使用 JPA 实体。在本章的大部分内容，你可以参考 Advanced-Mappings 项目，该项目可以在 wrox.com 代码下载站点下载。它涵盖了该项目中的映射，但没有提到你已经熟悉的 Spring JPA 存储库（repositories）、控制器（controllers）或简单接口。在本章的任何时候，你都可以从 IDE 编译并启动项目，或者访问 http://localhost:8080/mappings，并使用主页上的链接来测试实体映射。

在本章结束时，你将运用所掌握的主题，使客户支持应用程序中持久化实体任务变得更容易。

## 转换非标准数据类型

在第 20 章中，你学习了 JPA 供应商需要支持的 `@Basic`、`@Lob`、`@Enumerated` 和 `@Temporal` 类型。虽然非常详尽，但并不意味着它能满足你的所有需求。你已经看到，它不包含新的 JPA 8 日期和时间类型。（但请关注 JPA 下一版本对此的支持）某些提供者提供了额外的类型——例如，Hibernate ORM 自动支持 Joda Date 类型。Hibernate 5.0 可能会在某个时刻支持 JPA 8 日期和时间类型。依赖此是不可移植的，因为是非标准的。如果你某天切换了提供者，你的实体可能会停止工作。

那么你对此能做什么呢？在 JPA 之前的版本中，你无法做任何事情。在 JPA 2.1 之前，没有办法可以持久化和检索不受支持的简单类型（本身不是 POJO 的类型）。这很大地限制了你的选择。因此，大多数主要的供应商都提供了私有 API，允许你定义自定义类型。使用 Hibernate ORM，你可以使用 `org.hibernate.user.UserType` 或 `org.hibernate.user.CompositeType`，然后用 `org.hibernate.annotations` 注解属性以指定负责该属性的 UserType 或 CompositeType 实现。然而，这并不比依赖特定提供者支持的非标准类型更具可移植性，而且在你切换提供者时它会失效。

这个问题最终在 JPA 2.1 中通过属性转换器（attribute converters）得到了解决，尽管它们并非没有缺点。

## 理解属性转换器

属性转换器是任何实现了 `javax.persistence.AttributeConverter` 的类。属性转换器的目的是在实体属性在不支持的简单类型和支持的基本类型之间进行转换。这在几乎所有情况下都有效。使用 JDBC 时，你最终必须将值保存到数据库之前，将你所能每个简单类型转换为基本类型之一。例如，如果你创建了一个持有无符号整数的自定义 `UnsignedLong` 类，将值存入和取出数据库的方法是调用 `PreparedStatement.setBigDecimal` 方法和 `ResultSet.getBigDecimal` 方法。这意味着你可以通过实现一个在 `UnsignedLong` 和 `BigDecimal` 之间转换的 `AttributeConverter` 来完成这一点。

## 696 | 第 24 章 创建高级映射和自定义数据类型

讽刺的是，特殊情况是转换涉及日期时间的类型。JDBC 处理的 `setDate`、`setTime`、`setTimestamp`、`getDate`、`getTime` 和 `getTimestamp` 方法处理 `java.sql.Dates, Timestamp`。从 JDBC 4.1 开始，你必须使用这些类型在数据库中设置和检索日期和时间。你可能记得，从 JDBC 4.2 开始，增加了支持不仅仅是类型的方法。由于可以直接访问 JDBC 4.1 和 JDBC 4.2 驱动，以下代码是持久化 `Instant`、`LocalDateTime`、`LocalTime`、`OffsetDateTime`、`OffsetTime` 和 `ZonedDateTime` 属性的正确方式。

同样，你会使用类似代码检索这些类型：

```java
instant = result.getObject("Instant", Instant.class);
LocalDateTime = result.getObject("LocalDateTime", LocalDateTime.class);
localTime = result.getObject("LocalTime", LocalTime.class);
offsetDateTime = result.getObject("offsetDateTime", OffsetDateTime.class);
zonedDateTime = result.getObject("zonedDateTime", ZonedDateTime.class);
```

然而，`AttributeConverter` 不转换为 `PreparedStatement` 和 `ResultSet` 对象。它只能转换自定义类型和 JPA 支持的目标类型。因此，你必须编写在这些类型与 `java.sql.Date`、`Time` 和 `Timestamp` 之间转换的 `AttributeConverters`，或者使用像 Hibernate 的 `UserType` 这样的私有 API。你记得第 20 章，所有主要的数据库供应商提供 JDBC 4.2 驱动之前已经过了很多年。如果没有对这些新方法的支持，诉诸 `UserType` 是徒劳的。所以你最好的做法是坚持使用 `AttributeConverters`。

### 理解转换注解

实现 `AttributeConverter` 是开始和使用转换器的第一步。你还有几个用于让你的转换器起作用的注解。其中第一个是 `@javax.persistence.Converter`。实现 `AttributeConverter` 的具体类必须标记为 `@Converter`，或者在 JPA 映射文件（如 `orm.xml`）的 `<converter>` 元素中指定。此外，如果你不想将其包含在你的持久化单元中，或者启用了 `<exclude-unlisted-classes>`，你必须在 `persistence.xml` 中使用 `<class>` 或 `<jar-file>` 指明该转换器是一个托管类。`@Converter` 的 `autoApply`（默认为 `false`）指示 JPA 提供者是否应该自动将转换器应用到匹配的属性。属性转换器的定义通常看起来如下：

```java
@Converter
public class InstantConverter implements AttributeConverter<Instant, Timestamp> {
```

如果 `autoApply` 为 `false` 或省略（默认为 `false`），你必须在 JPA 属性上使用同命名的 `@javax.persistence.Convert` 注解，以指示转换器适用于哪些属性。你可以注解字段（如果使用字段访问）、访问器方法（如果使用方法访问）或 `@Convert`。以下三种 `@Convert` 的用法是等效的：

```java
public class MyEntity {
    @Convert(converter = InstantConverter.class)
    private Instant dateCreated;
    ...
    public Instant getDateCreated() { ... }
    public void setDateCreated(Instant instance) { ... }
}
```

```java
public class MyEntity {
    private Instant dateCreated;
    @Convert(converter = InstantConverter.class)
    public Instant getDateCreated() { ... }
    public void setDateCreated(Instant instance) { ... }
}
```

```java
@Convert(attributeName = "dateCreated", converter = InstantConverter.class)
public class MyEntity {
    private Instant dateCreated;
    ...
    public Instant getDateCreated() { ... }
    public void setDateCreated(Instant instance) { ... }
}
```

如果你使用后的方法，可能有多个需要转换的属性。虽然注解单个属性更容易，但你可以使用 `@javax.persistence.Converts` 注解在实体级别组组多个 `@Convert` 注解。

```java
@Convert({
    @Convert(attributeName = "dateCreated", converter = InstantConverter.class)
    @Convert(attributeName = "dateModified", converter = InstantConverter.class)
})
public class MyEntity {
    private Instant dateCreated;
```



## 创建和使用转换器

在很多情况下，你的属性非常简单。Advanced-Mappings 项目中的 `InstantConverter` 每个方法只有几行代码。

```java
@Converter
public class InstantConverter implements AttributeConverter<Instant, Timestamp> {

    @Override
    public Timestamp convertToDatabaseColumn(Instant instance) {
        return instance == null ? null : new Timestamp(instance.toEpochMilli());
    }

    @Override
    public Instant convertToEntityAttribute(Timestamp timestamp) {
        return timestamp == null ? null : Instant.ofEpochMilli(timestamp.getTime());
    }
}
```

`User` 实体演示了使用自定义属性转换器来持久化 `dateJoined` 属性，而无需使用 DTO 和服务来转换值。

```java
@Entity
@Table(name = "UserPrincipal")
public class User {

    private long id;
    private Instant dateJoined;
    private String username;

    @Id
    @Column(name = "UserId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ... }
    public void setId(long id) { ... }

    @Convert(converter = InstantConverter.class)
    public Instant getDateJoined() { ... }
    public void setDateJoined(Instant dateJoined) { ... }

    @Basic
    public String getUsername() { ... }
    public void setUsername(String username) { ... }
}
```

最后，在 `RootContextConfiguration` 中，`com.wrox.site.converters` 包被添加到 `LocalContainerEntityManagerFactoryBean` 的 `packagesToScan` 属性中。这确保了转换器被添加到持久化单元中，以便在应用程序中使用。

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactoryBean() {
    LocalContainerEntityManagerFactoryBean factory = new LocalContainerEntityManagerFactoryBean();
    factory.setDataSource(this.advancedMappingsDataSource());
    factory.setPackagesToScan("com.wrox.site.entities", "com.wrox.site.converters");
    factory.setSharedCacheMode(SharedCacheMode.ENABLE_SELECTIVE);
    return factory;
}
```

## 在实体中嵌入 POJO

有时候，让你的实体属性仅为简单类型会不方便。考虑经典的电话号码问题：`Person`（人）有一个电话号码，但你想将国家代码和电话号码存储在单独列中。你可以创建 `countryCode` 和 `phoneNumber` 属性，但那样很别扭。更理想的解决方案是拥有一个类型为 `PhoneNumber` 的 `phoneNumber` 属性，该属性又包含 `countryCode` 和 `number`。使用 JPA 嵌入类型（embeddable types）可以实现这种方法。嵌入类型本质上是其所属实体的部分。它们都存储在相同的表中，并共享相同的 ID。它们不是实际的实体。

### 表明该类型是嵌入的

在许多方面，嵌入类型看起来非常像实体。它可以包含任意数量的属性，并带有 `@Basic`、`@Column`、`@Lob`、`@Temporal`、`@Enumerated`、`@Convert` 等注解。然而，它不能标记 `@Entity` 或 `@Table`，也不能包含任何带有 `@Id` 或 `@Embeddable` 注解的属性。它可以包含其他嵌入类型的属性。

要将一个类标记为嵌入的，你只需要使用 `@javax.persistence.Embeddable` 进行注解。如下文中的 `PhoneNumber` 类所示，该注解表示它可以作为属性嵌入到应用程序中的任何实体中。嵌入类必须作为类注册到你的持久化单元中。这意味着你必须在持久化单元配置的 `<class>` 或 `<jar-file>` 中指定它们，或者在持久化单元配置中禁用 `<exclude-unlisted-classes>`，或者让 Spring 的 `LocalContainerEntityManagerFactoryBean` 发现这些类。通过将 `PhoneNumber` 放在 `com.wrox.site.entities` 包中，它会被自动发现并添加到持久化单元中。

```java
@Embeddable
public class PhoneNumber {
    private String countryCode;
    private String number;

    @Basic
    @Column(name = "PhoneNumber_CountryCode")
    public String getCountryCode() { ... }
    public void setCountryCode(String countryCode) { ... }

    @Basic
    @Column(name = "PhoneNumber_Number")
    public String getNumber() { ... }
    public void setNumber(String number) { ... }
}
```

注意，`PhoneNumber` 包含两个属性，每个属性映射到它自己的列。任何实体都可以包含 `PhoneNumber` 属性，该实体的表就有两列：`PhoneNumber_CountryCode` 和 `PhoneNumber_Number`。

### 将属性标记为嵌入

实际上，嵌入一个嵌入类型非常简单。只需将类型的属性标记为 `@javax.persistence.Embedded` 注解。你不能为该属性标记任何其他注解，例如 `@Basic`、`@Temporal` 或 `@Column`。这在 `Person` 实体中得到了演示。

```java
@Entity
public class Person {
    private long id;
    private String firstName;
    private String lastName;
    private PhoneNumber phoneNumber;

    @Id
    @Column(name = "PersonId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ... }
    public void setId(long id) { ... }

    @Basic
    public String getFirstName() { ... }
    public void setFirstName(String firstName) { ... }

    @Basic
    public String getLastName() { ... }
    public void setLastName(String lastName) { ... }

    @Embedded
    public PhoneNumber getPhoneNumber() { ... }
    public void setPhoneNumber(PhoneNumber phoneNumber) { ... }
}
```

> **注意**：`@Embedded` 的使用仅用于实体中的非 ID 属性。你可以将嵌入类型作为复合实体 ID，但你必须使用 `@javax.persistence.EmbeddedId` 来标记 ID 属性，而不是 `@Embedded`。你已经在第 20 章中探索过这样创建复合 ID。

正如前面提到的，嵌入类型可以包含嵌入属性。这的一个极佳例子是接下来的 `Address` 和 `PostalCode` POJO。

```java
@Embeddable
public class PostalCode {
    private String code;
    private String suffix;

    @Basic
    @Column(name = "Postal_Code")
    public String getCode() { ... }
    public void setCode(String code) { ... }

    @Basic
    @Column(name = "Postal_Code_Suffix")
    public String getSuffix() { ... }
    public void setSuffix(String suffix) { ... }
}

@Embeddable
public class Address {
    private String street;
    private String city;
    private String state;
    private String country;
    private PostalCode postalCode;

    @Basic
    @Column(name = "Address_Street")
    public String getStreet() { ... }
    public void setStreet(String street) { ... }

    @Basic
    @Column(name = "Address_City")
    public String getCity() { ... }
    public void setCity(String city) { ... }

    @Basic
    @Column(name = "Address_State")
    public String getState() { ... }
    public void setState(String state) { ... }

    @Basic
    @Column(name = "Address_Country")
    public String getCountry() { ... }
    public void setCountry(String country) { ... }

    @Embedded
    public PostalCode getPostalCode() { ... }
    public void setPostalCode(PostalCode postalCode) { ... }
}
```

### 覆盖列名

`PostalCode` 的设计可以单独使用，也可以作为 `Address` 的一部分。问题在于列名。按照写法，`Person` 表将具有 `Address_Street`、`Address_City`、`Address_State`、`Address_Country`、`PostalCode_Code` 和 `PostalCode_Suffix`。从这些名称并不看出邮政编码是地址的一部分。你可以在 `Person` 实体中使用 `@javax.persistence.AttributeOverride` 注解来轻松修复此问题，该注解允许你更改嵌入属性在实体中的列映射。你还可以使用 `@javax.persistence.AttributeOverrides` 注解，它允许你组合多个覆盖。

```java
@Entity
public class Person {
    ...
    private Address address;
    ...

    @AttributeOverrides({
        @AttributeOverride(name = "postalCode.code",
            column = @Column(name = "Address_PostalCode_Code")),
        @AttributeOverride(name = "postalCode.suffix",
            column = @Column(name = "Address_PostalCode_Suffix"))
    })
    public Address getAddress() { ... }
    public void setAddress(Address address) { ... }
}
```

`name` 属性使用点符号表示覆盖哪些列详情。`Address` 实体包含一个名为 `postalCode` 的属性，两个名称的第一部分都是 `postalCode`。此名称基于属性而不是属性类型，所以如果 `Address` 的 `PostalCode` 属性名为 `zip`，那么地址名称的第一部分将是 `zip`。名称的第二部分是正在被覆盖的 `PostalCode` 内的属性。

通过这种符号，你可以继续指定更深层的覆盖。属性覆盖还使得在任何给定的实体（或其他嵌入类型）中多次使用同一个嵌入类型成为可能。你只需要在除一次之外的所有使用场景中覆盖列名。（尽管通常你会覆盖所有场景。）通过这些更改，以下语句为 `Person` 实体创建了相应的表和列。

```sql
CREATE TABLE Person (
    PersonId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    FirstName VARCHAR(60) NOT NULL,
    LastName VARCHAR(60) NOT NULL,
    PhoneNumber_CountryCode VARCHAR(5) NOT NULL,
    PhoneNumber_Number VARCHAR(15) NOT NULL,
    Address_Street VARCHAR(100) NOT NULL,
    Address_City VARCHAR(100) NOT NULL,
    Address_State VARCHAR(100) NOT NULL,
    Address_Country VARCHAR(100) NOT NULL,
    Address_PostalCode_Code VARCHAR(10) NOT NULL,
    Address_PostalCode_Suffix VARCHAR(5)
) ENGINE = InnoDB;
```

## 定义实体之间的关系

正如你所见，实体与其他实体之间存在关系是非常常见的。例如，客户支持应用程序中的工单（Tickets）拥有附件（Attachments），到目前为止，你一直在服务层中管理这种关系。然而，这一步骤是不必要的。如果某个特定实体与其他实体有许多关系，你可能仍然想在某些情况下使用它。但除去这些特殊情况，你可以直接在这些实体内部定义实体关系，JPA 提供程序可以在你需要的时候获取你所需的实体。

### 理解一对一关系

一对一关系可能是你最可能定义的。一对一关系意味着实体 A 最多与一个实体 B 关联，而实体 B 最多与一个实体 A 关联。通常来说，这种关系违反了范式的规则，但符合面向对象的设计实践。然而，在某些情况下，它是解决特殊问题的更实用的方法。例如，如果一个实体包含数百个属性，你可能希望将这些属性分组到子实体中，使所有相关属性属于它们自己的实体。这个虚构的 `Employee` 实体展示了这样的情况。

```java
@Entity
public class Employee {
    private long id;
    ...
    private EmployeeInfo info;

    @Id
    @Column(name = "EmployeeId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    ...
}
```



# 定义实体之间的关系

```java
public long getId() { ... }

public void setId(long id) { ... }

@ToOne(mappedBy = "employee", fetch = FetchType.LAZY,
       cascade = CascadeType.ALL, orphanRemoval = true)
public EmployeeInfo getInfo() { ... }

public void setInfo(EmployeeInfo employeeInfo) { ... }
}

@Entity
```

```java
public class EmployeeInfo {

    private long id;
    private Employee employee;
    ...

    @Id
    public long getId() { ... }

    public void setId(long id) { ... }

    @OneToOne(mappedBy = "info")
    @Column(name = "EmployeeId")
    public Employee getEmployee() { ... }

    public void setEmployee(Employee employee) { ... }
}
```

如果你想在关系的某侧或另一侧定义关系。例如，你可以在 `Employee` 中保留 `info` 属性但在 `EmployeeInfo` 中省略 `employee` 属性（或反之）。在这种情况下，关系是双向的，因此你必须在 `Employee` 的属性和 `EmployeeInfo` 的 `employee` 属性上使用 `@javax.persistence.OneToOne` 注解，并且都必须指定 `mappedBy` 属性。

此属性告诉 JPA 提供程序关系末端的属性映射回“this”。`fetch` 属性指明了何时使用 `java.persistence.FetchType` 将相关实体检索回数据库。`FetchType.EAGER` 意味着 JPA 提供程序在检索实体时必须获取这些值。另一方面，`FetchType.LAZY` 作为对 JPA 提供程序的提示，表示它只在第一次访问时才获取这些值（这可能节省一次数据库访问）。然而，JPA 提供程序并不要求支持懒加载，因此值可能会被急加载。在这里，`fetch` 属性默认为 `FetchType.EAGER`，这通常用于一对一关系。Hibernate ORM 和 EclipseLink 支持懒加载，但对于一对多关系，你必须启用织入（weaving）。你可以在“完善客户支持应用程序”部分学习更多关于如何操作此。

`@OneToOne` 的 `cascade` 属性表示在指定指令的实体上执行操作时，相关实体会发生什么。使用 `java.persistence.CascadeType` 你可以指定 `MERGE`、`PERSIST`、`REFRESH`、`REMOVE` 中的一个或多个值。每个值表示级联到相关实体的 `EntityManager` 操作。你也可以使用 `ALL` 来指定所有五个值。对于一对一关系，你可能不想在所有实体内部指定级联指令。你可能想在所有实体内部指定级联指令。`orphanRemoval` 属性指明实体是否应该从数据库中删除。默认（`false`）意味着如果你将 `Employee` 的属性设置为 `null`，数据库中的 `EmployeeInfo` 记录将不会删除。这几乎不是你想要的结果，所以在示例中你应该使用 `true`。

最后，`optional` 属性指明关系是否为可选。如果为 `false`，则表示关系的双方都必须有一个值。它默认是 `true`，意味着关系的一侧可以为 `null`。

## 使用一对多 (One-to-Many) 和 多对一 (Many-to-One) 关系

一对多和多对一关系是你应用程序中常见的场景。它们之间的关系非常紧密。事实上，每当你在一个实体上指定一对多关系时，你就会在另一个实体上获取相应的多对一关系。在一对多关系中，实体 A 与多个实体 B 有关系。这通常由 A 中的某种集合表示，该集合存储了一些内容。

```java
@Entity
public class Applicant {

    private long id;
    private String firstName;
    private String lastName;
    private boolean citizen;
    private Set<Resume> résumés = new HashSet<>();

    @Id
    @Column(name = "ApplicantId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ... }

    public void setId(long id) { ... }

    @Basic
    public String getFirstName() { ... }

    public void setFirstName(String firstName) { ... }

    @Basic
    public String getLastName() { ... }

    public void setLastName(String lastName) { ... }

    @Basic
    public boolean isCitizen() { ... }

    public void setCitizen(boolean citizen) { ... }

    @OneToMany(fetch = FetchType.LAZY, cascade = CascadeType.ALL, orphanRemoval = true)
    @JoinColumn(name = "ApplicantId")
    public Set<Resume> getRésumés() { ... }

    public void setRésumés(Set<Resume> résumés) { ... }
}
```

```java
@Entity
@Table(name = "Applicant_Resume")
public class Resume {

    private long id;
    private String title;
    private String content;

    @Id
    @Column(name = "ResumeId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ... }

    public void setId(long id) { ... }

    @Basic
    public String getTitle() { ... }

    public void setTitle(String title) { ... }

    @Lob
    public String getContent() { ... }

    public void setContent(String content) { ... }
}
```

> **注**：提供的 OCR 文本包含大量重复和错误，我已根据逻辑流、实体结构和 JPA 理论进行了清理和重构。

```java
@Entity
public class Applicant {
    ...
    @OneToMany(mappedBy = "applicant")
}
```

`javax.persistence.OneToMany` 和 `javax.persistence.ManyToOne` 注解包含许多与 `@OneToOne` 相同的属性。`@OneToMany` 拥有一个可选属性，因为这种概念不适用于诗句的集合（集合始终可以是空的）。只有在双向“一对多”关系中，只有 `@OneToMany` 包含 `mappedBy` 属性，因为只有“多”的一侧需要此信息。`@OneToMany` 也是两个带有 `orphanRemoval` 属性的注解之一，因为这种操作仅在关系的一侧是有意义的。

你可能注意到 `@javax.persistence.JoinColumn` 注解已从原始的 `Applicant` 移动到 `Resume` 中的新属性中。该注解在很大程度上与 `@Column` 注解相似，它指定了连接表的列详细信息。如果键是复合的，你可以使用 `@javax.persistence.JoinColumns` 来组合多个注解。在单向的多对一关系中，它属于 `@ManyToOne` 侧（Applicant）。对于这些关系，它指示了另一个实体表中的哪一列包含“此”主键。然而，在双向“一对多”关系中，它属于 `@OneToMany` 侧。对于这些关系，`@JoinColumn` 指示了“此”实体表中的哪一列包含另一个实体的主键。它替换了该属性的 `@Column` 注解。

与其使用 Resumes 的 Set，你也可以使用 Resumes 的 List 并以某种方式维护它们的顺序。要做到这一点，你可以在 List 属性（即 `@OneToMany` 侧）上使用 `@javax.persistence.OrderColumn` 注解，并指定 `Applicant_Resume` 表中的列名。

# 第 24 章：创建高级映射和自定义数据类型

即 Resumes 应该排序的列名。你也可以指定一个 Resumes 的 Map。在这种情况下，你需要从 `Applicant_Resume` 表中选择某列作为 Map 的键。你可以对 Map 属性使用 `@javax.persistence.MapKey` 注解，这意味着 Map 的键是 Resumes 的 `@Id` 属性。或者，你也可以使用 `@javax.persistence.MapKeyColumn` 来指定 `Applicant_Resume` 表的某个列名（如 Title）作为 Map 的键。

最后一点说明：对于 Map 属性，你可以使用 `@Column`，其 Map 条目（通过 `entrySet()` 返回）和值（通过 `values()` 返回）将根据该列进行排序。

Applicant 和 Resume 实体的最终版本映射到以下 MySQL 架构：

```sql
CREATE TABLE Applicant (
  Id BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
  FirstName VARCHAR(60) NOT NULL,
  LastName VARCHAR(60) NOT NULL,
  Citizen BOOLEAN NOT NULL
) ENGINE = InnoDB;

CREATE TABLE Applicant_Resume (
  ResumeId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
  ApplicantId BIGINT UNSIGNED NOT NULL,
  Title VARCHAR(100) NOT NULL,
  Content TEXT NOT NULL,
  CONSTRAINT Applicant_Resume_FOREIGN KEY (ApplicantId)
  REFERENCES Applicant(ApplicantId) ON DELETE CASCADE
) ENGINE = InnoDB;
```

## 创建多对多关系

多对多关系是一对多和多对一关系的自然扩展。在多对多关系中，关系的双方都可以关联到另一端的多个实体。一个常见的例子是学校和学生之间的关系。一所学校可以有很多学生，一个学生可以上多所学校。因此，School 实体将拥有一个 Students Set、List 或 Map，而 Student 实体将返回一个 Schools Set、List 或 Map。

你可以使用 `@javax.persistence.ManyToMany` 观察多对多关系的一侧或双方。它具有你所熟悉的 `cascade`、`fetch` 和 `mappedBy` 属性。要使用它，你必须在关系的对端属性上指定 `mappedBy`。你只需要在关系的一侧指定 `mappedBy`（即非所有者侧，取决于你如何定义所有权）。

在处理多对多关系（单向或双向）时，JPA 供应商会尝试猜测连接表的名称及其列名。为了你的开发起见，最好记住这些猜测的变量并指定 `@javax.persistence.JoinTable` 注解。你将此注解放置在关系的所有者侧（即你指定 `mappedBy` 的对侧）。除了表名和其他详细信息外，该注解还包含 `joinColumns` 和 `inverseColumns` 属性。

你使用 `joinColumns` 来指定一个或多个 `@JoinColumns`，指示“此”（所有者实体）主键映射到哪一列或哪几列。同样，你使用 `inverseColumns` 来指定一个或多个 `@JoinColumns`，指示另一个（被所有）实体主键映射到哪一列。在之前描述的 School 和 Student 中，映射如下所示的 School 实体：

```java
@ManyToMany(fetch = FetchType.LAZY)
@JoinTable(name = "Student",
           joinColumns = { @JoinColumn(name = "SchoolId") },
           inverseColumns = { @JoinColumn(name = "StudentId") })
public List<Student> getStudents() { ... }

public void setStudents(List<Student> students) { ... }
```

## 处理其他常见情况

存在几种简单且自身不需要单独条目的常见情况。不要将其解释为它们没用；对于你的需求，其中某些可能是最有用的。这些主题，如实体版本控制、定义通用实体父类以及向实体中添加集合和 Map，都在下文中进行了介绍。

### 使用时间戳进行实体版本控制

实体版本化的简单方法是使用 `@Version` 注解。当你使用 `@Version` 时，JPA 供应商会使用乐观锁防止多个线程同时更新同一条记录。如果一个线程尝试更新已被另一个线程更改的记录，JPA 供应商将抛出 `OptimisticLockException`。

例如，更新语句如下：

```sql
UPDATE MyEntity SET ..., Version = Version + 1 
WHERE Id = ? AND Version = ?
```

如果此语句失败，意味着另一个进程更新了该记录。你可以通过重试操作或回滚事务来处理。大多数情况下，乐观锁足够了。

### 理解乐观锁与悲观锁

乐观锁允许两个线程同时读取同一个实体，但只允许一个更新它。这是通过 `@Version` 属性实现的。然而，如果你喜欢在数据库级别锁定行，可以通过指定 `@org.springframework.data.jpa.Lock(LockMode.PESSIMISTIC_READ)` 来使用悲观锁。在使用悲观锁时，可能会发生两种类型的失败。第一是锁定失败导致事务回滚。这种错误对于事务是致命的，并会导致 `javax.persistence.PessimisticLockException`。然而，锁定可能只导致单个语句的回滚。在这种情况下，失败是瞬时的，并产生 `javax.persistence.LockTimeoutException`。这取决于你如何通过重试语句来处理超时。

### 定义具有通用属性的抽象实体

在创建实体后，你可能会注意到它们至少包含几个重复的属性。例如，你会发现你所有的实体都有 ID、创建日期、修改日期和版本属性。与其在每次创建实体时重新定义属性，不如创建一个映射超类（mapped superclass）来一次性定义它们。

映射超类非常像实体。它不包含 `@Table` 注解，且 `javax.persistence.MappedSuperclass` 注解替换了 `@Entity` 注解，但在其他方面，你可以像在普通实体中一样映射其中的任何属性。映射超类中的属性映射方式始终与它继承的实体类相同。在层级结构中，你也不受限于单个映射超类。你可以定义任意数量的映射子类，实体会继承其作为祖先的所有映射子类的属性。

映射超类还可以通过重写访问器方法并重新定义 `@Column` 注解来覆盖其继承的属性列映射。然而，如果你使用字段访问而不是方法访问，这种方法不起作用，因此在这些情况下，你必须在类上使用 `@Override`，在 name 属性中指定属性名称，并提供新的 `@Column` 定义。你无法覆盖 `@Basic`、`@Lob`、`@Temporal`、`@Enumerated`、`@Convert` 以及其他 JPA 注解。如果映射超类定义了 `@Transient` 属性，其子类无法覆盖该属性以变为非 Transient。

同样，映射超类（mapped superclass）或实体不能重写其祖类中的非 `@Transient` 方法并将其标记为 `@Transient`。

Advanced-Mappings 项目中的映射超类 `BaseEntity` 定义了所有扩展实体都拥有的 `id` 属性。`VersionedEntity` 是一个映射超类，它继承自 `BaseEntity` 以为乐观锁指定一个 `@Version` 属性。最后，映射超类 `AuditedEntity` 继承自 `VersionedEntity` 并指定了创建和修改属性。

```java
@MappedSuperclass
public abstract class BaseEntity {
```



# 实体继承与映射超类

```java
private long id;

@Id
@GeneratedValue(strategy = GenerationType.IDENTITY)
public long getId() { ... }

public void setId(long id) { ... }
```

```java
@MappedSuperclass
public abstract class VersionedEntity extends BaseEntity {

    private long version;

    @Column(name = "Revision")
    public long getVersion() { ... }

    public void setVersion(long version) { ... }
}
```

```java
@MappedSuperclass
public abstract class AuditedEntity extends VersionedEntity {

    private Instant dateCreated;
    private Instant dateModified;

    @Convert(converter = InstantConverter.class)
    public Instant getDateCreated() { ... }

    public void setDateCreated(Instant dateCreated) { ... }

    @Convert(converter = InstantConverter.class)
    public Instant getDateModified() { ... }

    public void setDateModified(Instant dateModified) { ... }
}
```

现在你可以创建许多继承自这些映射超类的实体了。`NewsArticle` 实体继承自 `AuditedEntity` 并继承了其所有父类的属性。它的 SQL 架构反映了重写的 `id` 列名。

```java
@Entity
@AttributeOverride(name = "id", column = @Column(name = "ArticleId"))
public class NewsArticle extends AuditedEntity {

    private String title;
    private String content;

    @Basic
    public String getTitle() { ... }
    public void setTitle(String title) { ... }

    @Basic
    public String getContent() { ... }
    public void setContent(String content) { ... }
}
```

```sql
CREATE TABLE NewsArticle (
    ArticleId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    Revision BIGINT UNSIGNED NOT NULL,
    DateCreated TIMESTAMP(6) NULL,
    DateModified TIMESTAMP(6) NULL,
    Title VARCHAR(100) NOT NULL,
    Content TEXT NOT NULL,
    ENGINE = InnoDB
);
```

与 `@Entity` 类一样，`@MappedSuperclasses` 必须在持久化单元（persistence unit）中注册为托管类。你必须在持久化单元配置的 `<class>` 或 `<jar-file>` 元素中指定它们，或者在配置中禁用 `<exclude-unlisted-classes>`，或者将它们包含在 Spring 的 `LocalContainerEntityManagerFactoryBean` 发现的扫描类中。通过在 `com.wrox.site.entities` 包中使用 `BaseEntity`、`StandardEntity` 和 `AuditedEntity`，它们会被自动发现并添加到持久化单元中。

# 映射基本和嵌入集合

到为止，你已经创建了具有基本类型属性、嵌入类型属性以及其他实体集合属性的实体。然而，有时你只需要一个基本类型或嵌入类型的简单集合。例如，一个员工使用多个电话号码和地址。你可以添加两三个号码和两三个地址，为什么要拒绝呢？这并没有违反数据库范式，同时也验证了良好的面向对象设计实践。根据顺序对你是否重要，拥有电话号码和地址的 `List` 或 `Set` 更有意义。在 JPA 中，你可以使用 `@javax.persistence.ElementCollection` 注解来映射一个基本或嵌入类型集合的字段。

`@ElementCollection` 有一个 `targetClass` 属性，该属性在某些情况下可能需要，也可能不需要。它指定了存储在集合中的元素类型。如果你使用未经过处理的集合（实际上你真的不应该这样做，因为它们是不安全的），你必须指定 `targetClass` 属性。然而，只要你使用泛型（如 `List<String>` 或 `Set<Address>`），JPA 提供程序就可以自动发现元素类型（`String`、`Address`），你不需要指定 `targetClass` 属性。`fetch` 属性指示集合值是从数据库中尽早地还是懒性地检索的，默认值为 `FetchType.LAZY`。

你现在可能对之前描述的关于嵌入类型的限制感兴趣：它们必须存在于包含它们的实体所在的表中。嗯，这只是故事的一部分。

如果它们是集合属性的一部分，它们可能存在于单独表中。在这种情况下，集合默认存储在一个表中，表名等于包含它的实体的名称加上下划线，然后是属性名。根据类型和属性名对列名也做出了某些假设。以 `Employee` 实体为例。

```java
@Entity
public class Employee {
    private long id;
    private String firstName;
    private String lastName;
    private List<String> phoneNumbers = new ArrayList<>();
    private Set<Address> addresses = new HashSet<>();

    @Id
    @Column(name = "EmployeeId", strategy = GenerationType.IDENTITY)
    public long getId() { ... }
    public void setId(long id) { ... }

    @Basic
    public String getFirstName() { ... }
    public void setFirstName(String firstName) { ... }

    @Basic
    public String getLastName() { ... }
    public void setLastName(String lastName) { ... }

    @ElementCollection(fetch = FetchType.EAGER)
    public List<String> getPhoneNumbers() { ... }
    public void setPhoneNumbers(List<String> phoneNumbers) { ... }

    @ElementCollection(fetch = FetchType.LAZY)
    public Set<Address> getAddresses() { ... }
    public void setAddresses(Set<Address> addresses) { ... }
}
```

# 处理其他常见情况

> **注意**：除了嵌入类型和标准基本类型外，你还可以在 Collection 属性中存储需要转换的类型。只需像处理其他基本属性一样，在 Collection 属性上标记 `@Convert` 即可。

## 持久化键值对的 Map

尽管其名称暗示它仅适用于 Collection 属性，但 `@ElementCollection` 也可以标记 Map 以进行持久化。Map 属性始终将键和值存储在同一张表中，这与 Collection 属性的默认情况相同，你也可以使用 `@CollectionTable` 对其进行自定义。你使用 `@Column` 来指定存储 Map 值的列名，并使用 `@javax.persistence.MapKeyColumn` 来指定存储 Map 键的列名。Map 属性也应该使用泛型，如果由于某种原因你无法使用泛型，请使用 `@ElementCollection` 的属性来指定值类，并使用 `@javax.persistence.MapKeyClass` 来指定键类。

键和值可以是任何基本类型，包括枚举类型和时间类型，以及任何需要转换的类型。对于 Collection 属性，你不需要对键或值为嵌入类型的 Map 属性标指定 `@Embedded` 注解。枚举类型使用与基本属性相同的语义，你可以使用用于 Map 值的 `@Enumerated` 注解和用于键的 `@javax.persistence.MapKeyEnumerated` 注解来覆盖这些语义。同样，你可以使用通常用于值的 `@Temporal` 和用于键的 `@javax.persistence.MapKeyTemporal` 来自定义时间类型的语义。

使用 Map 属性是作为自定义字段存储在编译时未知的属性的实体补充属性的极佳方法。这通过以下新的 Employee 属性及其映射的表展示了这一点。

```java
@Entity
public class Employee {
    private Map<String, String> extraProperties = new HashMap<>();
    ...

    @ElementCollection(fetch = FetchType.EAGER)
    @CollectionTable(name = "Employee_Property", joinColumns = {
        @JoinColumn(name = "Employee", referencedColumnName = "EmployeeId")
    })
    @Column(name = "Value")
    @MapKeyColumn(name = "KeyName")
    public Map<String, String> getExtraProperties() { ... }
    public void setExtraProperties(Map<String, String> extraProperties) { ... }
}
```

```sql
CREATE TABLE Employee_Property (
    Employee BIGINT UNSIGNED NOT NULL,
    KeyName VARCHAR(100) NOT NULL,
    Value VARCHAR(255) Employee NOT NULL,
    CONSTRAINT Employee_Property FOREIGN KEY (Employee)
    REFERENCES Employee(EmployeeId) ON DELETE CASCADE
) ENGINE = InnoDB;
```

## 将实体存储在多张表中

虽然这是一个不太可能且不常见的场景，但你仍然可以将实体持久化到多张表中。不要将其与 Collection 或 Map 属性存储在单独表中的混淆——后者是良好规范化支持的预期做法。相反，这种场景实际上通过将实体的基本属性存储在单独的表中破坏了规范化。在一个荒谬的例子中，Employee 的名字必须存储在表 `Employee` 中，而他的姓存储在表 `Employee2` 中。这通常是遗留数据库的症状（为了适应对象关系映射而进行了改造），或者是实体超过了底层数据库供应商允许单个表的列数。

默认情况下，实体的所有非 Collection、非 Map 属性都假设存在于主表中。这在 `@Table` 中指定；如果没有 `@Table`，则使用与实体同名的表。如果实体的某些属性存在于次要表中，你应该使用 `@javax.persistence.SecondaryTable` 标记它，以指定表的名称和（可选的）其他细节。如果实体有多个次要表，可以使用多个 `@javax.persistence.SecondaryTable` 注解。然后，在整个实体中，每个属性必须使用 `@Column` 注解以指示它属于哪张表。`@Id` 属性始终存在于主表中。

假设次要表有一个与主表主键列同名同类型的列，且该列应该是次要表的主键。你可以在 `@SecondaryTable` 注解中自定义此列的细节。

虽然在 Advanced-Mappings 项目中没有演示将实体映射到多张表，但在这种场景下，Employee 实体可能看起来像这样：

```java
@Entity
@Table(name = "Employee")
@SecondaryTable(name = "Employee2", pkJoinColumnColumns = {
    @PrimaryKeyJoinColumn(name = "Employee",
                          referencedColumnName = "EmployeeId")
})
public class Employee {

    @Id
    @Column(name = "EmployeeId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ... }
    public void setId(long id) { ... }

    @Basic
    @Column(name = "FirstName", table = "Employee")
    public String getFirstName() { ... }
    public void setFirstName(String firstName) { ... }

    @Basic
    @Column(name = "LastName", table = "Employee2")
    public String getLastName() { ... }
    public void setLastName(String lastName) { ... }
}
```

## 创建程序化触发器

在很大程度上，你过去可能使用过的关系型触发器应该作为业务逻辑存在于你的服务中。这种从数据库中移除逻辑的做法是将应用程序从其存储机制中完全抽象出来的最后一步，并允许你根据需要轻松切换存储机制。同样，它强化了将应用程序视为数据库的观点。

### 在 CRUD 操作之前和之后

你可以使用触发器在实体持久化、更新或删除之前或之后执行操作。可用触发如下：

- `@PrePersist`: 在实体持久化之前调用。
- `@PostPersist`: 在实体持久化后立即调用。
- `@PreUpdate`: 在实体更新之前调用。
- `@PostUpdate`: 在实体更新后立即调用。
- `@PreRemove`: 在实体移除之前调用。
- `@PostRemove`: 在实体移除后立即调用。
- `@PreLoad`: 在实体从数据库加载之前调用。
- `@PostLoad`: 在实体从数据库加载后调用。

在很大程度上，你过去可能使用过的关系型触发器应该作为业务逻辑存在于你的服务中。这种从数据库中移除逻辑的做法是将应用程序从其存储机制中完全抽象出来的最后一步，并允许你根据需要轻松切换存储机制。同样，它强化了将应用程序视为数据库的观点。

触发器方法可以是多个事件的触发器（例如，它可以同时被标记为 `@PrePersist` 和 `@PreUpdate`），但一个实体对于特定事件的注解方法不能超过一个。这包括继承的触发器方法，这意味着例如实体中的 `@PostRemove` 将禁用它继承自映射父类的任何 `@PostRemove` 方法。然而，它并不会阻止该方法被其他标记的事件（如 `@PostUpdate`）调用。

触发器方法必须返回 `void` 且没有参数。它们可以命名为任何名称并可以是 `public`、`protected`、包级，但不能是静态的。为了防止异常行为，它们不应该调用 `EntityManager` 或 `Query` 方法或访问其他实体。如果触发器方法抛出异常，事务将回滚。

你创建的 `Person` 实体演示了使用所有不同的触发器方法来记录实体的生命周期。

```java
@Entity
public class Person {
    private static final Logger log = LogManager.getLogger();

    @PostLoad
    void readTrigger() {
        log.debug("Person entity read.");
    }

    @PrePersist
    void beforeInsertTrigger() {
        log.debug("Person entity about to be inserted.");
    }

    @PostPersist
    void afterInsertTrigger() {
        log.debug("Person entity inserted into database.");
    }

    @PreUpdate
    void beforeUpdateTrigger() {
        log.debug("Person entity just updated by call to mutator method.");
    }
}
```



```java
@PostUpdate
void afterUpdateTrigger() {
    log.debug("Person entity just updated in the database.");
}
```

```java
@PreRemove
void beforeDeleteTrigger() {
    log.debug("Person entity about to be deleted.");
}
```

```java
@PostRemove
void afterDeleteTrigger() {
    log.debug("Person entity about deleted from database.");
}
```

# 使用实体监听器

实体监听器与你刚刚阅读的触发方法密切相关。实体监听器是一种在实体类之外定义触发方法的构造构体。这些方法被称为外部触发方法或外部生命周期事件处理器，与你刚刚学到的作为实体类或其子类一部分的内部触发方法相反。外部触发方法允许你将此逻辑与实体类分离。实体监听器必须具有公共的无参构造函数，并可以定义之前描述的任何或所有触发方法。然而，有几点不同：

- 实体监听器定义的触发方法必须有一个参数：引起生命周期事件的实体。你可以让参数的类型尽可能模糊（一个映射超类或仅 `Object`），也可以非常具体（你想要使用的实体类型）。
- 实体监听器像内部触发方法一样继承自映射超类，但它们不会重写继承的实体监听器。这意味着你可以让针对同一实体的特定生命周期事件有多个触发方法执行。

在执行触发方法时，提供程序首先调用所有外部触发方法，然后调用所有内部触发方法。实体监听器中的外部触发方法从映射超类祖族的最高点开始执行，并在实际实体类处完成。你还可以定义在所有其他监听器之前执行的默认实体监听器。这些实体监听器适用于应用程序任何地方的所有实体，你只能在映射文件（如 `orm.xml`）中定义默认实体监听器。

编写实体监听器就像创建一个类并向其添加触发方法一样简单。该类不需要实现任何接口或扩展任何父类。（不过，如果对你有所帮助，它完全可以实现或扩展其他类型）。创建实体监听器后，你必须使用 `@javax.persistence.EntityListeners` 注解将其附加到实体上。你可以将此注解放在实体类或映射超类上，以便将监听器或多个监听器附加到该实体类或映射超类上，例如：

```java
@EntityListeners(Listener1.class)
@MappedSuperclass
public abstract class AbstractEntity {
}
@EntityListeners({Listener2.class, Listener3.class})
@Entity
public class ConcreteEntity extends AbstractEntity {
}
```

如果你创建一个扩展了映射超类的实体，但你不想继承映射超类的实体监听器，可以使用 `@javax.persistence.ExcludeSuperClassListeners` 注解该实体。你也可以在映射超类上注解 `@ExcludeSuperClassListeners`，以停止其及其子类对其超类监听器的继承。同样，你可以对实体或映射超类注解 `@javax.persistence.ExcludedDefaultListeners`，以排除其及其子类的所有默认监听器。

# 完善客户支持应用程序

通过你从这一章中学习到的这些工具，你可以对你在本书中一直在编写的客户支持系统进行许多改进。首先，你可以停止使用 `Ticket` 作为 `TicketEntity` 的 DTO，完全移除 `TicketEntity`，并开始直接使用 `Ticket` 作为实体。使用本章稍早创建的 `InstantConverter` 也是可能的。

你还可以定义 `Tickets` 和 `Attachments`（附件）之间的关系，这样在你检索 `Ticket` 实体时，可以自动检索该工单的附件。提到附件，你现在可以使用一个接表以及与 `Attachment` 的关系（类似于 `Ticket` 中的那种方式）为 `TicketComments` 添加附件。你也可以直接将 `UserPrincipal` 关联到 `Ticket` 或 `TicketComment`。最后，你可以确保 `Attachment` 的内容是按懒性加载的，这样在列出工单及其评论上的附件时，就不会丢失可能数百兆字节的数据。可以从 wrox.com 下载站点下载的 `Customer-Support-v18` 项目实现了所有这些功能。

# 映射附件集合

由于你现在对 `Tickets` 和 `TicketComments` 都使用 `Attachments`，`Attachment` 实体不再需要 `ticketId` 属性，相应的表也不再需要 `Ticket` 列。使用 `create.sql` 中的以下连接，将 `Attachments` 与 `Tickets` 和 `TicketComments` 关联起来。

```sql
USE CustomerSupport;

CREATE TABLE Ticket_Attachment (
  SortKey SMALLINT NOT NULL,
  TicketId BIGINT UNSIGNED NOT NULL,
  AttachmentId BIGINT UNSIGNED NOT NULL,
  CONSTRAINT Ticket_Attachment FOREIGN KEY (TicketId)
  REFERENCES Ticket (TicketId) ON DELETE CASCADE,
  CONSTRAINT Ticket_Attachment_Attachment FOREIGN KEY (AttachmentId)
  REFERENCES Attachment (AttachmentId) ON DELETE CASCADE,
  INDEX OrderedAttachments (TicketId, SortKey, AttachmentId)
  ENGINE = InnoDB;
```

```sql
CREATE TABLE Ticket_Comment_Attachment (
  SortKey SMALLINT NOT NULL,
  CommentId BIGINT UNSIGNED NOT NULL,
  CONSTRAINT Ticket_Comment_Attachment_Comment FOREIGN KEY (CommentId)
  REFERENCES Comment (CommentId) ON DELETE CASCADE,
  CONSTRAINT Ticket_Comment_Attachment_Attachment FOREIGN KEY (AttachmentId)
  REFERENCES Attachment (AttachmentId) ON DELETE CASCADE,
  INDEX Comment_OrderedAttachments (CommentId, SortKey, AttachmentId)
  ENGINE = InnoDB;
```

如果你正在运行旧版本的支持应用程序，你可能需要迁移数据。`create.sql` 中注释掉的语句处理了这个问题：

```sql
USE CustomerSupport;

INSERT INTO Ticket_Attachment (SortKey, AttachmentId)
SELECT @rn := @rn + 1, AttachmentId
FROM (SELECT @rn := 0) x
GROUP BY TicketId
WHERE @rn > 0;

DROP TABLE minKeys;
ALTER TABLE Attachment DROP FOREIGN KEY TicketId;
ALTER TABLE Attachment DROP COLUMN TicketId;
```

映射 `Ticket-Attachment` 和 `TicketComment-Attachment` 关系是简单的。首先，`Ticket` 不再有 `getAttachment` 方法来通过名称检索 `Attachment`。单个检索必须使用 ID。以下映射连接了 `Ticket` 和 `Attachment`：

```java
@OneToMany(fetch = FetchType.LAZY, cascade = CascadeType.ALL, orphanRemoval = true)
@JoinTable(name = "TicketAttachment",
    joinColumns = { @JoinColumn(name = "TicketId") },
    inverseJoinColumns = { @JoinColumn(name = "AttachmentId") })
@OrderColumn(name = "SortKey")
@XmlElement(name = "attachment")
@JsonProperty
public List<Attachment> getAttachments() {
    return this.attachments;
}
```

而以下连接了 `TicketComment` 及其附件：

```java
@OneToMany(fetch = FetchType.EAGER, cascade = CascadeType.ALL, orphanRemoval = true)
@JoinTable(name = "TicketAttachment",
    joinColumns = { @JoinColumn(name = "CommentId") },
    inverseJoinColumns = { @JoinColumn(name = "AttachmentId") })
@OrderColumn(name = "SortKey")
@XmlElement(name = "attachment")
@JsonProperty
public List<Attachment> getAttachments() {
    return this.attachments;
}
```

注意，`Ticket` 的附件是懒性加载的，而评论的附件是积极加载的。在列出工单时，我们并不列出它们的附件。没有理由加载不需要的信息。相反，在 `DefaultTicketService` 中，你可以在事务期间通过调用列表的方法告诉 Hibernate 加载单独检索工单的附件。（记得 `getNumberOfAttachments` 调用了 `List<Attachment>` 方法）。

```java
@Override
@Transactional
public Ticket getTicket(long id) {
    Ticket ticket = this.ticketRepository.findById(id);
    ticket.getNumberOfAttachments();
    return ticket;
}
```

然而，这是针对评论的。在查看工单时列出评论时，你也想列出它们的附件。由于 `Attachment` 在这两个实体之间共享，这种关系是单向的。（`Attachment` 没有指向 `Ticket` 或 `Comment` 的 `@ManyToOne` 属性。）

这种变化的好处之一是提高了 `DefaultTicketService` 的简单性。不再需要在 DTO 和实体之间进行转换，消除了大量的代码。你可以在下载的项目查看重构后的服务，以及更新后的控制器和视图。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_757_0.png)

# 使用加载时织入延迟加载简单属性

现在，工单及其评论都可以包含附件，这导致在查看工单时无谓地加载大量数据。如果一个工单有几个 10MB 大的附件，且每条评论也有几个 10MB 大的附件，那么一个工单可能会加载数百 MB 的未使用数据。这将是一个巨大的性能问题。你需要做的是加载附件的内容：

```java
@Lc
@Basic(fetch = FetchType.LAZY)
@XmlSchema(name = "base64Binary")
@JsonProperty
public byte[] getContents() {
    return this.contents;
}
```

然后，在 `DefaultTicketService` 中，你只有在获取单个工单（用于下载）时才加载这些内容：

```java
@Override
@Transactional
public Attachment getAttachment(long id) {
    Attachment attachment = this.attachmentRepository.findOne(id);
    if (attachment != null) {
        attachment.getContents();
    }
    return attachment;
}
```

然而，这并没有那么简单。对于 `Map` 和 `Set` 类型的属性，延迟加载是自动工作的，因为 Hibernate ORM 带有这些接口的代理实现，这些实现只有在 `Map` 或 `Collection` 被某种方式使用时（例如进行计算、迭代等）才会运行加载数据所需的查询。如果你想加载使用 `byte[]` 或 `String` 类型的简单属性，或者 `@OneToOne` 或 `@ManyToMany` 属性，Hibernate 必须对实体的字节码进行插入，以便拦截这些属性。在没有配置的情况下，它无法直接做到。

首先，你必须设置一个能够进行字节码插入的环境。你有三种方法来实现：

- 为 JVM 挂载 Java agent（查看 `java` 命令中的 `-agent` 参数），它使用类转换器来检查并转换由 JVM 中的类加载器加载的所有类。对于应用程序服务器或 Servlet 容器环境来说，这有点太重了，除非你需要一种适用于单个应用程序的方法。
- 使用 Hibernate 的 `org.hibernate.tool.instrument.InstrumentTask` Ant（在你的 Ant 脚本中或通过 Maven 中的 Ant 插件）。该任务会在构建时（即编译之后、部署应用程序之前）修改实体的字节码。其他 O/RM 也提供了在构建时装饰字节码的类似机制。
- 使用加载时字节码织入。你在 `Customer-Support-v18` 项目中可以看到这种方法。

Spring Framework 的加载时织入功能可以通过一个可插拔的 `org.springframework.instrument.class.LoadTimeWeaver` 实现，在类从类文件加载时对其进行转换。回退实现是之前提到的使用 Java agent 的实现，但这并不是真正的最佳。更好的选项是使用一个利用容器提供的可插入 ClassLoader 的织入器。

Glassfish、Jboss、WebLogic 和 Websphere 都提供了 Spring 可以利用的可插入 ClassLoader。在 Tomcat 8.0 之前，你可以告诉 Tomcat 使用一个特殊的 ClassLoader（由 Spring 提供），该类扩展了默认的 Tomcat 类。然而，Tomcat 8.0 已经了一个 Spring 可以自动使用的可插入 ClassLoader。

配置 Spring Framework 的加载时织入只需在 `RootContextConfiguration` 中添加 `@org.springframework.context.annotation.EnableLoadTimeWeaving` 即可。它会自动检测并使用 Tomcat 的可插入 ClassLoader。要让 Hibernate ORM 使用这种加载时织入器，还需要一个额外的 Hibernate 属性。

```java
@EnableLoadTimeWeaving
public class RootContextConfiguration implements
    AsyncConfigurer, SchedulingConfigurator, TransactionManagerConfigurator {

    @Bean
    public LocalContainerEntityManagerFactoryBean entityManagerBean() {
        properties.put("hibernate.ejb.use_class_enhancer", "true");
    }
}
```

你必须考虑的最后一点是实体的 XML 和 JSON 序列化。无论你如何处理这些类（构建时静态处理、使用 agent 或通过加载时织入动态处理），Hibernate 都可以为你的实体添加任意数量未指定的字段和方法。这是因为它们不会干扰你对这些实体的正常使用（用于 XML 序列化），且 JAXB 和 Jackson Data Processor（你用于 JSON 序列化）不知道如何处理这些字段和方法。解决方案是使用 `@XmlAccessorType` 和 `@JsonAutoDetect` 对你想要序列化的属性告诉 JAXB 和 Jackson *默认* 忽略实体属性，并从*不*序列化的属性中移除 `@XmlTransient` 和 `@JsonIgnore`。



```java
@XmlAccessorType(XmlAccessorType.NONE)
@JsonAutoDetect(createVisibility = JsonAutoDetect.Visibility.NONE,
    fieldVisibility = JsonAutoDetect.Visibility.NONE,
    getterVisibility = JsonAutoDetect.Visibility.NONE,
    isGetterVisibility = JsonAutoDetect.Visibility.NONE,
    setterVisibility = JsonAutoDetect.Visibility.NONE)
public class Ticket implements Serializable
```

```java
{
  @XmlElement
  @JsonProperty
  public long getId() { ... }
}
```

```java
@XmlAccessorType(XmlAccessorType.NONE)
@JsonAutoDetect(...)
public class TicketComment implements Serializable
{
  @XmlElement
  @JsonProperty
  public long getId() { ... }
}
```

```java
@XmlAccessorType(XmlAccessorType.NONE)
@JsonAutoDetect(...)
public class Attachment implements Serializable
{
  @XmlElement
  @JsonProperty
  public long getId() { ... }
}
```

在你检查了 Customer Support 应用程序的所有更改后，编译项目，从 IDE 中启动 Tomcat，并在浏览器中访问 `http://localhost:8080/support`。

# 第 25 章 介绍 Spring Security

你每天都会遇到验证（authentication）和授权（authorization）。当你早晨登录计算机网络时，这验证了你的身份并建立了你的身份标识。随后，你在网络上的权限将根据你的身份决定你有权访问哪些系统。如果某个下午因为父母被堵在交通路上，你去学校接侄女，学校会检查你孩子的档案以确保你确实是你所说的人。这就是验证。然后他们会检查你的身份证，如果是的话，就会让你带她离开。如果你输入军人身份，他们会立即检查你的身份证，确保你确实是你所说的人。有时，他们还会进行进一步的检查，例如指纹或视膜扫描，以更安全地验证你的身份。他们可能会询问你“今天的颜色”或“今天的密码”。当他们确认你的验证有效后，他们会检查你是否有权访问正尝试访问的区域。

虽然验证和授权确实是必然且不可分割的，但它们并不是同一个概念。在以后，你必须记住这两者的区别。在本章中，你将探索验证和授权涉及的细微差别和技术。然后你将查看 Spring Security，这是你在本书第四部分也是最后部分使用的一个框架，以便为你的 Web 应用添加安全性。

## 集成验证

尽管验证并不非是你集成到应用程序中的第一个组件，但你会在应用程序中访问受保护的资源。无论你是通过第三方还是直接通过你的应用程序提供的机制进行验证，在你授权他们之前，你的用户必须建立他们的身份。这种情况如何发生是一个非常感兴趣的话题。你可以采取几十种方法来创建验证机制。有些比其他的好，但大多数大相当。使用哪种方法很大程度上取决于你具体的业务和安全需求，而且通常是由用户的愿和技术水平驱动的。

## 匿名验证

匿名验证无疑是存在的最简单的验证形式。你可能在想：“匿名验证如何真的是验证呢？我以为验证是关于验证某人的身份”。这句话可能是正确的，但它完全取决于你对身份的定义。例如，你可能只需要断定访问页面的浏览器与几分钟前访问上一个页面的是同一个。HTTP 会话通过话 ID 实现这一点。因为服务器每次在你访问网站上的页面时都会向你返回相同的会 ID，你可以将这些请求关联为同一个身份。你可能根本不在乎访问者是谁，只想知道它是否是同一个人。这就是匿名验证的一种形式。

更广泛地说，你可以认为匿名验证仅仅是任何其他形式验证的缺失。许多 Web 应用在某种程度上支持匿名验证。例如，Twitter 允许你在不“登录”的情况下查看用户的动态、趋势话题等。这就是匿名验证。然而，如果你想发布推文或关注其他用户，你必须以某种建立你 Twitter ID 的方式进行验证。

许多网站允许你通过匿名验证执行一些基本任务并访问资源，只有当你想要保护受保护的活动或访问受保护的资源时，才需要更高级别的验证。这在整个互联网上的许多论坛上尤其如此，你通常可以阅读任何帖子，但在验证后可以创建新帖子。其他网站不需要验证——你可以用匿名验证做任何事情。虽然罕见，但某些网站不允许你匿名查看或做任何事情。你在整本书中一直工作的客户支持应用程序就是一个不允许匿名验证的例子。

## 密码验证

毫无疑问，当你还是个孩子时，你可能有某种堡垒、俱乐部或树屋，邀请朋友来玩。在进入之前，他们可能会向他们索要“密码”。如果没有授予访问权限的秘密单词或短语，他们就进不去。他们没有向他们索要用户名和密码。那太复杂了。你只想知道他们是否知道“密码”。最早记录的密码使用源于古罗马，罗马军队使用被称为“口号（watchwords）”的密码来验证他们遇到的军人员成员的身份。这很重要，因为军队规模之大，大多数成员并不认识其他成员。区分敌友的唯一方法就是索要密码。如果他们知道密码，就是朋友；如果不是，就是敌人。

这个系统存在的问题之一对你来说可能是显而易见的。罗马敌人最终在一名罗马士兵有机会之前捕获了一名要求索要密码的罗马士兵。该罗马士兵将密码交给了敌人，敌人就可以恶意使用该密码。为了应对这个问题，密码的使用最终演变为密码和对口（counter-passwords）的使用。在第二次世界大战期间，美国第 101 空降师伞兵会大喊“flash（闪电）”作为挑战，地面部队会以“thunder（雷）”作为响应。通过这种方式，伞兵和地面部队建立了他们作为美国人的身份。

这种密码/对口的方法与现代涉及应用程序的方法非常相似，用户在提供验证凭据之前，期望有一个 HTTPS 证书来确认网站的身份。如果用户将凭据交给伪装成目标网站的恶意网站，该网站就可以使用这些凭据造成伤害。双向验证有助于防止攻击，即中间人攻击。

最早记录的计算机密码验证使用发生在 1961 年的麻理工学院（MIT）。迭代时间共享系统（Iterative Time-Sharing System）需要用户密码来访问共享资源。从那时起，保护计算机和网站上的密码一直是一场无完没了的战斗。20 世纪 70 年，在 UNIX 系统上工作的 Robert Morris 提出了存储密码单向哈希（hashes）的想法。

当然，正如你可能知道的，破解密码的硬件和软件不断进步，计算哈希的算法也变得更加先进，以应对图形处理器（GPUs）。利用其能力的特殊软件，黑客每秒可以生成数十亿密码。今天的先进哈希算法（如 BCrypt）被设计得非常缓慢并利用内存，使得基于 GPU 的攻击变得困难或不可能。

## 用户名和密码

不太可能只用密码来保护你的应用程序。单一密码意味着任何想要你的网站的人都有相同的身份。这让让密码变得更加困难——你必须通知知道它的所有人——并让密码不安全。毫无疑问，你已经熟悉分配用户名和密码的替代方法。每个用户都有一个与其他用户共享的唯一用户名和一个与用户名关联的密码。

为了验证并建立他们的身份，用户必须在提示时输入用户名和密码。用户名是用户选择的值，例如名字、昵称或用户希望被称为“句柄（handle）”。其他时候用户名可能是用户的电子邮件地址，然后密码则是系统分配的值，用户对其没有控制权。这在人力资源系统等员工门户中很常见。用户名通常是员工的工号。银行使用客户的账号号码作为他们的用户名。

用户名的起源和意义对用户名密码验证的目的并不重要。通过这种验证类型，你为每个用户建立了一个唯一的身份。用户名作为该身份，而密码验证身份的真实性。用户名密码验证是许多不同验证方法的基础，例如表单验证、操作系统验证等。在你为网站、应用程序和系统进行验证时，你可能大部分时间使用某种形式的用户名密码验证。

## 基础和摘要验证

基础访问验证是一种 HTTP 验证协议，它允许主动的验证请求和验证挑战。当受基础验证保护的资源收到缺少凭据的请求时，它会返回 HTTP 状态码 401 Unauthorized 以及 WWW-Authentication 头，如下所示的响应：

```
HTTP/1.1 401 Not Authorized
Date: Sun, 25 Aug 2013 21:46:47 GMT
WWW-Authentication: realm="Multinational Widget Corp. Customer Support"
```

## 什么是身份验证？

当浏览器接收到此响应时，它会在一个包含 realm 头部中文本的模态窗口中提示用户输入用户名和密码。如果用户取消，浏览器将取消请求。如果用户输入了用户名和密码，浏览器将重新发送相同的请求，但会带上 `Authorization` 头部，该头部包含 `Basic` 单词、一个空格以及由冒号分隔的 Base64 编码的用户名和密码。如果用户名和密码为 "John:green"，浏览器会将 "John:green" 编码并重新发送请求如下：

```
/support HTTP/1.1
Host: www.example.org
Authorization: Basic 8m9objpncmVbg=
```

服务器解码该头部，并在服务端将用户名和密码与凭据数据库进行比较。如果凭据错误，服务器将持续返回 401 Not Authorized 和 `WWW-Authenticate` 头部。假设凭据通过，用户即通过身份验证并返回正常响应。浏览器随后会缓存该身份验证，并在对该资源或资源的每个后续请求中重新发送。通常，此缓存会在一段时间未活动后过期。

基础认证（basic authentication）的优点之一是它不需要登录页面、Cookie 或 HTTP 会话 ID。它还可以在没有 401 挑战响应、且不需要用户手动操作 `Authorization` 头部的情况下运行。用户可以将凭据直接嵌入 URL 中，其浏览器或命令行客户端（如 Wget 或 curl）会自动将这些凭据转换为 `Authorization` 头部。URL 看起来可能像：`http://John:green@example.org/support`。

当然，这种协议在许多方面都极其脆弱。首先，用户名和密码是以明文发送的（Base64 仅是一种编码算法；它没有采用任何哈希或或加密）。网络上的任何恶意嗅探包都可以观察并捕获传输过程中的凭据。对方随后可以使用这些凭据进行非法目的。即使对方对凭据本身不感兴趣，也可以简单地重放请求并访问受保护的资源。这些问题严重，但如果请求和响应通过 HTTPS 进行，这些就不存在了。HTTPS保护凭据免受窃听（中间人攻击）并防止重放攻击。然而，还有第三个问题：密码通常以明文存储在服务端，这是另一个漏洞。大多数现代 Web 服务器都提供了使用单向哈希存储密码的机制，例如。

在 HTTPS 可选或不需要的情况下，服务器和客户端仍然可以使用与摘要认证（digest authentication）类似的协议来实现某种程度的安全性。该协议使用 MD5 校验和算法计算一系列单向哈希，以便密码不会通过网络传输。此外，两个随机数（一个服务器随机数和一个客户端随机数）和一个序列请求次数可以防止重放攻击，使黑客无法简单地重放请求并查看受保护的资源。对于没有凭据的响应，服务器返回 401 Unauthorized 以及 `WWW-Authenticate: Digest` 头部，包括 `realm` 参数和其他头部参数：

- `algorithm` 指明算法，此处为 "MD5"，意味着第一个哈希是使用 MD5 计算的 (username:realm:password)。另一个值是 "MD5-sess"，意味着第一个哈希是使用 MD5 计算的 (MD5 (username:realm:password) : nonce)。

- `qop` 表示保护质量，可以是 "auth（默认值）" 或 "auth-int"，也可以是 "auth,auth-int"（以防客户端选择使用）。如果客户端选择 "auth"，第二个哈希是使用 MDS(requestMethod:requestUri) 计算的。如果客户端选择 "auth-int"，第二个哈希是使用 MDS(requestMethod:requestBody) 计算的。"auth-int" 仅适用于包含正体的请求（POST、PUT 等），服务器通常要求 "auth,auth-int"，而客户端对包含正体的请求响应 "auth-int"，对不包含正体的请求响应 "auth"。

- `opaque` 是一个随机字符串数据参数。它是十六进制或 Base64 编码的。客户端必须原样返回 opaque 值。它没有特殊含义，也不提供指令；它只是一个完整性检查。

- `nonce` 包含服务器随机数。它必须是随机的，且对于任何两个 401 Not Authorized 响应都不会重复。客户端必须原样返回 nonce 值。服务器只在客户端验证之前发送 401 Not Authorized 响应，客户端的每个请求都会发送一个服务器随机数——即最近的随机数。

> 注意 A 是一个用于防止重放攻击的特殊令牌。

程序员，你不需要担心这些细节。根据服务器环境，你只需要声明某个特定资源受基础认证（basic authentication）或摘要认证（digest authentication）的保护即可。然而，由于最近对 MD5 的攻击使其在很大程度上变得过时，除了 HTTPS 的安全保障外，摘要认证通常不是你不应该依赖的任何东西。即使在 HTTPS 上，在可能的情况下你也应该使用摘要认证而非基础认证。请注意，尽管现代浏览器支持摘要认证，但流行的浏览器中没有一个支持 auth-int 质量的保护。

## 表单认证 (Form Authentication)

HTTP 认证可能是你最熟悉的协议。它的实现非常简单：当客户端尝试访问受保护的资源时，服务器将客户端重定向到 302 Found、303 See Other 或 307 Temporary Redirect，跳转到一个包含用户名和密码字段的表单页面。用户在表单中输入用户名和密码，就像在基础或摘要认证的模态窗口中操作一样。如果凭据错误，服务器将继续将用户重定向回登录表单并告知登录尝试失败。如果凭据正确，服务器将用户送回其原始目的地（或者如果服务器行为不规范，则送回应用程序主页）。这种认证机制没有什么特别或需要强调的，你可能每天都在使用它。和基础认证一样，凭据是以明文通过网络发送的，因此你应该尽可能利用 HTTPS 来保护这些凭据。

## Microsoft Windows 认证 (Microsoft Windows Authentication)

与基础、摘要和表单认证一样，Windows 认证也要求用户提供用户名和密码。事实上，这些凭据可以使用基础认证或表单认证提交。在这些情况下，主要的区别在于凭据是在 Windows 域控制器处检查，而不是内部凭据数据库。然而，这些情况主要是基础或表单认证。集成 Windows 认证（IWA）使用 SPNE、Kerberos 或 NTLMSP 来捕捉客户端在其机器上的 Windows 凭据，并自动安全地传递给服务器，而无需在请求中包含密码。当这种机制生效时，过程对用户是透明的。他们永远不会被提示提供凭据的模态窗口或登录表单，因为协议会自动处理凭据。

然而，这在某些情况下才是可能的。通常，用户必须使用 Microsoft Internet Explorer。Mozilla Firefox 支持 NTLMSP，但只有当用户访问 `about:config` 并在 `network.ntlm-auth.trusted-proxy` 中配置站点时支持（该设置包含一个逗号分隔的可能请求 IWA 的信任站点列表）。大多数用户在技术上并不足够精通此类更改，因此 Firefox 通常不是一个选择。Google Chrome 支持 IWA，但其安全设置比 Internet Explorer 定义的更严格。站点必须在本地局域网（Local Intranet）区域中通过验证，Chrome 才会允许 IWA。

当然，这假设所有用户都从 Microsoft Windows 机器连接，这在今天比 10 年前要少得多。如今许多用户使用的是 Mac OS 或 Linux 机器，无法提供 Windows 域凭据。由于这个原因，集成 Windows 认证通常仅部署在用户工作于统一环境的企业环境内部资源中。公共网站很少使用 IWA 进行用户认证。此外，当你无法保证所有用户环境都是运行支持浏览器的 Windows 机器时，你必须提供备份方案，例如由 Windows 域控制器支持的基础或表单认证。

> 简单且安全的 GSSAPI 协商机制 (SPNEGO)、Kerberos 和 NT LAN Manager 安全支持程序 (NTLMSSP) 是关于协议协商和挑战-响应认证的不同且相关的协议。在书中你不会使用它们，因此进一步定义它们超出了范围。

## 客户端证书 (Client Certificates)

客户端证书认证是识别用户的另一种方法。它不涉及任何用户名或密码，使其安全性显著提高。事实上，客户端证书认证是最安全的认证协议之一。作为 SSL 协议的一部分，客户端证书认证需要 HTTPS。当你通过 HTTPS 连接到服务器时，服务器本身会出示受信任的证书颁发机构签名的公钥，并使用其私钥对你的浏览器的通信进行签名。客户端证书本质上是此相反。



在“注册”期间（用户通常使用用户名和密码的过程中），服务器告诉用户的浏览器生成一对公钥/私钥。浏览器将私钥安全地存储在用户的机器上，并将私钥传输到服务器。从那时起，浏览器向服务器提交公钥以用于身份验证，并使用私钥对与服务器的通信进行签名。使用这种协议的缺点是用户无法使用新的或不同的计算机来对你的站点进行认证。他们必须备份自己的公钥/私钥，并将其恢复到想要使用的其他计算机上。然而，这样做的好处是增加了安全性：用户的凭据不会轻易被破解。黑客必须控制用户的计算机才能使用其凭据。

许多需要安全的高度敏感应用程序都使用客户端证书认证。它的优点极具吸引力，但它需要比今天大多数 Internet 用户拥有的更高的技术水平，这使其成为最少使用的 Web 认证协议之一。

## 智能卡与生物识别

用户名-密码认证的两种替代方案是智能卡和生物识别。智能卡是一种特殊的集成电路，用户可以随身带在口袋里并在需要认证时插入计算机。就像政府颁发的身份卡或磁性员工安全通行证一样，智能卡包含断明用户身份的信息。出示此智能卡用于验证持有者即为该用户。Microsoft Internet Explorer、Mozilla Firefox 和 Google Chrome 都支持所有智能卡，尽管配置复杂程度各不相同。

生物识别涉及从用户获取指纹、声纹、虹膜扫描、DNA 或其他生物身份，并要求用户在每次认证时重新出示这种身份。大多数浏览器通过某种方式使用与所用生物识别硬件集成的供应商插件支持生物识别。生物识别是一个极其复杂的主题，远超本书的范围。

智能卡和生物识别都是 Web 认证的可能解决方案，它们更通常用于认证进入建筑的人员或登录公司及政府计算机系统。

## 基于声明的认证

到为止你已经学习了可以在应用程序中直接实现的各种认证机制。基于声明的认证是你无需实现的机制。在基于声明的认证中，你的应用程序信任第三方应用程序代表你进行认证。你既不知道也不关心第三方应用程序如何执行认证过程。如果你曾经用过 Facebook 为其他站点进行认证，你就使用过基于声明的认证。通常在基于声明的认证中，当用户尝试访问应用程序中受保护的资源时，你只需将他们重定向到第三方。认证成功后，他们带着一个或多个断言其身份的声明返回你的站点。这些声明由第三方应用程序发布，可以通过向应用程序发送回调请求来轻松进行验证，如图 25-1 所示。

在某些情况下，你的系统直接与第三方系统通信，以用凭据交换声明（claims）。两个常见的例子是 Microsoft Windows 的活动目录（Active Directory）域验证和轻级目录访问协议（LDAP）。直接基于声明的验证过程如图 25-2 所示。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_774_0.png)

图 25-2

这似乎是一个更简单且更理想的方法，但并不总是最佳选择（或可用选项）。用户喜欢在为特定的安全服务使用凭据时，访问同一个登录页面所带来的安全感。考虑一下：如果一个网站要求你使用 Google 账户进行身份验证，你倾向于被重定向到 Google 网站登录，还是倾向于将凭据交给那个潜在不可信的网站？你对问题的回答将清楚为什么这种方法很受欢迎。直接验证通常保留给高度信任的应用程序，并且通常限于控制 Facebook 的同一组织或公司内部。

# 多因素身份验证

到目前为止的所有机制仅涉及一个身份验证因素。使用用户名-密码验证及其衍生物，提供用户名和密码就是用户需要做的一切。对于证书验证，用户只需出示正确的证书即可。生物识别、智能卡和基于声明的验证也是如此。在所有这些机制中，唯一的一步就是成功验证用户。今天，许多 Web 应用需要或可以要求多因素身份验证（MFA）。Gmail、Twitter、Facebook、Amazon.com、WordPress 等许多平台为用户提供了启用多因素身份验证的选项。

多因素身份验证要求用户执行两个或更多步骤来断言其身份。这可能包括提供证书以及用户名和密码。更常见的是，在提交用户名和密码后，许多网站会向用户的已知手机发送短信，其中包含用户在继续之前必须输入 Web 应用程序的特殊代码。

更安全的解决方案包括设备，如带有简单 LCD 屏幕的钥匙令牌（dongles）或显示安全六到九位代码的手机应用程序，代码使用随机生成器每 30 到 60 秒旋转一次。这些令牌包含高精度的时钟和出厂安装的随机种子，使得知道种子的服务器能够预测任何时刻显示的数字。手机应用程序与服务器通信，以协调显示正确的令牌。当用户输入普通凭据（用户名和密码、证书等）时，他们会被要求输入其令牌或手机应用程序上显示的数字。

尽管多因素身份验证的概念很简单，但它的安全优势是显著的，并且到目前为止应该是显而易见的。攻击者极无可能同时提供凭据并收到发送给用户的短信，或其令牌或手机应用程序上的数字。所有的示例都只包含了两个身份验证因素。在第三或第四个因素的情况下，安全级别会进一步提高。由于这些原因，多因素身份验证变得越来越流行，你可以预计这种趋势将持续。

# 理解授权

在用户通过身份验证（通过这些方法之一或其他方法）之后，你就可以检查他们在系统中执行操作的权限。最简单的系统通常有两种不同类型的用户：低权限用户和管理员。这两种访问级别是不同类型的授权。被授权管理应用程序的用户可以看到菜单项，并执行比未授权管理应用程序的用户更多的任务。然而，授权系统并不要求访问级别创建某种类型的层次结构，即每一层都比下一层强大。更典型的应用程序需要许多不同的授权，其中某些可能具有平等的“权力”，但适用于不同的任务。

一个很好的例子是论坛系统。考虑一个拥有两个不同论坛的网站：产品论坛和一个艺术论坛。用户 A 可能被授权修改产品论坛中的主题，而用户 B 被授权修改艺术论坛中的主题。两名用户作为管理员具有平等的“权力”，但他们被授权修改不同的论坛。

同样，在一个非常大的应用程序中，你可能会有不同的类似于管理员的授权。例如，某些员工可以管理用户，而另一些人管理产品列表，另一些人查看新闻文章。所有这些员工在各自的领域具有相同的“权力”，但授权不同，以至于他们无法管理对方的系统。

# 使用原则和标识

建立用户授权的第一步是以某种标准格式表示该用户。尽管你可以以任何你喜欢的格式创建它，但在 Java 中，这个概念是实现 `java.security.Principal`。至少，一个 `Principal` 应该持有用户的身份。记住，身份是你进行验证的对象。你确认用户确实是她所声称的身份，因此该身份应该存储在 `Principal` 中。身份可以是一个用户名，也可以是许多其他信息，例如法定姓名、出生日期、地址和电话号码。你的系统中的任何代码都可以通过上下文中 `Principal` 的存在知道该身份已通过验证。那么 `Principal` 还有什么用处呢？

除了存储身份之外，`Principal` 还可以存储有关用户被授权执行的操作的信息。有了这些信息，应用程序中的任何代码都可以访问安全上下文，获取当前的 `Principal`，并判断用户是否被授权执行其尝试的操作。你有许多方法来表示这些信息；你接下来将学习一些标准技术。更重要的是，你应该使权限成为不可变的常量对象，例如枚举（enums）或内部字符串（intern Strings）。否则，具有许多授权的 `Principal` 可能会占用大量内存，这对性能是不利的的。

# 角色、组、活动和权限

选择表示授权权限的方法在很大程度上取决于个人喜好，但大多数方法都有优缺点。无论你如何处理授权，本质上都归于：你需要确定用户是否有权限执行他请求的操作。从表面上看，这听起来很简单。这是一项应该经过深思考和规划的任务，因为一旦在大型应用程序中选择了某条路，很难退出。

最常见且为人知的方法之一是将所有用户分配给角色。例如，在论坛系统中，你可以创建发布者（Poster）、管理员（Moderator）和管理员（Administrator）角色。发布者可以发布消息和回复；管理员可以执行这些操作并删除消息和回复；管理员可以在所有操作之外，还可以删除和禁用用户以及管理管理员。这种方法的优点应该是显而易见的：通过简单的单选按钮，你可以指示用户是发布者、管理员还是管理员，使得权限管理变得简单。然而，使用这种方法，你得到的代码看起来如下：

```
public void deleteMessage(long id) {
    if (security.userInRole("moderator")) {
    }
}
public void deleteReply(long id) {
    if (security.userInRole("moderator")) {
    }
}
```

当你决定对消息和回复设置不同的管理员时会发生什么？你必须修改、重新编译、重新测试并重新部署你的应用程序。规划这种变化实际上只需要让权限尽可能细粒。处理这种问题的最佳方法是

思考一下你的用户将执行哪些活动。在论坛示例中，这些是你可能期望看到的活动：

- 创建帖子
- 创建回复
- 编辑你的帖子
- 编辑你的回复
- 删除你的帖子
- 删除你的回复
- 删除他人的帖子
- 删除他人的回复
- 临时封禁用户
- 永久封禁用户
- 删除用户
- 分配用户权限

有了这组活动后，检查用户的授权情况与之前的示例没有太大区别：

```
public void deleteMessage(long id)
{
    if (security.userHasActivity("DELETE_OTHER_MESSAGE") ||
        isOwnMessage(id) && security.userHasActivity("DELETE_OWN_MESSAGE"))
    {
    }
}

public void deleteReply(long id)
{
    if (security.userHasActivity("DELETE_OTHER_REPLY") ||
        isOwnReply(id) && security.userHasActivity("DELETE_OWN_REPLY"))
    {
    ...}
}
```

也许确定你需要的哪些活动最简单的方法就是直接查看你服务中的方法。很可能每个方法对应一个活动。方法名通常是其执行操作的指示，例如在上面的代码中，你可能需要两个活动。在这种情况下，删除自己的消息与删除另一个用户的消息是不同的活动。

虽然这种细粒度减少了应用程序重新编译的概率，但也增加了管理用户权限所需的精力。在编辑用户时，你必须从许多权限的列表中选择一个或多个权限。在一个拥有数百种活动的特大型系统中，这个列表对于每个用户来说很快就会变得难以管理。这并非绝对必要，但你可以采用用户组的概念，组中的用户继承执行该组可以执行的所有活动的能力。你只需通过更改用户所属的组，就可以轻松更改许多用户执行的活动。如果你发现某个特定用户或用户需要不同的权限，只需将他们移动到不同的组即可。这与角色的概念几乎相同，区别在于组可以在运行时动态创建，而不需要更改代码。

> 注意：好的。角色？权限？组？它们之间真正的区别是什么？谁决定这些称呼？在本书的术语中，只需区分不同的安全约定即可。你可以在内部将它们命名为任何你。命名角色还是组并不重要，重要的是你如何使用它们。

定义组的一种方法是创建主体（Principals）。通过一个抽象的 `Principal` 实现，使其持有所有活动，你就可以扩展 `Principal` 来形成你的用户 `Principal` 和组 `Principal`。然后，用户可以将一个组 `Principal` 作为对象属性（或者一个组 `Principal` 列表，取决于你的需求）。这只是一个示例，有许多不同的处理方法。

# 基于声明的授权

在本节的早些部分，你探索了基于声明的身份验证（claims-based authentication）的概念。基于声明的授权是该概念的补充。在基于声明的授权中，用户的身份包含了该用户拥有权限的活动。此类系统的示例是微软的 Active Directory。当你使用 Windows 域凭据在机器上进行身份验证时，域控制器管理你的身份声明（用户名、名称、电子邮件地址以及附加到你的域的其他信息）和你的授权声明（分配给你的域权限）。你所属的域组是你身份声明的一部分，因此你也继承了分配给这些组的权限。这是一种基于组合的身份验证和授权系统。

如果你选择基于声明的身份验证，可以使用但不必使用基于声明的授权。通常，你用于验证用户的第三方系统对你的应用程序并不感知，因此它可能提供的任何声明授权对你的应用程序来说都是无用的。在这种情况下，当用户的身份声明从身份验证系统返回后，你还需要额外执行一步：你必须在你自己的系统中找到分配给该身份验证身份的权限。

# 为什么要用 SPRING SECURITY？

在本书的剩余部分，你将学习如何使用 Spring Security 将安全集成到你的应用程序中。尽管有很多 Java 安全框架可用，但 Spring Security 可能是 Web 应用中最流行的，而且作为一个 Spring 项目，它与 Spring Framework 无缝集成。请注意，就像完整的 Java EE 应用程序服务器可以提供 IoC、依赖注入和持久化提供服务一样，它也可以提供完整的安全框架。然而，与第二、第三部分一样，这部分侧重于为那些无法或不愿使用容器安全的应用程序提供一种容器安全的替代方案。

# 第 25 章 引入 Spring Security

# 理解 Spring Security 基础

Spring Security 提供身份验证和授权服务。你可以配置它来完全为你处理这些服务，也可以提供代码来执行关键操作以优化你的行为。除了使用 JDBC 或你的服务之一来验证用户外，Spring Security 还带有内置系统，用于身份验证以及（如果需要）使用微软的 Active Directory、Java 的中央认证服务 (CAS)、Java 身份验证与授权 JAAS（一种可插的身份验证模块 PAM）、LDAP 和 OpenID，所有这些都是基于声明的。通过 Spring Security，你可以保护基于 Web 和客户端的应用程序；它无疑是为 Web 设计的，在客户端应用程序中使用需要额外的精力。

Spring Security 围绕运行的核心接口是 `org.springframework.security.core.Authentication`。它提供了关于身份的一些额外信息。例如，`getIdentity` 方法返回一个代表 Principal 身份的对象。这通常是一个用户名（一个 String，以及 `getName`），也可以是其他对象，例如 X509 表示或电子邮件地址对象。`getCredentials` 返回据称证明身份是真实的凭据。这通常只在身份验证过程中使用，并在身份验证完成后被擦除。`isAuthenticated` 表示主体是否已通过身份验证（因此其身份已得到充分证明），而 `setAuthenticated` 是更改此指示的机制。这通常只在身份验证过程中使用。

Authentication 还通过 `Authorities` 方法提供用户的 `org.springframework.security.core.GrantedAuthority`。一个 GrantedAuthority 可以是一个角色（如果你使用基于角色的授权），也可以是一个活动（如果你使用基于活动的授权）。因为重要的不是名称，而是你如何使用它，GrantedAuthority 可以兼顾这两个用途。

当你针对 LDAP 或 Active Directory 等服务进行身份验证时，Spring Security 会自动用用户所属的组填充 Authorities。在这种情况下，组实际上充当了基于角色的验证中的角色。你可以通过编写少量代码将这些组替换为你的本地权限集或分配给这些组的权限，从而将其转换为基于活动的授权。

你将始终使用的最后一个接口是 `org.springframework.security.authentication.Provider`。正如其名，它是应用程序中身份验证服务的提供者。它的 `authenticate` 方法接收一个包含证明身份凭据的未身份验证的 Authentication，然后它可以标记 Authentication 为已验证并返回同一个对象，返回一个代表已身份验证主体的完全不同的 Authentication 实例，或者在身份验证失败时抛出 `org.springframework.security.core.AuthenticationException`。Spring 安全性提供了针对 Active Directory、CAS、JAAS、LDAP、OpenID、JDBC（使用你配置的表结构）等的 `AuthenticationProvider` 实现。你也可以提供自己的实现，以获得更自定义的身份验证行为。

## 使用 Spring Security 的授权服务

在 Spring Security 中，你有几种方法来使用授权，这些方法并不是互斥的。一种方法是使用全局方法安全注解。这是最好的方法之一，因为你可以在服务内部执行安全策略，而不是在 UI 内部——如果你有多个用户界面并使用了其中几种安全相关的注解之一，这一点尤为重要。Spring Security 会确保当前的 `Authentication` 具有正确的 `GrantedAuthority(s)` 来执行该方法。你将在接下来的章节中学习哪些注解以及如何使用它们。

另一种选择是在 Spring Security 配置中定义方法规则。这些规则类似于面向切面编程（AOP）的切入点。与安全注解一样，你可以定义拦截服务方法的规则，这使其成为使用授权保护代码的另一个吸引人的选项。根据应用程序的复杂程度，你可能会发现设置方法规则比注解更简单。此外，如果你使用 XML 配置，可以在无需重新编译的情况下更改方法拦截规则（这可能是你想要的，也可能不是）。你无法使用注解实现这一点。



你的最后一个选择是定义 URL 拦截规则。这是最简单的方法，但它有几个缺点。首先，你只能将其应用于 Web 应用程序，而不能应用于其他类型的应用程序。如果你有多个 Web 用户界面（例如，web、REST 和 SOAP），你必须为每个用户界面定义规则。这些规则很容易定义得不一致，从而导致授权漏洞。在任何情况下，你都希望使用注解或配置的规则来保护你的服务，将所有当前及未来的用户界面绑定到这些安全要求上。即使你使用方法安全，通常也想在登录和注销屏幕周围定义几个 URL 安全规则。在接下来的章节中，你将探索所有的选项。

## 配置 Spring Security

明确的是，你必须使用 Spring Framework 来利用 Spring Security。Spring Security 的配置与 Spring Framework 的配置紧密相关，它可能会大量使用 `ApplicationContext` 来管理其安全上下文。

在设置 Spring Security 时，你可以使用 XML、Java 或混合配置。Java 配置在某些方面是新的，它与 Spring Framework 的 Java 配置类似，但也有许多不同之处。一个重要的区别是，你没有许多配置相关的注解（只有两个）。相反，你的 `@Configuration` 类实现了接口，通过调用其中的方法来以编程的方式设置你的安全上下文。这是因为虽然 Spring Framework 每个应用上下文只有一个配置，但 Spring Security 在每个应用上下可以有多个配置。

例如，在 Web MVC 上下文中，根据该上下文内的 URL，你有一个、两个或十几个不同的安全上下文。每个上下文都需要单独的配置，因此你在 `@Configuration` 类中定义方法，使用 Spring Security 配置类添加你需要定义的每个安全上下文。你将在接下来的章节中详细探讨。更重要的是，由于 Java 配置比 Spring Framework 的 Java 配置冗长得多，你会看到同时使用 XML 和 Java 的每个配置。

### 总结

在这个简短的介绍章节中，你学习了身份验证（authentication）和授权（authorization）之间的区别，并理解了为什么有效安全需要这两者。你探索了用于身份验证和授权的许多方法，例如用户名和密码认证、基本认证和摘要认证、表单认证、基于角色的授权以及基于活动的授权。最后，你接触了 Spring Security，这是你在书中其余部分使用的身份验证和授权框架。你学习了它的 `Authentication`、`GrantedAuthority` 和 `AuthenticationProvider` 接口，以及它们如何构成 Spring Security 的基础。你还快速查看了使用 Spring Security 授权服务的不同方式，以及如何在 Spring Framework 应用程序中配置 Spring Security。

在下一章中，你将创建第一个启用 Spring Security 的应用程序，并学习如何验证用户以满足你的各种需求。

## 使用 Spring Security 验证用户

本章内容

- 为你的应用程序添加 Spring Security 身份验证
- 使用表单登录、JDBC、LDAP 和 OpenID
- 防止会话固定并限制用户会话
- 在会话之间记住用户
- 创建自定义身份验证提供者
- 缓解跨站请求伪造攻击

本章 WROX.COM 代码下载

你可以在下载选项卡通过 `http://www.wrox.com/go/javaforwebapps` 找到本章的 wrox.com 代码下载。本章的代码被分为以下示例：

- Authentication-App 项目
- Customer-Support-v19 项目

本章的新 MAVEN 依赖

除了在之前章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-web</artifactId>
  <version>3.2.0.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

```xml
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-config</artifactId>
  <version>3.2.0.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

```xml
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-crypto</artifactId>
  <version>3.2.0.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

你不再需要以下依赖项，因为 Spring Security 在其发行中包含了 BCrypt。

```xml
<dependency>
  <groupId>org.mindrot</groupId>
  <artifactId>jbcrypt</artifactId>
  <version>0.3m</version>
</dependency>
```

## 选择和配置身份验证提供者

你必须做的事情之一是选择使用什么机制来验证你的用户。正如你在上一章所看到的，Spring Security 拥有支持多种机制的内置 `AuthenticationProvider` 实现。你可以创建自己的实现，可能性是无限的。一旦选择了机制，你只需要对其进行配置并设置你的安全上下文。在本节中，我们将探索内置的提供者和 Spring Security 身份验证的配置。在下一节中，我们将创建自己的身份实现以执行更自定义的身份验证步骤。

> 如果你没有读过第 5 章并且对 `HttpSession`、会话标识符或会话固定攻击和其他会话漏洞的概念，强烈建议你在继续之前回到第 5 章。在本章中某些概念你可能无法理解。

## 配置用户详情提供者

你可以使用的简单的 `AuthenticationProvider` 实现之一是 `org.springframework.security.authentication.DaoAuthenticationProvider`。该提供者的核心概念是它使用数据访问对象（DAO），形式为 `org.springframework.security.core.userdetails.UserDetailsService` 的实现，根据用户名检索 `org.springframework.security.core.userdetails.UserDetails` 对象。

`UserDetails` 对象包含了有关用户的信息，例如用户名和密码、授权权限（`GrantedAuthorities`），以及用户是否已启用、过期和被锁定。这些内容共同构成了一个通用的身份提供者。你不需要担心验证用户的具体细节，只需提供一种获取用户详情的机制，让 Spring Security 来管理身份验证过程。当然，你也可以从各种默认的 `UserDetailsService` 实现中进行选择。

开始使用 `DaoAuthenticationProvider` 最简单的方法是使用 `org.springframework.security.provisioning.InMemoryUserDetailsManager`。这个简单的实现并非用于生产环境，但它非常适合简单的测试和演示——正如 Authentication-App 项目允许从 wrox.com 代码段中下载一样。

配置 Spring Security 的方式与配置 Framework 的方式存在一个关键区别。Spring Security 通过一系列过滤器（Filters）运行，这些过滤器在后台处理各种细节。这对于确保你的所有应用程序都能被正确地拦截并根据需要进行安全保护是必要的。因此，你不需要在单独的 `DispatcherServlet` 应用上下文中配置 Spring Security。相反，你始终要在运行时上下文（runtime context）中配置它，即使你打算用不同的安全原则来保护你的 `DispatcherServlet` 应用上下文。配置 Spring Security 包含两个关键：注册过滤器和设置安全规则。

## 设置 Spring Security 过滤器

对于使用 Java 配置注册过滤器，Spring Security 会为你处理这一切。请记住，`WebApplicationInitializer` 是它所使用的一个 Spring Framework 接口，用以初始化 Servlet 3.0 和新应用程序。Spring 的 `ServletContainerInitializer` 实现会发现所有的 `WebApplicationInitializer` 实现并对其进行初始化。在之前的章节中，我们创建了一个实现 `WebApplicationInitializer` 的 `Bootstrap` 类，用于注册所有的 Spring Framework 监听器和 Servlet。

当使用 Spring 的 Java 配置时，你所只需要扩展 `org.springframework.security.web.context.AbstractSecurityWebApplicationInitializer`。它负责注册所有正确的与安全相关的过滤器。但是，你必须小心应用程序中过滤器的顺序，它们必须按照以下顺序执行：

- 处理任何类型日志的过滤器，例如记录请求或向 Log4j `ThreadContext` 添加过滤器标记
- 所有安全过滤器（Security Filters）
- 处理安全敏感日志的过滤器，例如将当前用户添加到 Log4j 2 `ThreadContext` 中
- 处理多租户决策的过滤器（在多租户应用程序中，你需要尽早确定请求属于哪个租户。）
- 所有其他过滤器按其适当顺序排列

![](img/9c2d45f6d547f72cb870b3a991f62ef6_784_0.png)

在简单的 Authentication-App 中，你没有使用任何过滤器，所以暂时还不需要担心顺序。你将在下一节中查看这一点。现在，创建一个扩展 `AbstractSecurityWebApplicationInitializer` 的 `Bootstrap` 类。

```java
public class SecurityBootstrap extends AbstractSecurityWebApplicationInitializer
{}
```

注意，该类没有任何字段或方法；这是因为它不需要。这是为了注册 Spring 的过滤器。它还将会话跟踪模式设置为仅限 cookie（cookies only）。如果你选择了不同的会话跟踪方式（URL 或 SSL 会话 ID），则你需要重写 `getSessionTrackingModes` 方法来指示这一点：

```java
public class SecurityBootstrap extends AbstractSecurityWebApplicationInitializer{
    @Override
    protected Set<SessionTrackingMode> getSessionTrackingModes()
    {
        return EnumSet.of(SessionTrackingMode.SSL);
    }
}
```

然而，使用 cookie 是最简单的解决方案，并且适用于此目的，因此接受默认设置就是你需要做的。如果你没有使用 Java 配置，只需将 Spring 的 `DelegatingFilterProxy` 添加到你的部署描述符中。该类是一个过滤器代理，它封装了 Spring 的过滤器并在内部对它们进行排序。

```xml
<filter>
    <filter-name>springSecurityFilterChain</filter-name>
    <filter-class>org.springframework.web.filter.DelegatingFilterProxy</filter-class>
</filter>

<filter-mapping>
    <filter-name>springSecurityFilterChain</filter-name>
    <url-pattern></url-pattern>
    <dispatcher>ERROR,REQUEST</dispatcher>
</filter-mapping>
```

记住，如果你选择此路线，`DelegatingFilterProxy` 仍然必须出现在之前提到的顺序中，即下方 Spring Security 过滤器之前。如果你在任何地方通过程序方式注册过滤器，你可能需要坚持扩展 `AbstractSecurityWebApplicationInitializer`。

## 配置登录机制和受保护的 URL

现在已经注册了 Spring 过滤器，你可以继续为你的应用程序配置 Spring Security。将此内容放在根上下文（root context）中通常涉及在你自第二部分以来创建并使用的 `RootContextConfiguration` 中添加更多代码。然而，该类变得有点拥挤，而且安全配置最终可能会变得非常大，因此另一种具有吸引力的方法是创建一个新的配置类并从 `RootContextConfiguration` 导入它。

```java
@ComponentScan(
    basePackages = "com.wrox.site"
```

这段代码中有很多内容，让我们将其拆解并逐一检查。

你应该了解的两个非常相似的注解：`@org.springframework.security.config.annotation.web.EnableWebSecurity` 和 `@org.springframework.security.config.annotation.web.servlet.configuration.EnableWebMvcSecurity`。第一个注解启用了 Spring Security Web 身份验证和授权功能。第二个注解也启用了与 Spring MVC 的集成。除非你不使用 Spring MVC，否则你应该始终使用 `@EnableWebSecurity`。每当你在 `@Configuration` 类上注释 `@EnableWebSecurity` 或 `@EnableWebMvcSecurity` 时，该类必须扩展 `org.springframework.security.config.annotation.web.WebSecurity` 或实现 `org.springframework.security.config.WebConfigurerAdapter`。扩展 `WebConfigurerAdapter` 是一种更简单的方法，你没有理由不这样做。

`configure(AuthenticationManagerBuilder)` 方法设置了你应该用于验证用户的身份提供者（AuthenticationProvider）。你并不需要直接使用 `InMemoryUserDetailsManager` 来使用内存数据库。Java 和 XML 配置提供了配置 `InMemoryUserDetailsManager` 的快捷方式。在这个方法中，你在内存中创建了两个用户并分配了相应的授权权限（GrantedAuthorities）。这是一个授权细节，但有时很难防止这些细节溢出。

> 注意 你可能注意到 `configure(AuthenticationManagerBuilder)` 方法引用的是身份验证管理器（Authentication Manager），而书中提到的是身份验证提供者（Authentication Provider）。从技术上说，Spring 的力量在于 `org.springframework.security.authentication.AuthenticationManager` 的实现。虽然你技术上可以实现此接口，但你不应该这样做。默认且唯一的实现 `org.springframework.security.authentication.ProviderManager` 会委托给一个或多个 `AuthenticationManager` 实现。这允许你拥有多种验证用户的方法。在本节的稍后部分，你将看到这种方式的示例：“我自己”验证。

`configure(WebSecurity)` 方法非常简单。在这种情况下，它所做的只是防止 Spring 对安全考虑因素（JavaScript、样式表、图像等）评估访问。`configure(HttpSecurity)` 执行了大部分工作。首先它定义了几个 URL 模式以及如何保护它们。再次，这是一个授权细节，但为了设置某种最小级别的授权以让 Spring Security 用户登录是必要的。

`permitAll` 调用指示 Spring Security 允许访问 `/signup`、`/about` 以及 `/secure/` URL 下的所有内容需要用户具有 USER 权限，而访问 `/admin/` 及其下的所有内容则需要 ADMIN 权限。任何其他请求都需要 Spring 身份验证，无论权限如何。



接下来，调用 `formLogin` 开始通过表单登录配置用户名和密码认证的过程。它设置了登录表单应该存放的 URL；身份验证失败时用户跳转的 URL；以及登录表单中提交的用户名和密码名称。最后，调用 `logout` 配置了触发注销的 URL 以及用户注销后跳转的 URL。这两个地方的 `permitAll` 调用确保了用户无需身份验证即可访问登录和注销（原因显而易见）。在 Java 配置中，默认启用了跨站请求伪造（CSRF）保护。（在 XML 配置中默认是禁用的。）CSRF 保护是一个将在下一节介绍的复杂主题，因此目前禁用了它，通过调用 `csrf` 后调用 `disable` 来实现。

> 注意：你可能很好奇在 `configure(WebSecurity)` 中忽略 URL 与在 `configure(HttpSecurity)` 中允许访问所有 URL 的区别。忽略 URL 将跳过 Spring Security 的内部过滤器。这非常重要，因为你希望静态资源的访问尽可能快，而跳过 Spring 内部过滤器可以确保这种速度。允许访问所有 URL 仍然通过 Spring Security 内部过滤器向这些 URL 发送请求，这为受保护的 URL 必要的开销。配置这些设置时的可用选项非常多，无法一一列举。API 文档是你的朋友，你应该经常参考它。当 Spring Security 检测到用户身份验证以访问受保护的 URL 时，它会将用户重定向到配置的登录 URL。

你必须提供实现登录表单的视图，并确保提交 POST 请求到同一个 URL。然而，你并不需要实现提交的表单。当 Spring Security 检测到向配置的 URL 的 POST 请求时，它会使用配置的参数提取用户名和密码，找到配置的 `org.springframework.security.authentication.UsernamePasswordAuthenticationToken`（在这种情况下，提供者是带有 `InMemoryUserDetailsManager` 的 `DaoAuthenticationProvider`），并使用该提供者对用户进行验证。如果身份验证失败，Spring Security 将用户重定向到失败 URL。如果身份验证成功，它将用户发送到原始意图 URL（如果用户直接进入登录界面，则发送到默认 URL）。

最后，如果 Spring Security 检测到对配置的注销 URL 的请求，它将清除身份验证、失效 `HttpSession`、删除会话 Cookie并将用户重定向到配置的受保护 URL。

如你所见，Spring Security Java 配置使用了流式 API（fluent API），这与 Spring Framework 的 Java 配置形成鲜明对比。这是出于需要而不仅仅是为了设计。它让配置各种（有时是重复的）安全组件变得相当简单，你的 IDE 的代码提示可以帮助你确定每个组件的选项。然而，并不是人都喜欢流式 API，有些开发者更倾向于不同的方法。接的 XML 配置与 Authentication-App 中的 Java 配置完全相同。你可以使用 `@Import` 从 RootContextConfiguration 导入它。

```xml
<xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/security"
     xmlns:beans="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://www.springframework.org/schema/security
     http://www.springframework.org/schema/security/spring-security-3.2.xsd
     http://www.springframework.org/schema/beans
     http://www.springframework.org/schema/beans/beans-4.0.xsd">

<authentication-manager>
    <authentication-provider>
        <user-service>
            <user name="John" authorities="USER" password="password" />
            <user name="Margaret" authorities="USER, ADMIN" password="green" />
        </user-service>
    </authentication-provider>
</authentication-manager>

<http security="none" resource="/resource/**" />
    <intercept-url patterns="/signup" access="permitAllAll" />
    <intercept-url patterns="/about" access="permitAllAll" />
    <intercept-url patterns="/policies" access="permitAllAll" />
    <intercept-url patterns="/login" access="permitAllAll" />
    <intercept-url patterns="/logout" access="permitAllAll" />
    <intercept-url patterns="/secure/**" access="hasAuthority('USER')" />
    <intercept-url patterns="/admin/**" access="hasAuthority('ADMIN')" />
    <form-login login-page="/login"
                login-processing-success-url="/login"
                authentication-failure-default-url="/login?error"
                username-parameter="username"
                password-parameter="password" />
    <logout logout-url="/logout"
            logout-success-url="/login?loggedOut"
            invalidate-session="true"
            delete-cookies="JSESSIONID" />
</http>

</beans>
```

# 设置会话固定保护

你应该熟悉 HTTP 会话固定（session fixation）攻击问题，以及这些攻击如何导致你的用户在网站上的账户面临风险。在第 5 章中，你探索了缓解这些攻击的方法。坦率地说，Spring Security 也内置了缓解这些攻击的工具。在 Servlet 3.1 之前，开发者通常不得不采取创建新会话、将数据从一个会话复制到另一个会话，然后失效旧会话。Spring Security 让这项任务变得非常简单——只需一个简单的配置即可切换行为。默认情况下，Spring Security 保护了会话固定，因为会话固定攻击是 Web 应用程序中的一个大问题。Servlet 3.1 `HttpServletRequest changeSessionId` 方法使得会话固定保护变得极其简单，Spring Security 3.2 包含了对该方法的支持。你可以在配置中对其微调。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Override
    protected void configure(HttpSecurity security) throws Exception {
        security
            .invalidateSession(true).deleteCookies("JSESSIONID")
            .and().sessionManagement()
            .sessionFixation().changeSessionId()
            .and().csrf().disable();
    }
}
```

之前的代码获取会话管理配置并指示 Spring Security 使用 Servlet 3.1 `changeSessionId` 方法防御会话固定攻击。明确的是，这实际上对应的。默认情况下，Spring Security 为运行在 Servlet 3.1 容器上的应用程序使用 `changeSessionId` 机制，你也可以选择

- `newSession`：创建一个不包含现有会话属性的新会话。
- `migrateSession`：创建一个新会话并复制所有现有属性。
- `none`：禁用会话固定保护。

当应用程序运行在 Servlet 3.0 或更旧容器时，`migrateSession` 是默认值。在 XML 中配置会话固定保护同样简单：

```xml
<http use-expressions="true">
    ...
    <session-management session-fixation-protection="migrateSession" />
</http>
```

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter
{
}
```

```java
@Override
    protected void configure(HttpSecurity security) throws Exception
{
        ...
        .invalidateHttpSession(true).deleteCookies("JSESSIONID")
        .permitAll()
        .and()...sessionManagement()(
            .sessionFixation().changeSessionId()
            .maximumSessions(1).expiredUrl("/login?maxSessions")
        ).and().and()..csrf().disable();
    }
}
```

```xml
<http use-expressions="true">
    <session-management session-fixation-protection="changeSessionId">
        <concurrency-control max-sessions="1" expired-url="/login?maxSessions" />
    </session-management>
</http>
```

当配置了最大会话数量时，默认行为是在用户登录时使现有会话过期。在这种情况下，如果原始会话的持有者尝试访问该会话，他们将被重定向到 /login?maxSessions。这并不总是预期的行为。相反，你可以指示 Spring Security 防止第二次登录并返回未经授权的响应，允许会话不受影响地继续。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter
{
}
```

```java
@Override
    protected void configure(HttpSecurity security) throws Exception
{
        ...
        .invalidateHttpSession(true).deleteCookies("JSESSIONID")
        .permitAll()
        .and()...sessionManagement()(
            .sessionFixation().changeSessionId()
            .maximumSessions(1).maxSessionsPreventsLogin(true)
        ).and().and()..csrf().disable();
    }
}
```

```xml
<http use-expressions="true">
    <session-management session-fixation-protection="changeSessionId">
        <concurrency-control max-sessions="1" error-if-maximum-exceeded="true" />
    </session-management>
</http>
```

注意，此行为的配置选项在 Java 配置和 XML 配置中的名称不同。或者，你可以在不更改默认会话固定保护的情况下开启并发。只需省略 `sessionFixation()..option()` 代码或 `session-fixation-protection` XML 属性。

要启用并发，你必须配置一个特殊的 Spring Security 监听器来发布 HttpSession 相关的事件。这允许 Spring Security 构建一个会话注册表用于检测并发会话。启用此功能的简单方法是在你的 SecurityBootstrap 类中重写 `enableHttpSessionEventPublisher` 方法。

```java
public class SecurityBootstrap extends AbstractSecurityWebApplicationInitializer {
  @Override
  boolean enableHttpSessionEventPublisher() {
    return true;
  }
}
```

如果你使用 XML 配置，可以手动将监听器添加到部署描述符中。

```xml
<listener>
  <listener-class>
    org.springframework.security.web.session.HttpSessionEventPublisher
  </listener-class>
</listener>
```

无论你采用何种方法配置此项，如果你在集群环境中部署应用程序，你必须注意同步集群中所有节点上的会话。否则，监听器将无法感知所有会话，并且无法正确限制用户可以持有的会话数量。

Authentication-App 包含一个基础控制器，响应 Spring Security 保护的简单 URL。该控制器的细节并不重要，且包含的内容你已经熟悉。如需测试它，请遵循以下步骤：

1. 编译项目并从 http://localhost:8080/authentication/about、http://localhost:8080/authentication/signup 和 http://localhost:8080/authentication/policies 启动 Tomcat。你可以无需登录访问这些页面。
2. 现在访问 http://localhost:8080/authentication/secure/ 或其下的任何 URL，Spring Security 会要求你登录。输入错误的凭据，Spring Security 将你带回登录屏幕并提示你登录失败。
3. 输入正确的凭据，你应该被授予访问。
4. 点击 Log Out 链接注销，并使用另一组凭据登录。以 John 身份登录后尝试访问 http://localhost:8080/authentication/admin/，Spring Security 将阻止访问。
5. 注销并以 Margaret 身份重新登录，Spring Security 应该允许你访问管理页面。

## 使用 JDBC UserDetails 服务

如前所述，`InMemoryUserDetailsManager` 只是一个测试实现，永远不应在生产应用程序中使用。它对于演示很有用，但还有哪些选项呢？如果你将用户存储在数据库中（大多数应用的典型做法），`org.springframework.security.provisioning.JdbcUserDetailsManager` 提供了从数据库获取 `UserDetails` 的简单机制。你只需为其提供一个 `DataSource` 并配置 SQL 查询以从数据库中获取用户及其权限。



```java
@Configuration
@EnableMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Inject DataSource dataSource;

    @Override
    protected void configure(AuthenticationManagerBuilder builder)
        throws Exception {

        builder
            .jdbcAuthentication(this.dataSource)
            .usersByUsernameQuery("SELECT Username, Password, Enabled = ?\n" + 
                "FROM User WHERE Username = ?")
            .authoritiesByUsernameQuery("SELECT Username, Permission = ?\n" + 
                "FROM UserPermission WHERE Username = ?")
            .passwordEncoder(new BCryptPasswordEncoder());
    }
}
```

大部分配置应该是自而易懂的。“users by username”查询必须按顺序返回用户名、密码和启用状态。“authorities by username”查询必须按顺序返回用户名和权限。两个查询都需要一个参数，即要查找的用户名。

当然，你不应该在数据库中以明文存储用户密码，Spring Security 的 `org.springframework.crypto.password.PasswordEncoder` 接口提供了比较哈希密码的机制。`BCryptPasswordEncoder` 提供了标准的密码实现。

## 选择和配置身份提供者 | 759

以下 XML 配置与 JDBC 服务的 Java 配置完全相同。

```xml
<authentication-manager>
  <authentication-provider data-source-ref="dataSource">
    <jdbc-user-service users-by-username-query="SELECT Username, Password, Enabled FROM User WHERE Username = ?" 
      authorities-by-username-query="SELECT Username, Permission FROM UserPermission WHERE Username = ?" 
      <password-encoder hash="bcrypt" />
  </authentication-provider>
</authentication-manager>
```

## 使用其他详情服务

除了 `JdbcUserDetailsManager`，还有 `org.springframework.security.ldap.userdetails.LdapUserDetailsManager` 类。这些类不能用于实际的身份验证过程，因为它们无法从 LDAP 提供者获取密码。还有许多内置的 `UserDetailsService` 实现，但你也可以轻松定义自己的。只需创建一个 `UserDetails` 实现，在你的 `SecurityConfiguration` 中获取其实例（手动或注入），并将其添加到安全配置中。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Inject UserDetailsService myUserDetails;

    @Override
    protected void configure(AuthenticationManagerBuilder builder)
    throws Exception {
        builder.userDetailsService(this.myUserDetails)
            .passwordEncoder(new BCryptPasswordEncoder());
    }
}
```

使用 XML 配置你的 `UserDetailsService` 基本相同。

```xml
<authentication-manager>
  <authentication-provider user-service-ref="myUserDetails">
    <password-encoder hash="bcrypt" />
  </authentication-provider>
</authentication-manager>
```

## 与 LDAP 和活动目录提供者一起工作

要确保的是，`DaoAuthenticationProvider` 类和对应的 `UserDetailsService` 接口在简单情况下快速让 Spring 运行非常有用。

现实生活很少那么简单，通常需要调用更复杂的身份验证机制。使用轻量级目录访问协议（LDAP）进行声明的身份验证就是一个例子。为此，Spring Security 提供了一个 `org.springframework.security.ldap.authentication.LdapAuthenticationProvider`。

这个提供者是必要的，因为你无法从 LDAP 服务器上获取密码（哈希处理后的或其他格式）。例如，最常见的身份验证策略是绑定（Bind），即用户通过“登录”到 LDAP 服务器来确立其身份。`LdapAuthenticationProvider` 直接与 LDAP 服务器进行身份验证，而不是将用户重定向到身份验证服务器。它有多个选项，但你通常不需要直接配置它。相反，你可以使用 Java 配置或 XML 命名空间。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Override
    protected void configure(AuthenticationManagerBuilder builder)
        throws Exception {
        builder
            .ldapAuthentication()
                .contextSource()
                    .url("ldap://ldap1.example.org:389/dc-example,dc=org or ldap://ldap2.example.org:389/dc-example,dc=org")
                    .managerDn("uid=admin,ou=system")
                    .managerPassword("bindPassword")
                    .and()
                .userSearchFilter("uid={0})")
                .userSearchBase("ou=people")
                .groupSearchBase("ou=groups");
    }
}
```

```xml
<ldap-server-dn="uid=admin,ou=system" manager-password="bindPassword"
url="ldap://ldap1.example.org:389/dc-example,dc=org or ldap://ldap2.example.org:389/dc-example,dc=org" />

<authentication-manager>
    <ldap-authentication-provider user-search-filter="uid={0}"
        user-search-base="ou=people"
        group-search-base="ou=groups" />
</authentication-manager>
```

这些配置假设服务器没有启用匿名访问，因此需要一个管理器区分名（DN）和密码供其他进行绑定。如果你的服务器允许匿名访问，可以省略这些项。通过用逗号分隔 URL（遵循 LDAP 的惯），可以启用冗余和高可用的多个服务器。这些配置还假设用户可能位于目录的多个节点中（典型场景），并指定了用户搜索基路径和过滤器，以便在基节点内的范围内定位用户。如果你的用户始终位于同一个节点，可以省略搜索和基路径属性，而改用 `userDnPatterns`/`user-dn-pattern` 属性。组搜索基路径属性指示 Spring Security 如何定位用户所属的 LDAP 组。如果你还想利用目录进行基于声明的授权，则这是必要的，否则可以省略。要限制返回的组组，你可以指定 `groupSearchFilter`/`group-filter`。

> 警告：LDAP 是一个复杂的课题，超出了本书的范畴。任何类型的 LDAP 客户端都非常容易配置错误，根据所错误的类型，这可能会导致你的应用程序无法运行或无法访问。在尝试将 LDAP 身份验证集成到应用程序之前，应务必咨询 LDAP 服务器管理员。

早些时候读过 `LdapUserDetailsManager` 和 `LdapUserDetailsService` 类。这些类可以从 LDAP 服务器获取 `UserDetails`，但它们无法获取用于验证用户的密码信息。那么它们是做什么用的呢？嗯，你并不严格需要它们。上述针对 LDAP 服务器进行用户验证的配置，如果你想在启用了 LDAP 的应用程序登录界面上提供“记住我”复选框并使用 XML 配置，则你必须也配置 `LdapUserDetailsManager` 或 `LdapUserDetailsService`。（这些类解析外部用户的方式略有不同，这超出了本书的范畴。）

当一个“记住我”的用户返回并通过身份验证时，此服务会从 LDAP 服务器解析用户详情（并确保用户未被删除、禁用或锁定）。你应该使用与 `LdapAuthenticationProvider` 相同的搜索和过滤器详情来配置该服务。Java 配置会自动为你处理这一点。你将在本节中学习更多关于“记住我”身份验证的内容。

Spring Security 对 Windows 活动目录（Active Directory）认证提供了内置支持。这种支持使用 LDAP，并要求你在域控制器上启用 LDAP。（默认启用，但某些域管理员能够简化措施）。这意味着 `org.springframework.security.ldap.authentication.ActiveDirectoryLdapAuthenticationProvider` 与 `LdapAuthenticationProvider` 紧密相关——两者都扩展了 `org.springframework.security.ldap.authentication.AbstractLdapAuthenticationProvider`。

配置 `LdapAuthenticationProvider` 连接到 Windows 域控制器是一项非常复杂的任务。由于所有 Windows 域控制器的 LDAP 结构都是相同的，Spring Security 提供了 `ActiveDirectoryLdapAuthenticationProvider` 来极大简化任务。它还将域控制器返回的微软专用错误代码转换为更有用的错误信息。你只需要提供默认的 Windows 域名称（当用户名不包含漏洞时）以及域控制器 LDAP 服务器的 URL 或多个 URL，如下面的 Java 和 XML 配置所示。

```java
@Configuration
@EnableMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(AuthenticationManagerBuilder builder)
    throws Exception
    {
        builder.authenticationProvider(
            new ActiveDirectoryLdapAuthenticationProvider(
                "example.com",
                "ldap://dc1.example.org:389/"
            )
        );
    }
}
```

```xml
<bean id="activeProvider" class="org.springframework.security.ldap.authentication.ActiveDirectoryLdapAuthenticationProvider">
    <constructor-arg value="example.com" />
    <constructor-arg value="ldap://dc1.example.org:389/" />
</bean>

<authentication-manager>
    <authentication-provider ref="activeProvider" />
</authentication-manager>
```

> 注意：要使用 Spring 的 LDAP 支持，你需要在项目中添加以下依赖项。

```xml
<dependency>
    <groupId>org.springframework.security</groupId>
    <artifactId>spring-security-ldap</artifactId>
    <version>3.2.0.RELEASE</version>
    <scope>compile</scope>
</dependency>
```

## 使用 OpenID 进行身份验证

Spring Security 还提供了对 OpenID 认证的内置支持。如果你对 OpenID 身份验证感兴趣，可以跳到“记住用户”。本部分的假设你对 OpenID 的工作原理有所了解，并提到了几个 OpenID 概念。由于 OpenID 是一种基于声明的身份验证系统，需要将用户重定向到提供者，因此你不需要 `AuthenticationProvider`，也不需要配置登录机制。相反，你需要配置一个登录机制，向用户展示你支持的 OpenID 提供者列表以及用于输入 OpenID 标识符的字段。当用户提交此表单时，Spring Security 将接管，将他们重定向到正确的提供者 URL，并在他们返回时完成回调验证过程。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Override
    public void configure(HttpSecurity security) {
        security.ignoring().antMatchers("/resource/**");
    }
    @Override
    protected void configure(HttpSecurity security) throws Exception {
        security
            .authorizeRequests()
                .antMatchers("/signup", "about", "policies/").permitAll()
                .antMatchers("/secure/**").hasAuthority("USER")
                .antMatchers("/admin/**").hasAuthority("ADMIN")
                .anyRequest().authenticated()
            .loginPage("/login")
                .failureUrl("/loginerror")
                .defaultSuccessUrl("/secure/", true)
            .logout()
                .logoutUrl("/logout").logoutSuccessUrl("/login?loggedOut")
                .invalidateHttpSession(true).deleteCookies("JSESSIONID")
            .permitAll()
            .sessionManagement()
                .sessionFixation().changeSessionId()
                .maximumSessions(1).maxSessionsPreventsLogin(true)
            .and().csrf().disable();
    }
}
```



此配置设置了 OpenID 登录机制，并与两个常用的提供者配置了属性交换。为每个提供者创建处理设置可能会更合理一些。该配置还设置了熟悉的登录页面、失败 URL 和默认成功 URL，这些都是你之前为表单登录机制配置过的。

你提供的 `loginPage` 包含一个 OpenID 标识符（该字段必须命名为 `openididentifier`）以及你所支持的所有提供者的按钮。

`UserDetailsService` 是你设计的一个基于 `org.springframework.security.core.UserDetailsService` 的理论实现，能够接收 `org.springframework.security.openid.OpenIDAuthenticationToken` 并返回一个 `UserDetails` 对象。如果你决定同时启用“记住我”（remember me）身份验证，则必须提供一个 `UserDetailsService` 实现。你在这两个目的可以使用同一个 `UserDetailsService`。

如你所见，在 Spring Security 中配置 OpenID 涉及的细节非常多，足以填充另一个章节。如果你想看更多示例，Spring GitHub 仓库中的示例代码是一个极佳的资源。

> 注意：要使用 Spring Security 的 OpenID 支持，你需要在项目中添加以下 Maven 依赖（第一个作为直接依赖，其他用于强制使用包含许多错误修复和安全改进的较新依赖）。此依赖会引入许多传递依赖。

```xml
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-security-openid</artifactId>
    <version>3.2.0.RELEASE</version>
    <scope>compile</scope>
</dependency>
```

```xml
<dependency>
    <groupId>org.commons</groupId>
    <artifactId>commons-codec</artifactId>
    <version>1.9</version>
    <scope>runtime</scope>
</dependency>
```

```xml
<dependency>
    <groupId>org.apache.httpcomponents</groupId>
    <artifactId>httpclient</artifactId>
    <version>4.3.1</version>
    <scope>runtime</scope>
</dependency>
```

### 记住用户

许多网站都提供记住我身份验证（remember-authentication）。该概念通常涉及登录屏幕上的复选框，用户可以通过复选框指示网站记住他们的浏览器并在下次访问自动登录。这是通过在用户的浏览器中保存 cookie 来在他们下次访问时识别其身份实现的。

明确的是，这是一个等待发生的安全漏洞。攻击者可以获取用户的 cookie，然后代表用户访问你的应用程序。你可以通过使用快速过期或只能使用一次的记忆令牌（remember-tokens）来减轻安全顾虑，但实际上该漏洞仍然存在。在保护任何类型的敏感信息（如医疗保健数据、财务记录或就业信息）时，你永远不要使用“记住我”身份验证。然而，对于低安全性的情况（如用户论坛和带有内容的节点网站），出于用户便利性的考虑，这种妥协是可以接受的。

Spring Security 通过一个特殊的 `org.springframework.security.authentication.RememberMeAuthenticationProvider` 提供了记住我身份验证。如果你想启用记住我，请在你的登录屏幕上添加一个字段名为 `remember-me` 的复选框（使用 XML 配置时为 `spring_security_remember_me`），然后简单地在你的配置中开启记住我服务即可：

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter
{
    @Override
    protected void configure(HttpSecurity security) throws Exception
    {
        security.maxSessions(1).maxSessionsPreventsLogin(true)
            .and().csrf().disable()
            .rememberMe().key("MyAppName");
    }
}
```

```xml
<http use-expressions="true">
    <remember-me key="MyAppName"/>
</http>
```

如果你的登录过程通过 SSL 进行（这本应该是这样的），请使用 `SecureCookie`（或将 `use-secure-cookie` 设置为 true）来增加安全性。这消除了攻击者获取你用户记住我 cookie 的一种途径。你还可以使用 `tokenValidSeconds`（或 `token-validity-seconds`）来控制记住我令牌在过期前的有效期，进一步限制令牌的可用性。如之前讨论的，记住我服务需要 `UserDetails` 实现才能正常工作。然而，如果你有多个 `UserDetailsServices`，你必须选择你想要支持记住我服务的那个，并通过 `userDetailsService`（或 `user-service-ref`）指定它。

存在一个稍微安全一点的记住我服务，它需要一个 `DataSource` 和一个具有特定模式的表。该功能的使用在 Spring Security 文档中有详细介绍，但通常情况下作者建议永远不要使用记住我服务。

## 探索其他身份验证提供者

Spring Security 自带了其他几个内置 `AuthenticationProviders`。`org.springframework.security.authentication.CasAuthenticationProvider` 使用 Jas 中央认证服务管理身份验证。`org.springframework.security.authentication.jaas.DefaultJaAuthenticationProvider` 和 `org.springframework.security.authentication.jaas.JaasAuthenticationProvider` 使用 Java 认证和 JAAS 实现，这可能在所有 Java 虚拟机上都不可用，而 `DefaultJaasAuthenticationProvider` 可以与任何 JAAS 实现配合。

`org.springframework.security.web.authentication.preauth.PreAuthenticatedProvider` 是一个有趣的实现。它的运行基于：你可能会遇到某些无法或不想使用 Spring Security 身份验证功能的情况。此类场景包括客户端认证（Servlet 容器可以处理）、SiteMinder 身份验证以及直接在 Servlet 容器内处理的其它身份验证。在配置预认证时，你必须仔细告诉 Spring Security 如何正确且安全地处理预认证请求。

`org.springframework.security.authentication.rpc.RemoteAuthenticationProvider` 是一个非常相似的提供者，适用于身份验证在外部处理的略微不同的情况。最后一个内置提供者是 `org.springframework.security.web.authentication.AuthenticationFilter`。

## 编写你自己的身份提供者

尽管所有内置机制都很有用，但有时它们并不足够。坦率地说，编写自己的 `AuthenticationProvider` 相当简单，在本节中我们只需

## 编写你的身份提供者

该项目是自包含的，你下载后即可运行。本节仅涵盖了为了添加身份验证对项目进行的修改。如果你不是从一开始就开始工作的，别担心！

早期，你为应用程序添加了一个简单的用户名密码认证系统。这对于完成最基本的功能是必要的。现在，你可以用 Spring Security 的功能替换这种自制的认证。本节将向你如何这样做，并向你介绍跨站请求伪造（CSRF）。

## 正确顺序的启动

正如你可能记得，应用程序中的 Spring Framework、Servlet 和过滤器配置比你在示例中创建的复杂得多。一个重要的问题是 `LoggingFilter` 执行了两个任务：将一个标签（UUID 形式）和登录用户添加到 `ThreadContext` 中。这个问题在于，用户名在过滤器链执行后才会变得可用，这意味着过滤器代码必须放在最后。然而，最后执行过滤器标签代码将导致安全日志无法包含过滤器标签，这是不可接受的。由于由于，你必须将日志过滤器拆分为两个并按正确的顺序启动一切。

## 拆分过滤器

拆分过滤器不是复杂的任务。将 `LoggingFilter` 替换为 `PreSecurityLoggingFilter` 和 `PostSecurityLoggingFilter`。`PreSecurityLoggingFilter` 设置过滤器标签并在请求完成时清除过滤器标签和用户名。

```java
public class PreSecurityLoggingFilter implements Filter {
    @Override
    public void doFilter(ServletRequest request, ServletResponse response,
        FilterChain chain) throws IOException, ServletException {
        String id = UUID.randomUUID().toString();
        ThreadContext.put("id", id);
        try {
            ((HttpServletResponse) response).setHeader("X-Wrows-Request-Id", id);
```

`PostSecurityLoggingFilter` 更加简单。它使用 Spring Security `org.springframework.security.core.context.SecurityContextHolder` 的静态方法来获取当前的 `org.springframework.security.core.context.SecurityContext`。此上下文请求本地的，并持有属于当前请求和 HTTP 会话的身份验证（`Authentication`）。`PostSecurityLoggingFilter` 将从 `ThreadContext` 中移除用户名的操作委托给 `PreSecurityLoggingFilter`，这样用户名就可以尽可能在 `ThreadContext` 中存在得久一些。

```java
public class PostSecurityLoggingFilter implements Filter {
    @Override
    public void doFilter(ServletRequest request, HttpServletResponse response, FilterChain chain) throws IOException, ServletException {
        SecurityContext context = SecurityContextHolder.getContext();
        if (context != null && context.getAuthentication() != null) {
            ThreadContext.put("username", context.getAuthentication().getName());
        }
        chain.doFilter(request, response);
    }
}
```

## 启动类的排序

既然你已经拆分了日志过滤器，确保所有组件都按照正确的顺序初始化至关重要。必须先注册 `PreSecurityLoggingFilter`，然后是 Spring Security 过滤器，最后是 `PostSecurityLoggingFilter`。由于 Spring Framework 仅注册了一个 `ServletContextListener` 和几个服务器，因此在初始化 Spring Framework 方面这并不重要。它不会干扰过滤器的执行顺序。

对多个 Spring Framework `ApplicationInitializers` 进行排序非常简单。你只需要在类上加上 `@org.springframework.core.annotation.Order` 注解，并提供一个与初始化器优先级对应的值。值越小优先级越高，因此 -2,147,483,647 是可能的最高优先级。值越大优先级越低，因此可能的最低优先级是 2,147,483,647。对于你的需求，最简单的方法是将使用的三个启动类编号为 1、2 和 3。这些类被分组在 `com.springframework.config.bootstrap` 包中，Framework 替换了以前版本中的旧 `Bootstrap` 类。省略号代表未更改的 Spring Framework 启动代码。唯一的区别是之前的 `AuthenticationFilter` 消失了，并且在这里注册的是 `PreSecurityLoggingFilter` 而不是之前的 `LoggingFilter`。

```java
@Order(1)
public class FrameworkBootstrap implements ApplicationInitializer {
    private static final Logger log = LoggerFactory.getLogger();
    @Override
    public void onStartup(ServletContext container) throws ServletException {
        log.info("Executing framework bootstrap.");
        ...
        FilterRegistration.Dynamic registration = container.addFilter(
"preSecurityLoggingFilter", new PreSecurityLoggingFilter()
);
registration.addMappingForUrlPatterns(null, false, "*/*");
}
}
```

接下来，你需要启动 Spring Security 的过滤器链。除了添加 `@Order` 注解和一条日志语句（用于证明排序是正确的）之外，这与为 Authentication-App 项目创建的 `SecurityBootstrap` 完全相同。

```java
@Order(2)
public class SecurityBootstrap extends AbstractSecurityWebApplicationInitializer {
    private static final Logger log = LogManager.getLogger();

    @Override
    protected boolean enableHttpSessionEventPublisher() {
        log.info("Executing security bootstrap.");
        return true;
    }
}
```

启动过程的最后一步是在新的 `LoggingBootstrap` 类中注册 `PostSecurityLoggingFilter`。当 Spring Framework 启动时，它会按照它们出现的顺序执行这些启动类。

```java
@Order(3)
public class LoggingBootstrap implements WebApplicationInitializer {
    private static final Logger log = LogManager.getLogger();

    @Override
    public void onStartup(ServletContext container) throws ServletException {
        log.info("Executing logging bootstrap.");
        FilterRegistration.Dynamic registration = container.addFilter("postSecurityLoggingFilter", new PostSecurityLoggingFilter());
        registration.addMappingForUrlPatterns(null, false, "*/*");
    }
}
```

## 创建并配置提供者



现在日志和 Spring Security 已按正确的顺序设置启动，是时候创建自己的 `AuthenticationProvider` 实现了。由于你在整个应用程序中使用 `UserPrincipal` 实体作为身份，最简单的方法是直接更新 `UserPrincipal` 以实现 `Authentication`。然后你就可以从你的身份实现中返回它。

# 转换 User Principal 和身份验证服务

在大多数情况下，`UserPrincipal` 保持大部分不变。它的映射是相同的，并且仍然实现了 `Principal` 和 `Serializable`，但是通过实现 `Authentication` 间接实现的。主要的变化是增加了 `Authentication` 中指定的 `getAuthorities`、`getPrincipal`、`getDetails`、`getCredentials`、`isAuthenticated` 和 `setAuthenticated` 方法。它们的实现是模板代码。在下一章中，你会将权限（author）映射到新的数据库表上。

最重要的变化是 `AuthenticationService` 接口及其 `DefaultAuthenticationService` 实现。`AuthenticationService` 现在扩展了 `AuthenticationProvider`，重写了它的 `authenticate` 方法以明确该提供者只返回 `UserPrincipals`。

```java
@Validated
public interface AuthenticationService extends AuthenticationProvider {
    @Override
    UserPrincipal authenticate(Authentication authentication);

    void saveUser(
        @NotNull(message = "${saveUser}")
        UserPrincipal principal,
        String newPassword
    );
}
```

支持方法的实现没有改变任何内容。`authenticate` 显然发生了很大变化，支持方法表明该提供者仅可以使用 `UsernameAuthenticationTokens` 进行身份验证。在将 `Authentication` 强制转换为 `UsernameAuthenticationToken` 并获取用户名和密码后，`authenticate` 删除了存储在令牌中的明文密码以防泄露。它获取 `UserPrincipal` 并运行标准检查。在确认用户身份后，它将已验证标记置为 true 以确认身份验证成功。

```java
@Service
public class DefaultAuthenticationService implements AuthenticationService {
    @Override
    @Transactional
    public UserPrincipal authenticate(Authentication authentication) {
        UsernameAuthenticationToken credentials = (UsernameAuthenticationToken) authentication;
        String username = credentials.getPrincipal().toString();
        String password = credentials.getCredentials().toString();
        credentials.eraseCredentials();
        principal.setAuthenticated(true);
        log.debug("User {} successfully authenticated.", username);

        return principal;
    }

    @Override
    public boolean supports(Class<?> c) {
        return c == UsernameAuthenticationToken.class;
    }
}
```

现在你需要配置 Spring Security 使用该 `AuthenticationProvider`。这在列表 26-1 中的 `SecurityService` 实现类中所示，该类是从 `RootContext` 类导入的。注意，它让 Spring Framework 自动注入 `AuthenticationService` ，并简单地在 `configure(AuthenticationManager)` 方法中进行连接。`configure(WebSecurity)` 方法将静态资源和可能的 favicon 从 Spring 的过滤器链中排除，而 `configure(HttpSecurity)` 要求对所有请求进行身份验证并设置了表单登录和注销机制，与 Authentication-App 中的代码类似。它还有其他一些内容，你也将查看。

# 列表 26-1: SecurityConfiguration.java

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurer {
    @Inject AuthenticationService authenticationService;

    @Bean
    protected SessionRegistry sessionRegistryImpl() {
        return new SessionRegistryImpl();
    }

    @Override
    protected void configure(AuthenticationManagerBuilder builder) throws Exception {
        builder.authenticationProvider(this.authenticationService);
    }

    @Override
    public void configure(WebSecurity security) {
        security.ignoring().antMatchers("/resource/*", "*/favicon.ico");
    }

    @Override
    protected void configure(HttpSecurity security) throws Exception {
        security
            .authorizeRequests()
                .anyRequest().authenticated()
            .and().formLogin()
                .loginUrl("/login").failureUrl("/login?failed")
                .defaultSuccessUrl("/ticket/list")
                .usernameParameter("username")
                .passwordParameter("password")
                .permitAll()
            .and().logout()
                .logoutUrl("/login").logoutSuccessUrl("/login?loggedOut")
                .invalidateSession(true).deleteCookies("JSESSIONID")
                .permitAll()
            .and().sessionManagement()
                .sessionFixation().changeSessionId()
                .maximumSessions(1).maxSessionsPreventsLogin(true)
                .sessionRegistry(this.sessionRegistryImpl)
            .and().csrf()
                .requireCsrfProtectionMatcher(r -> {
                    String m = r.getMethod();
                    return r.getServletPath().startsWith("/services/*") &&
                           ("POST".equals(m) || "PUT".equals(m) || "DELETE".equals(m) || "PATCH".equals(m));
                });
    }
}
```

# 替换 Session Registry

你可能在奇怪为什么列表 26-1 中的 `SecurityConfiguration` 类手动创建了 Spring Security `SessionRegistry` own，然后将其注入到会话管理配置中。如果没有 Spring Security，它会自动创建这个吗？是的，Spring Security 会这样做，但这样做会导致 `SessionRegistry` 不会作为基础暴露给整个应用程序。在书早期，你使用 `SessionListener` 创建了自身的 `com.wrox.site.SessionRegistry`（`SessionListener` 和 `HttpSessionListener` 的一种实现）。Spring 的 `SessionRegistry` 可以完全替换此功能。通过手动创建 `SessionRegistryImpl`，你将该 bean 暴露给你的应用程序，你可以在 Spring 类之外的其他应用程序中使用它。`SessionListController` 现在使用 Spring 的 `SessionRegistry` 而不是旧的 `com.wrox.SessionRegistry`。

```java
@Controller
@RequestMapping("session")
public class SessionListController {

    @Inject SessionRegistry sessionRegistry;

    @RequestMapping(value = "list", method = RequestMethod.GET)
    public String list(Map<String, Object> model) {
        List<Session> sessions = new ArrayList<>();
        for(Object principal : this.sessionRegistry.getAllPrincipals()) {
            sessions.addAll(this.sessionRegistry.getAllSessions(principal, true));
        }
        model.put("timestamp", System.currentTimeMillis());
        model.put("numberOfSessions", sessions.size());
        return "session/list";
    }
}
```

使用 Spring Framework 的发布/订阅消息机制，Spring Security 在认证事件发生时会提供各种消息。这些不同的事件在 API 文档中均有记录，但对你最有用的事件包括：

- `org.springframework.security.authentication.event.AbstractAuthenticationFailureEvent`，当认证因某些原因失败时发布。其子类包含了失败的更详细原因。

- `org.springframework.security.authentication.event.AuthenticationSuccessEvent`，当认证成功时发布。然而，这可能也包含交互式认证事件，请使用 `org.springframework.security.authentication.event.InteractiveAuthenticationSuccessEvent`。

- `org.springframework.security.web.authentication.SessionFixationProtectionEvent`，当会话固定保护导致会话更改时（例如，会话迁移或 `changeSessionId`）发布。

列表 26-1 中的 `requireCsrfProtectionMatcher` 覆盖了 CSRF 保护的默认匹配器，将 Web 服务排除在 CSRF 保护之外。

> 注意：虽然 lambda 表达式确实很有帮助，但当你必须定义新匹配器时，列表 26-1 中的 CSRF 配置充其量是拙劣的。在第 28 章，你将学习在为 Web 服务添加认证和授权时配置此项内容的更好方法。

# 表单安全

在根据需求配置了 CSRF 保护后，你如何保护你的表单呢？嗯，在某种程度上，你什么都不需要做。只要你通过 `@EnableWebSecurity` 配置了 Spring Security，在任何使用 `<form>` 标签且动词为 POST、PUT、PATCH 或 DELETE 的地方，Spring Security 都会自动添加一个隐藏的 CSRF 令牌。如果你仍然想在登录视图中使用 `<form>` 标签——那么 CSRF 保护就会自动发生。（如果你只通过 `@EnableWebSecurity` 配置了 Spring Security，则你必须创建一个类型 `org.springframework.security.web.csrf.CsrfRequestTokenRepository` 的 bean 来启用此功能。）Spring 会自动为任何匹配所需匹配器的请求查找 CSRF 令牌。

你必须采取额外步骤添加 CSRF 保护的唯一情况是：当你使用标准的 HTML `<form>` 而不是 Spring 的 `<form>`、当你通过 JavaScript 提交表单以及向服务器进行 Ajax 调用时。在这些情况下，你有责任向表单或请求添加 CSRF 字段或标头。Spring Security 也通过在你所有的 JSP 视图中注册类型为 `org.springframework.security.web.csrf.CsrfToken` 的 EL 变量来使这变得简单。你只需要使用令牌属性将正确的值添加到你的表单或 JavaScript 中即可。Customer Support 应用程序中的 `postInvisibleForm` JavaScript 函数启动并合并数据块。对该函数进行简单的微调即可保护该主题中提交表单的任何代码。

```javascript
var postInvisibleForm = function (url, fields) {
    var form = $('<form id="mapForm" method="post"></form>');
    form.append('<action:' + url + ', style="display: none;">');
    for (var key in fields) {
        if (fields.ownProperty(key)) {
            form.append('<input type="hidden">').attr(
                name: ' + key + ', value: ' + fields[key]
            );
        }
    }
    form.append('<input type="hidden">').attr(
        name: '${csrf.parameterName}}', value: '${csrf.token}}'
    );
    $('body').append(form);
    form.submit();
};};
```

在保护表单安全时，你应该知道“最佳实践”是禁用表单的自动补全。这可以保护那些与他人共享电脑的用户，例如在公共图书馆中。进行此更改只需在 `login.jsp` 中的 `<form>`、`<form:input>` 和 `<form:password>` 标签中添加 `autocomplete="off"` 即可。启用 CSRF 保护后，Spring Security 要求注销必须通过 POST 发生。它不会响应通过 GET 的注销请求。这就是为什么 Customer Support 应用程序中的登录链接提交了一个隐藏的表单。

在查看所有这些更改后，编译项目并从 IDE 启动 Tomcat。在应用程序 `http://localhost:8080/support/` 登录，你不应该发现在创建、登录、搜索工单以及与支持人员聊天时有任何区别。从用户的角度来看，应用程序的执行上基本上是相同的；但它现在更安全、更健壮了。你仍然需要处理具有不同权限的用户——这将在下一章介绍。

# Spring Security 3.2 中的 HTTP 安全标头

在过去的几年里，行业专家和工作组提议并采用了多种与安全相关的 HTTP 标头，以指示浏览器启用某些安全机制。这些标头的制定是为了应对不同的漏洞，例如跨站脚本 (XSS) 和点击劫持（User Index Reference）攻击。



# Spring Security 安全标头与授权

## 安全标头

Spring 3.2 添加了自动将这些标头设置为“最佳实践”值的支持，使你的应用程序尽可能安全。通过 CSRF 保护，Spring Security 将这些标头设置为最佳实践值，使你的应用程序尽可能安全。如果你使用 XML 配置，这些标头是默认开启的。如果你使用 Java 配置，则需要确保开启。

- `Cache-Control` 设置为 `no-cache, no-store, max-age=0, must-validate`，`Pragma` 设置为 `no-cache`，告诉客户端和代理服务器不要缓存数据。
- `Content-Type-Options` 设置为 `nosniff`，指示浏览器不要猜测页面的 MIME 类型。
- `Strict-Transport-Security` 设置为 `max-age=31536000; includeSubDomains`，强制始终通过 HTTPS 访问站点及其子域名，防止中间人攻击。
- `Frame-Options` 设置为 `DENY`，防止响应在框架内显示，有助于防止点击劫持攻击。
- `XSS-Protection` 设置为 `1; mode=block`。结果是浏览器检测到包含 XSS 的可疑脚本时会完全禁用而不是只尝试禁用部分。

### XML 配置启用安全标头

要在 XML 配置中启用安全标头，只需在你想要应用的 `<http>` 配置中添加 `<headers />`。

### Java 配置禁用安全标头

若要在 Java 配置中禁用这些标头，可以如下所示：

```java
@Override
protected void configure(HttpSecurity security) throws Exception {
    security
    ...
    .and().headers().disable();
}
```

### 单独控制标头

你也可以单独控制每个标头类型。以下是启用所有（或禁用某些）标头的示例：

```java
@Override
protected void configure(HttpSecurity security) throws Exception {
    security
    .and().headers().cacheControl().contentTypeOptions()
    .frameOptions().httpTransportSecurity()
    .xssProtection();
}
```

## 总结

在本章中，你探索了 Spring Security 的认证。你还学习了 Spring Security 作为全方位解决方案的一些特性，例如通过 CSRF 缓解和 Spring Security 3.2 添加的新 HTTP 标头。你尝试了各种认证机制，并为 Customer Support 应用程序创建了自己的认证程序。最后，你学习了 XML 和 Java 配置选项以及它们之间的区别。

在下一章中，你将完成认证-授权的故事，学习检查用户权限的各种方法并确保只有授权的用户执行安全操作。

# 第 27 章：使用授权标签和注解

本章内容：

- 在代码中检查授权规则
- 声明 URL 和方法安全
- 使用常用和 Spring Security 注解
- 理解授权决策
- 为对象安全创建访问控制列表 (ACL)
- 使用 Spring Security 标签库

## 通过声明进行授权

在第 25 章中，你探索了用于授权的一些不同方法。你可以使用许多技术和手段，认为任何一种方法比其他方法更好是不准确的。这很大程度上取决于你的个人需求、应用程序架构以及你采用身份验证的方法。直觉的方法是将授权代码放置在你的代码中。一种非常常见且被视为最佳实践的技术是通过声明进行授权。在这种技术中，你的代码或配置声明了谁可以做什么，并由安全机制拦截对你代码的访问，以代表你执行这些规则。这种模式与你在书中第三部分探索过的事务模式相似。在本节中，你将探索实现这两种方法的各种方式，并学习 Spring Framework 中提供的约定和工具。

## 在方法代码中检查权限

通常，你的代码需要使用下面的代码来检查用户是否有权执行某操作：

```java
public void doSomeAction(...) {
    if (security.userCanPerformAction("ACTION_1")) {
        // 执行操作的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}
```

然而，这会很快让你的服务类充斥着重复代码。考虑一个管理论坛帖子和回复的服务：

```java
public Post getPost(long id) {
    if (security.userCanPerformAction("READ_POST")) {
        // 返回帖子的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public Page<Post> listPosts(long forumId, Pageable page) {
    if (security.userCanPerformAction("LIST_POSTS")) {
        // 列出帖子的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public void savePost(Post post) {
    if (security.userCanPerformAction("SAVE_POST")) {
        // 保存帖子的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public void deletePost(Post post) {
    if (security.userCanPerformAction("DELETE_POST")) {
        // 删除帖子的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public Reply getReply(long id) {
    if (security.userCanPerformAction("READ_REPLY")) {
        // 返回回复的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public Page<Reply> listReplies(long postId, Pageable pageable) {
    if (security.userCanPerformAction("READ_REPLIES")) {
        // 列出回复的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public void saveReply(Reply reply) {
    if (security.userCanPerformAction("SAVE_REPLY")) {
        // 保存回复的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public void deleteReply(Reply reply) {
    if (security.userCanPerformAction("DELETE_REPLY")) {
        // 删除回复的代码
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}
```

上述类的示例是简化的。它忽略了用户可能被允许查看某些帖子和回复的事实，并且没有考虑到管理员删除他人帖子与删除自己帖子之间的区别。尽管如此，在这些回调和 lambda 表达式中，至少有 24 行代码专门用于检查授权规则，而且代码非常重复。你可以使用回调和 lambda 表达式来消除重复，如下所示：

```java
public Post getPost(long id) {
    return security.doSecured("READ_POST", () -> {
        // 返回帖子的代码
    });
}
```

虽然这确实是一个改进，但你仍然复制了一些代码。这并不是最整洁的方法，因为你所有的服务代码最终都放置在了回调 lambda 表达式中。此外，考虑你将如何对之前的任何代码示例进行单元测试。这并不容易！

## 使用 URL 安全

你已经在第 26 章中探索了声明式安全的一种方法：URL 安全。这涉及声明 URL 模式并定义谁可以访问规则的规则。你已经见过 `permitAll`、`authenticated` 和 `hasAuthority` 规则。虽然你可以避免使用 URL 安全，但它确实让事情变得非常简单。例如，在 Customer 应用中，你使用 URL 安全来声明所有 URL 都需要用户登录，但从规则中排除了登录和注销 URL。`permitAll`、`authenticated` 和 `hasAuthority` 是表达式函数，基本上就是字面意思。你可以选择几个表达式函数：

- `denyAll` 防止所有人访问资源。（它始终评估为 `false`。）如果你需要临时阻止对特定 URL 的访问，这个非常有用，但它没有什么长期价值。
- `permitAll` 是 `denyAll` 的相反。它允许任何人访问资源，无论他们经过了什么验证。（它始终评估为 `true`。）
- `hasAuthority(String)` 如果用户具有作为函数参数的指定权限，则评估为 `true`。
- `hasAnyAuthority(String...)` 允许你指定多个权限，如果用户具有其中一个，则评估为 `true`。
- `hasRole(String)` 是 `hasAuthority` 的同义词，功能相同。使用哪一个取决于个人喜好。如果你想避免基于角色的授权的复杂性，你可能会选择 `hasAuthority`。
- `hasPermission` 是一个特殊的表达式函数，它根据用户角色或权限之外的因素检查用户访问特定资源的权限。例如，它可以检查用户是否可以访问特定的论坛，这可能因论坛不同而异。使用 `hasPermission` 是一个复杂的课题，在访问控制列表章节中会有详细介绍。
- `isAnonymous` 如果用户是匿名身份验证，则评估为 `true`（换句话说，他们没有“登录”）。
- `isRememberMe` 如果用户使用记住我的身份验证，则评估为 `true`。
- `isAuthenticated` 是 `isAnonymous` 的相反——如果用户不是匿名的，则评估为 `true`（换句话说，他们已“登录”）。
- `isFullyAuthenticated` 如果 `isAuthenticated` 为 `true` 且 `isRememberMe` 为 `false`，则评估为 `true`。你可以利用此来缓解记住我身份验证的风险。
- `hasIPAddress(String)` 如果用户请求源于给定的 IP 地址，则评估为 `true`。你也可以指定一个无类域间路由（CIDR）块（例如 `65.128.76.0/24`），如果用户的 IP 地址属于该 IP 地址块，`hasIPAddress` 评估结果为 `true`。
- `getAuthentication` 返回 `Authentication` 对象，你可以使用它来执行更复杂或专门的组合，这些组合的结果为布尔值。

Spring 框架表达式语言（EL 或 SpEL）是支持使用授权函数的动力。本章没有涵盖 SpEL，但它非常简单。它与 Java 统一表达式语言非常相似，你可以学习到关于使用 Spring 表达式的大部分内容。如果你想获取更多信息，可以在 Spring 框架参考文档中找到。

### XML 配置 URL 安全

当使用 XML 配置时，在 `<http>` 内部元素 `<intercept-url>` 中定义 URL 规则。默认情况下，`access` 属性具有 `hasRole` 或 `hasAuthorities`。它仅接受用逗号分隔的 `GrantedAuthority` 列表，用户必须拥有其中之一才能访问匹配的 URL。Spring Security 会按顺序评估 `<intercept-url>` 标签出现的规则，如果你反转这两条规则的顺序，任何人都可以访问 `/admin/` URL。

```xml
<http>
  <intercept-url pattern="/admin/**" access="ADMINISTRATOR" />
  <intercept-url pattern="/**" access="USER" />
  <form-login ...>
  <logout ...>
</http>
```

若要在 `access` 属性中使用表达式功能，你必须在 `<http>` 元素中启用表达式。启用表达式只需将 `use-expressions` 属性设置为 `true`。完成此操作后，你就不能再使用简单的逗号分隔的 `GrantedAuthority` 列表了。你必须使用一个或多个安全函数，并在必要时结合布尔运算符 `and` 或 `or`，以形成一个完整的安全表达式。通过这种语法，你可以为保护应用程序资源定义非常简单且非常复杂的规则。例如，要指定访问管理面板需要完全身份验证（不是“记住我”）、拥有管理员权限并且从内部 IP 地址范围连接，你可以这样配置：

```xml
<http use-expressions="true">
  <intercept-url pattern="/admin/**" access="isFullyAuthenticated() and hasAuthority('ADMINISTRATOR') and hasIPAddress('192.168.0.0/24')" />
  <intercept-url pattern="/**" access="hasAuthority('USER')" />
  <form-login ...>
  <logout ...>
</http>
```

在这种情况下，如果用户使用记住我进行身份验证，他在访问管理面板之前会被要求完全身份验证（“登录”）。如果用户没有 `ADMINISTRATOR` `GrantedAuthority` 或从受禁止的 IP 地址连接，他将收到 403 Forbidden 的 HTTP 错误。当然，你可以使用 `or` 代替 `and`，但那并不合理。那样的话只需要满足条件之一即可允许访问管理面板。

### Java 配置 URL 安全

Java 配置略有不同，因为它仅支持安全表达式。考虑到 Java 配置与 XML 配置之间已经有很大不同，且这些类型的默认设置也不同，这是自然的。当你在 Java 配置中选择 URL 模式（无论使用 `anyRequest`、`antMatchers` 还是 `regexMatchers`）时，返回的对象是 `org.springframework.security.config.annotation.web.ExpressionAuthorizationConfigurer`。通过此对象，你可以调用 `access` 方法来创建一个与你在 XML 配置中创建的相同的复杂 SpEL 表达式，或者使用以安全函数命名的便利方法来创建简单表达式。遵循 Java 配置与之前的 XML 配置相同。（注意，再次强调 URL 方法的顺序很重要。）

```java
@Override
protected void configure(HttpSecurity security) throws Exception {
    security
        .authorizeRequests()
            .antMatchers("/admin/**").access("isAuthenticated() and " +
            "hasAuthority('ADMINISTRATOR') and " +
            "hasIpAddress('192.168.0.0/24')")
            .antMatchers("/**").hasAuthority("USER")
            .and().formLogin();
}
```

> **警告** 尽管 `hasRole` 和 `hasAnyAuthority` 安全函数是相同的，但 Java 配置的便利方法并非如此。`hasRole` 和 `hasAnyRole` 便利方法会在它们传入的权限前面加上 `ROLE_`。如果权限以 `ROLE_` 开头，则是没问题的。在这种情况下，请省略 `ROLE_`，系统会自动为你添加。然而，如果你的权限不以 `ROLE_` 开头，你需要使用 `hasAuthority` 和 `hasAnyAuthority`。



使用 URL 安全配置有其优势。它很容易配置和应用广泛的 URL 集合，表达式非常灵活，如果你使用 XML 配置，你可以在不重新编译应用程序的情况下更改规则。这比在所有应用程序方法中评估安全限制要改进得多。然而，两个显而易见的缺点往往阻碍人们使用此功能：

- 它将授权与 Web 层耦合在一起——如果创建了另一个执行相同任务的用户，忘记为该用户界面定义重复的安全规则，将危及该功能的安全性。
- 它让重构更具风险——如果你的接口发生了变化而授权规则没有变，你的安全可能再次受到破坏。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_820_0.png)

而且，当然，如果你没有 Web 层，这可能不起作用。之前的代码意味着规则统一应用于所有地方。你会发现，最合理的做法是在 UI 上应用一些规则，而在服务层内部应用更精确的规则。

## 使用注解声明权限

那么如何在不实际编写授权代码的情况下在服务内部评估授权规则？你通过 `@Transactional` 处理过类似的需求，Spring 框架确保事务在方法执行前启动，并在方法完成后提交或回滚。你可以应用相同的模式来保护你的服务——使用一个或多个安全相关的注解来声明用户必须拥有的 `GrantedAuthority` 或调用之前必须成功评估的权限。

## 授权常用注解

Java EE 通用注解指定了几个用于此目的的注解。它们位于 `javax.annotation.security` 包中。

- `@DeclareRoles` 提供了一种列出所有角色（或权限、账户等）的方法。
- `@DenyAll` 禁止所有人访问。对方法标记此意味着外部类的无法执行它。对象通常可以执行自己的 `@DenyAll` 方法，因为在这种情况下代理并未激活。如果你使用字节码织入而不是接口或 CGLIB 代理（你在第 24 章学过的），它将不起作用。因此，很少的情况需要使用此注解。如果你在整个类或接口上标记此注解，它将阻止该类所有方法的执行。
- `@PermitAll` 自然是 `@DenyAll` 的相反。它声明任何人都可以执行此方法。但这看起来可能没用，它实际上可能非常有用。为了理解为什么，你必须先理解下一个注解。
- `@RolesAllowed` 可能具有误导性，因为它的名称暗示它只基于角色的授权。记住你在第 25 章学到的：重要的不是你调用它什么，而是你如何使用它。`@RolesAllowed` 指定了用户执行方法时必须具备的一个或多个（权限或 `GrantedAuthority`）。用户不需要拥有所有角色，只需要其中之一。如果指定在类或接口上，此注解适用于该类中的所有方法。然而，如果方法在类注解中也指定了角色，方法的限制将完全覆盖类的限制。此外，如果一个类被标记为 `@RolesAllowed` 而其一个方法被标记为 `@PermitAll`，则任何人都可以执行该方法。

`@RunAs` 指令容器以不同的用户运行该方法。然而，此注解仅在使用了容器提供的身份验证机制的完整 Java EE 容器中才有用。Spring Security 不支持此注解。

使用 `@RolesAllowed` 非常简单。将其添加到任何方法或类（必须是 Spring 管理的 bean）中，并在注解值中指定一个或多个角色。

```java
@RolesAllowed("ADMINISTRATOR")
public interface SettingManager {
    @RolesAllowed("ADD_GENERAL_SETTING", "ALTER_GENERAL_SETTING")
    void saveGeneralSettings(Map<String, Object> settings);

    @RolesAllowed("ALTER_MEMBERSHIP_SETTING")
    void saveMembershipSettings(Map<String, Object> settings);
}
```

如果用户尝试在没有权限的情况下调用方法，将抛出 `org.springframework.security.access.AccessDeniedException`。通常你不需要担心捕获此异常。作为一个 `RuntimeException`，它会导致任何相关的事务回滚并传播，而不会影响你的程序。Spring Security 的过滤器会捕获该异常并向用户返回 403 Forbidden 错误。在少数情况下，你可能需要捕获此异常，但通常这是针对非 Web 应用所需的。

如你所见，`@RolesAllowed` 和 `@PermitAll` 注解可能很有用，但仅此而已。在用 Spring Security 时，使用另外三个注解的意义不大。难道就这些了吗？这些注解虽然有用，但它们完全忽略用户请求方法是为了实现什么。如果这些方法通过相同的格式进入，你无法使用 `@RolesAllowed` 来限制某些论坛帖子而不是所有论坛。Spring Security 提供了一组更健壮的注解来满足你的需求。

## Secured 注解

`org.springframework.security.access.annotation.Secured` 注解是 Spring Security 对声明式安全注解的首次尝试。它在 Java EE 5 发布以及 Common Annotations API 可用之前出现。从实践上讲，`@Secured` 与 `@RolesAllowed` 相同。它接受一个或多个 `GrantedAuthorities`，只有当用户拥有其中至少一个 `GrantedAuthority` 时，用户才能执行被注解的方法。

然而，有一点不同：`@RolesAllowed` 适用于任何值，但 `@Secured` 要求值必须以 `ROLE_` 开头。你指定的任何不以 `ROLE_` 开头的 `GrantedAuthority` 都会被忽略。这是由于访问决策投票者模式中的成员不同导致的，你将在下一节中学习更多内容。如果你不希望所有的权限名称都以 `ROLE_` 开头，你应该避免使用 `@Secured` 而改用 `@RolesAllowed`。与 `@RolesAllowed` 一样，你可以在类或接口上指定 `@Secured` 以影响类或接口中的所有方法，也可以在单个方法上指定，或者两者都指定。在第三种情况下，适用相同的优先级和覆盖规则。

## 第 27 章 使用授权标签和注解

```java
@Secured("ROLE_ADMINISTRATOR")
public interface SettingsAuthenticatorService {
    @Secured("ROLE_ADD_GENERAL_SETTING", "ROLE_ALTER_GENERAL_SETTING")
    void saveGeneralSettings(Map<String, Object> settings);

    @Secured("ROLE_ALTER_MEMBERSHIP_SETTING")
    void saveMembershipSettings(Map<String, Object> settings);
}
```

## 执行前和执行后授权注解

Spring Security 的执行前和执行后授权注解是 Spring Security 现代声明式授权能力的核心。所有位于 `org.springframework.security.access.prepost` 包中的注解都允许你在方法执行之前或之后（或执行前后都）使用你之前读过的表达式。通过 `@RolesAllowed` 和 `@Secured`，你可以在类或接口上、单个方法上或两者都指定这些注解。如果你在方法及其所在的类上指定了相同的前后注解，则方法注解将完全覆盖类注解。

`@PreAuthorize` 是你可能在 Spring Security 中最频繁使用的注解。你在 `@PreAuthorize` 中指定的安全表达式会在方法执行前进行评估，并使用以 `#` 为前缀的参数名进行引用。例如，如果方法有一个名为 `employee` 的参数，你可以通过 `#employee` 访问该参数的值。暴露的 SpEL 变量与其对应的参数具有相同的类型，并且你可以对参数的访问属性调用方法。

```java
@PreAuthorize("isFullyAuthenticated and hasAuthority('USER')")
public interface UserService {
    @PreAuthorize("userId == authentication.principal.userId or " +
    "hasAuthority('CHANGE_OTHER_USER_PASSWORD')")
    void changePassword(long userId, String oldPassword, String newPassword);

    @PreAuthorize("userId == authentication.principal.userId or " +
    "hasAuthority('CHANGE_OTHER_USER_DETAILS')")
    void updateDetails(User user);

    @PreAuthorize("user.userId == 0 and (isAnonymous or " +
    "hasAuthority('CREATE_NEW_USER')")
    void addUser(User user);
}
```

如果表达式求值为 false，则方法将不会被调用并会抛出 `AccessDeniedException`。在这里，你必须小心参数名的解析。在 Java 8 之前，除非你的类在编译时带有调试信息，否则 SpEL 无法发现参数名。这意味着要在生产环境中编译带有调试符号，某些开发者倾向于避免这样做。此外，接口不包含调试信息，因此 Spring Security 无法通过调试符号发现接口方法的参数名。

凭借 Java 8 的新参数名反射功能以及从 Spring Security 3.2 开始，参数名的发现更加可靠。然而，在某些情况下仍然无法工作，你可以配合 `@P` 使用此注解来指定参数名到变量的映射。SpEL 变量与其对应的参数具有相同的类型，并且你可以对参数的访问属性调用方法。

```java
@PreAuthorize("user.userId == 0 and (isAnonymous or " +
"hasAuthority('CREATE_NEW_USER')")
void addUser(User user);
```

> **WARNING** 如果你无法依赖参数名反射，则必须使用 `@P` 前缀。这可以过滤方法返回的值。

## 通过声明进行授权

如你所见，Spring Security 的执行前和执行后授权注解比 Common Annotations API 或 `@Secured` 强大得多。考虑到将 SpEL 作为表达式引擎，使用这些注解几乎没有你做不到的事情。然而，你可能对 `hasPermission` 函数的示例用法感到困惑，因为你还没有学习过它。`hasPermission` 使用了 Spring Security 的访问控制列表（ACL），你将在“对象安全的访问控制列表”章节中学习它。

> **注意** 如果你不想使用 SpEL 表达式而倾向于使用 `@Secured` 和 `@RolesAllowed`，但仍然想获得 `isAnonymous`、`isRememberMe` 和 `isFullyAuthenticated` 安全函数的优势，只需使用特殊权限/角色 `IS_AUTHENTICATED_ANONYMOUSLY`、`IS_AUTHENTICATED_REMEMBERED` 和 `IS_AUTHENTICATED_FULLY`。它们的效果与这些函数相同。

## 使用注解的好处

在看到你基本上可以在某些注解中编写代码后，你可能会疑惑这比在服务方法中编写代码有什么改进。你之前不是没有读到分离业务逻辑的授权逻辑是一个关键目标吗？这难道不是转移了问题吗？记得你之前读过的关于测试服务的内容：使用 `SecurityContext` 并为每个单元测试测试可能的负面用例。在这种方法中使用注解消除了这些需求，因为授权检查仅仅在注解中声明，在你的测试期间永远不会被评估。这允许你专注于测试代码所实现的实际业务逻辑。

另一个重要点是，授权规则是一份合约。当你创建一个 `UserService` 接口时，你是为了建立一个关于所有 `UserService` 实现必须做什么的合约，无论它们如何实现。现在想象一下切换此 `UserService` 的实现。这些实现也会有不同的授权规则吗？不。授权规则不是实现细节。它们是合约的一部分——它们属于接口部分。Spring Security 的注解支持允许你（但并不要求你）在接口中声明这些授权规则，使其成为合约的一部分，并适用于任何实现。这与将授权检查嵌入应用程序代码中相比，是一个巨大的改进。

## 配置注解支持

Spring Security 默认禁用了注解支持。你必须启用注解支持才能使用本节中的任何注解；否则它们将被忽略。要启用注解支持，你首先需要将 `AuthenticationManager` 暴露为一个 bean。因为你可能有多个 Web 安全配置（你将在下一章中学习），`WebSecurityConfigurerAdapter` 默认不暴露 `AuthenticationManager` bean。（否则，可能会有重复的 bean。）通过重写配置适配器的 `authenticationManagerBean()` 方法可以暴露此 bean。

接下来，你需要向你的配置类添加 `@org.springframework.security.config.annotation.method.configuration.EnableGlobalMethodSecurity` 并配置其属性。这三个属性允许你指定想要支持的注解。`jsr250Enabled` 控制 Common Annotations API，而 `securedEnabled` 和 `prePostEnabled` 分别控制 `@Secured` 和执行前/执行后的注解。默认情况下，所有三种类型都是禁用的，因为属性默认为 `false`。以下配置使用第 26 章中创建的 `SecurityConfiguration` 类启用了所有三组的支持：

```java
@Configuration
@EnableWebMvcSecurity
@EnableGlobalMethodSecurity(
    jsr250Enabled = true, prePostEnabled = true
)
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Bean
    @Override
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManagerBean();
    }
}
```

在大多数情况下，你可能不想启用所有三个注解。事实上，混合这些组可能会导致意想不到的结果，这可能不是你的预期。你应该从三个注解组中选择一组并贯穿整个应用程序。在本书的最后两个章节中，你将专门使用执行前和执行后注解。

你还需要注意代理的顺序。你应该从第三部分记得，当你在 RootContext 中添加 `@EnableTransactionManagement` 时，所有包装代理的 Spring Framework 特性必须以相同的方式配置，并进行恰当的排序。如果你在其中一个使用了 `AdviceMode.PROXY`，你应该在所有项上都这样做。如果你在某处将 `proxyTargetClass` 设置为 `false`，`@EnableAsync`、`@EnableTransactionManagement` 和 `@EnableGlobalMethodSecurity` 提供了 `mode`、`proxyTargetClass` 和 `order` 属性来控制这些功能（如果它配置了包装代理的代理）。你应该使用与用于 `@EnableAsync` 和 `@EnableTransactionManagement` 相同的 `mode` 和 `proxyTargetClass` 值。通常情况下，Spring Security 代理应该在相同方法的任何其他代理之前执行。最重要的是，它应该始终在异步执行代理和事务管理代理之前执行。

```java
@Configuration
@EnableWebMvcSecurity
@EnableGlobalMethodSecurity(
    prePostEnabled = true, order = 0,
    mode = AdviceMode.PROXY, proxyTargetClass = false
)
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
}
```

之前的代码与以下 XML 配置可比：



# 理解授权决策

简单来说，理解这一决策过程也有助于你排除那些与你的意图或愿望不符的行为。最后，如果你决定从 Spring Security 的默认设置切换到 Spring 提供的替代设置，那么掌握 Spring Security 的访问决策机制至关重要。本节涵盖了决策过程以及支持该过程的接口和实现。

# 使用访问决策投票者 (Access Decision Voters)

访问决策投票者（Access Decision Voters）是决策过程中的关键参与者。一个典型的 Spring 配置包含多个投票者，它们是 `org.springframework.security.access.AccessDecisionVoter` 的实现。就像政府机构的成员对是否通过某项立法投票一样，访问决策投票者对是否允许访问应用程序的某些部分投票。当询问某个投票者关于是否应该授予访问的意见时，它会根据给定的特定知识进行投票。如果信息不足以做出明智投票（例如，某些其他功能不知道保护资源的唯一特征），它将从方法返回 `AccessDecisionVoter.ABSTAIN` 以避免投票。如果信息足够且应该授予访问，它将返回 `AccessDecisionVoter.ACCESS_GRANTED`。同样，如果它认为不应该授予访问，它会返回 `AccessDecisionVoter.ACCESS_DENIED`。

提供了多种 `AccessDecisionVoter` 实现，Spring Security 会根据你启用和禁用的安全特性为你配置合适的实现。你的应用程序可能只使用一个，也可能使用多个 `AccessDecisionVoters`。以下列出了实现：

- `org.springframework.security.acl.AclEntryVoter` 根据 Spring Security 的访问控制列表（ACL）进行投票。如果资源使用 `hasPermission` 表达式函数进行保护，`AclEntryVoter` 将放弃投票。此投票者不会自动配置，事实上，你可能永远都不会使用它。你有方法来配置访问控制列表，我们将在下一节中进行探讨。

- `org.springframework.security.access.vote.AuthenticatedVoter` 针对如 `IS_AUTHENTICATED_ANONYMOUS` 和 `IS_AUTHENTICATED_FULL` 等特殊角色起作用。如果不是受任何这些角色的保护，`AuthenticatedVoter` 将放弃投票。

- `org.springframework.security.access.annotation.Jsr250Voter` 对任何使用通用注解 API (JSR 250) 保护的方法进行投票。例如，如果方法标记了 `@RolesAllowed` 注解，`Jsr250Voter` 将根据该注解指定的权限投票。只有在你启用对 JSR 250 注解的支持时，此投票者才会被启用。启用后，仅当方法（或其类或接口）存在 JSR 250 注解时才会投票。如果不存在注解，或者访问决策针对非方法资源（如 URL），则此投票者将放弃投票。

- `org.springframework.security.access.prepost.PreInvocAuthorizationAdviceVoter` 根据 `@PreAuthorize` 和 `@PreFilter` 注解进行投票。只有在启用执行前和执行后访问控制时，它才被启用。对于非方法资源或当方法（或其类或接口）不存在注解时，它将放弃投票。`@PostFilter` 和 `@PostAuthorize` 没有对应的投票者——Spring 将这些注解视为特殊情况，因为投票者是在资源访问之前使用的。

- `org.springframework.security.access.vote.RoleHierarchyVoter` 使用 Spring 的角色层级系统做出决策。如果你启用了角色层级限制但受保护的资源不存在该限制，你必须手动创建它。本书没有详细介绍该层级系统的使用，因为通常不建议使用基于角色的授权（第 25 章）。`org.springframework.security.access.vote.RoleVoter` 用于受非表达式 URL 限制保护的资源、方法点表达式以及 `@Secured` 注解以及所有其他情况。它投出一个或多个以 `ROLE-` 前缀开头的“角色”（这就是为什么你在 `@Secured` 中仅使用 `ROLE-` 前缀的成员）。如果你启用了 `@Secured` 注解、如果你在 XML `<http>` 配置元素中将 `use-expressions` 设置为 `false`，或者你使用了方法点表达式，则此投票者会被启用。

- `org.springframework.security.web...` 对保护 URL 资源的表达式做出决策。它获取方法保护的决策，并在没有保护特定 URL 的表达式的情况下获取决策。如果你使用 Java 配置或在 XML `<http>` 配置元素中将 `use-expressions` 设置为 `true`，则它会被启用。

这种“赞成”、“否决”或“抽象”的投票模式在控制访问的技术中非常常见。几乎所有的防火墙系统都有评估为“接受”、“拒绝”或“中立”的投票者。如果你记得第 17 章中的 Log4j2 过滤器，你知道它们也使用了类似的模式。这是一种极其灵活的架构，支持所有可能的规则。

# 使用决策管理器 (Decision Managers)

如你所见，有多个内置的投票者，并且可能同时启用多个投票者。事实上，多个投票者对特定的访问决策可能有非抽象的意见。Spring Security 如何协调这些差异？访问决策管理器（Access Decision Managers）负责协调一个或多个投票者的票数，并将它们转换为对访问请求命运的最终决定。

继续使用治理机构的类比，实现 `org.springframework.security.access.AccessDecisionManager` 的决策管理器就像首相或治理机构的议长。它统计票数，并决定是否满足了授予访问的适当规则。归根结底，决策管理器是决定是否抛出 `AccessDeniedException` 的组件。

你的应用程序可能同时配置了多个决策管理器。如果你启用了全局方法安全，这将创建一个用于访问受保护方法的决策管理器。此决策器可以使用上述大多数投票者。例如，在你的 HTTP 配置中配置 URL 限制会创建另一个用于控制应用程序 URL 访问的决策管理器。

Spring Security 自带三个标准的 `AccessDecisionManager` 实现；然而，你可以轻松创建自己的。你可以将这些实现用于方法安全、URL 安全或任何其他调用管理器的场景。默认情况下，当所有投票者都抽象时访问会被拒绝，但在这种情况下，每个标准实现都提供设置来访问。

# 赞成决策 (Deciding by Affirmation)

`org.springframework.security.access.vote.AffirmativeBased` 是最简单的决策管理器。如果至少有一个非抽象投票者同意，该决策管理器授予访问。即使其他投票者拒绝，此决策管理器仍然允许访问。你可能看到这种模式在某些情况下存在问题，但在大多数情况下它是完全足够的。你通常不会有两个 URL 限制匹配，但如果确实如此，允许至少一个允许通常没有问题。这同样适用于方法限制。

# 共识决策 (Deciding by Consensus)

共识决策可能是你最熟悉的类型。所有的共和和民主政府形式都基于共识原则运行，即简单多数或治理机构的三分二同意。`org.springframework.security.access.vote.ConsensusBased` 按简单多数原则运行。如果超过半数的非抽象投票者赞成访问，则授予访问。

例如，如果你有 7 个投票者，4 个投票者抽象，2 个投票者赞成访问，1 个投票者拒绝，则授予访问。然而，如果 1 个投票者赞成，2 个投票者拒绝，则拒绝访问。当然，如果你遇到平局问题（即赞成和拒绝的票数相同），`ConsensusBased` 决策管理器提供了设置来决定平局策略。默认情况下，在平局时授予访问。

# 一致决策 (Deciding by Unanimity)

决策框架管理器的自然结论是要求所有非抽象投票者都投赞成票——`org.springframework.security.access.vote.UnanimousBased`。所有非抽象投票者都必须投票授予访问；否则此决策管理器将拒绝访问。这是一个非常严格的策略，但尽管如此在某些情况下是合适的。

为全局方法安全配置不同的 `AccessDecisionManager` 非常简单。如果你的 `@Configuration` 类没有扩展 `GlobalMethodSecurityConfiguration`，请修改。只需重写 `accessDecisionManager` 方法以返回 `ConsensusBased` 或某些自定义实现。无论你决定返回什么管理器，都不要忘记其中包含投票者。为 Web 安全配置不同的决策管理器很容易：只需将其添加到 `configure(HttpSecurity http)` 方法中。

```java
@Override
protected void configure(HttpSecurity security) throws Exception {
    authorizeRequests()
        .accessDecisionManager(new CustomDecisionManager());
}
```

# 为对象安全创建访问控制列表

到目前，本章介绍了一种相对简单的授权方法，在该方法中，只有用户的权限或其是否“拥有”某个资源就能决定对该资源的访问。这种方法在某些情况下非常适用。简单的应用程序，尤其是用户输入极少的应用程序，通常只在少数授权规则运行。即使是像用户论坛这样看似复杂的应用程序，在授权方面其实也很简单。然而，有时你可能需要复杂的解决方案。

访问控制列表（ACL）是一种更复杂的对象安全方法，它定义了针对每个用户、每个对象的权限。对于给定的对象类型 `Foo`，`Bar` 可能对它的不同实例具有完全不同的权限。这超出了所有权的概念：一个用户可能管理某些实例，写入另一些，删除另一些，最后完全不访问其他一些。操作系统文件（如 Microsoft Windows 和 Apple Mac OS X 中的文件）是基于 ACL 的。Linux 操作系统也支持 ACL 权限；但默认情况下它们并未启用，且许多 Linux 用户并不熟悉它们。

## 理解 Spring Security ACL

如果你曾经在 Windows、Mac OS X 或带有 ACL 权限的 Linux 中管理过权限，你就会非常熟悉 ACL 的工作原理。你文件系统上的每个文件都有一组权限，对于任何给定的文件，你可以为访问该文件系统的每个用户定义不同的权限。

你可以想象，一个支持这种特性的系统并非易事。除了复杂的权限管理机制外，系统还需要大量的后端数据来存储这些权限。如果你想象一个拥有一百万个用户、一百万条数据记录的应用程序，那么你可能需要万亿条记录来仅仅记录用户对这一个对象的权限！无论你存储这些数据的效率有多高，你面对的仍然是 TB 级的数据。虽然理解这是一种极端情况（大多数用户只对每份数据的一小部分具有访问权限），但你可以看到设计这样一个系统是多么重要。

Spring Security 自带了一个成熟且经过行业测试的 ACL 系统，提供对对用户权限的细粒度控制。该系统的核心组件是 `org.springframework.security.acls.model.Acl` 接口。它代表单个对象的访问控制列表，每个域对象都恰好有一个 ACL。它泛泛地以 `org.springframework.security.acls.model.ObjectIdentity` 的形式封装了域对象的 ID。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_833_0.png)

域对象所有者（创建它的用户）的 ID 以 `org.springframework.security.acls.model.Sid` 的形式表示，分配给每个允许以某种方式使用该对象的用户的权限列表则以 `org.springframework.security.acls.model.AccessControlEntry` 的 `List` 表示。

每个 `AccessControlEntry` 封装了持有该条目的用户 ID 以及分配给该条目的 `org.springframework.security.acls.model.Permission`。权限用位掩码（bitmasks）表示——这是一种高效的存储机制，数字的每一位控制一种权限。例如，位 1 可能控制读取权限，而位 2 控制写入权限。一个 Acl 还可以包含一个父 ACL，并从中继承该父 ACL 的 `AccessControlEntries`。

> 注意：位掩码对于经验丰富的开发者来说可能是一件可怕的事。这种技术也用于标准的 Unix 文件权限以及许多其他应用程序和系统活动。请放心，Spring Security 抽象了位掩码的困扰：你永远不需要直接处理它。标准的 Spring 实现 `org.springframework.security.domain.BasePermission` 理解读取、创建、删除和管理权限，这对于大多数用例已经足够。如果你需要支持其他权限，必须实现自己的 `Permission` 类，并告诉它为你的实现转换位掩码。



`org.springframework.security.acls.domain.PrincipalSid` 有两种标准实现，前者对应 `Authentication`，而 `org.springframework.security.acls.domain.GrantedAuthoritySid` 对应 `GrantedAuthority`。如果你使用 `GrantedAuthority` 来表示角色和组组，并想要向特定角色或组组中的所有人授予权限，后者就会很有用。对于这两种实现，SID 最终都用 `Authentication` 或 `GrantedAuthority` 的字符串（用户名或权限名称）表示。如果你想用长用户 ID 来表示这些，可以轻松地实现自己的 `Sid`。

ACL 系统由 `org.springframework.security.acl.model.Service` 的实现驱动。该服务可以按对象加载 ACL 以供权限评估。它使你能够使用 `hasPermission` 表达式来控制对方法的访问——使用 `AclService` 为给定的域对象调用 ACL。

如果你愿意，可以实现自己的 `AclService`，但不推荐这样做。Spring Security 的 `org.springframework.security.acl.jdbc.JdbcAclService` 设计用于将 ACL 高效存储在关系型数据库中，并以高性能的方式检索它们。`spring-acl` 的 JAR 节点包含了为 MySQL/MariaDB (`createAclSchemaMys.sql`)、PostgreSQL (`createAclSchemaPostgres.sql`) 和 HSQLDB (`createAclSchema.sql`) 创建必要表的 SQL 脚本。如果你决定使用不同的数据库，可以轻松地翻译这些脚本之一。由于 `JdbcAclService` 使用标准的 SQL 特性进行数据操作，它应该与几乎任何关系型数据库兼容。

四个 ACL 表承担以下功能：

- `acl_sid`：唯一定义系统中的 Sid，用于与其他表的引用完整性。通常你只使用 `PrincipalSid` 或类似项，系统中的每个用户在该表中都有一条记录。
- `acl_class`：唯一定义应用程序中的每个域类。与 `acl_sid` 一样，此表用于引用完整性。
- `acl_object_identity`：对应 ACL 类并持有 `ObjectIdentity`、所有者 Sid 以及其他 ACL 属性。系统中每个受 ACL 保护的域在该表中都有一条记录。
- `acl_entry`：映射到每个 ACL 的 `AccessControlEntry` 列表。

> **警告**：`acl_entry` 表具有增长到数十亿甚至万亿条记录的潜力，这取决于应用程序中域对象的数量、持久化实例的数量以及系统中的用户数量。你应该始终监控此表的性能问题，并根据情况调整索引、系统属性或硬件。

## 配置访问控制列表

如果你打算实现自己的 ACL 系统，其配置方式在很大程度上取决于你的设计。你要么需要实现一个 `AclService` 并修改 `DefaultSecurityExpressionHandler` 为其提供一个使用该服务的 `AclPermissionEvaluator`，要么定义自己的 `PermissionEvaluator`。

配置 Spring 的 ACL 实现相当复杂，但只要设置得当，它就能为你完成大部分工作。你将从在应用程序中创建 Spring Security ACL 方法并定义一个用于全局方法安全的内部 `@Configuration` 类开始。

## 为对象安全创建访问控制列表 (ACL)

> **注意**：`spring-security-acl` Maven 构件是你应用程序中所包含的其他 Spring Security 构件的运行时依赖。但是，如果你打算使用 ACL，你应该将此依赖设置为编译时依赖。

```xml
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-acl</artifactId>
  <version>3.2.0.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

你需要配置 `org.springframework.security.acls.domain.DomainAuthorizationStrategy` 的实现类。ACL 系统使用它来确定当前主体（principal）是否有权限访问 ACL 服务的管理功能（例如更改特定对象的 ACL）。标准实现允许：如果主体是该对象的所有者、拥有该对象的管理权限，或者在策略构造函数中具有任何授权列表，则允许其使用这些管理方法。

```java
@Bean
public AclAuthorizationStrategy aclAuthorizationStrategy() {
    return new AclAuthorizationStrategyImpl(
        new SimpleGrantedAuthority("ADMIN"));
}
```

接下来，你需要配置一个 `org.springframework.security.acls.model.PermissionGrantingStrategy`。该接口允许你自定义权限的评估方式，但标准实现通常足够了。我们需要一个 `org.springframework.security.acls.domain.AuditLogger` 来记录 ACL 授权事件。如下代码所示配置，使用 lambda 表达式提供日志行为。你可以采取许多不同的方法，例如使用默认的 `org.springframework.security.acls.domain.ConsoleAuditLogger` 将日志输出到标准输出。

```java
@Bean
public PermissionGrantingStrategy permissionGrantingStrategy() {
    return new DefaultPermissionGrantingStrategy((granted, entry) -> {
        if (!granted) {
            log.info("Access denied for {}", entry);
        }
    });
}
```

现在，你需要设置一个 `org.springframework.security.acls.model.AclCache` 实现。为了优化性能，ACL 系统需要在下次使用这些条目时进行缓存。Spring Security 带有相应的 AclCache 实现类，可以使用 Ehcache（一种流行的 Java 开源分式缓存系统）或 Spring Framework 的缓存系统。为了演示目的，基于 `java.util.concurrent.HashMap` 的 Spring Framework 缓存就足够了。如果你有集群化的应用程序，则必须提供适当分布式缓存实现。

## 802 | 第 27 章 使用授权标签和注解

```java
@Bean
public AclCache aclCache() {
    return new SpringCacheBasedAclCache("Security-*",
        this.permissionGrantingStrategy(),
        this.aclAuthorizationStrategy());
}
```

配置完这些基础系统后，你需要设置 JDBC ACL 实现并添加 `PermissionEvaluator`。`JdbcAclService` 和 `org.springframework.security.acls.jdbc.BasicLookupStrategy` 共同工作，使用你的应用程序 DataSource 高效检索 ACL 条目，并在适当的时候将其缓存。`AclPermissionEvaluator` 和 `org.springframework.security.acls.AclPermissionCacheOptimizer` 共同工作以评估 `hasPermission` 表达式。

```java
@Bean
@Inject DataSource dataSource;
public BasicLookupStrategy lookupStrategy() {
    return new BasicLookupStrategy(
        this.dataSource,
        this.aclCache(),
        this.aclAuthorizationStrategy(),
        this.permissionGrantingStrategy());
}
```

```java
@Bean
public AclService aclService() {
    return new JdbcAclService(this.dataSource, this.lookupStrategy());
}
```

```java
@Override
public MethodSecurityExpressionHandler createExpressionHandler() {
    DefaultMethodSecurityExpressionHandler handler = new DefaultMethodSecurityExpressionHandler();
    handler.setPermissionEvaluator(new AclPermissionEvaluator(this.aclService()));
    handler.setPermissionCacheOptimizer(new AclPermissionCacheOptimizer(this.aclService()));
    return handler;
}
```

最后你可以在方法上添加 `hasPermission` 表达式来根据 ACL 权限限制访问。大部分情况下，整个配置由简单的 bean 组成，你应该非常熟悉如何使用 XML 配置这些组件。如果你使用 XML 配置，需要为 `DefaultMethodSecurityExpressionHandler` 配置评估器和优化器，并使用 Spring Security 空间将其分配给全局方法安全：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/security"
       xmlns:beans="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/security http://www.springframework.org/schema/security/spring-security-3.2.xsd
                           http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-4.0.xsd">

    <global-method-security pre-post-annotations="enabled" order="0"
          proxy-target-class="false">
        <expression-handler ref="expressionHandler" />
    </global-method-security>
</beans>
```

## 为实体填充 ACL

到目前为止你已经知道如何使用 ACL，但你还需要为你的实体填充 ACL。你还需要为你的实体填充 ACL。Spring Security 不会自动完成这一点。每当你创建一个实体时，必须手动填充它的所有者。你可以通过调用 `MutableAcl` 的 `setOwner` 方法来更改这一点。为了实现这一点，你必须先使用 `JdbcAclService`。它会更新现有的 ACL，如果不存在则插入新的 ACL。或者，你可以使用接受 `Class<?>` 和 `Serializable` ID 的 `ObjectIdentityImpl` 构造函数。

```java
ObjectIdentityImpl identity = new ObjectIdentityImpl(forumPost);

MutableAcl acl;
try {
    acl = (MutableAcl)this.mutableclService.readById(identity);
} catch (NotFoundException e) {
    acl = this.mutableclService.createAcl(identity);
}

Authentication otherUser = userService.getUser("OtherUserName");
PrincipalSid sid = new PrincipalSid(otherUser);
acl.insert(acl.getEntries(), length, BasePermission.READ, sid, true);
acl.insert(acl.getEntries(), length, BasePermission.WRITE, sid, true);
this.mutableclService.updateAcl(acl);
```

这并不是最佳实践，所以如果可以，你应该避免这样做。相反，惯例是提供一个 `UserDetailsService` 实现，并在必要时提供自定义的 `UserDetails`。

## 决定 User Details 的实现

在设计系统时，你最终需要决定是否将用于持久化的用户对象与用于身份验证和授权的用户对象耦合。

将它们分离的优势在于，你不需要（甚至不想）在安全上下文中携带一个可变的用户对象，而保持它们分离可以确保这一准则。然而，将它们合并为同一个对象的优势是，你不需要花费太多精力就能将用户实体嵌入到其他实体中。最终，你可以决定最适合你的路径。

为了简单起见，`Customer Support` 应用将 `UserDetails` 实现和实体合并在同一个对象中。对 `UserPrincipal` 的更改非常简单。它实现了 `UserDetails` 而不是 `Authentication`，并且实现了 `org.springframework.security.core.CredentialsContainer`，这样 Spring 在身份验证完成后会清除密码。



```java
public class UserPrincipal implements UserDetails, CredentialsContainer, Cloneable {
    private static final long serialVersionUID = 1L;

    private String id;
    private String username;
    private byte[] hashedPassword;
    private Set<UserAuthority> authorities = new HashSet<>();
    private boolean accountNonExpired;
    private boolean accountNotLocked;
    private boolean credentialsNonExpired;
    private boolean enabled;

    // userid and username properties
    @Basic(fetch = FetchType.LAZY)
    @Column(name = "HashedPassword")
    public byte[] getHashedPassword() { ... }
    public void setHashedPassword(byte[] password) { ... }

    @Transient
    @Override
    public String getPassword() {
        return this.getHashedPassword() == null ? null :
            new String(this.getHashedPassword(), StandardCharsets.UTF_8);
    }

    @Override
    public void eraseCredentials() {
        this.hashedPassword = null;
    }

    @Override
    @ElementCollection(fetch = FetchType.LAZY)
    @CollectionTable(name = "UserPrincipal_Authority", joinColumns = {
        @JoinColumn(name = "UserId", referencedColumnName = "UserId")
    })
    public Set<UserAuthority> getAuthorities() { ... }
    public void setAuthorities(Set<UserAuthority> authorities) { ... }

    @Override
    @XmlElement @JsonProperty()
    public boolean isAccountNonExpired() { ... }
    public void setAccountNonExpired(boolean accountNonExpired) { ... }

    @Override
    @XmlElement @JsonProperty()
    public boolean isAccountNonLocked() { ... }
    public void setAccountNonLocked(boolean accountNonLocked) { ... }

    @Override
    public boolean isCredentialsNonExpired() { ... }
    public void setCredentialsNonExpired(boolean credentialsNonExpired) { ... }

    @Override
    @XmlElement @JsonProperty()
    public boolean isEnabled() { ... }
    public void setEnabled(boolean enabled) { ... }
}
```

当然，这需要在 `UserPrincipal` 表中添加一些额外的列。如果你是第一次运行 `Customer Support` 应用，请使用应用程序中 `create.sql` 中的 SQL 脚本来创建你所有需要的表和索引。否则，请使用以下代码添加必要的列。

```sql
USE CustomersSupport;
ALTER TABLE UserPrincipal
ADD COLUMN AccountNonExpired BOOLEAN NOT NULL DEFAULT TRUE,
ADD COLUMN AccountNonLocked BOOLEAN NOT NULL DEFAULT TRUE,
ADD COLUMN CredentialsNonExpired BOOLEAN NOT NULL DEFAULT TRUE,
ADD COLUMN Enabled BOOLEAN NOT NULL DEFAULT TRUE;
ALTER TABLE UserPrincipal
MODIFY COLUMN AccountNonExpired BOOLEAN NOT NULL,
MODIFY COLUMN AccountNonLocked BOOLEAN NOT NULL,
MODIFY COLUMN CredentialsNonExpired BOOLEAN NOT NULL,
MODIFY COLUMN Enabled BOOLEAN NOT NULL;
```

`UserAuthority` 类非常简单：它是一个实现了 `GrantedAuthority` 的嵌入 POJO。`UserPrincipal` 中的 `@CollectionTable` 将 `UserAuthority` 映射到 `UserPrincipal_Authority` 表。

```java
@Embeddable
public class UserAuthority implements GrantedAuthority
{
    private String authority;

    public UserAuthority() { }
    public UserAuthority(String authority) {
      this.authority = authority;
    }

    @Override
    public String getAuthority() { ... }

    public void setAuthority(String authority) {

    }
}
```

```sql
CREATE TABLE UserPrincipal_Authority (
  UserId BIGINT UNSIGNED NOT NULL,
  Authority VARCHAR(100) NOT NULL,
  UNIQUE KEY UserPrincipal_Authority_User_Authority(UserId, Authority),
  CONSTRAINT UserPrincipal_Authority_User_Id FOREIGN KEY (UserId)
  REFERENCES UserPrincipal(UserId) ON DELETE CASCADE
) ENGINE = InnoDB;
```

## 使用新的数据实体

旧的 `Authentication` 不再需要处理身份验证。相反，它扩展了 `Details`，因此将其重命名为 `UserService`（及其实现重命名为 `DefaultUserService`）是合理的。

```java
@Validated
public interface UserService extends UserDetails {

  @Override
  UserPrincipal loadByUsername(String username);
}
```

```java
@Service
public class DefaultUserService implements UserService {

  @Override
  @Transactional
  public UserPrincipal loadByUsername(String username) {

    UserPrincipal principal = userRepository.getByUsername(username);
    // 确保加载了权限和密码
    principal.getAuthorities().size();
    principal.getPassword();
    return principal;
  }
}
```

安全配置需要稍微调整一下。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Inject
    UserService userService;

    @Override
    protected void configure(AuthenticationManager builder) throws Exception {
        builder
            .userDetailsService(userService)
            .and()
            .passwordEncoder(new BCryptPasswordEncoder());
    }
}
```

## 保护服务方法

在第 26 章中，你已经在控制器上使用了 `@Authorize`。现在你需要保护服务方法，以便某些用户可以执行任务。首先，你必须启用全局方法安全。

```java
@Configuration
@EnableWebMvcSecurity
@EnableGlobalMethodSecurity(
    prePostEnabled = true, order = 0, mode = AdviceMode.PROXY,
    proxyTargetClass = false
)
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Bean
    @Override
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManagerBean();
    }
}
```

> **注意** 全局方法的顺序设置为 0。此外，异步方法执行的代理顺序为 1，而事务支持的代理顺序为 2。这确保了安全首先运行，然后是异步方法执行，最后是事务操作。

保护 `TicketService` 非常直接。可以使用 `@PreAuthorize` 和简单的表达式保护所有方法，由于你只想编辑自己的订单和评论（除非拥有管理员权限），你必须将 `Tickets` 和 `TicketComments` 拆分创建和更新方法。`TicketController`、`TicketRestEndpoint` 和 `TicketSoapEndpoint` 必须根据更改的方法名进行更新（此处未显示）。注意使用 `@P` 来指示 Spring 表达式的参数名。

```java
public interface TicketService {
    @NotNull
    @PreAuthorize("hasAuthority('VIEW_TICKET')")
    List<Ticket> getAllTickets();
    @NotNull
    @PreAuthorize("hasAuthority('VIEW_TICKET')")
    Page<SearchResult<Ticket>> search(...);
    @PreAuthorize("hasAuthority('VIEW_TICKET')")
    Ticket getTicket(id);
    @PreAuthorize("#id == 0 && hasAuthority('CREATE_TICKET')")
    void create(@NotNull @Valid(#ticket) Ticket ticket);
    @PreAuthorize("authentication.principal.equals(#{ticket.customer}) or " + "hasAuthority('EDIT_OWN_TICKET') or hasAuthority('EDIT_ANY_TICKET')")
    void update(@NotNull @Valid(#ticket) Ticket ticket);
    @PreAuthorize("hasAuthority('DELETE_TICKET')")
    void delete(id);
}
```

## 810 | 第 27 章 使用授权标签和注解

你需要保护聊天请求，这引入了一些复杂性。在这里，你不仅要检查用户是否有权执行该任务，还要检查他们在他们发送消息或离开会话时是否确实是该会话的成员。



```java
public interface ChatService {

    @PreAuthorize("authentication.principal.username.equals(#user) and hasAuthority('CREATE_REQUEST')")
    CreateResult createChat(@user String user);

    @PreAuthorize("authentication.principal.username.equals(#user) and hasAuthority('START_CHAT')")
    JoinResult joinSession(long id, @user String user);

    @PreAuthorize("authentication.principal.username.equals(#customerUsername) and #user.equals(#session.representativeUsername) and hasAuthority('CHAT')")
    ChatMessage leaveSession(@session ChatSession session);

    @PreAuthorize("authentication.principal.username.equals(#message.user) and (#message.equals(#session.customerUsername) or #message.equals(#session.representativeUsername)) and hasAuthority('CHAT')")
    void logMessage(@session ChatSession session, @message ChatMessage message);

    @PreAuthorize("hasAuthority('VIEW_CHAT_REQUESTS')")
    List<ChatSession> getPendingSessions();
}
```

然而，你必须考虑其他事情。目前，Spring Security 还没有处理 WebSocket 会话的支持。这是 Spring Security 4.0 计划中的功能，预计将在 2014 年中期发布。该版本应该会为你处理许多工作，例如在会话中携带 Principal，以及在 HttpSession 登销时关闭 WebSocket 会话。事实上，它可以消除你应用程序中的大量的代码。但目前，你必须自行采取一些特殊步骤。当 WebSocket 会话被移交并且你开始异步通信时，Security Context 会清空。为了补偿这一点，你必须创建一个方法来处理加密操作。

```java
private void doSecured(SecuredAction secureAction) {
    SecurityContext.setContext(this.securityContext);
    try {
        secureAction.execute();
    } finally {
        SecurityContext.clearContext();
    }
}
```

```java
@FunctionalInterface
private static interface SecuredAction {
    void execute();
}
```

```java
public static class EndpointConfigurator extends EndpointConfigurator {
    @Override
    public void modifyHandshake(ServerHandshake config, HandshakeRequest request, HandshakeResponse response) {
        config.getUserProperties().put(SECURITY_CONTEXT_KEY, SecurityContextHolder.getContext());
    }
}
```

然后你必须确保所有的 `@OnOpen`、`@OnClose`、`@OnMessage` 和 `@OnError` 方法（以及 WebSocket 容器可能调用的其他方法）都在加密操作内执行。例如，这里是 `@OnError` 方法：

```java
@OnError
public void onError(Throwable e) {
    this.doSecured(() -> {
        log.warn("Error received in WebSocket session.", e);
    });
    synchronized(this) {
        if(this.closed) {
            // ... 逻辑继续
        }
    }
    return;
    this.close(ChatService.ReasonForLeaving.ERROR, "error.chat.closed.exception");
}
```

你最后需要考虑的是会话列表。这是一个管理功能，但该服务（Spring 的 `SessionRegistry`）不受你控制，因此你无法向该服务添加安全注解。对于这一点，你将需要回退到 `SecurityConfiguration` 中标准的 URL 安全规则。

```java
@Override
protected void configure(HttpSecurity security)
```

（注：由于原文后半部分存在大量重复和截断的占位符，翻译已根据提供的逻辑对结构进行了对齐，并保持了代码块的完整性。）

所有的 Spring Security 标签都提供了类似 `<security:authorize>` 和 `<security:accesscontrolist>` 标签的属性；指定的变量包含评估规则的布尔结果。如果你使用了属性，则该标签不能嵌套。对于其他标签，`var` 将存储在指定的变量中。`WEB-INF/jsp/view/chart.list.jsp` 展示了如何使用 `<security:authorize>` 的 `var` 属性，如果用户没有 `START_CHAT` 权限，则从列表中省略链接。

```xml
<security:authorize access="hasAuthority('START_CHAT')" var="${canjoin}">
<spring:message code="message,chatlist.instruction"/>:<br /> <br />
<c:forEach items="${sessions}" var="s">
<c:choose>
<c:when test="${canjoin}">
<a>${s.customerUsername}</a><br />
</c:when>
<c:otherwise>${s.customerUsername}</c:otherwise>
</c:choose>
</c:forEach>
```

完成这些更改后，客户支持应用程序已准备就绪。继续编译它，为你的 IDE 启动 Tomcat，并访问 `http://localhost:8080/support`。以不同用户登录，并通过列出和创建工单、列出会话以及参与聊天会话来测试授权系统是否正常工作。如果你愿意，可以设置系统属性 `security.disableUIS`，这会禁用 `<security:authorize>` 标签，使其内容始终被渲染，从而更容易尝试对资源进行未经授权的访问，并确保方法安全正常运行。

> 注意：如果你以前从未运行过客户支持应用程序，或者忘记了用户名和密码，请查阅 `create.sql` 脚本。每个用户的 INSERT 语句都包含一个带有该用户明文密码的 SQL 注释。

### 总结

在本章中，你学习了许多关于在 Spring Security 中授权用户的知识。你探索了 URL 安全和全局方法安全，以及许多不同的方法安全注解及其使用方法。你学习了 Spring Security 如何做出访问决策以及投票者如何贡献这些决策，还了解了 Spring Security 强大的访问控制列表（ACL）系统。最后，你为跨国制品公司的客户支持应用程序添加了授权功能。你将 `UserPrincipal` 从 `Authentication` 转换为 `UserDetails`，配置了方法安全，使用安全标签库添加了用户界面安全，并采取特殊步骤在 WebSocket 端点中维护 `SecurityContext`。

完成客户支持应用程序仅剩最后一件事：你仍然有一些未安全且功能不完全 Web 服务端点。在书的下一也是最后一章中，你将学习 Web 安全和 OAuth，并将 Spring Security OAuth 集成到客户支持应用程序中。

# 第 28 章 使用 OAuth 保护 RESTful Web 服务

本章内容

- 理解 Web 服务安全
- OAuth 简介
- OAuth 1.0a 和 2.0 的比较
- 在 Spring Security 中使用 OAuth
- 完成客户支持应用程序
- 编写 OAuth 客户端应用程序

本章的 WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/projavaforwebapps` 的 Download Code 选项卡中找到本章的 wrox.com 代码下载。本章代码分为以下示例：

- Customer-Support-v21 项目
- OAuth-Client 项目

本章的新 MAVEN 依赖

除了在之前的章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework.security.oauth</groupId>
  <artifactId>spring-security-oauth2</artifactId>
  <version>1.0.5.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

```xml
<dependency>
  <groupId>commons-codec</groupId>
  <artifactId>commons-codec</artifactId>
  <version>1.9</version>
  <scope>runtime</scope>
</dependency>
```

```xml
<dependency>
  <groupId>org.apache.httpcomponents</groupId>
  <artifactId>httpclient</artifactId>
  <version>4.3.1</version>
  <scope>runtime</scope>
</dependency>
```

## 理解 Web 服务安全

在第四部分到目前为止，你已经探索了与 Web 服务安全相关的概念技术。在本章中，你将学习保护 Web 服务的各种方法。

### 比较 Web 和服务安全

保护 Web 服务与保护 GUI 不同。当你保护 GUI 时，你是在保护用户界面本身。当你保护 Web 服务时，你是在保护 API。客户端可能是人类，也可能是另一个 Web 服务。这意味着你必须考虑一组不同的威胁和漏洞。

例如，GUI 容易受到跨站脚本攻击（XSS）的影响。而 Web 服务则容易受到中间人（MITM）攻击。为了防止这些威胁，你需要使用不同的安全机制。为了防止 XSS，你可以使用输入验证和输出编码。为了防止 MITM 攻击，你可以使用 SSL/TLS。

在本章中，我们将探索保护 Web 服务的几种方法。我们将查看基础身份验证、摘要身份验证和 OAuth。我们还将讨论如何在 Spring Security 中实现这些机制。

3. 你做了一项实际上让你的用户更安全，但让他们感到更不安全的更改。这是一件坏事。如果用户因为感到不安全而停止使用你的网站，那么提高安全性也无济于事。你几乎总是可以通过更好的公关方法来避免这种困境。

4. 你做了一项实际上让你的用户变得不安全，而且让他们感到不安全的更改。这非常糟糕。不要让你的用户变得不安全。然而，如果你的用户决定感到不安全，他们就会停止使用你的网站，只有你才会承担后果。

5. 你做了一项实际上让你的用户变得不安全，但让他们感觉一样，甚至更安全的更改。是的，这实际上比第 4 点更糟糕。你可能在短期内获益，事实上你可能永远不会被发现。但很有可能你的用户最终会承担后果，当他们发现自己被骗了，他们可能会向你索要赔偿。

显然，你希望设计一个身份验证和授权系统，让每个功能都达到结果 1。因为这只在完美世界中才可能，你现实的目标是坚持结果 1 和 2，并尽可能让许多功能产生结果 1。如果你的安全功能包含导致结果 3、4 或 5 的功能，你必须后退并重新评估你的方法。

回到用户直接通过你的应用程序进行身份验证并向客户端返回断言令牌的想法，这种方法并非没有缺点。

- 你面临令牌被盗窃的风险。这种风险与凭据被盗窃的风险没有本质区别。事实上，如果你更换令牌，可以使事情更安全，因为用户通常不愿意频繁更改密码。
- 你面临着令牌伪造的问题。你可以简单地缓解这个问题（你将在下一节中学习到这一点）。

尽管有这些缺点，令牌是一种非常安全且有效的方法，也是整个行业用于保护 Web 服务的常用方法。像往常一样，重造轮子的意义不大，已经有可用工具可以在 Web 服务应用程序中集成强大的安全性。其中一个你在本章中将使用的工具就是 OAuth。

## 介绍 OAuth

OAuth 是一种开放的授权标准，由 Twitter 的 Blaine Cook、Magnolia 的 Larry Halfle、曾任职于 Google 及其他几家公司的开源倡导者 Chris Messina，以及来自 Facebook 的开源倡导者 David Recordon 创立。你可能已经在疑惑为什么要用“身份验证”（authentication）一词来描述 OAuth。难道你们不是在寻找身份验证的解决方案吗？不，你已经有解决方案了！事实上，你有很多解决方案！基础（Basic）、摘要（digest）、表单（form）、Windows、智能卡——列表长得很。

你不需要一种建立用户身份的新方法；你已经是这方面的专家了。你真正需要的是一种在请求上继续使用该身份验证的方法，以确保用户授权访问 Web 服务。这无疑强调了划分身份验证与授权之间界限的模糊地带。两者关系密切，并相互依赖。在某种程度上，你甚至可以将身份验证视为授权的形式。至少，身份验证始终是授权的第一步。需要说明的是，OAuth 是一种授权标准，但它与身份验证紧密相关。

> 警告 本书不是任何版本 OAuth 的权威指南。OAuth 的细节和细微差别无法在一个章节中涵盖。本章帮助你从一个简单的 OAuth 系统开始，但在阅读规范和支持文档之前，你不应该将 OAuth 部署到生产环境中。你可以在这里分别找到关于 OAuth 1.0a、OAuth 2.0 和 OAuth 2.0 Bearer Tokens 的 IETF 标准。

### 介绍核心角色

所有版本的 OAuth 都有官方术语，用于识别身份验证和授权过程中的关键角色。了解这些术语并理解每个角色在 OAuth 会话中发挥的作用至关重要。这些术语在文中经常使用，且没有经过进一步说明，因此请确保在继续之前已清楚理解。

- **客户端**（client）是任何可以使用 OAuth 向 Web 服务 API 发起请求的 HTTP 应用程序。它可以是 JavaScript 应用程序、浏览器插件、桌面应用程序、移动应用程序或你想到的任何其他。重要的是，客户端不是与你的应用程序进行身份验证的用户或人。
- **受保护资源**（protected resource）简单来说是你应用程序中受保护免受未经授权访问的资源。它只能通过 OAuth 验证的请求进行访问。
- **资源所有者**（resource owner）是被授权访问这些受保护资源的实体。资源所有者可能是一个组织、个人或另一个应用程序——通常来说，就是你想到的对象。资源所有者使用客户端连接到你的应用程序并检索或操作受保护资源。

### 起始：OAuth 1.0

OAuth 起始于几位创始人为各自的组织实现 OpenID。例如，Larry Halfle 正在尝试一种方法，让 OpenID 用户将他们的 Mac OS X Dashboard 小部件连接到 Magnolia 的服务。经过简短协商，创始人们确定没有适用于 Web 服务 API 的开放授权标准，OAuth 诞生了。

创始人们于 2007 年 4 月成立了一个开放标准讨论小组，并开始制定 OAuth 标准。它经历了多次修订，在此期间 Eran Hammer 加入了讨论。2007 年 10 月，小组发布了 OAuth Core 1.0 最终草稿。2009 年，发现 OAuth 1.0 容易受到某种会话固定攻击（session fixation attack）。这种攻击的细节超出了本书的范围，但你可以在 Eran Hammer 的博客上阅读它们。由于这个原因，你应该认为 OAuth 1.0 草稿是不安全的，不应该使用它。

### 标准：OAuth 1.0a



# 互联网工程任务组（IETF）与 OAuth 1.0a

互联网工程任务组（IETF）于 2008 年会，讨论了将 OAuth 1.0 草稿作为工作标准。OAuth 赢得了广泛的社区支持，IETF 小组对此工作了近 2 年。它于 2010 年 4 月作为互联网标准 RFC 5849 公式批准并发布。正式地，它是 OAuth 1.0 Revision A，并包含了对 OAuth 1.0 中识别的会话固定攻击的修复。它通常被称为 OAuth 1a，被认为是一种授权协议。（就本书而言，这意味着它描述了实现必须如何行为。）本节概述了 OAuth 1a 如何运作，包括为了缓解会话漏洞所做的更改。

# 理解 OAuth 1.0a 术语

标准定义了几个 OAuth 特有的术语。服务器（server）是你，或者说是你的应用程序。客户端向服务器发送请求并假设自己已授权，服务器向客户端返回响应。服务器的通用概念负责身份验证和授权服务，并托管你的受保护资源。凭据（Credentials）是能够建立身份的值对。该对由一个标识符（如用户名或公钥）和一个密钥（如密码或私钥）组成。在 OAuth 1a 中，有三种凭据。

- 客户端凭据（Client credentials）验证发起请求的客户端（记住：不是用户）。客户端凭据很重要，因为它们允许你限制哪些应用程序代表你的用户访问 Web 服务。

- 临时凭据（Temporary credentials）正如其名，是临时的，并在身份验证过程中用于连接所有步骤。

- 令牌凭据（Token credentials）由身份验证服务返回给客户端，客户端使用它授权资源所有者的所有请求。令牌（token）就像用户名，唯一的标识符（有时是完全随机的字符串，有时更有意义）。在资源所有者身份验证后，服务器向客户端发放令牌。令牌结合共享密钥形成令牌凭据，令牌将请求与经过验证的资源所有者关联。

# 使用 OAuth 1.0a 进行身份验证和授权

OAuth 验证请求的流程非常直观，即使这个概念看起来很困惑。图表使其更容易理解，因此本节有几个。使用客户端访问受保护资源时，以下三者中恰好有一个是：

> 注意：图 28-1 到 21-3 将在本章稍后的部分进行讨论，并伴有更多关于图中所示内容的讨论。在处理此列表时，请参考这些图。

- 客户端没有该资源所有者的令牌凭据，无法访问受保护资源（见图 28-1）。

- 客户端拥有该资源所有者的有效令牌凭据，可以访问受保护资源（图 28-2）。

- 客户端拥有资源所有者的过期或已撤销的令牌凭据，无法访问受保护资源（图 28-3）。

每种情况会导致不同的操作，最终获得对受保护资源的访问权限（假设允许此类访问）。在客户端没有资源令牌凭据的情况下，首先（对资源者透明）向临时凭据请求端点发送空 HTTP 请求（客户端已知道该 URL）。此请求使用 `Authorization: OAuth` 头和几个授权头协议参数来向服务器验证客户端的身份。

- `realm` 指定最终访问的应用程序或资源名称，就像标准的基础认证或摘要认证一样。

- `oauth_consumer_key` 包含客户端凭据中的标识符（客户端提前从服务器获取）。

- `oauth_signature_method` 是正在采用的签名机制。

- `oauth_timestamp` 是发送请求的时间戳，自 Unix 纪元以来的秒。

- `oauth_nonce` 是请求的唯一标识符，永不重复（以防止重放攻击）。

- `oauth_callback` 是客户端完成身份验证并授予访问后，服务器应返回给客户端的 URI。

- `oauth_signature` 是使用所有这些参数、请求各个部分以及客户端凭据中的密钥计算出的签名。

> 注意：明确的是，`Authorization` 头只是客户端可能用于传输协议参数的某种方法。当请求为 `x-www-form-urlencoded` 时（较不推荐），它也可能使用实体参数，以及使用请求 URL 参数（最不推荐）。使用 `Authorization` 头是首选机制，因为代理的行为更好，且不会缓存此类请求。

密钥绝不会在请求中传输——客户端在生成签名时不需要它。签名始终是 `HMAC-SHA1`（对称，使用密钥或多个密钥作为盐）或 `RSA-SHA1`（非对称，使用私钥生成签名）。由于服务器也知道对称密钥，它可以计算出如果客户端使用了正确的密钥，签名应该是什么，并确保签名与预期值匹配。对于非对称签名，服务器可以使用匹配的公钥验证由私钥生成的签名。

无论何种情况，只要签名有效，就会授予权限，服务器允许客户端继续授权。如果请求包含任何不支持的参数或协议版本，服务器返回 `400 Bad Request`；如果签名验证失败、凭据无效、令牌过期或通知无效或已使用，则返回 `401 Unauthorized`。此时，服务器向客户端返回一个 `x-www-form-urlencoded` 格式的 `200 OK`，在响应正文中包含临时凭据。`oauth_token` 响应参数包含临时临时标识符，而 `oauth_token_secret` 包含临时密钥。由于密钥以明文包含在响应中，标准要求此请求响应必须通过 TLS 进行（例如 HTTPS）。`oauth_callback_confirmed` 是第三个必需的响应参数，与协议的旧版本不同。它的值必须始终为 `true`。如图 28-1 中的步骤 1 到 2 所示。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_857_0.png)

图 28-1

# OAuth 823

现在客户端有了临时凭据，它可以在请求参数中使用临时 `oauth_token` 将资源所有者重定向到服务器的资源所有授权端点（步骤 3 和 4）。这是服务器接管身份验证过程的地方。如果资源所有者已经通过验证（例如服务器上当前的 HTTP 会话），服务器将直接跳转到授权屏幕。（尽管为了增强安全性，服务器可能会要求资源所有者进行验证）。否则，它要求资源所有者通过正常手段进行身份验证（步骤 5，可能是表单认证、基础认证、摘要认证、Windows 等以此此类推）。

资源所有者成功身份验证后，服务器告诉资源所有者客户端想要访问哪些受保护资源，并请求授予访问权限。如果资源所有者批准（步骤 6），服务器将资源所有者重定向到客户端的回调 URL。重定向需要临时 `oauth_token` 和一个带有随机字符串值的一次次性 `oauth_verifier` 参数（步骤 7 和 8）。`oauth_verifier` 缓解了上述的会话固定攻击。

> 注意：你可能会奇怪为什么称为 callback URI 而不是 callback URL。callback URI 可能不是标准的 Web URL。如果客户端应用程序是桌面或移动应用程序而不是 Web 应用程序，那么 Web URL 即可用。callback URI 可能是浏览器或操作系统使用的应用程序专用协议。当浏览器看到此 URI 时，它就可以打开目标应用程序并按照先约定的方式将请求参数传递给它。

例如，`nicholas@example.com` 打开一个客户端向 `nicholas@example.org` 发送消息。更现实的情况是，`fb://notifications` 打开 Facebook 应用程序进入通知列表，而 `twitter://timeline` 打开 Twitter 应用程序进入时间线。总的来说，应用程序操作必须向某些权威机构注册其 URI。

当客户端接收到回调重定向时，它向令牌端点发送 POST 请求（步骤 9）。此请求包含 `Authorization: OAuth` 头（显然，时间戳和 nonce 是不同的）。它还包含了不再需要的 `oauth_token` 和 `verifier` 参数。此请求使用临时密钥进行签名。服务器验证客户端身份，验证授权已批准，返回 `oauth_token_secret` 响应参数。此时，服务器使临时凭据失效，使其不再能被使用（步骤 10）。

这看起来似乎是一个复杂且漫长的过程，但在几秒钟内即可完成。重要的是，该策略强烈要求所有通信使用 TLS，因为密钥以明文包含在响应中。

当客户端拥有令牌凭据时，它可以访问受保护资源（无论资源所有者是否存在）。每个对受保护资源的请求都包含 `Authorization: OAuth` 头，带有临时凭据的 `oauth_token` 和 `verifier` 参数。这些请求都使用客户端凭据密钥和令牌密钥进行签名。服务器在允许访问受保护资源之前验证令牌和签名是否有效，如图 28-2 所示。

| 使用有效令牌凭据的请求 | 受保护资源 |
|---|---|
| 客户端 | 响应 |

图 28-2

令牌凭据可能会失效但不是永久的。服务器定期过期令牌凭据，或者资源所有者可能会撤销凭据（例如，资源所有者决定不再让客户端访问其数据）。当这种情况发生时，服务器将对下一个受保护资源请求返回 `401 Unauthorized`。客户端可以重新开始获取临时凭据、授权资源所有者并再次交换临时凭据获取令牌的过程。如图 28-3 所示。

| 使用过期/撤销令牌凭据的请求 | 受保护资源 |
|---|---|
| 客户端 | |
| 401 Unauthorized, Location: https://... | |
| 步骤 1: POST 客户端凭据 | 临时凭据请求端点 |
| 客户端 | | 步骤 2: 临时凭据 |

正常流程继续

图 28-3

1.0 是一个非常安全的协议，但它并非没有缺陷。首先，OAuth 起初在请求部分的出现顺序上经历过一些歧义。

# 介绍 OAuth 2.0

在签名中。例如，在列出需要签名的 URL、方法、请求头和参数时，最初并不清楚请求参数应该以什么顺序排列。这导致了不同的实现使用了不同的排序，从而导致了实现之间的不兼容性。从那时起，规范进行了澄清，规定出现在签名中的请求参数应采用确定性的顺序，但仍然存在一些遗留实现。

OAuth 1.0a 因其通用的签名要求而遭了严厉批评。行业内的一些人员对对的几乎每个部分进行签名感到不安。虽然这种技术确保了请求和响应不被篡改，但其能提供的安全性可以通过 TLS 更容易、更有效地实现。相反，许多签名应该只包含 `Authorization` 头中的参数。这对于足够实现最终目标，即证明客户端持有正确的密钥，而无需保护传输信道或引入不必要的复杂性。

另一个常见的投诉是，OAuth 1.0a 就其字面描述本质上假设资源所有者是一个人，且客户端是不可信的。OAuth 1.0a 的第一个流程忽略了两个重要的用例：

- 客户端应用程序本身也是资源所有者，因此可以仅通过客户端凭据进行身份验证。

- 客户端应用程序是由服务器相同的组织创建的。这意味着资源所有者信任客户端应用程序，并愿意直接信任客户端中的身份凭据，从而提供更好的用户体验。

出于这个原因，许多实现为 OAuth 1.0a 协议创建了扩展，以更好地支持这两个用例。例如，你可以使用 Spring Security OAuth 而无需资源所有者（转而将客户端视为资源所有者）。在这种方法中，每个请求始终包含客户端标识，并使用客户端凭据进行签名。这种技术被称为双角 OAuth（Two-Legged OAuth，与之相对，标准的非正式名称是三角 OAuth Three-Legged OAuth），并且在实现中被广泛支持。这使得这些实现与规范略有些冲突，仅当你以某种方式配置它们时。默认情况下，它们仍然应该符合标准（即三角 OAuth）。

> 注意：在阅读 OAuth 1.0a 后，你可能会认为它是一个非常强大的协议。事实上，令牌凭据非常像 HTTP Session ID（尽管存在一些安全差异）。但 REST Web 服务的目的不就是提供无状态架构吗？确实，OAuth 的有状态性与 REST 的无状态形成了鲜明对比。但是，真的，你无法避免这一点（至少无法以安全的方式避免）。为了实现真正的无状态，客户端必须在每个请求中发送资源所有者的凭据（类似于之前讨论的 basic 和 digest 方法）。这远不如不可信的第三方客户端那样安全，而且资源所有者不会容忍这种缺乏信任。一个安全的身份验证和授权系统需要有状态的协议。

# 演进：OAuth 2.0

OAuth 1.a 出版的墨水还未干，IETF OAuth 工作组就开始开发 OAuth 2.0。其最终草案于 2012 年 10 月作为建议标准 RFC 6749 发布。在互联网标准跟踪机制中，建议标准（Proposed Standard）是标准的入门级。在经过足够的反馈和修订后，标准最终从建议标准移动到草案标准（Draft Standard）。在草案标准阶段，很少进行更改，但仍可能进行修订以解决标准问题。第三也是最后的迭代是互联网标准（Internet Standard），意味着该标准已被采纳并准备广泛使用。

截至 2013 年 10 月，OAuth 2.0 仍然是一个建议标准。RFC 2026 说，这意味着它不适用于“对中断敏感的环境”（意味着不要在生产环境中使用）。尽管如此，它在整个行业被广泛采用，许多提供商（如 Facebook 和 Twitter）要求使用 OAuth 2.0。

OAuth 2.0 是 OAuth 1.a 的继替者，它不向后兼容。OAuth 1.a 客户端无法使用 OAuth 2.0 服务器（OAuth 2.0 客户端也无法使用 OAuth 1.a 服务器），实现允许同时支持这两个标准。重要的是，OAuth 2.0 并不是一个协议；相反，它是一个描述协议可能如何（但并非要求）实现的框架。这一直是许多争议的来源，将在本节后面介绍。

# 使用 OAuth 2.0 术语

与 OAuth 1.a 一样，OAuth 2.0 定义了自己的一些术语。OAuth 2.0 承认资源和身份验证/授权系统并不总是位于同一服务器上，因此 OAuth 1.a 中的服务器在 OAuth 2.0 中被分为*资源服务器*（resource server）和*授权服务器*（authorization server）。

凭据（Credentials）则是完全另一回事。通常情况下，你有某种形式的客户端凭据，但临时和令牌凭据没有被直接处理。根据所选择的授权授予（authorization grant），可能存在类似的概念，或者你可以为 OAuth 2.0 添加扩展以包含不同的凭据类型。

# 理解授权授予（Authorization Grants）

OAuth 2.0 的关键特性之一，也可以说是它的优势之一，是它考虑了 Web API 授权的各种用例。不再假设资源所有者与客户端是分离的，且所有客户端都是不可信的。标准定义了四种内置授权授予类型，以及使用每种类型进行身份验证和授权的过程，并允许你通过扩展添加额外的授予类型。所有授予类型都遵循图 28-4 所示的基本流程，尽管每种类型在获取授权授予的具体方式上有所不同。

与 OAuth 1.a 一样，当客户端向授权服务器发送直接（后台）请求时，客户端使用客户端身份与授权服务器（但不与资源服务器）交互。无论选择哪种授予类型，这都会发生。所有客户端都有客户端标识。客户端可能拥有完成客户端凭据的密钥。授权服务器必须区分*机密客户端*（confidential clients，即被认为可以保留其密钥的客户端）和*公共客户端*（public clients，即无法持有密钥的客户端，例如随应用程序分发的密钥）。

授权服务器不能仅依赖客户端凭据来建立公共客户端的身份。客户端使用 HTTP Basic 认证与授权服务器交互。这是提供者强制支持的客户端认证机制，尽管它们可能支持其他机制。

![](img/9c2d45f6d547f2cb870b3a991f2ef6_862_0.png)

授权码授予是角 OAuth。客户端将资源所有者重定向到授权服务器端以获取访问令牌，并包含请求参数 `response_type`（授予类型设置为“code”）、`client_id`（来自客户端凭据）、`redirect_uri`（授权后的重定向 URI）、`scope`（可选令牌，用于限制访问）和 `state`（防止 CSRF 攻击的推荐参数）。

当资源所有者在授权服务器完成授权和授予阶段时，服务器将资源所有者重定向到重定向端（如 OAuth 所示），在 `code` 响应参数中包含授权码，并在 `state` 参数中包含来自请求 `state` 参数的相同值（如果已提供）。该授权码是从后台 POST 回到授权服务器令牌端点的授权授予，并将授权码交换为访问令牌。访问令牌的请求包含请求参数 `grant_type`（授予类型设置为“authorization_code”）、`code`（刚收到的授权码）、`redirect_uri`（原始 `redirect_uri` 参数值）和 `client_id`。响应为 JSON 格式，包含根节点值 `access_token`、`token_type`（例如 bearer）、`expires_in`（以秒为单位的值）、`refresh_token`（可选，如果启用了刷新令牌）以及任何其他请求参数的回显。

此令牌的性质实际上并没有在框架中定义。相反，应用程序开发者可以选择几种扩展（或创建自己的扩展）来决定访问令牌的外观、存储位置、如何派生以及何时过期。在此实现，客户端

token 被用于访问资源服务器上的受保护资源。访问令牌的使用方式（例如请求参数或 Authorization 头部）也未定义，具体取决于所选择的访问令牌类型。

隐式授权（Implicit Grants）与授权码授权（Authorization Code Grants）非常相似，在功能上仍然等同于三方交互的 OAuth 1.0a，尽管安全性明显较低。在隐式授权中，资源所有者仍然信任授权服务器对客户端进行身份验证并授予访问权限。此请求与授权码授权几乎完全相同，只是 `response_type` 被设置为 "token"。然而，回调中不包含用于交换访问令牌的授权码。相反，回调中直接包含访问令牌（从而移除了图 28-4 流程中的中间步骤）。参数包括 `access_token`、`token_type`、`expires_in`、`scope` 和 `state`。（此授权类型禁止使用刷新令牌）。由于客户端已拥有了访问令牌，因此无需向令牌端点（token endpoint）请求令牌。

你可能会指出这种授权类型中显而易见的安全漏洞，正因如此，你所使用的标准仅在非常有限的情况下适用。例如，浏览器应用程序可能不会受到此类授权类型通常暴露的问题的影响。由于大多数应用程序是用 JavaScript 编写的，授权码授权可能会引入性能影响，而不会对安全性产生严重影响。尽管如此，但不建议使用隐式授权。



# 客户端凭据授权（Client Credentials Grant）

客户端凭据授权（Client Credentials Grant）如图 28-5 所示，在功能上等同于双方交互的 OAuth 1.0a，并已最终在标准中法化。客户端连接到令牌端点并将其凭据交换为访问令牌。请求包含一个设置为 `"client_credentials"` 的 `grant_type` 以及可选的 `scope` 参数。客户端通过通常的基础身份认证（basic authentication）过程进行身份验证。响应包含常用的 `access_token`、`token_type` 和 `expires_in` JSON 值。（此授权类型禁止使用刷新令牌。）通过这种方式，客户端充当了自身的资源所有者，客户端凭据即为图 28-4 中提到的授权许可。客户端可以使用访问令牌代表其自身访问资源服务器上的受保护资源，而不是代表其他资源所有者。

| 步骤 1: POST 客户端凭据 | |
| :--- | :--- |
| 客户端 | 授权服务器 |
| 步骤 2: 访问令牌 + 可选刷新令牌 | |
| 带有访问令牌的后续请求 | 资源服务器 |
| 响应: 受保护资源 | |

图 28-5

# 资源所有者密码凭据授权（Resource Owner Password Credentials Grant）

资源所有者密码凭据授权（Resource Owner Password Credentials Grant）如图 28-6 所示，既是最用户友的也可能是最不安全的授权类型。使用这种授权类型，资源所有者直接将其凭据（用户名、密码、私钥等）提供给客户端，而永远不需要重定向到授权端点。这就是图 28-4 中提到的资源所有者凭据。然后客户端代表资源所有者将这些凭据转发到令牌端点，并将其交换为访问令牌。

此时请求的 `grant_type` 参数设置为 `"password"`，且请求还包含 `username`、`password` 和 `scope` 参数。用户名和密码是资源所有者凭据的通用参数，实际上并不包含真实的用户名和密码。JSON 响应与授权码类型相同。同样，返回的访问令牌可以用于访问资源服务器上的受保护资源。

在处理桌面和移动应用程序时，这种授权无疑提供了最好的用户体验。资源所有者不需要为了身份验证而在应用程序和浏览器之间来切换（有时是频繁切换），只需留在单个应用程序中。当然，这有一个明显的安全影响，即资源所有者必须将未加密且不安全的凭据交给客户端应用程序。正因如此，最佳实践是仅当创建应用程序的组织也是托管授权服务器的组织时，才使用这种授权类型。这是客户端可以完全信任资源所有者凭据的情况之一。绝不要允许第三方客户端使用资源所有者密码凭据。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_864_0.png)

图 28-6

> **注意**：你可能注意到 OAuth 2.0 中没有临时凭据请求端点的替代方案。这是因为 OAuth 2.0 使用临时凭据，并且在重定向客户端到授权服务器之前不会发送获取临时凭据的请求。尽管这在某种程度上简化了流程，但也可以被视为一种漏洞。正因如此，你应该始终使用 `state` 参数来帮助防御这可能带来的某些问题。

# 使用持有者令牌 (Bearer Tokens)

你可能注意到，你没有读到任何关于 `Authorization` 头部格式以及从资源服务器传递给它的参数的说明。这是因为根本没有规定！更准确地说，OAuth 2.0 标准并没有强制要求这些。相反，这些格式和参数完全取决于你选择哪种类型的令牌。然而，标准且推荐的令牌实现是持有者令牌（bearer tokens）。持有者令牌在 RFC 6750（也作为提议）中规定，它们完全就是服务器所持有的东西。谁持有令牌，谁就拥有授权。这与 HTTP 会话 ID 令牌相同，听起来可能与 OAuth 1.0a 令牌凭据相似，但实际上它非常不同（而且可能非常不安全）。

回想 OAuth 1.0a 令牌凭据包含两个部分：身份（令牌）和密钥（secret）。相反，客户端使用密钥生成一个服务器可以复制或验证的签名。正确的令牌和有效签名的存在建立了授权。持有者令牌不使用签名。事实上，标准规定该框架是一个可选部分。如果持有者令牌被泄露，则没有方法可以撤销它。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_865_0.png)

图 28-7

持有者令牌不是 OAuth 2.0 遇到的唯一争议。许多开放标准社区的一个争议点是标准缺乏任何链接“约束力”。几乎每个功能都是可选的，或者在实现中存在例外，允许跳过它。事实上，标准在第 1.8 节中特别提到（本文已加强调）：

> OAuth 2.0 提供了一个具有良好安全属性的丰富授权框架。然而，作为一个丰富且高度可扩展的、具有许多可选组件的框架，这可能会产生一系列不可互操作的实现。

到 2012 年，许多社区成员甚至一些工作小组认为他们已经受够了。Ethan Hammer 从几乎一开始就开始参与了 OAuth，他从标准中删除了自己作为主编辑的名字，并退出了工作小组。他写了一系列博客文章并举办了一系列演讲，严厉地批评了工作小组的过程和 OAuth 2.0 标准的结果。特别引人关注的是，他声称 OAuth 标准是有意地为企业设计的，使其非常模糊，以至于参与其中的企业可以出售实施该标准的咨询服务。David Recordon 退出了工作组并将其名字从标准中移除，尽管他尚未公开说明这一决定。尽管有这些成员离开，OAuth 2.0 提议标准已于 2012 年 10 月发布，而且在解决这些主要问题之前，它很可能成为互联网标准。

# 使用 MAC 作为持有者令牌的替代方案

OAuth 工作组的几个成员以及其他社区成员提出了持有者令牌（bearer tokens）扩展的替代方案，该方案将为 OAuth 2.0 增加大量安全性，并消除许多当前的担忧（例如互操作性问题）。消息认证码（MAC）令牌扩展指定了一种不同类型的令牌，该令牌使用消息签名来证明客户端持有密钥，而无需在链上传输密钥。尽管这与推荐的持有者令牌扩展相比是一项重大的改进——而且，可以说，能够创建这样的扩展本身就是对 OAuth 2.0 设计的巨大测试——但该提议不太可能没有缺陷。

尽管该提议的预定路线是标准轨道（Standards Track），但目前它只是一个互联网草案（Internet Draft）。它没有建议标准（Proposed Standard），也没有分配 RFC 编号。截至本文，当前草案是版本 4，于 2014 年 1 月 16 日过期。届时，该草案可能会作为另一个草案版本移动建议标准，或者被遗弃。如果未被采用，可能需要几年才能成为互联网标准，这对于许多组织来说是一个没有吸引力的解决方案。

# 你应该使用哪个版本的 OAuth？

那么用哪个版本呢？这取决于你。使用和不使用每个版本的理由如下：OAuth 1.0a 更稳定、更成熟且经过了更多的行业测试。它目前没有漏洞，而且更多使用 OAuth 的开发者最不熟悉 OAuth 1.0a。然而，OAuth 2.0 功能更详尽，支持实用的额外授权类型，并且不可避免是 OAuth 的未来。由于主要参与者（例如 Twitter、Facebook 和 Google 等）已经采用了 OAuth 2.0，OAuth 1.0a 不太可能长期被广泛使用。此时，你可以探索其他解决方案。如果你决定使用 OAuth 2.0，你不应该使用持有者令牌。相反，请使用更安全的令牌类型（如 MAC 令牌）或创建你自己的令牌系统，使用消息签名来建立授权。

本章的其余部分将探索“自建”方法。通过 Spring Currency，你将使用自己的令牌系统实现 OAuth 2.0，并创建一个能够消费你服务的非常简单的客户端。

> **注意**：这一点指出一个讽刺的现象：OAuth 2.0 项目的目标之一是减少实现之间的非互操作性。通常，OAuth 1.0a 客户端必须使用提供者提供的库才能与提供者的授权/资源正常工作。然而，OAuth 2.0 内置的非互操作性几乎保证了这个问题会变化而非好。创建你自己的令牌系统——这对于安全地使用 OAuth 2.0 实际上是必须的——确保了你必须为客户端提供与你的私有 OAuth 2.0 实现接口的客户端库。

# 使用 SPRING SECURITY OAUTH

Spring Security 通过其 Spring Security 子项目为 OAuth 1.0a 和 2.0 提供了充分的支持。除了在提供程序应用程序保护你的保护资源，Spring Security OAuth 还可以帮助你保护客户端应用程序中受 OAuth 保护的资源。Spring Security OAuth 分为两个 Maven 构件：

- `spring-security-oauth` 提供对 OAuth 1.0 和 1.0a 的支持。
- `spring-security-oauth2` 提供对 OAuth 2.0 的支持。

这些类组织在不同的包中，因此你可以同时使用它们——但需要注意。尽管你可以用不同的 OAuth 供应商保护不同的服务或 URL，但你不能同时用 OAuth 1.0(a) 和 OAuth 2.0 保护相同的 URL。你可以创建一个使用 Spring Security OAuth 访问 OAuth 1.0(a) 和 OAuth 2.0 服务的客户端应用程序。

本书无法涵盖所有的 Spring Security OAuth 场景：OAuth 1.0(a) 提供者、OAuth 1.0(a) 客户端、OAuth 2.0 提供者和 OAuth 2.0 客户端。然而，它必须涵盖提供者和客户端场景；否则，你将无法测试你的应用程序。由于 OAuth 2.0 最终将取代 OAuth 1.0a，你将在本章中学习 Spring Security OAuth 2.0 的支持。本章还涵盖了实现你自己的令牌系统。因为 OAuth 1.0 具有一些相似之处但也有一些显著的区别。你可以在参考文档中了解更多关于 OAuth 1.0 支持的信息。

# 创建 OAuth 2.0 提供者

Spring Security OAuth 2.0 提供者的实现分为两个组件：

- 授权服务器实现
- 资源服务器实现

这对应于 OAuth 2.0 规范，该规范说明了位于不同服务器上的授权和服务资源服务。

如果你愿意，可以只将 Spring Security OAuth 用于授权服务器或仅用于资源服务器。然而，你更有可能将其用于授权服务器和资源服务器，无论是在同一台还是不同的服务器上。为了简单，本章的示例假设授权服务器和资源服务器存在于相同的服务器上，以及集群中的所有服务器上。最后一部分非常重要，因为你只能为简单的非集群应用程序在内存中持久化令牌。任何集群化的应用程序必须使用更持久的方式持久化令牌。

# 管理客户端详情

在第 26 和第 27 章中，你学习了 Spring Security 的 `UserDetails` 和 `UserDetailsService` 接口。Spring Security OAuth 包含了类似的接口：`org.springframework.security.oauth2.provider.ClientDetails` 和 `org.springframework.security.oauth2.provider.ClientDetailsService`。

`ClientDetails` 指定了关于允许访问应用程序的客户端信息。由于客户端可以代表自己访问资源（例如客户端凭据授权），`ClientDetails` 包含了客户端持有的 `GrantedAuthority` 集合。它提供了客户端 ID 和客户端密钥，`ClientDetails` 还指示了请求的授权类型、客户端可以访问的资源（无限制则为 null）以及。

同样，`ClientDetailsService` 允许你通过客户端加载 `ClientDetails` 实例。当客户端身份验证时，Spring OAuth 使用 `ClientDetailsService` 加载客户端并与 HTTP Header 中的密钥进行比较。Spring OAuth 的授权服务器组件需要 `UserDetailsService` 才能正常工作。该服务的两个默认实现位于相同的包。

- `InMemoryClientDetailsService` 在启动时配置应用程序支持的所有客户端。
- `JdbcClientDetailsService` 使用硬编码表定义来存储和检索客户端详情。

由于客户端使用 HTTP 身份验证进行认证，当 Spring Security 已经支持这一点时，你可以配置一个带有 `DaoAuthenticationProvider` 和 `org.springframework.security.oauth2.provider.ClientDetailsUserDetailsService` 的标准认证管理器。

# 理解授权服务器

当客户端需要访问你的保护资源之一但没有访问令牌时，它会将所有者重定向到你的授权端点。OAuth 的授权服务器托管此端点。它显示确认屏幕，处理提交，生成授权码并将所有者重定向回客户端。它还响应交换授权码以获取访问令牌的端点请求。在配置授权服务器时，你必须配置 Spring Security 来保护授权端点。这样，Spring Security 要求用户身份验证并拥有访问授权端点的必要权限。OAuth 已经使用客户端凭据通过 HTTP Basic 认证保护了令牌端点。

配置授权服务器非常复杂，取决于你的差异很大。本书无法涵盖所有可能的组合，但本节提供了一些通用信息。下一节将向你展示一种可能的配置示例。

# 配置代码和令牌服务

在配置授权服务器之前，你必须配置能够存储和检索授权码和访问令牌的服务。`org.springframework.security.oauth2.provider.code.AuthorizationCodeServices` 指定了一个用于创建、存储和消费授权码的接口。授权服务器在资源所有者批准客户端的授权时，使用此服务创建一个授权码。当客户端联系授权服务器以用授权码交换访问令牌（access token）时，它使用 `AuthorizationCodeServices` 来“消费”授权码。一旦被消费，授权码将无法再次使用。授权服务器使用 `org.springframework.security.oauth2.provider.token.AuthorizationServerTokenServices` 的实现来创建和刷新令牌并将其返回给客户端。该实现持久化令牌，以便服务器可以检索它们。

在对资源服务器的请求中，`org.springframework.security.oauth2.provider.token.ResourceServerServices` 提供了一种获取与访问令牌关联的 `Authentication` 对象的机制。`Authentication` 最初在资源所有者进行身份验证时创建，并在资源所有者授权客户端时被附加到授权码中。当授权码交换为访问令牌时，令牌会被附加到访问令牌上，以便客户端每次访问受保护资源时都能引用。这允许 Spring Security 的授权服务在请求受保护资源期间能够访问资源所有者的用户详情和权限。

标准的 `AuthorizationCodeServices` 实现与该接口位于同一个包中。

- `InMemoryAuthorizationCodeServices` 创建由随机字母组成的授权码并将其持久化在内存中。这种实现非常出色且经过优化，性能良好，但仅在你没有运行在集群时有效。即使是负载均衡器的粘性会话（sticky sessions），对于端点和令牌端点也可能不起。客户端的下一次请求可能会命中不同的服务器，而 `InMemoryAuthorizationCodeServices` 将没有另一个服务器上生成的授权码的记录。如果你计划对应用程序进行集群化（你很可能这样做），你需要在中心位置（例如数据库）持久化授权码。
- `JdbcAuthorizationCodeServices` 同样创建随机授权码，并提供了一种在创建和交换之间将其存储在关系型数据库中的简单机制。你可以自定义 `INSERT`、`SELECT` 和 `DELETE` 语句来管理这些代码。当然，如果你愿意，也可以创建自己的实现。

`org.springframework.security.oauth2.provider.token.DefaultServerTokenServices` 是 `AuthorizationServerTokenServices` 的唯一标准实现。它处理访问令牌（bearer tokens）的创建、存储和检索，并使用 `org.springframework.security.oauth2.provider.token.TokenStore` 来管理令牌的实际持久化。你可以从 `InMemoryStore`（它在集群环境中存在缺点）或 `JdbcTokenStore` 中进行选择，也可以自己实现这些接口。

你将这些服务作为 Spring bean 进行配置。如果你选择使用内存实现，Spring Security OAuth 提供了 XML 命名空间来简化这些 bean 的创建。在大多数情况下，当你不指定其他内容配置 Spring Security OAuth 时，默认选择内存实现。由于内存实现不适用于集群环境，你需要更改这些默认值。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_870_0.png)



Spring Security OAuth 2.0 的 XML URI 为 `http://www.springframework.org/schema/oauth2`。你可以将其添加到任何 Spring Bean XML 文件中（使用推荐的 `oauth2` 命名空间前缀）以配置 OAuth 2.0 支持。如果你想用 XML 配置 OAuth 1.0，请使用 `http://www.springframework.org/schema/security/oauth` 架构（以及推荐的 `oauth` 命名空间前缀）。由于这些方案是独立的，你可以同时配置 OAuth 1.0 和 OAuth 2.0 组件。`<oauth2:authorization-server-element>` 属性允许你指定 `<ClientDetailsService bean`，而 `<tokens-services-ref>` 指明 `AuthorizationServerTokensServices` 的实例。你还可以使用 `authorization-endpoint-url` 和 `token-endpoint-url` 属性自定义端点 URL（它们分别指向 `/oauth/authorize` 和 `/oauth/token`）。

通过此元素，你可以指定多个其他控制支持哪些授权类型（grant types）。默认情况下，支持所有授权类型。`<authorization-code>`、`<implicit>`、`<client-credentials>` 和 `<password>` 分别控制代码授权（Code Grant）、隐式授权（Implicit Grant）、客户端凭据授权（Client Credentials Grant）和资源凭据授权（Resource Credentials Grant）。还有一个 `<refresh>` 元素，允许刷新令牌的工作非常像一种特殊的授权类型。

这些授权控制元素每一个都有一个 `disabled` 属性，你可以将其设置为 `true` 以禁用该授权类型。`<authorization-code>` 元素还包含 `AuthorizationCodeServices` 属性，允许你对其进行自定义。同样，`<password>` 包含 `authentication-manager-ref` 属性，允许你指定备选的 `AuthenticationManager` 。

> 注意：你可能好奇为什么缺少 Java 配置的细节。尽管 Spring Security OAuth 1 和 2.0.x 版本中应该会有 Java 配置，但该版本在本书印刷后才发布，因此本书未涵盖 Java 配置。在编写时，Spring Security OAuth 的 Java 配置尚不完整，且缺乏 XML 命名空间所提供的许多功能。请务必查看本书的下一版，以获取修订后的 Spring Security OAuth 2 仅限 Java 配置。

## 使用资源服务器

如你所读，资源服务器负责控制对受保护资源的访问。它确保请求附带访问令牌，检查这些令牌的有效性，并将未经授权的请求重定向到授权端点。“服务器”一词对于此功能可能会产生误义，因为它根本不是一个服务器。资源服务器仅仅是一个过滤器（Filter）和一些辅助类。它实际上并不提供资源；而是拦截你的应用程序所提供的资源请求。资源服务器使用之前介绍过的 `ResourceServerTokensServices` bean 来循环并验证请求中包含的访问令牌。

在对资源服务器的请求中，`org.springframework.security.oauth2.provider.token.ResourceServerServices` 提供了一种获取与访问令牌关联的 `Authentication` 对象的机制。`Authentication` 最初在资源所有者进行身份验证时创建，并在资源所有者授权客户端时被附加到授权码中。当授权码交换为访问令牌时，令牌会被附加到访问令牌上，以便客户端每次访问受保护资源时都能引用。这允许 Spring Security 的授权服务在请求受保护资源期间能够访问资源所有者的用户详情和权限。资源服务器使用之前介绍过的 `ResourceServerTokensServices` bean 来循环并验证请求中包含的访问令牌。资源服务器具有多个部分，并且使用 `<oauth2:resource-server>` XML 元素更容易配置。在大多数情况下，你需要指定 `token-services-ref` 属性，它应该是 `ResourceServerServices` bean 的引用。此外，如果你使用资源 ID，应该使用 `resource-id` 属性指定保护的资源 ID；否则允许所有资源 ID。这是在应用中设置 Spring Security OAuth 的最后一部分。下一节将演示真实示例。

## 使用 OAuth 安全表达式

在第 27 章中，你学习了 Spring Security 的授权表达式，当使用 `@PreAuthorize` 注解时可以将其用于 URL 和方法安全。Spring Security OAuth 扩展了这种支持，以配置 `oauth2` SpEL 变量。该变量是多个授权函数的命名空间，并且永远不会为空（即使方法是在 OAuth 受保护资源上执行）。额外的授权函数如下：

- `@oauth2.denyAuthClient()`：如果认证不是 OAuth 认证，则禁止远程 OAuth 用户访问应用程序中的某些功能，即使他们有足够的权限。
- `@oauth2.hasRole(String)`：如果客户端拥有该权限。要检查资源所有者是否拥有权限，请使用标准的 `hasAuthority` 或 `hasRole` 函数。
- `@oauth2.hasAnyRole(String...)`：如果客户端拥有至少一个权限。要检查资源所有者是否拥有至少一个权限，请使用标准的 `hasAuthority` 或 `hasRole` 函数。
- `@oauth2.hasScope(String)`：如果 OAuth 认证具有指定的 OAuth 范围（scope）。
- `@oauth2.hasAnyScope(String...)`：如果 OAuth 认证具有至少一个指定的范围。
- `@oauth2.isClient()`：如果当前认证属于 OAuth 客户端（例如，使用客户端凭据授权）。
- `@oauth2.isUser()`：如果当前认证属于 OAuth 资源所有者（例如，使用代码授权、隐式授权或资源所有者密码凭据授权）。

要使用这些新表达式，你需要配置扩展支持并替换现有的表达式支持。如果你使用 XML 配置，可以使用 `<oauth2:expression-handler>` 和 `<oauth2:web-expression-handler>` 元素来配置方法安全和 Web 安全表达式处理器，为它们指定 bean ID，并将引用注入任何其他配置组件中。Java 配置相当简单。只需扩展 `GlobalMethodSecurityConfiguration` 并重写 `createExpression` 以创建一个 `OAuth2MethodSecurityExpressionHandler` 而不是默认的 `DefaultMethodSecurityExpressionHandler`。同样，在定义 URL 表达式时，将默认表达式处理器（`DefaultWebSecurityExpressionHandler`）替换为 `OAuth2WebExpressionHandler`。

## 创建 OAuth 2.0 客户端

使用 OAuth 保护你的服务的另一面，就是从客户端应用程序访问受 OAuth 保护的资源。如前面提到的，Spring Security OAuth 可以帮助你处理这些工作。

要理解 Spring Security OAuth 客户端组件的工作原理，你必须首先了解 Spring Framework 的 `org.springframework.web.client.RestTemplate`。该接口定义了一组基本的 RESTful Web 操作。通过使用该接口的实现，你可以从 Web 服务中 GET 条目或条目集合、DELETE 一个实体、POST 一个新实体、PUT 更新条目、RETRIEVE 资源的 HEAD 信息、确定资源的 OPTIONS，以及更多。类等操作。该接口的默认实现 `org.springframework.web.client.RestTemplate` 是你访问 RESTful Web 服务时唯一可能需要的类。该工具集非常完整且经过了充分测试，并提供了拦截请求和响应的方法（例如，添加或更改标头）。

然而，RestTemplate 并没有对任何类型的安全提供内置支持。虽然你可以使用拦截器手动实现 OAuth 授权，但这是没有必要的，因为 Spring OAuth 提供了此功能的实现。`org.springframework.security.oauth2.client.OAuth2RestTemplate` 扩展了 RestOperations 接口以指定与 OAuth 相关的方法。同样，`org.springframework.security.oauth2.client.OAuth2RestTemplate` 扩展了 RestTemplate 以实现 OAuth2Operations 并提供 OAuth 2.0 客户端支持。

## 配置 OAuth RestTemplate

在使用 OAuth2RestTemplate 时，你应该记住重要的一点。对于标准的 RestTemplate，你可以在应用程序的任何地方为任何 Web 服务端复用单个 RestTemplate。这是因为 RestTemplate 是完全无状态的，在请求之间不存储任何标识信息。然而，OAuth2RestTemplate 的如此——而且对于任何配置了拦截器的 RestTemplate，可能都不如此，这取决于该拦截器的作用。

当你配置 OAuth2RestTemplate 时

在独立应用程序（未托管在 Web 上的程序）中，使用 OAuth2RestTemplate 要简单得多。你可以像使用其他 RestTemplate 实例一样使用它，只是你为一个客户端凭据创建一个全局实例。你需要为每个 OAuth2RestTemplate 提供一个 `org.springframework.security.oauth2.client.OAuth2ClientContext` 实现，该实现能够确定特定请求的客户端上下文和访问码（如果有）。通常，你将这些信息全局存储在整个 JVM 的每个线程中。

如果访问令牌无效或受 OAuth 保护的资源被拒绝，OAuth2RestTemplate 方法将抛出相应的异常。然而，如果资源所有尚未授权但需要重定向到授权端点（因为你在使用授权码授权或隐式授权），这些方法将抛出 `org.spring.framework.security.oauth2.client.resource.UserRedirectRequiredException`。

捕获到此异常后，你可以启动浏览器窗口、重定向请求或任何必要的操作将用户发送到授权端点。记住，你的独立应用程序必须接收来自授权端点的重定向才能接收授权码（或隐式授权的访问令牌）。在独立应用程序中，这意味着你的应用程序必须操作系统和已安装的浏览器注册正确的启动 URI 方案，或者在应用程序中包含一个嵌入式浏览器。如果这不是可行方案，你需要使用客户端凭据授权或资源密码凭据授权。

## 在 Web 应用程序中使用 REST Template

在 Web 应用程序中使用 OAuth2RestTemplate 比在独立应用程序中更简单，因为 Spring 的过滤器链可以为你处理大部分困难性工作。`oauth2:resource` 元素根据给定的配置选项创建一个 OAuth2ProtectedDetails 豆。你可以配置客户端 ID 和密钥、授权端点 URL、访问令牌 URL，并根据需要多次使用它来定义你的应用程序将使用的多个资源。（或者，你也可以手动创建 `<bean>` 或 `@Beans` 而不是快捷元素）。

定义好应用程序使用的受保护资源后，你可以使用一个或多个 `oauth2:rest-template` 元素来定义使用这些受保护资源详情的 OAuth2RestTemplate。然后，你可以在其他豆中使用这些模板来访问受保护资源。这些模板配置了特殊的会话作用域上下文（session-scoped），这意味着多个用户可以同时使用模板代码，且代码将以线程安全的方式绑定到每个用户会话的授权客户端。

为了让这些功能生效，你必须在过滤器链中启用 OAuth 客户端过滤器。使用命名空间配置很容易。只需在你的 XML 配置中添加 `oauth2:client` 元素，并将定义的过滤器添加到 `<http>` 元素或元素中：

```
<oauth2:client id="oauth2ClientFilter" />

<http>
  ...
  <custom-filter ref="oauth2ClientFilter" after="EXPRESSION_TRANSLATION_FILTER" />
</http>
```

你可能会在课程（course）中或对你应用程序的 HTTP 请求响应中发现这一点。你应该注意，这些特殊的会话作用域模板仅在课程（course）中有效。只要后台线程是由 HTTP 请求处理线程派生的（这样身份验证和会话信息就会继承），你就可以在“后台”使用这些模板。然而，在这种情况下，你必须小心确保在线程移交之前已获取了访问令牌。你永远不要将这些模板用于纯粹的调度任务，这里有两个显而易见的原因：

- 调度任务无法被重定向到授权端点。
- 过滤器永远不会被调用，在调度任务中运行的代码无法为已验证的用户端选择正确的访问令牌。

如果你想在纯粹的调度任务中使用 OAuth2RestTemplate，你需要为这些任务使用客户端凭据授权。在这种情况下，你必须手动配置 OAuth2RestTemplate。

> 注意：尽管这听起来可能言而易见，但如果不同时使用 Spring Security，你就无法使用 Spring Client 功能。客户端功能需要 Spring 上下文的存在。

## 完成客户支持项目 wrox.com 代码下载

下载的 Customer-Support-v21 是该应用程序的最终版本。你从第 3 章开始一直在编写这个项目，它看起来与第一个版本非常不同。

该请求防止其被重放。nonce（随机数）应该是随机的，以确保它们无法被预测。然而，由于真正的随机性不能排除重复，nonce 应该与时间戳配合使用。提供者应确保任何 nonce-时间戳组合都是唯一的。为了防止攻击者仅仅更改时间戳并重用 nonce 来重放请求，签名令牌除了包含 nonce 之外还应该包含时间戳。

此时，你已经知道签名令牌至少应该包含访问令牌（access token，但仅作为签名的盐）、nonce 和时间戳。它还应该包含什么？嗯，为了提供者能够获取正确的访问令牌来验证签名，请求需要包含某种类型的标识符，提供者可以使用它从令牌存储中查找访问令牌。请求将包含此标识符，将该标识符也包含在签名中是有意义的。

OAuth 1.0 在每个受保护资源请求中包含 ID，以确保只有发行访问令牌的客户端可以访问，但 OAuth 2.0 缺乏这一安全特性。在受保护资源请求中包含 ID 非常简单，而将 ID 包含在签名中可以确保它未被篡改。作为最后的合理性检查，包含请求的某些组件也无害。它不需要像 OAuth 1.0 那样复杂，也不需要包含请求参数、post 和头部——只需请求方法或 URL 那么简单。在语法上，签名可能看起来如下：

```
SHA1( clientId " , tokenID " , nonce " , timestamp " , method " , tokenValue )
```

假设 ID 为 TestClient，token ID 为 y8Fg1FPKZW，nonce 为 i7K45E4yAB，时间戳为 138192740，请求方法为 POST，令牌值为 Y4KPI2432489ey5013hk，签名可以描述为：

```
SHA1( TestClient,y8Fg1FPKZW,i7K45E4yAB,138192740,POST,Y4KPI2432489ey5013hk )
```

签名的计算值如下：

ed3ca5a9b0d647f5a967477bb13dba9d7ca8sc592b

来自同一客户端和资源 nonce 的每个受保护资源请求，其 client ID、token ID 和 token value 都是。只有 nonce 和时间戳值在每次请求中发生变化。请求方法始终反映请求的方法。

你需要在每次请求中传输所有数据。授权受保护资源请求的标准机制是在每个请求中包含 `Authorization` 头部。当请求头以 "Bearer" 开头并跟一个签名时，资源的值代表持有者令牌（bearer token）。对于这种情况下，你可以用 "Signing" 代替 "Bearer"，并在值中使用逗号分隔的键值对来提供令牌信息。使用之前描述的值和签名，请求中的 `Authorization` 头部所示（省略了实际头部中为了清晰而的换行）：

```
Authorization: Signing clientID=TestClient,nonce=i7K45E4yAB,timestamp=138192740,signature=ed3ca5a9b0d647f5a967477bb13dba9d7ca8sc592b
```

注意，token value 没有出现在头部中，因为不需要传输令牌来证明客户端持有它。请求方法也没有出现在头部中，因为它仅仅是请求的一部分。虽然签名中出现的顺序非常重要，但它们在头部中出现的顺序并不重要。当提供者接收请求时，只需使用 token ID 查找 token value，确保指定的客户端是令牌持有者，检查 nonce 是否从未被使用过，然后使用给定信息重新计算签名。如果签名与提供的签名匹配，则建立了访问令牌的真实性。如果签名不匹配，则必须拒绝请求。



> **WARNING** 刚刚描述了 OAuth 2.0 文档指定的标准 bearer 令牌系统的理论替代方案。该替代方案尚未经过。尽管此提议提供了比 bearer 令牌更高的安全性，但在生产应用程序中使用它之前，你应该对其进行仔细、彻底的评估，并咨询你组织的安全官。在通常使用 OAuth 时，你也应该采取同样的严谨态度。

> **NOTE** 如果你想进一步提高安全级别，可以使用非对称公私钥对来生成和验证签名，而不是使用共享密钥令牌作为签名。额外的好处是授权服务器永远不存储密钥（私钥）——只有客户端拥有此信息。如果整个 OAuth 凭据被盗，攻击者无法利用其中的公钥来破坏你的系统。此外，只要由服务器生成密钥对，私钥就不需要在网络上传输——这是极其安全的。这种技术将需要多得努力，留给读者进一步探索。

# 实现客户端服务

你需要定义允许访问你的 Web 服务的客户端。对于一个具有非常静态且稳定的内部开发客户端的简单系统，你可以使用 Spring Security OAuth 的 `InMemoryClientDetailsService`，但在某些情况下这是不够的。你可以使用 `JdbcClientDetailsService`，但如果你已经在使用 JPA、Spring Data 和 Spring Framework 转换，那么创建自己的可能会更容易。

# 创建客户端实体

客户端实体非常简单。它需要实现 `ClientDetails`，这是 Spring Security OAuth 使用的接口。

```java
@Entity
public class WebServiceClient implements ClientDetails, Serializable
{
  @Id
  @Column(name = "serviceId")
  @GeneratedValue(strategy = GenerationType.IDENTITY)
  private long id;

  public long getId() { return id; }
  public void setId(long id) { this.id = id; }

  @Column(name = "clientId")
  private String clientId;

  @Override
  public String getClientId() { return clientId; }
  public void setClientId(String clientId) { this.clientId = clientId; }

  @Column(name = "clientSecret")
  private String clientSecret;

  @Override
  public String getClientSecret() { return clientSecret; }
  public void setClientSecret(String clientSecret) { this.clientSecret = clientSecret; }

  @Column(name = "scope")
  @ElementCollection(fetch = FetchType.EAGER)
  @CollectionTable(name = "WebServiceClient_Scope", joinColumns = {
  @JoinColumn(name = "serviceId", referencedColumnName = "serviceId")
  })
  private Set<String> scope;

  @Override
  public Set<String> getScope() { return scope; }
  public void setScope(Set<String> scope) { this.scope = scope; }

  @Column(name = "grantName")
  @ElementCollection(fetch = FetchType.EAGER)
  @CollectionTable(name = "WebServiceClient_Grant", joinColumns = {
  @JoinColumn(name = "serviceId", referencedColumnName = "serviceId")
  })
  private Set<String> authorizedGrants;

  @Override
  public Set<String> getAuthorizedGrants() { return authorizedGrants; }
  public void setAuthorizedGrants(Set<String> authorizedGrants) { this.authorizedGrants = authorizedGrants; }

  @Column(name = "uri")
  @ElementCollection(fetch = FetchType.EAGER)
  @CollectionTable(name = "WebServiceClient_RedirectUri", joinColumns = {
  @JoinColumn(name = "serviceId", referencedColumnName = "serviceId")
  })
  private Set<String> redirectUri;

  @Override
  public Set<String> getRedirectUri() { return redirectUri; }
  public void setRedirectUri(Set<String> redirectUri) { this.redirectUri = redirectUri; }

  private static final Set<String> RESOURCE_IDS = new HashSet<>();
  private static final Set<GrantedAuthority> AUTHORITIES = new HashSet<>();
  static {
    RESOURCE_IDS.add("SUPPORT");
    AUTHORITIES.add(new SimpleGrantedAuthority("OAUTH_CLIENT"));
  }

  @Override @Transient
  public Set<String> getResourceIds() { return RESOURCE_IDS; }

  @Override @Transient
  public Set<GrantedAuthority> getAuthorities() { return AUTHORITIES; }

  @Override @Transient
  public Integer getAccessTokenValiditySeconds() { return 3600; }

  @Override @Transient
  public Integer getRefreshTokenValiditySeconds() { return -1; }

  @Override @Transient
  public Map<String, Object> getAdditionalInformation() { return null; }

  @Override @Transient
  public boolean isSecretRequired() { return true; }

  @Override @Transient
  public boolean isScoped() { return true; }
}
```

# 提供客户端详情

支持此实体的 Spring 仓库接口非常简单，消除了你需要的任何额外工作。

```java
public interface WebServiceClientRepository
extends CrudRepository<WebServiceClient, Long>
{
    WebServiceClient getClientByClientId(String clientId);
}
```

`WebServiceClientService` 接口扩展了 `ClientDetailsService` 以明确该服务始终返回 `WebServiceClient` 实体，且实现非常直观。注意 `loadClientByClientId` 返回的是 null。如果找不到客户端，它将抛出 Spring Security OAuth 的 `ClientRegistrationException` 来表示该客户端无效。同样注意，该服务没有提供任何注册新客户端的机制。（同样，也没有用于此操作的 UI）。这在不同的业务用例之间差异很大，这是留给你完成的练习。

```java
public interface WebServiceClientService extends ClientDetailsService
{
    @Override
    WebServiceClient loadClientByClientId(String clientId);
}
```

```java
public class DefaultWebServiceClientServiceImpl implements WebServiceClientService
{
    @Inject WebServiceClientRepository clientRepository;
    @Override
    @Transactional
    public WebServiceClient loadClientByClientId(String clientId)
    {
        WebServiceClient client = this.clientRepository.getClientByClientId(clientId);
        if (client == null)
            throw new ClientRegistrationException("Client not found");
        return client;
    }
}
```

# 完成客户支持应用程序 | 845

项目的 `create.sql` 文件为客户支持数据库添加了新表，并在这些表中插入了一个测试客户端。如果你在之前的章节中没有处理过客户支持应用程序，则你需要运行 `create.sql` 脚本并创建相应的 Tomcat 数据源（命名为 `jdbc/CustomerSupport`）。如果你有现有的数据库需要升级，请确保运行这四个表的创建语句。插入到新表中的测试客户端数据如下所示。（客户端密码是 "y471I12D2y5SSU58rr8a2" 的 BCrypt 哈希值）

```sql
INSERT INTO WebService_Client (ClientId, ClientSecret) VALUES
('TestClient', '$2a$10e1DbFCb/ZkyuOpFKS.7001gn2EuhUy2yONPsoF3avx9.Hd/b8BTa');
```

```sql
INSERT INTO WebService_Scope (ClientId, Scope)
VALUES (1, 'READ'), (1, 'WRITE'), (1, 'TRUST');
```

```sql
INSERT INTO WebService_Grant (ClientId, GrantName)
VALUES (1, 'authorization_code');
```

```sql
INSERT INTO WebService_RedirectUri (ClientId, Uri)
VALUES (1, 'http://localhost:8080/client/support/');
```

如果你正在使用现有数据库，你需要授予访问网络服务的权限。来自 `create.sql` 脚本的以下语句为用户 Nicholas 和 John 添加了此权限（假设你在数据库中保留了默认用户）。

```sql
INSERT INTO UserPrincipal_Authority (UserId, Authority)
VALUES (1, 'USER_WEB_SERVICES'), (4, 'USER_WEB_SERVICES');
```

# 实现 Nonce 服务

Spring OAuth 2 没有任何类型与 nonce 相关的接口，因为 nonce 不是 OAuth 2.0 的标准部分。然而，伪造这样一个系统实际上非常简单。实现 nonce 实体、仓库和服务的的工作量非常小。如果你有现有的数据库需要升级，请务必运行 SQL 创建语句。

```java
@Entity
@Table(name = "OAuthNonce")
public class Nonce implements Serializable {

  private static final long serialVersionUID = 1L;

  private long id;
  private String value;
  private long timestamp;

  public Nonce() {}
  public Nonce(String value, long timestamp) {
      this.value = value;
      this.timestamp = timestamp;
  }

  @Id
  @Column(name = "OAuthNonceId")
  @GeneratedValue(strategy = GenerationType.IDENTITY)
  public long getId() { return id; }
  public void setId(long id) { this.id = id; }

  public String getValue() { return value; }
  public void setValue(String value) { this.value = value; }

  @Column(name = "NonceTimestamp")
  public long getTimestamp() { return timestamp; }
  public void setTimestamp(long timestamp) { this.timestamp = timestamp; }
}
```

```sql
CREATE TABLE OAuthNonce (
    OAuthNonceId BIGINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    Value VARCHAR(50) NOT NULL,
    NonceTimestamp BIGINT NOT NULL,
    UNIQUE KEY OAuthNonce_Value_Timestamp (Value, NonceTimestamp)
) ENGINE = InnoDB;
```

`NonceRepository` 使用了你在第 22 章中学会的技术，但没有尝试使用 `@org.springframework.data.jpa.repository.Query` 为不匹配标准 Spring Data 仓库的方法定义查询。`@org.springframework.data.jpa.repository.Modifying` 注解告诉 Spring Data 该方法修改数据（而不是读取），并且应该执行：

```java
public interface NonceRepository extends CrudRepository<Nonce, Long> {
    Nonce getByValueAndTimestamp(String value, long timestamp);

    @Modifying
    @Query("DELETE FROM Nonce n WHERE n.timestamp < :timestamp")
    void deleteWhereTimestamp(long timestamp);
}
```



NonRepository 使用了你在第 22 章中学会的技术，但没有尝试使用 `@org.springframework.data.jpa.repository.Query` 为不匹配标准 Spring Data 仓库的方法定义查询。`org.springframework.data.jpa.repository.Modifying` 注解告诉 Spring Data 该方法修改数据（而不是读取），并且应该执行：

`NonceRepository` 的 `delete` 方法的作用是简单的。它用于删除超过 2 分钟的 nonce。

```java
if (this.nonceRepository.getByValueAndTimestamp(nonce, timestamp) != null) {
    throw new InvalidTokenException("Duplicate value " + nonce + " " + timestamp);
}

this.nonceRepository.save(new Nonce(nonce, timestamp));
```

```java
public interface SigningAccessTokenRepository
    extends JpaRepository<SigningAccessToken, Long>
{
    SigningAccessToken getByKey(String key);
    SigningAccessToken getByValue(String value);
}
```

创建和检索访问令牌的服务要复杂得多。它不仅为了简单起见实现了 `AuthorizationServerServices` 和 `ResourceServerTokenServices`，还提供了一个额外的方法，通过令牌标识符（即 `key` 属性）查找访问令牌。该方法在 `SigningAccessTokenServices` 中定义：

```java
public interface SigningAccessTokenServices
    extends AuthorizationServerServices, ResourceServerTokenServices
{
    SigningAccessToken getAccessToken(String key);
}
```

列表 28-1 中的 `DefaultAccessTokenServices` 实现了此接口，并提供了创建和检索基于签名的访问令牌所需的所有逻辑。`refreshAccessToken` 抛出了 `UnsupportedException`，因为对于基于签名的令牌不需要刷新令牌，而且在这种特定情况下，你可能希望在访问令牌过期时要求用户重新授权。

`DefaultAuthenticationGenerator` 根据 `OAuthAuthentication` 创建一个确定性的密钥（你用它作为令牌标识符）。当客户端连接并用授权码交换访问令牌时，授权服务器会调用 `createAccessToken` 方法。在某些情况下，它也会调用 `getAccessToken(OAuthAuthentication)`，确定性密钥生成器使得查找访问令牌成为可能。授权服务器也会调用 `refreshAccessToken` 但在本项目中刷新令牌被禁用了。

`SigningAccessTokenServices` 中指定的 `getAccessToken(String)` 方法是资源服务器使用的方法，用于通过客户端提供的密钥来查找访问令牌。资源服务器通常会使用其他方法通过令牌值检索令牌和身份验证，但在你稍后在章节中创建的自定义资源服务器实现中，这些方法是不必要的。你必须使用 `getAccessToken(String)`，因为客户端连接包含的是令牌标识符而不是令牌值。

### 列表 28-1：DefaultAccessTokenServices.java

```java
public class DefaultAccessTokenServices
{
    AuthenticationKeyGenerator authenticationKeyGenerator =
        new DefaultAuthenticationKeyGenerator();

    @Inject SigningAccessTokenRepository repository;

    @Override
    @Transactional
    public OAuth2 createAccessToken(OAuthAuthentication auth)
        throws AuthenticationException
{
        String key = this.authenticationKeyGenerator.extractKey(auth);
        SigningAccessToken token = this.repository.getBy(key);
        if (token != null) {
            if (token.isExpired()) {
                this.repository.delete(token);
                this.repository.flush();
            } else {
                token.setAuthentication(auth); // 以防权限发生变化
                this.repository.save(token);
                return token;
            }
        }

        token = new SigningAccessToken(
            key,
            UUID.randomUUID().toString(),
            new Date(System.currentTimeMillis() + 86_400_000L), // 一天
            auth.getAuthorizationRequest().getScope(),
            auth
        );

        this.repository.save(token);

        return token;
    }

    @Override @Transactional
    public OAuth2AccessToken getAccessToken(OAuth2Authentication auth) {
        return this.repository.getByKey(
            this.authenticationKeyGenerator.extractKey(auth)
        );
    }

    @Override @Transactional
    public SigningAccessToken getAccessToken(String key) {
        return this.repository.getByKey(key);
    }

    @Override @Transactional
    public OAuth2AccessToken readAccessToken(String tokenValue) {
        return this.repository.getByValue(tokenValue);
    }

    @Override @Transactional
    public OAuth2Authentication loadAuthentication(String tokenValue)
    throws AuthenticationException {
        SigningAccessToken token = this.repository.getByValue(tokenValue);
        if(token == null) {
            throw new InvalidTokenException("Invalid token " + tokenValue + ".");
        }
    }

    @Override
    public OAuth2AccessToken refreshTokenToken(String refreshToken,
        throws AuthenticationException) {
        throw new UnsupportedOperationException();
    }
}
```

## 自定义资源过滤器

通常，你会使用 XML 命名空间元素 `<oauth2:resource-server>` 配置 Spring Security OAuth2 资源服务器。这个 `org.OAuth2AuthenticationProcessingFilter` 会拦截受保护的资源并验证访问令牌。该过滤器专门为 bearer tokens 编写，且不易扩展，因此在这种情况下，你必须实现自己的过滤器。

`OAuthSigningTokenFilter` 为你处理了这一切，并且大部分内容不会被打印。`parseHeader` 方法解析 `Authorization` 头部，确保它是 `Signing` 值，并返回头部中参数的 `Map<String, String>`。`doFilter` 调用 `parseHeader` 来确定头部是否存在，然后将头部值的 Map 传递给 `authenticate` 方法。该方法执行了硬性工作：计算签名、将其与提供的签名进行比对、验证令牌并确保请求不包含旧的或重复的。



```java
private void authenticate(Map<String, String> header,
    HttpServletRequest request) {
    String tokenId = header.get("token_id");
    if(tokenId == null) {
        throw new InvalidTokenException("Header " + header + ":" missing token_id.");
    }

    SigningAccessToken token = this.tokenServices.getAccessToken(tokenId);
    if (token == null) {
        throw new InvalidTokenException("Token " + tokenId + ":" not found.");
    }

    OAuth2Authentication authentication = token.getAuthentication();
    AuthorizationRequest authorizationRequest =
        authentication.getAuthorizationRequest();

    String clientId = header.get("client_id");

    if(!authorizationRequest.getClientId().equals(clientId))
        throw new InvalidTokenException("Client ID does not match.");

    Collection<String> resources = authorizationRequest.getResourcesIds();
    if(this.resourceId == null && resources != null &&
        !resources.isEmpty() && !resources.contains(this.resourceId))
        throw new InvalidTokenException("Resource ID not permitted.");

    String timestamp = header.get("timestamp");
    String nonce = header.get("nonce");
    if(timestamp == null || nonce == null)
        throw new InvalidTokenException("Header missing timestamp or nonce.");

    String toSign = clientId + "+" + tokenId + "+" + nonce + "+" +
        timestamp + "+" + request.getMethod().toUpperCase() + "+" +
        token.getValue();
    String signature = Base64.getEncoder().encode(
        DIGEST.digest(toSign.getBytes(StandardCharsets.UTF_8))
    , StandardCharsets.UTF_8);

    String presentedSignature = header.get("signature");
    if(!signature.equals(presentedSignature))
        throw new InvalidTokenException("Missing or invalid signature.");

    long timestampValue = Long.parseLong(timestamp);
    long now = System.currentTimeMillis() / 1000;
    if(timestampValue < now - 60 || timestampValue > now + 60)
        throw new InvalidTokenException("Header timestamp out of range.");

    this.nonceServices.reportNonceOrFailDuplicate(nonce, timestampValue);
    request.setAttribute(OAuthAuthenticationDetails.ACCESS_TOKEN_VALUE,
        token.getValue());
    authentication.setDetails(this.authenticationDetails.buildDetails(
        request
    ));
    SecurityContextHolder.getContext().setAuthentication(authentication);
}
```

# 完成客户支持应用程序

## 重新配置 Spring Security

完成 OAuth 2 提供者的最后一步是在 Spring Security 中对其进行配置。尽管你在之前的章节中使用了纯 Java 配置了 Spring Security，但 Spring Security OAuth 不支持 Java 配置。虽然从理论上讲，你可以创建一个结合了 XML 命名空间和 Java 特性的混合 Spring Security 配置，但这样做得不偿失。你最好完全使用 XML 命名空间。

你会发现 `SecurityConfiguration` 类已不再存在。它被 resources 目录下的 `securityConfiguration.xml` 文件所取代，而 `RootContextConfiguration` 类已更改为导入该 XML 文件：

```java
@ImportResource("classpath:wrox/config/securityConfiguration.xml")
public class RootContextConfiguration implements
    AsyncConfigurer, SchedulingConfigurer, TransactionManagementConfigurer {

}
```

XML 配置从命名空间导入和一些基础 bean 的定义开始：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xmlns:oauth2="http://www.springframework.org/schema/security/oauth2"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/beans.xsd">

    <bean id="userService" class="com.wrox.site.DefaultUserService" />
    <bean id="webClientService" class="com.wrox.site.DefaultWebClientService" />
    <bean id="clientDetailsUserService" class="com.wrox.site.DefaultUserService" />
    <bean id="client" class="org.springframework.oauth2.provider.client.ClientDetailsMapper">
        <constructor-arg ref="webClientService" />
    </bean>

    <bean id="sessionRegistry" class="org.springframework.security.core.session.SessionRegistryImpl" />
    <bean id="webSecurityExpressionHandler" class="org.springframework.security.oauth2.provider.expression.OAuth2WebSecurityExpressionHandler" />
    <bean id="methodSecurityExpressionHandler" class="org.springframework.security.oauth2.provider.expression.OAuth2MethodSecurityExpressionHandler" />

    <bean id="passwordEncoder" class="org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder" />

</beans>
```

## 完成客户支持应用程序 | 853

注意你在之前的章节中用 Java 配置的密码编码器、会话注册表（`session registry`）和 `DefaultUserService`。它还配置了 Spring Security OAuth 2 认证处理器，以替换默认的异常处理器以及你用于查找 OAuth 客户端的 `DefaultUserServiceClient`。`ClientUserDetailsService` 是 `ClientDetails` 和 `Service` 接口之间的特殊桥梁，对于认证管理器在访问令牌端点的正常工作是必须的。对于内存令牌（`bearer tokens`），你通常需要定义 `DefaultTokenStore` 和 `TokenStore`。例如，你可以配置：

```xml
<beans:bean id="tokenStore"
    class="org.springframework.security.oauth2.provider.token.MemoryTokenStore" />

<beans:bean id="tokenServices"
    class="org.springframework.security.oauth2.provider.token.DefaultTokenServices">
    <beans:property name="tokenStore" ref="refreshToken" />
    <beans:property name="clientDetailsService" value="true" />
</beans:bean>
```

相反，你只需要配置你的 `DefaultAccessTokenServices`：

```xml
<beans:bean id="tokenServices"
    class="com.wrox.site.DefaultAccessTokenServices" />
```

接下来，你需要配置其他几个 OAuth 和认证管理组件。`UserApprovalHandler` 处理授权客户端的资源响应。`OAuth2AccessDeniedHandler` 处理访问拒绝并返回带有客户端请求内容类型的响应。`OAuth2AuthenticationEntryPoint` 执行执行相同的操作，但是针对认证错误而非访问拒绝。第一个 `<authentication-manager>` 为你在第 26 节中配置的认证创建认证管理器，它创建了一个特殊的认证管理器来处理指向访问令牌端点的客户端请求。

```xml
<beans:bean id="userApprovalHandler"
    class="org.springframework.security.oauth2.provider.approval.TokenServicesUserApprovalHandler">
    <beans:property name="tokenServices" ref="tokenServices" />
</beans:bean>
```

```xml
<beans:bean id="oauthAccessDeniedHandler"
    class="org.springframework.security.oauth2.provider.error.OAuth2AccessDeniedHandler" />
```

```xml
<beans:bean id="oauthAuthenticationEntryPoint"
    class="org.springframework.security.oauth2.provider.error.OAuth2AuthenticationEntryPoint" />
```

```xml
<authentication-manager>
    <authentication-provider user-service-ref="userService">
        <password-encoder ref="passwordEncoder" />
    </authentication-provider>
</authentication-manager>
```

```xml
<authentication-manager id="oauthClientAuthenticationManager">
    <authentication-provider user-service-ref="clientDetailsUserService">
        <password-encoder ref="passwordEncoder" />
    </authentication-provider>
</authentication-manager>
```

```xml
<oauth2:authorization-server token-services="tokenServices"
    client-details-service-ref="webServicesService"
    user-approval-page="oauth/authorize"
    error-page="oauth/error">
    <oauth2:authorization-code />
</oauth2:authorization-server>
```

`oauth2:authorization-server` 元素是配置的核心。它配置了令牌服务、客户端详情服务和用户批准页面。`oauth2:authorization-code` 元素启用了授权码授权模式（`authorization code grant`），这是 Web 最常用的授权模式。

`token-services` 属性指向处理令牌生成和验证的 bean。`client-details-service-ref` 属性指向提供 ID 和密钥等客户端信息的 bean。`user-approval-page` 属性指定了用户被请求批准访问请求的 URL。`error-page` 属性指定了在授权过程中发生错误时用户被重定向的 URL。



<http url-expressions="true">
  <intercept-url pattern="/session/list"
    access="hasAuthority('VIEW_USER_SESSIONS')" />
  <intercept-url pattern="/auth/**">
    access="hasAuthority('USE_WEB_SERVICES')" />
  <intercept-url pattern="/login/**">
    access="permitAll()" />
  <intercept-url pattern="/logout/**">
    access="permitAll()" />
  <intercept-url pattern="/api/**">
    access="isFullyAuthenticated()" />
  <intercept-url pattern="/api/**">
    access="isFullyAuthenticated()" />
  <form-login default-target-url="/ticket/list" login-page="/login"
    login-url="/login/submit"
    authentication-failure-url="/login/loginFailed"
    username-parameter="username"
    password-parameter="password" />
  <logout logout-url="/logout" logout-success-url="/login/loggedOut"
    delete-cookies="JSESSIONID" invalidate-session="true" />
  <session-management invalid-session-url="/login"
    session-fixation-protection="changeSessionId">
    <concurrency-control error-if-max-exceeded="true" max-sessions="1"
      session-registry-ref="sessionRegistry" />
  </session-management>
  <csrf />
  <exception-handler ref="webSecurityExpressionHandler" />
</http>

到此时，你已经使用 Spring Security OAuth 成功创建了一个 OAuth 2.0 provider。你会发现 Web 服务端点在其处理器方法中利用 `@AuthenticationPrincipal` 来获取 `UserPrincipal`。

接下来你想要关注的是 `TicketService` 接口和 `DefaultTicketService` 实现。这些已经过更新，你的代码可以可选地指定 lambda 表达式，在事务内获取通常是懒加载（lazy-loaded）的属性，从而确保 `TicketRestTemplate` 支持这种扩展能力。当然，这只是解决此问题的方法之一，远不是性能最好的解决方案。最终，你需要一种方法告诉 Jackson Data Processor 和其他工具忽略那些尚未完全加载的懒加载属性。这是一项困难的任务，留给你来完成，因为这超出了本书的范围。

你在这里所做的更改目前还没有什么用处，因为你还没有办法测试它们。本章的下一个也是最后一个部分将帮助你创建一个简单的 OAuth 2 client，用于测试该 provider 和客户端应用程序。

## 创建 OAUTH 客户端应用程序

幸运的是，Spring Security OAuth 不仅包含 provider 的实现，还包含 client 的实现，使得消费受 OAuth 保护的资源变得简单得多。Spring Security OAuth 2 client 支持访问任何 RESTful 服务，因为它与你之前读过的 `OAuth2RestTemplate` 类紧密绑定。早期的工作正在进行，以便在下一个中实现这种支持，使其比其他客户端（如 SOAP 客户端）更通用，从而能够利用 OAuth 客户端功能。

你可以从 spring.com 代码站点下载 `OAuth-Client` 项目，它演示了如何使用 Spring OAuth 和 `OAuth2RestTemplate` 访问 Customer Support 应用程序的 RESTful 服务。

当你打开它时，首先会注意到它包含了来自 `Customer-Support-v21` 应用程序的 `Ticket`、`Attachment` 和 `Principal` 类（去掉了 JPA 注解）以及 `TicketWebServiceList`。这使得客户端能够轻松反序列化来自 Customer Support 服务的响应。事实上，provider 分发包含 `Ticket` 和 `Attachment` 等发布数据类型的制品是常见做法，这样客户端就可以更可靠地使用 Web 服务。

`OAuth-Client` 项目还提供了一个非常简单的 `AuthenticationController` 和登录界面，用于通过 Spring Security 处理应用程序的登录。

## 自定义 REST Template

通常情况下，开箱即用的客户端配置是直观的并且能够满足你的需求，但你正在使用自定义的签名令牌，因此你需要进行一些自定义。这种自定义没有在你实现 OAuth 时需要的那么复杂。你只需要扩展 `OAuth2RestTemplate` 并重写 `createRequest` 方法，使用你自定义的访问令牌协议，而不是默认的 bearer 令牌。列表 28-2 中的 `OAuth2SigningRestTemplate` 实现了客户端令牌签名的生成。它使用 UUID 生成一个随机 nonce，创建签名字符串，生成签名，然后将带有必要参数的头添加到请求中。

### 列表 28-2：OAuth2SigningRestTemplate.java

```java
public class OAuth2SigningRestTemplate extends OAuth2RestTemplate
{
    private static final Logger log = LogManager.getLogger(OAuth2SigningRestTemplate.class);
    private static final MessageDigest DIGEST;
    static {
        try {
            DIGEST = MessageDigest.getInstance("SHA-1");
        } catch (NoSuchAlgorithmException e) { // 不可能的
            throw new IllegalStateException(e);
        }
    }

    private final OAuth2ProtectedResourceDetails resource;

    public OAuth2SigningRestTemplate(OAuth2ProtectedResourceDetails resource)
    {
        ... 
    }
    public OAuth2SigningRestTemplate(OAuth2ProtectedResourceDetails resource,
        OAuth2ClientContext context) { ... }

    @Override
    protected ClientHttpRequest createRequest(URI uri, HttpMethod method)
    throws IOException
    { }
```

继续

### 列表 28-2（续）

```java
OAuth2AccessToken token = this.getAccessToken();

String tokenType = token.getType();
if(StringUtils.hasText(tokenType))
    tokenType = OAuth2AccessToken.BEARER_TYPE;

if("Signing".equalsIgnoreCase(tokenType))
{
    String clientId = this.getClientId();
    String tokenId = token.getValue();
    String nonce = UUID.randomUUID().toString();
    long timestamp = System.currentTimeMillis() / 1000;

    String sign = clientId + ":" + tokenId + ":" + nonce + ":" + timestamp;
    String signature = Base64.getEncoder().encode(sign.getBytes(StandardCharsets.UTF_8));

    request.getHeaders().add("Authorization", "Bearer " + signature);
}
```

## 配置 Spring Security

OAuth-Client 的大部分 Spring 配置都是样板代码。它包含了许多你已经见过的内容。`<authentication-manager>` 声明了一个包含两个用户的简单内存用户服务，其中 `<http>` 定义了认证和授权规则。`<oauth2:resource>` 和 `<oauth2:client>` 是你之前未使用过的新功能。首先，它定义了该客户端消费的保护资源，其中包括。

## 创建 OAuth 应用程序

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:security="http://www.springframework.org/schema/security"
     xmlns:aop="http://www.springframework.org/schema/aop"
     xmlns:oauth2="http://www.springframework.org/schema/oauth2"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
         http://www.springframework.org/schema/security http://www.springframework.org/schema/security/spring-security.xsd
         http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop.xsd
         http://www.springframework.org/schema/oauth2 http://www.springframework.org/schema/oauth2/spring-security-oauth2.xsd">

    <oauth2:resource id="OAuth2Client" client-authentication-scheme="header"
          client-id="TestClient" client-secret="y471d2g558rd"
          scope="READ, WRITE, TRUST"
          user-authorization-uri="http://localhost:8080/support/authorize"
          access-token-uri="http://localhost:8080/support/token" />

    <authentication-manager>
        <user-service>
            <user name="Steve" password="apple" authorities="USER" />
            <user name="Bill" password="orange" authorities="USER" />
        </user-service>
    </authentication-manager>

    <oauth2:client id="OAuth2ClientFilter" />

    <http url-expressions="true">
      <intercept-url pattern="/login/*" access="permitAllAll()" />
      <intercept-url pattern="/login" access="permitAllAll()" />
      <intercept-url pattern="/logout/*" access="permitAllAll()" />
      <intercept-url pattern="/**" access="hasAuthority('USER')" />
      <session-management invalid-session-url="/login"
          session-fixation-protection="changeSessionId" />
      <form authentication-failure-url="/login?loginFailed"
              login-page="/login" login-processing-url="/login/submit"
              username-parameter="username" password-parameter="password"
              default-target-url="/logout" />
      <logout logout-url="/logout" logout-success-url="/login?loggedOut"
              delete-cookies="JSESSIONID" invalidate-session="true" />
      <custom-filter ref="OAuth2ClientFilter"
                  after="EXCEPTION_TRANSLATION_FILTER" />
    </http>

</beans:beans>
```

最后你需要配置的是 RestTemplate 实现。如果你使用的是默认的 bearer 令牌类型，配置如下：

```xml
<oauth2:rest-template id="customerSupportRestTemplate"
    resource="OAuth2ClientBean" />
```

然而，由于你创建了自定义的 RestTemplate，你必须手动对其进行配置。这非常复杂，涉及到创建一个请求作用域的访问令牌并将其封装在代理中、创建一个会话作用域的客户端上下文并将其封装在代理中，最后创建一个消耗这些 bean 的自定义 RestTemplate。这些都是 `<oauth2:rest-template>` 通常自动为你提供的功能。对于 `<oauth2:resource>`，你需要为应用程序访问的每个受保护资源配置 RestTemplate。



```xml
<beans:bean name="accessTokenProxy" scope="request">
    class="org.springframework.security.oauth2.client.DefaultAccessTokenRequest">
    <beans:constructor-arg ref="${currentUri}" />
    <beans:constructor-arg index="0" value="${request.parameterMap}" />
    <beans:property name="uri" value="${request.getAttribute('currentUri')}" />
</beans:bean>
<beans:bean name="clientContextProxy" scope="session">
    class="org.springframework.security.oauth2.client.DefaultOAuth2ClientContext">
    <beans:constructor-arg>
    <beans:constructor-arg index="0" ref="accessTokenProxy" />
</beans:bean>
<beans:bean id="customerSupportRestTemplate">
    class="com.wrok.site.OAuth2SigningRestTemplate">
    <beans:constructor-arg index="0" ref="OAuth2ClientBean" />
    <beans:constructor-arg index="1" />
</beans:bean>
<beans:bean class="org.springframework.security.oauth2.config.DefaultOAuth2ClientRequestFactory">
    <beans:property name="resource" ref="OAuth2ClientBean" />
    <beans:property name="baseContext" value="bareContext" />
    <beans:bean class="org.springframework.security.oauth2.client.DefaultOAuth2ClientContext">
    <beans:property name="scopedContext" ref="clientContextProxy" />
</beans:bean>
</beans:property>
<beans:constructor-arg>
<beans:list name="messageConverter">
HttpMessageConverter
<beans:bean class="org.springframework.http.converter.json.MappingJackson2HttpMessageConverter">
<beans:property name="objectMapper" ref="objectMapper" />
</beans:bean>
</beans:list>
</beans:property>
</beans:constructor-arg>
</beans:bean>
```

> 注意：需要这种复杂的配置是因为 Spring Security OAuth 支持没有提供插件额外令牌类型的机制，这意味着你必须扩展 `OAuth2RestTemplate` 并配置扩展后的类。希望 Spring Security OAuth 2.0 版本 2 将提供一种提供替代令牌类型的机制来避免这个问题，但在本书出版之前还无法知晓这一点。

# 使用 REST Template

使用自定义的 `OAuth2RestTemplate` 可能是 OAuth-Client 项目中最简单的部分。SupportController 从客户支持 Web 服务获取所有工单（Tickets）列表，并将请求转发到显示所有列表的视图。如果用户当前登录的客户端应用程序没有该 Web 服务的访问令牌，将会发生 `UserRedirectRequiredException`，用户将被重定向到授权端点。

携带授权码返回此控制器后，Spring Security OAuth 2 会将代码交换为访问令牌。

```java
@Controller
public class SupportController {
    private static Logger log = LoggerFactory.getLogger(SupportController.class);

    @Autowired
    private RestTemplate webService;

    @RequestMapping("/support")
    public String getTickets(Map<String, Object> model) {
        List tickets = webService.getForObject("http://localhost:8080/tickets", List.class);
        model.put("tickets", tickets);
        return "support";
    }
}
```

> 注意：Spring Security OAuth 支持没有提供插件额外令牌类型的机制，这意味着你必须扩展 `OAuth2RestTemplate` 并配置扩展后的类。希望 Spring Security OAuth 2.0 版本 2 将提供一种提供替代令牌类型的机制来避免这个问题，但在本书出版之前还无法知晓这一点。

使用自定义的 `OAuth2RestTemplate` 可能是 OAuth-Client 项目中最简单的部分。SupportController 从客户支持 Web 服务获取所有工单（Tickets）列表，并将请求转发到显示所有列表的视图。如果用户当前登录的客户端应用程序没有该 Web 服务的访问令牌，将会发生 `UserRedirectRequiredException`，用户将被重定向到授权端点。

携带授权码返回此控制器后，Spring Security OAuth 2 会将代码交换为访问令牌。

# 提供者与客户端并存

使用自定义的 `OAuth2RestTemplate` 可能是 OAuth-Client 项目中最简单的部分。

- 在 IDE 中打开并构建 OAuth-Client 项目。
- 在 `target` 目录下找到 `oauth-client-1.0-SNAPSHOT`，并将其拷贝到 Tomcat 的 `webapps` 目录。
- 将复制的目录重命名为 `client`。
- 从 IDE 启动 Tomcat 应用。
- 在 Tomcat 完全启动后，访问 `http://localhost:8080/client` 并登录。
- 授予客户端访问权限，你将携带授权码重定向回 `http://localhost:8080/client/support`。

测试提供者（Provider）和客户端（Client）需要一些精力。在获取授权码后，Spring Security OAuth 2 在后台获取访问令牌并访问受保护资源。

你现在应该可以在客户端应用程序中看到订单列表，这意味着 OAuth 提供者和客户端都工作正常。

### 总结

本书涵盖了涉及保护你的 Web 服务免受未经授权访问的许多概念和技术。你学习了 OAuth 以及 OAuth 1.0a 和 OAuth 2.0 标准。由于你并没有深入研究 OAuth 标准，在将任何 OAuth 版本投入生产环境之前，你应该阅读相关规范。你探索了 OAuth 2.0 在 Spring Security OAuth 中如何工作，包括 Spring Security OAuth 如何帮助你创建资源应用程序和客户端应用程序。最后，你通过使用 OAuth 保护 Web 服务完成了客户支持应用程序，并创建了一个简单的客户端应用程序来证明该实现是有效的。

本书从对基础 Java Web 应用程序结构的介绍开始。你学习了 Java Servlet、JSP、自定义 JSP 标签、HTTP 会话、WebSocket 以及使用 Log4j 2 进行日志日志。接下来，你探索了 Spring Framework 及其帮助你创建世界级应用的强大功能。之后，你实验了 Java Persistence API（JPA），并学习了 Spring Data 如何让实体持久化变得只需几行代码。最后，在最后部分学习了如何使用 Spring Security、表单认证和 OAuth 来确保你的应用程序安全。

你在本书中使用的工具每天都会发布新版本，每个新版本都会带来改进你应用程序的功能。请关注这些新版本以及本书的未来版本，以掌握专业 Java Web 应用程序开发的最新技术和方法。

# 索引

# 数字与符号

- 3 位字母 ISO 639-2 代码, 193
- 64 位指针, 9
- `+ 101` 切换协议, 264, 265, 267
- `204` 无内容, 482, 483, 494, 498
- `302` 临时重定向, 109, 110, 111, 371, 736
- `303` 查看其他内容, 371, 736
- `307` 临时重定向, 736
- `400` 错误请求, 264, 265, 479, 498, 822
- `401` 未授权, 480, 481, 732, 733, 734, 735, 822, 824, 830
- `404` 未找到, 179, 237, 480, 481, 483, 498
- `405` 方法未允许, 44, 480, 482
- `406` 不可接受, 486
- `415` 不支持的媒体类型, 480
- `426` 需要升级, 264
- `500` 内部内部错误, 235, 237, 480, 838
- `#auth2.clientHasAnyRole(String...)`, 837
- `#auth2.clientHasRole(String)`, 837
- `#auth2.denyOAuthClient()`, 837
- `#auth2.hasScope(String ...)`, 837
- `#auth2.hasScope(String)`, 837
- `#auth2.isClient()`, 837
- `#auth2.is()`, 837
- `#AssertFalse`, 451
- `#AssertTrue`, 451
- 异步方法, 347, 405, 407, 408, 449, 523, 524
- `@Authenticated`, 341, 342, 344, 345, 419, 449, 600, 610
- `@Component`, 341-345, 352, 391, 392, 395, 484, 489, 504
- `@ComponentScan`, 347, 348, 394, 395, 651
- `@Configuration`, 345-349
- `@Configuration. 参注解配置`
- `@Controller`, 341, 343, 348, 380, 393, 395, 416, 484, 505
- `@DecimalMax`, 451
- `@DecimalMin`, 451
- `@DeclareRoles`, 786
- `@DenAll`, 786
- `@Digits`, 451
- `@ElVariable comment`, 163–164
- `@Email`, 466–468
- `@EnableAspectAutoProxy`, 347
- `@EnableAsync`, 347, 405, 406, 409, 607, 708, 792
- `@EnableCaching`, 347
- `@EnableLoadWeaving`, 347, 608, 724
- `@EnableMBeanExport`, 347
- `@EnableScheduling`, 347, 405, 608
- `@EnableSpringConfigured`, 637
- `@EnableSpringDataWebSupport`, 653, 666
- `@EnableTransactionTransactionManagement`, 347, 558, 559, 607, 608, 792
- `@EnableWebMvc`, 348, 485, 663
- `@EnableWebSecurity`, 752, 776, 782, 809
- `@EnableWebSecurity.2`, 752, 776
- `@ExceptionHandler`, 489–499
- `@Future`, 451
- `@Injected`, 342, 345, 349, 610
- `@Injected`, 342, 411, 449
- `@Injected ChatService`, 414
- `@Injected LocalResolver`, 427, 428
- `@Injected MutableService`, 803
- `@Injected NotificationService`, 408
- `@Injected RepositoryBean`, 408
- `@Injected ServletContexts`, 533
- `@Injected SessionFactory`, 559
- `@Injected SessionRegistry`, 412
- `@Max`, 451
- `@Min`, 451
- `@ModelAttribute`, 66, 374–385
- `@MultipartConfig`, 66
- `@NotBean`, 466–468
- `@Null`, 451, 459, 461, 465, 471, 613
- `@Null`, 451
- `@Past`, 453
- `@PathVariable`, 362–363, 379, 492
- `@Pattern anonymous`, 451, 453, 466, 467
- `@PermitAll`, 786, 787
- `@Authorize`, 789–790, 796
- `@PostFilter`, 790, 796
- `@PreAuthorize`, 788–790, 795, 797, 809, 837, 835
- `@PreFilter`, 790, 795
- `@Qualifier`, 341-342, 838, 861
- `@Request`, 341, 343, 392, 393, 395, 416, 484, 601
- `@RequestBody`, 338, 365-366, 388, 487, 492, 505
- `@RequestHeader`, 362, 365
- `@RequestMapping`, 356-370
- `@RequestParam`, 361, 362, 363, 364, 367, 392
- `@ResponseBody`, 338, 369, 378–379, 489, 492, 493
- `@ResponseEnd`, 485, 482, 495
- `@RolesAllowed`, 788–788, 791, 795
- `@Scheduled methods`, 347, 404, 405, 408-409, 413, 371, 787
- `@Service`, 341, 343, 344, 392, 393, 400, 416, 484
- `@Size`, 452, 456, 468, 469
- `@Transactional`, 357, 559, 599, 602, 607, 618, 632
- `@ValidateOnExecution`, 449, 460
- `@Valid`, 454, 455, 459, 470
- `@WebControls`, 381, 385
- `@WebListener`, 133, 134, 210
- ActivateServlet, 126-127
- ActiveDirectory, 739, 743, 744, 751, 761
- ActiveDirectoryAuthenticationProvider, 762-765
- activities, 741-743
- `addHeader()`, 56
- `addHeader()`, 56
- `add()`, 149, 150
- `addListener()`, 133
- Address-Book in, 188-203
- Address-Book request, 190-192
- Address-of Flash, 114, 263-264
- Advanced Messageuing Protocol. 见 AMQP
- Advanced-Criteria, 667-668
- Advanced-Mappings, 695-716
- AffirmativeBased, 767
- aggregate functions, 170
- Ajax (Asynchronous JavaScript and XML). 见
- Ajax-queuing endpoints, 371, 378-301
- CSRF, 276
- getting data from server to browser
- Applets and Adobe, 263-264
- chunked encoding, 262
- event polling, 259-260
- HTTP/1 request, 264-267
- long polling, 70, 260-261
- requests, 114, 259-270
- same-origin policy, 481
- AMQP (Advanced Messageuing Protocol)
- block configuration, 535-536
- distributed message, 534-540



- introduction, 520
- JS compared to, 139, 520, 536
- MSMQ compared to, 139
- multicast, 537-539
- SOAP transport mechanism, 475
- AMQP-Messaging protocol, 537-539
- and keyword, 148
- and method, 673
- Android, 262-274
- annotation configuration, 15, 56, 64, 341, 343
- Annotations. 见注解:
- constraint annotations, JPA annotations
- annotation configuration (`@Configuration`), 15, 56, 64
- annotation metadata model, 443, 444-445
- anonymous authentication, 730-731
- abbreviate strings, EL, function, 226-227
- abstract entities, with common properties, 710–712
- `AbstractSecurityAuthenticationInitializer`, 749-750, 757
- `AcceptHeaderLocation`, 425, 487
- `Accept-language` header, 418, 422, 425, 426, 436
- access control lists (ACLs), 798-804
- Access Managers, 796-798
- Accessors, 125, 154, 161, 189, 190, 223, 341, 344, 378, 380, 553, 667, 709
- `AccountController`, 365, 391
- `AccessEndpoint`, 491, 492, 494
- actions, 178-275
- `ActionServlet`, 317-318
- API documentation, Java EE, 51
- APIs (application interfaces), 3
- Appenders, 311
- Apple Safari, 267, 283
- Applets, Java, 87, 263–264
- application clustering. 见集聚类
- application contexts, 485–488
- root application context, 394–404
- business logic, 396–399
- multiple user interfaces, 394–395
- understanding, 327–329
- web application context, 342, 374, 394 485–488
- application events. 见事件
- application listeners, 512–513, 536, 540, 774
- application messaging. 见消息
- application programming interfaces. 见 APIs
- application scope, 160, 101, 167
- application servers, 19–23
- class loading, 16
- Geronimo, 20, 21
- Glassfish, 22–21, 140, 141, 222, 447, 552, 724
- JBoss, 22–245
- Spring Framework, 324
- TomEE, 20–21
- web containers, 19–20, 180–181
- WebSphere, 22, 23, 141, 447, 500, 724
- application variable, 89
- application workflow, 107, 108
- `applicationEvent`, 338, 512, 518, 523
- `ApplicationEventPublisher`, 342, 512
- `ApplicationListeners`, 512–513, 536, 540, 774
- `applicationScope`, 165, 166
- arithmetic operators, 149, 152
- Arrays, 154
- `Arrays` class, 167–18
- AspectJ recounts, 607–608, 794, 796
- aspect-oriented programming, 325, 347, 353, 410, 745
- aspects, 325
- async operator(`=`), 148, 149, 172
- `AsyncContextPostProcessor`, 449
- `AsyncContext`, 70, 237, 238, 243, 244
- `asyncFilter`, 224, 246, 247
- Asynchronous JavaScript and XML. 见 Ajax
- asynchronous execution, 404–409
- asynchronous request handling, 237, 243–247, 249
- `AsyncServlet.java`, 244–247
- `Attachment`, 65, 68
- attachments, 721–722
- cross-domain, 114, 266
- cross-site scripting, 114, 155, 172, 777-816
- dictionary attribute, 628, 732
- GPU-based attacks
- injection attacks, 182
- main-in-the-middle attack, 115, 264, 731, 733, 777, 816
- replay attacks, 733, 734, 825, 840
- faction attacks, 113–114, 748, 755–775, 816, 820
- `autoFlush`, 83–84
- `buffer` attribute, 83–84, 96
- constraint annotations, 452
- attribute, 79, 84
- `contentType` attribute, 79, 84
- `data-jpa:query` element, 649
- `data-jpa:repositories` element, 647–648
- dynamic attributes, 215, 216, 220
- `Expires` attribute, 108, 109
- `HttpOnly` attribute, 109, 114, 118
- `isGenerated` attribute, 83, 96, 218
- `isErrorPage` attribute, 7, 90
- `isThreadSafe` attribute, 84
- `language` attribute, 79, 218
- `Max-Age` attribute, 108, 109, 118
- `params` attribute, 359
- attributes (continued)
- `prefix`, 86, 179
- `removeAttribute()`, 123, 124, 133
- request attributes, 52, 89, 99, 100, 120
- attributes (continued), 356–360
- `Secure` attribute, 109, 118
- tag directive, 218–219
- `value` attribute, 86, 179, 180
- auditing, 300, 302, 547
- authentication, 729–740
- anonymous, 730–731
- authentication compared to, 729–730, 819
- basic access, 732–736
- biometrics, 732–738, 739
- claims-based, 723–739
- client certificate authentication, 737, 739, 766
- defined, 729–730
- digest access, 736
- form, 736
- Integrated Windows authentication, 736–737
- mechanism, for web services, 177–818
- Microsoft Windows authentication, 736–737
- multi-factor, 729–740
- OpenID, 762–764, 819
- password, 731–738
- rememberMe, 752, 761, 765, 766, 773, 784
- smart cards, 738, 739, 818
- username-password, 102, 737
- authentication providers
- `ActiveDirectoryLdapAuthenticationProvider`, 761–762
- custom, 766–773
- `DataAuthenticationProvider`, 734, 748–749, 753, 759
- `LdapAuthenticationProvider`, 760–762
- OpenID, 762–764, 819
- other, 766
- rememberMe, 752, 761, 765, 776, 783, 784
- user details, 749
- `InMemoryUserDetailsManager`, 749, 752, 753, 758
- `JdbcUserDetailsManager`, 758–759
- `LdapUserDetailsService`, 759
- `UserDetailsService`, 748–759, 764, 765, 805, 807, 833, 853
- Authentication-App Project, 749–754, 767, 769, 771
- `AuthenticationController`, 385, 409, 470, 774, 857
- `AuthenticationInterestedParty`, 522, 524, 533
- `AuthenticationPrincipal`, 782, 808, 856
- authorization
- activities, 741–743
- authentication compared to, 729–730, 819
- claims-based, 743, 761
- Customer Support group, 804–814
- declarative, 780–794
- groups, 741–743
- identities, 740–741
- permissions, 741–743
- principals, 740–743
- roles, 741–743
- understanding, 740–743
- ways to use, 745

### 错误请求 – 浏览器

错误请求 (400 状态码), 264, 265, 470, 499, 482, 822

- 基础仓库, 613–618
- 基础语法, 145–146
- 基础字面量 (base-literals), 15
- Base64, 266, 365, 734
- 基础访问认证, 732–736
- `basic.tag`, 229–230
- BCrypt, 628–630, 632, 657, 732, 748, 758, 845

## Bean 定义

- 反模式, 353
- `ReloadableResourceMessageSource`
- 安全考虑，利用, 349–353
- Bean 后置处理器 (bean post-processors), 449–450
- Bean 验证 (349), 441–472
    - 注释元数据, 443, 444–445
    - Bean 后置处理器, 449–450
    - 内置约束注解, 451–452
    - Spring Framework 中的配置, 445–450
    - 客户支持, 470–472
    - 已定义, 442–443
    - 员工 (Employee), 422–443, 452–454, 458–463, 465
        - Hibernate Validator, 444, 446–448, 454, 457, 458, 469–471
    - 国际化 (i18n), 448–449
    - JSR 303 标准, 440, 443, 472
    - 地化 (L10n), 448–449
    - Maven 依赖, 441–442
    - 方法返回值, 459–460
    - 方法验证, 458–465
    - MVC 递归验证, 454, 455, 459, 470
    - RESTful Web服务, 488–489
    - 在 Spring Framework 配置中, 445–450
    - 验证组, 452, 455–460
    - Bean Validation 约束扩展项目, 453, 469
- `BeanFactory`, 338, 342
- `BeanFactoryAware`, 362
- beans
    - 框架 beans, 338, 341, 342, 343, 345, 346, 372, 449
    - Spring 管理的, 326, 327, 328, 391, 405, 470, 410, 427, 445, 489, 512, 608, 787
    - `<beans>` XML 空间, 338, 350
- 访问者令牌 (bearer tokens), 819, 830–831, 832, 833, 834, 852, 853, 857, 861
- `BigDecimal`, 152, 153, 451, 570, 576, 695
- `BigINT`, 576
- `BigInteger`, 152, 451, 570, 576
- `BINARY`, 576
- 二进制 JSON, 302, 346
- 二进制大对象 (BLOBs), 594–595
- 二进制消息，WebSocket 集群, 268–287
- 二进制操作 (-1), 149, 150
- 生物识别, 737–739
- 位掩码, 799
- Blackberry 浏览器, 267
- `blank.jsp`, 78
- BLOBs. 二进制大对象
- `BodyController`, 396–398
- Body 内容, 213
- `BodyTag`, 225
- `BodyTagSupport`, 226
- 书条目, 568–577
- `BOOLEAN`, 576
- `Bootstrap.java`, 384–385
- 日志，Spring Currency, 767–769
- 多个启动类, 768–769
- Spring Framework, 329–336
- 部署器描述符, 330–332
- 在初始化器中程序化, 322–336

```
71–75
```

- 中括号 `[]`, 14, 145, 154, 159, 168
- 断点点
    - Eclipse, 38–79
    - IntelliJ IDEA, 34, 35–79
- 代理器 (broker), 511, 536–537
- 代理器集群, 311, 519, 535
- 浏览器，以及 WebSockets
    - Apple Safari, 267, 283
    - Blackberry, 267
    - 从服务器获取数据
        - Applets 和 Flash, 263–264
        - 分块编码, 262
        - 轮询, 259–260
        - HTTP1.1 升级, 264–267
        - 长轮询, 70, 260–261
        - Google Chrome, 36, 263, 280, 283, 379, 497, 736
        - Internet Explorer, 36, 253, 267, 280, 377, 379, 736
    - Mozilla Firefox, 36, 253, 267, 280, 836, 737
    - Opera, 267
    - WebSockets, 869

## BSON-ClusterNode.java

- BSON, 302, 546
- 树索引, 665
- `<buffer>`, 96
- 属性, 83–84, 96
- `BufferedReader`, 54
- 约束注解, 451–452
- 业务逻辑
    - Cluster-Service, 392
    - 到 WebSockets 的层, 409
    - 从 WebSockets 移动, 396–399
    - 持久化, 391–392
    - 用户界面, 390–391



- 规则, 422, 443, 445, 463, 464
- 服务, 392
- websockets, 409–415
- 字节码, 53
- 字节码织, 723, 786
- 字节, 153
- 编码器和解码器, 289–291
- JavaScript 应用, 294–296
- 服务器端点, 291–294
- `ChatController`, 385, 437
- `EndPoint.java`, 292–294
- `ChatMessage`, 290
- `ChatCodec.java`, 290–261
- 检查，`MultiValueServlet`, 59–61, 91, 92
- Chrome, 36, 253, 280, 389, 479, 736
- 分块编码, 262
- 基于 claims 的授权, 738–739
- 的授权, 743, 761
- 类加载器
    - 架构, 15–16
    - 优先类委托, 16, 17
    - 父类委托模型, 16
    - 范围, 88
- 客户端 API，WebSocket API, 271–272
- 客户端证书认证, 737, 739, 766
- 客户端凭据, 820–840
- 客户端 Gradle, 288, 834, 837, 839
- 客户端随机数 (nonce), 733, 734
- `clientHasAnyRole(String)`, 837
- `clientHasRole(String)`, 837
- client。参见 OAuth 2.0
- 机密, 826
- 已定义, 819
- OAuthia, 815–829
- 公共, 826, 827
- 客户端-服务器范式, 510

- CLOBs. 参见字符大对象
- 闭包 (Closure), 5
- 闭包, 15。参见 lambda 表达式
- `ClusterServerMulticaster`, 527–529, 531, 537–539
- 配置, 515–517
- 描述, 513–517
- 可分发的 Java EE Web 应用, 513–514
- 会话聚类, 139–141, 514–515
- 使用多个部署模拟, 533–534
- 测试, 533–534
- Tomcat, 515–517
- WebSockets, 284–288, 518–519
- `ClusterManager`, 331–533, 537
- `ClusterMessagingEndpoint`, 528–529, 530, 537
- `ClusterNodeEndPoint.java`, 286–287
- `ClusterNodeServlet.java`, 285–286

```
<choose>, 185, 191, 206
<:each, 186–187, 191, 213, 220, 380
<:forTokens, 177–188
<:if, 184–185, 191, 206, 232
<:import, 188–189, 212, 213
<:charOut, 185, 189, 206
<:out, 182, 191, 220, 221
<:param, 121, 183, 188, 212
<:remove, 189
<:set, 189
<:url, 121, 178, 183, 188, 206, 219
<:with, 185, 191, 202, 206
```

- 回调 (callback), 823
- `CasAuthenticationProvider`, 766
- 级联样式表 (Cascading Styles)。参见 CSS
- 代理, 406, 407, 600–601, 726, 786, 846
- 链式管道, 168
- 字符编码
- `getCharacterEncoding()`, 53
- `setCharacterEncoding()`, 55, 79
- 字符大对象 (CLOBs), 594–595
- 字符, 153
- css 样式表, 288–296

## 控制器建议 (controller advice)

- 随机数 (nonce), 733–735
- 代码重复, 634–638
- 集合字面量, 153–154
- 附件, 721–722
- 请求, 477–492
- 集合, 158–160
    - Collections API, 153, 158, 159, 723
    - Maps, 153, 154, 709, 723
    - 队列, 158
    - 返回, 170
    - Sets, 153, 158, 159, 723
- 列名, 702–703
- Comet, 261。也参见长轮询
- 逗号运算符 (), 149
- 通用对象, 364, 492, 683, 774
- 通用注解 API, 708–786, 791, 792, 795
- Apache 通用日志, 307, 308, 309, 319, 340, 345
- 比较器 (Comparator), 169, 170
- 关系运算符, 149, 150
- 编译时，约束注解, 457–458
- 复杂条件查询, 666–670
- 添加自定义搜索方法, 668–670
- Advanced-Criteria 项目, 667–776
- 从搜索输入创建, 670–674
- 和或方法, 675
- 复杂数字, 158
- 组件扫描, 341–348, 392, 395, 384, 489
- 压缩 64 位指针, 9
- 压缩过滤器, 234–235, 247–253, 255
- Compression-Filter 项目, 247–248
- `CompressionFilter.java`, 249–253
- 并发, 69, 757
- 并发连接限制, 263
- 并发编程语言，Erlang, 536
- 机密型客户端, 826
- CONFIG 日志级别, 304
- 配置变量, 89
- 配置详情，日志级别, 304
- 配置器，WebSocket, 411–412
- `configure(AuthenticationManagerBuilder)`, 751, 752, 758, 771
- `configure(HttpSecurity)`, 752, 753, 771, 797
- `configure(WebService)`, 752–775
- 配置顺序和令牌服务, 834–836
- 连接池, 546, 562, 563, 564, 602
- 连接超时, 260, 262, 263
- 基于共的, 797
- 控制台日志, 301
- 约束注解
    - 注释元数据模型, 443, 444–445
    - 属性, 452
    - 构建, 451–452
    - 自定义, 469
    - 已定义, 444
- 员工条目, 442–443, 452–454, 458–468
- 员工 POJO, 452–454
- 时的合法性, 457–458
- 方法参数, 459
- 方法验证, 458–465
- 编程切面, 458
- 递归验证, 454–455, 450
- 验证组, 452, 455–460
- ConstraintValidators
    - 创建, 469
    - 已定义, 444
- `@AEmail`, 466
- 生命周期, 469
- `@NotBean`, 466–468
- `ConstraintViolationException`, 462, 464, 469, 468, 480
- Contact POJO, 190
- 包含头, 56
- 内容协商, 377–380
- 内容类型，`@RequestMapping`, 360
- `contentType`, 79, 84
- `Content-Type` 头, 54, 79, 189, 370, 375, 376, 377, 378
- 上下文项, 61, 82, 99, 93, 165, 196
- `ContextParametersServlet`, 62
- `contextParameters.jsp`, 92, 93

# controller方法 – CSS

## 控制器方法

- 参数, 360–368
- 有效返回类型, 368–378
- 控制器 (Spring MVC controllers), `RequestMapping`;
- 参见 reports; Customer-v10 项目, 384–388
- Maven 依赖, 335–336
- 将业务逻辑移动到 service, 396–399
- 参数校验, 462–463
- RESTful Web 服务, 484–496
- 将 RESTful 请求映射到控制器方法, 491–495
- 按类型注解分离, 484–485
- 分离 web 和 REST 应用上下文, 485–488
- 将服务转换为控制器, 385–386
- 总结, 387–388
- 用户界面逻辑, 393

## Controller-Repository 模式

- MVC, 390–391, 416
- 程序的逻辑类型, 391–393
- 转换注解, 696–698
- Cook, 818

```
<url>: 112, 121, 178, 183–188, 206, 212, 219
<when>: 185, 191, 192, 206
```

## 核心 TLD

- c.tld 文件, 209, 216
- 文档根, 211–212
- 函数, 216–217
- 初始声明, 211
- 监听器, 212
- 位置, 211
- 标签文件, 216
- 标签库扩展, 217
- 标签, 212–216
- 验证器, 212

- Couchbase, 547
- count: 操作, 170
- Crash/Fatal Error, 日志级别, 304
- `createTicket()`: 68, 69, 130, 230
- `createUser()`: 381, 383
- 凭据
    - 客户端凭据, 820–840
    - Client Credentials Grant, 828, 834, 837, 839
    - 已定义, 820
    - Resource Owner Password Credentials Grant, 828–829, 837, 839
    - 临时边界条件, 820–824
    - 令牌凭据, 820–824

- criteria API. JSP API Criteria
- 创建 Session: Java, 71–674
- 跨内容透镜, 335
- 跨域攻击, 266
- 跨源资源共享 (Cross-Origin Resource Sharing), 481
- 跨站请求伪造. CSRF
- 跨站脚本 (XSS), 114, 155, 182, 217
- CRUD 操作
    - Jpa, 611–612
    - 程序化触发器, 717–720
    - RESTful Web 服务, 476
- CSRF (跨站请求伪造), 735, 777–788
- Authorization Code Grant, 827

```
<cookie-config>, 116, 117, 318, 337
```

- cooks, 108
- `document.cookie` DOM 属性, 114
- `getters()`, 55
- `issecure`, 115
- `JSESSIONID`, 110, 111, 112
- `remusername`, 110
- Secure cookie 标记, 114, 158
- session ID, 110, 114–117, 166, 817, 825
- `Set-cookie` headers, 108, 109, 110
- Spring Security 过滤器, 750
- 复制粘贴方法, 163
- 核心标签缓存 (映射), 182–192
- Abstract-Build Project-index, 190, 201
- `<include>`: 185, 191, 206
- `<each>`: 186–187, 196, 201, 213, 220, 380
- `<for:Tokens>`: 187–188
- `<if>`: 184–185, 191, 205, 206, 232
- `<import>`: 188–189, 212, 213
- `<otherwise>`, 185, 191, 206
- `<out>`: 182, 191, 206, 220, 221, 232
- `<param>`: 121, 183, 188, 212
- `<remove>`, 189
- `<set>`: 189

## CSS (层叠样式表)

- `chat.case` 样式表, 289
- `configure(WebSecurity)` 方法, 752
- EL 表达式, 147
- `main.case` 样式表, 289
- `/resource/styles/login.css`, 228, 229, 230

# c.tld 文件 - <data:>

- `/resource/stylesheet/main.css`, 228, 230
- Spring Framework themes, 429
- tic-tac-toe 游戏, 273, 278
- c.tld 文件, 209, 211, 216. 参见 TLD
- 货币转换, 193, 199
- 自定义注解, 466–469
- 自定义类型. 参见类型
- 自定义视图, 386–387
- 自定义 multicaster, 525, 527–529
- 自定义标签和函数, 209–252
- 日期格式化标签, 221–224
- EL 字符串, 226–227
- Java 替换为自定义标签, 227–232
- Maven 依赖, 209–210
- 标签指令, 217–219
- Template-Tags, 219–228
- 依赖注入 (DI), 325, 353, 445
- 部署器
    - 引导 Spring Framework, 330–332
    - 已定义, 15–16, 46
    - 过滤器, 237
    - Json 属性配置, 94–97
    - `<jsp-config>`, 95, 116, 146, 170, 179–180, 211–212, 220
    - `<script-invalid>` 标签, 95, 96, 217, 222
    - 添加 Servlet, 44–60
    - `<session-config>`, 116–118, 129, 160
    - 模板代码, 336–337
- `<description>`, 211, 212, 213, 214, 215, 216, 218, 584
- `destroy()`, 45–46, 50, 235, 290, 586
- DI. 参见依赖注入
- 方言, Hibernate ORM, 605–606
- 字典数组, 628, 732
- 散列访问认证, 733–739
- disJs, JSs, 79, 83–86
- 可发现性, 477–499
- Discussion-Board, 396–408
- `DiscussionController`, 396, 397, 399
- `dDispatcherServlet`, 328–335, 330, 342, 344, 426–427
- `dDispatcherServlets`, 328–335, 339
- `<display-name>`, 47, 58, 94, 211, 213, 216
- 差异操作, 168
- 可分发 EE Web 应用, 513–514
- 分布式消息. 参见 JMS
- AMQP, 534–550
- 问题, 518
- sits, 717–518
- `div`, 148, 149, 150
- `dive()`, 19, 140
- `document.cookie` DOM 属性, 114
- `doDelete()`, 43
- `doEndTag()`, 223, 225
- `doFilter()`, 235, 236

# D

- `DaoAuthenticationProvider`, 734, 748–749, 753, 759
- Data Access Objects, 328, 748
- 来自服务器的数据
    - Applets 和 Adobe Flash, 263–264
    - 分块编码, 259–260
    - 频繁轮询, 259–260
    - HTTP.1 利用功能, 264–267
    - 长轮询, 270, 261
- 数据持久化, 使用 JPA;
- 数据存储, 仓库, 399–404
- 数据类型, 576

```
<data:jackson2-popular>, 647
<data:jackson-popular>, 647
<data:jpa:auditing> 元素, 649
<data:jpa:repositories> 属性, 647–648
elements, 647
```

```
<data:unmarshaller-populator> - doFilter()
```



# 索引

## <data:unmarshaller-populator>
`<data:unmarshaller-populator>`, 647

## A
- 数据库访问标签. 参见 NoSQL
- `TransactionManager`, 599, 620, 621
- Date and Time API (310)
- `Contact`: POJO, 120
- 日期和时间占位符, 420
- `DayOfWeek` 枚举, 117
- `@Future`, 451
- `ObjectMapper`, 377
- `java.time.TemporalAccessor`, 221
- JDBC, 592
- 日期和时间类型, 592, 594, 652, 692, 695
- 日期格式化标签, 221–224
- `addHeader()`, 56
- `<fmt:parse-Date>`, 198, 199, 201, 202, 221
- `<fmt:parse-Date>`, 198, 199, 204, 222
- `<fmt:parse-Date>`, 198, 199, 204, 222
- `DateTag`, 227
- 映射的 (annotation-based), 592–594
- `setDate()`, 56
- `DATETIME`, 576
- `DayOfWeek` 枚举, 137
- Debug, 日志级别, 304
- 缺点, 298–299
- Servlets, 49–51
- web 应用, Tomcat
- Eclipse, 35–39
- IntelliJ IDEA, 30–35
- `DECIMAL`, 376
- 声明, JSs, 79, 83–86
- 声明式授权, 780–794
- 解码器和编码器, 289–291
- 解密. 参见加密
- `default-content-type`, 95, 96, 336
- `DefaultAuthenticationProvider`, 766
- 评估的 EL 语法, 145, 146, 215
- `<deferred-method>`, 146, 215
- `<deferred-syntax-allowed-literal>`, 96, 97, 146
- `<deferred-value>`, 146, 215
- DELETE
    - CSRF 令牌, 75, 776
    - `doDelete()`, 43
    - HTTP 方法, 43, 52, 359
    - OAuth , 838
    - RESTful Web 服务, 476, 483
    - statement, SQL 库, 203
- `anyAll`, 783
- `doAuthClient()`, 837
- 依赖注入 (DI), 325, 353, 445
- 部署器
    - 引导 Spring Framework, 330–332
    - 已定义, 15–16, 46
    - 过滤器, 237
    - Json 属性配置, 94–97
    - `<jsp-config>`, 95, 116, 146, 170, 179–180, 211–212, 220
    - `<script-invalid>` 标签, 95, 96, 217, 222
    - 添加 Servlet, 44–60
    - `<session-config>`, 116–118, 129, 160
    - 模板代码, 336–337
- `<description>`, 211, 212, 213, 214, 215, 216, 218, 584
- `destroy()`, 45–46, 50, 235, 290, 586
- DI. 参见依赖注入
- 方言, Hibernate ORM, 605–606
- 字典数组, 628, 732
- 散列访问认证, 733–739
- `disJs`, JSs, 79, 83–86
- 可发现性, 477–499
- Discussion-Board, 396–408
- `DiscussionController`, 396, 397, 399
- `dDispatcherServlet`, 328–335, 330, 342, 344, 426–427
- `dDispatcherServlets`, 328–335, 339
- `<display-name>`, 47, 58, 94, 211, 213, 216
- 差异操作, 168
- 可分发 EE Web 应用, 513–514

## doGet() – 实体

### `doGet()` – 实体
`doGet()`, 43, 44, 50, 51, 57–58, 59, 60, 65, 66–67
`doHead()`, 43

`[fn:toLowerCase(String)]`, 156
`[fn:toUpperCase(String)]`, 156
`[fn:trim(String)]`, 156

域管理服务器, Fish5, 55
域属性, 108

局限性, 157–158
lambda 表达式, 157–158
字面值, 151–154

`<domain>`, 117
`doOptions()`, 43
`doPost()`, 43, 51, 57–58, 59, 67, 78
`doPut()`, 43, 51

Maven 依赖, 143
运算符优先级, 148–150
放置, 146–147

`dot()` 运算符, 149, 150, 158
`dotTrace()`, 43
`double`, 152, 155
`DownloadView`, 371, 386–387

用途, 144
保留关键字, 148
作用域, 160–160

西洋跳棋–7
代码重复, 634–638
动态属性, 215–216, 218, 220
动态查询。另参见 criteria 查询

最简单表达式语言, 144
与 SpEL 比较, 74
静态字段，访问, 156–157
静态方法访问, 156–157

被规定的, 666–667
创建难度, 674
Querydsls, 642, 645

Stream API, 167–172
字符串字面量值, 151–152
语法
- 基础语法, 145
- 延迟 EL 语法, 145–146

`<dynamic-attributes>`, 215–216, 222
`dynamicInclude.jsp`, 85

## E

即时 EL 语法, 146, 146
松散类型, 147
对象属性和 154–155
使用 EL 语法编写, 147–170

EAR 文件（企业归档）, 17, 583–584
Eclipse。以及 IntelliJ IDEA
- 断点, 38–39, 77
- 调试 Web 应用, Tomcat, 35–39
- Jdt 编译器, 26–27, 39

Tomcat 版本, 21, 181
Web 应用技术, 8
嵌入式类型, 609–712, 713, 715
Employees 条目, Bean Validation, 442–443,
452–454, 458–468
`EmployeesService`, 459–464

Luna, 37
示例–调试 Eclipse 项目, 38–99
Eclipse, 551–552, 564, 574, 608, 705
ECMaScript, 154

空运算符, 148, 190
编码器和解码器，支持聊天, 289–291
Base4, 634
加密 Cookie, 115
加密过滤器, 234–235, 253
HTTPS, 117, 118
负载均衡器, 140
资源所有者密码凭据授权模式, 822

`editUser()`, 381
EJB（企业 JavaBean）, 5, 6, 17, 22, 551
583. 另参见 Spring 框架

EL 表达式（Java 统一表达式语言）,
147–175。另参见 JSTL
集合, 180–169

枚举, 175
历史, 144
隐式 EL 作用域, 161–166
隐式变量, 160–161, 167
用 EL 替换 Java 代码, 172–174
JPs, 13

JSTL 函数库, 155–156, 172, 178
`${fn:contains(String)}`, 155, 217
`${fn:escape(String)}`, 155, 162, 182
`${fn:join(String)}`, 156, 196
`${fn:length(Object)}`, 156, 164

SSL 会话 ID, 115, 116, 117, 118, 140, 141,
142, 750
SSL/TLS, 115, 265, 267

企业归档。参见 EAR 文件
企业 JavaBean。参见 EJB
实体

- 抽象的，带有公共属性, 710–712
- ACLs, 803–804

## 实体（续）

- Employee，Bean Validation, 442–443, 452–454, 458–468
- 查找，方法, 639–442
- 映射类, 710–712, 717, 718, 720
- 实体中的 `@RequestBody`, 669–703
- 响应实体, 328, 369–370, 375–380
- 存储在多个表中, 716–717
- 实体字段, 569
- 实体监听器, 719–720
- 实体管理器，线程, 599–600
- 实体映射, 561–581–595
- 作为实体属性, 590–592
- EL 表达式, 157
- 枚举-日期, 590–595
- 环境感知, 342
- 等运算符, 148, 149, 150
- 关系运算符, 149, 150
- 等方法, 150
- 国际化 (i18), 433–436
- 持久化实体, 548
- RESTful Web 服务, 488–491
- 错误处理，过滤器, 235
- 日志级别, 304
- 错误请求, 237
- `<error-declared-namespace>`, 96, 97
- `errorPage`, 885
- EL 错误, 145, 146, 147, 151, 152, 159
- 错误/崩溃，日志级别, 304
- HTTP 状态码
    - 101 切换协议, 264, 265
    - 204 无内容, 482, 483, 494
    - 302 临时重定向, 109, 110, 311, 371
    - 303 其他， 371, 736
    - 307 临时重定向, 736
    - 400 错误请求, 264, 265, 479, 490, 482
    - 401 未授权, 480, 481, 732, 734, 822, 824, 830
    - 403 拒绝, 480, 481, 785, 787
    - 404 未找到, 179, 237, 481, 483, 488, 493
    - 405 方法未允许, 44, 480, 482
    - 406 不接受, 480
    - 415 不支持的媒体类型, 480
    - 426 需要升级, 264
    - 500 内部服务器错误, 235, 237, 480, 488
- `isErrorPage` 属性, 84, 90
- JSP 编译时, 157
- 事件日志, 302
- 事件多路器
    - `EventListenerMulticaster`, 527–529, 531, 537–539
    - 自定义, 525, 527–529
    - 标准, 527
- 事件（应用事件）。另参见消息
    - 创建, 520–521
    - 分布式的，使用 AMQP, 534–540
    - 发送给的消息, 525
    - 发布, 342, 523–524
    - 发送和接收, 529–530
    - 订阅, 522–523
    - 更新到状态, 526–527
- `<example>`, 216, 217, 219
- 异常翻译, 601–602
- 异常变量, 84, 90
- 执行器, 404–405
- `Expires` 属性, 108, 109
- 显式视图, 371–373
- 表达式语言。另参见 EL
- JSP 表达式, 80–81, 102。另参见 EL 表达式
- `extends` 属性, 84
- 外部生命周期事件处理器, 719

## F

`Facelets`, 775
故障转移
- 代理集群, 551
- 控制台日志, 301
- 会话故障转移, 442
`false` 关键字, 148, 151
FatalError/崩溃，日志级别, 304
`Fiddler`, 109, 266, 366
文件上传到 Servlets, 64–69
档案保管局, 664

## Filter - 双工通信

`Filter`, `MessageSourceResourceBundle`, 423–424
过滤器链, 235–236, 242, 267, 768, 769, 771, 775, 777, 782, 787, 839
过滤器操作, 168

`Filter-Async`, 243
`Filter-Chain`, 235, 236, 241, 248, 250
`Filter-Order` 项目, 241–243
过滤器, 233–255

- 注解, 238
- 异步请求处理, 237, 243–247, 249, 255
- 身份验证过滤器, 234, 254–255
- 压缩过滤器, 234, 247, 253
- Complex-Filter 项目, 247
- `CompressionFilter.java`, 249–253
- Customer-Support, 234–255
- 部署用户, 237
- 加密过滤器, 234, 233, 255
- 错误处理, 239
- 日志过滤器, 248–249, 767–768
- 过滤器分发器, 236–237
- 过滤器 URL, 236
- 映射, 239, 241
- 顺序, 239–243
- 实际用途, 234, 235–247
- 程序化配置, 238–239
- `RequestLogFilter.java`, 248–249
- 响应过滤器, 234, 235, 247–253, 255
- 与 Servlets , 234
- Filters, List, 2, 311–312
- 过滤器，Spring Security, 749–750

- `firstOrderId`, 171
- 日志级别, 304
- 过滤器级别, 304
- 哈希, 337
- 标记, 316–317, 747
- `Flash`, Adobe, 109, 214, 263–264
- 平直文件, 301–302, 544
- `Float`, 451, 576
- `float`, 152, 451, 576
- `fmt` 命名空间。另参见国际化格式库
- `<fmt:bundle>`, 196–197
- `<fmt:formatDate>`, 198–199, 201, 202, 221
- `<fmt:formatNumber>`, 199–200, 420
- `<fmt:message>`, 194–195, 196, 201, 430, 431, 432
- `<fmt:parseDate>`, 198–199, 204
- `<fmt:parseNumber>`, 199–200
- `<fmt:requestEncoding>`, 197
- `<fmt:setBundle>`, 194, 196–198
- `<fmt:setLocation>`, 192, 197
- `<fmt:setTimeZone>`, 197–198
- `<fmt:timeZone>`, 197–198
- `fn(String, String, 155, 155`
- `fn:escapeXml(String)`, 155, 164, 182
- `fn:join(String)`, 156
- `fn:length(Object)`, 156, 64
- `fn:toLowerCase(String)`, 156
- `fn:toUpperCase(String)`, 156
- `fn:trim(String)`, 156
- 函数签名, 217, 226

## JPA 全文索引 - 错误处理

JPA 全文索引, 676–688
MySQL 表格, 677–678
可移植的, 684
可搜索存储库, 778–684
全文检索，Apache Hibernate 函数库。另参见自定义标签和函数库

- `<function>`元素, 216–217
- `function-class`元素, 217, 226
- 函数库, 155, 152, 175, 278。另参见 JSTL
- `${fn:contains(String)}`, 155
- `${escapeXml(String)}`, 155, 164, 182
- `${fn:join(String)}`, 156
- `${fn:length(Object)}`, 156, 64
- `${fn:toLowerCase(String)}`, 156
- `${fn:toUpperCase(String)}`, 156
- `${fn:trim(String)}`, 156

- `getInt()`, 55
- `getLastAccessedTime()`, 124
- `getLocal()`, 223, 418, 426, 435
- `getLocales()`, 418
- `getLocalizedMessage()`, 435
- `getInactiveInterval`, 124
- `getOrientation(Locale)`, 430
- `getOutput(Stream)`, 55, 89
- `getParameter()`, 33, 165
- `getPropertySet()`, 53
- `getParameterNames(String)`, 53
- `getPort()`, 64
- `getParts()`, 64
- `getRenderer()`, 54
- `getRequestURL()`, 398, 399, 401, 402
- `getServerPath()`, 54
- `getSession()`, 55, 120–121
- `getStatus()`, 56

## G

- `game.jsp`, 279–282
- `Game-Site`, 273
- `get`运算符, 148, 149, 150
- `getServiceImpl`, 337, 338, 340, 348
- `GenericBaseRepository`, 616
- `GenericJpaRepository`, 616, 717, 718, 720
- `GenericRepository`, 614, 615, 624, 638, 654, 656, 657
- `GenericServlet`, 43, 44, 50, 51, 57–58, 59, 60, 65, 66
- `Geronimo`, 21

- `doGet()`, 43, 44, 50, 51, 57–58, 59, 60, 65, 66
- OAuth 客户端, 338
- 行信息, 43
- `GlassFish`, 21, 22, 140, 141, 181, 222, 447, 515, 517
- GlassFish 域管理服务, 51
- 全局方法注解, 745, 793–794, 796–797, 803, 808, 819, 854–855
- `Google Chrome`, 256, 272, 260, 283, 379, 497, 736, 737

- 基于 GPU 的攻击, 732
- `GrantedAuditors`, 744, 745, 749, 752, 766, 782, 783, 784, 786, 787, 834
- 图形数据库, 547

- `GenericServiceImpl`, 337, 338, 340, 348
- `Greep`, 664, 665

- `Groovy`, 5, 324
- 组

- 授权权限, 741–743
- 验证组, 452, 455, 460
- `gt` 运算符, 148, 149, 150

## H

- `Halff`, Larry, 818, 819
- `Hammer`, Eran, 819, 820, 831
- `HandlerInterceptor`, 427–428
- 处理错误。另参见 错误处理

- `FormatDate:Tag`, 222

## 手 - HttpSessionIdListener

握手
- HTTP/1.1 升级功能, 264, 265, 267
- `modifyHandshake()`, 292, 439
- SSL, 115
- WebSockets, 269, 271, 273, 292
硬删除, 483
`hasAnyAuthority`, 783, 784, 785, 837
`hasAnyRole`, 783, 784, 837
`hasAnyScope String`, ...
`hasAuthority`, 783, 784, 785
`hasIPAddress`, 783, 784
`hasPermission`, 783, 791, 795, 799, 802, 813
`hasRole`, 783, 837
`hasScope (String)`
HD 视频流媒体, 268

粘性会话，141
Tomcat, 20, 22
`HAC-SHA1`, 821
`HomeHomeController`, 371–374, 378, 430, 533
HQL.se Spring Hibernate 查询语言
HR-项目门户, 445–465
HTML 注释, 81–82
HTML 标签, 75, 87, 147, 182, 183, 207, 215, 220
383. 另见 JSONs
HTTP Cookie, 266
HTTP 序言, 266
HTTP 请求方法限制, 358–359
HTTP 安全标头, 777–779
HTTP 会话，见 sessions
HTTP 状态码

HEAD
- `doHead()`, 43
- HTTP 方法, 439
- OAuth 客户端, 338
- RESTful Web, 481–482
《Head First 设计模式》(O'Reilly), 370
已死的, 165, 166
`headerName`, `@requestMapping`, 359–360
`headerValue`, 165, 166
`HelloController`, 337–338
Hello-User 项目, 61–56
Hello-World 项目, 44–56
Hello-World JSP 项目, 75–76, 78, 81, 85
十六进制编码, 734
十六进制字符串, 595
Hibernate ORM

- 101 切换协议, 264, 265, 267
- 204 无内容, 482, 483, 498
- 302 临时重定向, 109, 110, 311, 371, 736
- 303 见其他, 371
- 307 临时重定向, 736
- 400 请求错误, 264, 265, 479, 490, 498, 822
- 401 未授权, 480, 781, 732, 734, 735, 822, 824, 830
- 403 拒绝, 480, 481, 787
- 404 未找到, 179, 237, 481, 483, 488, 493, 498
- 405 不允许, 440, 482
- 406 不可接受, 460
- 415 不支持的媒体类型, 480
- 426 需要升级, 264
- 500 内部服务器错误, 233, 235, 480, 488
- RESTful Web 服务, 479–480
- HTTP/1.1 升级功能, 264–267
- `HTTPD`, Apache, 140, 301, 504, 515
- `HttpServlet`
    - HTTP 类型的空实现, 43
    - 扩展, 43–44, 51
- `HttpServletRequest`, 52–55, 71, 89, 97, 98, 100, 112, 120, 234, 235
- `HttpServletResponse`, 55–56, 76, 83, 89, 112, 234
- `HttpSessionSessionActivationListener`, 142, 514
- `HttpSessionBindingListener`, 133
- `HttpSessionIdListener`, 133–134, 115, 473

简要查看, 352–359
标准, API, 618
方言, 605–606
Hibernate Validator, 444
映射文件, 552–554
Maven 依赖, 注意, 564
使用原因, 552
Session API, 554–556
Hibernate 查询语言 (HQL), 551, 556
Hibernate Search, 664–692
Hibernate Validator, 446–448, 454, 457, 469, 471 另见 Bean Validation
高可用
- 代理集群, 535
- 集群, 510, 514
- GlassFish, 22
- JBoss, 22
- LDAP, 760

## HttpSessionListener – 国际化

`HttpSessionListener`, 133–134, 135, 212, 292, 410, 473
混合配置, Spring Framework, 340–345
应用程序状态, 477
`HyperSQL`, 350, 505, 684
超文本语言, 479

初始化参数
- 上下文初始化参数, 61–62, 89, 92, 165, 196, 200, 432
- Servlet 初始化参数, 25, 61, 62–64, 39
`initDestroyPostProcessor`, 449
`AbstractWebApplication`, 749–750, 769
启动 Spring Framework, 332–336
`ServletContainer`, 612, 118, 138, 230, 332, 335, 418, 749
`WebApplicationInitialization`, 333, 335, 348, 371, 384, 749
`initParam`, 165
注入实例, 610–611
注入攻击, 182
`InMemoryDiscoveryRepository`, 402
`InMemoryRepository`, 403
`InMemoryUserDetails`, 749, 752, 758
输入绑定, 364–365
`InputStream`, 53, 68, 272, 286, 290
源码, 115
实例, 148
即时消息, 510
`INTEGER`, 776
集成 Windows 认证, 736–737
IntelliJ IDEA 断点, 34–35, 39, 77
Web 主题, 30–35
`IntelliJ`, 32, 34–35
中间操作, Streams, 168–169
内部服务器错误 (状态 200), 235, 237, 480, 488
i18n 另见国际化
i18n 标签, 194–196
IANA 时区, 198
图标, 211, 216, 231, 418
幂等, 483
身份, 认证, 740–741
IETF (国际工程任务), 820, 826
Web 服务器, 140, 141, 515, 536
`IllegalArgumentException`, 55, 51, 514, 590
`illegalStateException`, 53, 54, 55, 244, 247
实现 EL 类型, 195, 146
隐含代码, 161–164
隐含权限, 828, 837, 839
隐含会话版本, 83, 89, 122
隐含 EL 表达式, 160–161, 165–167
JSB, 98–93, 160
视图, 373–375
`import` 属性, 82, 83, 218
include 指令, 85–87, 102, 218
`<include>`, 95, 96, 97
包含的请求, 237
`<include-preclude>`, 95, 96, 97
包含者, 19, 85
index 另见
- 索引方法, 666
- B 树, 665
- 复杂查询, 676
- 信息, 664–666
- 索引对比, 664
`index_jsp`, 34, 38, 39, 75, 77, 98, 101, 116, 188, 190, 215, 385
`index`, 495–496, 500
`indices`, 664. 另见
`INFO` 日志级别, 304
`Information`, 日志级别, 304
继承约束注解, 466–469
层次结构, Log4j 2 日志, 310
`init()`, 45–46, 50, 223, 235, 284, 290, 586
`InternalResourceView`, 371
国际化 (i18n)
- Address-Book i18n 项目, 200–203
- Bean Validation, 448–449
- 代码, 430–436
- 配置, 424–430
- 用户支持, 436–440
- 拦截器, 427–428
- 本地资源, 425–427
- 本地化到, 193
- 消息源, 421–425, 437
- Spring Framework 工具, 417–440

## 国际化标签 — Java 平台

文本方向，非英语区域, 430
主题, 229
时区支持, 429
国际化标签库 (FMT 命名空间), 193–203

- Address-Book i18n 项目, 200–203
- 投诉, 199
- 组件, 199

- `<fmt:bundle>` 198–199
- `<fmt:formatDate>` 189–199, 201, 222
- `<fmt:formatNumber>` 199–220, 430
- `<fmt:message>` 194–195, 196, 197, 421, 430, 431, 432, 440
- `<fmt:parseDate>` 198–199
- `<fmt:parseNumber>` 199–200
- `<fmt:requestEncoding>` 192
- `<fmt:setLocale>` 194, 196
- `<fmt:setTime>` 198, 204

格式化标签, 194
i18n 标签, 194
简介, 193
简化用法, Spring Framework

# Java Runtime Environment - JpaTemplate

## Java Runtime Environment - JpaTemplate

Java Runtime Environment (JRE), 4, 16, 25, 26, 35, 76
Java SE. Java 平台，标准版 (Standard Edition)
Java 序列化, 286, 510, 529, 539, 576
Java Server Faces (JSF), 6, 75, 144, 145, 146
Java 统一语言。参见 EL
Java 虚拟机 (JVM), 4
Java WebSocket APIs, 270–273
JavaBeans 激活框架, 6
Jakarta 开源软件。参见 JBoss
JavaScript。参见 Ajax

- 聊天应用程序, 294–296
- 跨站脚本攻击, 114, 155, 182, 777, 816
- `document.cookie` DOM 属性 114
- ECMAScript, 144, 153
- EL 语法, 147, 153
- HTML5 (JavaScript) API, 268–270
- Http 输出, 109, 114
- 注入, 206
- `jQuery` JavaScript 库, 273, 278
- 值, 151
- `Node.js`, 268
- 会话劫持, 114
- XML 实体, 146
- JavaScript 游戏代码，井字游戏, 278–282
- Java Servlets。参见 JPA
- Jasper Pages 标准标签库。参见 JSTL
- `tava.time.Temporal` 访问器, 221
- `Java.util.logging`, 299, 303, 304, 306
- `tava.util.Validator`, 446.参见 Validator
- `jaxb.Jaxb2Marshaller`, 376, 377, 380
- `JBoss` (Java 开源软件), 224, 724
- JBoss logging API 依赖, 445
- JDBC (Java 数据库连接)
    - ACLI 实现, 802
    - JPA, 552, 558, 696
    - 定义, 546
    - 驱动, 362–363
    - `JdbcTemplate`, 598, 602, 637, 641
    - `JdbcUserMapper`, 758–759
- JDK (Java 开发工具包)
    - 编译器, 227
    - 定义, 3, 4
    - OpenJDK 项目, 5, 300
- `Jetty`, 22, 23, 324
- JIT。参见 just in time (即时编译)
- JMS (Java 消息服务, JSR 343)
    - 与 AMQP 比较, 139, 520, 536
    - 引入, 519–520
    - 与 MSMQ 比较, 139
    - SOAP 传输机制, 475
- `Joda Time`, 12, 454, 551, 649, 659
- 连接, 745
- `JoAS`, 22
- JPA (Java Persistence API)。参见 Spring Data JPA
    - Bean 定义, 349
    - 在 Spring Framework 中配置, 602–610
    - 查找数据源, 602–603
    - 代码中的持久化单元, 603–607
    - Java EE 5, 7
    - 学习, 863
    - Maven 依赖，注, 564
    - Spring Framework 子集, 325
- JPA 注解
    - 映射条目, 565–596
    - 基本类型, 576–577
    - CLOBs 和 BLOBs, 594–595
    - 列名, 579
    - 复杂类型, 592–594
    - 日期和时间, 592–594
    - 实体字段, 569
    - 实体映射, 590–592
    - 枚举作为属性, 590–592
    - Enums-Lobs 项目, 590–595
    - 标记实体, 567–569
    - 代理键, 570–575
    - 基于 XML 的映射, 366–567
- JPA criteria API。参见搜索
    - 复杂查询, 666–677
    - 添加自定义搜索方法, 668–680
    - `Advanced-Criteria` 项目, 667–677
    - 从搜索输入创建, 670–674
    - 索引, 676
    - `and` 方法, 675
    - 危险, 674
    - 代码重用, 634
    - `GenericRepository`, 616
    - Hibernate ORM 的 criteria API, 618
    - 历史, 551
    - 与 JPQL 比较, 611, 632
- JPA 仓库, 610–624。参见 Spring Data JPA 仓库
    - 基础仓库, 613–618
    - 创建, 646–655
    - CRUD 操作, 611–612
    - 注入持久化单元, 610–611
- `JpaTemplate`, 598

# JpaTransactionManager – JSTL

## JpaTransactionManager – JSTL

`JpaTransactionManager`, 600, 610, 619–621, 632
`JPQL` (JPA 持久查询语言), 551, 611, 618, 632, 641, 642, 779
JavaScript 数据, 273, 278
JRE。参见 Java 环境
部署描述, 94–97
运行时, 76–77
Servlets-JSPs 组合, 94–101
会话, 在 121–122
会话, 100, 112, 116
Tomcat 版本, 21, 181
数组, 154
二进制, 302, 546
Java 序列化, 286
日志, 301
JSP API, 73, 74, 181
JSP 注释, 82, 102, 163
JSP 指令, 在 76–219
JSP 文档 (JSP), 303, 440, 472
JSP 文件, 552
JSP 解析器, 179
JSP 组, 95–96
JSP 脚本语言, 70, 90, 94, 218
JSP 中的日志, 309
JSR 310。参见日期时间 API
JSR 343。参见 JMS
JSR 349。参见 JSTL (Java 标签库), 177–208
XSD, 211
JSP 标签。参见 86–144
核心标签库 (C), 182–192
地址录项目, 190, 192, 206
JSP 片段, 86, 228
`<jsp:forward>`, 84, 180, 237
`<jsp:property>`, 85, 86, 87, 180, 237
`<jsp:include>`, 85, 86, 180
`<c:choose>`, 185, 191, 206
`<c:forEach>`, 186–187, 191, 206, 213
`<jsp:plugin>`, 187
`<jsp:group>`, 95–96, 197, 136
JSPs (Java), 73–104
备替代方案, 375
`<c:tokens>`, 187
`<c:if>`, 184–185, 191, 205, 232
`<c:import>`, 188–189, 212, 213
`<c:overElse>`, 185, 191, 206
`<c:out>`, 182, 192, 206, 221, 232
`<c:param>`, 121, 183, 188, 212, 219
创建, 78–81
自定义 JSP 编译器, Tomcat, 26–27
EL, 13
文件结构, 78–79
隐式变量, 88–93, 160
导入 Java 类, 82–83
JSPs 中的 Java, 88–94, 162, 172
生命周期, 77
`<c:remove>`, 189
`<c:set>`, 189
`<c:url>`, 112, 121, 178, 183, 184, 206, 212, 219
`<c:when>`, 185, 191, 206
Maven 依赖, 73–74
表现层, 94, 108, 201, 318
属性
- EL 规范, 154, 144
- 函数库, 155–156, 172, 175, 178
- `${fn:contains(String)}`, 155
- `${fn:escapeXML(String)}`, 155, 164, 182
- `${fn:join(String)}`, 156
- `${fn:length(Object)}`, 156, 164
- `${fn:toLowerCase(String)}`, 156
- `${fn:toUpperCase(String)}`, 156
- `${fn:trim(String)}`, 156
历史, 6, 144
国际化和格式标签库 (FMT), 193–203
地址录项目, 200–203

# JSTL (继续) – 负载均衡

## JSTL (继续)

`aints`, 194
货币版本, 193
`<c:bundle>`, 196, 197, 198
`<c:formatDate>`, 198–199, 201, 202, 221
`<c:formatNumber>`, 199–200, 420, 430
`<c:message>`, 194–195, 196, 197, 201, 423, 431, 437, 440
`<c:parseDate>`, 198–199, 200, 204
`<c:parameter>`, 199–198
`<c:requestEncoding>`, 194, 196, 198
`<c:setLocal>`, 197
`<c:setTimeZone>`, 196
格式标签, 194, 196
`n` tags, 118
SQL 库 (数据库访问), 203–204
Tomcat 实现, 181
Web 容器, 20
XML 库 (命名空间), 205
XML 前缀, `c`, 97
`JestUtils`, 423, 424, 426
`JstlView`, 371, 373, 422, 423
`Junk`, 497
即时 (JIT), 40, 50, 76, 77
`Kerberos`, 736, 737
`Kernighan`, Brian W. 299
键值对, 715–716
键值存储, 425, 547
关键字, 642–643

# lambda 表达式 (->), 149
lambda 表达式 `(E, E) -> int`, 169
谓词参数, 168
语言属性, 79, 218
语言代码, 193–194, 418
语言集成查询。参见 LINQ
大型对象，参见 LOBs
布局, LoGi
懒加载属性，时间织入, 723–725
LDAP (轻级目录访问协议), 733, 759–762
- `DataProvider`, 760–762
- `UserDetailsManager`, 759, 761
- `DetailsService`, 759, 761
操作, 148, 150
`ConstraintValidator`, 467–469
JSPs, 77
Web , 13
生命周期回调方法, 717
生命周期事件处理器, 719
数量限制, 755–758
操作, 169
LINQ (语言集成查询), 167
`Linux`, 24, 302, 536, 560, 738
`List` 字面量, 134
活动列表，客户支持, 135–139
应用程序监听器, 512–513, 540, 774
状态变化, 133–136
实体监听器，触发器, 719–720
`HttpSessionActivationListener`, 142, 514
`HttpSessionbindingListener`, 133, 134, 150
`HttpSessionDetailsListener`, 133, 134, 150, 212, 292, 412, 773
`ServletContextListener`, 62, 118, 133, 212, 247, 331, 332, 353, 384, 418, 768
`list.jsp`, 191–192, 202–203
`Lists`, 158, 159, 223
`ListServer.java`, 191
`listTickets.jsp`, 100, 101, 132, 207, 231
字面量值, 151–154
负载均衡
- 集群应用程序, 515–517
- 集群中的会话 ID, 139–141
884

# 加时间 – 负载均衡

加载时间织入, 723–725
`LoadRunner`, 497
日志级别, 303, 304, 306, 307
日志框架, 307–308
日志方法, 307–308
日志输出, 307–308
日志配置, 307–308
日志设置, 307–308
日志 SLF4J, 307, 308
日志工具, 307–308
日志用户, 307–308
日志, 307–308
日志错误业务逻辑；持久化日志；用户
接口逻辑
逻辑代码分组, 326–327
逻辑运算符, 148, 149, 640, 666
逻辑能力，客户支持项目, 129–132
`logInterestedParty`, 522, 524, 533
日志缩进, 132
`logInterestedParty`, 522, 524, 533
长轮询, 70, 260, 261
`LoopTag`, 225
松耦合, 326, 511
松类型，EL 语法, 197
`l` 1 运算符, 148, 149, 150
`Lucene Core`, 684–685
`Luna`, Eclipse, 355

# 机器码 - Microsoft IIS Web 服务器

## 机器码 - Microsoft IIS Web 服务器

机器码, 4, 5, 76
`Magnolia`, 818, 819
`main.css` 样式表, 289
`main.tag`, 228–229
维护状态, 106–017. 参见
管理客户端详情, 233–834
中间人攻击 (MITM), 115, 264, 231, 733, 777, 816, 831
多对多关系, 708–709
多对一关系, 705–708
`map` 操作, 169
映射的结构, 710–712, 717, 718, 720
映射
- 高级, 693–726
- 基础和嵌入集合, 712–715
- 附件集合, 721–722
- 实体到表（基于注解）, 565–596
- 基础数据类型, 576–577
- CLOBs 和 Blobs, 594–596
- 列名, 579
- 复杂数据类型, 590–595
- 日期和时间, 392–594
- 条目字段, 569
- `Entity-Mappings` 项目, 506, 561–585
- 枚举作为属性, 590–592
- `Enums-Dates-Loop` 项目, 590–595
- 标记条目, 567–569
- 代理键, 570–575
- 基于 XML 的映射器, 566–567
- Hibernate OR 文件, 552–554
- 针对请求调度器类型的过滤器, 236–237
- 针对 URL 的过滤器, 718–236
- 针对控制方法的 RESTful 请求, 491–495
- Servlet 到 URL, 47–49
- URL 模式映射到 Servlet 名称, 239–241, 243
`MappingJackson2Json`, 351
`Maps`, 153, 154, 158–159, 709, 723, 726
序列化, 371
大型多人在线角色游戏。
Maven 开启, 44, 221, 216, 454, 684, 801, 833
Maybe 依赖
- 认证, 747–748
- Bean Validation, 441–442
- 控制器, 355–356
- 自定义标签和函数库, 209–210
- EL 表达式, 143
- JPA 重新, 597–598
- JSPs, 73–74
- Log4j 2, 308–309
- 日志, 297–298
- ote, JPA 和 Hibernate Orm, 564
- OAuth, 815–816
- OpenID 支持, 764
- RESTful Web 服务, 473
- 服务和仓库, 389–390
- Servlets, 442
- SOAP, 473
- Spring Framework, 323–324
- Spring Web Services, 500
- WebSockets, 257–258
`max` 操作, 170
`Max-Attribute`, 108, 109, 118
`<max-age>`, 116, 118
`MD5`, 629, 733–736
消息转换器, 375–377
消息格式, 419–421, 432
消息源, 421–425, 437–440
`messageFactory`, 503
`messageInterceptor`, 448
`messageSourceAware`, 342
`messageResizable`, 419, 432, 434
`messageConfigSource`, 422–423
消息（应用消息）。JMS
- 与应用事件对比, 525
- 已解码, 510–513
- 分布式消息
    - AMQP, 534–540
- 问题, 518
- 用途, 177–518
- 发布/订阅消息 (pub/sub)
    - 引言, 326
    - 角色, 511
    - 社交网络, 511
- 理解, 510–511
- WebSocket 消息, 525–527, 537–539
`Messina`, Chris, 818
元数据模型, 443, 444–445. 参见 Validation
`method-code`, 607–608
方法代码，检查权限, 780–782
方法不允许允许 (405 状态码), 44, 480–482
方法参数，递归验证, 459
方法返回值, 459–460
方法范围, 80, 88
方法验证，约束注解, 485–468
`MethodValidationPostProcessor`, 449, 458, 460
MFA. 参见多因素认证
Microsoft IIS Web 服务器, 140, 141, 515, 516

# Microsoft 消息队列 - OAuth 1.0

## Microsoft 消息队列 - OAuth 1.0

Microsoft 消息队列. 参见 MSMQ
Microsoft Windows 认证, 736–737
MIME 类型, 53, 67, 366, 375, 377, 476, 777
MITM. 参见中间人攻击
MMORPGs (大型多人在线角色游戏), 268, 273
移动设备, 264, 474
`mod` keying, 148, 149, 150
视图-控制器模式 (MVC), 370–380. 参见 considers
- 基础应用, 390–391
- Bean Validation, 450
- Head First Design Patterns, 370
- 引言, 326
- 局限性, 390
`modifyHandshake()`, 292, 439
`mod_jk`, 140, 151, 515, 516
`modulus` (%), 149, 150
`MongoDB`, 302–303, 325, 425, 647
监控, 526
`Morris`, Terbit, 371
临时重定向 (302 状态码), 109, 111, 371, 736
`Mozilla Firefox`, 32, 253, 267, 280, 236, 737
`MSMQ` (Microsoft 消息队列), 139
`action`, 340
多播数据包, 519, 531–533
`multi-cache`, 110
多因素认证 (MFA), 729–740
`Gateway`, 65, 106, 208, 254, 289, 384, 512, 参见 Customer
multipart 请求, 52, 326–368
多人, Customer Support, 384–385
多人游戏，带 WebSockets, 268, 273–283
多个启动器, 768–769
多个表，存储, 716–717
多个用户界面，根应用上下文, 149, 150
`multiply ()`, 149
读取, 69–218, 308
`multiValueSet`, 55–61, 91
`mutators`, 125, 154, 161, 162, 189, 192, 223, 341, 344, 380, 353, 569, 667, 709, 718
MVC. 视图-控制器
- 带 JPA 的全文索引, 677–678
- 安装, 859–562
- JDBC 驱动, 362
- `MySQL Server`, 559, 561
- `MySQL Workbench`, 561–563, 581, 589, 595, 624, 632, 654, 674, 688
- `InnDialect`, 558, 559, 605, 688
- 自然食物链比喻, 393
- `operator`, 148, 149, 150
- `Network Address Translation` (NAT), 106
- 网络过滤工具, 109
- `News Ticker`, 268
- 无内容 (204 状态码), 482, 483, 494, 498
- 节点, 268
- 通过多播数据包发现, 531–533
- `NonAervlet`, 244, 246
- `tunces`, 735–821, 831, 840
- `idempotent`, 482
- 非索引搜索, 664
- 非空指针, 482, 483
- 非标准数据请求, 693–726
    - 描述, 546–547
    - 图形数据库, 547
    - 键值存储, 402–305
    - 日志, 302
    - `MongoDB`, 302–303, 325, 425, 648
    - `Redis`, 325, 425
- `Not Accept` (406 状态码), 480
- `Not Found` (404 状态码), 179, 237, 480, 481, 483, 498, 493
- `not` operator, 148, 150
- `NT LAN Manager` 支持, 737
- `null` 关键字, 148, 151, 153
- `nonipotent`, 481, 482
- 数字，国际化与格式化 library, 193
- 数值字量, 152–153
- OAuth 1.0
    - 挑战, 824–825
    - 历史, 819–820
    - 标准, 820
    - 术语, 820
    - 使用, 820–824

# OAuth 2.0 - pageContext

## OAuth 2.0 - pageContext

OAuth 2.0, 818–862
- 授权许可, 827–831
    - Authorization Code Grant, 827–829, 836, 837, 839
    - Client Credentials Grant, 827, 834, 837, 839, 840
    - Implicit Grants, 828, 836, 837, 839
    - Resource Owner Password Credentials Grant, 828–829, 837, 839
- 客户端应用, 838–840, 856–862
- 争议, 831–832
- 引言, 818–819
- 关键人物, 819
- Maven demeaning, 815–816
- provider
    - 授权服务器实现, 834–836
    - 配置代码和令牌服务, 834–836
    - 管理客户端详情, 233–834
- OAuth 安全实践, 337
- 资源服务器实现, 836–837
- 标准文档, 819
- 术语, 826
- Web 服务安全, 816–818
- XML Schema, 836
`OAuth 实验`, 337
`OAuth2RefreshOperations`, 338
`OAuth2RestTemplate`, 338–840, 856, 857, 860, 861–862
`OAuth2AccessTokenScope`, 856–862
`auth_callback`, 821
`OAuth-client`, 856
`auth_key`, 821
`auth_nonce`, 821
`auth_signature`, 821
对象数据库, 546
`Object People`, 550
对象-关系映射. 参见 ODBMS
多对多关系, 705–708
多对一关系, 703–704
`ODBMS`. 参见面向对象管理
`OPTIONS()`, 43
- HTTP 方法, 42, 532, 599
- OAuth client, 838
- RESTful Web 服务, 477, 478, 479, 480, 481, 498–492
`or` keyword, 148
`method`, 675
`Oracle`
- JEE 版本, 8–9
- `Sun Microsystem`, 5
- `O'Reilly`, Head First Design Patterns, 370
ORMs (对象关系映射)
- 定义, 547
- 描述, 547–552
`or.xml` SCD, 566–567
`OS X`, Mac, 24, 559, 665, 738, 789
`out` variable, 82
`output.println("<br>")`, 74–75
`OWASP` (Open Web Security Project), 112, 114
`page directive`, 75, 78, 80, 82, 83–86, 102
`page scope`, 160–161, 187, 184, 196, 198
`page variable`, 90
`PageContext`, 191, 165
`pageContext`, 89–90, 165, 214

![img](img/9c2d45f6d547f72cb870b3a991f62ef6_923_0.png)

888

# <page-encoding> - 受保护资源

## <page-encoding> - 受保护资源

`<page-encoding>`, 96, 97, 336
`pageEncoding` 属性, 83, 96, 218
`pageScope`, 165, 166
`pagingAndSortingRepository`, 644, 646, 656
`pagingAndSortingRepositoryT, ID extends Serializable`, 638–639
`param`, 165, 166
参数限制, `@RequestMapping`, 359
参数验证, 462–463
`param` 属性, 359
`paramValues`, 165, 166
父类加载器委托模型, 16, 17
密码认证, 731–732
`PATCH`

`Pike`, Rob, 299
`pings`, 266, 413, 414
流水线源, 168
普通 Java对象（plain old objects）。参见 POJOs
`PlatformTransactionManager`, 598–600, 609, 620, 648
可插认证模块（Pluggable Authentication Module）, 744
切点（pointcuts）, Aspect, 607–608, 794, 796
POJOs（普通 Java 对象）
- `Attachment` 类, 65
- 联系（Contact）, 190
- 嵌入实体中, 699–703
- 员工（Employee）, 452–454
- `Ticket` 类, 65
轮询（polling）。参见 WebSockets
- 频繁轮询, 259–260
- 长轮询, 270, 260, 261–262
`pongs.`, 276, 212, 413
`POST`

- CSRF 令牌, 775, 776
- `declare()`, 43, 51–57–58, 59, 67, 78
- HTTP 方法, 43, 52–53, 57, 65, 379
- OAuth 客户端, 838
- 行信息, 43
- `RestTemplate` Web 服务, 482
`post` 变量, 52–54, 33
执行注解, 778–791
`PostgresQL`, 559, 571, 596, 709
`PostSecurityLoggingFilter`, 767–769
预处理和执行注解, 778–791
谓词参数, 86, 179
`PreSecurityLoggingFilter`, 767–769
表现层, 94, 98–101, 203, 318
apis, 国际化和标签库, 193
基本类型字面量, 153
主体（principals）, 授权, 740–741
`PrintWriter`, 13, 44, 55, 57, 64, 74, 249
`processAttachment()`, 68
程序逻辑类型, 391–393。另另业务逻辑；持久化接口逻辑
程序化配置，过滤器, 238–239
程序化触发器, 717–720
契约编程范式, 444, 458
属性表达式, 640
受保护资源
- 已定义, 819
- OAuth 2.0, 826–862
- OAuth1.0a, 819–825

# 协议参数 - 资源包

## 协议参数 - 资源包

协议参数, 821
公共客户端, 826, 827
`Publisher.java`, 580–581
发布事件, 324, 523–524
发布/订阅消息（pub/sub）, 326
- 角色, 511
- 理解, 510–511
`ReloadableResourceMessage`, 421, 422, 424, 448
记住我认证, 752, 761, 765–776, 773, 783, 784
远程方法调用 (RPC), 6, 510, 518
`RemoteAuthenticationProvider`, 666
用户名 Cookie, 110
重放攻击, 733, 734, 735, 820
持久存储库, 389–416
`doPut()`, 43, 51
`REST`MVC 模式, 390–391
程序逻辑类型, 391–393
用于数据存储, 399–404
JPA 存储库, 610–624
- 基础存储库, 613–618
- CRUD 操作, 611–612
- 注入持久化单元, 610–611
- Maven 依赖, 389–390
- 存储库逻辑, 392
- 查找实体的查询方法, 639–642
查询参数, 52–53
`Querydsl`, 642, 645
`Querydsl.JpaRepository`, 645
队列, 158–159
请求属性, 52, 87, 99–100, 120, 130
请求调度器, 97, 280, 236–237
请求处理，异步, 237, 247–249, 355, 370
请求参数, `HttpServletServlet`, 52–53
请求作用域, 160, 184, 180
请求线程, 69–71, 730, 343
请求变量, 89
`RequestLogFilter`, 248–249
内容类型限制, 360
控制器方法, 360–368
- 参数, 360–365
- 有效返回类型, 365–370
HTTP 请求, 355–369
请求参数, 375–368
URL 限制, 375–368
值属性, 356–368
`requestScope`, 165, 166
`RequestView`, 369, 371, 373–374, 394
`RabbitMQ`, 536–540
关系型数据库系统（RDBMS）。参见管理系统
领域名称, 821
以及传输二进制消息，WebSocket 集, 286–287
记录, 818
递归验证, 454–455, 459, 470
`RedirectView`, 369, 372
`Redis`, 325, 427
重构 Customer Support, 656–661
引用实现, 6, 20, 442, 554, 562
反射, 827–830, 835, 448
正则表达式, 363, 451, 457, 463, 640
关系型数据库管理系统 (RDBMS), 303, 545–546
关系型数据库。参见 JDBC; NoSQL 数据库
- 符合 ACID 的, 303
- 期望, 545–546
- NoSQL 比较, 302
- 准备, 559–563
- Spring Data Project, 325
- SQL 标签库, 203–204, 205
关系, 717
资源键, 148
`Resin`, 222
资源包
- i18n 标签, 194, 195, 196, 197, 201
- 理解, 419–421

# 资源所有者凭据 –

## 资源所有者凭据 –

资源所有者凭据, 828–829, 837, 399
所有者
返回集合, 170
修订, 709–710
`RFC 2026`, 826
`RFC 2246`, 115
`RFC 2616`, 43, 264
`RFC 2822`, 442
`RFC 3986`, 363
`RFC 5849`, 819, 820
`RFC 6435`, 265, 269
`RFC 6749`, 819, 826
`RFC 6750`, 819, 830
已定义, 819
- OAuth 2.0, 826–855
- OAuth1.0a, 819–825
资源实现, 366–337
`ResourceMessage`, 421, 422, 425, 429
`ResourceLoader`, 338
`/resource/stylesheet/login.css`, 228, 229, 230
`/resource/stylesheet/main.css`, 228
响应码, 234, 235, 247, 255
实体, 328–369, 375–380
`REST` 控制器, 478–484
`RESTClient`, 497–498
`RESTExceptionHandler`, 490, 491, 500
RESTful Web 服务, 476–497
- Bean Validation, 488
- 配置, 484–496
- CRUD 操作, 476
- 可发现性, 477–479
- 错误处理, 488–491
- `HEAD`, 481–482
- HTTP 状态, 479–480
- Maven 依赖, 473
- `OPTIONS`, 477, 479, 480, 481, 488, 492–993
- `POST`, 482
- `PUT`, 482
- SOAP 比较, 476–477
- Spring MVC 控制器, 484–496
- 映射 RESTful 请求到控制器方法, 491–495
- 映射，使用元类型注解, 484–485
- 分离 Web 和 REST 应用上下文, 485–488
- 测试, 496–500
- URIs, 479–480
- Web 服务安全, 816–818
- WSDL, 471
`RestServerContextConfiguration`, 486–488, 490, 500, 653, 656
`RestTemplate`, 838–840, 859–892
返回第一个值, Streams, 171
`Rhino`, 5
角色, 授权, 741–743
滚动文件, 302, 314
根应用上下文, 394–404
- 业务逻辑开发, 396–399
- 多个用户界面, 394–395
`RootConfiguration`, 348, 371, 376, 394, 405, 424, 426, 448, 504, 524, 604, 607, 608, 631, 656, 688, 699, 724, 750, 751, 754, 771, 792, 804, 858
`RSA-SHA`, 821
`RTA` 协议, 264
`Ruby`, 555, 655
运行时, JS, 76–77
`RunAsAuthenticationProvider`, 766

# S

## S

`Safer`, 263
`SAML`, 738
`Sample-Debug-Eclipse` 项目, 38–39
`Sample-Debug-IntelliJ` 项目, 32, 34–35
`Sample-deployment.war`, 27–30
`Scala`, 5
调度方法执行, 404–409
- 控制器, 404–406
架构-数据库系统, 546。参见 NoSQL 数据库
作用域, 166–167
作用域
- 应用代码, 160, 161, 167
- 类作用域, 88
- EL 表达式, 160–164
- 隐式 EL 作用域, 161–164
- 方法作用域, 80–88
- 页面代码, 160–161, 167, 184, 189, 198
- 请求作用域, 160, 184, 189, 860
- 会 作用域, 160, 839, 860
- 令牌 作用域, 827
- 事务作用域, 598–599

# 脚本语言 – 会话事件

## 脚本语言 – 会话事件

脚本语言, JSP, 79, 94, 218
`<script-invalid>` 标签, 93, 96, 271, 227
脚本, JS, 102
`Script-Engine`, 324, 523–524
搜索, 360–368
- 方法, 360
- `Advanced-Criteria`, 367–376
- 从输入创建, 367–376
- 和方法, 370
- 全文本索引, 376–384
- 非索引, 374
- `Hibernate`, 363
- 全文, 376–384
- 反射, 827–830, 835, 448
- 正则表达式, 363, 451, 457, 463, 640
- 关系型数据库管理系统 (RDBMS), 303, 545–546
- 关系型数据库。参见 JDBC; NoSQL 数据库
- 符合 ACID 的, 303
- 期望, 545–546
- NoSQL 比较, 302
- 准备, 559–563
- Spring Data Project, 325
- SQL 标签库, 203–204, 205

## 会话故障转移 – 社交网络

- 会话故障转移, 142
- 会话固定攻击, 113–114, 744–755, 816, 820, 823
- 会话劫持, 114
- 会话 ID cookie, 110–117, 166, 817, 825
- 会话 ID 传输
    - 会话 cookie, 108–110
    - URL 中的会话 ID, 110–112, 183, 188
- 会话迁移, 113, 515, 517, 773
- 会话超时, 139, 141–142
- 会话范围, 160, 830, 896
- 会话变量, 83, 89, 122
- `session-config`, 116–118, 129
- `session-Activity` 项目, 125–128
- `sessionFactorories`, 556–559
- `sessionLocalResolver`, 426, 428, 487
- `sessionStrategy`, java, 135–138
- 会话, 105–142
    - 应用工作流, 107, 108
    - 集群, 139–141, 514–515
    - 客户支持项目
        - 活跃会话列表, 139–135
        - 监听器, 133–138
        - 登录功能, 129–132
    - 数据存储, 116–128
        - 复杂数据, 125–128
        - 在部署器中配置会话, 116–418
        - 数据, 123–125
        - 存储和检索数据, 119–123
    - 重要性, 106–107
    - JPS 中的 s, 121–152
    - 限制会话数量, 755–758
    - 维护状态, 106–107
    - 在 Servlets 中, 119–121
- 会话 ID 传输
    - 会话 cookie, 108–110
    - URL 中的会话 ID, 110–112, 183, 188
    - 购物车示例, 106–107
    - 购物车示例项目, 116–141, 139–142, 813, 835
    - 漏洞, 112–116, 748
    - Web 会话理论, 107–108
- `sessions.jsp`, 138, 174, 232
- `sessionWillPassivate()`, 142, 514
- `setLiteral`, 153–154
- `setCharacterEncoding()`, 55, 76, 79, 83
- `setContentLength()`, 1, 56
- `setContentLengthLong()`, 1, 56
- `setContentType()`, 1, 53, 76, 79
- `Set-Cookie Header`, 108, 109, 110
- `setDateHeader()`, 56
- `setHeader()`, 56
- `getIntHeader()`, 56
- `setMaxInteractiveInterval`, 124
- 集合, 153, 154, 158, 159, 723
- `setStatus`, 56
- setter 方法.
    - `setTime` 方法, 223
- `SEVER` 日志, 304
- `SHA`, 266, 629, 821
- 共享资源, 70–71
- 衬衫, 154
- 购物车示例, 106–107
- 购物车示例项目, 116–141
- 短, 153
- `<short-name>`, 211, 213, 222
- 简单保护的 GSSI 协商机制, 377
- 简单对象访问。参见 SOAP
- 最简单表达式语言, 144. 另见
- `SimpleTao`, 210, 213, 224, 225
- `SimpleTagsSupport`, 225
- `SimpleUrlHandlerMapping`, 340
- 模拟集群项目, 284–286
- 模拟集群，带有多个部署, 533–534
- 简单值参数, 53, 61
- `SimpleMesh`, 75
- `SLF4J`, 307, 308, 309, 319
- `SLMLINT`, 576
- 智能卡, 737, 738, 739
- `SmartLifecycle` 接口, 343
- `SMS` 日志方法, 302
- `SMTP` 日志方法, 302
- `SOAP`, 475–476
    - 特性, 475
    - RESTful Web 服务, 476–477
    - 简单对象访问协议, 475
- `Spring Web`, 337, 500–508
    - 测试, 496–500
    - Web 服务安全, 816–818
- `SOAP Body` 元素, 475
- `SOAP` 端点, 504–508
- `SOAP` Envelope, 475, 505, 507
- `SOAP Fault` 元素, 475
- `SOAP Header` 元素, 475
- `SoapServletContext`, 503–504
- 社交网络, 511, 893
- sockets – 静态方法访问, 302, 329-排序
- 软删除, 483
- 排序操作, 169
- 拆分日志过滤器, 766–768
- 统一数据访问, 634–647
- 代码重复, 634–638
- Spring Data Commons
    - API 文档, 338
    - Spring Data JPA, 333–662
    - Java 配置, 646–655
    - 添加的自定义行为, 642–646
    - 启用自动生成, 647–654
- Spring Data NoSQL, 349–351
- Spring Framework AOP 支持, 325
    - 面向面向编程, 325, 347, 353
- Bean 校验, 444–450
    - 部署描述符, 330–332
    - 配置, 336–349
    - 混合, 340–345
    - 数据访问, 325
    - 依赖注入, 225, 353, 445
    - 到 EJB, 324
    - 演进, 324
    - 国际化, 417–440
    - 介绍, 323–353
    - 逻辑组, 326–327
    - Maven 依赖, 322–324
    - 总结, 353
    - Spring Framework 语言 (SpEL), 784, 785, 798, 790, 814, 837
    - Spring MVC
        - 控制器, 746–746
        - 过滤器, 739–750
        - HTTP Header, 777–778
        - 标签库, 813–814
    - `Spring Validator`, 446, 450–487
    - `Spring Web Services`, 336, 477, 500–508
    - `SpringConfiguration`, 411–412
    - `Spring-混合`项目, 336–349
    - `Spring-managed beans`, 326, 327, 328, 391, 407, 410, 445, 485, 512, 608, 717
    - `Spring-XML`项目, 336–349
    - `SQL` (结构化查询语言), 545
    - Spring Data 标签库, 203–204, 203, 204
    - `@query`, 203, 204
    - `@query:DataSource`, 203, 204
    - `@query:transaction`, 203, 204
    - `SSL` 证书, 115–116, 118, 140, 150
    - `JS/TLS`, 115, 226, 267
    - 事件 multicaster, 527
    - `Start()`, 70, 244, 245
    - 状态, 106–107
    - 维护状态, 106–107
    - OAuth, 106
    - REST, 484, 817, 825
    - `RestTemplate`, 838–840, 859–862
    - `SOAP`, 817
    - `StatelessSessions`, 557
    - 静态分析器, 460
    - 静态访问, EL, 156–157
    - 静态 HTML 文档, 74–75
    - 静态方法访问, EL, 156–157

## 状态码

### 状态码 – System.println()

- 101 协议切换, 264, 265, 267
- 204 无内容, 482, 483, 494, 498
- 302 临时重定向, 109, 110, 371, 736
- 303 其他, 371, 736
- 307 临时重定向, 736
- 400 请求, 264, 265, 470, 498, 822
- 401 未授权, 480, 481, 732, 733, 734, 735, 822, 830
- 403 禁止, 480, 481, 785, 787
- 404 未找到, 179, 237, 480, 481, 483, 493, 498
- 405 方法未允许, 405
- 406 不可接受, 406
- 407 代理身份验证, 407
- 408 请求, 408
- 409 冲突, 409
- 410 已 gone way, 410
- 413 负载过大, 413
- 418 我是一个茶壶, 418
- 422 无法处理实体, 422
- 429 请求过多, 429
- 500 内部错误, 235, 237, 480, 481, 483, 493, 498
- 501 已实现, 501
- 502 网关错误, 502
- 503 服务不可用, 503
- 504 超时, 504
- Spring 表达式语言 (SpEL), 784, 785, 798, 790, 814, 837
- Spring Framework 表达式语言, 336, 349
- Spring Data 标签库, 203–204
- Spring MVC 控制器, 746–746
- Spring Security, 743–745
- Spring Web 服务, 336, 477, 500–508
- Spring Validator, 446, 450–487
- EL (表达式语言), 156, 157
- 静态方法访问, EL, 156–157

# TagSupport – Tomcat

语法, 178–179
XML 标签, 24, 102, 155, 178, 794
`TagSupport`, 222, 225
- `.tagx` 文件, 210, 218
`TaskExecutor`, 405
`TaskScheduler`, 405, 406, 409
TCP 通信, 224. 另见 HTTP/1.1
升级功能
- `<test-class>`, 213, 219
模板引擎, 275, 371. 另见 JSPs
`Template-Projects`, 219, 227
临时凭证, 802–824, 829
临时重定向 (307 状态码), 测试
终端操作, 170–171
测试驱动开发, 475
集群, 533–554
RESTful web, 496–500
SOAP, 496–530
Websocket 集群, 287–288
`TestNG`, 497
文本国际化和格式标签库, 193
文本方向, 非西方区域, 430, 440
主题, 国际化 (i18n), 429–430
`this.getServletName()`, 1, 48
`ThreadContext`, 314, 315, 316, 749, 767, 768
`ThreadFactory`, 405
线程
- 线程组, 69–75, 404, 405, 603
- 用于事务和实体管理器, 599–600
三脚架 OAuth, 825, 827, 828
`tickers`, WebSockets, 266, 268
`ticket`, 65, 68
`RestControllerEndpoint`, 500, 501, 505, 809, 826
`ticket-let`, 59, 65, 68–79, 97, 101, 131, 230, 254, 385
`ticketEndPoint`, 505–508
`tictac-toc` 游戏, 273–283
- `game.js`, 279–282
- 实现算法, 274
- javascript 脚本控制, 278–282
- 游戏, 283
- 服务端点, 274–278
- `ticTacToc.css` 样式表, 278
`ticTacTocServer.java`, 274–278
紧耦合, 3, 4, 305, 311
`tiles` 模板引擎, 275, 377
另见 Date and Time API
- `<fmt:setTime>`, 197–198
- `getLastAccessedTime()`, 124
- `getTimeZone()`, 223
- IANA 时间数据库, 198
- `Joda Time`, 12, 454, 551, 649, 651, 695
- 将项映射到表（基于注解）, 592–594
- `setTime` 方法, 223
- 时间支持, 国际化 (i18n), 429
- 时间间隔格式化, 207, 208, 227
- 超时, 260, 262, 263
- 时间戳, 版本条目, 279
`tiny`, 22
`TLDs`. 另见标签库描述符
- `<lib-version>`, 211, 222
`TLS`
- OAuth, 822, 823, 825, 831
- `SSL/TLS`, 115, 226, 267
`toArray` 操作, 170
令牌凭证, 802–824, 830
令牌范围, 827
令牌
- `bearer tokens`, 819, 830, 831, 832, 833, 835, 842, 850, 853, 857
- `<c:forTokens>`, 187–188
- CSRF 令牌, 775, 776
- 限制, 818
- `MAC`, 832
- `OAuthAccessToken_Scope`, 847
- 刷新令牌, 827–830, 835, 836, 842, 848
- `toLife` 操作, 170
`Tomcat`
- 增强, 20–21
- 集群化应用, 515–517
- 自定义 JSP 编译器, 26–27
- 调试应用程序
    - Eclipse, 35–39
    - IntelliJ IDEA, 305
- 部署和使用 web 方法
    - 手动操作, 28
    - Tomcat 管理, 28–30
- `EAR` 文件, 17
- EL 表达式, 21, 181
- 安装, 23–27
- Java EE, 21
- Java SE, 21
- JSPs, 21, 181
- `MySQL` 连接, 563
- 使用的原因, 23
- servlets, 181, 218
- 版本, 21
- WebSockets, 21, 181, 255

# TomEE – 校验

## TomEE – 校验

`TomEE`, 20–21
`TopLink`, 550–551, 552
`TRACE()`, 43
- HTTP 方法, 43, 52, 359
- 日志级别, 310, 317, 319
`Trace 1`, 304
`Trace 2`, 304
`<tracking-mode>`, 116, 117, 118
事务, 598–601
- AOP 子集, 325
- set up, 607–610
- 范围, 509, 628, 438
- 线程, 599–600
流转换, 169
传输和接收二进制消息,
WebSocket 集群, 286–287
实体 监听器, 719–720
程序化, 717–720
关系型数据库, 717
`<trim-directive-whitespaces>`, 95, 96, 376
`true` 关键字, 141
`try-with-resources`, 10
`T-SQL`, 545
`Two-Legged OAuth`, 828
字母代码, 193
类型安全, 159
`URI` 变量, 362–363, 375
`<uri>`, 211–212
回调, 823
`getRequestURI()`, 54
`https` 方案, 264
RESTful web 服务, 479–480
`URI` 参数, 52–53
`<url-pattern>`, 95
复制粘贴错误, 113
`URL` 过滤器, 236
Servlet CL, 477–490
URL 模式映射与 Servlet 名称, 239–241, 243
路径参数, 326
限制, `RequestMapping`, 358–368
安全, 743–786
session ID 到 URL, 110–112, 183
用户数据, Customer Support, 129–131
用户详情, 748–759
- `InMemoryUserDetailsManager`, 749, 752, 753, 758
- `JdbcUserDetailsManager`, 758, 759
- `LdapUserDetailsService`, 759, 761
- `UserDetailsService`, 748–759, 764, 765, 805, 807, 833, 853
用户论坛, 107, 705, 798
用户界面
- `Controller-Repository` 模式, 393
- 与 WebSocket 的逻辑分离, 409–415
- 分离, 414
- 业务逻辑持久化逻辑, 392
- 业务逻辑用户界面, 390–391
- 用户界面, root 应用上下文, 394–395
- 用户配置 locale, 428–429
`UserManagementController`, 380
`User-Profile` 项目, 160–172
`UserRegistrationForm`, 364
`UnanimousBased`, 797
负号 (i), 149, 150
未授权 (401 状态码), 480, 481, 732, 733, 735, 822, 824, 830
单向访问, Query Data, 634–647
查找实体的查询方法, 639–642
仓库接口, 638–639

# U

`Unique Language. Expressions`, 162
`UniqueConstraints`, 568, 569
不支持的媒体类型, 41 状态码, 480
`Upgrade header`, 264, 265, 266
`Upgrade Required` (426 状态码), 264
大写双字母代码, 193
`uri` 属性, 86, 179, 180
`URI` 路径参数, 363

# V

校验错误, 显示, 463–465
校验组, 452–456, 460
校验支持. 另见 Bean Validation

# Validator – WebSockets

## Validator – WebSockets

`Validator`. 另见 `Hibernate Validator` `java.validation.Validator`, 446, 447
`Validator`, 446, 450, 487
`<validator-class>`, 212
`value` 属性, `@RequestMapping`, 356–358
web 服务. 另见 RESTful 服务
- 认证机制, 817–818
- 定义, 474
- 安全, 816–818
- `SOAP` 的 Web Services, 336, 477, 500–508
- 测试, 496–500
`Web Services` 地址, 505
`<variable>` 元素, `Velocity` 模板引擎, 75, 371
版本条目, 709–710
视频流, 268
`view` 名称, 374
`view` 名称, 371–373
`view` 解析, 372–373
类型, 369
`Web Services Language` (WSDL), 474, 475, 501, 503, 509
web 理论, 107–108
`WebApplicationInitializer`, 333, 335, 348, 339, 384
`Viewapplication.jsp`, 127–128
`viewTicket.jsp`, 98, 173, 206
漏洞, sessions, 112–446

# W

`W3C`. 另见 Consortium 268, 474, 475
`WebApplication Messaging` (WAMP), 519, 520
`WebSocket` 对象, 269–270
`WebSocket-Messaging`, 527–527, 539
`WebSockets`, 257–296
`WAR` (web 应用) 目录, 14, 573–584
- `EAR` 监听器, 14
- 与 `JAR` 文件比较, 14–15
`Warning` 级别, 304
web 应用服务. 另见 application context, 342, 374, 394, 485
`HTML5` (JavaScript) API, 268–280
`Web APIs`, 270–273
`ClusterMessaging`, 527, 528
集群, 284–288, 518–519
`configurator`, 411–412
`Client-Support-v8`, 289, 295
未来更改, 296
从服务器到 Apache 和 Tomcat 分块编码, 262
频繁轮询, 259–260
`HTTP1.1` 升级功能, 264–267
长轮询, 70, 260–261
逻辑层分离, 409–415
Maven 依赖, 257, 258–282
多人游戏, 268, 273, 529–530
发送和接收事件, 284–286
另见 root context. `Web Technologies`, 6
8 web 服务. 另见 Java EE applications, 513–514
生命周期, 13
结构, 13
web 容器 (Servlets). 另见 Tomcat 应用服务, 19–220, 180–181
- 描述, 19–23
- `JBoss`, 22, 445, 324
- `Jetty`, 22, 324
`Web GUI` 服务, web 服务安全, 816–818
RESTful 服务端, 485, 493, 496–500
测试, 496–500
`Spring Framework` suite, 34
`SpringConfiguration`, 411–412
`tic-tac-toe` 游戏, 273–283
- `game.jsp`, 279–282
- 实现算法, 274
- `JavaScript` 游戏控制, 278–282
- 游戏, 283
web 服务, 816–818. 另见 OAuth

# WebSockets (continued) - XSS

## WebSockets (continued) - XSS

`WebSockets` (continued)
- 服务端点, 274–278
- `ticTacoe.css` 样式表, 227
- `ticTacoeServer.java`, 274–278
- `Tomcat`, 21, 181, 255
- `Tomcat Connector`, 515
- 用户, 268
`WebSphere`, 22, 23, 141, 447, 552, 600, 724
`Wildfly`, 22
`Windows Active Directory`, 739, 743, 744, 745, 761
`Windows Authentication`, 736–737
`Windows` 事件日志, 302
`Windows` 服务, Tomcat 安装, 24
`Windows-Apache-MySQL-PHP` (WAMP), 519
`Wireshark`, 109, 266, 368
`Workbench`, 另见 MySQL Benchmark
`workflow`, session, 107, 108
`World Wide Web Consortium` (W3C), 268, 474, 475
`wrox. tid`, 222
`ws` 方案, 265, 266
`WSDL`. 另见 Web Services Language
`ws` 方案, 265, 266, 267
`WWW-Authenticate header`, 732, 733, 735

# X

`X` 空间. 另见 XML Processing library
`XML`. 另见 Ajax
- 注释, 81–102
- 实体, 145, 146, 376
- 日志, 301
- `Streaming API for XML`, 7, 8, 500, 505
- 标签, 24, 102, 155, 178, 794
- `XML` 命名空间配置, Spring Data JPA 仓库, 647–650
- `XML` 处理标签库 (X 空间),
- `XML Schema`. 另见 XSD
- `XMLHTTPRequest`, 262, 263, 266, 269
- `XMLNS`, 86, 97, 103, 178, 180
- `XPath`, 144, 154, 205
- `XSD` (X Schema)
    - 合约优先 XSD, 501–503
    - `JSP` 标签库 XSD, 211
    - `OAuth 2.0`, 836
    - `WSDL`, 475
`XSS`. 另见 cross-site scripting

# Apache License，2.0 版本

本作品的源代码受 Apache License 2.0 许可条款限制（除非适用法律要求或经书面同意）。您可以在以下地址获取该许可协议：

```
```



# Apache License 2.0

## 使用、复制和分发的条款与条件

### 1. 定义

**“许可”** 是指本文第 1 节至第 9 节定义的用于、复制和分发的条款和条件。

**“许可方”** 是指授予许可的版权、专利或其他知识产权的拥有者实体。

**“作品”** 是指作者创作的作品，以及所有由许可方控制或与许可方受共同控制的其他条目。就此定义而言，“衍生作品”是指任何基于作品、或源自作品的，或者基于该作品（百分之五十或以上所有权）的作品，或代表该作品创作的作品。

**“源码形式”** 是指首选用于进行修改的作品形式，但不限于源代码、源文档和编译文件。

**“目标形式”** 是指对源码进行机械转换或翻译后产生的二进制或其他形式，但不限于编译后的代码和相关文件。

**“包含在的作品”** 是指根据许可协议制作的作者作品，无论是源码形式还是目标形式，并包括随附作品的作品中包含的任何版权声明（参见“通知”）。

**“衍生作品”** 是指任何基于作品、或源自作品，且需要对作品进行修改、添加、阐述、澄清或其他修改的作品。衍生作品不包括通过编译边界分离的、或仅通过编译边界与作品链接的作品。

**“贡献”** 是指任何作者创作的作品，包括作品的原始版本，以及贡献者或代表贡献者对作品进行的任何修改或添加。

**“作者”** 是指授权代表贡献者创作作品并已接收且整合到作品中的个人或法律实体。

**“授予”** 是指根据本许可授予的权利。

**“许可授予”** 是指许可方授予被许可方的一种全球性的、非排性的、免费的、免版税的、不可撤销的、可分许可的、永久许可，允许其制作、使用、要约出售、分发和传输作品，并以源码或目标形式分发作品。

**“贡献授予”** 是指贡献者授予许可方的一种全球性的、非排性的、免费的、免版税的、不可撤销的、可分许可的、永久许可，允许其制作、使用、要约出售、分发和传输贡献，并以源码或目标形式分发贡献。

### 2. 版权声明与“通知”文件要求

源码形式，但不包括属于任何衍生作品的部分；作为分发一部分的文本文件；如果作品包含“通知”（NOTICE）文本文件作为分发的一部分，您必须包含一份可读的版权声明、专利声明以及（如果适用）包含在声明中但不属于任何衍生作品的归属声明的副本。如果作品中提供了“通知”（NOTICE）文本文件，您必须在分发于衍生作品的“通知”文本文件中包含以下内容之一；或由作品生成的带有通常适用的归属声明的显示。“通知”的内容仅供参考，不修改许可协议。您可以在您分发的“通知”文件中添加您自己的归属声明，只要这些额外的归属声明没有更改或删除自该“通知”文件本身的源文件中包含的任何归属声明。

### 3. 商标限制

贡献者不根据商标、标志或服务标记授予任何许可，除非许可中包含的作品的使用和分发以及作品的复制和内容对此另有要求。

### 4. 适用法律

本许可受适用法律管辖。通过同意作品，您（以及每位贡献者）同意受适用条款的约束，而不考虑法律冲突条款，除非适用法律另有明确规定。

### 5. 责任限制

在任何情况下，任何作者（无论是基于合同、侵权还是其他原因）对您或任何其他贡献者对于因作品或无法使用作品而引起或与之相关的任何损害（包括直接、特殊、偶然、后果性或其他损害）均不负责，即使该作者已被告知发生此类损害的可能性。

### 6. 免责声明

作品按“按现状”基础提供，不提供任何形式的明式或暗示的保证，包括但不限于对商品性、非侵权和针对特定用途的适用性和所有权的保证。

## 如何将 Apache 许可应用于您的作品

如果您将 Apache 许可应用于您的作品，请按照以下步骤操作，并将括号 `[ ]` 替换为适当的文本。（以下文本应包含在作品根目录下名为“LICENSE”的文本文件中，并带有“打印页”上标识的人员及其身份）：

```
Copyright [年份] [版权所有者名称]

Apache License, Version 2.0（许可）

除非符合本许可，否则您无法使用此文件。您可以在以下地址获取许可副本：

http://www.apache.org/licenses/LICENSE-2.0
```

除非适用法律要求或经书面同意，根据本许可分发的软件按“按现状”基础提供，不提供任何形式的明式或暗示保证，包括但不限于对商品性、针对特定用途的适用性的保证。有关本许可许可权限和限制的特定语言，

![](img/9c2d45f6d547f72cb870b3a991f62ef6_937_0.png)

JetBrains 荣幸为 Nick Williams 的 Professional Java for Web Applications 用户提供 IntelliJ IDEA 13 的 90 天评估版。访问 `http://www.jetbrains.com/idea/professional_java_for_web_applications/` 或使用下方的二维码试用 IntelliJ IDEA 13 90 天。

![](img/9c2d45f6d547f72cb870b3a991f62ef6_937_1.png)

![](img/9c2d45f6d547f72cb870b3a991f62ef6_937_2.png)
