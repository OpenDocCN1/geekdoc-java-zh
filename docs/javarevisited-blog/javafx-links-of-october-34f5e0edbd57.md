
# 十月份的 JavaFX 链接

> 原文：<https://medium.com/javarevisited/javafx-links-of-october-34f5e0edbd57?source=collection_archive---------0----------------------->

当我 9 月份在 `jfx-central.com` 重新开始每周 JavaFX 链接时，我想知道是否每周都有足够的内容可以分享。

但这是一个愚蠢的错误，正如你在下面十月份发生的事情的总结中看到的…🙂

## JavaFX 19 和 20

*   JavaFX 19 在几周前刚刚发布，但 [**约翰·沃斯**](https://twitter.com/johanvos) 已经[期待](https://twitter.com/johanvos/status/1575159889994911744?t=PJn2au0k_icq2qseeLVOXA&amp;s=09)下一个版本：*Java FX 20 中真正值得一提的改进是由* [***劳伦特·布尔格***](https://twitter.com/laurent_bourges) *对 `MarlinFX 0.9.4.6` 的更新。非常感谢你的贡献。它们是 JavaFX 成功的重要组成部分。参见*[*【JDK-8287604】*](https://bugs.openjdk.org/browse/JDK-8287604)*。劳伦特甚至在 GitHub 上分享了他的待办事项清单，以防你对他正在做的事情感到好奇…*

*   想测试 JavaFX 20 早期访问？在**胶子**网站上已经有[了！](https://gluonhq.com/products/javafx/#ea)

*   到目前为止，每个较新的 JavaFX 版本都可以在较低的 JDK 下运行，例如 JavaFX 17 可以与 JDK 11 兼容。但这将会改变，因为[在邮件列表](https://mail.openjdk.org/pipermail/openjfx-dev/2022-October/036089.html)中提到：“JavaFX 20 需要 JDK 17 或更高版本。”

*   [**Dirk Lemmermann**](https://twitter.com/dlemmermann) 在一条 tweet 中分享了 `openjdk/jfx` 项目中 [pull 请求的截图：“哇，47 个 pull 请求在 #OpenJFX 中‘准备好接受审查’。看起来我们有交通堵塞。有些几岁了。一些以最后的评论结束‘你能评论这个吗？’🙂希望 Oracle 真的增加他们的 #javafx 团队成员数量。”](https://github.com/openjdk/jfx/pulls?q=is%3Apr+is%3Aopen+label%3Arfr)

*   在 10 月 20 日的 JavaOne 大会上，发布了一些与 JavaFX 相关的公告：

    - [一条推文](https://twitter.com/JavaFXpert/status/1583174188587589632)作者 [**James Weaver**](https://twitter.com/JavaFXpert) ：“伟大的 #JavaFX 公告来自 @kevinrushforth，在 #JavaOne 大会上由 @mono_quito89 介绍，而 bandmate 和 @Java legend @BrianVerm 混合饮料。在这个过程中，@ GluonHQ 的朋友兼同事 @johanvos 强调了这一点。

    - 以及 [**Bernard Traversat**](https://twitter.com/BTraTra) 的 [LinkedIn 消息](https://www.linkedin.com/posts/btratra_java-javafx-openjdk-activity-6988940880757882880-s4RA?utm_source=share&amp;utm_medium=member_desktop)：“我们今天宣布将为 JDK 20 制作 JavaFX build！为 Java 平台提供现代 UI 工具包将继续使 Java 成为教育工作者教授编程和 UI 创新者探索新的丰富应用程序 UI 设计的最具吸引力的平台。”

    - 所以最新的 JavaFX 不仅可以在 [Gluon 网站](https://gluonhq.com/products/javafx/)上获得，还可以在 `jdk.java.net/javafx20` 上获得。

    - 很好奇此次发布会有什么影响，以及下周我们可以在这里分享什么…

## 场景生成器

*   [**Chad Preisler**](https://twitter.com/cpreisler) 分享了[一个视频，展示了如何使用 `SceneBuilder` 和 JavaFX](https://www.youtube.com/watch?v=auao5UNrUcg) 创建一个表单，让表单以正确的方式调整大小。

*   [**胶子**](https://twitter.com/GluonHQ/) 宣布发布**胶子场景构建器 19**。你可以从 `github.com/gluonhq/scenebuilder/releases` 得到它。

    - 它整合了带来大量改进的 JavaFX 19，因此您可以从所有这些发布亮点中获益[。](https://openjfx.io/highlights/19/)

    - [这条推文展示了一个视频](https://twitter.com/Raumzeitfalle/status/1578692849746718720?t=mNxAaRN22Frjkf6kTfGy-w&amp;s=09)修复了 macOS 上的一个错误，其中复制&粘贴经常导致粘贴后条目翻倍。一个新的偏好设置“文本输入的替代粘贴行为”在 macOS 上可用，并且默认情况下是启用的。

## 比利时 Devoxx

*   Devoxx Belgium (10 月 10 日至 14 日)[感谢 Gluon 在推文中](https://twitter.com/Devoxx/status/1577934708100456448)对 #OSS Devoxx 移动应用的持续支持。`DevoxxBadges` JavaFX 应用程序[的源代码可以在 GitHub](https://github.com/gluonhq/DevoxxBadges) 上找到。

*   tweet wall 是 Devoxx 的访问者之间信息交流的重要部分，显示即将到来的会谈，排名最高的会谈等。这个推文墙是由 [**@jugbodensee**](https://twitter.com/jugbodensee) 成员推动的社区努力，得到了 Gluon 的支持，[来源在 GitHub](https://github.com/TweetWallFX/TweetwallFX) 上。

    - [**Johan Vos**](https://twitter.com/johanvos) 在一条推文中分享了一张[图片](https://twitter.com/johanvos/status/1580097937270788096)。

    - 对了(1)，`TweetwallFX` 有自己的 [Twitter 账号 @TweetwallFX](https://twitter.com/TweetwallFX) 。

    - 对了(2)，官方的“Devoxx”手机 app 也是 JavaFX 项目，由 Gluon 创建，你可以在 GitHub 上找到[。查看 GitHub 工作流程，了解更多关于如何构建和发布到谷歌和苹果商店的信息](https://github.com/devoxx/MyDevoxxGluon)[。](https://github.com/devoxx/MyDevoxxGluon/tree/main/.github/workflows)

## 来自“网络”的各种新闻

*   [**Dirk Lemmermann**](https://twitter.com/dlemmermann) 在推文中宣布 [CalendarFX 的 11.12.1 版本](https://twitter.com/dlemmermann/status/1576974458761486338)具有显示资源分配的新视图，改进的编辑行为，大量的修复和增强。你可以在 GitHub 上找到[，这里有](https://github.com/dlsc-software-consulting-gmbh/CalendarFX)[文档的新链接](https://dlsc-software-consulting-gmbh.github.io/CalendarFX/)。

    - Dirk 还为 [**GemsFX**](https://github.com/dlsc-software-consulting-gmbh/GemsFX) 添加了一个新的自定义控件，用于显示 JavaFX 应用程序的屏幕和窗口，其灵感来自 MacOS。关于截图，请查看[这条推文](https://twitter.com/dlemmermann/status/1578426485299449857?t=bCzbA3BPMatyoQVM362l-A&amp;s=09)和 YouTube 上的[演示。](https://www.youtube.com/watch?v=Kv7jo9fF9tc)

    - 他还宣布了 [CalendarFX](https://www.jfx-central.com/libraries/calendarfx) 的 11.12.2 版本，修复了与时区和重复条目相关的各种错误。

    - 他分享了[这个视频](https://www.youtube.com/watch?v=kwVXO0MdIdk)展示了一个定制的 JavaFX 控件，该控件可以用来显示扩展或堆叠的通知组，灵感来自 MacOS 通知中心。然而，通过 API 或 CSS 的大量定制选项可用于使该控件适合任何应用程序。

*   [**Robert lad sttter**](https://twitter.com/rladstaetter) 想要在 Windows aarch64(虚拟)机器上使用 JavaFX，[描述了从源代码构建它的过程](http://ladstatt.blogspot.com/2022/10/a-javafx-fanboy-forgets-about-his.html)。

*   [**Almas Baim**](https://twitter.com/AlmasBaim/) 在推文中分享了[一段视频](https://twitter.com/AlmasBaim/status/1576154186315882496)展示了用 FXGL(游戏引擎)生成的一座桥，以说明距离关节(它约束两个实体以保持它们彼此之间的距离)产生了一些有趣的结果。不同密度的实体被扔向它，并利用物理学飞过屏幕。

    - 与 FXGL 相关：[《用 FXGL 17 学习 JavaFX 游戏和 App 开发》](https://www.jfx-central.com/books/fxgl17)作者 [**阿尔马斯·拜姆**](https://twitter.com/AlmasBaim/) 通过 [**弗兰克·德尔博特**](https://twitter.com/FrankDelporte) 审核，在 [foojay.io](https://foojay.io/today/book-review-learn-javafx-game-and-app-development-with-fxgl-17/) 上阅读。

*   [**OrangoMango**](https://twitter.com/orango_mango) 分享了一个[项目，用 JavaFX](https://github.com/OrangoMango/RubikCube) 可视化并求解一个魔方，这也是一个安卓 APK。它的灵感来自胶子创造的[类似例子。](https://github.com/gluonhq/gluon-samples/tree/master/rubiks-cube)

*   [**Abhinay Agarwal**](https://twitter.com/iAbhinay) 分享了几个很有意思的 JavaFX 链接：

    - [**edencoding.com**](https://edencoding.com/category/javafx/) 有“我最近碰到的最有活力的 JavaFX 文章集合。向艾德·伊登·鲁普致敬”

    - 由**阿比内**自己创建的列表，其中包含了在[“JavaFX 应用程序标志”](https://abhinay.xyz/javafx/2022/10/03/OpenJFX-flags.html)上调试 Java FX 应用程序时可能会有帮助的所有标志

*   [**罗伯特·拉德斯特**](https://twitter.com/rladstaetter) 在 GitHub 上分享了一个 [HelloWorld 的示例项目，展示了如何使用](https://github.com/rladstaetter/javafx-advancedinstaller-example) [**高级安装程序**](https://twitter.com/advinst) 在 Windows Installer 上安装 JavaFX app。

*   [**佩德罗·杜克维埃拉**](https://twitter.com/P_Duke) 向 FXComponents 库添加了两个新控件：

    - `BlockingProgressBar`：[查看这条推文中的视频示例](https://twitter.com/P_Duke/status/1580570179376816129)。

    - `ReordableListView`，一个可以通过鼠标拖放单元格来重新排序的 `ListView`，也支持从外部源拖放到 `ListView` 单元格位置，正如你在这篇推文的视频中看到的[。](https://twitter.com/P_Duke/status/1582732021448978433)

*   [**Will Iverson**](https://twitter.com/wiverson) 更新了他的 [Java、JavaFX 和 Swing 模板，用一个新的 GitHub Action matrix 脚本为 macOS、Windows 和 Ubuntu 生成漂亮的原生安装程序，以生成所有安装程序，具有友好、匹配的版本号。](https://github.com/wiverson/maven-jpackage-template)

*   [**Clemens Lanthaler**](https://twitter.com/lanthale) 发布 [PhotoSlide 1.3](https://www.jfx-central.com/real_world/photoslide) 进行了许多小的更新和修复，包括 `librawfx` 和 `libheiffx` 的新版本，以及对 JDK19/Javafx19 的更新，再次提供了更好的多线程。

*   [LogoRRR—日志文件查看器—](https://github.com/rladstaetter/LogoRRR/releases/tag/22.3.0) [的新版本 22.3.0](https://twitter.com/logorrr/status/1581654374719557632) 已经发布。

*   [**WebFX**](https://twitter.com/WebFXProject)——一个 JavaFX 到 JavaScript 的 trans piler——现在可以访问本地文件，正如你可以在[这个 GitHub 讨论](https://github.com/webfx-project/webfx/discussions/14)上看到的，在 `files.webfx.dev` 上有一个[演示。](https://files.webfx.dev/)

    - [这个新演示](https://webfx.dev/#/demos)展示了添加到 JavaFX 媒体仿真中的 `MediaView`，这意味着 WebFX 现在可以显示视频了。

*   9 月 30 日， [**Gail Anderson**](https://twitter.com/gail_asgteach) 在 IntelliJ IDEA 大会上演讲“JavaFX for Mobile Development”。我们在这里承诺，如果有视频链接，我们会分享给大家，现在是。

*   [**肖恩·菲利普斯**](https://twitter.com/SeanMiPhillips) 用一个令人印象深刻的数据可视化工具分享了几个视频。

    - [使用 #Java 和 #JavaFX](https://twitter.com/SeanMiPhillips/status/1584287746637828098) 在解码后的超维空间中画弧线。

    - [Trinity JavaFX 3D 凸包生成器](https://www.youtube.com/watch?v=NXHQY5Fh1Do) - 外壳点云使用 #JavaFX 3D

*   [**Jakob Jenkov**](https://twitter.com/jjenkov) 在这条推文中问[，并有许多有趣的回复](https://twitter.com/jjenkov/status/1584090714320695296)：“嗨，Java fxers——我们在哪里有一些 JavaFX 应用程序设计模式吗？关于如何构建一个 #Java + #JavaFX 应用程序的建议，以便代码库和应用程序不会随着应用程序的增长而变得混乱？我有一些想法——但我想看看你们其他人也有什么 :-)”

## 关于 jfx-central.com 的新内容



真实世界 App: [JabRef](https://www.jfx-central.com/real_world/jabref) 是一款开源、跨平台的引用和参考管理工具，参见[jabref.org](https://www.jabref.org/)。

工具: <https://twitter.com/HydraulicCorp>，是`jpackage`工具的替代/替换，但支持（后台）更新、签名、公证。

另一库由 [佩德罗·杜克](https://twitter.com/P_Duke) 开发：[FXParallax](https://www.jfx-central.com/libraries/fxparallax)。这个框架增加了控件来给 JavaFX 应用程序添加视差效果，这种效果可以给使用它的地方增加深度感（像 3D 一样）。

即将推出…[Florian kir Maier](https://twitter.com/FlorianKirmaier)正在为 jfx-central 网站做宣传，希望它能很快变得更快。由于 [jpro.one](https://www.jpro.one/) 的架构，在`ScrollPane`中滚动需要服务器调用（因为 JavaFX 应用程序驻留在服务器上）。一个自定义皮肤，应该带一个解决方案…

人物: [扬·加森](https://twitter.com/jan_gassen) 的作品列在[这一页](https://www.jfx-central.com/people/j.gassen)。

库: [NSMenuFX](https://www.jfx-central.com/libraries/nsmenufx)，由 Jan Gassen 开发，这是一个简单的库，用于定制 macOS 菜单栏，使您的 JavaFX 应用程序具有更自然的外观和感觉。

提示: [Java FX 应用程序的标志](https://www.jfx-central.com/tips/application_flags)用于添加调试日志或切换配置。

博客: [abhinay.xyz](https://www.jfx-central.com/blogs/abhinay.xyz) 作者[abhi nay Agarwal](https://twitter.com/iAbhinay)关于 JavaFX 值得了解的事情。

原载于 2022 年 10 月 31 日 [https://foojay.io](https://foojay.io/today/javafx-links-of-october/)。
