
# Java 高级指南：Web 应用开发

加入讨论 @p2p.vrox.com

内部福利：免费 3 个月 IntelliJ 个人许可证

![](img/4677f981a0e1067137bb55a122f8498d_0_0.png)

![](img/4677f981a0e1067137bb55a122f8498d_2_0.png)

# 关于作者

**NICK WILLIAMS** 是位于印第安纳州印第安波利斯的工程师。他毕业于贝尔蒙特大学，拥有超过 10 年的商业开发经验。他是开源项目的频繁贡献者。他与妻子住在当地。

**JAKE RADAKVIC** 是位于印第安纳州印第安波利斯的工程师。他毕业于贝尔蒙特大学，拥有 10 年的商业开发经验。他是开源项目的频繁贡献者。他与妻子住在当地。

# 鸣谢

感谢……

- 我的妻子 Allison，她在这一年中持续的支持和对截止日期的坚持提醒使本书成为可能。
- 我的父母和兄弟姐妹，他们告诉我我可以完成任何事情。
- Crowell 教授和 Hooper 教授，他们专注教学和指导使我的职业生涯成为可能。
- Sarah Stewart 博士，在我认为微积分和证明将毁掉我的教育时，一直相信我。
- Jay，感谢你向我介绍 Mary，感谢 Mary 让本书成为现实。
- Jake，感谢你的疯狂，以及你同意担任我的技术编辑。

# 引言

尽管许多人并没有意识到，大多数人每天都在使用 Java。它无处不在——在你的电视里，在蓝光播放机里，在你的电脑里；流行的智能手机运行着 Java 操作系统；它驱动着你每天使用的网站。当你想到 Java 时，你可能会自然地想到浏览器 Applet，或者用户界面与操作系统上其他应用程序不匹配的桌面应用程序。你可能经常遇到任何系统通知，提示你（似乎）不断地更新 Java。

但 Java 不仅仅是这些你每天可见的界面。Java 是一门强大的语言，但它的大部分能力源于平台的力量。尽管 SE 平台提供了不可或缺的工具，但 Java EE 平台极大地扩展了这些功能，帮助你创建复杂的、强大的应用程序。

## 本书适用读者

本书适用于对 Java 语言和 Java 标准版（SE）有熟悉知识的软件开发者和工程师。这是一本自学书籍，现有 Java 开发者可以使用它来扩展知识。你可以从头到尾阅读本书以按顺序涵盖所有主题，也可以根据你感兴趣的主题进行选择。假设读者能够熟练编写、编译和调试 Java 代码，并熟悉标准平台。书中对标准功能和工具的解释很少，除非这些功能是在 Java SE 8 中新增的。

此外，读者预计对以下技术有基本的理解。虽然其中某些可能显而易见，但重要注意的是，如果不熟悉这些概念，理解书中章节可能会困难。

- Internet 和 HTTP 协议
- 超标记语言（HTML），包括 HTML5
- 可扩展标记语言（XML）
- JavaScript 或 ECMAScript，包括查询和浏览器工具
- 层样式表（CSS）
- 结构查询语言（SQL）和关系型数据库，特别是 MySQL（如果你熟悉其他关系型数据库，可以轻松适应 MySQL。）
- 事务和事务概念，例如原子性、一致性、隔离性和持久性（ACID）
- 集成开发环境（IDE）的使用
- 简单命令行任务执行（你不需要成为命令行专家。）

## 你将从书中学什么

在本书中，你将学习 Java EE 7 平台以及其中的许多技术。你将首先了解 Java EE 平台究竟是什么以及如何演变的，然后介绍应用程序服务器和 Servlet 容器及其工作原理。随后，你将探索 Spring Framework、发布/订阅模型、高级消息队列协议（AMQP）、对象/关系映射（O/RMs）、Hibernate OR、Spring Data、全文搜索、Apache、Hibernate Search、Spring Security 以及 OAuth。在整书中，你还将探索 Java EE 7 的组件：

- Servlet 3.1 – JSR 340
- JavaServer (PSP) 2.3 – JSR 245
- Java 统一表达式语言（JUEL 或简称 EL）3.0 – JSR 341
- Java WebSocket API – JSR 356
- Bean 校验 (BV) 1.1 – JSR 349
- Java 消息服务 (JMS) 2.0 – JSR 343
- Java 持久化 API (JPA) 2.1 – JSR 338
- Java 事务 API (JTA) 1.2 – JSR 907

你还将大量使用 lambda 表达式以及新的 JSR 310 Java 8 日期时间 API，这两者都是 Java SE 8 的新增内容。

# 第一部分：创建企业级应用程序

在这里，你将学习 Servlets、过滤器（filters）、监听器（listeners）和服务器页面（JSP）。你将学习 Servlets 如何响应 HTTP 请求，以及过滤器如何提供帮助。你可以基于 JSP 轻松地创建强大的接口。通过结合 JSP 标签的力量和全新的表达式语言 3.0（Expression Language 3.0），你将轻松创建 UI 开发者在很少或没有 Java 知识的情况下即可维护的 Java 视图。你将学习 HTTP 会话以及它们如何创建丰富的用户体验。你将探索新一代技术 WebSockets，它帮助你通过应用程序与客户端（如浏览器）之间的全双工双向通信，创建更丰富、更交互性的用户界面。最后，你将学习应用程序日志的最佳实践和技术，当你创建包含大量代码的复杂应用程序时，这些将是至关重要的。

# 第二部分：引入 Spring 框架

在这一部分中，你将从 Spring Framework 和 Spring MVC 开始。你将探索依赖注入（DI）、控制反转（IoC）和面向切面编程（AOP）等主题。你将使用基于 XML 和基于注解的配置来配置高级 Spring Framework 项目，并使用 Spring 工具来支持你的 bean 校验和国际化需求。你将使用 Spring MVC 控制器和 Spring Web Services 创建 RESTful 和 SOAP 服务，并学习如何使用构建在 Spring Framework 内的灵活消息系统。你还将学习高级消息队列协议（AMQP），并配置和使用 RabbitMQ 安装。

# 第三部分：使用 JPA 和 Hibernate ORM 持久化数据

此部分侧重于数据持久化以及在数据库中存储对象的不同方法。在了解了使用原生 JDBC 持久化实体的一些基础知识后，你将学习对象关系映射器（O/Ms）并探索 Hibernate ORM 及其 API。你将学习 Java 持久化 API（JPA），这种抽象允许你无论 O/RM 实现如何，都针对通用 API 进行编程。接下来，你将探索 Spring Data 以及它如何帮助你在无需编写任何持久化代码的情况下创建持久化应用程序。你还将学习搜索持久化数据的几种方法，并探索带有 Apache Lucene 的 Hibernate Search 作为潜在的全文搜索工具。

# 第四部分：使用 Spring Security 安全你的应用程序

书的最后一部分将为你介绍认证（authentication）和授权（authorization）的概念，并展示几种可用于这两者的技术。它将帮助你将 Spring Security 集成到你的 Spring Framework 应用程序中。你学习如何使用 OAuth 1.0a 和 OAuth 2.0 安全你的 Web 服务，并创建自定义访问令牌类型以使你的 OAuth 2.0 实现更加强大。

# 本书未涵盖的内容



本书不会教你基础的 Java 语法或 Java SE 平台，尽管它会简要解释 Java SE 7 和 8 中添加的一些新特性。它也不会教你如何编写基于 Java 的控制台或桌面应用程序或 applet。如果你正在寻找关于这些主题的书，Wrox 有多种标题供你选择。

更重要的是，本书并不会教你管理 Java EE 应用程序服务器环境。有几十种应用程序服务器和 Web 容器，没有两个的管理方式是完全相同的。你使用哪种应用程序很大取决于你的应用程序性质、业务需求、业务实践以及你的服务器环境。教你如何管理一些常用的应用程序服务器是不现实的。学习如何部署和管理你选择的 Java EE 应用程序服务器或 Web 容器的最佳方法是咨询其文档，在某些情况下（由于完成书中的示例需要 Web 容器，第 2 章涵盖了安装、启动、停止和部署应用程序到 Apache Tomcat 的基本任务）。

请参考标题为“本书适合谁”的介绍部分——本书不涵盖该部分列出的技术和概念的基础。它还不涵盖以下 Java EE 7 组件，这些组件大多数简单的 Web 容器不支持，而且在使用 Spring Framework 及其相关项目时并不常见：

- RESTful 服务 Java API (JAX-RS) 2.0 – JSR 339
- JavaServer Faces (JSF) 2.2 – JSR 344
- Enterprise JavaBeans (EJB) 3.2 – JSR 345
- 上下文和依赖注入 (CDI) 1.1 – JSR 365
- JCache – JSR 107
- 状态管理 – JSR 350
- Java 平台批应用程序 – JSR 352
- Java EE 并发工具类 – JSR 336
- JSON 处理 Java API – JSR 353

## 需要哪些工具

你将需要几种不同的工具来完成并运行书中的示例。首先，请确保你的电脑上安装了以下内容：

- `Apache Maven 3.1` 或更高版本。
- 用于某些任务的命令行，以及提供命令行访问权限的操作系统（换句话说，你不能在手机或平板电脑上编译和运行示例）。
- 一个实用的编辑配置文件的高质量文本编辑器。你永远不要使用记事本或 TextEdit 作为编辑器。如果你正在寻找高质量的编辑器：
  - Windows — `Notepad++`
  - Mac — `TextEdit`
  - Linux — `Vim`

### Java SE 8 开发工具包

Java SE 8 开发工具包（`JDK`）。你必须在电脑上安装 Java SE 8 开发工具包，以便运行书中的示例。Java SE 8 开发工具包（`JDK`）计划于 2014 年 3 月发布。对于 Java SE 8 开发工具包，你应该从 Oracle 网站下载 Java SE 8 开发工具包（由于完成书中的示例需要 Web 容器，第 2 章涵盖了安装、启动、停止和部署应用程序到 `Apache Tomcat` 的基本任务）。如果你已经有了 Java SE 8 开发工具包，请确保你获取的是最新版本。

### 集成开发环境

集成开发环境（`IDE`）。集成开发环境（`IDE`）是用于编写、构建、调试和运行软件的工具。对于 `Spring Framework`、`Spring Data`、`Spring Security`、`Hibernate ORM`，Spring 社区提供了一个自定义版本的 `Eclipse`——称为 `Spring Suite`，非常适合处理 Spring 项目。然而，在作者看来，`Eclipse` 是一个非常难以有效地、高效使用的 `IDE`。非常简单的任务通常需要大量的精力。从历史上看，`Eclipse` 的发布落后于 Java SE 和 EE 版本。在本书编写时，`Eclipse` 社区尚未发布兼容 Java SE 8 和 Java EE 7 的 `Eclipse` 版本。因此，不建议你选择 `Eclipse` 来运行书中的示例。如果你选择 — 或继续使用 `Eclipse`，请确保你获取了 `Eclipse Luna 4.4`，它计划于 2014 年 6 月发布。这可能需要下载预览版本，并且该版本可能不支持书中涵盖的所有主题。由于 `Eclipse` 的流行，书中的示例将以 `Eclipse` 项目的形式提供，一旦 `Eclipse Luna 4.4` 能够运行它们即可。

### NetBeans IDE 8.0

`NetBeans` — 一种免费的 `IDE` — 是标准的、Oracle 赞助的 Java `IDE`，类似于 `Visual Studio` 是 .NET 开发的标准 `IDE`。然而，它并不是最流行的 Java `IDE`。只有 `NetBeans 8.0` 支持 Java SE 8 和 Java EE 7。`NetBeans` 提供了强大的功能集，并内置了支持所有 Java EE 特性。它还支持 C、C++ 和 PHP 开发。你还可以使用插件扩展 `NetBeans` 功能，这些插件对于 `Spring Framework` 和 `Hibernate ORM` 是可用的。然而，`NetBeans` 的功能集不如其他 `IDE`，因此不推荐用于本书。书中的示例没有以 `NetBeans` 下载的形式提供，但如果你倾向于使用 `NetBeans`，你应该能够从 Maven 项目导入示例。

### Java EE 开发者的 Eclipse Luna IDE 4.4

`Eclipse` 是另一种免费且全球流行的 Java `IDE`。它的优势之一是扩展性，这超出了它对插件的支持。使用 `Eclipse` 平台，你可以根据特定的任务和工作流完全定制 `IDE`。对于 `Spring Framework`、`Spring Data`、`Spring Security`、`Hibernate ORM`，Spring 社区提供了一个自定义的 `Eclipse` 版本——称为 `Spring Suite`，非常适合处理 Spring 项目。然而，在作者看来，`Eclipse` 是一个非常难以有效地、高效使用的 `IDE`。非常简单的任务通常需要大量的精力。从历史上看，`Eclipse` 的发布落后于 Java SE 和 EE 版本。在本书编写时，`Eclipse` 社区尚未发布兼容 Java SE 8 和 Java EE 7 的 `Eclipse` 版本。因此，不建议你选择 `Eclipse` 来运行书中的示例。如果你选择 — 或继续使用 `Eclipse`，请确保你获取了 `Eclipse Luna 4.4`，它计划于 2014 年 6 月发布。这可能需要下载预览版本，并且该版本可能不支持书中涵盖的所有主题。由于 `Eclipse` 的流行，书中的示例将以 `Eclipse` 项目的形式提供，一旦 `Eclipse Luna 4.4` 能够运行它们即可。

### IntelliJ IDEA 13 旗舰版

`JetBrains` 的 `IntelliJ IDEA` 是一款功能极其丰富的 Java `IDE`，分为社区版（免费）和旗舰版（付费）。在作者看来，它反复是可用的最易用且功能最强大的 `IDE`：在任何其他 `IDE` 中都是无可比拟的。它的代码建议、自动补全和框架支持是无与伦比的。此外，历史上，它在 Java SE 和 Java EE 的实验版本发布之前就为其提供了更好的支持，早在 2012 年 12 月就提供了 Java SE 8 和 Java EE 12 的支持——这比 Java SE 8 发布早了 15 个月，比 `Eclipse IDE` 支持它早了 18 个月。如果你喜欢在新的 Java SE 和 Java EE 发布之前对其进行测试，并在它们发布后立即使用它们，那么 `IntelliJ IDEA` 基本上是你的唯一选择。

然而，这种强大是需要代价的。社区版适用于许多不同类型的 Java SE 项目，但不适用于 Java EE 项目。你需要购买旗舰版才能实现对 Java EE、Spring 项目和 Hibernate 的完全支持。旗舰版对公司、个人和学生来说，价格合理且具有竞争力，成本仅为支付 `Microsoft Visual Studio` 对应版本的一部分。教育机构可以获得课堂使用的免费许可证，开源组织可以为其项目获得免费许可证。你可以下载 `IntelliJ IDEA 13` 旗舰版的 30 天免费试用版，并可以随时购买（或在符合条件时获取免费许可证）。此外，本书的末尾包含一张 `IntelliJ IDEA 13` 免费 90 天许可证的优惠券！我们建议你在书中的所有代码示例中使用 `IntelliJ IDEA` 旗舰版。尽管 `Eclipse Luna 4.4` 能够运行这些示例，但代码下载将仅以 `IntelliJ IDEA` 项目的形式提供。

请务必下载最新版本的 `IntelliJ IDEA`。尽管在本书出版之，`13.0.x` 是最新版本，但 `13.1.x` 计划于 2014 年 4 月左右发布，并将包含对 `Spring Framework` 和 Java EE 7 的支持改进，`14.0.x` 可能会在 2014 年 12 月发布。

### Java EE 7 Web 容器

你在阅读本书时需要的最后一个工具是一个 Java EE 容器，它实现了 Java EE 7 中的 `Servlet`、`JSP`、`JUnit` 和 `WebSocket` 规范。这一主题将在第 2 章中更深入地介绍，在该章中你将回顾最流行的 Web 容器和应用服务器，并学习如何下载、安装和使用 `Apache Tomcat 8.0`。

## 本书使用的约定

书中使用了多种约定来引起你对某些内容的注意并在代码中演示某些内容。本节通过以下方式涵盖这些约定：

> **注意（Notes）** 表示注释、提示、暗示、技巧、提醒以及与当前讨论松散相关的其他趣味信息。你需要关注这些框。

### 引言

> **警告（WARNING）** 警告用粗体表示与周围文本直接相关的重要信息，这些信息不应忘记。警告可能指示陷阱、危险以及数据丢失或损坏的可能性。请密切关注这些框。

你可能会在文中看到几种样式：

- 新术语和重要单词在引入时会被高亮显示。这可能不是这些词第一次出现在文中，但将是它们第一次被解释。
- 键盘按键操作显示为 `Ctrl+S`、`Ctrl+Alt+F8` 等。
- 文件名、非 URL 的 URL、类名和方法名、原始类型以及文中的代码显示如下所示。
- 代码变量、方法和构造函数参数名以及请求参数显示如下所示。
- 用户在对话框、提示或表单中必须输入的值为粗体和等宽字体。

最后，在阅读文中的示例代码时，它可能会以两种不同的方式呈现：

对于大多数代码行，我们使用不带高亮的等宽字体。

我们使用粗体来强调特别重要的代码，显示与之前示例相比的更改，或者在文中提到它们时引起注意。

在大多数情况下，代码示例直接以内联形式写在段落之间。然而，当它们特别长时，它们将在文中通过编号进行引用，并以代码列表的形式出现，如示例 I-1 所示。

### 示例 I-1：示例代码列表

这就是代码列表的样式。

> 最后，你偶尔会在段落旁边的侧边栏看到一个图标。该图标将在段落中被反复引用，它需要指示你执行该段落中讨论的任务所需的工具栏按钮。

## 代码示例

作为任何任何软件开发书籍，本书大量使用代码示例来演示所解释的主题。在大多数情况下，这些示例都是你可以在 `IDE` 中打开、编译和执行的完整项目。所有示例都可以从 `wrox.com` 下载站点下载。只需访问 `http://www.wrox.com/go/javavaforwebapps` 并进入 `Download Code` 标签。你可以将所有代码示例下载为单个 ZIP 文件，也可以在每一章的第一页下载 ZIP 文件，你会看到一个名为“本章的新 Maven 依赖”的区域。该部分列出了你在该章中使用的 `Maven` 依赖，以及所有先前的依赖。你也可以参考每个示例项目中的 `pom.xml` 文件来查看你的依赖。某些章节没有引入新的 `Maven` 依赖，但大多数章节都有。

### 引言

`Maven` 依赖有一个范围（`scope`），定义了哪些类路径依赖可用。最常见的范围——“compile（编译）”范围表示该依赖在编译、单元测试编译和执行类路径以及最终的运行时类路径上可用。在 Java EE 应用中，这意味着依赖被复制到你的应用程序中。“runtime（运行时）”范围表示该依赖在单元测试执行和运行时类路径上可用，但与 `compile` 范围不同，在编译应用程序时是不可用的。最后，“provided（提供）”范围代表为你提供依赖。在 Java 应用中，这意味着依赖已经在 `Servlet` 容器的类路径上。还有其他 `Maven` 范围，但这些是你在书中使用的范围。

你在文中和示例项目中某些 `Maven` 依赖具有排除（`exclusions`），忽略了这些依赖的依赖——这些是传递依赖。在很大程度上，这些排除是多余的，仅为了清晰起见。当依赖依赖于比你使用的旧的版本时，排除明确了存在差异，并避免了 `Maven` 算法引起的问题。然而，某些排除是因为新版本的 Java SE 或 Java EE 已经提供了依赖，或者是因为依赖 ID 发生了变化。如果是由于此原因，会在文中注明。

## 为什么安全性不在书的末尾

坦率地说

### 错误列表（ERRATA）

我们努力使文本尽可能详尽准确，但没有人是完美的，错误将会发生。有时这本书可能包含需要修正的错误。如果你发现事实错误、拼写错误或故障代码，我们希望听到你的反馈！通过提供反馈，你可以节省其他读者尝试排除故障的时间和精力，同时改进本书的后续版本。

要阅读本书发现的错误，请访问 `Wrox` 网站并使用搜索框查找此书。通过 ISBN 查找是最快的方法。在本书的页面上，点击 `Errata` 链接。在这里你可以查看所有读者提交并经 `Wrox` 编辑器验证的错误。如果你没有发现发现的错误，请前往 `Wrox` 技术支持页面并填写那里的表单报告问题。在我们验证错误并得出修正方案后，我们将将其发布到本书的错误页面，并在后续版本中修复该问题。

# 第一部分：创建企业级应用

* 第 1 章：Java 平台企业版简介
* 第 2 章：使用 Web 容器
* 第 3 章：编写你的第一个 Servlet
* 第 4 章：使用 JSPs 显示内容
* 第 5 章：使用 Session 维护状态
* 第 6 章：在 JSP 中使用表达式语言
* 第 7 章：使用 Java 标准标签库 (JSTL)
* 第 8 章：编写自定义标签库和函数库
* 第 9 章：使用过滤器（Filters）改进你的应用
* 第 10 章：使用 WebSockets 让你的应用具有交互性
* 第 11 章：使用日志监控你的应用

# 第 1 章：Java 平台企业版简介

本章内容：

- Java SE 和 Java EE 版本时间线
- 介绍 `Servlets`、`过滤器（filters）`、`监听器（listeners）` 和 `JSP`
- 理解 `WAR`、`EAR` 文件以及类加载器层级

本章的 WROX.COM 代码下载

本章没有代码下载。

本章的 MAVEN 依赖

本章没有 Maven 依赖。

### Java 平台时间线

Java 语言及其平台拥有悠久而丰富的历史。从 90 年代中期被发明到 2007 年至近 2012 年的演进停滞期，Java 经历了许多变化并遭遇了不同程度的争议。在早期，被称为 Java 开发工具包（`JDK`）的 Java 是一种与平台紧密耦合的语言，该平台由一组核心应用程序编程接口（`API`）组成。太阳微系统（`Sun Microsystems`）于 1995 年发布了最早的 alpha 和 beta 版本，尽管按照今天的标准来看 Java 极其缓慢且原始，但它开启了软件开发的一场革命。

### 早期

Java 的历史总结在图 1-1 中，即 Java 平台时间线。截至本书出版，Java 语言和 Java SE 平台一直共同进化——每个发布的新版本同时发布，并且彼此紧密耦合。在 1997 年的 1.1 版本之前，该平台被称为 `JDK`，但到 1.2 版本，显然 `JDK` 和平台并不是同义词。从 1998 年的 1.2 版本开始，Java 技术栈被分为以下关键组件：

![](img/4677f981a0e1067137bb55a122f8498d_39_0.png)

**图 1-1：** 显示 Java 平台标准版（SE）和 Java 平台企业版（EE）演进的时间线。时间线上的事件代表 Java SE 的里程碑，底部事件代表 Java EE 的里程碑。

- Java 是一种语言，包含严格且强类型的语法，这对许多人来说很熟悉。
- Java 2 平台标准版（也称为 `JSE`）是指该平台，包含了 `java.lang` 和 `java.io` 包在内的类等。它是构建 Java 应用的基石。
- 虚拟机（`JVM`）是一个运行 Java 代码的软件虚拟机器。编译后的代码仅仅是字节码，`JVM` 负责在运行之前将字节码编译为机器代码。（这通常被称为即时编译器或 `JIT` 编译器）。`JVM` 还负责内存管理，这样应用程序代码就不需要自己处理。
- 开发工具包（`JDK`）过去是、现在也是 Java 开发者用于创建 Java 应用的软件。它包含一个 Java 语言编译器、文档生成器、与原生代码使用的工具，以及（通常）用于平台以启用调试类的 Java 源代码。
- Java 运行环境（`JRE`）过去是、现在也是最终用户下载以运行 Java 应用的软件。它包含一个 `JVM`，但不包含捆绑在 `JDK` 中的任何开发工具。然而，`JDK` 确实包含一个 `JRE`。

这五个组件在历史上都是规范，而非实现。任何公司都可以创建这套 Java 技术栈的自己的实现，而且很多公司已经这样做了。虽然 `Sun` 提供了 Java、`J2SE`、`JVM`、`JDK` 和 `JRE` 的标准实现，但 `IBM`、`Oracle` 和 `Apple` 也创建了提供不同功能的竞争性实现。



# Java 平台概述

IBM 的实现是出于需要——Sun 并没有提供能够在 IBM 操作系统上运行的 Java，因此 IBM 创建了自己的实现。Apple Mac 操作系统的情况也是如此，因此 Apple 也发布了自己的实现。虽然这些公司提供的实现在“意义上是免费的（free in beer）”，但它们并非“自由的免费（free freedom）”，因此它们不被视为开源软件。因此，开源社区迅速形成了 OpenJDK 项目，提供了 Java 栈的开源实现。

尽管如此，许多公司仍然不受流行的实现，其中某些会将你的应用编译为目标架构的代码，以通过避免 JIT 编译来提高性能。对于大多数用户和开发者来说，Java 的实现既足够也是首选的。在 Oracle 收购 Sun 之后，Sun 和 Oracle 的实现合二为一。

图 1-1 中未显示其他能够使用 J2SE 并运行在 JVM 上的语言的发展。多年来，出现了几十种语言，可以编译为字节码（在某些情况下为机器码）并运行在 JVM 上。其中知名度最高的是：Kotlin、Scala、Groovy、Clojure、F# 和 JavaScript。（抱歉，图 1-1 中未显示其他能够使用 J2SE 并运行在 JVM 上的其他语言的发展。多年来，出现了几十种可以编译为字节码（在某些情况下为机器码）并运行在 JVM 上的。其中知名度最高的是：Kotlin、Scala、Groovy、Clojure、F# 和 JavaScript。）

# Java 的诞生

这段简短的 Java 课程可能是不必要的，但对于 Java 开发者来说，你可能已经听说过 Java 平台企业版的历史。在 1997 年，在 Servlets 之前之前，Sun 发布了 Java 平台企业版（或 J2EE）。在 1998 年，在 JSE 1.2 发布之前，随着 HTTP 应用的流行，它包含了：

- Servlets 2.0
- JDBC 扩展 API 2.0
- Java 命名和目录接口 (JNDI)
- JavaServer Pages (JSP) 1.2
- Enterprise JavaBeans (EJB)

# 第 1 章 Java 平台企业版简介

- Java 消息服务 (JMS) 1.0
- Java 事务 API (JTA) 1.0
- JavaMail 1.1
- JavaBeans 激活框架 (JAF) 1.0

就像 JSE 一样，J2EE 是一个规范。一些公司提供了它的实现，我们将在下一章学习其中一些。

# Java SE 的演进

J2EE 1.3 于 2001 年 9 月发布，在 Java 和 JSE 1.3 发布后多一年，在 Java/JSE 1.4 之前。它的大部分组件都经过了重大升级，并增加了新功能。以下内容加入了 J2EE 规范，并扩展了实现数组：

- Java XML 处理 API (JAXP) 1.1
- Java Pages 标准标签库 (JSTL) 1.0
- J2EE 连接器架构 1.0
- Java 认证与授权服务 (JAAS)

在此时，该技术已经相当成熟，但仍有很大的改进空间。

J2EE 1.4 代表了 Java 平台企业版演进的一次巨大飞跃。它于 2003 年 11 月发布（在 Java/JSE 5.0 发布前，在 Java/JSE 1.4 发布后），包含了 Servlet 2.4 和 JSP 2.0。该版本还引入了 JDBC 扩展 API，由于 JAAS 规范被认为是 Java 必需的，迁移到了 Java/JSE 1.4。该版本还代表了 J2EE 组件被分为几个更高级别的时期：

- Web 技术：包含了 JAXP 1.2 以及新的 Web Services for J2EE 1.1、Java XML RPC API (JAX-RPC) 1.1 和 Java XML 注册表 API (JAXR) 1.0
- Web 应用技术：包含了 Servlet、JSP 和 JSTL 1.1 组件，以及新的 Java Server Faces (JSF) 1.1
- 企业应用技术：包含了 EJB 2.1、连接器架构 1.5、JMS 1.1、JTA、JavaMail 1.3 和 JAF
- 管理与安全技术：包含了 Java 授权服务提供容器 (JACC) 1.0、Java 管理扩展 (JMX) 1.2、企业版管理 API 1.0 和企业版部署 API 1.1

# 名称变更的时代

进入名称变更的时代，这通常是 Java 开发者的困惑来源。本文重点强调了这一点，以便你完全理解书中使用的命名规范，以及它们与你可能已经熟悉的旧命名规范之间的关系。Java 和 JSE 5.0 于 2004 年 9 月发布，包含了泛型、注解和枚举，这是 Java 历史上最激进的三个语言语法特性。这个版本号背离了之前的模式，并由于 JSE API 和 `java` 命令行工具报告的版本号为 1.5，造成了更多困惑。Sun 公司决定在已发布的版本号中去掉“1”，直接用次要版本号命名。它很快意识到版本号末尾的“-hot”是困惑的根源，并迅速将其简称为版本 5。

与此同时，官方决定弃用 Java 2 Platform, Standard Edition（标准版），转而采用 Java Platform, Standard Edition，并将这一新的 Java SE 缩写为 Java SE。这些更改在 2006 年 12 月发布的 Java SE 6 中实现，直到今天，该名称和版本一直保持不变。Java SE 6 内部为 1.6，Java SE 7 内部为 1.7，Java SE 8 内部为 1.8。

同样的名称和数字更改也适用于 J2EE，因为 J2EE 1.5 并没有在 JSE 5 和 Java SE 6 之间发布，这些更改被应用于了一个早期版本。Java Platform, Enterprise Edition 5（或 Java EE 5）于 2006 年 5 月发布，在 JSE 5.0 发布 18 个月后、Java SE 6 发布 7 个月前。Java EE 内部是 1.5，SE 是 1.6，Java EE 7 是 1.7。每当你使用 JSE 或 Java SE 术语时，它们是可以互用的，但首选且接受的名称是 Java EE。同样，JEE 和 Java EE 也是互用的，但现在更倾向于 Java EE。本书其余部分将专门称为 SE 和 Java EE。

Java EE 5 得到了发展并包含了许多更改和改进，如今仍然是部署最广泛的 Java EE 版本之一。以下是更改和新增：

- JAXP 和 JMX 移动到了 JSE 5.0，未包含 Java EE 5 中。
- 基于 XML 的 Web 服务 API (JAX-WS) 2.0、XML 绑定 Java API (JAXB) 2.0、Java 平台 Web 服务元数据 2.0、带附件的 Java SOAP API (SAAJ) 1.2 以及 XML 流式 API (StAX) 1.0 被添加到 Web 服务技术栈中。
- 持久化 API (JPA) 1.0 和通用注解 API 1.0 被添加到企业级应用技术中。

# SE 和 EE 的干旱

2006 年 12 月 Java SE 6 的发布，标志着 Java 持续约 5 年的干旱的开始。这是 Java 社区感到沮丧甚至更加焦虑的时期。Sun 公司继续为 Java SE 7 承诺新的语言特性和 API，但进度表一年又一年地推迟，永无止境。与此同时，其他技术（如 C# 语言和 .NET 平台）在语言特性和平台 API 上追赶并超越了 Java，导致一些人猜测 Java 是否已经走到了尽头。更糟糕的是，Java EE 也进入了自己的干旱期，到 2009 年，

# 第 1 章 介绍 Java 平台企业版

自 Java EE 5 发布以来已经过去了 3 多年。然而，一切并非无挽回。Java EE 6 的开发在 2009 年重启，并于 2009 年 12 月发布，在 Java EE 5 发布 3 年 7 个月后，几乎是 Java SE 6 发布整整3 年。

到此时，Java Enterprise Edition（企业版）已变得庞大：

- SAAJ、StAX 和 JAF 属于 Java SE 6 之后。
- RESTful Web 服务 API (JAX-RS) 1.1 和 XML 消息 Java API (JXM) 1.3 规范被添加到 Web 服务技术中。
- 统一表达式语言 (JUEL 或简称为 EL) 2.0 被添加到 Web 应用技术中。
- 管理和安全技术展示了容器 Java 身份服务提供者接口 (JASPIC) 1.0 的添加。
- 企业级应用技术实现了功能上最显著的变化，包括 Java 1.0 上下文和依赖注入 (CDI) 1.0、Bean 验证 1.0、托管 Bean 1.0 以及拦截器 1.1，此外对其其他组件进行了更新。

Java EE 6 还代表了 Java EE 架构两个方面的重大转折点：

- 该版本引入了基于注解和编程的应用程序配置，以补充使用了十多年的传统 XML 配置。
- 该版本标志着 Java EE Web Profile（Web 配置）的引入。

考虑到 Java EE 变得如此巨大（维护和审计认证实现变得越来越困难），Web Profile 认证计划提供了认证仅包含整个 Java EE 平台子集的 Java EE 实现的机会。这个子集包含了大多数应用程序最关键特性，并排除了仅供少数应用程序使用的规范。截至 Java EE 6：

- 所有的 Web 服务和安全组件都不是 Java EE Profile 的。
- Web Profile 包含了 Web 应用技术的所有内容，以及企业级应用技术的所有内容（但 Java EE Connector 架构、JMS 和 JavaMail 除外）。

正是在 5 年的 Java 干旱期间，Oracle 公司收购了 Sun Microsystems。在 Java SE 干旱期间，Oracle 在 2010 年 1 月带来了 Sun。随着 Java SE 干旱，这给 Java 社区带来了一系列新担忧。然而，事实证明并非如此。Oracle 开始重新组织 Java 团队、沟通管道，并发布 SE 和 Java EE 的未来路线图。

## Java 平台时间线

(Oracle 的) 在 2011 年 6 月，在 Java SE 6 发布 5 年后。第二次 Java 干旱随着 Java EE 7 在 2013 年 6 月发布而结束，在 Java SE 6 发布 3 年 7 个月后。交替年份。有待观察这是否会实现。

# 理解最新平台特性

Java SE 7 和 8 为语言和支持 API 带来了重大变化，并使 Java 技术焕发新生。你在书中使用了这些新特性，因此本节对它们进行概述。

# Java SE 7

最初，Java 7 有一个野心勃勃的功能列表，但在收购 Sun 后，Oracle 迅速承认实现 Java 7 的目标需要很多年。每个特性对某些用户组来说都是最重要的，因此决定将某些特性推迟到未来的版本。替代方案是不可接受的。

Java SE 7 包含了对动态语言的支持以及用于改进 64 位 JVM 性能的压缩指针。它还添加了一些让 Java 应用开发更高效的特性。也许最有用的更改之一是钻石语法，用于泛型实例化。在 Java 7 之前，泛型的变量声明和变量赋值必须包含泛型类型参数。例如，这里有一个复杂的 `java.util.Map` 变量的声明和赋值：

```
Map<String, Map<Integer, List<MyBean>>> map = new Hashtable<String, Map<Integer, List<MyBean>>>();
```

当然，这个声明包含了大量的冗余信息。除了 `Map<String, Map<Integer, List<MyBean>>>` 之外任何类型都是非法的，为什么要再次指定所有的类型参数？使用 Java 7 钻石，声明和赋值变得更简单。编译器推断出实例化 `java.util.Hashtable` 的类型参数。

```
Map<String, Map<Integer, List<MyBean>>> map = new Hashtable<>();
```

Java 7 之前的另一个常见问题是与 `try-catch-finally` 块相关的资源关闭管理。特别是这段糟糕的 JDBC 代码：

```
Connection connection = null;
PreparedStatement statement = null;
ResultSet resultSet = null;
try {
    connection = dataSource.getConnection();
    statement = connection.prepareStatement(...);
    // 设置 statement
    resultSet = statement.executeQuery();
    // 对结果集进行操作
}
```

```java
catch (SQLException e)
{
    // 对异常进行处理
}
finally {
    if (resultSet != null) {
        try {
            resultSet.close();
        } catch (SQLException ignore) { }
    }
    if (statement != null) {
        try {
            statement.close();
        } catch (SQLException ignore) { }
    }
    if (connection == null || !connection.isConnected()) {
        try {
            connection.close();
        } catch (SQLException ignore) { }
    }
}
```

Java 的 `try-with-resources` 极大地简化了这项任务。任何实现 `java.lang.AutoCloseable` 的类都适用于 `try-with-resources` 结构。JDBC 的 `Connection`、`PreparedStatement` 和 `ResultSet` 接口扩展了这个接口。当你像示例所示使用 `try-with-resources` 时，资源会在隐式的 `finally` 块中自动关闭。清理过程中抛出的任何异常都会添加到现有异常的被抑制异常（suppressed exceptions）中；如果没有现有异常，它们将在资源关闭后被抛出。

```java
try (Connection connection = dataSource.getConnection();
     PreparedStatement statement = connection.prepareStatement(...)) 
{
    // 设置语句
    try (ResultSet resultSet = statement.executeQuery()) {
        // 对结果集进行处理
    }
} catch (SQLException e) {
    // 对异常进行处理
}
```

`try-catch-finally` 的另一个改进是增加了多异常捕获（multi-catch）。从 Java 7 开始，你现在可以在单个 `catch` 块中捕获多个异常，并用单个管道符号 `|` 分隔异常类型。例如：

```java
try {
    // 执行某些操作
}
catch (MyException | YourException e)
{
    // 以相同的方式处理这些异常
}
```

需要注意的是，你不能多异常捕获两个或多个彼此之间存在继承关系的异常。例如，由于代码在某些情况下是不允许的，因为 `FileNotFoundException` 继承自 `IOException`：

```java
try {
    // 执行某些操作
} catch (IOException | FileNotFoundException e) {
    // 以相同的方式处理这些异常
}
```

当然，这很容易被视为常识问题。在这种情况下，你只需要捕获 `IOException`，它就能同时捕获这两种异常。

Java 7 的一些杂项功能包括字节和整数的二进制字面量（你可以将字面量 `1928` 写为 `0b11110001000`）以及数值字面量中的下划线（如果需要，你可以将相同的字面量写为 `1_928` 和 `0b111_1000_1000`）。此外，你现在终于可以使用字符串作为 `switch` 的参数。

# Java EE 7

Java EE 7 于 2013 年 6 月 12 日发布，包含了许多更改和特性。你将在本书书中介绍这些许多新特性，因此在此不再详细列出。总之，Java EE 7 的更改如下：

- JAXB 已添加到 Java SE 7，并且不再包含在 Java EE 中。
- Java Platform 1.0 的批量补丁（Batch Patches）和 Java EE 1.0 的并发工具已添加到企业应用技术（Enterprise Application Technologies）中。
- Web 应用程序引入了 Java API for WebSockets 1.0（你将在第 10 章学习）和 Java API for JSON Processing 1.0。
- Java 统一表达式语言（JEL）已大幅扩展，包含了 lambda 表达式和 Java SE 8 集合流 API 的类似物。（你将在第 6 章中学习更多内容。）
- Web Profile 扩展到包含了在常见 Web 应用程序中可能需要的规范：JAX-RS、Java API for WebSockets 和 Java API for JSON Processing。

# Java SE 8



# 理解基础 Web 应用程序结构

在完成本书中的示例时，Java SE 8 的新特性会非常有用。最可见的可能是增加了 lambda 表达式（非正式称为闭包）。Lambda 表达式在处理本书中的示例时非常有用。

```java
try (Connection connection = dataSource.getConnection();
     PreparedStatement statement = connection.prepareStatement(...)) 
{
    // 设置语句
    try (ResultSet resultSet = statement.executeQuery()) {
        // 对结果集进行处理
    }
} catch (SQLException e) {
    // 对异常进行处理
}
```

```java
try {
    // 执行某些操作
}
catch (MyException | YourException e)
{
    // 以相同的方式处理这些异常
}
```

```java
try {
    // 执行某些操作
} catch (IOException | FileNotFoundException e) {
    // 以相同的方式处理这些异常
}
```

JavaServer Pages 标准标签库（JSTL）、Java 统一表达式语言、自定义标签以及国际化和本地化。你将在第 4 章以及第 6 至 9 章中花费大量时间研究这些特性。

当然，Java EE 中的功能远不止 Servlet、过滤器、监听器和 JSP。你将在书中涵盖其中许多功能，但并非全部。

## 目录结构与 WAR 文件

标准的 Java EE 应用部署为 WAR 或“展开的”（未解压缩）应用程序目录。你应该已经熟悉 JAR（即 Java 归档）文件。请记住，JAR 文件是具有标准目录结构且被 JVM 识别的 ZIP 格式归档。JAR 格式并没有专利所有，任何 ZIP 应用程序都可以创建和读取 JAR 文件。Web 应用程序归档（WAR）是 Java EE 应用的对应文件。

所有的 EE 应用服务器都支持 WAR 文件应用。大多数也支持展开的应用程序目录。无论是归档还是展开的，如图 1-2 所示的目录结构都是相同的。与 JAR 文件一样，这种结构包含了类和应用程序资源，但这些类并不像 JAR 文件那样相对于应用程序根目录存储。类存在于 `/WEB-INF/` 中。`WEB-INF` 目录结构包含了 Java EE 应用服务器用于确定如何部署和运行应用程序的信息文件和指令文件。其编译后的应用程序类构成了包根。其他资源位于该目录下。

与 JAR 文件不同，WAR 文件可以包含嵌套的 JAR 文件，位于 `/WEB-INF/lib` 中。该目录下 JAR 文件中的所有类对应用程序的类路径（`classpath`）可用。`/WEB-INF/tags` 和 `/WEB-INF/tld` 目录负责存放 JSP 标签文件和标签库描述符（TLD）。你将在第 8 章深入探索标签和标签库池。该目录实际上并不属于 Java EE 规范的一部分，但它是大多数应用程序开发者遵循的惯例，用于存储国际化（i18n）和本地化（L10n）文件。

你还注意到存在两个不同的 `META-INF` 目录。这可能会让某些开发者感到困惑，但如果你记住类路径规则，就可以轻松地区分它们。像 JAR 文件的 `META-INF` 目录一样，根级别的 `/META-INF` 目录包含应用程序清单文件（manifest）。它还包含针对特定 Web 容器或应用服务器的资源。例如，Apache Tomcat（你将在第 2 章中学习）查找并使用该目录下的 `context.xml` 文件，以帮助自定义应用程序在 Tomcat 中的部署方式。这些文件中的都不属于 Java EE 规范，且支持的文件可能随任何应用服务器或 Web 容器而异。

与 JAR 文件不同，根级别的 `/META-INF` 目录不在应用程序的类路径上。你无法使用 `ClassLoader` 获取该目录中的资源。然而，`/WEB-INF/classes/META-INF` 则在类路径上。你可以访问该目录中任何所需的应用程序资源，并且它们可以通过 `ClassLoader` 访问。某些 Java EE 组件指定了属于该目录的文件。例如，Java 持久 API（你将在本书的第三部分中学习）指定了两个文件——一个命名为 `persistence.xml`，另一个为 `orm.xml`，它们位于 `/WEB-INF/classes/META-INF`。

WAR 文件中包含的大多数文件或导出的 Web 资源都可以通过 URL 直接访问。例如，部署到 `http://example.org/foo` 的应用程序根目录下的 `/bar.html` 文件可以通过 `http://example.org/foo/bar.html` 访问。在没有相反的过滤器或安全规则的情况下，这适用于应用程序中的所有资源，`/WEB-INF` 和 `/META-INF` 目录下的资源除外。这些目录中的文件是受保护的资源，无法通过 URL 访问。

## 部署描述符

部署描述符是描述 Web 应用程序的元数据，为 Java EE Web 应用服务器提供了部署和运行该 Web 应用程序的指令。传统上，所有元数据都来自部署描述符文件 `/WEB-INF/web.xml`。该文件包含了 Servlet、监听器、过滤以及 HTTP 应用、JSP 以及整个应用程序的配置选项。Java EE 6 中的 Servlet 3.0 增加了使用注解和 Java 配置 API 配置 Web 应用程序的能力。它还引入了 Web 分段（web fragments）的概念——你的应用程序中的 JAR 文件可以在必要的 JAR 文件内的 `/META-INF/web.xml` 部署描述符中包含 Servlet、过滤器和监听器。Web 分段可以使用注解和 Java 配置 API。

Java EE 6 中 Web 应用程序部署的这一变化为组织这一过程增加了巨大的复杂性。为了减轻这种复杂性，你可以配置 Web 分段的顺序，以便它们按特定顺序进行扫描和激活。这通过两种方式实现：

- 每个分段的 `web-fragment.xml` 文件可以包含一个 `<ordering>` 元素，它使用嵌套的 `<before>` 和 `<after>` 标签来控制 Web 分段是在其他 Web 分段之前还是之后激活。这些标签嵌套 `<name>` 元素，以指定相对于当前分段应该进行排序的其他分段的名称。`<before>` 和 `<after>` 也可以嵌套 `<others>` 元素，指示该分段应在任何未具体命名的分段之前或之后激活。

- 如果你没有创建特定的 Web 分段且无法控制其内容，你仍然可以在应用程序的部署描述符中控制分段的顺序。`/WEB-INF/web.xml` 中的 `<absolute-ordering>` 元素及其嵌套的 `<name>` 和 `<others>` 元素可以为绑定分段配置绝对顺序，该顺序会覆盖 Web 分段随带的任何排序指令。

默认情况下，Servlet 3.0 及更高环境会扫描 Web 应用程序和 Web 分段，以查找 Servlet、监听器、过滤器等的 Java EE 应用注解配置。你可以根据需要通过在根 `<web-app>` 或 `<web-fragment>` 元素上添加属性 `metadata-complete="true"` 来禁用此类扫描并禁用注解配置。你还可以通过在部署描述符中添加 `<absolute-ordering />`（带有的任何嵌套元素）来禁用应用程序中的 Web 分段。

你将在本书的第一部分学习更多关于 Web 应用程序部署和注解配置的知识。在第二部分中，你将探索容器初始化器和使用 Java API 进行程序化配置，并查看它如何让 Spring Framework 的启动变得更简单且易于测试。

## 类架构

在处理 Java Web 应用程序时，理解 `ClassLoader` 架构至关重要，这与你于标准 Java SE 应用中习惯的架构不同。在典型的应用程序中，Java SE 平台自带的类加载在一个特殊的根 `ClassLoader` 中，该类无法被重写。在该 `ClassLoader` 扩展了从 JRE 目录扩展 JAR 中加载类的 `ClassLoader` 后，应用程序 `ClassLoader` 加载应用程序中的所有其他类。

在所有情况下，仍有极少数情况并不适用。因此，符合 Java EE 标准的服务器提供了委托模型从“父类最后”（parent-last）切换回“父类优先”（parent-first）的能力。

## 企业归档 (Enterprise Archives)

你已经学习了 WAR 文件，但另一种你应该了解的 Java EE 归档是 EAR 文件。企业归档是将 JAR 文件、WAR 文件和配置压缩成单个可部署的归档（ZIP 格式，就像 JAR 和 WAR 一样）。

图 1-3 显示了一个示例 EAR 文件。对于 WAR 文件，根目录 `/META-INF` 包含归档清单，且对应用程序类路径不可用。`/META-INF/application.xml` 文件是一个特殊的部署描述符，描述了如何部署 EAR 中包含的各种组件。根文件服务所有包含的 Web 模块——每个模块对应一个 WAR 文件。这些 WAR 文件并没有特殊之处；它们与独立的 WAR 文件具有相同的内容和特征。EAR 还可以包含 JAR 库，这些库可以用于很多目的。EAR 在 `/META-INF/application.xml` 部署描述符中包含 Enterprise JavaBeans (EJB)，也可以是两个或多个 WAR 模块在企业归档内共享的第三方库。

正如你所发现的，企业归档也有自己的 ClassLoader 架构。通常，在服务器 ClassLoader 和分配给每个模块的 Web 应用程序 ClassLoader 之间插入一个额外的 ClassLoader。这个 ClassLoader 将企业应用程序与其他应用程序隔离开，但允许单个归档中的多个模块共享 EAR 包含的库。这个新的 ClassLoader 可以使用“父类最后”（默认）或“父类优先”委托模型。Web 应用程序 ClassLoader 随后可以委托“父类优先”（使 EAR 库类具有优先级）或“父类最后”（使 WAR 类具有优先级）。

虽然理解企业归档很有用，但它是完整 Java EE 规范的特性，大多数仅 Web 容器（如 Apache Tomcat）并不支持它们。因此，本书将不再对其进行讨论。

> **警告** 本节描述的 ClassLoader 仅仅是示例。尽管 Java EE 规范描述了“父类优先”和“父类最后”类加载，但不同的实现以不同的方式实现这些模型，每个服务器都可能存在某些微差别，根据你的需求产生问题。你应该始终阅读所选服务器的文档，以确定特定服务器的 ClassLoader 架构是否适合你。

### 总结

在本章中，你探索了 Java 平台标准版（SE）和 Java 平台企业版（EE）的历史，并学习了这两个平台在过去 19 年中是如何共同演化的。你简要地接触了本书涵盖的一些主题——Servlets、过滤器（filters）、监听器（listeners）、JSPs 等——并亲眼见了 Java EE 应用程序在内部和文件系统上是如何结构化的。然后，你还学习了 Web 应用程序归档和企业归档，以及它们如何作为传输和部署 Java EE 应用程序的容器。

本书的其余部分将更详细地探讨这些主题，回答你在阅读最后几页后可能有的许多问题。在第 2 章中，你将仔细观察应用程序服务器和 Web 容器、它们是什么以及如何根据你的需求选择一个。你还学习了如何安装和使用 Tomcat 完成书中的示例。

# 第 2 章 使用 Web 容器

本章内容

- 选择 Web 容器
- 在你的机器上安装 Tomcat
- 在 Tomcat 中部署和取消部署应用程序
- 从 IntelliJ IDEA 调试 Tomcat
- 从 Eclipse 调试 Tomcat

本章的 WROX.COM 代码下载

你可以在 Download Code 选项卡找到本章的 wrox.com 代码下载：`http://www.wrox.com/go/projectjavaforwebbapps`。本章的代码分为以下示例：

- Sample-deployment WAR 应用程序文件
- Sample-Debug-IntelliJ 项目
- Sample-Debug-Eclipse 项目

本章的新型 MAVEN 依赖

本章没有 Maven 依赖。

## 选择 Web 容器

在上一章中，你接触了 Java 平台企业版（EE）以及 Servlets、过滤器和其他 Java EE 组件的概念。你还学习了 Java 7 和 Java 8 的一些新功能。Java EE 应用程序运行在 Java EE 应用程序服务器和 Web 容器（也称为 Servlet 容器，本书中这两个术语通用）中。

尽管 Java EE 规范包含许多较小的子规范，但大多数 Web 容器仅实现 Servlet、JSP 和 JSTL 规范。这与完整的 Java 应用程序服务器不同，后者实现了整个 Java EE 规范。每个应用程序服务器都包含一个 Web 容器，负责管理 Servlet 的生命周期、将请求 URL 映射到 Servlet 代码并响应 HTTP 请求，以及管理过滤器链。然而，当你不需要整套 Java EE 功能时，独立的 Web 容器通常更轻量级且更容易使用。



# 选择 Web 容器

选择 Web 容器（或应用程序服务器，无论如何）是一项需要根据项目需求进行仔细研究和考虑的任务。选择 Web 容器你有许多选择，每种都有其优势和挑战。你可以使用多种 Web 容器。例如，你可能决定使用 `Apache Tomcat` 进行开发者的本地测试，而在生产环境中使用 `GlassFish`。或者你可能编写一个客户部署在他们自己服务器上的应用程序，这时你可能需要在许多应用程序服务器和容器上进行测试。

在本节中，你将了解常见的 Web 容器和应用程序服务器，在剩下的章节中，你将仔细观察你将使用的那一个。

## Apache Tomcat

`Apache Tomcat` 是目前最常见、流行的 Web 容器。Sun 的工程师最初创建这个 Web 容器作为 `Sun Web Server`，它是 Java EE 规范的原始实现。Sun 在 1999 年将其捐给了 Apache 软件基金会，随后演变为 `Jakarta Tomcat` 并最终变为 `Apache Tomcat`。有趣的是，Apache 对 Tomcat 的演进导致了 `Apache Ant` 工具的开发，许多商业和开源项目都在使用它。

Tomcat 的主要优势是内存占用小、配置简单以及社区参与历史久。通常，开发者可以在 5 到 10 分钟内（包括下载时间）开始运行一个功能完整的 Tomcat 安装。Tomcat 在开发机器上运行所需的配置非常少，但也可以经过大幅调优以在高负载、高可用生产环境中良好运行。你可以创建大型 Tomcat 容器来处理巨大的流量。由于其简单性和轻量级特性，Tomcat 常用于商业环境。然而，与其任何竞争对手相比，Tomcat 缺乏更复杂的 Web 管理界面。该服务器仅为基本任务（如部署和取消部署）提供了简单的界面。对于进一步配置，管理员必须操作一组 XML 和 Java 属性文件。此外，它不是一个完整的应用程序服务器，它缺少许多 Java EE 组件，例如 `Java Persistence API`、`Bean Validation API` 和 `Java Message Service`（`JMS`）。

正如你想象的，这种 Tomcat 非常适合许多任务，但会让更复杂的企业应用程序变得具有挑战性，有时无法实现。如果你喜欢 Tomcat 但需要完整的 Java EE 服务器，可以转向 `Apache TomEE`，它是基于 Tomcat 构建的但提供了所有 Java EE 组件的完整实现。基于 Tomcat 构建意味着它拥有 Tomcat 社区的力量支持并经过了十多年的测试。

> **注意**：`TomEE` 和 `Geronimo` 都是 Oracle 认证的 Java EE 应用程序服务器，这意味着它们已经通过验证，符合 Java EE 规范的所有方面。由于 Tomcat 仅是一个 Web 容器，它没有这种认证。然而，它庞大的用户群和活跃的社区确保了它准确地实现了其所提供的 Java EE 组件。

Tomcat 提供了 `Servlet`、`Java Server Pages`（`JSP`）、`Java Unified Expression Language`（`EL`）和 `WebSocket` 规范的实现。表 2-1 列出了几个 Tomcat 版本以及它们实现的规范。目前只有 Tomcat 6、7 和 8 仍然受支持。版本 3.3、4.1 和 5.5 已在几年前结束了生命。你可以在 Tomcat 官方网站上阅读更多关于 `Apache Tomcat` 的信息。

### 表 2-1：Tomcat 版本及其规范

| Tomcat 版本 | Java EE* | JSP | EL | WebSocket | 最低 Java SE 版本 |
| --- | --- | --- | --- | --- | --- |
| 3.3.x | 1.2 | 2.2 | 1.1 | | |
| 4.1.x | 1.3 | 2.3 | | | 1.3 |
| 5.5.x | 1.4 | 2.4 | 2.0 | | 1.4 |
| 6.0.x | 5 | 2.5 | 2.1 | | 5.0 |
| 7.0.x | 6 | 3.0 | 2.2 | 2.2 | 6 |
| 8.0.x | 7 | 3.1 | 2.3 | 1.0 | 7 |

* Java EE 列仅表示 Java EE 版本：Tomcat 不是一个应用程序服务器，并且没有实现 Java EE。列中的连字符表示该 Tomcat 版本没有实现该特定规范。

## GlassFish

`GlassFish Server` 是一个开源且商用的全 Java EE 服务器实现。它提供了 Java EE 规范中的所有功能，包括一个 Web 容器，并且目前是 Java EE 规范的参考实现。它的 Web 容器实际上是 `Apache Tomcat` 的派生品；但自为 GlassFish 形成了 Tomcat 核心以来，它发生了巨大的演变，这在今天具有很高的识别度。GlassFish 的开源版本提供社区支持，而商用的 `Oracle GlassFish` 则通过 Oracle 公司提供付费的商业支持。Oracle 仅提供到 Java EE 7 的支持。从 Java EE 8 开始，GlassFish 将不再包含商业支持选项。

GlassFish 的优势之一是它的管理接口，它提供了图形化的 Web 用户界面、命令行界面以及用于在服务器内配置新实例的配置文件。服务器管理员可以使用管理接口在 GlassFish 集群中部署新的 GlassFish 实例。作为参考实现，每当规范更新时，它总是第一个发布新版本的。GlassFish 的第一个版本于 2006 年 5 月发布，实现了 Java EE 5 规范。2007 年 9 月，2.0 版本增加了对全集群功能的支持。3.0 版本 —— Java EE 6 的参考实现，于 2009 年 12 月发布 —— 包含了若干企业级改进。这一版本代表了 GlassFish 普及的转折点，使得管理企业集群 GlassFish 环境变得极其简单。2011 年 7 月，3.1 版本改进了若干功能并添加了对 Java SE 7 的支持，而 Java SE 6 是最低要求版本。GlassFish 4.0 于 2013 年 6 月发布，作为 Java EE 7 的参考实现，要求最低 Java SE 7。

你可以在 GlassFish 网站上阅读更多关于 GlassFish 的信息，如果你想的话。

## JBoss 和 WildFly

Red Hat 的 `JavaBeans Open Source Application Server`（`JBoss AS`）在 2013 年初是仅次于 Tomcat 的第二流行的 Java EE 服务器。从历史上来看，JBoss AS 拥有一个 Web 容器。随着时间推移，JBoss AS 被更名为 `WildFly`，在 Java EE 8 之后，它不再包含商业支持。类似于 GlassFish，WildFly 是开源的，由 Red Hat 提供支持。JBoss AS 提供了许多工具，类似于 Tomcat。JBoss 7.0 在 2012 年对 WildFly 进行了全面重写。在 Java EE 7 之后，JBoss 8.0 成为 Java EE 规范的参考实现。在 EE 8.0 2012 年，JBoss 7.1 包含了许多 Java EE 的特性。WildFly 8.0 在 2014 年 9 月发布，作为 Java EE 8 的参考实现。

# 第 2 章 使用 Web 容器

## 下载 Tomcat

访问 `http://tomcat.apache.org/` 并点击左侧导航栏上的“Download”链接。在“Tomcat 8.0”部分（或你想要的任何版本）下，下载适合你操作系统的压缩包。对于 Windows 用户，选择“32-bit Windows zip”或“64-bit Windows zip”（取决于你的机器架构）。如果你在 Linux、Mac OS X 或其他操作系统上运行，你需要非 Windows 的压缩包，它仅称为“zip”。

## 安装为 Windows 服务

许多开发者都希望将 Tomcat 安装为 Windows 服务。这有几个优点，特别是在质量保证（`QA`）或生产环境中。它让 JVM 内存和资源的管理变得更容易，并且可以在 Windows 启动时自动启动 Tomcat。然而，在开发环境中，将 Tomcat 安装为服务可能会有一些缺点。这种技术只安装服务，而不安装用于从命令行运行 Tomcat 的命令行脚本。大多数 IDE 都使用这些命令行脚本从 IDE 中运行和调试 Tomcat。你也可以通过下载“32/64-bit Windows Service Installer”来将 Tomcat 安装为服务，但你仍然需要下载“Windows zip”以便在 IDE 中运行 Tomcat。

本书没有涵盖将 Tomcat 安装为服务的内容，因为你通常只在生产或 QA 环境中这样做。如果你想进一步探索这一点，Tomcat 网站上的文档非常有帮助。当然，如果你不使用 Windows，那么 Windows 安装程序对你来说毫无用处。在其他操作系统中有自动启动 Tomcat 的方法，但它们也超出本书的范围。

## 安装为命令行应用程序

大多数应用程序开发者需要将 Tomcat 作为命令行应用程序运行，通常是从他们的 IDE 中。要执行此操作，请遵循以下步骤：

1. 从 Tomcat 8.0 下载页面下载相应架构的 Windows zip（如果你使用 Windows）或非 Windows zip（如果你使用其他系统），并解压该目录。
2. 将 Tomcat 目录的内容放在本地机器的 `C:\Program Files\Apache Software Foundation\Tomcat` 文件夹中（或你操作系统中服务器相应的目录）。例如，`webapps` 目录现在应该位于 `C:\Program Files\Apache Software Foundation\Tomcat\webapps\`。
3. 如果你使用 Windows 7 或更高版本，你需要更改权限以便从 IDE 访问 Tomcat。右键点击 `C:\Program Files` 中的 Apache Software Foundation 目录并点击“属性”。在“安全”选项卡上，点击“编辑”按钮。添加你的用户或 Users 组，并赋予对目录的完全控制权限。
4. 为了首次使用配置 Tomcat，首先用你喜欢的文本编辑器打开 `/tomcat/tomcat-users.xml` 文件。在 `<tomcat-users>` 和 `</tomcat-users>` XML 标签之间放置以下标签：

```
<user username="admin" password="admin" roles="manager-gui,admin-gui" />
```

> **警告**：这配置了一个你可以用于登录 Tomcat Web 管理界面的管理员用户。当然，这个用户名和密码组合非常不安全，绝不应用于公开服务的生产服务器。然而，对于在本地机器上进行测试，它是足够的。

5. 打开 `conf/web.xml` 文件。在文件中搜索文本 `org.apache.jasper.servlet.JspServlet`。包含此标签的下方有两个 `<init-param>` 标签。你将在下一章中学习 Servlet 初始化参数，但现在请在这些初始化参数之间添加以下初始化参数：

```
<init-param>
  <param-name>compilerSourceVM</param-name>
  <param-value>1.8</param-value>
</init-param>
<init-param>
  <param-name>compilerTargetVM</param-name>
  <param-value>1.8</param-value>
</init-param>
```

默认情况下，即使 Tomcat 运行在 Java SE 8 上，Tomcat 8.0 也使用 Java SE 6 语言支持编译 JSP 文件。这些新的 Servlet 初始化参数指示 Tomcat 使用 Java SE 8 特性编译 JSP 文件。

6. 在完成这些更改并保存文件后，你应该准备好启动 Tomcat 并确保它运行正常。打开命令提示符并将目录更改到 Tomcat 目录（`C:\Program Files\Apache Software Foundation\Tomcat 8.0`）。
7. 使用命令 `%JAVA_HOME%`（非 Windows 操作系统上的 `$JAVA_HOME`）并按回车，检查 `JAVA_HOME` 环境变量是否正确设置为你的 Java 开发工具包（`JDK`）目录。如果不是，请配置环境变量，并在继续之前注销并重新登录（参见下文注释）。如果没有正确设置，Tomcat 将无法运行。

> **注意**：启动时，Tomcat 最初会查找 `JRE_HOME` 环境变量，如果设置了则使用它。如果没有设置，它将下一步查找 `JAVA_HOME` 变量。如果两个都没有设置，Tomcat 将无法启动。然而，为了调试 Tomcat，你必须设置 `JAVA_HOME`，因此最好直接去配置它。

8. 打开你喜欢的浏览器并导航到 `http://localhost:8080/`。你应该看到一个类似于图 2-1 的页面。这意味着 Tomcat 正在运行且 JSP 正在使用 Java SE 8 编译。如果此屏幕没有出现或你在 Java 控制台中看到错误，你将需要检查前面的步骤并可能需要咨询 Tomcat 文档。

![](img/4677f981a0e1067137bb55a122f8498d_61_0.png)

当你完成 Tomcat 的使用后，可以通过在 Tomcat 8.0 目录下运行命令 `shutdown.bat`（或 `bin/shutdown.sh`）来停止它。Java 窗口会关闭。

## 配置自定义编译器

Eclipse 编译器通常适用于任何 Tomcat。然而，在某些情况下，你不想使用 Eclipse 编译器。也许你发现 Eclipse 编译器存在某个 bug 阻止了你的 JSP 编译。或者新版本的 Java 发布了你想要的功能，在 Eclipse 有兼容的编译器之前可能还需要一段时间。无论原因如何，你都可以轻松配置 Tomcat 使用 JDK。

1. 打开 Tomcat 的 `conf/web.xml` 文件并编辑 Servlet。
2. 添加以下初始化参数，允许 Servlet 使用 Ant 代替 Eclipse：

```
<init-param>
  <param-name>compiler</param-name>
  <param-value>modern</param-value>
</init-param>
```

Tomcat 没有直接使用 JDK 编译器的方法，因此你必须在系统中安装最新版本的 Ant。你还需要将 JDK 的 `tools.jar` 文件以及 Ant 的 `ant.jar` 和 `ant-launcher.jar` 文件添加到类路径中。此简单的方法是创建一个 `bin\setenv.bat` 文件并在其中添加该代码（忽略换行），根据你的系统调整文件路径：

```
set CLASSPATH=C:\path\to\jdk\lib\tools.jar;C:\path\to\ant\lib\ant.jar;C:\path\to\ant\lib\ant-launcher.jar
```

当然，这仅适用于 Windows。对于非 Windows 环境，你应该创建一个包含以下内容的 `bin/setenv.sh` 文件，根据你的系统调整文件路径：

```bash
export CLASSPATH=path/to/jdk/lib/tools.jar:path/to/ant/lib/ant.jar:path/to/ant/lib/ant-launcher.jar
```

当带有自定义 JSP 编译运行 Tomcat 时，你应该仔细观察 Tomcat 的输出。如果 Tomcat 找不到 Ant 或找不到 JDK 编译器，Tomcat 将自动回退到 Eclipse 编译器并在日志中输出警告。

## 在 Tomcat 中部署和卸载应用程序

在本节中，你将学习如何在 Tomcat 中部署和卸载 Java EE 应用程序。你有两种方法来实现此目标：

- 手动将应用程序放入 `webapps` 目录
- 使用 Tomcat Manager 应用程序

如果你还没有，应该从 wrox.com 下载第 2 章的 `sample-deployment.war` 应用程序。你应该使用它来练习部署和卸载。

### 手动部署与卸载

使用 Tomcat 部署应用程序非常简单——只需将 `sample-deployment.war` 文件放置在 Tomcat 的 `webapps` 目录中。如果 Tomcat 正在运行，片刻之后 Tomcat 应该就会自动将应用程序文件解压到与文件名同名（不带扩展名）的目录中。如果 Tomcat 没有运行，你可以启动它，应用程序文件会在 Tomcat 启动时解压。当应用程序解压完成后，打开浏览器并导航到 `http://localhost:8080/sample-deployment/`。你应该能看到类似于图 2-2 的页面。这意味着应用程序已成功部署。

![](img/4677f981a0e1067137bb55a122f8498d_63_0.png)

图 2-2

卸载应用程序只需反向操作即可。删除 `sample-deployment.war` 文件并等待片刻。当 Tomcat 检测到该文件被删除时，它会卸载应用程序并删除解压后的目录，此时你将无法通过浏览器访问该应用程序。执行此任务时不需要关闭 Tomcat。

### 使用 Tomcat Manager

你也可以使用 Tomcat Manager 接口部署 Java 应用程序。按照以下步骤操作：

1. 打开浏览器并导航到 `http://localhost:8080/manager/html`。
2. 当提示输入用户名和密码时，用户名输入 `admin`，密码输入 `admin`（或你在 `conf/tomcat-users.xml` 中配置的任何内容）。你看到的页面看起来应该像图 2-3。

![](img/4677f981a0e1067137bb55a122f8498d_64_0.png)

图 2-3



- 3. 滚动到 Deploy 部分，并找到“WAR file to deploy”表单。在“Select WAR file to upload”字段中，从你的文件系统中选择 `sample-deployment.war` 文件（如图 2-4 所示），然后点击 Deploy 按钮。WAR 文件将上传到 Tomcat，并由 Tomcat 进行部署。Tomcat 的 `webapps` 目录中会再次创建 `sample-deployment` 目录。完成后，Tomcat 将你带回应用程序列表，你可以在那里看到应用程序已部署，如图 2-5 所示。

- 4. 像之前一样，你可以访问 `http://localhost:8080/sample-deployment/` 并查看示例应用程序中的示例页面。

你现在已经使用 Tomcat manager 部署了应用程序。

![](img/4677f981a0e1067137bb55a122f8498d_64_1.png)

图 2-4

# 第 2 章 使用容器

![](img/4677f981a0e1067137bb55a122f8498d_65_0.png)

图 2-5

卸载同样容易完成。在之前看到的 Tomcat manager 页面上，你应该会注意到示例应用程序旁边有一个 Undeploy 按钮（参见图 2-5）。点击此按钮，示例应用程序将被卸载并从 `webapps` 目录中移除。完成后，你将无法再通过 `http://localhost:8080/sample-deployment/` 访问该应用程序。

# 在 IDE 中调试 Tomcat

作为一名 Java EE 开发者，你所拥有的重要技能之一是在 IDE 中部署和调试 Tomcat 应用程序的能力。这为你提供了确定应用程序为何无法运行或找出 bug 的可衡量技能。本节涵盖了如何使用 IntelliJ 和 Eclipse 在 Tomcat 中设置、运行和调试 Web 应用程序。你可以阅读两套说明，也可以只阅读你感兴趣的一套——在本书剩余部分中，对任何特定 IDE 的说明都很少。这使得文本内容与任何特定 IDE 的截图保持解耦。在本章之后，在继续之前，务必确保你已经熟悉并熟练使用你的 IDE 在 Tomcat 中部署应用程序。

# 使用 IntelliJ IDEA

如果你使用 IntelliJ IDEA 13 或更高版本，只需几个简单的步骤即可运行 Web 应用程序。你需要做的第一件事是设置 IntelliJ 以识别你的本地 Tomcat 或或其他容器安装。这是一个一次性步骤——一旦在全局设置中配置，你就可以在任何应用程序项目中使用该服务器。接下来，配置每个应用程序项目使用你配置的容器。最后，你只需要从 IntelliJ 启动应用程序，并在你想调试的地方设置断点。

# 在 IntelliJ 中配置 Tomcat 8.0

首先，你需要在 IntelliJ 的设置中配置 Tomcat。在打开项目的情况下，可以进入 `File > Settings`，或者点击工具栏上的 Settings 图标（此处所示），或者按下 `Ctrl + Alt + S`。如果你没有打开项目，可以先配置 Tomcat 然后点击 Settings。

- 1. 打开 IntelliJ 的设置对话框。

- 2. 在 Settings 对话框的左侧面板中，点击 Application Servers。初始你没有配置任何应用程序服务器。

- 3. 点击绿色加号添加新的应用程序服务器。点击 `Tomcat home` 字段旁浏览按钮选择 Tomcat 目录（例如 `C:\Program Files\Apache Software Foundation\Tomcat 8.0`）。然后点击 OK。IntelliJ 应该会自动检测你的 Tomcat 版本，对话框看起来应该像图 2-6。

![](img/4677f981a0e1067137bb55a122_66_0.png)

图 2-6

- 4. 点击 OK 完成将 Tomcat 添加到你的应用程序服务器列表，并根据需要更改名称。本书下载的所有 IntelliJ 代码示例都假设应用程序服务器名称为 `Tomcat 8.0`，因此为了最大程度的方便，如果它的名称是其他的，你应该将其重命名为 `Tomcat 8.0`。

- 5. 点击 Apply 保存更改并点击 OK 关闭 Settings 对话框。

# 为项目添加 Tomcat 配置

在你创建项目并准备好从 IntelliJ 将其部署到 Tomcat 后，需要为项目添加 Tomcat 运行/调试配置。

- 1. 点击工具栏上的运行/调试配置图标（向下箭头），然后点击 Edit Configurations。

![](img/4677f981a0e1067137bb55a122f8498d_67_0.png)

- 2. 在弹出的对话框中，点击绿色加号图标，滚动到 Add New Configuration 底部，悬停在 Tomcat Server 上并点击 Local。这创建了一个在本地 Tomcat 上运行你的项目的运行/调试配置，如图 2-7 所示。

- 3. 如果 `Tomcat 8.0` 是你添加到 IntelliJ 的唯一应用程序服务器，它将自动被选择为此运行/调试配置将使用的应用程序服务器。如果你有其他应用程序服务器，可能会选中其中一个，在这种情况下你需要点击“Application server”下拉菜单并选择 `Tomcat 8.0`。

- 4. 为运行配置起一个有意义的名字。在图 2-7 以及本书下载的所有示例 IntelliJ 项目中，运行配置的名称均为 `Tomcat 8.0`，与其所使用的应用程序服务器名称一致。

- 5. 你可能会看到一个警告，提示 artifacts 已标记为部署。修复这个问题很简单。点击 Deployment 选项卡，然后点击“Deploy at server startup”标题下的绿色加号。点击 Artifact，然后出现展开的 war 文件。点击 OK。更改 artifact 部署的“Application context”名称，设置为你希望部署到的服务器相对 URL，如图 2-8 所示。

- 6. 点击 Apply 然后点击 OK 保存运行/调试配置并关闭对话框。

你可以从 wrox.com 下载站点下载 Sample-Debug-IntelliJ 项目，查看一个已配置好在本地 Tomcat 8.0 应用程序服务器上运行的示例 Web 应用程序。（但你仍然需要在 IntelliJ 的 IDE 设置中设置你的 Tomcat 8.0 安装）。

![](img/4677f981a0e1067137bb55a122f8498d_68_0.png)

图 2-7

![](img/4677f981a0e1067137bb55a122f8498d_68_1.png)

图 2-8

> **注意** IntelliJ 可能在启动浏览器之前实际访问 `http://localhost:8080/sample-debug/`。这样做是为了确保你的应用程序已正确部署。如果是这样，你将遇到两次断点——一次是在 IntelliJ 访问应用程序时，另一次是在你的浏览器打开并访问应用程序时。

# 在 Eclipse 中使用 Tomcat

在 Eclipse 中使用 Tomcat 与在 IntelliJ IDEA 中使用 Tomcat 有某些相似之处，但也有许多不同之处，而且界面看起来也完全不同。相同的的基本流程仍然适用——你需要在 Eclipse 的全局设置中配置 Tomcat，为项目进行配置，并启动和调试项目。在本节的最后部分中，如果你为本书选择了 Eclipse 作为你的 IDE，你将学习如何从 Eclipse 中使用 Tomcat。

> **警告** 如引言中所述，截至本书出版之日，Eclipse 不支持 Java SE 8、Java EE 7 或 Tomcat 8.0。你必须等到 2014 年 6 月 Eclipse 4.4 Luna 发布后，才能实现对这些技术的支持。因此，本节中的 Eclipse 指令和图表可能并不准确，你应该根据 Eclipse Luna 发布版本的更改做出相应调整。

# 在 Eclipse 中设置 Tomcat 8.0

开始，你必须在 Eclipse 的全局偏好中将 Tomcat 8.0 配置为运行时环境。按照以下步骤操作：

- 1. 打开适用于 Java EE 开发的 Eclipse IDE，进入 Windows Preferences（Windows 偏好）。

- 2. 在出现的 Preferences 对话框中，展开 Server，并点击 Runtime Environments（运行时环境）。会出现一个 Server Environments 面板，你可以在其中管理适用于所有项目的应用程序服务器和 容器。

- 3. 点击 Add（添加）按钮打开 New Runtime Environment（新建运行时环境）对话框。

- 4. 展开 Apache 文件夹并选择 Apache Tomcat v8.0，确保勾选“Create a local server”（创建本地服务器）复框。然后点击 Next（下一步）按钮。

- 5. 在下一个屏幕上，点击 Browse（浏览）按钮并导航到你的 Tomcat 8.0 目录（例如 `C:\Program Files\Apache Software Foundation\Tomcat 8.0`）。然后点击 OK。

- 6. 在 JRE 列表中，选择你的本地 Java SE 8 JRE 安装。为服务器任意命名。你在本书中下载的 Eclipse 示例假设服务器名为 `Tomcat v8.0`，这是 Eclipse 的默认值。此时，你应该能看到类似图 2-10 的界面。

# 第 2 章 使用容器

![](img/4677f981a0e1067137bb55a122f8498d_71_0.png)

图 2-10

- 7. 点击 Finish（完成）按钮完成在 Eclipse 中添加本地 Tomcat 服务器，然后点击 OK 关闭偏好对话框。

你现在已准备好在 Eclipse 项目中使用 Tomcat 8.0 了。

需要注意的是，默认情况下，Eclipse 使用内置浏览器打开你的 Web 应用程序。你应该禁用此功能，并改用主流浏览器，例如 Google Chrome、Mozilla Firefox 或 Microsoft Internet Explorer。要更改此设置，进入 Window Browser 菜单，选择“Internal Web Browser”（内部浏览器）以外的选项。大多数情况下，“1 Default System Browser”（默认系统浏览器）就足够了，但你可以随时针对你的特定项目更改此设置。

# 在项目中使用 Tomcat 服务器

在 Eclipse 中创建新项目时，你必须在第一个对话框中选择将用于该项目的已配置的运行时服务器，如图 2-11 所示。然而，这仅配置了应用程序的库。它并没有为你选择 Tomcat 8.0 服务器。对于这一点，请遵循以下步骤：

- 1. 在创建或打开项目后，进入 Properties（属性），并在出现的 Properties 对话框左侧点击 Server 项。

- 2. 默认情况下，选中的服务器为“None”（无），因此你应该将其更改为“Tomcat v8.0 Server at localhost”，如图 2-12 所示。

# 从你的 IDE 调试 Tomcat

![](img/4677f981a0e1067137bb55a122f8498d_72_0.png)

图 2-11

![](img/4677f981a0e1067137bb55a122f8498d_72_1.png)

图 2-12

- 3. 点击 Apply（应用）保存更改。

- 4. 更改部署到 Tomcat 的应用程序上下文 URL（假设你未在创建项目时配置它）。在项目 Properties 对框中，你可以点击 Web Project Settings 菜单并更新“Context root”字段来更改它。

- 5. 点击 Apply（应用）保存更改后，点击 OK 取消对话框。

你可以从 wrox.com 代码下载站点下载 Sample-Debug-Eclipse 项目，以查看已配置在本地 Tomcat 8.0 应用程序服务器上运行的示例应用程序。（但是，你仍然需要在 Eclipse IDE 偏好中设置你的 Tomcat 8.0 安装。）

# 启动应用程序并命中断点

你现在已准备好在 Eclipse 中启动应用程序并调试。

- 1. 从 wrox.com 代码下载站点下载 Sample-Debug-Eclipse 项目，并使用适用于 Java 的 Eclipse IDE 打开它。

- 2. 确保你的服务器设置已正确配置为使用本地 Tomcat 8.0 应用程序服务器。你应该在尝试之前进行此检查。

- 3. 打开后，你应该看到类似图 2-10 的界面。![](img/4677f981a0e1067137bb55a122f8498d_73_0.png)

图 2-13

- 4. 点击 Eclipse 工具栏上的调试图标（已高亮显示）以调试模式启动你的应用程序。Eclipse 将启动配置的浏览器，你应该立即命中 `index.jsp` 中的断点。

- 5. 若要继续，点击继续。

> 警告 当你从 Eclipse 运行 Tomcat 时，Eclipse 会覆盖你创建的用于 JSP 编译的 `conf/setenv.bat` 或 `setenv.sh` 文件。如果你不想使用 Eclipse JDT 编译器编译 JSP，需要在文件中添加 CLASSPATH。参考 Tomcat 文档确定放置的位置。

> 注意 你可能注意到 Eclipse 中的 只有一个断点，而 IntelliJ 中有两个。Eclipse 调试器限制更多，因此无法在此第7 行设置断点。

### 总结

在本章中，你了解了 Java EE 应用程序服务器和容器，并探索了它们的多种实现。你在本地安装了 Tomcat 8.0，配置了 JSP 编译，从命令行启动它，并实验了部署和卸载应用程序。最后，你学习了如何使用 IntelliJ IDEA 和适用于 Java 的 Eclipse IDE 配置并运行以及调试 Tomcat 8.0。

在下一章中，你将创建 Servlet 并了解 Java EE Web 应用程序的工作原理。

# 3 编写你的第一个 Servlet

在本章中

- 创建 Servlet 类

- 为部署配置 Servlet

- 理解 `doGet()`、`doPost()` 及其他方法

- 使用参数和接受表单提交

- 使用初始化参数配置你的应用程序

- 从表单上传文件

- 使你的应用程序线程安全

wrox.com 本章代码下载

你可以通过 wrox.com/go/javaforapps 的 Download Code 选项卡找到本章的 wrox.com 代码。本章的代码分为以下几个主要示例：

- Hello-World Project

- Hello-User Project

- Customer-Support-v1

本章的新 Maven 依赖

在本章中，你将需要第一个 Maven 依赖，如下代码所示。在本书的剩余内容中，每个 Servlet 都将使用此依赖。

在上一章中，你已经熟悉了应用 Servlet 和 Web 容器，并学会了如何从 Java IDE 运行、部署和调试 Apache Tomcat 8.0。在本章中，你将通过探索 Servlet 的世界开始构建 Web 应用程序。在本章以及本书的其余部分，你将不断地更改和改进这些应用程序，将其部署到 Tomcat 中进行测试和调试。

## 创建 Servlet 类

在 Java 平台企业版（Java EE）中，*Servlet* 是用于接收并响应终端用户请求的对象。Java EE API 规范对 Servlet 的定义如下：

> Servlet 是一个运行在 Web 服务器中的小型 Java 程序。Servlet 接收并响应来自 Web 客户端的请求，通常通过 HTTP（超文本传输协议）。

```
http://docs.oracle.com/javaee7/api/javax/servlet/Servlet.html
```

Servlet 是任何应用程序中的核心类，它们是唯一执行响应工作或将该工作委托给应用程序某些部分的类。除非 `minor` 提前返回了请求（将在第 9 章中讨论），否则对你的应用程序的每个请求都会通过 Servlet。你运行应用程序的 Web 容器将有一个或多个内置的 Servlet。这些 Servlet 处理 Servlet 页面、显示目录列表（如果你启用了它们）、访问静态资源（如 HTML 页面和图形）。你暂时不需要担心这些 Servlet（在某些情况下，甚至永远不需要）。在本章中，你将学习如何编写和配置构成你应用程序的 Servlet。

每个 servlet 都实现了 *javax.servlet* 接口，但通常不是直接实现。Servlet 是一个简单的接口，包含初始化、销毁 Servlet 以及处理请求的方法。然而，对于任何类型的请求，都会调用 *service* 方法，即使它不是 HTTP 请求（理论上，假设你的 Web 容器支持此类请求）。在某个示例中，可能会向 Java EE 中添加新的 Servlet 以支持文件传输协议（FTP）。因此，有各种 Servlet 类可以供你扩展使用。作为 Java EE 7，目前支持的唯一 Servlet 协议是 HTTP。

## 扩展哪些类

在所有情况下，Servlet 都继承自 *javax.servlet.GenericServlet*。*GenericServlet* 仍然是一个与协议无关的 Servlet，带有一个抽象的 *service* 方法，但它包含了几个用于记录和获取有关应用程序和 Servlet 配置信息的方法（更多内容请参见“为部署配置 Servlet”章节）。

为了响应特定于 HTTP 请求，*javax.servlet.http.HttpServlet* 继承了 *GenericServlet* 并实现了 service 方法以仅接受 HTTP 请求。然后，它为对应每个 HTTP 方法类型的方法提供了空实现，如表 3-1 所示。

表 3-1：HTTP 方法类型的空实现

| 方法 | servlet 方法 | 目的 |
| :--- | :--- | :--- |



# HTTP 方法与 Servlet 对应关系

| HTTP 方法 | Servlet 方法 | 说明 |
| :--- | :--- | :--- |
| GET | `doGet()` | 获取指定 URL 处的资源 |
| HEAD | `doHead()` | 与 GET 相同，仅返回响应头 |
| POST | `doPost()` | 通常用于 Web 表单提交 |
| PUT | `doPut()` | 将提供的实体存储在 URL 中 |
| DELETE | `doDelete()` | 删除由 URL 标识的资源 |
| OPTIONS | `doOptions()` | 返回允许哪些 HTTP 方法 |
| TRACE | `doTrace()` | 用于诊断目的 |

> **注意**：大多数程序员熟悉 GET 和 POST 方法，并在大多数时间里使用它们。如果你不熟悉各种 HTTP 方法或想了解更多，现在是点击 `http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html` 查看 RFC-2616 关于方法定义的章节的时机了。

# 创建基础 Servlet

在书中没有例外，你的 Servlets 总是扩展 `HttpServlet`。它提供了你需要的所有工具来选择性地接受和响应不同类型的 HTTP 请求，它的方法接受 `javax.servlet.http.HttpServletRequest` 和 `javax.servlet.http.HttpServletResponse` 参数，这样你就可以轻松访问请求的 HTTP 特有属性。你应该从创建一个扩展 `HttpServlet` 的空 Servlet 开始：

```java
package com.;

import javax.servlet.http.HttpServlet;

public class HelloServlet extends HttpServlet {

}
```

> **注意**：为了编译此代码，你需要在类路径中拥有 Java EE Servlet 库。这就是本章第一页列出的 Maven 构件发挥的地方。在每一章中，你都需要列出的 Maven 构件来编译该章的示例。

这种形式的你的 Servlet 已经准备好接受任何 HTTP 请求并返回 `405 Method Not Allowed` 错误。这是你控制 Servlet 响应哪些 HTTP 方法：任何你没有重写的 HTTP Servlet 方法将返回 HTTP 状态 405。不处理任何请求的 Servlet 显然没有用处，因此重写 `doGet` 方法以增加对 HTTP 方法 GET 支持：

```java
package com.wrox;

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

现在你的 Servlet 准备好响应 GET 请求并在响应体中返回纯文本 "Hello, World!"。响应代码是直观的。接下来，Web 容器处理头部和正文。

# 使用初始化器和销毁器

在你启动第一个 Servlet 时，可能应该了解 `init` 和 `destroy` 方法。当 Web 容器启动 Servlet 时，它会调用 `init` 方法。这有时是在应用程序部署时，但总是如此。（你将在下一节中学习如何控制这一点。）稍后当 Web 容器关闭时，它会调用 `destroy` 方法。这些方法与构造函数和析构函数不同。通常，这些方法什么都不做，但你可以重写它们来执行某些操作：

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

> **注意**：你应该知道另一个 `init` 方法接收单个 `javax.servlet.ServletConfig` 参数。该方法在 Servlet 接口中指定，而 `GenericServlet` 负责实现该方法，然后调用无参数的重载。通过这种方式，你不需要在 `init` 实现中调用 `super.init(servletConfig)`。

尽管你可以重写原始方法，但如果你忘记调用它，Servlet 可能无法正确初始化。如果你需要访问 `ServletConfig`，调用 `getServletConfig` 方法要简单得多。你在本书的第一、二部分中学习 `ServletConfig` 类。

你可以通过这两个方法做很多事情。更重要的是，`init` 在 Servlet 构建之后、响应第一个请求之前被调用。与调用构造函数不同，`init` 时 Servlet 上已经设置了所有属性，让你能够访问 `ServletConfig` 和 `javax.servlet.ServletContext` 对象。（你将在“使用初始化参数配置应用程序”章节中学习如何操作。）例如，你可能使用此方法读取属性文件或使用 JDBC 连接到数据库。`init` 方法在 Servlet 启动时被调用。如果 Servlet 配置为 Web 应用程序部署时自动启动，那么它在部署时被调用；否则，它直到接收到第一个 Servlet 请求。`destroy` 在 Servlet 不再接受任何请求后立即被调用。这通常发生在 Web 应用程序停止或卸载，或者 Web 容器关闭时。因为它在部署或关闭时立即被调用，你不需要等待垃圾回收触发析构函数来清理资源，如：

![清理资源示意图](img/4677f981a0e1067137bb55a122f8498d_80_0.png)

清理临时文件或断开不再使用的数据库连接。如果你的应用程序已卸载但服务器仍在运行，这一点尤为重要，因为垃圾回收运行之前可能需要几分钟或几小时。如果你在 `finalizer` 方法而不是 `destroy` 方法中清理资源，可能会导致你的应用程序部分卸载或部署失败，你应该始终使用 `destroy` 方法来清理请求之间 Servlet 持有的资源。

上一个代码示例分别使用 `init` 和 `destroy` 方法来记录 Servlet 启动和停止的日志。当你运行下一节节中的应用程序时，这些日志消息将出现在 IDE 调试器的输出窗口中。在本章的后半部分，你将更好地使用这些方法。

# 为部署配置 Servlet

现在你已经创建了 Servlet，是时候将其部署了。虽然你有了一个可以响应 HTTP GET 请求并给出巧妙问候的类，但你还没有为 Web 容器编写随应用程序一起部署该 Servlet 的指令。第 1 章介绍了部署描述符 (`web.xml`) 和 Web 应用程序的结构，在第 2 章中你学习了如何使用 IDE 部署和调试应用程序。在本节中，你将在 `WEB-INF` 目录下创建 `web.xml` 文件并创建用于部署的 Servlet。然后你使用 IDE 部署应用程序并在浏览器中查看它。最后，你在代码中设置断点并检查某些方法何时被调用。

## 将 Servlet 添加到描述符中

正如你所学到的，部署描述符指示 Web 容器应如何部署应用程序。具体来说，它定义了所有随应用程序一起部署的监听器、Servlet 和过滤器，以及应用程序部署时应使用的设置。首先，看一个（大部分）空的 `web.xml` 文件：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
     http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
     version="3.1">

<display-name>Hello World Application</display-name>

</web-app>
```

> **警告**：如果你在之前的 Java EE 版本中处理过部署描述符，这可能对你来说有些陌生。这是因为自 Java EE 6 以来，web 等配置文件的 XML 架构 URI 发生了变化。你必须使用新的 URI 以使你的应用程序符合 Java EE 7 标准。

在上例中，`<display-name>` 标签向应用程序服务器指示应用程序的名称。在列出所有已安装应用程序的 Tomcat 管理界面上，`<display-name>` 标签之间的名称将出现在你的应用程序旁边。起始 `<web-app>` 标签中的 `version` 属性指示应用程序是为哪个版本的 Servlet 编写的——在这种情况下，版本为 3.1。

现在你需要告诉 Web 容器创建你之前编写的 Servlet 实例，因此你必须在 `<web-app>` 开始标签和结束标签之间向描述符文件添加一个 Servlet：

```xml
<servlet>
    <servlet-name>helloServlet</servlet-name>
    <servlet-class>com.wrox.HelloServlet</servlet-class>
</servlet>
```

在本章较早之前，你学习了 Servlet 的 `init` 方法以及它通常在何时被调用。在本例中，当 Web 应用程序启动后第一个请求 Servlet 时，`init` 方法会被调用。通常情况下，这对于大多数用户来说足够了。然而，如果 `init` 方法执行了某些操作，Servlet 的启动可能会变成一个耗时的过程，这可能导致对 Servlet 的第一次请求花费几秒甚至几分钟！显然，这并不是理想的。对 Servlet 配置进行简单的微调，可以让 Servlet 在 Web 应用程序启动时立即启动：

```xml
<servlet>
    <servlet-name>helloServlet</servlet-name>
    <servlet-class>com.wrox.HelloServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
</servlet>
```

`<load-on-startup>` 标签指示 Web 容器在 Web 应用程序启动后立即启动 Servlet。如果多个 Servlet 包含此标签，它们将按照标签内值的顺序启动，较小的值靠前，较大的数字靠后。如果两个或多个 Servlet 在 `<load-on-startup>` 标签中有相同的值，则冲突的 Servlet 将按照它们在描述符文件中出现的顺序启动，仍然是在数字较小的 Servlet 之后、其他数字较大的 Servlet 之前启动。

## 将 Servlet 映射到 URL

你已经指示应用程序服务器启动 Servlet，但还没有告诉它 Servlet 应该响应哪个 URL 请求。这是一个简单的配置：

```xml
<servlet-mapping>
    <servlet-name>helloServlet</servlet-name>
    <url-pattern>/greeting</url-pattern>
</servlet-mapping>
```

通过此配置，所有对应用程序相对 URL `/greeting` 的请求都由 `helloServlet` 处理。（注意 `<servlet>` 和 `<servlet-mapping>` 标签内的 `<servlet-name>` 标签是匹配的。这就是 Web 容器关联两者的方式。）如果应用程序部署在 `http://www.example.net`，则 Servlet 响应流向 URL `http://www.example.net/greeting` 的请求。当然，你不局限于这一个映射。你可以将多个 URL 映射到同一个 Servlet：

```xml
<servlet-mapping>
    <servlet-name>helloServlet</servlet-name>
    <url-pattern>/greeting</url-pattern>
</servlet-mapping>
<servlet-mapping>
    <servlet-name>helloServlet</servlet-name>
    <url-pattern>/salutation</url-pattern>
</servlet-mapping>
<servlet-mapping>
    <servlet-name>helloServlet</servlet-name>
    <url-pattern>/up</url-pattern>
</servlet-mapping>
```

# 运行并调试你的 Servlet

保存后，编译你的应用程序，并检查你已设置好 IDE 配置以在 Tomcat 8.0 实例中运行项目。（如果你忘记了如何操作，请参阅第 2 章）。应用程序部署到 `/hello-world`。你也可以从 wrox.com 代码下载网站下载 Hello-World IDE 项目——它已经配置好正确部署。完成后，按照以下步骤操作：

1. 点击 IDE 中的调试图标以调试模式启动 Web 容器。你的 IDE 在 Web 容器启动后会将你的应用程序部署到其中。
2. 打开网页浏览器并导航到 `http://localhost:8080/hello-world/greeting`。你现在应该能看到图 3-1 中的场景。

![图 3-1](img/4677f981a0e1067137bb55a122f8498d_84_0.png)

3. 理解发生什么的好方法是在 `HelloServlet` 中设置一些断点并再次运行此实验。你应该停止调试器（这将关闭 Tomcat），这样你也可以在初始化器中命中断点。在你的 Servlet 的 `doGet`、`init` 和 `destroy` 方法中添加断点；然后重启你的调试器。当 Tomcat 启动并运行你的应用程序后，你会发现你没有命中任何断点（因为部署描述符中不存在 `<load-on-startup>` 标签）。
4. 在浏览器中刷新欢迎页面，你应该会在 IDE 的 `init` 方法中命中断点。这意味着 Tomcat 激活了你 Servlet 的即时初始化：它在第一个请求到来之前一直没有被初始化。
5. 就像该方法完成需要很长时间一样，来自浏览器的请求将保持激活状态，直到你控制调试器，现在就执行操作吧。你应该立即命中 `doGet` 方法中的断点。Servlet 处理了请求，但你的浏览器在等待响应。
6. 第二次继续调试器，现在响应将发送到你的浏览器。

此时，你可以随心所欲点击浏览器上的刷新按钮，你将反复命中断点，直到操作销毁了 Servlet（例如 Tomcat 关闭）然后重新启动。在此之前，你还没有命中 `destroy` 方法中的断点。遗憾的是，你现在想这样做，但如果你从 IDE 停止 Tomcat，调试器会在命中断点之前停止，因此你需要从命令行停止 Tomcat。请按照以下步骤操作：

1. 打开命令行并将当前目录切换到 Tomcat 目录（在 Windows 机器上为 `C:\Program Files\Apache Software Foundation\Tomcat 8.0`）。
2. 输入命令 `bin\shutdown.bat`（如果你不是 Windows 系统，请输入 `bin/shutdown.sh`）并按回车。
3. 在你的 IDE 窗口中，立即命中 `destroy` 方法中的断点。在你继续调试器之前，Tomcat 不会完全关闭。

如所述，你可以更改 Servlet 的配置，使其在应用程序启动时进行初始化。现在尝试一下。

1. 更新部署描述符中的 Servlet 声明，添加以下示例中的 `<load-on-startup>` 标签：

```xml
<servlet>
    <servlet-name>helloServlet</servlet-name>
    <servlet-class>com.wrox.HelloServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
</servlet>
```

2. 在 Servlet 中保留断点的情况下，启动调试器。再次，你在向 Servlet 发送第一个请求之前就会立即命中 `init` 方法中的断点。
3. 继续调试器并刷新浏览器。现在你应该只会在 `doGet` 方法中命中断点；Servlet 在应用程序启动时已经初始化，不需要再次初始化。



现在你已经创建了第一个 Servlet 并熟悉了 Servlet 的生命周期，鼓励你对 Servlet 的不同方法调用以及 `doGet` 方法中的请求和响应参数进行实验。在下一节中，你将进一步探索 `doGet`、`doPost` 和其他方法，以更好地理解 `HttpServletRequest` 和 `HttpServletResponse`。

> 注意：你应该查阅（并收藏）位于 `http://docs.oracle.com/javaee/7/api/` 的 Java EE 7 API 文档及其用途信息。

# 理解 GET()、POST() 以及其他方法

在上一节中，你学习了 `doGet` 方法以及映射到各种 HTTP 方法的其他方法。但在这些方法中你到底可以做什么？更重要的是，在这些方法中你应该做什么？这些问题的简短答案分别是“几乎可以做任何事”和“不多”。本节将探索你可以做的一些事情以及如何实现它们。

# 在 service 方法执行期间应该发生什么？

正如你之前学到的，Servlet 类的 `service` 方法处理所有传入的请求。最终，它必须根据使用的协议解析并处理传入请求中的数据，并向客户端返回符合协议的响应。如果 `service` 方法在没有向套字发送数据的情况下返回，客户端可能会观察到网络错误，例如“连接重置”。在 HTTP 协议中，`service` 方法应该理解客户端发送的 Header 和参数，并返回一个适当的 HTTP 响应，其至少包含最小的 HTTP Header（即使响应体为空）。实际上，这种实现是复杂的（涉及许多步骤），并且可能因 Web 容器而异。

扩展 `HttpServlet` 的妙之处在于你不需要担心这些细节。尽管事实是 `service` 方法在响应请求之前做了很多工作，但用户需要做的很少。实际上，在你在最后两个环节中使用的 Hello-World 项目中，如果你删除 `doGet` 方法中的单行代码并运行应用程序，一切仍然正常！一个结构良好且带有内容的 `HttpServlet` 会返回给客户端。唯一的要求是重写 `doGet` 方法（或 `doPost` 或任何你想支持的方法）；你不需要在其中放入任何内容。但这真的有用吗？

答案是“完全没用”。这是因为仅仅你可以返回空响应并不意味着你应该这样做。这就是 `HttpServletRequest` 和 `HttpServletResponse` 发挥作用的地方。在 `HttpServlet` 定义的各种方法中，你可以读取从客户端传递的参数、接受表单上传的文件、读取请求体包含的原始数据（用于处理 PUT 请求或接受 JSON 请求体）、读取请求 Header 并操作响应 Header，并将响应内容写回客户端。这些是在处理请求时可以做的许多事情之一，实际上你通常会做其中一项或多项。

# 使用 HttpServletRequest

`HttpServletRequest` 接口是 `ServletRequest` 的扩展，提供了关于接收请求的额外 HTTP 协议特定信息。它指定了数十种方法，让你获取有关 HTTP 请求的详细信息。它还允许设置属性（来自请求参数）。

> 注意：你将在下一章学习请求属性和身份验证详情检查。本书没有涵盖每个方法的细节（对此你可以查阅 API 文档），但涵盖了最重要的功能。

# 获取请求参数

`HttpServletRequest` 可能最重要的功能之一（也是你将在下一节中通过示例探索的功能）是获取客户端传递的请求参数。请求参数有两种形式：通过查询参数（也称为 URI 参数），或者在 `application/x-www-form-urlencoded` 或 `multipart/form-encoded` 请求体中（通常称为 post 变量或表单）。查询参数支持所有请求方法，并包含在 HTTP 请求的第一行中，如下所示：

```
GET /index.jsp?productID=9781118654644&category=Books HTTP/1.1
```

> 注意：技术上说，HTTP 协议的 RFC 规范并没有禁止任何 HTTP 方法使用查询参数。然而，许多服务器会忽略传递给 DELETE、TRACE 和 OPTIONS 的查询参数，查询参数在此类请求中的用性尚存疑。因此，最好不要对这些类型的请求依赖查询参数。本书没有涵盖 HTTP 协议的所有规则和错综性。这项练习留给你自己完成。

在此示例中，请求中包含两个查询参数：`productID`（其值为该书的 ISBN）和 `category`（其值为 `Books`）。这些相同的参数也可以作为 post 变量传递在请求体中。Post 变量正如其名，只能包含在 POST 请求中。考虑以下示例：

```
POST /index.jsp?returnTo=Page HTTP/1.1
Host: example.com
Content-Length: 48
Content-Type: application/x-www-form-urlencoded

addToCart&productid=9781118654644&category=Books
```

## 理解 doGet()、doPost() 以及方法

此 POST 请求包含 post 变量（指示网站将此书加入购物车）和查询参数（指示网站在任务完成后返回到产品页面）。尽管这两种参数的递送方式有所不同，但它们在本质上是相同的，并且传递了相同的信息。Servlet API 并不区分这两种类型的参数。在请求上调用任何与参数相关的 API，无论它们是作为查询参数还是 post 变量传递的，都会返回这些参数。

`getParameter` 方法为参数返回一个单一值。如果该参数有多个值，`getParameter` 会返回第一个值，而 `getParameterValues` 则返回该参数的多个值数组。如果参数只有一个值，该方法将返回一个包含该元素的数组。`getParameterMap` 返回一个 `java.util.Map<String, String[]>`，其中包含了所有参数名称及其映射的值；而 `getParameterNames` 返回所有可用参数名称的枚举；这两者对于遍历请求参数都非常有用。

> 警告：当你第一次在请求对象上调用 `getParameter`、`getParameterNames` 或 `getParameterValues` 时，容器会确定请求是否包含 post 变量，并可能通过获取请求的 `InputStream` 来读取和解析 post 变量。请求的 `InputStream` 只能读取一次。如果你在包含 post 变量的请求上调用 `getInputStream` 或 `getReader`，随后再次尝试获取该请求中的参数，将导致 `IllegalStateException`。同样，如果你在包含 post 变量的请求上获取了参数，随后调用 `getInputStream` 或 `getReader`，则对 `getInputStream` 或 `getReader` 的调用将失败并抛出 `IllegalStateException`。简单来说，每当你预计请求可能包含 post 变量时，最好只使用参数方法，并不要使用 `getInputStream` 和 `getReader`。

## 获取请求内容信息

有多种方法可以帮助确定 HTTP 请求内容的类型、长度和编码。`getContentType` 返回请求的 MIME 内容类型，例如 `application/x-www-form-urlencoded`、`application/json`、`text/plain` 或 `application/` 等名称。MIME 内容类型描述了其包含数据的某种类型。例如，ZIP 压缩包的 MIME 类型为 `application/zip`，表示它们包含 ZIP 存档数据。

`getContentLength` 和 `getContentLengthLong` 都返回请求体（内容）的字节数，后者方法适用于内容可能超过 2GB 的请求（虽然未设置，但这是可能的）。每当请求包含字符类型内容时（`text/plain`、`application/json` 和 `application/x-www-form-urlencoded` 都是字符型 MIME 类型的示例），`getCharacterEncoding` 方法会返回请求的字符编码（如 `UTF-8` 或 `ISO-8859-1`）。尽管这些方法在很多情况下派用场，但如果你使用参数方法从请求体获取 post 变量，那么它们中的任何一个都不是必须的。

> 注意：Java EE 7 中的 Servlet 3.1 规范是第一个支持 `getContentLengthLong` 方法的版本。在此版本之前，对于大于 2,147,483,647 字节的请求，你必须调用 `getHeader("Content-Length")` 并将返回的 String 转换为 long。

## 读取请求内容

可以使用 `getInputStream`（返回一个 `javax.servlet.ServletInputStream`）和 `getReader`（返回一个 `java.io.BufferedReader`）方法来读取正在读取的请求内容。哪一个最合适取决于读取请求的上下文。如果预计内容是字符编码的（如 `UTF-8` 或 `ISO-8859-1` 文本），使用 `BufferedReader` 通常是最简单的方法，因为它允许你读取 `char`。然而，如果请求数据在本质上是二进制的，你必须使用 `ServletInputStream` 以字节格式访问请求。你不应该在同一个请求上同时使用它们。在调用其中任何一个后，调用另一个将导致以 `IllegalStateException` 失败。请记住上述的警告，不要在带有 post 的请求上使用这些方法。

## 获取请求特征（如 URL、URI 和 Header）

你可能需要了解的许多请求特征，例如发送请求时使用的 URL 或 URI。这些可以很容易从请求对象中获取：

- `getRequestURL`：返回客户端发送请求时使用的 URL，包括协议（`http` 或 `https`）、服务器名称、端口号和服务器路径，但不包括查询字符串。因此，在对 `http://www.example.org/application/index.jsp?category=Books` 的请求中，`getRequestURL` 返回 `http://www.example.org/application/index.jsp`。

- `getRequestURI`：这与 `getRequestURL` 稍不同，因为它只返回请求的服务器路径；使用上例，将返回 `/application/index.jsp`。

- `getServletPath`：与 `getRequestURI` 类似，它返回的 URL 更少。如果请求是 `/hello-world/greeting?foo=world`，应用部署在 `/hello-world`（在 Tomcat 上），且 servlet 映射为 `/greeting`、`/salutation` 和 `/wazzup`，`getServletPath` 仅返回用于匹配 servlet 映射的 URL 部分：`/greeting`。

- `getHeader`：返回给定名称的 header 的值。header 的名称不需要与传递给方法的字符串完全匹配，因此 `getHeader("Content-type")` 可以匹配 `Content-Type` 头部。如果存在多个同名的 header，它仅返回第一个。在这种情况下，你可能想使用 `getHeaders` 方法来返回所有值的枚举。

- `getHeaderNames`：返回请求中所有 header 名称的枚举——这是遍历可用 header 的极佳方法。

- `getIntHeader`：如果你知道某个 header 始终是数字，可以调用此方法返回已转换为数字的值。如果 header 无法转换为整数，将抛出 `NumberFormatException`。

- `getDateHeader`：你可以调用此方法返回代表有效时间戳的毫秒值。如果 header 值未被识别为日期，将抛出 `IllegalArgumentException`。

## Session 和 Cookies

`getSession` 和 `getCookies` 方法仅在此处说明本章不涵盖它们，但它们是 `HttpServlet` 领域的重要部分。你可以在第 5 章学习更多关于它们的信息。

# 使用 HttpServletResponse

`HttpServletResponse` 接口扩展了 `ServletResponse` 并提供了请求的 HTTP 特有属性，`HttpServletResponse` 接口提供了用于设置响应头、写入正文、重定向请求、设置 HTTP 状态码以及发送 cookie。该对象的常用功能在此处介绍。

## 写入响应体

对响应对象常用的操作，以及你对响应对象执行的操作，都是向响应体写入内容。这可能是显示在浏览器中的 HTML、浏览器检索的图像或正在下载的文件内容。可以是纯文本或二进制数据。它可能只有几字节，也可能是几个 GB。

`getOutputStream` 方法（返回一个 `javax.servlet.ServletOutputStream`）和 `getWriter` 方法允许你向响应写入数据。类似于 `HttpServletRequest` 中的对应方法，你可能希望使用 `PrintWriter` 向客户端返回 HTML 或其他字符编码的文本，因为它便于向响应写入编码后的 String 和 char。对于发送二进制数据，你必须使用 `getOutputStream` 来发送响应体。此外，你不应该在同一个响应中同时使用 `getOutputStream` 和 `getWriter`。在调用其中一个后，调用另一个将导致 `IllegalStateException` 失败。

当你写入响应时，有必要设置内容类型或编码。你可以通过 `setContentType` 和 `setCharacterEncoding` 来实现这一点。你可以多次调用这些方法，最后一次调用是有效的。然而，如果你计划结合 `getWriter` 使用 `setContentType` 和 `setCharacterEncoding`，则你必须在调用 `getWriter` 之前调用这两个方法，以确保返回的 writer 配置了正确的编码。在调用 `getWriter` 之后进行的调用将被忽略。如果你在调用 `getWriter` 之前没有调用 `setContentType` 和 `setCharacterEncoding`，返回的 writer 将使用客户端的默认编码。

你还可以使用 `setContentLength` 和 `setContentLengthLong` 方法。在几乎所有情况下，都**不**需要调用这些方法。Web 容器在完成你的响应时会设置 `Content-Length` 头部，让它来完成操作是最安全的。

> 注意：Java EE 7 中的 Servlet 3.1 规范是第一个支持 `setContentLengthLong` 方法的版本。在此之前，对于响应大小可能超过 2,147,483,647 字节的响应，你必须调用 `setHeader("Content-Length", Long.toString(length))`。

## 设置头部和其他响应属性

作为 `HttpServletRequest` 中方法的对应方法，你可以调用 `setHeader`、`addHeader` 和 `setDateHeader` 来设置你需要的几乎任何头部值。如果现有响应中已经包含你设置的名称的头部，则该头部的值将被覆盖。为了避免这种情况，你可以使用 `addHeader`、`addHeader` 或 `addDateHeader` 来为该头部添加额外值。你还可以调用 `getHeader`、`getHeaders` 和 `containsHeader` 来检查响应中已经设置了哪些头部。

此外，你还可以使用：

- `setStatus`：设置 HTTP 响应状态码
- `getStatus`：确定响应的当前状态
- `sendError`：设置状态码，指定要写入响应数据的可选错误消息，直接让 Web 容器为客户端提供错误页面，并清空缓冲区
- `sendRedirect`：将客户端重定向到不同的 URL

本节涵盖了在 Servlet 中处理 HTTP 请求时可以执行的大多数操作，并说明了重要的细节和注意事项。在之前的章节中，你已经使用 Hello-World 项目来演示 Servlet 的工作。在接下来的章节中，你将进入一个稍微复杂一点示例。

## 使用参数和接受表单提交

在本节中，你将通过接受参数和表单提交让你的 Hello-World 项目变得更具动态性。你还将探索注解配置，并暂时放弃使用部署描述符。对于本节中的示例，你可以跟随完成的 Hello-User 项目进行操作，也可以在涵盖相关内容时直接将更改整合到现有的项目中。

项目发生了几处更改。你首先应该注意到 `doGet` 方法现在变得复杂得多：



# 第 3 章 编写你的第一个 Servlet

```java
private static final String DEFAULT_USER = "Guest";

@Override
protected void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    String user = request.getParameter("user");
    if (user == null) {
        user = HelloServlet.DEFAULT_USER;
    }

    response.setContentType("text/html");
    response.setCharacterEncoding("UTF-8");

    PrintWriter writer = response.getWriter();
    writer.append("<!DOCTYPE html>\r\n");
    writer.append("<html>\r\n");
    writer.append("<head>\r\n");
    writer.append("<title>Hello User Application</title>\r\n");
    writer.append("</head>\r\n");
    writer.append("<body>\r\n");
    writer.append("Hello, ").append(user).append("!<br/><br><br/>\r\n");
    writer.append("<form action=\"greeting\" method=\"POST\">\r\n");
    writer.append("Enter your name:<br/>\r\n");
    writer.append("<input type=\"text\" name=\"user\"/><br/>\r\n");
    writer.append("<input type=\"submit\" value=\"Submit\"/>\r\n");
    writer.append("</form>\r\n");
    writer.append("</body>\r\n");
    writer.append("</html>\r\n");
}
```

加粗的代码是新增的。它现在执行的逻辑很少：

- 它测试请求中是否包含 `user` 参数，如果没有，则使用 `DEFAULT_USER` 常量。
- 它将响应的内容类型设置为 `text/html`，并将字符编码设置为 `UTF-8`。
- 它从响应中获取 `PrintWriter`，并输出标准的 HTML5（注意针对特定用户的问候）以及一个用于提供用户名的表单。

你可能会奇怪，当表单方法设置为 `POST` 时，`doGet` 是如何接收表单提交的。以下是新的实现：

```java
@Override
protected void doPost(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
    this.doGet(request, response);
}
```

此实现简单地委托给 `doGet` 方法。查询参数或名为 `user` 的表单字段都可以触发问候。

你最后应该注意到 Servlet 声明下方的注解：

```java
@WebServlet(
    name = "HelloServlet",
    urlPatterns = {"/greeting", "/wazzup"},
    loadOnStartup = 1
)
public class HelloServlet extends HttpServlet {
}
```

> 注意：你会注意到最新的 Servlet 代码示例省略了类导入。随着代码变得越来越复杂，导入语句可能会占据几十行代码。这在书中高效地打印出来是不现实的。一个好的 IDE（如你阅读本书时使用的 IDE）可以识别类名并为你建议导入语句，从而减轻你的繁琐工作。除少数例外外，书中其余示例都将省略导入和包语句。除非另有说明，否则新类将位于 `com.wrox` 包中。

## 列表 3-1: MultiValueParameterServlet.java

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
        writer.append("<!DOCTYPE html>\n");
        writer.append("<head>\n");
        writer.append("<title>Hello User Application</title>\n");
        writer.append("<body>\n");
        writer.append("<form action=\"checkboxes\" method=\"POST\">\n");
        writer.append("Choose the fruits to eat:<br>\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Banana\"/>\r\n");
        writer.append("Banana\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Apple\"/>\r\n");
        writer.append("Apple\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Orange\"/>\r\n");
        writer.append("Orange\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Guava\"/>\r\n");
        writer.append("Guava\r\n");
        writer.append("<input type=\"checkbox\" name=\"fruit\" value=\"Kiwi\"/>\r\n");
        writer.append("Kiwi\r\n");
        writer.append("<input type=\"submit\" value=\"Submit\"/>\r\n");
        writer.append("</form>\n");
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
        writer.append("<!DOCTYPE html>\n");
        writer.append("<head>\n");
        writer.append("<title>Hello User Application</title>\n");
        writer.append("</head>\n");
        writer.append("<body>\r\n");
        writer.append("<h2>Your Selections</h2>\r\n");

        if (fruits == null) {
            writer.append(" You did not select any fruits.\r\n");
        } else {
            writer.append("<ul>\r\n");
            for (String fruit : fruits) {
                writer.append("<li>").append(fruit).append("</li>\r\n");
            }
            writer.append("</ul>\r\n");
        }
        writer.append("</body>\r\n");
        writer.append("</html>\r\n");
    }
}
```

这向你展示了在 Servlet 方法中请求参数的各种方式。你已经探索了查询参数和表单变量，以及单值和多值参数。在下一节中，你将学习如何使用输入参数来配置你的应用程序。

## 使用输入参数配置你的应用程序

在编写 Web 应用程序时，不可避免地需要为配置应用程序及其内部的 Servlet 提供方法。使用许多技术有很多种实现这一目标的方法，你将在书中探索其中几种。最简单的应用程序配置方法是通过可以通过上下文初始化参数（通常缩短为 init 参数）和 Servlet 参数进行，这将在本节中进行介绍。这些参数可以用于许多用途，从定义与关系型数据库通信的连接信息，到提供用于发送订单警报的电子邮件地址。它们在应用程序启动时定义，在不重启应用程序的情况下无法更改。

### 使用上下文初始化参数

稍早时候，你清空了部署描述符，并在实际类上替换了 Servlet 声明和映射注解。虽然这是（在 Java EE 6 的 Servlet 3.0 规范中添加）你无法通过部署描述符执行的操作，但仍有一些事情需要部署描述符。上下文初始化参数就是其中一个特性。你可以在 `web.xml` 文件中使用 `<context-param>` 标签声明上下文初始化参数。以下代码显示了添加到部署描述符中的两个上下文初始化参数：

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

这创建了两个上下文初始化参数：`settingOne` 的值为 `foo`，`settingTwo` 的值为 `bar`。你可以轻松地从 Servlet 代码中使用并设置这些值。`ContextParameterServlet` 演示了这一点：

```java
@WebServlet(
    name = "contextParameterServlet",
    urlPatterns = {"/contextParameters"}
)
public class ContextParameterServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        ServletContext c = this.getServletContext();
        PrintWriter writer = response.getWriter();
        writer.append("settingOne: ").append(c.getInitParameter("settingOne"));
        writer.append(", settingTwo: ").append(c.getInitParameter("settingTwo"));
    }
}
```

然而，这样做的缺点是，在不重新编译应用程序的情况下，无法更改 Servlet 初始化参数的值。当然，可能某些设置是你不希望在不重新编译应用程序的情况下更改的，但既然如此，为什么不把它们设为类常量呢？将 Servlet 初始化参数放在部署描述符中的优势是，服务器管理员只需要更改几行 XML 并重启已部署的应用程序即可更改效果。如果此类设置包含关系型数据库的信息，你最不想做的就是通过重新编译应用程序来更改数据库服务器的 IP 地址。

下一节将介绍 Servlet 3.0 规范中为 `HttpServletRequest` 添加的一个新功能，以及一个你将在书籍剩余部分中不断改进的示例应用程序。

## @CONFIG 的缺点

如前所述，在 Web 应用程序中使用基于注解的配置（通常称为 @Config）既有优点也有缺点。主要优点是消除了 XML，并可以使用直接、简洁的注解语言来配置你的应用程序。然而，这种方法也有许多缺点。

其中一个例子是无法为单个 Servlet 类创建多个实例。你在本章的前面的部分已经看到这种模式是如何使用的。由于注解的限制，无法仅使用 XML 配置或编程 Java 配置来实现任何更改。

在第 9 章中，你将学习过滤器以及为什么正确构造过滤执行顺序很重要。当使用 XML 配置或编程 Java 配置声明过滤器时，过滤器会按照特定的顺序执行。然而，如果你使用 `@javax.servlet.annotation.WebFilter` 声明过滤器，则无法让按特定顺序执行（这似乎是 Servlet 3.0 和 3.1 规范中的一个明显疏忽）。除非你的应用程序只有一个过滤器，否则 `@WebFilter` 是没用的。

还有许多较小的事情仍需要 Servlet 部署描述符来实现，例如定义错误处理页面、配置 JSP 设置以及提供欢迎页面列表。坦率地说，你可以混合使用 XML、注解和编程 Java 配置，因此你可以在最方便时使用每种方法。在整本书中，你将使用这三种技术。

## 从表单上传文件

向 EE Servlets 上传文件几乎总是可行的，但过去通常需要大量的努力。这项任务非常复杂，以至于 Apache Commons 专门创建了一个整个项目——Commons FileUpload 来处理这些工作。因此，看似是接受文件上传提交的简单需求，实际上需要在你的应用程序中引入第三方依赖。EE 6 中的 Servlet 3.0 通过为 Servlet 引入多部分配置选项以及 `HttpServletRequest` 中的 `getPart` 和 `getParts` 方法，改变了一切。

### 介绍客户支持项目

你可以将此功能作为你的交互示例的起点：客户支持项目。虽然每个章节都有较小的示例来演示特定的点，但每个章节还包含一个客户支持项目的新版本，结合了在该章中学到的新知识。

该设置是一个为跨国小部件公司全球客户服务的全球网站。你的产品经理被赋予任务为公司网站添加一个交互客户支持应用程序。它应该允许用户发布问题或支持工单，并允许员工响应这些查询。支持工单和注释都应该包含文件附件。对于紧急事项，客户应该进入与专门的支持代表的聊天窗口。而且，由于是跨国小部件公司，整个应用程序应该能够根据公司决定翻译的任何语言进行本地化。这要求并不高吧，对吧？

噢，是的。它还需要非常安全。

显然你不能一次性完成所有任务，特别是考虑到你目前学到的很少，因此每一章你要么处理一个小功能，要么改进上一章中编写的代码。在本章的剩余部分，请参考 Customer Support-v1 项目。该项目目前相对简单。它由三个页面组成：工单列表、创建一个工单的视图页面。它还具有下载工单的能力。

```java
@WebServlet(
    name = "TicketServlet",
    urlPatterns = {"/tickets"},
    initParams = {
        @WebInitParam(name = "maxFileSize", value = "2097152"),
        @WebInitParam(name = "maxRequestSize", value = "4194304")
    },
    multipartConfig = @MultipartConfig(
        maxFileSize = 2097152,
        maxRequestSize = 4194304
    )
)
public class TicketServlet extends HttpServlet {
    private volatile int TICKET_ID_SEQUENCE = 1;

    private Map<Integer, Ticket> ticketDatabase = new LinkedHashMap<>();
}
```



```java
case "download":
    this.downloadAttachment(request, response);
    break;
case "download":
default:
    this.listTickets(response);
    break;
}
```

在 `doGet` 方法中要做的事情太多了；以前，你可能有一个跨越数百行的方法。在这个示例中，`doGet` 方法使用了原始的动作/执行器模式：通过请求参数传递动作，`doGet` 方法根据该动作将请求发送给执行器（方法）。`doPost` 方法类似：

```java
@Override
void doPost(HttpServletRequest request, HttpServletResponse response)
{
    String action = request.getParameter("action");
    if (action == null) {
        action = "list";
    }
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

你可以在 `doPost` 中做的一件事是使用重定向方法。你在几个章节之前学习过这个方法。在这种情况下，如果客户端执行的 POST 请求缺少或无效的动作，其浏览器将重定向到列出票据的页面。该类中的大多数方法并没有什么新意：参数的使用、使用 `PrintWriter` 向客户端浏览器输出内容等。并不是所有的代码都能放入书中，但确实用到了一些功能，是你应该查看的。接下来的示例是 `downloadAttachment` 的片段，仅包含你以前没见过的部分：

```java
response.setHeader("Content-Disposition",
    "attachment; filename=" + attachment.getName());
response.setContentType("application/octet-stream");
```

```java
ServletOutputStream stream = response.getOutputStream();
stream.write(attachment.getContent());
```

这段简单的代码负责处理文件下载到客户端浏览器的过程。如设置的 `Content-Disposition` 头部，它会强制浏览器询问客户端保存或下载文件，而不是直接内联打开文件。浏览器内容是一种通用的、二进制内容类型，它可以防止数据被应用任何类型的字符编码。（一个正确的实现应该知道附件的实际 MIME 类型并使用该值，但这超出了本书的讨论范围。）最后，使用 `ServletOutputStream` 将文件内容写入响应中。这可能不是写入文件内容最高效的方法，因为大文件可能会导致响应出现内存问题。如果你预计会有大文件下载，你不应该将文件存储在内存中，而应该将字节从文件的 `InputStream` 复制到 `ResponseOutputStream`。你应该频繁刷新 `ResponseStream`，以便字节能够持续流回用户的浏览器，而不是缓冲在内存中。改进这段代码的代价由你决定。

# 接受文件上传

最后，看一眼 `createTicket` 方法以及它所使用的列表 3-2 中的 `processAttachment` 方法。这些方法特别重要，因为它们处理文件上传——这是你还没有做过的事情。`processAttachment` 方法从多部分请求中获取 `InputStream`，并将其复制到 `Attachment` 对象中。它使用了 Servlet 3.1 添加的 `getSubmittedFileName` 方法来识别上传前的原始文件名。`createTicket` 方法使用此方法和其他参数来填充 `Ticket` 对象并将其添加到数据库中。

+ 列表 3-2：HttpServlet.java 的部分

```java
private void createTicket(HttpRequest request,
                                HttpServletResponse response)
    throws SQLException
{
    Ticket ticket = new Ticket();
    ticket.setCustomerName(request.getParameter("customerName"));
    ticket.setSubject(request.getParameter("subject"));
    ticket.setBody(request.getParameter("body"));

    Part filePart = request.get("file");
    if(filePart != null)
    {
        Attachment attachment = this.processAttachment(filePart);
        if (attachment != null)
            ticket.addAttachment(attachment);
    }

    int id;
    synchronized(this)
    {
        id = TICKET_ID_SEQUENCE++;
        ticketDatabase.put(id, ticket);
    }

    response.sendRedirect("tickets?ticketId=" + id);
}

private Attachment processAttachment(Part filePart)
    throws IOException
{
    InputStream inputStream = filePart.getInputStream();
    ByteArrayOutputStream outputStream = new ByteArrayOutputStream();
```

```java
int read;
final byte[] bytes = new byte[1024];
```

```java
while ((read = inputStream.read(bytes)) != -1)
{
    outputStream.write(bytes, 0, read);
}
```

```java
Attachment attachment = new Attachment();
attachment.setName(filePart.getSubmittedFileName());
attachment.setContents(outputStream.toByteArray());
```

```java
return attachment;
```

你在 `createTicket` 方法中可以看到的一点是使用了同步块来锁定票据数据库。你将在本章的最后部分进一步探讨这一点。

# 使你的应用程序线程安全

Web 应用程序从本质上说是多线程的。在任何时刻，可能有零、一个或一千个人同时使用你的 Web 应用程序，你必须对此进行考虑。由于这个问题有很多不同的方面，已经有很多书籍是关于多线程和并发管理的了。显然，本书无法涵盖所有重要的多线程讨论。

# 理解请求、线程和执行

在请求和线程的主题上，在某些情况下，线程可能会贯穿请求的寿命。Java EE 3.0 引入了异步上下文的概念。本质上，当你的 Servlet 服务请求时，它可以调用 `ServletRequest.startAsync()`。你的 Servlet 然后可以从方法返回而不进行响应，线程将返回池。稍后当某些事件发生时，你的应用程序可以从 `asyncContext` 获取响应对象并使用它向客户端发送响应。你将在第 9 章学习更多关于使用异步请求。这种方法通常被用于长轮询技术，第 10 章将讨论这一点。

# 保护共享资源

为多线程应用程序编写时，典型的问题是共享资源的访问。在方法执行期间创建的对象和变量是安全的，只要该方法正在执行，其他线程无法访问它们。然而，例如 Servlet 中的静态和实例变量可以被多个线程同时访问（记住：在最坏的情况下会有 200 个线程）。同步访问这些资源是非常重要的，以防止其内容损坏并导致应用程序出现可能的错误。

你可以采用几种技术来保护共享资源。考虑 TicketServlet 中的第一行代码：

```java
private volatile int ticket_ID_SEQUENCE = 1;
```

接下来，回顾列表 3-2 中 `createTicket` 方法中的同步块代码：

```java
synchronized(this)
{
    id = this.TICKET_ID_SEQUENCE++;
    this.ticketDatabase.put(id, ticket);
}
```

这段代码块中发生了两件事：`TICKET_ID_SEQUENCE` 递增并获取了值，然后 `Ticket` 被插入到对象的哈希表中。这两个变量都是 Servlet 的实例变量，意味着多个线程可能同时访问它们。将这些操作放在 `synchronized` 块中，可以保证在它完成之前，其他线程无法执行独占访问，从而避免死锁。当然，在使用 `synchronized` 代码块或方法时应始终格外小心，以防止同步应用不当导致死锁，该问题超出了本书的讨论范围。

> **警告** 编写 Servlet 方法时需要记住的一点：永远不要将请求或响应对象存储在静态或实例变量中。千万不要这样做。没有可能——这会给你带来麻烦。任何属于请求的资源应该作为局部变量和方法参数存在。

### 总结

在本章中，你学习了 Servlet 接口以及 `GenericServlet` 和 `HttpServlet` 类，并了解了 `HttpServletRequest` 和 `HttpServletResponse` 接口。你学习了如何使用请求和响应对象来处理传入的请求并做出相应的响应。你尝试了部署描述符，并探索了如何使用 `web.xml` 和注解来配置 Servlets。你还发现了处理 HTTP 请求时最重要的任务之一：处理请求参数（包括查询参数和 POST 变量）以及通过表单提交接受文件上传。你介绍了 Servlet 和初始化参数以及如何使用它们来配置你的应用程序。最后，你学习了请求线程、线程池，以及多线程考虑在 Web 应用程序编程中为什么很重要。

到此时，你应该牢牢掌握了在 Web 应用程序中创建和使用 Servlet 的基础。在本章中你可能注意到的主要不便之一，是向响应中编写简单 HTML 的代码既复杂又繁琐。在下一章中，你将探索这个问题的答案，以及它如何让 Java EE 世界的生活变得更加轻松：JavaServer Pages（JSP）。

# 4

## 使用 JSP 显示内容

**本章内容**

- 使用你的第一个 JSP <br /> 比使用 `out.println("<br />")` 更简单
- 创建你的第一个 JSP
- 在 JSP 中使用 Java（以及为什么你不应该这样做）
- 结合 Servlets 和 JSP
- 关于 JSP 文档 (JSPX) 的说明

**本章 WROX.COM 代码下载**

你可以在 `www.wrox.com/go/projectforwebbapps` 的“Download Code”标签页找到本章的 `wrox.com` 代码下载。本章的代码分为以下示例：

- Hello-World-JSP 项目
- Hello-User-JSP 项目
- Customer-Support-v2 项目

**本章的新 MAVEN 依赖**

除了上一章引入的 Maven 依赖外，你还需要以下 Maven 依赖。排除（exclusions）是必要的，因为 JSTL 实现对旧版本的 JSP 和 Servlet 规范定义了临时依赖，这些版本的 Maven artifact ID 与当前版本不同。

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
```

```xml
<dependency>
  <groupId>org.glassfish.web</groupId>
  <artifactId>javax.servlet.jsp-jstl</artifactId>
  <version>1.2.2</version>
  <scope>compile</scope>
  <exclusions>
    <exclusion>
      <groupId>javax.servlet</groupId>
      <artifactId>servlet-api</artifactId>
    </exclusion>
    <exclusion>
      <groupId>javax.servlet.jsp</groupId>
      <artifactId>servlet-jsp-api</artifactId>
    </exclusion>
    <exclusion>
      <groupId>javax.servlet.jsp.jstl</groupId>
      <artifactId>jstl-api</artifactId>
    </exclusion>
  </exclusions>
</dependency>
```

在上一章中，你学习了 Servlets 以及处理请求、响应、请求参数、文件上传、Servlet 配置等内容。你可能注意到在编写 Servlet 代码输出 HTML 时存在某种不便。向响应输出内容：反复调用 `ServletOutputStream` 或 `PrintWriter` 类的方法来输出内容，并且必须将 HTML 内容放在 Java 字符串中，还需要对引号进行转义，这确实非常痛苦。在本章中，你将探索 Java Pages 以及它们如何让你的生活变得简单得多。

## <BR /> 比 OUTPUT.PRINTLN("<BR />") 更简单

Java 是一门强大的语言。它拥有许多功能和特性使其变得有用、灵活且易于使用。你是因为喜欢 Java 并想学习如何用它做更多事情而读这本书的吗？那么你是怎么想？

```java
PrintWriter writer = response.getWriter();

writer.append("<!DOCTYPE html>\r\n");
writer.append("<head>\r\n");
writer.append("<title>Hello Application</title>\r\n");
writer.append("</head>\r\n");
writer.append("<body>\r\n");
writer.append("Hello, World!\r\n");
writer.append("</body>\r\n");
writer.append("</html>\r\n");
```

这种方式的代码量相当冗长。为了实现这一点需要编写大量的代码。带有换行符（`\r\n`）的代码是为了让 HTML 源代码可读。如果你在纯 HTML 文件中编写之前的示例，它将非常简单：

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



最近示例的问题是它是一个静态 HTML 文档。如果在其加入动态内容，编写可能会更容易，维护也可能更容易。JSP 本质上是一种混合解决方案，结合了 Java 代码和 HTML 标签。除了 Java 代码，JSP 还可以包含任何 HTML 标签、内置 JSP 标签（第七章）、自定义 JSP 标签（第八章）以及被称为表达式语言（第五章）的技术。

在本章中，你将探索 JSP 的基本规则以及其语法、声明、脚本段和表达式的工作原理。你还学习了 JSP 的生命周期以及它最终如何向客户端发送响应。

# 为什么 JSP 更好

JSP 有替代方案。也许常见的替代方案是 Facelets，它属于更广泛的 JavaServer Faces（或简称 JSF，容易与之混淆）。还有模板框架，如 Velocity、FreeMarker、SiteMesh 和 Tiles，所有这些都以某种方式补充或替换 JSP 提供的功能。本书无法涵盖与 Servlet 3.1 规范配合的所有演示技术。因此，它将关注最流行和最广泛的技术。

下面的示例可以在 wrox 上 Hello-World-JSP 项目的 `index.jsp` 文件中找到，它重建了第二章中的 Hello-World 项目，但使用的是 JSP 而不是 Servlet 来向用户传递问候。

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<html>

<head>

    <title>Hello World Application</title>

</head>

<body>

    Hello, World!

</body>

</html>
```

此示例与本节中原始的仅 HTML 示例几乎完全相同。新代码是第一个，并已**加粗**显示。这是你将在“创建你的第一个 JSP”章节中详细检查的几个 JSP 指令之一。此特定指令设置了页的内容类型（content type）和编码，你之前通过 `HttpServletResponse` 上的 `setContentType` 和 `setCharacterEncoding` 方法实现了这一点。此 JSP 中的其他所有内容都是纯 HTML，按原样传回给客户端。问题是：“背后到底发生了什么？”

# JSP 在运行时发生了什么

JSP 仅仅是一个高级的 Servlet。也许你听过“语法糖（syntactic sugar）”这个短语。终究，无论以何种方式，今天经常使用的所有流行语言都是语法糖。以 Java 为例，作为你编写的代码，当你编译 Java 时，它会被转换为字节码。重要的是字节码——而不是 Java 本身。事实上，Java 中许多不同的语句可以转换为相同的字节码。但更进一步说，字节码并不是 JSP 的最终渲染结果。这种字节码是平台无关的，但不足以在不同的操作系统上运行。

当在 JRE 中运行时，JSP 编译器会将其编译成机器码并执行。像 C 这样的低级语言仅仅是它们实际被编译到的代码的语法糖。JSP 是另一种形式的语法糖。在运行时，JSP 代码由 JSP 编译器解释，该编译器解析 JSP 代码中的所有特殊特性并将其转换为 Java 代码。从每个 JSP 创建的类实现了 `Servlet`。然后，Java 代码会经历它正常通过的循环。在运行时，它被编译成字节码，然后转换为机器码。最后，转换为 Servlet 的 JSP 像其他 Servlet 一样处理请求。

为了研究这一点，请执行以下步骤：

1. 在你的 IDE 中编译 Hello-World-JSP 项目，启动调试器，并在浏览器中访问 `http://localhost:8080/hello-world`。你应该会在屏幕上看到那个熟悉的问候语。
2. 浏览你的文件系统找到 Tomcat 8.0 目录（Windows 为 `C:\Program Files\Apache Foundation\Tomcat 8`），并进入 `Catalina\localhost\hello-world` 目录。Tomcat 将应用程序的所有编译后的 JSP 放在此目录中，但它留下了生成的中间 Java 文件，以便你进行检查和排除故障。
3. 继续向下查找目录直到找到 `index_jsp.java` 文件。用你最喜欢的文本编辑器打开它（`index_jsp.class` 文件）。

你应该找到一个扩展了 `org.apache.jasper.runtime.HttpJspBase` 的类。这个抽象类——你可能已经猜到了——扩展了 `HttpServlet`。`HttpJspBase` 为所有 Tomcat 编译的 JSP 提供了一些基础功能，当你的 JSP 执行时，最终执行的是 Servlet 的 `service` 方法，该方法最终会执行 `_jspService` 方法。

如果你检查 `_jspService` 方法，你会发现系列向输出流写入 HTML 的方法调用。你所替换的这段代码对你来说看起来非常相似，因为它与你用此 JSP 替换的 Java 代码没有区别。当然，JSP Servlet 类在每个 Web 容器上看起来并不相同。例如，`org.apache.jasper` 类是 Tomcat 特有的。在你运行的每个 Web 容器上会有所不同。关键点是，JSP 的行为和语法有一个标准规范，只要你使用的容器与该规范兼容，你的 JSP 在所有容器上的运行情况应该是相同的，即使它们转换后的 Java 代码看起来完全不同。

JSP 像普通的 Servlet 一样也可以在运行时进行调试。为了演示这一点，在 JSP 中包含 "Hello, World" 的行上设置一个断点，并刷新浏览器。此时，你将命中 JSP 中的断点，并且会注意到几点。首先，你在 JSP 代码内部命中了断点！你不需要在翻译后的 Servlet 类中设置断点；Java、Tomcat 和你的 IDE 都可以将 JSP 中的断点与运行时执行的代码匹配。你还应该注意到，尽管断点可能在 JSP 中，但调试器显然不在那里。堆栈将显示你的运行时已进入了 `_jspService` 方法，变量将向你显示在 `index_jsp` 类该作用域内定义的实例和局部变量。

`language` 属性告诉容器 JSP 使用的是哪种 JSP 脚本语言。JSP 脚本语言（不要与解释型脚本语言混淆）是一种可以嵌入 JSP 中以执行某些操作的语言。目前，Java 是 JSP 唯一支持的脚本语言，但此属性允许未来对其进行扩展。

从技术上讲，你可以省略此属性。因为 Java 是唯一支持的 JSP 脚本语言，而且在规范中 Java 是默认值，因此当此属性缺失时，默认为 Java。`contentType` 属性告诉容器在响应时应该发送的 `Content-Type` 头部值。`Content-Type` 头部包含内容类型和字符编码，用分号隔开。如果你还记得读过 `index_jsp.java` 文件，它包含了该文件被翻译而成的 Java 代码：

```java
response.setContentType("text/html;charset=UTF-8");
```

需要注意的是，上述代码段等同于以下两行代码，这些你在第 3 章的 Hello-User 项目中见过：

```java
response.setContentType("text/html");
response.setCharacterEncoding("UTF-8");
```

此外，这两者都等同于以下一行代码：

```java
response.setHeader("Content-Type", "text/html;charset=UTF-8");
```

如你所见，有多种方法可以完成相同的任务。`setContentType` 和 `setCharacterEncoding` 是便利方法。使用哪种方法取决于你；尽管如此，通常应该选择一种并坚持使用以避免混淆。然而，由于这里的大部分内容代码都是基于 JSP 的，你主要将关注页面指令的 `contentType` 属性。

## 指令、声明、脚本段和表达式

除了在 JSP 中使用的 HTML 和 JSP 标签外，还有几种结构定义了 JSP 语言范围。它们是指令（directives）、声明（declarations）、脚本段（scriptlets）和表达式（expressions）。简单来说，它们看起来像：

```jsp
<%@ this is a directive %>
<%! This is a declaration %>
<% this is a scriptlet %>
<%= this is an expression %>
```

## 使用指令

指令用于引导 JSP 解释器执行操作（例如设置内容类型）或对文件进行假设（例如它使用哪种脚本语言）、导入类、在翻译时包含其他 JSP 或包含一个 JSP 库。

## 使用声明

你使用声明在你的 JSP Servlet 类作用范围内声明某些内容。例如，你可以在声明标签内定义实例变量、方法或类。你需要记住，这些声明都是在生成的 JSP Servlet 类中完成的或者你定义的任何类实际上都是该 JSP Servlet 类的内部类。

## 使用脚本段

与声明类似，脚本段也包含 Java 代码。然而，脚本段有不同的范围。虽然声明中的代码在翻译时会被复制到 JSP Servlet 类体中，且必须用于声明某些字段、类型或方法，但脚本段会被复制到之前使用的 `_jspService` 方法体中。此方法执行范围内的任何局部变量在你的脚本段中都是可见的，且任何在方法体内部合法的代码在脚本段中也是合法的。因此，你可以定义局部变量，但不能定义实例字段。你可以使用条件语句、操作对象并进行算术运算，这些在声明中是无法做到的。你甚至可以定义类（尽管听起来很奇怪，但在 Java 中在方法内进行类定义是合法的）；但这些类在 `_jspService` 方法之外没有范围。在声明中定义的类或变量可以在脚本段中使用，但不能在声明内部使用脚本段定义的变量。

## 使用表达式

表达式包含简单的 Java 代码，其返回的结果可以写入客户端输出，且表达式将代码的返回变量输出到客户端。因此，你可以在表达式中进行算术运算，得到一个可以显示的数值结果。你可以调用某些返回 String、数字或其他原始类型的方法，从而得到一个可显示的返回值。本质上，任何在整个范围内合法的代码都可以放在表达式中。赋值语句右侧的任何代码都可以放在表达式中。表达式与脚本段一样在同一个方法中执行。

看看这个示例代码。它并没有任何实际作用，但它展示了在指令、声明、脚本段和表达式中可以做的各种操作。

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%!
    private final int size = 0;
    protected String cowboy = "rodeo";

    // 下面的赋值不是声明式的，取消注释会导致错误
    // cowboy = "test";

    public long addFive(long number) {
        return number + 5L;
    }

    public class MyInnerClass {
    }

    MyInnerClass instanceVariable = new MyInnerClass();

    // WeirdClassWithinMethod 在方法范围内，所以下面的声明
    // 取消注释会导致错误
    // WeirdClassWithinMethod bad = new WeirdClassWithinMethod();
%>
<%
    class WeirdClassWithinMethod {
        WeirdClassWithinMethod weirdClass = new WeirdClassWithinMethod();
        MyInnerClass innerClass = new MyInnerClass();
        int seven;
        seven = 7;
    }
%>
<%= "Hello, World" %><br />
<%= addFive(12L) %>
```

## 汇总

在空项目的 Web 目录下创建一个名为 `gibberish.jsp` 的 JSP 文件，并将上述代码放入其中（或者直接使用 Hello-World-JSP 项目中的 JSP）。如你所见，有多种方法可以完成相同的任务。`setContentType` 和 `setCharacterEncoding` 是便利方法。使用哪种方法取决于你；尽管如此，通常应该选择一种并坚持使用以避免混淆。然而，由于这里的大部分内容代码都是基于 JSP 的，你主要将关注页面指令的 `contentType` 属性。

## 注释你的代码

就像所有其他语言一样，JSP 也有注释方法。有三种注释方式：

- 传统的行注释
- 传统的块注释
- JSP 注释

你还没有使用的新的注释类型是 JSP 注释。JSP 注释的语法类似于 XML 注释，唯一的区别在于：

- 行注释：`// ...`
- 块注释：`/* ... */`
- JSP 注释：`<%-- ... --%>`

执行此操作时需要考虑的是每一个没有产生输出的 JSP 标签以及每个指令（directive）、声明和脚本段（scriptlet），都会向客户端输出空行。因此，如果你有许多用于导入的页面指令，后面紧跟着各种声明和脚本段，你的输出中可能会出现几十行空行。为了修复这个问题，JSP 开发者通常会将一个标签的末尾与下一个标签相链：

```jsp
<%@ page import="java.util.Map" %>
<%@ page import="java.util.List" %>
<%@ page import="java.io.IOException" %>
```



这个示例的逻辑与上一个示例完全相同，但结果是在输出顶部只产生了一个空行。在“结合 Servlet 和 JSP”章节中，你将学习如何使用部署描述符来完全消除这些空间。

## 使用指令

之前你已经接触了指令（`directive`），这是一种以 `<%` 开头并 `%%>` 结尾的 JSP 特性。指令有不同的类型，此时将对其进行讨论：

## 更改页面属性

你已经探索了页面指令的一些功能，例如 `contentType`、`language` 和 `import` 属性。页面指令还有许多其他功能。正如前面解释过的，页面指令为你提供了对 JSP 如何翻译、渲染和传输到客户端的某些控制。以下是可能包含在此指令中的其他属性：

### pageEncoding

### session

此属性必须为 `true` 或 `false`，表示 JSP 是否参与 HTTP Session。默认情况下为 `true`，这允许你访问 JSP 中的隐式 `session` 变量（详见《使用 Java（以及为什么你不应该这样做）》）。如果你将其设置为 `false`，则无法使用该会话变量。如果你的应用程序不使用 Session 且你想提高性能，将其设置为 `false` 可能是一个好主意。在第 5 章中了解更多关于 HTTP Session 的信息。

### isELIgnored

此属性指定是否对此 JSP 进行解析和翻译表达式语言（EL）。你将在第 6 章中学习 EL。在 JSP 2.0 规范之前，默认值为 `true`，这意味着你对每个想要使用 EL 的 JSP 都必须将其设置为 `false`。从 JSP 2.0 开始（本书中使用的是 JSP 2.3），默认值为 `false`，因此你永远不需要担心这个设置。

### buffer and autoFlush

这两个属性密切相关，它们的默认值分别为 `"8kb"` 和 `true`。它们控制 JSP 的输出是在生成时立即发送到浏览器，还是经过缓冲后分批发送。`buffer` 属性指定 JSP 缓冲区的大小或 `"none"`（输出将不会被缓冲），而 `autoFlush` 指明缓冲区在达到其大小限制后是否自动刷新。如果 `buffer` 设置为 `"none"` 且 `autoFlush` 设置为 `false`，则在 JSP 翻译为 Java 时会发生异常。如果 `autoFlush` 设置为 `false` 且缓冲区满了，则会发生异常。这是确保 JSP 生成的内容不超过特定长度的一种方便方法。

当 `autoFlush` 设置为 `true`（默认值）时，缓冲区越小，刷新到客户端的数据就越少。通过 `buffer="none"` 完全禁用缓冲区可以提高 JSP 的性能，因为减少了内存消耗和 CPU 开销。然而，这并不是没有副作用的。无缓冲区会导致向浏览器发送更多数据包，这可能会略微增加带宽消耗。此外，当响应的第一个字符开始流向客户端时，HTTP 响应头必须在响应之前包含并发送。因此，在缓冲区刷新之后，你无法设置响应头（`response.setHeader(...)`）或转发 JSP（`<jsp:forward />`），在禁用了缓冲器的 JSP 中，你完全无法设置响应头或转发 JSP。在某些情况下，为了提高服务器端性能，这是一个可以接受的代价。

### errorPage

如果在执行 JSP 发生错误，此属性将指示容器将请求转发到何处。

### isErrorPage

此属性表示此 JSP 是否正作为错误页面使用（默认为 `false`）。如果设置为 `true`，则将启用页面上的隐式异常变量。你会在发生错误时跳转到的 JSP，或者在容器中定义为错误处理 JSP 的 JSP 中这样做。

### isThreadSafe

默认为 `true`，这告诉容器该 JSP 可以安全地同时处理多个请求。如果改为 `false`，容器将确保 JSP 是线程安全的。

### extends

此属性指定要继承的类。

## 其他属性

在大多数 JSP 中，`contentType`（以及 `pageEncoding`）是页面指令中唯一会改变的属性。`session` 和 `isErrorPage` 可能是最常用的属性。

## 包含 JSP

包含 JSP 很容易，但有些规则需要记住。为了演示这一点，请遵循以下步骤：

1. 在项目的 Web 目录下创建一个名为 `includ.jsp` 的 JSP，并在其中包含以下行代码（或使用 Hello-World-JSP 项目）：

```jsp
<%@ include file="index.jsp" %>
```

2. 编译并调试你的应用程序，并到 `localhost:8080/includ.jsp`。你应该看到熟悉的页面，这意味着你的包含操作已生效。
3. 现在进入 Tomcat 工作目录并打开创建的 `includ_jsp.java` 文件。你会立即注意到，除了类名外，它与 `index_jsp.java` 完全相同。这是因为 JSP 在翻译时被静态包含了。

`include` 指令为容器提供了被包含文件的路径。语法非常直观：

```jsp
<%@ include file="/path/to/some.jsp" %>
```

另一种包含 JSP 的方法，它可以实现动态（运行时）包含而不是静态（翻译时）包含。使用 `<jsp:include>` 标签来实现这一点：

```jsp
<jsp:include page="/path/to/some.jsp" />
```

`jsp:include` 没有 `file` 属性；它有一个 `page` 属性。路径仍然相对于当前文件或从 Web 根目录开始，就像 `include` 指令一样。它在翻译时不包含。相反，被包含的文件是动态编译的。在运行时，请求被临时转发到包含的 JSP，该 JSP 的输出被写入响应，然后控制权返回包含的 JSP。通过在项目 Web 根目录下创建一个 `dynamicIncluder.jsp` 文件并包含以下代码，可以很容易地观察到：

```jsp
<jsp:include page="index.jsp" />
```

再次编译并调试并访问 `http://localhost:8080/dynamicIncluder.jsp`，然后打开 Tomcat 创建的 `dynamicIncluder_jsp.java` 文件。你现在可以看到此 JSP 文件的内容完全不同。文件中最感兴趣的行代码是：

```java
org.apache.jasper.runtime.JspRuntimeLibrary.include(request, response, "index.jsp", out, false);
```

会将请求和响应发送到另一个方法，该方法运行包含的 JSP，将其内容写入响应，并返回。

这两种方法各有优劣。包含包含指令（`include directive`）速度快，因为它只被评估一次，而且在包含的 JSP 中定义的所有变量都在作用范围内，并可以被包含的 JSP 引用。这种方法会让你的 JSP（以及结果上的 `_jspService` 方法）运行时间更长，这一点非常重要，因为编译后的 Java 方法的字节码不能超过 65,534 字节。`<jsp:include>` 标签不会引起这个问题，但它的性能也没有那么好，因为它在每次页面加载时都必须评估，而且在包含的 JSP 中定义的变量不在作用范围内，无法在包含的 JSP 中使用。最终，你需要在每次需要包含文件时做出决定，但在某些情况下，使用包含指令是一个很好的选择。

> 注意：默认情况下，Web 容器会翻译并编译以 `.jsp` 和 `.jspx` 结尾的文件（你稍后会学习到这些 JSP）。你也可以使用 `.jspf` 扩展名；这些文件通常称为 JSP 片段（JSP Fragments），不会被 Web 容器编译。虽然没有规定 JSP 的硬性规则（如果你想，可以配置 Web 容器来编译它们），但存在一些公认的最佳实践。JSP 文件代表无法独立存在的 JSP 片段，应该被包含而不是被直接访问。这就是为什么 Web 容器通常不编译它们的原因。实际上，在某些情况下，JSP 文件引用了只有在被包含在另一个 JSP 文件中才存在的变量。出于这个原因，JSP 文件应该只使用包含指令进行包含，包含的 JSP 中定义的变量必须在包含的 JSP 作用范围内。

## 包含标签库

第 7 章和第 8 章将讨论标签库，但现在提到它们是因为它们被包含的方式。使用 `taglib` 指令来引用标签库，这样你就可以在 JSP 中使用该库定义的标签。与包含指令一样，`taglib` 指令也非常简单：

```jsp
<%@ taglib uri="http://java.sun.com/jsp/jstl" prefix="c" %>
```

`uri` 属性指定了标签库定义的 URI 命名空间，`prefix` 属性定义了你在引用库中标签时使用的别名。你将在第 7 章中学习更多关于其含义的内容。

## 使用 `<jsp>` 标签

所有的 JSP 都支持一种 XMLNS 为 `jsp` 的特殊标签。该标签有许多用途和功能。在 JSP 文档中（你将在本节最后一部分学习的 JSP 的 XML 版本）使用的功能，或者是旧 JSP 版本的遗留（在旧版本中操作比现在困难得多，因此这里没有涵盖）。但是，你应该学习该标签的几个有用功能。

### `<jsp:forward>`

你已经学习了 `<jsp:include>` 以及它与包含指令的区别。类似的标签是 `<jsp:forward>` 标签。它允许你将请求从当前执行的 JSP 转发到另一个 JSP。与 `<jsp:include>` 不同，请求不会返回到原始 JSP。这不是重定向（`redirect`）；客户端浏览器看不到这种变化。此外，当转发发生时，JSP 写入响应的内容将保留在响应中；它不会像重定向那样的被擦除。使用 `<jsp:forward page="some/other/page.jsp" />` 非常简单：

```jsp
<jsp:forward page="some/other/page.jsp" />
```

在这个示例中，请求被转发到 `/some/other/page.jsp`。转发之前生成的任何响应内容仍将发送到客户端浏览器。任何响应将被忽略且不评估。此标签与 `<jsp:include>` 标签不同。如果 `<jsp:forward>` 标签之后的代码被忽略，那么这个标签的行为将与 `<jsp:include>` 标签一样。

### `<jsp:useBean>`、`<jsp:getProperty>`、`<jsp:setProperty>`

三个相关的标签是 `<jsp:useBean>`、`<jsp:getProperty>` 和 `<jsp:setProperty>`。`<jsp:useBean>` 在页面上声明 JavaBean 的属性，`<jsp:getProperty>` 从使用 `<jsp:useBean>` 声明的 bean 中获取属性（使用 getter 方法）。同样，`<jsp:setProperty>` 设置属性（使用 setter 方法）。在这种情况下，Java bean 是任何实例化的对象。`<jsp:useBean>` 实例化一个类来创建 bean，而这个 bean 可以通过另外两个标签、自定义标签和 JSP 脚本来访问。以这种方式声明 bean 的优势在于，它让该 bean 对其他 JSP 标签可用；如果你只是简单地在脚本段（`scriptlet`）中声明 bean，那么它将只对脚本和表达式可用。

### `<jsp:plugin>`

最后是 `<jsp:plugin>` 标签，它是用于渲染的 HTML 中嵌入 Java Applet 的方便工具。该标签避免了弄乱为了在所有浏览器中运行 Java Applet 所需的 `<object>` 和 `<embed>` 标签复杂结构的风险。它为你处理这些 HTML 标签，Applet 能够在支持 Java 插件中心的所有主流浏览器中运行。以下是使用 `<jsp:plugin>` 标签的示例：

```jsp
<jsp:plugin type="applet" code="MyApplet.class" jversion="1.8">
  <jsp:params>
    <jsp:param name="appletParam" value="paramValue"/>
  </jsp:params>
  <jsp:fallback>
    你使用的浏览器不支持 Java Applets。你可能需要切换浏览器。
  </jsp:fallback>
</jsp:plugin>
```

注意 `<jsp:plugin>` 还可以包含标准的 object/embed HTML 属性，如 `name`、`align`、`height`、`width`、`hspace`、`vspace`。这些属性会被复制到 HTML 标记中。

> 注意：Java Applets 与 Web 应用程序是完全不同的主题，不在本书范围内。如果你想了解更多关于 Java 的知识，大多数书籍涵盖该主题。

## 在 JSP 中使用 Java（以及为什么你不应该这样做！）

在这一节中，你将通过替换 Hello-User 项目来少量探索 JSP 内部 Java。然后你将简要解释为什么不建议在 JSP 中使用 Java（以及为什么有一个部署描述符来禁用它）。

## 在 JSP 中使用隐式变量

JSP 文件有几个用于脚本段和表达式的隐式变量（对象）。它们被认为是隐式的，是因为你不需要在代码的任何地方定义或声明它们。JSP 规范要求 JSP 的翻译器和编译器提供这些变量，并具有精确的作用域。它们定义在执行 JSP 的 Servlet 中（即 `jspService` 方法）。这意味着你不能在 JSP 声明（`declarations`）中的任何代码中使用它们。声明具有类作用域。你可以通过查看上一节检查的任何 JSP 的 `jspService` 方法看到隐式变量是如何定义的：

```java
public void jspService(final java.servlet.http.HttpServletRequest request,
    final java.servlet.http.HttpServletResponse response) {
  final java.servlet.jsp.PageContext pageContext;
  final java.servlet.HttpSession session = null;
  final java.servlet.ServletContext application;
  final java.servlet.Config config;
  final java.servlet.jsp.JspWriter out = null;
  final java.lang.Object page = this;
  final java.servlet.jsp.JspWriter jsp_out = null;
  final java.servlet.jsp.PageContext jsp_page_context = null;
  try {
    response.setContentType("text/html;charset=UTF-8");
    pageContext = jspFactory.getContext(this, request, response,
        null, true, 8192, true);
    jsp_page_context = pageContext;
    application = pageContext.ServletContext();
    config = pageContext.getAuthConfig();
    session = pageContext.getSession();
    out = pageContext.getOut();
    jsp_out = out;
  }
```



# 在 JSP 中使用 Java（以及为什么你不应该这样做！）

代码并不是整洁代码，但代码的重要部分已加粗，以便你理解发生了什么。代码块强调了 JSP 规范要求的隐式变量的声明或赋值（或两者）。未加粗的变量（如 `_jsp_out` 或 `_jsp_page_context`）是 Tomcat 特有的变量，不保证在其他容器中存在且绝不应该在你的 JSP 中使用。这段代码中有八个隐式变量，但 JSP 规范定义了九个隐式变量。现在来看每一个这些隐式变量，你就会理解为什么缺少了一个。

## request 和 response

`request` 变量是 `HttpServletRequest` 的实例，`response` 变量是 `HttpServletResponse` 的实例，这两个你在第 3 章中学习过。在 Servlet 中对请求执行的任何操作在 JSP 中都可以完成，包括获取请求参数、设置属性，甚至从响应体中读取。你在上一章学到的规则同样适用于这里。然而，对 JSP 中响应对象的操作有一些限制。这些限制并不是合约限制，因此它们在编译时不会强制执行。相反，它们可能会导致意外的行为或错误。例如，你不应该调用 `getWriter` 或 `getOutputStream`，因为 JSP 已经在向响应输出写入内容。你也不应该设置内容类型或字符编码、刷新（flush）或重置缓冲区，或更改缓冲区大小。这些都是 JSP 会做的事情，如果你的代码也做了这些操作，就会导致问题。

## session

该变量是 `HttpSession` 的实例。你将在下一章学习更多关于 session 的知识。记得上一节提到的，page 指令有一个 `session` 属性，默认值为 `true`。这个 session 变量在之前的代码示例中可用，并且默认会在你所有的 JSP 中都可用。如果你将 page 指令的 `session` 属性设置为 `false`，则 JSP 中的 session 将未定义且无法使用。

## out

`JWriter out` 可供你在所有的 JSP 中使用。它是一个 `Writer`，就像你从 `HttpServletResponse` 的 `getWriter` 方法获取的一样。由于某种原因你需要直接写入响应，你应该使用 `out` 变量。然而，在大多数情况下，你可以使用简单的表达式或在 JSP 中编写 HTML 内容。

## application

这是 `ServletContext` 的实例。回想第 3 章，这让你能够访问整个应用程序的配置，包括所有的初始化参数。为什么这个变量被命名为 application 还是个谜团。

## config

`config` 变量是 `ServletConfig` 的实例。与 `application` 变量不同，它的名称实际上反映了它的本质。正如你在第 3 章中学习到的，你可以使用此对象来访问 JSP 的配置，例如初始化参数。

## pageContext

该对象是 `PageContext` 类的实例，提供了多个方便方法来获取请求属性和 session 属性，访问请求和响应以及其他文件。

## page

`page` 变量是一个值得研究的有趣对象。它是 `java.lang.Object` 的实例，这起初让它看起来毫无用处。然而，本质上它是来自 JSP 的变量。因此，你可以将其强制转换为 `Page` 并使用在 `Page` 接口上定义的方法。`JspPage`（继承 Page）和 `HttpRequest`（继承 JSP），你可能永远不需要使用这个变量。JSP 规范说，当脚本语言为 Java 时，`page` 是该变量的同义词。

## exception

这就是上一个示例中缺少的变量。回想上一节提到的，你可以在 JSP 中指定 `isErrorPage` 属性，其目的是为了处理错误。`isErrorPage` 的默认值为 `false`，如果你没有在任何地方都没有使用它，那么 `exception` 变量在任何 JSP 中都没有被定义。如果你创建一个 `isErrorPage` 设置为 `true` 的 JSP，隐式的 `exception` 变量（一个 `Throwable`）会被自动定义。你可以阅读 JSP 规范文档。

## 尝试隐式变量

现在你已经理解了隐式变量及其用途，你应该通过编写一些使用隐式变量的 JSP 代码来探索它们。在你的项目中，在 web 根目录下创建一个 `greeting.jsp` 文件，并将以下代码放入其中（或使用 Hello-User-JSP 项目）：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%
    private static String DEFAULT_USER = "Guest";

    String user = request.getParameter("user");

    if (user == null) {
        user = DEFAULT_USER;
    }
%>

<!DOCTYPE html>
<html>
<head>
    <title>Hello User Application</title>
</head>
<body>
    Hello, <%= user %><br><br>

    <form action="greeting.jsp" method="POST">
        Enter your name:<br />
        <input type="text" name="user" /><br />
        <input type="submit" value="Submit" />
    </form>
</body>
</html>
```

将此与你在上一章为 Hello-User 项目的 `HelloServlet.java` 中编写的内容进行比较。要写的内容少得多，但实现了相同的功能。注意 `DEFAULT_USER` 变量的使用、用于请求声明的脚本段（scriptlet）以定义名称并在未设置时赋予默认值，以及用于输出变量值的表达式。现在编译并调试这段代码，并在你的浏览器中访问 `http://localhost:8080/hello-world/greeting.jsp`。尝试在输入框中输入一个名称并点击 Submit 按钮——post 变量被检测并使用了。现在尝试访问 `http://localhost:8080/hello-world/greeting?user=Allison`，你会发现查询参数也被检测到了，并且被鼓励去探索 Tomcat 将你的 JSP 转换而后的代码。

你在 Hello-User 项目中做的另一件事是创建了一个 Servlet 来演示使用多个参数。这也可以使用 JSP 复制。在你的项目 web 根目录下创建一个名为 `checkboxes.jsp` 的文件（或使用 Hello-User-JSP 项目）：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<!DOCTYPE html>
<html>
<head>
    <title>Hello User Application</title>
</head>
<body>
    <form action="greeting.jsp" method="POST">
        <input type="checkbox" name="fruit" value="Banana" /><br />
        <input type="checkbox" name="fruit" value="Apple" /><br />
        <input type="checkbox" name="fruit" value="Orange" /><br />
        <input type="checkbox" name="fruit" value="Guava" /><br />
        <input type="checkbox" name="fruit" value="Kiwi" /><br />
        <input type="submit" value="Submit" />
    </form>
</body>
</html>
```



# 在 JSP 中使用 Java（以及为什么你不应该这样做！） | 89

存在且绝不应该在你的 JSP 中使用。这段代码中有八个隐式变量，但 JSP 规范定义了九个隐式变量。现在来看每一个这些隐式变量，你就会理解为什么缺少了一个。

## request 和 response

`request` 变量是 `HttpServletRequest` 的实例，`response` 变量是 `HttpServletResponse` 的实例，这两个你在第 3 章中学习过。在 Servlet 中对请求执行的任何操作在 JSP 中都可以完成，包括获取请求参数、设置属性，甚至从响应体中读取。你在上一章学到的规则同样适用于这里。然而，对 JSP 中响应对象的操作有一些限制。这些限制并不是合约限制，因此它们在编译时不会强制执行。相反，它们可能会导致意外的行为或错误。例如，你不应该调用 `getWriter` 或 `getOutputStream`，因为 JSP 已经在向响应输出写入内容。你也不应该设置内容类型或字符编码、刷新（flush）或重置缓冲区，或更改缓冲区大小。这些都是 JSP 会做的事情，如果你的代码也做了这些操作，就会导致问题。

## session

该变量是 `HttpSession` 的实例。你将在下一章学习更多关于 session 的知识。记得上一节提到的，page 指令有一个 `session` 属性，默认值为 `true`。这个 session 变量在之前的代码示例中可用，并且默认会在你所有的 JSP 中都可用。如果你将 page 指令的 `session` 属性设置为 `false`，则 JSP 中的 session 将未定义且无法使用。

## out

`JWriter out` 可供你在所有的 JSP 中使用。它是一个 `Writer`，就像你从 `HttpServletResponse` 的 `getWriter` 方法获取的一样。由于某种原因你需要直接写入响应，你应该使用 `out` 变量。然而，在大多数情况下，你可以使用简单的表达式或在 JSP 中编写 HTML 内容。

## application

这是 `ServletContext` 的实例。回想第 3 章，这让你能够访问整个应用程序的配置，包括所有的初始化参数。为什么这个变量被命名为 application 还是个谜团。

## config

`config` 变量是 `ServletConfig` 的实例。与 `application` 变量不同，它的名称实际上反映了它的本质。正如你在第 3 章中学习到的，你可以使用此对象来访问 JSP 的配置，例如初始化参数。

## pageContext

该对象是 `PageContext` 类的实例，提供了多个方便方法来获取请求属性和 session 属性，访问请求和响应以及其他文件。

## page

`page` 变量是一个值得研究的有趣对象。它是 `java.lang.Object` 的实例，这起初让它看起来毫无用处。然而，本质上它是来自 JSP 的变量。因此，你可以将其强制转换为 `Page` 并使用在 `Page` 接口上定义的方法。`JspPage`（继承 Page）和 `HttpRequest`（继承 JSP），你可能永远不需要使用这个变量。JSP 规范说，当脚本语言为 Java 时，`page` 是该变量的同义词。

## exception

这就是上一个示例中缺少的变量。记得上一节提到的，你可以在 JSP 中指定 `isErrorPage` 属性，其目的是为了处理错误。`isErrorPage` 的默认值为 `false`，如果你没有在任何地方都没有使用它，那么 `exception` 变量在任何 JSP 中都没有被定义。如果你创建一个 `isErrorPage` 设置为 `true` 的 JSP，隐式的 `exception` 变量（一个 `Throwable`）会被自动定义。你可以阅读 JSP 规范文档。

## 尝试隐式变量

现在你已经理解了隐式变量及其用途，你应该通过编写一些使用隐式变量的 JSP 代码来探索它们。在你的项目中，在 web 根目录下创建一个 `greeting.jsp` 文件，并将以下代码放入其中（或使用 Hello-User-JSP 项目）：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<%
    private static String DEFAULT_USER = "Guest";

    String user = request.getParameter("user");

    if (user == null) {
        user = DEFAULT_USER;
    }
%>

<!DOCTYPE html>
<html>
<head>
    <title>Hello User Application</title>
</head>
<body>
    Hello, <%= user %><br><br>

    <form action="greeting.jsp" method="POST">
        Enter your name:<br />
        <input type="text" name="user" /><br />
        <input type="submit" value="Submit" />
    </form>
</body>
</html>
```

将此与你在上一章为 Hello-User 项目的 `HelloServlet.java` 中编写的内容进行比较。要写的内容少得多，但实现了相同的功能。注意 `DEFAULT_USER` 变量的使用、用于请求声明的脚本段（scriptlet）以定义名称并在未设置时赋予默认值，以及用于输出变量值的表达式。现在编译并调试这段代码，并在你的浏览器中访问 `http://localhost:8080/hello-world/greeting.jsp`。尝试在输入框中输入一个名称并点击 Submit 按钮——post 变量被检测并使用了。现在尝试访问 `http://localhost:8080/hello-world/greeting?user=Allison`，你会发现查询参数也被检测到了，并且被鼓励去探索 Tomcat 将你的 JSP 转换而后的代码。

你在 Hello-User 项目中做的另一件事是创建了一个 Servlet 来演示使用多个参数。这也可以使用 JSP 复制。在你的项目 web 根目录下创建一个名为 `checkboxes.jsp` 的文件（或使用 Hello-User-JSP 项目）：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<!DOCTYPE html>
<html>
<head>
    <title>Hello User Application</title>
</head>
<body>
    <form action="greeting.jsp" method="POST">
        <input type="checkbox" name="fruit" value="Banana" /><br />
        <input type="checkbox" name="fruit" value="Apple" /><br />
        <input type="checkbox" name="fruit" value="Orange" /><br />
        <input type="checkbox" name="fruit" value="Guava" /><br />
        <input type="checkbox" name="fruit" value="Kiwi" /><br />
        <input type="submit" value="Submit" />
    </form>
</body>
</html>
```

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

![](img/4677f981a0e1067137bb55a122f8498d_128_0.png)

现在编译、调试并导航到 `http://localhost:8080/hello-world/contextParameters.jsp`。与基于 Servlet 的 Hello-User 项目一样，你应该能看到上下文参数的值。

# 为什么你不应该在 JSP 中使用 Java

在 JSP 中使用 Java 有许多优势，除了本章之前提到的用途外，你可能还会输出由指令（directives）、声明（declarations）、脚本段（scriptlets）和其他 JSP 标签产生的空白字符。在本章较早，你已经学习了如何将一个指令的结尾与下一个指令连接起来，以防止在响应中出现额外的换行。这已经为你处理了这些问题，让你能够编写更整洁的代码。

之前还提到了使用部署描述符完全禁用 Java JSP 的可能性。`<scripting-invalid>` 标签作为默认值以及你代码中的值，设置为 `false` 允许在组内的所有 JSP 中使用 Java。在书的后面部分，你将此值更改为 `true`。确实，在匹配的 JSP 中使用 Java 会导致转换错误。`<el-ignored>` 标签与页面指令的 `isIgnored` 属性类似。如果为 `true`，则在 JSP 中禁止表达式语言（EL）（如果使用 EL 将导致转换错误）。它的默认值为 `false`（允许表达式语言），你可以将其保持为 `true`。

还有少数你可能永远不会使用的其他 JSP 属性组标签。`<is-xml>` 表明匹配的 JSP 是 JSP 文档（`<deferred-syntax-allowed-as-language>` 是你在第 6 章将学习的表达式语言特性）。`<buffer>` 指的是你在本章之前学过的页面指令的 `buffer` 属性。最后，`<error-on-undeclared-namespace>` 指明在匹配的 JSP 中使用未知命名空间的标签时是否抛出错误，默认值为 `false`。

## 结合 Servlet 和 JSP

除了 `<url-pattern>` 之外，`<jsp-property-group>` 内部的所有标签都是可选的，但必须按照以下顺序出现，并省略未使用的标签：`<url-pattern>`, `<el-ignored>`, `<page-encoding>`, `<scripting-invalid>`, `<is-xml>`, `<include-prelude>`, `<include-coda>`, `<deferred-synch-as-literal>`, `<trim-whitespace>`, `<default-content-type>`, `<buffer>`, `<error-on-undeclared-namespace>`。

在客户支持（Customer Support）项目中，你已经在应用程序中所有的 JSP 文件中包含了 `/WEB-INF/jsp/base.jsp`。Web 服务器足够智能，不会在 `base.jsp` 自身包含此规则。它的内容如下：

```jsp
<%@ page import="com.work.TicketServlet, com.work.Attachment" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

这实现了两点：为所有 JSP 导入了这些类，并包含了带有 XMLNS 前缀 `c` 的 JSTL 代码库。你可以在第 7 章中学习更多关于 JSTL 的知识。你可能会好奇为什么这个文件放在 `/WEB-INF/jsp` 目录下而不是 web 根目录下。记住，`WEB-INF` 目录内的文件受 Web 访问保护。对于任何你不希望浏览器直接访问的 JSP，你都会希望这样做，例如依赖于转发 Servlet 提供的会话和请求属性的 JSP 以及仅被包含的 JSP。

在继续之前，你应该查看的是客户支持项目 web 根目录下的 `index.jsp` 文件。这是一个 Web 索引文件，它在 web 根目录的存在标识了应用程序根。它包含两行代码：

```jsp
<%@ page session="false" %>
<c:redirect url="tickets" />
```

第二行代码将用户重定向到相对于部署应用程序的 `/tickets` Servlet URL。第一行代码禁用了 `index.jsp` 文件中的会话，以防止将不必要的 `JSESSIONID` 参数附加到请求的 URL 中（这在创建会话且客户端在同一个请求中被重定向时会发生）。

## 将请求从 Servlet 转发到 JSP

结合 Servlet 和 JSP 的典型模式是：让 Servlet 接收请求、处理任何必要的业务逻辑数据存储或检索、准备一个可以方便在 JSP 中使用的模型，然后将请求转发到 JSP。客户支持应用中 `TicketServlet` 的方法只需要少少更改即可实现这一目标。你可以自己应用这些更改，也可以在下载的项目中查看它们。

## 使用请求调度器 (Request Dispatch)

你应该首先分析 `showTicketForm` 方法，因为它最容易更改。你需要更改它的签名以也接收 `HttpServletRequest`，然后将整个内容替换为简单的 JSP 转发：

```java
private void showTicketForm(HttpServletRequest request,
    HttpServletResponse response)
throws ServletException, IOException
{}
```

```java
request.getRequestDispatcher("/WEB-INF/jsp/view/ticketForm.jsp")
    .forward(request, response);
```



该方法的代码向你介绍了 `HttpServletRequest` 的一个新功能。`getRequestDispatcher` 方法获取一个 `javax.servlet.RequestDispatcher`，它处理内部转发并针对特定路径（在本例中为 `/WEB-INF/jsp/view/ticketForm.jsp`）。在不使用会话的情况下，你可以调用 `forward` 方法将当前请求转发到该 JSP。注意，这不是重定向（redirect）：用户的浏览器不会收到重定向状态码，浏览器 URL 也不会改变。相反，内部请求处理被转发到了应用程序的不同部分。在调用 `forward` 之后，你的 Servlet 代码不应再次操作响应。这样做可能会导致错误或异常行为。现在创建该方法使用的 JSP 文件（以便在下载的项目中查看它）：

```jsp
<%@ page session="false" %>

<!DOCTYPE html>

<html>

<head>

<title>Customer Support</title>

</head>

<body>

<h2>Create Ticket</h2>

<form method="POST" action="" type="multipart/form-data">

<input type="hidden" name="action" value="create"/>

Your Name<br/>

<input type="text" name="userName"/><br/><br/>

Subject<br/>

<input type="text" name="subject"/><br/><br/>

Body<br/>

<textarea name="body" rows="5" cols="30"></textarea><br/><br/>

Attachments<br/>

<input type="file" name="file"/><br/><br/>

<input type="submit" value="Submit"/>

</form>

</body>

</html>
```

## 为表现层进行设计

这并不是一个令人深刻的例子，因为你只是将代码从 Java 移动到了 JSP —— 并没有添加新内容。你还没有使用会话，所以这一点已经在 JSP 中显示了。你接下来应该更改 `TicketServlet` 的 `viewTicket` 方法，它更复杂。一个很好的思考方法是将 Servlet 与你的表现层连接起来——它运行时需要哪些数据元素？——然后编写你的 Servlet 方法来提供这些信息。在这种思路下，从 `/WEB-INF/jsp/view/ticket.jsp` 文件开始：

```jsp
<%@ page session="false" %>

<%

String ticketId = (String)request.getAttribute("ticketId");

Ticket ticket = (Ticket)request.getAttribute("ticketId");

%>

<!DOCTYPE html>

<html>

<head>

<title>Customer Support</title>

</head>

<body>

<h2>Ticket <%= ticketId %>: <%= ticket.getSubject() %></h2>

<i><%= ticket.getCustomerName() %></i><br/>

<%

  if (ticket.getNumberOfAttachments() > 0) {

    int i = 0;

    for (Attachment a : ticket.getAttachments()) {

      if (i > 0) {

        out.print(", ");

      }

      out.print("<a href=\"attachment?attachmentId=" + a.getId() + "\">" + a.getName() + "</a>");

      i++;

    }

  }

%>

<br/><br/>

<a href="tickets">Return to list</a>

</body>

</html>
```

创建此 JSP 显示了表现层需要 `ticketId` 和 `ticket` 才能正确显示。Servlet 将这些属性添加到请求中以实现这一点。`viewTicket` 方法可以更改为提供这些变量并将请求转发到 JSP：

```java
private void viewTicket(HttpServletRequest request,
    HttpServletResponse response)
throws ServletException, IOException {

String idString = request.getParameter("ticketId");

Ticket ticket = this.get(idString);

if(ticket == null) {

  return;

}

request.setAttribute("ticketId", idString);

request.setAttribute("ticket", ticket);

request.getRequestDispatcher("/WEB-INF/jsp/view/ticketForm.jsp")
.forward(request, response);
}
```

该方法的几行代码执行了解析请求参数并从数据中获取 ticket 的逻辑。下面的代码将两个属性添加到请求中。这是请求属性的主要用途。它们可以在处理相同请求的应用程序不同元素之间传递数据，例如在 Servlet 和 JSP 之间。请求属性与请求参数不同：属性是对象，而参数是字符串，且客户端无法像传递参数那样传递属性。请求属性仅供应用程序内部使用。

你需要创建的最后一个方法是 `listTickets` 方法。同样，从客户支持应用中的 `/WEB-INF/jsp/view/listTickets.jsp` 表现文件开始。由于请求属性是对象，你在检索时必须进行转换。在这种情况下，转换为 `Map<Integer, Ticket>` 是未检查的操作，因此你需要抑制警告。

```jsp
<%@ page session="false" import="java.util.Map" %>
<%@ suppressWarnings("unchecked") %>

Map<Integer, Ticket> tickets = (Map<Integer, Ticket>)request.getAttribute("tickets");
```

如你所见，这个 JSP 需要票数据库，所以你应该更改 `listTickets` 方法以提供这个变量并转发请求：

```java
private void listTickets(HttpServletRequest request,
    HttpServletResponse response)
throws ServletException, IOException {

request.setAttribute("ticketDatabase", this.ticketDatabase);

request.getRequestDispatcher("/WEB-INF/jsp/view/listTickets.jsp")
.forward(request, response);
}
```

## 更新后的客户支持应用程序

此时，你的 Servlet 代码应该看起来很杂乱。你已经将显示代码移动到了 JSPs 中，并专注于 Servlet 中的逻辑。在 `TicketServlet` 的上一个版本中有两个方法 `writeHeader` 和 `writeFooter`，它们现在没有被使用，可以删除。这些方法本让在 Servlet 中编写显示代码变得简单了一些，但现在你不需要它们了。最后，`doGet` 和 `doPost` 必须更新以反映你所调用的方法签的更改。

编译客户支持应用程序并在 IDE 调试器中运行 Tomcat。在您喜爱的浏览器中导航到 `http://localhost:8080/support/`。由于 .jsp 文件中的重定向代码，您应该会被重定向到 `http://localhost:8080/support/tickets`。您应该能看到图 4-2 所示的页面。创建几个工单，有些上传了附件，有些没有；查看工单；并下载附件。总体而言，该应用程序的功能与第 3 章中的版本 1 完全相同。然而，现在你不再用 Java 编写显示层，改进和扩展应用程序变得容易得多。

![](img/4677f981a0e1067137bb55a122f8498d_136_0.png)

图 4-2

在下一章中，你通过引入会话支持以及向支持工单添加注释的功能来继续改进客户支持应用程序。

## 关于 JSP 文档 (JSPX) 的说明

在本章稍早之前，你看到了一种名为 JSP 文档的技术，它以 `.jspx` 扩展结尾。它们并没有作为标准 JSP 被广泛使用，尽管它们支持相同的功能，但其实现方式不同。正如本节所示，使用 JSP 文档而非 JSP 带来的难度增加和代码量增加是不容忽视的。此外，由于 JSP 文档的普及程度较低，找到使用它的示例和代码会更少，而且你可能很难找到具有 JSP 文档经验的论坛和邮件列表用户来帮助解决可能遇到的任何问题。出于这些原因，本书没有使用 JSP 文档。只有在本章中，你为了理解这两种相关技术之间的差异看到了 JSP 文档的示例。尽管如此，在你可能处理 XML 的情况下，该技术是存在的。

JSP 文档是 XML 文档（因此得名），因此你见过的许多功能（如指令）无法以相同的方式工作。XML 文档必须遵循模式定义（schema），否则将解析失败。使用文档相比标准 JSP 的主要优势是可以在编译时而非运行时更容易检测 JSP 中的问题。然而，在许多情况下，这种收益并不值得处理 JSP 文档所带来的额外成本。表 4-1 列出了若干 JSP 特性将其语法与 JSP 文档语法进行对比。

## 表 4-1：JSP 特性与 JSP 文档特性对比

| 特性 | JSP 语法 | JSP 文档语法 |
| --- | --- | --- |
| 页指令 | `<%@ page %>` | `<jsp:directive.page />` |
| 包含指令 | `<%@ include %>` | `<jsp:directive.include />` |
| 标签库指令 | `<%@ taglib %>` | `xmlns:prefix="Library URI"` |
| 声明 | `<%! ... %>` | `<jsp:declaration> ... </jsp:declaration>` |
| 脚本段 | `<% ... %>` | `<jsp:scriptlet> ... </jsp:scriptlet>` |
| 表达式 | `<%= ... %>` | `<jsp:expression> ... </jsp:expression>` |
| 注释 | `<%-- ... --%>` | `<!-- ... -->` |

你应该注意到此标签中的两种模式：

- 所有的内容都是 JSP 指令，指令，声明、脚本段和表达式现在都是 XML 标签，并带有 JSP 命名空间前缀。唯一的异常是标签库指令，它变成了根文档标签的属性。

# 理解为什么需要会话

到为止，你已经学习了 Web 应用程序、Web 容器、Servlet、JSP，以及 Servlet 和 JSP 是如何协同工作的。你还学习了请求的生命周期，此时应该很清楚了，到目前为止为你介绍的工具无法让你将来自同一客户端的多个请求关联起来并在它们之间共享数据。你可能认为可以使用 IP 地址作为唯一标识符，并且在某时间范围内来自该 IP 的所有请求都属于你。遗憾的是，由于网络地址转换 (NAT)，这并不可靠。校园内的成千上万学生实际上可以隐藏在 NAT 路由器后面，使用同一个 IP 地址。正由于这个原因，HTTP 会话的概念已被几乎所有 HTTP 服务器端技术采用，而 Java EE 也在其规范中内置了会话支持。

并不是所有应用程序都需要会话。你在书中看到的 Hello World 不需要会话。到目前为止，“客户支持应用程序是需要会话的。但如果你考虑跨国小部件公司的客户支持，你可能会很快意识到在某些时刻你必须创建账户，而且这些用户需要登录应用程序。客户请求可能包含私有信息，例如其他客户不应看到的服务器配置文件。显然，你将无法限制对支持单的访问，提交的客户和 MWC 支持团队的成员可以访问任何特定的支持单。你可以让用户在访问的每个页面都提供用户名和密码，但可以肯定的是，客户不会对这种解决方案感到满意。

# 维护状态

需要会话来维护一个请求与下一个请求之间的状态。HTTP 请求本身是完全无状态的。从服务器的角度来看，当用户的浏览器打开服务器套字时，请求开始；当服务器将最后一个数据包发回客户端并关闭连接时，请求结束。此时，用户浏览器和服务器之间不再有联系，当下一个请求进来时，没有办法将下一个请求与上一个请求联系起来。

应用程序通常无法以这种无状态的方式正常运行。一个经典的例子是在线购物网站。如今几乎每个在线购物网站都要求你在购买前创建用户名和密码，但即使是少数不需要的网站也可以考虑。当你浏览商店时，发现了一个你喜欢的产品，并将其加入购物车。当你继续浏览商店发现另一个你喜欢的产品时，也将其加入购物车。当你查看购物车时，你会发现这两件产品都仍然来自同一台电脑上的同一个浏览器，并与你的购物车相关。没有其他人可以看到你的购物车或其中的物品——它专门绑定到你的计算机和浏览器上。这种场景是对现实生活中购物体验的类比。你进入最喜欢的杂货店，当你进门时，拿了一个购物车或篮子。（你从服务器获取了一个会话。）你穿过商店，边走边挑选物品，将它们放入购物车（将它们添加到会话中）。当你到达收银台时，你从购物车中取出物品交给收银员，收银员进行扫描并收钱。（你使用会话结账。）当你出门时，你还了购物车或篮子。（你关闭浏览器或注销，结束会话。）

在这个例子中，购物车或篮子在你穿过商店时维护了你的状态。如果没有购物车，你和商店都无法跟上购买所需的一切。如果请求之间不维护状态，你必须“走进来”，拿一件物品，付钱，“走出去”（结束），然后为你想要购买的每个物品重复整个过程。会话是维护请求之间状态的引擎，没有了它们，网络将变成一个完全不同的地方。

### 记住用户

另一个需要考虑的场景是用户论坛。在几乎所有的在线论坛中，用户通过其用户名或“句柄”被识别。当用户进入论坛时，他登录并提供用户名和密码来证明自己的身份。（用户名/密码验证作为身份证明的优点将留到第 2.5 节讨论。）从那个点起，他可以发布帖子、回复帖子、与其他用户进行私信、向版主举报帖子，并可能将帖子标记为收藏。注意，用户在那个时间线内只登录了一次。系统需要在每个请求之间通过某种方法记住他是，而会话提供了这种方法。

# 启用应用程序工作流

用户通常需要某种形式的工作流来使用高级 Web 应用程序完成任务。

立即删除它。（这就是删除 cookie 的方法——将它的过期时间设置为过去。）如果 cookie 没有 `Expires`（过期）或 `Max-Age`（最大年龄）属性，它将在浏览器关闭时被删除。如果存在 `Secure` 属性（它不需要值），浏览器将只通过 HTTPS 发送 cookie。这可以防止 cookie 以未加密的形式被传输。`HttpOnly` 属性将 cookie 限制在浏览器请求中。其他技术（如 JavaScript 和 Flash）将无法访问 cookie。

Web 应用程序和服务器使用 cookie 在客户端存储会话 ID，以便在每次请求时都能将其发送到服务器。在 Java EE 服务器中，此会话的名称默认为 `SESSIONID`。对于客户端与部署在 `http://www.example.com/support` 的 Java EE Web 应用程序之间的系列请求和响应，查看以下内容。这就是如果你使用 Fiddler 或 Wireshark 等网络嗅探工具跟踪 HTTP 请求和响应时，预期看到的内容。

# 请求 1

```
GET /support HTTP/1.1
Host: www.example.com
```

# 响应 1

```
HTTP/1.1 302 Moved Temporarily
Location: https://www.example.com/support/login
Set-Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn; Domain=.example.com; Path=/; HttpOnly
```

# 请求 2

```
GET /login HTTP/1.1
Host: www.example.com
Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn
```

# 响应 2

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
```



# HTTP 会话追踪示例

## 请求 3

```
POST /support/login HTTP/1.1
Host: www.example.com
Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn
```

## 响应 3

```
HTTP/1.1 302 Moved Temporarily
Location: http://www.example.com/support/home
Set-Cookie: remusername=Nick; Expires=Wed, 02-Jun-2021 12:15:47 GMT; Domain=.example.com; Path=/; HttpOnly
```

## 请求 4

```
GET /support/home HTTP/1.1
Host: www.example.com
Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn; remusername=Nick
```

## 响应 4

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 56823
```

响应中的 `Set-Cookie` 头部用于将 cookie 发送到用户的浏览器进行存储。同样，请求中的 `Cookie` 头部用于将 cookie 发回 Web 服务器。在假设的场景中，用户导航到某个支持站点并重定向到登录页面。在重定向期间，用户的浏览器访问登录页面，其中包含了 `SESSIONID` cookie。从那时起，浏览器每次发送新请求时，都会包含 `JSESSIONID` cookie。服务器不再再次发送，因为它知道浏览器已经拥有它。

登录成功后，服务器还会发送一个用户名 cookie。这与会话无关，目的是为了用户提供一种技术，以便每当他访问登录页面时都能自动填充用户名。未来的请求将始终包含此 cookie；尽管未来的响应并不会重置它。请注意，`JSESSIONID` cookie 没有过期日期，而用户名 cookie 将在 2021 年过期（距离现在还有很长时间，之后用户可能已经有一台不同的电脑），而 `JSESSIONID` cookie 将在用户关闭浏览器时立即过期。

> **注意**：在这里使用用户名 cookie 仅是为了演示 cookie 的另一种用途，以及 cookie 如何在 `Cookie` 请求头部中传输。实际的功能——记住用户名——与此并无关。

使用 cookie 传输会话 ID 的障碍之一是用户可以在其浏览器中禁用 cookie 支持，从而完全消除传输会话 ID 的方法。然而，在过去的十年里，这个问题变得越来越少，一个主要的搜索和电子邮件提供商和一个主要的社交网络要求其网站的用户启用 cookie。

# URL 中的会话 ID

另一种传输会话 ID 的流行方法是通过 URL。Web 或应用程序服务器知道要查找 URL 中包含会话 ID 的特定模式，如果找到，则从 URL 中检索会话。不同的技术在 URL 中嵌入和定位会话 ID 时使用不同的策略。例如，PHP 使用名为 `PHPSESSIONID` 的查询参数。Java EE 使用不同的方法：会话 ID 被放置在 URL 最后段（或目录）的矩阵参数中。这释放了查询字符串，使得会话 ID 不与其他查询字符串中的其他参数冲突。

```
http://example.com/support?PHPSESSIONID=Nrxc1Gg2v07kI4Ml1nfoo=bar&high=five
```

给定技术使用的特定技术对结果并不重要：将会话 ID 嵌入 URL 中你就可以避免需要使用 cookie。你可能会好奇，请求 URL 中的会话 ID 最初是如何到达浏览器的。请求只是为了将会话 ID 从浏览器传递到服务器。那么会话 ID 从哪里来？答案是会话 ID 必须嵌入在应用程序响应的每一个 URL 中，包括页面上的链接、表单操作和 302 重定向。考虑之前的示例，使用 Fiddler 或 Wireshark 等网络嗅探工具跟踪 HTTP 请求和响应时，你会看到如下（使用 cookie）：

## 请求 1

```
GET /support HTTP/1.1
Host: www.example.com
```

## 响应 1

```
HTTP/1.1 302 Moved Temporarily
Location: https://www.example.com/support/login
Set-Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn; Domain=.example.com; Path=/; HttpOnly
```

## 请求 2

```
GET /login HTTP/1.1
Host: www.example.com
Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn
```

## 响应 2

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 21765
```

## 请求 3

```
POST /support/login HTTP/1.1
Host: www.example.com
Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn
```

## 响应 3

```
HTTP/1.1 302 Moved Temporarily
Location: http://www.example.com/support/home
Set-Cookie: remusername=Nick; Expires=Wed, 02-Jun-2021 12:15:47 GMT; Domain=.example.com; Path=/; HttpOnly
```

## 请求 4

```
GET /support/home HTTP/1.1
Host: www.example.com
Cookie: SESSIONID=NRx1Clg2vG7ki4MdLn; remusername=Nick
```

## 响应 4

```
HTTP/1.1 200 OK
Content-Type: text/html;charset=UTF-8
Content-Length: 56823
```



响应中的 `Set-Cookie` 头部用于将 cookie 发送到用户的浏览器进行存储。同样，请求中的 `Cookie` 头部用于将 cookie 发回 Web 服务器。在假设的场景中，用户导航到某个支持站点并重定向到登录页面。在重定向期间，用户的浏览器访问登录页面，其中包含了 `SESSIONID` cookie。从那时起，浏览器每次发送新请求时，都会包含 `JSESSIONID` cookie。服务器不再再次发送，因为它知道浏览器已经拥有它。

登录成功后，服务器还会发送一个用户名 cookie。这与会话无关，目的是为了用户提供一种技术，以便每当他访问登录页面时都能自动填充用户名。未来的请求将始终包含此 cookie；尽管未来的响应并不会重置它。请注意，`JSESSIONID` cookie 没有过期日期，而用户名 cookie 将在 2021 年过期（距离现在还有很长时间，之后用户可能已经有一台不同的电脑），而 `JSESSIONID` cookie 将在用户关闭浏览器时立即过期。

> 注意：在这里使用用户名 cookie 仅是为了演示 cookie 的另一种用途，以及 cookie 如何在 Cookie 请求头部中传输。实际的功能——记住用户名——与此并无关。

# 第 5 章 维持会话状态

首先，`HttpServletResponse` 接口定义了两个重写 URL 以在需要时包含会话的方法：`encodeURL` 和 `sendRedirect`。所谓的“编码”意味着在满足以下任何条件时，会话 ID 将被嵌入在 URL 的适当位置版本中：

- 当前请求有一个活动会话（要么通过传递会话 ID 请求会话，要么应用程序创建了新会话）。
- 响应中不存在 `JSESSIONID` cookie。
- URL 不是绝对 URL，而是同一 Web 应用程序内部的 URL。
- 会话重写在部署描述中启用（更多请见“在会话中存储数据”）。

第二个条件是棘手的。只有通过检测浏览器是否允许 cookie，以便在下次请求中查找该 cookie。然而，你需要一个会话来关联；否则，你如何知道该请求是不同用户的第一次请求，还是同一用户未带 cookie 的第二次请求？因此，第二个条件假设缺少 `JSESSIONID` cookie 意味着用户的浏览器不支持 cookie，这意味着对于启用了会话的应用程序，URL 在第一次请求时会被编码（如果用户的浏览器支持 cookie）。不幸的是，即使用户的浏览器接受了 `JSESSIONID` cookie，URL 也会包含 `JSESSIONID` 矩阵参数。

当然，API 的 `HttpServletRequest` 部分可以帮助你向 URL 中嵌入会话 ID `<a>` 标签（在第 7 章中会有更多讨论）也会嵌入会话 ID。

# 会话漏洞

正如你想象的，会话并不是没有漏洞的，如果我不警告你这些漏洞将是我的失职，这些漏洞可能会给你的用户带来严重问题，如果你处理敏感或个人信息（如信用卡号或医疗数据），你可能会面临巨大的罚款。好消息是，解决这些漏洞有很多方法，你也将学习到。当然，我无法涵盖你应用程序中所有可能的漏洞，因为有很多攻击 Web 应用程序的方法。开发者应该在安全方面保持严谨并充分了解知识。在关键任务、敏感应用程序中，使用某种类型的商业扫描器来扫描你应用程序的漏洞是明智的。

## 复制与粘贴错误

会话被破坏的最简单方法之一，可能是毫无防备的用户从浏览器中将 URL 复制并粘贴到电子邮件、论坛帖子、聊天室或其他公共区域。在 URL 中嵌入会 ID（你在本节较早之前读过的相关内容）是这一问题的根源。还记得在客户端和服务器之间来回传递的 URL 吗？这些 URL（包含会 ID）会出现在客户端浏览器的地址栏中。如果用户决定与朋友分享你应用程序中的某个页面，并复制并粘贴地址栏中的 URL，那么会 ID 就会包含在朋友看到的 URL 中。如果他们在会话过期之前访问该链接，他们就会变成共享 URL 的用户的身份。这显而易见的问题是，用户可能会意外看到个人信息。

更危险的情况是心怀不轨的人发现了链接并利用它来劫持用户的会话。他可以更改账户邮箱地址，获取密码重置链接，最终修改密码——让攻击者对用户的账户及其所有内容拥有完全控制权。

尽管这个问题的起源（从地址栏复制并粘贴 URL）是无辜的，但解决这一漏洞的唯一万无一失的方法完全禁用 URL 中的会 ID。虽然这听起来是一个激进的措施，可能会对你应用程序的可用性产生灾难性的后果，但请记住前面提到的，大型互联网公司在使用网站时要求 Cookie 已成为常态。对于如今的网络用户来说，Cookie 已成为生活的一部分，而 Cookie 固有的漏洞比这种漏洞少得多且危险得多。

## 会话固定

会话固定攻击与复制粘贴错误类似，不同之处在于这种情况下“毫无防备的用户”是攻击者，而受害者是使用包含嵌入会 ID URL 链接的用户。攻击者可以通过这种方式获取会 ID（通过 URL 或通过检查浏览器的 Cookie），然后通过电子邮件（或最常见的电子邮件）将包含该 ID 的会话发送给受害者。此时，当攻击者点击链接进入网站时，他的会 ID 就被固定在 URL 中的内容——即攻击者已知的会 ID。如果用户随后在此会话期间登录网站，攻击者也将登录，因为他们共享了该会话，从而获得了访问用户账户的权限。

解决此问题有两种方法：

- 就像复制粘贴错误一样，你可以简单地禁用在 URL 中嵌入会 ID，并禁止你的应用程序通过 URL 接受会 ID（你将在“在会话中存储数据”中探索这一点）。
- 登录后采用会话迁移。当用户登录时，将会话详情更改为新会话并使原始会话失效。（两种方法达到相同的效果：为新“登录”的会话分配不同的会 ID）。攻击者仍然拥有原始的会 ID，但该 ID 已失效且未与用户的会话关联。

> 警告：还有另一种类型的会话固定攻击，恶意网站使用另一个网站的域名写入会 ID Cookie，有效地在受害者的浏览器中设置了另一个网站的会 ID。然而，该攻击的效果与 URL 会话固定攻击相同。Web 应用程序在不禁用会话的情况下无法防御这种漏洞。这种漏洞实际上是浏览器漏洞，而不是 Web 应用程序的漏洞。

所有现代浏览器都修复了这种跨域攻击漏洞（site example.net 为 .com 设置 cookie）。然而，恶意的 .example.net 仍然可以为域名 .example.net 设置会话 Cookie，然后这会被存在漏洞的 .example.net 获取。通过遵循一个简单的规则可以完全避免这个问题：不要与不可信的应用程序共享域名。

## 跨站脚本与会话劫持

你已经读过关于复制粘贴错误的内容，它会被恶意方利用，成为会话劫持的另一种形式。攻击者可以通过这种方式获取会 ID（通过 URL 或通过检查浏览器的 Cookie），然后通过电子邮件将包含该 ID 的会话发送给受害者。此时，当受害者点击链接进入网站时，他的会 ID 就被固定在 URL 中的内容——即攻击者已知的会 ID。如果用户随后在此会话期间登录网站，攻击者也将登录，因为他们共享了该会话，从而获得了访问用户账户的权限。攻击者利用跨站脚本注入页面来劫持会话。攻击者通过 `document.cookie` 属性获取会话 Cookie。这种会 ID 最显易的防御是禁用会话，Web 应用程序在不禁用会话的情况下无法防御这种漏洞。这种漏洞实际上是浏览器漏洞。

这种攻击的显易防御是使用 HttpOnly Cookie 属性，以防止攻击。此外，HttpOnly 属性可以禁用 Cookie 访问，从而防止跨站脚本攻击。

## 不安全的 Cookie

你应该考虑的最后一个漏洞是中间人攻击（MitM），即攻击者观察信息在客户端和服务器之间传输的经典攻击。这导致了传输层安全协议（SSL/TLS）。然而，问题是用户可能首先通过 HTTP 访问你的网站；损害已经造成：浏览器未加密传输会 ID。

Secure 标记是为了解决这个问题创建的。当你的服务器向客户端发送 Cookie 时，它会设置 Secure 标记。这告诉浏览器 Cookie 应通过 HTTPS 传输。从那时起，Cookie 将加密，攻击者无法拦截。缺点是你的网站必须始终是 HTTPS。

## 最强防御

在处理会话安全性时，最后一个选项是 SSL 会 ID。为了通过消除每次请求都执行 SSL 握手来提高 SSL 协议的效率，SSL 协议定义了自己的会 ID。会 ID 在 SSL 握手期间建立，并在随后的请求中共同用于确定加密和解密的密钥。这一概念简化了 HTTP 会 ID 的概念。然而，SSL 会 ID 不通过 Cookie 或 URL 传输或存储，你可以通过 RFC 2246 “TLS 协议”了解更多关于 SSL 会 ID 的工作。对于未经授权的用户，获取 SSL 会 ID 是困难的。一些高安全性网站（例如金融机构）使用 SSL 会 ID 作为 HTTP 会话，在消除 Cookie 和 URL 编码的同时仍保持请求之间的状态。

这是一种在跨请求建立 SSL 会 ID 的极其安全的方法，并且几乎不可攻击。此外，当发现 SSL 漏洞时，它们会在几周内得到处理并通过浏览器更新消除。然而，并非所有人都会使用这种技术；否则，没有方法可以指定这一点，因此旧版本 Java EE 开发人员必须使用容器特定的类来实现 SSL 会 ID。在 Java EE 6.0 规范中，增加了一个选项（你将在下一节中学习），以便轻松让 Web 容器使用 SSL 会 ID，因此配置不再是一个主要问题（尽管许多网站仍在使用这一点）。此外，由于 Secure Cookie 标记，它要求你的网站始终是 HTTPS。如果你足够关注安全并启用此功能，你可能打算让整个网站始终处于 HTTPS，因此这对你来说可能不是一个问题。

SSL Session ID 的另一个问题是，如果你使用 Web 服务器或负载均衡器来管理 SSL 通信——这在集群化服务器环境中非常常见——Web 容器将无法识别 SSL Session ID。在这样的集群环境中，用户的请求必须始终被路由到同一台服务器。根据你的服务器和浏览器，SSL Session ID 的生命周期可能很长，也可能很短，因此很难将其作为 HTTP Session ID 的替代方案。

现在，你已经了解了 session 的相关知识，学习了 `JSESSIONID` Cookie 和 URL 重写，并探索了 session 中固有的某些漏洞及其解决方法，是时候开始在 Java EE 应用程序中使用 session 了。

# 在 Session 中存储数据

在学习如何在 Java EE 中使用 session 的过程中，你将探索位于 w3.com 下载网站上的 Shopping-Cart（购物车）示例项目。你不会再创建一个另一个带有支付系统和相关功能的购物网站。你仅仅是探索使用 session 来聚合跨多个页面收集的数据（在本例中，即添加到购物车的商品）的概念。你可以自己创建该项目，也可以跟随 Shopping-Cart 项目进行。你的项目将从第 4 章的部署描述符 `<jsp-config>` 以及下面的 `/WEB-INF/jsp/base.jsp` 开始：

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

此外，你的 Web 根目录下应该有一个 `index.jsp` 文件，用于重定向到你的商店 Servlet：

```jsp
<c:redirect url="/shop" />
```

## 在部署描述符中配置 Session

在许多情况下，HTTP session 在 Java EE 中已经准备就绪，不需要显式配置。然而，你可以对其进行配置，而且出于安全考虑，你应该这样做。使用 `<session-config>` 标签在部署描述符中配置 session。在该标签内，你可以配置跟踪 session 的方法、session 超时时间，以及如果你使用了 session ID cookie，则可以配置其细节。其中许多项具有默认值，你永远不需要更改。以下代码演示了 session 的所有可能的部署描述符设置。

```xml
<session-config>
  <session-timeout>30</session-timeout>
  <cookie-config>
    <name>JSESSIONID</name>
    <domain>example.org</domain>
    <path>/shop</path>
    <comment><!--![CDATA[您已登录。查看我们的隐私政策获取更多信息。]]></comment>
    <http-only>true</http-only>
    <secure>false</secure>
    <max-age>1800</max-age>
  </cookie-config>
  <tracking-mode>COOKIE</tracking-mode>
  <tracking-mode>URL</tracking-mode>
  <tracking-mode>SSL</tracking-mode>
</session-config>
```

## 在 Session 中存储数据

所有的 `<session-config>` 和 `<cookie-config>` 标签都是可选的，但它们必须按照示例所示顺序出现（省略的标签除外）。`<session-timeout>` 标签指定了 session 在失效之前保持非活动状态的时长（以分钟为单位）。如果值为 0 或更小，则 session 永不会过期。如果省略了此标签，则应用容器的默认值。Tomcat 容器的默认值为 30，可以在 Tomcat 配置中进行更改。为了保持一致性，你应该使用此标签显式设置超时时间。在示例中，当具有特定 session ID 的用户向你的应用程序发送请求时，计时器会在其空闲时重置。如果他超过 30 分钟未发送请求，则该 session 被视为无效并被赋予一个新的 session。`<tracking-mode>` 标签用于 Servlet 3.0 Java EE 6，它指示容器应该使用何种技术来跟踪 session 标识。其取值为：

- URL：将 session ID 嵌入到 URL 中。它不使用 cookie 或 SSL session ID。这种方法并不安全。
- COOKIE：容器使用 cookie 来跟踪 session ID。这种技术非常安全。
- SSL：容器使用 SSL Session ID 作为 HTTP session ID。这种方法是可用中最安全的方法，但要求所有请求必须是 HTTPS 才能正常工作。

你可以多次使用 `<tracking-mode>` 来告诉容器它可以使用多种策略。例如，如果你同时指定了 COOKIE 和 URL，容器将偏于使用 cookie，但在 cookie 不可用时使用 URL（如上一节所述）。将 COOKIE 指定为唯一的跟踪模式会告诉容器将 session 嵌入到 URL 中，并假设用户已启用 cookie。同样地，将 URL 指定为唯一的跟踪模式会告诉容器永远不要使用 cookie。如果你使用 SSL 跟踪模式，则不能同时启用 COOKIE 或 URL 模式。session ID 必须独立使用；在缺少 HTTPS 的情况下，容器无法退回到 cookie 或 URL。

`<cookie-config>` 标签仅在指定为其中一种（或唯一的）跟踪模式时生效。标签允许你自定义容器返回给浏览器的 session cookie：

- `<name>` 标签为 session cookie 添加一个 Name 属性。默认值是 `JSESSIONID`，你可能不需要更改它。
- `<domain>` 和 `<path>` 标签对应于 cookie 的 Domain 和 Path 属性。Web 容器正确地设置了这些默认值，因此你通常不需要自定义它们。Domain 默认值为创建 session 时用于建立请求的域名。Path 默认值为部署上下文名称。
- `<comment>` 标签为 session ID cookie 添加一个 Comment 属性，提供了添加任意文本的机会。这通常用于解释 cookie 的目的，并引导用户查看网站的隐私政策。是否使用此标签完全取决于你。如果省略了此标签，session ID cookie 将不会添加 Comment 属性。

`<http-only>` 和 `<secure>` 标签对应于 HttpOnly 和 Secure 属性，两者默认为 false。为了增强安全性，你应该始终将 `<http-only>` 设置为 true。`<secure>` 只有在你有 HTTPS 时才更改为 true。

最后一个标签 `<max-age>` 指定了控制 cookie 何时过期的 Max-Age 属性。默认情况下，cookie 没有过期日期，这意味着它在浏览器关闭时过期。浏览器关闭时过期 cookie 通常是你想要的。你可以以秒为单位自定义此值（与分钟为单位的 `<session-timeout>` 不同），但这可能会在用户在使用应用程序期间导致跟踪失效。最好不要使用它。

> NOTE：从 Servlet 3.0/Java EE 6 开始，你可以跳过部署描述符，使用 `ServletContext` 编程配置这些许多选项。使用 `SessionTrackingMode` 常量。使用 `getServletCookieConfig` —— 运行此方法来配置任何 cookie-config 设置。仅应在 `ServletContainerListener` 的初始化方法或 `ServletContainerInitializer` 中配置跟踪模式或 cookie 配置。在“应用 session 的实用性”章节中学习监听器，在第 12 章学习 `ServletContainerInitializer`。你目前无法通过编程设置 session 超时——这一遗漏在 Java 8 中已修复。

现在你已经了解了所有可用选项，Shopping-Cart 项目的 session 配置如下：

```xml
<session-config>
```



## 会话配置

```xml
<session-config>
  <session-timeout>30</session-timeout>
  <cookie-config>
    <http-only>true</http-only>
  </cookie-config>
  <tracking-mode>COOKIE</tracking-mode>
</session-config>
```

这使得 session 持续 30 分钟，仅使用 cookie 跟踪 session，并让 session cookie 包含 HttpOnly 属性以确保安全。它接受所有其他默认值，并且没有为 cookie 指定注释。禁用了 URL 跟踪因为它不安全。在本书剩余部分，你将始终使用此 session 配置。

> **NOTE** 如前所述，最安全的方法是使用 SSL Session ID。安全的折中方案是使用 cookie 但设置 Secure 属性以要求 HTTPS。本书没有演示这两种技术之一，因为这需要生成自签名 SSL 证书并学习 Tomcat 中 SSL 的复杂性。这两个主题都超出了本书的范围，可以在 Tomcat 文档中进行更多探索。

## 存储与检索数据

在你的项目中创建一个名为 `com.wrox.StoreServlet` 的 Servlet，并将其注解为 URL 模式为 `/shop` 的 Servlet。此外，在你的 Servlet 中创建一个简单的 Map 来表示产品数据库。（或者直接使用 Shopping-Cart 项目。）

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

你可以使用这个产品数据库来“浏览”并将购物车中的项目与产品名称关联。

## Servlet 中的 Session

为 `doGet` 方法创建一个简单的实现，支持三种操作：浏览 (`browse`)、加入购物车 (`addToCart`) 和查看购物车 (`viewCart`)：

```java
@Override
protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
    String action = request.getParameter("action");
    if (action == null)
        action = "browse";
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

Servlet 的 `browse` 和 `viewCart` 方法应该非常简单，只需添加请求属性并转发到 JSP 即可：

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

这些方法的相似之处在于，它们都将产品添加到请求属性中，但它们将它们转发到了 JSP。现在来看下 `addToCart` 方法：

```java
private void addToCart(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
    int productID;
    try {
        productID = Integer.parseInt(request.getParameter("productID"));
    } catch (Exception e) {
        response.sendRedirect("shop");
        return;
    }
    HttpSession session = request.getSession();
    if (session.getAttribute("cart") == null) {
        session.setAttribute("cart", new Hashtable<Integer, Integer>());
    }
    @SuppressWarnings("unchecked")
    Map<Integer, Integer> cart = (Map<Integer, Integer>) session.getAttribute("cart");
    if (cart.containsKey(productID)) {
        cart.put(productID, cart.get(productID) + 1);
    }
    response.sendRedirect("shop?action=viewCart");
}
```

这个方法更为复杂。首先，它获取并解析要添加到购物车的产品 ID。之后，加粗的代码调用了一些你尚未查看过的新 Session 相关方法。`HttpServletRequest` 上的 `getSession` 方法有两种形式：`getSession()` 和 `getSession(boolean)`。

## 在 Session 中存储数据

调用 `getSession()` 会调用 `getSession(true)`，如果存在现有的 Session 则返回它，如果不存在 Session 则创建一个新的 Session（它永远不会返回 null）。相反，调用 `getSession(false)` 在存在现有的 Session 时返回它，在不存在 Session 时则返回 null。调用带参数 `false` 的 `getSession` 有其原因——例如，你可能想测试是否已经创建了 Session——但在大多数情况下只需调用 `getSession()` 即可。`getAttribute` 方法返回存储在 Session 中的对象。它有一个对应的方法 `getAttributeNames`，返回 Session 中所有属性名称的枚举。`setAttribute` 方法将对象绑定到 Session。在例子中，代码查找 `cart` 属性，将其添加到购物车，并获取简单的购物车 Map。然后它在购物车中查找产品 ID，如果不存在则将其添加并将数量置零。最后，它增加购物车中产品的数量。

## 在 JSP 中使用 Session

Servlet 代码可以处理应用程序中的逻辑，但你需要一些 JSP 来显示产品和购物车。开始创建 `/WEB-INF/jsp/view/browse.jsp`：

```jsp
<% page import="java.util.Map" %>
<!DOCTYPE html>
<html>
<head>
    <title>Product List</title>
</head>
<body>
    <h2>Product List</h2>
    <a href="<c:url value="/shop?action=viewCart" />">View Cart</a><br />
    <%
    @SuppressWarnings("unchecked")
    Map<Integer, String> products = (Map<Integer, String>) request.getAttribute("products");
    if (products != null) {
        for (Map.Entry<Integer, String> entry : products.entrySet()) {
            out.println(entry.getKey() + ": " + entry.getValue() + "<br>");
        }
    }
    %>
</body>
</html>
```

## 清空购物车

```java
(HttpServlet response)
throws ServletException, IOException {
    request.getSession().removeAttribute("cart");
    response.sendRedirect("shop?action=viewCart");
}
```

如你所见，这是你的 Servlet 中最简单的方法。该代码从 session 中删除了 `cart` 属性，并将你重定向到空购物车。

> **注意：** 应该指出的是，你也可以使用 `getAttribute` 来获取 `Map`，然后对 `Map` 调用 `clear` 方法。这也会清空购物车，而且效率更高，因为会导致更频繁的垃圾回收。然而，本示例演示了 `removeAttribute` 方法的使用。

3. 你需要一种方法导航到清空购物车的链接 `/WEB-INF/jsp/viewCart.jsp`，并在该处添加以下链接：
   `<a href="<c:url value="shop?action=emptyCart"/>">Empty Cart</a><br /> />`
4. 编译并调试你的应用程序，并向购物车中添加一些产品。
5. 当你的购物车开始填充后，点击“Empty Cart”（空购物车）。购物车中的所有产品都应该消失，为你留下一个空购物车。

你可以对 session 进行一些其他操作，这些操作在这里不会进行实验，但你需要了解它们。你可能想做的最明显的事情是获取 session ID 以用于目的。在 `HttpServlet` 对象上调用 `getID` 就可以轻松地实现这一点。还有 `getCreationTime` 和 `getLastAccessedTime` 方法。尽管 `getCreationTime` 返回的是 session 创建的时间（毫秒级的 Unix 时间戳），但 `getLastAccessedTime` 方法可能更直观。

这并不是你最后一次以某种方式使用 session。相反，它是最后一次请求该会话 session ID（在 URL、cookie 或 SSL 会话中）的请求时间戳。`isNew` 方法如果 session 是在当前请求期间创建的，则可以返回 `true`，这意味着用户的浏览器尚未收到 session ID。

`getInactiveInterval` 返回此 session 在过期之前可以处于非活动（无包含 session ID 的请求）的最大时间（秒为单位）。与之对应的方法是 `setInactiveInterval`，它允许你更改空闲窗口。默认情况下，`getInactiveInterval` 会覆盖你在 `<session-timeout>` 中设置的值。`setInactiveInterval` 方法会覆盖此配置设置，为此特定的 session 将其缩短或加长。

为了理解为什么你可能需要这样做，请考虑一个应用程序，其中某些用户（管理员）可能需要不同的空闲时间。你可能想让某个特定 session 的空闲时间比其他时间更短。`setInactiveInterval` 方法会覆盖此配置设置，为此特定的 session 将缩短或加长。

## 有效地应用会话

到此时，你应该已经熟悉会话的工作原理以及如何在 Java EE 应用程序中使用会话了。你可以用会话做很多事情。此外，还有额外的工具可以帮助你跟踪会话的创建、销毁和更新。你将在本节进一步探索这些工具。在本章的剩余部分中，你将使用在 wrox.com 下载网站上的 Customer-Support-v3 项目，并会将会话集成到客户支持应用程序中。

## 为客户支持应用程序添加登录功能

在上一章中，你通过在所有 JSP 的页面属性中添加 `sessions="false"` 禁用了客户支持应用程序中的会话。你现在想要使用会话，但这会阻止你的实现，因此请从客户支持应用程序版本 3 的所有 JSP 中移除 `session="false"` 属性。记住，该属性默认认为 true，移除该属性将启用会话。

你还应该将 `<session-config>` XML 添加到 Shopping-Cart 应用程序的部署描述符，以便对会话进行更好的安全性配置，并确保会话 ID 不出现在 URL 中。现在显而易见，客户支持应用程序需要某种带登录的用户数据库。在本章中，你将为应用程序添加一种基础的、不安全的登录功能。在书的最后部分，你将使用更全面的身份验证和授权系统来保护你的应用程序，现在可以保持简单。

## 设置用户数据库

在你的类中添加一个 `LoginServlet` 并在其中创建一个静态的、内存用户数据库：

```java
@WebServlet(
    name = "loginServlet",
    urlPatterns = "/login"
)
public class LoginServlet extends HttpServlet {
    private static final Map<String, String> userDatabase = new Hashtable<>();

    static {
        userDatabase.put("Nicholas", "password");
        userDatabase.put("Sarah", "drowsap");
    }
}
```



```java
userDatabase.put("Mike", "wordpass");
userDatabase.put("John", "green");
}
}
```

如你所示，用户数据库是用户名到密码的简单映射，没有考虑任何种不同的权限级别。用户可以访问系统，也可以不能，而且密码没有以安全的方式存储。`doGet` 方法负责显示登录界面，或者你现在就创建它。

# 第 5 章 维持状态会话

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
    request.getRequestDispatcher("/WEB-INF/jsp/view/login.jsp")
        .forward(request, response);
}
```

上一个示例中的第一步是检查用户是否已经登录（是否存在 username 属性），并将其重定向到该屏幕。如果用户未登录，它会将 `loginFailed` 属性设置为 false，并将请求转发到登录 JSP。当登录表单提交时，它将 POST 到 `doPost` 方法：

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
        request.getRequestDispatcher("/WEB-INF/jsp/view/login.jsp")
            .forward(request, response);
    } else {
        session.setAttribute("username", username);
        request.changeSessionId();
    }
}
```

## 创建登录表单

接下来创建以下内容：

```html
<!DOCTYPE html>
<html>
<head>
  <title>登录</title>
</head>
<body>
  <h2>登录</h2><br />
  <form method="post">
    用户名: <input type="text" name="username" /><br />
    密码: <input type="password" name="password" /><br />
    <input type="submit" value="登录" />
  </form>
</body>
</html>
```

## 添加退出链接

测试时，你必须关闭浏览器才能退出客户支持应用程序。这可能并不理想，也不是企业级应用程序的标志。添加退出链接是非常容易的。首先，调整 `LoginServlet.doGet` 方法的代码以支持用户退出：

```java
HttpSession session = request.getSession();
if (request.getParameter("logout") != null) {
  session.invalidate();
  response.redirect("login");
  return;
} else if (session.getAttribute("username") != null) {
  response.redirect("tickets");
  return;
}
```

## 使用监听器检测会话变化

Java EE 会话最实的功能之一是会话事件概念。当会话发生变化时（例如添加或删除会话属性），Web 容器可以通知你的应用程序这些变化。这是通过发布-订阅模型的形式实现的，允许你将应用程序中需要感知会话变化的代码与修改会话的代码解耦。如果某些第三方代码（如 Spring Framework 或 Spring Security）修改了你应用程序中的会话，这种方法特别有用；它允许你在不更改第三方代码的情况下检测到这些变化。你用于检测这些更改的工具被称为监听器。

Servlet API 定义了多个监听器，并不是所有的监听器都会监听某种形式的会话活动。你通过实现相应的监听器接口来订阅事件，然后（大多数情况下）要么向部署描述符中添加 `<listener>` 配置，要么从 Servlet 3.0/Java EE 6 开始使用 `@javax.servlet.annotation.WebListener` 注解该类（但其他注解例外）。

你可以在单个类中实现一个或多个数量的监听器接口；尽管你并不希望将不相关的代码放在同一个类中。当发生触发你代码所订阅的事件发布的情况时，容器会调用你类中对应于该事件的方法。

> **注意** 从 Servlet 3.0/Java EE 6 开始，你不再需要 `@WebListener` 注解监听器类或在部署描述符中声明它，而是可以使用 `ServletContext.addListener` 方法进行程序化注册。你只能在 `ServletContextInitialized` 或 `ServletContainerInitializer.onStartup` 方法中调用此方法。当然，你在此使用的任何 `ServletListener` 都必须经过注册（使用这三种方法之一）。你可以在第 12 章中学习更多关于 `ServletContainerInitializers` 的信息。

你可以实现的监听器之一是 `javax.servlet.HttpSessionAttributeListener`。它有三个方法，在会话属性被添加（更新）或删除时会收到通知。

一个特别有趣的监听器是 `javax.servlet.http.HttpSessionBindingListener`。与其他监听器不同，你不需要为 `HttpSessionBindingListeners` 添加部署描述符配置，或对其进行注解。如果一个类实现了此接口，它就能感知到自己作为会话属性的状态。例如，如果 `Foo` 实现了 `HttpSessionBindingListener` 并且你使用 `setAttribute` 将 `Foo` 的实例添加到 `HttpSession` 中，容器将调用包含该实例的 `valueBound` 方法。同样，当你使用 `removeAttribute` 将其从会话中删除时，容器会调用该实例的 `valueUnbound` 方法。

在本节中你将关注的两个监听器是 `javax.servlet.http` 包中的 `HttpSessionListener` 和 `HttpSessionIdListener`。在项目中创建一个实现这两个接口的 `SessionListener` 类，并用 `@WebListener` 注解它（或者跟随 Customer-Support-v3 项目的操作）：

![](img/4677f981a0e1067137bb55a122f8498d_168_0.png)

```java
@WebListener
public class SessionListener implements HttpSessionListener, HttpSessionIdListener {
}
```

`@WebServlet` 并不是通知容器你的代码正在订阅这些事件的唯一方法。你也可以通过程序化的方式注册它，或者在部署描述符中如下所示声明监听器（示例将坚持注解的形式，因为这是最简单的技术）。

```xml
<listener>
    <listener-class>com.wrox.SessionListener</listener-class>
</listener>
```

`HttpSessionListener` 接口定义了 `sessionCreated` 和 `sessionDestroyed` 方法。直观上，`sessionCreated` 在每次创建新会话时被调用。每当会话不再有效时，就会调用 `sessionDestroyed`。这可能是代码中对会话的 `invalidate` 方法的显式调用，也可能是由于活动超时导致的隐式失效。以下代码实现了这些方法：

```java
@Override
public void sessionCreated(HttpSessionEvent e) {
    System.out.println(this.date() + " : Session " + e.getSession().getId() + " created.");
}
```

```java
@Override
public void sessionDestroyed(HttpSessionEvent e) {
    System.out.println(this.date() + " : Session " + e.getSession().getId() + " destroyed.");
}
```

如你所见，这允许你记录会话创建或销毁的时间。这是该特定监听器的常见用例；管理员通常希望以某种方式记录这些信息以备存档。`HttpSessionIdListener` 只定义了一个方法 `sessionIdChanged`。每当请求的 `changeSessionId` 方法更改会话 ID 时，就会调用此方法，该方法在以下代码中实现：

```java
@Override
public void sessionIdChanged(HttpSessionEvent e, String oldSessionId) {
    System.out.println(this.date() + " : Session ID " + oldSessionId + " changed to " + e.getSession().getId());
}
```

这三个条目都使用一个简单的辅助方法为会话活动日志条目添加时间戳。

```java
private SimpleDateFormat formatter =
    new SimpleDateFormat("EEE, d MMM yyyy HH:mm:ss");
...
```

```java
private String date() {
    return this.formatter.format(new Date());
}
```

现在编译、调试并导航到你的应用程序。调试窗口中应立即出现一条日志消息，指示会话已创建。登录应用程序，你应该观察到另一条日志消息，显示会话 ID 已更改。如果你添加到项目中的会话固定保护机制正常工作，你应该看到一个新的会话 ID。

## 维护活动会话列表

除了记录之外，你还可以使用 `HttpSessionListener` 和 `HttpSessionIdListener` 来维护活动会话列表。为了实现这一点，请在列表 5-3 中创建 `SessionRegistry` 类。

### 列表 5-3: SessionRegistry.java

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

该注册表存储了所有活动会话的引用，但你必须以某种方式添加和删除会话。为此，请按照以下步骤操作：

1. 扩展你创建的 `SessionListener`。在 `sessionCreated` 方法中添加以下代码：
   `SessionRegistry.addSession(e.getSession());`
2. 在 `sessionDestroyed` 方法中添加以下代码：
   `SessionRegistry.removeSession(e.getSession());`
3. 在 `sessionIdChanged` 方法中添加以下代码：
   `SessionRegistry.updateSessionId(e.getSession(), oldSessionId);`

```java
public class SessionListServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        if (request.getSession().getAttribute("username") == null) {
            response.sendRedirect("/login");
            return;
        }
        request.setAttribute("numberOfSessions",
            SessionRegistry.getNumberOfSessions());
        request.setAttribute("sessionList", SessionRegistry.getAllSessions());
        request.getRequestDispatcher("/WEB-INF/jsp/view/sessions.jsp")
            .forward(request, response);
    }
}
```

用于显示会话的 `/WEB-INF/jsp/view/sessions.jsp` 代码包含在列表 5-4 中。

为了测试这一点，你需要两个不同的网络浏览器（而不仅仅是同一个浏览器的窗口）：

1. 重新构建并调试你的应用程序，打开第一个浏览器以支持应用程序 URL。
2. 登录后，导航到 `http://localhost:8080/support/sessions`。你应该能在会话列表中看到你当前的会话。
3. 打开第二个浏览器，登录支持应用程序，并在该浏览器中导航到 `http://localhost:8080/support/sessions`。你应该能看到与图 5-4 类似的屏幕。
4. 刷新你打开的第一个浏览器，新会话也应该出现在那里。这意味着你成功地维护了一个会话列表。

![](img/4677f981a0e1067137bb55a122f8498d_173_0.png)

图 5-4

# 列表 5-4：sessions.jsp

```jsp
<%@page import="java.util.List" %>
<%
```



```java
private static String toString(long timeInterval) {
    if (timeInterval < 1000)
        return "less than one second";
    if (timeInterval < 60000)
        return (timeInterval / 1000) + " seconds";
    return "about " + (timeInterval / 60) + " minutes";
}
```

```jsp
<%
    int numberOfSessions = (Integer) request.getAttribute("numberOfSessions");
    @SuppressWarnings("unchecked")
    List<HttpSession> sessions = (List<HttpSession>) request.getAttribute("sessionList");
%>
<!DOCTYPE html>
<html>
<head>
    <title>Customer Support</title>
</head>
<body>
    <a href="<c:url value='/login?logout' />">退出</a>
    <h2>会话列表</h2>
    此应用程序中总共有 <%= numberOfSessions %> 个活动会话。<br /><br />
    <%
        long timestamp = System.currentTimeMillis();
        for (HttpSession aSession : sessions) {
            out.print(aSession.getId() + " - " + aSession.getAttribute("username"));
            if (aSession.getId().equals(session.getId())) {
                out.print(" " + you + ")");
            }
            out.print(" - last active " + toString(timestamp - aSession.getLastAccessedTime()));
            out.print(" ago " + "<br>");
        }
    %>
</body>
</html>
```

**注意** 本示例中列出的会话仅限当前运行的 Tomcat 实例中的会话。如果你的应用程序部署在多个 Tomcat 实例上，根据你的应用程序请求落在哪个 Tomcat 实例，你将看到不同的会话，因为页面仍然只会列出特定 Tomcat 实例上的会话。解决此问题的方案涉及正确配置你的应用程序，以便在集群中设置会话复制。这些主题将在下一节中进行探讨。

# 对使用会话的应用程序进行集群化

在处理企业级应用程序期间，你无疑会对对应用程序进行集群的需求。集群化提供了许多优势，特别是为你的应用程序增加了冗余和可扩展性。配置恰当的应用程序可以发生故障或确保例行维护，而永远不会经历停机。在管理良好的环境中，管理员可以发布升级而不会引起停机。正如你所看到的，集群化是 Web 工具箱中不可或缺的成员。

然而，集群化并非没有缺点，存在着必须克服的挑战。这些挑战中最大的之一是在运行在单独机器上的应用程序实例之间传递消息，即使这些机器位于不同或不连接的网络上，或者世界的不同地区。几十年来，工程师们一直在重新构和重新设计消息系统，不断寻找稳定、可靠且快速的“完美”消息框架。高级队列协议 (`AMQP`)、Java 消息服务 (`JMS`) 和微软消息队列 (`MSMQ`) 是随之产生的三种竞争技术。当然，应用程序集群化的挑战不仅限于消息传递，你在本节中看到的问题是集群中的会话管理。

理解这一节需要你具备一些关于负载均衡的基础知识、它的工作原理以及一些常见的负载均衡策略。这些主题需要大量时间来讨论，并且超出了本书的范畴。

# 在集群中使用会话 ID

你在会话集群化中面临的直接问题是，会话作为对象存在于内存中，并且仅位于 Web 服务器的单个实例上。在纯轮询或智能负载均衡场景下，来自同一客户端的两个连续请求可能会不同的 Web 容器。第一个 Web 容器实例会为收到的第一个请求分配会话 ID，然后当下一个请求来自 Web 容器的另一个实例时，第二个实例将无法识别它。

解决此问题的方案是使用粘性会话（`Sticky Sessions`）。粘性会话的想法是负载均衡能够感知会话，并始终将请求发送到同一个服务器。这可以通过多种方式实现，并在很大程度上取决于负载均衡技术。例如，负载均衡可能会感知服务器的 Cookie，并知道它属于某个会话，从而在后续请求中添加并识别这些 Cookie。

这些技术的潜在缺点是，Web 容器无法使用 `SSL/HTTPS`，因为这会阻止负载均衡器检查或修改请求。然而，许多负载均衡器支持处理 `HTTPS` 的解密，因此你并没有让应用程序安全，只是将加密机制移动到了负载均衡器。某些组织防止使用 `SSL ID` 作为会话 ID。Tomcat 环境中最常用的负载均衡器是使用 `Apache HTTP` 或 `Microsoft IIS` 服务器在 `Apache` 实例之间进行负载均衡。`Apache Tomcat` 连接 <http://tomcat.apache.org/connectors-doc/> 为这些 Web 服务器与 Tomcat 的接口提供了机制。连接器的 `mod_jk` 组件就是粘性会话功能。就像 `iisservice`一样，`isapi_redirect` 是使用 `IIS` 时提供会话功能的 `IIS` 连接器。

图 5-5 所示的这种层次方法可以在维护会话亲和性的同时实现极高的性能和可用性。被称为路由的 Tomcat 连接器（`mod_jk` 或 `isapi_redirect`）使用 `jvmroute` 来指示应该将请求发送到哪个 Tomcat 实例。考虑以下会话 ID：

`AA6E8E2624FFEA96C148DF5BCBBE03`

在具有多个 Tomcat 实例的负载均衡环境中，每个 Tomcat 实例在 Tomcat 的 `conf/server.xml` 配置文件的 `<Connector>` 元素中配置 `jvmroute`。`jvmroute` 附加在所有 ID 的末尾。在具有 `jvmroute` `tcn01`、`tcn02` 和 `tcn03` 的三节点集群中，如果会话源于 `tcn02`，那么相同的会话 ID 将看起来像这样：

`AA6E8E2624FFEA96C148DF5BCBBE03.tcn02`

从那时 Web 服务器（`mod_jk` 或 `isapi_redirect`）就会识别该会话属于 Tomcat 实例 `tcn02`，并将该会话的请求始终发送到该实例。如果你的应用程序通过 `HTTPS` 安全，Web 服务器必须负责证书和加密/解密工作。使用 `mod_jk` 或 `isapi_redirect` 的优势是它们可以访问 `SSL` 会话 ID 并将其重传给 Tomcat，允许 `SSL` 会话跟踪正常工作。这种精确的粘性会话（`sticky-session`）负载均衡方法也适用于 `Apache HTTP/mod_jk` 以及 `IIS/isapi_redirect` 后的 `GlassFish`。

![](img/4677f981a0e1067137bb55a122f8498d_176_0.png)

图 5-5

配置 `mod_jk`、`isapi_redirect` 以及 Tomcat 和 GlassFish 的 `jvmroute` 的具体细节超出了本书的范围，并且随版本变化而异。请参考 Tomcat 和 GlassFish 文档获取说明。`WebLogic`、`WebSphere` 以及其他容器也提供了类似但最终不同的方法，这些方法在它们的文档中详细介绍。

## 理解会话复制与故障转移

使用粘性会话的主要问题是，它可能支持扩展性，但不支持高可用性。如果创建会话的 Tomcat 实例宕机，会话将会丢失，用户必须重新登录。更糟糕的是，用户可能会丢失未使用的工作。为了实现这些目的，会话可以在整个集群中复制，使得所有会话对所有 Web 容器都可用，无论它们源自哪个实例。在应用程序中启用会话复制很容易实现。你只需要在部署描述符中添加 `<distributable>` 标签即可：

```xml
<distributable />
```

到此为止。该标签没有任何属性、标签或内容。在部署描述符中存在此标签会告诉容器在存在集群的情况下跨集群复制会话。当在一个实例中创建会话时，它会被复制到其他实例。如果会话属性发生变化，该会话将重新复制到其他实例，以确保它们拥有会话的最新版本。

当然，这实际上并不简单。这只是标记你的应用程序支持分布式会话。它并没有配置你的 Web 容器的会话复制机制（这是一个本书未讨论的复杂的话题）。它也不自动意味着你的应用程序遵循了最佳实践。你必须小心设置了哪些属性（如果它们不是可序列化的，那么在调用 `setAttribute` 时会抛出 `IllegalArgumentException`）以及如何更新这些会话属性。考虑一下来自 Shopping-Cart 项目的这段代码：

```java
@SuppressWarnings("unchecked")
Map<Integer, Integer> cart = (Map<Integer, Integer>) session.getAttribute("cart");
if (!cart.containsKey(productId))
    cart.put(productId, 0);
cart.put(productId, cart.get(productId) + 1);
```

Web 容器并（也无法）知道包含购物车物品的 `Map` 发生了这种变化。正如此，对会话的更改将不会被复制，这意味着其他实例无法包含购物车中的新项目。这可以简单解决：

```java
@SuppressWarnings("unchecked")
Map<Integer, Integer> cart = (Map<Integer, Integer>) session.getAttribute("cart");
if (!cart.containsKey(productId))
    cart.put(productId, 0);
cart.put(productId, cart.get(productId) + 1);
session.setAttribute("cart", cart);
```

注意新增的代码 `session.setAttribute("cart", cart);`。这看起来可能很愚蠢，因为你用已经分配给它的的相同对象替换了购物车会话属性。然而，调用此方法会告诉容器会话已更改，并导致会话被复制。每当你更改分配给会话的对象时，都必须再次调用 `setAttribute` 以确保更改被复制。

还有一个与会话复制概念相关的监听器。添加到会话属性的对象会触发 `javax.servlet.HttpSessionActivationListener`。当会话被序列化以复制到其他服务器时，会调用 `sessionPassivate` 方法，赋予对象先执行某些操作的机会。当会话在另一个容器中反序列化时，会调用 `sessionActivate` 方法通知属性它已被反序列化。

最后注一点：会话和会话复制不是互斥的概念。一旦将它们结合来实现会话故障转移——会话仍然被复制，但同一会话中的请求会被发送到已知该会话的不同实例。你可以使用这些技术通过会话故障转移提高应用程序的效率，但它们超出了本书的范围。你的 Web 容器文档应该描述它支持的复制功能以及如何使用它们。

### 总结

在本章中，你了解了会话的概念以及客户端与服务器之间建立会话。你学习了会话属性、会话范围以及如何管理它们。你还探索了粘性会话及其对扩展性和可用性的影响。最后，你学习了会话复制以及如何在应用程序中启用它。

## 理解基础语法

EL 的基础语法将需要求值的表达式与 JSP 语法的其余部分开来。JSP 解释器必须检测 EL 表达式的开始和结束，以便能够独立于页面的其他部分解析并评估 EL 表达式。基础语法有两种不同类型：即时求值和延迟求值。

## 即时求值

即时求值 EL 表达式是指 JSP 引擎在渲染时应该解析并评估的表达式。这意味着 JSP 代码是从上往下执行的，当 JSP 引擎遇到 EL 表达式时，会立即对其进行求值，并在页面其他部分继续执行之前。应该被即时求值的 EL 表达式如下例所示，其中 `expr` 是一个有效的 EL 表达式。

```
${expr}
```

美元符号以及左右括号定义了 EL 表达式的边界。括号内的所有内容都将作为 EL 表达式进行评估。更重要的是，这意味着你不能在 JSP 的任何其他用途中使用此语法；否则，它将被求值为一个 EL 表达式，并可能导致 EL 语法错误。如果你确实需要使用此语法将内容写入响应中，你需要转义美元符号：

```
\$(not an EL expression)
```

美元符号前的反斜杠告诉 JSP 引擎这实际上不是一个 EL 表达式，不应被求值。上一个示例将字面地写入响应 `${not an EL expression}`。你也可以使用美元符号的 XML 实体 `&#36;` 代替 `\$`，结果相同。

```
&#36;$(not an EL expression)
```

尽管 JSP 引擎会忽略这一点，但许多人发现使用反斜杠更简单。这仅仅是个人偏好的问题。当然，你可能确实需要在一个想要求值的表达式前面加上一个反斜杠。这*要求*使用反斜杠 XML 实体：

```
\${EL expression to evaluate}
```

在这种情况下，EL 表达式将在反斜杠之后进行求值并渲染。

## 延迟求值

延迟求值 EL 表达式是统一表达式语言（Unified Expression Language）的一部分，主要支持 Faces 的需求。虽然延迟语法在 JSP 中是合法的，但在 JSP 中并不常见。延迟语法的看起来与即时语法几乎相同，同样 `expr` 是一个有效的 EL 表达式：

```
#{expr}
```

在 JSP 中，延迟表达式可以在页面渲染时评估，也可以在回传（postback）到页面时评估，甚至两者兼有。这些细节与本书无关，但你必须理解这与 JSP 不同，因为 JSP 没有 JSP 那样的生命周期概念。在 JSP 中，`#{ deferred syntax}` 仅在 JSP 标签属性中有效，用于延迟 EL 表达式的评估，直到标签的渲染过程。表达式不是在属性值绑定到标签之前进行求值（像使用 `${}` 那样），而是标签获取未求值的 EL 表达式的引用。然后标签可以在适当的时候调用方法对 EL 进行求值。这在第 8 章中会有更多的使用和探讨，但它很少使用。

延迟语法的一个潜在问题是，模板语言和 JavaScript 框架使用 `${}` 语法进行替换。因此，如果你使用这些替换，通常需要对它们进行转义，以防它们与延迟 EL 表达式混淆：

```
\#{not an EL expression}
&#35;also not an EL expression
```

然而，这对于某些利用此语法的框架可能不起作用，如果你需要使用这种语法，或者你有一组 JSP 需要配合 EL 2.1 或更高版本的 JSP，这可能会非常痛苦。（此外，XML 实体与 JavaScript 不兼容。）因此，还有另一种方法可以防止 `#{}` 字面量被作为延迟表达式求值。在部署描述符的 `<jsp-config>` 中，你可以向任何 `<jsp-property-group>` 添加以下标签：

```
<deferred-syntax-allowed-as-literal value="true"></deferred-syntax-allowed-as-literal>
```

这允许以字面方式使用 `#{}` 语法，并防止你在此处转义井号（#）。如果你需要为单个 JSP 控制这一点，可以使用 JSP 页面指令中的 `deferredSyntaxAllowedLiteral="true"` 属性。

在本书的剩余部分中，你只会在示例代码中看到即时求值 EL 语法，而不会使用延迟求值语法，只有一个例外。在第 8 章关于自定义标签和函数库的讨论中，将在定义自定义标签时遇到 `<deferred-value>` 和 `<deferred-method>` 选项。这需要演示延迟语法。

## 放置 EL 表达式

简单来说，EL 表达式几乎可以用 JSP 中的任何地方，但少数例外。
首先，EL 表达式不能在任何指令中使用，所以甚至不要尝试。
(`<%@ page %>`, `<%@ include %>`, 和 `<%@ tag %>` 在 JSP 编译时进行求值，而 EL 表达式是在 JSP 渲染时才求值的，因此它们不起作用。此外，EL 表达式在 JSP 声明 (`<%! %>`)、脚本 (`<% %>`) 或表达式 (`<%= %>`) 中是无效的。如果在其中任何地方使用，EL 表达式将被简单忽略，或者更糟，可能会导致语法错误。

除此之外，EL 表达式几乎可以用任何地方。你可能看到 EL 表达式的一个地方是在写入到屏幕的字面文本中：

用户将看到 `${expr}` 文字并知道 `${expr}` 是好的。

此示例包含两个 EL 表达式，它们在求值后被内联放置在显示的文本中。如果第一个表达式求值为 "red"，而第二个表达式求值为 "it"，用户将看到以下内容：

The user will see red text and will know that it is good.

此外，表达式可以在标准 HTML 标签属性中使用，如下例所示。

```jsp
<input type="text" name="something" value="${expr}" />
```

HTML 标签不是允许 EL 表达式唯一的地方。你也可以在 JSP 标签属性中使用它们，如下代码所示：

```jsp
<c:url value="${expr}/${expr}" />
<c:redirect url="${expr}" />
```



如你所见，EL 表达式不必构成整个属性值。相反，属性值的一个或多个部分可以包含 EL。你可能会好奇其他 HTML 特性，例如 JavaScript 或级联样式表。JSP 引擎不会解析此类标签，并将它们作为字面量写入响应中，因此它们可能以引号或字面格式包含 EL 表达式：

```html
<script type="text/javascript">
var employeeName = '${expr}';
var booleanValue = ${expr};
var numericValue = ${expr};
</script>
<style type="css">
span.error {
  color: ${expr};
}
background-image: url('/some/place/${expr}.png');
}
</style>
```

到目前你已经学习了 EL 的不同类型以及 EL 表达式可以放置的位置，但你可能好奇 `expr` 到底是什么样的。在下一节中你将了解到可以在 EL 表达式中放入什么。

## 使用 EL 语法编写

EL 表达式像任何其他语言一样，都有特定的语法。像 Java、JavaScript 和大多数其他语言一样，该语法是严格的，违反它将在你的 JSP 渲染时导致语法错误。然而，与 Java 不同的是，EL 是松类型的，并内置了许多隐式类型转换，类似于 PHP 或 JavaScript 等语言。表达式的首要规则是它应该求值为值。你不能在表达式中声明变量，或执行某种不会产生结果的赋值或操作。（例如，`${object.method()}` 仅在方法具有非 void 返回类型时有效。）EL 的设计不是为了取代 Java；相反，它的设计目的是提供创建无需 Java 的 JSP 所需的工具。

## 保留关键字

与任何其他语言一样，关于 EL 你首先需要了解的是它的保留关键字列表。这些词仅应被用于其预定义的用途。变量、属性和方法的名称不应与这些保留字相同。

- true or
- false not
- null eq
- instanceof ne
- empty lt
- div gt
- mod le
- and ge

你会认出前四个单词也是 Java 的保留关键字。你可以像在 Java 中使用它们对应的方式一样使用它们。`empty` 关键字用于验证某些 Collection、Map 或数组是否包含任何值，或者 String 的长度是否为一个或多个字符。如果这些值中任一个为 `null` 或 "empty"，则表达式求值为 `true`；否则，求值为 `false`。

```el
${empty x}
```

`div` 和 `mod` 关键字分别映射到 Java 的数学运算除法（/）和取模（%），仅仅是数学符号的替代方案。如果你愿意，仍然可以使用 `/` 和 `%`。`and`、`or` 和 `and not` 关键字分别映射到 Java 的逻辑运算符 `&&`、`|` 和 `||`。与数学运算符一样，你仍然可以使用传统的逻辑运算符，而 `eq`、`ne`、`lt`、`gt` 和 `ge` 分别是 Java 关系运算符 `==`、`!=`、`<`、`<=` 和 `>=` 的替代方案，也可以使用。

## 运算符优先级

与其他语言一样，之前的所有运算符加上 EL 中的其他运算符都有一个需要理解的优先级。这种顺序大部分是直观的。

> 注意：尽管你可以在 EL 3.0 规范内声明变量，但你可以为 EL 表达式赋值变量。使用标准赋值运算符 `=`，在表达式内部赋值 `A = B`，只要 `B` 是一个可以输出到页面上的值。表达式 `${x = 5}` 的结果是将 5 赋值给 `x`，并在 EL 表达式的位置渲染 5。

这与 Java 中的运算符优先级相似。更重要的是，在 Java 和算术方程中，相同优先级的运算符按照它们在表达式中出现的顺序（从左到右）进行考虑。

EL 表达式中首先求值的运算符是括号 `[]` 和点 `.` 解析运算符。考虑以下表达式：

```el
${myCollection['key'].memberName["anotherKey"]}
```

引擎首先解析映射到 `myCollection` 对象中 `key` 的值。然后解析 `myCollection` 中 `key` 值内部的 `memberName` 方法、字段或属性。最后，它定位 `memberName` 求值的 `otherKey` 值。在考虑这些运算符之后，会考虑分组括号 `()`。这些运算符用于改变其他运算符的优先级，就像在 Java 或算术表达式中一样。

第三组考虑的运算符是负号 `-`、`not`、`!` 和 `Empty`。EL 引擎先求值算术运算符 `*`、`/` 和取模 `%`，然后是加法 `+` 和二元减法 `-` 运算符，它们在数学方程中的顺序一样。之后求值 EL 字符串拼接 `+=`（EL 3.0 新增）。接下来，求值比较关系运算符 `<`（或 `lt`）、`>`（或 `gt`）、`<=`（或 `le`）和 `>=`（或 `ge`），然后是等值关系运算符 `==`（或 `eq`）和 `!=`（或 `ne`）。之后，从左到右评估所有的 `and` 和 `&&` 运算符，然后从左到右评估所有的 `||` 和 `or` 运算符，最后从左到右评估 `? :` 条件运算符。

EL 引擎下一个求值的是 lambda 表达式 (`->`)，这是 EL 3.0 规范新增的。它与 Java 8 lambda 表达式运算符具有相同的语法和语义目的。然而，EL lambda 表达式的有效并不运行在 Java 8 上。之后，EL 引擎求值赋值运算符 `=`，这也是在 EL 3.0 规范中添加的。该运算符将运算符右侧某个表达式的值赋值给运算符左侧的变量。表达式的结果就是运算符左侧变量的值。考虑以下表达式：

```el
${x = y + 3}
```

现在假设在执行时，`y` 的值为 4。表达式 `y + 3` 的结果是 7，7 被赋值给 `x`。因为表达式的结果是 `x`，所以 `x = y + 3` 的值是 7。

EL 引擎求值的最后一个运算符是分号 `;` 运算符，这也是 EL 3.0 的新功能。它模仿了 C 语言逗号 `,` 运算符，允许指定多个表达式，除最后一个表达式外的所有值都被声明。为了理解这一点，请参考以下表达式：

```el
${x = y + 3; object.callMethod(x); 'Hello, World!'}
```

这个组合 EL 包含四个表达式。

- 求值表达式 `y + 3`，假设 `y` 为 4，结果为 7。
- 将该值赋值给 `x`。
- 在 `object` 变量上调用 `callMethod` 方法并将 `x` (7) 作为参数传递。
- 求值字符串字面量 "Hello, World!"。该表达式的结果是最后一个分号之后表达式的结果："Hello, World!"

`x = y + 3` 表达式和 `object.callMethod(x)` 表达式的结果被丢弃。这特别适用于将值赋值给 EL 变量，然后将其包含在表达式的其他部分，而不仅仅是输出该值。

为了保持逻辑清晰，下面的列表总结了从上到下的优先级。

## 字面量值

统一表达式语言支持指定值。你已经见过 `true`、`false` 和 `null` 关键字，它们都是字面量。此外，EL 可以拥有字符串值。与 Java 字符串字面量始终由双引号围绕不同，EL 字面量可以使用任意引号。

```el
${This string will be rendered.}
${This string will also "rendered".}
```

你可以看到，使用任何类型的字符串都有优缺点，在许多情况下你只需使用方便的那种。如果字符串内部包含单引号，可能更容易使用双引号。同样，如果字符串内部包含双引号，可能更容易使用单引号。

必须注意的是 JSP 属性中的 EL 表达式字面量。由于这些是由 JSP 引擎解析的，属性引号和字符串字面量之间会冲突。因此，以下示例中的两个 EL 表达式属性都是无效的，会导致语法错误：

```jsp
<c:url value="${value}"/>
<c:url value='${value}' />
```

解决这种冲突有两种有效方法。属性和字面量可以使用相反的引号，或者对字面量引号进行转义。以下示例中的四行都是有效的。

```jsp
<c:url value="${value}"/>
<c:url value='${value}' />
<c:url value="\${value}"/>
<c:url value='\${value}' />
```

通常情况下，你会发现使用相反引号比转义更容易。但如果你的字符串字面量包含单引号或双引号，且你需要将表达式放入属性值中呢？没有其他办法。你必须转义。以下示例中的六行代码处理这种情况时都是有效的。

```jsp
<c:url value="${some \"value\"}"/>
<c:url value='${some \"value\"}' />
<c:url value="${some \'value\'}"/>
<c:url value='${some \'value\'}' />
<c:url value="${some \'value\\'}"/>
<c:url value='${some \'value\\}'}' />
```

需要在位于属性值的字符串字面量中混合单引号和双引号吗？这开始变得复杂：

```jsp
<c:url value="${some attribute\'s \value\"}"/>
<c:url value='${some \"attribute\" \'value\'}' />
```

如你所见，这可能会迅速失控。在可能的情况下，最好保留你的字符串字面量。关于字符串字面量的最后一点是，从 Java EE7 中的表达式语言 3.0 开始，你可以在 EL 表达式中拼接字符串字面量，就像在 Java 中一样。以下示例中的三行都是等价的，并产生相同的输出。

```el
The user will see ${expr} text and will ${expr}.
${'The user will see ' + expr + " * " + text and will += '.'}
${'The user will see ' + expr + " * " + text and will += '.*'}
```

如果 `expr` 返回一个不是字符串的对象，它将通过调用该对象的 `toString` 方法被强制转换为字符串。

EL 中的数字字面量比 Java 更加简化，你还可以在 Java 中无法对数值对象之间进行算术运算。考虑以下三个整数类型的数字字面量：

```el
${105}
${-132147483648}
${13922337203685477580}
```

- 第一个字面量是隐式的 int，在表达式表达式时被视为 int 处理。
- 第二个字面量太大，无法作为 int。在 Java 中，除非你在数字后面加上 L 来表示它是一个 long，否则将产生语法错误，但在 EL 中它直接变成了一个 long。
- 第三个字面量太大，甚至无法作为 long，因此它被隐式地视为 BigInteger。

所有这些转换都在后台完成，不需要你参与。然后是小数类型：

```el
${105.509}
${34000000000000000000000000000001.0}
${1.79769313486231570e+309}
```

与整数类型类似，这些分别是隐式的 float、double 和 BigDecimal。需要注意的是，虽然 Java 的默认小数类型是 double，但 EL 的默认小数类型是 float，除非需要更高的精度。在处理 EL 表达式时请记住这一点。你不能明确指定字面量类型——它总是被隐式处理。

EL 表达式让数学运算变得简单得多，因为所有的类型转换和精度升级都是隐式的，而且算术运算符作用于 BigInteger 和 BigDecimal 类型。考虑以下表达式，它相加了两个数并返回以下值：

```el
${12 + 1.79769313486231570e+309}
```

加法运算符左侧的数字是 int，而右侧的数字是隐式的 BigDecimal。在 Java 中实现此操作通常需要以下代码：

```java
new BigDecimal(12).add(new BigDecimal("1.79769313486231570e+309"));
```

然而，EL 引擎会为你处理好一切。首先，它将 12 从 int 强制转换为 BigDecimal；然后它将加法运算符转换为对方法的调用。

> 注意：在 Java 中，数字可以表示为标准（十进制，10）字面量、八进制（88，0123）字面量、十六进制（16进制，0x23）字面量或二进制（二进制，0b01010011）字面量。在 EL 表达式中，只允许十进制字面量。其他进制的字面量没有等价物。此外，Java 允许在数字字面量中使用下线（1,491_188，0b010_0011）以便于区分数字组（例如替换逗号），这在 EL 表达式中是不允许的。数字字面量必须是连续的。

需要考虑的三个原始字面量是 chars、bytes 和 shorts。你不需要在 EL 表达式中使用这些类型，但在 EL 中调用的某些方法可能期望 char、byte 或 short 作为参数。EL 不包含这些类型的特定字面量，但在需要时会将其他类型转换为 chars、bytes 和 shorts。

任何整数类型在需要时也会强制转换为 byte 或 short，只要该数字没有超出其强制转换的 byte 或 short 的范围。否则，尝试的转换将导致错误。

最后的字面量类型不是原始类型，而是创建各种集合的字面量。集合字面量的构造是一项作为 Java 8 Java Collections API 改进的提案，该提案最终未被采用，而在表达式语言 3.0（目前）中是需要的。你可以根据需要在 EL 表达式中创建集合。语法非常直观，非常类似于 JavaScript 和其他语言的语法，并符合 Java 9 的语法。你可以用 EL 集合构造 Sets、Lists 和 Maps，它们都将被构造为默认实现的实例。字面量 Set 会变成 `HashSet<Object>`，字面量 List 会变成 `ArrayList<Object>`，字面量 Map 会变成 `HashMap<Object, Object>`。考虑第一个 Set 字面量：

```el
{1, 2, 'three', 4.00, x}
```

这构造了一个具有五个不同类型元素的 `HashSet<Object>`。第五个对象 `x` 可以是任何值。逗号分隔字面量 Set 中的元素。你可能需要创建一个 Set，例如作为参数传入：

```el
{1, 2, 'three', 4.00, x}
```

## 对象的属性与方法

EL 提供了访问属性的简化方法。JavaBeans 用于访问方法。在标准表达式中，你可以访问公共字段。假设有一个变量名为 shift，EL 看到：

```el
${shift}
```



然而，在需要某些输入时，方法调用非常有用。假设你有一个 `ComplexNumber` 类表示实数和虚数（形式为 a + bi）。该类显然有一个 `plus` 方法，允许你添加整数、double 或另一个 `ComplexNumber`。你可以调用 `plus` 方法并传入参数：

```
${complex.plus(12)}
```

在这个例子中，`ComplexNumber` 的字符串表示被渲染。然而，假设你想让字符串表示中的 i 正确斜体。`ComplexNumber` 类有一个 `toHtml` 方法来实现这一点。你可以这样调用它：

```
${complex.plus(12).toHtml()}
```

这些是在标准 Java 代码中执行此操作的方法链调用。

# EL 函数

在 EL 中，函数是映射到类静态方法的特殊工具。类似于符合模式的 XML 标签，函数映射到一个命名空间。函数的整体语法如下，其中 `[ns]` 是命名空间，`[fn]` 是函数名，`[al]` 到 `[an]` 是参数：

```
${ns:fn({al1}, {al2}, ... )}
```

函数定义在标签描述符（TLD）中，这听起来很奇怪——函数不是标签。这是早期 EL 作为标准标签库（JSTL）规范的一部分并用于 JSP 属性时的遗留。由于 TLD 概念已经支持命名空间，将 EL 定义保留在 TLD 中是合理的。

可以在第 8 章了解更多关于 TLD 的信息。然而，JSTL 中已经有一组满足大多数开发者在 JSP 中需求的函数。所有与字符串相关的函数——修剪、连接、分割、转义等。按照约定，JSTL 库的命名空间为 `fn`；你可以在 taglib 指令中将其设置为任何内容。在下一节中使用 EL 函数，这里是一些常用的 JSTL EL 函数及其功能：

- `${fn:contains(String, String)}` — 此函数测试字符串是否包含第二个字符串的一个或多个实例，如果是则返回 true。
- `${fn:escapeXml(String)}` — 如果字符串包含特殊字符，使用此函数转义特殊字符。`<` 变成 `&lt;`；`>` 变成 `&gt;`；`&` 变成 `&amp;`；这是防止跨站脚本 (XSS) 攻击的一个特别重要的工具。
- `${fn:join(String[], String)}` — 此函数使用指定的字符串作为分隔符将字符串连接在一起。例如，这可能用于将电子邮件地址数组用逗号分隔并合并一个字符串，以便在页面显示。
- `${fn:length(Object)}` — 如果参数是字符串，此函数将调用并返回在指定字符串上调用 `length` 方法的结果。如果它是一个集合（`Collection`）、`Map` 或数组，它将返回其的大小（`size`）。不支持其他类型。这可能是 JSTL 中最实用的函数。
- `${fn:toLowerCase(String)}` 和 `${fn:toUpperCase(String)}` — 你可以使用这些函数将字符串的大小转换为全小写或全大写。
- `${fn:trim(String)}` — 此函数会去除指定字符串两端的所有空白字符。

JSTL 中还有更多可用函数，你可以点击查看其余部分。遗憾的是，Java EE 6 和 7 中的 JSTL 1.2 没有现成的获取的 HTML 文档。

## 静态字段和方法访问

在表达式语言 3.0 (Expression Language 3.0) 中，你现在可以访问你的 JSP 类路径中任何类中的公共静态字段和静态方法。你可以认为（确实有人这样做）这赋予了 JSP 作者过大的权力，使他们能够执行通常在脚本节（scriptlet）中才能做的任何事情。这是好坏取决于你的决定，但该功能确实存在且在 EL 3.0 中无法禁用。

你访问静态字段和方法的方法与在 Java 中相同——使用完全限定的类名以及用点操作符分隔的字段或方法名。例如，你可以通过以下表达式访问 `Integer` 类上的 `MAX_VALUE` 常量：

```
${java.lang.Integer.MAX_VALUE}
```

除非使用 JSP 页面指令导入了类，否则类名必须是完全限定的。记住在 JSP 中，像 Java 一样，`java.lang` 包下的所有类都为你隐式导入了。因此，之前的 `Integer.MAX_VALUE` 可以写成：

```
${Integer.MAX_VALUE}
```

通过这种方式，你可以访问 JSP 可以访问的任何类的静态字段或方法。需要注意的是，你只能读取字段的值，不能向其写入。（当然，如果一个字段也是 `final` 的，你通常也无法向其写入。）调用类的静态方法同样简单。假设你想反转一个数字的位顺序并查看数字的变化：

```
${java.lang.Integer.reverse(42)}
${Integer.reverse(24)}
```

此表达式调用了 `Integer` 类上的静态 `reverse` 方法，并将数字 42 作为其参数传递。除了调用静态方法外，你还可以调用类的构造函数，它会返回该类的实例，你可以进一步访问其属性、调用其方法，或者简单地强制转换为字符串输出。

```
${com.wrox.User()}
${com.wrox.User('First', 'Last').fName}
```

虽然静态访问可以完全取代 EL 函数和库的行为，但这并不意味着函数库是多余的。之前对 `Integer.reverse` 的静态方法调用可能很方便，但如果有一个映射到静态方法的理论 `int` 函数库，以下表达式更方便：

```
${int:reverse(42)}
```

这可能没有短多少，但想象一个长得多的类名，你就能很快发现为什么函数库非常有用。静态字段访问最实用的领域之一是枚举（enums），这是你接下来应该学习的内容。

## 枚举 (Enums)

你可能在某个时候接触过 Java 枚举，如果你已经使用 Java 一段时间了，你可能熟悉它们有多么实用和强大。传统上，EL 中的枚举在需要时会从字符串转换而来。例如，你的 JSP 中有一个名为 `dayOfWeek` 的作用域变量，它代表新 Java 8 日期时间 API 中 `java.time.DayOfWeek` 的值之一。你可以通过以下表达式测试 `dayOfWeek` 是否为周六：

```
${dayOfWeek == 'SATURDAY'}
```

`DayOfWeek` 被转换为字符串并与 "SATURDAY" 进行比较。这与 Java 不同，在 Java 中这种转换永远不会自动发生。虽然这很方便，但显然不是类型安全的。如果你错过了周六（或者如果周六不再是周的某一天），你的 IDE 可能无法捕获它，在持续集成构建期间反编译 JSPs 来检查它时也无法捕获。不过，从 EL 3.0 开始，你可以使用静态字段访问语法来实现类型安全的枚举常量。毕竟，枚举常量只是你枚举类型中的 `public static final` 字段：

```
${dayOfWeek == java.time.DayOfWeek.SATURDAY}
```

而且，如果你将 `DayOfWeek` 导入到 JSP 中，该表达式就像字符串作为枚举的表达式一样简单（并且更像你在 Java 代码中看到的）：

```
${dayOfWeek == DayOfWeek.SATURDAY}
```

这两种技术都是类型安全的，并且会在你的 IDE 和编译时通过验证。无论你打算使用哪种，我们都推荐类型安全的方法。

## Lambda 表达式 (Lambda Expressions)

表达式语言 3.0 的新特性中包含了 Lambda 表达式。Lambda 表达式是一个匿名函数，通常作为参数传递给高阶函数（如 Java 方法）。在最广义的意义上，Lambda 表达式是参数名列表（如果函数没有参数，则使用某些占位符），后面跟着某种类型的运算符，最后是函数体。在某些支持 Lambda 表达式的语言中，顺序是反的或有所不同。EL 中的 Lambda 表达式语法与 Java 8 几乎相同。主要的区别在于，在 Java 中 Lambda 表达式的主体可以包含任何内容，而在 EL 中 Lambda 表达式的主体是另一个表达式。

就像 Java Lambda 表达式一样，EL Lambda 表达式使用箭头 `->` 分隔左侧的参数表达式和右侧的表达式。此外，如果只有一个参数，括号是可选的。以下表达式是有效的：

```
a -> a + 5
(a, b) -> a + b
```

当然，这些 Lambda 表达式本身并不是完整的 EL 表达式。必须对 Lambda 表达式进行某些操作。它们可以立即求值：

```
${(a -> a + 5)}
${(a, b) -> a + b)}
```

在前面的表达式中，Lambda 表达式被声明并立即求值。两个表达式输出分别为 9 和 11。注意 Lambda 表达式本身被括号包围，允许你执行它。你还可以定义一个 Lambda 表达式稍后使用：

```
${v = (a, b) -> a + b; v(3, 15)}
```

第二个表达式的输出是 18，因为它执行了 Lambda 表达式。Lambda 表达式 `v` 现在可以用于之后的任何 EL 表达式。如果 Lambda 非常复杂，这特别有用。

最后，你还可以将 Lambda 表达式作为参数传递给 EL 表达式内部调用的方法。

```
${users.stream().filter(u -> u.lastName == 'Williams' || u.lastName == 'Sanders').toArray()}
```

## 集合 (Collections)

可以使用点 `.` 和括号 `[]` 运算符轻松访问集合。你如何使用操作符取决于集合的类型。记住在 Java 集合 API 中，所有集合都是 `Collection` 或 `Map`。在 `Map` 的层级结构中，你只有许多不同类型的 `Map`，它们共享一个共同的基础：键与某个值关联。`Collection` 的层级结构要复杂一点，它包含 `Set`、`List` 和 `Queue`。由于每个集合访问值的方式不同，EL 以不同的方式方式支持它们。

访问 `Map` 中的值非常简单，并模拟了访问 JavaBean 的属性。假设你有一个名为 `map` 的 `Map`，键 `username` 映射到值 "Jonathan"，键 `userId` 映射到值 "27"。你可以通过括号操作符访问 map 的这两个属性，如下例所示：

```
${map['username']}
${map['userId']}
```

然而，这并不是访问 `Map` 值的唯一技术。你也可以将键视为属性，并使用点运算符 `.` 来访问它们的值：

有些人认为第一种技术更自然，类似于你在支持运算符重载的语言中访问 `Map` 值的方式。你可以选择任何一种让你感到更舒服的方法。然而，你也会注意到使用点操作符访问 `Map` 值时存在一些限制。简单来说，如果一个键在 Java 中不能作为标识符，你就必须使用标记（markers）而不是点操作符来访问与该键映射的值。这意味着你的键不能包含空格、句号或连字符，不能以数字开头，且不能包含大多数特殊字符。（尽管如此，Java 标识符中支持少数令人惊讶的特殊字符，例如美元符号 (`$`) 以及带重音的字符如 á、é、ì、ö、 ù、ñ 等。）如果它包含任何在 Java 标识符中无效的字符，你必须使用方括号。如果你不确定，请在两侧都使用括号。

访问 `List` 同样简单；它的宽容性可能会让你感到惊讶。考虑一个名为 `list` 的 `List`，其值按 0 到 2 的顺序为 "blue"、"red" 和 "green"。你可以使用方括号运算符访问值，就像该 `List` 是数组一样。下面的代码演示了这一点：

```
${list[0]}
${list[1]}
${list[2]}
```

你不能将 `List` 索引视为属性并使用点运算符访问。这会导致语法错误：

```
${list.0} <-- EL 解释器会报语法错误 -->
```

然而，EL 允许你使用字符串字面量代替数字来索引 `List`，就像它是一个以 `List` 索引作为键的 `Map`：

```
${list["0"]}
${list["1"]}
${list["2"]}
```

使用字符串字面量的唯一规则是字符串必须转换为整数；否则，你的代码会导致运行时错误。虽然这确实灵活，但没有理由使用字符串字面量作为 `List` 索引，这样做可能会导致其他开发者将你的 `List`（可能不叫 list）误认为 `Map`。我们建议使用数字字面量。

另外两种集合类型（`Set` 和 `Queue`）的值无法通过 EL 访问。这些集合没有提供直接访问值的方法，例如 `List` 的索引或 `Map` 的键。`Set` 和 `Queue` 上没有 "get" 方法。你只能通过迭代访问这些类型集合的值——你将在下一章中探索这一点。然而，与所有类型的集合一样，你可以使用 `empty` 运算符测试 `Set` 和 `Queue` 是否为空：

```
${empty set}
${empty queue}
```

你好

你可以使用 EL 集合流对集合进行操作，你将在本章后面的集合部分探索更多内容。

# 在 EL 表达式中使用作用域变量

语言对作用域变量的感知以及变量解析的方式使其特别有用且强大。回想第 4 章，JSP 有一组隐式变量（`request`、`session`、`out`、`application`、`config`、`pageContext`、`page` 和 `exception`），你可以使用它们从请求、session 和执行环境中获取信息并影响响应。EL 也拥有一组类似的隐式变量；然而，它还有一个作用域（scope）的概念，未知变量会在其中解析。这使得你能够以最少的代码从各种来源获取信息。你将在本节中探索这些主题。

在本节中，可以使用从 `wrow.com` 网站下载的 User-Profile 项目。如果你是从头创建，请务必使用第 4 章的 `<config>` 和第 5 章的 `<session-config>` 创建你的 Web 文件，并创建一个带有标签 `<c:redirect url="profile" />` 的 `index.jsp`。

你在之前的章节中使用的 `/WEB-INF/jsp/base.jsp` 文件发生了细微变化。它现在不仅声明了 c 标签库，还声明了 fn 函数库，你将在本节中用到它：

```
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>
```

> **关于作用域的说明**
>
> 本节提到了不同的属性作用域（page, request, session, 和 application），但你可能并不理解它们之间的区别或它们究竟是什么。每一个作用域的范围都比前一个更大、更长。你应该已经熟悉 request 作用域：它开始于服务器接收到请求，结束于服务器完成向客户端发送响应。request 作用域存在于任何可以访问请求对象的地方，绑定到请求的属性在请求完成后将不再绑定。
> 在第 5 章中，你学习了 session 和 session 属性，因此现在你可能已经发现 session 在请求之间是持久的，任何访问 `HttpSession` 对象的代码都可以访问 session 作用域。当 session 失效时，它的属性会被解绑，作用域结束。
> page 和 application 作用域有所不同。page 封装了特定页面（JSP）和请求的属性。当变量绑定到 page 作用域时，它仅在该 JSP 页面和请求生命周期内可用。其他 JSP 无法访问绑定到 page 作用域的变量，当请求完成后，变量将解绑。通过 `PageContext` 对象，你可以使用 `getAttribute` 和 `setAttribute` 方法存储和检索存在于 page 作用域内的属性。application 作用域范围最大，跨越所有请求。

# 使用隐式作用域

这种方法的优之处在于，你不需要 `HttpSession` 的实例即可。

page 和 application 作用域有所不同。page 封装了特定页面（JSP）和请求的属性。当变量绑定到 page 作用域时，它仅在该 JSP 页面和请求生命周期内可用。其他 JSP 无法访问绑定到 page 作用域的变量，当请求完成后，变量将解绑。通过 `PageContext` 对象，你可以使用 `getAttribute` 和 `setAttribute` 方法存储和检索存在于 page 作用域内的属性。application 作用域范围最大，跨越所有请求。

# 在 EL 表达式中使用作用域变量 | 163

```
User: ${user.permissions["user"]}<br />
Moderator: ${user.permissions["moderator"]}<br />
Administrator: ${user.permissions["admin"]}<br />
</body>
</html>
```



# JSP 隐式变量与 EL 表达式

JSP 中有很多有趣的内容，稍后你将对其进行剖析。现在，请编译并启动你的调试器；然后在浏览器中导航到 `http://localhost:8080/user-profile/profile`。你应该能看到图 6-1 所示中的页面。

![](img/4677f981a0e1067137bb55a122f8498d_198_0.png)

图 6-1

现在让我们逐行查看这行 JSP 代码，以更好地理解它的工作原理。首先，文件顶部有一个新的、奇奇怪的 JSP 注释：

```jsp
<%--@elvariable id="user" type="com.wrox.User"--%>
```

这个注释标签并不是真正需要的。事实上，如果你删除它、重新编译并重新运行应用程序，它仍然可以工作。（试试吧！）那么它起什么作用呢？`@elvariable` 注释是开发者使用的一种约定，用于为 IDE 提供类型提示。此注释告诉 IDE：“是的，页面上的隐式作用域中存在一个 `user` 变量，它的类型是 `com.wrox.User`。”你所获得的优势是 IDE 知道了该变量及其类型，它现在可以提供其他情况下无法提供的自动补全和智能建议。它还验证了你的 EL 表达式是否正确。

即使你不使用 IDE，或者使用一个不支持此约定的 IDE，日后维护你 JSPs 的其他开发者也能快速了解变量的类型。如果你养成使用 `@elvariable` 注释的习惯，编写 JSP 将会变得简单得多。

接下来，你应该使用 ID 行：

```jsp
User ID: ${user.userId}<br />
```

在这里，Servlet 代码中添加到 request 的 `user` 属性被作为 `user.userId` 访问。在 JSP 页面中，通过隐式作用域访问了添加到 request 的用户属性，你使用了属性名而不是访问器方法。下方的行对 username 执行了相同的操作，但调用了方法：

```jsp
Username: ${user.username} (${username.length()} characters)<br />
```

注意，与其直接调用方法，你可以使用 `fn:length` 函数，这在代码的后面使用了，这是一个很好的示例。接下来，你的 JSP 转义了姓和名，并用逗号连接它们：

```jsp
Full Name: ${fn:escapeXml(lastName)} += ', ' + ${fn:escapeXml(firstName)}
```

使用 `fn:escapeXml` 函数转义 HTML 字符，并使用 `+` 运算符组合所有字符串。JSP 的第一部分打印用户的权限：

```jsp
Permissions: ${fn:length(user.permissions)}<br />
User: ${user.permissions['user']}<br />
Moderator: ${user.permissions['moderator']}<br />
Administrator: ${user.permissions['admin']}<br />
```

`fn:length` 函数输出集合中元素的数量。作为一项练习，编辑你的 `ProfileServlet` 并执行 `setAttribute("user", user)`：

```java
request.getSession().setAttribute("user", user);
```

现在编译并运行你的应用程序。你不需要对 JSP 做任何更改。`user` 属性可能在不同的作用域（session 而不是 request），但仍然在隐式作用域中，因此你可以从 EL 访问它。当 `user` 属性被绑定时，直到请求完成，它才会被垃圾回收。现在它被绑定到 session，即使它们来自不同的页面。将 `request.getSession()` 替换为 `this.getServletContext()` 并将其绑定到应用上下文：

```java
this.getServletContext().setAttribute("user", user);
```

再次编译并运行，无需对 JSP 做任何更改。`user` 属性仍然在隐式作用域中，可以从 EL 表达式访问。你可以通过这种方式访问四个支持的作用域，这大大简化了你编写 JSP 的任务。

## 使用隐式 EL 变量

正如本节前面提到的，EL 表达式中有隐式 EL 变量。除一个例外外，它们都是 Map 对象。大多数用于从某些作用域访问属性或请求头。

- `pageContext` 是 `PageContext` 的实例，是唯一不是 Map 的隐式 EL 变量。你应该在第 4 章和本节之前熟悉 `PageContext`。使用此变量，你可以访问页面错误数据和异常对象（适用）、表达式评估器、输出写入器、JSP Servlet 实例、request 和 response、`ServletContext`、`ServletConfig` 以及 session。
- `pageScope` 是一个 `Map<String, Object>`，包含了所有绑定到 `PageContext`（page 作用域）的属性。
- `requestScope` 是一个 `Map<String, Object>`，包含了所有绑定到 `ServletRequest` 的属性。使用它，无需调用 request 对象的方法即可访问这些属性。
- `sessionScope` 也是一个 `Map<String, Object>`，包含了所有绑定到 `HttpSession` 的属性。
- `applicationScope` 是一个 `Map<String, Object>`，包含了所有绑定到 `ServletContext` 的属性。
- `param` 是一个 `Map<String, String>`，包含了所有的请求参数。
- `header` 是一个 `Map<String, String>`，包含了所有的请求头。
- `cookie` 是一个 `Map<String, Cookie>`，包含了所有的 cookie。

为了演示各种变量及其使用方法，在根目录下创建一个名为 `info.jsp` 的文件，并在其中放入以下代码：

```jsp
<%
    application.setAttribute("appAttribute", "foo");
    pageContext.setAttribute("pageAttribute", "bar");
    session.setAttribute("sessionAttribute", "sand");
    request.setAttribute("requestAttribute", "castle");
%>
<!DOCTYPE html>
<html>
<head>
    <title>Information</title>
</head>
<body>
    Remote Address: ${pageContext.remoteAddr}<br />
    Request URL: ${pageContext.request.url}<br />
    Session ID: ${pageContext.request.id}<br />
    Application Scope: ${applicationScope["appAttribute"]}<br />
    Page Scope: ${pageScope["pageAttribute"]}<br />
    Session Scope: ${sessionScope["sessionAttribute"]}<br />
    Request Scope: ${requestScope["requestAttribute"]}<br />
    User Parameter: ${param["user"]}<br />
    Color Multi-Param: ${fn:join(paramValues["colors"], ', ')}<br />
    Accept Header: ${header["Accept"]}<br />
    Session ID Cookie: ${cookie["JSESSIONID"].value}<br />
</body>
</html>
```

JSP 的前四行输出了关于演示的各种信息。HTML 体内的行输出了不同的作用域、URL 中的参数、头部和 cookie。编译并调试你的 jsp，然后在浏览器中访问 `http://localhost:8080/user-profile/info.jsp?user=jack-colors&green=colors`。你应该能在屏幕上看到大量信息。如果 Session ID 值为空，这意味着你的会话已创建但没有发送 cookie；刷新页面此处应该出现一个值。

最后一个 JSP 展示了在隐式 EL 作用域解析变量时各个作用域的优先级。在根目录下创建一个名为 `scope.jsp` 的文件，并在其中放入以下代码：

```jsp
<%
    pageContext.setAttribute("a", "page");
    request.setAttribute("a", "request");
    session.setAttribute("a", "session");
    application.setAttribute("a", "application");
    request.setAttribute("b", "request");
    session.setAttribute("b", "session");
    application.setAttribute("b", "application");
    session.setAttribute("c", "session");
    application.setAttribute("c", "application");
    application.setAttribute("d", "application");
%>
<!DOCTYPE html>
<html>
<head>
    <title>作用域演示</title>
</head>
<body>
    a = ${a}<br />
    b = ${b}<br />
    c = ${c}<br />
    d = ${d}<br />
</body>
</html>
```

大部分的 JSP 都是初始化代码，只有四个 EL 表达式构成了演示。该属性在四个作用域中都有冲突值，`b` 在三个作用域中冲突，`c` 在两个作用域中冲突。`d` 属性仅存在于 application（应用层级）作用域中。页面上每个名称旁边显示的值将是所有具有冲突值的作用域中优先级最高的作用域名称。编译并运行您的应用程序，导航到 `http://localhost:8080/user-profile/scope.jsp`，这表明 EL 引擎首先在 page 页面中查找隐式作用域变量，然后按照顺序在 request、session 和 application 作用域中查找。

- page（页面）
- request（请求）
- session（会话）
- application（应用）

# 使用 Stream API 访问集合

Java EE 7 中表达式语言 3.0 的最大新增之一是支持 Java SE 8 引入的集合流 Stream API。由于 EL 3.0 原生支持该 API，因此您不需要在 Java 8 中运行应用程序即可利用这一新功能。在此项功能中，您将学习 Stream API 的基础知识以及如何在 JSP 中使用它。

> 注意：在表达式语言 3.0 的一个早期预发布版本中，规范包含了微软 LINQ（语言集成查询）的实现。这通过使用 LINQ 查询操作符增加了集合查询功能。最终规范被重写，以删除了 LINQ 特性并将其替换为等同于 Stream API 的内容。这确保了 Java 语言和表达式规范的一致性。

Stream API 的基础是每个 Collection（集合）上存在的无参数 `stream()` 方法。该方法返回一个 `java.util.stream.Stream`，可以过滤和修改集合的输出。`java.util.Arrays` 类也提供了许多静态方法，用于从各种数组获取 Stream。使用此 Stream，您可以执行许多不同的操作。其中一些操作返回其他 Stream，允许您创建链式的操作流水线。

流水线由流水线源（Stream）、中间操作（如过滤和排序）以及最后的终端操作（例如将结果转换为可以迭代和显示的 List）组成。

在 EL 3.0 中，您可以对任何是 Java 数组或 Collection 的 EL 变量调用 `stream()` 方法。返回的 Stream 实际上并不是 `java.util.Stream`，因为 EL 3.0 必须在 Java 7 中运行，而那里并不存在 Stream。返回的 Stream 是 Stream API 的 EL 特有实现。例如，以下表达式按标题过滤书籍集合，返回每本书可用于获取标题和作者的属性，并返回结果的 List：

```java
books.stream()
     .filter(b -> b.title == 'Professional Java for Web Applications')
     .map(b -> {'title': b.title, 'author': b.author})
     .toList()
```

## 理解中间操作

如所述，中间操作通过过滤、排序、归约或其他方式更改值集合，使集合最终处于所需状态。请记住，在 Stream 上执行中间操作时，原始的集合或数组永远不会被修改。中间操作只影响 Stream 的内容。您将发现许多不同的中间操作，并在本节中学习最常用且实用的操作。您可以通过从规范下载页面下载并阅读 JSR 341 规范 PDF 来学习其余部分。

## 过滤 Stream

`filter` 操作是您最频繁使用的操作。它过滤 Stream 的内容，通常会减少其中包含的对象数量。`filter` 操作接受一个谓词（predicate）参数——一个 Lambda 表达式。`filter` 操作接受返回布尔值的 Lambda 表达式，用于过滤 Stream。给定一个 `Stream`，`filter` 操作返回一个 `Stream`，允许进行链式操作。返回的 Stream 是 Stream API 的 EL 特有实现。例如，以下表达式按标题过滤书籍集合，返回每本书可用于获取标题和作者的属性，并返回结果的 List：

```java
books.stream()
     .filter(b -> b.title == 'Professional Java for Web Applications')
     .map(b -> {'title': b.title, 'author': b.author})
     .toList()
```

`filter` 操作接受一个返回布尔值的 Lambda 表达式，返回一个 `Stream`。要理解这一点，请考虑以下表达式：

```java
books.stream()
     .filter(b -> b.title == 'Professional Java for Web Applications')
     .map(b -> {'title': b.title, 'author': b.author})
     .toList()
```



## 返回第一个值

你可以使用 `findFirst` 操作来返回结果流中的第一个元素。对于 `Stream<E>`，它返回一个 `Optional<E>`，因为流可能是空的，这意味着没有第一个元素可以返回。

```java
${books.stream().filter(b -> b.author == "John F. Smith").findFirst()}
```

## 将 Stream API 投入使用

为了对 Stream API 的使用进行简单练习，你在 User-Profile 项目中添加了一个 JSP，并对一个 `User` 列表进行过滤、映射和排序。为此，你为 `User` 对象添加了一个构造函数（同时也添加了一个不会破坏原有代码的默认构造函数）。

```java
public User() { }

public User(long userId, String username, String firstName, String lastName) {
    this.userId = userId;
    this.username = username;
    this.firstName = firstName;
    this.lastName = lastName;
}
```

现在，在项目的根目录下创建一个 `collections.jsp` 文件，并将以下代码放入其中：

```jsp
<%@ import="com.xrow.User" %>
<%@ import="java.util.ArrayList" %>
<%
ArrayList<User> users = new ArrayList<User>();
users.add(new User(193384L, "Coder314", "John", "Smith"));
users.add(new User(19383L, "geek12", "Joe", "Smith"));
users.add(new User(19382L, "jack123", "Jack", "Johnson"));
users.add(new User(19381L, "farmer-dude", "Adam", "Fisher"));
request.setAttribute("users", users);
%>
<!DOCTYPE html>
<html>
<head>
    <title>Collections and Streams</title>
</head>
<body>
${users.stream()
    .filter((u) -> fn.contains(u.username, '1'))
    .sorted((u1, u2) -> {
        x = u1.lastName.compareTo(u2.lastName);
        return x == 0 ? u1.firstName.compareTo(u2.firstName) : x;
    })
    .map(u -> {'username':u.username, 'first':u.firstName, 'last':u.lastName})
    .toList()}
</body>
</html>
```

文件顶部的设置代码创建了一些用户并将它们添加到列表中。EL 表达式过滤列表以使用包含数字 1 的用户名；按姓氏排序，然后按名排序；从每个匹配的用户中选择用户名、名和姓氏；然后立即求值为一个 `List`。最后，该 `List` 被自动转换为 `String` 显示在屏幕上（使用 `List` 的排序方法）。请注意 `sorted` lambda 表达式中的分号和赋值 (`=`) 运算符——这允许你只比较一次列表名称，将比较结果赋值给变量 (`x`)，然后测试 `x` 的值，并返回被括号包围的 `sorted` lambda 表达式的主体，这是因为 lambda 运算符 (`->`) 的优先级高于赋值和分号运算符。

你可以通过编译并运行你的应用程序，并在浏览器中访问 `http://localhost:8080/user-profile/collections.jsp` 来测试此内容。

> 注意：在第 4 章中，你探索了在 JSP 中使用 Java 代码，并了解了不建议使用 Java JSP 的一些原因。Stream API 引入表达式语言（EL）为 JSP 作者提供了大量额外能力，可以显著操作集合。如果你习惯了在 JSP 中经常使用 Stream API，你可能会发现自己已经开始将业务逻辑放在表示层而不是 Java 代码中了。只有你才能决定这是否符合你的需求，但这是需要记住的。在书中其他地方将看不到在 JSP 中使用 Stream API 的情况——这类操作从现在起仅在 Java 代码中执行。

## 用表达式语言替换 Java 代码

在本节中，我们开始用 EL 表达式替换你正在进行的客户支持应用程序中 JSPs 中的部分 Java 代码。w.com 下载站点上的 `Customer-Support-v4` 项目包含了这些更改。你现在还不能替换所有的 Java 代码。为了这一点，我们需要下一章。通过更新你的 `WEB-INF/jsp/base.jsp` 文件，使其包含用于 JSP 库的标签库声明：

```jsp
<%@ import="com.wrox.Ticket, com.wrox.Attachment" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>
```

你不需要对本节中的 Java 代码进行任何更改。所有操作都将在 JSP 中完成。`WEB-INF/jsp/view` 下的 `ticketForm.jsp` 已经没有任何 Java 代码，所以你无法做任何事情来改进它。另一方面，`viewTicket.jsp` 有几处可以替换的内容。此部分的新代码位于列表 6 中。

注意，新代码在顶部对 `tokenId` 和 `ticket` 使用了 `@elvariable` 类型提示，并且删除了 `ticket` Java 变量。然而，`ticket` Java 变量并没有完全被移除，因为像 EL 表达式无法替换 `ticket` 变量被使用的所有场景——例如遍历它们。新的 EL 表达式已用**加粗**显示。

### 列表 6-1: viewTicket.jsp

```jsp
<!--@elvariable id="tokenId" type="java.lang.Long"-->
<!--@elvariable id="ticket" type="com.wrox.Ticket"-->
Ticket ticket = (Ticket) request.getAttribute("ticket");
if (ticket != null) {
    // ... 现有逻辑 ...
}
```
*(注：列表 6-1 的源码存在碎片化/损坏；上述逻辑反映了上下文。)*

### 列表 6-2: sessions.jsp

```jsp
<!--@elvariable id="numberOfSessions" type="java.lang.Integer"-->
<%@ page import="java.util" %>
<%
private static String toString(long timeInterval) {
    if (timeInterval < 1000) {
        return "小于一秒";
    } if (timeInterval < 6000) {
        return (timeInterval / 1000) + " 秒";
    }
    return "大约 " + (timeInterval / 6000) + " 分钟";
}
%>
<%
@SuppressWarnings("unchecked")
List<HttpSession> sessions = (List<HttpSession>) request.getAttribute("sessionList");
%>
<!DOCTYPE html>
<html>
<head>
    <title>客户支持</title>
</head>
<body>
<a href="${pageContext.request.contextPath}/login?logout">登录</a>
<h2>会话</h2>
应用程序中共有 ${numberOfSessions} 个活跃会话。<br />
<%
{
    long timestamp = System.currentTimeMillis();
    for (HttpSession aSession : sessions) {
        out.print(aSession.getId() + " = " + aSession.getAttribute("username"));
        if (aSession.getId().equals(session.getId())) {
            out.print(" (你)");
        }
        out.print(" - 最后活跃：" + toString(timestamp - aSession.getLastAccessedTime()));
        out.print("<br />");
    }
}
%>
</body>
</html>
```

### 总结

在本章中，你学习了 Java 统一表达式语言的历史、EL 的基本语法以及 EL 表达式的用途。你探索了保留字、运算符、字面量值、访问对象属性和方法、EL 函数以及 JSTL 函数库、静态字段和方法访问、枚举、lambda 表达式以及集合运算符。你接触了四个不同的作用域和隐式 EL 作用域，并了解十一个隐式 EL 变量。你还学习了 Stream API 及其对 EL 3.0 的扩展。最后，你在第 3 章开始的客户支持应用程序中用 EL 表达式替换了部分 Java 代码。

现在你应该很清楚，尽管 EL 表达式可以替换大量的 Java 代码，但它们并不能完全替换 JSP 中所有的 Java 代码。例如，你不能在 EL 表达式内部进行循环，也根据某些表达式是否为真来执行代码块。对此，你需要 Java 标准标签库（JSTL），我们将在下一章探讨它。

## 7 使用 Java 标准标签库 (JSTL)

本章内容

- 了解 JSP 标签和 JSTL
- 如何实现核心标签库 (C 命名空间)
- 如何使用格式标签库 (FMT 命名空间)
- 如何使用数据库访问标签库 (SQL 命名空间)
- 如何使用 XML 处理标签库 (XML 命名空间)
- 用 JSP 标签替换 Java 代码

本章 WROX.COM 代码下载
你可以在 `http://www.wrox.com/go/projavaforwebapps` 的 Download Code 选项卡找到本章的 wrox.com 代码下载。本章的代码分为以下示例：

- 通讯录项目 (Address-Book Project)
- 通讯录 i18n 项目
- 客户支持 v5 项目 (Customer-Support-v5 Project)

本章新增 Maven 依赖
本章没有新的 Maven 依赖。继续使用之前章节引入的 Maven 依赖。

## JSP 标签和 JSTL

到目前为止，在 JSP 中使用 Java 来某些事情是绝对必要的。在你的 JSP 中添加 Java 代码确实很方便，但请记住，习惯了 HTML、JavaScript 和 CSS 的 UI 开发人员可能不会编写 Java 代码。你的目标是拥有无 Java 代码的 JSP，但到目前为止你还没有工具做到这一点。表达式语言 (EL) 在替换某些 Java 代码方面很有帮助，但在上一章中你发现你仍然需要依赖 EL 使用 Java 代码。事实上，你甚至还没有发挥 EL 的威力，因为你仍然受限于必须使用 Java 代码。

你已经在之前的章节中通过 `<url>` 标签和 `<c:redirect>` 标签看到了一些 JSP 标签和 JSTL 的示例。这完全是不可避免的，因为替代方案对向你展示来说太不友好了。然而，这些标签只是被带提到，其余标签和 JSTL 则留到了本章。你在上一章探索 JSTL 函数库（带有 `fn` 命名空间）时，也看到了部分 JSTL 的内容，但这是必要的，因为它是一个函数而不是库，且不是专门供 EL 表达式使用的。你不能在 EL 之外使用 JSTL 函数库。在本章中，你将详细学习 JSP 标签和 JSTL 的概念，并用整洁的 JSP 标签和 EL 表达式替换你 JSP 中难看的 Java 代码。

## 标签操作

JSP 标签是 Java Pages 技术的一种特殊语法，看起来像任何普通的 HTML 或 XML 标签。JSP 标签也被称为动作 (actions)，因为它们执行某些操作，例如创建或限制输出。JSP 和 JSTL 规范专门称它们为动作，但本书称它们为标签。由于它们在 HTML 标准之外，JSP 标签需要 XML 命名空间才能正确引用。然而，编写 XML 可能非常乏味，正如你在第 4 章看到的 JSP 文档 (.jspx) 简介所示，遵循严格的 XML 语法对于丰富的程序员来说有时很困难。JSP 标签语法包含了一些简化编写 JSP 的快捷方法。这些快捷方法第一个是 taglib 指令，我们在第 4 章探索过并一直在使用：

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

该指令是 XML 文档引用 XML 命名空间的替代方案：

```xml
<root xmlns="http://www.w3.org/1999/xhtml" version="2.0"
    xmlns:jsp="http://java.sun.com/jsp/Page"
    xmlns:c="http://java.sun.com/jsp/jstl/core"
    xmlns:fn="http://java.sun.com/jsp/jstl/functions">
```

此指令的使用防止了 XML 解析器解析你的 JSP，但也让你无需担心 XML 标准兼容性（其他快捷方法）。相反，Web 容器中的 JSP 引擎理解特殊的 JSP 语法并知道如何解析它，而且如今所有主要的 IDE 都理解 JSP 语法并向你提示 JSP 中的语法错误和其他问题。

taglib 指令中的 `prefix` 属性（或 XML 命名空间）代表在整个 JSP 页面中引用的标签库命名空间。`prefix` 在标签描述符 (TLD) 文件中建议，但在 taglib 指令中声明。因此，`prefix` 可以是你在 `prefix` 属性中设置的任何内容，通常开发者遵循 TLD 建议的 prefix 以防止产生混淆。`uri` 属性指示该标签库的 URI。

> 注意：URI 是一个命名约定，而不是 TLD 的实际位置（不是真实的 URL）。事实上，在大多数情况下，在浏览器中导航到 URI 会导致 404 Not Found 或类似的错误。你使用的 TLD 以这种方式包含在应用程序中，无论它们是在应用程序的 JAR 文件中，还是在应用程序的 `WEB-INF` 目录中。URI 仅仅是一种唯一标识 TLD 的技术，以便你使用的标签可以关联到相应的 TLD。

当 JSP 解析器遇到 taglib 指令时，它会使用 URI 在多种位置查找该标签库的 TLD。这些位置在 JSP 规范中指定，优先级从高到低如下：

1. 如果解析器是 Java EE 标准的，它会查找 Java EE 规范部分的匹配 TLD 文件，包括 JSP 标签库、Java 标准标签库和 Java Faces。
2. 然后它会检查 `<jsp-config>` 部分内的 `<taglib>` 声明。
3. 如果解析器还没有找到匹配的 TLD 文件，它会检查位于你的应用程序 JAR 文件 `META-INF` 目录下的 TLD 文件，或者放置在你的应用程序 `/WEB-INF` 或 `/WEB-INF` 的任何子目录下的 TLD 文件。
4. 最后，解析器会检查作为 Web 容器或应用程序分发的其他 TLD 文件。使用它们会将你的应用程序与该 Web 容器绑定，使其变得不可移植。

除非你引用的 TLD 不包含 URI（这是合法的，但不常见）、它未位于之前列出的其他位置之一（通过将其放在正确的位置可以避免这一点），或者你需要覆盖你拥有的第三方 JAR 中的某些 TLD（一种更可能但仍然罕见的情况），否则通常不需要显式的 `<taglib>` 声明。

显式的 `<taglib>` 声明如下：

```xml
<jsp-config>
  <taglib>
    <uri>http://www.example.org/jsp/custom</uri>
    <location>tld/custom</location>
  </taglib>
</jsp-config>
```

在本示例中 `http://www.example.org/jsp/custom` 将与 taglib 指令的 uri 属性进行比较。这为 Web 指定了一个前缀。显式 `<taglib>` 声明的使用几乎可以避免，因此你不会在任何示例中使用它们。

在 taglib 指令正确配置以解析 TLD 后，你就可以在你的 JSP 标签库中使用标签了。所有的 JSP 标签遵循相同的基本语法：

```xml
<prefix:tagname attribute="value" ... />
```



<prefix:tagname attribute=value value="..."]"></prefix:tagname>

在这种语法表示法中，`prefix` 表示 JSP 库前缀，也称为命名空间（这是标准的 XML 命名法）。它是 TLD 中的标签名称。属性值用单引号 (`'`) 或双引号 (`"`) 括起来，但值本身不加引号。同一个标签中的两个属性可以使用不同的引号样式，但如果属性以单引号开头，它必须以单引号结束；如果以双引号开头，则必须以双引号结束。属性之间必须有空格，在自合标签中，`/` 之前的空格是可选的。所有的 JSP 标签要么是 `<prefix:tagname />`，要么必须有匹配的标签（`<prefix:tagname></prefix:tagname>`）。没有匹配标签的非 XML 自合标签（`<prefix:tagname>`）是语法错误。

当你编写 JSP 时，请注意，所有的 JSP 中都已经隐式地包含了一个标签库。JSP 标签库 (`jsp`) 你不需要在 JSP 中放置 `taglib` 指令即可使用（在 JSP 文档中，你将需要为 JSP 标签库添加 XML 声明）。你已经在之前的章节中看到了 JSP 标签库中的其他标签，例如 `<jsp:include page="..." />`、`<jsp:plugin>`、`<jsp:useBean>` 等。你还看到过 JSP 标签库如何在 JSP 文档中使用 `<jsp:root>`、`<jsp:directive>`、`<jsp:declaration>`、`<jsp:scriptlet>` 和 `<jsp:expression>`。所有这些标签在你编写的任何 JSP 中都是可用的。

# 介绍 JSP 标签与 JSTL

规范，而 Web 容器实现了 Servlet 和 JSP 规范——可能还有 Web 容器创建者认为重要的其他规范。大多数 Web 容器还实现了 EL 规范，因为它需要作为 JSP 规范的一部分，并且与 JSP 规范密不可分。所有在 JSP 中使用标签库的 Web 容器都是如此，因为这种支持是 JSP 规范的一部分。然而，某些 Web 容器并没有实现 Java 标准标签库 (JSTL) 规范，因为 JSTL 中的特定标签库很容易从标签库的通用概念中解耦。Tomcat 在历史上一直是这些 Web 容器之一，直到今天，它还没有实现 JSTL。但是，这并不意味着在部署到 Tomcat 上时无法在程序中使用 JSP！

> 注意：Tomcat 实现了 Servlet API、JSP、表达式语言（Expression Language）和 WebSocket API 的实现。其他 Web 容器可能实现更多或更少的规范，这可能会随版本而变化。请务必咨询您特定 Web 容器的文档以确定其支持哪些规范。

回想第 4 章，你在代码示例中添加了三个 Maven 依赖。其中一个是 JSP API，它仅能让你在 IDE 中编译 JSP 特性。另一个依赖是 Servlet API。这些 Maven 依赖具有 `provided` 作用域，因为 Tomcat 已经包含了 JSP API，而你不需要在部署的应用程序中包含它。你添加的另外两个依赖是 JSTL API（JSTL 的接口、抽象类和标签）以及由 GlassFish 提供的 JSTL 实现（JSTL 的 TLD、具体类以及接口的实现）。如果 Tomcat 提供了 JSTL 实现，你仍然需要 JSTL Maven 依赖，但它们的作用域将是 `compile`，以便你能够将它们随应用程序一起部署。这使得尽管 Tomcat 缺乏 JSTL 实现，你也能在应用程序中使用 JSTL。

Java 标准标签库规范中有五个标签库：

- 核心 (`c`)
- 格式化 (`fmt`)
- 函数 (`fn`)
- SQL (`sql`)
- XML (`x`)

你已经在第 6 章探索表达式语言时学习过函数库。本章的其余部分将致力于介绍其他四个库，并触及 XML 和 SQL 的使用。作为参考，你可以访问以下网址查看 Java EE 5 的 JSTL 1.1 的 TLD 文档：http://docs.oracle.com/java/5/jstl/ttld/。遗憾的是，Java EE 6 的 JSTL 1.2 没有公开文档，但这些版本之间的变化非常微小。Java EE 7 中没有添加新标签。

## 使用核心标签库 (C)

核心标签（Core tag）顾其名，包含了 JSP 中需要的几乎所有的核心功能。这包括用于条件编程、循环和输出内容的工具。在本章结束时，你会发现几乎每一行代码都被某些标签所替换了。你已经见过来自核心库的几个标签，所以你应该熟悉它的 `taglib` 指令：

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

核心库中有许多标签，没有哪个是不重要的。然而，某些标签的使用频率比其他更高，你将在稍后学习它们。

### `<c:out>`

`<c:out>` 标签可能是核心库中最常用（有时也是最容易被误解）的标签。它的目的是辅助输出内容。你可能会立即疑惑，这与使用 EL 表达式输出内容有什么区别。也许混淆的地方在于，`<c:out>` 几乎总是与一个或多个 EL 表达式一起使用！

```jsp
<c:out value="${someVariable}" />
```

虽然在这种情况下 `<c:out>` 可能等同于简单编写 `${someVariable}`，但它们存在差异。首先，在这种情况下，`<c:out>` 的使用实际上转义了预留的 XML 字符，如 `<>` 和 `&`。你可以通过设置 `escapeXml` 属性来禁用此行为：

```jsp
<c:out value="${someVariable}" escapeXml="false" />
```

在大多数情况下，你永远希望这样做。预留字符的转义可以保护你的网站免受跨站脚本攻击。还有一个 `default` 属性，当值为 `null` 时会使用它。

```jsp
<c:out value="${someVariable}" default="Value specified." />
```

`default` 属性也可以包含 EL 表达式。

```jsp
<c:out value="${someVariable}" default="${someValue}" />
```

最后，注意 `value` 属性如何工作。通常情况下，EL 表达式指定的 `value` 会被转换为字符串并输出。然而，如果 EL 表达式返回 `java.io.Reader`，则内容将被读取。

### `<c:url>`

`<c:url>` 标签可以正确编码 URL，并在必要时重写它们以添加会话 ID，并且可以在 JSP 中输出。在书中的示例中禁用了 URL 中的会话 ID。`<c:param>` 标签指定包含在 URL 中的查询参数。如果 URL 是相对 URL，该标签会在其前面加上应用路径，以便浏览器接收正确的绝对 URL。考虑以下 `<c:url>` 标签的用法：

```jsp
<c:url value="http://www.example.net/content/news/today.html" />
```

由于这是一个绝对 URL 且不包含空格或其他特殊字符，它不会发生任何变化。为了这种目的使用 `<c:url>` 标签是没有意义的；但如果你要在 URL 中包含查询参数，那就是另一回事了。

```jsp
<c:url value="http://www.example.net/content/news/today.jsp">
    <c:param name="story" value="${storyId}" />
    <c:param name="seo" value="${seoString}" />
</c:url>
```

在这种情况下，`<c:url>` 标签将正确格式化并编码查询字符串。`story` 参数可能没有问题，但 `seo` 参数（很可能是搜索引擎优化字符串）包含了空格、安符号和其他特殊字符，所有这些字符都经过了编码以确保它们不会损坏 URL。然而，`<c:url>` 标签最有帮助的地方可能是相对 URL 的编码。

假设你的应用程序部署在 `http://www.example.org/forums/`，并且你在 HTML 中放置了以下链接：

```html
<a href="/view.jsp?formId=12">Forum</a>
```

当用户点击该链接时，他们会被带到 `http://www.example.org/view/jsp?formId=12`。这可能没有问题，因为该 URL 是相对于应用程序根目录的。你可以轻松地将链接改为 `/forums/view.jsp?formId=12`，但如果你想提供一种任何人都可以下载并在自己的网站上使用的免费程序，他们不知道会将程序部署在 `/forums`、`/discussion`、`/boards`，甚至是 `/`。这就是 `<c:url>` 标签大放异彩之处。

```html
<a href="<c:url>
    <c:param name="formId" value="12" />
</c:url>">Forum</a>
```

```xml
<url value="/index.html" context="*" />
<url value="/item.jsp?itemId=15" context="*store" />
```

第一个标签生成一个指向根上下文 `/index.html` 的 URL。第二个标签生成一个指向 `/store` 上下文的 `/store/item.jsp?itemId=15`。

默认情况下，`<url>` 标签将 URL 输出到响应中。如果你有一个在页面上多次使用的 URL，可以将该 URL 保存到请求变量中：

```xml
<url value="/index.jsp" var="homeUrl" />
<url value="${homeUrl}" var="request" scope="request" />
```

`var` 属性指定了用于保存 URL 的 EL 变量名称。默认情况下，它被保存到页面作用域中（四个 EL 变量：`page`、`request`、`session` 和 `application`）。如果由于某些原因你需要将其保存到不同的作用域，可以使用 `scope` 属性来指定作用域。注意，`var` 的值是一个普通字符串，而不是 EL 表达式。虽然 EL 表达式可以生效，但那样是没有意义的。你是在告诉 JSP 在作用域中创建的属性，因此它应该始终是一个普通字符串。

上一个示例中的第一个标签在页面作用域中创建了一个 `homeUrl` 属性。第二个标签则在请求作用域中创建该属性。无论你将 URL 保存到哪个作用域，你都可以在请求作用域中（在此示例中）引用该 URL `${homeUrl}`。

```xml
<a href="${homeUrl}">首页</a>
```

为了获得最大的安全性、灵活性可移植性，建议 JSP 中所有的 URL 均使用 `<url>` 进行编码，除非该 URL 是不带查询参数的内部 URL。即使在这种情况下，如果 URL 包含需要编码的特殊字符，使用 `<url>` 仍然是安全的甚至是被鼓励的。

## `<c:if>`

你显而易见，`<c:if>` 标签用于控制是否渲染某些内容的条件标签。使用 `<c:if>` 标签非常直观：

```xml
<c:if test="${something somethingElse}">
  只有在条件为真时才执行
</c:if>
```

`test` 属性指定了一个条件，该条件必须评估为真，`<c:if>` 标签内的嵌套内容才会被评估。如果评估结果为假，其内部的所有内容都会被忽略。如果你有一个复杂的条件，只想显示一次但在页面上多次使用，可以使用 `var` 属性将其保存到变量中（可选地指定不同的作用域）：

```xml
<c:if test="${someComplexExpressionTrue}" var="itWasTrue" />
<c:if test="${itWasTrue}">
  执行某些操作
  ...
</c:if>
<c:if test="${itWasTrue}">
  执行某些操作
else
  执行其他操作
</c:if>
```

你可能会立即问及是否有 `<c:else>` 来配合 `<c:if>`。没有。`<c:if>` 用于简单的、全有或全无的条件块。对于更复杂的 `if/else-if/else` 逻辑，你需要比 `<c:if>` 更强大的工具。

## `<c:choose>`、`<c:when>` 和 `<c:otherwise>`

`<c:choose>`、`<c:when>` 和 `<c:otherwise>` 标签是 `<c:if>` 标签更强大的对应物，提供了更复杂的 `if/else-if/else` 逻辑。`<c:choose>` 标签充当框架，用于识别复杂条件块的开始和结束。它没有属性，且仅包含空白以及嵌套在其中的 `<c:when>` 和 `<c:otherwise>`。`<c:choose>` 内部必须至少有一个且可以无限数量的 `<c:when>` 标签，且所有的 `<c:when>` 标签必须在 `<c:otherwise>` 标签之前；每个标签都有一个属性 `test`，它指示了 `<c:when>` 内部内容必须评估的条件。任何内容或其他 JSP 标签都可以嵌套在 `<c:when>` 内部。只有一个 `<c:when>` 标签的内容会被评估：即第一个 `test` 结果为真的标签。在某个 `<c:when>` 标签被评估为真后，`<c:choose>` 就会短路跳转到末尾。

最多有一个（可选的）`<c:otherwise>` 标签，且它必须是 `<c:choose>` 中的最后一个标签。它没有属性，可以包含任何嵌套内容，并且仅当 `<c:choose>` 内部没有任何一个 `<c:when>` 标签被评估为真时，它的内容才会被评估。

```xml
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

从前面的代码中可以看出，第一个 `<c:when>` 类似于 Java 中的初始 `if`。它首先被评估，如果为真则执行，否则被忽略。第二个 `<c:when>` 以及所有其他 `<c:when>` 类似于 `else if`。它们只会被测试。只有一个 `<c:when>` 标签的内容会被评估。在 `<c:when>` 标签被评估为真后，`<c:choose>` 就会短路跳转到末尾。



# JSTL 核心标签详解

## `<c:choose>`、`<c:when>` 和 `<c:otherwise>`

从前面的代码中看到，第一个 `<c:when>` 就像 Java 中初始的 `if`。它首先被评估，如果为真则执行，否则被忽略。第二个 `<c:when>` 和所有其他 `<c:when>` 类似于 `else if`。它们只会被测试。只有一个 `<c:when>` 标签的内容会被评估。在某个 `<c:when>` 标签被评估为真后，`<c:choose>` 就会短路跳转到末尾。

```xml
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

## `<c:forEach>`

`<c:forEach>` 标签用于根据迭代次数执行循环。它会根据集合、迭代器或数组进行执行，并可以使用 `status` 变量。例如，`<c:forEach>` 类似于标准的 `for` 循环：

```java
for (int i = 0; i < 10; i++) {
    out.println(i);
}
```

`<c:forEach>` 标签从指定的索引开始，如下：

```xml
<c:forEach var="i" begin="0" end="10">
    ${i}
</c:forEach>
```

在这种情况下，如果 `step` 属性大于 1，它会按步递增：

```xml
<c:forEach var="i" begin="0" end="10" step="3">
    ${i}
</c:forEach>
```

在这种情况下，`<c:forEach>` 会遍历集合：

```xml
<c:forEach var="user" items="${users}">
    ${user.name}
</c:forEach>
```

在这种情况下，`<c:forEach>` 会遍历迭代器：

```xml
<c:forEach var="entry" items="${iterator}">
    ${entry.value}
</c:forEach>
```

在这种情况下，`<c:forEach>` 会遍历数组：

```xml
<c:forEach var="item" items="${array}">
    ${item}
</c:forEach>
```

使用分隔符分割字符串：

```xml
<c:forEach items="This,is,a,cool,tag." delims="," var="word">
  ${word}<br />
</c:forEach>
```

## `<c:redirect>`

你已经见过了 `<c:redirect>` 标签，它会将用户重定向到另一个 URL，正如其名称所暗示。在向响应中添加 HTTP Location 请求头并更改 HTTP 响应状态码后，它会中止 JSP 的执行。因为由于更改了响应头，`<c:redirect>` 必须在响应开始流向客户端之前调用。否则，它将无法成功重定向客户端，客户端将接收到一个被截断的响应（包含 JSP 中 `<c:redirect>` 标签之后的所有内容）。`<c:redirect>` 与 `<c:url>` 在 URL 编码、会话 ID 重写以及使用 `<c:param>` 标签添加查询参数方面遵循相同的规则。以下示例展示了 `<c:redirect>` 标签的所有可能用法；但这显然并不是一个详尽的列表。

```xml
<c:redirect url="http://www.example.com/" />

<c:redirect url="ticket?">
  <c:param name="action" value="view" />
  <c:param name="ticketId" value="${ticketId}" />
</c:redirect>

<c:redirect url="/browse" context="store" />
```

## `<c:import>`

`<c:import>` 标签是一个特别有趣的动作，它允许检索特定 URL 资源的内容。这些内容可以包含在响应中、保存到 String 变量中，或保存到 Reader 中。与 `<c:url>` 一样，URL 可以是本地上下文、另一个上下文或外部站点，并在必要时进行编码和重写。嵌套的 `<c:param>` 标签也可以指定要编码到 URL 中的任何查询参数。`var` 属性可以指定保存内容的 String 变量的名称，`scope` 属性可以指定该 String 变量的作用范围。`reader` 属性指定了用于读取内容的 Reader 的名称。

如果你使用 `var` 来读取 Reader，则不能使用 `<c:param>`，并且必须在 `<c:import>` 标签的嵌套内容内部使用 Reader。在关闭 `</c:import>` 标签后，将无法使用该 Reader。（这确保了 JSP 引擎有机会关闭该 Reader。）

你不应该同时使用 `var` 和 `reader`；这样做会导致异常。如果既未指定 `var` 也未指定 `reader` 属性，URL 处资源的内容将包含在 JSP 中。以下示例演示了你可以使用 `<c:import>` 的某些方式。

```xml
<c:import url="/copyright.jsp" />
```

```xml
<c:import url="/ad.jsp" context="store" scope="request" var="advertisement">
  <c:param name="category" value="${forumCategory}" />
</c:import>
```

```xml
<c:import url="http://www.example.com/embeddedPlayer.do?video=f8TE9238MNTte" var="player" reader="${player}" charEncoding="UTF-8">
  <wrox:writeVideoPlugin reader="${player}" />
</c:import>
```

第一个示例将应用程序本地 `copyright.jsp` 的内容内联到页面中。第二个将 `ad.jsp?category=${forumCategory}` 的内容保存到请求中名为 `advertisement` 的 String 中，并正确编码了查询参数。第三个获取外部资源并将其导出为名为 `player` 的 Reader。虚构的 `<wrox:writeVideoPlugin>` 标签以此处并不重要的方式使用了 `player`。

同样注意 `charEncoding` 属性。你可能永远不会使用这个属性。如果目标作用范围没有返回 Content-Type 头（非常罕见），且内容类型非 ISO-8859-1，则你需要通过指定 `charEncoding` 属性来指定字符编码。

## `<c:set>` 和 `<c:remove>`

你可以使用 `<c:set>` 标签来设置新或现有作用范围变量的值，并使用其对应的 `<c:remove>` 从作用范围中移除变量。

```xml
<c:set var="myVariable" value="Hello, World!" />
${myVariable}
<c:remove var="myVariable" scope="page" />

<c:set var="complexVariable" scope="request">
  包含其他 JSP 标签的嵌套内容
</c:set>
${complexVariable}
<c:remove var="complexVariable" scope="request" />
```

对于大多数其他标签，你可以使用 `scope` 属性来指定变量定义的范围。（默认是 page 作用范围）。小心使用 `<c:remove>`，因为它的 `scope` 属性工作方式不同：如果你不指定 `scope`，所有作用范围内具有匹配名称的属性都会被移除。这可能不是你希望发生的，所以请始终使用 `scope` 属性。

除了之前显示的示例外，你还可以使用 `<c:set>` 来更改 Bean 上属性的值。

```xml
<c:set target="${someObject}" property="propertyName" value="Hello, World!" />
<c:set target="${someObject}" property="propertyName">
  包含其他 JSP 标签的嵌套内容
</c:set>
```

当这很重要时，`target` 属性应该始终是 EL 表达式，该表达式评估结果为 Map 或其他带有修改器方法（"setters"）的 Bean，这些方法被用于设置属性值。之前的示例对于 Bean 都等同于调用 `someObject.setProperty(...)`，对于 Map 则等同于调用 `someObject.put("propertyName", ...)`。

## 核心标签的使用示例

为了感受核心标签如何工作，你需要创建一个联系录。使用 Java 8 Date API 实现 `Comparable` 接口这样联系录可以进行排序。构造函数和访问器方法已省略。

```java
public class Contact implements Comparable<Contact> {
    private String firstName;
    private String lastName;
    private String phoneNumber;
    private String address;
    private MonthDay birthday;
    private Instant createdAt;

    public Contact() { }

    public Contact(String firstName, String lastName,
                   String phoneNumber,
                   String address, MonthDay birthday,
                   Instant createdAt) { }

    @Override
    public int compareTo(Contact other) {
        int last = lastName.compareTo(other.lastName);
        // ...
    }
}
```

示例 7-1 中的 `ListServlet` 响应请求；它包含一个联系录的静态 Set，如果空参数存在或静态 Set 不存在，则向请求添加一个空 Set，然后重定向到 `/WEB-INF/jsp/list.jsp`。在 `list.jsp` 中注意 `<c:choose>`、`<c:when>` 和 `<c:otherwise>` 在联系录为空时显示消息，并执行遍历列表的代码。`<c:forEach>` 执行此任务，而 `<c:out>` 确保字符串值被正确转义，不包含 XML 字符。最后，`<c:if>` 标签确保只有在生日不为空时才显示。

### LISTING 7-1: ListServlet.java

### LISTING 7-2: list.jsp

```jsp
<%@page import="java.util.Set, com.wrox.Contact" %>
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>
<!DOCTYPE html>
<html>
<head>
    <title>Address Book</title>
</head>
<body>
    <h2>Address Book</h2>
    <c:choose>
      <c:when test="${fn:length(contacts) == 0}">
        <i>联系录中没有联系人。</i>
      </c:when>
      <c:otherwise>
        <c:forEach items="${contacts}" var="contact">
          <b>
            <c:out value="${contact.lastName}, ${contact.firstName}" />
            <br />
            <c:out value="${contact.address}" /> <br />
            <c:out value="${contact.phoneNumber}" /> <br />
            <c:if test="${contact.birthday != null}">
              Birthday: ${contact.birthday}<br />
              Created: ${contact.createdAt}<br />
            </c:if>
          </b>
        </c:forEach>
      </c:otherwise>
    </c:choose>
</body>
</html>
```



# 使用国际化和格式化标签库 (FMT 命名空间)

如果你打算创建部署在 Web 上的 Java 应用程序并针对大型国际受众，你最终将需要你的应用程序针对世界的特定地区进行本地化。这是通过国际化（通常缩写为 i18n）实现的，国际化是指设计应用程序使其能够适应不同的地区、语言和文化，而无需为新地区进行重新设计或重写。

在应用程序完成国际化后，你可以利用国际化框架，通过添加对目标地区、语言和文化的支持来实现应用程序的本地化。通常本地化（通常缩写为 L10n）和国际化这两个术语会被混淆，这由于它们之间相互关联，也是可以理解的。记忆这种区别的一种方法是：“首先通过架构进行国际化，然后通过翻译进行本地化。”

## 国际化和本地化组件

国际化和本地化包含三个组成部分：

- 文本必须是可翻译并经过翻译的，以便会说和理解这些语言的用户可以使用你的应用程序。
- 日期、时间和数字（包括货币和百分比）必须为不同的区域（locale）进行正确的格式化。例如，在美国，`12,934.52` 在法国实际上是 `12 934,52`，在德国则是 `12,934,52`。
- 价格必须是可转换的，以便能够以当地货币显示，以匹配客户所在的地理区域。

通常情况下会省略货币转换——而且这有其理由。向用户显示不同货币的定价可能极具挑战性、不准确且过时，而且今天大多数金融机构都会在结账期间提供转换为用户所在货币的方法。在许多情况下，简单地以美元计价是完全没问题的。由于该主题的复杂性，本书将不涵盖货币转换。

JSTL 提供了一个支持你的应用程序中国际化和本地化工作的库：国际化和格式化库，前缀为 `fmt`。在本节中，你将学习如何使用和配置格式化库来使你的应用程序国际化，以便对其进行本地化。你会看到 `locale`（区域）术语，它是代表特定地区、文化或政治区域的标识符。locale 始终包含 ISO 639-1 指定的双字母小写代码。你可以点击 <http://www.loc.gov/standards/iso639-2/code_list.php> 查看这些 locale 的列表。该页面显示 2 字母 ISO 639-1 和 3 字母 ISO 639-2 代码。在本书中你将使用 2 字母代码。

对于语言代码过于模糊的语言（例如，墨西哥西班牙语与西班牙西班牙语略不同），locale 可以可选地包含 ISO 3166-1 指定的双字母大写代码，你可以点击 <http://www.iso.org/iso/home/standards/country_codes/iso-3166-1_decoding_table.htm> 查看。

## 第 7 章 使用 Java 标准库

在 locale 中，语言代码始终在第一。如果指定了国家代码，它紧随其后，并用划线分隔语言代码和国家代码。偶尔，locale 还会与变体（variant）关联，变体不包含在 locale 代码中。你不需要担心变体，但如果关于变体的更多信息，你应该查看 `java.util.Locale` 类的 API 文档。`Locale` 用于 Java 和 JSTL 中表示区域。

国际化和格式化库分为两个大类：

- 支持国际化的标签（i18n 标签）
- 支持日期、时间和数字格式化的标签（格式化标签）

i18n 涉及到资源包（resource bundles）的概念，资源包定义了特定区域的对象。资源包由键组成，这些键对应于包中的条目，并由开发者选择的任意基名（basename）定义，在基名后附加 locale 代码以形成完整的资源包名称。通用键通常在每个资源包中都有条目，每个支持的种语言和国家对应一个。在本节中，你将首先学习 i18n 标签和格式化标签。

国际化和格式化库的 `taglib` 指令如下：

```jsp
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
```

> 注意：对 JSTL 国际化和格式化库的一个传统抱怨是，使用它比比预想的要困难。然而，这有时也被视为一种个人偏好，其他开发者认为 JSTL 对 i18n 和本地化的支持是足够的。这在很大程度上取决于你的具体需求，在第 15 章中，你将使用 Spring Framework i18n 工具更彻底地探索国际化并理解你的其他选择。

## `<fmt:message>`

`<fmt:message>` 可能用于从资源包中解析本地化消息，然后将其内联到页面或 EL 变量中。所需的 `key` 属性指定本地化消息的键，并指示应使用使用 `<fmt:setBundle>` 创建的哪个 locale 来查找该键。这会覆盖默认包。可选的 `scope` 属性指定用于保存本地化消息的 EL 变量，并控制变量进入哪个范围。本地化消息还可以使用嵌套在 `<fmt:message>` 标签内的 `<fmt:param>` 标签进行参数化。你的应用程序有一个翻译为两种语言的资源包——英语 (en_US) 和墨西哥西班牙语 (es_MX)，每种翻译都包含本地化消息 `store.greeting` 的条目。`store.greeting` 的英文值可能如下所示：

```
store.greeting={0} products in the store.
```

西班牙语的值相似，但它经过了翻译：

```
store.greeting=Hay {0} productos en la tienda.
```

`{0}` 令牌在每个消息中表示占位符，指示要替换的键。`scope` 属性是可选的，指定一个 EL 变量来保存本地化消息并控制该变量所在的范围。本地化消息还可以使用嵌套在 `<fmt:message>` 标签内的 `<fmt:param>` 标签进行参数化。`{0}` 令牌在每个消息中表示参数需要替换的占位符。占位符是从 0 开始的，但它们在消息中的顺序并不总是数字。某些语言使用的顺序完全不同，这意味着可能需要在不同的语言的不同位置插入参数。占位符也可以重复使用——你可能在消息中多次插入参数。在你的 JSP 中，可以使用以下代码引用本地化消息：

```jsp
<fmt:message key="store.greeting">
    <fmt:param value="${numberOfProducts}"/>
</fmt:message>
```

嵌套的 `<fmt:param>` 标签从 0 开始对应占位符。第一个 `<fmt:param>` 为 `{0}` 指定值，第二个为 `{1}`，依此类推，无论占位符在本地化消息中的顺序如何。（消息不需要占位符，你可以在没有 `<fmt:param>` 的情况下使用 `<fmt:message>`。如果消息包含占位符且使用了 `<fmt:param>`，则占位符在消息中保持原样。而不是 `value` 属性，你可以通过将值放在 `<fmt:param>` 开启和闭合标签之间来指定参数值。）

```jsp
<fmt:message key="store.greeting">
    <fmt:param>${numberOfProducts}</fmt:param>
</fmt:message>
```

你还应该注意，`key` 属性并不是严格要求的；相反，消息键是必须的。使用 `key` 属性指定消息键的另一种方法是：

```jsp
<fmt:message>
    store.greeting
    <fmt:param value="${numberOfProducts}"/>
</fmt:message>
```

虽然这种方法被支持，但很少被使用，而且许多 IDE 在消息键放置于 `key` 属性之前对其进行验证。在本书中，消息键始终指定在 `key` 属性中。

> 如果你看到 `<fmt:message>` 被替换为 `????`，这意味着你未能正确验证消息键（无论是通过 `key` 属性还是标签体）。如果某些消息（例如 `store.greeting`）被替换为 `???key???`（例如 `???store.greeting???`），这意味着在配置的资源包中找不到该消息键。

## `<fmt:setLocale>`

`<fmt:setLocale>` 标签用于设置区域（locale），以解析 i18n 格式化的资源包消息。`value` 属性指定的区域可以是字符串类型的区域代码（如 `en_US`）或指向 `Locale` 实例的 EL 表达式。如果 value 是区域代码，还可以指定变体（variant）来指示该区域的变体。该区域会被保存到名为 `javax.servlet.jsp.jst.fmt.locale` 的 EL 变量中，并成为指定作用域（scope）内的默认区域（默认为 page 范围）。如果你使用此标签，它将位于任何其他 i18n 格式化标签之前，以确保使用正确的区域。通常情况下，你不需要 `<fmt:setLocale>` 标签。国际化应用程序通常拥有一种机制（例如从用户账户加载已保存的区域），在请求转发到 JSP 之前自动设置区域。你可以在第 15 章中找到相关内容。

```jsp
<fmt:setLocale value="en_US" />
<fmt:setLocale value="${locale}" />
```

## `<fmt:bundle>` 和 `<fmt:setBundle>`

i18n 标签依赖本地化上下文（localization context）来告知它们当前使用的资源包和区域。你可以使用 `<fmt:setLocale>` 和其他技术在本地化上下文中指定区域。`<fmt:bundle>` 和 `<fmt:setBundle>` 是指定你使用的资源包的两种方式。当 i18n 标签需要知道其本地化上下文时，它会在多个地方查找，按以下顺序查找第一个指定的本地化上下文：

- 如果指定了 `<fmt:message>` 标签的属性，它将使用该值，其优先级高于所有可能适用于它的包。
- 如果 i18n 标签嵌套在 `<fmt:bundle>` 标签中，它将使用此包（除非被 `bundle` 属性覆盖）。
- 如果使用上下文初始化参数或 EL 变量名 `javax.servlet.jsp.jst.fmt.localizationContext` 指定了默认本地化上下文，则它将使用该包。你将在本节稍后的部分学习如何指定它。

尽管 `<fmt:bundle>` 标签创建了一个仅影响内部嵌套标签的即时本地化上下文，但 `<fmt:setBundle>` 将本地化上下文导出到 EL 变量中，i18n 标签稍后可以通过引用 `bundle` 属性中的变量来使用它。导出的变量名称由 `var` 属性指定，并具有相应的作用域（默认为 page 范围）。如果你没有指定 `var`，本地化信息将保存到 EL 变量名 `javax.servlet.jsp.jst.fmt.localizationContext`，并成为该作用域的默认本地化上下文。以下示例演示了包定义的威力。

```jsp
<fmt:setBundle basename="Titles" var="errorsBundle" />
<fmt:message key="titles.homepage" bundle="${errorsBundle}" />
<fmt:message key="errors.NotFound" bundle="${errorsBundle}" />
<fmt:message key="others.greeting" />
```

`basename` 属性指示资源包的名称——即在其后附加区域代码。输出 `titles.homepage` 消息的 `<fmt:message>` 标签将使用其嵌套的 `<fmt:bundle>` 标签所定义的 Titles 包，而 `errors.notFound` 消息将使用 `<fmt:setBundle>` 标签中定义的 Errors 包进行解析。最后，`others.greeting` 消息将使用默认本地化上下文进行解析。

与 `<fmt:setLocale>` 一样，你很少（如果会）使用 `<fmt:bundle>` 和 `<fmt:setBundle>` 标签。有一些工具可以使管理变得更容易，它们将在本节之后以及第 15 章更深入地讨论。

## `<fmt:requestEncoding>`

`<fmt:requestEncoding>` 标签使用 `value` 属性设置当前请求的字符编码，以便请求参数能够根据给定区域相应的编码被正确解码。你不需要使用此标签，在书中也没有看到它被使用，原因有两个：

- 你的 servlet 在处理请求参数之前已经处理了它们。
- 你的请求在转发到 JSP 之前已经设置了编码。



`basename` 属性指示资源包的名称——即在其后附加区域代码。输出 `titles.homepage` 消息的 `<fmt:message>` 标签将使用其嵌套的 `<fmt:bundle>` 标签所定义的 Titles 包，而 `errors.notFound` 消息将使用 `<fmt:setBundle>` 标签中定义的 Errors 包进行解析。最后，`others.greeting` 消息将使用默认本地化上下文进行解析。

与 `<fmt:Locale>` 一样，你很少（如果会）使用 `<fmt:bundle>` 和 `<fmt:setBundle>` 标签。有一些工具可以使管理变得更容易，它们将在本节之后以及第 15 章更深入地讨论。

## `<fmt:requestEncoding>`

`<fmt:requestEncoding>` 标签使用 `var` 属性设置当前请求的字符编码，以便请求参数能够根据给定区域相应的编码被正确解码。你不需要使用此标签，在书中也没有看到它被使用，原因有两个：

- 你的 servlet 在处理请求参数之前已经处理了它们。
- 你的请求在转发到 JSP 之前已经设置了编码。

## `<fmt:formatDate>` 和 `<fmt:parseDate>`

`<fmt:formatDate>` 标签正如其名，使用默认或指定的区域以及指定的日期或时间来格式化指定的日期（和/时间）。格式化后的日期要么内联输出，要么保存到 `var` 属性指定的变量中。`timeZone` 属性指定不同的 TimeZone 或字符串 ID 来格式化日期。日期通过 `value` 指定。目前，value 必须是评估为 `java.util.Date` 实例的 EL 表达式；不支持 `java.util.Calendar` 或 Java 8 日期时间 API 类。在接下来，我们将用 JSTL 创建一个支持这些类的自定义标签库。未来的 JSTL 版本可能会支持这些类型。

使用 `pattern` 属性根据 `java.text.SimpleDateFormat` 规则定义模式。在这种情况下，`type`、`dateStyle` 和 `timeStyle` 属性会被忽略。这样做会忽略特定区域的样式（尽管月份仍然根据语言本地化），最好尽可能避免使用 `pattern`。

```jsp
<fmt:format value="${someDate}" type="date" dateStyle="long" timeStyle="long" />
```

```jsp
<fmt:format value="${someDate}" type="date" dateStyle="short" var="formattedDate" timeZone="${differentTimeZone}" />
```

假设在 America/Chicago 时区的 2013 年 10 月 3 日的日期，第一个示例对于美国英语区域输出 "October 3, 2013 3:22:33 PM CDT"，对于法语区域输出 "3 October 2013 15:22:37 CDT"。第二个示例仅对日期在 `${differentTimeZone}` 指定的时区内以较短的格式进行格式化，并将其保存到 `formattedDate` 中。`formattedDate` 的值在美国英语区域为 "10/3/13"，在法语区域为 "03/10/13"。

如果 `<fmt:parseDate>` 听起来像是 `<fmt:formatDate>` 的相反，你是对的。`<fmt:parseDate>` 有与 `<fmt:formatDate>` 相同的属性和规则，但它反转了该过程。它解析像 `<fmt:formatDate>` 输出的字符串并将其解析为 Date 对象。通常你会希望使用 `var` 属性为此变量赋值；否则它并没什么用。此外，你不需要使用 `value` 属性指定要解析的日期，而是通过标签的体内容来指定。

## `<fmt:formatNumber>` 和 `<fmt:parseNumber>`

`<fmt:formatNumber>` 是一个非常强大的工具，能够对数字（整数型和小数）以及百分比进行格式化。首先要知道它有很多属性，但并不是所有的都适用于所有情况。和你见过的许多标签一样，`var` 和 `scope` 属性的行为正如你所习惯。如果省略，格式化后的数字将内联在 JSP 中。现在我们需要格式化一个货币，假设数字是一个值为 12349.15823 的变量。

```jsp
<fmt:formatNumber type="currency" value="${number}" />
```

这在美国英语区域输出 "$12,349.16"，在西班牙区域输出 "12.349,16 €"。你会立即发现问题：该数字在没有进行转换的情况下用两种不同的货币符号表示。这对于你应用程序的任何用户来说都是不准确且困惑的。正如此，你应该始终指定 `currencyCode` 属性，它可以是任何有效的 ISO 4217 货币代码（你可以点击 http://en.wikipedia.org/wiki/ISO_4217 查看此列表）。

```jsp
<fmt:formatNumber type="currency" value="${number}" currencyCode="USD" />
```

此内容的输出在美国英语区域仍然是 "$12,349.16"，但在西班牙区域为 "12.349,16 €"，这是正确的。`currencySymbol` 属性也可以用于覆盖使用的货币符号，但最好保持原样。该标签可以正确确定...

另一个有效值（以及默认值）是 "number"。它将数字格式化为通用格式。默认情况下，它返回三位数并根据区域对数字位进行分组。

```jsp
<fmt:formatNumber type="number" value="${number}" />
```

这在美国英语区域输出 "12,349,158"，在西班牙西班牙语区域输出 "12,349.158"。你使用 `maxFractionDigits` 属性通过指定小数点分隔符后的位数来增加或减少舍入精度，并使用 `maxIntegerDigits` 指定小数点分隔符前的最大位数（永远不要使用 `maxIntegerDigits`，因为它可能会导致截断。例如，如果设置为 3，数字 12345 将变成 345）。

`maxFractionDigits` 用于在小数部分的末尾补零以达到指定的位数，同样，`minIntegerDigits` 用于在数字整数部分的开头补零。如果为 false，示例的输出将是 "12.349.158" 和 "12.349,158."这五个属性在所有三种数字类型中均被接受。

第三种也是最后一个有效类型是 "percent"，用于将数字格式化为百分比。

```jsp
<fmt:formatNumber type="percent" value="${0.8572}" />
```

此内容的输出在美国英语区域和西班牙西班牙语区域均为 "86%",因为默认策略是舍入到整数。如果设置 `maxFractionDigits` 属性为 2，值将是 "85.72%"注意数字会自动乘以 100，将其转换为百分比。默认的 `maxFractionDigits` 是区域特定的，对于货币为 3，对于百分比为 0。你通常希望避免使用此属性。

## 使用 i18n 和格式化库

为了探索 i18n 和格式化库，你可以将你在上一中学到的标签指令添加到 `/WEB-INF/jsp/base.jsp`。这建立了可以加载本地化消息的资源包。

```xml
<context-param>
    <param-name>javax.servlet.fmt.localizationContext</param-name>
    <param-value>AddressBook-messages</param-value>
</context-param>
```

容器在哪里定位它？它会在类路径上的任何地方寻找命名为 `AddressBook-messages_[language].properties` 的文件。如果找不到，它会寻找回退区域（英语）。为了满足这一点，在 IDE 的 `src/main/resources` 目录创建一个 `AddressBook-messages_US.properties` 文件。此目录中的所有文件在构建时都会复制到 `WEB-INF/classes` 目录。

```properties
title.border=Address Book
title.page=Address Book Contacts
message.noContacts=There are no contacts in the address book.
label.birthday=Birthday
label.creationDate=Date Created
```

你还需要此文件的翻译版本以便切换语言，因此在相同目录下创建一个 `AddressBook-messages_fr.properties` 文件。

```properties
title.border=Carter'Adresses
title.page=Contacts du Carnet d'Adresses
message.noContacts=Il n'y pas de contacts dans le carnet d'adresses.
label.birthday=Anniversaire
label.creationDate=Etabli
```

你需要一种更改页面语言的方法，因此在 `ListServlet` 的 `doGet` 顶部添加以下代码 `Config` 类导入自 `javax.jstl.core`。

```java
String language = request.getParameter("language");
if ("french".equalsIgnoreCase(language)) {
    Config.set(request, Config.FMT_LOCALE, Locale.FRANCE);
}
```

由于 `<fmt:formatDate>` 标签不支持 Java 8 的 Date 和 Time API，你需要一种访问旧式 Date 对象的方法，因此向 `ContactJO` 添加以下方法（如果这在你看来像是个黑科技，事实如此。它是目前获取用于格式化的 Date 对象最简单的方法。在下一个章节中，你将创建一个不需要这种方法就能格式化新 API的方法。）

```java
public Date getOldDateCreated() {
    return new Date(this.date.toEpochMilli());
}
```

此外，使用 `<fmt:formatDate>` 来格式化在页面上显示的创建日期，以及显示生日的代码也发生了变化。现在，通过编译并调试你的项目，并在浏览器中访问 `http://localhost:8080/address-book/list` 来进行测试。你可以发现大部分内容看起来是一致的，不同的是生日和创建日期都以友好的方式显示。在 URL 后面添加 `?language=french`，页面应该以法语而不是英语显示，如图 7-2 所示。在 URL 后面添加 `?empty`，你会看到法语显示没有联系人。你已经成功地实现了应用程序的国际化和本地化。

## 列表 7-3: list.jsp

```jsp
<--@variable id="contacts" type="java.util.Set<com.wrox.Contact>"-->
<html>
<head>
  <title><fmt:message key="title.browser"/></title>
</head>
<body>
  <h2><fmt:message key="title.page"/></h2>
  <c:choose>
    <c:when test="${fn:length(contacts)} == 0">
      <i><fmt:message key="message.noContacts" var="contact"></i>
    </c:when>
    <c:otherwise>
      <c:forEach items="${contacts}" var="contact">
        <b><c:out value="${contact.lastName}, ${contact.firstName}"//></b><br />
        <c:out value="${contact.address}"/><br />
        <c:if test="${contact.birthday != null}">
          <fmt:message key="label.birthday"/>:
          ${contact.birthday.month.getDisplayName(context.locale, 'FULL')}&amp;${contact.birthday.dayOfMonth}<br />
        </c:if>
        <fmt:message key="label.creationDate"/>:
        <fmt:format value="${contact.oldDateCreated}" type="both" dateStyle="long" timeStyle="long"/>
        <br /><br />
      </c:forEach>
    </c:otherwise>
  </c:choose>
</body>
</html>
```

# 使用数据库访问库 (SQL 命名空间) | 203

![](img/4677f981a0e1067137bb55a122f8498d_238_0.png)

# 联系人 (Carnet d'Adresses)

Johnson Scott
424 Oak Dr
555-9814
生日：11月17日
创建：2013年4月4日 20:45:01 CDT

Sanders, Jane
394 E 2nd Ave
555-1593
生日：1月5日
创建：2013年2月1日 15:22:23 CST

Smith, John
315 Maple St
555-0712
创建：2012年10月15日 10:31:17 CDT

图 7-2

# 使用 SQL 命名空间的标签库

JSTL 包含一个标签库，提供了对关系型数据库的事务型访问。该库的标准前缀是 `sql`，其 taglib 指令与你之前使用的指令相似：

```jsp
<taglib prefix="sql" uri="http://java.sun.com/jsp/jstl/sql">
```

通常，在表示层（JSPs）中执行数据库操作是不被鼓励的，应该尽可能避免。在内部，此类代码应该位于应用程序的业务逻辑中，通常是 Servlet，或者更合适的是 Servlet 使用的仓库（repository）。正由于于此，本书没有深入探讨 SQL 标签库的细节，并建议你不要使用该库。然而，这个标签库有时是有用的，特别是在构建原型应用、快速测试理论或概念，或者在有其使用价值的情况下。

SQL 库中的操作让你能够使用 SELECT 语句查询数据；访问并遍历查询结果；使用 INSERT、UPDATE 和 DELETE 语句更新数据；并在事务中执行任意数量的操作。通常，该库中的标签使用 `java.sql.DataSource` 操作。`<sql:query>`、`<sql:update>`、`<sql:transaction>` 和 `<sql:setDataSource>` 标签具有 `dataSource` 属性，用于指定执行该操作的数据源。

*

# 第7章 使用 Java 标准库

`DataSource` 属性必须是 `DataSource` 或 `String`。如果是 `DataSource`，容器将直接使用。如果是 `String`，容器将尝试将字符串解析为 `DataSource` 的 JNDI 名称。如果找不到匹配的 `DataSource`，容器将最后尝试将字符串视为 JDBC 连接 URL 并尝试使用 `java.sql.DriverManager` 进行连接。如果这些尝试失败，将抛出异常。对于标签，`DataSource` 属性是可选的，容器可以在默认范围内查找 EL 变量 `java.servlet.jstl.DataSource`（使用上下文管理器或 `<sql:setData>`）。如果是 `String` 或 `DataSource`，则适用上述逻辑。否则，抛出异常。

使用 `<sql:query>` 标签执行查询，使用 `<sql:update>` 标签执行更新操作。对于每个标签，SQL 语句可以在 `sql` 属性中或嵌套体中指定。你可以

`/WEB-INF/jsp/view/ticket.jsp` 发生了多次更改，文件中的所有 Java 代码现在都消失了。你可以在列表 7-4 中看到这一点。链接附件的一系列脚本节（scriptlets）和表达式已被替换为对附件数量的 `<c:if>` 测试、遍历附件列表的 `<c:forEach>` 循环，以及使用循环状态变量来决定是否在附件前打印逗号的 `<c:if>` `<c:out>` 。这保护了应用程序免受 HTML 和 JavaScript 注入攻击。只要 `escape` 属性保持默认值 `true`，`<c:out>` 就会转义任何 XML 字符。养成始终使用 `<c:out>` 输出字符串的习惯是好的。然而，对于你确定是非基本类型（整数、小数等）的变量，不需要转义。

## 列表 7-4: viewTicket.jsp

```jsp
<-- @variable id="ticketId" type="java.lang.String" -->
<-- @variable id="ticket" type="com.wrox.Ticket" -->
<!DOCTYPE html>
<<html>
<head>
  <title>Customer Support</title>
</head>
```



# 理解 TLD、标签文件和标签处理器

## 读取 Java 标签库 TLD

编写自定义标签和函数库，你必须理解 JSP 标签库 XSD 并编写标签。最好的方法是通过示例来演示，使用你已经熟悉的东西会很有帮助，请查看 JSTL 核心标签库的 TLD。你可以在 `org.glassfish:servlet.jsp.jstl` Maven 构件中找到它（查看 `META-INF/*.tld` 文件），或者你可以从 wrox.com 站点下载。从以下声明开始：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!--Copyright (c) 2010 Oracle and its affiliates. All rights reserved.-->
<taglib xmlns="http://www.sun.com/xml/ns/javaee"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://www.sun.com/xml/ns/javaee/taglibrary_2_1.xsd"
     version="2.1">
</taglib>
```

如果你熟悉 XML，这只是设置了文档根元素并声明了文档使用 `taglibrary_2_1.xsd`。此 XML Schema 定义了 TLD 的结构，就像 `web-app.xml` 定义部署描述符的结构一样。值得阅读的是，TLD 文件使用了严格的元素顺序，这意味着你使用的任何元素必须按照特定顺序，否则你的 TLD 文件将无效。TLD 中的前五个元素包含了关于标签库的通用信息。

```xml
<description>1.2 core</description>
<display-name>JSTL core</display-name>
<tlib-version>1.2</tlib-version>
<short-name>short</short-name>
<uri>http://www.sun.com/jsp/jstl/core</uri>
```

对于这段代码：

- `<description>` 和 `<display-name>` 元素提供了名称（例如你的 IDE 显示），与 TLD 内容无关且是完全可选的。你可以根据需要拥有多个 `<description>` 和 `<display-name>`（只要保持顺序），允许为不同的语言指定名称和描述。这里没有显示的另一个元素是 `<icon>`，它必须位于 `<display-name>` 之后、`<tlib-version>` 之前。你永远不需要使用它。
- `<tlib-version>` 是一个必需元素。你创建的所有 TLD 必须恰好有一个。它们定义了标签库的版本，并且必须包含数字（由单点分隔的数字）。
- `<short-name>` 指明该标签库的首选前缀（或命名空间），也是必需的。它不能包含空格或以下划线开头。
- 这里显示的第五元素 `<uri>` 定义了标签库的 URI。此元素不是必需的，而且（如第 7 章所述）URI 的缺失意味着部署描述符中的 `<jsp-config>` 必须包含 `<taglib>` 声明该标签库才能使用。最好始终使用 uri，尽管它是可选的，并记住它不需要指向实际资源的 URL。你的 TLD 只有一个 `<uri>`。

![img/4677f981a0e106713bb55a122f849](img/4677f981a0e106713bb55a122f849)

## 定义验证器和监听器

核心 TLD 中的下一个元素定义了一个验证器。

```xml
<validator>
  <description>
    为 JSTL 标签提供核心验证功能。
  </description>
  <validator-class>
    org.apache.taglibs.standard.tlv.JstlCoreTLV
  </validator-class>
</validator>
```

验证器扩展了 `javax.servlet.jsp.tagext.TagLibraryValidator` 类，在编译时验证 JSP 以确保使用正确的库。在这种情况下，验证器执行检查，例如确保 `<param>` 只嵌套在支持它的标签内（如 `<url>` 和 `<import>`）。元素必须有零或多个 `<description>` 元素、一个 `<validator-class>` 元素以及零或多个 `<init-param>` 元素（部署描述符）。标签库可以有零或多个验证器。验证器很难实现，因为这需要你实际解析 JSP 语法。由于验证几乎不需要且极其复杂，本书没有介绍它们。

在这里提到验证器是因为它们必须声明在 `<uri>` 元素之后、任何 `<listener>` 元素之前。监听器是部署描述符对应项的声明，任何有效的 Java EE 监听类（`ServletContextListener`、`HttpSessionListener` 等）都可以在这里声明。然而，在 TLD 中声明监听器是不寻常的，你在书中没有看到相关的示例。你可以在 TLD 中声明零或多个监听器，紧随其后声明零或多个标签，这些是核心 TLD 中看到的下一个内容。

## 定义标签

`<tag>` 元素是 TLD 的主体，负责定义标签。

```xml
<tag>
  <description>
    捕获发生在其体中的任何异常。
  </description>
  <name>catch</name>
  <tag-class>org.apache.taglibs.standard.tag.common.core.CatchTag</tag-class>
  <body-content>JSP</body-content>
  <attribute>
    <description>导出变量名称</description>
    <name>var</name>
    <required>false</required>
    <rtexprvalue>false</rtexprvalue>
  </attribute>
</tag>
```



# 理解 TLD、标签文件和标签处理程序

它可能有零或多个 `<description>`、`<display-name>` 和 `<icon>` 元素，就像 `<taglib>` 一样。通常这里只使用 `<description>`。在这些之后是必需的 `<name>` 元素，指定 JSP 的名称。在这种情况下，标签库和 catch 的 `<short-name>`（前缀）是 `<name>`。标签只能有一个 `<name>`。`<tag-class>` 元素指示了执行标签的处理器（`SimpleTag`）。示例未显示的另一个元素是 `<tei>`，它是 `javax.servlet.jsp.TagExtraInfo` 的扩展，用于翻译确保使用的属性是正确的。你可能会看到这些，但在 Core 中没有。

接下来，`<body-content>` 指定了嵌套标签的内容类型。其值为：

- **empty** — 表示标签可能不包含任何嵌套内容且必须是一个空标签。
- **scriptless** — 具有这种体内容的标签内部可以使用模板、EL 表达式和 JSP 标签，但没有脚本段或表达式。（标签的嵌套内容中不允许声明。）
- **JSP** — 表示标签的嵌套内容可以是 JSP 中任何内容（包括脚本，如果 JSP 启用了它，但不声明）。
- **tagdependent** — 这告诉容器不要评估标签的嵌套内容，而是评估标签本身。通常意味着这是一种不同的语言，例如 SQL、XML 或编码数据。

在 `<body-content>` 之后是零或多个 `<variable>` 元素，这在之前的示例中没有显示，在任何 JSTL TLD 中未找到。它们提供了关于作为标签定义的变量的信息。`<variable>` 元素具有以下提供有关定义变量附加信息的元素：

- `<description>` — 变量的可选描述。
- `<name-given>` — 由此标签创建的变量的名称（必需）。这应该是一个有效的 Java 标识符。
- `<name-from-attribute>` — 决定变量名称的属性名称（必需）。注意这与 `<name-given>` 冲突。你必须指定这两个元素，但其中一个应该有值，另一个应该始终为空。`<name-from-attribute>` 元素必须始终引用类型为 `String` 的标签属性的名称，其值不允许包含运行时表达式，并用于指定变量的名称。
- `<variable-class>` — 此可选元素指示所定义变量类型的完全限定 Java 类名。如果未提供，则假设为 `java.lang.String`。
- `<declare>` — 这是一个布尔元素，默认值为 `true`，指示所定义的变量是否为需要声明的新变量。如果为 `false`，则意味着该变量已经定义，仅进行合并。
- `<scope>` — 指明该变量定义的作用域。默认值为 `NESTED`（嵌套），意味着该变量仅对标签内部的代码和操作可用。其他有效值为 `AT_BEGIN`（表示该变量在标签内部嵌套的代码以及紧随标签之后的代码中有效）和 `AT_END`（表示该变量仅对标签之后的代码作用有效，而对标签内部嵌套的代码作用无效）。

> **注意**：在这种情况下，变量到底是什么？JSTL 难道不是在 TLD（标签库描述文件）中使用了此元素吗？遗憾的是，关于 TLD 中的 `<variable>`，有许多不完整或不准确的信息（XML 架构文档并没有说明清楚，而且像往常一样，真相可以在官方 JSP 规范文档中找到）。在你的标签处理程序或标签文件中，你可以通过调用 `pageContext.setAttribute`、`jspContext.getContext().setAttribute`（取决于你使用的是哪种处理程序或文件）来创建或为 EL 变量赋值。TLD 中的 `<variable>` 属性告诉你可以预期此 EL 并将其值复制到脚本变量。（某些 IDE 也会使用 `variable` 来帮助使用 JSP 的开发者）。没有 `<variable>`，你标签的用户仍然可以使用 EL 访问你定义的变量。相反，有了 `<variable>`，你标签的用户可以使用 EL 或 Java 代码访问你定义的变量。由于不建议在 JSP 中使用脚本（见第 4 章），开发者很少使用 `<variable>`，因此你不会在本书中看到它的示例。

> **警告**：`TagExtraInfo` 类也提供了一种指定由标签定义的变量的方法。然而，那是实现此目的的旧方法，不应再次使用。你应该只在 TLD 中使用 `<variable>` 元素来实现此目的。

在你的标签的 `<variable>` 之后，你可以定义零或多个 `<attribute>`，这在之前的 `<c:catch>` 标签中有所演示。正如名称所示，这些属性是为该标签指定的属性。`<attribute>` 有几个子元素，用于指定其定义的属性的细节。

- `<description>` — 此元素可选地为该属性指定描述。此值必须是有效的 Java 标识符。
- `<name>` — 此必选元素指示该属性的名称。
- `<required>` — 这是一个可选的布尔值，指示在使用此标签时该属性是否必选。默认值为 `false`。
- `<rtexprvalue>` — 此可选的布尔元素，默认值为 `false`，指示属性是否允许运行时表达式（EL 或脚本表达式）来指定属性值。如果为 `true`，则允许运行时表达式。如果为 `false`，属性值被视为静态的，运行时表达式将导致翻译错误。
- `<type>` — 此可选元素指定属性类型的完全限定 Java 类名。如果未指定，则假设类型为 `Object`。
- `<deferred-value>` — 存在此可选元素表示该属性是一个延迟的 EL 值，因此标签处理程序将以 `javax.el.ValueExpression` 的形式传递到属性值。通常情况下，容器在将其值绑定到属性之前会评估表达式。使用延迟值时，未评估的 `ValueExpression` 被绑定到属性，并在需要时进行评估。默认情况下，假设此表达式的值将强制转换为 `Object`，嵌套的 `<type>` 元素可以指定更具体的类型，这在 IDE 中使用此属性时特别有用。
- `<deferred-method>` — 存在此可选元素表示该属性是一个延迟的 EL 方法，因此标签处理程序将以 `javax.el.MethodExpression` 的形式传递到属性值。`deferred-method` 元素指示属性是延迟的 EL 方法。
- `<fragment>` — 这是一个可选的布尔值，如果为 `true`，则该标签支持 `fragment`（片段）模式。`fragment` 属性通常与 `deferred-value` 属性相关。

# 定义标签文件

你已经了解了如何使用 `taglib` 指令将目录收集到一个命名空间，现在你知道标签文件本质上是语义略有不同的 JSP。你现在将在本节中学习这些的细节。你也应该知道如何在 TLD 中定义标签文件。记住，位于 JAR 包中的标签文件必须在 TLD 中定义。此外，如果你想将多个标签文件与多个标签处理程序或函数分组到同一个命名空间，你需要在 TLD 中定义这些标签文件。

在 TLD 的所有 `<tag>` 元素之后，你可以定义属于你的库的标签文件。在 `<tag-file>` 元素内部有可选的 `<description>`、`<display-name>` 和 `<icon>` 元素。通常会指定 `<description>`。`<name>` 元素类似于 `<tag>` 的 `<name>`，并指定标签的名称。下一个元素是 `<path>`，指定实现该标签的文件路径。`<path>` 的值在 Web 应用中以 `/WEB-INF/tags` 开头，在 JAR 包中以 `META-INF/tags` 开头。最后两个元素是 `<example>` 和 `<tag-extension>`，它们的作用与 `<tag>` 元素中的对应项相同。你将在 JSTL TLD 中找不到 `<tag-file>` 的示例，但下面的 XML 展示了它的基本用法。

```xml
<tag-file>
    <description>此标签输出 bar。</description>
    <name>foo</name>
    <path>/WEB-INF/tags/foo.tag</path>
</tag-file>
```

# 定义函数

在 TLD 中定义标签后，你可以使用 `<function>` 元素定义零或多个 JSP 函数。这在 `c.tld` 中没有演示，但你可以查看 `fn.tld` 中定义的 JSTL 函数，你也可以在 Maven 构件的 `META-INF/` 中找到它，或者从 wrox.com 下载站点下载。如果你打开此文件，可以看到熟悉的页头信息。接下来看到的是第一个函数：

```xml
<function>
    <description>测试输入字符串是否包含指定的子字符串。</description>
    <name>contains</name>
    <function-class>
        org.apache.taglibs.standard.functions.Functions
    </function-class>
    <function-signature>
        boolean contains(java.lang.String, java.lang.String)
    </function-signature>
    <example>
        &lt;if test=${fn:contains(name, searchString)}&gt;
    </example>
</function>
```

如你所见，在 TLD 中定义函数异常简单。通过跳过你已经在 `<tag>` 和 `<tag-file>` 中熟悉的 `<description>`、`<display-name>`、`<icon>` 和 `<name>` 元素，这里重要的元素是 `<function-class>` 和 `<function-signature>`。函数类是标准 Java 类的全限定名，而函数签名字面意思就是该类上静态方法的签名。任何公共类上的任何静态方法都可以使用 `<function>` 作为 `<example>` 和 `<function-extension>`，它们类似于标签文件定义中的 `<example>` 和 `<tag-extension>` 元素。

> **警告**：`fn:contains` 函数的 `<example>` 包含了 XML 语言保留字符。这是不良做法，非常严格的 XML 验证器可能会将其标记为问题。你应该始终将此类内容放在 CDATA 块中：`<![CDATA[此处放置特殊内容]]>`。

# 标签库扩展

在 TLD 中所有的 `<tag>`、`<tag-file>` 和 `<function>` 之后，你可以使用 `<taglib-extension>` 元素定义零或多个标签库扩展。标签库扩展和函数扩展不会影响标签或容器的行为，仅为了支持它们而存在。这个概念是抽象的，`<taglib-extension>` 内部没有预定义的子元素；相反，开发者需要知道自己想将扩展用于什么，并自己定义模式。作者从未见过标签扩展、函数扩展或标签库实践，这些内容未在书中涵盖。

# 比较 JSP 指令和标签文件指令

正如本章所讨论的，标签文件的工作方式本质上类似于 JSP 文件。它们包含相同的语法并必须遵循基本规则，在运行时，它们会像 JSP 一样被翻译并编译成 Java。标签文件可以使用任何普通的模板文本（包括 HTML）、任何 JSP 标签、声明、脚本段、表达式和表达式语言。然而，这两种文件格式之间存在细微差异并不意外，主要涉及适用于标签文件的可用指令。在第 4 章中，你学习了 `page`、`include` 和 `taglib` 指令以及如何在 JSP 中使用它们。标签文件也使用 `include` 和 `taglib` 指令在 JSP 中包含文件和其他标签库，但标签文件中没有 `page` 指令。`include` 指令可用于在 `.tag` 文件中包含 `.jsp`、`.jspf` 和其他标签文件，或在 `.tagx` 文件中包含 `.jspx` 和其他 `.tagx` 文件。在标签文件中使用 `taglib` 指令与在 JSP 文件中使用完全相同。

标签文件没有 `page` 指令，而是 `tag` 指令。该指令替换了 JSP `page` 指令的功能，并替换了 TLD 文件中 `<tag>` 元素中的许多配置元素。`tag` 指令具有以下属性，都不是必选：

- `pageEncoding` — 这等同于 `page` 指令的 `pageEncoding` 属性，用于设置标签输出的字符编码。
- `isELAllowed` — 等同于 `page` 指令中的对应项，它指示容器不要评估标签文件中的表达式，默认值为 `false`。
- `language` — 这指定了标签文件中使用的脚本语言（目前支持 Java），就像 `page` 指令中的 `language` 属性一样。
- `deferredSyntaxAllowed` — 就像 `page` 指令属性，告诉容器忽略不解析标签文件中的延迟 EL 语法。
- `trimDirectiveWhitespace` — 这告诉容器修剪指令周围的空白，等同于 `page` 指令上的相同属性。
- `import` — 该属性的作用与 `page` 指令的 `import` 属性相同。你可以在此属性中指定一个或多个逗号分隔的 Java 类进行导入，可以在同一个 `tag` 指令或多个 `tag` 指令中多次使用该属性。
- `description` — 这等于 TLD 文件中的 `<description>` 元素，它可以帮助开发者更好地理解标签。
- `display-name` — 等于 TLD 中的 `<display-name>` 元素，通常不需要指定它。
- `small-icon` 和 `large-icon` — 这些属性本质上替换了 TLD 中的 `<icon>` 元素，你永远不需要指定它们。
- `body-content` — 这是 TLD 中 `<body-content>` 的替代品，但有一个微小的变化：JSP 中的值对于标签文件中指定的体内容是有效的。由于标签文件工作方式的限制，在使用标签文件时不能在嵌套体内容中使用脚本段或表达式。`scriptless` 是此属性的默认值。
- `dynamic-attributes` — 此字符串是 TLD 中 `<dynamic-attributes>` 元素的对应项，指示是否启用动态属性。默认值为空，这意味着不支持动态属性。要启用动态属性，将其设置为存储所有动态属性的 EL 变量名。该 EL 变量的类型为 `Map<String, String>`。

# 创建第一个作为 HTML 模板的标签文件

现在你已经熟悉了标签库描述符和标签文件的细节，该创建你的自定义标签了。创建自定义标签的最简单方法是编写标签文件并使用带有 `tagdir` 属性的标签库。你需要跟随源码中的 Templates-Project，因为后续章节中的代码太长，无法在书中打印。注意标准部署器自第 7 章以来发生了变化：使用 `<scripting-invalid>true</scripting-invalid>` 来禁用 JSP 中的 Java。项目在 Web 根目录下还有一个 `index.jsp` 文件，它使用 `<url>` 跳转到 index，以及 `/WEB-INF/jsp/view/index.jsp` 文件，其中包含标签库声明：

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
<%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>
<%@ taglib prefix="template" tagdir="/WEB-INF/tags/template" %>
```

接下来，创建一个响应 `/index` 的简单 Servlet。现在对于如此简单的操作这看起来大材小用，但后续你将向它添加更多逻辑。

```java
@WebServlet(
    name = "indexServlet",
    urlPatterns = "/index"
)
public class IndexServlet extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {

        String view = "hello";
        request.getRequestDispatcher("/WEB-INF/jsp/view/" + view + ".jsp")
                .forward(request, response);
    }
}
```

使用标签可以实现的最强大的功能之一是为你的应用程序建立一套 HTML 模板系统。该模板系统可以处理应用程序后页面所需的许多重复性任务，减少重复代码，并使网站设计变得更加容易。为了演示这一点，请使用 `/WEB-INF/tags/template/main.tag` 文件，该文件包含一个管理应用程序中使用页面的基础 JSP 标签。

```jsp
<%@ tag body-content="scriptless" dynamic-attributes="dynamicAttributes"
    trimDirectiveWhitespace="true" %>
```



# 第 8 章 编写自定义标签和函数库

```java
protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException
{
    String value = "hello";
    request.getRequestDispatcher("/WEB-INF/jsp/view/*" + view + ".jsp")
        .forward(request, response);
}
```

使用标签可以实现的最强大的功能之一是为你的应用程序建立一套 HTML 模板系统。该模板系统可以处理应用程序后页面所需的许多重复性任务，减少重复代码，并使网站设计变得更加容易。为了演示这一点，请使用 `/WEB-INF/tags/template/main.tag` 文件，该文件包含一个管理应用程序中使用页面的基础 JSP 标签。

```jsp
<tag body-content="scriptless" dynamic-attributes="dynamicAttributes"
    trimWhitespace="true">
  <attribute name="title" type="java.lang.String" rtexprvalue="true"
    required="true">
  <include file="/WEB-INF/jsp/main.jsp" />
<!DOCTYPE html>
<html
<c:forEach items="${dynamicAttributes}" var="a">
<c:out value="${a.key}=\${escape(a.value)}" escape="true" />
</c:forEach>
<head>
  <title>${fn:trim(htmlTitle)}</title>
</head>
<body>
  <jsp:body />
</body>
</html>
```

现在查看以下示例代码：

- 该文件中的第一个指令规定了标签可以包含正文内容，它支持动态属性，可以通过 `dynamicAttributes` EL 变量访问动态属性，并且应该修剪空白字符。注意使用 `trimWhitespace` 属性来实现这一点；部署描述符中的 `<jsp-config>` 不影响标签文件，因此你需要在每个标签文件中手动执行此操作。
- 第二个指令指明了显式的 `htmlTitle` 属性。
- 第三个属性包含了 `base.jsp` 文件，同样是因为 `<jsp-config>` 不影响标签文件。
- `<c:forEach>` 循环将所有动态属性复制到 `<html>` 标签中。这通常是你不需要执行的操作，但它展示了动态属性（dynamic）有多用。
- 循环中的 `<c:out>` 似乎没有必要，但这样做是出于以下原因：它确保了每个属性之间的空格被忽略，属性值被正确转义，并且 `<c:out>` 属性值周围的引号不会被转义。

## 创建一个更有用的日期格式化标签处理器

- `htmlTitle` 使用 `<c:out>` 输出为文档 `<title>`，并使用 EL 表达式对其值进行修剪。
- 特殊的 `<jsp:doBody>` 标签用于 HTML `<body>`。该标签只能在 JSP 标签内部使用，告诉容器评估 JSP 标签的内容并将其内联。你还可以指定 `var` 或 `Reader` 属性以及 `scope` 属性，将正文内容输出到变量而不是内联。

现在将所有这些应用起来，创建 `/WEB-INF/jsp/view/hello.jsp` 文件并调用你创建的 `<template:main>`。

```jsp
<template:main htmlTitle="Template Homepage">
Hello,
Template!
</template:main>
```

就是这些了！编译应用程序并启动调试器；导航到 `http://localhost:8080/template-tags/index`。如果你查看生成页面的响应源，你会发现文档标题是 "Template Homepage"，并且文本 "Hello, Template!" 被放置在文档正文中。你成功创建了你的第一个自定义 JSP 标签！在下一节中，当你创建另一个页面来显示下一个自定义标签时，我们将进一步演示此 HTML 模板的力量。

## 创建一个更有用的日期格式化标签处理器

在上一章中，你探索了 JSTL 并学习了国际化、本地化以及标准的 `<fmt:format>` 标签，该标签的功能非常有限。你注意到的该标签的一些主要缺点是无法格式化 `java.util.Date` 之外的任何内容，在需要时将时间放在日期之前，或者在日期和时间之间插入标记字符串。第一个缺点是要求你始终将所有日期和时间转换为 `Date` 实例，第二个和第三个缺点要求你使用两个 `<fmt:formatDate>` 标签或使用 `pattern` 属性，这两者都不是理想的。

创建一个更好的格式化标签，从生成页面的源开始查看，你看到文档标题是 "Template Homepage"，并且文本 "Hello, Template!" 被放置在文档正文中。你成功创建了你的第一个自定义 JSP 标签！在下一节中，当你创建另一个页面来显示下一个自定义标签时，我们将进一步演示此 HTML 模板的力量。

## 创建一个更有用的日期格式化处理器

创建一个更好的格式化标签，从开始思考你想要支持的日期。显然，你希望支持 `Date` 还有 `Calendar`。在 Java 8 日期和时间 API 中，它包含了许多日期和时间类型。坦率地说，它有一个通用接口 `java.time.temporal.TemporalAccessor`，涵盖了主要的日期和时间类型。在 `IndexServlet` 的 `doGet` 方法中添加每种类型的代码。

```java
if(request.getParameter("dates") != null) {
    request.setAttribute("date", new Date());
    request.setAttribute("calendar", Calendar.getInstance());
    request.setAttribute("instant", Instant.now());
    view = "dates";
}
```

现在你已经知道标签需要什么，以及如何使用它。创建一个 TLD 文件来指定日期格式化标签的行为和属性。在实际编写标签处理器之前，基于接口进行编写。TLD 中的标签定义就是该用的接口。列表 8-1 声明了一个 URI 为 `http://www.wrox.com/jsp/tld/wrox` 的标签库，并指定了一个命名方便的 `formatDate` 的单标签。

整个标签声明超过 100 行——在书中打印太长。你需要从 wrox.com 下载 Template-Tags 项目来查看全部。该标签与 `<fmt:formatDate>` 具有相同的属性，通过阅读 TLD，你可以通过描述理解每个属性的。

### 列表 8-1: wrox.tld

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<taglib xmlns="http://java.sun.com/xml/ns/javaee"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/jsptaglib_2_1.xsd"
version="2.1">
<tld-version>1.0</tld-version>
<short-name>wrox</short-name>
<uri>http://www.wrox.com/jsp/tld/wrox</uri>
<tag>
<description></description>
<name>formatDate</name>
<tag-class>wrox.FormatDateTag</tag-class>
<body-content>empty</body-content>
<attribute>
<name>title</name>
<description></description>
<required>true</required>
<rtexprvalue>true</rtexprvalue>
</attribute>
<attribute>
<name>dynamicAttributes</name>
<description></description>
<required>false</required>
<rtexprvalue>true</rtexprvalue>
</attribute>
</tag>
</taglib>
```

# 224 | 第 8 章 编写自定义标签和函数库

```html
<b>带分隔符的即时时间：b>
<wrox:format value="instant" type="both" dateStyle="full" timeStyle="full" firstTime="true" separateDateWith="" /><br>
</template:main>
```



编译并调试你的应用程序，并在浏览器中访问 `http://localhost:8080/template-tags/index.html`。你将看到三个格式化的日期，其中两个以不同的格式显示，正如你指定的那样。你创建的这个新标签比 JSTL 自带的 `<fmt:format>` 标签要灵活且强大得多。

# 理解不同类型的标签处理器

你可以通过不同的方式编写标签处理器以完成许多不同的任务，这本简单的书无法涵盖所有的可能性。但理解这些不同标签类型之间的通用区别是非常重要的。所有标签都必须实现 `Tag` 或 `SimpleTag` 接口，两者都扩展了 `JspTag` 标记接口。`Tag` 是自 JSP 标签早期以来一直存在的经典标签处理器，而 `SimpleTag` 是在 JSP 2.0 中引入的，为了让标签的编写更加简单。

`SimpleTag` 对于许多任务可能更简单，但这些优势也带来了一个明显的缺点：`SimpleTag` 类被实例化、仅使用一次，然后被丢弃。而 `Tag` 实例可以被池化并重用，这对于频繁使用的标签或携带大量资源的标签可以带来显著的性能提升。然而，你不能忽略在 `SimpleTag` 中实现循环（例如）要容易得多。（在这种情况下，`invoke` 方法是将调用的正文写入 JSP 输出，但传入一个 `Writer` 而不是 `null` 会导致正文写入 `Writer`。）

```java
public void doTag() throws JspException, IOException {
    while (condition-is-true) {
        this.getContext().setAttribute("someElVariable", value);
        this.getJspBody().invoke(null);
    }
}
```

对比在 `Tag`（实现 `IterationTag` 并扩展 `Tag`）中实现相同循环的复杂程度：

```java
public int doStart() throws JspException { // 此方法恰好被调用一次
    if (condition-is-true) {
        this.pageContext.setAttribute("someElVariable", value);
        return Tag.EVAL_BODY_INCLUDE;
    }
    return Tag.SKIP_BODY;
}

public int doAfterBody() throws JspException { // 此方法根据需要被多次调用
    if (condition-is-true) {
        this.pageContext.setAttribute("someElVariable", value);
        return Tag.BODY_AGAIN;
    }
    return Tag.SKIP_BODY;
}

public int doEndTag() throws JspException { // 此方法恰好被调用一次
    return Tag.EVAL_PAGE;
}
```

你必须评估所需的每个标签，以确定是否需要将性能优于便利性。记住，`startTag` 可能只返回 `Tag.SKIP_BODY` 或 `Tag.EVAL_BODY_INCLUDE`；`doAfterBody` 可能只返回 `Tag.SKIP_BODY` 或 `IterationTag.EVAL_BODY_AGAIN`；而 `doEndTag` 可能只返回 `Tag.SKIP_PAGE` 或 `Tag.EVAL_PAGE`。

以下列表列出了你可以实现的各种标签（以及你应该扩展的辅助类）以及何时应该实现它们。

- `SimpleTag` 扩展 `JspTag` —— 用于所有不需要通过池化获得性能提升的标签。你通常应该扩展 `SimpleTagSupport`。
- `Tag` 扩展 `JspTag` —— 对于大多数不需要循环或访问正文内容的标签使用此池化标签处理器。（可以使用此标签评估正文内容，但不能访问。）你通常应该扩展 `TagSupport`。
- `LoopTag` 扩展 `Tag` —— 这并不常用，它可以遍历对象的集合（或数组）。你通常应该扩展 `LoopTagSupport`。
- `IterationTag` 扩展 `Tag` —— 这是一个更实用的迭代标签，可以在任何条件下进行迭代，遍历对象的集合。你通常应该扩展 `IterationTagSupport`。
- `BodyTag` 扩展 `IterationTag` —— 这种迭代允许将评估的正文输出缓冲到 `BodyContent` 对象中，随后用于其他用途（如将输出保存到变量）。这是通过从 `startTag` 返回 `BodyTag.EVAL_BODY_BUFFERED` 而不是 `Tag.EVAL_BODY_INCLUDE` 并在 `doEndTag` 中访问正文内容实现的。你通常应该扩展 `BodyTagSupport`。

# 创建一个缩短字符串的 EL 函数

回在本章早些时候，你可以使用 TLD 来定义 EL 函数以及标签。记住，EL 函数的定义非常简单；你只需要某个类的一个 `public static` 方法，就可以定义一个映射到该方法的 EL 函数。你不需要自己编写该静态方法。它可以是 Java SE 库、Java EE 库或完全不同的第三方库中的。考虑 Apache Commons Lang 库中的 `StringUtils`，它有一个非常有用的方法 `abbreviate`，可以确保字符串不会超过特定长度。如果字符串太长，它就会被缩短并在末尾添加省略号 (...)。这在 Web 世界中是一个非常有用的操作，因为用户输入可能很长，有时为了小屏显示或为了防止页面布局破坏 JSPs 而需要缩短。

要将此实用方法转换为可以从你的 JSPs 中调用的 EL 函数，请遵循以下步骤：

1. 打开 `wrow.tld` 文件，并在日期格式 `<tag>` 标签中添加以下 `<function>` 块：
```xml
<function>
  <description>...</description>
  <name>abbreviate</name>
  <function-class>org.apache.commons.lang3.StringUtils</function-class>
  <signature>
    java.lang.String abbreviate(java.lang.String, int)
  </signature>
</function>
```

这比在 JSP 中实现要容易得多。`<function-class>` 元素指定了方法所属的类名，`<signature>` 元素指定了函数的签名。

2. 现在在你的 `IndexServlet` 的 `doGet` 方法中添加：
```java
else if (request.getParameter("text") == null) {
  request.setAttribute("shortText", "This is short text.");
  request.setAttribute("longText", "This is really long text that should get cut off at 32 chars.");
  view = "text";
}
```

3. 创建 `view.jsp` 来演示该函数：
```jsp
<%--id="shortText" type="java.String"%>
<%--id="longText" type="java.String"%>
<template:main htmlTitle="Abbreviating Text">
  <b>Short text:</b>${wrox:abbreviate(shortText, 32)}<br/>
  <b>Long text:</b>${wrox:abbreviate(longText, 32)}<br/>
</template>
```

4. 再次编译并启动 Template-Tags 项目访问 `http://localhost:8080/template-tags/index`。

你会看到新函数缩短了字符串并添加了省略号。

# 用自定义标签替换 Java 代码

之前你承诺过将替换客户支持 JSPs 中的所有 Java 代码。你可以通过本章学到的所有知识来实现。你可以参考 Customer-Support-v6 项目，或者进行此处的更改。你应该从将 `scripting-disabled=false` 开始。这证明了你替换了所有的 Java 代码。

现在从 Template-Tags 项目将 `wrox.tag.FormatDate` 标签和 `/WEB-INF/wrox.tld` 文件复制到支持项目中；你可以在支持应用程序中使用日期格式和字符串缩短函数。你还可以在 TLD 中添加另一个函数。创建一个所示的 `TimeUtils` 类：

```java
public final class TimeUtils {
    public static String intervalToString(long timeInterval) {
        if (timeInterval < 1000)
            return "less than one second";
        if (timeInterval < 60000)
            return (timeInterval / 1000) + " seconds";
        return "about " + (timeInterval / 60000) + " minutes";
    }
}
```

你可以在 TLD 底部添加一个调用 `TimeUtils` 类中方法的函数：

```xml
<function>
    <description>
        以吸引的方式格式化时间间隔，例如“小于一秒”、“十秒”或“大约 12 分钟”。
    </description>
    <name>intervalToString</name>
    <function-class>com.wrox.TimeUtils</function-class>
    <signature>
        java.lang.String intervalToString(long)
    </signature>
</function>
```

确保 `/WEB-INF/jsp/base.jsp` 文件包含适当的 taglib 声明。

## 28 | 第8章 编写自定义标签和函数库

```jsp
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
<%@ taglib prefix="fn" uri="http://java.sun.com/jsp/jstl/functions" %>
<%@ taglib prefix="wrox" uri="http://www.wrox.com/tld/wrox" %>
<%@ taglib prefix="template" tagdir="/WEB-INF/tags/template" %>
```

你已经准备好设计 JSP 了。你还将创建几个标签来帮助支持应用程序并避免代码重复。从列表 8-2 中的 `/WEB-INF/tags/template/main.tag` 开始，它比 Template-Tags 项目中的模板标签更复杂。

注意，该标签的两个属性是简单字符串 `fragment`（片段）。这允许这些属性包含你可以重复用的 JSP 内容。在适当的位置，标签使用 `<jsp:invoke>` 标签来评估这些片段。这类似于 `<jsp:body>`，不同在于它作用于片段而不是标签正体内容。

### 列表 8-2: main.tag

```jsp
<%@ tag body-content="scriptless" trimDirectiveWhitespace="true" %>
<%@ attribute name="htmlTitle" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ attribute name="bodyTitle" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ attribute name="headContent" fragment="true" required="false" %>
<%@ attribute name="navigationContent" fragment="true" required="true" %>
<%@ include file="WEB-INF/jsp/base.jsp" %>
<!DOCTYPE html>
<html>
<head>
  <title>Customer Support :: <c:out value="${fn:trim(htmlTitle)}"/></title>
  <link rel="stylesheet" href="<c:url value="/resource/styles/main.css"/> />
  <jsp:invoke fragment="headContent" />
</head>
<body>
  <h1>Multinational Widget Corporation</h1>
  <table border="0" id="bodyTable">
    <tr>
      <td class="sidebarCell">
        <jsp:invoke fragment="navigationContent" />
      </td>
      <td class="contentCell">
        <h2><c:out value="${fn:trim(bodyTitle)}"/></h2>
        <jsp:doBody />
      </td>
    </tr>
  </table>
</body>
</html>
```

你可能想知道如何指定一个包含 JSP 内容的属性；因为这种值可能有很多行长，并包含其他 JSP 标签。列表 8-3 中的 `/WEB-INF/tags/loggedout.tag` 演示了这一点。当你使用 JSP 标签时，通常将属性指定为普通的 XML 属性，然后是标签体内部的内容。然而，当属性过长或包含 JSP 内容时，你可以在标签体内部使用 `<jsp:attribute>` 标签来指定属性值。

此时，属性是在标签体内部指定的，因此要指定实际的标签内容，你需要使用 `<jsp:body>`。此标签中的所有内容都将成为外层 `<template:main>`（在本例中）的标签体。列表 8-4 `/WEB-INF/tags/template/basic.tag` 通过在片段属性中包含更多内容演示了这一点。该标签指定了几个显示在页面侧边栏的链接，每个页面都使用此模板。它还提供了 `extraHeadContent` 和 `extraNavigationContent` 属性，允许调用方页面向表头或侧边栏添加额外内容。

虽然标签在技术上不能互相扩展，但这本质上就是你所做的的。主标签为模板奠定了基础，而 `loggedOut` 和 `basic` 标签则在此基础上进行构建。现在你可以看到标签的全部威力。

### 列表 8-3: loggedOut.tag

```jsp
<%@ tag body-content="scriptless" trimDirectiveWhitespaces="true" %>
<%@ attribute name="html" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ attribute name="bodyTitle" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ include file="/WEB-INF/jsp/base.jsp" %>
<template:main htmlTitle="${html}" bodyTitle="${bodyTitle}">
  <jsp:attribute name="headerContent">
    <link rel="stylesheet" href="<c:url value="resource/stylesheets/login.css" />" />
  </jsp:attribute>
  <jsp:attribute name="navigationContent" />
  <jsp:body>
    <jsp:body />
  </jsp:body>
</template:main>
```

### 列表 8-4: basic.tag

```jsp
<%@ tag body-content="scriptless" trimDirectiveWhitespaces="true" %>
<%@ attribute name="html" type="java.lang.String" rtexprvalue="true" required="true" %>
<%@ attribute name="bodyTitle" type="java.lang.String" rtexprvalue="true" required="true" %>
```



# 第 8 章 编写自定义标签函数库

```jsp
<%@ attribute name="extraHeadContent" fragment="false" required="false" %>
<%@ attribute name="extraNavigationContent" fragment="false" required="false" %>
<%@ include file="/WEB-INF/jsp/base.jsp" %>

<template:main htmlTitle="${html}" bodyTitle="${bodyTitle}">
  <jsp:attribute name="headContent">
    <jsp:invoke fragment="extraHeadContent" />
  </jsp:attribute>
  <jsp:attribute name="navigationContent">
    <jsp:invoke fragment="extraNavigationContent" />
  </jsp:attribute>
  <jsp:body>
    <jsp:body />
  </jsp:body>
</template:main>
```

### 列表 8-4 (继续)

```jsp
<jsp:attribute name="headContent">
    <jsp:invoke fragment="extraHeadContent" />
  </jsp:attribute>
<jsp:attribute name="navigationContent">
    <jsp:invoke fragment="extraNavigationContent" />
  </jsp:attribute>
<jsp:body>
    <jsp:body />
  </jsp:body>
</template:main>
```

> **注意** 你注意到这些标签中使用了了一些 CSS 文件，`resource/main.css` 和 `resource/login.css`。

## 用自定义标签替换 Java 代码

除了使用 `<template:basic>` 标签外，`ticketForm.jsp` 没有任何变化：

```jsp
<template:basic htmlTitle="Create Ticket" bodyTitle="Create Ticket">
<form method="POST" enctype="multipart/data">
<input type="hidden" name="action" value="create"/>
Subject<br />
<input type="text" name="subject"><br /><br />
Body<br />
<textarea name="body" rows="5" cols="30"></textarea><br /><br />
<b>Attachments</b><br />
<input type="file" name="file"><br /><br />
<input type="submit" value="Submit"/>
</form>
</template:basic>
```

除了使用模板，`viewTicket.jsp` 现在使用 `<wrox:dateFormat>` 标签来显示创建日期：

```jsp
<@elvariable id="ticketId" type="java.String"-->
<@elvariable id="ticket" type="com.wrox.Ticket"-->
<template:basic htmlTitle="${ticket.subject}" bodyTitle="${ticket.subject}">
<c:out value="${ticket.customerName}" /><br />
Created: <wrox:dateFormat value="${ticket.date}" type="both" style="full" /> <br />
<c:out value="${ticket.body}" /><br />
<c:if test="${ticket.numberOfAttachments}>0">
<c:forEach items="${ticket.attachments}">
<c:if test="${status.first}">
<a href="<c:url value="download/"
<c:param name="ticketId" value="${ticket.id}" />
<c:param name="attachment" value="${attachment.name}" />
</c:url>"><c:out value="${attachment.name}" /></a>
</c:if>
</c:forEach><br />
</c:if>
</template:basic>
```

`listTickets` 只使用了日期格式，还使用了 `wrox:abbreviateString` El 将主题文本截断为 60 个字符：

```jsp
<@elvariable id="ticketDatabase" type="java.util.Map, com.wrox.Ticket"-->
<template:basic htmlTitle="Tickets" bodyTitle="Tickets">
<c:choose>
<c:when test="${fn:length(ticketDatabase)} == 0">
<i>系统内没有工单。</i>
</</c:when>
<c:otherwise>
<c:forEach items="${ticketDatabase}" var="entry">
Ticket ${entry.key}: <a href="<c:url value="/tickets/
<c:param name="action" value="view" />
<c:param name="ticketId" value="${entry.key}" />
</c:url>">View</a>
</c:forEach>
</c:otherwise>
</c:choose>
</template:basic>
```

```xml
<c:out value="${wrox:abbreviateString(entry.value.subject, 60)}" />
<a href="/ />
<c:out value="${entry.value.customerName}" /> 创建工
<wrox:formatDate value="${entry.value.dateCreated}" type="both"
timeStyle="short" dateStyle="medium" />
<br />
</c:forEach>
<c:>
</c:otherwise>
</c:choose>
</template:basic>
```

`Notices.jsp` 经历了最大的变化。所有用于声明方法、循环和输出数据的 Java 代码都消失了，取而代之的是 100% 使用 `c:forEach`、`<c:out>`、`<c:if>` 和 `wrox:timeIntervalToString` 的 JSP 代码。

```jsp
<% var id="timestamp" type="long"--%>
<% var id="numberOfSessions" type="int"--%>
<% var id="sessionList" --%>
<template:basic title="Active Sessions" body="Active Sessions">
应用程序中总共有 ${numberOfSessions} 个活动会话。
<c:forEach items="${sessionList}" s="${session.getAttribute('username')}">
<c:out value="${s.id}" />
<c:if test="${s.id == pageContext.session.id}">&nbsp; - 最后活跃于
${wrox:timeIntervalToString(timestamp - s.lastAccessedTime)} 前 <br />
</c:if>
&nbsp;;
</c:forEach>
</template:basic>
```



你现在可以编译并运行你的应用程序，并在浏览器中访问 `http://localhost:8080/support/login`。登录支持应用程序以创建、查看和列出工单。注意视图和列表页面上的格式化日期，以及页面左侧方便的侧边栏。创建一个具有长主题的工单，看看它在列表页面换行之前是如何被截断的。你现在拥有了所有所需的工具，来创建无需在其中嵌入任何 Java 代码的动态 JSP。

### 总结

在本章中，你学习了如何创建自定义的 JSP 和 EL 函数。通过查看 Java 标准标签库 (JSTL) 的 TLD 并创建你自己的 TLD，你探索了标签库描述符 (TLD)。你接触了标签的概念，并使用这项技术创建了强大的 HTML 模板，作为你应用程序页面的基础。你创建了更好的日期和时间格式化，提供了更灵活的选项，并支持 `Date`、`Calendar` 以及 Java 8 日期时间 API，同时维护了 JSTL 中建立的本地化和时区约定。到此时，你已经掌握了创建自由 JSP 所需的所有知识。

从这里开始，我们将进入高级技术并关注它。在下一章中，你将探索过滤器以及如何轻松将它们应用于你的应用程序。

# 9 使用过滤器改进你的应用程序

## 本章内容

- 过滤器的目的
- 如何创建、声明和映射过滤器
- 如何正确排列过滤器的顺序
- 在异步请求处理中使用过滤器
- 探索过滤器的实际用途
- 使用过滤器简化身份验证

### 本章 WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/javaforwebapps` 的 Download Code 标签页找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Filter-Order Project（过滤器顺序项目）
- Filter-Async Project（过滤器异步项目）
- Compression-Filter Project（压缩过滤器项目）
- Customer-Support-v7 Project（客户支持 v7 项目）

### 本章新的 Maven 依赖

本章没有新的 Maven 依赖。继续使用之前所有章节中引入的 Maven 依赖。

## 理解过滤器的目的

过滤器是应用程序组件，可以拦截对资源的请求、资源的响应，或以某种方式处理这些请求。过滤器可以检查和修改请求与响应，并且拒绝、重定向或转发请求。

过滤器对于 Servlet 规范来说相对较新，在 Servlet 2.3 中引入，在 Servlet 2.4 中得到改进，之后没有发生过变化。`java.servlet.Filter` 接口非常简单，涉及你已经熟悉的 `HttpServletRequest` 和 `HttpServletResponse`。像 Servlet 一样，过滤器可以在部署描述符中通过编程或注解进行声明，并且它们拥有初始化参数和 `ServletContext`。过滤器的数量真的仅限于你的想象力；在本节中，你将探索一些常见的应用。

## 日志过滤器

过滤器对于应用程序日志记录特别有用。你将在第 11 章中学习与日志相关的概念和工具，但在某些场景下，应用程序可能需要记录应用程序的每个请求以及每个请求的结果（状态码、长度以及可能的其他信息）。通常 Web 容器提供了请求日志记录的功能，但如果你在日志请求中需要属性信息，可以使用过滤器来记录请求。你还可以使用过滤器跟踪将用于请求所有日志操作的信息。这被称为过滤器标记，你将在第 11 章中学习更多内容。

## 身份验证过滤器

当你需要确保只有授权人员访问你的应用程序时，这通常涉及对每个请求进行检查以确保用户已“登录”。该术语的含义在不同的应用程序中可能不同，但在每个 Servlet 中执行此操作的繁琐性是通用的。过滤器可以将身份验证和授权检查集中在一个拦截所有受保护请求的位置，从而使工作变得更容易。

在本章结束时，你将在正在进行的 Customer Support 项目中添加一个过滤器，专门为此，并移除整个项目中的重复代码。

## 压缩和加密过滤器

尽管你使用过滤器过滤的不只是 HTTP 请求和响应，但实际上，对于 Web 请求，响应始终是 `HttpServletResponse`。事实上，目前 Servlet API 不支持 HTTP 之外的任何协议。在 `doFilter` 中，你可以通过调用 `FilterChain` 对象的 `doFilter` 方法来拒绝请求或继续；你可以更改请求和响应；并且你可以封装请求和响应。

## 错误处理过滤器

面对吧：当软件开发者尝试处理软件执行期间出现的错误时，有时错误会漏掉。当操作系统崩溃时，严重的故障通常是软性故障，在技术领域被亲切地称为“蓝屏”。对于应用程序来说，结果通常是 HTTP 响应代码 500，通常带有带有“内部服务器错误”和某些诊断信息的纯页面。对于本地运行的应用程序（例如在局域网上），这些诊断信息通常是无害的，可能对开发者找出问题有用。对于远程运行的 Web 应用程序，这些诊断信息可能会暴露攻击者用来破坏系统的信息。

由于这些原因，你应该向用户显示更友好的通用错误代码（通常样式与你的应用程序一致），并在时记录错误或通知管理员。过滤器是处理此问题的完美工具。你可以将请求处理封装在 `try-catch` 块中，从而捕获并记录任何错误。这会导致请求被转发到一个不包含任何诊断敏感信息的通用错误页面。

## 理解过滤器链

虽然只有一个 Servlet 可以处理请求，但任意数量的过滤器都可以拦截请求。图 9-1 展示了过滤器链如何接收传入的请求并将其从过滤器传递进行过滤直到所有匹配的过滤器都已处理，然后将其传递给 Servlet。调用 `FilterChain.doFilter()` 会触发过滤器链的继续。如果当前过滤器是链中的最后一个，调用 `FilterChain.doFilter()` 将把控制权交回 Servlet 容器，由容器将请求传递给 Servlet。如果当前过滤器没有调用 `FilterChain.doFilter()`，则链会被中断，Servlet 以及任何剩余过滤器都永远不会处理该请求。

![](img/4677f981a0e1067137bb55a122f8498d_271_0.png)

图 9-1

通过这种方式，过滤器链非常像一个栈（事实上，系列的方法执行确实是在 Java 栈上进行的）。当请求来临时，它进入第一个过滤器，该过滤器被添加到栈中。当过滤器继续执行时，下一个过滤器被添加到栈中。这个过程一直持续，直到请求到达 Servlet，Servlet 是被添加到栈中的最后一个项。当请求完成并返回到最后一个过滤器时，当 Servlet 的 `service` 方法返回时，Servlet 会从栈中移除，控制权传递给上一个过滤器；该过滤器从栈中移除，控制权返回给上一个过滤器。当它的 `doFilter` 方法返回时，栈为空，请求处理完成。正因如此，过滤器可以在目标 Servlet 服务请求之前和之后对请求采取操作。

### 映射到 URL 模式和 Servlet 名称

与 Servlet 一样，过滤器也可以映射到 URL 模式。这决定了哪个或哪些过滤器将拦截请求。任何匹配了过滤器的 URL 模式的请求都会在进入任何匹配的 Servlet 之前进入该过滤器。使用 URL 模式，你不仅可以拦截指向 Servlet 的请求，还可以拦截其他资源，如图像、CSS 文件、JavaScript 文件等。

有时，映射到特定的 URL 可能不方便。你可能有多个 URL —— 其中几十个已经映射到了 Servlet，而你想将过滤器映射到这些 URL。与其将过滤器映射到一个或多个 URL，不如将其映射到一个或多个 Servlet 名称。如果请求匹配到一个 Servlet，容器会查找任何映射到该 Servlet 名称的过滤器并将它们应用于请求。在本节的随后的部分中，你将学习如何将过滤器映射到 URL 和 Servlet 名称。无论你使用 URL 模式、Servlet 名称还是两者来映射过滤器，一个过滤器都可以拦截多个 URL 模式和 Servlet 名称，而多个过滤器也可以拦截同一个 URL 模式或 Servlet 名称。

### 映射到不同的调度器类型

在 Servlet 容器中，你可以以任何方式分发请求。有：

- **普通请求** —— 这些源自客户端，包括指向容器中特定 Web 应用程序 URL。
- **转发请求** —— 当你的代码调用 `RequestDispatcher` 的 `forward` 方法或使用 `<jsp:forward>` 标签时触发。尽管它们与原始请求有关，但在内部是作为独立的请求进行处理的。
- **包含请求** —— 同样，使用 `<jsp:include>` 并调用 `RequestDispatcher` 的 `include` 方法会产生与原始请求相关的独立内部包含请求。（记住，这与 `<%@ include %>` 是相反的）。
- **错误资源请求** —— 这些是对错误页的请求，用于处理 HTTP 错误，如 404 Not Found、500 Internal Server Error 等。
- **异步请求** —— 这些是在处理任何其他请求期间从 `AsyncContext` 分发的请求。

在 Servlet 2.4 之前，过滤器仅适用于典型请求的资源。Servlet 2.4 增加了将过滤器映射到转发请求、包含请求和错误请求的能力，极大地扩展了功能。在 Servlet 3.0 (Java EE 6) 中，异步请求处理在响应发送之前就会返回 Servlet 的 `service` 方法，这导致过滤器链的能力受到削弱。为了补偿这一点，Servlet 3.0 引入了异步调度器类型，用于拦截从 `AsyncContext` 分发的请求。实现异步过滤器应该谨慎，因为对于单个异步请求，可能会被调用多次（可能在不同的线程中）。这将在下一节的详细内容中介绍。

在声明和映射过滤器时，你需要指定该过滤器适用于哪种或哪几种调度器类型，你将在本节的剩余部分学习这些内容。

### 使用部署描述符

在拦截请求之前，你必须像处理 Servlet 一样声明并映射它们。对于 Servlet，你可以通过多种方式实现这一目标。传统方法是在部署描述符中使用 `<filter>` 和 `<filter-mapping>` 元素（类似于 `<servlet>` 和 `<servlet-mapping>` 元素）。`<filter>` 必须包含至少名称和一个类，但也可以包含显示名称、图标和一个或多个参数。

```xml
<filter>
  <filter-name>myFilter</filter-name>
  <filter-class>com.wrox.myFilter</filter-class>
</filter>
```

上面的代码段显示了部署描述符中的简单过滤器声明。与 Servlet 不同，过滤器无法在第一次请求时加载。过滤器的 `init` 方法始终在应用程序启动时调用：在 `ServletContextListeners` 初始化之后，在 Servlet 初始化之前，并按照过滤器在部署描述符中出现的顺序执行。

声明过滤器后，你可以将其映射到任意数量的 URL 或 Servlet 名称。过滤器的 URL 映射也可以像 Servlet URL 映射一样包含通配符。

```xml
<filter-mapping>
  <filter-name>myFilter</filter-name>
  <url-pattern>/foo/*</url-pattern>
  <url-pattern>/*</url-pattern>
  <servlet-name>myServlet</servlet-name>
  <dispatcher>REQUEST</dispatcher>
  <dispatcher>ASYNC</dispatcher>
</filter-mapping>
```

在这种情况下，该过滤器响应 `/foo` 和 `/*` 的任意应用相对 URL，以及任何由名为 `myServlet` 的 Servlet 处理的请求。两个 `<dispatcher>` 元素使其响应普通请求和从 `AsyncContext` 分发的请求。有效的 `<dispatcher>` 类型有 REQUEST、FORWARD、INCLUDE、ERROR 和 ASYNC。过滤器映射可以有零或多个 `<dispatcher>` 元素。如果没有指定，则假设为默认的 REQUEST。

### 使用注解

像 Servlet 一样，你可以使用注解来声明和映射过滤器。`javax.servlet.WebFilter` 注解包含了部署描述符中所有选项的属性。以下代码的效果相当于之前部署描述符中的过滤器声明和映射：

```java
@WebFilter(
    filterName = "myFilter",
    urlPatterns = { "/foo", "/bar/*" },
    servletNames = { "myServlet" },
    dispatcherTypes = { DispatcherType.REQUEST, DispatcherType.ASYNC }
)
public class MyFilter implements Filter
```

使用注解声明和映射的主要缺点是无法在过滤器链上进行排序。过滤器具有特定的顺序，这对于它们的正常交互非常重要。如果你想在不使用部署描述符的情况下控制过滤器的执行顺序，你需要使用程序化配置。希望 Java EE 8 会包含对注解过滤器排序的能力。

### 使用程序化配置

你可以通过 `ServletContext` 程序化配置过滤器，就像配置 Servlet、监听器和其他组件一样。与其使用部署描述符或注解，不如调用 `ServletContext` 的方法来注册和映射过滤器。由于必须在 Servlet 完成之前完成，通常在 `ServletContextListener` 的 `contextInitialized` 方法中实现。（你也可以在 `ServletInitializer` 的 `onStartup` 方法中添加过滤器，你将在第二部分了解更多相关内容。）

```java
@WebListener
public class Configurator implements ServletContextListener {
    @Override
    public void contextInitialized(ServletContextEvent event) {
        ServletContext context = event.getServletContext();

        FilterRegistration.Dynamic registration =
            context.addFilter("myFilter", new MyFilter());
        registration.addMappingForUrlPatterns(
            EnumSet.of(DispatcherType.REQUEST, DispatcherType.ASYNC),
            false, "foo", "/*"
        );
        registration.addMappingForServletNames(
            EnumSet.of(DispatcherType.REQUEST, DispatcherType.ASYNC),
            false, "myServlet"
        );
    }
}
```

在此示例中，使用 `addFilter` 方法将过滤器添加到 `ServletContext` 中。它返回一个 `javax.servlet.FilterRegistration.Dynamic`，你可以用它为 URL 模式和 Servlet 名称添加过滤器映射。`addMappingForUrlPatterns` 和 `addMappingForServletNames` 方法都接受 `javax.servlet.DispatcherType` 集合作为第一个参数。在部署描述符中，如果调度器类型为 `null`，则默认的 REQUEST 调度器是：

```java
registration.addMappingForUrlPatterns(null, false, "foo", "/*");
```

第二个方法参数表示过滤器相对于部署描述符中过滤器的顺序。如果为 `false`（如例所示），程序化的过滤器映射将排在部署描述符中任何过滤器之前。如果为 `true`，部署描述符中的映射将排在你之前。你将在下一节中学习更多关于顺序。最后一个参数允许指定映射过滤器的 URL 模式（针对 `addMappingForUrlPatterns`）或 Servlet 名称（针对 `addMappingForServletNames`）。

## 正确配置你的过滤器

到此为止，你已经多次看到过滤器顺序，但你无疑在疑问它究竟是什么。过滤器顺序决定了过滤器出现在过滤器链的什么位置，反过来决定了一个过滤器相对于其他过滤器何时处理请求。在某些情况下，过滤器何时处理请求并不重要；在其他情况下，它是至关重要的——这完全取决于你如何使用过滤器。例如，一个为请求设置信息（或在日志中记录请求）的过滤器可能会放在任何其他过滤器之前，因为其他过滤器可能会改变请求的命运。如之前讨论的，你无法对使用注解定义的过滤器进行排序，这使得它们对于大多数企业应用几乎没有用。你将广泛使用部署描述符或程序化配置，但你可能永远不需要担心过滤器的配置。

## URL 模式映射与 Servlet 名称映射



过滤器顺序非常简单：匹配请求的过滤器按照其映射在部署描述符或程序化配置中出现的顺序添加到过滤器链中。（记住，如果你在部署描述符中配置了某些过滤器而在程序中配置了另一些，可以使用 `addMapping` 方法的第二个参数来确定程序化映射是否在 XML 映射之前。）图 9-2 展示了过滤器顺序，不同的请求匹配不同的过滤器，但始终按照相同的顺序。然而，顺序并没有那么简单：URL 映射的优先级高于 Servlet 名称映射。如果两个过滤器匹配一个请求，一个通过 URL 模式匹配，另一个通过 Servlet 匹配，那么通过 URL 模式匹配的过滤器始终出现在通过 Servlet 名称匹配的过滤器之前的链中，如图 9-3 所示，即使它的映射出现在之后。为了演示这一点，请考虑以下映射：

![](img/4677f981a0e1067137bb55a122f8498d_275_0.png)

FIGURE 9-2

![](img/4677f981a0e1067137bb55a122f8498d_275_1.png)

FIGURE 9-3

```xml
<servlet-mapping>
  <servlet-name>myServlet</servlet-name>
  <url-pattern>*/foo</url-pattern>
</servlet-mapping>

<filter-mapping>
  <filter-name>servletFilter</filter-name>
  <servlet-name>myServlet</servlet-name>
</filter-mapping>

<filter-mapping>
  <filter-name>myFilter</filter-name>
  <url-pattern>*/foo</url-pattern>
</filter-mapping>
```

```xml
<filter-mapping>
  <filter-name>anotherFilter</filter-name>
  <url-pattern>/foo/bar</url-pattern>
</filter-mapping>
```

如果一个普通请求来自 `/foo/bar`，它将匹配三个过滤器。过滤器链将由 `myFilter`、`anotherFilter` 然后 `servletFilter` 组成。`myFilter` 执行在 `anotherFilter` 之前，因为这是部署描述符中的顺序。URL 映射始终在 Servlet 名称映射之前。如果请求是转发（forward）、包含（include）或异步调度（asynchronous dispatch），它将不会匹配这些过滤器，因为映射没有显式指定 `<dispatcher>`。

# 通过简单示例探索过滤器顺序

要理解过滤器顺序是如何工作的，请查看 wrox 代码下载中的 Filter-Order 项目。它包含了三个 Servlet 和三个过滤器。以下代码段 `ServletOne` 与其对应的 `ServletTwo` 和 `ServletThree` 相同，只是所有的 "One" 都被替换成了 "Two" 和 "Three"：

```java
@WebServlet(name = "servletOne", urlPatterns = "/servletOne")
public class ServletOne extends HttpServlet
{
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        System.out.println("Entering ServletOne.doGet()");
        response.getWriter().write("Serve Servlet One");
        System.out.println("Leaving ServletOne.doGet()");
    }
}
```

同样，`FilterA` 与 `FilterB` 和 `FilterC` 相同：

过滤器在部署描述符中映射到请求如下，以便它们匹配图 9-2 所示的映射。

# 242 | 第 9 章 使用过滤器改进你的应用程序

```xml
<filter>
  <filter-name>filterA</filter-name>
  <class>com.wrox.FilterA</class>
</filter>

<filter-mapping>
  <filter-name>filterA</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>

<filter>
  <filter-name>filterB</filter-name>
  <class>com.wrox.FilterB</class>
</filter>

<filter-mapping>
  <filter-name>filterB</filter-name>
  <url-pattern>/servletTwo</url-pattern>
  <url-pattern>/servletThree</url-pattern>
</filter-mapping>

<filter>
  <filter-name>filterC</filter-name>
  <class>com.wrox.FilterC</class>
</filter>

<filter-mapping>
  <filter-name>filterC</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

要尝试这一点：

1. 编译应用程序并从 IDE 启动 Tomcat。

2. 在浏览器中访问 `http://localhost:8080/servletOne`。你可以看到打印到标准输出的多条消息：

```
Entering FilterA.doFilter()
Entering ServletOne.doGet()
Leaving ServletOne.doGet()
Leaving FilterA.doFilter()
```

3. 将浏览器中的地址改为 `/servlet` 并观察新的输出：

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

注意过滤器链如何从 A 到 C 然后到达 Servlet。然后当 Servlet 完成后，链以反序从 C 到 A 退出。

4. 将浏览器中的地址改为 `/servletThree`。它的输出应该如下：

```
Entering FilterA.doFilter()
Entering FilterB.doFilter()
Entering ServletThree.doGet()
Leaving ServletThree.doGet()
Leaving FilterB.doFilter()
Leaving FilterA.doFilter()
```

5. 对映射进行你可能的任何更改，看看它是如何影响过滤器链执行的。尝试将一个或多个 URL 映射改为 Servlet 名称映射，并注意过滤器链的变化。

# 带有异步请求的过滤器

如上一节所述，适用于异步请求处理的过滤器实现和配置可能非常复杂。关键问题是 Servlet 的 `service` 方法可以在响应发送到客户端之前就返回。请求处理可以委托给另一个线程或基于某些事件。

例如，`service` 方法（扩展为 `doGet`、`doPost` 等方法）可以启动 `AsyncContext`，为某些假设的消息（例如接收到请求）注册监听器，然后返回。当假设的监听器接收到消息时，它可以发送响应。使用这种技术，当请求处理暂停时，请求线程不会阻塞。拦截请求的过滤器会在 `service` 返回且响应实际发送之前完成，其 `do` 方法。

映射到 `ASYNC` 调度器的过滤器拦截由 `AsyncContext` dispatch 方法调用的内部请求。要演示这种更复杂的过滤，请查看 wrox 代码下载中的 Filter-Async。任何RequestFilter 过滤请求和响应（你将在下一节中探索），并打印任何类型的请求。如果它检测到 Servlet 启动了 AsyncContext，它会打印该信息，并指示响应使用的是原始请求和响应还是解包装后的响应。

```java
System.out.println("Entering " + this.name + " .doFilter().");
chain.doFilter(
    new HttpServletRequestWrapper(HttpServletRequest request),
    new HttpServletResponseWrapper(HttpServletResponse response)
);
if (request.isAsyncSupported() && request.isAsyncStarted()) {
    AsyncContext context = request.getAsyncContext();
    System.out.println("Leaving " + this.name + " .doFilter()., async " + 
        !context.hasOriginalRequestAndResponse());
} else {
    System.out.println("Leaving " + this.name + " .doFilter().");
}

@Override
public void destroy() {
}
```

此过滤器在 `web.xml` 中实例化并映射了三次。这三个映射都可以拦截任何 URL：`normalFilter` 仅拦截普通请求；`forwardFilter` 仅拦截转发请求；而 `asyncFilter` 拦截从 `AsyncContext` 出的请求。注意在每个 `<filter>` 元素中添加了 `<async-supported>true</async-supported>`。这告诉容器过滤器已准备好处理异步请求。如果一个没有 `<async-supported>` 的过滤器拦截了请求，尝试在该请求中启动 `AsyncContext` 将导致 `IllegalStateException`。

```java
The NonAsyncServlet 是非常直接的：它请求 /regular 并转发到 nonAsync.jsp 页面。
@WebServlet(name="nonAsyncServlet", urlPatterns="/regular*")public class NonAsyncServlet extends HttpServlet
{
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException
    {
        System.out.println("Entering NonAsyncServlet.doGet().");
        request.getRequestDispatcher("/WEB-INF/jsp/nonAsyncServlet.doGet.jsp").forward(request, response);
        System.out.println("Leaving NonAsyncServlet.doGet().");
    }
}
```

列表 9-1 中的 `AsyncServlet` 更加复杂。为了使日志清晰，它为当前请求生成了一个唯一的 ID。如果 `unwrap` 参数不存在，它将通过 `startAsync(ServletRequest, HttpServletResponse)` 启动 `AsyncContext`。这确保了 `AsyncContext` 获取了传递给 `doGet` 的请求和响应。如果过滤器包装了请求或响应，则 `AsyncContext` 使用的是该包装器。然而，如果存在 `unwrap`，则 `doGet` 将使用无参数的 `startAsync` 方法启动 `AsyncContext`。在这种情况下，`AsyncContext` 获取的是原始请求和响应，而不是包装后的请求和响应。注意调用 `AsyncContext` 的

## 正确排序你的过滤器

start(Runnable) 方法（使用 Java 8 方法引用）。这告诉容器使用其内部线程池运行 `Runnable`。你可以简单地启动自己的线程，但使用容器的线程池是安全的，可以避免资源耗尽。

## 列表 9-1: AsyncServlet.java

```java
@WebServlet(name = "AsyncServlet"
```

继续

![](img/4677f981a0e1067137bb55a122f8498d_280_0.png)

# 246 | 第 9 章 改进你的应用程序过滤器

# 列表 9-1 (继续)

```java
Thread.sleep(5_000L);
catch (Exception e) {
    e.printStackTrace();
}

HttpServletRequest request =
    (HttpServletRequest)this.context.getRequest();
System.out.println("Done sleeping. Request ID = " + this.id + 
    ", URL = " + request.getRequestURL() + "*");

    this.context.dispatch("/WEB-INF/jsp/async.jsp");

    System.out.println("*Asynchronous thread completed. Request ID = " + 
    this.id + "*");
    }
}
```

现在尝试一下 Servlets 和过滤器：

- 1. 编译应用并从 IDE 启动 Tomcat；然后在浏览器中访问 http://localhost:8080/filters/regular。你应该会在调试器的输出窗口中看到以下内容。注意 *normalFilter* 拦截了对 Servlet 的请求，而 *forwardFilter* 拦截了向到 JSP 的转发请求。

```
normalFilter.doFilter();
normalAsyncServlet.doGet();
forwardFilter.doFilter();
In nonAsync.jsp.
LeavingforwardFilter.doFilter();
LeavingAsyncServlet.doGet();
normalFilter.doFilter();
```

- 2. 访问 http://localhost:8080/filters/async。注意 *normalFilter* 拦截了对 Servlet 的请求，而 *forwardFilter* 拦截了向到 JSP 的转发请求。

```
normalFilter.doFilter();
normalAsyncServlet.doGet();
forwardFilter.doFilter();
In nonAsync.jsp.
LeavingforwardFilter.doFilter();
LeavingAsyncServlet.doGet();
normalFilter.doFilter();
```

- 3. 访问 http://localhost:8080/filters/regular。注意 *normalFilter* 拦截了对 Servlet 的请求，而 *forwardFilter* 拦截了向到 JSP 的转发请求。

```
normalFilter.doFilter();
normalAsyncServlet.doGet();
forwardFilter.doFilter();
In nonAsync.jsp.
LeavingforwardFilter.doFilter();
LeavingAsyncServlet.doGet();
normalFilter.doFilter();
```

- 4. 访问 http://localhost:8080/filters/async?timeout=3000。注意 *normalFilter* 拦截了对 Servlet 的请求，而 *forwardFilter* 拦截了向到 JSP 的转发请求。

```
normalFilter.doFilter();
normalAsyncServlet.doGet();
forwardFilter.doFilter();
In nonAsync.jsp.
LeavingforwardFilter.doFilter();
LeavingAsyncServlet.doGet();
normalFilter.doFilter();
```



异步请求处理有多复杂和强大这应该是显而易见的。然而，如果你直接使用 `AsyncContext` 处理响应，代码将在任何过滤器的范围之外执行。但如果你使用 `AsyncContext` 的 `dispatch` 方法在内部将请求转发到 URL，映射到 ASNC 请求的过滤器就可以拦截该内部转发并应用额外的逻辑。你必须决定何时这种方法是合适的，在大多数情况下，你不需要异步请求处理。本书的其余部分没有地方使用异步请求处理。

## 调查过滤器的实际用途

本章开始讨论了过滤器的许多实际用途。wrox.com 上的 Compression-Filter 项目演示了这些用途中的两种：日志过滤器和响应压缩过滤器。项目包含一个映射到 `/servlet` 的 Servlet，响应“This Servlet may be compressed.”。它还包含一个 `/index.jsp` 文件，响应“This content may be compressed.”。该项目使用以下 `ServletListener` 通过编程配置应用程序的过滤器。

```java
@WebListener
public class Configurator implements ServletContextListener
{
    @Override
    public void contextInitialized(ServletContextEvent event) {
        ServletContext context = event.getServletContext();
        FilterRegistration dynamic registration = context.addFilter("requestLogFilter", new RequestLogFilter());
        registration.addMappingForUrlPatterns(null, false, /*);

        registration = context.addFilter("compressionFilter",
            new CompressionFilter());
        registration.setAsyncSupported(true);
        registration.addMappingForUrlPatterns(null, false, /*);
    }

    @Override
    public void contextDestroyed(ServletContextEvent event) {}
}
```

## 添加简单的日志过滤器

列表 9-2 中的 `RequestLogFilter` 是所有请求过滤器链中的第一个过滤器。它测量处理请求所需的时间，并记录进入应用程序请求的信息——IP 地址、时间戳、请求方法、协议、状态和长度，以及处理请求——类似于 Apache HTTP 日志格式。日志发生在 `finally` 块中，这样过滤器链下游抛出的异常就不会阻止日志的写入。

### 列表 9-2: RequestLogFilter implements Filter

```java
public class RequestLogFilter implements Filter
{
    @Override
    public void doFilter(ServletRequest request
```

```java
System.out.println(in.getRemoteAddr() + " - " + "[" + time + "] "
    + "\" " + in.getMethod() + " " + in.getRequestURI() + " " +
    + in.getProtocol() + "\" " + out.getStatus() + " " + length +
    + " " + timer);


@Override
public void init(FilterConfig filterConfig) throws ServletException { }

@Override
public void destroy() { }
```

> **注意** `RequestLogFilter` 在处理异步请求时将无法正常工作。如果 Servlet 拥有 `AsyncContext`，`doFilter` 将在响应发送之前返回，这意味着过滤器将记录不完整或错误的信息。要让此过滤器在异步请求中正常工作是一项重大且复杂的任务，这留给读者自行思考了。

## 使用过滤器压缩响应内容

列表 9-3 中的 `CompressionFilter` 比 `RequestLogFilter` 要复杂得多。此时，你可能会认为应该排除该过滤器，然后在返回时执行压缩逻辑。然而，请记住，响应数据可能在 Servlet 完成请求处理之前就开始流向客户端传输。在处理异步请求的情况下，数据也可能开始流回客户端。因此，如果你想修改响应，必须封装向链中传递的响应对象。`CompressionFilter` 正是这样做的。

花一点时间阅读代码，看看 `CompressionFilter` 在做什么。首先，它检查客户端是否包含了包含 "zip" 编码的 `Accept-Encoding` 头部。如果没有包含，这是一个非常重要的检查；如果没有包含，客户端可能无法理解压缩后的响应。如果包含了，它会将 `Content-Encoding` 头部设置为 "zip"，然后用私有内部类 `ResponseWrapper` 的实例封装响应。该类反过来又将向客户端传回数据的 `PrintWriter` 或 `ServletOutputStream` 封装在私有类 `GZIPServletOutputStream` 中。此包装器包含一个内部的 `java.util.zip.GZIPOutputStream`。响应首先写入 `GZIPOutputStream`，完成后完成后将压缩后的响应写入被封装的 `ServletOutputStream`。`ResponseWrapper` 还防止了任何 Servlet 代码为响应设置 `content-length` 头部，因为在响应压缩之前无法知道内容长度。

### 列表 9-3：CompressionFilter 实现 Filter

```java
public class CompressionFilter {
    @Override
    public void doFilter(ServletRequest request, ServletResponse response,
            FilterChain chain) throws IOException, ServletException {
        if (((HTTPRequest)request).getHeader("Accept-Encoding")
                .contains("zip")) {
            System.out.println("Encoding requested.");
            ((HttpServletResponse)response).setHeader("Content-Encoding", "zip");
            ResponseWrapper wrapper =
                new ResponseWrapper((HttpServletResponse)response);
            try {
                chain.doFilter(request, wrapper);
                try {
                    wrapper.finish();
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
        } else {
            System.out.println("Encoding not requested.");
            chain.doFilter(request, response);
        }
    }

    @Override
    public void init(FilterConfig filterConfig) throws ServletException {}

    @Override
    public void destroy() {}
}

private static class ResponseWrapper extends HttpServletResponseWrapper {
    private GZIPServletOutputStream outputStream;
    private PrintWriter writer;

    public ResponseWrapper(HttpServletRequest request) {
        super(request);
    }

    @Override
    public synchronized ServletOutputStream getOutputStream()
        throws IOException {
        if (this.writer != null) {
            throw new IllegalStateException("getWriter() already called.");
        }
        if (this.outputStream == null) {
            this.outputStream =
                new GZIPServletOutputStream(super.getOutputStream());
        }
        return this.outputStream;
    }
}
```

```java
public synchronized PrintWriter getWriter() throws IOException {
if (this.writer == null && this.outputStream != null) {
    throw new IllegalStateException(
      "getOutputStream() already called.");
}
if (this.writer == null) {
    this.outputStream = 
      new GZIPOutputStream(super.getOutputStream());
    this.writer = new PrintWriter(new OutputStreamWriter(
      this.outputStream, this.getCharacterEncoding())
    ));
}
return this.writer;
}
```

```java
@Override
public void flushBuffer() throws IOException {
if (this.writer == null) {
    this.writer.flush();
} else if (this.outputStream != null) {
    this.outputStream.flush();
}
super.flushBuffer();
}
```

```java
@Override
public void setContentLength(int length) { }
```

```java
@Override
public void setContentLengthLong(long length) { }
```

```java
@Override
public void setHeader(String name, String value) {
if (!"content-length".equalsIgnoreCase(name)) {
    super.setHeader(name, value);
}
}
```

```java
@Override
public void addHeader(String name, String value) {
if (!"content-length".equalsIgnoreCase(name)) {
    super.setHeader(name, value);
}
}
```

```java
@Override
public void setIntHeader(String name, int value) {
if (!"content-length".equalsIgnoreCase(name)) {
    super.setIntHeader(name, value);
}
}
```

```java
@Override
public void addIntHeader(String name, int value) {
if (!"content-length".equalsIgnoreCase(name)) {
    super.addIntHeader(name, value);
}
```

```java
public void finish() { {
if (this.writer == null) {
    this.writer.flush();
} else if (this.outputStream != null) {
    this.outputStream.flush();
}
}
```

### 列表 9-3（继续）

```java
private static class GZIPServletOutputStream extends ServletOutputStream {
    private final ServletOutputStream outputStream;
    private final GZIPOutputStream gzipStream;

    public GZIPServletOutputStream(ServletOutputStream outputStream)
        throws IOException {
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
```

封装模式是一种非常常见的模式，你可能会在很多过滤器中看到它。请求和响应对象都可以被封装；然而，封装响应更为常见。封装响应允许你拦截响应的任何方法，从而提供了修改响应数据的能力。你也可以使用类似于列表 9-3 中的过滤器来加密响应数据而不是压缩。请求对象可以被封装以解密其内容。

尝试日志和压缩过滤器：

1. 从 IDE 编译你的应用程序和 Tomcat。
2. 在浏览器中访问 `http://localhost:8080/compression/` 和 `http://localhost:8080/compression/servlet`。
3. 使用浏览器的开发工具开始监控应用程序的请求和响应头部。（Microsoft Internet Explorer 和 Google Chrome 内置了开发工具可以，Mozilla Firefox 的 Firebug 插件也具有此功能）。你应该能看到如图 9-4 所示的头部。

### 图 9-4

注意 `Accept-Encoding` 请求头部包含了 "gzip" 编码，而 `Content-Encoding` 响应头部的值为 "gzip"。这意味着你的浏览器正在宣布它可以接受 gzip 编码响应，压缩过滤器顺应请求，在发送到浏览器之前对响应数据进行了压缩。

![](img/4677f981a0e1067137bb55a122f8498d_288_0.png)

# 使用过滤器简化身份验证

Web 应用程序中，过滤器的一个关键用途是保护应用程序免受未经授权的访问。你为 Multinational Widget Corporation 开发的客户支持应用程序使用了一种非常原始的身份验证机制来保护其页面。你可能注意到应用程序中的许多地方都包含相同的重复代码来检查身份：



```
if (request.getSession().getAttribute("username") == null) {
    response.sendRedirect("login");
    return;
}
```

在某个时刻，你可能会认为更好的解决方案是在某个类中创建一个公共静态方法来执行此检查并调用。但无疑，尽管代码重复了，它仍然导致在多个地方执行该方法。随着应用程序中 Servlet 数量的增加，对该静态方法的调用次数也会随之增加。

在学习了本章内容后，应该有一个更好的地方放置这段代码。wrox 代码下载中的 Customer-Support-v7 项目通过向 `Configurator` 监听类和 `AuthenticationFilter` 类添加代码演示了这一点。之前的代码段已从 `TicketServlet` 的 `doGet` 和 `doPost` 方法中移除。配置器非常简单：它声明了 `AuthenticationFilter` 并将其映射到 `/tickets` 和 `/sessions`。

```
@WebListener
public class Configurator implements ServletContextListener {

    @Override
    public void contextInitialized(ServletContext event) {
        ServletContext context = event.getServletContext();

        FilterRegistration.Dynamic registration = context.addFilter("authenticationFilter", new AuthenticationFilter());
        registration.setAsyncSupported(true);
        registration.addMappingForUrlPatterns(null, false, "*/sessions", "*/tickets");
    }

    @Override
    public void contextDestroyed(ServletContext event) {}
}
```

当你向应用程序添加更多 Servlet 或其他保护资源（如 JSP）时，你只需要将你的 URL 模式添加到过滤器注册中，以确保用户在访问这些资源之前已经登录。当然，此过滤器并不保护登录 Servlet，因为你不想保护登录屏幕。你不需要保护任何 CSS、JavaScript 或图像资源，因为它们不包含敏感数据。`AuthenticationFilter` 对任何 HTTP 方法的每个请求都执行身份验证检查，如果用户未登录，则将其重定向到登录屏幕：

```
public class AuthenticationFilter implements Filter {
    @Override
    public void doFilter(ServletRequest request, HttpServletResponse response, FilterChain chain) throws IOException, ServletException {
        HttpSession session = ((HttpServletRequest)request).getSession(false);
        if (session != null && session.getAttribute("username") == null) {
            ((HttpServletResponse)response).sendRedirect("/login");
        } else {
            chain.doFilter(request, response);
        }
    }

    @Override
    public void init(FilterConfig config) throws ServletException {}

    @Override
    public void destroy() {}
}
```

此变化的一个美好之处是，如果你更改了身份验证算法，只需要更改过滤器即可继续保护应用程序中的资源。在此之前，你必须对每个 Servlet 进行更改。在 IDE 中启动 Tomcat 并在浏览器中导航到 `http://localhost:8080/support` 来测试这些更改。尽管所有 Servlet 中都移除了身份验证检查，但在查看或创建票单或查看会话列表之前，你仍会被要求登录。

### 总结

在本章中，你探索了过滤器的用途以及可能使用它们的原因。你学习了 `Filter` 接口以及如何在应用程序中创建、声明和映射过滤器。你实验了至关重要的过滤器链，以及在某些场景和其他另一些场景下过滤器执行顺序的重要性。你接触了异步请求处理的概念，并使用过滤器进一步探索，从而理解了异步请求处理可能会有多么棘手。最后，在探索了声明和映射过滤器的三种不同方式（在部署描述符中、使用注解和通过编程方式）后，你实验了日志过滤器、响应压缩过滤器和身份验证过滤器。

在下一章中，你将探索 WebSockets 技术、它们如何极大提高交互式应用程序，以及如何在 Java 和 JavaScript 中使用它们。一个有趣的点是，Tomcat 中使 WebSocket 可行的代码实际上使用了一个过滤器来拦截应用程序中所有绑定到 WebSocket 的请求，并将它们发送到你的 WebSocket 端点（你将在下一章中学习更多信息）。因此，即使你什么都不做，你的应用程序已经有了过滤器在检查并在必要时修改请求。

# 使用 WebSockets 让你的应用程序具有交互性

## 本章内容

- Ajax 如何演进为 WebSockets
- 关于 WebSocket API 的讨论
- 使用 WebSockets 创建多人游戏
- 在集群中使用 WebSockets 进行通信
- 如何在 Web 应用程序中添加聊天功能

## 本章 WROX.COM 代码下载

你可以在 `http://www.wrox.com/remitle.cgi?isbn=1118656444` 的 Download Code 选项卡找到本章的 wrox.com 代码下载。本章的代码分为以下主要示例：

- Game-Site Project
- Simulated-Cluster Project
- Customer-Support-v8 Project

## 本章的新 Maven 依赖

除了之前章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```
<dependency>
  <groupId>javax.websocket</groupId>
  <artifactId>javax.websocket-api</artifactId>
  <version>1.0</version>
  <scope>provided</scope>
</dependency>
```

```
<dependency>
  <groupId>org.apache.commons</groupId>
  <artifactId>commons-lang</artifactId>
  <version>3.1</version>
</dependency>
```

```
<dependency>
  <groupId>com.fasterxml.jackson.core</groupId>
  <artifactId>jackson-core</artifactId>
  <version>2.3.2</version>
</dependency>
```

```
<dependency>
  <groupId>com.fasterxml.jackson.core</groupId>
  <artifactId>jackson-annotations</artifactId>
  <version>2.3.2</version>
</dependency>
```

```
<dependency>
  <groupId>com.fasterxml.jackson.core</groupId>
  <artifactId>jackson-databind</artifactId>
  <version>2.3.2</version>
</dependency>
```

```
<dependency>
  <groupId>com.fasterxml.jackson.data</groupId>
  <artifactId>jackson-datatype</artifactId>
  <version>2.3.2</version>
</dependency>
```

```
<dependency>
  <groupId>com.fasterxml.jackson.datatype</groupId>
  <artifactId>jackson-datatype-jsr310</artifactId>
  <version>2.3.2</version>
</dependency>
```

# 演进：从 AJAX 到 WEBSOCKETS

最初，用户希望网页具有交互性。答案是 JavaScript。在早期，这还不够。多年来，它在速度、安全能力方面有了显著提高。对于像 Ajax 这样强大的工具，这是一个很难解决的问题。

## 问题：从服务器获取新数据

Ajax（异步 JavaScript XML 的缩写）已与与通信的概念成为同义词。它并不强制使用 XML，正如名称暗示的那样，通常使用 JSON。这是问题的核心：浏览器并不一定知道何时有新数据。例如，当两个用户在 Web 应用程序中聊天时，只有服务器知道 A 何时给 B 发了消息。B 的浏览器在联系服务器之前不知道。

### 频繁轮询

也许解决这个问题最流行的方法之一是轮询服务器获取新数据。概念相当简单：每隔固定间隔（通常是一秒一次），浏览器向服务器发送 Ajax 请求以获取新数据。服务器处理请求。如果服务器有新数据，则返回新数据。如果没有，则返回空内容。这可能意味着一个空 JSON 对象或 XML 文档，或者 `Content-Length` 头部为 0。

这种协议的缺点是巨大而显而易见的：可能会产生大量不必要的请求。注意图中的第二次和第三次请求没有任何任何成就！加上建立连接、发送和接收头部以及销毁连接的开销，浪费了大量的处理和网络资源只为了发现服务器没有为浏览器提供新数据。

### 方案 2：长轮询

图 10-2 所示的长轮询与频繁轮询相似，不同之处服务器不会等到有数据要返回给浏览器时才发送。这种方式更高效，因为浪费的计算和网络资源更少，但它带来了一些自身的问题：

- 如果在服务器响应之前，浏览器有新数据要发送到服务器怎么办？浏览器必须要么发送单独的请求，要么终止当前请求（服务器必须优雅地恢复）并开始另一个请求。
- 连接超时是内置在 TCP 和 HTTP 规范中的。由于由于，服务器和客户端必须定期关闭并重新建立连接。有时连接每隔 60 秒就会关闭一次，尽管某些实现已经成功地保持了数秒的连接。
- HTTP/1.1 规范中存在连接限制规定。浏览器对任何主机名允许的并发连接数不宜超过两个。如果一个连接一直由于等待从服务器推送数据而处于占用状态，将使用于从服务器获取网页、图形和其他资源的连接数量缩减一半。

尽管存在这些问题，这仍然是一种在过去几年中获得广泛使用的流行方法，它通常被统称为 Comet（彗星，这是一个与 Ajax 的双关语游戏，因为这两个名字都可以指清洁产品）。

### 方案 3：分块编码

与长轮询方案非常相似，分块编码利用了 HTTP/1.1 的一项功能，该功能允许服务器在不声明内容长度的情况下对请求做出响应。可以使用 `Transfer-Encoding: chunked` 头部来代替 `Content-Length` 头部。这告诉浏览器响应是以“分块”形式发送的。在响应中，每个块以一个指示块长度的数字开头，后面是一系列表示块扩展的可选字符（与本文讨论无关），以及一个 CRLF（回车换行符）序列。随后是该块中包含的数据以及另一个 CRLF。之后可以跟随任意数量的块，理论上它们之间可以被任何时间（无论长短）隔开。当发送一个零长度块（一个 0 后面跟两个 CRLF）时，表示响应结束。

你通常使用分块编码来解决问题的方法是在连接开始时处理连接，以便接收来自服务器的某些事件。服务器的每个块都是一个新事件，并触发 JavaScript 对象的 `onreadystatechange` 事件处理程序。尽管偶尔（频率不如长轮询那么高），连接仍需要刷新。当浏览器需要向服务器发送新数据时，它会通过第二个短生存请求来完成。

该协议如图 10-3 所示。在左侧，浏览器在任何需要时使用短生存请求向“上游端点”发送新数据。在右侧，浏览器与“下游端点”建立一个单一的长连接连接，服务器使用该连接分块发送缓冲区更新。分块编码解决了长轮询中存在的主要超时问题（浏览器更容易忍受响应花费很长时间来完成，而不是忍受响应在*过程中*花费很长时间——但浏览器受限于两个连接的问题仍然存在）。此外，对于长轮询和分块编码，

### 方案 4：WebSockets

在过程早期，许多人意识到这还不够。他们需要一种全双工、持久且不需要浏览器插件的解决方案。因此，WebSockets 协议诞生了。

## WebSocket 协议基于 HTTP/1.1 之上

图 10-5 所示，WebSocket 连接始于对具有特殊方案的 URL 发起的并不常见的 HTTP 请求。URI 方案 `ws` 和 `wss` 分别对应其 HTTP 对应方案 `http` 和 `https`。`Connection: Upgrade` 头部与 `Upgrade: websocket` 头部一起出现，指示服务器将连接升级到 WebSocket 协议。这是一种在 2011 年通过 RFC 6455 形式化的持久性、全双工通信协议。握手完成后，文本和二进制消息可以在两个方向上同时发送，而无需关闭并重新建立连接。在此时，客户端和服务器之间本质上没有区别——它们对连接具有平等的能力和控制权，仅仅是对等节点。

> 注意：`ws` 和 `wss` 方案并不严格属于 HTTP 协议的一部分，因为 HTTP 请求和请求头实际上并不包含 URI 方案。相反，HTTP 请求仅在请求的第一行中包含相对于服务器的 URL，并现在 `Host` 头部中包含主机名。专门的 WebSocket 方案主要用于告知浏览器和 API，你打算使用 SSL/TLS (wss) 还是不加密 (ws) 进行连接。

WebSocket 协议的实现具有许多优点：

- 因为连接建立在端口 80 (ws) 或 443 (wss) 上，使用了与 HTTP 相同的端口，几乎没有防火墙会阻止 WebSocket 连接。
- 由于握手通过 HTTP 进行，该协议自然地集成到 浏览器和 HTTP 服务器中。
- 称为 `ping` 和 `pong` 的心跳消息往返发送，以保持 WebSocket 连接几乎无限持续。基本上，一方定期向另一方发送一个微小包（ping），另一个返回一个包含相同数据的数据包（pong）。这确保了双方仍然连接。
- 消息会代表你进行帧封装，无需额外的代码，因此服务器和客户端知道消息何时开始以及所有内容何时到达。
- 关闭连接涉及特殊的消息，该消息可以包含状态码并解释关闭连接的原因。
- WebSocket 连接可以安全地允许跨域连接，消除了对 Ajax 和 `XMLHttpRequest` 设置的限制。
- 握手完成后，HTTP 要求每个主机名同时连接限制为两个的规定不再适用，因为连接已不再是 HTTP 连接。

WebSocket 连接中的握手请求头非常简单。如果如果在像 Wireshark 或 Fiddler 等流量分析器中研究，可能会看到典型的 WebSocket 升级请求：

```
GET /websocketEndpoint HTTP/1.1
Host: www.example.com
Connection: Upgrade
Upgrade: websocket
Origin: http://example.com
Sec-WebSocket-Key: X3JHMDL1LeLkh9GBXdw==
Sec-WebSocket-Version: 13
Sec-WebSocket-Protocol: game
```

你应该已经熟悉 HTTP 序言（`GET /websocketEndpoint HTTP/1.1`）和 `Host` 头部。此外，`Connection` 和 `Upgrade` 头部之前已经解释过。`Origin` 头部是一种防止意外跨域请求的机制。请求者将此设置为提供 Web 页面的头部，服务器检查该值是否与“已批准”域名列表匹配。



`Sec-WebSocket-Key` 头部是一个一致性检查：浏览器生成一个随机密钥，对其进行 base64 编码，并放入请求头部。服务器发送 `258EAE7-B914-47DA-95CA-CADB0C5SB11` 来验证头部值，对其进行 SHA-1 哈希处理，并将 base64 编码后的哈希值返回在 `Sec-WebSocket-Accept` 响应头部中。

`Sec-WebSocket-Version` 表示客户端实现的协议当前版本，`Sec-WebSocket-Protocol` 是可选头部，进一步指示在 WebSocket 协议之上使用的协议。

WebSocket 接口的实现。（如果你记得 Ajax 的早期时代，不同的浏览器对于执行 Ajax 请求有不同的类和函数，这对于你来说将是一个意外的惊喜。）

# 创建 WebSocket 对象

创建一个 WebSocket 对象非常简单：

```
var connection = new WebSocket('ws://www.example.net/stocks/stream/');
var connection = new WebSocket('wss://secure.example.org/games/chess');
var connection = new WebSocket('ws://www.example.com/chat', 'chat');
var connection = new WebSocket('ws://www.example.com/chat', '.chat.v1,.chat.v2');
```

`WebSocket` 构造函数的第一个参数是你想要连接的 WebSocket 服务器的必填 URL。可选的第二个参数可以是字符串或字符串数组，用于定义你想要接受的一个或多个由客户端定义的协议。请记住，这些协议是由你实现的，并不由 WebSocket 技术管理。该参数仅为在你需要时传递这些信息提供了一种机制。

# 使用 WebSocket 对象

`WebSocket` 接口有几个属性。第一个属性 `readyState` 指明 WebSocket 连接的当前状态。它的值可以是 `CONNECTING`（数字 0）、`OPEN`（1）、`CLOSING`（2）或 `CLOSED`（3）。

```
if(connection.readyState == WebSocket.OPEN) { /* do something */ }
```

它主要在内部使用；但是为了确保在连接未打开时不发送消息，它是很有用的。与 `XMLHttpRequest` 不同，WebSocket 没有在任何类型事件发生时被调用的 `onreadystatechange` 事件，WebSocket 有四个独立的事件，代表了可能发生在 WebSocket 上的四种不同类型：

```
connection.onopen = function(event) { }
connection.onclose = function(event) { }
connection.onerror = function(event) { }
connection.onmessage = function(event) { }
```

事件名称清晰地指示了这些事件是如何触发的。重要的是，当 `readyState` 从 `CONNECTING` 变为 `OPEN` 时，会触发 `onopen` 事件，此时只读的 `url`（服务器提供的扩展）和 `protocol`（服务端协议）对象属性会被设置并固定。传递给 `onopen` 的事件是一个标准的 JavaScript `Event`，其中没有特别有趣的内容。然而，传递给 `onclose` 的事件有三个实用的属性：`wasClean`、`code` 和 `reason`。你可以使用这些属性向用户报告关闭情况：

```
connection.onclose = function(event) {
  if (event.wasClean) {
    alert(event.code + ' : ' + event.reason);
  }
}
```

合法条款定义在 RFC 6455 第 7.4 节（http://tools.ietf.org/html/rfc6455#section-7.4）。代码 1000 表示正常，所有其他代码均为异常。`onerror` 事件包含一个错误对象的 `data` 属性，该对象可以是任何内容（通常是字符串消息）。此事件仅针对客户端错误触发；协议错误会导致连接关闭。`onmessage` 是你处理得最仔细的事件处理器。此事件也包含一个 `data` 属性。如果消息是文本，该属性为字符串；如果消息是二进制消息且 WebSocket 的 `binaryType` 设置为 "blob"（默认值），则为 `Blob`；如果消息是二进制消息且 `binaryType` 设置为 "arraybuffer"，则为 `ArrayBuffer`。你通常应该在初始化 WebSocket 对象后立即设置 `binaryType`，并在连接的剩余时间内保持该值；但是在需要时更改该值也是合法的。

```
var connection = new WebSocket('ws://www.example.net/chat');
connection.binaryType = 'arraybuffer';
...
```

WebSocket 对象有两个方法：`send` 和 `close`。`close` 方法接受一个可选的码帧作为第一个参数（默认为 1000），以及一个可选的扩展字符串作为第二个参数（默认为空）。`send` 方法接受字符串、`Blob`、`ArrayBuffer` 或 `ArrayView` 作为参数，这是你可能使用 WebSocket 的 `bufferedAmount` 属性唯一的地方。`bufferedAmount` 指明从之前的发送的有多少数据正在等待发送到服务器。即使数据仍在等待发送，你也可以继续发送数据，有时你可能只想在没有数据等待发送时才将新数据推送到服务器：

```
connection.onopen = function() {
  var interval = window.setInterval(function() {
    if (connection.readyState != WebSocket.OPEN) {
      clearInterval(interval);
    }
  }, 5000);
}
```

# 第 10 章 使用 WebSocket 与你的应用程序交互

# Java API

WebSocket 的 Java API 定义了接口，而不是实现。你可以编写此 API，但在运行时你需要一个实现来支持。如果你的应用程序运行在 Java EE 服务器或支持 WebSocket 的 Web 服务器上，已经提供了客户端和服务器实现。如果它是独立运行的，你需要找到一个独立的客户端或服务器实现（取决于你的需求）来部署。

# 客户端 API

客户端 API 构建在 `ContainerProvider` 类以及 `WebSocketContainer`、`RemoteEndpoint` 和 `Session` 接口之上。`WebSocketContainer` 提供所有的 WebSocket 功能，而 `ContainerProvider` 类提供了静态 `getWebSocketContainer` 方法来获取实现。`WebSocketContainer` 提供了重载的 `connectToServer` 方法，用于连接并启动握手。这些方法接受标记了 `@ClientEndpoint` 的 POJO、任何标记了 `@ClientEndpoint` 的 POJO 类型、`Endpoint` 类的实例或扩展 `Endpoint` 的类。如果你使用任何类变体方法，你还必须提供一个无参构造函数，它将被实例化。如果你使用 `Endpoint` 或扩展 `Endpoint` 的方法，你还必须提供 `ClientEndpointConfig`。当握手完成后，`connect` 方法返回一个 `Session`。你可以在 `Session` 上执行很多操作，最典型的关闭 Session（这将关闭 WebSocket 连接）或向远程端发送消息。

> 注意：WebSocket 的 Java API 定义了接口，而不是实现。你可以编写此 API，但在运行时你需要一个实现来支持。如果你的应用程序运行在 Java EE 服务器或支持 WebSocket 的 Web 服务器上，已经提供了客户端和服务器实现。如果它是独立运行的，你需要找到一个独立的客户端或服务器实现（取决于你的需求）来部署。

WebSocket `Endpoint` 有 `onOpen`、`onClose` 和 `onError` 方法在这些事件发生时被调用，而 `@ClientEndpoint` 类可以拥有标记了 `@OnOpen`、`@OnClose` 和 `@OnError` 的可选方法。`@ClientEndpoint` 类和扩展 `Endpoint` 的类可以指定一个标记了 `@OnMessage` 的方法来处理来自远程端的消息。使用注解类和方法，你对方法的参数有很大的灵活性。

`@OnOpen` 方法可以：

- 一个 `Session` 参数
- 一个 `EndpointConfig` 参数

`@OnClose` 方法可以：

- 一个 `Session` 参数
- 一个可选的 `CloseReason` 参数

`@OnError` 方法可以：

- 一个 `Session` 参数
- 一个必须的 `Throwable` 参数

`@OnMessage` 方法更为复杂。除了标准的可选 `Session` 参数外，它们必须恰好包含以下参数组合之一：

- 一个 `String` 用于接收整条消息
- 一个 `String` 加上一个 `boolean` 用于分块接收文本消息，在最后一个分块时将布尔值设置为 `true`
- 一个 Java 原始类型或原始包装类，用于接收转换为该类型的完整消息
- 一个 `java.io.Reader` 用于作为阻塞流接收文本消息
- 一个 `byte[]` 或一个 `java.nio.Buffer` 用于接收整条二进制消息
- 一个 `byte[]` 或一个 `ByteBuffer` 加上一个 `boolean` 用于分块接收二进制消息
- 一个 `java.io.InputStream` 用于作为阻塞流接收二进制消息
- `PongMessage` 用于自定义处理心跳响应
- 如果该端点注册了 `Decoder.Text`、`Decoder.Binary`、`Decoder.TextStream` 或 `Decoder.BinaryStream` 以转换为该类型，则任何对象均可。文本或二进制的消息类型必须与注册的解码器匹配。

一个端点只能有一个方法来处理打开、关闭和错误事件；然而，你最多可以有三种消息处理模式：文本消息最多一个，二进制消息最多一个，pong 消息最多一个。关于客户端 API 的最后说明：本章使用的 WebSocket 依赖是用于服务器 API 的，它包含了对客户端 API 的依赖。如果你需要编写一个仅作为 WebSocket 客户端的 Java 应用程序，你需要客户端 API 的 Maven 依赖：

```
<dependency>
  <groupId>javax.websocket</groupId>
  <artifactId>javax.websocket-client-api</artifactId>
  <version>1.0</version>
  <scope>provided</scope>
</dependency>
```

## 服务器 API

服务器 API 依赖于整个客户端 API，并添加了方法以程序化方式注册 `ServerContainer`、`extends EndpointConfig` 实例，或带有 `@ServerEndpoint` 注解的类。在 Servlet 环境中，你通过调用 `ServletContext.getAttribute("javax.websocket.server.ServerContainer")` 来获取 `ServerContainer`。在独立应用程序中，你需要按照你所使用的特定 WebSocket 实现的说明来获取 `ServerContainer` 实例。

然而，在几乎所有情况下（包括所有 Java EE Web 容器内部），你实际上并不需要获取 `ServerContainer`。相反，只需为你的端点类加上 `@ServerEndpoint` 注解；WebSocket 实现可以扫描你的类以寻找此注解，并自动为你选取并注册你的服务器端点。容器会为你的端点类创建一个新实例，为该端点接收到一个新的 WebSocket 连接，并在连接关闭后销毁每个实例。

使用 `@ServerEndpoint` 时，你至少需要指定指定的 `value` 属性，该属性指示了该端点响应的应用程序相对 URL。URL 路径必须以斜杠 `/` 开头，并可以包含模板。例如，考虑以下注解：

```
@ServerEndpoint("/game/{gameType}")
```

如果你的应用程序部署在 `https://www.example.org/app/game/chess`，那么我们将响应 `ws://www.example.org/app/game/chess`。那么，你端点中的任何 `@OnOpen`、`@OnError` 或 `@OnMessage` 方法都可以有一个带有 `@PathParam("gameType")` 注解的可选参数。端点中的方法可以处理逻辑，但你最多可以有三种消息处理模式：文本消息最多一个，二进制消息最多一个，pong 消息最多一个。



如果你的应用程序部署在 `https://www.example.org/app/game/chess`，那么我们将响应 `ws://www.example.org/app/game/checks`。那么，你端点中的任何 `@OnOpen`、`@OnError` 或 `@OnMessage` 方法都可以有一个带有 `@PathParam("gameType")` 注解的可选参数。端点中的方法可以处理逻辑，但你最多可以有三种消息处理模式：文本消息最多一个，二进制消息最多一个，pong 消息最多一个。关于客户端 API 的最后说明：本章使用的 WebSocket 依赖是用于服务器 API 的，它包含了对客户端 API 的依赖。如果你需要编写一个仅作为 WebSocket 客户端的 Java 应用程序，你需要客户端 API 的 Maven 依赖：

# 使用 WebSockets 创建多人游戏

“此游戏已经开始。”

```java
));
List<String> actions = session.getRequestParameterMap().get("action");
if (actions != null && actions.size() == 1) {
    String action = actions.get(0);
    if ("start".equalsIgnoreCase(action)) {
        Game game = new Game();
        game.gameId = gameId;
        game.player1 = session;
        TicTacToeServer.games.put(gameId, game);
    } else if ("join".equalsIgnoreCase(action)) {
        Game game = TicTacToeServer.games.get(gameId);
        game.player2 = session;
        game.ticTacToeGame = TicTacToeGame.games.start(gameId, username);
        this.sendJsonMessage(game.player1, game,
            new GameStartedMessage(game.ticTacToeGame));
        this.sendJsonMessage(game.player2, game,
            new GameStartedMessage(game.ticTacToeGame));
    }
}
} catch (IOException e) {
    e.printStackTrace();
    try {
        session.close(new CloseReason(
            CloseReason.CloseCodes.UNEXPECTED_CONDITION, e.toString()));
    } catch (IOException exception) {
}
```

```java
@OnMessage
public void onMessage(Session session, String message,
    @PathParam("gameId") long gameId) {
    Game game = TicTacToeServer.games.get(gameId);
    boolean isPlayer1 = session == game.player1;
    try {
        Move move = TicTacToeServer.mapper.readValue(message, Move.class);
        game.ticTacToeGame.move(move);
        if (isPlayer1 ? TicTacToeGame.Player.PLAYER1 :
            TicTacToeGame.Player.PLAYER2) {
            // move.getRow(),move.getColumn();
        }
        this.sendJsonMessage(isPlayer1 ? game.player2 : game.player1, game,
            new OpponentMadeMoveMessage(move));
        if (game.ticTacToeGame.isOver()) {
            if (game.ticTacToeGame.isDraw()) {
                this.sendJsonMessage(game.player1, game,
                    new GameIsDrawMessage());
                this.sendJsonMessage(game.player2, game,
                    new GameIsDrawMessage());
            }
        } else {
            boolean wasPlayer1 = game.ticTacToeGame.getWinner() ==
                TicTacToeGame.Player.PLAYER1;
            this.sendJsonMessage(game.player1, game,
                new GameOverMessage(wasPlayer1));
            this.sendJsonMessage(game.player2, game,
                new GameOverMessage(!wasPlayer1));
            game.player1.close();
            game.player2.close();
        }
    } catch (IOException e) {
        this.handleException(e, game);
    }
}

@OnClose
public void onClose(Session session, @PathParam("gameId") long gameId) {
    Game game = TicTacToeServer.games.get(gameId);
    if (game == null) {
        return;
    }
    boolean isPlayer1 = session == game.player1;
    if (game.ticTacToeGame == null) {
        TicTacToeGame.removeQueuedGame(game.gameId);
    } else if (!game.ticTacToeGame.isOver()) {
        game.ticTacToeGame.forfeit(isPlayer1 ? TicTacToeGame.Player.PLAYER1 : game.ticTacToeGame.Player.PLAYER2);
        Session opponent = isPlayer1 ? game.player2 : game.player1;
        this.sendJsonMessage(opponent, game, new GameForfeitedMessage());
        try {
            opponent.close();
        }
    }
}
```

# LISTING 10-1 (继续)

（GameForfeited），清除对手声占的单元格，并在游戏结束时通知用户。最后是 `move` 函数，当点击游戏单元格时会被调用，它会将你的移动发送到服务器。

## 列表 10-2: game.jsp

```
<--@elvariable id="action" type="java.lang.String"--%>
<!--@elvariable id="gameId" type="long"--%>
<!--@elvariable id="username" type="java.lang.String"--%>
<!DOCTYPE html>
<head>
  <title>游戏网站 : 井字棋</title>
  <link rel="stylesheet" href="http://cdn.cloudflare.com/ajax/libs/twitter-bootstrap/2.3.1/bootstrap.min.css" />
  <link rel="stylesheet" value="resource/stylesheet/ticTacToe.css" /> />
  <script src="http://code.jquery.com/jquery-1.9.1.js"></script>
  <script src="http://cdn.cloudflare.com/ajax/twitter-bootstrap/2.3.1/js/bootstrap.min.js"></script>
</head>
<body>
  <h2>井字棋</h2>
  <span class="player-label">你：</span> <span>${username}</span><br>
  <span class="player-label">对手：</span> <span></</span>
  <span id="opponent"><i>等待中...&nbsp;</i>/</span>
  <div id="status">Container</div>
  <div id="gameContainer">
    <div class="row">
      <div id="r00" class="game-cell" onclick="move(0, 0);">&nbsp;</div>
      <div id="r01" class="game-cell" onclick="move(0, 1);">&nbsp;</div>
      <div id="r02" class="game-cell" onclick="move(0, 2);">&nbsp;</div>
    </div>
    <div class="row">
      <div id="r10" class="game-cell" onclick="move(1, 0);">&nbsp;</div>
      <div id="r11" class="game-cell" onclick="move(1, 1);">&nbsp;</div>
      <div id="r12" class="game-cell" onclick="move(1, 2);">&nbsp;</div>
    </div>
    <div class="row">
      <div id="r20" class="game-cell" onclick="move(2, 0);">&nbsp;</div>
      <div id="r21" class="game-cell" onclick="move(2, 1);">&nbsp;</div>
      <div id="r22" class="game-cell" onclick="move(2, 2);">&nbsp;</div>
    </div>
  </div>
  <div id="modalWaiting" class="modal hide fade">
    <div class="modal-header"><h3>请稍候...</h3></div>
    <div class="modal-body" id="modalWaitingBody">&nbsp;</div>
  </div>
  <div id="modalError" class="modal hide fade">
    <div class="modal-header">
      <button type="button" class="close" data-dismiss="modal">&times;
      </button>
      <h3>错误</h3>
    </div>
</body>
```

*项目*

## 列表 10-2（续）

```
</div>

<div class="modal-body" id="modalError">发生了一个错误。
</div>
<div class="modal-footer">
<button class="btn btn-primary" data-dismiss="modal">确定</button>
</div>
<div id="modalGameOver" class="hide fade">
<div class="modal-header"><button type="button" class="close" data-dismiss="modal">&times;

```:url>');} catch(error) {

  modalWaiting.modal('hide');

  modalErrorBody.text(error);

  modalErrorBody.modal('show');

  return;

}

server.onopen = function(event) {

  modalWaitingBody.text('等待对手加入游戏。');

  modalWaitingBody.modal({ keyboard: false, show: true });

};

window.onbeforeunload = function () {

  server.close();

};

server.onclose = function(event) {

  if(event.wasClean || event.code != 1000) {

    toggleTurn(false, '游戏因错误结束！');

    modalWaiting.modal('hide');

    modalErrorBody.text('代码 ' + event.code + ': ' + event.reason);

    modalErrorBody.modal('show');

  }

};

server.onerror = function(event) {

  modalWaiting.modal('hide');

  modalErrorBody.text(event.data);

  modalErrorBody.modal('show');

};

server.onmessage = function(event) {

  var message = JSON.parse(event.data);

  if(message.action == 'gameStarted') {

    if(message.game.player1 == username) {

      opponentUsername = message.game.player2;

    } else {

      opponentUsername = message.game.player1;

    }

    opponent.text(opponentUsername);

    toggleTurn(message.game.nextMove);

    modalWaiting.modal('hide');

  } else if(message.action == 'opponentMove') {

    $('#r' + message.row + '+' + message.column)

      .unbind('click')

      .removeClass('game-cell-selectable')

      .addClass('game-cell-taken');

    toggleTurn(true);

  } else if(message.action == 'gameOver') {

    toggleTurn(false, '游戏结束！');

    if(message.winner) {

      modalGameOverBody.text('恭喜，你赢了！');

    }

  }

```

## 列表 10-2（续）

```

modalGameOverBody.text('用户 ' + opponentUsername + ' 输了游戏。');

modalGameOver.modal('show');

else if (message.action == 'gameDraw') {

  toggleTurn(false, '平局。没有获胜者。');

  modalGameOverBody.text('游戏平局结束。没有人赢！');

  modalGameOver.modal('show');

} else if (message.action == 'gameForfeited') {

  toggleTurn(false, '你的对手放弃了！');

  modalGameOverBody.text('用户 ' + opponentUsername + ' 了游戏。你赢了！');

  modalGameOver.modal('show');

}
```



```javascript
var toggleTurn = function (isMyTurn, message) {
  var myTurn = isMyTurn;
  if (myTurn) {
    status.text(message || '轮到你了！');
    $('.game-cell:not(.game-cell-taken)')
      .addClass('game-cell-selectable');
  } else {
    status.text(message || '等待对手移动。');
    $('.game-cell-selectable')
      .removeClass('game-cell-selectable');
  }
};

move = function (row, column) {
  if (!isMyTurn) {
    modalErrorBody.text('不是你的回合！');
    modalError.modal('show');
    return;
  }
  if (server == null) {
    server.send(JSON.stringify({ row: row, column: column }))).unbind('click');
    $('#r' + row + 'c' + column).removeClass('game-cell-selectable')
      .addClass('game-cell-player-taken');
    toggleTurn(false);
  } else {
    modalErrorBody.text('未连接到服务器。');
    modalError.modal('show');
  }
};
});
</script>
</html>
```

## 玩 WebSocket 井字棋

现在你已经查看了代码并了解了所有部分是如何组合在一起的，你可以执行以下操作：

1. 编译 `Game-Site` 项目。
2. 在调试器中启动 `Tomcat`，并打开两个浏览器（例如 `Firefox` 和 `Safari`，或者 `Internet Explorer 10` 和 `Chrome`）。将它们调小，以便并排放置或堆叠放置。
3. 在两个浏览器中访问 `http://localhost:8080/games/ticToe`。目前应该还没有列出游戏。
4. 在一个浏览器中点击“开始游戏”，在提示中输入你的名字或喜欢的用户名，然后点击确定。你将进入游戏页面，并看到“等待对手”的消息。
5. 在另一个浏览器中，刷新列表页面，你应该看到处理中的游戏。点击该游戏并为对手输入一个不同的名字或用户名。一旦你进入游戏页面，第一个浏览器中的等待消息就会消失。你会注意到这几乎是瞬间完成的。两个浏览器中，你都会看到一条显示“轮到你了”的消息，而另一个显示“等待对手移动”。
6. 往回进行移动。

## 代码列表 10-3: `ClusterNodeServlet.java`

```java
@ClientEndpoint
public class ClusterNodeServlet extends HttpServlet {

    private Session session;
    private String nodeId;

    @Override
    public void init() throws ServletException {
        this.nodeId = this.getParameter("nodeId");
        String path = this.getServletContext().getPath() + "/clusterNodeSocket/" + this.nodeId;
        try {
            URI uri = new URI("ws://localhost:8080" + path, null, null);
            this.session = ContainerProvider.getWebSocketContainer().connectToServer(uri, uri);
        } catch (URISyntaxException | IOException | DeploymentException e) {
            throw new ServletException("Cannot connect to " + path + ".", e);
        }
    }

    @Override
    public void destroy() {
        try {
            this.session.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        ClusterMessage message = new ClusterMessage(this.nodeId,
            request.getParameter("ip") + " " + request.getRemoteAddr() +
            "?query=*" + request.getQueryString() + "&query=*");
        OutputStream outputStream = this.session.getBasicRemote().getStream();
        ObjectOutputStream outputStream = new ObjectOutputStream(outputStream);
        outputStream.writeObject(message);
        response.getWriter().append("OK*");
    }

    @OnMessage
    public void onMessage(InputStream input) {
        try {
            ObjectInputStream inputStream = new ObjectInputStream(input);
            ClusterMessage message = (ClusterMessage) inputStream.readObject();
            System.out.println("Node " + this.nodeId + " received message from cluster; node = " + message.getNodeId() + ", message = " + message.getMessage());
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

## 代码列表 10-3 (续)

### 传输与接收二进制消息

你可能注意到 `ClusterNodeServer` 使用 Java 序列化通过 WebSocket 连接发送和接收实现了 `Serializable` 的 `ClusterMessage`。为了实现这一点，WebSocket 消息必须是二进制的。这与井字游戏服务器端点不同，后者将消息转换为 JSON 并将其作为文本消息发送。Java 序列化比 JSON 快，因此在可能的情况下，使用 Java 序列化会更好。然而，只有当双方端点都是 Java 程序时，你才能这样做。如果只有一端是 Java，你就必须使用不同的技术，例如 JSON。尽管 `ClusterNodeServer` 通过 `OutputStream` 发送和接收二进制消息，但 `ClusterNodeEndpoint` 使用的是字节数组。在这种情况下，使用稍微多一点的代码（如 `ObjectStreams`）会更简单，因此学习这两种方法是有价值的。这取决于你的数据来自何处或者你想对它做什么。如果你需要发送已经以字节数组形式存在的数据，使用该数据会更简单。另一方面，如果你处理的是流，通常坚持使用流更简单。端点的唯一职责是将一个节点的消息回显到所有其他节点，并在节点加入或离开集群时通知这些节点。在另一种场景下，你可能没有一个连接并回显所有消息的中央端点。相反，每个节点直接连接到所有其他节点。这取决于你的用例和应用程序的需求。

## 代码列表 10-4: `ClusterNodeEndpoint.java`

```java
@ServerEndpoint("/clusterNode/{nodeId}")
public class ClusterNodeEndpoint {

    private static final List<Session> nodes = new ArrayList<>();

    @OnOpen
    public void onOpen(Session session, @PathParam("nodeId") String nodeId) {
        System.out.println("INFO: Node " + nodeId + " connected to cluster.");
        ClusterMessage message = new ClusterMessage(nodeId, "Joined the cluster.");
        try {
            byte[] bytes = ClusterNodeEndpoint.toByteArray(message);
            for (Session s : nodes) {
                s.getBasicRemote().sendBinary(ByteBuffer.wrap(bytes));
            }
        } catch (IOException e) {
            System.err.println("ERROR: notifying new node");
            e.printStackTrace();
        }
        nodes.add(session);
    }

    @OnMessage
    public void onMessage(Session session, byte[] message) {
        try {
            for (Session s : nodes) {
                if (s != null) {
                    s.getBasicRemote().sendBinary(ByteBuffer.wrap(message));
                }
            }
        } catch (IOException e) {
            System.err.println("ERROR: handling message on server");
            e.printStackTrace();
        }
    }

    private static byte[] toByteArray(ClusterMessage message) throws IOException {
        try (ByteArrayOutputStream outputStream = new ByteArrayOutputStream()) {
            ObjectOutputStream stream = new ObjectOutputStream(outputStream);
            stream.writeObject(message);
            return outputStream.toByteArray();
        }
    }
}
```



# 测试模拟集群

测试模拟集群应用程序非常简单。只需按照以下步骤操作：

1. 编译应用程序并在你的 IDE 中运行 Tomcat。
2. 在浏览器中访问 `http://localhost:8080/clusterNode`，你应该在调试器输出中看到以下消息。这是第一个 Servlet 的 `init` 方法被调用并连接到 WebSocket 服务器端点的结果。

   ```
   INFO: Node 1 connected to cluster.
   ```

3. 现在访问 `http://localhost:8080/clusterNode2`。这次你会看到几条消息。在这种情况下，第二个 Servlet 实例连接到了端点，并在向第一个 Servlet 发回消息时。

   ```
   INFO: 2 connected to cluster.
   INFO (Node 1): Message received from cluster; node = 2, message = Joined the cluster.
   INFO (Node 1): Message received from cluster; node = 2, message = request(ip:'127.0.0.1',query='*')
   ```

4. 尝试第一个 URL，但后面添加此查询字符串：`http://localhost:8080/clusterNode1#helloworldfoo`。注意这里没有连接消息，因为两个 Servlet 都已经启动了。

   ```
   INFO (Node 2): Message received from cluster; node = 1, message = request(ip:'127.0.0.1',query='helloworldfoo')
   ```

5. 最后一次，再次尝试集群，但带有查询字符串：`http://localhost:8080/clusterNode2?baz=qux&animal=dog`。

   ```
   INFO (Node 1): Message received from cluster; node = 2, message = request(ip:'127.0.0.1',query='baz=qux&animal=dog')
   ```

6. 如果你想进一步尝试，创建另一个 Servlet 实例并将其映射到 `/cluster3`；然后连接并启动应用程序。尝试访问三个 URL，你会发现 Servlet 响应了 GET 请求，另外两个 Servlet 接收到了该消息。

# 为客户支持应用程序添加“与支持聊天”

WebSocket 的用处最普遍的例子是互联网聊天。许多应用程序直接从你的桌面提供聊天功能，并使用某种服务提供商来路由聊天消息。这在网站上也很常见，许多社交网络、论坛和在线社区都提供聊天功能。通常情况下，这有两种工作方式：

- 这种有两个及以上的参与者，通常是无限制的。聊天室通常也是公开的，只需在该网站拥有身份即可加入。
- 这种只有两个参与者。其他人看不到聊天内容。

无论是私密聊天还是聊天室聊天，服务器端的实现方式本质上是相同的：它接受连接，关联所有相关的连接，并将传入的消息回显给所有已连接的连接。它还会发布兴趣事件，例如有人连接或断开聊天时。唯一的区别在于每个连接之间关联的连接数量。

跨国公司 Wiger Corporation 需要其客户支持应用中使用支持聊天功能。支持是一个基本概念：在紧急情况下，客户可能需要持续的帮助。客户可以登录支持网站并与客户支持代表进行私密聊天。这通常只在特定时段进行。此外，客户通常有权在会话结束后下载聊天记录或让聊天记录通过电子邮件发送给他们。在本节中，你将通过 `Customer-Support-v8` 项目，在客户支持应用中添加“与支持聊天”。你应该使用 WebSockets 在 wrx.com 下载站点上添加“与支持聊天”，因为书中的内容不足以打印它。

`main.css` 样式有一些更改，并有一个新的 `chat.css` 样式来创建样式页面。`/WEB-INF/tags/template/main.tag` 文件包含了一些第三方 CSS 和 JavaScript 库，并为页面定义了几个 JavaScript 函数。你会发现 `basic.tag` 现在有了用于创建新聊天支持或查看聊天请求的功能。

通常，自定义的支持代表可以查看并响应待处理的聊天请求，但客户支持应用尚未具备具有用户权限的完整安全性。你将在本书的第四部分添加这些功能。`ChatServlet` 的任务相当简单：它管理聊天会话的列表、创建和加入。`doPost` 方法设置 `Expires` 和 `Cache-Control` 头部，以确保浏览器不缓存聊天页面。`/WEB-INF/jsp/view/list.jsp` 负责列出客户支持响应的待处理聊天。`Config` 类还为 `/chat` URL 添加了 `AuthenticationFilter`，以便 `ChatServlet` 受到保护。

# 使用编码器和解码器翻译消息

在之前的 `Message` 章节中，你已经学习了可以为 `@OnMessage` 方法指定的所有可能参数。记住：

- 只要你提供一个能够将输入文本或二进制消息翻译为该对象的解码器，就可以指定任何 Java 对象作为参数。
- 只要你提供一个能够将该对象翻译为文本或二进制消息的编码器，就可以使用 `RemoteEndpoint.Basic` 或 `RemoteEndpoint.Async` 的 `setObject` 方法发送任何对象。
- 通过实现 `Encoder.Binary`、`Encoder.BinaryStream`、`Encoder.Text` 或 `Encoder.TextMessage` 并在 `@ClientEndpoint` 或 `@ServerEndpoint` 的 `encoders` 属性中指定这些类来提供编码器。

你可以实现 `Decoder.Binary`、`Decoder.BinaryStream`、`Decoder.Text` 或 `Decoder.TextStream`，并使用端点注解的 `decoders` 属性为你的消息提供解码器。

```java
public class ChatMessage {

    private OffsetDateTime timestamp;

    private Type type;

    private String user;

    private String content;

    // accessor and mutator methods

    public static enum Type {

        STARTED, JOINED, ERROR, LEFT, TEXT

    }

}
```

之前的 `ChatMessage` 代码显示它是一个简单的 POJO。WebSocket API 同时需要编码器和解码器，以便你的应用程序能够发送和接收消息。列表 10-5 包含一个用于编码和解码 `ChatMessage` 的简单类。它使用 Jackson Processor 来编码和解码消息。编码器方法接收一个 `ChatMessage` 和一个 `OutputStream`，通过将其转换为 JSON 来编码消息并将其写入 `OutputStream`。该方法执行相反的操作：给定一个 `InputStream`，它读取并反序列化 JSON `ChatMessage`。`init` 和 `destroy` 方法在编码器和解码器接口中都有指定。它们在这里没有被使用，但如果你需要初始化或释放编码器和解码器使用的资源时，它们非常有用。

## 列表 10-5: ChatMessageCodec.java

```java
public class ChatMessageCodec
    implements Decoder.BinaryStream<ChatMessage>,
    Encoder.BinaryStream<ChatMessage> {
    private static final ObjectMapper MAPPER = new ObjectMapper();
    static {
        MAPPER.findAndRegisterModules();
    }
    @Override
    public void encode(ChatMessage chatMessage, OutputStream outputStream) throws IOException {
        try {
            MAPPER.writeValue(outputStream, chatMessage);
        } catch (IOException e) {
            throw new EncoderException(e);
        }
    }

    @Override
    public ChatMessage decode(InputStream inputStream) throws IOException {
        try {
            return MAPPER.readValue(inputStream, ChatMessage.class);
        } catch (IOException e) {
            throw new DecoderException(e);
        }
    }
}
```

## 在客户支持应用程序中添加“与支持聊天”

```java
return;

String username = (String)session.getAttribute("username");
session.getUserProperties().put("username"
```

继续

## 列表 10-6（续）

```java
}

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
        return (ArrayList<Session>)session.getAttribute(WS_SESSION_PROPERTY);
    } catch (IllegalStateException e) {
        return new ArrayList<>();
    }
}

private Session close(Session s, ChatMessage message) { ... }
private Session getOtherSession(ChatSession c, Session s) { ... }
public static class EndpointConfigurator
    extends ServerEndpointConfigurator {
    @Override
    public void modifyHandshake(ServerEndpointConfig config, HandshakeRequest request, HandshakeResponse response) {
        super.modifyHandshake(config, request, response);
        config.getUserProperties().put(
            ChatEndpoint.HTTP_SESSION_PROPERTY, request.getHttpSession()
        );
    }
}
```

# 编写 JavaScript 应用程序

`WEB-INF/jsp/view/chat/chat.js` 文件包含了支持聊天的用户界面。大部分代码是用于展示、连接和错误处理的，这些你之前在井棋游戏中已经见过了。特别重要的是 `onmessage` 事件和 `send` 函数，它们分别处理接收和发送消息。由于此应用程序使用 JSON 在浏览器和服务器之间传递消息，因此使用文本消息而不是二进制消息会更简单。然而，你还没有见过如何在 JavaScript 中处理 WebSocket 消息，因此本示例正演示了这一点。

```javascript
server.onmessage = function(event) {
  if (event.data instanceof ArrayBuffer) {
    var message = JSON.parse(String.fromCharCode.apply(
      null, new Uint8Array(event.data)
    ));
    objectMessage(message);
    if (message.type == 'JOINED') {
      otherJoined = true;
      if (username != message.user) {
        infMessage('你现在正在与 ' + 
        message.user + '聊天...');
      }
    }
  } else {
    modalError.body.text('意外的数据类型 [' + 
      typeof(event.data) + '].');
    modalError.modal('show');
  }
};
nsend = function() {
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
    } catch(error) {
      modalError.body.text(error);
      modalError.modal('show');
    }
  }
};
```

# 11 使用日志监控你的应用程序

本章

- 关于日志的一切
- 什么是日志级别？
- 什么日志设施适合你？
- 如何将日志集成到你的应用程序

## WROX 代码下载

你可以在下载选项卡找到 wrox。本章代码分为以下部分：

- 日志集成
- 客户支持

## 本章新增 Maven 依赖

除了之前引入的 Maven 依赖外，你还需要：

```xml
<dependency>
  <groupId>org.logging.log4j</groupId>
  <artifactId>log4j-api</artifactId>
  <version>2.0</version>
  <scope>compile</scope>
</dependency>
```

```xml
<dependency>
    <groupId>org.logging.log4j</groupId>
    <artifactId>log4j-core</artifactId>
    <version>2.0</version>
    <scope>runtime</scope>
</dependency>
```

```xml
<dependency>
    <groupId>org.logging.log4j</groupId>
    <artifactId>log4j-jcl</artifactId>
    <version>2.0</version>
    <scope>runtime</scope>
</dependency>
```



</dependency>

```xml
<dependency>
    <groupId>org.logging.log4j</groupId>
    <artifactId>log4j-slf4j-impl</artifactId>
    <version>2.0</version>
    <scope>runtime</scope>
</dependency>
```

```xml
<dependency>
    <groupId>org.logging.log4j</groupId>
    <artifactId>log4j-taglib</artifactId>
    <version>2.0</version>
    <scope>runtime</scope>
</dependency>
```

## 理解日志的概念

想象这样一个场景：你收到了一个关于应用程序 bug 的报告。根据客户支持提供的复现步骤，你每次都能复现该 bug。问题是，一旦你在调试器中设置了断点，问题就消失了。无其妙。这可能（但并非一定）意味着问题与多线程有关，命中断点会降低执行速度，足以掩盖问题。你该如何找出问题所在？应用程序日志对于成功的调试、故障排除、监控和错误报告至关重要。在本章中，你将探索日志的概念、API 和实现，并将其集成到你的应用程序中。

## 为什么你应该记录日志

作为个人选择，我们倾向于不在获取堆栈跟踪或一两个变量的值之外使用调试器。原因之一是，在复杂的数据结构和控制流中很容易迷失细节；我们发现，单步执行程序比深入思考并在关键点添加输出和自检代码更有效。点击语句花费比扫描良好放置的输出要长。决定需要在何处放置 print 语句以单步执行到代码的关键区域，即使我们已经知道那是在哪里。更重要的是，调试语句可以随程序保留；而调试器会话是瞬即逝的。

> KERNIGHAN, BRIAN W. AND ROB PIKE. THE PRACTICE OF PROGRAMMING. READING: ADISON WESLEY LONGMAN, INC., 1999. 119.

有很多理由说明你应该记录日志。前面的引言强调了日志的重要点——以及调试器的缺点。需要注意的是，自那本书出版以来已经多年，调试器已经有了很大进步。在如今的世界，在 IDE 中启动调试器并单步执行应用程序的运行是不言而喻的。Java 调试器的很多方面都是最好的，在今天的 Java IDE 中进行调试使得静态、实例和变量的检查和评估变得非常简单。在大多数 IDE 中，你可以在断点处运行时评估任意表达式，并可以在不重启 Java 虚拟机的情况下更改、重新编译和加载代码。

但尽管如此，仅仅调试是不够的。前面的假设只是调试器产生障碍的众多例子之一。此外，有时无法使用调试器。考虑一种情况：客户问题无法在开发环境中甚至在质量保证环境中复现。在大多数情况下，将调试器附加到客户运行的生产应用程序上并不是一个选项。

面对现实吧：Bug 不是计划好的。你把应用程序写得非常完美，Bug 仍然会出现。你可以采用许多技术并使用许多工具来检测并尽量减少代码中的 Bug，但你永远无法避免它们。因此，在没有调试器的情况下记录日志是有意义的。

调试应用程序并不是你记录日志的唯一理由。通常，你需要被意外事件的通知，例如崩溃、应用程序配置的更改、行为启动或停止、数据变化。你还需要监控应用程序的性能，以确保它正常运行并能够承受某种活动。所有这些需求——以及更多——说明了你为什么应该记录日志。

在 Java 早期（直到 Java 1.4，`java.util.logging` 并不是框架的一部分），许多开发者使用 `System.err.println()` 和 `System.out.println()` 来“记录”错误和有趣信息。即使在今天，许多应用程序甚至库仍然充满了这样的语句。这些流可以被重定向到单独的文件，这具有一定的用途，但由于它们缺乏粒度和“始终开启”的特性会导致日志迅速填满并阻碍应用程序的性能。理想情况下，你想要一种容易自定义的东西，可以配置为显示少量或大量信息，根据包或类显示不同的信息，并且（最重要的是）不阻碍性能。

## 你可能想在日志中看到的内容

考虑到之前描述的理想日志系统——可自定义、可配置、按包或类可变且性能良好——关于你想要放入日志文件的所有信息。你可能会想到很多事情，而且从技术上讲可能性是无限的，但这里是一些入门的基础想法：

当应用程序崩溃或意外退出时，记录尽可能详细的信息（导致崩溃的所有内容）是关键的。堆栈跟踪、线程转储，甚至是堆转储。JVM 崩溃不是容易记录的事件。崩溃的大部分本质导致了日志记录无法工作。因此，大多数 JVM 都内置了工具来记录这些事件的发生。例如，Oracle 和 OpenJDK JVM 有命令行选项 `-XX:HeapDumpOnOutOfError`，它让 Java 在 JVM 耗尽内存时生成堆转储。请考虑你的 JVM 厂商的文档以获取更多信息。

当错误发生时，你应该记录你关于该错误的任何信息（类型、消息、堆栈跟踪以及错误发生时应用程序正在做什么）。然后，你可以向用户显示一条简短的错误消息，告诉他们出了问题，而不会泄露可能损害你系统的细节（如文件或 SQL 查询）。

有时会产生一些不完全是错误且不会阻止操作继续的问题，但可能属于日后某个时间要处理的问题。这些问题表明你的应用程序存在潜在的但非确定的问题。你应该记录这类情况，包括详细的消息和应用程序正在做什么。有时，堆栈跟踪也适用于这些情况。你可能认为这些是“警告（warnings）”。

有某些重要的事件，你可能想在日志中看到。记录诸如实体的创建、组件的启动、用户成功登录或任务的执行等内容可以帮助你了解系统是否运行正常。

当你想要追踪一个问题时，你想看到关于方法和例程执行的详细信息，包括相关变量的值。然而，你可能不想一直看到这些，创建这些数据可能会阻碍性能。

在最困难的调试场景中，你可能需要看到某些内容何时结束或退出，以及每个方法的参数值和返回值。在正在执行的循环中，你可能需要每次迭代的数据。这在高负载场景下当然是海量信息，所以你绝对不想一直看到它，而且也不是所有事件都要如此。在某些情况下，日志记录必须是安全的。总的来说，这并不是详尽的列表。

在 Linux 操作系统上，syslog 是所有进程都可以写入的设施。这些具体细节不在本书的讨论范围内，但本质上，日志事件被写入到由操作系统日志工具管理的平面文件中，并以标准化的格式存储在中心位置。Windows 通过 Windows 事件日志（Windows Event Log）提供了类似的功能，该数据以 XML 格式存储，并且操作系统内置了日志查看器。

滚动文件（rolling files）的概念可以应用于所有模式（在 syslog 和事件日志的情况下，它是自动适的）。当日志系统被设置为使用滚动文件时，它会定期更改其记录的文件。日志记录基于时间——例如，Tomcat 每天都会获得一组新的日志——而在其他情况下，当日志文件达到特定大小时，日志文件会被备份到一个索引文件名，并启动一个新的日志文件。

## 套接字 (Sockets)

套接字是一种常见的日志方法，但在某些情况下非常有用。日志事件被翻译成某种网络通信格式，然后通过网络发送到其他某个位置。有时接收的应用程序在同一台机器上；有时在同一网络的不同机器上；有时在不同的网络上（甚至在地球的另一端）。在几乎所有情况下，套接字连接的另一端都是一个专用的记录器，其唯一目的是以某种方式记录和持久化日志。

## SMTP 和 SMS

尽管发送电子邮件来记录日志事件听起来很奇怪，但请想想你有多想在应用程序发生错误时及时获知。在普通的日志记录中，很少看到电子邮件和 SMS 日志通知。在作者看到的每种情况下，电子邮件和 SMS 日志仅预留给严重的应用程序错误，例如导致系统操作终止或组件失败的异常。这通知系统管理员需要立即处理问题。

## 数据库 (Databases)

应用程序出于各种原因将日志记录到某种类型的数据库是非常常见的。数据库是高效、事务安全的存储手段，极易于查询和过滤数据。如果你正在记录审计数据，很可能会使用数据库来存储这些数据。将日志记录到数据库的缺点也显而易见。第一是速度：由于带有网络栈和数据库的开销，写入索引表的速度比写入文件慢得多（小规模下）。但随后存在数据库大小的问题：许多数据库对存储量有限制，当达到这些限制时，性能会大幅下降。插入操作可能需要几分之一秒或更长时间。对于许多人来说，为了可以轻松清除的日志而付出这样的代价是不合理的。

引入 NoSQL 数据库，它避免了关系型数据库为日志系统带来的许多问题。这些数据库以关系型的方式存储数据，这消除了大部分开销，并能够高效地存储数 GB 或 TB 级的数据。用于此类任务的最流行的数据库之一是 MongoDB，它是一种 NoSQL 数据库。该数据库以二进制 JSON (BSON) 格式存储数据，这是一种极其压缩且高效的存储手段。

MongoDB 牺牲了读取性能——在过滤数据集时可能会很慢——以换取写入性能。当数据库大小超过几个 GB 时，向 MongoDB 插入数据比流行的关系型数据库系统快几个数量级。对于日志系统来说这是一个巨大的优势，因为你希望尽量对应用程序性能的影响。MongoDB 与大多数文档数据库一样并不完全符合 ACID 标准，但如果你正确结构化你的文档，可以将丢失数据的概率降低到与 ACID RDBMS 相同的水平。

## 使用日志级别和类别 (USING LOGGING LEVELS AND CATEGORIES)

在上一节中，你探索了日志的一些概念，包括对你可能想在应用程序日志中看到的各种类型信息的概述。在你探索这个主题时，可能很快发现存在不同类型的日志事件，并且并不是所有类型都会被记录。这通常被称为日志级别（logging levels）概念。有时，级别是不够的。你通常需要应用程序特定部分的的最详尽日志细节，而不是整个程序。如果你能对日志事件进行分类，你的日志数据将变得更有用。在本节中，你将研究日志级别和类别。你还将查看日志偏移（log shifting）的概念以及它与日志分类的关系与区别。

## 为什么会有不同的日志级别？(Why Are Different Logging Levels?)

你可能已经回答了这个问题。到本章为止，你已经确定了很多应该包含在日志中的信息；有些指示严重错误，其他类型代表极其细微且大量的调试细节。如果你一直开启所有内容，你的日志每秒可能会增长几兆字节。（相信我，我见过这种情况！）这不仅会阻碍应用程序的性能，还会让你的日志变得基本上毫无用处。当你需要为一秒的程序执行筛选几 MB 的日志数据时，还不如不留任何日志。

级别表示所记录事件的严重程度或相对重要性。使用“相对”一词是因为事实确实如此：一个日志级别要么比另一个重要，要么没那么重要。日志级别的名称并没有定义它所传递消息的实际重要性；仅仅是该消息与其他消息相比的重要性。在系统中，日志级别通常是整数，仅此而已。在其他系统中，日志级别被赋予一个名称以提供某些有用的语义。对于日志级别的数量、顺序或名称，没有公认的标准。几乎你可以定义的每个系统都可以以不同的方式定义它们，这取决于你认为什么最适合你。

## 日志级别定义 (Logging Levels Defined)

尽管没有公认的标准，但在为 Java 应用程序编写的大多数日志系统中出现了常见的模式。日志级别通常被命名以赋予它们某些高层含义，在大多数系统中存在六个到十个不同的级别。表 11-1 列出了从严重到轻微的常见类型，以及 `java.util.logging` 中定义的常量。

### 表 11-1：常见日志级别 (TABLE: Common Logging Levels)

| 通用名称 (GENERIC NAME) | 级别常量 (Level CONSTANT) | 语义含义 (SEMANTIC MEANING) |
| :--- | :--- | :--- |
| 致命错误 / 崩溃 (Fatal Error / Crash) | 无对应项 | 表示最严重的错误。通常这些错误会导致应用程序崩溃或至少提前终止。 |
| 错误 (Error) | SEVERE | 表示发生了严重问题 |
| 警告 (Warning) | WARNING | 表示发生了某些可能不是问题但可能需要查看的事件 |
| 信息 (Information) | INFO | 如名称所示，这些信息性项目对应用程序监控和调试可能有用。 |
| 配置细节 (Configuration Details) | CONFIG | 此类别的事件通常包含配置信息。你通常在应用程序或组件启动时看到它。 |
| 调试 (Debug) | FINE | 表示调试信息，通常包含变量的值 |
| 跟踪级别 1 / 跟踪级别 2 (Trace Level 1 / Trace Level 2) | FINER / FINEST | 这些级别代表不同层次的应用程序跟踪。许多日志框架只定义了一个跟踪级别 |

在 Java 的几乎所有情况下（包括本章中看到的所有示例），日志类别都由命名的日志器实例表示，并且每个日志器都可以分配不同的级别。通过这种方式，通常情况下，两个不同的类可以拥有不同的日志器，你可以设置其中一个用于记录数据，而另一个仅记录警告。事实上，这正是大多数情况下“类别”（categories）的使用方式：在开发期间，每个类都有自己的日志器，通常以其完全限定的类名命名。根据日志系统的不同，通常会建立一个日志器层级结构，使得未定义级别赋值的日志器可以从某个父级日志器继承该级别。

## 日志筛选是如何工作的

日志筛选（Log sifting）在概念上与日志分类相似，但用途略有不同。通过日志筛选，不同类型或取向的事件会被记录到不同的位置（不同的文件、不同的数据库表或文档等）。在某些方面，这与分类的理念是相同的，区别在于分类通常定义的是不同的日志级别，而不是日志目标。大多数日志框架都允许你通过使用类别进行筛选，用一个功能解决了两个问题。另一些框架则提供了使用类别以及日志事件的其他属性进行筛选的能力（通常在某种过滤器中）。在 Java 中，所有主要的日志框架都允许根据日志类别进行筛选，即使不是基于每个日志事件的更多属性。你将在接下来的两个章节中进一步探讨筛选的话题。

## 选择日志框架

在理解应用程序的日志需求之后，你的下一个任务是选择一个日志框架。这并不意味着要使用第三方框架——它可能意味着创建自己的。然而，在几乎你遇到的所有情况下，都能找到经过行业测试的日志框架并对其进行配置以满足你的需求，这意味着创建自己的仅仅是一项不必要的任务。在本节中，我们将检查两个需要记住的重要指南，并查看一些现有的日志框架。

## API 与实现分离

考虑这样一个场景：你编写了一个包含数千个类的大型企业级应用程序。这些类大部分（那些不是 POJO 的类）都使用了日志。经过仔细研究，你选择并将一个行业标准的日志系统集成到应用程序中。一周后，你的工程团队告诉你，你选择的 syslog 输出并不足够，需要数据库日志。不幸的是，你选择的日志系统不支持数据库日志。你能做什么？你可以扩展日志系统，但实际上已经有一个非常好的日志系统支持数据库日志，你更倾向于使用它。然而，如果你发现需要更改数千个类来使用不同的日志系统，这项工作可能会花费数周时间并为你的公司带来数千美元。

这种场景中的根本问题在于，你使用的日志 API 与底层实现紧密耦合。你无法在不更改代码中所有使用日志的地方的情况下切换实现。如果你事先编写了一个简单的日志 API 来在代码中隐藏底层实现，你就可以避免这个问题。那么，要更换框架，你所做的只是更改你 API 中的少数几个类；应用程序的其他部分可以像往常一样继续使用你的 API 进行日志记录。坦率地说，这在日志框架世界中并不是一个新概念，而且你可能甚至不需要自己写这个 API。

Java 平台内置的标准的 `java.util.logging` 框架是日志 API 与实现分离的一个示例。`java.util.logging.LogManager` 类负责创建并返回 `Logger` 实例，并将这些工作委托给默认实现。开发者可以扩展 `LogManager` 并指定系统属性来提供标准日志 API 的替代实现。

标准实现具有处理器（handlers），可以写入文件、流、套接字、控制台和内存。当你可能疑惑为什么不能使用标准日志功能时，简单的答案是：“你可以用”。在许多情况下，对于应用程序而言，内置日志是完全足够的。然而，它有一个缺点，使得在 Web 应用程序中使用非常困难，甚至是不可能的：它从系统属性加载配置，而不是类路径（classpath）。由于这个原因，部署在相同容器中的两个 Web 应用程序不能具有不同的日志配置，除非容器扩展了日志实现。Tomcat 做到了这一点，但并不是所有容器都这样做，因此依赖它们是不可移植的。相反，最好找到其他结合了独立 API 和实现的解决方案。

## 性能

显然，无论你处理应用程序的哪个部分，性能都是一个巨大的考虑因素，日志记录也不例外。然而，请花几秒钟考虑写入文件、套接字、数据库或电子邮件的过程。这些任务在输入/输出操作完成之前花费大量时间处于阻塞状态，而阻塞是一种耗时性的情况。没有办法可以规避这一点。

以下是影响性能的关键情况：

- 在禁用日志时调用 debug 不应增加毫秒级延迟。
- 在最糟糕的情况下，两个 API 都可以创建自定义适配器，这可能会增加时间。
- 当 API 未提供支持特定日志框架的适配器时，框架通常会提供适配器。

## 快速查看 Apache Commons Logging 和 SLF4J

Apache Commons Logging (http://commons.apache.org/commons-logging/) 和 Simple Logging Facade for Java (http://www.slf4j.org/) 都是常用的框架。



多年来，Log4j 是无论是独立使用还是在不使用 Commons Logging 或 SL4J 的情况下最流行的日志框架。（它最常与 Commons Logging 一起使用）。然而，Log4j 有一些缺点，特别是接口狭窄（没有标记 markers、没有消息格式化，以及性能问题）。对各种 API 和框架的不满导致了 SL4J（对 Commons Logging 的改进）的创建，随后是 Logback（对 Log4j 的改进）。Logback 拥有极其实用的接口、强大的实现以及一系列证明其稳定性和性能的测试。人们开发 Log4j 2 并没有花费很长时间，它是原始 Log4j 框架的继任者，目标是改进原始 Log4j 的接口和性能。

# 介绍 Log4j 2

Log4j 2 (http://logging.apache.org/log4j/2.x/) 于 2014 年 2 月发布，相比 Log4j 有了巨大的改进；包含了重大的性能提升、极大地扩展的接口以及大量的测试来支持这一切。此外，API 和实现已经完全分离。该 API 为开发者提供了一个用于记录日志的接口，并提供了创建底层实现所需的钩子（hooks）。

当然，还有一个默认实现，应用程序开发者和其他日志框架的开发者可以使用该 API 进行适配，使其运行在其他日志实现之上。由于市上有非常多的日志框架，且 Log4j 2 仍然非常新，在编写库时，你仍然应该使用 Commons Logging 或 SLF4j 作为你的日志 API。这是因为你无法知道你库的消费者将使用哪种日志框架，而且这些日志框架适配 Commons Logging 或 SLF4j 的概率比适配 Log4j 2 大。然而，在编写应用程序时，主权掌握在你手中。直接针对 Log4j 2 API 编写提供了更大的灵活性，取决于你的使用方式，还可能对性能有所帮助，而且以后需要时，你不会失去切换底层实现的能力。

> 注意：Log4j 2 在其网站上包含了几项性能指标。最重要的指标——关闭日志记录时的性能——令人印象深刻：在关闭日志的情况下，调用 `isEnabled` 的耗时平均为 3 纳秒，调用 `debug` 的耗时平均为 4 纳秒。牺牲 40 亿分之一的时间就在你的应用程序中加入了有用的消息日志。从这个角度来看，如果禁用所有调试日志，你的应用程序每秒必须执行 250,000 或 250,000,000 个调试方法才能使执行时间翻倍。所有性能大致与 Logback 性能相当。而 Log4j 在处理日志文件方面真正表现出色。在多线程应用程序中，测试显示 Log4j 2 比其他日志框架快一个数量级，或者在过滤器处理激活时。

在本书的剩余部分中，你将使用 Log4j 2 API 记录日志，底层使用 Log4j 2 核心实现。（在现实场景中，你应该评估项目的需求，并决定哪种 API 和实现适合你）。你无疑注意到本章有五个 Log4j 2 Maven 依赖。以下是它们的说明：

- `log4j-api` 提供日志记录的 API。这是 Log4j 依赖中唯一需要编译的，因此你的应用程序只包含你编写代码时所针对的类。
- `log4j-core` 包含了标准的 Log4j 2 实现。当你在本章的剩余部分探索 Log4j 2 配置时，配置的是实现，而不是 API。API 不需要任何配置。
- `log4j-jcl` 是一个支持 Commons Logging API 的适配器。你在书剩余部分使用的这些库针对 Commons Logging API 记录日志，该适配器让 Commons Logging 使用 Log4j 2 作为其实现。
- `log4j-slf4j-impl` 是一个 SLF4j 实现适配器。在书剩余部分使用的几个库针对 SLF4J API 记录日志，该适配器让 SLF4J 使用 Log4j 2 作为其实现。
- `log4j-taglib` 是一个适配器，包含一个 JSP Tag Library，用于在你的 JSPs 中记录日志。与前三个依赖一样，该依赖处于运行时范围（runtime scope），对于编写应用程序代码来说，你不需要针对它进行编译。但是，如果你配置了构建来编译你的 JSPs，你就需要它。



# 第 11 章 使用日志监控你的应用程序

## Log4j 2 性能

Log4j 2 在其网站上包含了几项性能指标。最重要的指标——关闭日志记录时的性能——令人印象深刻：在关闭日志的情况下，调用 `isEnabled` 的耗时平均为 3 纳秒，调用 `debug` 的耗时平均为 4 纳秒。牺牲 40 亿分之一的时间就在你的应用程序中加入了有用的消息日志。从这个角度来看，如果禁用所有调试日志，你的应用程序每秒必须执行 250,000 或 250,000,000 个调试方法才能使执行时间翻倍。所有性能大致与 Logback 性能相当。而 Log4j 在处理日志文件方面真正表现出色。在多线程应用程序中，测试显示 `Log4j 2` 比其他日志框架快一个数量级，或者在过滤器处理激活时。

## API 与实现分离

完全分离。该 API 为开发者提供了一个用于记录日志的接口，并提供了创建底层实现所需的钩子。

当然，还有一个默认实现，应用程序开发者和其他日志框架的开发者可以使用该 API 进行适配，使其运行在其他日志实现之上。由于市上有非常多的日志框架，且 `Log4j 2` 仍然非常新，在编写库时，你仍然应该使用 `Commons Logging` 或 `SLF4j` 作为你的日志 API。这是因为你无法知道你库的消费者将使用哪种日志框架，而且这些日志框架适配 `Commons Logging` 或 `SLF4j` 的概率比适配 `Log4j 2` 大。然而，在编写应用程序时，主权掌握在你手中。直接针对 `Log4j 2 API` 编写提供了更大的灵活性，取决于你的使用方式，还可能对性能有所帮助，而且以后需要时，你不会失去切换底层实现的能力。

> **注意**：`Log4j 2` 在其网站上包含了几项性能指标。最重要的指标——关闭日志记录时的性能——令人印象深刻：在关闭日志的情况下，调用 `isEnabled` 的耗时平均为 3 纳秒，调用 `debug` 的耗时平均为 4 纳秒。牺牲 40 亿分之一的时间就在你的应用程序中加入了有用的消息日志。从这个角度来看，如果禁用所有调试日志，你的应用程序每秒必须执行 250,000 或 250,000,000 个调试方法才能使执行时间翻倍。所有性能大致与 `Logback` 性能相当。而 `Log4j` 在处理日志文件方面真正表现出色。在多线程应用程序中，测试显示 `Log4j 2` 比其他日志框架快一个数量级，或者在过滤器处理激活时。

在本书的剩余部分中，你将使用 `Log4j 2 API` 记录日志，底层使用 `Log4j 2` 核心实现。（在现实场景中，你应该评估项目的需求，并决定哪种 API 和实现适合你）。你无疑注意到本章有五个 `Log4j 2 Maven` 依赖。以下是它们的说明：

- `log4j-api` 提供日志记录的 API。这是 `Log4j` 依赖中唯一需要编译的，因此你的应用程序只包含你编写代码时所针对的类。
- `log4j-core` 包含了标准的 `Log4j 2` 实现。当你在本章的剩余部分探索 `Log4j 2` 配置时，配置的是实现，而不是 API。API 不需要任何配置。
- `log4j-jcl` 是一个支持 `Commons Logging API` 的适配器。你在书剩余部分使用的这些库针对 `Commons Logging API` 记录日志，该适配器让 `Commons Logging` 使用 `Log4j 2` 作为其实现。
- `log4j-slf4j-impl` 是一个 `SLF4j` 实现适配器。在书剩余部分使用的几个库针对 `SLF4J API` 记录日志，该适配器让 `SLF4J` 使用 `Log4j 2` 作为其实现。
- `log4j-taglib` 是一个适配器，包含一个 `JSP Tag Library`，用于在你的 `JSPs` 中记录日志。与前三个依赖一样，该依赖处于运行时范围（runtime scope），对于编写应用程序代码来说，你不需要针对它进行编译。但是，如果你配置了构建来编译你的 `JSPs`，你就需要它。

## 核心组件

### 日志器继承层次结构

**表 11-2：Log4j 日志器的继承层次结构**

| 日志器 (LOGGER) | 分配级别 | 有效级别 | 继承自 |
|---|---|---|---|
| root (特殊) | WARN | WARN | 无 |
| com | - | WARN | root |
| com.wrox | INFO | INFO | - |
| com.wrox.chat | DEBUG | DEBUG | - |
| com.wrox.shop | - | INFO | com.wrox |
| com.example.test | - | WARN | root |

### 输出处理器 (Appenders)

`Appenders` 负责将日志内容写入目标。当分配给日志器时，`Appenders` 实际上具有与级别相同的继承规则，但 `additivity` 属性决定了它们是否会覆盖继承的 `Appenders`。例如，`root` 日志器被分配到控制台，而 `com.wrox` 分配到文件。`com.wrox` 和 `com.wrox.chat` 的消息会进入控制台和文件，而 `com.example.test` 仅进入控制台。然而，如果你为 `com.wrox` 设置 `additivity` 为 `false`，则 `com.wrox` 和 `com.wrox.chat` 的消息仅进入控制台。（它们在 `Appender` 处停止。）如果 `com.wrox.shop` 的 `additivity` 属性仍为 `false` 且 `Appender` 设置为 `true`（默认值），则消息会进入文件，但不进入控制台。

### 布局 (Layouts)

`Appenders` 经常使用 `Layout` 来决定输出的格式。最常见的 `Layout` 类型是基于模式的 `Layout`，它在写入时定义了一系列待替换的令牌。还有 `HTML`、`XML` 和序列化布局，你将在下一节中探索 `PatternLayout`。

### 过滤器 (Filters)

`Log4j` 过滤器提供了一种机制，可以检查日志消息以决定是否写入以及如何写入。过滤器评估的结果为 `ACCEPT`、`DENY` 或 `NEUTRAL`，这就像 `Servlet` 过滤器一样。`ACCEPT` 表示消息应该被写入，所有其他过滤器都被忽略。如果过滤器评估结果为 `ACCEPT`，即使消息级别不够，消息也会被记录。`DENY` 则相反：这意味着消息被立即拒绝，后续过滤器没有机会评估该消息。`NEUTRAL` 表示过滤器既不拒绝消息，其他过滤器可能会进行进一步评估。

在 `Log4j 2` 配置中，过滤器可以附加到架构的四个阶段：上下文配置、`Logger` 配置、`Appender` 引用或 `Appender` 配置。当消息被记录时，第一个停止点是按声明顺序的全范围过滤器。假设之前的级别是 `NEUTRAL`，则消息将进入级别评估。如果通过测试，下一个停止点是 `Logger` 配置过滤器。过滤器决定 `Logger` 是否应该将消息路由到特定的 `Appender`（例如，可以将消息过滤到不同的文件或数据库表中）。最后，单个 `Appender` 上的过滤器决定 `Appender` 是否应该写入消息。

过滤器可以处理各种信息。一种常见的模式是在日志消息中使用 `Marker` 对象，过滤器对于过滤非常有用。过滤器还可以查看消息的内容、消息类型、附加到消息的异常以及存储在当前线程中的数据等。例如，过滤器可以使用与当前消息相关的系统时间来决定如何处理消息。你将在下一节中看到配置过滤器的示例。

## 将日志集成到你的应用程序

使用和配置 `Log4j` 是一个相当简单的任务。如上一节所述，你可以在应用程序中尽可能少地放置日志语句：

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

`Log4j 2` 可以使用默认配置自配置并开始将日志消息写入控制台。当然，这个默认配置可能对你来说不够。你可能需要不仅仅是错误（你可能还需要警告和信息），并且可能希望日志进入控制台以外的地方。你可以通过配置文件来实现这两点。

> **注意**：如果你正在配置旧版本的 `Log4j`，请记住两点：第一，`Log4j 2` 不支持通过 `Java` 属性文件进行配置。你必须使用 `XML` 或 `JSON`。第二，`Log4j 2` 的 `XML` 架构与 `Log4j` 的不同。如果你在任何应用程序中有现有的 `log4j.xml` 文件，不能简单地将这些文件重命名为 `log4j2.xml`。你必须采用新的配置架构。

## 创建 Log4j 配置文件

记住 `Log4j` 会查找两个不同的配置文件（`log4j2` 和 `log4j2-test`），并支持三种不同的文件扩展名（`.xml`、`.json`、`.jsn`）。`.json` 和 `.jsn` 扩展用于 `JSON` 格式配置。`JSON` 配置比 `XML` 配置更易读和编写。

> **注意**：如果在运行应用程序时，在 `Tomcat` 中找不到 `application.log` 文件，请尝试将相对路径更改为系统中某个目录的绝对路径并重启应用程序。

`PatternLayout` 提供了许多可以记录事件信息的模式，你可以在 `Log4j` 文档中了解它们（以及其他）运行情况。在这种情况下，文件 `Appender` 模式用 `%logger` 替换了 `%logger`（前者比后者短）以及 `%1`，后者会打印发生日志事件的类、方法、文件和行号。它还添加了 `%x{id}`（一个鱼标签/fish tag）和 `%{username}`，这些是 `ThreadContext` 上的属性——你可以了解这些内容。你还会发现，文件 `Appender` 的模式除了是不同的模式外，它是使用 `XML` 格式配置的，而控制台 `Appender` 则不是。你可以通过标签属性或嵌套标签指定 `Appenders`（输出器）、`Filters`（过滤器）、`Loggers`（日志器）等的属性。这两种方法是互换的。

最后，此文件中的新 `Logger` 配置说明，`com.wxyz` 和 `org.apache` 层次结构下的所有 `Logger` 都继承自 `INFO`，且 `com.wxyz` 中的 `Logger` 不是可加的（additive）——它们不继承 `Console Appender` 仅记录到文件 `Appender`。然而，注意用于控制台 `Appender` 的 `com.wxyz <appender-ref>` 有一个嵌套的 `<MarkerFilter>` 元素。该过滤器表示 `com.wxyz` 层次结构中的 `Logger` 可以记录到 `Console Appender`，但仅限于创建名为 `WROX_CONSOLE` `Marker` 的事件。你可以在 `Log4j Filter` 文档中了解各种可用过滤器。以下不完整的配置显示了 `Filter` 配置元素的所有有效位置（以粗体显示）：



```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <FilterName ... /><!-- 这是一个全局范围过滤器 -->
  <appenders>
    <AppenderName name="someAppender">
      <FilterName ... /><!-- 这是一个 appender 过滤器 -->
    </AppenderName>
  </appenders>
  <loggers>
    <logger name="someLogger" level="info">
      <FilterName ... /><!-- 这是一个 logger 过滤器 -->
      ...
      <appender-ref ref="someAppender">
        <FilterName ... /><!-- 这是一个 appender 引用过滤器 -->
        ...
      </appender-ref>
      ...
    </logger>
  </loggers>
</configuration>
```

本书无法展示所有配置 Log4j 的可能方法，因为方法有很多。如果你想获取更多信息，Log4j 手册是一个很好的起点。

# 在 Web 过滤器中使用鱼标签标记（Fish Tagging）

在使用任何日志框架时，你都应该对请求进行“鱼标记”（fish tag），以便能够将针对同一个请求的日志消息分组并进行分析。`org.apache.logging.log4j.ThreadContext` 将属性存储在当前线程中，直到 `ThreadContext` 被清空。在向 `ThreadContext` 添加和移除属性时，在同一线程中记录的任何事件都可以与该属性关联。如果每个请求都有许多请求，你希望识别在该特定请求期间记录的所有消息。

鱼标签通常是某种强唯一的标识，例如 UUID。`ThreadContext` 还可以存储其他内容来区分日志事件，例如登录用户的用户名。`LoggingFilter` 在请求开始时将鱼标签 (id) 和会话用户名 (username) 添加到 `ThreadContext` 中，并在请求完成时清空 `ThreadContext`。之前讨论的模式使用 `%X(id)` 和 `%X{username}` 打印这些属性。由于过滤器支持多种调度器类型并可能在单个请求中执行多次，它仅在鱼标签和用户名属性尚未设置时才设置它们，并在调用时清空 `ThreadContext`。

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
        if (!request.containsKey("id")) {
            clear = true;
            ThreadContext.put("id", UUID.randomUUID().toString());
            HttpSession session = ((HttpServletRequest) request).getSession(false);
            if(session != null) {
                ThreadContext.put("username", (String) session.getAttribute("username"));
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

# 在 Java 中编写日志语句

> 警告：回想你在第9章中学的关于 `ThreadContext` 的课程。如果你在请求开始时在 `ThreadContext` 上设置值，这些值将在请求完成之前被清空。使用 Log4j 非常简单。每个 Level（级别）都存在重载方法，这些如 `info`、`warn` 和 `error` 方法允许在 String 消息中指定一个或多个参数，并提供标记标记标记。

> 注意：`Logger` 的无参方法返回一个 `Logger`，其名称等于调用 `Logger` 的类的全限定名。在列表 11-1 中，即 `com.work.WebServlet`。你也可以使用接受 `Class` 参数的 `getLogger`，它将返回一个以类名命名的 `Logger`。如果你想使用类名以外的其他内容作为 `Logger` 名称，可以使用接受 `String` 参数（`Logger` 的名称）的 `getLogger` 方法。

# 列表 11-1：ActionServlet.java

```java
@WebServlet(name = "ActionServlet", urlPatterns = "/files")
public class ActionServlet extends HttpServlet {
    private static final Logger log = LogManager.getLogger();

    @Override
    protected void doGet(ServletRequest request, ServletResponse response)
            throws ServletException, IOException {
        String action = request.getParameter("action");
        if (action != null) {
            log.info("Received request with action {}.", action);
            String contents = null;
            switch(action) {
                case "license":
                    log.info("Reading license file...");
                    contents = Files.readString(Paths.get("/opt/tomcat/conf/LICENSE"));
                    break;
                case "badAction":
                    log.warn("Invalid action requested: {}", action);
                    break;
                case "foo":
                    try {
                        throw new RuntimeException("Something went wrong");
                    } catch (RuntimeException e) {
                        log.error("Error occurred while processing foo", e, MarkerManager.getMarker("WROX_CONSOLE"));
                    }
                    break;
            }
            response.getWriter().write(contents != null ? contents : "No content");
        }
    }
}
```

*(注：上面的代码根据碎片化的 OCR 片段和上下文重建)*

现在编译并启动应用程序，然后访问浏览器。`application.log` 文件应该出现在 Tomcat 日志目录中并包含条目。在 URL 中添加 `action=badAction` 并重新加载日志文件，会在文件中显示新的信息消息和警告。将 action 更改为 `readLicense` 将 Tomcat 许可文件读取到浏览器。日志文件中只显示信息消息。最后，将 action 更改为 `readFoo`，带有异常堆栈跟踪的错误将出现在日志文件中。此错误也会出现在控制台（调试器）输出中，因为它包含了名为 `WROX_CONSOLE` 的 Marker。注意每个记录消息的鱼标签，以及它在同一个请求中记录的多条消息中是相同的。你应该尝试 Log4j 配置文件并更改 `level`（级别）和 `additivity`（可加性）属性，观察日志数据的变化。

> 访问 Tomcat 许可文件使用的相对文件名仅当你的 IDE 从另一个目录启动 Tomcat 时才有效，你可能需要更改此文件的路径才能正常工作。

# 在 JSP 中使用 Log 标签库

如前所述，Log4j 2 附带了一个标签库，允许你在不使用脚本的情况下在 JSP 中记录日志消息。本书将不会对这个主题进行详细介绍，因为通常情况下来说，表示层对日志记录的需求要少得多。事实上，只要你的 JSP 中没有包含任何业务逻辑，你就永远不需要对它们进行日志记录。尽管如此，你可以通过以下指令包含该标签库：

```
<%@ taglib prefix="log" uri="http://logging.apache.org/log4j/tld/log" %>
```

Logging-Integration 项目在 Web 根目录下有一个 `logging.jsp` 文件，它演示了如何使用这些标签：

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<!DOCTYPE html>
<html>
<head>
  <title>Test Logging</title>
</head>
<body>
  <log:info message="JSP body displaying." />
  Messages have been logged.
  <log:info>JSP body complete.</log:info>
</body>
</html>
```

你应用程序中每个使用一个或多个 log 标签的 JSP 都会自动为你创建它。你可以使用 `<log:getLogger>` 标签或大多数其他标签上的 `logger` 属性来覆盖此日志记录。通过启动应用程序并在浏览器中访问 http://localhost:8080/8080-integration/logging.jsp 来尝试 JSP 日志。根据你所设置的日志级别，你将在日志中看到不同的消息。

# 在客户支持应用程序中记录日志

wrox.com 代码下载中的 Customer-Support+9 项目已从代码中删除了所有对 `System.out`、`System.err` 和 `Throwable.printStackTrace()` 的使用，并用其替换为 Log4j 2 日志。此外，在整个应用程序中增加了更多的日志消息。最后，将 `LoggingFilter` 从上一个示例复制并添加到 `Config` 中过滤器链的开头，以便所有请求都打上过滤器标记。

你应该下载并检查这些更改，但此处没有详细列出，因为这与你所学的内容是重复的。`com.wrox` 层次结构下所有 `Logger` 的默认日志级别设置为 `INFO`，到目前为止唯一的 `INFO` 事件是用户登录时。大多数日志事件都是 `DEBUG`、`TRACE`、`WARN` 或 `ERROR`。正因如此，当你运行客户支持应用程序时，在 `support.log` 文件中看不到很多内容。请放心，这将在第二部分开始学习 Spring Framework 时发生变化。

### 总结

在本章中，你学习了应用程序日志记录的基础知识，以及为什么在应用程序中记录日志如此重要。你研究了几种常见的日志模式，并探索了类别（categories）和日志级别的概念。你还学习了将日志 API 与其底层实现分离的重要性，这可以避免你以后遇到烦恼。你介绍了几个流行的日志 API 和实现，例如 Apache Commons Logging、SLF4J、Logback、Log4j 1.x 以及 Log4j 2。最后，你学习了使用和配置 Log4j 2 的细节，并尝试将其集成到 Web 应用程序中。在书的剩余部分，日志在每一个章节中都非常常见。你处理的每个项目都包含 Log4j 2 配置和日志语句。这样，你就可以养成在编写程序时始终记录日志的习惯。

到这里第一部分结束了，在第一部分中，你学习了使用 Java SE、Java EE、Servlets、JSPs、过滤器（filters）、WebSockets、应用服务器、Web 容器等进行 Web 应用程序开发的各个方面。现在，你应该已经掌握了基础知识，并能够编写相当复杂的应用程序。在第二部分中，你将开始提升企业级开发技能，学习 Spring Framework 以及它是如何补充、增强并且在某些情况下替代 Java 平台企业版（Java Platform, Enterprise Edition）部分的。

# 第二部分：将 Spring Framework 引入其中

- 第 12 章：引入 Spring Framework
- 第 13 章：用 Controllers 替换你的 Servlets
- 第 14 章：使用 Controllers 和 Repository
- 第 15 章：使用 Spring Framework 实现应用程序国际化
- 第 16 章：使用 JSR 349
- 第 17 章：创建 RESTful 和 SOAP 服务
- 第 18 章：使用 Messaging 和集群

# 控制反转与依赖注入

Spring Framework 的核心特性之一是支持紧密相关的概念：控制反转（IoC）和依赖注入（DI）。IoC 是一种软件设计模式，通过该模式，组装器在运行时而非编译时进行耦合绑定。当程序逻辑的某个组件（例如 Service A）依赖于另一个程序逻辑组件（Service B）时，该依赖关系是在应用程序运行时满足的，而不是由 Service A 直接实例化 Service B（后者将在编译时完成）。这使得应用程序能够针对一组接口进行编程，并且可以在不重新编译代码的情况下在不同环境中切换这些接口。在运行单元测试时，可以提供“模拟（Mock）”或“测试”服务；而同一段代码可以部署到带有更多“真实”服务的生产环境中进行运行。

这在理论上可以通过几乎许多方式实现；DI 是最常用的技术。使用 DI，一段程序代码（在 Spring Framework 中为一个类）声明它依赖于另一段程序代码（一个接口），在运行时，组装器会选择该依赖的某个实例（通常但并非总是单例）。

# 面向切面编程

由于 Spring Framework 处理了依赖的实例化和注入，它可以包装其注入的依赖实例，用其他行为来装饰方法调用。例如，使用 Spring Security，你可以对方法进行注解以识别设置在这些方法上的安全限制，而 Spring Framework 会包装这些方法调用，包含满足此类限制所需的安全检查。你还可以使用切面（Aspects）定义任何横切关注点，Spring Framework 会用这些关注点装饰所有相关的方法。横切关注点是指影响程序多个组件的关注点（例如安全关注点），通常不考虑它们影响哪些组件。面向切面的编程是面向对象编程的补充，它通过定义切面来应用这些关注点，切面指定了如何以及何时应用这些关注点。Spring Framework 为面向切面的编程提供了丰富的工具，你将在本书后续章节中学习它们。

# 数据访问与事务管理

Spring Framework 提供了一套数据访问工具，简化了 Java 对象在关系型数据库中的提取和持久化。这些特性使得数据访问测试变得更容易；但仍然需要特定版本的 SQL。Spring Framework 对 Java 持久 API（JPA）以及如 Hibernate ORM 等对象关系映射器提供了广泛支持，你将在本书的第三部分探索这些内容。通过 Spring Data 项目，在关系型数据库和如 MongoDB、Redis 等 NoSQL 数据库中投影对象变成了一项简单任务。最后，Spring Framework 支持声明式事务模型，其中被注解方法的执行被包装在事务中，如果方法抛出异常，则会回滚。这是通过 Spring Framework 的 AOP 支持实现的。

# 消息传递

在任何应用程序中，消息传递都是需要解决的重要关注点。例如，程序的某些部分可能需要知道程序的其他部分何时执行了指定的操作。执行该操作的程序部分可以简单地依赖对操作感兴趣的部分并调用所有部分的方法来通知它们，但那种类型的紧耦合难以维护，且可能变得非常混乱。



Spring Framework 提供了一个松耦合的消息传递系统，它使用了发布-订阅模式：系统中的组件通过订阅某些消息来宣布它们对某些消息感兴趣，而这些消息的生产者在发布消息时并不关心谁订阅了它们。这本质上就是 Twitter 的工作原理：人们把有趣的（或可能不有趣的）话通过推文出来，其他人则关注他们。使用 Spring Framework，一个由 Spring 管理的 bean 可以通过实现通用接口来订阅特定消息类型，而其他 Spring 管理的对象将这些消息发布给 Spring Framework，Spring Framework 还会跨应用程序集群投递消息。

# Web 应用程序的模型-视图-控制器模式

Spring Framework 具有模型-视图-控制器（MVC）模式框架，简化了创建 Web 应用程序的过程。无需手动处理 `Servlets`、`HttpServletRequest`、`HttpServletResponse` 的复杂性以及向 JSP 的跳转，Spring 会替你处理这些任务。控制器类中的每个方法都映射到不同的请求 URL，或请求的其他属性：`String`、`Object`。从控制器返回的 `View` 或视图名称（`String`）会促使 Spring 转换为适当的 JSP 视图。URL 参数会自动转换为基本数据类型或复杂的控制器方法参数。

除了典型的 HTML 视图外，Spring 还可以使用 XML 或 JSON 实体视图自动生成纯文本视图和文件下载视图。通过所有这些特性，Spring Framework 大大简化了在 Servlet 容器中的工作。

# 为什么选择 Spring Framework？

在之前的章节中，你已经学习了 Spring Framework 提供的许多特性，因此你可能已经知道在应用程序中使用 Spring Framework 的一些引人注目的理由。它的功能集以及对 Servlet API 的简化并不是 Spring Framework 的唯一优势。它所采用的模式（你将在本书的这部分中学习更多）提供了若干益处，当你努力创建强大的 Web 应用程序时，你无疑会非常欣赏这些。

# 逻辑代码分组

考虑你在本书之前的章节中创建的一些较复杂的 Servlet。每个 Servlet 都有一个 `doGet` 或 `doPost`（或者两者都有），包含许多语句或 `switch` 块，负责将请求路由到 Servlet 内的任意方法。在极其复杂的企业应用程序中，你会很快发现这种模式变得难以管理且极其难以测试。例如，一个处理用户配置的 Servlet 可能有几十个方法，每个方法在 `doGet` 或 `doPost` 方法中建立了不同的路由逻辑。

一种可能的解决方案是创建几十个 Servlet。这将导致代码库更具可测试性和可维护性；但由于逻辑分支随处可见，Servlet 的数量可能会迅速变得不可控。如果你的应用程序包含数百个功能、几十个页面，你会发现代码库会膨胀到数千个 Servlet；如果你的 Servlet 可以映射到单个方法而不是类，许多问题将迎刃而解。

使用 Spring 的 MVC 框架，控制器类的作用非常像具有方法级映射的 Servlet，对应参数编码器、标头值、内容类型和/或响应类型。回到用户配置示例，控制器可以有很多个映射方法，代表对用户配置可以执行的不同操作。`doGet` 或 `doPost` 方法负责将请求路由到正确的方法。Spring Framework 替你处理这一切分析和路由。

# 使用一个代码库多个用户界面

在现实场景中，你可能被要求创建一个具有数千个功能的先进应用程序，这些功能应该适用于桌面应用程序、网页浏览器、移动浏览器、RESTful Web 服务以及 SOAP Web 服务。如果仅使用 Servlet，这项任务将迅速变得令人生畏。你会重复大量代码，或者创建一个自己的系统，其中业务逻辑被抽象为许多用户界面使用的类。

幸运的是，Spring Framework 提供了这样一个系统，经过测试，只需少量工作即可使用。使用 Spring，业务逻辑封装在称为服务的业务对象中。这些服务执行所有用户界面通用的操作，例如确保实体属性正确指定。你的应用程序为每个用户界面包含一组不同的控制器，这些控制器使用特定的操作，例如将表单提交或 JSON 请求体转换为实体并将适当的值传递给用户。单元测试变得更容易，代码被复用，并且实现这些都需要少量工作。

## 理解应用上下文

Spring Framework 容器以一个或多个应用上下文的形式存在，由 `org.springframework.context.ApplicationContext` 接口表示。应用上下文管理一组 bean，这些 Java 对象执行业务逻辑、执行任务、持久化和检索数据、响应 HTTP 请求等。Spring 管理的 bean 自动适用于依赖注入、消息通知、调度方法执行、bean 验证以及其他关键的 Spring 服务。

一个 Spring 应用始终至少有一个应用上下文，有时它会有一些需求。然而，它还具有由多个应用上下文组成的层级结构。在这种层级结构中，任何 Spring 管理的 bean 都可以访问同一个应用上下文中的 bean、父应用上下文中的 bean、父的父应用上下文中的 bean，依此类推。它们无法访问兄弟或子级应用上下文中的 bean。这对于在与其他组件之间相互隔离时，定义一组共享的应用上下文非常有用。例如，你可能希望 Web 应用程序的 Web 部分和管理部分互不访问，但无疑你会有一些这两个部分都需要的共享资源。

> 注意：在本书的剩余部分中，你将一直使用 Spring Framework，你应该随时备好 API 文档。务必将文档书签，以便在你想了解更多关于 Spring 接口、类、注解或异常时能够随时查阅。

有许多接口扩展并实现了 `ApplicationContext`：

- `ConfigurableApplicationContext` 接口，顾名思义，而基类 `ApplicationContext` 只是只读的。
- `org.springframework.web.context.WebApplicationContext` 和 `ConfigurableWebApplicationContext` 旨在运行在 Servlet 容器中的 Java EE Web 应用，并提供对底层 `ServletContext` 以及（在适用情况下）`ServletConfig` 的访问。
- 具体类 `ClassPathXmlApplicationContext` 设计用于在独立应用中从 XML 文件加载 Spring 配置，而 `XmlWebApplicationContext` 则在 Java EE Web 应用中实现相同的功能。
- 采用 Java 而非 XML 来配置 Spring 时，`AnnotationConfigApplicationContext` 和 `AnnotationConfigWebApplicationContext` 分别在独立应用和 Java EE Web 应用中工作。

在 Java EE Web 应用中，Spring 使用 `DispatcherServlet` 处理请求，将请求委托给适当的控制器，并根据需要翻译请求和响应实体。你的 Web 应用可以根据用例需要创建任意数量的 `org.springframework.web.servlet.DispatcherServlet` 类的实例。

每个 `DispatcherServlet` 都有自己的应用上下文，该上下文引用了 Web 应用的 `ServletContext` 和它自己的 `ServletConfig`。你可能会创建多个 `DispatcherServlet`，例如，将你的 Web 用户界面与 Web 服务分开。由于这些 `DispatcherServlet` 都不访问任何其他 `DispatcherServlet` 的应用上下文，因此通常最好在一个公共根应用上下文中共享某些 bean（如业务对象或数据访问对象）。这个应用上下文对于整个 Web 应用是全局的，它是所有 `DispatcherServlet` 应用上下文的父级，并使用 `org.springframework.web.context.ContextLoaderListener` 创建。它也拥有对 Web 应用 `ServletContext` 的引用，但因为它不属于任何特定的 Servlet，所以它没有 `ServletConfig` 引用。

尽管拥有多个 `DispatcherServlet` 的想法在 Web 应用中很常见，并且在本书中都有涉及，但它只是无限可能性中的一种配置。在任何独立应用或 Web 应用中，你都可以根据需要创建任何应用上下文层级。作为一个一般原则，你应该始终有一个根应用上下文，所有其他应用上下文都以某种方式继承它，如图 12-1 所示。

![](img/4677f981a0e1067137bb55a122f8498d_364_0.png)

图 12-1

## 启动 Spring 框架

在计算机软件世界中，一切都必须在某个时刻进行启动。考虑你的桌面电脑、笔记本电脑或移动计算设备：当它开启时，某种类型的启动设备（通常是 BIOS 或类似设备）初始化所有硬件，从某个位置（如硬盘上的引导扇区）加载启动指令，并启动操作系统。从这个意义上说，硬件是操作系统的容器。操作系统是另一个容器——用于在其中运行的软件。

C 程序有一个标准化的启动机制：`main()` 方法。所有可运行的 C 程序必须包含此方法以进行启动。Java 虚拟机可执行文件（通常用 C 或 C++ 编写）包含这个 `main()` 方法（或其等效方法）。

```xml
<context-param>
    <param-name>contextClass</param-name>
    <param-value>org.springframework.web.context.support.AnnotationConfigWebApplicationContext</param-value>
</context-param>
<context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>com.wrox.config.RootContextConfiguration</param-value>
</context-param>
<listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>

<servlet>
    <servlet-name>springDispatcher</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <init-param>
        <param-name>contextClass</param-name>
        <param-value>org.springframework.web.context.support.AnnotationConfigWebApplicationContext</param-value>
    </init-param>
    <init-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>com.wrox.config.ServletContextConfiguration</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
    <servlet-name>springDispatcher</servlet-name>
    <url-pattern>/</url-pattern>
</servlet-mapping>
```

通常情况下，`ContextLoaderListener` 和 `DispatcherServlet` 会创建 `org.springframework.web.context.support.WebApplicationContext` 的实例，这要求 Spring 的配置以 XML 文件的形式存在。上一个示例覆盖了这一行为，并改用 `AnnotationConfigWebApplicationContext`。这种类型期望程序化的上下文配置，并在 `contextConfigLocation` 参数中以类名（而不是文件名）的形式进行指定。

### 在初始化器中程序化地启动 Spring

回想一下，在之前的章节中，我们使用 `ServletContextListener` 来程序化地配置应用程序中的 Servlets 和过滤器。这种方法的缺点是监听器的 `contextInitialized` 方法可能会在其他监听器之后被调用。Java EE 6 添加了一个新接口 `ServletContainerInitializer`。实现 `ServletContainerInitializer` 的类会在应用程序启动时、在所有监听器被通知之前调用其 `onStartup` 方法。这是应用程序生命周期中最早的可能点。你不需要配置 `ServletContainerInitializer`，而是使用 Java 的服务提供者机制来实现实现 `ServletContainerInitializer` 的一个或多个类，方法是在名为 `/META-INF/services/javax.servlet.ServletContainerInitializer` 的文件中列出这些类，每行一个。例如，以下文件内容列出了两个实现 `ServletContainerInitializer` 的类：

缺点是，该文件不能直接存在于应用程序的 WAR 文件或解压目录——你不能将该文件放在应用程序的 `/META-INF/services` 目录下。它必须位于应用程序 `/WEB-INF/lib` 目录下的某个 JAR 文件的 `/META-INF/services` 目录。

Spring Framework 提供了一个桥接接口，使得这种实现变得简单得多。`org.springframework.web.SpringServletContainerInitializer` 实现了 `ServletContainerInitializer` 接口，由于该类所属的 JAR 包含了类名列表的服务提供者，当你的应用程序启动时，它的 `onStartup` 方法会被调用。它会扫描类路径以寻找 `org.springframework.web.WebApplicationInitializer` 的实现，并调用它找到的任何匹配类的 `onStartup` 方法。在 `WebApplicationInitializer` 类中，你可以程序化地配置监听器、Servlets、过滤器等，而无需编写任何单行 XML。更重要的是，你可以从该类内部启动 Spring。

```java
class Bootstrap implements WebApplicationInitializer {
    @Override
    public void onStartup(ServletContext container) {
        XmlWebApplicationContext rootContext = new XmlWebApplicationContext();
        rootContext.setConfigLocation("/WEB-INF/rootContext.xml");
        container.addListener(new ContextLoaderListener(rootContext));

        XmlWebApplicationContext servletContext = new XmlWebApplicationContext();
        servletContext.setConfigLocation("/WEB-INF/servletContext.xml");
        ServletRegistration.Dynamic dispatcher = container.addServlet(
            "Dispatcher", new DispatcherServlet(servletContext));
        dispatcher.setLoadOnStartup(1);
        dispatcher.addMapping("/");
    }
}
```

这种启动方式在功能上等同于之前使用 Spring XML 配置的部署描述符启动。下面的启动方式则使用 Spring Java 配置来实现纯 Java 的启动和配置过程。

```java
class Bootstrap implements WebApplicationInitializer {
    @Override
    public void onStartup(ServletContext container) {
        AnnotationConfigWebApplicationContext rootContext =
            new AnnotationConfigWebApplicationContext();
        rootContext.register(com.wrox.config.RootContextConfiguration.class);
        container.addListener(new ContextLoaderListener(rootContext));

        AnnotationConfigWebApplicationContext servletContext =
            new AnnotationConfigWebApplicationContext();
        servletContext.register(com.wrox.config.ServletContextConfiguration.class);
        ServletRegistration.Dynamic dispatcher = container.addServlet(
            "SpringDispatcher", new DispatcherServlet(servletContext)
        );
        dispatcher.setLoadOnStartup(1);
        dispatcher.addMapping("/");
    }
}
```



当然，你不需要像你所做的那样配置所有的应用程序上下文。你可以混合并匹配用于启动 Spring 的配置方法。下面的示例演示了这一点，并演示了如何在独立应用程序（例如桌面应用程序）中启动 Spring。

```java
public class Bootstrap {
    public static void main(String... arguments) {
        ClassXmlApplicationContext rootContext =
            new ClassXmlApplicationContext("wrox/config/rootContext.xml");
        FileSystemXmlContext daemonContext =
            new FileSystemXmlContext("wrox/config/servletContext.xml");
        AnnotationConfigWebApplicationContext forkedProcessContext =
            new AnnotationConfigWebApplicationContext(com.springframework.config.ServletContextConfiguration.class);
        forkedProcessContext.setParent(rootContext);

        rootContext.start();
        daemonContext.start();
        forkedProcessContext.start();
    }
}
```

## Dispatcher Servlet 映射

到目前为止以及在本书中将看到的示例都显示将 `DispatcherServlet` 映射到 `/`。多年来，关于将 `DispatcherServlet` 映射到根目录存在很多困惑，在论坛、博客和其他技术网站很容易找到关于它的错误或不完整的信息。

你可以将 `DispatcherServlet` 映射到任何 URL。一些常见方法将其映射到 `/do/`、`*.do` 或 `*.action`，某些网站将其作为 `*.html` 以看起来更静态。然而，有一些重要的注意事项。不要将 `DispatcherServlet` 映射到 `/`。在大多数情况下，URL 模式必须以星号 `*` 开头或结尾，映射到应用程序根目录时，不带星号的斜杠足以让 Servlet 容器的 JSP 机制处理 JSP 请求。末尾的星号会导致 Servlet 将内部 JSP 请求发送给它，这是不符合要求的（因为容器在映射你的 Servlet 之后才映射其处理器，使其优先级较低）。

如果你计划将 `DispatcherServlet` 映射到应用程序根目录，请确保考虑到静态资源，例如 HTML 页面、CSS 和 JavaScript 文件以及图像。一些在线教程演示如何设置 Spring 来提供静态资源，但这样做并非且性能良好。当任何 Servlet 映射到应用程序根目录（不带星号）时，更具体的 URL 模式将覆盖它。允许你的 Servlet 容器提供静态资源，只需将这些资源映射到名为 `default` 的 Servlet（所有容器都会自动提供）。这可以通过部署描述符完成：

```xml
<servlet-mapping>
  <servlet-name>default</servlet-name>
  <url-pattern>/resources/*.css</url-pattern>
  <url-pattern>/*</url-pattern>
  <url-pattern>*.js</url-pattern>
  <url-pattern>*.png</url-pattern>
  <url-pattern>*.gif</url-pattern>
  <url-pattern>*.jpg</url-pattern>
</servlet-mapping>
```

或者在 `ServletContainerInitializer` (`WebApplicationInitializer`) 或 `ServletContextListener` 中程序化实现，如下：

```java
servletContext.getServletRegistration("default").addMapping(
  "/resources/*", "*.css", "*.js", "*.png", "*.gif", "*.jpg"
);
```

# 第 12 章 介绍 Spring 框架

默认的 Servlet 不需要声明。Servlet 容器会替你隐式地声明。这里显示的 URL 模式只是示例——只有你才能决定将静态资源放在哪里，从而决定哪些 URL 模式是合适的。

# 配置 Spring 框架

现在你已经知道如何启动 Spring 框架，已经准备好学习如何配置它了。本章的剩余部分将继续使用 XML 和程序化启动作为示例，但本书的后续章节将仅使用程序化启动。你已经看到，可以使用 XML 或 Java 来配置 Spring 应用上下文。你不仅可以在单个应用程序中以不同的方式配置不同的应用上下文，还可以使用 Java 和 XML 混合来配置单个应用上下文。这在现代应用程序中是一个罕见的场景，但在某些情况下是必须的。例如，Spring 3.2 中添加的 Java 配置没有涵盖所有的配置场景，因此对于书中第四部分中的某些示例，你必须使用 Spring 的 XML 配置。此外，你在第 17 章中学习的 Spring Web Services 不支持 Java 配置上下文。在配置使用这些工具的应用程序上下文时，你可以使用 Java 配置上下文，但不能为 Spring Security 或 Spring Web Services 使用 XML 配置。在本章中，你将学习所有内容。

本节利用了 wr 代码下载中的 `Spring-One-Context-XML-Config`、`Spring-XML-Config`、`Spring-Hybrid-Config` 和 `Spring-Java-Config` 项目。你可以在整个节中参考这些项目，或者自己创建这些代码。作为开始，所有项目都具有你在第一部分中应该使用的相同的基础部署器代码。你将在书的其余部分继续使用此模板部署描述符：

```xml
<display-name>Spring Application</display-name>

<jsp-config>
  <jsp-property-group>
    <url-pattern>*.jsp</url-pattern>
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

你还需要配置 `log4j2.xml` 以确保所有适当的消息都记录到你的日志中。在以下写入控制台和日志文件的示例消息中，尽管大多数消息限制为警告（warning），但 `com.wrox`、`org.apache` 和 `org.springframework` 包中的类记录级别为 INFO 级别。

```xml
<root level="warn">
  <appender-ref ref="Console" />
  <appender-ref ref="WfileAppender" />
</root>
<logger name="com.wrox" level="info" />
<logger name="org.apache" level="info" />
<logger name="org.springframework" level="info" />
```

所有项目还包含了非常基础的 `GreetingService` 接口及其 `GreetingServiceImpl` 实现。

```java
public class GreetingServiceImpl implements GreetingService {
    @Override
    public String getGreeting(String name) {
        return "Hello, " + name + "!";
    }
}
```

所有四个项目中都有响应 Web 请求的 `HelloController`。你现在不需要担心这些类的语义、控制器中的注解或控制器-服务器模式。你很快就会学习这些内容，但现在你应该记住，通过四个相同的基础项目，你可以以不同的方式配置 Spring 框架并达到相同的目的。

```java
@Controller
public class HelloController {
    private GreetingService greetingService;

    @ResponseBody
    @GetMapping("/")
    public String helloWorld() {
        return "Hello, World!";
    }

    @ResponseBody
    @GetMapping("/custom")
    public String helloName(@RequestParam("name") String name) {
        return greetingService.getGreeting(name);
    }
}
```

## 创建 XML 配置

要告诉 Spring 如何配置 bean，请使用 wr 代码下载中的 `Spring-One-Context-XML-Config`、`Spring-XML-Config`、`Spring-Hybrid-Config` 和 `Spring-Java-Config` 项目。你可以在整个节中参考这些项目，或者自己创建这些代码。作为开始，所有项目都具有你在第一部分中应该使用的基础部署器代码。你将在书的其余部分继续使用此模板部署描述符：

```xml
<display-name>Spring Application</display-name>

<jsp-config>
  <jsp-property-group>
    <url-pattern>*.jsp</url-pattern>
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

你还需要配置 `log4j2.xml` 以确保所有适当的消息都记录到你的日志中。在以下写入控制台和日志文件的示例消息中，尽管大多数消息限制为警告，但 `com.wrox`、`org.apache` 和 `org.springframework` 包中的类记录级别为 INFO 级别。

```xml
<root level="warn">
  <appender-ref ref="Console" />
  <appender-ref ref="WfileAppender" />
</root>
<logger name="com.wrox" level="info" />
<logger name="org.apache" level="info" />
<logger name="org.springframework" level="info" />
```

所有项目还包含了非常基础的 `GreetingService` 接口及其 `GreetingServiceImpl` 实现。

```java
public class GreetingServiceImpl implements GreetingService {
    @Override
    public String getGreeting(String name) {
        return "Hello, " + name + "!";
    }
}
```

所有四个项目中都有响应 Web 请求的 `HelloController`。你现在不需要担心这些类的语义、控制器中的注解或控制器-服务器模式。你很快就会学习这些内容，但现在你应该记住，通过四个相同的基础项目，你可以以不同的方式配置 Spring 框架并达到相同的目的。

```java
@Controller
public class HelloController {
    private GreetingService greetingService;

    @ResponseBody
    @GetMapping("/")
    public String helloWorld() {
        return "Hello, World!";
    }

    @ResponseBody
    @GetMapping("/custom")
    public String helloName(@RequestParam("name") String name) {
        return greetingService.getGreeting(name);
    }
}
```

```xml
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans-4.0.xsd">
    <bean name="greetingServiceImpl" class="com.wrox.GreetingServiceImpl" />
</beans>
```

接下来，你需要向部署中添加 `ContextLoaderListener`。

```xml
<context-param>
  <param-name>contextConfigLocation</param-name>
  <param-value>WEB-INF/rootContext.xml</param-value>
</context-param>
<listener>
  <class-name>org.springframework.web.context.ContextLoaderListener</class-name>
</listener>
```

你现在有了两个应用上下文：根应用上下文包含 greeting bean；而 `DispatcherServlet` 上下文继承了所有的根 bean，包含了 `helloController` bean，并初始化了注解驱动的控制器映射。为了让事情变得更有趣一点，请调整控制器中 `helloName` 方法的请求映射。

```java
@RequestMapping(value = "/*", params = {"name"})
public String helloName(@RequestParam("name") String name)
```

该方法被映射到 URL 作为 `hello` 方法，但它要求请求中必须存在 `name` 参数。参数的存在与否决定了 Spring 将请求发送到哪个地方。为了证明这一点，请编译并启动你的应用程序，尝试访问 `http://localhost:8080/xml/` 和 `http://localhost:8080/xml?name=Nick` URL。



> 注意：你可能已经注意到 Spring Framework 会向调试控制台和你的应用程序打印日志消息。在使用 Spring Log4j 吗？并没有直接使用，Spring 使用 Apache Logging 作为其日志 API。由于你的项目中所有类路径上都存在 `org.apache.logging.log4j.log4j-core` Commons Logging 桥接，Spring Framework 记录到 Commons Logging 的事件会到达 Log4j 并写入你的日志配置中。由于你在 log4j 配置文件中将 `org.springframework.framework` 的日志级别设置为 INFO，因此会出现 INFO 或更高级别的消息。

# 创建混合配置

正如你所想象的，使用 XML 配置 Spring Framework 可能会非常枯燥，而且之前的示例并没有演示 `MultiActionController` 和 `SimpleUrlHandlerMapping` 类——这是一种旧有的机制（在 Spring 4.0 中已移除），用于将请求映射到控制器，它涉及冗长的 XML 以及接受 `HttpServletRequest` 和 `HttpServletResponse` 的字符串方法。在大型应用程序中，你可以定义数百个 bean，每个 bean 都需要三或更多行的 XML。这种配置方法看起来并不比在部署描述符中使用 XML 配置 Servlets 好到哪里。

如果你是 XML 显式性的粉丝，但又不想那么长的配置文件——这些文件可能会变得极其难以维护——你可以创建一个结合了两个世界优点的混合配置。

这种混合配置的核心是组件扫描和注解配置的概念。通过组件扫描，Spring 会扫描你指定的包或多个包中带有特定注解的类。（在这些包中）任何被 `@org.springframework.stereotype.Component` 注解的类都会成为 Spring 管理的 bean，这意味着 Spring 会实例化它们并检测它们的依赖关系。

用于此类组件扫描的其他注解：任何被 `@Component` 注解的注解都会成为组件注解，而任何被另一个组件注解注解的注解也会成为组件注解。因此，带有 `@Controller`、`@Repository` 和 `@Service` 的类（它们与 `@Component` 在同一个包中）也会成为 Spring 管理的 bean。你可以创建自己的注解。在第 17 章中，你将创建 `@RestController` 和标记有 `@Controller` 的 `@RestController`，以区分普通控制器和 RESTFUL 服务控制器。

另一个与注解配置协同工作的键是 `@org.springframework.beans.factory.annotation.Autowired`。你可以对任何私有的、保护的或公共的字段、接受一个或多个参数的公共方法使用 `@Autowired`。`@Autowired` 创建了对 Spring 应在实例化后注入的属性的依赖，它也可以标记构造函数。通常，Spring 管理的 bean 必须有无参数构造器，但在存在的情况下

在这些情况下，如果 Spring 无法找到 bean，它将抛出异常且无法启动。同样，如果它发现多个匹配的 bean，也会抛出异常并无法启动。`org.springframework.beans.factory.Qualifier` 允许你指定应该使用的 bean 名称。关于应该在字段、方法还是构造函数上使用 `@Autowired` 已经争了多年。有些团队偏好使用字段，因为涉及的代码最少。另一些团队偏好使用构造函数，因为这使得 mock 依赖变得可能。在现实世界中，哪种方法完全取决于你，但在本书中大多数情况下我们将注解字段，以便代码示例更简洁。

> 注意：Spring Framework 也支持某些 Java EE 注解来替代其专用注解。`javax.inject.Inject` 与 `@Autowired` 完全相同，不需要特殊配置即可使其工作。你可以像使用 `@Autowired` 一样对字段、构造函数或方法使用 `@Inject`。`javax.annotation.Resource` 也与 `@Autowired` 同。类似于，`javax.inject.Named` 是 `@Qualifier` 的等物，且效果与 `@Autowired` 相同。使用哪种注解很大程度上取决于你；但认为使用 javax.* 注解以后更容易切换到其他。

正如前面提到的，Spring 会自动提供默认的框架 bean，有时你的 bean 需要这些 bean。通常，不建议使用框架 bean，因为这样做会将你的应用程序与 Spring 耦合，并使其难以切换。然而，当你想要发布-订阅消息时，必须使用这些 bean。你可以请求对这些 bean 进行 `@Autowired` 或注入，Spring 会满足你的要求，但许多人更喜欢以不同的方式连接到 Spring 框架。为此，你有 `org.springframework.beans.factory.Aware` 接口。Aware 只是一个标记接口，供其他类扩展以表示对某些框架 bean 的感知。例如，`org.springframework.context.ApplicationContext` 接口提供了 `setApplicationContext` 将当前（非父级）上下文实例传递给你的 bean。如果你需要，可以通过调用 `ApplicationContext` 的 `getParent` 方法获取父上下文。

还有许多扩展 Aware 的接口，但一些流行的包括：

- `ApplicationEventListener`：用于获取发布应用程序事件的 bean
- `BeanFactoryAware`：用于可以手动检索或创建 bean 的 BeanFactory
- `EnvironmentAware`：用于获取可以从属性源获取属性的 Environment 对象
- `MessageSourceAware`：用于获取国际化消息源
- `ServletContextAware`：在 Java EE bean 环境中获取 ServletContext
- `ServletConfigAware`：在 DispatchersServlet Web 应用上下文管理的 bean 中获取 ServletConfig

在所有依赖项都注入之后、但在作为任何其他 bean 的依赖注入之前，对类执行某些初始化也是理想的。这通过实现 `org.springframework.beans.factory.InitializingBean` 接口可以轻松实现。

# 配置 Spring Framework | 343

在完成 bean 的所有配置后（依赖已注入且 Aware 方法已被调用），Spring 会调用它的 `afterPropertiesSet` 方法。如果你不想将应用程序与此专有的 Spring 接口绑定，可以创建一个仅有的标记了 `@javax.annotation.PostConstruct` 注解的公共、零参数方法。它被调用的时间与通常 `afterPropertiesSet` 相同。

如果你的 bean 没有声明任何需要注入的依赖，无论你使用哪一个，都会被调用。相反，如果你的 bean 在引用消失后且 Spring 关闭之前需要关闭，你可以实现 `org.springframework.beans.DisposableBean` 的 `destroy` 方法，或者创建一个标记了 `@javax.annotation.PreDestroy` 注解的公共、零参数方法。

> 注意：如果你希望对 bean 的生命周期比 `InitializingBean`、`@PostConstruct`、`DisposableBean` 或 `@PreDestroy` 提供更高级的控制，请查看 `org.springframework.context.Lifecycle` 和 `SmartLifecycle` 接口的 API 文档。

使用现有的部署配置以及 `rootContext.xml` 和 `ServletContext.xml` 文件启动组件和注解配置是一项简单的任务。你可以在 Spring-Hybrid 配置中看到这一点。在 `rootContext.xml` 配置中，简单地删除所有 bean 定义并将其替换为 `<context:annotation-config>` 和：

```xml
<xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xmlns:context="http://www.springframework.org/schema/context"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/beans-4.0.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.0.xsd">

  <context:annotation-config />
  <context:component-scan base-package="com.wrox" />

</beans>
```

`base-package` 属性指示 Spring 扫描路径下任何子包中的类，寻找 `@Component`、`@Controller`、`@Repository` 和 `@Service`。`ServletContext.xml` 配置文件仍然包含 `<mvc:annotation-driven>` 元素：

```xml
<xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xmlns:context="http://www.springframework.org/schema/context"
     xmlns:mvc="http://www.springframework.org/schema/mvc"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-4.0.xsd
http://www.springframework.org/schema/context
http://www.springframework.org/schema/context/spring-context-4.0.xsd
http://www.springframework.org/schema/mvc
http://www.springframework.org/schema/mvc/spring-4.0.xsd">

<mvc:annotation-driven />

<context:annotation-config />
<context:component-scan base-package="com.wrox" />

</beans>
```

你还有两个地方需要更改：

- 你必须告诉 Spring 实例化 GreetServiceImpl，因此在类类上标记 `@Service` 注解。

```java
@Service
public class GreetServiceImpl implements GreetingService
```

- 你需要告诉 Spring 将 GreetService 注入到 HelloController 中，因此在方法上标记 `@Autowired` 注解。

```java
@Autowired
public void setGreetingService(GreetingService greetingService)
```

你可能已经注意此配置中的一个问题，通过在启动 Tomcat 之前在 GreetService 管理器处设置断点可以观察到这一点。这个断点为两个不同的 HelloController 和 GreetServiceImpl 实例触发了两次。你也可以在日志文件中看到这一点。Spring 实例化了两次 GreetServiceImpl 和 HelloController：一次在应用上下文中，一次在 DispatcherServlet 的应用上下文中。为什么会发生这种情况？

记住，组件扫描默认会扫描所有的 `@Component`，而你在两个应用上下文中都开启了组件扫描。你真正想要的是分离你的 bean。根应用上下文持有持有服务、仓库和其他逻辑，而 DispatcherServlet 的应用上下文持有与 Web 相关的 bean。你可以通过在 `rootContext.xml` 中配置组件扫描来实现这一点：

```xml
<context:annotation-config />
<context:component-scan base-package="com.wrox" use-default-filters="false">
  <context:exclude-filter type="annotation" expression="org.springframework.stereotype.*" />
</context:component-scan>
```

`ServletContext.xml` 配置随后包含了针对 Web 相关 bean 的组件扫描：

```xml
<mvc:annotation-driven />

<context:annotation-config />
<context:component-scan base-package="com.wrox" use-default-filters="false">
  <context:include-filter type="annotation" expression="org.springframework.stereotype.Controller" />
</context:component-scan>
```

# 配置 Spring Framework | 345

# 使用 @Configuration 配置 Spring

如何选择 Spring 取决于个人喜好。开发团队倾向于 XML 文件的冗长和描述性。然而，使用 XML 配置 Spring 有一些明显的缺点：

- XML 配置很难进行调试。你必须下载并将 Spring Framework 源码附加到你的项目中，并知道在何设置断点以及如何单步执行。Spring 的代码非常混乱，调试它并不是一项易事。
- XML 配置无法进行单元测试。当然，你可以在单元测试中程序化启动 Spring 配置，但那并不是真正的单元测试。因为这样做会启动整个应用上下文并接线你所有的 bean，它实际上是一个集成测试。

Spring Framework 的纯 Java 配置允许你通过编程方式配置 Spring 容器，以便你轻松地调试和测试每个部分的配置。这对于那些单纯不喜欢 XML 的开发团队也有用。

在章的早些部分，你使用 `AnnotationConfigWebApplicationContext` 探索了程序化的 Spring 配置。使用该类时，你通过 `register` 方法注册配置类。这些配置类（必须标记 `@org.springframework.context.annotation.Configuration`）通过标记 `@Bean` 的无参数方法注册 bean。

编译应用程序并从 IDE 中启动 Tomcat。访问 http://localhost:8080/hybrid/ 和 http://localhost:8080/hybrid?name=John，你会发现应用程序的运行效果与使用 XML 时完全一致。

# 346 | 第 12 章 介绍 Spring 框架

`@PostConstruct` 和 `@PreDestroy` 方法。如果 `@Configuration` 类需要直接访问框架 Bean，或者在另一个 `@Configuration` 类中被创建，这些方法非常有用。如果它需要在 Spring 调用其 `@Bean` 方法之前，在依赖注入后初始化两个或多个依赖 Bean，这些方法也很有用。

`@Configuration` 类也是 `@Component` 类，这意味着如果你在包含这些类的包上开启了组件扫描，你的 `@Configuration` 类会被自动拾取。这可能会产生意料之中或意料之外的后果。如果你的 `@Configuration` 类在它所在的包上启用了组件扫描，你的 Bean 可能会被实例化两次，这是不好的。

另一方面，如果你将应用程序分为许多模块，每个模块都可以有自己的 `@Configuration`，你可以创建一个核心的 `@Configuration` 组件来扫描所有模块的 `@Configuration`。需要记住的关键点是，在结合 `@Configuration` 和组件扫描时，始终应该保持小心。

将驱动配置的值外部化是理想的。例如，你的应用程序可能需要使用 JNDI 数据源，但你不想硬编码数据源名称。相反，将数据源名称存储在配置时加载的设置文件中更好。使用 `@org.springframework.context.annotation.PropertySource` 注解就可以实现这一点。

```java
@Configuration
@PropertySource(
    "classpath:wrox/config/settings.properties",
    "file:config.properties"
)
public class ExampleConfiguration
```



# 引入 Spring 框架

要访问属性源中的属性，你可以使用 `org.springframework.core.env.Environment` 实例来手动获取值，或者使用 `@org.springframework.beans.factory.annotation.Value` 来原子地映射注入的属性值。

```java
public class ExampleConfiguration
{
    @Inject Environment environment;

    @Value("my.property.key") String myPropertyValue;

}
```

你可能无法或不想将整个配置包含在一个类中。同样如此，你可能无法用 Java 配置一切。正如之前讨论的，某些工具可能需要 XML 配置。`@org.springframework.context.annotation.Import` 和 `@ImportResource` 注解提供了这些需求的支持。

```java
@Configuration
@Import ({ DatabaseConfiguration.class, ClusterConfiguration.class })
@ImportResource("classpath:wrox/config/spring-security.xml")
public class ExampleConfiguration
```

## 配置 Spring 框架

在之前的代码段中，Spring 框架将加载 `ExampleConfiguration` 中包含的配置以及 `DatabaseConfiguration`、`ClusterConfiguration` 和 `spring-security.xml` 中的配置。它不会按特定顺序初始化和执行这些配置；它会确定任何配置是否依赖于其他配置，并按照满足这些依赖关系的顺序来初始化配置。

Spring 框架有很多你已经使用过的不涉及 `<bean>` 定义的 XML 配置功能。这些允许你在 Bean 之前指定特定的框架 Bean 定义，但允许你以最小的精力指定配置，并包含如 `<mvc:annotation-driven>` 和 `<context:component-scan>` 等内容。使用一组配置相关的注解可以替代所有的命名空间功能。你可以通过对任何标记了 `@Configuration` 的类添加以下注解来启用这些功能。你将在书的其余部分学习更多关于这些注解的知识。

- `@ComponentScan` 替换了 `<context:component-scan>` 并在指定的包或包上启用扫描。与其对应的功能一样，你可以启用或禁用默认过滤器，并通过包含或排除来精调组件扫描算法。
- `@EnableAspectJAutoProxy` 是 `<aop:autoproxy>` 的替代品，它支持处理带有 AspectJ `@Aspect` 注解的类，并使用面向切面的编程对方法进行适当建议。
- `@EnableAsync` 替换了 Spring 的 `<task:>` 命名空间部分，并启用 Spring 的异步方法执行。通过 `AsyncConfigurer` 接口，你的 `@Configuration` 可以精调异步行为的配置。
- `@EnableCaching` 启用 Spring 的注解驱动缓存管理功能，并替换了 `cache:<*>` 命名空间。
- `@EnableLoadTimeWeaving` 替换了 `<context:load-time-weaver>`。它更改了 `@Transactional`、`@Configurable`、`@Aspect` 等多个功能的使用方式。在大多数情况下你不需要此功能，但当你与 Java Persistence API (JPA) 工作时，它是更好的。重要的是，它与 `@EnableAspectJAutoProxy` 是互斥的。
- `@EnableBeanExport` 是 `<context:bean-export>` 的替代品，并指示 Spring 将某些框架 Bean 和标记了 `@ManagedResource` 的 Bean 导出为 JMX Bean。
- `@Scheduling` 替换了 Spring 的 `<task:>` 命名空间剩余，并通过 `@Scheduled` 激活调度方法执行，使用由 `@EnableAsync` 启用的 `@Async` 方法执行。
- `@EnableSpringConfigured` 在非 Spring 管理的 Bean 对象中进行依赖注入并替换了 `<context:spring-configured>`。它需要加载时织入支持此功能，因为它必须拦截对象的构造。
- `@EnableTransactionManagement` 替换了 `<tx:annotation-driven>` 并为标记了 `@Transactional` 注解的方法启用数据库事务管理。
- `@EnableWebMvc` 注解驱动的控制器请求映射并替换了 `<mvc:annotation-driven>`。它激活了一个非常复杂的配置，你通常对其进行自定义。你可以通过让你的 `@Configuration` 类实现 `WebMvcConfigurer` 或更多接口来自定义整个 Web MVC 配置，也可以通过扩展 `WebMvcConfigurerAdapter` 仅自定义你需要的部分。

Spring-Java 项目演示了从 `WebApplicationInitializer` 启动到根上下文和 DispatcherServlet 上下文 `@Configuration` 类的纯 Java 配置使用。包括 `GreetingService`、`GreetingServiceImpl` 和 `HelloController` 类。

## 利用 Bean 定义配置

```java
public class Bootstrap WebApplicationInitializer
{
    @Override
    public void onStartup(ServletContext container) throws ServletException
    {
        container.getServletRegistration("default").addMapping("/*");

        AnnotationConfigWebApplicationContext rootContext =
            new AnnotationConfigWebApplicationContext();
        rootContext.register(RootConfigSource.class);
        container.addListener(new ContextLoaderListener(rootContext));

        AnnotationConfigWebApplicationContext servletContext =
            new AnnotationConfigWebApplicationContext();
        servletContext.register(ServletContextConfiguration.class);
        ServletRegistration.Dynamic dispatcher = container.addServlet("Dispatcher", new DispatcherServlet(servletContext));
        dispatcher.loadOnStartup(1);
        dispatcher.addMapping("/*");
    }
}
```

包含无模式数据存储的 NoSQL 仓库。用户可以安装同一个可执行文件，并通过简单的配置开关启用正确的配置。

- 你可能想要创建不同的开发（Development）、质量保证（Quality Assurance）和生产（Production）配置。在开发配置中，你可能可能会硬编码某些设置，例如所有开发者都必须创建的本地数据库连接。同样，质量保证配置可能包含与开发机器环境不同的硬编码设置。毫无疑问，你的生产环境团队需要更改应用程序的设置，而无需等待你进行更改并重新编译，因此生产配置将从属性文件中加载这些设置，你的技术人员可以更改该文件。

## 理解配置的工作原理

与提供配置文件的其他技术（如 Maven）类似，使用 Spring Bean 定义包含两个部分：声明和激活。你可以使用 XML 配置文件中的 `<beans>` 元素、`@Configuration` 类或 `@Component`（或两者兼有）来声明配置。任何 `<beans>` 元素都可以包含一个 `profile` 属性，以指示它属于特定的配置。幸运的是，你不需要为每个想要的配置都创建一个新的配置文件，因为你可以嵌套 `<beans>` 元素。以下代码演示了这一点：

```xml
<xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-4.0.xsd">

  <beans profile="development, qa">
    <jdbc:embedded-database id="dataSource" type="SQL">
      <jdbc:script location="classpath:wrox/config/sql/schema.sql"/>
      <jdbc:script location="classpath:wrox/config/sql/test-data.sql"/>
    </jdbc:embedded-database>
  </beans>

  <beans profile="production">
    <context:property-placeholder location="file:/settings.properties" />
    <jee:jndi-lookup id="dataSource"
      jndi-name="java:comp/env/${production.dsn}" />
  </beans>

</beans>
```

在这个示例中，两个不同配置的 DataSource 被注册在不同的配置中。如果开发或 qa 配置处于激活状态，则使用它；而只有在生产配置激活状态时，才会会在 JNDI 上文中查找该名称的数据源。由于两个 bean 都实现了 DataSource 且具有相同的 bean ID，任何地方都可以使用 dataSource bean 的引用，任何 `@Component` 都可以自动注入相应的 DataSource。你也可以使用 Java `@Configuration` 实现此功能，如下代码所示：

## 利用 Bean 定义配置

```java
interface DataConfiguration {
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
public class RootContextConfiguration {
}
```

```java
@Configuration
@Profile({"development", "qa"})
public abstract class DevQaDataConfiguration implements DataConfiguration {
    @Override
    @Bean
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
public class ProductionDataConfiguration implements DataConfiguration {
    @Value("production.dataSource")
    String dataSourceName;

    @Override
    @Bean
    public DataSource dataSourceLookup() {
        return new JndiDataSourceLookup()
            .getDataSource("java:comp/env/" + this.dataSourceName);
    }
}
```

在声明配置后，你可以通过一种或多种不同的方式激活它们。首先，你可以使用 `spring.profiles.active` 上文初始化参数：

```xml
<context-param>
    <param-name>spring.profiles.active</param-name>
    <param-value>development</param-value>
</context-param>
```

或者使用 Servlet 初始化参数：

```xml
<servlet>
...
  <init-param>
    <param-name>spring.profiles.active</param-name>
    <param-value>development</param-value>
  </init-param>
</servlet>
```

上下文参数影响 Web 应用程序内运行的所有 Spring 应用上文，而 Servlet 初始化参数仅影响设置了它的 Dispatcher 应用上文。

你还可以使用 `-D.profiles.active=development` 命令行参数来激活整个 Java 虚拟机中所有应用程序的配置。使用这些技术中的任何一种，都可以指定多个要激活的配置，逗号分隔（`<param-value>profile1,2</param-value>`, `-Dspring.profiles.active=profile1,profile2`）。这意味着配置名称不能包含逗号。

你可以通过调用 `ConfigurableEnvironment` `setActive` 方法编程地激活一个或多个配置：

```java
configurableEnvironment.setActiveProfiles("development");
configurableEnvironment.setActiveProfiles("profile1", "profile2");
```

使用此方法会影响应用上文。

## 考虑反模式和安全问题

当你决定使用 Bean 配置来解决以下问题时，应该记住一些重要的考虑因素：

是否存在更简单的方法来实现相同的结果？如果从多个配置中创建了 Bean，是否可以使用属性源和更多的属性文件？

你的配置中存在哪些类型的 Bean？通常情况下，两个不同的配置具有相同的 Bean，只是开启了调试、分析或报告。

使用 Bean 配置的安全影响是什么？通常情况下，你不应该使用配置来控制应用程序的某些方面。因为用户可以通过简单的启用或禁用 JVM 属性来轻松绕过安全限制。一种显性的反模式是在开发配置中禁用所有安全检查，而在 QA 和生产配置中启用它们。用户可以通过从生产配置切换到开发配置来避免购买你的应用程序。有方法避免这种情况，例如在生产构建期间剔除类或利用 Java SecurityManager，但最好的做法是完全避免这种情况。

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target({ElementType.TYPE, ElementType.METHOD})
@Profile("development")
public @interface Development
{
}
```

### 总结

在本章中，你接触了 Spring 框架，并学习了 bean、应用上文和调度 Servlet。然后你尝试了启动和配置 Spring 框架的许多方法。你探索了依赖注入（DI）和反转控制（IoC）、面向切面编程、事务管理、发布订阅消息以及 Spring MVC 框架。你还了解了 Spring 框架相比其他技术的优势，以及 Spring 如何让 Web 应用程序、桌面应用程序以及服务器守护进程的开发变得更加简单快速。



在下一章中，你将深入研究控制器和 MVC 框架，以理解 `@RequestMapping` 注解的真正用途。在书的剩余部分，你将看到许多 Spring 应用程序。请记住，可以在 Spring 应用程序中决定使用 XML 还是 Java 启动以及 XML、混合或 Java 配置。但是，为了一致性，从现在开始将专门使用 Java 启动和配置。

# 用控制器替换你的 Servlets

- 什么是 `@RequestMapping`？
- 如何利用 Spring Framework 的模型和视图模式
- 使用表单对象简化生活
- 保持客户支持应用程序的更新

## 本章内容

## 本章对应的 WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/javaforwebapps` 的 Download Code 标签页找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- 模型-视图-控制器 (MVC) 项目
- Spring-Forms 项目
- Customer-Support-v10 项目

## 本章的新 MAVEN 依赖

除了之前章节引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-oxm</artifactId>
  <version>4.0.2.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

# 理解 @RequestMapping

在第 12 章中，你学习了 Spring Framework 控制器以及如何使用 `@RequestMapping` 注解将请求映射到控制器中的方法。`RequestMapping` 是 Servlet 工具集中一个极其强大的工具，可以根据 URL、请求的 `Content-Type` 或 `Accept` 请求头、通过指定请求头的存在或值，或者上述这些者的任何组合，将 HTTP 请求映射到目标。

通过 `@RequestMapping`，你不再需要在 Servlet 的 `doGet` 或类似方法中使用复杂的 `switch` 语句或逻辑分支来选择要执行的方法。相反，请求会根据其行为自动路由到相应的控制器和方法。请求到相应控制器和方法的映射是通过各种 `@RequestMapping` 注解属性建立的。被映射的方法可以有任何名称、任意数量的参数以及多种返回类型之一。在本节中，你将学习到所有这些功能。

# 使用 @RequestMapping 属性缩小请求映射

`@RequestMapping` 注解揭示了哪些请求映射到特定方法。

你可以将 `@RequestMapping` 放在控制器上，或者同时放在控制器类及其方法上。在控制器类和方法上放置该注解会建立关于映射的继承和优先级规则。为类建立的某些 `@RequestMapping` 属性会被继承并与为方法建立的属性相加，而为方法建立的其他属性会覆盖为类建立的属性。因此，理解每个属性以及方法上的哪些值会增加或覆盖类上的值非常重要。

> **注意**：只有在控制器类上指定的 `@RequestMapping` 会被考虑，其父类上指定的不会。因此，你不能在抽象类上添加注解并让类继承该抽象类的映射。

## URL 限制

你已经使用 `@RequestMapping` 根据 URL 缩小方法可以响应的请求。使用 `value` 属性（隐式或显式地使用其他属性），你可以指定任何 Ant 风格的 URL 模式。这比 Servlet URL 映射灵活得多（后者可能只能以通配符开头或结尾，且不能在 URL 中间有多个通配符）。控制器方法映射使用 `DispatcherServlet` 的 Servlet URL 映射、控制器映射（如果适用）以及方法映射构建，全部由正斜杠分隔。为了演示，考虑以下映射到不同 URL 方法：

```java
@RequestMapping("viewProduct")
public String viewProduct(...) { ... }

@RequestMapping("addToCart")
public String addProductToCart(...) { ... }

@RequestMapping("writeReview")
public String writeProductServlet(...) { ... }
```

在这种情况下，如果你将 `DispatcherServlet` 映射到上下文根 (`/`) ，这些方法的应用程序相对 URL 分别变为 `/viewProduct`、`/addToCart` 和 `/writeReview`。假设你将 `DispatcherServlet` 映射到 `/store/*`，这些方法的 URL 分别变为 `/store/viewProduct`、`/store/addToCart` 和 `/store/writeReview`。

> **注意**：如果你熟悉 Ant 风格模式，请花几分钟查看 Apache Ant 文档。

如果你发现控制器中的许多 URL 共享一个公共元素，可以使用映射继承来减少冗余：

```java
@RequestMapping("product")
public class ProductController {
    @RequestMapping("view")
    public String viewProduct(...) { ... }

    @RequestMapping("addToCart")
    public String addProductToCart(...) { ... }

    @RequestMapping("writeReview")
    public String writeProductReview(...) { ... }
}
```

在这种情况下，如果 `DispatcherServlet` 映射到根目录，方法 URL 变为 `/product/view`、`/product/addToCart` 和 `/product/writeReview`。如果 `DispatcherServlet` 映射到 `/store/*`，则 URL 变为 `/store/product/view` 等。

URL 映射的另一个重要方面是，如果请求匹配了多个不同的 URL 映射，最具体的映射胜出。因此，考虑以下映射：

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

## 请求方法限制

你可以使用 `method` 属性将映射限制为特定的 HTTP 请求方法。该属性接受一个 `RequestMethod` 枚举数组。以下映射仅响应 `GET` 请求：

```java
@RequestMapping(value="user", method=RequestMethod.GET)
public User user(...) { ... }
```

## 参数限制

你可以使用 `params` 属性根据请求参数的存在或值来缩小映射范围。该属性接受一个字符串数组，每个字符串可以是参数名（表示该参数必须存在）、`!参数名`（表示该参数必须不存在）、`参数名=值`（表示该参数必须等于该值）或 `参数名!=值`（表示该参数必须不等于该值）。以下映射仅匹配包含 `id` 参数且 `type` 参数不等于 `admin` 的请求：

```java
@RequestMapping(value="user", params={"id", "type!=admin"})
public User user(...) { ... }
```

## 头部限制

你可以使用 `headers` 属性根据请求头的存在或值来缩小映射范围。语法与 `params` 类似。头部匹配是不区分大小写的。以下映射仅匹配包含 `X-Client` 头部且 `Content-Type` 头部为任何文本类型的请求：

```java
@RequestMapping(value="user", headers={"X-Client", "content-type=text/*"})
public User user(...) { ... }
```

## Content Type 限制

你可以使用请求类型或预期的响应类型（或两者）来进一步进行请求映射。使用 `headers` 可以实现这些限制，而 `consumes` 和 `produces` 属性是为了方便这项任务的便利。

`consumes` 属性接受一个或多个媒体类型（或媒体通配符），必须匹配请求的 `Content-Type` 头部。这定义了方法可以消费的类型。同样，`produces` 属性接受一个或多个媒体类型（或通配符），必须匹配请求的 `Accept` 头部。因此，它指定了方法可以产生的内容类型，以便 Spring 确定客户端期望的是哪种。以下请求映射仅匹配 `Content-Type` 为 `application/json` 或 `text/json` 且 `Accept` 头部包含 `application/json` 或 `text/json` 的请求。

```java
@RequestMapping(value="son", consumes={"text/json", "application/json"}, produces={"text/json", "application/json"})
public Spring son(...) { ... }
```

如果在类 `@RequestMapping` 和方法 `@RequestMapping` 中都指定了，方法上的 `consumes` 和 `produces` 属性将覆盖类上的属性。

> **注意**：内容类型限制很有用，但并不总是实现内容协商的最佳方法。本章的“配置内容协商”部分将对此主题进行更详细的介绍。

# 指定控制器方法参数

方法可以拥有任意数量不同类型的参数。Spring Framework 非常灵活。最简单的方法零参数，而复杂的方法可能有十个或更多。Spring 可以理解这些参数的作用，并在调用时提供适当的值。此外，简单的配置可以扩展 Spring 理解的参数类型。

## 标准 Servlet 类型

当需要时，Spring 可以为你的方法提供与 Servlet API 相关的许多参数。传递给这些参数的值永远不会为 `null`，因为 Spring 保证了它们的值。你的方法可以指定任何一个或多个参数类型：

- `HttpServletRequest`，用于使用请求属性
- `HttpServletResponse`，用于操作包响应
- `HttpSession`，用于操作 HTTP 会话
- `InputStream` 或 `Reader`（但不能两者兼具），用于读取请求体。在完成后，你不应该关闭此对象。
- `OutputStream` 或 `Writer`（但不能两者兼具），用于写入响应体。在完成后，你不应该关闭此对象。
- 客户端识别的 `java.util.Locale` 应用于本地化目的（如果指定，则使用默认本地化）。
- `org.springframework.web.context.request.WebRequest`，用于在不直接使用 Servlet API 的情况下使用请求属性并操作 HTTP 会话。如果你在同一个方法中也有 `HttpServletRequest`、`HttpServletResponse` 或 `HttpSession` 类型的参数，则不应使用此参数类型。

## 注解请求属性

你可以看到几个注解（它们都是 `org.springframework.web.bind.annotation` 包中的），用以指示方法参数的值应该从请求的某个属性获取。在大多数情况下，标记有这些注解之一的参数是基本类型或包装类型、`String`、`Class`、`File`、`Locale`、`Pattern`、`java.util.Properties` 或 `java.net.URL`，或者这些类型的任何集合。如果可能，Spring 会自动将值转换为该类型。你也可以向 Spring Framework 注册自定义的 `java.beans.PropertyEditor` 或 `org.springframework.core.convert.converter.Converter` 来处理其他类型。

`@RequestParam` 注解表示方法参数应该派自命名的请求参数。你使用 `value` 属性（隐式或显式）指定请求名称。默认情况下，该注解表示请求参数是必须的，如果没有它请求将无法映射。你可以将 `required` 设置为 `false`（使请求参数变为可选），在这种情况下，如果请求不包含该请求参数，则参数值为 `null`。你还可以使用 `defaultValue` 属性在请求缺少参数时传递除 `null` 以外的值。以下方法接受一个 `id` 请求参数、一个带有默认值的可选 `name` 参数，以及一个带有空字符串作为默认值的可选 `key` 参数。请求参数名称是区分大小写的。

```java
@RequestMapping("user")
public String user(@RequestParam("id") long userId,
    @RequestParam(value="name", required=false) String name,
    @RequestParam(value="key", defaultValue="") String key)
    { ... }
```

> **注意**：使用 `@RequestParam` 时，并不严格要求你指定 `value` 属性。Spring Framework 会推断请求参数名等于方法参数名。然而，这仅当你的代码在带有本地符号调试信息的情况下编译时才有效；否则 Spring 无法检测参数名。作为启用调试符号的替代方案，Spring 还支持 Java 8 引入的新类型参数名反射，这要求你在编译时启用了 `-parameters` 命令行参数。如果你无法依赖这两者任何一个，则应该坚持显式指定请求参数名称。

如果你期望一个请求参数有多个值，请将相应的方法参数设置为相应类型的数组或 `Collection`。

你还可以通过对类型为 `Map<String, String>` 的单个参数进行注解，在 `Map` 中获取请求参数值。该 map 将包含请求传递的所有参数。如果你想捕获特定参数，可以在这些参数上使用 `@RequestParam` 注解，并使用 `Map` 处理剩余参数。

## 路径变量

`@PathVariable` 注解用于将 URI 模板变量绑定到方法参数。你可以使用 `value` 属性指定 URI 模板变量名。以下示例展示了如何提取 `hotelId` 路径变量：

```java
@RequestMapping("/hotel/{hotelId}/guest")
public String getForRoom(@PathVariable("hotelId") long hotelId) { ... }
```

## 矩阵变量

`@MatrixVariable` 注解用于将 URI 中的矩阵变量（如 `/path;var=value`）绑定到方法参数。你可以使用 `pathVar` 属性指定矩阵变量所在的路径变量名。以下示例展示了如何提取 `hotelId` 路径变量上的矩阵变量：

```java
@RequestMapping("/hotel/{hotelId}/guest")
public String getForRoom(@PathVariable("hotelId") long hotelId,
    @MatrixVariable(pathVar="hotelId") Map<String, String> matrixVars) { ... }
```

## 输入绑定型表单对象

在处理 HTML 表单时，客户端提交的内容通常包含十个或更多字段。考虑一个用户注册表单，它可能包含用户名、密码、确认密码、电子邮件地址、姓氏、电话号码等。

尽管 `@RequestParam` 确实是一个非常有用的工具，但为方法提供几十个参数是非常麻烦的，而且会让单元测试变得脆弱。相反，Spring Framework 允许你将表单对象（也称为命令对象）作为控制器的一个参数。表单对象仅仅是带有访问方法和修改方法的 POJO。它们不需要实现任何特殊接口，你不需要用特殊注解来映射控制器参数，Spring 就能将其识别为表单对象。

```java
public class UserRegistrationForm {
    private String username;
    private String password;
    private String emailAddress;

    // other fields, and mutators and accessors
}
```

```java
@RequestMapping("*")
public class UserController {
    @RequestMapping(value="join", method=RequestMethod.POST)
    public String join(UserRegistrationForm form) { ... }
}
```

在这个示例中，Spring 会在 `UserRegistrationForm` 中查找以 `set` 开头的方法。它通过参数名称将请求参数映射到表单对象的属性。例如，`setUsername` 方法会被请求参数 `username` 的值调用，而 `setEmailAddress` 方法会被请求参数 `emailAddress` 的值调用。如果请求参数没有匹配任何表单对象属性，它们将被忽略。同样，如果你有表单对象属性，字符串类型的请求参数值将使用某些转换目标类型参数的转换器转换为其目标属性类型。

Spring 还可以自动验证你的表单对象的细节，这意味着你可以避免在控制器方法中嵌入验证逻辑。如果你启用了 Bean 验证并在表单对象参数上标记了 `@javax.validation.Valid`，那么紧跟表单对象参数之后的参数类型可以是 `org.springframework.validation.Errors` 或 `org.springframework.validation.BindingResult`。Spring 调用该方法，该参数的值就是验证过程的结果。如果紧跟对象参数的参数不是 `Errors` 或 `BindingResult` 对象且对象验证失败，Spring 将直接抛出 `org.springframework.web.bind.MethodArgumentNotValidException`。



```java
@RequestMapping(value="join", method=RequestMethod.POST)
public String join(@Valid UserRegistrationForm form,
BindingResult validation) { ... }
```

关于对象验证如何工作的细节以及如何启用它，将在第 16 章中介绍。

## 请求体转换与实体

到目前为止，你看到的与 `@RequestMapping` 配合使用的工具处理的是传统的 GET 和 POST 网络请求的传统功能：标头、URL 查询参数和 `x-www-form-encoded` 请求体（表单）。然而，POST 和 PUT 请求包含的数据除了 `x-www-form-encoded` 以外的格式。例如，在 RESTful 服务中，POST 或 PUT 请求可能包含 JSON 或 XML 格式的主体，以表示比 `x-www-form-encoded` 表达更复杂的数据。请求体还可以包含二进制、base64 编码数据，或者说，客户端和服务器可以理解的任何格式。当这些数据代表某种对象时，它通常被称为请求实体（request entity）或 HTTP 实体。使用 `@RequestBody` 注解，Spring 会自动将请求实体转换为控制器方法的参数。

```java
public class Account {
    public long accountId;
    public String accountName;
    public String emailAddress;

    // other fields, and mutators and accessors
}
@RequestMapping("account")
public class AccountController {
    @RequestMapping(value="update", method=RequestMethod.POST)
    public String update(@RequestBody Account account) { ... }
}
```

默认情况下，`@RequestBody` 体是必填的，但你可以使用 `required` 属性将其变为可选。请求实体使用 Spring 的 HTTP 消息转换器自动转换。在其他参数类型（如 `@RequestParam` 和 `@RequestHeader`）之后，简单类型通过 `PropertyEditors` 和 `Converters` 从其字符串表示自动转换为目标类型，而请求实体必须同时具有源格式（JSON、XML、二进制等）和目标格式。

你不局限于直接将部分上传作为控制器方法的参数。你的表单对象可以包含 `Part` 或 `MultipartFile` 字段，Spring 会自动知道它必须从文件部分获取值并相应地转换这些值。

```java
public class UploadForm {
    private String username;
    private List<Part> uploads;

    // mutators and accessors
}

@RequestMapping(value="/upload", method=RequestMethod.POST)
public String upload(UploadForm form) { ... }
```

到目前为止，你一直使用的是专门用于文件上传的 multipart 请求，但对于 Spring 请求处理来说，文件上传并不是支持的 multipart 内容。请求可能不是 `multipart/form-data`，而是 `multipart/mixed`。它的部分可以包含任何内容，包括 JSON、XML 或二进制格式的请求实体（entities）。Spring 可以将这些部分转换为其具有适当 HTTP 消息转换器的任何类型。你甚至可以对非文件部分进行验证，就像你对来自浏览器上传文件的 `@RequestBody` 能够所做的那样样。

```java
@RequestMapping(value="update", method=RequestMethod.POST)
public String update(@Valid @Part("account") Account account, BindingResult validation) { ... }
```

需要注意的是，以这种方式使用 multipart 请求是非常不寻常的。通常，实体请求（entity requests）有一个部分的主体；multipart 请求来自浏览器上传文件。

## 模型类型

在下一节中，你将探索 Spring MVC 架构中的模型和视图。这里需要注意的是，你的控制器方法可能有一个类型为 `Map<String, Object>`、`org.springframework.ui.Model` 或 `ModelMap` 的单注解参数。返回这些类型其中一种类型的方法代表了 Spring 传递给你的视图进行渲染的模型，在方法执行期间，你可以根据需要向其添加任何属性。

## 为控制器方法选择有效的返回类型

正如你所声明的，Spring Framework 对于 `@RequestMapping` 方法指定的方法参数是极其灵活的。同样，Spring 对于控制器方法返回的类型也非常灵活。通常来说，虽然方法参数通常与请求内容有关，但返回类型通常与响应有关。例如，`void` 类型告诉 Spring 你的方法手动处理写入响应，因此 Spring 不会对你的返回方法进行进一步处理。然而，更常见的情况是控制器方法返回某种类型（有时带有注解），指示 Spring 如何对请求做出响应。

### 模型类型

控制器方法可以返回 `Map<String, Object>`、`ModelMap` 或 `Model`。这是指定将其中一种类型作为方法参数的替代方案。Spring 可以识别此返回类型为一种方法逻辑，并根据配置的 `org.springframework.framework.web.servlet.RequestToViewNameTranslator`（默认为 `org.springframework.framework.web.servlet.view.DefaultRequestToViewNameTranslator`）自动确定视图。

### 视图类型

为了指示使用视图渲染器响应，你的控制器方法可以返回多种视图类型（或任何实现 `View` 接口的类）。`org.springframework.web.servlet.View` 接口表示你的方法返回了一个显式视图。在方法返回后，处理将交给该视图。Spring 提供了数十种视图实现（例如 `RedirectView`），你也可以创建自己的。你的控制器也可以返回一个 `String`，指示要解析的视图名称。你将在下一节中学习更多关于视图解析的内容。最后，你的方法可以返回一个 `org.springframework.web.servlet.ModelAndView`。该类提供了同时返回视图和模型类型，或者字符串视图名称和模型类型的能力。

### 响应体实体

就像请求可以包含 HTTP 实体（响应实体）一样，主体也可以包含 HTTP 实体（响应实体）。控制器方法可以返回 `ResponseEntity<?>` 或 `org.springframework.http.ResponseEntity<?>`，Spring 根据协商的内容类型使用适当的消息转换器将实体中的主体转换为正确的响应类型。`HttpEntity` 允许设置响应主体和各种标头。`ResponseEntity` 继承自 `HttpEntity`，增加了以 `org.springframework.http.HttpStatus` 形式设置响应状态码的能力。

```java
@RequestMapping(value='user', method=RequestMethod.GET)
public User getUser(Long id) {
    User user = userService.getUser(id);
    return new ResponseEntity<>(user, HttpStatus.OK);
}
```

如果你不想使用 `HttpEntity`，可以返回对象本身并对其使用 `@ResponseBody` 注解，效果是相同的。你可以对方法使用 `@ResponseStatus` 来设置响应状态码（如果你使用了 `@ResponseBody`，默认为 200 OK）。

```java
@RequestMapping(value='user/{userId}', method=RequestMethod.GET)
@ResponseBody
@ResponseStatus(HttpStatus.OK)
public User getUser(@PathVariable Long userId) {
    return userService.getUser(userId);
}
```

### 任意返回类型

你的方法可以返回任何对象，Spring 假设该对象是一个属性。它使用返回类型类的驼峰命名作为模型属性，除非使用了 `@ModelAttribute` 注解，在这种情况下 Spring 将使用注解指定的名称。在下面的示例中，第一个方法的返回值成为名为 `account` 的属性，第二个方法的返回值成为名为 `user` 的属性。

```java
@RequestMapping("/userId")
public UserAccount account(@PathVariable Long userId) {
    ...
}

@RequestMapping("/userId")
@ModelAttribute("user")
public UserView user(@PathVariable Long userId) {
    ...
}
```

### 异步类型

除了之前列出的所有返回类型外，控制器还可能返回 `java.util.concurrent.Callable<??>` 或 `org.springframework.web.context.request.async.DeferredResult<?>`。这些类型允许 Spring 在单独线程中执行 `Callable` 或 `DeferredResult`，从而释放请求线程。你通常会对响应时间较长的请求这样做，特别是当它们在网络或 I/O 上花费大量时间时。`Callable` 或 `DeferredResult` 的参数（返回类型）应该是你通常从控制器返回的类型（`View`、`String`、`StringMap`、`ModelAndView`、`ResponseEntity` 等）。你可以对控制器使用 `@ResponseBody`、`@ResponseStatus` 或 `@ModelAttribute` 来触发相应的处理器。第 9 章和第 19 章中关于使用过滤器和日志处理异步请求的相同异常也适用于此处。

## 使用框架的模型和视图模式

正如你圆满结束这一章的，Spring 的 MVC 架构因其依赖于模型-视图-控制器（MVC）设计模式而命名。

用一句话总结：控制器操纵代表用户感兴趣信息的模型，并将其传递给模型，模型随后以一种方式返回模型对用户有用。用户只会在有意识的情况下与视图交互，但在执行某些操作时，他会在无意中与控制器交互。MVC 模式在 Java 企业版环境中运行得非常好，实际上你从第 4 章开始就已经在使用它了。Servlet 以 `HttpServletRequest` 属性的形式构建模型，并代表请求的用户执行操作。然后，Servlet 将模型转发到视图（即 JSP）进行渲染（记住）：

Spring 通过将模型与请求分离，并使用一个可以用多种方式实现的高层 `View` 接口，来完成这两个步骤。`InternalView` 和 `JstlView` 分别实现了传统的 JSP 和 JSTL 增强型 JSP 视图。它们负责将模型属性转换为请求属性，并将请求转发到对应的 po。如果你不是 JSP 的用户，可以选择 `FreeMarkerTemplate`（支持 FreeMarker 模板引擎）、`VelocityView`（支持 Apache Velocity 模板引擎）以及 `TilesView`（支持 Apache Tiles 模板引擎）。你也可以为其他模板引擎实现视图。

如果你需要将模型转换为 JSON 或 XML 以用于 RESTful 服务和 Ajax 后端请求端点——Spring 提供了 `MappingJackson2View` 和 `MarshallingView`。它们支持 JSON 和 XML。你也可以使用 `RedirectView`，根据你构造它的，它会发送状态码为 302 Found（为了兼容 HTTP 1.0）或 303 See Other（HTTP 1.1 客户端的正确状态码）的 Location-header 响应。参见“更新客户应用程序”章节，你使用自定义的视图 `DownloadView` 将服务器端文件的内容发送到用户的浏览器。

当控制器方法返回 `View` 的实现，或者返回一个带有 `View` 实现的 `ModelAndView` 时，Spring 会直接使用 `View`，不需要额外的逻辑来确定如何向客户端展示模型。如果控制器方法返回一个字符串视图名称，或者一个用字符串名称构造的 `ModelAndView`，Spring 必须使用配置的 `org.springframework.web.servlet.ViewResolver` 将该视图名称解析为实际视图。如果方法返回模型或模型属性，Spring 必须先使用配置的 `RequestToViewTranslator`（如前所述）将请求转换为视图名称，然后使用 `ViewResolver` 解析命名的视图。最后，当控制器返回响应实体 `ResponseEntity` 或 `HttpEntity` 时，将使用内容协商来决定呈现实体的哪个视图。

本节涵盖了所有这些技术。你的应用程序可能在控制器中使用其中一种、部分或全部。你可以从 wrox.com 代码下载站点下载 Model-View-Controller 项目并进行练习。

## 使用显式视图和视图名称

Model-View-Controller 项目是按照程序化的方式进行启动和配置的，就像你在第 12 章学的那样：`WebApplication` 启动 Spring 框架，框架配置了两个 `@Configuration` 类：`RootContextConfiguration` 和 `ServletContextConfiguration`。对于此项目，所有请求都映射到 `HomeController` 类。

## 使用重定向视图

通常，你显式使用的最常见视图是 `org.springframework.web.servlet.view.RedirectView`，用于将客户端引导到不同的 URL。如果 URL 以协议（http:// 等）或网络前缀（//）开头，则被认为是绝对 URL。如果 URL 是相对的（没有协议或以斜杠开头），则被认为相对于当前 URL 是相对的（这是典型的 Web 和文件系统行为）。`RedirectView` 通常将以斜杠开头的 URL 视为服务器上下文 URL（在几乎几乎所有情况下，这并不是预期的行为）。因此，当你构造 `RedirectView` 时，启用上下文相关的绝对 URL 非常重要，正如 `HomeController` 中的第一个方法所所示。

```java
@RequestMapping("/dashboard")
public String dashboard(Map<String, Object> model)
{
    model.put("dashboardUrl", "/dashboard");
    return new RedirectView("${dashboardUrl}", true);
}
```

`RedirectView` 构造函数中的 `true` 参数告诉 `RedirectView` 该 URL 是相对于上下文的，而不是相对于服务器的。注意 `RedirectView` 的 URL 中的模板（`/dashboardUrl`）。`RedirectView` 会用模型中的属性替换此类模板。或者，在这种情况下，使用静态 URL 字符串构造视图（`new RedirectView("/dashboard", true)`）会更简单，但这个模板展示了 `RedirectView` 的威力。

如果没有处理程序，重定向到视图的最终 URL 是没有用的，而该方法在 `HomeController` 中处理了这个问题。

```java
@RequestMapping(value = "/dashboard", method = RequestMethod.GET)
public String dashboard(Map<String, Object> model)
{
    model.put("text", "This is a model attribute.");
    model.put("date", "Instant.now()");
    
    return "home/dashboard";
}
```

此方法返回 `/dashboard` URL，添加了文本和日期属性，并返回视图的字符串名称。但这意味着什么？Spring 如何获取这个名称并确定它在哪里？

## 配置视图解析



# 使用 Spring 框架的模型与视图模式

为了将此视图映射到实际视图，Spring 需要一个可以理解它的 `ViewResolver` 实例。创建解析器是一个在 `dispatcher servlet` 上下文中实例化框架 bean 的简单任务。对于此操作，你应该使用 `InternalResourceViewResolver`，它可以将视图名称转换为 JSP 文件名。这是通过 `ServletContextConfiguration` 的 `viewResolver` 方法实现的。

```java
@Bean
public ViewResolver viewResolver() {
    InternalResourceViewResolver resolver = new InternalResourceViewResolver();
    resolver.setViewClass(JspView.class);
    resolver.setPrefix("/WEB-INF/jsp/");
    resolver.setSuffix(".jsp");
    return resolver;
}
```

按照配置，`InternalResourceViewResolver` 通过添加前缀 `/WEB-INF/jsp/` 和后缀 `.jsp` 来解析名称。你不需要对视图名称做任何特殊处理。

## 创建视图

当然，`InternalResourceViewResolver` 通过添加前缀 `/WEB-INF/jsp/` 和后缀 `.jsp` 来解析名称。你不需要对视图名称做任何特殊处理。

```html
<%--variable type=`text`=java.lang.String--%>
<%--variable type=`date`=java.time.Instant--%>
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

## 使用模型属性的隐式视图

如果控制器方法返回模型或模型属性，Spring 必须先使用配置的 `RequestToViewTranslator`（如前所述）将请求转换为视图名称，然后使用 `ViewResolver` 解析命名的视图。

## 配置视图名称翻译

虽然你可以根据需要创建自己的 `RequestNameToTranslator`，但通常默认的足够。它会去掉应用上下文和扩展名。

```java
@Bean
public RequestNameToTranslator requestNameTranslator() {
    return new DefaultRequestNameToTranslator();
}
```

## 使用 @ModelAttribute

配置了视图名称翻译后，利用它非常简单。`HomeController` 中的 `userHome` 方法映射到 `/user/home` URL，创建一个 `User` 对象，设置某些值并返回该 `User`。在这种情况下，`User` 类是一个带有 `userId`、`username` 和 `name` 字段简单 POJO，并带有标准的修改器和访问器注解。

```java
@RequestMapping(value = "/user/home", method = RequestMethod.GET)
@ModelAttribute(name="currentUser")
public User userHome() {
    User user = new User();
    user.setUserId(1234987234L);
    user.setUsername("adam");
    user.setName("Adam Johnson");
    return user;
}
```

```html
Name: ${currentUser.name}<br />
</body>
</html>
```

现在编译项目，从 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/mvc/user/home`。你应该能看到在 `userHome` 控制器方法中创建的用户 ID、用户名和名称。名称翻译和视图解析共同工作，识别并显示了适用于请求的视图。

# 返回响应实体

获取请求实体和返回响应实体通常是留给 RESTful 服务或其他自动化任务的任务。在大多数情况下，只有当 JavaScript 应用向服务器发送 Ajax GET 或 POST 请求时，浏览器才会参与这些情况中。因此，HTTP 实体和内容协商将在第 17 章更详细地介绍。本节涵盖了处理响应实体以及配置消息转换器和内容的基础。

## 配置消息转换器

当服务器接收带有请求正体的 POST 或 PUT 请求时，该正体通常被称为 HTTP 实体或实体请求，也可能被称为消息。该消息无论何种格式，都会被转换为某种类型的 Java 对象，供你的控制器方法进行转换。这是根据请求的 `Content-Type` 头部发生的。

你已经学习了一个消息转换器，甚至可能没有意识到：`org.springframework.http.converter.FormHttpMessage` 负责将 `x-www-form-urlencoded` 消息转换为控制器方法使用的对象。消息转换器是双向的：它们既可以将传入的消息转换为 Java 对象，也可以将 Java 对象转换为导出的消息。它们运行基于识别 MIME 类型和目标类型的简单原理。每个转换器都拥有一个或多个 MIME 类型和 Java 类型，它可以将具有这些 MIME 类型的消息转换为对应类型的 Java 对象，反之亦然。这是内容协商过程的最后阶段。当 Spring 分配已协商的内容类型时，它会选择一个支持源类型和目标类型的转换器，并将其用于传入或导出的实体（如果适用）。在单个请求中，请求完全可能包含一种内容类型的消息，而服务器响应的是另一种类型的消息。

如果你需要配置任何内容，Spring 会为你自动创建某些消息转换器。在许多情况下，这种自动配置就足够了。为了演示和额外配置，Model-View-Controller 项目手动配置了消息转换器。要做到这一点，`ServletContext` 类必须扩展 `WebMvcConfigurerAdapter` 并重写 `configureMessageConverters` 方法。

```java
public class ServletContextConfiguration extends WebMvcConfigurerAdapter {
    @Inject ObjectMapper objectMapper;
    @Inject Marshaller marshaller;
    @Inject Unmarshaller unmarshaller;

    @Override
    public void configureMessageConverters(List<HttpMessageConverter<?>> converters) {
        converters.add(new ByteArrayHttpMessageConverter());
        converters.add(new StringHttpMessageConverter());
        converters.add(new FormHttpMessageConverter());
        converters.add(new SourceHttpMessageConverter<>());

        MarshallingJacksonHttpMessageConverter xmlConverter = new MarshallingJacksonHttpMessageConverter();
        xmlConverter.setSupportedMediaTypes(Arrays.asList(
            new MediaType("application", "xml"),
            new MediaType("text", "xml")
        ));
        xmlConverter.setMarshaller(this.marshaller);
        xmlConverter.setUnmarshaller(this.unmarshaller);
        converters.add(xmlConverter);

        MappingJacksonHttpMessageConverter jsonConverter = new MappingJacksonHttpMessageConverter();
        jsonConverter.setSupportedMediaTypes(Arrays.asList(
            new MediaType("application", "json"),
            new MediaType("text", "json")
        ));
        jsonConverter.setObjectMapper(this.objectMapper);
        converters.add(jsonConverter);
    }
}
```

`ByteArrayHttpMessageConverter`、`StringHttpMessageConverter`、`FormHttpMessageConverter` 和 `SourceHttpMessageConverter` 都是 Spring 会自动配置的转换器。它们在这里被配置，顺序与它们通常的配置顺序相同。顺序很重要，因为某些转换器处理更宽泛的 MIME 类型和 Java 类型范围，这可能会掩盖你想要使用的其他转换器。

`MarshallingHttpMessageConverter` 通常不会添加到消息转换器列表中，但在本例中为了支持从 XML 实体的转换。只要 Jackson Data Processor 在类路径上，`MappingJacksonHttpMessageConverter` 通常就会被自动创建。它是使用一个默认的、未配置的 `com.fasterxml.jackson.databind.ObjectMapper` 创建的，并且只支持 `application/json` MIME 内容类型。这里显示的配置添加了对 `text/json` 的支持，并使用了预配置的 `ObjectMapper`。

你一定注意到 `org.springframework.oxm.Unmarshaller` 和 `org.springframework.oxm.ObjectMapper` 被注入到配置类中，你可能在想它们来自哪里。为了让这些 bean 能够在应用程序中配置和共享，它们在 `RootContextConfiguration` 中进行了配置。`org.springframework.oxm.jaxb.Jaxb2Marshaller` 既是 `Marshaller` 也是 `Unmarshaller`，并满足依赖关系。

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
    marshaller.setPackagesToScan(new String[] {"com.example"});
    return marshaller;
}
```

Jackson `ObjectMapper` 配置完成了一些重要的工作：首先是查找并注册所有扩展模块，例如 JSR 310（Java 8 日期和时间）支持模块。然后将日期反序列化为时间戳整数（这意味着将以 ISO8601 字符串写入），并将反序列化的日期调整为当前时区（因此没有时间的被假设为 UTC）。`Jaxb2Marshaller` 的配置非常简单——只需扫描带注解的实体。

## 配置内容协商

内容协商是客户端发送一组首选响应类型（按偏好排序），服务器从中选择一个合适的内容类型（如果没有合适的则使用默认值）的过程。内容协商中最大且最具挑战性的部分是，如果客户端请求一个实体，它也会带有一个 `Content-type` 头部，但这并不一定是客户端想要的格式（尽管通常是）。然后是 `Accept` 头部，用于指示客户端接受的格式。这里的关键词是“格式”一词是复数；客户端可能指示许多可用格式并对每个格式指定偏好或优先级。旧浏览器发送的混乱的 `Accept` 头部，难以遵循，且最后打开 `text/html` 或者根本不打开。安装了 Microsoft Office 的 Windows 7 上的 Internet Explorer 8 发送了超过 200 字节的 `Accept` 头部，其中包含 14 种 MIME 类型，且没有一种是 `text/html`！

幸运的是，所有主流浏览器的最新版本发送的 `Accept` 头部都包含 `text/html`。此外，当使用 JavaScript 应用或 RESTful Web 服务时，客户端对 `Accept` 头部具有完全控制权，使其成为协商内容类型更可靠的因素。现实地说，服务器很少参与内容协商。在所有情况下，对 Web 应用程序的请求分为三类：

- 如果由于点击链接或在浏览器地址栏输入地址而产生的请求，目标是具有固定内容类型的资源，不受协商——HTML 页面（`text/html` 或 `application/xhtml+xml`）、下载的文件等。
- 如果是来自客户端 JavaScript 浏览器应用的 Ajax 请求，则客户端应用程序对执行内容协商的 `Accept` 头具有完全控制权。
- 如果是客户端应用程序访问您的 Web 服务，则它对执行内容协商的 `Accept` 头具有完全控制权。

Spring 中的内容协商使用多步方法来确定客户端希望接收返回的内容类型。有时消息转换器会被选用于请求和响应，有时则不会。当客户端请求实体时，始终会根据请求的 `Content-Type` 头来选择传入的消息转换器。当响应是一个实体时，传出的消息转换器是通过一个多步过程选择的：

1. Spring 在 URL 上查找文件扩展名。如果它包含文件扩展名（如 `.html`、`.xml`、`.json` 等），它将根据该扩展名确定请求的格式。如果不包含文件扩展名，或者扩展名未被识别，它将继续。
2. Spring 查找名为 `format` 的请求参数。（你可以更改此参数名。）如果它存在，它将使用请求的格式（html、json 等）。如果格式不存在或未被识别，它将确定所需的响应格式。
3. 最后，Spring 使用 `Accept` 头来确定所需的响应格式。

你可以自定义此过程以满足你的需求。你可以完全消除一个或多个步骤，并根据你想要执行内容协商的方式更改每个步骤的工作方式。（但是，你不能重新排序步骤）。模型-视图-控制器中的 `ServletContext` 类提供了 `WebMvcConfigurerAdapter` 的 `configureContentNegotiation` 方法来实现此。

```java
@Override
public void configureContentNegotiation(ContentNegotiationConfigurer configurer) {
    configurer.favorPathExtension(true).favorParameter(false)
        .parameterName("mediaType").ignoreAcceptHeader(false)
        .useJaf(false).defaultContentType(MediaType.APPLICATION_XML)
        .mediaType("xml", MediaType.APPLICATION_XML)
        .mediaType("json", MediaType.APPLICATION_JSON);
}
```

此配置启用了文件扩展名检查，禁用了请求参数检查，将请求参数名为 `mediaType`（此处已禁用，但此处用于演示），并确保 `Accept` 头不被忽略。它还禁用了 Java Activation Framework (JAF) —— 这是一个可以将文件扩展名映射到媒体类型等内容的工具 —— 转而手动指定支持的媒体类型。最后，它将默认内容类型设置为 `application/xml`，并添加了对 `application/xml` 和 `application/json` 的支持。

## 使用 @ResponseBody

现在内容协商已经经过妥当配置，你可以在控制器中使用它。`HomeController` 的 `getMethod` 正是这么做的。



```java
@RequestMapping(value = "/user/{userId}", method = RequestMethod.GET)
@ResponseBody
public User getUser(@PathVariable("userId") long userId)
{
    User user = new User();
    user.setUserId(userId);
    user.setUsername("john");
    user.setName("John Smith");
    return user;
}
```

注意 `@ResponseBody` 的使用，这就是所配置的内容协商策略。此方法使用 URI 模板变量和 `@PathVariable` 注解从请求参数的 URL 中获取用户 ID。现在编译应用程序，为你的 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/mvc/12`。你应该看到以 XML 形式表示的用户（如图 13-1 所示），因为你的浏览器发送的 Accept 头为 `application/xml` 或 `XML` 是你内容协商配置中的默认值。

![](img/4677f981a0e1067137bb55a122f8498d_414_0.png)

图 13-1

如果你更改 URL 末尾的 ID，XML 会发生变化以反映新的 ID。现在访问 `http://localhost:8080/mvc/13.json`，显示将从 XML 变为 JSON。我建议你使用 Chrome 或 Firefox，因为 Internet Explorer 会提示你下载 JSON 文件。你不需要更改控制器方法的 URL 映射，Spring 会识别扩展名，在请求映射时忽略它，并将其用于内容协商。现在如果你将扩展名从 JSON 改为 XML，显示将变回 XML。

> 注意：`JaxbMarshaller` 可以将 `User` 对象序列化为其 XML 表达式，因为 `User` 类标记了 `@javax.xml.bind.annotation.RootElement`。

# 使用表单对象让生活更轻松

Spring Framework 中的表单对象是编写基于浏览器的应用程序时最大的便利之一。定位、强制转换以及将请求参数转换为业务对象的工作可能是枯燥的，而且这种枯燥随着每个项目的而增加。wrox.com 展示了如何使用简单的控制器和几个 JSP 页面。`UserManagementController` 拥有两个私有字段和一个用于生成 ID 的同步方法。为了开始，它还有一个请求处理器 `displayUsers` 用于显示现有用户列表。

```java
@Controller
public class User {
    private final Map<Long, User> database = new HashMap<>();
    volatile long userIdSequence = 1;

    @RequestMapping(value = "list", method = RequestMethod.GET)
    public String displayUsers(Map<String, Object> model) {
        model.put("userList", database.values());
        return "user/list";
    }

    private synchronized long getNextUserId() {
        return userIdSequence++;
    }
}
```

`User` 类是一个简单的 POJO，具有 `userId`、`username` 和 `name` 字段以及相应的变变器（mutators）。`/WEB-INF/jsp/user/list.jsp` 提供了一个添加新用户的链接，并使用 `<c:forEach>` 标签来循环并显示现有用户。

```html
<!-- <variable id="userList" type="java.util.Collection<wrox.site.User>> -->
<!DOCTYPE html>
<html>
<head>
    <title>User List</title>
</head>
<body>
    <h2>Users</h2>
    <a href="${c:url value='/user/add'}">new user</a>
</body>
</html>
```

# 将表单对象添加到你的模型中

为了让你使用表单对象，它首先需要在显示表单的视图中是可访问的。`createUser(Map)` 方法向模型添加了一个新的 `UserForm` 对象并返回 `user/add` 名称。你可能会奇怪为什么代码同时使用了 `User` 和 `UserForm` 对象。诚然，在这种情况下这是多此一举。但它突显了业务对象并不总是看起来像表单对象。例如，你可能拥有许多不需要的字段，或者拥有格式不同的字段。实际上，很多时候必须分离表单对象和业务对象，而这演示了如何做到。

```java
@RequestMapping(value = "user/add", method = RequestMethod.GET)
public String create(Map<String, Object> model) {
    model.put("userForm", new UserForm());
    return "user/add";
}

@RequestMapping(value = "user/edit/{userId}", method = RequestMethod.GET)
@PathVariable("userId") long id {
    User user = this.userDatabase.get(id);
    UserForm form = new UserForm();
    form.setUserName(user.getUserName());
    form.setName(user.getName());
    model.put("userForm", form);
    return "user/edit";
}
```

注意 `editUser(Map, long)` 方法也向模型添加了 `UserForm`，但其方式不同。它首先获取正在编辑的 `User`，将用户信息拷贝到表单中，然后在返回 `user/edit` 视图名称之前将表单放入模型中。

# 使用 Spring Framework `<form>` 标签

`/WEB-INF/jsp/view/user/add.jsp` 和 `/WEB-INF/jsp/view/user/edit.jsp` 视图非常简单。它们做的只是设置标题 EL 变量并包含 `/WEB-INF/jsp/view/user/form.jsp`。

```jsp
<c:set var="title" value="Add User" />
<jsp:include file="form.jsp" />
```

这两行代码构成了整个 add.jsp，而 edit.jsp 几乎完全相同，只是标题设置为 "Edit User"。

```html
<!-- <id="userForm" type="wrox.site.UserForm"> -->
<!DOCTYPE html>
<html>
<head>
    <title>${title}</title>
</head>
<body>
    <form method="post" modelAttribute="userForm">
        <label path="username">Username</label> <br />
        <input path="username" /><br /><br />
        <label path="name">Name:</label><br />
        <input path="name" /><br /><br />
        <input type="submit" value="Save" />
    </form>
</body>
</html>
```

你可能首先注意到命名空间的使用。这个由 Spring 提供的标签库是对标准 `<form>` `<input>` 和 `<textarea>` 的封装，并提供了对表单对象的字段绑定。创建新用户时，这意义不大。但在编辑现有用户时，模型属性的值会自动放置在它们所属的字段中。这简化了你的代码，并消除了对正确转义值的担忧。在标签库中，你必须首先声明它。表单标签库在 base.jsp 文件中与其他标签一起声明：

```jsp
<%@ tag prefix="form" uri="http://www.springframework.org/tags" %>
```

该命名空间包含 14 个标签，封装了广泛的 Web 功能。除了属性外，每个标签都支持其等效 HTML 标签的所有标准 HTML 属性。`<form>` 标签是其他标签的一部分，指示字段将绑定到哪个模型属性对象。你不需要指定 action 属性（尽管可以），默认情况下 `<form:form>` 总是提交到当前页的 URL。其余 13 个标签通过 path 属性绑定到对象的各种属性。

- `<form:errors>` 等于 `<span>` 和自动表单对象验证。你将在第 16 章学习更多关于该标签的信息。
- `<form:label>` 指定字段的标签文本，等于 `<label>`。
- `<form:hidden>` 等于 `<input type="hidden">`。
- `<form:input>` 正如你所见，等于 `<input type="text">`。

# 使用表单对象让生活更简单 | 38

- `<form:password>` 通常等同于 `<input type="password">`，并有一个 `showPassword` 属性（默认认为 false），用于指定是否显示密码。当 `showPassword` 为 true 时，此标签实际上等同于 `<input type="text">`。
- `<form:textarea>` 等同于 `<textarea>`。
- `<form:checkbox>` 等同于 `<input type="checkbox">`，并且可以支持多种类型的属性，例如布尔值、Booleans 和数值类型。
- `<form:checkboxes>` 是 `<form:checkbox>` 的变体，它可以自动在你身上创建多个复选框字段。使用 `items` 属性来指定一个集合、Map 或对象数组以生成标签。`itemValue` 和 `itemLabel` 属性分别对应集合中对象的字段名（name）和字段标签（label）属性。
- `<form:radio>` 等于 `<input type="radio">`。你可以将两个或多个此类控件绑定到同一个路径（表单属性），Spring 会根据属性值自动选择一个。
- `<form:radiobuttons>` 之于 `<form:radiobutton>` 就像 `<form:checkboxes>` 之于 `<form:checkbox>`。它具有相同的 `items`、`itemValue` 和 `itemLabel` 属性来帮助生成单选按钮。`<form:radiobuttons>` 和 `<form:checkboxes>` 都非常适合派生字段。
- `<select>` 等同于 `<select>` 下拉列表或多选。它配合 `<form:option>` 和 `<form:options>` 使用。它根据 select 绑定的路径值自动选择正确的选项。
- `<form:option>` 嵌套在 `<form:select>` 内部，等同于 `<option>`。
- `<form:options>` 类似于 `<form:checkboxes>` 和 `<form:radiobuttons>`，具有 `items`、`itemValue` 和 `itemLabel` 属性，用于生成多个 `<option>` 元素。

# 获取提交的表单数据

当用户提交到你的控制器时，从该提交获取数据是非常简单的。`createUser(UserForm)` 和 `editUser(UserForm, long)` 方法都接收由 `FormHttpMessageMessageConverter` 从带注解的请求参数翻译而 Form 对象。

```java
@RequestMapping(value = "user/add", method = RequestMethod.POST)
public View createUser(UserForm form) {
    User user = new User();
    user.setId(this.getNextUserId());
    user.setUsername(form.getUsername());
    user.setName(form.getName());
    this.userDatabase.put(user.getUserId(), user);

    return new RedirectView("/user/list", true, false);
}
```

# 第 13 章 用控制器替换你的 Servlets

现在编译应用程序，从 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/forms/user/list`。点击新链接并输入用户名和名称创建一个新用户。添加一个或多个用户，并尝试编辑它们。你会发现 Spring 自动将你的 `UserForm` 对象绑定到模型（model）以形成视图中的表单字段。在提交时，它会自动将请求参数转换为表单对象。这是一个 Spring MVC 功能，你可以反复使用它，无论是在开发 Spring Framework 应用程序的过程中还是贯穿始终。

# 更新客户支持应用程序

你现在应该查看可以从 wrox.com 下载站点获取的 Customer-Support-v10 项目。该应用程序与本书的第一部分相比发生了巨大变化：它引导了 Spring Framework，将类移出 `com.wrox.site` 包，并将 Servlets 替换为 Spring MVC 控制器。由于空间限制，本书无法重印整个项目。但你应该理解一些关键区别。

# 启用 Multipart 支持

首先，`Configurator` 类已经消失了。该类是一个 `ServletListener`，通过编程方式配置了 `LoggingFilter` 和 `AuthenticationFilter`，以便它们按正确的顺序执行。每当你通过编程方式配置 Servlet API 时，最好在单个类中进行。在本章和上一章中你必须熟悉的 `Bootstrap` 类是用于 `Configurator` 中过滤器进行编程配置的完美位置。在 `Bootstrap` 类中配置的 `DispatcherServlet` 现在已配置了 multipart 支持。客户支持应用程序的 `Bootstrap` 类位于列表 13-1 中。

## Listing 13-1: Bootstrap.java

```java
public class Bootstrap implements WebApplicationInitializer {
    @Override
    public void onStartup(ServletContext container) throws ServletException {
        container.getServletRegistration("default").addMapping("/resource/*");

        AnnotationConfigWebApplicationContext rootContext = 
            new AnnotationConfigWebApplicationContext();
        rootContext.refresh(RootConfiguration.class);

        container.addListener(new ContextLoaderListener(rootContext));

        AnnotationConfigWebApplicationContext servletContext =
            new AnnotationConfigWebApplicationContext();
        servletContext.register(ServletContext.class);
        ServletRegistration.Dynamic dispatcher = container.addServlet(
            "Dispatcher", new DispatcherServlet(servletContext)
        );
        dispatcher.loadOnStartup(1);
        dispatcher.setMultipartConfig(new MultipartConfigElement(
            null, 20_971_520, 41_943_040L, 512_000
        ));
        dispatcher.addMapping("/");

        FilterRegistration.Dynamic registration = container.addFilter(
            "loggingFilter", new LoggingFilter()
        );
        registration.addMappingForUrlPatterns(null, false, "/*");

        registration = container.addFilter(
            "authenticationFilter", new AuthenticationFilter()
        );
        registration.addMappingForUrlPatterns(null, false, "/*");
    }
}
```



仅在 `Dispatcher` 上启用 `multipart` 不足以让文件在 Spring MVC 中工作。回想起在 3.0 之前，Servlet API 并没有内置的 `multipart` 支持。Spring MVC 需要一个 `MultipartResolver` 实例来创建该 bean。

```java
@Bean
public MultipartResolver multipartResolver() {
    return new StandardMultipartResolver();
}
```

# 将 Servlets 转换为 Spring MVC

`index.jsp` 文件已被移除并由 `IndexController` 替换。旧的 `SessionList` 被 `SessionAuthController` 替换。代码本身并没有区别，除了使用了 Spring 控制器代替了 `HttpServletRequest` 和 `HttpServletResponse`。

`LoginServlet` 变成了 `AuthenticationController`。这发生了一些变化。`UserController` 使用了 `ViewController`。Spring 负责处理 `@RequestMapping`。`UserController` 使用表单对象处理工单，该表单使用 Spring 的 `MultipartFile` 来轻松访问上传的文件。

```java
public static class Form {
    private String subject;
    private String body;
    private List<MultipartFile> attachments;
}
```

这使得创建处理程序的代码比之前的 Servlet 代码简洁得多。

```java
@RequestMapping(value = "create", method = RequestMethod.POST)
public View create(HttpSession session, Form form) throws IOException {
    Ticket ticket = new Ticket();
    ticket.setId(ticket.getNextTicketId());
    ticket.setCustomer((String) session.getAttribute("username"));
    ticket.setSubject(form.getSubject());
    ticket.setBody(form.getBody());
    ticket.setCreated(Instant.now());
    for (MultipartFile filePart : form.getAttachments()) {
        log.debug("Processing attachment for new ticket.");
        Attachment attachment = new Attachment();
        attachment.setName(filePart.getOriginalFilename());
        attachment.setMimeType(filePart.getContentType());
        attachment.setContents(filePart.getBytes());
        if ((attachment.getName() != null && attachment.getName().length() > 0) ||
            (attachment.getContent() != null && attachment.getContent().length() > 0)) {
            ticket.addAttachment(attachment);
        }
    }
    this.ticketDatabase.put(ticket, ticket);
    return new RedirectView("/ticket/view/" + ticket.getId(), true, false);
}
```

关于新的启用 Spring 的应用程序，你最后需要了解的是在列表 13-2 中使用了自定义 `com.work.site.DownloadView` 类，用于从 Spring 控制器下载文件。你可以在应用程序的任何地方利用此复用视图，将附加到响应的文件发送回给客户端下载。

# 列表 13-2: DownloadView.java

```java
public class DownloadingView implements FinalView
{
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

这个下载视图被大大简化了，包含一些硬编码的行为。在现实世界中，它可能会有几个设置用于自定义。不过，它能够完成任务，而且 `ViewController` 中的一行代码就能将附件发送到客户端浏览器进行下载。

```java
return new DownloadingView(attachment.getName(), attachment.getMimeType(), attachment.getContent());
```

和通常一样，你可以通过编译项目、从 IDE 启动 Tomcat 并在你喜欢的浏览器中访问 `http://localhost:8080/support/` 来测试重构后的 Customer Support 应用程序。通常的功能包括列出工单、创建工单、图表等。对于用户来说，它看起来大部分相同，但它正向着设计更好的应用程序迈进。

### 总结

本章涵盖了关于 Spring MVC 控制器和请求映射方法的大量信息。你学习了使用 `@RequestMapping` 的无限方式，以及许多其他注解和类型，用于创建强大的控制器方法，这些方法可以处理并响应任何类型的请求。你尝试了 Spring 对模型-视图-控制器（MVC）模式的支持，并设计了 Spring 可以从请求参数自动创建表单对象。最后，你看到了为跨国 Widget 公司重构的 Customer Support 应用程序，它现在使用 Spring 框架和控制器，而不是带有 action 模式的 Servlets。然后你学习了如何创建自己的 Spring View 来将文件下载推送到客户端浏览器。

在下一章中，你将探索服务和存储层如何进一步丰富你的应用程序；它们帮助将不同类型的程序逻辑分离到独立的层中，这些层可以被抽象和模拟以进行独立测试。

# 14

## 使用服务和存储层来支持你的控制器

本章内容

- 什么是 Model-View-Controller 加上 Controller-Service-Repository？
- 使用根应用上下文代替 Web 应用上下文
- 通过异步和定时执行增强服务
- 使用 WebSockets 结合逻辑分离

本章的 WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/projectjavawebbapps` 的 Download Code 标签页找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- 讨论板项目（Discussion-Board Project）
- 客户支持-Support-v11 项目

本章的新 MAVEN 依赖

除了之前章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-websocket</artifactId>
  <version>4.0.2.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

# 第 14 章 使用服务和存储层来支持你的控制器

# 理解 MODEL-VIEW-CONTROLLER 加上 CONTROLLER-SERVICE-REPOSITORY

在第 13 章中，你学习了用于用 Spring MVC 控制器替换 Servlets 的强大工具。你探索了 Spring 框架中实现的模型-视图-控制器 (MVC) 模式。到现在，你可能已经对该模式非常熟悉了，即使你以前从未见过它。然而，你可能已经发现了这种模式的一个问题。尽管它很简单，而且控制器比 Servlets 更简洁，你的控制器仍然可能变得难以维护。为了让你的业务逻辑简单：将提交的数据保存在内存某处。考虑一下在应用程序中创建或编辑数据时需要发生的所有其他事情：

- **验证**：数据需要以某种方式进行验证，以确保在创建时遵循了正确的规则。例如，某些字段可能不是可选的，或者其他字段可能有限制的值。
- **警报**：可能需要通过电子邮件、短信或手机通知发送有关更改的通知。
- **应用程序中的其他现有数据**：这些数据可能需要更改。以在线论坛系统为例，你通常会在每个论坛中看到帖子数以及最后发帖的用户和日期。然后，在论坛内部，每个帖子通常会显示回复数以及每个帖子中回复的用户和日期。为了提高性能，回复的统计数据通常汇总到论坛中，而帖子的统计数据通常汇总到论坛中。因此，在向帖子添加回复时，必须更新论坛数据。
- **数据持久化**：应用程序数据很少保存在内存中。它通常存储在某种类型的数据存储中，例如关系型数据库、NoSQL 数据库或平面文件。持久化这些数据本身涉及到整套逻辑，这种逻辑可能非常复杂并消耗大量资源。

考虑到所有这些，分离这些逻辑真的是最好的吗？考虑图 14-1，它展示了你组件的基本操作。如果你正在创建一个完全符合老板要求的应用程序，你可以复用控制器吗？可能不能。相反，你会发现自己正在对代码库进行重大重构，将用户界面逻辑与业务逻辑分离来。

# 理解 MODEL-VIEW-CONTROLLER 加上 CONTROLLER-SERVICE-REPOSITORY

![](img/4677f981a0e1067137bb55a12f849d_426_0.png)

# 1 识别不同类型的程序逻辑

用户界面逻辑是仅为支持特定界面而存在的逻辑。如果一段代码逻辑无论用户如何与应用程序交互都是需要的，那么这段逻辑就是业务逻辑。如果这段代码逻辑仅针对特定界面需要，它就是用户界面逻辑。在理想的应用程序中，你希望将这些类型的逻辑分离到不同的层中。通过这样做，你可以轻松地更换界面，甚至更好，同时利用多个界面，而无需更改任何业务逻辑。你还可以编写一个处理你业务逻辑的库，并在各种 Web 和桌面应用程序中使用该库。

当持久化到某种类型的数据存储时，有大量的逻辑致力于该数据的持久化，且与业务逻辑无关。持久化逻辑可以通过其在底层数据存储发生变化时的无用性识别。例如，当从 MySQL 切换到 PostgreSQL 或 NoSQL 数据库时，某些代码可能仍然必要，但当你切换到内存数据存储时它不再需要，那么它就是持久化逻辑。正如将用户界面逻辑与业务逻辑分离一样，你也将持久化逻辑与业务逻辑分离。这样做具有两个明显的优势：

- 如果你以后决定切换用于持久化数据的数据存储，你可以这样做而无需更改业务逻辑。
- 测试你的业务逻辑将变得简单得多，因为你可以模拟持久化逻辑，并仅隔离业务逻辑进行测试。

## 仓库提供持久化逻辑

在 Controller-Service-Repository（控制器-服务-仓库）模式中，仓库（repositories）是最低层，负责所有与将数据保存到数据存储以及从数据存储中检索已存数据的逻辑。你使用 `@Repository` 注解标记仓库以标明其用途。通过组件扫描（component scanning），`@Repository` 会在它们所属的 Spring 上文中被自动实例化、注入和管理。每个仓库负责单一的持久化对象或实体（entity）。这把仓库层拆分为更小的、易于测试的代码单元，如果你决定某个特定实体属于不同的存储器，你可以一次替换一个实体。

仓库是通过接口创建的。

# 服务提供业务逻辑

服务（Services）是仓库之后的下一层。服务封装了应用程序的业务逻辑并消耗其他服务，但不会消耗较高应用层（如控制器）的资源，尽管 Spring 并没有强制执行此规定。服务用 `@Service` 注解标记，使其具备自动实例化和依赖注入等能力。与仓库一样，服务也是通过接口创建的，以便依赖资源针对接口进行编程。这种基于接口集的分层模式允许每一层在与其他所有层隔离的情况下进行独立测试。从事务的角度来看，从高层（如控制器）执行的服务方法可以被视为一个事务性的工作单元（unit of work）。它可能在上下文中对多个仓库和其他服务执行操作，且所有操作要么作为一个整体成功，要么作为一个整体失败。当一个服务从另一个服务被执行时，通常认为它与调用它的方法属于同一个工作单元。

需要注意的是，这种“工作单元”的概念并不意味着它总能用传统的关系型数据库事务来处理。工作单元期间执行的操作可能在不同的数据存储或文件媒体上产生多个后果。这些操作可能包括应用内或应用间消息的传输、电子邮件、短信或手机通知，这些在大多数情况下是无法回滚的。维护这种逻辑工作单元的原子性超出了本书的范围，必须根据具体情况进行处理。简单来说，在处理符合 ACID 标准的数据存储的简单应用程序中，工作单元大致等同于数据库事务。Spring 为这些事务需求提供了支持，你将在本书的第三部分探索这些内容。

一些开发者不喜欢使用“服务”一词来描述应用的这一层，因为这有时会与 Web（网络）混淆。你如何命名你的逻辑层并不重要。你甚至不必使用 `@Service` 注解。你可以使用 `@Component` 注解，或者带有 `@Component` 元注解的自定义注解。你如何称呼它以及如何标记它都不会改变它的用途。然而，本书的其余部分将它们称为服务。

# 控制器提供用户界面逻辑

你已经对控制器（controllers）、`@Controller`、`@RequestMapping` 以及它们在 Spring MVC 中如何协同工作的概念非常熟悉。控制器是 Controller-Service-Repository 模式中食物链的顶端。事实上，这个三层系统可以很容易地比作自然界的食物链。在这个系统中，仓库是植物，从自然（数据库）中吸收养分；服务是杂食动物，消耗仓库（植物）或其他服务（杂食动物）。继续这个类比，控制器是肉食动物，从不直接消耗仓库（植物），也从消耗其他控制器。控制器以某种形式控制用户界面，并在服务的帮助下为视图（view）展示准备模型。

在 MVC 范式中，服务和仓库被认为是控制器的一部分（但不是 `@Controller` 本身）。这如图 14-2 所示。一个 `@Controller`、它依赖的 `@Services`、它依赖的 `@Repositories` 以及位于这些组件之间的任何缓存层共同构成了模型-视图-控制器（MVC）模式中的控制器。所有这些组件都以某种形式使用模型。最终，`@Controller`（可以是用于 Web GUI 或 Web 服务 API）将模型的必要部分传递给视图进行渲染。这可能是一个 JSP（用于 Web GUI），也可以是一个 JSON 或 XML 渲染引擎（用于 Web GUI 或 Web 服务 API）。

![](img/4677f981a0e1067137bb55a122f8498d_428_0.png)

图 14-2

# 使用根应用上下文而非 Web 应用上下文

想想你在过去两个章节中已经熟悉的 `ServletContextConfiguration` 类。当然，你可以将其命名为任何你喜欢的名称，但它的用途保持不变。作为 `DispatcherServlet` 的 Spring 应用上下文的配置，该类负责建立 Spring 在 Servlet 容器中接收 HTTP 请求时的运行方式。这一描述立即限制了该配置的范围。



## ServletContextConfiguration 的局限性

在 Servlet 之外，`ServletContextConfiguration` 没有任何用处。配置的内容反映了这一点。该类中配置的每个 bean 某种程度上是为了接受和响应 HTTP 请求的。如果你为应用程序创建一个 RESTful 或 SOAP 服务，你可能会创建一个独立的 `DispatcherServlet`，它有自己的应用上下文和 `@Configuration`，且该配置将与此上下文中控制器处理请求的方式不同。你可能会禁用不必要的 bean，例如 `ByteArrayConverter`、`StringHttpMessageConverter` 和 `FormHttpMessageConverter`，因为它们对于 RESTful 或 SOAP 服务是不需要的。你不需要 `ViewResolver` 和 `RequestTranslator` 等。

## 为多个用户界面复用根应用上下文

根据前面的讨论，请记住你不同的用户界面通常共享相同的服务。这样，你的业务逻辑在所有用户界面中就能保持一致。为了实现这一点，你不应该在 Web 应用上下文中管理和服务仓库，而应该放在作为所有 Web 应用上下文父级的根应用上下文中管理。所有的服务和仓库都被控制各种用户界面的 Web 应用继承。如果你在某时刻想使用 Web 服务的服务仓库创建一个桌面应用程序，可以使用根应用上下文配置（该配置已经通过不同的机制启动）。

你已经在第 12 章中花费了大量时间学习应用上下文的层级结构和继承、使用 Web 应用上下文（`ServletContextConfiguration`）配置根上下文（`RootContextConfiguration`），以及修改组件扫描以在每个上下文中扫描正确的组件。组件扫描是这种分离的关键。如果你使用组件扫描，必须对其进行正确配置。否则，你可能会重复 bean 定义，更糟糕的是 bean 定义可能没有被拾取。组件扫描基于两个原理：包扫描和类过滤。

使用 `@ComponentScan` 注解时，你通过 `String[] basePackages` 属性告诉要扫描哪些 Java 包以查找候选类。Spring 会定位所有属于这些包或子包的类，并为每个类分配资源。`basePackages` 属性的缺点是不是类型安全的，因此拼写错误很容易被忽略。另一种方案是，你可以使用 `Class[] baseClasses` 属性。

## 将业务逻辑从 Controller 移动到 Service

在理想的世界里，每个人都能使用最好的工具和最佳实践从零开始编写每个程序。但在现实中，你通常需要处理那些没有使用良好工具或实践的遗留应用程序。你不仅必须维护这些应用程序并解决用户报告的问题，还必须为它们添加新功能，而添加这些新功能需要重构代码以支持你的业务需求。

考虑一个简单的讨论板，以及它可能需要的业务逻辑。假设你没有类别或其他方式对讨论进行分类或分组，你的用户需要创建讨论和回复讨论的能力。在创建讨论时，你应该确保其逻辑和正文不为空。在回复讨论时，你不仅要检查回复是否为空，还要检查该回复是否针对一个实际上存在的讨论。讨论和回复都需要时间戳，但这个时间戳是自动生成的或由用户提供的，因此它是业务逻辑。在这个假设的场景中，你有一个应用程序，`BoardController` 允许查看和创建讨论，而 `DiscussionController` 包含了应用程序的所有代码库（配置和视图除外）。它们管理界面逻辑，执行业务逻辑，并将讨论和回复持久化到数据库中。

现在，你的老板分配了新任务：

- 用户在发布或回复时必须接收电子邮件提醒。
- 用户还能够以 RSS 馈送的形式查看讨论板和讨论。
- 服务器管理员希望自动删除一年前发布或回复过的话题，以节省存储空间并提高性能。

考虑一下为了支持这些新功能你需要做的所有更改。每个讨论都需要一个回复过该讨论的用户列表，以便于发送通知。正如通常一样，用户最终会取消订阅讨论，因此将此信息保留在讨论中，比每次都从回复中聚合它要简单得多且成本更低。此外，每个讨论都需要一个日期字段，表示回复的时间或在没有回复时发布的时间。但在这些更改中，其中一个产生了一个问题，因为这些对回复发布时间的更新是从 `DiscussionController` 触发的，但 `BoardController` 包含了保存讨论记录的逻辑。此外，你还有从数据库中检索讨论和回复并返回 JSP 视图的方法。你需要执行相同操作但返回 RSS 视图的新方法。这看起来像是代码重复。

在执行任何一个这些任务之前，将你的业务逻辑与界面逻辑分离离开不应该花费长时间。你将在本节 wrox.com 上的项目剩余部分中看到这一点。为了形象了解你的用户需要什么样的接口，请查看 `BoardController` 和 `DiscussionController` 的请求处理程序。现在不要担心代码。只需考虑接口。`BoardController` 包含了列出和创建讨论的方法。

```java
@Controller
@RequestMapping("discussion")
public class BoardController {
    @RequestMapping(value = "list", method = RequestMethod.GET)
    public String listDiscussions(Map<String, Object> model) { ... }

    @RequestMapping(value = "create", method = RequestMethod.GET)
    public String create(Map<String, Object> model) { ... }

    @RequestMapping(value = "create", method = RequestMethod.POST)
    public View createDiscussion(Discussion form) { ... }
}
```

同时，`DiscussionController` 包含了查看讨论和回复讨论的方法。

```java
@Controller
@RequestMapping("discussion/{discussionId}")
public class DiscussionController {
    @RequestMapping(value = "", method = RequestMethod.GET)
    public String viewDiscussion(Map<String, Object> model,
        @PathVariable("discussionId") long id) { ... }

    @RequestMapping(value = "reply", method = RequestMethod.POST)
    public ModelAndView reply(ReplyForm form,
        @PathVariable("discussionId") long id) { ... }
}
```

考虑你支持这些功能所需的 POJO。为了简单起见，假设用户用 String 代替对象。我们需要一个 `Discussion` 对象和一个 `Reply` 对象来持久化数据。

```java
public class Discussion {
    private long id;
    private String user;
    private String subject;
    private String uriSafe;
    private String message;
    private Instant created;
    private Instant lastUpdated;
    private Set<String> subscribedUsers = new HashSet<>();

    // mutators and accessors
}
```

```java
public class Reply {
    private long id;
    private long discussionId;
    private String user;
    private String message;
    private Instant created;

    // mutators and accessors
}
```

根据你对控制器的了解，`DiscussionService` 和 `ReplyService` 接口应该是非常简单的。注意 `ReplyService` 没有任何通过 ID 获取单个回复的方法。现在没有这种业务需求。如果你需要添加编辑回复的能力，那么你就需要添加此方法。

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

现在你的服务实现并不重要。你已经可以重构你的控制器来使用服务的接口。如果你查看 `BoardController` 的代码，你可以看到它是多简单。它的方法只包含与用户交互所需的代码。特别是 `createDiscussion`，它没有设置 `Discussion` 的所有属性。它只使用用户提供的属性，不需要知道这是如何实现的。

```java
@Inject DiscussionService;
@Inject ReplyService replyService;

@RequestMapping(value = "list", method = RequestMethod.GET)
public String listDiscussions(Map<String, Object> model) {
    model.put("discussions", this.discussionService.getAllDiscussions());
    return "discussion/list";
}

@RequestMapping(value = "create", method = RequestMethod.GET)
public String create(Map<String, Object> model) {
    model.put("discussionForm", new DiscussionForm());
    return "discussion/create";
}

@RequestMapping(value = "create", method = RequestMethod.POST)
public View createDiscussion(Discussion form) {
    Discussion discussion = new Discussion();
    discussion.setUser(form.getUser());
    discussion.setSubject(form.getSubject());
    discussion.setMessage(form.getMessage());
    this.discussionService.saveDiscussion(discussion);
    return new RedirectView("/discussion/" + discussion.getId() + "/" + discussion.getUriSafe(), true, false);
}
```

`DiscussionController` 的代码同样简单。大部分工作都委托给了 `DiscussionService` 和 `ReplyService`，让控制器只关注界面。

```java
@Inject DiscussionService discussionService;
@Inject ReplyService replyService;

@RequestMapping(value = "{discussionId}", method = RequestMethod.GET)
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
        return new ModelAndView("/discussion/" + id + "/" + discussion.getUriSafe(), true, false);
    }
    return new ModelAndView("discussion/errorNoDiscussion");
}
```

## 用于数据存储的 Repository

当你开始编写 `DiscussionService` 和 `ReplyService` 的实现时，你很快意识到许多必要代码都是用于将数据保存到数据库和从数据库中检索数据的。为了保持服务代码纯粹与业务相关，最好是创建一个仓库层来处理数据持久化。这使得你的服务方法更加简洁且易于测试。`DiscussionRepository` 和 `ReplyRepository` 接口非常简单，出乎意料地镜像了服务层。

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

现在你有了用于持久化的接口，你可以实现服务。`DefaultDiscussionService` 的 `getDiscussion` 方法没有任何业务逻辑（尽管你可能需要它），`getAllDiscussions` 在返回列表之前执行了一些有趣人的任务。`saveDiscussion` 在创建 URL 时对 `subject` 属性进行处理以使其搜索引擎友好。它更新了时间戳。



```java
@Service
public class DefaultDiscussionService implements DiscussionService {
    @Inject DiscussionRepository discussionRepository;

    @Override
    public List<Discussion> getAllDiscussions() {
        List<Discussion> list = discussionRepository.getAll();
        list.sort((d1, d2) -> d1.getLastUpdated().compareTo(d2.getLastUpdated()));
        return list;
    }

    @Override
    public Discussion getDiscussion(long id) {
        return discussionRepository.get(id);
    }

    @Override
    public void saveDiscussion(Discussion discussion) {
        String subject = discussion.getSubject();
        subject = Normalizer.normalize(subject, Normalizer.Form.NFD)
            .replaceAll("\\p{InDiacritical}+", "")
            .replaceAll("[^\\p{Alnum}]", "*");

        Instant now = Instant.now();
        discussion.setLastUpdated(now);

        if (discussion.getId() < 1) {
            discussion.setCreated(now);
            discussion.setSubscribedUsers(discussion.getUser());
            discussionRepository.add(discussion);
        } else {
            discussionRepository.update(discussion);
        }
    }
}
```

> 注意：`getAllDiscussions` 方法展示了 Java 8 lambda 表达式的力量，在某些情况下，在 Java 代码中进行排序比在数据库本身更高效。

`DefaultReplyService` 的 `getForDiscussion` 方法同样在返回列表之前对列表进行了排序。`saveReply` 同时使用了仓库和 `DiscussionService`（注意这里使用的是接口而不是实现）来执行某些任务。如果回复是新的，它会将回复关联到讨论并设置创建时间；如果不是，它会更新回复。无论哪种方式，`DiscussionService` 都确保了业务规则被遵循。

```java
@Service
public class DefaultReplyService implements ReplyService {
    @Inject ReplyRepository replyRepository;
    @Inject DiscussionService discussionService;

    @Override
    public List<Reply> getForDiscussion(long discussionId) {
        List<Reply> list = replyRepository.getForDiscussion(discussionId);
        list.sort((r1, r2) -> r1.getId() < r2.getId() ? -1 : 1);
        return list;
    }

    @Override
    public void saveReply(Reply reply) {
        Discussion discussion = discussionService.getDiscussion(reply.getDiscussionId());
        if (reply.getId() < 1) {
            discussion.getSubscribedUsers().add(reply.getUser());
            reply.setCreated(Instant.now());
            replyRepository.add(reply);
        } else {
            replyRepository.update(reply);
        }
        discussionService.saveDiscussion(discussion);
    }
}
```

现在是测试它了。书中没有足够的空间打印所有的 JSP 视图，但它们都在 `Discussion-Board` 项目中，你可以查看。当你准备好后，编译应用并在你的 IDE 中启动 Tomcat；然后访问 `http://localhost:8080/board/`。尝试创建并回复各种讨论。当你对代码运行感到满意时，回过，想象一下如果你把所有这些代码放在控制器中，代码会变得多糟糕——测试和扩展它又变得多困难。

由于你可以重用服务调用，创建用户请求的 RSS 视图的任务突然变得简单多了。这本书没有涵盖那个特定任务，但尽管自己尝试吧！

# 通过异步和调度执行改进服务

执行器负责记住任务应该何时执行，并按时执行它们（使用执行器）。

- `java.util.concurrent.Executor` 接口定义了一个可以执行简单 `Runnable` 的执行器。
- Spring 通过 `org.springframework.core.task.TaskExecutor` 扩展了此接口。
- Spring 还提供了 `org.springframework.scheduling.TaskScheduler` 接口，它指定了几个方法，用于调度任务在未来的某个点运行一次或多次。

这些 Spring 接口有许多实现，其中最常见的实现是 `org.springframework.scheduling.concurrent.ThreadPoolTaskScheduler`，它提供了一个执行器和一个调度器（由执行器支持），以及用于调度任务的线程池，以确保线程以有序高效的方式运行。当应用程序关闭时，该类会确保线程被正确关闭，以防止内存泄漏和其他问题。

该类还实现了 `java.util.concurrent.ThreadFactory` 接口。因此，你可以定义一个 `ThreadPoolTaskScheduler` Bean，它满足了你对 `Executor`、`TaskExecutor`、`TaskScheduler` 或 `ThreadFactory` 的所有依赖。当你需要配置异步和调度方法执行时，这会非常有用。

# 配置调度器和异步支持

若要在 `@Async` 方法上启用异步方法执行，请在你的 `@Configuration` 类上标记 `@EnableAsync`。同样，要在 `@Scheduled` 方法上启用调度方法执行，请使用 `@EnableScheduling` 注解。你希望将这些注解放在 `RootContextConfiguration` 上。然而，`@EnableAsync` 和 `@EnableScheduling` 本身建立了默认的异步和调度配置。要自定义此行为，你需要实现 `AsyncConfigurer` 接口返回正确的异步执行器，并实现 `SchedulingConfigurer` 接口将正确的执行器分配给调度器。

```java
@Configuration
@EnableAsync(proxyTargetClass = true)
@EnableScheduling
public class RootContextConfiguration implements AsyncConfigurer, SchedulingConfigurer {
    private static final Logger logger = LogManager.getLogger();
    private static final Logger schedulingLogger = LogManager.getLogger(logger.getName() + ".[scheduling]");

    @Bean
    public ThreadPoolTaskScheduler taskScheduler() {
        logger.info("Setting up thread task scheduler with 20 threads.");

        ThreadPoolTaskScheduler scheduler = new ThreadPoolTaskScheduler();
        scheduler.setPoolSize(20);
        scheduler.setThreadNamePrefix("task-");
        scheduler.setAwaitTerminationSeconds(60);
        scheduler.setWaitForTasksToCompleteOnShutdown(true);
        scheduler.setErrorHandler(t -> schedulingLogger.error("Unknown error occurred while executing task.", t));
        scheduler.setRejectedExecutionHandler((r, e) -> schedulingLogger.error("Execution of task {} was rejected for unknown reasons.", r, e));
        return scheduler;
    }
}
```

这里仅显示了类的部分；隐藏了已有的部分。`@EnableAsync` 注解中的 `proxyTargetClass` 属性告诉 Spring 使用 CGLIB 库来代理类，而不是 Java 接口代理。这允许你在 Bean 上拥有那些未在接口中指定的异步或调度方法。如果你将此属性设置为 `false`，则只有在接口中指定的方法可以按计划执行或异步执行。`@Bean` 方法暴露了 `AsyncConfigurer` 中指定的执行器，告诉 Spring 使用相同的调度器进行异步方法执行，而 `configureTasks` 方法（在 `SchedulingConfigurer` 中指定）告诉 Spring 使用相同的调度器进行调度方法执行。

你会立刻好奇这是如何工作的。`getAsyncExecutor` 和 `configureTasks` 都调用了 `taskScheduler`，难道不是实例化了两个 `TaskScheduler` 吗？实际上，只实例化了一个 `TaskScheduler`。Spring 代理调用所有 `@Bean` 方法，因此它们不会被调用超过一次。`@Bean` 方法的第一次调用结果会被缓存并用于后续调用。这允许你配置中的多个方法使用其他 `@Bean` 方法。由于此原因，在此配置中只实例化了一个 `TaskScheduler`，该实例被用于 Bean 定义、`getAsyncExecutor` 方法以及 `configureTasks` 方法。当你执行后两个方法时，这些方法中的日志语句将证明这一点。

# 创建和使用 @Async 方法

Spring Framework 通过将影响的 Bean 包装在代理中提供对 `@Async` 方法的支持。当 Spring 在依赖它的其他 Bean 中注入带有 `@Async` 方法的 Bean 时，它实际上注入的是代理而不是 Bean 本身。这些 Bean 然后调用代理上的方法。对于普通方法，代理直接委托给底层方法。对于标记了 `@Async` 或 `javax.ejb.Asynchronous` 的方法，代理指示执行器执行该方法并立即返回。这种工作方式导致了一个重要的后果：如果一个 Bean 可以调用它自己的一个 `@Async` 方法，该方法将不会异步执行——这一点无法证明。由于此原因，如果你想异步调用一个方法，它必须在另一个对象上。（而且，该对象必须是 Spring 管理的 Bean。）

> 注意：这并不完全正确。对于基于 Java 接口的代理，你无法对此进行代理。对于 CGLIB 代理，你可以通过重写原始类中的方法来实现代理。这就是配置 `@Bean` 缓存的工作原理——Spring 允许使用 CGLIB 代理 `@Configuration` 类。由于你在这里启用了 CGLIB 代理，你可以在同一个类上调用 `@Async` 方法，它们将以异步执行。然而，你不应该依赖这一点——配置的变化可能会破坏它。

Discussion-Board 项目中的 `NotificationService` 和 `FakeNotificationService` 演示了这是如何工作的。注意该方法在接口和实现类上都标记了 `@Async`。这并不是严格要求的。然而，当意图是让所有实现都异步执行时，对接口进行标记被认为是礼貌的，这样消费者就能意识到这一点。

```java
public interface NotificationService {
    @Async
    void sendNotification(String subject, String message, Collection<String> recipients);
}

@Service
public class FakeNotificationService implements NotificationService {
    private static final Logger log = LogManager.getLogger();

    @Override
    @Async
    public void sendNotification(String subject, String message, Collection<String> recipients) {
        log.info("Started notifying recipients {}.", recipients);
        try {
            Thread.sleep(5000L);
        } catch (InterruptedException exception) {
            log.info("Finished notifying recipients.");
        }
    }
}
```

`DefaultReplyService` 获取一个 `@Inject` 的 `NotificationService`，并通过几行简单的代码，在回复是新的情况下，调用 `saveReply` 中的异步方法。

```java
Set<String> recipients = new HashSet<>(discussion.getSubscribedUsers());
recipients.remove(reply.getUser()); // 不需要给回复者发邮件
this.notificationService.sendNotification(
    "Someone replied to " + discussion.getSubject(),
    recipients
);
```

# 创建和 @Scheduled 方法

创建 `@Scheduled` 方法与 `@Async` 方法没有区别。你所做的就是写一个你需要的方法并对其进行标记。关于 `@Scheduled` 方法唯一需要注意的事是，它们不能有任何参数。（Spring 如何知道使用什么参数？）仅仅因为方法是 `@Scheduled` 并不意味着你不能手动调用它。你可以随时调用它，尽管你不必这样做。事实上，你可以对 `@Scheduled` 方法标记 `@Async`，以便它在手动执行时以异步执行。

你在 Discussion-Board 项目中需要的调度执行删除一年前或更久以前发布的删除，以最近的为准。这需要对仓库进行一些调整以支持删除。在 `ReplyRepository` 及其实现中，你现在需要一个 `deleteForDiscussion` 方法。

```java
@Override
public void deleteForDiscussion(long id) {
    this.database.entrySet().remove(e -> e.getValue().getDiscussionId() == id);
}
```

`DiscussionRepository` 及其实现也需要一个 `delete` 方法。然而，删除需要级联到回复，此类需要一个 `@Inject` 的 `ReplyRepository`。

```java
@Override
public void delete(long id) {
    this.replyRepository.deleteForDiscussion(id);
}
```



```java
@Scheduled(fixedDelay = 15000, initialDelay = 15000)
public void deleteOldDiscussions()
{
    Instant oneYearAgo = Instant.now().minus(365, ChronoUnit.DAYS);
    log.info("Deleting discussions stale since %s", oneYearAgo);

    List<Discussion> list = this.discussionRepository.getAll();
    list.removeIf(d -> d.getLastUpdated().isAfter(oneYearAgo));

    for (Discussion old : list) {
        this.discussionRepository.delete(old.getId());
    }
}
```

该方法在 Spring 启动 15 秒后开始执行，并在上一次调用结束与下次调用开始之间间隔 15 秒再次执行。你可以以多种方式使用 `@Scheduled` 来控制方法的执行时间。注意，`deleteStaleDiscussions` 并不是 `DiscussionService` 的一部分，但该方法仍然按计划执行，因为 `EnableAsync` 的 `proxyTargetClass` 属性被设置为 `true`。（当然，在现实世界中，该方法的执行频率会较低，例如每天执行一次。）

现在你已经创建并配置了异步和定时方法，编译应用程序，从 IDE 启动 Tomcat，并访问 `http://localhost:8080/board/`。观察日志你会发现 `TaskScheduler` 仅实例化了一次，且定时方法每 15 秒执行一次。创建讨论和回复，你可以看到异步通知方法正在向日志写入内容。方法期间的 5 秒睡眠证明了它是以异步方式执行的，因为正如你所看到的，当你发布回复时，服务器的响应时间少于 5 秒。

## 对 WebSocket 逻辑层分离

如果你查看 wrox.com 代码网站上的 Customer-Support-v11 项目，你会发现其业务逻辑也移动到了服务（services）中，让控制器只负责用户界面逻辑。

- `InMemoryUserRepository` 实现了 `UserRepository`，将所有用户存储在内存中。
- `TemporaryAuthenticationService` 实现了 `AuthenticationService`，使用了 `UserRepository` 接口。
- `AuthenticationController` 现在使用 `AuthenticationService` 接口来执行业务逻辑。
- 同样，我们使用了 `InMemoryTicketRepository`、使用 `TicketRepository` 接口的 `DefaultTicketService`，而 `TicketController` 现在使用 `TicketService` 接口。

身份验证代码现在使用了 `java.security.Principal` 接口，`AuthenticationFilter` 封装了底层连接以建立 `Principal` 作为查询会话属性的快捷替代方案。你现在可以在这里看到这一点，查看 `TicketController` 上处理 POST 的 `create` 方法。它现在接受 `Principal` 而不是 `HttpSession` 作为第一个参数，而 Spring 知道如何提供该值。

## 向 Spring 应用程序上下文添加容器管理的对象

另一个变化是，以前的 `SessionRegistry` 类现在是一个包含实例方法的接口，而 `DefaultSessionRegistry` 实现了它。这对于 `SessionListControl` 是有效的，但此时你应该意识到 `SessionListener` 导致了问题。`SessionListener` 是由 Servlet 容器实例化和管理的，而不是 Spring 框架。这就是为什么 `SessionRegistry` 以前是一个静态方法的类。那么 `SessionListener` 如何获取 `SessionRegistry` Bean 实例呢？

你实际上有几种选择。一种是使用字节码注入和面向切面编程（AOP），在运行时非常自动化。你只需要对非 Spring 管理的类标上 `@org.springframework.beans.factory.annotation.Configurable` 注解，如果你希望它们在实例化时自动成为 Spring Bean。然而，实现此操作所需的配置相当复杂，如果不解释其工作原理就剥夺你所有的“魔法”将是不公平的。

或者，你可以在运行时通过程序将现有对象添加到 Spring 应用程序上下文。你首先需要移除 `SessionListener` 中的 `@WebListener` 注解，因为使用该注解时监听器的调用顺序是不可预测的。相反，在 `Bootstrap` 类中通过程序配置监听器，以确保它在 Spring 的 `ContextLoader` 之后被调用。

```java
container.addListener(new ContextLoaderListener(rootContext));
container.addListener(SessionListener.class);
...
```

现在，你需要注册 `SessionListener` 以使其实现 `ServletContextListener`。这样 `SessionListener` 会在容器启动时（在 Spring 启动之后）自初始化。

```java
public class SessionListener
implements HttpSessionListener, HttpSessionIdListener,
    ServletContextListener
{
    ...
}
```

你可以使用监听器中的 `contextInitialized` 方法从 `ServletContext` 获取根应用上下文，从应用上下文检索 Bean 工厂，并将 `SessionListener` 配置为根应用上下文中的 Bean。

```java
@Override
public void contextInitialized(ServletContextEvent event) {
    WebApplicationContext context = WebApplicationUtils.getRequiredWebApplicationContext(event.getServletContext());
    AutowireCapableBeanFactory factory = context.getAutowireCapableBeanFactory();
    factory.autowireBeanProperties(this, AutowireCapableBeanFactory.AUTOWIRE_BY_TYPE, true);
    factory.initializeBean(this, "sessionListener", "AUTOWIRE_BY_NAME");
    log.info("Session listener initialized in Spring application context.");
}
```

当 `contextInitialized` 方法执行完毕后，`SessionRegistry` 的实现会被注入，`SessionListener` 即可立即开始使用它。

## 对 WebSockets 应用逻辑层分离

> **警告**：监听器可能具备接线或其他特性，但它并不是一个完整的 Spring Bean。其他 Bean 无法通过 `@Autowired` 或 `@Injected` 注入该监听器，且调用 `ApplicationContext` 的 `getBean` 方法也不会返回该监听器。这是因为监听器从未被放入应用上下文的 Bean 注册表中。你可以通过调用 Bean 工厂的 `registerSingleton` 方法部分解决这个问题，但某些服务仍然无法工作，例如定时方法执行以及构造后/销毁前的回调方法。

## 使用 Spring WebSocket Configurator

正如你可能已经意识到的，WebSocket 服务器端点也是容器管理的对象。因此，你可以使用用于 `SessionListener` 的相同技术来接线你的 WebSocket 端点。你可能会疑惑为什么 Spring 没有提供等于控制器的替代方案来替换 WebSocket 端点。这个问题的答案是：控制器无法作为已经处理底层连接细节的 Servlet 的灵活替代方案。Java WebSocket API 已经在这方面做得很好，Spring 没有必要替换它。然而，为了避免每次实例化时都通过程序注册服务器端点（即每当每个连接获取一个新端点时），Spring 通过 `org.springframework.web.server.endpoint.SpringConfigurator` 为服务器端点提供了原生支持。

`SpringConfigurator` 扩展了 `javax.websocket.server.ServerEndpointConfigurator`，以确保你的端点在调用任何事件或消息处理方法之前已正确初始化。通常，你应该使用 `SpringConfigurator` 声明你的端点，如下例：

```java
@ServerEndpoint(value="${session}", configurator=SpringConfigurator.class)
```

然而，`ChatEndpoint.ServerEndpointConfigurator` 无法将 `HttpSession` 暴露为用户属性，而 `ChatEndpoint` 使用了这个自定义配置器。因此，你只需要将自定义配置器改为 `SpringConfigurator` 而不是 `ServerEndpointConfig.Configurator` 即可。

```java
public static class ChatEndpointConfigurator extends SpringConfigurator {
    @Override
    public void modifyHandshake(ServerEndpointConfig config, HandshakeRequest request, HandshakeResponse response) { ... }
}
```

如此。通过这个简单的更改，你的端点就可以拥有 `@Autowired` 属性并实现任何“魔法” Spring 接口（如 `Aware` 接口），就像一个原生 Bean 一样。然而，对于监听器，端点从未被放入单例 Bean 注册表，这意味着其他 Bean 无法访问它，且它不支持销毁前的生命周期通知或定时方法执行（尽管构造后方法可以工作）。如果你想让端点位于 Bean 注册表中并能够获得这些服务，

### 412 | 第 14 章 使用服务和仓库支持你的控制器

你可以在根应用上下文配置中声明端点的单例实例，如下：

```java
@Bean
public ChatEndpoint chatEndpoint()
{
    return new ChatEndpoint();
}
```

当你这样做时，在 `@ServerEndpoint` 注解中指定的 `SpringConfigurator`（或其扩展类）将不再为每个 WebSocket 连接返回新实例。相反，它会返回该单例实例来处理多个连接，就像 Servlet 或控制器一样。这需要仔细的协调，因为如果你这样做，它将无法再将 `Session`、`HttpSession`、`ChatSession`、`Principal` 以及其他对象作为实例变量——这些对象需要在每次调用方法时进行查找。那么，使用单例 `ChatBean` 的好处是什么？首先，它消耗的内存更少，当你有许多 WebSocket 连接时尤其是。此外，建立连接的时间更短，因为 Spring 只注入依赖项，而不是为每个连接注入。在 Customer-Support-v1 应用中，端点并不是这样配置的，而是遵循了每个 WebSocket 连接一个实例的传统模型。将其重构为单例对读者来说是一个较简单的练习。

## 记住：WebSocket 只是业务逻辑的另一个接口

起初，在 WebSocket 端点中将业务逻辑与用户界面分离似乎非常困难。在某些方面，它非常像控制器，并且可以像控制器响应传入的 HTTP 请求一样对每个传入的消息做出反应。承认的是，服务器端点可以在接收消息之前向客户端发送消息（控制器无法做到的），这让事情变得复杂。这里的界限变得模糊。没有人能告诉你如何划分界限；只有你和你的组织可以做出此决定。然而，重要的是，无论你如何看待，WebSocket 连接都只是某个业务逻辑单元的另一个接口。服务可以从业务和用户界面的纠缠中提取出来。

回想之前的 `ChatEndpoint` 版本还实现了 `HttpSessionListener`，以接收注销或聊天期间会话变化的通知。当时的情况是，如果用户在聊的另一个窗口中注销了，出于安全考虑，聊天将结束。

实现 `HttpSessionListener` 是一个混乱的解决方案，因为容器创建了 `ChatEndpoint` 的单例实例，该实例并没有实际处理连接，并且大量的静态字段来维护 `ChatEndpoint` 之间 `Session` 到 `HttpSession` 链接实例的信息。幸运的是，现在有更清晰的方法来实现它。

```java
void registerOnRemoveCallback(Consumer<HttpSession> callback);
void deregisterOnRemoveCallback(Consumer<HttpSession> callback);
```

`ChatEndpoint` 有一个 `@Injected` 的 `SessionRegistry`，并在其 `@PostConstruct` 方法中注册了回调。注意，回调是使用 Java 8 方法引用（`this::httpSessionRemoved`）注册和注销的，这使得代码变得显著得多。

```java
private final Consumer<HttpSession> callback = this::httpSessionRemoved;

@PostConstruct
public void initialize()
{
    this.sessionRegistry.registerOnRemoveCallback(this.callback);
}

private void httpSessionRemoved(HttpSession httpSession)
{
    if (httpSession == this.httpSession) {
        synchronized(this) {
            if (this.closed) {
                return;
            }
            log.info("Chat session ended abruptly by {} logging out.", this.principal.getName());
            this.close(ChatService.ReasonForLeaving.LOGGED_OUT, null);
        }
    }
}

private void close(ChatService.ReasonForLeaving reason, String unexpected)
{
    this.sessionRegistry.deregisterOnRemoveCallback(this.callback);
}
```

这段代码要清晰得多，并且完全消除了对复杂的 `Sessions` 到 `HttpSessions` 以及 `Sessions` 映射的需求。

> **注意**：你可能会奇怪为什么 `ChatEndpoint` 拥有回调实例变量，而不是简单地将 `this::httpSessionRemoved` 传递给 `registerOnRemoveCallback` 和 `deregisterOnRemoveCallback` 方法。方法引用（`this::something`）没有对象标识。正因如此，传递给 `registerOnRemoveCallback` 和 `deregisterOnRemoveCallback` 的引用看起来是不同的实例，导致无法注销回调。使用回调实例变量解决了这个问题。

`ChatEndpoint` 还使用了一个定时调度方法 `sendPing`，用于每隔 25 秒发送一次 ping 消息。浏览器会对 ping 做出响应，这有助于在一段时间内没有其他活动时保持连接活跃。WebSocket 容器不会代表你自动发送 ping，因此完成这一任务取决于你。这将是 Spring Framework 定时调度方法的完美应用。

为了解决这个问题，客户服务使用了一个简单的 lambda 表达式来响应支持代表加入会话的行为。当支持代表加入并调用 `setRepresentative` 方法时，这会触发回调，确保双方都知道对方。



```java
public class ChatSession {
    private Consumer<Session> onRepresentativeJoin;

    public void setRepresentative(Representative representative) {
        this.representative = representative;
        if (this.onRepresentativeJoin != null)
            this.onRepresentativeJoin.accept(representative);
    }

    public void setOnRepresentativeJoin(Consumer<ChatSession> onRepresentativeJoin) {
        this.onRepresentativeJoin = onRepresentativeJoin;
    }
}
```

现在当聊天会话创建时，客户服务使用一个简单的 lambda 表达式来响应支持代表加入会话的行为。（注意：`ChatEndpoint` 的注销逻辑是根据提供的 OCR 片段重构的，以确保逻辑流顺）。

```java
session.getBasicRemote().sendObject(result.createMessage());
} else {
    JoinResult result = this.chatService.joinSession(sessionId,
    this.principal.getName());
    if (result == null) {
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
    session.getBasicRemote().
        sendObject(this.chatSession.getCreationMessage());
    session.getBasicRemote().sendObject(result.getJoinMessage());
    this.otherWs.getBasicRemote().
        sendObject(result.getJoinMessage());
}
```

既然你已经审查了客户支持应用程序并获得了改进的许可，请编译项目、启动 Tomcat，并访问 `http://localhost:8080/support` 进行尝试。创建工单并查看会话列表，它们的工作方式与之前一样，但请在另一个浏览器中尝试支持聊天功能，看看它是如何工作的。

### 总结

在本章中，你探索了如何使用 Controller-Service-Repository（控制器-服务-仓库）实现模型-视图控制器模式。你学习了分离用户界面逻辑、业务逻辑和数据持久化层是非常重要的，以及这种方法如何简化你的代码。简单的代码更容易测试，且通常更稳定，这应该是软件开发中始终追求的目标。你还学习了如何分离这些不同的层，并发现了 Spring 框架通过 `@Controller`、`@Service` 和 `@Repository` 注解向你提供的支持。

在本章的后半部分，你发现了 Spring 提供的强大的异步和定时调度方法执行工具，并使用它们执行某些任务，例如在后台发送电子邮件通知以及定期从数据存储中清除旧数据。最后，你学习了如何初始化非 Spring Bean 以及 Spring 框架对管理 WebSocket 端点的支持。

在下一章中，你将重温一个旧话题——国际化和本地化，并学习 Spring 框架如何让为全球分发准备应用程序的任务变得更加简单。

# 15

使用 Spring 框架实现应用程序国际化 i18n

# 本章内容

- Spring 框架 i18n 的重要性
- 使用 Spring 的国际化和本地化 API
- 配置 Spring 的国际化支持
- 如何对代码进行国际化
- 客户支持应用程序的国际化

# 本章 WROX.COM 代码下载

你可以在 `http://www.wrox.com/projectjavaforwebbaps` 的“Download Code”选项卡找到本章的 wrox.com 代码下载。本章的代码分为以下示例：

- Local-Application Project（本地应用程序项目）
- Customer-MAVEN-Support-v12 项目

# 本章的新依赖

本章没有新的 Maven 依赖。请继续使用之前所有章节引入的 Maven 依赖。

# 为什么你需要 Spring 框架 i18n？

在第 7 章中，你学习了使用 JSTL 国际化和格式标签库（fmt）进行国际化（i18n）和本地化（L10n）。如果你没有读过第 7 章，不需要回去重读；但是，如果你不理解国际化、本地化或格式标签库，应该回去阅读第 7 章中的“使用国际化和格式标签库”部分。该部分为你提供了国际化和本地化原理的基本概述，并向你介绍了如何使用格式标签库来实现这些目标。它涵盖了语言、区域和国家代码、变体、`Locale` 以及时区，这些你必须理解，才能有效使用 Spring 框架的国际化支持。本章使用了许多这些概念和技术，但不再重复涵盖。

在本章中，你将探索 Spring 框架的国际化和本地化设施，以及使用它们比直接使用容器设施要简单得多。你将理解消息源（message sources）和更多的 Spring JSP 标签，并最终对客户支持应用程序进行国际化和本地化。

# 让国际化变得简单

你可能对国际化和格式标签库得出的结论之一是它并不是最容易使用的。首先，你必须在部署描述符中配置资源包（resource bundles），或者在 `ServletContainerInitializer` 或 `ServletContainerListener` 中使用 `java.servlet.jsp.jstl.fmt.localization` 上下文配置。尽管你可能想从其他地方（例如数据库或仅仅是文件）获取它们，但资源包必须是类路径上的类或文件（`WEB-INF/classes`）。

此外，你可能需要实现一种检测用户想要使用的区域的方法。`HttpServletRequest` 确实包含 `getLocale` 方法，它根据 `Accept-Language` HTTP 请求头推导出区域，并在缺少请求头时返回默认的 `Locale`，但这种机制仅在有限的情况下有效。用户必须使用配置了其偏好语言的计算机（并非总是如此，尤其是在公共计算机上），并且浏览器必须支持 `Accept-Language` 请求头（如今很典型，但无法保证）。在确定区域后，你必须使用 `java.servlet.jsp.jstl.core.Config` 类和 `Config.FMT_LOCALE` 常量来配置标签库使用该区域。哦，别忘了从请求中手动更改区域设置，这是不支持自动支持的。

Spring 为所有这些任务提供了简化，让你能够投入更少的工作来支持国际用户。除此，你可以在整个代码中使用 Spring 的 i18n 支持，而不仅仅是 JSP。Spring 的 i18n 支持分级，并在某些情况下，将 i18n 支持封装到了 Java SE 和 EE 平台以及 JSTL 中。在本章中，你将学习所有这些特性以及更多。你还学习了国际化和本地化的概念。

# 直接本地化错误消息

Java SE 和 EE 国际化的缺点之一是对严格依赖字符串作为本地化键。为了确保万无一失，你最终必须查找错误，而最简单的方法是使用字符串。然而，如果异常（Throwables）和验证错误对象可以直接传递给本地化 API，而无需始终在查找本地化消息之前调用方法来确定错误，就会更容易。使用 Spring 框架的 `MessageSourceResolvable` 就可以。你可以将任何实现此接口的对象传递给任何 i18n API，它会自动解析。在“对代码进行国际化”部分，你使用它来采用处理、日志记录和传播异常的可靠模式。在第 16 章中，你将使用它为 Bean 验证实现更多功能。

# 使用基础国际化和本地化 API

在深入进行应用程序的国际化之前，你应该熟悉一些基础类和 API。其中一些是平台类和 API，所以你可能已经熟悉了。其余的是 Spring 的类和 API，你必须理解它们是如何协同工作的。

# 理解资源包和消息格式

与标准标签库一样，Spring 框架 i18n 使用资源包和消息格式。它使用一种称为消息格式的抽象资源来提供更简单的获取本地化消息的 API。实践中，资源包是 `java.util.ResourceBundle` 的实现。`ResourceBundle` 是消息键映射到本地化消息格式的集合。这里需要注意的关键点是，键是消息格式，而不是本身。

当然，消息格式（`java.text.Format`）在存储于数据库或属性文件中看起来非常像本地化字符串。这些消息格式实际上包含各种占位符模板，在运行时用提供的参数值进行替换。如果值的类型指定为日期或时间，它们将根据给定的区域自动格式化。例如，以下都是美国英语本地化的消息格式：

- 路很长且弯曲。
- 农场上有 `{0}` 只猫。
- 有了 `{0,number,percentage}` 的折扣，最终价格是 `{1,number,currency}`。
- 圆周率到七位有效数字为 `{0,number,######}`。
- 我的出生日期：`{0,date,short}`。今天是 `{1,date,long} {1,time}`。
- 我的生日：`{0,date,MMMM-dd}`。今天是 `{1,date,MMMM YYYY} {1,time,hh:mm}`。
- `{0,choice,0#没有猫|1|有 {0,number,integer} 只猫}`。

重要的是，占位符是经过舍入的，并且在使用消息代码时，你按照占位符名称的顺序指定参数，而不是按照占位符在消息中出现的顺序。这是因为占位符在其他语言中可能会以不同的顺序出现。

# 420 | 第 15 章 使用 SPRING FRAMEWORK 实现应用程序国际化 I18N

占位符始终遵循以下语法之一，`#` 是占位符数字，斜体文本表示用户提供的值：

```
{#number}
{#number,integer}
{#number,percent}
{#number, currency}
{#number,custom format as specified in java.text.DecimalFormat}
{#date}
{#date, short}
{#date, medium}
{#date, long}
{#date, full}
{#date,custom format as specified in java.text.SimpleDateFormat}
{#time}
{#time, short}
{#time, medium}
{#time, long}
{#time, full}
{#time,custom format as specified in java.text.SimpleDateFormat}
{#choice,choice format as specified in java.text.ChoiceFormat}
```

数字和时间占位符遵循与 `<fmt:format>` 和 `<fmt:date>` 标签相同的格式规则。这意味着日期和时间占位符不支持 Java 8 的 Date and Time API。遗憾的是，对这些类型的支持尚未计划到 Java 9 SE 版本才发布。

当你使用上下文参数 `java.servlet.jsp.jstl.fmt.localizationContext` 指定资源包时，其值是一个或多个（用逗号分隔的）字符串，代表资源包的基础名（basenames）。随后 JSTL 在使用国际化标签时使用这些基名来定位资源包。当 JSTL 需要定位消息时，它会调用 `getBundle` 方法类并指定基名和区域（`Locale`）。`ResourceBundle` 会构建一个符合以下格式的匹配资源包名称列表：

```
[baseName]_[language]_[script]_[variant]
[baseName]_[language][script]_[region]
[baseName]_[language][script]
[baseName]_[language][region]_[variant]
[baseName]_[language][region]
[baseName]_[language]
```

如果 `Locale` 不包含变体（variant），则列表中的第一个和第四个名称会被省略。如果不包含区域（region），则第二个和第五个名称会被省略，第一个和第四个名称将分别包含脚本和语言变体，用两个下划线分隔（例如 `baseName_en_JAVA`）。如果 `Locale` 不包含脚本（script），则前三个名称会被省略。然后检查列表中是否存在这些名称的资源包。

对于列表中的每个包名，按照之前包名格式列表的优先级进行排序，`ResourceBundle` 首先尝试使用指定的基名加载并实例化一个扩展 `ResourceBundle` 的类，然后返回该类。如果没有找到该类，则：

# 使用基础国际化和本地化 API

`ResourceBundle` 将名称中的任何点 (`.`) 替换为正斜杠 (`/`)，在名称后附加 `.properties`，并在类路径（classpath）上查找该名称的文件，如果存在，则返回该文件的 `PropertyResourceBundle`。在搜索包之后，如果 `ResourceBundle` 没有找到匹配的包，它将使用回退区域（fallback Locale）生成一个新的可能的包列表并再次搜索。如果仍然没有找到匹配的包，它将查找查找与不带限定符的基名匹配的类和文件，如果未找到包，则抛出异常。

当找到并返回 `ResourceBundle` 后，就可以用它将消息代码解析为消息格式字符串。包由标准的 Java 风格消息组成，键使用消息代码，值使用 `MessageFormat`。你可以从这些值字符串中构造 `MessageFormat` 实例。

如果名称在 `java.servlet.jsp.jstl.fmt.localizationContext` 参数中使用属性，你可以看到管理它是多么简单。例如，你可能在类路径上拥有以下文件的标签名称和错误文件：

- `labels_en.properties`
- `labels_US.properties`
- `labels_GB.properties`
- `labels_FR.properties`
- `errors_en.properties`
- `errors_US.properties`
- `errors_GB.properties`
- `errors_FR.properties`

随着推推，每一个都会产生它自己的 `ResourceBundle`。然而，如果你想将消息存储在数据库中，你需要为每个支持的区域编写一个不同的类，大多数类执行本质上相同的逻辑（从数据库中选择值），或者你必须实现自己的系统来解析 `ResourceBundle` 实例。（即使如此，你仍然需要为每个支持的区域准备一个单独实例。）因为给定的 `ResourceBundle` 实例只能支持一个 `Locale`。检查 `ResourceBundle` 的 API 文档确认，实际上解析消息的方法不包含 `Locale` 参数。你应该

# 消息源来救急

`MessageSource` 为 `ResourceBundle` 提供了一种抽象。`MessageSource` 扩展了 `ResourceBundle` 并向底层 `MessageSource` 暴露 `ResourceBundle` 方法，将调用委托给特定 `Locale` 的 `ResourceBundle`。

在 Web 应用中直接使用 `MessageSource` API 确实有很多场景。例如，当你发送电子邮件或通知时，你需要本地化这些通知的内容。此外，如果指定了 `Accept-Language` 请求头，某些服务会检索本地化的错误消息。你的大部分本地化都发生在 JSP 中，那么 `MessageSource` 在那里有什么用呢？JSTL 期望的是 `ResourceBundle` 而不是 `MessageSource`。Spring 框架提供了两种 `MessageSource` 的实现：

- `org.springframework.context.support.ResourceBundleMessageSource`
- `org.springframework.context.support.ReloadableResourceBundleMessageSource`

![](img/4677f98a0e10673bb5598d_456.png)

# 42 | 第 15 章 使用 SPRING FRAMEWORK 实现应用程序国际化 I18N



ResourceBundleMessageSource 实际上有一个 ResourceBundles 集合作为支持。它使用 `getBundle` 通过与 ResourceBundle 相同的算法定位包。通过 `getBundle` 发现 ResourceBundles 的缺点是它们会被永久缓存，有时这并不是所需要的。`ReloadableResourceBundleSource` 正如其所示，是可以重新加载的。因为文件可以位于类路径上（如果基名以 `classpath:` 开头），也可以位于相对于上下文根的文件系统中。由于在类路径上加载的文件通常会被缓存，类路径使得 `ReloadableResourceBundleSource` 变得可卸载。使用 MessageSource API 非常简单：

```java
@Inject
MessageSource messageSource;
```

```java
this.messageSource.getMessage("foo.message.key", new Object [] {
    argument1, argument2, argument3
}, user.getLocalLocale());

this.messageSource.getMessage("foo.message.key", new Object [] {
    argument1, argument2, argument3
}, "This is the default message. Args: (0), (1), (2).*", user.getLocalLocale());
```

毫无疑问，你会发现 MessageSource 实现在 Java 代码中使用起来要容易得多。你的 Java 代码不再需要知道基名、为该包定位 ResourceBundle，并从注入的 MessageSource 实现中解析格式。相反，它只需要在注入的 MessageSource 实现上调用单个方法即可。这在桌面应用程序中将是极其有用的。但在一个设计良好的 Web 中，你有多频繁需要在 Java 代码中进行本地化？

# 使用消息源使 JSP 国际化

Spring 开始使用 `org.springframework.framework.context.support.MessageSourceResourceBundle`。（注意它与 `ResourceBundleMessageSource` 的相似之处；确保不要混淆。）`MessageSourceResourceBundle` 扩展了 `ResourceBundle` 并向底层 `MessageSource` 暴露 `ResourceBundle` 方法，将调用委托给特定 Locale 的 `ResourceBundle`。当使用 `JstlView` 访问 JSP 时，Spring MVC 会自动为用户指定的或默认设置 `MessageSourceResourceBundle`。

# 使用基础国际化和本地化 API

使用 `javax.servlet.jsp.fmt.LocalizationContext` 进行本地化，以便 `<fmt:message>` 能够正常工作。

当然，当你在从 Spring MVC 控制器使用 `JstlView`（无论是直接使用还是通过视图解析器）时，这种方法仅对 JSP 有效。你可能还会访问其他不通过 Spring 访问的 JSP，例如错误页面或不需要控制器的简单页面。由于 Spring 不会参与这些类型 JSP 的请求周期，因此它无法自动设置 `MessageSourceBundle`。

你可以使用两种策略来为这些不受 Spring Framework 控制的 JSP 获取用于国际化的 `MessageSourceBundle`：

- 最简单的方法是使用 Spring 库中的 `<spring:message>` 标签代替 `<fmt:message>` 标签。你将在本章的稍后学习更多关于它的内容，它比 `<fmt:message>` 标签具有多个优势。其中一个优势就是能够使用 `MessageSource`。

- 如果由于某些原因，你不想使用 `<spring:message>` 标签，另一种方法是创建一个过滤器（Filter），来处理所有未由 Spring Framework 处理的 JSP 请求。你需要使用 Spring 编写这个过滤器，它将使用 `org.springframework.web.servlet.support.JstlUtils` 类来模拟 `JstlView` 的行为并设置 `LocalizationContext`。当然，如果你使用 `Accept-Language` 以外的技术来设置用户本地化，你需要确保在过滤器在过滤器链上执行之前检测并设置了用户本地化。

下面的假设性 `JstlLocalizationFilter` 实现了第二种方法。

```java
public class JstlLocalizationFilter implements Filter
{
    private ServletContext servletContext;
    @Inject MessageSource messageSource;

    @Override
    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
        JstlUtils.exposeLocalizationContext((HttpRequest)request, this.messageSource);
        chain.doFilter(request, response);
    }

    @Override
    public void init(FilterConfig config) throws ServletException {
        ServletContext servletContext = config.getServletContext();
        WebApplicationContext context = WebApplicationUtils.getRequiredWebApplicationContext(this.servletContext);
        AutowiredCapableBeanFactory factory = context.getAutowireCapableBeanFactory();
        factory.autowireBeanProperties(this, BeanFactory.AUTOWIRE_BY_TYPE, true);
        factory.initializeBean(this, "jstlLocalizationFilter*");
        this.messagesSource = JstlUtils.getAwareMessageSource(
            this.servletContext, this.messageSource
        );
    }

    @Override
    public void destroy() { 
    }
}
```

## 在 Spring Framework 中配置国际化

现在你已经了解了消息源（message sources）和资源包（resource bundles）是如何运作的，你可能急于学习如何配置它们了。在 Spring 中配置消息源是简单的，只需要几行代码。然而，这并不是让 Spring 国际化正常运行所需的全部工作。大多数网站都为用户提供了某种更改本地化语言的方法，你可能也想提供这种功能。除了临时更改本地化之外，用户还希望通过某些配置设置永久设置他们的本地化。这些都是你必须考虑的事项。本节将在下一章中讨论不同的选项以及如何在 Spring 中配置国际化。

## 创建消息源

在 Spring Framework 中创建消息源是一项简单的任务。你所做的只是在你的配置类中创建一个 `@Bean` 方法，并返回你选择的 `MessageSource` 实现。该 bean 必须命名为 `messageSource`。

```java
private static final Logger logger = LoggerFactory.getLogger(getClass().getName());

@Bean
public MessageSource messageSource() {
    ReloadableResourceMessageSource messageSource = new ReloadableResourceMessageSource();
    messageSource.setCacheSeconds(-1);
    messageSource.setDefaultEncoding(StandardCharsets.UTF_8.name());
    messageSource.setBasenames(
        "WEB-INF/i18n/messages", "/WEB-INF/i18n/errors"
    );
    return messageSource;
}

@Bean
public ObjectMapper objectMapper() {
    ...
}
```

## 在 Spring 中配置国际化

在这种情况下，你使用了 `ReloadableResourceMessageSource`。你可能注意到缓存时间（秒）被设置为 -1。这将禁用重载并使源永久缓存（直到 JVM 重启）。

为什么不使用 `ReloadableResourceMessageSource` 呢？`ReloadableResourceMessageSource` 的性能优于 `ResourceBundleMessageSource` —— 前者是你禁用了重载。如果启用重载（`cacheSeconds > 0`），解析消息所需的时间相差了。将缓存时间设置为 -1 是你在生产环境中可以使用的最优性能配置。在开发环境中，你可能想将缓存时间设置为正数，这样你就可以在不重启的情况下更改本地化消息。这是 Spring Profiles 的完美人选，你在第 2 章中学习过它。

你注意到的关于消息源配置的另一个点是默认编码被设置为 UTF-8。Spring 必须知道属性文件的编码，以便正确读取它们。还有另一个属性 `fileEncodings`，你可以用它来设置单个文件的编码。`defaultEncoding` 属性设置了 `fileEncodings` 属性中未找到文件的编码。因为 UTF-8 可以编码来自任何已知语言的任何字符，在大多数情况下，你只需要将默认编码设置为 UTF-8，并确保你的属性文件是用 UTF-8 编码的。这比根据每个文件所包含的语言为每个文件管理不同的编码要简单得多。

最后，消息源配置了基名（basenames）`/WEB-INF/i18n/messages`。

# 在 Spring Framework 中配置国际化 | 427

```java
@Inject MessageSource messageSource;

@Override
public void doFilter(ServletRequest request, ServletResponse response,
    FilterChain chain) throws IOException, ServletException
{
    request.setAttribute(DispatcherServlet.LOCAL_RESOLVER_ATTRIBUTE, this.localResolver);
    JsUtils.exposeLocalizationContext(
        (HttpServletRequest) request, this.messageSource
    );
}
```

这段代码没有使用 `@Autowired LocalResolver`，因为过滤器是使用根应用上下文连接的，但 `localResolver` bean 存在于 `DispatcherServlet` 的应用上下文中。`LocalResolver` 的实现都是非常轻量级的对象，因此在这里有一个重复的解析器是可以接受的。

# 使用 HandlerInterceptor 更改语言区域

现在，你的应用程序可以确定用户所需的语言区域，但如果用户希望在此使用不同的语言区域，你该如何设置属性呢？`org.springframework.web.servlet.HandlerInterceptor` 接口定义了如何拦截 `DispatcherServlet` 处理的请求，类似于过滤器（Filter）。`preHandle` 方法在 `DispatcherServlet` 接收请求后、执行控制器上的处理器方法之前执行。`postHandle` 方法在处理器返回后、视图渲染之前执行。`afterCompletion` 方法在视图渲染后、`DispatcherServlet` 将控制权交回容器之前执行。

如果你有想要实现的类似于后期（later-like）的行为，可以使用 Spring 管理的 bean 来，并使该行为仅适用于由 `DispatcherServlet` 服务请求，使用 `HandlerInterceptor` 是实现这一点的很好的方法。

`org.springframework.web.servlet.i18n.LocaleChangeInterceptor` 是用于更改语言区域的 `HandlerInterceptor`。在每次向 `DispatcherServlet` 请求请求时，它会查找一个请求参数，该参数默认为 `locale`，但可以自定义。如果存在此请求参数，拦截器会将 String 参数转换为 `Locale`，然后使用 `LocaleResolver` 的 `setLocale` 方法来设置语言区域。这样，`LocaleResolver` 就负责确定如何获取语言区域以及如何设置语言区域。

要设置 `LocaleChangeInterceptor` 或任何其他拦截器，你需要在 ServletContext 配置类中重写 `WebMvcConfigurerAdapter` 的 `addInterceptors` 方法。如果你想自定义检查的请求参数，应该实例化拦截器，调用 `setParamName` 方法，然后将其添加到注册表中。

```java
@Override
public class UserHeaderLocaleResolver extends CookieLocaleResolver {
    @Override
    public Locale resolveLocale(HttpServletRequest request) {
        Locale locale = null;
        Principal user = request.getUserPrincipal();
        if (user != null && user instanceof FooPrincipal) {
            locale = ((FooPrincipal)user).getLocale();
        }
        if (locale == null) {
            locale = super.resolveLocale(request);
        }
        return locale;
    }
}
```

由于你有多种方法可以完成此任务，且这些方案很大程度上取决于你的身份验证机制和用户 API，因此本示例未在 Localized-Application 项目中演示。

# 包含时区支持

在对应用程序进行国际化时，语言区域（locale）并不是你唯一考虑的主题。除了语言和地区，时区也是 Web 应用用户的一个主要问题。大多数用户希望在页面上显示他们所在区域的时间，而不是服务器时间，特别是当服务器位于地球的另一端时。通常很难得知世界不同地区是哪一天；Spring Framework 4.0 包含了对时区的原生支持，使用了 `java.util.TimeZone` 和 `java.time.ZoneId` 类。对于这些类型的 Spring `PropertyEditors`，你可以在控制器方法中指定它们，Spring 可以为这些类型参数转换请求参数、路径变量和处理器值。

Spring 还可以解析用户的时区并将其提供给你的控制器方法，类似于它解析并将用户的语言区域提供给控制器方法的方式。然而，这种机制的工作原理与语言区域解析不同。没有 `TimeZone` 或 `ZoneId` 解析器，因此没有时区解析器。这种机制与语言区域解析不同。没有 `TimeZone` 或 `ZoneId` 解析器，因此没有解析器。时区与语言区域的处理方式不同，且它们通常不会像语言区域那样被更改。从 Spring 早期开始，就可以通过 `LocaleHolder` 手动设置语言区域。在 Spring 4.0 中，`LocaleHolder` 也支持获取当前时区。你可以利用 `LocaleHolder` 自动设置用户的时区。这使得管理时区的任务变得简单得多。你需要做的只是确定用户使用的时区并设置到区中。

# 理解主题如何改进国际化

Spring 有一个关于主题（themes）的概念，与国际化非常相似。主题是样式表、JavaScript 文件以及其他必要资源的集合。`Theme` 接口表示一个主题，可用的 `ThemeResolvers`（包括 `SessionThemeResolver` 和 `CookieThemeResolver`）可以解析主题。`ChangeThemeInterceptor` 使用可配置的请求参数来更新用户的主题。主题具有 `ResourceBundleSource`，与 `ResourceBundleMessageSource` 非常相似，后者持有属性。最后，当使用 `<spring:theme>` 标签创建视图时，输出特定主题的 URL。



# 第 15 章 使用 Spring Framework 进行国际化

到此时，你可能在想这与国际化和本地化有什么关系，除了 API 如此相似。请记住，在国际化应用程序时，语言内容并不是你必须考虑的内容。世界各地的语言也以不同的方向打印：

- 英语和其他西方语言从左到右、从上到下阅读。
- 中东语言（如阿拉伯语和希伯来语）通常从右到左、从上到下阅读。
- 日语、中文和韩语从上到下阅读。
- 蒙古语从上到下、从左到右阅读。

如果你认为仅仅翻译你的应用程序就很困难了，等当你尝试考虑所有四种语言方向吧！

Spring Framework 主实际上可以提供巨大的帮助。与其使用标准的 `ThemeResolver`，你可以创建一个根据语言设置主题的 `ThemeResolver`。使用 `java.awt.Component.Orientation(Locale)` 方法，你可以根据语言检测文本方向并返回该方向的正确主题。你还需要 `LocaleResolver` 和 `LocaleChangeInterceptor` 来防止用户选择你不支持的语言（如蒙古语）。由于主题始终基于语言区域，因此不需要 `ThemeChangeInterceptor`。在配置完成后，你可以更改文本方向的其他解决方案（例如为每个文本方向自定义视图）。

> **注意** 此主题显然是高级的，而且支持多种文本方向所产生的复杂性和问题非常多，超出了本书的范围。因此，这是你会在书中关于文本方向的唯一提及。希望它能为你提供如何更好地支持国际用户的灵感。

## 代码的国际化

在第 7 章中，你尝试使用 `<fmt:message>`、`<fmt:formatDate>` 和 `<fmt:formatNumber>` 对你的 JSP 进行国际化。本节将不会揭示格式化和国际化标签库的细节，但你可以使用它来国际化你的 JSP。Localized-Application 项目包含一个 `HomeController`，其中包含一个映射。这个简单的处理器方法向模型添加了几个项目并返回一个视图。

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

`WEB-INF/i18n/messages_en_US.properties` 文件包含了针对美国英语的本地化消息。

```properties
title.alerts=Server Alerts Page
alerts.current.date=Date and Time:
number.alerts={0,choice,0#no alerts|1#is no alert|1<|1,{0,integer} alerts} in the log:
alert.details=critical={0,choice,0#no critical is|1#One alert is|1<|1,{0,integer} alerts are critical}, important={0,choice,0#no important is|1#One alert is|1<|1,{0,integer} alerts are important}, trivial={1} are trivial.
```

`WEB-INF/i18n/messages_es_MX.properties` 包含了墨西哥西班牙语的本地化消息。

```properties
title.alerts=Server Alerts Página
alerts.current.date=Fecha y hora:
number.alerts={0,choice,0#no alertas|1#Hay alerta|1<|{0,integer} alertas} en el registro.
alert.details=critical={0,choice,0#no críticos son|1#Una alerta es|1<|{0,integer} alertas son críticos}, important={0,choice,0#no importantes son|1#Una importante es|1<|{0,integer} alertas son importantes}, trivial={0,choice,0#no hay alertas triviales|1#Una alerta es trivial|1<|{0,integer} alertas son triviales}.
```

## 使用 `<spring:message>` 标签

如果你熟悉 `<fmt:message>` 标签，那么 `<spring:message>` 标签应该会起来很自然，因为它非常相似但最终更好。`code` 属性相当于 `<fmt:message>` 的 `key` 属性，用于指定消息代码。两者都具有 `var` 和 `scope` 属性，用于在页面上内联打印之前将本地化值导出到 EL 变量。`<spring:message>` 没有 `bundle` 属性的等价项，因为 `<spring:message>` 使用的是 `ResourceBundle` 的 `MessageSource` 实例。

`javascript` 属性特别有用，如果设置为 `true`，它会将最终格式化消息中的 `"` 和 `'` 分别替换为 `\"` 和 `\'`，从而安全地用于 JavaScript 字符串。默认情况下，该属性为 `false`，且 `<fmt:message>` 中没有等价项。`htmlEscape` 属性同样允许 `<spring:message>` 在设置为 `true` 时将最终格式化消息中的特殊字符 `<`、`>`、`&` 和 `'` 转为对应的实体序列。默认值为 `false`。

如果页面上的大部分或所有 `<spring:message>` 标签都需要进行 HTML 转义，你可以在 JSP 中使用 `<spring:htmlEscape defaultHtmlEscape="true" />` 标签来影响其后的所有 `<spring:message>` 标签。如果你整个应用程序中的大部分或所有 `<spring:message>` 标签都需要进行 HTML 转义，你可以在描述符中通过程序方法将上下文参数 `defaultHtmlEscape` 设置为 `true`，这将影响应用程序中所有的 `<spring:message>` 标签。出于优先级考虑，如果显式设置 `<spring:message>` 的 `htmlEscape` 属性，它总是会覆盖 `<spring:htmlEscape>` 标签和上下文参数；而 `<spring:htmlEscape>` 标签如果被显式使用，总是会覆盖其所在的上下文。

```xml
<context-param>
  <param-name>defaultHtmlEscape</param-name>
  <param-value>true</param-value>
</context-param>
```

`<fmt:message>` 和 `<spring:message>` 之间的最终区别在于你如何在消息中指定本地化内容。当你使用 `<fmt:message>` 时，你可以仅使用 `key` 属性或标签作为消息代码来指定消息，并在必要时使用嵌套的 `<fmt:param>` 标签作为格式参数。`<spring:message>` 更加灵活，允许你使用以下三种策略之一。你可以使用 `<spring:message>` 标签指定消息，你可以：

- 传统上使用 `code` 属性或标签作为消息代码，并在必要时嵌套 `<spring:argument>` 标签作为格式参数。该功能在 Spring 4.0 中引入，工作方式与 `<fmt:param>` 标签完全相同。你还可以使用 `text` 属性指定默认消息格式，当消息代码无法解析时将使用该值。你不应结合 `arguments`、`argumentSeparator` 或 `message` 属性使用此策略。
- 使用 `code` 属性或标签作为消息代码，并在必要时在 `arguments` 属性中提供分隔的参数列表。默认分隔符是单个逗号，但你可以使用 `argumentSeparator` 属性自定义分隔符。你还可以使用 `text` 属性指定默认消息格式，当消息代码无法解析时将使用该值。你不应结合 `message` 属性或嵌套的 `<spring:argument>` 标签使用此策略。
- 使用 EL 表达式通过 `message` 属性使用 `MessageSourceResolvable` 实例。因为 `MessageSourceResolvable` 提供了自身的代码和默认消息，所以你不将其与 `code`、`arguments`、`argumentSeparator` 和 `text` 属性、标签体或嵌套的 `<spring:argument>` 标签一起使用。

`<spring:message>` 和 `<fmt:message>` 标签的使用在 Localized-Application 项目的 `WEB-INF/jsp/view/index.jsp` 文件中。你会发现该文件没有包含字符串字面量，而是对所有文本输出都使用了消息国际化。它应该是这样的：

```jsp
<%-- @elvariable id="date" type="java.util.Date"--%>
<%-- @elvariable id="alerts" type="int"--%>
<%-- @elvariable id="numCritical" type="int"--%>
<%-- @elvariable id="numImportant" type="int"--%>
<%-- @elvariable id="numTrivial" type="int"--%>
```

```html
<!DOCTYPE html>
<html>
<head>
  <title><spring:message code="title.alerts"/></title>
</head>
<body>
  <h2><spring:message code="title.alerts"/></h2>
  <fmt:message key="${alerts}.current.date">
  <fmt:message key="number"/><<<i>i</i> <br /> />
  <fmt:message key="number.alerts"/>
  <c:if test="${alerts} > 0">
  &nbsp;<spring:message code="alert.details">
    <spring:argument value="${numCritical}" />
    <spring:argument value="${numImportant}" />
    <spring:argument value="${numTrivial}" />
  </spring:message>
  </c:if>
</body>
</html>
```

## 清晰地处理应用程序错误

正如你所知，应用程序错误会发生。程序最终会出现问题并导致无法正常运行。通常这会导致抛出异常。在第 11 章中，你学习了日志如何帮助你清晰地处理这些错误。然而，对用户隐藏所有错误并不是向用户显示所有堆栈轨迹的替代方案。当出现问题时，用户需要知道。你应该记录技术细节，但应该向用户显示尽可能非技术性的错误消息，帮助他们理解发生了什么。这条消息还必须是本地化的。

你有许多方法来处理这个问题，涵盖所有可能性超本书的范围。相反，本书提供了一种模式供你参考，并展示了它如何极大地简化你的应用程序开发。

当某些预料但意外的类型异常时（例如使用 JDBC 执行 SQL 语句时发生 `SQLException`），自然的倾向是捕获异常并记录它。这样做可以，但你仍然需要向用户报告该错误消息。你可以重新抛出异常，但这样应用程序中的高层会知道它已经被记录过了吗？如果简单地重新抛出异常，如何向用户呈现实用的错误消息呢？毕竟，三层之下捕捉异常的视图并异常是在什么上下文中抛出的，因此没有能力为其创建实用的错误消息。

为了解决第一个问题，你可以创建自定义异常并抛出它代替原始异常。你可以将其命名为 `LoggedException`，然后实例化一种策略：`LoggedException` 永远不会被记录，并且在捕获时应重新抛出。所有的 `LoggedException` 构造函数都要求将底层异常作为原因包含。这确实解决了第一个问题，但没有解决第二个问题。

解决此问题的一种方法是让 `LoggedException` 实现 `MessageSourceResolvable`。这样，它就包含了自身的错误代码、默认消息和参数，你可以使用这些内容来实现异常显示的国际化。然而，如果你仔细思考一下，你会很快发现，在某些情况下，你需要在不捕获底层异常的情况下抛出国际化的异常。因此，你真正需要的是实现 `MessageSourceResolvable` 的 `InternationalizedException` 以及一个扩展它的 `LoggedException`。列表 15-1 显示了 Localized-Application 项目中的 `InternationalizedException`。

### 列表 15-1：InternationalizedException.java



```java
public class InternationalizedException extends RuntimeException implements MessageSourceResolvable {
    private static final long serialVersionUID = 1L;
    private static final Locale DEFAULT_LOCALE = Locale.US;

    private final String errorCode;
    private final String[] codes;
    private final Object[] arguments;

    public InternationalizedException(String errorCode, Object... arguments) {
        this(null, errorCode, arguments);
    }

    public InternationalizedException(Throwable cause, String errorCode, Object... arguments) {
        this(cause, errorCode, arguments);
    }

    public InternationalizedException(String errorCode, String defaultMessage, Object... arguments) {
        this(null, errorCode, defaultMessage, arguments);
    }

    public InternationalizedException(Throwable cause, String errorCode, String defaultMessage, Object... arguments) {
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
        Locale locale = LocaleContextHolder.getLocale();
        return locale == null ? InternationalizedException.DEFAULT_LOCALE : locale;
    }
}
```

`getMessage` 和 `getLocalizedMessage` 方法并不是严格要求的，但它们使得在 Java 代码内部使用该异常变得更容易。此异常可以在代码的任何地方抛出，也可以在没有引起异常的情况下抛出。它的扩展类是 `LoggedException`，如列表 15-2 所示。该异常没有任何方法或字段；它限制了用户通过构造函数提供一个引起异常。

## 列表 15-2：LoggedException.java

```java
public class LoggedException extends InternationalizedException {
    private static long serialVersionID = 1L;

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

你已经意识到记录异常并用之抛出 `LoggedException` 的优势，这可以防止高层捕获异常并重新抛出（relging）。为了演示本地化异常有多简单，请按照以下步骤操作：

1. 在 `HomeController` 的处理方法中添加以下内容。

```java
model.put("exception", new InternationalizedException(
    "bad.food.exception", "You ate bad food.");
);
```

2. 在 `/WEB-INF/i18n/errors_en_US.properties` 中为消息添加翻译：

```
bad.food.exception=You ate bad food.
```

3. 在 `/WEB-INF/i18n/errors_es_MX.properties` 中，

```
bad.food.exception=Comiste comida el mal estado.
```

4. 更新 `/WEB-INF/jsp/view/home/index.jsp`，使用 `<spring:message>` 显示异常。

```xml
<c:if>
    <c:if test="${exception != null}"><br /><br /> <spring:message message="${exception}" />
</c:if>
</body>
</html>
```

要测试 Local-Application 项目，请编译它，从 IDE 启动 Tomcat，并在你喜欢的浏览器中访问 `http://localhost:8080/i18n/`。你会看到页面以英文良好显示。访问 `http://localhost:8080/i18n/locale=es_MX`，页面应该切换为西班牙语。此外，你现在可以多次返回不带 locale 参数的 `http://localhost:8080/i18n/`，且页面将保持为西班牙语。只有当你访问 `http://localhost:8080/i18n/locale=en_US` 时，页面才会恢复为英文，并在没有 locale 参数的情况下保持该状态。

> 注意：如果你在本地语言为西班牙语的计算机上访问该应用程序，页面实际上应该首先显示西班牙语，而不是英语，前提是你的浏览器发送了 `Accept-Language` 头部。如果是那样……

## 更新客户支持系统

从 wrox.com 网站获取的 Customer-Support-v2 项目现在使用相同的配置进行国际化。唯一的区别是 Customer Support 应用程序有一个额外的资源包。

```java
messageSource.setBasenames(
  "/WEB-INF/i18n/titles",
  "/WEB-INF/i18n/messages",
  "/WEB-INF/i18n/errors"
);
```

i18n 文件 `errors_en_US.properties`、`messages_en_US.properties` 和 `titles_en_US.properties` 包含了几十条消息。大部分的国际化工作都是 `<spring:message>` 的常规操作，但 `/WEB-INF/jsp/view/chat.jsp` 文件是一个有趣的例子。这是一个需要进行本地化的 JavaScript 字符串的文件。配合 `JavaScriptEscape="true"` 使用 `<spring:message>` 对此非常方便……

## 直接使用 Message Source

为了解决这个问题，`ChatMessage` 需要包含一个消息代码和用于实际本地化的参数。`UserController` 使用 `MessageSource` 来实现这一目标。第一步是重构 `ChatMessage` 类。

```java
public class ChatMessage implements Cloneable {
    private long timestamp;
    private Type type;
    private String user;
    private String contentCode;
    private Object[] contentArguments;
    private String localizedContent;
    private String userContent;

    // mutators and accessors
    // enum
    // clone
}
static abstract class MixInForLogWrite {
    @JsonIgnore public abstract String getLocalizedContent();
    @JsonIgnore public abstract void setLocalizedContent(String l);
}
static abstract class MixInForWebSocket {
    @JsonIgnore public abstract String getContentCode();
    @JsonIgnore public abstract void setContentCode(String c);
    @JsonIgnore public abstract Object[] getContentArguments();
    @JsonIgnore public abstract void setContentArguments(Object[] c);
}
```

国际化 Customer Support 应用程序最后的挑战是处理聊天消息。与其他所有在视图渲染时解析的本地化消息不同，`ChatService` 和 `UserController` 通过 WebSocket 连接输出的消息也必须本地化。`<spring:message>` 和 `<fmt:message>` 标签在这里无效。

> You are now chatting with {0}.

这条消息是参数化的并需要参数。那么当参数在渲染时不可用但必须由 JavaScript 填充时，这种方法有效吗？嗯，简单的格式化会忽略替换模板，因为它们没有对应的参数，因此这条消息在运行时以 `You are now chatting with {0}` 的形式写入 JavaScript 代码中。此时使用该值只需要在 JavaScript 字符串上调用 `replace` 方法将参数替换为相应的参数。

```javascript
infoMessage('<spring:message code=message.chat.joined> JavaScriptEscape="true"' + replace('{0}', user));
```

新的 `MixInForLogWrite` 和 `MixInForWebSocket` 内部类是用于支持 Jackson 数据处理器 Mix-In 注解功能的特殊类。`localizedContent` 不应该是被写入聊天日志文件，因为它已针对特定用户进行了本地化。同样，`contentCode` 和 `contentArguments` 不需要通过 WebSocket 连接传输，因为消息已经过本地化。另一方面，用户提供了 `userContent` 属性，因此你无法对其进行本地化。你必须原封不动地传输并写入此消息。要使用这些 Mix-In 注解，首先要向 `DefaultChatService` 添加一个 `@PostConstruct` 方法。

```java
@PostConstruct
public void initialize()
{
    this.objectMapper.addMixInAnnotations(ChatMessage.class,
ChatMessage.MixInForLogWrite.class);
}
```

现在你可以使用静态初始化器在 `ChatMessageDecoderCodec` 的 `ObjectMapper` 中添加不同的 Mix-class。由于这是一个不同的 `ObjectMapper` 实例，它不会与你添加到 `DefaultChatService` 中的 Mix-In 发生冲突。

```java
MAPPER.addMixInAnnotations(ChatMessage.class,
ChatMessage.MixInForWebSocket.class);
```

接下来，你需要引用 `DefaultChatService` 来使用消息和参数，而不是静态消息。

```java
public CreateResult createSession(String user)
{
    message.setContent("*message.chat.started.*");
    message.setContentArguments(user);
    ...
}
```

```java
public JoinResult joinSession(long id, String user)
{
    ...
    message.setContent("*message.chat.joined.*");
    message.setContentArguments(user);
}
```

```java
public ChatMessage leaveSession(ChatSession session, String user,
ReasonForLeaving reason)
{
    if (reason == ReasonForLeaving.ERROR)
        message.setType(ChatMessage.Type.LEFT);
    if (reason == ReasonForLeaving.ERROR)
        message.setContent("*message.chat.left.chat.*");
    else if (reason == ReasonForLeaving.LOGGED_OUT)
        message.setContent("*message.chat.left.logged.*");
    else
        message.setContent("*message.chat.left.chat.normal.*");
    message.setContentArguments(user);
    ...
}
```

此时，一切都已编译，但端点尚未对消息进行本地化。它首先需要一个 `MessageSource` 和一个 `Locale`：

```java
private Locale locale;
private Locale otherLocale;
...
@Inject MessageSource messageSource;
```

本地化无法被注入，因此 `ChatEndpointConfigurator` 的 `modifyHandshake` 方法从 Spring 获取 `Locale` 并将其添加到 WebSocket Session 中。

```java
config.getUserProperties().put(LOCALE_KEY, LocaleContextHolder.getLocale());
```

`ChatEndpoint` 的 `getExposedLocale(session)` 方法：

```java
this.locale = EndpointConfigurator;

this.otherWsSession = this.chatSession.getCustomer();
this.otherLocale = EndpointConfigurator.getExposedLocale(this.otherWsSession);
```

`ChatEndpoint` 还需要一个内部辅助方法来简化本地化。通过调用此方法，你可以在一行代码中克隆并本地化一个 `Message`。



```java
private ChatMessage cloneAndLocalize(ChatMessage message, Locale locale)
{
    message = message.clone();
    message.setLocalizedContent(this.messageSource.getMessage(
        message.getCode(), message.getContentArguments(), locale
    ));
    return message;
}
```

你可以本地化所有内部生成的 `ChatMessage` 发送的地方。记住，你不能本地化用户生成的 `ChatMessage`，因为它们包含用户内容，而不是消息代码。

```java
session.getBasicRemote().sendMessage(this.cloneAndLocalize(
    result.createMessage(), this.locale
);

session.getBasicRemote().sendMessage(this.cloneAndLocalize(
    this.chatSession.createMessage(), this.otherLocale
));
session.getBasicRemote().sendMessage(this.cloneAndLocalize(
    result.getJoinMessage(), this.locale
);
this.otherWsSession.getBasicRemote(
    .sendMessage(this.cloneAndLocalize(
        result.getJoinMessage(), this.otherLocale
    ));

this.wsSession.getBasicRemote(
    .sendMessage(this.cloneAndLocalize(
    message, this.locale
this.wsSession.close(closeReason);
...
this.otherWsSession.getBasicRemote()
  sendObject(this.cloneAndLocalize(
    message, this.otherLocale
));
this.otherWsSession.close(closeReason);
```

现在客户支持应用程序的国际化已经完成，编译它，从 IDE 启动 Tomcat，并访问 `http://localhost:8080/support/`。登录并浏览。创建、列出和查看工单，查看会话列表。从另一个浏览器登录并参与会话。国际化和本地化确实需要投入大量精力，但 Spring Framework 提供的工具使任务变得简单得多。

### 总结

在本章中，你学习了关于国际化 (i18n) 和本地化 (L10n) 在概念和实践方面的大量知识。你见证了这些任务的困难之处，并尝试了 Spring Framework 提供的所有工具来简化它。你使用 `<spring:message>` 和 `<fmt:message>` 国际化了 JSP 视图，并使用 Spring 的 `MessageSource` 国际化了 Java 字符串。你还学习了配置 Spring 国际化和本地化支持时的所有选项，并接触了“日志记录与国际化异常”模式。最后，你还了解了对用户时区的支持，并简要介绍了非西方语言区域中中文本方向的复杂性。

在下一章中，你将学习 JSR 303/JSR 349 自动验证和 Hibernate Validator。

## 为什么选择 Hibernate Validator？

JSR 349 仅仅是元数据模型和验证 API 的规范。你仍然需要该 API 的实现才能在你的应用程序中使用 Bean Validation。Hibernate Validator 5.0 是 JSR 349 的参考实现，意味着它符合该规范。此外，你通常可以认为它在识别和修复问题方面领先于其他实现；它是所有 Bean Validation 实现中使用最广泛的。（Hibernate Validator 5.1 包含了多项重要的增强、错误修复和性能改进，以更好地支持 JSR 349。）

事实上，Hibernate Validator 是 Bean Validation 标准的灵感来源，这一点从 Hibernate Validator 的版本号远超规范版本号这一事实中可以显而易见看出。Hibernate Validator 已经存在多年了。它最初是 Hibernate ORM 项目的一部分（你将在本书的第三部分学习到它），在实体持久化到数据库之前对其提供声明式验证。最终，它变成了一个独立的项目，并在多年后演变为了 Bean Validation 标准。

## 理解注解元数据模型

Bean Validation 通过对字段、方法等进行注解来工作，指示特定约束适用于被注解的目标。任何保留策略为 `RUNTIME`（意味着注解在编译后生存并在运行时类中可用）并标记有 `@javax.validation.Constraint` 的注解都代表一个约束注解。API 带有了几个预定义的约束注解，但你可以创建自己的注解，并提供与你的自定义注解对应的 `javax.validation.ConstraintValidator` 实现。`ConstraintValidator` 负责评估特定的约束类型。API 没有为内置约束定义 `ConstraintValidators`，因为这取决于实现类如何处理这些内置注解。

约束注解可以放置在字段、方法或方法参数上。当放置在字段上，每当对类的实例调用验证方法时，验证器应该检查是否符合约束。当放置在 Java 访问方法（accessor method）上时，它仅作为注解底层字段的替代方案。在接口方法上进行注解，意味着约束应该应用于该方法执行后的返回值。对接口方法的一个或多个方法参数进行注解，意味着约束应该在方法执行之前应用于方法参数。

在 POJO 约束上使用 Bean Validation 注解时，你必须创建一个代理来验证目标实现类。这需要接口的消费者具备某种形式的依赖注入，以便实际调用其实现类的代理。实现 Java EE 7 的完整 Java EE 应用程序服务器提供了提供经过适当验证的 DI 实现的能力。然而，当使用 Tomcat 等 servlet 容器时，你必须提供其他的 DI 解决方案。

## 在 Spring Framework 中使用 Bean Validation

显然，Spring Framework 的依赖注入是解决此问题的方案。Spring Framework 会自动对使用 Bean Validation 的 Spring 管理 bean 创建代理。对带注解方法的调用将被拦截并妥善验证，无论消费者是否提供了有效参数或实现类是否返回了合法值。在 `@Services` 上使用 Bean Validation 非常常见，因为这些是处理业务逻辑的 Spring 管理 bean。如果参数被标记为 `@javax.validation.Valid`，Spring Framework 还会对传递给控制器处理程序的任何表单对象或其他带有约束注解的参数进行验证。

在本章中，你将探索如何在 Spring Framework 中配置 Bean Validation，以及如何使用所有提供的约束注解将业务规则应用于你的 bean。你还学习了如何为内置约束无法满足的规则创建自己的自定义的约束注解。

## 在 Spring Framework 容器中配置验证

在轻松使用任何验证工具之前，你必须首先在 Spring Framework 配置中设置 Bean Validation。这并不是说在 Spring 中配置 Bean Validation 是使用验证器的必要条件，因为即使没有 Spring 容器，标准的验证代码仍然可以工作：

```java
ValidatorFactory factory = Validation.buildDefaultValidatorFactory();
Validator validator = factory.getValidator();
Set<ConstraintViolation<Employee>> violations = validator.validate(employee);
if (violations.size() > 0)
    throw new ConstraintViolationException(violations);
```

但你并不希望那样使用它。你希望它是自动的，这意味着 Spring Framework 的依赖注入和代理支持必须参与其中。为了实现这一点，需要：

- 一个验证器
- 验证器的消息本地化
- 一个方法验证处理器
- Spring MVC 表单验证

对于这一点，请使用从 wrox.com 下载源获取 HR-Portal 项目。

由于在使用 Tomcat 时没有必要设置提供者类，因此书中的示例没有这样做。

## 设置错误代码本地化

在接下来的节中，你将探索如何向类和实体添加约束注解。当你执行此操作时，可以为每个约束指定一个相应的错误消息。或者，你可以指定一个错误代码。

错误代码允许你对约束进行国际化，以便在显示给用户之前对其进行本地化处理。Bean Validation 的默认国际化使用资源文件 `ValidationMessages.properties`、`ValidationMessages_[language].properties`、`ValidationMessages_[region].properties` 等。这些文件必须位于类路径上（`/WEB-INF/classes`）。然而，使用任何 Bean Validation 1.1 实现，你都可以通过 `javax.validation.MessageInterpolator` 提供自己的国际化（Hibernate Validator 4.2 和 4.3 在 Bean Validation 1.1 发布之前也提供了对插值器的支持）。无论哪种方式，你都需要为验证器指定每次激活时要使用的 `Locale`。

再次，Spring 出现出现，让你轻松地提供自定义的 `MessageInterpolator` 并消除对 `Locale` 的担忧。你只需要在 `RootContextConfiguration` 中定义的 `LocalFactoryBean` 上设置 `MessageSource`，它就会自动提供由该 `MessageSource` 支持的插值器：

```java
@Bean
public MessageSource messageSource() {
    ReloadableResourceBundleMessageSource messageSource = new ReloadableResourceBundleMessageSource();
    messageSource.setCacheDefaultEncoding(Charsets.UTF_8.name());
    messageSource.setBasenames("/WEB-INF/i18n/titles", "/WEB-INF/i18n/messages", "/WEB-INF/i18n/errors", "/WEB-INF/i18n/validation");
    return messageSource;
}
```

```java
@Bean
public LocalValidatorFactoryBean localFactoryBean() {
    LocalValidatorFactoryBean validator = new LocalValidatorFactoryBean();
    validator.setValidationMessageSource(this.messageSource());
    return validator;
}
```

现在你已经配置了 `LocalValidatorFactoryBean` 使用你的 `MessageSource`，你就可以在创建所有其他本地化消息的同时，创建本地化验证消息：

```java
@Bean
public LocalValidatorFactoryBean localValidatorFactoryBean() { ... }

@Bean
public MethodValidationPostProcessor methodValidationPostProcessor() {
    MethodValidationPostProcessor processor = new MethodValidationPostProcessor();
    processor.setValidator(this.localValidatorFactoryBean());
    return processor;
}

@Bean
public ObjectMapper objectMapper() { ... }

..
```

此 `MethodValidationPostProcessor` 会寻找带有 `@org.springframework.validation.annotation.Validated` 或 `javax.validation.executable.ValidateOnExecution` 注解的类代理，它们在方法执行前对带了注解的参数进行参数验证，并在方法执行后对带了注解的方法进行返回值验证。两个节之后，你将学习如何在类方法上添加注解来激活此过程。

## 让 Spring MVC 使用相同的验证

与你刚刚使用的 `MethodValidationPostProcessor`（它使用 `Validator` 实例）不同，`Spring MVC` 控制器的表单对象和参数验证使用的是 `Spring Validator` 实例。这支持为期望 `@Valid` 参数的方法提供 `Errors` 参数，因为 `Errors` 接口比 `ConstraintViolations` 更容易使用。幸运的是，`LocalValidatorFactoryBean` 同时实现了这两个验证器接口，但默认情况下，Spring MVC 会创建一个独立的 `Spring Validator` 实例，这会掩盖根应用上下创建的那个。

要更改此默认配置，你只需要更改 `ServletContextConfiguration` 类以重写 `WebMvcConfigurerAdapter` 的 `getValidator` 方法，并返回根应用中创建的验证器。

```java
@Override
public Validator getValidator()
{
    return this.validator;
}
```

通过此更改，Spring MVC 将使用你配置的验证器来验证适当的控制器处理参数，你的 Spring Bean Validation 现在就大功成了。

## 为你的 Bean 添加约束验证注解

对于 Bean Validation，你的 Spring 应用主要处理两种类型的 Bean：

- POJO 或类似于 JavaBean 的实体和表单对象，它们通常是方法参数或返回类型
- 像 `@Controllers` 和 `@Services` 这样的 Spring Bean，它们使用这些 POJO 作为方法参数和返回类型

这两类 Bean 都使用 Bean Validation 约束注解，但方式不同。在本节中，你将尝试在 POJO 上应用约束注解，在下一一节中，你将学习如何通过向你的 Spring Bean 应用注解来完成此过程。

## 添加内置约束注解

尽管你可以随时创建自己的约束注解，但 Bean Validation API 提供了几个满足最常见验证需求的内置注解。这些都是非常简单的约束，但在许多情况下，它们就是你所需要的。所有约束都在 `javax.validation.constraints` 包中，被注解的目标默认为 `null`。

- `@Null` 你可以将其应用于任何类型，并确保目标为 `null`。
- `@NotNull` 你也可以将其应用于任何类型。它确保目标不是 `null`。
- `@AssertTrue` 和 `@AssertFalse` 确保它们注解的值恰别为 true 和 false。因此，它们注解的字段、参数或方法（返回值）类型必须是 `boolean` 或 `Boolean`。每个约束对 `null` 都认为有效，所以如果你不接受 `null`，请将其与 `@NotNull` 结合。
- `@DecimalMax` 这为数值类型定义了上限，通过 `value` 属性指定。它注解 `BigDecimal`、`BigInteger`、`CharSequence(String)`、`byte`、`Byte`、`short`、`Int`、`Integer` 和 `Long` 类型的字段、参数和方法（返回值）。由于精度问题，不支持基本类型 `Double`、`Double`、`Float`。`CharSequence` 在验证前会被转换为小数，且 `null` 值被视为有效。可选的 `inclusive` 属性指定测试是否应该是包含性的（小于等于）还是不包含的（小于），默认为包含性的 `true`。
- `@DecimalMin` 这是 `@DecimalMax` 的对应项。它以相同的规则适用于所有类型。
- `@Digits` 你可以使用此来确保目标是可解析的数字（如果是 `CharSequence`、`BigInteger`、`byte`、`Byte`、`short`、`Int`、`Integer` 或 `Long`）。`integer` 属性指定整数位数，而 `fraction` 属性指定小数位数。始终认为 `null` 是有效的。
- `@Future` 确保 `Date` 或 `Calendar` 字段、参数或方法（返回值）在未来。在 Bean Validation 1.1 之后，它支持 Java 8 的 `Date` 和 `Time` API。`null` 值被视为有效。
- `@Past` 确保 `Date` 或 `Calendar` 类型在过去。



- `@Max` 和 `@Min` 这些与 `@DecimalMax` 和 `@DecimalMin` 类似，但它们不支持 `CharSequence` 约束，并且没有 `inclusive` 属性——它们总是包含性的。`null` 值被视为有效。

- `@Pattern` 定义了 `CharSequence(String)` 必须匹配的正则表达式 `regexp`，它包含一个可选的 `flags` 属性，支持 `Pattern` 数组。标志值为：

- `CANON_EQ` — 启用等效性

- `CASE_INSENSITIVE` — 不区分大小写的匹配

- `COMMENTS` — 模式中的空格和注释

- `DOTALL` — 开启点多行

- `MULTILINE` — 开启多行

- `UNICODE_CASE` — Unicode 大小转换

- `UNIX_LINES` — 开启行模式

`@Size` 为 `CharSequence(String)` 的长度、`Collection` 中的值数量、`Map` 中的条目数量或数组类型的元素数量定义包含性的最大最小值。

# 理解常用约束属性

如所示，你有大量的约束可以选择。除了已经提到的特定约束注解属性外，所有约束注解还具有以下可选属性。当你创建任何自定义约束时也必须包含这些属性。

- `message` —— 此 `String` 定义了应该显示给用户的消息。消息由花括号包含（例如，`message="*employee.firstName.notBlank*"`），它代表一个必须本地化的约束代码。否则，它只是一个硬编码的消息。默认是每个约束类型不同的消息代码。

- `payload` —— 这是另一个必须使用 `javax.validation.Payload` 的类数组。负载为评估约束的验证提供者或 `ConstraintValidator` 提供某些元信息。这使得内置约束类型在验证提供者之间不可迁移（API 未定义负载类型），但可以用于自定义约束。

最后，所有约束注解都定义了内部注解 `@List`，允许在目标上应用多个相同类型的约束。例如，你可以使用 `@Max` 列表在目标上应用多个 `@Max` 约束。本节后面验证组的部分演示了这些列表的一种可能用途。

# 使用约束

为了理解这些约束的基本用法，请查看 HR-Portal 项目中的 `Employee` POJO。它是基于章节开头看到的假设员工验证业务逻辑的。

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
        regexp = "^[a-z0-9!#\$%&'*+/=?^_`{|}~.-]+\\@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\\.)+[a-z0-9](?:[a-z0-9]))*$",
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

你应该立即注意到以下几点：

- 除了 `manager` 和 `middleName` 之外，大多数字段都标注了 `@NotNull` 注解。

- 之前对许多字段执行的 `trim().length() > 0` 检查没有替代方案，这很快就会变成问题。

- 电子邮件正则表达式如果在许多地方使用，可能会变得非常繁琐。

- `birthdate` 仅在路径中时进行检查，而没有确保员工至少满 18 岁。此外，为了使用内置约束 `birthdate` 必须是日期类型，你可能更倾向于使用 Java 8 的日期类型。

- 员工的部门、位置和职位没有被检查它们是否存在。

你可以通过自定义约束来解决许多问题。然而，并不是每个检查都适用于 Bean Validation 工具。检查部门、位置和职位需要其他的业务逻辑和数据库查询，因此此类任务最好留给手动验证。

> 注意：在本章的末尾，你将学习如何编写自定义验证约束，例如字符串长度、日期边界和电子邮件验证。然而，除了创建自定义约束外还有其他选项。Hibernate Validator 提供了你可以使用的专有约束，但这样做会将你绑定到始终使用 Hibernate Validator 作为提供者。

另一个选项是 Bean Validation Constraint Extensions 项目（Maven 坐标为 `net.nicholaswilliams.java:validation-api-constraint-extensions`），它提供了所有内置约束的空值版本，以及针对电子邮件、信用卡号、IP 地址、Java 8 日期和时间、Joda Date 等其他目标的约束。因为此库只包含约束而不是 Bean Validator，所以与任何提供者配合使用都是安全的。

# 使用 @Valid 进行递归验证

到目前为止，你一直在像 String 和基本数据类型等简单字段类型上使用验证约束注解。但如果你的 bean 包含一个复杂的字段，且该字段本身也标注了验证约束呢？例如，考虑以下情况：

```java
public class Train
{
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

在这种情况下，`Station` 和 `Person` 字段是拥有自己的字段的 POJO，而这些字段也都被标注了验证约束。这些嵌套对象不会被自动验证。为了确保它们是有效的，你可以在这些类型的字段上标注 `@Valid`，这表示字段、参数或方法（返回值）应该导致级联验证。

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

如果 `Station` 或 `Person` 包含也标记为 `@Valid` 的字段，验证将递归继续，直到达到所需的深度。然而，验证器通过循环引用检测无限循环，并在循环回到该字段时在不报错的情况下终止该字段的验证。

# 使用验证组

验证组提供了一种根据其所属的当前活动组来启用或禁用某些约束的方法。这对于 Spring Framework 的 Bean 定义配置（Profiles）非常有用。一个组由任何任意标记接口表示。该接口不需要任何常量或方法，因为它们没有被使用。相反，接口的类 对象在声明约束时标识该组。然后在验证验证时，Validator 仅应用指定了组类的约束。

例如，你可能为不同的场景使用不同的组：

```java
public interface Group1 {}
public interface Group2 {}

public class BusinessObject {
    @Size(min = 5, max = 100, groups = Group1.class)
    private String string1;

    @Size(min = 20, max = 75, groups = Group2.class)
    private String string2;

    // mutators and accessors
}
```

# 为你的 Beans 添加约束注解

```java
public class BusinessObject {
    @Size(min = 5, max = 100, groups = Group1.class)
    private String string1;

    @Size(min = 20, max = 75, groups = Group2.class)
    private String string2;

    // mutators and accessors
}
```



```java
public class Train
{
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

在这种情况下，`Station` 和 `Person` 字段是拥有自己的字段的 POJO，而这些字段也都被标注了验证约束。这些嵌套对象不会被自动验证。为了确保它们是有效的，你可以在这些类型的字段上标注 `@Valid`，这表示字段、参数或方法（返回值）应该导致级联验证。

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

如果 `Station` 或 `Person` 包含也标记为 `@Valid` 的字段，验证将递归继续，直到达到所需的深度。然而，验证器通过循环引用检测无限循环，并在循环回到该字段时在不报错的情况下终止该字段的验证。

# 使用验证组

验证组提供了一种根据其所属的当前活动组来启用或禁用某些约束的方法。这对于 Spring Framework 的 Bean 定义配置非常有用。一个组由任何任意标记接口表示。该接口不需要任何常量或方法，因为它们没有被使用。相反，接口的类对象在声明约束时标识该组。然后在验证验证时，`Validator` 仅应用指定了组类的约束。

例如，你可能为不同的场景使用不同的组：

```java
public interface Group1 {}
public interface Group2 {}

public class BusinessObject {
    @Size(min = 5, max = 100, groups = Group1.class)
    private String string1;

    @Size(min = 20, max = 75, groups = Group2.class)
    private String string2;

    // mutators and accessors
}
```

# 为你的 Beans 添加约束注解

```java
public class BusinessObject {
    @Size(min = 5, max = 100, groups = Group1.class)
    private String string1;

    @Size(min = 20, max = 75, groups = Group2.class)
    private String string2;

    // mutators and accessors
}
```

在 Maven 和 IDE 中还有其他方法应用注解处理器。例如，你可以将依赖添加到编译器插件的依赖中，而不是项目依赖中，这会将类从你的类路径中移除，但会迫使你单独在 IDE 中配置该处理器。对该技术及其他技术的探讨在本书的范围之外。你应该查阅 Java 编译器、Maven 以及你 IDE 的文档以获取更多信息。

## 为方法验证配置 Spring Bean

到目前为止，你已经创建了一个可以进行验证的 Bean（`Employee`），但你还没有编写任何代码来验证它。不过，你可能已经发现可以使用 `Validator` 的 `validateProperty` 或 `validateValue` 方法来验证此 Bean，但你真正想要的是在不直接使用 `Validator` 的情况下自动进行验证。因为 Spring 让这一切变得简单。你通过设置 `MethodValidationPostProcessor` 已经完成了一半工作，它确保了具有方法参数和返回值的 Spring Bean 会被验证。你只需要将你的 Spring Bean 方法进行映射，以指示哪些值或参数应该被验证。

## 注解接口而非实现

使用契约编程范式，开发者依赖代码的契约来满足需求或执行操作，而不必关心这些需求是如何满足的。在 Java 中，接口被认为是契约编程的主要方法。你已经在第 14 章中深入探讨了这一点。你创建一个定义了方法的接口，用以指示实现应该做什么。通常，你会使用 Javadoc 注释来详细说明接口所保证的契约。然后，接口的消费者在使用它时不需要知道或关心实现是如何工作的。

约束注解是编程契约的扩展。除了告诉 `Validator` 如何验证对象外，它们还告诉 API 消费者对类行为的预期。例如，一个标记了 `@NotNull` 注解的方法保证返回非 `null`。自然地，你可能会想这些良好的约束在实现类上会起什么作用，答案是：不会。事实上，它们可能会产生危害。

考虑以下场景：你正在调用接口上的一个方法，且其没有任何参数带有约束注解。然而，该整数参数的底层实现是 `@Max(121)`。当你调用接口方法时，你可能会提供一个 15 的值并认为它是没问题的，但实现类会抛出异常，因为触发了一个你不知道的约束。出于这个原因，禁止对接口中指定的方法实现进行约束注解。如果你对这样的方法进行注解，`Validator` 会在运行时抛出 `ConstraintViolationException`。这是 Hibernate Validator 注解处理器派上用场的另一个领域，因为它在编译期间就能检测到此类错误。

在使用约束注解进行方法验证时，你必须始终注解接口，而不是实现类。这确保了注解扩展了开发者所依赖的契约。如果开发者使用带有代码补全功能的智能 IDE，它会在他们使用每个方法时，告知他们这些额外的约束要求。

## 在方法参数上使用约束和递归验证

现在你已经有了一个 `Employee` 实体可以处理了，你需要一个服务来保存和检索 `Employee`。以下接口尽可能简单地定义了这样一个服务。

```java
public interface EmployeeService {
    public void saveEmployee(Employee employee);

    public Employee getEmployee(long id);

    public List<Employee> getAllEmployees();
}
```

考虑需要应用到 `getEmployee` 和 `saveEmployee` 参数的业务规则。在检索单个 `Employee` 时，你希望 ID 始终为正。为了指示这一点，请在 `id` 参数上标有 `@Min`。

```java
public Employee getEmployee(
    @Min(value = 1,
    message = "validate.employeesService.getEmployee(id)") long id
);
```

这足够简单；`Validator` 确保 ID 大于等于 1，并返回带有给定消息代码的验证错误。保存 `Employee` 稍微复杂一些。你希望确保员工不为空，同时也希望对 `Employee` 进行验证以满足其约束。要做到这一点，你只需要 `@NotNull` 约束和 `@Valid` 注解来指示递归验证。

```java
public void saveEmployee(
    @NotNull(message = "validate.employeesService.saveEmployee")
    @Valid Employee employee
)
```

现在，`Validator` 首先检查 `Employee` 是否为空，如果为空，它会返回带有给定消息代码的验证错误；如果不为空，`Validator` 将应用你之前在 `Employee` 属性上声明的所有约束，如果 `Employee` 无效，则返回相应的验证错误或多个错误。

## 验证方法的返回值

除了确保向方法提供值时接口的约束遵循适当规则外，你还希望保证实现遵循有关返回值的规则。`EmployeeService` 接口中的 `getAllEmployee` 方法永远不应该返回 `null`。如果没有 `Employee` 需要检索，它应该返回一个空列表。强制这一契约只需对方法标有 `@NotNull` 即可。

```java
@NotNull
public List<Employee> getAllEmployees();
```

注意，此约束没有提供消息代码。与方法约束不同（方法约束的状态通常由输入驱动），返回值表示实现问题，这是一种应该被解决的意外问题，而不是由用户来解决。这与检查异常和未检查异常之间的概念区别相似。检查异常应该是被预料并优雅处理的，而未检查异常通常是编程错误。你可能仅为返回值约束提供消息代码，但这是没有必要的。如果应用程序代码编写得当，此约束永远不会失败，因此创建本地化消息是浪费时间。

另外注意 `getEmployee` 方法没有标有 `@NotNull`；如果员工不存在，消费者希望得到一个 `null` 值。为了更清楚地表示允许返回 `null` 值，你可以使用 `@Nullable` 注解并用它装饰方法。此类注解本身不会在 `Validator` 中被强制执行（它只指示返回值可能为 `null`，而不是必须为 `null`），但它会改进你接口的契约。

> 注意：当然，你可以使用静态分析器在编译时强制这些限制。目前有多种工具可用（如 FindBugs 和 IntelliJ Annotations），它们提供了如 `@NotNull` 和 `@Nullable` 之类的注解，以及检查注解并确保字节码无法违反这些限制（或在使用 `@Nullable` 值之前进行检查）的注解处理器。此类工具可以确保你在编译时不违背契约，并可以减少可能的 bug 和运行时 `NullExceptions` 的数量。Java 8 曾讨论过创建静态的、启用代码分析的注解（`@NotNull`、`@Nullable` 和 `@ReadOnly`），但并未实现。

## 表明一个类适用于方法验证

现在既然你已经定义了处理器的方法验证契约，你需要告诉 Spring 的 `MethodValidationProcessor` 实际上对方法的执行应用验证。你这里有几个选择。你可以使用标准的 `@ValidateOnExecution` 注解或 Spring 的 `@Validated` 注解。每者都有其优缺点。`@ValidateOnExecution` 的粒度更细，因为你可以对单个方法进行注解，也可以对接口（应用于其所有方法）进行注解，而 `@Validated` 只能用在类或接口上。另一方面，你可以在方法参数上使用 `@Validated`，但不能在方法参数上使用 `@ValidateOnExecution`。

如果你想在方法执行期间指定应该应用的验证组，你可以在类上使用 `@ValidateOnExecution` 配合 `@javax.validation.GroupSequence` 运行。相比之下，`@Validated` 允许你直接在注解中指定验证组，而无需额外的注解，并且允许你在同一个控制器类中为不同的 MVC 控制器参数指定不同的组。（你无法通过 `@ValidateOnExecution` 和 `@GroupSequence` 实现这一点，因为 `@GroupSequence` 只能与 `@Valid` 配合。）遗憾的是，非 `@Validated` 的标准注解允许为同一个非控制器类中的方法参数指定不同的组。在任何情况下，`@Validated` 都更加简单。

```java
@Validated
public interface EmployeeService
{

}
```

如果你希望验证仅使用某个组或若干组中的约束，可以在 `@Validated` 注解中指定这些组。

```java
@Validated({Default.class,Group1.class})
public interface EmployeeService
{

}
```

你的应用程序需要 `EmployeeService` 的一个实现。接下来的默认实现包含了许多空方法，因为你不需要实际保存任何数据来证明验证组工作正常。请注意，该实现缺少任何与验证相关的注解。之所以这样做是因为接口包含了该契约。`getAllEmployees` 方法返回 `null`，这违反了契约。你将在稍后的章节中演示这一点。

```java
@Service
public class DefaultEmployeeService implements EmployeeService
{
    @Override
    public void saveEmployee(Employee employee)
    {
        // no-op
    }

    @Override
    public Employee getEmployee(long id)
    {
        return null;
    }

    @Override
    public List<Employee> getAllEmployees()
    {
        return null;
    }
}
```

# 在 Spring MVC 控制器中使用参数验证

除了验证服务、仓库和其他 Bean 的方法执行外，Spring 还可以验证 MVC 控制器处理方法中的指定参数。为了演示这一点，你需要一个 `EmployeeController` 和 `EmployeeForm`。`EmployeeForm` 缺少 `Employee` 中的许多字段，但这没关系。你并不是在尝试实际创建 `Employee`；你是在尝试演示 Bean 验证。`EmployeeForm` 同时使用了 `@NotNull` 和 `@Size`，因为某些人会表单字段发送空字符串，而另一些人则发送 `null` 值。

```java
public class EmployeeForm
{
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

控制器包含一个 `listEmployees` 处理方法，它响应索引请求并列出员工。正如你预期的，它会抛出 `ConstraintViolationException` 失败，因为默认的 `getAllEmployees` 方法返回 `null` 违反了契约。它还包含一个用于获取员工创建表单的简单处理方法。这些都是你见过并做过的标准操作。

```java
@Controller
public class EmployeeController
{
    @Inject EmployeeService employeesService;

    @RequestMapping(value = "/*", method = RequestMethod.GET)
    public String listEmployees(Map<String, Object> model)
{
        model.put("employees", this.employeesService.getAllEmployees());
        return "employee/list";
    }

    @RequestMapping(value = "/create", method = RequestMethod.GET)
    public String createEmployee(Map<String, Object> model)
{
        model.put("employeeForm", new EmployeeForm());
        return "employee/create";
    }
}
```

# 为方法验证配置 Bean

控制器的最后一个方法负责处理员工表单的提交。它包含了一些你来说可能并不熟悉的新内容。首先，方法参数被标记为 `@Valid`。通常情况下，如果验证失败，Spring 会抛出异常，但通过 `Errors` 参数，Spring 会将验证错误传递给方法而不是抛出异常。这允许你更优雅地处理这些错误。如果检测到错误，你可以将表单数据并返回到创建页面。



```java
@RequestMapping(value = "create", method = RequestMethod.POST)
public String createEmployee(Map<String, Object> model,
    @Valid EmployeeForm form, Errors errors) {
    if (errors.hasErrors()) {
        model.put("employeeForm", form);
        return "employee/create";
    }

    Employee employee = new Employee();
    employee.setFirstName(form.getFirstName());
    employee.setLastName(form.getLastName());
    employee.setMiddleName(form.getMiddleName());

    employeesService.saveEmployee(employee);
    return "redirect:/list";
}
```

# 向用户显示验证错误

在 `employee/create.jsp` 文件中，你可以显示验证错误。如下代码所示，显示了所有类型的错误：

```jsp
<h2><spring:message code="create.employee" /></h2>
<c:if test="${not empty validationErrors}">
<div class="errors">
  <ul>
    <c:forEach items="${validationErrors}" var="error">
      <li><c:out value="${error.defaultMessage}" /></li>
    </c:forEach>
  </ul>
</div>
</c:if>
<form method="post" modelAttribute="employeeForm">
  <label path="firstName"><spring:message code="form.firstName" /></label><br>
  <input path="firstName" />
  <form:errors path="firstName" cssClass="errors" /><br />
  <label path="middleName"><spring:message code="form.middleName" /></label><br>
  <input path="middleName" />
  <form:errors path="middleName" cssClass="errors" /><br />
  <label path="lastName"><spring:message code="form.lastName" /></label><br>
  <input path="lastName" />
  <form:errors path="lastName" cssClass="errors" /><br />
  <input type="submit" value="Submit" />
</form>
```

现在你已经有了用户界面，是时候对 Bean 验证进行测试了：

1. 编译应用程序并在 IDE 中启动 Tomcat。
2. 访问 `http://localhost:8080/portal/`，你应该会在浏览器中立即看到一个带有 `ConstraintViolationException` 的 HTTP 500 错误。这是预期的结果，意味着由于 `getAllEmployees` 方法返回了 `null`。
3. 现在访问 `http://localhost:8080/portal/create`，你应该看到员工创建表单。
4. 在不填写任何字段的情况下提交表单。你应该看到像图 16-1 那样的屏幕，其中姓和姓字段下方有错误。这意味着由于你没有提供这些值，你的对象未能通过验证。
5. 填写字段并再次提交表单。你应该看到一组不同的错误，如图 16-2 所示。这些错误是 Bean 验证拦截 `EmployeeService` 上的 `saveEmployee` 方法并确保你的员工符合所有业务规则的结果。

# 通过方法校验配置 Spring Beans | 465

![](img/4677f981a0e1067137bb55a122f8498d_500_0.png)

图 16-1

![](img/4677f981a0e1067137bb55a122f8498d_500_1.png)

图 16-2

# 编写自己的校验约束

此时，你可能已经注意到你的应用程序可以使用一些自定义约束。例如，在 `Employee` 中处处使用 `@NotNull` 并不足以检测空字符串。`Employee` 使用了 `@NotNull` 和 `@Size`，但这并不能检测只包含空格的字符串。你真正需要的是 `@NotBlank` 约束。此外，如果你需要多次使用电子邮件正则表达式，它会非常冗长，而 `@Email` 约束无疑会对这大有帮助。

幸运的是，在 Bean Validation 中编写自定义约束非常简单。位于 wrox.com 网站上的 Custom-Constraints 项目是 HR-Portal 项目的扩展，它添加了自定义约束 `@com.wrox.site.validation.NotBlank` 和 `@com.wrox.site.validation.Email`。现在我们先从 `@Email` 约束开始，信不由你，它更容易。

# 在自定义约束中继承其他约束

在 Bean Validation 中，约束可以相互继承。当然，这与类继承另一个类不同，因为你不能扩展注解。然而，按照惯例，约束注解通常包含一种 `Element.ANNOTATION_TYPE` 类型。当一个约束被注解标记时，`Validator`（校验器）会确定该注解定义是否被标记了任何其他约束。如果是，它会将所有额外的约束与它被注解的定义的逻辑结合。如果由于某种原因，你需要创建一个无法被继承的约束，你只需要从原始约束（如果有）中省略 `ElementType.ANNOTATION_TYPE`，将其合并到一个单一复合约束中。从这个意义上来说，来看 `@Email` 的细节。

```java
@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(Retention.RUNTIME)
@Documented
@Constraint(validatedBy = {})
@Pattern(regexp = "^[a-z0-9#$%&'*+\-=?^_`{|}~]+\@[a-z0-9#$%&'*+\-=?^_`{|}~]*|\\.)+[a-z0-9-]+\.)+[a-zA-Z]{2,}", flags = Pattern.CASE_INSENSITIVE)
public @interface Email {
	String message() default "@com.wrox.site.validation.Email message";
	Class<?>[] groups() default {};
	Class<? extends Payload>[] payload() default {};
}

@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(Retention.RUNTIME)
@Documented
static @interface List {
	Email[] value();
}
```

这里面有很多内容，所以请逐行查看，从注解开始：

- `@Target` — 该注解表示此注解可以放置在哪些语言特性上。这些值非常标准，应该适用于大多数约束。
- `@Retention` — 表明该注解将在运行时保留。否则，Bean Validation 将无法检测到它。
- `@Documented` — 这意味着标记了此注解的目标将指示它的存在。这在 IDE 中编程时特别有用，因为它让契约更加可见。
- `@Constraint` — 这是必须的：它表示此注解继承了 Bean Validation，因此所有定义都将带上此注解。然而，你的约束会被忽略。`@Constraint` 还表示 `ConstraintValidator` 的实现或注解负责校验你的约束。然而，在任何情况下 `ConstraintValidator` 并不都是必须的。
- `@Pattern` — 这是另一个约束，表示它继承了用 `@Pattern` 声明的约束。这与之前看到的正则表达式相同，但你不需要在每次使用时都重复该正则。你只需要使用 `@Email` 注解即可。
- `@ReportAsSingleViolation` — 表明复合约束应该被视为整体，并使用 `@Email` 的消息而不是 `@Pattern` 的消息。你创建一个不使用 `@ReportAsSingleViolation` 而继承其他约束的约束的情况是非常罕见的。

注解内部有三个属性：`message`、`groups` 和 `payload`。这些是所有约束中必须存在的标准属性。缺少其中一个或多个，`@Email` 将导致 `ConstraintDefinitionException`。`List` 注解像 Bean Validation 一样，定义了在目标上指定多个约束的方法。

# 创建约束校验器 (Constraint Validator)

`@NotBlank` 约束看起来与 `@Email` 几乎相同。在大多数方面，它具有相同的注解、属性和特征。它不是被标记为 `@Pattern`，而是被标记为 `@NotNull`。在这种情况下，`@NotNull` 意味着非空，因此继承 `@NotNull` 约束来实现此。如果你需要定义不能为空但可以是空白字符串的目标，只需从此注解中移除 `@NotNull`。

```java
@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(Retention.RUNTIME)
@Documented
@Constraint(validatedBy = {NotBlankValidator.class})
@NotNull
@ReportAsSingleViolation
public interface NotBean {
	String message() default "{com.wrox.site.validation.NotBlank.message}";
	Class<?>[] groups() default {};
	Class<? extends Payload>[] payload() default {};
}
```

```java
@Target({ElementType.METHOD, ElementType.FIELD, ElementType.ANNOTATION_TYPE,
ElementType.CONSTRUCTOR, ElementType.PARAMETER})
@Retention(Retention.RUNTIME)
@Documented
@interface List {
    NotBlank value();
}
```

与 `@Email` 不同，它不能继承其所有的功能。它需要一个 `ConstraintValidator` 来测试值是否为空。以下在 `@Constraint` 注解中声明的 `NotBlankValidator` 完成此此。

```java
public class NotBlankValidator implements ConstraintValidator<NotBlank, CharSequence> {
    @Override
    public void initialize(NotBlank annotation) {}

    @Override
    public boolean isValid(CharSequence value, ConstraintValidatorContext context) {
        if (value instanceof String)
            return ((String)value).trim().length() > 0;
        return value.toString().trim().length() > 0;
    }
}
```

有了新约束，查看 `Employee` 和 `EmployeeForm`。我们已经将它们的大部分 `@NotNull` 约束替换为 `@NotBlank`，`EmployeeForm` 不再使用 `@Size`。`Employee` 中的 `email` 字段更改为 `@Email`，并在 `EmployeeForm` 中添加了另一个字段，你可以看到电子邮件校验。

```java
@NotNull(message = "validate.email")
@Email(message = "validate.email")
private String email;
```

1. 编译并启动应用程序，访问 `http://localhost:8080/portal/create`。
2. 在所有字段中留空并提交表单，看到 `@NotBlank` 起作用。
3. 现在输入无效的电子邮件地址（例如没有 `@` 符号的），提交表单，`Email` 字段仍被标记为错误。
4. 输入有效的电子邮件地址并再次提交表单，校验通过，显示业务层错误。

# 理解约束校验器的生命周期

`@NotBlank` 和它的 `NotBlankValidator` 当然是非常简单的。根据约束类型、值类型和约束属性，你可以在校验器中执行高级任务。要理解你可以做什么，首先需要理解 `ConstraintValidator` 的生命周期。

当 `Validator` 遇到字段、参数或其他约束上的注解时，它首先检查该约束是否标记了其他约束。如果是，它会首先处理那些。如果不是，只要通过了所有继承的约束，值就被认为是有效的。如果是，`ConstraintValidator` 与目标类型最匹配。例如，你可能创建一个支持 `CharSequence` 和 `Integer` 的约束。对于这样的约束，你可能需要不同的 `ConstraintValidator`：

```java
public class IntValidator implements ConstraintValidator<MyConstraint, Integer> { ... }

public class StringValidator implements ConstraintValidator<MyConstraint, CharSequence> { ... }

@Constraint(validatedBy = {IntValidator.class, StringValidator.class})
```

在遇到 `ConstraintValidator` 后，`Validator` 实例化并调用 `ConstraintValidator` 的 `initialize` 方法。该方法每次使用约束时调用一次。如果你有一个 10 个字段的类，其中 5 个使用约束，就会创建并缓存 5 个 `ConstraintValidator` 实例；每次都使用同一个实例。`initialize` 方法允许你从特定的注解实例获取值（例如 `@Size` 注解的 `min` 和 `max` 属性）。这样，你只需要决定一次约束如何校验目标值，从而提高执行 `isValid` 方法的效率。

在 `initialize` 返回后，`Validator` 调用 `isValid`，之后每次校验字段、参数或其他目标时，它都是 `isValid` 的。

# 在客户支持应用程序中集成验证

Customer-Support-v13 项目可以从 wrox.com 代码下载站点下载，它演示了 Bean Validation 1.1 更深层次的集成。它并没有真正使用任何你在在本章中尚未见过的内容，但它是一个更稳定的应用程序，将验证逻辑应用于表单、POJO 和 Bean 中。`TicketController.TicketForm` 和 `AuthenticationController.LoginForm` 现在使用约束注解来确保表单字段不为空，且控制器中相应的方法使用 `Errors` 对象和 `ConstraintViolationException` 异常来检测错误并向用户报告错误。



```java
@RequestMapping(value = "create", method = RequestMethod.POST)
public ModelAndView create(Principal principal, @Valid TicketForm form, Errors errors, Map<String, Object> model)
    throws ConstraintViolationException
{
    if (errors.hasErrors()) {
        return new ModelAndView("ticket/add");
    }
    try {
        this.ticketService.save(ticket);
    }
    catch (ConstraintViolationException e) {
        model.put("validationError", e.getConstraintViolations());
        return new ModelAndView("ticket/add");
    }
}

@RequestMapping(value = "login", method = RequestMethod.POST)
public ModelAndView login(Map<String, Object> model, HttpSession session, HttpServletRequest request, @Valid LoginForm form, Errors errors)
{
    if (UserPrincipal.getPrincipal(session) != null) {
        return this.getTicketRedirect();
    }

    if (errors.hasErrors()) {
        form.setPassword(null);
        return new ModelAndView("login");
    }

    Principal principal;
    try {
        principal = this.authenticationService.authenticate(
            form.getUsername(), form.getPassword())
    }
}
```

```java
catch (ConstraintViolationException e) {
    form.setPassword(null);
    model.put("validationErrors", e.getConstraintViolations());
    return new ModelAndView("login");
}
```

值得注意的一个有趣点是，`Attachment` 具有约束，以确保名称和内容不为空，且附件内容至少包含 1 字节。`Ticket` 中的附件列表使用 `@Valid` 注解来确保对票单的所有附件进行递归验证。

```java
public class Attachment {
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
public class Ticket {
    // other fields

    @Valid
    private Map<String, Attachment> attachments = new LinkedHashMap<>();

    // mutators and accessors
}
```

为了确保 `Tickets` 在保存之前是有效的，`TicketService` 使用了 `@Validated` 并且对其所有方法都包含约束，以执行接口合约。

```java
@Validated
public interface TicketService {
    @NotNull
    List<Ticket> getAllTickets();
    Ticket getTicket(
        @Min(value = 1L, message = "{validate.ticketService.getTicket.id}")
        long id
    );
    void save(@NotNull(message = "{validate.ticketService.save.ticket}")
        @Valid Ticket ticket);
}
```

同样，`AuthenticationService` 也通过了 `@Validated`，并带有约束以确保用户名和密码不能为空。

```java
@Validated
public interface AuthenticationService {
    Principal authenticate(
        @NotBlank(message = "{*validate.authenticate.username}")
        String username,
        @NotBlank(message = "{*validate.authenticate.password}")
        String password
    );
}
```

根据这些说明，制作并编译该项目，从你的 IDE 启动 Tomcat，然后访问 `http://localhost:8080/support/`。你会注意到验证现在在登录屏幕和票单创建屏幕上生效了，你仍然可以登录并创建票单。

## 总结

在本章中，你学习了 Bean Validation 1.1（取代 JSR 303 的 JSR 349）、Hibernate Validator 5.1，以及如何在 Spring Framework 中结合使用 Bean Validation 和 Hibernate Validator。你探索了在 Spring 容器中配置 Bean Validation 的各个方面，以及如何为你需要验证的 POJO 和表单对象添加约束注解。你还学习了如何对 Spring Bean 进行限定以实现自动方法验证，并在 Spring MVC 控制器处理方法中触发表单验证。最后，你尝试了创建自定义约束，并领略了通过自定义 Bean Validation 约束可以做的许多事情。

在下一章中，你将探索作为 RESTful 服务的 Spring MVC 控制器，并学习涉及许多细节，包括错误处理和 HTTP 响应状态码。

# 17

# 创建 RESTful 和 SOAP Web 服务

## 本章

- 什么是 Web 服务？
- 如何使用 Spring MVC 配置 RESTful Web 服务？
- 如何测试你的 Web 服务端点
- 如何利用 Spring Web Services 处理 SOAP

## 本章的 WROX.COM 代码下载

你可以在 `http://www.wrox.com/go/projectavaforewebapps` 的 "Download Code" 标签页找到本章的 wrox.com 代码下载。本章的代码分为以下示例：

- Web-Service Project
- Customer-Support-v14 Project

## 本章的新 MAVEN 依赖

除了之前章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-aop</artifactId>
  <version>4.0.2.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

## 理解 Web 服务

为你的应用程序创建 Web 服务是你未来不可避免要面对的任务，即使你现在还没有这样做。这是因为 Web 服务为非人类客户端与应用程序的交互提供了方式。通常仍然有人类与 Web 服务交互，但在这一阶段并不重要。（在第 28 章的“创建 OAuth ”节中，你将使用 Spring 创建 Web 服务客户端）。

通常为了创建 Web 服务，你需要允许非人类客户端编程地使用甚至发现你的资源。随着移动应用程序变得越来越强大，传统的浏览器体验日益过时，这变得越来越重要。移动应用程序依赖 应用程序来执行任务，仅在移动设备上使用用户界面。这使得拥有许多设备（移动或其他）的人能够在设备之间共享体验。

今天，应用程序开发者选择仅创建 Web 服务以及与这些服务直接交互的单页 JavaScript 应用。这种模型将成为规则而非例外，因为它减少了应用程序开发者的工作量，同时为界面开发者提供了跨平台优雅应用程序的能力。

> Web 服务是一种支持网络上可操作机器间交互的软件系统。它具有用机器处理格式描述的接口（WSDL）。其他服务按照其描述的方式，使用 SOAP 消息（通常通过 HTTP 结合其他 Web 相关标准进行 XML 序列）与 Web 服务交互。

本书并不争论称某些技术为 Web 优劣。相反，它遵循 W3C 引用第一句话的精神。在本书的上下文中，Web 服务是指任何使用可操作的机器处理格式支持计算机网络上机器间交互的软件系统。这包含了 SOAP 和 RESTful Web 服务，以及独立创建的其他 Web 服务技术。

## 起初是 SOAP

不，我们并不是在讨论你用来洗手和洗澡的物质。事实上，有些开发者声称在使用 SOAP 之后感觉更脏了，而不是更干净了。但我离题了。SOAP 原名为简单对象访问协议（Simple Object Access Protocol），是一种使用 XML 消息形式结构化数据进行机器间交互的协议。在协议的 1.2 版本（首次由 W3C 采用）中，缩写被去除了，SOAP 独立存在。广义上来说，SOAP 并不是 Web 开始，因为 XML-RPC 等技术在 SOAP 出现很久就已经存在。然而，SOAP 的采用被认为是 Web 服务在企业中开始变得流行的转折点。

SOAP 具有推动其流行的三个主要特征：

- 它具有**可扩展性**，因为它很容易在基础协议之上添加其他功能（如安全性）。
- 它具有**中立性**，因为你使用何种机制并不重要——HTTP、JMS、AMQP、SMTP、TCP 等都是可选的。
- 它具有**独立性**，因为 SOAP 不依赖或背书任何特定的编程模型。

然而，SOAP 确实鼓励“契约优先”的设计。Web 服务描述语言（WSDL）技术定义了一种建立约的方法，用户应该遵守而 Web 服务也承诺遵守。它定义了特定位置可用的 Web 服务的位置，以及这些服务请求和响应的数据格式。契约通常使用 XSD（有时称为 XML 架构定义）编写，通常在编写任何 Web 服务代码之前创建，而 Web 服务是为了遵循该契约而创建的。这类似于测试驱动开发的概念——即在编写应用程序之前编写单元测试和应用测试，然后编写应用程序以通过测试——与完全不同的“契约后”设计形成鲜明对比，后者是先创建 Web 服务，然后编写契约来匹配它。

契约优先设计有其优点，定义用户需求并编写满足这些需求的应用程序总是最好的，而不是先写一个应用程序再去弄它是否满足了用户需求。但显然，明确定义用户需求和编写 WSDL 是两回事，用自然语言显式地定义契约、编写符合要求的 Web 服务代码，然后使用 XML 工具自动生成相应的 WSDL 要容易得多。在本书中，你将采用这种方法，从而避免手动处理 WSDL 文件。

SOAP 并不是一个简单的协议。每条消息（请求或响应）都以一个名为 SOAP 封（Envelope）的根元素开始。关于消息的所有信息都包含在这个封中。该封包含一个可选的 SOAP 头部（Header）（不要与 HTTP Header混淆），其中包含特定的应用程序信息，如身份验证详情。封内部还包含强制性的 SOAP 实体（Body），它包含请求或响应的指令和数据。最后，响应的封还可以有一个可选的 SOAP 故障（Fault），用于描述处理请求期间发生的任何错误。

这些元素的细节很多，很大程度上由 WSDL 定义。编写和处理 WSDL 文档有时是一项复杂且混乱的任务，你在过程中能越干净地集成自动化就越好。更糟糕的是，XML 是已知最冗长且最消耗带宽和处理资源的数据格式之一。尽管 SOAP 可能非常有用且强大，但幸运的是它并不是唯一的选择。

## RESTful Web 服务提供更简单的方法

表述状态转移（REST）是一种 Web 服务概念，很多方面与 SOAP 相似。该架构由服务器和客户端组成。客户端通过请求（获取或更改资源状态的请求）进行状态转换，服务器处理请求并检索相应的属性。资源可以是客户端和服务器理解的任何概念，并以约定的表示形式传输。REST 不定义或指定资源类型或表示形式。资源可以是想象中的任何类型的数据。它们的表示形式可以是纯文本、HTML、XML、YAML、JSON 或任何客户端和服务器都能理解的格式。REST 系统使用指示资源类型的 URL、使用指示媒体类型（MIME）即资源表示形式的动词运行，如果这让你想起了 HTTP 和万维网（World Web），那是自然的，而且这并非巧合。Roy Fielding 是 HTTP 1.0 和 1.1 的作者之一，他在 2000 年的博士论文中定义了 RESTful 状态转移。万维网从本质上说是存在的最大的 REST 系统。

RESTful 服务背后的一个主要原理是，对资源不需要执行许多主要操作。这些操作通常被称为 CRUD 操作：创建（Create）、读取（Read）、更新（Update）和删除（Delete）。HTTP 规范中的方法可以轻松映射到这些操作：POST、GET、PUT 和 DELETE。SOAP 使用封元素来描述动作（要执行的操作），而 REST 依赖 HTTP 协议来提供封。SOAP 还使用封来标识被操作的资源，而 REST 则依赖 HTTP URL。

在 RESTful Web 服务中，Content-Type 头部告知服务器请求体的表示形式，或者通过文件扩展名请求特定的响应，Content-Type 头部告知客户端响应的表示形式。有了这些信息，RESTful 服务可以使用 HTTP 这种方式作为封。由于这些原因，RESTful 服务 就可以使用 HTTP 资源。在这种情况下，RESTful 服务可以使用 HTTP 发现资源。RESTful 服务是基于 HTTP 的，通过 URL、动词和媒体类型来发现资源。通过 HTTP 这种方式，RESTful 服务是完全独立于协议的。（RESTful 服务可以使用 HTTP 这种方式作为封。）

## 理解 Web 服务

RESTful Web 服务的一个核心卖点在于缺乏 WSDL。明确地说，这并不意味着 RESTful 服务是无契约的。RESTful 服务甚至可以公开发布 XML Schema (XSD) 或 JSON Schema。由于这些原因，Spring 框架支持了 REST。在本章中，你将主要探索 Web 服务的构建。

## 理解可发现性

RESTful 服务的另一个重要特性是其可发现性。通过 URL 和 OPTIONS HTTP 方法，客户端可以在无需访问契约的情况下发现 Web 服务的资源，并在每个资源处，客户端可以发现该资源的可用操作。许多 RESTful 服务不支持自动可发现性。万维网是可发现的。作为用户，你可以打开浏览器并进入任何主页。从首页，你可以通过链接发现网站内的其他页面。点击链接会带你进入新页面。但在不需要预先知道内容的情况下，你可以在那里找到资源并与其进行交互。

这种约束是施加在应用架构上的。REST 客户端应该能够在预先不知道 Web 服务可用资源的情况下使用。这种概念被称为超媒体作为应用引擎（HATEOAS），它结合超文本（XML、YAML、JSON 或你选择的任何格式）和链接告知客户端 Web 服务的结构。例如，对服务基础 URL 的 GET 请求和响应可能如下：

```
> GET /services/Rest/ HTTP/1.1
> Accept: application/json

200 OK
- Content-Type: application/hal+json
{
  "links": {
    "self": {"href": "http://example.com/services/Rest"},
    "account": {"href": "http://example.com/services/Rest/account"},
    "order": {"href": "http://example.com/services/Rest/order"}
  }
}
```

有了这些数据，客户端现在知道了 Web 服务可用的资源。如果它想进一步探索账户，它有两种选择。首先，它可以对资源发送 GET 请求。这被称为集合请求，或对集合 URI 的请求，并返回该类型的每个资源。

```
> GET /services/Rest/account HTTP/1.1
> Accept: application/json

< 200 OK
< Content-Type: application/json
< {
{
  "id": 1075,
  "name": "John Smith",
}
{
  "id": 1076,
  "name": "Adam Green",
}
}
```



这有几个缺点。首先，这个集合可能非常大——甚至是海量的。想象一下 Amazon.com 的 Web 服务返回每一个产品，你就能很快理解问题所在。显而易见的解决方案是对资源进行分页（`paging`），在大多数情况下，需要分页来避免噩梦般的场景。（在下一节中，你将在实现 `SPRING REST` 控制器时详细地探索分页。）另一个问题是，此列表包含资源数据的链接，但不包含资源本身。一种方案是返回链接列表，但这会导致使用集合请求在为终端用户显示资源列表时变得毫无意义。因此，许多 Web 服务在集合响应中使用属性和链接的组合。

客户端可以采取的进一步探索账户资源的另一个操作是向该资源发送 `OPTIONS` 请求。

```
> OPTIONS /services/Rest/account HTTP/1.1
> Accept: application/json

< 200 OK
< Allow: OPTIONS, HEAD, GET, POST, PUT, PATCH, DELETE
< {
  "GET": "Get a resource or resources",
  "resourceTemplate": "http://example.net/services/Rest/account/{id}",
  "parameters": {
    "$select": {
      "type": "array/string",
      "description": "The properties to be returned for each resource."
    },
    "$filter..."
  },
  "POST": ...
}
```

# 理解 Web 服务

`OPTIONS` 响应可能特别强大。它不仅可以告诉客户端某种资源类型支持哪些操作，还可以根据客户端的权限进行过滤。例如，如果客户端有查看权限但没有创建、更新或删除的权限，那么 `Allow` 响应头的值将是 `OPTIONS, HEAD, GET`。此外，根据多个因素（包括权限），不同的单个资源可能可以使用不同的操作，如下所示两个请求及其响应所示：

```
> OPTIONS /services/Rest/account/1075 HTTP/1.1
> Accept: application/json

< 200 OK
< Allow: OPTIONS, HEAD, GET, PUT, PATCH, DELETE
< ...
```

```
> OPTIONS /services/Rest/account/1076 HTTP/1.1
> Accept: application/json

< 200 OK
< Allow: OPTIONS, HEAD, GET
< ...
```

RESTful Web 服务中可发现性（`discoverability`）的主要问题在于，对于发现资源的内容没有统一的单一标准。在超文本应用语言（`HAL`，它是多种新兴标准之一）的响应 `JSON` 表示中，虽然有链接，但 `HAL` 绝非唯一。账户的集合请求仅仅是标准的 `JSON` 集合，仅此而已。而 `OPTIONS` 响应中的 `Allow` 头是标准且通用的，但响应体完全是自定义的，许多厂商都是这样做的。

由于缺乏通用标准，可能导致很少厂商实现可发现性。你需要评估你的需求和当时的技术，以确定要使用的最佳可发现标准。你甚至可以决定不支持可发现性，并告诉客户端阅读说明手册，这没有关系。好消息是，在 `Spring Framework` 中实现 RESTful Web 服务并不依赖于资源或表示，因此采用某种标准而非另一种标准不会改变你在本章中学习的技巧。

# 使用 URL、HTTP 方法和 HTTP 状态码

重读时，RESTful Web 服务使用 `URL` 来标识请求的资源，使用 `HTTP` 来确定想要的操作。它们还使用 `HTTP` 状态码显示请求的结果。不同的状态码适用于不同类型的请求。然而，有几个状态码是通用的，适用于所有类型的请求：

- `400 Bad Request` 表示客户端发出的请求不受或无法被识别。这通常是因为没有遵循正确的请求语法。例如，如果在 `POST` 或 `PUT` 请求中某个必填字段为空，将导致 `400 Bad Request` 响应。响应体应在表示格式中包含关于请求错误原因的信息。

- `401 Unauthorized` 信号表示访问资源或执行请求的状态转换之前需要进行身份验证和授权。响应的内容根据所使用的身份验证协议（如 `OAuth`）而异。

- `403 Forbidden` 表示客户端已通过身份验证，但没有权限访问资源或执行请求的状态转换。根据所使用的身份验证协议，使用更多请求权限重新进行身份验证可能会解决此冲突。

- `404 Not Found` 简单来说，它告诉客户端资源不存在。它永远不应该用来表示资源存在但状态转换简单不支持或被不允许。那是 `405 Method Not Allowed` 和 `403 Forbidden` 的作用。

- `405 Method Not Allowed` 表示请求的状态转换（`HTTP` 方法）不受支持。它永远不应该用来表示客户端没有执行状态转换的权限；`403 Forbidden` 留给了该用途。

- `406 Not Accept` 表示 `Accept` 头中请求的表示格式不受服务器支持。例如，客户端可能请求了……

- `415 Unsupported Media` 表示 `Content-Type` 头中请求的表示格式不受服务器支持。

- `500 Internal Server Error` 表示处理请求时发生错误。

本节的其余部分将涵盖 `HTTP` 方法的语法和语义。

# OPTIONS

如所示，`OPTIONS` 是可用的发现机制之一。当向资源发出请求时，服务器必须返回 `Allow` 头。这些要求存在一些例外：

- 如果资源不存在，服务器应返回 `404 Not Found` 而不是 `200 OK`。

- 如果资源在未身份验证的情况下不允许任何方法，服务器应返回 `401 Unauthorized`。

- 如果客户端已验证但没有权限在资源上执行任何操作，服务器应返回 `403 Forbidden`。

`OPTIONS` 请求被认为是无副作用（`nullipotent`）的；它们在任何情况下都不会导致任何资源的修改。

> 注意某些 Web 服务启用了跨资源共享（`CORS`）。这种特殊的、较新的协议允许授权的浏览器应用程序使用一组特殊的头部绕过 `AJAX` 同源策略。如果你希望你的服务能被 `JavaScript` 应用程序直接访问，你需要启用 `CORS`。这部分的完整细节不在本书范围内。启用 `CORS` 的 Web 服务必须支持对账户的 `OPTIONS` 请求，并在响应 `OPTIONS` 请求时包含 `Access-Control-Allow-Methods` 头，其内容与 `Allow` 头相同。

# HEAD 和 GET

每当资源支持并允许 `GET` 时，`HEAD` 也必须被支持并允许。`GET` 和 `HEAD` 的唯一区别是 `HEAD` 响应没有体。`HEAD` 响应必须包含指示 `GET` 响应内容的头部。`GET` 请求用于获取资源或资源。如 `/services/Rest/account` 的 `URL` 表示客户端想要获取所有账户或过滤后的账户列表。通常，过滤、排序和分页指令包含查询字符串参数中。

请求 `URL` 如 `/services/Rest/account/1075` 表示客户端想要获取具有唯一标识符的单个账户。某些厂商还支持关系型 `URL`，例如 `/services/Rest/account/1075/order` 和 `/services/Rest/account/1075/order/1522`，分别表示请求账户 1075 的订单列表（可能经过过滤）以及属于账户 1075 的订单 1522。理论上，这种递归可以一直持续到 `URL` 长度限制为止。`/services/Rest/account/1075/order/1522/item/12` 可以返回账户订单中的某个特定行项目。

> 注意：在此处演示的 `URL` 中，账户和订单路径段使用的是单数形式。这仅仅是一种选择。`URL` 也可以包含复数形式的账户和订单段。这取决于你，你应该选择一种并在你的所有资源中保持一致。通常情况下，使用单数路径段可以获得更短的 `URL`，在需要时可以在查询字符串中包含更多内容。

对于成功的 `GET` 和 `HEAD` 请求，服务器应返回 `200 OK`，并在 `GET` 请求的响应体中使用约定的（或默认的）表示包含所请求的资源。

`GET` 和 `HEAD` 请求都是幂等的（`nullipotent`），不应对服务器上的资源产生任何副作用。

## POST

`POST` 请求用于在服务器上创建新资源。`POST` 请求始终应该指向一个集合 `URI` (`/services/Rest/account`)，但它也可以指向子集合 `URI` (`/services/Rest/account/1075/order`)。对单个元素 `URI` (`/services/Rest/account/1075`) 发出的 `POST` 请求应该导致 `405 Method Not Allowed`。在成功的 `POST` 请求中，服务器会创建请求的资源并返回 `201 Created`。响应中应包含一个 `Location` 请求头，指向新创建资源的 `URL`。

例如，向 `/services/Rest/account` 发出的创建新账户的 `POST` 请求可能会在 `Location` 请求头中返回 `http://www.example.com/services/Rest/account/9156`。响应体应该是被创建的资源，因为对 `Location` 请求头中的 `URL` 发起 `GET` 请求时将返回该资源。

`POST` 请求是非幂等的（非安全的——请求确实会导致一个或多个资源的修改）且非幂等性的（发送相同的 `POST` 请求会导致创建多个相同的资源）。

## PUT

`PUT` 请求用于替换服务器上的资源。正因如此，`PUT` 请求用于更新现有资源。与 `POST` 请求不同，`PUT` 请求绝不会用于更新集合 `URI`。它们被用于单个元素 `URI` (`/services/Rest/account/1075`, `/services/Rest/account/1075/order/5122`)。对集合 `URI` 或子集合 `URI` 发出的 `PUT` 请求应该导致 `405 Method Not Allowed` 响应。成功 `PUT` 请求的响应应返回 `204 No Content`，且其正文应为空。

`PUT` 请求显然是非幂等的。然而，它们应该是幂等的。两个或多个连续的相同的 `PUT` 请求除了第一个 `PUT` 请求产生的副作用外，不应有其他副作用。

这可能面临挑战的一个领域是，如果更新的资源包含“最后修改”时间戳或版本。根据幂等性限制，只有当底层实体确实发生变化时，服务器才应对 `PUT` 请求更新资源的时间戳和/或版本号。这种要求的实现可能非常有挑战性，因此许多供应商以部分幂等的方式实现 `PUT`，并说明在相同的 `PUT` 请求中时间戳和版本仍然会被更新。

## PATCH

`PATCH` 请求在目的和语义上与 `PUT` 请求非常相似。`PATCH` 是一个相对新的 `HTTP` 方法，仅在过去几年中被添加。它不是原始 `HTTP/1.1` 规范的一部分。`PATCH` 请求像 `PUT` 请求一样，旨在更新单个元素的资源。然而，`PATCH` 请求仅表示对资源进行部分更新，而不是完全替换资源。

例如，向 `/service/Rest/account/1075/order/5122` 发出的 `PATCH` 请求仅包含 `shippingaddress` 属性，那么订单中的 `shippingaddress` 将会被更新。其他属性将保持不变（时间戳和版本号除可能除外）。这是一个非常强大的方法，但实现起来也很有挑战性。为了支持 `PATCH`，你的应用程序必须在请求中接受一组非常灵活的属性，然后仅处理请求中存在的资源。你不能使用空值检查，因为 `PATCH` 可能会将某个属性值设置为 `null`。

成功 `PATCH` 请求的响应应为 `200 OK` 或 `204 No Content`。你可以决定在响应体中返回完整的更新后的实体还是不返回内容。如果支持 `PATCH`，你的应用程序必须在请求中接受一组非常灵活的属性，然后仅处理请求中存在的资源。如果支持 `PATCH` 但 `PATCH` 不支持，服务器应返回 `422 Unprocessable Entity`。如果预处理条件失败，服务器应返回 `409 Conflict`。

## DELETE

`DELETE` 请求用于从服务器上删除资源。`DELETE` 请求像 `PUT` 请求一样是幂等的。两个或多个连续的相同的 `DELETE` 请求除了第一个请求外，不应有其他副作用。如果资源已经被删除，服务器可能会返回 `404 Not Found` 或 `204 No Content`。对集合 `URI` 或子集合 `URI` 发出的 `DELETE` 请求应该导致 `405 Method Not Allowed` 响应。

# 使用 Spring MVC 配置 RESTful 服务

RESTful 服务伟大之处之一是它们在 `Spring MVC` 中工作非常整洁。从技术上讲，你不需要做任何特殊操作来创建 RESTful 服务。你只需要创建一个 `Controller`，添加一些 `@RequestMapping` 方法并开始运行。有许多消息转换器用于处理请求和响应格式；还有一些必要的 `ViewNameResolver`。既然如此，逻辑上应该创建独立的上下文。

在本节中，你将探索配置这些独立的上下文。你首先学习如何分离 Web 和 REST 控制器以防止它们交叉，然后创建另一个应用程序。你还查看了如何在服务中正确处理错误。最后，你创建一个 REST 控制器并使用 `@RequestMapping` 进行发现和状态表示。你可以参考下载的项目进行练习。

## 使用类型注解分离控制器

回顾第 12 和第 13 章，`@Controller` 注解有两个用途。作为 `@Component`，它负责将你的控制器标记为 `Spring` 管理的 `Bean`，以便实例化和依赖注入。在 `Spring MVC` 的上下文中，它还用于标记扫描 `@RequestMapping` 的 `Bean`。没有标记 `@Controller` 的 `Bean` 无法响应。因此，你的 REST 控制器与 Web 控制器一样，必须标记为 `@Controller`。

请求映射（`request mapping`）很好地解决了控制器的拆分问题。考虑到这一点，请查看 `Web-Service` 项目中的 `@com.wrox.config.annotation.WebController` 和 `@com.wrox.config.annotation.RestEndpoint` 注解。

```java
@Target({ ElementType.TYPE })
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Controller
public @interface WebController
{
    String value() default ""
}
@Target({ ElementType.TYPE })
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Controller
public @interface RestEndpoint
{
    String value() default ""
}
```

这些注解在实际上是完全相同的，但它们的语义含义有重要的区别。它们都表示目标豆（`bean`）是处理合格请求的控制器，但 `@WebController` 标记用于传统 Web 请求的控制器，而 `@RestEndpoint` 则表示 RESTful Web 服务。孤立的 `value` 属性在此处的作用与其他类型化注解（`stereotype annotations`）中的相同：它用于指定一个可以覆盖 `bean` 命名模式的 `bean` 名称。

## 分离 Web 和 REST 上下文

单独来说，这些自定义注解对你没有帮助。你可以将它们放置在控制器和端点上，但你在之前的章节中使用的 `ServletContext` 类会在它对 `@Controller` 的组件扫描中全部捕获到它们。因此，你需要更新此配置以仅扫描你的 `@WebController` 注解。为了消除其歧义，将此类重命名为 `HttpContext` 也是一个好主意。

```java
@Configuration
@EnableWebMvc
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(WebController.class)
)
public class HttpServletContextConfiguration extends WebMvcConfigurerAdapter
{
    ...
}
```

该类中的代码与之前的章节相比没有任何变化。你所做的只是了属于此应用上下文的类型化注解类型。现在你需要创建一个新的应用上下文——一个寻找 `@RestEndpoint` 且更适合 RESTful Web 服务的上下文。列表 17-1 中的 `HttpServletConfiguration` 正是这么做的。

### 列表 17-1：RestServletContextConfiguration.java



```java
@Configuration
@EnableWebMvc
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultScan = false,
    includeFilters = @ComponentScan.Filter(RestEndpoint.class)
)
public class RestServletContextConfiguration extends MvcConfigurerAdapter {
    @Inject ObjectMapper objectMapper;
    @Inject Marshaller marshaller;
    @Inject Unmarshaller unmarshaller;
    @Inject SpringValidatorAdapter validator;

    @Override
    public void configureMessageConverters(List<HttpMessageConverter<?>> converters) {
        converters.add(new SourceHttpMessageConverter());

        MarshallingHttpMessageConverter xmlConverter = new MarshallingHttpMessageConverter();
        xmlConverter.getSupportedMediaTypes(Arrays.asList(
            new MediaType("application", "xml*"),
            new MediaType("text", "xml*")
        ));
        xmlConverter.setMarshaller(marshaller);
        xmlConverter.setUnmarshaller(unmarshaller);
        converters.add(xmlConverter);

        MappingJackson2HttpMessageConverter jsonConverter = new MappingJackson2HttpMessageConverter();
        jsonConverter.getSupportedMediaTypes(Arrays.asList(
            new MediaType("application", "**"),
            new MediaType("text", "json*")
        ));
        jsonConverter.setObjectMapper(this.objectMapper);
        converters.add(jsonConverter);
    }

    @Override
    public void configureContentNegotiation(ContentNegotiationConfigurer config) {
        config.favorPathExtension(false).favorParameter(false)
            .ignoreAcceptHeader(false)
            .defaultContentType(MediaType.APPLICATION_JSON);
    }

    @Override
    public Validator getValidator() {
        return this.validator;
    }

    @Bean
    public LocaleResolver localeResolver() {
        return new AcceptHeaderLocaleResolver();
    }
}
```

该类与 `WebServletContextConfiguration` 在多个方面非常相似，但它也有许多重要的区别。它缺乏任何视图解析或多部分支持，因为这些功能根本不需要。它有更少转换器，专注于 JSON 和 XML 的序列化和反序列化任务，而忽略了字符串、表单和字节数组。`configureContentNegotiation` 方法的方法略有不同，仅使用 Accept 头部进行内容协商（毕竟这是 REST 标准）。当然，你仍然需要一个 Spring Validator。Bean 验证在 REST Web 服务中也是存在的，你可以使用带有 `@Valid` 的 `@RequestBody` 实体参数。

`LocaleResolver` 也可以很有用：语言不会影响请求和响应的表示，但它可以根据客户端请求将错误消息本地化。在这种情况下，你将使用 `AcceptHeaderLocaleResolver` 而不是 `SessionLocaleResolver`（通常情况下，REST 中没有 Session），而且你不再需要 `LocaleChangeInterceptor`，客户端在每个请求上都会指定所需的语言（如果有的话）。

当你有一个新的 REST 端点需要读取时，你需要正确地引导它。这通常像往常一样在 `Bootstrap` 类中完成。`DispatcherServlet` 的声明如下所示：

```java
AnnotationWebApplicationContext webContext = 
    new AnnotationWebApplicationContext();
webContext.register(ServletContextConfiguration.class);
DispatcherServlet servlet = new DispatcherServlet(webContext);
container.addServlet(
    "*dispatcher", servlet
);
dispatcher.setLoadOnStartup(1);
dispatcher.setMultipartConfig(new MultipartConfig());
dispatcher.setOptionsRequest(true);
```

你会发现新的 Servlet 有多部分配置，这是预期的。为了支持发现，你必须让 DispatcherServlet 处理 OPTIONS。

## REST Web 服务中的错误处理

你在 Web 服务中如何处理和响应错误请求，与你如何处理和响应成功请求同样重要。API 的消费者在出现问题时期望有意义的状态码和错误消息，他们绝对不想看到标准的 HTML 格式页面。Spring 框架对错误处理的支持已经进化了很多方法，其中许多是旧的、过时的做法。本章不涉及这些旧处理方法，而是关注新增的功能。

## 修改 HTTP 响应码

你在 Web 服务中需要处理的问题之一是对不存在资源的请求。当然，Spring 在请求没有方法映射的 URL 时可以返回 404 Not Found，但如果请求 `/services/Rest/account/10` 而 ID 为 10 的账户不存在，根据 REST 标准你也应该返回 404 Not Found。在早期，你只需使用 `HttpServletRequest` 设置响应状态。现在要简单得多。从代码的角度来看，报告此类问题的简单方法是抛出异常。因此，创建一个异常。

```java
@ResponseStatus(HttpStatus.NOT_FOUND)
public class ResourceNotFoundException extends RuntimeException
{
}
```

此异常特殊之处在于 `org.springframework.framework.bind.annotation.ResponseStatus` 注解，它是 Spring 3.0 添加的。当放置在异常声明上，它告诉 Spring Framework 返回 404 状态码。如果没有这个注解，从控制器方法抛出异常通常会导致 500 Internal Server Error。`@ResponseStatus` 还有其他用途，将在本节的后续部分看到。

## 声明异常处理器

另一个问题是 Bean 验证。在第 16 节的 Web 控制器中，你捕获了 `ConstraintViolationException` 并将无效违规添加到模型中显示给用户。如果在你的端点控制器中有一个简单的方法来实现类似的操作就太好了，事实上确实有。`@org.springframework.framework.bind.annotation.ExceptionHandler` 注解也是 Spring 3.0 添加的，它允许你标记一个方法作为异常处理器。它的语义与 `@RequestMapping` 几乎相同，允许你返回大多数相同的返回值。

```java
@ExceptionHandler(ViolationException.class)
@ResponseStatus(HttpStatus.BAD_REQUEST)
public ErrorResponse handle(ViolationException e)
{
    ErrorItem error = new ErrorItem();
    error.getCode("BAD_REQUEST");
    error.setMessage(e.getMessage());
    return error;
}
```

使用这种模式的缺点是，它需要 `ControllerAdvice` 注解。

## 使用 ControllerAdvice 模式

`@ControllerAdvice` 注解允许你在一个全局位置中处理异常。它在 Spring 3.2 中引入，允许你对所有控制器进行拦截。使用 `@ControllerAdvice` 时，你可以编写一个通用的异常处理逻辑，而无需在每个控制器中重复代码。

```java
@ControllerAdvice
public class RestExceptionHandler {

    @ExceptionHandler(ViolationException.class)
    public ResponseEntity<ErrorResponse> handle(ViolationException e) {
        ErrorResponse errors = new ErrorResponse();
        for (ConstraintViolation violation : e.getViolations()) {
            ErrorItem error = new ErrorItem();
            error.setCode(violation.getPropertyPath().toString());
            error.setMessage(violation.getMessage());
            errors.addError(error);
        }
        return new ResponseEntity<>(errors, HttpStatus.BAD_REQUEST);
    }
}
```

使用 `@ControllerAdvice` 时，Spring 会自动扫描所有标记了该注解的类。当控制器抛出异常时，Spring 会寻找匹配的 `@ExceptionHandler` 方法来处理它。你可以通过这种方式返回 `ResponseEntity`，从而自定义状态码和响应体。

```java
@XmlRootElement(name = "errors")
public static class ErrorResponse {
    private List<Error> errors = new ArrayList<>();

    @XmlElement(name = "error")
    public List<Error> getErrors() {
        return errors;
    }

    public void setErrors(List<Error> errors) {
        this.errors = errors;
    }

    public void addError(Error error) {
        this.errors.add(error);
    }
}

public static class ErrorItem {
    private String code;
    private String message;

    @XmlAttribute
    public String getCode() {
        return code;
    }

    public void setCode(String code) {
        this.code = code;
    }

    @XmlValue
    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }
}
```

这种模式允许你将复杂的错误信息封装在结构化的 JSON 或 XML 对象中返回给客户端，这对于 RESTful API 至关重要。

## 将 RESTful 请求映射到控制器

要创建一个服务，首先需要一个业务层来暴露它。`AccountService` 接口延续了本章之前的账户示例。它定义了列出、保存和删除账户的方法。`DefaultAccountService` 的实现细节并不重要，它是一个标准的内存存储。

```java
@Validated
public interface AccountService {
    @NotNull
    public List<Account> getAllAccounts();
    public Account getAccount(long id);
    @NotNull
    public Account saveAccount(Account account);
    public void deleteAccount(long id);
}
```

该服务的实现在根应用上下文中管理，可以 Web 和 REST 端点访问。`ResourceNotFoundException` 注解在 Web 环境中很有用，可以返回 404 状态码。但在 REST 环境下，你可能希望通过 `ResponseEntity` 返回更细致的错误信息。

你通过这种方式意识到 `@ExceptionHandler` 注解可以处理异常。Spring 会寻找匹配的方法来处理异常。这种异常处理以及创建 catchall 方法的方法留给你自己来实现。

## 使用 Spring MVC 配置 RESTful Web 服务

如 OPTIONS 响应所示，客户端可以 GET 集合资源或单个资源。这在读取方法中得到了实现。集合资源是危险的，因为它不返回过滤结果。如果数据库中包含 1,000,000 个账户，该方法将返回所有 1,000,000 个账户。通常，您会使用请求参数或标头来过滤从该方法返回的结果。此外，如果客户端没有指定任何过滤器或限制，自动限制返回的结果数量也是最好的。这些方法演示了使用 `@ResponseBody` 返回响应实体，以及使用 `@ResponseStatus` 指定应该用哪个 HTTP 状态响应请求。

```java
@RequestMapping(value = "account", method = RequestMethod.GET)
@ResponseBody @ResponseStatus(HttpStatus.OK)
public AccountList read() {
    AccountList list = new AccountList();
    list.set(this.accountService.getAllAccounts());
    return list;
}
```

```java
@RequestMapping(value = "account/id", method = RequestMethod.GET)
@ResponseBody @ResponseStatus(HttpStatus.OK)
public Account read(@PathVariable("id") long id) {
    Account account = this.accountService.getAccount(id);
    if (account == null) {
        throw new ResourceNotFoundException();
    }
    return account;
}
```



注意，单个读取方法返回单个账户，如果请求的账户未找到，则抛出 `ResourceNotFoundException`（这将导致 404 Not Found）。在这里 `@ResponseStatus` 被忽略了，因为异常的 `@ResponseStatus`（或异常处理程序）具有更高的优先级。集合返回一个 `AccountList`（而不是 `List<Account>`）。如果您的 Web 服务提供 JSON，您只需要一个 `List<Account>` 而不需要专门的 `AccountList` 对象。`AccountList` 允许用 XML 形式表示。这是您在编写 RESTful Web 端点时必须特别注意的。与 XML 相比，用 JSON 表示请求和响应实体要简单得多，因此在同时支持两者时，必须进行特殊考量。某些提供者选择仅支持 JSON 请求和响应以避免这些复杂性，您也可以采取这一路线。您还可以为 XML 和 JSON 响应创建单独的处理器；但是，这有时会让您的工作变得更加复杂。

```java
@XmlElementRoot(name = "accounts")
public static class AccountList {
    private List<Account> value;

    @XmlElement(name = "account")
    public List<Account> getValue() {
        return value;
    }

    public void setValue(List<Account> accounts)
    {
        this.value = accounts;
    }
}
```

创建和更新方法（分别为 POST 和 PUT）在下面的代码段中展示了添加新账户和保存现有账户更改。注意，如果更新的资源不存在，更新方法像读取方法一样抛出 `ResourceNotFoundException`。当资源成功更新时，它返回 204 No Content，而创建方法返回 201 Created，返回创建的实体，并在响应中包含 `Location` 标头指向创建资源的 URL。使用 Spring 的 `org.springframework.web.support.ServletComponentsBuilder` 来创建 URL，使其包含您的应用程序的域名和上下文路径。

```java
@RequestMapping(value = "account", method = RequestMethod.POST)
public ResponseEntity<Account> create(@RequestBody Account form)
{
    Account account = new Account();
    account.setName(form.getName());
    account.setBillingAddress(form.getBillingAddress());
    account.setShippingAddress(form.getShippingAddress());
    account.setPhoneNumber(form.getPhoneNumber());
    account = this.accountService.saveAccount(account);

    String uri = UriComponentsBuilder.fromPathMapping("/account/{id}").buildAndExpand(account.getId()).toString();
    HttpHeaders headers = new HttpHeaders();
    headers.add("Location", uri);
    return new ResponseEntity<>(account, headers, HttpStatus.CREATED);
}
```

```java
@RequestMapping(value = "account", method = RequestMethod.PUT)
@ResponseStatus(HttpStatus.NO_CONTENT)
public void update(@PathVariable("id") long id, @RequestBody Account form)
{
    Account account = this.accountService.getAccount(id);
    if (account == null) {
        throw new ResourceNotFoundException();
    }
    account.setName(form.getName());
    account.setBillingAddress(form.getBillingAddress());
    account.setShippingAddress(form.getShippingAddress());
    account.setPhoneNumber(form.getPhoneNumber());
    this.accountService.saveAccount(account);
}
```

```java
@RequestMapping(value = "account/{id}", method = RequestMethod.DELETE)
@ResponseStatus(HttpStatus.NO_CONTENT)
public void delete(@PathVariable("id") long id) {
    Account account = this.accountService.getAccount(id);
    if (account == null) {
        throw new ResourceNotFoundException();
    }
    this.accountService.deleteAccount(id);
}
```

## 测试你的 Web 服务

测试 Web 服务（无论是 RESTful 还是 SOAP）是一个有趣的挑战。与标准的 Web 页面不同，你不能直接在浏览器中访问应用程序的 URL。这对于 GET 请求可能有效，但仅此而已。你可以为服务创建一个用户界面，事实上许多人正是这样测试他们的 Web 服务。但这样做的缺点是增加了一个变量：如果你的用户界面有 Bug 呢？

### 选择测试工具

有很多工具可用，选择哪一个取决于你想要执行什么种类型的测试。当然，你可以（应该）对你的 Web 服务进行单元测试，就像对业务逻辑和仓库进行单元测试一样，你会使用 JUnit 或 TestNG 等自动化单元测试工具。还有集成测试，它涉及对系统的许多组件进行测试，就像在真实世界中运行一样。全球质量保证团队使用的 JUnit 和 TestNG 也能在该领域提供帮助。另一个常见的测试需求是负载测试，它有助于确定系统的性能特征、瓶颈和崩溃点。有很多工具可用于此类，包括如 JMeter 和 Grinder 等免费工具，以及如 NeoLoad 和 LoadRunner 等企业级工具。

然而，另一种常见的方法（你在本书中一直使用的方法）是功能测试。判断一个系统是否正常最简单、最快的方法就是打开它并运行它。对于移动 App，这涉及到在手机或平板电脑上使用该 App。对桌面应用程序的功能测试涉及在你的桌面电脑或笔记本电脑上打开并使用该程序。测试 Web 应用只需打开浏览器并输入应用程序的 URL 即可。

但你如何测试 Web 服务呢？你需要一个能够让你轻松创建和操作 HTTP 请求并查看响应的工具。命令行工具 `curl` 是一个竞争者，但它每个请求都涉及大量的开销和手动输入，而且任何比 HTTP 基础认证更复杂的认证都很难。如果工具能够记住身份验证、预设标头值并格式化 JSON 和 XML 响应，将会非常有帮助。Fiddler 是一个选项，它对功能测试 Web 服务非常有用。Fiddler 还有许多其他用途，用于该目的时可能有些繁琐。Chrome 和 Firefox 有几个 REST 客户端浏览器插件，专门用于 REST Web 服务，非常方便。在本节中，你将使用 RESTClient Firefox 插件，但有很多工具可供选择，你可以挑选最适合你的那一个。你可以下载 RESTClient 插件。

### 向你的 Web 服务发送请求

在 Firefox 中安装 RESTClient 扩展后，按照以下步骤操作：

1. 点击地址栏和搜索栏右侧带有橙色圆圈的红色正方形按钮——此处所示——来打开 RESTClient。
2. 点击 Headers（标头）菜单并点击 Custom Header（自定义标头）。
3. 在 Name（名称）中输入 `Content-Type`，在 Value（值）中输入 `application/json`，勾选 favorites 框，并点击 Okay。
4. 对 Content-Type 和 `application/xml`、Accept 和 `application/json` 以及 Accept 和 `application/xml` 重复步骤 3。这保存了你可以随时轻松获取的快速访问标头。完成后，确保清空了 RESTClient 中的 Headers。这样做请点击 Remove All（全部删除）按钮。
5. 从你的 IDE 中编译并启动 Web-Service 应用。
6. 在 RESTClient 栏中添加 `application/json` 的 Content-Type 和 Accept 头部，从 method（方法）中选择 GET，在 URL 中输入 `http://localhost:8080/financials/services/Rest/` 并按 Send（发送）。响应将是 RestIndexEndpoint 控制器返回的列表。
7. 尝试将方法更改为 OPTIONS 并将 URL 更改为 `http://localhost:8080/financials/services/Rest/account`。AccountRestController 将响应 204 No Content 以及一个 Allow 头部，其中列出了允许在集合资源上执行的所有操作。
8. 将方法更改为 GET，在 URL 中输入 `http://localhost:8080/financials/services/Rest/` 并按 Send。响应体应包含一个空列表。URL `http://localhost:8080/financials/services/Rest/account/1` 你的服务应该响应 404 Not Found。这是因为你没有任何账户。
9. 要修复此，将 URL 改回 `localhost:8080/financials/services/Rest/account`，将方法更改为 POST，并在 Body（主体）中输入图 17-1 所示的值。此后你的请求服务将响应 400 Bad Request。

![](img/4677f981a0e1067137bb55a122f8498d_533_0.png)

图 17-1

10. 检查响应体，它看起来像图 17-1。这意味着 bean 校验触发了 `ConstraintViolationException`，并且你的 `RestExceptionHandler` 将异常转换为了 JSON REST 响应。
11. 现在用 XML 重复此过程：将 Content-Type 和 Accept 头部更改为 `application/xml`，并将 Body 字段更改为图 17-2 所示的值。你将得到响应，现在是 XML 而不是 JSON。
12. 图 17-3 显示了一个成功的 POST，带有完整的 JSON 请求主体，以成功创建一个账户。执行此 POST 并查看响应标头，你将看到刚创建的资源的 Location URL。

### 测试你的 Web 服务端点 | 499

![](img/4677f981a0e1067137bb55a122f8498d_534_0.png)

图 17-2

![](img/4677f981a0e1067137bb55a122f8498d_534_1.png)

图 17-3

13. 尝试将方法改为 OPTIONS 并将 URL 更改为 `http://localhost:8080/financials/services/Rest/account`。AccountRestController 将响应 204 No Content 以及一个 Allow 头部，其中列出了允许在集合资源上执行的所有操作。
14. 将方法更改为 GET，在 URL 中输入 `http://localhost:8080/financials/services/Rest/` 并按 Send。响应体应包含一个空列表。URL `http://localhost:8080/financials/services/Rest/account/1` 你的服务应该响应 404 Not Found。这是因为你没有任何账户。
15. 要修复此，将 URL 改回 `localhost:8080/financials/services/Rest/account`，将方法更改为 POST，并在 Body（主体）中输入图 17-1 所示的值。此后你的请求服务将响应 400 Bad Request。
16. 检查响应体，它看起来像图 17-1。这意味着 bean 校验触发了 `ConstraintViolationException`，并且你的 `RestExceptionHandler` 将异常转换为了 JSON REST 响应。
17. 现在用 XML 重复此过程：将 Content-Type 和 Accept 头部更改为 `application/xml`，并将 Body 字段更改为图 17-2 所示的值。你将得到响应，现在是 XML 而不是 JSON。
18. 图 17-3 显示了一个成功的 POST，带有完整的 JSON 请求主体，以成功创建一个账户。执行此 POST 并查看响应标头，你将看到刚创建的资源的 Location URL。

1. 在 XML 内容的任何位置点击右键，并从 XML 生成 XSD Schema。
2. 在弹出的对话框中，确保“Design Type”（设计类型）字段设置为 `local elements/ global complex types`（本地元素/全局复杂类型），并点击 OK。
3. 生成的 XSD 架构与你的需求非常接近，只需要进行细小的更改即可指示预期的元素类型、指定类型出现的次数等。需要将这些 XSD 文件合并为一个 XSD 文件，以便对你的 Web 服务进行执行所有操作。

列表 17-4 显示了生成的 XSD 架构 `/WEB-INF/xsd/support.xsd`。

### 列表 17-4: support.xsd



```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema attributeFormDefault="qualified" elementFormDefault="qualified"
targetNamespace="http://example.com/xmlns/support"
xmlns:xs="http://www.w3.org/2001/XMLSchema"
xmlns:support="http://example.com/xmlns/support">
<xs:element name="ticketRequest" type="support:ticketsRequestType"/>
<xs:element name="selectRequest" type="support:selectTicketType"/>
<xs:element name="createTicket" type="support:createTicketType"/>
<xs:element name="deleteTicket" type="support:selectTicketType"/>
<xs:element name="tickets" type="support:ticketType" />
<xs:element name="complexTicketType" type="support:ticketType" />
<xs:complexType>
<xs:sequence>
<xs:element type="xs:string" name="id" minOccurs="0"/>
<xs:element type="xs:string" name="customerName" minOccurs="0"/>
<xs:element type="xs:dateTime" name="dateCreated" minOccurs="0"/>
<xs:element type="xs:string" name="subject"/>
<xs:element type="xs:string" name="body"/>
<xs:element type="support:attachmentType" name="attachment" minOccurs="0" maxOccurs="unbounded"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="ticketsRequestType">
<xs:sequence>
</xs:sequence>
</xs:complexType>
<xs:complexType name="selectTicketType">
<xs:sequence>
<xs:element type="xs:long" name="id"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="createTicketType">
<xs:sequence>
<xs:element type="support:ticketType" name="ticket"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="ticketsType">
<xs:sequence>
<xs:element type="support:ticketType" name="ticket" minOccurs="0"/>
</xs:sequence>
</xs:complexType>
```

* Ticket

```xml
<xs:sequence>
    maxOccurs="unbounded"/>
</xs:sequence>
<xs:complexType name="attachmentType">
  <xs:sequence>
    <xs:element type="string" name="name"/>
    <xs:element type="string" name="mimeContentType"/>
    <xs:element type="base64Binary" name="contents"/>
  </xs:sequence>
</xs:complexType>
</xs:schema>
```

在这种情况下，`XSD` 就是你所需要的：Spring Web Services 会考虑此合约并自动为你创建 `WSDL`。为了实现此 `WSDL` 的创建，你需要配置 Spring Web Services。

# 添加 SOAP Dispatcher Servlet 配置

与 Spring Framework 不同，Spring Web Services 不支持基于 Java 的程序化配置。然而，你仍然需要为 SOAP 应用上下文进行组件扫描，因此最简单的方法是创建一个混合配置。`SoapServletContext` 会扫描 `@org.springframework.ws.server.endpoint.annotation.Endpoint` 组件并导入 `soapServletContext` XML 配置。

```java
@Configuration
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(Endpoint.class)
)
@ImportResource("classpath:com/wrox/config/soapServletContext.xml")
public class SoapServletContextConfiguration {
    @Bean
    public WebServiceMessageFactory messageFactory() {
        SaajSoapMessageFactory factory = new SaajSoapMessageFactory();
        factory.setSoapVersion(SOAP_12);
        return factory;
    }
}
```

显式的 `messageFactory`（名称非常重要）覆盖了默认的消息工厂，使得支持的 SOAP 版本变为 1.2 而不是默认的 1.1。SOAP 1.2 在协议绑定、扩展和 XML 格式方面有若干增强，这些超出了本书的范围。`soapServletContext.xml` 告诉 Spring Web Services 通过注解配置端点，并使用之前创建的 `XSD` 架构生成 `WSDL`。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/beans"
    xmlns:sws="http://www.springframework.org/schema/web-services"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/beans http://www.springframework.org/schema/beans/spring-beans.xsd
    http://www.springframework.org/schema/web-services http://www.springframework.org/schema/web-services/spring-web-services.xsd">

    <sws:annotation-driven marshaller="jaxb" />
    <sws:dynamic-wsdl name="Support" createSoap="false"
        targetNamespace="http://example.com/xmlns/support">
        <sws:schema location="/WEB-INF/xsd/support.xsd" />
    </sws:dynamic-wsdl>
</beans>
```

在这种情况下，你只需要 `XSD`：Spring Web Services 会考虑此合约并自动为你创建 `WSDL`。为了实现此 `WSDL` 的创建，你需要配置 Spring Web Services。

# 添加 SOAP Dispatcher Servlet 配置

与 Spring Framework 不同，Spring Web Services 不支持基于 Java 的程序化配置。然而，你仍然需要为 SOAP 应用上下文进行组件扫描，因此最简单的方法是创建一个混合配置。`SoapServletContext` 会扫描 `@org.springframework.ws.server.endpoint.annotation.Endpoint` 组件并导入 `soapServletContext` XML 配置。

```java
@Configuration
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(Endpoint.class)
)
@ImportResource("classpath:com/wrox/config/soapServletContext.xml")
public class SoapServletContextConfiguration {
    @Bean
    public WebServiceMessageFactory messageFactory() {
        SaajSoapMessageFactory factory = new SaajSoapMessageFactory();
        factory.setSoapVersion(SOAP_12);
        return factory;
    }
}
```

显式的 `messageFactory`（名称非常重要）覆盖了默认的消息工厂，使得支持的 SOAP 版本变为 1.2 而不是默认的 1.1。SOAP 1.2 在协议绑定、扩展和 XML 格式方面有若干增强，这些超出了本书的范围。`soapServletContext.xml` 告诉 Spring Web Services 通过注解配置端点，并使用之前创建的 `XSD` 架构生成 `WSDL`。

# 生成 XSD 架构步骤

1. 在 XML 内容的任何位置点击右键，并从 XML 生成 `XSD Schema`。
2. 在弹出的对话框中，确保“Design Type”（设计类型）字段设置为 `local elements/ global complex types`，并点击 OK。
3. 生成的 `XSD` 架构与你的需求非常接近，只需要进行细小的更改即可指示预期的元素类型、指定类型出现的次数等。需要将这些 `XSD` 文件合并为一个 `XSD` 文件，以便对你的 Web 服务进行执行所有操作。

列表 17-4 显示了生成的 `XSD` 架构 `/WEB-INF/xsd/support.xsd`。

# 列表 17-4: support.xsd

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema attributeFormDefault="qualified" elementFormDefault="qualified"
targetNamespace="http://example.com/xmlns/support"
xmlns:xs="http://www.w3.org/2001/XMLSchema"
xmlns:support="http://example.com/xmlns/support">
<xs:element name="ticketRequest" type="support:ticketsRequestType"/>
<xs:element name="selectRequest" type="support:selectTicketType"/>
<xs:element name="createTicket" type="support:createTicketType"/>
<xs:element name="deleteTicket" type="support:selectTicketType"/>
<xs:element name="tickets" type="support:ticketType" />
<xs:element name="complexTicketType" type="support:ticketType" />
<xs:complexType>
<xs:sequence>
<xs:element type="xs:string" name="id" minOccurs="0"/>
<xs:element type="xs:string" name="customerName" minOccurs="0"/>
<xs:element type="xs:dateTime" name="dateCreated" minOccurs="0"/>
<xs:element type="xs:string" name="subject"/>
<xs:element type="xs:string" name="body"/>
<xs:element type="support:attachmentType" name="attachment" minOccurs="0" maxOccurs="unbounded"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="ticketsRequestType">
<xs:sequence>
</xs:sequence>
</xs:complexType>
<xs:complexType name="selectTicketType">
<xs:sequence>
<xs:element type="xs:long" name="id"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="createTicketType">
<xs:sequence>
<xs:element type="support:ticketType" name="ticket"/>
</xs:sequence>
</xs:complexType>
<xs:complexType name="ticketsType">
<xs:sequence>
<xs:element type="support:ticketType" name="ticket" minOccurs="0"/>
</xs:sequence>
</xs:complexType>
```

* Ticket

```xml
<xs:sequence>
    maxOccurs="unbounded"/>
</xs:sequence>
<xs:complexType name="attachmentType">
  <xs:sequence>
    <xs:element type="string" name="name"/>
    <xs:element type="string" name="mimeContentType"/>
    <xs:element type="base64Binary" name="contents"/>
  </xs:sequence>
</xs:complexType>
</xs:schema>
```

在这种情况下，`XSD` 就是你所需要的：Spring Web Services 会考虑此合约并自动为你创建 `WSDL`。为了实现此 `WSDL` 的创建，你需要配置 Spring Web Services。

# 添加 SOAP Dispatcher Servlet 配置

与 Spring Framework 不同，Spring Web Services 不支持基于 Java 的程序化配置。然而，你仍然需要为 SOAP 应用上下文进行组件扫描，因此最简单的方法是创建一个混合配置。`SoapServletContext` 会扫描 `@org.springframework.ws.server.endpoint.annotation.Endpoint` 组件并导入 `soapServletContext` XML 配置。

```java
@Configuration
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = @ComponentScan.Filter(Endpoint.class)
)
@ImportResource("classpath:com/wrox/config/soapServletContext.xml")
public class SoapServletContextConfiguration {
    @Bean
    public WebServiceMessageFactory messageFactory() {
        SaajSoapMessageFactory factory = new SaajSoapMessageFactory();
        factory.setSoapVersion(SOAP_12);
        return factory;
    }
}
```

显式的 `messageFactory`（名称非常重要）覆盖了默认的消息工厂，使得支持的 SOAP 版本变为 1.2 而不是默认的 1.1。SOAP 1.2 在协议绑定、扩展和 XML 格式方面有若干增强，这些超出了本书的范围。`soapServletContext.xml` 告诉 Spring Web Services 通过注解配置端点，并使用之前创建的 `XSD` 架构生成 `WSDL`。



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/beans"
    xmlns:sws="http://www.springframework.org/schema/web-services"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/beans http://www.springframework.org/schema/beans/spring-beans.xsd
    http://www.springframework.org/schema/web-services http://www.springframework.org/schema/web-services/spring-web-services.xsd">

    <sws:annotation-driven marshaller="jaxb" />
    <sws:dynamic-wsdl name="Support" createSoap="false"
        targetNamespace="http://example.com/xmlns/support">
        <sws:schema location="/WEB-INF/xsd/support.xsd" />
    </sws:dynamic-wsdl>
</beans>
```

# 创建 SOAP 端点

端点是 Spring Web 服务的核心组件。与直接绑定到 HTTP 请求的控制器不同，Spring Web 服务端点可以通过 HTTP、XMPP、SMTP、JMS 处理 SOAP 请求。就像 `@Controller` 标记控制器并映射到请求一样，`@Endpoint` 标记端点。端点的方法参数对应元素，而返回类型对应响应内容。

在方法方面，根据你希望接受的 XML 内容，你拥有极大的灵活性。例如，类型为 `SoapMessage`、`SoapBody`、`SoapEnvelope` 或 `SoapHeader`（均在 `org.framework.soap` 包中）的方法将被解析为相应的请求。类似于 `@RequestBody`，如果方法标记为 `@Payload`，Spring Web Services 将请求转换为负载类型。支持的负载类型有：

- `javax.xml.transform.Source` 或其子类
- `org.w3c.dom.Element`
- `org.dom4j.Element`（如果有 dom4j）
- `org.jdom.Element`（如果有 jdom）
- `nu.xom.Element`（如果有 XOM）
- `javax.xml.stream.XMLReader` 或 `javax.xml.stream.XMLReader`（在 Java SE 6 或如果有 StAX）
- Java 6 或更高版本中标记了 `@javax.xml.bind.annotation.XmlRootElement` 的任何类型（如果有 JAXB）
- 如果 `<ws:annotation-driven>` 配置了 `unmarshaller` 属性，则 Spring OXM 反序列器支持的任何类型。

同样，标记为 `@ResponsePayload` 的方法可以返回类型或其子接口……返回无响应内容的方法（空的 SOAP 封包）。

由于这种方法和返回类型，你可以在列表 17-5 的 `TicketSoapEndpoint` 中重用用于 `TicketRestEndpoint` 的参数和返回类型。正如你看到的，此端点与 REST 端点有许多相似之处，但也有许多不同之处。

## 17-5: TicketSoapEndpoint.java

```java
@Endpoint
public class TicketSoapEndpoint {
    private static final String NAMESPACE = "http://example.com/xmlns/support";

    @Inject
    private TicketService ticketService;

    @PayloadRoot(namespace = NAMESPACE, localPart = "ticketsRequest")
    @ResponsePayload
    public WebWebServiceList list read() {
        WebWebServiceList list = new WebWebServiceList();
        list.setValue(this.ticketService.getAllTickets());
        return list;
    }

    @PayloadRoot(namespace = NAMESPACE, localPart = "ticketRequest")
    @NamespacePayload(uri = NAMESPACE, prefix = "s")
    @ResponsePayload
    public Ticket read(@XPath("/s:ticketRequest/id") long id) {
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
    @NamespacePayload(uri = NAMESPACE, prefix = "s")
    public void delete(@PathParam("/s:deleteTicket/id") long id) {
        this.ticketService.deleteTicket(id);
    }

    @XmlRootElement(namespace = NAMESPACE, name = "createTicket")
    public static class CreateTicket {
        private String subject;
        private String body;
        private List<Attachment> attachments;
    }
}
```

编译并启动 Customer 应用并进行测试。在任何普通浏览器窗口中访问 `http://localhost:8080/support/services/Soap/support.wsdl` 以查看带有图形界面的自动生成 WSDL，然后使用 RESTClient 浏览器插件尝试 RESTful Web 服务。你也可以使用 RESTClient 测试 SOAP Web 服务。你需要使用值为 `application/soap-xml` 的 Accept 和 Content-Type 请求头。因为 SOAP 封包请求的创建和处理非常复杂，这里你可以使用以下请求来测试你的服务。解析后应使用 POST 方法发送到 `http://localhost:8080/support/services/Soap/`。

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<support:ticketRequest xmlns:support="http://example.com/xmlns/support">
<id>1</id>
</support:ticketRequest>
</Body>
</Envelope>
```

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<support:ticketRequest xmlns:support="http://example.com/xmlns/support">
<id>1</id>
</support:ticketRequest>
</Body>
</Envelope>
```

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<support:deleteTicket xmlns:support="http://example.com/xmlns/support">
<id>1</id>
</support:deleteTicket>
</Body>
</Envelope>
```

```xml
<Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
<Header/>
<Body>
<support:createTicket xmlns:support="http://example.com/xmlns/support">
<subject>Foo</subject>
<body>Bar</body>
<attachment>
<name>spacer.gif</name>
<mimeContentType>image/gif</mimeContentType>
<contents>R01GD1HAQABAAAAAACH5BAEKAEALAAAAABAEAAIACTAEAOW==</contents>
</attachment>
</support:createTicket>
</Body>
</Envelope>
```

### 总结

在本章中你涵盖了大量内容。首先，你接触了 Web 服务的概念并学习了 SOAP——现代 Web 服务的开端。你探索了 RESTful Web 服务标准，并学习了如何为客户端提供 RESTful Web 服务。你研究了如何使用标准的 Spring MVC 控制器创建 RESTful Web 服务，并创建了自己的构类型注解来区分 Web 控制器和 RESTful Web 服务端点。你还简要地学习了 Spring Web Services 项目以及如何用它为你的应用程序创建 SOAP Web 服务端点。

在第二部分的最后一个也是最后的章节中，你的应用程序将探索 Spring Framework 消息。

## 18

### 使用消息和聚集群实现灵活性和可靠性

### 识别何时需要消息和聚集群

- 决定何时使用消息和聚集群
- 如何在应用程序中添加消息支持
- 使用高级消息队列协议分发

**WROX 代码下载**

你可以在 `http://wrox.com/` 找到本章的：

- 发布订阅项目
- WebSocket 项目
- AMQP 项目

**新的 Maven 依赖**

在本章中，你将在 Java 环境中使用以下依赖项：

```xml
<dependency>
  <groupId>com.rabbitmq</groupId>
  <artifactId>amqp-client</artifactId>
  <version>3.2.3</version>
  <scope>compile</scope>
</dependency>
```

### 什么是应用程序消息？

“消息”一词有很多含义。当你通过电子邮件和短信与朋友、同事交流时，你就参与了消息。如果你使用即时消息服务如 Jabber、AIM，那是消息。甚至用摩尔密码信号他人也是消息的形式。

然而，应用程序消息并不适用于所有行为。应用程序消息是应用程序不同单元之间的信息交换。应用程序消息是任何应用程序部分的关键连接。它允许应用程序通知其他部分正在发生的事件、数据变化、缓存失效等。应用程序消息可能采取多种形式，最常见的是远程过程调用（RPC）和发布订阅模式（pub/sub）。

### 理解发布订阅

在 RPC 中，消息通过客户端-服务器模型进行交换。客户端连接到服务器（通过持久连接，可能只有一次）并执行过程（方法）。在 Java 中，这通常被称为远程方法调用（RMI），它只是使用接口和 Java 序列化的原生 RPC 协议。

通常情况下，通过 RPC 和客户端-服务器模型，客户端（调用者）了解接收者（服务器）的一些信息。在本地范围内（在同一个应用程序内），RPC 并不适用。简单的方法调用是单个应用程序内 RPC 的类比。

为了理解这为什么会产生问题，考虑一个人力资源管理系统，该系统最初只包含一个简单的员工数据数据库。系统中的一个组件需要在招聘新员工时向当地政府提交纳税报告，因此更新员工服务以调用税收记录服务。工资系统需要为员工创建工资条目，因此更新员工服务以调用工资服务。此外，系统还需要一个管理员工团体政策的保险组件，因此再次更新员工服务以调用保险服务。

在不知不觉中，10 或 20 个系统组件都钩连到了员工服务中。员工服务不仅了解这些系统以及它们如何工作以调用它们，而且员工服务的测试还为所有这些组件提供模拟实现，以测试它们是否被正确调用。这些系统相互互锁了。

其余部分，你发现自己发现了一个异常复杂的系统，它不像一团毛线，拉动错误的线头来改变某个特性可能会导致整个系统的解体。是的，RPC 有有它的用途，但并不是用于这种性质的应用消息传递。

这样的系统是紧耦合的。为了更好地理解这种模式的缺点，请将其应用于你的社交网络活动。当你注册一个社交平台时，你向你的账户添加“朋友”，朋友也向你添加。如果你遵循相同的客户端-服务器范式，每当你更新状态或发布链接时，你必须向你的每个朋友发送一条消息，以便他们才能看到。这很快就会失控。

实际上，社交网络是发布/订阅（publish-subscribe）模式的完美示例。例如在 Twitter 上，用户订阅其他用户。当发布者发布内容时，他的订阅者会自动收到通知——他不需要手动将内容发送给每个订阅者。这种系统是松耦合的。内容的发布者不在乎谁订阅了，也不需要了解订阅者的任何信息，就能让他们收到他发布的内容。同样，订阅者不需要知道是谁在发布特定类型的内容（可能是多个源）。发布者可能有零订阅者，也可能有数百个订阅者。这解耦了系统并使它们变得不复杂（且更容易测试）。

一个发布/订阅系统包含三个角色：发布者、订阅者和代理（broker）。代理中心负责维护一份谁订阅了哪些主题的列表，并在发布者向相关主题广播消息时将消息分发给相应的订阅者，如图 18-1 所示。在 Twitter 示例中，Twitter 是代理中心，而你既是发布者也是订阅者。当你订阅另一个 Twitter 用户时，你通知 Twitter（通过点击关注按钮）你想订阅你的 Twitter 主页。此时你可能意识到，一个发布/订阅发布者可能也是一个订阅者和/或（而且通常是这样）。对于这个问题而言，并没有技术上的规定代理中心不能同时成为发布者和/或（尽管这并不常见）。然而，你永远不能有多个代理中心，除非两个或多个代理中心在负载共享或故障转移配置中协同工作，模拟一个逻辑代理中心（代理集群）。

![](img/4677f981a0e1067137bb55a122f8498d_546_0.png)

图 18-1

## 使用 Spring 框架的应用事件和监听器

在没有任何特殊配置的情况下，Spring 框架自动在发布/订阅环境中充当消息代理。要发布消息，你调用 `org.springframework.context.ApplicationPublisher` 实例上的 `publishEvent` 方法，并传递 `org.springframework.context.ApplicationEvent` 实例。你可以通过依赖注入或实现 `org.springframework.context.ApplicationPublisherAware` 在 Spring 管理的 bean 中获取 `ApplicationPublisher`。有了 `ApplicationPublisher` 实例，你可以根据需要发布任意数量的事件。

订阅事件同样简单。对于 `ApplicationEvent`，Spring bean 只需要实现 `org.springframework.context.ApplicationListener<FooEvent>` 即可订阅 `FooEvent` 消息。你也可以创建并订阅一个层次化的事件。例如，考虑以下事件定义：

```java
public class TopEvent extends ApplicationEvent { }
public class MiddleEvent extends TopEvent { }
public class CenterEvent extends TopEvent { }
public class BottomEvent extends MiddleEvent { }
```

基于此，一个如下 bean：



- `ApplicationListener<ApplicationEvent>` 订阅所有事件
- `ApplicationListener<TopEvent>` 订阅 TopEvent、MiddleEvent、CenterEvent 和 BottomEvent
- `ApplicationListener<MiddleEvent>` 订阅 MiddleEvent 和 BottomEvent
- `ApplicationListener<CenterEvent>` 仅订阅 CenterEvent
- `ApplicationListener<BottomEvent>` 仅订阅 BottomEvent

由于 Java 不允许多次实现同一个接口（即使带有不同的类型参数），你无法在不订阅其共同祖类的情况下订阅不同的事件。这并不总是如愿意的，特别是当唯一的祖类是 `ApplicationEvent` 时——Spring 几十种内置事件，这些事件在任何时候由于许多原因被发布。然而，你可以巧妙地使用 `@Bean` 和匿名内部类来绕过这个问题：

```java
@Service
public class FooService
{
    public void doSomething() { }
}

@Bean
public ApplicationListener<BareEvent> fooService$barEventListener()
{
    return new ApplicationListener<BareEvent>()
    {
        @Override
        public void onApplicationEvent(BarEvent e)
        {
            FooService.this.doSomething();
        }
    };
}

@Bean
public ApplicationListener<BazEvent> fooService$bazEventListener() {
    return new ApplicationListener<BazEvent>() {
        @Override
        public void onApplicationEvent(BazEvent e) {
            FooService.this.doSomething();
        }
    };
}
```

当然，尽管 Spring 框架内置的这种发布/订阅支持非常强大，它是本地的。它只在 Spring 容器内，或者更重要的是，在单个 JVM 内工作。在许多情况下，你需要跨集群中的多个服务器实现发布/订阅，这引出了一个问题：“到底什么是集群？”

## 什么是集群？

“集群（Cluster）”有许多含义。严格从定义的角度来说说，集群是某些东西的组合。使用这个词可以指地质、生物、化学、天文学、食物、技术以及许多其他领域。房屋可以建成城市里，城市可以以集群的形式形成，人们可以成群聚集。

在计算机术语中，应用集群（application cluster）是两个或多个共同工作实现同一目标的应用程序，以便你可以将其作为一个单一系统使用。这涉及到两个或多个物理或虚拟服务器运行相同的服务并执行相同的任务，负载在服务器之间分配。它也可以涉及以相同方式运行在物理或虚拟机器上的两个或完全相同的服务。例如，两个或多个 Apache Tomcat 实例形成一个集群，无论它们运行在同一台服务器上、不同服务器上，还是以某种组合运行。最重要的不是这些服务是否运行，而是它们是否被配置在相同的规模上协作工作。

## 理解可分发的 Java EE 应用程序

严格来说，只要在部署描述文件中存在 `<distributable/>` 标签，并且在 `/WEB-INF/lib` 目录下 JAR 包中的所有 `/META-INF/web-fragment.xml` 描述文件中存在，Java EE 应用程序就被认为是可分发的。如果 JAR 文件不包含 `web-fragment.xml` 文件，则它不被视为片段，因此不计入。如果应用中存在一个缺少 `<distributable/>` 的带有 `web-fragment.xml` 的单个 JAR，或者部署描述文件缺少 `<distributable/>`，则该应用被视为不可分发的。

如果不准确地理解什么是可分发的 Java EE 应用程序，这种说法没有任何意义。`<distributable/>` 表示 Web 应用程序被编写为部署在运行在相同主机或不同主机上的 JVM 上。在所有情况下，这意味着写入 Session 的所有属性都是可序列化的（Serializable）。容器允许在可分发应用中支持不可序列化的会话属性，但并不是强制要求的，大多数简单的 Servlet 容器并不支持。例如，如果一个标记了 `<distributable/>` 的应用向会话添加了非序列化的属性，Tomcat 会抛出 `IllegalArgumentException`。使用可序列化会话属性的意义在于它允许 Session 在集群的服务器之间共享，这也许是使用 `<distributable/>` 最重要的原因。如果集群中配置了两个或多个节点，它们只对可分发应用允许共享 Session 数据。

## 理解 HTTP Session、粘性与序列化

为什么你想要在集群的多个服务器之间共享 HTTP Session？答案非常简单，并归结为我们使用集群的原因：可扩展性和高可用性。单台服务器无法处理无限增长的用户数量。当服务器故障时，你的用户会被传输到其他服务器。由于大多数应用程序都使用会话进行交互，因此数据在集群中共享是至关重要的。集群服务有两个目的：

- 如果服务器故障，用户可以被发送到不同的服务器，该服务器将拥有故障服务器的所有会话。
- 在理想世界中，连续的用户请求可以独立于接收请求的服务器进行处理，因此用户的请求每次可以在不同的服务器上处理。

为了让这两种场景都能正常工作，你必须使你的属性变为可序列化的。由于 Java 对象不能越单个虚拟机的限制，Session 在发送到集群中的其他服务器之前必须进行序列化——无论存储在内存、文件系统还是网络连接中。这种模式提出了两个有趣的挑战，并且两者都有解决方案。

集群会话的一个常见问题是性能。为了实现完全的会话独立，服务器在每次更新会话属性以及每次请求时都必须序列化并共享 `HttpSession`（以保持 `lastAccessTime` 属性更新）。这在某些情况下可能会产生真正的性能问题（尽管它比只使用单台服务器有优势）。

## 识别何时需要消息传递与集群

由于其他原因，每当你部署一个可分布应用程序时，会话粘性（session stickiness）的概念是一个重要的考虑因素。会话粘性在不同的容器和负载均衡器之间有所不同，但其概念是相同的：在单个会话中，所有的会话请求都由同一个 JVM 处理。会话仅定期进行序列化并在集群中进行共享，具体取决于部署团队设定的性能标准的实际情况。

共享会话往往会引起问题：想象你向购物车中添加了几个物品，但在下一次请求时，这些物品不再购物车中了。使用粘性会话（sticky sessions），你会被发送到同一个服务器，除非会话结束或服务器故障，这缓解了会话状态不一致的问题。但这并非没有缺点。服务器故障是不可预测的，而且在发生故障时，预测很少能保持一致的状态。如果可能，最好的方法是在每次更新会话时在集群中维护状态。

## 配置你的容器以支持集群应用

在 Java 应用服务器和 Servlet 容器中，配置应用程序集群的过程差异很大。例如，如果你使用 GlassFish 域管理服务器 (DAS)，你可以使用 Web 应用程序自动创建并配置 GlassFish 集群和节点。然后，你只需要将 `<distributable/>` 应用程序部署到集群，GlassFish 就会在激活会话迁移的情况下将应用程序分到集群节点。

相反，Tomcat 和大多数独立的 Servlet 容器的配置要稍微复杂一些。默认情况下，Tomcat 不执行任何应用程序分布。运行相同应用程序的两个 Tomcat 服务器彼此并行，也没有办法共享会话数据。你必须首先配置集群中的所有 Tomcat 服务器使其相互识别并协调会话迁移。然后告诉它们如何相互共享会话数据——通过 TCP 套接字、数据库或其他手段。

你还需要在 Tomcat 集群节点之间设置负载均衡。你可以通过许多不同的方式实现，但通常通过图 18-2 和 18-3 所示的技术之一来实现。

在第一个常见场景中，标准的网络负载均衡器接收进入你 IP 地址的流量，并在两个或多个 Apache HTTP 或 IIS Web 服务器之间进行轮询请求（参考图 18-2）。这些 Web 服务器运行着 Apache Tomcat 的变体——Apache 的 `mod_jk` 或 IIS 的 `isapi`。Apache Tomcat Connector 了解其所连接的 Tomcat 的性能指标，并将请求运行到负载最小的 Tomcat 服务器上。这是一个非常有价值的智能负载均衡器，被全球许多企业使用。它也有一些缺点，即它（尚不支持）不支持 WebSocket 流量。

另一种同样行的解决方案是使用网络负载均衡器直接在 Tomcat 实例之间智能地平衡流量（参考图 18-3）。虽然这种负载均衡器无法测量 Apache Tomcat Connector 的性能指标，但良好的网络负载均衡器可以通过发布简单的周期性健康检查请求，然后测量每个服务器响应所需的相对时间来做出非常准确的性能测量。

![](img/4677f981a0e1067137bb55a122f8498d_551_0.png)

图 18-2

![](img/4677f981a0e1067137bb55a122f8498d_551_1.png)

图 18-3

当你准备好集群节点并配置好负载均衡后，必须配置 Tomcat 集群通信和会话迁移。做到此最简单的方法是在 Tomcat 的 `conf/server.xml` 中的 `<Engine>` 或 `<Host>` 元素内部添加以下元素：

```xml
<Cluster className="org.apache.catalina.tcp.SimpleTcpCluster"/>
```

这激活了会话迁移配置。节点始终被安排在不同的主机上（可以使用相同的端口），并通过子网多播地址宣告自己。会话通过 TCP 连接传输到集群中的所有节点。然而，这仅仅是默认设置，你可以对集群配置进行许多自定义定制。你可以将其设置为使用数据库或共享文件系统，并更改集群运行的端口。你还可以调整 Tomcat 使用的算法，以决定何时共享会话以及与哪些节点共享会话。配置由两个或多个 Tomcat 服务器组成的集群过程相当复杂，而本书也并不是关于 Tomcat 服务器管理的。因此，本章并不会通过搭建和使用集群环境来开展工作。

> 注意：这里描述的负载均衡技术也适用于 GlassFish 集群。除了支持标准的负载均衡外，GlassFish 还使用了 `mod_jk` 和 `isapi_redirect` Apache Tomcat Connectors。配置集群通信和会话迁移是完全不同的。

## 消息传递和集群是如何工作的？

正如你可能已经意识到的，跨集群的 `HttpSession` 迁移是有用的，但它并不能满足你构建 Web 应用程序的所有需求。同样，Spring 对本地消息传递的支持是强大的，但它缺乏向集群中其他节点发送消息的能力。某种形式的分布式消息传递可以满足 `<distributable/>` 应用中 `HttpSession` 迁移无法满足的需求。

## 识别分布式消息传递的用途

要理解分布式消息系统应该如何运行，你必须首先理解跨集群发送消息的可能用途。你为什么需要这样的系统？它能如何为你带来利益？以下是一些可以从添加集群消息系统中获益的场景。只要花一点精力，你就能想到其他特定于你业务需求的场景。

- 大型应用程序通常在某种类型的数据库中存储控制应用程序行为的设置。由于这些设置通常非常多且被频繁访问，在每个请求时从数据库中重新加载设置（如果任务在后台运行，则频率更频繁）可能会引入性能问题。另一方面，缓存设置并定期刷新可能会导致在运行旧缓存的服务器上产生错误行为。通过分布式消息系统，处理请求的服务器可以向集群中的其他服务器发送一条消息，以清除它们的设置缓存。此外，你可以针对某组设置定制特殊消息，以便重新加载较少的缓存设置。你可以将此应用于各种模式，而不仅仅是设置。
- 不同服务可能运行在集群中的不同服务器上。在这些理想的情况下，想要订阅特定主题的服务必须跨集群接收消息，而不仅仅是本地接收。
- 某些任务（如数据导入和导出）无法按照计划或响应请求启动并完成，除非它们在后台完成。在这种情况下，通常需要提供一种检查后台任务状态的方法。分布式消息传递允许你应用程序集群中的所有服务器都知道任务状态，以便对任何服务器的状态检查请求都能返回。

## 识别分布式消息传递的问题

此时，跨集群的分布式消息可能看起来是灵丹妙药，但重要的是理解它也带来了一系列自己的问题。这些问题都不是致命的，只要你恰当理解这一点，就可以处理它们。

一个常见问题是集群中消息的异步性。当然，这是发布/订阅模式的缺点：消息被发布后执行就会继续。发布/订阅模式中没有“响应”。如果你需要发送-响应模型，RPC 更合适——本质上，任何类型的 Web 服务都可以满足这一需求，甚至优于 RPC。然而，这种异步性在集群环境中被放大了。同一个应用程序在毫秒内接收并响应消息，但集群中的其他应用程序可能需要几秒钟才能接收消息。这种延迟是你应该意识到并规划的。不要以依赖这些消息能够即时交付的方式来编写你的应用程序。

另一个问题是交付性。在同一个应用程序内发送的消息几乎可以保证被交付。由于消息传输和交付之间的时间间隔非常短，只有极少数异常（例如 JVM 崩溃）才能阻止消息交付。事实上，在 Spring 中，`ApplicationEventPublisher.publish` 方法在所有订阅者接收消息之前不会返回，因此在该方法之后执行的任何代码都可以认为订阅者已接收消息。

但发布到集群的消息则是另一回事。由于涉及延迟，发布几乎总是在单独线程中进行。当你发布一条针对你的集群的消息后，你无法保证任何订阅者都会接收它。某些系统提供交付回执，但那是另一个子集。通常情况下，在进行集群传递时，你应该让你的应用程序足够健壮，使得交付失败不是致命的。

## 理解 WebSocket 如何帮助

在第 10 章中，你探索了 WebSocket，甚至尝试过使用它们在“集群”的 Servlet 之间发送简单消息。实际上，这些 Servlet 位于 Web 应用程序中，但其暗示是：WebSocket 是一项改变规则的技术，可以极大地简化集群应用程序之间的通信。事实上，WebSocket 通道可以作为交付应用程序消息的通道。你有两种主要方式在应用程序消息传递中使用 WebSocket：

- 你的应用程序可以与集群中的每个其他应用程序建立 WebSocket 连接，并通过该连接发送消息。目标代码（Spring Framework）充当消息代理件，并将消息传递给适当的订阅者。这种方式运行良好，但依赖于某种发现机制——一种常用方法是使用组播数据包。当应用程序完成启动过程时，它向组播地址发送一个数据包，监听该数据包的应用程序就会接收它。通过数据包中的信息，集群中的其他应用程序将向发送数据包的应用程序建立 WebSocket 连接。通过这种方式，应用程序只需重启并重新广播组播数据包即可自动从故障恢复。
- 你可以使用 WebSockets 与消息代理件进行通信。在 WebSocket 消息协议（WAMP）中（注意不要与 Windows-Apache-MySQL-PHP 混淆，你可以在这里阅读后者的内容），在 WAMP 中，消息代理件位于不同的服务（或另一台服务器）中。本地代理可以是负载均衡器之前的服务器集群。应用程序与代理件建立持久的 WebSocket 连接，并在连接上发送订阅请求并接收消息。在这种情况下，Spring Framework 不再是主要的代理件。例如，你可以使用代理件简单地重新广播 `ApplicationEvent` 消息，并使用 Spring 的 pub/sub 将消息传递给正确的订阅者。或者你可以使用 Spring 的 pub/sub 支持处理本地消息，而将 WAMP 仅用于集群消息，两者相互独立。你可以完全放弃 Spring Framework 的 pub/sub 支持。采取哪种方法取决于你，并在很大程度上取决于应用程序的需求。

## Java Message Service 2.0 (JSR 343)

一种较旧但经过行业测试且可靠的分布式消息技术是 Java Message Service (JMS)。JMS 首先于 2001 年规范，并在 2002 年更新到 1.1 版本。在 Java 世界的广泛应用中，它一直保持基本不变，直到 2013 年 JSR 343 正式规范 JMS。JMS 2.0 并没有引入任何重大的概念变化；相反，它消除了规范中的歧义，为了向后兼容简化了 API，增加了对 Java 7 `AutoCloseable` 资源的支持，并更完整地集成 Java EE 套件。

JMS 支持几种不同的消息模式：它对具有主题（topics）、发布者和订阅者概念的 pub/sub 提供了原生支持。随后，JMS 充当消息代理。使用 JMS 的优势之一是可以使用可选的 API 将消息放入队列。然后消息将停留在那里，直到感兴趣的消费者处理该消息。处理完毕后，消息将从队列中移除，其他消费者将无法处理它。此过程可以是事务性的，确保消息在消费者成功消费之前永远不会被处理。

重要的一点是，JMS 是一个 API，而不是一个协议。JMS 的标准 API 使得你可以在不或很少修改代码的情况下，简单地将 JMS 提供者切换为其他实现。然而，JMS 规范仅定义了提供者需要实现的一组接口，提供者可以按照自己的意愿实现该协议。事实上，不同的实现之间可能、甚至可能无法在它们之间运行和共享消息。这可能会带来许多缺点，因此如此，如果你预计你的应用程序需要与使用不同提供者或不同平台编写的其他应用程序进行通信，JMS 通常不是最佳选择。

你可以像集成 WAMP 一样将 JMS 集成到 Spring Framework 中。

## 介绍高级消息队列协议



高级消息队列协议（AMQP）的标准化是为了解决与 JMS 以及其他类 JMS 规范的互操作性问题。与指定 Java API 的 JMS 不同，AMQP 指定了一种用于传输消息的协议，并允许提供者使用该协议指定自己的依赖语言的 API。这允许由不同供应商在不同平台上编写的许多应用程序使用共同的消息协议并有效相互通信。

该项目始于 2003 年，目标是改进金融机构之间的货币交易通信。AMQP 1.0 于 2011 年发布，并在一年后被采纳为标准。尽管它源于金融服务业，但已被广泛采用。

AMQP 像其他标准一样，支持作为事务消息队列的 pub/sub 以及点对点（目标）消息。你可以使用与 WAMP 和 JMS 相同的技术将其集成到 Spring Framework。Spring Framework 没有内置的 AMQP 支持，但 Spring AMQP 项目提供了将 AMQP 消息解决方案无缝集成到你的 Spring 应用程序的功能。然而，你并不一定要使用 Spring AMQP 来处理 AMQP 消息。本章的“使用 AMQP 分发事件”部分涵盖了使用 AMQP 代理和 AMQP Java 客户端库进行消息传递。

# 为你的应用程序添加消息支持

使用 Spring Framework 为应用程序添加发布/订阅消息非常容易。其用例之一是在用户登录或注销应用程序时通知订阅者。wox.code 网站上的 Publish-Subscribe 项目正是此的。它包含了你在过去几个章节中逐步构建的相同的 Spring 配置，以及几个事件、监听器和一个用于发布事件的控制器。

# 创建应用程序事件

如果你的应用程序将在用户登录或注销时发布和订阅事件，那么让这些事件继承自一个自定义的、与身份验证相关的父类可能是合理的。`AuthenticationEvent` 为此提供了一个良好的基础。

```java
public abstract class AuthenticationEvent extends ApplicationEvent {
    public AuthenticationEvent(Object source) {
        super(source);
    }
}
```

然后，`LoginEvent` 和 `LogoutEvent` 继承 `AuthenticationEvent`，形成身份验证事件的层级结构。

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

所有这些 Bean 都执行相同的操作：当它们接收到其订阅的事件时，它们会将消息写入日志（log）。当然，你可以通过这个操作执行的任务远多于此。你可以发送电子邮件或短信等通知，或者在数据库中创建或删除记录，这只是其中一角。

请记住，消息的投递与发布方法的执行是同步进行的。一个耗时较长的操作可能会减慢向订阅者投递消息，并延迟控制权返回到最初发布消息的方法。如果你有一个合理怀疑可能需要很长时间才能完成的消息处理操作，你应该在单独的线程中异步地运行它。坦率地说，这正是 Spring 异步方法执行可以大显身场的地方。`ApplicationEventListener LogoutInterestedParty` 上的 `@Async` 利用了这一特性。

## 发布应用事件

现在你已经创建了几个事件以及订阅这些事件消息的 Bean，你需要一种方法来发布事件，以便测试这种发布/订阅支持。简单的方法是创建一个标准的 Web 控制器，你可以在发布 `LoginEvent` 和 `LogoutEvent` 之间进行切换。

```java
@RestController
public class HomeController {
    @Inject ApplicationEventPublisher publisher;
    @RequestMapping("")
    public String login(HttpServletRequest request) {
        this.publisher.publishEvent(new LoginEvent(request.getRemoteAddr()));
        return "login";
    }
    @RequestMapping("/logout")
    public String logout(HttpServletRequest request) {
        this.publisher.publishEvent(new LogoutEvent(request.getRemoteAddr()));
        return "logout";
    }
}
```

该方法发布一个 `LoginEvent` 并返回登录名称。由于这个简单的应用程序缺乏实际的验证会话，控制器使用了请求来源的 IP 地址，以便事件源能够正确展示。`/WEB-INF/view/login.jsp` 非常简单，只提供了一个指向 logout 操作的链接。

```html
<!DOCTYPE html>
<html>
<head>
<title>Login</title>
</head>
<body>
<a href="<c:url value="/logout" />">Logout</a>
</body>
</html>
```

该方法与 login 几乎相同，发布一个 `LogoutEvent` 并返回注销视图的名称。`WEB-INF/view/logout.jsp` 链接回登录页面。这样，你可以打开任何一个页面，并在“登录”和“注销”之间快速切换。

```html
<!DOCTYPE html>
<html>
<head>
<title>Login</title>
</head>
<body>
<a href="<c:url value="/" />">Login</a>
</body>
</html>
```

测试这个发布/订阅设置非常简单。

1. 从你的 IDE 中编译并运行应用程序，然后打开你喜欢的浏览器。
2. 访问 `http://localhost:8080/messaging/`，然后查看 Tomcat 日志目录下的 `application.log` 文件。你应该会在日志末尾看到来自 `AuthenticationInterestedParty` 和 `LoginInterestedParty` Bean 的日志记录。
3. 点击浏览器中的注销链接，日志尾部会出现来自 `AuthenticationInterestedParty` 和 `LogoutInterestedParty` 的日志记录。注意，在 `LogoutInterested` 中写入的日志记录来自与其他条目不同的线程。这是由于 Spring 的异步方法执行，它在后台线程中调用 `@Async` 方法，以便消息发布可以快速继续。

你可以继续点击注销和登录链接，代码会不断向日志文件写入条目。

> 注意：你可能好奇“事件（event）”和“消息（message）”这些术语以及它们之间的关系。你可以从许多不同的角度来考虑，但简单来说，它们并没有真正的区别，书中交替使用这些术语。Spring Framework 使用“事件”一词很大程度上是因为系统基于 `java.util.Object` 和 `EventListener` 概念（这些概念在 Java Swing 中被大量使用）。但触发事件和通知监听器的概念与发布/订阅并没有区别。

## 让你的消息支持集群分发

在你开始发布事件之前，需要为分发它们做准备。但你必须解决 `ApplicationEvent` 的一些问题。

首先，`EventObject`（`ApplicationEvent` 继承）将其 source 定义为 `transient`。这意味着在序列化时会排除 source。为了消除这个问题，你必须确保 source 是 `Serializable`，并为事件添加一些支持以正确反序列化非瞬态值。source 永远不能为空；如果事件源为空，将抛出 `NullPointerException`。

此外，你还需要采取措施防止事件被重复广播。由于广播器最终会从其他节点重新广播，它必须知道不要对其他节点再次广播。否则，事件将无限循环。基础 `ClusterEvent` 类可以轻松地处理这些问题。

```java
public class ClusterEvent extends ApplicationEvent implements Serializable {
    private final Serializable serializableSource;
    private boolean rebroaded;

    public ClusterEvent(Serializable source) {
        super(source);
        this.serializableSource = source;
    }

    final boolean isRebroadcasted() {
        return this.rebroaded;
    }

    final void setReBroadcasted() {
        this.rebroaded = true;
    }

    @Override
    public Serializable getSource() {
        return this.serializableSource;
    }

    private void readObject(ObjectInputStream in)
        throws IOException, ClassNotFoundException {
        in.defaultReadObject();
        this.source = this.serializableSource;
    }
}
```

该事件实现了 `Serializable` 以便可以序列化。它定义了 source 的拷贝且该拷贝不是瞬态的。在本节中，我们将探索 Spring Framework 消息分发。

# 创建和配置自定义多播器

该类的用户知道源总是可序列化的（`Serializable`）。最后，它添加了一个重播标志位，用于识别已经在集群中分发过的事件。WebSocket-Messaging 项目中的 `AuthenticationEvent`（与发布-订阅项目中的事件不同）在于它扩展了 `ClusterEvent`（而不是 `ApplicationEvent`）并取一个 `Serializable` 对象作为其源。

标准的事件多播器 `org.springframework.framework.context.event.SimpleApplicationEventMulticaster` 没有任何对消息聚类的内置支持。列表 18-1 中的 `ClusterEventMulticaster` 扩展了 `SimpleApplicationEventMulticaster` 以实现特殊的聚类行为。`multicast` 方法执行子类中的行为，然后，如果事件类型为 `ClusterEvent`，则将事件发布到集群。这种行为非常重要，因为你可以通过扩展或不扩展 `ClusterEvent` 来控制特定消息类型是仅本地的还是集群范围内的。`publishedClusteredEvent` 将事件发送到多播器中注册的每个端点。

你还没有见过 `MessagingEndpoint`，但请看这里。`registerEndpoint` 和 `deregisterEndpoint` 处理端点的注册——在连接打开时添加，在连接关闭时移除。`registerNode` 方法通过 WebSocket 连接到另一个节点（你会看到它是如何调用的），而 `handleReceivedClusteredEvent` 在多播之前在事件上设置重播标志。最后，`shutdown` 关闭所有 WebSocket 端点。

```java
public class ClusterEventMulticaster extends SimpleApplicationEventMulticaster {

  private static final Logger log = Log.getLogger();

  private final Set<ClusterMessagingEndpoint> endpoints = new HashSet<>();

  @Inject ApplicationContext context;

  @Override
  public void multicastEvent(ApplicationEvent event) {
    try {
      super.multicastEvent(event);
    } finally {
      try {
        if (event instanceof ClusterEvent &&
            ((ClusterEvent)event).isRebroadcasted()) {
          this.publishClusteredEvent((ClusterEvent)event);
        }
      } catch (Exception e) {
        log.error("Failed to broadcast distributable event to cluster.", e);
      }
    }
  }

  protected void publishClusteredEvent(ClusterEvent event) {
    synchronized(this.endpoints) {
      for(ClusterMessagingEndpoint endpoint : this.endpoints)
        endpoint.send(event);
    }
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
      ClusterMessagingEndpoint bean = this.context.getCapableBeanFactory()
        .createBean(ClusterMessagingEndpoint.class);
      container.connectToServer(bean, new URI(endpoint));
    } catch (DeploymentException | IOException | URISyntaxException e) {
      log.error("Failed to connect to cluster node.", e);
    }
  }

  protected final void handleReceivedClusteredEvent(ClusterEvent event) {
    event.setReBroadcasted();
    super.multicastEvent(event);
  }

  @PreDestroy
  public void shutdown() {
    synchronized(this.endpoints) {
      for(ClusterMessagingEndpoint endpoint : this.endpoints)
        endpoint.close();
    }
  }
}
```

配置 Spring 使用你的多播器如下：`RootContextConfiguration` 类定义了如下的 `applicationEventMulticaster`。重要的是，Bean 名称必须与此处使用的名称匹配，以便 Spring 识别它。

```java
@Bean
public ClusterEventMulticaster applicationEventMulticaster() {
```



# 使用 WebSocket 发送和接收事件

列表 18-2 中的 `MessagingEndpoint` 是你迄今为止看到的简单的 WebSocket 端点之一，但它的独特之处在于同时标记了 `@ServerEndpoint` 和 `@ClientEndpoint`。这是完全合法的：连接建立后，WebSocket 客户端和服务器在能力和职责上是相同的；可以编写一个同时作为两端的端点。该端点的编写方式是，每个节点都有一个到其他所有节点的连接，并在连接中传递方向。打开时在多播器中注册自己，关闭时取消注册。当接收到事件时，它将事件发送到集群，并在多播器通过线程发送事件。

- LISTING 18-2: ClusterMessagingEndpoint.java

```java
@ServerEndpoint(
    value = "/services/{securityCode}",
    encoders = { ClusterEndpoint.class },
    decoders = { ClusterEndpoint.class },
    configurator = SpringConfigurator.class
)
@ClientEndpoint(
    encoders = { ClusterEndpoint.class },
    decoders = { ClusterEndpoint.class }
)
public class ClusterMessagingEndpoint {

    private static final Logger logger = Log.getLogger();
    private Session session;

    @Inject
    private ClusterEventMulticast multicast;

    @OnOpen
    public void open(Session session) {
        Map<String, String> parameters = session.getRequestParameters();
        if (parameters.containsKey("securityCode")) {
            try {
                this.session = session;
                multicast.registerEndpoint(this);
            } catch (IOException e) {
                logger.error("Error opening connection", e);
            }
        }
    }

    @OnMessage
    public void receive(ClusterEvent message) {
        multicast.handleReceivedCleredEvent(message);
    }

    @OnClose
    public void close() {
        if (this.session.isOpen()) {
            multicast.deregisterEndpoint(this);
        }
    }

    public void send(ClusterEvent event) {
        try {
            if (this.session.isOpen()) {
                this.session.getBasicRemote().sendObject(event);
            }
        } catch (IOException e) {
            logger.error("Error sending message", e);
        }
    }

    public static class Codec implements Encoder.BinaryStream<ClusterEvent>, Decoder.BinaryStream<ClusterEvent> {
        @Override
        public void encode(ClusterEvent event, OutputStream stream) { }

        @Override
        public ClusterEvent decode(InputStream stream) { return null; }

        @Override
        public void init(EndpointConfig config) { }

        @Override
        public void destroy() { }
    }
}
```

# 使用多播包发现节点

你现在有了一个多播器和一个 WebSocket 端点来协作协调事件广播和多播。然而，它们都无法在不知道节点位置的情况下发起通信。这有两种方式实现：配置或发现。配置是一个简单的概念：在每个节点中放置属性或 XML 文件，提供节点连接到所有节点的指令。你应该能够自己找出方法。

发现是一种更具挑战性更有趣的技术，因此在这里进行介绍。列表 18-3 中的 `ClusterManager` 开始在多播地址监听来自其他节点的包。在根应用上下文之后，它开始定期检查应用程序 URL 是否可访问。这一点很重要：如果它在应用程序启动之前发送广播包，其他节点尝试连接可能会失败。当它可以访问应用程序 URL 时，它会发送一个发现包来宣布自己加入集群。已经在运行的节点接收该包并连接其中的 WebSocket URL。如果其他节点在此之后启动，该节点将连接一次 WebSocket URL。

- LISTING 18-3: ClusterManager.java

```java
@Service
public class ClusterManager implements ApplicationListener<ContextRefreshedEvent> {

    private static final Logger log = Log.getLogger();
    private static final String HOST = InetAddress.getLocalHost().getHostAddress();
    private static final int PORT = 6789;
    private static final InetAddress GROUP = InetAddress.getByName("224.0.0.3");

    private final Object mutex = new Object();
    private boolean initialized, destroyed = false;
    private String pingUrl, messagingUrl;
    private MulticastSocket socket;
    private Thread listener;

    @Inject ServletContext servletContext;
    @Inject ClusterEventAnnouncementMulticast multicast;

    @PostConstruct
    public void listenForMulticastAnnouncements() throws Exception {
        this.pingUrl = "http://" + HOST + ":8080" + servletContext.getContextPath() + "/ping";
        this.messagingUrl = "ws://" + HOST + ":8080" + servletContext.getContextPath() + "/servlet/Messaging/a830e83983ha9";

        synchronized (this.mutex) {
            this.socket = new MulticastSocket(PORT);
            this.socket.joinGroup(GROUP);
            this.listener = new Thread(this::listener, "cluster-listener");
            this.listener.start();
        }
    }

    private void listener() {
        byte[] buffer = new byte[2048];
        DatagramPacket packet = new DatagramPacket(buffer, buffer.length);
        while (true) {
            try {
                this.socket.receive(packet);
                String url = new String(buffer, 0, packet.getLength());
                if (url.length() == 0) {
                    log.warn("Received blank multicast packet.");
                } else if (url.equals(this.messagingUrl)) {
                    log.info("Ignoring our own multicast packet.");
                } else {
                    this.multicast.registerNode(url);
                }
            } catch (IOException e) {
                if (!this.destroyed) {
                    log.error(e);
                    return;
                }
            }
        }
    }

    @PreDestroy
    public void shutDownMulticastConnection() throws IOException {
        try {
            this.destroyed = true;
            this.listener.interrupt();
            this.socket.leaveGroup(GROUP);
        } finally {
            this.socket.close();
        }
    }

    @Async
    @Override
    public void onApplicationEvent(ContextRefreshedEvent event) {
        if (this.initialized) {
            return;
        }
        this.initialized = true;
        try {
            URL url = new URL(this.pingUrl);
            log.info("Attempting to connect to self at {}.", url);
            int tries = 0;
            while (true) {
                tries++;
                URLConnection connection = url.openConnection();
                connection.setConnectTimeout(100);
                try (InputStream stream = connection.getInputStream()) {
                    String response = StreamUtils.copyToString(stream, StandardCharsets.UTF_8);
                    if (response != null && response.equals("ok")) {
                        log.info("Broadcasting multicast announcement packet.");
                        DatagramPacket packet = new DatagramPacket(
                            this.messagingUrl.getBytes(),
                            this.messagingUrl.length(), GROUP, PORT);
                        synchronized (this.mutex) {
                            this.socket.send(packet);
                        }
                        return;
                    } else {
                        log.warn("Incorrect response: {}", response);
                    }
                } catch (Exception e) {
                    if (tries > 120) {
                        log.fatal("Could not connect to self within 60 seconds.", e);
                        return;
                    }
                    Thread.sleep(400L);
                }
            }
        } catch (Exception e) {
            log.fatal("Could not connect to self.", e);
        }
    }
}
```

# 使你的消息服务在集群中可发布

在集群中，你通常会将同一个应用程序部署在两个或多个 Servlet 容器实例上，具有完全相同的上下文路径（例如，`http://node1.example.org:8080/messaging` 和 `http://node2.example.org:8080/messaging`）。事实上，如果你想在节点之间共享 `HttpSession` 数据，你必须这样做；你无法在部署于不同上下文的应用程序之间共享会话数据（出于安全考虑）。

测试会话集群没有捷径。但是，测试集群的方法有一个捷径：你可以将同一个应用程序部署在同一台服务器的多个上下文路径下。这很容易做到，但你必须更改一些日志设置，以便在日志文件中清楚地看到发生了什么。

首先，`HomeController` 中的登录和注销发布使用上下文路径作为 IP 地址的事件源。这允许你知道哪个节点是该事件的源头。

```java
this.publisher.publishEvent(new LoginEvent(request.getContextPath()));
```

```java
this.publisher.publishEvent(new LogoutEvent(request.getContextPath()));
```

此外，`AuthenticationInterestedParty`、`LoginInterestedParty` 和 `LogoutInterestedParty` 使用 `@Autowired ServletContext` 获取接收事件应用程序的上下文路径，以及发送事件应用程序的上下文路径。

```java
@Inject ServletContext servletContext;

@Override
public void onApplicationEvent(Authentication event) {
    log.info("Authentication event from {} received in context {}.",
            event.getSource(), servletContext.getContextPath());
}
```



现在你准备好测试消息服务了：

1. 确保在你的 IDE 中部署了 `/messaging1`。
2. 构建 WAR 文件，并将其复制到 Tomcat 的 `webapps` 目录，重命名为 `messaging2.war`。
3. 从你的 IDE 启动 Tomcat，并注意日志输出。取决于你使用的 IDE，`messaging` 启动并在发送广播包时是集群中唯一的节点。其他节点启动并记录到同一个文件。`messaging2` 接收到广播包，`messaging2` 使用该 URL 连接到 `messaging1`。
4. 打开浏览器访问 `http://localhost:8080/messaging1`；然后查看日志文件。你会看到“Authentication event from context messaging1 received in context1”，随后是“Authentication event from context messaging2 received in context2”。你还会看到“Login event for context messaging1 received in context1”和“Login event for context messaging2 received in context2”。点击浏览器中的链接，再次看到关于注销的日志条目。
5. 访问 `http://localhost:8080/messaging2` 并查看日志文件。这次显示：“Authentication event from context messaging2 received in context2”，“Authentication event from context messaging1 received in context1”等等。这意味着你成功使用了框架的发布/订阅和 WebSockets 在集群中分发消息。
6. 如果你有勇气，关闭 Tomcat 并创建另一个 WAR 文件副本，命名为 `messaging3.war`。重新启动并重复测试过程，同时也尝试第三个 URL。
7. 测试完成后，确保删除 Tomcat `webapps` 目录中的 `messaging1.war` 文件和对应的 `/messaging1` 目录。

# 使用 AMQP 分发事件

由于我们有许多方法可以在应用程序中实现分布式消息，本书只能涵盖其中少数。在上一节中，你探索了使用直接连接，这形成了一个基础图。这种配置的问题是可扩展性不高。它在小集群中有效，但连接数随着集群规模的增加呈非线性增长。如果你在学校学过图论，你会记得具有 $n$ 个顶点的连通图 $K_n$ 的边数为 $\frac{n(n-1)}{2}$。虽然四节点集群可能只有六个连接，但八节点集群有 28 个连接，16 节点集群有 120 个连接。如果你运行一个数百个节点的集群，你面对的是数万个连接（每个节点数百个）。此时你应该理解可扩展性问题。

其他消息协议如 WAMP、JMS 和 AMQP 的扩展性好得多，因为集群中的所有消息都通过中央代理。结果是，该配置形成了一个 1 正连通图（每个节点有一个连接），代理除外（有 $n-1$ 个连接），总连接数等于节点数减去代理数。这在图 18-5 中得到了演示，显示了一个带代理的六节点集群。为了高可用性和扩展性，你可以在集群中安排多个代理以形成单个逻辑代理。这略微增加了总连接数，甚至没有增加。

![](img/4677f981a0e1067137bb55a122f849d_570_0.png)

图 18-5

JMS 是 Java EE 环境中此类自然选择。然而，在独立应用程序或 Tomcat 等 Servlet 容器中配置 JMS 非常困难，因为它需要添加库并大量更改 Tomcat 配置。因此，本节介绍了使用高级消息队列协议 (AMQP) 在应用程序中进行分布式消息的方法。

在这种配置中，代理不管理发布/订阅主题。相反，它将所有消息传递给所有节点，Spring Framework（作为本地代理）将正确的消息传递给订阅者。你也可以直接使用 AMQP 而不通过 `ApplicationListeners` 来管理代理上多个主题的发布/订阅。虽然本节没有涵盖第二种选择，但从代码中可以清楚地看到你如何实现这一点。

# 配置 AMQP 代理

有多种 AMQP 提供者实现可供你在环境中选择使用的 AMQP 代理时提供选项。目前最流行且强大的实现是 RabbitMQ，它是一个免费开源的 AMQP 服务器，需要时还提供企业支持。本节并不作为 RabbitMQ 的配置和管理指南，但它将引导你在 10 分钟内下载、安装并以默认配置使用它。

RabbitMQ 用 Erlang 编写，Erlang 是一种具有垃圾回收和虚拟运行环境的并发语言，类似于 Java（尽管语法差异巨大）。在安装 RabbitMQ 之前，必须下载并安装 Erlang。在许多 Linux 发行版中，可以使用包系统，但在 Red Hat/Fedora/CentOS 系统上，你需要从网站下载。

此命令启用 Web 管理控制台，该功能默认是禁用的。

5. 如果你在 Windows 中安装了 RabbitMQ，请打开服务管理器并重启 RabbitMQ 服务。在其他操作系统上，请根据情况启动或重启二进制文件。
6. 此时，你应该能够通过你喜欢的浏览器在 `http://localhost:15672/` 访问 RabbitMQ，用户名和密码均为 `guest`，这是安装时的默认值。如果你无法访问管理控制台，请重新检查你的安装步骤并查阅文档以查看何处出了问题。

你所做的就是让一个基础的 RabbitMQ 服务器运行起来。在生产环境中，当然，你应该锁定安全性并针对性能进行配置微调。

## 创建 AMQP 多路广播器

创建一个使用 AMQP 分发事件的 `ApplicationEventMulticaster` 是简单的。你可以参考可以在 wrox.com code-download 下载的 AMQP-Messaging 项目。该项目与你之前过的 WebSocket-Messaging 项目非常相似，并且包含了相同的 `ClusterEvent`。它没有 `ClusterManager` 或 `ClusterMessagingEndpoint`。所有的逻辑都包含在列表 18-4 的 `ClusterEventMulticaster` 中，其 `multicastEvent` 方法与 WebSocket-Messaging 中的方法完全相同。

列表 18-4: ClusterEventMulticaster.java

```java
public class ClusterEventMulticaster extends SimpleApplicationEventMulticaster {

    private static final Logger log = Log.getLogger();

    private static final String EXCHANGE_NAME = "AMQPMessagingTest";

    private static final String HEADER = "X-Wrox-Cluster-Node";

    private final AMQP.BasicProperties.Builder builder =
        new AMQP.BasicProperties.Builder();

    private Connection amqpConnection;

    private Channel amqpChannel;

    private String queueName;

    private Thread listener;

    private boolean destroyed = false;

    @Override
    public final void multicastEvent(ApplicationEvent event) { ... }

    protected void publishClusteredEvent(ClusterEvent event) throws IOException {
        this.amqpChannel.basicPublish(EXCHANGE_NAME, "", this.builder.build(),
            SerializationUtils.serialize(event));
    }

    @PostConstruct
    public void setUpRabbitConnection() throws IOException {
        ConnectionFactory factory = new ConnectionFactory();
        factory.setHost("localhost");
        this.amqpConnection = factory.newConnection();
        this.amqpChannel = this.amqpConnection.createChannel();
        this.amqpChannel.exchangeDeclare(EXCHANGE_NAME, "fanout");
        this.queueName = this.amqpChannel.queueDeclare().getQueue();
        this.amqpChannel.queueBind(this.queueName, EXCHANGE_NAME, "*");
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
                Object header = delivery.getProperties().getHeaders().get(HEADER);
                if (header == null || !header.toString().equals(this.queueName)) {
                    ClusterEvent event = (ClusterEvent) SerializationUtils
                        .deserialize(delivery.getBody());
                    event.setRebroadcasted(true);
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



大部分有趣的工作发生在 `setupRabbitConnection` 和 `listen` 方法中。`shutdownRabbitConnection` 方法仅负责关闭资源。`setupRabbitConnection` 首先建立到本地 RabbitMQ 服务器的连接并打开通道。然后它设置了一个名为 `AMQPMessaging` 的交换机并将其设置为 `fanout`。

## 使用 AMQP 分发事件

> 注意：交换机（exchange）是定义消息如何传递到队列的机制。`Fanout` 模式意味着所有发布的消息都会被传递到队列。你可以在 RabbitMQ 文档中学习更多关于这些主题以及通道的知识。进一步探索这些内容超出了本书的范围。

接下来，此方法请求 RabbitMQ 创建一个随机队列（该节点特有），并将队列绑定到通道和交换机。用于创建并分配自定义 `X-Rabbit-Cluster-Node` 头的属性构建器会在发送每条消息时使用。当接收到消息时，节点可以忽略它自己发送的消息。最后，它启动一个监听器来监听传入的消息。

## 运行启用 AMQP 的应用程序

你可以按照测试 WebSocket-Messaging 的完全相同测试 AMQP-Messaging ：

1. 确保 RabbitMQ 正在运行。
2. 确保 IDE 中已配置应用程序部署到 Tomcat 服务器的 `/messaging1`。
3. 构建 WAR 文件构件，将其重命名为 `messaging2.war`，并复制到 Tomcat 的 `webapps` 目录。
4. 启动 IDE 中的 Tomcat，`/messaging1` 和 `/messaging2` 应该启动。
5. 导航到 http://localhost:8080/messaging1 和 http://localhost:8080/messaging2 并交替点击注销和登录链接。你应该看到与使用 WebSocket-Messaging 应用程序时相同的日志条目。再次，你可以创建并部署名为 `messaging3.war` 的第3个 WAR 文件来尝试模拟包含三个节点的集群。
6. 在 Tomcat 运行时，进入 RabbitMQ Web 管理控制台并点击顶部的 Queues 菜单项。你会看到一个类似于图 18-6 的屏幕，显示了 RabbitMQ 为你的应用程序实例创建的随机队列。
7. 测试完成后，确保从 Tomcat 的 `webapps` 目录删除 `messaging.war` 文件和相应的 `/messaging` 目录。

## 540 | 第 18 章 使用消息和集群实现灵活性与可靠性

![](img/4677f981a0e1067137bb55a122f8498d_575_0.png)

### 总结

在本章中你涵盖了大量内容。介绍了 EE Web 应用程序集群的概念和挑战，并学习了赋予这一企业级应用重要功能的技术和方法。你探索了发布-订阅消息模式，并学习了如何使用 Spring 的 `ApplicationEvent` 和 `ApplicationListener` 在本地实现发布-订阅。你还学习了 WebSockets、WAMP、JMS 和 AMQP，以及这些技术如何帮助你跨集群发送应用程序消息。你探索了集成 Spring 消息和 WebSockets 以直接在应用程序之间发送消息。然后你探索了为什么该配置的可扩展性不理想。最后，你学习了如何安装 RabbitMQ 服务器并使用 Spring 应用程序消息来代理 AMQP 消息。

到此本书第二部分结束，该部分向你介绍了 Spring Framework及其及其强大的功能。在第三部分中，你将学习如何在 Spring 应用程序中使用 Java Persistence API 和 Hibernate ORM 将应用程序数据持久化到数据库中。

![](img/4677f981a0e1067137bb55a122f8498d_578_0.png)

# 介绍 Java Persistence API 和 Hibernate ORM

## 本章内容

- 理解数据持久化
- 什么是对象关系映射（ORM）？
- 理解 Hibernate ORM
- 如何准备关系型数据库
- 如何在本章中使用 Maven 依赖

## 本章 WROX 代码下载

本章没有代码下载。

## 本章的新 Maven 依赖

本章没有 Maven 依赖。请继续使用之前章节引入的 Maven 依赖。

## 什么是数据持久化？

除少数例外外，每个应用程序都需要某种形式的持久化。但持久化究竟是什么？简单来说，持久化就是让某种形式的数据在程序的多次执行之间持续。从这个意义上说，持久化是一种持久化，以便你在程序执行后对其进行分析。事实上，你可以将信息持久化到平面文件、XML 文件、JSON 文件、数据库或其他任何媒介中。

通常，持久化并不是指日志。相反，它是将应用程序中的实体保存到某些存储介质中。实体可以是任何内容——人、用户、购物车、订单等等。列表层出不穷，整本书也长度长到无法列举所有。在软件开发中，数据通常具有意义。实体封装了程序使用的属性。在你的本书第二部分构建的 Spring Framework 中，控制器（controllers）创建实体并将其交给服务（services）以应用业务规则，然后使用 map 在内存中存储实体。同样，当你的控制器接收一个或多个实体时，它们从仓库（repositories）检索实体。Java 实体是 POJO；在 C# 中实体是 POCO。其他语言对这些类型有相应的术语。然而，内存持久化映射在现实世界中是不够的，因为数据存在于节点上，并且会在应用程序关闭时消失。在考虑如何持久化数据时，你有许多选择，其中一种选择就是对于某些特定用例来说是万能的“灵丹银弹”。

## 平面文件实体存储

实体持久化的自然方法是使用操作系统提供的原生文件系统。一种可能的场景是为每种实体类型创建一个目录，每个文件代表该实体的不同名称。代理键（SK）是实体的唯一标识符，允许你在存储介质中定位它。作为文件名，SK 充当某种索引，以便找到实体。存储在文件中的数据包含许多格式。它可以被持久化为 Java 序列化对象（或其他语言），或使用键值对、XML 或 JSON 表示。这种格式能够实现高效的存储和检索，但完全限制了可移植性。只有 Java 应用程序可以访问该实体。无论何种方式，与其替代方案相比，平面文件存储都非常缓慢且难以管理。每个 CRUD 操作都会导致打开文件、立即向文件系统写入数据并关闭文件。开销是巨大的，尤其是当定位操作涉及不仅是代理键时（例如根据实体的属性进行搜索）。由于由于原因，平面文件实体存储仅适用于最小且最基础的情况，例如应用程序设置。

## 结构化文件存储

结构化文件存储在许多方面与平面文件存储相似。它使用操作系统的文件系统将应用程序数据存储在文件中，CRUD 操作通常会导致反复打开和关闭文件。然而，结构化文件存储系统通常不是依赖目录和单个文件来存储实体，而是创建一个大文件，使用程序可以理解的预定义结构将许多实体存储在一个文件中。通常不是每种实体类型一个目录，而是每种实体类型一个文件。这种方法的好处是搜索操作高效得多；它们针对单个文件进行，而不是针对成百上千个文件。然而，通过代理键进行单独查找可能会受到这种安排的影响。通常需要创建一个某种类型的较小的索引文件，以便更容易识别大文件中记录的位置。

如果你觉得这听起来像是一个关系型数据库，那么你是正确的。许多关系型数据库的工作方式非常相似。Brief 作为最早的数据库类型之一，使用索引顺序访问方法（ISAM）在文件中存储条目。关系型数据库和结构化文件系统之间存在许多区别，即结构化文件存储往往是专有的且直接在应用程序代码中发生，而关系型数据库基于某种可移植的标准，通常运行在另一个应用程序内部。此外，结构化存储忽略了实体之间的关系。从这个意义上说，Brief 是一个结构化存储系统而不是关系型数据库；但是它具有今天关系型数据库中事务的概念。

## 关系型数据库系统

如果你正在阅读这些，可能已经了解了关系型数据库管理系统（RDBMS）。在本章和下一章必须了解它们。关系型数据库以表的形式存储条目，每个表仅存储一种类型的实体（尽管复杂实体可能包含来自多个表的数据）。这些表由模式（schema）组成，定义了各种字段或列的名称、类型和大小。你不能在不存在列的表中存储记录，也不能在列未定义 NULL 的表中存储空值的记录。通常，一个表包含一个主键列（或有时是形成复合主键的列），它充当代理键。你使用 ANSI 标准结构化查询语言（SQL）与关系型数据库交互，这种语言设计用于以一种特殊的方式操作表模式和数据。

遗憾的是，没有关系型数据库完全遵守 ANSI 标准，大多数数据库定义了自己不被其他系统支持的专用扩展。例如，Oracle 使用 PL/SQL，SQL Server 使用 T-SQL，而 PostgreSQL 使用 PL/pgSQL。这些扩展提供了强大的功能，但也使得在不同数据库系统之间进行迁移变得困难。关系型数据库仍然是最受欢迎的原因有几点。首先，SQL 是一种标准语言。其次，关系模型非常强大且灵活。第三，关系型数据库非常成熟并得到了良好支持。关系型数据库有许多替代方案，例如 NoSQL 数据库，它们对于某些用例更好。然而，由于其可靠性和数据完整性特性，关系型数据库仍然是大多数应用程序的选择。使用关系型数据库有许多原因，如-

与日志和审计相关的数据。一些流行的文档数据库包括 MongoDB、Apache CouchDB 和 Couchbase Server。

另一种流行的 NoSQL 数据库类型是键值存储。它顾如其名，以一种非常扁平化的方式存储键值对。这可以类比为 Java 的 `Map<String, String>`，尽管某些键值存储是多变量的，存储数据的方式更像 `Map<String, List<String>>`。一些流行的键值存储包括 Apache Cassandra、Firebase、Amazon DynamoDB、memcache、Redis、Apache River 和 MongoDB。（是的，某些文档数据库也兼作键值存储使用。）

图数据库是关注对象之间关系的 NoSQL 数据库。在图数据库中，对象具有属性（属性），属性与其他对象建立关系，而这些关系也具有属性。数据以图的形式进行存储和表示，实体之间的关系是自然存在的，而不是通过外键创建的人为方式。这使得解决“六隔之远”问题变得简单，能够找到在插入时可能未被检索到的实体之间的关系。也许最流行的图数据库是 Neo4j。尽管 Neo4j 是用 Java 编写的，且由于其名称，它可以在任何平台上运行。然而，它非常适合 Java 应用。

NoSQL 数据库并不按照 ANSI SQL 等标准进行操作。因此，没有通用的方法（JDBC）可以访问任何两个 NoSQL 数据库。这是使用 NoSQL 数据库的固有缺点，但也有其优点。每个 NoSQL 数据库都有自己的客户端库，这些客户端中的大多数都可以接收 Java 对象并将它们直接存储在数据库中，无论数据库要求何种格式。这消除了将 POJOs 映射到“表”以及将属性映射到“列”的任务，从而使 NoSQL 成为关系型实体存储的一种具有吸引力的替代方案。每个 NoSQL 数据库的方法都不同，由于 NoSQL 客户端库消除了对对象关系映射器（ORM）的需求，本书将不再涵盖这些内容。

## 什么是对象关系映射器？

截至目前，关系型数据库仍是最常用的数据库。你可以发现它们支撑着所有主要的企业级软件，存储着从应用设置到审计记录的所有内容。然而，在关系型数据库中存储面向对象的实体往往并非易事，需要大量的重复代码以及数据类型之间的转换。对象关系映射（或 O/M）的创建是为了解决这个问题。O/RM 在关系型数据库中持久化实体并从中检索实体，而无需程序员编写 SQL 语句，并将属性翻译为语句参数，以及将结果列翻译为实体属性。

本章将介绍五种对象关系映射器以及如何使用它们在你的应用程序中持久化实体。在真正认识出 O/RM 如何帮助你之前，你首先需要理解所在所在。

## 理解实体持久化问题

为了理解持久化和检索实体所需的代码规模，请考虑以下存储库方法，它从数据库中检索产品记录并将其数据拷贝到一个假设的 `Product` 对象中。

```java
public Product getProduct(long id) throws SQLException {

    try (Connection connection = this.getConnection();
         PreparedStatement s = connection.prepareStatement(
            "SELECT * FROM dbo.Product WHERE ProductId = ?")) {

        s.setLong(1, id);

        ResultSet r = s.executeQuery();

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
```

如你所知，这个图中缺少了一些东西。例如，这个方法没有错误处理，而在现实中是需要的。此外，产品通常拥有比这里多多的属性——这里的代码非常保守。这里创建一个新的 `Product`：

```java
public void addProduct(Product product) throws SQLException {

    try (Connection connection = this.getConnection();
         PreparedStatement s = connection.prepareStatement(
            "INSERT INTO dbo.Product (Name, Description, DatePosted, " +
            "Purchases, BulkPrice, MinimumUnits,Sku, EditorsReview) VALUES (?, ?, ?, ?, ?, ?, ?)", +
            new String[] { "ProductId" }) {

        s.setString(1, product.getName());

        s.setString(2, product.getDescription());

        s.setObject(3, product.getDatePosted(), java.sql.Types.TIMESTAMP);

        s.setLong(4, product.getPurchases());

        s.setDouble(5, product.getPrice());

        s.setDouble(6, product.getBulkPrice());

        s.setInt(7, product.getMinimumUnits());

        s.setString(8, product.getSku());

        s.setString(9, product.getEditorsReview());

        if(s.executeUpdate() != 1) 

            throw new SaveException("Failed to insert record.");

        try (ResultSet r = s.getGeneratedKeys()) {

            if (!r.next()) {

                throw new SaveException("Failed to insert record.");

            }

        }

    }

}
```

## 对象关系映射器是什么？

```java
throw new SaveException("Failed to insert record.");

try (ResultSet r = s.getGeneratedKeys()) {

    if (!r.next()) {

        throw new SaveException("Failed to insert record.");

    }

}
```



## JPA 提供了标准的 O/RM API

最早的 O/RM 之一是 TopLink，它于 20 世纪 90 年代初为 Smalltalk 开发。其开发者 The Object People（因此 TopLink 中的 Top）在 1998 年发布了 Java 版 TopLink，并于 2002 年 Oracle 公司收购了 TopLink 用于 Oracle Fusion Middleware。通过多年以及向 Sun Systems 最终向 Eclipse Foundation 代码捐赠，TopLink 变成了 EclipseLink。（不过，TopLink 至今作为 Oracle 的产品存在。）除了将对象映射到关系型数据库外，TopLink 和 EclipseLink 还将对象映射到 XML 文档。

另一个 O/RM——iBatis 起于 2002 年，并作为 Apache 软件基金会项目持续到 2010 年，当时它被退并在 Google Code 上被 MyBatis 取代。iBatis 是为 Java、.NET 和 Ruby 编写的，而 MyBatis 是为 Java 和 .NET 编写的。Hibernate ORM 可能是最流行的 Java/ORM 之一，它于 2001 年启动并不断演进。Hibernate 查询语言 (`HQL`) 解析 SQL，但它用于查询实体而不是表。NHibernate 是 `Hibernate ORM` 的 .NET 移植版，为 .NET 平台带来了类似的功能。

拥有许多不同 ORM 的问题在于灵活性。例如，使用 `Hibernate` 的应用程序在不对分层进行重大重构的情况下，无法更改 `EclipseLink` 或 `MyBatis`。Java 持久 API（`JPA`）的创建是为了解决这一问题，并为使用 O/RM 技术在关系型数据库中进行 Java 对象持久化提供一种标准 API。仅针对 Java Persistence API 编程允许您在需要时以最小的精力切换 O/RM 实现。

`JPA 1.0` 于 2006 年作为 `JSR 220` 的一部分引入，属于 Java 5 框架的一部分。它统一了 Java Data Objects (`JDO`) API 和 EJB 2.0 容器管理持久化 (`CMP`) API，并包含了许多受 `TopLink` 和 `Hibernate ORM` 启发或基于它们的功能。它还定义了 Java Persistence Language (`JPQL`)，一种与 `HQL` 几乎相同的查询语言。它存在一些缺点：

- 它缺乏一种在没有 `JPQL` 的情况下不通过复杂条件来查找对象的标准方法。许多开发者倾向于使用没有查询语言的纯 Java 方法，他们经常使用特定提供程序的特性，如 `Hibernate` 的 `Criteria`。
- `JPA` 的核心原则之一是能够将有限的 SQL 类型转换为 Java 数据类型，例如基本数据类型及其包装类、`String`、`Enum`、`Date`、`Calendar` 等。`JPA` 规定了一组所有实现都必须支持的数据类型转换，但遗憾的是，它没有提供定义到其他数据类型转换器的方法。某些实现通过依赖特定实现来支持额外的数据类型（例如，`Hibernate ORM` 支持所有 Joda time 类型）。实现还提供了一种指定自定义数据类型的方法，但这会将你绑定到特定的实现。
- `JPA 1.0` 不支持其他实体内的实体集合、多级嵌套实体以及有序列表。

`JSR 317` 于 2009 年作为 Java EE 6 的一部分标准化了 `JPA 2.0`，并对实体集合、嵌套实体和有序列表提供了更好的支持。它还增加了根据定义的实体自动生成数据库模式的支持，并与 Bean Validation API 整合了一。可能最重要的是，它添加了一个标准的 criteria API，允许在不使用 `JPQL` 的情况下进行实体查找。遗憾的是，它缺乏对自定义数据类型转换的支持，导致许多开发者继续依赖 `Hibernate` 的 `UserType` 等实现特性。`JPA 2.1` 终于满足了对自定义数据类型的需求。`JPA 2.1` 作为 Java EE 7 的一部分于 2013 年通过 `JSR 338` 标准化。除了自定义数据类型，它还包含了对 `JPQL`、存储过程的增强以及对 `JPA 2.0 criteria` 的改进以支持批量更新和删除操作。

![](img/4677f981a0e1067137bb55a122f8498d_586_0.png)

Sun 的 GlassFish 应用服务器包含了 `JPA 1.0` 的参考实现，基于 Oracle 捐出的 `JPA 1.0` 代码。Sun 将代码捐赠给了 Eclipse，TopLink 变成了 `EclipseLink`。尽管 `Hibernate` 极受欢迎，`EclipseLink` 仍被选为 `JPA 2.0` 和 `2.1` 的参考实现。`BambooJPA`、`DataNucleus`、`EclipseLink`、`Hibernate`、`ObjectDB`、`OpenJPA`、`IBM WebSphere` 和 `Versant` 只是 `JPA 2.0` 的提供者。写本文时，只有 `EclipseLink`、`DataNucleus` 和 `Hibernate` 发布了 `JPA 2.1` 实现。

> `JPA` 实现使用 `JDBC` 执行 SQL 语句，但永远不需要处理这些。你将始终使用 Java Persistence API，永远不会直接使用 `JDBC` API。

## 为什么选择 Hibernate ORM？

在本书中，你使用 `Hibernate ORM` 作为示例项目的 `JPA` 实现。这看起来可能很奇怪，因为 `Hibernate` 并不是原始的 Java O/RM，也不是 `JPA` 的参考实现——这两者都属于 `EclipseLink`。然而，`Hibernate` 是一个非常成熟且稳定的项目，拥有庞大的社区和数千篇教程文章。当你需要时，可以轻松获得 `Hibernate` 的帮助，但 `EclipseLink` 的全球知识库并不像以前那样简单（`Hibernate` 也是作者所熟悉的）。

`Hibernate ORM` 还支持集合的懒加载，而无需操作实体的字节码。相反，`EclipseLink` 必须将字节码装饰织入你的实体中以实现这一点，而且配置起来可能很复杂。好消息是，你不需要因为本书是这样做就使用 `Hibernate`。你将与 Java Persistence API 工作，因此你可以随地轻松切换到不同的 `JPA` 实现。

## Hibernate ORM 简览

接下来的几章将重点关注如何使用 Java Persistence API 在应用程序中持久化实体。你不会直接使用 `JPA` 提供程序实现（`Hibernate ORM`）。事实上，你在书中使用的提供程序库在 Maven 文件中具有运行时范围（`runtime scope`），这阻止了你直接使用它们。但在某些情况下，提供程序是必要的。

## 使用映射文件

回想上一节，在持久化 O/RM 之前，必须先定义映射。从 `Hibernate 3.0` 开始，你可以使用注解代替 XML 映射。虽然可以在单个文件中包含多个映射，但最佳实践是每个实体使用一个文件。例如，该类的映射文件为 `Product.hbm.xml`。另一种做法是将映射文件与实体类一起放在包结构中，因此 `com.wrox.entities.Product` 的文件将是 `com/wrox/entities/Product.hbm.xml`。

## Hibernate ORM 简述

你可能注意到本节提到了将“字段”映射到数据库列。在这种情况下，“字段”一词指的是 Java 属性（带有访问器和变器器的实例字段）。在 `JPA` 和 `Hibernate ORM` 中，所有映射的字段默认都是 JavaBean 属性。（然而，你可以指定不同的行为。字段名通过从 getter 中删除“get”或“is”并将首字母转换为小写来确定。字段名不是通过检查底层实例字段来确定的。）尽管被称为“字段”听起来是如此，但 `JPA` 和 `Hibernate` 实体字段不需要底层字段。匹配的 getter 和 setter 就足以被视为实体字段。

在 `<class>` 内部，`<id>` 指定了单列单字段的代理键，而与之互斥的 `<composite-id>` 指定了多列多字段的代理键。一个或多个 `<property>` 元素将类字段映射到数据库列。对于更多用例，映射完全可以使用 `<property>` 的属性表示，但对于更复杂的情况，你可能需要使用 `<column>` 元素。

```xml
<property name="purchases" column="Purchases" type="long" />
<property name="price" column="Price" type="double" />
<property name="BulkPrice" column="BulkPrice" type="double" />
<property name="minimumUnits" column="MinimumUnits" type="int" />
<property name="sku" column="Sku" type="string" length="12" />
<property name="editorReview" column="EditorsReview" type="string" length="2000" />
</class>
</hibernate-mapping>
```

大部分内容应该是显而易懂的。`productId` 被映射到 Microsoft SQL Server 中的 Product 列和标识生成器、MySQL 中的 `Auto_INCREMENT` 列等。其他属性都是映射到列的简单字段。你还可以使用 `<map>`、`<list>` 和 `<set>` 属性，以及诸如 `<one-to-many>` 和 `<many-to-one>` 等元素将实体相互关联。在 `Hibernate ORM 4.3` 用户手册中，有几十页的映射示例和说明。由于在书中只使用了 `JPA` 映射，因此将涵盖进一步的示例。

## 理解 Session API

在 `Hibernate ORM` 中工作的主要单元是 `org.hibernate.Session` 接口。`Hibernate Session` 完全不像 `HttpSession` 或 `WebSocket Session`。`Hibernate Session` 代表事务从开始到结束的生命周期。取决于你的应用程序的架构，它可能不到一秒，也可能是几分钟；在 Web 应用程序中，它可能是请求中的多个事务之一、持续整个请求的事务，或跨越多个请求的事务。`Session` 不是线程安全的，必须一次只能在一个线程中使用，它负责管理实体的状态。

当从数据库检索一个实体时，它会被附加到 `Session` 中，并在 `Session`（及其事务）结束之前一直是 `Session` 的一部分。这样，只要在 `Session` 的生命周期内访问，实体的属性就会以懒加载的方式加载。同样，当实体被添加或更新时，这些更改也会附加到 `Session` 中；当实体从数据库中删除时，它会从 `Session` 中移除。这与 `JPA` 的 `EntityManager` 工作原理非常相似。你稍后会学习。

使用 `Session` 实例上的 `get` 方法通过代理键查找实体是简单的：

```java
return (Product) session.get(Product.class, id);
```

如果指定的属性不存在，`get` 简单返回 `null`。要添加新实体，将其传递给 `save` 方法。

```java
session.save(product);
```

此方法返回所添加实体的生成的 ID；尽管你通常不需要使用返回的值。调用此方法后，你传递给方法的实体的 `id` 属性将已更新为生成的 ID。`save` 的替代方案是 `persist`，它也会添加新实体。关键区别是 `persist` 更安全：如果事务已经关闭，`persist` 永远不会导致 `INSERT`，而 `save` 会导致事务之外的插入。因此，`persist` 通常是首选方法。然而，`persist` 触发的 `INSERT` 不能保证在刷新（`flush`）时间之前执行，`persist` 不返回生成的 ID，且当 `persist` 完成时，实体的 ID 属性可能已未设置。如果你立即需要 ID，应该在保存实体后 `flush` Session：

```java
session.persist(product);
session.flush();
```

刷新 `Session` 仅仅会导致任何悬挂的语句立即执行；它不会结束事务。因此，你可以在 `Session` 的生命周期内根据需要调用多次 `flush`。关闭 `Session` 或提交其事务会自动刷新 `Session`。刷新 `Session` 的背后的原理在于 `Hibernate` 如何查询状态。在涉及多个账户的事务中，这些操作实际上并不是按照你指定的顺序执行的。在刷新时间，自上次刷新以来的所有操作将按照以下顺序执行：

- 按照添加的顺序执行所有实体插入
- 按照更新的顺序执行所有实体更新
- 按照删除的顺序执行所有集合删除
- 按照执行的顺序执行所有集合插入、更新和删除
- 按照添加的顺序执行所有集合插入
- 按照删除的顺序执行所有实体删除

因此，如果你需要保证某个操作或某些操作在另一个操作或操作之前执行，你必须在它们之间调用 `flush`。唯一的例外是 `save`，它无论是否刷新都会立即执行实体的 `INSERT`。（但记住，`persist` 受刷新的影响。）

> **警告** 刷新仅影响将 `Session` 的更改写入数据库。你对 `Session` 进行的更改会反映在内存中。请小心这种行为，因为可能是许多混乱的根源。

更新实体有点难理解。你可以像下面的代码片段中那样使用 `update` 方法：

```java
session.update(product);
```

然而，这仅当实体尚未附加到 `Session` 时才有效（如果你在事务期间没有对该实体执行过 `get`、`save` 或 `persist`）。如果实体已经附加，`update` 将抛出异常。正因如此，最好始终使用 `merge` 方法，无论实体是否已附加到 `Session`，它都能正常工作：

```java
session.merge(product);
```

删除实体非常非常直接：

```java
session.delete(product);
```

实体剔除（`eviction`）是 `Hibernate` 中一个很有趣的概念。调用 `evict` 方法会导致实体从 `Session` 中解离，但它不会像删除实体那样产生任何数据库的更改。

```java
session.evict(product);
```

如果你想剔除所有附加到 session 的实体，可以调用 `clear` 方法。注意，`evict` 会取消被剔除实体任何尚未刷新的更改。同样，`clear` 会取消 `Session` 中所有实体（包括插入和删除）的所有尚未刷新的更改。

使用代理键获取单个实体并不是你需要执行的查询类型。你将需要使用查询查找单个实体和实体集合。你可以使用 `org.hibernate.Criteria` API 或 `org.hibernate.Query` API 完成这些任务。以下两个返回语句产生完全相同的实体：

```java
return (Product) session.createCriteria(Product.class)
    .add(Restrictions.eq("sku", "sku"))
    .uniqueResult();
```

```java
return (Product) session.createQuery("FROM Product p WHERE p.sku = :sku")
    .setString("sku", "sku")
    .uniqueResult();
```

注意，在 `HQL` 查询中，`Product` 指的是实体名称而不是表名，且 `sku` 指的是实体的属性而不是数据库表中的字段。同样，以下两个返回语句都会产生一年内且以 "java" 开头的 `Product` 列表：

```java
return (List<Product>) session.createCriteria(Product.class)
    .add(Restrictions.gt("datePosted",
        Instant.now().minus(365L, ChronoUnit.DAYS))
    .add(Restrictions.ilike("name", "java", MatchMode.START))
    .addOrder("name")
    .list();
```

```java
return (List<Product>) session.createQuery("FROM Product p WHERE
datePosted > :oneYearAgo AND :nameLike ORDER BY name")
    .setParameter("oneYearAgo",
        Instant.now().minus(365L, ChronoUnit.DAYS))
    .setString("nameLike", "*java%")
    .list();
```

使用 `Session` API 还可以做很多事情，但这些基础任务应该能满足你们的需求。

## 从 SessionFactory 获取 Session

`Session` 不会凭空出现。`Session` 与 `JDBC` 数据库连接关联，必须由某些东西创建连接或从 `DataSource` 检索连接、实例化 `Session` 实现并将 `Session` 附加到连接上，然后才能使用。如果当前已经进行了一个 `Session`，则还需要“查找”现有的 `Session`。

## Hibernate ORM 简览

与其在每次执行操作时都创建一个 `Session`，不如使用一个上下文。`org.hibernate.SessionFactory` 接口正是为此而设计的。它包含了几个方法用于构建 `Session`、打开 `Session` 以及获取“当前”`Session`。例如，要打开一个新的 `Session`，可以调用 `openSession` 方法：



Session session = sessionFactory.openSession();

这将打开一个 Session，并配置为 `SessionFactory` 配置了所有默认设置（数据源、拦截器等）。然而，有时有必要重写这些设置。你可能需要使用数据库连接来完成某些特殊目的：

```java
Session session = sessionFactory.withOptions()
    .connection(connection)
    .openSession();
```

或者，你可能需要执行所有的 SQL 语句以便以某种方式对其进行修改。例如，你的映射可能会指定类似 `schema="SCHEMA@"` 的内容，而在运行时你用来自设置、参数或其他变量的值来替换它：

```java
Session session = sessionFactory.withOptions()
    .interceptor(new EmptyInterceptor() {
        @Override
        public String onPrepareStatement(String sql) {
            return sql.replace("@SCHEMA@", schema);
        }
    })
    .openSession();
```

Hibernate ORM 还有无状态会话，由 `org.hibernate.StatelessSession` 表示。`StatelessSession` 特别适用于批量操作，它可以完成 Session 能做的很多工作，但它不会像 Session 那样持有关联的实体。你可以使用 `openStatelessSession` 打开默认的 StatelessSession，并使用 `withOptions` 使用自定义的 StatelessSession。

可能 SessionFactory 最重要的功能之一是它持有和检索“当前”Session 的能力。由于无状态本质，Stateless Session 不具备这种能力。但究竟什么是“当前”Session 呢？与 Session 不同，SessionFactory 是线程安全的，因此“当前”Session 并不简单是使用 Session 打开的那个。相反，“当前”的含义是由提供的 `org.hibernate.context.spi.SessionContext` 实现定义的。最常见的实现是 `org.hibernate.context.internal.ThreadLocalContext`，它在 `java.lang.ThreadLocal` 中存储当前会话。所有对 `getCurrentSession` 的调用都会获取之前在当前线程中打开会话（如果有的话）。

```java
Session session = sessionFactory.openSession();
...
Session session = sessionFactory.getCurrentSession();
```

# 使用 Spring Framework 创建 SessionFactory

SessionFactory 的配置可能很复杂，在 Web 应用程序中，在每个请求结束时正确清理资源至关重要。未能这样做可能会导致内存泄漏或（更糟糕的）跨应用数据泄漏。与许多其他事物一样，Spring Framework 替你创建 SessionFactory 并代表你管理 Session 和事务的创建与关闭，这样你就不需要担心在应用程序到处编写重复的代码。在 Spring 中配置 Hibernate ORM 时，你使用两个 Spring 类之一来创建 SessionFactory。

如果你使用 XML 配置 Spring，最简单的方法是定义一个 `org.springframework.orm.hibernate4.LocalSessionFactoryBean`，这是一种特殊的 Spring Bean，用于创建并返回一个 SessionFactory。`LocalSessionFactoryBean` 还实现了 `org.springframework.orm.dao.PersistenceExceptionTranslator`，因此它可以作为一个翻译器，将 Hibernate ORM 异常转换为 Spring 通用异常。

当使用 Java 配置时，`org.springframework.orm.hibernate4.LocalSessionFactoryBuilder` 继承自 `org.hibernate.cfg.Configuration`，为在你的 Spring Framework 应用程序中配置 SessionFactory 提供了一些快捷方法。下方的 Java 配置片段所示：

```java
@EnableTransactionManagement
public class RootContextConfiguration
    implements AsyncConfigurer, SchedulingConfiguration {

    @Bean
    public PersistenceExceptionTranslator persistenceExceptionTranslator() {
        return new HibernateExceptionTranslator();
    }

    @Bean
    public HibernateTransactionManager transactionManager() {
        HibernateTransactionManager manager = new HibernateTransactionManager();
        manager.setSessionFactory(this.sessionFactory());
        return manager;
    }

    @Bean
    public SessionFactory sessionFactory() {
        LocalSessionFactoryBuilder builder = new LocalSessionFactoryBuilder(this.dataSource());
        builder.scanPackages("com.wrox.entities");
        builder.setProperty("hibernate.default_schema", "dbo");
        builder.setProperty("hibernate.dialect", MySQL5InnoDBDialect.class.getCanonicalName());
        return builder.buildSessionFactory();
    }
}
```

通过此配置，Spring Framework 可以在调用 `@org.springframework.transaction.annotation.Transactional` 服务或仓库方法之前自动创建一个 Session，并在方法返回后关闭该 Session。如果 `@Transactional` 方法调用了其他 `@Transactional` 方法，当前的 Session 和事务将保持有效。这时，你只需要在仓库中保留一个 `@Injected` 的 SessionFactory，并在需要使用 Session 时调用 `getCurrentSession`。你将在第 21 章学习更多关于 `@EnableTransactionManagement` 和 `@Transactional` 的知识。

# 准备关系型数据库

为了完成并使用书中其余部分的示例和示例项目，你需要访问一个关系型数据库来持久化实体。你可以使用像 HyperSQL 这样 100% Java 的嵌入式数据库，但这违背了替换你到目前为止构建的内存仓库的初衷。相反，如果你使用独立的关系型数据库（如 MySQL、PostgreSQL 或 Microsoft SQL Server），示例将会更加有效。

书中的示例假设你有访问关系型数据库权限；如果没有，请安装一个。此外，示例是针对 MySQL 服务器编写并基于其进行测试的，因为它是目前最流行的免费数据库系统。然而，并没有理由你不能使用任何关系型数据库来完成这些示例。大多数代码都独立于任何特定数据库运行（毕竟，它们是 ORM 的一部分），但在使用配置时，你需要一些独立思考。例如，每当你看到某些特定数据库的内容（如上一节中使用的 `MySQL5Dialect` 类）时，你需要为你的数据库找到合适的替代品。你还需要将 MySQL 的数据库、表和索引创建语句翻译为你数据库的相应语句。

除了展示如何在 Tomcat 中安装 JDBC 驱动程序和创建连接资源外，本节还帮助你安装 MySQL 服务器，以防你尚未访问数据库。如果你计划使用其他数据库，仍然要阅读这一节！它包含了适用于你数据库的重要信息。

## 安装 MySQL 和 MySQL Workbench

要安装 MySQL ，请遵循以下步骤：

1. 前往 MySQL 下载网站，下载 MySQL Community Server 和 MySQL Workbench 产品。
2. 对于 MySQL Community Server，选择合适的平台（Mac OS X、Windows、Linux 等），并下载适用于你平台版本的正确安装程序或存档。
3. 按照你操作系统的安装说明在计算机上安装 MySQL Community Server。安装程序将引导你完成此过程。
4. 如果出现“设置类型”（Setup Type）屏幕，你可以轻松地选择开发者默认（Developer Default），如图 19-1 所示。这将安装开发 MySQL 需要的所有内容，包括在 Windows 系统上的 Microsoft Excel 扩展程序。如果你只想安装某些功能，请选择自定义（Custom）设置类型，并在屏幕上选择你想要的功能，如图 19-2 所示。

> 注意：许多 Linux 发行版在它们的软件包管理系统中提供了 MySQL，使用该方法安装 MySQL 可能更简单。无论你如何安装，都必须使用 MySQL 5.6.12 或更高版本 —— 早期版本不支持后续章节使用的某些功能。从 MySQL 网站下载时，无需创建账户或登录。你可以点击“不用，直接开始下载”链接来跳过此过程。

![](img/4677f981a0e1067137bb55a122f8498d_595_0.png)

**图 19-1**

![](img/4677f981a0e1067137bb55a122f8498d_596_0.png)

**图 19-2**

MySQL Workbench 是一个数据库浏览器和管理工具，类似于 Microsoft SQL Server Management Studio 和 Oracle SQL Developer。书中一些示例和截图将指示你对你的 MySQL 数据库执行查询，并展示结果在 Workbench 中的预期样式。当然，你可以使用任何你喜欢的工具来执行这些任务。如果你运行了 MySQL 服务器的安装程序并且它安装了 Workbench，那么你就不需要进行任何操作来安装 Workbench。否则，若要下载并安装 Workbench，你应该选择合适的平台，并为你的平台版本下载正确的安装程序或二进制文件。安装 Workbench 的过程比安装 MySQL Community Server 要简单，而且 Workbench 通常不在标准的包管理仓库中。

在大多数情况下，你的 MySQL Community Server 在安装后应该已经就绪了。对于开发目的，它不需要额外的配置即可开始；但是，默认配置没有针对性能进行优化，也不安全。默认配置应足够用于书中的示例并执行书中介绍的任务。不过，你需要创建一个用户名和密码，你的应用程序可以通过 JDBC 访问数据库。

> 注意：管理 MySQL Community Server 的细节超出了本书的范围，但 MySQL 网站有大量的资源可以帮助你配置它以满足你的需求。

要创建此用户名和密码，请使用 MySQL Workbench 并连接到你的本地 MySQL 安装。如果你在安装期间没有设置 root 密码，则 root 密码默认为空。

在查询编辑器中，输入以下语句并点击执行图标执行它们：

```sql
GRANT ALL PRIVILEGES ON *.* TO 'tomcatUser'@'localhost'
IDENTIFIED BY 'password1234';

GRANT ALL PRIVILEGES ON *.* TO 'tomcatUser'@'127.0.0.1'
IDENTIFIED BY 'password1234';

GRANT ALL PRIVILEGES ON *.* TO 'tomcatUser'@'%'
IDENTIFIED BY 'password1234';

FLUSH PRIVILEGES;
```

这创建了一个用户，你可以用同一台机器上的 Tomcat 服务器与之连接。当然，该用户被授予了大量的权限。在生产机器上，你可能希望将其权限限制在单个数据库，并且可能只允许数据操作而禁止模式操作。对于开发机来说，这足够了。

## 安装 MySQL JDBC 驱动程序

MySQL 与其他关系型数据库一样，提供了 JDBC 驱动程序从 Java 连接 MySQL 数据库。你下载此驱动程序（JAR 文件）并将其放在你的 Tomcat 安装中，以便你可以在应用程序中使用它。这可能让你感到意外，因为其他 JAR 文件通常直接打包在程序的 `/WEB-INF/lib` 中，但对于 JDBC 驱动程序永远不要这样做，原因有二：

- 最重要的是，这样做会导致内存泄漏。JDBC 驱动程序会自动注册到 `java.sql.DriverManager` 中，它是 Java SE 核心库的一部分。如果你的应用程序在 `/WEB-INF/lib` 中使用 JDBC 驱动程序，`DriverManager` 将永久持有驱动类，即使你的应用程序被卸载。应用程序服务器随后无法完全卸载你的应用程序，从而导致内存泄漏。
- 让应用程序服务器管理你的 JDBC DataSource 是一种最佳实践。应用程序服务器内置了管理连接池的系统，可以提高应用程序中数据库连接的性能。为了让服务器能够管理这些连接，你必须在应用程序服务器类加载器中加载 JDBC 驱动，而不是在 Web 应用程序类加载器中加载。

在 Tomcat 中安装 MySQL JDBC 驱动程序极其简单。在之前提到的 MySQL 下载网站上，找到 Connector/J 项目。这就是 JDBC 驱动程序。它是平台无关的，因此你只需要下载 ZIP 或 TAR 压缩包（取决于哪一个在你电脑上使用最方便）。从压缩包中提取 JAR 文件，并将其复制到 `C:\Program Files\Apache Software Foundation\Tomcat 8.0\lib`（或你 Tomcat 安装的对应目录）。

就是这样。下一次 Tomcat 启动时，MySQL JDBC 驱动程序将对所有 Web 应用程序可用。

## 关于 Maven 依赖的说明

> 警告：截至本书时，MySQL JDBC 驱动程序大多与 JDBC 4.1 兼容，这是 Java 7 的一部分。Java 8 包含了 JDBC 4.2。JDBC 4.2 的唯一显著变化是增加了 Java 8 日期时间和类型用于 SQL DATE、TIME 和 DATETIME 类型。MySQL 驱动程序尚未兼容 JDBC 4.2，你目前还无法直接在 JDBC 语句和结果集中使用 Java 8 日期和类型——JDBC 厂商通常在 Java/JDBC 版本发布后 6 个月到若干几年后发布新版本的驱动程序，也可能不发布。当你读到这里时，MySQL 驱动程序可能已经符合 JDBC 4.2 标准。确保你下载最新版本并咨询 Connector/J 文档查看它是否符合 JDBC 4.2 标准。此警告也适用于你使用的任何其他 JDBC 驱动程序。

## 在 Tomcat 中连接资源

在 Tomcat 中创建连接池 DataSource 是非常直观的，只需要几分钟。当你为示例或示例项目使用新数据库时，本书指示你创建一个 Tomcat 连接资源。你可能需要经常回来看这一节以记住如何操作。与其在每次需要时都创建一个新资源，导致在书结束时拥有几十个资源，这样做也可以是：

1. 在你喜欢的编辑器中打开 `context.xml`。
2. 在开始和结束之间添加 `<Resource>` 元素。

```xml
<Resource name="jdbc/DataSource" type="java.sql.DataSource" maxActive="20" maxIdle="5" maxWait="10000" username="tomcatUser" password="password1234" driverClassName="com.mysql.jdbc.Driver" url="jdbc:mysql://localhost:3306/databaseName" />
```

3. 重启 Tomcat。

下一次 Tomcat 启动时，MySQL JDBC 驱动程序对所有 Web 应用程序可用。你可以通过 JNDI 查找：

```java
Context ctx = (Context) new InitialContext();
DataSource ds = (DataSource) ctx.lookup("java:comp/env/jdbc/DataSource");
```



# 使用 JPA 注解将实体映射到表

## 本章内容

- 理解和操作简单实体
- 设计和利用持久化单元
- 如何映射复杂数据类型

## 本章的 WROX.COM 代码下载

你可以在 http://www.wrox.com/go/javaforewebapps 的“Download Code”（下载代码）选项卡中找到本章的 wrox.com 代码下载。本章的所有代码都声明在以下示例中：

- Entity-Mappings 项目
- Enums-Dates-Lobs 项目

## 本章的新 MAVEN 依赖项

除了之前章节中引入的 Maven 依赖项，你还需要以下 Maven 依赖项。排除了 Hibernate 持久化 API 和 JBoss 事务 API 的瞬态依赖，因为它们与已声明的标准依赖冲突。排除了 XML API 依赖，因为它已经是 Java SE 7 及更高版本的一部分。最后，由于需要排除了 JBoss Logging，但为了清晰起见，在较早的章节中已经声明了对较新版本的依赖。

```xml
<dependency>
  <groupId>org.eclipse.persistence</groupId>
  <artifactId>javax.persistence</artifactId>
  <version>2.1.0</version>
  <scope>compile</scope>
</dependency>

<dependency>
  <groupId>javax.transaction</groupId>
  <artifactId>javax.transaction-api</artifactId>
  <version>1.2</version>
  <scope>compile</scope>
</dependency>

<dependency>
  <groupId>org.hibernate</groupId>
  <artifactId>hibernate-entitymanager</artifactId>
  <version>4.3.Final</version>
  <scope>runtime</scope>
  <exclusions>
    <exclusion>
      <groupId>org.hibernate.javax.persistence</groupId>
      <artifactId>hibernate-jpa-2.1-api</artifactId>
    </exclusion>
    <exclusion>
      <groupId>org.jboss.spec.transaction</groupId>
      <artifactId>jboss-transaction-api_1.2_spec</artifactId>
    </exclusion>
    <exclusion>
      <groupId>xml-apis</groupId>
      <artifactId>xml-apis</artifactId>
    </exclusion>
    <exclusion>
      <groupId>org.jboss.logging</groupId>
      <artifactId>jboss-logging</artifactId>
    </exclusion>
  </exclusions>
</dependency>
```

## 开始使用简单实体

在本章中，你将学习如何使用 JPA 注解将实体映射到关系型数据库表。你有大量的简单和复杂映射选项可供选择，本章尝试涵盖其中的大部分内容。为了让这个过程更简单，你在本章中使用了 Spring Framework。相反，你使用 Servlets 来执行 JPA 代码并列出你创建的实体。所有示例都包含在 Entity-Mappings 项目中，从 wrox.com 下载。

## 基于注解的映射还是基于 XML 的映射？

你不必在应用程序中映射实体。相反，你可以使用 `META-INF/orm.xml` 文件来创建类似于 Hibernate ORM 的 XML 映射。展示如何创建基于注解和基于 XML 的映射将花费双倍的页数，这显然不符合实际。注解是映射 JPA 实体最简单且首选的方法，因此本书只涵盖了这种技术。如果你对学习 XML 映射也感兴趣，XML 映射元素及其属性在本质上与映射注解及其属性是相同的。一个良好的 IDE（如 IntelliJ）可以根据 `orm.xml` 的 XSD 提供代码提示。为了帮助开始，一个空的 `orm.xml` 文件看起来如下：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-mappings xmlns="http://xmlns.jcp.org/xml/ns/persistence/orm"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence/orm
http://xmlns.jcp.org/xml/ns/persistence/orm_2_1.xsd"
version="2.1">
</entity-mappings>
```

### 标记实体并将其映射到表

前两个最基础的 JPA 映射注解是 `@javax.persistence.Entity` 和 `@javax.persistence.Table`。`@Entity` 标记一个类表示它是一个实体。每个实体都必须有此注解。默认情况下，实体名称等于未限定的实体类名，因此以下 `com.wrox.site.entities.Author` 类的实体名称为 `Author`。

```java
@Entity
public class Author implements Serializable
{
...
```

你可以通过在 `@Entity` 注解上指定 `name` 属性来自定义实体名称，例如 `com.wrox.site.entities.Publisher` 类。

```java
@Entity(name = "PublisherEntity")
public class PublisherEntity implements Serializable
{
...
```

实体映射的表默认为实体名称。因此，`Author` 的默认表名是 `Author`，`Publisher` 的默认表名是 `PublisherEntity`。你可以使用 `@Table` 注解的 `name` 属性更改表名。

```java
@Entity
@Table(name = "Authors")
public class Author implements Serializable
{
...
```

```java
@Entity(name = "PublisherEntity")
@Table(name = "Publishers")
public class Publisher implements Serializable
{
...
```

现在，这些类分别映射到 `Authors` 和 `Publishers` 表。你还可以使用此注解做其他几件事情。例如，你可以使用 `schema` 属性来覆盖数据库架构。

### 指示 JPA 如何使用实体

默认情况下，JPA 通过实体的 JavaBean 访问器（getter）和 setter 方法访问实体字段并将其映射到数据库列。因此，实体私有字段的名称和类型对 JPA 并不重要。相反，JPA 查看访问器的名称和类型。你也可以使用 `@Access` 注解来更改此行为，它允许你显式指定 JPA 应该采用的访问方法。

```java
@Entity
@Access(AccessType.FIELD)
public class SomeEntity implements Serializable
{
```



`AccessType` 枚举的选项包括 `PROPERTY`（默认）和 `FIELD`。对于 `PROPERTY`，提供者使用 JavaBean 属性获取和设置值。`FIELD` 让提供者使用实例字段获取和设置值。作为最佳实践，除非有极强的理由，否则你应该保持默认并使用 JavaBean。

其余的 JPA 注解大部分是属性注解。在本章的剩余部分将探索许多此类注解，例如 `@Id`、`@Basic`、`@Temporal` 等。从技术上讲，你可以将这些注解放在字段或公共访问方法上。如果你使用 `AccessType.PROPERTY`（默认）并注解字段而不是 JavaBean，则字段名必须与 JavaBean 属性名匹配。然而，如果你注解 JavaBean 访问器，则不要求匹配。同样，如果你使用 `AccessType.FIELD` 并注解 JavaBean 访问器而不是字段，字段名也必须与 JavaBean 属性名匹配。在这种情况下，如果你注解字段则不需要匹配。最好的做法是保持一致：对于 `AccessType.PROPERTY` 注解 JavaBean 访问器，对于 `AccessType.FIELD` 注解字段。

> **WARNING** 不要在同一个实体中混合使用 JPA 属性注解和 JPA 注解。这样做会导致未定义的行为并极可能导致错误。

## 映射代理键

在映射 JPA 实体时，你要的工作之一就是为实体创建代理键（也称为主键或 ID）。每个实体都应该有一个 ID，该 ID 可以是一个字段（即单列），也可以是多个字段（即多列）。因此，你有许多不同的方法来映射 ID。

## 创建简单 ID

首先，你可以用 `@javax.persistence.Id` 标记任何 JavaBean 属性。该注解表示该属性（在私有字段或公共访问方法、基本类型包装类上）是实体的代理键。该属性可以是任何基本类型、基本类型包装类、`String`、`java.util.Date`、`java.sql.BigInteger` 或 `java.math.BigDecimal`。某些提供商最终可能支持将 Java 8 Date 和其他类型作为字段类型；但目前尚不支持。（即便如此，这样做也不具有移植性。）JPA 2.2 可能会要求对这些类型提供支持。

如果你的类没有 ID，JPA 提供商会查找一个名为 `id` 的属性（带有 `getId` 和 `setId`）并自动使用它。该属性也必须是基本类型、包装类、`String`、`java.util.Date`、`java.sql.BigInteger` 或 `BigDecimal`。

作为最佳实践，实体 ID（主键）通常应该是 `ints`、`longs`、`Integers`、`Longs` 或 `Strings`。通常来说，使用 `int` 或 `Long` 会限制表可以存储的实体数量为 2,147,483,647。`BigInteger` 处理起来很麻烦，且不会像包装类那样自动转换为基本类型，而 `String` 则更难进行索引和数字查找。在少数情况下，`long` 或 `Long` 并不适用于实体 ID，因此本书在未演示其他类型实体 ID 之外排除了 `longs`。但无论你如何操作，如果你启用了架构生成（schema generation），JPA 提供商会自动为 ID 创建主键约束。你不需要在 `@Table` 中指定唯一约束。

然后，你可以创建一个具有手动生成并分配 ID 的实体。然而，这很少被需要，因为需要额外、重复且不必要的工作。通常，你希望实体 ID 以某种方式自动生成。你可以使用 `@javax.persistence.GeneratedValue` 注解来实现这一点。`@GeneratedValue` 允许你指定生成策略，并在必要时指定生成器名称。例如，`Book` 和 `Author` 实体的 ID 使用 `javax.persistence.GenerationType.IDENTITY` 来表示数据库列 ID 能够自动生成自己的值。

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
    public Long getId() {
        return this.id;
    }
}
```

这与 MySQL 的 `AUTO_INCREMENT` 列、Microsoft SQL Server 和 Sybase 的 `IDENTITY` 列、PostgreSQL 的 `DEFAULT NEXTVAL()` 列以及 Oracle 的 `DEFAULT GUID()` 兼容。对于不支持列值自动生成的可以使用 `GenerationType.IDENTITY`，但所有常用的关系型数据库都支持。

至少在任何支持插入前触发器（before-insert triggers）的数据库中，你都可以使用触发器为列生成值（这是 Oracle 数据库使用序列的一种非常常用的技术），该列就可以与 `GenerationType.IDENTITY` 兼容。不过，你可以使用其他生成器，而不必采用触发器和技巧来完成。由于许多数据库（如 Oracle 和 PostgreSQL）支持序列（sequences），你可以结合 `@GeneratedValue` 和 `@javax.persistence.SequenceGenerator`，告诉 JPA 提供商使用序列来生成值。

```java
@Entity
public class SomeEntity implements Serializable {

    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE,
                   generator = "SomeEntityGenerator",
                   sequenceName = "SomeEntitySequence")
    public Long getId() {
        return this.id;
    }
}
```

`@GeneratedValue` 的 `generator` 属性对应 `@SequenceGenerator` 的 `name` 属性，且生成器名称是全局的。这意味着你可以在一个实体上创建一个 `@SequenceGenerator` 并在多个实体中复用它。（不过，你也可以为每个实体使用单独的序列）。

```java
@Entity
public class SomeEntity implements Serializable {

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

或者，你也可以使用 `orm.xml` 中的 `<sequence-generator>` 元素创建多个实体共享的生成器。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-mappings xmlns="http://xmlns.jpa.org/ns/persistence/orm"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:noNamespaceLocation="http://xmlns.jpa.org/ns/persistence/orm_2_1.xsd"
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
    public long getId() {
        return this.id;
    }
}
```

使用 `@SequenceGenerator`（或 `<sequence-generator>`），你可以指定 `schema` 和 `catalog` 属性来指定所属的架构和数据库。如果你启用了 JPA 生成，你还可以使用 `initialValue(initial-value)` 和 `allocationSize(allocation-size)` 来指示序列的初始值以及每次插入操作的增量。`initialValue` 默认值为 0，`allocationSize` 默认值为 50。

你还可以使用 `@TableGenerator`（如 `Publisher` 所示）来使用单独的表。与 `@SequenceGenerator` 一样，`@TableGenerator` 具有相同的 `name`、`schema`、`catalog` 和 `allocationSize` 属性。它的其他属性包括：

- `table`：表名。
- `pkColumnName`：主键列名。
- `pkValue`：生成器表的值。
- `valueColumnName`：值列。

`@TableGenerator` 的常见用例是 JPA 现有的遗留数据库。`table`、`pkColumnName`、`pkValue` 和 `valueColumnName` 的默认值在规范中并未强制规定，不同提供商之间可能会不同。依赖这些默认值是不具有移植性的。如果你关心表、列的以及主键的值，你应该在每个实体上指定不同的 `@TableGenerator`。如果不指定，你只需省略 `@GeneratedValue(strategy = GenerationType.TABLE)`。这将导致为所有实体创建一个表，并为每个实体创建单独的行。

看到这里，你可能会立即好奇 `JoinTableCompositeId` 类的作用是什么。毕竟，JPA 提供者难道不能直接使用两个 `@Id` 列来持久化带有冗余属性的类吗？是的，可以，但之后你如何通过 ID 查找实体呢？
当通过 ID 查找实体时，你使用 `javax.persistence` 中的方法：

```java
JoinTableEntity entity = entityManager.find(JoinTableEntity.class, id);
```

`find` 方法不接受多个参数。它只接受一个 ID 参数，因此你必须创建一个 `JoinTableCompositeId` 实例来定位实体：

```java
JoinTableCompositeId compositeId = new JoinTableCompositeId();
compositeId.setFooTableSk(id1);
compositeId.setBarTableSk(id2);
JoinTableEntity entity = entityManager.find(JoinTableEntity.class, compositeId);
```

由于 `JoinTableCompositeId` 存在重复的属性，`@IdClass` 解决方案可能看起来有些笨拙：

```java
@Embeddable
public class JoinTableCompositeId implements Serializable {

    private long fooTableSk;
    private long barTableSk;

    public long getFooTableSk() { /* ... */ }
    public void setFooTableSk(long fooTableSk) { /* ... */ }
    public long getBarTableSk() { /* ... */ }
    public void setBarTableSk(long barTableSk) { /* ... */ }
}
```

```java
@Entity
@Table(name = "SomeTable")
public class JoinTableEntity implements Serializable {

    private JoinTableCompositeId id;

    @EmbeddedId
    public JoinTableCompositeId getId() { /* ... */ }
    public void setId(JoinTableCompositeId id) { /* ... */ }
}
```



这种解决方案可能对你来说更容易接受，而且它是组合 ID 的一种常用方法。无论你使用哪种技术，都应该使用在本章中学习的映射注解，将 `fooTableSk` 注解和 `barTableSk` 属性映射到相应的数据库列——例如 `@Column`、`@Basic`、`@Enumerated`、`@Temporal` 和 `@Convert`。对于 `@Embeddable` 解决方案，你应该将映射注解放在复合 ID 类上；对于 `@IdClass` 解决方案，则应放在实体类上。你将在第 24 章中学习更多关于 `@Embeddable` 及其其他用途。

## 使用基本数据类型

为了让你的工作更轻松，JPA 在不需要你任何指令的情况下自动映射某些数据类型。如果在实体（或使用 `AccessType.FIELD` 的字段）上发现具有以下类型的属性，它们将自动映射为对应标准 SQL 数据类型的基本属性。某些提供者还会将基本数据类型强制转换为其他 SQL 数据类型。

- 类型为 `short` 和 `Short` 的属性映射到 `SMALLINT`、`INTEGER`、`BIGINT` 或等字段。
- `int` 和 `Integer` 属性映射到 `INTEGER`、`BIGINT` 或等 SQL 数据类型。`long`、`Long` 和 `BigInteger` 属性映射到 `BIGINT` 或等字段。
- 类型为 `float`、`Float`、`double` 和 `BigDecimal` 的属性映射到 `DECIMAL` 或等 SQL 数据类型。
- `byte` 和 `Byte` 属性映射到 `BINARY`、`SMALLINT`、`INTEGER` 或等字段。
- 类型为 `char` 和 `Char` 的属性映射到 `CHAR`、`VARCHAR`、`BINARY`、`SMALLINT`、`INTEGER`、`BIGINT` 或等字段。
- 类型为 `boolean` 和 `Boolean` 的属性映射到 `BOOLEAN`、`BIT`、`SMALLINT`、`INTEGER`、`BIGINT` 或等字段。
- `byte[]` 和 `Byte[]` 属性映射到 `BINARY`、`VARBINARY` 或等 SQL 数据类型。
- `char[]`、`Character[]` 和 `String` 属性映射到 `CHAR`、`VARCHAR`、`BINARY`、`VARBINARY` 或等 SQL 数据类型。
- 类型为 `java.util.Date` 和 `Calendar` 的属性映射到 `DATETIME`、`TIME` 复数据类型，但你必须使用 `@Temporal` 使用额外的指令。在“映射复杂数据类型”章节中，你将学习如何更好地控制这些值的存储。
- 类型为 `java.sql.Timestamp` 的属性始终映射到 `DATETIME` 字段。
- 类型为 `java.sql.Date` 的属性始终映射到 `DATETIME` 字段。
- 类型为 `java.sql.Time` 的属性始终映射到 `TIME` 字段。
- 枚举属性映射到 `SMALLINT`、`INTEGER`、`BIGINT`、`CHAR`、`VARCHAR` 或等字段。默认情况下，枚举以序号（ordinal）形式存储，但你可以使用 `@Enumerated` 更改此行为。你将在“映射复杂数据类型”部分进行更多探索。
- 任何实现 `Serializable` 的其他属性都映射到。

## 指定列名和其他细节

默认情况下，JPA 将实体属性映射到同名的列。参考列表 20-1 中的 `Book` 实体，`id`、`isbn`、`title`、`author`、`price` 和 `publisher` 属性自动映射到 `Id`、`Isbn`、`Title`、`Price` 和 `Publisher`。然而，这并不总是想要的，有时由于许多原因，列名必须不同。通过 `@Column` 注解你可以自定义列名并微调 JPA 提供者的行为。

`name` 属性指示属性映射到哪个数据库列。它与 `table` 属性密切相关，`table` 属性指定实体所在的表，并默认为实体的主表。当实体用于多个表时（你将在第 24 章中探索），你会使用它。布尔值 `insertable` 和 `updatable` 指明值在插入和更新时是否被持久化。两者的默认都是 `true`。`@Column` 的其余属性用于模式生成。`nullable` 指定列是否应该是 `NULL` 或 `NOT NULL`，默认为 `(NULL)`。`unique` 是 `@UniqueConstraint` 注解的快捷方式，当唯一约束包含一列且你不在意约束名称时使用。默认为 `false`（非唯一）。

`length` 属性用于 `VARBINARY` 和 `VARCHAR` 列，指定列的长度，默认值为 255。`scale` 和 `precision` 属性默认为 0，指示小数列的标度（小数点前的数字）和精度（小数点后的数字）。如果你使用模式生成，必须为小数列提供非零的 `precision` 值。最后，`columnDefinition` 提供了一种指定生成列的实际 SQL 的方法。如果你使用它，可能在不同的数据库系统中无法实现。

列表 20-2 中完整的实体 `Author` 演示了使用 `@Column` 更改其属性的默认列名。列表 20-3 中的 `Publisher` 也演示了模式生成属性，在未启用模式生成时该会被忽略。

### 代码清单 20-2: Author.java

```java
@Entity
@Table(name = "Authors", indexes = {
    @Index(name = "Authors_Names", columnList = "AuthorName")
)}
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

### 代码清单 20-3: Publisher.java

```java
@Entity(name = "PublisherEntity")
@Table(name = "Publishers", indexes = {
    @Index(name = "Publishers_Names", columnList = "PublisherName")
})
public class Publisher implements Serializable {
    private long id;
    private String name;
    private String address;

    @Id
    @GeneratedValue(strategy = GenerationType.TABLE,
        generator = "PublisherGenerator")
    @TableGenerator(name = "PublisherGenerator", table = "SurrogateKeys",
        pkColumnName = "TableName", pkColumnValue = "Publishers",
        valueColumnName = "KeyValue", initialValue = 11923,
        allocationSize = 1)
    @Column(name = "PublisherId")
    public long getId() {
        return this.id;
    }

    public void setId(long id) {
        this.id = id;
    }

    @Basic
    @Column(name = "PublisherName", nullable = false)
    public String getName() {
        return this.name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Basic
    @Column(nullable = false)
    public String getAddress() {
        return this.address;
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

## 创建并使用持久化单元

现在你已经创建并映射了一些实体，已经准备好使用这些实体。你仍然需要创建数据库表并配置 JPA 提供者，然后就可以使用持久化 API 的代码来持久化和检索你的实体。

## 设计数据库表

对于这个练习，你需要使用 MySQL Workbench 或你选择的 SQL 数据工具来创建一个数据库和多个表。你可以在从 `wrox.com` 代码下载站点下载 Entity-Mappings 项目的 `create.sql` 文件中找到本节的架构定义语句。打开 Workbench 并使用 root 用户登录你的本地服务器。

在查询编辑器中输入以下 SQL 语句并点击执行图标，创建一个名为 `EntityMappings` 的数据库。

```sql
CREATE DATABASE EntityMappings DEFAULT CHARACTER SET 'utf8'
DEFAULT COLLATE 'utf8_unicode_ci';
```

该数据库使用 `utf8` 字符集和 `utf8_unicode_ci` 排序规则。在几乎所有情况下你都应该使用它们。这些值对于正确存储和检索来自任何语言的字符数据是最优。如果你需要覆盖这些值，可以单独在表和列上设置字符集和排序规则，但你很少需要使用这两种以外的其他设置。创建数据库后，你还需要需要为 Book、Author 和 Publisher 实体创建三个表。记住你使用 `@Table` 注解将表名为了复数形式。

```sql
USE EntityMappings;

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

这些表并没有特别之处。它们包含非常简单的列，清晰地翻译了实体属性名称和数据类型。这里的关键在于先编写代码，然后设计一个支持你代码的数据库。这是设计大多数类型应用程序时的首选方法，因为先创建数据库可能会迫使你的代码去适应数据库。最重要的是应用程序满足了用户的需求，以及代码中发生了什么。JPA 让创建实体变得非常简单，然后创建一个仅仅支持这些实体的数据库。

最后，请记住你告诉过 JPA 使用表生成器来处理 Publisher 的代理键，因此你需要创建适当的生成器表来支持这一需求。

```sql
USE SurrogateKeys;

CREATE TABLE SurrogateKeys (
    TableName VARCHAR(64) NOT NULL PRIMARY KEY,
    KeyValue BIGINT UNSIGNED NOT NULL,
    INDEX SurrogateKeys_Table_Values (TableName, KeyValue)
) ENGINE = InnoDB;
```

## 创建并使用持久化单元

就是这些。数据库已经创建并准备好用于持久化实体。你只需要在 Tomcat 的 `conf/context.xml` 文件中添加一个 `<Resource>`（作为 `<Context>` 元素的子元素），即可创建一个从 Web 应用程序访问数据库的方法。

```xml
<Resource name="jdbc/EntityMappings" type="javax.sql.DataSource"
    maxActive="20" maxIdle="5" maxWait="10000"
    username="tomcat" password="password1234"
    driverClassName="com.mysql.jdbc.Driver"
    uri="jdbc:mysql://localhost/EntityMappings" />
```



## 持久化单元范围

持久化单元是一个配置和一组逻辑分组的实体类。此配置控制附加到持久化单元的 `javax.persistence.EntityManager` 实例，特定持久化单元中的 `EntityManager` 只能管理该单元中定义的实体。例如，假设有两个持久化单元 Foo 和 Bar，为持久化单元 Foo 实例化的 `EntityManager` 只能管理持久化单元 Foo 中定义的实体。它不能管理 Bar 中定义的实体。但是，在多个持久化单元中定义实体是可能的。

你可以在命名的 `persistence.xml` 中定义一个或多个持久化单元。你必须将此文件（如果使用 XML 映射实体则为 `mappings.xml`）放在 `META-INF` 目录中。你应该将其放在哪个 `META-INF` 目录？如你所知，Web 应用程序可以有多个 `META-INF` 目录，例如：

- `mappings.war!/META-INF`
- `mappings.war!/WEB-INF/classes/META-INF`
- `mappings.war!/WEB-INF/lib/something.jar/META-INF`

第一个是 Web 应用程序的 `META-INF` 目录。与其他 `META-INF` 目录不同，该目录不在类路径上。该目录专门用于容器使用。例如，你可以在此目录下放置 `context.xml` 文件并在其中定义 Resource。（但这仅适用于 Tomcat，不适用于其他容器）。然而，你不能在此目录中放置 `orm.xml` 或 `persistence.xml`，因为 JPA 提供者找不到它们。

JPA 提供者可以在 `/WEB-INF/classes/META-INF` 目录以及类路径上任何 JAR 的 `META-INF` 文件中找到持久化文件。关于持久化单元范围的位置，理解持久化单元范围最重要的点是，`persistence.xml` 和 `orm.xml` 共享相同的范围，因此如果你使用 `orm.xml`，应该将它们放在同一个 `META-INF` 目录中。

范围定义了哪些代码可以访问持久化单元。持久化单元对于定义它的组件是可见的并且定义它。通常情况下（尽管有些提供者更宽松），如果你在 `/WEB-INF/classes/META-INF/persistence.xml` 中定义持久化单元，那么它对应用程序类以及 `/WEB-INF/lib` 中的任何组件（JAR 文件）都是可见的。如果你在 `/WEB-INF/lib` 中的某个 JAR 文件的 `META-INF/persistence.xml` 中定义持久化单元，则它只对定义该 JAR 的代码可见。同样，在 EAR 文件顶层定义的持久化单元对所有组件（WAR 文件、应用程序 JAR 文件或 EJB-JAR 文件）可见。

EAR 组件内部定义的持久化单元对组件或 EAR 本身是不可见的。

在 WAR 文件中定义持久化单元时，你通常希望将该持久化单元放置在 `/WEB-INF/classes/META-INF/persistence.xml`。在不提供 JPA 实现的容器中（例如 Tomcat，它只是一个 Servlet 容器，而不是完整的 Java EE 应用程序服务器），这一点尤为重要。在这些情况下，你必须提供自己的 JPA 实现（本书中使用 Hibernate ORM），该嵌入在应用程序 JAR 包中的实现，其工作方式更像是一个独立的应用程序，而不是持久化容器内的 Web 应用程序。

## 创建持久化配置

对于你创建的条目，你必须定义一个持久化单元。操作非常简单。创建一个 `persistence.xml` 文件，它与部署描述符并不相似，但需要考虑的选项更少。持久化配置文件的根元素是 `<persistence>`。该元素可以包含一个或多个 `<persistence-unit>` 元素，`<persistence>` 内部没有其他元素。`<persistence-unit>` 有两个属性：`name` 指定持久化单元的名称，`transaction-type` 指明该持久化单元使用的是 Java Transaction API (JTA) 事务还是本地事务。

你必须指定一个名称，以及你在代码中如何定位该持久化单元。如果没有指定，`transaction-type` 在 Java EE 应用程序服务器中默认为 JTA，在 Java SE 环境或简单的 Servlet 容器中默认为 `RESOURCE_LOCAL`。然而，为了防止出现意外行为，最好始终设置此值，而不是依赖默认值。

> **注意**：Java Transaction API（JTA）与 JPA 一样，是 Java EE 堆栈的一部分。JTA 是一种事务处理监控器，用于协调多个资源之间的事务，例如数据库和应用程序消息系统（JMS、AMQP 等）。JTA 在第 21 节和第 22 节中进一步介绍。

`<persistence-unit>` 包含以下内部元素。它们中的任何一个都不是强制要求的，但是你必须按照以下顺序指定你所使用的任何元素：

- `<description>`：包含对该持久化单元的有用描述。虽然它让阅读持久化单元变得更容易，但它没有语义学价值。
- `<provider>`：指定用于此持久化单元的 `javax.persistence.spi.PersistenceProvider` 实现的完全限定类名。默认情况下，当你查找持久化单元时，API 将使用类路径上的第一个 JPA 提供者。你可以包含此元素来强制使用特定的 JPA 提供者。
- `<jta-data-source>` 或 `<non-jta-data-source>`（但不可兼用）：指向 JNDI DataSource 资源。只有在 `transaction-type` 为 JTA 时，你才能使用 `<jta-data-source>`；同样，只有在 `transaction-type` 为 `RESOURCE_LOCAL` 时，你才能使用 `<non-jta-data-source>`。指定 `DataSource` 会导致持久化单元对所有实体操作使用该 `DataSource`。
- `<mapping-file>`：指定相对于路径的 XML 映射文件的路径。如果没有指定任何 `<mapping-file>`，提供程序将查找 `orm.xml`。你可以指定多个 `<mapping-file>` 元素来使用多个映射文件。
- `<jar-file>`：指定 JPA 提供者应该扫描的用于映射注解类的 JAR 文件或多个 JAR 文件。任何 `@Entity`、`@Embeddable`、`@javax.persistence.MappedSuperclass` 或 `@javax.persistence.Converter` 类都会被找到并添加到持久化单元中。
- `<class>`：指明应该添加到持久化单元的特定 `@Entity`、`@Embeddable`、`@MappedSuperclass` 或 `@Converter` 类。你必须对类进行 JPA 注解并标记。
- `<exclude-unlisted-classes>`：使用 `<exclude-unlisted-classes />` 或 `<exclude-unlisted-classes>true</exclude-unlisted-classes>` 表示提供程序将忽略未用 `<jar-file>` 或 `<class>` 指定的类。省略 `<exclude-unlisted-classes>` 或使用 `<exclude-unlisted-classes>false</exclude-unlisted-classes>` 会导致提供程序扫描持久化文件所在的类路径位置以查找带有 JPA 注解的类。如果 `persistence.xml` 位于 JAR 文件中，则会扫描该文件（且仅扫描该文件）。如果 `persistence.xml` 位于基于目录的类路径位置（例如 `WEB-INF/classes`），则会扫描该目录（且仅扫描该目录）。在 Hibernate 4.3.0 和 Spring Framework 3.2.5 之前，将此元素指定为 false 会被错误地解释为 true。
- `<shared-cache-mode>`：指明实体如何在持久化单元中被缓存（如果 JPA 提供者支持缓存，这是可选的）。`NONE` 禁用缓存，而 `ENABLE_SELECTIVE` 仅对所有被注解了 `@javax.persistence.Cacheable(true)` 或 `@Cacheable(true)`（或在 `orm.xml` 中标记为可缓存）的实体进行缓存。`DISABLE_SELECTIVE` 缓存除标记了 `@Cacheable(false)`（或在 `orm.xml` 中标记为不可缓存）的实体之外的所有实体。默认值 `UNSPECIFIED` 意味着由 JPA 提供者决定效果。Hibernate ORM 默认为 `ENABLE_SELECTIVE`，但依赖此值是不可移植的。
- `<validation-mode>`：指明是否以及如何将 Bean Validation 应用于实体。`NONE` 意味着未启用 Bean Validation，而 `CALLBACK` 在插入、更新和删除时对所有实体进行验证。如果类路径上存在 Bean Validation 提供者，则 `AUTO` 的有效值为 `CALLBACK`；如果不存在 Bean Validation 提供者，则其有效值为 `NONE`。如果你启用了它，JPA 提供者将配置一个新的 Validator 来验证你的实体。如果你配置了带有自定义错误代码的 Spring Framework Validator，JPA 提供者将忽略它。因此，最好在调用你的持久化层之前将验证模式设置为 `NONE` 并进行 Bean Validation。
- `<properties>`：提供了一种指定其他 JPA 属性的方法，包括标准 JDBC 连接字符串、用户名和密码，或架构设置，使用嵌套的 `<property>` 元素，每个元素都有 `name` 和 `value` 属性。

你创建的 `persistence.xml` 文件，在 Tomcat `context.xml` 文件中作为 JPA 提供者，启用 DataSource 资源以扫描 `WEB-INF/classes` 中的所有类，仅对注解的实体启用缓存以及 Bean Validation。它还包含一个属性以确保禁用架构生成（以防万一）。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence xmlns="http://xmlns.jcp.org/xml/ns/persistence"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence/persistence_2_1.xsd"
    version="2.1">
    <persistence-unit name="EntityMappings" transaction-type="RESOURCE_LOCAL">
        <provider>org.hibernate.jpa.HibernatePersistenceProvider</provider>
        <non-jta-data-source>
            java:comp/env/jdbc/EntityMappings
        </non-jta-data-source>
        <exclude-unlisted-classes>false</exclude-unlisted-classes>
        <shared-cache-mode>ENABLE_SELECTIVE</shared-cache-mode>
        <validation-mode>NONE</validation-mode>
        <properties>
            <property name="javax.persistence.schema-generation.database.action"
                  value="none"/>
        </properties>
    </persistence-unit>
</persistence>
```

## 使用持久化 API

使用持久化 API 非常简单。大部分代码用于处理事务和资源。保存和检索实体非常简单。`EntityManager` 添加并显示实体查看的是 `init` 和 `destroy` 方法，它们分别在启动时创建一个 `javax.persistence.EntityManagerFactory` 并在关闭时关闭它。

```java
@WebServlet(
    name = "entityServlet",
    urlPatterns = "/entities",
    loadOnStartup = 1)
public class EntityServlet extends HttpServlet {

    private final Random random;
    private EntityManagerFactory factory;

    public EntityServlet() {
        try {
            this.random = SecureRandom.getInstanceStrong();
        } catch (NoSuchAlgorithmException e) {
            throw new IllegalStateException(e);
        }
    }

    @Override
    public void init() throws ServletException {
        super.init();
        this.factory = Persistence.createEntityManagerFactory("EntityMappings");
    }

    @Override
    public void destroy() {
        super.destroy();
        this.factory.close();
    }
}
```

`entityManager` 方法从 `persistence.xml` 配置中获取名为 `EntityMappings` 的持久单元，并为该持久单元创建一个新的 `EntityManager`。在完整的 Java EE 应用服务器中，你不需要执行这些额外的步骤。相反，你可以这样做：

```java
public class EntityServlet extends HttpServlet {
    private final Random random;
    @PersistenceContext("EntityMappings")
    EntityManagerFactory factory;
}
```

这告诉容器创建并注入 `EntityManagerFactory`。然而，除非容器提供 JPA 和依赖注入（Tomcat 并不提供），否则它无法工作。下一章将学习如何使用 Spring Framework 工具来简化这一过程。

`EntityServlet` 响应 GET 和 POST 请求。对于 GET 请求，它查询实体并使用 `/WEB-INF/jsp/view/entities.jsp` 显示它们。首先，它创建了一个 `EntityManager` 并通过该管理器启动了一个事务。它使用 `javax.persistence.criteria.CriteriaBuilder`、`javax.persistence.criteria.CriteriaQuery` 和 `javax.persistence.TypedQuery` 来列出所有的出版社（Publishers）、作者（Authors）和书籍（Books），并在完成后提交事务并关闭管理器，或者在发生错误时回滚事务。

```java
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
            q1.select(builder.from(Publisher.class))
        ).getResultList());
        CriteriaQuery<Author> q2 = builder.createQuery(Author.class);
        request.setAttribute("authors", manager.createQuery(
            q2.select(builder.from(Author.class))
        ).getResultList());
        CriteriaQuery<Book> q3 = builder.createQuery(Book.class);
        request.setAttribute("books", manager.createQuery(
            q3.select(builder.from(Book.class))
        ).getResultList());
        transaction.commit();
        request.getRequestDispatcher("/WEB-INF/jsp/view/entities.jsp")
    }
}
```



```java
.forward(request, response);

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
```

对于 POST 请求，`EntityServlet` 持久化了一个新的出版社、新作者和新书籍。当然，这些值都是平庸且重复的，因为它们不是基于用户输入的，但演示很明确：使用 JPA 是很容易的。与 `doGet` 一样，`doPost` 也会根据需要启动、提交并回滚事务。

```java
@Override
public void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {

    EntityManager manager = null;
    EntityTransaction transaction = null;

    try {
        manager = this.factory.createEntityManager();
        transaction = manager.getTransaction();
        transaction.begin();

        Publisher publisher = new Publisher();
        publisher.setName("John Wiley & Sons");
        publisher.setAddress("*1234 Baker Street");
        manager.persist(publisher);

        Author author = new Author();
        author.setName("Nicholas S. Williams");
        author.setEmail("nick@example.com");
        manager.persist(author);

        Book book = new Book();
        book.setIsbn("" + random.nextInt(Integer.MAX_VALUE));
        book.setTitle("Professional Java for Web Applications");
        book.setAuthor("Nicholas S. Williams");
        book.setPublisher("John Wiley & Sons");
        book.setPrice(59.99);

        transaction.commit();
        response.sendRedirect(request.getContextPath() + "/entities");

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
```

# 创建和使用持久单元

要测试项目，请按照以下步骤操作：

1. 从你的 IDE 编译并启动 Tomcat。在任选的浏览器中访问 `http://localhost:8080/mappings/entities`，点击几次“Add More Entities”。
2. 关闭 Tomcat 并重新启动。
3. 回到 `http://localhost:8080/mappings/entities`，实体应该仍然在那里，它们是虚拟机的持久化实例。
4. 现在打开 MySQL Workbench 并执行以下语句，如图 20-1 所示。查看每个结果表，你可以看到 Hibernate ORM 已将数据插入到你的数据库表中。

```sql
USE EntityMappings;
SELECT * FROM Publishers;
SELECT * FROM Authors;
SELECT * FROM Books;
SELECT * FROM SurrogateKeys;
```

## 使用 JPA 注解将实体映射到表

![图 20-1](https://example.com/figure/20-1.png)

## 映射数据类型

到目前，你应该对实体映射的基础知识有了合理的掌握，在本节中，你将学习如何正确映射复杂类型，例如日期、时间和大对象。

## 使用枚举作为实体属性

如之前所述，JPA 可以在不需要任何特殊配置的情况下自动持久化枚举。考虑以下枚举：

```java
public enum Gender {
    MALE,
    FEMALE,
    UNSPECIFIED
}
```

```java
public class Author implements Serializable {
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

与此不同，JPA 提供者使用序号值（ordinal value）持久化枚举。因此，性别为男性的作者在 `gender` 列中的值为 0。同样，`FEMALE` 和 `UNSPECIFIED` 的持久化值分别为 1 和 2。这带来了几个挑战：

- 你无法直接查看数据库表（例如通过 MySQL Workbench）并自动识别数据。你只会看到 `gender` 列中的 0、1 和 2，而不是有用的描述。
- 如果有人更改了枚举并重新排列了常量（例如，为了按字母顺序排序），所有数据现在都损坏了——这显然是一个大问题。

当数据库列为数值列（如 `INT`）或字符串列时，这种默认行为保持不变。幸运的是，JPA 提供的 `@java.persistence.Enumerated` 属性允许你更改此值的持久化方式。`@Enumerated` 的默认值（带有讽刺的是）是 `EnumType.ORDINAL`。你的设置告诉 JPA 提供者以字符串格式（常量的名称）持久化枚举。这既是重构安全的（除非某人更改了常量名称，但那是更大的问题），又便于在数据库中直接查看。

```java
@Enumerated(EnumType.STRING)
public Gender getGender() {
  return this.gender;
}
```

使用 `EnumType.STRING` 时，不仅你的列必须是字符串类型列（这可能是显而易见的），它还必须是 Unicode（例如 `VARCHAR`，或带有 UTF-8 或 UTF-16 字符集的 `VARCHAR`）。该规则的例外是数据库厂商支持原生枚举类型时。原因是 Java 枚举常量可能包含无法正确存储在非 Unicode 列中的字符。当然，你只需简单地避免使用此类字符；由于 Java 中的 `String` 始终是 Unicode，最好是让你所有的文本列都是 Unicode，这样就不需要进行字符转换。

`Authors` 表的新定义如下，它使用了 MySQL 的 `ENUM` 数据类型以在数据库中提供额外的元数据层和验证，并在存储数据时更节省空间。

```sql
CREATE TABLE Authors (
  AuthorId BIGINT UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
  AuthorName VARCHAR(100) NOT NULL,
  EmailAddress VARCHAR(255) NOT NULL,
  Gender ENUM('MALE','FEMALE', 'UNSPECIFIED') NULL,
  INDEX Publishers_Names (AuthorName)
) ENGINE = InnoDB;
```

## JPA 如何处理日期和时间

在之前的 JDBC 版本中，你只能通过 `PreparedStatement` 的 `setDate`、`setTime` 和 `setTimestamp` 方法来插入日期、时间或日期时间。这些方法分别需要 `java.sql.Date`、`java.sql.Timestamp` 和 `java.sql.Time`。`ResultSet` 的 `getDate`、`getTime` 和 `getTimestamp` 方法返回 `Date`、`Time` 和 `Timestamp`，其 `updateDate`、`updateTime` 和 `updateTimestamp` 方法的功能与上述三个 `PreparedStatement` 方法相同，如下：

- `Date` 仅存储日期（年、月和日）。
- `Time` 仅存储时间（时、分和秒）。
- `Timestamp` 是两者的结合，始终存储为年、月、日、时、分和秒。

JDBC 4.2 增加了通过 `PreparedStatement` 的 `setObject(int, Object, java.sql.Type)` 方法以及 `ResultSet` 的 `getObject(int, Class, Class)`、`getObject(String, Class)` 方法将任何对象作为日期、时间、带时区的区、日期时间或带时区的日期时间的能力。当然，只有在驱动厂商支持的情况下才能使用这些方法，但预计所有 JDBC 4.2 驱动程序除了 `java.util.Date`、`Calendar`、`java.sql.Date` 和 `Timestamp` 之外都支持相应的 Java 8 日期时间类型。与日期时间类型对应的 SQL 类型为：

- `java.sql.DATE`（仅存储日期）
- `JDBCType.TIME`（仅存储时间）
- `JDBCType.TIME_WITH_ZONE`（仅存储时间和时区）
- `JDBCType.TIMESTAMP_WITH_ZONE`（存储日期、时间以及时区）

某些数据库系统（如 Microsoft SQL Server）除了始终匹配服务器时区的标准时间和日期时间列外，还支持良好存储时区的时间和日期时间列。其他数据库（如 MySQL）仅支持服务器时区的时间和日期时间列。`TIME_WITH_TIMEZONE` 和 `TIMESTAMP_WITH_TIMEZONE` 常量仅对支持组合时区列的厂商有效。你应该节制地使用它们，并且仅在必要时使用。对于大多数情况，你应该在服务器时区存储时间和日期，并仅在必要时才将其转换为其他时区。

> **警告** 在使用最新的 JDBC 4.1 和 JDBC 4.2 特性时，你应该保持谨慎。许多驱动程序（如 MySQL 和 Microsoft Server 的驱动）尚未跟上 2011 年 7 月为 Java 7 添加的 JDBC 4.1 特性。事实上，截至本文写作，PostgreSQL 的 JDBC 驱动程序仅支持 2002 年 2 月 Java 4 引入的 JDBC 3.0 特性。PostgreSQL 声称拥有符合标准的 JDBC 4.0 驱动，包含了 2006 年 12 月发布的 Java 6 特性，但该驱动远未完成且会抛出 `AbstractMethodError`。Oracle 是目前支持 JDBC 4.1 的唯一主要厂商。你可以预计这一趋势将持续，因此可能多年后你才能在 MySQL、Microsoft SQL Server 和 PostgreSQL 中使用新的 JDBC 4.2 特性。

使用 JPA 时，`java.sql.Date` 作为日期存储（使用 `PreparedStatement.setDate`）。即使数据库列是 `DATETIME`，该列的时间部分全为零。同样，时间属性存储为时间（使用 `PreparedStatement.setTime`），数据库列必须是 `TIME`（或等效）列。`Timestamp` 属性会自动与日期时间部分一起存储，相应的数据库列必须是 `DATETIME`（或等效）。棘手之处在于如果你的实体包含 `util.Date` 或 `Calendar` 属性。对于这些属性，请使用 `@javax.persistence.Temporal` 注解告诉提供程序持久化该类型。`value` 属性期望一个 `java.persistence.TemporalType`，其选项如下：

- `TemporalType.DATE`（将 `Calendar` 或 `Date` 属性转换为 `java.sql.Date`）
- `TemporalType.TIME`（在属性与 `Time` 之间转换）
- `TemporalType.TIMESTAMP`（在属性与 `Timestamp` 之间转换）

你不能在已经是 `java.sql.Date`、`Time` 或 `Timestamp` 类型的属性上使用 `@Temporal`。`Publisher` 实体的 `dateFounded` 使用 `Calendar` 来存储出版社成立的日期，并将值存储在 `DATE` 列中。

```java
public class Publisher implements Serializable {
    private Calendar dateFounded;
    ...
    @Temporal(TemporalType.DATE)
    public Calendar getDateFounded() {
        return dateFounded;
    }
    public void setDateFounded(Calendar dateFounded) {
        this.dateFounded = dateFounded;
    }
}
```

```sql
CREATE TABLE Publishers (
PublisherId BIGINT UNSIGNED NOT NULL PRIMARY KEY,
PublisherName VARCHAR(100) NOT NULL,
Address VARCHAR(1024) NOT NULL,
DateFounded DATE NOT NULL,
INDEX Publishers_Names (PublisherName)
) ENGINE = InnoDB;
```

当然，`java.sql.Date` 并不理想。你想使用 `java.time.LocalDate`。在第 24 章中你将学习如何使用 Java 8 的日期时间类型。与日期时间类型对应的 SQL 类型为：

- `java.sql.DATE`（仅存储日期）
- `JDBCType.TIME`（仅存储时间）
- `JDBCType.TIME_WITH_ZONE`（仅存储时间和时区）
- `JDBCType.TIMESTAMP_WITH_ZONE`（存储日期、时间以及时区）

## 将大对象映射到 CLOB 和 BLOB

有时你需要存储大量数据，例如长文本或二进制文件。对于这些情况，JPA 提供了 CLOB（字符大对象）和 BLOB（二进制大对象）。你可以使用 `@Lob` 注解将属性标记为大对象。

```java
public class Book implements Serializable {
    ...
    @Lob
    private String description;
    public String getDescriptionDescription() {
        return description;
    }
    public void setDescription(String description) {
        this.description = description;
    }
}
```

```sql
CREATE TABLE Books (
    Id UNSIGNED NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Isbn VARCHAR(13) NOT NULL,
    Title VARCHAR(255) NOT NULL,
    Author VARCHAR(100) NOT NULL,
    Price DECIMAL(6,2) NOT NULL,
    Publisher VARCHAR(100) NOT NULL,
    Description LONGTEXT NULL,
    UNIQUE KEY Books (Isbn),
    INDEX Titles (Title)
) ENGINE = InnoDB;
```

对于二进制数据，使用字节数组和 `Lob` 注解：



public class Book implements Serializable {

    @Lob
    private byte[] coverImage;

    public byte[] getCoverImage() {
        return coverImage;
    }

    public void setCoverImage(byte[] coverImage) {
        this.coverImage = coverImage;
    }
}

```sql
ALTER TABLE Books ADD coverImage MEDIUMOB;
```

## 映射复杂类型

Java 8 引入了新的日期时间 API，比旧的 `java.util.Date` 和 `java.sql.Date` 好得多。JPA 2.2 直接支持这些新类型。

```java
public class Book implements Serializable {
    ...
    private LocalDate publishedDate;

    public LocalDate getPublishedDate() {
        return publishedDate;
    }

    public void setPublishedDate(LocalDate publishedDate) {
        this.publishedDate = publishedDate;
    }
}
```

```sql
ALTER TABLE Books ADD publishedDate DATE;
```

同样，你可以使用 `LocalTime` 和 `LocalDateTime`：

```java
public class Book implements Serializable {
    ...
    private LocalTime lastUpdated;
    private LocalDateTime lastModifiedDate;

    public LocalTime getLastUpdated() {
        return lastUpdated;
    }

    public void setLastUpdated(LocalTime lastUpdated) {
        this.lastUpdated = lastUpdated;
    }

    public LocalDateTime getLastModifiedDate() {
        return lastModifiedDate;
    }

    public void setLastModifiedDate(LocalDateTime lastModifiedDate) {
        this.lastModifiedDate = lastModifiedDate;
    }
}
```

## 测试枚举和日期

测试 Enums-Lets-Dates 项目基本上与 Entity-Mappings 项目相同：

1. 在 MySQL Workbench 中运行 `create.sql` 以创建 `EnumsLetsDates` 数据库及其表。
2. 更新 Tomcat 的 JNDI 资源以指向新数据库。
   ```xml
   <Resource name="jdbc/EnumsLetsDates" type="java.sql.DataSource" maxActive="20" maxIdle="5" maxWait="10000" username="tomcatcatUser" password="password1234" driverClassName="com.mysql.jdbc.Driver" url="jdbc:mysql://localhost/EnumsLetsDates" />
   ```
3. 在你选择浏览器中访问 `http://localhost:8080/mappings/entities`，并几次“Add More Entities”。它的行为与之前完全一样，但增加了作者性别和出版社的成立日期（示例中为今天的日期）。
4. 你可以使用 MySQL Workbench 查询表以查看插入的数据。你需要将 `PreviewPdf` 列转换为十六进制字符串以便显示，使用 MySQL 的 `hex` 函数：
   ```sql
   USE EnumsLetsDates;
   SELECT * FROM Publishers;
   SELECT * FROM Authors;
   SELECT Id, Isbn, Title, Author, Price, Publisher, hex(PreviewPdf) FROM Books;
   SELECT * FROM SurrogateKeys;
   ```

### 总结

在本章中，你探索了使用 JPA 注解映射实体的基础，并看到了使用 `orm.xml` 进行 XML 映射的简要示例。你学习了 `persistence.xml`、它的作用、什么是持久化单元（persistence unit）以及持久化单元范围如何工作。你在 MySQL 中创建了几个表，并尝试使用持久化 API 在这些表中存储数据和检索数据。你还学习了在处理枚举（enums）、日期、时间、日期时间以及 LOB（大对象）时，涉及的一些重要步骤和注意事项。

你还没有充分利用持久化 API，关于查找、插入、更新和删除实体的许多部分你仍然需要学习。在下一章中，你将更彻底地探索持久化 API，使用 Spring Framework 来处理注入持久化单元和管理事务的琐碎工作。

# 21

# 在 Spring Framework 仓库中使用 JPA

本章内容

- 理解 Spring 仓库并利用事务
- 在 Spring Framework 中设置持久化
- 实现并使用 JPA 仓库
- 使用 DTO 和实体转换数据

本章的 WROX.COM 代码下载

你可以通过 http://www.wrox.com/go/projavaforwebapps 的“Download Code”选项卡找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Spring-JPA 项目
- Customer-Support-v15 项目

本章的新 Maven 依赖

除了之前章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-orm</artifactId>
  <version>4.0.0</version>
  <scope>compile</scope>
</dependency>
```

```xml
<dependency>
  <groupId>org.javassist</groupId>
  <artifactId>javassist</artifactId>
  <version>3.18.1-GA</version>
  <scope>runtime</scope>
</dependency>
```

# 使用 Spring 仓库和事务

在对象关系映射器（ORM）变得如此常见以及 JPA 持久 API 发布之前，Spring Framework 的 `org.springframework.jdbc.core.JdbcTemplate` 在 Spring 应用中提供了一种使用 JDBC 持久和检索条目的标准、简化方法。除了进行表到实体的转换外，`JdbcTemplate` 还能识别 JDBC 驱动抛出的各种特定厂商的 `SQLEceptions` 和错误代码，并将它们翻译为 `org.springframework.dao.AccessException` 层次结构中的成员。例如，由于 Oracle、SQL Server、MySQL 或任何其他支持数据库中的唯一键导致记录插入失败，会导致明确的 `org.springframework.DuplicateException`。`JdbcTemplate` 仍然存在，但与 JPA 或独立的 O/M 工具相比，它的强大之处是无法比拟的。

尽管如此，某些任务使用 JPA 执行时仍然很困难或繁琐。例如，在每个方法中创建 `EntityManager` 并进行手动管理，这消耗了你在上一章中编写的大部分持久化代码。重要的事务通常包括选择和操作多种类型的实体。你需要一种方法来创建 `EntityManager`、启动事务，并在单个工作单元的范围内跨多个仓库共享它。

幸运的是，Spring Framework 提供了恰恰好满足这种需求及更多需求的工具。在 Spring 版本中，`org.springframework.orm.jpa.JpaTemplate` 提供了一种类似于 `JdbcTemplate` 的机制，用于在 Spring Framework 应用中使用持久化 API。然而，`JpaTemplate` 在 Spring 3.1 中被弃用并在 Spring 4.0 中移除，以支持使用持久化实体 `EntityManager` 的新方式。在本章中，你将探索如何配置和使用 Spring Framework、共享的 `EntityManager` 以及 JPA 翻译。

# 理解事务范围

在 Spring Framework 中，你使用 `org.springframework.transaction.PlatformTransactionManager` 控制事务。你定义一个适用于你的环境的 `PlatformTransactionManager`，并在应用中选择持久化技术。该接口中的方法并不重要——你永远不会直接使用它，你只需要配置一个实现。Spring 会代表你自动管理启动、提交和回滚事务。这是通过 `@org.springframework.transaction.annotation.Transactional` 或 `@javax.transaction.Transactional` 注解实现的。你可以用这些注解标记接口、类、接口方法和类方法。对接口或类进行注解的效果等于对接口或类中的所有方法进行注解。对已标记注解的接口或类再次注解，其效果是覆盖接口类上的注解。

当 Spring 遇到带有注解的方法时，会开始一个事务。事务范围涵盖了该方法的执行、它所调用的任何方法的执行等，直到方法返回。在事务范围内使用的、且被配置的 `PlatformTransactionManager` 涵盖的任何托管资源都会参与事务。例如，如果你使用 `org.springframework.jdbc.datasource.DataSourceManager`，从关联的 `DataSource` 获取的 `Connection` 将参与事务。同样，在由 `org.springframework.jms.connection.JmsTransactionManager` 管理的事务期间执行的 Java Message Service 操作将参与该事务。

事务有两种终止方式：要么方法直接完成执行且事务管理器提交事务，要么方法抛出异常且事务管理器回滚。默认情况下，任何 `java.lang.RuntimeException` 都会导致事务回滚。使用任何 `@Transactional` 注解都可以扩展或限制此过滤器，以决定什么会触发事务回滚。

当然，这一切其中涉及一些魔术，你必须以特定的方式使用这些资源，事务范围才能生效。这在不同的 `PlatformTransactionManager` 实现之间以及不同的资源类型之间有所不同。

# 使用线程处理事务和 EntityManager

之前讨论的事务范围限制在事务开始的线程。事务管理器随后在事务生存期间将同一线程中使用的托管资源连接起来。当使用 Java Persistence API 时，你处理的资源是 `EntityManager`。如果它是功能性的，你会在启动事务并执行 JPA 操作之前，从 Hibernate 的 `Session` 和 JDBC 的 `Connection` 获取 `EntityManager`。然而，这在代表你管理事务的 Spring 框架中并不适用。

问题的解决方案是使用 `org.springframework.orm.jpa.support.SharedEntityManagerBean`。当你在 Spring Framework 中配置 JPA 时，它创建一个代理 `EntityManager` 接口的 `SharedEntityManagerBean`。然后当在该代理上调用 `EntityManager` 方法时，后台会发生以下情况：

- 如果当前线程已具有活动事务的 `EntityManager`，它将调用委托给该实体。
- 否则，Spring 从 `EntityManagerFactory` 获取一个新的 `EntityManager`，启动事务并将其绑定到当前线程。然后它将调用委托给该实体。

当事务提交或回滚时，Spring 会从线程中解绑 `EntityManager` 并关闭它。后续的线程 操作（即使在同一个请求内）将重新开始过程，从工厂获取新的 `EntityManager` 并开启新事务。这意味着给定线程在任何时候只有一个事务和一个 `EntityManager`。

不要在仓库中通过 `@Inject` 或 `@Autowired` 创建 `EntityManager` 字段，而是使用 `@javax.persistence.PersistenceContext` 注解指示 Spring 应该注入 `EntityManager` 的代理。

```java
@PersistenceContext
EntityManager entityManager;
```

普通的 `EntityManager` 不是线程安全的，并且始终要求在使用之前启动事务。从 Spring 获取 `PersistenceContext` EntityManager 意味着你的仓库可以在多个线程中使用此实例，且每个线程都有由 Spring 管理的事务。

使用 `@PersistenceContext` 的另一个优势是可以为 `EntityManager` 实例指定持久化单元名称。这样，你可以在 Spring 应用中定义多个持久上下文配置，并通过指定名称来区分你打算在仓库中使用哪个 `EntityManager` 实例。

```java
public class FooRepository {
    @PersistenceContext(unitName="fooUnit")
    EntityManager entityManager;
    ...
}

public class BarRepository {
    @PersistenceContext(unitName="barUnit")
    EntityManager entityManager;
}
```



# 在 Spring Framework 中使用 JPA

在 Spring Framework 中使用 JPA，可以使用两种 `PlatformTransactionManager` 实现：

- 最标准且常用的是 `org.springframework.orm.jpa.JpaTransactionManager`，这也是你在本书中使用的。该实现只能管理 `EntityManager` 操作的事务，且仅针对单个持久化单元，但在很多情况下这已经足够了。
- 如果你想在应用程序中使用多个持久化单元（如之前的示例所示），或者跨多个类型的资源（例如 `EntityManager` 和消息服务资源）管理事务，你需要 `org.springframework.transaction.jta.JtaTransactionManager` 或其子类（WebLogic 服务器上的 `WebLogicJtaTransactionManager`；WebSphere 服务器上的 `WebSphereUowTransactionManager`）。该实现需要 JTA API 提供程序，因此你需要完整的 Java EE 服务器或复杂的独立 JTA 配置（如 Tomcat 情况）。

JTA 是一个广泛的主题，在完整的 Java EE 服务器之外配置非常困难，因此本书未涵盖这一内容。网上有很多 JTA 教程，你的应用程序服务器文档应该是一个非常有用的资源。

# 利用异常翻译的优势

在 JDBC 使用时代，处理异常可能是一场噩梦。每个 JDBC 供应商都有自己的一套扩展 `java.sql.SQLException` 的异常，而且与这些异常相关的错误代码也随供应商而异。如果你想知道错误发生的原因，要么将代码限制在单个供应商上并弄清楚该供应商的异常模式，要么在 `catch` 块中对每种异常进行测试。这个过程非常乏味，通常导致编写的代码比你实际执行工作花费的时间多得多。

随着 O/RM（对象关系映射）变得越来越流行，有些定义了实用的异常层次结构，而有些则没有。Java Persistence API（JPA）定义了一个从 `javax.persistence.PersistenceException` 开始的简单异常层次结构，但它仍然缺少一些功能（例如指示发生唯一键冲突的异常）。在 NoSQL 工具领域，每个客户端库都有自己的一套检查异常或未检查异常，且没有一个继承自持久化异常，这使得问题变得更加棘手。

Spring 及其相关数据工具（如 Spring Data NoSQL）提供了 `org.springframework.dao.DataAccessException`。该组包含了大量异常，本书并未涵盖所有异常。可以说，无论你直接使用 JDBC、Hibernate 或其他 O/M、JPA、Java Data Objects (JDO) 还是 NoSQL，都可以在这些特定技术的异常层次结构中查找异常。

在应用程序中实现这种异常翻译有两个关键。
首先，你必须在根应用上下文中配置一个或多个 `org.springframework.dao.support.PersistenceExceptionTranslator` 实现。针对不同的技术有不同的 `PersistenceExceptionTranslator` 实现。如果你在应用程序中使用了多种持久化技术——例如 JPA 和 NoSQL——你需要配置一个能够处理所有实现的实现（Spring 会自动使用 `org.springframework.dao.support.ChainedPersistenceExceptionTranslator` 将它们链联起来）。

Spring Framework 拥有多种 `PersistenceExceptionTranslator` 来处理不同的技术。你在下一节中配置的 `org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean` 自身也是一个 `PersistenceExceptionTranslator`，能够将 JPA 异常和底层 JDBC 错误代码翻译为 `DataAccessException`。只需定义这个 bean，你就配置了 JPA 的异常翻译。如果你使用多种持久化技术，可以为每种技术配置一个。

配置异常翻译后，你必须在你的仓库（repositories）上加上 `@Repository` 注解。这告诉带有注解的 bean 能够使用配置的 `PersistenceExceptionTranslator` 进行异常翻译。如果仓库方法抛出任何持久化异常，`PersistenceExceptionTranslator` 将适当翻译这些异常。
注意，这意味着你不能从仓库本身捕获翻译后的 `DataAccessException`，因为此时翻译尚未发生。你只能在调用仓库方法的代码中捕获 `DataAccessException`。

# 在 Spring Framework 中配置持久化

> **注意**：如果你查看 Spring Framework 及其工具提供的所有 `PersistenceExceptionTranslator` 实现，你会发现没有纯粹的 JDBC 异常翻译器。当你在 Spring 仓库中使用 JDBC 时，预期的做法是使用 `JdbcTemplate`。因为 `JdbcTemplate` 是 Spring 工具而非第三方类，它内置了持久化翻译功能。

在 Spring 中配置 JPA 实际上非常简单，但你需要理解几个选项，这些节将解释它们。通常情况下，Spring JPA 的配置过程包含三个部分：

- 创建或查找 `DataSource`
- 创建或查找持久化单元（persistence unit）并配置 Spring 将其注入到你的仓库中。
- 设置事务管理，以便 `@Transactional` 方法能被正确处理。

你可以参考从 wrox.com 下载站提供的 Spring-JPA 项目。该项目从你在第二部分末尾使用的 Spring 引导和配置开始。

## 查找数据源 (Data Source)

你需要做的第一件事是让你的应用程序可以使用 `DataSource`。你有几种不同的方法来实现。如果你只是需要快速测试某些内容，可以使用 Spring 的 `org.springframework.jdbc.datasource.DriverManagerDataSource` 按需创建 `DataSource`：

```java
@Bean
public DataSource springDataSource() {
    DriverManagerDataSource dataSource = new DriverManagerDataSource();
    dataSource.setUrl("jdbc:mysql://localhost/SpringJpa");
    dataSource.setUsername("tomcatUser");
    dataSource.setPassword("password1234");
    return dataSource;
}
```

然而，这创建了一个返回单个 `Connection` 的简单 `DataSource`。因为它不提供连接池，所以它永远不应该在任何类型的生产环境中使用。在独立应用程序中，可以使用 Apache Commons DBCP 和 Apache Commons Pool 来创建并返回连接池化的 `DataSource`。通常，你需要读取一个包含 URL、用户名和密码信息的属性文件，这样更改连接详情无需重新编译。在应用服务器或 Servlet 容器上，最简单的方法是在服务器上定义一个 `DataSource`（如你在上一章中所做），并在你的 `RootApplicationContext` 中查找该 `DataSource`。这就是 Spring-JPA 项目所做的。

```java
@Bean
public DataSource springJpaDataSource() {
    JndiDataSourceLookup lookup = new JndiDataSourceLookup();
    return lookup.getDataSource("jdbc/SpringJpa");
}
```

> 连接池是你在第二部分学习的线程池概念。连接池包含多个供使用的空闲连接。这些连接从池中借用，不再需要时归还并重置。这样就避免了频繁打开和关闭连接的开销。在应用服务器或 Servlet 容器中配置的 `DataSource` 使用连接池。

在你进行此工作时，不要忘记在 Tomcat 的 `context.xml` 文件中定义 `DataSource` 资源（你将在下一节学习 `defaultTransactionIsolation` 属性）。

```xml
<Resource name="jdbc/SpringJpa" type="javax.sql.DataSource"
    maxActive="20" maxIdle="5" maxWait="10000"
    username="tomcatUser" password="password1234"
    driverClassName="com.mysql.jdbc.Driver"
    defaultTransactionIsolation="READ_COMMITTED"
    url="jdbc:mysql://localhost/spring_jpa" />
```

在此示例中，你使用的是无法参与 JTA 事务的标准 `DataSource`。这对于书中的示例足够，但如果你希望事务跨越多个 `DataSource` 或多种技术（如 JMS），你必须定义并查找支持 JTA 的 `DataSource`。这在 Tomcat 中可行但非常困难。最好的做法是使用全功能 Java EE 应用服务器。

## 在代码中创建持久化单元

配置 Spring Framework 的 JPA 支持时，最重要的任务之一就是设置持久化单元。你已经在第 20 章中探索了在 `/WEB-INF/classes/META-INF/persistence.xml` 文件中创建持久化单元，但使用 Spring Framework 时并不限于这种技术。

为了正确使用 JPA，你需要配置一个实现 `org.springframework.orm.jpa.AbstractEntityManagerFactoryBean` 的 bean。这种类型的 bean 可以创建管理仓库中线程绑定、事务关联的 `EntityManager`。最简单的方法是配置一个 `LocalEntityManagerFactoryBean`。该 bean 要求 `/META-INF/persistence.xml` 存在，并从文件中读取持久化单元配置。当你配置 `LocalEntityManagerFactoryBean` 时，要指定它应该使用的持久化单元名称。

![](img/4677f981a0e1067137bb55a122f8498d_638_0.png)

```java
@Bean
public LocalEntityManagerFactoryBean entityManagerFactoryBean() {
    LocalEntityManagerFactoryBean factory = new LocalEntityManagerFactoryBean();
    factory.setPersistenceUnitName("SpringJpa");
    factory.setJpaVendorAdapter(new HibernateJpaVendorAdapter());
    factory.setDataSource(this.springJpaDataSource());
    return factory;
}
```

这非常完美，但这已经是我们能做到的极限了。更有用的实现是 `org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean`，它不需要 `META-INF/persistence.xml` 存在。例如，将你的持久化文件放在名为 `META-INF` 的包中，然后在持久化文件所在使用 `LocalContainerEntityManagerFactoryBean`。

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactoryBean() {
    LocalContainerEntityManagerFactoryBean factory = new LocalContainerEntityManagerFactoryBean();
    factory.setPersistenceUnitLocation("classpath:wrox/config/persistence.xml");
    factory.setPersistenceUnitName("SpringJpa");
    factory.setJpaVendorAdapter(new HibernateJpaVendorAdapter());
    factory.setDataSource(this.springJpaDataSource());
    return factory;
}
```

最重要的是，使用 `LocalContainerEntityManagerFactoryBean` 甚至不需要持久化文件。你可以完全省略持久化 XML 位置和持久化单元名称，并使用纯 Java 代码来配置持久化单元。这就是 Spring-JPA 配置中的 `RootContextConfiguration` 配置持久化单元的方式。

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactoryBean() {
    Map<String, Object> properties = new Hashtable<>();
    properties.put("javax.persistence.schema-generation.database.action", "none");
    HibernateJpaVendorAdapter adapter = new HibernateJpaVendorAdapter();
    adapter.setDatabasePlatform("org.hibernate.dialect.MySQL8Dialect");
    LocalContainerEntityManagerFactoryBean factory = new LocalContainerEntityManagerFactoryBean();
    factory.setJpaVendorAdapter(adapter);
    factory.setDataSource(this.springJpaDataSource());
    factory.setPackagesToScan("com.wrox.site.entities");
    factory.setSharedCacheMode(SharedCacheMode.ENABLE_SELECTIVE);
    factory.setValidationMode(ValidationMode.NONE);
    factory.setJpaPropertyMap(properties);
    return factory;
}
```



仔细检查这段代码，因为其中发生了很多操作。首先，它创建了一个 map 来存储 JPA 配置属性——在本例中，是 schema 属性。接下来，它创建了一个 `org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter` 并将其设置为工厂的适配器。这是一个特殊的 Spring 属性，执行了以下操作：

- 它告诉 `LocalContainerEntityManagerBean` 使用哪个 `PersistenceProvider`（`org.hibernate.HibernatePersistenceProvider`）。这取代了 `persistence.xml` 中的 `<provider>` 标签。
- 它告诉 `SharedEntityManagerBean` 它将代理哪个扩展的 `EntityManagerFactory` 接口（`org.hibernate.HibernateEntityManagerFactory`）以及代理哪个扩展的 `EntityManager` 接口（`org.hibernate.HibernateEntityManagerManager`）。
- 它告诉 Spring 如何正确将 Hibernate ORM 特有的异常转换为 `DataAccessExceptions`。
- 它通知事务管理在开始和结束事务时应该使用的任何额外步骤，以处理可能出现的任何问题。
- 它配置 Hibernate ORM 使用适用于你所用数据库的正确方言（dialect）。Hibernate 会尝试检测合适的方言，但对于 MySQL，它总是选择 `org.hibernate.dialect.MySQLDialect`。这种遗留方言仅用于 MySQL 4.x，不应与 MySQL 5.x 使用。最安全的方法是手动指定此值。

有 50 多不同的 Hibernate ORM 方言。表 21-1 列出了常见的 Hibernate ORM 方言以及它们支持的数据库版本。

## 表 21-1：常见的 Hibernate 方言

| 数据库名称及版本(s) | 方言类 (DIALECT CLASS) |
| :--- | :--- |
| H2 Database Engine | `org.hibernate.dialect.H2Dialect` |
| HyperSQL 1.8+, 2.x+ | `org.hibernate.dialect.HSQLDialect` |
| MySQL 4.x Generic | `org.hibernate.dialect.MySQLDialect` |
| MySQL 4.x MyISAM 引擎 | `org.hibernate.dialect.MySQLMyISAMDialect` |
| MySQL 4.x InnoDB 引擎 | `org.hibernate.dialect.MySQLInnoDBDialect` |
| MySQL 5.x+ Generic + MyISAM | `org.hibernate.dialect.MySQL5Dialect` |
| MySQL 5.x+ InnoDB 引擎 | `org.hibernate.dialect.MySQL5InnoDBDialect` |
| Oracle Database 8i | `org.hibernate.dialect.Oracle8iDialect` |
| Oracle Database 9i | `org.hibernate.dialect.Oracle9iDialect` |

## 表 21-1（续）

| 数据库名称及版本(s) | 方言类 (DIALECT CLASS) |
| :--- | :--- |
| Oracle Database 10g, 11g+ | `org.hibernate.dialect.Oracle10gDialect` |
| PostgreSQL 8.1 | `org.hibernate.dialect.PostgreSQL8Dialect` |
| PostgreSQL 8.2+ | `org.hibernate.dialect.PostgreSQL82Dialect` |
| Microsoft SQL Server 2000 | `org.hibernate.dialect.SQLServerDialect` |
| Microsoft SQL Server 2005 | `org.hibernate.dialect.SQLServer2005Dialect` |
| Microsoft SQL Server 2008 | `org.hibernate.dialect.SQLServer2008Dialect` |
| Microsoft SQL Server 2012+ | `org.hibernate.dialect.SQLServer2012Dialect` |
| Microsoft SQL Server 2014+ | `org.hibernate.dialect.SQLServer2014Dialect` |
| Sybase 10 | `org.hibernate.dialect.Sybase10Dialect` |
| Sybase 11+ | `org.hibernate.dialect.Sybase11Dialect` |
| Sybase 12+ | `org.hibernate.dialect.Sybase12Dialect` |
| Sybase 15+ | `org.hibernate.dialect.Sybase15Dialect` |
| Sybase Anywhere | `org.hibernate.dialect.SybaseAnywhereDialect` |

## 608 | 第 21 章 在 Spring Framework 仓库中使用 JPA

当你使用动态代理时，它们提供的方法建议（method advice）仅当另一个类在 Spring 管理的 bean 实例执行方法时生效。如果在 `FooBean` 实例上调用的方法执行了该相同实例上的另一个方法（无论是否使用此功能），方法建议将不会执行。（参见 `org.springframework.aop.AspectContext` 以了解实现此操作的一种简陋方法，你应该尽量避免使用。）CGLIB 代理会重写类中的所有非 final 方法，因此当 `FooBean` 调用另一个 `FooBean` 方法时（无论是否使用此功能），方法建议都会生效。然而，Spring 无法为类创建 CGLIB 代理。

如果这两个选项不能满足你的需求，你可以使用启用了 AspectJ 加载时织入（load-time weaving）。加载时织入实际上是在类被加载时修改其字节码，直接将方法建议添加到字节码中。这不仅适用于 final 类和非 final 类，也适用于从同一个对象调用的方法。对象甚至不需要是 Spring 管理的 bean，方法建议即可生效！（这对于遗留应用程序非常有用。）你可以通过将建议模式设置为 `AdviceMode.ASPECT`，装饰你的根配置类使用 `@EnableLoadTimeWeaving(aspectWeaving.ENABLED)`，并向你的项目添加 Maven 依赖项来启用它：

```xml
<dependency>
  <groupId>org.springframework.framework</groupId>
  <artifactId>spring-aspects</artifactId>
  <version>4.0.2.RELEASE</version>
  <scope>runtime</scope>
</dependency>
```

你将在第 24 章探索 AspectJ 加载时织入。然而，如果你在应用程序中选择了方法建议，你必须对它使用的每个方法以相同的方式进行配置，或者像配置 `@EnableManagement` 一样对 `@EnableAsync` 进行配置。如果配置方式不同，Spring 会选取其中一种配置并将其应用于两者，这可能会导致意外的结果。

此外，考虑这两个代理的执行顺序也是重要的。如果事务管理代理在异步代理之前执行，那么与设置异步方法相关的操作将包含在事务管理中，并且线程绑定事务可能无法正常工作。`RootContext` 类使用这两个注解的 order 属性来确保代理按正确的顺序执行（异步操作在事务管理之前）。

```java
@Configuration
@EnableScheduling
@EnableAsync(
  mode = AdviceMode.PROXY, proxyTargetClass = false,
  order = Ordered.HIGHER_PRECEDENCE
)
@EnableTransactionManagement(
    mode = AdviceMode.PROXY, proxyTargetClass = false,
    order = Ordered.LOWEST_PRECEDENCE
)
@ComponentScan(
    basePackages = "com.wrox.site",
    excludeFilters = 
    @ComponentScan.Filter((Controller.class, ControllerAdvice.class))
)
public class RootContextConfiguration implements ..
```

任何当你使用 `@EnableTransactionManagement` 的时候，必须提供一个默认的 `TransactionManager`。对于 JPA 资源，你应该使用 `org.springframework.orm.jpa.JpaTransactionManager`。它的构造函数会构建一个 `EntityManagerFactory`，因此你应该使用之前创建的 `LocalContainerEntityManagerFactoryBean` 来构造 `JpaTransactionManager`。

```java
@Bean
public PlatformTransactionManager jpaTransactionManager() {
    return new JpaTransactionManager(this.entityManagerFactory().getObject(null));
}
```

默认情况下，事务管理会寻找名为 `txManager` 的 bean，然后回退到应用上下文中找到的第一个实现 `PlatformTransactionManagers` 的 bean。在这种情况下，Spring 可能会选择错误的默认事务管理器来处理 `@Transactional`。为了防止这种情况，你的配置类可以实现 `TransactionManagerConfigurer`，并始终使用 `annotationDrivenTransactionManager` 返回的管理器作为 `@Transactional` 方法的默认管理器。

```java
@Configuration
@EnableScheduling
@EnableAsync(
    mode = AdviceMode.PROXY, proxyTargetClass = false,
    order = Ordered.HIGHEST_PRECEDENCE
)
@EnableTransactionManagement(
    mode = AdviceMode.PROXY, proxyTargetClass = false,
    order = Ordered.LOWEST_PRECEDENCE
)
@ComponentScan(
    basePackages = "com.wrox.site",
    excludeFilters = 
    @ComponentScan.Filter((Controller.class, ControllerAdvice.class))
)
public class RootContextConfiguration implements
    TransactionManagerConfigurer, SchedulingConfigurer
{
    ..

@Bean
public PlatformTransactionManager jpaTransactionManager() {
    return new JpaTransactionManager(this.entityManagerFactory().getObject(null));
}

@Override
public PlatformTransactionManager annotationDrivenTransactionManager() {
    return jpaTransactionManager();
}
```

## 创建和使用 JPA 仓库

在 Spring 仓库中使用 JPA 比在它自身中使用更简单，因为你不需要处理事务。本节展示了执行此操作的简单步骤，以及如何在你的服务中装饰事务边界。你将拥有三个仓库——每个实体对应一个。这是一个常见且实用的模式，但并非强制要求。你可以为几个相关的实体创建一个仓库。

```java
public interface AuthorRepository { ... }
public interface BookRepository { ... }
public interface PublisherRepository { ... }
```

要在仓库实现类中执行 JPA 操作，你需要一个 `EntityManager` 实例。正如之前讨论的，你所只需要声明一个 `EntityManager` 字段并用 `@PersistenceContext` 标记它即可。你不需要在字段上使用 `@Inject` 或 `@Autowired`；`@PersistenceContext` 就起到了这个作用。因为 `@PersistenceContext` 出现于 Spring 支持 JPA 之前，所以没有与 Spring 等效的 Spring 注解，因此这个注解是你唯一需要担心的。

```java
@Repository
public class DefaultAuthorRepository implements AuthorRepository {}
```

```java
@PersistenceContext EntityManagerManager;
...
@Repository
public class DefaultBookRepository implements BookRepository {
    @PersistenceContext EntityManagerManager;
    ...
}

@Repository
public class DefaultPublisherRepository implements PublisherRepository {
    @PersistenceContext EntityManagerManager;
    ...
}
```

你可能在本章之前记得，这里注入的 `EntityManager` 并不是 JPA 供应商（Hibernate ORM）提供的那个。它是真实对象的代理，并会自动委托给为同一事务中之前的方法调用创建的、线程绑定的 `EntityManager`（如果尚未创建则创建一个一个新的 `EntityManager` 和事务）。

## 实现标准 CRUD 操作

你的仓库仅执行简单的操作——返回单个实体和实体列表、添加实体、更新实体和删除实体。这在 `AuthorRepository` 接口中很容易表示。

```java
public interface AuthorRepository {
    Iterable<Author> getAll();
    void add(Author author);
    void update(Author author);
    void delete(Author author);
    void delete(long id);
}
```

Listing 21-1 中这些方法的实现与你在上一章的 `EntityServlet` 中使用的方法略有不同。它没有使用 Criteria API，而是使用持久化查询语言（JPQL）来查找实体。你可以看出，JPQL 与 ANSI SQL 非常相似；然而，确实存在一些差异。例如，SELECT 子句中的标识符标识的是返回哪些实体，而不是 SQL 查询中返回哪些列。JPQL 查询可以在 WHERE 子句中使用多个实体，但在 SELECT 中只返回其中一个。

## 第 21 章 在 Spring Framework 仓库中使用 JPA

句。此外，FROM 子句中的标识符标识的是实体名称，而不是 SQL 查询中的表名。

## 列表 21-1：DefaultAuthorRepository.java

```java
@Repository
public class DefaultAuthorRepository implements AuthorRepository
{
    public PersistenceContext entityManager;

    @Override
    public Iterable<Author> getAll()
    {
        return this.entityManager.createQuery(
            "SELECT a FROM Author a ORDER BY a.name", Author.class
        ).getResultList();
    }

    @Override
    public Author get(long id)
    {
        return this.entityManager.createQuery(
            "SELECT a FROM Author a WHERE a.id = :id", Author.class
```



```java
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

## 为你的所有实体创建一个基础仓库

思考一下 `AuthorRepository` 及其指定的方法，并思考 `BookRepository` 和 `PublisherRepository` 应该指定的方法。你会立即发现它们的相似性：

```java
public interface BookRepository {
    Iterable<Book> getAll();
    Book get(long id);
    void add(Book book);
    void update(Book book);
    void delete(Book book);
    void delete(long id);
}

public interface PublisherRepository {
    Iterable<Publisher> getAll();
    Publisher get(long id);
    void add(Publisher publisher);
    void update(Publisher publisher);
    void delete(Publisher publisher);
    void delete(long id);
}
```

如果你考虑这些方法的实现，你会很快意识到它们与 `DefaultAuthorRepository` 类几乎完全相同。你会怀疑是否有一种方法可以编写代码处理你所有的实体。为了使其有用，这样的仓库需要使用泛型。根据最佳实践并从接口开始，考虑它可能看起来如下：

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

泛型变量 `I` 代表实体的代理键——通常是 `long`，但并不总是如此，这就是为什么它是一个变量。`E` 代表实体类型。Bean Validation 的 `@NotNull` 约束是告诉仓库用户和实现者不允许空参数和返回空值的极佳方法。由于 `I` 和 `E` 在此存在歧义（在理论上它们可以是相同的类型），编译器无法区分类型为 `I` 的方法参数和类型为 `E` 的方法参数。因此，`delete` 和 `deleteById` 方法使用了不同的名称。

> 注意：JPA 并不要求实体或其代理键实现 `Serializable`，但这是一个为了强制执行的最佳实践限制。

现在，你的仓库接口只需要扩展这个父接口，并指定适用于它们所访问的实体的类型变量。

```java
public interface AuthorRepository extends GenericRepository<Long, Author> {
}
```

```java
public interface BookRepository extends GenericRepository<Long, Book> {
    getByIsbn(String isbn);
}
```

```java
public interface PublisherRepository extends GenericRepository<Long, Publisher> {
}
```

`AuthorRepository` 和 `PublisherRepository` 接口不需要定义方法，因为它们不需要。方法都定义在 `GenericRepository` 接口中，类型值使得方法变得具体化。`BookRepository` 定义了一个额外的通过 ISBN 查找的方法——这是一个常见的需求。

下一步是为所有 `GenericRepositories` 定义通用实现。从 Java 8 开始，你可以采用使用 `default` 方法的独特方法：

```java
@Validated
public interface GenericRepository<I extends Serializable, E extends Serializable>
@NotNull
  default Iterable<E> getAll()
```

然而，由于以下原因，这是一个糟糕的选择：

- `default` 方法的设计目的并不是取代抽象类。它们的创建是为了在不破坏现有实现的情况下进行改进。例如，Java 8 集合通过默认方法得到了改进，而没有破坏现有的 `Collection`、`List`、`Set` 和 `Iterable` 实现。默认方法与抽象类中的具体方法具有不同的语义，不应为此目的。
- 你在这些方法中需要注入 `EntityManager`，而你无法在接口中获取它。
- 你需要访问 `I` 和 `E` 的类型（类）来执行安全的 JPA 操作。实现此点的最好（如果你想让这些值变为 `final`）是构造函数，而接口没有构造函数。

更合适的方法是使用泛型基类，这可以满足你所有的需求。

```java
public abstract class GenericBaseRepository<I extends Serializable, E extends Serializable> {
    protected final Class<I> idClass;
    protected final Class<E> entityClass;

    public GenericBaseRepository(Class<I> idClass, Class<E> entityClass) {
        this.idClass = idClass;
        this.entityClass = entityClass;
    }
}
```

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
        .
    }
}
```

关于上述代码的几点说明：

- `DefaultRepository` 演示了 Java 语言，但当你没有具体的实体类时并不该使用它（你可以在泛型仓库中选择实体）。`GenericJpaRepository` 而是使用 criteria API 来返回所有实体列表并按 ID 删除。
- `deleteById` 方法仅在你的所有实体都具有名为 `id` 的属性时有效，事实情况也是如此。如果代理键属性名称不同，你必须通过 ID 获取实体，然后调用 `remove` 方法。
- `DefaultAuthorRepository` 和 `DefaultPublisherRepository` 不再需要方法，因为它们的方法已经在 `GenericJpaRepository` 中定义了。
- 只有 `DefaultBookRepository` 需要一个方法，用于实现 `BookRepository` 接口中指定的额外 `getById` 方法。

```java
@Repository
public class DefaultAuthorRepository extends GenericJpaRepository<Long, Author>
    implements AuthorRepository {
}
```

```java
@Repository
public class DefaultBookRepository extends GenericJpaRepository<Long, Book>
    implements BookRepository {

    @Override
    public Book getByIsbn(String isbn) {
        CriteriaBuilder builder = this.entityManager.getCriteriaBuilder();
        CriteriaQuery<Book> query = builder.createQuery(this.entityManager);
        Root<Book> root = query.from(this.entityManager);
        return this.entityManager.createQuery(
            select(root).where(builder.equal(root.get("isbn"), isbn))
        ).getResultList();
    }
}
```

```java
@Repository
public class DefaultPublisherRepository
    extends GenericJpaRepository<Long, Publisher>
    implements PublisherRepository {
}
```

JPA Criteria OR/M API 并不是最直观的 API，而且比 Hibernate API 更难使用。Hibernate 的设计是为了方便在每次查找中添加表达式和限制条件，旨在模拟查询语言本身。`GenericJpaRepository` 中的 `getAll` criteria 实际上可以读为“从实体中选择”，这与我们为此目的创建的 JPQL 查询完全相同，只是缺少了排序指令。如果顺序很重要，你有几种选择。你可以根据需要重写该方法，或者指定一个子类使用的构造函数参数来指定默认排序指令。使用 criteria API 进行排序并不困难。

```java
Root<Book> root = query.from(Book.class);
return this.entityManager.createQuery(
    select(root).orderBy(builder.asc(root.get("name")))
).getResultList();
```

新的查询可以读为“按 Book.name 升序从 Book 中选择”。注意我们先创建了 `root` 查询类型，是因为在 `FROM` 和 `ORDER` 子句中都需要使用 `Book`。这似乎是多余的，因为 `CriteriaQuery` 实例已经类型化，但请记住 `CriteriaQuery` 是针对将返回的对象进行类型的。查询可能会使用返回类型以外的类型。你通常会发现 JPQL 更容易使用，也可以使用 criteria API 执行任何选项。这取决于你的用例和个人偏好来决定使用哪种。

## 在你的服务中划分事务边界

如之前所述，你使用 Spring 的 `@Transactional` 注解或 JTA 的 `@Transactional` 注解来告诉 Spring 如何开始和结束事务。Spring 的 `@Transactional` 比 JTA 注解更强大且灵活。

使用 `@javax.transaction.Transactional`，你可以通过 `dontRollbackOn` 属性定义一个不应触发回滚的异常黑名单，通过 `rollbackOn` 定义一个覆盖所有 `RuntimeException` 默认回滚规则的异常白名单，并使用 `Transactional.TxType` 枚举值属性定义创建事务的规则。`Transactional.TxType` 具有以下枚举常量：

- `MANDATORY`：表示必须已经存在事务。
- `NEVER`：表示不能存在事务。
- `NOT_SUPPORTED`：意味着不需要事务。
- `REQUIRED`：表示必须存在事务。
- `REQUIRES_NEW`：如果存在事务，则创建一个新事务。
- `SUPPORTS`：意味着可以使用现有事务。
- `NESTED`：如果存在事务，则创建一个嵌套事务。

JPA Criteria OR/M API 并不是最直观的 API，而且比 Hibernate API 更难使用。Hibernate 的设计是为了方便在每次查找中添加表达式和限制条件，旨在模拟查询语言本身。`GenericJpaRepository` 中的 `getAll` criteria 实际上可以读为“从实体中选择”，这与我们为此目的创建的 JPQL 查询完全相同，只是缺少了排序指令。如果顺序很重要，你有几种选择。你可以根据需要重写该方法，或者指定一个子类使用的构造函数参数来指定默认排序指令。使用 criteria API 进行排序并不困难。

受默认 (JPA) 事务管理器控制。同样，`actionTwo` 显式使用 `JpaTransactionManager` 执行，而 `actionThree` 则显式使用 `DataSourceTransactionManager` 执行。

```java
public class SomeService {
    @Transactional
    public void actionOne();

    @Transactional("jpaTransactionManager")
    public void actionTwo();

    @Transactional("dataSourceTransactionManager")
    public void actionThree();
}
```



# 使用 @Transactional 注解

在使用 `@Transactional` 注解时，你可以对接口、单个接口方法、类或类方法进行注解。对接口进行注解，等同于对该接口的方法进行注解。同样，对类进行注解等同于对类的方法进行注解。当应用程序代码需要事务边界时，最佳实践是对接口或其方法进行注解；`@Transactional` 仅在启用动态代理（`proxyTargetClass = true`）时有效，否则接口注解将失效。如果你需要使用 CGLIB 代理，与在接口上建立契约的 Bean 验证注解不同，`@Transactional` 是一个实现细节，不属于契约。列表 21-3 中的 `DefaultBookManager` 实现演示了对服务方法进行注解。`DefaultBookManager` 虽然未显示这一点，但 `@Transactional` 方法可以使用存储库（repositories）访问并管理多个实体，且都在同一个事务上下文中。

## 列表 21-3: DefaultBookManager.java

```java
@Service
public class DefaultBookManager implements BookManager {

    @Inject
    AuthorRepository authorRepository;

    @Inject
    BookRepository bookRepository;

    @Inject
    PublisherRepository publisherRepository;

    @Override
    public List<Author> getAuthors() {
        return this.toList(this.authorRepository.getAll());
    }

    @Override
    public List<Book> getBooks() {
        return this.toList(this.bookRepository.getAll());
    }
}
```

## 列表 21-3 (续)

```java
@Override
public List<Publisher> getPublishers() {
    return this.toList(this.publisherRepository.getAll());
}

private <E> List<E> toList(Iterable<E> i) {
    List<E> list = new ArrayList<>();
    i.forEach(list::add);
    return list;
}

@Override
public void saveAuthor(Author author) {
    if (author.getId() < 1)
        this.authorRepository.add(author);
    else
        this.authorRepository.update(author);
}

@Override
public void saveBook(Book book) {
    if (book.getId() < 1)
        this.bookRepository.add(book);
    else
        this.bookRepository.update(book);
}

@Override
public void savePublisher(Publisher publisher) {
    if (publisher.getId() < 1)
        this.publisherRepository.add(publisher);
    else
        this.publisherRepository.update(publisher);
}
```

## 使用 Transactional 服务方法

在使用 `@Transactional` 服务方法时，不需要任何配置。从消费者的角度来看，事务是透明发生的。`BookController` 的工作与第 20 章中的 `EntityServlet` 类似：它为 GET 请求列出作者、书籍和出版社，并为 POST 请求创建它们。

```java
@WebController
public class BookController {

    private final Random random;

    @Inject
    BookManager bookManager;

    public BookController() {
        try {
            this.random = SecureRandom.getInstanceStrong();
        } catch (NoSuchAlgorithmException e) {
            throw new IllegalStateException(e);
        }
    }

    @RequestMapping(value = "/", method = RequestMethod.GET)
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
        publisher.setDateFound(Calendar.getInstance());
        this.bookManager.save(publisher);

        Author author = new Author();
        author.setName("Nicholas");
        author.setEmail("nick@example.com");
        this.bookManager.save(author);

        Book book = new Book();
        book.setTitle("Professional Java");
        book.setPrice(59.99);
        this.bookManager.save(book);

        return "redirect:/";
    }
}
```

## 将数据转换为实体

要测试此功能，请遵循以下步骤：

1. 确保你使用了 DTO。
2. 编译代码。
3. 打开浏览器并查看实体。

## 为支持创建实体

由于 `Ticket` 包含一个实例和一个 `Map`，你需要创建一个 `TicketEntity` 来从 DTO 传输数据。它看起来像 `Ticket`，但使用 `Timestamp` 表示创建日期，并使用客户的 `UserPrincipal` ID 而不是名称。

```java
@XmlRootElement(name = "attachment")
@Entity
public class Attachment implements Serializable {

    private static final longVersionUID = 1L;

    private long id;
    private long ticketId;
    private String name;
    private String mimeContentType;

    @Basic
    public String getUsername() {
    }

    public void setUsername(String username) {
    }

    @Basic
    @Column(name = "HashedPassword")
    public byte[] getPassword() {
    }

    public void setPassword(byte[] password) {
    }
}
```

```java
@Entity
@Table(name = "Ticket")
public class TicketEntity implements Serializable {

    private static final long serialVersionUID = 1L;

    private long id;
    private long userId;
    private String subject;
    private String body;
    private Timestamp dateCreated;

    @Id
    @Column(name = "Ticket", strategy = GenerationType.IDENTITY)
    public long getId() { ... }

    public void setId(long id) { ... }

    @Basic
    public long getUserId() { ... }

    public void setUserId(long userId) { ... }

    @Basic
    public String getSubject() { ... }

    public void setSubject(String subject) { ... }

    @Basic
    public String getBody() { ... }

    public void setBody(String body) { ... }

    @Basic
    public Timestamp getDateCreated() { ... }

    public void setDateCreated(Timestamp dateCreated) { ... }
}
```

这些是你目前需要的所有实体。你还需要一个存储这些实体的数据库架构，并且初始的四个用户在之前的章节中硬编码在 Java 代码中。

```sql
USE CustomerSupport;
```

```sql
CREATE TABLE UserPrincipal (
    UserId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    Username VARCHAR(30) NOT NULL,
    HashedPassword BINARY(60) NOT NULL,
    UNIQUE KEY UserPrincipal_Username (Username)
) ENGINE = InnoDB;
```

```sql
CREATE TABLE Ticket (
    TicketId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    UserId BIGINT UNSIGNED NOT NULL,
    Subject VARCHAR(25) NOT NULL,
    Body TEXT,
    Created DATETIME NOT NULL,
    CONSTRAINT TicketUser FOREIGN KEY (UserId)
    REFERENCES UserPrincipal (UserId) ON DELETE CASCADE
) ENGINE = InnoDB;
```

```sql
CREATE TABLE Attachment (
    AttachmentId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    TicketId BIGINT UNSIGNED NOT NULL,
    AttachmentName VARCHAR(255) NOT NULL,
    MimeType VARCHAR(255) NOT NULL,
    Contents BLOB NOT NULL,
    CONSTRAINT Attachment_TicketId FOREIGN KEY (TicketId)
    REFERENCES Ticket (TicketId) ON DELETE CASCADE
) ENGINE = InnoDB;
```

```sql
INSERT INTO User (Username, HashedPassword) VALUES ('Nicholas', '$2a$10S0k/yAQgN8J5dCSEN.61EbVvHeKtdtyv.Rpra4jzR55S1KSC');
INSERT INTO User (Username, HashedPassword) VALUES ('Sarah', '$2a$10SJsKyMo.Jb4TT42/4RZgaUtAyYKZLcFeND1b0rzo7yWH0RQFQBY9');
INSERT INTO User (Username, HashedPassword) VALUES ('Mike', '$2a$10S0cwStNd.Y9hRffcBct.ECA90aj/QPbwnfJjCMovdTTsaISIG');
INSERT INTO User (Username, HashedPassword) VALUES ('John', '$2a$10vacugBw17trRRH8sByokztQThemfnK3c2W1Lav7/3Amby');
```

这些存储库（repositories）用于实体。接口继承了 `GenericRepository`，而实现类也继承了 `GenericRepository`。`UserRepository` 需要一个自定义方法，以便通过用户名查找用户，而 `AttachmentRepository` 需要一个方法来查找特定工单的附件。

```java
public interface UserRepository extends GenericRepository<Long, UserPrincipal> {
    UserPrincipal getByUsername(String username);
}
```

```java
@Repository
public class DefaultUserRepository
    extends GenericRepository<Long, UserPrincipal>
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
```

```java
@Repository
public class DefaultTicketRepository
    extends GenericRepository<Long, TicketEntity>
    implements TicketRepository { }
```

```java
public interface AttachmentRepository extends GenericRepository<Long, Attachment> {
    Iterable<Attachment> getById(long ticketId);
}
```

```java
@Repository
public class DefaultAttachmentRepository
    extends GenericRepository<Long, Attachment> {

    @Override
    public Iterable<Attachment> getById(long ticketId) {
        return this.entityManager.createQuery(
            "SELECT a FROM Attachment WHERE a.ticketId = :id ORDER BY a.id",
    }
}
```



```java
Attachment.class

).setParameter("id", ticketId).getResultList();

}

}
```

# 使用 BCrypt 安全用户密码

你需要更新客户支持应用程序中的服务以使用新的存储库。被重命名为 `DefaultAuthenticationService` 的 `TemporaryAuthenticationService` 现在要安全得多。它使用了行业标准的 jBCrypt Java 实现 BCrypt 哈希算法，该算法由以下 Maven 依赖提供。

```xml
<dependency>
  <groupId>org.mindrot</groupId>
  <artifactId>bcrypt</artifactId>
  <version>0.3m</version>
</dependency>
```

使用 BCrypt 时，它是非常强大的。它的设计初衷是极其缓慢。这听起来可能违背直觉，但实际上它并不会影响登录或保存用户的时间。性能的影响体现在于字典攻击中生成数亿个样本密码时——在字典攻击中使用不同的方法——在字典攻击中使用不同的方法。

你永远不应该使用像 MD5 或任何 SHA-1 变体哈希算法，因为它们太快了。BCrypt 的设计很缓慢，这使得暴力攻击变得困难得多。

# 列表 24：DefaultAuthenticationService.java

```java
@Service
class DefaultAuthenticationService implements AuthenticationService {

    private static final Logger log = LoggerFactory.getLogger(DefaultAuthenticationService.class);

    private static final int ROUNDS = 10;

    private final UserRepository userRepository;

    private final TicketRepository ticketRepository;

    private final AttachmentRepository attachmentRepository;

    @Autowired
    public DefaultAuthenticationService(UserRepository userRepository, 
                                        TicketRepository ticketRepository, 
                                        AttachmentRepository attachmentRepository) {
        this.userRepository = userRepository;
        this.ticketRepository = ticketRepository;
        this.attachmentRepository = attachmentRepository;
    }

    @Override
    @Transactional
    public boolean authenticate(String username, String password) {
        User user = userRepository.getByUsername(username);

        if (user == null) {
            log.warn("User not found: {}", username);
            return false;
        }

        if (BCrypt.checkpw(password, user.getHashedPassword())) {
            log.info("User {} authenticated successfully.", username);
            return true;
        } else {
            log.warn("Invalid password for user: {}", username);
            return false;
        }
    }
}
```

# 列表 25：DefaultTicketService.java

```java
@Service
public class DefaultTicketService implements TicketService {

    private final TicketRepository ticketRepository;
    private final AttachmentRepository attachmentRepository;
    private final UserRepository userRepository;

    @Autowired
    public DefaultTicketService(TicketRepository ticketRepository, 
                                 AttachmentRepository attachmentRepository, 
                                 UserRepository userRepository) {
        this.ticketRepository = ticketRepository;
        this.attachmentRepository = attachmentRepository;
        this.userRepository = userRepository;
    }

    @Override
    @Transactional
    public List<Ticket> getAllTickets() {
        List<Ticket> list = new ArrayList<>();
        ticketRepository.getAll().forEach(e -> list.add(convert(e)));
        return list;
    }

    @Override
    @Transactional
    public Ticket getTicket(long id) {
        TicketEntity entity = ticketRepository.get(id);
        return entity == null ? null : convert(entity);
    }

    private Ticket convert(TicketEntity entity) {
        Ticket ticket = new Ticket();
        ticket.setId(entity.getId());
        ticket.setCustomerName(
            userRepository.get(entity.getUserId()).getUsername()
        );
        ticket.setSubject(entity.getSubject());
        ticket.setBody(entity.getBody());
        ticket.setDateCreated(Instant.ofEpochMilli(
            entity.getDateCreated().getTime()
        ));
        this.attachmentRepository.getByTicketId(entity.getId())
            .forEach(attachment -> ticket.addAttachment(attachment));
        return ticket;
    }

    @Override
    @Transactional
    public void save(Ticket ticket) {
        TicketEntity entity = new TicketEntity();
        entity.setId(ticket.getId());
        entity.setUserId(userRepository.getByUsername(
            ticket.getCustomerName()
        ).getId());
        entity.setSubject(ticket.getSubject());
        entity.setBody(ticket.getBody());
        if (ticket.getId() < 1) {
            ticket.setDateCreated(Instant.now());
            entity.setDateCreated(new Timestamp(
                ticket.getDateCreated().toEpochMilli()
            ));
            this.ticketRepository.add(entity);
            ticket.setId(entity.getId());
            for (Attachment attachment : ticket.getAttachments()) {
                attachment.setTicketId(entity.getId());
                this.attachmentRepository.add(attachment);
            }
        } else {
            this.ticketRepository.update(entity);
        }
    }
}
```

# 列表 21-5（续）

```java
@Transactional
public void deleteTicket(long id) {
    this.ticketRepository.deleteById(id);
}
```

你应该能够在你的 Tomcat 的 `context.xml` 文件中部署 Customer Support 应用，但这次你的工单将持久化在数据库中：

1. 为你的 Tomcat 创建以下 `DataSource` 资源，并运行 `create.sql` 脚本来创建数据库和表。

   ```xml
   <Resource name="jdbcCustomerSupport" type="javax.DataSource" maxActive="20" maxIdle="10000" username="tomcat" password="password1234" className="com.mysql.jdbc.Driver" defaultIsolation="READ_COMMITTED" url="jdbc:mysql://localhost/CustomerSupport" />
   ```

2. 编译应用程序并从你的 IDE 启动 Tomcat。
3. 访问 http://localhost:8080/support/ 并使用数据库中预存在的用户之一进行登录。
4. 创建一个或两个工单，附加一些文件，然后重启 Tomcat。这些工单仍然存在，并持久化在数据库中。

你应该在 MySQL Workbench 中查询数据库表以查看持久化的实体。

### 总结

在本章中，你学习了 Spring Framework 中的 JPA 和 Hibernate ORM。你实验了创建 `LocalContainerEntityManagerFactoryBean`，学习了 Spring Framework 建议方法的不同方式，探索了使用 `@Transactional` 和 `JpaTransactionManager` 进行的事务管理，并创建了一个可以处理所有实体标准 CRUD 操作的通用仓库（repository）。你学习了 Spring 如何完全替换 `persistence.xml` 文件并在内存中创建持久化单元，从而减少了你需要编写的 XML 数量。你还对 criteria API 和 JPQL 进行了比较，并看到了使用两者的优缺点。最后，在将密码持久化到数据库之前，你使用安全的 `BCrypt` 密码慢哈希算法保护了用户密码。

然而，你可能会发现仍然有大量冗余的代码需要编写，特别是在查找持久化实体时。如果你需要使用许多不同的字段以许多不同的方式查找实体怎么办？还有结果的排序和分页处理，这可能会让问题变得更加复杂。在下一章中，你将学习 Spring Data JPA 如何让你的 JPA 仓库变得更加简单——甚至变得无需编写它们。

# 22 使用 Spring Data JPA 消除模板代码仓库

## 本章内容

- 理解 Spring Data 的统一数据访问
- 创建 Spring Data JPA 仓库
- 如何重构 Customer Support 应用

## 本章 WROX.COM 代码下载

你可以在 http://www.wrox.com/projavaforwewabapps 的 "Download Code" 标签页找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Spring-Data-JPA 项目
- Customer-Support-v16 项目

## 本章的新 MAVEN 依赖

除了在前几个章节中引入的 Maven 依赖外，你还需要以下 Maven 依赖。排除了 SLF4J JCL 桥接，因为你对 Log4j 2 的使用使得桥接变得不再需要了。

```xml
<dependency>
  <groupId>org.springframework.data</groupId>
  <artifactId>spring-data-jpa</artifactId>
  <version>1.5.0.RELEASE</version>
</dependency>
```

```xml
<scope>compile</scope>
<exclusions>
  <exclusion>
    <groupId>org.slf4j</groupId>
    <artifactId>jcl-over-slf4j</artifactId>
  </exclusion>
</exclusions>
</dependency>
```

```xml
<dependency>
  <groupId>org.slf4j</groupId>
  <artifactId>slf4j-api</artifactId>
  <version>1.7.5</version>
  <scope>runtime</scope>
</dependency>
```



# 理解 Spring Data 的统一数据访问

在第 20 章中，你学习了 Persistence API 有多强大，在第 21 章中，你学习了 Spring Framework 如何让 JPA 变得更加简单。Spring 负责所有的事务管理和 `EntityManager` 的创建，你无需亲自操作。它消除了在应用程序中包含 `persistence.xml` 文件的需求！最有帮助的是，你创建了一个通用基仓库，所有的仓库都可以扩展它，提供了基本的 CRUD 操作，而无需为每个仓库编写它们。

但让我们面对现实：你的大多数仓库都需要匹配标准的 CRUD 操作。首先，你经常需要使用主键以外的唯一列进行基本查找。在 `last-Spring-JPA` 项目中，你添加了通过 ISBN 查找书籍的方法，而在 `Customer-Support-v15` 项目中，你使用了 `UserRepository` 包含的方法通过用户名查找用户。

然后，你需要根据多个字段过滤实体。例如，作为系统管理员，你可能需要通过姓、名或电话号码查找人员，这可能会返回多个结果。然后是搜索，例如查找包含某些关键词的产品，或查找内容匹配搜索短语的工单。最后，可能是最难处理的任务：你无法返回所有实体的列表，甚至是符合过滤条件的实体列表。这既不可行也不易于在你的用户界面中使用（想象从数据库返回 1000 万条记录，只在屏幕上显示 50 条。）因此，你必须以某种方式实现结果的分页，在此过程中你必须始终考虑结果的排序。

## 避免代码重复

使用持久查询语言（JPQL）和 criteria API 都可以对结果进行排序和分页。然而，并没有捷径。两种操作都需要你构建并执行两个独立的查询：一个返回计数，另一个返回结果子集。以下代码演示了使用 JPQL 的这种方法。在两个示例中使用 `predicates...` 的地方就是你放置用于过滤结果的 `WHERE` 语句的地方，这意味着你需要以相同的方式两次创建这些谓词并设置参数。Hibernate API 要简单得多，它允许你构建一次实体并复用它来生成计数和实体列表。

幸运的是，并非如此。Spring Data 是一个与 Spring Framework 独立但又依赖于它的 Spring 项目，它可以为你编写存储库类（repositories）。你只需要创建一个接口，Spring Data 就会在运行时动态生成必要的代码来实现该接口。图 22-1 显示了你在 Spring Framework 中已经习惯的正常程序执行路径。你的控制器是针对服务接口编写的。Spring 拦截对这些接口的调用，并执行任何必要的任务，例如 Bean 验证（Bean Validation）、启动事务、异步调用方法。当服务方法返回时，Spring 可能会执行进一步的 Bean 验证并提交或回滚事务。

同样，服务代码也是针对仓库接口编写的。当你调用仓库方法时，Spring 再次执行任何必要的任务，如启动事务。当方法返回时，Spring 将任何抛出的异常转换为 `DataAccessException`。你真正需要的仓库代码。它不包含业务逻辑（应该在服务层中）或用户逻辑（应该在控制器中），因此你的应用程序在仓库中不需要做任何特殊操作。它是用于持久化和检索实体的样板代码（boilerplate code）。

![](img/4677f981a0e1067137bb55a122f8498d_671_0.png)
图 22-1

当你使用 Spring Data 时，这些仓库代码就会为你写好了。极少数情况下你需要编写 Spring Data 无法自动处理的仓库代码，而且存在机制来处理这些罕见情况。图 22-2 显示了这种新的执行路径。其中大部分内容保持不变，因为控制器和服务包含你应用程序特有的逻辑。但在你对仓库接口执行一个方法后，你编写的代码就结束了。在该点之后发生的一切都由 Spring Framework 和 Spring Data 处理。

Spring Data 支持多种数据访问方法，包括 JPA、JdbcTemplate、NoSQL 等。它的主要子项目 Spring Data Commons 提供了一个核心工具集，所有其他项目都使用该工具集来创建存储库。Spring Data JPA 子项目为基于 Java Persistence API 实现的仓库提供支持。

![](img/4677f981a0e1067137bb55a122f8498d_672_0.png)
图 22-2

## 第 22 章 使用 Spring Data JPA 消除样板仓库

> 注意：你使用了许多来自 Spring Data Commons 和 Spring Data JPA 的不同类，本书无法告诉你关于它们的每一个细节。你应该审阅并收藏 Spring Data Commons API 文档和 Spring Data JPA API 文档以供参考。

## 使用仓库接口

Spring Data Commons 提供的工具之一是 `org.springframework.data.repository.Repository<T, ID>` 接口，它没有指定任何方法。只有扩展 `Repository` 的接口才有资格进行动态实现。泛型类型 `T` 和 `ID` 代表实体类型和标识符类型，类似于你在第 21 章中创建的 `GenericRepository`。

> 注意：Spring Data 中的类型参数与你在 `GenericRepository` 中创建的相反。此外，`ID` 参数必须实现 `Serializable`，但对 `T` 没有强制性限制。

你可以直接创建一个扩展 `Repository` 的接口，但因为它没有指定任何方法，你可能永远不会这样做。更有用的方法是扩展 `org.springframework.data.repository.CrudRepository<T, ID>`，它指定了许多用于基本 CRUD 操作的方法。此接口与你在第 21 章中创建的 `GenericRepository` 非常相似，但使用了一些不同的约定。

- `count()` 返回一个表示扩展 `T` 的未过滤实体总数的 `long` 类型。
- `delete(T)` 和 `delete(ID)` 删除单个指定的实体，而 `delete(Iterable<? extends T>)` 删除多个实体，`deleteAll()` 则删除该类型的所有实体。
- `exists(ID)` 返回一个布尔值，表示具有给定代理键的类型实体是否存在。
- `findAll()` 返回所有类型为 `T` 的实体，而 `findAll(Iterable<ID>)` 返回具有给定代理键的类型为 `T` 的实体。
- `findOne(ID)` 根据代理键检索单个类型为 `T` 的实体。
- `save(S)` 保存类型为 `S`（其中 `S` 扩展 `T`）的给定实体（或更新），并返回保存的实体。
- `save(Iterable<S>)` 保存所有实体（所有 `S` 均扩展 `T`），并以新的 `Iterable<S>` 形式返回保存的实体。

## 理解 Spring Data 的统一数据访问

所有 Spring Data 项目已经知道如何为给定类型实现这些方法。然而，你会发现此仓库仍然没有指定支持分页和排序的方法。这样做是为了防止这些方法弄乱你并不希望支持分页和排序的仓库。如果你希望仓库提供分页和排序方法，它的接口可以扩展 `org.springframework.data.repository.PagingAndSortingRepository<T, ID>`（实现 `Serializable`）。

- `findAll(Sort)` 根据提供的 `Sort` 指令将所有实体作为 `Iterable<T>` 返回。
- `findAll(Pageable)` 返回单个 `org.springframework.data.domain.Page<T>` 实体，该实体已根据 `Pageable` 指令进行排序和绑定。

`org.springframework.data.domain.Sort` 对象封装了关于用于排序结果的属性以及排序方向的信息。`org.springframework.data.domain.Pageable` 同样封装了 `Sort` 以及每页实体数量（两者均为 `int`）。在 Web 应用程序中，你通常不需要担心在 Spring 中创建 `Pageable` 对象。Spring Data 提供了两个 `org.springframework.web.support.HandlerMethodArgumentResolver` 实现，它们将 HTTP 请求参数转换为 `Pageable` 和 `Sort` 对象：`org.springframework.web.servlet.PageHandlerMethodArgumentResolver`。

## 查询方法

Spring Data 最强大的功能之一是它能够从方法名称自动生成查询。你只需要在仓库接口中声明一个方法，Spring Data 就会根据方法名称解析并生成相应的查询。这种机制称为“查询方法”。

### 查询方法命名规则

查询方法名称通常以 `find...By`、`read...By`、`query...By`、`count...By` 或 `get...By` 开头。`By` 后面跟着属性名称和条件关键字。Spring Data 会忽略 `find`、`read`、`query`、`count`、`get` 等引导词以及 `By`、`And`、`Or` 等连接词，重点解析实体属性和条件关键字。

例如：
- `findByLastname`：根据 lastname 查找
- `findByFirstnameAndLastname`：根据 firstname 和 lastname 查找
- `findByAgeGreaterThan`：查找 age 大于给定值的实体
- `countByLastname`：统计指定 lastname 的实体数量

### 支持的条件关键字

除了可以分隔多个标准的 `Or` 和 `And`，查询方法名中的标准还可以包含其他关键字来细化标准匹配：

- 在没有其他关键字的情况下，`Is` 和 `Equals` 是隐含的，但你也可以显式使用它们。例如，`findByIsbn` 等同于 `findByIsbnEquals`。
- `Not` 和 `IsNot` 会否定任何其他条件。在没有其他关键字的情况下，`Is` 和 `Equals` 仍然是隐含的，所以 `findByIsbnNot` 等同于 `findByIsbnIsNotEqual`。
- `After` 和 `IsAfter` 表示该属性是一个应该在给定值之后的日期和时间。例如：`findByDateAfter(Date date)`。
- `Containing`、`IsContaining` 和 `Contains` 表示属性值的开头和结尾可以是任何内容，但应该包含给定值。这类似于 `StartingWith`、`IsStartingWith` 和 `StartsWith`，后者表示该属性应以指定值开头。同样，`EndingWith`、`IsEndingWith` 和 `EndsWith` 表示该属性应以指定值结尾。例如：`findByTitleContains(String value)` 等同于 SQL 标准 `WHERE title LIKE '%value%'`。
- `Like` 和 `IsLike` 与 `Contains`、`StartsWith` 和 `EndsWith` 相似，区别在于你的值已经包含了通配符（而不是由 Spring Data 为你添加）。这赋予了你使用更高级模式的灵活性。`NotLike` 表示不匹配。例如：`findByTitleLike(String value)` 用 `"%Catcher%"` 调用，将匹配 "The Catcher in the Rye" 和 "Catcher Home Rye"。
- `Between` 和 `IsBetween` 表示该属性应该位于此属性标准的两个参数之间。你可以对任何可以通过这种方式进行数学比较的类型使用 `Between`，例如数值和日期类型。例如：`findByDateFoundBetween(Date start, Date end)`。
- `Exists` 表示某些内容应该存在。名称可能取决于存储介质。它大致等于 JPQL 和 SQL 中的 `EXISTS` 关键字。
- `True` 和 `IsTrue` 表示该属性应为真，`False` 和 `IsFalse` 表示命名属性应为假。这些关键字不需要方法参数，因为值由关键字本身隐含。例如：`findByActiveTrue()`。
- `GreaterThan` 和 `IsGreaterThan` 表示属性大于参数值。你可以使用 `GreaterThanEqual` 或 `IsGreaterThanEqual` 将参数值包含在边界内。这些关键字的反词是 `LessThan`、`IsLessThan`、`LessThanEqual` 和 `IsLessThanEqual`。
- `In` 表示属性值必须等于指定值中的至少一个。匹配此标准的参数应该是该类型的 `Iterable`。例如：`findByAuthorIn(Iterable<String> authors)`。
- `Null` 和 `IsNull` 表示值应该为空。这些关键字也不需要参数，因为值本身就是它。
- `Near`、`Within` 和 `IsWithin` 是某些 NoSQL 数据库类型的有用关键字，但在 JPA 中没有实际意义。
- `Regex`、`MatchesRegex` 和 `Matches` 表示属性值应匹配在相应方法参数中指定的字符串正则表达式（不使用 `Pattern`）。

### 特殊关键字

- `Distinct`：出现在引导句中（如 `findDistinctBooksByAuthor`），这会触发特殊行为，即在底层查询中启用 distinct 标志。这可能适用也可能不适用，对于 JPA 和 JdbcTemplate 仓库，它等同于在 JPQL 或 SQL 查询中使用 `DISTINCT` 关键字。
- `Top`、`First`：用于限制查询结果数量，如 `findTop10ByLastname` 或 `findFirstByLastname`。

### 排序与分页

你可以在方法签名中添加 `Sort` 或 `Pageable` 参数来实现排序和分页：
- `List<Person> findByLastname(String lastname, Sort sort);`
- `Page<Person> findByLastname(String lastname, Pageable pageable);`

## 提供自定义方法实现

如你所见，查询方法语言非常强大。使用 Spring Data 接口方法可以做的事情并不多。在几乎所有情况下，你都可以创建一个接口，坐下来休息，让 Spring Data 为你完成工作。偶尔，你会遇到 Spring Data 无法处理的情况。一个例子是执行全文搜索，你将在第 23 章中探索它。

另一个例子是用户生成的动态查询。通常，你希望严格限制用户可以在持久化数据上执行的查询。允许对几乎任何属性进行过滤可能会产生灾难性的性能影响。但如果你了解风险并做出相应计划，这种工具对你的用户来说可能非常强大且有用。这也是使用 Spring Data 查询方法无法实现的。

> 注意：尽管 Spring Data 不提供执行动态查询的机制，但 Spring Data JPA 提供了两种使用 JPA criteria API 或 Querydsl 谓词来实现它的专用机制。如果你使用 JPA 仓库，可以使用这些机制之一。如果你使用其他 Spring Data 仓库类型，你可能仍然需要为动态查询创建自己的机制。

无论 Spring Data 自身无法实现什么功能，为 Spring Data 仓库添加自定义行为通常非常简单。你可以根据需要采取两种方法之一或同时采用：自定义单个仓库或自定义所有仓库。

### 自定义单个仓库

自定义单个仓库的第一步是为该自定义项创建一个接口。该接口应与实际的仓库接口分开，并指定为你的仓库具有自定义实现的所有方法（至少一个）。然后，仓库接口应该扩展该自定义接口。

```java
public interface RepositoryCustomization {
    Page<Book> findBooksWithQuery(DynamicQuery query, Pageable p);
    Page<Book> searchBooks(String searchQuery, Pageable p);
}
```

```java
public interface BookRepository
    extends PagingAndSortingRepository<Book, Long>, RepositoryCustomization {
}
```

> 注意：自定义实现类的命名约定为：接口名 + `Impl`。Spring Data 会自动查找该类。

```java
public class BookRepositoryImpl implements RepositoryCustomization {
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

如果你大量使用全文搜索或动态查询，自定义单个仓库可能是常见的。

### 自定义所有仓库

如你所见，自定义单个仓库非常简单。在大多数自定义场景中，你要么自定义少数仓库，要么所有仓库的自定义都不同。在这种情况下，单个自定义是你选择的路线。然而，在极少数情况下，你可能希望为特定类型的仓库提供相同的自定义方法（例如所有的 JPA 仓库）。这种过程要复杂得多。首先，你必须创建一个扩展项目接口的新接口，并指定自定义方法或方法。

```java
@NoRepositoryBean
public interface CustomRepository<T, ID extends Serializable>
    extends JpaRepository<T, ID> {
    void putCustomOperation(T entity);
}
```



注意该接口扩展了 `org.springframework.data.repository.JpaRepository`（其中 `PagingAndSortingRepository` 扩展 `CrudRepository`）。每个 Spring Data 子类型提供一个或多个扩展基础 Spring 接口的接口。以 Spring Data JPA 为例，`CustomRepository` 扩展了 Spring Data 扫描的接口 `JpaRepository`。

你还必须对 `CustomRepository` 注解 `@org.springframework.data.repository.NoRepositoryBean`。由于 `CustomRepository` 自身扩展 `Repository`（通过 `JpaRepository` 扩展 `PagingAndSortingRepository` 扩展 `CrudRepository`），Spring Data JPA 通常会检测到并创建它的实现。你不希望这样——仅仅作为你仓库的基接口。（如果你查看 `CrudRepository`、`PagingAndSortingRepository` 和 `JpaRepository` 的 API 文档，它们也都标记了 `@NoRepository`。）

在指定新接口后，你必须扩展 Spring Data JPA 项目提供的基类。

```java
public class CustomRepositoryImpl<T, ID extends Serializable>
    extends SimpleJpaRepository<T, ID>
    implements CustomRepository<T, ID> {

    private Class<T> domainClass;
    private EntityManager entityManager;

    public CustomRepositoryImpl(Class<T> domainClass, EntityManager entityManager) {
        super(domainClass, entityManager);
        this.domainClass = domainClass;
        this.entityManager = entityManager;
    }

    public CustomRepositoryImpl(Information<T, ?> information, EntityManager entityManager) {
        super(information, entityManager);
        this.domainClass = (Class<T>) information.getJavaType();
    }

}
```

# 理解 Spring Data 的统一数据访问 | 645

```java
this.entityManager = entityManager;
```

```java
}
```

```java
public void customOperation(T) {
    // 实现自定义操作的代码
}
```

现在到了最具挑战性的部分，即为你的所有仓库提供自定义行为。Spring Data 不会自动将你的 `CustomRepositoryImpl` 作为它的仓库。你必须创建一个工厂 bean 来执行此任务，并用你的工厂 bean 替换默认的工厂 bean。

```java
public class CustomRepositoryFactoryBean<R extends JpaRepository<T, ID>, T, ID extends Serializable>
    extends JpaRepositoryFactoryBean<R, T, ID>
```

```java
@Override
protected RepositoryFactorySupport createRepositoryFactory(EntityManager em) {
    return new CustomRepositoryFactory<T, ID>(e);
}
```

```java
private static class CustomRepositoryFactory<T, ID extends Serializable> {
    private EntityManager entityManager;

    public CustomRepositoryFactory(EntityManager entityManager) {
        super(entityManager);
        this.entityManager = entityManager;
    }
```

```java
@Override
@SuppressWarnings("unchecked")
protected Object getTargetRepository(RepositoryMetadata metadata) {
    return new CustomRepositoryImpl<T, ID>((Class<T>) metadata.getDomainType(), this.entityManager);
}
```

```java
@Override
protected Class<?> getRepositoryBaseClass(RepositoryMetadata metadata) {
    return CustomRepositoryImpl.class;
}
```

# 646 | 第 22 章 使用 Spring Data JPA 消除样板代码仓库

就像 `LocalContainerEntityManagerBean` 充当创建 `EntityManagerFactory` 的工厂一样，`CustomRepositoryFactory` 也充当创建 `CustomRepositoryFactory` 的工厂。`CustomRepositoryFactory` 存储 `EntityManager` 并响应对新自定义实例的调用。由于 `CustomRepositoryImpl` 在其代码中通过扩展 `SimpleJpaRepository` 已经实现了 `CRUDRepository`、`PagingAndSortingRepository`、`JpaRepository` 和 `CustomRepository` 中指定的所有基础方法，Spring Data JPA 只需要获取 `CustomRepositoryImpl`，并为任何扩展接口（如 `BookRepository` 或 `PersonRepository`）中指定的方法动态添加实现。

为你的所有 JPA 实体添加此自定义行为的最后一步是配置 Spring Data JPA 使用 `CustomRepositoryBean` 而不是默认的 `JpaRepositoryBean`。你将在下一节中学习如何这样做。你可能永远不需要为给特定数据库的所有仓库添加相同的自定义方法，本书没有提供可运行的示例；但是，你可以从所示的示例代码创建一个。在某些情况下，像定制化单个仓库那样创建一个定制化接口和实现可能更简单，然后将其应用到你的所有仓库中。

# 配置和创建 Spring Data JPA 仓库

在上一节中，你探索了使用 Spring Data 编写仓库接口，并学习了它如何完全取代你手写的接口。虽然文中偶尔提到了 Spring Data JPA（在添加自定义方法实现时），但你读到的所有关于 Spring Data 的通用内容，都可以将你所学的技巧不仅应用于 Spring Data JPA，还适用于许多支持不同数据库类型的其他 Spring Data 项目。你将转换思路，专门学习 Spring Data JPA、如何使用它以及如何配置它。在上一章中，你学习了如何在 Spring Framework 中配置 JPA。如果你没有读过上一章，请现在回去补上。本章的介绍在这一节中被大量用于设置 Spring Data JPA。

配置 Spring Data JPA 并为它创建要实现的仓库是非常简单的任务。使用任何 Spring Data 项目的优之处在于，除非你需要实现自定义行为，否则并没有列表供你执行。在这一节中，你探索了如何使用从 wrox.com 下载站点提供的 `Spring-Data-Jpa` 项目来设置并运行 Spring Data JPA。它是基于你在上一章中工作的 `Spring-Jpa` 项目。它的实体是相同的，并使用现有数据库、表结构和 Tomcat DataSource 资源。

# 启用仓库自动生成

配置 Spring Data JPA 并不费精力。你只需要考虑少数选项。与 Spring Framework 一样，你可以采取两种不同的配置方法：XML 或 Java。本节将介绍这两种，但 `Spring-Data-Jpa` 项目中仅演示了 Java 配置。即使你不打算使用它，也要阅读关于 XML 命名空间的配置，因为它引入了一些对 Java 配置重要的概念。

# 使用 XML 命名空间配置

在配置 Spring Data JPA 时你使用两个 XML 命名空间。第一个 `http://www.springframework.org/schema/data/repository` 是 Spring Data Commons 的核心命名空间（在本书中，命名空间前缀为 `data`）。所有的 Spring Data 项目都以此方式命名空间来配置仓库数据。在某些情况下，Spring Data 项目（如 Spring Data JPA）可能会扩展 Spring Data Commons 命名空间中定义的某些类型以创建额外的元素。这正是 Spring Data JPA 命名空间 `http://www.springframework.org/schema/data/jpa`（在书中带有 `data-jpa` 命名空间前缀）的情况。

Spring Data 能够通过它生成的仓库填充你的数据库。它使用 XML 或 JSON 文件来实现。本书不会详细介绍此功能的细节，你应该只在开发环境中使用它，在生产系统中可能是非常危险的。但是，要配置此功能，可以使用以下 XML 元素之一，它们都来自 Spring Data Commons 命名空间。

- `<jackson-population>` 定义了一个通过 Jackson 库使用 JSON 文件填充实体的 bean。
- `<json-population>` 定义了一个使用 JSON 文件填充实体的 bean。
- `<custom-population>` 定义了一个允许你自定义填充过程的 bean。

## 配置和创建 Spring Data JPA 存储库

扩展 Spring Data JPA 的 `JpaRepository` 和 Spring Data MongoDB 的 `MongoRepository` 的接口。（你也可以将这些存储库放在不同的包中。）

```xml
<data-jpa:repositories base-package="com.sample">
    <include-filter type="assignable"
        expression="org.springframework.data.jpa.repository.JpaRepository" />
</data-jpa:repositories>
```

```xml
<data-mongo:repositories base-package="com.sample">
    <include-filter type="assignable"
        expression="org.springframework.data.mongodb.repository.MongoRepository" />
</data-mongo:repositories>
```

Spring Data JPA 定义了一个额外的 `entity-manager-ref`，以便你可以指定 Spring Data JPA 在 JPA 操作中使用的 `EntityManagerFactory`。由于你通常配置了 `LocalContainerFactoryBean`，你应该直接引用该 bean。

在使用 Spring Data JPA 时，可以使用 `<data-jpa:auditing>` 元素配置审计。通过审计，Spring Data 可以在每次保存实体时设置实体属性，例如创建者或日期和时间值。其他 Spring Data 项目也拥有此元素（但带有不同的命名空间缀）。所有支持此元素的项目都有以下属性：

- `auditor-aware-ref` — 这是一个 `org.springframework.data.domain.AuditorAware<>` 的 bean，用于确定当前已身份的用户或 `Principal`。如果没有此引用，审计将不会记录修改记录的用户。
- `set-dates` — 这是一个布尔属性，指示在创建或保存实体时是否应该设置创建和修改日期。默认值为 `true`。
- `date-time-provider-ref` — 使用此属性指定 `org.springframework.data.DateTimeProvider` 实现的名称，用于确定用于审计的日期和时间。默认值是 `org.springframework.data.auditing.CurrentDateTimeProvider`。对于 Spring Data 1.7，使用提供者需要你的类路径中包含 Java Time。从 1.7 版本开始，`DateTimeProvider` 现在基于 `Calendar`，不再需要 Joda Time。
- `modify-on-creation` — 此属性默认值为 `true`，表示你是否也想在创建时设置修改日期。如果设为 `false`，则只在更新时保存修改日期。

这看起来可能很多，但在典型的 Spring Data JPA 配置中，可能像这样：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:data-jpa="http://www.springframework.org/schema/data/jpa"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-4.0.xsd
    http://www.springframework.org/schema/data/jpa
    http://www.springframework.org/schema/data/jpa/spring-data-jpa-1.3.xsd">
    <data-jpa:repositories base-package="com.sample"
        transaction-manager-ref="jpaTransactionManager"
        entity-manager-factory-ref="entityManagerBean"/>
</beans>
```

如果你正在配置自定义扫描器、自动填充和不同的查询策略，你的配置可能更像这样：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:data="http://www.springframework.org/schema/data/repository"
    xmlns:data-jpa="http://www.springframework.org/schema/data/jpa"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-4.0.xsd
    http://www.springframework.org/schema/data/repository
    http://www.springframework.org/schema/data/repository/spring-data-repository-1.6.xsd
    data-jpa:schemaLocation="http://www.springframework.org/schema/data/jpa
    http://www.springframework.org/schema/data/jpa/spring-data-jpa-1.3.xsd">
    <data-jpa:repositories base-package="com.sample"
        transaction-manager-ref="jpaTransactionManager"



```xml
entity-manager-factory-ref="entityManagerFactoryBean"
query-lookup-strategy="create">
    <include-entity-filter type="annotation" expression="com.sample.MyRepository" />
</data-jpa:repositories>
<data-jpa:auditing auditor-ref="com.sample.AuditorImpl" />
</beans>
```

## 使用 Java 配置

`@org.springframework.data.jpa.repository.config.EnableJpaRepositories` 注解替换了 `data-jpa:repositories` 元素。它注册了必要的 bean，并包含了与 XML 元素相同的配置选项。

- `basePackages` 和 `basePackageClasses` 替换了属性 `base-package`。
- `namedQueriesLocation` 替换了属性 `named-queries-location`。
- `repositoryImplementationPostfix` 替换了 `repository-impl-postfix`。

# 配置并创建 Spring Data JPA 仓库

```java
public class WebServletContextConfiguration extends WebMvcConfigurer {
    ...
}
```

使用 `@EnableSpringDataSupport` 注册的 Bean 包含许多初始化为默认值的设置。这些设置包括参数名称、最大页大小，以及当请求参数缺失时默认的 `Pageable` 和 `Sort` 值。这些默认值对你来说可能是可以的，但如果不是，你只需要省略 `@EnableSpringDataWeb` 注解并手动注册这些 Bean。在 `WebServletContextConfiguration` 中演示了这一点。

```java
@Configuration
@EnableWebMvc
@ComponentScan(
    basePackages = "com.wrox.site",
    useDefaultFilters = false,
    includeFilters = {
        @ComponentScan.Filter({RestEndpoint.class, RestEndpointAdvice.class})
    }
)
```

```java
public class HttpServletContextConfiguration extends WebMvcConfigurer {
    private static final Logger log = LogManager.getLogger(log);
    @Inject ApplicationContext applicationContext;

    @Override
    public void addArgumentResolvers(List<HandlerMethodArgumentResolver> resolvers) {
        Sort defaultSort = new Sort(Sort.Order(Sort.Direction.ASC, "id"));
        Pageable defaultPageable = new PageRequest(0, 20, defaultSort);
        SortHandlerArgumentResolver sortResolver = new SortHandlerArgumentResolver();
        // sortParameter 默认为 "sort"
        sortResolver.setSortParameter("sort");
        sortResolver.setFallbackResolver(defaultSort);
        PageableHandlerArgumentResolver pageResolver = new PageableHandlerArgumentResolver(sortResolver);
        pageResolver.setOneIndexedParameters(true); // page 从 1 开始，而不是 0
        // pageProperty 默认为 "page"，sizeProperty 默认为 "size"
        // 以下用于用于 setPageProperty("paging.page") 和
        // setSizeProperty("paging.size");
        pageResolver.setPrefix("paging.");
        pageResolver.setFallbackPageable(defaultPageable);
        resolvers.add(sortResolver);
        resolvers.add(pageResolver);
    }
}
```

```java
@Override
public void addFormatters(FormatterRegistry registry) {
    if (!(registry instanceof FormattingConversionService)) {
        log.warn("无法注册 Spring Data JPA 器.");
        return;
    }
    // DomainClassConverter 将自身注册到注册表中
    DomainClassConverter<FormattingConversionService> converter =
        new DomainClassConverter((FormattingConversionService) registry);
    converter.setApplicationContext(this.applicationContext);
}
```

# 编写和使用 Spring Data JPA 接口

除非你有几十个或数百个仓库，否则在创建仓库时你可能不需要更多的 Spring Data JPA 配置。Spring-Data-JPA 项目中新的 `AuthorRepository`、`BookRepository` 和 `PublisherRepository` 几乎是空的。上一章 Spring-JPA 项目中的 `GenericRepository`、`GenericBaseRepository`、`GenericJpaRepository`、`DefaultAuthorRepository`、`DefaultBookRepository` 和 `DefaultPublisherRepository` 已经消失且不再需要了。想想你删除了所有的代码吧！

```java
public interface AuthorRepository extends CrudRepository<Author, Long> {
}
public interface BookRepository extends CrudRepository<Book, Long> {
    Book getByIsbn(String isbn);
}
public interface PublisherRepository extends CrudRepository<Publisher, Long> {
}
```

使用这些接口只需要对 `BookManager` 服务进行细小的更改。`saveAuthor(Author)`、`saveBook()` 和 `savePublisher()` 以前在 ID 小于 1 时调用 `add()`，否则调用 `update()`，现在简单地调用相应仓库的 `save()` 方法。`getAuthors()`、`getBooks()` 和 `getPublishers()` 方法以前使用 `getAll()` 仓库方法，现在使用 `findAll()` 仓库方法。

```java
@Override
@Transactional
public List<Author> getAuthors() {
    return this.toList(this.authorRepository.findAll());
}
```

# 配置并创建 Spring Data JPA 仓库

```java
@Override
@Transactional
public void saveAuthor(Author author) {
    this.authorRepository.save(author);
}
```

你可能会奇怪为什么仓库返回的是 `Iterable<T>` 而不是 `List<T>`，为什么你必须额外花一步迭代 `Iterable<T>` 将其转换为 `List<T>`。ORM 通常直接使用 JDBC `ResultSet` 来支持它们创建的实体列表。这提高了性能，并允许代码在数据库仍在运行时开始执行。然而，当 Spring Data 返回 `Iterable` 时，如果你需要一个 `List`，就必须进行转换。

# 转换现有的仓库

当然，除非你有几十个或数百个仓库，否则在创建仓库时，你可能需要更多的 Spring Data JPA 配置。事实上，你正在构建的 Customer Support 应用可以利用 Spring Data 和 Spring Data JPA。实际上，你可以显著减少应用中的代码量并使应用程序更加简单。

在本节中，你可以参考 wrox.com 代码网站上的 Customer-Support-v1 项目。它使用了你在上一章创建的 `@EnableRepositories` 配置。然而，它在 `WebServletConfiguration` 中没有 `@EnableSpringDataWeb`。相反，它手动创建了 `SortHandlerArgumentResolver` 和 `PageableArgumentResolver` 以应用合理的默认值，就像 `RestServletConfiguration` 一样。

## 转换仓库

就像 Spring-Data-Jpa 项目一样，你会发现：

- `GenericRepository`、`GenericBaseRepository` 和 `GenericJpaRepository` 不再存在于 Customer-Support-v1 项目中。
- `DefaultAttachmentRepository`、`DefaultTicketRepository` 和 `UserRepository` 也消失了。
- `AttachmentRepository`、`TicketRepository` 和 `UserRepository` 现在继承 `CrudRepository` 并移动到了 `com.wrox.site` 包。

你甚至不需要为 `AttachmentRepository` 和 `UserRepository` 添加额外的方法；它们已经与 Spring Data 查询方法算法兼容。

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

这些仓库的更改需要对使用它们的服务进行一些微调。例如，`DefaultAuthenticationService` 中的 `saveUser` 方法需要使用仓库的新方法，而不是 `add` 和 `update`。

```java
@Override
@Transactional
public void saveUser(UserPrincipal principal, String newPassword) {
```

### 重构客户支持应用程序

```java
if (newPassword != null && newPassword.length() > 0) {
```



```java
String salt = BCrypt.gensalt(HASHING_ROUNDS, RANDOM);

principal.setPassword(BCrypt.hashpw(newPassword, salt).getBytes());

}

this.repository.save(principal);

```

在 `DefaultTicketService` 中，使用了以下更改：

- `getAll` 变为 `findAll`。
- `get` 变为 `findOne`。
- `add` 和 `update` 变为 `save`。
- `deleteById` 变为 `delete`。

这些更改很小，但贯穿整个类，因此代码未在此包含。你会发现 Customer-Support-v16 项目中的更改并没有利用 Spring Data 提供的分页功能。更新现有代码以实现分页是留给你完成的任务。在本节稍后，你将使用评论分页作为示例。

> 注意：在之前的 `GenericRepository` 接口中，两个类型参数都扩展了 `Serializable`，通过拥有 `delete(E)` 和 `delete(I)` 方法会导致歧义且无法编译。这就是为什么 `GenericRepository` 定义了 `delete(E)` 和 `deleteById(I)` 方法。在 `CrRepository` 中，只有 ID 类型扩展了 `Serializable`，因此可以以此方式重载 `delete` 方法。因此，`CrRepository` 的方法是 `delete(T)` 和 `delete(ID)`。

# 为支持工单添加评论

客户支持系统的主要功能之一是评论。如果没有人评论，良好的报告有什么意义呢？使用 JPA、Spring Data 和 Spring Data JPA，为客户支持应用程序中添加评论非常简单。你需要更改业务逻辑和用户界面，而持久层将由系统处理。你首先创建评论实体和仓库，然后更新服务来操作评论。完成后，你需要在用户界面中添加评论。

# 创建实体和仓库

你可以从创建一个 `TicketComment` POJO 开始。当然，它看起来和 ticket 非常相似，但缺少主题。

```java
public class TicketComment {

    private long id;

    @NotBlank(message = "validate.ticket.comment.customerName")

    private String customerName = "{validate.ticket.comment.body}";

    private String body;

    private Instant dateCreated;

    // 省略变异器和访问器

}
```

由于你无法持久化带有 `Instant` 属性的实体，你需要创建一个单独的 `TicketComment` 实体。`TicketComment` 可充 DTO。

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

你还需要一个新的 MySQL 表来持久化评论。请确保在你的客户支持数据库上运行以下创建语句（你也可以在 `create.sql` 中找到它）。

```sql
CREATE TABLE TicketComment (

CommentId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,

TicketId BIGINT UNSIGNED NOT NULL,

UserId BIGINT UNSIGNED NOT NULL,

Body TEXT,

DateCreated TIMESTAMP(6) NULL,

CONSTRAINT TicketCommentUserId FOREIGN KEY (UserId)
REFERENCES UserPrincipal(UserId) ON DELETE CASCADE

CONSTRAINT TicketCommentId FOREIGN KEY (TicketId)
REFERENCES Ticket (TicketId) ON DELETE CASCADE

Engine = InnoDB;

```

最后，创建 `TicketCommentRepository` 是简单的一步，因为你只需要定义接口并让 Spring Data 处理剩下的。

```java
public interface TicketCommentRepository
extends CrudRepository<TicketCommentEntity, Long> {

    Page<TicketCommentEntity> getByTicketId(long ticketId, Pageable page);

}
```

# 更新服务

服务层也应该更新。你需要获取工单评论、保存评论和删除评论的方法。添加到 `TicketService` 接口的三个方法确保了这些评论与工单是关联的。

```java
Page<TicketComment> getComments(@Page(value = 1) long ticketId, Pageable page);

void save(@Valid TicketComment comment, @Page(value = 1) long ticketId);

void deleteComment(long id);
```

`DefaultTicketService` 中 `deleteComment` 的实现相当标准，模仿了 ticket 的对应方法。`getComments` 则很有趣，因为你必须将仓库返回的 `Page<TicketCommentEntity>` 转换为 `Page<TicketComment>`。

```java
@Override
@Transactional
public Page<TicketComment> getComments(long ticketId, Pageable page) {

    List<TicketComment> comments = new ArrayList<>();

    Page<TicketCommentEntity> entities = commentRepository.getByTicketId(ticketId, page);

    entities.forEach(e -> comments.add(convert(e)));

    return new PageImpl<>(comments, page, entities.getTotalElements());

}

private TicketComment convert(TicketCommentEntity entity) {

    TicketComment comment = new TicketComment();

    comment.setId(entity.getId());

    comment.setCustomerName(userRepository.findOne(entity.getUserId()).getUsername());

    comment.setBody(entity.getBody());

    comment.setCreated(Instant.ofEpochMilli(entity.getCreated().getTime()));

    return comment;

}
```

# 从用户界面评论

更新用户界面是为客户支持应用程序添加评论的最后一步。`TicketController` 的更改很小。首先，`view` 方法需要一个 Spring Data 自动解析的 `Pageable` 参数，新增了两行：

```java
model.put("comments", ticketService.getComments(ticketId, page));

model.put("commentForm", new CommentForm());
```

控制器还需要一个添加新评论的方法。评论表单位于查看页面，以便用户在评论时查看工单和其他评论。因此，如果发生验证错误，此方法将交给 `view` 方法处理。

```java
@RequestMapping(value = "/ticketId", method = RequestMethod.POST)
public ModelAndView comment(Principal principal, @Valid CommentForm form, Errors errors, Map<String, Object> model, Pageable page, @PathVariable("ticketId") long ticketId) {

    Ticket ticket = ticketService.getTicket(ticketId);

    if (ticket == null) {

        return new redirectModelAndView();

    }

    if (errors.hasErrors()) {

        return this.view(model, page, ticketId);

    }

    TicketComment comment = new TicketComment();

    comment.setCustomerName(principal.getName());

    comment.setBody(form.getBody());

    try {

        ticketService.save(comment, ticketId);

    } catch (ConstraintViolationException e) {

        model.put("validationErrors", e.getConstraintViolations());

        return this.view(model, page, ticketId);

    }

    return new ModelAndView(new RedirectView("/ticket/view/" + ticketId), true, false);

}
```

显示和添加评论的 JSP 代码很长，大部分用于分页。你可以在 `WEB-INF/jsp/view/ticket.jsp` 中查看代码。21行之后都在显示和添加评论。在阅读代码时，你可能会发现对分页链接可以做得更多（例如第一页和最后一页链接，以及当页面很多时不在每一页都显示评论）。你应该很快意识到，在需要分页的地方复制代码是不理想的。自定义 JSP 标签是解决此问题的办法，创建此标签是留给你完成的任务。

你现在准备好使用以下步骤编辑客户支持应用程序了：

- 如果你没有在第21章中测试应用程序，请确保运行了 `create.sql` 脚本并将 DataSource 资源添加到 Tomcat 的 `context.xml` 文件中。如果已经，请确保向数据库添加了 Comment 表。
- 编译项目并从 IDE 启动 Tomcat。
- 在浏览器中访问 `http://localhost:8080/support/`，登录并对你在第21章创建的工单进行评论。
- 如果喜欢，可以创建工单，并尝试以不同用户的身份发表不同的评论。
- 为工单添加超过10条评论，以便测试分页。使用 Spring Data JPA，你轻松地重构了支持系统添加了评论。

你可能注意到 SOAP 和 RESTful Web 服务没有更新以处理创建和返回评论。这也是留给你完成的任务。

### 总结

在本章中，你探索了 Spring Data 和 Spring Data JPA 如何消除编写仓库代码的枯燥重复任务。你学习了如何创建 Spring Data 仓库接口和编写 Spring Data 查询方法，还学习了 Spring Data 如何动态创建这些接口的实现。你被简要介绍了如何向 Spring Data 仓库添加自定义行为，你将在下一章中进一步探索。最后，得益于 Spring Data，你以最小的精力为客户支持应用程序中的工单添加了评论，并演示了在没有 Spring Data 的 `Pageable` 和 `Sort` 对象的情况下进行分页是多么简单。

在下一章中，你将学习各种数据搜索方法，以及如何将原生 MySQL 全文检索和通用 Apache Lucene 全文检索集成到你的 JPA 仓库中。

# 使用 JPA 和 Hibernate Search 进行数据搜索

# 本章内容

- 搜索基础
- 如何使用高级准则定位对象
- 在 JPA 中使用全文索引
- 使用 Apache Lucene 和 Hibernate Search 为数据建立索引

# 本章 WROX.COM 代码下载

你可以在 http://www.wrox.com/go/projectjavaforwebapps 的 "Download Code" 标签页中找到本章的 wrox.com 代码下载。本章的代码分为以下几个主要示例：

- Advanced-Criteria
- Customer-Support-v17 项目
- Search-Engine 项目

# 本章的新增 MAVEN 依赖

除了在前几个章节中引入的 Maven 依赖外，你还需要在涵盖 Apache Lucene、Hibernate Search 和 Search-Engine 项目的章节中使用以下 Maven 依赖。

```xml
<dependency>
  <groupId>org.hibernate</groupId>
  <artifactId>hibernate-search-orm</artifactId>
  <version>4.5.0.Final</version>
  <scope>compile</scope>
</dependency>
```



### 搜索简介

搜索数据有许多不同的形式。你可能使用如 `grep`、`find`、Agent Rack、Spotlight 或 Windows 等工具来在硬盘上搜索文件。你可以寻找匹配的文件名或匹配的文件内容。也许你最熟悉的搜索方式是打开网络浏览器，使用诸如 Google 这样流行的搜索工具来搜索互联网上的内容。或者你可能有一个 Gmail 账号，使用 Gmail 页面顶部的搜索栏查找电子邮件并根据搜索结果创建过滤器。

如果你喜欢网购，你会有自己喜欢的商店，而且很可能使用搜索工具来寻找你感兴趣的产品。作为开发者，你无疑在 IDE 中拥有一个搜索工具，用于在项目或代码文件中查找特定的文件或类。你可能用过 GitHub 在开源仓库中搜索代码，然后使用浏览器的搜索工具定位页面上的特定关键词。也许你还拥有社交网络账号，并使用搜索工具寻找你认识的人或你感兴趣的话题。当然，你可能不会忘记这种久经考验（尽管准确性最低）的传统搜索方法：手动翻阅文件柜里的纸质文档或图书馆里的微缩胶来寻找你需要的数据。

在所有这些不同的搜索方法中，出现了两个不可争议的事实：索引搜索比非索引搜索更快，而创建索引会让内容处理花费更长的时间。

> **等等 —— INDEX 还是 ICICES？**
> 语言与计算机术语的交汇经常导致一些有趣的争议。例如，你使用的是 computer（计算机）还是 mice（鼠标）？单词 "index" 的复数形式传统上是 "indexes"，但近年来发生了一些变化。有些人学过这样一种说法：“Books index; has indices.” 由于数学索引在计算机科学中也有重要含义，因此许多人在指代技术性但非数学性的索引复数形式时，更倾向于使用 "indexes"。本书也使用 "indexes" 这个词。

### 理解索引的重要性

以文件柜为例。你拿到文档后，可以把它们直接扔进文件柜里的第一个可用位置。这非常快，而且在抽屉关闭时，看起来非常有条理。但在拿到它六个月后要找回那一份文档，将证明是一项极其耗时的任务。

或者，你可以在文件柜中创建文件夹，将所有的账单分类在一起——所有的保险文件放在一起，所有关于特定主题的研究放在一起，等等。突然之间，寻找那张账单变得杂乱无章。与其翻遍整个文件柜（或者糟糕是多个文件柜）直到找到账单，你可以打开已知它所在的某个抽屉，伸进“账单”文件夹，在数百份简单的文档中筛选，直到找到正确的那一份。缺点是，将账单插入文件柜花费的时间更长。你不能只是打开抽屉扔进去就走人。你必须为文档类型找到正确的抽屉，定位合适的文件夹，如果不存在则创建一个，然后插入文档。

对文档建立索引还涉及定期的重新组织。如果某个抽屉或文件夹太满了，就将其分成更小、更细的类别，并对部分或全部文档进行重新分类。任何人都应该清楚，保持文档整洁不是免费的。它并不便宜，并且会消耗大量时间。这是包含数字信息的索引花费的时间。你必须一直问自己的问题是这个代价值得吗？

对比使用 `grep` 搜索文档与使用 Mac OS 的 Spotlight 功能。如果你得到一个内容较少的文件夹，它返回结果可能会很快。那么对于 Spotlight 来说，一个包含数百个文件的整个硬盘呢？`grep` 可能需要几分钟或几小时才能返回结果，而 Spotlight 仅需几秒。区别在于方法。`grep` 必须打开并读取它搜索的每一份文档；而 Spotlight 维护着文件内容的索引并使用该索引。成本在于性能：每当你保存一个文件时，Spotlight 就会更新索引。每隔几天或几小时（取决于电脑的活跃程度），Spotlight 就会全力运行 CPU 来重新组织其索引。大部分时候你察觉不到，但有时你的机器会短暂变慢。这换取搜索速度的巨大提升值得吗？对于大多数用户来说，答案是肯定的。

索引是一种让查找数据更容易的结构。索引有多种形式，取决于它们索引的是什么。许多关系型数据库使用 B 树索引，它们能很好地存储有序数据。文本密集型数据存储器则需要根据内容与搜索查询的匹配程度进行搜索。

### 使用高级标准定位对象

![](img/4677f981a0e1067137bb55a122f8498d_702_0.png)

图 23-1

### 创建复杂的标准查询

继续图 23-1 中的搜索示例，假设你的应用具有以下 `Person` 实体，并带有相应的修改器（mutator）和访问器（accessor）。你可以参考 wrox.com 代码库中提供的 Advanced-Criteria 项目中的本章节。

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

### 在 API 中表示搜索标准

你不能使用 JPA Criteria API 来创建搜索标准并将其传递给应用的每一层。该 API 需要一个 `EntityManager` 实例以及对领域层的访问，而领域层不应该是可以从用户界面层访问的。你需要某种方法将搜索查询从用户界面传递到仓库。由于这可能不是你想要以这种方式搜索的唯一实体，你需要在整个应用程序中复用这种机制，因此它不能是特定于 `Person` 的。

```java
public class Criterion {
    private final String propertyName;
    private final Operator operator;
    private final Object compareTo;

    public Criterion(String propertyName, Operator operator, Object compareTo) {
        ...
    }

    // accessors

    public static enum Operator {
        EQ, NEQ, LT, LTE, GT, GTE, LIKE, NOT_LIKE, IN, NOT_IN, NULL, NOT_NULL
    }
}

public interface SearchCriteria extends List<Criterion> {}
```

该 API 非常简单：搜索涉及包含一个或多个 `Criterion` 实例的列表。每个 `Criterion` 代表实体上的属性与值之间的比较，使用 `Operator` 枚举来确定如何执行该操作。现在，它仅允许对标准进行 AND 连接，因为你这种搜索只需要这些，且实现起来更简单。如果你想添加 AND/OR 切换或添加 AND/OR 分组，你可以在 `SearchCriteria` 接口中创建额外功能。（这是一个你可以独立完成的任务。）

### 添加自定义搜索方法

你的仓库需要一个可以接受 `SearchCriteria` 参数的自定义搜索方法。它还应该接受一个 `Pageable` 并返回一个 `Page<Person>`，以便分页检索搜索结果。然而，你不想为每个仓库重写此方法，因此你需要将其泛型化。使用我们在第 21 章中使用过的一些巧妙技巧来获取泛型类的类型参数。

首先，创建一个接口来反映你希望可搜索仓库执行的操作。你的 `PersonRepository` 接口应该扩展此接口，以表示人员是可搜索的。

```java
public interface SearchableRepository<T> {
    Page<T> search(SearchCriteria criteria, Pageable pageable);
}
```

```java
public interface PersonRepository extends JpaRepository<Person, Long>, SearchableRepository<Person> {}
```

所有可搜索仓库都共享你创建的搜索方法的通用实现，因此为你的自定义仓库实现一个通用的基类是有意义的。搜索中的代码需要知道 T 的 `Class`，但你可能还有其他需要此信息的通用基类。因此，创建一个抽象类型参数的基类和一个用于搜索的基类。

```java
abstract class AbstractDomainClassAwareRepository<T> {
    protected final Class<T> domainClass;

    @SuppressWarnings("unchecked")
    protected AbstractDomainClassAwareRepository() {
        Type genericSuperclass = this.getClass().getSuperclass();
        while (!(genericSuperclass instanceof ParameterizedType)) {
            genericSuperclass = genericSuperclass.getGenericSuperclass();
        }
        ParameterizedType type = (ParameterizedType) genericSuperclass;
        Type[] arguments = type.getActualTypeArguments();
        domainClass = (Class<T>) arguments[0];
    }
}
```

```java
abstract class AbstractSearchableJpaRepository<T> extends AbstractDomainClassAwareRepository<T> implements SearchableRepository<T> {
    @PersistenceContext
    protected EntityManager entityManager;

    @Override
    public Page<T> search(SearchCriteria criteria, Pageable pageable) {
        return null;
    }
}
```

### 第 23 章 使用 JPA 检索数据

现在，`search` 方法只是存根（stubbed），但稍后我们会填充它。为了解决这个问题，你需要 `PersonImpl` 类。

### 从输入创建查询

当你开始考虑所有选项时，`search` 方法需要完成几件事：

- 将 `SearchCriteria` 转换为 `CriteriaQuery` 以统计记录数量。
- 将 `SearchCriteria` 转换为 `CriteriaQuery` 以检索实体。
- 将 `Pageable` 参数应用到查询中。
- 将结果转换为 `Page<T>`。
- 使用 `pageable` 信息对结果进行排序。

然而，如果此方法继续这样做，你会很快意识到这有多复杂。因为你必须转换 `SearchCriteria`，而不是使用面向对象的方法。由于 `Operator` 枚举自然具有多态性，为什么要执行如此复杂的逻辑？

从通用意义上说（在接口的情况下），谓词可以使用 `Criterion`、`Root` 和 `CriteriaBuilder` 评估的布尔表达式。`Operator` 枚举定义了一个抽象的 `toPredicate` 方法，并在每个常量中实现。

### 列表 23-1：Criterion.java

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
                return b.lessThan((Comparable) r.get(c.getProperty()), (Comparable) c.compareToTo());
            }
        },
        LTE {
            @Override
            @SuppressWarnings("unchecked")
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.lessThanOrEqualTo((Comparable) r.get(c.getProperty()), (Comparable) c.compareToTo());
            }
        },
        GT {
            @Override
            @SuppressWarnings("unchecked")
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.greaterThan((Comparable) r.get(c.getProperty()), (Comparable) c.compareToTo());
            }
        },
        GTE {
            @Override
            @SuppressWarnings("unchecked")
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.greaterThanOrEqualTo((Comparable) r.get(c.getProperty()), (Comparable) c.compareToTo());
            }
        },
        LIKE {
            @Override
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.like(r.get(c.getProperty()), (String) c.compareToTo());
            }
        },
        NOT_LIKE {
            @Override
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return b.notLike(r.get(c.getProperty()), (String) c.compareToTo());
            }
        },
        IN {
            @Override
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return r.get(c.getProperty()).in((Collection<?>) c.compareToTo());
            }
        },
        NOT_IN {
            @Override
            public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {
                return !r.get(c.getProperty()).in((Collection<?>) c.compareToTo());
            }
        }
    }
}
```



NULL {

    @Override

    public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {

        return b.isNull(r.get(c.getProperty()));

    }

},

NOT_NULL {

    @Override

    public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b) {

        return b.isNotNull(r.get(c.getProperty()));

    }

}

}

}

```

```java

@Override

public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b)

{

    return b.like(

        r.get(c.getPropertyName()), getString(c)

    );

}, NOT_LIKE {

    @Override

    public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b)

    {

        return b.notLike(

            r.get(c.getPropertyName()), getString(c)

        );

    }

}, IN {

    @Override

    public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b)

    {

        Object o = c.compareToTo();

        if(o == null)

            return r.get(c.getPropertyName()).in();

        if(o instanceof Collection)

            return r.get(c.getPropertyName()).in((Collection) o);

        throw new IllegalArgumentException(c.getPropertyName());

    }

}, NOT_IN {

    @Override

    public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b)

    {

        Object o = c.compareToTo();

        if (o == null)

            return b.not(r.get(c.getPropertyName()).in());

        if(o instanceof Collection)

            return b.not(r.get(c.getPropertyName()).in((Collection) o));

        throw new IllegalArgumentException(c.getPropertyName());

    }

}, NULL {

    @Override

    public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b)

    {

        return r.get(c.getPropertyName()).isNull();

    }

}, NOT_NULL {

    @Override

    public Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b)

    {

        return r.get(c.getPropertyName()).isNotNull();

    }

}

}

public abstract Predicate toPredicate(Criterion c, Root<?> r, CriteriaBuilder b);

@SuppressWarnings("unchecked")

private static Comparable<?> getComparable(Criterion c) {

    Object o = c.compareToTo();

    if (o != null && !(o instanceof Comparable))

        throw new IllegalArgumentException(c.getPropertyName());

    return (Comparable<?>)o;

}

private static String getString(Criterion c) {

    if (!(c.compareTo() instanceof String))

        throw new IllegalArgumentException(c.getPropertyName());

    return (String)c.compareTo();

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

    CriteriaQuery<T> pageQuery = builder.createQuery(criteria.domainClass);

    Root<T> pageRoot = pageQuery.from(criteria.domainClass);

    List<T> list = this.entityManager.createQuery(

        pageQuery.select(pageRoot)

        .where(toPredicate(criteria, pageRoot, builder))

        .orderBy(toOrder(pageable.getSort(), pageRoot))

    ).setFirstResult(pageable.getOffset())

    .setMaxResults(pageable.getSize())

    .getResultList();

    return new PageImpl<>(new ArrayList<>(list), pageable, total);

}

private static Predicate[] toPredicate(SearchCriteria criteria, Root<?> root, CriteriaBuilder builder) {

    Predicate[] predicates = new Predicate[criteria.size()];

    int i = 0;

    for (Criterion c : criteria) {

        predicates[i++] = c.getOperator().toPredicate(c, root, builder);

    }

    return predicates;

}

```

这段代码执行了之前列举的五个步骤。`toOrders` 方法的调用是来自 `org.springframework.data.jpa.query.QueryUtils` 的静态导入，它将 Spring Sort 转换为 JPA 排序指令。`search` 方法返回一个包含 `Pageable` 信息和总记录数的新的 `org.springframework.data.domain.PageImpl`。

```java

builder.and(

    builder.equal(expr),

    builder.greaterThan(expr)

);

```

## 创建索引以提高性能

正如你之前读到的内容，请记住 `LIKE` 比较可以使用索引，除非它以通配符开头——当发生这种情况时，它将触发全表扫描。扫描的性能是糟糕的（非常慢），所以当你知道将要执行带有通配符的 `LIKE` 比较时，尝试包含至少另一个可以使用索引的准则。例如，你可以要求用户使用日期范围，或者自动将结果限制在过去一个月内创建或更新的内容。

在大多数情况下，`OR` 连接的准则可以利用索引，但效率不如 `AND` 连接的准则。如果你有两个或多个需要使用 `OR` 的条件，尽量尝试也包含一个 `AND` 索引。

请记住，查询必须包含索引中的第一列，才能使用该索引中的任何其他列。如果你有一个开销巨大的查询，其 `WHERE` 子句中只有一列，且没有以该列开头的索引，那么你将会遇到性能问题。让该列作为索引的第二或第三列看起来并不理想。

最后，唯一约束是你的朋友。它们是主键之外最快的索引。在 Oracle 等某些数据库中，你必须显式地创建索引以匹配约束。如果你正在创建一个 `User` 表并心想：“我将在代码中强制用户名的唯一性”，请退后考虑一步。唯一约束不仅强制了唯一性——它还为你提供了一种非常高效的手段，用于定位那些你很可能通过某列进行查找的记录（否则，你为什么要关心唯一性呢？）。在代码中强制唯一性是肯定的——这是一种最佳实践。但请同时也加上唯一约束。

## 在 JPA 中利用全文索引

尽管不同的行业和应用程序类型存在不同的趋势，但现今大多数用户倾向于在单个文本框中进行搜索查询来查找数据。你有几种方法来处理这种情况；**全文**是一个非常常见的解决方案。在全文搜索中，搜索引擎会分析数据库中每一份文档中的每一个单词，并计算包含相关性评分的匹配项。不同的搜索引擎计算相关性的方式不同，但通常来说，它涉及衡量结果与搜索查询的匹配程度，以及搜索词在特定结果中的接近程度。包含精确短语的结果其相关性评分将高于仅包含所有单词但并非精确的结果。

这种搜索的成本可能比简单的 `LIKE` 比较大得多，但专门的全文索引可以使任务变得高效得多。这些索引存储了索引数据中存在的每个单词，以及每个单词出现的次数（常见词的权重低于最罕有的词）以及它出现在哪些记录中，存储在其他统计和分析中。当执行全文搜索时，数据库可以使用索引快速找到匹配项，然后计算结果的相关性。这种技术比暴力全文本搜索要高效得多，以至于大多数数据库在允许执行全文搜索之前，都要求你必须拥有一个全文索引。

在本节中，你将探索如何在 MySQL 中创建全文索引、如何在 JPA 仓库中使用这些索引，以及如何让全文搜索在其他关系型数据库中更具可移植性。你可以为你贯穿本书编写的 `Customer Support` 项目添加全文搜索功能，让你的用户和员工能够轻松搜索你的支持工单。你可以参考 `Customer-Support-v17` 项目中的文本，该项目可以从 `wrox.com` 下载站点下载。

## 在 MySQL 表中创建全文索引

MySQL 与大多数数据库一样，如果你想执行全文搜索，就需要全文索引。作为 MyISAM 数据库引擎的一部分，它已经支持全文索引超过 10 年，在此期间只有 MyISAM 表可以持有全文索引。这意味着你可以创建一个事务表 (InnoDB)，也可以创建一个支持全文的表 (MyISAM)。但是，从 MySQL 5.6 开始，你现在可以创建既支持事务又支持全文的表，这是成千上万用户一直在使用的功能。最后，你可以在 InnoDB 中创建全文索引以支持全文搜索。这一变化并非没有限制，但你应该注意以下几点：

- MyISAM 和 InnoDB 是不同的引擎，因此它们的全文实现并不相同；在从 MyISAM 切换到 InnoDB 时记住这一点。
- 如果你在 MyISAM 上创建全文索引，InnoDB 的不同之处在于一次只能添加一个全文索引。一个表可以有多个全文索引，但由于某些原因，它们必须分语句添加。
- MyISAM 的 `ft_word_length` 配置和 `innodb_ft_token_size` 本质上相同，但默认值不同。如果你之前使用的是 MyISAM，可能需要将 `innodb_ft_token_size` 修改为适合你的值。
- InnoDB 的关键全文 Bug 最近已经修复。请确保你运行的至少是 MySQL 5.6.3。

> 注意：当你创建这些全文索引时，MySQL 会发出警告信息：“正在重建表以添加 FTS_DOC-ID”。不要担心，这是正常的。MySQL 为索引的 InnoDB 表添加了一个隐藏列来唯一标识记录。你永远看不到此列，它也不会干扰对表的正常使用。如果一个表有多个全文索引，MySQL 只添加此隐藏列，该表的所有索引共享它。
- InnoDB 引擎计算的相关性评分与 MyISAM 引擎计算的完全不同；无法将针对 MyISAM 表的查询评分与针对 InnoDB 表的查询评分进行比较。
- 文档提供了为这两个引擎添加和从停用词列表中移除内容的说明。

对于 `Customer Support` 应用（你从第一部分开始就在使用），你希望工单主题、工单正文和注释被索引。打开 MySQL Workbench 并运行以下语句，创建必要的全文索引：

```sql

Use CustomerSupport;

ALTER TABLE Ticket ADD FULLTEXT (Subject, Body);

ALTER TABLE Comment ADD FULLTEXT (Body);

```

运行项目提供的全部 `sql` 脚本，并在 Tomcat 的 `context.xml` 配置文件中创建适当的 `DataSource`。

## 创建并使用可搜索的仓库

与之前一样，你需要自定义仓库以使其可搜索。这始于你在上一节中使用的略有不同的 `SearchableRepository`。你还需要一种方法来返回不仅是 `Ticket`，还有它与结果的相关性。这需要使用自定义的 JPA 结果集映射，这是你还没有做过的操作，但将在本节中完成。为了返回实体和相关性，新的 `Search` 类作为两者的包装器。

```java

public class SearchResult<T>

{

    private final T entity;

    private final double relevance;

    public SearchResult(T entity, double relevance)

    {

        this.entity = entity;

        this.relevance = relevance;

    }

    // accessors

}

```

```java

public interface SearchableRepository<T>

{

    Page<SearchResult<T>> search(String query, boolean useBooleanMode, Pageable pageable);

}

```

```java

public interface TicketRepository extends JpaRepository<TicketEntity, Long>

{

    SearchableRepository<TicketEntity>

}

```

# 使用原生查询和自定义映射进行搜索

JPA 原生不支持全文搜索。在 criteria API 或 JPQL 中没有提供执行全文搜索的机制。然而，JPA 确实允许你执行原生查询（native queries）。原生查询是直接在数据库中执行的，而不是像 JPQL 查询那样由 JPA 供应商程序（JPA provider）进行解释。因此，你必须使用你所用数据库供应商的 SQL 语法编写原生查询，而不是 JPA 语法。你可以使用原生查询在数据库上执行全文搜索。遗憾的是，原生查询不是强类型查询（TypedQueries），但你在创建它们时仍然可以提供领域类实体，这样提供程序仍然知道如何将结果翻译为正确的实体。

此外，你还需要仅通过一次查询从数据库中检索 `TicketEntity` 和一个自定义列。这意味着你不能使用仅包含领域类的标准查询。相反，你需要定义一个自定义结果映射，告诉 JPA 如何处理这些额外的列。这是通过使用 `javax.persistence.SearchResultMapping` 注解映射 `TicketEntity` 类来实现的。

```java

@Entity

@Table(name = "Ticket")

@SqlResultMapping(

    name = "SearchResultMapping.ticket",

    entities = { @EntityResult(entityClass = TicketEntity.class) },



# 第 23 章 使用 JPA 和 HIBERNATE SEARCH 搜索数据

自定义结果集会被命名，当你在创建应使用该映射的查询时引用它。你可以使用一个或多个实体、列、类属性来指定结果集的映射方式。使用实体（entities），你可以指定一个或多个应该从结果中映射的托管 JPA 实体。（因此你可以使用一次查询返回多个实体。）列（column）属性允许你将单个列映射到标量（scalar）。在这种情况下，`_ft_scoreColumn` 映射到 `Double`。最后，类（classes）属性是 `@java.persistence.Constructor` 注解的数组。通过此属性，你可以将多个列映射到任何类的构造函数中，并使用这些列来构造并返回该类。

`@ResultSetMapping` 并不替换它所映射的实体的映射指令。事实上，它不需要出现在它所映射的任何实体上——它只需要出现在某个地方，以便 JPA 能够发现该自定义结果映射。如果你不想为此目的使用该注解，可以使用 XML 映射。替。以下 XML 与之前使用 `@ResultSetMapping` 的用法相同：

```xml
<xml version="1.0" encoding="UTF-8"?>
<entity-mappings xmlns="http://xmlns.jpa.org/xml/ns/persistence/orm"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schema-location="http://xmlns.jpa.org/xml/ns/persistence/orm_2_1.xsd">
  <result-set-mapping name="searchSearchResult*">
    <entity-result class="com.wrox.site.entities.TicketEntity" />
    <column-result name="ft_scoreColumn" class="java.lang.Double" />
  </result-set-mapping>
</entity-mapping>
</entity-mappings>
```

通常你会将此 XML 放在 `META-INF/orm.xml` 中。然而，你可以使用 `persistence.xml` 中的 `<mapping-file>` 为此文件指定不同的类路径。你还可以使用 Spring Framework 的 `LocalContainerEntityManagerFactoryBean` 来指定不同的类路径：

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactoryBeanBean() {
  LocalContainerEntityManagerFactoryBean factory = new LocalContainerEntityManagerFactoryBean();
  factory.setPropertiesMap("properties");
  factory.setMappingResources("com/wrox/mappings.xml");
}
```

`TicketRepositoryImpl` 处理搜索，同时也处理分页。正如你所见到的，`TicketRepositoryImpl` 处理搜索，同时也处理分页。大部分工作与 `getAllTickets` 和 `getComments` 方法并没有显著区别。

```java
public class TicketRepositoryImpl implements SearchableRepository<TicketEntity> {
    @PersistenceContext
    private EntityManager entityManager;

    @Override
    public Page<SearchResult<TicketEntity>> search(String query, boolean useBooleanMode, Pageable pageable) {
        String mode = useBooleanMode ? "NATURAL LANGUAGE" : "BOOLEAN LANGUAGE";

        long total = entityManager.createQuery(
            "SELECT COUNT(DISTINCT t) FROM Ticket t WHERE MATCH(t.subject, :query IN ...)", Long.class)
            .setParameter("query", query)
            .getSingleResult();

        List<Object[]> results = entityManager.createQuery(
            "SELECT t.*, MATCH(t.subject, :query IN " + mode + ") AS score "
            "FROM Ticket t ORDER BY score DESC")
            .setParameter("query", query)
            .setFirstResult(pageable.getOffset())
            .setMaxResults(pageable.getPageSize())
            .getResultList();

        List<SearchResult<TicketEntity>> list = new ArrayList<>();
        for (Object[] row : results) {
            list.add(new SearchResult<>((TicketEntity) row[0], (Double) row[1]));
        }
        return new PageImpl<>(list, pageable, total);
    }
}
```

> 注意：搜索方法的实现必须创建一个新的 `SearchResult` 对象集，这非常遗憾，并且进一步加强了消除 DTO 过程并思考直接持久化 `Ticket`、自动映射 `Instant` 字段和附件的必要性。不要放弃。你将在下一章中学习这些！

在控制器中添加搜索功能同样简单。你只需要一个简单的方法来显示空搜索表单，另一个用于处理它的简单方法。你还需要新的 `SearchForm` 命令对象，它只是一个 POJO。

```java
public class TicketController {
    @RequestMapping(value = "search")
    public String search(Map<String, Object> model) {
        model.put("searchPerformed", false);
        model.put("searchForm", new SearchForm());
        return "ticket/search";
    }

    @RequestMapping(value = "search", params = "query")
    public String search(Map<String, Object> model, @Valid SearchForm form,
        Errors errors, Pageable paging) {
        if (errors.hasErrors()) {
            // handle errors
        } else {
            model.put("searchPerformed", true);
            model.put("results", this.ticketService.search(form.getQuery(), form.isUseBooleanMode(), paging));
        }
        return "ticket/search";
    }
}
```

视图文件 `/WEB-INF/jsp/view/ticket/jsp.jsp` 虽然很长但很直接，因此在这里不再打印。它包含一个简单的表单用于提供查询并启用布尔搜索运算符，具有你在上一章中看到的分页功能，并且列表功能与 `/WEB-INF/jsp/view/ticket/list.jsp` 类似。在 `/WEB-INF/tags/template/basic.tag` 中还有一个指向搜索页的新链接。视图显示了每个结果的相关性，这对于大多数用户来说非常有意义。让这种具有意义的练习留给你来完成。

现在你可以尝试了！编译项目并从 IDE 启动 Tomcat。登录到 `http://localhost:8080/support/` 支持应用程序，并确保你有几条内容不同的 Ticket，这样你的搜索就不会返回所有内容。然后点击搜索链接，输入搜索短语并提交表单。务必搜索一些你知道没有结果的内容，你可不是在搜索记录！

# 使全文搜索具有可移植性

目前编写的 `TicketRepositoryImpl` 中的搜索方法是严格针对 MySQL 的。它无法在任何其他数据库上运行。那么，如何让这个方法具有可移植性呢？嗯，简单来说你做不到至少每个关系型数据库都支持全文搜索，因此你无法让此功能具有可移植性。许多 JPA 特性也是如此，例如身份生成的 ID（当 Oracle 不支持时）。实现通用移植性是可能的，支持所有支持全文搜索的数据库。

实现这一点并非易事。通用的事务——例如执行查询和处理分页——可以在通用场景中发生。你需要为每个支持的数据库提供一个不同的实现，用于生成原生 SQL 查询。然后，你必须检测底层数据库或要求进行某种类型的配置。（这并不合理——你总是必须配置 Hibernate ORM 方言）。因此，在你付出这些努力之前，你必须问问自己是否真的需要它。现实中，你通常在特定的应用程序中使用单个关系型数据库。如果你切换或添加另一个数据库，可以根据需要添加对其全文搜索的支持。

或者，你可以使用开源的 JPA Native Full-Text Search（Maven 坐标 `net.nicholsilliams.java.search`）来提供一个通用的、自配置的 JPA 全文集成，它跨多个数据库工作并可以支持你所有的实体，而无需编写任何查询。然而，它仍然是一个年轻的项目，需要贡献者支持所有不同的 SQL 方言并测试其所有功能。

# 使用 APACHE LUCENE 和 HIBERNATE SEARCH 索引任何数据

正如你所看到的，全文搜索是一个极其强大的工具，对你和你的用户可能是不可或缺的。然而，它并不总是你的可用选项。也许你使用的是不支持全文搜索的关系型数据库，例如 HyperSQL。或者你可能使用了数据库组合，并希望搜索在所有数据库中保持一致。也许你可能使用了其他存储选项，例如 XML 或 JSON 文件，或者不支持全文搜索的 NoSQL 数据库。甚至可能是你不喜欢数据库中全文搜索的工作方式，但没有切换的选项。坦率地说，并没有规定你必须使用数据库供应商提供的全文搜索工具。有许多其他选项可以满足你的搜索需求。其中之一就是 Apache Lucene。

Apache Lucene 是一个伞型项目，包含了各种开源搜索软件项目。其中之一就是 Lucene Core。Lucene 是一个基于 Java 的搜索引擎，还提供高级工具，如拼写检查、高亮显示和高级搜索分析。它可以说比大多数数据库提供的全文搜索更先进、功能更丰富，并为 Twitter、Apple 和 Wikipedia 等网站提供搜索。

# 使用 Apache Lucene 和 Hibernate Search 索引任何数据

Apache Solr 是由 Lucene 驱动的搜索服务器。它提供了高性能的 HTTP、XML、JSON、Ruby 和 Python API、缓存、复制和服务器管理界面。你可以使用 Lucene Core 或不通过 Solr 使用其客户端 Java API。更好用，使用 Hibernate Search，你可以将 Lucene Core 和 JPA/Hibernate 搜索集成，针对 Lucene 核心返回你的 JPA 实体。

> 注意：搜索方法的实现必须创建一个新的 `SearchResult` 对象集，这非常遗憾，并且进一步加强了消除 DTO 过程并思考直接持久化 `Ticket`、自动映射 `Instant` 字段和附件的必要性。不要放弃。你将在下一章中学习这些！

# 理解 Lucene 全文索引

Lucene 的另一个伟大功能是你可以配置其异步进行。这意味着你的创建、更新和删除操作不会被全文索引减慢。这是现代数据库简单无法提供的有用能力。

当你单独使用 Lucene 时，通过调用 Lucene Java API 来索引数据（从索引中删除数据）。本书不涵盖 Lucene API。相反，我们使用 Hibernate Search，它提供了一个更简单的接口来索引和搜索 JPA 和 Hibernate 实体。Hibernate ORM 会在你添加和更新实体时自动索引它们，并通过 JPA 检索它们。

与其为所有实体手动配置 Lucene，不如为你要索引的实体添加 Hibernate 注解，让 Hibernate Search 为你完成这一切。只需将 Lucene 视为 Lucene 的 JDBC API。Search-Engine 项目代表了一个极其原始的论坛，用户可以在那里发布消息。它没有任何回复功能。User 实体显然是一个简单的实体。它包含一个 ID 和用户名。

```java
@Entity
@Table(name = "UserPrincipal")
public class User {
    private long id;
    private String username;

    @Id
    @Column(name = "UserId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { ...; }

    public void setId(long id) { ...; }

    @Basic
    @Field
    public String getUsername() { ...; }

    public void setUsername(String username) { ...; }
}
```

该实体是一个简单的 JPA 实体。在这种情况下，你实际上不需要对用户实体执行全文搜索，但你确实需要根据创建帖子的用户的用户名来搜索论坛帖子。那么，它是如何工作的呢？看一看 `ForumPost` 实体。

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



ForumPost 使用了两个你尚未学习过的注解：`@ManyToOne` 和 `@JoinColumn`。你将在下一章节中探索它们，但目前它们对于演示 Hibernate 的功能是必须的。该实体使用了 `@org.hibernate.search.annotations.Indexed` 注解，表示该实体有资格进行全文索引。当你添加或保存它时，Hibernate Search 会自动创建或更新文档。`@org.hibernate.search.annotations.DocumentId` 注解告诉 Search 哪个属性是文档 ID。将其放置在属性上仅用于演示目的；如果你漏掉它，Hibernate Search 会自动回退到标记了 `@Id` 的属性。

`@org.hibernate.search.annotations.IndexedEmbedded` 是一个值得关注的注解。它告诉 Hibernate Search 该属性是一个带有索引字段的实体，该字段应该是此文档的一部分。通过这种方式，你可以在搜索中使用用户属性，并根据发布帖的用户来查找帖子。

`@org.hibernate.search.annotations.Field` 注解同时用于 `User` 和 `ForumPost` 实体。它将属性标记为应该进行全文索引并允许被搜索的属性，并且它有许多可以影响属性索引和存储方式的属性。理解如何使用这些属性需要对 Lucene 有深入的理解，而本书并未涉及这一点。在许多情况下，使用默认值是非常安全的。在 `ForumPost` 实体中，`keywords` 属性通过 `@org.hibernate.search.annotations.Boost` 注解字面上地提供了额外的权重，`boost` 属性指定了从 `keywords` 属性派生的相关性评分增加的因子。在这种情况下，该属性包含了用户指定的关键词，作者认为这些关键词指示了帖子的内容，因此让关键词在评分中具有更大的权重是合理的。

Search-Engine 项目中的 `create sql` 文件创建了 `SearchEngine` 数据库以及实体所需的表。它还向表中填充了几个用户。你应该使用 MySQL Workbench 并执行此脚本来创建数据库，然后创建以下 DataSource xml 配置文件：

```xml
<Resource name="jdbc:SearchEngine" type="java.sql.DataSource"
    maxActive="20" maxIdle="15" maxWait="10000"
    username="tomcat" password="password1234"
    driverClassName="com.mysql.jdbc.Driver"
    defaultTransactionIsolation="READ_COMMITTED"
    url="jdbc:mysql://localhost/SearchEngine" />
```

# 在 JPA 中使用 Hibernate Search

当你准备好进行索引时，你必须配置 Hibernate Search 和 Apache Lucene API 来执行搜索。然后，就是使用你现在可能非常熟悉的 Spring Data 自定义功能来创建另一个可搜索仓库的问题。

## 配置 Hibernate Search

配置 Hibernate Search 非常简单。你只需要在 `RootContext` 类中配置的 `EntityManagerFactory` 中添加以下属性（加粗部分）。

```java
@Bean
public LocalContainerEntityManagerFactoryBean entityManagerFactoryBean() {
    Map<String, Object> properties = new HashMap<>();
    properties.put("javax.persistence.schema-generation.action", "none");
    properties.put("hibernate.search.default.directory.provider", "filesystem");
    properties.put("hibernate.search.default.indexBase", "../search/indexes");
    HibernateJpaVendorAdapter adapter = new HibernateJpaVendorAdapter();
    adapter.setDatabasePlatform("org.hibernate.dialect.MySQL5InnoDialect");
    LocalContainerEntityManagerFactoryBean factory = new LocalContainerEntityManagerFactoryBean();
    factory.setJpaVendorAdapter(adapter);
    factory.setDataSource(this.searchEngineDataSource());
    factory.setPackagesToScan("com.wrotx.tomcat.entities"); // 修改为你的实体
    factory.setSharedCacheMode(SharedCacheMode.ENABLE_SELECTIVE);
    factory.setValidationMode(ValidationMode.NONE);
    factory.setJpaPropertyMap(properties);
    return factory;
}
```

## 使用 Apache Lucene Hibernate Search 索引任何数据 | 689

添加这两个属性完成了几项工作：

- 它启用了 Hibernate ORM 对 Hibernate Search 的使用。
- 它指定全文索引应该使用 Lucene 独立模式（不使用 Solr）并将索引保存到本地文件系统。
- 它指定 `../search/indexes`（相对于当前目录）作为保存全文索引的位置。

当然，如果你使用 Tomcat 集群或同时从多个 JVM 访问这些索引，那么这种做法是不安全的。你也可以使用具有不同取值的这些及类似的属性来配置 Hibernate Search 使用 Solr 服务器，从而在集群环境中是安全的。对于本地测试目的，此配置已经足够了。

## 创建 Lucene 可搜索仓库

创建一个启用了 Lucene 搜索的仓库与你在上一个版本中创建的原生仓库不同，但并不会更困难。与之不同的关键点之一是使用了 `org.hibernate.search.FullTextManager`，这是 Hibernate 集成中的核心接口。它扩展了 `EntityManager` 以添加线程绑定、事务关联的 `EntityManager` 代理。与 Spring 注入的 `EntityManager` 不同，Hibernate Search 只有在能够访问实际 Hibernate ORM 实现（而非代理）时才能创建 `FullTextEntityManager`。通常你从 `SearchableRepository` 和 `ForumRepository` 等基础接口开始。

```java
public interface SearchableRepository<T> {
    Page search(String query, Pageable pageable);
}
```

```java
public interface ForumRepository extends JpaRepository<ForumPost, Long>, SearchableRepository<ForumPost> {
}
```

### 列表 23-2: ForumRepositoryImpl.java

```java
public class ForumRepositoryImpl implements SearchableRepository<ForumPost> {
    @PersistenceContext
    EntityManager entityManager;

    EntityManagerProxy entityManagerProxy;

    @Override
    public Page<SearchResult<ForumPost>> search(String query, Pageable pageable) {
        FullTextEntityManager manager = this.getFullTextManager();
        QueryBuilder builder = manager.getSearchFactory().buildQueryBuilder()
            .entity(ForumPost.class).get();
        Query lucene = builder.keyword()
            .onFields("title", "body", "keywords", "user.username")
            .matching(query)
            .createQuery();
        FullTextQuery q = manager.createFullTextQuery(lucene, ForumPost.class);
        q.setProjection(FullTextQuery.THIS, FullTextQuery.SCORE);
        long total = q.getResultSize();
        q.setFirstResult(pageable.getOffset())
            .setMaxResults(pageable.getPageSize());
        @SuppressWarnings("unchecked")
        List<Object[]> results = q.getResultList();
        List<SearchResult<ForumPost>> list = new ArrayList<>();
        results.forEach(o -> list.add(
            new SearchResult<ForumPost>(o[0], (Float) o[1])
        ));
        return new PageImpl<>(list, pageable, total);
    }

    private FullTextEntityManager getFullTextManager() {
        return Search.getFullTextEntityManager(
            this.entityManagerProxy.getTargetEntityManager()
        );
    }

    @PostConstruct
    public void initialize() {
        if (!(this.entityManager instanceof EntityManagerProxy)) {
            throw new FatalBeanException("Entity manager " + this.entityManager +
                " was not a proxy");
        }
        this.entityManagerProxy = (EntityManagerProxy) this.entityManager;
    }
}
```



# 使用 Apache Lucene 和 Hibernate Search 索引任何数据

> **注意** 如果您直接使用 Hibernate API（而不是 JPA），则您将使用 `org.hibernate.search.FullTextSession` 接口，它为 `org.hibernate.Session` 添加了全文检索功能，而不是 `FullTextEntityManager`。

为了解决这个问题，`initialize` 方法首先将 `EntityManager` 强制转换为 `org.springframework.framework.orm.jpa.EntityManagerProxy`，这是 `Spring-EntityManager` 实现的接口。该方法只被调用一次，但每次需要 `FullTextEntityManager` 时都会调用 `getFullTextEntityManager`，且仅在事务内部调用。它调用 `EntityManagerProxy` 上的 `getTargetEntityManager` 来获取 Hibernate ORM `EntityManager` 实现。然后它使用 `org.hibernate.search.jpa.Search` 方法 `getFullTextEntityManager` 从底层的 `EntityManager` 获取 `FullTextQuery`。

当我们搜索 `FullTextEntityManager` 时，它为 `ForumPost` 创建一个 `org.hibernate.search.query.dsl.QueryBuilder`。然后它使用该构建器为查询字符串和您将搜索的 `ForumPosts` 创建一个 `org.apache.lucene.search.Query`。注意使用点表示法（列表 23-2 中的加粗部分）来搜索 `user` 字段中实体的 `username` 字段。您可以根据需要使用任意数量的点表示法来包含嵌入实体。另外注意，如果您愿意，可以使用 Lucene API 并使用其中一个 `QueryBuilder` 来创建此查询。

接下来的代码为 Lucene 查询和 `ForumPost` 实体获取一个 `org.hibernate.search.FullTextQuery`。`FullTextQuery` 是一个 `javax.persistence.Query`，能够执行所有必要的 Lucene 和 JPA 查询。它设置了查询的投影，告诉 Hibernate Search 将实体作为对象数组的第一个元素返回（`FullTextQuery.THIS`），并将相关性评分作为第二个元素返回（`FullTextQuery.SCORE`），这实际上与您在上一个方法中用于检索实体和分数的技术完全相同。

最后，代码获取了预期的总结果大小、分页边界、结果大小，并将其转换为 `SearchResultForumPosts` 的 `Page`。唯一需要注意的点是 Lucene 不参与 JPA 事务，因此结果数量在 `getResultSize` 和 `getResultList` 之间可能会变化。

# 测试搜索引擎

在测试 Apache Lucene 存储库之前，您需要采取最后一步是创建一个事务性服务、控制器和用户界面。`MainService` 和 `DefaultMain` 非常简单，仅作为控制器和存储库之间标记了 `@Transactional` 的透传层。`MainActivity` 非常简单。对于您习惯的许多验证和检查例程，这只是对 Lucene 搜索能力的测试。它响应主页的请求，并在 `/WEB-INF/jsp/view/add.jsp` 中提供一个简单的表单用于创建新的论坛帖子。控制器的处理逻辑对您来说应该非常熟悉，它们与 `Customer Support` 应用程序中的 `TicketController` 几乎相同。最后，`/WEB-INF/jsp/view/search.jsp` 视图处理表单搜索、搜索结果显示和分页，其方式也与 `Customer Support` 应用程序非常相似。

现在您已经查看了代码的其余部分，请采取以下步骤进行测试：

1. 编译应用程序并从 IDE 启动 Tomcat。在 Tomcat 根目录下查看 Lucene 索引文件目录（如果您使用 Windows，可能是 `C:\Program Files\Apache Software Foundation\Tomcat 8.0`）。
2. 在浏览器中访问 `http://localhost:8080/forums/` 并创建几个论坛帖子。在每个帖子提供的用户名之间在 `Nicholas`、`Sarah`、`Mike` 和 `John` 之间交替。这些是您之前创建的数据库中预置的用户。
3. 在创建了几个内容各不同的帖子后，检查搜索链接并尝试一些不同的搜索查询。确保您也搜索一两个用户名，以找到这些用户的帖子。

### 总结

您在本章中涵盖了大量内容。您学习了搜索和索引数据的一些基本概念，并探索了如何使用 JPA Criteria API 创建极其复杂的查询。您接触了全文检索的概念，学习了如何在 MySQL 中创建全文索引，并探索了 Apache Lucene 和 Hibernate Search，创建了带索引的实体以及能够使用 Lucene 全文索引搜索这些实体的存储库。需要注意的是，您对 Apache Lucene 和 Hibernate Search 的研究仅触及了皮毛。关于它们的使用和功能可以写几百页，希望本章能激发您进一步研究这些主题的兴趣。

下一章将结束 JPA 持久化 API。您将学习如何创建一些复杂的映射，并最终使用 JPA 转换器将 Java 8 日期时间类型包含在实体中。您还学习了在本章上一节中看到的 `@ManyToOne` 和 `@JoinTable` 注解。

# 24 创建高级映射和自定义数据类型

## 本章内容

- 为什么要转换非标准数据类型？
- 如何将 POJO 嵌入实体内部
- 如何定义实体之间的关系
- 使用版本号和时间戳对实体进行建模
- 如何定义通用实体祖类
- 如何映射基本值和嵌入值的集合和映射
- 使用多表存储实体
- 构建程序化触发器
- 使用时间织入延迟加载简单属性

## 本章 WROX.COM 代码下载

您可以在 http://www.wrox.com/go/projectjavaforwebapps 的 `Download Code` 标签页中找到本章的代码下载。本章的代码分为以下几个主要示例：

- Advanced-Mappings Project
- Customer-Support-v18 Project

## 本章的新 Maven 依赖

本章没有新的 Maven 依赖。继续使用之前章节中引入的 Maven 依赖。

# 还剩下什么？

所以您已经通过 JPA 完成了一些很酷的事情。从简单查询到复杂查询，您彻底探索了 Java 持久化 API 和所有的 CRUD 能力。

还剩下什么？嗯，您只是触及了对象映射到数据库表的表面。在现实中，您的实体不会是简单的。您在 `Customer Support` 应用程序的 `TicketEntity` 和 `CommentEntity` 中已经看到了这个问题。例如，持久 `Instant` 创建日期会更容易，但现在 JPA 2.2（或未来的 JPA 3.0）将会支持，但现在需要一个不同的解决方案。

> **注意** 为了确保在下一个版本的 JPA 中包含 Java 8 日期时间支持，请访问 https://java.net/browse/JPA_SPEC-63 为该功能请求投票。您需要创建一个 Java.net 账户或使用现有的 Java.net 账户登录投票。

作为起点，请查看您还需要学习以充分利用实体的一些内容：

- 转换不支持的简单类型，例如 `Instant`、`LocalDateTime`、`java.net.InetAddress` 等。
- 除基本属性外，为实体映射 POJO 属性类型。例如，您可能有一个 `PhoneNumber` 对象，它包含存储在多个列中的电话号码组件，但它本身不是一个实体。
- 定义一对一、多对一和多对多的关系。一个很好的例子是在检索 `Ticket` 的同时检索其 `Attach`。当然，这种关系应该是延迟加载的，以免在简单列出 `Tickets` 时不必要的加载大量的 `Attach`。另一个例子是同时检索 `Ticket` 和创建该 `Ticket` 的 `UserPrincipal`。
- 版本实体，跟踪它们更新的次数。
- 在基类中定义许多实体的通用属性，让这些实体继承该基类。这样您就不需要为 ID、审核和版本控制等编写重复代码。
- 适配现有的数据库和应用程序。并不是应用程序都能从领域模型开始并创建合适的数据库。在这种情况下，有时将实体数据拆分成多个表是有帮助的，并且需要一种方法将所有这些数据映射到一个实体中。
- 定义在实体 CRUD 操作之前或之后执行的自定义行为。

正如您看到的，您才刚刚开始。在本章中，您将涵盖所有这些主题，完成后，您将拥有无限的方法来使用 JPA 实体。在本章的大部分内容中，您可以参考 Advanced-Mappings 项目，该项目可以在 wrox.com 代码下载站点下载。本章涵盖了该项目中的映射，但没有提到您已经熟悉的 Spring Data JPA 存储库、控制器或（简单的）接口。在本章的任何时候，您都可以从您的 IDE 中编译并启动项目，或者访问 `http://localhost:8080/mappings`，并使用主页上的链接来测试实体映射。

在本章结束时，您将运用掌握的主题使客户支持（Customer Support）应用程序中持久化实体的任务变得更容易。

## 转换非标准数据类型

在第 20 章中，您学习了 JPA 供应商需要支持的 `@Basic`、`@Lob`、`@Enumerated` 和 `@Temporal` 类型。这些非常详尽，但绝不能满足所有需求。您可能已经发现它不包含新的 JPA 日期和时间类型。（但请关注新版本 JPA 中对这些的支持。）某些提供商提供了额外的类型——例如，Hibernate ORM 自动支持 Joda Time 类型。Hibernate ORM 5.0 可能在某时刻支持 JPA 日期和时间类型。依赖此特性是不可移植的，因为它是非标准的。如果您某天切换了供应商，您的代码可能会停止工作。

那么您能对此做什么呢？在 JPA 之前的版本中，没有什么可以做。在 JPA 2.1 之前，没有办法可以持久化和检索不受原生支持的简单类型（即本身不是 POJO 的类型）。这限制了您的选择。结果，大多数主要的供应商都提供私有 API 来定义自定义类型。使用 Hibernate，您可以实现 `org.hibernate.usertype.UserType` 或 `org.hibernate.usertype.CompositeUserType`，然后为该属性指定 `UserType` 或 `CompositeUserType` 实现。然而，这并不比依赖特定供应商支持的非标准类型更具可移植性，而且在您切换供应商时它会失效。

这个问题在 JPA 2.1 中通过**属性转换器**得到了解决，尽管它们并非没有缺点。

## 理解属性转换器

属性转换器是实现 `javax.persistence.AttributeConverter` 的任何类。属性转换器的目的是在实体与不支持的简单类型以及支持的基本类型之间进行转换。这在几乎所有情况下都有效。使用 JDBC 时，您最终必须在保存值到数据库之前将您可以想象的任何简单类型转换为基本类型之一。例如，如果您创建了一个持有无符号整数的自定义 `UnsignedLong` 类，将值存入和取出数据库唯一的方法是调用 `PreparedStatement.setBigDecimal` 和 `ResultSet.getBigDecimal` 方法。这意味着您可以通过实现一个在 `UnsignedLong` 和 `BigDecimal` 之间转换的 `AttributeConverter` 在 JPA 中完成这一点。

讽刺的是，特殊情况是转换涉及日期和时间的类型。JDBC 处理的 `setDate`、`setTime`、`setTimestamp`、`getDate`、`getTime` 和 `getTimestamp` 方法处理的是 `java.sql.Date` 和 `Timestamp`。从 JDBC 4.1 开始，您必须使用这些类型在数据库中设置和检索日期和时间。您记得从 JDBC 4.2 开始，增加了支持比这更多类型的方法。由于可以直接访问 JDBC 4.1 和 JDBC 4.2 驱动程序，以下代码是持久化 `Instant`、`LocalDateTime`、`LocalTime`、`OffsetDateTime`、`OffsetTime` 和 `ZonedDateTime` 属性的正确方法。

```java
statement.setObject(1, instant, JDBCType.TIMESTAMP);
statement.setObject(2, dateTime, JDBCType.TIMESTAMP);
statement.setObject(3, date, JDBCType.DATE);
statement.setObject(4, localTime, JDBCType.TIME);
statement.setObject(5, offsetDateTime, JDBCType.TIMESTAMP_WITH_TIMEZONE);
statement.setObject(6, offsetTime, JDBCType.TIME_WITH_TIMEZONE);
statement.setObject(7, zonedDateTime, JDBCType.TIMESTAMP_WITH_TIMEZONE);
```

同样，您使用类似于下面的代码检索这些类型：

```java
instant = result.getObject("Instant", Instant.class);
localDateTime = result.getObject("LocalDateTime", LocalDateTime.class);
localTime = result.getObject("LocalTime", LocalTime.class);
offsetDateTime = result.getObject("offsetDateTime", OffsetDateTime.class);
zonedDateTime = result.getObject("zonedDateTime", ZonedDateTime.class);
```

然而，`AttributeConverter` 并不会将自定义类型转换为 JPA 支持的目标类型。因此，您必须编写在这些类型与 `java.sql.Date`、`Time` 和 `Timestamp` 之间转换的 `AttributeConverter`，或者您仍然必须使用如 Hibernate 的 `UserType` 等私有 API。您应该记得第 20 章提到的，所有主要的关系型数据库供应商提供 JDBC 4.2 驱动程序可能需要数年。如果没有这些新方法的支持，诉诸 `UserType` 是徒劳的。因此，您最好的选择是坚持使用 `AttributeConverter`。

## 理解转换注解

实现 `AttributeConverter` 是创建和使用属性转换器的第一步。有几个简单的注解您必须利用以让您的转换器工作。其中第一个是 `@javax.persistence.Converter`。实现 `AttributeConverter` 的具体类必须标记有 `@Converter` 注解，或者在 JPA 映射文件（如 `orm.xml`）的 `<converter>` 中指定。此外，如果您不想将其包含在持久化单元中，或者启用了 `<exclude-listed-classes>`，您必须使用 `<class>` 或 `<exclude-listed-classes>` 指明该转换器是一个受管理的类。

如果 `autoApply` 为 `false` 或未省略（默认为 `false`），您必须在属性上使用 `javax.persistence.Convert` 注解来指示哪个转换器。您可以注解字段（如果您使用属性访问）、访问器方法（如果您使用方法访问）或实体本身。以下三种 `@Convert` 的用法是等效的：

```java
public class MyEntity {
    @Convert(converter = InstantConverter.class)
    private Instant dateCreated;
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
}
```

如果您使用后一种方法，可能有多个需要转换的属性。虽然注解单个属性更容易，但您可以使用 `@javax.persistence.Converts` 注解在实体级别组合多个 `@Convert` 注解。

```java
@Converts({
```



## 创建和使用属性转换器

在很多情况下，你的属性非常简单。Advanced-Mappings 项目中的 `InstantConverter` 在每个方法中只有一行代码。

```java
@Convert(attributeName = "dateCreated", converter = InstantConverter.class),
@Convert(attributeName = "dateModified", converter = InstantConverter.class)
)
public class MyEntity {

    private Instant dateCreated;
    private Instant dateModified;

    public Instant getDateCreated() { ... }
    public void setDateCreated(Instant instance) { ... }
    public Instant getDateModified() { ... }
    public void setDateModified(Instant instance) { ... }
}
```

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
    @Column(name = "UserId", strategy = GenerationType.IDENTITY)
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

最后，在 `RootContextConfiguration` 中，`com.wrox.site.converters` 包被添加到 `LocalContainerEntityManagerFactoryPackagesToScan` 中。这确保了转换器被添加到持久化单元中，以便在应用程序中使用。

```java
@Bean
public LocalContainerEntityManagerFactory entityManagerBean() {
    factory.setDataSource(this.advancedMappingsDataSource());
    factory.setPackagesToScan("com.wrox.site.entities", "com.wrox.site.converters");
    factory.setSharedCacheMode(SharedCacheMode.ENABLE_SELECTIVE);
}
```

### 在实体中嵌入 POJO

有时，让实体仅使用简单类型可能并不方便。考虑经典的电话号码难题：人（Person）拥有一个电话号码，但你想将国家代码和电话号码存储在不同的列中。你可以创建 `countryCode` 和 `phoneNumber` 属性，但这样做很笨拙。更理想的解决方案是拥有一个类型为 `PhoneNumber` 的 `phoneNumber` 属性，它内部包含 `countryCode` 和 `number`。使用 JPA 嵌入类型（embeddable types）可以实现这种方法。嵌入类型本质上是其所属实体的一部分。它们始终存储与实体相同的表中，并共享相同的 ID。它们不是实体，也不能是实体。

## 表明类型是可嵌入的

在许多方面，嵌入类型看起来非常像实体。它可以包含任意数量带有 `@Basic`、`@Column`、`@Lob`、`@Temporal`、`@Enumerated`、`@Convert` 注解的属性，但它不能标记 `@Entity` 或 `@Table`，也不能包含任何标记为 `@Id` 或 `@Embedded` 的属性。它可以包含其他嵌入类型的属性。

要标记一个类为可嵌入，你需要的就是 `@javax.persistence.Embeddable`。在接下来的 `PhoneNumber` 类中进行了演示，该注解表示它可以作为你应用程序中的任何属性被嵌入。实体类和 `@Embeddable` 类必须在你的持久化单元中被注册为类。这意味着你必须在持久化单元配置的 `<class>` 或 `<jar-file>` 元素中指定它们，或者在持久化单元配置中禁用 `<exclude-unlisted-classes>`，或者让 Spring 的 `LocalContainerEntityManagerFactoryBean` 发现扫描到的类。通过将 `PhoneNumber` 放置在 `com.wrox.site.entities` 包中，它会被自动发现并添加到持久化单元中。

## 第 24 章：创建高级映射和自定义数据类型

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

注意，`PhoneNumber` 包含两个属性，每个属性映射到它自己的列。任何实体都可以包含一个 `PhoneNumber` 属性，该实体的表将拥有列 `PhoneNumber_CountryCode` 和 `PhoneNumber_Number`。

### 将属性设为嵌入

实际上，嵌入一个嵌入实体非常简单。只需为该类型的属性标记上 `@javax.persistence.Embedded` 注解即可。你不能对该属性标记任何其他注解，例如 `@Basic`、`@Temporal` 或 `@Column`。这在 `Person` 实体中得到了演示。

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

> **注意**：`@Embedded` 仅用于实体中的非 ID 属性。你可以使用嵌入类型作为复合实体 ID，但你必须使用 `@javax.persistence.EmbeddedId` 而不是 `@Embedded` 来标记 ID 属性。你已经在第 20 章中探索过如何创建这样的复合 ID。

如前提到的，嵌入类型可以包含嵌入属性。此的一个很好的例子是接下来的 `Address` 和 `PostalCode` POJO。

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
    @Column(name = "PostalCode_Suffix")
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

### 覆盖嵌入列名

`PostalCode` 的设计使其可以单独使用或作为地址的一部分使用。问题在于列名。按照目前的写法，`Person` 表将拥有 `Address_Street`、`Address_City`、`Address_State`、`Address_Country`、`PostalCode_Code` 和 `PostalCode_Suffix`。从这些名称并不看出邮政编码列是地址的一部分。你可以轻松地在 `Person` 实体中使用 `@javax.persistence.AttributeOverride` 注解修复此，它允许你在使用这些实体中更改这些列名。你还可以使用 `@javax.persistence.AttributeOverrides` 注解，它允许你对一组覆盖。

```java
@Entity
public class Person {
    private Address address;

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

`name` 属性使用点符号法来指示覆盖哪些列名。由于 `Address` 实体包含一个名为 `postalCode` 的属性，因此两个名称的第一部分都是 `postalCode`。这是基于属性名称而非属性类型，所以如果 `Address` 的 `PostalCode` 属性名为 `zip`，那么名称的第一部分将是 `zip`。名称的第二部分是 `PostalCode` 中被覆盖的属性。

通过这种表示法，你可以指定更深层的覆盖。属性覆盖还允许在任何给实体（或其他嵌入类型）中多次覆盖同一个嵌入类型。你只需要在除一个处以外的所有地方进行覆盖。（通常你会覆盖所有但一个处。）

通过这些更改，以下语句将为 `Person` 实体创建相应的表和列。

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

### 定义实体之间的关系



### 定义实体之间的关系

正如你所看到的，实体与其他实体之间存在关系是非常常见的。例如，客户支持应用程序中的工单（`Tickets`）拥有附件（`Attachments`），到目前为止，你必须在服务层中管理这种关系。然而，这一额外的步骤并不是必要的。如果某个特定实体与其他实体有许多关系，你可能仍然想在某些情况下使用它。但撇开这些特殊情况，你可以直接在实体内部定义实体关系，JPA 提供程序可以在你需要的时候获取你所需的实体。

## 一对一关系

一对一关系可能是你最可能定义的一种关系。一对一关系意味着实体 A 与最多一个实体 B 关联，而实体 B 与最多一个实体 A 关联。泛而言之，这种关系违反了范式规则和认可的面向对象设计实践。然而，在某些情况下，它是解决特殊问题的更实用的方法。例如，如果一个实体包含数百个属性，你可能希望将这些属性分组到子实体中，使所有相关的属性都属于自己的实体。这个虚拟的员工（`Employee`）实体就展示了这样的情况。

```java
@Entity
public class Employee {

    private long id;
    ...
    private EmployeeInfo info;

    @Id
    @Column(name = "EmployeeId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { return ... }

    public void setId(long id) { return ... }

    @OneToOne(mappedBy = "employee", fetch = FetchType.LAZY,
               cascade = CascadeType.ALL, orphanRemoval = true)
    public EmployeeInfo getInfo() { return ... }

    public void setInfo(EmployeeInfo employeeInfo) { return ... }
}

@Entity
public class EmployeeInfo {

    private long id;
    private Employee employee;

    @Id
    public long getId() { ... }

    public void setId(long id) { ... }

    @OneToOne(mappedBy = "info")
    @Column(name = "EmployeeId")
    public Employee getEmployee() { ... }

    public void setEmployee(Employee employee) { ... }
}
```

如果你想在关系的某一侧定义关系。例如，你可以在 `Employee` 中保留 `info` 属性，但在 `EmployeeInfo` 中省略 `employee` 属性（反之亦然）。在这种情况下，关系是双向的，因此你必须在 `Employee` 上的属性和 `EmployeeInfo` 上的 `employee` 属性上使用 `@javax.persistence.OneToOne` 注解，并都指定 `mappedBy` 属性。

该属性告诉 JPA 提供程序关系另一端的哪个属性映射回“this”。`fetch` 属性指示何时使用 `java.persistence.FetchType` 将相关实体取回数据库。`FetchType.EAGER` 意味着 JPA 提供程序在检索实体时必须获取这些值。另一方面，`FetchType.LAZY` 是向 JPA 提供程序的一个提示，表示它只有在首次访问时才获取这些值（这可能是真的，从而节省一次数据库访问）。然而，JPA 提供程序并不要求支持懒加载，因此值可能仍会被急加载。在这里，`fetch` 属性默认为 `FetchType.EAGER`，通常对于一对一关系也是如此。Hibernate ORM 和 EclipseLink 支持懒加载，但对于一对一关系，必须启用类加载。你可以在“完善客户支持”章节中学习更多信息。

`@OneToOne` 的 `cascade` 属性表示当对实体执行操作时会对相关实体发生什么。使用 `java.persistence.CascadeType` 你可以指定一个或多个值：`DETACH`、`MERGE`、`PERSIST`、`REFRESH`、`REMOVE` 对应 `EntityManager` 操作。你也可以使用 `ALL` 作为这些值的快捷方式。对于一对一关系，你可能需要在实体内部指定级联指令。`orphanRemoval` 属性指示相关实体是否被删除。如果设置为 `false`，则该关系是可选的。它的默认值为 `true`，意味着该关系是可选的。

```java
@Entity
public class Applicant {

    private long id;
    private String firstName;
    private String lastName;
    private boolean citizen;
    private Set<Resume> resumés = new HashSet<>();

    @Id
    @Column(name = "ApplicantId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { return ... }

    public void setId(long id) { return ... }

    @Basic
    public String getFirstName() { return ... }

    public void setFirstName(String firstName) { return ... }

    @Basic
    public String getLastName() { return ... }

    public void setLastName(String lastName) { return ... }

    @Basic
    public boolean isCitizen() { return ... }

    public void setCitizen(boolean citizen) { return ... }

    @OneToOne(mappedBy = "applicant", fetch = FetchType.LAZY, cascade = CascadeType.ALL)
    public Set<Resume> getResumés() { return ... }

    public void setResumés(Set<Resume> resumés) { return ... }
}

@Entity
@Table(name = "Applicant_Resume")
public class Resume {

    private long id;
    private String title;
    private String content;

    @Id
    @Column(name = "ResumeId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { return ... }

    public void setId(long id) { return ... }

    @Basic
    public String getTitle() { return ... }

    public void setTitle(String title) { return ... }

    @Lob
    public String getContent() { return ... }

    public void setContent(String content) { return ... }

    @OneToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "ApplicantId")
    public Applicant getApplicant() { return ... }

    public void setApplicant(Applicant applicant) { return ... }
}
```

### 一对多与多对一关系

```java
@Entity
public class Applicant {
    ...
}

@OneToMany(mappedBy = "applicant", fetch = FetchType.LAZY,
    cascade = CascadeType.ALL, orphanRemoval = true)
public Set<Resume> getResumes() { ... }

public void setResumes(Set<Resume> résumes) { ... }
```

```java
@Entity
@Table(name = "Applicant_Resume")
public class Resume {
    ...
    private long id;
    private Applicant applicant;
    ...
    @ManyToOne(fetch = FetchType.EAGER, optional = false)
    @JoinColumn(name = "ApplicantId")
    public Applicant getApplicant() { ... }

    public void setApplicant(Applicant applicant) { ... }
}
```

`javax.persistence.OneToMany` 和 `javax.persistence.ManyToOne` 注解包含许多与 `@OneToOne` 相同的属性。`@ManyToOne` 拥有一个 `optional` 属性，因为这种概念不适用于值集合（集合始终可能是空的）。只有在双向一对多关系中，`@OneToMany` 包含 `mappedBy` 属性，因为只有一对多的一侧需要此信息。`@OneToMany` 也是这两个注解中唯一带有 `orphanRemoval` 属性的注解，因为这种操作仅在关系的一侧才有意义。

你可能注意到 `@javax.persistence.JoinColumn` 注解在 `Resume` 中从原始属性移动到了新属性。这类似于 `@Column` 注解，用于指定连接这两个实体的列的详细信息。（如果键是复合的，则使用 `@javax.persistence.JoinColumns` 来包含多个注解。）在单向一对多关系中，它位于关系中可以放置的唯一一侧：即 `@OneToMany` 侧（`Applicant`）。对于这些关系，它指示了另一个实体表中的哪一列包含此主键。在单向多对一关系或双向一对多关系中，它属于 `@ManyToOne` 侧（`Resume`）。对于这些关系，`@JoinColumn` 指明了“当前”实体表中哪一列包含另一个实体的主键。它替换了该属性的 `@Column` 注解。

与其使用 `Resumes` 的 `Set`，你可以使用 `Resumes` 的 `List` 并以某种方式维护它们的顺序。要做到这一点，你需要在 `List` 属性（即 `@OneToMany` 侧）上使用 `@javax.persistence.OrderColumn` 注解，并指定 `Applicant_Resume` 表中 `Resumes` 应该排序的列名。你也可以指定一个 `Resumes` `Map`。在这种情况下，你需要从 `Applicant_Resume` 表中选择某些列作为 `Map` 的键。你可以在 `Map` 属性上使用 `@javax.persistence.MapKey` 注解，这意味着 `Map` 的键是 `Resumes` 的 `@Id` 属性。或者，你可以使用 `@javax.persistence.MapKeyColumn` 指定一个 `Applicant_Resume` 列的名称（如 `Title`）作为 `Map` 的键。

最后一点说明：对于 `Map` 属性，你可以使用 `@OrderBy` 来让 `Map` 条目（通过 `entrySet()` 返回）和值（通过 `values()` 返回）根据该列进行排序。

`Applicant` 和 `Resume` 实体的最终版本映射到以下 MySQL Schema：

```sql
CREATE TABLE Applicant {
    ApplicantId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    FirstName VARCHAR(60) NOT NULL,
    LastName VARCHAR(60) NOT NULL,
    Citizen BOOLEAN NOT NULL
} ENGINE = InnoDB;
```

```sql
CREATE TABLE Resume {
    ResumeId BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    ApplicantId BIGINT UNSIGNED NOT NULL,
    Title VARCHAR(100) NOT NULL,
    Content TEXT NOT NULL,
    CONSTRAINT Applicant_Resume_FOREIGN KEY (ApplicantId)
    REFERENCES Applicant(ApplicantId) ON DELETE CASCADE
} ENGINE = InnoDB;
```

# 创建多对多关系

多对多关系是一对多和多对一关系的自然扩展。在多对多关系中，关系的每一侧都可以关联另一侧的多个实体。一个常见的例子是学校和学生之间的关系。一所学校有很多学生，一个学生可以上多所学校。因此，学校实体将拥有一个学生的 `Set`、`List` 或 `Map`，而学生实体将拥有一个学校的 `Set`、`List` 或 `Map`。

你可以使用 `@javax.persistence.ManyToMany` 观察多对多关系的一侧或双侧。它具有为人知的 `cascade`、`fetch` 和 `mappedBy` 属性。只有当关系是双向的，你必须指定 `mappedBy`，且通常情况下，其值属性指向关系的另一端。你仅在关系的一侧（非所有者侧，取决于你如何定义所有权）上指定 `mappedBy`。

在添加多对多关系（单向或双向）时，JPA 供应商会尝试猜测连接表及其列的名称。为了稳妥起见，最好避免这种不确定性的猜测并指定 `@javax.persistence.JoinTable` 注解。你将此注解放在关系的所有者侧（即你指定 `mappedBy` 的对侧）。除了表名和其他详细信息外，该注解还包含 `joinColumns` 和 `inverseJoinColumns` 属性。你使用 `joinColumns` 指定一个或多个 `@JoinColumn`，指示“当前”（所有者实体）主键映射到哪列或哪些列。同样，你使用 `inverseJoinColumns` 指定一个或多个 `@JoinColumn`，指示另一个（被拥有的）实体主键映射到哪一列。在前面描述的学校和学生示例中，映射可能如下：

```java
@ManyToMany
@JoinTable(
  name = "school_student",
  joinColumns = @JoinColumn(name = "school_id"),
  inverseJoinColumns = @JoinColumn(name = "student_id")
)
private Set<Student> students = new HashSet<>();

@ManyToMany(mappedBy = "schools")
private Set<School> schools = new HashSet<>();
```



### 处理其他常见情况

存在许多不需要处理简单的情况，但某些是有用的，例如实体版本管理。

## 使用时间戳进行实体版本管理

简单来说，你可以创建一个映射超类来定义实体的版本。

当使用悲观锁时，可能会发生两种失败。第一种是锁定失败导致数据库回滚。此类错误会导致 `javax.persistence.PersistenceLockException`（同样回滚存在的 JTA 事务）。然而，数据库锁定可能导致单个语句的回滚。在这种情况下，失败是瞬时的，会导致 `javax.persistence.LockTimeoutException`。需要你通过重试语句或回滚事务来处理超时。

## 理解乐观锁与悲观锁

乐观锁允许两个或多个线程同时读取同一个实体，但只允许一个更新实体。这可以防止并发修改。但如果你倾向于锁定行以便始终只有一个线程可以读取实体，可以通过指定 `javax.persistence.LockModeType PESSIMISTIC_READ` 实现。在 Spring Data JPA 中，你可以使用 `@Lock` 实现相同的效果。在大多数情况下，乐观锁就足够了，你不需要启用悲观锁。

## 定义带有通用属性的抽象实体

创建特殊实体后，你可能会发现它们包含至少几个相同的属性。例如，你可能会发现所有的实体都有 ID、创建日期、修改日期和 `@Version` 属性。你不需要在每次创建实体时重新定义属性，可以创建一个映射超类来一次定义这些实体。

同样，映射超父类（mapped superclass）不能重写其祖类中的一个非 `@Transient` 方法并将其标记为 `@Transient`。

Advanced-Mappings 项目中的 `BaseEntity` 超类定义了所有扩展实体都将拥有的简单 id 属性。`VersionedEntity` 是一个映射超父类，继承自 `BaseEntity`，以指定一个 `@Version` 属性用于乐观锁。最后，`AuditedEntity` 映射超父类继承自 `VersionedEntity`，并指定了创建和修改属性。

```java
@MappedSuperclass
public abstract class BaseEntity {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { }

    public void setId(long id) { }
}
```

```java
@MappedSuperclass
public abstract class VersionedEntity extends BaseEntity {

    private long version;

    @Version
    @Column(name = "Revision")
    public long getVersion() { }

    public void setVersion(long version) { }
}
```

```java
@MappedSuperclass
public abstract class AuditedEntity extends VersionedEntity {

    private Instant dateCreated;
    private Instant dateModified;

    @Convert(converter = InstantConverter.class)
    public Instant getDateCreated() { }

    public void setDateCreated(Instant dateCreated) { }

    @Convert(converter = InstantConverter.class)
    public Instant getDateModified() { }

    public void setDateModified(Instant dateModified) { }
}
```

你可以创建继承自这些映射超父类中任何一个的新实体。`NewsArticle` 实体继承自 `AuditedEntity` 并继承了其所有超类的属性。它的 SQL 架构反映了被重写的 id 列名。

```java
@Entity
@AttributeOverride(name = "id")
public class NewsArticle {
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
  Id BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
  Revision BIGINT UNSIGNED NOT NULL,
  DateCreated TIMESTAMP(6) NULL,
  DateModified TIMESTAMP(6) NULL,
  Title VARCHAR(100) NOT NULL,
  Content TEXT NOT NULL
) ENGINE = InnoDB;
```

与实体类一样，`@MappedSuperclasses` 必须在你的持久化单元（persistence unit）中注册为托管类。你必须在持久化单元配置的 `<class>` 或 `<jar-file>` 中指定它们，或者在持久化单元配置中禁用 `exclude-unlisted-classes`，或者让 Spring 的 `LocalEntityManagerFactoryBean` 发现的扫描类包含它们。通过在 `com.wrox.site.entities` 包中使用 `BaseEntity`、`EmbeddedEntity` 和 `AuditedEntity`，它们会被自动发现并添加到持久化单元中。

## 映射基本和嵌入集合

到目前为止，你已经创建了具有基本类型属性、嵌入类型属性以及作为其他实体集合属性的实体。然而，有时你只需要一个基本类型或嵌入类型的集合。例如，一个员工可能有多个电话号码和地址。你可以添加二三个电话号码和二三三个地址，为什么要限制它呢？这并没有违反数据库范式，而且符合良好的面向对象设计实践。根据顺序对你是否重要，拥有电话号码和地址的 `List` 或 `Set` 更有意义。在 JPA 中，你使用 `@javax.persistence.ElementCollection` 注解来映射一个基本或嵌入类型集合的字段。

`@ElementCollection` 有一个 `targetClass` 属性，在某些情况下可能需要也可能不需要。它指定了存储在集合中的元素类型。如果你使用带注解的集合（你应该极少这样做，甚至永远不要这样做，因为是不安全的），你必须指定 `targetClass` 属性。然而，只要你使用泛型（如 `List<String>` 或 `Set<Address>`），JPA 提供程序就可以自动发现元素类型（String，Address），你不需要指定 `targetClass` 属性。`fetch` 属性指示是否应该从数据库中懒加载地获取集合值，默认为 `FetchType.LAZY`。

你现在可能在好奇之前描述的关于嵌入类型的限制：它们必须存在于与其包含的实体相同的表中。嗯，这只是故事的一部分。

如果它们是集合属性的一部分，它们可能存在于单独的表中。在这种情况下，集合默认存储在一个表中，该表名等于包含它的实体的表名后加上下划线，然后是属性名。还会根据类型和属性名对列名做出某些假设。以 `Employee` 实体为例。

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
    public long getEmployeeId() { ... }

    public void setEmployeeId(long id) { ... }

    @Basic
    public String getFirstName() { ... }

    public void setFirstName(String firstName) { ... }

    @Basic
    public String getLastName() { ... }

    public void setLastName(String lastName) { ... }

    @Basic
    public List<String> getPhoneNumbers() { ... }

    public void setPhoneNumbers(List<String> phoneNumbers) { ... }

    @ElementCollection
    public Set<Address> getAddresses() { ... }

    public void setAddresses(Set<Address> addresses) { ... }
}
```

在这些默认情况下，Employee 的电话号码假设位于 `Employee_Phone` 中，并有一个名为 `EmployeeId` 的外键。Employee 的地址假设位于 `Employee_Address` 中，同样带有 `EmployeeId` 外键。然而，你之前创建的 `Address` 类是一个可嵌入类型，所以你可以对其进行自定义：

```java
@Entity
public class Employee {

    ...

    @ElementCollection
    @Fetch(fetch = FetchType.EAGER)
    @CollectionTable(name = "Employee_Phone", joinColumns = @JoinColumn(name = "Employee", referencedColumnName = "EmployeeId"))
    @OrderColumn(name = "Priority")
    public List<String> getPhoneNumbers() { ... }

    public void setPhoneNumbers(List<String> phoneNumbers) { ... }

    @ElementCollection
    @Fetch(fetch = FetchType.LAZY)
    @CollectionTable(name = "Employee_Address", joinColumns = @JoinColumn(name = "Employee", referencedColumnName = "EmployeeId"))
    @AttributeOverrides({
        @AttributeOverride(name = "street", column = @Column(name = "Street")),
        @AttributeOverride(name = "city", column = @Column(name = "City")),
        @AttributeOverride(name = "state", column = @Column(name = "State")),
        @AttributeOverride(name = "country", column = @Column(name = "Country"))
    })
    public Set<Address> getAddresses() { ... }

    public void setAddresses(Set<Address> addresses) { ... }
}
```

如此处映射，`Employee` 实体位于 MySQL 架构：

```sql
CREATE TABLE Employee (
  Employee BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
  FirstName VARCHAR(50) NOT NULL,
  LastName VARCHAR(50) NOT NULL
) ENGINE = InnoDB;

CREATE TABLE Employee_Phone (
  Employee BIGINT UNSIGNED NOT NULL,
  Priority SMALLINT UNSIGNED NOT NULL,
  Number VARCHAR(20) NOT NULL,
  CONSTRAINT Employee_Phone_Employee FOREIGN KEY (Employee)
  REFERENCES Employee(EmployeeId) ON DELETE CASCADE
) ENGINE = InnoDB;

CREATE TABLE Employee_Address (
  Employee BIGINT UNSIGNED NOT NULL,
  Street VARCHAR(100) NOT NULL,
  City VARCHAR(100) NOT NULL,
  State VARCHAR(100) NULL,
  Country VARCHAR(100) NOT NULL,
  PostalCode_Code VARCHAR(100) NOT NULL,
  PostalCode_Suffix VARCHAR(5),
  CONSTRAINT Employee_Address_Employee FOREIGN KEY (Employee)
  REFERENCES Employee(EmployeeId) ON DELETE CASCADE
) ENGINE = InnoDB;
```

## 持久化键值对 Map

尽管其名称暗示它仅适用于集合（Collection）属性，但 `@ElementCollection` 也可以将 Map 标记为持久化。Map 属性始终与键和值存储在同一张表中，这与 Collection 属性的默认情况相同；你也可以使用 `@CollectionTable` 自定义指定存储 Map 值的列名，并使用 `@javax.persistence.MapKey` 来指定存储 Map 键的列名。Map 属性也应该使用泛型，但如果由于某些原因你无法使用，可以使用 `@ElementCollection` 的 `convert` 属性来指定值类，并使用 `@javax.persistence.MapKey` 来指定键类。

键和值可以是任何基本类型，包括枚举类型（enum）和时间临时类型（temporal types），以及任何需要转换器的类型。对于键或值为可嵌入类型（embeddable types）的 Map 属性，可以使用 `@Embedded` 注解。枚举类型对于 Map 值遵循与 `@Enumerated` 注解相同的语义，对于键则遵循 `@javax.persistence.MapKeyEnumerated` 注解的语义。同样，你可以使用通常的 `@Temporal` 对值以及使用 `@javax.persistence.MapKeyTemporal` 对键来自定义时间临时类型的语义。

使用 Map 属性是存储编译时未知的补充实体属性（作为自定义字段）的一种极佳方法。以下新的 Employee 属性及其映射的表进行了演示。

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

    public void setExtraProperties(Map<String, String> extraProperties) { }
}
```

```sql
CREATE TABLE Employee_Property (
  Employee BIGINT UNSIGNED NOT NULL,
  KeyName VARCHAR(100) NOT NULL,
  Value VARCHAR(255) NOT NULL,
  CONSTRAINT Employee_Property_Employee FOREIGN KEY (Employee)
  REFERENCES Employee(EmployeeId) ON DELETE CASCADE
) ENGINE = InnoDB;
```



# 将实体存储在多张表中

与不寻常的情景不同，你可以将一个实体持久化到多张表中。不要将其与集合或 Map 属性存储在单独表中的概念混淆——后者是良好规范形式的预期做法。相反，这种特定场景实际上通过将实体的基本属性存储在单独的表中破坏了规范式。在一个荒谬的示例中，`Employee` 的姓必须存储在表 `Employee1` 中，而他的名则存储在表 `Employee2` 中。这通常是遗留数据库、为了对象关系映射而事后改进设计不当的数据库，或实体超过了底层数据库供应商在单表中所允许的列数的症状。

默认情况下，实体的所有非集合、Map 属性都被认为存储在主表中。这体现在 `@Table` 注解中，或者在没有 `@Table` 的情况下，体现在与实体同名的表中。如果实体的某些属性存储在次要表中，你应该使用 `@javax.persistence.SecondaryTable` 注解它，以指定名称和（可选的）其他细节。如果实体有多个次要表，可以使用 `@javax.persistence.SecondaryTables` 组合多个 `SecondaryTable` 注解。然后，在整个实体中，每个属性都必须使用 `@Column` 注解来指示它属于哪张表。`@Id` 属性必须始终留在主表中。

假设次要表有一个与主表主键列同名且同类型的列，该列应该是次要表的主键。你可以在 `@SecondaryTable` 注解中自定义此列的细节。

虽然 `Advanced-Mappings` 项目中没有演示将实体映射到多张表，但在这种情况下，`Employee` 实体可能像下面所示：

```java
@Entity
@Table(name = "Employee")
@SecondaryTable(name = "Employee2", pkJoinColumns = {
    @PrimaryKeyJoinColumn(name = "Employee", referencedColumnName = "EmployeeId")
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

    public void setLastName(String lastname) { ... }
}
```

# 编程触发器

在很大程度上，你过去可能使用过的关系型触发器应该作为业务逻辑存在于你的服务中。这种从数据库中移除业务逻辑是将应用程序从其存储机制中完全抽象化的最后一步，并允许你根据需要轻松切换存储机制。同样，它强化了这种观点：数据库仅仅是实现这一目标的手段。然而，有时你的实体可能需要你自己的持久化逻辑。经典的例子是更新与版本和审计相关的字段。（尽管你可能只是想让 Spring Data 为你处理这些。）尽管这与映射密切相关，但 JPA 允许你向实体添加特殊注解，以定义编程触发器。

## 在 CRUD 操作之前和之后执行

你可以通过注解方法来定义 CRUD 操作之前和之后的触发器。重要的一点是，使用 JPA 时，你实际上并不一定需要调用 `merge` 来更新实体。因此，当实体通过突变改变时，触发器就会触发。

不同的触发器注解如下：

- `@PrePersist`：在实体持久化之前调用。
- `@PostPersist`：在实体持久化之后立即调用。
- `@PreUpdate`：在实体更新之前调用。
- `@PostUpdate`：在实体写入数据库之后调用。
- `@PreRemove`：在实体被标记为删除时调用。
- `@PostRemove`：在实体实际删除后调用。

一个触发器可以是多个事件的触发器（例如，它可以同时注解 `@PrePersist` 和 `@PreUpdate`），但一个实体对于特定事件不能超过一个注解方法。这包括继承的触发器方法，这意味着对于从映射父类继承的实体，例如 `@PostRemove` 方法。但这不会禁用该方法在其他事件中被调用。

触发器方法必须返回 `void` 且没有参数。它们可以任意命名，可以是公共、保护、包私有或私有的，但不能是静态的。为了防止异常行为，它们不应该调用 `EntityManager` 或 `Query` 方法或访问任何其他实体。如果触发器抛出异常，事务将回滚。（因此，你可以使用触发器方法防止非法修改。）

你创建的 `Person` 实体演示了使用所有不同的触发器方法来记录实体的生命周期。

```java
@Entity
public class Person {
    private static final Logger log = LogManager.getLogger();

    @PostLoad
    void readTrigger() {
        log.debug("Person entity 已读取.");
    }

    @PrePersist
    void beforeInsertTrigger() {
        log.debug("Person entity 即将插入.");
    }

    @PostPersist
    void afterInsertTrigger() {
        log.debug("Person entity inserted into database.");
    }

    @PreUpdate
    void beforeUpdateTrigger() {
        log.debug("Person entity just updated by call to mutator method.");
    }

    @PostUpdate
    void afterUpdateTrigger() {
        log.debug("Person entity just updated in the database.");
    }

    @PreRemove
    void beforeDeleteTrigger() {
        log.debug("Person entity about to be deleted.");
    }

    @PostRemove
    void afterDeleteTrigger() {
        log.debug("Person entity deleted from database.");
    }
}
```

## 实体监听器

实体监听器与你刚刚阅读的触发器方法密切相关。实体监听器是一种用于在实体类之外定义触发方法的构造结构。这些方法被称为外部触发方法或外部生命周期事件处理器，与你刚刚学到的内部触发方法相比，后者是作为实体类或其子类的一部分存在的。外部触发方法允许你将这些逻辑与实体类分离。实体监听器必须具有公共的无参构造函数，并定义之前描述的任何或所有触发方法。然而，有几个细微的差别：

- 在实体监听器中定义的触发方法必须有一个参数：引起生命周期事件的实体。你可以让参数的类型变得非常模糊（一个映射的父类甚至是 `Object`），也可以非常具体（你使用的特定实体类型）。
- 实体监听器像内部触发方法一样从映射的子类继承，但它们不会重写已继承的实体监听器。这意味着你可以让同一个实体的特定生命周期事件执行多个触发器方法。

在执行触发器方法时，提供程序首先调用所有外部触发方法，然后调用所有内部触发方法。实体监听器中的外部触发方法从映射子类类谱系中的最高点开始执行，并在实际实体类处完成。你还可以定义在所有其他监听器之前执行的默认实体监听器。这些实体监听器适用于应用程序任何地方的所有实体，你只能在映射文件（如 `orm.xml`）中定义默认实体监听器。

编写一个实体监听器类非常简单，只需创建一个类并向其添加触发方法即可。该类不需要实现任何接口或扩展任何父类。（不过，它当然可以实现或扩展其他对你非常有帮助的类型）。在你创建实体监听器后，必须使用 `@javax.persistence.EntityListeners` 注解将其附加到实体上。你可以将此注解放在实体类或映射的父类上，以便将监听器或多个监听器附加到该实体类或映射父类上，例如：

```java
@EntityListeners({ Listener1.class })
@MappedSuperclass
public abstract class AbstractEntity {
}

@EntityListeners({ Listener2.class, Listener3.class })
@Entity
public class ConcreteEntity extends AbstractEntity {
}
```

如果你创建了一个扩展了映射父类的实体，但不想继承映射父类的实体监听器，可以使用 `@javax.persistence.ExcludeSuperclassListeners` 注解标记该实体。你也可以对映射的父类使用 `@ExcludeSuperclassListeners`，以停止其及其子类对该父类监听器的继承。同样，你可以对实体或映射父类使用 `@javax.persistence.ExcludeDefaultListeners`，以排除其及其子类的所有默认监听器。

# 完善客户支持应用程序

通过你在本章中学习的工具，你可以对你在整本书中一直编写的客户支持应用程序进行许多改进。首先，你可以停止使用 `Ticket` 作为 `TicketEntity` 的 DTO，完全删除 `TicketEntity`，并开始直接将 `Ticket` 作为实体。使用你在本章之前创建的 `InstantConverter` 也是可能的。

你还可以定义 `Tickets` 和 `Attachments` 之间的关系，这样当你检索 `Ticket` 实体时，可以自动检索票据。提到附件，你现在可以使用连接表和与 `Ticket` 类似的与 `Attachment` 的关系为 `TicketComments` 添加附件。你还可以直接将 `UserPrincipal` 关联到 `Ticket` 或 `TicketComment`。最后，你可以确保 `Attachment` 的内容是延迟加载的，这样在列出票据及其注释上的附件时，就不会加载可能数百兆字节的数据。可以从 wrox.com 下载站点下载的 `Customer-Support-v18` 项目实现了所有这些功能。

## 映射附件集合

由于你现在对 `Tickets` 和 `TicketComments` 都使用 `Attachments`，`Attachment` 实体不再需要 `ticketId` 属性，相应的表也不再需要 `TicketId` 列。使用 `create.sql` 中的以下连接表将 `Attachments` 与 `Tickets` 和 `TicketComments` 关联。

```sql
USE CustomerSupport;

CREATE TABLE Ticket_Attachment (
    SortKey SMALLINT NOT NULL,
    TicketId BIGINT UNSIGNED NOT NULL,
    AttachmentId BIGINT UNSIGNED NOT NULL,
    CONSTRAINT Ticket_Attachment_Ticket FOREIGN KEY (TicketId)
    REFERENCES Ticket (TicketId) ON DELETE CASCADE,
    CONSTRAINT Ticket_Attachment_Attachment FOREIGN KEY (AttachmentId)
    REFERENCES Attachment (AttachmentId) ON DELETE CASCADE,
    INDEX Ticket_OrderedAttachments (TicketId, SortKey, AttachmentId)
) ENGINE = InnoDB;
```

```sql
CREATE TABLE Ticket_Comment_Attachment (
    SortKey SMALLINT NOT NULL,
    CommentId BIGINT UNSIGNED NOT NULL,
    AttachmentId BIGINT UNSIGNED NOT NULL,
    CONSTRAINT Ticket_Comment_Attachment_Comment FOREIGN KEY (CommentId)
    REFERENCES TicketComment (CommentId) ON DELETE CASCADE,
    CONSTRAINT Ticket_Comment_Attachment_Attachment FOREIGN KEY (AttachmentId)
    REFERENCES Attachment (AttachmentId) ON DELETE CASCADE,
    INDEX Comment_OrderedAttachments (CommentId, SortKey, AttachmentId)
) ENGINE = InnoDB;
```

如果你一直在运行之前的版本的 Customer Support，则需要迁移数据。以下语句将处理这种情况：

```sql
USE CustomerSupport;

CREATE TABLE Ticket_Attachment (
    SortKey SMALLINT NOT NULL,
    TicketId BIGINT UNSIGNED NOT NULL,
    AttachmentId BIGINT UNSIGNED NOT NULL,
    CONSTRAINT Ticket_Attachment_Ticket FOREIGN KEY (TicketId)
    REFERENCES Ticket (TicketId) ON DELETE CASCADE,
    CONSTRAINT Ticket_Attachment_Attachment FOREIGN KEY (AttachmentId)
    REFERENCES Attachment (AttachmentId) ON DELETE CASCADE,
    INDEX Ticket_OrderedAttachments (TicketId, SortKey, AttachmentId)
) ENGINE = InnoDB;

CREATE TABLE Ticket_Comment_Attachment (
    SortKey SMALLINT NOT NULL,
    CommentId BIGINT UNSIGNED NOT NULL,
    AttachmentId BIGINT UNSIGNED NOT NULL,
    CONSTRAINT Ticket_Comment_Attachment_Comment FOREIGN KEY (CommentId)
    REFERENCES TicketComment (CommentId) ON DELETE CASCADE,
    CONSTRAINT Ticket_Comment_Attachment_Attachment FOREIGN KEY (AttachmentId)
    REFERENCES Attachment (AttachmentId) ON DELETE CASCADE,
    INDEX Comment_OrderedAttachments (CommentId, SortKey, AttachmentId)
) ENGINE = InnoDB;

ALTER TABLE Attachment DROP TicketId;

USE CustomerSupport;

CREATE TABLE minSortKeys AS
SELECT min(SortKey) as SortKey, TicketId
FROM Ticket_Attachment
GROUP BY TicketId;

UPDATE Ticket_Attachment
SET SortKey = minSortKeys.SortKey + 1
FROM minSortKeys
WHERE Ticket_Attachment.TicketId = minSortKeys.TicketId;

DROP TABLE minSortKeys;
```



如果你创建了一个扩展了映射父类的实体，但不想继承映射父类的实体监听器，可以使用 `@javax.persistence.ExcludeSuperclassListListeners` 注解标记该实体。你也可以对映射的父类使用 `@ExcludeSuperclassListListeners`，以停止其及其子类对该父类监听器的继承。同样，你可以对实体或映射父类使用 `@javax.persistence.ExcludedDefaultListeners`，以排除其及其子类的所有默认监听器。

映射 `Ticket-Attachment` 和 `TicketComment-Attachment` 关系。首先，`Ticket` 不再有通过名称检索附件的方法。以下映射连接了 `Ticket` 和实体：

```java
@OneToMany(fetch = FetchType.LAZY, cascade = CascadeType.ALL, orphanRemoval = true)
@JoinTable(name = "Attachment",
    joinColumns = { @JoinColumn(name = "TicketId") },
    inverseJoinColumns = { @JoinColumn(name = "AttachmentId") })
@OrderColumn(name = "SortKey")
@XmlElement(name = "attachment")
@JsonProperty
public List<Attachment> getAttachments() {
    return this.attachments;
}
```

而以下映射连接了 `TicketComment` 与其附件：

```java
@OneToMany(fetch = FetchType.EAGER, cascade = CascadeType.ALL, orphanRemoval = true)
@JoinTable(name = "Attachment",
    joinColumns = { @JoinColumn(name = "CommentId") },
    inverseJoinColumns = { @JoinColumn(name = "AttachmentId") })
@OrderColumn(name = "SortKey")
@XmlElement(name = "attachment")
@JsonProperty
public List<Attachment> getAttachments() {
    return this.attachments;
}
```

这种更改的一个内部变化是改进了 `DefaultTicketService` 的简单性。你不再需要转换 DTO，并且消除了大量的代码。你可以在下载的项目中查看重构后的服务以及更新后的控制器和视图。

# 使用加载时织入懒加载简单属性

现在，工单及其评论都可以包含附件，这导致仅通过查看工单就会无谓地加载大量数据。如果一个工单有几个 10MB 的附件，而每条评论也有几个 10MB 的附件，那么一个工单可能会加载数百兆的未使用数据。这将是一个巨大的性能问题。你真正需要做的是加载附件的内容。

```java
@Lob
@Basic(fetch = FetchType.LAZY)
@XmlSchema(name = "base64Binary")
@JsonProperty
public byte[] getContents() {
    return this.contents;
}
```

然后在 `DefaultTicketService` 中，你只在获取单个工单（为了下载）时才加载这些内容：

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

然而，这并没有那么简单。懒加载对于 `Map` 和 `Collection`（`List` 和 `Set`）属性是自动工作的，因为 Hibernate ORM 带有这些接口的代理实现，当 `Map` 或 `Collection` 以某种方式使用时（被计算、迭代等），它们会运行必要的查询来加载数据。要让你使用 `byte[]` 或 `String`、或 `@OneToOne` 或 `@ManyToOne` 属性来加载简单属性，Hibernate 必须对实体的字节码进行插入，以便拦截这些属性。在没有配置的情况下，它无法做到。

首先，你必须设置一个能够进行字节码插入的环境。你有三种方法来实现：

- 向 JVM 挂载 Java agent（参见 `java` 命令的 `-agent` 参数），它使用类转换器来检查并转换由 JVM 中的类加载器加载的所有类。不过，对于应用服务器或 Servlet 环境来说，这有点太重了。你需要适用于单个应用程序的方法。
- 使用 Hibernate 的 `org.hibernate.tool.instrument.InstrumentTask`（可以在你的 Ant 脚本中或通过 Maven 的 Ant 插件使用）。该任务在构建时（在部署应用程序之前编译之后）修改你的实体的字节码。其他的 O/RM 也提供了类似的在构建时装饰字节码的机制。
- 使用加载时字节码织入（load-time bytecode weaving）。你在 `Customer-Support-v18` 项目中看到了这种最终方法。

# 72 | 第 24 章 创建高级映射和自定义数据类型

Spring Framework 的加载时织入功能可以在类从其类文件加载时，通过一个可插件的 `org.springframework.instrument.classloading.LoadTimeWeaver` 实现类来对类进行转换。回退实现是如前所述使用 Java agent 的一种实现，但这并不理想。更好的选项是使用利用容器提供的可插入 `ClassLoader` 的织入器。

Glassfish、Jboss、WebLogic 和 Websphere 都具有 Spring 可以利用的可插入 `ClassLoaders`。在 Tomcat 8.0 之前，你可以告诉 Tomcat 使用一个特殊的（由 Spring 提供的）扩展了默认 Tomcat `ClassLoader` 的 `ClassLoader`。然而，Tomcat 8.0 提供了一个 Spring 可以自动使用的 `ClassLoader`。

配置 Spring Framework 的加载时织入仅需向 `RootContextConfiguration` 中添加 `@org.springframework.context.annotation.EnableLoadTimeWeaving`。它会自动检测并使用 Tomcat 的可插入 `ClassLoader`。让 Hibernate ORM 使用此加载时织入器需要额外的 Hibernate 属性。

```java
@EnableLoadTimeWeaving
public class RootContextConfiguration implements AsyncConfigurer, SchedulingConfigurer, TransactionManagerConfig {

    @Bean
    public LocalContainerEntityManagerFactoryBean entityManagerFactoryBean() {
        properties.put("hibernate.ejb.use_class_enhancer", "true");
    }
}
```

你必须考虑的最后一点是实体的 XML 和 JSON 序列化。无论你如何对这些类进行插入（静态使用 agent 或动态加载时织入），Hibernate 都可以为你的实体添加任意数量未指定的字段和方法。这是因为它们不会干扰你对这些实体的正常使用，JAXB（你用于 XML 序列化）和 Jackson Data Processor（你用于 JSON 序列化）不知道如何处理这些字段和方法。解决方案是告诉 JAXB 和 Jackson 默认忽略实体的属性，通过在你想要序列化的属性上添加 `@XmlAccessor` 和 `@JsonIgnore`，并从不想序列化的属性上移除 `@XmlTransient` 和 `@JsonIgnore`。

```java
@XmlAccessorType(XmlAccessorType.NONE)
@JsonAutoDetect(createVisibility = Visibility.NONE,
    fieldVisibility = JsonAutoDetect.Visibility.NONE,
    getterVisibility = JsonAutoDetect.Visibility.NONE,
    isGetterVisibility = JsonAutoDetect.Visibility.NONE,
    setterVisibility = JsonAutoDetect.Visibility.NONE)
public class Ticket implements Serializable {

    @XmlElement
    @JsonProperty
    public long getId() { ... }
}
```

```java
@XmlAccessorType(XmlAccessorType.NONE)
@JsonAutoDetect(...)
public class TicketComment implements Serializable {

    @XmlElement
    @JsonProperty
    public long getId() { ... }
}
```

```java
@XmlAccessorType(XmlAccessorType.NONE)
@JsonAutoDetect(...)
public class Attachment implements Serializable {

    @XmlElement
    @JsonProperty
    public long getId() { ... }
}
```



在你检查了 Customer Support 应用程序的所有更改后，编译项目，从 IDE 启动 Tomcat，并在浏览器中访问 `http://localhost:8080/support`。登录，创建一个或两个工单，并添加带有附件的评论以查看其运行情况。如果你在 `TicketController` 的 `view/{ticketId}` 中设置断点，你会发现工单或工单评论上的任何附件内容均为 `null`。只有在通过 `attachment/(attachmentId)` 方法下载时，内容才会被加载。

> **注意** 你可能会发现 RESTful 和 SOAP Web 服务不再工作了。这是因为工单需要 `UserPrincipal` 且没有它将无法保存。你将在第 28 章学习 Web 服务安全时修复这个问题。

### 总结

在本章中，你学习了关于 JPA 映射实体所需的几乎所有知识。你探索了如何创建属性转换器来处理非标准类型，使用 `@Embeddable` 和 `@Embedded` 在实体中嵌入 POJO，以及在实体之间创建自动或懒加载的关系。你还了解了如何对实体进行版本控制并创建通用实体祖类、向实体添加基本值和嵌入值的 `Collections` 和 `Maps`、将实体存储在多个表中，最后在 Java 代码中创建触发器，以便在各种 CRUD 操作之前或之后激活它们。你还进一步完善了 Customer Support 应用程序，去除了它的 DTO，简化了服务层，并用附件增强了工单评论。

到此，本书的第三部分结束。它没有涵盖 JPA 及其 API 的每一个细微细节，并省略了许多作为注解替代方案的 XML 映射语法。相反，它关注于你应用程序中每天需要的关键工具，并向你展示如何使用 Spring Framework、Spring Data JPA 和 Hibernate Search 等库更智能地使用这些工具。你可能仍然想了解关于 JPA 的少量知识（例如其 XML 映射语法），你现在只需下载规范文档即可轻松阅读并理解。

在本书的最后部分——第四部分中，你将探索如何使用 Spring Security 和相关工具保护你的应用程序免受未经授权的访问。

# 第四部分

# 使用 Spring Security 安全你的应用程序

- 第 25 章：简介 Spring Security
- 第 26 章：使用 Spring Security 进行用户验证
- 第 27 章：使用授权标签和注解
- 第 28 章：使用 OAuth 保护 RESTful Web 服务

# 第 25 章 介绍 Spring Security

## 本章内容

- 理解认证与授权
- 集成 Spring Security

## 本章的 WROX.COM 代码下载

本章没有代码下载。

## 本章的新 Maven 依赖

本章没有新的 Maven 依赖。请继续使用之前所有章节中引入的 Maven 依赖。

## 什么是认证？

当许多人想到认证（Authentication）时，他们想的是一种确定某人是否有权访问系统的机制。虽然这个过程与认证有关，但它实际上是授权（Authorization）。当你检查某人是否有权访问系统、建筑、文件或其他对象时，你实际上是在检查他们是否有权以请求的方式使用目标资源。授权的第一步是认证。公司的总裁可能被授权查看某些机密文件，但在你验证了他的身份之前，你无法确定他真的是总裁，还是一个冒充总裁的人。如果他是一个冒充者，你就不应该对他进行认证，因此不应该授予他授权。

你每天都会遇到认证和授权。当你早晨登录计算机网络时，这验证了你的身份并建立了你的身份标识。随后，你在网络上的权限将根据你的身份决定你有权访问哪些系统。如果你某个下午因为父母堵车而去学校接外甥，学校会检查你的身份证件以确保你是你本人。这就是认证。然后他们会检查女孩的档案，看看你的名字是否在被授权接送她的名单上。如果是，他们就会让你带她离开。如果你进入军事设施，他们会立即检查你的身份证件，确保你如你所说的身份。有时，他们还会进行进一步的检查，例如指纹或视网膜扫描，以更安全的方式认证你。他们可能会询问你“今日颜色”或“今日密码”。当他们确信你的认证有效时，他们会检查你是否有权访问正尝试访问的区域。

虽然认证和授权确实是必然且不可分的关系，但它们并不是同一个概念。在以后，你必须记住这其中的区别。在本章中，你将探索认证和授权涉及的细微差别和技术。你将查看 Spring Security，这是一个你在书的第四部分也是最后部分中使用的框架，以便为你的 Web 应用程序添加安全性。

## 集成认证

虽然认证并不一定是你集成到应用程序中的第一个组件，但它是用户参与受保护活动或访问应用程序中受保护资源之前必须采取的第一步。无论他们是通过第三方认证还是直接通过你的应用程序提供的机制进行认证，你的用户在你授权他们之前必须建立自己的身份。有几十种方法。有些比其他的更好，但大多数大致相当。使用哪种方法很大程度上取决于你具体的业务和安全需求，而且通常是由用户的意愿和技术水平驱动的。

## 匿名认证

匿名认证无疑是存在的最简单的认证形式。你可能在想：“匿名认证如何真的是认证呢？我以为认证是关于验证某人的身份吗？”这句话可能是正确的，但它完全取决于你对“身份”的定义。例如，你可能只需要断访问页面的浏览器与几分钟前访问该页面的浏览器是同一个。HTTP 会话通过 Web 会话 ID 实现这一点。因为浏览器每次访问你网站的页面时都会向服务器发送相同的会话 ID，你可以将这些请求关联起来，属于同一个身份。你可能不在乎那个访问者是谁。相反，你只想知道它是否是同一个人。这就是匿名认证的形式。

更广泛地说，你可以将匿名认证仅仅视为任何其他形式认证的缺失。许多 Web 应用程序在某种程度上支持匿名认证。例如，Twitter 允许你在不“登录”的情况下查看用户动态、趋势话题等。这就是匿名认证。然而，如果你想发推或关注其他用户，你必须以某种方式建立你的 Twitter ID 以进行认证。

许多网站允许你通过匿名认证执行某些基本任务并访问某些资源，只有当你想要执行受保护活动或访问受保护资源时，才需要更高层次的认证。对于互联网上的许多论坛也是如此，在这些论坛中你通常可以阅读任何帖子，但在认证后才能创建新帖子。其他网站仍然不需要认证——你可以用匿名认证做任何事情。你在整本书中所编写的客户支持应用程序就是一个不允许匿名认证的例子。

## 密码认证

毫无疑问，当你还是孩子时，你可能有一个某种堡垒、俱乐部或树屋并邀请朋友过来。在他们进入之前，你可能会向他们索要“密码”。如果没有允许访问的秘密单词或短语，他们就进不去。你不会向他们要用户名和密码，那太复杂了。你只想知道他们是否知道“密码”。最早的密码记录追溯到古罗马，古罗马军队使用被称为“口号”（watchwords）的密码来对他们遇到的军事成员进行认证。这很重要，因为军队规模之大，大多数成员并不认识彼此。区分敌人的唯一方法就是密码。如果这个人知道密码，他们就是朋友。如果不是，他们就是敌人。

这个系统的一个问题对你来说可能是显而易见的。罗马人最终发现了这一点，当他们面对罗马士兵时，他们会在罗马士兵有机会之前先索要密码。罗马士兵会立即报出密码，而没有意识到他正把密码交给了敌人，敌人随后可以恶意使用该密码。为了应对这个问题，密码的使用最终演变为使用密码和反密码（counter-passwords）。在第二次世界大战期间，美国第 11 空兵师在诺曼底战役使用了密码。空伞兵会大喊“闪电”（flash）作为挑战，部队会用“雷鸣”（thunder）作为回答。通过这种方式，空伞兵和部队相互建立了他们作为美国人的身份。

这种密码/反密码的方法与现代涉及应用程序的方法非常相似，其中用户在提供认证凭证之前，期望有一个 HTTPS 证书来确认网站的身份。如果用户将凭证提供给伪装成该身份的恶意网站，该网站就可以使用这些凭证造成伤害。双向认证有助于防止被称为中间人攻击的攻击。

计算机认证最早记录之一发生在 1961 年的 MIT。迭代时间共享系统（Iterative Time-Sharing System）有一个 `LOGIN` 命令，需要用户密码才能访问共享资源。从那时起，保护计算机和网站上的密码是一场无止境的战斗。20 世纪 70 年代，罗伯特·莫里斯（Robert Morris）在 UNIX 系统上提出了存储密码单向哈希值（hashes）而不是密码本身的想法。理论上，由于这些哈希值是不可逆的，黑客无法确定真实的密码并使用它们访问受保护的资源。存储单向哈希的技术一直持续今天，并且仍然是密码数据库泄露时保护用户密码最安全的方法。

当然，正如你可能已经知道的那样，哈希破解硬件和软件一直在不断进步，计算哈希值的算法也变得更加先进，以领先于黑客。现代密码破解计算机包含多达 30 个图形处理器（GPU）。GPU 通常用于显示器渲染图形所需的高强度数值计算，它比标准 CPU 更适合快速计算密码哈希值。此外，创建一个包含几十个 GPU 的系统比包含几十个 CPU 的系统容易得多。使用能够利用其能力的特殊软件，黑客每秒可以生成数十亿个密码。这使得黑客能够通过计算数十亿种可能的密码组合哈希值，并与密码数据库中的哈希值进行比较，对密码数据库发起字典攻击。今天的高级计算算法（如 BCrypt）被设计为非常缓慢并利用内存资源，使得基于 GPU 的攻击变得困难或不可能。

## 用户名和密码

你不太可能仅用密码来保护应用程序。单一密码意味着连接到你网站的任何人都具有相同的身份。这使得更改密码变得更加困难——你必须通知所有知道密码的人——并且降低了密码的安全性。无疑，你已经熟悉了分配用户名和密码的替代方法。每个用户都有一个其他用户不共享的唯一用户名，以及一个仅与该用户名关联的密码。

为了验证并建立其身份，用户必须在提示时输入用户名和密码。用户名是用户选择的值，例如名称、昵称或用户希望被识别的“句柄”（handle）。在其他情况下，用户名可能是用户的电子邮件地址，简化了原本需要同时存储用户名和电子邮件地址的系统。此外，用户名可能是系统分配的值，用户对其没有控制权。这在员工门户到 HR 资源系统（如电子工资单）中很常见。用户名通常是分配的员工 ID 号。银行使用客户的账号作为他们的用户名。

用户名的来源和含义对于用户名-密码认证的目的来说并不重要。通过这种类型的身份验证，你为每个用户分配了一个唯一身份。用户名充当身份，而密码则验证身份的真实性。用户名-密码认证是许多不同认证方法的基础，例如表单认证、操作系统认证等。在对网站、应用程序和系统进行身份验证时，你可能大部分或全部都在使用某种形式的用户名-密码认证。

## 基础认证和摘要认证

基础认证（Basic authentication）是一种 HTTP 认证协议，它能够支持主动认证请求和认证挑战。当受基础认证保护的资源收到缺少凭据的请求时，它会返回 HTTP 状态码 401 Not Authorized 以及 `WWW-Authenticate` 头部，如下示例所示：

```
HTTP/1.1 401 Not Authorized
Date: Sun, 25 Aug 2013 21:46:47 GMT
WWW-Authenticate: Basic="Multinational Widget Corp. Customer Support"
```

当浏览器收到此响应时，它会在模态窗口中提示用户输入用户名和密码，窗口包含来自 realm 头部参数的文本。如果用户取消，浏览器将取消请求。如果用户输入了用户名和密码，浏览器将重新发送原始请求，其中 `Authorization` 头部包含单词 `Basic`，后面跟着一个空格，以及用冒号分隔的 Base64 编码的用户名和密码。如果密码是 "John"，而浏览器对 "John:green" 进行编码并如下重新发送请求：

```
GET /support HTTP/1.1
Host: www.example.org
Authorization: Basic Bm9objpncmVbg==
```

服务器对头部进行解码，并在服务器端将用户名和密码与凭据数据库进行比较。尽管凭据是不正确的，服务器将继续返回 401 Not Authorized 和 `WWW-Authenticate` 头部。假设凭据检查通过，用户通过身份验证并返回正常响应。浏览器随后会缓存认证信息，并在对该资源的后续请求中重新发送它。通常，该缓存会在活动一段时间后过期。

基础认证的优点之一是它不需要登录页面、Cookie 或 HTTP 会话 ID。它也可以在无需 401 挑战响应且用户无需管理 `Authorization` 头部的情况下运行。用户可以将凭据直接嵌入 URL，或者浏览器或命令行工具（如 Wget 或 curl）会自动将凭据转换为 `Authorization` 头部。URL 可能像这样：`http://John:green@www.example.org/support`。

当然这在许多方面非常脆弱。首先，用户名和密码是以明文发送的（Base64 仅是一种编码算法，不采用任何哈希或加密）。网络上的任何恶意嗅探包都可以观察并捕获传输过程中的凭据。对方随后可以将这些凭据用于恶意目的。即使对方对凭据本身感兴趣，也可以简单地重放密码并访问受保护的资源。这些问题是严重的，但如果请求和响应通过 HTTPS 进行，这些就会消失。HTTPS 保护凭据免受嗅探（中间人）并防止重放攻击。然而，还有第三个问题：密码在服务器端通常以明文存储，这同样不可接受。大多数现代 Web 服务器提供了使用单向哈希存储密码的机制。

在 HTTPS 可选或不希望使用的情况下，服务器和客户端可以使用类似于摘要认证的协议来实现某种程度的安全。该协议使用 MD5 校验和来计算一系列单向哈希，因此密码不会在链上传输。此外，两个不同的随机数（服务器 nonce 和客户端 nonce）。

> **注意** nonce 是一种用于防止重放攻击的特殊令牌。每当客户端向服务器发送请求时，它都会生成一个随机令牌并将其包含在请求中。服务器存储 nonce 以确保两次请求不使用相同的 nonce。通常，nonce 与时间戳配对，这样服务器就不需要永久存储 nonce——超过特定时间的旧 nonce 总是会被拒绝。这要求 nonce 和时间戳被包含在哈希计算中，以便攻击者无法更改 nonce 或时间戳来重放请求。

这种交换通过以下请求和响应演示，假设用户名、域（realm）和密码与之前相同：

## 请求 1

```
GET /support HTTP/1.1
Host: www.example.org
```

## 响应 1

```
HTTP/1.1 401 Not Authorized
Date: Sun, 25 Aug 2013 21:46:47 GMT
WWW-Authenticate: Digest realm="Multinational Widget Corp. Customer Support"
algorithm="MD5-sess", qop="auth,auth-int"
nonce="d4d8dcd9f3fb0b204e9800998ec8427e"
opaque="66ffcd4df3b3f0ceb07195b60fa7991952"
```

## 请求 2

```
GET /support HTTP/1.1
Host: www.example.org
Authorization: Digest realm="Multinational Widget Corp. Customer Support"
username="John", qop="auth", uri="/support"
nonce="d4d8dcd9f3fb0b204e980099ec8427e"
opaque="66ffcd4df3b3f0ceb07195b60fa7991952"
nonce="93a95637e8635a4d912075cd62ea55530c0"
response="4b4b383cc8220fc105e81a952931c"
```

## 响应 2

```
HTTP/1.1 200 OK
Date: Sun, 25 Aug 2013 21:47:10 GMT
Content-Type: text/html;charset=UTF-8
Content-Length: 11485
...
```

## 请求 3

```
GET /ticket/list HTTP/1.1
Host: www.example.org
Authorization: Digest realm="Multinational Widget Corp. Customer Support"
username="John", qop="auth", uri="/support/ticket/list"
nonce="d4d8dcd9f3fb0b204e980099ec8427e"
opaque="66ffcd4df3b3f0ceb07195b60fa7991952"
nc="3611aece5c435219d208b613f5aa613f5aa957096"
response="456fd23109400477064caf992"
```

## 响应 3

```
HTTP/1.1 200 OK
Date: Sun, 25 Aug 2013 21:49:31 GMT
Content-Type: text/html;charset=UTF-8
Content-Length: 15817
...
```



由于 nonce 会发生变化且服务器会记住这些值一段时间，因此防止了重放攻击。密码永远不会在客户端之间传输，而是以哈希格式存储，从而保持了安全性。幸运的是，服务器会为你处理这些，如下：

第 25 章 介绍 Spring Security 程序员你不必担心这些细节。根据服务器环境，你只需要声明特定资源受基础认证（basic authentication）或摘要认证（digest authentication）的保护。然而，由于最近对 MD5 的多次攻击使其在很大程度上过时，摘要认证通常不是你应该依赖的东西。即使在 HTTPS 之上，你仍应尽可能使用摘要认证。请注意，尽管现代浏览器支持摘要认证，但

## 表单认证 (Form Authentication)

表单认证是你最熟悉的协议。它的实现非常简单：当客户端尝试访问受保护的资源时，服务器将通过 302 Found 或 307 Temporary Redirect 将客户端重定向到包含用户名和密码字段的不同页面。用户在表单中输入用户名和密码。如果凭据错误，服务器将继续将用户重回登录表单，告知登录尝试失败。如果凭据正确，服务器将用户带回原始目的地（或者如果行为良好，则返回应用程序主页）。这种你每天使用的身份验证机制没有什么特别强调的。与基础认证一样，凭据是以明文在 Web 上传输的，因此你应该尽可能利用 HTTPS 来保护这些凭据。

## Microsoft Windows 身份认证 (Microsoft Windows Authentication)

与基础、摘要和表单认证一样，Windows 身份认证要求用户提供用户名和密码。在这些情况下，主要的区别在于凭据是针对 Windows 域控制器而不是内部数据库进行检查。集成 Windows Authentication（IWA）使用 SPNEGO、Kerberos 或 NTLMSS 来捕获客户端机器上的 Windows 凭据，并在不需要密码的情况下安全地将其传递给服务器。当此生效时，该过程对用户来说是透明的。他们不会弹出窗口或登录表单来提供凭据，因为协议会自动处理 Windows 凭据。

然而，这在某些情况下才是可能的。通常，用户必须使用 Microsoft Internet Explorer。Mozilla Firefox 支持 NTLMSS，但前提是用户在 `network.ntlm-auth.trusted-site` 属性中配置站点，该属性包含用逗号分隔的可能请求 IWA 的信任站点列表。大多数用户在技术上并不足以进行此更改，因此 Firefox 通常不是一个选择。Google Chrome 支持 IWA，但安全设置比 Internet Explorer 更严格。站点必须在本地局域网（Local Intranet）区域获得资格后，Chrome 才会允许 IWA 继续。

当然，所有的 IWA 都假设用户从 Windows 机器连接，这在 10 年前要少得多。如今许多用户使用的是 MacOS 或 Linux 机器，无法提供 Windows 凭据。由于由于原因，集成 Windows 身份认证通常仅用于用户环境统一的企业内部资源。公共网站很少使用 IWA 进行用户认证。此外，当你无法保证所有用户环境都是运行支持浏览器的 Windows 机器时，你必须提供由 Windows 域控制器支持的备用方案。

> Simple GSSAPI Negotiation Mechanism (SPNEGO)、Kerberos 和 NT 命令行安全提供程序 (NTLMSSP) 是关于协议协商和挑战/响应认证的不同相关协议。你将在书中不会使用它们，因此进一步定义它们超出了范围。

## 客户端证书 (Client Certificates)

客户端证书认证是一种识别用户的方法。它不涉及用户名或密码，因此安全得多。事实上，客户端证书认证是最安全的身份验证协议之一。作为 SSL 协议的一部分，证书认证需要 HTTPS。当你通过 HTTPS 连接到服务器时，该服务器通过 SSL 证书进行身份识别。它展示由信任证书权威颁签的公钥，并使用其私钥对与浏览器的通信进行签名。客户端证书本质上是此的反向。

在“注册”期间（用户通常在此过程中创建用户名和密码），服务器告诉你的浏览器生成一对公钥/私钥对。浏览器将私钥安全地存储在用户的机器上，并将公钥传输给服务器。从以后，浏览器向服务器展示公钥用于身份识别，并使用私钥对与服务器的通信进行签名。使用此协议的缺点是用户无法使用新的或不同的计算机与你的网站进行身份验证。他们必须备份并恢复密钥对。然而，优点是增加了安全性：用户的凭据不会被轻易破解。黑客必须接管用户的计算机才能使用其凭据。

生物识别涉及从用户处获取指纹、声纹、虹膜扫描、DNA 或其他生物身份，并在用户每次进行身份验证时需要重新呈现该身份。大多数浏览器以某种方式支持生物识别，或使用供应商提供的、与所使用的生物识别硬件集成的插件。生物识别是一个极其复杂的话题，远远超本书的范围。

虽然智能卡和生物识别都是 Web 应用程序身份验证的可能解决方案，但它们通常用于验证进入建筑的人员或登录公司或政府计算机系统。

## 基于声明的身份验证 (Claims-Based Authentication)

到目前为止，你学习了可以可以直接在应用程序中实现的各种身份验证机制。而基于声明的身份验证是你*不需要*实现的机制。在基于声明的身份验证中，你的应用程序信任第三方应用程序代表你对用户进行验证。你既不需要需要需要这个第三方应用程序是如何执行身份验证过程的。如果你曾使用 Facebook 验证其他网站的身份，你就使用基于声明的身份验证。通常在基于声明的身份验证中，当你尝试访问应用程序中的受保护资源时，只需将他们重定向到第三方应用程序。验证成功后，他们将带着一个或多个断言其身份的声明返回给你。这些声明由第三方应用程序颁发，可以通过向应用程序发送回调请求来获取此类验证，如图 25-1 所示。许多不同的协议（如 OAuth 和 SAML）实现了基于声明的身份验证机制。你也可以将声明用于授权，这一点你将在本节稍后部分进行探索。

![](img/4677f981a0e1067137bb55a122f8498d_773_0.png)

在某些情况下，你的系统直接与第三方系统通信，用凭据交换声明。两个常见的例子是 Microsoft Windows 的 Active Directory 域验证和轻级目录访问协议 (LDAP)。直接基于声明的身份验证过程如图 25-2 所示。

![](img/4677f981a0e1067137bb55a122f8498d_774_0.png)

这看起来像是一个更简单、因此更理想的方法，但它并不总是最佳选择（或可用选项）。用户喜欢在在使用凭据访问特定的安全服务时，始终访问同一个登录页面所带来的安全感。考虑一下：如果一个网站要求你使用 Google 账户进行身份验证，你倾向于被重定向到 Google 网站登录，还是倾向于交给可能不可信的 Facebook？你对这个问题的回答将清楚为什么第一种方法是理想的方法。直接验证通常保留给高度信任的应用程序，并且通常只限于控制身份验证服务的同一组织或公司内部。

## 多因素身份验证 (Multi-Factor Authentication)

到目前为止的所有机制仅涉及一个身份验证因素。对于用户名-密码身份验证及其衍生机制，提供用户名和密码就是用户需要做的一切。对于证书验证，用户只需提供正确的客户端证书。生物识别、智能卡和基于声明的身份验证也是如此。在所有这些机制中，唯一的步骤就是成功验证用户。今天，许多 Web 应用程序要求或可以要求多因素身份验证 (MFA)。Gmail、Twitter、Facebook、Amazon.com、WordPress 等许多平台为用户提供了启用多因素身份验证的选项。

多因素身份验证要求用户执行两个或更多步骤来断言其身份。这可能包括提供客户端证书以及用户名和密码。更常见的是在提交用户名和密码后，许多网站向用户的已知手机手机发送发送包含特殊代码，用户必须在继续之前将该代码输入 Web 应用程序。

更安全的解决方案包括设备，例如带有简单 LCD 屏幕的钥匙令牌 (dongles) 或显示安全六到九位代码的手机 App，该代码使用随机生成器每 30 到 60 秒旋转一次。这些令牌包含一个高精度的时钟和一个出厂安装的随机种子，使得已知种子的服务器能够预测任何时刻显示的数字。手机 App 与令牌通信以协调显示正确的令牌。当用户输入其常规凭据（用户名和密码、证书等）时，会被要求输入其令牌或手机 App 中显示的数字。

尽管多因素身份验证的概念很简单，但它的安全优势是巨大的，且到目前为止应该是显而易见的。攻击者极难绕过多个因素。

## 理解授权 (Understanding Authorization)

多因素身份验证的概念很简单，但它的安全优势是巨大的，且到目前为止应该是显而易见的。攻击者极难绕过多个因素。

## 使用主体和身份 (Using Principles and Identities)

建立授权的第一步是表示用户。至少，主体 (Principal) 应该持有一个用户名，它也可以包含许多其他信息，例如法律姓名、出生日期、地址和电话号码。

思考你的用户将执行哪些活动。在论坛示例中，这些是你可能预期看到的活动：

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

有了这组活动，检查用户的授权与上一个示例没有太大区别：

```java
public void deleteMessage(long id) {
    if (security.user.hasActivity("DELETE_OTHER_MESSAGE") ||
        isOwnMessage() && security.user.hasActivity("DELETE_OWN_MESSAGE")
}
```



确定你需要哪些活动的最简单的方法可能是直接查看你服务类中的方法。很可能你为每个方法需要一个活动。方法名通常是其功能的指示，例如之前代码中的某些方法，可能需要两个活动。在这种情况下，删除自己的消息与删除另一个用户的消息是不同的活动。

虽然这种细粒度减少了应用程序重新编译的概率，但也增加了管理用户权限的工作量。在编辑用户时，你必须从许多权限列表中选择一个或多个权限。在一个包含数百个活动的非常大的系统中，这个列表对于每个用户来说很快就会变得难以管理。这并非绝对必要，但你可以采用“用户组”的概念，组内的用户继承执行该组可以执行的所有活动的能力。你可以通过简单用户所属的组来轻松更改许多用户可以执行的活动。如果你发现某个用户或某些用户需要不同的权限，只需将他们移动到不同的组即可。这与“角色”的概念几乎相同，不同之处组可以在运行时动态创建和更改，而不需要更改代码。

> **注意**：好的。角色？权限？组？它们之间真正的区别是什么？谁来决定这些术语？在本书的术语中，它们仅仅是不同的约定。你可以在内部为它们命名任何名称。无论你命名角色还是组并不重要，重要的是你如何使用它们。

定义组的一种方法是将它们制为主体（`Principals`）。通过一个设计用于处理所有活动的抽象 `Principal`，你可以扩展 `Principal` 来形成你的用户 `Principal` 和组 `Principal`。用户 `Principal` 随后可以将一个组 `Principal` 作为对象的属性（或者可能是一个组 `Principal` 列表，取决于你的需求）。这只是一个例子，有许多不同的方法来实现。

## 基于声明的授权

在此之前，你探索了基于声明（claims-based）的认证的概念。在基于声明的授权中，用户的身份包含了该用户拥有权限的活动。此类系统的示例是微软的 `Active Directory`（活动目录）。当你使用 Windows 域凭据在机器上进行身份验证时，域控制器会收集你的身份声明（用户名、姓名邮箱地址以及附加到你的域的其他信息）和你的授权声明（分配给你的域权限）。你所属的域组是你身份声明的一部分，然后你也会继承分配给这些组的权限。这是一种基于组合的认证和授权系统。

如果你选择基于声明的认证，你可能不需要使用声明授权。通常，你进行身份验证的第三方系统并不了解你的应用程序，因此所提供的声明授权对你的应用程序来说可能是无用的。在这些情况下，当用户的身份声明从身份验证系统返回后，你还需要额外执行一个步骤：你必须在你自己的系统中找到分配给来自身份验证系统的该身份的权限。

## 为什么使用 SPRING SECURITY？

在本书的剩余部分，你将学习如何使用 `Spring Security` 将安全性集成到你的应用程序中。虽然有很多 Java 框架可用，但 `Spring Security` 可能是 Web 应用中最流行的，而且作为一个 Spring 项目，它与 Spring Framework 无缝集成。请注意，正如完整的 Java EE 应用服务器可以提供 IoC、依赖注入和持久化提供者服务一样，它也可以提供完整的安全框架。然而，与第二、第三部分一样，这部分侧重于为那些不想或无法使用容器安全的应用程序提供一种容器安全的替代方案。

### 理解 Spring Security 基础

认证还通过 `Authorities` 方法提供用户的 `org.springframework.security.core.GrantedAuthorities`。如果你使用角色，`GrantedAuthority` 就可以是一个角色。你将始终使用的最终接口是 `org.springframework.security.core.AuthenticationProvider`，或者如果身份验证失败则抛出 `org.springframework.security.core.AuthenticationException`。安全性带有针对 CAS、JAAS、LDAP、OpenID、JDBC（使用表）等等的 `AuthenticationProvider` 实现。你也可以提供自己的实现。

## 使用 Spring Security 授权

你有几种方法在 `Spring Security` 中使用授权，这些方法并不是互斥的。一种方法是使用全局安全注解。这是最好的方法之一，因为可以在可以在服务内部强制执行安全，而不是在 UI 中。你将在接下来的章节中学习更多关于可以使用的注解以及如何使用它们。

另一种选项是在 `Spring Security` 中定义方法拦截规则。这些规则类似于面向切面编程（AOP）的切入点（join points）。与安全注解一样，你可以定义拦截你的服务的规则，这使其成为保护你代码授权的另一个具有吸引力的选项。取决于应用程序的复杂性，你可能会发现方法拦截规则比注解更容易设置。此外，如果你使用 XML 配置，可以在不重新编译的情况下更改方法拦截规则（这可能是你所想要的）。

你的最后一个选项是定义 URL 拦截规则。这是最简单的方法，但它有许多缺点。首先，它适用于 Web 应用程序而不适用于其他类型的应用程序。此外，如果你有多个 Web 接口（例如 Web、REST 和 SOAP），你必须为每个用户接口定义规则。不一致地定义这些规则很容易，在所有情况下，你都希望使用注解或配置规则来保护你的服务，将所有及未来的用户界面绑定到这些安全需求。即使你使用方法安全，通常也希望为登录和注销屏幕定义一些 URL 安全规则。

### 配置 Spring Security

明确，必须使用 Spring Framework 才能使用 `Spring Security`。`Spring Security` 的配置与 Spring Framework 的配置紧密相关，并大量利用 `ApplicationContext` 来管理其安全上下文。

在设置 `Spring Security` 时，你可以使用 XML、Java 或混合配置。Java 配置在某些方面是新的，它与 Spring Framework 的 Java 配置相似，但也有许多关键区别。一个区别是你你没有许多配置相关的注解（只有两个）。相反，你的 `@Configuration` 类实现了配置接口，这些接口的方法会被调用以程序方式设置你的安全上下文。这是因为虽然 Spring Framework 每个应用上下文中只有一个配置，但 `Spring Security` 每个应用上下文中可以有多个配置。

例如，在 Web MVC 上文中，你根据该上下文内的 URL 拥有一个、两个或几十个不同的安全上下文（security contexts）。每个上下文都需要单独的配置，因此你在 `@Configuration` 类中定义方法，使用 `Spring Security` 配置类来添加你需要的每个安全上下文。你将在接下来的章节中详细探讨这一点。更重要的是，由于 Java 配置比 Spring Framework 的 Java 配置冗长得多，你将看到同时使用 XML 和 Java 来编写每种配置。

### 总结

在这个简短的介绍章节中，你学习了认证（authentication）与授权（authorization）之间的区别，并理解了为什么有效的安全同时需要这两者。你探索了认证和授权可以采取的许多不同方法，例如用户名和密码认证、基本认证和摘要认证、表单认证、基于角色的授权以及基于活动的授权。最后，你结接触了 `Spring Security`，这是你在本书的剩余部分将使用的认证和授权框架。你学习了它的 `Authentication`、`GrantedAuthority` 和 `AuthenticationProvider` 接口，以及它们如何构成 `Spring Security` 运行的基础。你还快速查看了使用 `Spring Security` 授权服务以及在 Spring Framework 中配置 `Spring Security` 的不同方法。

在下一章中，你将创建第一个启用 `Spring Security` 的应用程序，并学习如何认证用户以满足各种需求。

## 第 26 章：使用 Spring Security 认证用户

### 本章内容

- 为你的应用程序添加 `Spring Security` 认证
- 使用表单登录（Form Login）、JDBC、LDAP 和 OpenID
- 防止会话固定（session fixation）并限制用户会话
- 在会话之间记住用户
- 创建自定义认证程序
- 缓解跨站请求伪造（CSRF）攻击

本章对应的代码下载

你可以在 `http://www.wrox.com/projavaforwebaps` 的 "Download Code" 标签页找到本章的 wrox.com 代码下载。本章的代码分为以下示例：

- Authentication-App 项目
- Customer-Support-v19 项目

## 本章新增的 MAVEN 依赖

除了之前章节引入的 Maven 依赖项外，你还需要以下 Maven 依赖项：

```xml
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-web</artifactId>
  <version>3.2.0.RELEASE</version>
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

你不再需要以下依赖项，因为 `Spring Security` 在其发行版中包含了 BCrypt 实现。

```xml
<dependency>
  <groupId>org.jmindrot</groupId>
  <artifactId>jbcrypt</artifactId>
  <version>0.3m</version>
</dependency>
```

## 选择和配置认证程序

你必须选择的内容之一是决定使用哪种机制来认证你的用户。正如你在上一章中看到的，`Spring Security` 内置了支持多种不同机制的 `AuthenticationProvider` 实现。你可以创建自己的实现，使可能性变得无限。在你选择好一种机制后，你只需要配置它并设置你的安全上下文。在本节中，你将探索 `Spring Security` 认证的内置提供程序和配置。在下一节中，你将创建自己的 `Authentication` 实现以执行更自定义的认证步骤。

> **注意**：如果你没有阅读第 5 章，并且对 `HttpSessions`、会话标识符或会话固定攻击和其他会话漏洞不熟悉，强烈建议你在继续之前回去重读第 5 章。本章中提到的某些概念，否则你可能无法理解。

### 配置用户详情提供者

你可以使用的最简单的 `AuthenticationProvider` 实现之一是 `org.springframework.security.authentication.DaoAuthenticationProvider`。该提供器的核心概念是它使用一个数据访问对象（DAO），以 `org.springframework.security.core.userdetails.UserDetailsService` 实现的形式，通过用户名检索 `org.springframework.security.core.userdetails.UserDetails` 对象。

`UserDetails` 对象包含有关用户的信息，例如用户名和密码、`GrantedAuthorities`，以及用户是否被启用、过期和被锁定。这些要素共同构成了一个通用的认证程序。与其担心认证用户的细节，你只需提供一种检索用户的机制，让 `Spring Security` 来管理认证过程。当然，你也可以从各种默认的 `UserDetailsService` 实现中选择。

开始使用 `DaoAuthenticationProvider` 最简单的方法是采用 `framework.security.provisioning.InMemoryUserDetailsManager`。这个简单的实现并非用于生产，但它非常适合简单的测试和演示——因为 `Spring-Application` 项目始终可以从 wrox.com 的代码片段中下载。

在配置 `Spring Security` 与配置 Framework 之间存在一个关键区别。`Spring Security` 通过一系列过滤器（Filters）运行，这些过滤器在后台处理各种细节。这是为了确保你的应用程序能够被正确拦截并根据需要采取适当的安全措施。由于此，你不需要在独立的 `DispatcherServlet` 中配置 `Spring Security`。

### 设置 Spring 过滤器

`Spring Security` 通过一系列过滤器运行，这些过滤器在后台处理各种细节。这是为了确保你的所有应用程序能够被正确拦截并根据需要采取适当的安全措施。由于此，你不需要在独立的 `DispatcherServlet` 中配置 `Spring Security`。

- 处理 `Spring Security` 日志的过滤器
- 处理多租户决策的过滤器（在多租户应用程序中，尽早确定请求属于哪个租户）
- 以适当顺序的所有过滤器

在简单的 App 项目中，你没有使用任何过滤器，所以你不需要担心顺序。你将在下一节查看这一点。现在，创建一个扩展 `AbstractWebApplicationInitializer` 的类：

```java
public class SecurityBootstrap extends AbstractWebApplicationInitializer {
}
```

注意，该类没有任何字段或方法；因为你不需要。这也设置了会话跟踪。如果你选择不同的会话跟踪方式（URL 或 SSL），你需要重写 `getTrackingModes` 方法来指示这一点：

```java
public class SecurityBootstrap extends AbstractWebApplicationInitializer {
    @Override
    protected Set<SessionTrackingMode> getTrackingModes() {
        return EnumSet.of(SessionTrackingMode.SSL);
    }
}
```

然而，使用 bean 配置是最简单的解决方案，并适用于此目的。如果你没有使用 Java 配置，只需将 Spring 的 `DelegatingFilterProxy` 添加到部署描述符中。

```xml
<filter>
  <filter-name>springSecurityFilterChain</filter-name>
  <filter-class>org.springframework.web.filter.DelegatingFilterProxy</filter-class>
</filter>
```

```xml
<filter-mapping>
  <filter-name>springSecurityFilterChain</filter-name>
  <url-pattern></url-pattern>
  <dispatcher>ERROR</dispatcher>
  <dispatcher>REQUEST</dispatcher>
</filter-mapping>
```

现在 Spring 过滤器已经注册，你可以继续为应用程序配置 `Spring Security`。将此放在根上下文通常涉及向你创建并使用的 `RootContext` 中添加更多代码。然而，该类变得有点拥挤，并且安全配置最终可能会获取规模相当大，因此另一种且吸引力的方法是创建一个新的配置类并从 `RootContextConfiguration` 导入它。

```java
@ComponentScan(
    basePackages = "com.wrox.site",
    excludeFilters = {
```



@ComponentScan.Filter((Controller.class, ControllerAdvice.class))

}

)

@Import({SecurityConfiguration.class})

public class RootContextConfiguration implements

    AsyncConfigurer, SchedulingConfigurer, TransactionManagementConfigurer

```

```java

@Configuration

@EnableWebMvcSecurity

public class SecurityConfiguration extends WebSecurityConfigurerAdapter

{

    @Override

    protected void configure(AuthenticationManagerBuilder builder)

        throws Exception

    {

        builder

            .inMemoryAuthentication()

            .withUser("John")

            .password("password")

            .authorities("USER")

            .and()

            .withUser("Margaret")

            .password("green")

            .authorities("USER", "ADMIN");

    }

}

```

```java

@Override

public void configure(WebSecurity security)

{

    security.ignoring().antMatchers("/resource/**");

```

```java

@Override

protected void configure(HttpSecurity security) throws Exception

{

    security.authorizeRequests()

        .antMatchers("/signup", "/about", "/policies").permitAll()

        .antMatchers("/secure/**").hasAuthority("USER")

        .antMatchers("/admin/**").hasAuthority("ADMIN")

        .anyRequest().authenticated()

    .and().formLogin()

        .loginPage("/login").failureUrl("/login?error")

        .defaultSuccessUrl("/secure/")

        .usernameParameter("username")

        .passwordParameter("password")

```

# 752 | 第 26 章 使用 SPRING SECURITY 认证用户

```java

.permitAll()

.and()

    .logoutUrl("/logout").logoutSuccessUrl("/login/logout")

    .invalidateSession(true).deleteCookies("JSESSIONID")

    .and().csrf().disable();

}

```

这段代码中包含很多内容，让我们让我们将其拆解并逐部分进行检查。

有两个你应该了解的注解，它们非常相似：`@org.springframework.security.config.annotation.web.configuration.EnableWebSecurity` 和 `@org.springframework.security.config.annotation.servlet.configuration.EnableWebMvcSecurity`。第一个注解启用了 Spring Web 认证和授权功能。第二个注解也启用了与 Spring MVC 控制器的集成。除非你没有使用 Spring MVC，否则你应该始终使用带有 `@EnableWebWebSecurity` 或 `@EnableWebMvcSecurity` 的 `@Configuration` 类，该类必须实现或扩展 `org.springframework.security.config.annotation.web.WebSecurityConfigurer` 或 `org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter`。扩展 `WebSecurityConfigurerAdapter` 是一种简单得的方法，你没有理由不这样做。

`configure(AuthenticationManagerBuilder)` 方法设置了你应该用于认证用户的 `AuthenticationProvider`。你并不需要直接使用 `InMemoryUserDetails` 就可以使用内存中的用户数据库。Java 和 XML 配置为配置 `InMemoryUserDetailsManager` 提供了快捷方式。在这个方法中，你在内存中创建了两个用户并为他们分配了适当的 `GrantedAuthorities`。这虽然是一个授权细节，但有时很难防止这些细节泄露。

> 注意：你可能注意到 `configure (AuthenticationManagerBuilder)` 方法引用的是一个认证管理器（authentication manager），而书中提到的是认证提供者（authentication provider）。从技术上说，Spring Security 的认证能力位于 `org.springframework.security.authentication.AuthenticationManager` 的实现中。虽然你技术上可以实现此接口，但你不应该应该这样做。默认且唯一的实现 `org.springframework.security.authentication.ProviderManager` 会委托给一个或多个 `Authentication` 实现。这使得你有多种方式认证用户。在本节的后部分，你将看到此方面的示例：“记住我认证”。

`configure (WebSecurity)` 方法非常简单。在这种情况下，它防止了 Spring Security 出于安全考虑对（JavaScript、样式表、图像等）的访问。`configure (HttpSecurity)` 执行了大部分困难工作。首先，它定义了几个 URL 模式以及它们是如何受保护的。再次，这是一个授权细节，但必须设置最小级别的授权以让 Spring Security 要求用户登录。

# 选择并配置认证提供者 | 753

`permitAllAll` 调用指示 Spring Security 允许对 `/signup`、`/about` 和 `/policies` URL 的所有访问。`/secure/` URL 下的所有内容都需要用户拥有权限，而访问 `/admin/` 及其其下的所有内容需要 `ADMIN` 权限。任何其他请求都需要认证，无论权限如何。

接下来，调用 `formLogin` 开始通过表单登录配置用户名和密码认证的过程。它设置了登录表单应该显示的 URL；用户认证失败时跳转的 URL；登录表单中提交的用户名和密码的名称。调用 `logout` 配置了用户在注销后应触发注销的 URL。这两个地方的 `permitAll` 调用确保了用户可以在不认证的情况下登录和注销（出于显而易见的原因）。Java 配置默认启用了跨站请求伪造（CSRF）保护。（在 XML 配置中默认是禁用的。）CSRF 保护是一个复杂的课题，将在下一节中介绍，因此通过不使用调用 `csrf()` 后调用 `disable()` 禁用了它。

> 你可能好奇在 `configure(WebSecurity)` 中忽略 URL 与在 `configure(HttpSecurity)` 中允许所有 URL 之间的区别。忽略 URL 会让这些 URL 跳过 Spring 的内部过滤器。这很重要，因为你希望访问静态资源时尽可能快，并且

[789]
# 第 26 章 使用 SPRING SECURITY 认证用户

正如你在这里看到的，Java 配置使用了流式 API，这与 XML 配置形成了鲜明对比。这是出于需要，而非仅仅为了设计。它使得各种（有时是重复的）安全组件配置变得简单，你的 IDE 代码提示可以帮助确定每个组件的选项。以下是通过 `@Import` 从你的 `RootContextConfiguration`。

```xml

<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/security"

     xmlns:beans="http://www.springframework.org/schema/beans"

     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

     xsi:schemaLocation="http://www.springframework.org/schema/security

http://www.springframework.org/schema/security/spring-security-3.2.xsd

http://www.springframework.org/schema/beans

http://www.springframework.org/schema/beans/spring-beans-4.0.xsd">

  <authentication-manager>

    <authentication-provider>

      <user-service>

        <user name="John" authorities="USER" password="password" />

        <user name="Margaret" authorities="USER, ADMIN" password="green" />

      </user-service>

    </authentication-provider>

  </authentication-manager>

  <http security="none" resource="/resource/**" />

  <intercept-url patterns="/about" access="permitAll" />

  <intercept-url patterns="/policies" access="permitAll" />

  <intercept-url patterns="/login" access="permitAll" />

  <intercept-url patterns="/login" access="permitAll" />

  <intercept-url patterns="/logout" access="permitAll" />

  <intercept-url patterns="/secure/**" hasAuthority('USER') />

  <intercept-url patterns="/admin/**" access="hasAuthority('ADMIN')" />

  <form-login login-page="/login"

               login-processing-success-url="/login"

               authentication-failure-url="/loginerror"

               default-target-url="/secure/"

               username-parameter="username"

               password-parameter="password" />

  <logout logout-url="/logout"

        logout-success-url="/login?loggedOut"

        invalidate-session="true"

        delete-cookies="JSESSIONID" />

</http>

</beans>

```

# 设置会话固定攻击保护

你应该熟悉 HTTP 会话固定攻击的问题，以及这些攻击如何让你的用户面临账户网站被受攻击的风险。在第 5 章中你





## 选择并配置身份验证提供 | 755

探索了缓解这些攻击的方法。坦率地说，Spring Security 也自带了用于缓解这些攻击的工具。在 Servlet 3.1 之前，开发者不得不通过创建新的 session、将数据从一个 session 复制到另一个 session，然后失效旧的 session。Spring Security 使这项变得非常简单——只需简单的配置即可切换 session 行为。默认情况下，Spring Security 启用了 session 保护，因为 session 固定攻击是 Web 应用中的一个主要问题。Servlet 3.1 在 HttpServletRequest 中添加了 `changeSessionId`，使得 session 保护变得简单得多，Spring Security 3.2 包含了对该方法的支持。你可以在配置中进行细调。

```

@Configuration

@EnableWebMvcSecurity

public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Override

    protected void configure(HttpSecurity security) throws Exception {

        security.invalidateSession(true).deleteCookies("JSESSIONID")

            .and().sessionManagement()

            .and().sessionFixation().changeSessionId()

            .and().csrf().disable();

    }

}

```

之前的代码获取了会话管理配置，并指示 Spring Security 使用 Servlet 3.1 的 `changeSessionId` 方法来防止 session 固定攻击。明确地说，这实际上并不是必须。默认情况下，Spring Security 为运行在 Servlet 3.1 容器上的应用程序使用 `changeSessionId` 机制，你也可以选择：

- newSession，创建一个不包含现有 session 属性的新 session。
- migrateSession，它会创建一个新 session 并复制所有现有的属性。
- none，禁用 session 固定保护。

当你的应用程序运行在 Servlet 3.0 或更早版本的容器中时，`migrateSession` 是默认选项。在 XML 中配置 session 保护同样简单：

```

<http use-expressions="true">

    ...

    <session-management session-fixation-protection="migrateSession" />

</http>

```

## 限制用户会话数量

有时，限制单个用户同时持有的会话数量是有有益的。这可以防止他们同时从多台计算机、浏览器或位置访问你的网站，通常被用作安全特性，以确保只有一个人使用一组凭据。使用会话管理配置，你可以限制并发会话的数量。以下 Java 和 XML 配置启用了此功能。

```

@Configuration

@EnableWebMvcSecurity

public class SecurityConfiguration extends WebSecurityConfigurerAdapter

{

  @Override

  protected void configure(HttpSecurity security) throws Exception

  {

    ...

    .invalidateHttpSession(true).deleteCookies("JSESSIONID")

    .permitAll()

    .and().sessionManagement(

      .sessionFixation().changeSessionId()

      .maximumSessions(1).expiredUrl("/login?maxSessions")

    .and().and().csrf().disable();

  }

}

```

```

<http use-expressions="true">

  <session-management session-fixation-protection="changeSessionId">

    <concurrency-control max-sessions="1"



## 会话管理配置

```xml
<http>
  <session-management
    expired-url="/login?maxSessions" />
</http>
```

当配置了最大会话数时，默认行为是在用户登录时使现有的会话失效。在这种情况下，当原始 session 的持有者尝试访问该 session 时，他们将被重定向到 `/login?maxSessions`。这并不总是预期的行为。相反，你可以指示 Spring Security 防止第二次登录并返回未经授权的响应，允许原始 session 继续不受干扰地运行。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
  @Override
  protected void configure(HttpSecurity security) throws Exception {
    ...
    .invalidateHttpSession(true).deleteCookies("JSESSIONID")
    .permitAll()
    .and().sessionManagement()
      .sessionFixation().changeSessionId()
      .maximumSessions(1).maxSessionsPreventsLogin(true)
    .and().and().csrf().disable();
  }
}
```

```xml
<http use-expressions="true">
...
</http>
```

注意，此行为的配置选项在 Java 配置和 XML 配置中的名称不同。或者，你可以在不更改默认 session 固定保护的情况下启用并发控制。去掉 `sessionFixation()` 代码或 `session-fixation-protection` XML 属性。要启用并发，你还必须配置一个特殊的 Spring session 监听器，它发布与 httpSession 相关的事件。这允许 Spring Security 构建一个会话注册表，用它可以检测并发会话。启用此监听器最简单的方法是在你的 `SecurityBootstrap` 类中重写 `enableHttpSessionEventPublisher` 方法。

```java
public class SecurityBootstrap extends AbstractSecurityWebApplicationInitializer {
    @Override
    protected boolean enableHttpSessionEventPublisher() {
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

无论你采取哪种方法配置此项，如果你在集群环境中部署应用程序，必须注意在集群中的节点之间同步 session。否则，监听器将无法感知所有 session，无法正确限制用户可以持有的 session 数量。

## Authentication-App 测试步骤

Authentication-App 包含一个基础控制器，对 Spring Security 保护的简单 URL 响应。该控制器的细节并不重要，包含的你不熟悉的内容。要测试它，请按照以下步骤操作：

1. 编译项目并从 IDE 启动 Tomcat。
2. 访问 `http://localhost:8080/authentication/about`、`http://localhost:8080/authentication/signup` 和 `http://localhost:8080/authentication/policies`。你无需登录即可访问这些页面。
3. 现在访问 `http://localhost:8080/authentication/secure/` 或其下的任何 URL，Spring Security 会要求你登录。输入错误的凭据，Spring Security 将你带回登录界面并提示你登录失败。
4. 输入正确的凭据，你应该被授予访问。
5. 点击 Log Out 链接退出并使用另一组凭据登录。以 John 身份登录，尝试访问 `http://localhost:8080/authentication/admin/`，Spring Security 将阻止访问。
6. 退出并以 Margaret 身份登录，Spring Security 应该允许你访问管理页面。

## 使用 JDBC User Details Service

如前所述，`InMemoryUserDetailsManager` 只是一个测试实现，绝不应在生产应用程序中使用。它对演示很有用，但还有哪些选项？如果你将用户存储在数据库中（大多数应用程序的典型做法），`org.springframework.security.provisioning.JdbcUserDetailsManager` 提供了一种从数据库获取 User 对象的简单机制。你只需要给它一个 `DataSource` 并配置用于从数据库获取用户及其权限的 SQL 查询即可。

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
            .usersByUsernameQuery("SELECT Username, Password, Enabled * " +
                "FROM User WHERE Username = ?")
            .authoritiesByUsernameQuery("SELECT Username, Permission * " +
                "FROM UserPermission WHERE Username = ?")
            .passwordEncoder(new BCryptPasswordEncoder());
    }
}
```

大部分配置应该是自而易懂的。“users by username” SQL 查询将返回一个包含用户名、密码和启用/禁用标志的结果集，按顺序排列。“authorities by username” SQL 查询将返回一个包含用户名和权限名称的结果集，同样按顺序排列。两个查询都需要一个参数，即要查找的用户的用户名。

当然，你不应该以明文形式在数据库中存储用户密码，Spring Security 的 `org.springframework.security.crypto.password.PasswordEncoder` 接口提供了一种将密码哈希为哈希密码的机制。你只需要在已配置的 `users by username` 查询中返回哈希后的密码，并提供相应的 `PasswordEncoder` 实现来处理哈希密码格式。`org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder` 提供了一个使用 BCrypt 哈希算法进行密码比较的标准实现。

以下 XML 配置与 JDBC 详情服务的 Java 配置相同。

```xml
<authentication-manager>
  <authentication-provider data-source-ref="dataSource">
    <jdbc-user-service users-by-username-query=
      "SELECT Username, Password, Enabled FROM User WHERE Username = ?"
      authorities-by-username-query=
      "SELECT Username, Permission FROM UserPermission WHERE Username = ?" />
    <password-encoder hash="bcrypt" />
  </authentication-provider>
</authentication-manager>
```

## 使用其他用户详情服务

除了 `JdbcUserDetailsManager` 之外，还有 `org.springframework.security.ldap.userdetails.LdapUserDetailsManager` 和 `LDAPUserDetailsService` 类仅用于信息检索。你不能将它们用于实际的身份验证过程，因为它们无法从 LDAP 提供者获取密码。你拥有更多绑定的 `UserDetails` 实现，你也可以完全地定义自己的。只需创建一个 `UserDetailsService` 实现类，在你的 `SecurityConfiguration` 中获取它的实例（通过手动获取或注入），并将其添加到安全配置中即可。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Inject UserDetailsService myUserDetailsService;

    @Override
    protected void configure(AuthenticationManagerBuilder builder)
    throws Exception {
        builder.userDetailsService(this.myUserDetailsService)
            .passwordEncoder(new BCryptPasswordEncoder());
    }
}
```

使用 XML 配置自定义的 `UserDetailsService` 本质上是相同的。

```xml
<authentication-manager>
  <authentication-provider user-service-ref="myUserDetailsService">
    <password-encoder hash="bcrypt" />
  </authentication-provider>
</authentication-manager>
```

## 与 LDAP 和 Active Directory 提供者配合

为了确保起见，`DaoAuthenticationProvider` 类和相应的 `UserDetailsService` 接口在简单情况下快速让 Spring 运行起来非常有用。

现实情况很少那么简单，需要更复杂的身份验证机制。使用轻量级数据访问协议（LDAP）进行声明身份验证就是一个例子。为此，Spring Security 自带了一个 `org.springframework.security.ldap.authentication.LdapAuthenticationProvider`。

这个提供者是必要的，因为你并不总是能从 LDAP 服务器获取密码（哈希后的或其他）。例如，最常见的身份验证策略是 Bind（绑定），即用户通过“登录”到 LDAP 服务器来建立其身份。`LdapAuthenticationProvider` 直接与 LDAP 服务器进行身份验证，而不是将用户重定向到身份验证服务器。它有多个选项，但你可能不需要直接配置它。相反，你可以使用 Java 配置或 XML 命名空间。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Override
    protected void configure(AuthenticationManagerBuilder builder)
    throws Exception {
        builder.ldapAuthentication()
            .contextSource()
                .url("ldap://ldap.example.org:389/dc-example,dc=org ld://ldap2.example.org:389/dc-example,dc=org")
                .managerDn("uid=admin,ou=system")
                .managerPassword("bindPassword")
                .and()
            .userSearchFilter("uid=*")
            .userSearchBase("ou=people")
            .groupSearchBase("ou=groups");
    }
}
```

```xml
<ldap-server manager-dn="uid=admin,ou=system" manager-password="bindPassword" url="http://ldap.example.org:389/dc-example,dc=org" />
<authentication-manager>
    <ldap-authentication-provider user-search-filter="uid={}"
        user-search-base="ou=people"
        group-search-base="ou=groups" />
</authentication-manager>
```

这些配置假设服务器上没有启用匿名访问，并提供了一个管理员区分名称（DN）和密码，用于绑定其他用户。如果你的服务器允许匿名访问，你可以省略这些内容。

## 选择和配置身份验证提供者

用户提交表单后，Spring Security 接管并将他们重定向到正确的提供者 URL，并在他们从提供者返回时完成回调认证过程。



```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Override
    public void configure(WebSecurity security) {
        security.ignoring().antMatchers("/resource/**");
    }

    @Override
    protected void configure(HttpSecurity security) throws Exception {
        security
            .authorizeRequests("/signup", "/about", "/policies/*").permitAll()
            .antMatchers("/secure/**").hasAuthority("USER")
            .antMatchers("/admin/**").hasAuthority("ADMIN")
            .anyRequest().authenticated()
            .loginPage("/login")
            .failureUrl("/loginerror")
            .defaultSuccessUrl("/secure/", new MyUserDetailsService()
            .attributeExchange("https://www.google.com.*"
                .attribute("firstname").required(true)
                .type("http://axschema.org/namePerson/first")
                .and()
                .attribute("lastname").required(true)
                .type("http://axschema.org/namePerson/last")
                .and()
                .attribute("email").required(true)
                .type("http://axschema.org/contact/email")
                .and()
            .attributeExchange("*.yahoo.com.*"
                .attribute("fullname").required(true)
                .type("http://axschema.org/namePerson")
                .and()
                .attribute("email").required(true)
                .type("http://axschema.org/contact/email")
                .and()
            .logout()
            .logoutUrl("/logout").logoutSuccessUrl("/login?loggedOut")
            .invalidateHttpSession(true).deleteCookies("JSESSIONID")
            .permitAll()
            .and()
            .sessionManagement(
                .changeSessionId()
                .maximumSessions(1).maxSessionsPreventsLogin(true)
            )
            .and().csrf().disable();
    }
}
```

## 764 | 第 26 章 使用 SPRING SECURITY 认证用户

此配置设置了 OpenID 登录机制，并配置了与两个常用提供者的属性交换。实际上，为每个提供者创建处理设置的方法可能更有意义。该配置还设置了登录页面、失败 URL 和默认成功 URL，这些是你之前为表单登录机制配置过的内容。

`loginPage` 是你提供的视图，其中包含 OpenID 标识符（字段必须命名为 `identifier`）以及你支持的所有提供者的按钮。`UserDetailsAuthenticationService` 是一个根据你设计的 `org.springframework.security.core.userDetailsService` 理论实现，它能够接受 `org.springframework.security.openid.OpenIDAuthenticationToken` 并返回一个 `UserDetails` 对象。如果你决定启用“记住我”认证，则必须提供一个 `UserDetails` 实现。你可以同时为了这两个目的使用 `UserDetailsService`。

如你所见，在 Spring Security 中配置 OpenID 涉及的细节非常多，足以填满另一个章节。如果你想看更多示例，Spring GitHub 仓库中的示例代码是一个极佳的资源。

> 注意：要使用 Spring Security 的 OpenID 支持，你需要在项目中添加以下 Maven 依赖（第一个作为直接依赖，其他用于强制使用许多带有大量 bug 修复和安全改进的近期临时依赖）。此依赖会拉入许多临时依赖。

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
  <groupId>org.commons-codec</groupId>
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

许多网站提供“记住我”认证。该概念通常涉及登录屏幕上的一个复选框，用户可以通过该复选框指示网站记住他们的浏览器，并在下次时自动登录。这是通过在用户的浏览器中保存 cookie 来在他们下次访问时识别他们来实现的。

明确地说，这是一个随时可能发生的安全漏洞。攻击者可以获取用户的 cookie，然后代表用户访问你的应用程序。你可以通过让“记住我”令牌快速过期或仅使用一次来在某种程度上缓解安全疑虑，但实际上漏洞仍然存在。在保护任何类型的敏感信息（如医疗数据、财务记录或就业信息）时，绝不要使用“记住我”认证。然而，对于低安全需求的情况（如用户论坛和带有评论的新闻网站），为了用户方便考虑，这种妥协是可以接受的。

Spring Security 通过特殊的 `org.springframework.security.authentication.RememberMeAuthenticationProvider` 提供“记住我”认证。如果你想启用“记住我”，请在登录屏幕上添加一个字段名为 `remember-me` 的复选框（当使用 XML 配置时使用 `_spring_remember_me`），然后在配置中简单地切换到记住我服务即可：

```java
@Configuration
@EnableMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Override
    protected void configure(HttpSecurity security) throws Exception {
        .maximumSessions(1).maxSessionsPreventsLogin(true)
        .and().csrf().disable();
    }
}
```

```xml
<http>
    <remember-me key="MyAppName"/>
</http>
```

如果你的登录过程在 SSL 上进行（这应该是这样的），使用 `secureCookie`（或 `secure-cookie`）。你还可以使用 `tokenValidity`（或 `token-validity-seconds`）来控制记住我令牌的有效期。如前所述，记住我服务需要一个 `UserDetailsService` 才能工作。然而，如果你有多个 UserServices，你必须

该项目是自包含的，下载后即可立即运行。本节仅涵盖了为客户支持（Customer Support）应用程序添加身份验证而对项目进行的更改。

早期，你为应用程序添加了一个简单的用户名和密码身份验证系统。这对于完成项目中所需的一些基础功能是必要的。现在，你可以用 Spring Security 的企业级功能替换这种自制的身份验证机制。本节将展示如何进行此操作，并向你介绍跨请求伪造（Cross-Request Forgery）攻击以及 Spring Security 3 引入的缓解功能。

### 按正确的顺序引导

正如你可能记得的，客户支持应用程序中的 Spring Framework、Servlet 和过滤器配置比你在示例 `Authentication-App` 中创建的要复杂得多。一个重要的问题是，`LoggingFilter` 执行了两个任务：将一个标签（UUID 形式的）和登录用户添加到 Log4j 的 `ThreadContext` 中。这样做的问题在于，用户名只有在 Spring 过滤器链执行后才可用，这意味着过滤器代码必须运行。然而，运行过滤器标签代码会导致 Spring 日志不包含该过滤器标签，这并不是我们所希望的。因此，你必须将日志拆分为两个过滤器，并按照正确的顺序引导所有内容。

## 拆分日志过滤器

拆分日志过滤器并不是一项复杂的任务。将 `LoggingFilter` 替换为 `PreSecurityLoggingFilter` 和 `PostSecurityLoggingFilter`。`PreSecurityLoggingFilter` 负责设置过滤器标签并在请求完成后清除过滤器标签和用户名。

```java
public class PreSecurityLoggingFilter implements Filter {

    @Override
    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
        String id = UUID.randomUUID().toString();
        ThreadContext.put("id", id);
        try {
            ((HttpServletResponse) response).setHeader("X-Rows-Id", id);
            chain.doFilter(request, response);
        } finally {
            ThreadContext.remove("id");
            ThreadContext.remove("username");
        }
    }
}
```

`PostSecurityLoggingFilter` 更加简单。它使用 Spring Security 的 `org.springframework.security.core.context.SecurityContextHolder` 静态方法来获取当前的 `org.springframework.security.core.context.SecurityContext`。该上下文是请求本地的，持有属于当前请求和 HTTP 会话的 `Authentication`。`PostSecurityLoggingFilter` 将从 `ThreadContext` 中移除用户名的任务委托给 `PreSecurityLoggingFilter`，以便用户名尽可能久地留在 `ThreadContext` 中。

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

## 引导类的排序

现在你已经拆分了日志过滤器，确保所有应用程序组件按正确的顺序初始化变得至关重要。`PreSecurityLoggingFilter` 必须在 `PostSecurityLoggingFilter` 之后。由于 Spring Framework 仅注册了一个 `ServletContextListener` 和几个服务器，因此在那个过程中初始化 Spring Framework 实际上并不重要。它不会干扰过滤器的执行顺序。

对多个 Spring Framework `WebApplicationInitializer` 进行排序非常简单。你只需需要使用 `org.springframework.core.annotation.Order` 注解这些类，并提供一个与初始化器优先级相对应的值。值越小优先级越高，因此 `-2,147,483,648` 是优先级最高的。值越大优先级越低，因此最低优先级是 `2,147,483,647`。对于你的用途，最简单的方法是将你使用的三个引导类编号为 1、2 和 3。这些类被分组在 `com.vertx.bootstrap` 包中，且 `FrameworkBootstrap` 替换了以前版本中的旧 `Bootstrap` 类。省略号替换了没有更改的 Spring Framework 引导代码。主要的区别是之前的 `AuthenticationFilter` 消失了，并且在这里注册的是 `PreSecurityLoggingFilter` 而不是之前的 `LoggingFilter`。

```java
@Order(1)
public class FrameworkBootstrap implements WebApplicationInitializer {
    private static final Logger log = LogManager.getLogger();
    @Override
    public void onStartup(ServletContext container) throws ServletException {
        log.info("Executing framework bootstrap.");
        ...
        FilterRegistration.Dynamic registration = container.addFilter(
            "preSecurityLoggingFilter", new PreSecurityLoggingFilter()
        );
        registration.addMappingForUrlPatterns(null, false, "/*");
    }
}
```

接下来，你需要引导 Spring Security 的过滤器链。除了添加 `@Order` 注解和一条日志语句（用于证明顺序是正确的）外，这和你为 `Authentication-App` 项目创建的 `SecurityBootstrap` 完全相同。

```java
@Order(2)
public class SecurityBootstrap extends AbstractSecurityWebApplicationInitializer {
    private static final Logger log = LogManager.getLogger();
    @Override
```



```java
protected boolean enableEventPublisher() {

    log.info("Executing security bootstrap.");

    return true;

}

}
```

引导过程的最后一步是在 `LoggingBootstrap` 类中注册 `PostSecurityLoggingFilter`。当 Spring Framework 启动时，它会按照顺序执行这些引导类。

```java
@Order(3)
public class LoggingBootstrap implements WebApplicationInitializer {

    private static final Logger log = LogManager.getLogger();

    @Override
    public void onStartup(ServletContext container) throws ServletException {

        log.info("Executing logging bootstrap.");

        FilterRegistration.Dynamic registration = container.addFilter("postSecurityLoggingFilter", new PostSecurityLoggingFilter());

        registration.addMappingForUrlPatterns(null, false, "/*");

    }

}
```

## 编写自己的身份验证器

现在日志和 Spring Security 已按正确顺序设置引导，是时候创建自己的 `AuthenticationProvider` 了。由于你在整个应用程序中使用 `UserPrincipal` 实体作为标识，最简单的方法是更新 `UserPrincipal` 实现 `Authentication`。然后你就可以从 `AuthenticationProvider` 实现中返回它。

## 转换 User Principal 和身份服务

大部分情况下，`UserPrincipal` 几乎没有变化。它的映射保持不变，并且仍然实现了 `Principal` 和 `Serializable`，但是通过 `Authentication` 间接实现的。主要的更改是增加了 `Authentication` 中指定的 `getAuthorities`、`getPrincipal`、`getDetails`、`getCredentials`、`isAuthenticated` 和 `setAuthenticated` 方法。它们的实现都是模板代码。

最重要的更改是 `AuthenticationService` 接口，它的 `DefaultUserService` 实现现在扩展了 `AuthenticationProvider`，并重写了 `authenticate` 方法，以明确该提供者只返回 `UserPrincipal`。

```java
@Validated
public interface AuthenticationService extends AuthenticationProvider {

    @Override
    UserPrincipal authenticate(Authentication authentication);

    void saveUser(
        @NotNull(message = "*validate.saveUser")
        UserPrincipal principal,
        String newPassword
    );

}
```

```java
@Service
public class DefaultAuthenticationService implements AuthenticationService {

    @Override
    @Transactional
    public UserPrincipal authenticate(Authentication authentication) {

        UsernameAuthenticationToken credentials = (UsernameAuthenticationToken) authentication;
        String username = credentials.getPrincipal().toString();
        String password = credentials.getCredentials().toString();
        // ... implementation继续

    }

}
```

```java
credentials.eraseCredentials();
principal.setAuthenticated(true);
log.debug("User {} successfully authenticated.", username);

return principal;

}

@Override
public boolean supports(Class<?> c) {

    return c == UsernamePasswordAuthenticationToken.class;

}
```

现在，你需要配置 Spring Security 以使用 `AuthenticationProvider`。这在列表 26-1 的 `SecurityConfiguration` 类中得到了演示，该类是从 `RootContext` 类导入的。注意，它让 Spring Framework 自动注入 `AuthenticationService` Bean，并简单地将其连接到 `configure(AuthenticationManagerBuilder)` 方法中。`configure(WebSecurity)` 方法将静态资源和可能的 favicon 排除在 Spring Security 过滤器链之外；`configure(HttpSecurity)` 则要求所有请求进行身份验证，并设置了表单登录和注销机制，与 Authentication-App 中的代码类似。它还做了一些其他事情，你很快就会看到。

## 列表 26-1: SecurityConfiguration.java

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
                .loginPage("/login").failureUrl("/login?failed")
                .defaultSuccessUrl("/ticket/list")
                .usernameParameter("username")
                .passwordParameter("password")
                .permitAll()
            .and().logout()
                .logoutUrl("/logout").logoutSuccessUrl("/login?loggedOut")
                .invalidateSession(true).deleteCookies("JSESSIONID")
            .and().sessionManagement()
                .sessionFixation().changeSessionId()
                .maxSessions(1).maxSessionsPreventsLogin(true)
                .sessionRegistry(this.sessionRegistryImpl)
            .and().csrf()
                .requireCsrfProtectionMatcher((r) -> {
                    String m = r.getMethod();
                    return r.getServletPath().startsWith("/services/*") &&
                        ("POST".equals(m) || "PUT".equals(m) || "DELETE".equals(m) || "PATCH".equals(m));
                });

    }

}
```

## 替换 Session Registry

你可能奇怪为什么列表 26-1 中的 `SecurityConfiguration` 类要手动创建 Spring Security `SessionRegistryImpl` Bean，然后将其注入到会话管理配置中。难道 Spring Security 不会自动创建这个 Bean 吗？是的，Spring Security 会这样做，但这样做会导致 `SessionRegistry` 不会以 Bean 的形式暴露给整个应用程序。在书早期，你使用 `SessionListener`（`HttpSessionListener` 的实现）创建了你自己的 `com.wrox.site.SessionRegistry`。Spring 的 `SessionRegistry` 可以完全取代此功能。通过手动创建 `SessionRegistryImpl`，将 Bean 暴露给你的应用程序，以便你可以在 Spring 类之外的其他应用程序中使用它。`SessionListController` 现在使用 Spring 的 `SessionRegistry` 而不是旧的 `com.wrox.site.SessionRegistry`。

```java
@RequestMapping("session")
public class SessionListController {

    @Inject SessionRegistry sessionRegistry;

    @RequestMapping(value = "list", method = RequestMethod.GET)
    public String list(Map<String, Object> object) {

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

使用 Spring Framework 的发布-订阅消息机制，Spring Security 在发生身份验证事件时会发布各种消息。这些不同的事件在 API 文档中有详细说明，但你最常用的是以下几个：

- `org.springframework.security.authentication.event.AbstractAuthenticationFailureEvent`，当身份验证由于某种原因失败时发布。其子类包含了更多原因的细节。
- `org.springframework.security.authentication.event.AuthenticationSuccessEvent`，当身份验证成功时发布。然而，这可能包含交互式身份验证事件，如重新身份验证。如果你只想了解交互式身份验证，请使用 `org.springframework.security.authentication.event.InteractiveSuccessEvent`。
- `org.springframework.security.web.authentication.session.SessionFixationProtectionEvent`，当会话保护导致会话变化（例如会话迁移或 sessionId 更改）时发布。
- `org.springframework.security.core.session.SessionDestroyedEvent`，当会话被销毁（无论是注销还是超时）时发布。

当会话被销毁（无论是注销还是超时）时发布。在书早期，你使用 `SessionListener`（`HttpSessionListener` 的实现）创建了你自己的 `com.wrox.site.SessionRegistry`。Spring 的 `SessionRegistry` 可以完全取代此功能。通过手动创建 `SessionRegistryImpl`，将 Bean 暴露给你的应用程序，以便你可以在 Spring 类之外的其他应用程序中使用它。`SessionListController` 现在使用 Spring 的 `SessionRegistry` 而不是旧的 `com.wrox.site.SessionRegistry`。

使用 Spring Framework 的发布-订阅消息机制，Spring Security 在发生身份验证事件时会发布各种消息。这些不同的事件在 API 文档中有详细说明，但你最常用的是以下几个：

- `org.springframework.security.authentication.event.AbstractAuthenticationFailureEvent`，当身份验证由于某种原因失败时发布。其子类包含了更多原因的细节。
- `org.springframework.security.authentication.event.AuthenticationSuccessEvent`，当身份验证成功时发布。然而，这可能包含交互式身份验证事件，如重新身份验证。如果你只想了解交互式身份验证，请使用 `org.springframework.security.authentication.event.InteractiveSuccessEvent`。
- `org.springframework.security.web.authentication.session.SessionFixationProtectionEvent`，当会话保护导致会话变化（例如会话迁移或 sessionId 更改）时发布。
- `org.springframework.security.core.session.SessionDestroyedEvent`，当会话被销毁（无论是注销还是超时）时发布。

当会话被销毁（无论是注销还是超时）时发布。在书早期，你使用 `SessionListener`（`HttpSessionListener` 的实现）创建了你自己的 `com.wrox.site.SessionRegistry`。Spring 的 `SessionRegistry` 可以完全取代此功能。通过手动创建 `SessionRegistryImpl`，将 Bean 暴露给你的应用程序，以便你可以在 Spring 类之外的其他应用程序中使用它。`SessionListController` 现在使用 Spring 的 `SessionRegistry` 而不是旧的 `com.wrox.site.SessionRegistry`。

```java
@RequestMapping("session")
public class SessionListController {

    @Inject SessionRegistry sessionRegistry;

    @RequestMapping(value = "list", method = RequestMethod.GET)
    public String list(Map<String, Object> object) {
```



```java
List<Session> sessions = new ArrayList<>();

for (Object principal : this.sessionRegistry.getAllPrincipals()) {
    sessions.addAll(this.sessionRegistry.getAllSessions(principal, true));
}

model.put("timestamp", System.currentTimeMillis());
model.put("numberOfSessions", sessions.size());

return "session/list";
}
}
```

当会话被销毁（无论是注销还是超时）时发布。在书早期，你使用 `SessionListener`（`HttpSessionListener` 的实现）创建了你自己的 `com.wrox.site.SessionRegistry`。Spring 的 `SessionRegistry` 可以完全取代此功能。通过手动创建 `SessionRegistryImpl`，将 Bean 暴露给你的应用程序，以便你可以在 Spring 类之外的其他应用程序中使用它。`SessionListController` 现在使用 Spring 的 `SessionRegistry` 而不是旧的 `com.wrox.site.SessionRegistry`。

使用 Spring Framework 的发布-订阅消息机制，Spring Security 在发生身份验证事件时会发布各种消息。这些不同的事件在 API 文档中有详细说明，但你最常用的是以下几个：

- `org.springframework.security.authentication.event.AbstractAuthenticationFailureEvent`，当身份验证由于某种原因失败时发布。其子类包含了更多原因的细节。
- `org.springframework.security.authentication.event.AuthenticationSuccessEvent`，当身份验证成功时发布。然而，这可能包含交互式身份验证事件，如重新身份验证。如果你只想了解交互式身份验证，请使用 `org.springframework.security.authentication.event.InteractiveSuccessEvent`。
- `org.springframework.security.web.authentication.session.SessionFixationProtectionEvent`，当会话保护导致会话变化（例如会话迁移或 sessionId 更改）时发布。
- `org.springframework.security.core.session.SessionDestroyedEvent`，当会话被销毁（无论是注销还是超时）时发布。

Listing 26-1 中的 `requireCsrfProtectionMatcher` 覆盖了默认的 CSRF 匹配器，将 Web 服务排除在 CSRF 保护之外。

> 注意：虽然 lambda 表达式确实有所帮助，但 Listing 26-1 中的 CSRF 配置至少也是的，你必须定义一个新的匹配器。在第 28 章中，当你为 Web 服务添加认证和授权时，将学习到更好的配置方法。

## 表单安全

在根据需求配置了 CSRF 保护后，如何保护你的表单呢？在某种程度上，你不需要做什么。只要你在使用 `<form:form>` 标签并进行 post、PUT、PATCH 或 DELETE 请求时，都通过 `@EnableWebSecurity` 配置了 Spring Security，Spring 就会自动添加一个隐藏的 CSRF 令牌字段。如果你仍然想对登录视图使用 `<form:form>`——CSRF 保护就会自动发生。如果你只用 `@EnableWebSecurity` 配置了 Spring Security，则必须创建一个类型为 `org.springframework.security.web.servlet.csrf.CsrfRequestDataValueProcessor` 的 bean 来启用此功能。Spring 会自动为任何匹配配置匹配器的请求查找 CSRF 令牌。

你必须采取额外步骤添加 CSRF 保护的唯一情况是：使用标准的 HTML `<form>` 而非 Spring 的 `<form:form>`、通过 JavaScript 提交表单以及通过 Ajax 调用服务器时。在这些情况下，你有责任向表单或请求添加 CSRF 字段或标头。Spring 也通过在所有 JSP 视图中注册类型为 `org.springframework.security.web.csrf.CsrfToken` 的 EL 变量来使这一切变得简单。你只需要使用令牌属性将适当的值添加到你的表单或 JavaScript 中。客户支持应用程序中的 `postInvisibleForm` JavaScript 函数启动并连接了链，并将它们全部发出。对此函数进行简单的微调即可保护以此方式提交表单的代码。

```javascript
var postInvisibleForm = function (url, fields) {
    var form = $('<form id="mapForm" method="post"></form>')
        .attr({action: url, style: 'display:none;});

    for (var key in fields) {
        if (fields.hasOwnProperty(key)) {
            form.append($('<input type="hidden">').attr({
                name: key, value: fields[key]
            }));
        }
    }

    form.append($('<input type="hidden">').attr({
        name: '${_csrf.parameterName}', value: '${_csrf.token}'
    }));

    $('body').append(form);
    form.submit();
};
```

在保护表单的同时，你应该知道“最佳实践”是禁用表单的自动补全。这可以保护那些与他人共享电脑的用户（例如在公共图书馆中）。进行此更改只需在 `login.jsp` 中的 `<form>`、`<form:input>` 和 `<form:password>` 标签中添加 `autocomplete="off"`。在启用 CSRF 保护的情况下，Spring 要求注销必须通过 POST 进行。这就是为什么客户支持应用程序中的登录链接会提交一个隐藏表单。

在检查所有这些更改后，编译项目并从 IDE 启动 Tomcat。在 `http://localhost:8080/support/` 登录应用程序，你不应该发现创建、列出和搜索工单以及与支持人员聊天时有什么区别。从用户的角度来看，应用程序的执行上基本上是相同的；但它现在更安全、更健壮了。你仍然需要处理不同权限的用户——这将在下一章中介绍。

## SPRING SECURITY 3.2 中的 HTTP 安全标头

在过去的几年里，行业专家和工作组提出并采用了几种安全相关的 HTTP 标头，以指示浏览器启用某些安全机制。这些标头是为了应对不同的 Web 漏洞，例如跨站脚本（XSS）和点击劫持（Clickjacking）攻击。

Spring 3.2 增加了将这些标头设置为最佳实践值的支持，使你的应用程序尽可能安全。与 CSRF 保护一样，这些标头仅添加到 Spring Security 过滤器链处理的 URL 响应中。如果你使用 XML 配置，这些标头默认启用以保持与之前的版本行为一致。然而，如果你使用 Java 配置，这些标头默认启用的，这意味着你了解它们的工作原理，以及如何确定是否需要禁用其中任何一个。

- `Cache-Control` 被设置为 `no-cache, no-store, max-age=0, must-revalidate`，`Pragma` 被设置为 `no-cache`。这告诉客户端和代理永远不要缓存服务器返回的机密数据。
- `Content-Type-Options` 被设置为 `nosniff`，指示浏览器永远不要依赖页面和资源的 MIME 类型。相反，浏览器会确保有效的 MIME 类型。
- `Strict-Transport-Security` 被设置为 `max-age=31536000; includeSubdomains`，这有助于使用 HTTPS。
- `Frame-Options` 被设置为 `DENY`，防止响应在框架内显示。这可以防止点击劫持攻击。
- `XSS-Protection` 被设置为 `1; mode=block`。结果是如果浏览器检测到可能包含 XSS 的疑脚本，它将禁用脚本而不是尝试仅禁用嫌部分。

要在 XML 配置中启用这些标头，只需向你想应用的 `<http>` 配置中添加 `<headers />`。要在 Java 配置中禁用这些标头，可以执行如下所示的操作：

```java
@Override
protected void configure(HttpSecurity security) throws Exception {
    security
    ...
    .and().headers().disable();
}
```

你也可以单独控制每个标头类型。以下是启用（或禁用）它们的等效代码：

```java
@Override
protected void configure(HttpSecurity security) throws Exception {
    security
    .and().headers().cacheControl().contentTypeOptions()
    .frameOptions().httpTransportSecurity()
    .xssProtection();
}
```

### 总结

在本章中，你探索了 Spring Security 认证。你还学习了 Spring Security 作为全安全解决方案的某些方法，例如 CSRF 缓解和 Spring Security 3.2 中添加的新 HTTP 标头。你实验了各种认证机制，并为客户支持应用程序创建了自己的认证提供程序。最后，你学习了 XML 和 Java 配置选项，以及 Spring Java 配置与 Spring 配置有何显著区别。

在下一章中，你将完成认证-授权的故事，学习检查用户权限以及确保只有授权用户执行受保护操作的方法。

## 27 使用授权标签和注解

本章内容

- 在代码中检查授权规则
- 声明 URL 和方法安全
- 使用常用注解和 Spring Security 注解
- 理解授权决策
- 为对象安全创建访问控制列表
- 使用 Spring Security 标签库

本章的 WROX.COM 代码下载

你可以在 `http://www.wrox.com/projectjavaforwebapps` 的 Download Code 选项卡找到本章的 wrox.com 代码下载。本章的代码包含在示例中：

- Customer-Support-v20 项目

本章的新增 MAVEN 依赖

除了之前章节引入的 Maven 依赖外，你还需要以下 Maven 依赖：

```xml
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-taglibs</artifactId>
  <version>3.2.0.RELEASE</version>
  <scope>runtime</scope>
</dependency>
```

# 通过声明进行授权

在第 25 章中，你探索了实现授权的不同方法。你可以使用许多技术和手段，认为任何一种方法都比其他方法更好是不准确的。这很大程度上取决于你的个人需求、应用程序架构以及你采用身份验证的方法。直觉的方法可能是简单地将授权放在代码中。一种非常常见且通常被视为最佳实践的技术是**通过声明进行授权**。在这种技术中，你的代码或配置声明了谁可以做什么，而安全机制会拦截对代码的访问并代表你执行规则。这种模式与你在书中第三部分探索的事务模式相似。在本节中，你探索实现这两种方法的各种方式，并学习 Spring Framework 提供的工具。

### 在方法代码中检查权限

通常，你的代码需要使用类似下面的代码来检查用户是否有权执行某操作：

```java
public void doSomeAction(...) {
    if (security.userCanPerformAction("*ACTION_1*")) {
        // code that performs the action
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}
```

然而，这会迅速让你的服务充斥着重复代码。考虑一个管理论坛帖子和回复的服务：

```java
public Post getPost(long id) {
    if (security.userCanPerformAction("*READ_POST*")) {
        // code that returns post
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

Page<Post> listPosts(long forumId, Pageable pageable) {
    if (security.userCanPerformAction("*LIST_POSTS*")) {
        // code that lists posts
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public void savePost(Post post) {
    if (security.userCanPerformAction("*SAVE_POST*")) {
        // code that saves post
    } else
```



# 代码示例：硬编码授权检查

```java
throw new AccessDeniedException("Not authorized to perform action.");
}

public void deletePost(Post post) {
    if (security.userCanPerformAction("DELETE_POST")) {
        // code that deletes post
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public Reply getReply(long id) {
    if (security.userCanPerformAction("READ_REPLY")) {
        // code that returns reply
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public Page<Reply> listReplies(long postId, Pageable pageable) {
    if (security.userCanPerformAction("READ_REPLIES")) {
        // code that lists replies
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public void saveReply(Reply reply) {
    if (security.userCanPerformAction("SAVE_REPLY")) {
        // code that saves reply
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}

public void deleteReply(Reply reply) {
    if (security.userCanPerformAction("DELETE_REPLY")) {
        // code that deletes replies
    } else {
        throw new AccessDeniedException("Not authorized to perform action.");
    }
}
```

当然，这太简单了。它忽略了用户可能只允许查看帖子和回复的事实，并且没有考虑到管理员删除他人帖子与删除自己帖子之间的区别。尽管如此，在所有的回调和 lambda 表达式中，至少有 24 行代码专门用于检查授权规则，这是相当的重复性工作。你可以使用回调和 lambda 表达式来消除重复，例如：

```java
public Post getPost(long id) {
    return security.doSecured("READ_POST", () -> {
        // code that returns post
    });
}
```

...

虽然这确实是一个改进，但你最终仍然复制了部分代码。这并不是最简洁的方法，因为你所有的服务代码最终都被放在了回调 lambda 表达式中。此外，你如何对之前的任何代码示例进行单元测试呢？这并不容易！每个测试都必须模拟安全上下文。这是为什么你不应该将授权检查硬编码到业务逻辑中的另一个原因。相反，你应该使用**声明式授权**。

通过使用声明式授权，你可以将业务逻辑与安全考虑分离。这使得你的代码更整洁、更容易测试且更容易维护。Spring 提供了实现此目的的方法，包括方法级安全和 URL 级安全。在接下来的章节中，我们将详细探索这些方法。

# 第 27 章 使用授权标签和注解

- `hasIPAddress(String)`：如果用户的请求源于指定的 IP 地址，则评估为 true。你也可以解析无类网域间路由 (CIDR) 块（例如 `65.128.76.0/24`），如果用户的 IP 地址属于该 IP 地址块，`hasIPAddress` 将评估为 true。

`getAuthentication` 返回 `Authentication` 对象，你可以用它执行更复杂或专门的组合，并评估出一个布尔值。

Spring 框架表达式语言（EL 或 SpEL）是强制你使用授权函数的动力。本文没有涵盖 SpEL，但它非常简单。它与 Java 统一表达式语言非常相似，你可以学习很多关于使用 Spring 表达式所需的知识。如果你想获取更多信息，可以在 Spring 框架参考文档中找到。

当使用 XML 配置时，在 `<http>` 内部的元素 `<intercept-url>` 中定义 URL 规则。默认情况下，`access` 属性具有 `hasRole` 或 `hasAuthorities`。它简单地接受逗号分隔的 `GrantedAuthority` 列表，用户必须拥有其中之一才能访问匹配的 URL。注意这些 `<intercept-url>` 标签出现的顺序非常重要。如果你反转了这两个规则的顺序，任何人都可以访问 `/admin/` URL。

```xml
<http>
  <intercept-url pattern="/admin/**" access="ADMINISTRATOR" />
  <intercept-url pattern="***" access="USER" />
  <form-login ...>
  <logout ...>
</http>
```

要使用 `access` 属性中的授权表达式功能，你必须在 `<http>` 元素中启用表达式。启用表达式简单，只需将 `use-expressions` 属性设置为 `true`。之后，你就不能再提供简单的逗号分隔的 `GrantedAuthority` 列表。你必须使用一个或多个安全函数，结合布尔运算符 `and` 或 `or`（如果需要）来形成一个完全安全的表达式。通过这种语法，你可以为保护应用程序的 Web 资源定义简单且复杂的规则。例如，要指定访问管理面板需要完全身份验证（“记住我”）、拥有管理员权限并且从内部 IP 地址范围连接，你可以这样配置：

```xml
<http use-expressions="true">
  <intercept-url pattern="/admin/**" access="fullyAuthenticated and hasAuthority('ADMINISTRATOR') and hasIPAddress('192.168.0.0/24')" />
  <intercept-url pattern="***" access="hasAuthority('USER')" />
  <form-login ...>
  <logout ...>
</http>
```

在这种情况下，如果用户使用“记住我”认证进行身份验证，他在访问管理面板之前会被要求进行完全身份验证（“登录”）。如果用户没有 `ADMINISTRATOR` `GrantedAuthority` 或从受禁止的 IP 地址连接，他将收到 403 Forbidden HTTP 错误。当然，你可以使用 `or` 代替，但那并不符合逻辑。那样，只需满足三个条件中的之一即可允许访问管理面板。

Java 配置略有不同，因为它只支持安全表达式。考虑到 Java 配置与 XML 配置之间有多大的不同，以及这些类型之间默认设置的差异，这是很自然的。当你在 Java 配置中选择 URL 时（使用 `anyRequest`、`antMatchers` 或 `regexMatchers`），返回的对象是 `org.springframework.security.config.annotation.web.configurers.ExpressionAuthorization.AuthorizedUrl`。通过此对象，你可以调用 `access` 方法来创建一个复杂的 SpEL 表达式，以识别你在 XML 配置中会创建的内容，或者你可以使用用安全函数命名的便利方法来创建简单表达式。以下 Java 配置与之前的 XML 配置相同。（再次注意，URL 的顺序非常重要。）

```java
@Override
protected void configure(HttpSecurity security) throws Exception {
    security.authorizeRequests()
        .antMatchers("/admin/**").access("isAuthenticated() and hasAuthority('ADMINISTRATOR') and hasIpAddress('192.168.0.0/24')")
        .antMatchers("/**").hasAuthority("USER")
    .and()
    .formLogin();
}
```

> **警告**：尽管 `hasRole` 和 `hasAnyRole` 安全函数与 `hasAuthority` 和 `hasAnyAuthority` 安全函数相同，但 Java 配置的便利方法并非如此。`hasRole` 和 `hasAnyRole` 便利方法会在它们接收的权限前面加上 `ROLE_`。如果权限以 `ROLE_` 开头，则是没问题的。在这种情况下，请省略 `ROLE_`，它会自动为你添加。然而，如果你的权限不是以 `ROLE_` 开头的，你需要坚持使用 `hasAuthority` 和 `hasAnyAuthority`。

使用 URL 安全确实有其优势。对于广泛的 URL 集合，表达式非常灵活，如果你使用 XML 配置，你可以在不重新编译应用程序的情况下更改授权规则。这比在你所有的应用程序方法中评估安全限制绝对是一个改进。然而，两个显著的缺点通常阻碍了人们使用此功能：

- 它将授权与 Web 层绑定——如果创建了另一个执行相同任务的用户，如果忘记为该接口定义重复的安全规则，就会危及该功能的安全性。
- 它让重构更具风险——如果你的接口发生了变化，而你的授权规则没有变，你的安全可能再次受到威胁。

![](img/4677f981a0e1067137bb55a122f8498d_820_0.png)

而且，当然，这完全忽略了你可能根本没有 Web 层的可能性！之前的代码将规则统一应用于整个类。然而，如果你在整个类或接口上标记此注解，它将阻止该类所有方法的执行。此外，如果一个类被标记为 `@RolesAllowed` 且其中一个方法被标记为 `@PermitAll`，任何人都可以执行该方法。

## 使用注解声明权限

那么，你如何在不实际编写代码的情况下在服务中评估授权规则呢？你在 Spring 中处理数据库事务时遇到过类似的需求：使用 `@Transactional` 注解方法可以确保事务在执行前启动或在执行后回滚。你可以应用相同的模式为你的方法添加安全性。

# 用于授权的常用注解

Java EE 的常用注解 API 指定了若干可以用于此目的的授权注解。它们都位于 `javax.annotation.security` 包中。

- `@DeclareRoles`：在 Spring Security 环境中提供了一种列出应用程序使用的所有角色（权限、账户等）的方法。
- `@DenyAll`：禁止所有人的访问。在方法上标记此注解意味着外部执行者（另一个类）永远无法执行它。对象通常可以执行其 `@DenyAll` 方法，因为代理对象不会处于这种状态下。如果你使用字节码织入而不是接口或 CGLIB 代理（你在第 24 章中学过的），它将不起作用。因此，很少的情况需要你使用此注解。如果你在整个类或接口上标记此注解，它将阻止该类所有方法的执行。
- `@PermitAll`：自然是 `@DenyAll` 的反面。它声明任何人都可以执行此方法。尽管这看起来没用，但它实际上非常有用。要理解为什么，你必须先理解下一个注解。
- `@RolesAllowed`：可能具有误导性，因为它的名称暗示它只适用于基于角色的授权。记住你在第 25 章中学到的：不在于你调用它，而在于你如何使用它。`@RolesAllowed` 指定了用户执行方法必须拥有的一个或多个（权限或 `GrantedAuthority`）。用户不需要拥有所有角色，只需一个。如果在类或接口上指定，此注解适用于该类中的所有方法。如果同时在类和方法上指定，方法的限制通常会累加到类的限制。然而，如果方法注解中也包含了类注解的内容，则方法的限制将完全覆盖类的限制。
- `@RunAs`：指示容器以不同的用户身份运行方法。然而，此注解仅在完整的 Java EE 容器中且当你使用容器提供的授权时才有用。Spring Security 不支持此注解。

使用 `@RolesAllowed` 注解非常简单。将它添加到任何方法或类（对于由 Spring 管理的 bean）中，在注解值中指定一个或多个参数。

```java
@RolesAllowed("ADMINISTRATOR")
public interface SettingManagerService {
    @RolesAllowed("ADD_GENERAL_SETTING", "ALTER_GENERAL_SETTING")
    void saveGeneralSettings(Map<String, Object> settings);

    @RolesAllowed("ALTER_MEMBERSHIP_SETTING")
    void saveMembershipSettings(Map<String, Object> settings);
}
```

如果用户尝试在没有权限的情况下调用方法，将抛出 `org.springframework.security.access.AccessDeniedException`。通常你不需要担心捕获这个异常。作为一个 `RuntimeException`，它会导致任何相关的事务回滚并传播，而无需你进行任何输出。Spring 的过滤器链会捕获该异常并向用户返回 403 Forbidden 错误。在少数情况下，你可能需要捕获此异常，但除非是为了用于非 Web 应用程序。

你可以看到，`@RolesAllowed` 和 `@PermitAll` 注解很有用，但仅此而已了。在使用 Spring Security 时，使用其他注解的意义不大。难道就这些吗？这些注解虽然有用，但它们完全不知道用户请求方法执行的操作。如果某些论坛是通过相同的格式进入的，你无法使用 `@RolesAllowed` 来限制对某些论坛的访问而不是所有论坛。Spring 提供了一组更健壮的注解来满足你的需求。

# Secured 注解

`org.springframework.security.access.annotation.Secured` 注解是 Spring Security 对声明式注解的首次尝试。它出现于 Java EE 5 之前的 Common API 可用之前。从实践上来说，`@Secured` 与 `@RolesAllowed` 相同。它接受一个或多个 `GrantedAuthority`，只有当用户拥有其中至少一个已授予权限时，才能执行被注解的方法。

有一个细微的差别：`@RolesAllowed` 适用于任何值，但 `@Secured` 要求值以 `ROLE_` 开头。你指定的任何不以 `ROLE_` 开头的 `GrantedAuthority` 都会被忽略。这是由于访问决策投票者模式（access decision voter pattern）中成员的不同，我们将在下一节中详细介绍。如果你不希望所有的权限名称都以 `ROLE_` 开头，你应该避免使用 `@Secured` 而改用 `@RolesAllowed`。与 `@RolesAllowed` 一样，你可以在类或接口上指定 `@Secured` 以影响该类或接口中的所有方法，也可以在单个方法上指定，或者两者兼顾。在第三种情况下，适用相同的优先级和覆盖规则。

# 788 | 第 27 章 使用授权标签和注解

```java
@Secured("ADMINISTRATOR")
public interface SettingsMutatorService {
    @Secured("ADD_GENERAL_SETTING", "ALTER_GENERAL_SETTING")
    void saveGeneralSettings(Map<String, Object> settings);

    @Secured("ALTER_MEMBERSHIP_SETTING")
    void saveMembershipSettings(Map<String, Object> settings);
}
```

# 用于授权的执行前和执行后注解

Spring Security 的执行前和执行后注解是 Spring Security 现代声明式授权的核心。这组四个注解全部位于 `org.springframework.security.access.annotation` 包中，它们允许你在方法执行之前或之后使用之前读过的表达式。通过 `@RolesAllowed` 和 `@Secured`，你可以在类或接口上、单个方法上或两者兼顾地指定这些注解。如果你在方法和类上指定了同名的执行前或执行后注解，方法上的注解将完成类注解。

`@PreAuthorize` 是你可能用得频繁的注解，它是 Spring Security 支持的特性。你在 `@PreAuthorize` 中指定的安全表达式会在方法执行之前进行求值。该表达式可以引用任何以 `#` 为前缀的方法参数。例如，如果方法有一个名为 `employee` 的参数，你可以使用 `#employee` 访问该参数的值。暴露的 SpEL 变量具有与其对应的参数相同的类型，并且你可以在访问参数属性时调用其上的方法。



@PreAuthorize("isAuthenticated and hasAuthority('USER')")

public interface UserService {

    @PreAuthorize("#userId == authentication.principal.userId || " +
    "hasAuthority('CHANGE_OTHER_USER_PASSWORD')")
    void changePassword(long userId, String oldPassword, String newPassword);

    @PreAuthorize("#userId == authentication.principal.userId || " +
    "hasAuthority('CHANGE_OTHER_USER_DETAILS')")
    void updateDetails(User user);

    @PreAuthorize("#user.userId == 0 and (isAnonymous or " +
    "hasAuthority('CREATE_NEW_USER')")
    void addUser(User user);

}

```

如果表达式求值结果为 `true`，则方法不会被调用并会抛出 `AccessDeniedException`。在这里，你必须小心参数名称的解析。在 Java 8 之前，除非类在编译时带有调试信息，否则 SpEL 无法发现参数名称。这意味着需要将带有调试信息的类编译到生产环境中，而某些开发者倾向于避免这样做。此外，接口不包含调试信息，因此 Spring Security 无法通过调试信息发现接口方法的参数名称。

凭借 Java 8 新的参数名称反射功能以及从 Spring Security 3.2 开始，参数名称的发现变得更加可靠。然而，你可以使用 `@Param` 注解来确保参数名称是正确的。例如，如果方法有一个名为 `employee` 的参数，你可以使用 `#employee` 访问该参数的值。暴露的 SpEL 变量具有与其对应的参数相同的类型，并且你可以在访问参数属性时调用其上的方法。

为了确保参数名称被正确识别，你应该在编译时使用 `-parameters` 标志。这允许 Spring Security 从字节码中检索参数名称，而不需要调试信息。

# 通过声明授权 | 791

如你所见，Spring Security 的执行前和执行后授权注解比通用注解 API（Common Annotations API）或 `@Secured` 强大得多。由于有 SpEL 作为表达式引擎，使用这些注解几乎可以做任何事情。然而，你可能仍然对 `hasPermission` 函数的示例用法感到困惑，因为你可能还没有学习过它。`hasPermission` 使用了 Spring Security 的访问控制列表（ACL），你将在“为对象安全创建访问列表”中学习到它。

> 注意：如果你不想使用 SpEL 表达式而倾向于使用 `@Secured` `@RolesAllowed`，但仍然想获得 `isAnonymous`、`isRememberMe` 和 `isFullyAuthenticated` 安全函数的优势，只需使用特殊情况权限/角色 `IS_AUTHENTICATED_ANONYMOUS`、`IS_AUTHENTICATED_REMEMBERED` 和 `IS_AUTHENTICATED_FULLY` 即可。它们与这些函数的效果相同。

# 使用注解的好处

在看到你基本上可以在某些注解中编写代码后，你可能会想这与在服务方法中编写代码相比有什么改进。你之前不是读过将授权逻辑与业务逻辑分离是一个目标吗？这难道不是直接解决了问题吗？记住你之前读过的关于测试服务的内容：当你为每个单元测试创建一个 `SecurityContext` 并对正例和负例进行测试时，这会变得更加困难。在这种方法中使用注解可以确保授权检查在你的单元测试期间永远不会求值。这允许你专注于测试代码所实现的实际业务逻辑。

另一个重要点是，授权规则是一个契约。当你创建一个 `UserService` 接口时，你是为了建立一个关于所有 `UserService` 实现必须做什么的契约，无论它们如何实现。想象一下切换此 `UserService` 的实现。这些实现类也会有不同的授权规则吗？不。授权规则不是实现细节。它们是契约的一部分，由于它们属于实现——但 Spring Security 的注解支持允许你（但并不要求你）在接口中声明这些授权规则，以便它们成为契约的一部分并适用于任何实现。这与将授权检查嵌入你的应用程序代码中相比，是一个巨大的改进。

# 配置注解支持

Spring Security 默认禁用了注解支持。你必须启用注解支持才能使用本节中列出的任何注解；否则，它们会被忽略。要启用注解支持，你首先需要将 `AuthenticationManager` 暴露为一个 bean。因为你可以有多个安全配置（你将在下一章中学习），`WebSecurityConfigurer` 默认不暴露 `AuthenticationManager` bean。（否则，可能会有重复的 bean）。通过重写配置适配器的 `authenticationManager` 方法可以暴露此 bean。

接下来，你需要添加 `@org.springframework.security.config.annotation.method.configuration.EnableGlobalMethodSecurity` 来配置你的类及其属性。这三个属性允许你指定你想要支持哪些注解。`jsr250Enabled` 控制通用注解 API，而 `secured` 和 `prePostEnabled` 则用于执行前和执行后注解。默认情况下，这所有三种类型都是禁用的，因为这些属性的默认值为 `false`。以下配置使用在第 26 章中创建的 `SecurityConfiguration` 类开启了对所有组的支持：

```java
@Configuration
@EnableWebMvcSecurity()
@EnableGlobalMethodSecurity(
    jsr250Enabled = true, prePostEnabled = true
)
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Bean
    @Override
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManager();
    }
}
```

在大多数情况下，你可能不想启用所有三组注解。事实上，混合这些组可能会导致意料之外的结果，这可能不是你预期的。你通常应该选择这三组中的一组并在整个应用程序中保持一致。在本书的最后两章中，你将专门使用执行前和执行后注解。

你还需要注意代理顺序。

# 理解授权决策 | 795

要简单得多。理解这一决策过程也有助于你排查不符合你预期或愿望的行为。最后，如果你决定从 Spring Security 的默认决策设置切换到 Spring Security 提供的替代设置，掌握 Spring Security 的访问决策机制至关重要。本节将涵盖决策过程以及支持该过程的接口和实现。

# 使用访问决策投票者 (Access Decision Voters)

访问决策投票者（Access Decision Voters）是决策过程的关键执行者。典型的 Spring Security 配置包含多个投票者，它们是 `org.springframework.security.access.AccessDecisionVoter` 的实现。就像政府机构的成员投票是否通过立法一样，AccessDecisionVoters 投票决定是否允许访问应用的某些部分。当询问某个投票者关于是否授予访问权限的意见时，它会根据给定的特定知识投票。如果没有足够的信息来做出知情投票（例如，它不熟悉的某个功能是保护资源的唯一功能），它将从方法返回 `DecisionVoter.ABSTAIN`（抽象）以避免投票。如果它有足够的信息并认为应该授予访问，它将返回 `DecisionVoter.ACCESS_GRANTED`（允许访问）。同样，如果它认为不应该授予访问，它将返回 `DecisionVoter.ACCESS_DENIED`（拒绝访问）。

提供了多种 `AccessDecisionVoter` 实现，Spring Security 会根据你启用和禁用的安全特性配置适当的实现。你的应用程序可能使用一个或多个 `AccessDecisionVoter`。以下列表详细列出了这些实现：

- `org.springframework.security.acl.ACLEntryVoter` 根据 Spring Security 的访问控制列表（ACL）进行投票。如果资源受 `hasPermission` 表达式函数的保护，`ACLEntryVoter` 将放弃投票。该投票者不会被自动配置，事实上，你可能永远不会使用它。你有更好的方法的方法来配置访问列表，我们将在下一节中探讨。
- `org.springframework.security.access.vote.AuthenticatedVoter` 针对特殊角色 `IS_AUTHENTICATED_ANONYMOUS` 和 `IS_AUTHENTICATED_FULL` 起作用。如果它没有被这些角色中的任何一个保护，`AuthenticatedVoter` 将放弃投票。
- `org.springframework.security.annotation.Jsr250Voter` 针对任何使用通用注解 API (JSR 250) 保护的方法进行投票。例如，如果一个方法被标记了 `@RolesAllowed`，`Jsr250Voter` 将根据该注解中指定的权限投票。只有在你启用了对 JSR 250（或其类或接口）的支持时，该投票者才被启用。如果不存在或者访问决策是非方法资源（如 URL），该投票者将放弃投票。
- `org.springframework.security.access.prepost.PreInAuthorizationVoter` 根据 `@PreAuthorize` 和 `.PreFilter` 注解投票。只有在启用了执行前后的访问控制时，它才被启用。对于非方法资源或当方法（或其类或接口）不存在注解时，它将放弃投票。对于 `@PostFilter` 和 `@PostAuthorize` 没有投票者——Spring 将这些注解视为特殊情况处理，因为投票者仅在访问资源之前使用。
- `org.springframework.security.access.vote.RoleHierarchyVoter` 使用 Spring 的角色层级系统做出决策。如果你使用了受保护资源上不存在的角色层级限制，则必须手动创建。本书没有详细介绍角色层级系统的使用，因为通常不建议基于角色的授权（参见第 25 章）。
- `org.springframework.security.access.vote.RoleVoter` 用于受非表达式 URL 限制、方法点表达式以及 `@Secured` 注解保护的资源，以及所有其他情况。它投出一个或多个以 `ROLE_` 前缀的“角色”（这就是为什么你在 `@Secured` 中只使用 `ROLE_` 前缀成员）。如果你启用了 `@Secured` 注解、在 XML `<http>` 配置元素中将 `use-expressions` 设置为 `false`、或者使用了方法点表达式，该投票者将被启用。
- `org.springframework.security.web.expression.WebExpressionVoter` 对保护 URL 资源的表达式做出决策。它获取方法保护决策，并在没有保护特定 URL 的表达式的情况下获取决策。如果你使用 Java 配置或在 XML `<http>` 配置元素中将 `use-expressions` 设置为 `true`，它将被启用。

这种“是”、“否”或“抽象”的投票模式在控制访问的技术中非常常见。几乎所有的防火墙系统都有评估为“接受”、“拒绝”或“中立”的投票者。如果你还记得第 11 章中的 Log4j 过滤器，你会发现它们也使用了类似的模式。这是一个极其灵活的架构，支持所有可能的规则。

# 使用决策管理器 (Decision Managers)

如你所见，有多个内置的投票者，并且可能同时启用多个投票者。事实上，多个投票者可能对特定的访问决策持有非抽象的意见。Spring 如何协调这些差异？访问决策管理器（Access Decision Managers）协调一个或多个投票者的投票，并将它们转换为对访问请求命运的最终决策。

继续用政府机构进行类比，实现 `org.springframework.security.access.AccessDecisionManager` 的决策管理器就像首相或政府机构的议长。它统计票数，并确定是否满足了授予访问的相应规则。归结底，决策器是决定是否不抛出 `AccessDeniedException` 的组件。

你的应用程序可以同时配置多个决策管理器。如果你启用了全局方法安全，这将创建一个决策管理器来管理对受保护方法的访问。此决策器可以使用上述大多数投票者。同样，在 HTTP 配置中配置 URL 限制会创建另一个决策管理器，用于控制对应用程序 URL 的访问。`WebExpressionVoter` 的存在仅是为了为此管理器提供服务，因为它在应用程序的其他地方没有用处。

Spring Security 带有三种标准的 `AccessDecisionManager` 实现；但是，你可以轻松地创建自己的投票者。你可以将这些实现用于方法安全、URL 安全或任何需要决策器的地方。默认情况下，当所有投票者都抽象时，访问是被拒绝的，但每个标准实现都提供了一个设置，用于确定在这种情况下是否授予访问。

# 通过肯定进行决策 (Deciding by Affirmation)

`org.springframework.security.access.vote.AffirmativeBased` 是最简单的决策管理器。如果至少有一个非抽象的投票者同意，该决策管理器就会授予访问。即使其他投票者拒绝访问，只要至少有一个投票者返回 `ACCESS_GRANTED`，此决策器仍然会授予访问。你可能看出为什么这种模式在某些情况下是有问题的，但在大多数情况下它是完全足够的。通常情况下，你不会有匹配的 URL 限制，但如果确实有，只要有一条规则允许，允许访问通常是没问题的。它适用于方法限制。例如，你很少在同一个方法上同时使用 `@Secured` 和 `@PreAuthorize`，但如果你确实这样做，逻辑上可以推断这些选择应该是“或”关系，而不是“非或”关系。

# 通过共识进行决策 (Deciding by Consensus)

共识决策可能是你最熟悉的。所有的共和和民主政府形式都基于共识的简单原则运行，无论是简单多数还是三分之二的同意。`org.springframework.security.access.ConsensusBased` 决策管理器根据简单多数原则运行。如果半数加一的非抽象投票者批准，则授予访问。

例如，如果你有 7 个投票者，4 个投票者授予访问，2 个投票者允许访问，1 个投票者拒绝，则授予访问。然而，如果 1 个投票者允许，2 个投票者拒绝，则拒绝访问。当然，如果你遇到平局问题（即允许和拒绝的数相等），`ConsensusBased` 决策管理器提供了一个设置来确定平局策略。默认情况下，在平局时授予访问。

# 通过一致性进行决策 (Deciding by Unanimity)

标准决策器的自然结论是要求所有非抽象投票者都投赞成票——`org.springframework.security.access.vote.UnanimousBased`。所有非抽象投票者都必须授予访问；否则此决策器将拒绝访问。这是一个非常严格的策略，但在某些情况下仍然适用。

为全局方法安全配置不同的 `AccessDecisionManager` 相对简单。如果你的 `@Configuration` 类没有继承 `GlobalMethodSecurityConfiguration`，请进行该更改。然后重写 `accessDecisionManager` 方法以返回一个 `ConsensusBased` 或自定义实现。不要忘记在你返回的任何管理器中包含投票者。为 Web 安全配置不同的决策器很容易：只需将其添加到 `configure(HttpSecurity)` 方法中即可。

```java
@Override
```



protected void configure(HttpSecurity security) throws Exception {

    security
        .authorizeRequests()
        .accessDecisionManager(new CustomDecisionManager())

}

## 为对象安全创建访问控制列表 (ACL)

到目前为止，本章介绍了一种相对简单的授权方法，该方法仅根据用户的权限或其是否“拥有”某个资源或对象来决定其对该资源的访问权限。这种方法有时是完全足够的。简单的应用程序，尤其是输入极少的应用程序，通常只运行极少数授权规则。即使是像用户论坛这类相当复杂的应用程序，在授权方面其实也是简单的。然而，有时您需要更复杂的解决方案。

访问控制列表（ACL）是一种更复杂的对象安全处理方法，它定义了针对每个用户、每个对象的权限。对于给定的对象类型 `Foo`，用户 `Bar` 可能对该对象的不同实例拥有完全不同的权限。这超出了所有权的范畴：一个用户可能管理某些实例，写入另一些，删除另一些，并且最后完全无法访问另一些。操作系统的文件权限（如 Microsoft Windows 和 Apple Mac OS X 中的）是基于 ACL 的。Linux 操作系统也支持 ACL 权限；但是，默认情况下它们并未启用，且许多用户并不熟悉如何使用。

### 理解 Spring Security ACL

如果您曾经在 Windows、Mac OS X 或带有 ACL 权限的 Linux 中管理过权限，那么您将非常熟悉 ACL 的工作原理。您文件系统上的每个文件都有一组权限，对于任何给定的文件，您可以为访问该文件系统的每个用户定义不同的权限。

正如您可以想象的，支持这种系统并非易事。除了复杂的权限管理机制外，系统还需要大量的后端数据来存储这些权限。如果您想象一个拥有百万条数据记录和百万用户的用户的系统，那么仅仅为了这些用户对这一个对象的权限，您可能拥有数万亿条数据！无论您存储这些数据的效率有多高，您面对的都是几个 TB的数据。请理解这是一种极端情况（大多数用户只拥有每条数据一小部分的权限），但无疑您能看到设计这样一个系统有多重要。

Spring Security 自带了一个成熟的、经过行业测试的 ACL 系统，可以对您的用户权限进行细粒度控制。该系统的核心组件是 `org.springframework.security.acls.model.Acl` 接口。它代表单个对象的访问控制列表，每个领域对象都有以 `org.springframework.security.acls.model.ObjectIdentity` 形式表示的领域对象 ID、对象所有者（创建它的用户）以 `org.springframework.security.acls.model.Sid` 形式表示的 ID，以及分配给允许以某种方式使用该对象的用户的权限列表（即 `org.springframework.security.acls.model.AccessControlEntry` 列表）。

每个 `AccessControlEntry` 封装了持有该条目的的用户 ID 以及分配给该条目的的 `org.springframework.security.model.Permission`。权限用位掩（bitmasks）表示——这是一种高效的存储机制，数字的每一位代表一个单独的权限。例如，我可能控制读取权限，而 B 控制写入权限。`Acl` 还可以包含一个父级 ACL，从中继承该父级的 `AccessControlEntries`。

> 注意：位掩即使对经验丰富的开发者来说也可能是令人畏的。这种技术也用于 Unix 文件系统权限和许多其他活动。请放心，Spring Security 抽象了位掩的困扰；您永远不需要直接处理它。标准实现 `org.springframework.security.domain.BasePermission` 理解读取、创建、删除和管理权限，这对于大多数情况已经足够。如果您需要支持其他权限，必须实现自己的 `Permission` 类，并告诉它如何转换您实现中的位掩。

`org.springframework.security.acls.domain.PrincipalSid` 有两种标准实现，对应于 `Authentication`，而 `org.springframework.security.acls.domain.GrantedAuthority` 对应于 `GrantedAuthority`。如果您使用 `GrantedAuthority` 来表示角色和组，并且当你想向特定角色或组中的每个人授予权限时，后者非常有用。对于这两种实现，SID 最终都以 `Authentication` 或 `GrantedAuthority` 的字符串形式（用户名或权限名称）表示。如果您想用长用户 ID 来表示这些，可以轻松地实现自己的 `SID`。

ACL 由 `org.springframework.security.acls.model.AclService` 的实现驱动。该服务可以根据对象标识加载 ACL 以进行权限评估。它让您能够使用 `hasPermission` 表达式来控制对方法的访问——通过使用 `AclService` 实现来为领域对象调用此函数。

如果您愿意，可以实现自己的 `AclService`，但不建议这样做。Spring 的 `org.springframework.security.acls.jdbc.JdbcAclService` 设计用于高效地在关系型数据库中存储 ACL 并以高性能的方式检索它们。spring 的 JAR 构包含了为 MySQL/MariaDB (`createAclSchemaMys.sql`)、PostgreSQL (`createAclSchemaPostgres.sql`) 和 HSQLDB (`createAclSchema.sql`) 创建所需表的 SQL 脚本。如果您决定使用不同的数据库，可以轻松地翻译这些脚本之一。由于 `JdbcAclService` 使用标准的 ANSI SQL 特性进行数据操作，它应该兼容几乎任何流行的关系型数据库。

四张 ACL 表承担以下功能：

- `acl_sid`：唯一定义系统中的每个 `Sid`，用于与其他表的引用完整性。通常情况下，假设您只使用 `PrincipalSid`，那么系统中的每个用户在该表中都有一条记录。
- `acl_class`：唯一定义应用程序中的每个领域对象类。与 `acl_sid` 类似，此表用于引用完整性。
- `acl_object_identity`：对应 `Acl` 类，持有 `ObjectIdentity`、`Sid` 和其他 `Acl` 属性。对于系统中每个受 ACL 的领域，在该表中都有一条记录。
- `acl_entry`：映射到每个 `Acl` 的 `AccessControlEntry` 列表。

> 警告：acl_entry 表可能会增长到数十亿或万亿条记录，取决于应用程序中领域对象的数量、这些领域对象的持久实例数量以及系统中用户的数量。您应该始终监控此表的性能问题，并根据需要调整索引、系统属性或硬件。

## 配置访问列表

如果您打算实现自己的 ACL 系统，如何配置它在很大程度上取决于您的如何设计。您要么需要实现一个 `AclService` 并修改 `DefaultMethodSecurityExpression` 以使用该服务的 `AclPermissionEvaluator` 来处理它，要么定义自己的 `PermissionEvaluator` 实现。

配置 Spring 的 ACL 实现要复杂得多，但一旦设置好，它会为您完成大部分工作。您首先应该在应用程序中创建 Spring Security ACL 方法，并定义一个全局方法安全的内部 `@Configuration` 类。

```java
@Configuration
@EnableGlobalMethodSecurity(
    prePostEnabled = true, order = 0,
    mode = Advice.PROXY, proxyTargetClass = false
)
public static class MethodAuthorizationConfiguration
extends GlobalMethodSecurityConfiguration
{
    private static final Logger log = LogManager.getLogger();
    ...
}
```

## 为对象安全创建访问控制列表 (ACL)

> 注意：spring-security-acl Maven 构件已经你应用程序中包含的其他 Spring Security 构件的运行时依赖。但是，如果你打算使用 ACL，你可以将此依赖变为编译时依赖。

```xml
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-acl</artifactId>
  <version>3.2.0.RELEASE</version>
  <scope>compile</scope>
</dependency>
```

你需要配置 `org.springframework.security.acls.domain.AuthorizationStrategy` 的实现类。ACL 系统使用它来确定当前主体（principal）是否有权限访问 ACL 服务的管理功能（例如，更改特定对象的 ACL）。标准实现允许：如果主体是该对象的所有者、拥有该对象的管理权限，或者在策略构造函数中具有任何授权列表，则允许使用这些管理方法。

```java
@Bean
public ACLAuthorizationStrategy aclAuthorizationStrategy() {
    return new ACLAuthorizationStrategyImpl(
        new SimpleGrantedAuthority("ADMINISTRATOR")
    );
}
```

接下来，你需要配置一个 `org.springframework.security.acls.model.PermissionGrantingStrategy`。此接口允许你自定义权限的评估方式，但标准实现通常已经足够。你需要一个 `org.springframework.security.acls.domain.AuditLogger` 来记录 ACL 授权事件。按照下面的代码进行配置，使用 lambda 表达式来提供日志行为。你可以采取不同的方法，例如使用默认的 `org.springframework.security.acls.domain.ConsoleAuditLogger` 将日志输出到控制台。

现在，你需要设置 `org.springframework.security.acls.model.ACLCache` 实现。为了优化性能，ACL 系统需要缓存条目直到下一次需要它们。Spring Security 提供了 ACL 实现，它们可以使用 Eithercache（一种流行的 Java 开源分布式缓存系统）或 Spring Framework 的缓存系统。出于演示目的，基于 `java.util.concurrent.HashMap` 的 Spring Framework 缓存就足够了。如果你的应用程序是集群的，你必须提供合适的分布式缓存实现。

```java
@Bean
public AclCache aclCache()
{
    return new SpringCacheBasedAclCache("Security",
        new ConcurrentMapCache(
            this.permissionGrantingStrategy(),
            this.aclAuthorizationStrategy()
        ));
};
```

配置好这些系统后，你需要设置 JDBC ACL 实现并添加 `PermissionEvaluator`。`JdbcAclService` 和 `org.springframework.security.acl.jdbc.BasicLookupStrategy` 协同工作，使用你的应用程序数据 获取 ACL 条目并在适当的时候对其进行缓存。`AclPermissionEvaluator` 和 `org.springframework.security.acl.AclPermissionCache` 协同工作以评估 `hasPermission` 表达式。

```java
@Bean
public LookupStrategy lookupStrategy()
{
    return new BasicLookupStrategy(
        this.dataSource,
        this.aclCache(),
        this.aclAuthorizationStrategy(),
        this.permissionGrantingStrategy()
    );
};
```

```java
@Bean
public AclService aclService(this.dataSource, this.lookupStrategy())
{
    return new JdbcAclService(this.dataSource, this.lookupStrategy());
};
```

```java
@Override
public MethodSecurityExpressionHandler createExpressionHandler()
{
    DefaultMethodSecurityExpressionHandler handler =
        new DefaultMethodSecurityExpressionHandler();
    handler.setPermissionEvaluator(new AclPermissionEvaluator(
            this.aclService())
    );
    handler.setPermissionCacheOptimizer(new AclPermissionCacheOptimizer(
            this.aclService()
    );
    return handler;
};
```

最后，你可以在方法中添加 `hasPermission` 表达式，以根据 ACL 权限限制访问。大部分情况下，此配置由简单的 Bean 组成，你应该非常熟悉如何使用 XML 配置这些组件。

这是最佳实践，如果可能的话，你应该避免这样做。相反，惯例是提供一个 `UserDetailsService` 实现，并在必要时提供一个自定义的 `UserDetails`。

## 决定 User Details 实现

在设计系统时，你最终需要决定是否将用于持久化的用户对象与用于身份验证和授权的用户对象耦合在一起。分离的优势在于，你真的不需要（甚至不想）在安全上下文中携带一个可变的用户对象，而保持它们分离可以确保这一准则。使用同一个对象的用处是，你不需要花费大量工作就可以将用户实体嵌入到其他实体中。最终，你可以决定最适合你的方法。

为了简单起见，Customer Support 应用程序将 `UserDetails` 实现和实体合并在同一个对象中。对 `UserPrincipal` 的更改非常简单。它实现了 `UserDetails` 而不是 `Authentication`，并且实现了 `org.springframework.security.core.CredentialsContainer`，以便 Spring Security 在认证过程完成后清除凭密码。

```java
public class UserPrincipal implements UserDetails, CredentialsContainer, Cloneable {
    private static final long serialVersionUID = 1L;
    private long id;
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
```



```java
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
@XmlElement @JsonProperty() { ... }
public boolean isAccountNonExpired() { ... }
public void setAccountNonExpired(boolean accountNonExpired) { ... }

@Override
@XmlElement @JsonProperty() { ... }
public boolean isAccountNonLocked() { ... }
public void setAccountNonLocked(boolean accountNonLocked) { ... }

@Override
public boolean isCredentialsNonExpired() { ... }
public void setCredentialsNonExpired(boolean credentialsNonExpired) { ... }

@Override
@XmlElement @JsonProperty() { ... }
public boolean isEnabled() { ... }
public void setEnabled(boolean enabled) { ... }
}
```

本课程需要在 `UserPrincipal` 表中添加一些额外的列。如果你是第一次运行 Customer Support 应用程序，只需运行应用程序中 `create.sql` 中的 SQL 脚本，即可创建所需的所有表和索引。否则，请使用以下代码添加必要的列。

```sql
USE CustomersSupport;

ALTER TABLE UserPrincipal
ADD COLUMN AccountNonExpired BOOLEAN NULL DEFAULT TRUE,
ADD COLUMN AccountNonLocked BOOLEAN NULL DEFAULT TRUE,
ADD COLUMN CredentialsNonExpired BOOLEAN NULL DEFAULT TRUE,
ADD COLUMN Enabled BOOLEAN NULL DEFAULT TRUE;

ALTER TABLE UserPrincipal
MODIFY COLUMN AccountNonExpired BOOLEAN NULL,
MODIFY COLUMN AccountNonLocked BOOLEAN NULL,
MODIFY COLUMN CredentialsNonExpired BOOLEAN NULL,
MODIFY COLUMN Enabled BOOLEAN NULL;
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
    UNIQUE KEY UserPrincipal_Authority_User_Authority (UserId, Authority),
    CONSTRAINT UserPrincipal_Authority_User_Id FOREIGN KEY (UserId)
    REFERENCES UserPrincipal(UserId) ON DELETE CASCADE
) ENGINE = InnoDB;
```

## 新的用户实体

旧的 `Authentication` 不再需要处理身份验证。相反，它扩展了 `UserDetailsService`，因此将其重命名为 `UserService`（及其实现重命名为 `DefaultUserService`）是合理的。

```java
@Validated
public interface UserService extends UserDetails {
    @Override
    UserPrincipal loadUserByUsername(String username);
}
```

```java
@Service
public class DefaultUserService implements UserService {
    ...
    @Override
    @Transactional
    public UserPrincipal loadUserByUsername(String username) {
        UserPrincipal principal = userRepository.getByUsername(username);
        // 确保权限和密码已加载
        principal.getAuthorities().size();
        principal.getPassword();
        return principal;
    }
}
```

需要对由 `UserService` 支持的 `DaoConfigurationProvider` 进行微调，并告诉 Spring Security 在认证后清除凭据。

## 使用标签和注解

### 保护你的服务方法

在第 26 章中，你添加了一个简单的授权规则，通过要求身份验证来保护所有 URL。现在你需要保护你的服务方法，以便某些用户可以执行任务。首先，你必须启用全局方法安全。

```java
@Configuration
@EnableWebMvcSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Inject UserService userService;
    @Override
    protected void configure(AuthenticationManagerBuilder builder) throws Exception {
        builder
            .userDetailsService(userService)
            .passwordEncoder(new BCryptPasswordEncoder())
            .and()
            .eraseCredentials(true);
    }
}
```

### 为 Customer Support 添加授权

在这种情况下，不需要创建一个扩展自 `GlobalMethodSecurity` 的内部类，因为方法安全中没有内容需要自定义。

```java
@Configuration
@EnableGlobalMvcSecurity
@EnableGlobalMethodSecurity(
    prePostEnabled = true, order = 0, mode = AdviceMode.PROXY,
    proxyTargetClass = false
)
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {
    @Bean
    @Override
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManager();
    }
}
```

> 注意：这里全局方法安全的代理顺序被设置为 0。此外，异步执行方法的代理顺序为 1，而事务支持的代理顺序为 2。这确保了安全首先运行，然后是异步方法执行，最后是事务操作。

保护 `TicketService` 非常简单。你可以使用 `@Authorize` 和简单的表达式来保护所有方法，由于你只想编辑自己的订单和评论（除非他们拥有编辑任何评论的管理员权限），你必须将 `Tickets` 和 `TicketComments` 的 `save` 方法拆分为 `create` 和 `update` 方法。`TicketController`、`TicketRestEndpoint` 和 `TicketSoapEndpoint` 需要同步更改的方法名（未显示）。注意使用 `@P` 来指示 Spring Security 表达式的参数名。

```java
public interface TicketService {
    @NotNull
    @Authorize("hasAuthority('VIEW_TICKET')")
    List<Ticket> getAllTickets();

    @NotNull
    @Authorize("hasAuthority('VIEW_TICKET')")
    PageResult<Ticket> search(Page...);

    @Authorize("hasAuthority('VIEW_TICKET')")
    Ticket getTicket(Long id);

    @Authorize("#ticket.id == 0 && hasAuthority('CREATE_TICKET')")
    void create(@NotNull(message = "#{validate.ticketService.save(ticket)}") @Valid Ticket ticket);

    @Authorize("#authentication.principal.equals(#{ticket.customer}) or hasAuthority('EDIT_ANY_TICKET')")
    void update(@NotNull(message = "#{validate.ticketService.save(ticket)}") @Valid Ticket ticket);

    @Authorize("hasAuthority('DELETE_TICKET')")
    void delete(Long id);
}
```

# 810 | 第 27 章 使用权限标签与注解

```java
void deleteTicket(long id);

@NonNull
@PreAuthorize("hasAuthority('VIEW_COMMENTS')")
Page<TicketComment> getComments(Pageable pageable) { ... }

@PreAuthorize("#comment.id == 0 and hasAuthority('CREATE_COMMENT')")
void create(
    @NonNull(message = "{validate.ticketService.saveComment}")
    @Valid("#comment") Ticket comment,
    @Min(value = IL, message = "{validate.ticketService.saveComment}")
    long ticketId
);

@PreAuthorize("authentication.principal.equals(#comment.user) or " +
    "hasAuthority('EDIT_OWN_COMMENT') or " +
    "hasAuthority('EDIT_ANY_COMMENT')")
void update(@NonNull(message = "{validate.ticketService.saveComment}")
    @Valid("#comment") Ticket comment);

@PreAuthorize("hasAuthority('DELETE_COMMENT')")
void deleteTicket(long id);

@PreAuthorize("hasAuthority('VIEW_ATTACHMENT')")
Attachment getAttachment(long id);
```

你还需要保护聊天请求的安全，这引入了更多的复杂性。在这里，你不仅需要检查用户是否有权执行某项任务，还需要检查他们在发送消息或离开会话时实际上是该聊天会话的成员。

```java
public interface ChatService {
    @PreAuthorize("authentication.principal.username.equals(#user) and " +
        "hasAuthority('CREATE_CHAT_REQUEST')")
    Create createResult(@user String user);

    @PreAuthorize("authentication.principal.username.equals(#user) and " +
        "hasAuthority('START_CHAT')")
    JoinResult joinSession(long id, @user String user);

    @PreAuthorize("authentication.principal.username.equals(#username) and " +
        "#user.equals(#session.representativeUsername)) and " +
        "hasAuthority('CHAT')")
    ChatMessage leaveSession(@session ChatSession session, @reason String reason);

    @PreAuthorize("authentication.principal.username.equals(#message.user) and " +
        "(#message.user.equals(#session.customerUsername)) or " +
        "(#message.user.equals(#session.representativeUsername)) and " +
        "hasAuthority('CHAT')")
    void logMessage(@session ChatSession session, @message ChatMessage message);

    @PreAuthorize("hasAuthority('VIEW_CHAT_REQUESTS')")
    List<ChatSession> getPendingSessions();
}
```

然而，你还需要考虑其他事情。目前，Spring Security 尚未支持处理 WebSocket 会话。这是 Spring Security 4.0 的计划功能，希望它会在 2014 年年中发布。该版本应该能为你处理许多问题，例如覆盖 Session 中的 Principal，以及在 HttpSession 注销时关闭 WebSocket 会话。事实上，它可以消减你应用程序中的大量代码。但目前，你必须自行采取一些特殊步骤。当 WebSocket 会话被移交并开始异步通信时，安全上下文（Security Context）会被清除。为了补偿这一点，你必须创建一个方法来处理受保护的操作。

```java
private void doSecured(SecuredAction secureAction) {
```



```java
SecurityContextHolder.setContext(this.securityContext);

try {

  secureAction.execute();

} finally {

  SecurityContextHolder.clearContext();

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
public static class EndpointConfigurator extends SpringConfigurator {

  ...

  @Override

  public void modifyHandshake(ServerHandshake config, HandshakeRequest request, HandshakeResponse response) {

    ...

    config.getUserProperties().put(SECURITY_CONTEXT_KEY, SecurityContextHolder.getContext());

    ...

  }

}
```

你必须确保所有的 `@OnOpen`、`@OnClose`、`@OnMessage` 和 `@OnError` 方法（以及 WebSocket 容器可能调用的任何其他方法）都在受保护的操作中执行。例如，这里是 `@OnError` 方法：

```java
@OnError

public void onError(Throwable e) {

  this.doSecured(() -> {

    log.warn("Error received in WebSocket session.", e);

    synchronized(this) {

      if(this.closed) {

        // ...

      }

    }

  });

}
```

你最后需要考虑的是会话列表。这是一个管理级功能，但该服务（Spring 的 `SessionRegistry`）并不受你控制，因此你无法为该服务添加注解。对于这一点，你将需要退回到 `SecurityConfiguration` 中的标准 URL 规则。现在你已经知道了应用程序中所有的安全操作，你需要为你的用户分配权限。如果你只是在数据库中运行 `.sql` 脚本，那么就像已经为你做的那样，你必须先找到插入语句并运行它们，以授予预先填充的用户（Nicholas, Sarah, Mike）“自定义”权限，并向 John 授予 Mike 的“代表性”权限。

```sql
INSERT INTO PrincipalAuthority (UserId, Authority) VALUES (1, 'VIEW_TICKETS'), (1, 'VIEW_TICKET'), (1, 'CREATE_TICKET'), (1, 'EDIT_OWN_TICKET'), (1, 'VIEW_COMMENTS'), (1, 'CREATE_COMMENT'), (1, 'EDIT_OWN_COMMENT'), (1, 'VIEW_ATTACHMENT'), (1, 'CREATE_CHAT_REQUEST'), (1, 'CHAT');

INSERT INTO PrincipalAuthority (UserId, Authority) VALUES (2, 'VIEW_TICKETS'), (2, 'VIEW_TICKET'), (2, 'CREATE_TICKET'), (2, 'EDIT_OWN_TICKET'), (2, 'VIEW_COMMENTS'), (2, 'CREATE_COMMENT'), (2, 'EDIT_OWN_COMMENT'), (2, 'VIEW_ATTACHMENT'), (2, 'CREATE_CHAT_REQUEST'), (2, 'CHAT');

INSERT INTO PrincipalAuthority (UserId, Authority) VALUES (3, 'VIEW_TICKETS'), (3, 'VIEW_TICKET'), (3, 'CREATE_TICKET'), (3, 'EDIT_OWN_TICKET'), (3, 'VIEW_COMMENTS'), (3, 'CREATE_COMMENT'), (3, 'EDIT_OWN_COMMENT'), (3, 'VIEW_ATTACHMENT'), (3, 'CREATE_CHAT_REQUEST'), (3, 'CHAT');

INSERT INTO PrincipalAuthority (UserId, Authority) VALUES (4, 'VIEW_TICKETS'), (4, 'VIEW_TICKET'), (4, 'CREATE_TICKET'), (4, 'EDIT_OWN_TICKET'), (4, 'VIEW_COMMENTS'), (4, 'CREATE_COMMENT'), (4, 'EDIT_OWN_COMMENT'), (4, 'VIEW_ATTACHMENT'), (4, 'CREATE_CHAT_REQUEST'), (4, 'CHAT');
```

# 使用 Spring Security 标签库

你还需要保护聊天请求的安全，这引入了更多的复杂性。在这里，你不仅需要检查用户是否有权执行某项任务，还需要检查他们在发送消息或离开会话时实际上是该聊天会话的成员。

# 814 | 第 27 章 使用授权标签和注解

所有的 Spring Security 标签提供了如 `<security:authorize>` 和 `<security:accesscontrollist>` 标签的属性，指定的变量包含评估规则的布尔结果。如果你使用属性，则该标签不能嵌套。对于其他标签，标签存储在指定的变量中。`WEB-INF/jsp/view/chart.jsp` 演示了使用 `<security:authorize>` 的 `var` 属性，如果用户没有 `START_CHAT` 权限，则从列表中省略链接。

```jsp
<security:authorize access="hasAuthority('START_CHAT')" var="canJoin"/>
<spring:message code="message.chatlist.instruction"/>:<c:br /><br />
<c:forEach items="${sessions}" var="s">
<c:choose>
<c:when>${s.username}<a href="/"></a></c:when>
<c:otherwise>${s.username}</c:otherwise>
</c:choose>
```

通过这些更改，客户支持应用程序已准备就绪。继续编译它，为你的 IDE 启动 Tomcat，并访问 `http://localhost:8080/support`。以不同的用户登录，并通过列出和创建工单、列出会以及参与聊天会来测试授权系统是否正常工作。如果你愿意，可以设置安全属性 `spring.security.disableUISecurity`，该属性会禁用 `<security:authorize>` 标签，使其内容始终被渲染，从而更容易尝试对资源进行未经授权的访问，并确保安全方法正常运行。

> 注意：如果你以前从未运行过客户支持应用程序，或者不记得它的用户名和密码，请查阅 `create.sql` 脚本。每个用户的 `INSERT` 语句都包含一个带有用户明文密码的 SQL 注释。

### 总结

在本章中，你学习了许多关于在 Spring Security 中授权用户的知识。你探索了 URL 安全和全局安全方法，以及许多不同的安全方法注解及其使用方法。你学习了 Spring Security 如何做出访问决策以及投票者如何为这些决策贡献，还了解了 Spring Security 强大的访问控制列表（ACL）系统。最后，你为 Multinational Widget 的客户支持应用程序添加了授权。你将 `UserPrincipal` 从 `Authentication` 转换为 `UserDetails`，配置了安全方法，使用了带有安全标签库的用户界面，并采取了特殊步骤在 WebSocket 端点中维护 `SecurityContext`。

完成客户支持应用程序仅剩最后一件事：你还没有安全且功能完全的 Web 服务端点。在书的最后一个章节中，你将学习 Web 安全和 OAuth，并将 Spring Security OAuth 集成到客户支持应用程序中。

# 使用 OAuth 安全 RESTful Web 服务

本章内容

- 理解 Web 服务安全
- OAuth 简介
- OAuth 1.0a 和 2.0 的比较
- 在 Spring Security 中使用 OAuth
- 完成客户支持应用程序
- 编写 OAuth 客户端应用程序

本章 WROX.COM 代码下载

你可以在 `http://www.wrox.com/goavaforwebapps` 的 Download Code 标签下找到本章的 wrox.com 代码下载。本章的代码分为以下主要示例：

- Customer-Support-v21 项目
- OAuth-Client 项目

本章的新 MAVEN 依赖

除了之前章节引入的 Maven 依赖项外，你还需要以下 Maven 依赖项：

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



# 理解 Web 服务安全

到第四部分为止，你已经探索了身份验证相关的概念和技术，并将新知识应用于保护 Web 用户界面。第 17 章你学习了 `SOAP` 和 `RESTful` Web 服务，但直到现在你一直让这些 Web 服务处于未保护状态。在本章中，你学习了 Web 服务安全以及保护 Web 服务的各种方法。你探索了 `OAuth` 标准并将其集成到客户支持应用程序中。最后，你创建了一个非常简单的 Web 服务客户端来测试客户 `RESTful` Web 服务。

# 比较 Web GUI 和 Web 服务安全

保护 Web 服务与保护 Web GUI 是一项完全不同的任务。你不再需要担心某些漏洞。因为没有用户必须填充的图形表单，所以你不需要担心跨站请求伪造（`CSRF`）。由于缺少 `JavaScript`，你不需要担心跨站脚本（`XSS`）。由于你使用了 `HTTP` 会话和 `Cookie`，你不会受到会话固定攻击（`session fixation attacks`）的影响；但你可能会面临新的类似的漏洞。

现在，不要误会。这并不是说使用你 Web 服务的客户端应用程序开发人员不需要担心这些漏洞——他们需要。此外，如果你使用 Web 服务来支持 Web 用户界面，你仍然需要记住这些漏洞。

3. 你做了一项更改，实际上让你的用户更安全了，但让他们觉得不安全了。这是一件糟糕的事情。如果用户感到不安全而停止使用你的网站，那么增加安全性也是徒劳的。你可以通过更好的公关方式来处理这项更改，从而避免这种困境。

4. 你做了一项更改，实际上让你的用户变得不安全，同时也让他们觉得不安全。这非常糟糕。不要让你的用户变得不安全。然而，如果你的用户决定他们感到没必要的不安全，他们就会停止使用你的服务，而只有你将承担后果。

5. 你做了一项更改，实际上让你的用户变得不安全，同时也让他们觉得一样安全甚至更不安全。是的，这实际上比后果 4 更糟糕。你可能在短期内获益，事实上，你可能永远不会被发现。但很有可能你的用户最终会承担后果，而当他们发现自己被骗了时，他们可能会回来要求赔偿。

显然，你希望设计一个身份验证和授权系统，让每个功能都达到后果 1。由于这只在完美世界中才可能，你现实的做法是坚持后果 1 和 2，尽可能让许多功能产生后果 1。如果你的安全功能导致了后果 3、4 或 5 的结果，你必须后退一步并重新评估你的方法。

> 你面临令牌被盗窃的风险。这种风险与凭据被盗窃的风险没有本质区别。事实上，如果你频繁更换令牌（至少每天一次），你实际上可以让事情更安全，因为用户通常不愿频繁地更改密码。

> 你面临着令牌伪造的问题。你可以安全地缓解这个问题（你将在下一节中学习到这一点）。

无论这些缺点如何，令牌都是一种非常安全且有效的方法，是整个行业广泛使用的、用于保护 Web 服务的方案。像往常一样，重新发明轮子意义不大，而且已经有现成的工具可以在 Web 服务应用程序中集成强有力的安全防护。其中一个你在本章中用到的工具就是 `OAuth`。

# 介绍 OAuth

`OAuth` 是一种由 `Twitter` 的 `Blaine Cook`、`Magnolia` 的 `Larry Halff`、曾任于 `Google` 及其他几公司的开源倡导者 `Chris Messina` 以及来自 `Facebook` 的开放标准倡导者 `David Record` 创立开放授权标准。你可能疑惑使用“授权”一词来描述 `OAuth` 的原因。你们不应该是在寻找身份验证的解决方案吗？不，你们已经有解决方案了！事实上，你们有许多解决方案！基础的、摘要的、表单、`Windows`、智能卡——列表层列不穷。

你不需要新方法来建立用户的身份；你已经是这方面的专家了。你真正需要的是一种方法在未来的请求中继续这种身份验证，以确定该用户被授权访问该 Web 服务。这显然强调了划分身份验证和授权界限的模糊线条。两者关系密切，并且相互依赖。在某种程度上，你甚至可以将身份验证视为授权的形式。至少，身份验证始终是授权的第一步。明确的是，`OAuth` 是一种授权标准，但它与身份验证紧密相关。

> 警告：此书不是任何版本 `OAuth` 的权威指南。`OAuth` 的细节和细微差别无法在一个章节中完全涵盖。这可以帮助你从一个简单的 `OAuth` 系统开始，但在阅读规范和支持文档之前，你不应该将 `OAuth` 部署到你的生产环境中。你可以在这里分别找到 `OAuth 1.0a`、`OAuth 2.0` 和 `OAuth 2.0 Bearer Tokens` 的 `IETF` 标准。

# 介绍核心参与者

`OAuth` 的所有版本都有官方术语来标识身份验证和授权过程中的关键参与者。了解这些术语并理解每个参与者在 `OAuth` 会话中扮演的角色至关重要。这些术语在文中经常出现，且没有进一步说明，因此请在继续之前确保你已经清楚理解。

- 客户端（`client`）是任何能够使用 `OAuth` 向 Web 服务 `API` 发起请求的 `HTTP` 应用程序。
- 资源所有者（`resource owner`）是授权的实体，通常是用户。
- 授权服务器（`authorization server`）负责验证资源所有者并颁发令牌的服务器。
- 受保护资源（`protected resource`）是用户在提供有效令牌后通过资源服务器（`resource server`）访问的资源。
- 令牌（`token`）是用于授权请求的凭据，由授权服务器颁发。

> **注意** 图 28-1 至 21-3 将在本章的稍后部分进行讨论，并环绕着更多对图表内容的讨论。在处理此列表时，请参考这些图表。

- 客户端没有该资源所有者的令牌凭据，无法访问受保护的资源（见下文图 28-1）。
- 客户端拥有资源所有者的有效令牌凭据，可以访问受保护的资源（图 28-2）。
- 客户端拥有资源所有者的已过期或撤销令牌，无法访问受保护的资源（图 28-3）。

每种情况都会导致一组不同的操作，最终授予对受保护资源的访问权限（假设允许此类访问）。在客户端没有资源所有者令牌凭据的情况下，它首先（对资源所有者透明）向临时凭据请求端点发送一个空的 `HTTP` 请求（客户端已知道该 `URL`）。此请求使用 `Authorization` `OAuth` 头部和多个授权头部协议来通过服务器对客户端进行身份验证。

- `realm` 命名最终访问的应用程序或资源，就像标准的基础认证或摘要认证一样。
- `oauth_consumer_key` 包含客户端凭据中的标识符（客户端提前从服务器获取）。
- `oauth_signature_method` 是正在采用的签名机制。
- `oauth_timestamp` 是发送请求时的时间戳，以自 `Unix` 纪元起的秒为单位。
- `oauth_nonce` 是请求的唯一标识符，永不重复（以防止重放攻击）。
- `oauth_callback` 是客户端通过身份验证并获得访问权限后，服务器应该返回的 `URI`。
- `oauth_signature` 是使用所有这些参数、请求的各个部分以及客户端凭据中的密钥计算出的签名。

> **注意** 需要说明的是，`Authorization` 头部只是客户端可能用于传输协议参数的方法之一。当请求为 `x-www-form-urlencoded`（较不推荐）时，它也可能使用资源实体参数，并使用请求 `URL` 参数（最不推荐）。使用 `Authorization` 头部是首选机制，因为互联网代理的行为倾向于更好，且不会缓存此类请求。

密钥永远不会在请求中传输——客户端不需要使用密钥来生成签名。签名可以是 `HMAC-SHA1`（对称的，使用密钥作为盐）或 `RSA-SHA1`（非对称的，使用私钥生成签名）。由于服务器也知道对称密钥，它可以计算出如果客户端使用正确的密钥，签名应该是什么，并确保签名与预期值匹配。对于非对称签名，服务器可以使用匹配的公钥验证由私钥生成的签名。

无论何种情况，只要签名有效，就会授予权限，服务器允许客户端继续授权。如果请求包含任何不支持的参数或协议版本，服务器将返回 `400 Bad Request`；如果签名验证失败、凭据无效、令牌过期或已使用，则返回 `401 Unauthorized`。此时，服务器向客户端返回一个 `x-www-form-urlencoded` 格式的 `200 OK` 响应，响应正文中包含临时凭据。`oauth_token` 响应参数包含临时标识符，而 `oauth_token_secret` 包含临时密钥。由于密钥是以明文形式包含在响应中，标准要求此请求和响应必须通过 `TLS`（例如 `HTTPS`）进行。`oauth_callback_confirmed` 是第三个要求的响应参数，与协议的其他版本不同。它的值必须始终为 `true`。这些内容对应图 28-1 中的步骤 1 到步骤 2。

![](img/4677f981a0e1067137bb55a122f8498d_857_0.png)

## 介绍 OAuth 823

现在客户端已有了临时凭据，它可以将资源所有者重定向到服务器的资源所有者授权端点，并带有临时的 `oauth_token`（步骤 3 和 4）。如果资源所有者已经通过身份验证，服务器将直接授权。否则，它将要求资源所有者进行身份验证（步骤 5）。

在资源所有者授权后，服务器告知客户端想要访问的资源并请求访问权限。如果资源所有者批准（步骤 6），服务器将重定向到客户端。重定向请求包含 `oauth_token` 和 `verifier` 参数（步骤 7 和 8）。`verifier` 参数缓解了会话攻击。

当客户端收到重定向后，向令牌端点发送一个新的 `POST` 请求（步骤 9）。此请求使用客户端密钥签名。服务器验证客户端，验证令牌和 `verifier` 是否匹配，并使用 `oauth_token` 和 `oauth_token_secret` 返回凭据。此时，服务器使临时凭据失效，无法再次使用（步骤 10）。这似乎是一个复杂且漫长的过程，但只需几秒钟即可完成。更重要的是，标准强烈建议使用 `TLS`，因为密钥是以明文形式包含在响应中的。当客户端拥有令牌凭据时，它可以访问受保护资源（无论资源所有者是否存在）。对受保护资源的每个请求都包含令牌凭据的 `Authorization` 头部。

![](img/4677f981a0e1067137bb55a122f8498d_858_0.png)

| 使用有效令牌凭据签名的请求 |
| :--- |
| 客户端 | 受保护资源 |
| 受保护资源响应 |
图 28-2

令牌可能并非永久。服务器可能会定期过期令牌，资源所有者可能会撤销令牌（例如，资源所有者决定不再让客户端访问任何数据）。发生这种情况时，服务器会对下一个受保护资源请求返回 `401 Unauthorized` 响应。此时，客户端可以开始获取临时凭据、授权资源所有者并再次交换临时凭据以令牌。这在图 28-3 中所示。

![](img/4677f981a0e1067137bb55a122f8498d_859_0.png)

> **警告** `OAuth 1.0a` 标准对于此过程中包含的任何令牌的结构、内容或长度（客户端凭据标识符、临时凭据标识符和令牌凭据标识符）没有任何规定。它可以采取提供者想要的任何形式和长度。令牌可以是随机数据组成，也可以包含提供者理解的可预测结构。因此，客户端不应对这些令牌做出任何假设，也不加任何限制。

## OAuth 1.0a 面临的挑战

`OAuth 1.0a` 是一个非常安全的协议，但它并非没有缺陷。首先，`OAuth` 最初在请求各部分的出现顺序上经历过一些歧义。

# 介绍 OAuth | 825

在签名中。例如，当列出需要签名的 `URL`、方法、请求头和参数时，最初并不清楚这些请求参数应该放在什么位置。这导致了不同的实现使用了不同的排序，从而导致了实现之间的不兼容性。从那时起，规范被明确为：出现在签名中的请求参数应采用确定性顺序，但仍然存在一些遗留的实现。

`OAuth 1.0a` 因其签名需求遭了严厉的批评。行业的一些人士认为，对请求的几乎每个部分进行签名没有任何意义。这种技术虽然确保了请求和响应不被篡改，但其提供的安全性可以通过 `TLS` 更简单、更有效地实现。相反，许多人认为，仅对 `Authorization` 请求头中的参数签名就足以达到建立客户端在传输过程中持有正确密钥的最终目标，而这种做法引入了不必要的复杂性。

另一个常见的投诉是，`OAuth 1.0a` 的编写方式本质上假设资源所有者是人类，而客户端是不可信的。`OAuth 1.0a` 的第一个流程忽略了两个用例：

- 客户端应用程序本身也是资源所有者，因此仅通过其客户端凭据进行身份验证。
- 客户端应用程序是由服务器相同的组织创建。这意味着资源所有者信任客户端应用程序，并愿意直接信任客户端中的身份凭据，从而提供更好的用户体验。

出于这个原因，许多实现为 `OAuth 1.0a` 协议创建了扩展，以更好地支持这两个用例。你可以使用不带资源所有者的 `Spring Security OAuth`（转而将客户端视为资源所有者）。在这种方法中，每个请求始终包含客户端标识符，并使用客户端凭据进行签名。这种技术被称为“双足 `OAuth`”（`Two-Legged OAuth`，相对于标准的非正式名称“三足 `OAuth`”`Three-Legged OAuth`），并被许多实现广泛支持。这使得这些实现与规范有些冲突，但仅当你以某种方式配置它们时。默认情况下，它们仍然符合标准（即三足 `OAuth`）。

> 注意：在读完 `OAuth 1.0a` 后，你可能会认为是一个非常强大的协议。事实上，凭据非常像 `HTTP Session ID`（尽管存在一些安全性差异）。但 `REST` Web 服务的目的不就是提供无状态架构吗？`OAuth` 的有状态确实与 `REST` 的无状态性形成了鲜明对比。但实际上，你无法避免这一点（至少，无法安全地避免）。为了实现真正的无状态，客户端必须在每个请求中发送资源所有者的凭据（类似于之前讨论的 `basic` 和 `digest` 方法）。这并不安全，因为不可信的第三方客户端和资源所有者不会容忍这种缺乏信任。安全的身份验证和授权系统需要一个有状态协议。

# 演进：OAuth 2.0

`OAuth 1.0a` 的墨水还未干，`IETF OAuth` 工作组就开始开发 `OAuth 2.0`。它的最终草案于 2012 年 10 月作为建议标准 `RFC 6749` 发布。在互联网标准轨道中，建议标准（`Proposed Standard`）是标准的入门级。在经过足够的反馈和修订后，标准最终从建议标准移动到草案标准（`Draft Standard`）。在草案标准阶段，很少进行更改，但仍然可能进行某些修订以解决标准的问题。第三也是最终的成熟阶段是互联网标准（`Internet Standard`），意味着该标准已被采用并准备广泛使用。

截至 2013 年 10 月，`OAuth 2.0` 仍然是一个建议标准。`RFC 2026` 表示这意味着它不适用于“对中断敏感的环境”（意味着不要在生产环境中使用）。尽管如此，它在整个行业被广泛采用，许多提供商（如 `Facebook` 和 `Twitter`）要求使用 `OAuth 2.0`。

`OAuth 2.0` 是 `OAuth 1.0a` 的替代者，它不向后兼容。`OAuth 1.0a` 客户端无法使用 `OAuth 2.0`（`OAuth 2.0` 客户端无法使用 `OAuth 1.0a` 服务器），但实现允许同时支持两种标准。重要的是，`OAuth 2.0` 不是一个协议；而是一个描述协议可能如何（但不是必须）实现的框架。这一直是许多争议的来源，将在本节后部分介绍。

# 使用 OAuth 2.0 术语

与 `OAuth 1.0a` 一样，`OAuth 2.0` 定义了自己的的一些术语。`OAuth 2.0` 承认身份验证/授权系统并不总是位于同一服务器上，因此 `OAuth 1.0a` 中的服务器在 `OAuth 2.0` 中分为资源服务器和授权服务器。

凭据（`Credentials`）是完全不同的。通常情况下你会拥有某种形式的凭据，但临时凭据和令牌凭据并未被直接涉及。根据所选择的授权许可（`authorization grant`），可能会存在类似的概念，或者你可以为 `OAuth 2.0` 添加扩展以包含不同类型的凭据。

# 理解授权许可

`OAuth 2.0` 的关键特性之一，也可以说是它的优势之一，是它考虑了 Web `API` 资源所有者与客户端分离且均不可信的各种情况。标准定义了四种内置授权许可类型，以及使用每种类型进行身份验证和授权的过程，并允许你通过扩展添加额外的许可类型。所有许可类型都遵循图 28-4 所示的基本流程，尽管每种类型在获取授权许可的方式上有所不同。

与 `OAuth 1.0a` 一样，当客户端向授权服务器发送直接（后台）请求时，客户端使用凭据与授权服务器（但不是资源服务器）进行通信。无论选择哪种类型，这总会发生。所有客户端都有公共标识符。授权服务器必须意识到机密客户端（`confidential clients`，预期可以保留密钥的客户端）与公共客户端（`public clients`，无法持有密钥的客户端，如应用程序）之间的区别。

授权服务器不能仅依赖客户端凭据来建立公共客户端的身份。通常，客户端使用 `HTTP` 身份验证与授权服务器进行验证。这是提供商必须支持的客户端身份验证机制，尽管它们也可以支持其他机制。

![](img/4677f981a0e1067137bb55a122f8498d_862_0.png)
图 28-4

授权码许可（`Authorization Code Grant`）是三足 `OAuth 1.0a` 的功能等同。客户端将资源所有者重定向到授权服务器端以获取访问令牌，并包含请求参数 `response_type`（设置为 `code` 类型）、`client_id`（来自客户端凭据）、`redirect_uri`（批准后发送资源所有者的 `URI`）、`code`（可选的令牌代码，用于限制访问）和 `state`（防止 `CSRF` 攻击的推荐参数）。

当资源所有者在授权服务器上完成授权和许可阶段时，服务器将资源所有者重定向到 `OAuth 1.0a` 中的重定向端，在代码响应参数中包含一个 `authorization code`，并包含与请求 `state` 参数相同值的 `state` 参数（如果已提供）。该授权码是客户端用来交换访问令牌的授权许可。获取访问令牌的请求包含请求参数 `grant_type`（设置为授权 类型）、`code`（刚收到的授权码）、`redirect_uri`（原始 `redirect_uri` 参数值，设置为授权端点）以及 `client_id`。响应为 `JSON` 格式，包含根节点值 `access_token`、`token_type`（例如 `bearer`）、`expires_in`（以秒为单位）、`refresh_token`（可选，如果启用了刷新令牌）以及其他其他请求参数的回显。

这种本质实际上并没有在框架中定义。相反，应用程序开发者可以选择几种扩展之一（或创建自己的）来决定访问令牌的样式、存储位置、如何派生以及如何过期。在此处实现，`token` 被用于访问资源服务器上的受保护资源。访问令牌如何使用（例如，请求参数或 `Authorization` 头部）尚未定义，具体取决于所选择的访问令牌类型。

隐式授权（`Implicit Grants`）与授权码模式（`Authorization Code Grants`）非常相似，并且在功能上等同于三脚 `OAuth 1.0a`，尽管其安全性较低。资源所有者仍然需要授权服务器进行身份验证并授予客户端访问权限。在隐式授权中，此请求与授权码模式几乎完全相同，只是 `response_type` 被设置为 `"token"`。然而，回调中不包含用于交换访问令牌的授权码。相反，回调中直接包含访问令牌（从而消除了图 28-4 中流程中的中间步骤）。参数为 `access_token`、`token_type`、`expires_in`、`scope` 和 `state`。由于客户端已拥有了访问令牌，因此不需要向令牌端点（`token endpoint`）请求令牌。

你可能已经发现了这种授权模式存在一些明显的漏洞，正因如此，你使用的标准仅在非常有限的情况下适用。对于浏览器应用程序而言，可能不受这种授权模式所暴露问题的影响。由于大多数浏览器应用程序是用 `JavaScript` 编写的，授权码模式可能会引入隐式授权模式可以解决的性能影响，而不会严重影响安全性。尽管如此，不建议你使用隐式授权。

客户端凭据授权模式（`Client Credentials Grant`）如图 28-5 所示，在功能上等同于两脚 `OAuth 1.0a`，并最终在标准中被规范。客户端连接到令牌端点并将其凭据交换为访问令牌。请求包含一个设置为 `"client_credentials"` 的 `grant_type` 参数以及可选的 `scope` 参数。客户端通过通常的进程基础身份认证（`process-basic authentication`）进行身份验证。响应包含常用的 `access_token`、`token_type` 和 `expires_in` `JSON` 值。（该授权模式禁止使用刷新令牌 `Refresh tokens`）。通过这种方式，客户端充当了自身的资源所有者，客户端凭据即为图 28-4 中提到的授权许可。客户端可以使用访问令牌代表其访问资源服务器上的受保护资源，而不是代表其他资源所有者。

| 客户端 | 步骤 1: `POST` 客户端凭据 | 授权服务器 |
| :--- | :--- | :--- |
| | 步骤 2: 访问令牌 + 可选刷新令牌 | |
| 客户端 | 使用访问令牌的后续请求 | 资源服务器 |
| | 响应: 受保护资源 | |

图 28-5

资源所有者密码凭据授权模式（`Resource Owner Password Credentials Grant`）如图 28-6 所示，是最用户友好且也可能是最不安全的授权模式。使用这种授权模式，资源所有者将她的凭据（用户名、密码、私钥等）提供给客户端，而无需重定向到授权端点。这就是图 28-4 中提到的这些资源所有者凭据。然后，客户端代表资源所有者将这些凭据转发到令牌端点，并将其交换为访问令牌。

此时，请求的 `grant_type` 参数设置为 `"password"`，请求还包含 `username`、`password` 和 `scope` 参数。`username` 和 `password` 参数是资源所有者凭据的通用术语，实际上并不包含具体的用户名和密码。`JSON` 响应与授权码类型相同。同样，返回的访问令牌随后可以用于访问资源服务器上的受保护资源。

在处理桌面和移动应用程序时，这种授权模式无疑提供了最好的用户体验。资源所有者不需要为了身份验证而在应用程序和浏览器之间切换（有时是频繁切换），而是留在单个应用程序中。当然，这有一个明显的安全影响，即资源所有者必须将他未加密且不安全的凭据交给客户端应用程序。正因如此，最佳实践是仅当创建应用程序的组织也是托管授权服务器的组织时，才使用这种授权模式。在这种客户端可以完全信任资源所有者凭据的情况下。你绝不允许第三方客户端使用资源所有者密码凭据。

步骤 1：凭据提示

![](img/4677f981a0e106713bb55a12f849d864.png) 步骤 2：资源所有者凭据

步骤 3：`POST` R.O. 凭据

步骤 4：访问令牌 + 可选刷新令牌

图 28-6

他离开了并将其名字从标准中移除，尽管他尚未公开说明这一决定。尽管有这些成员退出，`OAuth 2.0` 提议标准已于 2012 年 10 月发布，并且在没有解决这些主要问题的情况下也可能成为互联网标准。

## 使用 MAC 作为持者令牌的替代方案

`OAuth` 工作组的几位成员以及其他社区成员提出了一种持者令牌（`bearer tokens`）扩展的替代方案，该方案将为 `OAuth 2.0` 增加大量安全性并消除许多当前的担忧（互操作性问题除外）。消息认证码（`MAC`）令牌扩展规定了一种不同类型的令牌，它使用消息签名来证明客户端持有机密，而无需在网络上传输机密钥。尽管这与推荐的持者令牌扩展相比是一项重大改进——而且可以说，能够创建这样一种扩展是对 `OAuth 2.0` 设计的一项巨大的测试——但如果没有其缺点，该提议是不可能实现的。

尽管该提议的分类是“轨道”（`Tracks`），但目前它仍然是一个互联网草案（`Internet Draft`）。它尚未成为提议标准（`Proposed Standard`），也没有分配 `RFC` 编号。截至本文编写，当前草案版本为 4，于 2014 年 1 月 16 日过期。到那时，该草案可能会变为提议标准、另一个草案版本或被放弃。即使它不被放弃，在成为互联网标准可能还需要数几年，这使其对许多组织来说是一个没有吸引力的解决方案。

## 你应该使用哪个版本的 OAuth？

那么你应该使用哪个版本呢？嗯，这取决于你。使用每个版本的理由：`OAuth 1.0a` 更稳定、更成熟，并经过了行业测试。它目前没有漏洞，而且大多数使用 `OAuth` 的开发者对 `OAuth 1.0a` 最不熟悉。然而，`OAuth 2.0` 具有具扩展性，支持额外的授权类型，并且不可避免是 `OAuth` 的未来。由于主要参与者（如 `Twitter`、`Facebook` 和 `Google` 等）已经采用了 `OAuth 2.0`，`OAuth 1.0a` 不太可能长期被广泛使用。如果你不喜欢 `OAuth` 的未来，就不应该使用持者令牌。相反，请使用更安全的令牌类型（如 `MAC` 令牌）或创建你自己的使用消息签名来建立授权的令牌系统。

本章的其余部分将探索“创建自己的方法”。使用 `Spring Security`，你将使用自己的令牌系统实现 `OAuth 2.0`，并创建一个能够消费你服务的简单客户端。

> 指出一个讽刺现象是非常重要的：`OAuth 2.0` 项目的目标之一是减少实现之间的非互操作性。通常，`OAuth 1.0a` 客户端必须使用提供者库才能与提供者的授权/资源服务器正常工作。然而，`OAuth 2.0` 内置的非互操作性保证了这个问题只会变得糟糕而不是更好。创建自己的令牌系统（这对于安全使用 `OAuth 2.0` 实际上是要求的）确保了你必须为客户端提供与你的私有 `OAuth 2.0` 实现接口的客户端库。

## 使用 SPRING SECURITY OAUTH

`Spring Security` 通过其 `Spring Security OAuth` 子项目为 `OAuth 1.0a` 和 `2.0` 提供了充足的支持。除了在提供程序应用程序中保护你的资源外，`Spring Security OAuth` 还可以帮助你保护应用程序中受 `OAuth` 保护的资源。`Spring Security OAuth` 的支持分为两个 `Maven` 构件：

- `spring-security-oauth` 提供 `OAuth 1.0` 和 `1.0a` 支持。
- `spring-security-oauth2` 提供 `OAuth 2.0` 支持。

这些构件中的类组织在不同的包中，因此你可以同时使用它们——但要注意限制。尽管你可以用不同的 `OAuth` 权限保护不同的服务 `URL`，但你不能同时用 `OAuth 1.0(a)` 和 `OAuth 2.0` 保护相同的 `URL`。你可以创建一个使用 `Spring Security OAuth` 访问两种 `OAuth 1.0(a)` 和 `OAuth 2.0` 服务的应用程序。

本书无法涵盖所有的四个 `Spring Security OAuth` 场景：`OAuth 1.0(a)` 提供者、`OAuth 1.0(a)` 客户端、`OAuth 2.0` 提供者和 `OAuth 2.0` 客户端。然而，它必须涵盖提供者和场景；否则你将无法测试你的应用程序。由于 `OAuth 2.0` 最终将取代 `OAuth 1.0a`，你将在本章中学习 `Spring Security OAuth 2.0` 的支持。本章涵盖了实现你自己的令牌系统。对于 `OAuth 1.0`，它有一些相似之处，也有一些显著的差异。你可以在参考文档中了解更多关于 `OAuth 1.0` 支持。

## 创建 OAuth 2.0 提供者

`Spring Security OAuth 2.0` 提供者的实现分为两个组件：

- 授权服务器实现
- 资源服务器实现

这对应于 `OAuth 2.0` 规范，该规范解释了位于不同服务器上的授权服务和资源服务。

如果你愿意，可以只将 `Spring Security OAuth` 用于授权服务器或仅用于资源服务器。然而，你很可能将其同时用于授权服务器和资源服务器，无论是在相同的还是不同的服务器上。为了简单起见，本章中的示例假设授权服务器和资源服务器存在于同一服务器以及集群中的所有服务器上。最后一部分非常重要，因为对于简单的非集群应用程序，你可以将令牌持久化在内存中。任何集群应用程序都必须使用更持久的手段持久化令牌。

## 管理客户端详情

在第 26 章和第 27 章中，你学习了 `Spring` 的 `UserDetails` 和 `UserDetailsService` 接口。`Spring Security OAuth` 包含了类似的接口：`org.springframework.security.oauth2.provider.ClientDetails` 和 `org.springframework.security.oauth2.provider.ClientDetailsService`。

`ClientDetails` 指定了允许访问应用程序的 `OAuth` 客户端的信息。由于客户端可以代表自己访问资源（例如客户端凭据模式），`ClientDetails` 包含了客户端持有的 `GrantedAuthority` 集合。它提供了客户端 `ID` 和客户端密钥，用于授权请求的身份验证。`ClientDetails` 还指示了请求的授权类型集（无限制时为 `null`）。

同样，`ClientDetailsService` 允许你通过客户端 `ID` 加载 `ClientDetails` 实例。当客户端身份验证时，`Spring OAuth` 使用 `ClientDetailsService` 加载客户端并与 `HTTP Basic` 头中的密钥进行比较。`Spring OAuth` 的授权组件需要 `UserDetailsService` 才能正常工作。该服务的两个默认实现位于同一个包。

- `InMemoryClientDetailsService` 在启动时配置了应用程序支持的所有客户端。
- `JdbcClientDetailsService` 使用硬编码表定义来存储和检索客户端详情。

由于客户端使用 `Basic` 身份验证（`Spring` 已经支持），你可以配置一个带有 `DaoAuthenticationProvider` 和 `org.springframework.security.oauth2.provider.ClientDetailsUserDetailsService` 的标准认证管理器。

## 理解授权服务器

当客户端需要访问你的保护资源但没有访问令牌时，它会将所有者重定向到你的授权端点。`Spring` 授权服务器托管此端点。它显示确认屏幕，处理提交，生成授权码并将所有者重回客户端应用程序。它响应令牌端请求以用授权码换取访问令牌，以及用客户端凭据和资源凭据换取访问令牌。在配置授权服务器时，你还必须配置 `Spring Security` 来保护授权端点。这意味着，`Spring Security` 要求用户身份验证并拥有访问授权端点的必要权限。`Spring OAuth` 已经使用客户端 `Basic` 身份密钥保护了令牌端点。

配置授权服务器非常复杂，并根据你的应用程序而显著不同。本书无法涵盖所有可能的组合，但本节提供了一些通用信息。接下来的章节将向你展示一种可能的配置示例。

## 配置代码和令牌服务

要配置授权服务器，你必须配置能够存储和检索授权码和访问令牌的服务。`org.springframework.security.oauth2.provider.code.AuthorizationCodeServices` 指定了一个用于创建、存储和消费授权码的接口。授权服务器使用此服务在资源所有者批准对客户端的授权时创建一个授权码。当客户端联系授权服务器“消费”该授权码时，一旦被消费，该 `AuthorizationCode` 就无法再次使用。授权服务器使用 `org.springframework.security.oauth2.provider.token.AuthorizationServerTokenServices` 的实现来创建和刷新令牌，并将它们返回给客户端。该实现持久化了令牌，以便服务器稍后检索它们。

在后续对资源服务器的请求中，`org.springframework.security.oauth2.provider.ResourceServerTokenServices` 提供了一种获取与访问令牌关联的 `Authentication` 对象的机制。`Authentication` 最初在资源所有者进行身份验证时创建，并在资源所有者授权客户端时将其附加到授权码上。当授权码交换为访问令牌时，客户端每次访问受保护资源时，它都会附加到访问令牌上。这允许 `Spring Security` 的授权服务在请求资源期间访问资源所有者的用户详情和权限。

标准的 `AuthorizationCodeServices` 实现类与接口位于同一个包中。

- `InMemoryAuthorizationCodeServices` 创建由随机字母组成的授权码并将其持久化在内存中。此实现速度快且经过优化，性能良好，但仅当你的应用程序未运行在集群中时有用。集群负载均衡器的粘性会话（`sticky sessions`）在授权端点令牌端点可能无法正常工作。一种可能性是客户端的下次请求可能会命中不同的服务器，而 `InMemoryAuthorizationCodeServices` bean 将没有在另一个服务器上生成的授权码的记录。如果你计划对应用程序进行集群化（你很可能会这样做），则你需要在中心位置（如数据库）中持久化授权码。
- `JdbcAuthorizationCodeServices` 同样创建随机授权码，并提供了一种简单的机制，在创建和交换之间将其存储在关系型数据库中。你可以自定义 `INSERT`、`SELECT` 和 `DELETE` 语句来管理这些代码。当然，如果你需要，也可以创建自己的实现。

`org.springframework.security.oauth2.provider.token.DefaultTokenServices` 是 `AuthorizationServerTokenServices` 的唯一标准实现。它也是标准的 `ResourceServerTokenServices` 实现。它处理持有者令牌（`bearer tokens`）的创建、存储和检索，并使用 `org.springframework.security.oauth2.provider.token.TokenStore` 来管理令牌的持久化。你可以从 `InMemoryTokenStore`（它在集群环境中存在某些缺点）或 `JdbcTokenStore` 中进行选择，或者自己实现这些接口。

你可以将这些服务作为简单的 `Spring bean` 进行配置。如果你选择使用内存实现，`Spring Security OAuth` 使用 `XML` 命名空间来简化这些 `bean` 的创建。在大多数情况下，在不指定其他内容的情况下配置 `Spring Security OAuth` 时，默认选择内存实现。由于内存实现不适用于集群环境，你需要更改这些默认值。

![](img/4677f981a0e1067137bb55a122f8498d_870_0.png)

`Spring Security OAuth 2.0` 的 `XML schema URI` 为 `http://www.springframework.org/schema/oauth2`。你可以将此内容添加到任何 `Spring Beans XML` 文件中（推荐的 `oauth2` 命名空间前缀）以配置 `OAuth 2.0` 支持。如果你想使用 `XML` 配置 `OAuth 1.0`，请使用 `http://www.springframework.org/schema/security/oauth` `URI`（以及推荐的 `oauth` 命名空间前缀）。由于这些架构是分开的，你可以同时配置 `OAuth 1.0` 和 `OAuth 2.0` 组件。其 `client-details-service-ref` 属性允许你指定 `ClientDetailsService` 的引用，而 `tokens-services-ref` 指明 `AuthorizationServerTokens` 的实例。你还可以使用 `authorization-endpoint-url` 和 `token-endpoint-url` 属性自定义端点 `URL`，它们分别指向 `/oauth/authorize` 和 `/oauth/token`。

# 创建 OAuth 2.0 客户端

使用 `OAuth` 保护你的服务的另一面，就是从客户端应用程序访问受 `OAuth` 保护的资源。正如前面提到的，`Spring OAuth` 可以替你处理这些工作。

要理解 `Spring OAuth` 客户端组件的工作原理，你必须首先了解 `Spring Framework` 的 `org.springframework.web.client.RestOperations`。该接口定义了一组基本的 `RESTful` 服务操作。通过使用该接口的实现，你可以从 Web 服务 `GET` 一个条目或实体集合、`DELETE` 一个条目、`POST` 一个新实体、`PUT` 更新它、获取资源的 `HEAD`、确定资源的 `OPTIONS`，以及更多操作。该接口的默认实现 `org.springframework.web.client.RestTemplate` 是你访问 `RESTful` 服务时唯一需要的类。该工具集非常完整且经过了充分测试，并提供了拦截请求和响应的机制（例如，添加或更改请求头）。

然而，`RestTemplate` 没有提供任何类型安全性的内置支持。虽然你可以使用拦截器手动实现 `OAuth` 授权，但这是没有必要的，因为 `Spring OAuth` 提供了该功能的实现。`org.springframework.security.oauth2.client.OAuthRestOperations` 扩展 `RestOperations` 接口以指定与 `OAuth` 相关的方法。同样，`org.springframework.security.oauth2.client.OAuth2RestTemplate` 扩展了 `RestTemplate` 以实现 `OAuthRestOperations` 并提供 `OAuth 2.0` 客户端支持。

# 配置 OAuth Rest Template

在使用 `OAuth2RestTemplate` 时你应该记住一点。对于标准的 `RestTemplate`，你可以在应用程序的任何地方复用单个 `RestTemplate` bean 来访问 Web 上的任何服务端点。这是因为 `RestTemplate` 是完全无状态的，在请求之间不存储任何信息。然而，`OAuth2RestTemplate` 并非如此——而且你使用的任何带有拦截器的 `RestTemplate` 都可能不是如此，这取决于该拦截器的具体功能。

当你配置 `OAuth2RestTemplate` 时，你为它提供了一个 `org.springframework.security.oauth2.client.resource.OAuth2ResourceDetails` 对象。它指定了模板在身份验证资源服务器时使用的客户端 `ID`、客户端密钥（`client secret`）和其他信息。它代表单个远程资源，或一组接受相同客户端凭据和访问令牌的资源。因此，如果你将访问受不同资源服务器保护的多个 Web 服务，你需要定义多个 `OAuth2RestTemplate` bean，并使用 `Spring` 的 `@Qualifier` 或 `Java EE` 的 `@Qualifier`（将在第 12 章介绍）。

在独立应用程序（未托管在 Web 上的程序）中，使用 `OAuth2RestTemplate` 首先，它可能像任何其他 `RestTemplate` 实例一样，只是你为每个客户端凭据创建一个实例，而不是一个全局实例。你需要为每个 `OAuth2RestTemplate` 提供一个 `org.springframework.security.oauth2.client.OAuth2ClientContext`，它能够为特定请求确定正确的客户端代码（如果有的话）。通常，你将此信息存储在每个线程中或 `JVM` 全局范围内。

如果访问令牌无效或受 `OAuth` 保护的资源被拒绝，`OAuth2RestTemplate` 方法将抛出相应的异常。然而，如果资源所有者尚未授权并需要重定向到授权端点（因为你正在使用授权码模式或隐式授权模式），方法将抛出 `org.springframework.security.oauth2.client.resource.UserRedirectRequiredException`。

捕获到此异常后，你可以启动浏览器窗口、重定向请求或执行任何必要操作将用户发送到授权端点以授权客户端。记住，你的应用程序必须接收来自授权端点的重定向以接收代码（或用于隐式授权的访问令牌）。在独立应用程序中，这意味着你的应用程序必须向操作系统和已安装的浏览器注册正确的应用程序启动 `URI` 方案，或者在应用程序内部包含一个嵌入浏览器。如果这不是选项，你需要使用客户端凭据模式或资源所有者密码模式。

# 在 Web 应用程序中使用 REST Template

Web 应用程序中的 `OAuth2RestTemplate` 比独立应用程序更为简单，因为 `Spring Security` 的过滤器链可以处理大部分困难工作。

该请求防止了其被重放。`nonce`（随机数）应该是随机的，以便无法被预测。然而，由于真正的随机性不能排除重复，`nonce` 应该与时间戳配合使用。提供者应确保任何 `nonce`-时间戳组合都是唯一的。为了防止攻击者仅更改时间戳并重用 `nonce` 来重放请求，签名令牌除了 `nonce` 之外还应该包含时间戳。

至此，你已经知道签名令牌至少应该包含访问令牌（`access token`）（但仅作为签名的盐）、`nonce` 和时间戳。它还应该包含什么？为了让提供者获取正确的访问令牌以验证签名，请求需要包含某种类型的标识符，提供者可以使用该标识符从令牌存储中查找访问令牌。请求将包含此标识符，将标识符也包含在令牌签名中也是合理的。

`OAuth 1.0` 在每个受保护资源请求中都包含 `ID`，以确保只有授权该访问令牌的客户端可以使用它，但 `OAuth 2.0` 缺乏这一安全特性。在受保护请求中包含 `ID` 是有风险的，作为最后的健康检查，将 `ID` 包含在签名中可以确保它未被篡改。作为请求签名的一部分，它不需要像 `OAuth 1.0` 中的方法或 `URL` 那样复杂。在语法上，签名可能如下：

```



# 签名计算与授权头部

签名计算公式如下：

```
SHA1( clientId " , tokenID " , nonce " , timestamp " , method " , tokenValue )
```

如果 Client ID 为 `TestClient`，token ID 为 `y8g1FPKZW`，nonce 为 `i74K5E4y4b,138192740`，请求方法为 `POST`，token 值为 `Y4KPI2432489ey5013h`，签名可以描述如下：

```
SHA1( TestClient,y8g1FPKZW,i74K5E4y4b,138192740,POST,Y4KPI2432489ey5013h )
```

签名的计算值如下：
`edca55ea9b0d647f5495746bb13dba97c8ca5923b`

来自同一客户端和资源的每个受保护资源请求的 client ID、token ID 和 token value 都是固定的。只有 nonce 和时间戳值在每次请求中发生变化。当然，请求方法反映了请求的方法。

你每次请求都需要传输所有这些数据。授权受保护资源请求的标准机制是在每个请求中包含 `Authorization` 头部。当请求头以单词 "Bearer" 开头并跟一个空格时，请求的值代表了持有者令牌（bearer token）。在这种情况下，你可以用 "Signing" 代替 "Bearer"，并在值中使用逗号分隔的键值对作为令牌信息。使用之前描述的值和签名，请求中的 `Authorization` 头部看起来如下（为了清晰，实际标头中省略了换行）：

```
Authorization: Signing client_id=TestClient,token_id=y8g1FPKZW,nonce=i74K5E4y4b,timestamp=138192740,signature=edca55ea9b0d647f5495746bb13dba97c8ca5923b
```

注意，client 值没有出现在头部中，因为目标不是传输令牌来证明客户端持有该令牌。请求方法也没有出现在头部中，因为它仅仅是请求的一部分。虽然在签名中出现的顺序非常重要，但在头部中出现的顺序则不然。当提供者接收请求时，它只需要使用 token ID 查找 token value，确保指定的客户端是令牌的持有者，检查 nonce 是否从未被使用过，然后使用给定的信息重新计算签名。如果签名与提供的签名匹配，则确保了访问令牌的真实性。如果签名不匹配，请求将被拒绝。

> **警告** 刚刚描述了 OAuth 2.0 文档中指定的标准持有者令牌系统的一种理论替代方案。该替代方案尚未经过 OAuth 社区或安全专家的审查。尽管此提议提供了比持有者令牌高得多的安全性，但在生产应用程序中使用它之前，你应该对其进行仔细、彻底的评估，并咨询您组织的安全官员。在使用 OAuth 时，您应该保持同样的严谨态度。

> **注意** 如果你想进一步提高安全级别，可以使用非对称的公私密钥对来生成和验证签名，而不是使用共享密钥令牌作为签名的盐。额外的好处是授权服务器从不存储密钥（私钥）——只有客户端拥有此信息。如果整个 OAuth 凭据被盗，攻击者将无法利用其中的公钥来破坏您的系统。此外，只要密钥对是由客户端而不是服务器生成的，私钥就永远不需要通过网络传输——那是极其安全的。这种技术将需要更多精力，留给读者进一步探索。

## 实现客户端服务

你需要定义允许访问你的 Web 服务的客户端。对于具有静态种类和稳定内部开发客户端集合的简单系统，你可以使用 Spring OAuth 的 `InMemoryClientDetailsService`，但在许多情况下这是不够的。如果你已经在使用 JPA、Spring Data 和 Spring Framework 事务，可能创建自己的实现会更容易。

## 创建客户端实体

客户端实体非常直观。它需要实现 `ClientDetails` 并映射到几个数据库表。由于你正在自定义此项，OAuth 1.0 在每个受保护资源请求中包含 ID...（此处原文似乎存在重复或截断，此处按原意保留）。

项目的 `create.sql` 文件为客户支持数据库添加了新表，并从中插入了一个测试客户端。如果你在之前的章节中没有处理过客户支持应用程序，则你需要运行 `create.sql` 脚本并创建相应的 Tomcat Data Resource（命名为 `jdbc/CustomerSupport`）。如果你有现有的数据库需要升级，请确保运行这四张表的 `create` 语句。插入新表中的测试客户端数据如下（客户端密码为 "y471II2D2y5SSU588rd2" 的 BCrypt 哈希值）。

```sql
INSERT INTO WebServiceClient (ClientId, ClientSecret) VALUES
('TestClient', 'Q2S@I0e1DbFcb/ZkyuNpKFS.7014gn2EuhUy20YNPsoF3avx9.Hd/b8BTa');
```

```sql
INSERT INTO WebServiceClient_Scope (WebServiceClientId, Scope)
VALUES (1, 'READ'), (1, 'WRITE'), (1, 'TRUST');
```

```sql
INSERT INTO WebServiceClient_Grant (ClientId, GrantName)
VALUES (1, 'authorization_code');
```

```sql
INSERT INTO WebServiceClient_RedirectUri (WebServiceClientId, Uri)
VALUES (1, 'http://localhost:8080/client/support/');
```

如果你正在使用现有数据库，则需要为 Web 服务创建授权权限。`create.sql` 脚本中的以下语句将此权限添加到用户 Nicholas 和 John 中（假设你已经在数据库中保留了默认用户）。

```sql
INSERT INTO UserPrincipal_Authority (UserId, Authority)
VALUES (1, 'USE_WEB_SERVICES'), (4, 'USE_WEB_SERVICES');
```

## 实现 Nonce 服务

Spring Security OAuth 2.0 并没有指定任何类型的与 nonce（一次性随机数）相关的接口，因为它们不是 OAuth 2.0 的标准部分。然而，构建一个这样的系统其实非常简单。对于 nonce 实体、存储库和服务来说，工作量很少。如果你有现有的数据库需要升级，请确保运行 SQL 创建语句。

```java
@Entity
@Table(name = "Nonce")
public class Nonce implements Serializable {

    private static final long serialVersionUID = 1L;

    private long id;
    private String value;
    private long timestamp;

    public Nonce() { }

    public Nonce(String value, long timestamp) { ... }

    @Id
    @Column(name = "NonceId")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    public long getId() { }

    public void setId(long id) { }

    public String getValue() { ... }

    public void setValue(String value) { ... }

    @Column(name = "NonceTimestamp")
    public long getTimestamp() { ... }

    public void setTimestamp(long timestamp) { ... }
}
```

```sql
CREATE TABLE OAuthNonce (
    id BIGINT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    Value VARCHAR(50),
    NonceTimestamp BIGINT NOT NULL,
    UNIQUE KEY (OAuthNonce_Value_Timestamp)
) ENGINE = InnoDB;
```

`NonceRepository` 使用了你在第 22 章中学习过但没有实验过的技术——使用 `org.springframework.data.jpa.repository.Query` 为不匹配标准 Spring Repository 方法模式的方法定义查询。`@org.springframework.data.jpa.Modifying` 注解告诉 Spring Data 该方法会修改数据（而不是读取），并且应该如下执行：

```java
public interface NonceRepository extends CrudRepository<Nonce, Long> {

    Nonce getByValueAndTimestamp(String value, long timestamp);

    @Modifying
    @Query("DELETE FROM Nonce WHERE n.timestamp < :timestamp")
    void deleteWhereLessThan(long timestamp);
}
```

删除的目的非常简单。因为 nonce 必须检查重复性，如果你的服务器负载很大，nonce 表将很快填满。解决此问题的简单方案是定期删除时间戳在几分钟之前的 nonce，并直接拒绝过期时间戳的请求。该系统要求客户端的时钟相当准确，这对于一个安全系统来说并不是不合理的要求。

`DefaultOAuthNonceServices` 中的 `deleteOldNonces` 方法使用 Spring Framework 调度在 2 分钟后删除旧 nonce。记住，为了使方法有效，必须正确正确实现。

```java
public class DefaultOAuthNonceServices implements OAuthNonceServices {

    @Inject
    NonceRepository repository;

    @Override
    @Transactional
    public void deleteOldNonces() {
        repository.deleteWhereLessThan(System.currentTimeMillis() - 120000);
    }

    @Override
    public void recordIfDuplicate(String value, long timestamp) {
        Nonce nonce = repository.getByValueAndTimestamp(value, timestamp);
        if (nonce != null) {
            throw new IllegalArgumentException("Duplicate nonce: " + value);
        }
    }
}
```

## 列表 28-1

```java
public class DefaultAccessTokenServices implements SigningAccessTokenServices {

    AuthenticationKeyGenerator authenticationKeyGenerator =
        new DefaultAuthenticationKeyGenerator();

    @Inject SigningAccessTokenRepository repository;

    @Override
    @Transactional
    public OAuth2AccessToken createAccessToken(OAuth2Authentication auth)
        throws AuthenticationException
    {
        // 实现
    }
}
```

```java
String key = this.authenticationKeyGenerator.extractKey(auth);
SigningAccessToken token = this.repository.getByKey(key);
if (token != null) {
    if (token.isExpired()) {
        // 后续逻辑
    }
}
```



```java
this.repository.delete(token);
this.repository.flush();
} else {
    token.setAuthentication(auth); // in case authorities changed
    this.repository.save(token);
    return token;
}
}

token = new SigningAccessToken(
    key,
    UUID.randomUUID().toString(),
    new Date(System.currentTimeMillis() + 86_400_000L), // one day
    auth.getAuthorization().getScope(),
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
public OAuth2AccessToken loadAuthentication(String tokenValue) throws AuthenticationException {
    SigningAccessToken token = this.repository.getByValue(tokenValue);
    if (token == null) {
        throw new InvalidTokenException("Invalid token " + tokenValue + ".");
    }
}
```

# 850 | 第 28 章 使用 OAUTH 保护 RESTFUL Web 服务

## 自定义资源过滤器

通常情况下，你会使用 XML 命名空间元素 `<oauth2:resource-server>` 来配置 Spring Security OAuth2 资源服务器。这创建一个 `OAuth2AuthenticationProcessingFilter`，用于拦截受保护的资源并验证访问令牌。该过滤器专门为 bearer tokens 编写的，并不易于扩展，因此在这种情况下你必须实现自己的过滤器。

`OAuthSigningAuthenticationFilter` 会为你处理好一切。这个类也很长，而且大部分内容都没有打印。`parseHeader` 方法解析 `Authorization` 请求头，确保它是一个签名（Signing）值，并返回请求头中参数的 `Map<String, String>`。`doFilter` 调用 `parseHeader` 来判断请求头是否存在，然后将请求头值的映射传递给 `authenticate` 方法。该方法执行了最核心的工作：计算签名、与提供的签名进行对比、验证令牌，并确保请求不包含异常或重复的随机数（nonce）。

```java
private void authenticate(Map<String
```

# 完成客户支持应用程序 | 85

```java
if(!authorizationRequest.getClientId().equals(clientId))
    throw new InvalidTokenException("Client ID does not match token.");
Collection<String> resourceIds = authorizationRequest.getResourceIds();
```

```java
Collection<String> resourceIds = authorizationRequest.getResourceIds();
if(this.resourceId == null && resourceIds != null &&
    !resourceIds.isEmpty() && !resourceIds.contains(this.resourceId))
    throw new InvalidTokenException("Resource ID not permitted.");
```

```java
String timestamp = header.get("timestamp");
String nonce = header.get("nonce");
if(timestamp == null || nonce == null)
    throw new InvalidTokenException("Header missing timestamp or nonce.");
```

```java
String toSign = clientId + "+" + tokenId + "+" + nonce + "+" + 
    timestamp + "+" + request.getMethod().toUpperCase() + "+" + 
    token.getValue();
String signature = new String(Base64.getEncoder().encode(
    DIGEST.digest(toSign.getBytes(StandardCharsets.UTF_8)))
), StandardCharsets.UTF_8);
```

```java
String presentedSignature = header.get("signature");
if(!signature.equals(presentedSignature))
    throw new InvalidTokenException("Missing or invalid signature.");
```

```java
long timestampValue = Long.parseLong(timestamp);
long system = System.currentTimeMillis() / 1000;
if(timestampValue > system - 60 || timestampValue > system + 60)
    throw new InvalidTokenException("Header timestamp out of range.");
```

```java
this.nonceServices.recordOrFailDuplicate(nonce, timestampValue);
```

```java
request.setAttribute(OAuthAuthenticationDetails.ACCESS_TOKEN, 
token.getValue());
authentication.setDetails(this.authenticationDetails.build(
request));
```

```java
SecurityContextHolder.getContext().setAuthentication(authentication);
```

该方法的一个点是它只接受当前时间前后1 分钟内的请求。由于之前创建的 nonce 服务会在2 分钟后删除随机数，因此你应该只允许在2 分钟窗口内（时间戳前后）的随机数。这意味着 Web 服务需要同步时间。**注意**：所有操作系统都启用了网络时间协议，因此这个标准的 OAuth2 处理过滤器是必要的，因为 Spring Security OAuth2 没有提供额外类型的机制。希望 Spring Security 2.0 版本会提供替代类型的机制，但在书中尚未介绍。

# 重新配置 Spring Security

完成你的 OAuth2 提供者实现的最后一步是在 Spring Security 中配置它。虽然你在之前的章节中使用了纯 Java 配置了 Spring Security，但理论上你可以创建一个结合 XML 命名空间和 Java 特性的混合配置，不过这样做带来的麻烦大于收益。你最好完全使用 XML 命名空间。你会发现 `SecurityConfiguration` 类不再存在了，它被 `resources` 目录下的 `securityConfiguration.xml` 文件取代，而 `RootContextConfiguration` 已更改为导入该文件：

```java
@ImportResource("classpath:wrox/config/securityConfiguration.xml")
public class RootContextConfiguration implements AsyncConfigurer, SecurityConfigurer {
```

XML 配置以命名空间导入和一些基础 bean 的定义开始。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:oauth2="http://www.springframework.org/schema/oauth2"
       xmlns:security="http://www.springframework.org/schema/security"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
                           http://www.springframework.org/schema/oauth2 http://www.springframework.org/schema/oauth2/spring-oauth2.xsd
                           http://www.springframework.org/schema/security http://www.springframework.org/schema/security/spring-security.xsd">

<bean id="userService" class="wrox.site.DefaultUserService" />
<bean id="webServiceClient" class="wrox.site.DefaultWebServiceClient" />
<bean id="clientDetails" class="wrox.site.ClientDetailsUserService" />
<bean id="clientDetailsDetailsService" class="org.springframework.security.oauth2.provider.client.ClientDetailsDetailsService">
    <constructor-arg ref="webServiceClient" />
</bean>
<bean id="sessionRegistry" class="org.springframework.security.core.session.SessionRegistryImpl" />
<bean id="oauth2SecurityExpressionHandler" class="org.springframework.security.oauth2.provider.expression.OAuth2SecurityExpressionHandler" />
<bean id="methodSecurityExpressionHandler" class="org.springframework.security.oauth2.provider.expression.OAuth2MethodSecurityExpressionHandler" />
<bean id="passwordEncoder" class="org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder" />
</beans>
```

# 完成客户支持应用程序 | 85

注意在之前的章节中使用 Java 配置的密码编码、会话注册表和 `DefaultUserService`。它还配置了 Spring Security OAuth2 认证处理器，以替换默认的异常处理器以及用于查找 OAuth 客户端的 `DefaultClient`。`ClientDetailsUserDetailsService` 是 `ClientDetails` 和 `UserDetailsInterface` 之间的特殊桥梁，对于认证管理器正常工作访问令牌是必要的。对于 bearer 令牌，你通常需要定义 `DefaultTokens` 和 `TokenStore`。例如，你可以这样配置：

```xml
<bean id="tokenStore"
    class="org.springframework.security.oauth2.provider.token.MemoryTokenStore" />
<bean id="tokenServices"
    class="org.springframework.security.oauth2.provider.token.DefaultTokenServices">
        <property name="tokenStore" ref="tokenStore" />
        <property name="support" value="true" />
        <property name="clientDetailsService" ref="webServiceClient" />
    </bean>
```

相反，你只需要配置你的 `DefaultAccessTokenServices`。

```xml
<bean id="tokenServices"
    class="com.wrox.site.DefaultAccessTokenServices" />
```

接下来你需要配置几个其他 OAuth 和认证管理组件。`UserApprovalHandler` 处理所有授权客户端的响应。`OAuth2AccessDeniedHandler` 处理访问拒绝错误并返回带有客户端请求的内容类型的响应。`OAuth2AuthenticationEntryPoint` 执行相同的事情，只是第一个 `<authentication-manager>` 创建了你在第 26 章中配置的认证的认证管理器，而第二个创建了一个特殊的认证管理器来处理指向访问令牌端点的客户端请求。

```xml
<bean id="userApprovalHandler"
    class="org.springframework.security.oauth2.provider.approval.TokenServicesUserApprovalHandler">
        <property name="tokenServices" ref="tokenServices" />
    </bean>
```

```xml
<bean id="oauthAccessDeniedHandler"
    class="org.springframework.security.oauth2.provider.error.OAuth2AccessDeniedHandler" />
```

```xml
<bean id="oauthAuthenticationEntryPoint"
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
<authentication-provider>
</authentication-provider>
```



<authentication-manager id="oauthClientAuthenticationManager">
  <authentication-provider user-service-ref="clientDetailsUserService">
    <password-encoder ref="passwordEncoder" />
  </authentication-provider>
</authentication-manager>

<oauth2:authorization-server ref="token-services"
  client-details-service-ref="webServicesClientService"
  user-approval-page="oauth/authorize" error-page="oauth/error" />

`oauth2:authorization-server` 元素是 OAuth 配置的重要部分。它设置了授权端点（`/oauth/authorize`，以释放你的应用根路径）和访问令牌端点（`/oauth/token`），并处理对 URL 的请求。配置的授权服务器会自动使用 HTML 表单响应这些请求。然而，这种方式非常通用，不会匹配你的网站进行样式调整。`user-approval-page` 属性允许你为显示授权请求的表单指定 Spring MVC 视图，而 `error-page` 属性则允许你为发生授权错误时显示的错误页指定视图。

你选择的视图名称为 `/WEB-INF/jsp/view/oauth/authorize.jsp` 和 `/WEB-INF/jsp/view/oauth/error.jsp`。这些 JSP 中的 EL 变量和字段名是 Spring Security OAuth 标准，不应更改。

你需要配置的下一步是资源过滤器（resource filter）。通常情况下，你会这样配置它：

```xml
<oauth2:resource-server id="resourceServerFilter" resource-id="SUPPORT"
  entry-point-ref="oauthAuthenticationEntryPoint"
  token-services-ref="tokenServices" />

<bean id="nonceServices"
  class="com.wrox.site.DefaultOAuthNoncesServices" />

<bean id="resourceServerFilter"
  class="com.wrox.site.OAuthSigningTokenAuthenticationFilter">
  <property name="authenticationEntryPoint"
    ref="oauthAuthenticationEntryPoint" />
  <property name="nonceServices" ref="nonceServices" />
  <property name="tokenServices" ref="tokenServices" />
  <property name="resourceId" value="SUPPORT" />
</bean>
```

这开箱即处理了 bearer 令牌，但由于你使用了自定义令牌，你需要手动配置你的 nonce（随机数）和自定义资源过滤器。

完成这些配置后，最后一步是配置全局方法安全（global method security）和 HTTP 安全。全局方法安全非常简单，前两个 `<http>` 元素配置了被所有安全过滤器排除的 URL 模式。

```xml
<global-method-security pre-post-annotations="enabled" order="0"
  proxy-target-class="true">
  <expression-handler ref="methodSecurityExpressionHandler" />
</global-method-security>
```

```xml
<http security="none" pattern="resource/**" />
<http security="none" pattern="favicon.ico" />
```

下一个 `<http>` 元素配置访问端点的安全性。这确保了客户端在换换访问令牌之前，使用 HTTP 认证通过其 client ID 和 secret 进行验证。请注意这些 `<http>` 元素出现的顺序非常重要，因为每个请求都会使用第一个匹配的配置。另外注意，此配置是无状态的，这意味着不会为访问端点的请求创建 HTTP 会话。

```xml
<http use-expression="True" create-session="stateless"
  authentication-manager-ref="oauthClientAuthenticationManager"
  entry-point-ref="oauthEntryPoint" pattern="/oauth/token">
  <intercept-url pattern="/oauth/token" access="hasAuthority('OAUTH_CLIENT')" />
  <http-basic />
  <access-denied-handler-ref="oauthAccessDeniedHandler" />
  <expression-handler ref="webSecurityExpressionHandler" />
</http>
```

下一个 `<http>` 元素也是无状态的，并使用你之前创建的自定义资源服务器通过基于签名的访问令牌来保护你的 Web 服务。它确保资源所有者在允许使用你的 Web 服务之前被授予 `USE_WEB_SERVICES` 权限——不要替换添加到所有服务中的 `@Authorize` 检查点这些它们仍然有效。

```xml
<http use-expressions="True" create-session="stateless"
  entry-point-ref="oauthEntryPoint" pattern="/services/**">
  <intercept-url pattern="/services/**" access="hasAuthority('USE_WEB_SERVICES')" />
  <custom-filter ref="resourceServerFilter" before="PRE_AUTH_FILTER" />
  <access-denied-handler-ref="oauthAccessDeniedHandler" />
  <expression-handler ref="webSecurityExpressionHandler" />
</http>
```

最后一个 `<http>` 元素实际上与你在第 26 章用 Java 创建的 httpSecurity 配置基本相同，仅有两处微调。

- 虽然 Java 配置允许登录表单在显示时提交到同一个 URL，但 XML 配置不支持此操作，因此登录表单不会前往 `/login/submit`。

注意使用 `<csrf>` 元素来启用 CSRF 保护，它在 XML 配置中默认是禁用的。

```xml
<http url-expressions="true">
  <intercept-url pattern="/session/list" access="hasAuthority('VIEW_USER_SESSIONS')" />
  <intercept-url pattern="/oauth/**" access="hasAuthority('USE_WEB_SERVICES')" />
  <intercept-url pattern="/**" access="permitAll()" />
  <intercept-url pattern="/logout" access="permitAll()" />
  <intercept-url pattern="/login" access="permitAll()" />
  <intercept-url pattern="/login/submit" access="permitAll()" />
  <form-login login-page="/login" login-success-url="/session/list" error-page="/error" />
  <csrf />
  <session-management>
    <concurrency max-sessions="1" session-fixation-protection="migrate" />
  </session-management>
  <expression-handler ref="webSecurityExpressionHandler" />
</http>
```

到此时，你已经成功使用了 Spring Security OAuth。你可能想要查看的是 TicketService。

# 列表 28-2（续）

## 配置 Spring OAuth 客户端

OAuth Client 项目的大部分 Spring Security 配置都是样板代码。它包含了许多你已经见过的内容，并且像客户支持应用程序（Customer Support application）一样，是从 `RootContextConfiguration` 导入的。

`<authentication-manager>` 声明了一个简单的内存用户服务，其中包含两个硬编码的用户，而 `<http>` 元素定义了直接的身份验证和授权规则。`<oauth2:resource>` 和 `<oauth2:client>` 是你之前没有使用过的新功能。首先，它定义了该客户端消耗的第三方受保护资源，包括它的授权端点和访问端点、客户端 ID（client ID）、客户端密钥（client secret）等。如果你的客户端从多个提供者访问受保护资源，你将需要定义多个 `resource` 元素。

## 创建 OAuth 客户端应用程序

`client` 元素始终只使用一次——它定义了一个过滤器，用于捕获 `UserRedirectRequiredExceptions`，并在发生此类异常时将用户重定向到正确的授权端点。

```xml
<xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/security"
    xmlns:beans="http://www.springframework.org/schema/beans"
    xmlns:aop="http://www.springframework.org/schema/aop"
    xmlns:oauth2="http://www.springframework.org/schema/security/oauth2"
    beans:xsi="...">
```

```xml
<oauth2:resource id="http://OAuth2Client" authentication-scheme="header"
    client-id="TestClient" client-secret="y47l1d2Y2g5U555r8d2"
    scope="READ, WRITE, TRUST"
    user-authorization-uri="http://localhost:8080/support/oauth/authorize"
    access-token-uri="http://localhost:8080/support/oauth/token" />

<authentication-manager>
    <user-service>
        <user name="Steve" password="apple" authorities="USER" />
        <user name="Bill" password="orange" authorities="USER" />
    </user-service>
</authentication-provider>
</authentication-manager>
```

```xml
<oauth2:client id="OAuth2ClientFilter" />

<http use-expressions="true">
    <intercept-url pattern="/login/*" access="permitAllAll()" />
    <intercept-url pattern="/login" access="permitAllAll()" />
    <intercept-url pattern="/logout/*" access="permitAllAll()" />
    <intercept-url pattern="***" access="hasAuthority('USER')" />
    <session-management invalid-session-url="/login"
        session-fixation-protection="sessionId" />
    <form authentication-failure-url="/login?loginFailed"
        login-page="/login" login-processing-url="/login/submit"
        username-parameter="username" password-parameter="password"
        default-target-url="/login" />
    <logout logout-url="/logout" access-url="/login?loggedOut"
        delete-cookies="JSESSIONID" invalidate-session="true"
        custom-ref="oauth2ClientFilter" />
</http>

<beans:beans>
    <RestTemplate
```

你最后需要配置的是 `RestTemplate` 的实现。如果你使用的是默认的 own令牌（bearer token）类型，配置将简单如下：

```xml
<oauth2:rest-template id="customersSupportRestTemplate
    resource="OAuth2ClientBean" />
```

然而，由于你创建了自定义的 `RestTemplate`，你必须手动对其进行配置。这是复杂的，涉及到创建一个请求作用域（request-scoped）访问令牌并将其封装在代理中，创建一个会话作用域（session-scoped）客户端上下文并将其封装在代理中，最后创建一个使用这些 bean 的自定义 `RestTemplate`。这些 都是 `<oauth2:rest-template>` 通常会自动为你完成的工作。对于 `<oauth2:resource>`，你需要为应用程序访问的每个受保护资源配置 `RestTemplate`。

```xml
<beans:bean name="accessTokenRequest" scope="request"
    class="org.springframework.security.oauth2.client.DefaultAccessTokenRequest">
    <aop:scoped-proxy />
    <beans:constructor-arg index="0" value="#{request.parameterMap}" />
    <beans:property name="currentUri" value="#{request.getAttribute('currentUri')}" />
</beans:bean>

<beans:bean name="clientContext" scope="session"
    class="org.springframework.security.oauth2.client.DefaultOAuth2ClientContext">
    <aop:scoped-proxy />
    <beans:constructor-arg index="0" ref="accessTokenRequest" />
</beans:bean>

<beans:bean id="customRestTemplate"
    class="com.work.site.OAuth2SigningRestTemplate">
    <beans:constructor-arg index="0" ref="OAuth2ClientBean" />
    <beans:constructor-arg index="1" />
</beans:bean>

<beans:bean name="oauth2ClientFactory" class="org.springframework.security.oauth2.config.DefaultOAuth2ClientFactory">
```



```xml
<beans:property name="resource" ref="OAuth2ClientBean" />

<beans:property name="name" value="clientContext" />

<beans:bean class="org.springframework.security.oauth2.client.DefaultOAuth2ClientContext">

    <beans:property name="scopedContext" ref="clientContext" />

</beans:bean>

<beans:constructor-arg>

    <beans:list list="messageConverter">

        <beans:bean class="org.springframework.http.converter.json.MappingJacksonHttpMessageConverter">

            <beans:property name="objectMapper" ref="objectMapper" />

        </beans:bean>

    </beans:list>

</beans:constructor-arg>

</beans:bean>
```

> 注意：需要这种复杂的配置是因为 Spring Security OAuth 没有提供插入额外令牌类型的机制，这意味着你必须扩展 `OAuth2RestTemplate` 并对其进行配置。希望 Spring Security OAuth 2 会提供此功能。

## 使用 RestTemplate

使用自定义的 `OAuth2RestTemplate` 可能是项目中最简单的部分。`SupportController` 从客户支持服务获取所有工单（tickets）列表，并将请求转发到显示所有标题的视图。如果当前登录的客户端应用程序没有 Web 服务的访问令牌，将产生 `UserRedirectRequiredException`，用户并将重定向到授权端点。

带有授权码返回此控制器后，Spring OAuth 2 会联系访问令牌端点并将代码交换为访问令牌。随后它可以使用访问令牌安全地访问客户支持服务。

```java
@Controller
public class SupportController {

    private static final Logger log = LoggerFactory.getLogger(SupportController.class);

    @Autowired("customerSupportRestTemplate")
    private RestTemplate webService;

    @RequestMapping("support")
    public String getTickets(Map<String, Object> model) {

        TicketList list = webService.forObject(
            "http://localhost:8080/support/ticket",
            TicketList.class
        );

        model.put("tickets", list);
        return "support";
    }
}
```

> 注意：需要这种复杂的配置是因为 Spring Security OAuth 没有提供插入额外令牌类型的机制，这意味着你必须扩展 `OAuth2RestTemplate` 并对其进行配置。希望 Spring Security OAuth 2 会提供此功能。

> 注意：你现在可能发现，如果你使用 own令牌，你必须使用 HTTPS。重定向到授权端点。即使你使用签名令牌，你仍然需要使用 HTTPS。重定向到授权端点。

## 总结

本章涵盖了为了防止未经授权访问而保护你的 Web 服务所涉及的大概念和技术。你学习了 OAuth 以及 OAuth 1.0a 和 OAuth 2.0 标准。你还没有深入研究 OAuth 标准，在将任何版本的 OAuth 实现放入生产环境之前，你应该阅读规范。你探索了 OAuth 2.0 在 Spring Security OAuth 中的工作，包括 Spring Security OAuth 如何帮助你创建资源应用程序和客户端。

本书从基础 Java Web 应用程序结构的简单介绍开始。你学习了 Servlet、JSP、自定义 JSP 标签、HTTP 会话、WebSocket 以及使用 Log4j 2 的应用程序逻辑。接下来，你探索了 Spring Framework 及其帮助你创建世界级应用程序的强大功能。之后你实验了 Java 持久化接口（API），并学习了 Spring Data 如何让实体持久化变得几行代码一样简单。最后，在最后一部分你学习了如何使用 Spring Security、表单身份验证和 OAuth 使你的应用程序安全。

你永远无法学完关于 Java EE、Spring Framework 和 Java 持久化方面的所有内容（持续学习是其中的乐趣所在！），但这本书已经为你提供了所需的工具，并让你走上了创建能够为你和你的客户提供良好服务的高级企业级应用程序的道路。

你在书中所使用的这些工具每天都会发布新版本，每个新版本都带来了可以改进你的应用程序的新功能。请关注这些新版本以及本书的后续版本，以掌握专业 Java Web 应用开发的最新技术和方法。

# 索引

## 数字与符号

- 3 字母 ISO 639-2 代码, 193
- 64 位指针, 9
- 101 切换协议 (Switching Protocols), 264, 265, 267
- 204 不允许内容 (No Content Allowed), 482, 483, 494, 498
- 302 临时位置 (Temporarily Location), 109, 110, 111, 371, 736
- 303 其他 (Not Other), 371, 736
- 307 临时重定向 (Temporary Redirect), 736
- 400 错误请求 (Bad Request), 264, 265, 479, 498, 822
- 401 未授权 (Unauthorized), 480, 481, 732, 733, 734, 735, 822, 824, 830
- 404 未找到找到 (Not Found), 179, 237, 480, 483, 488
- 405 方法未允许 (Method Not Allowed), 44, 480, 482
- 406 可接受 (Acceptable), 488
- 415 不支持的媒体类型 (Unsupported Media Type), 480
- 426 需要升级 (Upgrade Required), 264
- 500 内部错误 (Internal Error), 235, 237, 480, 488
- `#oauth2.clientHasAnyRole(String...)`, 837
- `#oauth2.clientHasRole(String)`, 837
- `#oauth2.denyOAuthClient(String)`, 837
- `#oauth2.hasScope(String...)`, 837
- `#oauth2.hasScope(String)`, 837
- `#oauth2.isClient()`, 837
- `#oauth2.isUser()`, 837
- `#AssertFalse`, 451
- `#AssertTrue`, 451
- `#asynch methods`, 347, 405, 407, 408, 449, 523, 524
- `#Auto-generated`, 341–342, 344, 345, 411, 449, 600, 610
- `#Component`, 341–345, 352, 391, 392, 395, 484, 489, 504
- `#ComponentScan`, 347, 348, 394, 395, 661
- `#Configuration`, 345–349
- `#Configuration.Set 解配置`
- `#Controller`, 341, 343, 348, 390, 393, 395, 416, 484, 505
- `@DecimalMax`, 451
- `@DecimalMin`, 451
- `@DeclareRoles`, 786
- `@DenAll`, 786
- `@Digits`, 451
- `@Enableable 注`, 163–164
- `@EnableAspectProxy`, 347
- `@EnableAsync`, 347, 405, 406, 607, 608, 792
- `@EnableCaching`, 347
- `@EnableLoadTimeWeaving`, 347, 608, 724
- `@EnableMBeanExport`, 347, 405, 608, 609
- `@EnableSerialization`, 633, 636
- `@EnableSpringConfig`, 347
- `@EnableSpringDataWeb`, 837
- `@EnableTransactionManagement`, 347, 558, 559, 607, 608, 792
- `@EnableWebMvc`, 348, 485, 653
- `@EnableWebSecurity`, 752, 776, 782, 809
- `@ExceptionHandler`, 489–490
- `@Future`, 451
- `@Injected`, 342, 345, 349, 600, 610, 342, 411, 449
- `@Injected ChatService`, 414
- `@Injected LocalResolver`, 427, 428
- `@Injected MutableService`, 803
- `@Injected NotificationService`, 408
- `@Injected RepositoryLayer`, 408
- `@Injected ServletContexts`, 533
- `@Injected SessionFactory`, 559
- `@Injected SessionRegistry`, 412
- `@Max`, 451
- `@Min`, 451
- `@ModelAttribute`, 66, 370–375, 389
- `@MultipartConfig`, 66
- `@NotBlank`, 468
- `@Null`, 451, 459, 461, 471, 613, 9Pattern, 451
- `@Past`, 453
- `@PathVariable`, 362–379, 392
- `@Pattern - 匿名`, 451, 453, 466, 467
- `@PreCommitAll`, 786, 787
- `@PostAuthorize`, 789–790, 796
- `@PostFilter`, 790, 796
- `@PreAuthorize`, 788–790, 795, 797, 809, 837
- `@PreFilter`, 790, 795
- `@Qualifier`, 341–342, 838, 861
- `@Qualifier`, 341, 343, 392, 395, 313, 484, 601
- `@RequestBody`, 338, 365–366, 388, 487, 492, 505
- `@RequestHeader`, 362, 365
- `@RequestMapping`, 356–370
- `@RequestParam`, 361, 62, 364, 367, 492
- `@ResponseBody`, 338, 369, 378–379, 489, 492, 493
- `@RestController`, 341
- `@RestEndpoint`, 485, 495
- `@RowsAllowed`, 788–788, 791, 795
- `@RunAs`, 787–788
- `@Scheduledmethods`, 347, 404, 405–408, 410, 371
- `@Section`, 787–788
- `@Service`, 341, 343, 344, 392, 393, 400, 484
- `@Size`, 452, 456, 468
- `@Transactional`, 357, 559, 599, 602, 607, 609, 618–622, 632
- `@ValidateOnExecution`, 449, 460
- `@Validates`, 454–455, 459, 470
- `@WebControls`, 381, 385
- `@WebListener`, 133, 134, 210
- `@ActivateServlet`, 126–127
- `@ActiveDirectory`, 739, 743, 744, 751
- `@ActiveDirectoryProvider`, 761–762
- activities, 741–743
- `addHeader()`, 56
- `addHeader()`, 56
- `addInt()`, 56
- `addParam()`, 149, 150
- `addListener()`, 133
- Address-Book I18n-project, 202–203
- Address-Book, 190–192
- Adobe Flash, 109, 223–264
- Advanced Messaging Protocol. 查看 AMQP
- Advanced-Criteria, 667–676
- Advanced-Mappings, 695–716
- AffirmativeBased, 797
- aggregate functions, 170
- AJAX (Asynchronous JavaScript and XML). 查看
- AJAX-request endpoints, 371, 378
- Comet, 261
- CSRF, 276
- Applets and Adobe, 263–264
- chunked encoding, 262
- frequent polling, 259–260
- HTTP1/1 feature, 264–267
- long polling, 70, 260–261
- requests, 124, 259–260
- same-origin policy, 481
- AMQP (Advanced Messaging Protocol)
- block configuration, 537–536
- distributed messaging, 534–540
- introduction, 520
- JS 比较, 139, 520, 536
- MSMQ 比较, 139
- multicaster, 537–539
- SOAP transport mechanism, 475
- AMQP-Messaging protocol, 537–539
- and keyword, 148
- Androst, 267, 324



# 索引

- annotation configuration, 15, 56, 64, 341, 343
- Annotations. 查看 annotations
- constraint annotations, JPA annotations
- annotation configuration (@Configuration), 15, 56, 64
- annotated metadata model, 443, 444–445
- filters, 238, 239
- anonymous authentication, 730–731
- abbreviated strings, EL function, 226–227
- abstract entities, with common properties, 710–712
- Initializer, 749–750
- AcceptLocation, 425, 487
- language header, 418, 422, 425, 436
- access list controls (ACLs), 798–804
- Decision Managers, 796–798
- Devisors, 795
- accessora, 125, 154, 161, 190, 223, 341, 344, 378, 380, 553, 569, 607, 718
- AccountController, 365, 391, 492
- RESTEndpoint, 491, 492, 495
- ACID-compliant, 303, 392, 677
- ACLs. 查看 access lists
- actions, 178
- ActionServlet, 317–318
- anonymous message board, 106
- ANSI SQL, 545, 547, 611, 799
- Ant, 20, 27, 356, 723
- ipatterns, 353
- Aspect pointcuts, 607–608, 794
- aspect-oriented programming, 325, 347, 353, 410, 745
- aspects, 325
- AOP support, Spring Framework, 325
- File, 224
- Logging, 307–308
- @Injected, 342
- asynchronous execution, 409
- asynchronous request, 237, 243, 249, 255
- AsyncServlet, 224, 247
- @Injected, 342, 345, 349, 600, 610, 342, 411, 449
- @Injected ChatService, 414
- @Injected LocalResolver, 427, 428
- @Injected MutableService, 803
- @Injected NotificationService, 408
- @Injected RepositoryLayer, 408
- @Injected ServletContexts, 533
- @Injected SessionFactory, 559
- @Injected SessionRegistry, 412

# 属性（继续）— 知感知接口

## 属性（继续）

- 前缀 prefix, 86, 179
- `removeAttribute()`, 123–124, 133
- 请求属性 attributes, 52, 89, 99–100, 120, 130
- `@RequestMapping`, 356–360
- 安全属性 Secure, 109, 118
- 会话属性 session attribute, 84
- 直接属性 direct attribute, 216–219
- uri 属性 uri attribute, 86, 179, 180
- 值属性 value attribute, 356–358
- 审计 auditing, 300, 302, 547
- 验证 authentication, 729–740
- 匿名 anonymous, 730–731
- 授权与验证的对比 compared to, 729–730
- 基础访问 basic access, 732–736
- 生物识别 biometrics, 732–738, 739
- 基于声明的 claims-based, 723–739
- 客户端证书认证 client certificate authentication, 737, 739, 766
- 已定义 defined, 729
- 摘要摘要访问 digest access, 736
- 过滤器 filters, 234–255
- 表单 form, 736
- 集成 Windows 认证 Integrated Windows authentication, 736–737
- 服务的机制 mechanism for web services, 817–818
- 微软 Windows 认证 Microsoft Windows authentication, 736–737
- 多因素 multi-factor, 739
- OpenID, 762–764, 819
- 密码 password, 731–738
- 记住我 rememberme, 752, 761, 765–766, 773, 783, 784
- 智能卡 smart cards, 738, 739, 818
- 用户名密码 username-password, 107, 732, 737
- 验证提供者 authentication providers
  - ActiveDirectoryLdAuthenticationProvider, 761–762
  - 自 custom, 766–773
  - DataAuthenticationProvider, 734, 748–749, 753, 759
  - LdAuthenticationProvider, 760–762
  - OpenID, 762–764, 819
  - 其他 other, 766
  - 记住我 rememberme, 752, 761, 765–766, 773, 783, 784
- 用户详情提供者 user details providers, 748–759
  - InMemoryUserDetailsManager, 749, 752, 753, 758
  - JdbcDetailsManager, 758–759
  - LdUserDetailsService, 759, 761
  - UserDetailsService, 748–759, 764, 765, 805, 807, 833, 853
- 认证应用项目 Authentication-App Project, 749, 754, 767, 769
- 认证控制器 AuthenticationController, 385, 409, 470, 774, 857
- 认证感兴趣方 AuthenticationInterestedParty, 52, 524, 533
- 认证主体 AuthenticationPrincipal, 782, 808, 856
- 授权 authorization
  - 活动 activities, 741–743
  - 授权与验证的对比 compared to, 729–730, 819
  - 基于声明的 claims-based, 743, 761
  - 客户支持项目 Customer Support project, 804–814
  - 声明式 declarative, 780–794
  - 组 groups, 741–743
  - 身份 identities, 740–741
  - 权限 permissions, 741–743
  - 主体 principals, 740–743
  - 角色 roles, 741–743
  - 理解 understanding, 740–743
  - 使用方法 ways to use, 745
- 认证注解 authentication annotations
  - 收益 benefits, 791
  - 通用注解 API Common Annotations API, 7, 786–787, 791, 792, 795
  - 配置支持 configuring support, 791–794
  - 声明权限 declare permissions, 786–794
  - 执行前后的后注解 pre- and post-execution annotations, 788–791
  - @servlet, 787–788
- 授权码模式授权 Authorization Code Grant, 827–829, 836, 837
- 授权视图 authorization views, 724–798, 799
- 授权表达式函数 authorization expression functions, 783–786, 795, 799
- 授权许可 authorization grants, 826–831
- 授权码模式授权 Authorization Code Grant, 827–829, 836, 837, 839
- 客户端凭据授权 Client Credentials Grant, 828, 834, 837, 839, 840
- 隐式授权 Implicit Grants, 828, 836, 837
- 资源所有者密码凭据授权 Resource Owner Credentials Grant, 826–829, 837
- 授权头部 authorization header, 733, 724, 821, 828, 834, 850
- 授权实现 authorization implementation, 836–840
- java 授权 java-authorization, 759–780
- 属性 Flush attribute, 83–84
- `@AutowiredPostProcessor`, 449
- 可用性 availability
  - 路器 breaker cluster, 335
  - 集群 clustering, 510, 514
  - Glass, 22
  - JBoss, 22
  - LDAP, 760
  - 粘性会话 sticky sessions, 141
  - Tomcat, 20, 22
- Bad Request
- Bad Request (400 状态码), 264, 265, 470, 490, 822
- JPA 存储库 base repository, 613–618
- EL 语法 base syntax, 145–146
- 字面量 base literals, 153
- Base64, 266, 373, 734
- 基础访问认证 base authentication, 732–736
- 标签 base.tag, 229–230
- BCrypt, 628–630, 632, 657, 732, 748
- Bean Definition Profiles
  - 模式 patterns, 353
  - 可刷新消息源 ReloadableMessageSource, 425
  - 安全关注 security concerns, 395
  - 利用 utilizing, 349–353
- Bean Validation (JSR 349), 441–472
  - 注解元数据 metadata, 433, 444–445
  - 后处理器 bean post-processors, 449–450
  - 约束注解 constraint annotations, 451–452
  - Spring Framework 中的配置 configuration in Spring Framework, 445–450
  - 已定义 defined, 442–443
  - 员工实体 Employee entity, 422–443, 452–454, 458–463, 465
  - Hibernate Validator, 444, 446–448, 454, 457, 458, 469
  - 国际化 (i18n), 448–449
  - JSR 303 标准, 440, 443, 446, 472
  - 本地化 (i10n), 448–449
  - Maven 依赖 Maven dependencies, 441–442
  - 方法返回值 method return value, 459–460
  - 方法验证 method validation, 458–465
  - MVC 递归验证 recursive validation, 454, 455, 459, 470
  - RESTful Web 服务 RESTful web services, 488–489
  - 验证组 validation groups, 452, 455–460
  - Bean Validation Constraint, 434, 469
  - BeanFactory, 338, 342
  - BeanFactoryAware, 362
  - beans 框架 beans framework, 338, 341, 342, 343, 345, 336, 372, 449
  - Spring 管理 Spring-managed, 326, 327, 328, 391, 405, 470, 410, 425, 445, 489, 512, 608, 787
  - beans 命名空间 beans namespace, 338, 350
- 令牌令牌 bearer tokens, 819, 830–831, 832, 833, 834, 853, 857, 861
- BigDecimal, 152, 153, 451, 570, 695
- BigInteger, 152, 451, 570, 776
- 二进制 Binary, 576
- 二进制 JSON Binary JSON, 302, 346
- 二进制大对象 (BLOBs), 594–595
- 二进制消息 WebSocket 集群 binary messages WebSocket cluster, 268–287
- 二进制操作 binary operation, 149, 150
- 指标 metrics, 737–739
- 位掩码 bit masking, 799
- 黑莓浏览器 Blackberry Browser, 267
- blank.jsp, 78
- BLOBs. 参见二进制大对象 see Binary Large Objects
- BoardController, 396–398
- `<body>`, 213
- BodyTag, 225
- BodySupport, 225
- 实体 Book entity Book entity, 568, 577–578
- 布尔值 Boolean, 576
- Bootstrap.java, 384–385
- 引导日志 Spring 货币 bootstrapping logging Spring Currency, 767–769
- 多个引导类 multiple bootstrap classes, 668–769
- Spring 框架 Spring Framework, 329–336
- 部署器描述 deployer descriptor, 330–332
- 程序化初始化 programmatically initializer, 332–336
- `<br />`, 75–76
- 括号 `[]`, 145, 149, 154, 164
- 断点 Eclipse, 38–39, 77
- IntelliJ IDEA, 34, 35–779
- 代理 broker, 311, 519, 535
- 代理 brokers 参见 WebSockets see WebSockets
- 苹果 Safari, 267, 283
- 黑莓 Blackberry, 267
- 从服务器获取数据 getting from server
- Applets 和 Flash Applets and Flash, 263–264
- 分块编码 chunked encoding, 262
- 频繁轮询 frequent polling, 259–260
- HTTP1.1 升级 HTTP1.1 Upgrade, 264–267
- 轮轮询 long polling, 70, 260–261
- Google Chrome, 36, 263, 280, 283, 379, 497, 736
- Internet Explorer, 36, 253, 267, 280, 283, 377, 379, 736
- Mozilla Firefox, 36, 253, 267, 280, 286, 737
- Opera, 264
- BSONClusterNode.java
- BSON, 302, 546
- 树索引 B-tree indices, 665
- `<buffer>`, 96, 97
- 缓冲区属性 buffer attribute, 83–84, 96
- 缓冲读取 BufferedReader, 54
- 约束注解 constraint, 451–452
- 业务逻辑 business logic
  - 编码器和解码器 encoders and decoders, 289–291



- JavaScript 图表 JavaScript chart, 294–296
- 服务器端点 server endpoint, 291–294
- 直接使用消息源 use message source, 437–440

- ChatController, 385, 437
- EndPoint.java, 292–294
- 簇服务 Cluster-Service, 392
- 到 WebSocket 的逻辑层 logic layer to WebSocket, 409–415
- 从 WebSockets 移动 move from WebSockets, 396–399
- ChatMessage, 290
- ChatMessageCodec.java, 290–261
- 检查 MultiValueParameterServlet, 59–61, 91
- 业务逻辑持久化 business logic persistence, 391–392
- 业务用户界面 business user interface, 390–391

- Chrome, 36, 253, 280, 399, 437, 736
- 分块编码 chunked encoding, 262
- 基于声明的授权 claims-based authorization, 738–739
- 基于声明的授权 claims-based authorization, 743, 761
- 业务规则 business rules, 422, 443, 445, 463, 464, 544
- 字节码 bytecode, 53, 76
- 字节码织入 bytecode weaving, 723, 786
- 字节 bytes, 153
- 架构 architecture, 15–16
- 父优先类模型 parent-first class model, 16
- 类委托模型 parent-class delegation model, 16
- 类作用域 class scope, 88
- WebSockets, 409–415
- 客户端 API WebSocket client API WebSocket, 271–272
- 客户端认证 client authentication, 733, 739, 766
- 客户端凭据 client credentials, 820–840
- 客户端许可 client Grans, 884, 837, 839, 840

# C

- `<choose>`, 185, 191, 206
- `<forEach>`, 186–187, 191, 216, 213, 220, 380
- `<if>`, 184–185, 191, 206, 232
- `<import>`, 188–189, 212, 213
- `<charSet>`, 185, 191, 206
- `<out>`, 182, 191, 220, 221, 232
- `<param>`, 121, 183, 188, 212
- `<remove>`, 189
- `<set>`, 189
- `<url>`, 112, 121, 178–184, 188, 206, 219
- 客户端拥有任意角色 `clientHasAnyRole(String)`, 837
- 客户端拥有某角色 `clientHasRole(String)`, 837
- 客户端-服务器范式 client-server paradigm, 510
- 已定义 defined, 819
- 机密 confidential, 819–825
- 公开 public, 826, 827
- 闭包 closures 参见 lambda 表达式 see lambda expressions
- 簇多播 `ClusterMulticaster`, 527–529, 531, 537–539
- `casAuthentication`, 766
- 级联样式表 Cascading Style Sheets. See CSS
- Caucho, 226
- CGLIB 代理 CGLIB proxies, 406, 407, 600–601, 621, 786, 846
- 链式管道操作 chained pipeline of operations, 168
- 配置 configuring, 515–517
- 描述 described, 513–517
- 分布式 EE 应用 distributable EE applications, 513–514
- 集群 clustering, 139–141, 514–515
- 多个部署 simulates with multiple deployments, 533–534
- 测试 testing, 533–534
- Tomcat, 515–517
- 字符编码 character encoding
  - `getCharacterEncoding()`, 53
  - `setCharacterEncoding()`, 55, 76, 79
- 字符大对象 (CLOBs), 594–595
- 字符 chars, 153
- 聊天 chat with, 288–296
- chat.css 样式 chat.css style, 288
- WebSockets, 284–288, 518–519
- 簇管理器 `ClusterManager`, 531–533, 537
- 簇消息端点 `ClusterMessagingEndpoint`, 528–529, 530, 537
- 簇节点端点 `ClusterNode.java`, 286–287
- 簇节点 Servlet `ClusterNodeServlet.java`, 285–286
- 控制器建议模式 cnonce – controller advice pattern
- nonce, 733–735
- 代码重复 code duplication, 634–638
- 集合字面量 literals, 153–154
- 附件集合 collection of attachments, 721–722
- 请求集合 collection requests, 477–492
- 集合 collections, 158–160. 参见流 Streams see Streams
- 集合 API Collections API, 153
- 列表 Lists, 153, 158, 159, 723
- 映射 Maps, 153, 154, 158, 709, 726
- 队列 Queues, 158
- 返回 returning, 170
- 集合 Sets, 153, 158, 159, 723
- 流 API Stream API, 167–172
- 列名 column names, embeddable, 702–703
- Comet, 261. 参见日志 see logging
- 逗号运算符 (`,`), 149
- 逗号对象 comma objects, 364, 492, 683, 774. 参见表单 see form
- 命令行选项 command-line option, Tomcat installation, 24–26
- 注释 `<comment>`, 117
- 注释变量 comments variable, 163–164
- JSP 中的注释 comments in JSP, 81–82
- 通用注解 API Common Annotations API, 786–787, 791, 792, 795
- 通用 Common
  - 参见 Spring Data Common: Spring Data Common
- 通用日志 Common Logging, Apache, 307, 308, 309, 319, 340, 345
- 比较器 `Comparator`, 169, 170
- 比较关系 comparational relations, 149, 150
- 编译时 compile time, constraint annotations logging, 457–458
- 复杂查询 complex queries, 666–670
- 添加自定义搜索方法 adding custom search method, 668–770
- 高级项目 Advanced-Criteria project, 667–776
- 从搜索输入创建 creating from search input, 670–774
- 索引和方法 indexes and method, 675
- 或方法 or method, 675
- 复杂数字 Number, 153
- 组件扫描 component scanning, 340
- 并发限制 concurrency limits, 340
- 并发超时 concurrency timeouts, 260, 262
- 连接池 connection pool, 546, 562, 563, 602
- 共识基础 `ConsensusBase`, 301
- 控制台日志 console logging, 301
- 约束注解 constraint annotations
  - 注解元数据 metadata, 433, 444–445
  - 属性 attributes, 451–452
  - 构建 build, 451–452
  - 自定义 custom, 466–469
  - 已定义 defined, 444
- 联系 POJO `Contact POJO`, 190
- 包含头部 `containsHeader`, 56
- 内容表示 content notation, 377–380
- 内容类型限制 `@RequestMapping`, 360
- 内容类型 contentType, 79, 84
- 内容类型 `Content-Type`, 54, 79, 189, 370, 377, 380
- 内容项参数 content item parameters, 61–62, 89, 92, 195, 196
- 上参数 Servlet `ContextParametersServlet`, 62
- 上参数 JSP `contextParameters.jsp`, 92, 93
- 契优先设计 contract-first design, 475, 477
- 契优先 XSD contract-first XSD, 501–503
- 契后设计 contract-last design, 475, 477

## controller methods – CSS

### controller methods

- 参数, 360
- 有效返回类型, 358–358
- 控制器 (Spring MVC controllers), `@RequestMapping`
- 另见：reports，Customer-v10项目，384–387
- Maven 依赖, 355–356
- 将业务逻辑移动到 service, 396–399
- 参数验证, 462–463
- RESTful web services, 484–496
- 将 RESTful 请求映射到控制器方法, 491–495
- 按构型注解分离, 484–485
- 分离 web 和 REST 应用上下文, 485–498
- 转换为控制器的 Servlets, 385–386
- 总结, 387–388
- 用户界面逻辑, 393
- Controller-Service-Repository MVC, 390–391, 416
- 程序逻辑类型, 391–393
- 转换注解, 696–698
- Cook, 818
- `<cookie-config>`, 116, 117, 118, 336
- 定义, 108
- `document.cookie` DOM 属性, 114
- `getCookies()`, 55
- isSecure, 115
- JSESSIONID, 110, 111, 112
- 维护, 110
- Secure cookie flag, 115, 118
- session ID, 110, 114, 117, 166, 817, 825
- Set-cookie headers, 108, 109, 110
- Spring Security 过滤器, 750
- 复制粘贴方法, 136
- 核心标签 (类名), 192–182
- Address-Book-project, 190–191
- `<choose>`, 185, 191, 206
- `<forEach>`, 186–187, 196, 201, 213, 220, 380
- `<for>`, 187–188
- `<if>`, 184–185, 191, 205, 206, 232
- `<import>`, 188–189, 212, 213
- `<otherwise>`, 185, 191, 206
- `<out>`, 182, 191, 206, 220, 221, 232
- `<param>`, 121, 183, 188
- `<remove>`, 189
- `<set>`, 189
- `<url>`, 112, 121, 178, 183–184, 188, 206, 212, 219
- `<when>`, 185, 191, 206

### Core TLD

- c.tld file, 209, 211, 216
- 文档根, 211–212
- 函数, 216–217
- 初始声明, 211/listeners, 212
- 位置, 211
- 标签文件, 216
- 标签库条目, 217
- 验证器, 212

- Couchbase, 547
- count: option, 170
- 错误日志级别, 304
- `createTicket()`, 68, 69, 130, 236
- `createUser()`, 381, 383
- creds
  - 客户端凭据, 820–840
  - Client Credentials Grant, 828, 834, 837, 839
  - 定义, 820
  - Resource Owner Password Credentials Grant, 828–829, 837, 839
  - 临时凭据, 820–824
  - token 凭据, 820–824
- criteria API. Java, 671–674
- 跨内容问题, 325
- 跨域攻击, 266
- 跨源资源共享 (CORS), 481
- 跨站请求伪造 CSRF
- 跨站脚本 (XSS), 114, 155, 182, 817
- crud
  - JPA 操作, 611–612
  - 程序化触发器, 717–720
  - RESTful web services, 476
- CSRF (跨站请求伪造), 775–778
- Authorization Code Grant, 827
- `<element>`, 855
- `<html>` 元素, 813
- `<securityfield>`, 813
- Web 服务安全, 816

### CSS (层联样式表)

- chat.style sheet, 289
- `configure(WebSecurity)` 方法, 752
- EL 表达式, 147
- main.css sheet, 289
- `/resource/styles/login.css`, 228, 229, 230
- `/resource/stylesheet/main.css`, 228, 230
- tic-tac-toe game, 273, 278
- c.tld file, 209, 211, 216
- 文档根, 211–212
- Spring Framework 主题, 429
- 货币转换, 193, 199
- 自定义约束注解, 466–469
- 自定义类型。另见 de-serialization-data
- 自定义下载, 386–387
- 自定义事件, 525–527
- 自定义标签和函数库, 209–232
- 日期格式标签, 221–224
- Java 替换为 JSP 标签, 227–232
- Maven 依赖, 209–210
- Template-Tags 项目, 219–228
- Constraints 项目, 466–469
- 匿名留言板, 106
- 身份验证, 225–254
- 授权, 804–814
- Bean Validation, 470–472
- 支持聊天, 288–296
- Checkpoint.java, 294–292
- JavaScript 应用, 294–296
- 服务器端点, 291–294
- 直接使用消息, 477–440 (页面错误)
- Customer-Support-v1, 65–71
- Customer-Support-v2, 94–101
- Customer-Support-v3, 129–139
- Customer-Support-v4, 172–174



- Customer-Support-v5, 205–207
- Customer-Support-v6, 227–232
- Customer-Support-v7, 254–255
- Customer-Support-v8, 289, 295–296
- Customer-Support-v9, 319
- Customer-Support-v10, 384–387
- Customer-Support-v11, 409–415
- Customer-Support-v12, 436–440
- Customer-Support-v13, 470–472
- Customer-Support-v14, 500–508
- Customer-Support-v15, 624–632, 634
- Customer-Support-v16, 636–666
- Customer-Support-v17, 677–684
- Customer-Support-v18, 720–725
- Customer-Support-v19, 766–775
- Customer-Support-v20, 804–814
- Customer-Support-v21, 840–856
- 自定义资源服务, 850–851
- 实现客户端服务, 842–847
- 实现 token 服务, 847–850
- 国际化, 436–440
- Java 替换为 JSP 标签, 227–232
- Java 替换为 EL, 172–174
- Java 替换为 JSP 标签, 205–207
- 局部化 (L10n), 436–440
- 日志, 319
- Widget Corporation, 65, 106, 254, 388
- 多部分支持, 384–385
- 重配置 Spring, 852–856
- 重构, 656–661
- 请求需求, 804–842
- 转换为控制器, 385–386
- 活跃话列表, 135–139
- 监听器, 133–135
- 登录容量, 129–132
- 签名令牌, 840–842
- Spring Web Services, 500–508
- 细节, 804–808

## D

- `DaoAuthenticationProvider`, 734, 748–749, 753, 759
- `Data Access Objects`, 328, 748
- 来自服务器
- Applets 和 Flash, 263–264
- 分块代码, 226, 259–260
- 频繁轮询, 259–260
- HTTP 1.1 功能, 264–267
- 长轮询, 260–261
- 数据持久化，见 JPA
- 存储，仓库的, 399–404
- 数据类型, 756
- `<data:jackson2-popular>`, 647
- `<data:jackson-popular>`, 647
- `<data:jpa:auditing>` 元素, 649
- `<data:jpa:repositories>` 元素, 447–648
- 子元素, 447
- `<data:unmarshaller-populator>` - `doFilter()`
- `<data:unmarshaller-populator>`, 647
- 数据库访问。见 SQL列表
- 数据库。另见 NoSQL；关系型数据库
- `DataSourceTransactionManager`, 599, 620, 621
- 日时间 API (ISR 310)
- 日时间占位符, 420
- 日时间类型, 592, 594, 652, 695
- 日期格式标签, 221–224
- 日期
- `addStateHandler()`, 56
- `DayOfWeek` 枚举, 137
- 格式化器, 223
- Debug, 日志级别, 304
- 缺点, 298–299
- Servlets, 49–151
- Eclipse, 35–39
- IntelliJ IDEA, 30–35
- `DECIMAL`, 576
- 声明, 79, 102
- 声明式授权, 780–794
- dec 和编码器， 短, 289
- 解密。见 `<deferred-content-type>`, 95, 96, 336
- `DefaultAuthenticationProvider`, 766
- 求值 EL 表达式, 145, 146, 215
- `<deferred-method>`, 146, 215
- `<deferred-syntax-allowed-as-literal>`, 96, 176
- `<deferred-value>`, 146, 215
- DELETE
- CSRF 令牌, 75, 776
- `doDelete()`, 43
- HTTP 方法, 43, 52, 359
- OAuth 客户端, 838
- RESTful web services, 476, 483
- SQL 语句库, 203
- anyall, 783
- `dayClient()`, 837
- 依赖注入 (DI), 325, 353, 445
- 部署器 Spring Framework, 330–332
- 定义, 15–16, 46
- 过滤器, 237
- JS 属性配置, 94–97
- `<jsp-config>`, 95, 116, 140, 179–180, 211–220
- `<script-invalid>` 标签, 95, 96, 217, 227
- 添加的 Servlet, 44–60
- `<session-config>`, 116–188, 129, 160
- 模板代码, 336–337
- `<description>`, 211, 212, 213, 215, 216, 218, 584
- `destroy()`, 45–46, 50, 235, 290, 586
- DI. 依赖注入
- 方言, Hibernate ORM, 605–606
- 字典数组, 628, 732
- 摘要身份验证, 733–779
- JSPs, 79–86
- 可发现性, 477–499
- Discussion-board, 396–408
- `DiscussionController`, 396, 397, 399
- `DispatcherServlet`, 328–335, 330, 342, 344, 426–437
- `DispatcherServlets`, 328–335, 339
- 禁用验证错误, 463–465
- `<display-name>`, 47, 58, 94, 213, 216, 217
- 不同的操作, 168
- 可分发 EE Web 应用, 513–554
- 分布消息。另见 AMQP, 534–550
- 问题, 518
- sits, 717–518
- div 关键字, 148, 149, 150
- `divide()`, 14, 150

### 实体（续）—— 档案柜类比

实体（续）

`Employee`（员工）, Bean Validation, 442–443, 452–454, 458–465, 468

查找, 查询方法, 639–642

映射类, 710–712, 717, 718, 719, 720

- 嵌入在实体中的 POJOs, 699–703

关系

- 多对一, 708–709
- 多对一, 705–708
- 一对一, 703–704

`@RequestBody`, 365–366

响应实体, 328, 369–370, 375–380

存储, 在多张表中, 716–717

版本控制, 709–710

实体字段, 569

实体监听器, 719–720

实体管理器, 线程, 599–600

Entity-Mappings 项目, 560–581–595

枚举

- EL 表达式, 147
- 作为实体属性使用, 590–592

Enums-Dates-Object, 590–595

`EnvironmentAware`, 342

eq 运算符, 148, 149, 150

等值关系运算符, 149, 150

equal 方法, 150

erlang

- 错误处理

过滤器, 235

国际化 (i18n), 433–436

持久化实体, 548

RESTful 网页服务, 488–491

错误级别日志, 304

er 资源请求, 237

`<error-on-undeclared-namespace>`, 96, 97

errorPage, 84

错误

- EL 语法错误, 145, 146, 147, 151, 152, 153, 159
- 致命错误/崩溃, 日志级别, 304

HTTP 状态码

- 201 切换协议, 264, 265, 267
- 204 无内容, 482, 483, 494, 498
- 302 临时重定向, 109, 110, 311, 371
- 303 查看其他, 371, 736
- 307 临时重定向, 736
- 400 请求请求, 264, 265, 479, 490, 482
- 401 未授权, 480, 481, 732, 733, 734, 822, 824, 830
- 403 拒绝, 480, 481, 785, 787
- 404 未找到, 179, 237, 480, 481, 488, 493, 498
- 405 方法未允许, 44, 480, 482
- 406 不可接受, 480
- 415 不支持的媒体类型, 480
- 426 需要升级, 264
- 500 内部服务器错误, 235, 237, 480, 488

isErrorAttribute, 84, 90

JSP-编译, 175

Event 日志, 302

事件多播器

- `EventListenericaster`, 527–529, 531, 自定义, 525, 527–529
- 标准, 527

事件（应用事件）

- 通过 AMQP, 534–540
- 发送到, 525
- 发布, 342, 523–524
- 与 WebSockets 接收, 529–530
- 订阅到, 522–523
- 支持, 526–527
- `<example>`, 216, 219
- 异常翻译, 601–602
- 异常变量, 84, 90
- 执行器, 404–405
- Expires 属性, 108, 109
- 显式视图, 371–373
- 表达式. 见 EL
- JSF, 80–81, 102
- extends 属性, 84
- 外部事件处理器, 719
- Facelets, 75
- 故障转移
  - 集群, 551
  - 控制台日志, 301
  - false 关键字, 148, 151
- 致命错误/崩溃, 日志级别, 304
- Fiddler, 109, 266, 367
- 文件上传, 到 Servlets, 64–69
- 档案柜类比, 664, 876

### Filter-plex 通信

Filter, MessageSource, 423–424

过滤器链, 235–236, 242, 267, 268, 769, 771, 775, 782, 789

过滤器操作, 168

Filter-Async, 243

`FilterChain`, 235, 236, 241, 244, 248, 250

Filter-Order 项目, 241–243

过滤器

- 注解用法, 230, 239
- 异步请求处理, 237, 243–247, 249, 255
- 身份验证过滤器, 234, 254–255
- 压缩过滤器, 234–245, 237–253, 255
- Filter-Compression 项目, 247
- `CompressionFilter.java`, 249–253
- Customer-Support, 234–255
- 部署用法, 237
- 加密过滤器, 234–233, 255
- 错误处理, 235
- 日志过滤器, 238–249, 767–768
- 映射
  - 到分发器, 236–237
  - 到 URL, 236
  - URL 模式映射, 239–241
- 顺序, 239–243
- 实际用途, 234–245, 237
- 程序化配置, 238–239
- 目的, 235
- `RequestFilter.java`, 248–249
- 响应过滤器, 234–245, 247–253, 255
- 与 Servlets 比较, 234

Filter, List, 2, 301–312

过滤器, Spring Security, 749–750

框架, 460

firstOperation, 171

Fiddler, 109, 266, 367

FINE 日志级别, 304

FINER 日志级别, 304

FINEST 日志级别, 304

Firefox, 326, 263, 267, 268, 280, 736, 737

first hash, 738

Fish 标签, 316–319, 747

Flash, Adobe, 109, 214, 263–262

扁平文件, 301–302, 544

Float, 451, 576

float, 152, 451, 576

Fmt 命名空间. Servlet. 国际化与格式化日志

- `<fmt:bundle>`, 196–197, 198
- `<fmt:formatDate>`, 198–199, 201, 202, 222
- `<fmt:formatNumber>`, 199–200, 420
- `<fmt:message>`, 194–195, 196, 201, 423, 430, 431, 432, 437, 440
- `<fmt:parseDate>`, 198–199, 200, 204
- `<fmt:parseNumber>`, 199–200
- `<fmt:requestEncoding>`, 197
- `<fmt:setBundle>`, 194, 196, 197
- `<fmt:setLocation>`, 196, 197, 198
- `<fmt:timeZone>`, 197–198
- `${fn:toString}`, String, 155, 217
- `${fn:escapeXml(String)}`, 155, 164, 182
- `${fn:join(String, String)}`, 156
- `${fn:length(Object)}`, 156, 64
- `${fn:toLowerCase(String)}`, 156
- `${fn:toUpperCase(String)}`, 156
- `${fn:trim(String)}`, 156

food 链, 393

Forbidden (403 状态码), 480, 481, 785, 787

forEach 操作, 169

form 身份验证, 736

form 对象

- command 对象, 364, 492, 683, 774
- 输入绑定, 364–365
- 提交, 383–384
- 使用, 380–384
- `<form>` 标签, 381–383
- `<form:checkbox>`, 383
- `<form:checkbox>`, 383
- `<form:errors>`, 382
- `<form:input>`, 382, 777
- `<form:label>`, 382
- `<form:options>`, 383
- `<form:options>`, 383
- `<form:password>`, 383, 777
- `<form:radiobutton>`, 383
- `<form:radiobuttons>`, 383
- `<form:select>`, 383

FormatDate, 222, 227

格式化标签, 194, 196, 197. 见集成与格式化

forum 系统, 740–742

转发请求, 273

`ForumPostImpl.java`, 689–691

框架 beans, 338, 341, 342, 345, 372, 449

FreeMarker, 75, 371

频繁轮询, 259–260

full-plex 通信, 263, 264, 877

### full-indexes 与 JPA

full-indexes 与 JPA, 676–678

MySQL 表, 777–778

移植的, 684

可搜索仓库, 678–684

搜索, Apache, 684–692

- `<function>` 元素, 216–217
- function 类元素, 217, 226
- Function 库, 155, 156, 172. 见 JSTL
- `${fn:contains(String, String)}`, 155, 217
- `${fn:escapeXml(String)}`, 155, 164, 182
- `${fn:join(String, String)}`, 156
- `${fn:length(Object)}`, 156, 64
- `${fn:toLowerCase(String)}`, 156
- `${fn:toUpperCase(String)}`, 156
- `${fn:trim(String)}`, 156
- function 签名, 217, 226
- `getInt()`, 55
- `getLastAccessedTime()`, 124
- `getLocal()`, 223, 418, 426, 435
- `Locales()`, 418
- `getLocalizedMessage()`, 435
- `getInInterval`, 124
- `getOrientation(Locale)`, 430
- `getOutputStream()`, 55, 89
- `getParameter()`, 33, 165
- `getProperty()`, 53
- `getterNames(String)`, 53
- `getParameterValues()`, 53, 165
- `getPort()`, 64
- `getParts()`, 64



## 索引

`Renderer()`, 54

`getRepliedDiscussion()`, 398, 399, 401, 402

`getRequestURL()`, 54

`getServerURL()`, 54

`setServletPath()`, 54

`getSession()`, 55, 120–121

`getStatus`, 56

### G

`game.jsp`, 279–282

Game-Site 项目, 273–283

get 运算符, 148, 159

`GeetingServiceImpl`, 337, 338, 344, 348

`GenericBaseRepository`, 616, 654, 656

`GenericRepository`, 616, 617, 618, 624, 627, 635

`GenericRepository`, 614, 615, 624, 638, 654, 656, 657

`GenericServlet`, 42–43, 51

`Generonic`, 20, 21

`doGet()`, 43, 44, 50, 51, 57–58, 59, 60, 65, 66

OAuth 类, 138

online, 43

`getAllDiscussions()`, 398, 400, 401

`getAuthentication`, 784

`getCharacterEncoding()`, 53

`getContentLength()`, 53, 53–54

`contents()`, 53

`getCookies()`, 55

`getHeader()`, 55

`header()`, 54, 56

`getHeaderNames()`, 54, 56

`getInputStream()`, 53, 54

getter methods. 见 accessors

`getTime()`, 223

`getWriter()`, 44, 55

geberish., 81

GlassFish, 21–22, 140, 181, 222, 447, 515, 552, 724

GlassFish Administration Service, 515

global security 注, 743–794, 796–797, 803, 808, 854

Google Chrome, 26, 373, 265, 280, 283, 379, 497, 736

GPU-based attacks, 732

`GuaranteedAuthority`, 744, 745, 749, 752, 766, 784, 833

databases, 547

`GenericServiceImpl`, 337, 338, 340, 348

Groovy, 5, 324

### H

Hammer, 818, 819, 820, 831

`HandlerInterceptor`, 427–428

handling errors. 见 handling

authorization privileges, 741–743

validation groups, 452–456

hard deletes, 483

HQL Query Language

`hasAuthority`, 783, 784, 785, 837

HR-Portal 项目, 445–465

HTML comments, 81–82

HTML tags, 75, 87, 147, 182, 183, 207, 388

`hasAddress`, 783, 785

`hasPermission`, 783, 791, 795, 799, 802, 813

`hasRole`, 783, 857

`hasScope (String)`,

HTTP cookies, 266

HTTP prelude, 266

HTTP request method, 358–359

HTTP security headers, 777

HTTP sessions, 见 sessions

HD video streaming, 268

HEAD

HTTP 状态码

- 101 切换协议, 264, 265, 266
- 204 无内容, 483, 484, 498
- 302 临时重定向, 109, 110, 311, 371, 736
- 303 查看, 见 371
- 307 临时重定向, 736
- 400 请求请求, 264, 265, 479, 490, 482
- 401 未授权, 480, 481, 732, 733, 734, 822, 824, 830
- 403 拒绝, 480, 481, 785, 787
- 404 未找到, 179, 231, 480, 481, 488, 493, 498
- 405 方法未允许, 440, 480, 482, 882
- 406 不可接受, 460
- 415 不支持的媒体类型, 480
- 426 需要升级, 264
- 500 内部服务器错误, 233, 237, 480, 488

HTTPD, Apache, 140, 301, 505

HTTP 方法, 435, 459

RESTful web, 481–482

RESTful 网页服务, 479–480

Session API, 554–556

First Design Patterns (O'Reilly), 370

HelloController, 337–338

Hello-User 项目, 88–92

Hello-World 项目, 44–56

Hello-World JSP, 75–76, 81, 85

Hibernate ORM

Hibernate Validator, 444

mapping files, 552–554

Maven dependencies, 564

Oauth client, 338

HMAC-SHA1, 821

HTTP/1.1 Feature, 264, 265, 267

sticky sessions, 141

Tomcat, 20

WebSockets, 269, 271, 273

### HttpSessionListener – 国际化

`HttpSessionListener`, 133–134, 134, 135, 212, 292, 410, 473

混合配置, Spring Framework, 340–345

超媒体作为应用状态引擎 (Hypermedia as the Engine of Application State), 477

HyperSQL, 350, 505, 684

超文本语言 (Hypertext Language), 479

#### 初始化参数

- 内存中的 context, 61–62, 89, 93, 165, 196, 200, 204, 432
- servlet 初始化, 25, 61, 62–64, 395
- `initDestroyAnnotationBeanPostProcessor`, 449

#### 初始化器

- `AbstractSecurityWebApplication initBean`, 749–750, 769
- 启动 Spring Framework, 332–336
- Servlet 容器初始化 (ServletContainerInitialization), 62, 118, 133, 238, 330, 332, 335, 318, 479
- Web 应用初始化 (WebApplicationInitialization), 333, 335, 348, 371, 384, 749, 768
- `initParam`, 165
- 注入持久化, 100–611
- 注入攻击, 182
- 内存发现仓库 (InMemoryDiscoveryRepository), 402
- 内存回复仓库 (InMemoryReplyRepository), 403
- `InUserDetailsManager`, 749, 752, 758
- 输入表单绑定, 364–365
- `InputStream`, 53, 68, 272, 286, 290
- 源代码编码器, 115
- `instanceof` 关键字, 148
- 即时消息服务, 510
- `intInteger`, 576
- Windows 集成身份验证 (Integrated Windows Authentication), 736–737
- 初始化合约注解, 460

#### IntelliJ IDEA

- 断点点, 34–35, 39, 77
- web 调试主题, 30–35
- orm.xml XML, 566–567
- Sample-Debug–IntelliJ, 32, 34–35
- 中间操作, 168–169
- 间歇性服务器错误 (状态码200), 235, 237, 480, 488
- 内部资源视图, 371

#### 国际化 (i18n)

- 通讯录 i18n 项目, 200–203
- Bean 校验 (Bean Validation), 448–449
- 代码, 430–436
- 配置, 424–430
- 客户支持, 436–440
- 定义, 193
- 错误处理, 433–436
- 处理器拦截器, 427–428
- 本地解析器, 425–427
- 本地化到, 193
- 消息源 (message sources), 421–425, 437–440
- Spring Framework 工具, 417–440

### i18n. 国际化

- i18n 标签, 194–196
- IANA 时区数据库 (IANA Time Zone Database), 198
- mybatis, 551
- `<icon>`, 111, 213, 216, 317, 218
- 等等性, 483
- 身份标识, 740–741
- IETF (任务组), 820, 826
- iis 服务器, 140, 141, 515, 516
- `IllegalArgumentException`, 55, 54, 240
- `illegalStateException`, 53, 55, 244, 247
- 实现 El, 195, 146
- 隐式代码, 161–164
- 隐式 Grants, 828, 836, 839
- 隐式版本, 83, 89, 122
- 隐式变量
- EL 表达式, 160–161, 165–167
- jsr, 38–93, 160
- 隐式视图, 373–375
- import 属性, 82, 83, 218
- include 指令, 85–107, 212
- `<include>`, 95, 96, 97
- 包含请求, 237
- `<include-exclude>`, 95, 96, 97
- includer, 1, 85
- 方法, 666
- B-tree, 665
- 复杂查询, 676
- 信息, 664–666
- 索引到, 664
- `indexjsp`, 34, 38, 39, 75, 101, 116, 180, 190, 215, 385
- `IndexEndpoint`, 495–496, 500
- 索引, 664
- info 日志级别
- 日志级别, 304
- 继承注解, 466–469
- 层级日志器, 310
- `init()`, 45–46, 50, 223, 235, 284, 586

### 国际化与格式化 — Java 平台

- 非西方区域, 430, 440
- 主题, 229–430
- 时区支持, 429
- 用户配置, 428–429

#### 国际化与格式化 (FMT 命名空间), 193–203

- 通讯录 i18n 项目, 200–203
- 投诉, 199
- 组件, 199
- 货币转换, 193
- `<fmt:bundle>`, 198–199
- `<fmt:formatNumber>`, 199–220, 430
- `<fmt:message>`, 194–195, 196, 221, 430, 431, 437
- `<fmt:parseDate>`, 198–199, 204
- `<fmt:parseNumber>`, 199–220
- `<fmt:requestEncoding>`, 192
- `<fmt:setBundle>`, 194, 196, 198
- `<fmt:setLocale>`, 196, 197
- `<fmt:setTime>`, 197–198
- `<fmt:setTimeZone>`, 197–198
- 格式化标签, 194, 197
- i18n 标签, 194
- 简介, 193
- 简化用法, Spring Framework, 418
- `InternationalizedException`, 434–435

### 互联网工程任务组: 查看 Servlet

- Internet Explorer, 36, 255, 267, 280, 387, 379, 736, 737
- Internet Explorer Mobile, 62
- 解释型脚本语言, 79
- 包含子句, 640–641
- 反转控制 (loc), 325, 353, 743
- loc, 查看 反转控制
- IOS, 267
- IRC 协议, 264
- `isAnonymous`, 783, 788, 799
- `isadiabatic`, 140, 141, 515, 516
- `isAuthenticated`, 744, 770, 783
- `isClient`, 837
- `isIgnored` 属性, 83, 96, 218
- `isErrorPage` 属性, 84, 90
- `isFullyAuthenticated`, 783, 784, 775
- ISO 639-1, 193
- ISO 639-2, 193
- ISO 3166-1, 193
- ISO 8859-1, 53, 54, 78, 96, 189, 197, 222
- `isRememberMe`, 783, 791
- `isThreadSafe` 属性, 84
- `isUser(I)`, 837
- `IterationTag`, 224, 225
- `IterationSupport`, 225

查看 Java 企业版平台

查看 Java 标准版平台

- `JaAuthenticationProvider`, 766
- `ObjectMapper`, 377
- EAR 文件, 17, 578–583
- Jasig 中央认证服务, 744, 766
- Java, 查看 450
- Java 企业版平台 (JEE), 5–6
- Java 标准版平台 (JSE), 4, 5, 6

### Java 运行时环境

- Java 运行时环境 (JRE), 4, 16, 25, 26, 35, 76
- Java SE. 查看 Java 标准版平台
- Java 序列化, 286, 510, 529, 539, 576
- Java Server Faces (JSF), 6, 75, 144, 145, 176
- Java 统一语言. 查看 EL
- Java 虚拟机 (JVM), 4
- Java WebSocket APIs, 270–273
- JavaBeans 框架, 6
- Jakarta 开源软件. 查看 JBoss
- JavaScript. 查看
- 数组, 154
- 聊天应用, 294–296
- 跨站脚本, 114, 155, 182, 277
- `document.cookie` DOM 属性, 114
- ECMAScript, 144, 154
- EL, 147, 153
- HTML5 (JavaScript) 客户端, 268–270
- HTTP 输出, 109, 114
- 注入, 206
- jQuery 库, 273, 278
- literal 151
- Node.js, 268
- 会话劫持, 114
- XML 实体, 146
- Java 泛型代码, 278–282
- JavaServer. 查看 JSP
- Java Servlets 标准标签库. 查看 JSTL
- `java.time.TemporalAccessor`, 221
- `java.util.logging`, 299, 303, 304, 306, 307
- `java.validation.Validator`, 446
- `jaxb.Jaxb2Marshall`, 376, 377, 380
- JBoss (Java 开源软件), 224, 724
- JBoss 日志 API 依赖, 445
- JDBC (Java 数据库连接)
- ACL 实现, 802
- API, 552, 688, 696
- 定义, 546
- 驱动, 362–363
- `JdbcTemplate`, 598, 602, 637, 641
- `JdbcEntityManager`, 758–759
- JDK (Java 开发包)
- 编译器, 227
- 定义, 3, 4
- OpenJDK 项目, 5, 300
- Jetty, 22, 23, 324
- JIT. 查看即时编译
- JMS (Java 消息服务, JSR 343)
- AMQP 比较, 139, 520, 536
- 引入, 519–520
- MSMQ 比较, 139
- SOAP 传输机制, 475
- Joda Time, 12, 454, 551, 649, 651, 695
- 切接点, 475
- JPA, 22

#### JPA (Java Persistence API). 另 Spring JPA

- Bean 定义, 349
- 在 Spring Framework 中配置, 602–610
- 查找数据, 602–610
- 代码中的持久化单元, 603–607



- Java EE 5, 7
- 学习, 863
- Maven 依赖, 564
- Spring Framework 支持, 325

### JPA 注解

- 映射项, 565–596
- 基础类型, 576–577
- CLOB 和 BLOB, 594–595
- 列名, 579
- 复杂类型, 590–595
- 日期和时间, 592–594
- 实体字段, 569
- 实体映射, 590–592
- 属性的枚举, 590–592
- 枚举 Lobs 项目, 590–595
- 标记项, 567–569
- 代理键, 570–575
- XML 映射, 566–567

### JPA criteria API. 另请搜索

- 复杂查询, 626–676
- 添加自定义搜索方法, 668–680
- Advanced-Criteria, 667–676
- 从输入创建, 670–674
- 索引, 676
- 和方法, 675

# JpaTransactionManager – JSTL

`JpaTransactionManager`, 600, 609, 619–621, 632

- 部署描述符中的配置, 94–97
- 使用, 96–97
- 在运行时, 66–77
- Servlets, 76

`JPQL` (Java Persistence查询语言), 551, 611, 618, 632, 634, 641, 642, 679

- 查询 DataScript, 273
- JRE. 参见 Java Runtime Environment (Java 环境)
- Ruby, 5
- Servlets-JSPs 组合, 94–101
- 会话中的, 121–122
- 与 HTML 文档状态对比, 74–75
- Tomcat 版本, 21–181
- `jspService` 方法, 77, 80, 86, 88

`JSESSIONID Cookie`, 100, 111, 112, 116

JSP 参见 Java Server Files (Java 服务器文件)

JSON

```jsp
<jsp:set>Property,
<jsp:useBean>, 187
```

JSP 参见 JSP Documents (JSP 文档)

- Ajax, 259
- 数组, 154
- 二进制 JSON, 302, 546
- Java 序列化, 286
- 日志, 301

JSR 303, 440, 443, 446, 472. 参见 Bean Validation (Bean验证)

- JSR 310. 参见 Date and Time API (日期时间 API)
- JSR 343. 参见 JMS (Java 服务)
- JSR 349. 参见 Bean Validation (Bean验证)

STL (JSP 页面标签库), 177–208

- XML 处理标签库, 205
- JSP API, 70, 74, 181
- JSP 注释, 82, 102, 163
- JSP 指令, 76–219
- JSP 文档 (JSPX), 102
- JSP 片段. 参见 JSP Files (JSP 文件)
- JSP 解析器, 179
- JSP 属性组, 95–96
- JSP 脚本库, 70, 90, 914
- JSP 标签库, 14, 179, 180
- XSD, 211
- 核心标签库 (C 命名空间), 182–192
- 电话录项目, 190–202
- `<c:choose>`, 185, 191, 206
- `<c:forEach>`, 186–187, 191, 206, 213, 220
- `<c:tokens>`, 187
- `<c:if>`, 184–189, 191, 205, 232
- `<c:import>`, 188–189, 212, 213
- `<c:otherwise>`, 185, 191, 206
- `<c:out>`, 182, 191, 206, 220, 232
- `<c:param>`, 121, 183, 188, 212
- `<c:remove>`
- `<c:set>`, 189
- `<c:url>`, 112, 121, 178, 183, 184, 206, 212, 219
- `<c:when>`, 185, 191, 202, 209–232

JSP 标签. 参见 84–84, 144

- `<jsp:tag>`, 95, 116, 146, 160, 179–180
- JSP 文件 (JSP fragments), 86, 228
- `<jsp:forward>`, 84, 180, 237
- `<jsp:getProperty>`, 87
- `<jsp:include>`, 85, 86, 87, 180, 237
- `<jsp:plugin>`, 187
- `<jsp:group>`, 95–96, 197, 136
- JSPs (服务器页面), 73–104
- 替代方案, 375
- 自定义 JSP 编译器, Tomcat 26–27
- 文件结构, 78–79
- 隐式变量, 88–193
- 导入 Java 类, 82–83
- JSPs 中的 Java, 88–94, 142, 172
- 生命周期, 77
- Maven 依赖, 73–74
- 表示层, 94, 98–101, 203, 318
- EL 规范, 144, 155
- 函数库, 155–156, 172, 175
- `${fn:contains(String)}`, 155
- `${fn:escapeXML(String)}`, 155, 164, 182
- `${fn:join(String)}`, 156
- `${fn:toLowerCase(String)}`, 156
- `${fn:toUpperCase(String)}`, 156
- `${fn:trim(String)}`, 156
- 历史, 6, 144
- 国际化与格式化标签库 (FMT 命名空间), 193–203
- i18n 项目, 200–203

# JSTL (续)

- 负载均衡, 94
- 货币版本, 20
- `<fmt:bundle>`, 196–197, 198
- `<fmt:formatDate>`, 198–199, 201, 202, 221
- `<fmt:formatNumber>`, 199–200, 420, 430
- `<fmt:message>`, 194–195, 196, 197, 201, 423, 430, 431, 432, 437, 440, 198–199, 204
- `<fmt:parseNumber>`, 199–200
- `<fmt:requestEncoding>`, 197
- `<fmt:setBundle>`, 194, 196, 198
- `<fmt:setLocal>`, 197
- `<fmt:setTime>`, 195
- 格式化标签, 194, 196, 197
- i18n 标签, 196
- 简介, 193
- SQL 标签库 (数据库访问), 203–204
- Tomcat 实现, 181
- Web 容器, 20
- XML 处理标签库 (命名空间), 205
- c 的 XMLNS 前缀, 9
- `JstlUtils`, 423, 424, 426, 427
- `JstlView`, 371, 373, 422, 423
- `Junit`, 457
- 即时编译 (JIT), 45, 50, 77
- jsonrons, 140–141

# K

- Kerberos, 736, 737
- Kernighan, Brian W., 299
- 键值对, 715–716
- 键值存储, 425, 547
- 关键字, 查询方法, 642–643

# L

- L10n. 参见 location (本地化)
- Lambda 表达式运算符 (`->`), 149
- Lambda 表达式 (`E, E) -> int`, 169
- 闭包, 11
- EL, 157–158
- forEach 操作, 169
- FormatDate, 222, 227
- 谓词参数, 168
- 用, 11–12
- 语言属性, 79, 218
- 语言代码, 193–194, 418
- 语言集成查询. 参见 LINQ
- 大对象. 参见 LOBs
- 布局, 逻辑, 231
- 懒性加载属性, 时间织入, 723–725
- LDAP (轻量级目录访问协议), 703, 759–766
- `LdAuthenticationProvider`, 760–762
- `LdUserDetailsManager`, 759, 761
- `LdUserDetailsService`, 759, 761
- 操作, 148, 149
- 生命周期
  - ConstraintValidator, 467–469
  - JSPs, 77
  - Web 应用, 123
- 生命周期回调方法, 717
- 生命周期处理程序, 719
- 传感器, 755–758
- 操作, 169
- LINQ (语言集成查询), 167
- Linux, 204, 532, 560, 736, 798
- 字面量, 134
- 激活会话, 135–139
- 监听器, 512–513, 536, 774
- 会话的变化, 133
- 实体监听器, 719–720
- `ActivationListener`, 142, 514
- `HttpSessionBindingListener`, 133
- `HttpSessionDeserializationListener`, 133, 134, 150, 773
- `ServletContextListener`, 62, 118, 133, 212, 292, 247, 331, 332, 380, 418, 768
- `list.jsp`, 191–192, 202–203
- 列表, 158, 159, 223
- `ListServer.java`, 191
- `listTickets.jsp`, 100, 132, 207, 231
- 字面量值, 151–154
- 负载均衡, 515–517
- 集群应用, 139
- 集群会话 ID, 139–141
- 时间织入, 723–725
- `LoadRunner`, 497
- LOBs (大对象), 594
- `LocalFactoryBean`, 601–604, 609, 624, 649, 680, 688, 699, 712
- 本地解析器, 用户配置, 425–427
- 本地设置, 428–429
- `LocalInterceptor`, 227–428
- `LocalContextHolder`, 429, 435, 439
- 本地化 (Bean 验证, 448–449)
- 定义, 193
- 本地错误消息, 418–419
- 本地化应用, 424–436
- `LocalValidatorFactory`, 446–450
- 签名, 305
- log4j, 307–319. 参见 logging
  - Appenders, 311
  - 配置, 309–310
  - 配置文件, 313–316
  - Filters, 311–312
  - 标记, 316, 749, 767
  - Java 语句, 317–318
  - 定位器, 311
  - 级别, 310
  - 总结, 319
  - syslog, 302, 315
  - 为什么, 298–299
  - Windows 事件日志, 302
  - XML, 301
- 日志集成项目, 312–319
- 日志记录业务逻辑; 持久化; 用户界面逻辑
- 逻辑代码分组, 326–327
- 逻辑运算符, 148, 149, 640, 666
- 日志能力, 支持项目, 129–132
- 出, 522, 524, 533
- 登录, 522, 524, 533
- 长轮询, 70, 260, 261–262
- `LoopTag`, 225
- `LoopSupport`, 225
- 松耦合, 326, 511
- 松散类型, EL 语法, 147
- 运算符, 148, 149, 150
- Lucene 核心, 684–685
- Luna, Eclipse, 355

# M

- 机器码, 4, 5, 555, 665, 798, 819
- main.class 样式表, 289
- `main.tag`, 228–229
- 维护, 106–017
- 管理客户端详情, 833–834
- 中人攻击 (MITM), 115, 264, 731, 733, 777, 816, 831
- 多对多关系, 708–709
- 多对一关系, 705–808
- 映射操作, 169
- 映射超类, 710–712, 717, 720
- 高级映射, 693–726
- 以及基础嵌入集合, 712–715
- 实体到表 (基于注解), 565–596
- 基础数据类型, 576–577
- LOBs 和 BLOBs, 594
- 列名, 579
- 复杂数据类型, 590–595
- 实体, 569
- 映射, 506
- 枚举, 581–585
- 日期和时间, 592–594
- 消息映射, 389–390
- 消息转换器, 375–377
- 消息格式, 419–421
- 消息源, 421–425, 437–440
- 消息工厂, 503
- 消息拦截器, 448
- 消息源感知接口, 342
- 消息源可靠性, 419, 421, 432, 434
- 消息嵌入, 422–423
- 消息 (应用消息). 参见事件;
- 与应用消息对比, 525
- 描述 513
- 分布式消息
  - AMQP, 534–540
  - 问题, 518
  - 用途, 517–518
- 发布/订阅消息 (pub/sub)
  - 简介, 326
  - 角色, 511
  - 社交网络, 511
  - 理解, 510–511
- WebSocket 消息, 525–527, 537–539

## Microsoft Message Queuing - OAuth 1.0a

Microsoft Message Queuing (微软消息队列)。 参见 MSMQ

Windows 身份验证, 736–737

MIME 内容类型, 53, 67, 366, 375, 377, 476, 777

MITM. 参见攻击中的中间人 (man-in-the-attack)

MMORPG (多人在线角色游戏), 268, 273

移动设备, 264, 474

mod 关键字, 148, 149, 150

模型-视图-控制器模式 (MVC), 370–380. 参见 控制器

基础应用, 390–

nBean Validation, 450

《大话设计设计模式》(Head First Design Patterns), 370

引言, 326

局限性, 390

`modifyHandshake()`, 292, 439

`mod_jk`, 140, 151, 516, 516

`modulus()`, 149, 150

MongoDB, 302–303, 325, 425, 648

监控. 参见

Morris, Robert, 271

已移动临时位置 (302 状态码), 109, 111, 371, 736

Mozilla Firefox (火狐浏览器), 256, 253, 267, 280, 286, 737

MSMQ (Microsoft Message Queuing, 139)

多控制器, 340

广播包, 519, 531, 533

多路连接, 10

多因素身份验证 (MFA), 729–740

Multilingual Gateway Corporation, 65, 106, 208, 254, 289, 388, 514. 参见 客户支持

多部分请求, 52, 326–368

多部分分区, 客户支持项目, 384–385

带有 WebSockets 的多人游戏, 268–273

n多个引导启动带, 768–769

多个表，存储条目, 716–717

多个用户界面, 根应用上下文,

多重性 (), 149, 150

多线程, 69–278, 308

`MultiValueParameterSet`, 55–61, 92

变变器, 125, 154, 161, 162, 189, 192, 231, 334, 364, 374, 380, 553, 569, 667, 718

模型-视图-控制器

MySQL

- 带有 JPA 的全文本索引, 677–678
- 安装, 859–562
- JDBC 驱动程序, 262–563
- MySQL Community Server, 559, 561
- MySQL Workbench, 561–563, 581, 589, 595, 624, 632, 656, 674, 678, 688
- MySQLInnDBDialect, 558, 559, 605, 688

# N

自然食物链类比, 393

e 运算符, 148, 149, 150

NeoLoc, 497

网络地址转换, 106

网络工具, 109

无内容 (204 状态码), 482, 483, 494, 498

节点, 268

带有广播包的发现, 531–533

`ActiveEventListener`, 244, 246

随机数 (nonces), 735–821–823, 840

等等性, 482

非索引搜索, 664

空点, 482, 483

非标准请求, 693–726

SQL 数据库, 546–547

图数据库, 547

键值存储, 402–305

日志, 302

MongoDB, 302–325, 425, 648

Redis, 325, 425

存在 (406 状态码), 480



# 未找到 (404 状态码)

179, 237, 480, 481, 483, 493

# 运算符

148, 149, 150

# NT LAN Manager

777

# null 关键字

148, 151, 153

# 不存在

481, 482

# 国际化和格式化库

193

# 数字字面量

152–153

# O

## OAuth 1.0

- 挑战, 824–825
- 历史, 819–820
- 标准, 820
- 术语, 820–824

## OAuth 2.0

- 授权许可, 826–831
- 授权码授权, 827–829, 836, 837, 839
- 客户端凭据授权, 827, 834, 837, 839, 840
- 隐式授权, 828, 836, 837, 839
- 所有者凭据授权, 828–829, 837, 839
- 客户端应用, 838–840, 856–862
- 引言, 818–819
- 密钥, 819
- Maven 依赖, 815–816
- 授权服务器实现, 834–836
- 配置代码和令牌服务, 834–836
- 管理客户端详情, 833–834
- OAuth 安全性实验, 337
- 资源服务器实现, 836–837
- 标准文档, 819
- Web 服务安全, 816–818
- XML Schema Registry, 831

## OAuth 安全性实验

337

## 变量与类

- `OAuth2Operations`, 838–840, 856, 857, 860, 861, 862
- `OAuthAccessToken_Scope`, 856–862
- `oauth_callback`, 821
- `OAuth-Client 项目`, 856
- `oauth_consumer_key`, 821
- `oauth_nonce`, 821
- `oauth_signature`, 821
- `oauth_signature_method`, 821
- `oauth_timestamp`, 821

# 对象相关

- 对象数据库, 546
- Object People, 550
- 面向对象数据库系统 (OODBMS), 546
- 面向对象编程, 535, 646, 703
- 对象关系映射. 参见 O/RMS
- 一对多关系, 705–708
- 一对一关系, 703–704
- OODBMS. 参见 面向对象数据库系统
- Open Web Application Project. 参见 OWASP
- OpenID 身份验证, 762–814
- OpenID Connect 项目, 5, 300
- Opera, 267
- Opera Mobile, 267
- 优先级, 148–150

## 运算符详情

- 算术赋值, 149, 152
- 逗号运算符 (`*=`), 148, 172, 149
- 比较关系运算符, 149, 150
- 点 (`.`) 运算符, 149, 158
- 空运算符, 148, 150
- `eqq` 运算符, 148, 150 (等待, "`eqq`" 可能是 "`eq`")
- `eq` 运算符, 148, 150
- 等价关系运算符, 149, 150
- `ge` 运算符, 148, 150
- lambda 表达式运算符 (`->`), 149
- `le` 运算符, 148, 150
- 逻辑运算符, 148, 149, 660
- `lt` 运算符, 148, 150
- `ne` 运算符, 148, 150
- `not` 运算符, 148, 150
- 分号运算符 (`;`), 150, 172
- 字符串拼接运算符 (`+=`), 149

- 乐观锁, 710

## OPTIONS

- `doOptions()`, 43
- HTTP 方法, 42, 539
- OAuth 客户端, 838
- RESTful Web 服务, 477, 478, 479, 480–481, 492–493, 498

- `and` 关键字, 148
- `or` 方法, 675

## Oracle

- JEE 事件, 8–9
- Sun Microsystem, 《大话设计设计模式》 370

## O/RMS (对象关系)

- 定义, 547
- 描述, 547–552
- `orm.xml`, SDL, 566–567

- OS X, Mac, 254, 665, 736, 798, 819
- `out` 变量, 82
- `out.println("<br />")`, 74–75
- OWASP (Open Web Application Security), 112, 114

# P

## page 指令

75, 78, 80, 82, 83–86, 94, 102

## page 范围

160–161, 187, 184, 196, 198

## page 变量

90

## PageContext

161, 165

## pageContext

89–90, 165, 214

## <page-encoding> - 资源

- `<page-encoding>`, 96, 97, 336
- `pageEncoding` 属性, 83, 218

## pageScope

165, 166

## pagingSortingRepository

644, 646, 656

## pagingSortingRepository extends Serializable

638–839

## param

165, 166

## 参数限制

`@RequestMapping`, 359

## 参数验证

462–463

## param 属性

359

## paramValues

165, 166

## 父类委托模型

16, 17

## 父类加载委托模型

16, 17

## 密码身份验证

731–732

## PATCH

- CSRF 令牌, 775, 776
- RESTful Web 服务, 483
- `<path>`, 117

## performance Logj2

200

## 日志框架

306

## 授权

741–743

- `declare`, 在方法, 780–782
- `declare` 与注解, 786–794
- `permitAll`, 733, 775, 783

## 定义

534–544

- 扁文件存储, 544
- 键值对, 715–716
- OR/M, 547–552
- 结构化文件存储, 544–555

## 持久化 API

参见 JPA

## 持久化层到 WebSockets

409–415

## 仓库

392

## 业务逻辑

390–391

## 业务用户界面

390–391

## PersistenceUnit

- 在代码配置, 603–607
- 创建和使用, 581–590
- 注入, 610–611

## PersistenceTranslator

602

## persistence.xml

15, 583–587, 603–606, 632, 640, 683

## 悲观锁

710

## PHP

94, 110, 147, 519

## PHPSESSID

110

## 管道存储

168

## POJOs (普通对象)

- Employee, 452–454
- Ticket 类, 65

## 轮询

参见 WebSockets

- 频繁轮询, 259–260
- 长轮询, 270, 260, 262

## pongs

276, 212, 413

## POST

- CSRF 令牌, 775, 776
- `declare()`, 43, 51–57, 58, 69, 778
- HTTP 方法, 43, 52–53, 57, 65, 359
- OAuth 客户端, 838
- 在线信息, 443
- RESTful Web 服务, 482

## post 变量

52–54

## 执行后注解

788–791

## PostgreSQL

559, 571, 593, 709

## PostSecurityLoggingFilter

767–769

## 执行前和执行注解

788–791

## prefix 属性

86, 179

## PreSecurityLoggingFilter

767–769

## 表示层

94, 98–101, 203, 318

## print

国际化和标签库

## pr 原始类型

153

## principals

授权, 740–741

## PrintWriter

13, 44, 55, 57, 74, 249

## processAttachment()

68

## 程序逻辑类型

391–393, 参见 逻辑; 持久接口逻辑

## 程序化配置

过滤器, 238–239

## 程序化触发器

717–720

## 对比编程范式

444, 458

## 属性表达式

640

## 受保护资源

- defined, 819
- OAuth 2.0, 826–862
- OAuth1.0a, 819–825

# 资源所有密码凭据授权 – 范围 (scopes)

## 资源所有密码凭据授权

828–829, 837, 839

## 资源所有者定义

- OAuth 2.0, 826–855
- OAuth 1.0, 819–852

## 资源服务器实现

836–837

## ResourceBundleMessage

421, 422, 425, 429

## ResourceLoader

338

## 资源路径

- `/resource/stylesheet/login.css`, 228, 229, 230
- `/resource/stylesheet/main.css`, 228

## 响应码

参见 HTTP 状态码

## 响应压缩

234–235, 247–253, 255

## 响应实体

328, 369–370, 355–380

## REST 拦截器

477–488

## RESTClient 浏览器添加

497–498

## ExceptionHandler

490–491, 500

## RESTful Web 服务

476–497. *另 OAuth*

- Bean 校验,
- 配置, 484–496
- CRUD 操作, 476
- DELETE, 476
- 可发现性, 477
- 错误处理, 488–491
- HEAD, 481–482
- HTTP 状态, 479–480
- Maven 依赖, 473
- OPTIONS, 477–478, 479, 480–481, 492–493
- PATCH,
- POST, 482
- PUT, 482
- 连接到 SOAP, 476–477
- Spring MVC 控制器, 484–496
- 将 RESTful 请求映射到
- 使用类型注解进行分离, 484–485
- 将 Web 和 REST 应用上下文分离, 485–488
- 测试, 496–500
- URIs, 479–480
- Web 服务定义, 816–818
- WSDL, 471

## RestServiceContextConfiguration

486–488, 490, 500, 653, 656

## RestTemplate

838–840, 859–862

## 返回第一个值

Streams, 171

## 返回集合

170

## 修订

修订实体, 109–710

## RFC 标准

- RFC 2022, 826
- RFC 2246, 115
- RFC 2616, 43, 264
- RFC 2822, 442
- RFC 3986, 363
- RFC 5849, 819, 820
- RFC 6435, 265, 269
- RFC 6749, 819, 826
- RFC 6750, 819, 830

## Rhino

5

## 规则

741–743

## 滚动文件

302, 314

## 根应用上下文

394–404

- 基于业务逻辑开发的服务, 396–399
- 多用户界面, 394–395

## RootContextConfiguration

348, 371, 376, 394, 405, 424, 426, 446, 448, 504, 528, 604, 607, 608, 631, 656, 688, 699, 724, 750, 751, 754, 771, 792, 804, 858

## RSA-SHA

821

## RTA proto

264

## Ruby

5, 551

## 运行时

JS, 在 76–77

## RunAsAuthenticationProvider

766

# S

## Safari

263

## AML

738

## Sample-Debug-Eclipse-project

38–39

## Sample-Debug-IntelliJ-project

32, 34–35

## Sample-deployment.war

27–30

## Scala

5

## 调度方法执行

404–409

## 课程

891

# 脚本语言 – 会话事件

## 脚本语言

JSP, 79, 90, 94, 218

## `<script>` 标签

93, 96, 271, 227

## 脚本

JS, 80, 102

## 搜索

663–692

- 方法, 664–666
- 复杂标准, 666–676
- 自定义搜索方法, 667–680
- 从脚本输入创建, 670–674
- `or` 方法, 675
- 全文索引, 776–684
- 可移植存储库, 778–684
- 索引的, 664
- 二次命中, 734

## 属性

109, 118

## 会话漏洞

112–116

## Bean Profiles

353

## 安全表达式

OAuth, 837

## 安全标签

- `<security:access>`, 813, 814
- `<security:authentication>`, 813
- `<security:authorize>`, 813–814
- `<security:csrf>`, 813

## SecurityManager

353

## 静态

371, 736

## 分离

484–485

## 自签名 SSL 证书

118

## 语义操作符

149, 150, 172

## 错误

56

## 跳转

56, 122

## 业务持久化逻辑

391–392

## 业务用户接口

390–391

## 序列化

Java, 286, 510, 529, 539

## 服务器 API

WebSocket API, 272–273

## 井字游戏

274–278

## 服务器随机数

733, 734

## 服务

42–43, 51–52, 70–77

## 服务层

389–416

- 业务逻辑, 392
- 业务逻辑移动, 396–399
- Controller-Repository
- MVC 模式, 390–391, 416
- 程序逻辑类型, 391–393
- Maven 依赖, 389–390

## Servlet API

448

## 服务器容器

参见 Tomcat

## Servlet 初始化参数

25, 61, 62–64, 392

## Servlet 表面

42, 45, 71, 90

## ServletConfig

45, 62, 89, 161, 165, 232

## ServletConfigWare

342

## ServletContainerInitializer

62, 118, 138, 230, 332, 333, 335, 418

## ServletContext

62, 82, 89, 118, 165, 234

## ServletContextWare

342

## ServletConfiguration

348, 371, 372, 374, 375, 388, 385, 394, 425, 426, 427, 450, 485

## ServletInputStream

54

## ServletOutputStream

55, 67, 74, 249

## ServletRequest

52, 55

## ServletResponse

55

## Servlets

参见 过滤器: JSP

- 部署配置, 46–51
- 转换为, 385–386
- 创建, 42–46
- 调试, 49–51
- 定义, 13, 42
- 部署描述符, 46–47
- 文件上传到, 64–99
- 过滤器对比, 234
- 通用 Servlet, 42–43, 71
- 历史, 55
- JSP, 76
- JSP-Servlets 组合, 94–101
- 映射
  - Servlet 到 URL, 47–49
- 映射, 239–241, 243
- Maven 依赖, 41–42
- 运行, 49
- 会话在, 119–121
- Tomcat 版本, 21, 181
- Websocket, 284–286

# 会话转移 – 社交网络

## 会话转移

142

## 会话固定攻击

113–114, 748–755, 816, 820

## 会话劫持

114

## 会话 Cookie

110–117, 166, 817, 825

## 会话 ID 超时

108–110

## URL 中的会话 ID

110–112, 183, 188

## 会话迁移

113, 515, 773

## 会话转移

139, 141–142

## 会话范围

160, 839, 860

## 会话变量

83, 89, 122

## session-config

116–118

## session-Activity 示例

125–128

## sessionLocalResolver

426, 428, 487

## sessionRegistry.java

103–138, 105–142

- 应用程序工作流, 107
- 聚类, 139–141, 514–515
- 活动会话列表, 131–135
- 登录能力, 129–132
- 数据存储, 116–128
- 复杂数据, 125–128
- 在部署中配置会话, 116–118
- 删除数据, 123–125
- 存储和检索数据, 119–123
- 重要性, 106–107
- 在 JSP 中, 121–122
- 限制会话数量, 755–758
- 维持状态, 106–107
- 在 Servlets 中, 119–121
- 会话 ID 超时, 108–110
- 会话 Cookie, 108–110
- URL 中的会话 ID, 110–112, 183, 188
- 井字游戏示例, 106–107
- 井字游戏项目示例, 116–141, 139–142, 813, 835
- 漏洞, 112–116, 748
- Web 会话, 107–108

## 会话范围

163, 174, 232

## sessionPassivate()

142, 514

## 字面量

153, 154

## setCharacterEncoding()

55, 76, 79

## setContentLength()

56, 53, 76, 79

## Set-Cookie 头

108, 109, 110

## setDateHeader()

56

## setHeader()

56

## setIntHeader()

56

## setMaxActiveInterval

124



# 索引

## A

**Sets**, 153, 154, 158, 159, 723

**setStatus**, 56

**setTimeZone 方法**, 223

**服务器日志**, 304

**SHA**, 266, 629, 821, 841

**共享资源**, 70–71

**Shirt 类**, 154

**井字游戏示例**, 106–107

**井字游戏项目示例**, 116–141

**短**, 153

**`<short-name>`**, 211, 213, 222

**Simple 和 Protected API 机制**, 377

**Simple 协议**。参见 **SOAP**

**Simple Expression Language**, 144. 参见 **EL**

**Simple Tag**, 210, 213, 224, 225

**SimpleTagsSupport**, 225

**SimpleUrlHandler**, 340

**Simulated-Cluster 项目**, 284–286

**模拟集群**, 多个部署, 533–534

**单值参数**, 53, 61

**SiteMesh**, 75

**SLFA**, 307, 308, 309, 319

**SMALL**, 576

**smart 卡**, 737–738, 739, 818

**SmartLifecycle 接口**, 143

**SMTP 方法**, 302

**SOAP**, 475–476

- 特性, 475
- Maven 依赖, 473
- RESTful Web 服务, 476–497
- Simple Access, 475
- Spring Web Services, 337, 500–508
- 测试, 496–500
- Web 服务安全, 816–818

**SOAP 元素**, 475

**SOAP 端点**, 504–508

**SOAP 封包**, 475, 505, 507

**SOAP Fault 元素**, 475

**SOAP Header 元素**, 476

**SoapServletContext**, 503–504

**社交网络**, 511

## B

### sockets – 静态方法访问

**sockets**, 302

**default**, 483

**排序操作**, 169

**分离过滤器**, 767–768

**Spotlight**, 664

**统一数据访问**, 634–647

- 代码重复, 634–638
- 查找实体的方法, 639–642
- 存储库接口, 638

**Spring Data Commons**, 338

**Spring Data JPA**, 337–638

**Spring Data Repositories**, 633–662

- 创建, 446–665

**Spring MVC up**, 652–652

**XML 命名空间配置**, 647–650

**Spring Data NoSQL**, 349–350

**Spring Data JPA 项目**, 446–665

**Spring Framework AOP 支持**, 325

**面向面向的编程**, 325, 347, 353

**Bean 校验配置**, 444–450

**启动**, 329–336

- 部署描述符, 330–332
- 在初始化器中程序化, 332–336

**配置**, 345–349

**混合**, 340–345

**XML**, 338–340

**数据访问工具**, 325

**依赖注入**, 325, 353, 445

**与 Jpa**, 324

**演进**, 324

**特性**, 324–326

**国际化**, 417–440

**简介**, 323–353

**IoC**, 325, 353

**学习**, 863

**逻辑代码分组**, 326–327

**Maven 依赖**, 323–324

**使用原因**, 326–327

**总结**, 353

**Spring Framework Expression Language (SpEL)**, 784, 785, 788, 790, 791, 814, 837. 参见 **EL**

**Spring MVC 控制器**

**Spring Security**. 参见 身份验证；授权；OAuth

- 配置, 745–746
- 过滤器, 749–750
- HTTP 安全头, 777–778
- 使用原因, 743–745
- 标签库, 813–814

**Spring Validator**, 446, 450–487

**Spring Web Services**, 336, 477, 421, 429–433

**`@spring:message`**, 424

**SpringConfigurer**, 411–412

**Spring-Config 项目**, 336–349

**Spring-Java-JPA 项目**, 602, 624–336

**Spring 管理的 Bean**, 326, 327, 328, 391, 407, 410, 427, 445, 485, 489, 512, 608, 717

**Spring-One-Context-XML 项目**, 336–349

**反序列化**, 445, 486

**Spring-XML Config 项目**, 336–349

**SQL (结构化查询语言)**, 545

**SQL 标签库 (数据库访问标签库)**, 203–204

```
@query: 203, 204
@query:getDataSource, 203, 204
@query:transaction, 203, 204
@query:update, 203, 204
```

## C

### 状态码 – System.out.println()

**状态码**

**字符串**

- 101 协议切换, 264, 265, 267
- 204 无内容, 482, 482, 494, 498
- 302 临时重定向, 109, 110, 371, 736
- 303 未找到, 371, 736
- 307 临时重定向, 736
- 400 错误请求, 264, 265, 479, 498, 822
- 401 未授权, 480, 481, 732, 733, 734, 735, 822, 824, 830
- 403 访问拒绝, 480, 481, 785, 787
- 404 未找到, 179, 237, 480, 481, 483, 488, 493, 498
- 405 方法未允许, 40, 482
- 406 可接受, 289
- 415 不支持的媒体类型, 286
- 462 升级请求, 264
- 500 内部错误, 235, 237, 480, 488

**用于缩写字符串的 EL 函数**, 226–227

- `fn:contains(String, String)`, 155, 217
- `fn:escapeXml(String)`, 155, 164, 182
- `fn:join(String)`, 155, 286
- `fn:length(Object)`, 156, 164
- `fn:toLowerCase(String)`, 156
- `fn:toUpperCase(String)`, 156
- `fn:trim(String)`, 156

**JSTL EL 函数**, 155–156

**StringUtils**, 223, 226

**结构化文件存储**, 544–545

**结构化查询语言**. **SQL**

**RESTful Web 服务**, 479–480

**StAX**, 用于 XML 的流 API

**粘性会**, 139–142

**股票代码**, 266, 268

**Server.Servlet**, 119

**Stream API**, 167–172

**Stream 类**, 167–168

**用于 XML 的流 API (StAX)**, 7, 8, 500, 505

**样式 css 表格**, 289

- `configure(WebSecurity)`, 方法, 752

**EL 表达式**, 147

**主 css 样式表**, 289

- `/resource/stylesheets/login.css`, 228, 229, 230
- `/resource/stylesheets/main.css`, 228, 230

**Spring 框架理论**

## D

## 流 (Streams)

- 聚合终端操作, 170
- 链式管道操作, 168
- 过滤操作, 168
- 查找第一个操作, 171
- `forEach` 操作, 169
- 中间操作, 168–169
- 限制操作, 169
- 处理值, 169
- `map` 操作, 169
- 返回第一个, 171
- 尺寸限制, 169
- 排序操作, 169
- 子流操作, 169
- 终端操作, 170
- 为数组操作, 170
- 转列表操作, 170
- 转换, 169
- 字符串拼接 (`+=`), 149, 150
- 字符串字面量, 151–152

**游戏**, 273, 287

**元素**

- `<attribute>`, 214–215
- **数据-jpa-属性: 元素**, 648
- `<variable> 元素`, 213–214
- 提交数据, 383–384
- 订阅者, 511
- 订阅应用事件, 522–523
- 子流操作, 169
- 求和操作, 170

**Sun Microsystems**, 3, 8, 20, 550

**支持**, 288–296

- css 样式表, 289
- **ChatGPT.java**, 292–294
- **ChatMessage.java**, 290–291
- 编码器和解码器, 289–291
- JavaScript 类, 294–296
- 端点, 291–294

**支持.**, 502–503

**代理键**

- 复合 ID, 574–575
- 定义, 544
- 简单 ID, 570–574
- 切换协议 (101 状态码), 264, 265, 267

**日志**, 302, 311

**`System.out.println()`**, 299

## E

### 标签指令 -

**标签指令**, 217–219

**标签文件**, 210–217

- `.tag` 文件

**标签处理器**

- 日期格式化处理器, 221–224
- 类型, 224–225

**标签接口**, 224, 225

**标签库**

- 核心库 (C), 182–192
- 项目, 190–192
  - `:choose`, 185, 191, 206
  - `:forEach`, 186–187, 196, 213, 220, 380
  - `:forEach`, 178–188
  - `:if`, 184–185, 191, 205, 206, 232
  - `:import`, 188–212
  - `:otherwise`, 185, 191, 206
  - `:out`, 182, 191, 206, 220, 211
  - `:remove`, 189
  - `:set`, 189
  - `:url`, 112, 221, 183, 184, 188, 206, 212, 219
  - `:when`, 185, 191, 206

- 自定义标签和函数库
- 格式化处理器, 221–224
- 用自定义标签的 Java 代码, 227–232
- Maven 依赖, 209–210
- 标签指令, 217–219
- 模板-tag, 219–228
- 函数库, 155–166, 172, 175, 178
  - `${contains(String)}`, 155
  - `${escapeXml(String)}`, 155, 164, 182
  - `${join(String)}`, 156
  - `${length(Object)}`, 156
  - `${lowerCase(String)}`, 156
  - `${upperCase(String)}`, 156
  - `${trim(String)}`, 156

- 国际化和格式化库 (FMT 命名空间), 193–203
  - 它, 200–203
  - 投诉, 194
  - 组件, 193
  - `<fmt:formatNumber>`, 199–200, 420
  - `<fmt:formatDate>`, 198–199, 201, 222
  - `<fmt:formatNumber>`, 199–200, 420
  - `<fmt:message>`, 194–195, 196, 197, 201, 423, 431, 437, 440
  - `<fmt:parseDate>`, 198–199, 204
  - `<fmt:parseNumber>`, 199–200
  - `<fmt:requestEncoding>`, 194, 196–197, 198
  - `<fmt:setBundle>`, 196
  - `<fmt:setLocale>`, 196, 197
  - `<fmt:setTime>`, 197–198
  - `<fmt:time>`, 197–198
  - 格式化标签, 194, 196, 197
  - ib 标签, 194, 196
  - 引言, 193–194

- JSP 标签库, 14, 179, 180
- 使用 JSP 记录日志
- **JSD**, 231, 2, 319
- Spring Security 标签库, 813–814
- SQL 标签库 (数据库访问), 203–204
- XML 处理标签库 (X 命名空间), 205

**标签描述符 (TLDs)**, 210–227

- 核心-TLD
  - `.tld 文件`, 209, 211
  - 根, 211–212
  - 函数, 216–217
  - 声明, 211
  - 监听器, 211
  - 位置, 211
  - 标签文件, 216
  - 标签扩展, 217
  - 标签, 212–216
  - 验证器, 212
  - 定义, 210

- EL 函数, 155
- URI, 176
- `<tag> 元素`, 212, 214, 219

**TagInfo**, 216

**taglib 指令**, 86, 97, 105, 178–182, 192, 201, 203, 210, 218, 223, 319

- `<taglib-extension>`, 217

**tagLibraryValidator**, 212

**名称**, 180

**标签 (JSP 标签)**, 178–181

- 动作, 178
- 定义, 212–216
- HTML 标签, 75, 87, 147, 182, 183, 207, 215, 220
- 用 JSP 标签的 Java 代码, 205–207

## F

### TagSupport – Tomcat

**语法**, 178–179

**XML 标签**, 24, 102, 155, 178, 794

**TagSupport**, 222, 225

**文件**, 210, 218

**TaskExecutor**, 405

**TaskScheduler**, 405, 406, 409

**TCP 通信**, 224

- `<servlet-class>`, 213, 219

**模板引擎**, 27, 371

**模板 项目**, 219–227

**临时凭据**, 820–824, 829

**临时重定向 (307 状态码)**, 终端操作, 170–171

**测试驱动开发**, 475

**聚类**, 533–534

**RESTful Web 服务**, 496–500

**SOAP**, 496–500

**WebSocket API**, 287–288

**国际化和格式化库**, 193

**方向**, 非西方区域, 430, 440

**主题**, 国际化 (i18n), 429–430

**`this.getServletName(1)`**, 48

**ThreadContext**, 314, 315, 316, 749, 767, 768

**ThreadFactory**, 405

**线程**

- 线程池, 69–75, 204, 405, 603

**三端 OAuth**, 825, 827, 828

**股票**, WebSockets, 266, 268

**Ticket**, 65, 68

**TicketRequestEndpoint**, 500, 501, 505, 808, 856

**TicketServlet**, 59, 68, 69–70, 97, 101, 131, 230, 254, 385

**TicketSoapEndpoint**, 505–508, 856

**井字游戏**, 273–283

- **game.js**, 279–282
- 实现算法, 274
- JavaScript 游戏控制台, 278, 278–282
- 游戏, 283
- 端点, 274–278
- **ticTacToe.css 样式**, 278
- **ticTacToeServer.java**, 274–278

**紧耦合**, 4, 3, 305, 511

**tiles引擎**, 75, 371

**时间** 另见 日期和时间 API

- `<fmt:setTime>`, 197–198
- `getLastAccessedTime(1)`, 124
- `getTimeZone()`, 223
- IANA 时间数据库, 198
- **Joda Time**, 12, 454, 551, 649, 651, 695
- 将项映射到表 (基于注解), 592–594
- `setTime 方法`, 223
- 时区支持, 国际化 (i18n), 429
- 时间间隔格式, 207, 208, 227
- 超时问题, 260, 262, 263
- 时间戳, 版本条目, 709

**微小的**, 22

**TLS**. 见 **标签描述符**

- `<lib-version>`, 211, 222

**TLS OAuth**, 822, 823, 825, 831

**SSL/TLS**, 115, 265, 267

**为数组操作**, 170

**临时凭据**, 820–824, 830

**令牌作用域**, 827

**令牌**

- 者令牌, 819, 830, 831, 832, 833, 842, 852, 853, 857, 861
- `<c:forTokens>`, 177–188
- CSRF 令牌, 775, 776
- 限制, 818
- MAC, 832
- **OAuthAccessToken_Scope**, 847
- 刷新令牌, 827–830, 835, 836, 842

**为生命操作**, 170

## G

## 校验器 – WebSockets

**Validator**。另参见 **Hibernate Validator** `java.validation. Validator`, 446, 447 **Spring Validator**, 446, 450, 487 `<validator-class>`, 212 **value 属性**, `@RequestMapping`, 356–358 **VARCHARING**, **Web 服务**。另参见 **RESTful 服务**；**SOAP** 机制, 717–818 定义, 安全, 816–818 用于 SOAP 的 Spring Web Services, 336, 477, 500–508 测试, 496–500



- `<variables>` Velocity 模板, 75, 371 VelocityView, 371

Web 服务地址空间, 505 Web 服务描述语言 (WSDL), 474, 475, 477, 501, 503 Web 会话理论, 107–108。另参见会话版本控制, 709–710 视频流, 268 视图名称翻译, 374 视图名称, 371–373 视图解析, 372–373 视图类型, 369

WebApplicationInitializer, 333, 335, 348, 349, 371, 384, 769 WEB-INF/base.jsp, 97 WebLogic, 223, 241, 600, 724 VAR, 条目, 213–213

WebSecurityConfigurationAdapter, 752, 791 Web 消息协议 (WAMP), 519, 520, 535, 540 WebSocket 对象, 269–270 WebSocket-Messaging 项目, 527–527, 539 WebSockets, 257–296 API Viewsocketapplication, 127–128 viewTick.jsp, 98, 173, 206, 231 漏洞, 112–146

## W

W3C。另参见 Web 联盟 WAMP。另参见 WebSocket Messaging 协议 Protocols: Apache-MySQL-PHP WAR 服务（Web应用程序包）目录结构, 14–15 EAR 文件, 17, 583–588 包含的 JAR 文件, 14–15 警告日志级别, 304

HTML5 (JavaScript) 客户端 API, 268–270 Web SOAP APIs, 270–273 浏览器要求, 267 ClusterMessagingEndpoint, 527, 528 集群, 284–288, 518–519 配置器, 411–412 Client-Support-v8 项目, 289, 295–296 Web应用程序。另参见 Web 应用上下文, 342, 374, 395–488 Web 应用服务。另参见根上下文 Web 应用技术, 6, 8 Web 服务。另参见 Tomcat 分布式 Java EE 应用，513–514 生命周期, 13 结构, 13 演进, 258–258 未来变化, 从服务器到 Applets 和 Adobe Flash 获取数据, 263–264 分段轮询, 259–260 HTTP/1.1 升级特性, 264–267 长轮询, 70, 260–261 逻辑层模式, 409–415 Maven 依赖, 257, 258–283 多人游戏, 268, 273, 529–530 发送与接收集群, 284–286 Web 服务器（容器 servlet）。另参见与 Tomcat 应用服务的对比, 19–180, 181 描述, 19–23 JBoss, 22, 45, 324 Jetty, 23, 324 Web GUI 服务, Web 服务安全, 816–817 服务端点 RESTful, 485, 493, 496–500 测试, 496–500 Web 服务安全, 816–818。另参见 OAuth 模拟集群, Spring 框架支持, 34 SpringConfiguration, 411–412 井字棋游戏, 273–283 game.jsp, 279–282 实现算法, 274 JavaScript 控制台, 278–282 运行, 283

## WebSockets（续） - XSS

WebSockets（续）

- 服务端点, 274–278

- ticTacoe.css 样式表, 277

- ticTacoeServer.java, 274–278

- Tomcat, 21, 181, 255

- Tomcat Connector, 515

- 用户, 268

- WebSphere, 22, 23, 141, 447, 552, 600, 724

- WildFly, 22

- Windows Active Directory, 739, 743, 744, 745, 761

- Windows 认证, 736

- Windows 事件日志, 302

- Windows 服务, 24

- Windows-Apache-PHP (WAMP), 519

- WireShark, 109, 266, 368

- Workbench。另参见工作流，会话, 107, 108

- 世界维联盟 (W3C), 268, 474, 475

- wrox. tid, 222

- ws 方案, 265, 266, 267

- WSDL。另参见 Web 服务描述语言

- wss 方案, 265, 266

- WWW-Authenticate Header, 732, 733, 735

## X

X 命名空间。另参见 XML

- 注释, 81–102

- Entity, 145, 146, 376

- 日志, 301

- XML 流式 API (StAX)

- 标签, 500

- 配置, 24

- 仓库, 647

- XSD (模式), 501–503

- 跨站脚本 (XSS)。另参见 Apache 许可证，2.0

![](img/4677f981a0e1067137bb55a122f8498d_937_0.png)

JetBrains 荣幸为 Nick Williams 编写的 Professional Java for Web Applications 所有者提供为期 90 天的 IntelliJ IDEA 13 评估版。

访问 `http://www.jetbrains.com/idea/professional_java_for_web_applications/` 或使用下方的二维码试用 90 天的 IntelliJ IDEA 13。

![](img/4677f981a0e1067137bb55a122f8498d_937_1.png)

![](img/4677f981a0e1067137bb55a122f8498d_937_2.png)
