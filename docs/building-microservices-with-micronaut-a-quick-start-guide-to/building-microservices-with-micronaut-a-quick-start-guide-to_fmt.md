
# Micronaut® 微服务构建指南：Java 开发者高性能响应式微服务快速启动指南我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。## Micronaut® 基金会序

- **产品组经理：** Aaron Lazar
- **产品经理：** Denim Pinto
- **高级编辑：** Storm Mann
- **内容开发编辑：** Tiksha Lal
- **技术编辑：** Pradeep Sahu
- **文稿编辑：** Safis Editing
- **项目协调员：** Deeksha Thakkar
- **校对员：** Safis Editing
- **索引员：** Tejal Daruwale Soni
- **制作设计：** Vijay Kamble

> 献给我我最亲爱的妻子 Rajveer，感谢你与我共同走过写这本书的旅程。你是在我翅膀下的风。
>
> Nirmal Singh

> 献给我的妻子 Waheetha 和儿子 Aaryan，感谢他们说服我完成了这本书。每一位作者的背后都有一个支持且充满爱的家庭。
>
> Zack Dawood

# 序言

2018 年 3 月，Micronaut 共同创始人 Graeme Rocher 在马德里的 Greach 大会上发表了主题演讲，在会上介绍了一个全新的、开源、全栈 JVM 软件开发框架。尽管 Graeme 和该框架所属公司 Object Computing 的核心开发团队深知他们构建了一套开创性的工具集，有望彻底改变微服务和无服务器应用程序的运行方式，但他们无法预测到在产品发布后，该框架和团队将迅速获得如此惊人的热情和支持。

通过将框架基础设施转移到编译器功能中，Micronaut 框架显著改变了开发者在构建微服务和无服务器应用程序时对启动时间和内存消耗的看法。它颠覆了开发者在服务器端 Java 中处理框架设计的方法，并重写了后 Java EE 时代如何构建框架的准则。

该框架已被 SmartThings、StainAI、Minecraft 以及全球许多其他机构使用。它曾在世界各地的技术会议上亮相，在 ThoughtWorks 技术雷达的“语言与框架”板块获得“试用”状态，在 Minecraft 的 Micronaut Blueprint 中获得了在线文青的青睐，并在 Micronaut Launch（一个用于快速轻松创建 Micronaut 程序的在线工具）上创建了超过 60,000 个应用程序。

说 Micronaut 框架大获成功也并非夸张！

2020 年，我们成立了 Micronaut 基金会，这是一个非营利公司，负责软件的路线图和开发、最佳实践与流程、仓库控制、文档与支持以及筹款。我们的目标是什么？确保框架的技术创新和进步，推动框架成为 JVM 领域的领先技术，并构建和支持互补文档、功能和服务的生态系统。

基金会由技术顾问委员会领导，该委员会由来自不同行业的思想领袖和代表组成。Object Computing 非常重视技术、经验和专业知识带来的机会。当 Dacwood 和 Nirmal Singh 找到我们并告诉我们正在写本书时，我们乐意以任何方式提供帮助。我们相信，Micronaut 框架将是一个游戏改变者，在 Zack 和 Nirmal 的指导下，你很快就会发现框架所提供的所有好处。无论你是从框架诞生之初就是它的粉丝，还是通过拿起这本书才刚刚开始，你都加入了一个致力于创造极致技术解决方案的社区和组织。我们坚信 Micronaut 框架将改变现状，从那里开始，你的旅程将走向何方？这将使你发现，智能编译器、快速运行时和技术解决方案将受限于你的想象。

Micronaut® 基金会序

# 贡献者

# 关于作者

Nirmal Singh 是一位富有创业精神的全才技术领袖，拥有 10 多年处理跨领域需求、领导高性能开发团队以及交付稳健软件解决方案的广泛且独特的经验。他在健康科技、金融科技、零售和电子商务领域担任过多种技术性职位。目前他在 CGI 领导一个工程小组，重构一个关键的财富管理应用程序。

> 我想特别感谢我亲爱的妻子在写这本书的旅程中的耐心和鼓励。没有她，这一切是不可能的。

Zack Dawood 是一位常驻加拿大的技术专家、领导者、作者和演讲者。Zack 在 IT 产品开发、大数据、机器学习、移动应用开发、区块链、支付、敏捷、企业架构和 DevOps 方面拥有 16 年经验。Zack 拥有众多认证，关键认证包括认证敏捷领袖、认证 Scrum 专家、SAFe、ITIL、微软认证专业人士和 TOGAF。自 2018 年以来，他一直是高级演讲大师（DTM）。Zack 还自 2018 年 11 月担任一个非营利组织的董事会成员。Zack 撰写技术博客并在 Stack Overflow 上做出贡献。

> 我首先要感谢我亲爱且耐心的妻子 Waheetha 和儿子 Aaryan，感谢他们在写书过程中提供的持续支持、耐心和鼓励。感谢 Packt 团队在完成这本书方面的支持和鼓励。

# 关于评审员

Patrick Pu 是 CGI 的高级全栈开发人员，负责构建基于微服务架构的基金会计平台。

Patrick 曾担任高级顾问，帮助许多客户为个人和商业银行、B2B 关系管理、儿童行为研究、体育流媒体和数字货币交易所构建数字解决方案。

Patrick 是一个猫爱好者和区块链爱好者。

- 在本地搭建 Apache Kafka 生态系统 150

# 前言

第 4 章“保护 Web 服务”涵盖了在 Micronaut 框架中保护 Web 端点的多种方法，例如会话认证、JWT 和 OAuth。

第 5 章“使用事件驱动架构集成微服务”从事件驱动架构开始，介绍了两种发布事件的模式：拉取模型和推送模型。随后，你将深入研究事件流，并使用 Apache Kafka 在宠物诊所应用（示例项目）中集成两个微服务。

第 6 章“测试微服务”阐明了各种自动化测试——单元测试、服务测试和集成测试，以及如何采用这些测试技术来实施审慎的自动化策略，以降低成本并增加微服务的健壮性。

第 7 章“处理微服务关注点”涵盖了开发微服务时的某些问题，如分布式配置管理、服务 API 文档编写、服务发现和 API 网关。随后，你还将探索 Micronaut 框架中的容错机制。

第 8 章“部署微服务”涵盖了微服务的构建和部署方面。你将通过自动化工具构建容器产物，然后利用 Docker Compose 部署微服务。

第 9 章“分布式日志、追踪与监控”重点讲解了如何通过分布式日志、分布式追踪和分布式监控在微服务中实现可观测性模式。

第 10 章“使用 Micronaut 进行 IoT”从介绍与 Alexa IoT 开始，涵盖了 Alexa 基础知识和一个 hello-world 示例。随后，你将能够在开发宠物诊所应用时将 Micronaut 与 Alexa 集成。

第 11 章“构建企业级微服务”涵盖了开发微服务的最佳实践以及如何构建和扩展企业级微服务。

## 系统要求

| 项目 | 要求 |
|---|---|
| 硬件 | CPU：8 核，内存：16 GB，硬盘：100 GB。 |
| 操作系统 | Windows、macOS X 和 Linux（任意）。 |
| Java JDK | 版本 8 或更高。 |
| Maven | 在你的本地工作区中设置 Maven。 |
| 开发 IDE | 可以使用任何基于 Java 的 IDE。 |
| Git | 在本地设置 Git。 |
| PostgreSQL | 将 PostgreSQL 作为独立应用或 Docker 容器应用设置。 |
| MongoDB | 将 MongoDB 作为独立应用或 Docker 容器应用设置。 |
| REST 客户端 | 设置任何 REST 客户端，如 Postman 或 Advanced REST client。 |
| Docker | 在本地设置 Docker。 |

如果你正在使用本书的电子版，我们建议你手动输入代码或通过 GitHub 仓库访问代码（链接在下一节提供）。这样做将帮助你避免任何与代码复制粘贴相关的潜在错误。

你可以从 GitHub 下载本书的示例代码文件：

`https://github.com/PacktPublishing/Building-Microservices-with-Micronaut`

如果代码有更新，将在现有的 GitHub 仓库中进行更新。

我们的书籍和视频目录中还提供了其他代码包，地址为：

`https://github.com/PacktPublishing/`

快去看看吧！

我们还提供了一个 PDF 文件，其中包含了书中使用的截图和图表的彩色版本。你可以在此处下载：

`https://static.packt-cdn.com/downloads/9781800564237_ColorImages.pdf`

全书使用了多种文本规范。

## 文本规范

**内联代码：**表示文本中的代码、数据库表名、文件名、文件扩展名、路径名、虚拟 URL、用户输入和 Twitter 账号。示例：“遵循这些指令，我们添加了一个 `foo-stream` 主题并向该主题添加了一条消息。”

代码块设置如下：

```java
@KafkaClient
public interface VetReviewClient {
    @Topic("vet-reviews")
    void send(@Body VetReviewDTO vetReview);
}
```

**粗体：**表示新术语、重要词汇或你在屏幕上看到的单词。例如，菜单或对话框中的单词在文中以如下形式显示。示例：“正如在 Kaidrop 上所看到的，我们可以验证来自 `pet-clinic-reviews` 微服务的事件已流出并添加到 `vet-reviews` 主题中。”

| 提示或重要注意事项 |
|---|
| 它们像这样显示。 |

我们随时欢迎读者的反馈。

当你读完《Building Microservices with Micronaut》后，我们想听听你的想法！请点击此处直接进入评价。你的评价对我们非常重要。

# 1 核心概念与基础

本节开启了微服务之旅，涵盖了微服务基础知识、微服务设计模式以及为什么 Micronaut 是理想的框架。本节包含以下章节：

- 使用 Micronaut 开始微服务

## 使用 Micronaut 开始微服务

在最近，关于微服务以及微服务架构如何改变 Web 的讨论非常热烈。在本章中，我们将回顾 Web 服务的演变，快速深入研究一些微服务设计模式，探讨大多数传统 Java 框架的缺陷以及 Micronaut 如何解决这些问题。最后，为了开始使用 Micronaut 框架，我们将设置 Micronaut CLI 并运行项目。

# 4 使用 Micronaut 开始微服务

在本章中，我们将重点关注以下主题：

- 微服务及其演变
- 理解微服务设计模式
- 为什么 Micronaut 是开发微服务的最佳选择
- 开始使用 Micronaut 框架
- 在 Micronaut 框架中运行 Hello 项目

在本章结束，你将理解 Web 服务如何演变为微服务，并了解与 Micronaut 框架相比，传统的 Java 框架在开发微服务方面的局限性。此外，通过运行项目，你还将获得使用该框架的实践知识。

## 技术要求

本章所有的命令和技术指令均在 Windows 10 和 macOS X 上运行。本章涵盖的代码示例可在 GitHub 仓库获取：

`https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/Chapter01`

需要在开发环境中安装并设置以下工具：

- **Java SDK：**版本 13 或更高（我们使用了 Java 14）。
- **Maven：**如果你希望使用 Maven 作为构建系统，则是可选的。但我们建议在任何开发机器上都设置 Maven。下载和安装 Maven 的说明请访问 `https://maven.apache.org/download.cgi`。
- **开发 IDE：**根据你的喜好，可以使用任何基于 Java 的 IDE，编写本章时使用的是 IntelliJ。
- **Git：**下载和安装 Git 的说明请访问 `https://git-scm.com/downloads`。

## 介绍微服务及其演变

在深入介绍和定义微服务之前，了解微服务是如何演变的将非常有帮助。在 20 世纪 60 年代后期，艾兰·凯（Alan Kay）创造了“面向对象编程”这一术语。尽管这是一个决定性的思想，但它后来诞生了使用面向对象编程构建软件解决方案的四大支柱：

- 封装
- 继承
- 多态
- 抽象

用一个短的助记法表示，它被称为 EIPA。自从这四大支柱诞生以来，软件行业经历了许多编程语言、框架、设计模式的兴起与衰落。随着每一次适配和理念的出现，思考者和实践者试图通过保持模块化设计以及松耦合且紧密封装的应用程序组件，来更接近 EIPA。在过去的几十年里，软件团队通过系统地采用这些关键支柱，从面向对象编程的“艺术”转向了面向对象编程的“科学”。这种迭代的旅程就是微服务的演变。

在 20 世纪 80 年代后期和 90 年代初，几乎每个企业级应用都通过命令行界面或原生桌面软件呈现。应用程序与数据库紧密连接，就像终端用户直接与数据库交互，而应用程序只是中间的一个薄薄的外壳层。那是单体应用或客户端/服务器（C/S）架构的时代。

## 使用 Micronaut 框架开始学习微服务

在下面的图中，我们可以看到用户是如何与单体应用交互的：

![单体客户端/服务器架构](img/768b67b9430f02ca52f7bb252e4a68e4_27_0.png)

图 1.1 – 单体客户端/服务器架构

如图 1.1 所示，在单体客户端/服务器架构中，应用程序与数据库紧密耦合，用户通过终端外壳或桌面应用程序进行交互。在这种架构中，维护良好的服务水平协议（SLA）是非常痛苦的。几乎所有的关键非功能性因素，如可扩展性、高可用性、容性和灵活性都表现不佳或失败。

为了解决这些某些问题，服务面向的架构（SOA）应运而生。在 21 世纪 20 年代，SOA 在行业中正式化，并出现了一些标准协议，如简单对象访问协议（SOAP）。Web 服务描述语言（WSDL）也在此期间创建。Web 2.0 应用程序随着异步 JavaScript 和 XML（AJAX）而流行。企业总线和消息系统催生了一种向终端用户交付软件解决方案的新范式：软件即服务（SaaS）。软件解决方案不再通过桌面应用程序和终端客户端交付，而是通过 HTTP 以托管在线服务的形式交付给终端用户。在下面的图中，我们可以看到用户是如何与基于 SOA 的应用程序交互的：

## 介绍微服务及其演变

![SOA](img/768b67b9430f02ca52f7bb252e4a68e4_28_0.png)

图 1.2 – SOA

如图所示，SOA 通过分离 Web 应用、Web 服务器和应用服务器之间的关注点，带来了更多的解耦。应用服务器或企业总线（ESB）通常与数据库交互，而用户通过浏览器访问数据库来与之交互（SaaS 解决方案）。虽然 SOA 带来了一些缓解，但 SaaS 的采用让可扩展性和灵活性留下了未待解决的难题。

2010 年之后，技术世界的运行速度比之前的二十年快得多。随着容器、云、大数据和机器学习的引入，架构设计中的一切都开始快速移动。这是一个 Uber、Airbnb、Netflix 以及免费/高级版应用的时代。应用程序的设计是针对分布式计算和可扩展性的。通过微服务架构，应用程序被拆分为相互独立、松耦合的微服务，每个微服务都拥有自己的数据库。在下面的图中，我们可以看到用户是如何与基于微服务的应用程序交互的：

![微服务架构](img/768b67b9430f02ca52f7bb252e4a68e4_28_1.png)

图 1.3 – 微服务架构

## 使用 Micronaut 框架开始学习微服务

在后续的图中，我们可以看到用户是如何与单体应用交互的：

如图所示，在单体客户端/服务器架构中，应用程序与数据库紧密耦合，用户通过终端外壳或桌面应用程序进行交互。在这种架构中，维护良好的服务水平协议（SLA）是非常痛苦的。几乎所有的关键非功能性因素，如可扩展性、高可用性、容性和灵活性都表现不佳或失败。

为了解决这些某些问题，服务面向的架构（SOA）应运而生。在 21 世纪 20 年代，SOA 在行业中正式化，并出现了一些标准协议，如简单对象访问协议（SOAP）。Web 服务描述语言（WSDL）也在此期间创建。Web 2.0 应用程序随着异步 JavaScript 和 XML（AJAX）而流行。企业总线和消息系统催生了一种向终端用户交付软件解决方案的新范式：软件即服务（SaaS）。软件解决方案不再通过桌面应用程序和终端客户端交付，而是通过 HTTP 以托管在线服务的形式交付给终端用户。在下面的图中，我们可以看到用户是如何与基于 SOA 的应用程序交互的：

如图所示，SOA 通过分离 Web 应用、Web 服务器和应用服务器之间的关注点，带来了更多的解耦。应用服务器或企业总线（ESB）通常与数据库交互，而用户通过浏览器访问数据库来与之交互（SaaS 解决方案）。虽然 SOA 带来了一些缓解，但 SaaS 的采用让可扩展性和灵活性留下了未待解决的难题。

2010 年之后，技术世界的运行速度比之前的二十年快得多。随着容器、云、大数据和机器学习的引入，架构设计中的一切都开始快速移动。这是一个 Uber、Airbnb、Netflix 以及免费/高级版应用的时代。应用程序的设计是针对分布式计算和可扩展性的。通过微服务架构，应用程序被拆分为相互独立、松耦合的微服务，每个微服务都拥有自己的数据库。在下面的图中，我们可以看到用户是如何与基于微服务的应用程序交互的：

![微服务架构](img/768b67b9430f02ca52f7bb252e4a68e4_28_1.png)

图 1.3 – 微服务架构



用一个短的助记法表示，它被称为 EIPA。自从这四大支柱诞生以来，软件行业经历了许多编程语言、框架、设计模式的兴起与衰落。随着每一次适配和理念的出现，思考者和实践者试图通过保持模块化设计以及松耦合且紧密封装的应用程序组件，来更接近 EIPA。在过去的几十年里，软件团队通过系统地采用这些关键支柱，从面向对象编程的“艺术”转向了面向对象编程的“科学”。这种迭代的旅程就是微服务的演变。

在 20 世纪 80 年代后期和 90 年代初，几乎每个企业级应用都通过命令行界面或原生桌面软件呈现。应用程序与数据库紧密连接，就像终端用户直接与数据库交互，而应用程序只是中间的一个薄薄的外壳层。那是单体应用或客户端/服务器（C/S）架构的时代。

## 使用 Micronaut 框架开始学习微服务

在下面的图中，我们可以看到用户是如何与单体应用交互的：

![](img/768b67b9430f02ca52f7bb252e4a68e4_27_0.png)

图 1.1 – 单体客户端/服务器架构

如图 1.1 所示，在单体客户端/服务器架构中，应用程序与数据库紧密耦合，用户通过终端外壳或桌面应用程序进行交互。在这种架构中，维护良好的服务水平协议（SLA）是非常痛苦的。几乎所有的关键非功能性因素，如可扩展性、高可用性、容性和灵活性都表现不佳或失败。

为了解决这些某些问题，服务面向的架构（SOA）应运而生。在 21 世纪 20 年代，SOA 在行业中正式化，并出现了一些标准协议，如简单对象访问协议（SOAP）。Web 服务描述语言（WSDL）也在此期间创建。Web 2.0 应用程序随着异步 JavaScript 和 XML（AJAX）而流行。企业总线和消息系统催生了一种向终端用户交付软件解决方案的新范式：软件即服务（SaaS）。软件解决方案不再通过桌面应用程序和终端客户端交付，而是通过 HTTP 以托管在线服务的形式交付给终端用户。在下面的图中，我们可以看到用户是如何与基于 SOA 的应用程序交互的：

## 介绍微服务及其演变

![](img/768b67b9430f02ca52f7bb252e4a68e4_28_0.png)

图 1.2 – SOA

所示，SOA 通过分离 Web 应用、Web 服务器和应用服务器之间的关注点，带来了更多的解耦。应用服务器或企业总线（ESB）通常与数据库交互，而用户通过浏览器访问数据库来与之交互（SaaS 解决方案）。虽然 SOA 带来了一些缓解，但 SaaS 的采用让可扩展性和灵活性留下了未待解决的难题。

2010 年之后，技术世界的运行速度比之前的二十十年快得多。随着容器、云、大数据和机器学习的引入，架构设计中的一切都开始快速移动。这是一个 Uber、Airbnb、Netflix 以及免费/高级版应用的时代。应用程序的设计是针对分布式计算和可扩展性的。通过微服务架构，应用程序被拆分为相互的、松耦合的微服务，每个微服务都拥有自己的数据库。在下面的图中，我们可以看到用户是如何与基于微服务的应用程序交互的：

![](img/768b67b9430f02ca52f7bb252e4a68e4_28_1.png)

图 1.3 – 微服务架构

## 理解微服务设计模式

为了充分实现任何架构的好处，包括微服务架构，通常需要设计模式来支持架构方法。在接下来的章节中，我们将涵盖微服务中实用且常用的设计模式。每个模式解决应用程序的一个方面，我们将从实用角度来看这些模式。我们将从拆分设计模式开始。

### 拆分设计模式

拆分设计模式规定了我们如何将大型应用程序拆分为更小的服务。这些模式在设计任何变革性架构时都非常有用。以下是拆分中常用的设计模式。

### 按业务能力拆分

任何业务能力都是盈利的工具。如果我们能将应用程序列出并分类为一组业务能力，如库存管理、客户订单或运营，那么应用程序就可以拆分为基于这些能力的微服务。这种拆分过程对于中小型应用程序是有效且推荐的。

### 按领域/子领域拆分

如果应用程序是企业级且重量级的应用，那么上述方法可能会导致应用程序被拆分为较小的单体。这些单体虽然较小，但仍然是整体。在某些情况下，业务建模有助于将应用程序功能分类并映射到领域和子领域。领域/子领域内部的功能是类似的，但与其他领域/子领域的功能非常不同。微服务随后将围绕领域或子领域进行设计和构建（如果许多功能映射到某个领域）。

### 集成设计模式

一旦应用程序被拆分为更小的微服务，我们需要在这些服务之间建立内聚性。集成设计模式解决了此类协作需求。以下是集成中常用的设计模式。

### API 网关模式

通常，上游前端需要通过外壳层访问微服务。这个外壳层被称为 API 网关。API 网关设计模式为保持前端客户端简单起着重要作用：

- 前端客户端不需要向微服务发送过多的请求。
- 前端客户端不需要处理/聚合多个响应。
- 在服务器端，网关将请求路由到多个微服务，这些微服务可以并行运行。
- 在发送最终响应之前，我们可以聚合来自不同微服务的单独响应。

### 聚合模式（The aggregator pattern）

该模式与上述的 API 网关模式类似。然而，复合微服务是关键区别。复合微服务的职责是将传入的请求分发到多个微服务，然后通过协作创建一个统一的响应。当用户请求从业务逻辑角度来看是原子的，但由多个微服务处理时，就会使用这种模式。

### 链式微服务模式（The chained microservices pattern）

在某些场景下，传入请求按一系列步骤执行，其中每一步都可能产生对微服务的调用。例如，在在线市场订购商品需要以下步骤：

1. 搜索商品（库存管理服务）。
2. 将商品加入购物车（购物车服务）。
3. 检查已添加商品（支付服务、邮件服务、库存管理服务）。

所有这些服务调用都是同步的。完成用户请求将是所有链式微服务调用的集合。

### 数据管理模式（Data management patterns）

与持久层的集成是任何基于微服务的应用的重要方面。绿地（新建）和棕地（遗留系统改造）应用可能会规定它们在选择数据管理模式的要求。以下是微服务数据管理中最常用的设计模式。

### 每个服务一个数据库（Database per service）

在绿地（新建）应用中，为每个服务配备一个数据库是理想的。每个服务都是隔离数据库（关系型或非关系型）的所有者，任何数据操作必须仅通过该微服务执行。此外，如果任何其他微服务需要执行数据库操作，则它应该路由到该所有者微服务。

### 共享数据库（Shared database）

在棕地（改造类）应用中，将数据库分解为每个服务一个数据库可能是不可行的。在这种情况下，微服务架构的实现可以通过共享公共单体数据库的服务来启动。

### 命令查询职责分离（CQRS，Command query responsibility segregation）

在绿地应用或完全改造的应用中，由于每个微服务都是独立的数据库所有者，可能存在从多个数据库查询数据的需求。CQRS 模式规定将应用分解为命令和查询，以：

- **命令（Command）：** 这部分将管理任何创建、更新和删除请求。
- **查询（Query）：** 这部分将使用数据库视图管理查询请求，数据库视图可以统一来自多个架构或数据源的数据。

### 跨切面模式（Cross-cutting patterns）

某些关注点跨了微服务的所有方面/层。在接下来的子章节中，我们将讨论这些关注点和模式。

### 服务发现模式（The service discovery pattern）

在基于微服务的应用中，每个微服务在运行时可能有多个实例。此外，这些服务实例可以根据流量在运行时添加或删除。这种运行时灵活性对于上游消费者或它们如何连接服务可能是一个问题。

服务发现模式通过实现一个服务注册数据库来解决这个问题。服务注册是一个元数据存储器，包含如服务名称、服务运行位置以及服务当前状态等信息。任何运行时信息都将在服务注册中更新，例如，当服务添加新实例或服务宕机时。这减轻了上游消费者连接应用中不同微服务的困扰。

### 断路器模式（The circuit breaker pattern）

在基于微服务的应用中，服务之间通常通过调用端点相互交互。可能会出现这种情况：一个服务正在调用下游服务，但下游服务已宕机。如果没有断路器，上游服务将在下游服务宕机期间继续调用它，这将持续影响用户与应用的交互。

在断路器模式中，下游服务调用将通过代理进行路由。如果下游服务宕机，该代理将在固定间隔超时。超时过期后，代理将尝试重新连接。如果成功，它将连接下游服务；否则，它将重置超时时间。因此，断路器不会用不必要的调用轰炸下游服务，且不会影响用户与应用的交互。

### 日志聚合模式（The log aggregation pattern）

在微服务格局中，通常一个传入的请求会被多个服务处理。每个服务都会产生日志。在微服务格局中，通常一个传入的请求会被多个服务处理。每个服务都会产生日志。在微服务格局中，通常一个传入的请求会被多个服务处理。在微服务架构。在后续章节中，我们将深入探讨 Micronaut。

## 为什么 Micronaut 是开发微服务的最佳选择（Why Micronaut is the best choice for microservices）

在基于微服务的应用中，每个微服务在运行时可能有多个实例。此外，这些服务实例可以根据流量在运行时添加或删除。这种运行时灵活性对于上游消费者或它们如何连接服务可能是一个问题。

服务发现模式通过实现一个服务注册数据库来解决这个问题。服务注册是一个元数据存储器，包含如服务名称、服务运行位置以及服务当前状态等信息。任何运行时信息都将在服务注册中更新，例如，当服务添加新实例或服务宕机时。这减轻了上游消费者连接应用中不同微服务的困扰。

考虑到上述关键点，Micronaut 成为开发云原生、超轻量且快速微服务的首选框架。此外，我们进行了一次快速的基准测试实验，比较了 Micronaut 与另一个流行的传统框架的启动时间。在下图中，显示了 Micronaut 和传统框架的启动时间：

![](img/768b67b9430f02ca52f7bb252e4a68e4_35_0.png)

如上一个图表所示，传统框架需要 6,156 毫秒来启动，而 Micronaut 仅需 3,750 毫秒。应用启动时间的这种差异是巨大的，这使得 Micronaut 成为开发云原生和快速微服务的首选框架。

在接下来的章节中，我们将开始在 Windows 和 macOS 上使用 Micronaut 框架。

## 开始使用 Micronaut 框架

为了开始使用 Micronaut 框架，我们将首先在 Mac 和 Windows 操作系统上安装 Micronaut CLI。

### 在 macOS 上安装 Micronaut CLI

在 macOS 上，我们可以通过几种方式安装 Micronaut CLI——使用 SDKMAN!、Homebrew 或 MacPorts。在接下来的章节中，我们将分步介绍安装 Micronaut CLI 的指令。

### 使用 SDKMAN! 安装 Micronaut

请按照以下步骤使用 SDKMAN! 安装 Micronaut CLI：

1. 打开终端（Terminal）。
2. 如果你没有安装 SDKMAN!，请执行以下步骤：
   1. 输入或粘贴以下命令：

      ```bash
      curl -s https://get.sdkman.io | bash
      ```

   2. 接下来，输入或粘贴以下命令：

      ```bash
      source "$HOME/.sdkman/bin/sdkman-init.sh"
      ```

3. 要安装 Micronaut CLI，输入或粘贴以下命令：

   ```bash
   sdk install micronaut
   ```

在 Mac 终端上安装 Micronaut CLI 时，你将观察到以下交互：

```text
zackwood@zacks-mbp ~ % source "$HOME/.sdkman/bin/sdkman-init.sh"

zackwood@zacks-mbp ~ % sdk install micronaut

=================================================================

* 2020-08-10: Jbang 0.8.0 released on SDKMAN! https://github.com/jbang

djbang/releases/tag/v0.8.0. Follow @jbang #jbang

* 2020-08-17: Jbang 0.37.0 released on SDKMAN! Checkout https://github.com/jbang

djbang/releases/tag/v0.37.0. Follow @jbang #jbang

* 2020-08-17: Kotlin 1.4 released on SDKMAN! #kotlin

=================================================================
```

Downloading: micronaut 2.0.1

```text
################################################################# 100.0%

################################################################# 100.0%
```

Installing: micronaut 2.0.1  
Done installing!

Setting micronaut 2.0.1 as default.

图 1.5 – 使用 SDKMAN! 在 mac 上安装 Micronaut CLI

4. 如果上述所有步骤执行成功，你可以通过在终端中运行以下命令来验证 Micronaut CLI 的安装：

   ```bash
   mn -version
   ```

### 使用 Homebrew 安装 Micronaut

请按照以下步骤使用 MacPorts 安装 Micronaut CLI（注：原文此处为 MacPorts，但标题为 Homebrew）：

1. 打开终端。
2. 如果你没有安装 Homebrew，请执行以下步骤：
   1. 输入或粘贴以下命令：

      ```bash
      /bin/bash -c "$(curl -fSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
      ```

   2. 接下来，输入或粘贴以下命令：

      ```bash
      brew update
      ```

3. 输入或粘贴以下命令：

   ```bash
   brew install micronaut
   ```

在安装 Micronaut CLI 时，你将在终端中观察到以下交互：

```text
$ zackwood --- curl ~ ruby -W0 -- disable-gems,did you_mean,rubocop?/usr/local/Library/Homebrew/brew.rb install micronaut...

zackwood@zacks-mbp % brew install micronaut

== Downloading https://homebrew.bintry.com/bottles/openjdk-14.0.1.catalina.bot

== Downloading from https://d2v9kc4aoW7i7.cloudflare.net/d44db8c5b2b12a36d73f11

########################### 21.1%
```

> 图 1.6 - 使用 HomeBrew 在 macOS 上安装 Micronaut CLI

4. 如果上述所有步骤执行成功，你可以通过在终端输入以下命令来验证 Micronaut CLI 的安装：

   ```bash
   mn -version
   ```

### 使用 MacPorts 安装 Micronaut

请按照以下步骤使用 Homebrew 安装 Micronaut CLI（注：原文此处为 Homebrew，但标题为 MacPorts）：

1. 如果你没有安装 MacPorts，请遵循 https://www.macports.org/install.php 的说明。
2. 打开终端。
3. 输入或粘贴以下命令：

   ```bash
   sudo port sync
   ```

4. 输入或粘贴以下命令：

   ```bash
   sudo port install micronaut
   ```

在安装 Micronaut CLI 时，你将在终端中观察到以下交互：

![](img/768b67b9430f02ca52f7bb252e4a68e4_38.png)

图 1.7 - 使用 MacPorts 安装 Micronaut CLI

5. 如果上述所有步骤执行成功，你可以通过在终端输入以下命令来验证 Micronaut CLI 的安装：

   ```bash
   mn -version
   ```



### 在 Windows 上安装 Micronaut

请按照以下步骤在 Windows 上安装 Micronaut CLI：

1. 从 https://micronaut.io 下载二进制文件。
2. 将二进制文件解压到系统中的文件夹中。建议放在`C:\Program Files\Micronaut`。
3. 创建名为`MICRONAUT_HOME`的新环境变量。请将`%MICRONAUT_HOME%\bin`添加到你的`PATH`中。

#### 使用 Micronaut 框架开始微服务

4. 更新你的`PATH`变量。
5. 打开命令行或任何终端并输入以下命令：

```
mn
```

这将首次启动 CLI 并解析依赖项。

6. 要测试 CLI 是否安装正确，输入以下命令：

```
mn h
```

这是命令输出：

![](img/768b67b9430f02ca52f7bb252e4a68e4_39.png)

图 1.8 - 在 Windows 上安装 Micronaut CLI

7. 在输入上述命令后，你应该看到所有的 CLI 选项。

在本节中，我们将探索在 Windows 和 macOS 上安装 Micronaut CLI 的不同方法。为了上手操作 Micronaut 框架，我们将开始处理一个世界项目。

## 在 Micronaut 中进行 hello 世界项目

为了理解使用 Micronaut 框架开发微服务的实际方面，我们将处理一个 hello 世界项目。这将帮助你快速上手 Micronaut 框架，并让你直观体验开发微服务有多简单。

Micronaut 与 Maven 和 Gradle 包管理器无缝集成。我们将使用 Micronaut CLI 以及 Micronaut Launch（网页界面）分别涵盖一个示例。

### 使用 Micronaut CLI 创建 hello 世界项目

请按照以下步骤使用 Micronaut CLI 创建 hello 世界应用：

1. 打开终端（或命令行）。
2. 切换到你想创建 hello 世界项目的目录。
3. 输入以下命令：

```
mn create-app hello-world-maven --build-maven
```

4. 等待 Micronaut CLI 完成，它将创建一个`hello-world-maven`项目。`create-app`命令将为你创建一个带有 Maven 构建和系统安装的 Java 版本的骨架项目。它将创建`Application.java`以及示例测试类`ApplicationTest.java`。
5. 探索你新创建的`hello-world-maven`项目，在你偏好的 IDE 中打开该项目。
6. 要运行你的项目，请在 Bash 终端运行以下命令：

```bash
./mvnw compile exec:exec
```

请注意，如果你是从其他地方复制的项目，则需要通过输入以下命令重新配置`mvnw`：

```bash
mvn -N io.takari:maven:wrapper
```

为了创建一个简单的端点，让我们在`hello-world-maven`项目中添加一个简单的控制器。

- 为我们的`hello-world-maven`项目添加一个 web 包。
- 添加一个`HelloWorldController` Java 类。它将包含一个简单的 hello 端点：

```java
@Controller("/hello")
public class HelloWorld {

    @Get("/hello")
    @Produces(MediaType.TEXT_PLAIN)
    public String helloMicronaut() {
        return "Hello, Micronaut!";
    }
}
```

`HelloWorld`可以通过`.../hello`访问，`helloMicronaut()`将生成一个纯文本`"Hello, Micronaut!"`。

- 重新运行您的应用程序并在浏览器窗口中访问`http://localhost:8080/hello/`。服务器将返回以下响应：

![](img/768b67b9430f02ca52f7bb252e4a68e4_41_0.png)

默认情况下，应用程序将可以通过端口 8080 访问，可以在应用程序属性中更改此端口。

到此为止，我们使用 Micronaut CLI 完成了一个 hello world 项目。接下来，我们将探索 Micronaut Launch，这是一个 Web 界面，用于生成启动代码项目。

### 使用 Micronaut Launch 创建 hello 世界项目

`Micronaut Launch`（https://micronaut.io/launch/）是一个直观的 Web 界面，随 Micronaut 2.0.1 发布。我们可以使用此界面快速为各种 Micronaut 应用生成启动代码（如服务器应用程序、CLI、无服务器函数、消息应用程序等）。

让我们快速使用它为我们生成一个 hello world 应用。

请遵循以下指令使用 Micronaut Web 界面生成 hello world 项目：

1. 在浏览器窗口打开 Micronaut Launch：https://micronaut.io/launch/
2. 在 Application Type（应用类型）下，选择 Application（应用）。
3. 在 Micronaut Version（Micronaut 版本）下，选择 2.0.1。
4. 对于 Java version（Java 版本），选择 Java 14。
5. 对于 Language（语言），选择 Java。
6. 给出一个包名，例如`com.packpub.micronaut`。
7. 在 build option（构建选项）中选择 Gradle。
8. 为应用程序命名，例如`hello-world-gradle`。
9. 选择 JUnit 作为测试框架。
10. 完成所有选项的选择后，点击 GENERATE PROJECT（生成项目）。

在选择上述选项并提供各种输入后，Micronaut Launch 界面应如下：

![](img/768b67b9430f02ca52f7bb252e4a68e4_42_0.png)

您的项目启动代码源代码将生成并在一个压缩文件中。您可以将该压缩文件解压到所需的目录中，并在您偏好的 IDE 中打开它。就像上一个示例（`hello-world-maven`）一样，我们可以添加一个基本的`HelloWorldController`实例。

要运行项目，请在 Bash 终端中运行以下命令：

```
gradlew.bat run
```

当项目运行时，访问`http://localhost:8080/hello`，您可以在浏览器标签页中看到`Hello, Micronaut!`消息。

在本节中，我们探索了如何通过 Micronaut CLI 和 Micronaut Launch 用户界面通过开发小型世界项目来上手 Micronaut 框架。这个小练习将为下一章的内容提供良好的铺垫。

## 本章总结

在本章中，我们通过探索微服务的演进和一些实用的设计模式开启了微服务之旅。我们对比了 Micronaut 框架与传统的基于反射的 Java 框架。Micronaut 利用运行时编译（ahead-of-time compilation，而非反射）的方法使其成为开发微服务的理想框架。我们介绍了适用于 mac OS 以及 Windows 操作系统的 Micronaut CLI。最后，我们处理了`hello-world-maven`和`hello-world-gradle`项目。在两个项目中，我们都添加了 hello 端点。

通过涵盖微服务的基础知识以及实战项目，本章增强了您对微服务演进、设计模式以及为什么在开发微服务时应优先选择 Micronaut 的理解。这种基础性的理解是在 Micronaut 框架中进行微服务开发的基石。

在本章末尾，我们使用 Micronaut CLI 和 Micronaut Launch 开启了激动人的微服务开发旅程。在下一章中，我们将探索如何在 Micronaut 框架中集成不同的持久化存储和数据库。

## 复习问题

1. Web 服务是如何演变为微服务的？
2. 什么是微服务？
3. 什么是微服务架构？
4. 微服务设计模式有哪些？
5. 什么是 Micronaut？
6. 为什么在开发微服务时应优先选择 Micronaut？
7. 应该使用哪个框架开发微服务？
8. 如何在 macOS 上安装 Micronaut CLI？
9. 如何在 Windows OS 上安装 Micronaut CLI？
10. 如何使用 Micronaut CLI 创建项目？
11. 如何使用 Micronaut Launch 创建项目？

# 第 2 节：构建微服务

本节将涵盖微服务开发，包括与持久层的集成、Web 端点的处理、端点安全性以及使用事件流集成微服务。您将在开发 Micronaut 框架下的微服务应用时完成所有这些操作。

本节包含以下章节：

- 第 2 章：处理数据访问
- 第 3 章：处理 RESTful Web 服务
- 第 4 章：Web 端点安全
- 第 5 章：使用事件驱动架构集成微服务

# 第 2 章：处理数据访问

任何微服务的采用如果没有集成持久化或数据存储都是不完整的。在本章中，我们将探索 Micronaut 框架中关于数据访问的各个方面。我们首先使用对象关系映射（ORM）框架来集成关系型数据库。然后，我们将深入研究持久化框架。此外，最后我们将查看集成 NoSQL 数据库的示例。为了涵盖这些主题，我们将处理一个 pet clinic 应用。该应用由：

- `pet-owner`：使用 ORM 框架集成关系型数据库的微服务
- `pet-clinic`：使用持久化框架集成关系型数据库的微服务
- `pet-clinic-review`：集成 NoSQL 数据库的微服务

在本章结束后，您将获得处理各种持久化框架以及如何在 Micronaut 框架中集成各种数据库（关系型及 NoSQL）的良好实践知识。

## 技术要求

本章中的所有命令和技术指令均在 Windows 10 和 macOS 上运行。本章涵盖的代码示例可以在仓库中找到：https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/Chapter02

需要在开发环境中安装并设置以下工具：

- Java SDK：13 版本及以上（我们使用了 Java 14）。
- Maven：可选，仅在您希望使用 Maven 作为构建系统时需要。然而，我们建议在任何开发机器上设置 Maven。下载和安装 Maven 的指令请参见 https://maven.apache.org/download.cgi。
- 开发 IDE：根据您的喜好，可以使用任何基于 Java 的 IDE。本章使用了 IntelliJ。
- Git：下载和安装 Git 的指令请参见 https://git-scm.com/downloads。
- PostgreSQL：下载和安装 PostgreSQL 的指令请参见 https://www.postgresql.org/download/。
- MongoDB：MongoDB Atlas 提供一个高达 512 MB 存储的免费在线数据库服务。然而，如果偏好本地数据库，则下载和安装的指令请参见 https://docs.mongodb.com/manual/administration/install-community/。我们在编写时使用了本地安装。
- Studio 3T for MongoDB：配合 MongoDB 本地安装，我们使用了 Studio 3T 作为 GUI。下载和安装 Studio 3T 的指令请参见 https://studio3t.com/download。

# 在 Micronaut 框架中与持久化集成

为了展示在 Micronaut 框架中与持久化（数据库）的集成，我们将针对 pet-clinic 应用的三个不同的微服务进行工作：

| 服务名称 | 数据库类型 | 持久化框架 |
|---|---|---|
| `pet-owner` | 关系型 (PostgreSQL) | Hibernate |
| `pet-clinic` | 关系型 (PostgreSQL) | MyBatis |
| `pet-clinic-reviews` | MongoDB | MongoDB Sync |

图 2.1 - pet-clinic 应用中的微服务

Hibernate 和 MyBatis 是关系型数据库的持久化框架，而为了与 NoSQL (MongoDB) 集成，我们将使用其原生同步驱动。

在接下来的章节中，我们将通过对相应微服务进行实际操作，涵盖每种集成技术。每个微服务（在本章范围内）将被组件为以下类型的组件：

- *Entity*（实体）：用于封装 ORM
- *Repository*（存储库）：用于封装与底层 Hibernate 框架的交互
- *Service*（服务）：包含任何业务逻辑以及对下游仓库的调用
- *CLI client*（CLI 客户端）：将增删改查（CRUD）请求连接到服务

下面的图描述了这些组件及其相互之间的作用：

![](img/768b67b9430f02ca52f7bb252e4a68e4_51_0.png)

图 2.2 – 微服务组件

我们将遵循服务-存储库模式来分离关注点并解耦微服务内部的组件。我们将以自底上的方式涵盖这些组件，从实体开始，然后是存储库，最后是服务。在下一节中，我们将探索使用 ORM 框架与关系型数据库进行集成。

## 使用 ORM (Hibernate) 框架与关系型数据库集成

ORM 框架允许你使用面向对象的范式来存储、查询或操作数据。它提供了一种面向对象的方法来访问数据库中的数据，换句话说，你无需使用 SQL，而是可以使用 Java 对象与数据库交互。

在 Java 中，作为一项标准规范，Java Persistence API (JPA) 规定了以下内容：

- 哪些 Java 对象应该被持久化
- 这些对象应该如何被持久化

JPA 不是一个框架或工具，而是规定了标准协议并涵盖了提取什么以及如何持久化的核心概念。各种实现框架（如 Hibernate 和 Eclipse）都采用了这些 JPA 标准。我们将使用 Hibernate 作为我们的 ORM 框架。

为了在 Micronaut 框架中实际操作 Hibernate，我们将处理小型 pet-clinic 应用，特别针对 Hibernate，我们将关注 pet-owner 微服务。接下来的图展示了 pet-owner 微服务的架构设计：

| owners | | visits |
|---|---|---|
| PK id | | PK id |
| first_name | name | visit_date |
| last_name | birth_date | description |
| address | Date | pet_id |
| city | FK owner_id | |
| telephone | FK type_id | |
| | | types |
| | | name |

图 2.3 - pet-owner 架构

本质上，在 pet-owner 架构中，一个人可以拥有零或多个（特定类型的）宠物，而只宠物可以有零或多次兽医访问。在接下来的章节中，我们将开始设置 pet-owner 架构。

## 在 PostgreSQL 中生成 pet-owner 架构

要生成 pet-owner 架构，请遵循以下指令：

1. 从 https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/blob/master/Chapter02/micronaut-petclinic/pet-owner/src/main/resources/db/db-sql.txt 下载 DB-SQL。
2. 打开 PostgreSQL 的 PgAdmin 并打开查询工具。
3. 分段运行前面的 SQL 章节。它将创建一个 pet-owner 用户、架构和表。
4. 最后，运行 SQL 数据以向这些表中摄入一些虚拟数据。

完成架构设置后，我们将把注意力转向下一个处理 Micronaut 项目。

## 为 pet-owner 微服务创建 Micronaut 应用

为了为 pet-owner 微服务生成样板代码，我们将使用 Micronaut Launch。Micronaut Launch 是一个生成样板代码的直观界面，可以通过 https://micronaut.io/launch/ 访问。打开后，该界面将如下截图所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_53_0.png)

图 2.4 – 使用 Micronaut Launch 生成 pet-owner 项目

在 Micronaut Launch 中，我们将选择以下功能（点击 FEATURES 按钮）：

- `data-jpa`
- `hibernate-jpa`
- `jdbc-hikari`
- `logback`
- `postgres`

指定上述选项后，点击 GENERATE PROJECT 按钮。

一个 ZIP 文件将下载到你的系统。将下载的源代码解压到你的工作空间，并在你偏好的 IDE 中打开项目。

在 pet-owner 微服务应用中，我们将遵循服务-存储库模式来分离关注点并解耦微服务内部的组件。正如之前讨论的，我们将采取自底上的方法涵盖这些组件，从实体开始，然后是存储库，最后是服务。

### 创建实体

实体是一个带有`@Entity`注解的普通 Java 对象（POJO）。为了映射表，我们可以定义`Owner`实体类。在前面的代码段中，我们正在为`owners`表声明`Owner`实体。

```java
@Entity
@Table(name = "owners", schema = "petowner")
```



```java
public class Owner implements Serializable {

    private static final long serialVersionUID = 1L;

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(name = "first_name")
    private String firstName;

    @Column(name = "last_name")
    private String lastName;

    @Column(name = "address")
    private String address;

    @Column(name = "city")
    private String city;

    @Column(name = "telephone")
    private String telephone;

    // Getters and setters

    public Long getId() { return id; }

    public void setId(Long id) { this.id = id; }

    public String getFirstName() { return firstName; }

    public void setFirstName(String firstName) { this.firstName = firstName; }

    public String getLastName() { return lastName; }

    public void setLastName(String lastName) { this.lastName = lastName; }

    public String getAddress() { return address; }

    public void setAddress(String address) { this.address = address; }

    public String getCity() { return city; }

    public void setCity(String city) { this.city = city; }

    public String getTelephone() { return telephone; }

    public void setTelephone(String telephone) { this.telephone = telephone; }
}
```

### 处理数据访问

在前面的代码中，我们为`owners`表声明`Owner`实体。同样，我们可以定义其他实体类：`pets`表的`Pet`、`visits`表的`Visit`以及`types`表的`PetType`。我们将在下一节查看关系的定义。

### 定义实体之间的关系

使用 Hibernate 框架，我们可以定义以下关系类型：

- 一对一
- 一对多/对一
- 多对多

让我们来看每种关系类型。

### 映射一对一关系

在`pet-owner`示例中，实体之间没有一对一关系。然而，假设将`owners`表中的所有地址信息都提取到`addresses`表中；结果架构将如下所示：

| owners |  | pets |  | visits |
|---|---|---|---|---|
| PK id |  | PK id |  | PK id |
| first_name | name |  | visit_date |
| last_name | birth_date |  | description |
| address | Date |  | pet_id |
| city | FK owner_id |  | FK |
| telephone | FK type_id |  |  |

| owners |  | addresses |
|---|---|---|
| PK id |  | PK id |
| first_name |  | address |
| last_name |  | city |
| FK address_id |  | telephone |

图 2.5 – `owners`和`addresses`之间的一对一关系

本质上，在上述架构中，一个所有者拥有一个地址。

在`Owner`实体中，为了定义这种关系，可以使用`@ToOne`：

```java
@Entity
@Table(name = "owners", schema = "petowner")
public class Owner implements Serializable {

    private static final long serialVersionUID = 1L;

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ToOne(cascade = CascadeType.ALL)
    @JoinColumn(name = "address_id", referencedColumnName = "id")
    private Address address;

    // Getters and setters
}
```

`@JoinColumn`将连接`owners`表中的`address_id`列。

而在`Address`（地址）实体中的这种关系将如下定义：

```java
@Entity
@Table(name = "address")
public class Address {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @Column(name = "id")
    private Long id;

    //...

    @OneToOne(mappedBy = "address")
    private User user;

    //... getters and setters
}
```

你可能注意到，在`Owner`实体中，我们使用`@JoinColumn`定义了一对一关系，因为`owners`表包含了`address_id`。然而，在`Address`实体中，我们可以简单地使用`mappedBy`并指向`Owner`实体中定义的`address`变量。JPA 会在后台处理这种双向关系的管理。

### 映射一对多/多对一关系

幸运的是，在`pet-owner`模式中，我们有多种一对多或多对一关系的实例（多对一仅仅是一对多关系的反转）。为了保持重点，让我们考虑`owners`表和`pets`表之间的以下关系：

## 使用 ORM（Hibernate）框架与关系型数据库集成

| owners | pets | visits |
|---|---|---|
| PK | id | PK | id | PK | id |
|  | first_name | name | visit_date |
|  | last_name | birth_date | description |
|  | address | Date | pet_id |
|  | city | FK | owner_id |  |
|  | telephone | FK | type_id |  |

| types |  |
|---|---|
| PK | id |
|  | name |

| owners | addresses |  |  |
|---|---|---|---|
| PK | id | PK | id |
|  | first_name | address |
|  | last_name | city |
|  |  | telephone |
| FK | address_id |  |  |

| owners | pets |  |  |
|---|---|---|---|
| PK | id | PK | id |
|  | first_name | name |
|  | last_name | birth_date |
|  | address | Date |
|  | city | FK | owner_id |
|  | telephone | FK | type_id |

图 2.6 – `owners`与`pets`之间的一对多关系

在`Owner`实体中，上述的一对多关系将如下定义：

```java
@Entity
@Table(name = "owners", schema = "petowner")
public class Owner implements Serializable {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    //...

    @OneToMany(mappedBy = "owner", cascade = CascadeType.ALL)
    private Set<Pet> pets = new HashSet<>();

    //...
}
```

在`Pet`实体中，该关系将映射如下：

```java
@Entity
@Table(name = "pets", schema = "petowner")
public class Pet implements Serializable {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    //...

    @ManyToOne
    @JoinColumn(name = "owner_id")
    private Owner owner;

    //...
}
```

再次，如果你注意到，`Pet`实体中我们使用`@JoinColumn`定义了与`Owner`之间清晰的关系（因为`pets`表包含了`owner_id`），而在`Owner`实体中，我们仅使用了`mappedBy = "owner"`。JPA 将在后台定义并管理这种双向关系。

### 映射多对多关系

映射和管理多对多关系要稍微复杂一些。在`pet-owner`模式中，我们并没有多对多关系的实例（正如前面所示，在`Pet`实体中我们使用`@JoinColumn`定义了与`Owner`之间清晰的关系，而在`Owner`实体中，我们仅使用了`mappedBy = "owner"`。JPA 将在后台定义并管理这种双向关系）。在`pet-owner`模式中，我们有一个多对多关系的实例。假设`owners`和`pets`之间有一个多对多关系：

![](img/many-to-many_0.png)

图 2.7 – `owners`与`pets`之间的多对多关系

## 数据访问

上述多对多关系将如下定义在实体中：

```java
@Entity
@Table(name = "owners")
public class Foo {

    // ...

    @ManyToMany(mappedBy = "owner", cascade = CascadeType.ALL)
    private Set<Bar> bars = new HashSet<>();
}
```

### 创建实体服务

服务将包含任何业务逻辑以及对存储的下游访问。我们可以为每个实体定义标准接口。

为了包含所有服务，我们将创建一个`com.packpub.micronaut.service`包。`OwnerService`接口将如下定义：

```java
public interface OwnerService {

    Owner save(Owner owner);

    Page<Owner> findAll(Pageable pageable);

    Optional<Owner> findOne(Long id);

    void delete(Long id);
}
```

`OwnerService`接口提供了所有服务方法的抽象声明。我们可以在类中实现所有声明的方法：

```java
@Singleton
@Transactional
public class OwnerServiceImpl implements OwnerService {

    private final Logger log = LoggerFactory.getLogger(OwnerServiceImpl.class);

    private final OwnerRepository ownerRepository;

    public OwnerServiceImpl(OwnerRepository ownerRepository) {
        this.ownerRepository = ownerRepository;
    }

    @Override
    public Owner save(Owner owner) {
        log.debug("Request to save Owner : {}", owner);
        return ownerRepository.mergeAndSave(owner);
    }

    @Override
    @ReadOnly
    @Transactional
    Page<Owner> findAll(Pageable pageable) {
        log.debug("Request to get all Owners");
        return ownerRepository.findAll(pageable);
    }

    @Override
    @ReadOnly
    @Transactional
    public Optional<Owner> findOne(Long id) {
        log.debug("Request to get Owner : {}", id);
        return ownerRepository.findById(id);
    }

    @Override
    public void delete(Long id) {
        log.debug("Request to delete Owner : {}", id);
        ownerRepository.deleteById(id);
    }
}
```

### 创建存储库

`JpaRepository`框架允许我们对实体进行 CRUD 操作。到目前为止，我们已经涵盖了如何定义存储库：

```java
@Repository
public interface OwnerRepository extends JpaRepository<Owner, Long> {
}
```

同样，我们可以为其他实体定义这些存储库——例如`Pet`、`Visit`和`PetType`。

在下一节中，我们将重点关注创建一个小型命令行实用程序，用于在宠物-所有者数据库中执行常见的 CRUD 操作。

### 执行基础 CRUD 操作

为了演示对实体执行基础 CRUD 操作，我们将创建一个简单的实用工具。我们可以创建一个名为`com.packpub.micronaut.utils`的新包来定义`PetOwnerClient`：

```java
@Singleton
public class PetOwnerClient {

    private final OwnersService ownerService;

    private final PetService petService;

    private final VisitService visitService;

    private final PetType petType;

    public PetOwnerClient(
        OwnersService ownerService,
        PetService petService,
        VisitService visitService,
        PetType petType
    ) {
        this.ownerService = ownerService;
        this.petService = petService;
        this.visitService = visitService;
        this.petType = petType;
    }

    // methods for performing CRUD operations...
}
```

该实用工具将使用构造方法注入所有服务。在此实用工具中进行的任何 CRUD 调用都将使用注入的服务执行。

### 执行读取/获取操作

我们可以在`PetOwnerClient`中定义一个简单的实用工具方法，调用`OwnerService`来获取所有者。此外，由于一个所有者有多个宠物，且每只宠物可以有多次就诊，获取所有者将获取宠物-所有者架构中的几乎所有内容。

```java
protected void findAll() {

    Page<Owner> pOwners =
        ownerService.findAll(Page.unpagged());

    ... iterate through paged content
}
```



`performAll()` 将获取所有所有者及其宠物（以及宠物就诊）。

### 执行保存操作

为了保存带有宠物和就诊的所有者，我们可以在 `PetOwnerClient` 中定义一个方法：

```java
protected Owner performSave() {
    Owner owner = initOwner();
    return ownerService.save(owner);
}
```

```java
private Owner initOwner() {
    Owner owner = new Owner();
}
```

```java
owner.setFirstName("Foo");
owner.setLastName("Bar");
owner.setCity("Toronto");
owner.setAddress("404 Adelaide St W");
owner.setTelephone("647000999");
```

```java
Pet pet = new Pet();

pet.setType(PetService.findAll(Page.unpagged())
    .getContent().get(1));
pet.setName("Baz");
pet.setBirthDate(LocalDate.of(2010, 12, 12));
pet.setOwner(owner);
```

### 处理数据访问

```java
Visit visit = new Visit();

visit.setVisitDate(LocalDate.now());
visit.setDescription("Breathing issues");
visit.setPet(pet);
```

```java
return owner;
}
```

`initOwner()` 初始化了一个带有宠物和就诊的所有者，它将被 `performSave()` 用于调用下游服务类方法来保存此所有者。

### 执行删除操作

在 `PetOwnerClient` 中，我们将定义一个删除方法来删除所有者（以及宠物和就诊）：

```java
protected void performDelete(Owner owner) {
    /** delete owner pets and their visits */

    Set<Pet> pets = owner.getPets();
```

```java
if (CollectionUtils.isNotEmpty(pets)) {
    for (Pet pet : pets) {
        Set<Visit> visits = pet.getVisits();

        if (CollectionUtils.isNotEmpty(visits)) {
            for (Visit visit : visits) {
                visitService.delete(visit.getId());
            }

            petService.delete(pet.getId());
        }
    }
}
```

```java
ownerService.delete(owner.getId());
}
```

`performDelete()` 首先遍历宠物和宠物就诊；在删除宠物就诊和宠物后，它将最终委托调用删除所有者。

## 总结

为了执行 `PetOwnerClient` CRUD 操作，我们将向 `Application.java` 中添加以下代码逻辑：

```java
@Singleton
public class Application {

    private final PetOwnerClient petOwnerClient;

    public Application(PetOwnerClient petOwnerClient) {
        this.petOwnerClient = petOwnerClient;
    }

    public static void main(String[] args) {
        Micronaut.run(Application.class, args);
    }

    @EventListener
    void init(StartupEvent event) {
        petOwnerClient.performDatabaseOperations();
    }
}
```

然后，当我们运行应用程序时，上述的 `@EventListener` 会调用 `PetOwnerClient` 执行数据库操作。

在本节中，通过宠物-所有者微服务，我们涵盖了将基于 Micronaut 的微服务与关系型数据库集成的方法。我们还讨论了如何定义实体、仓库和服务，最后演示了 CRUD 操作。在下一节中，我们将探索如何使用另一种类型的持久化框架（MyBatis）与关系型数据库集成。

## 使用持久化（MyBatis）框架集成关系型数据库

MyBatis 是一个 Java 持久化框架。与 Hibernate（一种 ORM 框架）不同，MyBatis 不支持将 Java 对象直接映射到数据库，而是将 Java 方法映射到 SQL 语句。

### 处理数据访问

MyBatis 通常用于迁移或转换项目，这些项目中已经存在旧数据库。由于数据库中已经定义了许多表、视图和其他数据对象，重构和规范化这些表/视图定义以将其直接映射到 Java 对象（使用 ORM 框架）可能不是理想场景。MyBatis 提供了将 Java 方法映射到 SQL 语句的理想方式。

| specialties | | vets |
| --- | --- | --- |
| Id | FK specialty_id | PK id |
| name | FK vet_id | first_name |
| | | last_name |

本质上，一个医生可以有许多专长，一个专长可以属于多个。在下一节中，我们将开始构建宠物诊所架构。

## 在 PostgreSQL 中生成 pet-clinic 架构

要生成 pet-clinic 架构，请遵循以下指令：

1. 从 https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/blob/Chapter02/micronaut/pet-clinic/src/main/resources/db-sql.txt 下载 DB-SQL。
2. 打开 PostgreSQL 的 PgAdmin 并打开查询工具。
3. 逐节运行前面的 SQL 部分。它将创建 pet-owner 用户、架构和表。
4. 最后，运行数据以向这些表中摄入一些虚拟数据。

### 生成 Micronaut 应用

完成架构工作后，我们将注意力转移到项目开发。

为了为 pet-clinic 生成样板代码，我们将使用 Micronaut Launch：

图 2.9 - 生成 pet-clinic 项目

在 Micronaut Launch 中，我们将选择以下功能（点击 FEATURES 按钮）：

- `jdbc-hikar`
- `logback`
- `postgres`

指定上述选项后，点击 GENERATE PROJECT 按钮。一个 ZIP 文件将下载到你的系统。

将下载的源代码解压到工作空间，并在优好的 IDE 中打开项目。一旦在 IDE 中打开项目，在 `pom.xml`（或 gradle build）中为 MyBatis 添加以下依赖：

```xml
<!-- https://mvnrepository.com/artifact/org.mybatis/mybatis -->
<dependency>
  <groupId>org.mybatis</groupId>
  <artifactId>mybatis</artifactId>
  <version>3.5.5</version>
</dependency>
```

该依赖是我们集成 Micronaut pet-clinic 架构的核心。与服务-仓库模式一致，我们将从底向上的方式探索 MyBatis 集成。首先，我们将定义实体，然后是仓库，最后是处理服务。

## 定义 MyBatis 工厂

为了执行各种 SQL 语句，MyBatis 在运行时需要一个 `SqlSessionFactory`。我们将从添加一个包 `com.packpub.micronaut.config` 开始。在此新包中添加以下类：

```java
@Factory
public class MybatisFactory {

  private final DataSource dataSource;

  public MybatisFactory(DataSource dataSource) {
    this.dataSource = dataSource;
  }

  @Context
  public SqlSessionFactory sqlSessionFactory() {
    TransactionFactory transactionFactory = new JdbcTransactionFactory();

    Environment environment = new Environment(
        "pet-clinic",
        transactionFactory,
        dataSource
    );

    Configuration configuration = new Configuration(environment);
    configuration.addMappers(
        "com.packpub.micronaut.repository"
    );

    return new SqlSessionFactoryBuilder().build(configuration);
  }
}
```

在 `application.yml` 中使用标准属性，Micronaut 将定义一个基于 Hikari 的数据源，该数据源将被注入以定义 `SqlSessionFactory`。在定义环境时，你可以选择任何名称（我们已经给出了 pet-clinic）。

### 创建实体类

与 Hibernate 实体类似，MyBatis 实体从根本上定义了一个 Java 类，用于将上游 Java 类与下游 SQL 交互（定义在 XML 或 Java map 中）集成起来。然而，一个细微的区别在于，任何 MyBatis 实体本身都不会包含任何映射逻辑。

我们将添加一个 `com.packpub.micronaut.domain` 包来包含领域实体。我们添加一个实体来代表 Specialty（专业科室）：

```java
@Introspected
public class Specialty implements Serializable {

    private static final long serialVersionUID = 1L;

    @NotNull
    private Long id;

    private String name;

    // ... getters and setters
}
```

同样，我们可以为 `vet` 表定义一个实体：

```java
@Introspected
public class Vet implements Serializable {
```

```java
private static final long serialVersionUID = 1L;
```

```java
@NotNull
private Long id;
```

```java
private String firstName;
```

```java
private String lastName;
```

```java
private Set<Specialty> specialties = new HashSet<>();
```

你可以注意到，这两个实体都没有任何映射到 `specialties` 或 `vets` 表的映射逻辑。在下一节中，我们将关注如何在 MyBatis 中创建数据访问仓库。

### 为实体定义 mappers（存储库）

对于 Vet 和 Specialty 实体，我们需要定义 MyBatis mappers。MyBatis 使用这些 mappers 与下游数据库交互。与 Java 应用相比，MyBatis mappers 是数据访问仓库。我们将添加一个 `com.packpub.micronaut.repository` 包来包含所有这些仓库。

在此包下，我们将添加 `SpecialtyRepository` 接口：

```java
/**
 * 用于 @{@link Specialty} 的 Mybatis mapper。
 */
public interface SpecialtyRepository {
```

```java
@Select("SELECT * FROM petclinic.specialties")
Collection<Specialty> findAll() throws Exception;
```

```java
@Select("SELECT * FROM petclinic.specialties WHERE id = #{id}")
Specialty findById(@Param("id") Long id) throws Exception;
```

```java
@Select("SELECT * FROM petclinic.specialties WHERE
UPPER(name) = #{name}")
Specialty findByName(@Param("name") String name) throws
Exception;
```

```java
@Select(
    "INSERT INTO petclinic.specialties(id, name)\n" +
    "VALUES (COALESCE(#{id}, (select
nextval('petclinic.specialties_id_seq'),
#{name})))\n" +
    "ON CONFLICT (id)\n" +
    "DO UPDATE SET name = #{name} \n" +
    "WHERE petclinic.specialties.id = #{id}\n" +
    "RETURNING id"
)
```

```java
@Options(flushCache = Options.FlushCachePolicy.TRUE)
Long save(Specialty specialty) throws Exception;
```

```java
@Delete("DELETE FROM petclinic.specialties WHERE id = #{id}")
void deleteById(@Param("id") Long id) throws Exception;
```

```java
@Select(
    "SELECT DISTINCT id, name FROM\n    petclinic.specialties WHERE id IN(" +
    "SELECT specialty_id FROM petclinic.vet_specialties\n    WHERE vet_id = #{id})"
)
Set<Specialty> findByVetId(@Param("id") Long id) throws Exception;
```

### 处理数据访问

```java
log.debug("Request to get Specialty : {}", id);
return Optional.ofNullable(
    (specialtyRepository.findById(id));
)
```

```java
@Override
public void delete(Long id) throws Exception {
    log.debug("Request to delete Specialty : {}", id);
    specialtyRepository.deleteById(id);
}
```

具体的服务方法在本质上非常简单，负责处理对下游存储库方法的调用。我们将为 Vet 添加一个类似的服务接口和具体实现，分别为 `VetService` 和 `VetServiceImpl`。

在下一节中，我们将重点关注创建一个小的命令行实用工具，用于对实体执行常见的 CRUD 操作，我们可以创建一个简单的工具类。我们可以创建一个名为 `com.packpub.micronaut.utils` 的新包来定义 `PetClinicCliClient`。

### 执行基础 CRUD 操作

为了使用之前章节中定义的服务和存储库，并对实体执行基础 CRUD 操作，我们可以创建一个简单的工具类。我们可以创建一个名为 `com.packpub.micronaut.utils` 的新包来定义 `PetClinicCliClient`。



```java
@Singleton
public class PetClinicCliClient {

    private final VetService vetService;
    private final SpecialtyService specialtyService;

    public PetClinicCliClient(VetService vetService, SpecialtyService specialtyService) {
        this.vetService = vetService;
        this.specialtyService = specialtyService;
    }

    // ...
}
```

## 使用持久化框架（MyBatis）与关系型数据库集成

`PetClinicCliClient` 通过构造方法注入了 `VetService` 和 `SpecialtyService`。这些服务将用于对 `vets`、`specialties` 和 `vet_specialties` 表执行各种数据库操作。

### 执行读取/获取操作

我们可以在 `PetClinicCliClient` 中定义一个简单的工具方法，调用 `VetService` 来获取所有医生。此外，由于一个医生可以有多个专长，获取医生将从 `specialties` 表获取数据：

```java
protected void performFindAll() {
    List<Vet> vets;
    try {
        vets = (List<Vet>) vetService.findAll();
        ... iterate on vets
    } catch (Exception e) {
        log.error("Exception: {}", e.toString());
    }
}
```

`performFindAll()` 方法会从数据库中获取所有医生及其对应的专长。

### 执行保存操作

我们将在 `PetClinicCliClient` 中保存一个带有专长的医生：

```java
protected Vet performSave() {
    Vet vet = initVet();
    Vet savedVet = null;
    try {
        savedVet = vetService.save(vet);
    } catch (Exception e) {
        log.error("Exception: {}", e.toString());
    }
    return savedVet;
}
```

```java
private Vet initVet() {
    Vet vet = new Vet();
    vet.setFirstName("Foo");
    vet.setLastName("Bar");

    Specialty specialty = new Specialty();
    specialty.setName("Baz");

    vet.getSpecialties().add(specialty);

    return vet;
}
```

`initVet()` 方法初始化了一个带有专长的新医生，然后由 `performSave(Object)` 方法将该对象持久化到数据库表中。

### 执行删除操作

在 `PetClinicCliClient` 中，我们将定义一个删除方法来删除医生（以及其专长）：

```java
protected void performDelete(Vet vet) {
  try {
    vetService.delete(vet.getId());
  } catch (Exception e) {
    log.error("Exception: {}", e.toString());
  }
}
```

`performDelete()` 方法将调用委托给 `VetService`，由其调用存储库最终从数据库中删除医生。

## 总结

为了执行 `PetClinicCliClient` 的 CRUD 操作，我们向 `Application.java` 中添加以下代码逻辑：

```java
@Singleton
public class Application {

    private final PetClinicCliClient petClinicCliClient;

    public Application(PetClinicCliClient petClinicCliClient) {
        this.petClinicCliClient = petClinicCliClient;
    }

    public static void main(String[] args) {
        Micronaut.run(Application.class, args);
    }

    @EventListener
    void init(StartupEvent event) {
        petClinicCliClient.performDatabaseOperations();
    }
}
```

当我们运行应用程序时，上述的 `@EventListener` 将调用 `PetClinicCliClient` 来执行各种数据库操作。

在本节中，我们使用 MyBatis 与关系型数据库进行了集成。我们涵盖了如何定义实体、存储库和服务，最后通过一个工具类展示了基础的 CRUD 操作。在下一节中，我们将探索 Micronaut 框架中与 NoSQL 数据库的集成。

# 与 NoSQL 数据库（MongoDB）集成

MongoDB 是基于文档的数据库，它以 JSON 或 BSON 格式存储数据。数据以键值对存储，类似于 JSON 对象。MongoDB 采用扩展性设计，当数据量和结构灵活且增长迅速时，建议使用它。与关系型数据库相比，有几个关键术语：

- **数据库（Database）：** MongoDB 中的数据库与关系型数据库中的数据库非常相似。
- **表（Table）：** 文档集合（collection）与关系型数据库中的表非常相似。
- **行（Row）：** 一个 BSON 或 JSON 文档将类比于“行”。

## 处理数据访问

为了开始，我们将使用 MongoDB。由于 MongoDB 采用扩展性设计，当数据量和结构灵活且增长迅速时，建议使用它。与关系型数据库相比，有几个关键术语：

- **数据库（Database）：** MongoDB 中的数据库与关系型数据库中的数据库非常相似。
- **表（Table）：** 文档集合（collection）与关系型数据库中的表非常相似。
- **行（Row）：** 一个 BSON 或 JSON 文档将类比于“行”。

## 创建 NoSQL 数据库

对于 petclinic 应用，我们将使用以下内容。由于 MongoDB 采用扩展性设计，当数据量和结构灵活且增长迅速时，建议使用它。与关系型数据库相比，有几个关键术语：

- **数据库（Database）：** MongoDB 中的数据库与关系型数据库中的数据库非常相似。
- **表（Table）：** 文档集合（collection）与关系型数据库中的表非常相似。
- **行（Row）：** 一个 BSON 或 JSON 文档将类比于“行”。

## 生成 Micronaut 应用

为了生成模板代码，我们将使用 Micronaut Launch。这是一个直观的界面：

图 2.10 – 使用 Micronaut Launch 生成项目

在 Micronaut Launch 中，我们将选择以下功能（点击 FEATURES 按钮）：

- `mongodb-sync`（MongoDB 的同步访问）
- `logback`

指定上述选项后，点击 GENERATE PROJECT 按钮。ZIP 文件将下载到你的系统。解压下载的源码到工作区并在你喜欢的 IDE 中打开项目。

## 在 Micronaut 中配置 MongoDB

在新的 pet-clinic-reviews 项目中，我们需要更新 `application.yml` 中的 URI 以正确的 MongoDB 实例。此外，我们将定义两个新的自定义属性——`databaseName` 和 `collectionName`：

```yaml
micronaut:
  application:
    name: Pet Clinic Reviews
mongodb:
  uri: mongodb://localhost:27017/pet-clinic-reviews
  databaseName: pet-clinic-reviews
  collectionName: vet-reviews
```

为了在项目中可以使用上述数据库和集合，我们可以在新包 `com.packpub.micronaut.config` 中定义一个配置类：

```java
public class MongoConfiguration {

  @Value("${mongodb.databaseName}")
  private String databaseName;

  @Value("${mongodb.collectionName}")
  private String collectionName;

  public String getDatabaseName() {
    return databaseName;
  }

  public String getCollectionName() {
    return collectionName;
  }
}
```

这将允许在项目中轻松访问 `databaseName` 和 `collectionName`，而无需反复使用 `@Value`。此外，由于这些属性是只读的，我们只为这些属性定义 getter 方法。

接下来，我们将创建一个实体类来定义医生评价对象。

### 创建实体类

在根级别，添加名为 `com.packpub.micronaut.domain` 的新包。该包将包含兽医评审（vet review）的领域/实体。我们可以定义以下 POJO 来表示兽医评审：

```java
public class VetReview {
    private String reviewId;
    private Long vetId;
    private Double rating;
    private String comment;
    private LocalDate dateAdded;

    @BsonCreator
    @JsonCreator
    public VetReview(
        @JsonProperty("reviewId")
        @JsonProperty("reviewId") String reviewId,
        @JsonProperty("vetId")
        @JsonProperty("vetId") Long vetId,
        @JsonProperty("rating") Double rating,
        @JsonProperty("comment")
        @JsonProperty("comment") String comment,
        @JsonProperty("dateAdded") LocalDate dateAdded
    ) {
        this.reviewId = reviewId;
        this.vetId = vetId;
        this.rating = rating;
        this.comment = comment;
        this.dateAdded = dateAdded;
    }

    // ... getters and setters
}
```

`@BsonCreator` 和 `@JsonCreator` 依附于类构造函数，用于将 `VetReview` 对象映射到相应的 BSON 或 JSON 文档。这在从 MongoDB 获取或存储文档并随后将其映射到 Java 对象时非常有用。

接下来，我们将重点关注如何为 `VetReview` 创建数据访问仓库（repository）。

### 创建数据访问仓库

为了管理对 `vet-reviews` 集合的访问，我们将创建一个仓库。我们可以通过添加 `com.packpub.micronaut.repository` 包来包含此仓库类。

为了抽象仓库将暴露的所有方法，我们可以声明一个接口：

```java
public interface VetReviewRepository {

    List<VetReview> findAll();

    VetReview findById(String reviewId);

    VetReview save(VetReview vetReview);

    void delete(String reviewId);
}
```

`VetReviewRepository` 概述了该仓库支持的基本操作。

我们需要在 `com.packpub.micronaut.repository.impl` 包中为 `VetReviewRepository` 接口提供具体的实现：

```java
@Singleton
public class VetReviewRepositoryImpl implements VetReviewRepository {

private final MongoClient mongoClient;

private final MongoConfiguration mongoConfiguration;

public VetReviewRepositoryImpl(MongoClient mongoClient, MongoConfiguration mongoConfiguration) {
this.mongoClient = mongoClient;
this.mongoConfiguration = mongoConfiguration;
}
```

```java
@Override
public List<VetReview> findAll() {
    List<VetReview> vetReviews = new ArrayList<>();
    getCollection().find().forEach(vetReview -> {
        vetReviews.add(vetReview);
    });
    return vetReviews;
}
```

```java
@Override
public VetReview findById(String reviewId) {
    return getCollection().find(eq("reviewId",
    reviewId)).first();
}
```

```java
@Override
public VetReview save(VetReview vetReview) {
    getCollection().insertOne(vetReview);
    getInsertedId();
    return findById(vetReview.getReviewId());
}
```

```java
@Override
public void delete(String reviewId) {
    getCollection().deleteOne(eq("reviewId",
    reviewId));
}
```

```java
private MongoCollection<VetReview> getCollection() {
    return mongoClient
    .getDatabase(mongoConfiguration.getDatabaseName())
    .getCollection(mongoConfiguration.getCollectionName(), VetReview.class);
}
```

该类中的 `getCollection()` 方法将从 MongoDB 获取数据库和集合。如前所示，向此集合保存和删除数据是简单的。若要根据特定条件查找，我们可以使用 `find()` 配合 `eq()`。`eq()` 是 MongoDB 驱动程序本身定义的 BSON 过滤器。

### 为实体创建服务

服务将封装任何业务逻辑以及对 `vet-reviews` 集合（在 MongoDB 中）的下游访问。我们可以声明一个接口来抽象服务中的核心方法。创建一个服务，我们应该首先在根包下创建 `com.packpub.micronaut.service` 包。

`VetReview` 接口可以声明为：

```java
public interface VetReviewService {

    List<VetReview> findAll();

    VetReview findByReviewId(String reviewId);

    VetReview save(VetReview vetReview);

    void delete(String reviewId);
}
```

`VetReviewService` 接口将声明该服务支持的基础骨干方法。为了提供具体实现，我们将在 `com.packpub.micronaut.service.impl` 包下创建一个 `VetServiceImpl` 类。



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。@Singleton
public class VetReviewServiceImpl implements VetReviewService {

    private final VetReviewRepository vetReviewRepository;

    public VetReviewServiceImpl(VetReviewRepository vetReviewRepository) {
        this.vetReviewRepository = vetReviewRepository;
    }
}
```

```java
@Override
public List<VetReview> findAll() {
    return vetReviewRepository.findAll();
}
```

```java
@Override
public VetReview findById(String reviewId) {
    return vetReviewRepository.findById(reviewId);
}
```

```java
@Override
public VetReview save(VetReview vetReview) {
    return vetReviewRepository.save(vetReview);
}
```

```java
@Override
public void delete(String reviewId) {
    vetReviewRepository.delete(reviewId);
}
```

提供了这些方法的具体实现。然而，对于未来的任何需求，这些方法可以扩展以包含业务逻辑，例如数据校验或数据转换。

为了对`VetReview`实体执行基本的 CRUD 操作，我们可以在`com.packpub.micronaut.utils`中创建一个简单的工具类来定义`PetClinicReviewClient`：

```java
@Singleton
@Requires(beans = MongoClient.class)
public class PetClinicReviewClient {

    private final Logger log = LoggerFactory.getLogger(PetClinicReviewClient.class);

    private final VetReviewService vetReviewService;

    public PetClinicReviewClient(VetReviewService vetReviewService) {
        this.vetReviewService = vetReviewService;
    }
}
```

该工具类通过构造函数注入`VetService`。我们将通过服务委托 CRUD 调用。

### 执行操作

我们可以在`PetClinicReviewClient`中定义方法，调用`VetReviewService`获取所有兽医评审或特定的评审：

```java
protected void performFindAll() {
    List<VetReview> vetReviews = this.vetReviewService.findAll();
    log.info("Reviews: {}", vetReviews);
}
```

```java
protected void performFindById(String reviewId) {
    VetReview vetReview = this.vetReviewService.findById(reviewId);
    log.info("Review: {}", vetReview);
}
```

`performFindAll()`将获取集合中所有的兽医评审，而`performFindById()`将根据`reviewId`获取特定的评审。

### 执行保存操作

我们将通过`PetClinicReviewClient`中的方法保存一个兽医评审：

```java
protected VetReview performSave() {
    VetReview vetReview = new VetReview(
        UUID.randomUUID().toString(),
        1L,
        3.5,
        "Good experience",
        LocalDate.now());
    return vetReviewService.save(vetReview);
}
```

### 执行删除操作

在`PetClinicReviewClient`中，我们将定义一个删除方法来删除兽医评审：

```java
protected void performDelete(VetReview vetReview) {
    vetReviewService.delete(vetReview.getReviewId());
}
```

## 总结

在`Application.java`中，我们可以作为启动事件调用`PetClinicReviewClient`，随后就可以展示对`vet-reviews`集合的基本 CRUD 操作。

```java
private final PetClinicReviewCliliClient
petClinicReviewCliliClient;
```

```java
public Application(PetClinicReviewCliliClient petClinicReviewCliliClient) {
this.petClinicReviewCliliClient = 
petClinicReviewCliliClient;
}
```

```java
public static void main(String[] args) {
Micronaut.run(Application.class, args);
}
```

```java
@EventListener void init(StartupEvent event) {
petClinicReviewCliliClient.
performDatabaseOperations();
}
```

当我们启动应用程序时，上述的`@EventListener`将调用`PetClinicReviewCliliClient`来执行数据库操作。

在本节中，我们涵盖了如何将 Micronaut 应用与 MongoDB 集成。我们定义了访问 MongoDB 数据库的实体、存储库和服务层。最后，我们通过一个轻量级实用程序展示了 CRUD 操作。

## 总结

在本章中，我们涵盖了将 Micronaut 应用与关系型以及 NoSQL 数据库集成的各个方面。我们探索了不同的持久化集成方式，即使用 ORM（Hibernate）、持久化框架（MyBatis）以及基于驱动的框架（MongoDB Sync）。在每种技术中，我们都深入探讨了如何定义实体、关系、存储库和服务。每个微服务都定义了一个命令行实用程序来展示常见的 CRUD 操作。

本章使我们掌握了涵盖 Micronaut 中几乎所有数据访问方面的技能。在书的剩余部分中，我们将通过更多的动手实践和涵盖 Micronaut 框架的其他方面，进一步探索和使用这些技能和学习成果。

在下一章中，我们将处理`pet-clinic`应用程序的 Web 层，在所有微服务中定义各种 REST 端点。

## 问题

1. 什么是对象-关系映射（ORM）框架？
2. 什么是 Hibernate？
3. 如何在 Micronaut 中使用 Hibernate 定义实体？
4. 如何在 Micronaut 中使用 Hibernate 映射一对一关系？
5. 如何在 Micronaut 中使用 Hibernate 映射一对多或多对一关系？
6. 如何在 Micronaut 中使用 Hibernate 映射多对多关系？
7. 如何在 Micronaut 中使用 Hibernate 执行 CRUD 操作？
8. 如何在 Micronaut 中使用 MyBatis 与关系型数据库集成？
9. 如何在 Micronaut 中定义 MyBatis mappers？
10. 如何在 Micronaut 中使用 MyBatis 执行 CRUD 操作？
11. 如何在 Micronaut 中与 NoSQL（MongoDB）数据库集成？
12. 如何在 Micronaut 中对 MongoDB 执行 CRUD 操作？

# 3 专注于 RESTful Web 服务

在任何微服务开发中，核心方面之一都是微服务如何与外部世界交互。RESTful 或 restful 已经成为构建这些服务接口的金标准。RESTful 将所有信息交换视为系统之间的资源交换。资源代表对象在传输时的状态，因此有了表述状态转移（Representational State Transfer）这一术语。

在本章中，我们将探索在 Micronaut 框架中处理这些 restful 接口的关键方面。我们将继续使用“控制器-服务-存储库”模式，并在`pet-clinic`应用程序内的微服务项目添加 restful 端点。对于这些端点的入站和出负载，我们将使用数据传输对象（DTOs）配合 MapStruct 将 DTO 映射到实体或从实体映射出来。

对于实践工作，我们将为以下微服务添加 restful 端点：

- `pet-owner`：动手操作为 pet-owner schema 对象添加 HTTP GET、POST、PUT 和 DELETE 端点。
- `pet-clinic`：动手操作为 pet-clinic schema 对象添加 HTTP GET、POST、PUT 和 DELETE 端点。
- `pet-clinic-review`：动手操作为 pet-clinic-reviews 集合添加 HTTP GET、POST、PUT 和 DELETE 端点。

在处理上述微服务时，我们将深入探讨本章的选题：

- 在 Micronaut 框架中处理 restful 微服务。
- 用于端点负载的 DTO。
- 为微服务创建 restful 端点。
- 使用 Micronaut 的 HTTP 服务器 API。

在本章结束时，你将掌握在 Micronaut 框架中处理 restful 服务的实用知识。这些知识对于处理微服务的 Web 层非常重要。此外，我们还将探索 Micronaut 框架中的 HTTP 服务器对象和客户端。

## 技术要求

本章的所有命令和技术说明都在 Windows 和 macOS 上运行。本章涵盖的代码示例可以在 GitHub 仓库中找到：`https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/master/Chapter03`。

开发环境中需要安装设置以下工具：

- Java SDK：8 版本或更高。
- Maven：如果你想使用 Maven 作为构建系统，这是可选的。但我们建议在任何开发机器上设置 Maven。下载和安装 Maven 可以在`https://maven.apache.org/download`。
- 开发 IDE：根据你的喜好，可以使用任何基于 Java 的 IDE，但为了本章使用了 IntelliJ。
- Git：下载和安装 Git 可以在`https://git-scm.com/downloads`。
- PostgreSQL：下载和安装 PostgreSQL 可以在`https://www.postgresql.org/download/`。
- MongoDB Atlas 提供高达 512 MB 存储的免费数据库服务。然而，如果偏于本地数据库，下载和安装说明可以在`https://docs.mongodb.com/manual/administration/community/`。
- Rest 客户端：可以使用 HTTP REST 客户端。

## 在 Micronaut 框架中处理 restful 微服务

为了学习 Micronaut 框架中的 restful 微服务，我们将继续处理`pet-clinic`。下表总结了我们对`pet-clinic`应用中每个微服务将进行的更改：

| 微服务名称 | 支持的 RESTFUL 端点 | 数据库类型 |
|---|---|---|
| pet-owner | HTTP get, post, put, delete | 关系型（PostgreSQL） |
| pet-clinic | HTTP get, post, put, delete | 关系型（PostgreSQL） |
| pet-clinic-reviews | HTTP get, post, put, delete | MongoDB |

表 3.1 - pet-clinic 应用中的微服务

在每个微服务中，我们将通过添加 HTTP 端点来对它们拥有的数据对象执行 CRUD 操作。在我们的讨论中，我们将关注：

- DTO：如何使用 DTO 封装 restful 端点的出站和入站负载。
- 服务：服务如何与数据库存储库交互。
- 控制器：控制器如何为 Micronaut 框架中的外部世界提供标准的 restful 接口。

在第二章“处理数据”的图 2.2 中，以下是本章每个微服务中的组件：

![](img/768b67b9430f02ca52f7bb252e4a684_99_0.png)

图 3.1 - 微服务组件

我们将遵循控制器-服务-存储库模式继续实现职责分离。对于服务和控制器之间的通信，我们将探索 DTO。我们在涵盖 DTO、服务和控制器时将以自底上的方式工作。DTO、映射器、服务控制器遵循相同的方法，因此为了保持讨论的集中，我们将针对 pet-owner 微服务。

在下一节中，我们的焦点将是 DTO。

## 使用 DTO 处理端点负载

DTO 模式源于企业应用程序架构，从根本上说，数据对象聚合并封装了要传输的数据。由于在微服务架构中，终端可能需要来自不同资源的数据（例如发票数据以及用户信息），DTO 模式在限制对微服务的调用以获取数据投影方面非常有效。DTO 也被称为组装对象，因为它们从多个实体类中组装数据。

在本节中，我们将探索如何实现和映射（到实体）DTO。在随后的章节中，我们将进一步探讨使用 DTO 作为从微服务传输和进入微服务传输数据的有效机制。我们还将查看 DTO 如何通过组装数据来减少对微服务的调用。

### 实现 DTO

为了实现一个 DTO，我们将开始为宠物所有者定义一个 DTO 类。

在你偏好的 IDE 中打开（在第二章“处理数据”中创建的）pet-owner 微服务项目。添加`com.packpub.micronaut.service.dto`包以包含所有 DTO。我们定义`OwnerDTO`如下：

```java
@Introspect
public class OwnerDTO implements Serializable {
    private Long id;
    private String firstName;
    private String lastName;
    private String address;
    private String city;
    private String telephone;
    private Set<PetDTO> pets = new HashSet<>();
    ... getters and setters
}
```

`OwnerDTO`实现了 Serializable 标记接口，以标记该 DTO 是可序列化的。此外，延续我们之前对组装模式的讨论，`OwnerDTO`还将包含一组`PetDTO`实例。

遵循类似的 POJO 模型，我们可以为 pet-owner 微服务中的其他实体定义 DTO，例如`com.packpub.micronaut.service.dto`包中的`PetDTO`、`VisitDTO`和`PetTypeDTO`。

80 完善 RESTful Web 服务

在下一节中，我们将处理将这些 DTO 映射到数据库实体的工作。

### 使用 MapStruct 定义映射器

**MapStruct**是一个代码生成器，它使用注解处理机制来实现源类和目标 Java 类之间的映射。实现的 MapStruct 代码由普通的方法调用组成，因此它是类型安全且易于读的。由于我们不需要为这些映射编写代码，MapStruct 能够非常有效地减少源代码的体量。

为了将 DTO 映射到实体反反亦然，我们将在宠物所有者（pet-owner）微服务中使用 MapStruct。由于我们使用 Maven，将必须在`pom.xml`项目中添加以下内容：

```xml
...
<properties>
  <org.mapstruct.version>1.3.1</org.mapstruct.version>
</properties>
<dependencies>
  <dependency>
    <groupId>org.mapstruct</groupId>
    <artifactId>mapstruct</artifactId>
    <version>${org.mapstruct.version}</version>
  </dependency>
</dependencies>
```

通过将 MapStruct 导入项目，POM 将允许我们利用 MapStruct 工具包。此外，对于 Maven 编译器，我们需要在`annotationProcessorPaths`中添加 MapStruct：



```xml我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。...
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-compiler-plugin</artifactId>
      <configuration>
        ...
      </configuration>
```

## 使用 DTO 作为端点载负载 81

```xml
<annotationProcessorPaths>
  <path>
    <groupId>org.mapstruct</groupId>
    <artifactId>mapstruct-processor</artifactId>
    <version>${org.mapstruct.version}</version>
  </path>
  <!-- other annotation processors -->
</annotationProcessorPaths>
<compilerArgs>
  <arg>-DmapStruct.defaultComponentModel=jsr330</arg>
</compilerArgs>
</configuration>
</plugins>
</build>
```

POM 中的注解处理设置将引导 Java 注解处理器为标记了 MapStruct 注解的映射生成源代码。此外，在 Micronaut 框架的语境下，`jsr330` 被指定为默认组件模型（在 Spring 中，通常使用 Spring 模型）。

我们将创建一个名为 `com.packpub.micronaut.service.mapper` 的新包来包含所有的映射器接口。通过抽象出一个泛型映射器，我们可以声明以下接口：

```java
public interface EntityMapper<D, E> {
  E toEntity(D dto);
  D toDto(E entity);
  List<E> toEntity(List<D> dtoList);
  List<D> toDto(List<E> entityList);
}
```

`EntityMapper` 接口抽象了对象到对象以及列表到列表的转换方法。通过扩展此接口，我们可以轻松地定义一个接口将 `OwnerDTO` 映射到 `Owner` 实体：

```java
@Mapper(componentModel = "jsr330", uses = {PetMapper.class})
public interface OwnerMapper extends EntityMapper<OwnerDTO, Owner> {
    default Owner fromId(Long id) {
        if (id == null) {
            return null;
        }
        Owner owner = new Owner();
        owner.setId(id);
        return owner;
    }
}
```

`OwnerMapper` 接口扩展了 `EntityMapper` 并使用了 `PetMapper`。`PetMapper` 用于将一组 `PetDTO` 实例映射到 `Pet` 实体。`PetMapper` 可以使用非常相似的方法定义。

遵循相同的方法，我们可以分别为 `Pet`、`Visit` 和 `PetType` 实体定义 `PetMapper`、`VisitMapper` 和 `PetMapper`。

因此，我们已经深入研究了 DTO 及其到对应实体类的映射。在下一节中，我们将重点关注涉及 DTO 的服务更改。

### 修改服务以使用 DTOs

在第 2 章“完善数据访问”中，为了简化讨论，我们定义了直接使用实体类的服务方法。由于多种原因，这种方法是不被推荐的，包括我们最终导致了与数据库实体的耦合/耦合逻辑，或者如果一个服务需要使用多个实体，它可能会变得非常复杂。简单来说，我们必须通过将数据库实体与业务所需的数据对象解耦来分离关注点。

要在业务服务中使用 DTO，我们需要修改抽象接口。`Owner` 接口可以修改为如下使用 DTO：

```java
public interface OwnerService {
    OwnerDTO save(OwnerDTO ownerDTO);
    Page<OwnerDTO> findAll(Pageable pageable);
```

## 使用 DTO 作为端点载负载 83

```java
Optional<OwnerDTO> findOne(Long id);
void delete(Long id);
}
```

`save()` 方法被修改为保存 `OwnerDTO` 而不是 `Owner` 实体。

同样，`findAll()` 和 `findOne()` 将返回 `OwnerDTO` 而不是 `Owner`。

遵循相同的方法，我们可以修改宠物所有者微服务中其他实体的服务，即 `PetService`、`PetTypeService` 和 `VisitService`。

由于我们修改了抽象服务接口，我们也必须实现这些类。`OwnerServiceImpl` 使用 DTO 的实现如下所示：

```java
@Singleton
@Transactional
public class OwnerServiceImpl implements OwnerService {
    ... injections for OwnerRepository and OwnerMapper
    @Override
    public OwnerDTO save(OwnerDTO ownerDTO) {
        Owner owner = ownerMapper.toEntity(ownerDTO);
```

## 完善 RESTful 服务 105

```java
public void delete(Long id) {
    ownerRepository.deleteById(id);
}
```

`save()` 方法被修改为保存 `OwnerDTO` 而不是 `Owner` 实体。

同样，`findAll()` 和 `findOne()` 将返回 `OwnerDTO` 而不是 `Owner`。

遵循相同的方法，我们可以修改宠物所有者微服务中其他实体的服务，即 `PetService`、`PetTypeService` 和 `VisitService`。

由于我们修改了抽象服务接口，我们也必须实现这些类。`OwnerServiceImpl` 使用 DTO 的实现如下所示：

```java
@Singleton
@Transactional
public class OwnerServiceImpl implements OwnerService {
    ... injections for OwnerRepository and OwnerMapper
    @Override
    public OwnerDTO save(OwnerDTO ownerDTO) {
        Owner owner = ownerMapper.toEntity(ownerDTO);
    
```

```

## 为资源列表创建端点

为了为资源列表创建端点，我们可以开始通过添加 `com.micronaut.web.rest` 包来包含所有控制器。我们将在宠物所有者微服务的 `OwnerResource` 中添加获取所有所有者。

```java

@Controller("/api")

public class OwnerResource {

    ...

    @Get("/owners")

    @ExecuteOn(TaskExecutors.IO)

    public HttpResponse<List<OwnerDTO>> getAllOwners(HttpRequest request, Pageable pageable) {

        log.debug("REST request to get a page of owners");

```

## 为微服务创建 RESTful 端点 106

```java

        Page<OwnerDTO> page = ownerService.findAll(pageable);

        return HttpResponse.ok(page.getContent()).

        headers(headers ->

            PaginationUtil.generatePaginationHttpHeaders(headers, UriBuilder.of(request.getPath()), page));

    }

}

```

我们需要考虑的几点：

- `@Controller`：这是一个类型，将 `OwnerResource` 标记为 RESTful 控制器并暴露在 `/api` 基路径上。
- `@Get`：此注解用于在相对路径 `/owners` 上暴露 `getAllOwners()` 方法。
- `@ExecuteOn`：此注解指定在 I/O 线程上执行此 GET 请求。
- `HttpRequest`：`getAllOwners()` 将 `HttpRequest` 作为输入参数。通常传递 `HttpRequest` 以跟踪并记录源的详情，例如，提交请求的 IP 地址。
- `pageable`：这是 `io.micronaut.data.model` 包中的标准接口，通常用于在请求中传递分页信息，例如 `...api/owners?page=1&size=50&sort=(firstName)`。
- `HttpResponse`：`getAllOwners()` 返回 `HttpResponse`，它是一个泛型接口并体现了示例中的特定响应。在示例中，它返回 `List<OwnerDTO>`。
- `PaginationUtil`：这是 `com.packtub.micronaut.util` 包中的一个自定义类，它生成分页响应。

# 编写 RESTful Web 服务

我们可以在本地运行 `pet-owner` 服务，默认情况下，它将运行在 8080 端口。我们可以使用任何 REST 客户端并访问 `http://localhost:8080/api/owners`，并获得得到以下响应：

![](img/768b67b9430f02ca52f7bb252e4a68e4_107_0.png)

图 3.2 – 获取所有所有者

## 为微服务创建 RESTful 端点

如上一个截图所示，当我们调用获取所有所有者的端点时，我们没有传递任何分页信息来获取所有所有者。因此，它将从数据库中检索所有所有者及其宠物信息。

### 创建用于获取特定资源的端点

为了创建一个用于获取特定资源的端点，我们将在 `OwnerResource` 中添加一个方法来获取特定的所有者，如下：

```java

@Get("/owners/{id}")

@ExecuteOn(TaskExecutors.IO)

public HttpResponse<Optional<OwnerDTO>> getOwner(@PathVariable Long id) {

    log.debug("REST request to get Owner : {}", id);

    return ownerService.findOne(id);

}

```

这里有几点我们需要深思：

- 1. `@PathVariable`：这用于指定并匹配 HTTP 调用中的路径变量。在之前的示例中，我们正将所有者 ID 作为路径变量传递。
- 2. `Optional`：在这个示例中，我们返回了一个可选对象。如果服务能找到指定 ID 的所有者，将发送 HTTP 200 响应；否则，将返回 HTTP 404。

我们可以在本地运行 `pet-owner` 服务，默认情况下，它将运行在 8080 端口。我们可以使用任何 REST 客户端并通过访问 `http://localhost:8080/api/owners/1`，我们将得到以下响应：

### 请求

| Method | 请求 URL |
|---|---|
| GET | http://localhost:8080/api/owners/1 |

参数

```json

{

  "id": 1,

  "firstName": "George",

  "lastName": "Franklin",

  "address": "110 W. Liberty St.",

  "city": "Madison",

  "telephone": "6085551023",

  "pets": Array[1] [

    {

      "id": 1,

      "name": "Leo",

      "birthDate": Array[3] [2010, 9, 7],

      "type": {

        "id": 1,

        "name": "cat"

      }

    }

  ]

}

```

图 3.3 – 获取特定的所有者

## 为微服务创建 RESTful 端点

`OwnerDTO` 也封装了宠物数据，因此响应负载完整获取了 ID 为 1 的所有者的详细信息。此外，如果向后续 HTTP 请求传递了任何不存在的 ID，将导致 HTTP 404：

```text
Request URL

GET http://localhost:8080/api/owners/123789
```

```text
404 Not Found 25.27 ms
```

```json

{

  "message": "Page Not Found",

  "links": {

    "href": "/api/owners/123789",

    "templated": false

  }

}

```

图 3.4 – 获取一个不存在的所有者

在之前的 API 调用中，我们尝试获取 ID 为 123789 的所有者，但由于我们没有此 ID 的所有者，结果导致了 HTTP 404 not found 响应。

### 创建用于插入资源的端点

为了创建一个插入资源的端点，我们将在 `OwnerResource` 中添加一个 HTTP POST 方法，如下：

```java

@Post("/owners")

@ExecuteOn(TaskExecutors.IO)

public HttpResponse<OwnerDTO> createOwner(@Body OwnerDTO ownerDTO) throws URyntaxException {

  if (ownerDTO.getId() != null) {

```

# 编写 RESTful Web 服务

```java

throw new BadRequestAlertException("A new owner cannot

already have an ID", ENTITY_NAME, "idexists");

}

OwnerDTO result = ownerService.save(ownerDTO);

URI location = new URI("/api/owners/" + result.getId());

return HttpResponse.created(result).headers(headers -> {

    headers.location(location);

    HeaderUtil.createEntityCreationAlert(headers,

applicationName, true, ENTITY_NAME, result.getId().toString());

});

...

```

这里有几点需要注意：

- 1. `@Post`：`createOwner()` 使用 `@Post` 注解暴露为 HTTP POST API。
- 2. `@ExecuteOn`：此注解指定在 I/O 线程池上执行此 POST 请求。
- 3. `@Body`：`@Body` 注解指定 `createOwner()` 中的 `ownerDTO` 方法参数绑定到传入的 HTTP POST 请求体上。
- 4. 非空检查：使用 `if` 结构，我们快速检查 HTTP 请求体是否包含一个已定义 ID 的负载。这是一种业务验证的断言情况，如果失败，则 API 将抛出坏请求异常。
- 5. `HttpResponse.created`：在理想路径（happy path）场景下，API 将返回 HTTP 201 created。此响应表示请求执行成功。

我们可以在本地运行 `pet-owner` 服务，并如下所示发送 POST 请求：

为微服务创建 RESTful 端点

### 请求

| Method | 请求 URL |
|---|---|
| POST | http://localhost:8080/api/owners |

参数

| Headers | Body |
|---|---|
| Content-Type application/json | ```json

{

  "firstName": "George",

  "lastName": "Franklin",

  "address": "110 W. Liberty St.",

  "city": "Madison",

  "telephone": "6085551023"

}

``` |

```text
201 Created 66 ms
```

图 3.5 – 插入一个所有者

图 3.6 – 插入一个所有者

在之前的 HTTP 调用中，我们传递了一个所有者对象进行插入。正如预期的那样，调用成功并返回了 HTTP 201。此外，如果我们尝试创建一个已经拥有该 ID 的所有者，将会失败：

```text
Internal Server Error: A new owner cannot already have an ID
```

## 更新资源的端点

为了创建一个更新资源的端点，我们将在 `OwnerResource` 中添加 PUT 方法，如下：

```java

@Put("/owners/{id}")
```



@ExecuteOn(TaskExecutors.IO)

public HttpResponse<OwnerDTO> updateOwner(@Body OwnerDTO ownerDTO) throws SyntaxException {

    log.debug("REST request to update Owner : {}", ownerDTO);

    if (ownerDTO.getId() == null) {

        throw new BadRequestAlert("Invalid id", ENTITY_NAME);

    }

    OwnerDTO result = ownerService.save(ownerDTO);

    return HttpResponse.ok(result).headers(headers -> {

        HeaderUtil.createEntityUpdateAlert(headers,

        true, ENTITY_NAME, result.getId());

    });

}

```

## 更新资源

这里有几点需要深思：

- 1. `@Put`：`updateOwner()` 使用 `@Put` 注解暴露为 HTTP PUT API。
- 2. `@ExecuteOn`：此注解指定在 I/O 线程池上执行此 PUT 请求。
- 3. `@Body`：`@Body` 注解指定 `updateOwner()` 中的 `ownerDTO` 参数绑定到传入的 HTTP PUT 请求体上。
- 4. 空检查：使用 `if` 结构，我们快速检查 ID 是否为空。如果 ID 为空，则 API 将抛出异常。
- 5. `HttpResponse.ok`：在理想路径场景下，API 将返回 HTTP 200。此响应表示请求执行成功。

我们可以在本地启动 `pet-owner` 微服务，并在 REST 客户端中发送 PUT 请求，如下：

![](img/768b67b9430f02ca52f7bb252e4a68e4_115_0.png)

![](img/768b67b9430f02ca52f7bb252e4a68e4_115_1.png)

```json

{

  "id": 39,

  "firstName": "Sam",

  "lastName": "Potterman",

  "address": "120 King St.",

  "city": "New York",

  "telephone": "6085551023"

}

```

200 OK 65.45 ms DETAILS

```json

{

  "id": 39,

  "firstName": "Sam",

  "lastName": "Potterman",

  "address": "120 King St.",

  "city": "New York",

  "telephone": "6085551023"

}

```

图 3.7 – 更新所有者

在 HTTP PUT 请求中，我们请求更新之前刚刚插入的资源。我们正在更新该资源的地址和城市。正如预期的那样，请求执行成功并返回了 HTTP 200 响应。如果我们尝试更新一个 ID 为 null 的资源，它将会失败：

![](img/768b67b9430f02ca52f7bb252e4a68e4_116_0.png)

在之前的 HTTP PUT 调用中，我们尝试更新一个 ID 为 null 的所有者（owner）。系统抛出了 HTTP 500 内部服务器错误，消息为 – `Internal Server Error: Invalid id`。

### 创建删除资源的端点

为了演示删除资源的操作，我们可以为 `OwnerResource` 添加一个 HTTP DELETE 方法，如下所示：

```java

...

@Delete("/owners/{id}")

@ExecuteOn(TaskExecutors.ID) {

    log.debug("REST request to delete Owner: {}", id);

    ownerService.delete(id);

    return HttpResponse.noContent().headers(headers ->

        HeaderUtil.createEntityDeletionAlert(headers, applicationName,

true, ENTITY_NAME, id.toString()));

}

```

这里有几点需要考虑：

- `@Delete`：`@Delete` 注解将 `deleteOwner()` 方法暴露为一个 HTTP DELETE API。
- `@ExecuteOn`：该注解指定在 I/O 线程池上执行此 PUT 请求。
- `@PathVariable`：`@PathVariable` 将 ID 参数绑定到 HTTP 请求 URL 中指定的变量。
- `.noContent`：在理想路径（happy path）场景下，API 将返回 HTTP 204。这表示请求执行成功，且响应负载中没有额外内容。

我们可以在本地启动 `pet-owner` 微服务，并在 REST 客户端中发送 HTTP DELETE 请求：

![](img/768b67b9430f02ca52f7bb252e4a68e4_117_0.png)

## 使用 Micronaut 的 HTTP 服务器 API

我们请求删除在之前的示例中插入/更新的所有者。正如预期的那样，请求成功了，并返回了 HTTP 204 响应。

到为止，我们已经探索了如何创建所有类型的 RESTful 端点。这段讨论为我们进入 Micronaut 的服务器 API 铺平了道路。在下一节中，我们将涵盖利用这些服务器 API 的实用方面。

## 使用 Micronaut 的 HTTP 服务器 API

Micronaut 框架提供了一个基于 Netty 的非阻塞 HTTP 服务器。这些服务器 API 可用于处理一些实用的微服务场景。为了进行实际操作，我们将继续使用 `pet-owner` 微服务。

在开始之前，必须在项目 POM 中包含以下 Maven 依赖项：

```xml

...

<dependency>

<groupId>io.micronaut</groupId>

<artifactId>micronaut-http-server-netty</artifactId>

<scope>compile</scope>

</dependency>

...

```

该依赖项应该存在于 `pet-owner` 项目中。在后续章节中，我们将探索 HTTP 服务器领域中一些常用的配置。

### 在 Micronaut 框架中绑定 HTTP 请求

有几种方法可以在 Micronaut 框架中将参数绑定到 HTTP 请求：

- `@Body`：如前所述，`@Body` 从 HTTP 请求体（body）中绑定参数。
- `@CookieValue`：这从 HTTP 请求的 cookie 值中绑定参数。
- `@Header`：这从 HTTP 请求的标头（header）中绑定参数。
- `@QueryValue`：这从 HTTP 请求的查询参数（query parameter）中绑定参数。
- `@PathVariable`：这从 HTTP 请求的路径（path）中绑定参数。

## 构建 RESTful Web 服务

- `@Part`：在多部分（multi-part）HTTP 请求中，这将参数绑定到某个部分。
- `@RequestBean`：这将任何对象（HTTP 请求）绑定到 Java Bean。

除了上述的 HTTP 请求绑定，Micronaut 框架支持多个 URI 模板。这些模板对于创建各种类型的 RESTful 资源非常有用。考虑到 `owner` 资源，我们可以在 Micronaut 中支持以下 URI 模板匹配：

| URI 模板 | 描述 | 示例 |
| --- | --- | --- |
| `/owners/(ID)` | 根据匹配的 ID 获取所有者资源。 | `/owners/1` |
| `/owners/(ID:4)` | 获取最多四位数字的所有者资源。其中 ID 可以取任意值。 | `/owners/321` |
| `/owners/(ID)` | 获取所有者，如果提供了 ID（可选），则匹配指定 ID 的所有者。 | `/owners` 或 `/owners/1` |
| `/owners/(?(pageNumber, pageSize)` | 获取所有者，如果指定了可选查询参数，则根据查询参数过滤并处理请求。 | `/?pageNumber=10,pageSize=10,locale=fr` |
| `/owners/(ID:regex)` | 根据匹配的 ID 获取所有者资源，其中 ID 只能根据正则取值。 | `/owners/1` |
| `/owners/(ID:[0-9]+)` | | |

表 3.2 – Micronaut 框架中的 URI 模板

在前面的表中，我们可以看到匹配/限制传入 HTTP 请求的各种方法，以及每种方法对特定资源可以实现什么功能。在下一节中，我们将讨论如何验证 HTTP 请求中的数据。

### 验证数据

Micronaut 框架同时支持 JSR 380 验证和 Hibernate Bean 验证。默认情况下，Micronaut 项目通常包含以下内容：

- `@NotNull`：断言参数不为 null。
- `@NotEmpty`：断言参数不为空。
- `@Min`：断言值大于或等于指定值。
- `@Max`：断言值小于或等于指定值。
- `@Valid`：验证对象图。

如果未满足任何这些验证条件，将抛出 `ConstraintViolationException`。

### 处理错误

Micronaut 框架对请求生命周期内产生的各种异常提供了良好的覆盖。标准异常处理器可以在 `micronaut.server.exceptions` 中找到。默认提供了以下处理器：

- `ContentLengthExceeded`：处理 `ContentLengthExceededException` 并返回 `REQUEST_ENTITY_TOO_LARGE`。
- `ConversionErrorHandler`：处理 `ConversionErrorException` 并返回 `BAD_REQUEST`。
- `HttpStatusHandler`：处理 `HttpStatus` 中指定的 `HttpStatusException`。
- `JsonExceptionHandler`：处理 `JsonProcessingException` 并返回 `BAD_REQUEST`。
- `UnsatisfiedArgumentHandler`：处理 `UnsatisfiedArgumentException` 并返回 `BAD_REQUEST`。
- `URISyntaxHandler`：处理 `URISyntaxException` 并返回 `BAD_REQUEST`。

除了上述标准异常和异常处理器，我们还可以创建自定义的异常和异常处理器。

## 构建 RESTful Web 服务

我们可以假设有一个由微服务抛出的假设 `FooException`：

```java

public class FooException extends RuntimeException {

  ...

}

```

`FooException` 继承自 `RuntimeException`，使其成为一个未检查异常，我们可以创建 `FooExceptionHandler` 来处理此异常：

```java

@Produces

@Singleton

@Requires(classes = {FooException.class, ExceptionHandler.class})

public class FooExceptionHandler implements ExceptionHandler<FooException, HttpResponse> {

  @Override

  public HttpResponse handle(HttpRequest request, FooException exception) {

    JsonError error = new JsonError(exception.getMessage());

    error.path('/' + exception.getArgument().getName());

    error.link(Link.SELF, Link.of(request.getUri()));

    return HttpResponse.status(HttpStatus.INTERNAL_SERVER_ERROR).body(error);

  }

}

```

版本控制默认是不支持的，要启用版本控制，我们必须在 `application.yml` 中进行以下更改：

```yaml

micronaut:

  application:

    name: Pet-Owner

  router:

    versioning:

      enabled: true

      default-version: 1

```

在配置中，我们启用了版本控制。默认情况下，如果没有指定版本，则传入的请求将由版本 1 的 API 服务。

为了演示版本控制，我们在 `pet-owner` 微服务的 `OwnerResource` 类的 `getOwner()` 方法上添加了 `@Version` 注：

```java

@Version("1")

@Get("/owners/{id}")

@ExecuteOn(Executors.IO)

public Optional<OwnerDTO> getOwner(@PathVariable Long id) {

  log.debug("REST request to get Owner : {}", id);

  return ownerService.findOne(id);

}

```

```java

@Version("2")

@Get("/owners/{id}")

@ExecuteOn(Executors.IO)

public Optional<OwnerDTO> getOwnerV2(@PathVariable Long id) {

  log.debug("REST request to get Owner : {}", id);

  return ownerService.findOne(id);

}

```

`@Version` 允许 `getOwner()` 方法有多个投影。该注解在支持事件驱动的微服务时非常有用。

# 编写 RESTful Web 服务

为了测试这些更改，我们可以在本地运行 `pet-owner` 并使用高级 REST 客户端对 `getOwner()` 进行调用：

![](img/768b67b9430f02ca52f7bb252e4a68e4_123_0.png)

图 3.10 - 调用带标识的 API

在之前的 HTTP 调用中，我们使用 `X-API-VERSION` 头部指定了版本。根据该标头中指定的值，此调用将由版本 2 的 API 服务。

到为止，我们已经探索了如何在 Micronaut 框架中利用 HTTP 服务器 API。在下一节中，我们将关注 HTTP 客户端方面。

# 使用 Micronaut 的 HTTP 客户端 API

Micronaut 的 HTTP 客户端是一个基于 Netty 的非阻塞客户端，内置了服务发现和负载均衡等云功能。这种自定义实现通过微服务架构增强了标准的 HTTP 客户端。

为了演示基本的 HTTP 调用，我们将为 `pet-owner` 微服务中的 `OwnerResource` 创建一个 HTTP 客户端。首先，我们必须在 `pom.xml` 项目中拥有 `micronaut-http-client` 依赖：

```xml

...

<dependency>

  <groupId>io.micronaut</groupId>

  <artifactId>micronaut-http-client</artifactId>

  <scope>compile</scope>

</dependency>

...

```

`micronaut-http client` 封装了所有与 HTTP 客户端相关的 API，例如创建 `HttpClient`、执行所有 HTTP 操作以及处理处理响应负载。

接下来，我们将探索如何利用 `micronaut-http-client` 在我们之前创建的端点上执行各种 HTTP 操作。

# 执行 HTTP PUT 操作

要执行 HTTP PUT 操作，我们可以创建 `OwnerResourceClient`。该客户端可以封装在 `com.packtpub.micronaut.web.rest` 包中。

我们可以添加以下方法来执行 HTTP 调用：

```java

public List<OwnerDTO> getAllOwners() throws MalformedURLException {

  HttpClient client = HttpClient.create(new URL("https://" + server.getHost() + ":" + server.getPort()));

  OwnerDTO[] owners = client.toBlocking().

  retrieve(HttpRequest.GET("/api/owners"), OwnerDTO[].class);

  return List.of(owners);

}

```

`HttpClient.create()` 将创建一个 HTTP 客户端，然后我们用它发送 HTTP GET 请求。

### 执行 HTTP POST 操作

要执行 HTTP POST 操作，我们可以在 `OwnerResourceClient` 中添加以下方法：

```java

public OwnerDTO createOwnerClient() throws

URLException {



```java
HttpClient client = HttpClient.create(new URL("https://" + 
server.getHost() + ":" + server.getPort()));

OwnerDTO newOwner = new OwnerDTO();

newOwner.setFirstName("Lisa");

newOwner.setLastName("Ray");

newOwner.setAddress("100 Queen St.");

newOwner.setCity("Toronto");

newOwner.setTelephone("1234567890");

return client.toBlocking().retrieve(HttpRequest.POST("/api/owners", newOwner), OwnerDTO.class);

}
```

`HttpClient.create()` 将创建一个 HTTP 客户端，然后我们用它发送 HTTP POST 请求。所有者对象将作为请求负载传递。

# 执行 HTTP PUT 操作

要执行 HTTP PUT 操作，我们可以在 `OwnerResourceClient` 中添加以下方法：

```java
public OwnerDTO updateOwnerClient() throws
URLException {

    HttpClient client = HttpClient.create(new URL("https://" + 
    server.getHost() + ":" + server.getPort()));

    OwnerDTO owner = new OwnerDTO();

    owner.setId(1L);

    owner.setAddress("120 Queen St.");

    return client.toBlocking().retrieve(HttpRequest.PUT("/api/owners", owner), OwnerDTO.class);

}
```

# 总结 105

`HttpClient.create()` 将创建一个 HTTP 客户端，我们然后用它发送 HTTP PUT 请求。所有者对象将作为请求负载传递。

# 执行 HTTP DELETE 操作

要执行 HTTP DELETE 操作，我们可以在 `OwnerResourceClient` 中添加以下方法：

```java
public Boolean deleteOwnerClient() {

    HttpClient client = HttpClient.create(new URL("https://" + 
    server.getHost() + ":" + server.getPort()));

    return client.toBlocking().retrieve(HttpRequest.DELETE("/api/owners", Boolean.class);

}
```

- Rest client：可以使用任何 HTTP REST 客户端。我们使用了 Advanced REST Client Chrome 插件。
- Docker：下载和安装 Docker 的指令可以在 <https://docs.docker.com/get-docker/> 找到。
- OpenSSL：下载和安装 OpenSSL 的指令可以在 <https://www.openssl.org/source/> 找到。

## 在 Micronaut 框架开发 RESTful 微服务

为了深入研究 Micronaut 框架的安全性，我们将继续对 pet-clinic 应用进行开发。下表总结了我们将为了保护应用程序中的每个微服务而将进行的更改：

| 微服务名称 | 身份验证策略 | 身份提供者 |
| --- | --- | --- |
| pet-owner | Session | Local |
| pet-clinic | JWT | Keycloak |
| pet-clinic-reviews | OAuth | 云 SaaS 身份提供者 (Okta) |

表 4.1 - pet-clinic 应用中微服务的安全保护

为了保护微服务中的目标端点，我们将关注以下两个关键方面：

- **身份提供者 (Identity provider)**：本质上，身份提供者负责存储和维护数字身份的相关事务。此外，它通过对提交的数字身份与其存储的身份库进行验证，来解决任何安全主张。
- **身份验证策略 (Authentication strategy)**：身份验证策略将决定微服务如何与身份提供者通信，以验证用户请求并进行授权。

在第 3 章“开发 Restful Web 服务”的组件图的基础上，以下是本章每个微服务中的更改：

![微服务组件](img/768b67b9430f02ca52f7bb252e4a68e4_131_0.png)

图 4.1 – 微服务组件

我们将坚持通常的关注点分离模式。我们将在每个微服务中结合使用身份提供者和身份验证策略。

在下一节中，我们的重点将介绍 Micronaut 框架提供的开箱即用的安全工具。

## Micronaut 安全基础

为了处理任何安全方面，Micronaut 框架内置了一个 `SecurityFilter` 对象。`SecurityFilter` 对象拦截任何传入的 HTTP 请求，并按照应用程序的配置启动身份验证/授权过程。在图中，你可以看到 `SecurityFilter` 对象中授权用户请求的工作流：

![Micronaut 安全过滤器](img/768b67b9430f02ca52f7bb252e4a68e4_132_0.png)

图 4.2 – Micronaut 安全过滤器

Micronaut 的 `SecurityFilter` 有三个核心组成部分：

- **AuthenticationFetcher**：`AuthenticationFetcher` 将获取用于验证用户请求所需的下游身份验证器。
- **Authenticator**：`Authenticator` 注入配置的身份验证提供者（者）和安全配置，用于验证用户请求。将根据身份验证操作的成功或失败创建一个 `AuthenticationResponse` 对象。
- **SecurityRule**：如果身份验证成功，安全过滤器将进一步调用安全规则。应用程序可以使用开箱即用的安全规则（如 `SecuredAnnotationRule` 或 `IpPatternsRule`）或通过扩展 `AbstractSecurityRule` 创建自己的安全规则来配置一个或多个安全规则。如果请求满足所有安全规则，安全过滤器将返回一个成功的 `AuthenticationResponse`；否则返回一个失败的 `AuthenticationResponse`。

通过利用 `SecurityFilter`，在下一节中，我们将关注如何使用 Micronaut 框架中的会话身份验证来保护微服务。

## 使用会话身份验证保护服务端点

在基于会话的身份验证中，用户状态存储在服务器端。当用户登录服务器时，服务器启动会话并在 Cookie 中发布会 ID。服务器使用会 ID 唯一地识别会话。任何后续的用户请求必须将此会 ID 作为 Cookie 传递以恢复会话：

![基于会话的身份验证](img/768b67b9430f02ca52f7bb252e4a68e4_133_0.png)

图 4.3 - 基于会话的身份验证

所示，在基于会话的身份验证策略中，服务器负责跟踪会话的主要工作。客户端必须提供有效的会 ID 来恢复会话。

为了学习如何使用基于会话的身份验证保护微服务，将在 pet-owner 微服务上进行实验。首先，我们需要通过向 `pom.xml` 项目添加以下依赖项来启用安全性：

```xml
<!-- Micronaut security -->

<dependency>
  <groupId>io.micronaut.security</groupId>
  <artifactId>micronaut-security</artifactId>
</dependency>

<dependency>
  <groupId>io.micronaut.security</groupId>
  <artifactId>micronaut-security-session</artifactId>
</dependency>
```

通过导入 `micronaut-security` 和 `micronaut-security-session` 依赖，我们可以在 pet-owner 微服务中使用会话身份验证工具包。一旦导入了这些依赖，我们需要按照下一个代码块所示配置 `application.properties`：

```yaml
security:
  enabled: true
  authentication: session

session:
  enabled: true

# Auth 端点
endpoints:
  login:
    enabled: true
  logout:
    enabled: true
```

如前面的 `application.properties` 实例所示，我们将通过将 `enabled` 设置为 true 并指定 `session` 为身份验证策略来启用安全性。此外，Micronaut 安全工具包开箱即提供了 `LoginController` 和 `LogoutController`。由于我们为这些控制器指定了自定义路径，它们将分别通过默认路径 ...login 和 ...logout 访问。

我们将使用一个基本的身份提供者，它将利用应用程序属性来存储用户数据。这非常原始，但有助于学习和探索。让我们在 `application.properties` 中添加一些用户数据：

```yaml
identity-store:
  users:
    alice: password1
    bob: password2
    charlie: password3
```

## 保护微服务

```yaml
roles:
  alice: ADMIN
  bob: VIEW
  charlie: VIEW
```

我们添加了三个用户：alice、bob 和 charlie。每个用户还为 pet-owner 微服务分配了一个角色。

在下一节中，我们将探索如何实现一个使用配置的应用程序属性获取用户数据的身份验证提供者。

## 实现基础身份验证提供者

为了实现基础身份验证提供者，我们将开始创建 `com.packpub.micronaut.security` 包。该包将包含所有涉及安全的构制品。

我们首先向此包中添加 `IdentityStore`：

```java
@ConfigurationProperties("identity-store")
public class IdentityStore {

    @MapFormat
    Map<String, String> users;

    @MapFormat
    Map<String, String> roles;

    public String getPassword(String username) {
        return users.get(username);
    }

    public String getUserRole(String username) {
        return roles.get(username);
    }

}
```

`IdentityStore` 类映射到应用程序属性以访问用户数据。

我们可以利用这个身份存储器实现身份验证提供者，如下代码段所示：

```java
@Singleton
public class LocalAuthProvider implements AuthenticationProvider {

    @Inject
    IdentityStore store;

    @Override
    public Publisher<AuthenticationResponse> authenticate(
        HttpRequest httpRequest,
        AuthenticationRequest authenticationRequest) {

        String username =
            authenticationRequest.getIdentity().toString();

        String password =
            authenticationRequest.getSecret().toString();

        if (password.equals(store.getPassword(username))) {
            UserDetails details = new UserDetails(
                (username, Collections.singletonList(
                    store.getUserRole(username))));

            return Flowable.just(details);
        } else {
            return Flowable.just(new AuthenticationFailed());
        }

    }

}
```

# 微服务的安全防护

`LocalAuthProvider` 通过具体实现 `authenticate()` 方法实现了标准的 `AuthProvider` 接口。在 `authenticate()` 方法中，我们只需检查用户请求中指定的身份标识和密钥是否与身份存储器中的任何用户名和密码匹配。如果找到匹配项，我们返回 `UserDetails` 对象；否则，返回 `AuthenticationFailed`。

在接下来的章节中，我们将重点关注如何为 `pet-owner` 端点配置授权。

# 为服务端点配置授权

在微服务的用户需求中，通常会有既需要匿名访问也需要安全访问的场景。首先，我们将为 `PetResource` 和 `VisitResource` 提供匿名访问。

在 Micronaut 安全中，提供匿名访问有两种方式：

- 使用 `@Secured(SecurityRule.IS_ANONYMOUS)`
- 在应用属性（application properties）中配置 `intercept-url-map`

在接下来的几个章节中，我们将深入研究这两种方法。

# 使用 SecurityRule.IS_ANONYMOUS 授予匿名访问

Micronaut 安全内置了访问安全规则。要为整个控制器授予访问或将其限制在特定的端点，我们可以简单地使用 `@Secured` 注解。在 `PetResource` 中，我们通过此注解在控制器级别为所有端点提供了匿名访问：

```java
@Controller("/api")
@Secured(SecurityRule.IS_ANONYMOUS)
public class PetResource {

}
```

使用 `@Secured(SecurityRule.IS_ANONYMOUS)` 允许访问所有 `PetResource` 端点。我们可以直接启动服务并尝试任何 `PetResource` 端点。你可以使用任何 REST 客户端来访问该端点。在后续的截图中，你会注意到我们是如何使用 REST 客户端发起 HTTP GET 请求的：

### 请求

| 方法 | 请求 URL |  |
| --- | --- | --- |
| GET | http://localhost:8081/api/pets | SEND |

200 OK 2211.73 ms DETAILS

```json
Array[13] [
  {
    "id": 1,
    "name": "Leo",
    "birthDate": [Array[3]
      0: 2010,
      1: 9,
      2: 7
    ],
    "type": {
      "id": 1,
      "name": "cat"
    }
  },
  {
    "id": 2,
    "name": "Basil",
    "birthDate": [Array[3]
      0: 2012,
      1: 8,
      2: 6
    ],
    "type": {
      "id": 6,
      "name": "hamster"
    }
  },
  {
    "id": 3,
    "name": "Rosy",
    "birthDate": [Array[3]
      0: 2011,
      1: 4,
      2: 17
    ]
  }
]
```

图 4.4 – 对宠物的匿名访问

如之前的截图所示，我们可以匿名访问 `PetResource`，因为它已经通过 `@Secured(SecurityRule.IS_ANONYMOUS)` 配置了匿名访问。

在下一节节中，我们将看到如何使用应用属性来授予匿名访问。

# 使用应用属性授予匿名访问

我们也可以使用应用属性为控制器或控制器中的特定端点配置匿名访问。在以下代码段中，我们正在为 `.../api/visits` 端点配置匿名访问：

```yaml
### 拦截规则

intercept-url-map:
  pattern: /api/visits
  access: isAnonymous()
```



在应用属性中，我们配置了任何指向`...api/visits`的用户请求都应被授予匿名访问。这将允许所有用户（已认证和未认证的）访问`VisitResource`。

为了快速测试我们是否可以访问`.../api/vist`，我们可以尝试：

### 请求

| 方法 | 请求 URL | | |
| --- | --- | --- | --- |
| GET | `http://localhost:8081/api/visits` | SEND | |

`200 OK 2211.73 ms DETAILS`

```json
Array[13] [
  {
    "id": 1,
    "name": "Leo",
    "birthDate": [Array[3]
      0: 2010,
      1: 9,
      2: 7
    ],
    "type": {
      "id": 1,
      "name": "cat"
    }
  },
  {
    "id": 2,
    "name": "Basil",
    "birthDate": [Array[3]
      0: 2012,
      1: 8,
      2: 6
    ],
    "type": {
      "id": 6,
      "name": "hamster"
    }
  },
  {
    "id": 3,
    "name": "Rosy",
    "birthDate": [Array[3]
      0: 2011,
      1: 4,
      2: 17
    ]
  }
]
```

# 使用 JWT 认证保护服务端点

![](img/768b67b9430f02ca52f7bb252e4a68e4_146_0.png)

图 4.10 – 在 Keycloak 服务器中创建客户端

Keycloak 服务器将在默认的 `master` realm 中创建 `pet-clinic` 客户端。接下来，我们将为该客户端空间设置用户。

## 在客户端空间中设置用户

用户设置将允许我们使用这些身份作为测试用户（当然，稍后可以配置实际用户）。我们将从创建角色开始。对于 `pet-clinic` 微服务，我们将定义两个角色：`pet-clinic-admin` 和 `pet-clinic-user`。要创建角色，请按照接下来的指令说明操作：

1. 在主菜单上选择 `Roles`（角色）。
2. 点击 `Add Role`（添加角色）按钮。
3. 提供角色名称并点击 `Save`（保存）按钮。

## 保护微服务

我们将添加三个用户——`Alice`（管理员）、`Bob`（用户）和 `Charlie`（用户）。要添加用户，请按照接下来的指令说明操作：

1. 在主菜单上选择 `Users`（用户）并点击 `Add User`（添加用户）。
2. 提供用户名并使用默认设置。点击 `Save`（保存）按钮。
3. 用户创建后，进入 `Credentials`（凭据）标签页指定密码并将 `Temporary`（临时）标记改为关闭。点击 `Reset Password`（重置密码）按钮。
4. 要配置用户-角色，进入 `Role Mappings`（角色映射）标签页并选择所需的角色。更改将自动保存。

重复上述指令以将 `Alice` 设置为 `pet-clinic-admin`，`Bob` 设置为 `pet-clinic-user`，`Charlie` 设置为 `pet-clinic-user`。

为了在 Keycloak 中显示这些角色数据，我们需要进行以下更改：

1. 在主菜单上选择 `Client Scopes`（客户端范围）选项。
2. 在列出的选项中选择 `Roles`（角色）。
3. 进入角色的 `Mappers`（映射器）并选择 `Realm Roles`（领域/域角色）。
4. 按照下方截图所示的高亮内容提供输入：

![](img/768b67b9430f02ca52f7bb252e4a68e4_147_0.png)

图 4.11 - 配置 Realm Roles 映射器

一旦创建了用户并分配了角色，我们就可以修改 `pet-clinic` 微服务。在下一节中，我们将深入研究如何使用 Keycloak 身份提供者基于令牌的认证来保护 `pet-clinic`。

## 使用基于令牌的认证保护 pet-clinic 微服务

为了保护 `pet-clinic` 微服务，我们首先需要在 `pom.xml` 项目中通过添加以下依赖来启用安全功能。

```xml
<!-- Micronaut security -->
<dependency>
  <groupId>io.micronaut.security</groupId>
  <artifactId>micronaut-security</artifactId>
  <version>${micronaut.version}</version>
</dependency>

<dependency>
  <groupId>io.micronaut.security</groupId>
  <artifactId>micronaut-security-jwt</artifactId>
  <version>${micronaut.version}</version>
</dependency>

<dependency>
  <groupId>io.micronaut.security</groupId>
  <artifactId>micronaut-security-oauth2</artifactId>
  <version>${micronaut.version}</version>
</dependency>
```

通过导入 `micronaut-security` 和 `micronaut-security-jwt` 依赖，我们可以在 `pet-clinic` 微服务中利用令牌认证工具包。我们将使用 OAuth 2 与 Keycloak 服务器集成。一旦导入了这些依赖，我们还需要按照如下方式配置 `application.properties`：

```yaml
security:
  authentication: idtoken
  endpoints:
    login:
      enabled: true
```

```yaml
redirect:
  login-success: /secure/anonymous
token:
  jwt:
    enabled: true
    signatures.jwks.keycloak:
      url: http://localhost:8888/auth/realms/master/openid-connect/certs
auth2.clients.keycloak:
  grant-type: password
  client-id: pet-clinic
  client-secret: XXXXXXXX
authorization:
  url: http://localhost:8888/auth/realms/master/openid-connect/auth
token:
  url: http://localhost:8888/auth/realms/master/openid-connect/token
  auth-method: client_secret
```

在 `application properties` 中，`client-id` 和 `client-secret` 必须从 Keycloak 复制。`Client secret` 可以通过 `Credentials` 标签页复制。此外，授权和令牌的 URL 是标准的，但你可以访问 `http://localhost:8888/auth/realms/master/.well-known/openid-configuration`。

在下一节中，我们将关注如何使用基于令牌的认证策略和 Keycloak 身份服务器授予端点授权访问。

## 使用 Keycloak 身份提供者授予授权访问

为了授予授权访问，可以使用 `@Secured`。在动手示例中，我们将使用 `@Secured` 注解为 `VetResource` 授予授权访问，如下：

```java
@Controller("/api")
@Secured(AUTHENTICATED)
public class VetResource {
}
```

`VetResource` 内的所有端点仅授予授权访问。如果我们尝试访问 `/api/vets` 端点，微服务将返回拒绝响应：

```http
Request
Method: GET
URL: http://localhost:8082/api/vets
Host: localhost:8082
Accept: */
User-Agent: Postman/7.2.4

HTTP/1.1 401 Unauthorized
Content-Type: application/json
Content-Length: 35
Access-Control-Allow-Origin: *

{"error": "No valid token"}
```

图 4.12 – 未认证访问 vets

如上所示，如果不指定有效令牌访问任何 `vet` 端点，微服务将返回 HTTP 401 Unauthorized。

为了成功访问 `vet` 端点，我们需要获取有效的 JWT。我们可以使用内置控制器登录。只需向 `/login` 路径发送 POST 请求。如果请求成功，响应中将发送包含 JWT 的 Cookie，如下方的截图所示：

```http
GET /api/vets HTTP/1.1
Host: localhost:8082
Accept: */
User-Agent: Postman/7.2.4

HTTP/1.1 401 Unauthorized
Content-Type: application/json
Content-Length: 35
Access-Control-Allow-Origin: *
```



图我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。4.13 – 获取授权访问的 Cookie

# 保护微服务

如截图所示，我们使用正确的用户名和密码向`/login`端点发送`post`请求。服务将使用 Keycloak 身份提供者授予授权访问并返回带有 JWT 的 Cookie。

从前面的响应中复制 JWT 部分。我们可以将此令牌传递给`VetResource`的任何请求。在接下来的图中，我们使用刚刚获取的 JWT 调用`/api/vets`端点：

![](img/768b67b9430f02ca52f7bb252e4a68e4_151_0.png)

图 4.14 – 使用令牌进行授权访问

由于我们在请求头中传递了有效令牌，服务将验证该令牌并成功返回 HTTP 200 响应。

到目前为止，我们探索了如何使用外部身份提供者的 JWT 保护微服务。在下一节中，我们将关注如何使用基于云身份提供者的 OAuth 实现微服务安全。

# 使用 OAuth 保护服务端点

OAuth 是另一种基于令牌的认证策略。它的广泛接受度、对网络安全深度广度的良好覆盖以及在客户端和服务器端管理用户会话的灵活性，使其成为一种企业级认证机制。OAuth 规定使用令牌来建立身份，而不是传递用户名和密码。可以从外部身份提供者获取令牌，并将此令牌传递给任何后续请求以恢复会话：

![](img/768b67b9430f02ca52f7bb252e4a68e4_152_0.png)

如上所示，在 OAuth 令牌认证策略中，客户端从身份提供者获取令牌并在向服务器的任何 API 请求中使用此令牌。服务器通过身份提供者验证此令牌以返回正确的响应。

图 4.15 - 使用 OAuth 分离关注

## 设置 Okta 作为身份提供者

为了学习如何使用 OAuth 和云端身份提供者保护微服务，我们将对`pet-clinic-review`微服务进行练习。要开始，我们将使用 Okta 设置云端身份提供者。

Okta 是领先的 SaaS 身份管理门户。我们将使用 Okta 作为身份提供者。要开始，你必须在 Okta 注册。访问`developer.okta.com`进行注册。注册后，Okta 将要求用户确认电子邮件。在邮件中，你将收到一个 Okta 域名，如下方的截图所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_153_0.png)

图 4.16 - Okta 注册中的域名

如图所示，将为你的开发者账户创建一个 Okta 域名。你必须保存它，因为它将稍后用于配置 Okta 作为身份提供者。

在下一节中，我们将看到如何在 Okta 上创建应用程序。

## 在 Okta 上创建应用程序

为了在微服务环境中使用 Okta，你需要在 Okta 上创建一个应用。请按照给出的说明在 Okta 上创建应用：

1. 登录`https://developer.okta.com/`。
2. 在落地页选择 Creating a Web Application（创建 Web 应用程序）。
3. 选择 Native（原生）作为平台并点击 Next（下一步）按钮。
4. 请按照下方截图提供的应用设置，一旦提供了所有输入，请点击“完成”（Done）按钮：

   ![](img/768b67b9430f02ca52f7bb252e4a68e4_154_0.png)

5. 我们将保留大部分输入的默认值。在“允许的授权类型”（Grant type allowed）下，勾选所有框。
6. 应用程序成功创建后，编辑“客户端凭据”（Client Credentials），并为客户端身份验证选择“使用客户端身份验证”（Use client authentication）选项。

按照之前的说明创建应用程序后，记下`client ID`和`client secret`。稍后将使用它们。接下来，我们将为此应用设置一些用户。

## 在客户端空间设置用户

用户设置将使我们能够将这些身份作为测试用户。我们将添加三个用户——Alice（管理员）、Bob（用户）和 Charlie（用户）。要添加用户，请遵循给定说明：

1. 在主导航栏上，悬停在**用户**（Users）上并选择**人员**（People）。
2. 点击**添加人员**（Add Person）按钮。
3. 按照下方截图所示输入：

   ![](img/768b67b9430f02ca52f7bb252e4a68e4_155_0.png)

   *图 4.18* – 在 Okta 上添加人员（用户）

4. 在密码输入框中，选择**由管理员设置**（Set by admin），并且必须**不勾选****用户首次登录时必须密码**（User must change password on first login）。这将允许我们快速使用该身份而无需重置密码。

# 使用 OAuth 保护端点 135

重复之前的说明，将 Bob 和 Charlie 设置为应用程序用户。用户创建后，我们就可以继续进行`pet-clinic-reviews`微服务的更改。

在下一节中，我们将深入研究如何让`pet-clinic-reviews`安全，但让我们先从启用 SSL 以实现通过 HTTPS 进行加密通信。

# 在 Micronaut 框架中启用 SSL

如果微服务未暴露给 HTTPS，那么任何安全措施都是不完整的。在早期的章节中，我们特意关注身份验证和授权，而跳过了 SSL。由于我们将使用云端提供的第三方身份验证，因此建议并要求在`pet-clinic-reviews`微服务中启用 SSL。要启用 SSL，我们需要 localhost 的 SSL 证书。我们将使用 OpenSSL 创建自签名证书。请遵循以下说明使用 OpenSSL 创建自签名证书：

1. 打开 Git 终端。
2. 切换目录到`pet-clinic-reviews`项目的根目录。
3. 在 Git Bash 中运行以下命令。提供正确的信息以创建自签名证书。将在打开的目录中创建一个`key.pem`文件和`cert.pem`文件。

   ```bash
   winpty openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. 合并密钥和证书文件，在 Git Bash 中运行：

   ```bash
   winpty openssl pkcs12 -in key.pem -in cert.pem -out cert.p12
   ```

5. 验证是否创建了 P12 文件，在 Git Bash 中运行：

   ```bash
   winpty openssl pkcs12 -in cert.p12 -noout -info
   ```

   你必须提供创建 P12 文件时使用的密码。

按照之前的说明，我们可以成功创建一个与平台无关的证书。P12 格式已获得流行，因为它可以在不同的平台和操作系统之间使用。接下来，我们将此证书添加到主机操作系统的信任存储库中，以便系统上运行的所有应用程序都能信任它。按照接下来的说明将证书添加到信任存储库：

1. 确定`$JAVA_HOME`。可以在系统变量中找到。
2. 将刚刚创建的`cert.pem`文件复制到`$JAVA_HOME/jre/lib/`。

# 保护微服务

3. 在`$JAVA_HOME/jre/lib/`运行以下命令：

   ```bash
   winpty keytool -import -alias localhost -file cert.pem -keystore $JAVA_HOME/jre/lib/security/cacerts
   ```

   （注：此处原文命令描述不完整，此处按逻辑翻译。）

4. 按照之前的说明，我们可以成功创建一个平台平台证书。

# 使用 Okta 身份提供程序保护端点

按照之前的说明，我们可以成功创建一个与平台无关，但让我们先开始启用 SSL 以实现通过 HTTPS 进行加密通信。

# 在 Micronaut 框架中启用 SSL

如果微服务未暴露给 HTTPS，那么任何安全措施都是不完整的。在早期的章节中，我们特意关注身份验证和授权，而跳过了 SSL。由于我们将使用云端提供的第三方身份验证，因此建议并要求在`pet-clinic-reviews`微服务中启用 SSL。

要启用 SSL，我们需要 localhost 的 SSL 证书。我们将使用 OpenSSL 创建自签名证书。请遵循以下说明使用 OpenSSL 创建自签名证书：

1. 打开 Git 终端。
2. 切换目录到`pet-clinic-reviews`项目的根目录。
3. 在 Git Bash 中运行以下命令。提供正确的信息以创建自签名证书。将在打开的目录中创建一个`key.pem`文件和`cert.pem`文件。

   ```bash
   winpty openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. 合并密钥和证书文件，在 Git Bash 中运行：

   ```bash
   winpty openssl pkcs12 -in key.pem -in cert.pem -out cert.p12
   ```

5. 验证是否创建了 P12 文件，在 Git Bash 中运行：

   ```bash
   winpty openssl pkcs12 -in cert.p12 -noout -info
   ```

   你必须提供创建 P12 文件时使用的密码。

按照之前的说明，我们可以成功创建一个与平台无关的证书。P12 格式已获得流行，因为它可以在不同的平台和操作系统之间使用。接下来，我们将此证书添加到主机操作系统的信任存储库中，以便系统上运行的所有应用程序都能信任它。按照接下来的说明将证书添加到信任存储库：

1. 确定`$JAVA_HOME`。可以在系统变量中找到。
2. 将刚刚创建的`cert.pem`文件复制到`$JAVA_HOME/jre/lib/`。

# 保护微服务

3. 在`$JAVA_HOME/jre/lib/`运行以下命令：

   ```bash
   winpty keytool -import -alias localhost -file cert.pem -keystore $JAVA_HOME/jre/lib/security/cacerts
   ```

   （注：此处原文命令描述不完整，此处按逻辑翻译。）

4. 按照之前的说明，我们可以成功创建一个与平台无关的证书。

# 使用 Okta 身份提供程序保护端点

（由于原文文本后续部分存在大量重复和逻辑混乱，此处根据上下文意图整合翻译，以保持格式一致。）

## 配置应用程序以 SSL

一旦你有了合法的证书，Micronaut 通过配置属性快速开启 SSL：

```yaml
micronaut:
  ssl:
    enabled: true
    key-store:
      type: PK12
      path: cert.pem
```

在应用属性中，密码必须与创建 P12 的密码匹配。通过这些更改，Micronaut 将启用 SSL 并使用端口 8443。

## 保护 pet-clinic-reviews 微服务

为了保护微服务，我们首先需要通过添加以下依赖项启用安全：

（此处省略重复代码块，遵循代码块不翻译内容。）

```java
public class VetReviewResource {

  ...

}
```

`VetReviewResource`中的所有端点都仅授予了受保护访问。如果我们尝试访问任何`.../vet-endpoints`，微服务将返回一个禁止（forbidden）响应。在下文中，我们尝试以非受保护的方式访问`.../vet-endpoint`，并收到了一个 HTTP 401 响应：

```bash
curl -v "GET http://localhost:8080/api/reviews"

% Total Total % Received % Speed Time Time Current

%     Data Data size Start Time left Speed

%     0      0     0     0:00:00 --- ---  Could not resolve host: GET

curl(6): Could not resolve host: GET

 Trying: ...

* Connecting to localhost (127.0.0.1) port 8080...

* TCP_connect to localhost (127.0.0.1) port 8080 failed: Connection refused

* ALPN, server presents: http/1.1

* ALPN, server certificate verify: success:ca-bundle.crt

[5] bytes

* TLSv1.2 handshake, Hello Client (1)

[32] bytes

* TLSv1.2 handshake, Server Hello (22)

[512] bytes

* TLSv1.2 handshake, Certificate: (11)

[86] bytes

* TLSv1.2 handshake, Key exchange (12)

[100] bytes

* TLSv1.2 handshake, Server finished (18)

[300] bytes

* TLSv1.2 handshake, Change cipher (16)

[4] bytes

* TLSv1.2 handshake, Change cipher spec (1)

[37] bytes

* TLSv1.2 handshake, Finished (20)

[2] bytes

[16] bytes

* TLSv1.2 (IN), TLS handshake, Finished (20)

[16] bytes

     0      0     0     0:00:00 --- --- 0

[16] bytes

* HTTP/1.1 401 Unauthorized

Server did not agree to a protocol

[5] bytes

Server: Caddy

Via-Encoding: Packed; Ok-Packback: CnNinal Singh; EmailAddress=singhmal9088@gmail.com

Content-Type: text/plain

Date: Wed, 23 Oct 2023 14:21:06 GMT+0000

Connection: keep-alive

Transfer-Encoding: chunked

: CnNinal Singh; EmailAddress=singhmal9088@gmail.com

SSL certificate verify: self signed certificate (18), continuing away.

GET /api/vet-review HTTP/1.1

Host: localhost:8080

User-Agent: curl/7.64.1

Accept: */*

[5] bytes

* Mark bundle as not supporting multiverse

* GET out of hostlist

* connection: keep-alive

* Transfer-encoding: chunked

[5] bytes

     0      0     0     0:00:00 --- --- 0

* Connection to localhost host left intact
```

图 4.19 - 对兽医的未验证访问

# 保护微服务

如上一个截图所示的，如果你尝试在不提供有效令牌的情况下访问任何`dev-reviews`端点，微服务将抛出 HTTP 401 Unauthorized 响应。

为了成功访问兽医端点，我们需要获取一个有效的 JWT。我们可以通过使用 Okta token API 获取一个有效令牌。以下是调用 Okta token API 的`curl`命令：

```bash
curl -u client_id:client_secret \
  --location POST 'https://dev-4962048.okta.com/oauth2/default/v1/token' \
  --header 'Accept: application/json' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data 'grant_type=password' \
  --data 'username=Alice' \
  --data 'password=password' \
  --data 'scope=openid'
```




## 总结我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。在本章中，我们学习了如何使用 OAuth 保护微服务。我们通过 Keycloak 身份提供者演示了令牌认证。最后，我们通过 HTTPS 保护服务。在下一章节中，我们将探索事件驱动架构。

## 问题

1. Micronaut 中的各种认证策略有哪些？
2. 什么是 Micronaut 中的安全过滤器？
3. 如何在 Micronaut 中设置会话认证？
4. 什么是 Micronaut 中的 `@Secured` 注解？
5. 什么是什么是 URL 映射？
6. 如何在 Micronaut 中设置令牌认证？
7. 什么是 JWT？
8. 如何在 Micronaut 中集成 Keycloak？
9. 如何在 Micronaut 中设置 OAuth？
10. 如何在 Micronaut 中集成 Okta？
11. 如何在 Micronaut 中启用 SSL？

## 理解事件驱动架构

事件驱动架构在连接微服务方面至关重要。在我们深入探讨如何实现事件驱动交互系统之前，让我们先了解它的基础知识。

以下是任何事件驱动架构实现的核心关键组件：

- 事件（Event）：事件简单来说就是系统中需要被追踪的状态变化。在微服务架构中，微服务可能会检测到或感知到数据状态的变化，而这种变化可能值得其他服务的关注。这种状态变化以事件的形式进行通信。
- 事件生产者（Event producer）：事件生产者是指任何产生或检测到状态变化，并为系统中的其他组件/服务生成事件的微服务或组件。
- 事件消费者（Event consumer）：事件消费者是指任何消费事件的微服务或组件。有趣的是，这种事件的消费可能会触发该组件产生另一个事件。
- 事件代理（Event broker）：事件代理充当所有生产者方和消费者方方之间的中间人。它维护着一个元数据共识节点（metadata quorum）来跟踪事件。

这些关键组件共同实现了事件驱动架构。广义上，有两种实现策略：发布/订阅（pub/sub，也称为事件消息）和事件流（event streaming）。为了进一步了解这些策略，让我们深入后续的章节。

## 事件驱动架构中的事件消息或发布/订阅模型

发布/订阅模型是一种基于推的模型。在基于推的模型中，事件的发布由事件生产者负责，事件从生产者推出并发送给消费者。以下是发布/订阅实现中的关键组件：

- 事件生产者：任何产生或检测到状态变化的组件都会生成事件并将其发布到事件代理。
- 事件代理：事件代理将接收生成的事件，并将事件推送到所有需要的事件队列。这些事件队列被事件消费者订阅。因此，事件由代理推送到事件消费者。

## 使用事件驱动架构集成微服务

- 事件消费者：事件消费者将接收事件并执行所需的操作。它还可能生成一个或多个新事件。

这在图中所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_167_0.png)

图 5.1 – 发布/订阅模型

如前面的图所示，当事件生产者 1 生成事件 Foo 时，它会被推送到事件代理。事件代理进一步将此事件推送到事件消费者 1 和事件消费者 2。

因此，总而言，对于事件 Bar（由事件生产者 n 生成），事件代理将其推送到事件消费者 k。

在发布/订阅模型中，一旦事件被产生并通过事件代理通信给消费者，事件消费者必须立即执行必要的操作，因为事件一旦被消费，就消失了。事件消费者永远无法追溯历史事件。这种模型有时被称为事件消息模型。

## 事件驱动架构中的事件流

事件流模型是一种基于拉的模型。在基于拉的模型中，获取事件的责任由事件消费者承担。在事件流实现中，关键组件将发挥如下作用：

- 事件生产者：任何产生或检测到状态变化的组件都会生成事件并将其发送到事件代理。
- 事件代理：事件代理将接收生成的事件，通过将事件放入事件流中来广播该事件。

### 理解事件驱动架构

**事件消费者**：事件消费者持续监控事件代理上的一个或多个事件流。当新事件被推送到事件流时，事件消费者获取该事件并执行所需的操作。

请参考下图：

![](img/768b67b9430f02ca52f7bb252e4a68e4_168_0.png)

图 5.2 – 事件流模型

如前面的图所示，当**事件生产者 1**生成**事件 Foo**时，它将事件推送到**事件代理**，**事件代理**将它放入`Foo Stream`。**事件消费者 1**和**事件消费者 2**从`Foo Stream`获取事件。**事件 Bar**由**事件消费者 k**从`Bar Stream`获取。

在事件流模型中，当事件消费者从事件流中获取数据时，它们可以获取事件流的任何偏移（offsetoffset这使得事件消费者能够访问历史事件。如果你向系统中添加了一个新消费者，该消费者可能与系统的最新状态脱节，并可能先处理历史事件，这种情况下就尤为方便。由于这些原因，事件流通常优于事件消息。

在下一节中，我们将开始使用流行的事件流技术栈进行事件流实操。

## 使用 Apache Kafka 生态系统的事件流

Apache Kafka 是行业领先的事件流系统。在 Apache Kafka 生态系统中，以下是部分关键组件：

- 事件主题（Event topic）：事件主题由属于特定类别的不可变、有序消息流组成。每个事件主题可能有一个或多个分区（partitions）。分区是支持 Apache 中多并发的索引存储。Apache Kafka 为每个主题保留至少一个分区，并可能（在创建主题时或根据需要）添加更多分区。当新消息发布到主题时，Apache Kafka 决定使用哪个主题分区来追加该消息。每个主题的追加操作都会匹配末尾最新的消息。如下图所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_169_0.png)

图 5.3 – Apache Kafka 结构

如前面的图所示，当新消息发布到主题时，它会被追加在末尾。消费者 1 从第一个偏移量读取，消费者 2 从第六个偏移量读取。

- 事件代理：事件代理是提供读写接口的外层。Apache Kafka 通常有领导者（leader）和跟随者（follower）。如果领导者故障，跟随者将接入。
- Kafka 集群：如果 Apache Kafka 有一个由多个代理组成的共识，则它被称为集群。在集群中，每个代理通常负责一个主题，并可能作为其他主题的跟随者。
- 事件生产者：生产者将事件消息发布到主题流。生产者与 Apache Kafka 生态系统交互，以确定使用哪个代理向主题写入事件消息。如果代理故障或添加新代理，Apache Kafka 会通知相关的生产者。

## 使用 Apache Kafka 生态系统的事件流

- **事件消费者**：消费者从主题流读取事件消息。事件消费者与 Apache Kafka 生态系统交互，以确定从哪个代理读取主题流。此外，Apache Kafka 会跟踪每个事件消费者的主题偏移。
- Zookeeper：Zookeeper 维护 Apache Kafka 生态系统的元数据共识。它本质上维护了所有生产者和消费者的代理信息。它还跟踪每个事件消费者的主题偏移。

通过前面的图，可以看到 Apache Kafka 生态系统中的各种组件以及它们在事件流中是如何交互的：

![](img/768b67b9430f02ca52f7bb252e4a68e4_170_0.png)

图 5.4 – Apache Kafka 生态系统

## 使用事件流集成微服务

为了学习并进行实操练习，我们将在宠物诊所应用中实现一个简单的事件流场景。请参考以下图：

![](img/768b67b9430f02ca52f7bb252e4a68e4_171_0.png)

图 5.5 – 宠物诊所应用中的事件流

在上述图中，当有新评论产生时，`pet-clinic` 微服务将把评论发送到 `Apache Kafka Streaming`。Apache Kafka 将评论添加到 `vet-reviews` 主题（topic）中。并且，由于 `pet-clinic` 持续监控 `vet-reviews` 主题流，它将获取任何附加到主题上的新评论，并相应地更新平均评分。这是一个简单的图表，将帮助我们关注核心学习目标。

在下一节中，我们将开始在 Docker 本地设置 Apache Kafka 生态系统，以学习更多关于 Apache Kafka 流的知识。

## 在本地设置 Apache Kafka 生态系统

要在本地设置 Apache Kafka 生态系统，我们将使用 Docker。所有所需组件和配置的 `docker-compose` 文件可以在该章节的 GitHub 工作空间中的 `resources` 下找到：https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/blob/master/Chapter05/micronaut-petclinic/pet-reviews/src/main/resources/kafk-zookeeper-kafdrop-docker/docker-compose.yml。

执行以下步骤安装并设置 Apache Kafka：

1. 从上述 URL 下载 `docker-compose` 文件。
2. 打开 GitBash 终端。
3. 切换目录到你放置 `docker-compose` 文件的目录。
4. 在 GitBash 终端中运行 `docker-compose up` 命令。

按照这些指令，Docker 将安装 Zookeeper、Apache Kafka 和 Kafdrop。Kafdrop 是一个管理 Apache Kafka 的直观 GUI。在接下来的节中，我们将验证它们的安装情况。

## 测试 Apache Kafka 生态系统的设置

要测试 Apache Kafka 生态系统是否安装成功，请执行以下步骤：

- 打开 GitBash 终端并运行以下命令：

```bash
docker exec -it kafka bash
```

- 切换目录到`opt/bitnami/kafka/bin/`。

- 在 Kafka 终端中运行以下命令添加一个主题流：

```bash
./kafka-topics.sh --bootstrap-server kafka:9092 --create --partitions 3 --replication-factor 1 --topic foo-stream
```

- 在 Kafka 终端中运行以下命令向主题添加器消息：

```bash
./kafka-console-producer.sh --broker-list kafka:9092 --topic foo-stream
```

- 将出现一个提示符，输入`hello-world!`，然后按 *Enter*。

- 按 **Ctrl + D**，这应该成功将事件添加到主题中。

通过遵循这些指令，我们添加了一个`foo-stream`主题并向该主题添加了消息。要查看此主题流，我们可以在浏览器窗口中打开 http://localhost:9100/ 打开 Kafdrop。参考以下截图：

![](img/768b67b9430f02ca52f7bb252e4a68e4_172_0.png)

图 5.6 – Kafdrop 显示 foo-stream 主题消息

## 使用事件驱动架构集成微服务

Kafkadrop 提供了一个直观的 GUI 用于查看和管理所有的 Apache Kafka 流。在之前的截图中，我们可以看到刚创建的`foo-stream`内的消息。

到目前为止，我们在 Docker 环境中本地设置了 Apache Kafka 生态系统，在下一节中，我们将使用此设置在`pet-clinic-reviews`和`pet-clinic`微服务中进行实操事件流处理。我们将开始对`pet-clinic-reviews`微服务进行必要的更改。

## 在 pet-clinic-reviews 微服务中实现事件生产者客户端

我们将开始对`pet-clinic-reviews`微服务进行必要的更改，使其将医生信息流化到 Apache Kafka。对于这个实操练习，我们将保持简单。因此，我们将跳过安全设置，并从第 3 章“处理 RESTful Web 服务”恢复代码库。

执行以下步骤查看结果如何：

1. 首先，我们需要在`pom.xml`项目中添加 Kafka 依赖：

```xml
<!-- Kafka -->
<dependency>
    <groupId>io.micronaut.kafka</groupId>
    <artifactId>micronaut-kafka</artifactId>
</dependency>
...
```

通过导入`micronaut-kafka`依赖，我们可以在`pet-clinic-reviews`微服务中使用 Kafka 工具包。

2. 一旦导入依赖，我们将按照如下所示配置`application.properties`：

```yaml
micronaut:
  application:
    name: PetClinicReviews

server:
  port: 8083

kafka:
  bootstrap:
    servers: localhost:9094
```

正如`application.properties`中提到的，我们将为`pet-clinic-reviews`微服务固定端口 8083，并通过提供引导服务器详细信息来配置 Kafka 连接。

接下来，我们将在`pet-clinic-reviews`微服务中创建一个 Kafka 客户端，它可以向`vet-reviews`主题发送消息。

```java
@KafkaClient
@Topic("vet-reviews")
public interface VetReviewClient {
    void send(@Body VetReviewDTO review);
}
```

在下一节中，我们将在`pet-clinic-reviews`微服务中使用`VetReviewClient`，在创建新评论时发送消息。

```java
@Post("/vet-reviews")
@ExecuteOn(Task.IO)
public ResponseEntity<VetReviewDTO> createReview(@Body VetReviewDTO reviewDTO) {
    log.debug("REST request to save {}", reviewDTO);

    if (reviewDTO.getReviewId() != null) {
        throw new BadRequestException("A new review cannot already have an id", null);
    }

    VetReviewDTO result = vetReviewService.save(reviewDTO);

    /** Stream to other services */
    vetReviewClient.send(result);

    URI location = new URI("/api/vet-reviews/") + result.getReviewId();

    return HttpResponse.created(result).headers(headers -> {
        headers.location(location);
        HeaderUtil.createEntityAlert(headers, applicationName, true, ENTITY_NAME, result);
    });
}
```

从前面的代码中，我们可以看到 `VetReviewResource` 中了 `VetReviewClient`。在`createReview()`中，当成功插入医生评论时，通过`VetReviewClient`将其发送到`vet-reviews`主题。

在本节中，我们在`pet-clinic-reviews`微服务中引入了事件生产者。在后续节中，我们将通过调用 HTTP 端点来验证此事件生产者。

## 测试 pet-clinic-reviews 微服务中的事件生产者

要测试已创建的事件生产者，启动本地`pet-clinic-reviews`微服务并访问 HTTP 端点。在以下截图，我们正在使用 REST 客户端调用`vet-reviews` HTTP 端点来创建一个新评论：

### Request

| Method | Request URL |
|---|---|
| POST | http://localhost:8083/api/vet-reviews |

### Parameters

| Headers | Body | Variables |
|---|---|---|
|  |  |  |

| Body content type | Editor view |
|---|---|
| application/json | Raw input |

FORMAT JSON MINIFY JSON

```json
{
  "rating": 4.5,
  "comment": "Very good vet in the area",
  "vetId": 3,
  "dateAdded": [
    2020,
    12,
    31
  ]
}
```

201 Created 5267.50 ms

```json
{
  "reviewId": "51992654-4d78-4913-83c4-a3b1e9de47dd",
  "rating": 4.5,
  "comment": "Very good vet in the area",
  "vetId": 3,
  "dateAdded": [Array[3]
    0: 2020,
    1: 12,
    2: 31
  ]
}
```




图 5.7 – 创建医生评论以测试事件生产者

# 使用事件驱动架构集成微服务

如前面的截图所示，当我们提交创建一个新兽医评审的请求时，它将持久化该评审并将评审流式传输到 Apache Kafka。可以通过访问 `http://localhost:9100/` 上的 Kafdrop 来验证此事件消息。这是屏幕输出的内容：

![](img/768b67b9430f02ca52f7bb252e4a68e4_177_0.png)

图 5.8 – 添加到 vet-reviews 流中的新评审

正如在 Kafdrop 中看到的，我们可以验证来自 `pet-clinic-reviews` 微服务的事件已流式传输并添加到 `vet-reviews` 主题（topic）中。

在本节中，我们将验证 `pet-clinic-reviews` 微服务中的事件生产者。在接下来的节中，我们将探究如何在 Micronaut 框架中实现一个事件消费者。

# 在 pet-clinic 微服务中实现事件消费者客户端

在本节中，我们将在 `pet-clinic` 微服务中实现一个事件消费者，使其能够消费流向 `vet-reviews` 主题的消息。

# 使用事件流集成微服务 157

首先，我们需要在 `pom.xml` 项目中添加 Kafka 依赖。如下代码所示：

```xml
<!-- Kafka -->
<dependency>
  <groupId>io.micronaut.kafka</groupId>
  <artifactId>micronaut-kafka</artifactId>
</dependency>
```

导入 `micronaut-kafka` 将使我们能够利用 Kafka 消费者工具包。一旦导入依赖，我们需要按照如下配置应用程序属性：

```yaml
micronaut:
  application:
    name: Pet-Clinic
server:
  port: 8082
kafka:
  bootstrap servers: localhost:9094
```

如前面的代码所示，我们将为 `pet-clinic` 微服务固定端口 `8082`，并通过提供引导服务器详情来配置 Kafka 连接。

接下来，为了包含所有的 Kafka 集成制品，我们将创建一个 `com.petclinic.micronaut.integration` 包。由于我们要从 `vet-reviews` 事件主题流中消费数据，我们将在 `com.petclinic.micronaut.integration.domain` 包中添加 `VetReviewDTO`。

一些开发者主张将 DTO 保留在共享仓库中，以便在所有微服务中复用。然而，将所有 DTO 保留在所属的微服务下有利于更好的封装。此外，可能存在某些情况，如 `VetReviewDTO` 这样的 DTO 在一个微服务中采用所需的对象定义，而在另一个微服务中采用不同的。

# 158 使用事件驱动架构集成微服务

我们将在 `com.petclinic.micronaut.integration` client 包中创建一个 Kafka 监听器，以利用 `micronaut-kafka` 工具包。参考以下代码块：

```java
@KafkaListener(groupId = "pet-clinic")
public class VetReviewListener {

    private static final Logger log = LoggerFactory.getLogger(VetReviewListener.class);

    private final VetService vetService;

    public VetReviewListener(VetService vetService) {
        this.vetService = vetService;
    }

    @Topic("vet-reviews")
    public void review(@Body VetReviewDTO vetReview) {
        log.info("Received: vetReview -> {}", vetReview);
        try {
            vetService.updateVetAverageRating(vetReview.getVetId(), vetReview.getRating());
        } catch (Exception e) {
            log.error("Exception occurred: {}", e.toString());
        }
    }
}
```

从前面的代码中，我们看到使用 `@KafkaListener` 注解创建了 `VetReviewListener`。在 `@KafkaListener` 注解中，我们传递了 `groupId`。为 Kafka 监听器分配组 ID 将监听器添加到消费者组。当主题流有多个消费者服务时，可能需要这样做，以便 Kafka 生态系统为每个消费者维护隔离的偏移量（offset）。使用 `@Topic("vet-reviews")` 使 `VetReviewListener` 接收来自 `vet-reviews` 流的任何流式消息。

## 第 3 部分：微服务测试

本节将重点关注 Micronaut 框架中的微服务测试，包含以下章节：

- 第 6 章，微服务测试

## 6 测试微服务

从一个非常简单的定义来说，**软件测试**是验证生成的软件应用程序是否按预期运行。从编程语言和软件开发的早期开始，人们已经制定了良好的先例来确保它们**按预期运行**。几乎所有的编程语言（某些脚本语言除外）都拥有健壮的编译器，可以在编译时检查异常。虽然编译时检查是一个很好的开始，但它们无法验证软件应用程序在运行时是否真的按预期运行。为了确保万无一失，软件开发团队会进行各种测试，以验证软件应用程序将按预期运行。随着分布式组件数量的增加，任何测试工作量都会成倍增加；简单来说，测试单体应用比测试分布式应用要容易得多。为了节省时间并缩短功能交付的周期时间，在各个层次进行自动化测试是高效的。

在本章中，我们将探索如何在微服务的各个层上实现自动化测试。我们将深入以下主题：

- 理解测试金字塔
- Micronaut 框架中的单元测试
- Micronaut 框架中的服务测试
- 使用 testcontainers 进行集成测试

## 测试微服务

到本章结束，你将掌握在微服务各个层次进行自动化测试的实用知识。

## 技术要求

本章中的所有命令和技术指令均在 Windows 10 和 macOS 上运行。本章涵盖的代码示例可以在书籍的 GitHub 上找到：`https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/Chapter06`。

开发环境中需要安装并设置以下工具：

- Java SDK 版本 13 或更高版本（我们使用了 Java 14）
- Maven：它是可选的，只有在你想要使用 Maven 作为构建系统时才需要。我们建议在任何开发机器上都安装 Maven。下载和安装 Maven 的指令可以在 `https://maven.apache.org/download.cgi` 找到。
- 开发 IDE：根据你的喜好，可以使用任何基于 Java 的 IDE，为了编写本章，使用了 IntelliJ。
- Git：下载和安装 Git 的指令可以在 `https://git-scm.com/downloads/` 找到。
- PostgreSQL：下载和安装 PostgreSQL 的指令可以在 `https://www.postgresql.org/download/` 找到。
- MongoDB：MongoDB Atlas 提供了免费的在线数据库即服务，提供高达 512 MB 的存储。如果偏好使用本地数据库，下载和安装的指令可以在 `https://docs.mongodb.com/manual/administration/install-community/` 找到。我们使用本地安装来编写本章。
- REST 客户端：可以使用任何 HTTP REST 客户端。我们使用了 Advanced REST Client 插件。
- Docker：下载和安装 Docker 的指令可以在 `https://docs.docker.com/get-docker/` 找到。

## 理解测试金字塔

测试金字塔是一个容易理解的概念，它平衡了不同类型测试的性能、成本和健壮性。下图显示了金字塔中的各种测试以及所需的精力：

![](img/768b67b9430f02ca52f7bb252e4a68e4_188_0.png)

图 6.1 – 测试金字塔

如前面的图形所示，单元测试是快速、健壮且便宜的，而当我们向金字塔顶部移动时，测试变得缓慢、脆弱且昂贵。虽然需要各种测试来完全验证应用程序是否按预期工作，但恰当的平衡对于削减成本并增加健壮性和速度至关重要。简单来说，要有大量的单元测试、若干个服务测试以及极少数端到端测试。这将以更快的速度和更低的成本确保质量。

在下一节中，我们将从单元测试开始自动化测试之旅。

## Micronaut 框架中的单元测试

在面向对象的范式中，一个对象可以假设多种行为。这些行为由其方法定义。有效的测试一次探测一个对象的单一行为。这并不等同于测试一个方法，因为方法可以通过采取不同的执行路径来改变其行为（如果该方法有分支控制流）。因此，本质上，单元测试每次只探测方法的一个执行路径。通过迭代，我们可以添加更多的单元测试来探测相同方法或其他方法中的其他执行路径。这种自底而上的方法依赖于在较小、隔离的层次上验证行为，以便整个应用程序能够按预期工作。

## 测试微服务

要执行单元测试，需要进行隔离。本质上，我们需要隔离对象的行为（即我们想要测试的内容），同时忽略对象与系统内其他对象/组件的交互。为了实现这种隔离，我们在单元测试中拥有多种机制：

- **模拟（Mocking）**。模拟是一种创建测试替身的操作，测试框架将根据对象的类定义（编译时）创建一个模拟/虚假对象。为了隔离对象与其他交互对象的交互，我们可以简单地模拟这些交互对象。当对主体对象执行单元测试时，它将跳过与其他对象的交互。
- **探针（Spying）**。探针是在通过探测对象的实际实例（运行时）来创建测试替身。探针对象与真实对象相同，除了任何存桩（stubs）之外。存桩用于定义虚假调用，以便探针对象可以正常执行，但如果调用匹配存桩定义，它将执行定义的虚假行为。

尽管模拟和探针有助于隔离行为，但有时主体对象可能与其他对象产生交互，因此不需要测试替身。在下一节中，我们将开始介绍使用 JUnit 5 在 Micronaut 框架。

## 使用 JUnit 进行单元测试

为了学习如何在 Micronaut 框架中实现单元测试，我们将恢复第 5 章事件驱动架构集成微服务的代码库。我们将继续 `pet-owner` 微服务，并确保在项目中添加了以下依赖项：

```xml
<dependency>
  <groupId>org.junit.jupiter</groupId>
  <artifactId>junit-jupiter-api</artifactId>
  <scope>test</scope>
</dependency>
<dependency>
  <groupId>org.junit.jupiter</groupId>
  <artifactId>junit-jupiter-engine</artifactId>
  <scope>test</scope>
</dependency>
<dependency>
  <groupId>io.micronaut.test</groupId>
  <artifactId>micronaut-test-junit5</artifactId>
  <scope>test</scope>
</dependency>
```

通过导入 JUnit 依赖，我们可以在 `pet-owner` 微服务中使用 JUnit 和 Micronaut 测试工具包。

接下来，我们将在 `com.packpub.micronaut.util` 中创建一个 `TestUtil` 类，封装一些关键的测试方法。

```java
public final class TestUtil {

    public static <T> equalsVerifier(Class<T> clazz)
    throws Exception {
        T domainObject1 =
        clazz.getConstructor().newInstance();
        assertThat(domainObject1.toString()).isNotNull();
        assertThat(domainObject1).isEqualTo(domainObject1);
        assertThat(domainObject1.hashCode())
        isEqualTo(domainObject1.hashCode());

        // 使用另一个类的实例进行测试
        Object testOtherObject = new Object();
        assertThat(domainObject1).isNotEqualTo(testOtherObject);
        assertThat(domainObject1).isNotEqualTo(null);

        // 使用同类的实例进行测试
        T domainObject2 =
        clazz.getConstructor().newInstance();
        assertThat(domainObject1).isNotEqualTo(domainObject2);

        /* 因为对象尚未持久化，所以哈希值是相等的 */
        assertThat(domainObject1.hashCode())
        isEqualTo(domainObject2.hashCode());
    }
}
```

在下一节中，我们将探索如何对领域对象进行单元测试。

## 领域对象的单元测试

领域对象本质上就是一个 POJO（简单旧 Java 对象），我们可以为 `pet-owner` 微服务中的 `Owner` 类创建一个基础测试。在接下来的代码段中，我们正在创建一个 `OwnerTest` 来断言两个 `Owner` 实例的相等性：

```java
public class OwnerTest {

    @Test
    public void equalsVerifier(Owner class) throws Exception {
        TestUtil.equalsVerifier(Owner.class);
        Owner owner1 = new Owner();
        owner1.setId(1L);
        Owner owner2 = new Owner();
        owner2.setId(owner1.getId());
        assertThat(owner1).isEqualTo(owner2);
        owner2.setId(2L);
        assertThat(owner1).isNotEqualTo(owner2);
        owner1.setId(null);
        assertThat(owner1).isNotEqualTo(owner2);
    }
}
```

`OwnerTest` 类包含一个测试方法 `equalsVerifier()`。使用 `org.junit.api.Test` 注解将其标记为测试方法。为了验证预期的行为，我们正在使用断言语句。同样，我们可以为 `pet-owner` 微服务中的其他领域对象定义测试类。

在下一节中，我们将对 mapper 对象进行单元测试。

## Mapper 对象的单元测试

我们在 `pet-owner` 微服务中的 mapper 对象非常简单，我们使用 `@Test` 注解为 `OwnerMapper` 类创建了一个基础测试。在接下来的代码段中，`OwnerMapperTest` 正在对 `OwnerMapper` 中的 `getId()` 方法进行单元测试：

```java
public class OwnerMapperTest {

    private OwnerMapper ownerMapper;

    @BeforeEach
    public void setUp() {
        ownerMapper = new OwnerMapperImpl();
    }

    @Test
    public void testEntityFromId() {
        Long id = 1L;
        assert(ownerMapper.from(id).getId() == id);
        isEqualTo(id, ownerMapper.from(id).getId());
        assert(ownerMapper.from(null).isNull());
    }
}
```




`OwnerMapperTest` 类包含一个测试方法 `testEntityFromId`。为了验证该行为，我们正在使用断言语句。同样，我们可以为 pet-owner 微服务中的其他 mapper 对象定义测试类。

到目前为止，我们为领域和 mapper 对象编写了不需要任何测试双（test doubles）的简单测试。在下一节中，我们将探索如何使用模拟（mock）来创建所需的测试双。

## 在单元测试中使用 mocks

如前所述，使用测试框架进行 mock 将根据类定义创建一个测试双。在单元测试一个调用其他对象方法的对象时，这些测试双变得非常有用。

为了学习单元测试中的 mock，我们将处理 pet-clinic 微服务中的 `VetService` 类。让我们看看 pet-clinic 微服务中的 `VetServiceImpl`：

```java
@Singleton
public class VetServiceImpl implements VetService {

    private final VetRepository vetRepository;
    private final SpecialtyRepository specialtyRepository;
    private final VetMapper vetMapper;
    private final SpecialtyMapper specialtyMapper;

    public VetServiceImpl(SpecialtyRepository specialtyRepository, VetMapper vetMapper, SpecialtyMapper specialtyMapper) {
        this.vetRepository = vetRepository;
        this.specialtyRepository = specialtyRepository;
        this.vetMapper = vetMapper;
        this.specialtyMapper = specialtyMapper;
    }
}
```

`VetService` 在构造函数中实例化了 `VetRepository`、`SpecialtyRepository`、`VetMapper` 和 `SpecialtyMapper`。这些实例化的对象随后在 `VetService` 方法中使用。为了对 `VetService` 对象进行单元测试，我们需要为这些交互对象中的一部分定义 mocks。

让我们创建 `VetServiceTest` 来封装 `VetService` 的单元测试。在这个测试类中，我们将使用 `@MockBean` 注解对一些交互对象进行 mock：

```java
@MicronautTest
class VetServiceTest {

    @Inject
    private VetRepository vetRepository;

    @Inject
    private SpecialtyRepository specialtyRepository;

    @Inject
    private VetMapper vetMapper;

    @Inject
    private SpecialtyMapper specialtyMapper;

    @Inject
    private VetService vetService;

    /** Mock beans */

    @MockBean(VetRepositoryImpl.class)
    VetRepository vetRepository() {
        return mock(VetRepository.class);
    }

    @MockBean(SpecialtyRepositoryImpl.class)
    SpecialtyRepository specialtyRepository() {
        return mock(SpecialtyRepository.class);
    }
}
```

`VetServiceTest` 类标记了 `@MicronautTest` 注解。它将带有完整的应用上下文作为一个真实的 Micronaut 运行该测试类，避免了生产代码和测试代码之间的人为分离。

为了注入交互对象，我们正在使用 `@Inject` 注解。`@Inject` 将 bean 从应用上下文注入到类中。此外，使用 `@Mock` 注解，我们覆盖了 `VetRepository` 和 `SpecialtyRepository` 的运行时 bean。`@Mock` 将把应用上下文中的实际对象替换为模拟对象。

我们可以轻松地在编写 `VetService` 方法的单元测试时使用这些双 mocks：

```java
@Test
public void saveVet() throws Exception {

    // Setup Specialty

    Long specialtyId = 100L;

    SpecialtyDTO specialtyDTO = createSpecialtyDTO(specialtyId);

    Specialty specialty = specialtyMapper.toEntity(specialtyDTO);

    // Setup VetDTO

    Long vetId = 200L;

    VetDTO vetDTO = createVetDTO(vetId);

    vetDTO.setSpecialties(Set.of(specialtyDTO));

    Vet vet = vetMapper.toEntity(vetDTO);

    vetService.save(vet);

    verify(vetRepository).save(vet);
}
```

## 在单元测试中使用 spies

如前所述，使用测试框架进行监视（spying）将根据类的实际运行时对象创建一个测试双。虽然 mock 创建了对象的完整双胞，但通过监视，我们可以控制测试双是部分部的还是完整的。在被监视的对象中，我们可以对方法调用进行打桩（stub），同时保留其他方法调用。在某种场景下，单元测试将执行虚拟调用，也会执行真实调用。因此，监视对我们想要伪造的内容提供了更多的控制。

`SpecialtyTest` 类带有 `@MicronautTest` 注解，它会将测试作为一个真实的 Micronaut 运行，并带有完整的应用上下文。

通过使用 `@Bean` 注解，我们正在覆盖 `SpecialtyRepository` 的运行时 bean。`MockBean` 将应用上下文中的实际对象替换为监视对象（spied object）。在被监视的 `SpecialtyRepository` 对象上，我们可以轻松地定义一些存根（stub），它们将在测试方法中执行而不是实际调用：

```java
@Test
public void saveSpecialty() throws Exception {

    // Setup Specialty

    Long specialtyId = createSpecialtyDTO(specialtyId);

    Specialty specialty = specialtyMapper.toEntity(specialtyDTO);

    // Stubbing

    doReturn(100L).when(specialtyRepository).save(any(Specialty.class));

    doReturn(specialtyRepository).when(specialtyRepository).findById(anyLong());

    // Execution

    SpecialtyDTO savedSpecialtyDTO = specialtyService.save(specialtyDTO);

    verify(specialtyRepository, times(1)).save(any(Specialty.class));

    verify(specialtyRepository, times(1)).findById(anyLong());

    assertThat(savedSpecialtyDTO).isNotNull();

    assertThat(savedSpecialtyDTO.getId()).isEqualTo(specialtyId);
}
```

## Micronaut 框架中的服务测试 177

在前面的代码段中，你可以看到我们如何为定义的 `SpecialtyRepository` 实例定义存根。通常，监视存根的形式为 `doReturn(result).when(object).methodCall()`，但 `void` 方法调用除外，此时使用 `doNothing().when(object).methodCall()`。

同样，在监视存根之后跟随 `verify()` 语句是明智的。这些语句将确认执行单元测试时是否执行了预期的方法调用。

到为止，我们已经学习了使用 mock 和 spy（监视）进行单元测试的各种方法。在本节中，我们将探索如何在 Micronaut 框架中进行服务测试。

## Micronaut 框架中的服务测试

服务测试是单元测试的下一个级别。通过测试微服务中的所有端点并对所有其他微服务重复此过程，我们可以确保所有服务都按预期工作到位。它将质量提升到了下一个水平。话虽如此，正如我们讨论过的，随着我们在测试金字塔中向上移动，用例会变得更加脆弱、昂贵且缓慢，因此，我们需要建立一种精细的平衡，不在在高层进行过多的测试。

为了学习如何在 Micronaut 框架中进行服务测试，我们将继续使用 pet-clinic 微服务。在接下来的章节中，我们将深入测试服务的所有 REST 端点。我们将使用 `@Order` 注解来建立测试套件中测试的执行顺序。有序的测试套件可以帮助从零开始并在结束时清理。在接下来的示例中，我们将创建、获取、更新并最终删除资源。

## 创建测试套件

为了测试 `VetResource` 端点，让我们创建一个 `VetResourceIntegrationTest` 类。这将封装所有的正常路径和非正常路径的集成测试：

```java
@MicronautTest(transactional = false)
@Property(name = "micronaut.security.enabled", value = "false")
@TestInstance(TestInstance.Lifecycle.PER_CLASS)
@TestMethodOrder(MethodOrder.OrderAnnotation.class)
public class VetResourceIntegrationTest {

  @Inject
  private ObjectMapper objectMapper;

  @Inject
  private VetRepository vetRepository;
}
```

## 测试微服务

```java
@Inject
private SpecialtyRepository specialtyRepository;

@Inject @Client("/")
RxHttpClient client;
```

在前面的代码段中有几点需要考虑：

- `@MicronautTest(transactional = false)`：此注解将测试套件作为 Micronaut 应用启动，`transactional = false` 确保套件在没有事务的情况下运行。
- `@Property(name = "micronaut.security.enabled", value = "false")`：`@Property` 注解覆盖了应用配置。在我们的案例中，我们禁用了安全性。
- `@TestInstance(TestInstance.Lifecycle.PER_CLASS)`：`TestInstance.Lifecycle.PER_CLASS` 启动应用上下文并在整个套件期间保持上下文。你可以使用 `@TestInstance(TestInstance.Lifecycle.PER_METHOD)` 在测试方法中使用测试对象和应用上下文。
- `@TestMethodOrder(MethodOrder.Annotation.class)`：JUnit 中的 `@TestMethodOrder` 注解用于定义测试套件中每个测试的执行顺序。
- `@Inject @Client`：此注解注入了一个响应式 HTTP 客户端（Micronaut 内置），用于对资源端点执行 RESTful 调用。

设置好测试套件后，我们就可以进行服务测试。在接下来的几个章节中，我们将涵盖测试方法中的所有 restfulful 调用。

### 测试创建端点

`VetResource` 有一个用于创建新 Vet 的 POST 端点。它接受请求体中的 `VetDTO`。让我们使用 HTTP 客户端创建一个兽医：

```java
@Test
@Order(1)
public void createVet(Vet vet) throws Exception {

    int databaseSizeBeforeCreate = vetRepository.findAll().size();

    VetDTO vetDTO = vetMapper.toDto(vet);
}
```

```java
// Create the Vet

HttpResponse<VetDTO> response =
    client.exchange(HttpRequest.POST("/api/vets", vetDTO),
    VetDTO.class).blockingFirst();

assertThat(response.status().getCode()).isEqualTo(
    (HttpStatus.CREATED.getCode()));
```

```java
// Validate the Vet in the database

List<Vet> vetList = (List<Vet>) vetRepository.findAll();

assertThat(vetList).hasSize(databaseSizeBeforeCreate + 1);

VetDTO testVet = vetList.get(
```

```java
// Set ID

testVet.setId(getId());

assertThat(testVet.getFirstName()).isEqualTo(FIRST_NAME);

assertThat(testVet.getLastName()).isEqualTo(LAST_NAME);
```

在前面的文中，我们创建 `VetDTO` 并调用 POST 端点。为了让响应式客户端返回项，我们使用 `blockingFirst()`。它会阻塞直到可观察发布项。

### 测试 GET 端点

服务测试是测试的下一个水平。在前面的测试中，我们在 POST 端点创建了一个 Vet。我们可以利用持久化的 Vet 来测试 GET 端点：

```java
@Test
@Order(3)
public void getAllVets() throws Exception {

    // Get all vets

    List<VetDto> vets = client.retrieve(HttpRequest.GET("/api/vets?eager=true")), VetDto.class).blockingFirst();

    VetDto testVet = vets.get(vets.size() - 1);

    assertThat(testVet.getFirstName()).isEqualToTo(FIRST_NAME);

    assertThat(testVet.getLastName()).isEqualToTo(LAST_NAME);
}
```

```java
@Test
@Order(4)
public void getVet() throws Exception {

    // Get the vet

    VetDto testVet = client.retrieve(HttpRequest.GET("/api/vets/" + vet.getId()), VetDto.class).blockingFirst();

    assertThat(testVet.getFirstName()).isEqualToTo(FIRST_NAME);

    assertThat(testVet.getLastName()).isEqualToTo(LAST_NAME);
}
```

在前面的测试中，我们正在测试两个端点：`getVet()` 和 `getAllVets()`。`getAllVets()` 返回一个列表，`getVet()` 只返回需要的对象。

### 测试更新端点

为了测试更新端点，我们将利用在服务中持久化的 Vet，因此在创建和 GET 调用之后使用它：

```java
@Test
@Order(6)
public void updateVet() throws Exception {

    int databaseSizeBeforeUpdate = vetRepository.findAll().size();

    // Update the vet

    Vet updatedVet = vetRepository.findById(vet.getId());

    updatedVet
        .firstName(UPDATED_FIRST_NAME)
```




```java
.lastName(UPDATED_LAST_NAME);

VetDTO updatedDTO = vetMapper.toDto(updatedVet);

@SuppressWarnings("unchecked")

HttpResponse<VetDTO> response =
    client.exchange(HttpRequest.PUT("/api/vets", updatedDTO), VetDTO.class)
        .onErrorReturn(t -> (HttpResponse<VetDTO>(
            (HttpClientException)t.getResponse())).blockingFirst());

assertThat(response.status().getStatusCode()).isEqualTo(
    (HttpStatus.OK.getStatusCode()));

// Validate the Vet in the database

List<Vet> vetList = (List<Vet>) vetRepository.findAll();

assertThat(vetList).hasSize(databaseSizeBeforeUpdate);

Vet testVet = vetList.get(vetList.size() - 1);

assertThat(testVet.getFirstName()).isEqualTo(UPDATED_FIRST_NAME);
```

```java
assertThat(testVet.getLastName()).isEqualTo(UPDATED_LAST_NAME);
}
```

在上述测试中，我们测试了`update()`端点。我们首先获取了持久化的兽医，然后在调用 update 端点之前更新了姓和名。最后，我们通过断言（assert）确认实际行为符合预期行为。

### 测试 delete 端点

为了测试 delete 端点，我们将利用之前的 delete 操作中持久化的兽医资源。因此，我们将在 create、GET 和 update 调用之后使用一个顺序：

```java
@Test
@Order(8)
public void deleteVet() throws Exception {
    int databaseSizeBeforeDelete = vetRepository.findAll().size();

    // 删除兽医

    @SuppressWarnings("unchecked")
    HttpResponse<DTO> response =
        client.exchange(
            HttpRequest.DELETE("/api/vets/" + vet.getId()),
            DTO.class)
        .onErrorReturn(t -> (HttpResponse<DTO>)
            (ClientResponseException)t).getResponse().blockingFirst());

    assertThat(response.status().getStatusCode()).isEqualTo(
        (HttpStatus.NO_CONTENT.getStatusCode()));

    // 验证数据库现在已为空

    List<Vet> vetList = (List<Vet>) vetRepository.findAll();

    assertThat(vetList).hasSize(databaseSizeBeforeDelete - 1);
}
```

在上述测试中，我们测试了`deleteVet()`端点。我们传递了之前持久化的`vetId`。在成功调用服务后，我们通过比较服务调用前后的数据库大小来断言确认实际行为符合预期行为。

测试套件中的测试顺序（orders）确保了我们总是从零开始，并在完成套件中的测试后保持清洁。与在测试方法级别进行设置和清理相比，这种模式在服务测试中各有优缺点。你可以在分析应用需求以及是否在测试方法级别使用套件级设置和清理后，选择合适的模式。

在下一节中，我们将探索用于集成测试的精彩 Testcontainers 世界。

## 使用 Testcontainers 进行集成测试

Testcontainers 是一个 Java 库，它优雅地将测试世界与 Docker 虚拟化结合。使用 Testcontainers 库，我们可以在测试代码中设置、实例化并注入任何 Docker 容器。这种方法为执行集成测试提供了许多途径。在测试套件或测试方法设置中，我们可以启动一个 Docker 化的数据库、Kafka 或邮件服务器或任何集成应用，执行集成测试，并在清理时销毁 Docker 化应用。通过这种模式，我们接近生产环境，同时又不会用测试后的任何副作用影响环境。

为了学习我们如何使用 Testcontainers 库，我们将在与 MongoDB 集成的`pet-clinic-reviews`微服务上进行实验。在下一节中，我们将开始在 Micronaut 应用中设置 Testcontainers。

### 在 Micronaut 应用中设置 Testcontainers

为了在`pet-clinic-reviews`微服务中使用 Testcontainers，请在项目的`pom.xml`中添加以下依赖：

```xml
<!-- Test containers -->
<dependency>
  <groupId>org.testcontainers</groupId>
  <artifactId>junit-jupiter</artifactId>
  <version>1.15.2</version>
  <scope>test</scope>
</dependency>
```

```xml
<dependency>
  <groupId>org.testcontainers</groupId>
  <artifactId>mongodb</artifactId>
  <version>1.15.2</version>
  <scope>test</scope>
</dependency>
```

通过导入 MongoDB 风格的测试容器，我们将能够利用 MongoDB Docker 工具包。在导入所需的 Testcontainers 依赖后，让我们设置一个抽象类，它可以提供集成测试所需的任何容器：

```java
public class AbstractContainerBaseTest {

    public static final MongoDBContainer MONGO_DB_CONTAINER;

    static {
        MONGO_DB_CONTAINER = new MongoDBContainer.parse("mongo:4.0.10");
        MONGO_DB_CONTAINER.start();
    }
}
```

在`AbstractContainerBaseTest`中，我们静态地在 Docker 中配置并启动 MongoDB 实例。该容器的静态性质将简化访问并避免在测试套件或测试方法级别启动过多的实例。只需极少的代码即可拉取 MongoDB Docker 镜像、启动并运行它。

在下一节中，我们将使用 Testcontainers 为`VetReviewRepository`编写集成测试。

### 使用 Testcontainers 编写集成测试

在上一节中，我们涵盖了如何使用 Testcontainers 创建一个 Docker 化的 MongoDB。我们将继续使用 Docker MongoDB 实例测试`VetReviewRepository`。让我们从测试套件和测试方法的设置开始：

```java
@Testcontainers
@TestInstance(TestInstance.Lifecycle.PER_CLASS)
@TestMethodOrder(MethodOrderer.OrderAnnotation.class)
```

```java
class VetReviewRepositoryIntegrationTest extends AbstractContainerBaseTest {

    private VetReviewRepository vetReviewRepository;

    @BeforeAll
    void init() {
        ApplicationContext context =
            ApplicationContext.run(
                PropertySource.of("test", Map.of(
                    "mongodb.uri",
                    MONGO_DB_CONTAINER.getReplicaSetUrl()
                ))
            );

        vetReviewRepository = context.getBean(VetReviewRepository.class);
    }

    @BeforeEach
    public void initTest() {
        if (!MONGO_DB_CONTAINER.isRunning()) {
            MONGO_DB_CONTAINER.start();
        }
    }
}
```

```java
@Test
@Order(1)
public void saveVetReview() {
    VetReview vetReview = new VetReview();

    String reviewId = UUID.randomUUID().toString();
    vetReview.setReviewId(reviewId);
    vetReview.setVetId(1L);
    vetReview.setRating(3);
    vetReview.setDateAdded(LocalDate.now());
    vetReview.setComment("Good vet");

    vetReviewRepository.save(vetReview);

    VetReview savedVetReview =
        vetReviewRepository.findByIdId(reviewId);

    assertThat(savedVetReview).isNotNull();
    assertThat(savedVetReview.getReviewId()).isEqualTo(reviewId);
}
```

在`saveVetReview()`测试中，我们创建一个新的兽医评论并调用`VetRepository`来持久化该评论。最后，我们通过获取并比较值来断言该评论已成功持久化。我们在测试套件中使用`@Order`模式以便清理缓存。

在本节中，我们探索了 Testcontainers 如何通过启动数据库或其他服务的 Docker 实例来简化集成测试。我们通过创建 MongoDB 测试容器为`VetRepository`实现了集成测试。

## 总结

本章从测试金字塔开始，在单元测试、服务测试和集成测试之间实现了自动化测试的良好平衡。我们从单元测试的基础知识开始，例如利用模拟（mock）和间谍（spy）编写单元测试。我们深入了如何使用 Micronaut 框架中的响应式 HTTP 客户端对各种 RESTful 端点编写服务测试。最后，我们探索了用于集成测试的精彩 Testcontainers 世界。我们使用 Testcontainer 在测试环境中实例化 MongoDB。

本章让你对 Micronaut 框架中不同级别的测试（如单元、服务或集成）有坚固的理解。在微妙而灵活的理论讨论之后，我们通过良好的实战示例增强了你在 Micronaut 框架自动化测试方面的实战技能。

在下一章中，我们将探索如何处理 Micronaut 框架中的微服务架构问题。

## 问题

1. 什么是单元测试？
2. 单元测试中的 Mock（模拟）是什么？
3. 如何使用 JUnit 在 Micronaut 框架中进行 Mock？
4. 单元测试中的 Spy（间桩）是什么？
5. 如何使用 JUnit 在 Micronaut 框架中进行 Spy？
6. 如何在 Micronaut 框架中编写服务测试？
7. 什么是测试容器（Test Containers）？
8. 如何在 Micronaut 框架中使用测试容器？
9. 如何在 Micronaut 框架中编写集成测试？

## 第 4：微服务部署

本节将探索微服务工作的下一个阶段，即部署。首先，你将关注微服务中的一些核心问题，例如服务发现、API 网关、应用配置和容错性。随后，你将使用 Docker 容器部署示例`pet-clinic`应用程序。

本节包含以下章节：

- 第 7 章：处理微服务关注的问题
- 第 8 章：部署微服务

## 7 处理微服务关注的问题

如果没有处理基础微服务关注问题（如配置管理、API 文档、服务发现、API 网关和容错性），任何微服务架构实现都是不完整的。到目前为止，我们关注的是微服务的拆解之旅，例如如何在模块化微服务中分离关注点。为了实现无缝且统一的应用访问，我们需要微服务集成并暴露一个合并的接口。合并接口使上游消费者能够像处理单一系统一样与后端微服务进行交互。

实现微服务的关键优势是容错性。按需扩展、回退（fallbacks）和断路器等容错机制使得微服务无处不在且健壮。

在本章中，我们将探索处理和实现以下微服务问题的方法：

- 配置外部化
- 编写服务 API 文档
- 实现服务发现
- 实现 API 网关
- 实现容错机制

## 技术要求

本章中的所有命令和技术指令均运行在 Windows 10 和 macOS 上。本章涵盖的代码示例可以在书籍的 GitHub 仓库中找到：<https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/Chapter07>。

需要在开发环境中安装并设置以下工具：

- Java SDK 版本 13 或更旧版本（我们使用了 Java 14）。
- Maven – 这是可选的，只有在你想使用 Maven 作为构建系统时才需要它。然而，我们建议在任何开发机器上设置 Maven。下载和安装 Maven 的指令可以在 <https://maven.apache.org/download.cgi> 处找到。
- 开发 IDE – 根据你的偏好，可以使用任何基于 Java 的 IDE，但为了编写本章，我们使用了 IntelliJ。
- Git – 下载和安装 Git 的指令可以在 <https://git-scm.com/downloads> 处找到。
- PostgreSQL – 下载和安装 PostgreSQL 的指令可以在 <https://www.postgresql.org/download/> 处找到。
- MongoDB – MongoDB Atlas 提供一个存储高达 52 MB 的免费在线数据库即服务（DBaaS）。但是，如果你更倾向于使用本地数据库，下载和安装它的指令可以在 <https://docs.mongodb.com/manual/administration/install-community/> 处找到。我们在编写本章时使用了本地安装版本。
- REST 客户端 – 可以使用任何 HTTP REST 客户端。我们使用了 Advanced REST Client Chrome 插件。
- Docker – 下载和安装 Docker 的指令可以在 <https://docs.docker.com/get-docker/> 处找到。

## 配置外部化

无论微服务应用的规模和复杂程度如何，为每个服务维护配置设置似乎都是微服务工作中最关键的方面之一。将服务配置解耦回到了我们之前关于分离关注点的讨论。在前面的章节中，我们已经看到了如何使用`application.properties`文件来处理服务配置。虽然这比不在生产代码中硬编码这些配置要进了一步，但仍然不够。

任何微服务的服务之一是敏捷性。理想的微服务在应对用户需求的任何变化，以及处理代码缺陷或网络问题时，应该是灵活且快速的。尽管如此，每个企业级应用都需要满足合规性和审计的特定需求，这意味着开发者通常不能直接从工作区将代码产物部署到生产环境。如果配置与代码逻辑解耦，那么我们就可以轻松地构建产物（不包含配置）并将其部署到许多环境中（每个环境都可以引导它自己的配置）。

在下一节中，我们将深入研究如何在 Micronaut 框架中管理分布式服务配置。

### 使用分布式配置管理实现配置的外部化

Micronaut 提供了开箱即用的分布式配置管理功能。它对 HashiCorp 的 Consul 有内置支持和集成。虽然 Consul 是服务交付工具，但它也具有存储属性的功能。在下一节中，我们将使用 Consul 键值存储来管理 pet-owner 微服务的配置。

### 在 Consul 中实现配置存储

我们将使用 Docker 化的实例。按照以下指令在 Docker 中安装和运行 Consul：

1. 确保 Docker 应用程序在你的工作区/环境中运行。然后打开终端并运行以下命令：

```bash
```



```bash
docker run -d --name consul -p 8500:8500 consul
```

等待 Docker 下载并安装。前面的命令将启动一个单节点实例并在 8500 端口上暴露。我们可以通过访问`http://localhost:8500`处的 Consul 界面来验证安装情况。

要在 Consul 中创建配置存储，请遵循以下指令：

- 打开`http://localhost:8500`处的 Consul 界面。
- 点击`Key/Value`。
- 输入`pet-owner/application.yml`。
- 在文本区域添加以下配置：

```yaml
micronaut:
  application:
    name: pet-owner
  router:
    static-resources:
      swagger:
        paths: classpath:META-INF/swagger
  datasources:
    default:
      url: jdbc:postgresql://localhost:5432/postgres
      username: postgres
      password: postgres
      driverClassName: org.postgresql.Driver
  jpa:
    default:
      countries: com.packt.domain
```

### 配置外部化（续）

通过上述步骤，我们为 pet-owner 微服务在 Consul 中建立了键值存储。

良好的做法是在 pet-owner 资源文件夹中保留这些属性的备份，因为 Docker 化的 Consul 可能会丢失配置。

我们可以通过查看 pet-owner application.yml 文件来查看配置：

![Figure 7.1](img/768b67b9430f02ca52f7bb252e468e4_216.png)

图 1 – 在 Consul 中管理 pet-owner 配置

如图 7.1 所示，我们可以在 Consul 中轻松查看/修改配置。我们可以保存编辑或删除应用程序文件（如果你想重新开始）。

### 将 pet-owner 微服务与 Consul 配置管理集成

为了将 pet-owner 微服务与 Consul 集成，我们需要在`.xml`项目中添加以下依赖：

```xml
<dependency>
  <groupId>io.micronaut</groupId>
  <artifactId>micronaut-discovery-client</artifactId>
</dependency>
```

通过引入`micronaut-discovery-client`依赖，我们可以利用开箱即用的服务发现（我们将在本章稍后部分讨论）和 Consul 集成功能。

我们还需要在 pet-owner 微资源目录下添加一个新的`bootstrap.yml`文件。引导 YAML 允许服务在启动时从外部资源加载（或引导）应用属性。为此，在 bootstrap.yml 文件中添加以下配置：

```yaml
micronaut:
  application:
    name: pet-owner
  config-client:
    enabled: true

consul:
  client:
    config:
      enabled: true
      format: yaml
      defaultZone: ${CONSUL_HOST:localhost}:${CONSUL_PORT:8500}
      path: "config/pet-owner/"
```

## 外部化配置

```yaml
registration:
  enabled: true
```

所有与 Consul 服务器相关的配置都带有关键字`consul`前缀。以下是一些需要考虑的配置：

- **defaultZone**：此参数指向 Consul 服务器。默认情况下，我们提供了 localhost 和端口 8500 作为回备方案。
- **path**：这指向 Consul 服务器上`application.yml`的相对路径。

在`bootstrap.yaml`中的这些更改将允许从 Consul 加载`pet-owner`微服务的配置。我们可以通过运行`pet-owner`微服务来验证所做的更改。在启动时，它应该与 Consul 同步以加载配置：

![](img/768b67b9430f02ca52f7bb252e4a68e4_218_0.png)

图 7.2 – Pet-owner 微服务在启动时从 Consul 加载服务配置

*注：* 当我们启动`pet-owner`微服务时，`bootstrap.yml`会通知服务从 Consul 服务器加载配置。`micronaut-discover-client`依赖中的内置组件将与 Consul 同步并加载此外部配置。

到此，你已经学会了如何使用 Micronaut 进行分布式配置管理。在下一节中，我们将使用 Micronaut 框架实现 API 文档。

## 服务 API 文档

在微服务架构中，API 文档对于直观地访问 API 信息尤为重要，因为一个应用程序可能拥有多个微服务，且每个微服务运行着多个 API 端点。**OpenAPI** 是任何 Web 服务的标准。**Swagger 框架**作为 OpenAPI 的实现，可以轻松集成到 Micronaut 微服务中。我们可以使用 Swagger 轻松地记录所有的服务端点。在接下来的章节中，我们将探索如何将 Swagger 集成到`pet-owner microservice`中。

### 使用 Swagger 文档 pet-owner 服务端点

要在`pet-owner microservice`中开始使用 Swagger，我们首先需要将以下依赖导入到 pom.xml 项目中中：

```xml
<!-- Swagger -->
<dependency>
  <groupId>io.swagger.core.v3</groupId>
  <artifactId>swagger-annotations</artifactId>
  <version>${swagger.version}</version>
  <scope>compile</scope>
</dependency>
```

通过导入上述依赖，我们可以利用`pet-owner`微服务中的 Swagger v3 工具箱。我们可以在提示符属性部分配置`swagger.version`。我们还需要修改注解处理，以便使注解处理器能够在编译时生成 Swagger 产物。在`maven-compiler-plugin`的注解处理路径中添加以下路径：

```xml
<path>
  <groupId>io.micronaut.openapi</groupId>
  <artifactId>micronaut-openapi</artifactId>
  <version>2.3.1</version>
</path>
```

将`micronaut-openapi`添加到注解处理路径将使`maven-compile`为项目构建 Swagger 产物。一旦你对项目提示符进行了更改，请在主类中添加以下注解：

```java
@OpenAPIDefinition(
  info = @Info(
    title = "pet-owner-service",
    version = "1.0",
    description = "Pet Owner APIs"
  )
)
@Singleton
public class Application {
  ...
}
```

`@OpenAPIDefinition`注解将在生成的源中创建一个符合`<title>-<version>.yml`模式的 Swagger 产物。在我们的案例中，当我们构建项目时，将创建一个`pet-owner-service-1.0.yml` Swagger 产物：

```text
pet-owner C:\Users\nirm.singh\workspace\micronaut\chapter-07\micronaut-petclinic\pet-idea
  .mvn
  src
  target
    classes
      backup
      com
      db
    META-INF
      services
        swagger
          pet-owner-service-1.0.yml
    application.yml
    bootstrap.yml
    logback.xml
  generated-sources
  generated-test-sources
  test-classes

.gitignore
Dockerfile
microaut-cli.yml
mnvw
mnvw.bat
pet-owner.iml
pom.xml
README.md
```

图 7.3 – 生成的 Swagger 产物

如图 7.3 所示，target 文件夹中存在`pet-owner-service-1.0.yml`产物。生成的纯文本产物可以在`https://editor.swagger.io/`的 Swagger Editor 中打开。

![](img/768b67b9430f02ca52f7bb252e4a68e4_222_0.png)

图 7.4 - 在编辑器中查看 YAML

使用 Swagger Editor 审查 YAML 非常直观。它为所有服务端点提供了一个简单的界面，包括尝试 API 用的选项。虽然 Micronaut 提供了一种生成 Swagger UI 视图的机制，但它非常新且需要花费大量精力。因此，使用标准的 Swagger Editor 是一个更简单、更快速的选择。

当我们有不同的产品团队处理隔离的微服务时，API 文档就大显用场了。此外，如果一个微服务暴露给终端，它必须了解有关服务的所有信息。继续这段整合之旅，在下一节中，我们将为`pet-clinic`应用程序中的微服务实现服务发现。

## 实现服务发现

在单体架构中，如果一个应用程序有多个服务，通常这些服务运行在固定且已知的位置（例如 URL 或端口）。这种对“已知”的理解与代码逻辑耦合，以实现服务间的调用。与之相反，微服务通常运行在虚拟化或容器化环境中，且端口是动态分配的。为了方便服务间的调用，我们实现了服务发现。在服务发现模式中，所有微服务都会向服务发现注册，客户端（即上游客户端）将与服务发现同步以获取所需的服务位置。此外，服务发现会对所有注册的服务进行持续健康检查。在接下来的章节中，我们将使用 Consul 实现服务发现。

### 使用 Consul 实现服务发现

要启用服务发现，你需要在 pom 项目文件中导入以下依赖。我们已经在`pet-owner`微服务中添加了它，现在也为`pet-clinic`和`pet-clinic-reviews`微服务添加：

```xml
<!-- Service discovery -->
<dependency>
  <groupId>io.micronaut</groupId>
  <artifactId>micronaut-discovery-client</artifactId>
</dependency>
```

一旦在服务中导入`micronaut-discovery-client`，我们就可以利用它的服务功能。为了与 Consul 同步服务，请在`pet-clinic`和`pet-clinic-reviews`微服务中进行以下更改：

```yaml
consul:
  client:
    registration:
      enabled: true
```

通过这些更改，我们使`pet-clinic`和`pet-clinic-reviews`微服务能够注册服务发现。Micronaut 的`micronaut-discovery-client`实现已经包含了所需的工具，因此我们不需要任何代码更改。要验证所有服务已注册到 Consul，只需运行服务，它们将按照应用程序名称自动注册，如下所示：

> 注意  
> 如果你在`pet-clinic`和`pet-clinic-microservices`中使用了 Apache Kafka，请在服务启动之前启动 Apache Kafka 的 Docker 容器。

![](img/768b67b9430f02ca52f7bb252e4a68e4_224_0.png)

## 服务共 4 个

| 搜索 | 跨搜索 | 健康状态 | 服务类型 |
|---|---|---|---|
| consul 1 Instance | | | |
| pet-clinic 1 Instance | | | |
| pet-clinic-reviews 1 Instance | | | |
| pet-owner 1 Instance | | | |

图 7.5 – Pet-clinic 应用服务发现

成功启动后，微服务将其实例注册到 Consul 服务发现。我们可以通过进入 Consul 上的服务屏幕来查看运行的服务。

虽然服务发现通过集中运行时元数据（主要是网络位置）将所有服务汇聚到一个伞下，但对于上游消费者来说仍然留了一个空白，因为我们还没有统一的接口。在下一节中，我们将为`pet-clinic`实现一个 API 网关，为所有客户端提供一个统一的接口。

## 实现 API 网关

延续之前对微服务架构中动态网络位置的讨论，我们现在将重点放在 API 网关。API 网关是一个编排服务，旨在为所有服务提供统一、无处的访问。尽管我们在后端运行了多个微服务，但 API 网关可以为上游消费者提供一个统一的接口来访问它们。对于上游消费者来说，API 网关似乎是后端唯一运行的服务。在接收到客户端请求时，API 网关将使用服务发现来决定调用哪个实例。

为了学习如何实现 API 网关，我们将在 pet-clinic 应用中添加一个 API 网关服务。由于该微服务是一个编排服务，我们可以将其命名为 pet-clinic-concierge。网关服务之后的系统组件如图 7.6 所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_225_0.png)

图 7.6 – 带有服务发现和 API 网关的 Pet Clinic 应用程序

在前面的图中，我们可以看到 pet-clinic 应用中的 API 网关和服务发现编排。pet-clinic-concierge 服务将实现 API 网关，任何服务消费者将调用网关（而不是服务或服务发现），网关将通过同步服务发现来确定服务实例。图中的双线连接器显示了实际的服务请求如何在 pet-clinic 应用内部执行。

在下一节中，我们将深入探讨如何在 pet-clinic-concierge 服务中实现 API 网关。

### 实现 API 网关服务

为了学习我们如何在 Micronaut 中实现 API 网关，我们将创建一个名为 pet-clinic-concierge 的服务项目。要生成模板代码，请按照以下说明操作：

1. 访问`https://micronaut.io/launch/`打开 Micronaut Launch。
2. 在 Application Type 下拉菜单中选择 Micronaut Application。
3. 在 Java Version 下拉菜单中选择 Java 13。
4. 在 Base Package 输入框中输入 com.packtub。
5. 在 Name 输入框中输入 pet-clinic-concierge。
6. 在 Features 多选选项中选择以下内容：
   - `config-discovery`
   - `discovery-consul`
   - `http-client`
   - `netflix-hystrix`
   - `netflix-ribbon`
   - `openapi`
7. 点击 Generate Project 并选择 Download Zip。

Micronaut 现在将为 pet-clinic-concierge 服务生成模板代码。在 Micronaut Launch 中，我们选择了发现和 OpenAPI，因此模板代码将已经启用并配置了这些功能。在下一节中，我们将探索在 pet-clinic-concierge 服务中实现统一的服务 Fac面。

### 为 API 网关实现统一的服务 Fac面

首先，我们需要将所有数据传输对象（DTOs）复制到 pet-clinic-concierge 服务中。这些 DTO 将用于实现所有 pet-clinic 服务的客户端。复制 pet-clinic-concierge 项目中的所有 DTO。然后我们可以为所有 RESTful 服务定义客户端。

在下一节中，我们将重点为 pet-owner 微服务定义客户端。

## 访问 pet-owner 资源

为了访问 pet-owner 资源，我们将在`com.packptub.micronaut.web.rest.client.petowner`包下创建客户端。对于 pet-owner 微服务中的每个资源控制器，我们都将声明一个 HTTP 客户端接口。以下是`OwnerResource`的客户端接口：

```java
@Client(id = "pet-owner")
public interface OwnerResourceClient {

    @Post("/api/owners")
    HttpResponse<OwnerDTO> createOwner(@Body OwnerDTO dto);

    @Put("/api/owners")
```



```java
HttpResponse<OwnerDTO> updateOwner(@Body OwnerDTO dto);

@Get("/api/owners")

HttpResponse<List<OwnerDTO>> getAllOwners(HttpRequest request, Pageable pageable);

@Get("/api/owners/{id}")

Optional<OwnerDTO> getOwner(@PathVariable Long id);

@Delete("/api/owners/{id}")

HttpResponse deleteOwner(@PathVariable Long id);

}
```

`@Client` 注解将实现一个具体的客户端。该客户端将与用于`pet-owner`服务的 Consul 服务集成。我们需要声明`OwnerResource`中暴露的所有 RESTful 方法及其相对路径。

尽管在构建后我们已经有了一个具体的`OwnerResourceClient`，但我们仍然需要将`OwnerResource`中的各种 RESTful 方法映射到本地控制器。该控制器将作为上游消费者的服务 Fac面 出来。对于`OwnerResourceClient`，我们可以如下创建`OwnerResourceController`：

```java
@Controller("/api")
public class OwnerResourceClientController {

    @Inject
    OwnerResourceClient ownerResourceClient;

    @Post("/owners")
    public HttpResponse<OwnerDTO> createOwner (OwnerDTO ownerDTO) {
        return ownerResourceClient.createOwner(ownerDTO);
    }

    @Put("/owners")
    HttpResponse<OwnerDTO> updateOwner(@Body OwnerDTO ownerDTO) {
        return ownerResourceClient.updateOwner(ownerDTO);
    }

    @Get("/owners")
    public HttpResponse<List<OwnerDTO>> getAllOwners(HttpRequest request, Pageable pageable) {
        return ownerResourceClient.getAllOwners(request, pageable);
    }

    @Delete("/owners/{id}")
    public Optional<OwnerDTO> getOwner(@PathVariable Long id) {
        return ownerResourceClient.getOwner(id);
    }

    @Delete("/owners/{id}")
    HttpResponse deleteOwner(@PathVariable Long id) {
        return ownerResourceClient.deleteOwner(id);
    }

}
```

在`OwnerResourceClientController`中，我们注入了`OwnerResourceClient`，因此进入控制器的任何请求将传递给客户端，客户端将调用`pet-owner`服务。同样，我们还将为其他资源实现`VetController`。

## 访问 pet-clinic 资源

为了访问`pet-clinic`资源，我们将在`com.packpub.micronaut.web.rest.client.petclinic`包下创建客户端。对于`pet-clinic`微服务中的每个资源控制器，我们都将声明一个 HTTP 客户端接口。以下是`VetResource`的客户端接口：

```java
@Client(id = "pet-clinic")
public interface VetResourceClient {

    @Post("/api/vets")
    HttpResponse<VetDTO> createVet(@Body VetDTO dto);

    @Put("/api/vets")
    HttpResponse<VetDTO> updateVet(@Body VetDTO dto);

}
```

`@Client`注解将使用服务发现中的`pet-clinic`服务实例实现具体的客户端。为了将这些方法暴露为服务 Fac面，我们将实现`VetResourceController`：

```java
@Controller("/api")
public class VetResourceClientController {

    @Inject
    VetResourceClient vetResourceClient;

    @Post("/vets")
    public HttpResponse<VetDTO> createVet(VetDTO vetDTO) {
        return vetResourceClient.createVet(vetDTO);
    }

    @Put("/vets")
    public HttpResponse<VetDTO> updateVet(VetDTO vetDTO) {
        return vetResourceClient.updateVet(vetDTO);
    }

}
```

在`VetResourceClientController`中，我们注入了`VetResourceClient`，因此进入控制器的任何请求将传递给客户端，客户端将调用`pet-clinic`服务。在下一节中，我们将重点关注实现`pet-clinic-reviews`的服务 Fac面。

## 处理微服务关注点

在这里，我们将`VetReviewResourceClient`注入到`VetReviewResourceClientController`中，发送到控制器的请求将传递给客户端，客户端将调用`pet-clinic-reviews`服务实例进行进一步处理。

在下一节中，我们将重点关注与微服务相关的容错关注点的处理。

## 实现容错机制

在微服务环境中，故障和失效是不可避免的。随着分布式组件数量的增加，每个组件内部的故障以及由于相互交互产生的故障数量随之增加。任何微服务应用都必须针对这些不幸的情况具备内置的韧性能力。在本节中，我们将探索并实现使用 Micronaut 框架中处理故障和失效的不同方法。

### 利用内置机制

Micronaut 是一个云原生框架，具有处理故障和失效的内置能力。本质上，它的容错性是由重试建议（retry advice）驱动的。重试建议提供了`@Retryable`和`@CircuitBreaker`注解，它们可以用于任何 HTTP 客户端。

### 在 HTTP 客户端中使用 @Retryable

`@Retryable`是一种简单而有效的容错机制——简单来说，它用于在失败时尝试重试。这些尝试可以在固定延迟后再次进行，并持续直到服务响应或没有剩余尝试。

通过`@Retryable`，我们可以对客户端声明进行注解。我们可以如下所示在`OwnerResource`上使用`@Retryable`：

```java
@Retryable(
    attempts = "5",
    delay = "2s",
    multiplier = "1.5",
    maxDelay = "20s"
)
@Client(id = "pet-owner")
public interface OwnerResourceClient {

}
```

通过在`OwnerResourceClient`上使用`@Retryable`，你启用了其所有方法的容错能力。如果`pet-owner`微服务宕机，`OwnerResourceClient`将尝试重新建立通信，最多五次。我们可以通过以下设置配置`@Retryable`：

- `attempts`：这表示客户端可以进行的最大重试次数。默认是 3 次。
- `delay`：标记重试之间的延迟，默认为 1 秒。
- `multiplier`：指定用于计算延迟的倍数，默认是 1。
- `maxDelay`：指定最大的总延迟，默认是 1。如果指定了，当重试达到最大延迟限制时，任何重试尝试将停止。

`@Retryable`非常适用于临时/瞬间故障，而对于长时间故障，我们需要使用断路器模式。在下一节中，我们将看到如何在使用 Micronaut 框架中使用断路器。

### 在 HTTP 客户端中使用 @CircuitBreaker

正如讨论过的，在像微服务这样高度分布的系统中，故障是不可避免的。在微服务架构中，如果某个服务宕机，还有另一种防御机制来帮助避免用请求拥塞服务流量，直到服务恢复健康。这种机制被称为断路器。在正常情况下，电路是开启的（open）并接受请求。发生故障时，计数器增加直到达到指定的阈值。达到阈值后，电路进入关闭状态（closed），服务将立即响应以避免任何超时。断路器具有一个内部轮询机制来确定服务的健康状况，如果服务是健康的，电路将重置为开启状态。

我们可以简单地使用 Micronaut 的内置注解（built-annotation）为 HTTP 客户端指定断路器。让我们在`PetResourceClient`中实现一个断路器：

```java
@Client(id = "pet-owner")
@CircuitBreaker(
    delay = "5s",
    attempts = "3",
    multiplier = "2",
    reset = "300s"
)
public interface PetResourceClient {

    @Post("/api/pets")
    HttpResponse<PetDTO> createPet(@Body PetDTO petDTO);

    @Put("/api/pets")
    HttpResponse<PetDTO> updatePet(@Body PetDTO petDTO);

    ...

}
```

在之前的断路器实现中，如果`PetResource`端点失败，`PetResourceClient`将尝试五次，第一次尝试等待 3 秒，随后的尝试使用倍数 2。在五次尝试之后，如果服务没有响应，客户端将进入关闭状态。它将在 5 分钟的重置间隔后再次尝试访问，以检查服务是否健康。

### 为 HTTP 客户端使用 @Fallback

在断路器实现中，可以使用 Feign 客户端或回退（fallbacks）。在电路关闭时，而不是抛出服务器错误，回退实现可以处理请求并正常响应。当实际服务调用可能返回回退也能返回的内容时，这种方法特别特别有效。

在以下`PetResourceClient`的断路器示例中，我们可以创建一个简单的回退，在电路关闭时处理传入的请求：

```java
@Fallback
public class PetResourceFallback implements PetResourceClient {

    @Override
    public HttpResponse<PetDTO> createPet(PetDTO petDTO) {
        return HttpResponse.ok();
    }

    @Override
    public HttpResponse<PetDTO> updatePet(PetDTO petDTO) {
        return HttpResponse.ok();
    }

    @Override
    public HttpResponse<List<PetDTO>> getAllPets(
        HttpRequest request,
        Pageable pageable
    ) {
        return HttpResponse.ok();
    }

    @Override
    public Optional<PetDTO> getPet(Long id) {
        return Optional.empty();
    }

    public HttpResponse deletePet(Long id) {
        return HttpResponse.noContent();
    }

}
```

`PetResourceFallback`拥有所有端点的默认实现，当`PetResource`无法访问时，它将提供优雅的响应。在本示例中，我们返回一个空响应。

## 总结

在在本章节中，你学习了如何在 Micronaut 框架中处理各种微服务关注点。我们通过使用 Consul 外部化配置启动了分布式配置管理。随后我们深入了如何使用 OpenAPI 和 Swagger 自动化 API 文档。最后我们讨论了服务发现和 API 网关，并在宠物诊所应用中实现了它们。最后，我们探索了容错性以及如何使用 Micronaut 框架的内置机制构建应用程序的韧性。本章为你提供了所有与服务发现、API 网关和容错相关的实战知识。在下一章中，你将探索部署微服务应用的不同方法。

## 问题

1. 什么是分布式配置管理？
2. 如何在 Consul 中实现配置存储？
3. 如何使用 Swagger 自动化 API 文档？
4. 什么是服务发现？
5. 如何在 Micronaut 框架中实现服务发现？
6. 微服务架构中的 API 网关是什么？
7. 如何在 Micronaut 框架中实现 API 网关？
8. Micronaut 中的`@Retryable`是什么？
9. Micronaut 中的`@CircuitBreaker`是什么？
10. 如何在 Micronaut 框架中实现断路器？
11. 如何在 Micronaut 中实现回退？

# 8 部署微服务

部署的字面意思是将资源投入实际行动。因此，在微服务的背景下，它意味着将微服务投入实际行动。任何服务的部署都是多步骤过程，通常涉及构建制品并将其推送到运行时环境。在微服务世界，有效的微服务部署策略至关重要。本质上，在规划部署过程中我们需要注意以下点：

- 继续采用关注点分离模式，自隔离每个微服务的制品构建过程。
- 解耦微服务内部的任何连接需求，让服务发现或靠近服务发现的实现处理微服务绑定。
- 实现一种以统一和自动的方式实例化所有微服务应用组件的无缝部署流程。

在本章中，我们将深入上述这些问题并涵盖以下主题：

- 构建容器制品
- 部署容器制品

## 部署微服务

在本章结束时，你将熟通微服务部署的这些方面。

## 技术要求

本章中的所有命令和技术指令均在 Windows 10 和 macOS 上运行。本章涵盖的代码示例可以在书籍的 GitHub 仓库中找到：

```text
https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/master/Chapter08
```



需要在开发环境中安装并设置以下工具：

- **Java SDK**：版本 13 或更高版本（我们使用了 Java 14）。
- **Maven**：根据你的偏好选择，仅在你想使用 Maven 作为构建系统时才需要。然而，我们建议在任何开发机器上都设置好 Maven。下载和安装 Maven 的指令请访问 <https://maven.apache.org/download.cgi>。
- **开发环境 IDE**：根据你的偏好选择，可以使用任何基于 Java 的 IDE，但为了本章的编写需要，我们使用了 IntelliJ。
- **Git**：下载和安装此工具的指令请访问 <https://git-scm.com/downloads>。
- **PostgreSQL**：下载和安装此工具的指令请访问 <https://www.postgresql.org/download/>。
- **MongoDB**：MongoDB Atlas 提供高达 512 MB 存储的免费在线数据库即服务。然而，如果更倾向于使用本地数据库，下载和安装它的指令可以从 <https://docs.mongodb.com/manual/administration/install-community/> 获取。我们在编写本章时使用了本地安装。
- **REST 客户端**：可以使用任何 HTTP REST 客户端。我们使用了 Advanced REST Client 插件。
- **Docker**：下载和安装 Docker 的指令请访问 <https://docs.docker.com/get-docker/>。

## 构建容器产物

部署一个应用程序的第一步是构建所有所需的产物。构建产物通常涉及检出源代码、编译并创建可部署的产物。对于微服务而言，这种可部署的形式通常是 Docker 镜像。

Docker 镜像优雅地解耦了运行时需求。Docker 镜像与平台无关，可以部署到任何运行 Docker 的宿主机上。在下一节中，我们将深入研究如何为宠物医院应用中的微服务构建 Docker 镜像。

### 使用 Jib 将 Micronaut 微服务容器化

Jib 是 Google 提供的一个容器化框架，它可以与 Maven 或 Gradle 等 Java 构建框架无缝衔接，以构建容器镜像。Jib 极大地简化了创建容器（Docker）镜像的过程。让我们快速查看创建 Docker 镜像的工作流：

![](img/768b67b9430f02ca52f7bb252e4a68e4_238_0.png)

如前面的图所示，如果不使用 Jib 构建 Docker 镜像，我们需要构建源代码并创建一个 Docker 文件。然后，Docker 守护进程将使用构建上下文创建容器镜像并将其推送到仓库/注册表。

## 部署微服务

与前面的工作流相比，Jib 如下所示简化了整个过程：

![](img/768b67b9430f02ca52f7bb252e4a68e4_239_0.png)

图 8.2 – 使用 Jib 进行 Docker 容器化

Jib 从构建文件（如项目的 `pom` 文件或 Gradle 文件）获取配置来构建容器镜像，并将其上传到配置的仓库/注册表。

在接下来的几节中，我们将使用 Jib 为微服务容器化。

### 宠物主（`pet-owner`）微服务的容器化

在 `pet-owner` 微服务中，我们将简化配置管理以使用本地的 `application.properties`。我们仍然可以使用 Consul 进行配置管理，但为了专注于容器化方面，我们选择使用本地的应用程序属性文件。

删除或备份 `bootstrap.yml` 文件并对 `application.properties` 文件进行更改：

```yaml
micronaut:
  application:
    name: pet-owner

server:
  port: 32581

router:
  static-resources:
    swagger:
      paths: classpath:META-INF/swagger
      mapping: /swagger/**

datasources:
  default:
    url: "jdbc:postgresql://host.docker.internal:5432/postgres"
    username: postgres
    password: postgres
```

```yaml
driverClassName: org.postgresql.Driver

consul:
  client:
    default-zone: "consul:8500"
    registration:
      enabled: true
```

```yaml
jpa:
  ...
```

在这些应用程序属性更改中，有几点需要考虑：

- **Datasource URL：** 我们将使用 `host.docker.internal` 而不是 `localhost` 来指向在操作系统（Docker 之外）上的 Postgres 实例。
- **Consul default-zone：** 在我们的 Docker 服务中，我们将配置一个 Consul 服务。要从 `pet-owner` Docker 容器使用 Docker 化的 Consul，我们需要指定服务名称而不是 `localhost`。
- **Port：** 我们指定了一个固定端口来运行 `pet-owner` 微服务，因为我们稍后将在部署中暴露此端口。

本质上，为了使用宿主机上的任何内容，我们应该使用 `host.docker.internal`；而要使用任何 Docker 服务容器，必须指定 Docker 服务名称。

在完成前面的应用程序配置更改后，我们可以进行容器化。为了将 `pet-owner` 微服务容器化，我们将使用 Jib。在项目的 `pom` 文件中进行以下更改：

```xml
<build>
  <plugins>
    <groupId>com.google.cloud</groupId>
    <artifactId>jib-maven-plugin</artifactId>
    <version>2.8.0</version>
    <configuration>
      <from>
        <image>openjdk:13-slim</image>
      </from>
      <to>
        <image>pet-owner:0.1</image>
      </to>
    </configuration>
  </plugins>
</build>
```

## 部署微服务

在前面的 `pom` 中，我们使用 `jib-maven-plugin` 构建容器。要为创建的镜像命名，请执行以下步骤：

1. 打开终端并切换到 `pet-owner` 根目录。
2. 在终端中输入并运行 `mvn compile jib:docker`。
3. 等待命令完成。

在终端中使用 `docker images` 命令验证 `pet-owner`：

```text
$ MING64@CA-LZ602 MING64 ~/workspace/micronaut/Chapter08
$ docker images | grep pet-owner
pet-owner:0.1 latest a65b93fdea5 24 hours ago 441MB
```

图 8.3 - 在本地注册表中验证 `pet-owner`

在前面的截图中，我们可以看到 `docker images` 的输出。`pet-owner:0.1` 镜像存储在本地注册表中。

### 宠物医院（`pet-clinic`）微服务的容器化

为了让 `pet-clinic` 微服务准备好容器，请对 `application.properties` 进行以下更改：

```yaml
micronaut:
  application:
    name: pet-clinic

server:
  port: 32582

kafka:
  bootstrap:
    servers: kafka:9092

datasources:
  default:
    url: "jdbc:postgresql://host.docker.internal:5432/postgres"
    username: postgres
    password: postgres
    driverClassName: org.postgresql.Driver

consul:
  client:
    default-zone: "consul:8500"
    registration:
      enabled: true
```

完成上述应用配置更改后，我们可以继续进行容器化。为了对 `pet-clinic` 微服务进行容器化，我们将使用 Jib。在项目的 `pom` 文件的构建设置中进行以下更改：

```xml
<build>
  <plugins>
    ....
    <plugin>
      <groupId>com.google.cloud.tools</groupId>
      <artifactId>jib-maven-plugin</artifactId>
      <version>2.8.0</version>
      <configuration>
        <from>
          <image>openjdk:13-jdk-slim</image>
        </from>
        <to>
          <image>pet-clinic-0.1-image</image>
        </to>
        <container>
          <creationTime>${build.build.timestamp}</creationTime>
        </container>
      </configuration>
    </plugin>
  </plugins>
</build>
```

在前面的 `pom` 更改中，我们使用 `jib-maven-plugin` 来构建容器镜像。`<configuration>` 部分指定了 Docker 配置，例如作为 `<from>` 镜像（指向 JDK 13）。为了命名创建的镜像，我们使用 `<to>` 并配合 `<creationTime>` 在镜像上正确地打上时间戳。

要构建镜像，请执行以下步骤：

1. 打开终端并进入 `pet-clinic` 根目录。
2. 在终端中输入并运行 `mvn compile jib:dockerBuild` 命令。
3. 等待命令完成。

前面的指令将创建一个本地 Docker 镜像，可以使用终端中的 `docker images | grep pet-clinic` 命令对其进行验证。

### 将 `pet-clinic-reviews` 微服务容器化

为了让 `pet-clinic-reviews` 微服务准备好容器化环境，请对 `application.properties` 文件进行以下更改：

```yaml
micronaut:
  application:
    name: pet-clinic-reviews
  server:
    port: 32583

kafka:
  bootstrap:
    servers: kafka:9092

mongo:
  uri: mongodb://mongodb:mongodb@host.docker.internal:27017/pet-clinic-reviews
  databaseName: pet-clinic-reviews
  collectionName: vet-reviews

consul:
  client:
    default-zone: <consul:8500>
  registration:
    enabled: true
```

以下是应用属性更改中需要考虑的几点：

- **Mongo 数据库 URI**：我们将使用 `host.docker.internal` 而不是 `localhost` 来指向安装在主机操作系统（Docker 之外）上的 Mongo DB 实例。
- **Consul 默认区域**：在我们的 Docker 服务中，我们将配置一个 Consul 服务。为了从 `pet-clinic-reviews` Docker 容器使用容器化的 Consul，我们需要指定服务名称而不是 `localhost`。
- **Kafka 服务器**：在我们的 Docker 服务中，我们将配置一个 Kafka 服务。为了从 `pet-clinic-reviews` Docker 容器使用容器化的 Kafka，我们需要指定服务名称而不是 `localhost`。
- **端口**：我们指定了一个固定端口来运行 `pet-clinic-reviews` 微服务，因为我们稍后将在部署中暴露此端口。

完成上述应用配置更改后，我们可以继续进行容器化。为了对 `pet-clinic-reviews` 微服务进行容器化，我们将使用 Jib。在项目的 `pom` 文件的构建设置中进行以下更改：

```xml
<build>
  <plugins>
    <plugin>
      <groupId>com.google.cloud.tools</groupId>
      <artifactId>jib-maven-plugin</artifactId>
      <version>2.8.0</version>
      <configuration>
        <from>
          <image>openjdk:13-jdk-slim</image>
        </from>
        <to>
          <image>pet-clinic-reviews-0.1-image</image>
        </to>
        <container>
          <creationTime>${maven.build.timestamp}</creationTime>
        </container>
      </configuration>
    </plugin>
  </plugins>
</build>
```

在前面的 `pom` 更改中，我们正在使用 `jib-maven-plugin` 来构建容器镜像。`<configuration>` 部分指定了 Docker 配置，例如 `<from>` 镜像（指向使用 JDK 13）。为了命名创建的镜像，我们使用 `<to>` 并配合 `<creationTime>` 在镜像上正确地打上时间戳。

要构建镜像，请执行以下步骤：

1. 打开终端并进入 `pet-clinic-reviews` 根目录。
2. 在终端中输入并运行 `mvn compile jib:dockerBuild` 命令。
3. 等待命令完成。

前面的指令将创建一个本地 Docker 镜像，可以使用终端中的 `docker images | grep pet-clinic-reviews` 命令对其进行验证。

### 将 `pet-clinic-concierge` 微服务容器化

为了让 `pet-clinic-concierge` 微服务准备好容器化环境，请对 `application.properties` 文件进行以下更改：

```yaml
micronaut:
  application:
    name: pet-clinic-concierge
  server:
    port: 32584
  config-client:
    enabled: true
  consul:
    client:
      default-zone: "consul:8500"
    registration:
      enabled: true
...
```

以下是应用属性更改中需要考虑的几点：

- **Consul 默认区域**：在我们的 Docker 服务中，我们将配置一个 Consul 服务。为了从 Docker 容器使用容器化的 Consul，我们需要指定服务名称而不是 `localhost`。
- **端口**：我们指定了一个固定端口来运行 `pet-clinic-reviews` 微服务，因为我们稍后将在部署中暴露此端口。

# 26 部署微服务

完成上述应用配置更改后，我们可以继续进行容器化。为了对 `pet-clinic` 微服务进行容器化，我们将使用 Jib。在项目的 `pom` 文件的构建设置中进行以下更改：

```xml
<build>
  <plugins>
    ....
    <plugin>
      <groupId>com.google.cloud.tools</groupId>
      <artifactId>jib-maven-plugin</artifactId>
      <version>2.8.0</version>
      <configuration>
        <from>
          <image>openjdk:13-jdk-slim</image>
        </from>
        <to>
          <image>pet-clinic</image>
        </to>
        <container>
          <creationTime>${build.build.timestamp}</creationTime>
        </container>
      </configuration>
    </plugin>
  </plugins>
</build>
```

在前面的配置更改中，我们使用 `jib-maven-plugin` 来构建容器镜像。`<configuration>` 部分指定了 Docker 配置，例如 `<from>` 镜像（指向 JDK 13）。为了命名创建的镜像，我们使用 `<to>` 并配合 `<creationTime>` 在镜像上正确地打上时间戳。

要构建镜像，请执行以下步骤：

1. 打开终端并进入 `pet-clinic` 根目录。



2. 在终端中输入并运行 `mvn compile jib:dockerBuild` 命令。

3. 等待命令完成。

前面的指令将创建一个本地 Docker 镜像，可以使用终端中的 `docker images | grep pet-clinic` 命令对其进行验证。

## 部署容器制品

在上一节中，我们探索了如何使用 Jib 简化微服务的容器化。在本节中，我们将深入如何使用 Docker 排来实现无缝且统一的部署。

### 使用 `docker-compose` 部署 `pet-clinic` 服务

`docker-compose` 是 Docker 生态中的工具，对于定义和部署多容器应用程序非常直观。通过简单的 YAML 语法，我们可以通过一个命令设置所有服务及其依赖项。我们将为 `pet-clinic` 应用创建一个 `docker-compose` 文件，涵盖所有必要的服务/组件，包括微服务、服务发现和 Apache Kafka 生态系统。

首先，让我们在 `docker-compose` 中定义辅助服务：

```yaml
version: '3'
consul:
  image: bitnami/consul:latest
  ports:
    - '8500:8500'
zookeeper:
  image: bitnami/zookeeper:3-debian-10
  ports:
    - 2181:2181
  volumes:
    - zookeeper_data:/pet-clinic-reviews
  environment:
    - ALLOW_ANONYMOUS_LOGIN=yes
kafka:
  image: bitnami/kafka:2-debian-10
  ports:
    - 9094:9094
  volumes:
    - kafka_data:/pet-clinic-reviews
  environment:
    - KAFKA_BROKER_ID=1
    - KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper:2181
    - ALLOW_PLAINTEXT_LISTENER=yes
    - KAFKA_LISTENERS=INTERNAL://kafka:9092,OUTSIDE://
```

`kafka:9094`

```yaml
- KAFKA_ADVERTISED_LISTENERS=INTERNAL://nkafka:9092,OUTSIDE://localhost:9094
- KAFKA_LISTENER_SECURITY_MAP=INTERNAL:PLAINTEXT,OUTSIDE:PLAINTEXT
- KAFKA_INTER_BROKER_LISTENER_NAME=INTERNAL
```

```yaml
depends_on:
  - zookeeper

kafdrop:
  image: obsidiandynamics/kafdrop
  ports:
    - 9100:9000
  environment:
    - KAFKA_BROKER_CONNECT=kafka:9092
    - JVM_OPTS=-Xms32M -Xmx64M
  depends_on:
    - kafka
```

从之前的代码中，我们看到了 `docker-compose` 文件。我们首先为 `consul` 服务发现定义了一个服务。我们将 `consul` 暴露在端口 8500。此外，我们还为 Apache Kafka 生态系统定义了服务，即 Zookeeper、Kafka 和 Kafdrop UI。一旦在 `docker-compose` 文件中定义了这些服务，我们就可以继续处理 `pet-clinic` 微服务。参考以下代码：

`pet-owner`：

```yaml
image: "pet-owner-0.1-image"
ports:
  - "32581:32581"
depends_on:
  - consul
```

`pet-clinic`：

```yaml
image: "pet-clinic-0.1-image"
ports:
  - "32582:32582"
```

## 部署微服务

```yaml
depends_on:
  - kafka
  - consul
pet-clinic-reviews:
  image: "pet-clinic-reviews-0.1-image"
  ports:
    - "32583:32583"
  depends_on:
    - kafka
    - consul
pet-clinic-concierge:
  image: "pet-clinic-concierge-0.1-image"
  ports:
    - "32584:32584"
  depends_on:
    - consul
```

在定义 `pet-clinic` 微服务的配置时，我们可以使用 `depends_on` 指定依赖项。这将确保 Docker 按照依赖顺序实例化服务。此外，对于部署每个服务，我们将使用 `pet-clinic` 微服务的 Docker 镜像。

一旦为 `pet-clinic` 应用定义了 `docker-compose` 文件，请参考以下指令部署 `pet-clinic` 应用：

1. 开启 bash 终端。
2. 切换目录到存储 `docker-compose` 文件的位置。
3. 输入并运行 `docker compose up` 命令。
4. 等待 Docker 按照 `docker-compose` 文件中的规范实例化容器。

在成功运行 `docker-compose` 命令后，我们可以在 Docker Dashboard 中验证 `pet-clinic` 应用，显示如下：

## 部署容器产物 231

![](img/768b67b9430f02ca52f7bb252e4a68e4_252_0.png)

图 8.5 – 在 Docker Dashboard 上验证 `pet-clinic` 的部署情况

在之前的截图中，你可以看到 `pet-clinic` 应用中所有服务的状态。你可以点击某个服务并监控日志以及访问 Web 界面（如果有）。此外，我们可以检查 `consul v1` 服务发现以确认 `pet-clinic` 微服务的健康状况。参考以下截图：

![](img/768b67b9430f02ca52f7bb252e4a68e4_252_1.png)

图 8.6 – 在服务发现中验证微服务的健康状况

在 `consul` 服务发现中，我们可以观察每个微服务实例的健康状况。在之前的截图中，我们可以看到所有 `pet-clinic` 微服务都在正常运行。

微服务容器编排是任何部署策略的基石。在本章范围内，我们涵盖了 `pet-clinic` 应用的本地 Docker 部署，但构建的容器可以使用如 `docker-compose` 等容器编排工具部署在任何地方，无论是在本地还是云环境中。

## 总结

在本章中，我们通过讨论让 Micronaut 微服务准备就绪来启动我们的理解。随后，我们深入研究了使用 Jib 为每个微服务创建容器镜像。我们学习了如何使用 `docker-compose` 定义服务容器配置，并使用单个命令无缝部署所有所需的服务组件。

本章通过提供有关容器化和自动化部署的第一手知识，增强了你在 Micronaut 微服务之旅中的部署方面。这种技能在微服务应用开发和维护中备受青睐。

在下一章中，我们将探索在 Micronaut 中监控 `pet-clinic` 应用不同方面的方法。

## 问题

1. 什么是 Jib？
2. 如何使用 Jib 在 Micronaut 中创建 Docker 容器？
3. 如何从 Micronaut 的 Docker 容器访问 localhost？
4. 如何使用 `docker-compose` 在 Micronaut 中部署多服务应用？
5. 如何对 Micronaut 微服务应用进行 Docker 容器化？

在宠物诊所（`pet-clinic`）应用的上下文中，我们将实现 ELK（Elasticsearch、Logstash、Kibana 的简称）栈用于分布式日志记录。请参考下图：

![](img/768b67b9430f02ca52f7bb252e4a68e4_259_0.png)

图 9.1 - 使用 ELK 栈进行分布式日志

在前面的图中，ELK 栈用于实现宠物诊所应用中的分布式日志记录。Logstash 将日志发送到 Elasticsearch 引擎，然后由 Kibana 使用提供用户界面。

在下一节中，我们将探索如何在 Docker 化的容器中设置 ELK 栈。

## 在 Docker 中设置 ELK

要在 Docker 中设置 ELK，请遵循以下指令操作：

1. 从 `https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/master/Chapter09/micronaut-petclinic/docker-elk` 检出 `docker-elk`。
2. 打开任意 Bash 终端（我们使用了 Git Bash）。
3. 切换目录到你检出 `docker-elk` 的位置。
4. 运行 `docker compose up -d` 命令。
5. 等待 Docker 下载镜像并实例化 ELK 容器。

上述指令将在 Docker 中启动 ELK 应用。你可以通过进入 Docker Dashboard | **Containers / Apps** 来验证安装情况，如下：

![](img/768b67b9430f02ca52f7bb252e4a68e4_260_0.png)

图 9.2 – 在 Docker Dashboard 中验证 ELK

在这里，你可以验证 ELK 的实例化。默认情况下，Elasticsearch 运行在 9200 端口，Logstash 运行在 5000 端口，Kibana 运行在 5601 端口。

在下一节中，我们将修改 `pet-clinic` 微服务，将日志发送到 Logstash 实例。

## 将 Logstash 集成到 Micronaut 微服务

为了将 Logstash 集成到 `pet-clinic` 微服务中，我们将利用 Logback。我们为 Logback 引入一个新的 appender（挂载器），该载器可以将日志发送到之前创建的 Logstash 实例。

在本地检出的 `docker-elk` 目录中，你可以验证 Logstash 已配置了以下设置：

```text
input {
  tcp {
    port => 5000
    type => syslog
    codec => json_lines
  }
}
filter {
  grok {
    match => [ "message", "%{GREEDYDATA}"] 
  }
  mutate {
    add_field => { "instance_name" => "%{app_name}-%{host}:%{app_port}" }
  }
}
out {
  stdout { # 这将记录所有消息，以便我们确认 Logstash 正在接收它们
    codec => rubydebug
  }
elasticsearch {
  hosts => [
    "${XPACK_MONITORING_ELASTICSEARCH_HOSTS}" 
  ]
  user => "${XPACK_MONITORING_ELASTICSEARCH_USERNAME}"
  password => "${XPACK_MONITORING_ELASTICSEARCH_PASSWORD}"
  index => "logstash-%{YYYY.MM.dd}"
}
}
```

在 `logstash.config` 中，我们有以下三个部分：

- **input**：Logstash 具有聚合超过 50 种不同日志源的能力。Input 配置为 Logstash 配置一个或多个输入源。在我们的配置中，我们启用了端口 5000 上的 TCP 输入。
- **filter**：Logstash 的 filter 了一种了一种简单的方法，将传入的日志转换为 filter 定义日志。这些事件随后被推送到存储。在前面的配置中，我们正在使用 grok filter 配合 mutate 向事件中添加额外信息（`app_name` 和 `app_port`）。
- **output**：output 部分配置接收源，以便 Logstash 可以将日志推送到配置的输出源。在前面的配置中，我们正在配置标准输出和 Elasticsearch 来接收生成的日志。

到目前为止，我们已经启动了一个 ELK Docker 实例，并配置了 Logstash 来接收、转换并将日志发送到 Elasticsearch。接下来，我们将在 `pet-clinic` 微服务中进行必要的修改，以便日志可以被传输到 Logstash。

## 为分布式日志记录配置微服务

为了让 `pet-clinic` 微服务聚合并将日志发送到 Logstash，我们需要在所有微服务的 `pom.xml` 文件中添加以下 `logstash-logback-encoder` 依赖：

```xml
<dependency>
  <groupId>net.logstash.logback</groupId>
  <artifactId>logstash-logback-encoder</artifactId>
  <version>6.3</version>
</dependency>
```

通过导入 `logstash-logback-encoder`，我们可以在 `logback.xml` 中利用 `net.logstash.logback.appender.LogstashTcpSocketAppender` 类。该类提供了 logstash appender，可以从微服务将日志发送到 Logstash 服务器。

通过如下添加 Logstash appender 来修改所有微服务的 `logback.xml`：

```xml
<appender name="logstash" class="net.logstash.logback.app.LogstashTcpSocketAppender">
  <destination>host.internal</destination>
  <port>5000</port>
  <encoder class="net.logstash.logback.encoder.LogstashEncoder"/>
</appender>

<root level="debug">
  <appender-ref ref="logstash"/>
  <appender-ref ref="stdout"/>
</root>
```

在前面的代码中，我们添加了 `app_name` 和 `app_port` 的属性。我们如下操作：

```xml
<property name="app_name" value="pet-clinic"/>
<property name="app_port" value="8080"/>
```

## 验证分布式日志

为了验证 Logstash 正在接收来自所有微服务的日志，我们需要重新构建 `pet-clinic` 应用。执行以下步骤：

- 在 `owner` 目录打开终端：
  1. 运行 `mvn clean docker:build`。
  2. 等待 Docker 构建并推送镜像到仓库。
- 在 `pet-clinic` 微服务目录打开终端：
  1. 运行 `mvn clean docker:build`。
  2. 等待 Docker 构建并推送镜像到仓库。
- 在 `pet-clinic-reviews` 目录打开终端：
  1. 运行 `mvn clean docker:build`。
  2. 等待 Docker 构建并推送镜像到仓库。
- 在 `pet-clinic-concierge` 目录打开终端：
  1. 运行 `mvn clean docker:build`。
  2. 等待 Docker 构建并推送镜像到仓库。
- 打开任意终端并切换到你拥有 `pet-clinic docker-compose.yml` 文件的目录：
  1. 运行 `docker compose up -d`。
  2. 等待 Docker 完成启动 `pet-clinic` 栈。

## 分布式日志、追踪和监控

一旦 `pet-clinic` 应用在 Docker 中实例化并运行，我们需要配置 Kibana 来索引并显示日志。要在 Kibana 中索引日志，请执行以下步骤：

1. 访问 `http://localhost:5601` 进入 Kibana，并使用 `docker-elk` 目录中 `.env` 文件维护的 Elasticsearch 凭登录。
2. 打开首页并点击 **Connect to your Elasticsearch index** 超链接。点击 **Connect to your Elasticsearch index** 后，Kibana 将提供一个连接索引的设置页面（见下所示）：

![](img/768b67b9430f02ca52f7bb252e4a68e4_265_0.png)

图 9.3 – 在 Kibana 中连接 Elasticsearch 索引

Kibana 提供了一个直观的用户界面来连接你的 Elasticsearch 索引。点击截图中的高亮部分并按照 Kibana 展示的步骤进行操作。

## Micronaut 微服务中的分布式日志 245

3. 当设置页面加载时，在 **Index Patterns**（索引模式）框中输入 `logstash`。
4. 点击 **Next step**（下一步）按钮并在配置设置中选择 `@timestamp`。
5. 然后，点击 **Create index pattern.**（创建索引模式）。

成功创建索引后，你可以进入 **Discover** 页面并如下所示查看日志：

![](img/768b67b9430f02ca52f7bb252e4a68e4_266_0.png)



图 9.4 – 在 Discover 中日志

在`Discover`页面，我们可以访问微服务的实时日志流。由于我们将日志事件包含了`app_name`和`app_port`，我们可以通过钻取参数来选择特定的微服务。

现在，我们已经实现了 ELK 堆栈分布式日志，它直观地提供了一个统一访问微服务日志的场所。如果任何微服务出现任何故障，你可以直接访问 Kibana 并查看/搜索日志。随着你向运行时拓扑结构添加更多微服务实例和组件，ELK 将简化日志管理。

在下一节中，我们将深入探讨分布式追踪以及我们如何在`pet-clinic`应用中实现分布式追踪。

## Micronaut 微服务中的分布式追踪

分布式追踪是系统通过收集请求从一个服务组件传输到另一个组件过程中产生的数据，来跟踪和观察分布式系统中请求执行流的能力。该追踪编译了各种指标，例如每个服务所需的时间以及端到端的执行流。时间指标可以帮助定位性能问题，确定哪个服务组件是执行流的瓶颈以及原因何。

追踪（trace）是一种类似于甘特图的数据结构，它在跨度（span）中存储追踪信息。每个 span 将保留特定服务组件中执行流的追踪。此外，一个 span 可以拥有父 span 和子 span 的引用。请参考下图：

![](img/768b67b9430f02ca52f7bb252e4a68e4_267_0.png)

图 9.5 – 分布式追踪

## Micronaut 247 中的分布式追踪

在前面的图中，我们可以看到在用户界面应用上加载 foo 页面时的追踪/跨度。它调用 Service A 来获取 foo 对象，而 Service A 又调用 Service B 和 Service C 分别获取 foo 的 Bars 和 Bazs。整个执行过程所需的时间将是各个服务组件执行时间的累计总量。

在下一节中，我们将在 pet-clinic 应用中实现分布式追踪解决方案。

## 在 Micronaut 中实现分布式追踪

为了在 Micronaut 中上手实践分布式追踪，我们将在 pet-clinic 应用中实现基于 Zipkin 的追踪。

我们将在 Docker 中运行一个 Zipkin 实例。要在 Docker 中运行 Zipkin，请以下步骤：

1. 打开任意 Bash 终端。

2. 运行`docker run -d -p 9411:9411 openzipkin/zipkin`命令。等待 Docker 下载并在端口 9411 上实例化 Zipkin。成功实例化后，你可以访问 http://localhost:9411/zipkin 来验证 Zipkin。

3. 接下来，我们将从 pet-clinic-concierge 服务开始，它是 API 网关。在 pet-clinic-concierge 的 POM 中添加以下依赖项：

```xml
<!-- Distributed tracing -->
<dependency>
  <groupId>io.micronaut</groupId>
  <artifactId>micronaut-tracing</artifactId>
  <version>${micronaut.version}</version>
  <scope>compile</scope>
</dependency>
<dependency>
  <groupId>io.zipkin.brave</groupId>
  <artifactId>brave-instrumentation-http</artifactId>
  <version>5.12.3</version>
  <scope>runtime</scope>
</dependency>
<dependency>
```

## 分布式日志、追踪与监控

```xml
<groupId>io.zipkin.reporter2</groupId>
  <artifactId>zipkin-reporter</artifactId>
  <version>2.15.0</version>
  <scope>runtime</scope>
</dependency>
<groupId>io.opentracing.brave</groupId>
  <artifactId>brave-opentracing</artifactId>
  <version>0.37.2</version>
  <scope>compile</scope>
</dependency>
```

通过导入上述依赖项，我们可以利用 Micronaut 以及第三方代码产物来实现分布式追踪。

4. 为了启用分布式追踪，我们还需要修改应用程序属性。添加与 Zipkin 相关的以下属性：

```yaml
tracing:
  zipkin:
    url: http://host.docker.internal:9411
    enabled: true
  sampler:
    probability: 1
```

上述用于 Zipkin 的应用程序属性添加在根级别。在 url 中，我们指定了运行在 localhost 上的 Zipkin Docker 实例。此外，我们将 sampler.probability 的值为 1，这将启用对所有用户请求的追踪。该概率可以降低为 0 到 1 之间的任何值，0 表示从不采样，1 表示对每个请求采样。

5. 接下来，我们需要为控制器方法标记 span。为了管理 span，我们有以下两个标签：

a. @NewSpan: 这将创建一个新的 span。

b. @ContinueSpan: 这将继续上一个 span。

## Micronaut 微服务分布式追踪 249

由于 pet-clinic-concierge 中的所有控制器都是所有上游消费者的接口，因此我们在这些方法上使用 @NewSpan。以下是 OwnerResourceController 中与 span 相关的更改：

```java
@Controller("/api")
public class OwnerResourceController {
    @Inject
    OwnerClient client;

    @NewSpan
    @Post("/owners")
    public ResponseEntity<OwnerDTO> createOwner(@SpanTag("owner.dto") OwnerDTO ownerDTO) {
            return client.createOwner(ownerDTO);
    }

    @NewSpan
    @Put("/owners")
    public ResponseEntity<OwnerDTO> updateOwner(@SpanTag("owner.dto") @Body OwnerDTO ownerDTO) {
            return client.updateOwner(ownerDTO);
    }
}
```

应该在所有 pet-owner、pet-clinic 和 pet-reviews 微服务中对客户端方法进行类似的注解更改。接下来，我们需要修改 pet-clinic 微服务以支持分布式追踪。

## 修改 pet-clinic 微服务以支持分布式追踪

继续分布式追踪，我们需要对 pet-owner、pet-clinic 和 pet-reviews 微服务的项目 POM 和应用程序属性进行所需的更改（如上一节所述）。此外，为了继续追踪，我们需要用 ContinueSpan 标签注解控制器方法。参考以下代码块：

```java
@Post("/owners")
@ExecuteOn(TaskExecutors.IO)
@ContinueSpan
public ResponseEntity<OwnerDTO> createOwner(@Body OwnerDTO ownerDTO) throws URISException {

}
```

@ContinueSpan 必须注解所有微服务中的控制器方法（排除 pet-clinic-concierge，它是 API 网关）。@ContinueSpan 将继续上一个 span/trace。在 net-clinic-concierge 中，我们用 @NewSpan 注解 createOwner() 方法，而在 pet-owner 微服务中使用 @ContinueSpan。这些使用将实现端到端的执行流。

## 验证 pet-clinic 应用中的分布式追踪

为了验证 pet-clinic 应用中的分布式追踪，你必须运行 net-clinic 服务。我们将通过 API 网关获取所有列表。为此执行以下步骤：

1. 在任意浏览器标签页或 REST 客户端访问 http://localhost:32584/api/owners。

2. 访问 Zipkin 以验证 http://localhost:9411/zipkin 之前的 HTTP GET 调用的追踪。

3. 点击 Run Query 按钮。

4. 进入结果中的 get /api/owners 请求并点击 Show。

成功执行这些步骤后，你将看到以下界面：

# Micronaut 微服务中的分布式追踪 251

![](img/768b67b9430f02ca52f7bb252e4a68e4_272_0.png)

图 9.6 – 在 Zipkin 中查看 owners 的分布式追踪

Zipkin 提供了一个直观的用户界面来访问请求执行轨迹。你可以看到第一个请求到达了 pet-clinic-concierge，然后它被进一步推送到 pet-owner 微服务。完成请求总共耗时约 948 毫秒，其中大部分时间花在了 pet-owner 微服务上。

在下一节中，我们将重点关注分布式监控以及如何在 Micronaut 框架中实现分布式监控。

## Micronaut 微服务中的分布式监控

监控简单来说就是记录关键性能指标以增强对应用状态的可视性。通过记录并展示所有分布式组件的系统性能指标（如 CPU 使用率、线程池、内存使用和数据库连接），可以提供微服务系统在特定时间点运行情况的整体视图。微服务的特性要求监控系统的方式发生转变。我们不再依赖于主机环境工具，而是需要一个统一的监控解决方案，能够结合各种服务的性能指标并提供一个一站式接口。在本节中，我们将探索如何为 pet-clinic 应用实现分布式监控解决方案。

为了实现分布式监控，我们将使用非常流行的 Prometheus 和 Grafana 栈。让我们来看分布式监控的系统组件：

![](img/768b67b9430f02ca52f7bb252e4a68e4_273_0.png)

图 9.7 – 使用 Prometheus 和 Grafana 进行分布式监控

如前面的图所示，pet-clinic 微服务将向 Prometheus 服务器通信指标，而 Grafana 将展示用户界面。Prometheus 配置将存储在 YAML 文件中。

在下一节中，我们将从在 Docker 中设置 Prometheus 和 Grafana 开始。

### 在 Docker 中设置 Prometheus 和 Grafana

在 Docker 中实例化 Prometheus 和 Grafana 之前，我们需要为 Prometheus 定义配置，以便它可以从 pet-clinic 微服务拉取指标。你可以从 https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/master/Chapter09/micronaut-pet-clinic/docker-prometheus 查看 docker-docker-compose 和 prometheus.yml。

一旦检出到本地，你可以查看 prometheus.yml 文件如下：

```
global:
  scrape_interval: 15s
  evaluation_interval: 15s
  external_labels:
    monitor: 'pet-clinic-monitor'
scrape_configs:
  - job_name: 'prometheus'
    scrape_interval: 10s
    static_configs:
      - targets: ['host.docker.internal:9090','node-exporter:91100']
  - job_name: 'micronaut'
    metrics_path: '/metrics'
    scrape_interval: 10s
    static_configs:
      - targets: ['host.docker.internal:32581', 'host.docker.internal:32582', 'host.docker.internal:32583', 'host.docker.internal:32584']
```

## 254 分布式日志、追踪和监控

在 prometheus.yml 中，我们主要需要配置`scrape_configs`。这将负责调用微服务端点以获取指标。我们可以在`targets`中指定 pet-clinic 微服务。此外，你可以注意到`scrape_interval`为 10 秒。这将配置 Prometheus 每 10 秒获取一次指标。

接下来，按照以下指令在 Docker 中设置 Prometheus 和 Grafana：

1. 从 https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/master/Chapter09/micronaut-petclinic/docker-prometheus 检出 docker-prometheus。

2. 打开任何 Bash 终端（我们使用的是 Git Bash）。

3. 切换目录到你检出 docker-prometheus 的位置。

4. 运行`docker compose -d`。

5. 等待 Docker 下载镜像并实例化 Prometheus 容器。

这些指令将在 Docker 中启动监控应用。你可以通过进入 Docker Dashboard 的 Containers / Apps 来验证安装。

在下一节中，我们将探索如何将 pet-clinic 微服务集成到 Prometheus 中。

## 为分布式监控配置微服务

为了为 pet-clinic 微服务配置分布式监控，我们需要更新带有 Micrometer 依赖项的小项目 POM 文件。

在 pet-owner 项目的 POM 中添加以下依赖项：

```
<!-- Micrometer -->
<dependency>
  <groupId>io.micrometer</groupId>
  <artifactId>micronaut-micrometer-core</artifactId>
</dependency>
<dependency>
```

## 255 Micronaut 微服务中的分布式监控

```
<dependency>
  <groupId>io.micronaut.micrometer</groupId>
  <artifactId>micronaut-micrometer-registry-prometheus</artifactId>
</dependency>
<dependency>
  <groupId>io.micronaut</groupId>
  <artifactId>micronaut-management</artifactId>
</dependency>
```

通过导入 micronaut-micrometer 依赖项，我们可以在 pet-owner 微服务中利用分布式监控工具包。

为了向 Prometheus 暴露服务指标，我们需要在所有 pet-clinic 微服务中暴露指标端点。我们将在 com.packpub.micronaut.rest 包添加一个名为`PrometheusController`的新控制器：

```
@RequiresMetrics
@Controller("/metrics")
public class PrometheusController {
    private final PrometheusMeterRegistry;
    @Inject
    public PrometheusController(PrometheusMeterRegistry prometheusRegistry) {
        this.prometheusMeterRegistry = prometheusRegistry;
    }

    @Get
    @Produces("text/plain")
    public String metrics() {
        return prometheusMeterRegistry.scrape();
    }
}
```

PrometheusController 将在`/metrics`端点暴露`prometheusMeterRegistry.scrape()`。

`prometheusMeterRegistry.scrape()`将提供 application.properties 中配置的服务指标。

我们需要配置 application.properties 文件如下：

```
micronaut:
...
metrics:
  enabled: true
export:
  prometheus:
    enabled: true
    step: PT1M
    descriptions: true
```

```
endpoints:
  metrics:
    enabled: false
  prometheus:
    enabled: false
```



在`application.properties`中，我们启用了指标并以 Prometheus 格式导出。此外，由于我们提供了自定义的`/metrics`端点，我们禁用了属性中的默认端点。

同样，我们需要修改 Prometheus POM、添加`PrometheusController`并更新`pet-clinic`、`pet-clinic-reviews`服务的属性。之后，我们需要运行`mvn compile jib:dockerBuild`命令构建所有服务的 Docker 镜像。一旦构建并上传到本地 Docker 仓库，我们需要停用 Docker 中旧的`pet-clinic`应用并运行`docker compose up -d`来重新实例化修改后的`pet-clinic`应用。

在下一节中，我们将验证`pet-clinic`应用的分布式监控。

## 验证 `pet-clinic` 应用的分布式监控我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。验证`pet-clinic`应用的分布式监控，你必须在 Docker 中运行`pet-clinic`和 Prometheus 应用。你需要按照以下指令验证 Prometheus 与`pet-clinic`应用的集成：

1. 访问所有微服务的`/metrics`端点，验证服务是否向 Prometheus 暴露了指标。
2. 访问`http://localhost:32581/metrics`验证`pet-owner`指标。
3. 访问`http://localhost:32582/metrics`验证`pet-clinic`指标。
4. 访问`http://localhost:32583/metrics`验证`pet-clinic-reviews`指标。
5. 访问`http://localhost:32584/metrics`验证`pet-clinic-concierge`指标。
6. 导航到`http://localhost:9090/graph`并检查是否能看到`system_cpu_usage`指标。

## 258 分布式日志、追踪与监控

在成功完成上述步骤后，你将看到以下界面：

Prometheus 告警状态经典 UI

- 使用时间
- 启用查询历史
- 启用自动补全
- 使用实验编辑器
- 启用高亮
- `system_cpu_usage`执行

### 图表

| - 2h | 结束时间 | Res. (s) |
|---|---|---|
| 1.10 | | |
| 1.00 | | |
| 0.90 | | |
| 0.80 | | |
| 0.70 | | |
| 0.60 | | |
| 0.50 | | |
| 0.40 | | |
| 0.30 | | |
| 0.20 | | |
| 0.10 | | |
| 0.00 | | |
| 09:10 | 09:20 | 09:30 | 09:40 | 09:50 | 10:00 | 10:10 | 10:20 | 10:30 | 10:40 | 10:50 | 11:00 |

- `system_cpu_usage instance="host.docker.internal:32581" job="micronaut"`
- `system_cpu_usage instance="host.docker.internal:32582" job="micronaut"`
- `system_cpu_usage instance="host.docker.internal:32583" job="micronaut"`
- `system_cpu_usage instance="host.docker.internal:32584" job="micronaut"`

点击选择系列，CTRL+点击：切换多个系列。

**图 9** – 在 Prometheus 中访问`pet-clinic`应用程序的 CPU 使用率图。在之前的预检中，我们可以验证`pet-clinic`微服务能够在端点上暴露性能指标，并且 Prometheus 可以调用`/metrics`端点。Prometheus 可以看到图表，但作为系统管理员或开发者，你可能需要一个包含所有指标图表的系统仪表板。

在接下来的指令中，我们将 Grafana 与 Prometheus 服务器集成：

1. 导航到`http://localhost:3000/`并使用用户名`admin`和密码`pass`登录。
2. 登录后，导航到`http://localhost:3000/datasources`。
3. 点击添加数据源按钮。
4. 在时间序数据库列表中，选择 Prometheus。
5. 在 URL 中，提供值`http://prometheus:9090`。保持结果为默认值。
6. 点击保存并测试按钮。你应该会收到成功消息。
7. 转到 Dashboards 标签页并点击 Prometheus 2.0 stats。

在成功完成这些步骤后，你应该能看到：

![](img/768b67b9430f02ca52f7bb252e4a68e4_280_0.png)

图 9.9 – Grafana 中的 Prometheus 仪表板

如之前的截图所示，Grafana 提供了一个非常直观、统一的仪表板，用于访问`pet-clinic`应用程序所有服务组件的关键系统指标。在处理生产环境中的任何性能问题和系统故障时，一站式访问这些遥测数据非常方便。

在本节中，我们探索了什么是分布式监控以及如何在 Micronaut 框架中使用 Prometheus 和 Grafana 实现分布式监控。

## 总结

在本章中，我们从分布式日志开始，介绍了它为什么对任何微服务实现都很重要。我们为`pet-clinic`应用实现了用于分布式日志的 ELK Stack。此外，我们还深入研究了使用 Kibana 用户界面连接到 Elasticsearch 应用程序日志索引。

随后，我们探索了什么是分布式追踪，以及如何在 Micronaut 框架中使用 Zipkin 实现分布式追踪。我们还在 Zipkin 用户界面验证了 HTTP 调用的追踪。

最后，我们深入探讨了分布式监控的世界，并使用 Prometheus 和 Grafana 堆栈为`pet-clinic`应用实现了分布式监控解决方案。

本章通过分布式日志、分布式追踪和分布式监控等可观测模式，增强了你的 Micronaut 微服务之旅，让你掌握了如何在 Micronaut 框架中实现这些模式的实战知识。

在下一章中，我们将探索如何在 Micronaut 框架中实现 IoT 解决方案。

## 问题

1. 什么是微服务中的分布式日志？
2. 如何在 Docker 中运行 ELK Stack？
3. 如何在 Micronaut 框架中实现分布式日志？
4. 如何从 Micronaut 微服务连接到 Docker Logstash？
5. 什么是微服务中的分布式追踪？
6. 如何在 Micronaut 框架中实现分布式追踪？
7. 什么是微服务中的分布式监控？
8. 如何在 Docker 中运行 Prometheus 和 Grafana 堆栈？
9. 如何在 Micronaut 框架中实现分布式监控？

## 第 6：Micronaut 与 Closure 的 IoT

本节将通过一个关于物联网（IoT）的强化章节，结束 Micronaut 框架中的微服务之旅。

本节涵盖：

- 第 10 章，Micronaut 与 IoT
- 第 11 章，构建级微服务

## 10 Micronaut 与 IoT

物联网（IoT）是增长最快的技术之一。IoT 可以涵盖：

- 房屋自动化
- 制造业
- 医疗保健
- 交通运输
- 军事

在本章结束时，你将学习以下主题：

## 技术要求

需要安装以下工具：

- Java SDK：版本 13 或以上。
- Maven：如果你想使用 Maven。
- IDE：根据你的偏好，我们使用了 IntelliJ。
- Git：用于版本控制。
- PostgreSQL：用于数据库存储。
- MongoDB：如果你倾向于使用本地数据库。
- REST Client：用于测试 API。
- Docker：用于容器化。
- Amazon：用于 Alexa。

## IoT 基础

物联网（IoT）是设备或事物的网络。这些事物可以是任何东西——可以是佩戴健康监测器的人、佩戴地理定位传感器的宠物、带有轮胎压力传感器的汽车、具有语音/视觉功能的电视机或智能扬声器。IoT 还可以使用云端的高级机器学习（ML）和人工智能（AI）来提供下一级别的服务。IoT 通过数据收集让事物变得智能。底图说明了 IoT：

![](img/768b67b9430f02ca52f7bb252e4a68e4_288_0.png)

图 10.1 – 物联网（IoT）

IoT 设备具有网络功能并互联连接，因此它们构成了一个生态系统。该生态系统可以连接、发送并处理从其他事物处获取的数据。例如，当你到达家时，可以打开家里的灯。

现在我们已经学习了 IoT 的基础及其应用，让我们来了解 Alexa 技能的基础知识。

## Alexa 技能的基础知识

Alexa 是一种基于云的语音识别服务，适用于亚马逊及第三方设备制造商的数百万设备，例如电视、蓝牙扬声器、耳机、汽车等。你可以使用 Alexa 构建交互式的语音请求-响应应用程序。

Alexa 可以集成到各种应用程序中。Alexa 还具有视觉化显示响应的能力，Echo Show 是一种带有显示屏幕的 Alexa 扬声器。下图展示了 Alexa 架构：

![](img/768b67b9430f02ca52f7bb252e4a68e4_289_0.png)

### Amazon Alexa

图 10.2 – Amazon Alexa 架构

用户可以说设备的唤醒词 Alexa 并执行操作。例如，为了查询当前位置的天气，你可以说“Alexa现在的天气如何？”，你会收到回复，例如“你所在位置现在的气温是 28 度”。Alexa 技能就像 App，你可以使用 Alexa App 为特定设备启用或禁用技能。技能是基于语音的 Alexa 能力。

Alexa 可以执行以下操作：

- 设置闹钟。
- 从 Spotify、Apple Music 或 Google Music 播放音乐。
- 创建待办事项列表并添加到购物清单。
- 检查天气。
- 查看日历。
- 阅读新闻简报。
- 查询银行账户。
- 在餐厅点餐。
- 查询互联网上的事实。

这些是 Alexa 可以执行的许多事情中的几个。现在，让我们继续了解更多关于 Alexa。

## Alexa 技能的基础

使用任何语音助手或工具的用户可以使用唤醒词来打开技能或应用程序。例如，对于 Google Home，我们使用 Google 或 OK Google；对于 Apple Siri，我们使用 Hey Siri 或 Siri；对于 Amazon Alexa，我们使用 Alexa。这个唤醒词可以替换为 Amazon、Echo 或 computer。所有的 Alexa 技能都是基于语音交互模型设计的；也就是说你可以对技能说的实现你目标的短语，例如“Alexa，开灯”或“Alexa，现在的温度是多少？”。

Alexa 支持以下两种语音交互模型：

- **预构建语音交互模型**：Alexa 为每个技能为你定义短语。
- **自定义语音交互模型**：你定义用户可以用来与你的技能交互的短语。

对于我们的工作示例代码，我们将使用自定义语音交互模型。下图说明了使用自定义语音交互模型打开技能的过程：

### 打开技能

![](img/768b67b9430f02ca52f7bb252e4a68e4_291_0.png)

现在我们知道了唤醒词，紧随其后的短语是启动词，随后是调用名称（invocation name）。对于我们的示例应用程序 Pet Clinic（宠物诊），启动词将是`open`，后面是调用名称 Pet Clinic。

下图说明了话语（utterance）与意图（intent）之间的关系：

![](img/768b67b9430f02ca52f7bb252e4a68e4_291_1.png)

图 10.3 – 打开技能

图 10.4 – 打开技能

话语（utterance）是用户对 Alexa 说的以传达他们想做的事情，例如“开灯”、“现在的温度是多少？”等。用户可以用不同的方式表达相同的内容，例如“查找温度”、“当前温度”、“室外温度”、“[location] 的温度”，而 Alexa 将作为自定义语音交互模型的一部分，提供预构建的话语和相关的请求。此话语列表可以映射到请求或意图。

下图说明了带有唤醒词的自定义语音交互模型：

| 唤醒词 | 启动词 | 调用名称 |
|---|---|---|
| Alexa | open | Pet Clinic |

## 276 使用 Micronaut 进行 IoT

```json
{
  "name": "PetClinicWelcomeIntent",
  "slots": [],
  "samples": [
    "find near by pet clinics",
    "find pet clinics"
  ],
  "types": []
}
```

你可以使用 JSON 配置文件来配置意图的调用名称和示例用语。

一旦你将 JSON 文件复制到 Alexa 开发者控制的 JSON 编辑器中，点击 Save Model（保存模型），然后点击 Build Model（构建模型）并 Evaluate Model（评估模型）。

> 注意
>
> 以上配置是本章 GitHub 文件夹中的示例。
>
> 实际的架构可以从 GitHub 复制。

一旦你构建了模型，点击 Alexa 开发者控制台中的 Test（测试）并启用技能测试过程。现在，我们需要为响应开发后端代码。

使用你喜欢的 IDE 创建一个 Maven 项目。这需要以下依赖项：

```xml
<dependencies>
  <dependency>
    <groupId>com.amazon.alexa</groupId>
    <artifactId>ask-sdk</artifactId>
    <version>2.20.2</version>
  </dependency>
</dependencies>
```

## 277 Alexa 技能基础知识操作

我们将使用 Amazon 的`ask-sdk`进行后端 Java 开发。你也可以使用 Gradle 配置依赖项。可以在下面的代码查看示例 Gradle 配置：

```gradle
dependencies {
  compile 'com.amazon.alexa:alexa-skills-kit:1.1.2'
}
```

我们需要为所有的意图（intents）创建一个 Java 类。在我们的 JSON 架构中，定义了`CancelIntent`、`HelpIntent`、`StopIntent`、`NavigateHomeIntent`、`FallbackIntent`和`PetClinicWelcomeIntent`。对于每个意图，我们都需要创建一个处理器（handler）；例如，`PetClinicWelcomeIntent`应该有一个`PetClinicWelcomeIntentHandler`。处理器的名称将添加到每个意图名称的末尾。我们还必须创建一个在 JSON 架构未配置的处理器，这被称为`LaunchRequestHandler`。这是在技能启动时触发的第一个意图。以下代码说明了`LaunchRequestHandler`：

```java
public class LaunchRequestHandler implements RequestHandler {
  @Override
  public boolean canHandle(HandlerInput handlerInput) {
    return handlerInput.matches(
      (requestType (RequestHandler.class));
  }

  @Override
  public Optional<Response> handle(HandlerInput handlerInput) {
    String speechText = "Welcome to Pet Clinic, You can
      say find near by Pet Clinics";
    return handlerInput.getResponseBuilder()
      .withSpeech(speechText)
      .withSimpleCard("PetClinic", speechText)
      .withReprompt(speechText)
      .build();
  }
}
```

## 278 使用 Micronaut 进行 IoT

`LaunchRequestHandler`会在技能启动时覆盖处理器方法和响应语音消息。这在代码块中已有定义。在代码中，我们有一个名为“Welcome to Pet Clinic, you can find near by Pet Clinics”的语音文本响应，以及“PetClinic”的标题。

现在我们已经创建了处理器（`CancelStopIntentHandler`、`HelpIntentHandler`、`LaunchRequestHandler`、`PetClinicWelcomeIntentHandler`和`SessionEndedRequestHandler`），我们需要创建`StreamHandler`。`StreamHandler`是 AWS Lambda 函数的入口点。终端用户发送到 Alexa 并调用你的技能的所有请求都将通过此类。你需要从 Amazon Alexa 开发者控制台复制技能 ID。参考以下代码：



```java
public class PetClinicStreamHandler extends SkillStreamHandler {
    private static Skill getSkill() {
        return Skills.standard()
            .addRequestHandlers(
                new CancelStopIntentHandler(),
                new PetClinicWelcomeIntentHandler(),
                new HelpIntentHandler(),
                new LaunchRequestHandler(),
                new SessionEndedRequestHandler())
            .withSkillId("amzn.ask.skill.de392a0b-0a95-451a-a615-dcbalf9a42c66")
            .build();
    }
    public PetClinicStreamHandler() {
        super(getSkill());
    }
}
```

## Alexa 技能基础知识操作

借此，我们学习了如何使用流处理器以及如何调用意图处理器。让我们学习技能 ID 的使用，你可以从中获取关于技能 ID 的信息。下面的截图说明了技能 ID 在开发者控制台中的位置：

![](img/768b67b9430f02ca52f7bb252e4a68e4_300_0.png)

图 10.10 - 端点技能 ID 和默认区域

技能 ID 可以在 Alexa 开发者控制台的 Endpoint（端点）屏幕找到。下一步是为代码创建一个包含依赖的`.jar`文件。你可以执行`mvn assembly:assembly -Ddescriptor=jar-with-dependencies package`命令来创建`.jar`文件。该`.jar`文件将位于`target`目录，如下所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_301_0.png)

图 10.11 - Maven JAR 文件位置

下一步是创建 Lambda 函数，这是我们的后端服务代码。

导航到`https://console.amazon.com/lambda/`创建函数。将函数命名为`lambda_for_petclinic`，将选项设置为 Author from scratch（从零开始创建），并将运行时设置为 Java 11。用户界面如下图所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_302_0.png)

下一步是创建触发器，并将触发器配置设置为 Alexa Skills Kit，如下图所示。你需要从 Alexa 开发者控制台的 Endpoint 屏幕复制 Alexa Skill Id。此外，你需要从 Lambda 开发者控制台复制 Function ARN（Amazon 资源名称）到 Alexa 技能开发者控制台的 Endpoint。截图说明了 AWS Lambda 函数 ARN 的位置：

![](img/768b67b9430f02ca52f7bb252e4a68e4_303_0.png)

图 10.13 - AWS Function ARN

Function ARN 值必须从 Alexa 开发者控制台的 Endpoint 屏幕复制到 Default Region（默认区域）部分。图 10.10 显示的技能 ID 应该复制到 Lambda 触发器，如下所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_304_0.png)

### 添加触发器

#### 触发器配置

- Enable（启用）
- Disable（禁用）
- Skill ID

Lambda 将为 Amazon Alexa 调用你的函数添加必要的权限。一旦添加了必要的 Skill ID 并复制了 Function ARN，下一步是将`.jar`文件上传到 Lambda 函数。

## 使用 Micronaut 进行 IoT

下面的截图说明了向 Amazon Lambda 函数上传`.jar`文件的过程：

![](img/768b67b9430f02ca52f7bb252e4a68e4_305_0.png)

图 10.15 - 向 Amazon Lambda 上传代码

现在我们已经创建了第一个 Alexa 技能并上传了必要的代码，让我们测试一下。

### 测试你的代码

最后一个步骤是使用开发者控制台中的 Alexa Simulator 来测试代码。下面的截图说明了如何请求 Alexa Simulator：

![](img/768b67b9430f02ca52f7bb252e4a68e4_306_0.png)

图 10.16 - Alexa Simulator 请求/响应

请求/响应字符串接受文本或搜索。你可以在这里输入或打开“pet clinic”并“find nearby pet clinics”。你应该能在 JSON Output 1 部分看到来自 Java 代码的响应。如果你看到响应，这意味着我们成功创建了第一个基础 IoT 宠物诊所示例，包含了请求和响应。

## 将 Micronaut 与 Alexa 集成

正如我们在上一节讨论过的，在本节中，我们将开始理解如何将 Micronaut 与 Alexa 集成。Micronaut 提供了各种扩展来支持 Amazon Web Services (AWS)。这里的重点是 AWS Lambda。`micronaut-function-aws-alexa`模块包含了对 Micronaut 构建 Alexa 技能的支持。Micronaut Alexa 的支持可以通过`AlexaFunction`将你的 Alexa 应用接起来，并支持以下类型的依赖注入：

- `com.amazon.ask.dispatcher.handler.RequestHandler`
- `com.amazon.ask.dispatcher.request.interceptor`
- `com.amazon.ask.dispatcher.exception.ExceptionHandler`
- `com.amazon.ask.builder.SkillBuilder`

Micronaut 的`aws-alexa`模块简化了我们使用 Java、Kotlin 或 Groovy 开发 Alexa 技能的方法。以下是`aws-alexa`模块的 Maven 依赖：

```xml
<dependency>
    <groupId>io.micronaut</groupId>
    <artifactId>micronaut-aws-alexa</artifactId>
</dependency>
```

正如我们在前面的章节中学到的，Micronaut 使用 Java 注解。要更改任何 Alexa Java 处理器使其能够与 Micronaut 配合，我们只需要添加必要的`@Singleton`注解；即`java.inject.Singleton`。带有`Singleton`注解的`LaunchRequestHandler`示例如下：

```java
@Singleton
public class LaunchRequestHandler implements RequestHandler {
    @Override
    public boolean canHandle(HandlerInput handlerInput) {
        return handlerInput.matches(
            (requestType (LaunchRequest.class));
    }
    @Override
    public Optional<Response> handle (HandlerInput handlerInput) {
```

```java
String speechText = "Welcome to Pet Clinic, You can
find near by Pet Clinics";
return handlerInput.getResponseBuilder()
    .withSpeech(speechText)
    .withSimpleCard("PetClinic", speechText)
    .withReprompt(speechText)
    .build();
```

借助 Micronaut，你可以轻松地对意图（intents）进行单元测试。这是因为`@MicronautTest`注解提供了无缝的单元测试。在这里我们可以将处理器注入到单元测试用例中。Micronaut 框架利用 Amazon `LaunchRequest`类执行以下操作：

```java
@MicronautTest
@Inject
public class LaunchRequestIntentHandlerTest {
    @Test
    void testLaunchRequestIntentHandler() {
        LaunchRequest builder = LaunchRequest.builder().build();
        HandlerInput input = HandlerInput.builder()
            .withRequestEnvelope(RequestEnvelope.builder()
            .withRequest(request).build()).build();

        assertTrue(handler.canHandle(input));
        Optional<Response> responseOptional = handler.handle(input);
        assertTrue(responseOptional.isPresent());
        Response response = responseOptional.get();
```

```java
assertTrue(response.getOutputSpeech() instanceof SmlOutputSpeech);
String speechText = "Welcome to Pet Clinic, You can
say find by Pet Clinics";
String expectedSml = "<speak>" + speechText + "</speak>";
assertEquals(expectedSml, ((SmlOutputSpeech))
response.getOutputSpeech()).getSml());
assertNotNull(response.getReprompt());
assertNotNull(response.getReprompt().getOutputSpeech());
assertTrue(response.getReprompt().getOutputSpeech() instanceof SmlOutputSpeech);
assertEquals(expectedSml, ((SmlOutputSpeech))
response.getReprompt().getOutputSpeech()).getSml());
assertTrue(response.getCard() instanceof SimpleCard);
assertEquals("PetClinic", ((SimpleCard))
response.getCard()).getTitle());
assertEquals(speechText, ((SimpleCard))
response.getCard()).getContent());
assertFalse(response.getShouldEndSession());
```

你可以在本书的 GitHub 仓库中找到`petclinic-alexamicronaut-maven`项目的完整工作示例。你可以在处理器中连接到 Web 服务或后端数据库以发送请求并接收响应。下面的图展示了 Alexa 技能与后端集成的设计：

![](img/768b67b9430f02ca52f7bb252e4a68e4_310_0.png)

图 10.17 – 使用自定义后端的 Alexa 技能

你的后端逻辑可以嵌入在意图处理器中。例如，为了查找宠物诊所的位置，你可以调用 Web 服务并将其作为`speechText`的响应，如下代码片段所示：

```java
@Override
public Optional<Response> handle(HandlerInput handlerInput) {
    String speechText = service.getPetClinicLocation();
    return handlerInput.getResponseBuilder()
        .withSpeech(speechText)
        .withSimpleCard("PetClinic", speechText)
        .withReprompt(speechText)
        .build();
}
```

`searchText`处理方法可以从微服务调用添加，并从数据库或服务检索信息。

现在我们已经将 Micronaut 与 Alexa 集成，我们可以通过语音和 Micronaut 微服务来控制 IoT 设备。

## 总结

在本章中，我们探索了如何使用 IoT 和 Amazon Alexa 的基础。然后，我们创建了一个 Micronaut 微服务并与 Amazon Alexa 集成。通过这种集成，我们可以通过语音和 Micronaut 微服务控制 IoT 设备。

本章增强了你在 IoT 领域的 Micronaut 微服务之旅。它让你具备了 IoT 的第一手知识。

在下一章中，我们将通过架构设计、扩展和部署，将学到的所有主题提升到一个高度。

## 问题

1. 什么是 IoT？
2. 列举几个设备。
3. 什么是 Alexa 技能？
4. 什么是意图（intents）？
5. Alexa 支持哪些编程语言？
6. 默认类是什么？
7. 对于企业级微服务，你需要做出的哪种更改？

## 技术要求

本章中的所有命令和技术指令都可以在 Windows 10 和 Mac OS X 上运行。本章中的代码示例可以在本书的 GitHub 仓库中找到：`https://github.com/PacktPublishing/Building-Microservices-with-Micronaut/tree/master/Chapter11`。

在你的开发环境中安装并设置以下工具：

- Java SDK：版本 8 或更早版本（我们使用了 Java 13）。
- Maven：这是可选的，只有在你想使用 Maven 作为构建系统时才需要。然而，我们建议在任何开发机器上都安装 Maven。下载和安装 Maven 的指令可以在`https://maven.apache.org/download.cgi`找到。
- 开发 IDE：根据你的喜好可以使用任何基于 Java 的 IDE，但本章使用的是 IntelliJ。
- Git：下载和安装 Git 的指令可以在`https://git-scm.com/downloads`找到。
- PostgreSQL：下载和安装 PostgreSQL 的指令可以在`https://www.postgresql.org/download/`找到。
- MongoDB：MongoDB Atlas 提供免费的在线数据库即服务以及高达 512 MB 的存储空间。然而，如果你倾向于使用本地数据库，下载和安装 MongoDB 的指令可以在`https://docs.mongodb.com/manual/administration/install-community/`找到。我们在编写本章时使用的是本地安装版本。

### 技术要求

- **REST 客户端**：可以使用任何 HTTP REST 客户端。在本章中，我们使用了 Advanced Client Chrome 插件。
- **Docker**：下载和安装 Docker 的说明可以在`https://docs.docker.com/get-docker/`处找到。
- **Amazon**：Alexa 的 Amazon 账户：`https://developer.amazon.com/alexa`。

## 总结全文

让我们回顾一下到目前所有章节中学到的所有内容。在第 1 章“使用 Micronaut 框架入门微服务”中，我们开始在使用 Micronaut 框架的同时研究微服务。在那里，我们学习了微服务及其演进：微服务设计模式。我们学习了为什么 Micronaut 是开发微服务应用程序的最佳选择。在第 2 章“处理数据访问”中，我们学习了关于数据访问的相关工作。

我们开始了第一个宠物诊所、宠物所有者和宠物评论的 Micronaut 项目。我们学习了如何使用 Micronaut 框架集成持久化层，以及如何使用对象关系映射框架 Hibernate 框架集成关系型数据库。我们在 PostgreSQL 中创建了 Micronaut 后端，定义了实体之间的关系，映射了实体之间的关系，并创建了数据访问仓库。我们还通过 Micronaut 在数据库中实现了插入/创建、读取/获取、更新和删除的基本 CRUD 操作。之后，我们使用 MyBatis 框架集成了关系型数据库。我们还通过 MongoDB 和 Micronaut 探索了 NoSQL 数据库的功能。



在第我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。3 章“处理 RESTful Web 服务”中，我们学习了如何使用 Micronaut 处理 RESTful 服务。为我们的宠物诊所、所有者和宠物评论 Micronaut 项目增加了 RESTful Web 服务能力。我们学习了数据传输校验、错误处理、API 版本控制以及 HTTP 客户端 API。我们在服务上执行了带有 `GET`、`POST`、`PUT` 和 `DELETE` 的 RESTful 操作。

在第 4 章“微服务安全”中，我们学习了微服务的安全保护。我们通过启用安全切面创建了一个 RESTful 微服务的示例。我们学习了 Micronaut 安全的基础知识，包括：使用会话认证保护服务端点、实现基础身份验证提供程序、配置授权、授予未授权和安全访问、使用 OAuth、在 Docker 中设置 Keycloak、使用 Okta 身份提供者以及在 Micronaut 框架中启用 SSL。

在第 5 章“使用事件驱动架构集成微服务”中，我们学习了如何使用事件驱动架构集成微服务。我们学习了事件驱动架构的基础知识、使用 Apache Kafka 进行事件流，以及在宠物诊所微服务中实现事件生产者和消费者客户端。在第 6 章“微服务测试”中，我们掌握了如何使用 Micronaut 测试微服务。我们学习了在 Micronaut 框架中结合 JUnit 5 的单元测试基础、Mock 测试、服务测试、可用的测试套件以及使用 Docker 容器进行集成测试。

在第 7 章“处理微服务关注点”中，我们学习了如何处理微服务的关注点。我们学习了应用程序外部化、分布式配置管理、使用 Swagger 文档 Service API、实现服务交付、使用 Consul 创建服务发现、实现 API 网关以及使用断路器和回退机制实现容错机制。在第 8 章“部署微服务”中，我们学习了部署容器产物、使用 Jib 进行容器化、部署容器产物、使用 `docker-compose` 以及部署多服务应用。

在第 9 章“分布式日志、追踪和监控”中，我们学习了分布式日志、追踪和监控。我们还学习了日志生产者、调度器、存储和可视化工具。我们实现了 Elasticsearch、Logstash 和 Kibana。之后，我们在 Docker 中设置了 ELK，并与 Micronaut 微服务集成，并在 Micronaut 中实现了分布式追踪。最后，我们在 Docker 中设置了 Prometheus 和 Grafana。在第 10 章“使用 Micronaut 进行 IoT”中，我们学习了使用 Micronaut 进行 IoT。我们学习了 IoT Alexa、技能、空间事实、口语、意图、你的第一个 Alexa 技能、语音交互模型、将 Micronaut 与 Alexa、AWS、`AlexaFunction` 集成，以及使用 Micronaut 测试你的 `AlexaFunction`。

总结来说，我们学习了构建企业级应用所需的所有组件，包括数据库、Web 服务、容器、部署、测试、配置、监控、事件驱动架构、安全和 IoT。我们涵盖的所有工作示例都可以在本书的 GitHub 仓库中找到。

## 企业级微服务架构设计

### 章节总结

下面的图提供了本书所有章节的总结：

![](img/768b67b9430f02ca52f7bb252e4a68e4_316_0.png)

图 11.1 – 总结全文 – 章节路线图

至此，我们学习了创建 Micronaut 微服务的基础。现在我们已经熟悉了 Micronaut、必要的开发工具、测试、数据库、事件驱动架构、分布式日志、追踪、监控和 IoT，拥有创建企业级微服务所需的所有知识和技能。将在下一节学习企业级微服务的架构设计。

实现企业级微服务需要组织中多个利益相关者的理解和动力。你需要规划并分析微服务是否适合当前的问题。如果合适，那么就对该服务进行设计、开发、部署和维护。

在使用微服务之前，让我们了解什么时候不应该使用它们。问问自己以下问题：

- 你的团队了解微服务吗？
- 你的业务是否足够成熟以采用微服务？
- 你是否有敏捷 DevOps 实践和基础设施？
- 你是否拥有可扩展的本地或云端基础设施？
- 你是否有对现代工具和技术的支持？
- 你的数据库是否已准备好去中心化？
- 你是否得到了所有利益相关者的支持？

如果你对这些问题的回答都是“是”，那么就可以适配并实施微服务。实施微服务最困难的部分是基础设施。传统上，应用程序是松耦合的。当你架构微服务时，你需要在各个阶段应用多种技术。下图展示了实施微服务的阶段。

![](img/768b67b9430f02ca52f7bb252e4a68e4_317_0.png)

图 11.2 – 微架构架构实施阶段

我们将在后续章节中查看这些内容。

### 规划与分析

在创建微服务架构之前，你需要根据需求分析它是否合适。你也可以为应用程序的一部分实现微服务。

从传统的单体架构转向微服务是一个耗时且复杂的过程。但如果规划得当，就可以无缝实施。获得所有利益相关者的支持至关重要，这可以在规划和分析阶段完成。团队成员具备微服务知识也是至关重要的，是成功的关键因素。

### 开发

开发是微服务实施过程中至关重要的阶段。开发时请始终使用最新的稳定且受支持的版本。使用 Micronaut 框架来执行各个层级的自动化测试，例如单元测试、服务测试和集成测试。在第 6 章“微服务测试”中，我们学习了如何测试微服务。在这里，我们了解到在开发过程中，你应该始终使用容器或云基础设施来模拟真实环境，并使用模拟（mocking）和间谍（spying）概念。

如果你为每个服务创建一个版本控制策略，那么该服务就可以存储在独立的仓库中，并带有所需的配置和日志。确保你同步了开发、QA、UAT 和 PROD 环境，并确保在开发的各个阶段具有完全相同的基础设施。在开发期间，如果你希望支持旧版本的微服务，请考虑微服务的兼容性。为每个微服务准备一个单独的数据库，以发挥其最大的潜力。

### 部署

涉及到部署时，你应该使用自动化工具和技术，并利用快速部署策略。我们在第 8 章“部署微服务”中学习了如何部署微服务。高效地使用容器、虚拟机、云、Jib 和 Jenkins 等工具以及基础设施——不要过度分配。最后，确保你有一套专用的微服务 DevOps 策略，以促进持续集成和持续交付（CI/CD）。

### 管理与维护

维护多个微服务是关键且复杂的。你应该通过分布式日志、追踪和监控来监控你的应用程序，正如我们在第 9 章“分布式日志、追踪和监控”中所学习的那样。使用 Elasticsearch、Logstash、Kibana、Prometheus 和 Grafana 等工具来实现。使用 Sonar DevSecOps 监控代码库的健康状况，并定期检查代码中的安全漏洞。你应该经常更新技术版本、操作系统和工具。此外，要实时监控 CPU 使用率、内存占用和存储空间。

最后，在运行时扩展你的基础设施以避免硬件的过度使用。我们将在接下来的章节中讨论如何扩展 Micronaut。

## 了解 Micronaut 的 OpenAPI

现在我们已经了解了如何构建微服务，让我们进一步了解 Micronaut 的 OpenAPI。

你可以在 <https://www.openapi.org/> 学习更多关于 OpenAPI 的信息。

既然我们已经学习了 Micronaut 的 OpenAPI，让我们了解如何在企业中扩展 Micronaut。

### 扩展 Micronaut

在设计和实现企业级应用时，需要规划扩展能力。使用微服务的最大优势之一就是可扩展性。Micronaut 服务在设计上就是一个至关重要的因素。它不仅仅是处理量——它关乎以最小的精力进行扩展。Micronaut 能够更容易识别扩展问题并解决每个微服务层面的挑战。Micronaut 微服务是单用途应用程序，可以通过组合来构建企业级软件系统。运行时扩展是企业现代化的关键因素。

扩展有三种类型：x 轴扩展、y 轴扩展和 z 轴扩展。下图说明了 x 轴（水平扩展）和 y 轴（垂直扩展）。

#### 垂直扩展

#### 水平扩展

![](img/768b67b9430f02ca52f7bb252e4a68e4_321_0.png)

增加内存、CPU、存储空间等。

图 11.3 – 垂直扩展与水平扩展的对比

水平扩展也称为 x 轴扩展。在水平扩展中，我们通过创建新的服务器或虚拟机来扩展；整个服务的基础设施都得到了扩展。例如，如果虚拟机中运行着 10 个服务，当其中一个服务需要额外容量时，我们需要添加一个包含 10 个服务的虚拟机。如果你分析这种场景，将会发现有未被使用的服务器容量，因为只有一个服务需要额外的 CPU，而不是 10 个。然而，这种类型的扩展提供了基础设施的无限扩展能力。

垂直扩展也称为 y 轴扩展。在垂直扩展中，我们通过向现有服务器添加容量来扩展。通过添加额外的 CPU、存储空间和内存来扩展容量。例如，如果虚拟机中运行着 10 个服务，如果其中一个服务需要额外的容量（如内存和 CPU），则我们需要在同一台虚拟机上添加额外的内存和 CPU。这是水平扩展和垂直扩展之间的根本区别。然而，垂直扩展有一个局限性：它无法超出特定的限制。下图说明了 x 轴（水平扩展）和 z 轴（微服务水平扩展）。

## 实现 Micronaut 微服务

### 传统水平扩展

### 微服务水平扩展

![](img/768b67b9430f02ca52f7bb252e4a68e4_322_0.png)

图 11.4 – 传统水平扩展与微服务水平扩展的对比

微服务水平扩展也称为 z 轴扩展。这与传统水平扩展几乎相同。例如，如果微服务容器环境中运行着 10 个服务，如果其中一个服务需要额外容量，我们需要添加一个微服务容器环境，而不是 10 个。如果你分析这种场景，你会发现这是对可用容量的最优利用。这种类型的扩展允许你根据自己的意愿多次扩展基础设施，是成本效益最高的方法。它的性能优于未扩展的环境。你可以使用容器进行扩展，也可以使用云基础设施进行扩展。自动伸缩（autoscaling）的能力非常强大，并且对微服务来说非常有用。

现在我们已经学习了如何扩展微服务，让我们根据所学到的知识来实现企业级微服务。

## 实现 Micronaut 微服务

现在，让我们在本章中实现已经学的内容。你可以使用本章 GitHub 仓库中的代码。我们将使用本章涵盖的项目——pet clinic 和 concierge。我们还将使用 Zipkin 容器进行分布式追踪。使用 Prometheus 进行指标和监控，并使用 ELK 容器用于 Elasticsearch、Logstash 和 Kibana。

## 构建企业级微服务

下图展示了我们将使用的项目列表：

| 名称 |
| --- |
| `docker-compose.yml` |
| `docker-elk` |
| `docker-prometheus` |
| `docker-zipkin` |
| `notes.txt` |
| `pet-clinic` |
| `pet-clinic-concierge` |
| `pet-clinic-reviews` |
| `pet-owner` |

图 11.5 – 用于我们实现的 GitHub 项目

遵循以下步骤：

1. 第一步是设置 Keycloak。请参考第 4 章“微服务安全”，将 Keycloak 设置为身份提供者以及在 Keycloak 服务器上创建客户端。

   可以使用以下命令创建 Keycloak Docker 镜像：

   ```bash
   docker run -d --name keycloak -p 8888:8080 -e KEYCLOCK_USER=micronaut -e KEYCLOCK_PASSWORD=micronaut123 jboss/keycloak
   ```

   > **注意**
   >
   > 设置 Keycloak 是一项重要的活动，请确保参考第 4 章“微服务安全”。

   一旦创建了 Keycloak 镜像，启动 Keycloak Docker 镜像。下图显示了 Keycloak 在端口 8888 上运行：

   ![](img/768b67b9430f02ca52f7bb252e4a68e4_324_0.png)

   图 11.6 – 运行中的 Docker Keycloak

2. 一旦 Keycloak 运行，则需要从“Clients | Credentials”中复制客户端密钥。进入 Keycloak | Clients | Credentials | Secret。

   下图显示了你的 Keycloak 客户端 ID 和密钥的位置：

   ![](img/768b67b9430f02ca52f7bb252e4a68e4_324_1.png)

   图 11.7 – Keycloak 门户 – 客户端 – pet-clinic 密钥

> **注意**
>
> Keycloak pet 用户和客户端应该已经设置好。请参阅第 4 节“微服务安全”以获取更多信息。

3. 更改 Keycloak 中的超时设置。进入 Keycloak 控制台 | Clients | Settings | Advanced Settings。测试示例代码建议设置为 15 分钟。

   以下屏幕展示了 Keycloak 访问令牌有效期（Access Token Lifespan）所在的位置：

   ![](img/768b67b9430f02ca52f7bb252e4a68e4_325_0.png)

   图 11.8 – Keycloak 访问令牌有效期

4. 需要复制密钥（secret），以便将其替换到 pet-clinic、pet-owner、pet-clinic-reviews 和 pet-clinic-concierge 项目中。YAML 配置文件 `client-secret` 需要根据 Keycloak 的密钥进行更新，如下截图所示。以下是必须更新的文件：

   ```text
   Chapter11/micronaut-pet-clinic/pet-clinic-reviews/src/main/resources/application.yml
   Chapter11/micronaut-pet-clinic/pet-owner/src/main/resources/application.yml
   Chapter11/micronaut-pet-clinic/pet-clinic/src/main/resources/application.yml
   Chapter11/micronaut-pet-clinic/pet-clinic-concierge/src/main/resources/application.yml
   ```

   以下截图展示了一个需要替换 client secret 的 `.yaml` 配置文件：

   ![](img/768b67b9430f02ca52f7bb252e4a68e4_326_0.png)

   图 19 – Keycloak 门户 - YAML 文件中的 client secret

5. 一旦每个 client secret 都已更新，在所有四个项目（pet-clinic-concierge、pet-clinic-reviews、pet-clinic 和 pet-owner）中执行 Maven Docker 构建。以下 Maven 命令为每个项目创建一个 Docker 镜像：

   ```bash
   mvn clean compile jib:dockerBuild
   ```

   > **注意**
   >
   > Postgres 数据库和 MongoDB 数据库必须正在运行。它们还必须包含 pet-clinic 和 pet-reviews 的数据库表。详情请参阅第 02 节“数据访问操作”。

6. 检查 Docker 设置资源。你需要 4 个 CPU 和至少 6 GB 内存。进入 Docker settings | Resources | Advanced：

   ![](img/768b67b9430f02ca52f7bb252e4a68e4_327_0.png)

创建 Docker 镜像后的下一步，是为 Kafka、Zipkin、Prometheus 和 ELK 创建 `docker-compose`。在终端或控制台中执行以下命令来创建 Docker 镜像：

```bash
docker-compose create
or docker-compose up -d
```

首先，需要为 Kafka 创建 Docker Compose。配置文件位于此处：

```text
Chapter11/micronaut-petclinic/pet-clinic-reviews/src/main/resources/kafka-zookeeper-kafdrop-docker/docker-compose.yml
```

该文件的工作方式如下：

```text
zackdwood@Zacks-MacBook-Pro kafka-zookeeper-kafdrop % docker-compose create
WARNING: The create command is deprecated. Use the up command with the --no-start flag instead.
Creating kafka-zookeeper-kafdrop-docker_zookeeper_1 ... done
Creating kafka-zookeeper-kafdrop-docker_kafka_1 ... done
Creating kafka-zookeeper-kafdrop-docker_kafdrop_1 ... done
zackdwood@Zacks-MacBook-Pro kafka-zookeeper-kafdrop %
```

图 11.11 – Docker Compose – Kafka

接下来，需要为 Zipkin 创建 Docker Compose。配置文件位于此处：

```text
Chapter11/micronaut-petclinic/docker-zipkin/docker-compose.yml
```

该文件的工作方式如下：



```text我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。Last login: Sat Jun 5 23:01 on ttys000
zackdwood@Zacks-MacBook-Pro docker-zipkin docker-compose up -d
Docker Compose is now in the Docker CLI, try `docker-compose up`
Creating network "docker-zipkin-default" with the default driver
Creating docker-zipkin_zipkin_1 ... done
zackdwood@Zacks-MacBook-Pro docker-zipkin %
```

图 11.12 – Docker Compose – Zipkin

接着，需要为 Prometheus 创建 Docker Compose。配置文件位于此处：

```text
Chapter11/micronaut-petclinic/docker-prometheus/docker-compose.yml
```

该文件的工作方式如下：

```text
Last login: Sat Jun 5 23:20 on ttys004
zackdwood@Zacks-MacBook-Pro docker-prometheus docker-compose up -d
Docker Compose is now in the Docker CLI, try `docker-compose up`
Creating network "docker-prometheus-default" with the default driver
Creating docker-prometheus_node_exporter_1 ... done
Creating docker-prometheus_1 ... done
Creating docker-prometheus_grafana_1 ... done
zackdwood@Zacks-MacBook-Pro docker-prometheus %
```

图 11.13 – Docker Compose – Prometheus

现在，需要为 ELK 创建 Docker Compose。配置文件位于此处：

```text
Chapter11/micronaut-petclinic/docker-elk/docker-compose.yml
```

该文件的工作方式如下：

```text
Last login: Sat Jun 5 23:40 on ttys000
zackdwood@Zacks-MacBook-Pro docker-elk docker-compose up -d
Docker Compose is now in the Docker CLI, try `docker-compose up`
Creating network "docker_elk_internal" with the default driver
Creating docker-elk_elasticsearch_1 ... done
Creating docker-elk_logstash_1 ... done
Creating docker-elk_kibana_1 ... done
zackdwood@Zacks-MacBook-Pro docker-elk %
```

图 14 - Docker Compose – ELK

最后，需要在父级创建 Docker Compose。你可以通过进入以下文件来实现：

```text
Chapter11/micronaut-petclinic/docker-compose.yml
```

该文件的工作方式如下：

```text
Last login: Sat Jun 5 26:00 on ttys000
zackdwood@Zacks-MacBook-Pro micronaut-petclinic docker-compose up -d
Docker Compose is now in the Docker CLI, try `docker-compose up`
Creating network "micronaut_petclinic_default" with the default driver
Creating micronaut-petclinic-consul_1 ... done
Creating micronaut-petclinic-zookeeper_1 ... done
Creating micronaut-petclinic-kafka_1 ... done
Creating micronaut-petclinic-owner_1 ... done
Creating micronaut-petclinic-concierge_1 ... done
Creating micronaut-petclinic-reviews_1 ... done
Creating micronaut-petclinic-clinic_1 ... done
zackdwood@Zacks-MacBook-Pro micronaut-petclinic %
```

图 15 - Docker Compose – Micronaut

注意安全配置使用 Keycloak 保护所有项目：

- `pet-clinic-reviews`：已保护
- `pet-clinic-concierge`：使用 Keycloak 保护
- `pet-clinic`：使用 Keycloak 保护
- `owner`

8. 在测试应用程序之前，检查所有应用程序是否都在 Docker 容器中运行。以下截图展示了应用程序成功在 Docker 容器运行：

![](img/768b67b9430f02ca52f7bb252e4a68e4_331_0.png)

9. 现在所有项目都在 Docker 中运行，让我们测试 URL 的集成情况。你可以如下从 API 网关调用所有服务：

- `pet-owner`：`http://localhost:32584/api/owners`
- `pet-clinic`：`http://localhost:32584/api/pets`
- `pet-clinic-reviews`：`http://localhost:32584/api/clinic-reviews`

一旦项目在 Docker 中运行，你就可以通过调用 Keycloak API 获取安全令牌：

```bash
curl -X POST 'http://localhost:8888/auth/realms/master/openid-connect/token/' \
-H 'Content-Type: application/x-www-urlencoded' \
--data-encode 'client_id=pet-clinic' \
--data-encode 'grant_type=password' \
--data-encode 'client_secret=PUT_CLIENT_SECRET_HERE' \
--data-encode 'scope=openid' \
--data-encode 'username=alice' \
--data-encode 'grant_type=password' \
--data-encode 'password=alice'
```

> **注意**
>
> `PUT_CLIENT_SECRET_HERE` 必须替换为 Keycloak 证书密钥。

现在，控制台的结果如下：

```text
zackdaw@Zacks-MacBook-Pro micronaut-petclinic % curl -X POST 'http://localhost:8888/realms/master/openid-connect/token' \
-H 'Content-Type: application/x-www-urlencoded' \
--data-encode 'client_id=alice' \
--data-encode 'grant_type=password' \
--data-encode 'client_secret=6e211143-c455-4b8a-b727-f07fa236d3f' \
--data-encode 'scope=openid' \
--data-encode 'username=alice' \
--data-encode 'password=alice'
```

图 11.17 – 获取 JWT 的 curl 请求

我们可以检查请求是否返回了访问令牌：

```text
zackdaw@Zacks-MacBook-Pro micronaut-petclinic % curl -X POST 'http://localhost:8888/realms/master/openid-connect/token' \
-H 'Content-Type: application/x-www-urlencoded' \
--data-encode 'client_id=alice' \
--data-encode 'grant_type=password' \
--data-encode 'client_secret=6e211143-c455-4b8a-b727-f07fa236d3f' \
--data-encode 'scope=openid' \
--data-encode 'username=alice' \
--data-encode 'password=alice'
{"access_token":"eyJhbGciOiJIUzI1NiIsInR5CI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZCI6IkpvaG4gRG9lLCiaWF0IjoxNTE2MjM5MDIyMCwwleHAiIjoxNTE2MjM5OTk5LCJz29wGU6Im9w4gaW5kZXN0IWF0LCJ0YXNlIiwiaWF0IjoxNTE2MjM5MDI5LCJleHAiOjE1MTYyMzk5OTksImF1ZCI6IjEyMzQ1Njc4OTAifQ.SflKRHSKKKKKKF2QT4fwpMeJf3POk6yJV_Qjsww5c","token_type":"Bearer","expires_in":3600}
```

图 11.18 – curl 响应 JWT

## 构建企业级微服务

10. 使用 JSON 格式化工具复制并格式化 JSON 响应。必须从格式化响应中复制 `access_token` 的值，该值将作为 JWT 传递，如下所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_333_0.png)

图 11.19 - curl 响应 JWT

11. 一旦收到 curl 的响应，你就可以将 `access_token` 的值复制到请求头中传递给服务，如下所示：

## 实现 Micronaut 微服务

![](img/768b67b9430f02ca52f7bb252e4a68e4_334_0.png)

图 11.20 – pets API 的 REST 响应

## 构建企业级微服务

现在，我们必须使用以下链接测试所有的应用程序 URL 及其集成情况：

- API 网关：`http://localhost:32584`。
- 服务发现：`http://localhost:8500/ui/dc1/services`。这将启动 Consul，如截图所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_335_0.png)

### 服务总共 5 个

![](img/768b67b9430f02ca52f7bb252e4a68e4_335_1.png)

图 11.21 – pets API 的 REST 响应

## 实现 Micronaut 微服务

分布式日志：`http://localhost:5601/app/kibana`。这将启动 Kibana 日志门户，如截图所示：

![](img/768b67b9430f02ca52f7bb252e4a68e4_336_0.png)

> **注意**
>
> Kibana 默认名为 `elastic`，密码为 `changeme`。

## 构建企业级微服务

**分布式监控：** `http://localhost:3000/?orgId=1`。这将启动 Grafana 监控工具。在第 9 章“分布式日志、追踪和监控”中有配置仪表板的详细步骤：

![](img/768b67b9430f02ca52f7bb252e4a68e4_337_0.png)

图 11.23 - 使用 Grafana 进行分布式监控

> **注意**
>
> Prometheus 默认名为 `admin`，密码为 `pass`。

分布式追踪：`http://localhost:9411/zipkin/`。接下来的截图展示了用于分布式追踪的 Zipkin 用户界面：

![](img/768b67b9430f02ca52f7bb252e4a68e4_338_0.png)

图 11.24 - 使用 Zipkin 进行分布式追踪

IDP：`http://localhost:8888/auth/` 是身份提供者，将启动作为身份提供者的 Keycloak。

Kafka Kafdrop：`http://localhost:9100/`。在这里你可以通过 Kafdrop 查看集群：

![](img/768b67b9430f02ca52f7bb252e4a68e4_339_0.png)

图 11.25 - Kafdrop 集群视图

总体而言，我们已经测试了从网关到分布式监控、追踪、日志和搜索的所有集成功能。到此，我们完成了本章的内容。在本节中，我们学习了如何在生产环境中使用 Micronaut 实现微服务。

## 总结

在本章中，我们将之前章节中学到的所有内容整合在了一起。然后，我们深入研究了企业级微服务的架构。我们还学习了微服务的扩展、不同类型的扩展及其优势。

本章增强了你的 Micronaut 微服务知识，让你能够开发生产级的应用程序。它赋予了你所有必要的技能和专业知识。我们从微服务的基础开始这段旅程，现在我们已经有了使用 Micronaut 创建企业级微服务的知识。我们希望你喜欢与我们一起学习的旅程。

## 问题

1. 在构建微服务架构时，你应该考虑哪些因素？
2. 列举几种设计模式。
3. 在微服务的设计阶段，你应该考虑哪些因素？
4. 在微服务的开发阶段，你应该考虑哪些因素？
5. 列举几种在部署阶段使用的工具。
6. 列举几种在管理和维护阶段使用的工具。
7. 扩展的不同类型有哪些？
8. 微服务架构中使用哪种类型的扩展？

## 评估

第 1 到 9 章的答案大部分是理论或实践性的。因此，读完这些章节就足以回答其中的问题了。

## 第 10 章

1. 物联网（IoT）是……
2. 列举几种设计模式。
3. 在微服务的设计阶段，你应该考虑哪些因素？
4. 在微服务的开发阶段，你应该考虑哪些因素？
5. 列举几种在部署阶段使用的工具。

……（根据 OCR 上下文，其余文本已截断）

- 云端
- Jib
- 支持持续集成和持续交付的 DevOps 策略和基础设施

我们在 *Deploy*（部署）章节中讨论过这些。

6. 以下是用于管理和维护阶段的几个工具：

- Elasticsearch
- Logstash
- Kibana
- Prometheus
- Grafana
- Sonar

我们在 *Manage and maintain*（管理与维护）章节中讨论过这些。

7. 以下是扩展缩容的类型：

- 垂直扩展
- 水平扩展
- 微服务水平扩展

我们在 *Scaling Micronaut*（扩展 Micronaut）章节中讨论过这些。

8. 使用的工具是 *Microservices Horizontal*（基于容器/服务的扩展）。

我们在 *Scaling Micronaut*（扩展 Micronaut）章节中讨论过这些。

# Packt

Packt.com

订阅我们的在线数字库，即可访问 7,000 多本书籍和视频，以及行业领先的工具，帮助您规划个人发展并提升职业生涯。更多信息请访问我们的网站。

## 为什么要订阅？

- 通过来自 4,000 多名行业专业人士的实用电子书和视频，减少学习时间，投入更多代码编写。
- 通过为您特别定制的技能计划（Skill Plans）提升您的学习。
- 每月获得一本免费电子书或视频。
- 全文搜索，方便获取关键信息。
- 复制、粘贴、打印和为内容添加书签。

您知道吗？Packt 出版的每本书都提供电子书版本，提供 PDF 和 ePub 文件。您可以在 packt.com 升级到电子书版本。作为印刷版客户，您有权获得电子版折扣。请通过 `customercare@packtpub.com` 与我们联系获取详情。

在 `www.packt.com`，您还可以阅读免费技术文章集，订阅一系列免费新闻邮件，并接收 Packt 书籍和电子书的专属折扣和优惠。

# 您可能感兴趣的其他书籍

如果您喜欢这本书，您可能对 Packt 出版的其他书籍感兴趣：

# 使用 GraalVM 增强您的应用程序

Vijay Kumar 著

ISBN：978-1-80056-490-99

- 深入理解 GraalVM 及其工作原理。
- 使用 GraalVM 的高性能优化编译器，并查看它如何在 JIT（即时编译）和 AOT（提前编译）模式下使用。
- 掌握 GraalVM 在运行时执行的各种优化。
- 使用高级工具分析并诊断代码中的性能问题。
- 使用 GraalVM 上的 Truffle 进行语言编译、嵌入、运行以及跨语言操作。
- 使用 Micronaut 和 Quarkus 等流行框架构建最优微服务，创建云原生应用。

# Spring Boot 与 Spring Cloud 微服务实战——第二版

Magnus Larsson 著

ISBN：978-1-80107-297-7

- 使用 Spring Boot 构建响应式微服务。
- 使用 Spring Cloud 开发弹性且可扩展的微服务。
- 使用 OAuth 2.1/OIDC 和 Spring Security 保护公共 API。



- 实现 Docker 以桥接开发、测试和生产之间的差距
- 使用 Kubernetes 部署和管理微服务
- 应用 Istio 改进安全性、观测性和流量管理
- 使用 JUnit、testcontainers、Gradle 和 bash 编写并运行手动及微微测试

# Packt 寻找像您这样的作者

如果您有兴趣成为 Packt 的作者，请访问 `authorspackpub.com` 立即申请。我们已与成千上万像您这样的开发者和技术专家合作，帮助他们与全球技术社区分享见解。您可以提交通用申请、申请我们正在招募作者的特定热门话题，或提交自己的想法。

# 分享您的想法

现在您已经完成了《使用 Micronaut 构建微服务》，我们非常想听听您的意见！如果您是从亚马逊购买的书籍，请点击此处直接进入该书的亚马逊评论页并分享您的反馈，或在您购买的网站上评论。

您的评论对我们和技术社区至关重要，并将帮助我们确保交付高质量的内容。

# 索引

# 符号

- `@CircuitBreaker`
  使用，在 HTTP 客户端 211, 212
- `@Fallback`
  使用，用于 HTTP 客户端 212, 213
- `@Retryable`
  使用，在 HTTP 客户端 210, 211
- 匿名访问
  授予，使用 `SecurityRule.IS_ANONYMOUS` 116-118
- Apache Kafka 203
- Apache Kafka 生态系统
  事件流 148, 249
  本地设置 150
  设置, 151, 152
- Apache Kafka 生态系统，消费者
  事件代理 148
  事件消费者 149
  事件生产者 148
  事件主题 148
  Kafka 集群 148
  Zookeeper 149
- API 网关
  实现 204
  统一服务门面，实现用于 205
- API 网关模式 9
- API 网关服务
  实现 205
- 应用
  创建，在 Okta 上 132, 133
- 应用程序配置
  外部化 193

# A

- 聚合器模式 10
- Alexa
  关于 268
  功能 268
  意图，基础 271, 272
  与 Micronaut 集成 286-290
  任务 269
  语音交互模型 269
- `AlexaFunction` 286
- Alexa 技能
  基础 269-271
  代码测试 285
- Amazon 资源名称 (ARN) 282
- Amazon Web服务 (AWS) 286
- 应用程序属性
  配置，用于 SSL 137
  用于授予匿名访问 118-120
- 人工智能 (AI) 267
- ASM 生成字节码 13
- 异步 JavaScript 和 XML (AJAX) 6
- 用于实现服务 202, 203
- Consul 配置管理
  `pet-owner` 微服务集成 196
- Consul 键值存储 197
- 容器产物
  构建 217
  部署 227
- 持续集成和持续交付 (CI/CD) 298
- 创建端
  测试 178, 179
- 授权
  配置，用于服务 116

# B

- 后端逻辑 289
- 基础认证
  实现 114-116
- 业务能力
  用于解耦设计模式 9
- 链式微服务
  模式 10
- 断路器 211
- 断路器模式 11
- 客户端
  创建，在 Keycloak 服务器上 124, 125
- 命令查询分离 (CQRS) 模式 11
- 配置
  外部化，使用分布式配置管理 193

# C

- 数据访问存储库
  创建 41, 42
- 数据库 61
- 配置存储 193

# D

- 数据管理模式
  关于 10
  命令查询分离 (CQRS) 模式 11
  每个服务数据库 10
  共享数据库模式 10

# E

- Elasticsearch, Logstash, Kibana (ELK) 设置 238, 239
- Grafana 设置 253, 254
- Prometheus 设置 253, 254
- `docker-compose`
  用于部署 `pet-clinic` 服务 228-232
- 数据传输对象 (DTOs)
  关于 77, 205
  实现 79
  用于端点 79
  用于业务 82-84
- 领域对象
  单元测试 170
- 领域/子领域模式
  用于解耦设计模式 9
  业务能力模式，使用 9
  领域/子领域模式，使用 9
- 删除端点
  测试 182, 183
- 分布式配置管理
  使用以外部化配置 193
- 分布式日志
  在 Micronaut 微服务中 237
- 分布式监控
  在 Micronaut 微服务中 252, 253
- 分布式追踪
  在 Micronaut 微服务中实现 246-299
  在 Micronaut 微服务中 246
- 实体类
  在 Micronaut 微服务中 237, 238
  `pet-clinic` 微服务，配置 241, 242
  验证，在 `pet-clinic` 应用程序 243-245

## 332 索引

## E

- 事件消费者
  - 在 `pet-clinic-reviews` 微服务中实现 156-159
  - 在 `pet-clinic-reviews` 微服务中测试 160, 161
- 事件驱动架构
  - 简介 145
- 事件流式处理 147
- 事件流式处理模型 146
- 发布/订阅模型（事件消息传递） 145, 146
- 事件驱动架构实现，组件
  - 事件 145
  - 事件代理器 145
  - 事件消费者 145
  - 事件生产者 145
- 事件生产者
  - 在 `pet-clinic-reviews` 微服务中实现 152-154
  - 在 `pet-clinic-reviews` 微服务中测试 154-156
- 事件流式处理
  - 简介 145
  - 用于集成微服务 150
  - 与 Apache Kafka 生态系统 148, 149
- 事件流式处理模型（事件消息传递）实现 146, 147
- 事件流式处理模型（事件消息传递）实现，组件
  - 事件代理器 146
  - 事件消费者 147
  - 事件生产者 146

## F

- 回退 (fallbacks) 212
- 容错机制
  - 利用内置机制 210
  - 实现 210
- `feign` 客户端 212

## G

- 通用数据保护条例 (GDPR) 297
- GET 端点
  - 测试 180
- Grafana
  - 在 Docker 中设置 253, 254

## H

- 健康保险可携带性与责任法案 (HIPAA) 297
- HelloWorld Alexa 技能
  - 创建 272-284
- hello world 项目
  - 使用 Micronaut CLI 创建 19
  - 使用 Micronaut Launch 创建 21, 22
  - 添加 `HelloWorldController` 到 20
- Hibernate 29-31
- Homebrew
  - 用于安装 Micronaut CLI 16
- HTTP 客户端
  - 使用 `@CircuitBreaker`, 211, 212
  - 使用 `@Fallback`, 212, 213
  - 使用 `@Retryable`, 210, 211
- HTTP 客户端 API
  - 使用 103
- HTTP delete 操作
  - 执行 105
- HTTP get 操作
  - 执行 103
- HTTP post 操作
  - 执行 104
- HTTP put 操作
  - 执行 104
- HTTP 请求
  - 在 Micronaut 框架中绑定 97, 98
- HTTP 服务器 API
  - 使用 97
- 用于 `pet-clinic-reviews` 微服务的容器化 223-225
- 用于 `pet-owner` 微服务的容器化 218-220
- JSON Web 令牌 (JWTs) 123
- JUnit5
  - 用于单元测试 168, 169
- 即时编译 (JIT) 编译器 13
- JWT 身份验证
  - 用于保护服务端点 123

## I

- 身份提供者
  - 简介 109
  - 设置 Keycloak 为 124
  - 设置 Okta 为 132
- 集成设计模式
  - 简介 9
  - 聚合模式 10
  - API 网关模式 9
  - 链式微服务模式 10
- 集成测试
  - 使用 Testcontainers 183
  - 使用 Testcontainers 编写 184-186
- 意图模式 271
- 物联网 (IoT) 267

## K

- Keycloak
  - 设置为身份提供者 124
- Keycloak 身份提供者
  - 用于授予访问 128-130
- Keycloak 服务器
  - 在 124, 125 上创建客户端

## L

- 本地身份提供者
  - 用于授予安全访问 120-123
- 日志聚合
  - 组件 237
- 日志聚合模式 12
- Logstash
  - 与 Micronaut 微服务集成 239-241

## J

- Java 持久 API (JPA) 31
- Jib
  - 用于 Micronaut 微服务的容器化 217, 218
  - 用于 `pet-clinic-concierge` 微服务的容器化 225-227
  - 用于 `pet-clinic` 微服务的容器化 220-222

## M

- 机器学习 (ML) 267
- mac OS
  - 安装 Micronaut CLI 15
- MacPorts
  - 用于安装 Micronaut CLI 16, 17
- 多对多关系
  - 映射 39, 40
- 多对一关系
  - 映射 36-39
- 映射对象 (mapper object)
  - 单元测试 170, 171
- 映射器 (mappers)
  - 为实体定义 52-56
  - 错误处理 99, 100
- 正在处理 hello world 项目 19
- HTTP 绑定，绑定 27, 98
- 持久化，集成 29, 30
- 微服务 77, 78, 109, 110
- 服务测试 177
- SSL，启用 135, 136
- 单元测试 167, 168
- Micronaut Launch
  - 引用 21
  - 用于创建 hello world 项目 22
- MapStruct
  - 用于定义映射器 80-82
- Micronaut
  - 开发微服务 12-14
  - 与 Alexa 集成 286-290
  - MongoDB，配置 64
  - 扩展 299-301
- Micronaut 应用
  - 创建 `pet-owner` 微服务 32, 33
  - 生成 `pet-clinic` 微服务 49, 50
  - 生成 `pet-clinic-reviews` 微服务 63
- Micronaut 微服务
  - 使用 Jib 容器化 217, 218
  - 分布式日志 237
  - 分布式监控 252, 253
  - 分布式追踪 246, 247, 249
  - 演进 5-8
  - 在 `pet-clinic` 应用中 77
  - 与事件流式处理集成 150
  - 创建 restful 端点 84-86
  - 设置 containers 183, 184
- Micronaut CLI
  - 在 mac 上安装 15
  - 在 Windows 上安装 17, 18
  - 使用 Homebrew 安装 16
  - 使用 MacPorts 安装 16, 17
  - 使用 SDKMAN! 安装 15, 16
  - 用于创建 hello world 项目 19
- Micronaut 框架
  - 简介 14
  - API 版本控制 100-102

## N

- 微服务组件
  - CLI 客户端 29
  - 仓库 29
  - 服务 29
- 微服务设计模式
  - 简介 8
  - 交叉关注模式 11
  - 数据管理模式 10
  - 解构设计模式 8
  - 集成设计模式 9
- mocks 168
  - 在单元测试中使用 177-174
- MongoDB
  - 简介 61
  - 在 Micronaut 中配置 64
  - 在 PostgreSQL 中配置 48
- MyBatis
  - 简介 47
  - CRUD 操作 58
  - 创建实体类 51, 52
  - 创建实体服务 56-58
  - 定义实体映射器 52-56
  - `pet-clinic` 微服务 49, 50
  - PostgreSQL 中生成 `pet-clinic` schema 48
- `PetOwnerClient` CRUD
  - 执行 60, 61
  - 与关系数据库集成 48

## O

- NoSQL 数据库
  - CRUD 操作 70
  - 创建数据访问仓库 66-68
  - 创建实体类 65, 66
  - 创建实体服务 68, 69
- `PetClinicReviewClient`, 创建 71, 72
- 在 MongoDB 中创建 `vet-reviews` 集合 62
- NoSQL 数据库 CRUD 操作
  - 删除操作 71
  - 执行读取/获取操作 70
  - 保存操作 71

## P

- OAuth
  - 用于保护 `pet-clinic-reviews` 微服务 137, 138
  - 用于保护服务端点 131
- 面向对象编程 5
- Okta
  - 在 132, 133 上创建应用
  - 设置为身份提供者 132
- Okta 身份提供者
  - 用于授予安全访问 138-140
- 一对一关系
  - 映射 36-38
- 一对一关系映射 34-36
- OpenAPI
  - 简介 198, 299
- OpenAPI 倡议 (OAI) 299
- ORM 框架
  - 执行 CRUD 操作 44
  - 创建数据访问仓库 41, 42
  - 创建实体类 33, 34
  - 创建实体服务 42-44
  - 在 PostgreSQL 中生成 `pet-owner` schema 32
  - 定义关系类型 34
  - 用于与关系数据库集成 30, 31
- 配置分布式日志 241, 242
- 配置分布式监控 254-256
- 修改分布式追踪 249, 250
- `pet-clinic` 资源
  - 使用基于令牌的身份验证保护 127, 128
  - 用于生成 Micronaut 应用 49, 50
- `pet-clinic` 资源
  - 访问 208
- 使用 Jib 容器化 `pet-clinic-reviews` 223-225
- 事件消费者客户端，实现 156-159
- 事件消费者，测试 160, 161
- 事件生产者客户端，实现 152-154
- 事件生产者客户端，测试 154-156
- 使用 OAuth 保护 137, 138
- 用于生成 Micronaut 应用 63
- `pet-clinic` schema
  - 在 PostgreSQL 中生成 48
- `pet-clinic` 服务
  - 使用 `docker-compose` 部署 228-233
- `pet-owner` 微服务
  - 使用 Jib 容器化 218-220
  - 与 Consul 配置管理集成 196, 197
  - 用于创建 Micronaut 应用 32, 33

## P

- 持久化
  - 与 Micronaut 框架集成 29, 30
- 个人信息和电子文档法 (PIPEDA) 297
- `pet-clinic` 应用
  - 分布式日志验证 243-245
  - 分布式监控验证 257-260
  - 分布式追踪验证 250, 251
  - 微服务 77
- `pet-clinic-concierge` 微服务
  - 使用 Jib 容器化 225-227
- `pet-clinic` 微服务
  - 简介 150

索引 337

- 宠物所有者资源
  访问 206, 207
- 宠物所有者模式 (schema)
  生成，在 PostgreSQL 中 31, 32
- 宠物所有者服务端点
  文档，使用 Swagger 198-201
- 简单 Java 对象 (POJO) 170
- PostgreSQL
  - 宠物所有者模式，生成, 32
  - 编程逻辑 274
- restful 端点
  创建，针对微服务 84
- RESTful 微服务
  在 Micronaut 框架中 77, 78, 109, 110
- 重试切面 (retry advice) 210
- 行 (row) 61
- Prometheus
  设置，在 Docker 中 253, 254
- pub/sub 模型（事件消息） 145
- pub/sub 模型（事件消息）实现
  事件驱动架构 145, 146
- pub/sub 模型（事件消息）实现，组件
  事件代理器 145
  事件消费者 146

# S

- SDKMAN!
  使用，用于安装 Micronaut CLI 15, 16
- 安全访问
  授权，使用 Keycloak 身份提供者 128-130
  授权，使用本地身份提供者 120-123
  授权，使用 Okta 身份提供者 138-140
- `SecurityFilter`
  - `AuthenticationFetcher` 111
  - `Authenticator` 111
  - `SecurityRule` 111
  - `SecurityRule.IS_ANONYMOUS`
    用于，授予匿名访问 116-118
- 服务 API
  文档化 198
- 服务发现
  实现 202
  实现，使用 Consul 202, 203
- 服务发现模式 11



- 服务端点
  - 授权，为 116 进行配置
  - 安全保护，使用 JWT 认证 123
  - 安全保护，使用 OAuth 131
  - 安全保护，使用会话认证 112, 123

# R

- 关系型数据库
  - 集成，使用 MyBatis 框架 46
  - 集成，使用 ORM 框架 30, 31
  - 关系类型
    - 定义 34
    - 多对多关系，映射 39, 40
    - 多对多关系，映射 36-38
    - 一对多关系，映射 36-38
    - 一对一关系，映射 34-36

# 索引

- 服务水平协议 (SLAs) 6
- 服务面向架构 (SOA) 6
- 服务
  - 关于 77
  - 修改，以使用 DTOs 82-84
  - 服务测试，在 Micronaut 框架中
    - 关于 177
    - 创建端点，178, 179
    - 删除端点，182, 183
    - GET 端点，测试 180
    - 测试套件，177, 178
    - 更新端点，测试 181, 182
  - 共享数据库模式
    - 使用，在数据管理模式中 10
- 简单对象访问协议 (SOAP) 6
- 槽 (slots) 272
- 软件即服务 (SaaS) 6
- 间谍 (spies)
  - 使用，在单元测试中 174-177
- 监控 (spying) 168
- SSL
  - 应用属性
    - 为 137 进行配置
  - 启用，在 Micronaut 框架中 135, 136
- Swagger
  - 使用，用于宠物所有者服务端点的文档 198-201
  - Swagger Editor 201
  - Swagger 框架 198
  - Swagger 规范 299
  - Swagger v3 工具箱 199

# T

- 表 61
- Testcontainers
  - 设置，在 Micronaut 中
    - 应用 183, 184
    - 使用，用于集成测试 183
  - 用于，编写集成测试 184-186
- 测试金字塔 166, 167
- 测试套件
  - 创建 177, 178
- 基于令牌的认证
  - 用于，安全保护宠物诊所微服务 127, 128

# U

- 统一服务外层 (BFF)
  - 实现，用于 API 网关 205
- 单元测试
  - 领域对象 170
    - 在 Micronaut 框架中 167, 168
  - 映射对象 170, 171
  - 机制 168
  - 模拟 (mocks)，使用 171-174
  - 间谍 (spies)，使用 174-177
  - 配合 JUnit5 168, 169
- 更新端点
  - 测试 181, 182
- 用户设置
  - 在客户端空间 125-127, 134
- 话用语 (utterances) 272

# V

- 兽医评论集合 (vet-reviews collection)
  - 创建，在 MongoDB 中 62
- 语音交互模型 274
- 语音交互模型，Alexa
  - 自定义 269
  - 预构建 269

# W

- Web 服务描述语言 (WSDL) 6
- Windows
  - Micronaut CLI 安装 17, 18
