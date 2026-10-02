
# JPA 2.2 入门指南：Java Persistence API

Thorben Janssen 序言

作者在文中引用的任何源代码读者均可在 `https://github.com/agoncal/agoncal-fascicle-jpa/tree/2.2` 获取。该源代码使用 MIT 许可证，因此可供复制和分发。[1]

- `www.antoniogoncalves.org`
- `www.antoniogoncalves.org/category/books`

> *献给我可爱的女儿们 Eloise 和 Ligia，她们是生命带给我最好的礼物。*

## 序言

许多 Java 应用都使用对象关系映射（ORM）框架（如 Hibernate 或 EclipseLink）来从关系型数据库中读取数据或向其写入数据。作为本专题的读者，你可能已经知道这两个框架都实现了 Java 持久化 API（JPA）规范，并且流行的 Spring Data JPA 项目将它们集成到了 Spring 生态系统中。但如果你从未听过 JPA 规范，也不要担心。如果是这样，我想祝贺你决定学习它。

JPA 是 Java 世界最受欢迎的规范之一。它定义了一种易于使用的方法，将数据库记录映射到 Java 对象，并根据对 Java 对象所做的更改更新数据库记录。它还规定了一种查询语言，你可以用它根据你的 Java 类定义数据库查询。如果你了解 JPA 的基本概念，所有这些强大的功能都相对易于使用。这就是为什么 Hibernate 和其他 JPA 实现变得如此流行，并被应用于大多数企业 Java 应用中。

因此，显而易见的是，作为一个专业的 Java 开发者或渴望成为开发者的人员，你应该对 JPA 的通用概念和能力有深入的理解。

当 Antonio 邀请我写这篇序言时，我非常乐意答应。我仍然记得在 2000 年代中期作为 Java 开发者职业生涯的早期，就读过他的博客文章。这使得写这篇序言变得与不同。他用易懂的方式解释复杂功能的能力令我惊讶，这让我成为他作品的长期读者和关注者。

显然，我不是唯一喜欢他的教学和写作风格的人。2007 年，他编写并出版了第一本关于 Java EE 5 的书。那仅仅是一个开始。在接后的几年里，他又写了 3 本书，并录制了 7 门视频课程向 Java 开发者教授各种 Java EE 规范，如 JPA 或 Bean Validation。他还担任各种 Java EE 规范的专家组成员，并共同创立了 Devoxx France 和 Voxx Days 微服务会议。Antonio 显然是 Java EE 社区中一位多产的成员，这只是他受欢迎的原因之一。

*(注：原文后续段落存在重复，翻译已按逻辑保持一致)*

- 1 Devoxx France `https://devoxx.fr`
- 2 Amazon `https://www.amazon.com/author/agoncal`
- 3 Les Cast Codeurs `https://lescastcodeurs.com`
- 4 Java Champions `https://community.oracle.com/community/groundbreakers/java/java-champions`

## 致谢

在你手中的，这本技术小册源于我写作、学习和分享的历程。在写作时，你需要过量的好奇心、一丝自律的洞察力、一分专注，以及极大程度的疯狂。当然，你还需要被那些能以任何可能为你提供帮助的人包围（这样你才不会完全疯狂）。这里是感谢他们的地方。

首先，我真的想感谢我的校对团队。在写作过程中，我不断与 Thorben、Youness、Aurelie 和 Aymeric 保持联系，他们审阅了这本书并向我提供了宝贵的建议。我必须说，与如此博学的开发者一起合作是一次真正的享受。

能邀请 Thorben Janssen 为本书撰写序言是我的极大荣幸。Thorben 是一位独立的顾问和培训师，专门负责解决使用 JPA 和 Hibernate 的 Java 持久化问题。他也是亚马逊畅销书《Hibernate Tips - More than 70 solutions to common Hibernate problems》的作者。Thorben 从 Java 和 Java EE 已有近 20 年，是 CDI 2.0 专家组（JSR 365）的成员。他在博客上编写关于 JPA、Hibernate 以及其他持久化相关的话题。[1]

Youness Teimouri 是一位高级 Java 开发人员，拥有十余年的 Java 开发经验。他利用 Java 技术栈帮助了电信、移动银行、ERP 和现场服务管理系统等多个行业的众多公司成长。他合著并贡献了一些关于云计算的论文，并为我之前的几本书做出了贡献。Youness 对 Java 在不同行业中的无限可能深着迷，并喜欢指导初级开发者，激励他们提升自己的 Java 技能树。你可以在 `http://www.youness-teimouri.com` 找到更多关于他的信息。他住在加拿大。[2]

Aurélie Vache 是法国图卢斯大陆智能交通系统的云开发人员（兼 DevOps 工程师）。[3] 她担任开发者已 10 多年。曾担任 Java/Java EE 开发人员，后是 Web、全栈和首席开发人员，现在是云开发人员，负责连接和自动驾驶车辆项目的 DevOps。Go、Docker、Kubernetes、Istio、Jenkins、Terraform……都是她日常生活的一部分。她像一把瑞士军刀。作为 Duchess France（一个促进女性开发者和 IT 女性的协会）的领导者，她深度参与了他们的教练计划 #AdoptADuche[4]，帮助初级开发者和职业转型人员。她还是 DevFest Toulouse 的组织者之一、图卢斯数据科学（TDS）核心团队成员，以及 Simplon 和 Elles Bougent 的导师。她喜欢写技术文章。

Aymeric 是一位来自法国巴黎的高级软件工程师。他的主要专业方向是后端架构和开发，但在空闲时间也好奇探索机器学习或家居自动化等广泛的计算机话题。他之前的经历非常丰富，从早期初创公司到微软等公司。他现在 PayPay PayPay担任性能工程师，关注可扩展性、可用性和语言理论。他参加 Node.js、JS、TS、Golang 和 Rust 的巴黎聚会；他还是 Devoxx France 大会的志愿者；你可能会在那里遇到他！

感谢我的校对员 Gary Branigan，他为本小册增添了莎士比亚式的色彩。

将 JPA 与 CDI 和 JTA 集成需要一些工作。我想感谢 Gunnar Morling 帮助集成所有这些技术，以便它们易于测试。

如果没有 Java 社区的帮助（博客、文章、邮件列表、论坛、推特等），我无法完成本小册。

你手中的本小册使用了 Asciidoctor 工具链，使得创建 EPUB 和 MOBI 文件成为可能。我非常感谢 Asciidoctor 社区，当然还有 Dan Allen，他帮助我解决了一些问题，使得最终结果看起来如此棒极。[5] PlantUML 是一个非常强大的工具，拥有非常丰富的绘图语法……而有时，你需要一点帮助。所以，感谢 PlantUML 社区。[6] 至于编写本小册使用的文本编辑器，你可能猜到了：它是一个 IDE！

感谢 JetBrains 为我提供了卓越的 IntelliJ IDEA 免费许可证。[7]

住在巴黎，我还必须感谢所有为我提供避风港的酒吧，让我能够边喝咖啡边聊天边写作：La Fontaine、Le Chat Bossu、La Grille、La Liberté 和 Bottle Shop。

向我可爱的女儿 Eloise 和 Ligia 献上大大的吻。她们是生命给我的最好的礼物。

谢谢大家！

- 1 Thorben Janssen 博客 `https://thoughts-on-java.org`
- 2 Youness Teimouri `http://www.youness-teimouri.com`
- 3 @aurelievache `https://twitter.com/aurelievache`
- 4 Duchess France `http://www.duchess-france.org`
- 5 Asciidoctor doctor `http://asciidoctor.org`
- 6 PlantUML `http://plantuml.com`
- 7 IntelliJ IDEA `https://www.jetbrains.com/idea`

## 引言

在 90 年代后期，我正在研究 J2EE 1.2：这是 Java 企业版的第一个版本。那时也是公司开始意识到互联网对其业务潜力的时期。几个月来，我为一家著名的英国航空公司工作，建立他们的电子商务网站。是的，那是一个你通常在旅行旅行社购买机票或火车票的时代。这种革命性的尝试（在线购买机票）付出了技术成本：一个静态内容集群（HTML、CSS、图像）、一个 Web 层集群（Servlets 和 JSPs）、一个无状态 EJB 集群、一个实体豆（Entity Beans）集群以及一个数据库集群。正如你可以想象的，每一层的负载均衡、故障转移和粘性会（sticky sessions）都充满了应用服务器。这个电子商务网站上线了……而且它运行良好！

接着是 Struts、Spring 和 Hibernate。全 J2EE 应用服务器缩小到像 Tomcat 或 Jetty servlet 容器。我们看到事物在发生变化，例如架构变得无状态化、放弃了故障转移、从 SOAP 到 REST 的迁移，以及移动设备接管了网页爬虫。其他事情没有变化，比如老牌“四人龙”设计模式、架构模式、单元测试框架和构建工具。我们重新发明了一些轮子并给它们起了不同的名字，但我们也学习了数十种新的编程语言（无论是否运行在 JVM 之上）以及敏捷方法。得于这些演进，今天你可以坐下来阅读本小册。

## 本小册从何而来？

自1998年参与 JEE 以来，我一直关注它的演进并加入了从 6 到 8 的 Java EE 专家组。期间，我写了一本名为《Java EE 5》的法文书。这本书由一家法国编辑出版并引起了关注。随后，一位美国编辑联系我希望编写英文版。我喜欢这个挑战。因此，我改变了书籍结构，更新了它，翻译了它，并形成了《Java EE 6》。几年后，Java EE 7 发布了，我更新了书籍，增加了一些章节，并形成了长达500 页的《Java EE 7》[1]。这种写作过程变得有些痛苦（某些文本编辑器不适合写书）、缺乏活性（很难频繁更新论文），而且我也和我的编辑发生过冲突。[2]

与此同时，Java EE 8 的历史也有些痛苦且漫长。我仍然是专家组的一员，但没有人知道为什么专家邮件列表如此安静。没有真正的交流，没有愿景，没有真正的挑战。那时我决定不再浪费时间写关于 Java EE 8 的书。但社区并不这么认为。我开始收到关于更新书籍的邮件。我决定审视一下。是什么阻碍了我写作？显然是我的编辑和 Java EE 8。因此，我决定抛弃它们。我从我的《Java EE 7》书中提取了我需要的章节并更新了它们。这就是编写“小册”（fascicles）而不是一整本书的灵感所在。然后，我研究了自出版，现在我来到 Amazon Kindle Publishing 了。[3]

Java Persistence API 占据了我《Beginning Java EE 7》一书的三个章节，长度超过了一百页。它是关于 Java Persistence API 2.0 的。从那时起，该规范已演进到了 2.2 版本，并被许多不同的框架使用。我甚至为 PluralSight 创建了一整一门在线课程。[4] 直到今天，我仍然在项目中广泛使用 JPA。

希望你会发现这个小册对你有帮助。

## 本小册是面向谁的？

Java Persistence API 起于 Hibernate 社区。它随后在 JCP 中定义了规范，并成为 Java EE 平台的一部分。

因此，本小册面向整个 Java 社区。如果你来自 Java EE 背景，你无疑对 JPA 非常熟悉。但本小册也旨在供 Spring 社区使用。Spring 从一开始就拥抱了 JPA。因此，你在小册中看到的所有解释和示例在 Spring、Java EE 以及其他 Java 技术中都可以箱即用。

当然，Java Persistence API 可以在纯 Java SE 上运行，因此任何 Java 开发者都能从中受益。遵循和理解本小册的唯一要求是了解 Java 并具有一些关系数据库的知识。

## 本小册是如何结构的？

本小册侧重于 JPA 2.2。它的结构将帮助你发现这项技术，如果你已经有了某些经验，也将帮助你深入研究。

本小册从第 1 章开始，展示了几行 JPA 代码。这是因为作为开发者，我们学习学习新技术时喜欢先读代码。

第 2 章简要介绍了 Java Persistence API、它所解决的问题，并解释了贯穿整个小册的共同关注点。本章还探讨了该技术的标准化方面及其来源。

第 3 章主要用于展示 Java Persistence API 的基础代码，并引入了它的主要 API 和部署描述符。

第 4 章介绍了对象关系映射（即将 Java 对象映射到关系型数据库中），并展示了我们如何使用注解和 XML 将 JPA 实体映射到关系数据库。

一旦完成了映射，第 5 章将向你展示如何管理这些实体：如何从关系数据库中持久化、删除或查找实体。

对实体进行 CRUD 操作是不够的。第 6 章解释了如何使用强大的 Java Persistence Query Language（JQL），以便你可以根据不同的标准查询实体。

实体具有复杂的生命周期，将在第 7 章中解释。本章还涵盖了回调和监听器。

第 8 章将涵盖一些高级主题，如缓存和并发访问。

第 9 章展示了如何将 Java Persistence API 与其他技术（如 Bean Validation、CDI、JTA 和 Spring）集成。

在第 10 章，你将利用小册介绍的大部分概念构建一个更复杂的应用程序。

第 10 章以你在小册中所学内容的总结结束。

附录 A 重点介绍了整个小册中使用的工具以及如何安装它们。

JPA 2.2 背后有着悠久的规范历史。附录 B 列出了该规范的所有修订。

附录 C 指了一些外部参考文献，如果你想了解更多关于 JPA 的知识，这些非常阅读。

这不是我写的唯一的小册。你可以在附录 D 中找到其他小册的描述：Understanding Bean Validation 2.0，Understanding JPA 2.2。

## 约定

本小册使用了多种语言，主要是 Java，但也包括 XML 或 shell 脚本。每个代码示例都经过适当显示，并以等宽字体出现。所有代码均来自公共 Git 仓库并经过持续测试。因此，你不应该在语法不正确的代码上遇到任何问题。在某些情况下，源代码经过特殊格式处理以适应可用的页面空间，增加了额外的换行或修改了缩进。为了提高可读性，某些示例省略了认为不必要的代码。但请始终记住，你可以在线上 `https://github.com/agoncal/agoncal-fascicle-jpa/tree/2.2` 找到完整代码。

*斜体*用于首次强调一个重要的词，或为缩写词/术语提供定义。**粗体**很少使用。

> 关于某些有用信息的说明。

> 关于重要事情的重要说明。

## 示例应用程序

在本书中，你将看到所有属于 CD-BookStore 应用程序的代码。该应用程序是一个电子商务网站，允许用户浏览出售的书籍和 CD 目录。通过购物车，他们可以在浏览目录时添加或删除物品，并结账以便付款并获取订单。该应用程序与银行系统有外部交互，以验证信用卡号。

与系统交互的角色：

- 公司员工，他们需要管理物品目录和客户详情。他们也可以浏览订单。
- 访问网站并咨询书籍和 CD 目录的匿名用户。如果他们想买物品，他们需要创建一个账户成为客户。
- 客户，他们可以浏览目录、更新账户详情并在网上购买物品。
- 系统将信用卡验证委托给的外部银行。

图 1 展示了用例图，描述了系统的参与者和功能。

![](img/c29e53007c33cf0fd2f7aed02ac4b8_27_0.png)

图 1. 应用程序的用例图

应用程序操作几个在图 2 中描述的领域对象。当然包括书籍和 CD，还有章节、订单、发票和购物车。目前不要在这个图上花费太多时间，因为你将在整个小册中遇到其中的大部分内容。

![](img/c29e53007c33cf0fd2f7aed02ac4b8_29_0.png)

图 2. 应用程序的类图

你在小册中看到的代码灵感源自 CD-BookStore 应用程序。如果你需要，可以下载该应用程序的代码，但如果你只需要遵循本小册的代码，则没有必要。[5]

## 下载和运行代码

本小册中使用的示例设计为用 JDK 1.8 编译，用 Maven 3.6.x 构建，用 JUnit 5.x 测试并将数据存储在 H2 数据库中。附录 A 显示了如何安装所有这些包，这些包将在大多数章节中用于构建、运行和测试代码。代码是在 Mac OS X 平台上开发和测试的，但在 Windows 或 Linux 上也应该运行。小册中示例的源代码可在公共 Git 仓库获取，并在 `https://github.com/agoncal/agoncal-fascicle-jpa/tree/2.2` 进行克隆、下载或在线浏览。

## 获取帮助
