
# Java 9 微服务精通 - 第二版

![](img/f551c3d57000fcdbbc1268267d5af69e_1_0.png)

# 致谢名单

**作者：** Sourabh Sharma

**文字编辑：** Safis Editing

**审稿员：** Guido Grazioli

**项目协调员：** Vaidehi Sawant

**策划编辑：** Aaron Lazar

**校对员：** Safis Editing

**版权编辑：** Denim Pinto

**索引员：** Aishwarya Gangawane

**内容开发编辑：** Zeeyan Pinheiro

**制作协调员：** Melwyn D'sa

**技术编辑：** Romy Dias

# 关于作者

**Sourabh Sharma** 在产品/应用开发方面拥有超过 15 年的经验。他的专长在于设计、开发、部署和测试 N 级 Web 应用以及领导团队。他热爱解决复杂问题并寻找最佳解决方案。

在整个职业生涯中，他成功地为一些世界 500 强企业交付了各种本地和云端应用/产品，令利益相关者惊叹，包括许多满意的客户。

Sourabh 相信学习是一个持续的过程，并不断更新自己的技能树——从独立应用开发到微服务开发，从 JDK 1.2 到 Java 9，从依赖 IE 5 的前端代码到跨浏览器开发，以及从本地化部署到云端部署。他有效地管理了从单一产品到系列应用的交付。

# 关于审稿员

**Guido Grazioli** 曾担任应用开发人员、软件架构师和系统集成员，涉及多个领域的各种业务应用程序。他是一位混合软件工程师，对 Java 平台、工具以及 Linux 系统有深入了解。他对 SOA（面向服务的架构）、EIP（企业集成模式）、持续集成与交付以及云端服务编排特别感兴趣。

有关与本书相关的支持文件和下载，请访问 www.PacktPub.com。您知道 Packt 为每本书籍都提供电子书版本，提供 PDF 和 ePub 文件吗？您可以在 www.PacktPub.com 升级到电子书版本，作为纸质客户，您有权获得电子版折扣。请联系 service@packtpub.com 了解更多详情。

在 www.PacktPub.com，您还可以阅读免费技术文章集，订阅系列免费通讯邮件，并接收 Packt 书籍和电子书的专属折扣和优惠。

![](img/f551c3d57000fcdbbc1268267d5af69e_1_0.png)

有关与本书相关的支持文件和下载，请访问 www.PacktPub.com。您知道 Packt 为每本书籍都提供电子书版本，提供 PDF 和 ePub 文件吗？您可以在 www.PacktPub.com 升级到电子书版本，作为纸质客户，您有权获得电子版折扣。请联系 service@packtpub.com 了解更多详情。

在 www.PacktPub.com，您还可以阅读免费技术文章集，订阅系列免费通讯邮件，并接收 Packt 书籍和电子书的专属折扣和优惠。

![](img/f551c3d57000fcdbbc1268267d5af69e_1_0.png)

有关与本书相关的支持文件和下载，请访问 www.PacktPub.com。您知道 Packt 为每本书籍都提供电子书版本，提供 PDF 和 ePub 文件吗？您可以在 www.PacktPub.com 升级到电子书版本，作为纸质客户，您有权获得电子版折扣。请联系 service@packtpub.com 了解更多详情。

在 www.PacktPub.com，您还可以阅读免费技术文章集，订阅系列免费通讯邮件，并接收 Packt 书籍和电子书的专属折扣和优惠。

## 参考文献

## 总结

# 第 10 章：故障排除指南

## 日志与 ELK 栈

- 简要概述

- Elasticsearch

- Logstash

- Kibana

## ELK 栈搭建

- 安装 Elasticsearch

- 安装 Logstash

- 安装 Kibana

- 使用 Docker Compose 运行 ELK 栈

- 将日志推送到 ELK 栈

## 服务调用中的关联 ID 使用

- 看看我们如何解决这个问题

- 使用 Zipkin 和 Sleuth 进行追踪

## 依赖与版本

- 循环依赖与版本

- 微服务与工具

## 参考文献

## 总结

# 第 11 章：将单体应用迁移到微服务架构

# 规范

在书中，你将发现许多文本样式，用于区分不同类型的信息。以下是这些样式的示例以及对其含义的解释。

文中的文字

代码块的设置如下：

```
angular.module('otrsApp.restaurants', [
  'ui.router',
  'ui.bootstrap',
  'ngStorage',
  'ngResource'
])
```

任何命令行输入或输出均如下所示所示：

```
npm install --no-optional gulp
```

**新术语**和**重要词汇**用粗体显示。你在屏幕上看到的单词（例如在菜单或对话框中）在文本中的显示方式如下：“在**工具** 对话框中，选择**创建 package.json**、**创建 bowerjson** 和**创建 gulpfile.js**。”

> 提示和重要注意事项将以这种框的形式出现。

> 提示和技巧将以这种形式出现。

# 读者反馈

我们随时欢迎读者的反馈。请告诉我们你对这本书的看法——你喜欢或不喜欢的地方。读者反馈对我们非常重要，因为它能帮助我们开发出真正让你受益的书籍。如需发送通用反馈，请直接发送电子邮件至 feedback@packpub.com，并在邮件主题中注明书名。如果你对某个专长领域感兴趣并希望编写或贡献书籍，请参阅 www.packpub.com/authors 的作者指南。

# 前言

# 客户支持

既然你已经是 Packt 书籍的自豪所有者，我们有很多方法可以帮助你充分利用你的购买。

# 下载示例代码

你可以从 http://www.packtpub.com 账户下载书中的示例代码文件。如果你是在其他地方购买的这本书，可以访问 http://www.packtpub.com/support 并注册，以便文件直接通过电子邮件发送给你。你可以按照以下步骤下载代码文件：

1. 使用你的电子邮件和密码登录或注册我们的网站。
2. 将鼠标指针悬停在顶部的 SUPPORT 标签上。
3. 点击 Code Downloads & Errata（代码下载与错误）。
4. 在搜索框中输入书名。
5. 选择你想下载代码文件的书籍。
6. 从你购买本书的下拉菜单中选择。
7. 点击 Code Download（代码下载）。

文件下载完成后，请确保使用以下最新版本的解压或提取文件夹：

- Windows：WinRAR / 7-Zip
- Mac：Zip / iZip / UnRX
- Linux：7-Zip / PeaZip

此书的代码包也托管在 GitHub 上，地址为 https://github.com/PacktPublishing/Mastering-Microservices-with-Java-9-Second-Edition。我们丰富的书籍和视频目录中还有其他代码包可用，地址为 https://github.com/PacktPublishing。快去看看吧！

感谢你帮助保护我们的作者以及我们为你提供价值内容的能力。

# 问题

如果你对本书的任何方面有疑问，可以通过 questions@packpub.com 联系我们，我们将尽力解决问题。

## 解决方案方法

作为前提条件，你应该对微服务和软件架构风格有基本的了解。基础性的理解有助于你透彻理解这些概念和本书。

阅读完本书后，你可以为本地化或云端生产部署实现微服务，并学习从设计、开发、测试到持续集成和部署的完整生命周期。本书专为实际应用而编写，旨在激发你作为架构师的思维。你的学习将帮助你为任何类型的环境（包括 SaaS、PaaS 等）开发和交付产品。我们将主要使用 Java 和基于 Java 的框架工具（如 Spring Boot 和 Jetty），并使用 Docker 作为容器。

在本章中，你将学习微服务的永恒存在以及它是如何演变的。它强调了本地和云端产品面临的大问题，以及微服务是如何处理这些问题的。

在本章中，你将学习以下主题：

- 微服务背景——单体架构
- 单体架构的局限性
- 微服务的优势

# 微服务的演进

众所周知，变化是永恒的。人类一直在寻找更好的解决方案。这就是微服务变成今天模样的原因，并且未来可能会进一步演进。今天，组织正在使用敏捷方法开发应用程序——这是一个快速迭代的环境，在云和分布式技术发明之后，其规模也大得多。许多人认为单体架构也可以实现类似的作用并与敏捷方法保持一致，但微服务在生产就绪应用的许多方面仍然提供了更好的解决方案。

Martin Fowler 解释道：

> “微服务”一词在 2011 年的一次工作会上被讨论，用于描述一种架构风格。

微服务并不复杂

> 小即是美。

前 Netflix 架构师 Adrian Cockcroft 将其描述为：

> 细粒度。

微服务与 SOA（服务面向架构）共享许多特征，尽管它们可能使用消息总线，但仅用于传输。它仅仅是基于智能端点的。

Tony 完美地定义了微服务：

> 在我的心理模型中，我将其认为自包含的（如容器所示）、通过 HTTP 通信的轻量级进程。

## 解决方案方法

# 第 1 章

尽管 Tony 只提到了 HTTP，但事件驱动微服务可能使用不同的协议进行通信。你可以利用 Kafka 来实现事件驱动微服务。

# 单体架构概述

## 第一章

# 解决方案

为了理解单体架构与微服务架构之间的设计差异，让我们以一个餐厅订座应用为例。该应用可能包含许多服务，如客户、预订、分析等，以及诸如表现层和数据库等常规组件。

我们在这里将探索三种不同的设计：传统的单体设计、带有服务的单体设计以及微服务设计。

## 传统的单体设计

下图解释了传统的单体应用设计。这种设计在 SOA（面向服务的架构）流行之前广泛广泛：

![](img/f551c3d57000fcdbbc1268267d5af69e_23_0.png)

在传统的单体设计中，所有内容都封装在同一个归文件中，例如`表现层代码`、`应用逻辑和业务逻辑代码以及 DAO` 以及与数据库文件或其他源交互的相关代码。

## 带有服务的单体设计

随着 SOA 的出现，应用程序开始基于服务进行开发，每个组件为其他组件或外部实体提供服务。下图描绘了带有不同服务的单体应用；在这里，服务与表现层组件一起使用。所有服务、表现层组件或任何其他组件都被封装在一起：

![](img/f551c3d57000fcdbbc1268267d5af69e_24_0.png)

## 服务设计

第三种设计描绘了微服务。在这里，每个组件代表了自治性。每个组件都可以独立地进行开发、构建、测试和部署。在这里，即使应用程序的用户界面（UI）组件也可以作为客户端并消费微服务。为了示例演示，所设计的层位于 u-Service 内部。

API 网关提供了接口，不同的客户端可以通过该接口访问单个服务，并解决以下问题：

当你想要对同一个服务向不同的客户端发送不同的响应时，该怎么办？例如，预订服务可以向移动客户端（极简信息）和桌面客户端（详细信息）发送提供不同不同的响应，并向第三方客户端发送完全不同的内容。

一个响应可能需要从两个或多个服务获取信息。

![](img/f551c3d57000fcdbbc1268267d5af69e_25_0.png)

在观察了所有的示例设计图（这些都是非常高层的设计）后，你可能会发现，在单体设计中，组件是封装在一起并且紧耦合的。

所有服务都是同一个包的一部分。同样，在第二个设计图中，你可以看到第一张图的变体，所有服务都可以有自己的层并形成不同的 API，但如图所示，它们也被封装在一起了。

相反，在微服务中，设计组件不是封装在一起的，而是松散耦合的。每个服务都有自己的层和数据库，并封装在单独的归档文件中。所有这些部署的服务都提供了特定的 API，例如 Customers、Bookings 或 Customer。这些 API 准备好被消费。而 UI 也是单独部署并使用 µ 设计的。由于由于原因，它与相应的单体版本相比许多优势。我仍然提醒你，在某些特殊情况下，单体应用的开发是非常成功的，例如 Etsy 以及点对点电子商务 Web 应用。

现在让我们讨论一下在处理单体应用时会面临的局限性。

## 一维扩展性

单体应用在扩展时规模庞大，由于所有组件都封装在一起，因此必须扩展一切。例如，在餐厅订座应用案例中，即使你想扩展订座服务，它也会扩展整个应用；它无法单独扩展订座服务。这没有充分利用资源。

此外，这种扩展是一维的。运行更多的应用程序副本可以提供随着事务量增加而增长的扩展。运维团队可以使用基于负载池或云的负载均衡器调整应用程序副本的数量。这些副本中的每一个都会访问相同的数据源，从而增加了内存消耗，并导致 I/O 操作使得缓存效果大折扣。

微服务提供了仅扩展需要扩展服务的灵活性，并允许对资源进行优化利用。正如我们之前提到的，当需要时，你可以扩展预订服务而不影响任何其他组件。它还允许二维扩展；在这里，我们不仅可以增加事务量，还可以通过缓存增加数据量（平台规模扩展）。

这样开发团队就可以专注于新功能的交付和发布，而不再需要担心扩展问题（产品规模扩展）。

正如我们之前看到的，微服务可以帮助你从平台、人员和产品三个维度进行扩展。这里的人员扩展指的是根据微服务的特定开发和关注需求，增加或减少团队规模。

使用 RESTful Web 服务开发进行微服务开发，使得它在这个意义上是可扩展的，因为 REST 服务器是无状态的；这意味着服务器之间的通信并不多，这使其具有水平可扩展性。

## 失败时的回滚

由于单体应用要么封装在同一个归文件中，要么包含在单个目录中，它们阻止了代码模块化的部署。例如，你们许多人可能经历过由于一个功能的失败而推迟整个版本发布的痛苦。

为了解决这些情况，微服务给了我们仅回滚那些失败功能的灵活性。这是一种非常灵活且高效的方法。例如，假设你是一个在线购物门户开发团队的成员，并想基于微服务开发应用程序。从产品、支付、购物车等不同领域开始，将所有这些组件封装为独立的包。一旦你单独部署了所有这些包，它们将作为可以独立开发、测试和部署的单个组件，并被称为 µ-Service。

现在，让我们看看这如何帮助你。假设在生产环境发布新功能、增强和错误修复后，你在支付服务中发现了需要立即修复的缺陷。由于你使用的架构基于微服务，你可以回滚支付服务而不是回滚整个版本（如果你的架构允许），或者对支付服务进行修复而不影响其他服务。这不仅让你能够正确处理故障，还有助于向客户快速交付功能/修复。

## 采用新技术的问题

单体应用大多是根据项目或产品开发初期主要使用的技术进行开发和增强的。这使得在开发后期或产品成熟状态下（例如几年后）引入新技术变得非常困难。此外，同一个项目中的不同模块依赖于同一库的不同版本，这使得问题变得更具挑战性。

技术随年不断进步。例如，你的系统可能是用 Java 设计的，几年后，由于业务需求或为了利用新技术的优势，你想用 Ruby on Rails 或 NodeJS 开发一个新的服务。在现有的单体应用中利用新技术是非常困难的。

这不仅是代码级集成的问题，还涉及到测试和部署。可以通过重写整个应用程序来采用新技术，但这是一项耗时且具有风险的工作。

相反，由于基于组件的开发和设计，微服务给了我们灵活性，在开发中使用任何技术（无论是新的还是旧的）。它不限制你使用特定的技术，而是为你的开发和工程活动提供了一种新的范式。你可以在随时使用 Ruby on Rails、NodeJS 或任何其他技术。

# 解决方案

## 第一章

那么，这是实现的呢？嗯，这非常简单。基于微服务的应用程序代码没有打包成单个归包，也没有存储在单个目录中。每个微服务都有自己的归包并被独立部署。新服务可以在隔离环境中开发，并在不产生任何技术问题的情况下进行测试和部署。如你所知，微服务还拥有自己独立的进程；它们各司其职，不会发生如共享资源或紧密耦合等冲突，且进程保持独立。

由于根据定义，微服务是一个微小的、自包含的函数，因此它为尝试新技术提供了一个低风险的机会。这在单体系统中显然并非如此。

你可以将你的微服务作为开源软件发布，供他人使用；如果需要，它还可以与闭源专有系统协同工作，这在单体应用中是不可能的。

## 与敏捷实践的对齐

毫无疑问，单体应用可以使用敏捷实践进行开发，而且这些应用正在开发中。可以使用持续集成（CI）和持续部署（CD），但问题是——它是否有效地利用了敏捷实践？让我们检查以下几点：

- 例如，当故事之间存在很很概率相互依赖，且可能出现各种场景时，在依赖故事完成之前，该故事无法被采用
- 随着代码规模的增加，构建所需的时间更长
- 频繁部署大型单体应用是一项难以实现的任务任务
- 如果你更新了单个组件，就必须重新部署整个应用程序
- 重新部署可能会给已经运行的组件带来问题，例如，作业调度器可能会因为组件是否影响它而发生变化
- 如果单个更改的组件运行不正常或需要更多修复，重新部署的风险可能会增加
- UI 开发人员总是需要更多的重新部署，这对于大型单体应用来说是非常高风险且耗费时间的

# 解决方案

## 第一章

上述问题可以通过微服务轻松地解决，例如，UI 开发人员可以有自己的 UI 组件，这些组件可以独立地进行开发、构建、测试和部署。同样，其他微服务也可以独立部署，并且由于它们的自主特性，系统故障的风险降低了。开发层面的另一个优势是，UI 开发人员可以使用 JSON 对象和模拟 Ajax 调用来开发 UI，这可以以隔离的方式进行。开发完成后，开发者可以消费实际 API 并测试功能。总而言之，你可以说微服务开发是快速的，并符合业务的增量需求。

## 开发便利性 – 还可以做得更好

通常，大型单体应用代码对开发者来说是最难理解的，新开发者变得有生产力需要时间。即使是把大型单体应用加载到 IDE 中都是麻烦的，它会让 IDE 变慢并降低开发者的效率。



由于代码库庞大，大型单体应用中的更改难以实现且耗费时间，如果没有进行正确且彻底的影响分析，就会产生很高的 Bug 风险。因此，在实施更改之前进行彻底的影响分析成为了开发者的先决条件。

在单体应用中，由于所有组件打包在一起，依赖关系随着时间的推移而积累。随着代码更改（修改行数）的增加，代码更改相关的风险呈指数级增长。

当代码库巨大且有超过 100 名开发者在上面工作时，由于上述原因，构建产品和实现新功能变得非常困难。你需要确保万事就绪，并且一切协调一致。在这种情况下，设计良好且文档的 API 有很大帮助。

Netflix，一家按需互联网流媒体提供商，在开发应用程序方面遇到过问题，当时有大约 100 人在上面工作。然后，他们使用了云并将应用程序拆分成不同的部分。这些部分最终变成了微服务。微服务的出现是因为对速度、敏捷性以及独立部署团队的愿望。

# 解决方案

## 第一章

得益于暴露的 API，微组件之间是松耦合的，这些 API 可以进行持续集成测试。凭借微服务的持续发布周期，更改是微小的，开发者可以通过回归测试快速地利用它们，然后进行检查并修复最终发现的缺陷，从而降低部署风险。这导致了更高的速度和更低的关联风险。

由于功能的分离和单一职责原则，微服务使得团队非常有生产力。你可以在网上找到许多示例，大型项目是以仅有八到十名开发者的最小团队规模完成的。

开发者可以专注于更小的代码量，并获得更好的功能实现，从而与产品用户产生更高层次的共情关系。这激发了功能实现中更好的动力和清晰度。与用户的共情关系允许了更短的反馈循环，并能对功能流水线进行更好、更快速的优先级排序。更短的反馈循环也让缺陷检测更快。

每个微服务独立工作，新功能或想法的实现无需与更大范围的受众进行协调。微服务设计中的端点失败处理也容易实现。

最近，在一次会议上，一个团队展示了他们如何在 10 周内开发了一个基于微服务的货运跟踪应用程序（包括 iOS 和 Android 应用），该应用具有 Uber 类型的跟踪功能。一家大型咨询公司对同一个应用程序向客户给出了七个月的估算。这说明了微服务是如何适应敏捷方法和 CI/CD 的。

## 微服务构建流水线

微服务还可以使用 `Jenkins`、`TeamCity` 等流行的 CI/CD 工具进行构建和测试。这与单体应用的构建方式非常相似。在微服务中，每个微服务被视为一个小型应用程序。

例如，一旦你在仓库（`SCM`）中提交代码，CI/CD 工具就会触发构建：

- 清理代码
- 代码编译
- 单元测试执行
- 合同验收测试执行
- 构建归包/镜像

# 解决方案

## 第一章

- 将归包/镜像发布到仓库管理
- 部署到 `Dev`、`QA`、`Stage` 等交付环境
- 集成和功能测试
- 其他步骤

然后，更改 `pom.xml` 中的 `SNAPSHOT` 或 `RELEASE` 版本（如果是 `Maven` 的话）的重新构建触发器按照常规触发器构建制品。将制品发布到制品仓库。在仓库中标记该版本。如果你使用容器镜像，则作为构建的一部分构建容器镜像。

## 使用 Docker 等容器进行部署

由于微服务的设计，你需要一个为持续集成和部署以及运输提供灵活性、敏捷性和流畅的环境。微服务的部署需要速度、隔离管理和敏捷生命周期。

以前，虚拟机被用于创建软件镜像以便在需要的地方部署。后来，像 `Docker` 容器变得更加流行，因为它们兼容传统的虚拟站系统和云环境。例如，在开发者的笔记本电脑上部署多个虚拟机是不现实的。构建和启动虚拟机通常是 I/O 密集型的，因此非常缓慢。

## 容器

容器（例如 `Linux` 容器）提供了一个轻量级的运行时环境，它由虚拟机的核心功能和操作系统的隔离服务组成。这使得微服务的打包和执行变得简单且顺畅。

如下图所示，容器在`操作系统`内部作为应用程序（微服务）运行。操作系统运行在硬件之上，每个操作系统可以拥有多个容器，每个容器运行一个应用程序。

容器利用了操作系统的内核接口，如 `cgroups` 和 `命名空间 (namespaces)`，这允许多个容器在相互完全隔离的同时共享相同的内核。这带来的优势是无需为每次使用都完成一次操作系统的安装；结果就是消除了开销。它还优化地利用了`硬件`：

![](img/f551c3d57000fcdbbc1268267d5af69e_32_0.png)

## 解决方案方法

## 第 1 章

### Docker

容器技术是当今增长最快的技术之一，而 `Docker` 领先这一领域。`Docker` 是一个开源项目，于 2013 年发布。在 2013 年 8 月交互式教程发布后，有 10,000 名开发者尝试了它；到 2013 年 6 月发布 1.0 版本时，尝试次数已达275 万次。许多大型公司已与 `Docker` 签署了合作伙伴协议，例如微软、红帽、`HP`、`OpenStack` 以及 `Amazon Web Services`、`IBM` 和 `Google` 等服务提供商。

如前所述，`Docker` 也利用了 `Linux` 内核功能（如 `cgroups` 和 `命名空间`）来确保资源隔离以及应用程序及其依赖的打包。这种对依赖的打包使得应用程序能够在不同的 `Linux` 操作系统/发行版上按预期运行，支持了一定的可移植性。此外，这种移植性允许开发者使用任何语言开发应用程序，然后轻松地从笔记本电脑部署到测试或生产环境服务器。

`Docker` 原生运行在 `Linux` 上。然而，你也可以使用 `VirtualBox` 和 `boot2docker` 在 `Windows` 和 `MacOS` 上运行 `Docker`。

![](img/f551c3d57000fcdbbc1268267d5af69e_33_0.png)

容器仅由应用程序及其依赖项（包括基础操作系统）组成。这使其在资源利用方面既轻量又高效。开发者和系统管理员对容器的可移植性和高效的资源利用感兴趣。

容器中的所有内容均在主机上原生执行，并直接使用主机内核。每个容器都有自己的所有者命名空间。

## Docker 架构

如 `Docker` 文档所述，`Docker` 架构采用客户端-服务器架构。如下所示（来自 `Docker` 官网：https://docs.docker.com/engine/docker-overview/），`Docker` 客户端主要是终端用户使用的界面；客户端与 `Docker` 守护进程进行通信。`Docker` 守护进程负责构建、运行和分发你的 `Docker` 容器的重量工作。`Docker` 客户端和守护进程可以运行在同一系统上，也可以在不同的机器上。

`Docker` 客户端和守护进程通过 `RESTful API` 使用 `sockets` 进行通信。`Docker Registry` 是公共或私有的 `Docker` 镜像仓库，你可以从那里上传或下载镜像，例如 `Docker Hub` (hub.docker.com) 就是一个公共的 `Docker` 注册表。

![](img/f551c3d57000fcdbbc1268267d5af69e_34_0.png)

`Docker` 的主要组件是：

- **Docker 镜像**：`Docker` 镜是一个只读模板。例如，一个镜像可以包含安装了 `Ubuntu` 操作系统、`Apache Web` 服务器和你的 `Web` 应用程序。`Docker` 镜是 `Docker` 的构建组件，镜像用于创建 `Docker` 容器。`Docker` 提供了一种构建新镜像或更新现有镜像的简单方法。你也可以使用他人创建的镜像和或对其进行扩展。

- **Docker 容器**：`Docker` 容器是由 `Docker` 镜像创建的。`Docker` 的工作使得容器只能看到自己的进程，并有一个层叠在主机文件系统上的自己的文件系统以及网络栈，该网络栈连接到主机的网络栈。`Docker` 容器可以被运行、启动、停止、移动或删除。

## 部署

使用 `Docker` 进行微服务部署涉及三个部分：

- 应用程序打包，例如 `JAR`
- 使用 `Docker` 指令文件（`Dockerfile`）和命令 `docker build` 构建带有 `JAR` 及其依赖项的 `Docker` 镜像。这有助于重复创建镜像
- 使用 `docker run` 从这个新构建的镜像中进行 `Docker` 容器的执行

上述信息将帮助你理解 `Docker` 的基础知识。你将在第 5 章“部署与测试”中学习更多关于 `Docker` 及其实际用法。来源和参考请参阅：https://docs.docker.com。

## 总结

在本章中，你已经学习或回顾了大型软件项目的高层设计，从传统的单体应用到微服务应用。你还了解了微服务的简要历史、单体应用的局限性，以及微服务提供的优势和灵活性。我希望这一章帮助你理解单体应用在生产环境中面临的常见问题，以及微服务如何解决此类问题。你还接触了轻量高效的 `Docker` 容器，并展示了容器化是简化微服务部署的极佳方式。

在下一章中，你将了解从 `IDE`、其他开发工具到不同库的开发环境搭建。我们将处理基础项目并设置 `Spring Boot` 配置来构建并开发我们的第一个微服务。我们将使用 `Java 9` 作为语言并使用 `Spring Boot` 作为项目框架。

## #2 设置开发环境

本章侧重于开发环境的搭建和配置。如果你熟悉这些工具和库，可以跳过本章并继续学习第 3 章“领域驱动设计”，在那里你可以探索领域驱动设计 (`DDD`)。

本章将涵盖以下主题：

- `NetBeans IDE` 的安装与设置
- `Spring Boot` 配置
- 使用 `Java 9` 模块的示例 `REST` 程序
- 构建设置
- 使用 `Chrome` 的 `Postman` 扩展进行 `REST API` 测试

本书的示例和代码将仅使用开源工具和框架。本书也将使用 `Java 9` 作为编程语言，应用程序框架将基于 `Spring Framework`。本书利用 `Spring Boot` 开发微服务。

`NetBeans` 集成开发环境 (`IDE`) 为 `Java` 和 `JavaScript` 提供了顶尖的支持，并且满足我们的需求。多年来，它发生了巨大变化，并对本书所用的大多数技术提供了内置支持，例如 `Maven`、`Spring Boot` 等。因此，我建议你使用 `NetBeans IDE`。不过，你可以自由使用任何 `IDE`。

## 设置开发环境

我们将使用 `Spring Boot` 来开发服务和微服务。在书中选择最流行的框架 `Spring Boot` 及其子集 `Spring Cloud` 是一个深思熟虑的决定。正如此，我们不需要从零编写应用程序。`Spring Boot` 概述将在 `Spring Boot` 章节提供。如果你是 `Spring Boot` 新，这对你有帮助。

我们将使用 `Maven` 作为构建工具。在 `IDE` 中，你可以使用任何需要的构建工具，例如 `Gradle` 或 `Ant` 带 `Ivy`。我们将使用嵌入 `Jetty` 作为 `Web` 服务器，另一种方案是嵌入 `Tomcat`。我们还将使用 `Chrome` 的 `Postman` 扩展来测试我们的 `REST` 服务。

从 `Spring` 配置开始。如果你是 `NetBeans` 新手或在设置环境遇到问题，可以参考以下。

### NetBeans IDE 安装与设置

`NetBeans IDE` 是免费开源的，拥有庞大的用户群。你可以从官方网站 https://netbeans.org 下载 `NetBeans IDE`。

在编写本书时，`Java 9` 的 `NetBeans` 仅以预览版本可用（从 http://bits.netbeans.org/download/trunk/nightly/latest/ 下载）。如下所示，下载我们需要的支持 `NetBeans` 包：

| 技术 | Java SE | Java EE | HTML5/JavaScript | PHP | C/C++ | AB |
| --- | --- | --- | --- | --- | --- | --- |
| NetBeans Platform SDK | | | | | | |
| Java SE | | | | | | |
| Java FX | | | | | | |
| Java EE | | | | | | |
| Java ME | | | | | | |
| HTML5/JavaScript | | | | | | |
| PHP | | | | | | |
| C/C++ | | | | | | |
| Oracle | | | | | | |
| Java Card™ 3 Connected | | | | | | | |
| Bundled servers | | | | | | | |
| Glassfish Server Source Edition 4.1.1 | | | | | | | |
| Apache Tomcat 8.0.27 | | | | | | | |
| | 下载 | 下载 | 下载 >B6 | 下载 >B6 | 下载 >B6 | 下载 |
| | Free, 95 MB | Free, 197 MB | Free, 108 - 112 MB | Free, 108 - 112 MB | Free, 107 - 110 MB | Free, 221 MB |

## 设置开发环境

`GlassFish Server` 和 `Apache Tomcat` 是可选的。所需的程序包和运行时标记为“已安装”（因为我的系统中已经安装了 `NetBeans`）：

![](img/f551c3d57000fcdbbc1268267d5af69e_38_0.png)

下载安装包后，执行安装程序文件。如如下所示所示接受许可协议，并按照其余步骤安装 `NetBeans IDE`。

![](img/f551c3d57000fcdbbc1268267d5af69e_39_0.png)

`NetBeans` 许可证对话框

安装和运行所有 `NetBeans` 捆包需要 `JDK 8` 或更高版本。本书使用 `Java 9`，因此我们将使用 `JDK 9`。你可以从 http://www.oracle.com/technnetwork/java/javase/downloads/index.html 下载独立的 `JDK 9`。由于在撰写本书时 `JDK 9` 尚未发布，我不得不使用 `JDK 9` 的早期访问构建版本。它可以在 http://jdk.java.net/9/ 获取。

## 第 2 章

一旦安装了 `NetBeans IDE`，启动 `NetBeans IDE`。`NetBeans IDE` 的启动情况如下：

![](img/f551c3d57000fcdbbc1268267d5af69e_40_0.png)

`Maven` 和 `Gradle` 都是 `Java` 构建工具。它们为你的项目添加依赖库、编译代码、设置属性、构建归包并进行许多相关活动。`Spring Boot` 或 `Spring Cloud` 都支持 `Maven` 和 `Gradle` 构建工具。然而，在本书中，我们将使用 `Maven` 构建工具。如果你愿意，也可以自由使用 `Gradle`。

`Maven` 在 `NetBeans IDE` 中已可用。现在，我们可以启动一个新的 `Maven` 项目来构建我们的第一个 `REST` 应用程序。

以下是创建空 `Maven` 项目的步骤：

1. 点击**文件 (File)** 菜单下的**新建项目 (New Project (Ctrl + Shift + N))**。这将打开**新建项目**向导。
2. 从**类别 (Categories)** 列表中选择 **Maven**。然后，如下所示所示，从**项目 (Projects)** 列表中选择 **POM Project**。然后，点击**下一步 (Next)** 按钮。

![](img/f551c3d57000fcdbbc1268267d5af69e_41_0.png)

3. 现在，将项目名称输入为 `6392_chapter2`。同样如下所示所示输入其他属性。填写所有必填字段后点击**完成 (Finish)**：

![](img/f551c3d57000fcdbbc1268267d5af69e_42_0.png)

`Aggelos Kalias` 为 `NetBeans IDE` 开发了一个非常有用的插件，可为 `Spring Boot` 配置提供自动补全支持，地址为 https://github.com/keevosh/nb-spring-configuration-support。你可以从其项目页面 http://keevosh.github.io/nb-spring-configuration-support/ 下载它。你也可以使用 `Pivotal` 的 `Spring Tool IDE` (https://spring.io/tools) 代替 `NetBeans IDE`。它是一个基于 `Eclipse` 的定制一体化发行版，使开发变得简单。

完成所有步骤后，`NetBeans` 将显示新创建的 `Maven` 项目。你将使用此项目通过 `Spring Boot` 创建示例应用程序。

4. 为了使用 `Java 9` 作为源，将 `Source/Binary Format` 设置为 `9`，如下所示：

![](img/f551c3d57000fcdbbc1268267d5af69e_43_0.png)

5. 转到“构建 (Build) | 编译 (Compile)”并确保 `Java Platform` 设置为 `JDK 9 (Default)`，如下：

![](img/f551c3d57000fcdbbc1268267d5af69e_44_0.png)

6. 同样，你可以通过打开右键菜单并选择**新建模块 (New Module)** 添加两个名为 `lib` 和 `rest` 的新模块。这次你应该在 **Categories** 列表中选择 `Maven`，并在 **Projects** 列表中选择 `Java Application`。

# Spring Boot 概述

`Spring Boot` 是由 `Pivotal` 创建出强大的工具，并于 2014 年 4 月发布（`GA`）。它是基于“无容器”`Web` 架构的需求开发的。你可能在想，为什么是无容器？因为今天的云环境或 `PaaS` 提供了基于容器的架构的大部分功能，例如可靠性、管理或扩展性。因此，`Spring Boot` 专注于让自己变得极轻量。



# Spring Boot 预先配置以便轻松创建生产就绪的 Web 应用

Spring Initializr 是一个页面，你可以在其中选择 Maven 或 Gradle 等构建工具，以及作为 group、artifact 和依赖的项目元数据。一旦输入了所需字段，只需点击**生成项目 (Generate Project)** 按钮，这将为你提供可以用于生产应用程序的 Spring Boot 项目。在该页面上，默认的打包选项是 Jar。我们将使用 JAR 使微服务开发更简单。原因很简单：想想如果每个微服务都运行在自己的实例上，管理和创建基础设施有多困难。Josh Long 在他的演讲中分享道：

> “制作 Jar 比制作 War 好。”

稍后我们将使用 Spring Cloud，它是 Spring Boot 之上的一个封装。我们将开发一个使用 Java 9 模块功能的示例 REST 应用程序。我们将创建两个模块——lib 和 rest。lib 模块将为 rest 模块提供任何支持的类。rest 模块将包含开发 REST 应用程序所需的所有类，并将 lib 模块定义的模型。lib 和 rest 模块都是 maven 模块，它们的父模块是我们的主项目 `6392-chapter2`。`module-info.java` 文件是一个控制其类访问权限的重要类。我们将使用 `requires`、`opens` 和 `exports` 来使用 spring 模块，并在我们 REST 应用程序的 lib 和 rest 模块之间建立生产者-消费者关系。

## 将 Spring Boot 添加到我们的主项目

我们将使用 Java 9 开发微服务。因此，我们将使用最新的 Spring Framework 和 Spring Boot 项目。在撰写本书时，Spring Boot 2.0.0 构建发布版本已可用。你可以使用最新发布的版本。Spring Boot 2.0.0 build snapshots Spring 5 (5.0.0 build snapshot release)。

让我们来看以下步骤并学习如何将 Spring Boot 添加到我们的主项目中：

- 打开 `pom.xml` 文件（在 `6392_chapter2 | Files` 下可用）向你的示例项目添加 Spring Boot：

```xml
<mainClass>${start-class}</mainClass>
</configuration>
</execution>
</executions>
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
  <version>3.6.1</version>
  <configuration>
    <source>1.9</source>
    <target>1.9</target>
    <showDeprecation>true</showDeprecation>
    <showWarnings>true</showWarnings>
  </configuration>
</plugin>
</plugins>
</build>
<repositories>
  <repository>
    <id>spring-snapshots</id>
    <name>Spring Snapshots</name>
    <url>https://repo.spring.io/snapshot</url>
    <snapshots>
      <enabled>true</enabled>
    </snapshots>
  </repository>
  <repository>
    <id>spring-milestones</id>
    <name>Spring Milestones</name>
    <url>https://repo.spring.io/milestone</url>
    <snapshots>
      <enabled>false</enabled>
    </snapshots>
  </repository>
</repositories>
<pluginRepositories>
  <pluginRepository>
    <id>spring-snapshots</id>
    <name>Spring Snapshots</name>
    <url>https://repo.spring.io/snapshot</url>
    <snapshots>
      <enabled>true</enabled>
    </snapshots>
  </pluginRepository>
  <pluginRepository>
    <id>spring-milestones</id>
    <name>Spring Milestones</name>
    <url>https://repo.spring.io/milestone</url>
    <snapshots>
      <enabled>false</enabled>
    </snapshots>
  </pluginRepository>
</pluginRepositories>
</project>
```

你可以观察到我们在父项目 `pom.xml` 中定义了两个模块 `lib` 和 `rest`。

- 2. 如果你是第一次添加这些依赖，你需要在 Projects 窗格中 `6392_chapter2` 项目下的 `Dependencies` 文件夹上点击右键来下载依赖，如下截图所示：

![](img/f551c3d57000fcdbbc1268267d5af69e_49_0.png)

- 3. 同样，为了解决项目问题，右键点击 NetBeans 项目 `6392_chapter2` 并选择 `Resolve Project Problems....`（解决项目问题）。它将打开所示所示对话框。点击 `Resolve...` 按钮来解决问题：

![](img/f551c3d57000fcdbbc1268267d5af69e_50_0.png)

- 4. 如果你在代理后使用 Maven，请更新 Maven 目录中 `settings.xml` 中的代理设置。如果你使用的是 NetBeans 自带的 Maven，请使用 `<NetBeans 安装目录>\java\maven\conf\settings.xml`。你可能需要重启 NetBeans IDE。

如果本地 Maven 仓库中没有声明的依赖和传递性依赖，上述步骤将从远程 Maven 仓库下载所有所需的依赖。如果你是第一次下载依赖，取决于你的网络速度，可能需要一些时间。

## 示例 REST 程序

我们将使用一种简单的方法来构建独立应用程序。它将所有内容打包成单个可执行的 JAR 文件，并由 `main()` 方法驱动。在此过程中，你利用 Spring 将 Jetty Servlet 容器作为 HTTP 运行时嵌入，而不是将其部署到外部实例。因此，我们将创建一个可执行的 JAR 文件来代替需要部署在外部 Web 服务器上的 war 文件，这是 `rest` 模块的一部分。我们将在 `lib` 模块中定义模型并在 `rest` 模块中定义 API 类。

以下是 `lib` 和 `rest` 模块的 `pom.xml`。

### `lib` 模块的 `pom.xml` 文件

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
     http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <parent>
    <groupId>com.packptub</groupId>
    <artifactId>6392-chapter2</artifactId>
    <version>1.0-SNAPSHOT</version>
  </parent>
  <artifactId>lib</artifactId>
</project>
```

### `rest` 模块的 `pom.xml`

```xml
<modelVersion>4.0.0</modelVersion>
  <parent>
    <groupId>com.packptub</groupId>
    <artifactId>6392-chapter2</artifactId>
    <version>1.0-SNAPSHOT</version>
  </parent>
  <artifactId>rest</artifactId>
  <dependencies>
    <dependency>
      <groupId>com.packptub.mmj</groupId>
      <artifactId>lib</artifactId>
    </dependency>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
  </dependencies>
</project>
```

这里，`spring-boot-starter-web` 依赖用于开发独立的可执行 REST 服务。

我们将分别在 `lib` 和 `rest` 模块的默认包中添加以下 `module-info.java` 类。

### `lib` 模块中的 `module-info.java` 文件

```java
module com.packtub.mmj.lib {
    exports com.packtub.mmj.model to com.packtub.mmj.rest;
    opens com.packtub.mmj.lib.model;
}
```

在这里，我们将 `com.packtub.mmj.lib.model` 包导出到 `com.packtub.mmj.rest`，这允许 rest 类访问 lib 模型类。

### `rest` 模块中的 `module-info.java` 文件

```java
module com.packtub.mmj.rest {
    requires com.packtub.mmj.lib;
    exports com.packtub.mmj.rest;
    opens com.packtub.mmj.rest to com.packtub.mmj.lib;
}
```

我们将为 Calculation 资源实现两个 URI——平方根（`Math.sqrt()` 函数）作为 `/calculations/sqrt` URI，以及幂（`Math.pow()` 函数）作为 `/calculation/power` URI。

## @RequestMapping 注解

`@RequestMapping` 注解用于类级别，用于将 `/calculation` URI 映射到 `CalculationController` 类，也就是说，它确保对 `/calculation` 的 HTTP 请求映射到 `CalculationController` 类。根据使用 `@RequestMapping` 定义的 URI 路径（`/calculation` 的后缀，例如 `/calculation/sqrt/144`），它将映射到相应的方法。在这里，请求映射 `/calculation/sqrt` 映射到 `sqrt()` 方法，而 `/calculation/power` 映射到 `pow()` 方法。

你可能还会注意到，我们没有定义这些方法使用的默认方法（GET/PUT 等）。`@RequestMapping` 注解默认映射所有的 HTTP 请求。你可以通过使用 RequestMapping 的 `method` 属性来使用特定的方法。例如，你可以在如下代码中使用 `@RequestMethod` 注解来使用 POST 方法：

```java
@RequestMapping(value = "/pow", method = POST)
```

为了在过程中传递参数，示例分别使用 `@RequestParam` 和 `@PathVariable` 注解演示了请求参数和路径参数。

## @RequestParam 注解

`@RequestParam` 负责将查询参数绑定到控制器方法的参数上。例如，查询参数 base（基数）和 exponent（指数）绑定到 `CalculationController` 中 `pow()` 方法的参数 `b` 和 `e`。`pow()` 方法的两个查询参数都是的，因为我们没有为它们设置任何默认值。查询参数的默认值可以使用 `@RequestParam` 的 `defaultValue` 属性设置，例如 `@RequestParam(value="base", defaultValue="2")`。在这里，如果用户没有传递查询参数 base，则将使用默认值 2 作为 base。



如果没有定义 `defaultValue` 且用户未提供请求参数，`RestController` 将返回 HTTP 状态码 400，带有消息 "Required String parameter 'base' is not present"。如果缺少多个请求参数，它将始终使用第一个必需参数的引用：

```json
{
  "timestamp": 1464678493402,
  "status": 400,
  "error": "Bad Request",
  "exception": "org.springframework.web.bind.MissingServletRequestParamException",
  "message": "Required String parameter 'base'",
  "path": "/calculation/power/"
}
```

## @PathVariable 变量注解

`@PathVariable` 帮助你创建动态 URL。`@PathVariable` 注解允许将 Java 参数映射到路径参数。它与 `@RequestMapping` 配合使用，在 URI 中创建占位符，然后将占位符名称用作 `PathVariable` 或方法参数，正如你在 `CalculationController` 类的 `sqrt()` 方法中所示。在这里，值占位符在 `@RequestMapping` 内部创建，并被赋值给 `@PathVariable` 的值。

`sqrt()` 方法接收 URI 中的参数代替请求参数，例如 `http://localhost:8080/calculation/sqrt/144`。在这里，值 144 作为路径参数传递，该 URL 返回 144 的平方根，即 12。

若要在 value 中使用基本检查，使用正则表达式 `^-+\\d+\\.?\\d*$` 以仅允许参数中出现有效数字。如果传递了非数值，相应的方法会在 JSON 的输出键中添加一条错误消息：

`CalculationController` 还在路径变量（路径参数）中使用正则表达式 `. +` 以允许数值中的小数点（.）：`/path/{variable:.}`。Spring 会忽略最后一个小数点之后的任何内容。Spring 默认将其视为文件扩展名。

还有其他替代方案，例如在末尾添加斜杠（`/path/{variable}/`），或重写 `WebMvcConfigurerAdapter` 的 `configurePathMatch(PathMatch)` 方法将 `useRegisteredSuffixPathMatcher` 设置为 `true`，使用 `PathMatchConfigurer`（在 Spring 4.0.1 中可用）。

![](img/f551c3d57000fcdbbc1268267d5af69e_56_0.png)

## CalculationController 资源代码，我们在其中实现了 REST 端点

```java
package com.packtub.mmj.rest.resources;

import com.packtub.mmj.lib.model.Calculation;
import java.util.ArrayList;
import java.util.List;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import static org.springframework.web.bind.annotation.RequestMethod.GET;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

/**
 * @author soushamham
 */
@RestController
@RequestMapping("/calculation")
public class CalculationController {

    private static final String PATTERN = "^-?\\d+\\.?\\d*$";

    /**
     * @param b
     * @param e
     * @return
     */
    @RequestMapping("/power")
    public Calculation pow(@RequestParam(value = "base") String b, @RequestParam(value = "exponent") String e) {
        List<String> input = new ArrayList();
        input.add(b);
        input.add(e);
        List<String> output = new ArrayList();
        String powValue;
        if (b != null && e != null && b.matches(PATTERN) &&
        e.matches(PATTERN)) {
            powValue = String.valueOf(Math.pow(Double.valueOf(b), Double.valueOf(e)));
        } else {
            powValue = "Base or Exponent is not numeric.";
        }
        output.add(powValue);
        return new Calculation(input, output);
    }

    /**
     * @param aValue
     * @return
     */
    @RequestMapping(value = "/sqrt/{value}", method = GET)
    public Calculation sqrt(@PathVariable(value = "value") String aValue) {
        List<String> input = new ArrayList<>();
        input.add(aValue);
        List<String> output = new ArrayList<>();
        String sqrtValue;
        if (aValue != null && aValue.matches(PATTERN)) {
            sqrtValue = String.valueOf(Math.sqrt(Double.valueOf(aValue)));
        } else {
            sqrtValue = "Input value is not numeric.";
        }
        output.add(sqrtValue);
        return new Calculation(input, output);
    }
}
```

在这里，我们使用 URI `/calculation/power` 和 `/calculation/sqrt` 暴露 power 和 sqrt 函数。

> 这里我们将 sqrt 和 power 作为 URI 的一部分，这是为了演示的目的。理想情况下，这些应该作为请求参数的值传递。

## 创建可执行的示例 REST 应用

创建一个带有 `SpringApplication` 注解的 `RestSampleApp` 类。主方法使用 Spring 的 `SpringApplication.run()` 方法启动应用程序。

我们在 `RestSampleApp` 类上使用 `@SpringBootApplication` 注解，它隐式添加了以下标记：

- `@Configuration` 注解将类标记为应用上下文 Bean 定义源。
- `@EnableAutoConfiguration` 注解表示 Spring Boot 通过类路径设置、Bean 以及各种属性设置启动 Bean。
- 如果 Spring Boot 在类路径中找到 spring-mvc，则添加 `@EnableWebMvc` 注解。它将应用程序视为 Web 应用并激活设置 `DispatcherServlet` 等行为。
- `@ComponentScan` 注解指示在给定包中查找其他组件、配置和服务：

```java
package com.packpub.mmj.rest;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class RestSampleApp {
    public static void main(String[] args) {
        SpringApplication.run(RestSampleApp.class, args);
    }
}
```

此 Web 应用是 100% 纯 Java，你不需要使用 XML 配置任何水水或基础设施；相反，它使用了被 Spring Boot 进一步简化的 Java 注解。因此，除了 Maven 的 `pom.xml` 之外，没有一行 XML。甚至没有 `web.xml` 文件。

## 设置开发环境

# 第 2 章

## 添加嵌入式 Jetty 服务器

Spring Boot 默认提供 Apache Tomcat 作为嵌入式应用容器。本书将使用 Jetty 嵌入式容器代替 Apache Tomcat。因此，我们需要添加 Jetty 应用容器依赖项以支持 Jetty Web 服务器。

Jetty 还允许你使用类路径（classpaths）读取密钥或信任存储，也就是说你不需要将这些存储文件保留在 JAR 文件之外。如果你在 Tomcat 中使用 SSL，你将需要直接从文件系统访问密钥存储或信任存储，但你无法通过类路径做到。结果是，你无法在 JAR 文件内读取密钥存储或信任存储，因为 Tomcat 要求密钥存储（如果你在使用信任存储则也包括）在文件系统中是可访问的。这在本书编写之后可能会发生变化。

此限制不适用于 Jetty，它允许在 JAR 文件内读取密钥或信任存储。rest 模块中 `pom.xml` 的部分如下：

```xml
<dependencies>
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
    <exclusions>
      <exclusion>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-tomcat</artifactId>
      </exclusion>
    </exclusions>
  </dependency>
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-jetty</artifactId>
  </dependency>
</dependencies>
```

## 设置应用构建

无论 `pom.xml` 文件如何，我们到为止所使用的内容已足够执行我们的示例 REST 服务。该服务会将代码打包成 JAR 文件。为了让此 JAR 文件可执行，我们需要选择以下选项：

- 运行 Maven 工具
- 使用 Java 命令执行

接下来的章节将详细介绍这些内容。

## 运行 Maven 工具

此方法可能无效，因为 Java 9、Spring Boot 2 和 Spring Framework 5 均处于早期发布或快照发布阶段。如果不起作用，请使用使用 Java 命令的项目。

在这里，我们使用 Maven 工具来执行生成的 JAR 文件，步骤如下：

1. 右键点击 `pom.xml` 文件。
2. 从弹出菜单中选择 Run Maven | Goals...。这将打开一个对话框，在 Goals 字段中输入 `spring-boot:run`。我们在代码中使用已发布版本的 Spring Boot。但是，如果你使用的是快照版本，可以勾选 Update Snapshots 复选框。以后要使用，可以在 Remember as 字段中输入 `spring-boot-run`。
3. 下次，你可以直接点击 Run Maven | Goals | spring-boot-run 来执行项目。

![](img/f551c3d57000fcdbbc1268267d5af69e_62_0.png)

4. 点击 OK 执行项目。

## 使用 Java 命令执行

在执行以下命令之前，请确保 Java 和 `JAVA_HOME` 已设置为 Java 9。请查看以下步骤：

1. 要构建 JAR 文件，请从父根目录 (6392_chapter2) 的命令行中执行 `mvn clean package` 命令。在这里，clean 和 package 是 Maven 目标：

```bash
mvn clean package
```

2. 它会在相应的 target 目录下创建 JAR 文件。我们将执行在 `6392_chapter2\rest\target` 目录下生成的 JAR 文件。可以使用以下命令执行 JAR 文件：

```bash
java -jar rest\target\rest-1.0-SNAPSHOT-exec.jar
```

请确保执行的是前述命令所示带有 `exec` 后缀的 JAR 文件。

## 使用 Postman Chrome 扩展测试 REST API

本书使用 Chrome 扩展 Postman - REST Client 来测试我们的 REST 服务。我使用的是 5.0.1 版本的 Postman。你可以使用 Postman Chrome 应用或任何其他 REST Client 来测试你的示例 REST 应用，如下截图所示：

![](img/f551c3d57000fcdbbc1268267d5af69e_63_0.png)

一旦安装了 Postman - REST Client，让我们来测试第一个 REST 资源。我们从开始菜单或快捷方式启动 Postman - REST Client。

默认情况下，嵌入式 Web 服务器启动在端口 8080 上。因此，我们需要使用 `http://localhost:8080/<resource>` URL 来访问示例 REST 端点。例如：`http://localhost:8080/calculation/sqrt/144`。

一旦启动，你可以使用 Calculation REST URL，并将 sqrt 和值 144 作为路径参数。你可以在下图中看到它。该 URL 输入在 Postman 扩展的 URL (enter request URL here) 输入框中。默认情况下，请求方法为 GET。我们使用请求方法的默认值，因为我们也编写了 RESTful 服务来处理请求 GET 方法。

一旦你按照前面提到的准备好输入数据，就可以点击 Send 按钮提交请求。你可以在下图中看到示例 REST 端点返回了响应码 200。你可以在下图中找到 Status 标签以查看 200 OK 状态。成功的请求还会返回 Calculation 资源的 JSON 数据，显示在 Pretty 标签页中。返回的 JSON 显示了函数的 `sqrt` 值。它还显示了 144 和 12.0 作为输入和输出：

![](img/f551c3d57000fcdbbc1268267d5af69e_64_0.png)

同样，我们还会在 Postman 扩展中输入数据，测试用于计算幂函数的示例 REST 服务：

- URL：`http://localhost:8080/calculation/power?base=2`
- 请求方法：GET

在这里，我们传递了请求 base 和 exponent，值分别为 2 和 4。它返回了如下 JSON：

```json
{
  "function": "power",
  "input": [
    "2",
    "4"
  ],
  "output": [
    "16.0"
  ]
}
```

它返回上述带有 200 响应的 JSON，如下图所示：

![](img/f551c3d57000fcdbbc1268267d5af69e_65_0.png)

# 开发环境搭建

你将学习如何实际使用基于领域驱动设计（DDD）的示例服务。你还将学习如何在其基础上设计领域模型和 REST 服务。以下是几个链接，你可以查看这些链接以了解更多关于我们在此使用的工具的信息：

- **Spring Boot**: http://projects.spring.io/spring-boot/
- **下载 NetBeans**: https://netbeans.org/downloads
- **表述状态转移 (REST)**: Roy Thomas Fielding 博士论文《架构风格与网络化软件的设计》的第 5 章（https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm）
- **REST**: https://en.wikipedia.org/wiki/Representational_state_transfer



- **Maven**: https://maven.apache.org/
- **Gradle**: http://gradle.org/

# 3 领域驱动设计

本章通过引用一个示例项目，为后续章节奠定基调。从这里开始，该示例项目将用于解释不同的微服务概念。本章将利用该示例项目，通过功能性服务与领域服务（或应用程序）的不同组合来解释领域驱动设计（DDD）。它将帮助你学习 DDD 的基础及其实际用法。你还将学习使用 REST 服务设计领域模型的概念。

本章涵盖了以下主题：

- DDD 基础
- 如何使用 DDD 设计应用程序
- 领域模型
- 基于 DDD 的示例模型设计

良好的软件设计对于产品或服务的成功，与其所提供的功能同等重要。它对产品的成功具有同等权重；例如，Amazon.com 提供了购物平台，但其架构设计使其与其他相似网站区分开来，并贡献了它的成功。这说明了软件或架构设计对于产品/服务的成功有多么重要。DDD 是软件设计实践之一，我们将通过各种理论和实践示例来对其进行探索。

DDD 是一项关键的设计实践，有助于设计你正在开发的产品的微服务。因此，在进入微服务开发之前，我们首先将探索 DDD。在学习本章之后，你将理解 DDD 对微服务开发的重要性。

## 领域驱动设计基础

企业或云应用程序用于解决业务问题和其他现实世界问题。如果不了解领域，这些问题是无法解决的。例如，如果你不了解股票交易所及其运行机制，就无法为在线交易等金融系统提供软件解决方案。因此，拥有领域知识是解决问题的必要条件。现在，如果你想使用软件或应用程序提供解决方案，你需要在领域知识的帮助下进行设计。当我们将领域与软件设计相结合时，它提供了一种被称为 DDD 的软件方法论。

当我们开发软件来实现提供领域功能的现实场景时，我们便创建了一个领域模型。模型是领域的抽象或蓝图。

> 埃里克·埃文斯（Eric Evans）在他其于 2004 年出版的《领域驱动设计：应对软件核心的复杂性》一书中提出了 DDD 术语。

设计这个模型并不是科学幻想，但它需要领域专家大量的努力、提炼和不断改进。它是软件设计人员、领域专家和开发人员共同的工作。他们组织信息，将其划分为更小的组，逻辑上进行分组，并创建模块。每个模块都可以单独处理，并使用类似的方法进行划分。这个过程可以一直持续到单元级，或者当我们无法进一步细分时。一个复杂的项目可能会有更多的迭代；同样，一个简单的项目可能只有一次迭代。

一旦定义了模型并进行了良好的文档记录，就可以进入下一个阶段——代码设计。因此，在这里我们有一套软件设计——领域模型和代码设计，以及领域模型的代码实现。领域模型提供了解决方案（软件/应用程序）的高层架构，而代码实现则赋予领域模型生命，使其成为运行的模型。

DDD 让设计和开发协同工作。它提供了持续开发软件的能力，同时根据从开发中收到的反馈保持设计的更新。它解决了敏捷和瀑布方法提供的一个局限性，使软件（包括设计和代码）具有可维护性，并保持应用程序的最小可行性。

## 领域驱动设计

设计驱动开发涉及从初始阶段就开始的开发人员，以及建模过程中所有软件设计人员与领域专家讨论领域的会议。它为开发人员提供了理解领域的正确平台，并提供了分享领域模型实现早期反馈的机会。它消除了在后期利益相关者等待交付物时出现的瓶颈。

## DDD 基础

为了理解领域驱动设计，我们可以将这三个概念大致归类为：

- 通用语言（Ubiquitous language）和统一建模语言（UML）
- 多层架构
- 构件（组件）

接下来的章节将解释通用语言和多层架构的作用和重要性。还将解释模型驱动设计中使用的不同构件。

### 通用语言

通用语言是项目内部通信的共同语言。正如我们所见，设计模型是软件设计人员、领域专家和开发人员共同努力的结果；因此，需要一种共同语言来进行交流。DDD 使得使用通用语言变得必要。领域模型在其图表、描述、演示和会议中使用通用语言。它消除了他们之间的误解、误读和沟通隔阂。它必须包含在所有的图表、描述、演示、会议等等——简而言之，在一切之中。

在创建模型时通用语言被使用且流行。它也有一些局限性；当你有成千上万个类时，很难表示组件为 UI、应用程序逻辑等。

## 多层架构

多层架构是 DDD 的常用解决方案。它包含四层：

1. 表现层或用户界面（UI）。
2. 应用层。
3. 领域层。
4. 基础设施层。

![](img/f551c3d57000fcdbbc12682675af973_0)

你可以看到只有领域层负责模型，其他负责 UI、应用程序逻辑等。这种分层架构非常重要。它将领域代码与其他层分开。在多层架构中，每层包含各自的代码，有助于实现松耦合并避免代码混合。

### 表现层

该层代表 UI，为交互和信息显示提供用户界面。该层可以是 Web 应用程序、移动应用程序或调用服务的第三方应用程序。

### 应用层

该层负责应用程序逻辑。它维护并协调产品/服务的整体流程。它不包含业务逻辑或 UI。它可能持有应用程序的状态，例如进行中的任务。例如，你的产品 REST 服务就属于应用层。

### 领域层

领域层是非常重要的层，因为它包含了领域信息和业务逻辑。它持有业务对象的状态。它持久化业务对象，并将这些持久化状态传递给基础设施层。

### 基础设施层

该层支持所有其他层并负责层之间的通信。它包含了其他层使用的支持库。它还实现了业务对象的持久化。

为了理解不同层之间的交互，让我们以餐厅订位为例。最终用户使用 UI 发起订位请求。UI 将请求传递给应用层。应用层从领域层获取领域对象（如餐厅、桌子、日期等）。领域层从基础设施获取这些已持久化的对象，并调用相关方法进行订位并将其持久化回基础设施层。一旦领域对象持久化，应用层就会向最终用户显示订位确认。

## 领域驱动设计的产物

DDD 中使用了七种不同的产物来表达、创建和检索领域模型：

- 实体 (Entities)
- 值对象 (Value objects)
- 服务 (Services)
- 聚合 (Aggregates)
- 存储仓库 (Repository)
- 工厂 (Factory)
- 模块 (Module)

## 实体

实体是某些可识别的且在产品/服务的状态过程中保持不变的对象类型。这些对象不是通过它们的属性识别的，而是通过它们的身份和连续性来的。这类对象被称为**实体**。

这听起来非常简单，但它具有复杂性。我们需要理解如何定义实体。以一个表格订位系统为例，我们有一个 `restaurant` 类，包含餐厅名称、地址、电话号码、成立数据等属性。我们可以两个 `restaurant` 类的实例，它们无法通过餐厅名称来识别，因为可能存在其他同名的餐厅。同样，如果我们根据任何其他属性，也找不到任何可以唯一标识某个特定餐厅的属性。如果两家餐厅的所有属性值都相同，它们就是同一个，并且可以互相替换。尽管如此，它们仍然不是实体，因为它们都具有不同的引用（内存地址）。

相反，让我们来看美国公民类。每位公民都有自己的社会安全号码。这个号码不仅是唯一的，而且在公民的生命范围内保持不变，并确保了连续性。这个公民存在于内存中，会被序列化，然后从内存中移除并存储在数据库中。它在人去世后仍然存在。只要系统存在，它就会一直留在系统中。无论表现形式如何，公民的社会安全号码都保持不变。

因此，在产品中创建实体意味着创建一个身份。现在，给上一个示例中的任何餐厅赋予一个身份，可以使用餐厅名称、成立日期和街道等属性组合，或者添加一个如 `restaurant_id` 的标识符来标识它。基本规则是两个标识符不能相同。因此，当我们为实体引入标识符时，我们需要确保它的准确性。

为对象创建唯一身份有不同的方法，描述如下：

- 使用表中的主键。
- 使用领域模块自动生成的 ID。领域程序生成标识符并将其分配给跨层持久化的对象。
- 少数现实世界对象带有用户定义的标识符。例如，每个国家都有自己的国际直拨区码（ISD）。
- 复合键。这是属性的组合，也可以用于创建标识符，正如前面餐厅对象所解释的那样。

> 实体对于领域模型非常重要。因此，它们应该从建模过程的初始阶段就进行定义。

当一个对象可以通过其标识符而不是其属性来识别时，表示这些对象的类应该有一个简单的定义，并且应该注意其生命周期的连续性和身份。识别该类中具有相同属性值的对象是关键的。定义的系统应该为每个查询的对象返回唯一的结果。设计者应该确保模型定义了什么是“是同一个东西”的含义。

## 值对象

值对象（VOs）简化了设计。实体具有身份、连续性以及不定义其身份的属性等特征。与实体相比，值对象只有属性而没有概念上的身份。最佳实践是将对象保持为不可变对象。如果可能，你甚至应该让实体对象也保持不可变。

实体概念会倾向于让你将所有对象视为实体，即内存或数据库中唯一可识别且具有周期连续性的对象，但每个对象必须有一个实例。现在，假设你正在创建客户实体对象。每个客户对象都代表一个餐厅顾客，这不能用于预订其他客的订单。如果客户使用该系统，内存中将产生数百万个客户实体对象。系统中存在数百万个唯一可识别的对象，但每个对象都被跟踪。创建和跟踪这些对象需要一个高度可靠的系统，这不仅非常复杂，而且消耗资源。这可能导致系统性能下降。因此，使用值对象而不是实体是非常重要的。原因将在接下来的几段中解释。

应用程序不需要可追溯且具有可识别的客户对象。在某些情况下，你只需要领域元素的部分或全部属性。这些就是可以使用值对象的情况。这让事情变得简单并提高了性能。

由于缺少身份，值对象可以很容易地创建和销毁。这简化了设计——如果没有其他对象引用它们，值对象就可以被垃圾回收。

让我们讨论值对象的不可变性。值对象应该被设计和编码为不可变。一旦被创建，它们在生命周期内永远不应被修改。如果你需要 VO 或其任何对象的不同值，只需创建一个新的值对象，而不要修改原始值对象。在这里，不可变性携带了`面向对象编程 (OOP)`的所有意义。当且仅当值对象是不可变的时，它就可以被共享和使用而不影响其完整性。

## 常见问题

- 值对象可以包含另一个值对象吗？
  是的，可以
- 值对象可以引用另一个值对象或实体吗？
  是的，可以
- 我可以使用不同值对象或实体的属性创建值对象吗？
  是的，可以

## 服务

在创建领域模型时，你可能会遇到行为可能与任何对象都不相关的这种情况。这些行为可以放在服务对象中。

服务对象是领域层的一部分，没有任何内部状态。它的唯一目的是为领域提供不属于单个实体或值对象的行为。

通用语言帮助你在建模过程中识别具有不同属性和行为的对象、身份和值对象。在创建领域模型的过程中，你可能会发现不属于任何特定对象的行为或方法。这些行为是重要的，不能忽视。你无法将它们添加到实体或值对象中。添加不属于它的行为会破坏该对象。记住，行为可能会影响多个对象。面向对象编程的使用使得附加到某些对象变得可能，这被称为服务。

服务在技术框架中很常见。它们也被用于 DDD 中的领域层。创建服务时，你需要满足以下所有点：

- 服务对象的行为在实体和值对象上执行，但不属于实体或值对象
- 服务对象的行为状态不维护，因此它们是无状态的
- 服务是领域模型的一部分

服务可能存在于其他层中。保持领域层服务的隔离是非常重要的。这消除了复杂性并保持了设计的解耦。

让我们来看一个例子，餐厅老板想查看他的每月报告。在这种情况下，他将以管理员身份登录，并在提供必要的输入字段（如时长）后点击显示报告按钮。应用层将请求传递给拥有报告（report）和模板（templates）对象的领域层，并带上报告 ID 等参数。使用模板创建报告，数据则从数据库或其他源获取。然后，应用层将所有参数（包括报告 ID）传递给业务层。在这里，需要从数据库或其他源获取模板，以便根据 ID 生成报告。此操作既不属于报告对象，也不属于模板对象。因此，使用一个服务对象（service object）来执行此操作，从数据库中检索所需的模板。

## 聚合（Aggregates）

聚合领域模式与对象的生命周期有关，定义了所有权和边界。

当你使用应用程序在喜爱的餐厅在线预订位置时，你不需要担心完成预订所需的内部系统和流程，包括搜索可用餐厅、检查给定日期和时间是否有可用空位等。因此，你可以说订位应用程序是几个其他对象的**聚合（aggregate）**，并作为订位系统中所有其他对象的**根（root）**。

这个根应该是一个将对象集合绑定在一起的实体。它也被称为**聚合根（aggregate root）**。根对象不会向外部世界传递内部对象的任何引用，并保护内部对象内部执行的更改。

我们需要理解为什么需要聚合器。领域模型可能包含大量的领域对象。应用程序的功能和规模越大，设计越复杂，存在的对象就越多。这些对象之间存在关系。某些对象之间可能是多对多的关系，少数对象之间是一对多的关系，另一些则可能是一对一的关系。这些关系通过代码中的模型实现或数据库强制执行，以确保对象之间的关系保持完整。关系不是单向的；它们也可以是双向的。它们会增加复杂性。

设计者的工作是简化模型中的这些关系。现实领域中可能存在某些关系，但在领域模型中可能不需要。设计者需要确保此类关系在领域模型中不存在。同样，可以通过这些约束来减少基数（multiplicity）。一个约束就可以完成由许多对象满足该关系的工作。双向关系也可能转换为单向关系。

无论你投入了多少简化工作，模型中可能仍然存在某些关系。这些关系需要在代码中进行维护。当一个对象被删除时，代码应该从其他地方删除对该对象的所有引用。例如，从一个表中删除记录，需要在所有以外键等形式引用该它的地方进行处理，以保持数据一致性并维护完整性。此外，每当数据更改时，都需要强制并维护不变性（invariants）。

关系、约束和不变性带来了复杂性，这需要在代码中进行高效处理。我们通过使用由称为“根”的单一实体表示的聚合来找到解决方案，它与一组在数据变化方面保持一致的对象相关联。

这个根是唯一可以从外部访问的对象，因此该根充当了将内部对象与外部世界隔离开的边界。根可以引用一个或多个内部对象，这些内部对象可以引用其他内部对象，这些内部对象可能与根有也无关系。然而，外部对象也可以引用根，而不引用任何内部对象。

聚合确保了数据完整性并强制不变性。外部对象不能对内部对象进行任何更改；它们只能更改根。然而，它们可以通过调用暴露的操作利用根更改内部对象。如果需要，根应该将内部对象的值传递给外部对象。

如果聚合对象存储在数据库中，则查询应只返回聚合对象。当对象在内部链接到聚合根时，应使用关联遍历（Traversal associations）来返回该对象。这些内部对象可能还有对其他聚合的引用。

聚合根实体持有其全局身份（global identity），并在实体内部持有本地身份（local identities）。

订位系统中聚合的一个简单示例是客户。客户可以暴露给外部对象，它们的根对象包含它们的内部对象地址和联系信息。

当被请求时，内部对象的值对象（如地址）可以传递给外部对象：

| 客户 | 联系信息 |
|---|---|
| customerID | workPhone |
| firstName | homePhone |
| lastName | email |
| 地址 | |
|---|---|
| houseNo | |
| street | |
| Area | |
| city | |
| state | |

![](img/f551c3d57000fcdbbc1268267d5af69e_81_0.png)

## 仓库（Repository）

在领域模型中，在给定时刻可能存在许多领域对象。每个对象可能有其自己的生命周期，从对象的创建到删除或持久化。当任何领域操作需要领域对象时，它应该高效地检索所请求对象的引用。如果你不在中心对象中维护所有可用领域对象，将非常困难。中心对象持有所有对象的引用，并负责返回请求的对象引用。这个中心对象被称为**仓库（repository）**。

仓库是与数据库或文件系统等基础设施交互的点。仓库对象是领域模型的一部分，它与数据库、外部源等存储进行交互，以检索持久化对象。当仓库接收到对象引用的请求时，它返回已存在的对象。如果它在仓库中不存在，则从存储器中检索。例如，如果你需要一个客户，你会查询仓库以提供带 ID 的客户。如果客户已经在仓库中，仓库将提供该客户对象；如果不在，它将查询持久化存储（如数据库），获取它并提供其引用。

使用仓库的主要优势是拥有一种一致的方法来获取对象，请求者不需要直接与存储进行交互。

仓库可以从各种存储类型查询对象，例如数据库、文件系统、工厂仓库等。在这种情况下，仓库可能拥有策略，策略指向不同对象类型或类别的不同源：

![](img/f551c3d57000fcdbbc1268267d5af69e_82_0.png)

如仓库对象流图所示，仓库与基础设施层交互，而该接口是领域层的一部分。请求者可能属于领域层或应用层。仓库帮助系统管理领域对象的生命周期。

## 工厂（Factory）

当简单的构造函数不足以创建对象时，就需要工厂。它帮助创建复杂对象，或涉及创建其他相关对象的聚合。

工厂也是领域对象生命周期的一部分，因为它负责创建这些对象。工厂和仓库在某种程度上是相互关联的，因为它们都引用领域对象。工厂引用新创建的对象，而仓库返回已存在的对象。

让我们通过一个用户创建流程应用程序来观察控制流是如何的。假设有一个用户使用用户名 `user1` 注册。该用户的创建过程首先与工厂交互，工厂创建名称 `user1`，然后将其缓存在领域存储库中，同时将其存储在存储器中以进行持久化。

当同一用户再次登录时，调用将移动到存储库进行引用。这会使用存储器加载引用并将其传递给请求者。

请求者随后可以使用此 `user1` 对象在指定的餐厅和指定的时间预订桌。这些值作为参数传递，并使用存储库在存储器中创建一条订桌记录：

![](img/f551c3d57000fcdbbc1268267d5af69e_83_0.png)

工厂可能会使用面向对象的编程模式之一（如工厂模式或抽象工厂模式）来创建对象。

## 模块

模块是分离相关业务对象的最佳方式。它们最适用于领域对象较大的项目。对于终端用户来说，将领域模型划分为模块并设置这些模块之间的关系是有意义的。一旦你理解了模块及其关系，就能开始看到领域模型的整体视图，从而更容易进一步钻取并理解模型。

模块也有助于代码的高内聚性或保持低耦合性。可以使用通用语言（Ubiquitous language）来命名这些模块。对于订桌系统，我们可以有不同的模块，例如用户管理、餐厅和桌位、分析和报告等。

## 策略设计与原则



# 企业模型通常非常大且复杂

企业模型通常非常大且复杂。它可能分布在组织的不同部门之间。每个部门可能有一支独立的领导团队，因此共同工作和设计可能会产生困难和协调问题。在这种情况下，维护领域模型的完整性并不是一项轻松的任务。

在这些情况下，在统一模型上工作并不是解决方案，大型企业模型需要被分为不同的子模型。这些子模型包含了极其详细的准确关系和契约。每个子模型必须无例外地维护定义的契约。

可以遵循各种原则来维护领域模型的完整性，列举如下：

- **边界上下文** (Bounded Context)
- **持续集成** (Continuous Integration)
- **上下文映射** (Context Map)
  - **共享内核** (Shared Kernel)
  - **客户-供应商** (Customer-Supplier)
  - **顺从者** (Conformist)
  - **反腐层** (Anticorruption Layer)
  - **分离方式** (Separate Ways)
  - **开放主机服务** (Open Host Service)
  - **蒸馏** (Distillation)

# 领域驱动设计

## 第 3 章

## 边界上下文

当你有不同的子模型时，当所有子模型结合时维护代码是很困难的。你需要一个分配给单个团队的小模型。你可能需要收集相关元素并将它们分组。上下文通过应用一组条件，保留并维护为其相应子模型定义的领域术语的含义。

这些领域术语定义了模型的范围，创建了上下文的边界。

边界上下文看起来与你在上一节中学到的模块非常相似。事实上，模块是边界上下文的一部分，边界上下文定义了子模型发生和开发的逻辑框架。而模块组织了领域模型的元素，并在设计文档和代码中可见。

现在，作为一名设计者，你必须保持每个子模型都有良好的定义且一致。这样，你就可以独立地重构每个模型，而不影响其他子模型。这为软件设计人员提供了灵活性，可以在任何时间对其进行精炼和改进。

现在，让我们检查我们一直使用的订桌示例。当你开始设计系统时，你会看到客人会访问应用程序，并在指定的餐厅、日期和时间请求预订桌位。然后，有一个后端系统通知餐厅预订信息，同样，餐厅也会根据订桌情况更新他们的系统，因为桌位也可以由餐厅自己预订。所以，当你查看系统的细微差点时，你可以看到两个领域模型：

- 在线订桌系统
- 离线餐厅管理系统

它们都有自己的边界上下文，你只需要确保它们之间的接口运行良好。

## 持续集成

当你开发时，代码散布在许多团队和各种技术中。这些代码被组织在不同的模块中，并为相应的子模型具有相应的边界上下文。

这种开发可能会在代码重复、代码破坏或边界上下文损坏方面带来某种程度的复杂性。它的发生不仅是因为代码和领域模型的规模巨大，还因为其他因素，例如团队成员的变动、新成员的加入或缺乏良好的文档模型（仅列举几个）。

当使用 DDD 和敏捷方法设计和开发系统时，领域模型在编码开始之前并没有完全设计，领域模型及其元素随着时间的推移而演进，并逐渐发生持续的改进和精炼。

因此，集成持续持续，这是今天开发的关键原因之一。在持续集成中，代码被频繁合并以避免领域模型的任何中断和问题。合并后的代码不仅被部署，还经常接受测试。市场上有很多各种持续集成工具，可以在不同时间对代码进行合并、构建和部署。在这些日子，组织更加强调持续流的自动化。`Hudson`、`TeamCity` 和 `Jenkins CI` 是持续集成的一些常用可用工具。`Hudson` 和 `Jenkins CI` 是开源工具，而 `TeamCity` 是专有工具。

在每个构建中附带测试套件可以确认模型的一致性和完整性。测试套件从物理角度定义了模型，而 UML 则告知你任何需要更改代码的错误或意外结果。

## 上下文映射

上下文映射帮助你理解企业应用程序的整体视图。它展示了边界上下文出现在企业模型中的方式以及它们是如何相互关联的。因此，我们可以说任何解释边界上下文及其关系的图表或文档都称为上下文映射。

上下文映射帮助所有团队成员（无论是在同一个团队还是在不同的团队）以各种部分（边界上下文或子模型）的形式理解高层级企业模型。

这让个人对所执行的任务有更清晰的认识，并可能允许他们对模型的完整性提出任何担忧/问题：

![](img/f551c3d57000fcdbbc1268267d5af69e_87_0.png)

上下文映射示例图是上下文映射的一个样本。在这里，`Table1` 和 `Table2` 都出现在**订桌上下文** (Table Reservation Context) 中，也出现在**餐厅账目上下文** (Restaurant Ledger Context) 中。有趣的地方是，`Table1` 和 `Table2` 在每个边界上下文中都有各自的概念。在这里，使用通用语言将边界上下文命名为**订桌**和**餐厅账目**。

在下一节中，我们将探索一些用于定义上下文映射不同上下文之间通信的模式。

## 共享内核

正如名称所示，边界上下文的一部分与另一个的边界上下文共享。正如底图所示，`Restaurant` 实体正在**订桌上下文** (Table Reservation Context) 和**餐厅账目上下文** (Restaurant Ledger Context) 之间共享：

![](img/f551c3d57000fcdbbc1268267d5af69e_88_0.png)

## 客户-供应商 (Customer-Supplier)

客户-供应商模式代表了两个边界上下文之间的关系，当一个边界上下文的输出是另一个边界上下文的需求时。也就是说，其中一个向另一个提供信息（被称为客户），由后者消费这些信息。

在现实世界的示例中，汽车经销商在汽车制造商交付汽车之前无法销售汽车的。因此，在这个领域模型中，汽车制造商是供应商，经销商是客户。这种关系建立了一种客户-供应商关系，因为一个边界上下文（汽车制造商）的输出（汽车）是另一个边界上下文（经销商）所需要的。

在这里，客户和供应商团队应该定期会面，以建立合同并形成正确的协议来相互通信。

## 顺从者 (Conformist)

这种模式与客户和供应商模式相似，一方需要提供合同和信息，而另一个则需要使用它。在这里，参与上游/下游关系的不是边界上下文，而是实际团队。

此外，上游团队由于缺乏动力，并不会满足下游团队的需求。因此，下游团队可能需要提供并处理某些永远不会出现的项。为了解决此类情况，如果供应商提供的信息价值不足，客户团队可以开发自己的模型。如果供应商提供的信息确实很有价值或具有部分价值，客户可以使用接口或翻译器（translators），这些工具可以用于使用自己的模型来消费供应商提供的信息。

## 反腐层 (Anticorruption Layer)

反腐层仍然是领域的一部分，当系统需要从外部系统或其自身的遗留系统获取数据时使用。在这里，反腐层是与外部系统交互的层，并在领域模型中使用外部系统数据，而不会影响领域模型的完整性和原始性。

在大多数情况下，一个服务可以作为反腐层，该服务可以使用带有适配器（adapter）和翻译器的外观模式（facade pattern），在内部模型内部外部领域数据。因此，你的系统将使用该服务来检索数据。服务层可以使用外观模式进行设计。这将确保它能与领域模型协同工作，以给定的格式提供所需的数据。该服务还可以使用适配器和翻译器模式，以确保无论外部源发送什么格式和层次结构，服务都能以所需的格式提供，并使用适配器和翻译器处理层次结构。

## 分离方式 (Separate Ways)

当你有一个企业级应用和一个领域，其中不同领域没有共同元素，并且它由独立运行的小子模型组成，但对终端用户来说仍然作为一个单一应用运行。

在这种情况下，设计者可以创建没有关系的独立模型，并在它们之上开发小型应用程序。这些小型应用程序在合并时就会变成一个单一应用程序。

雇主的内部网应用程序提供了各种小型应用程序，例如与人力资源相关的、问题跟踪器、交通或公司内部社交网络，这就是这样一种设计者可以使用“分离方式”模式的应用程序。

集成使用独立模型开发的应用程序将非常具有挑战性且复杂。因此，在实现此模式之前，你应该仔细考虑。

## 开放主机服务 (Open Host Service)

当两个子模型相互作用时，会使用翻译层。当你将模型与外部系统集成时，会使用这种翻译层。当你有一个子模型使用的这个外部系统被许多子模型使用，为了消除多余和重复的代码，就需要为每个子模型系统编写翻译层，此时就需要开放主机服务。

开放主机服务通过包装器（wrapper）为所有子模型提供外部系统的服务。

## 蒸馏 (Distillation)

如你所知，蒸馏是提纯液体的过程。同样，在 DDD 中，蒸馏是过滤掉不需要的信息并保留所需信息的过程。

```java
public int getCapacity() {
    return capacity;
}
```

现在，我们可以实现如下所示的聚合类。在这里，只使用了基础属性。你可以根据需要添加任意数量的属性，也可以添加其他功能：

```java
public class Restaurant extends BaseEntity<String> {
    private List<Table> tables = new ArrayList<>();
    public Restaurant(String name, String id, List<Table> tables) {
        super(id, name);
        this.tables = tables;
    }

    public void setTables(List<Table> tables) {
        this.tables = tables;
    }

    public List<Table> getTables() {
        return tables;
    }

    @Override
    public String toString() {
        return new StringBuilder("id: ").append(id).append(", name: ")
            .append(name).append(", tables: ")
            .append(tables).append(":").toString();
    }
}
```

# 存储库实现

现在我们可以按照本章所学的模式实现存储库模式。首先，你将创建两个接口：`Repository` 和 `ReadOnlyRepository`。`ReadOnlyRepository` 接口将用于为只读操作提供抽象，而 `Repository` 抽象将用于执行所有类型的操作：

```java
public interface ReadOnlyRepository<TE, T> {
    boolean contains(T id);
    Entity get(T id);
    Collection<TE> getAll();
}
```

基于此接口，我们可以创建 `Repository` 的抽象，它将执行添加、删除和更新等额外操作：

```java
public interface Repository<TE, T> extends ReadOnlyRepository<TE, T> {
  void add(TE entity);
  void remove(T id);
  void update(TE entity);
}
```

之前定义的 `Repository` 抽象可以用适合你自己的方式来实现，以持久化你的对象。持久化代码的更改（属于基础设施层的一部分）不会影响你的领域层代码，因为合约和抽象是由领域层定义的。领域层使用抽象类和接口来消除了对直接具体类的使用，并提供了松耦合。为了演示之目的，我们可以简单地使用留在内存中的 map 来持久化对象：

```java
public interface RestaurantRepository<Restaurant, String> extends Repository<Restaurant, String> {
  boolean containsName(String name);
}
```

```java
public class InMemRestaurantRepository implements RestaurantRepository<Restaurant, String> {
  private Map<String, Restaurant> entities;

  public InMemRestaurantRepository() {
    entities = new HashMap();
  }

  @Override
  public boolean containsName(String name) {
    return entities.containsKey(name);
  }

  @Override
  public void add(Restaurant entity) {
    entities.put(entity.getName(), entity);
  }

  @Override
  public void remove(String id) {
    if (entities.containsKey(id)) {
        entities.remove(id);
    }
  }

  @Override
  public void update(Restaurant entity) {
    if (entities.containsKey(entity.getName())) {
        entities.put(entity.getName(), entity);
    }
  }

  @Override
  public boolean contains(String id) {
    throw new UnsupportedOperationException("Not supported yet.");
    // To change body of generated methods, choose Tools | Templates.
  }

  @Override
  public Entity get(String id) {
    throw new UnsupportedOperationException("Not supported yet.");
    // To change body of generated methods, choose Tools | Templates.
  }

  @Override
  public Collection<Restaurant> getAll() {
    return entities.values();
  }
}
```

# 服务实现

与前一种方法相同，你可以将领域服务的抽象分为两部分——主服务抽象和只读服务抽象：

```java
public abstract class ReadOnlyBaseService<TE, T> {
    private final Repository<TE, T> repository;

    ReadOnlyBaseService(ReadOnlyRepository<TE, T> repository) {
        this.repository = repository;
    }
    // ...
}
```

现在，我们可以使用这个 `ReadOnlyBaseService` 来创建 `BaseService`。在这里，我们通过构造函数使用依赖注入模式将具体对象映射到抽象上：

```java
public abstract class BaseService<TE, T> extends ReadOnlyBaseService<TE, T> {
    private final Repository<TE, T> _repository;

    BaseService(Repository<TE, T> repository) {
        _repository = repository;
    }

    public void add(TE entity) throws Exception {
        _repository.add(entity);
    }

    public Collection<TE> getAll() {
        return _repository.getAll();
    }
}
```

现在，在定义了服务抽象后，我们可以如下所示实现 `RestaurantService`：

```java
public class RestaurantService extends BaseService<Restaurant, BigInteger> {
    private final RestaurantRepository<Restaurant, String> restaurantRepository;

    public RestaurantService(RestaurantRepository repository) {
        super(repository);
        restaurantRepository = repository;
    }

    public void add(Restaurant restaurant) throws Exception {
        if (restaurantRepository.containsName(restaurant.getName())) {
            throw new Exception(String.format("There is already a product with name - %s", restaurant.getName()));
        }
    }
}
```



同样，你也可以为其他实体编写实现。这段代码是一个基础实现，你可以在生产代码中添加各种实现和行为。我们可以创建一个应用程序类来执行并测试我们编写的模型。`RestaurantApp.java` 文件如下：

```java
public class RestaurantApp {
    public static void main(String[] args) {
        try {
            // 初始化服务
            RestaurantService restaurantService = new RestaurantService(InMemRestaurantRepository());

            // 数据的创建
            Table table1 = new Table("Table 1", BigInteger.ONE, 6);
            Table table2 = new Table("Table 2", BigInteger.valueOf(2), 4);
            Table table3 = new Table("Table 3", BigInteger.valueOf(3), 2);
            List<Table> tableList = new ArrayList<>();
            tableList.add(table1);
            tableList.add(table2);
            tableList.add(table3);
            Restaurant restaurant1 = new Restaurant("Big-O Restaurant", tableList);

            // 使用服务添加的餐厅
            restaurantService.add(restaurant1);

            // 注意：为了引发异常，给下面的一个相同的餐厅名称
            Restaurant restaurant2 = new Restaurant("Pizza Shops", "2", null);
            restaurantService.add(restaurant2);

            Restaurant restaurant3 = new Restaurant("La Pasta", "3", null);
            restaurantService.add(restaurant3);

            // 使用服务获取所有餐厅
            Collection<Restaurant> restaurants = restaurantService.getAll();

            // 将获取的餐厅打印到控制台
            System.out.println("Restaurants List:");
            restaurants.stream().forEach((restaurant) -> {
                System.out.println(String.format("Restaurant: %s", restaurant));
            });
        } catch (Exception ex) {
            System.out.println(String.format("Exception: %s", ex.getMessage()));
        }
        // 异常处理代码
    }
}
```

要运行此程序，可以在 IDE 中直接运行或使用 Maven 运行。它将输出以下内容：

```
Scanning for projects...

Building 6392-chapter3 1.0-SNAPSHOT

--- exec-maven-plugin:1.5.0:java (default-cli) @ 6392_chapter3 --
Restaurants List:
Restaurant: {id: 3, name: La Pasta, tables: null}
Restaurant: {id: 2, name: Pizza Shops, tables: [{id: 1, name: Table 1, capacity: 6}, {id: 2, name: Table 2, capacity: 4}, {id: 3, name: Table 3, capacity: 2}]}


BUILD SUCCESS
```

## 总结

在本章中，你学习了领域驱动设计（DDD）的基础知识。你还探索了多层架构以及可用于 DDD 开发软件的不同模式。到此时，你应该已经意识到领域模型设计对于软件的成功至关重要。最后，我们通过餐厅餐桌预订系统演示了一个领域服务的具体实现。

在下一章中，你将学习如何使用该设计来实现示例项目。该示例项目的设计说明源自上一章，并将使用 DDD 来构建微服务。本章不仅涵盖了编码内容，还涵盖了微服务的不同方面，如构建、单元测试和打包。在下一章结束时，示例微服务项目将准备好进行部署和调用。

# 第 4 章 实现微服务

本章将带你从设计阶段进入到示例项目的实现——一个在线餐桌预订系统（OTRS）。在这里，你将使用上一章中解释的设计并对其进行增强，以构建微服务。在本章结束时，你不仅学习了如何实现该设计，还学习了微服务的不同方面——构建、测试和打包。虽然重点是构建和实现餐厅微服务，但你可以使用相同的方法来构建和实现 OTRS 中使用的其他微服务。

在本章中，我们将涵盖以下主题：

- OTRS 概述
- 微服务的开发与实现
- 测试

我们将使用上一章中演示的领域驱动设计核心概念。在上一章中，你看到了如何使用核心 Java（`core Java`）通过领域驱动开发领域模型。现在，我们将从示例领域实现转向 Spring 框架驱动的实现。你将使用 `Spring Boot` 来实现领域驱动设计概念，并将它们从核心 Java 转换为基于 Spring 框架的模型。

此外，我们还将使用 `Spring Cloud`，它提供了一个通过 `Spring Boot` 可用的云解决方案。`Spring Boot` 允许你在服务内部启用依赖于 Tomcat 或 Jetty 的嵌入应用程序容器，并将其打包为 JAR 或 WAR。该 JAR 作为独立进程运行，即微服务，为所有请求提供服务和响应，并指向服务中定义的端点。

`Spring Cloud` 还可以轻松与 `Netflix Eureka` 集成，这是一个服务注册和发现组件。OTRS 将使用它进行微服务的注册和发现。

## OTRS 概述

根据微服务原则，我们需要为每个功能分离微服务。在观察 OTRS 后，我们可以很容易将其分为三个主要的微服务——餐厅服务（Restaurant service）、预订服务（Booking service）和用户服务（User service）。OTRS 中还可以定义其他微服务。我们的重点是这三个微服务。其理念是让它们保持独立，拥有各自独立的数据库。

我们可以将这些服务的功能总结如下：

- **餐厅服务**：该服务提供餐厅资源的功能——创建、读取、更新、删除（CRUD）操作以及基于标准的搜索。它提供了餐厅与餐桌之间的关联。餐厅还会提供对表（`Table`）实体的访问。
- **用户服务**：如名所示，该服务允许终端用户对用户（`User`）实体执行 CRUD 操作。
- **预订服务**：该服务利用餐厅服务和用户服务对预订执行 CRUD 操作。它将使用餐厅搜索，并根据指定时间内的餐桌可用性进行关联查找和分配。它创建了餐厅/餐桌与用户之间的关系：

![](img/f551c3d57000fcdbbc1268267d5af69e_101_0.png)

前面的图显示了每个微服务如何独立工作。这就是为什么微服务可以被单独开发、增强和维护，而不影响其他服务的原因。这些服务可以各自拥有自己的分层架构和数据库。不限制使用相同的技术、框架和语言来开发这些服务。在任何给定时间，你都可以引入新的微服务。例如，为了会计目的，我们可以引入一个会计服务，并暴露给餐厅用于记账。同样，分析和报告是其他可以集成并暴露的其他服务。

为了演示目的，我们只实现前面所示的三个服务。

## 开发和实现微服务

我们将使用上一章描述的领域驱动实现方法，使用 `Spring Cloud` 实现微服务。让我们回顾一下关键构件：

- **实体**：这些是可识别的、且在产品/服务的状态过程中保持不变的对象类别。这些对象不是通过它们的属性定义的，而是通过它们的身份和连续性定义的。实体具有身份、连续性以及不定义其身份的属性特征。
- **值对象**：只有属性而没有概念身份。最佳实践是将值对象保持为不可变对象。在 Spring 框架中，实体是纯 POJOs；因此我们也会把它们用作值对象。
- **服务对象**：这些在技术框架中很常见。它们也被用于领域驱动设计中的领域层。服务对象没有内部状态；它的唯一目的是为领域提供行为。服务对象提供了无法与特定实体或值对象相关的行为。服务对象可能为一个或多个实体或值对象提供一个或多个相关行为。在领域模型中显式定义服务是最佳实践。
- **仓库对象**：仓库对象是领域模型的一部分，它与存储（如数据库、外部源等）交互以检索持久化对象。当仓库接收到对象引用的请求时，它返回现有的对象引用。如果请求的对象在仓库中不存在，则它从存储器中检索该对象。

### 下载示例代码

下载代码包的详细步骤在本书的序言中提到。请查阅。本书的代码包也托管在 GitHub 上：`https://github.com/PacktPublishing/Mastering-Microservices-with-Java`。我们从丰富的书籍和视频目录中还有其他代码包可用，地址为：`https://github.com/PacktPublishing/`。去看看它们吧！

每个 OTRS 微服务 API 都代表一个 RESTful Web 服务。OTRS API 使用诸如 `GET`、`POST` 等 HTTP 动词以及 RESTful 端点结构。请求和响应负载格式化为 JSON。如果需要，也可以使用 XML。

### 餐厅微服务

餐厅微服务将通过 REST 端点暴露给外部世界进行调用。我们在餐厅微服务示例中找到以下端点。可以根据需要添加任意端点：

#### 1. 通过 ID 获取餐厅的端点

| Endpoint | GET /v1/restaurants/<Restaurant-Id> |
| :--- | :--- |
| Name | Description |
| Restaurant_Id | 代表与此 ID 关联的唯一餐厅的路径参数 |
| Request Property | Type | Description |
| None | | |
| Response Property | Type | Description |
| Restaurant | 给定 ID 关联的餐厅对象 |

#### 2. 通过名称搜索餐厅的端点

| 端点 | GET /v1/restaurants/ |
| :--- | :--- |
| 名称 | 描述 |
| 无 | | |
| 请求属性 | 类型 | 描述 |
| Name | String | 表示餐厅名称或餐厅名称子字符串的查询参数 |
| 响应属性 | 类型 | 描述 |
| Restaurants | 餐厅对象数组 | 返回所有名称包含给定值的餐厅 |

#### 3. 创建新餐厅的端点

| 端点 | POST /v1/restaurants/ |
| :--- | :--- |
| 名称 | 描述 |
| 无 | | |
| 请求属性 | 类型 | 描述 |
| Restaurant | 餐厅对象 | 餐厅对象的 JSON 表示形式 |
| 响应属性 | 类型 | 描述 |
| Restaurant | 餐厅对象 | 新创建的 Restaurant 对象 |

同样，我们可以添加各种端点及其实现。为了演示目的，我们将使用 `Spring Cloud` 实现上述的端点。

### OTRS 实现

我们将创建一个多模块 Maven 项目来实现 OTRS。将使用以下技术栈来开发 OTRS 。请注意，在编写本书时，只有 `Spring Boot` 和 `Spring Cloud` 的快照版本可用。因此，在最终发布中可能会发生一两处变化：

- Java 版本 1.9
- `Spring Boot` 2.0.0.M1
- `Spring Cloud` Finchley.M2
- `Maven Compiler Plugin` 3.6.1 (用于 Java 1.9)

上述所有点均在根 `pom.xml` 中提到，以及以下 OTRS 模块：

- `eureka-service`
- `restaurant-service`
- `user-service`
- `booking-service`

根 `pom.xml` 文件如下所示：

```xml
<xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <model>4.0.0</model>
  <groupId>com.packt.pom</groupId>
  <artifactId>6392-chapter4</artifactId>
  <version>PACKET-SNAPSHOT</version>
  <name>6392_chapter4</name>
  <description>Master Microservices with Java Ed 2, Chapter 4 - 
Implementing Microservices</description>

  <packaging>pom</packaging>
  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
    <java.version>1.9</java.version>
    <maven.compiler.source>1.9</maven.compiler.source>
    <maven.compiler.target>1.9</maven.compiler.target>
  </properties>

  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.0.0.M1</version>
  </dependency>
  <dependencies>
    <dependency>
      <groupId>org.springframework.cloud</groupId>
      <artifactId>spring-cloud-dependencies</artifactId>
      <version>Finchley.M2</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
  </dependencies>

  <modules>
    <module>eureka-service</module>
    <module>restaurant-service</module>
    <module>booking-service</module>
    <module>user-service</module>
  </modules>

  <!-- 构建步骤需要包含以下插件 -->
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.6.1</version>
        <configuration>
          <source>1.9</source>
          <target>1.9</target>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```



# 实现微服务

## RestaurantController 类

```java
@RestController
@RequestMapping("/restaurants")
public class RestaurantController {

    private final Logger logger = Logger.getLogger(RestaurantController.class.getName());
    private final RestaurantService restaurantService;

    @Autowired
    public RestaurantController(RestaurantService restaurantService) {
        this.restaurantService = restaurantService;
    }

    /**
     * 按名称获取餐厅。
     *
     * @param name
     * @return 非空餐厅集合。
     */
    @RequestMapping(method = RequestMethod.GET)
    public ResponseEntity<Collection<Restaurant>> findByName(@RequestParam("name") String name) {
        logger.info(String.format("restaurant-service findByName(%s) invoked: %s",
            name.trim().toLowerCase(), restaurantService.getClass().getName()));
        Collection<Restaurant> restaurants = restaurantService.findByName(name);
        try {
            return restaurants.isEmpty() ? new ResponseEntity<>(HttpStatus.NO_CONTENT) : new ResponseEntity<>(restaurants);
        } catch (Exception ex) {
            logger.log(Level.WARNING, "Exception raised findByName", ex);
            return new ResponseEntity<>(HttpStatus.INTERNAL_SERVER_ERROR);
        }
    }

    /**
     * 根据 ID 获取餐厅。
     *
     * @param restaurant_id
     * @return 非空实体。
     */
    @RequestMapping(value = "/{restaurant_id}", method = RequestMethod.GET)
    public ResponseEntity<Entity> findById(@PathVariable("restaurant_id") String id) {
        logger.info(String.format("restaurant-service findById() invoked: %s", restaurantService.getClass().getName(), id));
        id = id.trim();
        Entity restaurant;
        try {
            restaurant = restaurantService.findById(id);
        } catch (Exception ex) {
            logger.log(Level.SEVERE, "Exception raised findById Rest Call");
            return new ResponseEntity<>(HttpStatus.INTERNAL_SERVER_ERROR);
        }
        return restaurant != null ? new ResponseEntity<>(restaurant, HttpStatus.OK) : new ResponseEntity<>(HttpStatus.NO_CONTENT);
    }

    /**
     * 使用指定信息添加餐厅。
     *
     * @param restaurantVO
     * @return 非空餐厅。
     * @throws RestaurantNotFoundException 如果没有任何匹配项。
     */
    @RequestMapping(method = RequestMethod.POST)
    public ResponseEntity<Restaurant> add(@RequestBody Restaurant restaurantVO) {
        logger.info(String.format("restaurant-service add() invoked: %s", restaurantService.getClass().getName(), restaurantVO.getName()));
        Restaurant restaurant = new Restaurant(null, null, null);
        // 实现细节
        BeanUtils.copyProperties(restaurantVO, restaurant);
        try {
            restaurantService.add(restaurant);
        } catch (Exception ex) {
            logger.log(Level.WARNING, "Exception raised add Restaurant REST Call " + ex);
            return new ResponseEntity<Restaurant>(HttpStatus.UNPROCESSABLE_ENTITY);
        }
        return new ResponseEntity<Restaurant>(HttpStatus.CREATED);
    }
}
```

## Service 类

`RestaurantController` 类使用了 `RestaurantService` 接口。

`RestaurantService` 是一个定义了 CRUD（增删改查）及搜索操作的接口，定义如下：

```java
public interface RestaurantService {

    public void add(Restaurant restaurant) throws Exception;

    public void update(Restaurant restaurant) throws Exception;

    public void delete(String id) throws Exception;

    public Entity findById(String restaurantId) throws Exception;

    public Collection<Restaurant> findByName(String name) throws Exception;

    public Collection<Restaurant> findByCriteria(Map<String, ArrayList<String>> name) throws Exception;
}
```

现在，我们可以实现刚刚定义的 `RestaurantService`。它还扩展了你在上一章中创建的 `BaseService` 类。我们使用 Spring 的 `@Service` 注解将其定义为一个服务：

```java
@Service("restaurantService")
public class RestaurantServiceImpl extends BaseService<Restaurant, String>
implements RestaurantService {

    private RestaurantRepository<Restaurant, String> restaurantRepository;

    @Autowired
    public RestaurantServiceImpl(RestaurantRepository<Restaurant, String> restaurantRepository) {
        this.restaurantRepository = restaurantRepository;
    }

    public void add(Restaurant restaurant) throws Exception {
        if (restaurant.getName() == null || "".equals(restaurant.getName())) {
            throw new Exception("Restaurant name cannot be null or empty string.");
        }

        if (restaurantRepository.containsName(restaurant.getName())) {
            throw new Exception(String.format("There is already a product with the name - %s", restaurant.getName()));
        }

        super.add(restaurant);
    }

    @Override
    public Collection<Restaurant> findByName(String name) throws Exception {
        return restaurantRepository.findByName(name);
    }

    @Override
    public void update(Restaurant restaurant) throws Exception {
        restaurantRepository.update(restaurant);
    }

    @Override
    public void delete(String id) throws Exception {
        restaurantRepository.remove(id);
    }

    @Override
    public Entity findById(String restaurantId) throws Exception {
        return restaurantRepository.get(restaurantId);
    }

    @Override
    public Collection<Restaurant> findByCriteria(Map<String, ArrayList<String>> name) throws Exception {
        throw new UnsupportedOperationException("Not supported yet."); // To change body of generated methods, choose Tools | Templates.
    }
}
```

## Repository 类

`RestaurantRepository` 接口定义了两个方法：`containsName` 和 `findByName`。它还扩展了 `Repository` 接口：

```java
public interface RestaurantRepository<T, ID> extends Repository<T, ID> {
    boolean containsName(String name) throws Exception;

    Collection<T> findByName(String name) throws Exception;
}
```

`Repository` 接口定义了三个方法：`add`、`remove` 和 `update`。它还扩展了 `ReadOnlyRepository` 接口：

```java
public interface Repository<TE, T> extends ReadOnlyRepository<TE, T> {
    void add(TE entity);
    void remove(T id);
    void update(TE entity);
}
```

`ReadOnlyRepository` 接口包含 `get` 和 `getAll` 方法，它们分别返回布尔值、实体和实体集合。如果你只想暴露仓库的只读抽象，这个接口就会非常有用：

```java
public interface ReadOnlyRepository<TE, T> {
    boolean contains(T id);
    Entity get(T id);
    Collection<TE> getAll();
}
```

Spring 框架利用 `@Repository` 注解来定义实现仓库的 Bean。在 `RestaurantRepository` 的情况下，你可以看到使用 Map 代替实际的数据库实现。这会将所有实体保存在内存中。因此，当我们启动服务时，会在内存中找到两个餐厅。我们使用 JPA 进行数据库持久化。这是生产级实现的通用做法：

```java
@Repository("restaurantRepository")
public class InMemoryRestaurantRepository implements RestaurantRepository<Restaurant, String> {
    private Map<String, Restaurant> entities;

    public InMemoryRestaurantRepository() {
        entities = new HashMap<>();
        Restaurant r1 = new Restaurant("Big-O Restaurant", "1", null);
        entities.put("1", r1);
        Restaurant r2 = new Restaurant("O Restaurant", "2", null);
        entities.put("2", r2);
    }

    @Override
    public boolean containsName(String name) {
        try {
            return this.findBy(name).size() > 0;
        } catch (Exception ex) {
            // Exception Handler
        }
        return false;
    }

    @Override
    public void add(Restaurant entity) {
        entities.put(entity.getId(), entity);
    }

    @Override
    public void remove(String id) {
        if (entities.containsKey(id)) {
            entities.remove(id);
        }
    }

    @Override
    public void update(Restaurant entity) {
        entities.put(entity.getId(), entity);
    }
}
```

## Restaurant 实体类方法

```java
public void setID(T id) {
    this.id = id;
}
```

```java
public boolean isModified() {
    return isModified;
}
```

```java
public void setModified(boolean isModified) {
    this.isModified = isModified;
}
```

```java
public String getName() {
    return name;
}
```

```java
public void setName(String name) {
    this.name = name;
}
```

Restaurant 服务的实现已经完成。现在，我们将开发 Eureka 模块（服务）。

## 注册与发现服务（Eureka 服务）

我们需要一个让所有微服务都能注册并可以被引用的地方——一个服务发现与注册应用程序。Spring Cloud 提供了最先进的服务注册与发现应用 Netflix Eureka。我们将它用于我们的示例项目 OTRS。



一旦你按照本节的描述准备好了 Eureka 服务，它将对所有传入的请求可用并将其列在 Eureka 服务上。Eureka 服务会注册/列出所有由 Eureka 客户端配置的微服务。一旦你启动服务，它会向你在 `application.yml` 中配置的 Eureka 服务发送心跳，一旦建立连接，Eureka 服务就会注册该服务。

它还允许通过连接其他微服务的统一方式来实现微服务的发现。你不需要任何 IP、主机名或端口来查找服务，只需要为其提供服务 ID 即可。服务 ID 配置在各自微服务的 `application.yml` 中。

# 实现微服务

在以下三个步骤中，我们可以创建一个 Eureka 服务（服务注册与发现服务）：

1.  **Maven 依赖**：它需要一个 Spring Cloud 依赖如下所示，以及在 `pom.xml` 中一个带有 `@EnableEurekaServer` 注解的启动类：

    ```xml
    <dependency>
        <groupId>org.springframework.cloud</groupId>
        <artifactId>spring-cloud-starter-config</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.cloud</groupId>
        <artifactId>spring-cloud-netflix-eureka-server</artifactId>
    </dependency>
    ```

2.  **启动类**：启动类 `App` 只需使用 `@EnableEurekaServer` 类注解即可无缝运行 Eureka 服务：

    ```java
    package com.packpub.mmj.eureka.service;

    import org.springframework.boot.SpringApplication;
    import org.springframework.boot.autoconfigure.SpringBootApplication;
    import org.springframework.cloud.netflix.eureka.server.EnableEurekaServer;

    @SpringBootApplication
    @EnableEurekaServer
    public class App {

        public static void main(String[] args) {
            SpringApplication.run(App.class, args);
        }
    }
    ```

    在 `pom.xml` 项目的 `<properties>` 标签下使用 `<start-class>com.packpub.mmj.eureka.service.App</start-class>`。

    ![](img/f551c3d57000fcdbbc1268267d5af69e_118_0.png)

3.  **Spring 配置**：Eureka 服务还需要用于 Eureka 服务器配置的 Spring 配置（`src/main/resources/application.yml`）：

    ```yaml
    server:
      port: 8761 # HTTP端口

    eureka:
      instance:
        hostname: localhost
      client:
        registerWithEureka: false
        fetchRegistry: false
        serviceUrl:
          defaultZone: ${vacap.services.${PREFIX}}eureka.credentials.uri:http://user:password0@localhost:8761/eureka/
      server:
        waitTimeInMsWhenSyncEmpty: 0
        enableSelfPreservation: false
    ```

## Eureka 客户端

与 Eureka 服务器类似，每个 OTRS 服务也应该包含 Eureka 客户端配置，以便在 Eureka 服务器和客户端之间建立连接。没有它，将无法发现服务。你的服务可以使用以下 Spring 配置来配置 Eureka 客户端。在 Restaurant、Booking 等服务的 `restaurant-service/src/main/resources/application.yml` 中添加以下配置：

```yaml
eureka:
  client:
    serviceUrl:
      defaultZone: http://localhost:8761/eureka/
```

## 执行

要查看代码如何工作，我们需要先构建后执行。以下是一些示例：

```
Eureka 服务注册/列出所有由 Eureka 客户端配置的微服务。一旦你启动服务，它会向你在 application.yml 中配置的 Eureka 服务发送心跳，一旦建立连接，Eureka 服务就会注册该服务。
```

现在，执行这些服务，只需使用以下命令（在项目目录下）：

```
Eureka 服务注册/列出所有由 Eureka 客户端配置的微服务。一旦你启动服务，它会向你在 application.yml 中配置的 Eureka 服务发送心跳，一旦建立连接，Eureka 服务就会注册该服务。
```

要启用测试，在 `pom.xml` 中添加以下：

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
</dependency>
```

要测试服务，使用以下注解：

```java
@RunWith(JUnit4.class)
@SpringBootTest(classes = App.class)
public abstract class AbstractRestControllerTests {
    protected static final String RESTAURANT = "1";
    protected static final String RESTAURANT_NAME = "Big-O";

    @Autowired
    protected RestaurantController restaurantController;

    @Test
    public void validById() {
        // validById 的实现细节
        ResponseEntity<Restaurant> restaurant = restaurantController.findById(RESTAURANT);
        Assert.assertEquals(HttpStatus.OK, restaurant.getStatusCode());
        Assert.assertTrue(restaurant.hasBody());
        Assert.assertNotNull(restaurant.getBody());
        Assert.assertEquals(RESTAURANT, restaurant.getBody().getId());
        Assert.assertEquals(RESTAURANT_NAME, restaurant.getBody().getName());
    }

    @Test
    public void validByName() {
        // validByName 的实现细节
        ResponseEntity<Collection<Restaurant>> requests = restaurantController.findByIdName(RESTAURANT_NAME);
        Assert.assertEquals(HttpStatus.OK, requests.getStatusCode());
        Assert.assertTrue(requests.hasBody());
        Assert.assertNotNull(requests.getBody());
        Restaurant restaurant = (Restaurant) requests.getBody().toArray()[0];
        Assert.assertEquals(RESTAURANT, restaurant.getId());
        Assert.assertEquals(RESTAURANT_NAME, restaurant.getName());
    }

    @Test
    public void validAdd() {
        // validAdd 的实现细节
        RestaurantVO restaurant = new RestaurantVO();
        restaurant.setId("999");
        restaurant.setName("Test Restaurant");

        ResponseEntity<Restaurant> response = restaurantController.add(restaurant);
        Assert.assertEquals(HttpStatus.CREATED, response.getStatusCode());
    }
}
```

（注：OCR 文本包含大量的重复和片段；上述重构侧重于提供的逻辑流。）

- 最后，继承之前创建的抽象类的 `RestaurantControllerTests` 类也创建了 Restaurant Service 和 RestaurantRepository 实现：

```java
public class RestaurantControllerTests extends AbstractRestControllerTests {

    protected static final Restaurant restaurantStaticInstance =
        new Restaurant(RESTAURANT, RESTAURANT_NAME, null);

    protected static class TestRestaurantRepository implements RestaurantRepository<Restaurant, String> {

        private Map<String, Restaurant> entities;

        public TestRestaurantRepository() {
            entities = new HashMap<>();
            Restaurant restaurant = new Restaurant("Big-O Restaurant", "1", null);
            entities.put("1", restaurant);
            restaurant = new Restaurant("O Restaurant", "2", null);
            entities.put("2", restaurant);
        }

        @Override
        public boolean containsName(String name) {
            try {
                return this.findByIdName(name).size() > 0;
            } catch (Exception ex) {
                // 异常处理器
            }
            return false;
        }

        @Override
        public void add(Restaurant entity) {
            entities.put(entity.getId(), entity);
        }

        @Override
        public void remove(String id) {
            if (entities.containsKey(id)) {
                entities.remove(id);
            }
        }

        @Override
        public void update(Restaurant entity) {
            if (entities.containsKey(entity.getId())) {
                entities.put(entity.getId(), entity);
            }
        }

        @Override
        public Collection<Restaurant> findByName(String name) throws Exception {
            Collection<Restaurant> restaurants = new ArrayList();
            int noOfChars = name.length();
            entities.forEach((k, v) -> {
                if (v.getName().toLowerCase().contains(name.subSequence(0, noOfChars))) {
                    restaurants.add(v);
                }
            });
            return restaurants;
        }

        @Override
        public boolean contains(String id) {
            throw new UnsupportedOperationException("Not supported yet");
        }

        @Override
        public Restaurant get(String id) {
            return entities.get(id);
        }

        @Override
        public Collection<Restaurant> getAll() {
            return entities.values();
        }
    }
}
```

```java
@Before
public void setup() {
    restaurantController = new RestaurantController(restaurantService);
}
```

## 参考文献

- Bakhti Mehta 著的《RESTful Java Patterns and Best Practices》，Packt Publishing：https://www.packt.com/application-development/restful-java-patterns-and-best-practices
- Spring Cloud: http://cloud.spring.io/
- Netflix Eureka: https://github.com/netflix/eureka

## 总结

在本章中，我们学习了如何在微服务中使用领域驱动设计模型。在运行演示应用程序后，我们可以看到每个微服务是如何独立开发、部署和测试的。你可以非常方便地使用 Spring Cloud 创建微服务。我们还探索了如何结合 Spring Cloud 使用 Eureka 注册表和发现组件。



# 部署与测试

在本章中，我们将接续第4章“实现微服务”的内容继续。我们将为我们的在线订桌系统（OTRS）应用程序添加更多服务，该程序仅依赖于三个功能性服务（餐厅、用户和预订服务）以及 Eureka（服务发现与注册），以创建一个功能完整的微服务栈。该技术栈将包含网关（`Zuul`）、负载均衡（带有 `Zuul` 和 `Eureka` 的 `Ribbon`）以及监控（`Hystrix`、`Turbine` 和 `Hystrix` 仪表板）。你想要组合 API 并查看微服务之间是如何通信的。本章还将解释如何使用 `Docker` 将微服务容器化，以及如何使用 `docker-compose` 运行多个容器。在此基础上，我们还将添加集成测试。

在本章中，我们将涵盖以下主题：

- 使用 Netflix OSS 的微服务架构概述
- 边缘服务器
- 负载均衡微服务
- 断路器与监控
- 使用容器部署微服务
- 使用 Docker 容器进行微服务集成

## 良好微服务的必要服务

为了实现基于微服务的设计，应该具备一些模式/服务。此列表包括：

- 服务发现与注册
- 边缘或代理服务器
- 负载均衡
- 断路器
- 监控

将在本章中实现这些服务以完成我们的 OTRS 系统。以下是简要概述。我们稍后详细讨论这些模式/服务。

### 服务发现与注册

`Netflix Eureka` 服务器用于服务发现和注册。我们在上一章中创建了 `Eureka` 服务器。它不仅允许你注册和发现服务，还通过 `Ribbon` 提供负载均衡。

### 边缘服务器

边缘服务器提供了一个单一访问点，允许外部世界与你的系统交互。你所有的 API 和前端都只能通过此服务器访问。因此，它们也被称为网关或代理服务器。这些服务器用于将请求路由到不同的微服务或前端应用程序。我们将使用 `Netflix Zuul` 服务器作为边缘中的边缘服务器。

### 负载均衡

`Netflix Ribbon` 用于负载均衡。

### 断路器

断路器应该防止整个系统崩溃。

### 监控

`Hystrix` 仪表板用于监控。

## 使用 Netflix OSS 的微服务架构概述

`Netflix OSS` 为微服务架构提供了多种工具，包括 `Zuul`、`Eureka`、`Ribbon`、`Hystrix` 和 `Turbine`。

## 部署与测试

通常，建议为所有请求准备单个边缘服务器。然而，一些公司为每个客户端使用单个边缘服务器以扩展规模。例如，`Netflix` 为每种设备类型使用专用的边缘服务器。

在下一章节中，也将使用边缘服务器，当时我们将配置并实现微服务安全。

在 `Spring Cloud` 中配置和使用边缘服务器非常简单。你需要执行以下步骤：

1. 在 `pom.xml` 文件中定义 `Zuul` 依赖：

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-zuul</artifactId>
</dependency>
```

2. 在你的应用程序类中使用 `@EnableZuulProxy` 注解。它在内部也使用了 `@EnableDiscoveryClient` 注解；因此，它也会自动注册到 `Eureka` 服务器。你可以在名为“客户端负载均衡”的图中找到 `Zuul` 服务器。

3. 在更新 `application.yml` 文件中的 `Zuul` 配置，如下所示：

   - `zuul.ignoredServices`：此项将跳过服务的自动添加。我们可以在这里定义服务模式。`**` 表示我们正在忽略所有服务。在以下示例中，除了 `restaurant-service` 之外，所有服务均被忽略。
   - `Zuul.routes`：此包含定义 URI 模式的 `path` 属性。在这里，使用 `serviceId` 属性将 `/restaurantapi` 映射到 `restaurant-service`。`ServiceId` 属性代表 `Eureka` 服务器中的服务。如果没有使用 `Eureka` 服务器，我们可以使用 `URL`。我们还使用了 `stripPrefix` 属性来剥离前缀 (`/restaurantapi`)，生成的 `/restaurantapi/v1/restaurantapi/1` 在调用服务时会调用 `/v1/restaurantapi/1`：

```yaml
application.yml
info:
  component: Zuul Server
  # Spring 属性
spring:
  application:
    name: zuul-server # 服务在此名称下注册

endpoints:
  restart:
    enabled: true
  shutdown:
    enabled: true
eureka:
  client:
    serviceUrl:
      defaultZone: http://localhost:8761/eureka/
zuul:
  ignoredServices: '**'
  routes:
    restaurant-service:
      path: /restaurantapi/**
      serviceId: restaurant-service
      stripPrefix: true
```

```properties
${spring.application.name}:${vcap.application.instance_id:${spring.application.instance_id:${random.value}}}
```

## 让我们来看一个运行中的边缘服务器

首先，我们将调用部署在端口 `3402` 上的 `Restaurant` 服务，如下：

```
http://localhost:3402/v1/restaurants?name=
```

![](img/f551c3d57000fcdbbc1268267d5af69e_132_0.png)

然后，我们将使用部署在端口 `8765` 上的边缘服务器调用同一个服务。你可以看到使用 `/restaurantapi` 前缀来调用 `/v1/restaurants?name=o`，它带给了我们相同的结果。

## 负载均衡微服务

- 向 `Eureka` 查询服务器是否启动的请求。使用 `DiscoveryEnabledNIWSSList` 接口来代替 `Ribbon` 的 `IPing`。

`Spring Cloud` 中有不同的可用的客户端，例如 `RestTemplate` 或 `FeignClient`。这些客户端允许微服务相互进行通信。当使用 `Eureka` 服务器时，客户端使用主机名和端口中的实例 ID 来对服务进行 HTTP 调用。客户端将服务 ID 传递给 `Ribbon`，`Ribbon` 使用负载均衡器从 `Eureka` 服务器中选择实例。

如果 `Eureka` 中有多个可用服务实例，如下截图所示，`Ribbon` 会根据负载均衡算法为请求仅选择一个：

### 当前注册到 Eureka 的实例

| 应用程序 (Application) | AMIs | 区域 (Zones) | 状态 (Status) |
| --- | --- | --- | --- |
| RESTAURANT-SERVICE | n/a (2) | | UP (2) - SOUSHARM-IN:restaurant-service-5b043f31fd44c9ff66d5c5fb1bd4c38d7, SOUSHARM-IN:restaurant-service:707b06d8d0d2e3516f3d2e3c8658d1 |
| ZUUL-SERVER | n/a (1) | UP (1) - SOUSHARM-IN:zuul-server:9094ea5ae179efe903061bd27e2e167 |

我们使用 `DiscoveryClient` 来查找 `Eureka` 服务器中所有可用的服务实例，如下代码所示。`DiscoveryClientSample` 类的 `getLocalServiceInstance()` 方法返回 `Eureka` 服务器中所有本地服务实例。

这是 `DiscoveryClient` 示例：

```java
@Component
class DiscoveryClientSample implements CommandLineRunner {

    @Autowired
    private DiscoveryClient discoveryClient;

    @Override
    public void run(String... args) throws Exception {
        // 打印 Discovery Client 描述
        System.out.println(discoveryClient.description());
        // 获取 restaurant-service 实例并放入 info
        discoveryClient.getInstances("restaurant-service").forEach((ServiceInstance serviceInstance) -> {
            System.out.println(new StringBuilder("Instance --\n").append(serviceInstance.getId())
                .append("\nServer:").append(serviceInstance.getHost()).append(":").append(serviceInstance.getPort())
                .append("\nURI:").append(serviceInstance.getUri()).append("\n\n"));
        });
    }
}
```

执行时，这段代码会打印以下信息。它显示了两个 `Restaurant` 服务的实例：

- Spring Cloud Eureka Discovery Client

Instance: RESTAURANT-SERVICE

Server: SOUSHARM-IN:3402

URI: http://SOUSHARM-IN:3402

使用 `/restaurantapi` 前缀来调用 `/v1/restaurants?name=o`，它带给了我们相同的结果。

### 对于 restaurant-service 部署在端口 3402 上的 Restaurant 实例

- Spring Cloud Eureka Discovery Client

Instance: RESTAURANT-SERVICE

Server: SOUSHARM-IN:3402

URI: http://SOUSHARM-IN:3402

使用 `/restaurantapi` 前缀来调用 `/v1/restaurants?name=o`，它带给了我们相同的结果。

### 对于 restaurant-service 部署在端口 3402 上的 Restaurant 实例

- Spring Cloud Eureka Discovery Client

Instance: RESTAURANT-SERVICE

Server: SOUSHARM-IN:3402

URI: http://SOUSHARM-IN:3402

这些客户端显示了如何使用 `/v1/restaurant` 参数。

这是 `RestTemplate` 示例：

```java
@Component
class RestTemplateExample implements CommandLineRunner {
    @Autowired
    private RestTemplate restTemplate;

    @Override
    public void run(String... args) throws Exception {
        System.out.println("\n\n start RestTemplate...");
        ResponseEntity<Collection<Restaurant>> exchange =
            this.restTemplate.exchange(
                "http://restaurant-service/v1/restaurants?name=",
                HttpMethod.GET,
                null,
                new ParameterizedTypeReference<Collection<Restaurant>>() {}
            );
        exchange.getBody().forEach((restaurant) -> {
            System.out.println("\n\n " + restaurant.getId() + " - " + restaurant.getName());
        });
    }
}
```

这是 `FeignClient` 示例：

```java
@FeignClient("restaurant-service")
interface RestaurantClient {
    @GetMapping("/v1/restaurants")
    List<Restaurant> getRestaurants(@RequestParam("name") String name);
}
```

所有之前的示例将输出：

- 1 Restaurant
- 2 Restaurant

## 断路器与监控

通常情况下，断路器是一种用于停止电路中电流流的自动设备。相同的概念被用于微服务开发，被称为断路器。它跟踪如 `Eureka` 服务器、API 服务 `restaurant-service` 等外部服务的可用性，并防止服务消费者在不可用的服务上执行任何操作。

我们将使用 `Netflix Hystrix` 作为断路器。当发生故障（例如通信错误或超时）时，它会调用消费者中的回退方法。它嵌入在消费者中执行。在下一节中，你将找到实现此功能的代码。

`Hystrix` 在反复失败时打开断路，直到服务再次可用。当对特定服务的调用达到特定阈值（默认为 5 秒内失败 20 次）时，断路打开且不再进行调用。你可能想，如果 `Hystrix` 打开了断路，它如何知道服务是可用的？它异常允许某些请求调用服务。

### 使用 Hystrix 回退方法

实现回退方法有五个步骤。为了这个目的，我们将像创建其他服务一样创建一个另一个服务 `api-service`。`api-service` 将消费 `restaurant-service` 等服务，并在边缘服务器中配置以向外部暴露 REST API。这五个步骤如下：

1. **启用断路器**：消费其他服务的微服务主类应该被 `@EnableCircuitBreaker` 注解。因此，我们将注解：

```java
@SpringBootApplication
@EnableCircuitBreaker
@ComponentScan("com.packpub.mmj.user.service")
package com.packpub.mmj.common;
public class ApiException {
}
```

2. **配置回退方法**：使用 `@HystrixCommand` 注解配置 `fallbackMethod`。我们将注解控制器以配置回退方法。这是该文件：

```java
@HystrixCommand(fallbackMethod = "defaultRestaurant")
@RequestMapping("/restaurants/{restaurant-id}")
public ResponseEntity<Restaurant> getRestaurant(
    @PathVariable("restaurant-id") int restaurantId) {
    MDC.put("restaurant-id", restaurantId);
    String url = "http://restaurant-service/v1/restaurants/" + restaurantId;
    LOG.debug("GetRestaurant from URL: {}", url);

    ResponseEntity<Restaurant> result =
        restTemplate.getForEntity(url, Restaurant.class);
    LOG.info("GetRestaurant http-status: {}", result.getStatusCode());
    LOG.debug("GetRestaurant body: {}", result.getBody());

    return serviceHelper.createOkResponse(result.getBody());
}
```

3. **回退方法**：一种处理失败并执行安全步骤的方法。我们刚刚添加了一个示例；可以根据我们想要处理失败的方式对其进行修改：

```java
public ResponseEntity<Restaurant> defaultRestaurant(
    @PathVariable int restaurantId) {
    return serviceHelper.createResponse(null, HttpStatus.BAD_GATEWAY);
}
```

4. **Maven 依赖**：对于 API 服务或我们希望实现 API 调用容错的项目，我们需要在 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-hystrix</artifactId>
</dependency>
```

5. **在 application.yml 中配置 Hystrix**：我们将在 `application.yml` 文件中添加以下 `Hystrix` 属性：

```yaml
hystrix:
  threadpool:
    default:
      # 使用线程池时的最大并发请求数 (默认: 10)
      coreSize: 100
      # LinkedBlockingQueue 的最大大小 - -1 表示使用 SynchronousQueue
      maxQueueSize: -1
      # 队列拒绝阈值 (默认: 5)
      queueSizeRejectionThreshold: 5
```



```yaml
queueSizeRejectionThreshold: 5
command:
  default:
    circuitBreaker:
      sleepWindowInMilliseconds: 30000
      requestVolumeThreshold: 2
    execution:
      isolation:
        strategy: SEMAPHORE, 不使用线程池但使用线程超时处理
停止工作
  strategy: THREAD
  thread:
    timeoutInMilliseconds: 6000
```

这些步骤应该足够对服务调用进行容错处理，并向服务消费者返回更合适的响应。

## 监控

Hystrix 提供了一个带有 Web 界面的仪表板，可以提供断路器的精美图表。

![](img/f551c3d57000fcdbbc1268267d5af69e_139_0.png)

# 部署与测试

Netflix Turbine 是一个 Web 应用，它可以连接到集群中的 Hystrix 应用程序实例并聚合信息，这种聚合是实时的（每 0.5 秒更新一次）。Turbine 使用一种称为 Turbine 流的流提供信息。

如果你将 Hystrix 与 Netflix Turbine 结合使用，就可以在 Hystrix 仪表板上从 Eureka 服务器获取所有信息。这让你能够获得所有断路器信息的全局视图。

要在 Hystrix 中使用 Turbine，只需在前面的截图中显示的第一个文本框中输入 Turbine URL `http://localhost:8989/turbine.stream`（端口 8989 是在 `application.yml` 中为 Turbine 服务器配置的），并点击 **Monitor Stream**（监控流）。

Netflix Turbine 和 Turbine 使用 RabbitMQ，这是一个开源消息队列软件。RabbitMQ 基于**高级消息队列协议 (AMQP)** 工作。这是一个定义队列并使用连接的应用程序交换消息的软件。消息可以包含任何类型的信息。消息可以存储在 RabbitMQ 队列中，直到接收程序连接并消费消息（从队列中取出）。

Hystrix 使用 RabbitMQ 将指标数据馈送给 Turbine。

> 在我们配置 Hystrix 和 Turbine 之前，请在您的平台上安装 RabbitMQ 应用程序。Hystrix 和 Turbine 之间使用 RabbitMQ 进行通信。

## 设置 Hystrix 仪表板

我们将按照创建其他服务的方式，在 Hystrix 仪表板中创建另一个项目。在这个新项目中，我们将为 Hystrix 服务器添加新的 Maven 依赖 `dashboard-server`。在 Spring Cloud 中配置和使用 Hystrix 仪表板非常简单。

# 部署与测试

当您运行 Hystrix 仪表板应用程序时，它看起来将像之前显示的默认 Hystrix 截图。您只需要遵循以下步骤：

1. 在 `pom.xml` 文件中定义 Hystrix 仪表板依赖：

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-hystrix-dashboard</artifactId>
</dependency>
```

2. 主 Java 类中的 `@EnableHystrixDashboard` 注解会为您完成您所需的所有工作。我们还使用 `@Controller` 将请求从根 URI 转发到 Hystrix 仪表板 UI URI (`/hystrix`)。

3. 在 `application.yml` 中更新仪表板应用配置，如下：

```yaml
## Hystrix Dashboard 属性
spring:
  application:
    name: dashboard-server
```

```yaml
endpoints:
  restart:
    enabled: true
```

# 部署与测试

## 第 5 章

```yaml
shutdown:
  enabled: true

server:
  port: 7979

eureka:
  instance:
    leaseRenewalIntervalInSeconds: 3
    metadataMap:
      instanceId: ${vcap.application.instance_id:${spring.application.name}:${spring.application.instance_id:${random.value}}}

client:
  # 默认值来自
  org.springframework.cloud.netflix.eureka.EurekaClientConfigBean.registryFetchIntervalSeconds: 5
  instanceInfoReplicationIntervalSeconds: 5
  initialInstanceReplicationIntervalSeconds: 5
  serviceUrl: http://localhost:8761/eureka/
  fetchRegistry: false
```

```yaml
logging:
  level:
    ROOT: WARN
    org.springframework.web: WARN
```

# 创建 Turbine 服务

Turbine 将所有的 `/hystrix.stream` 端点聚合到一个合并的 `/turbine.stream` 以供 Hystrix 仪表板使用，这更有帮助，因为允许您在单个仪表板上查看系统的整体健康状况，而不是使用 `/hystrix.stream` 监控单个服务。我们将像创建其他服务一样在 IDE 中创建另一个服务项目。然后，我们将在 `pom.xml` 中为 Turbine 添加 Maven 依赖。

现在，我们将使用以下步骤配置 Turbine 服务器：

1. 在 `pom.xml` 中定义 Turbine 依赖：

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-turbine</artifactId>
</dependency>
```

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-rabbit</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

2. 在您的应用类中使用 `@EnableTurbineStream` 注解，如下所示。我们还定义了一个返回 RabbitMQ `ConnectionFactory` 的 bean：

```java
@SpringBootApplication
@EnableTurbineStream
public class TurbineApp {

    private static final Logger LOG =
        LoggerFactory.getLogger(TurbineApp.class);

    @Value("${rabbitmq.host:localhost}")
    String rabbitMQHost;

    @Bean
    public ConnectionFactory connectionFactory() {
        LOG.info("为 host {} 创建 RabbitMQ ConnectionFactory", rabbitMQHost);
        CachingConnectionFactory cachingFactory = 
            new CachingConnectionFactory(rabbitMQHost);
        return cachingFactory;
    }

    public static void main(String[] args) {
        SpringApplication.run(TurbineApp.class, args);
    }
}
```

3. 在 `application.yml` 中更新 Turbine 配置，如下：

```yaml
application.yml
spring:
  application:
    name: turbine-server

server:
  port: 8989

management:
  port: 8990

turbine:
  aggregator:
    clusterConfig: USER-SERVICE, RESTAURANT-SERVICE
    appConfig: user-service, restaurant-service

eureka:
  instance:
    leaseRenewalIntervalSeconds: 10
    metadataMap:
      instanceId: ${vcap.application.instance_id:${spring.application.name}:${spring.application.instance_id:${random.value}}}
  client:
    serviceUrl:
      defaultZone: ${vcap.services.${PREFIX}.eureka.credentials.uri:http://user:passwo@localhost:8761}/eureka/
    fetchRegistry: true

logging:
  level:
    root: INFO
    com.netflix.discovery: 'OFF'
    org.springframework.framework.integration: DEBUG
```

## 构建并运行 OTRS 应用

使用以下文件 `..\Chapter5 pom.xml` 通过 `mvn clean install` 编译所有项目。

输出结果如下：

```
6392_chapter                                     SUCCESS [3.03s]
online-table-reservation:common                SUCCESS [5.899s]
online-table-reservation:zuul-server               SUCCESS [4.517s]
online-table-reservation:restaurant-service      SUCCESS [49.250s]
online-table-reservation:eureka-server            SUCCESS [2.850s]
online-table-reservation:dashboard-server         SUCCESS [2.893s]
online-table-reservation:turbine-server          SUCCESS [3.670s]
online-table-reservation:user-service            SUCCESS [47.983s]
online-table-reservation:api-service               SUCCESS [3.065s]
online-table-reservation:booking-service          SUCCESS [26.496s]
```

然后，在命令提示符中，进入 `<path to source>/6392_chapter5` 并运行以下命令：

```
java -jar eureka-server/target/eureka-server.jar
java -jar turbine-server/target/turbine-server.jar
java -jar dashboard-server/target/dashboard-server.jar
java -jar restaurant-service/target/restaurant-service.jar
java -jar user-service/target/user-service.jar
java -jar booking-service/target/booking-service.jar
java -jar api-service/target/api-service.jar
```

注意：在启动 Zuul 之前，请确保 Eureka 仪表板中的所有服务均已启动：`http://localhost:8761/`

```
java -jar zuul-server/target/zuul-server.jar
```

再次检查 Eureka 仪表板，确保所有应用程序均已启动。进行测试。

## 使用容器部署微服务

在读完第 1 章“解决方案方法”后，你可能已经了解了 Docker 的要点。

# 部署与测试

## 第 5 章

Docker 容器提供了一个轻量级的运行环境，它由虚拟机的核心功能和操作系统的隔离服务组成，被称为 Docker 镜像。Docker 使微服务的打包和执行变得更加简单和顺畅。每个操作系统可以拥有多个 Docker，而每个 Docker 则可以运行单个应用程序。

## 安装与配置

如果你没有使用 Linux 操作系统，则 Docker 需要一个虚拟化服务器。你可以安装 VirtualBox 或类似的工具作为 Docker Toolbox 来让它运行。Docker 安装页面提供了有关它的更多信息，并教你如何操作。因此，请参考 Docker 网站上提供的 Docker 安装指南。

你可以根据你的平台，按照以下说明安装 Docker：`https://docs.docker.com/engine/installation/`。

DockerToolbox-1.9.1 是编写时提供的最新版本。我们使用的就是这个版本。

## 4 GB 内存的 Docker machine

默认机器创建带有 2 GB 内存。我们将重新创建一个具有 4 GB 内存的 Docker machine：

```
docker-machine rm default
docker-machine create -d virtualbox --virtualbox-memory 4096 default
```

## 使用 Maven 构建 Docker 镜像

有各种 Maven 插件可以使用：

- `https://github.com/rhuss/docker-maven-plugin`
- `https://github.com/alexec/docker-maven-plugin`
- `https://github.com/spotify/docker-maven-plugin`

你可以根据选择使用其中任何一个。我发现 `@rhuss` 提供的 Docker Maven 插件最适合我们。它定期更新，并且与其他插件相比，具有许多额外功能。

# 部署与测试

在讨论 `docker-maven-plugin` 的配置之前，我们需要在 `application.yml` 中引入 Docker Spring profile。这将使我们在为各种平台构建服务时工作变得更加轻松。我们需要配置以下四个属性：

- 我们将使用标识为 `Docker` 的 Spring profile。
- 嵌入 Tomcat 之间不会出现端口冲突，因为服务将在它们各自的容器中执行。我们现在可以使用端口 `8080`。
- 我们倾向于使用 IP 地址在 Eureka 中注册我们的服务。因此，Eureka 实例属性 `preferIPAddress` 将设置为 `true`。
- 最后，我们将在 `serviceUrl:defaultZone` 中使用 Eureka 服务器主机名。

要在你的项目中添加 Spring profile，请在 `application.yml` 的现有内容之后添加以下行：

```yaml
---
# 用于在 Docker 容器中部署
spring:
  profiles: docker

server:
  port: 8080

eureka:
  instance:
    preferIPAddress: true
  client:
    serviceUrl: defaultZone: http://eureka:8761/eureka/
```

运行 `mvn -P docker clean package` 命令将生成带有 Tomcat 8080 端口的服务 JAR 包，该包将使用主机名 `eureka` 注册到 Eureka 服务器。

现在，让我们配置 `docker-maven-plugin` 来构建我们的餐厅微服务的镜像。该插件必须先创建一个 Dockerfile。Dockerfile 在两个地方配置——在 `pom.xml` 和 `docker-assembly.xml` 文件中。我们将在 `pom.xml` 中使用以下插件配置：

```xml
<properties>
<!-- Docker hub 留空；对于本地 Docker Registry 使用 "localhost:5000" -->
<docker.registry.name>localhost:5000</docker.registry.name>
```

# 部署与测试



# 构建并运行 OTRS 应用

使用以下文件 `..\Chapter5 pom.xml` 通过 `mvn clean install` 编译所有项目。

输出结果如下：

```
6392_chapter                                     SUCCESS [3.03s]
online-table-reservation:common                SUCCESS [5.899s]
online-table-reservation:zuul-server               SUCCESS [4.517s]
online-table-reservation:restaurant-service      SUCCESS [49.250s]
online-table-reservation:eureka-server            SUCCESS [2.850s]
online-table-reservation:dashboard-server         SUCCESS [2.893s]
online-table-reservation:turbine-server          SUCCESS [3.670s]
online-table-reservation:user-service            SUCCESS [47.983s]
online-table-reservation:api-service               SUCCESS [3.065s]
online-table-reservation:booking-service          SUCCESS [26.496s]
```

然后，在命令提示符中，进入 `<path to source>/6392_chapter5` 并运行以下命令：

```
java -jar eureka-server/target/eureka-server.jar
java -jar turbine-server/target/turbine-server.jar
java -jar dashboard-server/target/dashboard-server.jar
java -jar restaurant-service/target/restaurant-service.jar
java -jar user-service/target/user-service.jar
java -jar booking-service/target/booking-service.jar
java -jar api-service/target/api-service.jar
```

注意：在启动 `Zuul` 之前，请确保 Eureka 仪表板中的所有服务均已启动：`http://localhost:8761/`

```
java -jar zuul-server/target/zuul-server.jar
```

再次检查 Eureka 仪表板，确保所有应用程序均已启动。进行测试。

# 使用容器部署微服务

在读完第 1 章“解决方案方法”后，你可能已经了解了 Docker 的要点。

## 部署与测试

### 第 5 章

Docker 容器提供了一个轻量级的运行环境，它由虚拟机的核心功能和操作系统的隔离服务组成，被称为 Docker 镜像。Docker 使微服务的打包和执行变得更加简单和顺畅。每个操作系统可以拥有多个 Docker，而每个 Docker 则可以运行单个应用程序。

## 安装与配置

如果你没有使用 Linux 操作系统，则 Docker 需要一个虚拟化服务器。你可以安装 `VirtualBox` 或类似的工具作为 Docker Toolbox 来让它运行。Docker 安装页面提供了有关它的更多信息，并教你如何操作。因此，请参考 Docker 网站上提供的 Docker 安装指南。

你可以根据你的平台，按照以下说明安装 Docker：`https://docs.docker.com/engine/installation/`。

`DockerToolbox-1.9.1` 是编写时提供的最新版本。我们使用的就是这个版本。

## 4 GB 内存的 Docker machine

默认机器创建带有 2 GB 内存。我们将重新创建一个具有 4 GB 内存的 Docker machine：

```
docker-machine rm default
docker-machine create -d virtualbox --virtualbox-memory 4096 default
```

## 使用 Maven 构建 Docker 镜像

有各种 Maven 插件可以使用：

- `https://github.com/rhuss/docker-maven-plugin`
- `https://github.com/alexec/docker-maven-plugin`
- `https://github.com/spotify/docker-maven-plugin`

你可以根据选择使用其中任何一个。我发现 `@rhuss` 提供的 Docker Maven 插件最适合我们。它定期更新，并且与其他插件相比，具有许多额外功能。

## 部署与测试

在讨论 `docker-maven-plugin` 的配置之前，我们需要在 `application.yml` 中引入 Docker Spring profile。这将使我们在为各种平台构建服务时工作变得更加轻松。我们需要配置以下四个属性：

- 我们将使用标识为 `Docker` 的 Spring profile。
- 嵌入 Tomcat 之间不会出现端口冲突，因为服务将在它们各自的容器中执行。我们现在可以使用端口 `8080`。
- 我们倾向于使用 IP 地址在 Eureka 中注册我们的服务。因此，Eureka 实例属性 `preferIPAddress` 将设置为 `true`。
- 最后，我们将在 `serviceUrl:defaultZone` 中使用 Eureka 服务器主机名。

要在你的项目中添加 Spring profile，请在 `application.yml` 的现有内容之后添加以下行：

```yaml
---
# 用于在 Docker 容器中部署
spring:
  profiles: docker

server:
  port: 8080

eureka:
  instance:
    preferIPAddress: true
  client:
    serviceUrl:
      defaultZone: http://eureka:8761/eureka/
```

运行 `mvn -P docker clean package` 命令将生成带有 Tomcat 8080 端口的服务 JAR 包，该包将使用主机名 `eureka` 注册到 Eureka 服务器。

现在，让我们配置 `docker-maven-plugin` 来构建我们的餐厅微服务的镜像。该插件必须先创建一个 Dockerfile。Dockerfile 在两个地方配置——在 `pom.xml` 和 `docker-assembly.xml` 文件中。我们将在 `pom.xml` 中使用以下插件配置：

```xml
<properties>
  <!-- Docker hub 留空；对于本地 Docker Registry 使用 "localhost:5000" -->
  <docker.registry.name>localhost:5000</docker.registry.name>
</properties>
```

```xml
<plugin>
  <groupId>org.github.rhuss</groupId>
  <artifactId>docker-maven-plugin</artifactId>
  <version>1.1.2</version>
  <configuration>
    <image>
      <!-- 待补充配置 -->
    </image>
  </configuration>
</plugin>
```

```xml
<run>
  <namingStrategy>alias</namingStrategy>
  <ports>
    <port>${docker.port}:8080</port>
  </ports>
  <wait>
    <url>http://${docker.host.address}:8080/v1/restaurants/1</url>
    <time>100000</time>
  </wait>
  <log>
    <prefix>${project.artifactId}</prefix>
    <color>cyan</color>
  </log>
</run>
```

在这里，我们定义了运行 Restaurant 服务容器的参数。我们将 Docker 容器端口 8080 映射到系统主机的端口，这使得我们能够访问服务。同样，我们还将容器的日志目录绑定到了宿主机系统的 `<home>/logs` 目录。

Docker Maven 插件可以通过轮询管理后台的 ping URL 直到收到响应，来检测容器是否已启动。

请注意，如果你在 Windows 或 MacOS 上使用 DockerToolbox 或 bootdocker，Docker 宿主机不是 `localhost`。你可以通过执行 `docker-machine ip default` 来检查 Docker 镜像的 IP。它在启动时也会显示。

Docker 容器已就绪。使用以下 Maven 命令来启动它：

```
mvn docker:start
```

## 使用 Docker 进行集成测试

通过在 `pom.xml` 中将以下执行阶段绑定到 `docker-maven-plugin` 的生命周期阶段，可以启动和停止 Docker 容器：

```xml
<execution>
  <id>start</id>
  <phase>pre-integration-test</phase>
  <goals>
    <goal>build</goal>
    <goal>start</goal>
  </goals>
</execution>
<execution>
  <id>stop</id>
  <phase>post-integration-test</phase>
  <goals>
    <goal>stop</goal>
  </goals>
</execution>
```

现在，我们将配置 Failsafe 插件以使用 Docker 执行集成测试。这允许我们执行集成测试用例。我们在 `service.url` 标签中传递服务 URL，以便我们的集成测试可以使用它来执行测试。

我们将使用 `DockerIntegrationTest` 标记来标记我们的 Docker 集成测试。它的定义如下：

```java
package com.packpub.mmj.restaurant.resources.docker;

public interface DockerIT {
  // Docker 集成测试的标记
}
```

查看下面的集成插件代码。你可以看到 `DockerIT` 被配置用于包含集成测试（Failsafe 插件），而在单元测试中被用于排除（Surefire 插件）：

```xml
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-failsafe-plugin</artifactId>
  <configuration>
    <phase>integration-test</phase>
    <groups>com.packpub.mmj.restaurant.docker.DockerIT</groups>
    <systemPropertyVariables>
      <service.url>http://${docker.host.address}:${docker.port}</service.url>
    </systemPropertyVariables>
  </configuration>
  <executions>
    <execution>
      <goals>
        <goal>integration-test</goal>
        <goal>verify</goal>
      </goals>
    </execution>
  </executions>
</plugin>
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-surefire-plugin</artifactId>
  <configuration>
    <excludedGroups>com.packpub.mmj.restaurant.resources.docker.DockerIT</excludedGroups>
  </configuration>
</plugin>
```

一个简单的集成测试如下所示：

```java
@Category(DockerIT.class)
public class RestaurantAppDockerIT {

    @Test
    public void testConnection() throws IOException {
        String baseUrl = System.getProperty("service.url");
        URL serviceUrl = new URL(baseUrl + "v1/restaurants/1/");
        HttpURLConnection connection = (HttpURLConnection) serviceUrl.openConnection();
        int responseCode = connection.getResponseCode();
        assertEquals(200, responseCode);
    }
}
```

你可以使用以下命令通过 Maven 执行集成测试（请在运行集成测试之前，务必从项目目录根节点运行 `mvn clean install`）：

```
mvn integration-test
```

## 将镜像推送到注册表

在 `docker-maven-plugin` 下添加以下标签，以将 Docker 镜像发布到 Docker Hub：



# 响应式微服务

## 总结

在本章中，我们学习了各种微服务管理功能：负载均衡、边缘（网关）服务器、断路器和监控。通过本章的学习，你现在应该已经了解如何实现负载均衡和路由。我们还学习了如何设置和配置边缘服务器。故障转移机制是你在本章中学习的另一个重要部分。使用 Docker 或任何容器都可以使部署变得简单。我们演示了如何使用 Maven 构建并集成了 Docker。

从测试的角度来看，我们对服务的 Docker 镜像进行了集成测试。我们还探索了如何编写诸如 `RestTemplate` 和 Netflix Feign 等客户端。

在下一章中，我们将学习如何从身份验证和授权方面对微服务进行安全防护。我们还将探索微服务安全的其他方面。

## Maven 部署配置示例

### 跳过 JAR 发布

你可以通过 `maven-deploy-plugin` 的以下配置跳过 JAR 的发布：

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-deploy-plugin</artifactId>
    <version>2.7</version>
    <configuration>
        <skip>true</skip>
    </configuration>
</plugin>
```

### 推送 Docker 镜像

在 Docker Hub 中发布 Docker 镜像需要用户名和密码：

```bash
mvn -Ddocker.username=<username> -Ddocker.password=<password> deploy
```

你也可以将 Docker 镜像推送到你自己的注册表。要实现此点，请向你的 `docker-compose.yml` 中添加以下配置：

```yaml
services:
  restaurant:
    image: my-registry.com/restaurant:latest
    ports:
      - "8080:8080"
```

## Maven 执行配置

```xml
<execution>
    <id>push-to-docker-registry</id>
    <phase>deploy</phase>
    <goals>
        <goal>push</goal>
    </goals>
</execution>
```

---

# 第6章 响应式微服务

在本章中，我们将使用 Spring Boot、Spring Stream、Apache Kafka 和 Apache Avro 来实现响应式微服务。我们将利用现有的 Booking 微服务来实现消息生产者，换句话说，就是生成事件。我们还将创建一个新的微服务（Billing）来消费由更新后的 Booking 微服务产生的消息，或者说，消费 Booking 微服务生成的事件。我们还将讨论基于 REST 的微服务与基于事件的微服务之间的权衡。

在本章中，我们将涵盖以下主题：

- 响应式微服务架构概述
- 生成事件
- 消费事件

## 响应式微服务架构概述

到目前为止，我们开发的微服务都是基于 REST 的。我们使用 REST 同时进行内部（微服务之间通信，即一个微服务与同一系统中的另一个微服务通信）和外部（通过公共 API）通信。目前，REST 最适用于公共 API。微服务之间的通信还有其他替代方案吗？实现 REST 进行微服务通信是最佳方法吗？我们将在本节中讨论这些。

你可以构建纯异步的微服务。你可以构建基于事件通信的基于微服务的系统。REST 和基于事件的微服务之间存在权衡。REST 提供同步通信，而响应式微服务是基于异步通信（异步消息传递）。

我们可以使用异步通信进行微服务之间的通信。根据需求和功能，我们可以选择 REST 或异步消息传递。考虑用户下单的示例案例，这为实现响应式微服务的极佳案例。订单下单成功后，库存服务将重新计算可用物品；账户服务将向所有涉及的用户（如客户和供应商）发送消息（短信、电子邮件等）。在这种情况下，多个微服务可能会根据在一个微服务中执行的操作（下单）执行不同的操作（库存、账户、消息传递等）。现在，想一想如果所有这些通信都是同步的会怎样。相反，带有异步消息传递的响应式通信提供了硬件资源的高效利用、非阻塞、低延迟和高吞吐量操作。

我们主要将微服务的实现分为两类——基于 REST 的微服务和基于事件/消息驱动的微服务。响应式微服务是基于事件的。

![响应式微服务架构](img/f551c3d57000fcdbbc1268267d5af69e_158_0.png)

响应式微服务基于[响应式宣言 (Reactive Manifesto)](https://www.reactivemanifesto.org/)。响应式宣言包含了四个原则，我们现在将讨论这些原则。

### 响应 (Responsive)

响应是及时处理请求的特征。它通过延迟衡量。生产者应该及时提供响应，消费者也应该及时接收响应。为请求执行的操作链中的故障不应导致响应延迟或失败。因此，这对于服务的可用性非常重要。

### 弹性 (Resilient)

一个弹性系统是一个健壮的系统。弹性原则与响应原则一致。微服务尽管出现故障也应该提供响应，如果微服务的某个实例宕机，请求应该由同一微服务的另一个节点来处理。弹性的微服务应该被监控以检测故障，并处理所有故障。在上一章中，我们使用了服务发现 `eureka` 进行监控，并使用 `Hystrix` 实现断路器模式。

### 可伸缩 (Elastic)

如果响应式系统对负载做出反应，那么它就是弹性。它可以在黑五或排灯节等销售期间实例化微服务的新实例。在正常日期，它可以减少实例数量。

### 消息驱动 (Message driven)

如果响应式系统无事可做，它就会空闲；它不会浪费使用资源。理想情况下，通信应该是异步且非阻塞的。响应式系统使用消息进行通信。在本章中，我们将使用 Apache Kafka 进行消息传递。

## 实现响应式微服务

理想情况下，响应式编程语言是实现微服务的最佳方式。响应式编程语言提供了异步和非阻塞调用。Java 也可以使用 Kafka 开发微服务。我们已经实现了服务发现和注册服务（Eureka）、具有弹性的代理服务器（Zuul）以及用于断路器（弹性和响应）的 Hystrix。

响应式微服务响应事件执行操作。我们将修改代码以为我们的示例实现生成和消费事件。虽然我们将创建一个事件，但微服务可以有多个生产者事件或消费者事件。此外，一个微服务可以同时拥有生产者事件和消费者事件。我们将利用 Booking 微服务中创建新订单的现有功能 `POST /v1/booking`。这将是我们的事件，并利用 Apache Kafka 发送此事件。其他微服务可以通过监听该事件来消费此事件。

### 生成事件

当产生事件时，对象会被发送到 Kafka。同样，Kafka 将此对象发送给所有监听器（微服务）。简之，产生的对象在网络上传输。因此，我们需要对这些对象的序列化支持。我们将使用 Apache Avro 进行数据序列化。它以 JSON 格式定义数据结构（模式），并为 Maven 和 Gradle 提供了插件，用于使用模式生成 Java 类。Avro 与 Kafka 配合得很好，因为两者都是 Apache 产品，并在集成方面相互契合。

让我们从定义在创建新订单时在网络上传输的对象模式开始。正如之前提到的，为了生成事件，我们将利用现有的 Booking 微服务。我们将在 Booking 微服务的 `src/main/resources/avro` 目录中创建 Avro 模式文件 `bookingOrder.avro`。

`bookingOrder.avro` 文件将如下所示：

```json
{
  "namespace": "com.packpub.mmj.booking.domain.valueobject.avro",
  "type": "record",
  "name": "BookingOrder",
  "fields": [
    {"name": "id", "type": "string", "default": ""},
    {"name": "name", "type": "string", "default": ""},
    {"name": "userId", "type": "string", "default": ""},
    {"name": "requestId", "type": "string", "default": ""},
    {"name": "tableId", "type": "string", "default": ""},
    {"name": "date", "type": "[null, \"string\"]", "default": null},
    {"name": "time", "type": "[null, \"string\"]", "default": null}
  ]
}
```

在这里，`namespace` 代表记录该类的包类型，`name` 代表类的名称，而 `fields` 代表类的属性。当我们使用此模式生成 Java 类时，它会在 `com.packpub.mmj.booking.domain.valueobject.avro` 包中创建一个新的 Java 类 `BookingOrder.java`，包含 `fields` 中定义的所有属性。

在 `fields` 中，我们有 `name` 和 `type` 分别代表属性的名称和类型。对于所有字段，我们都使用了输入类型 `string`。你也可以使用其他原始类型，如 `boolean`、`int` 和 `double`。此外，你还可以使用复杂类型，如 `record`（在前面的代码段中使用）、`enum`、`array` 和 `map`。`default` 类型代表属性的默认值。

上述模式将用于生成代码。我们将利用 `avro-maven-plugin` 从 Avro 模式生成 Java 源文件。我们将在子 pom（即服务的 `pom.xml`）的 `plugins` 部分中添加此插件：

```xml
<plugin>
  <groupId>org.apache.avro</groupId>
  <artifactId>avro-maven-plugin</artifactId>
  <version>1.8.2</version>
  <executions>
    <execution>
      <phase>generate-sources</phase>
      <goals>
        <goal>schema</goal>
      </goals>
    </execution>
  </executions>
  <configuration>
    <sourceDirectory>${project.basedir}/src/main/resources/avro/</sourceDirectory>
    <outputDirectory>${project.basedir}/src/main/java/</outputDirectory>
  </configuration>
</plugin>
```

你可以看到在配置部分，配置了 `sourceDirectory` 和 `outputDirectory`。因此，当你运行 `mvn package` 时，它会在位于配置的 `outputDirectory` 内部的 `com.packpub.mmj.booking.domain.valueobject.avro` 包中创建 `BookingOrder.java` 文件。

现在我们已经有了 Avro 模式和生成的 Java 源文件，我们将添加产生事件所需的 Maven 依赖项。

在 Booking 微服务的 `pom.xml` 文件中添加依赖：

```xml
<dependency>
  <groupId>org.apache.avro</groupId>
  <artifactId>avro</artifactId>
  <version>1.8.2</version>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-stream</artifactId>
  <version>2.0.0.M1</version>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-kafka</artifactId>
</dependency>
<dependency>
  <groupId>org.apache.kafka</groupId>
  <artifactId>kafka-clients</artifactId>
  <version>0.11.0</version>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-stream-schema</artifactId>
</dependency>
```

在这里，我们添加了三个主要的依赖：`avro`、`spring-cloud-stream` 和 `kafka-clients`。此外，我们添加了与 Kafka 的流集成（`spring-cloud-starter-kafka`）和流支持模式（`spring-cloud-stream-schema`）。

现在，既然依赖已经就绪，我们就可以开始编写生产者的实现。Booking 微服务将向 Kafka 流发送 `amp.bookingOrdered` 事件。我们将为此目的声明消息通道。这可以通过带有 `@InboundChannelAdapter` 的 `Source.OUTPUT` 完成，也可以通过声明 Java 接口来实现。我们将使用接口方法，因为它更容易理解和关联。

我们将在 `com.packtub.mmj.booking.domain.message` 包中创建 `BookingMessageChannels.java` 消息通道。在这里，我们可以添加所有所需的消息通道。由于我们在示例实现中使用单个事件，我们只需要声明 `bookingOrderOutput`。

`BookingMessageChannels.java` 文件将如下所示：

```java
package com.packtub.mmj.booking.domain.message;

import org.springframework.cloud.stream.annotation.Output;
import org.springframework.messaging.MessageChannel;

public interface BookingMessageChannels {

    public final static String BOOKING_ORDER = "bookingOrderOutput";

    @Output(BOOKING_ORDER)
    MessageChannel bookingOrderOutput();
}
```

在这里，我们使用 `@Output` 注解定义了 `bookingOrderOutput` 通道。我们需要在 `application.yaml` 中配置 Kafka 服务器：

```yaml
spring:
  cloud:
    bindings:
      bookingOrderOutput:
        destination: amp.bookingOrdered
```

在这里，`bookingOrderOutput` 通道绑定到了 Kafka 流。



# 响应式微服务

在这里，`bookingOrderOutput` 通道绑定到了 Kafka 流。

现在，既然依赖已经就绪，我们可以开始编写生产者的实现。Booking 微服务将向 Kafka 流发送 `amp.bookingOrdered` 事件。我们将为此目的声明消息通道。这可以通过带有 `@InboundChannelAdapter` 的 `Source.OUTPUT` 完成，也可以通过声明 Java 接口来实现。我们将使用接口方法，因为它更容易理解和关联。

我们将在 `com.packtub.mmj.booking.domain.service.message` 包中创建 `BookingMessageChannels.java` 消息通道。在这里，我们可以添加所有所需的消息通道。由于我们在示例实现中使用单个事件，我们只需要声明 `bookingOrderOutput`。

`BookingMessageChannels.java` 文件将如下：

```java
package com.packtub.mmj.booking.domain.message;

import org.springframework.cloud.stream.annotation.Output;
import org.springframework.messaging.MessageChannel;

public interface BookingMessageChannels {

    public final static String BOOKING_ORDER = "bookingOrderOutput";

    @Output(BOOKING_ORDER)
    MessageChannel bookingOrderOutput();
}
```

在这里，我们使用 `@Output` 注解定义了 `bookingOrderOutput` 通道。我们需要在 `application.yaml` 中配置 Kafka 服务器：

```yaml
spring:
  cloud:
    bindings:
      bookingOrderOutput:
        destination: amp.bookingOrdered
```

在这里，`bookingOrderOutput` 通道绑定到了 Kafka 流。

## BookingServiceImpl 实现

`BookingServiceImpl.java` 文件如下：

```java
@EnableBinding(BookingMessageChannels.class)
public class BookingServiceImpl extends BaseService<Booking, String>
    implements BookingService {
...
    private BookingMessageChannels bookingMessageChannels;

    @Autowired
    public void setBookingMessageChannels(BookingMessageChannels bookingMessageChannels) {
        this.bookingMessageChannels = bookingMessageChannels;
    }
}
```

```java
@Override
public void add(Booking booking) throws Exception {
    ...
    super.add(booking);
    produceBookingOrderEvent(booking);
}
```

```java
@Override
public void produceBookingOrderEvent(Booking booking) throws Exception {
    final BookingOrder.Builder builder = BookingOrder.newBuilder();
    builder.setId(booking.getId());
    builder.setName(booking.getName());
    builder.setRestaurantId(booking.getRestaurantId());
    builder.setTableId(booking.getTableId());
    builder.setUserId(booking.getUserId());
    builder.setDate(booking.getDate().toString());
    builder.setTime(booking.getTime().toString());
    BookingOrder bo = builder.build();
    final Message<BookingOrder> message = MessageBuilder.withPayload(bo).build();
    bookingMessageChannels.bookingOrderOutput().send(message);
    LOG.info("sending booking order: {}", booking);
}
```

在这里，我们声明了通过 setter 方法自动注入的 `bookingMessageChannel` 对象。Spring cloud stream 注 `@EnableBinding` 绑定了 `BookingMessageChannels` 类中定义的 `bookingOrderOutput` 通道。

添加了 `produceBookingOrder` 方法，该方法接收一个订单对象。在 `produceBookingOrder` 方法内部，使用传入的订单对象来设置 `BookingOrder` 对象的属性。然后，使用 `bookingOrder` 对象构建消息。最后，通过 `bookingMessageChannels` 将消息发送到 Kafka。

在订单成功持久化到数据库（DB）之后会调用 `produceBookingOrder` 方法。

## 测试验证

要测试此功能，你可以运行以下命令启动 Booking 微服务：

```
java -jar booking-service/target/booking-service.jar
```

请确保 Kafka 和 Zookeeper 应用程序已在 `application.yaml` 中定义的主机和端口上正常运行，以便进行成功的测试。

然后，通过任何 REST 客户端通过发送一个 POST 请求（`http://<host>:<port>/v1/booking`）来处理订单，其有效负载（payload）如下：

```json
{
  "id": "99999999999",
  "name": "Test Booking 888",
  "userId": "3",
  "restaurantId": "1",
  "tableId": "1",
  "date": "2017-10-02",
  "time": "20:20:20.963543300"
}
```

它将产生一个 `amp.bookingOrder` Kafka 主题（事件），如 Booking 微服务控制台上发布的的日志所示：

```
2017-10-02 20:22:17.538 INFO 4940 --- [nio-7052-exec-1]
c.p.m.b.d.service.BookingServiceImpl : sending bookingOrder: {id:
999999999999, name: Test Booking 888, userId: 3, restaurantId: 1, tableId:
1, date: 2017-10-02, time: 20:20:20.963543300
```

同样，Kafka 控制台将显示以下消息，确认 Kafka 已成功接收到消息：

```
[2017-10-02 20:22:17,646] INFO Updated PartitionLeaderEpoch. New: (epoch:0,
offset:0), Current: (epoch-1, offset-1) for Partition:
amp.bookingOrder-0. Cache now contains 0 entries.
(kafka.server.epoch.LeaderEpochFileCache
```

我们现在可以转向之前生成的事件的消费者了。

# 第6章

## 消费事件

首先，我们将在父级 `pom.xml` 文件中添加新模块 `billing-service`，并按照第 5 章“部署与测试”中的方法创建 Billing 微服务。我们为 Booking 微服务编写的大部分响应式代码将复用在 Billing 微服务中，例如 Avro schema 和 `pom.xml` 条目。

我们将像在 Booking 微服务中添加那样，在 Billing 微服务中添加 Avro schema。由于 schema 命名空间（包名）在 Billing 微服务中将是相同的 booking 包，因此我们需要在 `BillingApp.java` 的 `@SpringBootApplication` 注解的 `scanBasePackages` 属性中添加 `com.packpub.mmj.booking`。这允许 Spring 上下文也扫描 booking 包。

我们将在 Billing 微服务的 `pom.xml` 中添加以下依赖，这与我们在 Booking 微服务中添加的相同。

Billing 微服务的 `pom.xml` 文件如下：

```xml
<dependency>
    <groupId>org.apache.avro</groupId>
    <artifactId>avro</artifactId>
    <version>1.8.2</version>
</dependency>
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-stream</artifactId>
    <version>2.0.0</version>
</dependency>
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-stream-binder-kafka</artifactId>
    <version>2.0.0.RELEASE</version>
</dependency>
<dependency>
    <groupId>org.apache.kafka</groupId>
    <artifactId>kafka-clients</artifactId>
    <version>2.0.0</version>
</dependency>
```

## 参考链接

以下链接将为你提供更多信息：

- Apache Kafka: https://kafka.apache.org/
- Apache Avro: https://avro.apache.org/
- Avro Specs: https://avro.apache.org/docs/current/spec.html
- Spring Cloud Stream: https://cloud.spring.io/spring-cloud-stream/

## Billing 消息通道配置

在这里，我们在 Billing 服务中添加了带有 `@Input` 注解的通道：

```java
package com.packpub.mmj.booking;

import org.springframework.cloud.stream.annotation.Input;
import org.springframework.messaging.MessageChannel;

public interface BillingMessageChannels {

    /**
     * 
     */
    String BOOKING_ORDER = "bookingOrderInput";

    @Input(BOOKING_ORDER)
    MessageChannel bookingOrderInput();
}
```

我们将在 `application.yaml` 中将 `bookingOrderInput` 绑定到 Kafka：

```yaml
spring:
  cloud:
    stream:
      bindings:
        bookingOrderInput:
          destination: amp.bookingOrder
          consumer:
            group: bookingGroup
```

最后，我们将通过 `@EnableBinding` 注解启用 `bookingOrderInput` 到流的绑定，并在 `BillingApp.java`（billing-service 的主类）中创建 `EventListener` 的 bean。

`BillingApp.java` 看起来如下：



```java
package ...

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.cloud.stream.annotation.EnableBinding;
import org.springframework.context.annotation.Bean;

@SpringBootApplication(scanBasePackages = {"com.packpub.mmj.billing", "com.packpub.mmj.booking"})
@EnableBinding(BillingMessageChannels.class)
public class BillingApp {
    public static void main(String[] args) {
        SpringApplication.run(BillingApp.class, args);
    }

    @Bean
    public EventListener eventListener() {
        return new EventListener();
    }
}
```

现在，你可以启动 `Billing` 微服务并触发一个新的 `POST /v1/booking` REST 调用。你可以在 `Billing` 微服务的日志中找到收到的对象，如下所示：

```
2017-10-02 00:22:17.728 INFO 6748 --- [C-1]
c.p.m.b.d.s.EventListener : Received BookingOrder: {"id":"999999999999","name":"Test Booking 888","userId":"3","restaurantId":"1","tableId":"1","date":"2017-10-02","time":"20:20:20.963543300"}
```

## 总结

在本章中，你学习了响应式微服务或基于事件的微服务。这些服务基于消息/事件工作，而不是通过 HTTP 进行 REST 调用。它们在服务之间提供了异步通信，实现了非阻塞通信，并允许更好地利用资源和处理故障。

我们使用了 Apache Avro 和 Apache Kafka 配合 Spring Cloud Stream 库来实现响应式微服务。我们在现有的 `booking-service` 模块中添加了代码，在 Kafka topic 下产生 `amp.bookingOrdered` 消息，并添加了新的 `billing-service` 模块来消费同一个事件。

你可能想为生产者和消费者添加新事件。你可以作为练习，为一个事件添加多个消费者，或创建一个事件链。

在下一章中，你将学习如何从身份验证和授权方面对微服务进行安全保护。我们还将探索微服务安全的其他方面。

# 微服务的安全保护

如你所知，微服务是我们在部署在本地或云基础设施中的组件。微服务可以提供 API 或 Web 应用程序。我们的示例应用程序 OTRS 提供了 API。本章将重点介绍如何使用 Spring Security 和 Spring OAuth2 保护这些 API。我们还将关注 OAuth 2.0 基础，使用 OAuth 2.0 来保护 OTRS API。有关保护 REST API 的更多信息，请参阅 Packt Publishing 的书籍。你也可以参考 Packt Publishing 的 Spring Security 视频获取有关 Spring Security 的更多信息。我们还将学习跨源请求过滤器和跨站脚本阻止器。

在本章中，我们将涵盖以下主题：

- 启用安全套接层 (SSL)
- 身份验证与授权
- OAuth 2.0

## 启用安全套接层

在此，我们使用了超文本传输协议 (HTTP)。HTTP 以明文传输数据，但在互联网上以明文传输完全不是一个好主意。这会让黑客的工作变得简单，并允许他们使用数据嗅探器获取你的隐私信息，例如用户 ID、密码和信用卡详情。

我们绝对不想损害用户数据，因此我们将提供访问 Web 应用程序的最安全方式。因此，我们需要加密用户与我们应用程序之间交换的信息。我们将使用安全套接层 (SSL) 或传输安全层 (TLS) 来加密数据。

SSL 是一种旨在为网络通信提供安全（加密）的协议。HTTP 与 SSL 结合以提供 HTTP 的安全实现，被称为安全超文本传输协议，或称为基于 SSL 的超文本传输协议 (HTTPS)。HTTPS 确保了交换数据的隐私性和完整性得到保护。它还确保了所访问网站的真实性。这种安全性围绕在托管应用程序的服务器、用户终端和第三方信任存储服务器之间分发的签名数字证书。让我们看看这个过程是如何发生的：

1. 用户使用 Web 浏览器向 Web 应用程序发送请求，例如 `http://twitter.com`
2. 接收到请求后，服务器使用 HTTP 代码 302 将浏览器重定向到 `https://twitter.com`
3. 用户浏览器连接到 `https://twitter.com`，作为响应，服务器向用户浏览器提供包含数字签名的证书
4. 用户浏览器接收到此证书，并对照受信任的证书机构 (CA) 列表进行验证
5. 一旦证书一直验证到根 CA，用户浏览器与托管应用程序的服务器之间就会建立加密通信：

![](img/f551c3d57000fcdbbc1268267d5af69e_173_0.png)

尽管 SSL 确保了加密和 Web 应用程序真实性方面的安全性，但它无法防止钓鱼和其他攻击。专业的黑客可以解密使用 HTTPS 发送的信息。

![](img/f551c3d57000fcdbbc1268267d5af69e_174_0.png)

现在，在过了 SSL 的基础之后，让我们为我们的示例 OTRS 项目实现它。我们不需要为所有微服务实现 SSL。所有微服务都将通过我们的代理或边缘服务器（外部环境的 `Zuul-Server`）访问，但我们新的微服务 `security-service` 除外，我们将在本章引入它用于身份验证和授权。

首先，我们将在边缘服务器上设置 SSL。我们需要处理在嵌入式 Tomcat 中启用 SSL 所需密钥库。我们将使用自签名证书进行演示。我们将使用 Java `keytool` 使用以下命令生成密钥库。你可以使用任何其他工具：

```
keytool -genkey -keyalg RSA -alias selfsigned -keystore keystore.jks -ext dns:localhost -storepass password -validity 365 -keysize 2048
```

它会询问名称、地址、组织等信息（如下截图所示）：

```
C:\workspace\ms\online-table-reservation-6>keytool -genkey -keyalg RSA -alias selfsigned -keystore keystore.jks -ext dns:localhost -storepass password -validity 365 -keysize 2048
What is your first and last name?
[Unknown]: localhost
What is the name of your organizational unit?
[Unknown]: unit
What is the name of your organization?
[Unknown]: org
What is the name of your City or Locality?
[Unknown]: city
What is the name of your State or Province?
[Unknown]: state
What is the name of your Country?
[Unknown]: CN
Is the password for the keystore correct?
Enter password password: password
Enter new password for the alias: password
```

![](img/f551c3d57000fcdbbc1268267d5af69e_174_0.png)

## OAuth 的用法

OAuth 的各种用途如下：

- 正如所述，它可以用于身份验证。你可能在各种应用程序中见过它，它显示诸如“使用 Facebook 登录”或“使用 Twitter 登录”等消息。
- 应用程序可以使用它从其他应用程序读取数据，例如通过在应用程序中集成 Facebook 小部件，或在你的博客上显示 Twitter Feed。
- 或者，前一点的反面也可能成立：你允许其他应用程序访问终端用户的数据。

## OAuth 2.0 规范 - 简要细节

我们将尝试以简洁的方式讨论并理解 OAuth 2.0 规范。让我们先看看使用 Twitter 登录是如何运作的。

请注意，此处提到的过程是在编写时使用的，未来可能会发生变化。然而，该过程正确地描述了 OAuth 2.0 流程之一：

1. 用户访问 Quora 首页，页面显示了多种登录选项。我们将探索“使用 Twitter 继续”链接的流程。
2. 当用户点击“使用 Twitter 继续”链接时，Quora 打开一个新窗口（Chrome），将用户重定向到 `www.twitter.com` 应用。在此过程中，很少有 Web 会将用户重定向到同一个打开的标签页/窗口。
3. 在此新窗口/标签页中，用户使用其凭据登录 `www.twitter.com`。
4. 如果用户尚未授权 Quora 应用程序使用其数据，Twitter 将请求用户许可，授权 Quora 访问用户信息。如果用户已经授权了 Quora，则跳过此步骤。
5. 经过适当身份验证后，Twitter 带认证码将用户重定向到 Quora 的重定向 URI。
6. 当在浏览器中输入 Quora 重定向 URI 时，Quora 将 client ID、client secret token 和认证码（Twitter 在步骤五中发送的）发送给 Twitter。
7. 在验证这些参数后，Twitter 将访问令牌发送给 Quora。
8. 成功获取访问令牌后，用户成功登录 Quora。
9. Quora 可能会使用此访问令牌从 Twitter 获取用户信息。

你一定在想 Twitter 是如何获取 Quora 的重定向 URI、client ID 和 secret token 的。Quora 作为客户端应用程序工作，而 Twitter 作为授权服务器。Quora 作为客户端，在 Twitter 上注册，使用 Twitter 的 OAuth 实现使用资源所有者（终端用户）信息。Quora 在注册时提供一个重定向 URI。Twitter 向 Quora 提供 client ID 和 secret token。在 OAuth 2.0 中，用户信息被称为用户资源。Twitter 提供资源服务器和一个授权服务器。我们将在后续章节中讨论更多 OAuth 术语。

![](img/f551c3d57000fcdbbc1268267d5af69e_178_0.png)

## OAuth 2.0 角色

OAuth 2.0 规范中定义了四个角色：

- 资源所有者



# 微服务安全

## 第 7 章

### 核心角色

- 资源服务器
- 客户端
- 授权服务器

![](img/f551c3d57000fcdbbc1268267d5af69e_179_0.png)

### 资源所有者

以 Quora 使用 Twitter 登录为例，Twitter 用户就是资源所有者。资源所有者是拥有可共享的受保护资源（例如用户名、推文等）的实体。该实体可以是应用程序，也可以是人。我们称该实体为资源所有者，因为它只能授予对其资源的访问权限。规范还规定，当资源所有者是人时，他们被称为终端用户。

### 资源服务器

资源服务器托管受保护的资源。它应该能够使用访问令牌处理对这些资源的访问请求。以 Quora 使用 Twitter 登录为例，Twitter 是资源服务器。

### 客户端

以 Quora 使用 Twitter 登录为例，Quora 是客户端。客户端是代表资源所有者向资源服务器请求受保护资源访问的应用程序。

### 授权服务器

授权服务器只有在资源所有者通过身份验证后，才会向客户端应用程序提供不同的令牌，例如访问令牌或刷新令牌（`refresh tokens`）。

OAuth 2.0 没有提供资源服务器与授权服务器之间交互的任何规范。因此，授权服务器和资源服务器可以在同一台服务器上，也可以在单独的服务器上。

单个授权服务器也可以用于多个资源服务器发放访问令牌。

### OAuth 2.0 客户端注册

与授权服务器通信以获取资源访问密钥的客户端应该先在授权服务器上注册。OAuth 2.0 规范没有规定客户端向授权服务器注册的方式。注册不需要客户端与授权服务器之间的直接通信。注册可以使用自颁发或第三方颁发的断言（`assertions`）完成。授权服务器使用这些断言之一获取所需的客户端属性。客户端属性包括：

- 客户端类型（见下一节）
- 客户端重定向 URI，如 Quora 使用 Twitter 的示例所示。这是 OAuth 2.0 使用的端点之一。将在端点章节讨论。
- 授权所需的其他信息，例如客户端名称、描述、图标。

### 客户端类型

根据维护客户端凭据的能力，规范描述了两种客户端类型：机密和公共。授权服务器使用凭据与它们通信。

- **机密客户端类型**：这种应用程序能够安全地维护密码或其他凭据。在 Quora 使用 Twitter 的示例中，Quora 应用是安全的且访问受限的。因此它是客户端类型之一。只有 Quora 管理员可以访问凭据。
- **公共客户端类型**：这些应用程序无法安全地维护密码或其他凭据。运行在移动或桌面上的原生应用是公共类型的完美示例，因为这些凭据嵌入在内部。黑客可以破解这些内容，凭据可能会泄露。

客户端可以是分布式组件的应用程序，例如，它可能同时拥有浏览器组件和服务器端组件。在这种情况下，两个组件具有不同的客户端类型和安全上下文。如果授权服务器支持此类客户端，客户端应将每个组件注册为独立的客户端。

### 客户端配置

根据 OAuth 2.0 客户端类型，客户端可以具有以下配置：

- **Web 应用程序**：Quora 使用 Twitter 示例中的 Quora Web 应用是 OAuth 2.0 Web 配置的完美示例。Quora 是运行在 Web 服务器上的机密客户端。资源所有者（终端用户）通过设备（桌面电脑/平板电脑/手机）上的浏览器访问 Quora 应用（OAuth 2.0 客户端）。资源所有者无法访问客户端（OAuth 2.0 客户端）凭据和访问令牌，因为这些存储在 Web 服务器上。你可以在 OAuth 2.0 示例流程图中看到这种行为。参见下图中步骤六到八：
- **用户代理应用程序**：用户代理应用程序属于公共客户端类型。尽管如此，应用程序位于 Web 服务器上，但资源所有者在用户代理（例如网络浏览器）上下载并运行该程序。在这里，位于资源所有者设备上的下载程序与授权服务器通信。资源所有者可以访问客户端凭据和访问令牌。游戏应用程序是此类应用配置的良好示例。用户代理应用程序流程所示：

![](img/f551c3d57000fcdbbc1268267d5af69e_182_0.png)

- **原生应用**：原生应用与基于用户代理的应用程序类似，不同之处在于它们被安装在资源所有者的设备上并原生执行，而不是从 Web 服务器下载后在用户代理内部执行。你在移动设备上下载的许多原生客户端（移动应用程序）都是原生应用类型。在这里，平台确保设备上的其他应用程序不会访问其他应用程序的凭据和令牌。此外，原生应用不应与与其应用通信的服务器共享客户端凭据和 OAuth 令牌，如图所示：

![](img/f551c3d57000fcdbbc1268267d5af69e_184_0.png)

### 客户端标识符 (Client identifier)

授权服务器负责为注册的客户端提供一个唯一的标识符。该客户端标识符是注册客户端提供的信息的字符串表示。授权服务器需要确保该标识符是唯一的。授权服务器不应单独使用该标识进行身份验证。

OAuth 2.0 规范没有规定客户端标识符的大小。授权服务器可以设置大小，并应该记录其发布的客户端标识符的大小。

### 客户端身份验证 (Client authentication)

授权服务器应该根据客户端类型对客户端进行身份验证。授权服务器应该确定适合并满足安全要求的身份验证方法。在每个请求中应只使用一种身份验证方法。

通常，授权服务器使用一组客户端凭据（如客户端密码和某些密钥令牌）来验证机密客户端。

授权服务器可以与公共客户端建立客户端身份验证方法。但出于安全考虑，不能依靠此身份验证方法来识别客户端。

拥有客户端密码的客户端可以使用基本 HTTP 身份验证。OAuth 2.0 不建议在请求体中发送客户端凭据，而是建议在需要身份验证的端点使用 TLS 和防暴力攻击保护。

### OAuth 2.0 协议端点 (OAuth 2.0 protocol endpoints)

端点是我们用于 REST 或 Web 组件（如 Servlet 或 JSP）的 URI。OAuth 2.0 定义了三种类型的端点。两个是授权服务器端点，一个是客户端端点：

- 授权端点（授权服务器端点）
- 令牌端点（授权服务器端点）
- 重定向端点（客户端端点）

### 授权端点

该端点负责验证资源所有者的身份，验证通过后获取授权许可。我们将在后续章节中讨论授权许可。

授权服务器要求授权端点使用 TLS。端点 URI 不得包含分片组件（`fragment component`）。授权端点必须支持 HTTP GET 方法。

规范未规定以下内容：

- 授权服务器验证客户端的方式。
- 客户端将如何接收授权端点 URI。通常，文档包含授权端点 URI，或者客户端在注册时获取。

### 令牌端点

客户端通过发送授权许可（`grant token`）或刷新令牌（`refresh token`）调用令牌端点以接收访问令牌。除了隐式许可外，所有的授权许可都使用令牌端点。

与授权端点一样，令牌端点也需要 TLS。客户端必须使用 HTTP POST 方法向令牌端点请求。

与授权端点一样，规范未规定客户端将如何接收令牌端点 URI。

### 重定向端点

一旦资源所有者和授权服务器完成授权端点的交互，授权服务器将通过重定向端点将资源所有者的用户代理（例如浏览器）定向回客户端。客户端在注册时提供重定向端点。重定向端点必须是绝对 URI 不包含分片组件。OAuth 2.0 端点如下：

![](img/f551c3d57000fcdbbc1268267d5af187_0.png)

### OAuth 2.0 许可类型 (OAuth 2.0 grant types)

客户端根据从资源所有者获得的授权，向授权服务器请求访问令牌。资源所有者以授权许可的形式授权。OAuth 2.0 定义了四种授权许可：

- 授权码许可 (`Authorization grant`)
- 隐式许可 (`Implicit grant`)
- 资源所有者密码许可 (`Resource owner password grant`)
- 客户端凭据许可 (`Client grant`)

OAuth 2.0 还提供了扩展类型。你可以在官方 OAuth 2.0 规范中探索这些。

### 授权码许可 (Authorization code grant)

我们在 OAuth 2.0 示例中讨论的授权码许可流程描述了授权码许可。我们将增加更多步骤来完成流程。假设用户登录到应用程序：

1. 登录后，用户点击他们的个人资料页。
2. OAuth 客户端从资源所有者（`resource owner`）的授权向授权服务器请求访问令牌。
3. 授权服务器验证访问令牌。
4. 验证令牌成功后，授权服务器提供请求的资源。
5. 应用程序显示用户的个人资料页。

### 授权码请求与响应 (Authorization code requests and responses)

让我们讨论这些请求中使用的参数：

![](img/f551c3d57000fcdbbc1268267d5af69e_189_0.png)

#### 向授权端点的授权请求（第四步）

| 参数 | 是否必要 | 描述 |
|---|---|---|
| `response_type` | 必须 | `authorization_code` |
| `client_id` | 必须 | 代表注册时客户端发布的 ID。 |
| `redirect_uri` | 必须 | 如果在授权码请求中包含，则为必须。 |
| `scope` | 可选 | 请求范围。 |
| `state` | 推荐 | 客户端使用此参数维护请求与回调（来自授权服务器）之间的状态。 |

#### 授权响应（第五步）

| 参数 | 是否必要 | 描述 |
|---|---|---|
| `code` | 必须 | 授权服务器生成的授权码。代码在生成后应过期；建议的最大生命周期为 10 分钟。客户端不能多次使用该代码。如果客户端多次使用，则必须拒绝请求并撤销所有基于该代码之前的令牌。代码绑定到客户端 ID 和重定向 URI。 |
| `state` | 必须 | 代表注册时客户端发布的 ID。 |

#### 向令牌端点的令牌请求（第七步）

| 参数 | 是否必要 | 描述 |
|---|---|---|
| `grant_type` | 必须 | `authorization_code` |
| `code` | 必须 | 从授权服务器接收的代码。 |
| `redirect_uri` | 必须 | 如果在授权码请求中包含，则为必须。 |
| `client_id` | 必须 | |

#### 令牌响应（第八步）

| 参数 | 是否必要 | 描述 |
|---|---|---|
| `access_token` | | 授权服务器发布的访问令牌。 |
| `token_type` | 必须 | 授权服务器定义的令牌类型。根据此，客户端可以使用访问令牌。例如，`Bearer` 或 `Mac`。 |
| `refresh_token` | 可选 | 客户端可以使用此令牌通过相同的授权许可获取新的访问令牌。 |
| `expires_in` | 推荐 | 秒表示访问令牌的生命周期。600 表示访问令牌寿命为 10 分钟。如果响应中未提供此参数，文档应强调访问令牌的生命周期。 |
| `scope` | 可选/必须 | 与客户端请求的范围相同时可选。如果访问令牌范围与客户端提供的范围不同，则为必须，以告知客户端实际授予的范围。如果客户端在请求令牌时未提供范围，则授权服务器应提供默认范围，或拒绝请求并指示无效范围。 |

#### 错误响应

| 参数 | 必选/可选 | 说明 |
|---|---|---|
| `error` | 必选 | 规范中定义的错误代码之一，`unauthorized_client` 或 `invalid_scope`。 |
| `error_description` | 可选 | 错误的简短描述。 |
| `error_uri` | 可选 | 描述错误的错误页面的 URI。 |

如果在客户端授权请求中传递了 `state`，则错误响应中也会发送额外的错误参数 `state`。

### 隐式授权 (Implicit grant)

隐式授权流不涉及授权码步骤。它为授权码提供隐式授权。将隐式授权流与授权码授权流相比，除了授权码步骤外，一切都是相同的。因此，它被称为隐式授权。让我们来看看它的流程：

1. 客户端应用（例如 Quora）向资源服务器（例如 Facebook、Twitter 等）发送访问令牌请求，并带有 client ID、重定向 URI 等参数。
2. 如果用户尚未身份验证，则可能需要进行身份验证。在身份验证成功和其他输入验证后，资源服务器发送访问令牌。
3. OAuth 客户端从资源服务器请求用户（资源所有者）的资源（例如 Twitter 头像等），并发送上一步收到的访问令牌。
4. 资源服务器使用授权服务器验证访问令牌。
5. 访问令牌验证成功，资源服务器将请求的资源提供给客户端应用（OAuth 客户端）。
6. 客户端应用使用这些资源。

### 隐式授权请求与响应

如果你查看隐式授权流的所有步骤（共六步），可以看到客户端向授权服务器总共发送了两个请求，授权服务器提供了两个响应：一个用于访问令牌的请求-响应，另一个用于访问令牌验证的请求-响应。

让我们讨论一下这些请求和响应中使用的参数。

#### 向授权端点 URI 的授权请求

| 参数 | 必选/可选 | 说明 |
|---|---|---|
| `response_type` | 必选 | `Token`（必须使用此值）。 |
| `client_id` | 必选 | 代表授权服务器在注册时颁给客户端的 ID。 |
| `redirect_uri` | 可选 | 代表客户端在注册时提供的重定向 URI。 |
| `scope` | 可选 | 请求的范围。如果未提供，授权服务器将根据定义的策略提供范围。 |
| `state` | 建议 | 客户端使用此参数来维护请求与回调（来自授权服务器）之间的客户端状态。规范建议使用它来防止跨站请求伪造攻击。 |

#### 访问令牌响应

| 参数 | 必选/可选 | 说明 |
|---|---|---|
| `access_token` | 必选 | 授权服务器颁发的访问令牌。 |
| `token_type` | 必选 | 授权服务器定义的令牌类型。根据此类型，客户端可以使用该访问令牌。例如，`Bearer` 或 `Mac`。 |
| `refresh_token` | 可选 | 客户端可以使用此令牌通过相同的授权许可获取新的访问令牌。 |
| `expires_in` | 建议 | 表示访问令牌的有效期（以秒为单位）。值 600 表示访问令牌的有效期为 10 分钟。如果响应中未提供此参数，文档应突出访问令牌的有效期。 |
| `scope` | 可选/必选 | 如果与客户端请求的范围相同，则可选。如果访问令牌范围与客户端在请求中提供的范围不同，则必选，以告知访问令牌的实际范围。如果客户端在请求访问令牌时未提供范围，授权服务器应提供默认范围，或拒绝请求并指示范围无效。 |
| `state` | 可选/必选 | 如果在客户端授权请求中传递了 `state`，则必选。 |

#### 错误响应

| 参数 | 必选/可选 | 说明 |
|---|---|---|
| `error` | 必选 | 规范中定义的错误代码之一，例如 `unauthorized_client` 或 `invalid_scope`。 |
| `error_description` | 可选 | 错误的简短描述。 |
| `error_uri` | 可选 | 描述错误的错误页面的 URI。 |

如果在客户端授权请求中传递了 `state`，则错误响应中也会发送额外的错误参数 `state`。

### 资源所有者密码凭据授权 (Resource owner password credentials grant)

此流程通常用于移动或桌面端应用程序。在此授权流中，仅发起了两个请求：其中一个用于请求访问令牌，另一个用于访问令牌验证，与隐式授权流类似。唯一的区别是资源所有者的用户名和密码会随访问令牌请求一起发送。（在隐式授权中，通常在浏览器中，会重定向用户进行身份验证。）让我们来看看它的流程：

1. 客户端应用（例如 Quora）向资源服务器（例如 Facebook、Twitter 等）发送访问令牌，并带有 client ID、资源所有者的用户名和密码等。在参数验证成功后，资源服务器发送访问令牌。
2. OAuth 客户端从资源服务器请求用户（资源所有者）的资源（例如 Twitter 头像），并发送上一步收到的访问令牌。
3. 资源服务器使用授权服务器验证访问令牌。
4. 访问令牌验证成功后，资源服务器将请求的资源提供给客户端应用。
5. 客户端应用使用这些资源。

#### 资源所有者密码凭据授权请求与响应

正如前所述，在所有步骤（共五步）中可以看到客户端向授权服务器总共发送了两个请求，授权服务器提供了两个响应：一个用于访问令牌的请求-响应，另一个用于资源的请求-响应。

让我们讨论一下这些请求和响应中使用的参数。

#### 向令牌端点的访问令牌请求

| 参数 | 必选/可选 | 说明 |
|---|---|---|
| `grant_type` | 必选 | `password`（必须使用此值）。 |
| `username` | 必选 | 资源所有者的用户名。 |
| `password` | 必选 | 资源所有者的密码。 |
| `scope` | 可选 | 请求的范围。如果没有提供，授权服务器提供范围。 |

#### 访问令牌响应（第一步）

| 参数 | 必选/可选 | 说明 |
|---|---|---|
| `access_token` | 必选 | 授权服务器颁发的访问令牌。 |
| `token_type` | 必选 | 授权服务器定义的令牌类型。根据此类型，客户端可以使用该访问令牌。例如，`Bearer` 或 `Mac`。 |



| refresh_token | 可选 | 客户端可以使用此令牌通过相同的授权许可获取新的访问令牌。 |

| expires_in | 建议 | 表示访问令牌的有效期（以秒为单位）。值 600 表示访问令牌的有效期为 10 分钟。如果响应中未提供此参数，文档应突出访问令牌的有效期。 |

| scope | 可选 | 额外参数。 |

# 微服务安全

## 第 7 章

## 客户端凭据授权

顾名思义，使用的是客户端凭据而不是用户（资源所有者）。除了凭据外，与资源所有者授权流非常相似：

1. 客户端应用（例如 Quora）向资源服务器（例如 Facebook、Twitter 等）发送访问令牌请求，并带有 `grant type` 和 `scope`。`client ID` 和 `secret` 被添加到 header 中。验证成功后，资源服务器发送访问令牌。
2. OAuth 客户端从资源服务器请求用户（资源所有者）的资源（例如 Twitter 头像等），并发送上一步收到的访问令牌。
3. 资源服务器使用授权服务器验证访问令牌。
4. 验证成功后，资源服务器将请求的资源提供给客户端应用（OAuth 客户端）。
5. 客户端应用使用这些资源。

### 客户端凭据授权请求与响应

如果你查看客户端凭据授权流的所有步骤（共五步），可以看到客户端向授权服务器总共发送了两个请求，授权服务器提供了两个响应：一个用于访问令牌的请求-响应，另一个用于涉及访问令牌验证的资源的请求-响应。

让我们讨论一下这些请求和响应中使用的参数。

#### 向端点的访问令牌请求

| 参数 | 必选/可选 | 说明 |
|---|---|---|
| grant_type | 必选 | `client_credentials`（必须使用此值）。 |
| scope | 可选 | 请求的范围。如果未提供，授权服务器将根据定义的策略提供范围。 |

#### 访问令牌响应

| 参数 | 强制/可选 | 说明 |
|---|---|---|
| access_token | 强制 | 由授权服务器颁发的访问令牌 |
| token_type | 强制 | 由授权定义的令牌类型。根据此类型，客户端可以使用访问令牌。例如：`Bearer` 或 `Mac`。 |
| expires_in | 建议 | 表示访问令牌的有效期（以秒为单位）。值 600 表示访问令牌的有效期为 10 分钟。如果响应中未提供此参数，则文档应突出显示访问令牌的有效期。 |

## 使用 Spring Security 实现 OAuth

OAuth 2.0 是一种保护 API 的方法。Spring Security 提供了 `Spring Cloud Security` 和 `Spring Cloud OAuth2` 组件，用于实现我们之前讨论的授权流。

我们将创建一个新服务——`security-service`，它将控制身份验证和授权。

创建一个新的 Maven 项目并按照以下步骤操作：

1. 在 `pom.xml` 中添加 Spring Security 和 Spring Cloud OAuth 2 依赖：

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-security</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-oauth2</artifactId>
</dependency>
```

2. 在应用程序类中使用 `@EnableResourceServer` 注解。这将允许该应用程序作为资源服务器工作。`@EnableAuthorizationServer` 注解是我们将使用的另一个注解，用于根据 OAuth 2.0 规范启用授权服务器：

```java
@SpringBootApplication
@RestController
@EnableResourceServer
public class SecurityApp {

    @RequestMapping("/user")
    public Principal user(Principal user) {
        return user;
    }

    public static void main(String[] args) {
        SpringApplication.run(SecurityApp.class, args);
    }

    @EnableAuthorizationServer
    protected static class OAuth2Config extends AuthorizationServerConfigurerAdapter {

        @Autowired
        private AuthenticationManager authenticationManager;

        @Override
        public void configure(AuthorizationServerEndpointsConfigurer endpointsConfigurer) throws Exception {
            endpointsConfigurer.authenticationManager(authenticationManager);
        }

        @Override
        public void configure(ClientDetailsServiceConfigurer clientDetailsServiceConfigurer) throws Exception {
            // 使用硬编码内存机制，因为这只是为了演示
            clientDetailsServiceConfigurer.inMemory()
                .withClient("acme")
                .secret("acmesecret")
                .authorizedGrantTypes("authorization_code", "refresh_token", "implicit", "password", "client_credentials")
                .scopes("webshop");
        }
    }
}
```

3. 在 `application.yml` 中更新 `security-service` 配置，如下代码所示：

- `server.contextPath`：表示上下文路径
- `security.user.password`：我们将在本次演示中使用硬编码密码。在实际使用时可以对其进行重新配置：

```yaml
info:
  component: Security Server

server:
  port: 9001
  ssl:
    key-store: classpath:keystore.jks
    key-store-password: password
    key-password: password
  contextPath: /auth

security:
  user:
    password: password

logging:
  level:
    org.springframework.security: DEBUG
```

现在我们已经准备好了安全服务器，我们将使用新的 `api-service` 微服务来暴露我们的 API，该服务将用于与外部应用程序和 UI 通信。

我们将修改 `Zuul-Server` 模块使其成为资源服务器。这可以通过以下步骤实现：

1. 在 `pom.xml` 中添加 Spring Cloud 和 Spring Security OAuth 2 依赖。这里，最后两个依赖是启用 `Zuul-Server` 作为资源服务器所需的：

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-zuul</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-eureka</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-feign</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-netflix-hystrix-stream</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-bus-amqp</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-stream-rabbit</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-web</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-security</artifactId>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-oauth2</artifactId>
</dependency>
```

2. 在应用程序类中使用 `@EnableResourceServer`。这将允许该应用程序作为资源服务器工作：

```java
@SpringBootApplication
@EnableResourceServer
@EnableEurekaClient
@EnableCircuitBreaker
@Configuration
@EnableFeignClients
public class EdgeApp {

    private static Logger LOG = LoggerFactory.getLogger(EdgeApp.class);

    static {
        // 仅在开发期间禁用主机名检查
        URLConnection.setDefaultHostnameVerifier((hostname, sslSession) -> true);
    }

    @Value("${rabbitmq.host:localhost}")
    String rabbitMqHost;

    @Bean
    public ConnectionFactory connectionFactory() {
        LOG.info("Create RabbitCF for host: {}", rabbitMqHost);
        CachingConnectionFactory connectionFactory = new CachingConnectionFactory(rabbitMqHost);
        return connectionFactory;
    }

    public static void main(String[] args) {
        SpringApplication.run(EdgeApp.class, args);
    }
}
```

3. 在 `application.yml` 中更新 `Zuul-Server` 配置，如下代码所示。`application.yml` 文件将如下：

```yaml
info:
  component: Security Server

spring:
  application:
    name: zuul-server
  aop:
    auto: false

zuul:
  ignoredServices: "*"
  routes:
    restaurantapi:
      path: /api
      serviceId: api-service
      stripPrefix: true

server:
  ssl:
    key-store: classpath:keystore.jks
    key-store-password: password
    key-password: password
  port: 8765

compression:
  enabled: true

security:
  oauth2:
    resource:
      userInfo: http://localhost:9001/auth/user

management:
  security:
    enabled: false
## 其他属性如 Eureka、日志等
```

在这里，`security.oauth2.resource.userInfo` 属性指向安全服务。API 通过指向服务的路由配置暴露给外部世界。

现在我们已经准备好了安全服务器，我们将使用 `api-service` 微服务来暴露我们的 API，该服务将用于与外部应用程序和 UI 通信。

现在，让我们测试并探索不同的 OAuth 2.0 授权类型的工作原理。

> 我们将利用 Chrome 浏览器的 Postman 扩展来测试不同的流。

![](img/f551c3d57000fcdbbc1268267d5af69e_203_0.png)

## 授权码模式

我们将在浏览器中输入以下 URL。授权码请求如下：

```
https://localhost:9001/oauth/authorize?response_type=code&client_id=client&redirect_uri=http://localhost:7771/apiAccess&state=1234
```

在这里，我们提供了客户端 ID（默认情况下，我们在安全服务中硬编码了该客户端）、重定向 URI、范围（安全服务中硬编码的 `apiAccess`）以及状态。你可能对 `state` 参数感到好奇。它包含一个随机数，我们以此防止跨站请求伪造。

如果资源所有者（用户）尚未身份验证，它将要求提供用户名和密码。提供用户名 `username`，提供密码 `password`；我们在安全服务中硬编码了这些值。

登录成功后，系统将要求你提供（资源所有者的）批准：

![](img/f551c3d57000fcdbbc1268267d5af69e_204_0.png)

点击 **Approve**（批准）并后点击 **Authorize**（授权）。此操作将把应用程序重定向到 `http://localhost:7771/1?code=o8t4fi&state=1234`。

如你所见，它返回了授权码（`code`）和状态（`state`）。

现在，我们将使用 Postman Chrome 扩展程序通过此代码获取访问令牌。首先，我们将使用 Username 作为客户端，Password 作为 `clientsecret` 来添加授权头，如下截图所示：

![](img/f551c3d57000fcdbbc1268267d5af69e_204_1.png)

这将向请求中添加 `Authorization` 头，其值为 `Basic Y2xpZW500mNsaWVudHN1Y3J1dA==`，这是 `client client-secret` 的 base-64 编码。

现在，我们将向请求添加几个参数，如下截图所示，然后提交请求：

![](img/f551c3d57000fcdbbc1268267d5af69e_205_0.png)

根据 OAuth 2.0 规范，这会返回以下响应：

```json
{
  "access_token": "6a233475-a5db-476d-8e31-d0aeb2d003e9",
  "token_type": "bearer",
  "refresh_token": "9d81b9e2-7f2f-44d5-b14b-dbbdccd648b8",
  "expires_in": 43199,
  "scope": "apiAccess"
}
```

现在，我们可以使用这些信息来访问资源所有者拥有的资源。例如，如果 `https://localhost:8765/api/restaurant/1` 代表 ID 为 1 的餐厅，那么它应该返回相应的餐厅详情。

如果没有访问令牌，如果我们直接输入 URL，它会返回 Unauthorized 错误信息：**Full authentication is required to access this resource.**（访问此资源需要完全身份验证。）

现在，让我们使用访问令牌访问此 URL，如下截图所示：



![](img/f551c3d57000fcdbbc1268267d5af69e_206_0.png)

如你所见，我们已经添加了带有访问令牌的 `Authorization` 头。

现在，我们将探索隐式授权（implicit grant）的实现。

# 隐式授权

隐式授权与授权码非常相似，区别在于缺少授权码授予步骤。如果你从授权码授权中移除第一步——授权码授予步骤（客户端应用程序从授权服务器接收授权令牌），其余步骤都是相同的。让我们检查一下。

在浏览器中输入以下 URL 和参数并按回车。同时，如果提示，请确保添加基本身份验证，以客户端作为用户名，密码作为密码：

```
https://localhost:9001/auth/oauth/authorize?response_type=token&redirect_uri=https://localhost:8765?scope=apiAccess&state=553344&client_id=client
```

在这里，我们使用以下请求参数调用授权端点：`response_type`、`client_id`、`redirect_uri`、`scope` 和 `state`。

当请求成功时，浏览器将重定向到下方的 URL，并带有新的请求参数和值：

```
https://localhost:8765/#access_token=6a233475-a5db-476d-8e31-d0aeb2bd003e9u9&token_type=bearer&state=553344&expires_in=19592
```

在这里，我们收到了 `access_token`、`token_type`、`state` 以及令牌的过期时长（`expires_in`）。现在，我们可以像授权码授权那样使用此访问令牌来访问 API。

# 资源所有者密码凭据授权

在这种授权模式中，我们在请求访问令牌时提供用户名和密码作为参数，同时带有 `grant_type`、`client` 和 `scope` 参数。我们还需要使用 `client_id` 和 `secret` 来验证请求。这些授权流使用客户端应用程序代替浏览器，通常用于移动和桌面应用程序。

# 微服务安全

在下方的 Postman 工具截图中，已经使用 `client_id` 和 `password` 通过基本身份验证添加了授权头：

![](img/f551c3d57000fcdbbc1268267d5af69e_208_0.png)

一旦客户端接收到访问令牌，其用法与在授权码授权中的用法类似。

# 客户端凭据授权

在此流中，客户端提供自己的凭据并获取访问令牌。它不使用资源所有者的凭据和权限。

如后续截图所示，我们直接输入 tokenendpoint，仅包含两个参数：`grant_type` 和 `scope`。授权头使用 `client_id` 和 `client secret` 添加：

![](img/f551c3d57000fcdbbc1268267d5af69e_209_0.png)

你可以像在授权码授权中解释的那样，使用访问令牌。

## 参考文献

如需更多信息，你可以参考以下链接：

- *RESTful Java Web Services Security*, René Enríquez, Andrés Salazar C, Packt Publishing: https://www.packpub.com/application-development/restful-java-web-services-security
- *Spring Security [Video]*, Packt Publishing: https://www.packpub.com/application-development/spring-security-video
- *The OAuth 2.0 Authorization Framework*: https://tools.ietf.org/html/rfc6749
- *Spring Security*: http://projects.spring.io/spring-security
- *Spring OAuth2*: http://projects.spring.io/spring-security-oath/

## 总结

在本章中，我们学习了如何使用 OAuth 2.0 保护微服务。我们探索了授权码授权、隐式授权、资源所有者密码凭据授权以及客户端凭据授权。我们还看到了如何使用访问令牌访问受保护的资源。在下一章中，我们将探索如何实现刷新令牌（`refresh tokens`）。

---

# 使用微服务 Web 消费服务

# 第 8 章

- 应用 DOM 配置：这告诉 AngularJS 执行引导（bootstrapping）的 DOM 元素位置。可以通过两种方式实现：

  1. 一个 `index.html` 文件，该文件还包含一个 HTML 元素（通常是 `<html>`），其具有 `ng-app`（AngularJS 指令）属性，该属性的值在 `app.js` 中给出的。AngularJS 指令以 `ng` (AngularJS) 为缀：`<html lang="en" ng-app="opts" class="no-js">`
  2. 或者，如果你是异步加载 JavaScript 文件，请使用此方法：`AngularJS.bootstrap(document.documentElement, ['otrsApp']);`

一个 AngularJS 模块有两个重要部分，`config()` 和 `run()`，除了控制器、服务、过滤器等组件外：

- `config()` 用于注册和配置模块，它只接受使用 `$injector` 的提供者（providers）和常量（constants）。`$injector` 是 AngularJS 服务。我们将在下一节介绍提供者和 `$injector`。你不能在此处使用实例。这防止了在完全配置之前使用服务。
- `run()` 用于在通过前面的 `config()` 方法创建 `$injector` 后执行代码。它只包含实例和常量。你不能在这里使用提供者，以避免在运行时进行配置。

## 提供者和服务

让我们来看下面的代码：

```
.controller('optsAppCtrl', function ($injector) {
  var log = $injector.get('$log');
```

`log` 是一个内置的 AngularJS 服务，提供日志 API。在这里，我们正在使用另一个内置服务 `$injector`，它允许我们使用 `$log` 服务。`$injector` 是控制器中的一个参数。AngularJS 使用函数定义和正则表达式向调用者（也称为控制器）提供 `$injector`。这些是 AngularJS 有效使用依赖注入模式的示例。

AngularJS 大量使用依赖注入模式，使用注入器服务（`$injector`）来实例化并接线我们在 AngularJS 应用中使用的大多数对象。该注入器创建两种类型的对象——服务和特殊对象。

为了简单起见，你可以说我们（开发者）定义了服务。相反，特殊对象是 AngularJS 的项，如控制器、过滤器、指令等。

AngularJS 提供了五种配方类型，告诉注入器如何创建服务对象——提供者（provider）、值（value）、工厂（factory）、服务和服务常量（constant）。

- 提供者是核心且最复杂的配方类型。其他配方是它的语法糖。除非我们需要创建需要全局配置的可重用代码，否则我们通常避免使用提供者。
- 值和常量配方类型正如其名。它们都不能有依赖。此外，它们之间的区别在于用法。我们不能在配置阶段使用服务对象。
- 工厂和服务是最常用的服务类型。它们属于相似的类型。当我们想要生成 JavaScript 原型和函数时，我们使用工厂配方。另一方面，当我们想要生成自定义类型时，则使用服务。

由于我们对服务有了一些了解，可以说服务有两种常见用途——组织代码和在应用程序之间共享代码。已经看到了一些内置的 AngularJS 服务，如 `$injector`、`$log` 等。AngularJS 服务以 `$` 符号为前缀。

## 作用域 (Scopes)

在 AngularJS 应用中，有两种作用域被广泛使用——`$rootScope` 和 `$scope`：

- `$rootScope` 是服务层次结构中的顶层对象，并关联全局作用域。这意味着你附加到它的任何变量都随处可用，因此，使用 `$rootScope` 应该是一个仔细考虑的决定。
- 控制器在回调函数中将 `$scope` 作为参数。它用于将数据从控制器绑定到视图。它的作用域限于它所关联的控制器。

## 控制器 (Controllers)

控制器由 JavaScript 构造函数定义，并带有 `$scope` 作为参数。控制器的主要目的是将数据绑定到视图。控制器函数还用于编写业务逻辑——设置 `$scope` 对象的初始状态并向 `$scope` 添加行为。控制器的签名看起来如下：

```
RestModule.controller('RestantsCtrl', function ($scope, restaurantService) {
```

在这里，控制器是 `RestModule` 的一部分，控制器的名称为 `RestaurantCtrl`，`$scope` 和 `restaurantService` 作为参数传递的。

## 过滤器 (Filters)

过滤器的作用是格式化给定表达式的值。在下面的代码中，我们定义了 `datetime` 过滤器，它接受日期作为参数并将值更改 `dd MMM yyyy HH:mm` 格式，例如 `04 Apr 2016 04:13 PM`：

```
.filter('datetime', function ($filter) {
  return function (argDateTime) {
    if (argDateTime) {
      return $filter('date') (new Date(argDateTime), 'dd MMM yyyy HH:mm a');
    }
    return ""
  }
};
```

## 指令 (Directives)

正如我们在模块部分看到的，AngularJS 指令是带有 `ng` 前缀的 HTML 属性。一些流行的指令有：

- `ng-app`: 此指令定义 AngularJS 应用
- `ng-model`: 此指令将 HTML 表单输入绑定到数据
- `ng-bind`: 此指令将数据绑定到 HTML 视图
- `ng-submit`: 此指令提交 HTML 表单
- `ng-repeat`: 此指令遍历集合：

```
<div ng-app="">
  <p>Search: <input type="text" ng-model="searchValue"></p>
  <p ng-bind="searchedTerm"></p>
</div>
```

## UI-Router

在单页应用 (SPA) 中，页面只加载一次，用户通过不同的链接进行刷新。这一切都是归功于路由（routing）。路由是让 SPA 导航感觉像正常网站的方法。因此，路由对于 SPA 非常重要。

AngularJS 团队构建了 UI-Router，这是一个 AngularJS 路由框架。UI-Router 不是 AngularJS 核心的一部分。UI-Router 只更改路由 URL，当用户点击 SPA 中的任何链接时，它还会更改应用程序的状态。由于 UI-Router 还可以创建状态，你可以在不更改 URL 的情况下更改页面视图。这是由于 UI-Router 对应用程序状态的管理。

如果我们把 SPA 比作状态机，状态就是应用程序的当前状态。在创建路由时，我们会在 link 标签中使用 `ui-sref` 属性。链接中的 `href` 属性将从该点生成，并指向 `app.js` 中创建的应用程序状态。

我们在 HTML div 中使用 `ui-view` 属性来使用 UI-Router。例如：

```
<div ui-view></div>
```

## OTRS 特性的开发

如你所知，我们正在开发 SPA。因此，一旦应用程序加载，你就可以在不刷新的情况下执行所有操作。与服务器的所有交互都是通过 AJAX 调用完成的。现在，我们将利用第一节介绍的 AngularJS 概念。我们将涵盖以下场景：

- 一个显示餐厅列表的页面。这将是我们的首页。
- 搜索餐厅。
- 带有预订选项的餐厅详情。
- 登录（不是来自服务器，但用于显示流程）。
- 预订确认。

# 使用微服务 Web 消费服务

在设计或实现首页之前，你一定会对查看它很感兴趣。因此，让我们先看看在内容准备就绪后它看起来会什么样：

| #id | 名称 | 地址 |
|---|---|---|
| 1 | Le Meource | 228 rue de Rivoli, 75001, Paris |
| 2 | L'Ambroisie | 9 place de Vosges, 75004, Paris |
| 3 | Arpège | 84, rue de Varenne, 75007, Paris |
| 4 | Alain Ducasse au Plaza Athénée | 25 avenue de Montaigne, 75008, Paris |
| 5 | Pavilion LeDenoyen | 1, avenue Dutull, 75008, Paris |
| 6 | Pierre Gagnayre | 6, rue Balzac, 75008, Paris |
| 7 | L'Astrance | 4, rue de Beethoven, 75016, Paris |
| 8 | Pre Catelan | Bois de Boulogne, 75016, Paris |
| 9 | Guy Savoy | 18 rue Troyon, 75017, Paris |
| 10 | Le Bristol | 112, rue du Faubourg St Honoré, 8th arrondissement, Paris |

现在，为了设计我们的首页，我们需要添加以下四个文件：

- `index.html`: 我们的主 HTML 文件
- `app.js`: 我们的主 AngularJS 模块
- `restaurants.js`: 餐厅模块，其中也包含餐厅 Angular 服务
- `restaurants.html`: 将显示餐厅列表的 HTML 模板

## index.html

首先，我们将 `/app/index.html` 添加到项目工作区。index.html 文件的内容从这里起将进行说明。

> 我在代码之间添加了注释，以便代码更具可读性并易于理解。

index.html 文件分为许多部分。我们在这里讨论其中的几个关键部分。首先，我们将看到如何处理旧版本的 Internet Explorer。如果你想针对大于 8 的 Internet Explorer 浏览器版本或 IE 9 及以后的版本，我们需要添加以下代码块，它将阻止 JavaScript 渲染并在末尾输出 `no-js`：

在添加了几个 meta 标签和应用程序标题后，我们还会定义重要的 meta 标签 `viewport`。viewport 用于响应式 UI。

`content` 属性中定义的 `width` 属性控制视口的大小。它可以被设置为特定的像素值，如 `width = 600`，也可以设置为特殊的 `device-width` 值，即 CSS 像素中 100% 比例下的屏幕宽度。

`initial-scale` 属性控制第一个页面加载时的缩放级别。`maximum-scale`、`minimum-scale` 和 `user-scalable` 属性控制用户如何放大或缩小页面：

```
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### 使用微服务 Web 消费服务

在接下来的几行中，我们将定义应用程序的样式表。我们从 HTML5 模板代码中添加 `normalize.css` 和 `main.css`。我们还添加了应用程序自定义 `app.css`。最后，我们添加了 Bootstrap 3 CSS。除了自定义的 `app.css`，其他 css 都在其中被引用。这些 CSS 文件中没有实际内容：

```
<link rel="stylesheet" href="bower_components/html5-boilerplate/dist/normalize.css">
<link rel="stylesheet" href="bower_components/html5-boilerplate/dist/main.css">
<link rel="stylesheet" href="public/css/app.css">
<link data-require="bootstrap-css@3" data-semver="3.0.0" rel="stylesheet" href="netmdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap.css">
```

然后，我们将定义 `script` 标签。我们还添加了 modernizer、Angular、Angular-route 以及 `app.js`（我们自己开发的自定义 JavaScript 文件）。我们已经讨论过 Angular 和 Angular-UI。`app.js` 将在节讨论。

modernizer 允许开发者使用新的 CSS3 和 HTML5 特性，同时对不支持这些特性的浏览器保持细粒度的控制。基本上，modernizer 在页面在浏览器加载时执行下一代特性检测（检查这些特性的可用性）并产生结果。基于这些，你可以检测浏览器中可用的最新特性，并据此为用户端提供界面。如果浏览器不支持某些特性，则为终端用户提供备用工作流或 UI。

我们还使用 `bootstrap-tpls` JavaScript 文件添加了用 JavaScript 编写的 Bootstrap 模板：



<script src="bower_components/html5-boilerplate/dist/vendor/modernizer-2.8.3.min.js"></script>
<script src="bower_components/angular/angular.min.js"></script>
<script src="bower_components/angular-route/angular-route.min.js"></script>
<script src="app.js"></script>
<script data-require="ui-bootstrap@0.5.0" data-semver="0.5.0" src="http://angular-ui.github.io/bootstrap/ui-bootstrap-tpls-0.6.0.js"></script>

# 使用微服务 Web 消费服务

## 第 8 章

```javascript
var $rootScope = $injector.get('$rootScope');
var log = $injector.get('$log');
var sessionStorage = $injector.get('$sessionStorage');
$scope.showSpinner = false;
```

/* 此函数在用户搜索任何餐厅时被调用。它使用了我们将在下一节中定义的 Angular 餐厅服务来搜索指定的搜索字符串。 */

```javascript
$scope.search = function () {
  $scope.restaurantService = restaurantService;
  restaurantService.async().then(function () {
    $scope.restaurants = restaurantService.search($scope.searchedValue);
  });
};
```

* 当状态改变时，新的控制器将根据视图和配置控制流程，而现有的控制器将被销毁。此函数在 destroy 事件时被调用。

```javascript
$scope.on('$destroy', function destroyed () {
  log.debug('otrAppCtrl destroyed');
  controller = null;
  $scope = null;
});

$scope.fromState;
$scope.fromStateParams;
$scope.on('$StateChangeSuccess', function (event, toState, fromState, fromStateParams) {
  $scope.fromState = fromState;
  $scope.fromStateParams = fromStateParams;
});
```

```javascript
// 工具方法
$scope.loggedIn = function () {
  if (sessionStorage.session) {
    return true;
  } else {
    return false;
  }
};
```

```javascript
/* spinner 状态 * */
$scope.isSpinnerShown = function () {
  return AjaxHandler.getSpinnerStatus();
};
```

# 使用微服务 Web 消费服务

```javascript
.run(['$rootScope', '$injector', '$state', function ($rootScope, $injector, $state) {
  $rootScope.restaurants = null;
  // 自引用
  var controller = this;
  // 注入外部引用
  var log = $injector.get('$log');
  var $sessionStorage = $injector.get('$sessionStorage');
  var AjaxHandler = $injector.get('AjaxHandler');

  if ($sessionStorage.currentUser) {
    $rootScope.currentUser = $sessionStorage.currentUser;
  } else {
    $rootScope.currentUser = "Guest";
    $sessionStorage.currentUser = "";
  }
}])
```

## restaurants.js

`restaurants.js` 代表了我们应用程序中的 Angular 服务，我们将用于处理餐厅。我们知道服务有两个常见用途：组织代码和在应用程序间共享代码。因此，我们创建了一个 `restaurants` 服务，它将用于搜索、列表等不同模块之间。

> 服务是单例对象，由 AngularJS 服务工厂懒性地实例化。

接下来的节节初始化了 `restaurants` 服务模块并加载了所需的依赖项：

```javascript
angular.module('otrsApp.restaurants', [
  'ui.router',
  'ui.bootstrap',
  'ngStorage',
  'ngResource'
])
```

# 使用微服务 Web 消费服务

在配置中，我们正在使用 UI-Router 定义 `otrApp.restaurants` 模块的路由和状态。

首先，我们通过传递一个 JSON 对象来定义 `restaurants` 状态，该对象包含了指向路由器 URI 的 URL、指向显示餐厅状态的 HTML 模板的 URL，以及处理餐厅视图上事件的控制器。

在餐厅视图（路由 - `/restaurants`）之上，还定义了一个嵌套的 `restaurants.profile` 状态，它将代表特定的餐厅。例如，`/restaurant/1` 将打开并显示由 Id 1 表示的餐厅的个人资料（详情）页。当在餐厅模板中点击链接时，会调用此状态。在 `ui-sref="restaurants.profile({id: rest.id})"` 中，代表从餐厅视图中获取的餐厅对象。

注意状态名称为 `'restaurants.profile'`，这告诉 AngularJS UI-Router 它是 `restaurants` 状态的嵌套状态：

```javascript
config({
  '$stateProvider', '$urlRouterProvider',
  function ($stateProvider, $urlRouterProvider) {
    $stateProvider.state('restaurants', {
      url: '/restaurants',
      templateUrl: 'restaurants/restaurants.html',
      controller: 'RestaurantsCtrl'
    });

    // 餐厅显示页
    .state('restaurants.profile', {
      url: '/:id',
      views: {
        '@': {
          templateUrl: 'restaurants/restaurant.html',
          controller: 'RestaurantCtrl'
        }
      }
    });
  });
})
```

在接下来的代码节中，我们使用 Angular 工厂服务类型定义餐厅服务。此餐厅服务通过 REST 调用从服务器获取餐厅列表。

```javascript
factory('restaurantService', function ($injector, $q) {
  var log = $injector.get('$log');
  var ajaxHandler = $injector.get('AjaxHandler');
```

```javascript
var deffered = $q.defer();
var restaurantService = {};
restaurantService.restaurants = {};
restaurantService.orignalRestaurants = [];
restaurantService.async = function () {
  ajaxHandler.startSpinner();
  if (restaurantService.restaurants.length === 0) {
    ajaxHandler.startSpinner();
    ajaxHandler.get('/api/restaurant',
      success(function (data, status, config) {
        log.debug('Getting restaurants');
        sessionStorage.isActive = true;
        log.debug('if restaurants' + restaurantService.length);
        if (restaurantService.restaurants.length < 1) {
          restaurantService.restaurants = [];
        }
        restaurantService.restaurants = data;
        ajaxHandler.stopSpinner();
        deferred.resolve();
      },
      error(function (error, status, headers) {
        if (restaurantService.restaurants.length < 1) {
          restaurantService.restaurants = [];
        }
        restaurantService.push({
          id: 104,
          name: ':sons - Chicago',
          address: '128 N. Rush St., Division, Chicago'
        });
        restaurantService.push({
          id: 105,
          name: 'ayayaysss',
          address: '33 W.. St., River North, Chicago'
        });
        ajaxHandler.stopSpinner();
        deferred.resolve();
      });
    return deferred.promise;
  } else {
    deferred.resolve();
  }
};
restaurantService.list = function () {
  return restaurantService;
};
restaurantService.add = function () {
  console.log("add");

  restaurant..push({
    id: 103,
    name: ' Noodles',
    address: '13 W. St., Eastern Park, Chicago'
  });
};
restaurantService.search = function (searchedValue) {
  ajaxHandler.startSpinner();
  if (!searchedValue) {
    ajaxHandler.get('/api/restaurant?' + searchedValue,
      success(function (data, status, config) {
        log.debug('Getting restaurants');
        sessionStorage.isActive = true;
        log.debug('if restaurants' + restaurantService.length);
        if (restaurantService.restaurants.length < 1) {
          restaurantService.restaurants = [];
        }
        restaurantService.restaurants = data;
        ajaxHandler.stopSpinner();
        deferred.resolve();
      },
      error(function (error, status, headers) {
        if (restaurantService.restaurants.length < 1) {
          restaurantService.restaurants = [];
        }
        restaurantService.push({
          id: 104,
          name: ':sons - Chicago',
          address: '128 N. Rush St., Division, Chicago'
        });
        restaurantService.push({
          id: 105,
          name: 'ayayays\'s',
          address: '33 W. St., River North, Chicago'
        });
        ajaxHandler.stopSpinner();
        deferred.resolve();
      });
    return deferred.promise;
  } else {
    deferred.resolve();
  }
};
```

# 使用微服务 Web 消费服务

## 第 8 章

```javascript
ajaxHandler.stopSpinner();
  deferred.resolve();
}

return deferred.promise;

}

return restaurantService;
))
```

在 `restaurants.js` 模块的下一节中，我们将为路由配置中定义的 `restaurants` 和 `restaurants.profile` 状态添加两个控制器。这两个控制器分别是 `RestaurantsCtrl` 和 `RestaurantCtrl`，分别处理 `restaurants` 状态和 `restaurants.` 状态。

`RestaurantsCtrl` 非常简单，它使用餐厅服务的列表加载餐厅数据：

```javascript
.controller('RestaurantsCtrl', function ($scope, restaurantService) {

  $scope.restaurantService = restaurantService;
  restaurantService.async().then(function () {
    $scope.restaurants = restaurantService.list();
  });
});
```

`RestaurantCtrl` 控制器负责显示给定 ID 的餐厅详情。它还负责对所显示的餐厅执行预订操作。当我们设计带有预订选项的餐厅页面时将使用此控制器：

```javascript
.controller('RestaurantCtrl', function ($scope, $state,
  $stateParams, $injector, restaurantService) {
  $scope.sessionStorage = $injector.get('$sessionStorage');
  $scope.format = 'dd MMMM yyy';
  $scope.today = $scope.dt = new Date();
  $scope.dateOptions = {
    formatYear: 'yy',
    maxDate: new Date().setDate($scope.today.getDate() + 180),
    minDate: $scope.today.getDate(),
    startingDay: 1
  };

  $scope.popup1 = {
    opened: false
  };
  $scope.altInputFormats = ['M/d/!yyyy'];
  $scope.open1 = function () {
});
```

## 使用微服务 Web 消费服务

```javascript
$scope.popup1.opened = true;

$scope.hstep = 1;
$scope.mstep = 30;
```



```javascript
if ($sessionStorage.reservationData) {
  $scope.restaurant = $sessionStorage.reservationData.restaurant;
  $scope.dt = new Date($sessionStorage.reservationData.tm);
  $scope.tm = $scope.dt;
} else {
  $scope.dt.setDate($scope.today.getDate() + 1);
  $scope.tm.setHours(19);
  $scope.tm.setMinutes(30);
  restaurantService.async().then(function () {
    angular.forEach(restaurantService.list, (value, key) => {
      if (value.id == parseInt(stateParams.id)) {
        $scope.restaurant = value;
      }
    });
  });
  $scope.book = function () {
    var tempHour = $scope.tm.getHours();
    var tempMinute = $scope.tm.getMinutes();
    $scope.tm = $scope.dt;
    $scope.tm.setHours(tempHour);
    $scope.tm.setMinutes(tempMinute);
    if ($sessionStorage.currentUser) {
      console.log("$scope.tm --> " + $scope.tm);
      alert("Booking Confirmed!!!");
      $sessionStorage.reservationData = null;
      $state.go("restaurants");
    } else {
      $sessionStorage.reservationData = {};
      $sessionStorage.reservationData.restaurant = $scope.restaurant;
    }
    $sessionStorage.reservationData.tm = $scope.tm;
    $state.go("login");
  };
}
```

## 使用微服务 Web 消费服务

我们还在 `restaurants.js` 模块中添加了一些过滤器用于格式化日期和时间。这些过滤器对输入数据执行以下格式化：

- **date1**：以 `dd MMM yyyy` 格式返回输入日期，例如：`13-Apr-2016`
- **time1**：以 `HH:mm:ss` 格式返回输入时间，例如：`11:55:04`
- **datetime1**：以 `dd MMM yyyy HH:mm:ss` 格式返回输入日期时间，例如：`13-Apr-2016 11:55:04`

在下面的代码段中，我们应用了这三个过滤器：

```javascript
.filter('date1', function ($filter) {
  return function (argDate) {
    if (argDate) {
      var d = $filter('date')(new Date(argDate), 'dd MMM yyyy');
      return d.toString();
    }
    return ""
  }
})
.filter('time1', function ($filter) {
  return function (argTime) {
    if (argTime) {
      return $filter('date')(new Date(argTime), 'HH:mm:ss');
    }
    return ""
  }
})
.filter('datetime1', function ($filter) {
  return function (argDateTime) {
    if (argDateTime) {
      return $filter('date')(new Date(argDateTime), 'dd MMM yyyy HH:mm a');
    }
    return ""
  }
});
```

### restaurants.html

我们需要为 `restaurants.profile` 状态添加定义的模板。如你所示，在模板中，我们使用 `ng-repeat` 指令来遍历由 `restaurantService.restaurants` 返回的对象列表。`restaurantService` 变量在控制器中定义。`RestaurantsCtrl` 与 `restaurants` 状态下的此模板相关联：

```html
<h3>巴黎著名的美食餐厅</h3>
<div class="row">
  <div class="col-md-12">
    <table class="table table-bordered table-striped">
      <thead>
        <tr>
          <th>#Id</th>
          <th>名称</th>
          <th>地址</th>
        </tr>
      </thead>
      <tbody>
        <tr ng-repeat="rest in restaurantService.restaurants">
          <td>{{rest.id}}</td>
          <td><a ui-sref="restaurants.profile({{rest.id}})">{{rest.name}}</a></td>
          <td>{{rest.address}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
```

### 搜索餐厅

在首页 `index.html` 中，我们在页眉部分添加了搜索表单，允许进行搜索。搜索功能将使用与之前相同的文件。它利用 `app.js`（搜索处理器）、`restaurants.js`（餐厅服务）和 `restaurants.html` 来显示记录：

| 在线表格系统 | C | 欢迎您！ |
| :--- | :--- | :--- |
| 巴黎著名的美食餐厅 | | #Id | 地址 |
| 104 | Gibsons - Chicago St. | 128 N. Rush St., Division, County, Paris |
| 105 | Harryay's Italian Steakhouse | 33 W. Kinzie St., River North, County, Paris |

### 带预订的餐厅详情

带预订的餐厅详情将是内容区域（页面中间部分）的一部分。顶部将包含一个指向列表页的面包屑导航，随后是餐厅的名称和地址。最后部分将包含预订日期时间选择框和一个预订按钮。

此页面将看起来如下截图所示：

![img/f551c3d57000fcdbbc126826d5af69e_235_0.png](img/f551c3d57000fcdbbc126826d5af69e_235_0.png)

在这里，我们将使用在 `restaurants.js` 中声明的相同餐厅服务。唯一的更改是如 `restaurants.profile` 状态所述的模板。此模板将使用 `restaurant.html` 定义。

### restaurant.html

如你所示，面包屑导航使用了通过 `ui-sref` 属性定义的路由。此模板定义的预订表单通过表单上的 `ng-submit` 调用控制器中定义的 `book()` 函数：

```html
<div class="row">
  <div class="col-md-12">
    <div class="breadcrumb">
      <ol class="breadcrumb">
        <li><a ui-sref="restaurants">餐厅</a></li>
        <li class="active">餐厅详情</li>
      </ol>
    </div>
  </div>
</div>
```

```html
<div class="row">
  <div class="col-md-12">
    <h1>{{restaurant.name}}</h1>
    <p>地址：{{restaurant.address}}</p>
    <form ng-submit="book()">
      <div class="form-group">
        <label>预订日期：</label>
        <input type="date" class="form-control" ng-model="dt">
      </div>
      <div class="form-group">
        <label>预订时间：</label>
        <input type="time" class="form-control" ng-model="tm">
      </div>
      <button type="submit" class="btn btn-primary">预订</button>
    </form>
  </div>
</div>
```

## 使用微服务 Web 消费服务

在控制器中，我们定义了取消（`cancel`）和提交（`submit`）操作，这些操作是从 `login.html` 模板中调用的：

```javascript
angular.module('otsrApp.login', [
  'ui.router',
  'ngStorage'
])
.config(function config($stateProvider) {
  $stateProvider.state('login', {
    url: '/login',
    controller: 'LoginCtrl',
    templateUrl: 'login/login.html'
  });
})
.controller('LoginCtrl', function ($state, $scope, $rootScope) {
  var $sessionStorage = $injector.get('$sessionStorage');
  if ($scope.current) {
    $scope.go($rootScope.fromStateParams());
  }
  var controller = this;
  var log = $injector.get('$log');
  var http = $injector.get('$http');

  $scope.on('$destroy', function destroyed() {
    log.debug("LoginCtrl destroyed");
    controller = null;
    $scope = null;
  });
  this.cancel = function () {
    $scope.dismiss();
    $scope.go('restaurants');
  };
  console.log("Current -- " + $state.current);
  this.submit = function (username, password) {
    $rootScope.currentUser = username;
    $sessionStorage.currentUser = username;
    if ($rootScope.fromState.name) {
      $scope.go($rootScope.fromStateParams());
    } else {
      $scope.go("restaurants");
    }
  };
});
```

### 预订确认

当用户登录并点击预订（Reservation）按钮后，餐厅控制器将显示带有确认信息的警示框，如下所示：

![带有预订确认的餐厅详情页](img/f551c3d57000fcdbbc1268267d5af69e_240_0.png)

### 设置 Web 应用

由于我们计划在 UI 应用开发中使用最新的技术栈，因此我们将使用 Node.js 和 npm（Node.js 包管理器），它们为开发服务器端 JavaScript Web 应用提供了开源运行时环境。

> **提示**：我建议至少过一遍这一部分。它将介绍 JavaScript 构建工具和技术栈。不过，如果你熟悉 JavaScript 构建工具或不想探索它们，可以跳过此部分。

Node.js 构建在 Chrome 的 V8 JavaScript 引擎之上，采用事件驱动、非阻塞 I/O，这使其既轻量又高效。Node.js 的默认包管理器 npm 是最大的开源库生态系统。它允许安装 Node.js 程序，并更方便地指定和链接依赖：

1. 首先，如果尚未安装 npm，则需要安装它。这是一个前提条件。你可以访问链接来安装 npm：<https://docs.npmjs.com/getting-started/installing-node>。
2. 要检查 npm 是否设置正确，请在 CLI 中执行 `npm -v` 命令。输出中应该返回已安装的 npm 版本。我们可以切换到 NetBeans，在 NetBeans 中创建一个新的 AngularJS JS HTML 项目。在编写本文时，我使用的是 NetBeans 8.1。
3. 导航到 **File（文件）** | **New Project（新建项目）**。应该会弹出一个新项目对话框。在 **Categories（类别）** 列表下选择 **HTML5/JavaScript**，并在 **Projects（项目）** 选项下选择 **HTML5/JS Application**，如下所示：

![NetBeans - 新的 HTML5/JavaScript 项目](img/f551c3d57000fcdbbc1268267d5af69e_241_0.png)

4. 点击 **Next（下一步）** 按钮。然后在 **Name and Location（名称和位置）** 对话框中输入 **Project Name（项目名称）**、**Project Location（项目位置）** 和 **Project Folder（项目文件夹）**，并点击 **Next** 按钮：

![NetBeans 新项目 - 名称和位置](img/f551c3d57000fcdbbc1268267d5af69e_242_0.png)

5. 在 **Site Template（站点模板）** 对话框中，在 **Download Online Template（在线下载模板）** 选项下选择 **AngularJS Seed** 项，并点击 **Next** 按钮。AngularJS Seed 项目地址为：<https://github.com/angular/angular-seed>：

![Site Template 对话框](img/f551c3d57000fcdbbc1268267d5af69e_243_0.png)

6. 在 **Tools（工具）** 对话框中，选择 **Create package.json**、**Create bower.json** 和 **Create gulpfile.js**。我们将使用 gulp 作为我们的构建工具。Gulp 和 Grunt 是 JS 最流行的两个构建框架。作为一名 Java 程序员，你可以将这些工具与 Ant 联系起来。它们在各自方面都很出色。如果你需要，也可以使用 Grunt。

![Tools 对话框](img/5551c3757000f121268267d5af69e_244_0.png)

7. 点击 **Finish（完成）** 后，可以看到 HTML5/JS 目录。目录结构如下：

![目录结构](img/f551c3d57000fcdbbc1268267d5af69e_245_0.png)

8. 检查是否配置正确，看到项目中的感叹号：

![检查配置](img/f551c3d57000fcdbbc1268267d5af69e_246_0.png)

9. 只要所有依赖都已正确配置，就会像所示：

![依赖配置完成](img/f551c3d57000fcdbbc1268267d5af69e_247_0.png)

10. 完成后，`package.json` 看起来如下：

```json
{
  "name": "otrs-ui",
  "private": true,
  "version": "1.0.0",
  "description": "Online Reservation",
  "main": "index.js",
  "license": "MIT",
  "dependencies": {
    "coffee-script": "^10.0",
    "del": "^1.1.1",
    "gulp-angular-templatecache": "^1.9.1",
    "gulp-clean": "^0.3.2",
    "gulp-connect": "^3.2.3",
    "gulp-file-include": "^0.13.7",
    "gulp-sass": "^2.3.2",
    "gulp-util": "^3.0.8",
    "run-sequence": "^1.2.2"
  }
}
```



# 使用微服务 Web 应用消费服务

## 第8 章

### 15. 接下来，我们将更新 `bower.json`，如下所示所示：

```json
{
  "name": "OTRS-UI",
  "description": "OTRS-UI",
  "version": "0.0.1",
  "license": "MIT",
  "private": true,
  "dependencies": {
    "AngularJS": "~1.5.0",
    "AngularJS-ui-router": "~0.2.18",
    "AngularJS-mock": "~1.5.0",
    "AngularJS-Bootstrap": "~1.2.1",
    "AngularJS-touch": "~1.5.0",
    "bootstrap-sass-official": "~3.3.6",
    "AngularJS-route": "~1.5.0",
    "AngularJS-loader": "~1.5.0",
    "ngstorage": "~0.3.10",
    "AngularJS-resource": "~1.5.0",
    "html5-boilerplate": "~5.2.0"
  }
}
```

### 16. 接下来，我们将修改 `.bowerrc` 文件，如代码所示，以指定 Bower 存储 `bower.json` 中定义组件的目录。我们将 Bower 组件存储在应用程序目录下：

```json
{
  "directory": "app/bower-components"
}
```

### 17. 接下来，我们将设置 `gulpfile.js`。我们将使用 CoffeeScript 来定义 gulp 任务。因此，我们只会在 `gulpfile.js` 中定义 CoffeeScript，而实际的任务将在 `gulpfile.coffee` 文件中定义。让我们看看 `gulpfile.js` 文件的内容：

```javascript
require('coffee-script/register');
require('./gulpfile.coffee');
```

### 18. 在这一步中，我们将定义 gulp 配置。我们使用 CoffeeScript 来定义 gulp 文件。用 CoffeeScript 编写的 gulp 文件名为 `gulpfile.coffee`。默认任务定义为 `default_sequence`：

```javascript
default_sequence = ['connect', 'build', 'watch']
```

## 使用微服务 Web 应用消费服务

让我们了解 `default_sequence` 任务执行了什么：

- 作为定义的 `default_sequence` 任务，它首先会连接到服务器，然后构建 Web 应用，并保持对更改的监听。监听功能将帮助渲染我们在代码中所做的更改，并立即显示在 UI 上。
- 该脚本中最重要的任务是 `connect` 和 `watch`。其他的任务自言易懂。所以，让我们深入研究它们。
- **gulp-connect**：这是一个用于运行 Web 服务器的 gulp 插件。它还允许热重载。
- **gulp-watch**：这是一个文件监听器，它使用 `chokidar` 并发射 vinyl 对象（描述文件——其路径和内容）。简单来说，我们可以说 `gulp-watch` 监视文件变化并触发任务。

`gulpfile.coffee` 看起来像这样：

```javascript
gulp               = require('gulp')
util               = require('gulp-util')
del                 = require('del')
clean              = require('gulp-clean')
connect            = require('gulp-connect')
fileinclude        = require('gulp-file-include')
runSequence = require('run-sequence')
templateCache      = require('gulp-AngularJS-templatecache')
sass               = require('gulp-sass')
```

```javascript
paths =
  scripts:
    src: ['/app/src/scripts/**/*.js']
    dest: ['public/scripts']
  scripts2:
    src: ['/app/src/views/**/*.js']
    dest: ['public/scripts']
  styles:
    src: ['/app/src/styles/**/*.scss']
    dest: ['public/styles']
  fonts:
    src: ['/app/src/fonts/**']
    dest: ['public/fonts']
  images:
    src: ['/app/src/images/**']
    dest: ['public/images']
  templates:
    src: ['/app/src/views/**/*.html']
    dest: ['public/scripts']
```

```javascript
html:
  src: ['/app/src/*.html']
  dest: 'public'
bowerbower:
  src: ['/app/bower_components/**/*']
  dest: 'public/bower_components'
```

### 将 bower 模块到 public 目录

```javascript
gulp.task('bower', ->
  gulp.src(paths.bower.src)
  pipe gulp.dest(paths.bower.dest)
  pipe connect.reload()
```

### 将脚本到 public 目录

```javascript
gulp.task('scripts', ->
  gulp.src(paths.scripts.src)
  pipe gulp.dest(paths.scripts.dest)
  pipe connect.reload()
```

### 将 scripts2 到 public 目录

```javascript
gulp.task('scripts2', ->
  gulp.src(paths.scripts2.src)
  pipe gulp.dest(paths.scripts2.dest)
  pipe connect.reload()
```

### 将样式到 public 目录

```javascript
gulp.task('styles', ->
  gulp.src(paths.styles.src)
  pipe sass()
  pipe gulp.dest(paths.styles.dest)
  pipe connect.reload()
```

### 将图片到 public 目录

```javascript
gulp.task('images', ->
  gulp.src(paths.images.src)
  pipe gulp.dest(paths.images.dest)
  pipe connect.reload()
```

### 将字体到 public 目录

```javascript
gulp.task('fonts', ->
  gulp.src(paths.fonts.src)
  pipe gulp.dest(paths.fonts.dest)
  pipe connect.reload()
```

### 将 html到 public 目录

```javascript
gulp.task('html', ->
  gulp.src(paths.html.src)
  pipe gulp.dest(paths.html.dest)
  pipe connect.reload()
```

### 将模板到 public 目录

```javascript
gulp.task('templates', ->
  gulp.src(paths.templates.src)
  pipe gulp.dest(paths.templates.dest)
  pipe connect.reload()
```

### 清理 public 目录

```javascript
gulp.task('clean', ->
  del([public]))
```

### 构建任务

```javascript
gulp.task('build', ->
  runSequence('clean', 'bower', 'scripts', 'scripts2', 'styles', 'images', 'fonts', 'html', 'templates'))
```

### 监听任务

```javascript
gulp.task('watch', ->
  gulp.watch(paths.scripts.src, ['scripts'])
  gulp.watch(paths.scripts2.src, ['scripts2'])
  gulp.watch(paths.styles.src, ['styles'])
  gulp.watch(paths.images.src, ['images'])
  gulp.watch(paths.fonts.src, ['fonts'])
  gulp.watch(paths.html.src, ['html'])
  gulp.watch(paths.templates.src, ['templates']))
```

### 默认任务

```javascript
gulp.task('default_sequence', ->
  runSequence('connect', 'build', 'watch'))
```



# 第 9 章：最佳实践与通用原则

在为获得开发微服务示例项目的经验而付出了大量努力之后，你可能在思考如何避免常见错误，并改进基于微服务的产品和服务的整体流程。我们可以遵循这些原则或指南来简化微服务的开发过程，并避免/减少潜在的局限性。在本章中，我们将关注这些核心概念。

本章分为以下三个部分：

- 概述与心态
- 最佳实践与原则
- 微服务框架与工具

## 概述与心态

你可以在新产品和现有产品和服务上实现基于微服务的设计。与人们认为的从零开始开发和设计新系统比对已运行的现有系统进行修改更容易的观点相反，每种方法都有各自的挑战和优势。

## 最佳实践与通用原则

例如，由于新产品或服务没有现有的系统设计，你拥有设计系统的自由和灵活性，而无需考虑其影响。然而，你对新系统的功能和系统需求并不完全清晰，因为这些需求会随着时间的推移而成熟并成型。另一方面，对于成熟的产品和服务，你已经掌握了功能和系统需求的详细知识和信息。尽管如此，你面临着减轻设计变更给微服务带来影响风险的挑战。因此，当将生产系统从单体更新为微服务时，你需要进行比从零构建系统时更完善的规划。

经验丰富的软件设计专家和架构师总是会评估优劣，并在对现有运行系统进行任何更改时采取谨慎的方法。不应该因为某些可能很酷或流行就对现有系统进行更改。因此，如果你想将现有生产系统的设计更新为微服务，你需要在决定之前评估所有的优劣。

我相信单体系统为升级到成功的基于微服务的设计提供了一个很好的平台。显然，我们在这里不讨论这种情况。你对现有系统和功能非常了解，这让你能够根据功能以及它们相互作用的方式拆分现有系统并构建微服务。此外，如果你的单体产品已经以某种方式实现了模块化，通过暴露 `API` 而不是应用程序二进制接口（`ABI`）直接转换为微服务可能是实现微服务架构最简单的方法。一个成功的微服务系统比任何东西都更依赖于微服务及其交互协议。

话虽如此，并不意味着如果你从零开始就能拥有一个成功的微服务系统。建议基于单体设计启动新项目，这让你对系统和功能有一个视角和理解。它允许你快速找到瓶颈，并引导你识别任何可以使用微服务开发的潜在功能。在这里，我们还没有讨论项目的规模，这是另一个重要因素。我们将在下一节讨论这一点。

在当今的云时代和敏捷开发世界，从做出任何更改到更改上线需要一小时的时间。在当今的竞争环境中，每个组织都希望拥有快速向用户交付功能的优势。持续开发、集成和部署是生产交付过程的一部分，这是一个完全自动化的过程。

如果你提供云产品或服务，这样更有意义。这时，基于微服务的系统使团队能够敏捷地响应，修复任何问题或为用户提供新功能。

因此，在你决定从零开始启动新的基于微服务的项目，或计划将现有单体系统的设计升级为基于微服务的系统之前，你需要评估所有的优劣。你必须听取并理解团队中分享的不同观点和视角，并且需要采取谨慎的方法。

最后，我想分享对于一个成功的生产系统来说，拥有良好的流程和高效系统的重要性。拥有基于微服务的系统并不保证拥有成功的生产系统，而单体应用并不意味着你现在无法拥有一个成功的生产系统。`Netflix`（一个基于微服务的系统）、基于微服务的视频租赁服务以及 `Etsy`（一个单体电子商务平台）都是成功的例子。因此，流程和敏捷性对于生产系统也是关键。

## 微服务、规模与单体

你项目中的每个微服务在规模上应该是很小的，并且能够独立地执行某个功能或特性。

以下是来自 `Mike Gancarz`（`X Window` 系统的设计者）的两句引言，他定义了 `Unix` 哲学的最高原则之一，这同样适用于微服务范式：

> “小即是美。”
>
> “让每个程序只做好一件事。”

现在，在当今时代，我们如何根据代码量（`LOC`）定义规模，特别是当你有一个框架（例如 `Finagle`）来定义它时？此外，许多现代语言（如 `Python` 和 `Erlang`）非常简洁。这使得决定是否想要让这些代码成为微服务变得困难。

显然，你可能为了少量的代码实现一个微服务；这实际上并不是一个微服务。

`Arnon Rotem-Gal-Oz` 将微服务定义为一种反模式：

> “微服务是一种粒度过细的反模式。微服务是指其开销（通信、维护等）超过了它的效用。”

因此，根据功能设计微服务总是有意义的。领域驱动设计使得在领域层面定义功能变得更容易。

正如之前提到的，项目规模是决定是否实现微服务或确定你想要的微服务数量的关键因素。在一个简单的小型项目中，例如基于我们在第三章中学到的领域驱动设计（`DDD`），你将对自己的功能需求有一个清晰的理解，并有助于你在这各种功能或特性之间划分边界。例如，在我们实现的示例项目（在线预留系统 `OTRS`）中，使用单体设计开发项目非常容易，只要你不想向客户暴露 `API`，或者你不想将其作为 `SaaS` 使用，或者在决定之前有许多想要评估的类似模式。

关注上述几点可以减轻你在迁移到微服务时可能遇到的任何困难。

通常情况下，由于前面的章节讨论了微服务所提供的许多优势，大型或复杂的项目应该使用基于微服务的架构进行开发。

我甚至建议将你的初始项目作为单体架构（`monolithic`）开发；一旦你对项目功能和复杂性有了更好的理解，就可以将其迁移到微服务。理想情况下，开发出的初始原型应该为你提供功能边界，使你能够做出正确的选择。

## 持续集成与部署

你必须建立一套持续集成和部署流程。它能让你获得更快速地交付变更并尽早发现 `Bug` 的优势。因此，每个服务都应该有自己的集成和部署流程。此外，它必须是自动化的。目前有很多可用工具，如 `Teamcity`、`Jenkins` 等，被广泛使用。它可以帮助你自动化构建过程——从而及早发现构建问题，特别是当你将更改集成到主干分支（如发布分支/标签或 `master` 分支）时。

你还可以将测试集成到每个自动化的集成和部署过程中。集成测试测试系统不同部分之间的交互，例如两个接口之间（`API` 提供者和消费者之间），或者系统中不同组件或模块之间（例如 `DAO` 和数据库之间等）。集成测试非常重要，因为它测试了模块之间的接口。单个模块首先进行隔离测试。然后进行集成测试，以检查组合行为并验证需求是否正确实现。因此，在微服务中，集成测试是验证 `API` 的关键工具。我们将在下一节中介绍更多内容。

最后，你可以在部署构建的 `CD`（持续部署）机器上看到更新后的主干变更。

流程并在此处结束：你可以制作一个容器（如 `Docker`）并交给你的 `WebOps` 团队，或者通过一个独立的流程交付到配置的位置或部署到 `WebOps` 阶段环境。从这里开始，一旦获得指定的批准，可以直接部署到你的生产系统。

## 产品和服务交付的系统/端到端部分

测试是任何产品和服务交付中非常重要的一部分。你不想向客户交付带有 `Bug` 的应用程序。在瀑布模型流行的早期，组织在交付给客户之前的测试阶段通常需要 1 到 6 个月甚至更久。近年来随着敏捷流程的流行，人们更加强调自动化。与之前的测试类似，自动化也是强制性的。

无论你是否遵循测试驱动开发（`TDD`），我们都必须建立系统或端到端的测试自动化。测试你的业务场景非常重要，端到端测试也是如此，它可能从你的 `REST` 调用到数据库检查，或从 `UI` 到数据库检查。

此外，如果你有公共 `API`，那么测试你的 `API` 也是重要的。

这样做可以确保任何更改都不会破坏任何功能，并确保生产环境交付的无缝且无 `Bug`。正如上一节所讨论的，每个模块都使用单元测试进行隔离测试，以检查一切运行情况是否符合预期，然后在不同模块之间进行集成测试，以检查预期行为并验证需求（无论实现是否正确）。在集成测试之后，会执行功能测试，以验证功能和特性需求。

因此，如果单元测试确保了单个模块在隔离状态下工作，那么集成测试确保了不同模块之间的交互符合预期。如果单元测试运行良好，意味着集成测试失败的变更风险将大大降低。同样，集成测试确保了功能测试很可能会成功。

> 假设人们始终保持所有类型的测试更新，无论是单元级测试还是端到端测试场景。

## 自监控与日志记录

微服务应该提供关于自身以及它所依赖的各种资源状态的信息。服务信息代表统计数据，例如处理请求的平均时间、最小时间和最大、成功和失败请求的数量、可追踪性、内存占用等。

`Adrian Cockcroft` 在 2015 年的 `Glue Con` 大会上强调了几项对于监控微服务非常重要的实践。其中大多数都适用于任何监控系统：

- 花更多时间在编写收集、移动、存储和显示指标的代码上。这不仅有助于提高生产力，还能为微调微服务和提高系统效率提供重要参数。其理念是开发更多的分析工具，而不是开发更多的工具。
- 显示延迟的指标需要小于人类的注意力范围。根据 `Adrian` 的说法，这意味着少于 10 秒。
- 验证你的测量系统具有足够的准确性。收集响应时间的直方图。
- 准确的数据使决策更快，并允许你不断微调直到达到精度水平。他还建议显示响应时间的最佳图表是直方图。
- 监控系统比被监控的系统具有更高的可用性和扩展性。
- 这句话说明了一切：你不能依赖一个本身不稳定或无法 24/7 可用的系统。
- 针对分布式、瞬态、云原生、容器化的微服务进行优化。
- 将指标拟合模型以理解它们的关系。

监控是微服务架构的核心组件。根据项目规模，你可能有几十个到数千个微服务（对于大企业的大型项目如此）。即使为了扩展和高可用，组织为每个微服务创建了集群或负载均衡池/`pod`，甚至为每个版本的微服务创建了池。最终，这增加了你需要的资源数量……建立一个流程是重要的，这样每当出现问题时，你都能立即获知。`Netflix` 使用工具进行监控，如 `Netflix Atlas`、`Security Monkey`（基于 `AWS` 环境的安全）、`Scumblr`（信息收集工具）以及 `FIDO`（用于事件报告）。

### 日志记录

日志记录是微服务的另一个重要方面，不应被忽视。有效的日志意味着一切。由于可能有 10 个或更多微服务，管理日志是一项巨大的任务。

在我们的示例项目中，使用了映射诊断上下文（`MDC`）日志，这对于单个微服务的日志是足够的。然而，我们需要整个系统的日志。我们需要聚合统计。有很多工具可以完成这项工作，如 `Loggly` 或 `Logspout`。

一个请求和生成的事件提供了该请求的整体视图。为了跟踪任何事件和请求，重要的是将事件和请求分别关联服务 `ID`。你还可以将事件的内容（如消息、严重性、类名等）关联到服务 `ID`。

![](img/f551c3d57000fcdbbc1268267d5af69e_264_0.png)

## 每个微服务的独立数据库

如果你记得，微服务最重要的特征之一是微服务与其他微服务隔离运行，最常见的是作为应用程序。

遵循这一规则，建议不要在多个微服务之间共享同一个数据库或其他任何数据存储。在大型项目中，你可能有不同的团队在同一个项目上工作，你希望为每个微服务选择最适合该微服务的数据库。

现在，这也带来了一些挑战。

例如，以下内容对于在同一个项目内工作不同微服务的团队是相关的，如果该项目共享相同的数据库结构。存在其中一个微服务的更改可能会影响另一个微服务的模型。在这种情况下，一个服务的更改可能会影响依赖的微服务，因此你也需要更改依赖的模型结构。

同样，由于数据存储的不同，实际项目数据也分布在多个数据存储中，这使得数据管理变得更加复杂，因为独立的存储系统很容易不同步或变得不一致，且外键可能会发生变化。为了解决此类问题，你需要使用主数据管理（`MDM`）。`MDM` 工具在后台运行，并发现任何不一致之处。对于示例来说，它可能会检查每个存储订单请求 `ID` 的数据库，以验证相同的 `ID` 是否存在于所有数据库（换句话说，任何数据库中都没有缺失或额外的 `ID`）。市场上现有的 `MDM` 工具包括 `Informatica`、`IBM MDM Advance Edition`、`Oracle Siebel UCM`、`Postgres`（主备复制）、`mariadb`（主主配置）等。

如果现有产品中都不符合你的需求，或者你对专用产品不感兴趣，那么你可以编写自己的。具体来说，`API` 驱动开发和平台减少了这种复杂性；因此，微服务应该使用 `API` 平台进行开发，这是重要的。

## 事务边界

我们在第 3 章《领域驱动设计》中学习了领域驱动设计的概念。如果你还没有完全掌握，请回顾该章节，因为它能让你对状态有纵向的理解。由于我们专注于基于微服务的设计，结果是我们拥有一个系统，每个微服务都代表一个系统。在这种环境中，在任何给定时间寻找整个系统的状态是非常挑战性的。如果你熟悉分布式应用程序，那么在状态方面你可能会在这种环境下游刃有余。

建立事务边界是非常重要的，它描述了在任何给定时间哪个微服务拥有某条消息。你需要一种能够参与事务、路由选择、错误处理器、幂等消费者和补偿操作的方法或过程。要确保异构系统跨实现事务行为并非易事，但有许多工具可以为你完成这项工作。

例如，`Camel` 具有出色的事务能力，可以帮助开发者轻松创建具有事务行为的服务。

## 微服务框架与工具

总是比重造轮子要好。因此，我们希望探索已经有了哪些工具，并提供使微服务开发和部署变得更简单的平台、框架和特性。

在整本书中，我们大量使用了 `Spring Cloud`，原因相同：它提供了使微服务开发变得非常容易的所有工具和平台。`Spring Cloud` 使用了 `Netflix` 开源软件（`OSS`）——这是一个完整的包。

我还添加了关于每个工具如何帮助构建良好的微服务架构的简要概述。

## Netflix 开源软件 (OSS)

`Netflix OSS` 中心是基于 `Java` 的微服务项目最流行、最广泛开源软件。世界上最成功的视频租赁服务依赖于它。`Netflix` 拥有超过 4000 万用户并在全球范围内使用。`Netflix` 是一个纯云的解决方案，基于微服务架构开发。`Netflix` 是人们想到的第一个名字。让我们讨论一下它提供的各种工具。我们在设计示例 `OTRS` 应用时已经讨论了其中许多工具。然而，还有几个我们还没有探索。在这里，我们将仅涵盖每个工具的概述，而不是深入细节。它将让你对微服务架构的实际特性及其在云中的应用有一个整体概念。

### 构建 - Nebula

`Netflix Nebula` 是 `Gradle` 插件的集合，它使用 `Gradle` 这种类似于 `Maven` 的构建工具让你的微服务构建变得更简单。对于我们的示例项目，我们使用了 `Maven`，因此在书中没有机会探索 `Nebula`。然而，探索它会很有趣。对于开发者来说，`Nebula` 最显著的特性是消除 `Gradle` 构建文件中的样板代码，让开发者能够专注于编码。

一个良好的构建环境，尤其是 `CI/CD`（持续集成和持续部署），对于微服务开发和保持敏捷开发一致是必不可少的。`Netflix Nebula` 让你的构建更加简单和高效。

### 部署与交付 - 带有 Aminator 的 Spinnaker

一旦构建完成，你就想将构建移动到 `Amazon Web Services (AWS) EC2`。`Aminator` 创建并以 `Amazon Machine Image (AMI)` 的形式打包构建镜像。`Spinnaker` 将这些 `AMIs` 部署到 `AWS`。

`Spinnaker` 是一个持续交付平台，用于以高速度和效率发布代码更改。`Spinnaker` 还支持其他云服务，例如 `Google Compute Engine` 和 `Cloud Foundry`。

如果你想将最新的微服务构建部署到如 `EC2` 等云环境，`Spinnaker` 和 `Aminator` 可以帮助你以自主的方式完成。

### 服务注册与发现 - Eureka

正如我们在书中所探索的那样，`Eureka` 提供了一个负责微服务注册和发现的服务。此外，`Eureka` 还用于中间层（托管不同微服务的进程）的负载均衡。`Netflix` 也使用 `Eureka` 配合 `Cassandra` 或 `memcached` 等其他工具来增强其整体可用性。

服务注册与发现是微服务架构的必需。`Eureka` 正承担了此目的。关于 `Eureka` 的更多信息，请参考第 4 章“实现微服务”。

### 服务通信 - Ribbon

如果没有进程间或服务间的通信，微服务架构将毫无用处。`Ribbon` 应用提供了这一功能。`Ribbon` 与 `Eureka` 配合进行负载均衡，与 `Hystrix` 配合进行故障允许或断路器操作。

除了 `HTTP`，`Ribbon` 还支持 `TCP` 和 `UDP` 协议。它在异步和响应模型中提供了这些协议支持。它提供了缓存和批量处理能力。

> 由于项目中会有微服务，你需要一种处理进程间或服务通信的方法。`Ribbon` 提供了这一点。

### 断路器 - Hystrix

`Hystrix` 是一个用于故障容忍或断路器操作延迟的工具。`Hystrix` 防止级联故障。

> 一个微服务的故障不应导致你的整个系统停止；防止这一点并提供有用信息是 `Hystrix` 的工作。

### 边缘（代理）服务器 - Zuul

`Zuul` 是边缘服务器或代理服务器，为 `UI` 客户端、`Android/iOS` 应用或任何第三方 `API` 消费者服务。从概念上说，它是外部应用的门。`Zuul` 允许对请求进行动态路由和监控。它还对每个资源执行安全操作，如身份验证。

> 你的微服务需要一个边缘服务器或 `API` 网关。`Zuul` 提供了这一点。更多信息请参考第 5 章“部署与测试”。

### 运行监控 - Atlas

`Atlas` 是一个运行监控工具，提供关于维度时间序列数据的近实时信息。它捕获运行智能，提供了系统内部正在发生情况的快照。它具有内存数据存储特性，能够非常快速地收集和报告大量指标。目前，`Netflix` 有 13 亿个指标。

`Atlas` 是一个可扩展的工具。这就是为什么它现在可以处理 13 亿个指标，而几年前只有 100 万个。`Atlas` 不仅在读取数据方面提供可扩展性，还作为请求的一部分进行聚合。

`Atlas` 使用 `Netflix Spectator` 库记录维度时间序列数据。

> 一旦你在云环境中部署了微服务，你就需要一个监控系统来跟踪和监控所有微服务。`Netflix Atlas` 为你完成这一切。

### 可用性监控服务 - Simian Army

在云中，没有单一组件可以保证 100% 的可用性。因此，成功的微服务架构要求在单个云组件故障时整个系统仍然可用。`Netflix` 开发了一个名为 `Simian Army` 的工具来避免系统故障。`Simian Army` 保持云环境的安全、可靠和高可用。为了实现高可用性和安全性，它在云中使用各种服务（猴子）来产生各种故障、检测异常情况，并测试云生存这些挑战的能力。

它使用了以下服务（猴子），取自 `Netflix` 博客：

- **混沌猴子 (`Chaos Monkey`)**：`Chaos Monkey` 是识别系统组并随机终止组中的一个系统的服务。该服务在控制的时间和间隔内运行，目的是让工程师能够保持警觉并做出响应。
- **清道夫猴子 (`Janitor Monkey`)**：`Janitor Monkey` 是一个运行在 `AWS` 云端的服务，用于查找并清理未使用的资源。它可以扩展以支持其他云提供商和云资源。服务的调度是可配置的。`Janitor Monkey` 通过对资源应用一套规则来确定该资源是否为清理候选对象。如果任何规则确定该资源是清理候选对象，`Janitor Monkey` 会标记该资源并设定清理时间。对于特殊情况，当你想更久地保留未使用的资源时，在 `Janitor Monkey` 删除资源之前，资源所有者将在清理时间前收到配置天数的通知。
- **一致性猴子 (`Conformity Monkey`)**：`Conformity Monkey` 是一个运行在 `AWS` 云端的服务，用于查找不符合最佳实践定义的实例。它可以扩展以支持其他云提供商和云资源。服务的调度是可配置的。如果任何规则确定实例不符合规定，该猴将向实例所有者发送电子邮件通知。可能存在特殊情况，你希望忽略某些应用程序特定符合性规则的警告。
- **安全猴子 (`Security Monkey`)**：`Security Monkey` 监控策略变化并对 `AWS` 账户中的不安全配置发出警报。`Security Monkey` 的主要目的是安全，尽管它本质上是一个变更跟踪系统，也被证明是追踪潜在问题的有用工具。

成功的资源架构可以确保你的系统始终可用，单个云组件的失败不应导致整个系统的故障。`Simian Army` 使用许多服务来实现高可用性。

### AWS 资源监控 - Edda

在云环境中，没有任何是静态的。例如，虚拟主机实例频繁变化，`IP` 地址可能会被各种应用程序重用，或者可能会发生防火墙或相关的变更。

`Edda` 是一个跟踪这些动态 `AWS` 资源的服务。`Netflix` 将该服务命名为 `Edda`（意为北欧神话中的传说），因为它记录了云管理和部署的故事。`Edda` 使用 `AWS API` 轮询 `AWS` 资源并记录结果。这些记录允许你搜索并查看云随时间发生的变化。例如，如果任何 `API` 服务器导致了任何问题，你需要找出是哪个主机出了问题以及由哪个团队负责。

这些是它提供的功能：

- **动态查询**：`Edda` 提供 `REST API`，并支持矩阵参数，提供字段选择器，允许你只检索所需的数据。
- **历史/更改**：`Edda` 维护所有 `AWS` 资源的历史记录。这些信息在你分析停机原因和影响时很有帮助。`Edda` 还可以提供有关资源的当前和历史信息的视图。在编写时，它将信息存储在 `MongoDB` 中。
- **配置**：`Edda` 支持许多配置选项。通常，你可以从多个账户和多个区域轮询信息，可以使用账户和区域端点的组合。同样，它为 `AWS`、`Crawler`、`Elector` 和 `MongoDB` 提供了不同的配置。

如果你正在使用 `AWS` 托管你的基于微服务的产品，`Edda` 发挥了监控 `AWS` 资源的作用。

### 主机性能监控 - Vector

`Vector` 是一个静态 `Web` 应用程序，运行在浏览器内部。这允许它监控安装了 **Performance Co-Pilot (`PCP`)** 的主机性能。`Vector` 支持 `PCP 3.10+` 版本。`PCP` 收集指标并供 `Vector` 使用。

它提供了按需获取的高分辨率真实指标。这有助于工程师理解系统行为并正确排查性能问题。

> `Vector` 是一个监控工具，帮助你监控远程主机的性能。

### 分布式配置管理 - Archaius

`Archaius` 是一个分布式配置管理工具，允许你执行以下操作：

- 使用动态类型属性。
- 执行线程安全的配置操作。
- 使用轮询框架检查属性更改。
- 在有序的配置层次结构中使用回调机制。
- 使用 `JConsole` 检查并对属性执行操作，因为 `Archaius` 提供 `JMX MBean`。
- 当你有基于微服务的产品时，需要良好的配置管理工具。`Archaius` 帮助在分布式环境中配置不同类型的属性。

### Apache Mesos 调度器 - Fenzo

`Fenzo` 是一个用 `Java` 编写的 `Apache Mesos` 框架调度器库。`Apache Mesos` 框架匹配并将资源分配给待处理的任务。以下是它的关键特性：

- 它支持长时间运行的服务型任务和批处理任务
- 它根据资源需求自动扩展执行主机集群。
- 它支持你可以根据需求创建的插件
- 你可以监控资源分配失败，允许你调试根源。

### 成本与云利用率 - Ice

`Ice` 从成本和使用的角度提供云资源的视角。它提供了有关分配给不同团队的配置云资源分配的最新信息，为优化云资源利用增加了价值。

`Ice` 是一个里程碑项目。用户与 `UI` 组件交互，显示通过 `Ice` 读取组件发送的信息。读取器从 `Ice` 处理器组件生成的数据获取信息。`Ice` 处理器组件从详细的云账单文件中读取数据信息，并转换为 `Ice` 读取组件可读的数据。

### 其他安全工具 - Scumblr 和 FIDO

除了 `Security Monkey`，`Netflix OSS` 还使用了 `Scumblr` 和全集成防御操作 (`FIDO`) 工具。

为了跟踪并保护你的微服务免受常规威胁和攻击，你需要自动化方法来保护和监控微服务。`Netflix Scumblr` 和 `FIDO` 为完成这项工作。

#### Scumblr

`Scumblr` 是一个基于 `Ruby on Rails` 的 `Web` 应用程序，允许你执行定期搜索并对识别出的结果进行存储/采取行动。基本上，它收集利用全网定向搜索的智能，以暴露安全问题。

`Scumblr` 利用 `Workflowable gem` 来为不同类型的结果设置灵活的工作流。`Scumblr` 利用称为 `Search Providers` 的插件。它检查以下异常。由于它是可扩展的，你可以根据需要添加任意：

- 泄露的凭据
- 漏洞/黑客讨论
- 攻击讨论
- 安全相关的社交媒体讨论

#### 全集成防御操作 (FIDO)

`FIDO` 是一个用于分析事件和自动化事件响应的安全编排框架。它通过评估、判断和响应恶意软件来自动化事件响应过程。`FIDO` 的主要目的是处理评估来自当今安全栈威胁所需的大量手动工作，以及它们产生的大量警报。

作为一个编排平台，`FIDO` 可以让使用现有的安全工具更加高效，并大幅减少检测、通知和响应攻击所需的人工工作。有关更多信息，你可以参考以下链接：

- <https://github.com/Netflix/Fido>
- <https://github.com/Netflix>

## 参考文献

- 单体 (`Etsy`) 对比 微服务 (`Netflix`) `Twitter` 讨论：<https://twitter.com/adriano/status/441169921863860225>
- `Adrian Cockcroft` 关于监控微服务和容器的演示：<http://www.slideshare.net/adriancockcroft/gluecon-monitoring-microservices-and-containers>
- 微服务反模式：<https://arnon.me/2014/03/services-microservices/>
- 用于微服务架构的 `Apache Camel`：<https://www.javocodegeeks.com/2014/09/apache-camel-for-micro%C2%ADservice-architectures.html>
- `Teamcity`：<https://www.jetbrains.com/teamcity/>
- `Jenkins`：<https://jenkins-ci.org/>
- `Loggly`：<https://www.loggly.com/>

## 总结

在本章中，我们探索了最适用于基于微服务的产品和服务的各种实践和原则。微服务架构是云环境的结果，与基于本地的单体系统相比被广泛使用。我们确定了一些与规模、敏捷性和测试相关的原则，这些原则对于成功实施必须到位。

我们概述了 `Netflix OSS` 用于成功实现基于微服务架构的产品和服务的各种功能所需的不同工具。`Netflix` 成功地使用相同的工具提供视频租赁服务。

在下一章中，读者可能会遇到问题并可能卡在这些问题上。该章将解释开发微服务期间遇到的常见问题及其解决方案。

# 第 10 章：故障排除指南

我们已经走过了很远，我相信你正享受这段充满挑战且快乐的学习之旅中的每一个时刻。我不会说这本书在这一章之后就结束了，而是说你正在完成第一个里程碑。这一里程碑为在云中学习和实现基于微服务设计的新范式开启了大门。我想重申，集成测试是测试微服务与 `API` 之间交互的重要方法。在开发你的示例应用程序**在线预订系统 (`OTRS`)** 期间，我相信你已经面临了许多挑战，特别是在调试应用程序时。在这里，我们将介绍一些可以帮助你排查部署的应用、`Docker` 容器和宿主机问题的实践和工具。

本章涵盖了以下三个主题：

- 日志与 `ELK` 栈
- 使用 `Zipkin` 和 `Sleuth` 通过相关 `ID` 进行服务调用
- 依赖关系与版本

## 日志与 ELK 栈

你能想象一下在不看生产系统日志的情况下如何调试任何问题吗？简单来说，因为很难回溯过去。因此，我们需要日志。如果日志的设计和编码得当，它们还能为系统提供警报信号。日志记录和日志分析是排查任何问题的重要步骤，也是吞吐量、容量以及监控系统健康状况的关键。因此，拥有一个非常好的日志平台和策略将实现有效的调试。日志记录是软件开发初期最重要的组件之一。

微服务通常使用 `Docker` 等镜像容器进行部署，这些容器提供了命令帮助你读取容器内部署服务的日志。`Docker` 和 `Docker Compose` 提供了命令来分别流式输出容器以及所有容器内运行服务的日志。请参考以下 `Docker` 和 `Docker Compose` 的日志命令：

### Docker logs 命令

```



Usage: `docker logs [OPTIONS] <CONTAINER NAME>`

获取容器的日志：

- `-f, --follow` 持续跟踪日志输出
- `--help` 打印用法
- `--since=""` 显示自某个时间戳的日志
- `-t, --timestamps` 显示时间戳
- `--tail="all"` 从日志末尾显示的行数

![](img/f551c3d57000fcdbbc1268267d5af69e_276_0.png)

## Docker-compose logs 命令

```
Usage: docker-compose logs [options] [SERVICE...]
```

选项：

- `--no-color` 生成单色输出
- `-f, --follow` 持续跟踪日志输出
- `-t, --timestamps` 显示时间戳
- `--tail` 从每个容器末尾显示的行数
- `[SERVICES...]` 代表容器的服务 - 你可以提供多个

这些命令帮助你探索运行在容器内部的微服务和其他的日志。如你所见，当你有较多数量的服务时，上述命令将是一项具有挑战性的任务。例如，如果你有几十或上百个微服务，跟踪每个微服务的日志将是非常困难的。同样，你可以想象，即使没有容器，单独监控日志会有多么困难。因此，你可以假设探索和关联数十到数百个容器日志的难度有多大。这是非常耗时的，而且增加的价值很小。

因此，日志聚合器和可视化工具（如 ELK 栈）成了我们的救星。它将用于集中日志记录。我们将在下一节中探讨这一点。

# 故障排除指南
## 第 10 章

### 简述

Elasticsearch, Logstash, Kibana (ELK) 栈是一系列执行日志聚合、分析、可视化和监控的工具链。ELK 栈提供了一个完整的日志平台，允许你分析、可视化和监控你所有的日志，包括所有类型的产品日志和系统日志。如果你已经了解了 ELK 栈，请跳到下一节。在这里，我们将对 ELK 栈中的每个工具进行简要介绍：

![](img/f551c3d57000fcdbbc1268267d5af69e_277_0.png)

### Elasticsearch

Elasticsearch 是最受欢迎的企业级全文搜索引擎之一。它是开源软件。它是可分发的并支持多租户。单个 Elasticsearch 服务器存储多个索引（每个索引代表一个数据库），单个查询可以搜索多个索引的数据。它是一个分布式搜索引擎并支持集群。

它可以很容易地扩展，并能提供延迟为 1 秒的近实时搜索。它是使用 Java 和 Apache Lucene 开发的。Apache Lucene 是免费开源的，它提供了 Elasticsearch 的核心，也称为信息检索库。

Elasticsearch API 本质上非常广泛且非常详尽。Elasticsearch 提供了基于 JSON 的模式、更少的存储，并用 JSON 表示数据模型。Elasticsearch API 使用 JSON 文档进行 HTTP 请求和响应。

### Logstash

Logstash 是一个具有实时流水线能力的开源数据收集引擎。简单来说，它收集、解析、处理并存储数据。由于 Logstash 具有数据流水线能力，它可以帮助你处理来自各种系统的任何事件数据，例如日志。Logstash 作为代理运行，收集数据、对其进行解析、过滤，并将输出发送到指定的应用（例如 Elasticsearch）或控制台上的简单标准输出。

它还有一个非常好的插件生态系统（图像源自 www.elastic.co）：

![](img/f551c3d57000fcdbbc1268267d5af69e_278_0.png)

### Kibana

Kibana 是一个基于浏览器的 Web 应用程序，旨在与 Elasticsearch 配合工作。它允许你搜索、可视化和与 Elasticsearch 中的数据交互。它是一个分析应用程序，可以制作图表、表格和地图。

### ELK 设置

通常，这些工具被安装并配置为相互通信。

#### 安装 Elasticsearch

要安装 Elasticsearch，我们可以使用镜像：

```
docker pull docker.elastic.co/elasticsearch:5.5.1
```

我们也可以通过以下步骤安装 Elasticsearch：

1. 从 https://www.elastic.co/downloads 下载 Elasticsearch 发行版。
2. 解压到系统的目标位置。
3. 确保安装了最新版本的 Java 并设置了 `JAVA_HOME` 环境变量。
4. 进入 Elasticsearch 目录，在 Unix 上运行 `bin/elasticsearch`，在 Windows 上运行 `bin/elasticsearch.bat`。
5. 打开任何浏览器访问 `http://localhost:9200/`。安装成功后它应该为你提供类似下面的 JSON 对象：

```json
{
  "name": " ",
  "cluster_name": "elasticsearch",
  "version": {
    "number": "2.3.1",
    "build_hash": "bd98092901aef407cb0843e616269",
    "build_timestamp": "2016-04-04T12:25:02Z",
    "build_snapshot": false,
    "lucene_version": "5.5.0"
  },
  "tagline": "You Know, for Search"
}
```

#### 安装 Logstash

要安装 Logstash，我们可以使用镜像：

```
docker pull docker.elastic.co/logstash/logstash:5.5.1
```

我们也可以通过执行以下步骤安装 Logstash：

1. 从 https://www.elastic.co/downloads/logstash 下载最新版本的 Logstash 发行版。
2. 解压到系统的目标位置。
3. 准备一个配置文件。它指示 Logstash 从给定文件读取输入并传递给 Elasticsearch（参见下面的配置文件；Elasticsearch 由 localhost 和 9200 端口表示）。这是一个简单的配置文件。要添加过滤器并了解更多关于 Logstash 的信息，你可以探索 https://www.elastic.co/guide/logstash/current/index.html 中的 Logstash 参考文档：

```
input {
  ### OTRS ###
  file {
    path => "\logs\otrs-service.log"
    type => "otrs-api"
    codec => "json"
    start_position => "beginning"
  }
}
```

如你所见，OTRS 服务日志和边缘服务器日志被作为输入添加。同样，你也可以添加其他微服务的日志文件。

```
file {
  path => "/logs/edge-server.log"
  type => "edge-server"
  codec => "json"
}

output {
  stdout {
    codec => rubydebug
  }
  elasticsearch {
    hosts => "localhost:9200"
  }
}
```

3. 进入 Logstash 根目录，在 Unix 类系统上运行 `bin/logstash agent -f logstash.conf`，在 Windows 上运行 `bin/logstash.bat agent -f logstash.conf`。在这里，Logstash 使用 agent 命令执行。Logstash agent 从配置文件中输入字段中提供的源中收集数据，并将输出发送到 Elasticsearch。在这里，我们没有使用过滤器（filters），因为否则可能会在将数据提供给 Elasticsearch 之前对其进行处理。

同样，你也可以使用下载的 Docker 镜像运行 Logstash（稍后，我们将使用 docker-compose 一起运行 ELK 栈）。

#### 安装 Kibana

要安装 Kibana，我们可以使用 Kibana Docker 镜像：

```
docker pull docker.elastic.co/kibana/kibana:5.5.1
```

我们也可以通过执行以下步骤安装 Kibana Web 应用：

1. 从 https://www.elastic.co/downloads/kibana 下载最新版本的 Kibana 发行版。
2. 将其解压到系统中的指定位置。
3. 找到并打开 Kibana 根目录下的配置文件 `config/kibana.yml`，并将 `elasticsearch.url` 指向之前配置的搜索实例：

```
elasticsearch.url: "http://localhost:9200"
```

4. 进入 Kibana 根目录，在 Unix 类系统上运行 `bin/kibana`，在 Windows 上运行 `bin/kibana.bat`。
5. 如果你使用的是 Kibana Docker 镜像，则可以运行该 Docker 镜像（稍后，我们将使用 docker-compose 一起运行 ELK 栈）。
6. 现在，你可以通过浏览器使用 URL `http://localhost:5601/` 访问 Kibana 应用。要了解更多关于 Kibana 的信息，请浏览 Kibana 参考文档 https://www.elastic.co/guide/kibana/current/getting-started.html。

由于我们遵循了前面的步骤，你可能已经注意到如果你想进行手动设置，是需要一些精力的。你可以将其 Docker 化。如果你不想费精力创建 ELK 栈的 Docker 容器，可以从 Docker Hub 中选择一个。在 Docker Hub 上，有很多现成的 ELK 栈 Docker 镜像。你可以尝试不同的 ELK 容器并选择适合你的一个，`docker/elk` 是负载最高的容器，且启动简单，与 Docker Compose 配合良好。

### 使用 Docker Compose 运行 ELK 栈

elastic.co 的 Docker 仓库中提供的 ELK 镜像在编写本节时已启用了 XPack 包。在将来，这可能是可选的。根据 ELK 镜像中 XPack 的可用性，你可以修改 `docker-compose-elk.yml` 文件：

```yaml
version: '2'

services:
  elasticsearch:
    image: docker.elastic.co/elasticsearch/elasticsearch:5.5.1
    ports:
      - "9200:9200"
      - "9300:9300"
    environment:
      ES_JAVA_OPTS: "-Xmx256m -Xms256m"
      xpack.security.enabled: "false"
      xpack.monitoring.enabled: "false"
    # 以下是运行开发模式所需的。对于生产模式，请删除它们，并且 vm_max_map_count 内核设置需要至少设置为 262144
    http.host: "0.0.0.0"
    transport.host: "127.0.0.1"
    networks:
      - elk

  logstash:
    image: docker.elastic.co/logstash/logstash:5.5.1
    volumes:
      - ~/pipeline:/usr/share/logstash
    # windows 手动复制到 docker cp pipeline/logstash.conf <container_id>:/usr/share/logstash/ restart container after
    ports:
      - "5001:5001"
    environment:
      LS_JAVA_OPTS: "-Xms256m -Xms256m"
      xpack.monitoring.enabled: "false"
      xpack.monitoring.url: "http://192.168.99.100:9200"
    command: logstash -e 'input { tcp { port => 5001 codec => "json" } } output { elasticsearch { hosts => "192.168.99.100" index => "mm" } }'
    networks:
      - elk
    depends_on:
      - elasticsearch

  kibana:
    image: docker.elastic.co/kibana/kibana:5.5.1
    ports:
      - "5601:5601"
    environment:
      xpack.security.enabled: "false"
      xpack.reporting.enabled: "false"
      xpack.monitoring.enabled: "false"
    networks:
      - elk
    depends_on:
      - elasticsearch

networks:
  elk:
    driver: bridge
```

一旦保存了 ELK Docker Compose 文件，可以使用以下命令运行 ELK 栈（在包含 Docker Compose 文件的目录下）：

```
docker-compose -f docker-compose-elk.yml up -d
```

上述命令的输出如下：

```
$ docker-compose up -d
Creating network_default with "bridge"
Creating elasticsearch_1 ...
Creating logstash_1 ...
Creating kibana_1 ...

$ docker-compose ps
Name                Command                  Ports
elasticsearch_1    /usr/bin/elasticsearch  up  0.0.0.0:9200/tcp,0.0.0.0:9300/tcp
logstash_1         /usr/local/bin/logstash  up  0.0.0.0:5001/tcp
kibana_1           /usr/local/bin/kibana      up  0.0.0.0:5601/tcp
```

#### 使用 Docker 运行 ELK 栈

如果不使用 volume（卷），对于像 Windows 等难以配置卷的环境，你可以将 pipeline 文件复制到容器内部并重启 Logstash 容器：

```
docker cp pipeline/logstash.conf <container_id>:/usr/share/logstash/pipeline
```

复制 pipeline 文件后重启 Logstash 容器：

```
input {
  tcp {
    port => 5001
    codec => "json"
  }
}

output {
  elasticsearch {
    hosts => "elasticsearch:9200"
  }
}
```

### 推送日志到 ELK 栈

我们现在让 ELK 栈可用。现在 Logstash 只需要由 Elasticsearch 索引的日志流。一旦创建 Elasticsearch，就可以在 Kibana 面板上访问并处理日志。

为了将日志推送到 Logstash，我们需要对服务代码进行以下更改。我们需要在服务中添加 logback 和 logstash-logback 依赖。

在 `pom.xml` 文件中添加以下依赖项：

```xml
...
<dependency>
  <groupId>net.logstash.logback</groupId>
  <artifactId>logstash-logback-encoder</artifactId>
  <version>4.6</version>
</dependency>
<dependency>
  <groupId>ch.qos.logback</groupId>
  <artifactId>logstash-core</artifactId>
  <version>1.1.9</version>
</dependency>
...
```

我们需要通过向 `src/main/resources` 添加 `logback.xml` 来配置 logback。

`logback.xml` 文件看起来如下：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <appender name="stash"
```



```xml
<appender name="stash" class="net.logstash.logback.LogstashSocketAppender">
  <destination>192.168.99.100:5001</destination>
  <!-- encoder is required -->
  <encoder class="net.logstash.logback.encoder.LogstashEncoder" />
  <keepAliveDuration>5 minutes</keepAliveDuration>
</appender>

<appender name="stdout" class="ch.qos.logback.ConsoleAppender">
  <encoder>
    <pattern>%d{HH:mm:ss.SSS} [%thread] %X(X-B3-TraceId),%X(X-B3-SpanId) - %msg%n</pattern>
  </encoder>
</appender>

<property name="spring.application.name" value="nameService" scope="context"/>

<root level="INFO">
  <appender-ref ref="stash" />
  <appender-ref ref="stdout" />
</root>

<shutdownHook class="ch.qos.logback.core.hook.DelayingShutdownHook"/>
</configuration>
```

# 故障排除指南

## 第 10 章

在这里，目标是 `192.168.99.100:5001`，Logstash 托管在此；你可以根据你的配置进行更改。对于 encoder，使用了 `net.logstash.logback.encoder.LogstashEncoder` 类。`spring.application.name` 属性的值应设置为所配置的服务。同样，添加了停机钩子，以便在服务停止时释放并清理所有资源。

你希望在 ELK 栈可用后启动服务，以便服务能够将日志推送到 Logstash。

一旦 ELK 栈和服务已启动，你可以检查 ELK 栈以查看日志。你需要在启动 ELK 栈后等待几分钟，然后访问以下 URL（根据你的配置替换 IP）。

要检查 Elasticsearch 是否启动，访问以下 URL：

```
http://192.168.99.100:9200/
```

要检查是否创建了索引，访问以下 URL 之一：

```
http://192.168.99.100:9200/_cat/indices/
http://192.168.99.100:9200/_aliases/pretty
```

## 服务调用中使用相关性 ID（correlation ID）

当你对任何 REST 端点进行调用时，如果弹出任何错误，很难追溯该问题及其根源，因为每次调用都是向服务器发起的，而该调用可能会调用另一个，以此类推。这使得非常难以确定是哪个特定请求被转换了以及它被称为什么什么。通常情况下，由一个服务引起的问题会对其他服务产生多米诺效应，或者导致服务操作失败。追踪这非常困难，并且可能耗费大量的精力。如果是单体架构，你知道你查找的方向是正确的，但微服务会让你难以理解问题的源头以及你应该从哪里获取数据。

## 让我们看看如何解决这个问题

通过使用跨越所有调用的相关性 ID，允许你轻松地跟踪每个请求并追踪其路由。每个请求都将有一个唯一的相关性 ID。因此，当我们调试任何问题时，相关性 ID 是我们的起点。我们可以顺着它，并在此过程中发现哪里出了问题。

相关性 ID 需要一些额外的开发工作，但从长远来看，这些努力是值得的，因为它非常有帮助。当请求在不同的微服务之间传输时，你将能够看到所有的交互以及哪个服务出现了问题。

这不是微服务的新事物或专门发明的。这种模式已被许多如 Microsoft SharePoint 等这样的流行产品使用。

## 使用 Zipkin 和 Sleuth 进行追踪

对于 OTRS 应用，我们将利用 Zipkin 和 Sleuth 进行追踪。它提供了追踪 ID（trace IDs）、跨度 ID（span IDs）以及一个用于追踪请求良好的 UI。更重要的是，你可以在 Zipkin 中找到每个请求花费的时间，它允许你深入分析以找到处理请求耗时最长的请求。

### 故障排除指南

#### 第 10 章

在下面的截图，你可以看到餐厅 `findById` API 调用所花费的时间，以及同一请求的追踪 ID。它还显示了跨度 ID：

![](img/f551c3d57000fcdbbc1268267d5af69e_288_0.png)

我们将遵循以下步骤在 OTRS 服务中配置 Zipkin 和 Sleuth。

只需要添加 Sleuth 和 Sleuth-Zipkin 依赖项来启用追踪和请求追踪：

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-sleuth</artifactId>
</dependency>

<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-sleuth-zipkin</artifactId>
</dependency>
```

访问 Zipkin 仪表板并查看不同请求花费的时间。如果更改了默认端口，请替换端口。请确保在在使用 Zipkin 之前服务已启动：

```
http://<zipkin host name>:9411/zipkin/
```



## 故障排除指南

### 第 10 章

现在，如果 ELK 栈已配置并运行，那么你就可以使用此 ID 在 Kibana 中找到相应的日志，如下幅截图所示。Kibana 中可以找到 `X-B3-TraceId` 字段，该字段用于通过追踪 ID 查找日志：

![](img/f551c3d57000fcdbbc1268267d5af69e_289_0.png)

## 依赖和版本

我们在产品开发中面临两个常见问题是循环依赖和 API 版本。我们将从微服务架构的角度来讨论它们。

## 循环依赖及其影响

通常，单体架构是典型的分层模型，而微服务带有图模型特征。因此，微服务可能会有依赖循环依赖。

因此，有必要检查微服务之间的关系。

## 故障排除指南

### 第 10 章

让我们来看这两个情况：

- 如果你的微服务之间存在依赖循环，那么当某个事务可能卡在循环中时，你就会受到分布式栈溢出错误。例如，当餐厅桌位被某人预订时。在这种情况下，餐厅需要知道那人 (`findBookedUser`)，而那人在给定时间需要知道餐厅。如果设计得不好，这些服务可能会在循环中相互调用。结果可能是由 JVM 生成的栈溢出。
- 如果两个服务共享一个依赖，并且你更新另一个服务的 API 的方式可能会影响到它们，那么你需要同时更新所有三个。这引出了诸许多问题，例如，你应该先更新吗？此外，你如何进行这种安全过渡？

## 在设计系统时分析依赖

因此，在设计微服务时，在不同服务内部建立适当的关系非常重要，以避免任何循环依赖。这是一个设计问题，如果需要重构代码，则必须解决。

## 维护不同的版本

当你有更多服务时，意味着每个服务都有不同的发布周期，这通过引入服务的不同版本增加了复杂性，即同一个服务的多个版本。在旧版本中复现问题将变得非常困难。

## 让我们探索更多

API 版本控制很重要，因为随着时间的推移，API 会发生变化。你的知识经验随着时间增长，这导致了 API 的变化。更改 API 可能会破坏现有的集成。

## 故障排除指南

### 第 10 章

因此，有多种方法管理 API 版本。其中一种是我们在书中使用路径中的版本；有些也使用 HTTP 头。HTTP 头可以是自定义请求头，或者你可以使用 `Accept` 头来表示调用 API。有关如何使用 HTTP 头处理版本的更多信息，请参考 Bhakti Mehta 写的《RESTful Java Patterns and Best Practices》：
https://www.packpub.com/application-development/restful-java-patterns-and-best-practices.

在排查任何问题时，确保你的微服务实现为产生版本号是非常重要的。理想情况下，你应该避免出现任何过多微服务的实例。

## 参考文献

以下将将更多信息：

- Elasticsearch: https://www.elastic.co/products/elasticsearch
- Logstash: https://www.elastic.co/products/logstash
- Kibana: https://www.elastic.co/products/kibana
- willdurand/elk: elk

## 总结

在本章中，我们探索了 ELK 栈的概述和安装。在 ELK 栈中，Elasticsearch 用于存储来自 Kibana 的日志和查询查询。Logstash 是运行在你想要收集日志的服务器上的代理。Logstash 读取日志，对其进行过滤/转换，并提供给 Elasticsearch。Kibana 从 Elasticsearch 读取数据并以表格或图形可视化的形式呈现。

# 将单体应用迁移到基于微服务的应用

## 第 11 章

## 你需要迁移吗？

这是应该为你的迁移定基调的第一个问题。你真的需要将应用程序迁移到微服务架构吗？它能带来什么好处？后果是什么？我们如何支持现有客户？现有客户是否会支持并承担迁移到微服务的成本？我需要从头开始编写代码吗？数据将如何迁移到新的微服务系统？迁移的时间表是怎样的？现有团队是否足够熟练以快速实现这一变化？我们可以在迁移过程中接受新的功能变更吗？我们的流程能够适应迁移吗？诸此类推。我相信你的脑海中会产生很多类似的问题。我希望通过之前的所有章节，你可能已经对微服务系统所需的工作有了良好的了解。

在权衡所有优缺点之后，你的团队将决定是否迁移。如果答案是肯定的，本章将帮助你迈向迁移的道路。

## 云端、本地化以及云混合

你目前提供的方案是云端解决方案、本地化解决方案，还是你想同时提供云端和本地化解决方案？或者你想在提供本地化解决方案的同时开始提供云端服务？你的方法将取决于你提供的解决方案类型。

## 仅云端解决方案

如果你提供云端解决方案，那么你的迁移任务比另外两种要简单。尽管如此，这并不意味着它会轻而易举。你对迁移拥有完全的控制权。你可以不考虑迁移对客户的直接影响。云客户只需使用解决方案，而不会被实现或托管方式所困扰。我假设没有 API 或 SDK 的变化，显然，迁移不应涉及任何功能变更。仅在云端进行微服务迁移具有使用平滑增量迁移的优势。这意味着你首先转换 UI 应用，然后是一个一个 API/服务，然后是下一个，以此此类推。记住，控制权掌握在你手中。

## 仅本地化解决方案

本地化解决方案部署在客户的基础设施上。此外，你可能有很多客户在他们的基础设施上部署了不同的版本。你对这些部署没有完全控制权。你需要与客户合作，并且需要团队努力才能成功迁移。

此外，在接触客户之前，你应该准备好完善的迁移方案。产品的多个版本使得这变得额外困难。我建议提供最新版本的迁移，而在你开发迁移期间，只允许客户进行安全修复和破坏性修复。是的，你不应该提供新功能。

## 云端和本地化解决方案

如果你的应用程序既提供云端也提供本地化，那么本地化解决方案向微服务的迁移可以与云端同步进行，或者反之亦然。这意味着如果你投入精力迁移其中一个，可以在另一个上复制相同的操作。因此，它包含了之前提到的针对云端或本地化迁移的变更，并增加了在其他环境上的复制。此外，有时本地化客户可能有他们自己的定制内容。在迁移时也需要考虑这些这一点。在这里，你自己的云端解决方案应该先迁移到微服务，稍后可以复制到本地。

迁移仅在本地化部署的生产/解决方案，但你又想开始云端部署；这是最具挑战性的。你必须按照我的服务设计来迁移现有代码，确保它也支持现有的本地化部署。有时，它可能是旧的技术栈，甚至现有代码可能是使用某些专有技术（如协议）编写的。设计可能不够灵活，无法拆分为微服务。这种类型的迁移带来的挑战最大。应该对本地化解决方案进行微服务化的增量迁移，其中你可以分离 UI 应用并提供与 UI 应用交互的外部 API。如果 API 已经到位，或者你的应用程序已经拆分为独立的 UI 应用，相信我，这消除了迁移过程中的大量负担。然后，你可以专注于迁移服务器代码，包括为 UI 应用开发的 API。你可能会问，为什么我们不能同时迁移所有的 UI 应用、API 和服务器代码。是的，你可以这样做。但进行增量开发会带给你确定性、信心以及快速的失败/学习。毕竟，敏捷开发的核心就在于增量开发。

## 将单体应用迁移到基于微服务的应用

如果你的现有代码不是模块化的，或者包含大量的旧代码，我建议你对其进行重构并使其模块化。这会让你的任务变得更容易。尽管如此，应该按模块进行。在迁移到纯微服务之前，尽可能拆分并重构你能重构的代码。

我们将讨论几种可能帮助你将大型复杂的单体应用重构为微服务的方法。

## 成功迁移的方法和关键点

软件现代化已经做了多年。为了实现成功的软件现代化，付出了大量工作。你会发现回顾所有成功软件现代化（迁移）的最佳实践和原则将很有帮助。在本章中，我们将专门讨论微服务架构的软件现代化。

## 增量迁移

你应该以增量的方式将单体应用转换为微服务。你不应该一次性开始对整个代码进行全面的迁移。这会干扰风险收益比，并增加失败的概率。它还会增加转换时间，从而增加成本。你可能想将代码拆分为不同的模块，并逐一个转换每个模块。很有可能你可能想从头重写几个模块，如果现有代码紧密耦合且复杂到无法重构，那么是应该重写的。但从头开始编写整个解决方案是大忌。你应该避免这样做。它会增加迁移的成本、时间以及失败的概率。

## 流程自动化和工具搭建

敏捷方法与微服务相得益彰。你可以使用任何敏捷流程（如 Scrum 和看板）结合现代开发流程（如测试驱动开发或结对编程）来完成增量开发。流程自动化适用于基于微服务的环境。你应该建立自动的 CI/CD 和测试自动化。如果 CI/CD 流水线尚未完成交付物的容器化，那么你应该这样做。它能够实现新开发的微服务与现有或其他或其他微服务的集成。

你可能希望在开始第一次微服务转换之前，或并行设置服务发现、服务网关、配置服务器或基于事件的系统。

## 试点项目

我在微服务迁移中观察到的另一个问题是完全从不同的模块开始开发。理想情况下，一个小型团队应该执行试点项目，将任何一个现有模块转换为微服务。一旦成功，这种方法就可以复制到其他模块。如果你同时开始迁移各种模块，那么你可能会在所有微服务中重复同样的错误。这增加了失败的风险和转换的持续时间。

执行成功迁移的团队为开发模块及其与现有单体应用的成功集成提供了路径。

## 独立用户界面应用程序

如果你已经拥有了调用 API 的独立用户界面应用程序，那么你离成功迁移只有一步了。如果不是如此，第一步应该是将用户界面与服务器代码分离。UI 应用将调用 API。如果现有应用程序没有 UI 应用应该调用的 API，那么你应该在现有代码之上编写封装 API。

## 将单体应用迁移到基于微服务的应用

查看下图，该图反映了 UI 应用迁移之前的表示层：

![](img/f551c3d57000fcdbbc1268267d5af69e_298_0.png)

下方的图反映了 UI 应用迁移后的表示层：

![](img/f551c3d57000fcdbbc1268267d5af69e_298_1.png)

你可以看到，在此之前，UI 与业务逻辑和 DAO 一起包含在单体应用内部。迁移后，UI 应用从单体应用中分离出来，并通过消费 API 与服务器代码进行通信。REST 是在现有代码之上实现 API 的标准。

## 将模块迁移到微服务

现在，你有一个服务器端单体应用和一个或多个 UI 应用。这为你带给你一个优势：在将模块从现有单体应用中分离的同时，可以消费 API。例如，在分离 UI 应用后，你可能将其中一个模块转换为微服务。一旦 UI 应用通过测试，与该模块相关的 API 调用就可以路由到新转换的模块，而不是单体 API。如网图所示，当调用 `API GET/customer/1` 时，网关可以将请求路由到客户微服务，而不是单体应用。

在创建新的基于微服务的 API 之前，你也可以在生产环境中进行测试，通过比较来自单体模块和微服务模块的响应。一旦我们获得了了一致匹配的响应，就可以确定转换已成功完成，API 调用可以迁移到重构后的模块 API。如下图所示，部署了一个组件，它在被调用时会对新的客户 API 发起另一个调用。然后，它会比较两次调用的响应并存储结果。这些结果可以进行分析，并对任何不一致之处提供修复方案。当新转换微服务的响应与现有的单体响应匹配时，你就可以停止将调用路由到现有单体应用，并用新的微服务替换它。

遵循这种方法允许你逐个将模块迁移到微服务，并在某个时间点，你可以将所有单体模块迁移到微服务。

![](img/f551c3d57000fcdbbc1268267d5af69e_299_0.png)

## 在迁移期间如何适应新功能

在理想情况下，迁移期间应避免引入新功能。只允许进行重要的修复和安全更改。然而，如果迫切需要实现新功能，则应该在独立的微服务中开发，或者以模块化的方式在现有单体代码中开发，使其更容易从现有代码中分离。

例如，如果你确实需要客户模块中的一个新功能，你可以简单地创建一个新的客户微服务，并通过外部世界或其他模块使用它进行特定的 API 调用。使用 REST 调用还是用于进程间通信取决于你。

同样，如果你需要一个依赖于其他模块的新功能（例如，一个依赖于预订的新功能），并且它没有作为 API 向 UI 或服务 API 暴露，那么它仍然可以作为独立的微服务进行开发，如下图所示。客户模块调用新开发的微服务，然后调用预订模块进行请求处理，并将响应返回给客户模块。在这里，进程间通信可以使用 REST 或事件。

![](img/f551c3d57000fcdbbc1268267d5af69e_300_0.png)

实现一个调用另一个模块的新模块作为微服务

## 参考文献

阅读以下书籍以获取更多关于代码重构和领域驱动设计的信息：

- Martin Fowler 著的 *Refactoring: Improving the Design of Existing Code*
- Eric J. Evans 著的 *Domain-Driven Design*

## 总结

软件现代化是当前环境下前进的道路，因为一切都已移动到云端，资源力量和容量增加的方式发生了变化，基于设计的微服务看起来比其他任何都要都合适。我们讨论了云端和本地解决方案的结合，以及将这些转换为微服务的挑战。对于从单体应用到微服务，我们还讨论了增量方法。我们还谈论了成功迁移所需的各种实践。

# 索引

## A

- 高级消息队列 (AMQP) 126
- 聚合根 (aggregate root) 65
- Amazon 机器 (AMI) 253
- 亚马逊云服务 (AWS) 253
- Angular UI 242
- Angular 框架 242
- 控制器 (controllers) 202
- 指令 (directives) 203
- 过滤器 (filters) 202
- 模型-视图-控制器 (MVC) 198
- 模型-视图-模型 (MVVM) 198
- 模块 (modules) 199
- 概述 (overview) 198
- 提供者和 own (providers and services) 200
- 范围 (scopes) 201
- Apache Avro 156
- Apache Kafka 156
- API 网关 (API Gateway) 210
- 应用程序接口 (ABI) 244
- 应用构建 (application build) 48
- 使用 Java 执行 (executing, with Java) 47
- 设置 (setting up) 47
- 成功的迁移方法 (approaches, successful migration) 282
- 增量迁移 (incremental migration) 282
- 模块迁移到微服务 (modules, migrating to microservices) 285
- 新功能的适应 (new functionality, accommodating) 286
- 流程自动化 (process automation) 283
- 独立接口 (standalone interface) 283
- 工具设置 (tools setup) 283
- Archaius 257
- DDD 产物 (artifacts, DDD) 61
- 聚合根 (aggregates) 65
- 实体 (entities) 68
- 工厂 (factory) 70
- 存储库 (repository) 67
- 服务 (services) 67
- 值对象 (VOs) 62
- Atlas 258
- 身份验证 (authentication) 162
- 授权 (authorization) 162
- Avro 256

## B

- 证书机构 (certificate authority) 159
- 混沌猴 (Chaos Monkey) 255
- 熔路器设计 (circuit breaker design) 122

## C

- OAuth 2.0 (client, OAuth 2.0) 168
- 原生应用 (native application) 170
- 基于代理的应用程序 (user agent-based application) 169
- Web 应用程序 (web application) 168
- OAuth 2.0 (client, OAuth 2.0) 171
- 机密客户端类型 (confidential client type) 167
- 标识符 (identifier) 171
- 配置文件 (profiles) 168
- 公共客户端类型 (public client type) 167

- 微服务架构最佳实践 (best practices, microservice-based architecture) 245
- 持续集成与部署 (continuous integration and deployment) 247
- 单体 (monolithic) 246
- 微服务 (nanoservice) 245
- 自我监控与日志 (self-monitoring and logging) 248
- 微服务的独立数据存储 (separate data store, for microservice) 250
- 尺寸 (size) 245
- 系统/端端测试自动化 (system/end-end test automation) 248

- 云解决方案 (cloud solution) 280
- 与本地解决方案 (versus on-premise solution) 280
- 通用名称 (common name) 161
- 一致猴 (Conformity Monkey) 256
- 容器 (containers) 18
- 用于部署 (used, for deployment) 17
- 用于微服务部署 (used, for microservice deployment) 131
- 内容 (content map) 72
- 反腐层 (anticruption layer) 75
- 客户-供应商模式 (customer-supplier pattern) 74
- 提炼 (distillation) 76
- 开放主机服务 (open host service) 76
- 分离模式 (separate ways pattern) 75
- 共享内核 (shared kernel) 73
- 关联 ID (correlation ID) 273
- 用于服务调用 (using, for service calls) 273

## D

- 数据访问对象 (DAO) 8
- 依赖关系 (dependencies) 275
- 在系统设计时分析 (analyzing, while system designing) 276
- 循环依赖 (cyclicic dependencies) 275
- 单体架构设计 (designs, monolithic architecture)
- 带有服务的单体设计 (monolithic design with services) 10
- 服务设计 (services design) 10
- 传统单体设计 (traditional monolithic design) 9
- 显示报告按钮 64

## E

- Elasticsearch, Logstash, Kibana (ELK) 栈与日志 261
- 使用 Docker Compose 执行 (executing, Docker Compose used) 268
- 实现提示 (implementation tips) 272
- 日志推送到 (logs, pushing to) 270
- 概述 (overview) 263
- 设置 (set) 265
- 停滞 (stalling) 265
- 参考文献 (reference) 277
- 企业归档 (EAR) 8
- 企业服务总线 (ESB) 7
- 实体 68
- Eureka 253
- Eureka 客户端 105
- 预订和用户服务 (Booking and User services) 105
- 执行 (executing) 106
- Eureka 服务 104
- Maven 依赖 (Maven dependency) 104
- 注册 (registration) 103
- Spring 配置 (spring configuration) 104
- 启动类 (startup class) 104

## F

- Fenzo
  - 关于 258
  - 特性 258
- 全集成身份验证 (FIDO) 258, 259
- 身份，创建
  - 自动生成 ID，使用 62
  - 复合键，使用 62
  - 主键，使用 62
  - 用户定义标识 62
- 集成开发环境 (IDE) 222
- 集成测试 247
- 接口隔离原则 (ISP) 77
- 互联网工程任务组 (IETF) 162

## G

- Gulp
  - 参考 242

## H

- Hystrix 254
  - 回退方法
  - 熔路器，启用 123
  - 配置 123
  - 定义 124
  - Maven 依赖 124
  - 属性，在 application.yml 文件中添加 124
  - 特性，已添加
  - 配置 257
  - 动态查询 257
  - 历史/变更 257
- Hystrix 仪表板
  - 设置 126
- 基于 SSL 的超文本传输协议 (HTTPS) 159
- 安全超文本传输协议 159
- 首页/餐厅列表地图
  - 关于 204
  - app.js 210
  - index.html 206, 209
  - restaurants.html 219
  - restaurants.js 212, 216

## I

- Janitor Monkey 256
- Jenkins
  - 参考 260
- 授权类型，OAuth 2.0
  - 授权码授权 174
  - 客户端凭据授权 183
  - 隐式授权 178
  - 资源所有者密码据授权 181

## K

- Kibana
  - 关于 264
  - 下载链接 267
  - 安装 267
  - 参考 268, 277

## L

- 单体架构相比于解决方案的局限性
  - 与敏捷实践对齐 14
  - 开发，改进 15
  - 微服务构建流水线 16
  - 新技术采纳，问题 13
  - 单维度扩展性 12
  - 发布回滚 12
- 代码行 (LOC) 246
- Loggly
  - 参考 260
- 登录页面
  - 关于 223
  - login.html 模板 224
  - login.js 224
- Logstash
  - 关于 264
  - 安装链接 266
  - 安装 266
  - 参考 266, 277
- 模型-视图-视图 (MVVM)

## M

- 微服务的强制性服务
  - 熔路器 113
  - 边缘服务器 112
  - Hystrix 仪表板 113
  - 负载均衡 112
- Netflix Eureka 上下文 (MDC) 250
- 主数据管理 (MDM) 251
- 微服务架构
  - 熔路器 122
  - 客户端负载均衡 119, 122
  - Hystrix 回退方法 123
  - Hystrix，监控 125
  - 负载均衡 115
  - 概述，使用 Netflix OSS 113
  - 服务端负载均衡 115, 118
  - Turbine 服务，创建 128
- 微服务部署，使用的容器
  - Docker 容器，管理 139
  - Docker 镜像，配合 Maven 123
  - Docker 机器，配备 4 GB 内存 123
  - Docker，使用 Maven 执行 135
  - Docker，安装 132
  - 镜像，推送到仓库 138
  - 集成测试，使用 Docker 136
- 基于服务的设计
  - 概述 243
- 微服务框架和工具
  - 关于 252
  - Netflix 开源软件 (OSS) 252
- 微服务
  - 部署，使用 Docker 21
  - 开发 88
  - 演进 7
  - 实现 88
  - 强制性服务 112
  - 餐厅微服务 89
  - 模型 57
- 模型-视图-控制器 (MVC)
  - 控制器 198
  - 模型 198
  - 视图 198
- 模型 198
- 视图 198
- 模块
  - 关于 199
  - 应用模块加载 199
  - 应用模块配置 200
  - 应用模块 199
  - 特性 199
- 单体应用
  - 迁移到微服务应用 280
- 单体架构
  - 概述 8
  - 局限性 8
- 多层架构
  - 关于 59
  - 应用层 60
  - 领域层 60
  - 基础设施层 60
  - 表示层 60

## N

- Nebula 252
- NetBeans IDE
  - 下载链接 23
  - 安装 23, 26
- Netflix 开源软件 (OSS) 252
- Netflix Ribbon
  - 参考 141
- Netflix Zuul
  - 参考 141
- npm (Node.js 包管理器)
  - 关于 226
  - 安装链接 227

## O

- OAuth 2.0
  - 关于 162
  - 授权框架 196
  - 客户端注册 167
  - 协议端点 171
  - 角色 165
  - 规范 163
- OAuth 实现
  - 授权码授权 189, 192
  - 客户端凭据 195
  - 隐式授权 193
  - 资源所有者密码凭据 193
  - Spring Security，使用 184, 189
- 对象面向编程 (OOP) 63
- 本地解决方案
  - 关于 281
  - 云解决方案 280
- 在线表格系统 (OTRS)
  - 关于 86, 261
  - 实现 91
  - 8
- 开源软件 (OSS) 352
- OTRS 应用
  - 构建 131
  - 运行 131
- OTRS 特性 204
- 首页/餐厅列表页 204
- 登录页面 223
- 预订确认 226
- 餐厅详情，带预订选项 220
- restaurant.html 221
- 餐厅，搜索 220
- OTRS 实现
  - 控制器类 93
  - 控制器类，API 版本 93
  - 实体类 100
  - 仓库类 98
  - 服务类 96
- OTRS 功能
  - 预订服务 87
  - 餐厅服务 87
  - 用户服务 87

## P

- 性能辅助 (PCP) 257
- Pivotal 31
- Simple Java 对象 (POJO) 39
- Postman Chrome 扩展
  - 用于 REST API 测试 49, 51
- OAuth 2.0 协议端点
  - 授权端点 172
  - 重定向端点 173
  - Token 端点 172

## R

- RabbitMQ
  - 参考 141
- 响应式宣言 (Reactive Manifesto)
  - 参考 144
- 响应式微服务架构
  - 弹性原则 145
  - 事件驱动/消息驱动微服务 144
  - 消息驱动原则 145
  - 韧性原则 145
  - 响应原则 145
  - 基于 REST 的微服务 144
- 响应式微服务实现
  - 关于 146
  - 事件消费 153, 156
  - 事件产生 146, 152
- AngularJS 类型
  - 常量 201
  - 提供者 201
  - 服务 201
  - 值 201
- 远程过程调用 (RPC) 8
- 仓库对象 88
- 表述状态转移 (REST) 40
- REST API 测试
  - 异常测试用例 53
  - 正向测试用例 52
  - Postman Chrome 扩展 49, 51
- REST 应用
  - 执行 45
- REST 控制器类
  - @PathVariable 注解 42
  - @Request 注解 41
  - @RequestParam 注解 41
  - @RestController 注解 40
  - 创建 40
- REST 程序
  - 关于 37
- 嵌入式 Jetty 服务器，添加 46
- REST 应用，执行 45
- REST 控制器类，编写 40
- Ribbon 23
- OAuth 2.0 角色
  - 授权服务器 166
  - 客户端 166
  - 资源所有者 166
  - 资源服务器 166
- 软件设计 57
- Spinnaker 253
- SPR-9888
  - 参考 31
- Spring Boot
  - 添加到主项目 32, 36
  - 配置 31
  - 概述 31
- Spring Cloud Stream
  - 参考 157
- Spring Initializr
  - 参考 31
- Spring OAuth2
  - 参考 196
- Spring Security
  - 参考 196
  - 用于 OAuth 实现 184
- 战略设计与原则
  - 关于 70
  - 边界上下文 71
  - 上下文映射 72
  - 持续集成 71
- 备用名称 (SANs) 161

## S

- 示例领域服务
  - 创建 77
  - 实体实现 78
  - 仓库实现 79
  - 服务实现 81, 84
- Scumbjr 259
- 搜索提供者 259
- 安全套层 (SSL)
  - 启用 158
- 安全猴子 256
- 服务对象 64, 88
- 服务面向架构 (SOA) 7, 245
- 猴子军 255
- 简单对象访问协议 (SOAP) 7
- 单页应用 (SPAs) 203
- Sleuth
  - 用于追踪 273
  - 维护 276

## T

- Teamcity
  - 参考 260
- 测试驱动开发 (TDD) 248
- 测试
  - 启用 106, 108
- 传输层安全 (TLS) 158, 162
- Turbine
  - 参考 142
- Twitter
  - URL 159

## U

- 用户界面 (UI) 10

## V

- 值对象 (VOs) 88
- Vector 257
- 版本
  - 关于 275
  - 探索 277

## W

- Web 应用程序
  - 设置 226, 230, 233, 236, 241
- Web 存档 (WAR) 8

## Z

- Zipkin
  - 用于追踪 273
- Zuul 254
