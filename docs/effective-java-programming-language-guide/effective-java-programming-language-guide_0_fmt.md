
# Java 编程语言指南

## 关于本电子书

EPUB 是一种开放的行业标准电子书格式。然而，不同的阅读设备和应用程序对 EPUB 及其许多功能的支持程度不相同。请使用您的设备或应用设置来根据您的喜好自定义显示效果。您可以自定义的设置通常包括字体、字号、单栏或双栏布局、横屏或竖屏模式，以及可以点击或触控放大的图片。有关您的阅读设备或应用上相关设置和功能的更多信息，请访问设备制造商的网站。

许多书籍包含编程代码或配置示例。为了优化这些元素的显示效果，请在单栏横屏模式下查看电子书，并将字体大小调整为最小设置。除了以重流文本格式呈现代码和配置外，我们还包含了代码的图像，以模拟印刷版中的显示效果；因此，当重流格式可能会损害代码列表的显示效果时，您将看到一个“点击此处查看代码图像”的链接。点击链接即可查看高保真的代码图像。要返回上一页，请点击设备或应用上的“返回”按钮。

波士顿 • 哥伦布斯 • 印第纳波利 • 纽约 • 旧金山 • 阿姆斯特丹 • 开普敦

迪拜 • 伦敦 • 马德里 • 米兰 • 慕尼黑 • 巴黎 • 蒙特利尔 • 多伦多 • 德里 • 墨西哥城

圣保罗 • 悉尼 • 香港 • 首尔 • 新加坡 • 台北 • 东

致我的家人：Cindy, Tim, 和 Matt

## 9 通用编程

### Item 57: 缩小局部变量的作用范围

### Item 58: 优先使用 for-each 循环而非传统的 `for` 循环

### Item 59: 并使用库

### Item 60: 如果需要精确答案，避免使用 `float` 和 `double`

### Item 61: 优先使用基本类型而非包装后的基本类型

### Item 62: 在其他类型更合适的情况下避免使用字符串

### Item 63: 注意字符串拼接的性能

### Item 64: 通过接口引用对象

### Item 65: 优先使用接口而非反射

### Item 66: 审慎地使用原生方法

### Item 67: 审慎地优化

### Item 68: 遵循通常通用的命名规范

## 10 异常

### Item 69: 仅对异常情况使用异常

### Item 70: 对可恢复的情况使用检查异常，对编程错误使用运行时异常

### Item 71: 避免不必要地使用检查异常

### Item 72: 优先使用标准异常

### Item 73: 抛出符合抽象层级的异常

### Item 74: 为每个方法抛出的所有异常编写文档

### Item 75: 在详细消息中包含失败捕获信息

### Item 76: 追求失败原子性

### Item 77: 不要忽略异常

## 11 并发

### Item 78: 对共享可变数据的访问同步

### Item 79: 避免过度同步

### Item 80: 优先使用执行器（executors）、任务和流而非线程

### Item 81: 优先使用并发工具而非 `wait` 和 `notify`

### Item 82: 档线程安全性

### Item 83: 审慎地使用懒初始化

### Item 84: 不要依赖线程调度器

## 12 序列化

### Item 85: 优先使用 Java 序列化的替代方案

### Item 86: 极其谨慎地实现 `Serializable`

### Item 87: 考虑使用自定义序列化格式

### Item 88: 防御地编写 `readObject` 方法

### Item 89: 对于单例控制，优先使用枚举类型而非 `readResolve`

### Item 90: 考虑使用序列化代理而非序列化实例

## 与第二版对应的章节

## 参考文献

## 索引

# 前言

如果一位同事对你说：“Spouse of me this night today manufactures the unusual meal in a home. You will join?”，你脑海中可能会闪过三个念头：第三，你被邀请去吃晚饭；其次，英语不是你同事的母语；第一，还有极大的困惑。

如果你自己学过第二门语言并尝试在教室外使用它，你就知道你必须掌握三件事：语言是如何构建的（语法），如何命名你想要讨论的话题（词汇），以及表达日常事物的习惯且有效的方法（用法）。课堂里往往只涵盖了前两点，当你试图让自己表达意清楚时，你会发现母语者在不断地忍住笑意。

编程语言也是如此。你需要理解核心语言：它是算法的、函数式的，还是面向对象的？你需要了解词汇：标准库提供了哪些数据结构、操作和设施？你还需要熟悉表达日常事物的习惯且有效的方法。

# 前言

## 第三版序言

1997 年，Java 刚出现时，James Gosling（Java 之之父）将其描述为一种“蓝领语言”，而且“相当简单” [G97]。大约同一时期，Bjarne Stroustrup（C++ 之之父）将 C++ 描述为一种“多范式语言”，它“刻意与支持单一程序编写方式的语言有所不同” [S95]。Stroustrup 警告说：

Java 的相对简单性——就像大多数新语言一样——部分是幻象，部分由于其不完整性。随着时间的推移，Java 的规模和复杂性将显著增加。它的体积会翻倍或三倍，并增长依赖实现的扩展或库。

现在二十年后，可以说 Gosling 和 Stroustrup 都是正确的。现在的 Java 变得庞大且复杂，在许多方面（从并行执行、迭代到日期和时间的表示）都有多种抽象。

我仍然喜欢 Java，尽管随着平台的增长，我的热情冷却了一些。鉴于其规模和复杂性的增加，对一份最新的最佳实践指南的需求变得尤为关键。在《Effective Java》的第三版中，我尽力为你提供了这样一份指南。我希望这一版在满足需求的同时，依然忠于前两个版本的精神。

小是美，但简单并不容易。

又记：如果我没有提到最近占据我大量时间的一个行业内最佳实践，我将失职了。自 20 世纪 50 年我们领域诞生以来，我们一直在重新实现对方的 API。这种做法对于计算机技术的飞速成功至关重要。我一直致力于维护这种自由 [CompSci17]，并鼓励你加入我的行列。对于我们职业的持续健康，保留重新实现对方 API 的权利至关重要。

## 第二版序言

自我 2001 年编写此书第一版以来，Java 平台发生了许多变化，现在是时候出第二版了。最重的一变化是 Java 5 中增加了泛型、枚举类型、注解、自动装箱以及 for-each 循环。紧随其后的是同样在 Java 5 中发布的新的并发库 `java.util.concurrent`。与 Gilad Bracha 一起，我非常有幸地领导了设计这些新语言特性的团队。我也有幸参与了由 Doug Lea 领导的、设计开发并发库的团队。

平台的另一个大变化是现代集成开发环境（IDE，如 Eclipse、IntelliJ IDEA 和 NetBeans）以及静态分析工具（如 FindBugs）的广泛采用。虽然我没有参与这些工作，但我从中获益匪浅，并学会了它们如何影响 Java 开发体验。

2004 年，我从 Sun 搬到了 Google，但在过去的四个里里，我继续参与了 Java 平台的开发，通过 Google 和 Java 社区进程（Java Community Process）为并发和集合 API 贡献力量。我还有幸幸利用 Java 平台开发了 Google 内部使用的库。现在，我知道当用户是什么感觉了。

正如 2001 年我写第一版时一样，我的首要目标与你们分享我的经验，这样你们就可以模仿我的成功，同时避免我的失败。新材料继续大量使用了 Java 平台库中的真实世界示例。

第一版的成功超出了我最疯狂的预期，我尽力在保持其精神的同时，涵盖了使书籍更新所需的所有新内容。书籍的增长是不可避免的，它确实增长了，从 57 项增加到了 78 项。我不仅增加了 23 项内容，还彻底修订了所有原始材料，并淘汰了一些已经过时的内容。

在附录中，你可以看到本书的内容与第一版内容的关系。

在第一版序言中，我写道 Java 编程语言及其库极大地有助于质量和生产力，并且是一件愉快的事。第 5 和第 6 版本的变化让一件很好的事情变得更好。现在的平台比 2001 年大得多，也更复杂，但一旦你学会了使用新特性的模式和惯用法，它们就能让你的程序更好，生活更轻松。我希望这一版能捕捉到我对平台持续的热情，并帮助你在使用该平台及其新特性时更加高效、愉快。

加利福尼亚州，圣何塞

2008 年 4 月

## 第一版序言

1996 年，我安顿了自己的家园，西进到 JavaSoft（当时是名）工作，因为显然那里是舞台的中心。在随后的五年里，我担任了 Java 平台库架构师。我设计、实现并维护了许多库，并担任了许多其他库的顾问。在 Java 平台成熟的过程中负责这些库是一生难得的机会。这么说并不夸张：我有幸能与我们这一代一些伟大的软件工程师共事。在这个过程中，我学习了许多关于 Java 编程语言的知识——什么是有效的，什么是无效，以及如何使用语言及其库以达到最佳效果。

这本书是我尝试与你们分享经验，这样你们就可以模仿我的成功，同时避免我的失败。我借用了 Scott Meyers 的《Effective C++》的格式，它包含五十项内容，每项都传达了一个改进程序和设计的特定规则。我发现这种格式非常有效，希望你们也这么觉得。

在许多情况下，我擅自地使用 Java 平台库中的真实世界示例来说明这些条目。在描述本可以做得更好的事情时，我试着挑我自己写的代码刺，但偶尔也会挑同事写的代码。如果尽管我尽了最大努力，仍然冒犯了任何人，我诚挚地道歉。引用反面例子不是为了指责责任，而是出于合作精神，以便我们所有人都能从前人的经验中获益。

虽然这本书的受众并不仅仅是可重用组件的开发者，但它不可避免地浸染了我过去二十年编写此类组件的经验。我自然而然地以导出 API（应用程序编程接口）来思考，我也鼓励你们也这样做。即使你们没有开发可重用组件，用这些术语思考往往也能提高你们所写软件的质量。此外，在不知情的情况下编写可重用组件并不稀见：你写了一些有用的东西，和隔壁的同事分享，不久之后就有六个用户了。此时，你不再有随意更改 API 的灵活性了，并感谢你在最初编写软件时为设计 API 所付出的所有努力。

我对 API 设计的关注对于那些新型轻量级软件开发方法（如*极端编程*）粉丝来说可能显得有些不自然。这些方法强调编写尽可能简单的程序。如果你正在使用这些方法之一，你会发现对 API 设计的关注在*重构*过程中非常有帮助。重构的基本目标是改进系统结构和避免代码重复。如果没有设计良好的组件 API，这些目标是无法实现的。

没有语言是完美的，但有些是优秀的。我发现 Java 编程语言及其库极大地有助于质量和生产力，并且是一件愉快的事。我希望这本书能捕捉我的热情，并帮助你们使用该语言更加高效、愉快。

加利福尼亚州，库比蒂诺

2001 年 4 月

## 谢谢

### 第三版致谢

感谢本书前两个版本的读者给予了如此亲切热烈的反响，将书中的理念付诸心，，并让我它们对他们和工作有多大的积极影响。感谢许多在课程中使用这本书的教授，以及许多采纳这本书的工程团队。

感谢 Addison-Wesley 和 Pearson 的整个团队，他们的慷慨、专业、耐心和在极端压力下的优雅。在整个过程中，我的编辑 Greg Doench 始终保持从容：一位出色的编辑，一位完美的绅士。我担心由于这个项目，他的头发可能白了一些，我诚恳地道歉。我的项目经理 Julie Nahil 和我的项目编辑 Dana Wilson 是我所能希望的所有：勤奋、及时、有组织且友好。

我再次幸运地拥有想象中最完美的审稿团队，并向他们每一个人表示最诚挚的感谢。核心团队审查了几乎每一个章节，包括 Cindy Bloch、Brian Kernighan、Kevin Bourrillion、Joe Bowbeer、William Chargin、Joe Darcy、Brian Goetz、Tim Halloran、Stuart Marks、Tim Peierls 和 Yoshiki Shibata。其他审稿人包括 Marcus Biel、Dan Bloch、Beth Bottos、Martin Buchholz、Michael Diamond、Charlie Garrod、Tom Hawtin、Doug Lea、Aleksey Shipilëv、Lou Wasserman 和 Peter Weinberger。审稿人提出了许多建议，使这本书得到了巨大的改进，并使我免于许多尴尬。

我特别感谢 William Chargin、Doug Lea 和 Tim Peierls，他们担任了书中许多想法的倾听者。William、Doug 和 Tim 在时间和知识上总是一如既往地大慷慨。

最后，我要感谢我的妻子 Cindy Bloch，她鼓励我写作，阅读每一项初稿内容，编写索引，帮助我处理在承担大项目时不可避免会出现的所有问题，并在我写作期间忍受我。

### 第二版致谢

我感谢第一版读者的给予本书如此亲切和热烈的反响，将它的想法记在心中，并让我知道它对他们和工作产生了积极影响。我感谢许多在课程中使用这本书的教授，以及许多采纳它的工程团队。

我感谢 Addison-Wesley 整个团队的友善、专业、耐心和在压力之下的优雅。在整个过程中，我的编辑 Greg Doench 始终从容不迫：一位出色的编辑，一位完美的绅士。我的制作经理 Julie Nahil 具备一个制作经理应该的所有品质：勤奋、及时、有组织性且友好。我的文字编辑 Barbara Wood 严谨且有品味。

我再次幸运地拥有想象中最完美的审稿团队，并向他们每一个人表示最诚挚的感谢。核心团队审查了每一个章节，包括 Lexi Baugher、Cindy Bloch、Beth Bottos、Joe Bowbeer、Brian Goetz、Tim Halloran、Brian Kernighan、Rob Konigsberg、Tim Peierls、Bill Pugh、Yoshiki Shibata、Peter Stout、Peter Weinberger 和 Frank Yellin。其他审稿人包括 Pablo Bellver、Dan Bloch、Dan Bornstein、Kevin Bourrillion、Martin Buchholz、Joe Darcy、Neal Gafter、Laurence Gonsalves、Aaron Greenhouse、Barry Hayes、Peter Jones、Angelika Langer、Doug Lea、Bob Lee、Jeremy Manson、Tom May、Mike McCloskey、Andriy Tereshchenko 和 Paul Tyma。再次，这些审稿人提出了许多建议，使这本书得到了巨大的改进，并使我免于许多尴尬。再次，任何剩下的尴尬都是我的责任。

我特别感谢 Doug Lea 和 Tim Peierls，他们担任了书中许多想法的倾听者。Doug 和 Tim 在时间和知识上总是一如既往地慷慨。

我感谢我的 Google 经理 Prabha Krishna 对我持续的支持和鼓励。

最后，我要感谢我的妻子 Cindy Bloch，她鼓励我写作，阅读每一项初稿内容，帮助我使用 `Framemaker`，编写索引，并在我写作期间忍受我。

### 第一版致谢

感谢 Patrick Chan 建议我写这本书，并向系列管理主编辑 Lisa Friendly 推销了这个想法；感谢系列技术编辑 Tim Lindholm 以及 Addison-Wesley 的执行编辑 Mike Hendrickson。感谢 Lisa、Tim 和 Mike 鼓励我追求这个项目，并对我终有一天能写出这本书持有超人的耐心和坚定的信念。

感谢 James Gosling 和他的原始团队给我提供了一个伟大的写作题材，并感谢许多追随 James 足迹的 Java 平台工程师。特别感谢我在 Sun Java 平台工具与库组的同事，感谢他们的见解、鼓励和支持。团队包括 Andrew Bennett、Joe Darcy、Neal Gafter、Iris Garcia、Konstantin Kladko、Ian Little、Mike McCloskey 和 Mark Reinhold。前成员包括李正华、Bill Maddox 和 Naveen Sanjeeva。

感谢我的经理 Andrew Bennett 和我的主管 Larry Abrahams 为这个项目提供了全面且热情的支持。感谢 Java Software 的工程副总裁 Rich Green 提供了一个让工程师能够自由进行创造性思考并发表成果的环境。

我幸运拥有想象中最完美的审稿团队，并向他们每一个人表示最诚挚的感谢：Andrew Bennett、Cindy Bloch、Dan Bloch、Beth Bottos、Joe Bowbeer、Gilad Bracha、Mary Campione、Joe Darcy、David Eckhardt、Joe Fialli、Lisa Friendly、James Gosling、Peter Haggar、David Holmes、Brian Kernighan、Konstantin Kladko、Doug Lea、李正华、Tim Lindholm、Mike McCloskey、Tim Peierls、Mark Reinhold、Ken Russell、Bill Shannon、Peter Stout、Phil Wadler 以及两位匿名审稿人。他们提出了许多建议，使这本书得到了巨大的改进，并使我免于许多尴尬。任何剩下的尴尬都是我的责任。

Sun 内外的许多同事参与了技术讨论，提高了了书的质量。其中，Ben Gomes、Steffen Grarup、Peter Kessler、Richard Roda、John Rose 和 David Stoutamire 贡献了有用的见解。特别感谢 Doug Lea，他担任了书中许多想法的倾听者。Doug 在时间和知识上总是一如既往地慷慨。

感谢 Julie Dinicola、Jacqui Doucette、Mike Hendrickson、Heather Olszyk、Tracy Russ 以及 Addison-Wesley 整个团队的支持。即使在极其紧迫的进度内，他们总是友好且配合。



感谢 Guy Steele 撰写序言。他能参与此项目深感荣幸。

最后，我要感谢我的妻子 Cindy Bloch，鼓励并偶尔威胁我写下这本书，阅读每一项初稿内容，帮助我使用 `Framemaker`，编写索引，并在我写作期间忍受我。

## 第 1 章：引言

本书旨在帮助有效地使用 Java 编程语言及其基础库：`java.lang`、`java.util` 和 `java.io`，以及 `java.util.concurrent` 和 `java.util.function` 等子包。书中也会讨论其他库。

本书由数十项组成，每项传达一条规则。这些规则被优秀且丰富的程序员认为是有益的。这些项目松散地分为十一章，每章涵盖软件设计的一个广泛方面。本书并非从头到尾阅读：每一项在程度上都是独立的。项目之间有大量的交叉引用，你可以轻松在书中规划自己的路线。

自本书上一版出版以来，平台增加了许多新功能。本书中的大多数项目都以某种方式使用了这些功能。下表显示了关键功能的重点覆盖区域：

| 特性 | 项目编号 | 发布版本 |
| :--- | :--- | :--- |
| Lambdas | 项目 42–44 | Java 8 |
| Streams | 项目 45–48 | Java 8 |
| Optionals | 项目 55 | Java 8 |
| 接口中的默认方法 | 项目 21 | Java 8 |
| `try`-with-resources | 项目 9 | Java 7 |
| `@SafeVarargs` | 项目 32 | Java 7 |
| 模块 | 项目 15 | Java 9 |

# 前言

大多数条目都通过程序示例进行了说明。本书的一个关键特点是它包含了说明许多设计模式和惯用法的代码示例。在适当的情况下，这些示例会交叉引用该领域的标准参考著作 [Gamma95]。

许多条目包含一个或多个程序示例，用于说明某些应该避免的实践。这些示例有时被称为*反模式（antipatterns）*，它们会被用诸如 `// Never do this!` 之类的注释明确标记。在每个情况下，条目都解释了为什么该示例是糟糕的，并建议了替代方案。

本书不是为初学者准备的：它假设你已经熟练了 `Java`。如果你还没有，请考虑许多优秀的入门读物，例如 Peter Sestoft 的 *Java Precisely* [Sestoft16]。虽然《Effective Java》的设计旨在让任何具备该语言知识的人都能理解，但即使对于高级程序员来说，它也应该提供深思。

书中的大多数规则都源于几个基本原则。清晰和简单至关重要。组件的用户不应该对其行为感到惊讶。组件应该尽可能小，但不能更小。（在本书中，*组件（component）*一术语指的是任何可重用的软件元素，从单个方法到由多个包组成的复杂框架。）代码应该重用而不是复制。组件之间的依赖关系应该保持最少。错误应该在发生后尽快检测出来，理想情况下是在编译时。

虽然书中的规则并非 100% 的时间适用，但它们在大多数情况下刻画了最佳编程实践。你不应该盲目地遵循这些规则，而应在偶尔且理由充分的情况下违反它们。学习编程艺术，与其他大多数学科一样，包括首先学习规则，然后学习在何时打破规则。

在很大程度上，本书不是关于性能的。它是关于编写清晰、正确、可用、健壮、灵活且可维护的程序。如果你能做到，获得所需的性能通常是很简单的事（Item 67）。某些条目确实讨论了性能问题，少数条目提供了性能数据。这些数据通过“在我的机器上”这一短语引入，最多应被视为近似值。供参考，我的机器是一台老旧的自组 3.5GHz 四核 Intel Core i7-4770K，配备 16GB 的 DDR3-1866 CL9 内存，运行 Azul 的 Zulu 9.0.0.15 版本 OpenJDK，基于 Microsoft Windows 7 专业版 SP1 (64 位)。

在讨论 Java 编程语言及其库时，有时需要引用特定的版本。为了方便，本书优先使用昵称而非官方发布名称。下表显示了发布名称与昵称之间的映射：

| 官方发布名称 | 昵称 |
| :--- | :--- |
| JDK 1.0.*x* | Java 1.0 |
| JDK 1.1.*x* | Java 1.1 |
| Java 2 Platform, Standard Edition, v1.2 | Java 2 |
| Java 2 Platform, Standard Edition, v1.3 | Java 3 |
| Java 2 Platform, Standard Edition, v1.4 | Java 4 |
| Java 2 Platform, Standard Edition, v5.0 | Java 5 |
| Java Platform, Standard Edition 6 | Java 6 |
| Java Platform, Standard Edition 7 | Java 7 |
| Java Platform, Standard Edition 8 | Java 8 |
| Java Platform, Standard Edition 9 | Java 9 |

示例相当完整，但优先考虑可读性而非完整性。它们自由地使用了 `java.util` 和 `java.io` 包中的类。为了编译示例，你可能需要添加一个或多个 import 声明或其他此类模板代码。本书的网站 `http://joshbloch.com/effectivejava` 包含了每个示例的扩展版本，你可以对其进行编译和运行。

在很大程度上，本书使用的技术术语与 *The Java Language Specification, Java SE 8 Edition* [JLS] 中的定义一致。有几个术语值得特别提及。语言支持四种类型：*接口（interfaces）*（包括*注解 annotations*）、*类（classes）*（包括*枚举 enums*）、*数组（arrays）*和*基本数据类型（primitives）*。前三种被称为*引用类型（reference types）*。类实例和数组是*对象（objects）*；基本类型值不是。一个类的*成员（members）*由它的*字段（fields）*、*方法（methods）*、*成员类（member classes）*和*成员接口（member interfaces）*组成。一个方法的*签名（signature）*由它的名称和形式参数的类型组成；签名*不包含*方法的返回值。

本书使用的几个术语与 *The Java Language Specification* 不同。与 *The Java Language Specification*不同，本书将*继承（inheritance）*作为*子类化（subclassing）*的同义词。本书没有对接口使用继承一词，而是简单说明类*实现（implements）*一个接口或一个接口*扩展（extends）*另一个接口。为了描述在未指定时应用的访问级别，本书使用了传统的*包私有（package-private）*而非技术上正确的*包访问（package access）* [JLS, 6.6.1]。

本书还使用了一些 *The Java Language Specification* 中未定义的技术术语。*导出 API（exported API）*或简单称为 *API*，指的是程序员访问类、接口或包的类、构造函数、成员和序列化形式。

类可以为其客户端提供静态工厂方法，而不是（或者作为补充）公共构造函数。提供静态工厂方法而不是公共构造函数既有优点也有缺点。

### 优势一：工厂方法有名称

静态工厂方法的一个优势是，与构造函数不同，它们是有名称的。如果构造函数的参数本身不能描述所返回的对象，那么使用一个命名良好的静态工厂方法会更易使用，而且生成的客户端代码也更易于读。例如，构造函数 `BigInteger(int, int, Random)` 返回一个可能为质数的 `BigInteger`，这用命名为 `BigInteger.probablePrime` 的静态工厂方法来表示会更好。（该方法是在 Java 4 中添加的。）

一个类对于给定的签名只能有一个构造函数。众所 way 程序员通过提供两个参数列表仅在参数类型顺序上不同的构造函数来绕过这一限制。这是一个非常糟糕的主意。此类 API 的用户永远无法记住哪个构造函数是哪一个，最终会错误地调用其中一个。阅读使用这些构造函数的代码的人如果不查阅类文档，将不知道代码在做什么。

因为有了名称，静态工厂方法不受上一段落中讨论的限制。在类似乎需要多个相同签名的构造函数的情况下，将构造函数替换为静态工厂方法，并仔细选择名称以突出它们的区别。

### 优势二：它们不要求创建新对象

静态工厂方法的第二个优势是，与构造函数不同，它们并不要求每次调用时都创建一个新对象。这允许不可变类使用预先构造的实例，或者在构造时缓存实例并反复提供，避免创建不必要的重复对象。`Boolean.valueOf(boolean)` 方法说明了这种技术：它从不创建对象。这种技术类似于重量重模式（Flyweight pattern）。如果经常请求等效对象，特别是当创建成本很高时，这可以极大提高性能。

静态工厂方法通过重复调用返回相同对象的能力，允许类对任何时候存在的实例保持严格控制。做到此点的类被称为实例控制类（instance-controlled）。编写实例控制类有几个原因。实例控制允许类保证自己是单例的或不可实例化的。此外，它还允许不可变值类保证不存在两个相等的实例：当且仅当 `a == b` 时，`a.equals(b)`。这是重量重模式的基础。枚举（Enum）类型提供了这种保证。

### 优势三：它们可以返回任何子类型的对象

静态工厂方法的第三个优势是，与构造函数不同，它们可以返回返回类型的任何子类的对象。这让你在选择返回对象的类时具有极大的灵活性。

这种灵活性的一个应用是，API 可以在返回对象而不将其类公开的情况下。以这种方式隐藏实现类可以导致非常紧凑的 API。这种技术适用于基于接口的框架，其中接口为静态工厂方法提供了自然的返回类型。

在 Java 8 之前，接口不能包含静态方法。按照惯例，名为 `Type` 的接口的静态工厂方法被存放在一个名为 `Types` 的不可实例化的伴随类中。例如，Java 集合框架（Java Collections Framework）对其接口有四五个工具类级实现，提供了不可修改集合、同步集合等。几乎所有的这些实现都是通过一个不可实例化的类（`java.util.Collections`）中的静态工厂方法导出的。返回对象的类都是非公共的。

如果集合框架 API 导出四五个个独立的公共类（每个便利实现一个），那么它的规模会比现在小得多。减少的不仅仅是 API 的主体，还有概念上的重量：程序员为了使用该 API 必须掌握的概念的数量和难度。程序员知道返回的对象恰好拥有其接口所指定的 API，因此不需要为实现类阅读额外的类文档。此外，使用这种静态工厂方法要求客户端通过接口而非实现类来引用返回的对象，这通常是良好的做法。

从 Java 8 开始，接口不能包含静态方法的限制被消除了，因此通常没有理由为接口提供一个不可实例化的伴随类。许多本该放在此类类中的公共静态成员应该直接放在接口本身中。然而，请注意，可能仍需要将这些静态方法之后的大部分实现代码放在一个单独的包私有（package-private）类中。这是因为 Java 8 要求接口的所有静态成员必须是公共的。Java 9 允许私有静态方法，但静态字段和静态成员类仍被要求必须是公共的。

### 优势四：返回的类可以变化

静态工厂的第四个优势是，返回对象的类可以根据输入参数随每次调用而变化。声明的返回类型的任何子类型都是允许的。返回对象的类也可以随着发布版本的不同而变化。

`EnumSet` 类没有公共构造函数，只有静态工厂。在 OpenJDK 实现中，它们返回两个子类之一的实例，取决于底层枚举类型的大小：如果它有六十四个或更少的元素（大多数枚举类型都是如此），静态工厂返回 `RegularEnumSet` 实例，它由单个 `long` 支持；如果枚举类型有六十五个或更多元素，工厂返回一个由 `long` 数组支持的 `JumboEnumSet` 实例。

这两个实现类的存在对客户端是不可见的。如果 `RegularEnumSet` 对小枚举类型不再提供性能优势，可以在未来的版本中将其消除而不会产生任何不良影响。同样，如果证明对性能有益，未来的版本可以添加 `EnumSet` 的第三种或第四种实现。客户端既不知道也不关心它们从工厂获取的对象是什么类；它们只关心它是 `EnumSet` 的某个子类。

### 第五优势：返回的类在编写时不必存在

静态工厂的第五个优势是，在编写包含该方法的类时，返回对象的类不必存在。这种灵活的静态工厂方法是服务提供者框架的基础，例如 Java 数据库连接 API（JDBC）。服务提供者框架是一个系统，提供者实现服务，系统将实现提供给客户端，从而将客户端与实现解耦。

服务提供者框架有三个核心组件：服务接口（代表实现）、提供者注册 API（提供者用于注册实现）、服务访问 API（客户端用于获取服务实例）。服务访问 API 允许客户端指定选择实现的标准。在缺乏此类标准的情况下，API 返回默认实现的实例，或者允许客户端遍历所有可用实现。服务访问 API 是构成服务提供者框架基础的灵活静态工厂。

服务提供者框架的一个可选第四种组件是`服务提供接口`（service provider interface），它描述了一个产生服务接口实例的工厂对象。在没有服务提供接口的情况下，必须通过反射实例化实现（Item 65）。在 JDBC 中，`Connection` 充当服务接口，`DriverManager.registerDriver` 是提供注册 API，`DriverManager.getConnection` 是服务访问 API，而 `Driver` 就是服务提供接口。

服务提供者框架模式有很多变体。例如，服务访问 API 可以为客户端返回比提供者提供的丰富的服务接口。这就是 `Bridge` 模式 [Gamma95]。依赖注入框架（Item 5）可以被视为强大的服务提供者。从 Java 6 开始，平台包含了一个通用的服务提供框架 `java.util.ServiceLoader`，因此你不需要、通常也不应该自己写它（Item 59）。JDBC 没有使用 `ServiceLoader`，因为前者早于后者。

### 仅提供静态工厂方法的主要局限性是，没有公共或受保护构造函数的类无法被子类。例如，无法创建 Collections Framework 中任何便利实现类的子类。可以这么说，这可能是无中之福，因为它鼓励了程序员使用组合而不是继承（Item 18），并且对于不可变类型是必须的（Item 17）。

### 静态工厂方法的第二个缺点是程序员很难找到它们。它们在 API 文档中不像构造函数那样引人注目，因此可能很难弄出如何实例化一个提供静态工厂方法而非构造函数的类。Javadoc 工具有一天可能会引起静态工厂方法的关注。在此期间，你可以通过在类或接口文档中对静态工厂引起关注，并遵循通用的命名规范来减少这一问题。以下是一些静态工厂方法的常见名称。此列表远不是穷尽的：

- `from`—一种`类型转换方法`，它接收一个参数并返回该类型的对应实例，例如：

```java
Date d = Date.from(instant);
```

- `of`—一种聚合方法，它接收多个参数并返回一个包含这些参数的该类型实例，例如：

```java
Set<Rank> faceCards = EnumSet.of(JACK, QUEEN, KING);
```

- `valueOf`—`from` 和 `of` 的更冗长的替代方案，例如：

```java
BigInteger prime = BigInteger.valueOf(Integer.MAX_VALUE);
```

- `instance` 或 `getInstance`—返回一个由其参数（如果有）描述的实例，但不能说具有相同的值，例如：

```java
StackWalker luke = StackWalker.getInstance(options);
```

- `create` 或 `newInstance`—与 `instance` 或 `getInstance` 类似，不同在于该方法保证每次调用都返回一个新实例，例如：

```java
Object newArray = Array.newInstance(classObject, arrayLen);
```

- `getType`—与 `getInstance` 类似，但用于工厂方法位于不同类中的情况。`Type` 是工厂方法返回的对象类型，例如：

```java
FileStore fs = Files.getFileStore(path);
```

- `newType`—与 `newInstance` 类似，但用于工厂方法位于不同类中的情况。`Type` 是工厂方法返回的对象类型，例如：

```java
BufferedReader br = Files.newBufferedReader(path);
```

- `type`—`getType` 和 `newType` 的简洁替代方案，例如：

```java
List<Complaint> litany = Collections.list(legacyLitany);
```

总之，静态工厂方法和公共构造函数都有它们的用处，理解它们的相对优点是值得的。通常静态工厂更更好，因此避免在没有先考虑静态工厂的情况下就反射性地提供公共构造函数。

### Item 2：面对许多构造函数参数时考虑构建器（builder）

静态工厂和构造函数共享一个局限性：它们在面对大量可选参数时扩展性不好。考虑一个代表包装食品上营养成分标签的类。这些标签有几个必选字段——份量、每容器份数和每份热量，以及二十多个可选字段——总脂肪、饱和脂肪、反式脂肪、胆固醇、钠等。大多数产品只有这些可选字段中的几个是非零值。



对于这样的类，你应该编写什么样的构造函数或静态工厂？传统上，程序员使用`链式构造`（telescoping constructor）模式，其中你提供一个只包含必需参数的构造函数，另一个包含单个可选参数的构造函数，第三个包含两个可选参数的构造函数，以此类推，最后是一个包含所有可选参数的构造函数。这是它们在实践中的样子。为了简洁起见，只显示了四个可选字段：

```java
// 链式构造模式 - 扩展性不好！

public class NutritionFacts {

    private final int servingSize;  // (mL)            required
    private final int servings;     // (per container) required
    private final int calories;     // (per serving)  optional
    private final int fat;         // (g/serving)    optional
    private final int sodium;       // (mg/serving)  optional
    private final int carbohydrate; // (g/serving)   optional

    public NutritionFacts(int servingSize, int servings) {
        this(servingSize, servings, 0);
    }

    public NutritionFacts(int servingSize, int servings,
            int calories) {
        this(servingSize, servings, calories, 0);
    }

    public NutritionFacts(int servingSize, int servings,
            int calories, int fat) {
        this(servingSize, servings, calories, fat, 0);
    }

    public NutritionFacts(int servingSize, int servings,
            int calories, int fat, int sodium) {
        this(servingSize, servings, calories, fat, sodium, 0);
    }

    public NutritionFacts(int servingSize, int servings,
            int calories, int fat, int sodium, int carbohydrate) {
        this.servingSize  = servingSize;
        this.servings     = servings;
        this.calories     = calories;
        this.fat          = fat;
        this.sodium      = sodium;
        this.carbohydrate = carbohydrate;
    }
}
```

当你想创建一个实例时，使用包含所有想要设置的参数的最短参数列表构造函数：

```java
NutritionFacts cocaCola =
    new NutritionFacts(240, 8, 100, 0, 35, 27);
```

通常这种构造函数调用需要许多你不想设置的参数，但你仍然为它们传递了一个值。在这种情况下，我们为`fat`传递了`0`。对于“只有”六个参数这看起来并不糟糕，但随着参数数量的增加，情况会迅速失控。

简而言之，覆盖构造函数模式（telescoping constructor pattern）有效，但当参数很多时，编写客户端代码很困难，阅读起来更困难。读者会疑惑这些值代表什么，必须仔细数数参数才能找到答案。长长的相同类型参数可能会导致细微的错误。如果客户端不小心反反了两个这样的参数，编译器不会报错，但程序在运行时会发生异常（Item 51）。

当构造函数中面临许多可选参数时，另一种替代方案是`JavaBeans`模式。在这种模式下，你调用无参构造函数来创建对象，然后调用 setter 方法来设置每个必需参数以及感兴趣的每个可选参数：

```java
// JavaBeans Pattern - 允许不一致性，强制可变性
public class NutritionFacts {
    // 参数初始化为默认值（如果有）
    private int servingSize  = -1; // 必需；无默认值
    private int servings     = -1; // 必需；无默认值
    private int calories     = 0;
    private int fat          = 0;
    private int sodium      = 0;
    private int carbohydrate = 0;

    public NutritionFacts() { }

    // Setters
    public void setServingSize(int val)  { servingSize = val; }
    public void setServings(int val)    { servings = val; }
    public void setCalories(int val)    { calories = val; }
    public void setFat(int val)           { fat = val; }
    public void setSodium(int val)       { sodium = val; }
    public void setCarbohydrate(int val) { carbohydrate = val; }
}
```

这种模式没有覆盖构造函数模式的那些缺点。创建实例很简单（虽然有点冗长），且生成的代码易于阅读：

```java
NutritionFacts cocaCola = new NutritionFacts();
cocaCola.setServingSize(240);
cocaCola.setServings(8);
cocaCola.setCalories(100);
cocaCola.setSodium(35);
cocaCola.setCarbohydrate(27);
```

遗憾的是，`JavaBeans`模式也有其严重的缺点。由于构造被拆分到多次调用，一个 `JavaBean` 在构造的途中可能处于不一致的状态。该类无法仅通过检查构造函数参数的有效性来强制执行一致性。尝试在对象处于不一致状态时使用它可能会导致失败，这些失败与包含 bug 的代码相隔遥远，因此难以调试。相关的缺点是，`JavaBeans`模式排除了使类变为不可变的可能性（Item 17），并要求程序员付出额外努力来确保线程安全。

可以通过在构造完成后手动“冻结”对象，并在冻结前不允许其使用，从而减少这些缺点，但这种变体非常笨重，且在实践中很少使用。此外，它可能会在运行时引起错误，因为编译器无法确保程序员在使用对象之前已调用了冻结方法。

幸运的是，还有第三种替代方案，它结合了覆盖构造函数模式的安全性和 `JavaBeans`模式的可读性。它是`Builder`模式的一种形式 [Gamma95]。客户端不再直接创建所需的对象，而是调用带有所有必需参数的构造函数（或静态工厂）并获取一个 builder 对象。然后，客户端在 builder 对象上调用类似 setter 的方法来设置每个感兴趣可选参数。最后，客户端调用无参的`build`方法来生成对象，该对象通常是不可变的。builder 通常是它构建的类的静态成员类（Item 24）。以下是它在实践中的样子：

```java
// Builder Pattern
public class NutritionFacts {
    private final int servingSize;
    private final int servings;
    private final int calories;
    private final int fat;
    private final int sodium;
    private final int carbohydrate;

    public static class Builder {
        // 必需参数
        private final int servingSize;
        private final int servings;
        // 可选参数 - 初始化为默认值
        private int calories  = 0;
        private int fat  = 0;
        private int sodium  = 0;
        private int carbohydrate = 0;

        public Builder(int servingSize, int servings) {
            this.servingSize = servingSize;
            this.servings = servings;
        }

        public Builder calories(int val) { calories = val; return this; }
        public Builder fat(int val) { fat = val; return this; }
        public Builder sodium(int val) { sodium = val; return this; }
        public Builder carbohydrate(int val) { carbohydrate = val; return this; }

        public NutritionFacts build() {
            return new NutritionFacts(this);
        }
    }

    private NutritionFacts(Builder builder) {
        servingSize = builder.servingSize;
        servings = builder.servings;
        calories = builder.calories;
        fat = builder.fat;
        sodium = builder.sodium;
        carbohydrate = builder.carbohydrate;
    }
}
```

`NutritionFacts`类是不可变的，所有参数默认值都在一个地方。builder 的 setter 方法返回它本身，以便可以链式调用，从而形成流式 API。客户端代码如下：

```java
NutritionFacts cocaCola = new NutritionFacts.Builder(240, 8)
    .calories(100).sodium(35).carbohydrate(27).build();
```

这种客户端代码易写，更重要的是易读。`Builder`模式模拟了 `Python` 和 `Scala` 中的命名可选参数。

为了省略了有效性检查。为了尽早检测无效参数，请在 builder 的构造函数和方法中检查参数有效性。在`build`方法调用的构造函数中检查涉及多个参数的不变性。为了防止攻击这些不变性，请在从 builder 复制参数后进行检查（Item 50）。如果检查失败，抛出一个`IllegalArgumentException`（Item 72），其详细消息应指示哪些参数无效（Item 75）。

`Builder`模式非常适合类层次结构。使用并行的 builder 层级结构，每个 builder 嵌套在相应的类中。抽象类具有抽象的 builder；具体类具有具体的 builder。例如，考虑层次结构根部的一个代表各种披萨的抽象类：

```java
// 类层次结构的 Builder 模式
public abstract class Pizza {
    public enum Topping { HAM, MUSHROOM, ONION, PEPPER, SAUSAGE }
    final Set<Topping> toppings;

    abstract static class Builder<T extends Builder<T>> {
        EnumSet<Topping> toppings = EnumSet.noneOf(Topping.class);

        public T addTopping(Topping topping) {
            toppings.add(Objects.requireNonNull(topping));
            return self();
        }

        abstract Pizza build();

        // 子类必须重写此方法以返回 "this"
        protected abstract T self();
    }

    Pizza(Builder<?> builder) {
        toppings = builder.toppings.clone(); // 见 Item 50
    }
}
```

注意`Pizza.Builder`是一个带有`recursive type parameter`（递归类型参数）（Item 30）的`generic type`。这结合抽象的`self`方法允许方法链在子类中正常工作，而无需进行类型转换。这种针对 Java 缺乏`self`类型的解决方案被称为`simulated self-type`（模拟自类型）用例。

这里是`Pizza`的两个具体子类，其中一个代表标准的纽约风格披萨，另一个是意式饺饼（calzone）。前者有一个必需尺寸参数，而后者允许你指定酱料是在里面还是外面：

```java
public class NyPizza extends Pizza {

    public enum Size { SMALL, MEDIUM, LARGE }

    private final Size size;

    public static class Builder extends Pizza.Builder<Builder> {

        private final Size size;

        public Builder(Size size) {
            this.size = Objects.requireNonNull(size);
        }
        @Override public NyPizza build() {
            return new NyPizza(this);
        }
        @Override protected Builder self() { return this; }
    }

    private NyPizza(Builder builder) {
        super(builder);
        size = builder.size;
    }
}

public class Calzone extends Pizza {

    private final boolean sauceInside;

    public static class Builder extends Pizza.Builder<Builder> {

        private boolean sauceInside = false; // Default

        public Builder sauceInside() {
            sauceInside = true;
            return this;
        }
        @Override public Calzone build() {
            return new Calzone(this);
        }
        @Override protected Builder self() { return this; }
    }

    private Calzone(Builder builder) {
        super(builder);
        sauceInside = builder.sauceInside;
    }
}
```

注意，每个子类 builder 中的`build`方法都声明为返回正确的子类：`NyPizza.Builder`的`build`方法返回`NyPizza`，而`Calzone.Builder`中的`build`方法返回`Calzone`。这种将子类方法声明为返回父类中返回类型之子类型的技术被称为`covariant return typing`（协变返回类型）。它允许客户端使用这些 builder 而无需进行类型转换。



这些“分级 builder”的客户端代码与简单的 `NutritionFacts` builder 的代码基本相同。接下来所示的示例客户端代码为了简洁起见，假设对枚举常量使用了静态导入：

```java
NyPizza pizza = new NyPizza.Builder(SMALL)
        .addTopping(SAUSAGE).addTopping(ONION).build();

Calzone calzone = new Calzone.Builder()
        .addTopping(HAM).sauceInside().build();
```

builder 相比构造函数的一个微小优势是，builder 可以拥有多个变长参数，因为每个参数都在其自己的方法中指定。或者，builder 可以将传递给多次调用的参数聚合到一个字段中，正如之前的 `addTopping` 方法所所示。

Builder 模式非常灵活。一个 builder 可以重复使用来构建多个对象。在多次调用 `build` 方法之间，可以调整 builder 的参数以创建不同的对象。builder 可以在创建对象时自动填充某些字段，例如每次创建对象时都会增加的序列号。

Builder 模式也有其缺点。

要使一个使用上述方法之一的单例类变为可序列化的（第 12 章），仅仅在类声明中添加 `implements Serializable` 是不够的。为了维持单例保证，应将所有实例字段声明为 `transient` 并提供一个 `readResolve` 方法（Item 89）。否则，每当序列化的实例被反序列化时，都会创建一个新实例，在我们的示例中，这会导致伪 `Elvis` 实例出现。为了防止这种情况发生，请在 `Elvis` 类中添加此 `readResolve` 方法：

```java
// readResolve method to preserve singleton property
private Object readResolve() {
    // 返回唯一的真 Elvis 并让垃圾回收器
    // 处理 Elvis 冒充者。
    return INSTANCE;
}
```

实现单例的第三种方法是声明一个单元素枚举：

```java
// Enum singleton - the preferred approach
public enum Elvis {
    INSTANCE;
    public void leaveTheBuilding() { ... }
}
```

这种方法与公共字段的方法类似，但它更简洁，免费提供了序列化机制，并且即使在面对复杂的序列化或反射攻击时，也能提供防止多次实例化的铁律保证。这种方法可能感觉有点不自然，但单元素枚举类型通常是实现单例的最佳方式。请注意，如果你的单例必须继承除 `Enum` 以外的父类，则无法使用这种方法（尽管你可以声明一个枚举来实现某些接口）。

## Item 4：通过私有构造函数强制执行不可实例化

有时你可能想要编写一个仅作为静态方法和静态字段分组的类。这类类声誉不佳，因为一些人滥用它们来避免从对象的角度进行思考，但它们确实有其合理的用途。它们可以用于以类似于 `java.lang.Math` 或 `java.util.Arrays` 的方式，对原始值或数组的相关方法进行分组。它们还可以用于以类似于 `java.util.Collections` 的方式，对实现某些接口的对象对静态方法（包括工厂方法（Item 1））进行分组。（从 Java 8 开始，你也可以将此类方法放在接口中，假设你有权修改它。）最后，此类类可以用于对 final 类的方法进行分组，因为你无法将它们放在子类中。

此类工具类并不是为了实例化而设计的：创建一个实例将是没有意义的。然而，在没有显式构造函数的情况下，编译器会提供一个公共的、无参数的默认构造函数。对于用户来说，这个构造函数与其他构造函数没有区别。在发布的 API 中，看到无意中实例化的类并不罕见。

通过将类设为抽象类来强制执行不可实例化不可行的。该类可以被子化，并且子类可以实例化。此外，这会误导用户认为该类是为了继承而设计的（Item 19）。然而，有一种简单的惯用法可以确保不可实例化。只有当类不包含显式构造函数时，才会生成默认构造函数，因此通过包含私有构造函数可以使一个类变为不可实例化：

```java
// Noninstantiable utility class
public class UtilityClass {
    // 抑制默认构造函数以实现不可实例化
    private UtilityClass() {
        throw new AssertionError();
    }
    ... // 剩余部分省略
}
```

由于显式构造函数是私有的，因此在类外部是不可访问的。`AssertionError` 并不是严格要求的，但它为在从类内部意外调用构造函数时提供了保障。它保证了该类在任何情况下都不会被实例化。这种惯用法略微反直觉，因为显式提供构造函数恰是为了让它无法被调用。因此，如之前所示，包含注释是明智的。

作为副作用，这种惯用法还防止了类被子化。所有构造函数必须显式或隐式地调用父类构造函数，而子类将没有可用的父类构造函数可以调用。

## Item 5：优先使用依赖注入而非硬编码资源

许多类依赖于一个或多个底层资源。例如，拼写检查器依赖于字典。看到此类类被实现为静态工具类（Item 4）并不罕见：

```java
// Inappropriate use of static utility - 不灵活 & 不可测试!
public class SpellChecker {
    private static final Lexicon dictionary = ...;
    private SpellChecker() {} // 不可实例化
    public static boolean isValid(String word) { ... }
    public static List<String> suggestions(String typo) { ... }
}
```

同样，看到它们被实现为单例（Item 3）也不罕见：

```java
// Inappropriate use of singleton - 不灵活 & 不可测试!
public class SpellChecker {
    private final Lexicon dictionary = ...;
    private SpellChecker(...) {}
    public static SpellChecker INSTANCE = new SpellChecker(...);
    public boolean isValid(String word) { ... }
    public List<String> suggestions(String typo) { ... }
}
```

这两种方法都不令人满意，因为它们假设只有一个值得使用的字典。在实践中，每种语言都有自己的字典，并且特殊的词汇表使用特殊的字典。此外，在测试时可能希望使用特殊的字典。假设一个字典可以永远足够是痴人说梦。

你可以尝试通过将 `dictionary` 字段设为非 final 并为现有拼写检查器添加更改字典的方法让 `SpellChecker` 支持多个字典，但这样做会很笨拙、容易出错，并在并发环境下不可行。对于行为由底层资源参数化的类，静态工具类和单例是不适当的。

我们需要支持该类的多个实例（在我们的示例中是 `SpellChecker`），每个实例都使用客户端所需的资源（在我们的示例中是字典）。满足这一要求的简单模式是在创建新实例时将资源传入构造函数。这是依赖注入的一种形式：字典是拼写检查器的依赖，并在创建它时注入到拼写检查器中。

```java
// Dependency injection provides flexibility and testability
public class SpellChecker {
    private final Lexicon dictionary;
    public SpellChecker(Lexicon dictionary) {
        this.dictionary = Objects.requireNonNull(dictionary);
    }
    public boolean isValid(String word) { ... }
    public List<String> suggestions(String typo) { ... }
}
```

依赖注入模式非常简单，以至于许多程序员在使用多年后仍不知道它有一个名字。虽然我们的拼写检查器示例只有一个资源（字典），但依赖注入适用于任意数量的资源和任意依赖图。它保持了不可变性（Item 17），因此多个客户端可以共享依赖对象（假设客户端需要相同的底层资源）。依赖注入同样适用于构造函数、静态工厂（Item 1）和构建器（Item 2）。

该模式的一种实用变体是向构造函数传递一个资源工厂。工厂是一个可以被重复调用以创建特定类型实例的对象。此类工厂体现了工厂方法（Factory Method）模式 [Gamma95]。Java 8 引入的 `Supplier<T>` 接口非常适合表示工厂。以 `Supplier<T>` 作为输入的方法通常应该使用边界通配符类型（bounded wildcard type）Item 31 来限制工厂的类型参数，以便客户端传递一个创建指定类型任何子类的工厂。例如，这里有一个方法使用客户端提供的工厂生产每个瓷砖创建一个马赛克：

```
Mosaic create(Supplier<? extends Tile> tileFactory) { ... }
```

尽管依赖注入极大地提高了灵活性和测试性，但它可能会让大型项目变得臃肿，这些项目通常包含成千上万的依赖。使用依赖注入框架可以几乎消除这种臃肿，例如 `Dagger` [Dagger]、`Guice` [Guice] 或 `Spring` [Spring]。这些框架的使用超出了本书的范围，但请注意，为手动依赖注入设计的 API 可以很容易地适配供这些框架使用。

总之，不要使用单例或静态工具类来实现一个依赖于一个或多个底层资源的类（这些底资源的行为会影响该类的行为），也不要让该类直接创建这些资源。相反，将这些资源或创建它们的工厂传递到构造函数（或静态工厂或构建器）中。这种做法被称为依赖注入，将极大增强类的灵活性、可重用性和测试性。

## Item 6：避免创建不必要的对象

在需要时重用单个对象而不是每次都创建一个功能等效的新对象通常是合适的。重用既可能更快，也更优雅。如果一个对象是不可变的（Item 17），则总是可以被重用。

作为一个不恰做法的极端示例，考虑以下语句：

```
String s = new String("bikini");  // 不要这样做！
```

该语句每次执行时都会创建一个新的 `String` 实例，而这些对象创建没有一个是必要的。`String` 构造函数的参数（`"bikini"`）本身就是一个 `String` 实例，与构造函数创建的所有对象在功能上是相同的。如果这种用法出现在循环或频繁调用的方法中，可能会浪费创建数百万个 `String` 实例。

改进后的版本简单如下：

```
String s = "bikini";
```

这个版本使用单个 `String` 实例，而不是每次执行时都创建一个新的。此外，可以保证任何运行在相同虚拟机中恰好包含相同字符串字面量的代码都会重用该对象 [JLS, 3.10.5]。

对于同时提供构造函数和静态工厂方法的不可变类，通常可以使用静态工厂方法（Item 1）代替构造函数，从而避免创建不必要的对象。例如，工厂方法 `Boolean.valueOf(String)` 优于在 Java 9 中已弃用的构造函数 `Boolean(String)`。构造函数每次被调用时必须创建一个新对象，而工厂方法则永远不需要这样做，在实践中也不会这样做。除了重用不可变对象，如果你知道它们不会被修改，你也可以重用可变对象。

某些对象的创建比其他对象昂贵得多。如果你需要反复使用这种“昂贵对象”，可能建议将其缓存以供重用。遗憾的是，当你创建这样的对象时，并不总是显见的。假设你想写一个方法来判断字符串是否为有效的罗马数字。这是使用正则表达式实现此最简单的方法：

```
// 性能可以大大提高！
static boolean isRomanNumeral(String s) {
    return s.matches("^(?=.)M*(C[MD]|D?C{0,3})"
             + "(X[CL]|L?X{0,3})(I[XV]|V?I{0,3})$");
}
```

这种实现方式的问题在于它依赖于 `String.matches` 方法。虽然 `String.matches` 是检查字符串是否匹配正则表达式最简单的方法，但它不适用于性能敏感的场景中的重复使用。问题在于它在内部为正则表达式创建了一个 `Pattern` 实例并仅使用一次，之后它就符合垃圾回收条件。创建 `Pattern` 实例是昂贵的，因为需要将正则表达式编译为有限状态机。

为了提高性能，应显式地将正则表达式编译为 `Pattern` 实例（它是不可变的）作为类初始化的一部分，并将其缓存，并在每次调用 `isRomanNumeral` 方法时重用同一个实例：

```java
// 重用昂贵对象提高性能
public class RomanNumerals {
    private static final Pattern ROMAN = Pattern.compile("^(?=.)M*(C[MD]|D?C{0,3})"
             + "(X[CL]|L?X{0,3})(I[XV]|V?I{0,3})$");

    static boolean isRomanNumeral(String s) {
        return ROMAN.matcher(s).matches();
    }
}
```

`isRomanNumeral` 的改进版本如果频繁调用，将提供显著的收益。在我的机器上，原始版本处理 8 个字符的字符串耗时 1.1 µs，而改进版本仅需 0.17 µs，速度快了 6.5 倍。不仅性能得到了提高，可以说，清晰度也提高了。为这个原本不可见的 `Pattern` 实例创建一个静态 final 字段，允许我们为它命名，这比正则表达式本身可读性高得多。

如果包含改进版 `isRomanNumeral` 的类被初始化了但从未调用过该方法，字段 `ROMAN` 将被不必要的初始化。可以通过在第一次调用 `isRomanNumeral` 方法时对该字段进行延迟初始化（Item 83）来消除初始化，但不建议这样做。正如延迟初始化常见的情况一样，这会增加实现复杂度而不会产生可衡量的改进 Item 67]。

当一个对象是不可变的，安全重用是易见的，但在其他情况下，这并不易见，甚至反直觉。考虑适配器（adapters）[Gamma95]的情况，也称为视图（views）。适配器是一个委托给底层对象的对象，提供了一种替代接口。因为适配器除了底层对象的状态外没有状态，所以没有必要为给定的对象创建多个一个适配器实例。

例如，`Map` 接口的 `keySet` 方法返回 `Map` 对象的 `Set` 视图，包含 map 中所有的键。直观上看，每次调用 `keySet` 似乎都要创建一个 `Set` 实例，但对给定的 `Map` 对象每次调用 `keySet` 可能返回同一个 `Set` 实例。尽管返回的 `Set` 实例通常是可变的，但所有返回的对象在功能上是相同的：当其中一个返回对象发生变化时，其他对象也会随之变化，因为它们都由同一个 `Map` 实例支持。虽然创建多个 `keySet` 视图对象大致无害，但这是没有，也没有益处。

另一种创建不需要对象的方法是自动装箱（autoboxing），它允许程序员混合使用基本类型和包装基本类型，并根据需要自动进行装箱和拆箱。自动装箱模糊并没有消除基本类型与包装基本类型之间的区别。它们之间存在细微的语义差别以及显而易见的性能差异（Item 61）。考虑以下方法，它计算所有正整数 `int` 值的和。为了实现这一点，程序必须使用 `long` 算术，因为一个 `int` 的空间不足以容纳所有正整数 `int` 值的和：

```
// 慢得离谱！你能发现对象创建的地方吗？
private static long sum() {
    Long sum = 0L;
    for (long i = 0; i <= Integer.MAX_VALUE; i++)
        sum += i;
    return sum;
}
```

这个程序得到了正确答案，但由于一个字符的拼写错误，它的运行速度比应该有的慢得多。变量 `sum` 被声明为 `Long` 而不是 `long`，这意味着程序构造了大约 2³¹ 个不必要的 `Long` 实例（大约每当将 `long i` 加到 `Long sum` 时产生一个）。将 `sum` 的声明从 `Long` 改为 `long` 在我的机器上将运行时间从 6.3 秒缩短到了 0.59 秒。教训很明显：优先使用基本类型而非包装基本类型，并注意无意间的自动装箱。

这一项不应被误解为对象创建是昂贵的且应该避免的。相反，构造函数几乎不做任何显式工作的小对象的创建和回收是廉价的，尤其是在现代 JVM 实现上。创建额外的对象来增强程序的清晰性、简单性或功能通常是好事。



相反，通过维护自己的`对象池（object pool）`来避免对象创建是一个坏主意，除非池中的对象极其重量。`确实`需要对象池的经典例子是数据库连接。建立连接的代价足够，因此重用这些对象是有意义的。总的来说，维护自己的对象池会使代码变得混乱，增加内存占用并损害性能。现代 JVM 实现具有高度优化的垃圾回收器，它们在处理轻量级对象时轻松优于此类对象池。

此项的对立观点是 Item 50 中的`防御性拷贝（defensive copying）`。本项说，“当你本应该重用现有对象时，不要创建新对象”，而 Item 50 说，“当你本应该创建新对象时，不要重用现有对象”。请注意，在需要防御性拷贝时重用对象的代价远比无谓地创建一个冗隆对象的代价要大得多。在需要的地方没有进行防御性拷贝会导致隐蔽的 Bug 和安全漏洞；而不必要地创建对象只会影响风格和性能。

## 第 7 项：消除过时的对象引用

如果你从具有手动内存管理功能的语言（如 C 或 C++）切换到具有垃圾回收机制的语言（如 Java），你作为程序员的工作变得简单了一许多，因为在你用完对象后，它们会被自动回收。当你第一次体验到它时，感觉几乎就像魔法一样。这很容易给人一种印象，认为你不需要考虑内存管理的错觉，但并非完全如此。

考虑以下简单的栈栈实现：

```
// 你能发现这个“内存泄漏”吗？

public class Stack {
    private Object[] elements;
    private int size = 0;
    private static final int DEFAULT_INITIAL_CAPACITY = 16;
    public Stack() {
        elements = new Object[DEFAULT_INITIAL_CAPACITY];
    }
    public void push(Object e) {
        ensureCapacity();
        elements[size++] = e;
    }

    public Object pop() {
        if (size == 0)
            throw new EmptyStackException();
        return elements[--size];
    }

    /**
     * 确保至少有一个多余元素的空间，
     * 每次数组需要增长时将容量翻倍。
     */
    private void ensureCapacity() {
        if (elements.length == size)
            elements = Arrays.copyOf(elements, 2 * size + 1);
    }
}
```

这个程序没有任何明显的错误（但泛型版本请参见 Item 29）。你可以对其进行详尽的测试，它会完美通过每一个测试，但其中潜伏着一个问题。泛之，该程序有一个“内存泄漏”，这可能会静默地表现为由于垃圾回收器活动增加或内存占用增加导致的性能下降。在极端情况下，这种内存泄漏会导致磁盘分页甚至导致程序因 `OutOfMemoryError` 失败，但此类失败相对罕见。

那么内存泄漏在哪里呢？如果栈增长后又缩小，从栈中弹出的对象将不会被垃圾回收，即使使用该栈的程序不再拥有它们的引用。这是因为栈保留了对这些对象的`过时引用（obsolete references）`。过时引用简单来说就是永远不会被再次引用的引用。在这种情况下，元素数组“活跃部分”之外任何引用都是过时的。活跃部分由索引小于 `size` 的元素组成。

垃圾回收语言中的内存泄漏（更准确的说是*无意保留（unintentional object retentions）*）是隐蔽的。如果一个对象引用被无意地保留，不仅该对象被排除在回收之外，被其引用的对象也是如此，以此类推。即使只有少数对象引用被无意保留，也可能导致大量对象无法被回收，对性能产生巨大影响。

这类问题的修复方法很简单：一旦引用过时就将其置为空。在我们的 `Stack` 类示例中，一旦元素从栈中弹出，该引用就过时了。修正后的 `pop` 方法如下所示：

```java
public Object pop() {
    if (size == 0)
        throw new EmptyStackException();
    Object result = elements[--size];
    elements[size] = null; // 消除过时引用
    return result;
}
```

将过时引用置空的额外好处是，如果随后错误地引用了它们，程序会立即抛出 `NullPointerException` 失败，而不是静静地做错。尽早检测编程错误是有益的。

当程序员第一次被这个问题刺痛时，可能会过度补偿，在程序完成使用每个对象引用后立即将它们置为空。这既没有必要也不理想；它会无谓地干扰代码。**将对象引用赋值应该是例外而非常态。**消除过时引用的最佳方法是让包含引用的变量超出作用域。如果你在尽可能窄的作用域内定义每个变量，这种情况就会自然发生（Item 57）。

那么什么时候应该置空引用呢？`Stack` 类的哪个方面使得它容易产生内存泄漏？简单来说，它*管理自己的内存*。*存储池*由 `elements` 数组的元素组成（对象引用单元，而不是对象本身）。数组中活动部分（如前文定义）的元素是*已分配的*，而数组剩余部分的元素是*空闲的*。垃圾回收器无法得知这一点；对于垃圾回收器来说，`elements` 数组中的所有对象引用都同样有效。只有程序员知道数组的非活动部分是不重要的。程序员通过在数组元素一成为非活动部分就手动将其置空，有效地将这一事实传达给垃圾回收器。

通常情况下，**每当一个类管理自己的内存时，程序员就应该警惕内存泄漏**。每当一个元素被释放时，元素中包含任何对象引用都应该被置空。

**内存泄漏的另一个常见源是缓存。** 一旦你将一个对象引用放入缓存，很容易忘记它存在那里，并在它变得无关很久后仍将其留在缓存中。这个问题有几种解决方案。如果你足够幸运实现了一种缓存，其条目的有效性恰恰取决于缓存外部是否存在对其键的引用，那么将缓存表示为 `WeakHashMap`；条目在过期后会被自动移除。记住，只有当缓存条目的预期寿命是由对键的外部引用而非值决定时，`WeakHashMap` 才有用。

更常见的情况下，缓存条目的有效生命周期定义得并不明确，条目的价值会随着时间的推移而降低。在这种情况下，缓存应该偶尔清理那些不再使用的条目。这可以通过后台线程（可能是 `ScheduledThreadPoolExecutor`）或者作为向缓存中添加新条目时的副作用来完成。`LinkedHashMap` 类通过其 `removeEldestEntry` 方法有助于后者的实现。对于更复杂的缓存，你可能需要直接使用 `java.lang.ref`。

**内存泄漏的第三个常见源是监听器和其他回调。** 如果你实现了一个客户端注册回调但没有显式注销它们的 API，那么除非你采取某些行动，否则它们将不断累积。确保回调被及时垃圾回收的一种方法是仅对它们存储*弱引用*，例如仅将它们作为键存储在 `WeakHashMap` 中。

由于内存泄漏通常不会表现为明显的失败，它们可能会在系统中存在多年。它们通常只通过仔细的代码检查或借助名为*堆转储分析器（heap profiler）*的调试工具才能被发现。因此，在这些问题发生之前学会预测并防止它们的发生是非常理想的。

## 第 8 条：避免终化器（finalizers）和清理器（cleaners）

**终化器不可预测的，往往是危险的，并且通常没有必要。** 使用它们会导致异常行为、性能低下以及可移植性问题。终化器有一些有效的用途，我们将在本节稍后介绍，但根据原则，你应该避免使用它们。从 Java 9 开始，终化器已被弃用，但 Java 库仍在使用它们。Java 9 替代终化器的是*清理器（cleaners）*。**清理器比终化器不危险，但仍然不可预测的、缓慢的且通常没有必要。**

警告 C++ 程序员不要将终化器或清理器认为是 Java 中 C++ 析构函数的对应物。在 C++ 中，析构函数是回收与对象相关资源的正常方式，是构造函数的必要对应。在 Java 中，当对象变得不可达时，垃圾回收器会回收与对象相关的存储，不需要程序员付出任何特殊努力。C++ 析构函数还用于回收其他非内存资源。在 Java 中，`try`-with-resources 或 `try`-`finally` 块被用于此目的（第 9 条）。

终化器和清理器的一个缺点是，无法保证它们会被及时执行 [JLS, 12.6]。从对象变得不可达到到其终化器或清理器运行之间，可能会耗费任意长的时间。这意味着你**永远不要在终化器或清理器中执行任何对时间敏感的操作。** 例如，依赖终化器或清理器来关闭文件是一个严重的错误，因为打开的文件描述符是有限的资源。如果由于系统运行终化器或清理器的迟缓，导致许多文件一直保持打开状态，程序可能会因为无法再次打开文件而失败。

终化器和清理器执行的及时性主要取决于垃圾回收算法的这种函数，而该算法在不同的实现中差异巨大。依赖终化器或清理器执行及时性的程序行为可能也会存在差异。完全有可能，这样的程序在你测试的 JVM 上运行得完美，但在你最重要的客户所青睐的 JVM 上却会惨惨失败。

迟缓的终化不仅仅是一个理论问题。为某个类提供终化器会任意地延迟其实例的回收。一位同事调试了一个长时间运行的 GUI 应用程序，该程序神秘地因 `OutOfMemoryError` 死亡。分析显示，在它死亡时，应用程序的终化器队列上有成千上万个图形对象正等待被终化和回收。不幸的是，终化器线程的优先级低于另一个应用程序线程，因此对象被终化的速度赶不上它们进入终化条件的速度。语言规范对于哪个线程将执行终化器没有保证，因此除了避免使用终化器之外，没有可移植的方法可以防止这类问题。清理器在这方面比终化器好一点，因为类作者对自己的清理器线程有控制权，但清理器仍在后台运行，受垃圾回收器的控制，因此无法保证能及时清理。

规范不仅不保证终化器或清理器会及时执行，而且不保证它们会执行。完全可能，甚至很可能，程序在终止时没有对某些不可达的对象执行这些操作。结果是，你**永远不要依赖终化器或清理器来更新持久化状态。** 例如，依赖终化器或清理器来释放共享资源（如数据库）的持久化锁，会导致你的整个分布式系统停滞。

不要被 `System.gc` 和 `System.runFinalization` 方法诱惑。它们可能会增加终化器或清理器执行的概率，但不能保证这一点。有两个方法曾声称对此这种保证：`System.runFinalizersOnExit` 和它的邪恶孪生兄弟 `Runtime.runFinalizersOnExit`。这些方法存在致命缺陷，已经被弃用了几十年。

终化器的另一个问题是，在终化期间抛出的未捕获异常会被忽略，且该对象的终化过程会终止 [JLS, 12.6]。未捕获的异常可能会导致其他对象处于损坏状态。如果另一个线程尝试使用此类损坏的对象，可能会导致任意的非确定行为。通常情况下，未捕获的异常会终止线程并打印堆栈跟踪，但如果它发生在终化器中则不会——它甚至不会打印警告。清理器没有这个问题，因为使用清理器的库对其线程有控制权。

使用终化（finalizers）和清理器（cleaners）会有严重的性能代价。在我的机器上，创建一个简单的 `AutoCloseable` 对象、使用 `try`-with-resources 关闭它并让垃圾回收器回收它的时间大约是 12 ns。使用终化会将此时间增加到 550 ns。换句话说，使用终化创建和销毁对象的速度慢了约 50 倍。这主要是因为终化阻碍了高效的垃圾回收。如果你使用清理器来清理类的所有实例，其速度与终化相当（在我的机器上每个实例约 500 ns），但正如下面所述，如果你仅将其作为安全网，清理器会快得多。在这种情况下，创建、清理和销毁一个对象大约需要 66 ns，这意味着如果你没有使用安全网，你付出的代价是五倍而不是五十倍。

### 终化有一个严重的安全问题：它们让你的类容易受到终化攻击

终化攻击的原理很简单：如果构造函数或其序列化等价方法——`readObject` 和 `readResolve` 方法（第 12 章）——抛出异常，恶意子类的终化器就可以在一个本该“夭折在篮子里”的部分构造的对象上运行。这个终化器可以将对象的引用记录在静态字段中，防止其被垃圾回收。一旦格式错误的对象被记录下来，调用该对象上的任意方法就简单了，而这些方法本不应该被允许存在。在构造函数中抛出异常应该足以阻止对象的产生；但在存在终化的情况下，并非如此。此类攻击可能导致灾难性的后果。最终类（final classes）对终化攻击是免疫的，因为没有人可以编写最终类的恶意子类。为了保护非最终类免受终化攻击，请编写一个什么都不做的 final `finalize` 方法。

### 优选方法

那么，对于一个对象封装了需要终止的资源（如文件或线程）的类，除了编写终化或清理器之外，你应该做什么？只需让你的类实现 `AutoCloseable`，并要求客户端在不再需要每个实例时调用其实例的 `close` 方法，通常使用 `try`-with-resources 来确保即使在出现异常时也能终止（项目 9）。一个值得注意的细节是，实例必须跟踪自己是否已关闭：`close` 方法必须在字段中记录对象不再有效，而其他方法在对象关闭后被调用时，必须检查该字段并抛出 `IllegalStateException`。

### 清理器和终化的用途

那么，清理器和终化有什么用处呢？它们也许有两个合法的用途。一个是在资源所有者忽略调用其 `close` 方法时作为安全网。虽然不能保证清理器或终化器会及时运行（或根本不运行），但如果客户端未能这样做，晚释放资源总比永远不释放要好。如果你正在考虑编写这样的安全网终化，请仔细考虑这种保护是否值得付出。某些 Java 库类，如 `FileInputStream`、`FileOutputStream`、`ThreadPoolExecutor` 和 `java.sql.Connection` 具有作为安全网的终化。

清理器的第二个合法用途涉及带有原生伴侣（native peers）的对象。原生伴侣是一个原生的（非 Java）对象，普通对象通过原生方法委托给它。由于原生伴侣不是普通对象，垃圾回收器并不知道它，当它的 Java 伴侣被回收时无法回收它。清理器或终化器可能是执行此任务的合适工具，前提是性能是可以接受的，且原生伴侣不持有关键资源。如果性能不可接受或原生伴侣持有必须及时回收的资源，则该类应该如前所述拥有一个 `close` 方法。

### 示例：Room 类

清理器的使用有点复杂。下面是一个简单的 `Room` 类，演示了这一功能。假设房间在被回收之前必须进行清理。`Room` 类实现了 `AutoCloseable`；其自动清理安全网使用清理器这仅仅是一个实现细节。与终化不同，清理器不会污染类的公共 API：

```java
// 使用清理器作为安全网的自动关闭类

public class Room implements AutoCloseable {

    private static final Cleaner cleaner = Cleaner.create();

    // 需要清理的资源。**绝对不能引用 Room！**

    private static class State implements Runnable {

        int numJunkPiles; // 此房间内垃圾堆的数量

        State(int numJunkPiles) {
            this.numJunkPiles = numJunkPiles;
        }

        // 由 close 方法*或*清理器调用
        @Override public void run() {
            System.out.println("Cleaning room");
            numJunkPiles = 0;
        }
    }

    // 此房间的状态，与可清理对象共享
    private final State state;

    // 我们的可清理对象。当它符合 gc 条件时清理房间
    private final Cleaner.Cleanable cleanable;

    public Room(int numJunkPiles) {
        state = new State(numJunkPiles);
        cleanable = cleaner.register(this, state);
    }

    @Override
    public void close() {
        cleanable.clean();
    }
}
```

静态 `State` 类持有清理器所需的资源。在这种情况下，它是 `numJunkPiles` 字段。更现实的情况下，它可能是一个指向原生伴侣的 `long`。`State` 实现了 `Runnable`，其 `run` 方法最多调用一次，由我们在 `Room` 构造函数中将 `State` 注册清理器时得到的 `Cleanable` 调用。`run` 方法的调用将由两种情况触发：通常是由调用 `Room` 的 `close` 方法触发的。如果 `Room` 实例可以被回收，清理器将（希望）调用 `State` 的 `run` 方法。

`State` 实例不引用其 `Room` 实例至关重要。如果这样做，会导致循环，导致 `Room` 实例无法进入垃圾回收（无法无法自动清理）。因此，`State` 必须是一个静态嵌套类。同样不建议使用 lambda，因为很容易捕获对象的引用。

正如我们之前说的，`Room` 的清理器仅作为安全网。如果客户端将所有 `Room` 实例化放在 `try`-with-resources 块中，则永远不需要自动清理。这个良好的客户端演示了：



```java
public class Adult {
    public static void main(String[] args) {
        try (Room myRoom = new Room(7)) {
            System.out.println("Goodbye");
        }
    }
}
```

正如你预期的，运行`Adult`程序会打印`Goodbye`，然后是`Cleaning room`。但这个从不清理房间的不良程序又会呢？

点击此处查看代码图像

```java
public class Teenager {
    public static void main(String[] args) {
        new Room(99);
        System.out.println("Peace out");
    }
}
```

你可能期望它打印出`Peace out`，然后是`Cleaning room`，但在我的机器上，它从未打印过`Cleaning room`；它直接退出了。这就是我们之前谈过的不可预测性。`Cleaner`规范说：“`Cleaner`在`System.exit`期间的行为取决于具体实现。对于是否调用了清理动作，不作任何保证。”虽然规范没有明说，但对于正常的程序退出也是同样的。在我的机器上，在`Teenager`的`main`方法中添加`System.gc()`这一行足以让它在退出前打印出`Cleaning room`，但不能保证你的机器上会有相同的行为。

总之，不要使用清理器（`cleaners`），或者在 Java 9 之前的版本中不要使用终化器（`finalizers`），除非将其作为安全网或用于终止非关键的本地资源。即便如此，也要注意其不确定性和对性能的影响。

### Item 9：优先使用`try`-with-resources 优于`try`-`finally`

Java 库中包含了许多必须通过调用`close`方法手动关闭的资源。例如`InputStream`、`OutputStream`和`java.sql.Connection`。客户端经常忽略关闭资源，这会导致意料之且糟糕的性能后果。虽然这些资源中许多使用终化器作为安全网，但终化器的效果并不好（Item 8）。

从历史上看，`try`-`finally`语句是保证资源被正确关闭（即使在发生异常或返回时）的最佳方法：

点击此处查看代码图片

```java
// try-finally - 不再关闭资源的最佳方式了！
static String firstLineOfFile(String path) throws IOException {
    BufferedReader br = new BufferedReader(new FileReader(path));
    try {
        return br.readLine();
    } finally {
        br.close();
    }
}
```

这看起来并不坏，但当你添加第二个资源时，情况就会变得更糟：

点击此处查看代码图片

```java
// 在使用多个资源时，try-finally 非常难看！
static void copy(String src, String dst) throws IOException {
    InputStream in = new FileInputStream(src);
    try {
        OutputStream out = new FileOutputStream(dst);
        try {
            byte[] buf = new byte[BUFFER_SIZE];
            int n;
            while ((n = in.read(buf)) >= 0)
                out.write(buf, 0, n);
        } finally {
            out.close();
        }
    } finally {
        in.close();
    }
}
```

这可能难以相信，但即使是优秀的程序员在大多数时候也犯了这个错误。首先，我在*Java Puzzlers*的第 88 页就写错了 [Bloch05]，而且多年无人注意到。事实上，在 2007 年，Java 库中`close`方法使用的三分之二都是错误的。

即使是使用`try`-`finally`语句关闭资源的正确代码（如之前的两个代码示例所示），也存在细微的缺陷。`try`块和`finally`块中的代码都可能抛出异常。例如，在`firstLineOfFile`方法中，对`readLine`的调用由于底层物理设备的故障而抛出异常，随后对`close`的调用可能因为相同的原因失败。在这种情况下，第二个异常会完全覆盖掉第一个异常。异常堆栈跟踪中没有第一个异常的记录，这会极大地增加真实系统的调试复杂度——通常你希望看到的是第一个异常以便诊断问题。虽然编写代码来抑制第二个异常以保留第一个异常是可能的，但几乎没有人这样做，因为那实在太啰嗦了。

所有这些问题在 Java 7 引入`try`-with-resources 语句时 [JLS, 14.20.3] 都被迎刃而解了。要使用这种结构，资源必须实现`AutoCloseable`接口，该接口包含一个返回`void`的单一`close`方法。Java 库和第三方库中的许多类和接口都实现了`AutoCloseable`。如果你编写了一个表示必须关闭的资源的类，你的类就应该实现`AutoCloseable`。以下是使用`try`-with-resources 后我们第一个示例的写法：

```java
// try-with-resources - 关闭资源的最佳方式！
static String firstLineOfFile(String path) throws IOException {
    try (BufferedReader br = new BufferedReader(new FileReader(path))) {
        return br.readLine();
    }
}
```

这里是使用`try`-with-resources 后我们第二个示例的写法：

```java
// 多个资源使用 try-with-resources - 简洁高效
static void copy(String src, String dst) throws IOException {
    try (InputStream in = new FileInputStream(src);
         OutputStream out = new FileOutputStream(dst)) {
        byte[] buf = new byte[BUFFER_SIZE];
        int n;
        while ((n = in.read(buf)) >= 0)
            out.write(buf, 0, n);
    }
}
```

`try`-with-resources 版本不仅比原始版本更短、更易读，而且它们提供了更好的诊断信息。如果`readLine`调用和（不可见的）`close`都抛出了异常，后者会被*抑制*以优先保留前者。事实上，多个异常并非简单地被丢弃；它们会在堆栈跟踪中打印，并注明它们被抑制了。你还可以通过`getSuppressed`方法以编程的方式访问它们，该方法是在 Java 7 中添加到`Throwable`中的。

你可以像在`try`-`finally`语句上一样，为`try`-with-resources 语句添加`catch`子句。这允许你处理异常，而无需让代码陷入嵌套。作为一个略显构造的示例，这里是我们的`firstLineFile`方法，它不抛出异常，但在无法打开或读取文件时返回一个默认值：

点击此处查看代码图片

```java
// 带有 catch 子句的 try-with-resources
static String firstLineOfFile(String path, String defaultVal) {
    try (BufferedReader br = new BufferedReader(new FileReader(path))) {
        return br.readLine();
    } catch (IOException e) {
        return defaultVal;
    }
}
```

结论是：处理必须关闭的资源时，始终优先使用`try`-with-resources 而不是`try`-finally`。生成的代码更短更清晰，生成的异常更有用。`try`-with-resources 语句使得编写关闭资源的正确代码变得简单，而这在使用`try`-finally`时几乎是不可能的。

## 第 3 章 所有对象的通用方法

尽管`Object`是一个具体类，但它的主要设计目的是扩展。它所有的非 final 方法（`equals`、`hashCode`、`toString`、`clone`和`finalize`）都有明确的*通用约定*，因为它们被设计重写。重写这些方法的类有责任遵守这些通用约定；否则会导致依赖这些契约的其他类（如`HashMap`和`HashSet`）无法与该类正常协作。

本章将告诉你何时以及如何重写非 final`Object`方法。`finalize`方法未在本章讨论，因为它已经在 Item 8 中讨论过。虽然它不是`Object`方法，但`Comparable.compareTo`也在本章中讨论了它，因为它具有类似的特征。

重写`equals`方法看起来非常简单，但有很多种出错的方法，后果可能是灾难性的。避免问题最简单的方法是不重写`equals`方法，在这种情况下，类的每个实例只与它自己相等。如果满足以下任何条件，这样做就是正确的：

- **类的每个实例在本质上都是唯一的。** 这对于像`Thread`这样表示活动实体而非值的类来说是事实。`Object`提供的`equals`实现对这些类具有恰当的行为。

- **该类不需要提供“逻辑相等性”测试。** 例如，`java.util.regex.Pattern`本可以重写`equals`来检查两个`Pattern`实例是否表示完全相同的正则表达式，但设计者认为客户端并不需要或想要这种功能。在这种情况下，继承自`Object`的`equals`实现是理想的。

- **父类已经重写了`equals`，且父类的行为适用于该类。** 例如，大多数`Set`实现都从`AbstractSet`继承其`equals`实现，`List`实现从`AbstractList`继承，而`Map`实现从`AbstractMap`继承。

- **该类是私有的或包私有的，且你确定其`equals`方法永远不会被调用。** 如果你极度规避风险，可以重写`equals`方法以确保它不会意外调用：

点击此处查看代码图片

```java
@Override public boolean equals(Object o) {
    throw new AssertionError(); // 方法永远不会被调用
}
```

那么，什么时候重写`equals`是合适的呢？当一个类具有逻辑相等的概念，且该概念不同于仅仅的对象恒等性，且父类尚未重写`equals`时，就是合适的。这通常适用于值类（value classes）。值类简单来说表示值的类，例如`Integer`或`String`。使用`equals`方法比较值对象引用的程序员期望的是判断它们在逻辑上是否等价，而不是判断它们是否引用同一个对象。重写`equals`方法不仅对于满足程序员的预期是必要的，还能让实例能够作为 map 的键或 set 的元素，并具有可预测且符合预期的行为。

一种不需要重写`equals`方法的值类是使用实例控制（Item 1）来确保每个值最多存在一个类。枚举类型（Item 34）属于这一类。对于这些类，逻辑相等等同于对象恒等，因此`Object`的`equals`方法就可以作为逻辑`equals`方法。

当你重写`equals`方法时，必须遵守它的通用约定。以下是来自`Object`规范的约定：

`equals`方法实现等价关系。它具有以下属性：

- **反射性**：对于任何非空引用值`x`，`x.equals(x)`必须返回`true`。

- **对称性**：对于任何非空引用值`x`和`y`，`x.equals(y)`返回`true`当且仅当`y.equals(x)`返回`true`。

- **传递性**：对于任何非空引用值`x`、`y`、`z`，如果`x.equals(y)`返回`true`且`y.equals(z)`返回`true`，则`x.equals(z)`必须返回`true`。

- **一致性**：对于任何非空引用值`x`和`y`，多次调用`x.equals(y)`必须一致返回`true`或一致返回`false`，前提是`equals`中使用的任何信息都没有被修改。

- 对于任何非空引用值`x`，`x.equals(null)`必须返回`false`。

除非你对数学很感兴趣，否则这看起来可能吓人，但不要忽略它！如果你违反了它，你可能会发现程序行为异常或崩溃，而且定位失败原因可能非常困难。引用但恩的话说，没有类是孤岛。一个类的实例经常被传递给另一个类。许多类（包括所有集合）都依赖于传递给它们遵守`equals`约定。

既然你已经意识到了违反`equals`约定的危险，让我们详细回顾一下。好消息是，尽管外表如此，它实际上并不复杂。一旦你理解了它，遵守它并不难。

那么什么是等价关系？通俗地说，它是将元素集合划分为若干部分的运算符，其中的元素被视为与另一个元素相等。这些子集被称为等价类。为了使`equals`方法有用，每个等价类中的所有元素从用户的角度来看都必须是互换的。现在让我们检查这五个要求：

**反射性**：第一个要求说对象必须与自身相等。很难想象会无意中违反这一点。如果你无意中违反了它并将你的类实例添加到集合中，`contains`方法很可能会说集合并不包含你刚刚添加的那个实例。

**对称性**：第二个要求任何两个对象必须在它们是否相等上达成共识。与第一个要求不同，很难想象会无意中违反这一点。例如，考虑以下类，它实现了一个不区分大小写的字符串。字符串的大小由`toString`保留但在`equals`比较中被忽略：

点击此处查看代码图片

```java
// 错误 - 违反了对称性！
public final class CaseInsensitiveString {
    private final String s;
    public CaseensitiveString(String s) {
        this.s = Objects.requireNonNull(s);
    }

    // 错误 - 违反了对称性！
    @Override public boolean equals(Object o) {
        if (o instanceof CaseInsensitiveString) {
            return s.equalsIgnoreCase(((CaseInsensitiveString) o).s);
        }
        if (o instanceof String) // 单向互操作性！
            return s.equalsIgnoreCase((String) o);
        }
        return false;
    }
    // ... 省略剩余
}
```

该类中意良好的`equals`方法天真地尝试与普通字符串互操作。假设我们有一个不区分大小写的字符串和一个普通的字符串：

点击此处查看代码图片

```java
CaseInsensitiveString cis = new CaseensitiveString("Polish");
String s = "polish";
```

正如预期，`cis.equals(s)`返回`true`。问题在于，虽然`CaseInsensitiveString`的`equals`方法认识普通字符串，但`String`的`equals`方法忽略不区分大小写的字符串。因此，`s.equals(cis)`返回`false`，这显然违反了对称性。假设你将一个不区分大小写的字符串放入集合中：

点击此处查看代码图片

```java
List<CaseInsensitiveString> list = new ArrayList<>();
list.add(cis);
```

在此时，`list.contains(s)`返回什么？谁知道呢？在当前的 OpenJDK 实现中，它恰好返回`false`，但这仅仅是实现上的产物。在另一种实现中，它完全可能返回`true`或抛出运行时异常。一旦你违反了`equals`约定，你就无法知道其他对象在遇到你的对象时会如何表现。

要消除这个问题，只需从`equals`方法中删除与`String`互操作的错误尝试即可。一旦这样做，你就可以将该方法重构为单条返回语句：

点击此处查看代码图片

```java
@Override public boolean equals(Object o) {
    return o instanceof CaseInsensitiveString &&
           ((CaseInsensitiveString) o).s.equalsIgnoreCase(s);
}
```



### 传递性

`equals` 合约的第三个要求是：如果一个对象等于第二个对象，而第二个对象等于第三个对象，那么第一个对象必须等于第三个对象。同样，想象在无意中违反这一要求并不困难。考虑一种向其父类添加了新的*值组件*（value component）的子类情况。换句话说，子类添加了一部分影响 `equals` 比较的信息。让我们从一个简单的不可变二维整数点类开始：

```java
public class Point {
    private final int x;
    private final int y;
    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
    @Override public boolean equals(Object o) {
        if (!(o instanceof Point))
            return false;
        Point p = (Point)o;
        return p.x == x && p.y == y;
    }
    ...  // 剩余部分省略
}
```

假设你想扩展这个类，为点引入颜色的概念：

```java
public class ColorPoint extends Point {
    private final Color color;
    public ColorPoint(int x, int y, Color color) {
        super(x, y);
        this.color = color;
    }
    ...  // 剩余部分省略
}
```

`equals` 方法应该写什么样？如果你完全不写它，它将继承 `Point` 的实现，且在 `equals` 比较会忽略颜色信息。虽然这没有违反 `equals` 合约，但显然是不可接受的。假设你写了一个 `equals` 方法，只有当参数是另一个位置和颜色都相同的 `ColorPoint` 时才返回 `true`：

```java
// 错误 - 违反了对称性！
@Override public boolean equals(Object o) {
    if (!(o instanceof ColorPoint))
      return false;
    return super.equals(o) && ((ColorPoint) o).color == color;
}
```

这种方法的问题在于，当你比较一个点和一个颜色点（以及反之）时，可能会得到不同的结果。前者比较忽略了颜色，而后者比较因为参数类型不正确而始终返回 `false`。为了具体化这一点，让我们创建一个点和一个颜色点：

```java
Point p = new Point(1, 2);
ColorPoint cp = new ColorPoint(1, 2, Color.RED);
```

然后 `p.equals(cp)` 返回 `true`，而 `cp.equals(p)` 返回 `false`。你可能尝试通过让 `ColorPoint.equals` 在进行“混合比较”时忽略颜色来修复此问题：

```java
// 错误 - 违反了传递性！
@Override public boolean equals(Object o) {
    if (!(o instanceof Point))
        return false;
    // 如果 o 是普通的 Point，进行盲色比较
    if (!(o instanceof ColorPoint))
        return o.equals(this);
    // o 是 ColorPoint；进行完整比较
    return super.equals(o) && ((ColorPoint) o).color == color;
}
```

这种方法确实提供了对称性，但是以牺牲传递性为代价的：

```java
ColorPoint p1 = new ColorPoint(1, 2, Color.RED);
Point p2 = new Point(1, 2);
ColorPoint p3 = new ColorPoint(1, 2, Color.BLUE);
```

现在 `p1.equals(p2)` 和 `p2.equals(p3)` 返回 `true`，而 `p1.equals(p3)` 返回 `false`，这显然违反了传递性。前两次比较是“盲色的”，而第三次比较考虑了颜色。此外，这种方法可能会导致无限递归：假设存在 `Point` 的子类，例如 `ColorPoint` 和 `SmellPoint`，它们都具有这种 `equals` 方法。那么调用 `myColorPoint.equals(mySmellPoint)` 将抛出 `StackOverflowError`。

那么解决方案是什么呢？事实证明，这是面向对象语言中等价关系的一个根本问题。除非你愿意放弃面向对象抽象的好处，否则没有办法在扩展可实例化的类并添加值组件的同时保留 `equals` 合约。你可能会听说，通过在 `equals` 方法中使用 `getClass` 测试来代替 `instanceof` 测试，可以在扩展可实例化的类并添加值组件的同时保留 `equals` 合约：

```java
// 错误 - 违反了里氏夫替换原则（第 43 页）
@Override public boolean equals(Object o) {
    if (o == null || o.getClass() != getClass())
      return false;
    Point p = (Point) o;
    return p.x == x && p.y == y;
}
```

这种方法的效果是仅当对象具有相同的实现类时才被视为相等。这看起来可能并不坏，但后果是不可接受的：`Point` 子类的实例仍然是一个 `Point`，它仍然需要像 `Point` 一样工作，但如果你采取这种方法，它就无法做到！假设我们想写一个方法来判断点是否在单位圆上。这是我们可以实现的一种方法：

```java
// 初始化 unitCircle 包含所有单位圆上的点
private static final Set<Point> unitCircle = Set.of(
    new Point(1, 0), new Point(0, 1),
    new Point(-1, 0), new Point(0, -1));
public static boolean onUnitCircle(Point p) {
    return unitCircle.contains(p);
}
```

虽然这可能不是实现功能最快的方法，但它可以运行良好。假设你以某种微不足道的方式扩展了 `Point` 但没有添加值组件，例如通过让构造函数跟踪创建了多少个实例：

```java
public class CounterPoint extends Point {
    private static final AtomicInteger counter = new AtomicInteger();
    public CounterPoint(int x, int y) {
        super(x, y);
        counter.incrementAndGet();
    }
    public static int numberCreated() { return counter.get(); }
}
```

*里氏夫替换原则*规定，类型的任何重要属性都应适用于所有子类型，以便为该类型编写的方法可以同样良好。这是我们之前主张的正式说法：`Point` 的子类（如 `CounterPoint`）仍然是一个 `Point` 并必须像 `Point` 一样工作。但假设我们将一个 `CounterPoint` 传递给 `onUnitCircle` 方法。如果 `Point` 类使用基于 `getClass` 的 `equals` 方法，无论 `CounterPoint` 实例的 `x` 和 `y` 坐标如何，`onUnitCircle` 方法都会返回 `false`。这是因为大多数集合（包括 `onUnitCircle` 方法使用的 `HashSet`）使用 `equals` 方法测试包含性，而没有 `CounterPoint` 实例等于任何 `Point`。然而，如果你在 `Point` 上使用正确的基于 `instanceof` 的 `equals` 方法，那么在面对 `CounterPoint` 实例时，同样的 `onUnitCircle` 方法就能正常工作。

虽然没有令人满意的方法来扩展可实例化的类并添加值组件，但有一个很好的变通方法：遵循项 18 的建议，“组合优于继承”。不要让 `ColorPoint` 继承 `Point`，而是给 `ColorPoint` 提供一个私有的 `Point` 字段和一个公共的*视图*方法（项 6），返回与该颜色点位置相同的点：

```java
// 在不违反 equals 合约的情况下添加值组件
public class ColorPoint {
    private final Point point;
    private final Color color;
    public ColorPoint(int x, int y, Color color) {
        point = new Point(x, y);
        this.color = Objects.requireNonNull(color);
    }
    /**
     * 返回此颜色点的点视图。
     */
    public Point asPoint() {
        return point;
    }
}
```

```java
  }

  @Override public boolean equals(Object o) {

      if (!(o instanceof ColorPoint))
          return false;
      ColorPoint cp = (ColorPoint) o;
      return cp.point.equals(point) && cp.color.equals(color);
  }

  ... // Remainder omitted
}
```

Java 平台库中存在一些类继承了可实例化的类，并添加了值组件。例如，`java.sql.Timestamp` 继承了 `java.util.Date` 并增加了一个 `nanoseconds` 字段。`Timestamp` 的 `equals` 实现确实违反了对称性，如果将 `Timestamp` 和 `Date` 对象用在同一个集合中或进行混合使用，会导致不可预测的行为。`Timestamp` 类有一个免责声明，警告程序员不要混合使用日期和时间戳。只要你将它们分开使用，就不会遇到麻烦，但没有什么可以阻止你将它们混合，而产生的错误可能很难调试。`Timestamp` 类的这种行为是一个错误，不应该被模仿。

请注意，你*可以*在*抽象*类的子类中添加值组件，而不必违反 `equals` 合约。这对于遵循 Item 23 “优先使用类层次结构而不是标记类”建议而得到的类层次结构来说是极其重要的。例如，你可以有一个没有值组件的抽象类 `Shape`，一个增加了 `radius` 字段的子类 `Circle`，以及一个增加了 `length` 和 `width` 字段的子类 `Rectangle`。只要无法直接创建父类实例，就不会出现前面所示的问题。

### 一致性

`equals` 合约的第四个要求是：如果两个对象相等，它们在任何时候都保持相等，除非其中一个（或两个）被修改。换句话说，可变对象可以在不同的时间等于不同的对象，而不可变对象不能。当你编写一个类时，要仔细考虑它是否应该是不可变的（Item 17）。如果你认为它应该是不可变的，请确保你的 `equals` 方法强制执行这一限制：相等的对象始终保持相等，不相等的对象始终保持不相等。

无论一个类是否不可变，都不要编写依赖于不可靠资源的 `equals` 方法。如果你违反了这一禁令，要满足一致性要求极其困难。例如，`java.net.URL` 的 `equals` 方法依赖于与 URL 关联的主机 IP 地址的比较。将主机名转换为 IP 地址可能需要访问网络，并且无法保证随着时间的推移产生相同的结果。这会导致 `URL equals` 方法违反 `equals` 合约，并在实践中引起过问题。`URL` 的 `equals` 方法的行为是一个错误，不应该被模仿。遗憾的是，由于兼容性要求，它无法更改。为了避免这类问题，`equals` 方法应该只对内存中的对象进行确定性的计算。

### 非空性

最后一个要求缺乏官方名称，因此我权将其命名为“非空性”。它规定所有对象都不能等于 `null`。虽然很难想象在调用 `o.equals(null)` 时会意外返回 `true`，但想象意外抛出 `NullPointerException` 并不困难。通用合约禁止了这种行为。许多类的 `equals` 方法通过显式的 `null` 测试来防止这种情况：

```java
@Override public boolean equals(Object o) {

    if (o == null)
        return false;

    ...
}
```

这种测试是不必要的。为了测试参数的相等性，`equals` 方法必须先将其参数强制转换为适当的类型，以便调用其访问器或访问其字段。在进行强制转换之前，方法必须使用 `instanceof` 运算符来检查其参数是否为正确类型：

```java
@Override public boolean equals(Object o) {

    if (!(o instanceof MyType))
          return false;
    MyType mt = (MyType) o;

    ...
}
```

如果缺少此类型检查且向 `equals` 方法传递了类型错误的参数，`equals` 方法将抛出 `ClassCastException`，这违反了 `equals` 合约。但根据规定，`instanceof` 运算符如果第一个操作数是 `null`，则返回 `false`，无论第二个操作数中出现什么类型 [JLS, 15.20.2]。因此，如果传入 `null`，类型检查将返回 `false`，所以你不需要显式的 `null` 检查。

综上所述，这里有一个高质量 `equals` 方法的配方：

1. 使用 `==` 运算符检查参数是否是此对象的引用。如果是，返回 `true`。这仅仅是一种性能优化，但如果比较开销可能很大，这样做是值得的。

2. 使用 `instanceof` 检查参数是否具有正确类型。如果不是，返回 `false`。通常情况下，正确类型是该方法所在的类。

3. 将参数强制转换为正确类型。因为在强制转换之前进行了 `instanceof` 测试，所以可以保证转换成功。

4. 对于类中的每个“重要”的字段，检查参数的该字段是否匹配此对象的相应字段。如果所有这些测试都成功，返回 `true`；否则返回 `false`。如果第 2 步中的类型是接口，你必须通过接口方法访问；如果类型是类，取决于访问权限，可能可以直接访问字段。

对于类型不是 `float` 或 `double` 的原始类型字段，使用 `==` 运算符进行比较；对于对象引用字段，递归调用 `equals` 方法；对于 `float` 字段，使用静态方法 `Float.compare(float, float)`；对于 `double` 字段，使用 `Double.compare(double, double)`。对 `float` 和 `double` 字段的特殊处理由于 `Float.NaN`、`-0.0f` 以及相应的 `double` 值的存在而变得必要；详见 JLS 15.21.1 或 `Float.equals` 的文档。虽然可以使用静态方法 `Float.equals` 和 `Double.equals` 来比较 `float` 和 `double` 字段，但每次比较都会涉及装箱，性能很差。对于数组字段，将这些指南应用于每个元素。如果数组字段中的每个元素都是重要的，请使用 `Arrays.equals` 方法之一。

某些对象引用字段可能合法地包含 `null`。为了避免抛出 `NullPointerException` 的可能，使用静态方法 `Objects.equals(Object, Object)` 检查此类字段的相等性。

对于某些类（例如上面的 `CaseInsensitiveString`），字段比较比简单的相等测试更复杂。如果是，你可能希望存储字段的*规范形式*（canonical form），这样 `equals` 方法就可以对规范形式进行廉价的精确比较，而不是进行更昂贵的非标准比较。这种技术最适用于不可变类（Item 17）；如果对象可以改变，你必须保持规范形式更新。

`equals` 方法的性能可能会受比较字段顺序的影响。为了获得最佳性能，你应该首先比较那些更有可能不同、比较开销较小的字段，或者理想情况下，两者兼具。你不能比较不属于对象逻辑状态的字段，例如用于同步操作的锁字段。你不需要比较 `derived fields`（派生字段），这些字段可以从“重要字段”计算出来，但这样做可能会提高 `equals` 方法的性能。如果一个派生字段等同于整个对象的摘要描述，那么在比较失败时，比较该字段将节省你比较实际数据的开销。例如，假设你有一个 `Polygon` 类，并缓存了面积。如果两个多边形的面积不相等，你就不必去比较它们的边和顶点了。



当你写完`equals`方法后，问问自己三个问题：它是对称的吗？它具有传递性吗？它是一致的吗？而且不要仅仅自问自，要编写单元测试来检查，除非你使用了`AutoValue`（第 49 页）来生成`equals`方法，在这种情况下你可以安全地省略测试。如果这些属性不成立，请找出原因并相应地修改`equals`方法。当然，你的`equals`方法还必须满足另外两个属性（自反射性和非空性），但这两个通常会自动处理好。

按照前述配方构建的`equals`方法在下面这个简单的`PhoneNumber`类中：

```java
// 具有典型 equals 方法的类
public final class PhoneNumber {

    private final short areaCode, prefix, lineNum;

    public PhoneNumber(int areaCode, int prefix, int lineNum) {
        this.areaCode = rangeCheck(areaCode, 999, "area code");
        this.prefix  = rangeCheck(prefix, 999, "prefix");
        this.lineNum  = rangeCheck(lineNum, 9999, "line num");
    }

    private static short rangeCheck(int val, int max, String arg) {
        if (val < 0 || val > max)
            throw new IllegalArgumentException(arg + ": " + val);
        return (short) val;
    }

    @Override
    public boolean equals(Object o) {
        if (o == this)
            return true;
        if (!(o instanceof PhoneNumber))
            return false;
        PhoneNumber pn = (PhoneNumber)o;
        return pn.lineNum == lineNum && pn.prefix == prefix
               && pn.areaCode == areaCode;
    }

    ... // 省略其余部分
}
```

这里有几个最后的注意事项：

- **在重写`equals`时，务必重写`hashCode`** (Item 11)。

- **不要试图表现太聪明。** 如果你只是简单地测试字段是否相等，要遵守`equals`约并不难。如果你在寻找等价性时过于激进，很容易陷入麻烦。考虑任何形式的别名（aliasing）通常都是个坏主意。例如，`File`类不应该尝试等同指向同一个文件的符号链接。幸运的是，它并没有这样做。

- **不要在`equals`声明中用其他类型替换`Object`。** 程序员写一个像这样的`equals`方法并不罕见，然后花费几个小时困惑为什么它工作不正常：

```java
// 错误 - 参数类型必须是 Object！
public boolean equals(MyClass o) {
    ...
}
```

问题在于，该方法并没有*重写*`Object.equals`（其参数类型为`Object`类型），而是*重载*了它 (Item 52)。即使在提供了正常方法的情况下，提供这样一个“强类型”的`equals`方法也是不可接受的，因为这可能导致子类中的`Override`注解失败。

## Item 11：在重写`equals`时，务必重写`hashCode`

你必须在每个重写了`equals`的类中重写`hashCode`。如果你这样做，你的类将违反`hashCode`的通用合约，这将导致它无法在`HashMap`和`HashSet`等集合中正常工作。以下是根据`Object`规范改编的合约：

- 在应用程序执行期间反复对对象调用`hashCode`方法时，只要`equals`比较中使用的任何信息没有被修改，它必须一致地返回相同的值。该值不需要在应用程序的多次执行之间保持一致。

- 如果两个对象根据`equals(Object)`方法是相等的，那么在这两个对象上调用`hashCode`必须产生相同的整数结果。

- 如果两个对象根据`equals(Object)`方法是不相等的，*并不要求*对每个对象调用`hashCode`产生不同的结果。然而，程序员应该意识到，为不相等的对象产生不同的结果可能会提高哈希表的性能。

当你未能重写`hashCode`时违反的关键条款是第二条：相等的对象必须具有相等的哈希码。两个不同的实例根据类的`equals`方法在逻辑上可能是相等的，但对于`Object`的`hashCode`方法来说，它们只是两个没有多少共同点的对象。因此，`Object`的`hashCode`方法返回了两个看似随机的数字，而不是合约要求的两个相等数字。

例如，假设你尝试使用 Item 10 中的`PhoneNumber`类实例作为`HashMap`的键：

```java
Map<PhoneNumber, String> m = new HashMap<>();
m.put(new PhoneNumber(707, 867, 5309), "Jenny");
```

此时，你可能期望`m.get(new PhoneNumber(707, 867, 5309))`会返回`"Jenny"`，但实际上，它返回了`null`。注意这里涉及到两个`PhoneNumber`实例：一个用于插入`HashMap`，而另一个等价实例用于（尝试）检索。`PhoneNumber`类没有重写`hashCode`，导致两个等价实例具有不相同的哈希值，这违反了`hashCode`契约。因此，`get`方法可能会在一个不同的哈希桶中查找电话号码，而不是它被`put`方法存储的那个桶。即使这两个实例恰好哈希到同一个桶中，`get`方法也几乎肯定会返回`null`，因为`HashMap`有一种优化：它会缓存与每个条目相关的哈希值，如果哈希值不匹配，它就不会去检查对象的相等性。

修复这个问题只需要为`PhoneNumber`写一个适当的`hashCode`方法。那么，一个好的`hashCode`方法应该是什么样的呢？写一个糟糕的方法易如反。例如下面这个方法总是合法的，但绝不应该被使用：

```java
// 最糟糕的合法 hashCode 实现 - 永远不要使用！
@Override public int hashCode() { return 42; }
```

合法的，因为它确保了等价对象具有相同的哈希值。它是可怕的，因为它确保了*每一个*对象都有相同的哈希值。因此，每个对象都哈希到同一个桶中，哈希表退化为链表。本应在线性时间内运行的程序改为在二次方时间内运行。对于大型哈希表来说，这是正常工作与无法运行之间的区别。

一个良好的哈希函数倾向于为不相等的实例产生不相同的哈希值。这正是`hashCode`契约第三部分的含义。理想情况下，哈希函数应该将任何合理的不等价实例集合均匀地分布在所有`int`值上。实现这一理想可能困难。幸运的是，实现一个公平的近似并不难。这里有一个简单的配方：

1. 声明一个名为`result`的`int`变量，并将其初始化为对象第一个显著字段的哈希值`c`，如步骤 2.a 所计算。（回想 Item 10，显著字段是指影响 equals 比较的字段。）

2. 对于对象中的每个剩余显著字段`f`，执行以下操作：

   a. 为该字段计算一个`int`哈希值`c`：

      i. 如果字段是基本类型，计算`Type.hashCode(f)`，其中`Type`是与`f`类型对应的装箱基本类型类。

      ii. 如果该字段是对象引用，且该类的`equals`方法通过递归调用`equals`来比较该字段，则对该字段递归调用`hashCode`。如果需要更复杂的比较，则为该字段计算一个“规范表示”，并对该规范表示调用`hashCode`。如果字段的值为`null`，则使用`0`（或其他常数，但`0`是传统做法）。

      iii. 如果字段是数组，则将其视为每个显著元素都是一个独立的字段。也就是说，通过递归应用这些规则为每个显著元素计算哈希值，并按照步骤 2.b 组合这些值。如果数组没有显著元素，使用一个常量，最好不是`0`。如果所有元素都是显著的，使用`Arrays.hashCode`。

   b. 如下方式将步骤 2.a 计算的哈希值`c`组合到`result`中：

```java
result = 31 * result + c;
```

3. 返回`result`。

写完`hashCode`方法后，问问自己等价实例是否具有相同的哈希值。编写单元测试来验证你的直觉（除非你使用 AutoValue 来生成`equals`和`hashCode`方法，如果是那样，你可以安全地省略这些测试）。如果等价实例具有不相同的哈希值，找出原因并修复问题。

你可以从哈希值计算中排除*派生字段*。换句话说，你可以忽略任何值可以从包含在计算中的字段中得出的字段。你*必须*排除任何未在`equals`比较中使用的字段，否则你可能会违反`hashCode`契约的第二条规定。

步骤 2.b 中的乘法使得结果依赖于字段的顺序，如果类有多个相似的字段，这将产生更好的哈希函数。例如，如果在`String`哈希函数中省略了乘法，所有的字母位词都具有相同的哈希值。选择 31 是因为它是一个奇质数。如果它是偶数且乘法溢出，信息将会丢失，因为乘以 2 等同于位移。使用质数的优势并不那么明显，但它是传统做法。31 的一个很好的属性是，乘法可以用位移和减法代替，以在某些架构上获得更好的性能：`31 * i == (i << 5) - i`。现代虚拟机会自动进行这种优化。

让我们将之前的配方应用于`PhoneNumber`类：

```java
// 典型的 hashCode 方法
@Override public int hashCode() {
    int result = Short.hashCode(areaCode);
    result = 31 * result + Short.hashCode(prefix);
    result = 31 * result + Short.hashCode(lineNum);
    return result;
}
```

因为该方法返回了简单计算的结果，对于这三个显著字段，等价的`PhoneNumber`实例具有相同的哈希值。事实上，该方法对于`PhoneNumber`来说是一个非常好的`hashCode`实现，与 Java 库中的实现相当。它简单、运行较快，并在分散不相等数值桶方面做得良好。

虽然此节中的配方产生了相当好的哈希函数，但它们并不是顶尖的。它们的质量与平台库中的值类型哈希函数相当，适用于大多数场景。如果你确实需要不容易冲突的哈希函数，请参见 Guava 的`com.google.common.hash.Hashing`。

`Objects`类有一个静态方法接收任意数量的对象并返回它们的哈希值。名为`hash`的方法让你写出单行的`hashCode`方法，其质量与本文写的相当。遗憾的是，它们运行较慢，因为需要创建数组来传递数量参数，而且如果参数是基本类型，还会涉及装箱和拆箱。这种风格的哈希函数建议仅在性能关键的情况下使用。这是一个使用该技术编写的`PhoneNumber`哈希函数：

```java
// 单行 hashCode 方法 - 性能中庸
@Override public int hashCode() {
    return Objects.hash(lineNum, prefix, areaCode);
}
```

如果一个类是不可变的且计算哈希值的代价很高，你可以考虑在对象中缓存哈希值，而不是每次请求时都重新计算。如果你认为该类型的多数对象将用作哈希键，那么你应该在创建实例时计算哈希值。否则，你可能会选择在第一次调用`hashCode`时*延迟初始化*哈希值。需要一些小心以确保在存在延迟初始化字段的情况下类保持线程安全（参见 Item 83）。我们的`PhoneNumber`类不需要这种处理，但为了向你展示如何操作，这里所示。注意`hashCode`字段的初始值（在此例中为 0）不应该是常用创建实例的哈希值：

```java
// 使用惰性初始化缓存哈希值的 hashCode 方法
private int hashCode; // 初始化为 0

@Override public int hashCode() {
    int result = hashCode;
    if (result == 0) {
        result = Short.hashCode(areaCode);
        result = 31 * result + Short.hashCode(prefix);
        result = 31 * result + Short.hashCode(lineNum);
        hashCode = result;
    }
    return result;
}
```

**不要为了提高性能而试图从哈希计算中排除重要字段。** 虽然生成的哈希函数可能运行得更快，但其糟糕的质量可能会导致哈希表的性能下降到无法使用的地步。特别是，哈希函数可能会遇到大量主要区别在于你所忽略的区域的实例。如果发生这种情况，哈希函数会将所有这些实例映射到少数几个哈希值，本应该在线性时间内运行的程序将改为在二次级时间内运行。

这不仅仅是一个理论问题。在 Java 2 之前，`String`哈希函数使用字符串中均匀分布的最多 16 个字符，从第一个字符开始。对于像 URL 这样的层次名称的大型集合，该函数表现出了与上述完全相同的病态行为。

**不要为`hashCode`返回的值提供详细的规范，这样客户端就无法合理地依赖它；这赋予了你更改它的灵活性。** Java 库中的许多类（如`String`和`Integer`）都指定了其`hashCode`方法返回的精确值，作为实例值的函数。这*不是*一个好主意，而是我们被迫接受的一个错误：它阻碍了在未来发布中改进哈希函数的能力。如果你不指定细节，并且在哈希函数中发现了缺陷或发现了更好的哈希函数，你可以在后续发布中更改它。

总而言之，每当你重写`equals`时，*必须*重写`hashCode`，否则你的程序将无法正常运行。你的`hashCode`方法必须遵守`Object`中指定的通用约定，并能够合理地为不相等的实例分配不同的哈希值。使用第 51 页的配方，这很容易实现（虽然稍微有一点点无聊）。正如第 10 节所提到的，AutoValue 框架提供了一个手动编写`equals`和`hashCode`方法的良好替代方案，IDE 也提供了此类部分功能。

## 第 12 节：始终重写`toString`

虽然`Object`提供了`toString`方法的实现，但它返回的字符串通常不是你的类的用户想要看到的。它由类名、紧随后的“at”符号（`@`）以及哈希值的无符号十六进制表示组成，例如`PhoneNumber@163b91`。`toString`的通用约定说，返回的字符串应该是“一个简洁但包含信息的表示，便于人类阅读”。虽然可以认为`PhoneNumber@163b91`是简洁且易读的，但与`707-867-5309`相比，它并没有包含多少信息。`toString`约定继续说：“建议所有子类都重写此方法。”这确实是很好的建议！

虽然这不像遵守`equals`和`hashCode`约定那样关键（第 10 节和 第 11 节），但**提供良好的`toString`实现会让你的类变得更加易用，并让使用该类的系统更易调试**。当对象传递给`println`、`printf`、字符串拼接操作符或`assert`，或者由调试器进行打印时，`toString`方法会被自动调用。即使你从未对对象调用过`toString`，其他人可能也会。例如，一个拥有你对象引用的组件可能会在记录错误消息时包含该对象的字符串表示。如果你未能重写`toString`，该信息可能几乎毫无用处。

如果你为`PhoneNumber`提供了一个良好的`toString`方法，生成实用的诊断信息就像这样：

```java
System.out.println("Failed to connect to " + phoneNumber);
```

无论你是否重写了`toString`，程序员都会以这种方式生成诊断信息，但除非你重写了，否则信息是没有用的。提供良好的`toString`方法的好处不仅适用于类的实例，还适用于包含这些实例引用的对象，特别是集合。在打印 map 时，你更倾向于看到`{Jenny=PhoneNumber@163b91}`还是`{Jenny=707-867-5309}`？



在实际情况下，`toString` 方法应该返回对象中包含*所有*有趣信息，正如电话号码示例所示。如果对象很大或者它包含不利于字符串表示的状态，则是不切行的。在这种情况下，`toString` 应该返回一个摘要，例如 `Manhattan residential phone directory (1487536 listings)` 或 `Thread[main,5,main]`。理想情况下，字符串应该是自解释的。（`Thread` 的示例就未达到此标准。）未能在其字符串表示中包含对象所有信息的一个特别恼人的代价是，测试报告看起来像这样：

点击此处查看代码图片 断言失败：`{abc, 123}`。实现 `toString` 时你必须做的一个重要决定是是否指定格式。建议对*值类*（如电话号码）这样做。指定格式的优点是它可以作为标准的、无歧的、人类可读的表示。这种表示可以用于输入输出以及持久化数据。如果你指定了格式，通常最好提供匹配的静态工厂方法或构造函数，以便程序员可以在对象和字符串表示之间进行转换。这种方法被 Java 平台的许多值类采用，包括 `BigInteger`、`BigDecimal` 和大部分原始类。

指定 `toString` 返回值的格式的缺点是，一旦你指定，只要该类被广泛使用，你就受限于它。程序员会编写代码来解析、生成表示并将其嵌入持久化数据。如果你在未来的发布中更改表示，就会破坏他们的代码和数据。通过选择不指定格式，你保留了在后续发布中添加信息或改进格式的灵活性。

无论你是否决定指定格式，都应该明确说明你的意图。如果你指定了格式，你应该精确地指定。例如，这是与第 11 节](#ch3.xhtml_lev11) 中的 `PhoneNumber` 类对应的 `toString` 方法：

点击此处查看代码图片

```java
/**
 * 返回电话号码的字符串表示。
 * 字符串由十二个字符组成，格式为
 * "XXX-YYY-ZZZZ"，其中 XXX 是区码，YYY 是前缀，ZZZZ 是线路号码。
 * 每个大写字母代表一个十进制数字。
 *
 * 如果电话号码的三个部分任何一个太小无法填充其字段，
 * 则字段将用前导零填充。
 * 例如，如果线路号码的值为 123，字符串表示的最后四个字符将是 "0123"。
 */
@Override public String toString() {
    return String.format("%03d-%03d-%04d", areaCode, prefix, lineNum);
}
```

如果你决定不指定格式，文档注释应该如下所示：

点击此处查看代码图片

```java
/**
 * 返回此药剂的简要描述。表示形式的具体细节
 * 未指定，且可能会更改，
 * 但以下内容可以被视为典型的：
 *
 * "[药剂 #9: 类型=爱情,气味=松节油,外观=墨水]"
 */
@Override public String toString() { ... }
```

在读完这段注释后，那些编写依赖于格式细节的代码或持久化数据的程序员，当格式发生变化时，除了怪自己外别无怪别人了。

无论你是否指定了格式，都应该对 `toString()` 返回的值中所包含的信息提供程序化的访问方法。例如，`PhoneNumber` 类应该包含获取区号、前缀和线路号码的访问器。如果你没有做到这一点，你就 `force`（强制）了需要这些信息的程序员去解析字符串。除了降低性能和给程序员增加不必要的工作外，这个过程很容易出错，并导致系统在格式更改时崩溃（变得脆弱）。通过不提供访问器，你将字符串格式变成了一个事实上的 API，即使你已经指定过它是可能会更改的。

在静态工具类中编写 `toString()` 方法（Item 4）是没有意义的。你不应该在大多数枚举类型中编写 `toString()` 方法（Item 34），因为 Java 为你提供了一个非常好的实现。然而，你应该在任何子类共享共同字符串表示的抽象类中编写 `toString()` 方法。例如，大多数集合实现的 `toString()` 方法都是继承自抽象集合类的。

Google 开源的 AutoValue 工具（在 Item 10 中讨论过）会为你生成一个 `toString()` 方法，大多数 IDE 也是如此。这些方法非常利于告诉你每个字段的内容，但它们并没有针对类的*含义*进行专门化。因此，例如，对我们的 `PhoneNumber` 类使用自动生成的 `toString()` 方法是不恰当的（因为电话号码有标准的字符串表示），但对于我们的 `Potion` 类来说是完全可以接受的。尽管如此，自动生成的 `toString()` 方法远比继承自 `Object` 的要好得多，后者对对象的值*一无所知*。

总结一下，在你写的每个可实例化类中重写 `Object` 的 `toString()` 实现，除非父类已经这样做了。这使得类的使用变得更加愉快，并有助于调试。`toString()` 方法应该返回一个简洁、实用的描述，并且格式美观。

## Item 13: 谨慎地重写 `clone`

`Cloneable` 接口的设计初衷是作为*混合接口*（Item 20），供类声明它们允许克隆。遗憾的是，它未能实现这一目的。它的主要缺陷是缺少 `clone()` 方法，而 `Object` 的 `clone()` 方法是保护的。在不诉诸*反射*（Item 65）的情况下，你不能仅仅因为对象实现了 `Cloneable` 就调用它的 `clone()`。即使是反射调用也可能失败，因为无法保证对象一定有一个可访问的 `clone()` 方法。尽管存在这个以及许多其他缺陷，该机制仍被广泛使用，因此理解它是有价值的。本项告诉你如何实现一个良好的 `clone()` 方法，讨论了何时这样做是合适的，并提供了替代方案。

既然 `Cloneable` 不包含任何方法，它*到底*做了什么呢？它决定了 `Object` 的保护 `clone()` 实现的行为：如果一个类实现了 `Cloneable`，`Object` 的 `clone()` 方法会返回对象的字段拷贝；否则将抛出 `CloneNotSupportedException`。这是一种非常不典型的接口用法，不值得模仿。通常情况下，即使实现一个接口也会说明该类能为它的客户端提供什么。在这种情况下，它修改了父类中保护方法的行为。

尽管规范没有说明，但实践中，实现 `Cloneable` 的类预计会提供一个运行正常的公共 `clone()` 方法。为了实现这一点，该类及其所有父类必须遵守一个复杂的、不可强制的、文档稀疏的协议。产生的机制是脆弱的、危险的且是*语言之外的*（extralinguistic）：它在不调用构造函数的情况下创建对象。

`clone()` 方法的通用约定是非常弱的。这里是来自 `Object` 规范的内容：

创建并返回此对象的拷贝。“拷贝”的精确含义可能取决于对象的类。通用意图是，对于任何对象 `x`，表达式

```
x.clone() != x
```

将为 `true`，且表达式

点击此处查看代码图片

```
x.clone().getClass() == x.getClass()
```

将为 `true`，但这些并不是绝对的要求。虽然通常情况下

```
x.clone().equals(x)
```

将为 `true`，但这并不是绝对的要求。

按照约定，此方法返回的对象应该通过调用 `super.clone` 获取。如果一个类及其所有父类（`Object` 除外）都遵循这一约定，将会出现：

点击此处查看代码图片

```
x.clone().getClass() == x.getClass()
```

按照约定，返回的对象应该独立于被克隆的对象。为了实现这种独立性，可能在返回之前修改 `super.clone` 返回的对象的一个或多个字段。

这种机制与构造函数链有些相似，不同在于它没有强制执行：如果一个类的 `clone()` 方法返回的不是通过调用 `super.clone` 获取的，而是通过调用构造函数获取的，编译器不会报错，但如果该类的子类调用 `super.clone`，结果对象将具有错误的类，导致子类的 `clone` 方法无法正常工作。如果重写了 `clone` 的类是 `final` 的，则可以忽略这一约定，因为没有需要考虑的子类。但如果一个 `final` 类的 `clone()` 方法没有调用 `super.clone`，那么该类没有理由实现 `Cloneable`，因为它并不依赖 `Object` clone 的行为。

假设你想在一个提供了良好的 `clone()` 方法的类中实现 `Cloneable`。首先调用 `super.clone`。你得到的对象将原始对象的完整副本。类中声明的任何字段都具有与原始对象相同的值。如果每个字段包含原始值或对不可变对象的引用，那么返回的对象可能正是你需要的，在这种情况下不需要进一步处理。例如，Item 11 中的 `PhoneNumber` 类就是如此，但请注意，不可变类不应提供 `clone()` 方法，因为这只会鼓励浪费性的拷贝。在这一前提下，`PhoneNumber` 的 `clone()` 方法看起来如下：

点击此处查看代码图片

```java
// 无可变状态引用的类的 clone 方法
@Override public PhoneNumber clone() {
    try {
        return (PhoneNumber) super.clone();
    } catch (CloneNotSupportedException e) {
        throw new AssertionError(); // 不可能
    }
}
```

为了使这种方法生效，必须修改 `PhoneNumber` 的类声明，以指示它实现了 `Cloneable`。虽然 `Object` 的 `clone` 方法返回的是 `Object`，但这个 `clone` 方法返回的是 `PhoneNumber`。这样做是合法且理想的，因为 Java 支持*协变返回类型*（covariant return types）。换句话说，重写方法的返回类型可以是被重写方法返回类型的子类。这消除了客户端类型转换的需要。我们在返回 `super.clone` 的结果之前，必须将其从 `Object` 强制转换为 `PhoneNumber`，但这种转换保证会成功。

对 `super.clone` 的调用被包含在一个 `try-catch` 块中。这是因为 `Object` 声明其 `clone` 方法会抛出 `CloneNotSupportedException`，这是一个*检查异常*（checked exception）。由于 `PhoneNumber` 实现了 `Cloneable`，我们知道对 `super.clone` 的调用将成功。这种模板代码的存在表明 `CloneNotSupportedException` 应该是一个未检查异常（Item 71）。

如果一个对象包含引用可变对象的字段，前面所示的简单 `clone` 实现可能是灾难性的。例如，考虑 Item 7 中的 `Stack` 类：

点击此处查看代码图片

```java
public class Stack {
    private Object[] elements;
    private int size = 0;
    private static final int DEFAULT_INITIAL_CAPACITY = 16;

    public Stack() {
        this.elements = new Object[DEFAULT_INITIAL_CAPACITY];
    }

    public void push(Object e) {
        ensureCapacity();
        elements[size++] = e;
    }

    public Object pop() {
        if (size == 0)
            throw new EmptyStackException();
        Object result = elements[--size];
        elements[size] = null; // 消除过期引用
        return result;
    }

    // 确保至少留出一个新元素的空间
    private void ensureCapacity() {
        if (elements.length == size)
            elements = Arrays.copyOf(elements, 2 * size + 1);
    }
}
```

假设你想让这个类变为可克隆。如果 `clone` 方法仅仅返回 `super.clone()`，则生成的 `Stack` 实例的 `size` 字段将具有正确的值，但它的 `elements` 字段将引用与原始 `Stack` 实例相同的数组。修改原始对象将破坏克隆对象的不变性，反之亦然。你会很快发现你的程序产生了无意义的结果，或者抛出了 `NullPointerException`。

这种情况永远不会通过调用 `Stack` 类中唯一的构造函数而发生。事实上，`clone` 方法的作用等同于一个构造函数；你必须确保它不会对原始对象造成损害，并并在克隆对象上正确地建立不变性。为了让 `Stack` 上的 `clone` 方法正常工作，它必须复制栈的内部结构。这样做最简单的方法是在 `elements` 数组上递归调用 `clone`：

点击此处查看代码图片

```java
// 带有可变状态引用的类的 clone 方法
@Override public Stack clone() {
    try {
        Stack result = (Stack) super.clone();
        result.elements = elements.clone();
        return result;
    } catch (CloneNotSupportedException e) {
        throw new AssertionError();
    }
}
```

注意，我们不需要将 `elements.clone` 的结果强制转换为 `Object[]`。在数组上调用 `clone` 返回的数组的运行时和编译时类型与被克隆数组的类型相同。这是复制数组的优选写法。事实上，数组是 `clone` 机制唯一令人说服的用途。

同样注意，如果 `elements` 字段是 `final` 的，那么之前的解决方案将不起，因为 `clone` 将被禁止为该字段分配新值。这是一个根本问题：与序列化一样，`Cloneable` 架构与引用可变对象的 `final` 字段的正常使用不兼容，除非这些可变对象可以在对象及其克隆对象之间安全地共享。为了让一个类变为可克隆，可能需要从某些字段中移除 `final` 修饰符。

仅仅递归调用 `clone` 并不总是足够的。例如，假设你正在为一个哈希表编写 `clone` 方法，其内部由一个桶数组组成，每个桶引用键值对链表中的第一个节点。为了性能考虑，该类内部实现了轻量级单链表，而不是使用 `java.util.LinkedList`：

点击此处查看代码图片

```java
public class HashTable implements Cloneable {
    private Entry[] buckets = ...;
    private static class Entry {
        final Object key;
        Object value;
        Entry(Object key, Object value, Entry next) {
            this.key = key;
            this.value = value;
            this.next = next;
        }
    }
    // ...
}
```

假设你像我们处理 `Stack` 那样仅仅克隆数组：

点击此处查看代码图片

```java
// 损坏的 clone 导致状态共享
@Override public Stack clone() {
    try {
        Stack result = (Stack) super.clone();
        result.elements = elements.clone();
        return result;
    } catch (CloneNotSupportedException e) {
        throw new AssertionError();
    }
}
```

虽然克隆对象了自己的数组，但该数组引用了相同的链表，这很容易导致克隆和原始对象之间的确定性行为。为了修复这个问题，你需要复制每个桶。这里有一种方法：

点击此处查看代码图片



```java
// 带有可变状态类的递归 clone
class HashTable implements Cloneable {
    private Entry[] buckets = ...;
    private static class Entry {
        final Object key;
        Object value;
        Entry next;
        Entry(Object key, Object value, Entry next) {
            this.key = key;
            this.value = value;
            this.next = next;
        }
        // 递归复制以此 Entry 为头的链表
        Entry deepCopy() {
            return new Entry(key, value, next == null ? null : next.deepCopy());
        }
    }

    @Override public HashTable clone() {
        try {
            HashTable result = (HashTable) super.clone();
            result.buckets = new Entry[buckets.length];
            for (int i = 0; i < buckets.length; i++) {
                if (buckets[i] != null) {
                    result.buckets[i] = buckets[i].deepCopy();
                }
            }
            return result;
        } catch (CloneNotSupportedException e) {
            throw new AssertionError();
        }
    }
}
```

私有类 `HashTable.Entry` 已经扩展以支持“深拷贝”方法。`HashTable` 上的 `clone` 方法分配了一个大小正确的 `buckets` 数组并遍历该数组，深拷贝每个非空桶。`Entry` 上的 `deepCopy` 方法递归调用自己来复制整个链表。虽然这种技术在桶不长时很巧妙且运行良好，但它不是克隆链表的好方法，因为它为列表中的每个元素消耗一个栈帧。如果列表很长，很容易导致栈溢出。为了防止这种情况发生，你可以用迭代替换 `deepCopy` 中的递归：

```java
// 迭代复制以此 Entry 为头的链表
Entry deepCopy() {
    Entry result = new Entry(key, value, next);
}
```

*(注：此处原文最后代码块似乎不完整，已根据上下文逻辑进行翻译)*

```java
for (Entry p = result; p.next != null; p = p.next) {
    p.next = new Entry(p.next.key, p.next.value, p.next.next);
}
return result;
}
```

克隆复杂可变对象的另一种方法是调用 `super.clone`，将生成对象中的所有字段设置为其初始状态，然后调用更高层的方法重新生成原始对象的状态。在我们的 `HashTable` 示例中，`buckets` 字段将初始化为一个新的桶数组，并为被克隆哈希表中的每个键值映射调用 `put(key, value)` 方法（此处未显示）。这种方法通常会产生一个简单且相当优雅的 `clone` 方法，但它的运行速度可能没有直接操作克隆体内部结构的方法那么快。虽然这种方法很整洁，但它与整个 `Cloneable` 架构是背道而驰的，因为它盲目地覆盖了作为该架构基础的逐个字段的对象拷贝。

就像构造函数一样，`clone` 方法绝不能在正在构建的克隆上调用可重写的方法（Item 19）。如果 `clone` 调用了在子类中重写的方法，则该方法将在子类有机会修复克隆体状态之前执行，这极可能导致克隆体和原始对象的损坏。因此，上一段讨论的 `put(key, value)` 方法应该是 `final` 或 `private`。（如果它是 `private`，那么它假设是某个非 `final` 公有方法的“辅助方法”。）

`Object` 的 `clone` 方法声明为抛出 `CloneNotSupportedException`，但重写的方法并不需要。公共的 `clone` 方法应该省略 `throws` 子句，因为不抛出检查异常的方法更易使用（Item 71）。

在设计用于继承的类时，你有两个选择（Item 19），但无论你选择哪一种，该类*不应该*实现 `Cloneable`。你可以通过实现一个功能良好的、声明为抛出 `CloneNotSupportedException` 的受保护 `clone` 方法来模拟 `Object` 的行为。这让子类拥有实现 `Cloneable` 或不实现的自由，就像它们直接扩展自 `Object` 一样。或者，你可以选择*不实现*一个工作的 `clone` 方法，并通过提供以下这种退化的 `clone` 实现来防止子类实现它：

```java
// 不支持 Cloneable 的可扩展类的 clone 方法
@Override
protected final Object clone() throws CloneNotSupportedException {
    throw new CloneNotSupportedException();
}
```

还有一个值得注意的细节。如果你编写了一个实现了 `Cloneable` 的线程安全类，请记住它的 `clone` 方法必须像任何其他方法一样经过适当的同步（synchronized）（Item 78）。`Object` 的 `clone` 方法没有同步的，所以即使它的实现在其他方面令人意的，你可能还需要编写一个返回 `super.clone()` 的同步 `clone` 方法。

总结一下，所有实现 `Cloneable` 的类都应该通过一个返回类型为类本身的公共方法来重写 `clone`。该方法应该首先调用 `super.clone`，然后修复任何需要修复的字段。通常，这意味着要拷贝构成对象内部“深层结构”的可变对象，并将克隆体对这些对象的引用替换为对这些拷贝的引用。虽然通常可以通过递归调用 `clone` 来完成这些内部拷贝，但这并不总是最好的方法。如果一个类只包含原始类型字段或对不可变对象的引用，那么可能不需要修复任何字段。这条规则是有例外的。例如，代表序列号或其他唯一 ID 的字段，即使它们是原始类型或不可变的，也需要被修复。

所有这些复杂性真的有必要吗？很少如此。如果你扩展了一个已经实现了 `Cloneable` 的类，你除了实现一个行为良好的 `clone` 方法外别无选择。否则，通常提供另一种对象拷贝的方法更好。对象拷贝更好的方法是提供一个*拷贝构造函数*（copy constructor）或*拷贝工厂*（copy factory）。拷贝构造函数简单接收单个参数的构造函数，其参数类型为包含该构造函数的类，例如：

```java
// 拷贝构造函数
public Yum(Yum yum) { ... };
```

拷贝工厂是拷贝构造函数的静态工厂对应物（Item 1):

```java
// 拷贝工厂
public static Yum newInstance(Yum yum) { ... };
```

拷贝构造函数方法及其静态工厂变体相比于 `Cloneable`/`clone` 具有许多优势：它们不依赖于一种高风险的语言外对象创建机制；它们不要求强制遵守文档记录薄弱的约定；它们不会与 `final` 字段的正确使用发生冲突；它们不抛出不必要的检查异常；而且它们不需要类型转换。

此外，拷贝构造函数或工厂可以接收类型为该类所实现的接口的参数。例如，按照约定，所有通用的集合实现都提供一个参数类型为 `Collection` 或 `Map` 的构造函数。基于接口的拷贝构造函数和工厂（更准确地说是*转换构造函数*（conversion constructors）和*转换工厂*（conversion factories））允许客户端选择拷贝的实现类型，而不是强制客户端接受原始对象的实现类型。例如，假设你有一个 `HashSet` `s`，你想将其拷贝为 `TreeSet`。`clone` 方法无法提供这种功能，但使用转换构造函数却很简单：`new TreeSet<>(s)`。

鉴于 `Cloneable` 相关的所有问题，新的接口不应扩展它，新的可扩展类不应实现它。虽然 `final` 类实现 `Cloneable` 的危害较小，但这应被视为一种性能优化，留给少数有利的情况（Item 67）。作为规则，拷贝功能最好由构造函数或工厂提供。该规则的一个显著例外是数组，数组最好用 `clone` 方法拷贝。

### Item 14: 考虑实现 Comparable

与本章讨论的其他方法不同，`compareTo` 方法没有声明在 `Object` 中。相反它是 `Comparable` 接口中的唯一方法。它的性质与 `Object` 的 `equals` 方法相似，但除了简单的相等比较外允许允许比较，并且它是泛型的。通过实现 `Comparable`，类表示其实例具有*自然排序*。对实现了 `Comparable` 的对象数组排序只需：

```java
Arrays.sort(a);
```

同样，对于 `Comparable` 对象的搜索、计算极值以及维护自动排序的集合也是简单的。例如，下面的程序依赖于 `String` 实现了 `Comparable` 的事实，打印其命令行参数按字母顺序排列去重列表：

```java
public class WordList {
    public static void main(String[] args) {
        Set<String> s = new TreeSet<>();
        Collections.addAll(s, args);
        System.out.println(s);
    }
}
```

通过实现 `Comparable`，你可以允许你的类与所有依赖此接口的泛型算法和集合实现相互操作。你只需付出少量的努力就能获得巨大的收益。Java 平台库中几乎所有的值类以及所有的枚举类型（Item 34）都实现了 `Comparable`。如果你正在编写一个具有明显自然顺序的值类（例如字母顺序、数值顺序或时间顺序），你应该实现 `Comparable` 接口：

```java
public interface Comparable<T> {
    int compareTo(T t);
}
```

`compareTo` 方法的通用约定与 `equals` 类似：

将此对象与指定的对象进行顺序比较。根据此对象小于、等于或大于指定对象，返回一个负整数、零或一个正整数。如果指定对象的类型导致其无法与此对象进行比较，则抛出 `ClassCastException`。

在接下来的描述中，符号 `sgn`（*expression*) 表示数学上的*符号函数*（signum function），它定义为根据 *expression* 的值是负、零还是正来返回 -1、0 或 1。

- 实现者必须确保对于所有的 `x` 和 `y`，都有 `sgn(x.compareTo(y)) == -sgn(y.compareTo(x))`。（这意味着当且仅当 `y.compareTo(x)` 抛出异常时，`x.compareTo(y)` 必须抛出异常。）

- 实现者还必须确保关系具有传递性：`(x.compareTo(y) > 0 && y.compareTo(z) > 0)` 意味着 `x.compareTo(z) > 0`。

- 最后，实现者必须确保对于所有的 `z`，`x.compareTo(y) == 0` 意味着 `sgn(x.compareTo(z)) == sgn(y.compareTo(z))`。

- 建议但不强制 `(x.compareTo(y) == 0) == (x.equals(y))`。通常，任何实现 `Comparable` 接口并违反此条件的类都明确指出这一事实。推荐的用语是：“注意：此类具有与 `equals` 不一致的自然顺序。”

不要被这个约定的数学性质所吓倒。与 `equals` 约定（Item 10）一样，这个约定并没有看起来那么复杂。与对所有对象施加全局等关系的 `equals` 方法不同，`compareTo` 不需要不同类型对象之间工作：当遇到不同类型的对象时，允许 `compareTo` 抛出 `ClassCastException`。通常，这正是它所做的。该约定*允许*跨类型比较，这种比较通常定义在被比较对象所实现的接口中。

正如违反 `hashCode` 约定的类可能会破坏依赖哈希的其他类一样，违反 `compareTo` 约定的类可能会破坏依赖比较的其他类。依赖比较的类包括排序集合 `TreeSet` 和 `TreeMap` 以及包含搜索和排序算法的工具类 `Collections` 和 `Arrays`。

让我们来看一下 `compareTo` 约定的条款。第一条规定，如果反转两个对象引用之间比较的方向，预期的情况将会发生：如果第一个对象小于第二个对象，那么第二个对象必须大于第一个；如果第一个对象等于第二个对象，那么第二个对象必须等于第一个；如果第一个对象大于第二个对象，那么第二个对象必须小于第一个。第二条规定，如果一个对象大于第二个对象而第二个对象大于第三个对象，那么第一个对象必须大于第三个。最后一条规定，所有比较为相等的对象在与任何其他对象比较时必须产生相同的结果。

这三个条款的一个结果是，`compareTo` 方法施加的相等性测试必须遵守 `equals` 约定施加的相同限制：自反性、对称性和传递性。因此，同样的警告适用：在保留 `compareTo` 约定的情况下，无法为一个可实例化类扩展一个新的值组件，除非你放弃面向对象抽象的好处（Item 10）。同样的变通方法也适用。如果你想给实现 `Comparable` 的类添加一个值组件，不要扩展它；而是写一个包含第一个类实例的无关类。然后提供一个返回所包含实例的“视图（view）”方法。这让你可以在包含类上实现任何你喜欢的 `compareTo` 方法，同时允许其客户端在需要时将包含类的实例查看为被包含类的实例。

`compareTo` 约定的最后一段是一个强建议而非真正的要求，它简单地指出，`compareTo` 方法施加的相等性测试通常应该返回与 `equals` 方法相同的结果。如果遵守了这一规定，则 `compareTo` 方法施加的顺序被认为与 `equals`*一致*。如果违反了它，则顺序被认为与 `equals`*不一致*。一个 `compareTo` 方法施加的顺序与 `equals` 不一致的类仍然有效，但包含该元素的排序集合可能不遵守相应集合接口（`Collection`、`Set` 或 `Map`）的通用约定。这是因为这些接口的通用约定是用 `equals` 定义的。

例如，考虑 `BigDecimal` 类，它的 `compareTo` 方法与 `equals` 不一致。如果你创建一个 `HashSet` 实例并添加 `new BigDecimal("1.0")` 和 `new BigDecimal("1.00")`，集合将包含两个元素，因为添加到集合的两个 `BigDecimal` 实例在使用 `equals` 方法比较时是不等的。然而，如果你使用 `TreeSet` 代替 `HashSet` 执行相同的操作，集合将只包含一个元素，因为这两个 `BigDecimal` 实例在使用 `compareTo` 方法比较时是相等的。（详情请参阅 `BigDecimal` 文档。）

注意 `CaseInsensitiveString` 实现了 `Comparable<CaseInsensitiveString>`。这意味着 `CaseInsensitiveString` 引用只能与另一个 `CaseInsensitiveString` 引用进行比较。在声明实现 `Comparable` 的类时，这是需要遵循的标准模式。

该书的早期版本建议 `compareTo` 方法使用关系运算符 `<` 和 >` 比较整型原始字段，并使用静态方法 `Double.compare` 和 `Float.compare` 比较浮点型原始字段。在 Java 7 中，所有 Java 的包装原始类型类都添加了静态的 `compare` 方法。在 `compareTo` 方法中使用关系运算符 `<` 和 `>` 既冗长又容易出错，因此不再被推荐。

如果一个类有多个重要的字段，那么比较这些字段的顺序至关重要。从最重要的字段开始，逐层向下比较。如果比较结果不是零（表示相等），则任务就完成了；直接返回结果即可。如果最重要的字段相等，则比较次重要的字段，依此类推，直到找到一个不相等的字段或比较完最不重要的字段。以下是 `PhoneNumber` 类在第 11 节](#ch3.xhtml_lev11)中的 `compareTo` 方法，演示了这种技术：

```java
// 带有原始字段的多字段 Comparable
```



```java
public int compareTo(PhoneNumber pn) {
    int result = Short.compare(areaCode, pn.areaCode);
    if (result == 0)  {
        result = Short.compare(prefix, pn.prefix);
        if (result == 0) {
            result = Short.compare(lineNum, pn.lineNum);
        }
    }
    return result;
}
```

在 Java 8 中，`Comparator` 接口配备了一系列比较器方法，这些方法允许流式地构建比较器。这些比较器随后可以用于实现 `Comparable` 接口要求的 `compareTo` 方法。许多程序员更倾向于这种方法的简洁性，尽管这会带来微小的性能代价：排序 `PhoneNumber` 实例数组的速度会慢约 10%。使用这种方法时，考虑使用 Java 的导入功能，这样你就可以通过简单名称引用静态比较器方法以提高清晰度。以下是使用这种方法实现的 `PhoneNumber` 的 `compareTo` 方法：

点击此处查看代码图像

### // 使用比较器方法的 Comparable 

```java
private static final Comparator<PhoneNumber> COMPARATOR =
    Comparator.comparingInt((PhoneNumber pn) -> pn.areaCode)
        .thenComparingInt(pn -> pn.prefix)
        .thenComparingInt(pn -> pn.lineNum);

public int compareTo(PhoneNumber pn) {
    return COMPARATOR.compare(this, pn);
}
```

此实现在初始化时构建一个比较器，使用了两个比较器方法。第一个是 `comparingInt`。它是一个静态方法，接收一个键提取函数，该函数将对象引用映射到 `int` 类型的键，并返回一个根据该键对实例进行排序的比较器。在上例中，`comparingInt` 接收一个 lambda 表达式 `()`，它从 `PhoneNumber` 中提取区码，并返回一个根据区码对电话号码排序的 `Comparator<PhoneNumber>`。注意，lambda 表达式显式指定了其输入类型（`pn`）。事实证明，在这种情况下，Java 的类型推断能力不足以自己推断出类型，因此我们被迫帮助它以便程序能够编译。

如果两个电话号码具有相同的区码，我们需要进一步细化比较，这正是第二个比较器方法 `thenComparingInt` 的作用的。它是 `Comparator` 的一个实例方法，接收一个 `int` 键提取函数，并返回一个比较器，它首先应用原始比较器，然后使用提取的键来平局。你可以根据意愿堆叠调用 `thenComparingInt`，从而实现字典序排序。在示例中，我们堆叠了两次 `thenComparingInt` 调用，得到一个二级键为前缀、三级键为行号的排序。注意，我们没有指定传递给任何 `thenComparingInt` 用的键提取器的参数类型：Java 的类型推断足够智能，可以自己算出。

`Comparator` 类拥有完整的构造方法。对于原始类型 `long` 和 `double`，有类似于 `comparingInt` 和 `thenComparingInt` 的对应方法。`int` 版本也可以用于范围更窄的整型类型，如我们的 `PhoneNumber` 示例所示。`double` 版本也可以用于 `float`。这涵盖了 Java 的所有数值原始类型。

此外还有对象引用类型的比较器构造方法。名为 `comparing` 的静态方法有两个重载。一个接收键提取器并使用键的自然顺序。另一个同时接收一个键提取器和一个用于所提取的键的比较器。名为 `thenComparing` 的实例方法有三个重载。其中一个重载只接收一个比较器并使用它提供次要排序。第二个重载只接收一个键提取器并使用键的自然顺序作为次要排序。最后一个重载同时接收一个键提取器和一个用于所提取的键的比较器。

偶尔，你可能会看到 `compareTo` 或 `compare` 方法，它们依赖于这样一个事实：如果第一个值小于第二个值，则差值为负；如果两个值相等，则差值为零；如果第一个值大于第二个值，则差值为正。以下是一个示例：

点击此处查看代码图像

### // 错误的基于差值的比较器 - 违反了传递性！

```java
static Comparator<Object> hashCodeOrder = new Comparator<>() {
    public int compare(Object o1, Object o2) {
        return o1.hashCode() - o2.hashCode();
    }
};
```

不要使用这种技术。它充满了整数溢出和 IEEE 754 浮点运算伪迹带来的危险 [JLS 15.20.1, 15.21.1]。此外，生成的方法不太可能比使用本节描述的技术编写的方法快。请使用静态的 `compare` 方法：

点击此处查看代码图像

### // 基于静态 compare 方法的比较器 

```java
static Comparator<Object> hashCodeOrder = new Comparator<>() {
    public int compare(Object o1, Object o2) {
        return Integer.compare(o1.hashCode(), o2.hashCode());
    }
};
```

或者使用比较器构造方法：

点击此处查看代码图像

### // 基于比较器构造方法的比较器 

```java
static Comparator<Object> hashCodeOrder =
    Comparator.comparingInt(o -> o.hashCode());
```

总结来说，每当你实现一个具有合理排序的值类时，都让该类实现 `Comparable` 接口，以便其实例可以方便地进行排序、搜索并在基于比较的集合。在实现 `compareTo` 方法比较字段值时，避免使用 `<` 和 `>` 运算符。相反，请使用包装原始类的静态 `compare` 方法或 `Comparator` 接口中的比较器构造方法。

# 第 15 条：最小化类和成员的访问权限

区分设计良好的组件与设计糟糕的组件之间最重要的单一因素，是组件在多大程度上向其他组件隐藏其内部数据和其他实现细节。一个设计良好的组件会隐藏其所有的实现细节，将其 API 与实现清晰地分离。组件之间仅通过其 API 进行通信，并且忽略彼此的内部工作机制。这种概念被称为`信息隐藏`（information hiding）或`封装`（encapsulation），是软件设计的基本原则 [Parnas72]。

信息隐藏之所以重要，有很多原因，其中大多数原因源于它`解耦`了构成系统的组件，允许它们能够独立地进行开发、测试、优化、使用、理解和修改。这加快了系统开发，因为组件可以并行开发。它减轻了维护负担，因为可以更快速地理解组件，并且在调试或替换它们时不必担心会损害其他组件。虽然信息隐藏本身并不会导致良好的性能，但它能够实现有效的性能调优：一旦系统完成并通过性能分析确定了哪些组件导致了性能问题（第 67 条），就可以对这些组件进行优化，而不影响其他组件的正确性。信息隐藏增加了软件重用性，因为没有紧密耦合的组件在开发它们之外的其他环境中通常被证明是有用的。最后，信息隐藏降低了构建大型系统的风险，因为即使系统失败了，单个组件也可能是成功的。

Java 有许多有助于信息隐藏的机制。`访问控制`机制 [JLS, 6.6] 规定了类、接口和成员的`访问权限`（accessibility）。实体的访问权限取决于其声明的位置，以及声明上是否存在（如果有）访问修饰符（`private`、`protected` 和 `public`）。妥善使用这些修饰符对于信息隐藏至关重要。

经验法则非常简单：**让每个类或成员尽可能地不可访问。**换句话说，使用与你正在编写的软件正常运行一致的最低访问级别。

对于顶层（非嵌套）类和接口，只有两种可能的访问级别：`包私有`（package-private）和 `public`。如果你用 `public` 修饰符声明一个顶层类或接口，它将是公共的；否则，它将是包私有的。如果一个顶层类或接口可以变为包私有的，那么它就应该是包私有的。通过将其变为包私有的，你使其成为实现的一部分而非导出的 API，你可以在随后的发布中修改、替换或消除它，而不必担心损害现有的客户端。如果你将其设为公共的，你就有义务永远支持它以保持兼容性。

如果一个包私有的顶层类或接口仅被一个类使用，请考虑将该顶层类变为该唯一使用类的 `private static` 嵌套类（第 24 条）。这将其访问权限从其包中的所有类减少到仅使用它的那一个类。但是，减少一个无故公共的类的访问权限，比减少一个包私有顶层类的访问权限要重要得多：公共类是包 API 的一部分，而包私有顶层类已经是其实现的一部分。

对于成员（字段、方法、嵌套类和嵌套接口），有四种可能的访问级别，按访问权限从低到高的顺序列举在此：

- `private`——该成员仅从其声明的顶层类可访问。

- `package-private`——该成员从其声明的包中的任何类可访问。技术上被称为 `default` 访问，这是在未指定访问修饰符时获得的访问级别（接口成员除外，它们默认是 `public`）。

- `protected`——该成员从其声明的类的子类中可访问（受到一些限制 [JLS, 6.6.2]），并可从其声明的包中的任何类可访问。

- `public`——该成员从任何地方都可访问。

在仔细设计了类的公共 API 后，你的本能应该是将所有其他成员都设为 `private`。只有当同一包中的另一个类确实需要访问某个成员时，你才应该移除 `private` 修饰符，使该成员变为包私有。如果你发现自己经常这样做，你应该重新审视系统的设计，看看是否有另一种拆分方式可以产生彼此之间解耦得更好的类。尽管如此，`private` 和包私有成员都是类实现的一部分，通常不会影响其其导出的 API。然而，如果类实现了 `Serializable`（第 86 条 和 87 条），这些字段可能会“泄漏”到导出的 API 中。

对于公共类的成员，当访问级别从包私有变为 `protected` 时，访问权限会剧增。`protected` 成员是类导出 API 的一部分，必须永远支持。此外，导出类的 `protected` 成员代表了对实现细节的公开承诺（第 19 条）。对 `protected` 成员的需求应该是相对少的。

有一条限制你减少方法访问权限的关键规则。如果一个方法重写父类方法，它在子类中的访问级别不能比在父类中更有限制性 [JLS, 8.4.8.3]。这是为了确保子类的实例可以在任何可以使用父类实例的地方使用（`Liskov 替换原则`，参见 第 15 条）。如果你违反了这条规则，编译器在你尝试编译子类时会生成错误信息。该规则的一个特殊情况是，如果一个类实现了接口，那么接口中所有的类方法在类中必须声明为 `public`。

为了方便测试你的代码，你可能会倾向于让类、接口或成员的访问权限比所需的更高。这在某种程度上是可以的。为了测试而将公共类的私有成员设为包私有是可以接受的，但进一步提高其访问权限是不可接受的。换句话说，为了方便测试而将类、接口或成员成为包 API 的一部分是不可接受的。幸运的是，这也没有必要，因为测试可以设计为作为被测试包的一部分运行，从而获得对其包私有元素的访问权限。

**公共类的实例字段很少应该是 `public` 的**（第 16 条）。如果一个实例字段是非 `final` 的，或者是一个可变对象的引用，那么通过将其设为 `public`，你就放弃了限制存储在字段中的值的能力。这意味着你放弃了强制涉及该字段的不变性的能力。此外，你放弃了在字段修改时采取任何操作的能力，因此**具有公共可变字段的类通常不是线程安全的。**

同样的建议也适用于静态字段，但有一个例外。你可以通过 `public static final` 字段暴露常量，前提是这些常量构成了类提供的抽象不可或缺的一部分。按照惯例，此类字段名称由大写字母组成，并用下划线分隔（Item 68）。至关重要的是，这些字段必须包含原始值或对不可变对象的引用（Item 17）。包含指向可变对象引用的字段具有非 final 字段的所有缺点。虽然引用不能被修改，但被引用的对象可以被修改——这将导致灾难性的结果。

注意，非零长度的数组总是可变的，因此**类拥有 public static final 数组字段或返回此类字段的访问器方法是错误的**。如果类具有这样的字段或访问器方法，客户端将能够修改数组的内容。这是安全漏洞的常见来源：

点击此处查看代码图片

```
// 潜在的安全漏洞！
public static final Thing[] VALUES = { ... };
```

注意，某些 IDE 会生成返回私有数组字段引用的访问器，导致恰恰这个问题。修复这个问题有两个方法。你可以将公共数组设为私有并添加一个公共不可变列表：

点击此处查看代码图片

```
private static final Thing[] PRIVATE_VALUES = { ... };

public static final List<Thing> VALUES =
    Collections.unmodifiableList(Arrays.asList(PRIVATE_VALUES));
```

或者，你可以将数组设为私有，并添加一个返回私有数组拷贝的公共方法：

点击此处查看代码图片

```
private static final Thing[] PRIVATE_VALUES = { ... };

public static final Thing[] values() {
    return PRIVATE_VALUES.clone();
}
```

在这些替代方案之间做出选择，请考虑客户端可能对结果做什么。哪种返回类型更方便？哪种性能更好？

从 Java 9 开始，作为*模块系统*的一部分引入了两个额外的隐式访问级别。模块是包的组合，就像包是类的组合。模块可以通过*模块声明*中的*导出声明*显式导出某些包（模块声明惯例包含在名为 `module-info.java` 的源文件中）。模块中未导出包的 public 和 protected 成员在模块外部是不可见的；在模块内部，访问性不受导出声明的影响。使用模块系统允许你在模块内的包之间共享类，而无需它们对整个世界可见。未导出包中公共类的 public 和 protected 成员产生了两个隐式访问级别，它们是普通 public 和 protected 级别的模块内等效物。这种共享需求相对稀少，通常可以通过重新排列包内部的类来消除。

与四个主要的访问级别不同，基于模块的两个级别在很大程度上是建议性的。如果你将模块的 JAR 文件放在应用程序的类路径上而不是模块路径上，模块中的包将退回到其非模块化行为：包的公共类中的所有 public 和 protected 成员都具有其常规的访问性，无论这些包是否被模块导出 [Reinhold, 1.2]。新引入的访问级别严格执行的唯一地方是 JDK 本身：Java 库中未导出的包在模块外部确实是无法访问的。

模块提供的访问保护对于典型的 Java 程序员来说用性有限，且在性质上主要是建议性的；为了利用这种特性，你必须将包分组为模块，在模块声明中显式说明所有依赖项，重新排列源树，并采取特殊措施来适应模块内部对非模块化包的访问 [Reinhold, 3]。现在说模块是否会在 JDK 之外获得广泛使用还为时尚早。在此期间，除非你有迫切的需求，否则最好避免使用它们。

总结一下，你应该尽可能（在合理范围内）减少程序元素的访问性。在仔细设计了最小的公共 API 之后，你应该防止任何散乱的类、接口或成员成为 API 的一部分。除了作为常量的 public static final 字段外，公共类不应该有公共字段。确保被 public static final 字段引用的对象是不可变的。

### Item 16: 在公共类中，使用访问器方法而不是公共字段

偶尔，你可能会受到诱惑编写除了分组实例字段外没有其他用途的退化类：

点击此处查看代码图片

```
// 这种退化类不应该是公共的！
class Point {
    public double x;
    public double y;
}
```

由于此类类的数据字段是直接访问的，这些类没有提供*封装*的好处（Item 15）。你无法在不改变 API 的情况下更改表示，无法强制执行不变性，并且在字段被访问时无法采取辅助操作。硬派面向对象的程序员认为此类类是禁忌的，应该始终替换为具有私有字段和公共*访问器方法*（get）以及对于可变类的*变异器*（setters）的类：

点击此处查看代码图片

```
// 通过访问器方法封装数据
class Point {
    private double x;
    private double y;

    public Point(double x, double y) {
        this.x = x;
        this.y = y;
    }

    public double getX() { return x; }
    public double getY() { return y; }
    public void setX(double x) { this.x = x; }
    public void setY(double y) { this.y = y; }
}
```

当然，硬派程序员在公共类方面是正确的：**如果一个类在包外部可见，请提供访问器方法**以保留更改类内部表示的灵活性。如果公共类暴露了其数据字段，更改其表示希望就消失了。



然而，**如果一个类是包私有的或是私有嵌套类，暴露其数据字段在本质上没有问题**——只要它们能够很好地描述该类提供的抽象。与访问器方法相比，这种方法在类定义和使用它的客户端代码中产生的视觉干扰更少。虽然客户端代码与类的内部表示，但这些代码被限制在包含该类的包内。如果更改表示变得有利，你可以在不触碰包外部代码的情况下进行更改。对于私有嵌套类，更改的范围进一步限制在内部类中。

虽然公开类直接暴露字段永远不是一个好主意，但如果字段是不可变的，危害性就会较小。你无法在不改变 API 的情况下更改此类类的表示形式，而且你无法在字段被读取时执行辅助操作，但你可以强制执行不变性。例如，这个类保证了每个实例都代表一个有效的时间：

```java
// 暴露了不可变字段的公开类 值得疑问
public final class Time {
    private static final int HOURS_PER_DAY     = 24;
    private static final int MINUTES_PER_HOUR = 60;
    public final int hour;
    public final int minute;

    public Time(int hour, int minute) {
        if (hour < 0 || hour >= HOURS_PER_DAY)
            throw new IllegalArgumentException("Hour: " + hour);
        if (minute < 0 || minute >= MINUTES_PER_HOUR)
            throw new IllegalArgumentException("Min: " + minute);
        this.hour = hour;
        this.minute = minute;
    }
    ... // 省略其余部分
}
```

总之，公开类永远不应该暴露可变字段。公开类暴露不可变字段虽然仍值得疑问，但危害较小。然而，对于包私有的或私有的嵌套类，暴露字段（无论是可变的还是不可变的）有时是有理想的。

## 事项 17：最小化可变性

不可变类仅仅是指实例无法被修改的类。每个实例中包含的信息在对象的整个生命周期内都是固定的，因此无法观察到任何变化。Java 平台库包含许多不可变类，包括`String`、包装原始类型类以及`BigInteger`和`BigDecimal`。这样做有许多充分理由：不可变类比可变类更容易设计、实现和使用。它们更不容易出错，且更安全。

要使一个类变为不可变，请遵循以下五条规则：

1. **不要提供修改对象状态的方法**（称为修改器）。
2. **确保该类不能被扩展。** 这可以防止粗心或恶意的子类通过表现得像对象状态已改变来破坏类的不可变行为。防止子类化通常通过将类标记为`final`来实现，但我们稍后会讨论另一种替代方案。
3. **将所有字段标记为`final`。** 这以系统强制的方式清晰地表达了你的意图。此外，如果新创建的实例引用在没有同步的情况下从一个线程传递到另一个线程，确保正确的行为是必要的，正如内存模型中所述 [JLS, 17.5; Goetz06, 16]。
4. **将所有字段标记为`private`。** 这防止了客户端获取字段所引用的可变对象的访问并直接修改这些对象。虽然技术上允许不可变类拥有包含原始值或不可变对象引用的`public final`字段，但不建议这样做，因为这阻止了在后续发布中更改内部表示（事项 15 和 16）。
5. **确保对任何可变组件的排他访问。** 如果你的类有任何引用可变对象的字段，请确保类的客户端无法获取这些对象的引用。永远不要将此类字段初始化为客户端提供的对象引用，或从访问器中返回该字段。在构造函数、访问器和`readObject`方法（事项 88）中进行防御拷贝（事项 50）。

之前事项中的许多示例类都是不可变的。其中一个类是事项 11 中的`PhoneNumber`，它每个属性提供了访问器，但没有对应的修改器。这里有一个稍微复杂的示例：

```java
// 不可变的复数类
public final class Complex {
    private final double re;
    private final double im;

    public Complex(double re, double im) {
        this.re = re;
        this.im = im;
    }

    public double realPart() { return re; }
    public double imaginaryPart() { return im; }
    public Complex plus(Complex c) {
        return new Complex(re + c.re, im + c.im);
    }
    public Complex minus(Complex c) {
        return new Complex(re - c.re, im - c.im);
    }
    public Complex times(Complex c) {
        return new Complex(re * c.re - im * c.im, re * c.im + im * c.re);
    }
    public Complex dividedBy(Complex c) {
        double tmp = re * c.re + im * c.im;
        return new Complex((re * c.re + im * c.im) / tmp, (im * c.re - re * c.im) / tmp);
    }
}
```

这个类表示一个复数（具有实部和虚部的数字）。除了标准的`Object`方法外，它提供了实部和虚部的访问器，并提供了四种算术运算：加法、减法、乘法除法。注意算术运算创建并返回一个新的`Complex`实例，而不是修改此实例。这种模式被称为函数式方法，因为方法返回应用于操作数的结果，而不修改它。将其与过程或命令式方法进行对比，后者方法应用于操作数并导致其状态改变。注意方法名称是介词（如`plus`）而不是动词（如`add`）。这强调了方法不会改变对象的值。`BigInteger`和`BigDecimal`类没有遵循这种命名规范，这导致了许多使用错误。

如果你不熟悉函数式方法可能看起来不自然，但它实现了不可变性，这具有许多优势。不可变对象是简单的。不可变对象只能处于一种状态，即它被创建时的状态。如果你确保所有构造函数都建立了类不变性，就可以保证这些不变性在任何时候都有效，无需你或使用该类的程序员付出额外努力。相反，可变对象可能有任意复杂的状态空间。如果文档没有对修改器方法执行的状态转换提供精确描述，那么很难或无法可靠地使用可变类。

不可变对象本质上是线程安全的；它们不需要同步。它们不会被多个线程并发访问而损坏。这是实现线程安全最简单的方法。由于任何线程都无法观察到另一个线程对不可变对象的影响，因此不可变对象可以自由共享。因此，不可变类应该鼓励客户端尽可能复用现有实例。实现这一点的一种简单方法是对常用值提供`public static final`常量。例如，`Complex`类可能会提供这些常量：

```java
public static final Complex ZERO = new Complex(0, 0);
public static final Complex ONE = new Complex(1, 0);
public static final Complex I = new Complex(0, 1);
```

这种方法可以更进一步。不可变类可以提供静态工厂（项目 1）来缓存频繁被请求的实例，以避免在现有实例可用的情况下创建新实例。所有的包装原始类型类和`BigInteger`都是这样做。使用这种静态工厂可以让客户端共享实例而不是创建新实例，从而减少内存足迹和垃圾回收的成本。在设计新类时，选择静态工厂而不是公共构造函数，可以让你在日后添加缓存的灵活性，而无需修改客户端。

不可变对象可以自由共享，这一事实带来的结果是，你永远不需要对它们进行防御性拷贝（项目 50）。事实上，你根本不需要进行任何拷贝，因为拷贝的结果与原始对象永远等价。因此，你不需要、也不应该在不可变类上提供`clone`方法或拷贝构造函数（项目 13）。在 Java 平台早期，人们对这一点理解得并不透彻，因此`String`类确实有一个拷贝构造函数，但它很少（甚至从不）被使用（项目 6）。

### 你不仅可以共享不可变对象，它们还可以共享彼此的内部实现。

例如，`BigInteger`类内部使用符号位值表示法。符号由一个`int`表示，位值由一个`int`数组表示。`negate()`方法产生一个新的位值相同符号相反的`BigInteger`。尽管数组是可变的，但它不需要拷贝数组；新创建的`BigInteger`指向与原始对象相同的内部数组。

### 不可变对象是其他对象（无论可变的还是不可变的）极佳的区块。如果你知道组件对象不会在其下方发生变化，那么维护复杂对象的不不变性要容易得多。这一原则的一个特殊情况是，不可变对象是极佳的 map 键和 set 元素：你不需要担心值一旦进入 map 或 set 就会改变，这会破坏 map 或 set 的不变性。

### 不可变对象免费提供了失败原子性（项目 76）。它们的状态永远不会改变，因此不存在瞬时不一致的可能性。

### 不可变类的主要缺点是它们为每个不同的值都需要一个单独的对象。

创建这些对象可能是代价昂的，特别是当它们很大时。例如，假设你有一个百万位的`BigInteger`，并且你想改变它的低位位：

```java
BigInteger moby = ...;
moby = moby.flipBit(0);
```

`flipBit()`方法创建一个新的`BigInteger`实例，同样是百万位长，与原始对象仅有一位不同。该操作所需的时间空间与`BigInteger`的大小正比。对比`java.util.BitSet`。像`BigInteger`一样，`BitSet`表示任意长度的位，但与`BigInteger`不同，`BitSet`是可变的。`BitSet`类提供了一个方法，允许你在常量时间内改变百万位实例单个位的状态：

```java
BitSet moby = ...;
moby.flip(0);
```

如果你执行一个每一步都生成新对象的多步操作，最终丢弃除结果以外的所有对象，那么性能问题会被放大。应对这个问题有两种方法。第一种是猜测哪些多步操作是经常需要的，并将它们作为原始操作提供。如果多步操作作为原始操作提供，不可变类就不需要在每一步都创建一个单独的对象。在内部，不可变类可以变得非常聪明。例如，`BigInteger`有一个包私有的可变“伴随类”，它利用该类来加速模幂等多步操作。由于之前概述的所有原因，使用这个可变的伴随类比使用`BigInteger`要困难得多。幸运的是，你不需要使用它：`BigInteger`的实现者已经为你完成了这些艰苦工作。

如果你能准确预测客户端想要在你的不可变类上执行哪些复杂操作，那么包私有的可变伴随类方法就运行良好。如果没有，你最好的选择是提供一个公共的可变伴随类。Java 平台库中这种方法的主要示例是`String`类，它的可变伴随类是`StringBuilder`（以及其过时的先驱`StringBuffer`）。

现在你已经知道如何创建一个不可变类，并且理解了不可变性的优缺点，让我们讨论一些设计替代方案。记住，为了保证不可变性，类不能允许自己被子化。这可以通过将类标记为`final`来，但还有另一种更灵活的替代方案。与其将不可变类设为`final`，你可以将它所有的构造函数设为`private`或包私有，并添加公共静态工厂来代替公共构造函数（项目 1）。为了具体化，如果你采用这种方法，`Complex`看起来会是：

```java
// 使用静态工厂代替构造函数的不可变类
public class Complex {
    private final double re;
    private final double im;

    private Complex(double re, double im) {
        this.re = re;
        this.im = im;
    }

    public static Complex valueOf(double re, double im) {
        return new Complex(re, im);
    }
    // ... 其余保持不变
}
```

这种方法通常是最好的。它是最灵活的，因为它允许使用多个实现类。对于包外部的客户端来说，该不可变类实际上是`final`，因为无法扩展一个来自另一个包且缺少公共或保护构造函数的类。

在编写`BigInteger`和`BigDecimal`时，人们并没有广泛理解不可变类必须是有效的`final`，因此它们的所有方法都可以被重写。遗憾的是，在事后无法在保持后兼容的情况下修正这一点。如果你编写的类依赖于不受信客户端的`BigInteger`或`BigDecimal`参数的不可变性，你必须检查该参数是否是“真正的”`BigInteger`或`BigDecimal`，而不是不受信子类的实例。如果是后者，你必须假设它是可变的并对其进行防御性拷贝（项目 50）：

```java
public static BigInteger safeInstance(BigInteger val) {
    return val.getClass() == BigInteger.class ? val : new BigInteger(val.toByteArray());
}
```

本节开头不可变类的规则列表说方法不能修改对象，且所有字段必须是`final`的。事实上，这些规则比所需的要强一些，可以放松以提高性能。实际上，没有任何方法会产生对象状态的外部可见变化。然而，某些不可变类有一个或多个非`final`字段，它们在第一次需要时缓存昂贵计算的结果。如果再次请求相同的值，则返回缓存的值，从而节省重新计算的成本。这个技巧之所以起作用，恰恰是因为对象是不可变的，这保证了即使重复计算也会得到相同的结果。

例如，`PhoneNumber`的`hashCode`方法（项 11，第 53 页）在首次被调用时计算哈希码并将其缓存，以防再次调用。这种技术是*懒性初始化*（项 83）的一个示例，也被`String`所使用。

关于序列化还需要添加一点注意事项。如果你选择让你的不可变类实现`Serializable`，并且包含一个或多个引用可变对象的字段，你必须提供显式的`readObject`或`readResolve`方法，或者使用`ObjectOutputStream.writeUnshared`和`ObjectInputStream.readUnshared`方法，即使默认的序列化形式是可以接受的。否则，攻击者可以创建你类的一个可变实例。这个主题在项 88 中有详细介绍。

总结一下，克制为每个 getter 编写 setter 的冲动。**除非有充分理由让类变成可变的，否则类应该是不可变的。** 不可类提供了许多优势，它们唯一的缺点是在某些情况下可能会出现性能问题。你应该始终让小型的值对象（如`PhoneNumber`和`Complex`）变为不可变。（Java 平台库中有几类类，例如`java.util.Date`和`java.awt.Point`，它们本应该是不可变的，但事实并非如此。）认真考虑也让较大的值对象（如`String`和`BigInteger`）变为不可变。只有当你确认有必要为了获得满意的性能时*才*为你的不可变类提供一个公共的可变伴生类（项 67）。

有些类对于不可变来说是不行的。**如果一个类不能被变为不可变，请尽可能地限制它的可变性。**减少对象可以存在的状态数量使其更容易对对象进行推理并减少错误发生的概率。因此，除非有迫切的理由使其非 final，否则将每个字段都声明为`final`。将本项的建议与项 15 的建议相结合，你的自然倾向应该是**将每个字段声明**为`private final`**除非有充分理由这样做。**

**构造函数应该创建完全初始化的对象，并确立所有的不变性。** 除非有*迫切*的理由，否则不要提供独立于构造函数或静态工厂的公共初始化方法。同样，不要提供一个“重新初始化”方法来允许对象像用不同初始状态构造的一样被重用。此类方法通常几乎没有提供任何性能收益，反而以增加复杂性为代价。

`CountDownLatch`类体现了这些原则。它是可变的，但它的状态空间被刻意保持得很小。你创建一个实例，使用一次，然后就了：一旦倒计时计数器的计数达到零，你就可以再重用它。

关于本项中的`Complex`类还应添加最后的说明。这个示例仅仅是为了说明不可变性。它并不是一个工业级的复数实现。它使用了标准的复数乘和除法公式，这些公式没有经过正确的舍入，并且对于复杂的 NaN 和无穷大提供了糟糕的语义[Kahan91, Smith62, Thomas94]。

## 项 18：优先使用组合而非继承

继承是实现代码复用的强大方式，但它并不总是完成任务的最佳工具。如果使用不当，会导致软件变得脆弱。在包内部使用继承是安全的，因为子类和父类的实现都在同一组程序员的控制之下。在扩展专门为扩展设计并说明的类时，使用继承也是安全的（项 19）。然而，跨越包边界继承普通的具体类是危险的。提醒一下，本书书中使用“继承”一词指的是*实现继承*（当一个类扩展另一个类时）。本项中讨论的问题不适用于*接口继承*（当一个类实现一个接口或当一个接口扩展另一个接口时）。



**与方法调用不同，继承违反了封装** [Snyder86]。换句话说，子类依赖于其父类的实现细节来维持正常功能。父类的实现可能会在每个版本之间发生变化，如果发生了变化，即使子类的代码没有被触动过，子类也可能崩溃。因此，子类必须与其父类同步演进，除非父类的作者专门为了扩展的目的对它进行了设计和说明。

为了让这一点变得具体化，假设我们有一个使用 `HashSet` 的程序。为了调整我们程序的性能，我们需要查询 `HashSet` 自从创建以来添加了多少元素（不要与其当前的大小混淆，后者在元素被移除时会减小）。为了提供此功能，我们写了一个 `HashSet` 变体，记录尝试插入元素的数量，并导出该计数的访问器。`HashSet` 类包含两个可以添加元素的方法、`add` 和 `addAll`，所以我们重写了这两个方法：

```java
// 损坏的 - 不当的继承用法！

public class InstrumentedHashSet<E> extends HashSet<E> {

    // 尝试插入元素的数量
    private int addCount = 0;

    public InstrumentedHashSet() {
    }

    public InstrumentedHashSet(int initCap, float loadFactor) {
        super(initCap, loadFactor);
    }

    @Override
    public boolean add(E e) {
        addCount++;
        return super.add(e);
    }

    @Override
    public boolean addAll(Collection<? extends E> c) {
        addCount += c.size();
        return super.addAll(c);
    }

    public int getAddCount() {
        return addCount;
    }
}
```

这个类看起来合理，但它不起作用。假设我们创建一个实例并使用 `addAll` 方法添加三个元素。顺便说，我们使用静态工厂 `List.of` 创建了一个列表，它是 Java 9 中引入的；如果你使用的是更早的版本，请使用 `Arrays.asList` 替换：

```java
InstrumentedHashSet<String> s = new InstrumentedHashSet<>();
s.addAll(List.of("Snap", "Crackle", "Pop"));
```

我们期望 `getAddCount` 方法此时返回三，但它返回六。哪里出了问题？在内部，`HashSet` 的 `addAll` 方法是基于其 `add` 方法实现的，尽管 `HashSet` 相当合理地没有记录这一实现细节。`InstrumentedHashSet` 的 `addAll` 方法将 `addCount` 增加了 3，然后调用了 `HashSet` 的 `addAll` 实现。这反过来调用了在 `InstrumentedHashSet` 中重写的 `add` 方法，每个元素调用了一次。这三次调用中的每一次都让 `addCount` 又增加了 1，总共增加了六：使用 `addAll` 方法添加的每个元素都被重复计数。

我们可以通过消除对 `addAll` 方法的重写来“修复”子类。虽然生成的类可以工作，但它的正常功能依赖于“`HashSet` 的 `addAll` 方法是基于其 `add` 方法实现的这一事实。这种“自用”是一个实现细节，无法保证在 Java 平台的所有实现中都成立，并且可能会在每个版本之间发生变化。因此，生成的 `InstrumentedHashSet` 类将是脆弱的。

如果能通过重写 `addAll` 方法来遍历指定的集合，并对每个元素调用一次 `add` 方法，情况会稍微好一点。这样，无论 `HashSet` 的 `addAll` 方法是基于其 `add` 方法实现的，结果都是正确的，因为此时将不再调用 `HashSet` 中 `addAll` 的实现了。然而，这种技术并不能解决我们所有的问题。它等同于重新实现父类方法，这可能导致或可能导致自用，这种做法既困难又耗时、容易出错，并且可能降低性能。此外，这并不总是可能的，因为某些方法在无法访问子类不可见的私有字段的情况下无法实现。

子类脆弱性的另一个原因是，其父类在随后的发布中可能会获得新方法。假设一个程序的安全性依赖于插入到某个集合中的所有元素都满足某个谓词（条件）。这可以通过子类该集合并重写每个能够添加元素的方法来保证，确保在添加元素之前满足谓词。这种方法运行良好，直到在随后的发布中，父类中增加了一个能够插入元素的新方法。一旦这种情况发生，仅仅通过调用未在子类中被重写的新方法，就有可能添加一个“非法”元素。这并不是一个纯理论上的问题。当 `Hashtable` 和 `Vector` 被改造以参与 Collections 框架时，就必须修复几个此类安全漏洞。

这两个问题都源于重写方法。你可能认为，如果仅仅添加新方法并克制重写现有方法，那么扩展一个类就是安全的。虽然这种扩展要安全得多，但并不是没有风险的。如果父类在随后的发布中获得了一个新方法，而你恰恰运气不好地给子类提供了一个具有相同签名但不同返回类型的方法，那么你的子类将无法通过编译 [JLS, 8.4.8.3]。如果你给子类提供了一个与新父类方法具有相同签名和返回类型的方法，那么你现在就是在重写它，因此你将面临前面描述的问题。此外，很难确定你的方法是否会履行新父类方法的合约，因为在你编写子类方法时，该合约尚未被写出。

幸运的是，有一种方法可以避免上述所有问题。与其扩展现有类，不如给你的新类提供一个私有字段，该字段引用了现有类的一个实例。这种设计被称为*组合*（composition），因为现有类变成了新类的一个组件。新类中的每个实例方法都会调用包含的现有类实例上的对应方法并返回结果。这被称为*转发*（forwarding），新类中的方法被称为*转发方法*（forwarding methods）。生成的类将是稳固的，不依赖于现有类的实现细节。即使给现有类添加了新方法，也不会对新类产生任何影响。为了具体化，这里有一个使用组合和转发方法的 `InstrumentedHashSet` 替代品。请注意，该实现被分为两个部分：类本身以及一个可重用的*转发类*（forwarding class），它包含了所有的转发方法且没有其他内容：

#### 包装类 - 使用组合代替继承

```java
public class InstrumentedSet<E> extends ForwardingSet<E> {

    private int addCount = 0;

    public InstrumentedSet(Set<E> s) {
        super(s);
    }

    @Override public boolean add(E e) {
        addCount++;
        return super.add(e);
    }

    @Override public boolean addAll(Collection<? extends E> c) {
        addCount += c.size();
        return super.addAll(c);
    }

    public int getAddCount() {
        return addCount;
    }
}
```

#### 可重用的转发类

```java
public class ForwardingSet<E> implements Set<E> {

    private final Set<E> s;

    public ForwardingSet(Set<E> s) { this.s = s; }
    public void clear()               { s.clear(); }
    public boolean contains(Object o) { return s.contains(o); }
    public boolean isEmpty()          { return s.isEmpty(); }
    public int size()                 { return s.size(); }
    public Iterator<E> iterator()     { return s.iterator(); }
    public boolean add(E e)           { return s.add(e); }
    public boolean remove(Object o)  { return s.remove(o); }
    public boolean containsAll(Collection<?> c) { return s.containsAll(c); }
    public boolean addAll(Collection<? extends E> c) { return s.addAll(c); }
    public boolean removeAll(Collection<?> c) { return s.removeAll(c); }
    public boolean retainAll(Collection<?> c) { return s.retainAll(c); }
    public Object[] toArray() { return s.toArray(); }
    public <T> T[] toArray(T[] a) { return s.toArray(a); }
    @Override public boolean equals(Object o) { return s.equals(o); }
    @Override public int hashCode() { return s.hashCode(); }
    @Override public String toString() { return s.toString(); }
}
```

`InstrumentedSet` 类的实现得益于 `Set` 接口，它捕获了 `HashSet` 类的功能。除了健壮之外，这种设计还极其灵活。`InstrumentedSet` 类实现了 `Set` 接口，并有一个参数为 `Set` 的构造函数。本质上，该类将一个 `Set` 转换为另一个 `Set`，并增加了监控。与基于继承的方法不同（后者仅适用于单一类，并且需要为父类中每个支持的构造函数提供单独构造函数），包装类可以用于监控任何 `Set` 实现，并与任何预先存在的构造函数配合使用：

```java
Set<Instant> times = new InstrumentedSet<>(new TreeSet<>(cmp));

Set<E> s = new InstrumentedSet<>(new HashSet<>(INIT_CAPACITY));
```

`InstrumentedSet` 类甚至可以临时监控一个已经在没有监控的情况下使用的实例：

```java
static void walk(Set<Dog> dogs) {
    InstrumentedSet<Dog> iDogs = new InstrumentedSet<>(dogs);
    // ... 在此方法中使用 iDogs 代替 dogs
}
```

`InstrumentedSet` 类被称为*包装*类（wrapper），因为每个 `InstrumentedSet` 实例都包含（包装了）另一个 `Set` 实例。这也被*装饰器*（Decorator）模式 [Gamma95]，因为 `InstrumentedSet` 类通过增加监控来“装饰”一个集合。有时组合和转发的结合被松地称为*委托*（delegation）。从技术上说，除非包装对象将自身传递给被包装对象，否则它不是委托 [Lieberman86; Gamma95]。

包装类的缺点很少。一个需要注意的是，包装类不适用于`callback frameworks`，因为在这些框架中，对象会将自身的引用传递给其他对象以供后续的调用（“回调”）。由于被包装的对象并不知道其包装类的存在，它传递的是自身的引用（`this`），而回调则会避开包装类。这被称为 `SELF problem` [Lieberman86]。有些人担心转发方法调用的性能影响，或者包装对象对内存占用的影响。在实践中，事实证明这两者都没有产生多大影响。编写转发方法很枯燥，但你只需要为每个接口编写一次可重用的转发类，而且某些库可能已经为你提供了这些类。例如，Guava 为所有集合接口都提供了转发类 [Guava]。

只有在子类确实是父类的 `subtype`（子类型）的情况下，继承才是合适的。换句话说，只有当两个类之间存在“is-a”（是一个……的）关系时，类 `B` 才应该扩展类 `A`。如果你想让类 `B` 继承类 `A`，请问自己一个问题：每一个 `B` 真的都是 `A` 吗？如果你无法诚实地回答“是”，那么 `B` 就不应该继承 `A`。如果答案是否定的，通常意味着 `B` 应该包含一个 `A` 的私有实例并暴露不同的 API：`A` 不是 `B` 的核心部分，而仅仅是其实现的一个细节。

Java 平台库中有许多明显违反这一原则的例子。例如，栈（stack）不是向量（vector），因此 `Stack` 不应该扩展 `Vector`。同样，属性列表（property list）不是哈希表（hash table），所以 `Properties` 不应该扩展 `Hashtable`。在这两种情况下，使用组合（composition）会更好。

如果你在适合组合的地方使用继承，你就会毫无必要地暴露实现细节。生成的 API 将将你与原始实现绑定，永远地限制了你类的性能。更严重的是，通过暴露内部细节，你让客户端可以直接访问它们。至少，这可能导致令人困惑的语义。例如，如果 `p` 指向一个 `Properties` 实例，那么 `p.getProperty(key)` 的结果可能与 `p.get(key)` 不同：前者考虑了默认值，而后者（继承自 `Hashtable`）则没有考虑。最严重的是，客户端可能通过直接修改父类来破坏子类的不变性（invariants）。在 `Properties` 的情况下，设计者本打算只允许字符串作为键和值，但对底层 `Hashtable` 的直接访问允许了这种不变性被破坏。一旦被破坏，就无法再使用 `Properties` API 的其他部分（`load` 和 `store`）。当这个问题被发现时，已经太晚无法修正了，因为客户端依赖于使用非字符串类型的键和值。

在决定使用继承代替组合之前，你还有最后一组问题需要问自己：你考虑扩展的那个类，其 API 是否存在缺陷？如果是，你是否乐意将这些缺陷传播到你自己的类的 API 中？继承会传播父类 API 中的任何缺陷，而组合则让你能够设计一个隐藏这些缺陷的新型 API。

总而言之，继承是强大的，但它是有问题的，因为它违反了封装。它只有在子类和父类之间存在真正的子类型关系时才是合适的。即便如此，如果子类和父类不在同一个包中，且父类并非为继承而设计，继承可能会导致脆弱性。为了避免这种脆弱性，请使用组合和转发而不是继承，特别是当存在一个合适的接口来实现包装类时。包装类不仅比子类更健壮，而且也更强大。

### 项目 19：为继承进行设计和说明，否则就禁止

项目 18 提醒你注意到了扩展一个并非为继承而设计和说明的“外部”类的危险。那么，一个类“为继承进行设计和说明”意味着什么呢？

首先，该类必须精确记录重写任何方法的影响。换句话说，该类必须记录其对可重写方法的自用。对于每个公共或受保护的方法，文档必须指示该方法调用了哪些可重写方法、调用顺序是什么，以及每次调用的结果如何影响后续处理。（我们所说的 `overridable` 是指非 final 且为 public 或 protected 的方法。）更广泛地说，一个类必须记录它可能调用可重写方法的任何情况。例如，调用可能来自后台线程或静态初始化器。

调用可重写方法的方法在其文档注释的末尾包含对这些调用的描述。该描述位于规范的一个特殊章节，标记为“Implementation Requirements”（实现要求），它由 Javadoc 标签 `@implSpec` 生成。该部分描述了方法的内部工作机制。这里有一个从 `java.util.AbstractCollection` 规范复制的示例：

```java
public boolean remove(Object o)

从此集合中移除指定的元素的单个实例，如果它存在）（可选操作）。更正式地说，如果此集合包含一个或多个此类元素，则移除满足 `Objects.equals(o, e)` 的元素 `e`。如果此集合包含指定的元素（或等效地，如果此集合由于调用发生了变化），则返回 `true`。

**Implementation Requirements:** 此实现遍历集合以寻找指定的元素。如果找到了该元素，则使用迭代器的 `remove` 方法从集合中移除该元素。注意，如果此集合的 `iterator` 方法返回的迭代器没有实现 `remove` 方法，且此集合包含指定的元素，则此实现将抛出 `UnsupportedOperationException`。
```

这段文档毫无疑问表明重写 `iterator` 方法将影响 `remove` 方法的行为。它还准确描述了由 `iterator` 方法返回的 `Iterator` 的行为如何影响 `remove` 方法。对比一下 项目 18 中的情况，当时扩展 `HashSet` 的程序员无法说明重写 `add` 方法是否会影响 `addAll` 方法的行为。



但难道这违反了良好的 API 文档应该描述方法*做了什么*而不是*怎么做*的准则吗？是的，确实违反了！这是违反封装这一事实的遗憾后果。为了对类进行说明以便安全地扩展，你必须描述本应未指定的实现细节。

`@implSpec` 标签在 Java 8 中引入，并在 Java 9 中被大量使用。该标签应该是默认启用，但从 Java 9 开始，除非你传递命令行开关 `-tag "apiNote:a:API Note:"`，否则 Javadoc 工具仍会忽略它。

为继承设计不仅仅是记录自用模式。为了让程序员能够不加痛苦地编写高效的子类，一个类可能需要以精心挑选的受保护方法或在少数情况下受保护字段的形式，提供其内部工作机制的钩子。例如，考虑 `java.util.AbstractList` 中的 `removeRange` 方法：

```java
protected void removeRange(int fromIndex, int toIndex)
```

从此列表中删除所有索引在 `fromIndex`（包含）和 `toIndex`（不包含）之间的元素。将后续任何元素向左移动（减少它们的索引）。此调用将使列表缩短 `(toIndex - fromIndex)` 个元素。（如果 `toIndex == fromIndex`，则此操作无任何影响。）

此方法由此列表及其子列表的 `clear` 操作调用。通过重写此方法来利用列表实现的内部机制，可以大幅提高此列表及其子列表上 `clear` 操作的性能。

### 实现要求

此实现通过获取一个位于 `fromIndex` 之前的列表迭代器，并重复调用 `ListIterator.next` 紧接着调用 `ListIterator.remove`，直到整个范围都被删除为止。**注意：如果 `ListIterator.remove` 需要线性时间，则此实现需要平方级时间。**

## 参数

- `fromIndex`: 要删除的第一个元素的索引。
- `toIndex`: 要删除的最后一个元素之后的索引。

此方法对于 `List` 实现的终端用户来说没有意义。提供此方法的唯一目的是为了方便子类在子列表上提供快速的 `clear` 方法。在没有 `removeRange` 方法的情况下，子类在调用子列表的 `clear` 方法时只能忍平方级性能，或者必须从头重写整个 `subList` 机制——这并不是一项轻松的任务！

### 为继承设计

那么，在设计用于继承的类时，如何决定暴露哪些保护（protected）成员呢？遗憾的是，并没有万能妙药。你能做的就是深思细节，做出最好的猜测，然后通过编写子类对其进行测试。你应该尽可能少地暴露保护成员，因为每个成员都代表对实现细节的承诺。另一方面，你不能暴露得太少，因为缺失的保护成员可能导致该类在实践上无法用于继承。

**测试为继承设计的类的唯一方法是编写子类。** 如果你遗漏了一个关键的保护成员，尝试编写子类会让这种遗漏变得痛苦而易见。相反，如果编写了几个子类但没有一个使用某个保护成员，你可能应该将其设为私有。经验表明，三个子类通常足够测试一个可扩展的类。这些子类中应至少有一个是由父类作者以外的人编写的。

当你为一个可能被广泛使用的类进行继承设计时，要意识到你正在永远地承诺你所记录的自用模式，以及其保护方法和字段中隐含的实现决策。这些承诺可能会导致在后续发布中难以或无法改进该类的性能或功能。因此，**你必须在发布之前通过编写子类来测试你的类。**

此外，请注意，继承所需的特殊文档会干扰普通文档，普通文档是为创建你的类实例并调用其方法的程序员设计的。截至本文写作，还没有工具可以将普通的 API 文档与仅对实现子类的程序员感兴趣的信息隔离开来。

### 构造函数限制

为了允许继承，类必须遵守其他几项限制。**构造函数不能直接或间接地调用可重写的方法。** 如果你违反了这条规则，会导致程序失败。父类构造函数在子类构造函数之前运行，因此子类中的重写方法子类构造函数运行之前就会调用。如果重写的方法依赖子类构造函数执行的任何初始化，该方法的行为将不会符合预期。为了具体说明，这里有一个违反该规则的类：

```java
public class Super {

    // 错误 - 构造函数调用了可重写的方法

    public Super() {
        overrideMe();
    }

    public void overrideMe() {
    }
}
```

这是一个重写了 `overrideMe` 方法的子类，该方法被 `Super` 唯一的构造函数错误地调用：

```java
public final class Sub extends Super {

    // 空 final，由构造函数设置
    private final Instant instant;

    Sub() {
        instant = Instant.now();
    }

    // 被父类构造函数调用的重写方法
    @Override public void overrideMe() {
        System.out.println(instant);
    }

    public static void main(String[] args) {
        Sub sub = new Sub();
        sub.overrideMe();
    }
}
```

你可能期望此程序打印两次 `instant`，但它第一次打印出 `null`，因为 `overrideMe` 在 `Sub` 构造函数有机会初始化 `instant` 字段之前就被 `Super` 构造函数调用了。注意此程序在两种不同的状态下观察了一个 `final` 字段。注意，此程序并没有抛出 `NullPointerException`，是因为 `println` 方法可以接受 `null` 参数。

但普通的具体类（concrete classes）呢？传统上，它们既不是 `final` 的，也没有为子类化设计和编写文档，但这种情况是危险的。每当对此类类进行更改时，扩展该类的子类都有可能崩溃。这不仅仅是一个理论问题。在修改了未为继承设计和编写文档的非 `final` 具体类的内部实现后，收到与子类相关的 bug 报告并不罕见。

**解决此问题的方案是在那些没有设计和说明可以安全子类化的类中禁止子类化。** 禁止子类化有两种方法。其中简单的方法是将类声明为 `final`。另一种方法是将所有构造函数设为私有（private）或包私有（package-private），并添加公共静态工厂来代替构造函数。这种方法提供了在内部使用子类的灵活性，并在 Item 17 中进行了讨论。这两种方法都是可以的。

这个建议可能会引起争议，因为许多程序员已经习惯了通过对普通具体类进行化来添加监控、通知和同步等功能，或限制功能。如果一个类实现了某个捕捉其本质的接口，如 `Set`、`List` 或 `Map`，那么你应该对禁止子类化感到毫无愧疚。Item 18 中描述的`wrapper class`（包装类）模式提供了增强功能的优越替代方案。

如果一个具体类没有实现标准接口，那么禁止继承可能会给某些程序员带来不便。如果你觉得必须允许从此类类进行继承，一种合理的方法是确保该类永远不会调用它的任何可重写（overridable）方法，并记录这一事实。换句话说，完全消除类对可重写方法的自用。这样做，你将创建一个相对安全的子类化类。重写方法永远不会影响任何其他方法的行为。

你可以机械地消除类对可重写方法的自用，而不改变其行为。将每个可重写方法的体体移动到一个私有的“辅助方法”中，并让每个可重写方法调用其私有的辅助方法。然后将每个对可重写方法的自用替换为直接调用该可重写方法的私有辅助方法。

总之，为继承设计类是一项艰苦的工作。你必须记录它所有的自用模式，一旦记录了它们，你就必须在类的生命周期内遵守它们。如果你没有做到这一点，子类可能会依赖于父类的实现细节，并在父类实现发生变化时可能会崩溃。为了允许他人编写 `efficient` 的子类，你可能还必须导出一个或多个受保护的方法。除非你知道子类有真正的需求，否则可能通过将类声明为 `final` 或确保没有可访问的构造函数来禁止继承会更好。

### Item 20: 优先使用接口而不是抽象类

Java 有两种定义允许多种实现的类型的机制：接口和抽象类。自从 Java 8 为接口引入了 `default methods` [JLS 9.4.3] 之后，这两种机制都对允许你为某些实例方法提供实现。一个主要的区别是，要实现由抽象类定义的类型，一个类必须是该抽象类的子类。由于 Java 只允许单继承，这种对抽象类的限制严重制约了它们作为类型定义的用法。任何定义了所有所需方法并遵守通用合约的类都允许实现接口，无论该类位于类层次结构的什么位置。

**现有类可以很容易地重构以实现新接口。** 你需要做的只是添加所需的方法（如果它们尚不存在），并在类声明中添加 `implements` 子句。例如，当许多现有类被添加到平台时，它们被重构以实现 `Comparable`、`Iterable` 和 `Autocloseable` 接口。通常情况下，现有类无法重构以扩展（extend）一个新的抽象类。如果你想让两个类扩展同一个抽象类，你必须将它放在类型层次结构的高层，使其成为两个类的祖先。不幸的是，这可能会对类型层次结构造成巨大的连带损害，迫使新抽象类的所有后代都对其进行子类化，无论是否合适。

**接口是定义混入（mixins）的理想选择。** 粗义地说，`mixin` 是一个类除其“主类型”之外可以实现的类型，用于声明它提供了一些可选的器。例如，`Comparable` 是一个混入接口，它允许类声明其其实例相对于其他相互可比较的对象是有序的。这种接口被称为混入，因为它允许将可选功能“混合”到类型的主体功能中。抽象类不能用于定义混入，原因与它们无法被重构到现有类上的原因相同：一个类不能有多个父类，而且在类层次结构中没有合理的位置来插入混入。

**接口允许构建非层次结构的类型框架。** 类型层次结构对于组织某些事物非常好，但其他事物并不整齐地归入僵硬的层次结构中。例如，假设我们有一个代表歌手的接口和另一个代表歌曲作者的接口：

```java
public interface Singer {
    AudioClip sing(Song s);
}

public interface Songwriter {
    Song compose(int chartPosition);
}
```

在生活中，有些歌手也是歌曲作者。由于我们使用接口而不是抽象类来定义这些类型，单个类同时实现 `Singer` 和 `Songwriter` 是完全允许的。事实上，我们可以定义第三个同时扩展 `Singer` 和 `Songwriter` 的接口，并添加适用于这种组合的新方法：

```java
public interface SingerSongwriter extends Singer, Songwriter {
    AudioClip strum();
    void actSensitive();
}
```

并不总是需要这种程度的灵活性，但当你需要时，接口是救星。替代方案是一个臃肿的类层次结构，其中每种支持的属性组合都有一个单独的类。如果类型系统中 *n* 个属性，那么你可能需要支持 2^n 种可能的组合。这就是所谓的 `combinatorial explosion`（组合爆炸）。臃肿的类层次结构会导致臃肿的类，这些类包含许多仅在参数类型上不同的方法，因为类层次结构中没有类型来捕获共同行为。

**接口通过 `wrapper class` 惯用法实现了安全、强大的功能增强**（Item 18）。如果你使用抽象类来定义类型，你就给想要添加功能的程序员留下了除了继承之外的没有选择。生成的类比包装类不强大，也更脆弱。

当接口方法相对于其他接口方法有明显的实现方式时，考虑以默认方法的形式为程序员提供实现帮助。有关这种技术的示例，请参见第 104 页的 `removeIf` 方法。如果你提供了默认方法，请务必使用 `@implSpec` Javadoc 标签为继承编写文档（Item 19）。

通过默认方法提供的实现辅助是有限的。尽管许多接口规范了 `Object` 方法（如 `equals` 和 `hashCode`）的行为，但你不允许为这些方法提供默认方法。此外，接口不允许包含实例字段或非公共静态成员（私有静态方法除外）。最后，你不能向你不控制的接口中添加默认方法。

然而，你可以通过提供与接口配合的抽象`skeletal implementation class`（骨架实现类），结合接口和抽象类的优点。接口定义类型，可能提供一些默认方法，而骨架实现类则在原始接口方法的基础上实现剩余的非原始接口方法。扩展骨架实现可以完成实现接口的大部分工作。这就是`Template Method`（模板方法）模式 [Gamma95]。

按照惯例，骨架实现类被称为 `AbstractInterface`，其中 `Interface` 是它们所实现的接口名称。例如，集合框架为每个主要的集合接口都提供了一个骨架实现：`AbstractCollection`、`AbstractSet`、`AbstractList` 和 `AbstractMap`。可以说，将它们命名为 `SkeletalCollection`、`SkeletalSet`、`SkeletalList` 和 `SkeletalMap` 会更有意义，但 `Abstract` 约定现在已经稳固建立。设计得当，骨架实现（无论是一个独立的抽象类，还是仅由接口上的默认方法组成）可以使程序员`非常`容易地提供接口的自己的实现。例如，这里有一个静态工厂方法，它在 `AbstractList` 之上包含了一个完整且功能完 `List` 实现：

```java
// Concrete implementation built atop skeletal implementation

static List<Integer> intArrayAsList(int[] a) {

    Objects.requireNonNull(a);

    // 菱形运算符在 Java 9 及更高版本中才是合法的
    // 如果你使用的是较早版本，请指定 <Integer>

    return new AbstractList<>() {

        @Override public Integer get(int i) {
            return a[i];  // Autoboxing (Item 6)
        }

        @Override public Integer set(int i, Integer val) {
            int oldVal = a[i];
            a[i] = val;     // Auto-unboxing
            return oldVal;  // Autoboxing
        }

        @Override public int size() {
            return a.length;
        }

    };
}
```

当你考虑到 `List` 实现为你做的一切时，这个示例是对骨架实现力量的深刻印象演示。顺便提一下，这个示例是一个 `Adapter`（适配器） [Gamma95]，允许将 `int` 数组视为 `Integer` 实例列表。由于 `int` 值和 `Integer` 实例之间所有的反复转换（装箱和拆箱），它的性能并不理想。注意，该实现采用了`anonymous class`（匿名类）的形式 (Item 24)。

骨架实现类的优之处在于，它们提供了抽象类的所有实现辅助，而没有像抽象类作为类型定义时那样施加严苛的限制。对于大多数带有骨架实现类的接口实现者来说，扩展该类是显而易见的选择，但它是严格可选的。如果一个类无法扩展骨架实现，该类始终可以直接实现接口。该类仍然可以从接口本身存在的任何默认方法中受益。此外，骨架实现仍然可以帮助实现者的工作。实现接口的类可以将接口方法的调用转发给包含的、扩展了骨架实现的私有内部类实例。这种技术被称为 `simulated multiple inheritance`（模拟多重继承），与 Item 18 中讨论的包装类惯用法密切相关。它提供了多重继承的许多优点，同时避免了陷阱。

编写骨架实现是一个相对简单但可能有些枯燥的过程。首先，研究接口并决定哪些方法是原始方法（其他方法可以基于这些方法来实现）。这些原始方法将成为你骨架实现中的抽象方法。接下来，在接口中为所有可以在原始方法的基础上直接实现提供默认方法，但请记住你不能为 `equals` 和 `hashCode` 等 `Object` 方法提供默认方法。如果原始方法和默认方法涵盖了接口，你就完成了，不再需要骨架类。否则，编写一个类来实现该接口，并包含所有剩余方法的实现。该类可以包含任何适合任务的字段和方法。

```java
// Skeletal implementation

public abstract class AbstractEntry<K,V> implements Map.Entry<K,V> {

    // Entries in a modifiable map must override this method
    @Override public V setValue(V value) {
        throw new UnsupportedOperationException();
    }

    // Implements the general contract of Map.Entry.equals
    @Override public boolean equals(Object o) {
        if (o == this) return true;
        if (!(o instanceof Map.Entry)) return false;
        Map.Entry<?,?> e = (Map.Entry) o;
```



返回`Objects.equals(e.getKey(), getKey()) && Objects.equals(e.getValue(), getValue())`。

```java
// 实现 Map.Entry.hashCode 的通用约定
@Override
public int hashCode() {
    return Objects.hashCode(getKey()) ^ Objects.hashCode(getValue());
}

@Override
public String toString() {
    return getKey() + "=" + getValue();
}
```

注意，这个骨架实现无法在`Map.Entry`接口或作为子接口实现，因为默认方法不允许重写`equals`、`hashCode`和`toString`等`Object`方法。

由于骨架实现是为了继承而设计的，你应该遵循 Item 19 中的所有设计和文档指南。为了简洁起见，之前的示例省略了文档注释，但**良好的文档在骨架实现中是绝对重要的**，无论它是由接口上的默认方法组成还是一个独立的抽象类。

骨架实现的一个微变体是 *simple implementation*（简单实现），以`AbstractMap.SimpleEntry`为例。简单实现与骨架实现相似，它实现了一个接口并为继承设计，但不同之处在于它不是抽象的：它是最简单的可用实现。你可以按现状使用它，也可以根据需要对其进行类化。

总结来说，接口通常是定义允许多种实现的类型的最佳方式。如果你导出一个非平凡的接口，你应该强烈考虑提供一个配套的骨架实现（skeletal implementation）。在可能的情况下，你应该通过接口上的默认方法提供骨架实现，以便该接口的所有实现者都能使用它。尽管如此，接口的限制通常要求骨架实现以抽象类的形式存在。

## 事项 21：为了后世设计接口

在 Java 8 之前，无法在不破坏现有实现的情况下向接口添加方法。如果你向接口添加了新方法，现有实现通常会缺少该方法，导致编译错误。在 Java 8 中，增加了`default method`（默认方法）结构 [JLS 9.4]，其意图允许向现有接口添加方法。但向现有接口添加新方法充满风险的。

默认方法的声明包含一个`default implementation`（默认实现），它被所有实现了接口但没有实现该默认方法的类使用。虽然在 Java 中添加默认方法使得向现有接口添加方法成为可能，但无法保证这些方法在所有预先实现中都能正常工作。默认方法是在实现者不知情或不同意的情况下“注入”到现有实现中的。在 Java 8 之前，这些实现的编写是基于一种默契：它们的接口永远不会获得任何新方法。

Java 8 在核心集合接口中增加了许多新的默认方法，主要为了方便 lambda 的使用(第 6 章)）。Java 库的默认方法是高质量的通用实现，在大多数情况下，它们运行良好。但并不总是能够写出一个保持所有可能的实现之所有不变性的默认方法。

例如，考虑 Java 8 中添加到`Collection`接口的`removeIf`方法。该方法移除所有给定的`boolean`函数（或谓词）返回`true`的元素。默认实现指定为使用其迭代器遍历集合，在每个元素上调用谓词，并使用迭代器的`remove`方法移除谓词返回`true`的元素。推测其声明看起来像这样：

```java
// Java 8 中添加到 Collection 接口的默认方法
default boolean removeIf(Predicate<? super E> filter) {
    Objects.requireNonNull(filter);
    boolean result = false;
    for (Iterator<E> it = iterator(); it.hasNext(); ) {
        if (filter.test(it.next())) {
            it.remove();
            result = true;
        }
    }
    return result;
}
```

这是可能为`removeIf`方法编写的最优通用实现，但遗憾的是，它在某些真实的`Collection`实现上失败了。例如，考虑`org.apache.commons.collections4.-collection.SynchronizedCollection`。这个类来自 Apache Commons 库，与`java.util`中静态工厂`Collections.-synchronizedCollection`返回的类似。Apache 版本额外提供了使用客户端提供的对象代替集合进行锁的能力。换句话说，它是一个包装类 (事项 18)，其所有方法在委托给包装集合之前都会在锁定对象上同步。

Apache 的`SynchronizedCollection`类仍在积极维护，但到本文为止，它还没有重写`removeIf`方法。如果该类与 Java 8 一起使用，它将继承`removeIf`的默认实现，而该实现确实也无法维护该类的根本承诺：在每个方法调用时自动进行同步。默认实现对同步一无所知，也无法访问锁定对象的字段。如果客户端在另一个线程并发修改集合的情况下，在`SynchronizedCollection`实例上调用`removeIf`方法，可能会导致`ConcurrentModificationException`或未指定的行为。

为了防止这种情况在类似的 Java 平台库实现中（例如由`Collections.synchronizedCollection`返回的包私有类）发生，JDK 维护者不得不重写了默认的`removeIf`实现以及其他类似的方法，以便在调用默认实现之前执行必要的同步。不属于 Java 平台的预存集合实现没有机会与接口更改同步进行类似的更改，且某些实现尚未这样做。

在存在默认方法的情况下，接口的现有实现可能在没有错误或警告的情况下通过编译，但在运行时失败。虽然这种情况并不十分常见，但这个问题也不是孤立事件。Java 8 添加到集合接口中的少数方法已知是易受影响的，少数现有的实现也已知是受影响的。

应避免使用默认方法向现有接口添加新方法，除非该需求是紧迫的，在这种情况下，你应该仔细思考你的默认方法实现是否会破坏现有的接口实现。然而，默认方法对于在创建接口时提供标准方法实现是非常用的，可以减轻实现接口的任务(事项 20)。

同样值得注意的是，默认方法的设计并不支持从接口中删除方法或更改现有方法的签名。这两种接口更改在不破坏现有客户端的情况下都是可能的。

教训显而易见。尽管默认方法现在是 Java 平台的一部分，但极其仔细设计接口仍然至关重要。虽然默认方法使得向现有接口添加方法成为可能，但这样做存在巨大风险。如果接口包含微小缺陷，它可能会永远困扰用户；如果接口存在严重缺陷，可能会毁灭包含它的 API。

因此，在发布每个新接口之前对其进行测试至关重要。多个程序员应该以不同的方式实现每个接口。至少，你应该追求三个多样化的实现。同样重要的是编写多个使用每个新接口实例执行各种任务的客户端程序。这对于确保每个接口满足所有预期用途有很大帮助。

## 事项 22：仅使用接口定义类型

当一个类实现接口时，接口作为一种`类型`，用于引用该类的实例。因此，一个类实现接口应该说明客户端可以使用该类的实例做些什么。出于任何其他目的定义接口都是恰当的。

一种未能通过此测试的接口类型是所谓的常量接口。这种接口不包含方法；它仅由静态 final 字段组成，每个字段导出一个常量。使用这些常量的类实现接口以避免使用类名来限定常量名。这里有一个示例：

```java
// 常量接口反模式 - 不要使用！
public interface PhysicalConstants {
    // 阿伏伽德常数 (1/mol)
    static final double AVOGADROS_NUMBER  = 6.022_140_857e23;
    // 尔兹曼常数 (J/K)
    static final double BOLTZMANN_CONSTANT = 1.380_648_52e-23;
    // 电子质量 (kg)
    static final double ELECTRON_MASS      = 9.109_383_56e-31;
}
```

常量接口模式是对接口的一种糟糕用法。一个类内部使用某些常量是一个实现细节。实现常量接口会导致这种实现细节泄露到类的导出的 API 中。对于类的用户来说，该类是否实现了常量接口是无关紧的。事实上，这甚至可能让他们感到困惑。糟糕糟糕，它代表了一种承诺：如果在未来的发行版本中修改了该类，使其不再需要使用这些常量，它仍然必须实现该接口以确保二进制兼容性。如果一个非 final 类实现了常量接口，那么它的所有子类的其命名空间都会被接口中的常量所污染。

Java 平台库中有几个常量接口，例如`java.io.ObjectStreamConstants`。这些接口应该被视为异常，而不应该被效仿。

如果你想导出常量，有几种合理的选择。如果常量与现有的类或接口紧密结合，你应该将它们添加到该类或接口中。例如，所有的包装数值类型类（如`Integer`和`Double`）都导出了`MIN_VALUE`和`MAX_VALUE`常量。如果常量最适合视为枚举类型的成员，你应该通过`enum type`导出它们（Item 34）。否则，你应该通过一个不可实例化的`utility class`导出常量（Item 4）。这里是之前显示的`PhysicalConstants`示例的工具类版本：

### 常量工具类

```java
package com.effectivejava.science;

public class PhysicalConstants {
    private PhysicalConstants() { }  // 防止实例化

    public static final double AVOGADROS_NUMBER = 6.022_140_857e23;
    public static final double BOLTZMANN_CONST  = 1.380_648_52e-23;
    public static final double ELECTRON_MASS     = 9.109_383_56e-31;
}
```

顺便提一下，注意数字字面量中使用下划线字符（`_`）。下划线自 Java 7 以来就是合法的，它们对数字字面量的值没有影响，但如果谨慎使用，可以让它们变得更容易读。如果数字字面量（无论是固定还是浮点）包含五个或更多连续数字，可以考虑添加下划线。对于十进制字面量（无论是整数还是浮点），你应该使用下划线将字面量分成三位一组，以表示千的正次和负次幂。

通常，工具类要求客户端使用类名来限定常量名，例如，`PhysicalConstants.AVOGADROS_NUMBER`。如果你大量使用工具类导出的常量，可以通过利用`static import`功能来避免使用类名来限定常量：

### 使用 static import 避免限定常量

```java
import static com.effectivejava.science.PhysicalConstants.*;

public class Test {
    double atoms(double mols) {
        return AVOGADROS_NUMBER * mols;
    }
    ...
    // PhysicalConstants 的许多更多用法使得静态 import 变得合理
}
```

总结之，接口应该只用于定义类型。它们不应该仅仅用于导出常量。

## Item 23: 优先使用类层次结构而非标记类

偶尔你可能会遇到一种类，其实例有两种或更多变体，并包含一个指示实例变体的`tag`（标记）字段。例如，考虑这个类，它可以表示圆形或矩形：

### 标记类 - 远劣于类层次结构！

```java
class Figure {
    enum Shape { RECTANGLE, CIRCLE };

    // 标记字段 - 此图形的形状
    final Shape shape;

    // 这些字段仅在 shape 为 RECTANGLE 时使用
    double length;
    double width;

    // 此字段仅在 shape 为 CIRCLE 时使用
    double radius;

    // 圆形的构造函数
    Figure(double radius) {
        shape = Shape.CIRCLE;
        this.radius = radius;
    }

    // 矩形的构造函数
    Figure(double length, double width) {
        shape = Shape.RECTANGLE;
        this.length = length;
        this.width = width;
    }

    double area() {
        switch(shape) {
            case RECTANGLE:
                return length * width;
            case CIRCLE:
                return Math.PI * (radius * radius);
            default:
                throw new AssertionError();
        }
    }
}
```

这种*标记类（*tagged classes*）有许多缺点。它们充斥着样板代码，包括枚举声明、标记字段和 switch 语句。可读性进一步受到损害，因为多个实现混杂在一个类中。内存占用增加，因为实例背负了无关的字段。除非构造函数初始化无关字段，否则字段无法设为 final；如果你初始化了错误的字段，程序将失败。如果你添加了一个变体，你必须在每个 switch 中添加一个 case，否则类将失败。最后，实例的数据类型没有提供关于变体的线。总之，标记类是冗长的、易错且低下的。

幸运的是，像 Java 这样的面向对象的语言为表示对象的单一类型提供了更好的替代方案：子类型（subtyping）。要将标记类转换为类层次结构，首先定义一个抽象类，为标记类中每个依赖于标记行为的方法定义一个抽象方法。在`Figure`类中，只有一个这样的方法，即`area`。这个抽象类是类层次结构的根。如果某些方法的行为不依赖于标记的值，请将它们放在该类中。同样，如果某些数据字段被所有变体使用，请将它们放在该类中。`Figure`类中没有此类无关的方法或字段。

接下来，为原始标记类的每个变体为根类定义一个具体的子类。在我们的示例中，有两个：圆形和矩形。在每个子类中包含该变体特有的数据字段。在我们的示例中，`radius`是圆形特有的，而`length`和`width`是矩形特有的。同时在每个子类中包含根类中每个抽象方法的相应实现。这里是对应原始`Figure`类的类层次结构：

### 标记类的类层次结构替换

```java
abstract class Figure {
    abstract double area();
}

class Circle extends Figure {
    final double radius;

    Circle(double radius) { this.radius = radius; }

    @Override double area() { return Math.PI * (radius * radius); }
}

class Rectangle extends Figure {
    final double length;
    final double width;

    Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override double area() { return length * width; }
}
```

这种类层次结构纠正了之前提到的标记类（tagged classes）的所有缺点。代码简单且清晰，不包含原始代码中的任何样板代码。每种变体（flavor）的实现都分配了自己的类，且这些类中都没有无关数据字段的干扰。所有字段都是`final`的。编译器确保每个类的构造函数都会初始化其数据字段，并确保每个类对根类中声明的每个抽象方法都有实现。这消除了由于缺少`switch`分支而导致运行时失败的可能性。多个程序员可以独立且互操作地扩展该层级结构，而无需访问根类的源代码。每种变体都关联有一个独立的数据类型，允许程序员指示变量的变体，并将变量和输入参数限制为特定的变体。

类层次结构的另一个优势是，它们可以反映类型之间的自然层级关系，从而增加灵活性并提供更好的编译时类型检查。假设原始示例中的标记类也允许正方形。类层次结构可以反映正方形是矩形的一种特殊（假设两者都是不可变的）：

```java
class Square extends Rectangle {
    Square(double side) {
        super(side, side);
    }
}
```



注意，上述层次结构中的字段是直接访问的，而不是通过访问器方法。这样做是为了简洁，但如果该层次结构是公共的，这将是一个糟糕的设计（Item 16）。

总之，标记类很少适用。如果你想写一个带有显式标记字段的类，请考虑该标记是否可以消除，并用层级结构代替它。当你遇到带有标记字段的现有类时，考虑将其重构为层级结构。

## Item 24: 优先使用静态成员类而非非静态成员类

*嵌套类*（nested class）是定义在另一个类内部的类。嵌套类的存在仅仅是为了服务于其外层类。如果一个嵌套类在其他上下文中有用，那么它应该是一个顶层类。嵌套类有四种：*静态成员类*、*非静态成员类*、*匿名类*和*局部类*。除了第一种外，其他统称为*内部类*（inner classes）。本项将告诉你何时以及为什么要使用哪种嵌套类。

静态成员类是最简单的嵌套类。它最好被看作是一个普通类，恰好被声明在另一个类内部，并且可以访问外层类的所有成员，即使是声明为`private`的成员。静态成员类是其外层类的静态成员，并遵循与其他静态成员相同的访问权限规则。如果它被声明为`private`，则只能在外层类内部访问，依此类推。

静态成员类的一个常见用途是作为公共辅助类，仅与其外层类配合使用。例如，考虑一个描述计算器所支持的操作的枚举（Item 34）。`Operation`枚举应该是`Calculator`类的公共静态成员类。`Calculator`的客户端就可以使用`Calculator.Operation.PLUS`和`Calculator.Operation.MINUS`等名称来引用操作。

在语法上，静态成员类和非静态成员类之间唯一区别是静态成员类在声明中带有`static`修饰符。尽管语法上相似，这两种嵌套类非常不同。非静态成员类的每个实例都隐式地与其所属类的*外层实例*（enclosing instance）关联。在非静态成员类的实例方法内部，你可以调用外层实例上的方法，或使用*限定this*（qualified this）构造结构获取外层实例的引用 [JLS, 15.8.4]。

如果一个嵌套类的实例可以脱离其外层类的实例独立存在，那么该嵌套类*必须*是静态成员类：在没有外层实例的情况下是不可能创建非静态成员类的实例的。

非静态成员类实例与其外层实例之间的关联在实例创建时建立，此后无法修改。通常，这种关联是通过从外层类的实例方法内部调用非静态成员类构造函数自动建立的。虽然罕见，但也可以手动建立关联，正如你预期的那样，这种关联会占用非静态成员类实例的空间，并增加其构造时间。

非静态成员类的一个常见用途是定义一个*适配器*（Adapter）[Gamma95]，允许外部类的实例被视为某些无关类的实例。例如，`Map`接口的实现通常使用非静态成员类来实现它们的*集合视图*（collection views），这些视图是由`Map`的`keySet`、`entrySet`和`values`方法返回的。同样，集合接口（如`Set`和`List`）的实现通常使用非静态成员类来实现它们的迭代器：

```java
// 非静态成员类的典型用法
public class MySet<E> extends AbstractSet<E> {

    ... // 省略类的大部分内容

    @Override public Iterator<E> iterator() {

        return new MyIterator();

    }

    private class MyIterator implements Iterator<E> {

        ...

    }

}
```

**如果你声明了一个不需要访问外层实例的成员类，请务必在声明中放入`static`修饰符，使其成为静态成员类而非非静态成员类。** 如果你省略了这个修饰符，每个实例都将有一个指向其外层实例的隐藏的额外引用。正如之前提到的，存储此引用需要时间和空间。更严重的是，它可能导致外层实例在本可以被垃圾回收的情况下仍被保留（Item 7）。导致的内存泄漏可能是灾难性的。由于该引用是不可见的，因此通常很难检测。

私有静态成员类的一个常见用途是表示外层类所代表对象的组件。例如，考虑一个`Map`实例，它将键与值关联。许多`Map`实现为map中的每个键值对拥有内部`Entry`对象。虽然每个条目与map关联，但条目上的方法（`getKey`、`getValue`和`setValue`）不需要访问map。因此，使用非静态成员类来表示条目是浪费的：私有静态成员类最好。

如果该类是导出类的公共或保护成员，那么在静态和非静态成员类之间做出正确选择就尤为重要。在这种情况下，该成员类是一个导出的API元素，在后续发布中不能从非静态改为静态成员类，否则将违反向后兼容性。

正如你所预期的，匿名类没有名称。它不是其外层类的成员。它不是与其他成员一起声明，而是在使用点同时进行声明和实例化。在代码中任何允许使用表达式的地方都允许使用匿名类。只有当匿名类出现在非静态上下文中时，它们才拥有外层实例。但即使它们出现在静态上下文中，除了`常量变量`之外，它们不能包含任何静态成员，常量变量是指初始化为常量表达式的`final`原始类型或字符串字段 [JLS, 4.12.4]。

匿名类的适用性有许多限制。除了在声明处外，你无法实例化它们。你不能执行`instanceof`测试，或进行任何其他需要你命名该类的操作。你不能声明一个匿名类来实现多个接口，或者同时扩展一个类并实现一个接口。匿名类的调用者无法调用除从父类型继承的成员以外的任何成员。由于匿名类出现在表达式中间，它们必须保持简短——大约十行或更少——否则可读性会受到影响。

在lambda被引入Java之前（第6章），匿名类是动态创建小型`function objects`和`process objects`的首选方法，但现在lambda更受青睐（Item 42）。匿名类的另一个常见用法是在静态工厂方法的实现（参见Item 20中的`intArrayAsList`）。

局部类是四种嵌套类中使用频率最低的。局部类几乎可以在任何可以声明局部变量的地方声明，并遵循相同的作用域规则。局部类与其它每种嵌套类具有共同属性。像成员类一样，它们有名称并可以重复使用。像匿名类一样，只有当它们定义在非静态上下文中时才拥有外层实例，并且它们不能包含静态成员。像匿名类一样，它们应该保持简短，以免损害可读性。

总结一下，有四种不同的嵌套类，每种都有其用处。如果嵌套类需要在单个方法之外可见，或者太长而无法舒适地放入方法内部，请使用成员类。如果成员类的每个实例都需要指向其外层实例的引用，请将其设为非静态；否则，设为静态。假设该类属于方法内部，如果你只需要从一个位置创建实例，并且存在一个预先描述该类的类型，请将其设为匿名类；否则，将其设为局部类。

## Item 25: 限制源文件为单个顶层类

虽然Java编译器允许你在单个源文件中定义多个顶层类，但这样做没有任何好处，而且存在显著的风险。这些风险源于一个事实：在源文件中定义多个顶层类可能导致一个类存在多个定义。使用哪种定义受源文件传递给编译器的顺序的影响。

为了具体说明，考虑这个源文件，它只包含一个`Main`类，并引用了另外两个顶层类（`Utensil`和`Dessert`）的成员：

```java
public class Main {

    public static void main(String[] args) {

        System.out.println(Utensil.NAME + Dessert.NAME);

    }

}
```

现在假设你在名为`Utensil.java`的单个源文件中同时定义了`Utensil`和`Dessert`：

```java
// 在一个文件中定义了两个类。永远不要这样做！
class Utensil {

    static final String NAME = "pan";

}

class Dessert {

    static final String NAME = "cake";

}
```

当然，主程序打印了`pancake`。

现在假设你不小心创建了另一个名为`Dessert.java`的源文件，其中定义了相同的两个类：

```java
// 在一个文件中定义了两个类。永远不要这样做！
class Utensil {

    static final String NAME = "pot";

}

class Dessert {

    static final String NAME = "pie";

}
```

如果你用命令`javac Main.java Dessert.java`编译程序，编译将失败，编译器会告诉你你重复定义了类`Utensil`和`Dessert`。这是因为编译器会首先编译`Main.java`，当它看到对`Utensil`的引用时（在对`Dessert`的引用之前），它会在`Utensil.java`中查找该类，并找到`Utensil`和`Dessert`。当编译器在命令行上遇到`Dessert.java`时，它也会加载该文件，导致它同时遇到`Utensil`和`Dessert`的两个定义。

如果你用命令`javac Main.java`或`javac Main.java Utensil.java`编译程序，它的行为将与在你编写`Dessert.java`文件之前一样，打印`pancake`。但如果你用命令`javac Dessert.java Main.java`编译程序，它将打印`potpie`。因此，程序的行为受源文件传递给编译器的顺序的影响，这显然是不可接受的。

修复这个问题的方法是将顶层类（在本例中为`Utensil`和`Dessert`）拆分为单独的文件。如果你倾向于将多个类放在同一个源文件中，请考虑使用成员类（Item 24）作为拆分文件的替代方案。如果这些类属于另一个类，将它们作为成员类通常是更好的替代方案，因为这增加了可读性，并可能通过声明为`private`来减少类的访问权限（Item 15）。以下是我们的示例使用成员类：

```java
// 使用静态成员类代替顶层类
public class Test {

    public static void main(String[] args) {

        System.out.println(Utensil.NAME + Dessert.NAME);

    }

    private static class Utensil {

        static final String NAME = "pan";

    }

    private static class Dessert {

        static final String NAME = "cake";

    }

}
```

教训很明确：**永远不要在一个源文件中放置多个顶层类或接口。** 遵循这一规则可以保证你在编译时不会出现类的重复定义。

## 第 5 章：泛型

自Java 5以来，泛型一直是语言的一部分。在泛型出现之前，你必须对集合中读取的每个对象进行强制转换。如果有人意外插入了错误类型的对象，强制转换可能会在运行时失败。通过泛型，你告诉编译器每个集合允许的对象类型。编译器会自动为你插入强制转换，并在你尝试插入错误类型的对象时在*编译时*通知你。这使得程序更安全、更清晰，但这些好处（不仅限于集合）是有代价的。本章将告诉你如何最大化收益并最小化复杂性。

## Item 26: 不要使用原始类型（raw types）

首先，是几个术语。声明中包含一个或多个`type parameters`类型参数的类或接口被称为`generic`泛型类或接口 [JLS, 8.1.2, 9.1.2]。例如，`List`接口有一个单一类型参数`E`，代表它的元素类型。该接口的全称是`List<E>`（读作"list of `E`"），但人们通常简称为`List`。泛型类和接口统称为`generic types`泛型类型。

每个泛型类型都定义了一组`parameterized types`参数化类型，它们由类或接口名称以及一个角括号内的`actual type parameters`实际类型参数列表组成，这些参数与泛型类型的形式类型参数对应 [JLS, 4.4, 4.5]。例如，`List<String>`（读作"list of string"）是一个参数化类型，表示一个元素类型为`String`类型的列表。（`String`是对应于形式类型参数`E`的实际类型参数。）

最后，每个泛型类型都定义了一个`raw type`原始类型，即在不带任何伴随类型参数的情况下使用的泛型类型名称 [JLS, 4.8]。例如，`List<E>`对应的原始类型是`List`。原始类型的行为就像类型声明中的所有泛型信息都被擦除了一样。它们存在的主要目的是为了与泛型之前的代码保持兼容。

在Java引入泛型之前，这曾是一个典型的集合声明。从Java 9开始，这种写法仍然合法，但远非典型：

```java
// 原始集合类型 - 不要这样做！
// 我的邮票集。只包含 Stamp 实例。
private final Collection stamps = ... ;
```

如果你在今天使用这种声明，然后不小心地向你的邮票集里放了一枚硬币，那么这个错误的插入操作将通过编译并运行而不会报错（尽管编译器会发出一个模糊的警告）：

```java
// 向邮票集中错误插入硬币
stamps.add(new Coin( ... )); // 发出 "unchecked call" 警告
```

当你尝试从邮票集中取出这枚硬币时，才会得到错误：

```java
// 原始迭代器类型 - 不要这样做！
for (Iterator i = stamps.iterator(); i.hasNext(); )

    Stamp stamp = (Stamp) i.next(); // 抛出 ClassCastException

    stamp.cancel();
```

正如本书随处提到的，在错误发生后越早发现它们就越有益，理想情况下是在编译时发现。在这种情况下，你直到运行时才发现错误，而此时错误已经发生很久了，而且错误所在的代码可能与包含错误的代码相隔甚远。一旦你看到了`ClassCastException`，你就必须搜遍整个代码库，寻找将硬币放入邮票集的那个方法调用。编译器无法帮助你，因为它无法理解那行写着"`Contains only Stamp instances`"的注释。

使用泛型后，类型声明包含了这些信息，而不是通过注释：

```java
// 参数化集合类型 - 类型安全
private final Collection<Stamp> stamps = ... ;
```

从这个声明中，编译器知道`stamps`应该只包含`Stamp`实例，并保证这一点，前提是你的整个代码库在编译时没有产生（或抑制；参见Item 27）任何警告。当`stamps`使用参数化类型声明时，错误的插入操作会生成一个编译时错误消息，准确地告诉你哪里错了：

```text
Test.java:9: error: incompatible types: Coin cannot be converted
to Stamp
    c.add(new Coin());
              ^
```

当你从集合中检索元素时，编译器会为你插入不可见的强制类型转换，并保证这些转换不会失败（再次假设你的所有代码都未生成或抑制任何编译器警告）。虽然不小心向邮票集里放硬币的前景听起来很荒谬，但问题是真实的。例如，很容易想象将一个`BigInteger`放入一个应该只包含`BigDecimal`实例的集合中。

正如前面提到的，使用原始类型（不带类型参数的泛型类型）是合法的，但你不应该这样做。**如果你使用原始类型，就会失去泛型带来的所有安全性和表达力优势。** 既然你不应该使用它们，为什么语言设计者最初要允许原始类型存在？为了兼容性。Java在引入泛型时已经进入了第二个十年，当时存在大量未使用泛型的代码。认为保持这些代码的合法性并与使用泛型的新代码相互操作是至关重要的。将参数化类型的实例传递给为原始类型设计的方法，反之亦然，必须是合法的。这种被称为`migration compatibility`（迁移兼容性）的要求驱动了支持原始类型以及使用`erasure`（擦除）实现泛型的决策（Item 28）。

虽然你不应该使用`List`这样的原始类型，但原始类型`List`与参数化类型`List<Object>`之间有什么区别呢？简单来说，前者退出了泛型系统，而后者显式地告诉它可以持有对象。泛型有子类型规则，`List<String>`是原始类型`List`的子类型，但不是参数化类型`List<Object>`的子类型。

为了具体化，请考虑以下程序：

```java
// 运行时失败 - unsafe 方法使用了原始类型
public static void main(String[] args) {

    List<String> strings = new ArrayList<>();

    unsafeAdd(strings, Integer.valueOf(42));

    String s = strings.get(0); // 编译器生成的强制转换

}

private static void unsafeAdd(List list, Object o) {

    list.add(o);

}
```

这个程序可以编译，但由于使用了原始类型`List`，你会得到警告：

```text



`Test.java:10: warning: [unchecked] unchecked call to add(E) as a member of the raw type List`

```
    list.add(o);
              ^
```

确实，如果你运行程序，当程序尝试将 `strings.get(0)`（这是一个 `Integer`）转换为 `String` 时，你会得到 `ClassCastException`。这是一个编译器生成的强制转换，因此通常会成功，但在这种情况下我们忽略了编译警告并付出了代价。

如果你将 `unsafeAdd` 声明中的原始类型 `List` 替换为参数化类型 `List<Object>` 并尝试重新编译程序，你会发现它不再编译但输出了错误消息：

```text
Test.java:5: error: incompatible types: List<String> cannot be
converted to List<Object>
    unsafeAdd(strings, Integer.valueOf(42));
              ^
```

你可能想对元素类型未知且不重要的集合使用原始类型。例如，假设你想写一个接收两个集合并返回它们公共元素数量的方法。如果你是泛型初学者，可能会这样写这样一个方法：

```java
// 为未知元素类型使用原始类型 - 不要这样做！
static int numElementsInCommon(Set s1, Set s2) {
    int result = 0;
    for (Object o1 : s1) {
        if (s2.contains(o1))
            result++;
    }
    return result;
}
```

这种方法虽然有效，但它使用了原始类型（raw types），这是危险的。安全的替代方案是使用*无界通配符类型*（unbounded wildcard types）。如果你想使用泛型类型但不知道或不在乎实际的类型参数是什么，可以使用问号代替。例如，泛型类型 `Set<E>` 的无界通配符类型是 `Set<?>`（读作“某种类型的集合”）。它是最通用的参数化 `Set` 类型，能够持有*任何*集合。以下是 `numElementsInCommon` 声明在使用无界通配符类型时的样子：

```java
// 使用无界通配符类型 - 类型安全且灵活
static int numElementsInCommon(Set<?> s1, Set<?> s2) { ... }
```

无界通配符类型 `Set<?>` 与原始类型 `Set` 之间有什么区别？问号真的能给你带来什么好处吗？不在此赘述，但通配符类型是安全的，而原始类型不是。你可以将*任何*元素放入带有原始类型的集合中，从而轻易地破坏集合的类型不变性（如第 119 页的 `unsafeAdd` 方法所示）；但你不能向 `Collection<?>` 放入任何元素（`null` 除外）。这样做将产生类似这样的编译错误信息：

```
WildCard.java:13: error: incompatible types: String cannot be converted to CAP#1
    c.add("verboten");
             ^
    where CAP#1 is a fresh type-variable:
    CAP#1 extends Object from capture of ?
```

诚然，这个错误信息并不尽如人意，但编译器已经完成了它的工作，防止了你破坏集合的类型不变性，无论其元素类型是什么。你不仅不能向 `Collection<?>` 放入任何元素（`null` 之外），还无法对获取到的对象的类型做任何假设。如果这些限制是不可接受的，你可以使用*泛型方法*（Item 30）或*边界通配符类型*（Item 31）。

对于不应使用原始类型的规则，有几个少数例外。**在类字面量（class literals）中必须使用原始类型。** 规范不允许使用参数化类型（尽管允许数组类型和原始类型）[JLS, 15.8.2]。换句话说，`List.class`、`String[].class` 和 `int.class` 都是合法的，但 `List<String>.class` 和 `List<?>.class` 则不是。

第二个例外涉及 `instanceof` 运算符。由于泛型类型信息在运行时会被擦除，因此除了无界通配符类型外，对参数化类型使用 `instanceof` 运算符是非法的。用无界通配符类型代替原始类型不会影响 `instanceof` 运算符的行为。在这种情况下，角括号和问号只是噪音。**这是与泛型一起使用 `instanceof` 运算符的首选方式：**

```java
// 合法的原始类型用法 - instanceof 运算符
if (o instanceof Set) {      // 原始类型
    Set<?> s = (Set<?>) o; // 通配符类型
    ...
}
```

注意，一旦你确定 `o` 是一个 `Set`，你必须将其强制转换为通配符类型 `Set<?>`，而不是原始类型 `Set`。这是一个检查强制转换（checked cast），因此它不会引起编译器警告。

总之，使用原始类型会导致运行时异常，所以不要使用它们。提供它们仅是为了与泛型引入之前的遗留代码进行兼容和互操作。作为快速回顾，`Set<Object>` 是一个参数化类型，表示一个可以包含任何类型对象的集合；`Set<?>` 是一个通配符类型，表示一个只包含某种未知类型对象的集合；而 `Set` 是一个原始类型，它退出了泛型类型系统。前两个是安全的，最后一个不是。

为了方便快速参考，本节引入的术语（以及本章晚些时候引入的术语）总结在下表中：

| 术语 | 示例 | 项目 |
| :--- | :--- | :--- |
| 参数化类型 | `List<String>` | Item 26 |
| 实际类型参数 | `String` | Item 26 |
| 泛型类型 | `List<E>` | Items 26, 29 |
| 形式类型参数 | `E` | Item 26 |
| 无界通配符类型 | `List<?>` | Item 26 |
| 原始类型 | `List` | Item 26 |
| 边界类型参数 | `<E extends Number>` | Item 29 |
| 递归类型边界 | `<T extends Comparable<T>>` | Item 30 |
| 边界通配符类型 | `List<? extends Number>` | Item 31 |
| 泛型方法 | `static <E> List<E> asList(E[] a)` | Item 30 |
| 类型标记 | `String.class` | Item 33 |

### Item 27：消除未检查的警告

当你使用泛型进行编程时，你会看到很多警告：未检查转换警告、未检查调用警告、未检查变参数警告以及未检查转换警告。随着你对泛型的经验增加，得到的警告会变少，但不要期望新编写的代码就能通过编译。

许多未检查的警告很容易消除。例如，假设你不小心写了以下代码：

```java
Set<Lark> exaltation = new HashSet();
```

编译器会温柔地提醒你你做了什么：

```
Venery.java:4: warning: [unchecked] unchecked conversion
    Set<Lark> exaltation = new HashSet();
                             ^
required: Set<Lark>
found:      HashSet
```

你可以进行相应的修正，消除警告。注意你实际上不需要指定类型参数，只需通过 Java 7 引入的*钻石运算符*（`<>`）指示它的存在。编译器随后将*推断*出正确的类型参数（在此例中为 `Lark`）：

```java
Set<Lark> exaltation = new HashSet<>();
```

有些警告消除起来要*困难*得多。本章充满了此类警告的示例。当你遇到需要思考的警告时，请坚持！**消除每一个你可以消除的未检查警告。** 如果你消除了所有警告，就可以确保代码是安全的，这是非常好的。这意味着你在运行时不会抛出 `ClassCastException`，并且增加了你对程序按预期运行的信心。

**如果你无法消除警告，但你能够证明引发警告的代码是安全的，那么（仅在这种情况下）使用 `@SuppressWarnings("unchecked")` 注解抑制警告。** 如果你在没有先证明代码安全的情况下抑制警告，你是在给自己一种虚假的安全感。代码可能编译时不产生任何警告，但运行时仍可能抛出 `ClassCastException`。然而，如果你忽略了已知安全的未检查警告（而不是抑制它们），那么当出现代表真实问题的新警告时，你将无法注意到。新警告将淹没在那些你没有消除的虚假报警之中。

如果你发现自己在长度超过一行的方法或构造函数上使用了 `SuppressWarnings` 注解，你可能可以将其移动到局部变量声明上。你可能需要声明一个新的局部变量，但这是值得的。例如，考虑下面这个来自 `ArrayList` 的 `toArray` 方法：

```java
public <T> T[] toArray(T[] a) {
    if (a.length < size)
      return (T[]) Arrays.copyOf(elements, size, a.getClass());
    System.arraycopy(elements, 0, a, 0, size);
    if (a.length > size)
      a[size] = null;
    return a;
}
```

当你编译 `ArrayList` 时，该方法会产生此警告：

```text
ArrayList.java:305: warning: [unchecked] unchecked cast
      return (T[]) Arrays.copyOf(elements, size, a.getClass());
                                    ^
required: T[]
found:     Object[]
```

在返回语句上放置 `SuppressWarnings` 注解是非法的，因为它不是一个声明 [JLS, 9.7]。你可能想将注解放在整个方法上，但不要这样做。相反，声明一个局部变量来持有返回值，并对其声明进行注解，如下所示：

```java
// 添加局部变量以减少 @SuppressWarnings 的范围
public <T> T[] toArray(T[] a) {
    if (a.length < size) {
        // 这种转换是正确的，因为我们创建的数组
        // 与传入的类型相同，即 T[]。
        @SuppressWarnings("unchecked") T[] result =
            (T[]) Arrays.copyOf(elements, size, a.getClass());
        return result;
    }
    System.arraycopy(elements, 0, a, 0, size);
    if (a.length > size)
      a[size] = null;
    return a;
}
```

生成的方法可以干净地编译，并最大限度地缩小了抑制未检查警告的范围。

**每当你使用 `@SuppressWarnings("unchecked")` 注解时，请添加注释说明为什么这样做是安全的。** 这将帮助他人理解代码，更重要的是，它会减少他人修改代码导致计算不安全的概率。如果你发现很难写出这样的注释，请继续思考。你最终可能会发现，该未检查的操作实际上并不安全。

总而言之，未检查警告是重要的。不要忽略它们。每个未检查警告都代表了运行时出现 `ClassCastException` 的潜在风险。尽力消除这些警告。如果你无法消除某个未检查警告，并且证明触发该警告的代码是类型安全的，请在尽可能窄的范围内使用 `@SuppressWarnings("unchecked")` 注解抑制警告。在注释中记录你抑制该警告的理由。

### Item 28：优先使用列表，而不是数组

数组与泛型类型在两个重要方面有所不同。首先，数组是*协变的*（covariant）。这个听起来很吓人的词简单来说意味着：如果 `Sub` 是 `Super` 的子类型，那么数组类型 `Sub[]` 也是数组类型 `Super[]` 的子类型。相比之下，泛型是*不变的*（invariant）：对于任何两个不同的类型 `Type1` 和 `Type2`，`List<Type1>` 既不是 `List<Type2>` 的子类型，也不是超类型 [JLS, 4.10; Naftalin07, 2.5]。你可能认为这意味着泛型是有缺陷的，但可以说数组是有缺陷的。这段代码片段是合法的：

```java
// 运行时失败！
Object[] objectArray = new Long[1];
objectArray[0] = "I don't fit in"; // 抛出 ArrayStoreException
```

但这段代码是不合法的：

```java
// 无法编译！
List<Object> ol = new ArrayList<Long>(); // 类型不兼容
ol.add("I don't fit in");
```

无论如何，你都不能将 `String` 放入 `Long` 容器中，但使用数组时你会在运行时发现犯了错误；而使用列表时，你会在编译时发现。当然，你更希望在编译时发现。

数组与泛型之间的第二个主要区别是数组是*实例化的*（reified [JLS, 4.7]）。这意味着数组在运行时知道并强制其元素类型。正如前面提到的，如果你尝试将 `String` 放入 `Long` 数组，你会得到一个 `ArrayStoreException`。相比之下，泛型是通过*擦除*（erasure）实现的 [JLS, 4.6]。这意味着它们仅在编译时强制类型约束，并在运行时丢弃（或*擦除*）其元素类型信息。擦除使得泛型类型能够与未使用泛型的遗留代码自由交互（Item 26），确保了向泛型的平滑过渡。

禁止创建泛型数组（generic array creation）可能会让人感到困恼。这意味着，例如，泛型集合无法返回其元素类型的数组（但请参见 Item 33 的部分解决方案）。它还意味着当你结合泛型使用变长参数（varargs）方法（Item 53）时，会得到混乱的警告。这是因为每当你调用变长参数方法时，都会创建一个数组来存储这些长度参数。如果该数组的元素类型不是可具体化的（reifiable），你就会得到一个警告。可以使用 `SafeVarargs` 注解来解决这个问题（Item 32）。

当你遇到泛型数组创建错误或对数组类型进行转换时的未检查转换警告时，最佳解决方案通常是使用集合类型 `List<E>` 而不是数组类型 `E[]`。你可能会牺牲一些简洁性或性能，但作为交换，你获得了更好的类型安全性和操作性。

例如，假设你想编写一个 `Chooser` 类，它的构造函数接收一个集合，并有一个单一方法返回从集合中随机选择的元素。根据你传递给构造函数的集合，你可以将 `chooser` 用作游戏骰子、魔力球或蒙特卡洛模拟的数据源。这里是一个不使用泛型的简单实现：

```java
// Chooser - 一个极度需要泛型的类！
public class Chooser {
    private final Object[] choiceArray;

    public Chooser(Collection choices) {
        choiceArray = choices.toArray();
    }

    public Object choose() {
        Random rnd = ThreadLocalRandom.current();
        return choiceArray[rnd.nextInt(choiceArray.length)];
    }
}
```

要使用此类，你每次调用该方法时，都必须将 `choose` 方法的返回值从 `Object` 强制转换所需的类型，如果类型错误，转换将在运行时失败。铭记了 Item 29 的建议后，我们尝试修改 `Chooser` 使其泛型化。更改用**粗体**显示：

```java
// 尝试使 Chooser 泛型化 - 无法编译
public class Chooser<T> {
    private final T[] choiceArray;

    public Chooser(Collection<T> choices) {
        choiceArray = choices.toArray();
    }

    // choose 方法未变
}
```

如果你尝试编译此类，你将得到此错误消息：

```text
Chooser.java:9: error: incompatible types: Object[] cannot be converted to T[]
```



`choiceArray = choices.toArray();`

```
^
where T is a type-variable:
  T extends Object declared in class Chooser
```

你可能会说，没什么大不了，我会把 `Object` 数组转换为 `T` 数组：

```java
choiceArray = (T[]) choices.toArray();
```

这消除了错误，但取而代之你得到了一个警告：

```text
Chooser.java:9: warning: [unchecked] unchecked cast
    choiceArray = (T[]) choices.toArray();
                               ^
  required: T[], found: Object[]
  where T is a type-variable:
T extends Object declared in class Chooser
```

编译器在告诉你，它无法在运行时保证转换的安全性，因为程序不知道 `T` 代表什么类型——记住，元素类型信息在运行时会从泛型中擦除。程序能运行吗？可以，但编译器无法证明这一点。你可以向自己证明这一点，将证明放在注释中并使用注解抑制警告，但你并没有从根本上消除警告的根源（Item 27）。

要消除未检查转换，请使用列表而不是数组。这是一个可以编译且没有错误或警告的 `Chooser` 类版本：

```java
// 基于列表的 Chooser - 类型安全的
public class Chooser<T> {
    private final List<T> choiceList;

    public Chooser(Collection<T> choices) {
        choiceList = new ArrayList<>(choices);
    }

    public T choose() {
        Random rnd = ThreadLocalRandom.current();
        return choiceList.get(rnd.nextInt(choiceList.size()));
    }
}
```

这个版本稍微冗长一点，可能稍微慢一点，但为了获得运行时不会出现 `ClassCastException` 的安心感，这是值得的。

总而言之，数组和泛型有非常不同的规则。数组是协变的且可化的（`reified`）；泛型是不变的且被擦除（`erased`）。因此，数组提供了运行时类型安全但不是编译时安全，泛型反亦然。按照规则，数组和泛型并不好混合。如果你发现自己正在混合使用它们并遇到编译时错误或警告，你的第一反应应该是将数组替换为列表。

### Item 29: 偏好泛型类型

对你的声明进行参数化并利用 JDK 提供的泛型类型和方法通常并不困难。编写自己的泛型类型稍微困难一些，但学习如何这样做是值得的。考虑来自 Item 7 的简单（玩具）栈实现：

```java
// 基于 Object 的集合 - 泛型的理想备人选
public class Stack {
    private Object[] elements;
    private int size = 0;
    private static final int DEFAULT_INITIAL_CAPACITY = 16;

    public Stack() {
        elements = new Object[DEFAULT_INITIAL_CAPACITY];
    }

    public void push(Object e) {
        ensureCapacity();
        elements[size++] = e;
    }

    public Object pop() {
        if (size == 0)
            throw new EmptyStackException();
        Object result = elements[--size];
        elements[size] = null; // 消除过期引用
        return result;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    private void ensureCapacity() {
        if (elements.length == size)
            elements = Arrays.copyOf(elements, 2 * size + 1);
    }
}
```

这个类本该应该是参数化的，但由于它不是，我们可以在事后对其*泛型化*（`generify`）。也就是说，我们可以在不影响原始非参数化客户端的情况下对其参数化。目前客户端必须转换从栈弹出的对象，这些转换在运行时可能会失败。泛型化类的第一步是在声明中添加一个或多个类型参数。在这种情况下，有一个类型参数代表栈的元素类型，该类型参数的约定名称是 `E`（Item 68）。

下一步是将所有类型 `Object` 替换为相应的类型参数，然后尝试编译生成的程序：

```java
// 尝试使 Stack 泛型化的 - 无法编译！
public class Stack<E> {
    private E[] elements;
    private int size = 0;
    private static final int DEFAULT_INITIAL_CAPACITY = 16;

    public Stack() {
        elements = new E[DEFAULT_INITIAL_CAPACITY];
    }

    public void push(E e) {
        ensureCapacity();
        elements[size++] = e;
    }

    public E pop() {
        if (size == 0)
            throw new EmptyStackException();
        E result = elements[--size];
        elements[size] = null; // 消除过期引用
        return result;
    }

    // ... isEmpty 和 ensureCapacity 没有变动
}
```

你通常会得到至少一个错误或警告，这个类也不例外。幸运的是，这个类只产生了一个错误：

```text
Stack.java:8: Generic 型数组创建
elements = new E[DEFAULT_INITIAL_CAPACITY];
            ^
```

正如 Item 28 所示，你不能创建不可重化的（`non-reifiable`）类型的数组，例如 `E`。每当你编写由数组支持的泛型类型时，都会出现这个问题。有两种合理的方法可以解决它。第一种解决方案直接绕过了对泛型数组创建的限制：创建一个 `Object` 数组并将其强制转换为泛型数组类型。现在，编译器不再产生错误，而是发出的警告。这种用法是合法的，但（通常来说）不是类型安全的：

```text
Stack.java:8: 警告：[unchecked] 未检查的强制转换
找到：Object[], 需要：E[]
elements = (E[]) new Object[DEFAULT_INITIAL_CAPACITY];
            ^
```

编译器可能无法证明你的程序是类型安全的，但你可以。你必须说服自己未检查的强制转换不会破坏程序的类型安全。相关的数组（`elements`）存储在私有字段中，永远不会返回给客户端或传递给任何其他方法。数组中存储的元素只有传递给 `push` 方法的元素，它们的类型为 `E`，因此未检查的强制转换没有任何害。

一旦你证明了未检查的强制转换是安全的，请在尽可能小的范围内抑制警告（Item 27）。在这种情况下，构造函数只包含未检查的数组创建，因此在整个构造函数中抑制警告是合适的。通过添加注解来实现这一点，`Stack` 可以顺利通过编译，你可以使用它而无需显式强制转换，也不担心 `ClassCastException`：

```java
// elements 数组将只包含来自 push(E) 的 E 实例。
// 这足以确保类型安全，但数组的运行时
// 类型将不是 E[]; 它将始终是 Object[]！
@SuppressWarnings("unchecked")
public Stack() {
    elements = (E[]) new Object[DEFAULT_INITIAL_CAPACITY];
}
```

在 `Stack` 中消除泛型数组创建错误的第二种方法是将字段 `elements` 的类型从 `E[]` 改为 `Object[]`。如果你这样做，你会得到不同的错误：

```text
Stack.java:19: 类型不兼容
找到：Object, 需要：E
E result = elements[--size];
           ^
```

你可以通过将从数组中检索的元素强制转换为 `E` 来将此错误转换为警告，但你会得到一个警告：

```text
Stack.java:19: 警告：[unchecked] 未检查的强制转换
找到：Object, 需要：E
E result = (E) elements[--size];
             ^
```

由于 `E` 是一个不可重化的类型，编译器无法在运行时检查该强制转换。同样，你可以很容易地说服自己未检查的强制转换是安全的，因此抑制警告是合适的。根据 Item 27 的建议，我们只在包含未检查强制转换的赋值处抑制警告，而不是整个整个 `pop` 方法：

```java
// 对未检查警告的适当抑制
public E pop() {
    if (size == 0)
        throw new EmptyStackException();
    // push 要求元素类型为 E，因此强制转换是正确的
    @SuppressWarnings("unchecked") E result =
        (E) elements[--size];
    elements[size] = null; // 消除过时引用
    return result;
}
```

*(注：原文中存在大量重复内容，译文已去重并保留核心逻辑)*

### 使用了原始类型 - 不可接受！(Item 26)

```java
public static Set union(Set s1, Set s2) {
    Set result = new HashSet(s1);
    result.addAll(s2);
    return result;
}
```

该方法可以编译，但有两个警告：

```text
Union.java:5: warning: [unchecked] 未检查的调用
`HashSet(Collection<? extends E>)` 作为原始类型 `HashSet` 的成员
`Set result = new HashSet(s1);`
^

Union.java:6: warning: [unchecked] 未检查的调用
`addAll(Collection<? extends E>)` 作为原始类型 `Set` 的成员
`result.addAll(s2);`
^
```

为了修复这些警告并使方法类型安全，请修改其声明，声明一个代表三个集合（两个参数和一个返回值）的元素类型的*类型参数*，并在整个方法中使用该类型参数。**声明类型参数的类型参数列表位于方法的修符和返回类型之间。** 在示例中，类型参数列表为 `<E>`，返回类型为 `Set<E>`。类型参数的命名约定对于泛型方法和泛型类型是相同的（Items 29, 68）：

```java
// 泛型方法
public static <E> Set<E> union(Set<E> s1, Set<E> s2) {
    Set<E> result = new HashSet<>(s1);
    result.addAll(s2);
    return result;
}
```

至少对于简单的泛型方法，就此了。该方法编译时不产生任何警告，并提供了类型安全性和易用性。这里是一个练习该方法的简单程序。该程序不包含强制转换，且编译没有错误或警告：

```java
// 练习泛型方法的简单程序
public static void main(String[] args) {
    Set<String> guys = Set.of("Tom", "Dick", "Harry");
    Set<String> stooges = Set.of("Larry", "Moe", "Curly");
    Set<String> aflCio = union(guys, stooges);
    System.out.println(aflCio);
}
```

当你运行该程序时，它会打印 `[Moe, Tom, Harry, Larry, Curly, Dick]`。（输出中元素的顺序取决于实现。）

`union` 方法的局限性是三个集合的类型（包括输入参数和返回值）必须完全相同。你可以通过*边界通配符类型*来使方法更灵活（Item 31）。

有时，你需要创建一个不可变但适用于许多不同类型的对象。由于泛型是通过擦除实现的（Item 28），你可以使用单个对象用于所有所需的类型参数化，但你需要编写一个静态工厂方法来为每个请求的类型参数化反复分发该对象。这种模式被称为*泛型单例工厂*，用于函数对象（Item 42），如 `Collections.reverseOrder`，偶尔也用于集合如 `Collections.emptySet`。

假设你想编写一个恒等函数分发器。库提供了 `Function.identity`，所以没有理由编写自己的（Item 59），但这样做是有启发意义的。在每次请求时创建一个新的恒等函数对象是浪费的，因为它是无状态的。如果 Java 的泛型是具体化的，你每个类型需要一个恒等函数，但由于它们被擦除了，一个泛型单例就足够了。如下所示：

```java
// 泛型单例工厂
private static UnaryOperator<Object> IDENTITY_FN = (t) -> t;

@SuppressWarnings("unchecked")
public static <T> UnaryOperator<T> identityFunction() {
    return (UnaryOperator<T>) IDENTITY_FN;
}
```

将 `IDENTITY_FN` 强制转换为 `(UnaryFunction<T>)` 会产生未检查的转换警告，因为对于每个 `T`，`UnaryOperator<Object>` 并不是 `UnaryOperator<T>`。但恒等函数是特殊的：它返回它的参数。

总之，泛型方法与泛型类型一样，比那些要求客户端对输入参数和返回值进行显式强制转换的方法更安全、更容易使用。就像类型一样，你应该确保你的方法可以在不需要强制转换的情况下使用，这通常意味着将它们泛型化。就像类型一样，你应该对那些使用需要强制转换的现有方法进行泛型化。这可以在不破坏现有客户端的情况下，让新用户的生活变得轻松 (Item 26)。

### Item 31: 使用有界通配符增加 API 的灵活性

正如 Item 28 所述，参数化类型是*不变的*（`invariant`）。换句话说，对于任何两个不同的类型 `Type1` 和 `Type2`，`List<Type1>`既不是 `List<Type2>` 的子类型，也不是超类型。尽管 `List<String>` 不是 `List<Object>` 的子类型听起来不符合直觉，但它确实很有道理。你可以将任何对象放入 `List<Object>`，但只能将字符串放入 `List<String>`。由于 `List<String>` 无法做 `List<Object>` 能做的一切，因此它不是子类型（根据里氏夫替换原则 (Item 10)）。

有时，你需要比不变类型能提供的更多灵活性。考虑 Item 29 中的 `Stack` 类。为了唤起你的记忆，这里是它的公共 API：

```java
public class Stack<E> {
    public Stack();
    public void push(E e);
    public E pop();
    public boolean isEmpty();
}
```

假设我们想添加一个方法，接收元素序列并将它们全部推入栈中。这里是第一次尝试：

```java
// 没有使用通配符类型的 pushAll 方法 - 不完善！
public void pushAll(Iterable<E> src) {
    for (E e : src)
        push(e);
}
```



这个方法可以顺利编译，但并不尽如人意。如果`Iterable src`的元素类型与栈的元素类型完全匹配，它可以运行良好。但假设你有一个`Stack<Number>`并调用了`push(intVal)`，其中`intVal`的类型是`Integer`。这是可以的，因为`Integer`是`Number`的子类型。所以逻辑上讲，这似乎也应该是：

```java
Stack<Number> numberStack = new Stack<>();

Iterable<Integer> integers = ... ;

numberStack.pushAll(integers);
```

然而，如果你尝试这样做，你会得到这个错误信息，因为参数化类型是不变的：

```
StackTest.java:7: error: incompatible types: Iterable<Integer>
cannot be converted to Iterable<Number>
    numberStack.pushAll(integers);
^
```

幸运的是，有一个办法。语言提供了一种特殊的参数化类型，称为有界通配符类型（bounded wildcard type），用来处理这种情况。`pushAll`输入参数的类型不应该是`E`的`Iterable`，而是`E`的某个子类型的`Iterable`，而有一种通配符类型恰恰表示此意：`Iterable<? extends E>`。（使用`extends`关键字稍微有点误导性：回想Item 29，子类型的定义使得每个类型都是自身的子类型，尽管它并没有扩展自身。）让我们修改`pushAll`以使用这种类型：

```java
// 作为 E 生产者的参数的通配符类型
public void pushAll(Iterable<? extends E> src) {
    for (E e : src)
        push(e);
}
```

通过这一更改，不仅`Stack`能够顺利编译，那些在原始`pushAll`声明下无法编译的客户端代码也能顺利编译。由于`Stack`及其客户端都能顺利编译，你就知道一切都是类型安全的。

现在假设你想写一个`popAll`方法来配合`pushAll`使用。`popAll`方法从栈中弹出每个元素并将元素添加到给定的集合中。这是第一次尝试编写`popAll`方法的写法：

```java
// 没有使用通配符类型的 popAll 方法 - 不完善！
public void popAll(Collection<E> dst) {
    while (!isEmpty())
        dst.add(pop());
}
```

同样，如果目标集合的元素类型与栈的元素类型完全匹配，它就可以顺利编译并运行良好。但再次，它并不完全尽如人意。假设你有一个`Stack<Number>`和类型为`Object`的变量。如果你从栈中弹出一个元素并存储在变量中，它可以通过编译并运行而没有错误。那么你不也应该能够这样做吗？

```java
Stack<Number> numberStack = new Stack<Number>();
Collection<Object> objects = ... ;
numberStack.popAll(objects);
```

如果你尝试针对之前显示的`popAll`版本编译这段客户端代码，你会得到一个与我们从第一个版本的`pushAll`中得到的非常相似的错误：`Collection<Object>`不是`Collection<Number>`的子类型。再次，通配符类型提供了一个解决办法。`popAll`输入参数的类型不应该是“`E`的集合”，而是“`E`的某个超类型的集合”（其中超类型的定义使得`E`是它的子类型）。再次，有一种通配符类型恰恰表示此意：`Collection<? super E>`。让我们修改`popAll`来使用它：

```java
// 作为 E 消费者的参数的通配符类型
public void popAll(Collection<? super E> dst) {
    while (!isEmpty())
        dst.add(pop());
}
```

教训是明确的。**为了最大的灵活性，对代表生产者或消费者的输入参数使用通配符类型。**如果一个输入参数既是生产者又是消费者，那么通配符类型对你很有用：这里有一个帮助你记住使用哪种通配符类型的口诀：

**PECS 代表生产者-extends, 消费者-super。**

换句话说，如果一个参数化类型代表生产者，使用`<? extends T>`；如果它代表消费者，使用`<? super T>`。在我们`Stack`示例中，`pushAll`的参数`src`产生`E`实例，因此`src`的适当类型是`Iterable<? extends E>`；`popAll`的参数`dst`消费`E`实例，因此`dst`的适当类型是`Collection<? super E>`。PECS口诀捕捉了指导通配符使用的基本原则。

记住这个口诀，让我们看看本之前章节中的一些方法和构造函数声明。Item 28中的`Chooser`构造函数有如下声明：

```java
public Chooser(Collection<T> choices)
```

这个构造函数仅使用集合`choices`来产生类型为`T`的值（并存储供以后使用），因此它的声明应该使用扩展`T`的通配符类型。这是生成的构造函数声明：

```java
// 作为 T 生产者的参数的通配符类型
public Chooser(Collection<? extends T> choices)
```

这种更改在实践中会有任何区别吗？会有。假设你有一个`List<Integer>`，并且你想将其传递给`Chooser<Number>`的构造函数。在原始声明下无法编译，但一旦我们在声明中添加了有界通配符类型，就可以编译了。

两个参数`s1`和`s2`都是`E`的生产者，因此PECS助记法告诉我们声明如下：

```java
public static <E> Set<E> union(Set<? extends E> s1,
                               Set<? extends E> s2)
```

注意返回类型仍然是`Set<E>`。**不要使用有界通配符类型作为返回类型。**这样做不仅没有为用户提供额外的灵活性，反而会强迫他们在客户端代码中使用通配符类型。使用修改后的声明，这段代码将顺利编译：

```java
Set<Integer> integers = Set.of(1, 3, 5);
Set<Double> doubles = Set.of(2.0, 4.0, 6.0);
Set<Number> numbers = union(integers, doubles);
```

使用得当，通配符类型对类的用户来说几乎是不可见的。它们使得方法能够接受它们应该接受的参数，并拒绝它们应该拒绝的参数。**如果类的用户必须考虑通配符类型，那么它的API设计可能有问题。**

在Java 8之前，类型推断规则不够智能以处理前面的代码片段，该片段需要编译器使用上下文指定的返回类型（或目标类型）来推断`E`的类型。之前所示`union`用的目标类型是`Set<Number>`。如果你尝试在较早的Java版本中编译该片段（使用适当的`Set.of`厂方法替换），你会得到像这样长且复杂的错误信息：

```text
Union.java:14: error: incompatible types
    Set<Number> numbers = union(integers, doubles);
                                 ^
    required: Set<Number>
    found:   Set<INT#1>
  where INT#1,INT#2 are intersection types:
    INT#1 extends Number,Comparable<? extends INT#2>
    INT#2 extends Number,Comparable<?>
```

幸运的是，有一种方法可以处理这类错误。如果编译器没有推导出正确的类型，你始终可以通过显式类型参数告诉它使用哪种类型 [JLS, 15.12]。即使在Java 8引入目标类型之前，这也不是你经常需要的事情，这是好事，因为显式类型参数并不好看。通过添加显式类型参数（如下所示），代码片段在Java 8之前的版本中可以顺利编译：

```java
// 显式类型参数 - Java 8 之前需要
Set<Number> numbers = Union.<Number>union(integers, doubles);
```

接下来，让我们关注项目30中的`max`方法。这里是原始声明：

```java
public static <T extends Comparable<T>> T max(List<T> list)
```

这里是使用通配符类型的修改后的声明：

```java
public static <T extends Comparable<? super T>> T max(
    List<? extends T> list)
```

为了从原始声明获得修改后的声明，我们应用了两次PECS启发式方法。直接应用于参数`list`。它产生`T`实例，因此我们将类型从`List<T>`更改为`List<? extends T>`。复杂的应用是类型参数`T`。这是我们第一次看到将通配符应用于类型参数。最初，`T`被指定为扩展`Comparable<T>`，但`T`的可比较对象会消耗`T`实例（并产生指示顺序关系的整数）。因此，参数化类型`Comparable<T>`被有界通配符类型`Comparable<? super T>`取替。可比较对象始终是消耗者，因此你通常应该**优先使用`Comparable<? super T>`而不是`Comparable<T>`**。比较器（Comparator）也是如此；因此你通常应该**优先使用`Comparator<? super T>`而不是`Comparator<T>`**。

修改后的`max`声明可能是最复杂的。增加的复杂性换来了什么吗？再次，换来了。这里有一个简单的列表示例，原始声明会排除它：

```java
List<? extends T> list
```

还有一个值得讨论的与通配符相关的课题。类型参数和通配符之间存在对立性，许多方法可以使用其中一种来声明。例如，这里是方法的两种可能的声明：

```java
public static <E> void swap(List<E> list, int i, j);
public static void swap(List<?> list, int i, j);
```

这两个声明中哪个更好？在公共API中，第二种更好，因为它更简单。作为一个规则，**如果类型参数在声明中只出现一次，就将其替换为通配符**。如果它是无界类型参数，将其替换为无界通配符；如果它是有界类型参数，将其替换为有界通配符。

等等，似乎我们无法将刚刚取出的元素放回列表中是不对的。问题是`list`的类型是`List<?>`，你不能向`List<?>`放入`null`以外的任何值。幸运的是，有一种方法不需要不安全转换或原始类型来实现此方法。思路是编写一个私有辅助方法来捕获通配符类型。辅助方法必须是泛型方法以便捕获类型。如下所示：

```java
public static void swap(List<?> list, int i, int j) {
    swapHelper(list, i, j);
}

// 用于捕获通配符的私有辅助方法
private static <E> void swapHelper(List<E> list, int i, int j) {
    list.set(i, list.set(j, list.get(i)));
}
```

`swapHelper`方法知道`list`是一个`List<E>`。因此，它知道从这个列表中获取的任何值都是类型`E`，并且将任何类型为`E`的值放入列表中都是安全的。这种稍显复杂的`swap`实现可以整洁地编译。它允许我们导出优雅的、基于通配符的声明，同时在内部利用更复杂的泛型方法。`swap`方法的调用者不需要面对更复杂的`swapHelper`声明，但他们确实从中受益。值得注意的是，该辅助方法的签名恰恰是那些之前认为对于公共方法来说过于复杂的签名。

总而言之，在API中使用通配符类型虽然复杂，但它会让API变得灵活得多。如果你编写一个将要广泛使用的库，应该将正确使用通配符类型视为强制性。记住基本规则：`producer-extends`，`consumer-super` (PECS)。还要记住，所有的`Comparable`和`Comparator`都是消费者。

### Item 32: 明智地结合泛型和变长参数

变长参数方法（Item 53）和泛型都是在Java 5中引入平台的，因此你可能期望它们能够优雅地交互；遗憾的是，它们并没有。变长参数的目的是允许调用者向方法传递数量数量的参数，但它是一个泄漏的抽象（leaky abstraction）：当你调用变长参数方法时，会创建一个数组来存放这些变长参数；该数组本应是一个实现细节，现在却是可见的。因此，当变长参数具有泛型或参数化类型时，你会得到令人困惑的编译器警告。

回想Item 28，一个非可重化类型（non-reifiable type）是指其运行时表示比编译时表示包含更的信息，而几乎所有的泛型和参数化类型都是非可重化的。如果方法声明其变长参数为非可重化类型，编译器会在声明处生成警告。如果在一个推断类型为非可重化的变长参数上调用该方法，编译器也会在调用处生成警告。这些警告看起来像这样：

```
warning: [unchecked] Possible heap pollution from
    parameterized vararg type List<String>
```

堆污染（Heap pollution）发生在一个参数化类型的变量指向一个并非该类型的对象时 [JLS, 4.12.2]。它可能会导致编译器自动生成的类型转换失败，违反泛型类型系统的根本保证。

例如，考虑这个方法，它是第127页代码片段的伪装变体：

```
// 混合泛型和变长参数可能会违反类型安全！
static void dangerous(List<String>... stringLists) {
    List<Integer> intList = List.of(42);
    Object[] objects = stringLists;
    objects[0] = intList;
}
```

这种方法本身没有任何错误，因此它编译时不会产生任何警告。但当你运行它时，它会抛出一个`ClassCastException`，尽管其中没有任何可见的强制类型转换。你没有看到的是，编译器对`pickTwo`返回的值生成了到`String[]`的隐式转换，以便将其存储在`attributes`中。该转换失败了，因为`Object[]`不是`String[]`的子类型。这种失败令人困惑，因为它与导致堆污染的方法（`toArray`）相隔两个层级，而且在实际参数存储进去之后，变长参数并没有被修改。

这个例子旨在说明一点：让另一个方法访问泛型变长参数（genericargs）数组是不安全的，但有两个例外：将数组传递给另一个正确标记了`@SafeVarargs`注解的变长方法是安全的；将数组传递给一个仅计算某些内容的非变长方法也是安全的。

这里有一个泛使用泛型变长参数的示例。该方法接收任意数量的列表，并返回一个包含所有输入列表的单个列表。由于该方法标记了`@SafeVarargs`注解，它在声明处或调用处都不会生成任何警告：

#### 带有泛型变长参数的安全方法

```java
@SafeVarargs
static <T> List<T> flatten(List<? extends T>... lists) {
    List<T> result = new ArrayList<>();
    for (List<? extends T> list : lists) {
        result.addAll(list);
    }
    return result;
}
```



决定何时使用`@SafeVarargs`的规则很简单：在每个带有泛型或参数类型的方法上使用它，这样它的用户就不会被没必要且误惑的编译器警告所困扰。这意味着你应该编写像`dangerous`或`toArray`这样不安全的变长方法。每当编译器警告你你控制的方法中的泛型变长参数可能导致堆污染时，检查该方法是否是安全的。提醒一下，泛型方法满足以下条件时是安全的：

1. 它没有在变长数组中存储任何内容，并且
2. 它没有让该数组（或其克隆）对不可信的代码可见。

如果违反了其中任何一项规定，请修复它。

注意，`@SafeVarargs`注解仅在不可覆盖的方法上合法的，因为无法保证每个覆盖方法都是安全的。在 Java 8 中，该注解仅对静态方法和 final 实例方法合法；在 Java 9 中，它也变为私有实例方法合法。

使用`@SafeVarargs`注解的替代方案是采取第 28 条的建议，将变长参数（本质上是一个数组）替换为`List`参数。以下是这种方法应用于我们的`flatten`方法时的样子。注意，只有参数声明发生了变化：

点击此处查看代码图片

#### List 作为泛型变长参数的类型安全替代

```java
static <T> List<T> flatten(List<List<? extends T>> lists) {
    List<T> result = new ArrayList<>();
    for (List<? extends T> list : lists) {
        result.addAll(list);
    }
    return result;
}
```

该方法可以与静态工厂方法`List.of`结合使用，以允许任意数量的参数。注意，这种方法依赖于`List.of`的声明标记了`@SafeVarargs`注解：

点击此处查看代码图片

```java
audience = flatten(List.of(friends, romans, countrymen));
```

这种方法的优点是编译器可以证明该方法是类型安全的。你不需要通过`@SafeVarargs`注解来保证它的安全性，也不必担心可能在判断其安全性时可能了错。主要的缺点是客户端代码稍微冗长，并且运行速度可能慢一点。

这种技巧也可以用于无法编写安全变长方法的情况，如第 147 页上的`toArray`方法。它的`List`对应物是`List.of`方法，所以我们甚至不需要编写它；Java 库的作者已经为我们完成了这项工作。`pickTwo`方法随后变成了：

点击此处查看代码图片

```java
static <T> List<T> pickTwo(T a, T b, T c) {
    switch(rnd.nextInt(3)) {
        case 0: return List.of(a, b);
        case 1: return List.of(a, c);
        case 2: return List.of(b, c);
    }
}
```

主方法变为：

点击此处查看代码图片

```java
public static void main(String[] args) {
    List<String> attributes = pickTwo("Good", "Fast", "Cheap");
}
```

总结来说，变长参数和泛型之间的结合并不良好，因为变长参数是数组之上的泄露抽象。变长参数的类型不是类型安全的，因为数组不是协变的。

### 第 33 条：考虑类型安全的异构容器

泛型的常见用途包括集合，如`Set<E>`和`Map<K,V>`，以及单元素容器，如`ThreadLocal<T>`和`AtomicReference<T>`。在所有这些用法中，被参数化的都是容器。通常这正是你所期望的。

然而，有时你需要灵活性。例如，数据库行可以有任意数量的列，如果能够以类型安全的方式访问所有列就太好了。幸运的是，有一种简单的方法可以实现这一点。这种思想是对*键*而不是容器进行参数化。然后将参数化的键呈现给容器以插入或检索值。泛型类型系统被用于保证值的类型与其键一致。

作为这种方法的一个简单示例，考虑一个`Favorites`类，它允许客户端存储和检索任意数量类型的喜好实例。该类型的`Class`对象将充当参数化的键。这种方法之所以有效是因为类是泛型的。类字面量的类型不仅仅是`Class`，而是`Class<T>`。例如，`String.class`的类型是`Class<String>`，`Integer.class`的类型是`Class<Integer>`。当类字面量在方法之间传递以通信编译时运行时类型信息时，它被称为*类型令牌*（type token）[Bracha04]。

`Favorites`类的 API 非常简单。它就像一个简单的 map，只是键参数化的而不是 map。客户端在设置和获取喜好时呈现`Class`对象。这里是其 API：

点击此处查看代码图片

```java
public class Favorites {
    public <T> putFavorite(Class<T> type, T instance);
    public <T> T getFavorite(Class<T> type);
}
```

这是一个测试`Favorites`类的示例程序，存储、检索并打印喜好的`String`、`Integer`和`Class`实例：

点击此处查看代码图片

```java
public static void main(String[] args) {
    Favorites f = new Favorites();
}
```

```java
f.putFavorite(String.class, "Java");
f.putFavorite(Integer.class, 0xcafebabe);
f.putFavorite(Class.class, Favorites.class);
String favoriteString = f.getFavorite(String.class);
int favoriteInteger = f.getFavorite(Integer.class);
Class<?> favoriteClass = f.getFavorite(Class.class);
System.out.printf("%s %x %s%n", favoriteString,
    favoriteInteger, favoriteClass.getName());
```

正如你所期的，这个程序打印了`Java cafebabe Favorites`。顺便注意，Java 的`printf`方法与 C 语言的区别在于，你应该在原本 C 使用`\n`的地方使用`%n`。`%n`会生成与平台相关的行分隔符，它在许多（但不是所有）平台上都是`\n`。

`Favorites`实例是*类型安全的*：当你向它请求`String`时，它永远不会返回`Integer`。它还是*异构的*：与普通的 map 不同，所有的键都是不同类型。因此，我们称`Favorites`为*类型安全的异构容器*。

`Favorites`的实现出奇地简单。这里是完整代码：

点击此处查看代码图像

### // 类型安全的异构容器模式 - 实现

```java
public class Favorites {
    private Map<Class<?>, Object> favorites = new HashMap<>();

    public <T> void putFavorite(Class<T> type, T instance) {
        favorites.put(Objects.requireNonNull(type), instance);
    }

    public <T> T getFavorite(Class<T> type) {
        return type.cast(favorites.get(type));
    }
}
```

这里面有一些微妙之处。每个`Favorites`实例都由一个名为`favorites`的私有`Map<Class<?>, Object>`支撑。你可能认为由于无界通配符类型而无法向这个`Map`中放入任何东西，但事实恰恰相反。需要注意的是，通配符类型是嵌套的：通配符类型不是 map 的类型，而是其键的类型。这意味着每个键都可以拥有一个*不同*的参数化类型：其中一个可以是`Class<String>`，下一个可以是`Class<Integer>`，依此类推。这就是异构性的来源。

接下来需要注意的是，`favorites`Map 的值类型仅仅是`Object`。换句话说，`Map`并不保证键和值之间的类型关系（即每个值都是其键所代表的类型）。事实上，Java 的类型系统并不强大到可以表达这一点。但我们知道这是真的，并且在检索偏好项时利用了这一点。

`putFavorite`的实现显而易见：它简单地向`favorites`存入从给定的`Class`对象到给定的偏好实例的映射。如所述，这丢弃了键和值之间的“类型链接”；它丢失了值是键的实例这一知识。但没关系，因为`getFavorites`方法可以并且确实重新建立了这种链接。

`getFavorite`的实现比`putFavorite`更复杂一些。首先，它从`favorites`map 中获取与给定的`Class`对象对应的值。这是要返回的正确对象引用，但它的编译时类型是错误的：它是`Object`（`favorites`map 的值类型），而我们需要返回一个`T`。因此，`getFavorite`的实现使用`Class`的`cast`方法，将对象引用*动态转换*为`Class`对象所代表的类型。

`cast`方法是 Java 强制转换操作符的动态等价物。它简单地检查参数是否为`Class`对象所代表类型的实例。如果是，则返回参数；否则抛出`ClassCastException`。我们知道`getFavorite`中的转换调用不会抛出`ClassCastException`，前提是客户端代码通过了编译。也就是说，我们知道`favorites`map 中的值始终与其键的类型匹配。

既然`cast`方法仅仅是返回其参数，那么它为我们做了什么？`cast`方法的签名充分利用了`Class`类是泛型的事实。它的返回类型是`Class`对象的类型参数：

点击此处查看代码图像

```java
public class Class<T> {
    T cast(Object obj);
}
```

这正是`getFavorite`方法需要的。正是它让我们能够在不诉助于对`T`进行强制强制转换的情况下，使`Favorites`变得类型安全。

`Favorites`类有两个值得注意的局限性。首先，恶意的客户端……（注：原文最后几段存在重复或混乱句子，但关于`Class`局限性的核心逻辑已保留）。

参数`annotationType`是一个受限类型令牌（bounded type token），表示一种注解类型。该方法返回该元素的该类型注解（如果存在），如果不存在，则返回`null`。从本质上说，一个带有注解的元素是一个类型安全的异构容器，其键是注解类型。

假设你有一个类型为`Class<?>`的对象，并想将其传递给需要受限类型令牌的方法，例如`getAnnotation`。你可以将该对象强制转换为`Class<? extends Annotation>`，但这种强制转换是不经过检查的（unchecked），因此会产生编译时警告（Item 27）。幸运的是，`Class`类提供了一个实例方法，可以安全地（动态地）执行这种强制转换。该方法名为`asSubclass`，它将其被调用的`Class`对象强制转换为表示其参数所代表的类的子类的类。如果转换成功，该方法将返回其参数；如果转换失败，则会抛出`ClassCastException`。

以下是如何使用`asSubclass`方法读取类型在编译时未知的注解的方法。该方法编译时没有错误或警告：

点击此处查看代码图片

```java
// 使用 asSubclass 安全地强制转换为受限类型令牌
static Annotation getAnnotation(AnnotatedElement element,
                                 String annotationTypeName) {
    Class<?> annotationType = null; // 无界限类型令牌
    try {
        annotationType = Class.forName(annotationTypeName);
    } catch (Exception ex) {
        throw new IllegalArgumentException(ex);
    }
    return element.getAnnotation(
        annotationType.asSubclass(Annotation.class));
}
```

总结来说，泛型的普通用法（以集合 API 为例）限制了每个容器只能有固定数量的类型参数。你可以通过将类型参数放置在键而不是容器上来绕过这一限制。你可以使用`Class`对象作为此类类型安全异构容器的键。以这种方式使用的`Class`对象被称为类型令牌（type token）。你也可以使用自定义的键类型。例如，你可以有一个代表数据库行的`DatabaseRow`类型（容器），以及一个泛型类型`Column<T>`作为其键。

## 第 6 章：枚举与注解

JAVA 支持两种特殊用途的引用类型族：一种称为*枚举类型*（enum type）的类和一种称为*注解类型*（annotation type）的接口。本章讨论了使用这些类型族的最佳实践。

### Item 34：使用枚举代替`int`常数

*枚举类型*（enumerated type）是一种合法值由固定常量集合组成的类型，例如季节、太阳系中的行星或扑牌中的花色。在枚举类型被添加到语言之前，表示枚举类型的常用模式是声明一组命名的`int`常数，为该类型的每个成员声明一个常量：

点击此处查看代码图片

```java
// int 枚举模式 - 严重缺陷！
public static final int APPLE_FUJI         = 0;
public static final int APPLE_PIPPIN      = 1;
public static final int APPLE_GRANNY_SMITH = 2;

public static final int ORANGE_NAVEL      = 0;
public static final int ORANGE_TEMPLE     = 1;
public static final int ORANGE_BLOOD      = 2;
```

这种被称为*`int`枚举模式*（`int` enum pattern）的技术有许多缺点。它在类型安全方面没有提供任何帮助，在表达能力方面也乏乎无几。如果你将苹果传递给一个期望橘子的方法，使用`==`运算符比较苹果和橘子，或者更糟，编译器不会抱怨：

点击此处查看代码图片

```java
// 美味的的柑橘味苹果酱！
int i = (APPLE_FUJI - ORANGE_TEMPLE) / APPLE_PIPPIN;
```

注意，每个苹果常量的名称都带有`APPLE_`前缀，每个橘子常量的名称带有`ORANGE_`前缀。这是因为 Java 没有为`int`枚举组提供命名空间。前缀可以防止两个`int`枚举组具有同名常量时发生命名冲突，例如`ELEMENT_MERCURY`和`PLANET_MERCURY`之间。

使用`int`枚举的程序是脆弱的。因为`int`枚举是*常量变量* [JLS, 4.12.4]，它们的`int`值会被编译到使用它们的客户端中 [JLS, 13.1]。如果与`int`枚举关联的值发生变化，其客户端必须重新编译。否则，客户端将仍然运行，但它们的行为将是错误的。

没有简单的方法可以将`int`枚举常量转换为可打印的字符串。如果你打印此类常量或从调试器中显示它，你看到的只是一个数字，这并没太大帮助。没有可靠的方法可以遍历组中所有的`int`枚举常量，甚至无法获取一个`int`枚举组的大小。

你可能会遇到这种模式的变体，其中使用`String`常数代替了`int`常数。这种被称为*`String`枚举模式*（`String` enum pattern）的变体更不可理想。虽然它确实为常量提供了可打印的字符串，但它可能导致新手用户将字符串常量硬编码到客户端代码中，而不是使用字段名。如果这样的硬编码字符串常量包含拼写错误，它将逃避编译时的检测并导致错误。

幸运的是，Java 提供了一种替代方案，它避免了`int`枚举模式的所有缺点并提供了许多额外好处。这就是*枚举类型*（enum type） [JLS, 8.9]。它在最简单的形式下如下：

点击此处查看代码图片

```java
public enum Apple { FUJI, PIPPIN, GRANNY_SMITH }
public enum Orange { NAVEL, TEMPLE, BLOOD }
```



从表面上看，这些枚举类型可能与 C、C++ 等语言的枚举相似，但外观具有欺骗性。Java 的枚举类型是功能类，远比这些语言中作为 `int` 值的枚举强大。

Java 枚举类型背后的思想很简单：它们通过静态 `final` 字段导出每个枚举导出实例。由于没有可见的构造函数，枚举类型实际上是 `final` 的。因为客户端无法创建枚举类型的实例也不能扩展它，因此除了定义的枚举常量外没有其他实例。换句话说，枚举类型是实例控制的（第 6 页）。它们是单例 (Item 3) 的泛化，单例本质是单元素枚举。

枚举提供了编译时的类型安全。如果你将参数声明为 `Apple` 类型，你可以保证传递给参数的非空对象引用是三个有效的 `Apple` 值之一。传递错误类型的值将导致编译错误，将一个枚举类型的表达式赋值给另一个类型的变量或使用 `==` 运算符比较不同枚举类型的值也是如此。

具有相同常量的枚举类型可以共存，因为每个类型都有自己的命名空间。你可以在枚举类型中添加或重新排序常量，而无需重新编译客户端，因为导出常量的字段提供了枚举类型与客户端之间的隔离层：常量值不会被编译到客户端中，就像在 `int` 枚举模式中那样。最后，你可以通过调用 `toString` 方法将枚举转换为可打印的字符串。

除了修正 `int` 枚举的缺陷外，枚举类型允许你添加任意的方法和字段并实现任意接口。它们提供了 `Object` 方法的高质量实现 (第 3 章)，实现了 `Comparable` (Item 14) 和 `Serializable` (第 12 章)，它们的序列化形式设计能够抵御枚举类型的大多数更改。

那么，为什么你想向枚举（`enum`）类型添加方法或字段呢？首先，你可能想将其常量与数据关联起来。例如，我们的 `Apple` 和 `Orange` 类型可能会从一个返回水果颜色的方法，或者一个返回其图像的方法中受益。你可以用任何看起来合适的方法来增强枚举类型。枚举类型最初可能只是枚举常量的简单集合，并随着时间的推移演变为一个功能完备的抽象。

关于丰富枚举类型的很好的例子，考虑我们太阳系中的八大行星。每个行星都有质量和半径，通过这两个属性，你可以计算出它的表面引力。这反过来又让你能在给定物体质量的情况下，计算出物体在行星表面的重量。以下是该枚举的样子。每个枚举常量后面括号中的数字是传递给构造函数的参数。在这种情况下，它们是行星的质量和半径：

```
// 带有数据和行为的枚举类型
```

```java
public enum Planet {

    MERCURY(3.302e+23, 2.439e6),

    VENUS  (4.869e+24, 6.052e6),

    EARTH  (5.975e+24, 6.378e6),

    MARS   (6.419e+23, 3.393e6),

    JUPITER(1.899e+27, 7.149e7),

    SATURN (5.685e+26, 6.027e7),

    URANUS (8.683e+25, 2.556e7),

    NEPTUNE(1.024e+26, 2.477e7);

    private final double mass;           // 公斤

    private final double radius;          // 米

    private final double surfaceGravity; // m / s²

    // 万有引力常数，单位为 m³ / kg s²

    private static final double G = 6.67300E-11;

    // 构造函数

    Planet(double mass, double radius) {

        this.mass = mass;

        this.radius = radius;

        surfaceGravity = G * mass / (radius * radius);

    }

    public double mass()            { return mass; }

    public double radius()          { return radius; }

    public double surfaceGravity() { return surfaceGravity; }

    public double surfaceWeight(double mass) {

        return mass * surfaceGravity;  // F = ma

    }

}
```

编写像 `Planet` 这样丰富的枚举类型是很容易的。**要将数据与枚举常量关联，请声明实例字段并编写一个接收数据并存储在字段中的构造函数。** 枚举本质上是不可变的，因此所有字段都应该是 `final` 的（Item 17）。字段可以是公共的，但将它们设为私有并提供公共访问器更好（Item 16）。在 `Planet` 的情况下，构造函数还计算并存储了表面引力，但这仅仅是一种优化。在每次由 `surfaceWeight` 方法使用时，都可以根据质量和半径重新计算引力，该方法接收物体的质量并返回其在常量所代表的行星上的重量。

虽然 `Planet` 枚举很简单，但它的功能强大得惊人。这是一个短程序，它接收一个物体（任何单位）在地球上的重量，并打印该物体在八大行星上重量（相同单位）的表格：

```java
public class WeightTable {

    public static void main(String[] args) {

        double earthWeight = Double.parseDouble(args[0]);

        double mass = earthWeight / Planet.EARTH.surfaceGravity();

        for (Planet p : Planet.values()) {

            System.out.printf("Weight on %s is %f%n", p, p.surfaceWeight(mass));

        }

    }

}
```

注意，`Planet` 和所有枚举一样，有一个静态的 `values()` 方法，它返回按声明顺序排列的值的数组。注意，`toString()` 方法返回每个枚举的声明名称。如果你对这种表示方式不满意，可以通过重写 `toString()` 方法来更改它。以下是用命令行 185 运行我们的 `WeightTable`（未重写 `toString`）的结果：

```
Weight on MERCURY is 69.912739
Weight on VENUS is 167.43436
Weight on EARTH is 185.000000
Weight on MARS is 70.226739
Weight on JUPITER is 467.99066
Weight on SATURN is 197.12011
Weight on URANUS is 167.398264
Weight on NEPTUNE is 210.20875
```

直到 2006 年（在枚举添加到 Java 的两年后），王星还是一个行星。这引出了一个问题：“当你从枚举中删除一个元素时会发生什么？”答案是，当你从枚举中删除一个元素时，引用该元素的程序将继续工作。例如，我们的 `WeightTable` 程序将只少一行。而对于引用该元素的程序（在本例中为 `Planet`）呢？如果你重新编译，它将抛出一个有用的异常。这比你使用 `int` 模式所得到的行为要好得多。

`Planet` 枚举虽然简单，但它的功能强大得惊人。在 `Planet` 示例中展示的技巧对于大多数枚举类型都是足够的，但有时你需要更多。每个 `Planet` 常量都有不同的数据，但有时你需要为每个常量关联本质不同的行为。例如，假设你正在编写一个表示基础计算器运算的枚举类型，你想提供一个方法来执行每个常量所代表的算术运算。实现这一点的一种方法是对枚举的值进行 `switch`：

```
// 对自身值进行 switch 的枚举类型 - 值得怀疑
```

```java
public enum Operation {

    PLUS, MINUS, TIMES, DIVIDE;

    // 执行此常量所代表的算术运算

    public double apply(double x, double y) {

        switch(this) {

            case PLUS:   return x + y;

            case MINUS:  return x - y;

            case TIMES:  return x * y;

            case DIVIDE: return x / y;

        }

        throw new AssertionError("Unknown op: " + this);

    }

}
```

这段代码可以工作，但它并不漂亮。如果没有 `throw` 语句，它将无法编译，因为方法的末尾在技术上是可到达的，尽管永远不会被到达 [JLS, 14.21]。更糟糕的是，代码是脆弱的。如果你添加了一个新的枚举常量但忘记在 `switch` 中添加相应的 `case`，枚举仍然可以通过编译，但当你尝试应用新操作时，它会在运行时失败。

幸运的是，有一种更好的方法可以将每个枚举常量与不同的行为关联起来：在枚举类型中声明一个抽象的 `apply` 方法，并在每个常量的特定类体中用具体方法来重写它。此类方法被称为**常量特定方法实现**（constant-specific method implementations）：

```java
// 具有常量特定方法实现的枚举类型

public enum Operation {

  PLUS  {public double apply(double x, double y){return x + y;}},

  MINUS {public double apply(double x, double y){return x - y;}},

  TIMES {public double apply(double x, double y){return x * y;}},

  DIVIDE{public double apply(double x, double y){return x / y;}};

  public abstract double apply(double x, double y);

}
```

如果你在 `Operation` 的第二个版本中添加一个新常量，你不太可能忘记提供 `apply` 方法，因为该方法紧跟在每个声明之后。即使在极少数情况下你忘记了，编译器也会提醒你，因为枚举类型中的抽象方法必须在所有常量中用具体方法进行重写。

常量特定方法实现可以与常量特定数据结合。例如，这里的 `Operation` 版本重写了 `toString` 方法，以返回通常与操作相关联的符号：

```java
// 具有常量特定类体和数据的枚举类型

public enum Operation {

    PLUS("+") {

      public double apply(double x, double y) { return x + y; }

    },

    MINUS("-") {

      public double apply(double x, double y) { return x - y; }

    },

    TIMES("*") {

      public double apply(double x, double y) { return x * y; }

    },

    DIVIDE("/") {

      public double apply(double x, double y) { return x / y; }

    };

    private final String symbol;

    Operation(String symbol) { this.symbol = symbol; }

    @Override public String toString() { return symbol; }

    public abstract double apply(double x, double y);

}
```

所示的 `toString` 实现使得打印算术表达式变得简单，正如这个小程序所示：

```java
public static void main(String[] args) {

    double x = Double.parseDouble(args[0]);

    double y = Double.parseDouble(args[1]);

    for (Operation op : Operation.values())

        System.out.printf("%f %s %f = %f%n",

                          x, op, y, op.apply(x, y));

}
```

使用 2 和 4 作为命令行参数运行此程序将产生如下输出：

```
2.000000 + 4.000000 = 6.000000
2.000000 - 4.000000 = -2.000000
2.000000 * 4.000000 = 8.000000
2.000000 / 4.000000 = 0.500000
```

枚举类型具有一个自动生成的 `valueOf(String)` 方法，该方法将常量的名称转换为常量本身。如果你在枚举类型中重写了 `toString` 方法，考虑编写一个 `fromString` 方法将自定义的字符串表示转换回对应的枚举。以下代码（已对类型名称进行了适当更改）只要每个常量都具有唯一的字符串表示，就可以对任何枚举都有效：

```java
// 在枚举类型上实现 fromString 方法

private static final Map<String, Operation> stringToEnum =

    Stream.of(values()).collect(

        toMap(Object::toString, e -> e));

public static Optional<Operation> fromString(String symbol) {

    return Optional.ofNullable(stringToEnum.get(symbol));

}
```

你真正想要的是，在每次添加枚举常量时，都被迫选择一种加班费策略。幸运的是，有一种很好的方法可以实现这一点。该思路是将加班费计算移动到一个私有的嵌套枚举中，并将该策略枚举的实例传递给 `PayrollDay` 枚举的构造函数。然后 `PayrollDay` 枚举将加班费计算委托给策略枚举，从而消除了在 `PayrollDay` 中使用 `switch` 语句或特定常量方法实现的需求。虽然这种模式没有 `switch` 语句简洁，但它更安全、更灵活：

```
// 策略枚举模式
```

```java
enum PayrollDay {

    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY,

    SATURDAY(PayType.WEEKEND), SUNDAY(PayType.WEEKEND);

    private final PayType payType;

    PayrollDay(PayType payType) { this.payType = payType; }

    PayrollDay() { this(PayType.WEEKDAY); }  // 默认

    int pay(int minutesWorked, int payRate) {

        return payType.pay(minutesWorked, payRate);

    }

    // 策略枚举类型

    private enum PayType {

        WEEKDAY {

            int overtimePay(int minsWorked, int payRate) {

                return minsWorked <= MINS_PER_SHIFT ? 0 :

                    (minsWorked - MINS_PER_SHIFT) * payRate / 2;

            }

        },

        WEEKEND {

            int overtimePay(int minsWorked, int payRate) {

                return minsWorked * payRate / 2;

            }

        };

        abstract int overtimePay(int mins, int payRate);

        private static final int MINS_PER_SHIFT = 8 * 60;

        int pay(int minsWorked, int payRate) {

            int basePay = minsWorked * payRate;

            return basePay + overtimePay(minsWorked, payRate);

        }

    }

}
```



如果对枚举使用 `switch` 语句不是实现枚举特定常量行为的好选择，那么它们有什么用呢？**枚举上的 `switch` 语句适用于为枚举类型增强特定的常量行为。**例如，假设 `Operation` 枚举不受你的控制，而你希望它有一个实例方法来返回每个操作的逆操作。你可以通过以下静态方法模拟这种效果：

```java
// 对枚举使用 switch 来模拟缺失的方法
public static Operation inverse(Operation op) {
    switch(op) {
        case PLUS:   return Operation.MINUS;
        case MINUS:  return Operation.PLUS;
        case TIMES:  return Operation.DIVIDE;
        case DIVIDE: return Operation.TIMES;
        default:  throw new AssertionError("Unknown op: " + op);
    }
}
```

如果一个方法简单地不属于枚举，你也应该对你控制的枚举类型使用这种技术。该方法可能在某些情况下需要，但其重要性不足以将其包含在。总的来说，枚举的性能与 `int` 常量相当。枚举的一个微小缺点是加载和初始化枚举类型有空间和时间成本，但这种成本可能并察觉不到。

那么，你应该使用枚举吗？**当你需要一组成员在编译时已知的常量时，请随时使用枚举。**当然，这包括“自然枚举类型”，例如行星、星期几和象棋棋子。但它也包括其他你在编译时已知所有可能值的集合，例如菜单上的选项、操作代码和行标志。**枚举中的常量集没有必要保持固定。** 枚举特性的设计初衷就是为了允许二进制兼容的演进。

简而言之，枚举类型相对于 `int` 常量的优势是显而易见的。枚举更具可读性、安全且更强大。许多枚举不需要构造函数或成员，但其他枚举可以通过与每个常量关联数据并提供行为受这些数据影响的方法受益。较少枚举能从与单个方法关联多个行为中获益。在这些罕见的情况下，优先使用特定常量的方法，而不是对其值进行 `switch` 的枚举。如果某些（而非所有）枚举常量共享共同行为，请考虑策略枚举模式。

## 项目 35：使用实例字段代替序数（ordinal）

许多枚举自然地与单个 `int` 值关联。所有枚举都有一个 `ordinal()` 方法，它返回每个枚举常量在其类型中的数值位置。你可能会想从 `ordinal` 推派出一个 `int` 值：

```java
// 滥用 ordinal 派导出关联值 - 不要这样做
public enum Ensemble {
    SOLO, DUET, TRIO, QUARTET, QUINTET,
    SEXTET, SEPTET, OCTET, NONET, DECTET;

    public int numberOfMusicians() { return ordinal() + 1; }
}
```

虽然这个枚举可以工作，但它是一个维护的噩梦。如果常量被重新排序，`numberOfMusicians` 方法将会失效。如果你想添加一个已用过的 `int` 值的第二个枚举常量，你就没运气了。例如，添加一个代表“双四重奏”（double quartet）的常量可能很好，它和八重奏（octet）一样由八位音乐家组成，但没有方法可以做到。此外，在不添加所有中间 `int` 值的情况下，你无法为 `int` 值添加常量。例如，假设你想添加一个代表 12 位音乐家的三重奏（triple quartet）常量，这种做法很糟糕。在最理想的情况下，这种做法也很丑。如果有许多 `int` 值未未使用，这种表示法是不切实际的。对于未使用的 `int` 值（`11`）。

幸运的是，有一个解决这些问题的简单方法。**永远不要从序数派生与枚举关联的值；将其存储在实例字段中：**

```java
public enum Ensemble {
    SOLO(1), DUET(2), TRIO(3), QUARTET(4), QUINTET(5),
    SEXTET(6), SEPTET(7), OCTET(8), DOUBLE_QUARTET(8),
    NONET(9), DECTET(10), TRIPLE_QUARTET(12);

    private final int numberOfMusicians;

    Ensemble(int size) { this.numberOfMusicians = size; }

    public int numberOfMusicians() { return numberOfMusicians; }
}
```

`Enum` 规范对 `ordinal` 是这样说的：“大多数程序员对这个方法没有需求。它是为通用枚举数据结构（如 `EnumSet` 和 `EnumMap`）设计的。”除非你正在编写此类特征的代码，否则最好完全避免 `ordinal` 方法。

## 项目 36：使用 `EnumSet` 代替位域

如果枚举类型的元素主要用于集合，传统的做法是使用 `int` 枚举模式（项目 34），为每个常量分配不同的 2 的幂：

```java
// 位域枚举常量 - 已过时！
public class Text {
    public static final int STYLE_BOLD = 1 << 0;  // 1
    public static final int STYLE_ITALIC = 1 << 1;  // 2
    public static final int STYLE_UNDERLINE = 1 << 2;  // 4
    public static final int STYLE_STRIKETHROUGH = 1 << 3;  // 8

    // 参数是零或多个 STYLE_ 常量的位或结果
    public void applyStyles(int styles) { ... }
}
```

这种表示法允许你使用按位 `OR` 操作将多个常量组合成一个集合，即位域：

```java
text.applyStyles(STYLE_BOLD | STYLE_ITALIC);
```

位字段（bit field）表示允许你使用位运算高效地执行并集和交集等集合操作。但位字段具有 `int` 枚举常量的所有缺点，甚至更多。当位字段被用作数字打印时，它比一个简单的 `int` 枚举常量更难解释。目前没有简单的方法可以遍历位字段所表示的所有元素。最后，你必须在编写 API 时预测未来可能需要的最大比特数，并据此为位字段选择类型（通常是 `int` 或 `long`）。一旦选定了类型，在不更改 API 的情况下，你就无法超过它的宽度（32 或 64 位）。

一些倾向于使用枚举而非 `int` 常量的程序员，在需要传递一组常量时，仍然固执于使用位字段。这样做没有理由，因为存在一个更好的替代方案。`java.util` 包提供了 `EnumSet` 类，它用于高效地表示源自单个枚举类型的值的集合。该类实现了 `Set` 接口，提供了与任何其他 `Set` 实现相同的全部丰富功能、类型安全和可互操作性。但在内部，每个 `EnumSet` 都表示为一个位向量。如果底层的枚举类型有六十四个或更少的元素（大多数都是如此），整个 `EnumSet` 将由单个 `long` 表示，因此其性能与位字段相当。批量操作（如 `removeAll` 和 `retainAll`）是使用位运算实现的，就像你手动对位字段进行操作的那样。但你免受了手动位操作的丑陋和易错性的干扰：`EnumSet` 为你完成了这些繁琐的工作。

以下是上一个示例修改为使用枚举和枚举集代替位字段后的样子。它更短、更清晰且安全：

```java
// EnumSet - 位字段的现代替代方案
public class Text {
    public enum Style { BOLD, ITALIC, UNDERLINE, STRIKETHROUGH }

    // 可以传入任何 Set，但 EnumSet 显然是最好的
    public void applyStyles(Set<Style> styles) { ... }
}
```

以下是向 `applyStyles` 方法传递 `EnumSet` 实例的客户端代码。`EnumSet` 类提供了丰富的静态工厂方法以便于创建集合，其中一个在代码中得到了演示：

```java
text.applyStyles(EnumSet.of(Style.BOLD, Style.ITALIC));
```

注意，`applyStyles` 方法接收的是 `Set<Style>` 而不是 `EnumSet<Style>`。虽然所有客户端很可能都会向该方法传递 `EnumSet`，但接受接口类型而非实现类型通常是一个良好的做法（第 64 条）。这允许不寻常的客户端传入其他 `Set` 实现的可能性。

总而言之，**仅仅因为枚举类型将在集合中使用，就没有理由用位字段来表示它。** `EnumSet` 类结合了位字段的简洁性和性能以及第 34 条中描述的枚举类型的所有众多优点。`EnumSet` 唯一的真正的缺点是，截至 Java 9 为止，无法创建一个不可变的 `EnumSet`，但这可能会在即将推出的发行版本中得到解决。在此期间，你可以用 `Collections.unmodifiableSet` 封装 `EnumSet`，但简洁性和性能将会受到影响。

## 第 37 条：使用 `EnumMap` 代替序数索引

偶尔你可能会看到使用 `ordinal` 方法（第 35 条）来索引数组或列表的代码。例如，考虑这个表示植物的简单类：

```java
class Plant {
    enum LifeCycle { ANNUAL, PERENNIAL, BIENNIAL }

    final String name;
    final LifeCycle lifeCycle;

    Plant(String name, LifeCycle lifeCycle) {
        this.name = name;
        this.lifeCycle = lifeCycle;
    }

    @Override public String toString() {
        return name;
    }
}
```

现在假设你有一个代表花园的植物数组，并且你想按照生命周期（一年生、多年生或二年生）列出这些植物。为了做到这一点，你构建了三个集合，每个生命周期一个，并遍历花园，将每种植物放在相应的集合中。一些程序员会通过将集合放入一个由生命周期序数索引的数组来实现这样做：

```java
// 使用 ordinal() 索引数组 - 不要这么做！
Set<Plant>[] plantsByLifeCycle =
    (Set<Plant>[]) new Set[Plant.LifeCycle.values().length];
for (int i = 0; i < plantsByLifeCycle.length; i++)
    plantsByLifeCycle[i] = new HashSet<>();

for (Plant p : garden)
    plantsByLifeCycle[p.lifeCycle.ordinal()].add(p);

// 打印结果
for (int i = 0; i < plantsByLifeCycle.length; i++) {
    System.out.printf("%s: %s%n",
        Plant.LifeCycle.values()[i], plantsByLifeCycle[i]);
}
```

这种技术虽然有效，但充满了问题。由于数组与泛型不兼容（第 28 条），程序需要一个未经检查的转换并且无法顺利编译。因为数组不知道它的索引代表什么，你必须手动标记输出。但这种技术最严重的问题是，当你访问由枚举序数索引的数组时，使用正确的 `int` 值是你的责任；`int` 并不提供枚举那样的类型安全。如果你使用了错误的值，程序将静默地执行错误的操作，或者（如果你运气好的话）抛出 `ArrayIndexOutOfBoundsException`。

有一种得更好的方法来实现这种效果。数组实际上充当了从枚举到值的映射，因此你大可以使用 `Map`。更具体地说，有一种专为使用枚举键设计的、非常快速的 `Map` 实现，即 `java.util.EnumMap`。以下是程序重写为使用 `EnumMap` 后的样子：

```java
// 使用 EnumMap 将数据与枚举
Map<Plant.LifeCycle, Set<Plant>> plantsByLifeCycle =
    new EnumMap<>(Plant.LifeCycle.class);
for (Plant.LifeCycle lc : Plant.LifeCycle.values())
    plantsByLifeCycle.put(lc, new HashSet<>());
for (Plant p : garden)
    plantsByLifeCycle.get(p.lifeCycle).add(p);
System.out.println(plantsByLifeCycle);
```

这个程序更短、更清晰、更安全，并且速度与原始版本相当。没有不安全的转换；不需要手动标记输出，因为 map 的键是已知如何转换为可打印字符串的枚举；而且没有计算索引错误的可能性。`EnumMap` 速度与序数索引数组相当的原因是 `EnumMap` 在内部使用了这样的数组，但它向程序员隐藏了这一实现细节，结合了 `Map` 的丰富性、类型安全性。注意 `EnumMap` 的构造函数接收键类型的 `Class` 对象：这是一个*边界类型令牌*（bounded type token），它提供了运行时泛型信息（第 33 条）管理映射，之前的程序可以进一步简化。以下是很大程度上复制上一个示例行为的最简单流式代码：

```java
// 朴素的流式方法 - 不太可能产生 EnumMap!
System.out.println(Arrays.stream(garden)
    .collect(groupingBy(p -> p.lifeCycle)));
```

这段代码的问题在于它自己选择了 map 的实现，在实践中，它不会是一个 `EnumMap`，因此无法与显式使用 `EnumMap` 的版本具有相同的空间和时间性能。要解决这个问题，请使用 `Collectors.groupingBy` 的三参数形式，它允许调用者通过 `mapFactory` 参数指定 map 的实现：

```java
// 使用 stream 和 EnumMap 将数据与枚举值关联起来
System.out.println(Arrays.stream(garden)
    .collect(groupingBy(p -> p.lifeCycle,
        () -> new EnumMap<>(LifeCycle.class), toSet())));
```

这种优化对于像这里这样的简易程序来说是不值得的，但在大量使用 map 的程序中，它可能是至关重要的。

基于流的版本与 `EnumMap` 版本的行为略有不同。`EnumMap` 版本始终为每种植物生命周期创建一个嵌套 map，而基于流的版本版本仅在花园中包含一个或多个具有该生命周期的植物时才会创建一个嵌套 map。例如，如果花园中包含一年生和多年生植物但没有二年生，那么在 `EnumMap` 版本中 `plantsByLifeCycle` 的大小为三，而在两个基于流的版本中大小均为二。

你可能会看到一个通过序数（ordinal）（两次！）索引的数组数组，用于表示两个枚举值之间的映射。例如，此程序使用这样的数组将两个阶段映射到一个阶段转换（液态到固体是冷结，液态到气态是沸腾，以此此类推）：

```java
// 使用 ordinal() 索引数组数组 - 不要这样做！
public enum Phase {
    SOLID, LIQUID, GAS;

    public enum Transition {
        MELT, FREEZE, BOIL, CONDENSE, SUBLIME, DEPOSIT;

        // 行按从-序数索引，列按到-序数索引
        private static final Transition[][] TRANSITIONS = {
            { null,     MELT,     SUBLIME },
            { FREEZE,  null,      BOIL    },
            { DEPOSIT, CONDENSE, null    }
        };

        // 返回从一个阶段到另一个阶段的阶段转换
        public static Transition from(Phase from, Phase to) {
            return TRANSITIONS[from.ordinal()][to.ordinal()];
        }
    }
}
```



这个程序可以运行，甚至看起来很优雅，但表象具有欺骗性。就像之前看到的更简单的花园示例一样，编译器无法知道序数与数组索引之间的关系。如果你在转换表中犯错，或者在修改`Phase`或`Phase.Transition`枚举类型时忘记更新它，你的程序将在运行时失败。这种失败可能是`ArrayIndexOutOfBoundsException`、`NullPointerException`或者（更糟糕的）静默的错误行为。而且，表格的大小与阶段数量呈平方级增长，即使非空元素的数量较少，这种空间开销依然是平方倍的。

再次，你可以使用`EnumMap`做得更好。由于每个阶段转换都是通过一对枚举进行索引的，最好的方法是将这种关系表示为从一个枚举（“起始”阶段）到第二个枚举（“目标”阶段）再到结果（阶段转换）的 map。与阶段转换关联的两个阶段最好的捕捉方式是将它们与阶段转换枚举关联，然后用它初始化`EnumMap`：

点击此处查看代码图片

`// 使用嵌套的 EnumMap 将数据与枚举关联起来`

```java
public enum Phase {

    SOLID, LIQUID, GAS;

    public enum Transition {

        MELT(SOLID, LIQUID), FREEZE(LIQUID, SOLID),

        BOIL(LIQUID, GAS), CONDENSE(GAS, LIQUID),

        SUBLIME(SOLID, GAS), DEPOSIT(GAS, SOLID);

        private final Phase from;

        private final Phase to;

        Transition(Phase from, Phase to) {

            this.from = from;

            this.to = to;

        }

        // 初始化阶段转换 map

        private static final Map<Phase, Map<Phase, Transition>> m =

            Stream.of(values()).collect(groupingBy(t -> t.from,

                () -> new EnumMap<>(Phase.class),

                toMap(t -> t.to, t -> t, (x, y) -> y, () -> new EnumMap<>(Phase.class))));

        public static Transition from(Phase from, Phase to) {

            return m.get(from).get(to);

        }

    }

}
```

初始化阶段转换 map 的代码有点复杂。map 的类型是`Map<Phase, Map<Phase, Transition>>`，意味着“从（源）阶段到从（目标）阶段到转换的 map”。这个 map-of-maps 是使用两个收集器的级联序列初始化的。第一个收集器按源阶段对转换进行分组，第二个收集器创建一个从目标阶段到转换的`EnumMap`。第二个收集器中的合并函数`(x, y) -> y`未被使用；它之所以被要求是因为我们需要指定一个 map 工厂来获取`EnumMap`，而`Collectors`提供了嵌套式工厂（telescoping factories）。本书的上一个版本使用显式迭代来初始化阶段转换 map。代码更冗长，但可以说更容易理解。

现在假设你想系统中添加一个新的新阶段：`plasma`（等离子态）。与该阶段相关的两个转换是`ionization`（从气态到等离子态）和`deionization`（从等离子态到气态）。要更新基于数组的程序，你必须在`Phase`中添加一个新常量并在`Phase.Transition`中添加两个，并将原始九个元素的数组替换为十六个元素的版本。如果你在数组中添加的元素过多或过少，或者顺序错误，你就没救了：程序会编译，但在运行时会失败。要更新基于`EnumMap`的版本，你只需要在阶段列表中添加`PLASMA`，并在阶段转换列表中添加`IONIZE(GAS, PLASMA)`和`DEIONIZE(PLASMA, GAS)`：

点击此处查看代码图片

`// 使用嵌套 EnumMap 实现添加新阶段`

```java
public enum Phase {

    SOLID, LIQUID, GAS, PLASMA;

    public enum Transition {

        MELT(SOLID, LIQUID), FREEZE(LIQUID, SOLID),

        BOIL(LIQUID, GAS), CONDENSE(GAS, LIQUID),

        SUBLIME(SOLID, GAS), DEPOSIT(GAS, SOLID),

        IONIZE(GAS, PLASMA), DEIONIZE(PLASMA, GAS);

        ... // 保持不变

    }

}
```

程序处理了其他所有问题，几乎没有给你留下犯错的机会。在内部，map-of-maps 是用数组数组实现的，因此为了增加清晰度、安全性和可维护性，你付出的空间或时间成本很小。

为了简洁起见，上面的示例使用`null`来表示状态变化的缺失（即`to`和`from`相同的情况）。这不是良好的做法，并可能导致运行时出现`NullPointerException`。为这个问题设计一个简洁、优雅的解决方案出乎意料地困难，生成的程序足够长，会分散本项的主要内容。

总结来说，**很少应该使用序数来索引数组：请使用`EnumMap`。** 如果你要表示的关系是多维的，请使用`EnumMap<..., EnumMap<...>>`。这是通用原则的一个特例，即应用程序程序员很少应该、甚至永远不应该使用`Enum.ordinal`（第 35 项）。

在几乎所有方面，枚举类型（enum types）都优于本书第一版中描述的类型安全模式 [Bloch01]。表面上看，唯一的例外是可扩展性，这在原始模式下是可能的，但语言结构并不支持这一点。换句话说，使用该模式时，可以让一个枚举类型扩展另一个；而使用语言特性则无法做到。这并非巧合。在大多数情况下，枚举的可扩展性被证明是一个坏主意。扩展类型中的元素是基类型的实例，而反之则不然，这很令人困惑。目前没有好的方法可以列出基类型及其扩展的所有元素。最后，可扩展性会使设计和实现的许多方面变得复杂。

尽管如此，扩展枚举类型至少有一个引人注目的用例，即`operation codes`（操作码），也称为`opcodes`。操作码是一种枚举类型，其元素代表了对某些机器上的操作，例如 Item 34 中的`Operation`类型，它代表了简单计算器的功能。有时，让 API 的用户提供自己的操作是很有意义的，这实际上扩展了 API 提供的操作集。

幸运的是，有一种使用枚举类型实现这种效果的好方法。基本思想是利用枚举类型可以实现任意接口的特性，通过为操作码类型定义一个接口以及一个作为该接口标准实现的枚举。例如，这里是来自 Item 34 的`Operation`类型的扩展版本：

点击此处查看代码图片

```java
// 使用接口模拟可扩展枚举

public interface Operation {

    double apply(double x, double y);

}

public enum BasicOperation implements Operation {

    PLUS("+") {

        public double apply(double x, double y) { return x + y; }

    },

    MINUS("-") {

        public double apply(double x, double y) { return x - y; }

    },

    TIMES("*") {

        public double apply(double x, double y) { return x * y; }

    },

    DIVIDE("/") {

        public double apply(double x, double y) { return x / y; }

    };

    private final String symbol;

    BasicOperation(String symbol) {

        this.symbol = symbol;

    }

    @Override public String toString() {

        return symbol;

    }

}
```

虽然枚举类型（`BasicOperation`）不是可扩展的，但接口类型（`Operation`）是，而且 API 中使用的接口类型来表示操作。你可以定义另一个实现此接口的枚举类型，并用这种新类型的实例来代替基类型。例如，假设你想对之前显示的操作类型定义扩展，包含幂运算和取模运算。你只需要编写一个实现`Operation`接口的枚举类型即可：

点击此处查看代码图片

```java
// 模拟扩展枚举

public enum ExtendedOperation implements Operation {

    EXP("^") {

        public double apply(double x, double y) {

            return Math.pow(x, y);

        }

    },

    REMAINDER("%") {

        public double apply(double x, double y) {

            return x % y;

        }

    };

    private final String symbol;

    ExtendedOperation(String symbol) {

        this.symbol = symbol;

    }

    @Override public String toString() {

        return symbol;

    }

}
```

现在，你可以在任何可以使用基本操作的地方使用新操作，只要 API 编写时接收的是接口类型（`Operation`）而不是实现类（`BasicOperation`）。注意，你不需要在枚举中声明抽象的`apply`方法，就像你在不可扩展枚举中使用特定特定实例的方法实现的那样（第 162 页）。这是因为抽象方法（`apply`）是接口（`Operation`）的成员。

不仅可以在任何期望“基枚举”的地方传递“扩展枚举”的单个实例，还可以传递整个扩展枚举类型，并使用其元素来补充或代替基枚举的元素。例如，这里是第 163 页测试程序的版本，它执行了之前定义的所有扩展操作：

点击此处查看代码图片

```java
public static void main(String[] args) {

    double x = Double.parseDouble(args[0]);

    double y = Double.parseDouble(args[1]);

    test(ExtendedOperation.class, x, y);

}

private static <T extends Enum<T> & Operation> void test(Class<T> enumType, double x, double y) {

    for (T op : enumType.getEnumConstants()) {

        System.out.printf("%f %s = %f%n", x, op, op.apply(x, y));

    }

}
```

总而言之，虽然你无法编写可扩展的枚举类型，但可以通过编写一个接口，并配合一个实现了该接口的基础枚举类型来模拟它。这允许客户端编写实现该接口的自己的枚举（或其他类型）。假设 API 是基于接口编写的，那么这些类型的实例就可以在任何可以使用基础枚举类型实例的地方使用。

## 第 39 物品：优先使用注解而非命名模式

在历史上，使用命名模式来指示某些程序元素需要工具或框架进行特殊处理是一种常见做法。例如，在第 4 版本发布之前，JUnit 测试框架要求用户通过以`test`字符开头方法名来指定测试方法 [Beck04]。这种技术虽然有效，但它有几个很大的缺点。首先，拼写错误会导致静默失败。例如，假设你不小心地将一个测试方法命名为`tsetSafetyOverride`而不是`testSafetyOverride`。JUnit 3 不会报错，也不会执行该测试，从而导致虚假的安全感。

命名模式的第二个缺点是，没有办法确保它们只用在适当的程序元素上。例如，假设你将一个类命名为`TestSafetyMechanisms`，希望 JUnit 3 会自动测试它的所有方法，无论其名称如何。同样，JUnit 3 不会报错，也不会执行这些测试。

命名模式的第三个缺点是，它们没有提供良好的方法将参数值与程序元素关联起来。例如，假设你想支持一种测试，该测试仅在抛出特定异常时才成功。异常类型本质上是测试的一个参数。你可以使用某些复杂的命名模式将异常类型名称编码到测试方法名中，但这样做既难看又脆弱 (Item 62)。编译器无法检查那个本应命名异常的字符串是否真的命名的了异常。如果命名的类不存在或不是异常，你直到尝试运行测试时才能发现。

注解 [JLS, 9.7] 很好地解决了所有这些问题，JUnit 也从第 4 版本开始采用注解。在本物品中，我们将编写一个自己的玩具测试框架，以展示注解是如何工作作用的。假设你想定义一个注解类型，用于指定自动运行并在抛出异常时失败的简单测试。以下是这样一个名为`Test`的注解类型可能的外观：

点击此处查看代码图片

```java
// 标记注解类型声明

import java.lang.annotation.*;

/**

 * 表明被注解的方法是一个测试方法。

 * 仅可用于无参数的静态方法。

 */

@Retention(RetentionPolicy.RUNTIME)

@Target(ElementType.METHOD)

public @interface Test {

}
```

`Test`注解类型的声明本身被`Retention`和`Target`注解标记了。注解类型声明上的此类注解被称为元注解（meta-annotations）。`@Retention(RetentionPolicy.RUNTIME)`元注解表示`Test`注解应该在运行时保留。如果没有它，`Test`注解对测试工具来说是不可见的。`@Target(ElementType.METHOD)`元注解表示`Test`注解仅在方法声明上合法的：它不能应用于类声明、字段声明或其他程序元素。

`Test`注解声明之前的注释说，“仅可用于无参数的静态方法。”如果编译器能够强制这一点就太好了，但它不能，除非你编写一个注解处理器来实现它。关于此主题的更多信息，请参阅`javax.annotation.processing`的文档。在没有此类注解处理器的情况下，如果你将`Test`注解放在实例方法的声明上或带有一个或多个参数的方法上，测试程序仍将编译，交给测试工具在运行时处理该问题。

以下是`Test`注解在实践中的样子。它被称为标记注解，因为它没有参数，仅仅是“标记”被注解的元素。如果程序员拼错了`Test`，或者将`Test`注解应用于方法声明之外的程序元素，程序将无法编译：

点击此处查看代码图片

```java
// 包含标记注解的程序

public class Sample {

    @Test public static void m1() { }  // Test 应该通过

    public static void m2() { }

    @Test public static void m3() {     // Test 应该失败

        throw new RuntimeException("Boom");

    }

    public static void m4() { }

    @Test public void m5() { } // 无效用法：非静态方法

    public static void m6() { }

    @Test public static void m7() {     // Test 应该失败

        throw new RuntimeException("Crash");

    }

    public static void m8() { }

}
```

`Sample`类有七个方法，其中四个标记了注解。其中两个（`m3`和`m7`）抛出了异常，另外两个（`m1`和`m5`）没有。被注解的方法中有一个没有抛出异常的`m5`是实例方法，所以它不是有效的用法。`Test`注解对`Sample`类没有直接影响。它们仅供程序使用。通常，注解不会改变被注解代码的语义，但允许对其进行像如下的特殊处理：

```java
// 处理注解的程序

import java.lang.reflect.*;

public class RunTests {

    public static void main(String[] args) throws Exception {

        int tests = 0;

        int passed = 0;
```



`Class<?> testClass = Class.forName(args[0]);`

```
for (Method m : testClass.getDeclaredMethods()) {
    if (m.isAnnotationPresent(Test.class)) {
        tests++;
        try {
            m.invoke(null);
            passed++;
        } catch (InvocationTargetException wrappedExc) {
            Throwable exc = wrappedExc.getCause();
            System.out.println(m + " failed: " + exc);
        } catch (Exception exc) {
            System.out.println("Invalid @Test: " + m);
        }
    }
}
System.out.printf("Passed: %d, Failed: %d%n", passed, tests - passed);
```

测试运行工具从命令行接收一个全限定类名，并通过反射调用`Method.invoke`运行类中所有类的`Test`方法。`isAnnotationPresent`方法告诉工具运行哪些方法。如果测试方法抛出异常，反射机制将其封装在`InvocationTargetException`中。工具捕获该异常并打印包含测试方法抛出的原始异常的失败报告，该异常是通过`getCause`方法从`InvocationTargetException`中提取的。

如果通过反射调用测试方法抛出了`InvocationTargetException`外的任何异常，则表明`Test`注解用法在编译时未捕获。此类用法包括注解实例方法、带有一个或多个参数的方法或不可访问的方法。测试运行器中的第二个`catch`块捕获这些`Test`用法错误并打印相应的错误信息。当在`Sample`上运行`RunTests`时，打印的输出如下：

```
public static void Sample.m3() failed: RuntimeException: Boom
Invalid @Test: public void Sample.m5()
public static void Sample.m7() failed: RuntimeException: Crash
```

通过: 1, 失败: 3

现在，让我们为那些仅在抛出特定异常时才通过的测试添加支持。我们需要一个新的注解类型来实现：

```java
import java.lang.annotation.*;

/**
 * 表示被注解的方法是一个测试方法，
 * 该方法必须抛出指定的异常才能通过。
 */
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface ExceptionTest {
    Class<? extends Throwable> value();
}
```

该注解的参数类型为`Class<? extends Throwable>`。坦诚然，这个通配符类型读起来很绕口。在英语中，它的意思是“某个继承`Throwable`的类的`Class`对象”，它允许注解的使用者指定任何异常（或错误）类型。这种用法是*边界类型令牌*（Item 33）的一个示例。以下是该注解在实践中的样子。注意使用类字面量作为注解参数的值：

```java
public class Sample2 {
    @ExceptionTest(ArithmeticException.class)
    public static void m1() {  // 测试应该通过
        int i = 0;
        i = i / i;
    }

    @ExceptionTest(ArithmeticException.class)
    public static void m2() {  // 应该失败（异常错误）
        int[] a = new int[0];
        int i = a[1];
    }

    @ExceptionTest(ArithmeticException.class)
    public static void m3() { }  // 应该失败（无异常）
}
```

现在，让我们修改测试运行器工具以处理新的注解。这样做包括在`main`方法中添加以下代码：

```java
if (m.isAnnotationPresent(ExceptionTest.class)) {
    tests++;
    try {
        m.invoke(null);
        System.out.printf("Test %s failed: no exception%n", m);
    } catch (InvocationTargetException wrappedEx) {
        Throwable exc = wrappedEx.getCause();
        Class<? extends Throwable> excType =
            m.getAnnotation(ExceptionTest.class).value();
        if (excType.isInstance(exc)) {
            passed++;
        } else {
            System.out.printf(
                "Test %s failed: expected %s, got %s%n",
                m, excType.getName(), exc);
        }
    } catch (Exception exc) {
        System.out.println("Invalid @Test: " + m);
    }
}
```

这段代码与我们用于处理`Test`注解的代码相似，唯一的区别在于：这段代码提取了注解参数的值，并用它来检查测试抛出的异常是否为正确的类型。这里没有显式的强制转换，因此没有`ClassCastException`的危险。测试程序通过编译这一事实保证了其注解参数代表有效的异常类型，但有一个例外：如果注解参数在编译时是有效的，但表示指定异常的类文件在运行时不存在，则测试运行器将抛出`TypeNotPresent`。

将我们的异常测试更进一步，可以设想一种测试在抛出几个异常中的任意一个时就能通过。注解机制有一项功能可以轻松支持这种特性。假设我们将`ExceptionTest`注解的参数类型更改为`Class`对象数组：

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface ExceptionTest {
    Class<? extends Exception>[] value();
}
```

注解中数组参数的语法是灵活的。它针对单元素数组进行了优化。之前所有的`ExceptionTest`注解在数组参数版本的`ExceptionTest`中仍然有效，并且结果为单元素数组。要指定多元素数组，用花括号括起元素并用逗号分隔：

```java
@ExceptionTest({IndexOutOfBoundsException.class, NullPointerException.class})
public static void doublyBad() {
    List<String> list = new ArrayList<>();
    // 这允许此方法抛出 
    // IndexOutOfBoundsException 或 NullPointerException
    list.addAll(null);
}
```

修改测试运行器工具以处理`ExceptionTest`的新版本是非常直接的。这段代码替换了原始代码：

```java
if (m.isAnnotationPresent(ExceptionTest.class)) {
    tests++;
    try {
        m.invoke(null);
        System.out.printf("Test %s failed: no exception%n", m);
    } catch (Throwable wrappedEx) {
        Throwable exc = wrappedEx.getCause();
        int oldPassed = passed;
        Class<? extends Exception>[] excTypes =
            m.getAnnotation(ExceptionTest.class).value();
        for (Class<? extends Exception> excType : excTypes) {
            if (excType.isInstance(exc)) {
                passed++;
                break;
            }
        }
        if (passed == oldPassed) {
            System.out.printf("Test %s failed: %s %n", m, exc);
        }
    }
}
```

从 Java 8 开始，有多值值的另一种方法。与其声明带有数组参数的注解，你可以在注解声明上使用`@Repeatable`元注解，以指示该注解可以重复地应用于单个元素。该元注解接受单个参数，该参数是*容器注解类型*的类对象，其唯一的参数是该注解类型的数组 [JLS, 9.6.3]。如果我们在`ExceptionTest`注解中采用这种方法，注解声明如下。注意，容器注解类型必须标记适当的策略和目标，否则声明将无法编译：

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
@Repeatable(ExceptionTestContainer.class)
public @interface ExceptionTest {
    Class<? extends Exception> value();
}

@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface ExceptionTestContainer {
    ExceptionTest[] value();
}
```

当使用重复注解代替数组值注解时，我们的`doublyBad`测试看起来如下：

```java
@ExceptionTest(IndexOutOfBoundsException.class)
@ExceptionTest(NullPointerException.class)
public static void doublyBad() { ... }
```

处理可重复注解（repeatable annotations）需要格外小心。重复注解会生成一个包含它的注解类型的合成注解。`getAnnotationsByType`方法忽略了这一事实，可以用于访问可重复注解类型的重复和非重复注解。但`isAnnotationPresent`显式地指出，重复注解并不属于该注解类型，而是属于包含它的注解类型。如果一个元素具有某种类型的重复注解，而你使用`isAnnotationPresent`方法来检查该元素是否具有该类型的注解，你会发现它并没有。因此，使用此方法检查注解类型的存在会导致你的程序静默地忽略重复注解。同样，使用此方法检查包含它的注解类型会导致程序静默地忽略非重复注解。要使用`isAnnotationPresent`检测重复和非重复注解，你必须同时检查该注解类型及其包含它的注解类型（containing annotation type）。以下是我们的`RunTests`程序中相关部分在修改为使用可重复的`ExceptionTest`注解后的样子：

```java
// Processing repeatable annotations
if (m.isAnnotationPresent(ExceptionTest.class)
    || m.isAnnotationPresent(ExceptionTestContainer.class)) {
    tests++;
    try {
        m.invoke(null);
        System.out.printf("Test %s failed: no exception%n", m);
    } catch (Throwable wrappedExc) {
        Throwable exc = wrappedExc.getCause();
        int oldPassed = passed;
        ExceptionTest[] excTests =
                m.getAnnotationsByType(ExceptionTest.class);
        for (ExceptionTest excTest : excTests) {
            if (excTest.value().isInstance(exc)) {
                passed++;
                break;
            }
        }
        if (passed == oldPassed)
            System.out.printf("Test %s failed: %s %n", m, exc);
    }
}
```

引入重复注解是为了提高逻辑上给给定程序元素应用多个相同类型注解源码的可读性。如果你觉得它们增强了源代码的可读性，请使用它们，但记住，声明和处理重复注解需要更多的样板代码，而且处理重复注解是容易出错的。

本项中的测试框架只是一个玩具，但它清楚地展示了注解相对于命名模式的优越性，而且这仅仅触及了使用注解的皮毛。如果你编写一个需要程序员在源码中添加信息的工具，请定义合适的注解类型。**既然可以使用注解，完全没有理由使用命名模式。**

尽管如此，除了工具开发者，大多数程序员不需要定义注解类型。但**所有程序员都应该使用 Java 提供的预定义注解类型**（项目 40、27）。此外，考虑使用 IDE 或静态分析工具提供的注解。此类注解可以提高这些工具提供的诊断信息的质量。但请注意，这些注解尚未标准化，因此如果你切换工具或出现新标准，你可能需要做一些工作。

### 项目 40：一致地使用`Override`注解

Java 库包含了几种注解类型。对于典型的程序员来说，其中最重要的是`@Override`。此注解只能用于方法声明，它表示被注解的方法声明覆盖了父类中的某个声明。如果你一致地使用此注解，它将保护你免受很大一类恶性 bug。考虑这个程序，其中`Bigram`类表示一个*二元组*（bigram），即字母的有序对：

```java
// Can you spot the bug?
public class Bigram {
    private final char first;
    private final char second;

    public Bigram(char first, char second) {
        this.first = first;
        this.second = second;
    }

    public boolean equals(Bigram b) {
        return first == b.first && second == b.second;
    }

    public int hashCode() {
        return 31 * first + second;
    }

    public static void main(String[] args) {
        Set<Bigram> s = new HashSet<>();
        for (char ch = 'a'; ch <= 'z'; ch++) {
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`。

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```

---

```java
// Can you spot the bug?

public class Bigram {

    private final char first;

    private final char second;

    public Bigram(char first, char second) {

        this.first = first;

        this.second = second;

    }

    public boolean equals(Bigram b) {

        return first == b.first && second == b.second;

    }

    public int hashCode() {

        return 31 * first + second;

    }

    public static void main(String[] args) {

        Set<Bigram> s = new HashSet<>();

        for (char ch = 'a'; ch <= 'z'; ch++) {

            s.add(new Bigram(ch, ch));

        }

        System.out.println(s.size());

    }

}
```

显然，`Bigram`的作者想要覆盖`equals`，但参数不是`Object`，因此`Bigram`继承了`Object`的`equals`方法。这解释了为什么程序输出了260。幸运的是，编译器可以帮你发现这个问题，但前提是你通过告诉它你意图覆盖`Object`来帮助它。这样做只需为`Bigram.equals`加上`@Override`，如下所示：

```java
@Override public boolean equals(Bigram b) {

    return first == b.first && second == b.second;

}
```

插入此注解并尝试重新编译，编译器将生成类似下面的错误信息：

```
Bigram.java:10: method does not override or implement a method

from a supertype

    @Override public boolean equals(Bigram b) {

                               ^
```

你会立即意识到自己哪里错了，拍一下自己的脑门，并用正确的实现替换错误的`equals`实现（项目 10）：

```java
@Override public boolean equals(Object o) {

    if (!(o instanceof Bigram)) {

        return false;

    }

    Bigram b = (Bigram) o;

    return b.first == first && second == b.second;

}
```

大多数 IDE 都提供了另一个一致使用`Override`注解的理由。如果你启用了相应的检查，当你的某个方法没有使用`Override`注解但重写了父类方法时，IDE 将生成一个警告。如果你一致地使用`Override`注解，这些警告将提醒你注意无意中的重写。它们与编译器的错误信息形成互补——后者会提醒你注意无意中未能重写的情况。通过 IDE 和编译器，你可以确保自己在任何想要重写的地方都重写了方法，而在其他地方没有重写。

`Override`注解可以用于重写接口定义方法的声明，也可以用于重写类方法的声明。随着默认方法（default methods）的出现，在接口方法的具体实现上使用`Override`是一种良好的做法，可以确保方法签名是正确的。如果你知道某个接口没有默认方法，你可以选择省略接口方法具体实现上的`Override`注解，以减少冗余。

然而，在抽象类或接口中，对于你认为重写了父类或父接口方法的*所有*方法（无论是具体的还是抽象的），添加注解都是*值得的*。例如，`Set`接口没有向`Collection`接口添加新方法，因此它应该在其所有方法声明上包含`Override`注解，以确保它不会无意向`Collection`接口添加任何新方法。

总之，如果你在每一个认为重写了父类型声明的方法上都使用`Override`注解，编译器可以保护你免受许多错误，但有一个例外：在具体类中，你不需要对认为重写了抽象方法声明的方法添加注解（尽管这样做没有害）。

### 事项 41：使用标记接口定义类型

*标记接口*（marker interface）是一个不包含任何方法定义的接口，它仅仅用于指定（或“标记”）实现该接口的类具有某种属性。例如，考虑`Serializable`接口（第 12 章）。通过实现此接口，类表示其实例可以被写入`ObjectOutputStream`（或称被“序列化”）。

你可能会听人说，标记注解（事项 39）使标记接口过时了。这种断言是不正确的。与标记注解相比，标记接口有两个优势。首先最重要的是，`标记接口定义了一个由被标记类的实例实现的类型；而标记注解则不是。`标记接口类型的存在允许你在编译时捕捉错误，而如果你使用标记注解，只有在运行时才能捕捉到这些错误。

Java 的序列化机制（第 6 章）使用`Serializable`标记接口来指示一个类型是可序列化的。`ObjectOutputStream.writeObject`方法用于序列化传递给它的对象，它要求参数是可序列化的。如果该方法的参数类型是`Serializable`，那么尝试序列化一个不适当的对象将在编译时被检测（通过类型检查）。编译时错误检测是标记接口的意图，遗憾的是，`ObjectOutputStream.write` API 并没有利用`Serializable`接口：它的参数被声明为`Object`类型，因此尝试序列化不可序列化的对象将直到运行时才会失败。

**标记接口相对于标记注解的另一个优势是，它们可以更精确地目标化。** 如果一个注解类型的目标声明为`ElementType.TYPE`，则它可以应用于*任何*类或接口。假设你有一个仅适用于特定接口实现的标记。如果你将其定义为标记接口，你可以让它扩展其所适用的唯一接口，从而保证所有标记类型也是该受用唯一接口的子类型。

可以认为，`Set`接口恰恰就是这样一个*受限标记接口*。它仅适用于`Collection`子类，但它没有添加除`Collection`定义之外的方法。它通常不被视为标记接口，因为它精炼了几个`Collection`方法的契约，包括`add`、`equals`和`hashCode`。很容易想象一种标记接口，它仅适用于某些特定接口的子类，并且*没有*精炼该接口的任何方法的契约。这种标记接口可能描述整个对象的某些不变性，或者指示实例有条件被某个其他类的方法处理（就像`Serializable`接口指示实例有条件被`ObjectOutputStream`处理一样）。

**标记注解相对于标记接口的主要优势是，它们是更大注解机制的一部分。** 因此，标记注解允许基于注解的框架保持一致性。

那么，你什么时候应该使用标记注解，什么时候应该使用标记接口呢？显然，如果标记适用于类或接口以外的任何程序元素，你必须使用注解，因为只有类和接口可以被要求实现或扩展接口。如果标记仅适用于类和接口，问自己：“我是否可能想写一个或多个只接受带有此标记的对象的方法？”如果是，你应该倾向于使用标记接口而不是注解。这将使你能够将该接口作为相关方法的参数类型，从而获得编译时类型检查的益处。如果你能说服自己永远不想写一个只接受带标记对象的方法，那么你可能使用标记注解更好。此外，如果该标记是某个大量使用注解的框架的一部分，那么标记注解是明显的选择。

总而言之，标记接口和标记注解都有其用处。如果你想定义一个不与任何新方法相关的类型，标记接口是不之选。如果你想标记类和接口以外的程序元素，或者将标记放入一个已经大量使用注解的框架中，那么标记注解是正确的选择。**如果你发现自己在编写一个目标为** `ElementType.TYPE` 的标记注解类型，请花时间确定它是否真的应该是注解，或者标记接口是否更合适。

## 第 7 章.Lambda 与流（Streams）

Java 8 引入了函数式接口、Lambda 和方法引用，使得创建函数对象变得容易。流 API 也随这些语言变化引入，为处理元素序列提供了库支持。在本章中，我们将讨论如何充分利用这些设施。

### 事项 42：优先使用 Lambda 而非匿名类

历史上，具有单个抽象方法的接口（或罕见的抽象类）被用作*函数类型*。它们的实例被称为*函数对象*，代表函数或动作。自 JDK 1.1 于 1997 发布以来，创建函数对象的主要手段是匿名类（事项 24）。这里有一个按长度排序字符串列表的代码片段，使用匿名类来创建排序的比较函数（该函数施加了排序顺序）：

```java
// 作为函数对象的匿名类实例 - 已过时！

Collections.sort(words, new Comparator<String>() {

    public int compare(String s1, String s2) {

        return Integer.compare(s1.length(), s2.length());

    }

});
```

对于需要函数对象的经典面向对象设计模式，匿名类已经足够用了，特别是`Strategy`模式 [Gamma95]。`Comparator`接口代表了排序的`抽象策略`；而上面的匿名类则是字符串排序的`具体策略`。然而，匿名类的繁琐使得 Java 的函数式编程成为了一项不具吸引力的前景。

在 Java 8 中，语言正式化了这样一个概念：即具有单个抽象方法的接口是特殊的，值得特殊对待。这些接口现在被称为`函数式接口`（functional interfaces），语言允许你使用`lambda 表达式`（简称为 `lambdas`）创建这些接口的实例。Lambdas 的功能与匿名类相似，但简洁得多。以下是用 lambda 替换匿名类后，上述代码片段的样子。样板代码消失了，行为也清晰易见：

```java
// 作为函数对象的 Lambda 表达式（替换匿名类）

Collections.sort(words,

    (s1, s2) -> Integer.compare(s1.length(), s2.length()));
```

注意，lambda 的类型（`Comparator<String>`）、其参数类型（`s1` 和 `s2`，均为 `String`）以及返回值（`int`）都没有出现在代码中。编译器根据上下文推断这些类型，这个过程被称为`类型推断`（type inference）。在某些情况下，编译器将无法确定类型，此时你就必须指定它们。类型推断的规则非常复杂：它们占据了 Java 规范（JLS）中的整个章节 [JLS, 18]。很少有程序员详细了解这些规则，但没关系。**除非所有 lambda 参数的类型会让你的程序更清晰，否则省略这些类型。** 如果编译器生成的错误提示它无法推断 lambda 参数的类型，那么请指定它。有时你可能需要对返回值或整个 lambda 表达式进行强制转换，但这种情况很少见。

关于类型推断还应补充一点注意事项。项目 26 建议不要使用原始类型（raw types），项目 29 建议优先使用泛型，项目 30 建议优先使用泛型方法。在使用 lambdas 时，这些建议格外重要，因为编译器通过泛型获取大部分允许执行类型推断的类型信息。如果你不提供这些信息，编译器将无法进行类型推断，你就必须在 lambda 中手动指定类型，这将大大增加它们的冗余性。例如，如果变量`words`声明为原始类型`List`而不是泛型类型`List<String>`，上面的代码片段将无法编译。

顺便提一下，如果使用`比较器构造方法`代替 lambda，片段中的比较器可以变得更加简洁（项目 14. 43）：

```java
Collections.sort(words, comparingInt(String::length));
```

事实上，利用 Java 8 添加到`List`接口的`sort`方法，该片段可以写得更短：

```java
words.sort(comparingInt(String::length));
```

lambda 在语言中的引入，使得在以前没有意义的地方使用函数对象变得切实可行。例如，考虑 项目 34 中的`Operation`枚举类型（enum）。由于每个枚举对其`apply`方法有不同的行为，我们使用了常量特定的类体，并在每个枚举常量中重写了`apply`方法。为了唤起记忆，这里是代码：

```java
// 带有常量特定类体和数据的枚举类型 (项目 34)

public enum Operation {

    PLUS("+") {

        public double apply(double x, double y) { return x + y; }

    },

    MINUS("-") {

        public double apply(double x, double y) { return x - y; }

    },

    TIMES("*") {

        public double apply(double x, double y) { return x * y; }

    },

    DIVIDE("/") {

        public double apply(double x, double y) { return x / y; }

    }

}
```

项目 34 说，枚举实例字段优于常量特定的类体。Lambdas 使得使用前者来实现常量特定的行为变得简单。构造函数将 lambda 在实例中，`apply`方法将调用转发给 lambda。生成的代码比原始版本更简单清晰：

```java
// 带有函数字段和常量特定行为的枚举

public enum Operation {

    PLUS("+", (x, y) -> x + y),

    MINUS("-", (x, y) -> x - y),

    TIMES("*", (x, y) -> x + y),

    DIVIDE("/", (x, y) -> x / y);

    private final String symbol;

    private final DoubleBinaryOperator op;

    Operation(String symbol, DoubleBinaryOperator op) {

        this.symbol = symbol;

        this.op = op;

    }

    @Override

    public String toString() {

        return symbol;

    }

    public double apply(double x, double y) {

        return op.applyAsDouble(x, y);

    }

}
```



注意，我们使用`DoubleBinaryOperator`接口作为表示枚举常量行为的 lambda。这是`java.util.function`中许多预定义函数式接口之一（项目 44）。它代表一个接受两个`double`参数并返回`double`结果的函数。

看着基于 lambda 的`Operation`枚举，你可能会认为常量特定的方法体已经过时了，但并非如此。与方法和类不同，lambdas 缺乏名称和文档；如果计算不是自自明的，或者超过了数行，就不要把它放在 lambda 中。lambda 的理想长度是单行，三行是一个合理的上限。如果你违反了这一规则，会对你的程序可读性造成严重损害。如果一个 lambda 很长或难以阅读，要么找到方法简化它，要么重构你的程序以消除它。此外，传递给枚举构造函数的参数是在静态文中求值的。因此，枚举构造函数中的 lambda 无法访问枚举的实例成员。如果枚举类型具有难以理解、无法在几行内实现或需要访问实例字段或方法的常量特定行为，那么常量特定的类体仍然是最佳选择。

同样地，你可能认为在 lambda 时代匿名类已经过时了。这种说法虽然接近事实，但有些事情你可以用匿名类完成，而 lambda 无法做到的。lambda 局限于函数式接口。如果你想创建一个抽象类的实例，可以使用匿名类来实现，但不能使用 lambda。同样，你也可以使用匿名类来创建具有多个抽象方法的接口的实例。最后，lambda 无法获取其自身的引用。在 lambda 中，`this`关键字指向外围的实例，这通常正是你想要的。在匿名类中，`this`关键字指向该匿名类的实例。如果你需要在函数体内部访问该函数对象本身，那么你必须使用匿名类。

lambda 与匿名类有一个共同点，即你无法在不同的实现之间可靠地对其序列化和反序列化。因此，你应该很少（甚至不要）序列化 lambda（或匿名类实例）。如果你有一个想要序列化的函数对象（例如`Comparator`），请使用私有静态嵌套类的实例（Item 24）。

总结来说，截至 Java 8， lambda 仍然是表示小函数对象最好的方式。除非你必须创建非函数式接口类型的实例，否则不要对函数对象使用匿名类。此外，请记住，lambda 让表示小函数对象变得如此简单，这为以前在 Java 中并不行的函数式编程技术开启了大门。

### Item 43：优先使用方法引用代替 lambda

lambda 优于匿名类的主要优势在于它们更简洁。Java 提供了一种比 lambda 更简洁的生成函数对象的方法：*方法引用*（method references）。这里来自一个程序的代码片段，该程序维护一个从任意键到`Integer`值的 map。如果该值被解释为键的实例计数，那么该程序就是一个多集实现。该代码段的功能是：如果键不在 map 中，则将数字 1 与键关联；如果键已存在，则增加其关联的值：

```
map.merge(key, 1, (count, incr) -> count + incr);
```

注意，这段代码使用了`merge`方法，该方法是 Java 8 添加到`Map`接口的。如果给定的键没有映射，该方法将简单地插入给定的值；如果映射已经存在，`merge`会将给定的函数应用于当前值和给定值，并用结果覆盖当前值。这段代码代表了`merge`方法的一个典型用例。

代码读起来很自然，但仍然存在样板代码。参数`count`和`incr`没有增加太大价值，并且占据了相当空间。实际上，lambda 告诉你的仅仅是函数返回了两个参数之和。从 Java 8 开始，`Integer`（以及所有其他包装数值原始类型）提供了一个静态方法`sum`，其功能完全相同。我们可以简单地传递该方法的引用，从而在减少视觉杂乱的情况下获得相同的结果：

```
map.merge(key, 1, Integer::sum);
```

方法的参数越多，你通过方法引用消除的样板代码就越多。然而，在某些 lambda 中，你选择的参数名称提供了有用的文档，使得 lambda 比方法引用更具可读性和可维护性，即使 lambda 较长。

方法引用无法做的事情，lambda 同样也能做到（除了一个晦涩的例外——如果你感兴趣，请参阅 JLS 9.9-2）。尽管如此，方法引用通常会产生更短、更清晰的代码。它们还为 lambda 变得过长或过于复杂提供了退路：你可以将 lambda 中的代码提取到一个新方法中，并用对该方法的引用替换 lambda。你可以给该方法起一个好名字，并尽情地为其编写文档。

如果你使用 IDE 编程，它会在可能的地方提供将 lambda 替换为方法引建议。你应该（但不是总是）接受 IDE 的建议。偶尔，lambda 会比方法引用更简洁。这种情况通常发生在方法与 lambda 位于同一个类时。例如，考虑以下片段，假设它出现在名为`GoshThisClassNameIsHumongous`的类中：

```
service.execute(GoshThisClassNameIsHumongous::action);
```

lambda 的等价形式如下：

```
service.execute(() -> action());
```

使用方法引用的片段并不比使用 lambda 的片段更短或更清晰，因此请选择后者。类似的，`Function`接口提供了一个泛型静态工厂方法来返回恒等函数`Function.identity()`。通常情况下，*不*使用该方法而是直接内联编写等价的 lambda`x -> x`会更短更简洁。

许多方法引用指向静态方法，但有四种引用不是。其中两种是*绑定的*（bound）和*未绑定的*（unbound）实例方法引用。在绑定引用中，接收对象在方法引用中指定。绑定引用的性质与静态引用相似：函数对象获取的参数与所引方法的参数相同。在未绑定引用中，接收对象在应用函数对象时指定，通过方法前的额外参数来完成。未绑定引用通常用作流式流水线中的映射和过滤函数（Item 45）。最后，有两种类的*构造器*引用，用于类和数组。构造器引用作为工厂对象。所有五种方法引用总结在下表：

| 方法引用类型 | 示例 | Lambda 等价形式 |
| :--- | :--- | :--- |
| 静态 | `Integer::parseInt` | `str -> Integer.parseInt(str)` |
| 绑定 | `Instant.now()::isAfter` | `Instant then = Instant.now(); t -> then.isAfter(t)` |
| 未绑定 | `String::toLowerCase` | `str -> str.toLowerCase()` |
| 类构造器 | `TreeMap<K,V>::new` | `() -> new TreeMap<K,V>` |
| 数组构造器 | `int[]::new` | `len -> new int[len]` |

总结，方法引用通常提供了比 lambda 更简洁的替代方案。在方法引用更短更清晰的地方，使用它们；如果不是，就坚持使用 lambda。

### Item 44：优先使用标准函数式接口

既然 Java 有了 lambda，编写 API 的最佳实践发生了巨大变化。例如，*模板方法*模式 [Gamma95]（子类通过重写*原始方法*来特化父类的行为）变得不再那么吸引人。现代的替代方案是提供一个接受函数对象的静态工厂或构造函数以来实现相同的效果。更广泛地说，你将编写更多接受函数对象作为参数的构造函数和方法。选择正确的函数参数类型需要仔细。

考虑`LinkedHashMap`。你可以通过重写其`removeEldestEntry`方法将该类作为缓存，该方法在每次向 map 添加新键时由`put`调用。当该方法返回`true`时，map 就会移除其最旧的条目，该条目会被传递给该方法。以下重写允许 map 增长到一百个条目，然后在每次添加新键时删除最旧的条目，保持最近的百个条目：

```java
protected boolean removeEldestEntry(Map.Entry<K,V> eldest) {
  return size() > 100;
}
```

这种技术可以运行，但使用 lambda 可以让你获得更好的效果。如果`LinkedHashMap`是在今天编写的，它会有一个接收函数对象的静态静态工厂方法或构造函数。观察`removeEldestEntry`的声明，你可能会认为函数对象应该接收一个`Map.Entry<K,V>`并返回一个`boolean`，但这并不能解决问题：`removeEldestEntry`方法调用`size()`来获取 map 中条目的数量，这之所以能行得通是因为`removeEldestEntry`是 map 的一个实例方法。你传递给构造函数的函数对象不是 map 的实例方法，而且无法捕获它，因为在调用工厂方法或构造函数时 map 尚未存在。因此，map 必须将自身传递给函数对象，因此该函数对象必须将 map 及其最旧条目作为输入。如果你声明这样一个函数式接口，它看起来像这样：

```java
// 不必要的函数式接口；请改用标准的接口。
@FunctionalInterface interface EldestEntryRemovalFunction<K,V>{
    boolean remove(Map<K,V> map, Map.Entry<K,V> eldest);
}
```



这个接口可以正常工作，但你不应该使用它，因为你不需要为此目的声明一个新接口。`java.util.function` 包提供了大量的标准函数式接口集合供你使用。如果其中一个标准函数式接口可以胜任，你通常应该优先使用它，而不是专门定制的函数式接口。这通过减少 API 的概念表面积，使你的 API 更易于学习，并提供显著的互操作性优势，因为许多标准函数式接口提供了实用的默认方法。例如，`Predicate` 接口提供了组合谓词的方法。在我们的 `LinkedHashMap` 示例中，应该使用标准的 `BiPredicate<Map<K,V>, Map.Entry<K,V>>` 接口，而不是自定义的 `EldestEntryRemovalFunction` 接口。

`java.util.Function` 中有四十三个接口。你不能要求记住所有的它们，但如果你记住了六个基础接口，在需要时就可以推导出其他接口。基础接口对对象引用类型操作。`Operator` 接口表示结果类型和参数类型相同的函数。`Predicate` 接口表示接收参数并返回 `boolean` 的函数。`Function` 接口表示参数类型和返回类型不同的函数。`Supplier` 接口表示不接受参数并返回（或“提供”）值的函数。最后，`Consumer` 表示接收一个参数且不返回任何内容的，本质上消耗了它的参数。六个基础函数式接口总结如下：

| 接口 | 函数签名 | 示例 |
| :--- | :--- | :--- |
| `UnaryOperator<T>` | `T apply(T t)` | `String::toLowerCase` |
| `BinaryOperator<T>` | `T apply(T t1, T t2)` | `BigInteger::add` |
| `Predicate<T>` | `boolean test(T t)` | `Collection::isEmpty` |
| `Function<T,R>` | `R apply(T t)` | `Arrays::asList` |
| `Supplier<T>` | `T get()` | `Instant::now` |
| `Consumer<T>` | `void accept(T t)` | `System::out::println` |

这六个基础接口的每种都有三种变体，用于对原始类型 `int`、`long` 和 `double` 操作。它们的名称通过在基础接口前加上原始类型前缀衍生。例如，一个接收 `int` 的谓词是 `IntPredicate`，一个接收两个 `long` 值并返回 `long` 的二元运算符是 `LongBinaryOperator`。这些变体类型中没有 `Function` 变体是参数化的，它们按返回类型参数化。例如，`LongFunction<int[]>` 接收一个 `long` 并返回一个 `int[]`。

`Function` 接口还有九个变体，用于结果类型为原始类型的情况。源类型和结果类型总是不同的，因为从一个类型到其自身的函数是 `UnaryOperator`。如果源类型和结果类型都是原始类型，在 `Function` 前加上 `Src`To`Result`，例如 `LongToIntFunction`（六个变体）。如果源是原始类型而结果是对象引用，在 `Function` 前加上 `Src>ToObj`，例如 `DoubleToObjFunction`（三个变体）。

这三个基础函数式接口有双参数的版本，这些版本是有意义的：`BiPredicate<T,U>`、`BiFunction<T,U,R>` 和 `BiConsumer<T,U>`。还有返回三个相关原始类型的 `BiFunction` 变体：`ToIntBiFunction<T,U>`、`ToLongBiFunction<T,U>` 和 `ToDoubleBiFunction<T,U>`。`Consumer` 有接收一个对象引用和一个原始类型的双参数变体：`ObjDoubleConsumer<T>`、`ObjIntConsumer<T>` 和 `ObjLongConsumer<T>`。总而言之，基础接口有九个双参数版本。

最后是 `BooleanSupplier` 接口，它是 `Supplier` 的一种变体，返回 `boolean` 值。这是任何标准函数式接口名称中唯一明确提到 `boolean` 类型的地方，但 `boolean` 返回值通过 `Predicate` 及其四个变体形式支持。`BooleanSupplier` 接口和前面描述的四十二接口构成了所有的函数式接口。诚然，这听起来很多，而且并不那么正交。另一方面，你需要的大多数函数式接口已经写好了，而且名称足够规律，需要时不需要困难。

大多数函数式接口是为了支持原始类型而存在的。**不要被诱惑使用带箱的基础接口来代替原始接口。** 虽然这样做可行，但它违反了 Item 61 的建议，“优先使用原始类型而非箱类型。”在批量操作中使用箱类型的性能后果可能是致命的。

现在你知道你应该优先使用函数式接口而不是编写自己的。但你*什么时候*应该编写自己的？当然，如果没有一个标准接口能满足你的需求，你就需要编写，例如如果你需要一个接收三个参数的谓词，或者一个抛出检查异常的谓词。但在某些情况下，即使标准接口结构相同，你也应该编写自己的。

### 考虑 Comparator

考虑我们的老朋友 `Comparator<T>`，它在结构上与 `ToIntBiFunction<T,T>` 接口相同。即使后者在前者添加到库中时已经存在，使用它也是错误的。有几个理由说明 `Comparator` 值得自己的接口。首先，它的名称每次在 API 中运行时都提供了良好的文档，而且它被频繁使用。其次，`Comparator` 接口对什么是有效实例有很的要求，这构成了它的*通用合约*。通过实现接口，你承诺遵守该合约。第三，该接口配备了大量实用的默认方法来转换和组合比较器。

如果你需要一个与 `Comparator` 共享一个或多个特征的函数式接口，你应该认真考虑编写一个专门的函数式接口，而不是使用标准的接口：

- 它会被频繁使用，并能从描述性名称中获益。
- 它关联有强合约。
- 它能从自定义默认方法中获益。

如果你选择编写自己的函数式接口，请记住它是一个接口，因此应该非常仔细的设计（Item 21）。

注意 `EldestEntryRemovalFunction` 接口（第 199 页）被标记了 `@FunctionalInterface` 注解。这种注解类型在精神上与 `@Override` 类似。它是程序员意图的声明，具有三个作用：它告诉该类及其文档的读者，该接口是为了启用 lambda 而设计的；它能让你保持严谨，因为该接口必须恰好有一个抽象方法，否则将无法编译；它还可以防止维护者在接口演进过程中意外地向接口添加抽象方法。**始终为你的函数式接口加上 `@FunctionalInterface` 注解。**

关于在 API 中使用函数式接口，还有最后一点说明。如果可能为客户端引起可能的歧义，请勿在相同的参数位置提供带有不同函数式接口的重载方法。这不仅仅是一个理论性问题。`ExecutorService` 的 `submit` 方法可以接受 `Callable<T>` 也可以接受 `Runnable`，并且可能写出一个需要通过强制类型转换来指示正确重载的客户端程序（Item 52）。避免此问题最简单的方法是不在相同的参数位置上编写接受不同函数式接口的重载。这是 Item 52 中“谨慎使用重载”建议的一个特例。

总而言之，既然 Java 现在已经有了 lambda，你务必在设计 API 时考虑到 lambda。在输入时接受函数式接口类型，并在输出时返回它们。通常最好是使用 `java.util.function.Function` 提供的标准接口，但也要留意那些较少见的情况，在那些情况下编写自己的函数式接口可能会更好。

### Item 45: 谨慎使用流

Streams API 是在 Java 8 中引入的，旨在简化执行顺序或并行批量操作的任务。该 API 提供了两个核心抽象：`stream`（流），代表有限或无限的数据元素序列；以及 `stream pipeline`（流流水线），它代表对这些元素进行多阶段计算。流中的元素可以来自任何地方。常见来源包括集合、数组、文件、正则表达式模式匹配器、伪随机数生成器和其他流。流中的数据元素可以是对象引用或基本类型值。它支持三种基本类型：`int`、`long` 和 `double`。

一个流流水线由一个源流组成，后面跟着零个或多个`intermediate operations`（中间操作）和一个`terminal operation`（终端操作）。每个中间操作都会以某种方式转换流，例如将每个元素映射到该元素的函数，或者过滤掉所有不满足某些条件的元素。所有的中间操作都会将一个流转换为另一个流，其元素类型可能与输入流相同，也可能不同。终端操作对上一个中间操作产生的流执行最终计算，例如将其元素存储到集合中、返回某个元素或打印所有元素。

流流水线是**惰性**（`lazily`）求值的：在调用终端操作之前，计算不会开始，而且为了完成终端操作而不需要的数据元素永远不会被计算。这种惰性求使得处理无限流成为可能。注意，没有终端操作的流流水线是一个沉默的空操作，所以不要忘记包含一个。

Streams API 是**流式的**（`fluent`）：它的设计允许将组成流水线的所有调用链成一个单一表达式。事实上，多个流水线也可以链接到单个表达式中。

默认情况下，流流水线按顺序执行。让流水线并行执行非常简单，只需在流水线中的任何流上调用 `parallel` 方法即可，但这样做并不常见（Item 48）。

Streams API 足够多功能，几乎任何计算都可以使用流来完成，但仅仅因为你可以这样做，并不意味着你应该这样做。当使用恰当时，流可以使程序更短、更清晰；当使用不当时，它们会使程序难以阅读和维护。关于何时使用流，没有硬性规定，但有一些启发式方法。

考虑以下程序，它从字典文件中读取单词，并打印所有大小符合用户指定的最小限制的异位词组（anagram groups）。回想，如果两个单词由相同的字母但顺序不同组成，它们就是异位词。该程序从用户指定的字典文件中读取每个单词，并将单词放入 map 中。map 的键是字母按字母顺序排序后的单词，因此 `"staple"` 的键是 `"aelpst"`，而 `"petals"` 的键也是 `"aelpst"`：这两个词是异位词，且所有的异位词都共享同一个字母排序形式（有时被称为 `alphagram`）。map 的值是一个包含所有共享字母排序形式单词的列表。处理完字典后，每个列表都是一个完整的异位词组。程序然后遍历 map 的 `values()` 视图并打印每个大小达到阈值的列表：

```java
// 迭代打印字典中所有大型异位词组
public class Anagrams {
    public static void main(String[] args) throws IOException {
        File dictionary = new File(args[0]);
        int minGroupSize = Integer.parseInt(args[1]);
        Map<String, Set<String>> groups = new HashMap<>();
        try (Scanner s = new Scanner(dictionary)) {
            while (s.hasNext()) {
                String word = s.next();
                groups.computeIfAbsent(alphabetize(word), () -> new TreeSet()).add(word);
            }
        }
        for (Set<String> group : groups.values()) {
            if (group.size() >= minGroupSize)
                System.out.println(group.size() + ": " + group);
        }
    }
    private static String alphabetize(String s) {
        char[] a = s.toCharArray();
        Arrays.sort(a);
        return new String(a);
    }
}
```

该程序中的一步值得注意。将每个单词插入 map 的操作（如加粗所示）使用了 `computeIfAbsent` 方法，该方法是在 Java 8 中添加的。该方法在 map 中查找键：如果键存在，该方法直接返回其值。如果不存在，方法通过将给定的函数应用到键来计算出一个值，将此值与键关联，并返回计算出的值。`computeIfAbsent` 方法简化了将多个值与每个键关联的 map 的实现。

现在考虑以下程序，它解决了相同的问题，但大量使用了流。注意，除了打开字典文件的代码外，整个程序都包含在一个表达式中。在单独表达式中打开字典的唯一原因是允许使用 `try`-with-resources 语句，这确保了字典文件会被关闭：

```java
// 过度使用流 - 不要这样做！
public class Anagrams {
    public static void main(String[] args) throws IOException {
        Path dictionary = Paths.get(args[0]);
        int minGroupSize = Integer.parseInt(args[1]);
        try (Stream<String> words = Files.lines(dictionary)) {
            words.collect(
                groupingBy(word -> word.chars().sorted()
                    .collect(StringBuilder::new,
                        (sb, c) -> sb.append((char) c),
                        StringBuilder::append).toString()))
            .values().stream()
            .filter(group -> group.size() >= minGroupSize)
            .map(group -> group.size() + ": " + group)
            .forEach(System.out::println);
        }
    }
}
```

如果你觉得这段代码难以阅读，不要担心；你并不孤单。它虽然更短了，但可读性也降低了，对于那些不是流使用专家的程序员来说更是。**过度使用流会导致程序难以阅读和维护。**

幸运的是，有一个折中方案。下面的程序解决了相同的问题，它使用了流，但并没有过度使用。结果是得到了一个比原始代码更短、更清晰的程序：

```java
// 对流的得体使用增强了清晰性和简洁
public class Anagrams {
    public static void main(String[] args) throws IOException {
        Path dictionary = Paths.get(args[0]);
        int minGroupSize = Integer.parseInt(args[1]);
        try (Stream<String> words = Files.lines(dictionary)) {
            words.collect(groupingBy(word -> alphabetize(word)))
                .values().stream()
                .filter(group -> group.size() >= minGroupSize)
                .forEach(g -> System.out.println(g.size() + ": " + g));
        }
    }
    // alphabetize 方法与原始版本相同
}
```



即使你之前对流几乎没有接触，这个程序也并不难理解。它在`try`-with-resources`块中打开字典文件，获取一个包含文件中所有行的流。该`stream`变量被命名为`words`，以暗示流中的每个元素都是单词。该流上的流水线没有中间操作；它的终端操作将所有单词收集到一个 map 中，该 map 根据单词按字母顺序排序后的形式对单词进行分组（项目 46）。这与程序之前的两个版本中构建的 map 是完全相同的。然后，在 map 的`values()`视图上打开了一个新的`Stream<List<String>>`。该流中的元素显然是字母异位词组。对该流进行了过滤，忽略了所有大小小于`minGroupSize`的组，最后由终端操作`forEach`打印剩余的组。

注意，lambda 参数名经过了仔细选择。参数`g`应该命名为`group`，但生成的代码行会太宽，无法放入书中。在缺少显式类型的情况下，仔细命名 lambda 参数对于流流水线的可读性至关重要。

同样注意，单词的字母排序是在单独`alphabetize`方法中完成的。通过为操作提供一个名称并将实现细节排除在主程序之外，增强了可读性。在流流水线中，使用辅助方法对于可读性的重要性甚至高于迭代代码，因为流水线缺乏显式的类型信息和命名的临时变量。

`alphabetize`方法可以重新实现为使用流，但基于流的`alphabetize`方法会不清晰，更难正确编写，而且可能更慢。这些缺陷源于 Java 缺乏对原始`char`流的支持（这并不意味着 Java 应该支持`char`流；这样做是不可行的）。为了演示用流处理`char`值的危险，请考虑以下代码：

```java
"Hello world!".chars().forEach(System.out::print);
```

你可能期望它打印`Hello world!`，但如果你运行它，你会发现它打印出`721011081081113211911111410810033`。这是因为`"Hello world!".chars()`返回的流元素不是`char`值而是`int`值，因此调用了`print`的`int`重载版本。一个名为`chars`的方法返回`int`值的流确实令人困惑。你*可以*通过使用转换强制调用正确的重载版本来修复程序：

```java
"Hello world!".chars().forEach(x -> System.out.print((char) x));
```

但理想情况下，你应该避免使用流来处理`char`值。

当你开始使用流时，可能会产生将所有循环转换为流的冲动，但请克制这种冲动。虽然可能，但可能会损害你代码库的可读性和可维护性。作为一个原则，即使是中等复杂的任务，最好也通过流和迭代的结合来完成，如上面的`Anagrams`程序所示。因此，重构现有代码使用流，并仅在合理的地方在新代码中使用流。

正如本项目中的程序所示，流流水线使用函数对象（通常是 lambda 或方法引用）表示重复计算，而迭代代码则使用代码块表示重复计算。有些你可以在代码块中做、但在函数对象中无法做的事情：

* 从代码块中，你可以读取或修改作用范围内的任何局部变量；从 lambda 中，你只能读取最终或有效最终的变量 [JLS 4.12.4]，且你不能修改任何局部变量。
* 从代码块中，你可以从闭包的方法中`return`，`break`或`continue`闭包循环，或者抛出该方法声明要抛出的任何检查异常；从 lambda 中，你不能做这些任何一件事。

如果一个计算最适合使用这些技术来表达，那么它可能不适合流。相反，流使得某些事情变得非常简单：

* 统一地转换元素序列
* 过滤元素序列
* 使用单个操作组合元素序列（例如将它们相加或计算最小值）
* 将元素序列累积到集合中，可能按某些属性对其进行分组
* 在元素序列中搜索符合某些标准的元素

如果一个计算最适合使用这些技术来表达，那么它就是流的良好候选。

用流很难做的一件事是同时访问多个阶段的对应元素：一旦你将一个值映射到其他值，原始值就丢失了。一种通方法是将每个值映射到包含原始值和新值的对对象，但这并不是一个满意的解决方案，特别是当流水线的多个阶段都需要这些对对象时。生成的代码既混乱又冗长，违背了流的主要意目的。在适用的情况下，更好的通方法是在需要访问早期阶段的值时反转映射。

例如，让我们写一个程序打印前二十个梅森数。为了复习记忆，梅森数是形式为`2^p − 1`的。如果*p*是素数，相应的梅森数*可能*是素数；如果是，它就是梅森素数。作为流水线的初始流，我们需要所有的素数。这里有一个返回该（无限）流的方法。我们假设已经使用了静态导入以便方便访问`BigInteger`的静态成员：

```java
static Stream<BigInteger> primes() {
    return Stream.iterate(TWO, BigInteger::nextProbablePrime);
}
```

方法名（`primes`）是描述流元素的复数名词。这种命名约定建议用于返回流的方法，因为它增强了流流水线的可读性。该方法使用了静态工厂`Stream.iterate`，它接受两个参数：流中的第一个元素，以及一个从上一个元素生成流中下一个元素的函数。这里是打印前二十个梅森素数的程序：

```java
public static void main(String[] args) {
    primes().map(p -> TWO.pow(p.intValueExact()).subtract(ONE))
        .filter(mersenne -> mersenne.isProbablePrime(50))
        .limit(20)
        .forEach(System.out::println);
}
```

### 基于流的实现

该程序是对上述文字描述的直接编码：它从素数开始，计算对应的梅森数，过滤掉除素数以外的所有数（魔术数字`50`控制了概率素数测试），将结果流流限制在二十个元素，并将其打印出来。

现在假设我们想在每个梅森素数的前面带上它的指数（`p`）。这个值只存在于初始流中，因此在打印结果的终端操作中是无法访问的。幸运的是，通过反转第一个中间操作执行的映射，可以很容易计算出梅森数的指数。指数仅仅是二进制表示法中的位数，因此这个终端操作生成了所需的结果：

```java
.forEach(mp -> System.out.println(mp.bitLength() + ": " + mp));
```

在许多任务中，并不明显应该使用流还是迭代。例如，考虑初始化一副新扑克牌的任务。假设`Card`是一个不可变值类，封装了`Rank`（点数）和`Suit`（花色），两者都是枚举类型。这个任务对于任何需要从两个集合中选出所有元素对的任务都代表性。数学家将此称为两个集合的*笛卡尔积*。这里有一个带有嵌套 for-each 循环的迭代实现，它看起来对你来说非常熟悉：

#### 迭代笛卡尔积计算

```java
private static List<Card> newDeck() {
    List<Card> result = new ArrayList<>();
    for (Suit suit : Suit.values())
        for (Rank rank : Rank.values())
            result.add(new Card(suit, rank));
    return result;
}
```

这是一个使用中间操作`flatMap`的流式实现。该操作将流中的每个元素映射到一个流，然后将所有这些新流连接成单个流（或将其*展平*）。注意，此实现包含一个加粗显示的嵌套 lambda 表达式：

#### 流的笛卡尔积计算

```java
private static List<Card> newDeck() {
    return Stream.of(Suit.values())
        .flatMap(suit ->
            Stream.of(Rank.values())
                .map(rank -> new Card(suit, rank)))
        .collect(toList());
}
```

两个版本的`newDeck`哪个更好？这取决于个人偏好以及你编程的环境。第一个版本更简单，可能感觉更自然。会有更多的 Java 程序员能够理解并维护它，但某些程序员会觉得第二个（基于流的）版本更舒服。如果你对流和函数式编程足够熟悉，它会更简洁，而且理解起来并不困难。如果你不确定更偏于哪一个版本，迭代版本可能是更安全的选择。如果你更偏于流版本，并且认为处理该代码的其他程序员也会有同样的偏好，那么你就应该使用它。

总而言之，某些任务最适合用流完成，而另一些则最适合用迭代。许多任务最适合通过结合这两种方法来完成。对于选择哪个任务使用哪种方法没有硬性规定，但有一些实用的启发式方法。在很多情况下，使用哪种方法是很清楚的；在某些情况下则不会。如果你不确定某个任务更适合用流还是迭代，请尝试两种方法看看哪种效果更好。

### 元素 46：在流中优选使用无副作用函数

如果你是流的初学者，可能很难掌握它们。仅仅将你的计算表示为流水线（pipeline）可能是困难的。当你成功时，你的程序会运行，但你可能发现没什么（即使有）好处。流不仅是一个 API，它是一种基于函数式编程的范式。为了获得流所提供的表达力、速度以及在某些情况下的并行性，你必须采用这种范式，而不仅仅是其 API。

流范式最重要的部分是将计算结构化为一系列转换，每个阶段的结果尽可能地是上一个阶段结果的*纯函数*。纯函数是指结果仅取决于其输入的函数：它不依赖于任何可变状态，也不会更新任何状态。你传递到流操作（无论是中间操作还是终端操作）的任何函数都应该没有副作用。偶尔，你会看到像这样的流代码，它构建了一个频率表：

#### 使用了流 API 但未使用范式——不要这样做

```java
Map<String, Long> freq = new HashMap<>();
try (Stream<String> words = new Scanner(file).tokens()) {
    words.forEach(word ->
        freq.merge(word.toLowerCase(), 1L, Long::sum));
}
```

这段代码有什么问题？毕竟，它使用了流、lambda 和方法引用，并且得到了正确的答案。简单来说，它根本不是流代码；它是伪装成流的迭代代码。它没有从流 API 中获得任何收益，而且比迭代代码更长（一点）、更难读且维护性更差。问题源于该代码在终端`forEach`操作中执行所有工作，并修改了（频率表）。那么，这段代码应该是样子的？

#### 正确使用流初始化频率表

```java
Map<String, Long> freq;
try (Stream<String> words = new Scanner(file).tokens()) {
    freq = words.collect(groupingBy(String::toLowerCase, counting()));
}
```

这段代码与前一个做了相同的事，但正确地使用了流 API。它更短更清晰。那么为什么有人会用那种写法呢？因为它使用了他们已经熟悉的工具。Java 程序员知道如何使用 for-each 循环，而`forEach`终端操作与之相似。但`forEach`操作是终端操作中最弱且最不便于流的操作之一。它是显式迭代，因此不利并行化。`forEach`操作应该只用于报告流计算的结果，而不是执行计算。偶尔，将`forEach`用于其他目的是合理的，例如将流计算的结果添加到预定义的集合中。

改进后的代码使用了收集器（collector），这是一个你为了使用流而必须学习的新概念。`Collectors`API 令人敬畏：它有 39 个方法，其中某些方法多达五个类型参数。好消息是，你不需要深入其全部的复杂性就可以从这个 API 中获得大部分收益。初学者，你可以忽略`Collector`接口，并将收集器视为一个封装了*归约*（reduction）策略的不透明对象。在这种语境下，归约意味着将流中的元素合并为一个单个对象。收集器产生的对象通常是一个集合（这就是 collector 名称的由来）。

将流中的元素收集到真正的`Collection`中的收集器是非常直观的。有三个这样的收集器：`toList()`、`toSet()`和`toCollection(collectionFactory)`。它们分别返回一个集合、一个列表以及程序员指定的集合类型。掌握了这些知识后，我们可以编写一个流流水线，从我们的频率表中提取出前十名的列表。

```java
// 从频率表中获取单词前十名列表的流水线
List<String> topTen = freq.keySet().stream()
    .sorted(comparing(freq::get).reversed())
    .limit(10)
    .collect(toList());
```

注意，我们没有使用类`Collectors`对`toList`方法进行限定。静态导入`Collectors`的所有成员是一种惯常做法也是明智的，因为这使得流流水线更具可读性。

这段代码中唯一复杂的地方在于传递给`sorted`的比较器：`comparing(freq::get).reversed()`。`comparing`方法是一个比较器构造方法（项目 14），它接受一个键提取函数。该函数接收一个单词，而“提取”实际上是表查询：绑定的方法引用`freq::get`在频率表中查找该单词，并返回该单词在文件中出现的次数。最后，我们在比较器上调用`reversed`，因此我们是按频率从高到低对单词进行排序。然后，将流限制为十个单词并将它们收集到列表中就是轻而易举了。

之前的代码片段使用`Scanner`的`stream`方法来获取关于扫描器的流。该方法是在 Java 9 中添加的。如果你使用的是更早版本，可以使用类似于项目 47 中的`streamOf(Iterable<E>)`的适配器，将实现`Iterator`的扫描器转换为流。

那么`Collectors`中的其他 36 个方法呢？它们大多数方法的存在是为了让你将流收集到映射（maps），这比将它们收集到真正的集合要复杂得多。每个流元素都与一个键*和一个值*关联，并且多个流元素可以关联同一个键。

最简单的映射收集器是`toMap(keyMapper, valueMapper)`，它接受两个函数，其中一个将流元素映射到键，另一个将其映射到值。我们在项目 34 的`fromString`实现中使用了这个收集器，从枚举的字符串形式到枚举本身创建一个映射：

```java
// 使用 toMap 收集器创建一个从字符串到枚举的映射
private static final Map<String, Operation> stringToEnum =
    Stream.of(values()).collect(
        toMap(Object::toString, e -> e));
```

如果流中的每个元素都映射到一个唯一的键，这种简单形式的`toMap`就是完美的。如果多个流元素映射到同一个键，流水线将以`IllegalStateException`终止。

更复杂的`toMap`形式以及`groupingBy`方法为你提供了多种方式来提供处理此类冲突的策略。一种是在向`toMap`方法提供键映射和值映射器之外，再提供一个*合并函数*（merge function）。合并函数是一个`BinaryOperator<V>`，其中`V`是映射的值类型。与键关联的任何额外值都将合并函数与现有值合并，例如，如果合并函数是乘法，你最终得到的值是由值映射器与键关联的所有值相乘的结果。

`toMap`的三参数形式也用于创建一个从键到与键关联的所选元素的映射。例如，假设我们有一个由不同艺术家提供的录音专辑流，我们想要创建一个从录制艺术家到最畅销专辑的映射。这个收集器可以完成工作。

```java
// 生成从键到所选元素映射的收集器
Map<Artist, Album> topHits = albums.collect(
    toMap(Album::artist, a->a, maxBy(comparing(Album::sales)));
```

注意，该比较器使用了静态工厂方法`maxBy`，该方法是从`BinaryOperator`静态导入的。此方法将`Comparator<T>`转换为`BinaryOperator<T>`，用于计算由指定比较器所隐含的最大值。在这种情况下，比较器是由比较器构造方法`comparing`返回的，该方法接受键提取函数`Album::sales`。这看起来可能有点复杂，但代码读起来很自然。粗略地说，它的意思是：“将专辑流转换为映射，将每个艺术家映射到销售额最好的专辑。”这与问题陈述的描述非常接近。

`toMap`三参数形式的另一个用途是产生一个在发生冲突时实施“后写入者获胜”（last-write-wins）策略的收集器。对于许多流来说，结果将是不确定的，但如果映射函数可能与键关联的所有值都是相同的，或者如果它们都是可以接受的，那么这个收集器的行为可能正是你需要的：

```java
// 执行后写入者获胜策略的收集器
```



`toMap(keyMapper, valueMapper, (v1, v2) -> v2)`

`toMap` 的最后一个版本接受第四个参数，映射工厂，用于当你想要指定特定的映射实现（如 `EnumMap` 或 `TreeMap`）时。

`toMap` 前三个版本也有变体形式，命名为 `toConcurrentMap`，它们可以高效地并行并产生 `ConcurrentHashMap` 实例。

除了 `toMap` 方法外，`Collectors` API 还提供了 `groupingBy` 方法，它返回用于根据*分类函数*将元素分组到映射中的收集器。分类函数接收一个元素并返回它所属的类别。该类别作为元素的键。`groupingBy` 方法的最简单版本只接受分类器，并返回一个值为每个类别元素列表的映射。这是我们在项目 45 的 `Anagram` 程序中使用的收集器，用于生成从字母顺序单词到共享相同字母顺序单词列表的映射：

```java
words.collect(groupingBy(word -> alphabetize(word)))
```

如果你想让 `groupingBy` 返回一个值不是列表的收集器，可以在分类器之外指定一个下游收集器。下游收集器从包含类别所有元素的流产生一个值。该参数的最简单用法是传递 `toSet()`，这会导致映射值为元素的集合而不是列表。

或者，你可以传递 `toCollection(collectionFactory)`，这允许你创建将每类元素放入其中的集合。这给了你选择任何所需集合类型的灵活性。`groupingBy` 二参数形式的另一个简单用法是将 `counting()` 作为下游收集器。这会产生一个将每个类别与类别中的*数量*关联的映射，而不是包含元素的集合。这就是我们在项目开头的频率表示例中所看到的：

```java
Map<String, Long> freq = words
    .collect(groupingBy(String::toLowerCase, counting()));
```

`groupingBy` 的第三版本允许你在指定下游收集器（downstream collector）的同时指定一个 map 工厂。请注意，该方法违反了标准的嵌套参数列表（telescoping argument list）模式：`mapFactory` 参数在 `downStream` 参数之前而不是之后。这个版本的 `groupingBy` 让你能够控制容器 map 以及包含的集合，例如，你可以指定一个返回 `TreeMap` 且其值为 `TreeSet` 的收集器。

`groupingByConcurrent` 方法提供了 `groupingBy` 所有三个重载版本的变体。这些变体在并行环境下高效运行并产生 `ConcurrentHashMap` 实例。还有一个 `groupingBy` 的不常用相关方法叫做 `partitioningBy`。它没有使用分类方法，而是接收一个谓词（predicate）并返回一个键为 `Boolean` 的 map。该方法有两个重载，其中一个除了接收谓词外还接收一个下游收集器。

`counting` 方法返回的收集器*仅*用于作为下游收集器。相同的功能可以通过 `Stream` 上的 `count` 方法直接获得，因此永远没有必要使用 `collect(counting())`。还有 15 个具有此类属性的 `Collectors` 方法。它们包括九个以 `summing`、`averaging` 和 `summarizing` 开头的方法（这些功能在对应的原始类型流上同样可用）。它们还包括 `reducing` 方法的所有重载，以及 `filtering`、`mapping`、`flatMapping` 和 `collectingAndThen` 方法。大多数程序员可以安全地忽略这些方法的大部分。从设计角度来看，这些收集器代表了在收集器中部分复制流的功能，以便下游收集器可以充当“微流”（ministreams）。

我们还没有提到三个 `Collectors` 方法。虽然它们在 `Collectors` 类中，但并不涉及集合。前两个是 `minBy` 和 `maxBy`，它们接收一个比较器（comparator）并根据比较器的结果返回流中的最小或最大元素。它们是 `Stream` 接口中 `min` 和 `max` 方法的次要泛化，并且是 `BinaryOperator` 中同名方法返回的二元运算符的收集器等价物。回想一下我们在畅销专辑示例中使用过 `BinaryOperator.maxBy`。

最后一个 `Collectors` 方法是 `joining`，它只对 `CharSequence` 实例流（如字符串）操作。在无参数形式下，它返回一个简单拼接元素的收集器。它的单参数形式接收一个名为 `delimiter` 的 `CharSequence` 参数，并返回一个连接流元素的收集器，在相邻元素之间插入分隔符。如果你传递逗号作为分隔符，收集器将返回一个逗号分隔的字符串（但注意，如果流中的任何元素包含逗号，该字符串将产生义）。三参数形式除了分隔符外还接收前缀和后缀。生成的收集器产生的字符串类似于打印集合时得到的字符串，例如 `[came, saw, conquered]`。

总之，流管道编程的本质是无副作用函数对象。这适用于所有传递给流及相关对象的函数对象。终端操作 `forEach` 应该只用于报告流执行计算的结果，而不是用于执行计算。为了正确使用流，你必须了解收集器。最重要的收集器工厂是 `toList`、`toSet`、`toMap`、`groupingBy` 和 `joining`。

## 事项 47：优先使用 Collection 而非 Stream 作为返回类型

许多方法返回元素序列。在 Java 8 之前，此类方法的明显返回类型是集合接口 `Collection`、`Set` 和 `List`；`Iterable` 以及数组类型。通常，决定返回这些类型中的哪一个很容易。规范是返回集合接口。如果方法仅仅是为了支持 for-each 循环，或者返回的序列无法实现某些 `Collection` 方法（通常是 `contains(Object)`），则使用 `Iterable` 接口。如果返回的元素是原始值或有严格的性能要求，则使用数组。在 Java 8 中，流被引入平台，极大地增加了为返回序列的方法选择合适返回类型的复杂性。

你可能会听到别人说，流现在是返回元素序列的明显选择，但正如在 事项 45 中讨论的，流并没有让迭代过时：编写良好的代码需要明智地结合流和迭代。如果一个 API 只返回流，而某些用户想用 for-each 循环遍历返回的序列，这些用户会感到理所当然的。这尤其令人沮丧，因为 `Stream` 接口包含了 `Iterable` 接口中唯一的抽象方法，且 `Stream` 对该方法的规范与 `Iterable` 兼容。唯一阻止程序员使用 for-each 循环遍历流的原因是 `Stream` 未扩展 `Iterable`。

遗憾的是，这个问题没有好的折通方案。乍看之下，将方法引用传递给 `Stream` 的 `iterator` 方法似乎是行的。生成的代码可能有点冗杂且晦懂，但并不可理：

```java
// 无法编译，由于 Java 类型推断的限制
for (ProcessHandle ph : ProcessHandle.allProcesses()::iterator) {
    // 处理该进程
}
```

不幸的是，如果你尝试编译这段代码，你将得到一个错误消息：

```
Test.java:6: error: method reference not expected
for (ProcessHandle ph : ProcessHandle.allProcesses()::iterator) {
                               ^
```

为了让代码通过编译，你必须将方法引用强制转换为适当的 `Iterable`：

```java
// 遍历流的丑陋折通方案
for (ProcessHandle ph : (Iterable<ProcessHandle>) ProcessHandle.allProcesses()::iterator) {
```

这种客户端代码有效，但在实践中太冗杂且晦懂了。更好的折通方案是使用适配器方法。JDK 没有提供这样的方法，但使用上面代码段中的相同技术很容易编写一个。注意，适配器方法中不需要转换，因为 Java 的类型推断在此上下文中工作正常：

```java
// 从 Stream<E> 到 Iterable<E> 的适配器
public static <E> Iterable<E> iterableOf(Stream<E> stream) {
    return stream::iterator;
}
```

有了这个适配器，你可以用 for-each 语句遍历任何流：

```java
for (ProcessHandle p : iterableOf(ProcessHandle.allProcesses())) {
    // 处理进程
}
```

注意事项 34 中 `Anagrams` 程序的流版本使用 `Files.lines` 方法读取字典，而迭代版本使用了 scanner。`Files.lines` 方法优 scanner，后者会静默吞掉读取文件时遇到的任何异常。理想情况下，我们会在迭代版本中也使用 `Files.lines`。如果一个 API 只提供序列的流访问，而用户想用 for-each 语句遍历序列，这就是程序员会做出的妥协。

相反，如果一个想使用流管道处理序列的程序员发现一个 API 只提供了 `Iterable`，他们会感到理所当然的愤怒。再次 JDK 没有提供这样的适配器，但编写一个很容易：

```java
// Adapter from Iterable<E> to Stream<E>
public static <E> Stream<E> streamOf(Iterable<E> iterable) {
    return StreamSupport.stream(iterable.spliterator(), false);
}
```

如果你正在编写一个返回对象序列的方法，并且知道它只会被用于流流水线（stream pipeline），那么你当然可以自由地返回一个 `stream`。同样，返回一个仅用于迭代的序列的方法应该返回一个 `Iterable`。但如果你正在编写一个返回序列的公共 API，你应该为那些想要编写流流水线的用户以及那些想要编写 `for-each` 语句的用户都提供支持，除非你有充分的理由相信大多数用户都想使用同一种机制。

`Collection` 接口是 `Iterable` 的子类型，并且有一个 `stream` 方法，因此它同时提供了迭代和流访问。因此，`Collection` 或其适当的子类型通常是返回序列的公共方法的最佳返回类型。数组也通过 `Arrays.asList` 和 `Stream.of` 方法提供了方便的迭代和流访问。如果你返回的序列足够小，可以轻松放入内存中，那么返回一个标准集合实现类（如 `ArrayList` 或 `HashSet`）可能是最好的选择。但不要为了将其作为集合返回而将大型序列存储在内存中。

如果你返回的序列很大但可以用简洁的方式表示，请考虑实现一种特殊用途的集合。例如，假设你想返回给定集合的幂集（power set），即该集合的所有子集。`{a, b, c}` 的幂集是 `{{}, {a}, {b}, {c}, {a, b}, {a, c}, {b, c}, {a, b, c}}`。如果一个集合有 $n$ 个元素，它的幂集就有 $2^n$ 个。因此，你甚至不应该考虑在标准集合实现中存储幂集。然而，借助 `AbstractList` 的帮助，可以很容易为该任务实现一个自定义集合。

这里的技巧是将幂集中每个元素的索引用作位向量，其中索引中的第 $n$ 位表示源集合中第 $n$ 个元素是否存在。本质上，从 0 到 $2^n - 1$ 的二进制数与具有 $n$ 个元素的集合的幂集之间存在着天然映射。代码如下：

```java
// Returns the power set of an input set as custom collection
public class PowerSet {
    public static final <E> Collection<Set<E>> of(Set<E> s) {
        List<E> src = new ArrayList<>(s);
        if (src.size() > 30)
            throw new IllegalArgumentException("Set too big " + s);
        return new AbstractList<Set<E>>() {
            @Override public int size() {
                return 1 << src.size(); // 2 to the power srcSize
            }
            @Override public boolean contains(Object o) {
                return o instanceof Set && src.containsAll((Set)o);
            }
            @Override public Set<E> get(int index) {
                Set<E> result = new HashSet<>();
                for (int i = 0; index != 0; i++, index >>= 1)
                    if ((index & 1) == 1)
                        result.add(src.get(i));
                return result;
            }
        };
    }
}
```

注意，如果输入集合超过 30 个元素，`PowerSet.of` 将抛出异常。这突出了使用 `Collection` 作为返回类型而非 `Stream` 或 `Iterable` 的缺点：`Collection` 有一个返回 `int` 的 `size` 方法，这限制了返回序列的长度为 `Integer.MAX_VALUE`，或 $2^{31}-1$。`Collection` 规范允许在集合更大时 `size` 方法返回 $2^{31}-1$，但这并不是令人满意的解决方案。

为了在 `AbstractCollection` 之上编写 `Collection` 实现，你除了 `Iterable` 所需的方法外，只需要两个方法：`contains` 和 `size`。通常，编写这些方法的有效实现是容易的。如果不可行（可能是因为序列的内容在迭代发生之前尚未确定），请返回一个 `stream` 或 `iterable`，取决于哪种方式更自然。如果你愿意，可以使用单独的方法同时返回两者。

有时，你将仅仅根据实现的易用程度来选择返回类型。例如，假设你想编写一个返回输入列表所有（连续）子列表的方法。只需三行代码即可生成这些子列表并将它们放入标准集合中，但持有此集合所需的内存相对于源列表的大小呈二次方。虽然这不像指数级增长的幂集那么糟糕，但显然是不可接受的。实现自定义集合（正如我们为幂集做的那样）将很冗冗，而且 JDK 缺乏骨架 `Iterator` 实现来帮助我们。

然而，实现一个输入列表所有子列表的 `stream` 是直接的，尽管这需要一些细微的见解。我们将包含列表第一个元素的子列表称为列表的*前缀*（prefix）。例如，`{a, b, c}` 的前缀是 `{a}`、`{a, b}` 和 `{a, b, c}`。同样，我们将包含最后一个元素的子列表称为*后缀*（suffix），所以 `{a, b, c}` 的后缀是 `{a, b, c}`、`{b, c}` 和 `{c}`。这里的见解是，列表的子列表就是前缀的后缀。这种观察直接指向了一个清晰的实现：

```java
// Returns a stream of all the sublists of its input list
public class SubLists {
    public static <E> Stream<List<E>> of(List<E> list) {
        return Stream.concat(Stream.of(Collections.emptyList()),
            prefixes(list).flatMap(SubLists::suffixes));
    }
    private static <E> Stream<List<E>> prefixes(List<E> list) {
        return IntStream.rangeClosed(1, list.size())
            .mapToObj(end -> list.subList(0, end));
    }
    private static <E> Stream<List<E>> suffixes(List<E> list) {
        return IntStream.range(0, list.size())
            .mapToObj(start -> list.subList(start, list.size()));
    }
}
```



注意`Stream.concat`方法用于将空列表添加到返回的流中。同样注意`flatMap`方法（第 45 节）用于生成一个由所有后缀组成的单个流。最后，注意我们通过映射由`IntStream.range`和`IntStream.rangeClosed`返回的连续整数值来生成前缀和后缀。这种惯用法粗略来说是标准整数`for`循环的流等价物。因此，我们的子列表实现与明显的嵌套`for`循环相似：

```java
for (int start = 0; start < src.size(); start++)
    for (int end = start + 1; end <= src.size(); end++)
        System.out.println(src.subList(start, end));
```

可以将此`for`循环直接翻译为流。结果比我们之前的实现更简洁，但可能可读性稍差。它与第 45 节中笛卡尔积的流代码相似：

```java
// Returns a stream of all the sublists of its input list
public static <E> Stream<List<E>> of(List<E> list) {
    return IntStream.range(0, list.size())
        .mapToObj(start ->
            IntStream.rangeClosed(start + 1, list.size())
                .mapToObj(end -> list.subList(start, end)))
        .flatMap(x -> x);
}
```

与其先的`for`循环一样，这段代码*没有*产生空列表。为了修复这个缺陷，你可以像我们在上一个版本中做的那样使用`concat`，或者在`rangeClosed`调用中将`1`替换为`(int) Math.signum(start)`。

两种子列表的流实现方式都是可以的，但它们都要求某些用户使用`Stream`-to-`Iterable`适配器，或者在迭代更自然的地方使用流。`Stream`-to-`Iterable`适配器不仅会弄乱客户端代码，还会在我的机器上让循环速度变慢 2.3 倍。一个专门构建的`Collection`实现（此处未显示）虽然冗长得多，但在我的机器上运行速度大约比我们基于流的实现快 1.4 倍。

总之，在编写一个返回元素序列的方法时，请记住，某些用户可能希望将其作为流进行处理，而另一些用户可能想对它们进行迭代。尽力兼顾这两组用户。如果返回集合是可行的，请这样做。如果你已经将元素放在集合中，或者序列中的元素数量足够小，足以创建一个新集合，那么请返回像`ArrayList`这样的标准集合。否则，考虑实现一个自定义集合，就像我们为幂集做的那样。如果返回集合是不可行的，请返回流或可迭代对象，取决于哪个看起来更自然。如果在此后的 Java 版本中，`Stream`接口的声明被修改为扩展`Iterable`，那么你可以放心地返回流，因为它们将同时允许流处理和迭代。

## 事项 48：在创建并行流时要小心

在主流语言中，Java 一直在提供简化并发编程任务设施方面处于前沿。Java 在 1996 年发布时，它已经对线程有了内置支持，带有同步机制和`wait`/`notify`。Java 5 引入了`java.util.concurrent`库，包含了并发集合和执行器框架。Java 7 引入了`fork-join`包，这是一个用于并行分解的高性能框架。Java 8 引入了流，可以通过单次调用`parallel`方法实现并行化。在 Java 中编写并发程序变得越来越容易，但编写既正确又快速的并发程序仍然如既往一样困难。安全性和活跃性违反是并发编程中的常态，并行流流水线也不例外。

考虑来自事项 45 的这个程序：

```java
// 用于生成前 20 个梅森质数的流程序
public static void main(String[] args) {
    primes().map(p -> TWO.pow(p.intValueExact()).subtract(ONE))
        .filter(mersenne -> mersenne.isProbablePrime(50))
        .limit(20)
        .forEach(System.out::println);
}

static Stream<BigInteger> primes() {
    return Stream.iterate(TWO, BigInteger::nextProbablePrime);
}
```

在我的机器上，这个程序立即开始打印质数，并需要 12.5 秒运行完成。假设我天真地尝试通过在流流水线添加添加`parallel()`调用来加速。你认为它的性能会发生什么变化？它会快几个百分点吗？还是慢几个百分点？遗憾的是，发生的情况是它什么都不打印，但 CPU 使用率飙升到 90% 并无限保持在那里（这是一个*活跃性失败*）。程序最终可能会终止，但我不想去发现结果；我在半小时后强制停止了它。

这里发生了什么？简单来说，流库并不知道如何并行化这条流水线，启发式方法失效了。即使在最理想的情况下，如果源源自`Stream.iterate`或者使用了中间操作`limit`，并行化流水线也可能无法提高其性能。这条流水线必须同时应对*这两个*问题。更糟糕的是，默认的并行化策略通过假设`limit`的不可预测性来处理，即假设处理几个额外的元素并丢弃任何不需要的结果没有害处。在这种情况下，找到每个梅森质数花费的时间大约是找到上一个数的两倍。因此，计算一个额外元素的成本大致等同于计算所有之前元素的总和，而这个看起来看似无害的流水线让自动并行化算法彻底瘫痪。这个故事的寓理很简单：不要不加区别别地并行化流流水线。性能后果可能是灾难性的。

根据原则，并行带来的性能提升在对`ArrayList`、`HashMap`、`HashSet`和`ConcurrentHashMap`实例；数组；`int`范围以及`long`范围的流上最好。这些数据结构的共同点是，它们都可以准确且廉价地分成任何所需的子范围，这使得在并行线程之间分配工作变得容易。流库执行此任务时使用的抽象是*spliterator*（拆分器），它由`Stream`和`Iterable`上的`spliterator`方法返回。

所有这些数据结构的另一个重要共同点是，它们在顺序处理时提供了良好到极佳的*引用局部性*（locality of reference）：顺序元素引用在内存中聚集在一起。这些引用所指向的对象在内存中可能并不相邻，这会降低引用局部性。事实证明，引用局部性对于并行批量操作至关重要：如果没有它，线程将花费大量时间空闲，等待数据从内存传输到处理器的缓存中。具有最佳引用局部性的数据结构是原始类型数组，因为数据本身连续存储在内存中。

流流水线终端操作的性质也会影响并行执行的效率。如果终端操作相对于整个流水线的工作占很大比例，且该操作本质上是顺序的，那么并行化流水线的效率将有限。并行最好的终端操作是*归约*（reductions），即流产生的所有元素使用`Stream`的`reduce`方法进行组合，或者使用预包的归约如`min`、`max`、`count`和`sum`。短路操作`anyMatch`、`allMatch`和`noneMatch`也适用于并行。`Stream`的`collect`方法执行的操作被称为可变归约（mutable reductions），并不是并行化的良好候选，因为合并集合的开销是巨大的。

如果你编写了自己的`Stream`、`Iterable`或`Collection`实现并希望获得良好的并行性能，你必须重写`spliterator`方法并充分测试结果流的并行性能。编写高质量的 spliterator 是困难的，且超出了本书的范围。

并行化流不仅可能导致性能下降（包括活跃性失败），它还可能导致错误的结果和不可预测的行为（*安全失败*）。安全失败可能源于并行化使用了映射、过滤以及程序员提供的函数对象未能遵循其规范的流水线。`Stream`规范对这些函数对象有严格的要求。例如，传递给`Stream`的`reduce`操作的累加器和合并器必须是结合的、非干扰的且无状态的。如果你违反了这些要求（部分在事项 46 中讨论过）但按顺序运行流水线，它可能会产生正确的结果；如果你对其进行并行化，它可能会失败，甚至可能是灾难性的。

沿着这些思路，值得注意的是，即使并行化的梅森数数程序运行完成，它也不会按照正确的（升序）顺序打印这些质数。为了保留顺序执行版本所显示的顺序，你必须将`forEach`终端操作替换为`forEachOrdered`，它保证按照*相遇顺序*（encounter order）遍历并行流。

即使假设你正在使用一个高效可拆分的源流、可并行化或廉价的终端操作，以及非干涉的函数对象，除非流水线执行了足够的实际工作以抵消并行化相关的成本，否则你无法从并行化中获得良好的加速。作为一个*非常*粗略的估算，流中的元素数量乘以每个元素执行的代码行数至少应该是十万次 [Lea14]。

务必记住，并行化流严格来说只是一种性能优化。与任何优化一样，你必须在更改前后进行性能测试，以确保这种做法是值得的（Item 67）。理想情况下，你应该在真实的系统设置下进行测试。通常，程序中所有的并行流流水线都运行在一个公共的 fork-join 池中。单个运行不当的流水线可能会损害系统中不相关部分的其他流水线的性能。

如果你觉得并行化流流水线看起来胜算极小，那是因为事实确实如此。一位维护数百万行代码库并大量使用流的熟人发现，只有在少数几个地方并行流是有效的。这*并不*意味着你应该避免对流进行并行化。**在适当的情况下，仅通过在流流水线中添加一个`parallel`调用，*确实*可能实现相对于处理器核心数量的近线性加速。** 某些领域，如机器学习和数据处理，特别适用于这些加速。

作为一个并行化有效的流流水线的简单示例，请考虑下面这个用于计算 π(*n*) 的函数，该函数计算小于或等于 *n* 的质数个数：

```java
// 质数计数流流水线 - 从并行化受益
static long pi(long n) {
    return LongStream.rangeClosed(2, n)
            .mapToObj(BigInteger::valueOf)
            .filter(i -> i.isProbablePrime(50))
            .count();
}
```

在我的机器上，使用该函数计算 π(10⁸) 需要 31 秒。只需添加一个`parallel()`调用即可将时间缩短到 9.2 秒：

```java
// 质数计数流流水线 - 并行版本
static long pi(long n) {
    return LongStream.rangeClosed(2, n)
            .parallel()
            .mapToObj(BigInteger::valueOf)
            .filter(i -> i.isProbablePrime(50))
            .count();
}
```

换说，并行化计算在我的四核机器上将速度提升了 3.7 倍。值得注意的是，在实践中，这*并不是*你计算大值 *n* 的 π(*n*)的方法。存在更高效的算法，特别是 Lehmer 公式。

如果你打算对随机数流进行并行化，请从`SplittableRandom`实例开始，而不是`ThreadLocalRandom`（或基本过时的`Random`）。`SplittableRandom`专为此用途而设计，并具有线性加速的潜力。`ThreadLocalRandom`设计用于单线程使用，它可以适应作为并行流源，但不会像`SplittableRandom`快。`Random`在每次操作上都会同步，因此会导致破坏并行性的过度竞争。

总之，除非你有充分理由相信它能保持计算的正确性并提高速度，否则甚至不要尝试对流流水线进行并行化。不当并行化流可能会导致程序失败或性能灾难。如果你认为并行化可能是合理的，请确保你的代码在并行运行时保持正确性，并在真实条件下进行仔细的性能测量。如果你的代码仍然保持正确，且这些实验证实了你对性能提升的疑虑，那么仅在此时才在生产代码中对流进行并行化。

# 第 8 章 方法

本章讨论了方法设计的几个方面：如何处理参数和返回值、如何设计方法签名，以及如何记录方法。本章的大部分内容适用于构造函数，也适用于方法。与第 4 章一样，本章关注可用性、健壮性和活性。

## Item 49：检查参数的有效性

大多数方法和构造函数对传入参数的值都有某些限制。例如，索引值必须是非负的，对象引用必须不能为空，这种情况并不罕见。你应该清晰地记录所有此类限制，并在方法开头强制执行。这是"应尽快检测错误"这一通用原则的特例。

如果向方法传递了无效值，且方法检查了其参数，它将快速且干净地抛出相应的异常并失败。如果方法没有检查参数，可能会发生几种情况：方法可能在处理过程中由于令人困惑的异常而失败；糟糕，方法可能正常返回但计算出错误结果；最糟糕的是，方法可能正常返回但让某些对象处于受损状态，导致代码中某个不确定的、无关点发生错误。换句话说，未验证参数可能导致*原子性失败*（Item 76）。

对于公共和保护方法，使用 Javadoc 的`@throws`标签来记录在违反限制时抛出的异常（Item 74）。通常，产生的异常将是`IllegalArgumentException`、`IndexOutOfBoundsException`或`NullPointerException`（Item 72）。一旦你记录了参数的限制并记录了违反这些限制时抛出的异常，执行这些限制就是件简单的事。这是一个典型的示例：

```java
/**
 * 返回值为 (this mod m) 的 BigInteger。此方法与 remainder 方法的区别在于
 * 它总是返回非负 BigInteger。
 *
 * @param m 模，必须为正
 * @return this mod m
 * @throws ArithmeticException 如果 m 小于等于 0
 */
public BigInteger mod(BigInteger m) {
    if (m.signum() <= 0) {
        throw new ArithmeticException("Modulus <= 0: " + m);
    }
    ... // 执行计算
}
```

注意，文档注释中并没有说"如果 m 为空，则 mod 会抛出`NullPointerException`"，尽管该方法由于调用`m.signum()`确实这样做。该异常已记录在闭包类`BigInteger`类的类级注释中。该类级注释适用于该类所有公共方法中的所有参数。这是避免在每个方法上单独记录每个`NullPointerException`导致杂乱的好方法。它可以结合`@Nullable`或类似注解的使用，以指示特定参数可以为空，但这种做法并不标准，且有多种注解用于此目的。

`Objects.requireNonNull`方法在 Java 7 中引入，既灵活又方便，因此没有理由继续手动进行空检查了。如果你愿意，可以指定自己的异常详细消息。该方法返回其输入值，因此你可以在使用值的同时进行空检查：

```java
// Java 空检查功能的内联使用
this.strategy = Objects.requireNonNull(strategy, "strategy");
```

你也可以忽略返回值，并在需要的地方将`Objects.requireNonNull`作为一个独立的空检查使用。

在 Java 9 中，`java.util.Objects`增加了范围检查功能。该功能由三个方法组成：`checkFromIndexSize`、`checkFromToIndex`和`checkIndex`。该功能没有空检查方法那么灵活。它不允许你指定自定义的异常详细消息，而且专门为用于列表和数组索引而设计。它不处理闭区间（即同时包含两个端点的区间）。但如果它能满足你的需求，它仍然是一个实用的便利工具。

对于未导出的方法，你作为包作者，控制了方法被调用的情况，因此你能够并且应该确保只传入有效的参数值。因此，非公共方法可以使用`assertions`（断言）来检查参数，如下所示：

```java
// 用于递归排序的私有辅助函数
private static void sort(long a[], int offset, int length) {
    assert a != null;
    assert offset >= 0 && offset <= a.length;
    assert length >= 0 && length <= a.length - offset;
    ... // 执行计算
}
```



本质上，这些断言是声明所断言的条件*将*为是真的，无论客户端如何使用封装它的包。与普通的有效性检查不同，断言在失败时会抛出`AssertionError`。而且与普通的有效性检查不同，除非你启用它们，否则它们没有任何作用且基本没有成本。你可以通过向`java`命令传递`-ea`（或`-enableassertions`）标志来启用它们。有关断言的更多信息，请参见教程 [Asserts]。

检查未被方法使用但存储以备后使用的参数的有效性尤为重要。例如，考虑第 101 页上的静态工厂方法，它接收一个`int`数组并返回数组的`List`视图。如果客户端传入`null`，方法将抛出`NullPointerException`，因为该方法有一个显式检查（对`Objects.requireNonNull`的调用）。如果省略了检查，方法将返回一个新创建的`List`实例引用，一旦客户端尝试使用它，该实例就会抛出`NullPointerException`。到那时，`List`实例的来源可能难以确定，这将极大地增加调试难度。

构造函数代表了该原则的一个特殊情况：你应该检查要存储后后使用的参数的有效性。检查构造函数参数的有效性至关重要，以防止构造违反其类不变性的对象。

在执行计算之前显式检查方法参数的规则是有例外的。一个重要的例外是：有效性检查开销高昂或不实际*且*该检查在计算过程中隐式执行了。例如，考虑一个排序对象列表的方法，如`Collections.sort(List)`。列表中的所有对象必须是相互可的。在排序列表的过程中，列表中的每个对象都会与列表中的其他对象进行比较。如果对象不是相互可比较的，这些比较中的某一个将抛出`ClassCastException`，这正是`sort`方法应该做的。因此，提前检查列表中的元素是否相互可比较的意义不大。但请注意，盲目依赖隐式有效性检查可能会导致丢失*失败原子性*（Item 76）。

偶尔，计算会隐式地执行所需的有效性检查，但在检查失败时抛出错误的异常。换句话说，计算因无效参数值而自然抛出的异常与方法文档说明中会抛出的异常不匹配。在这种情况下，你应该使用*异常翻译*（exception translation）惯用法（这在 Item 73 中描述），将自然异常翻译为正确的异常。

不要根据此章节推导出对参数的任意限制是好事。相反，你应该设计方法，使其在实际范围内尽可能通用。你对参数设置的限制越少越好，前提是方法对它接受的所有参数值都能执行合理的操作。然而，通常某些限制是所实现的抽象所固有的。

总结一下，每当你编写一个方法或构造函数时，都应该考虑其参数上存在哪些限制。你应该记录这些限制并在方法体的开头通过显式检查来强制执行它们。养成这种习惯很重要。当第一次有效性检查失败时，你付出的微小工作将获得丰倍回报。

## Item 50: 需要时进行防御性拷贝

让 Java 变得易用的特性之一是它是一种*安全语言*。这意味着在没有原生方法的情况下，它免受诸如 C 和 C++ 等不安全语言中常见的缓冲区溢出、数组越界、野指针和其他内存损坏错误的困扰。在安全语言中，可以编写类并确切知道它们的不变性将保持有效，无论系统的任何其他部分发生了什么。这在将所有内存视为一个巨型数组的语言中是不可能实现的。

即使在安全语言中，如果你不付出一些努力，也无法免受其他类的影响。**你必须进行防御性编程，假设你类的客户端会尽尽努力破坏它的不变性。**随着人们越来越尝试破解系统的安全性这变得越来越真实，但更常见的是，你的类必须处理由来自良好的程序员的无意错误导致的意外行为。无论何种情况，花时间编写在面对不良客户端时依然健壮的类都是值得的。

虽然另一个类在没有对象帮助的情况下无法修改对象的内部状态，但要提供这种帮助却异常地简单。例如，考虑以下类，它旨在表示一个不可变的时间段：

点击此处查看代码图片

```java
// 损坏的“不可变”时间类
public final class Period {

    private final Date start;

    private final Date end;

    /**
     * @param  start 时间段的开始
     * @param  end 时间段的结束；不能早于 start
     * @throws IllegalArgumentException 如果 start 在 end 之后
     * @throws NullPointerException 如果 start 或 end 为 null
     */
    public Period(Date start, Date end) {
        if (start.compareTo(end) > 0)
            throw new IllegalArgumentException(start + " after " + end);
        this.start = start;
        this.end = end;
    }

    public Date start() {
        return start;
    }

    public Date end() {
        return end;
    }

    ... // 略去剩余部分
}
```

乍一看，这个类似乎是不可变的，并且强制了“周期的开始时间不会在其结束时间之后”这一不变性。然而，利用`Date`是可变的这一事实，很容易违反这一不变性：

点击此处查看代码图片

```java
// 攻击 Period 实例的内部实现
Date start = new Date();
Date end = new Date();
Period p = new Period(start, end);
end.setYear(78);  // 修改了 p 的内部！
```

从 Java 8 开始，解决这个问题的明显方法是使用`Instant`（或`LocalDateTime`或`ZonedDateTime`）代替`Date`，因为`Instant`（以及其他的`java.time`类）是不可变的（项目 17）。`Date`已经过时，不应再在新代码中使用。尽管如此，问题仍然存在：某些时候，你必须在 API 和内部表示中使用可变值类型，而本项中讨论的技术在这些情况下是合适的。

为了保护`Period`实例的内部实现免受此类攻击，必须对构造函数的每个可变参数进行防御性拷贝，并使用副本作为`Period`实例的组件，而不是原始对象：

点击此处查看代码图片

```java
// 修复构造函数 - 对参数进行防御性拷贝
public Period(Date start, Date end) {
    this.start = new Date(start.getTime());
    this.end  = new Date(end.getTime());
    if (this.start.compareTo(this.end) > 0)
      throw new IllegalArgumentException(
          this.start + " after " + this.end);
}
```

有了新的构造函数，之前的攻击将对`Period`实例产生影响。注意，防御性拷贝是在检查参数有效性*之前*进行的（项目 49），并且有效性检查是在副本上执行而不是原始对象。虽然这看起来可能不自然，但它是必要的。它能保护类防止在参数检查和拷贝之间的时间漏洞窗口内，由另一个线程对参数进行修改。在计算机安全领域，这被称为*检查时间/使用时间*或 *TOCTOU* 攻击 [Viega01]。

同样注意，我们没有使用`Date`的`clone`方法来制作防御性拷贝。因为`Date`不是 final 类，`clone`方法不能保证返回一个类为`java.util.Date`的对象：它可能返回一个专门为恶意破坏而设计的不可信子类的实例。例如，此类子类可能会在创建时将每个实例的引用记录在一个私有的静态列表中，并允许攻击者访问该列表。这将允许攻击者对所有实例肆意妄为。为了防止此类攻击，不要使用`clone`方法对类型可被不可信第三方子类的参数进行防御性拷贝。

虽然替换后的构造函数成功防御了之前的攻击，但仍然可能修改`Period`实例，因为它的访问器提供了对其可变内部实现的访问：

点击此处查看代码图片

```java
// 对 Period 实例内部实现的第二次攻击
Date start = new Date();
Date end = new Date();
Period p = new Period(start, end);
p.end().setYear(78);  // 修改了 p 的内部！
```

为了防御第二次攻击，只需修改访问器，使其返回可变内部字段的防御性拷贝：

点击此处查看代码图片

```java
// 修复的访问器 - 对内部字段进行防御性拷贝
public Date start() {
    return new Date(start.getTime());
}

public Date end() {
    return new Date(end.getTime());
}
```

有了新的构造函数和新的访问器，`Period`是真正的不可变的。无论程序员多么恶意或无能，根本无法违反“周期的开始时间不会在其结束时间之后”这一不变性（除非诉诸原生方法和反射等语言外手段）。这是因为除了`Period`本身，没有任何类可以获取`Period`实例中任何一个可变字段的访问。这些字段被真正封装在对象内部。

在访问器中，与构造函数不同，允许使用`clone`方法制作防御性拷贝。这是因为我们知道`Period`内部`Date`对象的类是`java.util.Date`，而不是某些不可信的子类。尽管如此，通常情况下使用构造函数或静态工厂来拷贝实例会更好，原因如 项目 13 所示。

参数的防御性拷贝不仅用于不可变类。每当你编写一个方法或构造函数，将客户端提供的对象引用存储在内部数据结构中时，请考虑客户端提供的对象可能是可变的。如果是，请考虑你的类是否能够容忍该对象在进入数据结构后发生变化。如果答案是否定的，你必须对对象进行防御性拷贝，并将副本代替原始对象放入数据结构。例如，如果你正在考虑将客户端提供的对象引用作为内部`Set`实例的元素或内部`Map`实例的键，你应该意识到，如果对象在插入后被修改，集合或映射的不变性将被破坏。

在将内部组件返回给客户端之前，对其进行防御性拷贝也是如此。无论你的类是否不可变，在返回可变内部组件的引用之前，你应该仔细考虑。可能你应该返回一个防御性拷贝。记住，非零长度的数组总是可变的。因此，在将内部数组返回给客户端之前，你应该始终对其进行防御性拷贝。或者，你可以返回数组的不可变视图。这两种技术在 项目 15 中都有展示。

可以说，这一切中真正的教训是，在可能的情况下使用不可变对象作为你对象的组件，这样你就不必担心防御性拷贝了（项目 17）。在我们`Period`示例案例中，使用`Instant`（或`LocalDateTime`或`ZonedDateTime`），除非你使用的是 Java 8 之前的版本。如果你在使用更早的版本，一种方案是存储`Date.getTime()`返回的原始`long`值代替`Date`引用。

防御性拷贝可能会带来性能开销，并且并不总是合理的。如果一个类信任调用者不会修改其内部组件（可能因为该类和它的调用者都在同一个包中），那么放弃防御性拷贝可能是合适的。在这种情况下，类的文档应明确说明调用者不得修改受影响的参数或返回值。

即使跨包边界，在将可变参数集成到对象之前对其进行防御性拷贝也不总是合适的。某些方法和构造函数的调用表示对参数所引用对象的显式*移交*（handoff）。在调用此类方法时，客户端承诺不再直接修改该对象。期望获取客户端提供的可变对象所有权的方法或构造函数必须在文档中明确说明这一点。

包含方法或构造函数的类，如果其调用意味着控制权的转移，那么这些类无法防御恶意客户端。只有当类与其客户端之间存在互信，或者对类的不变量的破坏不会伤害任何人（仅伤害客户端）时，此类类才是接受的。后一种情况的例子是包装类模式（项 18）。取决于包装类的性质，客户端可能会在对象被包装后直接访问它，从而破坏类的不变量，但这通常只会损害客户端。

总之，如果一个类拥有它从客户端获取或返回给客户端的可变组件，那么该类必须对这些组件进行防御性拷贝。如果拷贝的成本无法接受，且该类信任客户端不会不当的修改这些组件，则可以用文档代替防御性拷贝，概述客户端有不修改受影响组件的责任。

## 项 51：严谨地设计方法签名

此项包含了许多 API 设计提示的杂锦，这些提示并不足以单独列为一项。将它们结合在一起，将帮助你的 API 更容易学习和使用，并且更不容易出错。

**仔细选择方法名。** 名称应始终遵循标准的命名约定（项 68）。你的首要目标应该是选择易于理解且与同一包内其他名称一致的名称。要目标应该是选择与更广泛的共识（如果存在）一致的名称。避免过长的方法名。如果不确定，可以参考 Java 库的 API 作为指导。虽然存在许多不一致之处——考虑到这些库的规模和范围，这是不可避免的——但也存在相当多的共识。

**不要过度提供便利方法。** 每一个方法都应该“物有所值”。过多的方法会让类难以学习、使用、文档化、测试和维护。对于接口来说更是如此，过多的方法会增加实现者和用户的负担。对于你的类或接口支持的每个操作，请提供一个功能完全的方法。只有当该方法会被频繁使用时，才考虑提供一个“简写”方法。**如果不确定，就省掉它。**

**避免过长的参数列表。** 目标是四个或更少的参数。大多数程序员无法记住更长的参数列表。如果你的许多方法超过了此限制，那么如果不经常参考文档，你的 API 将是不可使用的。现代 IDE 有助于此，但你使用短参数列表仍然会更好。**相同类型参数的长序列特别是有害的。** 用户不仅无法记住参数的顺序，而且当他们不小心调换参数时，他们的程序仍然会编译并运行，只是不会按照作者的意图执行。

缩短过长参数列表有三种技术。第一种是将方法拆分为多个方法，每个方法仅只需要参数的子集。如果处理得不小心，可能会导致方法过多，但它也可以通过增加正交性来帮助减少方法数量。例如，考虑`java.util.List`接口。它没有提供查找子列表中元素第一个或最后一个索引的方法，而这两者都需要三个参数。相反，它提供了`subList`方法，该方法接受两个参数并返回子列表的视图。该方法可以与`indexOf`或`lastIndexOf`方法结合使用（每个方法都只有一个参数），从而产生所需的功能。此外，`subList`方法可以与任何操作`List`实例的方法结合使用，以对子列表执行任意计算。生成的 API 具有很高的能效比。

缩短长参数列表的第二种技术是创建辅助类来持有一组参数。通常，这些辅助类是静态成员类（项 24）。如果发现频繁出现的参数序列代表某些特定的实体，则建议使用这种技术。例如，假设你正在编写代表纸牌游戏的类，你发现自己不断传递一个由两个参数组成的序列，分别代表牌的等级和花色。如果你添加一个辅助类来表示牌，并将参数序列的每次出现替换为该辅助类的单个参数，你的 API 以及类的内部实现可能都会受益。

第三种技术结合了前两种方法的特点，是将构造器模式（项 2）从对象构造适配到方法调用。如果你有一个有很多参数的方法，特别是当某些参数是可选的，那么定义一个表示所有参数的对象，并允许客户端对该对象进行多次“setter”调用是有益的，每次调用设置一个参数或一小组相关的参数。一旦设置了所需的参数，客户端就会调用对象的“execute”方法，该方法会对参数进行最终的有效性检查并执行实际计算。

**对于参数类型，优先使用接口而非类**（项 64）。如果有合适的接口来定义参数，请使用它而不是实现该接口的类。例如，没有理由编写一个接受`HashMap`作为输入的方法——使用`Map`。这允许你传入`HashMap`、`TreeMap`、`ConcurrentHashMap`、`TreeMap`的子映射或任何尚未编写的`Map`实现。通过使用类而不是接口，你限制了使用特定的实现，并且如果输入数据恰好以其他形式存在，就会强制执行不必要且可能昂贵的拷贝操作。

**用双元素枚举类型代替布尔参数**，除非布尔值的含义在方法名中很清晰。枚举让你的代码更易读、易写。而且，它们便于以后添加更多选项。例如，你可能有一个`Thermometer`类型，带有一个接收此枚举的静态工厂：

点击查看代码

```java
public enum TemperatureScale { FARENHEIT, CELSIUS }
```

`Thermometer.newInstance(TemperatureScale.CELSIUS)`比`Thermometer.newInstance(true)`有意义得多，而且你可以在未来的版本中向`TemperatureScale`添加`KELVIN`，而无需在`Thermometer`中添加新的静态工厂。此外，你可以将刻度依赖重构为枚举常量上的方法（项 34）。例如，每个刻度常量都可以有一个接收`double`值并将其转换为摄氏度的方法。

## 项 52：谨慎使用重载

以下程序是一个出于善的尝试，试图根据集合是集合、列表还是其他类型的集合对其进行分类：

点击查看代码

```java
// 坏了！——这个程序会打印什么？
public class CollectionClassifier {

    public static String classify(Set<?> s) {
        return "Set";
    }

    public static String classify(List<?> lst) {
        return "List";
    }

    public static String classify(Collection<?> c) {
        return "Unknown Collection";
    }
```



`public static void main(String[] args)` {

    `Collection<?>[] collections` = {

        `new HashSet<String>()`,

        `new ArrayList<BigInteger>()`,

        `new HashMap<String, String>().values()`

    };

    for (`Collection<?> c` : `collections`) {

        `System.out.println(classify(c))`;

    }

}

```

你可能期望此程序会打印 `Set`，然后是 `List` 和 `Unknown Collection`，但事实并非如此。它打印了三次 `Unknown Collection`。为什么会发生这种情况？因为 `classify` 方法是重载的，而调用哪一个重载版本是在编译时决定的。对于循环的全部三次迭代，参数的编译时类型都是相同的：`Collection<?>`。运行时类型在每次迭代中都是不同的，但这不会影响重载的选择。由于参数的编译时类型是 `Collection<?>`，唯一适用的重载是第三个 `classify(Collection<?>)`，并且该重载在循环的每次迭代中都被调用。

该程序的行为是违反直觉的，因为重载方法的选择是静态的，而重写方法的选择是动态的。重写方法的正确版本是在运行时根据调用方法的对象的运行时类型选择的。提醒一下，当子类包含一个与祖类中方法声明签名相同的方法时，该方法即为重写。如果实例方法在子类中被重写，并且在子类的实例上调用该方法，那么无论子类实例的编译时类型如何，执行的都是子类的重写方法。为了更具体化，请考虑以下程序：

```java
class Wine {

    String name() { return "wine"; }

}

class SparklingWine extends Wine {

    @Override String name() { return "sparkling wine"; }

}

class Champagne extends SparklingWine {

    @Override String name() { return "champagne"; }

}

public class Overriding {

    public static void main(String[] args) {

        List<Wine> wineList = List.of(

            new Wine(), new SparklingWine(), new Champagne());

        for (Wine wine : wineList)

            System.out.println(wine.name());

    }

}
```

`name` 方法在类 `Wine` 中声明，并在子类 `SparklingWine` 和 `Champagne` 中被重写。正如你预期的那样，该程序打印了 `wine`、`sparkling wine` 和 `champagne`，尽管实例的编译时类型是 `Wine`。在调用重写方法时，对象的编译时类型对执行哪个方法没有影响；执行的是“最具体”的重写方法。与之对比的是，在重载中，对象的运行时类型对执行哪个重载版本没有影响；选择是在编译时完全根据参数的编译时类型进行的。

在 `CollectionClassifier` 示例中，程序的意图是通过根据参数的运行时类型自动分发到适当的方法来识别参数的类型，正如 `name` 方法所做的那样。方法重载并没有提供这种功能。假设需要静态方法，修复 `CollectionClassifier` 最佳方法是将所有三个 `classify` 重载版本都替换为执行 `instanceof` 测试的单一方法：

```java
public static String classify(Collection<?> c) {

    return c instanceof Set ? "Set" : c instanceof List ? "List" : "Unknown Collection";

}
```

由于重写是常态而重载是例外，重写设定了人们对方法调用行为的预期。正如 `CollectionClassifier` 示例所示，重载很容易混淆这些预期。编写行为可能让程序员感到困惑的代码是一种坏习惯。这对于 API 尤为如此。如果 API 的典型用户不知道对于给定的参数集会调用多个重载中的哪一个，那么对 API 的使用可能会导致错误。这些错误可能会表现为运行时的无常行为，许多程序员将很难诊断它们。因此，你应该避免引起混淆的重载。

究竟什么构成了混淆的重载使用仍存在争议。一种安全、保守的策略是永远不要导出具有相同参数数量的两个重载。如果方法使用了 `varargs`，保守的策略是除非如第 53 条中所述，否则根本不要对其进行重载。如果你遵守这些限制，程序员永远不会对任何参数集适用于哪种重载产生疑问。这些限制并不困难，因为你总是可以给方法起不同的名称而不是使用重载。

例如，考虑 `ObjectOutputStream` 类。它对每种基本类型和几种引用类型都有 `write` 方法的变体。这些变体并没有重载 `write` 方法，而是使用了不同的名称，例如 `writeBoolean(boolean)`、`writeInt(int)` 和 `writeLong(long)`。与重载相比，这种命名模式的额外益处是可以提供具有相应名称的读取方法，例如 `readBoolean()`、`readInt()` 和 `readLong()`。`ObjectInputStream` 类确实提供了此类读取方法。

对于构造函数，你没有使用不同名称的选项：一个类的多个构造函数总是是重载的。在许多情况下，你有导出静态工厂方法而不是构造函数的选项（第 1 条）。此外，对于构造函数，你不需要担心重载和重写之间的交互，因为构造函数不能被重写。你可能会有机会导出具有相同参数数量的多个构造函数，因此了解如何安全地这样做是有价值的。

如果始终能够明确哪种重载适用于任何给定的实际参数集，那么导出具有相同参数数量的多个重载不太可能混淆程序员。当每对重载中至少有一个对应的参数在在两个重载中具有“截然不同”的类型时，情况就是如此。如果两种类型显然无法将任何非空表达式转换为这两种类型，那么这两种类型就是截然不同的。在这种情况下，哪种重载适用于给定的实际参数完全由参数的运行时类型决定，不受其编译时类型的影响，因此主要的混淆来源就消失了。例如，`ArrayList` 有一个接收 `int` 的构造函数和一个接收 `Collection` 的第二个构造函数。很难想象在任何情况下会对这两个构造函数中的哪一个调用产生混淆。

在 Java 5 之前，所有基本类型与所有引用类型都是截然不同的，但在存在自动装箱的情况下并非如此，这造成了真正的麻烦。考虑以下程序：

```java
public class SetList {

    public static void main(String[] args) {

        Set<Integer> set = new TreeSet<>();

        List<Integer> list = new ArrayList<>();

        for (int i = -3; i < 3; i++) {

            set.add(i);

            list.add(i);

        }

        for (int i = 0; i < 3; i++) {

            set.remove(i);

            list.remove(i);

        }

        System.out.println(set + " " + list);

    }

}
```

首先，程序将从 −3 到 2（包含边界）的整数添加到排序集合（`set`）和一个列表（`list`）中。然后，对集合和列表分别调用三次相同的 `remove` 方法。如果你像大多数人一样，你可能会认为程序会从集合和列表中移除非负值（0, 1 和 2），并打印出 `[-3, -2, -1] [-3, -2, -1]`。事实上，程序从集合中删除了非负值，从列表中删除了奇数，并打印出 `[-3, -2, -1] [-2, 0, 2]`。用“困惑”来形容这种行为都有些保守了。

以下是发生的情况：`set.remove(i)` 调用选取了重载方法 `remove(E)`，其中 `E` 是集合的元素类型（`Integer`），并将 `i` 从 `int` 自动装箱为 `Integer`。这是预期的行为，因此程序最终删除了集合中的正值。相反，`list.remove(i)` 调用选取了重载方法 `remove(int i)`，该方法移除列表中指定*位置*的元素。如果你从列表 `[-3, -2, -1, 0, 1, 2]` 开始，依次移除第零个、第一个和第二个元素，最后就会剩下 `[-2, 0, 2]`，谜随之解开了。要修复这个问题，可以将 `list.remove` 的参数强制转换为 `Integer`，从而强制选取正确的重载。或者，你也可以对 `i` 调用 `Integer.valueOf` 并结果传递给 `list.remove`。无论哪种方法，程序都会如预期般打印 `[-3, -2, -1] [-3, -2, -1]`：

```java
for (int i = 0; i < 3; i++) {

    set.remove(i);

    list.remove((Integer) i);  // 或 remove(Integer.valueOf(i))

}
```

前一个示例展示的困惑行为是因为 `List<E>` 接口的 `remove` 方法有两个重载：`remove(E)` 和 `remove(int)`。在 Java 5 引入泛型泛化 `List` 接口之前，它拥有一个 `remove(Object)` 方法来代替 `remove(E)`，且对应的参数类型 `Object` 和 `int` 有本质的区别。但在泛型和自动装箱存在的情况下，这两个参数类型不再有本质区别。换句话说，向语言中添加泛型和自动装箱损害了 `List` 接口。幸运的是，Java 库中几乎没有其他 API 受到类似的损害，但这个故事清楚地表明，自动装箱和泛型增加了重载时谨慎的重要性。

Java 8 中 Lambda 和方法引用的引入进一步增加了重载产生混淆的可能性。例如，考虑以下两个片段：

```java
new Thread(System.out::println).start();

ExecutorService exec = Executors.newCachedThreadPool();

exec.submit(System.out::println);
```

虽然 `Thread` 构造函数的调用和 `submit` 方法的调用看起来相似，但前者可以编译，而后者不能。它们的参数是相同的（`System.out::println`），且构造函数和方法都存在一个接受 `Runnable` 的重载。这里发生了什么？令人惊讶的答案是，`submit` 方法有一个接受 `Callable<T>` 的重载，而 `Thread` 构造函数没有。你可能认为这不产生任何影响，因为 `println` 的所有重载都返回 `void`，所以方法引用不可能是 `Callable`。这听起来完全合理，但并不是重载解析算法的工作方式。同样令人惊讶的是，如果 `println` 方法没有被重载，那么 `submit` 方法的调用将是合法的。正是被引用方法（`println`）和被调用方法（`submit`）的重载相结合，导致了重载解析算法无法以你预期的方式运行。

从技术上说，问题在于 `System.out::println` 是一个*不精确方法引用* [JLS, 15.13.1]，且“包含隐式类型 Lambda 表达式或不精确方法引用的某些参数表达式会被适用性测试忽略，因为在选择目标类型之前无法确定它们的含义 [JLS, 15.12.2]”。如果你不理解这段话，不要担心；它是写给编译器编写者的。关键点在于，在相同的参数位置使用不同的函数接口重载方法或构造函数会导致混淆。因此，**不要在相同的参数位置上重载方法以接受不同的函数接口。** 在本文项的术语中，不同的函数接口并没有本质区别。如果你传递命令行开关 `-Xlint:overloads`，Java 编译器会就此类问题的重载向你警告。

正如 `-Xlint:overloads` 所示，除 `Object` 之外的数组类型是有区别。此外，除 `Serializable` 和 `Cloneable` 之外的接口类型也有区别。如果两个不同的类互不为子类，则称它们是*不相关*的 [JLS, 5.5]。例如，`String` 和 `Throwable` 是不相关的。一个对象不可能是两个无关类的实例，因此不相关的类也存在本质区别。

还存在其他无法相互转换的类型对 [JLS, 5.1.12]，但一旦超出上述简单情况，大多数程序员就很难判断哪种重载适用。决定哪个重载的规则极其复杂，并随着版本的发布而变得更加复杂。很少程序员能理解所有的微妙之处。

有时你可能会觉得需要违反本文项的指南，特别是在扩展现有类时。例如，考虑 `String`，它从 Java 4 开始就有 `contentEquals(StringBuffer)` 方法。在 Java 5 中，引入了 `CharSequence` 为 `StringBuffer`、`StringBuilder`、`String`、`CharBuffer` 以及其他类型提供通用接口。在添加 `CharSequence` 的同时，`String` 也配备了接受 `CharSequence` 的 `contentEquals` 重载。

虽然这种重载显然违反了本文项的指南，但由于在同一个对象引用上调用时，两个重载的行为完全相同，因此没有害。程序员可能不知道会调用哪个重载，但只要它们行为一致，就无关了。确保这种行为的标准方法是让更具体的重载转发给更通用的重载：

```java
// 通过转发确保 2 个方法的行为一致

public boolean contentEquals(StringBuffer sb) {

    return contentEquals((CharSequence) sb);

}
```

虽然 Java 库在很大程度上遵循了本文项建议的精神，但许多类违反了它。例如，`String` 导出两个重载的静态工厂方法 `valueOf(char[])` 和 `valueOf(Object)`，当传递相同的对象引用时会执行完全不同的操作。这没有真正的理由，它应该被视为一个可能产生真实混淆的异常。

总而言之，仅仅因为你可以重载方法并不意味着你应该这样做。通常最好的做法是避免对具有相同参数数量的多个签名的方法进行重载。在某些情况下，特别是涉及构造函数时，可能无法遵循这一建议。在这种情况下，你至少应该避免通过添加类型转换将同一组参数传递给不同的重载版本。如果无法避免这种情况（例如，因为你正在重构现有类以实现新接口），那么你应该确保在传递相同参数时，所有重载方法的行为完全一致。如果你没有做到这一点，程序员将难以有效使用该重载方法或构造函数，并且他们不知道为什么它不起作用。

## 第 53 项：审慎使用变长参数

变长参数方法（正式称为 `variable arity` 方法 [JLS, 8.4.1]）接受零或多个指定类型的参数。变长参数机制的工作原理是：首先创建一个大小等于调用处传递的参数数量的数组，然后将参数值放入数组中，最后将数组传递给方法。

例如，这里有一个接收 `int` 参数序列并返回其和的变长参数方法。正如你预期的，`sum(1, 2, 3)` 的值为 `6`，而 `sum()` 的值为 `0`：

```java
// 变长参数的简单用法

static int sum(int... args) {

    int sum = 0;

    for (int arg : args)

        sum += arg;

    return sum;

}
```

有时，编写一个需要某个类型的`一个`或多个参数的方法比需要`零`或多个参数更合适。例如，假设你想写一个计算其参数最小值的函数。如果客户端没有传递任何参数，这个函数的定义就是模糊。你可以在运行时检查数组长度：

```java
// 使用变长参数传递一个或多个参数的错误方式！

static int min(int... args) {

    if (args.length == 0)

        throw new IllegalArgumentException("参数太少");

    int min = args[0];

    for (int i = 1; i < args.length; i++)

        if (args[i] < min)

            min = args[i];

    return min;

}
```

这种解决方案有几个问题。最严重的问题是，如果客户端不带参数调用此方法，它会在运行时失败而不是编译时失败。另一个问题是它很丑。你必须对 `args` 包含显式的有效性检查，除非你将 `min` 初始化为 `Integer.MAX_VALUE`，否则你无法使用 for-each 循环，这也很丑。

幸运的是，有更好的方法来实现所需的效果。声明该方法接收两个参数：一个指定类型的普通参数，另一个该类型的变长参数。这种解决方案纠正了之前方法的所有缺陷：

```java
// 使用变长参数传递一个或多个参数的正确方式
```



`static int min(int firstArg, int... remainingArgs) {`

```
int min = firstArg;

for (int arg : remainingArgs)

    if (arg < min)

        min = arg;

return min;
```

从这个示例中可以看出，当你需要一个具有可变参数的方法时，变长参数是有效的。变长参数是为`printf`设计的（它是与变长参数同时加入平台的），并为核心反射机制（Item 65）设计的（它是重构的）。`printf`和反射都从变长参数中获益匪浅。

在性能敏感的情况下使用变长参数时要小心。每次调用变长参数方法都会导致数组的分配和初始化。如果你通过经验确定无法承担这种成本，但又需要变长参数的灵活性，那么有一种模式可以让你兼得。假设你确定对某个方法的 95% 的调用具有三个或更少的参数。那么就为该方法声明五个重载版本，每个版本分别带有零到三个普通参数，并带有一个变长参数方法，用于参数数量超过三个的情况：

```java
public void foo() { }
public void foo(int a1) { }
public void foo(int a1, int a2) { }
public void foo(int a1, int a2, int a3) { }
public void foo(int a1, int a2, int a3, int... rest) { }
```

现在你知道只有当参数数量超过三个时才会支付创建数组的成本。像大多数优化技术一样，这种技术通常并不适用，但在适用时，它是救命稻星。

总而言之，当你需要定义具有可变参数的方法时，变长参数是无价的。在变长参数之前放置任何必需的参数，并注意使用变长参数的性能后果。

## 第 54 项：返回空集合或数组，而不是 null

看到像这样的方法并不罕见：

```java
// 返回 null 表示空集合。不要这样做！
private final List<Cheese> cheesesInStock = ...;

/**
 * @return 包含所有奶酪的列表，
 * 如果没有可用奶酪则返回 null。
 */
public List<Cheese> getCheeses() {
    return cheesesInStock.isEmpty() ? null : new ArrayList<>(cheesesInStock);
}
```

没有理由在没有可用奶酪的情况下进行特殊处理。这样做需要客户端编写额外的代码来处理可能为 null 值，例如：

```java
List<Cheese> cheeses = shop.getCheeses();
if (cheeses != null && cheeses.contains(Cheese.STILTON))
    System.out.println("太棒了，正需要的。");
```

几乎每次使用返回`null`代替空集合或数组的方法时都需要这种绕弯写法。这是容易出错的，因为编写客户端的程序员可能会忘记编写处理`null`返回值的特殊处理代码。这种错误可能多年都不会被察觉，因为此类方法通常返回一个或多个对象。此外，返回`null`代替容器会增加返回容器方法的实现复杂度。

有时认为，返回`null`值比空集合或数组更好，因为避免了分配空容器的开销。这个论点在两个方面都失败了。首先，除非测量结果显示该分配是性能问题的实际贡献因素（Item 67），否则在这一层级担心性能是不理想的。其次，*确实*可以在不分配它们的情况下返回空集合和数组。这里是返回可能的空集合的典型代码。通常，你只需要这些：

```java
// 返回可能的空集合的正确 方式
public List<Cheese> getCheeses() {
    return new ArrayList<>(cheesesInStock);
}
```

在极少数情况下，如果你有证据表明分配空集合会损害性能，你可以通过反复返回相同的不可变空集合来避免这些分配，因为不可变对象可以自由共享 (Item 17)）。这里是使用`Collections.emptyList`方法实现该操作的代码。如果你返回的是集合，则应使用`Collections.emptySet`；如果你返回的是映射，则使用`Collections.emptyMap`。但记住，这是一种优化，而且很少需要。如果你认为自己需要，请在操作前后分别测量性能，以确保它确实起了作用：

```java
// Optimization - avoids allocating empty collections
public List<Cheese> getCheeses() {
    return cheesesInStock.isEmpty() ? Collections.emptyList()
        : new ArrayList<>(cheesesInStock);
}
```

数组的情况与集合相同。**永远不要返回`null`而不是零长度数组**。通常，你应该直接返回一个长度正确的数组，长度可以为零。注意，我们是将一个零长度数组传递到`toArray`方法中，以指示预期的返回类型为`Cheese[]`：

```java
// The right way to return a possibly empty array
public Cheese[] getCheeses() {
    return cheesesInStock.toArray(new Cheese[0]);
}
```

如果你认为分配零长度数组会损害性能，你可以反复返回相同的零长度数组，因为所有零长度数组都是不可变的：

```java
// Optimization - avoids allocating empty arrays
private static final Cheese[] EMPTY_CHEESE_ARRAY = new Cheese[0];

public Cheese[] getCheeses() {
    return cheesesInStock.toArray(EMPTY_CHEESE_ARRAY);
}
```

在优化后的版本中，我们将相同的空数组传递到每次`toArray`调用，每当`cheesesInStock`为空时，`getCheeses`就会返回这个数组。**不要为了提高性能而预先分配传递给`toArray`的数组**。研究表明这样做往往适得其反 [Shipilëv16]：

```java
// Don’t do this - preallocating the array harms performance!
return cheesesInStock.toArray(new Cheese[cheesesInStock.size()]);
```

总之，**永远不要用`null`代替空数组或集合**。这会让你的 API 变得更难用且更容易出错，而且没有任何性能优势。

## 第 55 条：审慎地返回 Optional

在 Java 8 之前，当你编写一个在某些情况下无法返回值的方法时，有两种方法可以采取。要么你可以抛出一个异常，要么你可以返回`null`（假设返回类型是对象引用类型）。这两种方法都不是完美的。异常应该只留给异常情况 (Item 69)，而且抛出异常是有开销的，因为在创建异常时会捕获整个堆栈轨迹信息。返回`null`虽然没有这些缺点，但它也有自己的问题。如果一个方法返回`null`，客户端必须包含特殊情况代码来处理返回`null`的可能性，除非程序员能够证明返回`null`是可能的。如果客户端忽略了对`null`的检查并将`null`值存储在某些数据结构中，可能会在未来的某个时刻、代码的某个任意位置导致`NullPointerException`，而那个地方与问题本身无关。

在 Java 8 中，编写可能无法返回值的方法有第三种方法。`Optional<T>`类表示一个不可变的容器，它可以包含一个单个非空`T`引用，也可以什么都不包含。不包含任何内容的`Optional`被称为*空的*（empty）。在非空的`Optional`中包含值，则称该值是*存在的*（present）。`Optional`本质上是一个最多包含一个元素的不可变集合。`Optional<T>`没有实现`Collection<T>`，但原则上它可以实现。

一个在概念上返回`T`但在某些情况下可能无法返回的方法，可以声明为返回`Optional<T>`。这允许方法返回一个空结果，表示它无法返回有效结果。一个返回`Optional`的方法比抛出异常的方法更灵活且易于使用，并且比返回`null`的方法更不容易出错。

在 Item 30 中，我们展示了这种根据元素自然顺序计算集合中最大值的方法。

```java
// Returns maximum value in collection - throws exception if empty
public static <E extends Comparable<E>> E max(Collection<E> c) {
    if (c.isEmpty())
        throw new IllegalArgumentException("Empty collection");

    E result = null;
    for (E e : c)
        if (result == null || e.compareTo(result) > 0)
            result = Objects.requireNonNull(e);

    return result;
}
```

如果给定的集合为空，该方法会抛出一个`IllegalArgumentException`。我们在 Item 30 中提到过，更好的替代方案是返回`Optional<E>`。当方法修改为这样做时，看起来如下：

```java
// Returns maximum value in collection as Optional<E>
public static <E extends Comparable<E>>
    Optional<E> max(Collection<E> c) {
    if (c.isEmpty())
        return Optional.empty();

    E result = null;
    for (E e : c)
        if (result == null || e.compareTo(result) > 0)
            result = Objects.requireNonNull(e);

    return Optional.of(result);
}
```

你可以看到，返回`Optional`是很简单的。你只需要使用适当的静态工厂创建`Optional`。在这个程序中我们使用了两个：`Optional.empty()`返回一个空的`Optional`，而`Optional.of(value)`返回一个包含给定非空值的`Optional`。将`null`传递给`Optional.of`是编程错误。如果你这样做，方法将通过抛出`NullPointerException`来响应。`Optional.ofNullable(value)`方法接受可能为空的值，如果传入`null`则返回空的 Optional。**不要从返回 Optional 的方法返回 null 值**：这违背了该便利方法的全部意义。

流的许多终端操作都返回`Optional`。如果我们使用流重写`max`方法，`Stream`的`max`操作会为我们生成`Optional`（尽管我们必须显式传递比较器）：

```java
// Returns max value in collection as Optional<E> - uses stream
public static <E extends Comparable<E>>
    Optional<E> max(Collection<E> c) {
    return c.stream().max(Comparator.naturalOrder());
}
```

那么，如何选择返回`Optional`而不是返回`null`或抛出异常？**Optional 在精神上与检查异常相似** (Item 71)，它们*强制* API 使用者面对可能没有返回值的事实。抛出未检查异常或返回`null`允许用户忽略这种可能性，可能会导致严重的后果。然而，抛出检查异常需要在客户端编写额外的模板板代码。

如果方法返回`Optional`，客户端可以自己在方法无法返回值时采取何种行动。你可以指定一个默认值：

```java
// Using an optional to provide a chosen default value
String lastWordInLexicon = max(words).orElse("No words...");
```

或者你可以抛出任何合适的异常。注意，我们传入的是一个异常工厂而不是实际的异常实例。这避免了在异常实际被抛出之前产生创建异常的开销：

```java
// 使用 optional 抛出指定的异常
Toy myToy = max(toys).orElseThrow(TemperTantrumException::new);
```

如果你能`证明`一个`optional`是非空的，你就可以从`optional`中获取值，而无需指定当`optional`为空时要执行的操作；但如果你判断错了，你的代码将抛出`NoSuchElementException`：

```java
// 在确定有返回值时使用 optional
Element lastNobleGas = max(Elements.NOBLE_GASES).get();
```

偶尔，你可能会遇到获取默认值的开销很高的情况，你希望在非必要时避免这种开销。对于这些情况，`Optional`提供了一个接受`Supplier<T>`并在仅在需要时调用它的方法。该方法被称为`orElseGet`，但或许它应该被称为`orElseCompute`，因为它与三个以`compute`开头的`Map`方法密切相关。`Optional`还有其他几个方法用于处理更具特定针对性的用例：`filter`、`map`、`flatMap`和`ifPresent`。在 Java 9 中，又增加了两个方法：`or`和`ifPresentOrElse`。如果上述描述的基础方法不符合你的用例，请查看这些更高级方法的文档，看看它们是否能完成任务。

如果所有这些方法都不能满足你的需求，`Optional`提供了`isPresent()`方法，这可以被视为一个安全阀。如果`optional`包含一个值，则返回`true`；如果为空则返回`false`。你可以使用此方法对`optional`结果进行任何需要的处理，但请务必理智使用。`isPresent`的许多用法可以有效地替换为上述提到的方法之一。生成的代码通常会更短、更清晰且更符合习惯。

例如，考虑这段代码片段，它打印父进程的进程 ID，如果进程没有父进程则打印`N/A`。该片段使用了 Java 9 中引入的`ProcessHandle`类：

```java
Optional<ProcessHandle> parentProcess = ph.parent();
System.out.println("Parent PID: " + (parentProcess.isPresent() ?
    String.valueOf(parentProcess.get().pid()) : "N/A"));
```

上面的代码片段可以用下面这段替换，它使用了`Optional`的`map`函数：

```java
System.out.println("Parent PID: " +
  ph.parent().map(h -> String.valueOf(h.pid())).orElse("N/A"));
```

在用流（streams）编程时，发现自己拥有一个`Stream<Optional<T>>`并需要一个包含所有非空`optional`中元素的`Stream<T>`以继续操作，并不罕见。如果你在使用 Java 8，可以这样弥补这一差距：

```java
streamOfOptionals
    .filter(Optional::isPresent)
    .map(Optional::get)
```

在 Java 9 中，`Optional`被备了`stream()`方法。该方法是一个适配器，如果`optional`中存在元素，它将其转换为一个包含该元素的`Stream`；如果为空，则返回一个空流。结合`Stream`的`flatMap`方法（项目 45），该方法为上述代码片段提供了简洁的替换：

```java
streamOfOptionals.
    .flatMap(Optional::stream)
```



并不是所有的返回类型都能从 `optional` 处理中受益。**容器类型，包括集合、映射、流、数组和 `optional` 不应该被包装在 `optional` 中。** 与其返回一个空的 `Optional<List<T>>`，你应该直接返回一个空的 `List<T>`（项目 54）。返回空容器将消除客户端代码处理 `optional` 的需要。`ProcessHandle` 类确实有 `arguments` 方法，它返回 `Optional<String[]>`，但此方法应该被视为一种不应模仿的异常情况。

那么，什么时候应该声明一个返回 `Optional<T>` 而不是 `T` 的方法？根据原则，**如果一个方法可能无法返回结果，并且客户端在没有返回结果时必须进行特殊处理，你就应该声明该方法返回 `Optional<T>`。** 尽管如此，返回 `Optional<T>` 并不是免费的。`Optional` 是一个必须分配并初始化的对象，且从 `optional` 中读取值需要额外的间接层。这使得 `optional` 不适用于某些对性能敏感的场景。某个特定方法是否属于此类，只能通过仔细的测量来确定（项目 67）。

与返回原始类型相比，返回一个包含包装原始类型的 `optional` 代价极其昂贵，因为 `optional` 有两层装箱而不是零层。因此，库的设计者认为有为原始类型 `int`、`long` 和 `double` 提供 `Optional<T>` 的对应物。这些可选类型是 `OptionalInt`、`OptionalLong` 和 `OptionalDouble`。它们包含了 `Optional<T>` 的大部分但并非所有的方法。

返回一个包含包装原始类型的 `optional` 与返回原始类型相比是昂贵得难以接受的，因为 `optional` 有两层装箱而不是零层。除非是 `Boolean`、`Byte`、`Character`、`Short` 和 `Float`。

到目前为止，我们讨论了返回 `optional` 以及在返回后对其处理。我们还没有讨论其他用法，这是因为大多数 `optional` 的其他用法都是可疑的。例如，你不应该将 `optional` 作为映射的值。如果你这样做，你有两种方式来表示键的逻辑缺失：键不存在于映射中，或者键存在但映射到一个空的 `optional`。这代表了不必要的复杂性并可能引发错误。更广泛地说，**几乎永远不应该在键、值或集合或数组元素中使用 `optional`。**

这留下了一个未解决的大问题。在实例字段中存储 `optional` 是否合适？通常这是一种“异味”：暗示你应该有一个包含可选字段的子类。但有时这是合理的。考虑我们在项目 2 中的 `NutritionFacts` 类。一个 `NutritionFacts` 实例包含许多并非必需的字段。你无法为这些字段的每种组合创建一个子类。此外，字段是原始类型，这使得直接表示缺失变得很别扭。`NutritionFacts` 的最佳 API 是每个可选字段的 getter 返回一个 `optional`，因此将这些 `optional` 直接存储在对象的字段中是有意义的。

总结，如果你发现自己正在编写一个不能总是返回值的方法，并且你认为用户每次调用该方法时都应该考虑这种可能性，那么你应该返回一个 `optional`。然而，你应该意识到返回 `optional` 存在着真实的性能代价；对于性能关键型方法，返回 `null` 或抛出异常可能更好。最后，你不应该在返回值之外的任何地方使用 `optional`。

虽然文档注释规范并不是语言正式的一部分，但它们构成了每个 Java 程序员都应该知道的事实 API。这些规范在《如何编写文档注释》网页页面 [Javadoc-guide] 中进行了描述。尽管该页面自 Java 4 发布以来再未更新过，但它仍然是一份极具价值的资源。Java 9 添加了一个重要的文档标签 `{@index}`；Java 8 添加了一个 `{@implSpec}`；Java 5 添加了两个 `{@literal}` 和 `{@code}`。这些标签在上述网页中并未提及，但在本文中对其进行了讨论。

### 正确地记录你的 API

为了正确记录你的 API，你必须在每个导出的类、接口、构造函数、方法和字段声明之前加上文档注释。如果一个类是可序列化的，你还应该记录其序列化形式（第 87 项）。在缺少文档注释的情况下，Javadoc 能做的最好就是将声明复现作为受影响的 API 元素的唯一文档。使用缺少文档注释的 API 是令人沮丧且容易出错的。公共类不应使用默认构造函数，因为没有办法为它们提供文档注释。为了编写可维护的代码，你还应该为大多数未导出的类、接口、构造函数、方法和字段编写文档注释，尽管这些注释不需要像导出的 API 元素那样详尽。

### 方法文档注释

方法的文档注释应该简明地描述方法与其客户端之间的约定。除了为继承而设计的类中的方法（第 19 项）外，约定应该说明方法做了*什么*，而不是它是*如何*执行任务的。文档注释应该列出方法所有的*前置条件*（preconditions），即客户端调用它时必须满足的条件；以及*后置条件*（postconditions），即在调用成功完成后将满足的条件。通常，前置条件通过未检查异常的 `@throws` 标签隐式地描述；每个未检查异常都对应一个前置条件的违反。此外，也可以在 `@param` 标签中结合受影响的参数一起指定前置条件。

除了前置条件和后置条件，方法还应该记录任何*副作用*。副作用是指系统状态的一种可观测变化，且这种变化并不是实现后置条件所明显需要的。例如，如果一个方法启动了后台线程，文档应该对此注明。

为了完全描述方法的约定，文档注释应为每个参数提供一个 `@param` 标签，除非方法的返回类型为 `void`，否则提供一个 `@return` 标签，并为方法抛出的每个异常（无论是受检查还是未检查的，第 74 项）标记。如果 `@return` 标签中的文本与方法的描述相同，根据你所遵循的编码标准，允许省略它。

按照习惯，`@param` 或 `@return` 标签后的文本应该是描述参数或返回值所代表的值的名词短语。极少使用算术表达式代替名词短语；示例请参见 `BigInteger`。`@throws` 标签后的文本应包含单词“if”，后跟描述触发异常条件的从句。按照习惯，`@param`、`@return` 或 `@throws` 标签后的短语或从句不以句号结束。以下文档注释说明了所有规范：

```java
/**
 * 返回此列表中指定位置的元素。
 *
 * <p>此方法不保证以常数
 * 时间运行。在某些实现中，它的运行时间可能与
 * 元素的位置成比例。
 *
 * @param  index 要返回的元素的索引；必须是
 *         非负且小于此列表的大小
 * @return 此列表中指定位置的元素
 * @throws IndexOutOfBoundsException 如果索引超出范围
 *          ({code index < 0 || index >= this.size()})
 */
E get(int index);
```

注意此文档注释中使用的 HTML 标签（`<p>` 和 `<i>`）。Javadoc 实用程序将文档注释转换为 HTML，而文档注释中的任意 HTML 元素最终将出现在生成的 HTML 文档中。偶尔，程序员们甚至会在文档注释中嵌入 HTML 表格，尽管这种情况很罕见。

同样注意在 `@throws` 子句的代码片段周围使用了 Javadoc 的 `{@code}` 标签。该标签有两个作用：它使代码片段以代码字体渲染，并抑制对代码片段中 HTML 标记和嵌套的 Javadoc 标签的处理。后者的属性使我们能够在代码片段中使用小于号（`<`），尽管它是一个 HTML 元字符。若要在文档注释中包含多行代码示例，请使用封装在 HTML `<pre>` 标签内的 Javadoc `{@code}` 标签。换句话说，代码示例之前使用字符 `<pre>{@code`，之后使用 `}</pre>`。这保留了代码中的换行，并消除了转义 HTML 元字符的需求，但不能转义 @ 符号（`@`），如果代码示例使用了注解，则必须转义该符号。

最后，注意文档注释中使用“this list”一词的情况。按照习惯，“this”指的是调用该方法的对象。

### 继承与 implSpec

如第 15 项所示，当你为继承设计一个类时，你必须记录其自使用模式（self-use patterns），以便程序员知道重写其方法的语义。这些自使用模式应该使用 Java 8 添加的 `@implSpec` 标签进行记录。记住，普通的文档注释描述方法与客户端之间的约定；相比之下，`@implSpec` 注释描述方法与子类之间的约定，允许子类在继承方法或通过 `super` 调用它时依赖该实现。它在实际应用中的效果如下：

```java
/**
 * 如果集合为空，则返回 true。
 *
 * @implSpec
 * 此实现返回 {@code size() == 0}。
 *
 * @return 如果集合为空则返回 true
 */
public boolean isEmpty() { ... }
```

截至 Java 9，Javadoc 实用程序仍然忽略 `@implSpec` 标签，除非你传递命令行开关 `-tag "implSpec:a:Implementation Requirements:"`。希望这会在后续版本中得到解决。

不要忘记，为了生成包含 HTML 元字符的文档必须采取特殊操作，例如小于号（`<`）、大于号（`>`）和和符号（`&`）。将这些字符引入文档的最佳方法是将它们放在 `{@literal}` 标签中，该标签会抑制对 HTML 标记和嵌套 Javadoc 标签的处理。它类似于 `{@code}` 标签，区别在于不会以代码字体渲染文本。例如，此 Javadoc 片段：

```java
* 如果 {@literal |r| < 1} 则几何级数收敛。
```

将生成文档：“A geometric series converges if |r| < 1.”

每个文档注释（下文定义）的第一个“句子”将成为该注释所指元素的*摘要描述*（summary description）。例如，第 255 页文档注释中的摘要描述是“返回此列表中指定位置的元素。”摘要描述必须能够独立地描述其所总结的元素的功能。为了避免混淆，**类或接口中的任何两个成员或构造函数都不应具有相同的摘要描述。** 请特别注意重载方法，对于重载方法，使用相同的第一个句子往往是理所当然的（但在文档注释中是不可接受的）。

如果预期的摘要描述包含句号，请务必小心，因为句号可能会提前终止描述。例如，一个以“`A college degree, such as B.S., M.S. or Ph.D.`”这句话开头的文档注释将导致摘要描述变为“A college degree, such as B.S., M.S.”。问题在于，摘要描述会在第一个后面跟着空格、制表符或换行符的句号（或第一个块级标签）处结束 [Javadoc-ref]。在这里，缩写 `M.S.` 中的第二个句号后面跟着一个空格。最佳解决方案是将引起问题的句号和任何相关文本用 `{@literal}` 标签括起来，这样源代码中的句号后面就不再有空格了：

```java
/**
 * A college degree, such as B.S., {@literal M.S.} or Ph.D.
 */
public class Degree { ... }
```

说摘要描述是文档注释中的第一个*句子*有点误导性。按照惯例，它很少应该是一个完整的句子。对于方法和构造函数，摘要描述应该是一个描述方法所执行操作的动词短语（包括任何对象）。例如：

* `ArrayList(int initialCapacity)`—构造一个具有指定初始容量的空列表。
* `Collection.size()`—返回此集合中元素的数量。

如这些示例所示，请使用第三人称陈述句时态（如“returns the number”），而不是第二人称祈使句（“return the number”）。

对于类、接口和字段，摘要描述应该是一个名词短语，用于描述类或接口实例或字段本身所表示的事物。例如：

* `Instant`—时间线上的瞬时点。
* `Math.PI`—比任何其他值都接近 pi 的 `double` 值，即圆周长与直径的比率。

在 Java 9 中，Javadoc 生成的 HTML 增加了一个客户端索引。该索引便于在大型 API 文档集之间进行导航，其形式为页面右上角的搜索框。当你向框中输入内容时，你会得到匹配页面的下拉菜单。API 元素（如类、方法和字段）会自动建立索引。有时，你可能希望索引对你的 API 重要的额外术语。为此目的增加了 `{@index}` 标签。索引文档注释中出现的术语只需将其封装在该标签中即可，如该代码片段所示：

```java
* This method complies with the {@index IEEE 754} standard.
```

泛型、枚举和注解在文档注释中需要特别 care。**在记录泛型类型或方法时，请务必记录所有的类型参数：**

```java
/**
 * An object that maps keys to values.  A map cannot contain
 * duplicate keys; each key can map to at most one value.
 *
 * (Remainder omitted)
 *
 * @param <K>此 map 维护的键的类型
 * @param <V> 映射值的类型
 */
public interface Map<K, V> { ... }
```

**在记录枚举类型时，请务必记录常量**以及该类型和任何公共方法。注意，如果文档注释很短，你可以将整个文档注释放在一行上：

```java
/**
 * An instrument section of a symphony orchestra.
 */
public enum OrchestraSection {
    /** Woodwinds, such as flute, clarinet, and oboe. */
    WOODWIND,

    /** Brass instruments, such as french horn and trumpet. */
    BRASS,

    /** Percussion instruments, such as timpani and cymbals. */
    PERCUSSION,

    /** Stringed instruments, such as violin and cello. */
    STRING;
}
```

**在记录注解类型时，请务必记录任何成员**以及类型本身。使用名词短语来记录成员，就像它们是字段一样。对于类型的摘要描述，使用动词短语来说明当程序元素具有此类型的注解时意味着什么：

```java
/**
 * Indicates that the annotated method is a test method that
 * must throw the designated exception to pass.
 */
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface ExceptionTest {
    /**
     * 测试方法必须抛出的异常
     * (允许测试抛出该类对象的任何子类。)
     */
    Class<? extends Throwable> value();
}
```



包级文档注释应该放置在名为`package-info.java`的文件中。除了这些注释外，`package-info.java`必须包含包声明并可以包含该声明的注解。同样，如果你选择使用模块系统（Item 15），模块级注释应该放置在`module-info.java`文件中。

API 文档中经常被忽略的两个方面是线程安全和序列化。无论类或静态方法是否是线程安全的，你都应该记录其线程安全级别，如 Item 82 所示。如果一个类是可序列化的，你应该记录其序列化形式，如 Item 87 所示。

Javadoc 具有“继承”方法注释的能力。如果 API 元素没有文档注释，Javadoc 会搜索最具体的可用文档注释，其中接口优于超类。搜索算法的细节可以在*The Javadoc Reference Guide* [Javadoc-ref] 中找到。你也可以使用`{@inheritDoc}`标签从父类型继承文档注释的*部分*。这意味着，类可以重用它们实现的接口的文档注释，而不是复制这些注释。此功能具有减少维护多组几乎相同的文档注释负担的潜力，但使用起来很复杂且具有某些局限性。细节超出了本书的范围。

Javadoc 会自动检查是否符合本项目中的许多建议。在 Java 7 中，需要使用命令行开关`-Xdoclint`才能获得此行为。在 Java 8 和 9 中，检查是默认开启的。如`checkstyle`等 IDE 插件会进一步检查对这些建议的遵循情况 [Burn01]。你还可以通过让 Javadoc 生成的 HTML 文件通过`HTML 有效检查器`来减少文档注释出现错误的概率。这可以检测到许多错误的 HTML 标签。有多种此类检查器可以下载，你可以使用 W3C 标记验证服务 [W3C-validator] 在网页上验证 HTML。在验证生成的 HTML 时，请记住从 Java 9 开始，Javadoc 能够生成 HTML5 以及 HTML 4.01，尽管它仍然默认生成 HTML 4.01。如果你想让 Javadoc 生成 HTML5，请使用`-html5`命令行开关。

本项目描述的约定涵盖了基础内容。尽管在写本文时，该指南已存在十五年，但编写文档注释的权威指南仍然是*How to Write Doc Comments* [Javadoc-guide]。

如果你遵循本项目中的指南，生成的文档应该对你的 API 提供清晰的描述。然而，唯一能够完全确定的方法是阅读 Javadoc 工具生成的网页。对于每个会被他人使用的 API，这样做都是值得的。正如测试程序几乎不可避免地会导致代码发生某些变化一样，阅读文档通常会导致文档注释至少发生几次微调。

总结来说，文档注释是记录 API 的最佳、最有效的方法。对于所有导出的 API 元素，应将它们的使用视为强制性的。采用符合标准惯定的一致风格。请记住，文档注释中允许任意 HTML，且 HTML 元字符必须经过转义。

## 第 9 章 通用编程

本章致力于语言的细节要点。它讨论了局部变量、控制结构、库、数据类型以及两个语言外设施：*反射*和*原生方法*。最后，它讨论了优化和命名约定。

### 第 57 项：最小化局部变量的作用范围

本项目的性质与 Item 15 “最小化类和成员的访问权限”相似。通过最小化局部变量的作用范围，你增加了代码的可读性和可维护性，并减少了错误的概率。

旧的编程语言（如 C）规定局部变量必须在块的头部声明，某些程序员出于习惯继续这样做。这是一个值得打破的习惯。作为一个温和的提醒，Java 允许你在任何合法语句的地方声明变量（C 语言也是如此，从 C99 开始）。

**最小化局部变量作用范围最强大的技术是在首次使用它的地方对其进行声明。** 如果一个变量在使用之前就声明了，那么它就是多余的——这会让试图弄清楚程序功能的读者又分心精力。等到变量被使用时，读者可能已经忘记了变量的类型或初始值。

过早声明局部变量可能会导致其作用范围不仅开始得太早，而且结束得太晚。局部变量的作用范围从声明点一直延伸到闭闭块的结束。如果变量在它使用的块之外声明，那么在程序退出该块后它仍然是可见的。如果变量在预定使用区域之前或之后意外使用，后果可能是灾难性的。

**几乎每个局部变量声明都应该包含一个初始化器。** 如果你还没有足够的信息来合理地初始化变量，你应该推迟声明，直到你有这些信息。该规则的一个例外是`try-catch`语句。如果一个变量初始化为一个求值可能抛出检查异常的表达式，则该变量必须在`try`块内部初始化（除非包含的方法可以传播异常）。如果该值必须在`try`块之外使用，那么它必须在`try`块之前声明，而在那里还无法被“合理地初始化”。示例请参见第 283 页。

循环为最小化变量的作用范围提供了特殊机会。`for`循环（无论是传统形式还是 for-each 形式）允许你声明*循环变量*，将其作用范围限制在所需的确切区域。（该区域包括循环体以及`for`关键字与循环体之间括号内的代码）。因此，假设循环变量的内容在循环结束后不再需要，**优先使用`for`循环而不是`while`循环**。

例如，这里是遍历集合的首选惯用 (Item 58)：

```java
// 遍历集合或数组的首选惯用
for (Element e : c) {
    ... // 对 e 执行某些操作
}
```

如果你需要访问迭代器（例如调用它的`remove`方法），首选的惯用是用传统的`for`循环来代替 for-each 循环：

```java
// 需要迭代器时的遍历惯用
for (Iterator<Element> i = c.iterator(); i.hasNext(); ) {
    Element e = i.next();
    ... // 对 e 和 i 执行某些操作
}
```

为了了解为什么这些`for`循环比`while`循环更好，请考虑以下代码片段，它包含两个`while`循环和一个 bug：

```java
Iterator<Element> i = c.iterator();
while (i.hasNext()) {
    doSomething(i.next());
}
...
Iterator<Element> i2 = c2.iterator();
while (i.hasNext()) {              // 错误！
    doSomethingElse(i2.next());
}
```

第二个循环包含一个复制错误：它初始化了一个新的循环变量`i2`，但使用了旧的变量`i`，不幸的是，`i`仍在作用范围内。生成的代码可以通过编译且不会抛出异常，但它执行的是错误的。它没有遍历`c2`，而是立即终止，给出一个`c2`是空的假象。由于程序静默报错，错误可能长期无法被发现。

如果在任何一个`for`循环（for-each 或传统的）中出现类似的复制错误，生成的代码将无法编译。第一个循环的元素（或迭代器）变量在第二个循环中不在作用范围内。使用传统的`for`循环看起来如下：

```java
for (Iterator<Element> i = c.iterator(); i.hasNext(); ) {
    Element e = i.next();
    ... // 对 e 和 i 执行某些操作
}
...
// 编译错误 - 找不到符号 i
for (Iterator<Element> i2 = c2.iterator(); i.hasNext(); ) {
    Element e2 = i2.next();
    ... // 对 e2 和 i2 执行某些操作
}
```

此外，如果你使用`for`循环，你不太可能犯这种复制错误，因为没有动力在两个循环中使用不同的变量名。这两个循环是完全独立的，因此重用元素（或迭代器）变量名没有害。事实上，这样做通常是有格调的。

`for`循环相比`while`循环还有一个优势：它更短，从而增强了可读性。这里是另一个最小化局部变量作用范围的循环惯用法：

```java
for (int i = 0, n = expensiveComputation(); i < n; i++) {
    ... // 对 i 执行某些操作
}
```

关于这个惯用用法，需要注意的重要点是，它有*两个*循环变量，`i`和`n`，它们的作用范围都恰好正确。第二个变量`n`用于存储第一个变量的限制，从而避免了在每次迭代中进行冗余计算的开销。原则上，如果循环测试涉及到一个保证在每次迭代中返回相同结果的方法调用，你就应该使用这种惯用用法。

最小局部变量作用范围的最后一种技术是保持方法短小且专注。如果你在同一个方法中结合了两个活动，那么与一个活动相关的局部变量可能会处于执行另一个活动的代码的作用范围内。为了防止这种情况发生，只需将该方法分为两个：每个活动一个方法。

### 条目 58：优先使用 for-each 循环而不是传统的`for`循环

正如条目 45 中过的，某些任务最适合用流（streams）完成，而另一些则适合迭代。这里是一个遍历集合的传统`for`循环：

```java
// 遍历集合的最优方式！
for (Iterator<Element> i = c.iterator(); i.hasNext(); ) {
    Element e = i.next();
    ... // 对 e 执行某些操作
}
```

这里是一个遍历数组的传统`for`循环：

```java
// 遍历数组的最优方式！
for (int i = 0; i < a.length; i++) {
    ... // 对 a[i] 执行某些操作
}
```

这些惯用用法比`while`循环（条目 57）更好，但它们并不完美。迭代器和索引变量都是多余的——你需要的元素。此外，它们代表了出错的机会。迭代器在每个循环中出现了三次，索引变量出现了四次，这给了你很多使用错误变量的机会。如果你真的用错了，无法保证编译器能捕获到问题。最后，这两个循环非常不同，会引起人们对容器类型的不必要的关注，并为更改该类型增添（微小的）麻烦。

for-each 循环（正式称为“增强型`for`语句”）解决了所有这些问题。它通过隐藏迭代器或索引变量消除了多余的内容和出错的机会。生成的惯用用法同样适用于集合和数组，简化了容器实现类型从一种切换到另一种类型的过程：

```java
// 遍历集合和数组的首选惯用用法
for (Element e : elements) {
    ... // 对 e 执行某些操作
}
```

当你看到冒号（`:`）时，将其读作“在……之中”（in）。因此，上面的循环读作“对于`elements`中的每个元素`e`”。使用 for-each 循环没有性能损失，即使对于数组也是如此：它们生成的代码本质上与你手动编写的代码相同。

当涉及到嵌套迭代时，for-each 循环相比传统`for`循环的优势更大。这里是人们在进行嵌套迭代时经常犯的一个常见错误：

```java
// 你能发现这个 Bug 吗？
enum Suit { CLUB, DIAMOND, HEART, SPADE }
enum Rank { ACE, DEUCE, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT,
            NINE, TEN, JACK, QUEEN, KING }
...
static Collection<Suit> suits = Arrays.asList(Suit.values());
static Collection<Rank> ranks = Arrays.asList(Rank.values());
List<Card> deck = new ArrayList<>();
for (Iterator<Suit> i = suits.iterator(); i.hasNext(); )
    for (Iterator<Rank> j = ranks.iterator(); j.hasNext(); )
        deck.add(new Card(i.next(), j.next()));
```

如果你没有发现这个 Bug，不要感到遗憾。许多专家程序员都曾在某个时候犯过这个错误。问题在于外部集合（`suits`）迭代器的`next`方法被调用了太次。它应该在外部循环中调用，以便每个花色调用一次，但实际上它是在内部循环中调用的，所以每张牌调用一次。当你用完所有花色后，循环会抛出`NoSuchElementException`。

如果你真的很不幸，外部集合的大小是内部集合大小的倍数——也许是因为它们是同一个集合——那么循环将正常终止，但并不会按照你的预期。例如，考虑这个打印两对骰子所有可能组合的糟糕尝试：

```java
// 同样的 Bug，不同的症状！
enum Face { ONE, TWO, THREE, FOUR, FIVE, SIX }
...
Collection<Face> faces = EnumSet.allOf(Face.class);
for (Iterator<Face> i = faces.iterator(); i.hasNext(); )
    for (Iterator<Face> j = faces.iterator(); j.hasNext(); )
        System.out.println(i.next() + " " + j.next());
```

程序没有抛出异常，但它只打印了六个“双”（从“`ONE ONE`”到“`SIX SIX`”），而不是预期的三十六种组合。

要修复这些示例中的 Bug，你必须在外部循环的作用范围内添加一个变量来保存外部元素：

```java
// 修复了，但很丑——你可以做得更好！
for (Iterator<Suit> i = suits.iterator(); i.hasNext(); ) {
    Suit suit = i.next();
    for (Iterator<Rank> j = ranks.iterator(); j.hasNext(); )
        deck.add(new Card(suit, j.next()));
}
```

如果你使用嵌套的 for-each 循环，问题就直接消失了。生成的代码是你所能希望的最简洁：

```java
// 集合和数组嵌套迭代的首选惯用用法
for (Suit suit : suits)
    for (Rank rank : ranks)
        deck.add(new Card(suit, rank));
```

不幸的是，有三种常见情况你*不能*使用 for-each：

*   **破坏性过滤**——如果你需要遍历集合并移除某些元素，那么你需要使用显式迭代器以便调用它的`remove`方法。你通常可以使用 Java 8 添加的集合`removeIf`方法来避免显式遍历。
*   **转换**——如果你需要遍历列表或数组并替换其元素的部分或全部值，那么你需要列表迭代器或索引来替换元素。
*   **并行迭代**——如果你需要并行遍历多个集合，那么你需要显式控制迭代器或索引变量，以便所有迭代器或索引变量同步移动（正如上面的卡牌和骰子示例中无意中的那样）。

如果你发现自己处于这些情况下，请使用普通的`for`循环，并注意本条中提到的陷阱。

for-each 循环不仅让你遍历集合和数组，还能让你遍历任何实现了`Iterable`接口的对象，该接口仅包含一个方法。该接口定义如下：

```java
public interface Iterable<E> {
    // 返回该可迭代对象的元素的迭代器
    Iterator<E> iterator();
}
```

如果你必须从零编写自己的`Iterator`实现，实现`Iterable`会有点困难，但如果你正在编写一个代表一组元素的类型，你应该强烈建议它实现`Iterable`，即使你没有让它实现`Collection`。这将允许你的用户使用 for-each 循环遍历你的类型，他们将感激不尽。

总结来说，for-each 循环相比传统的`for`循环在清晰度、灵活性和预防 Bug 方面具有巨大的优势，且没有性能损失。在任何可能的地方，优先使用 for-each 循环代替`for`循环。

假设你想生成 0 到某个上限之间的随机整数。面对这一常见任务，许多程序员会写一个像这样的小方法：

```java
// 常见但存在严重缺陷！
static Random rnd = new Random();
static int random(int n) {
    return Math.abs(rnd.nextInt()) % n;
}
```

这个方法看起来可能不错，但它有三个缺陷。第一个是，如果`n`是 2 的小幂，随机数序列在很短的之后就会重复。第二个缺陷是，如果`n`不是 2 的幂，那么平均情况下，某些数字出现的频率会比其他数字更高。如果`n`很大，这种效果会非常明显。下面的程序有力地证明了这一点，它在一个精心选择的范围内生成了一百万个随机数，然后打印出落在该范围下半部分的数字个数：

```java
public static void main(String[] args) {
    int n = 2 * (Integer.MAX_VALUE / 3);
    int low = 0;
    for (int i = 0; i < 1000000; i++)
        if (random(n) < n/2)
            low++;
    System.out.println(low);
}
```



如果`random`方法工作正常，该程序将打印出一个接近五十万的数字，但如果你运行它，你会发现它打印出一个接近 666,666 的数字。`random`方法生成的数字中有二之二落在其范围的下半部分！

`random`方法的第三个缺陷是，在极少数可能会灾难性失败，返回一个超出指定范围的数字。这是因为该方法试图通过调用`Math.abs`将`rnd.nextInt()`返回的值映射为非负`int`。如果`nextInt()`返回`Integer.MIN_VALUE`，`Math.abs`也返回`Integer.MIN_VALUE`，而取模运算符（`%`）将返回一个负数（假设`n`不是 2 的幂）。这几乎肯定会导致你的程序失败，而且这种失败可能很难复现。

要编写一个修复了这些缺陷的`random`方法版本，你需要对伪随机数生成器、数论和补码算术有相当的了解。幸运的是，你不需要自己这样做——已经有人为你完成了。它被称为`Random.nextInt(int)`。你不需要担心它是如何工作的细节（尽管如果你好奇，可以研究它的文档或源代码）。一位具有算法背景的资深工程师花费了大量时间设计、实现和测试这个方法，然后将其展示给该领域的几位专家以确保它是正确的。然后，该库经过了测试测试、发布，并被数百万程序员广泛使用了近二十年。目前尚未发现该方法有任何缺陷，但如果发现了缺陷，将在下一个版本中修复。通过使用标准库，你可以利用编写该库的专家知识以及在此之前使用者的经验。

从 Java 7 开始，你不应该再使用`Random`了。对于大多数用途，现在选择的随机数生成器是`ThreadLocalRandom`。它产生的随机数质量更高，而且速度非常快。在我的机器上，它比`Random`快 3.6 倍。对于 fork join 池和并行流，请使用`SplittableRandom`。

使用库的第二个优势是，你不需要浪费时间为与你的工作细微相关的问题编写临时解决方案。如果你像大多数程序员一样，你更愿意花时间在你的应用程序上，而不是底层的管道工作上。

使用标准库的第三个优势是，它们的性能往往随着时间的推移而提高，而你不需要任何努力。因为很多人在使用它们，而且因为它们被用于行业基准测试，提供这些库的机构有强动力让它们运行得更快。Java 平台的许多库多年来被重写过，有时多次重写，导致了性能的巨大提升。

使用库的第四个优势是它们的功能随着时间的推移而增加。如果一个库缺少某些功能，开发者社区会发现，缺失的功能可能会在随后的发布中添加。

使用标准库的最后一个优势是你将你的代码置于主流中。这样的代码更容易被大量开发者阅读、维护和重用。

鉴于所有这些优势，优先使用库设施而不是临时实现似乎是合逻辑的，但许多程序员并没有这样做。为什么呢？也许他们不知道库设施的存在。每个主要版本发布时，库中都会添加许多新功能，关注这些新增是有回报的。每当 Java 平台发布一个大版本时，都会发布一个描述其新功能的网页。这些页面非常值得阅读 [Java8-feat, Java9-feat]。为了强化这一点，假设你想写一个程序来打印命令行指定的 URL 内容（这大致是`curl`命令所做的）。在 Java 9 之前，这段代码有点麻烦，但在 Java 9 中，`InputStream`添加了`transferTo`方法。这里有一个执行此任务的完整程序：

```java
// 使用 Java 9 添加的 transferTo 执行任务
public static void main(String[] args) throws IOException {
    try (InputStream in = new URL(args[0]).openStream()) {
        in.transferTo(System.out);
    }
}
```

库太大，无法学习所有的文档 [[Java9-api]]，但每个程序员应该熟悉`java.lang`、`java.util`和`java.io`及其子包的基础。其他库的知识可以在需要时获取。总结库提供的设施超出了本文的范围，这些库多年来已经变得极其巨大。

几个库值得特别提及。集合框架和流库（项目 45–48）应该是每个程序员工具箱的一部分，`java.util.concurrent`中的并发工具也是如此。该包包含了简化多线程编程的高级工具，以及允许专家编写高级并发抽象的低级 primitive。`java.util.concurrent`的高级部分在项目 80 和 81 中讨论。

有时，库设施无法满足你的需求。你的需求越专业，这种情况越容易发生。虽然你的第一反应应该是使用库，但如果你查看了它们在某些领域提供的功能并不能满足你的需求，那么请使用替代实现。任何有限库提供的的功能总会有漏洞。如果你在 Java 平台库中找不到你需要的功能，下一个选择应该是寻找高质量的第三方库，例如 Google 优秀的开源 Guava 库 [Guava]。如果你在任何合适的库中都找不到你需要的功能，你可能不得不自己实现它。

总结来说，不要重复轮子。如果你需要执行某项看起来很常见的操作，那么库中可能已经有了可以实现你需求的各种方法。如果有，就使用它；如果你不知道，就检查一下。总的来说，库代码可能比你自己编写的代码更好，并且可能随着时间的推移而改进。这并不意味着你作为程序员的能力有问题。规模效应决定了库代码所获得的关注远超过大多数开发者能够投入到相同功能上的精力。

## 项目 60：如果需要精确答案，避免使用`float`和`double`

`float`和`double`类型主要为科学和工程计算设计。它们执行二进制浮点数运算，这种运算经过仔细设计，以便在很宽的范围内快速提供准确的近似值。然而，它们并不提供精确的结果，在需要精确结果的地方不应使用。`float`和`double`类型特别不适用于货币计算，因为无法用`float`或`double`精确地表示 0.1（或任何其他 10 的负幂）。

例如，假设你的口袋里有 $1.03，你花了 42 分钱。你还剩下多少钱？这里有一个尝试回答这个问题的简单程序片段：

```java
System.out.println(1.03 - 0.42);
```

不幸的是，它打印出`0.6100000000000001`。这并不是孤立案例。假设你的口袋里有一美元，你买了九个单价为 10 分钱的垫圈。你找多少零钱？

```java
System.out.println(1.00 - 9 * 0.10);
```

根据这个程序片段，你得到了 $0.09999999999999998。

你可能认为这个问题可以通过在打印前对结果进行舍入来解决，但遗憾的是这并不总是有效。例如，假设你的口袋里有一美元，你看到货架上有一排排美味的糖果，价格分别为 10 分、20 分、30 分等等，直到 1 美元。你每种糖果买了一个，从 10 分钱的开始买，直到你买不起货架上的下一颗糖果为止。你买了多少颗糖果？找回多少零钱？这里有一个旨在解决这个问题的简单程序：

```java
// 错误 - 货币计算使用了浮点数！
public static void main(String[] args) {
    double funds = 1.00;
    int itemsBought = 0;
    for (double price = 0.10; funds >= price; price += 0.10) {
        funds -= price;
        itemsBought++;
    }
    System.out.println(itemsBought + " items bought.");
    System.out.println("Change: $" + funds);
}
```

如果你运行该程序，你会发现你只能买得起三颗糖果，并且剩下`$0.3999999999999999`。这是一个错误的答案！解决这个问题的正确方法是在货币计算中使用`BigDecimal`、`int`或`long`。

这里是将上一个程序转换为使用`BigDecimal`类型代替`double`的直接转换。注意，这里使用了`BigDecimal`的`String`构造函数而不是`double`构造函数。这是为了避免在计算中引入不准确的值 [Bloch05, Puzzle 2]：

```java
public static void main(String[] args) {
    final BigDecimal TEN_CENTS = new BigDecimal(".10");
    int itemsBought = 0;
    BigDecimal funds = new BigDecimal("1.00");
    for (BigDecimal price = TEN_CENTS;
             funds.compareTo(price) >= 0;
             price = price.add(TEN_CENTS)) {
        funds = funds.subtract(price);
        itemsBought++;
    }
    System.out.println(itemsBought + " items bought.");
    System.out.println("Change: $" + funds);
}
```

如果你运行该程序，你会发现你只能买得起三颗糖果，并且剩下`$0.3999999999999999`。这是一个错误的答案！解决这个问题的正确方法是在货币计算中使用`BigDecimal`、`int`或`long`。使用`BigDecimal`的额外优势是它让你对舍入有完全的控制权，可以在操作涉及舍入时从八种舍入模式中进行选择。

## 项目 61：基本类型优于包装基本类型

Java 有一个双部分类型系统，由基本类型（如`int`、`double`和`boolean`）和引用类型（如`String`和`List`）组成。每个基本类型都有对应的引用类型，称为包装基本类型（boxed primitive）。对应`int`、`double`和`boolean`的包装基本类型是`Integer`、`Double`和`Boolean`。

正如项目 6 提到的，自动装箱和自动拆箱模糊了并没有消除基本类型和包装类型之间的区别。它们之间存在真实的差异，意识到你正在使用哪种类型并在它们之间进行仔细选择是非常重要的。

基本类型和包装基本类型之间有三个主要区别。首先，基本类型只有其值，而包装基本类型具有与其值不同的身份。换句话说，两个包装基本类型实例可以具有相同的值但不同的身份。其次，基本类型只有完全功能的值，而每个包装基本类型除了对应基本类型的所有功能性值外，还有一个非功能性的值，即`null`。最后，基本类型在时间和空间上比包装基本类型更高效。如果你不小心，这三个差异都可能让你遇到大麻烦。

考虑以下比较器，它被设计用于表示`Integer`值的升序数值。（记住，比较器的`compare`方法返回一个负数、零或正数，取决于其第一个参数是否小于、等于或大于第二个参数。）在实践中，你不需要编写这个比较器，因为它实现了`Integer`的自然排序，但它提供了一个非常有趣的例子：

```java
// 错误的比较器 - 你能发现缺陷吗？
Comparator<Integer> naturalOrder =
    (i, j) -> (i < j) ? -1 : (i == j ? 0 : 1);
```

这个比较器看起来似乎可以工作，并且能够通过许多测试。例如，它可以用于`Collections.sort`来正确地对一个包含百万个元素的列表进行排序，无论列表是否包含重复元素。但这个比较器存在严重的缺陷。为了让自己确信这一点，只需打印`naturalOrder.compare(new Integer(42), new Integer(42))`的值即可。这两个`Integer`实例代表相同的值 (42)，所以该表达式的值本应是 0，但结果是 1，这表明第一个`Integer`值大于第二个！

那么问题出在哪里呢？`naturalOrder`中的第一个测试运行正常。评估表达式`i < j`会导致`i`和`j`所引用的`Integer`实例被自动拆箱（auto-unboxed）；即提取它们的原始类型值。评估继续进行，检查生成的`int`值中的第一个是否小于第二个。但假设事实并非如此。那么下一个测试会评估表达式`i==j`，该表达式会对两个对象引用进行标识比较（identity comparison）。如果`i`和`j`指向代表相同`int`值的不同`Integer`实例，则比较将返回`false`，比较器将错误地返回 1，指示第一个`Integer`值大于第二个。在包装后的原始类型上使用`==`运算符几乎总是错误的。

在实践中，如果你需要一个比较器来描述类型的自然顺序，你应该简单地调用`Comparator.naturalOrder()`；如果你自己编写比较器，则应该使用比较器的构造方法，或者原始类型上的静态`compare`方法（Item 14）。尽管如此，你可以通过向损坏的比较器添加两个局部变量来存储与包装`Integer`参数对应的原始`int`值，并在这些变量上执行所有比较来修复该问题。这避免了错误的标识比较：

```java
Comparator<Integer> naturalOrder = (iBoxed, jBoxed) -> {
    int i = iBoxed, j = jBoxed; // Auto-unboxing
    return i < j ? -1 : (i == j ? 0 : 1);
};
```

接下来，考虑这个有趣的短程序：

```java
public class Unbelievable {
    static Integer i;
    public static void main(String[] args) {
        if (i == 42)
            System.out.println("Unbelievable");
    }
}
```

不，它并没有打印`Unbelievable`——但它的行为几乎同样奇怪。在评估表达式`i==42`时，它抛出了`NullPointerException`。问题是`i`是一个`Integer`而不是`int`，和所有非常量对象引用字段一样，它的初始值为`null`。当程序评估表达式`i==42`时，它正在比较一个`Integer`和一个`int`。在几乎所有操作中混合原始类型和包装后的原始类型的情况下，包装后的原始类型会被自动拆箱。如果对空对象引用进行自动拆箱，就会得到`NullPointerException`。正如这个程序所示，这种情况几乎发生在任何地方。修复这个问题简单的方法是将`i`声明为`int`而不是`Integer`。

最后，考虑来自 Item 6 第 24 页的程序：

```java
// 极其缓慢的程序！你能发现对象的创建吗？
public static void main(String[] args) {
    Long sum = 0L;
    for (long i = 0; i < Integer.MAX_VALUE; i++) {
        sum += i;
    }
    System.out.println(sum);
}
```

这个程序的运行速度比应该慢得多，因为它意外地将局部变量（`sum`）声明为包装后的原始类型`Long`而不是原始类型`long`。程序编译时没有错误或警告，但变量被反复装箱和拆箱，导致了观察到的性能下降。

在本节讨论的全部三个程序中，问题是相同的：程序员忽略了原始类型和包装后的原始类型之间的区别，并承担了后果。在前两个程序中，后果是完全失败；而在第三个中，是严重的性能问题。

那么，什么时候应该使用包装后的原始类型呢？它们有几个合法的用途。第一个是集合中的元素、键和值。你不能将原始类型放入集合中，所以你被迫使用包装后的原始类型。这是更通用情况下的一个特例。你必须在泛型类型和泛的类型参数中使用包装后的原始类型（第 5 章）。

## Item 62：在适用其他类型的地方避免字符串

字符串的设计是为了表示文本，并且它们在这方面做得。由于字符串非常常见且深受语言支持，人们有一种自然的倾向，将字符串用于其设计目的之外的其他用途。本节讨论了一些你不应该对字符串做的事情。

字符串是其他类型的糟糕替代品。当部分数据从文件、网络或键盘输入进入程序时，它通常是字符串形式的。人们倾向于让它保持原样，但这种倾向只有在数据本质上确实是文本时才是合理的。如果它是数值，应该被转换为适当的数值类型，如`int`、`float`或`BigInteger`。如果它是是否问题的答案，应该转换为适当的枚举类型或`boolean`。更通地说，如果存在适当的值类型（无论是原始类型还是对象引用），你应该使用它；如果没有，你应该写一个。虽然这个建议似乎显而易见，但经常被违反。

字符串是枚举类型的糟糕替代品。如 Item 34 所述，枚举类型比字符串是更好的枚举类型常量。

字符串是聚合类型的糟糕替代品。如果一个实体有多个组件，将其表示为单个字符串通常是一个坏主意。例如，这里有一行来自真实系统的代码——为了保护已更改了标识符名称：

```java
// 不当使用字符串作为聚合类型
String compoundKey = className + "#" + i.next();
```



这种方法有许多缺点。如果用于分隔字段的字符出现在某个字段中，可能会导致混乱。要访问单个字段，必须解析字符串，这既慢又麻烦且容易出错。你无法提供`equals`、`toString`或`compareTo`方法，只能接受`String`提供的行为。更好的方法是简单编写一个类来表示聚合类型，通常是一个私有的静态成员类（Item 24）。

# 字符串并不是能力（capabilities）的糟糕替代品

偶尔，字符串被用于授予对某些功能的访问。例如，考虑线程局部变量设施的设计。这种设施为每个线程提供了其自己的值的变量。Java 库从 1.2 版本发布起就有线程局部变量设施，但在那之前，程序员必须自己实现。多年前在面对设计这种设施的任务时，几个人独立地提出了相同的设计，在该设计中，使用客户端提供的字符串键（string keys）来标识每个线程局部变量：

```java
// 错误 - 不恰当将字符串用能力！

public class ThreadLocal {

    private ThreadLocal() { } // 不实例化

    // 设置命名变量的当前线程值。

    public static void set(String key, Object value);

    // 返回命名变量的当前线程值。

    public static Object get(String key);

}
```

这种方法的问题在于，字符串键代表了线程局部变量的共享全局命名空间。为了让这种方法生效，客户端提供的字符串键必须是唯一的：如果两个客户端独立地决定为它们的线程局部变量使用相同的名称，它们就会无意中共享同一个变量，这通常会导致两个客户端都失败。此外，安全性很差。恶意的客户端可能特意使用与另一个客户端相同的字符串键，以非法访问另一个客户端的数据。

此 API 可以通过将字符串替换为不可伪造的键（有时称为*能力*/capability）来修复：

```java
public class ThreadLocal {

    private ThreadLocal() { }     // 不实例化

    public static class Key {     // (能力)

        Key() { }

    }

    // 生成一个唯一的、不可伪造的键

    public static Key getKey() {

        return new Key();

    }

    public static void set(Key key, Object value);

    public static Object get(Key key);

}
```

虽然这解决了基于字符串的 API 的两个问题，但你还可以做得更好。你不再需要静态方法了。相反，它们可以变成键上的实例方法，此时，键不再是线程局部变量的键：它*本身*就是一个线程局部变量。此时，顶层类不再为你提供任何帮助，所以你大可以将其抛弃，并将嵌套类重命名为`ThreadLocal`：

```java
public final class ThreadLocal {

    public ThreadLocal();

    public void set(Object value);

    public Object get();

}
```

这个 API 不是类型安全的，因为当你从线程局部变量中检索值时，必须将其从`Object`强制转换为其实际类型。让原始的基于字符串的 API 类型类型安全是不可能的，让基于`Key`的 API 类型安全也很困难，但通过使`ThreadLocal`成为参数化类来实现此 API 类型安全是简单的事（项目 29）：

```java
public final class ThreadLocal<T> {

    public ThreadLocal();

    public void set(T value);

    public T get();

}
```

粗略来说，这就是`java.lang.ThreadLocal`提供的 API。除了解决了基于字符串的 API 的问题外，它比任何基于键的 API 都更快、更优雅。

总结一下，当存在更好的数据类型或可以编写更好的数据类型时，避免将对象表示为字符串的自然倾向。使用不当的字符串比其他类型更繁琐、灵活性更低、速度更慢且更容易出错。经常被误用的类型包括原始类型、枚举和聚合类型。

## 项目 63：警惕字符串拼接的性能

字符串拼接运算符（`+`）是将几个字符串合并为一个字符串的方便方法。对于生成单行输出或构建小型固定大小对象的字符串表示它是没问题的，但它并不可扩展。反复使用字符串拼接运算符连接`n`个字符串需要与`n`成二次关系的时间。这是由于字符串是*不可变的*（项目 17）所导致的不幸后果。当两个字符串拼接时，两者的内容都会复制。

例如，考虑这个方法，它通过反复拼接每个项目的行来构建账单陈据的字符串表示：

```java
// 不恰当使用字符串拼接 - 性能差！

public String statement() {

    String result = "";

    for (int i = 0; i < numItems(); i++)

        result += lineForItem(i); // 字符串拼接

    return result;

}
```

如果项目数量很大，该方法的性能非常糟糕。为了获得可以接受的性能，使用`StringBuilder`代替`String`：

```java
public String statement() {

    StringBuilder b = new StringBuilder(numItems() * LINE_WIDTH);

    for (int i = 0; i < numItems(); i++)

        b.append(lineForItem(i));

    return b.toString();

}
```

自 Java 6 以来，在提高字符串拼接方面做了很多工作，但两种方法之间的差异仍然巨大：如果`numItems`返回 100，`lineForItem`返回 80 个字符，第二种方法运行快 6.5 倍。因为第一种方法与数量呈二次关系，而第二种是线性的，随着项目数量的增长，差异会变得大。注意，第二种方法预分配了足够容整个结果的`StringBuilder`，消除了自动增长的需求。即使它使用默认大小的`StringBuilder`，仍然比第一种方法快 5.5 倍。

道理很简单：除非性能无关，否则不要使用字符串拼接运算符合并多个字符串。相反使用`StringBuilder`的`append`方法。或者使用字符数组，或者逐个处理字符串而不是合并它们。

## 项目 64：通过接口引用对象

项目 51 说你应该使用接口而不是类作为参数类型。更广泛地说，你应该优先使用接口来引用对象。如果存在合适的接口类型，那么参数、返回值和字段都应该使用接口类型声明。你真正需要引用对象类的时候是在创建它时。为了具体化，考虑`LinkedHashSet`的情况，它是`Set`接口的实现。养成输入这种习惯：

```java
// 好 - 使用接口作为类型

Set<Son> sonSet = new LinkedHashSet<>();
```

而不是这种：

```java
//  - 使用类作为类型！

LinkedHashSet<Son> sonSet = new LinkedHashSet<>();
```

如果你养成使用接口作为类型的习惯，你的程序将变得灵活得多。如果你决定切换实现，你只需要更改构造函数中的类名（或使用不同的静态工厂方法）。例如，第一个声明可以更改为：

```java
Set<Son> sonSet = new HashSet<>();
```

所有的周围代码将继续工作。周围代码对旧的实现类型感知，因此它对更改毫无察觉。

有一个需要注意：如果原始实现提供了某些接口通用合约未要求的特殊功能，且代码依赖于该功能，那么新实现提供相同的功能是至关重要的。例如，如果第一个声明周围的代码依赖于`LinkedHashSet`的排序策略，那么在声明中使用`HashSet`替换`LinkedHashSet`就是不正确的，因为`HashSet`不保证迭代顺序。

那么，你为什么想要更改实现类型呢？因为第二种实现比原始实现具有更好的性能，或者因为它提供了原始实现所缺乏的理想功能。例如，假设一个字段包含一个`HashMap`实例。将其更改为`EnumMap`可以提供更好的性能，以及与键的自然顺序一致的迭代顺序，但只有当键的类型为枚举类型时你才能使用`EnumMap`。将`HashMap`更改为`LinkedHashMap`将提供可预测的迭代顺序，且性能与`HashMap`相当，同时对键的类型没有特殊要求。

你可能认为使用实现类型来声明变量是没问题的，因为你可以同时更改声明类型和实现类型，但无法保证这种更改会导致程序能够编译。如果客户端代码使用了原始实现类型上的方法，而这些方法在替换类型上并不存在，或者客户端代码将实例传递到需要原始实现类型的方法中，那么进行此更改后代码将不再编译。使用接口类型声明变量可以让你保持严谨。

**在没有合适接口的情况下，通过类而非接口来引用对象是完全恰当的。** 例如，考虑值类，如`String`和`BigInteger`。值类很少是为了考虑多种实现而编写的。它们通常是最终的（final），并且极很少有相应的接口。将此类值类作为参数、变量、字段或返回类型是完全合适的。

另一种没有合适接口类型的情况是属于某个框架的对象，该框架的根本类型是类而非接口。如果一个对象属于这样一个基于类的框架，最好通过相关的基类（通常是抽象类）来引用它，而不是通过它的实现类。许多`java.io`类（如`OutputStream`）都属于这一类。

最后一种没有合适接口类型的情况是，那些实现了接口但也提供了接口中未发现额外方法的类——例如，`PriorityQueue`拥有一个`comparator`方法，该方法在`Queue`接口中并不存在。只有当程序依赖这些额外方法时，应该使用此类类来引用其实例，而这种情况应该是非常罕见的。

这三种情况并不是穷尽的，只是为了传达在什么情况下通过类引用对象是恰当的。在实践中，给定的对象是否具有合适的接口应该是显而易见的。如果有，使用接口来引用该对象将使你的程序更加灵活且优雅。**如果没有合适的接口，请直接使用类层次结构中提供所需功能的最不具体的类。**

## 第 65 节：优先使用接口而非反射

核心反射机制`java.lang.reflect`提供了对任意类的程序化访问。给定一个`Class`对象，你可以获取`Constructor`、`Method`和`Field`实例，它们分别代表该`Class`实例所表示的类的构造函数、方法和字段。这些对象提供了对类的成员名称、字段类型、方法签名等的程序化访问。

此外，`Constructor`、`Method`和`Field`实例允许你通过反射操作其底层对应对象：你可以通过调用`Constructor`、`Method`和`Field`实例上的方法，来构造实例、调用方法并访问底层类的字段。例如，`Method.invoke`允许你调用任何类的任何对象的任何方法（受限于通常的安全限制）。反射允许一个类使用另一个类，即使后者在先者编译时还并不存在。然而，这种力量是有代价的：

- **你失去了所有编译时类型检查的优势，** 包括异常检查。如果程序尝试通过反射调用一个不存在或不可访问的方法，除非你采取了特殊的预防措施，否则将在运行时失败。
- **执行反射访问所需的代码是笨拙且冗长的。** 它写起来很枯燥，读起来很困难。
- **性能受到影响。** 反射方法调用比普通方法调用要慢得多。具体慢多少很难说，因为有许多因素在起。在我的机器上，使用反射调用一个无输入参数且返回`int`的方法比普通的慢了十一倍。

有一些需要反射的复杂应用。例如代码分析工具和依赖注入框架。即使是这些工具，最近也在逐渐远离反射，因为它的缺点变得越来越明显。如果你对应用程序是否需要反射有任何疑问，那么它可能不需要。

**对于许多必须使用在编译时不可用的类的程序，在编译时存在一个合适的接口或超类可以借此引用该类（第 64 节），通过仅以非常有限的形式使用反射，你可以获得许多反射优势的同时避免其大部分成本。如果是这样，你可以反射地创建实例，并通过接口或超类正常地访问它们。

例如，这里有一个创建`Set<String>`实例的程序，其类由第一个命令行参数指定。程序将剩余的命令行参数插入集合并打印。无论第一个参数是什么，程序都会打印去除了重复的剩余参数。然而，这些参数的打印顺序取决于第一个参数中指定的类。如果你指定`java.util.HashSet`，它们将以看似随机顺序打印；如果你指定`java.util.TreeSet`，它们将按字母顺序打印，因为`TreeSet`中的元素是排序的：

```java
// 接口访问反射

public static void main(String[] args) {

    // 将类转换为 Class 对象

    Class<? extends Set<String>> cl = null;

    try {

        cl = (Class<? extends Set<String>>) // 未检查的转换！

              Class.forName(args[0]);

    } catch (ClassNotFoundException e) {

        fatalError("未找到类.");

    }

    // 获取构造函数

    Constructor<? extends Set<String>> cons = null;

    try {

        cons = cl.getDeclaredConstructor();

    } catch (NoSuchMethodException e) {

        fatalError("无无参数构造函数");

    }

    // 实例化集合

    Set<String> s = null;

    try {

        s = cons.newInstance();

    } catch (IllegalAccessException e) {

        fatalError("构造函数不可访问");

    } catch (InstantiationException e) {

        fatalError("类不可实例化.");

    } catch (InvocationTargetException e) {

        fatalError("构造函数抛出异常 " + e.getCause());

    } catch (ClassCastException e) {

        fatalError("类未实现 Set");

    }

    // 使用集合

    s.addAll(Arrays.asList(args).subList(1, args.length));

    System.out.println(s);

}
```

```java
private static void fatalError(String msg) {

    System.err.println(msg);

    System.exit(1);
}
```



虽然这个程序只是一个示例，但它所演示的技术是非常强大的。这个示例程序可以很容易地转换为一个通用的集合测试器，通过激进地操作一个或多个实例并检查它们是否遵守`Set`约束，来验证指定的`Set`实现。同样，它也可以被转换为一个通用的集合性能分析工具。事实上，这种技术足够强大，可以实现一个完整的服务提供者框架（Item 1）。通常，在反射方面，这种技术就是你需要的所有。

这个示例展示了反射的两个缺点。首先，该示例可以在运行时生成六种不同的异常，如果不是使用反射实例化，所有这些异常都将是编译时错误。（为了好玩，你可以通过传递合适的命令行参数让程序生成这六种异常中的每一种。）第二个缺点是，需要二十五行繁琐的代码才能从类名生成类的实例，而一个构造函数调用可以简洁地写在一行内。通过捕获`ReflectiveOperationException`（Java 7 引入的各种反射异常的父类），可以缩短程序的长度。这两个缺点都局限于程序中实例化对象的部分。一旦实例化，该集合与任何其他`Set`实例没有区别。在实际程序中，大部分代码因此不受这种有限反射使用的影响。

如果你编译这个程序，你将得到一个未检查的类型转换警告。这个警告是合理的，因为即使命名类不是`Set`实现，转换到`Class<? extends Set<String>>`也会成功，在这种情况下，程序在实例化该类时将抛出`ClassCastException`。要了解如何抑制警告，请阅读 Item 27。

反射的一个合法但罕见的用法是管理类对运行时可能不存在的其他类、方法或字段的依赖关系。如果你正在编写一个必须针对某些其他包的多个版本的包，这将非常有用。这种技术是针对支持该包所需的最小环境（通常是最旧的版本）编译你的包，并通过反射访问任何较新的类或方法。为了使之工作，如果你尝试访问的较新类或方法在运行时不存在，你必须采取适当的行动。适当的行动可能包括使用某些替代手段来实现相同的目标，或者以减少的功能进行操作。

总之，反射是一项强大的机制，对于某些复杂的系统编程任务是必要的，但它有许多缺点。如果你正在编写一个必须与编译时未知的类工作的程序，只要可能，你应该只使用反射来实例化对象，并使用编译时已知的接口或超类来访问这些对象。

## Item 66: 审慎使用原生方法

Java 原生接口（JNI）允许 Java 程序调用原生方法，即用 C 或 C++ 等原生编程语言编写的方法。从历史上看，原生方法有三个主要用途。它们提供了对平台特定设施（如注册表）的访问。它们提供了对现有原生代码库的访问，包括提供访问遗留数据的旧库。最后，原生方法用于用原生语言编写应用程序中性能至关重要的部分，以提高性能。

使用原生方法访问平台特定设施是合法的，但很少有必要：随着 Java 平台的成熟，它提供了对许多以前只在宿主平台上找到的功能的访问。例如，Java 9 中添加的进程 API 提供了对操作系统进程的访问。当 Java 中没有等效库时，使用原生方法使用原生库也是合法的。

**很少建议使用原生方法来提高性能。** 在早期版本（Java 3 之前）中，这通常是必要的，但自那以后 JVM 已经变得快得多。对于大多数任务，现在可以在 Java 中获得可比的性能。例如，当`java.math`在 1.1 版本中添加时，`BigInteger`依赖于当时一个用 C 编写的快速多精度算术库。在 Java 3 中，`BigInteger`用 Java 重新实现，并经过仔细调优，到其运行速度比原始的原生实现更快。

这个故事一个遗憾的结局是，`BigInteger`自那以后变化很小，除了 Java 8 加快了大数的乘法外。在过去的一段时间里，原生库的工作仍在快速进行，特别是 GNU 多精度算术库（GMP）。需要真正高性能多精度算术运算的 Java 程序员现在有理由通过原生方法使用 GMP [Blum14]。

使用原生方法有严重的缺点。因为原生语言是不安全的（Item 50），使用原生方法的应用程序不再对内存损坏错误免疫。因为原生语言比 Java 更依赖于平台，使用原生方法的程序移植性较差。它们也更难调试。如果你不小心，原生方法可能会降低性能，因为垃圾回收器无法自动甚至无法跟踪原生内存的使用（Item 8），而且进入和退出原生代码是有成本的。最后，原生方法需要难以阅读和编写起来繁琐的“胶水代码”。

总之，在使用原生方法之前请考虑两次。你很少需要为了提高性能而使用它们。如果你必须使用原生方法访问低级资源或原生库，请尽可能少地使用原生代码并对其进行彻底测试。原生代码中的一个错误就可能损坏你的整个应用程序。

## Item 67: 审慎地优化

有三个关于优化的格言每个人都应该知道：

以效率的名义犯下的计算罪行（而不一定能实现它）比任何其他单一原因都多——包括盲目的愚蠢。
—William A. Wulf [Wulf72]

在 97% 的时间里，我们应该忘记微小的效率：过早优化是万恶之源。
—Donald E. Knuth [Knuth74]

我们在优化问题上遵循两条规则：

规则 1。不要做。

规则 2（仅限专家）。现在不要做——也就是说，在你拥有一个完美且未优化的解决方案之前不要做。
—M. A. Jackson [Jackson75]

所有这些格言都比 Java 语言早二十年。它们揭示了关于优化的深层真理：事大于利是很容易的，特别是当你过早优化的时候。在这个过程中，你可能会产生既不快也不正确且难以修复的软件。

不要为了性能牺牲良好的架构原则。**努力编写良好的程序，而不是快速程序。** 如果一个良好的程序速度不够快，它的架构将允许对其优化。良好的程序体现了信息隐藏原则：在可能的情况下，它们将设计决策局部化在单个组件内部，以便在更改决策时不影响系统的其余部分（Item 15）。

这`not`意味着你可以在程序完成之前忽略性能问题。实现层面的问题可以通过后期优化来修复，但限制性能的普遍性架构缺陷在不重写系统的情况下可能是无法修复的。在事后更改你设计的根本方面可能会导致系统结构不合理，难以维护和演进。因此，你必须在设计过程中考虑性能。

### 努力避免限制性能的设计决策

设计中，在事后最难以更改的组件是那些指定组件之间交互以及与外部世界交互的部分。这些设计组件中最重要的是 API、线层级协议和持久化数据格式。这些设计组件不仅在事后难以或无法更改，而且它们所有项都可能对系统能达到的任何性能产生重大限制。

### 考虑你的 API 设计决策对性能的影响

将一个公共类型设为可变可能需要大量的不必要的防御性拷贝（Item 50）。同样，在可以使用组合的公共类中使用继承，这会将该类与它的父类永久绑定在一起，这可能会对子类的性能造成人为的限制（Item 18）。最后一个例子是，在 API 中使用实现类型而非接口，会将你绑定到特定的实现上，即使未来可能会编写更快的实现（Item 64）。

API 设计对性能的影响是非常真实的。考虑`java.awt.Component`类中的`getSize`方法。将这个性能关键方法设计为返回一个`Dimension`实例的决策，加上`Dimension`实例是可变的决策，迫使该方法的任何实现在每次调用时都分配一个新的`Dimension`实例。尽管在现代虚拟机上分配小对象的代价开销很小，但无谓地分配数百万个对象会对性能造成实质性的损害。

曾经存在过几种 API 设计替代方案。理想情况下，`Dimension`应该是不可变的（Item 17）；或者，`getSize`可以被两个返回`Dimension`对象中各个原始数据类型组件的方法所取代。事实上，出于性能考虑，Java 2 在`Component`中添加了两个这样的方法。然而，现有的客户端代码仍然使用`getSize`方法，并且仍然遭受着原始 API 决策带来的性能后果。

幸运的是，通常良好的 API 设计与良好的性能是一致的。为了获得良好的性能而扭曲 API 是一个非常糟糕的主意。导致你扭曲 API 的性能问题可能会在平台或其他底层软件的未来版本中消失，但扭曲的 API 以及随之而来的维护头疼问题将与你伴随终生。

一旦你仔细设计了程序并产生了一个清晰、简洁且结构良好的实现，`那么`可能就是时候考虑优化了，前提是你尚未对程序的性能感到满意。

回想一下 Jackson 优化的两条规则是“不要做”以及“（仅限专家）。现在不要做”。他本可以再增加一点：**在每次尝试优化的前后测量性能。** 你可能会对你发现的结果感到惊讶。通常情况下，尝试的优化对性能没有可衡量的影响；有时，它们会让情况变得更糟。主要原因是很难猜测你的程序将时间消耗在了哪里。你认为程序中缓慢的部分可能并没有问题，如果是这种情况下，你就是在浪费时间尝试优化它。常识告诉我们程序 90% 的时间花在 10% 的代码上。

性能剖析工具（Profiling tools）可以帮助你决定将优化精力集中在哪里。这些工具为你提供运行时信息，例如每个方法大约消耗了多少时间以及被调用了多少次。除了专注于调优，这还可以提醒你需要进行算法更改。如果你的程序内部隐藏着一个二次（或更糟）算法，任何调优都无法解决问题。你必须用更高效的算法替换它。系统中的代码越多，使用剖析器就越重要。这就像在大海捞针：大海越大，拥有金属探测器就越有用。另一个值得特别提到的工具是`jmh`，它不是一个剖析工具，而是一个`微基准框架`，为 Java 代码的详细性能提供了无与伦比的可见性 [JMH]。

Java 中测量尝试优化的效果更为必要，因为 Java 的性能模型较弱：各种原始操作的相对成本定义得不够明确。程序员编写的内容与 CPU 执行的内容之间的“抽象鸿沟”更大，这使得更难可靠地预测优化的性能后果。流传着许多性能神话，结果被证明是半真半假或彻头彻尾的谎言。

Java 的性能模型定义模糊，而且还随实现、发布版本以及处理器的不同而异。如果你将在多个实现或多个硬件平台上运行程序，那么测量优化在每个平台上的影响是非常关键的。偶尔你可能被迫在不同实现或硬件平台上的性能之间进行权衡。

在本文项目首次编写以来的近二十年里，Java 软件栈的每个组件都变得更加复杂，从处理器到虚拟机再到库，运行 Java 的硬件多样性也急剧增长。所有这些因素共同导致 Java 程序的性能现在比 2001 年时更不可预测，对测量性能的需求也随之增加。

总结一下，不要努力编写快速的程序——努力编写良好的程序；速度会随之而来。但在设计系统时，务必考虑性能，特别是在设计 API、线层级协议和持久化数据格式时。当你构建完系统后，测量它的性能。如果足够快，你就大功告成。如果不够，借助剖析器定位问题所在，并开始优化系统的相关部分。第一步是检查你的算法选择：任何底层优化都无法弥补糟糕算法选择。根据需要重复此过程，每次更改后测量性能，直到你满意为止。

## Item 68：遵循通用的命名规范

Java 平台有一套广良好的`命名规范`，其中许多包含在《Java 语言规范》[JLS, 6.1] 中。粗略来说，命名规范分为两类：类型和语法。

只有少数类型命名规范，涵盖了包、类、接口、方法、字段和类型变量。你应该很少违反它们，除非有非常充分的理由。如果 API 违反了这些规范，可能会难以使用。如果实现违反了这些，可能会难以维护。在两种情况下，违反规范都可能困扰和干扰与代码一起工作的其他程序员，并可能导致错误的假设引发错误。这些规范在本项中总结。

### 包和模块名称

包（Package）和模块的名称应该是层次化的，组件之间用点`.`分隔。组件应由小写字母组成，极少数情况下包含数字。任何在你的组织之外使用的包名都应以你组织的 Internet 域名开头，并反转组件顺序，例如`edu.cmu`、`com.google`、`org.eff`。标准库和可选包（其名称以`java`和`javax`开头）是这一规则的例外。用户不得创建名称以`java`或`javax`开头的包或模块。关于将 Internet 域名转换为包名前缀的详细规则，可以在 JLS [JLS, 6.1] 中查找到。

包名的剩余部分应由一个或多个描述该包的组件组成。组件应该很短，通常为八个字符或更少。鼓励使用有意义的缩写，例如用`util`而不是`utilities`。缩写是可以接受的，例如`awt`。组件通常应由单个单词或缩写组成。

许多包的名称除了 Internet 域名外仅有一个组件。对于规模大到需要拆分为非正式层次结构的大型机构，额外的组件是适当的。例如，`javax.util`包拥有丰富的包层次结构，名称如`java.util.concurrent.atomic`。此类包被称为`subpackages`（子包），尽管在语言上对包层次结构几乎没有支持。

### 类和接口名称

类和接口名称（包括枚举和注解类型名称）应由一个或多个单词组成，每个单词的首字母大写，例如`List`或`FutureTask`。应避免使用缩写，但缩写和某些如`max`和`min`等常见的缩写除外。对于缩写应该是全大写还是仅首字母大写，存在一些分歧。虽然某些程序员仍然使用大写，但有一个强有力的理由支持仅大写首字母：即使多个缩写连续出现，你仍然可以判断一个单词何时开始，另一个单词何时结束。你更愿意看到哪种类名，`HTTPURL`还是`HttpUrl`？

### 方法和字段名称

方法和字段名称遵循与类和接口相同的排版约定，但方法或字段名称的首字母应该小写，例如`remove`或`ensureCapacity`。如果缩写作为方法或字段名称的第一个单词，则它应当是小写。

上述规则的唯一例外是“常量字段”，其名称应由一个或多个用下划线`_`分隔的大写单词组成，例如`VALUES`或`NEGATIVE_INFINITY`。常量字段是一个值不可变的`static final`字段。如果一个`static final`字段具有原始类型或不可变引用类型（Item 17），那么它就是一个常量字段。例如，枚举常量就是常量字段。如果`static final`字段具有可变引用类型，只要所引用的对象是不可变的，它仍然可以是常量字段。注意，常量字段是下划线的推荐用法。

### 变量和类型参数

局部变量名称的排版命名约定与成员名相似，但允许使用缩写、单个字符以及意义取决于其出现上下文的短字符序列，例如`i`、`denom`、`houseNum`。输入参数是一种特殊的局部变量。它们的命名应该比普通局部变量小心得多，因为它们的名称是方法文档中不可或缺的一部分。

类型参数名称通常由单个字母组成。最常见的是这五个之一：`T`表示任意类型，`E`表示集合的元素类型，`K`和`V`表示 map 的键和值类型，`X`表示异常。函数的返回类型通常是`R`。任意类型的序列可以是`T`、`U`、`V`或`T1`、`T2`、`T3`。

为了方便参考，下表显示了排版约定的示例：

| 标识符类型 | 示例 |
| :--- | :--- |
| 包或模块 | `org.junit.jupiter.api`, `com.google.common.collect` |
| 类或接口 | `Stream`, `FutureTask`, `LinkedHashMap`, `HttpClient` |
| 方法或字段 | `remove`, `groupingBy`, `getCrc` |
| 常量字段 | `MIN_VALUE`, `NEGATIVE_INFINITY` |
| 局部变量 | `i`, `denom`, `houseNum` |
| 类型参数 | `T`, `E`, `K`, `V`, `X`, `R`, `U`, `V, T1, T2` |

### 语法命名约定

语法命名约定比排版约定更灵活，也更具争议。包并没有什么可言的语法命名约定。可实例化的类（包括枚举类型）通常用单数名词或名词短语命名，例如`Thread`、`PriorityQueue`或`ChessPiece`。不可实例化的工具类（Item 4）通常用复数名词命名，例如`Collectors`或`Collections`。接口的命名与类相似，例如`Collection`或`Comparator`，或者以`able`或`ible`结尾的形容词，例如`Runnable`、`Iterable`或`Accessible`。由于注解类型有许多用途，没有某种词性占主导。名词、动词、介词和形容词都很常见，例如`BindingAnnotation`、`Inject`、`ImplementedBy`或`Singleton`。

执行某些操作的方法通常用动词或动词短语（包括对象）命名，例如`append`或`drawImage`。返回`boolean`值的方法通常以单词`is`开头，或者较少用的`has`，后接名词、名词短语或任何作为形容词的单词或短语，例如`isDigit`、`isProbable`、`isEmpty`、`isEnabled`或`hasSiblings`。

返回被调用对象的非`boolean`函数或属性的方法通常用名词、名词短语或带有动词`get`的动词短语命名，例如`size`、`hashCode`或`getTime`。有一种观点认为只有第三种形式（以`get`开头）是可以接受的，但这种主张缺乏依据。前两种形式通常产生更具可读性的代码，例如：

```
if (car.speed() > 2 * SPEED_LIMIT)
    generateAudibleAlert("Watch out for cops!");
```



如果类包含相同属性的 setter 和 getter，也有遵循这种命名的惯例。在这种情况下，这两个方法通常命名为`getAttribute`和`setAttribute`。

### 特殊方法名称

以`get`开头的形式源于早已过时的 *Java* 规范，该规范是早期复用组件架构的基础。现代工具继续依赖 Beans 命名约定，在与这些工具配合使用的任何代码中，你尽管可以使用它。

少数方法名称值得特别提及。转换对象类型并返回不同类型的独立对象的实例方法通常称为`getType`，例如`toString`或`toArray`。返回与接收对象类型不同的视图（Item 6）的方法通常称为`asType`，例如`asList`。返回与调用对象值相同的原始类型的方法称为`isValue`，例如`intValue`。静态工厂的常见名称包括`from`、`of`、`valueOf`、`instance`、`getInstance`、`newInstance`、`getType`和`newType`（Item 1, 第 9 页）。

字段名的语法约定没有类、接口和方法名的约定那样完善，也不那么重要，因为良好的 API 很少（甚至没有）暴露字段。`boolean`类型的字段通常命名方式类似于`boolean`访问器方法，但省略了开头的`is`，例如`initialized`、`composite`。其他类型的字段通常用名词或名词短语命名，例如`height`、`digits`或`bodyStyle`。局部变量的语法约定与字段相似，但更弱。

总结一下，要内化标准的命名约定，并学会将它们变成本能。排版约定是直观且在很大程度上没有歧义的；语法约定则更为复杂且松散。引用《Java 语言规范》[JLS, 6.1] 的话：“如果长期以来的习惯用法另有规定，则不应盲目遵循这些约定。”请运用常识。

# 第 10 章 异常

当使用良好时，异常可以提高程序的可读性、可靠性和维护性。当使用不当时，它们可能会适得其反。本章提供了有效使用异常的指南。

### 第 69 条：仅对异常情况使用异常

某一天，如果你运气不好，你可能会遇到看起来类似这样的代码：

```java
// 对异常的糟糕滥用。千万不要这样做！
try {
    int i = 0;
    while(true)
        range[i++].climb();
} catch (ArrayIndexOutOfBoundsException e) {
}
```

这段代码是做什么的？从检查上看这并不显而易见，这足以理由不使用它（第 67 条）。事实证明，这是一个糟糕构思的遍历数组元素的惯用法。无限循环通过在尝试访问数组边界之外的第一个元素时，通过抛出、捕获并忽略`ArrayIndexOutOfBoundsException`来终止的。它本应该等同于遍历数组的标准惯用法，而任何 Java 程序员都能立即识别出来：

```java
for (Mountain m : range)
    m.climb();
```

那么，为什么有人会选择基于异常的循环而不是经过检验且可靠的方法呢？这是一种试图提高性能的误导尝试，其错误推理是：既然 VM 会检查所有数组访问的边界，那么正常的循环终止测试（被编译器隐藏，但在 for-each 循环中仍然存在）是多余的，应该被避免。这种推理有三个错误：

- 因为异常是专为特殊情况设计的，所以 JVM 实现者几乎没有动力让它们变得像显式测试一样快。
- 将代码放在`try-catch`块中会抑制 JVM 实现本可能执行的某些优化。
- 遍历数组的标准惯用法并不一定会导致冗余检查。许多 JVM 实现都会将它们优化掉。

事实上，基于异常的惯用法比标准的要慢得多。在我的机器上，对于一百个元素的数组，基于异常的惯用法大约是标准的两倍。

基于异常的循环不仅模糊了代码意图并降低了性能，而且无法保证正常工作。如果循环中存在 bug，使用异常进行流程控制可能会掩盖 bug，极大地增加调试的复杂度。假设循环体中的计算调用了一个方法，该方法对某些无关的数组进行了越界访问。如果使用了合理的循环惯用法，bug 将产生一个未被捕获的异常，导致线程立即终止并带有完整的堆栈跟踪。如果使用了这种误导性的基于异常的循环，与 bug 相关的异常将被捕获并被误认为是正常的循环终止。

这个故事的寓理很简单：**异常正如其名所示，仅用于异常情况；它们永远不应该用于普通的控制流。** 更通地说，要优先使用标准的、易于识别的惯用法，而不是那些声称能提供更好性能的过度巧妙的技术。即使性能优势是真实的，在不断改进的平台实现面前，它也可能不再存在。然而，过度巧妙的技术带来的细微 bug 和维护上的头疼问题却会一直存在。

这一原则对 API 设计也有影响。**良好的 API 设计绝不能强制其客户端使用异常进行普通的控制流。** 一个具有“状态依赖”方法的类，如果该方法只能在某些不可预测的条件下被调用，则通常应该有一个独立的“状态测试”方法，用以指示调用该状态依赖方法是否合适。例如，`Iterator`具有状态依赖方法`next`和对应的状态测试方法`hasNext`。这使得可以使用传统的`for`循环遍历集合（以及 for-each 循环，其内部使用了`hasNext`方法）的标准惯用法：

```java
for (Iterator<Foo> i = collection.iterator(); i.hasNext(); ) {
    Foo foo = i.next();
    ...
}
```

如果`Iterator`缺少`hasNext`方法，客户端将不得不执行以下操作：

```java
// 不要使用这种丑陋的代码来遍历集合！
try {
    Iterator<Foo> i = collection.iterator();
    while(true) {
        Foo foo = i.next();
        ...
    }
} catch (NoSuchElementException e) {
}
```

在看到本项开始的数组示例后，这看起来应该非常熟悉。除了冗长和误导性之外，基于异常的循环性能可能很差，并可能掩盖其他部分的 bug。

提供独立的状态测试方法的替代方案是，让状态依赖方法在无法执行所需计算时返回一个空的可选 (第 55 条) 或特殊值（如`null`）。

以下是帮助你在状态测试方法与可选或特殊返回值之间做出选择的指南。如果对象要在没有外部同步的情况下并发访问或受到外部状态转换，你必须使用可选或特殊返回值，因为在调用状态测试方法和状态依赖方法之间，对象的状态可能会发生。如果单独的状态测试方法会重复状态依赖方法的工作，性能考虑可能决定使用可选或特殊返回值。在其他条件相同的情况下，状态测试方法略优于特殊返回值。它提供了略好的可读性，且错误用法可能更容易被检测：如果你忘记调用状态测试方法，状态依赖方法将抛出异常，使 bug 变得明显；如果你忘记检查特殊返回值，bug 可能是细微的。对于可选返回值来说，这不是问题。

总结，异常是为异常情况设计的。不要将它们用于普通的控制流，也不要编写强制他人这样做 API。

### 第 70 条：使用检查异常处理可恢复的情况，使用运行时异常处理编程错误

Java 提供了三种可抛异常：*检查异常*、*运行时异常*和*错误*。程序员对于何时使用每种可抛异常存在一些困惑。虽然决策并非总是一目了然的，但一些通用规则提供了强有力的指导。

决定使用受检异常（checked exception）还是未检查异常（unchecked exception）的核心规则是：`对于调用者可以合理恢复的情况使用受检异常。`通过抛出受检异常，你强制调用者在`catch`句中处理异常，或将其向外传播。因此，方法声明要抛出的每个受检异常都是向 API 用户提供的一个强有力信号，表明相关条件是调用该方法时可能的结果。

通过向用户呈现受检异常，API 设计者实际上提供了一项恢复该状态的强制性指令。用户可以通过捕获异常并忽略它来无视指令，但这通常是一个坏主意（Item 77）。

未检查的可抛异常有两种类型：运行时异常（runtime exceptions）和错误（errors）。它们在行为上是相同的：两者都是不需要（通常也不应该）被捕获的可抛对象。如果程序抛出未检查异常或错误，通常意味着恢复是不可能的，且继续执行的弊大于利。如果程序不捕获此类可抛对象，它将导致当前线程停止并显示相应的错误信息。

`使用运行时异常来指示编程错误。` 大多数运行时异常表示`前置条件违反（precondition violations）`。前置条件违反简单来说就是客户端未能遵守 API 规范所建立的约定。例如，数组访问约定规定数组索引必须在零到数组长度减一之间（包含边界）。`ArrayIndexOutOfBoundsException`表示违反了这一前置条件。

这条建议的一个问题是，并不总是清楚你面对的是一个可以恢复的情况还是编程错误。例如，考虑资源耗尽的情况，这可能是由编程错误（如分配一个异常巨大的数组）引起的，也可能是真实的资源短缺。如果资源耗尽是由临时短缺或需求临时增加引起的，该情况可能是可以恢复的。特定的资源耗尽实例是否可能允许恢复，取决于 API 设计者的判断。如果你认为某个情况可能允许恢复，请使用受检异常；否则，请使用运行时异常。如果不确定是否可以恢复，你可能使用未检查异常会更好，原因请见 Item 71 中的讨论。

虽然 Java 语言规范没有强制要求，但有一个强有惯例：`errors`被预留给 JVM 使用，以指示资源不足、不变性失效或其他使执行无法继续的情况。鉴于这一惯例几乎被通俗接受，最好不要实现任何新的`Error`子类。因此，`你实现的所有未检查可抛对象都应该是 RuntimeException 的子类`（直接或间接地）。你不光应该定义`Error`子类，除了`AssertionError`之外，你也不应该抛出它们。

可以定义一个不是`Exception`、`RuntimeException`或`Error`子类的可抛对象。JLS 没有直接处理此类可抛对象，但隐式地规定它们的行为类似于普通的受检异常（即`Exception`的子类但不是`RuntimeException`）。那么你什么时候应该使用这种“怪物”呢？简而言之，永远不要。它们相比普通的受检异常没有任何优点，只会困扰你 API 的用户。

API 设计者经常忘记，异常是功能完全的对象，可以在上面定义任意方法。此类方法的首要用途是提供捕获异常的代码，并包含有关导致异常抛出的条件的额外信息。在缺少此类方法的情况下，已知程序员会解析异常的字符串表示来搜寻额外信息。这是一种极糟糕的做法（Item 12）。Throwable 类很少指定其字符串表示的细节，因此字符串表示可能随实现和发布版本的不同而不同。因此，解析异常字符串表示的代码很可能是不可移植且脆弱的。

由于受检异常通常表示可恢复的情况，因此让它们提供相关信息以帮助调用者从异常状态中恢复的方法显得尤为重要。例如，假设在尝试使用礼品卡购买时因资金不足而失败，抛出了受检异常。该异常应该提供一个访问方法来查询缺口金额。这将允许调用者将金额传递给购物者。关于此主题的更多信息，请参见 Item 75。

总结：对于可恢复的情况抛出受检异常，对于编程错误抛出未检查异常。疑问时抛出未检查异常。不要定义任何既受检异常不是运行时异常的可抛对象。在你的受检异常上提供辅助恢复的方法。

### Item 71: 避免不必要的受检异常

许多 Java 程序员不喜欢受检异常，但如果使用得当，它们可以改进 API 和程序。与返回码和未检查异常不同，它们`强制`程序员处理问题，增强了可靠性。尽管如此，在 API 中过度使用受检异常会使它们变得非常难用。如果一个方法抛出受检异常，调用它的代码必须在一个或多个`catch`块中处理它们，或者声明它抛出了这些异常并让它们向外传播。无论哪种方式，都给 API 用户增加了负担。这种负担在 Java 8 中增加了，因为抛出受检异常的方法不能直接在流中使用（Items 45–48）。

如果异常情况无法通过正确使用 API 来防止*且*使用 API 的程序员在遇到异常后可以采取某些有效操作，那么这种负担就是合理的。除非这两个条件都满足，否则使用未检查异常更为合适。作为一个测试标准，问问自己程序员将如何处理该异常。这是最好的做法吗？

```java
try {
    // ...
} catch (TheCheckedException e) {
    throw new AssertionError(); // 不可能！
}
```

或者是这个？

```java
try {
    // ...
} catch (TheCheckedException e) {
    e.printStackTrace(); // 哎，我们输了。
    System.exit(1);
}
```

如果程序员无法做得更好，那么就需要未检查异常了。

如果一个受检异常是方法抛出的*唯一*受检异常，它给程序员增加的额外负担会大得多。如果还有其他异常，该方法已经出现在`try`块中了，而这个异常最多只需要另外一个`catch`块。如果一个方法只抛出一个受检异常，该异常就是该方法必须出现在`try`块且不能直接在流使用的唯一原因。在这种情况下，问问自己是否有方法可以避免受检异常。

消除受检异常最简单的方法是返回一个所需结果类型的*optional*（Item 55）。方法不再抛出受检异常，而是简单返回一个空可选。这种技术的缺点是方法无法返回任何详细说明其无法执行所需计算的额外信息。相比之下，异常具有描述性的类型，并可以导出方法提供额外信息（Item 70）。

你也可以通过将抛出异常的方法拆分为两个方法，将检查异常（checked exception）转换为未检查异常（unchecked exception）。第一个方法返回一个`boolean`，表示是否会抛出异常。这种 API 重构将调用序列从如下：

```java
// 使用检查异常的调用
try {
    obj.action(args);
} catch (TheCheckedException e) {
    ... // 处理异常情况
}
```

转变为如下所示：

```java
// 使用状态测试方法和未检查异常的调用
if (obj.actionPermitted(args)) {
    obj.action(args);
} else {
    ... // 处理异常情况
}
```

这种重构并不总是适用的，但在适用情况下，它可以让 API 使用起来更加顺手。虽然后者的调用序列并不比前者更漂亮，但重构后的 API 更具灵活性。如果程序员知道调用将会成功，或者乐意在失败时让线程终止，那么重构也允许这种简易的调用序列：

```java
obj.action(args);
```



如果你怀疑这种简易的调用将成为常态，那么这种 API 重构可能是合理的。生成的 API 本质上是 Item 69 中的状态测试方法 API，并且适用相同的限制：如果一个对象要在没有外部同步的情况下被并发访问，或者它会受到外部诱导的状态转换，那么这种重构是不恰当的，因为在调用`actionPermitted`和`action`之间对象的状态可能会发生变化。如果单独的`actionPermitted`方法会重复`action`方法的工作，则可能因为性能原因排除这种重构。

总而言之，当节使用时，检查异常可以增加程序的可靠性；当过度使用时，它们会让 API 的使用变得痛苦。如果调用者无法从失败中恢复，请抛出未检查异常。如果可能恢复且你希望*强制*调用者处理异常情况，请先考虑返回一个`optional`。只有在失败情况下提供的信息不足时，你才抛出检查异常。

## Item 72: 优先使用标准异常

区分资深程序员和缺乏经验程序员的一个特质是，资深人士追求并通常能实现高程度的代码复用。代码复用是好事，这一规则也不例外。Java 库提供了一系列异常，涵盖了大多数 API 大部分的抛出需求。

复用标准异常有许多好处。其中最重要的的一点是，它让你的 API 更容易学习和使用，因为它符合程序员已经熟悉的既定约定。其次是，使用你 API 的程序更容易阅读，因为它们不会被不熟悉的异常所困扰。最后（也是最不重要的一点），异常类更少意味着内存占用更小，加载类花费的时间更短。

最常重用的异常类型是`IllegalArgumentException`（Item 49）。当调用者传递的参数值不合适时，这通常是应该抛出的异常。例如，如果调用者在一个表示某些操作重复次数的参数中传递了一个负数，那么就抛出此异常。

另一个常用的重用异常是`IllegalStateException`。如果由于接收对象的状态导致调用是非合法的，这通常是应该抛出的异常。例如，如果调用者尝试在使用某些对象之前对其进行适当初始化，那么就抛出此异常。

可以认为，每种错误的方法调用都可以归结为非法参数或状态，但其他异常被标准地用于某些特定的非法参数和状态。如果调用者在禁止`null`值的参数中传递了`null`，约定规定抛出`NullPointerException`而不是`IllegalArgumentException`。同样，如果调用者在表示序列索引的参数中传递了一个超出范围的值，应该抛出`IndexOutOfBoundsException`而不是`IllegalArgumentException`。

另一个可复用的异常是`ConcurrentModificationException`。如果一个设计用于单线程（或带有外部同步）的对象检测到它正在被并发修改，则应该抛出此异常。这种异常充其量只是一个提示，因为无法可靠地检测到并发修改。

最后一个值得注意的标准异常是`UnsupportedOperationException`。如果对象不支持尝试的操作，则抛出此异常。它的使用很稀，因为大多数对象都支持它们的所有方法。该异常由那些未能实现其实现的接口定义的定义或多个*可选操作*的类使用。例如，一个只允许追加的`List`实现如果有人尝试从列表中删除元素，就会抛出此异常。

**不要**直接复用`Exception`、`RuntimeException`、`Throwable`或`Error`。将这些类视为抽象类来对待。你无法可靠地测试这些异常，因为它们是方法可能抛出的其他异常的父类。

下表总结了最常重用的异常：

| Exception | 使用时机 |
| :--- | :--- |
| `IllegalArgumentException` | 非空参数值不合适 |
| `IllegalStateException` | 对象状态不适用于方法调用 |
| `NullPointerException` | 在禁止的情况下参数值为 null |
| `IndexOutOfBoundsException` | 索引参数值超出出范围 |
| `ConcurrentModificationException` | 在禁止的情况下检测到对对象的并发修改 |
| `UnsupportedOperationException` | 对象不支持该方法 |

虽然这些是目前最常见的异常，但在需要的情况下也可以复用其他异常。例如，如果你正在实现算术对象（如复数或有理数），复用`ArithmeticException`和`NumberFormatException`是合适的。如果某个异常符合你的需求，尽管去使用它，但仅当在你抛出异常的情况下与该异常的文档一致时才：复用必须基于记录的语义，而不仅仅是名称。此外，如果你想添加更多细节，可以对标准异常进行子类化（Item 75），但记住异常是序列化的（第 12 章）。仅此一点就足以在没有正当的情况下编写自己的异常类。

## Item 73: 抛出符合抽象的异常

当一个方法抛出的异常与其执行的任务之间没有明显的联系时，这会令人困惑。这通常发生在方法传播了由低层抽象抛出的异常时。这不仅令人困惑，还会用实现细节细节污染高层的 API。如果高层的实现在稍后的发布中发生变化，它所抛出的异常也会随之改变，可能会破坏现有的客户端程序。

为了避免这个问题，`高层应该捕获低层异常，并取而代之抛出可以用高层抽象来解释的异常。`这种惯用法被称为`异常翻译`（exception translation）：

```java
// Exception Translation

try {

    ... // 使用低层抽象执行我们的任务

} catch (LowerLevelException e) {

    throw new HigherLevelException(...);

}
```

这里是一个来自`AbstractSequentialList`类的异常翻译示例，该类是`List`接口的一个`骨架实现`（Item 20）。在这个示例中，异常翻译是由`List<E>`接口中`get`方法的规范规定的：

```java
/**
 * 返回此列表中指定位置的元素。
 * @throws IndexOutOfBoundsException 如果索引超出范围
 *          ({code index <  0 || index >= size()}).
 */
public E get(int index) {
    ListIterator<E> i = listIterator(index);
    try {
        return i.next();
    } catch (NoSuchElementException e) {
        throw new IndexOutOfBoundsException("Index: " + index);
    }
}
```

在低层异常可能对调试导致高层异常的问题的人有帮助的情况下，会调用一种名为`异常链`（exception chaining）的异常翻译的特殊形式。低层异常（`cause`）被传递给高层异常，高层异常提供了一个访问器方法（`Throwable`的`getCause`方法）来获取低层异常：

```java
// Exception Chaining

try {

    ... // 使用低层抽象执行我们的任务

} catch (LowerLevelException cause) {

    throw new HigherLevelException(cause);

}
```

高层异常的构造函数将原因传递给一个感知链的（chaining-aware）父类构造函数，因此它最终会被传递给`Throwable`的感知链构造函数之一，例如`Throwable(Throwable)`：

```java
// Exception with chaining-aware constructor

class HigherLevelException extends Exception {

    HigherLevelException(Throwable cause) {

        super(cause);

    }

}
```

大多数标准异常都有具有链链的构造函数。对于没有这种构造函数的异常，你可以使用`Throwable`的`initCause`方法设置原因。异常链不仅允许你通过程序方式访问原因（通过`getCause`），还将原因的堆栈跟踪集成到高层异常的堆栈跟踪中。

`虽然异常翻译优于从低层盲目传播异常，但不应过度使用它。`在可能的情况下，处理低层异常的最佳方法是避免它们，即确保低层方法成功执行。有时你可以通过在将参数传递给低层之前检查高层方法参数的有效性来实现。

如果无法防止低层异常，最好的办法是让高层静静地规避这些异常，将高层方法的调用者与低层问题隔离开。在这种情况下，使用如`java.util.logging`等适当的日志记录设施记录异常。这允许程序员调查问题，同时保护客户端代码和用户免受其影响。

总之，如果无法防止或处理低层异常，请使用异常翻译，除非低层方法恰好保证其所有异常对于高层来说都是合适的。链（Chaining）兼顾了两者的优势：它允许你抛出一个合适的高层异常，同时捕获底层原因以便失败分析（Item 75）。

## Item 74: 为每个方法抛出的所有异常编写文档

对方法所抛出的异常的描述是正确使用该方法所需的文档的重要部分。因此，花时间仔细记录每个方法抛出的所有异常（Item 56）至关重要。

`始终使用 Javadoc 的 @throws 标签单独声明受检查异常，并精确记录每种异常被抛出的条件`。不要走捷径声明一个方法抛出它可能抛出的某些异常类的超类。作为一个极端例子，不要声明一个公共方法`throws Exception`，或者更糟糕的`throws Throwable`。除了无法为方法用户提供关于抛出异常的任何指导外，这种声明还极大地阻碍了该方法的使用。此建议的一个例外是`main`方法，它可以安全地声明抛出`Exception`，因为它只被虚拟机调用。

虽然语言没有要求程序员声明方法能够抛出的未检查异常，但像记录受检查异常一样仔细记录它们是明智的。未检查异常通常代表编程错误（Item 70），让程序员熟悉他们可能犯的错误有助于他们避免这些错误。方法抛出的未检查异常的良好列表有效地描述了其成功执行的`前提条件`。每个公共方法的文档都描述其前提条件（Item 56）是本质的，而记录其未检查异常是满足这一要求的最佳方法。

接口方法记录其可能抛出的未检查异常尤为重要。这些文档构成了接口`通用合约`的一部分，并使多个实现之间具有共同行为。

`使用 Javadoc 的 @throws 标签记录方法可能抛出的每个异常，但不要对未检查异常使用 throws 关键字。`让使用你 API 的程序员了解哪些异常是受检查的、哪些是未检查的很重要，因为在这两种情况下程序员的责任是不同的。在方法声明中没有相应 throws 子句的情况下，由 Javadoc @throws 标签生成的文档会为程序员提供强有力的视觉提示，说明该异常是未检查的。

如果一个类中的许多方法由于相同的原因抛出异常，你可以在该类的文档注释中记录该异常，而不是为每个方法单独进行记录。一个常见的例子是`NullPointerException`。在类的文档注释中写道：“此类中的所有方法如果在在任何参数中传递了空对象引用，都会抛出`NullPointerException`”或类似的话是完全可以的。

总而言之，记录你所编写的每个方法可能抛出的每一个异常。这对于未检查异常和受检异常、对于抽象方法和具体方法都是如此。这些文档应该以 doc 注释中`@throws`标签的形式存在。在方法的`throws`子句中单独声明每个受检异常，但不要声明未检查异常。如果你未能记录你的方法可能抛出的异常，他人将难以或无法有效地使用你的类和接口。

## 事项 75：在详详细消息中包含详细的失败捕获信息

当程序由于未捕获的异常而失败时，系统会自动打印出异常的堆栈跟踪（stack trace）。堆栈跟踪包含异常的字符串表示，即调用其`toString()`方法的结果。这通常由异常的类名后跟其详细消息组成。通常情况下，这是程序员或站点可靠性工程师在调查软件故障时拥有的唯一信息。如果失败无法轻易重现，可能难以或无法获取更多信息。因此，让异常的`toString()`方法尽可能返回更多有关失败原因的信息至关重要。换句话说，异常的详细消息应该捕获失败的情况以便供后续分析。

为了捕获失败，异常的详细消息应该包含导致异常的所有参数和字段的值。例如，`IndexOutOfBoundsException`的详细消息应该包含下界、上界以及未能落在界限之间的索引值。这些信息反映了大量关于失败的情况。这三个值中的任何一个或全部都可能是错误的。索引可能比下界小 1，或者等于上界（“栅栏柱错误”），也可能是一个离谱的值，太低或太高。下界可能大于上界（严重的内部不变性失效）。这些情况中的每一种都指向一个不同的问题，如果你知道正在寻找什么样的错误，将极大地有助于诊断。

有一个注意事项是关于安全敏感信息的。由于在诊断和修复软件问题的过程中，堆栈跟踪可能会被很多人看到，因此不要在详细消息中包含密码、加密密钥等。

虽然在异常的详细消息中包含所有相关数据至关重要，但包含大量的散文描述通常是不重要的。堆栈跟踪旨在结合文档以及在必要时结合源代码一起进行分析。它通常包含了抛出异常的精确文件和行号，以及堆栈上所有其他方法调用的文件和行号。对失败的长篇散文描述是多余的；可以通过阅读文档和源代码获取这些信息。

异常的详细消息不与用户级错误消息混淆，后者必须对终端用户是可以理解的。与用户级错误消息不同，详细消息主要供程序员或站点可靠性工程师在分析故障时使用。因此，信息内容远比可读性更重要。用户级错误消息通常是本地化的，而异常详细消息很少是本地化的。

确保异常的详细消息中包含足够的失败捕获信息的一种方法，是在构造函数中要求这些信息，而不是要求一个字符串详细消息。这样详细消息就可以自动生成以包含这些信息。例如，与其使用`String`构造函数，`IndexOutOfBoundsException`本可以有一个像这样的构造函数：

```java
/**
 * 构建一个 IndexOutOfBoundsException。
 *
 * @param lowerBound 最合法的索引值
 * @param upperBound 最高合法的索引值加一
 * @param index      实际索引值
 */
public IndexOutOfBoundsException(int lowerBound, int upperBound,
                                  int index) {
    // 生成一个捕获失败的详细消息
    super(String.format(
            "Lower bound: %d, Upper bound: %d, Index: %d",
            lowerBound, upperBound, index));
    // 保存失败信息以便程序化访问
    this.lowerBound = lowerBound;
    this.upperBound = upperBound;
    this.index = index;
}
```

从 Java 9 开始，`IndexOutOfBoundsException`终于获得了一个接受`int`类型`index`参数的构造函数，但遗憾的是它省略了`lowerBound`和`upperBound`参数。更通地说，Java 库并没有大量使用这种惯用法，但强烈建议这样做。它让抛出异常的程序员能够轻松捕获失败。事实上，它让程序员很难不去捕获失败！实际上，这种惯用法在异常类中集中了生成高质量详细消息的代码，而不是要求该类的每个用户都重复地生成详细消息。

正如 [事项 70] 所建议，异常为其失败捕获信息提供访问器方法（上述示例中的`lowerBound`、`upperBound`和`index`）可能是适当的。在受检异常上提供此类访问器比在未检查异常上重要，因为失败捕获信息对于从失败中恢复可能有用。虽然罕见（尽管并非不可能），程序员可能希望程序化访问未检查异常的细节。然而，即使对于未检查异常，从一般原则上来说提供这些访问器似乎也是明智的（[事项 12]，第 57 页）。

## 事项 76：追求失败原子性

在对象抛出异常后，通常希望该对象仍然处于定义良好的、可状态，即使失败发生在执行操作的过程中。这对于预期调用者进行恢复的受检异常尤为如此。通常来说，失败的方法调用应该让对象保持在调用之前的状态。具有这种属性的方法被称为失败原子。

有几种方法可以实现这种效果。最简单的方法是设计不可变对象（事项 17）。如果对象是不可变的，失败原子性就是免费的。如果操作失败，它可能会阻止新对象的创建，但永远不会让现有对象处于不一致的状态，因为每个对象的状态在创建时是一致的，之后不会修改。

对于操作可变对象的方法，实现失败原子性的常用方法是在执行操作之前检查参数的有效性（事项 49）。这使得大多数异常在修改开始之前被抛出。例如，考虑 [事项 7] 中的`Stack.pop`方法：

```java
public Object pop() {
    if (size == 0) {
        throw new EmptyStackException();
    }
    Object result = elements[--size];
    elements[size] = null; // 消除失效引用
    return result;
}
```



如果消除了初始的大小检查，该方法在尝试从空栈中弹出元素时仍然会抛出异常。然而，它会使`size`字段处于一种不一致（负数）状态，导致未来对该对象的任何方法调用都会失败。此外，`pop`方法抛出的`ArrayIndexOutOfBoundsException`对于该抽象来说是不恰当的（Item 73）。

实现失败原子性（failure atomicity）的另一种相关方法是调整计算顺序，使得任何可能失败的部分发生在修改对象的部分之前。当在不执行部分计算的情况下无法检查参数时，这种方法是前一种方法的自然扩展。例如，考虑`TreeMap`的情况，它的元素是根据某种顺序排序的。为了向`TreeMap`中添加元素，该元素必须是可以使用`TreeMap`排序进行比较的类型。尝试添加类型错误的元素时，在树被任何方式修改之前，由于在树中搜索元素，自然会因`ClassCastException`失败。

实现失败原子性的第三种方法是在对象的临时副本上执行操作，一旦操作完成，用临时副本替换对象的内容。当数据存储在临时数据结构后可以更快地执行计算时，这种方法自然会发生。例如，某些排序函数在排序之前会将输入列表拷贝到数组中，以减少排序内部循环中访问元素的代价。这样做是为了性能考虑，但作为一个额外的好处，它确保了如果排序失败，输入列表将保持完好无损。

实现失败原子性的最后且远不常见的方法是编写*恢复代码*（recovery code），来拦截操作中途发生的故障，并使对象状态回滚到操作开始之前的点。这种方法主要用于持久化（基于磁盘的）数据结构。

虽然失败原子性通常是理想的，但它并不总是可以实现的。例如，如果两个线程尝试在没有适当同步的情况下并发修改同一个对象，该对象可能会处于不一致状态。因此，假设在捕获到`ConcurrentModificationException`后对象仍然可用是错误的。错误（Errors）是不可恢复的，因此在抛出`AssertionError`时，你甚至不需要尝试保持失败原子性。

即使在可以实现失败原子性的情况下，它也不总是理想的。对于某些操作，这会显著增加成本或复杂性。尽管如此，一旦你意识到这个问题，实现失败原子性通常是免费且容易的。

总结来说，根据原则，任何作为方法规范一部分的生成的异常，都应该让对象保持在方法调用之前的原始状态。如果违反了这一规则，API 文档应该清楚地指示对象将处于什么状态。遗憾的是，现有的许多 API 文档未能达到这一理想。

### Item 77：不要忽略异常

虽然这个建议看起来显而易见，但它被违反的频率高到值得重复强调。当 API 的设计者声明一个方法会抛出异常时，他们正试图告诉你一些信息。不要忽略它！通过将方法调用封装在`try`语句中并让`catch`块为空，可以很容易地忽略异常：

```java
// 空 catch 块忽略了异常 - 非常可疑！
try {
    ...
} catch (SomeException e) {
}
```

空的`catch`块违背了异常的目的，异常的目的是迫使你处理异常情况。忽略异常等同于忽略火警报警——并将其关闭，让其他人没有机会查看是否真的发生了火灾。你可能侥幸逃过，但结果可能是灾难性的。每当你看到空的`catch`块，脑子里就应该响起警报。

在某些情况下，忽略异常是合适的。例如，在关闭`FileInputStream`时可能是合适的。你没有改变文件的状态，因此不需要执行任何恢复操作，而且已经从文件中读取了所需的信息，所以没有理由中止正在进行的操作。记录异常可能是明智的，这样如果这些异常频繁发生，你就可以调查这个问题。如果你选择忽略异常，`catch`块应该包含一条注释说明为什么这样做是，并且变量应该命名为`ignored`：

```java
Future<Integer> f = exec.submit(planarMap::chromaticNumber);
int numColors = 4; // 默认；保证对任何地图足够
try {
    numColors = f.get(1L, TimeUnit.SECONDS);
} catch (TimeoutException | ExecutionException ignored) {
    // 使用默认值：最小着是理想的，不是强制的
}
```

此项中的建议同样适用于受检异常（checked exceptions）和未受检异常（unchecked exceptions）。无论异常代表可预测的异常情况还是编程错误，用空的`catch`块忽略它都会导致程序在面对错误时静默运行。程序可能会在未来的任意时间失败，且在某个与问题源没有明显关系的代码点失败。正确处理异常可以完全避免失败。仅仅让异常向外传播，至少可以导致程序快速失败，并保留有助于调试的信息。

## 第 11 章：并发

线程允许允许多个活动并发进行。并发编程比单线程编程更困难，因为可能会出现更多问题，而且故障很难重现。你无法避免并发。它是平台固有的，如果你想从多核心处理器（现在已无处不在）获得良好的性能，这是要求的。本章包含了帮助你编写清晰、正确、文档良好的并发程序的建议。

### Item 78：同步对共享可变数据的访问

`synchronized`关键字确保一次只有一个线程可以执行方法或块。许多程序员仅将同步视为*互斥*（mutual exclusion）的手段，防止对象在被另一个线程修改时被观察到处于不一致的状态。在这种观点下，对象在创建时处于一致状态（Item 17），并在访问它的方法锁定。这些方法观察状态并可选地导致状态转换，将对象从一个一致状态转换为另一个。正确使用同步可以确保任何方法都不会观察到对象的不一致状态。

这种观点是正确的，但它只是故事的一部分。如果没有同步，一个线程的更改可能对其他线程可见。同步不仅防止线程观察到对象的不一致状态，还确保进入同步方法或块的每个线程看到由相同锁保护之前的所有修改。

语言规范保证读取或写入变量是原子的，除非该变量类型为`long`或`double` [JLS, 17.4, 17.7]。换之，读取除`long`或`double`以外的变量保证返回某个线程存储到该变量的值，即使多个线程在没有同步的情况下并发修改该变量。

你可能会听到有人说，为了提高性能，在读写原子数据时应该省去同步。这种建议是极其错误的。虽然语言规范保证了线程在读取字段时不会看到任意值，但它并不能保证一个线程写入的值对另一个线程可见。**线程之间的可靠通信以及互斥访问都需要同步。** 这是由于语言规范中一个被称为`memory model`（内存模型）的部分引起的，该模型规定了一个线程所做的更改在何时以及如何对其他线程变得的 [JLS, 17.4; Goetz06, 16]。

即使数据是原子级可读可写的，如果未能对共享可变数据的访问进行同步，后果也可能是毁灭性的。考虑从另一个线程停止一个线程的任务。库提供了`Thread.stop`方法，但该方法很久以前就被弃用了，因为它从本质上是`unsafe`的——使用它可能会导致数据损坏。**不要使用`Thread.stop`。** 从另一个线程停止线程的推荐方法是让第一个线程轮询一个`boolean`字段，该字段初始为`false`，但可以被第二个线程设置为`true`，以指示第一个线程停止自身。由于读取和写入`boolean`字段是原子的，一些程序员在访问该字段时省去了同步：

```java
// Broken! - 你预期这个程序会运行多久？
public class StopThread {
    private static boolean stopRequested;

    public static void main(String[] args)
            throws InterruptedException {
        Thread backgroundThread = new Thread(() -> {
            int i = 0;
            while (!stopRequested)
                i++;
        });
        backgroundThread.start();

        TimeUnit.SECONDS.sleep(1);
        stopRequested = true;
    }
}
```

你可能认为这个程序会运行大约一秒，之后主线程将`stopRequested`设置为`true`，导致后台线程的循环终止。然而，在我的机器上，该程序*从没有*停止：后台线程在无限循环！

问题在于，在缺乏同步的情况下，无法保证后台线程何时（如果会的话）能看到主线程对`stopRequested`值的更改。在没有同步的情况下，虚拟机将此代码转换为如下形式是完全可以的：

```java
while (!stopRequested)
    i++;
```

变为这段代码：

```java
if (!stopRequested)
    while (true)
        i++;
```

这种优化被称为`hoisting`（提升），而这正是 OpenJDK Server VM 所做的。结果是`liveness failure`（活跃性失败）：程序无法进展。解决这个问题的方法之一是对`stopRequested`字段的访问进行同步。该程序如预期地在大一秒后终止：

```java
// Properly 同步的协作式线程终止
public class StopThread {
    private static boolean stopRequested;

    private static synchronized void requestStop() {
        stopRequested = true;
    }

    private static synchronized boolean stopRequested() {
        return stopRequested;
    }

    public static void main(String[] args)
            throws InterruptedException {
        Thread backgroundThread = new Thread(() -> {
            int i = 0;
            while (!stopRequested())
                i++;
        });
        backgroundThread.start();

        TimeUnit.SECONDS.sleep(1);
        requestStop();
    }
}
```

（注：提供的同步块原始文本包含一些格式伪影/冗余；我已清理了逻辑以反映标准的 Java 语法，同时保留了文中描述的逻辑。）

避免此项目中所述问题的办法是不共享可变数据。要么共享不可变数据（Item 17），要么完全不共享。换句话之，`将可变数据限制在单个线程中`。如果你采用这一策略，对其进行记录是非常重要的，以便在程序演进过程中维持该策略。同时，深入理解你正在使用的框架和库也很重要，因为它们可能会引入你无法察觉的线程。

允许一个线程修改数据对象一段时间，然后与其他线程共享它是可以的，仅对共享对象引用的行为进行同步。只要该对象不再被修改，其他线程就可以在进一步同步的情况下读取该对象。此类对象被称为`有效不可变的` [Goetz06, 3.5.4]。将此类对象引用从一个线程转移到其他线程被称为`安全发布` [Goetz06, 3.5.3]。安全发布对象引用有很多方法：你可以将其作为类初始化的一部分存储在静态字段中；你可以将其存储在`volatile`字段、`final`字段或通过普通锁访问的字段中；或者你可以将其放入并发集合（Item 81）。

总之，`当多个线程共享可变数据时，每个读取或写入数据的线程都必须执行同步`。在没有同步的情况下，无法保证一个线程的更改对另一个线程可见。未能同步共享可变数据的代价是存活性失败和安全性失败。这些失败是最难调试的故障之一。它们可能是间歇性的且依赖于时间的，程序行为在不同的虚拟机（VM）之间可能会发生巨大变化。如果你只需要线程间的通信而不需要互斥，`volatile`修饰符是一种可以接受的同步形式，但正确使用它可能很棘手。

### Item 79: 避免过度同步

Item 78 警告了同步不足的危险。本项目涉及的是相反的问题。根据情况，过度同步会导致性能下降、死锁，甚至非确定性行为。

`为了避免存活性和安全性失败，永远不要在同步方法或块中将控制权交给客户端。`换句话说，在同步区域内部，不要调用设计为可重写的方法，或由客户端以函数对象形式提供的方法（Item 24）。从带有同步区域的类的来看，此类方法是`外来的（alien）`。该类不知道该方法在做什么，也对其没有控制。取决于外来方法的操作，从同步区域调用它可能会导致异常、死锁或数据损坏。

为了使这一点具体，考虑以下类，它实现了一个`可观察的（observable）`集合封装。它允许客户端在元素添加到集合时订阅通知。这是`Observer`模式 [Gamma95]。为了简单起见，该类没有在元素从集合中删除时提供通知，但提供这些也是简单的事。该类是基于 Item 18（90 页）中重用的`ForwardingSet`实现的：

```java
// Broken - 从同步块中调用了外来方法！
public class ObservableSet<E> extends ForwardingSet<E> {
    public ObservableSet(Set<E> set) { super(set); }

    private final List<SetObserver<E>> observers = new ArrayList<>();

    public void addObserver(SetObserver<E> observer) {
        synchronized(observers) {
            observers.add(observer);
        }
    }

    public boolean removeObserver(SetObserver<E> observer) {
        synchronized(observers) {
            return observers.remove(observer);
        }
    }

    private void notifyElementAdded(E element) {
        synchronized(observers) {
            for (SetObserver<E> observer : observers)
                observer.added(this, element);
        }
    }

    @Override public boolean add(E element) {
        synchronized(observers) {
            boolean added = super.add(element);
            if (added) {
                notifyElementAdded(element);
            }
            return added;
        }
    }

    @Override public boolean addAll(Collection<? extends E> c) {
        synchronized(observers) {
            boolean result = true;
            for (E element : c) {
                if (!add(element)) {
                    result = false;
                    break;
                }
            }
            return result;
        }
    }
}

interface SetObserver<E> {
    void added(ObservableSet<E> set, E element);
}
```

```java
public void added(ObservableSet<Integer> s, Integer e) {
    System.out.println(e);
    if (e == 23) {
        ExecutorService exec =
            Executors.newSingleThreadExecutor();
        try {
            exec.submit(() -> s.removeObserver(this)).get();
        } catch (ExecutionException | InterruptedException ex) {
            throw new AssertionError(ex);
        } finally {
            exec.shutdown();
        }
    }
}
```



值得注意的是，此程序在一个 `catch` 子句中捕获了两种不同类型的异常。这种非正式称为多异常捕获（multi-catch）的功能是在 Java 7 中引入的。它可以极大提高对多种异常类型具有相同行为的程序的清晰度，并减小程序体积。

当我们运行这个程序时，并没有得到异常，而是得到了死锁。后台线程调用 `s.removeObserver`，它尝试锁定 `observers`，但无法获取锁，因为主线程已经持有该锁。在此期间，主线程一直在等待后台线程完成观察者的移除，这解释了死锁的原因。

这个例子是人为构造的，因为观察者没有理由使用后台线程来取消订阅，但这种问题是真实的。在同步区域（synchronized regions）内部调用外部方法（alien methods）已导致许多真实系统（如 GUI 工具包）出现死锁。

在之前的两个例子（异常和死锁）中，我们是幸运的。受同步区域保护的资源（`observers`）在调用外部方法（`added`）时处于一致状态。假设你在同步区域内调用一个外部方法，而此时该同步区域保护的不变性临时失效了。由于 Java 编程语言中的锁是重入的，这种调用不会导致死锁。正如导致异常的第一个例子一样，调用线程已经持有了锁，因此该线程在尝试重新获取锁时将成功，尽管在锁所保护的数据上正在进行另一个逻辑上不相关的操作。这种失败的后果可能是灾难性的。本质上，锁未能完成任它的职责。重入锁简化了多线程面向对象程序的构建，但它们可能会将活跃性失败转变为安全性失败。

幸运的是，通过将外部方法的调用移到同步块之外，修复这类问题通常并不困难。对于 `notifyElementAdded` 方法，这涉及对 `observers` 列表拍摄“快照”，然后可以在没有锁的情况下安全地进行遍历。有了这一更改，之前的两个例子在运行时都不会再出现异常或死锁：

点击此处查看代码图片

### 移到同步块外的外部方法 - 开放调用

```java
private void notifyElementAdded(E element) {
    List<SetObserver<E>> snapshot = null;
    synchronized(observers) {
        snapshot = new ArrayList<>(observers);
    }
    for (SetObserver<E> observer : snapshot)
        observer.added(this, element);
}
```

事实上，有一种更好的方法将外部方法的调用移出同步块。库提供了一种名为 `CopyOnWriteArrayList`（项目 81）的并发集合，它是为了这一目的量身定制的。这个 `List` 实现是 `ArrayList` 的变体，其中所有的修改操作都通过创建整个底层数组的全新副本来实现。因为内部数组永远不会被修改，所以遍历不需要锁定且速度非常快。对于大多数用例，`CopyOnWriteArrayList` 的性能将是糟糕的，但它对于很少修改且经常遍历的观察者列表来说是完美的。

如果将列表修改为使用 `CopyOnWriteArrayList`，则 `ObservableSet` 的 `add` 和 `addAll` 方法不需要更改。以下是类的剩余部分的结构。注意，这里没有任何显式的同步：

点击此处查看代码图片

### 使用 CopyOnWriteArrayList 的线程安全可观察集合

```java
private final List<SetObserver<E>> observers =
    new CopyOnWriteArrayList<>();

public void addObserver(SetObserver<E> observer) {
    observers.add(observer);
}

public boolean removeObserver(SetObserver<E> observer) {
    return observers.remove(observer);
}

private void notifyElementAdded(E element) {
    for (SetObserver<E> observer : observers)
        observer.added(this, element);
}
```

在同步区域之外调用的外部方法被称为开放调用（open calls）[[Goetz6, 10.1.4]]。除了防止失败外，开放调用还可以极大提高并发性。外部方法可能会运行任意长的时间。

**原则上，你应该在同步区域内尽可能少地工作。** 获取锁，检查共享数据，根据需要对其进行转换，然后释放锁。如果你必须执行某些耗时的活动，请找一种方法将其移出同步区域，同时不要违背项目 78 中的准则。

本项目的第一个部分是关于正确性的。现在让我们简单看一眼性能。虽然自 Java 早期以来，同步的成本已经大幅下降，但避免过度同步比以往任何时候都重要。在多核世界中，过度同步的真实代价不是获取锁所花费的 CPU 时间，而是竞争：并行化机会的丧失，以及为了确保每个核心都拥有内存的一致视图而引入的延迟。过度同步的另一个隐藏成本是它可以限制 JVM 优化代码的能力。

如果你正在编写一个可变类，你有两个选择：你可以省略所有同步，并在需要并发时允许客户端外部同步；或者你可以内部同步，使类成为线程安全的（项目 82）。只有当你通过内部同步实现的并发性显著高于客户端锁定整个对象时，你才应该后者。`java.util` 中的集合（过时的 `Vector` 和 `Hashtable` 除外）采用前者方法，而 `java.util.concurrent` 中的集合则采用后者（项目 81）。

在 Java 早期，许多类违反了这些准则。例如，`StringBuffer` 实例几乎总是单线程使用的，但它们却执行内部同步。正因如此，`StringBuffer` 被 `StringBuilder` 取代，后者只是一个没有同步的 `StringBuffer`。同样，这也是 `java.util.Random` 中线程安全的伪随机数生成器被 `java.util.concurrent.ThreadLocalRandom` 中的非同步实现取代的主要原因之一。如果不确定，不要对你的类进行同步，但要记录它不是线程安全的。

如果你确实在类内部进行同步，可以使用各种技术来实现高并发，例如锁拆分、锁分段和非阻塞并发控制。这些技术超出了本书的范围，但在其他地方有讨论 [Goetz6, Herlihy08]。

如果一个方法修改了静态字段，并且该方法极可能从多个线程调用，那么你*必须*在内部对该字段的访问进行同步（除非该类可以容忍非确定性行为）。多线程客户端无法对此类方法执行外部同步，因为无关的客户端可以在不同步的情况下调用该方法。即使该字段是私有的，它本质上也是一个全局变量，因为可以被无关的客户端读取和修改。项目 78 中的方法 `generateSerialNumber` 所使用的 `nextSerialNumber` 字段就说明了这种情况。

总而言之，为了避免死锁和数据损坏，永远不要在同步区域内调用外来方法（alien method）。更普遍地说，尽量将你在同步区域内执行的工作量减少到最低。在设计可变类时，要考虑它是否应该处理自己的同步。在多核时代，避免过度同步比以往任何时候都重要。只有在有充分理由的情况下，才在类内部进行同步，并清楚地记录你的决策（项目 82）。

### 项目 80：优先使用执行器、任务和流，而不是线程

本书的第一版包含了一个简单的*工作队列*代码 [Bloch01, 项目 49]。该类允许客户端将工作存入队列，由后台线程进行异步处理。当工作队列不再需要时，客户端可以调用一个方法，请求后台线程在完成队列中的任何现有工作后优雅地自毁。该实现顶多只是一个玩具，但尽管如此，它仍然需要一整页微妙且精细的代码，这类代码如果处理得不当，极易导致安全性和活跃性故障。幸运的是，现在没有必要再写这种代码了。

当本书的第二版出版时，`java.util.concurrent` 已经被加入到 Java 中。这个包包含了一个*执行器框架*（Executor Framework），这是一个灵活的、基于接口的任务执行设施。要创建一个在各方面都优于本书第一版的工作队列，只需要一行代码：

点击此处查看代码图像

```
ExecutorService exec = Executors.newSingleThreadExecutor();
```

以下是提交一个可运行对象执行的方法：

```
exec.execute(runnable);
```

以及如何告诉执行器优雅地终止（如果你没有做到这一点，你的虚拟机很可能不会退出）：

```
exec.shutdown();
```

你可以使用执行器服务做*更多*事情。例如，你可以等待特定任务完成（使用 `get` 方法，如项目 79 第 319 页所示），你可以等待一组任务中的任何一个或所有任务完成（使用 `invokeAny` 或 `invokeAll` 方法），你可以等待执行器服务终止（使用 `awaitTermination` 方法），你可以在任务完成时逐个检索其任务结果（使用 `ExecutorCompletionService`），你可以调度任务在特定时间运行或定期运行（使用 `ScheduledThreadPoolExecutor`），等等。

如果你希望用多个线程来处理来自队列的请求，只需调用不同的静态工厂方法，它会创建一个不同类型的执行器服务，称为*线程池*。你可以创建一个具有固定数量或可变线程的线程池。`java.util.concurrent.Executors` 类包含了静态工厂，可以提供你可能需要的绝大多数执行器。然而，如果你想要一些不寻常的东西可以直接可以使用 `ThreadPoolExecutor` 类。该类允许你配置线程池操作的几乎每一个方面。

为特定应用程序选择执行器服务可能是很棘手的。对于小型程序或负载轻的服务器，`Executors.newCachedThreadPool` 通常是一个很好的选择，因为不需要配置且通常能“做正确的事”。但对于负载沉重的生产环境服务器，缓存线程池绝不是一个好的选择！在缓存线程池中，提交的任务不会排队，而是被立即交给一个线程执行。如果没有可用的线程，就会创建一个新的。如果服务器负载重到所有 CPU 都已满载，并且有更多任务到达，就会创建更多线程，这只会让情况变得更糟。因此，在负载沉重的生产服务器上，最好使用 `Executors.newFixedThreadPool`（它提供一个具有固定数量线程的池）或直接使用 `ThreadPoolExecutor` 类以获得最大的控制。

你不仅应该克制编写自己的工作队列，而且通常应该避免直接与线程打交道。当你直接与线程工作时，`Thread` 既是工作单元，又是执行它的机制。在执行器框架中，工作单元和执行机制是分离的。核心抽象是工作单元，即*任务*（task）。任务有两种类型：`Runnable` 及其近亲兄弟 `Callable`（它类似于 `Runnable`，区别在于它可以返回一个值并可以抛出任意异常）。执行任务的通用机制是*执行器服务*（executor service）。如果你从任务来思考并让执行器服务为你执行它们，你就获得了灵活性来选择合适的执行策略以满足你的需求，并在需求变化时更改策略。本质上，执行器框架对执行所做的工作，就像集合框架对聚合所做的那样。

在 Java 7 中，执行器框架被扩展以支持 fork-join 任务（分叉合并任务），这种任务由一种特殊的执行器服务（fork join pool）运行。fork-join 任务由 `ForkJoinTask` 表示，可以被分成更小的子任务，组成 `ForkJoinPool` 的线程不仅处理这些任务，还会相互“偷取”任务以确保所有线程保持忙碌，从而提高 CPU 利用率、吞吐量并降低延迟。编写和调优 fork-join 任务是复杂的。并行流（项目 48）是基于 fork join 池编写的，允许你以很小的努力利用它们的性能优势，只要它们适用于当前任务。

对执行器框架的处理超出了本书的范围，但感兴趣的读者被引向《Java 并发编程》[Goetz06]。

### 项目 81：优先使用并发工具，而不是 wait 和 notify

本书的第一版专门用一个项目介绍了正确使用 `wait` 和 `notify` [Bloch01, 项目 50]。它的建议仍然有效，并总结在项目的末尾，但这些建议已比以前没那么重要。这是因为使用 `wait` 和 `notify` 的理由少得多。自从 Java 5 以来，平台提供了更高层的并发工具，可以完成你以前必须在 `wait` 和 `notify` 之上手动编写的事情。考虑到正确使用 `wait` 和 `notify` 的困难，你应该使用这些高层并发工具。

`java.util.concurrent` 中的高层工具分为三类：执行器框架（在项目 80 中已简要介绍）、并发集合和同步器。并发集合和同步器将在在本项目中简要介绍。

并发集合是 `List`、`Queue` 和 `Map` 等标准集合接口的高性能并发实现。为了提供高并发性，这些实现在其内部管理自身的同步机制（Item 79）。因此，无法从并发集合中排除并发活动；锁定它只会减慢程序的速度。

由于你无法在并发集合上排除并发活动，因此无法在它们上对方法调用进行原子的组合。因此，并发集合接口配备了状态依赖型修改操作（state-dependent modify operations），这些操作将多个原语组合成单个原子操作。这些操作在并发集合上被证明非常有用，因此它们在 Java 8 中通过默认方法被添加到相应的集合接口中（Item 21）。

例如，`Map` 的 `putIfAbsent(key, value)` 方法在键不存在时为该键插入一个映射并返回与该键关联的旧值；如果不存在则返回 `null`。这使得实现线程安全的规范化映射（canonicalizing maps）变得简单。该方法模拟了 `String.intern` 的行为：

点击此处查看图片

```java
// 基于 ConcurrentMap 实现的并发规范化映射 - 并非最优
private static final ConcurrentMap<String, String> map =
    new ConcurrentHashMap<>();

public static String intern(String s) {
    String previousValue = map.putIfAbsent(s, s);
    return previousValue == null ? s : previousValue;
}
```

事实上，你可以做得更好。`ConcurrentHashMap` 针对检索操作（如 `get`）进行了优化。因此，值得先调用 `get`，只有在 `get` 显示有必要时才调用 `putIfAbsent`：

点击此处查看图片

```java
// 基于 ConcurrentMap 实现的并发规范化映射 - 更快！
public static String intern(String s) {
    String result = map.get(s);
    if (result == null) {
        result = map.putIfAbsent(s, s);
        if (result == null)
            result = s;
    }
    return result;
}
```

除了提供出色的并发性外，`ConcurrentHashMap` 还非常快。在我的机器上，上述 `intern` 方法比 `String.intern` 快六倍以上（但记住，`String.intern` 必须采用某些策略来防止在长寿应用中内存泄漏）。并发集合使得同步集合（synchronized collections）很大程度上过时了。例如优先使用 `ConcurrentHashMap` 而不是 `Collections.synchronizedMap`。简单地将同步映射替换为并发映射就可以大幅提高并发应用程序的性能。

某些集合接口扩展了阻塞操作（blocking operations），这些操作会等待（或阻塞）直到可以成功执行为止。例如，`BlockingQueue` 继承自 `Queue` 并添加了几个方法，包括 `take`，它会从队列中移除并返回头部元素，如果队列为空则等待。这使得阻塞队列可以用于工作队列（也称为生产者-消费者队列），一个或多个生产者线程向其入队工作项，一个或多个消费者线程在项目可用时从其出队并处理。正如你所预期的，大多数 `ExecutorService` 实现（包括 `ThreadPoolExecutor`）都使用 `BlockingQueue`（Item 80）。

同步器（Synchronizers）是允许线程相互等待的对象，允许它们协调自己的活动。最常用的同步器是 `CountDownLatch` 和 `Semaphore`。不常用的是 `CyclicBarrier` 和 `Exchanger`。最强大的同步器是 `Phaser`。

倒计数器（Countdown latches）是单次使用的屏障，允许一个或多个线程等待一个或多个其他线程完成某事。`CountDownLatch` 的唯一构造函数接收一个 `int` 参数，表示在所有等待线程允许继续之前必须在计数器上调用 `countDown` 方法的次数。

在这个简单的原语之上构建实用的工具出奇地简单。例如，假设你想构建一个简单的框架来为并发执行的动作计时。该框架由单个方法组成，接收一个用于执行动作的执行器、一个代表并发执行动作数量的并发级别，以及一个代表动作的 runnable。在计时线程启动闹钟之前，所有工作线程都已准备好运行该动作。当最后一个工作线程准备好运行该动作时，计时线程“鸣发令枪”，允许工作线程执行该动作。一旦最后一个工作线程完成动作执行，计时线程就会停止闹钟。直接在 `wait` 和 `notify` 之上实现这种逻辑至少将是混乱的，但在 `CountDownLatch` 之上实现却出奇地简单：

点击此处查看图片

```java
// 用于并发执行计时的简单框架
```



`public static long time(Executor executor, int concurrency, Runnable action) throws InterruptedException` {

    `CountDownLatch ready = new CountDownLatch(concurrency);`

    `CountDownLatch start = new CountDownLatch(1);`

    `CountDownLatch done = new CountDownLatch(concurrency);`

    `for (int i = 0; i < concurrency; i++)` {

        `executor.execute(() ->` {

            `ready.countDown();` // 告诉计时器我们准备好了

            `try` {

                `start.await();` // 等待伙伴也就绪

                `action.run();`

            } `catch (InterruptedException e)` {

                `Thread.currentThread().interrupt();`

            } `finally` {

                `done.countDown();` // 告诉计时器我们完成了

            }

        });

    }

    `ready.await();` // 等待所有工作就绪

    `long startNanos = System.nanoTime();`

    `start.countDown();` // 它们开始了！

    `done.await();` // 等待所有工作完成

    `return System.nanoTime() - startNanos;`

}

注意该方法使用了三个倒计数器。第一个 `ready` 由工作线程用于告知计时器它们已就绪。工作线程随后在第二个屏障 `start` 上等待。当最后一个工作线程调用 `ready.countDown()` 时，计时线程记录开始时间并调用 `start.countDown()`，允许所有工作线程继续。然后计时线程等待第三个屏障 `done`，直到最后一个工作线程完成动作并调用 `done.countDown()`。一旦发生这种情况，计时线程醒来并记录结束时间。

还有一些细节需要注意。传递给 `time` 方法的执行器必须允许创建至少等于并发级别的线程，否则测试将永远不会完成这被称为*线程饥饿死锁*（thread starvation deadlock）[Goetz06, 8.1.1]。如果工作线程捕获了 `InterruptedException`，它使用 `Thread.currentThread().interrupt()` 惯用法重新断中断并从其 `run` 方法返回。这允许执行器根据其意愿处理中断。注意使用 `System.nanoTime()` 对活动进行计时。对于间隔计时，请始终使用 `System.nanoTime()` 而不是 `System.currentTimeMillis()`。`System.nanoTime()` 更加准确和精确，且不受系统实时钟调整的影响。最后，请注意除非 `action` 执行了大量工作（例如一秒或更多），否则此示例中的代码将无法产生准确的计时。准确的微基准测试是非常困难的，最好借助如 `jmh` 等专用框架 [JMH] 来进行。

本节仅触及了并发工具所能实现的功能的一角。例如，上一个示例中的三个计数计数器（countdown latches）可以用单个 `CyclicBarrier` 或 `Phaser` 实例来替换。生成的代码会更简洁一些，但可能更难理解。

虽然你应该始终优先使用并发工具而不是 `wait` 和 `notify`，但你可能需要维护使用 `wait` 和 `notify` 的遗留代码。`wait` 方法用于让线程等待某些条件。它必须在锁定其被调用对象的同步区域（synchronized region）内部被调用。以下是使用 `wait` 方法的标准惯用法：

```
// 使用 wait 方法的标准惯用法
synchronized (obj) {
    while (<条件不满足>)
        obj.wait(); // (释放锁，并在唤醒时重新获取)
    ... // 执行与条件相应的的操作
}
```

始终使用 wait 循环惯用法来调用 `wait` 方法；绝不要在循环之外调用它。循环的作用是在等待前后后测试条件。

在等待前测试条件并在条件已满足时跳过等待，对于确保**活性（liveness）**是必要的。如果条件已经满足，且在线程等待之前 `notify`（或 `notifyAll`）方法已经被调用，则无法保证线程一定能从等待中唤醒。

在等待后测试条件并在条件不满足时再次等待，对于确保**安全性（safety）**是必要的。如果线程在条件不满足的情况下继续操作，可能会破坏由锁保护的不变量。线程在条件不满足时唤醒有几个原因：

- 另一个线程可能在线程调用 `notify` 与等待线程唤醒之间获取了锁并改变了受保护的状态。
- 另一个线程可能在条件不时不无意或恶意地调用了 `notify`。通过在公共访问的对象上等待，类会暴露在这种破坏之下。公共访问对象的同步方法中的任何 `wait` 都容易受到这个问题的影响。
- 通知线程在唤醒等待线程时可能过于“慷慨”。例如，即使只有部分等待线程满足了条件，通知线程也可能调用 `notifyAll`。
- 等待线程可能（罕见地）在没有通知的情况下唤醒。这被称为*虚假唤醒*（spurious wakeup）[POSIX, 11.4.3.6.1; Java9-api]。

一个相关问题是使用 `notify` 还是 `notifyAll` 来唤醒等待线程。（记住，`notify` 唤醒一个等待线程（假设存在这样一个线程），而 `notifyAll` 唤醒所有等待线程。）有人说你应该始终使用 `notifyAll`。这是一个合理且保守的建议。它始终会产生正确的结果，因为它保证了你会唤醒那些需要唤醒的线程。你可能也会唤醒其他线程，但这不会影响程序的程序的正确性。这些线程会检查它们正在等待的条件，在发现条件为假后，将继续等待。

作为一种优化，如果可能处于等待集合中的所有线程都在等待同一个条件，并且一次时间只有一个线程能从条件变为真中获益，你可能会选择调用 `notify` 而不是 `notifyAll`。

即使满足了这些前提条件，可能也有理由使用 `notifyAll` 替替 `notify`。正如将 `wait` 调用放在循环中可以防止对公共访问对象的意外或恶意通知一样，使用 `notifyAll` 替 `notify` 可以防止来自无关线程的意外或恶意等待。否则，这些等待可能会“吞掉”一个关键通知，导致其预期的接收者无限等待。

总之，直接使用 `wait` 和 `notify` 就像在使用“并发汇编语言”编程，相比之下，`java.util.concurrent` 提供了高级别的语言。在新代码中很少有理由使用 `wait` 和 `notify`。如果你维护使用 `wait` 和 `notify` 的代码，请确保它始终在 `while` 循环内部使用标准惯用法来调用 `wait`。通常应优先使用 `notifyAll` 而不是 `notify`。如果使用 `notify`，必须非常小心以确保活性。

## 章节 82：记录线程安全性

一个类在方法被并发使用时的行为是其与客户端约的重要组成部分。如果你未能记录类行为的这一方面，其用户将被迫做出假设。如果这些假设是错误的，导致程序可能会出现同步不足（Item 78）或同步过度（Item 79 的情况。在任何情况下，都可能导致严重错误。

你可能会听到说，可以通过查看文档中是否有 `synchronized` 修饰符来判断一个方法是否是线程安全的。这在多个方面都是错误的。在正常运行时，Javadoc 的输出不包含 `synchronized` 修饰符，这很有道理。方法声明中 `synchronized` 修饰符的存在是一个实现细节，而不是 API 的一部分。它不能可靠地指示一个方法是线程安全的。

此外，认为 `synchronized` 修饰符的存在足以记录线程安全性的观点，体现了线程安全性是一个全或全无属性的误解。事实上，线程安全性有多个级别。为了实现安全的并发使用，类必须清楚地记录它支持什么种的线程安全性。以下列表总结了线程安全性的级别。并非详尽，但涵盖了常见情况：

- **不可变（Immutable）**——该类的实例看起来是常量。不需要外部同步。示例包括 `String`、`Long` 和 `BigInteger`（Item 17）。
- **无条件安全（Unconditionally thread-safe）**——该类的实例是可变的，但该类具有足够的内部同步，使其可以并发使用而不需要任何外部同步。示例包括 `AtomicLong` 和 `ConcurrentHashMap`。
- **条件安全（Conditionally thread-safe）**——与无条件安全类似，但某些方法需要外部同步才能安全使用。示例包括由 `Collections.synchronized` 包装的集合，其迭代器需要外部同步。
- **非线程安全（Not thread-safe）**——该类的实例是可变的。为了并发使用它们，客户端必须使用选择的外部同步来封装每个方法调用（或调用序列）。示例包括通用集合实现，如 `ArrayList` 和 `HashMap`。
- **线程敌性（Thread-hostile）**——即使每个方法调用都由外部同步封装，该类对于并发使用是不安全的。线程敌性通常源于在同步的情况下修改静态数据。没有人故意编写线程敌性的类；此类类通常是未能考虑并发的结果。当发现类或方法是线程敌性的时，通常会修复或废弃。Item 78 中的 `generateSerialNumber` 方法在没有内部同步的情况下将是线程敌性的，正如第 322 页所讨论的。

这些类别（线程敌性除外）大致对应《Java Concurrency in Practice》中的*线程安全性注解*，即 `Immutable`、`ThreadSafe` 和 `NotThreadSafe` [Goetz06, 附录 A]。上述分类法中的无条件安全和条件安全类别都包含在 `ThreadSafe` 注解下。

记录一个条件线程安全的类需要谨慎。你必须指明哪些调用序列需要外部同步，以及在执行这些序列时必须获取哪种锁（或在少数情况下是多个锁）。通常情况下，锁是实例本身的锁，但存在例外。例如，`Collections.synchronizedMap` 的文档是这样说的：

用户在遍历其任何集合视图时，必须手动对返回的 map 进行同步处理：

```java
Map<K, V> m = Collections.synchronizedMap(new HashMap<>());
Set<K> s = m.keySet();  // 不需要放在同步块中
    ...
synchronized(m) {  // 对 m 进行同步，而不是 s！
    for (K key : s)
        key.f();
}
```

未能遵循此建议可能会导致非确定性的行为。

类线程安全性的描述通常属于类的文档注释（doc comment），但具有特殊线程安全属性的方法应该在自己的文档注释中描述这些属性。没有必要记录枚举类型的不可变性。除非从返回类型可以显而易见，否则静态工厂必须记录返回对象的线程安全性，如上文 `Collections.synchronizedMap` 所示。

当一个类承诺使用一个公开访问的锁时，它允许客户端原子地执行一系列方法调用，但这种灵活性是需要代价的。它与高性能的内部并发控制不兼容，例如 `ConcurrentHashMap` 等并发集合所使用的那种类型。此外，客户端可以通过长时间持有公开访问的锁来发起拒绝服务攻击。这可能是无意的，也可能是故意的。

为了防止这种拒绝服务攻击，你可以使用 `private lock object` 而不是使用同步方法（同步方法意味着使用一个公开访问的锁）：

```java
// 私有锁对象惯用法 - 防止拒绝服务攻击
private final Object lock = new Object();
public void foo() {
    synchronized(lock) {
        ...
    }
}
```

由于私有锁对象在类外部不可访问，客户端无法干扰该对象的同步。实际上，我们通过将锁对象封装在它所同步的对象中，应用了 Item 15 的建议。

注意 `lock` 字段被声明为 `final`。这防止你无意中更改其内容，否则可能导致灾难性的非同步访问 (Item 78)。我们通过最小化 `lock` 字段的可变性，应用了 Item 17 的建议。锁字段应该始终声明为 `final`。无论你使用普通的显示器锁（如所示）还是来自 `java.util.concurrent.locks` 包的锁，都是如此。

私有锁对象惯用法只能用于**无条件**线程安全的类。条件线程安全的类不能使用这种惯用法，因为它们必须记录客户端在执行某些方法调用序列时需要获取哪种锁。

私有锁对象惯用法特别适用于为继承而设计的类 (Item 19)。如果此类类使用其实例进行加锁，子类可能会很容易且无意地干扰基类的操作，反之亦然。通过对不同的用途使用同一个锁，子类和基类最终可能会“互相绊脚”。这不仅仅是一个理论问题；它在 `Thread` 类中发生过 [Bloch05, Puzzle 77]。

总结来说，每个类都应该用措辞仔细的散文描述或线程安全性注解清晰地记录其线程安全性属性。`synchronized` 修饰符在这些文档中不起任何作用。条件线程安全的类必须记录哪些方法调用序列需要外部同步，以及执行这些序列时应获取哪种锁。如果你编写一个无条件线程安全的类，考虑使用私有锁对象来代替同步方法。这可以保护你免受客户端和子类的同步干扰，并让你在后续发行版本中采用更复杂的并发控制方法时具有更大的灵活性。

## Item 83: 谨慎使用懒性初始化

`懒初始化`（Lazy initialization）是在推迟字段的初始化，直到需要该值。如果该值永远不会被需要，该字段永远不会被初始化。这种技术同时适用于静态字段和实例字段。虽然懒初始化主要是一种优化，但它也可以用于打破类和实例初始化中的有害循环 [Bloch05, Puzzle 51]。

与大多数优化一样，懒初始化的最佳建议是“除非你需要，否则不要这样做” (Item 67)。懒初始化是一双刃剑。它降低了初始化类或创建实例的代价，但是以增加访问懒初始化字段的代价为代价的。取决于这些字段最终有多少比例需要初始化、初始化它们的成本，以及每个字段在初始化后被访问的频率，懒初始化实际上（像许多“优化”一样）可能会损害性能。

尽管如此，懒初始化仍有其用处。如果一个字段仅在类的一部分实例上被访问，*并且*初始化该字段的成本很高，那么懒初始化可能是值得的。唯一确定的方法是测量类在使用和不使用懒初始化时的性能。

在多线程存在的情况下，懒初始化是棘手的。如果两个或多个线程共享一个懒初始化字段，则必须采用某种形式的同步，否则可能会导致严重的错误 (Item 78)。本节讨论的所有初始化技术都是线程安全的。

大多数情况下，正常初始化优于懒初始化。这是一个正常初始化实例字段的典型声明。注意 `final` 修饰符的使用 (Item 17)：

```java
// 实例字段的正常初始化
private final FieldType field = computeFieldValue();
```

如果你使用懒初始化来打破初始化循环，使用同步访问器是因为它是最简单的替代方案：

```java
// 实例字段的懒初始化 - 同步访问器
private FieldType field;
private synchronized FieldType getField() {
    if (field == null)
        field = computeFieldValue();
    return field;
}
```

这两个惯用法（正常初始化和带同步访问器的懒初始化）在应用于静态字段时保持不变，只需在字段和访问器声明中添加 `static` 修饰符。

如果你需要在静态字段上为了性能使用懒初始化，请使用懒初始化持有类惯用法。这种惯用法利用了类在使用之前不会初始化的 [JLS, 12.4.1]。它看起来如下：

```java
// 静态字段的懒初始化持有类惯用法
private static class FieldHolder {
    static final FieldType field = computeFieldValue();
}
private static FieldType getField() { return FieldHolder.field; }
```



当第一次调用`getField`时，它会首次读取`FieldHolder.field`，从而导致`FieldHolder`类的初始化。这种习用的精妙之处在于`getField`方法没有同步，并且仅执行了字段访问，因此懒加载几乎没有给访问带来任何额外成本。典型的虚拟机只会在初始化类时同步字段访问。一旦类初始化完成，虚拟机就会修补代码，使得后续对字段的访问不再涉及任何测试或同步。

如果你需要对实例字段进行性能优化的懒性初始化，请使用`双重检查模式`（double-check idiom）。这种模式避免了在初始化后访问字段时的锁开销（Item 79）。该模式背后的思想是检查两次字段的值（因此名为“双重检查”）：第一次不加锁检查，如果发现字段似乎未初始化，则再次加锁进行第二次检查。只有当第二次检查表明字段未初始化时，调用才会初始化字段。由于字段一旦初始化后就不需要锁定，因此将字段声明为`volatile`是至关重要的（Item 78）。以下是该模式：

```java
// 用于实例字段懒性初始化的双重检查模式
private volatile FieldType field;

private FieldType getField() {
    FieldType result = field;
    if (result == null)  // 第一次检查（不加锁）
        synchronized(this) {
            if (field == null)  // 第二次检查（加锁）
                field = result = computeFieldValue();
        }
    return result;
}
```

这段代码看起来可能有些复杂。特别是对局部变量（`result`）的需求可能并不清晰。这个变量的作用是确保在字段已经初始化的常见情况下，`field`只被读取一次。虽然不是严格必要的，但这可能提高性能，并根据低级并发编程的标准来说更加优雅。在我的机器上，上述方法比没有局部变量的直观版本快约 1.4 倍。

虽然你也可以将双重检查模式应用于静态字段，但没有理由这样做：懒性初始化持有者类模式是更好的选择。

双重检查模式有两个变体值得注意。有时，你可能需要懒性初始化一个可以容忍重复初始化的实例字段。如果你发现处于这种情况，可以使用一种省略第二次检查的双重检查模式变体。意不其料，它被称为`单次检查模式`（single-check idiom）。如下所示。注意`field`仍然被声明为`volatile`：

```java
// 单次检查模式 - 可能导致重复初始化！
private volatile FieldType field;

private FieldType getField() {
    FieldType result = field;
    if (result == null)
        field = result = computeFieldValue();
    return result;
}
```

本节中讨论的所有初始化技术都适用于原始类型字段以及对象引用字段。当双重检查或单次检查模式应用于数值原始类型字段时，字段的值将是与`0`（数值原始类型变量的默认值）对比而非`null`。

如果你不在乎*每个*线程是否重新计算字段的值，并且字段类型是`long`或`double`以外的原始类型，那么你可以选择从单次检查模式的字段声明中移除`volatile`修饰符。这种变体被称为`竞态单次检查模式`（racy single-check idiom）。它在某些架构上可以加速字段访问，代价是额外的初始化（每个访问该字段的线程最多一次）。这绝对是一种奇特的技术，不适用于日常使用。

总结，你应该正常初始化大多数字段，而不是懒性初始化。如果你为了实现性能目标或打破有害的初始化循环而必须懒性初始化字段，请使用适当懒性初始化技术。对于实例字段，使用双重检查模式；对于静态字段，使用懒性初始化持有者类模式。对于可以容忍重复初始化的实例字段，也可以考虑单次检查模式。

## Item 84：不要依赖线程调度器

当许多线程处于就绪状态时，线程调度器决定哪些线程可以运行以及运行多久。任何合理的操作系统都会尝试公平地做出判断，但策略可能会有所不同。因此，编写良好的程序不应该依赖此策略的细节。任何依赖线程调度器来保证正确性或性能的程序都是不可移植的。

编写健壮、响应迅速且可移植程序的最佳方法是确保*就绪*线程的平均数量不会过多。

另一种相关的技术（同样适用于此类）是调整线程优先级。**线程优先级是 Java 中可移植性差的特性之一。** 通过微调几个线程优先级来调整应用程序的响应速度并不合理，但这通常并非必要，而且不具备可移植性。试图通过调整线程优先级来解决严重的生存性（liveness）问题是不合理的。在您发现并修复根本原因之前，该问题可能会再次出现。

总之，不要依赖于线程调度器来保证程序的正确性。这样生成的程序既不健壮，也不具有可移植性。作为一个推论，不要依赖`Thread.yield`或线程优先级。这些设施仅仅是给调度器的提示。可以谨慎地使用线程优先级来提高已经运行良好的程序的服务质量，但绝不应该使用它们来“修复”一个勉强运行的程序。

# 第 12 节 序列化

本章涉及*对象序列化*（object serialization），这是 Java 用于将对象编码为字节流（*序列化*/serializing）以及从其编码重构对象（*反序列化*/deserializing）的框架。一旦对象序列化，其编码就可以从一个虚拟机发送到另一个虚拟机，或存储在磁盘上供以后反序列化。本章重点关注序列化的危险以及如何尽可能地减少这些危险。

## 项目 85：优先使用 Java 序列化的替代方案

当序列化在 1997 年加入 Java 时，已知它具有一定的风险。这种方法已经在一种研究语言（Modula-3）中尝试过，但从未在生产语言中用过。虽然程序员只需投入精力就能实现分布式对象的承诺很有吸引力，但其代价是不可见的构造函数以及 API 与实现之间模糊的边界，并可能在正确性、性能、安全和维护方面出现问题。支持者认为收益大于风险，但历史证明事实并非如此。

本书之前的版本描述的安全问题被证明与某些人所担心的那样严重。21 世纪初讨论的漏洞在接下来的十年中演变成了严重的攻击漏洞，其中著名的案例包括对旧金山大都会交通局市政铁路（SFMTA Muni）的勒索软件攻击，该攻击在 2016 年 11 月导致整个票务收集系统关闭了两天 [Gallagher16]。

序列化的一个根本问题是其*攻击面*（attack surface）太大而无法保护，并且在不断增长：对象图是通过调用`ObjectInputStream`上的`readObject`方法来反序列化的。该方法本质上是一个魔术构造函数，它可以实例化类路径上几乎任何类型的对象，只要该类型实现了`Serializable`接口。在反序列化字节流的过程中，该方法可以执行这些类型中任何一种类型的代码，因此*所有*这些类型的代码都是攻击面的一部分。

攻击面包括 Java 平台库中的类、第三方库（如 Apache Commons Collections）中的类以及应用程序本身中的类。即使你遵循了所有相关的最佳实践，并成功编写了不受攻击的可序列化类，你的应用程序仍然可能存在漏洞。引述 CERT 协调中心技术经理 Robert Seacord 的话：

Java 反序列化是一个清晰而紧迫的危险，因为它广泛被应用程序直接使用，也被间接用于如 RMI（远程方法调用）、JMX（Java 扩展）和 JMS（Java 消息系统）等 Java 子系统。对不可信的流进行反序列化可能导致远程代码执行（RCE）、拒绝服务（DoS）以及一系列其他攻击。即使应用程序没有做任何错，也可能受到这些攻击。[Seacord17]

攻击者和安全研究人员研究 Java 库常用第三方库中的可序列化类型，寻找在反序列化期间调用的执行潜在危险活动的方法。这些方法被称为*gadgets*（getget）。多个 gadget 可以协作使用，形成*gadget 链*（gadget chain）。每隔一段时间就会发现一种足够强大的 gadget 链，它允许攻击者在仅有提交精心构建的字节流进行反序列化的机会的情况下，在底层硬件上执行任意本地代码。这正是在 SFMTA Muni 攻击中发生的情况。这种攻击并非孤立。还有其他案例，而且未来会有更多。

在不使用任何 gadget 的情况下，你也可以通过导致一个需要长时间反序列化的短流的反序列化，轻松地发起拒绝服务攻击。这种流被称为*反序列化炸弹*（deserialization bombs）[Svoboda16]。这里有一个 Wouter Coekaerts 提供的示例，它仅使用了哈希集合和一个字符串 [Coekaerts15]：

```java
// 反序列化炸弹 - 反序列化这个流需要永远的时间
static byte[] bomb() {
    Set<Object> root = new HashSet<>();
    Set<Object> s1 = root;
    Set<Object> s2 = new HashSet<>();
    for (int i = 0; i < 100; i++) {
        Set<Object> t1 = new HashSet<>();
        Set<Object> t2 = new HashSet<>();
        t1.add("foo"); // 使 t1 不等于 t2
        s1.add(t1); // 使 t1 不等于 t2
        s1.add(t2); // 使 t1 不等于 t2
        s2.add(t1); // 使 t1 不等于 t2
        s2.add(t2); // 使 t1 不等于 t2
        s1 = t1;
        s2 = t2;
    }
    return serialize(root); // 为了简起省略了方法
}
```



对象图由 201 个 `HashSet` 实例组成，每个实例包含 3 个更少的对象引用。整个流长度为 5744 字节，但在你反序列化它之前太阳都会燃尽。问题在于，反序列化 `HashSet` 需要计算其元素的哈希值。根集的 2 个元素本身是包含 2 个元素的集合，每个集合又包含 2 个元素的集合，以此类推，深达 100 层。因此，反序列化集合会导致 `hashCode` 方法被调用 2¹⁰⁰ 次。除了反序列化需要永远的时间之外，反序列化器没有任何迹象显示异常。

在不使用任何 gadget 的情况下，我们如何防御这些问题？每当你反序列化一个不可信的字节流时，你就让自己面临危险。避免反序列化攻击的最佳方法是永远不要反序列化任何东西。正如 1983 年电影《游戏》中计算机 Joshua 所说，“唯一的获胜之策是不玩。”在你编写的任何新系统中，没有理由使用 Java 序列化。有其他机制可以在对象和字节序列之间进行转换，这些机制避免了 Java 序列化的许多危险，同时提供了许多优势，如跨平台支持、高性能、庞大的工具生态以及广泛的专家社区。在本书中，我们把这些机制称为*跨平台结构化数据表示*（cross-platform structured-data representations）。虽然其他人有时将其称为序列化系统，但本书避免了这种用法以防与 Java 序列化混淆。

这些表示法的共同点是它们比 Java 序列化要*简单得多*。它们不支持任意对象图的自动序列化反序列化。相反，它们支持由属性值对组成的简单结构化数据对象。仅支持少量原始和数组类型。这种简单的抽象被证明足以构建极其强大的分布式系统，并且足够简单，可以避免 Java 序列化自诞生以来困扰它的严重问题。

领先的跨平台结构化数据表示有 `JSON` [JSON] 和 `Protocol Buffers`，也称为 `protobuf` [Protobuf]。`JSON` 由 Douglas Crockford 设计用于浏览器与服务器之间的通信，而 protocol buffers 由 Google 设计在其服务器之间存储和交换结构化数据。尽管这些表示有时被称为语言无关，但 `JSON` 最初是为 JavaScript 开发的，而 `protobuf` 是为了 C++；两种表示都保留了它们的起源痕迹。

`JSON` 和 `protobuf` 之间最重要的区别在于：`JSON` 是基于文本的且人类可读，而 `protobuf` 是二进制的且效率高得多；`JSON` 仅作为数据表示，而 `protobuf` 提供了模式（类型）来记录并强制适当的使用。虽然 `protobuf` 比 `JSON` 更高效，但对于基于文本的来说，`JSON` 已经非常高效了。尽管 `protobuf` 是二进制表示，但它确实提供了一种替代的文本表示，用于需要人类可读性的场景（`pbtxt`）。

如果你无法完全避免 Java 序列化（可能是因为你正在一个需要它的遗留系统环境中工作），那么次优的方案是永远不要反序列化不可信的数据。特别是，你不永远应该接受来自不可信源的 RMI 流量。Java 官方安全编码指南指出：“对不可信的数据进行反序列化本质上是危险的，应该避免。”这句话使用了大号、粗体、斜体、红色字体，而且它是整个文档中唯一经过这种处理的文本 [Java-secure]。

如果你无法避免序列化，并且无法完全确定正在反序列化的数据的安全性，请使用 Java 9 中添加并回溯到早期版本的对象反序列化过滤功能（`java.io.ObjectInputFilter`）。该机制允许你指定一个在反序列化之前应用到数据流的过滤器。它在类粒度上运行，允许你接受或拒绝某些类。默认接受类并拒绝一个潜在危险类列表被称为“黑名单”；默认拒绝类并接受一个被认为安全的类列表被称为“白名单”。优先使用白名单而不是黑名单，因为黑名单只能保护你免受已知威胁的影响。名为 Serial Whitelist Application Trainer (SWAT) 的工具可以用于为你的应用程序准备白名单 [Schneider16]。过滤机制还会保护你免受过度内存使用和过深对象图的影响，但无法保护你免受像上面那序列化攻击。

不幸的是，序列化在 Java 生态系统中仍然普遍。如果你正在维护一个基于 Java 序列化的系统，请认真考虑迁移到跨平台的结构化数据表示，尽管这可能是一项耗时的工作。现实来说，你可能仍然发现自己必须编写或维护可序列化的类。编写一个正确、安全且高效的可序列化类需要极大的小心。本章的其余部分提供了关于何时以及如何这样做的建议。

总之，序列化是危险的，应该被避免。如果你正在从零设计一个系统，请使用 `JSON` 或 `protobuf` 等跨平台结构化数据表示。不要反序列化不可信的数据。如果你必须这样做，请使用对象反序列化过滤，但请注意这并不保证能阻止所有攻击。避免编写可序列化类。如果必须这样做，请务必格外小心。

## 事项 86：极其谨慎地实现 `Serializable`

允许类的实例被序列化可能只需在其声明中添加 `implements Serializable` 单词。因为这太容易做到，人们有一个常见的误解，认为序列化对程序员来说几乎不需要努力。事实要复杂得多。虽然使一个类变为可序列化的直接成本可能微乎其微，但长期成本通常是巨大的。

实现 `Serializable` 的一个主要成本是它降低了在类发布后更改其实现的灵活性。当一个类实现 `Serializable` 时，它的字节流编码（或序列化形式）就成为了其导出 API 的一部分。一旦你广泛发布一个类，通常需要永久支持该序列化形式，就像你需要支持导出 API 的所有其他部分一样。如果你不设计自定义序列化形式而仅仅接受默认值，序列化形式将永远与类的原始内部表示绑定。换句话说，如果你接受默认的序列化形式，类的私有和包级私有实例字段将成为其导出 API 的一部分，而最小化字段访问的实践（事项 15）作为信息隐藏工具将失去效效果。

如果你接受了默认的序列化形式并在之后更改了类的内部表示，会导致序列化形式发生不兼容的变化。尝试使用旧版本的类序列化实例并使用新版本反序列化（或反之）的客户端将遇到程序故障。可以在保持原始序列化形式的同时更改内部表示（使用 `ObjectOutputStream.putFields` 和 `ObjectInputStream.readFields`），但这可能是困难的，并在源码中留下明显的瑕疵。如果你选择使一个类变为可序列化，你应该仔细设计一个你愿意长期共处的高质量序列化形式（事项 87, 90）。这样做会增加初始开发成本，但这种努力是值得的。即使是设计良好的序列化形式也会对类的演进产生限制；设计糟糕的序列化形式可能是致命的。

序列化对演进施加限制的一个简单示例涉及流唯一标识符，更为人知的序列版本 UID。每个可序列化类都关联有一个唯一标识符。如果你不通过声明名为 `serialVersionUID` 的静态 final long 字段来指定此数字，系统将在运行时通过对类结构应用加密哈希函数（SHA-1）自动生成它。该值受类名、它实现的接口以及大多数成员（包括编译器生成的合成成员）的影响。如果你更改了这些内容，例如添加了一个便利方法，生成的序列版本 UID 就会改变。如果你未能声明序列版本 UID，兼容性将被破坏，导致运行时抛出 `InvalidClassException`。

实现 `Serializable` 的第二个成本是它增加了漏洞和安全漏洞的概率（事项 85）。通常，对象是通过构造函数创建的；序列化是一种创建对象的语言外机制。无论你是接受默认行为还是重写它，反序列化都是一个“隐藏构造函数”，具有与其他构造函数相同的问题。由于反序列化没有显式构造函数，很容易忘记你必须确保它保证了构造函数建立的所有不变性，并且不会允许攻击者访问正在构建的对象的内部。依赖默认的反序列化机制很容易让对象面临不变性被破坏和非法访问（事项 88）。

实现 `Serializable` 的第三代价是它增加了与类的新版本发布相关的测试负担。当一个可序列化类被修改时，务要检查是否能够在新版本中序列化一个实例并在旧版本中反序列化该实例，反之亦然。因此，所需的测试量与可序列化类的数量与发布次数的乘积成正比，这可能是巨大的数字。你必须确保序列化-反序列化过程成功，并且其结果是原始对象的忠实副本。如果在编写类时就仔细设计了自定义的序列化形式，就可以减少测试的需求（Item 87, 90）。

实现 `Serializable` 不是一个可以轻率的决定。如果一个类要参与依赖 Java 序列化进行对象传输或持久化的框架，那么它是至关重要的。此外，它极大地方便了将一个类作为实现了 `Serializable` 的另一个类中的组件使用。然而，实现 `Serializable` 也有许多代价。每当你设计一个类时，都要权衡成本与收益。从历史上看，像 `BigInteger` 和 `Instant` 这样的值类实现了 `Serializable`，集合类也是如此。表示活动实体的类（如线程池）很少应该实现 `Serializable`。

设计用于继承的类（Item 19）很少应该实现 `Serializable`，接口也很少扩展它。违反这一规则会给任何扩展该类或实现接口的人带来沉重的负担。在某些情况下，违反规则是合适的。例如，如果一个类或接口存在的主要目的是参与一个要求所有参与者都实现 `Serializable` 的框架，那么该类或接口实现或扩展 `Serializable` 就是有意义的。

设计用于继承且确实实现了 `Serializable` 的类包括 `Throwable` 和 `Component`。`Throwable` 实现 `Serializable`，以便 RMI 可以将异常从服务器发送到客户端。`Component` 实现 `Serializable`，以便 GUI 可以发送、保存和恢复，但即使在 Swing 和 AWT 的全盛时期，这一功能在实践中也很少使用。

如果你实现了一个带有实例字段的既可序列化又可扩展的类，有几个风险需要注意。如果实例字段值有任何不变性，那么关键是要防止子类重写 `finalize` 方法，类可以通过重写 `finalize` 并将其声明为 `final` 来做到。否则，该类将易受到终结器攻击（*Item 8*）。最后，如果类具有某些如果其实例字段被初始化为默认值（整数类型为 0，布尔类型为 `false`，对象引用类型为 `null`）就会被违反，你必须添加此 `readObjectNoData` 方法：

```java
// 用于有状态的可扩展序列化类的 readObjectNoData
private void readObjectNoData() throws InvalidObjectException {
    throw new InvalidObjectException("Stream data required");
}
```

该方法是在 Java 4 中添加的，以涵盖向现有可序列化类添加可序列化父类的特殊情况 [Serialization, 3.5]。

关于*不*实现 `Serializable` 的决定，有一个例外。如果一个设计用于继承的类不可序列化，那么编写一个可序列化的子类可能需要额外的努力。对此类类的正常反序列化要求父类具有一个可访问的无参数构造函数 [Serialization, 1.10]。如果你不提供这样的构造函数，子类将被迫使用序列化代理模式（Item 90）。

内部类（Item 24）不应该实现 `Serializable`。它们使用编译器生成的生成的合成字段来存储对外部实例的引用，并存储外部作用域中局部变量的值。这些字段如何对应类定义是不指定的，匿名类和局部类的名称也是如此。因此，内部类的默认序列化形式是未定义的。然而，静态成员类可以实现 `Serializable`。

总结来说，实现 `Serializable` 的便利是虚幻的。除非一个类仅用于受保护的环境，其中版本永远不需要互操作，且服务器永远不会暴露给不可信的数据，否则实现 `Serializable` 是一项应该非常谨慎地做出的严肃承诺。如果一个类允许继承，则需要格外小心。

## Item 87：考虑使用自定义的序列化形式

当你在时间压力下编写类时，通常认为将精力集中在设计最佳 API 上是合适的。有时这意味着发布一个你知道会在未来版本中替换的“临时”实现。通常这不是问题，但如果该类实现了 `Serializable` 并使用了默认的序列化形式，你永远无法完全逃离这个临时实现。它将永远决定序列化形式。这不仅仅是一个理论性问题。它发生过 Java 库中的几个类上，包括 `BigInteger`。

### 在没有先考虑是否合适的情况下不要接受默认的序列化形式。接受默认序列化形式应该是一个有意识的决定，即从灵活性、性能和正确性的角度来看这种编码是合理的。通常情况下，只有当默认序列化形式与你设计自定义序列化形式时选择的编码大部分相同时，你才应该接受默认序列化形式。

对象的默认序列化形式是对以对象为根的对象图物理表示的一种相当高效编码。换句话说，它描述了对象以及从它可达的每个对象中所包含的数据。它还描述了所有这些对象相互关联的拓扑结构。对象的理想序列化形式只包含对象所表示的逻辑数据。它独立于物理表示。

### 如果一个对象的物理表示与其内容相同，那么默认序列化形式可能是合适的。例如，对于下面这个简单表示人名的类，默认序列化形式将是合理的：

```java
// 默认序列化形式的好候选
public class Name implements Serializable {
    /**
     * 姓。不能为 null。
     * @serial
     */
    private final String lastName;

    /**
     * 名。不能为 null。
     * @serial
     */
    private final String firstName;

    /**
     * 中名，如果没有则 null。
     * @serial
     */
    private final String middleName;

    ... // 剩余部分省略
}
```

从逻辑上讲，一个名字由三个字符串组成，代表姓、名名。`Name` 的实例字段精确地映射了这种逻辑内容。

**即使你决定默认序列化形式是合适的，你通常也必须提供 `readObject` 方法来确保不变性和安全性。** 以 `Name` 类为例，`readObject` 方法必须确保 `lastName` 和 `firstName` 字段不为空。这个问题在 Item 88 和 90 中进行了详细讨论。

注意 `lastName`、`firstName` 和 `middleName` 字段上有文档注释，尽管它们是私有的。这是因为这些私有字段定义了一个公共 API（即类的序列化形式），而这个公共 API 必须被记录。`@serial` 标签告诉 Javadoc 将此文档放置在记录序列化形式的特殊页面上。

在 `Name` 对应的另一端，考虑以下类，它代表一个字符串列表（暂不考虑你可能使用标准的 `List` 实现之一会更好）：

```java
// 默认序列化形式的极糟糕候选者
public final class StringList implements Serializable {
    private int size = 0;
    private Entry head = null;

    private static class Entry implements Serializable {
        String data;
        Entry  next;
        Entry  previous;
    }

    ... // 剩余部分省略
}
```

从逻辑上说，这个类代表一个字符串序列。从物理上说，它将该序列表示为双向链表。如果你接受默认的序列化形式，那么序列化形式将费力地镜像链表中的每个条目以及条目之间的所有链接（涵盖两个方向）。

### 当对象的物理表示与其逻辑数据内容存在显著差异时，使用默认序列化形式有四个缺点：

* **它将导出的 API 与当前的内部表示永久性绑定。** 在上面的示例中，私有的 `StringList.Entry` 类变成了公共 API 的一部分。如果在未来的发布中更改了表示形式，`StringList` 类仍然需要在输入时接受链表表示并在输出时生成它。该类将永远无法摆所有处理链表条目的代码，即使它不再使用这些代码。
* **它可能会消耗大量空间。** 在上面的示例中，序列化形式不必要表示链表中的每个条目和所有链接。这些条目和链接仅仅是实现细节，不值得包含在序列化形式中。由于序列化形式异常巨大，将其写入磁盘或通过网络发送将非常缓慢。
* **它可能会消耗大量时间。** 序列化逻辑并不了解对象图的拓扑结构，因此必须经过昂贵的图遍历。在上面的示例中，只需跟随 `next` 引用就足够了。
* **它可能会导致栈溢出。** 默认序列化程序对对象图进行递归遍历，即使对于中等规模的对象图也可能导致栈溢出。序列化一个包含 1000–1800 个元素的 `StringList` 实例会在我的机器上产生 `StackOverflowError`。惊讶的是，导致序列化引起栈溢出的最小列表大小在每次运行时都不同（在我的机器上）。出现此问题的最小列表大小可能取决于平台实现和命令行标记；某些实现可能完全没有这个问题。

`StringList` 一个合理的序列化形式仅仅是列表中字符串的数量，随后是字符串本身。这构成了 `StringList` 所表示的逻辑数据，去除了物理表示的细节。以下是修订后的 `StringList` 版本，带有 `writeObject` 和 `readObject` 方法来实现这种序列化形式。提醒一下，`transient` 修饰符表示实例字段应从类的默认序列化形式中省略：

```java
// 具有合理自定义序列化形式的 StringList
public final class StringList implements Serializable {
    private transient int size  = 0;
```



`private transient Entry head = null;`

```java
// 不再可序列化！

private static class Entry {

    String data;

    Entry next;

    Entry previous;

}

// 将指定的字符串添加到列表

public final void add(String s) { ... }

/**

 * 序列化此 {@code StringList} 实例。

 *

 * @serialData 列表的大小（包含的字符串数量）

 * 输出（{@code int}），随后是所有的

 * 元素（每个都是 {@code String}），

 * 按正确的顺序输出。

 */

private void writeObject(ObjectOutputStream s) throws IOException {

    defaultWriteObject();

    s.writeInt(size);

    // 按正确顺序写入所有元素

    for (Entry e = head; e != null; e = e.next) {

        s.writeObject(e.data);

    }

}

private void readObject(ObjectInputStream s) throws IOException, ClassNotFoundException {

    defaultReadObject();

    int numElements = s.readInt();

    // 读取所有元素并插入列表

    for (int i = 0; i < numElements; i++) {

        add((String) s.readObject());

    }

}

... // 剩余部分省略
```

例如，考虑哈希表的情况。其物理表示是一个包含键值对条目的哈希桶（buckets）序列。条目所在的桶是其键的哈希值的函数，而通常情况下，哈希值无法保证在不同实现之间是相同的。事实上，它甚至无法保证在每次运行之间是相同的。因此，接受哈希表的默认序列化形式将构成一个严重的错误。序列化和反序列化哈希表可能会产生一个不变性被严重破坏的对象。

无论你是否接受默认的序列化形式，每个没有标记为 `transient` 的实例字段在调用 `defaultWriteObject` 方法时都会被序列化。因此，每个可以声明为 `transient` 的实例字段都应该被声明。这包括派生字段，其值可以从主数据字段计算得出（例如缓存哈希值）。它还包括值与 JVM 的某一次运行绑定的字段，例如表示原生数据结构指针的 `long` 字段。**在决定将一个字段设为非 `transient` 之前，请务必说服自己它的值是对象逻辑状态的一部分。** 如果你使用自定义序列化形式，大部分或所有实例字段都应该标记为 `transient`，如上面的 `StringList` 示例所示。

如果你使用默认的序列化形式并标记了一个或多个字段为 `transient`，请记住当实例被反序列化时，这些字段将被初始化为默认值：对象引用字段为 `null`，数值基本类型字段为 0，`boolean` 字段为 `false` [JLS, 4.12.5]。如果这些值对于任何 `transient` 字段都是不可接受的，你必须提供一个 `readObject` 方法，调用 `defaultReadObject` 方法并将 `transient` 字段恢复为可接受的值 (Item 88)。或者，这些字段可以在第一次被使用时进行懒性初始化 (Item 83)。

无论你是否使用默认的序列化形式，**你必须对对象序列化施加任何你对读取对象整个状态的其他方法会施加的同步措施。** 因此，例如，如果你有一个线程安全的对象 (Item 82)，它通过同步每个方法来实现线程安全，且你选择使用默认序列化形式，请使用以下 `writeObject` 方法：

```java
// 带有默认序列化形式的同步类的 writeObject

private synchronized void writeObject(ObjectOutputStream s)

    throws IOException {

    s.defaultWriteObject();

}
```

如果你在 `writeObject` 方法中放入同步代码，你必须确保它遵循与其他活动相同的锁顺序约束，否则你可能会面临资源顺序死锁的风险 [Goetz06, 10.1.5]。

**无论你选择何种序列化形式，请在你编写的每个可序列化类中声明一个显式的 `serialVersionUID`。** 这消除了 `serialVersionUID` 作为潜在不兼容源的问题 (Item 86)。它还有细微的性能收益。如果没有提供 `serialVersionUID`，则会在运行时执行昂贵的计算来生成一个。

声明 `serialVersionUID` 非常简单。只需在你的类中添加此行即可：

```java
private static final long serialVersionUID = randomLongValue;
```

如果你编写一个新类，为 `randomLongValue` 选择什么值都无所谓。你可以通过在类上运行 `serialver` 工具来生成该值，但随手取一个数字也可以。`serialVersionUID` 并不*要求*必须是唯一的。如果你修改了一个缺少 `serialVersionUID` 的现有类，并且你想让新版本接受现有的序列化实例，你必须使用为旧版本自动生成的值。你可以通过在旧版本的类（即存在序列化实例的那个类）上运行 `serialver` 工具来获取此数字。

如果你想创建一个与现有版本*不兼容*的类的新版本，只需更改 `serialVersionUID` 声明中的值即可。这将导致尝试反序列化以前版本的序列化实例时抛出 `InvalidClassException`。**除非你想破坏与该类所有现有序列化实例的向后兼容性，否则不要更改 `serialVersionUID`。**

总结一下，如果你已经决定一个类应该是可序列化的 (Item 86)，请深思序列化形式应该是怎样的。只有*当默认序列化形式是对象逻辑状态的合理描述时*才使用它；否则，请设计一个恰当描述对象的自定义序列化形式。你分配给设计类序列化形式的时间应该与你分配给设计导出方法的时间一样 (Item 51)。正如你无法从未来的版本中消除导出方法一样，你无法从序列化形式中消除字段；它们必须被永久保留，以确保序列化兼容性。选择错误的序列化形式可能会对类的复杂性和性能产生永久的负面影响。

## 第 88 项（Item）：防御性地写入 `readObject` 方法

Item 50 包含一个带有可变私有 `Date` 字段的不可变日期范围类。该类通过在构造函数和访问器中防御性地拷贝 `Date` 对象来保持其不变性和不可变性。以下是该类：

```java
// 使用防御性拷贝的不可变类

public final class Period {

    private final Date start;

    private final Date end;

    /**

     * @param start 日期的开始

     * @param end 日期的结束

     * @throws IllegalArgumentException 如果 start 晚于 end

     * @throws NullPointerException 如果 start 或 end 为 null

     */

    public Period(Date start, Date end) {

        this.start = new Date(start.getTime());

        this.end = new Date(end.getTime());

        if (this.start.compareTo(this.end) > 0)

            throw new IllegalArgumentException(start + " after " + end);

    }

    public Date start () { return new Date(start.getTime()); }

    public Date end () { return new Date(end.getTime()); }

    public String toString() { return start + " - " + end; }

    // ...

}
```

假设你认为一个类应该是可序列化的。由于 `Period` 对象的物理表示与其逻辑数据完全一致，使用默认序列化形式是不不合理的 (Item 87)。因此，你可能认为要使该类可序列化只需要在类声明中添加 `Serializable` 关键字。然而，如果你这样做，该类将不再保证其关键的不不变性。

问题在于，`readObject` 方法实际上是另一个公共构造函数，它要求的关注度与其他任何构造函数相同。

广义地说，`readObject` 是一个以字节流作为唯一参数的构造函数。在正常情况下，字节流是通过序列化一个正常构造的实例生成的。当 `readObject` 接收到一个人工构造的字节流，且该流生成的对象违反了类的不变性时，问题就出现了。这种字节流可以用来创建一个“不可能的对象”（impossible object），这种对象无法通过普通的构造函数创建。

假设我们简单地在 `Period` 类的声明中添加了 `implements Serializable`。那么这个糟糕的程序将会生成一个 `Period` 实例的结束时间早于开始时间。对高位为 1 的 `byte` 值进行强制转换，由于 Java 缺乏 `byte` 字面量，加上将 `byte` 类型设计为有符号类型的这一遗憾决策的结果：

```java
public class BogusPeriod {

  // 字节流不可能来自真实的 Period 实例！

  private static final byte[] serializedForm = {

    (byte)0xac, (byte)0xed, 0x00, 0x05, 0x73, 0x72, 0x00, 0x06,

    0x50, 0x65, 0x72, 0x69, 0x6f, 0x64, 0x40, 0x7e, (byte)0xf8,

    0x2b, 0x4f, 0x46, (byte)0xc0, (byte)0xf4, 0x02, 0x00, 0x02,

    0x4c, 0x00, 0x03, 0x65, 0x6e, 0x64, 0x74, 0x00, 0x10, 0x4c,

    0x6a, 0x61, 0x76, 0x61, 0x2f, 0x75, 0x74, 0x69, 0x6c, 0x2f,

    0x44, 0x61, 0x74, 0x65, 0x3b, 0x4c, 0x00, 0x05, 0x73, 0x74,

    0x61, 0x72, 0x74, 0x71, 0x00, 0x7e, 0x00, 0x01, 0x78, 0x70,

    0x73, 0x72, 0x00, 0x0e, 0x6a, 0x61, 0x76, 0x61, 0x2e, 0x75,

    0x74, 0x69, 0x6c, 0x2e, 0x44, 0x61, 0x74, 0x65, 0x68, 0x6a,

    (byte)0x81, 0x01, 0x4b, 0x59, 0x74, 0x19, 0x03, 0x00, 0x00,

    0x78, 0x70, 0x77, 0x08, 0x00, 0x00, 0x00, 0x66, (byte)0xdf,

    0x6e, 0x1e, 0x00, 0x78, 0x73, 0x71, 0x00, 0x7e, 0x00, 0x03,

    0x77, 0x08, 0x00, 0x00, 0x00, (byte)0xd5, 0x17, 0x69, 0x22,

    0x00, 0x78

  };

  public static void main(String[] args) {

    Period p = (Period) deserialize(serializedForm);

    System.out.println(p);

  }

  // 返回具有指定序列化形式的对象

  static Object deserialize(byte[] sf) {

    try {

      return new ObjectInputStream(

          new ByteArrayInputStream(sf)).readObject();

    } catch (IOException | ClassNotFoundException) {

      throw new IllegalArgumentException(e);

    }

  }

}
```

用于初始化 `serializedForm` 的 `byte` 数组是通过序列化一个 `Period` 实例并手动编辑生成的字节流生成的。流的细节并不重要，但如果你感兴趣，序列化流格式在《Java 对象序列化规范》[序列化, 第 6 节] 中有描述。如果你运行这个程序，它会打印 `Fri Jan 1 12:00:00 PST 1999 - Sun Jan 1 12:00:00 PST 1984`。只需声明 `Period` 为可序列化的，就能让我们能够创建一个违反其不变性的对象。

为了解决这个问题，为 `Period` 提供一个 `readObject` 方法，该方法调用 `defaultReadObject` 然后检查反序列化对象的有效性。如果有效性检查失败，`readObject` 方法将抛出 `InvalidObject`，防止反序列化完成：

```java
// 带有有效性检查的 readObject 方法 - 不！

private void readObject(ObjectInputStream s)

throws IOException, ClassNotFoundException {

  s.defaultReadObject();

  // 检查我们的不变性是否被满足

  if (start.compareTo(end) > 0)

    throw new InvalidObject(start +" "+ end);

}
```

虽然这防止了攻击者创建无效的 `Period` 实例，但还有一个更微妙的问题在潜伏。通过伪造一个以有效的 `Period` 实例开始的字节流，然后附加指向 `Period` 实例内部私有 `Date` 字段的额外引用，可以创建一个可变的 `Period` 实例。攻击者从 `ObjectInputStream` 读取 `Period` 实例，然后读取附加到流中的“流氓对象引用”。这些引用让攻击者可以访问 `Period` 对象内部私有 `Date` 字段所引用的对象。通过修改这些 `Date` 实例，攻击者就可以修改 `Period` 实例。下面的类演示了这一点：

```java
public class MutablePeriod {

  // 一个 period 实例

  public final Period period;

  // period 的 start 字段，我们不应该访问它

  public final Date start;

  // period 的 end 字段，我们不应该访问它

  public final Date end;

  public MutablePeriod() {

    try {

      ByteArrayOutputStream bos = new ByteArrayOutputStream();

      ObjectOutputStream out = new ObjectOutputStream(bos);

      // 序列化一个有效的 Period 实例

      out.writeObject(new Period(new Date(), new Date()));

      /*

       * 为 Period 内部的 Date 字段附加

       * 流氓“之前的对象引用”。详情请参见《Java

       * 对象序列化规范》第 6.4 节。

       */

      byte[] ref = { 0x71, 0, 0x7e, 0, 5 }; // 引用 #5

      bos.write(ref); // start 字段

      ref[4] = 4;     // 引用 #4

      bos.write(ref); // end 字段

      ObjectInputStream in = new ObjectInputStream(new ByteArrayInputStream(bos.toByteArray()));

      // 反序列化

      period = (Period) in.readObject();

      // “被盗取”的 Date 引用

      start = (Date) in.readObject();

      end = (Date) in.readObject();

    } catch (IOException | ClassNotFoundException e) {



```java
throw new IllegalArgumentException(e);
```

要看到攻击生效，请运行以下程序：

```java
public static void main(String[] args) {
    MutablePeriod mp = new MutablePeriod();
    Period p = mp.period;
    Date pEnd = mp.end;
    // 让我们时钟拨回
    pEnd.setYear(78);
    System.out.println(p);
    // 回到 60 代
    pEnd.setYear(69);
    System.out.println(p);
}
```

在我的本地设置下，运行此程序会产生以下输出：

```text
Wed Nov 22 00:21:29 PST 2017 - Wed Nov 22 00:21:29 PST 1978
Wed Nov 22 00:21:29 PST 2017 - Sat Nov 22 00:21:29 PST 1969
```

```java
throw new InvalidObjectException(start + " after " + end);
```

请注意，防御拷贝是在有效性检查之前进行的，而且我们没有使用`Date`的`clone`方法来执行防御拷贝。这两个细节对于保护`Period`免受攻击（Item 50）都是必要的。同样注意，`final`字段无法进行防御拷贝。为了使用`readObject`方法，我们必须使`start`和`end`字段非`final`。这很遗憾，但这是两害相轻。有了新的`readObject`方法并且从`start`和`end`字段中删`final`修饰符，`MutablePeriod`类失效了。上面的攻击程序现在生成了以下输出：

```text
Wed Nov 22 00:23:41 PST 2017 - Wed Nov 22 00:23:41 PST 2017
Wed Nov 22 00:23:41 PST 2017 - Wed Nov 22 00:23:41 PST 2017
```

这里有一个用于判断默认`readObject`方法对于某个类是否可以接受的简单试金石：你是否乐意添加一个公共构造函数，该构造函数以对象中每个非`transient`字段的值作为参数，并在没有任何验证的情况下将这些值存储在字段中？如果不可以，你必须提供一个`readObject`方法，并且它必须执行构造函数所需的所有有效性检查和防御拷贝。或者，你可以使用*序列化代理模式*（Item 90）。这种模式被高度推荐，因为它减少了安全反序列化的大量工作。

`readObject`方法与构造函数之间还有另一个相似之处，适用于非`final`可序列化类。与构造函数一样，`readObject`方法不能直接或间接调用任何可重写的方法（Item 19）。如果违反了这一规则且相关方法被重写，则重写的方法将在子类状态被反序列化之前运行。这可能导致程序失败 [Bloch05, Puzzle 91]。

总结一下，每当你编写`readObject`方法时，都要抱这样的心态：你正在编写一个公共构造函数，无论给定什么字节流，都要产生一个有效的实例。不要假设字节流代表一个实际序列化的实例。虽然此项中的示例涉及使用默认序列化形式的类，但提出的所有问题同样适用于具有自定义序列化形式的类。这里是以总结形式给出的`readObject`方法的指南：

- 对于必须保持为私有的对象引用字段的类，请对该字段中的每个对象进行防御拷贝。不可变类中的可变组件属于此类项。
- 检查任何不变式，如果检查失败则抛出`InvalidObjectException`。检查应该在任何防御拷贝之后进行。
- 如果必须在反序列化后验证整个对象图，请使用`ObjectInputValidation`接口（本书未讨论）。
- 不要直接或间接地调用类中的任何可重写方法。

## Item 89：对于实例控制，优先使用枚举类型而非`readResolve`

Item 3 描述了*单例*模式并给出了以下单例类的示例。该类限制了对其构造函数的访问，以确保只会创建一个实例：

```java
public class Elvis {
    public static final Elvis INSTANCE = new Elvis();
    private Elvis() { ... }
    public void leaveTheBuilding() { ... }
}
```

如 Item 3 所示，如果在其声明中添加`implements Serializable`词汇，该类将不再是单例。无论该类使用默认序列化形式还是自定义序列化形式（Item 87）都并不重要，该类是否提供显式的`readObject`方法（Item 88）也不重要。任何`readObject`方法（无论是显式的还是默认）都会返回一个新的创建实例，它不会与类初始化时创建的实例相同。

`readResolve`功能允许你用另一个实例替换由`readObject`创建的实例 [Serialization, 3.7]。如果反序列化对象的类定义了具有适当声明的`readResolve`方法，则该方法会在新创建的对象在反序列化后被调用。该方法返回的对象引用将替代新创建的对象返回。在此项功能的大多数用法中，不会保留对新创建的对象的引用，因此它会立即进入垃圾回收范围。

如果让`Elvis`类实现`Serializable`，则下面的`readResolve`方法就足以保证单例属性：

```java
// 用于实例控制的 readResolve - 你可以做得更好
private Object readResolve() {
    // 返回唯一的 Elvis 并让垃圾收集器处理
    return INSTANCE;
}
```

此方法忽略反序列化的对象，返回在类初始化时创建的`Elvis`实例。因此，`Elvis`实例的序列化形式不需要包含任何数据；所有实例字段都应该是`transient`的。事实上，如果你依赖`readResolve`进行实例控制，所有实例字段都必须是`transient`的。否则，有有心的攻击者可能在`readResolve`方法运行之前获取反序列化对象的引用，使用一种与 Item 88 中的`MutablePeriod`攻击类似的技术。

攻击有点复杂，但原理很简单。首先，编写一个“stealer”类，它既有一个`readResolve`方法，又有一个指向“隐藏”其中的序列化单例的实例字段。在序列化流中，将单例的非`transient`字段替换为 stealer 的实例。你现在有了循环引用：单例包含 stealer，而 stealer 指向单例。

由于单例包含 stealer，当单例反序列化时，stealer 的`readResolve`方法首先运行。结果是当 stealer 的`readResolve`方法运行时，它的实例字段仍然指向部分反序列化（尚未解析）的单例。

stealer 的`readResolve`方法将引用从实例字段复制到静态字段，以便在`readResolve`方法运行后可以访问该引用。该方法随后返回一个与其隐藏字段类型匹配的值。如果不这样做，当序列化系统尝试将 stealer 引用存入该字段时，VM 将抛出`ClassCastException`。

为了使其具体，请考虑以下损坏的单例：

```java
// 损坏的单例 - 有非 transient 对象字段！
public class Elvis implements Serializable {
    public static final Elvis INSTANCE = new Elvis();
    private Elvis() { }
    private String[] favoriteSongs = {
        "Hound Dog", "Heartbreak Hotel"
    };
    public void printFavorites() {
        System.out.println(Arrays.toString(favoriteSongs));
    }
    private Object readResolve() {
        return INSTANCE;
    }
}
```

这是一个根据上述描述构建的“窃取器”（stealer）类：

```java
public class ElvisStealer implements Serializable {
    static Elvis impersonator;
    private Elvis payload;
    private Object readResolve() {
        // 保存对“未解析” Elvis 实例的引用
        impersonator = payload;
        // 为 favoriteSongs 字段返回正确类型的对象
        return new String[] { "A Fool Such as I" };
    }
    private static final long serialVersionUID = 0;
}
```

最后，这是一个丑的程序，它通过反序列化手工构造的流来产生两个不同的有缺陷单例实例。该程序中省略了`deserialize`方法，因为它与第 354 页上的方法完全相同：

```java
public class ElvisImpersonator {
    // 字节流不可能来自真实的 Elvis 实例！
    private static final byte[] serializedForm = {
        (byte)0xac, (byte)0xed, 0x00, 0x05, 0x73, 0x72, 0x00, 0x05,
        0x45, 0x6c, 0x76, 0x69, 0x73, (byte)0x84, (byte)0xe6,
        (byte)0x93, 0x33, (byte)0xc3, (byte)0xf4, (byte)0x8b,
        0x32, 0x02, 0x00, 0x01, 0x4c, 0x00, 0x0d, 0x66, 0x61, 0x76,
        0x6f, 0x72, 0x69, 0x74, 0x65, 0x53, 0x6f, 0x6e, 0x67, 0x73,
        0x74, 0x00, 0x12, 0x4c, 0x6a, 0x61, 0x76, 0x61, 0x2f, 0x6c,
        0x61, 0x6e, 0x67, 0x2f, 0x4f, 0x62, 0x6a, 0x65, 0x63, 0x74,
        0x3b, 0x78, 0x70, 0x73, 0x72, 0x00, 0x0c, 0x45, 0x6c, 0x76,
        0x69, 0x73, 0x53, 0x74, 0x65, 0x61, 0x6c, 0x65, 0x72, 0x00,
        0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x02, 0x00, 0x01,
        0x4c, 0x00, 0x07, 0x70, 0x61, 0x79, 0x6c, 0x6f, 0x61, 0x64,
        0x74, 0x00, 0x07, 0x4c, 0x45, 0x6c, 0x76, 0x69, 0x73, 0x3b,
        0x78, 0x70, 0x71, 0x00, 0x7e, 0x00, 0x02
    };
    public static void main(String[] args) {
        // 初始化 ElvisStealer.impersonator 并返回
        // 真实的 Elvis（即 Elvis.INSTANCE）
        Elvis elvis = (Elvis) deserialize(serializedForm);
        Elvis impersonator = ElvisStealer.impersonator;
        elvis.printFavorites();
        impersonator.printFavorites();
    }
}
```

运行此程序会产生以下输出，确凿证明了可以创建两个不同的`Elvis`实例（具有不同的音乐品味）：

```text
[Hound Dog, Heartbreak Hotel]
[A Fool Such as I]
```

你可以通过将`favoriteSongs`字段声明为`transient`来解决这个问题，但通过将`Elvis`改为单元素枚举类型（项目 3）来修复它。正如`ElvisStealer`攻击所示，使用`readResolve`方法来防止攻击者访问“临时”的反序列化实例是脆弱的，并且需要极其小心。

最后，在`SerializationProxy`类上提供一个`readResolve`方法，返回一个与包装类逻辑等价实例。该方法的存在使得序列化系统在反序列化时将序列化代理转换回包装类的实例。

这个`readResolve`方法仅使用类的公共 API 创建包装类的实例，这正是该模式的精妙之处。它在很大程度上消除了序列化的非语言特定特征，因为反序列化的实例是使用与任何其他实例相同的构造函数、静态工厂方法和方法创建的。这让你无需再单独确保反序列化的实例遵循类的类的不变性。如果该类的静态工厂方法或构造函数建立了这些不变性，且其实例方法维护了这些不变性，那么你就确保了序列化也会维护这些不变性。

以下是上述`Period.SerializationProxy`的`readResolve`方法：

```java
// readResolve method for Period.SerializationProxy
private Object readResolve() {
    return new Period(start, end);   // Uses public constructor
}
```

与防御性拷贝方法（第 357 页）类似，序列化代理方法可以有效制止虚假字节流攻击（第 354 页）和内部字段窃取攻击（第 356 页）。与之前的两种方法不同，这种方法允许`Period`的字段为`final`，而这是使`Period`类真正成为不可变类的要素（Item 17）。而且与之前的两种方法不同，这种方法不需要大量的思考。你不需要弄清楚哪些字段会被狡猾的序列化攻击破坏，也不需要作为反序列化的一部分显式地执行有效性检查。

序列化代理模式在`readObject`中还有比防御性拷贝强大的地方。序列化代理模式允许反序列化的实例与原始序列化的实例具有不同的类。你可能认为这在实践中没有用，但实际上有用。

考虑`EnumSet`的情况（Item 36）。该类没有公共构造函数，只有静态工厂。从客户端的角度来看，它们返回的是`EnumSet`实例，但在当前的 OpenJDK 实现中，它们返回两个子类之一，取决于底层枚举类型的大小。如果底层枚举类型有六十四或更少元素，静态工厂返回`RegularEnumSet`；否则，它们返回`JumboEnumSet`。

现在考虑如果你序列化一个包含 60 个元素的枚举集，然后向该枚举类型再添加 5 个元素，最后反序列化该枚举集会发生什么。它在序列化时是一个`RegularEnumSet`实例，但在反序列化后它必须是一个`JumboEnumSet`实例。事实上，事实确实如此，因为`EnumSet`使用了序列化代理模式。如果你感兴趣，这里是`EnumSet`的序列化代理。它真的这么简单：

```java
// EnumSet's serialization proxy
private static class SerializationProxy<E extends Enum<E>>
        implements Serializable {
    // The element type of this enum set.
    private final Class<E> elementType;
    // The elements contained in this enum set.
    private final Enum<?>[] elements;
    SerializationProxy(EnumSet<E> set) {
        elementType = set.elementType;
        elements = set.toArray(new Enum<?>[0]);
    }
    private Object readResolve() {
        EnumSet<E> result = EnumSet.noneOf(elementType);
        for (Enum<?> e : elements)
            result.add((E)e);
        return result;
    }
    private static final long serialVersionUID =
        362491234563181265L;
}
```



序列化代理模式有两个局限性。它与允许用户扩展的类兼容（Item 19）。此外，它与某些包含循环引用对象的类不兼容：如果你尝试从序列化代理的`readResolve`方法内部调用此类对象的方法，你将得到`ClassCastException`，因为你还没有该对象，只有它的序列化代理。

最后，序列化代理模式带来的额外力量安全性并非免费。在我的机器上，使用序列化代理序列化和反序列化`Period`实例的比防御性拷贝高 14%。

## 附录：第二版对应的项目

| 第二版项目 | 第三版项目 |
| :--- | :--- |
| 1 | 考虑静态方法 own |
| 2 | 当面对许多构造函数时 |
| 3 | 使用私有构造函数强制不可实例化 |
| 4 | 或使用枚举类型 |
| 5 | 避免创建不必要的对象 |
| 6 | 消除对象引用 |
| 7 | 避免使用 finalizers 和 cleaners |
| 8 | 在重写`equals`时遵循通用契约 |
| 9 | 在重写`equals`时重写`hashCode` |
| 10 | 始终重写`toString` |
| 11 | 谨慎使用`clone` |
| 12 | 考虑实现`Comparable` |
| 13 | 最小化类的可访问性 |
| 14 | 在公共类中，使用访问器方法而不是公共字段 |
| 15 | 最小化可变性 |
| 16 | 组合优于继承 |
| 17 | 为继承设计或禁止继承 |
| 18 | 接口优于抽象类 |
| 19 | 仅使用接口定义类型 |
| 20 | 类层次结构优于标记类 |
| 21 | Lambda 表达式优于匿名类 |
| 22 | 静态成员优于非静态 |
| 23 | 不要使用原始类型 |
| 24 | 消除未检查警告 |
| 25 | 列表优于数组 |
| 26 | 泛泛型 |
| 27 | 泛泛型方法 |
| 28 | 使用边界通配符增加 API 灵活性 |
| 29 | 考虑类型安全的容器 |
| 30 | 使用枚举代替`int`常量 |
| 31 | 使用实例字段代替序数 |
| 32 | 使用`EnumSet`代替位域 |
| 33 | 使用`EnumMap`代替有序索引 |
| 34 | 使用接口模拟可扩展枚举 |
| 35 | 注解优于命名模式 |
| 36 | 一致地使用`Override`注解 |
| 37 | 使用标记接口定义类型 |
| 38 | 检查参数有效性 |
| 39 | 需要时进行防御性拷贝 |
| 40 | 仔细设计方法签名 |
| 41 | 谨慎使用重载 |
| 42 | 谨慎使用可变参数 |
| 43 | 返回空集合或数组，而不是 null |
| 44 | 为所有公开的 API 元素编写注释 |
| 45 | 最小化局部变量的作用范围 |
| 46 | for-each 循环优于传统的`for`循环 |
| 47 | 了解并使用类库 |
| 48 | 如果需要精确答案，避免使用`float`和`double` |
| 49 | 原始类型优于包装原始类型 |
| 50 | 在其他类型更合适时避免使用字符串 |
| 51 | 注意字符串拼接的性能 |

| 56 | 68 | 遵循通通用的命名约定 |
| 57 | 69 | 仅对异常情况使用异常 |
| 58 | 70 | 对可恢复的情况使用检查异常（checked exceptions），对编程错误使用运行时异常（runtime exceptions） |
| 59 | 71 | 避免不必要的检查异常 |
| 60 | 72 | 优先使用标准异常 |
| 61 | 73 | 抛出与抽象层次合适的异常 |
| 62 | 74 | 记录每个方法抛出的所有异常 |
| 63 | 75 | 在详细消息中包含失败捕获信息 |
| 64 | 76 | 追求失败的原子性 |
| 65 | 77 | 不要忽略异常 |
| 66 | 78 | 对共享可变数据的访问进行同步 |
| 67 | 79 | 避免过度同步 |
| 68 | 80 | 优先使用执行器（executors）、任务（tasks）和流（streams），而不是线程（threads） |
| 69 | 81 | 优先使用并发工具类代替`wait`和`notify` |
| 70 | 82 | 记录线程安全性 |
| 71 | 83 | 审慎使用懒性初始化 |
| 72 | 84 | 不要依赖线程调度器 |
| 73 | (已弃) | |
| 74 | 85 | 优先使用 Java 序列化的替代方案 86 | 极其谨慎地实现`Serializable` |
| 75 | 85 | 优先使用 Java 序列化的替代方案 87 | 考虑使用自定义序列化形式 |
| 76 | 85 | 优先使用 Java 序列化的替代方案 88 | 防御性地编写`readObject`方法 |
| 77 | 85 | 优先使用 Java 序列化的替代方案 89 | 例如对于控制，优先使用枚举类型（enum types）代替`readResolve` |
| 78 | 85 | 优先使用 Java 序列化的替代方案 90 | 考虑使用序列化代理（serialization proxies）代替序列化实例 |

## 参考文献

### [Asserts]

*Programming with Assertions*. 2002\. Sun Microsystems. [`docs.oracle.com/javase/8/docsotes/guides/language/assert.html`](http://docs.oracle.com/javase/8/docsotes/guides/language/assert.html)

### [Beck04]

Beck, Kent. 2004\. *JUnit Pocket Guide*. Sebastopol, CA: O’Reilly Media, Inc. ISBN: 0596007434.

### [Bloch01]

Bloch, Joshua. 2001\. *Effective Java Programming Language Guide.* Boston: Addison-Wesley. ISBN: 0201310058.

### [Bloch05]

Bloch, Joshua, and Neal Gafter. 2005\. *Java Puzzlers: Traps, Pitfalls, and Corner Cases.* Boston: Addison-Wesley. ISBN: 032133678X.

### [Blum14]

Blum, Scott. 2014\. “Faster RSA in Java with GMP.” *The Square Corner* (blog). Feb. 14, 2014\. [`medium.com/square-corner-blog/faster-rsa-in-java-with-gmp-8b13c51c6ec4`](https://medium.com/square-corner-blog/faster-rsa-in-java-with-gmp-8b13c51c6ec4)

### [Bracha04]

Bracha, Gilad. 2004\. “Lesson: Generics” online supplement to *The Java Tutorial: A Short Course on the Basics,* 6th ed. Upper Saddle River, NJ: Addison-Wesley, 2014\. [`docs.oracle.com/javase/tutorial/extra/generics/`](https://docs.oracle.com/javase/tutorial/extra/generics/)

### [Burn01]

Burn, Oliver. 2001–2017\. *Checkstyle.* [`checkstyle.sourceforge.net`](http://checkstyle.sourceforge.net)

### [Coekaerts15]

Coekaerts, Wouter (@WouterCoekaerts). 2015\. “Billion-laughs-style DoS for Java serialization [`gist.github.com/coekie/a27cc406fc9f3dc7a70d`](https://gist.github.com/coekie/a27cc406fc9f3dc7a70d) … WONTFIX,” Twitter, November 9, 2015, 9:46 a.m. [`twitter.com/woutercoekaerts/status/663774695381078016`](https://twitter.com/woutercoekaerts/status/663774695381078016)

### [CompSci17]

Brief of Computer Scientists as Amici Curiae for the United States Court of Appeals for the Federal Circuit, Case No. 17-1118, Oracle America, Inc. v. Google, Inc. in Support of Defendant-Appellee. (2017)

### [Dagger]

*Dagger*. 2013\. Square, Inc. [`square.github.io/dagger/`](http://square.github.io/dagger/)

### [Gallagher16]

Gallagher, Sean. 2016\. “Muni system hacker hit others by scanning for year-old Java vulnerability.” *Ars Technica,* November 29, 2016. [`arstechnica.com/information-technology/2016/11/san-francisco-transit-ransomware-attacker-likely-used-year-old-java-exploit/`](https://arstechnica.com/information-technology/2016/11/san-francisco-transit-ransomware-attacker-likely-used-year-old-java-exploit/)

### [Gamma95]

Gamma, Erich, Richard Helm, Ralph Johnson, and John Vlissides. 1995. *Design Patterns: Elements of Reusable Object-Oriented Software.* Reading, MA: Addison-Wesley. ISBN: 0201633612.

### [Goetz06]

Goetz, Brian. 2006\. *Java Concurrency in Practice*. With Tim Peierls, Joshua Bloch, Joseph Bowbeer, David Holmes, and Doug Lea. Boston: Addison-Wesley.

### [Goetz97]

Gosling, James. 1997\. *The Java Language Specification.*

9945-1:1996 (ISO/IEC) [IEEE/ANSI Std. 1003.1 1995 版] 信息技术—可移植操作系统接口 (POSIX)—第 1 部分：系统应用：程序接口 (API) C 语言] (ANSI), IEEE 标准出版社, ISBN: 1559375736。

### [Protobuf]

`Protocol Buffers`. 2017. Google Inc. [`developers.google.com/protocol-buffers`](https://developers.google.com/protocol-buffers)

### [Schneider16]

Schneider, Christian. 2016. SWAT (序列白名单训练器)。 [`github.com/cschneider4711/SWAT/`](https://github.com/cschneider4711/SWAT/)

### [Seacord17]

Seacord, Robert. 2017. `使用前瞻对象输入流 (LAOIS) 应对 Java 反序列化漏洞`. 旧金山: NCC Group 白皮书。 [`www.nccgroup.trust/globalassets/our-research/us/whitepapers/2017/june/ncc_group_combating_java_deserialization_vulnerabilities_with_look-ahead_object_input_streams1.pdf`](https://www.nccgroup.trust/globalassets/our-research/us/whitepapers/2017/june/ncc_group_combating_java_deserialization_vulnerabilities_with_look-ahead_object_input_streams1.pdf)

### [Serialization]

`Java 对象序列化规范`. 2005 年 3 月. Sun Microsystems 公司。 [`docs.oracle.com/javase/9/docs/specs/serialization/index.html`](http://docs.oracle.com/javase/9/docs/specs/serialization/index.html)

### [Sestoft16]

Sestoft, Peter. 2016. `Java Precisely`, 第 3 版. 马萨诸塞州剑桥: MIT 出版社。ISBN: 0262529076。

### [Shipilëv16]

Aleksey Shipilëv. 2016. `古代智慧之数组.` [`shipilev.net/blog/2016/arrays-wisdom-ancients/`](https://shipilev.net/blog/2016/arrays-wisdom-ancients/)

### [Smith62]

Smith, Robert. 1962. 算法 116 复数除法。收于 `ACM 通报` 5, no. 8 (1962 年 8 月): 435。

### [Snyder86]

Snyder, Alan. 1986. “面向对象编程语言中的封装与继承。”收于`面向对象编程系统、语言和应用会议论文集`, 38–45. 纽约州: ACM 出版社。

### [Spring]

`Spring 框架`. Pivotal Software, Inc. 2017. [`projects.spring.io/spring-framework/`](https://projects.spring.io/spring-framework/)

### [Stroustrup]

Stroustrup, Bjarne. [约 2000 年]. “如果你不需要与 C 兼容，你会设计 Java 语言吗？”`Bjarne Stroustrup 的常见问题解答`. 更新于 2017 年 10 月 1 日。 [`www.stroustrup.com/bs_faq.html#Java`](http://www.stroustrup.com/bs_faq.html#Java)

### [Stroustrup95]

Stroustrup, Bjarne. 1995. “为什么 C++ 不仅仅是一种面向对象的编程语言。”收于`第 10 届面向对象编程系统、语言和应用会议附录`, Steven Craig Bilow 和 Patricia S. Bilow 编. 纽约州: ACM. [`dx.doi.org/10.1145/260094.260207`](http://dx.doi.org/10.1145/260094.260207)

### [Svoboda16]

Svoboda, David. 2016. `利用 Java 反序列化获取乐趣与利润`. 卡内基梅隆大学软件工程研究所。 [`resources.sei.cmu.edu/library/asset-view.cfm?assetid=484347`](https://resources.sei.cmu.edu/library/asset-view.cfm?assetid=484347)

### [Thomas94]

Thomas, Jim, and Jerome T. Coonen. 1994. “关于 C 和 C++ 虚类型的问题。”收于`C 语言翻译期刊` 5, no. 3 (1994 年 3 月): 134–138。

### [ThreadStop]

`为什么`Thread.stop`、`Thread.suspend`、`Thread.resume`和`Runtime.runFinalizersOnExit`被弃用了？` 1999 年. Sun Microsystems 公司。 [`docs.oracle.com/javase/8/docs/technotes/guides/concurrency/threadPrimitiveDeprecation.html`](https://docs.oracle.com/javase/8/docs/technotes/guides/concurrency/threadPrimitiveDeprecation.html)

### [Viega01]

Viega, John, and Gary. 2001. `构建安全软件: 避免问题的正确方法.` 波士顿: Addison-Wesley. ISBN: 02017251

### [W3C]

`W3C 服务`. 2007. 世界 Web 联盟。 [`www.w3.org/`](http://www.w3.org/)

### [Wulf72]

Wulf, W. 反对 GOTO。1972. 收于`第 25 届 ACM 全国会议`, 791–797. 纽约: ACM。

## 索引

### 符号

- 在数字字面量中的，108
- `...` 参数数量（见 `varargs`)
- `<>` 通配符类型，117
- `<?>` 无界类型，120

### A

- 抽象类设计继承，97
- 接口，99–103
- 子类，与`equals`，45
- 访问控制，74
- 访问级别，73–77
- `readResolve`的，362
- 静态成员类的规则，112
- 访问器方法，78
- 防御性拷贝和，80，233
- 不可变性和，80
- 命名规范对于，291–292
- 与公有字段，78–79
- `toString`数据的，57
- 实际类型参数，117
- 适配器模式，23，101，113
- 聚合类型与字符串，276
- 异类方法，317
- 注释，157，180–192
- 定义，180
- 检测重复和非重复，186
- 文档，259
- 功能性接口和，202
- 与命名模式，180–187
- 类的，186
- 另见标记注解
- 匿名类，112,114,193
- 在适配器中，101
- 优先使用 lambda 表达式代替类，193–196
- 序列化和，196
- 反模式，2
- 位字段枚举模式，169
- 有界通配符类型作为返回类型，142
- 违反命名规范，82
- 忙等待，336
- 作为`hashCode`的常量，51
- 常量接口，107–108
- 不变对象的构造函数，83
- 基于差异的比较器，71
- 空 catch 块，310
- 使用不可靠资源的`equals`，45
- 异常用于流程控制，293
- 过度字符串拼接，279
- 浮点数用于货币计算，270
- 硬编码资源，20
- `hashCode`缺少重要字段，54
- 不变类不是有效的 final，85
- 不适当的子类化，92
- `int`枚举模式，157
- 签名因参数类型顺序而异，6
- `String`枚举模式，158
- `string`的过度使用，276
- 标记的类，109–111
- 值组件子类与`equals`，44

## API 设计

- 访问级别和，74
- 边界通配符类型和，139–145
- 回调，28
- 常量接口模式和，107
- 异常和，294, 296–297
- 信息隐藏和，286
- 继承和，93–98
- 作为参数类型的接口，170
- 成员类和，114
- 性能和，286–287
- 序列化和，343–345
- 单例，18
- API 元素，4
- 文档化，254–260
- API，`toString`返回值作为事实标准，57

## 数组

- `clone`和，65
- 协型类型，126
- 防御性拷贝，76, 234
- 空数组，vs.`null`作为返回值，247–248
- 用于实现泛型，131–133
- vs. 列表，126–129
- 可变性和，234, 248
- 实例化的，126
- 安全问题，76
- 断言，229

## 原子性

- 变量的，311
- 同步和，312–314
- 自动装箱，24, 273–275
- 性能和，275
- `AutoCloseable`接口，31–32, 35

## B

- 底层对象，23
- 基类，281
- `BigDecimal`类
- `compareTo`与`equals`不一致，68
- 用于货币计算，270
- 性能和，271
- 位域 vs. 枚举集，169–170
- 阻塞操作，326
- 伪造字节流攻击，354
- `boolean` vs. 枚举类型，237
- 边界类型参数，134
- 用于边界类型令牌，154
- vs. 边界通配符类型，144
- 边界类型令牌，154, 172, 178, 183
- 边界通配符类型，136, 140
- 用于 API 灵活性，139–145
- vs. 边界类型参数，144
- 用于边界类型令牌，154
- vs. 类对象，178
- 依赖注入和，21
- 用于 PECS 记忆口法，141
- 作为返回类型，142
- vs. 无边界通配符类型，121
- 箱后的原始类型
- `==`运算符和，274
- 适当使用，275
- 泛型和，134
- 优于原始类型，24, 273–275
- 桥接模式，8
- 生成器模式，10–16
- 适配方法调用的，237
- 忙等待，336

## C

- 缓存
- 防止内存泄漏，28
- 高开销对象，22–23
- 哈希码，53
- 不可变对象和，82, 85
- 回调框架，包装类和，91
- 回调，防止内存泄漏，28
- 规范形式，47
- 能力 vs. 字符串，276–277
- 强制转换
- 动态，153, 155
- 不可见的（见编译器生成的转换(#index.xhtml_index_67))
- 未检查的警告，127, 129, 137
- `char`值和流，206
- 检查异常
- 防止过度使用，298–299
- 声明，304
- 失败原子性和，308
- 目的，296
- 重构为未检查，299
- vs. 未检查，296–297
- 循环性
- 在清理器中，33
- 初始化，333, 366
- 序列化攻击和，360
- `Class`类，作为参数键，151
- 类层级，110
- 生成器模式和，14
- 组合爆炸中的，100
- 类字面量
- 作为注解参数值，183
- 作为泛型，151
- 原始类型中的，121
- 基于类的框架，281
- 类，73–114
- 访问级别，74
- 匿名，23
- 基类，281
- 组合，87–92
- 面向继承设计，93–98
- 为了继承，93–98
- 泛型的，117
- 用于参数列表的辅助，237
- 层级（见不可变对象(#index.xhtml_index_184))
- 不可变（见）
- 实例，3
- 线程安全级别，330–332
- 成员，3
- 最小化访问性，73–77
- 可变的，以及线程安全的，322
- 命名规范，289–291
- 不可实例化的，19
- 可重用的转发，89–91
- 单例（见单例(#index.xhtml_index_361))
- 摘要描述的，257
- `SuppressWarnings`注解和，124
- 标记的，vs. 类层级，109–111
- 无意实例化的，19
- 相关的，243
- 工具（见工具类(#index.xhtml_index_433))
- 包装（见包装类(#index.xhtml_index_450))

## 通用合约

- 通用，58–59
- 不变对象和，83
- 非 final 类和，233
- 非 final 方法和，64
- 可重写方法和，96
- 线程安全和，64
- `Cloneable`接口，58–65
    - 替代方案，65
    - 行为，58
    - 针对继承的设计和，64, 96
    - 实现，64

## 集合

- 并发，321, 325–326
- 空集合，对比 null 返回值，247
- 可选类型和，252
- 作为返回类型，对比流，216–221
- 收集器，211–215
    - 下游，213
    - `Collectors` API 的组织结构，211–215
- 组合爆炸，100

## 伴侣类

- 可变的，84
- 不可实例，7
- `Comparable`接口，66–72
    - 作为 PECS 中的消费者，143
    - 递归类型边界和，137
    - 另另`compareTo`方法](#index.xhtml_index_64)
- 比较器构造方法，70, 194
- 比较器，69
    - 作为 PECS 中的消费者，143
- `compareTo`方法，66–68
    - 另另`Comparable`接口](#index.xhtml_index_61)

## 兼容性

- 向后兼容，350
- 二进制兼容，107, 305
- 向前兼容，350
- 迁移，119
- 源码，305
- 未检查异常和，305
- 编译器警告的类型，123
- 编译器生成的强制转换，117, 119, 127
- 组件，2
- 组合，8, 89
- `equals`和，44
    - 对比继承，87–92
- 概念权重，7
- 并发性，311
- 为之记录方法行为，330–332
- 通过内部同步改进，322
- 并发实用程序，323–329
    - 对比`wait`和`notify`，325–329
- 并发集合，321, 325–326
- 条件安全的类的记录，331
- 一致性要求
    - `equals`，38, 45
    - `hashCode`，50
    - 与`equals`一致，68
    - 不可靠资源和，45
    - 常量字段的命名规范，290
    - 常量接口，107
    - 常量工具类，108
    - 常量，76
    - 匿名类中的，114
    - 命名规范，290
    - 类特定的行为，162–166
    - 用于 lambda 表达式，195
    - 类特定的类体，162
    - 类特定的方法实现](#index.xhtml_index_81)
    - 构造函数，4
    - 在其中调用可重写方法，95
    - 参数检查，353
    - 作为`clone`，61
    - 拷贝与转换，65
    - 默认，19
    - 参数的防御性拷贝，232
    - 反序列化作为，344
    - 建立不变性，82, 86
    - 不实例化和，19
    - 私有构造函数
    - 作为`readObject`，353
    - 反射和，282
    - 用静态工厂替换，5–9
    - 安全重载，240–241
    - 用于单例的，17–18
    - 摘要描述，257
    - `SuppressWarnings`注解和，124
    - 参数的有效性检查，229
    - 争用、同步和，321

## 合约

- `clone`，58
- `compareTo`，66
- 作为文档，304
- `equals`，38–46
- `hashCode`，50
- `toString`，55
- 损坏的对象，12, 30, 227, 309
- 计数锁，326
- 协变数组，126
- 协变返回类型，16, 60
- 创建对象，5–33
- 跨平台数据表示，341
- 序列化形式，346–352

## D

- 失败的数据一致性，308–309
- 同步，311–316
- 数据损坏，285, 312
- `Date`的替换，232
- 资源排序，320, 351
- 线程饥饿，328
- 装饰器模式，91
    - 默认私有访问
    - 默认构造函数，19
    - 默认实现，99, 105
    - 默认序列化形式，346–352
    - 缺陷，231–235
    - 防御拷贝，234
    - 数组中的，234
    - 构建器，14
    - 与`clone`的，233
    - 反序列化和，353, 357
    - 记录，234
    - 不变对象和，83
    - 可变内部字段，233
    - 可变参数，232–233
    - 对比对象重用，25
    - 性能和，234
    - `readObject`和，353, 357
    - 控制权转移和，235
    - 有效性检查和，232
    - 委托，91
    - 拒绝服务攻击，331
    - 依赖注入，20–21
    - 派生字段，47, 52
    - 反序列化作为构造函数，344
    - 单例和，17–18

## 索引

- 详细消息，306
- 菱操作符，123
- 文档化
- 注解类型，259
- `compareTo`,67
- 条件性线程安全，331
- 枚举类型，258, 331
- 异常，227, 304–305
- 暴露的 API 元素，254–260
- 泛型，258
- `hashCode`,54
- 用于继承，93–94
- 方法，254–255
- 多行代码示例，255
- 异常发生后的对象状态，309
- 参数，227
- `toString`的返回值，56
- 可重写方法的自用，93, 98
- 自用模式，256
- 序列化字段，347
- 骨架实现，103
- 静态工厂方法，9
- `SuppressWarnings`注解，125
- 线程安全，330–332
- 用于序列化的`writeObject`，350

*另请* Javadoc

## `double`

- 用于二进制浮点数运算，270
- 何时应避免，270–272
- 双重检查检用法，334–335
- 下游收集器，213
- 动态类型转换，153, 155

## E

- 有效不可变对象，316
- 空数组，对比以 null 作为返回值，247–248
- 封装，73, 286
- 被继承破坏，87, 94
- 被序列化破坏，343
- 数据字段，78
- 内部实例，112
- 枚举类型，157–192
- 向其添加数据和行为，159–161
- 对位字段，169–170
- 对`boolean`，237
- 内置序列化机制，362
- 针对特定常量的，162–166
- 文档化，258, 331
- 扩展性与，176–179
- 不可变性，160
- 实例控制的，158
- 对`int`常量，157–167
- 优于`readResolve`，359–362
- 从中移除元素，161
- 从单例中移除，170–180
- 枚举模式，166
- 对`String`常量，158, 276
- `switch`语句与，167
- 作为顶层类或成员类，161
- `toString`与，160
- 类型安全，158
- 何时使用，167
- 枚举类型，*参见* 枚举类型
- `EnumMap`对序，171–175
- `EnumSet`对位字段，169–170
- `equals`方法，37
- 意外重载，49, 188
- 规范形式与，47
- `compareTo`与，68
- 组合与，44
- 通用合约，38–46
- `hashCode`与，48, 50–54
- 如何编写，46
- `Override`注解与，188
- 返回值，以及`compareTo`，68
- 子类化与，42, 45
- 不可靠的资源与，45
- 何时重写，37–38
- 等价类，39
- 等价关系，38
- 擦除，119, 126

## 错误

- 泛型数组创建，126–127, 133
- 目的，297
- 运行时、默认方法与，105
- 确切结果，获取的类型，270
- 异常链，302–303
- 异常翻译检用法，230, 302
- 异常，293–310
- 访问器方法，297, 307
- 检查异常 vs. 非检查异常，296–297
- 在其之间选择，296
- 常见的，301
- 控制流与，294
- 详细消息，306-(307](#ch10.xhtml_page_307)
- 文档化，227, 304–305
- 捕获数据，307
- 无效参数，228
- 忽略，310
- 忽略，36
- 恰当使用，293–295

## F

- 工厂模式，5, 21
- 失败原子性，230, 308
- 字段
- 访问级别，73–77
- 类不变式与，75
- 常量，命名规范，290
- 派生的，对比 访问器方法，47, 52
- 暴露，78–79
- final (*参见* final fields)
- 初始化技术，335
- 可变的防御性拷贝，233
- 命名规范，290, 292
- public static final，用于单例，17

## Executor 框架

- 执行器服务，323–324
- 显式类型参数，142
- 导出声明，76
- 暴露的 API

*参见* API 设计

## 反射

- 反射与，282
- 总结性描述，257
- 标签，109
- 线程安全性与，75

## final 字段

- 用于定义常量，290
- 与克隆不兼容，61
- 与序列化不兼容，357
- 终化器攻击及其防御，30–31
- 终化器，29–33
- 替代方案，31

## float

- 用于二进制浮点数运算，270
- 何时应避免，270–272

## 链式 API

- 14, 203

## 权重类模式

- 6

## 内存占用 (footprint)

- *参见* 空间消耗

## for 循环

- 双变量惯用法（dual variable idiom），263
- 优先使用 for-each 循环，264–266
- 与`while`循环的对比，262

## for-each 循环

- 局限性，266
- 优于`for`循环，264–266

## fork-join 任务与池，324

## 形式式类型参数，117

## 转发方法，89, 102

## 框架

- 回调，91
- 基于类的，281
- 执行器，323
- 基于接口的，6
- 非层次级类型，99
- 服务提供者，8
- 函数对象，114
- 与代码块的对比，207
- 功能式接口，193
- 方法重载与，243
- 标准的组织，200–201
- 使用标准，199–202
- 函数式编程，82

## G

- getget（gadgets），340
- 垃圾回收，27, 29–30, 113

## 普通契约

- *参见* 契约
- 通用数组创建错误，126–127, 133
- 通用类和接口，117
- 通用方法，135–138
- 与无界通配符类型的对比，121
- 通用单例工厂，18, 136

## 通用类型参数

- *参见* 类型参数
- 通用类型，14, 117, 130–134
- 文档化，258
- 与不可变性，136
- 通用变长数组
- 堆污染，147–148
- 用列表替换，149
- 不安全的存储，146
- 不安全地暴露，147–148
- 通用泛型，117–155
- 装箱基本类型，134
- 编译器生成的强制类型转换，117
- 擦除与，126
- 在数组上实现，131–133
- 与基本类型不兼容，134
- 变型，126
- 变长参数与，127, 146–150
- 改造现有代码，130
- Get and Put 原则，141

## H

- `hashCode`方法
- 与`equals`，48, 50–54
- 通用契约，50
- 如何编写，51
- 与不可变对象，53
- 堆污染，133, 146–148
- 堆分析器，28
- 辅助类，112
- 用于缩短参数列表，237
- 隐藏构造函数，61, 96, 339, 344, 353
- *参见* 语言外机制
- 分层次构建器模式，16

## I

## 不变对象

- 规范形式与，47
- 与`clone`，59
- 依赖注入与，21
- 与空数组，248
- 枚举类型与，160
- 与`EnumSet`，170
- 失败原子性与，308
- 函数式方法与，82
- 与`hashCode`，53
- JavaBeans 与，12
- 用于可变伴侣类，84
- 对象复用与，22
- 规则，80
- 序列化与，85, 353–358
- 静态工厂方法与，84
- 子类化与，97
- 线程安全性与，82
- 过程式编程，82

## 实现细节

- 继承的文档化，94
- 暴露，92
- 实现继承，87
- 实现接口，4
- 默认方法与，105
- 与`equals`不一致，67–68
- 不可靠资源，45

## 信息隐藏

- *参见* 封装
- 继承，3
- 与组合，87–92
- 构造函数与，95
- 设计，93–94
- 封装，87
- 脆弱性，89
- 用于方便的钩子，94
- 实现对比，3
- 方法注释，259
- 多种，102
- 可重写方法与，98
- 用法，92
- *另* 子类化

## 初始化

- 循环依赖，333, 366
- 防御拷贝与，80
- 序列化时的字段，351
- 不完整，96
- 懒加载（*参见 懒初始化）
- 局部变量，261
- 普通与懒加载，333

## 继承

- 在对象创建时，86
- 内部类，112
- 与`Serializable`，345
- 扩展骨架实现，102

## 实例字段

- 访问权限，75
- 初始化，333
- 懒加载初始化，334
- 与序数的对比，168
- 实例控制类，6, 158
- 单例，17–18
- 静态工厂方法与，6
- 工具类，19
- *另* 枚举类型

## `instanceof`运算符

- 参数类型，121
- `int`常量与枚举类型的对比，157–167

## 接口

- `int`，用于货币计算，270
- 基于接口的框架，6, 99–103
- 接口继承，87
- 接口，73–114
- 与抽象类的对比，99–103
- 访问级别，74
- 静态成员的可访问性，7
- 默认方法，99, 104–105
- 用于定义类型，107–108, 191–192
- 设计，104–106
- 使用模拟可扩展枚举，176–179
- 启用功能增强，100
- 泛型，117
- 标记（参见标记接口）
- 混入（mixin），58, 99
- 命名规范，289–291
- 用于非分级类型框架，99
- 不可实例化的伴侣类和，7
- 作为参数类型，170, 237
- 优于反射，282
- 目的，58, 107–108
- 用于引用对象，280–281
- 反射式实例化，283–284
- 序列化和，344
- 骨骼实现和，100–103
- 静态方法和，7
- 摘要描述，257

*另参见具体的接口名称*

## 不变性

- 内部字段窃取攻击，360–362
- 不变性类型，126, 139
- `clone`和，61
- 并发和，328
- 构造函数和，82, 86
- 破坏，92
- 举举类型和，362
- 维护，229, 234, 308
- 对象和成员，75, 78

## J

## JavaBeans

- 不可变性，12
- 方法命名规范，291
- 模式，11–12
- Javadoc，254
- 架构文档，260
- 类级注释，228, 331
- 客户端索引，258
- 注释继承，259
- 格式，255–256
- 模块级和包级注释，259
- 摘要描述，257

## K

- Key 提取函数，70

## L

- Lambdas，70, 193–225
- 清洁器和，33
- 针对常量特定的行为，195
- 优于方法引用，197–198
- 优于匿名类，193–196
- 序列化和，196
- 懒加载初始化，23, 53, 85, 333–334
- 懒加载 holder 类，334–335
- 使用同步访问器的懒加载初始化，333–334
- 泄漏的抽象，146
- 库，267–269
- Liskov 替换原则，43, 75
- 监听器，避免内存泄漏，28

## lists

- 与数组对比，126–129
- 用于可变参数的数组，149
- 相互可比性，138

## liveness

- 确保，317–322
- 失败，224, 313
- 本地类，112, 114

## local variables

- 范围最小化，261–263
- 命名规范，290, 292
- 引用的局部性，223

## locks

- 包含的字段，332
- 终结器或清洁器和，30
- 私有的，332
- 重入的，320

## 逻辑等价，37–38

- `long`，用于货币计算，270

## loops

- 嵌套，264–266

*另参见`for`循环; for-each 循环*

## M

## maps

- 成员类和，113
- 嵌套，173–175
- 与流对比的行为，173
- 标记注解，181
- 与静态对比，191
- 标记接口，191–192
- 成员类，112–114

*另参见静态成员*

- 最小化可访问性，73–77
- 内存占用，267
- 内存泄漏，28–27
- 非静态类和，113
- 内存管理，28
- 内存模型，80
- 合并函数，70
- 元注解，181
- 方法链式，18
- 方法重载，49–54
- 自动装箱和泛型的影响，241–242
- 泛式接口和，202, 243
- 参数，240
- 静态选择，238
- 方法重写，49, 238–239
- 访问级别和，75
- `clone`，58
- 动态选择，238
- `equals`，37–49
- `hashCode`，50–54
- 自使用和，98
- `toString`，55–57
- 无意的，190
- 方法引用，18
- 种类，198
- 优于 lambdas，197–198
- 方法，3, 227–260
- 访问级别，74
- 访问器（参见访问方法）
- 外类的，317
- 所有对象共有的，37–72
- 针对枚举类型的常量特定，162
- 可覆盖的, 93
- 摘要描述的, 257
- 线程安全性, 330–332
- 失败原子性与, 308–309
- 转发（参见转发方法）
- 泛型的, 121, 135–138
- 调用、反射和, 282
- 对于`SafeVarargs`, 149
- 最小化...的访问性, 73
- 命名约定, 9, 290–291
- 原生的, 31, 285
- 非 final 的，以及`clone`, 64
- 重载（参见方法重载）
- 重写（参见方法重写）
- 参数列表, 236
- 私有的，用于捕获通配符类型, 145
- 缩短参数列表, 236
- 签名, 3, 236–237
- 大小, 263
- 状态测试, 对比 特殊返回值, 295
- 静态工厂（参见静态工厂方法）
- `SuppressWarnings`注解与, 124
- 有效性检查参数, 227–230
- 可变长度参数, 245–246

### 另参见具体的方法名

- 混入接口, 58, 99
- 混合基本类型，装箱基本类型, 24, 274
- 模块, 76–77
- 货币计算，对应的类型, 270–271
- 蒙提 Python 梗，微妙的, 247
- 多异常捕获机制, 320
- 多继承，模拟, 102

## 可变性

- JavaBeans 模式与, 11
- 最小化, 80–86
- 可变的伴侣类, 84
- 可变归约, 223
- 修改器, 78
- 相互可比较性, 138
- 互斥, 311

## N

- 命名可选参数, 14
- 命名约定, 236, 289–292
- 泛型类型参数的, 131
- 语法上的, 291–292
- 骨架实现类的, 101
- 静态工厂方法的, 9
- 流与, 208
- 类型参数的, 135
- 命名模式对比注解, 180–187
- 原生方法, 31, 285
- 原生伴侣, 31
- 自然排序, 66
- 嵌套类, 112
- 访问级别, 74
- 通过...降低访问性, 74
- 序列化中的, 363
- 类型, 112
- 嵌套接口，访问级别, 74
- 嵌套映射, 173–175
- 非层次结构框架, 99
- 不可实例类, 19
- 不可实例伴侣类, 7
- `equals`的非空性, 38, 45
- 可重化的类型, 127, 131, 146
- 非静态成员类, 112–114
- `notify`与`notifyAll`, 328–329
- 空值检查, 228
- 将引用置空, 27
- `NullPointerException`, `equals`约, 46

## O

- 对象池, 24
- 对象引用字段，`equals`与, 47
- 对象, 3
- 避免反射访问, 282–284
- 基类与, 281
- 创建与销毁, 5–33
- 创建与性能, 6, 22–23
- 反序列化过滤, 342
- 有效不可变, 316
- 消除过时的引用, 26–28, 60, 308
- 创建的开销, 24
- 优先通过接口引用, 280–281
- 函数, 114
- 不可变（参见不可变对象）
- 在不一致状态下, 11–12, 96, 309
-（另参见损坏对象）
- 所有类共方法, 37–72
- 将过时的引用置空, 27
- 处理, 114
- 重用, 22–25
- 安全发布, 316
- 字符串表示, 55–57
- 通过接口引用时, 281
- 模式, 317
- 过时的引用, 26–28, 60, 308
- 打开的, 221
- 缓存哈希值, 53
- 懒初始化, 33–35
- `notify`与`notifyAll`, 328–329
- 对象重用, 22–25
- `equals`中的顺序, 47
- 并行化流, 224
- 静态初始化, 23
- `StringBuffer`与, 279
- 在`equals`中`==`, 46
- 可选的, 249
- 异常与, 295, 298
- 作为返回值, 249–253
- 序数与枚举映射, 171–175
- 对比实例字段, 168
- 重载（参见方法重载）
- `Override`注解, 49, 188–190
- 重写（参见方法重写）

## P

- 包私有访问级别, 4, 74, 84
- 包的命名约定, 289–292
- 并行化流, 222–225

## 参数列表

- 编译器的, 14
- 缩短, 236–237
- 可变长度参数与, 245–246
- 参数化类型, 117–122
- 可重化的, 127
- 无参构造函数, 19

## 参数

- 可变的防御性拷贝, 232
- 类型（参见类型参数）
- 有效性检查，227–230, 353–355
- PECS 记忆法，141
- 性能，286–288
- 自动装箱与，24, 201, 275
- `BigDecimal`与，271
- 构建器模式，16
- 清理器，29–30
- 防御性拷贝与，234
- 枚举的，167, 170
- `equals`的，46–47
- 过度同步的，321
- 终化器，29–30
- for-each 循环与，264
- `hashCode`的，50, 53
- 不可变类与，83–85
- 库与，268
- 测量，287
- 内存泄漏与，27
- 原生方法与，285
- 对象创建与，6, 22–23
- 反射的，282
- 流的并行化与，222–225
- 序列化的，348–350
- 软件架构与，286–287
- 状态测试 vs. 特殊返回值，295
- 静态工厂与，6
- 字符串拼接的，279
- `toString`与，57
- 可变参数与，246
- 包装类与，91

*另请* 优化

- 性能模型，288
- 可移植性
- 清理器与，29
- 终化器与，29
- 原生方法与，285
- 线程优先级与，337
- 线程调度器与，336
- 谓词，104

## 类型字段

- `compareTo`与，69
- `equals`与，47
- 原始类型，273
- 与泛型的不兼容性，134
- optionals 与，253
- 优于包装后的原始类型，24, 273–275

*另请参见各个原始类型*

- 私有访问级别，74
- 私有构造函数，84
- 为了不可实例化，19
- 为了单例，17–18
- 私有锁对象，332
- 私有锁对象，332
- 过程化编程，82
- 过程对象，114
- 生产者-消费者队列，326
- 编程原则，2
- 终化的及时性，29
- 保护访问级别，74–75
- public 访问级别，74
- public 字段 vs. 访问器方法，78–79
- public 可访问锁，331
- 限定的`this`构造，112

## 竞态条件检查，335

- 范围检查，229
- 原始类型，117–122
- `readObject`方法，353–358
- 防御性拷贝与，80
- 如何编写，358
- 与实例控制对象的不兼容，359
- 可覆盖的方法与，96, 358
- `readResolve`方法，97
- 访问级别，362
- 选择访问级别，359–362
- 优于枚举类型，359–362
- 用于实例控制类，359

## 食谱

- 为单个枚举常量添加行为，162
- 为枚举类型添加数据，160
- 构建器模式，12
- `equals`中的重要字段检查，47
- `clone`，64
- `compareTo`，68
- 消除自用，98
- `equals`，46
- 将类泛型化，130–133
- `hashCode`，51
- 在数组上实现泛型，131–133
- 方法链式，14
- 不可实例化类，19
- `readObject`，358
- 序列化代理，363–364
- 序列化单例，18
- 单元素枚举作为单例，18
- 带有私有构造函数的单例，17
- 骨架实现，102
- 标记类到类层次结构，110–111

*另请参见* 规则

- 递归类型边界，137
- 递归类型参数，14
- 归约策略，211
- 归约，223
- 重入锁，320
- 引用类型，3, 273
- 反射，282
- `AccessibleObject`，17
- `clone`与，64
- 的缺点，282
- 反射接口实例化，283
- `compareTo`，68
- `equals`，38–39
- 具化类型，126
- 资源，21
- 资源排序死锁，351
- 锁定的以及终化器，29
- 释放，31
- 受限标记接口，191
- 序列化代理模式与，365

## 编写文档注释, 254–260

## 运行时异常

*参见 未检查异常*

## S

- 安全数组访问, 76
- 安全语言, 231
- 安全发布, 316
- 安全故障, 315
- 并行流和, 224
- `wait`和, 328
- `SafeVarargs`注解, 147
- 合法使用, 149

## 范围

- 局部变量, 261–263
- `SuppressWarnings`注解, 124
- 变量的过时引用和, 27
- 安全，防御性拷贝, 25, 231

## 安全问题

- 可访问的非零数组, 76
- `AccessibleObject.setAccessible`攻击, 17
- 拒绝服务攻击, 331
- 反序列化炸弹, 339–340
- `ElvisStealer`攻击, 362
- 终结器攻击, 30–31
- getget (gadgets), 340
- 内部字段窃取攻击, 355–357
- 勒索软件攻击, 339
- 反射, 17
- 远程代码执行, 340
- 恶意对象引用攻击, 355–357
- 序列化, 339, 344, 353, 360
- 窃取攻击, 362
- 用字符串作为授予数据访问键, 277
- 子类化和, 89
- 检查时间/使用时间 (TOCTOU) 攻击, 233
- SELF 问题, 91

## 自使用

- 文档化，针对继承, 93
- 消除，针对继承, 98
- 序列化版本 UID, 343, 351–352
- `Serializable`, 343–345
- 序列化, 339–366
- 匿名类和, 196
- 成本, 343
- 降低危险, 341–342
- 继承设计和, 96–97
- 针对的文档化, 347, 350
- 对导出 API 的影响, 343
- 灵活的返回类, 365
- 不可变性和, 85, 353
- 内部字段窃取攻击, 360–362
- Lambda 表达式, 196
- 对象反序列化过滤, 342
- 优于替代方案, 339–342
- 单例和, 18
- 同步, 351
- 标记字段, 348
- 有效性, 357
- 何时使用, 345
- 序列化模式, 363–366
- 导出 API 的的序列化形式, 343
- 序列化实例 vs 序列化代理, 363–366
- 服务提供框架, 8
- 短路操作, 223
- 方法签名, 3, 236–237
- 函数, 67
- 简单实现, 103
- 模拟多继承, 102
- 模拟自类型模式, 14
- 单例检查模式, 335
- 单例, 17–18
- vs 依赖注入, 20
- 骨架实现, 100–101
- 源文件, 115–116

## 空间消耗

- 枚举类型, 175
- 不可变对象, 83
- 内存泄漏和, 27
- 非静态成员类和, 113
- Spliterator, 223
- 虚假唤醒, 329
- 状态相关的修改操作, 325
- 状态测试方法, 294–295, 299
- 静态工厂方法的优势, 5–8
- 内部的匿名类, 114
- API 文档中的, 8
- vs 克隆, 65
- 拷贝与转换工厂, 65
- 返回类的灵活性, 7–8
- 泛型单例, 18, 136
- 不可变对象, 22, 82, 84
- 实例控制类和, 6
- 局限性, 8–9
- 命名规范, 9, 292
- 用...替换构造函数, 5–9, 22, 240

## 字符串表示，55–57, 306

### 字符串

- 拼接，279
- 作为其他类型的替代，276–278
- 子类化，3, 87
- 抽象类，以及`equals`，45
- 访问级别和，75
- 适当性，92
- `Cloneable`和，96
- `compareTo`和，68
- `equals`和，40, 42
- 终结器攻击和，31
- 脆弱性，89
- 不变性破坏和，92
- 方法访问级别和，75
- 禁止，8, 18–19, 85, 97
- 序列化和，344
- 骨骼实现，102
- 静态工厂方法和，8
- 作为继承设计的的测试，95

*另参见* 继承

- 子类型关系，134, 140
- Javadoc 中的摘要描述，257
- 超类型关系，141
- `SuppressWarnings`注解，123–125
- `switch`语句和枚举类型，164, 167

### 对称性要求

- `compareTo`，68
- `equals`，38–39

### 同步

- 原子数据的，312–314
- 过度的，317–322
- 和性能，321
- 其影响，317
- 内部的，322
- 为了互斥，311
- 序列化和，351
- 为了共享可变数据，311–316
- 其技术，314–316
- 为了线程通信，312–314

### 同步区域

- 外来方法和，317–321
- 在其中最小化工作，321
- 同步器，326
- 合成注解，186

### T

- tag 字段，109
- 延迟终结，29
- 任务，324
- vs. 线程，323–324
- 阶梯式构造函数模式，10
- Template 方法模式，101, 199
- `this`，在注释中，256
- `this`，在 lambda vs. 匿名类中，196
- 线程池，323
- 调整，336
- 线程优先级，337

### 线程安全

- 文档化，322, 330
- 不可变对象和，82
- 级别，330–331
- 可变性，75, 322
- 线程调度器，336–337
- 线程死锁，328
- 避免`Thread.yield`方法，337
- 线程忙等待，336
- 可抛异常类型，296
- 检查时间/使用时间攻击，233
- TOCTOU 攻击，233
- `toString`方法，55–57
- 枚举类型和，160
- 通用合约，55
- 何时重写，57
- transient 字段，348–351
- 带有`readResolve`，360
- 何时使用，351

### 传递性要求

- `compareTo`，68
- `equals`，38, 40–45

### `try`-`finally`

- 优先使用`try-with-resources`替用 34

### `try`-with-resources

- 优于`try`-`finally`，34–36
- 递归类型边界，137
- 类型推断，70, 123, 142, 194
- 类型参数列表，135
- 类型参数，117, 135
- 有边界的，134, 154
- 命名规范，135, 290
- 递归绑定的，14, 137
- vs. 通配符，144

### 类型安全

- 动态转换和，154
- 从枚举类型，158
- 堆污染和，146
- 泛化类型和，119
- 原始类型和，119
- 类型令牌，151

## 类型

- 转换的，65, 291
- 泛型，117, 130–134
- 用于定义的，107–108
- 非实性的，127, 131
- 参数化的，117–122
- 原始，273
- 引用，273
- 类型安全容器，151–155
- 与实性类型的不兼容性，154

## U

- 无界类型参数，144
- 无界通配符，120
- 嵌套的，152
- vs. 原始类型，121
- 实性的，127

## 未检查异常

- vs. 已检查异常，296–297
- 兼容性，305
- 从方法声明中排除，304
- 目的，296
- 未检查警告，123–125
- 强制转换的，127, 129, 137
- 数字字面量中的划线，108
- 意外的对象留存

*参见* 内存泄漏

- 无意实例化的类，19
- API 用户，4
- 工具类，19
- vs. 常量接口，108
- vs. 依赖注入，20

## V

- 有效性检查
- 构建器和，14
- 构造函数参数，229
- 防御性拷贝和，232
- 针对反序列化对象的，355
- 隐式的，230
- 参数，227–230
- 失败原子性和，308
- `readObject`参数，353–355
- 值类，38
- `toString`和，56
- 值类型与字符串，276
- 可变参数，245–246
- 构建器和，16
- 结合泛型，146–150
- 泛型以及编译器警告，127
- 性能，246
- 变长个数方法，245
- 变长返回类
- 序列化代理模式和，365
- 静态工厂方法和，7–8
- 变量
- 原子操作于，311
- 局部（参见局部变量
- 范围以及失效引用，27
- 为了避免子类化，44, 68
- 为了维护不变性，234
- 命名规范，291
- 对象复用和，23
- `volatile`修饰符，314–315

## W

- 等待循环用例，328–329
- 警告，未检查（参见未检查警告
- `while`循环与`for`循环，262
- 通配符类型
- 捕获，145
- 与类型参数，144
- （参见有界通配符类型;无界通配符类型
- 工作队列，326
- 包装类用例，100
- 包装类，89–91
- 防御性拷贝和，235
- 与回调框架不，91
- 与子类化相比，97
- `writeReplace`方法的访问级别，97

## Z

- 零长度数组的不可变性，248

## 代码段

许多标题都包含编程代码或配置示例。为了优化这些元素的呈现效果，请以单列横屏模式查看电子书，并将字体大小调整为最小设置。除了以流式文本格式展示代码和配置外，我们还包含了代码的图像，以模拟印刷书籍中的呈现效果；因此，当流式格式可能会损害代码列表的呈现效果时，您将看到“点击此处查看代码图像”链接。点击链接即可查看高保真代码图像。要返回之前查看的页面，请点击设备或应用程序上的“后退”按钮。

![Image](img/#ch2.xhtml_pch2ex1)![Image](img/#ch2.xhtml_pch2ex2)![Image](img/#ch2.xhtml_pch2ex3)![Image](img/#ch2.xhtml_pch2ex4)![Image](img/#ch2.xhtml_pch2ex5)![Image](img/#ch2.xhtml_pch2ex6)![Image](img/#ch2.xhtml_pch2ex7)![Image](img/#ch2.xhtml_pch2ex8)![Image](img/#ch2.xhtml_pch2ex9)![Image](img/#ch2.xhtml_pch2ex10)![Image](img/#ch2.xhtml_pch2ex11)![Image](img/#ch2.xhtml_pch2ex12)![Image](img/#ch2.xhtml_pch2ex13)![Image](img/#ch2.xhtml_pch2ex14)![Image](img/#ch2.xhtml_pch2ex15)![Image](img/#ch2.xhtml_pch2ex16)![Image](img/#ch2.xhtml_pch2ex17)![Image](img/#ch2.xhtml_pch2ex18)![Image](img/#ch2.xhtml_pch2ex19)![Image](img/#ch2.xhtml_pch2ex20)![Image](img/#ch2.xhtml_pch2ex21)![Image](img/#ch2.xhtml_pch2ex22)![Image](img/#ch2.xhtml_pch2ex23)![Image](img/#ch2.xhtml_pch2ex24)![Image](img/#ch2.xhtml_pch2ex25)![Image](img/#ch2.xhtml_pch2ex26)![Image](img/#ch2.xhtml_pch2ex27)![Image](img/#ch2.xhtml_pch2ex28)![Image](img/#ch2.xhtml_pch2ex29)![Image](img/#ch2.xhtml_pch2ex30)![Image](img/#ch2.xhtml_pch2ex31)![Image](img/#ch2.xhtml_pch2ex32)![Image](img/#ch2.xhtml_pch2ex33)![Image](img/#ch2.xhtml_pch2ex34)![Image](img/#ch2.xhtml_pch2ex35)![Image](img/#ch2.xhtml_pch2ex36)![Image](img/#ch2.xhtml_pch2ex37)![Image](img/#ch2.xhtml_pch2ex38)![Image](img/#ch2.xhtml_pch2ex39)![Image](img/#ch2.xhtml_pch2ex40)![Image](img/#ch3.xhtml_pch3ex1)![Image](img/#ch3.xhtml_pch3ex2)![Image](img/#ch3.xhtml_pch3ex3)![Image](img/#ch3.xhtml_pch3ex4)![Image](img/#ch3.xhtml_pch3ex5)![Image](img/#ch3.xhtml_pch3ex6)![Image](img/#ch3.xhtml_pch3ex7)![Image](img/#ch3.xhtml_pch3ex8)![Image](img/#ch3.xhtml_pch3ex9)![Image](img/#ch3.xhtml_pch3ex10)![Image](img/#ch3.xhtml_pch3ex11)![Image](img/#ch3.xhtml_pch3ex12)![Image](img/#ch3.xhtml_pch3ex13)![Image](img/#ch3.xhtml_pch3ex14)![Image](img/#ch3.xhtml_pch3ex15)![Image](img/#ch3.xhtml_pch3ex16)![Image](img/#ch3.xhtml_pch3ex17)![Image](img/#ch3.xhtml_pch3ex18)![Image](img/#ch3.xhtml_pch3ex19)![Image](img/#ch3.xhtml_pch3ex20)![Image](img/#ch3.xhtml_pch3ex21)![Image](img/#ch3.xhtml_pch3ex22)![Image](img/#ch3.xhtml_pch3ex23)![Image](img/#ch3.xhtml_pch3ex24)![Image](img/#ch3.xhtml_pch3ex25)![Image](img/#ch3.xhtml_pch3ex26)![Image](img/#ch3.xhtml_pch3ex27)![Image](img/#ch3.xhtml_pch3ex28)![Image](img/#ch3.xhtml_pch3ex29)![Image](img/#ch3.xhtml_pch3ex30)![Image](img/#ch3.xhtml_pch3ex31)![Image](img/#ch3.xhtml_pch3ex32)![Image](img/#ch3.xhtml_pch3ex33)![Image](img/#ch3.xhtml_pch3ex34)![Image](img/#ch3.xhtml_pch3ex35)![Image](img/#ch3.xhtml_pch3ex36)![Image](img/#ch3.xhtml_pch3ex37)![Image](img/#ch3.xhtml_pch3ex38)![Image](img/#ch3.xhtml_pch3ex39)![Image](img/#ch3.xhtml_pch3ex40)![Image](img/#ch3.xhtml_pch3ex41)![Image](img/#ch3.xhtml_pch3ex42)![Image](img/#ch3.xhtml_pch3ex43)![Image](img/#ch3.xhtml_pch3ex44)![Image](img/#ch3.xhtml_pch3ex45)![Image](img/#ch3.xhtml_pch3ex46)![Image](img/#ch3.xhtml_pch3ex47)![Image](img/#ch3.xhtml_pch3ex48)![Image](img/#ch3.xhtml_pch3ex49)![Image](img/#ch4.xhtml_pch4ex1)![Image](img/#ch4.xhtml_pch4ex2)![Image](img/#ch4.xhtml_pch4ex3)![Image](img/#ch4.xhtml_pch4ex4)![Image](img/#ch4.xhtml_pch4ex5)![Image](img/#ch4.xhtml_pch4ex6)![Image](img/#ch4.xhtml_pch4ex7)![Image](img/#ch4.xhtml_pch4ex8)![Image](img/#ch4.xhtml_pch4ex9)![Image](img/#ch4.xhtml_pch4ex10)![Image](img/#ch4.xhtml_pch4ex11)![Image](img/#ch4.xhtml_pch4ex12)![Image](img/#ch4.xhtml_pch4ex13)![Image](img/#ch4.xhtml_pch4ex14)![Image](img/#ch4.xhtml_pch4ex15)![Image](img/#ch4.xhtml_pch4ex16)![Image](img/#ch4.xhtml_pch4ex17)![Image](img/#ch4.xhtml_pch4ex18)![Image](img/#ch4.xhtml_pch4ex19)![Image](img/#ch4.xhtml_pch4ex20)![Image](img/#ch4.xhtml_pch4ex21)![Image](img/#ch4.xhtml_pch4ex22)![Image](img/#ch4.xhtml_pch4ex23)![Image](img/#ch4.xhtml_pch4ex24)![Image](img/#ch4.xhtml_pch4ex25)![Image](img/#ch4.xhtml_pch4ex26)![Image](img/#ch4.xhtml_pch4ex27)![Image](img/#ch4.xhtml_pch4ex28)![Image](img/#ch4.xhtml_pch4ex29)![Image](img/#ch4.xhtml_pch4ex30)![Image](img/#ch4.xhtml_pch4ex31)![Image](img/#ch4.xhtml_pch4ex32)![Image](img/#ch4.xhtml_pch4ex33)![Image](img/#ch4.xhtml_pch4ex34)![Image](img/#ch4.xhtml_pch4ex35)![Image](img/#ch4.xhtml_pch4ex36)![Image](img/#ch4.xhtml_pch4ex37)![Image](img/#ch4.xhtml_pch4ex38)![Image](img/#ch4.xhtml_pch4ex39)![Image](img/#ch4.xhtml_pch4ex40)![Image](img/#ch4.xhtml_pch4ex41)![Image](img/#ch4.xhtml_pch4ex42)![Image](img/#ch4.xhtml_pch4ex43)![Image](img/#ch4.xhtml_pch4ex44)![Image](img/#ch4.xhtml_pch4ex45)![Image](img/#ch4.xhtml_pch4ex46)![Image](img/#ch4.xhtml_pch4ex47)![Image](img/#ch4.xhtml_pch4ex48)![Image](img/#ch4.xhtml_pch4ex49)![Image](img/#ch4.xhtml_pch4ex50)![Image](img/#ch4.xhtml_pch4ex51)![Image](img/#ch4.xhtml_pch4ex52)![Image](img/#ch4.xhtml_pch4ex53)![Image](img/#ch4.xhtml_pch4ex54)![Image](img/#ch4.xhtml_pch4ex55)![Image](img/#ch4.xhtml_pch4ex56)![Image](img/#ch4.xhtml_pch4ex57)![Image](img/#ch4.xhtml_pch4ex58)![Image](img/#ch4.xhtml_pch4ex59)![Image](img/#ch4.xhtml_pch4ex60)![Image](img/#ch4.xhtml_pch4ex61)![Image](img/#ch4.xhtml_pch4ex62)![Image](img/#ch4.xhtml_pch4ex63)![Image](img/#ch4.xhtml_pch4ex64)![Image](img/#ch4.xhtml_pch4ex65)![Image](img/#ch4.xhtml_pch4ex66)![Image](img/#ch4.xhtml_pch4ex67)![Image](img/#ch4.xhtml_pch4ex68)![Image](img/#ch4.xhtml_pch4ex69)![Image](img/#ch4.xhtml_pch4ex70)![Image](img/#ch4.xhtml_pch4ex71)![Image](img/#ch4.xhtml_pch4ex72)![Image](img/#ch4.xhtml_pch4ex73)![Image](img/#ch4.xhtml_pch4ex74)![Image](img/#ch4.xhtml_pch4ex75)![Image](img/#ch4.xhtml_pch4ex76)![Image](img/#ch4.xhtml_pch4ex77)![Image](img/#ch4.xhtml_pch4ex78)![Image](img/#ch4.xhtml_pch4ex79)![Image](img/#ch4.xhtml_pch4ex80)![Image](img/#ch4.xhtml_pch4ex81)![Image](img/#ch4.xhtml_pch4ex82)![Image](img/#ch4.xhtml_pch4ex83)![Image](img/#ch4.xhtml_pch4ex84)![Image](img/#ch4.xhtml_pch4ex85)![Image](img/#ch4.xhtml_pch4ex86)![Image](img/#ch4.xhtml_pch4ex87)![Image](img/#ch4.xhtml_pch4ex88)![Image](img/#ch4.xhtml_pch4ex89)![Image](img/#ch4.xhtml_pch4ex90)![Image](img/#ch4.xhtml_pch4ex91)![Image](img/#ch4.xhtml_pch4ex92)![Image](img/#ch4.xhtml_pch4ex93)![Image](img/#ch4.xhtml_pch4ex94)![Image](img/#ch4.xhtml_pch4ex95)![Image](img/#ch4.xhtml_pch4ex96)![Image](img/#ch4.xhtml_pch4ex97)![Image](img/#ch4.xhtml_pch4ex98)![Image](img/#ch4.xhtml_pch4ex99)![Image](img/#ch4.xhtml_pch4ex100)![Image](img/#ch4.xhtml_pch4ex101)![Image](img/#ch4.xhtml_pch4ex102)![Image](img/#ch4.xhtml_pch4ex103)![Image](img/#ch4.xhtml_pch4ex104)![Image](img/#ch4.xhtml_pch4ex105)![Image](img/#ch4.xhtml_pch4ex106)![Image](img/#ch4.xhtml_pch4ex107)![Image](img/#ch4.xhtml_pch4ex108)![Image](img/#ch4.xhtml_pch4ex109)![Image](img/#ch4.xhtml_pch4ex110)![Image](img/#ch4.xhtml_pch4ex111)![Image](img/#ch4.xhtml_pch4ex112)![Image](img/#ch4.xhtml_pch4ex113)![Image](img/#ch4.xhtml_pch4ex114)![Image](img/#ch4.xhtml_pch4ex115)![Image](img/#ch4.xhtml_pch4ex116)![Image](img/#ch4.xhtml_pch4ex117)![Image](img/#ch4.xhtml_pch4ex118)![Image](img/#ch4.xhtml_pch4ex119)![Image](img/#ch4.xhtml_pch4ex120)![Image](img/#ch4.xhtml_pch4ex121)![Image](img/#ch4.xhtml_pch4ex122)![Image](img/#ch4.xhtml_pch4ex123)![Image](img/#ch4.xhtml_pch4ex124)![Image](img/#ch4.xhtml_pch4ex125)![Image](img/#ch4.xhtml_pch4ex126)![Image](img/#ch4.xhtml_pch4ex127)![Image](img/#ch4.xhtml_pch4ex128)![Image](img/#ch4.xhtml_pch4ex129)![Image](img/#ch4.xhtml_pch4ex130)![Image](img/#ch4.xhtml_pch4ex131)![Image](img/#ch4.xhtml_pch4ex132)![Image](img/#ch4.xhtml_pch4ex133)![Image](img/#ch4.xhtml_pch4ex134)![Image](img/#ch4.xhtml_pch4ex135)![Image](img/#ch4.xhtml_pch4ex136)![Image](img/#ch4.xhtml_pch4ex137)![Image](img/#ch4.xhtml_pch4ex138)![Image](img/#ch4.xhtml_pch4ex139)![Image](img/#ch4.xhtml_pch4ex140)![Image](img/#ch4.xhtml_pch4ex141)![Image](img/#ch4.xhtml_pch4ex142)![Image](img/#ch4.xhtml_pch4ex143)![Image](img/#ch4.xhtml_pch4ex144)![Image](img/#ch4.xhtml_pch4ex145)![Image](img/#ch4.xhtml_pch4ex146)![Image](img/#ch4.xhtml_pch4ex147)![Image](img/#ch4.xhtml_pch4ex148)![Image](img/#ch4.xhtml_pch4ex149)![Image](img/#ch4.xhtml_pch4ex150)![Image](img/#ch4.xhtml_pch4ex151)![Image](img/#ch4.xhtml_pch4ex152)![Image](img/#ch4.xhtml_pch4ex153)![Image](img/#ch4.xhtml_pch4ex154)![Image](img/#ch4.xhtml_pch4ex155)![Image](img/#ch4.xhtml_pch4ex156)![Image](img/#ch4.xhtml_pch4ex157)![Image](img/#ch4.xhtml_pch4ex158)![Image](img/#ch4.xhtml_pch4ex159)![Image](img/#ch4.xhtml_pch4ex160)![Image](img/#ch4.xhtml_pch4ex161)![Image](img/#ch4.xhtml_pch4ex162)![Image](img/#ch4.xhtml_pch4ex163)![Image](img/#ch4.xhtml_pch4ex164)![Image](img/#ch4.xhtml_pch4ex165)![Image](img/#ch4.xhtml_pch4ex166)![Image](img/#ch4.xhtml_pch4ex167)![Image](img/#ch4.xhtml_pch4ex168)![Image](img/#ch4.xhtml_pch4ex169)![Image](img/#ch4.xhtml_pch4ex170)![Image](img/#ch4.xhtml_pch4ex171)![Image](img/#ch4.xhtml_pch4ex172)![Image](img/#ch4.xhtml_pch4ex173)![Image](img/#ch4.xhtml_pch4ex174)![Image](img/#ch4.xhtml_pch4ex175)![Image](img/#ch4.xhtml_pch4ex176)![Image](img/#ch4.xhtml_pch4ex177)![Image](img/#ch4.xhtml_pch4ex178)![Image](img/#ch4.xhtml_pch4ex179)![Image](img/#ch4.xhtml_pch4ex180)![Image](img/#ch4.xhtml_pch4ex181)![Image](img/#ch4.xhtml_pch4ex182)![Image](img/#ch4.xhtml_pch4ex183)![Image](img/#ch4.xhtml_pch4ex184)![Image](img/#ch4.xhtml_pch4ex185)![Image](img/#ch4.xhtml_pch4ex186)![Image](img/#ch4.xhtml_pch4ex187)![Image](img/#ch4.xhtml_pch4ex188)![Image](img/#ch4.xhtml_pch4ex189)![Image](img/#ch4.xhtml_pch4ex190)![Image](img/#ch4.xhtml_pch4ex191)![Image](img/#ch4.xhtml_pch4ex192)![Image](img/#ch4.xhtml_pch4ex193)![Image](img/#ch4.xhtml_pch4ex194)![Image](img/#ch4.xhtml_pch4ex195)![Image](img/#ch4.xhtml_pch4ex196)![Image](img/#ch4.xhtml_pch4ex197)![Image](img/#ch4.xhtml_pch4ex198)![Image](img/#ch4.xhtml_pch4ex199)![Image](img/#ch4.xhtml_pch4ex200)![Image](img/#ch4.xhtml_pch4ex201)![Image](img/#ch4.xhtml_pch4ex202)![Image](img/#ch4.xhtml_pch4ex203)![Image](img/#ch4.xhtml_pch4ex204)![Image](img/#ch4.xhtml_pch4ex205)![Image](img/#ch4.xhtml_pch4ex206)![Image](img/#ch4.xhtml_pch4ex207)![Image](img/#ch4.xhtml_pch4ex208)![Image](img/#ch4.xhtml_pch4ex209)![Image](img/#ch4.xhtml_pch4ex210)![Image](img/#ch4.xhtml_pch4ex211)![Image](img/#ch4.xhtml_pch4ex212)![Image](img/#ch4.xhtml_pch4ex213)![Image](img/#ch4.xhtml_pch4ex214)![Image](img/#ch4.xhtml_pch4ex215)![Image](img/#ch4.xhtml_pch4ex216)![Image](img/#ch4.xhtml_pch4ex217)![Image](img/#ch4.xhtml_pch4ex218)![Image](img/#ch4.xhtml_pch4ex219)![Image](img/#ch4.xhtml_pch4ex220)![Image](img/#ch4.xhtml_pch4ex221)![Image](img/#ch4.xhtml_pch4ex222)![Image](img/#ch4.xhtml_pch4ex223)![Image](img/#ch4.xhtml_pch4ex224)![Image](img/#ch4.xhtml_pch4ex225)![Image](img/#ch4.xhtml_pch4ex226)![Image](img/#ch4.xhtml_pch4ex227)![Image](img/#ch4.xhtml_pch4ex228)![Image](img/#ch4.xhtml_pch4ex229)![Image](img/#ch4.xhtml_pch4ex230)![Image](img/#ch4.xhtml_pch4ex231)![Image](img/#ch4.xhtml_pch4ex232)![Image](img/#ch4.xhtml_pch4ex233)![Image](img/#ch4.xhtml_pch4ex234)![Image](img/#ch4.xhtml_pch4ex235)![Image](img/#ch4.xhtml_pch4ex236)![Image](img/#ch4.xhtml_pch4ex237)![Image](img/#ch4.xhtml_pch4ex238)![Image](img/#ch4.xhtml_pch4ex239)![Image](img/#ch4.xhtml_pch4ex240)![Image](img/#ch4.xhtml_pch4ex241)![Image](img/#ch4.xhtml_pch4ex242)![Image](img/#ch4.xhtml_pch4ex243)![Image](img/#ch4.xhtml_pch4ex244)![Image](img/#ch4.xhtml_pch4ex245)![Image](img/#ch4.xhtml_pch4ex246)![Image](img/#ch4.xhtml_pch4ex247)![Image](img/#ch4.xhtml_pch4ex248)![Image](img/#ch4.xhtml_pch4ex249)![Image](img/#ch4.xhtml_pch4ex250)![Image](img/#ch4.xhtml_pch4ex251)![Image](img/#ch4.xhtml_pch4ex252)![Image](img/#ch4.xhtml_pch4ex253)![Image](img/#ch4.xhtml_pch4ex254)![Image](img/#ch4.xhtml_pch4ex255)![Image](img/#ch4.xhtml_pch4ex256)![Image](img/#ch4.xhtml_pch4ex257)![Image](img/#ch4.xhtml_pch4ex258)![Image](img/#ch4.xhtml_pch4ex259)![Image](img/#ch4.xhtml_pch4ex260)![Image](img/#ch4.xhtml_pch4ex261)![Image](img/#ch4.xhtml_pch4ex262)![Image](img/#ch4.xhtml_pch4ex263)![Image](img/#ch4.xhtml_pch4ex264)![Image](img/#ch4.xhtml_pch4ex265)![Image](img/#ch4.xhtml_pch4ex266)![Image](img/#ch4.xhtml_pch4ex267)![Image](img/#ch4.xhtml_pch4ex268)![Image](img/#ch4.xhtml_pch4ex269)![Image](img/#ch4.xhtml_pch4ex270)![Image](img/#ch4.xhtml_pch4ex271)![Image](img/#ch4.xhtml_pch4ex272)![Image](img/#ch4.xhtml_pch4ex273)![Image](img/#ch4.xhtml_pch4ex274)![Image](img/#ch4.xhtml_pch4ex275)![Image](img/#ch4.xhtml_pch4ex276)![Image](img/#ch4.xhtml_pch4ex277)![Image](img/#ch4.xhtml_pch4ex278)![Image](img/#ch4.xhtml_pch4ex279)![Image](img/#ch4.xhtml_pch4ex280)![Image](img/#ch4.xhtml_pch4ex281)![Image](img/#ch4.xhtml_pch4ex282)![Image](img/#ch4.xhtml_pch4ex283)![Image](img/#ch4.xhtml_pch4ex284)![Image](img/#ch4.xhtml_pch4ex285)![Image](img/#ch4.xhtml_pch4ex286)![Image](img/#ch4.xhtml_pch4ex287)![Image](img/#ch4.xhtml_pch4ex288)![Image](img/#ch4.xhtml_pch4ex289)![Image](img/#ch4.xhtml_pch4ex290)![Image](img/#ch4.xhtml_pch4ex291)![Image](img/#ch4.xhtml_pch4ex292)![Image](img/#ch4.xhtml_pch4ex293)![Image](img/#ch4.xhtml_pch4ex294)![Image](img/#ch4.xhtml_pch4ex295)![Image](img/#ch4.xhtml_pch4ex296)![Image](img/#ch4.xhtml_pch4ex297)![Image](img/#ch4.xhtml_pch4ex298)![Image](img/#ch4.xhtml_pch4ex299)![Image](img/#ch4.xhtml_pch4ex300)![Image](img/#ch4.xhtml_pch4ex301)![Image](img/#ch4.xhtml_pch4ex302)![Image](img/#ch4.xhtml_pch4ex303)![Image](img/#ch4.xhtml_pch4ex304)![Image](img/#ch4.xhtml_pch4ex305)![Image](img/#ch4.xhtml_pch4ex306)![Image](img/#ch4.xhtml_pch4ex307)![Image](img/#ch4.xhtml_pch4ex308)![Image](img/#ch4.xhtml_pch4ex309)![Image](img/#ch4.xhtml_pch4ex310)![Image](img/#ch4.xhtml_pch4ex311)![Image](img/#ch4.xhtml_pch4ex312)![Image](img/#ch4.xhtml_pch4ex313)![Image](img/#ch4.xhtml_pch4ex314)![Image](img/#ch4.xhtml_pch4ex315)![Image](img/#ch4.xhtml_pch4ex316)![Image](img/#ch4.xhtml_pch4ex317)![Image](img/#ch4.xhtml_pch4ex318)![Image](img/#ch4.xhtml_pch4ex319)![Image](img/#ch4.xhtml_pch4ex320)![Image](img/#ch4.xhtml_pch4ex321)![Image](img/#ch4.xhtml_pch4ex322)![Image](img/#ch4.xhtml_pch4ex323)![Image](img/#ch4.xhtml_pch4ex324)![Image](img/#ch4.xhtml_pch4ex325)![Image](img/#ch4.xhtml_pch4ex326)![Image](img/#ch4.xhtml_pch4ex327)![Image](img/#ch4.xhtml_pch4ex328)![Image](img/#ch4.xhtml_pch4ex329)![Image](img/#ch4.xhtml_pch4ex330)![Image](img/#ch4.xhtml_pch4ex331)![Image](img/#ch4.xhtml_pch4ex332)![Image](img/#ch4.xhtml_pch4ex333)![Image](img/#ch4.xhtml_pch4ex334)![Image](img/#ch4.xhtml_pch4ex335)![Image](img/#ch4.xhtml_pch4ex336)![Image](img/#ch4.xhtml_pch4ex337)![Image](img/#ch4.xhtml_pch4ex338)![Image](img/#ch4.xhtml_pch4ex339)![Image](img/#ch4.xhtml_pch4ex340)![Image](img/#ch4.xhtml_pch4ex341)![Image](img/#ch4.xhtml_pch4ex342)![Image](img/#ch4.xhtml_pch4ex343)![Image](img/#ch4.xhtml_pch4ex344)![Image](img/#ch4.xhtml_pch4ex345)![Image](img/#ch4.xhtml_pch4ex346)![Image](img/#ch4.xhtml_pch4ex347)![Image](img/#ch4.xhtml_pch4ex348)![Image](img/#ch4.xhtml_pch4ex349)![Image](img/#ch4.xhtml_pch4ex350)![Image](img/#ch4.xhtml_pch4ex351)![Image](img/#ch4.xhtml_pch4ex352)![Image](img/#ch4.xhtml_pch4ex353)![Image](img/#ch4.xhtml_pch4ex354)![Image](img/#ch4.xhtml_pch4ex355)![Image](img/#ch4.xhtml_pch4ex356)![Image](img/#ch4.xhtml_pch4ex357)![Image](img/#ch4.xhtml_pch4ex358)![Image](img/#ch4.xhtml_pch4ex359)![Image](img/#ch4.xhtml_pch4ex360)![Image](img/#ch4.xhtml_pch4ex361)![Image](img/#ch4.xhtml_pch4ex362)![Image](img/#ch4.xhtml_pch4ex363)![Image](img/#ch4.xhtml_pch4ex364)![Image](img/#ch4.xhtml_pch4ex365)![Image](img/#ch4.xhtml_pch4ex366)![Image](img/#ch4.xhtml_pch4ex367)![Image](img/#ch4.xhtml_pch4ex368)![Image](img/#ch4.xhtml_pch4ex369)![Image](img/#ch4.xhtml_pch4ex370)![Image](img/#ch4.xhtml_pch4ex371)![Image](img/#ch4.xhtml_pch4ex372)![Image](img/#ch4.xhtml_pch4ex373)![Image](img/#ch4.xhtml_pch4ex374)![Image](img/#ch4.xhtml_pch4ex375)![Image](img/#ch4.xhtml_pch4ex376)![Image](img/#ch4.xhtml_pch4ex377)![Image](img/#ch4.xhtml_pch4ex378)![Image](img/#ch4.xhtml_pch4ex379)![Image](img/#ch4.xhtml_pch4ex380)![Image](img/#ch4.xhtml_pch4ex381)![Image](img/#ch4.xhtml_pch4ex382)![Image](img/#ch4.xhtml_pch4ex383)![Image](img/#ch4.xhtml_pch4ex384)![Image](img/#ch4.xhtml_pch4ex385)![Image](img/#ch4.xhtml_pch4ex386)![Image](img/#ch4.xhtml_pch4ex387)![Image](img/#ch4.xhtml_pch4ex388)![Image](img/#ch4.xhtml_pch4ex389)![Image](img/#ch4.xhtml_pch4ex390)![Image](img/#ch4.xhtml_pch4ex391)![Image](img/#ch4.xhtml_pch4ex392)![Image](img/#ch4.xhtml_pch4ex393)![Image](img/#ch4.xhtml_pch4ex394)![Image](img/#ch4.xhtml_pch4ex395)![Image](img/#ch4.xhtml_pch4ex396)![Image](img/#ch4.xhtml_pch4ex397)![Image](img/#ch4.xhtml_pch4ex398)![Image](img/#ch4.xhtml_pch4ex399)![Image](img/#ch4.xhtml_pch4ex400)![Image](img/#ch4.xhtml_pch4ex401)![Image](img/#ch4.xhtml_pch4ex402)![Image](img/#ch4.xhtml_pch4ex403)![Image](img/#ch4.xhtml_pch4ex404)![Image](img/#ch4.xhtml_pch4ex405)![Image](img/#ch4.xhtml_pch4ex406)![Image](img/#ch4.xhtml_pch4ex407)![Image](img/#ch4.xhtml_pch4ex408)![Image](img/#ch4.xhtml_pch4ex409)![Image](img/#ch4.xhtml_pch4ex410)![Image](img/#ch4.xhtml_pch4ex411)![Image](img/#ch4.xhtml_pch4ex412)![Image](img/#ch4.xhtml_pch4ex413)![Image](img/#ch4.xhtml_pch4ex414)![Image](img/#ch4.xhtml_pch4ex415)![Image](img/#ch4.xhtml_pch4ex416)![Image](img/#ch4.xhtml_pch4ex417)![Image](img/#ch4.xhtml_pch4ex418)![Image](img/#ch4.xhtml_pch4ex419)![Image](img/#ch4.xhtml_pch4ex420)![Image](img/#ch4.xhtml_pch4ex421)![Image](img/#ch4.xhtml_pch4ex422)![Image](img/#ch4.xhtml_pch4ex423)![Image](img/#ch4.xhtml_pch4ex424)![Image](img/#ch4.xhtml_pch4ex425)![Image](img/#ch4.xhtml_pch4ex426)![Image](img/#ch4.xhtml_pch4ex427)![Image](img/#ch4.xhtml_pch4ex428)![Image](img/#ch4.xhtml_pch4ex429)![Image](img/#ch4.xhtml_pch4ex430)![Image](img/#ch4.xhtml_pch4ex431)![Image](img/#ch4.xhtml_pch4ex432)![Image](img/#ch4.xhtml_pch4ex433)![Image](img/#ch4.xhtml_pch4ex434)![Image](img/#ch4.xhtml_pch4ex435)![Image](img/#ch4.xhtml_pch4ex436)![Image](img/#ch4.xhtml_pch4ex437)![Image](img/#ch4.xhtml_pch4ex438)![Image](img/#ch4.xhtml_pch4ex439)![Image](img/#ch4.xhtml_pch4ex440)![Image](img/#ch4.xhtml_pch4ex441)![Image](img/#ch4.xhtml_pch4ex442)![Image](img/#ch4.xhtml_pch4ex443)![Image](img/#ch4.xhtml_pch4ex444)![Image](img/#ch4.xhtml_pch4ex445)![Image](img/#ch4.xhtml_pch4ex446)![Image](img/#ch4.xhtml_pch4ex447)![Image](img/#ch4.xhtml_pch4ex448)![Image](img/#ch4.xhtml_pch4ex449)![Image](img/#ch4.xhtml_pch4ex450)![Image](img/#ch4.xhtml_pch4ex451)![Image](img/#ch4.xhtml_pch4ex452)![Image](img/#ch4.xhtml_pch4ex453)![Image](img/#ch4.xhtml_pch4ex454)![Image](img/#ch4.xhtml_pch4ex455)![Image](img/#ch4.xhtml_pch4ex456)![Image](img/#ch4.xhtml_pch4ex457)![Image](img/#ch4.xhtml_pch4ex458)![Image](img/#ch4.xhtml_pch4ex459)![Image](img/#ch4.xhtml_pch4ex460)![Image](img/#ch4.xhtml_pch4ex461)![Image](img/#ch4.xhtml_pch4ex462)![Image](img/#ch4.xhtml_pch4ex463)![Image](img/#ch4.xhtml_pch4ex464)![Image](img/#ch4.xhtml_pch4ex465)![Image](img/#ch4.xhtml_pch4ex466)![Image](img/#ch4.xhtml_pch4ex467)![Image](img/#ch4.xhtml_pch4ex468)![Image](img/#ch4.xhtml_pch4ex469)![Image](img/#ch4.xhtml_pch4ex470)![Image](img/#ch4.xhtml_pch4ex471)![Image](img/#ch4.xhtml_pch4ex472)![Image](img/#ch4.xhtml_pch4ex473)![Image](img/#ch4.xhtml_pch4ex474)![Image](img/#ch4.xhtml_pch4ex475)![Image](img/#ch4.xhtml_pch4ex476)![Image](img/#ch4.xhtml_pch4ex477)![Image](img/#ch4.xhtml_pch4ex478)![Image](img/#ch4.xhtml_pch4ex479)![Image](img/#ch4.xhtml_pch4ex480)![Image](img/#ch4.xhtml_pch4ex481)![Image](img/#ch4.xhtml_pch4ex482)![Image](img/#ch4.xhtml_pch4ex483)![Image](img/#ch4.xhtml_pch4ex484)![Image](img/#ch4.xhtml_pch4ex485)![Image](img/#ch4.xhtml_pch4ex486)![Image](img/#ch4.xhtml_pch4ex487)![Image](img/#ch4.xhtml_pch4ex488)![Image](img/#ch4.xhtml_pch4ex489)![Image](img/#ch4.xhtml_pch4ex490)![Image](img/#ch4.xhtml_pch4ex491)![Image](img/#ch4.xhtml_pch4ex492)![Image](img/#ch4.xhtml_pch4ex493)![Image](img/#ch4.xhtml_pch4ex494)![Image](img/#ch4.xhtml_pch4ex495)![Image](img/#ch4.xhtml_pch4ex496)![Image](img/#ch4.xhtml_pch4ex497)![Image](img/#ch4.xhtml_pch4ex498)![Image](img/#ch4.xhtml_pch4ex499)![Image](img/#ch4.xhtml_pch4ex500)![Image](img/#ch4.xhtml_pch4ex501)![Image](img/#ch4.xhtml_pch4ex502)![Image](img/#ch4.xhtml_pch4ex503)![Image](img/#ch4.xhtml_pch4ex504)![Image](img/#ch4.xhtml_pch4ex505)![Image](img/#ch4.xhtml_pch4ex506)![Image](img/#ch4.xhtml_pch4ex507)![Image](img/#ch4.xhtml_pch4ex508)![Image](img/#ch4.xhtml_pch4ex509)![Image](img/#ch4.xhtml_pch4ex510)![Image](img/#ch4.xhtml_pch4ex511)![Image](img/#ch4.xhtml_pch4ex512)![Image](img/#ch4.xhtml_pch4ex513)![Image](img/#ch4.xhtml_pch4ex514)![Image](img/#ch4.xhtml_pch4ex515)![Image](img/586pro01.jpg)](#ch4.xhtml_pch4ex516)![Image](img/587pro01.jpg)](#ch4.xhtml_pch4ex517)![Image](img/588pro01.jpg)](#ch4.xhtml_pch4ex518)![Image](img/589pro01.jpg)](#ch4.xhtml_pch4ex519)![Image](img/590pro01.jpg)](#ch4.xhtml_pch4ex520)![Image](img/591pro01.jpg)](#ch4.xhtml_pch4ex521)![Image](img/592pro01.jpg)](#ch4.xhtml_pch4ex522)![Image](img/593pro01.jpg)](#ch4.xhtml_pch4ex523)![Image](img/594pro01.jpg)](#ch4.xhtml_pch4ex524)![Image](img/595pro01.jpg)](#ch4.xhtml_pch4ex525)![Image](img/596pro01.jpg)](#ch4.xhtml_pch4ex526)![Image](img/597pro01.jpg)](#ch4.xhtml_pch4ex527)![Image](img/598pro01.jpg)](#ch4.xhtml_pch4ex528)![Image](img/599pro01.jpg)](#ch4.xhtml_pch4ex529)![Image](img/600pro01.jpg)](#ch4.xhtml_pch4ex530)![Image](img/601pro01.jpg)](#ch4.xhtml_pch4ex531)![Image](img/602pro01.jpg)](#ch4.xhtml_pch4ex532)![Image](img/603pro01.jpg)](#ch4.xhtml_pch4ex533)![Image](img/604pro01.jpg)](#ch4.xhtml_pch4ex534)![Image](img/605pro01.jpg)](#ch4.xhtml_pch4ex535)![Image](img/606pro01.jpg)](#ch4.xhtml_pch4ex536)![Image](img/607pro01.jpg)](#ch4.xhtml_pch4ex537)![Image](img/608pro01.jpg)](#ch4.xhtml_pch4ex538)![Image](img/609pro01.jpg)](#ch4.xhtml_pch4ex539)![Image](img/610pro01.jpg)](#ch4.xhtml_pch4ex540)![Image](img/611pro01.jpg)](#ch4.xhtml_pch4ex541)![Image](img/612pro01.jpg)](#ch4.xhtml_pch4ex542)![Image](img/613pro01.jpg)](#ch4.xhtml_pch4ex543)![Image](img/614pro01.jpg)](#ch4.xhtml_pch4ex544)![Image](img/615pro01.jpg)](#ch4.xhtml_pch4ex545)![Image](img/616pro01.jpg)](#ch4.xhtml_pch4ex546)![Image](img/617pro01.jpg)](#ch4.xhtml_pch4ex547)![Image](img/618pro01.jpg)](#ch4.xhtml_pch4ex548)![Image](img/619pro01.jpg)](#ch4.xhtml_pch4ex549)![Image](img/620pro01.jpg)](#ch4.xhtml_pch4ex550)![Image](img/621pro01.jpg)](#ch4.xhtml_pch4ex551)![Image](img/622pro01.jpg)](#ch4.xhtml_pch4ex552)![Image](img/623pro01.jpg)](#ch4.xhtml_pch4ex553)![Image](img/624pro01.jpg)](#ch4.xhtml_pch4ex554)![Image](img/625pro01.jpg)](#ch4.xhtml_pch4ex555)![Image](img/626pro01.jpg)](#ch4.xhtml_pch4ex556)![Image](img/627pro01.jpg)](#ch4.xhtml_pch4ex557)![Image](img/628pro01.jpg)](#ch4.xhtml_pch4ex558)![Image](img/629pro01.jpg)](#ch4.xhtml_pch4ex559)![Image](img/630pro01.jpg)](#ch4.xhtml_pch4ex560)![Image](img/631pro01.jpg)](#ch4.xhtml_pch4ex561)![Image](img/632pro01.jpg)](#ch4.xhtml_pch4ex562)![Image](img/633pro01.jpg)](#ch4.xhtml_pch4ex563)![Image](img/634pro01.jpg)](#ch4.xhtml_pch4ex564)![Image](img/635pro01.jpg)](#ch4.xhtml_pch4ex565)![Image](img/636pro01.jpg)](#ch4.xhtml_pch4ex566)![Image](img/637pro01.jpg)](#ch4.xhtml_pch4ex567)![Image](img/638pro01.jpg)](#ch4.xhtml_pch4ex568)![Image](img/639pro01.jpg)](#ch4.xhtml_pch4ex569)![Image](img/640pro01.jpg)](#ch4.xhtml_pch4ex570)![Image](img/641pro01.jpg)](#ch4.xhtml_pch4ex571)![Image](img/642pro01.jpg)](#ch4.xhtml_pch4ex572)![Image](img/643pro01.jpg)](#ch4.xhtml_pch4ex573)![Image](img/644pro01.jpg)](#ch4.xhtml_pch4ex574)![Image](img/645pro01.jpg)](#ch4.xhtml_pch4ex575)![Image](img/646pro01.jpg)](#ch4.xhtml_pch4ex576)![Image](img/647pro01.jpg)](#ch4.xhtml_pch4ex577)![Image](img/648pro01.jpg)](#ch4.xhtml_pch4ex578)![Image](img/649pro01.jpg)](#ch4.xhtml_pch4ex579)![Image](img/650pro01.jpg)](#ch4.xhtml_pch4ex580)![Image](img/651pro01.jpg)](#ch4.xhtml_pch4ex581)![Image](img/652pro01.jpg)](#ch4.xhtml_pch4ex582)![Image](img/653pro01.jpg)](#ch4.xhtml_pch4ex583)![Image](img/654pro01.jpg)](#ch4.xhtml_pch4ex584)![Image](img/655pro01.jpg)](#ch4.xhtml_pch4ex585)![Image](img/656pro01.jpg)](#ch4.xhtml_pch4ex586)![Image](img/657pro01.jpg)](#ch4.xhtml_pch4ex587)![Image](img/658pro01.jpg)](#ch4.xhtml_pch4ex588)![Image](img/659pro01.jpg)](#ch4.xhtml_pch4ex589)![Image](img/660pro01.jpg)](#ch4.xhtml_pch4ex590)![Image](img/661pro01.jpg)](#ch4.xhtml_pch4ex591)![Image](img/662pro01.jpg)](#ch4.xhtml_pch4ex592)![Image](img/663pro01.jpg)](#ch4.xhtml_pch4ex593)![Image](img/664pro01.jpg)](#ch4.xhtml_pch4ex594)![Image](img/665pro01.jpg)](#ch4.xhtml_pch4ex595)![Image](img/666pro01.jpg)](#ch4.xhtml_pch4ex596)![Image](img/667pro01.jpg)](#ch4.xhtml_pch4ex597)![Image](img/668pro01.jpg)](#ch4.xhtml_pch4ex598)![Image](img/669pro01.jpg)](#ch4.xhtml_pch4ex599)![Image](img/670pro01.jpg)](#ch4.xhtml_pch4ex600)![Image](img/671pro01.jpg)](#ch4.xhtml_pch4ex601)![Image](img/672pro01.jpg)](#ch4.xhtml_pch4ex602)![Image](img/673pro01.jpg)](#ch4.xhtml_pch4ex603)![Image](img/674pro01.jpg)](#ch4.xhtml_pch4ex604)![Image](img/675pro01.jpg)](#ch4.xhtml_pch4ex605)![Image](img/676pro01.jpg)](#ch4.xhtml_pch4ex606)![Image](img/677pro01.jpg)](#ch4.xhtml_pch4ex607)![Image](img/678pro01.jpg)](#ch4.xhtml_pch4ex608)![Image](img/679pro01.jpg)](#ch4.xhtml_pch4ex609)![Image](img/680pro01.jpg)](#ch4.xhtml_pch4ex610)![Image](img/681pro01.jpg)](#ch4.xhtml_pch4ex611)![Image](img/682pro01.jpg)](#ch4.xhtml_pch4ex612)![Image](img/683pro01.jpg)](#ch4.xhtml_pch4ex613)![Image](img/684pro01.jpg)](#ch4.xhtml_pch4ex614)![Image](img/685pro01.jpg)](#ch4.xhtml_pch4ex615)![Image](img/686pro01.jpg)](#ch4.xhtml_pch4ex616)![Image](img/687pro01.jpg)](#ch4.xhtml_pch4ex617)![Image](img/688pro01.jpg)](#ch4.xhtml_pch4ex618)![Image](img/689pro01.jpg)](#ch4.xhtml_pch4ex619)![Image](img/690pro01.jpg)](#ch4.xhtml_pch4ex620)![Image](img/691pro01.jpg)](#ch4.xhtml_pch4ex621)![Image](img/692pro01.jpg)](#ch4.xhtml_pch4ex622)![Image](img/693pro01.jpg)](#ch4.xhtml_pch4ex623)![Image](img/694pro01.jpg)](#ch4.xhtml_pch4ex624)![Image](img/695pro01.jpg)](#ch4.xhtml_pch4ex625)![Image](img/696pro01.jpg)](#ch4.xhtml_pch4ex626)![Image](img/697pro01.jpg)](#ch4.xhtml_pch4ex627)![Image](img/698pro01.jpg)](#ch4.xhtml_pch4ex628)![Image](img/699pro01.jpg)](#ch4.xhtml_pch4ex629)![Image](img/700pro01.jpg)](#ch4.xhtml_pch4ex630)![Image](img/701pro01.jpg)](#ch4.xhtml_pch4ex631)![Image](img/702pro01.jpg)](#ch4.xhtml_pch4ex632)![Image](img/703pro01.jpg)](#ch4.xhtml_pch4ex633)![Image](img/704pro01.jpg)](#ch4.xhtml_pch4ex634)![Image](img/705pro01.jpg)](#ch4.xhtml_pch4ex635)![Image](img/706pro01.jpg)](#ch4.xhtml_pch4ex636)![Image](img/707pro01.jpg)](#ch4.xhtml_pch4ex637)![Image](img/708pro01.jpg)](#ch4.xhtml_pch4ex638)![Image](img/709pro01.jpg)](#ch4.xhtml_pch4ex639)![Image](img/710pro01.jpg)](#ch4.xhtml_pch4ex640)![Image](img/711pro01.jpg)](#ch4.xhtml_pch4ex641)![Image](img/712pro01.jpg)](#ch4.xhtml_pch4ex642)![Image](img/713pro01.jpg)](#ch4.xhtml_pch4ex643)![Image](img/714pro01.jpg)](#ch4.xhtml_pch4ex644)![Image](img/715pro01.jpg)](#ch4.xhtml_pch4ex645)![Image](img/716pro01.jpg)](#ch4.xhtml_pch4ex646)![Image](img/717pro01.jpg)](#ch4.xhtml_pch4ex647)![Image](img/718pro01.jpg)](#ch4.xhtml_pch4ex648)![Image](img/719pro01.jpg)](#ch4.xhtml_pch4ex649)![Image](img/720pro01.jpg)](#ch4.xhtml_pch4ex650)![Image](img/721pro01.jpg)](#ch4.xhtml_pch4ex651)![Image](img/722pro01.jpg)](#ch4.xhtml_pch4ex652)![Image](img/723pro01.jpg)](#ch4.xhtml_pch4ex653)![Image](img/724pro01.jpg)](#ch4.xhtml_pch4ex654)![Image](img/725pro01.jpg)](#ch4.xhtml_pch4ex655)![Image](img/726pro01.jpg)](#ch4.xhtml_pch4ex656)![Image](img/727pro01.jpg)](#ch4.xhtml_pch4ex657)![Image](img/728pro01.jpg)](#ch4.xhtml_pch4ex658)![Image](img/729pro01.jpg)](#ch4.xhtml_pch4ex659)![Image](img/730pro01.jpg)](#ch4.xhtml_pch4ex660)![Image](img/731pro01.jpg)](#ch4.xhtml_pch4ex661)![Image](img/732pro01.jpg)](#ch4.xhtml_pch4ex662)![Image](img/733pro01.jpg)](#ch4.xhtml_pch4ex663)![Image](img/734pro01.jpg)](#ch4.xhtml_pch4ex664)![Image](img/735pro01.jpg)](#ch4.xhtml_pch4ex665)![Image](img/736pro01.jpg)](#ch4.xhtml_pch4ex666)![Image](img/737pro01.jpg)](#ch4.xhtml_pch4ex667)![Image](img/738pro01.jpg)](#ch4.xhtml_pch4ex668)![Image](img/739pro01.jpg)](#ch4.xhtml_pch4ex669)![Image](img/740pro01.jpg)](#ch4.xhtml_pch4ex670)![Image](img/741pro01.jpg)](#ch4.xhtml_pch4ex671)![Image](img/742pro01.jpg)](#ch4.xhtml_pch4ex672)![Image](img/743pro01.jpg)](#ch4.xhtml_pch4ex673)![Image](img/744pro01.jpg)](#ch4.xhtml_pch4ex674)![Image](img/745pro01.jpg)](#ch4.xhtml_pch4ex675)![Image](img/746pro01.jpg)](#ch4.xhtml_pch4ex676)![Image](img/747pro01.jpg)](#ch4.xhtml_pch4ex677)![Image](img/748pro01.jpg)](#ch4.xhtml_pch4ex678)![Image](img/749pro01.jpg)](#ch4.xhtml_pch4ex679)![Image](img/750pro01.jpg)](#ch4.xhtml_pch4ex680)![Image](img/751pro01.jpg)](#ch4.xhtml_pch4ex681)![Image](img/752pro01.jpg)](#ch4.xhtml_pch4ex682)![Image](img/753pro01.jpg)](#ch4.xhtml_pch4ex683)![Image](img/754pro01.jpg)](#ch4.xhtml_pch4ex684)![Image](img/755pro01.jpg)](#ch4.xhtml_pch4ex685)![Image](img/756pro01.jpg)](#ch4.xhtml_pch4ex686)![Image](img/757pro01.jpg)](#ch4.xhtml_pch4ex687)![Image](img/758pro01.jpg)](#ch4.xhtml_pch4ex688)![Image](img/759pro01.jpg)](#ch4.xhtml_pch4ex689)![Image](img/760pro01.jpg)](#ch4.xhtml_pch4ex690)![Image](img/761pro01.jpg)](#ch4.xhtml_pch4ex691)![Image](img/762pro01.jpg)](#ch4.xhtml_pch4ex692)![Image](img/763pro01.jpg)](#ch4.xhtml_pch4ex693)![Image](img/764pro01.jpg)](#ch4.xhtml_pch4ex694)![Image](img/765pro01.jpg)](#ch4.xhtml_pch4ex695)![Image](img/766pro01.jpg)](#ch4.xhtml_pch4ex696)![Image](img/767pro01.jpg)](#ch4.xhtml_pch4ex697)![Image](img/768pro01.jpg)](#ch4.xhtml_pch4ex698)![Image](img/769pro01.jpg)](#ch4.xhtml_pch4ex699)![Image](img/770pro01.jpg)](#ch4.xhtml_pch4ex700)![Image](img/771pro01.jpg)](#ch4.xhtml_pch4ex701)![Image](img/772pro01.jpg)](#ch4.xhtml_pch4ex702)![Image](img/773pro01.jpg)](#ch4.xhtml_pch4ex703)![Image](img/774pro01.jpg)](#ch4.xhtml_pch4ex704)![Image](img/775pro01.jpg)](#ch4.xhtml_pch4ex705)![Image](img/776pro01.jpg)](#ch4.xhtml_pch4ex706)![Image](img/777pro01.jpg)](#ch4.xhtml_pch4ex707)![Image](img/778pro01.jpg)](#ch4.xhtml_pch4ex708)![Image](img/779pro01.jpg)](#ch4.xhtml_pch4ex709)![Image](img/780pro01.jpg)](#ch4.xhtml_pch4ex710)![Image](img/781pro01.jpg)](#ch4.xhtml_pch4ex711)![Image](img/782pro01.jpg)](#ch4.xhtml_pch4ex712)![Image](img/783pro01.jpg)](#ch4.xhtml_pch4ex713)![Image](img/784pro01.jpg)](#ch4.xhtml_pch4ex714)![Image](img/785pro01.jpg)](#ch4.xhtml_pch4ex715)![Image](img/786pro01.jpg)](#ch4.xhtml_pch4ex716)![Image](img/787pro01.jpg)](#ch4.xhtml_pch4ex717)![Image](img/788pro01.jpg)](#ch4.xhtml_pch4ex718)![Image](img/789pro01.jpg)](#ch4.xhtml_pch4ex719)![Image](img/790pro01.jpg)](#ch4.xhtml_pch4ex720)![Image](img/791pro01.jpg)](#ch4.xhtml_pch4ex721)![Image](img/792pro01.jpg)](#ch4.xhtml_pch4ex722)![Image](img/793pro01.jpg)](#ch4.xhtml_pch4ex723)![Image](img/794pro01.jpg)](#ch4.xhtml_pch4ex724)![Image](img/795pro01.jpg)](#ch4.xhtml_pch4ex725)![Image](img/796pro01.jpg)](#ch4.xhtml_pch4ex726)![Image](img/797pro01.jpg)](#ch4.xhtml_pch4ex727)![Image](img/798pro01.jpg)](#ch4.xhtml_pch4ex728)![Image](img/799pro01.jpg)](#ch4.xhtml_pch4ex729)![Image](img/800pro01.jpg)](#ch4.xhtml_pch4ex730)![Image](img/801pro01.jpg)](#ch4.xhtml_pch4ex731)![Image](img/802pro01.jpg)](#ch4.xhtml_pch4ex732)![Image](img/803pro01.jpg)](#ch4.xhtml_pch4ex733)![Image](img/804pro01.jpg)](#ch4.xhtml_pch4ex734)![Image](img/805pro01.jpg)](#ch4.xhtml_pch4ex735)![Image](img/806pro01.jpg)](#ch4.xhtml_pch4ex736)![Image](img/807pro01.jpg)](#ch4.xhtml_pch4ex737)![Image](img/808pro01.jpg)](#ch4.xhtml_pch4ex738)![Image](img/809pro01.jpg)](#ch4.xhtml_pch4ex739)![Image](img/810pro01.jpg)](#ch4.xhtml_pch4ex740)![Image](img/811pro01.jpg)](#ch4.xhtml_pch4ex741)![Image](img/812pro01.jpg)](#ch4.xhtml_pch4ex742)![Image](img/813pro01.jpg)](#ch4.xhtml_pch4ex743)![Image](img/814pro01.jpg)](#ch4.xhtml_pch4ex744)![Image](img/815pro01.jpg)](#ch4.xhtml_pch4ex745)![Image](img/816pro01.jpg)](#ch4.xhtml_pch4ex746)![Image](img/817pro01.jpg)](#ch4.xhtml_pch4ex747)![Image](img/818pro01.jpg)](#ch4.xhtml_pch4ex748)![Image](img/819pro01.jpg)](#ch4.xhtml_pch4ex749)![Image](img/820pro01.jpg)](#ch4.xhtml_pch4ex750)![Image](img/821pro01.jpg)](#ch4.xhtml_pch4ex751)![Image](img/822pro01.jpg)](#ch4.xhtml_pch4ex752)![Image](img/823pro01.jpg)](#ch4.xhtml_pch4ex753)![Image](img/824pro01.jpg)](#ch4.xhtml_pch4ex754)![Image](img/825pro01.jpg)](#ch4.xhtml_pch4ex755)![Image](img/826pro01.jpg)](#ch4.xhtml_pch4ex756)![Image](img/827pro01.jpg)](#ch4.xhtml_pch4ex757)![Image](img/828pro01.jpg)](#ch4.xhtml_pch4ex758)![Image](img/829pro01.jpg)](#ch4.xhtml_pch4ex759)![Image](img/830pro01.jpg)](#ch4.xhtml_pch4ex760)![Image](img/831pro01.jpg)](#ch4.xhtml_pch4ex761)![Image](img/832pro01.jpg)](#ch4.xhtml_pch4ex762)![Image](img/833pro01.jpg)](#ch4.xhtml_pch4ex763)![Image](img/834pro01.jpg)](#ch4.xhtml_pch4ex764)![Image](img/835pro01.jpg)](#ch4.xhtml_pch4ex765)![Image](img/836pro01.jpg)](#ch4.xhtml_pch4ex766)![Image](img/837pro01.jpg)](#ch4.xhtml_pch4ex767)![Image](img/838pro01.jpg)](#ch4.xhtml_pch4ex768)![Image](img/839pro01.jpg)](#ch4.xhtml_pch4ex769)![Image](img/840pro01.jpg)](#ch4.xhtml_pch4ex770)![Image](img/841pro01.jpg)](#ch4.xhtml_pch4ex771)![Image](img/842pro01.jpg)](#ch4.xhtml_pch4ex772)![Image](img/843pro01.jpg)](#ch4.xhtml_pch4ex773)![Image](img/844pro01.jpg)](#ch4.xhtml_pch4ex774)![Image](img/845pro01.jpg)](#ch4.xhtml_pch4ex775)![Image](img/846pro01.jpg)](#ch4.xhtml_pch4ex776)![Image](img/847pro01.jpg)](#ch4.xhtml_pch4ex777)![Image](img/848pro01.jpg)](#ch4.xhtml_pch4ex778)![Image](img/849pro01.jpg)](#ch4.xhtml_pch4ex779)![Image](img/850pro01.jpg)](#ch4.xhtml_pch4ex780)![Image](img/851pro01.jpg)](#ch4.xhtml_pch4ex781)![Image](img/852pro01.jpg)](#ch4.xhtml_pch4ex782)![Image](img/853pro01.jpg)](#ch4.xhtml_pch4ex783)![Image](img/854pro01.jpg)](#ch4.xhtml_pch4ex784)![Image](img/855pro01.jpg)](#ch4.xhtml_pch4ex785)![Image](img/856pro01.jpg)](#ch4.xhtml_pch4ex786)![Image](img/857pro01.jpg)](#ch4.xhtml_pch4ex787)![Image](img/858pro01.jpg)](#ch4.xhtml_pch4ex788)![Image](img/859pro01.jpg)](#ch4.xhtml_pch4ex789)![Image](img/860pro01.jpg)](#ch4.xhtml_pch4ex790)![Image](img/861pro01.jpg)](#ch4.xhtml_pch4ex791)![Image](img/862pro01.jpg)](#ch4.xhtml_pch4ex792)![Image](img/863pro01.jpg)](#ch4.xhtml_pch4ex793)![Image](img/864pro01.jpg)](#ch4.xhtml_pch4ex794)![Image](img/865pro01.jpg)](#ch4.xhtml_pch4ex795)![Image](img/866pro01.jpg)](#ch4.xhtml_pch4ex796)![Image](img/867pro01.jpg)](#ch4.xhtml_pch4ex797)![Image](img/868pro01.jpg)](#ch4.xhtml_pch4ex798)![Image](img/869pro01.jpg)](#ch4.xhtml_pch4ex799)![Image](img/870pro01.jpg)](#ch4.xhtml_pch4ex800)![Image](img/871pro01.jpg)](#ch4.xhtml_pch4ex801)![Image](img/872pro01.jpg)](#ch4.xhtml_pch4ex802)![Image](img/873pro01.jpg)](#ch4.xhtml_pch4ex803)![Image](img/874pro01.jpg)](#ch4.xhtml_pch4ex804)![Image](img/875pro01.jpg)](#ch4.xhtml_pch4ex805)![Image](img/876pro01.jpg)](#ch4.xhtml_pch4ex806)![Image](img/877pro01.jpg)](#ch4.xhtml_pch4ex807)![Image](img/878pro01.jpg)](#ch4.xhtml_pch4ex808)![Image](img/879pro01.jpg)](#ch4.xhtml_pch4ex809)![Image](img/880pro01.jpg)](#ch4.xhtml_pch4ex810)![Image](img/881pro01.jpg)](#ch4.xhtml_pch4ex811)![Image](img/882pro01.jpg)](#ch4.xhtml_pch4ex812)![Image](img/883pro01.jpg)](#ch4.xhtml_pch4ex813)![Image](img/884pro01.jpg)](#ch4.xhtml_pch4ex814)![Image](img/885pro01.jpg)](#ch4.xhtml_pch4ex815)![Image](img/886pro01.jpg)](#ch4.xhtml_pch4ex816)![Image](img/887pro01.jpg)](#ch4.xhtml_pch4ex817)![Image](img/888pro01.jpg)](#ch4.xhtml_pch4ex818)![Image](img/889pro01.jpg)](#ch4.xhtml_pch4ex819)![Image](img/890pro01.jpg)](#ch4.xhtml_pch4ex820)![Image](img/891pro01.jpg)](#ch4.xhtml_pch4ex821)![Image](img/892pro01.jpg)](#ch4.xhtml_pch4ex822)![Image](img/893pro01.jpg)](#ch4.xhtml_pch4ex823)![Image](img/894pro01.jpg)](#ch4.xhtml_pch4ex824)![Image](img/895pro01.jpg)](#ch4.xhtml_pch4ex825)![Image](img/896pro01.jpg)](#ch4.xhtml_pch4ex826)![Image](img/897pro01.jpg)](#ch4.xhtml_pch4ex827)![Image](img/898pro01.jpg)](#ch4.xhtml_pch4ex828)![Image](img/899pro01.jpg)](#ch4.xhtml_pch4ex829)![Image](img/900pro01.jpg)](#ch4.xhtml_pch4ex830)![Image](img/901pro01.jpg)](#ch4.xhtml_pch4ex831)![Image](img/902pro01.jpg)](#ch4.xhtml_pch4ex832)![Image](img/903pro01.jpg)](#ch4.xhtml_pch4ex833)![Image](img/904pro01.jpg)](#ch4.xhtml_pch4ex834)![Image](img/905pro01.jpg)](#ch4.xhtml_pch4ex835)![Image](img/906pro01.jpg)](#ch4.xhtml_pch4ex836)![Image](img/907pro01.jpg)](#ch4.xhtml_pch4ex837)![Image](img/908pro01.jpg)](#ch4.xhtml_pch4ex838)![Image](img/909pro01.jpg)](#ch4.xhtml_pch4ex839)![Image](img/910pro01.jpg)](#ch4.xhtml_pch4ex840)![Image](img/911pro01.jpg)](#ch4.xhtml_pch4ex841)![Image](img/912pro01.jpg)](#ch4.xhtml_pch4ex842)![Image](img/913pro01.jpg)](#ch4.xhtml_pch4ex843)![Image](img/914pro01.jpg)](#ch4.xhtml_pch4ex844)![Image](img/915pro01.jpg)](#ch4.xhtml_pch4ex845)![Image](img/916pro01.jpg)](#ch4.xhtml_pch4ex846)![Image](img/917pro01.jpg)](#ch4.xhtml_pch4ex847)![Image](img/918pro01.jpg)](#ch4.xhtml_pch4ex848)![Image](img/919pro01.jpg)](#ch4.xhtml_pch4ex849)![Image](img/920pro01.jpg)](#ch4.xhtml_pch4ex850)![Image](img/921pro01.jpg)](#ch4.xhtml_pch4ex851)![Image](img/922pro01.jpg)](#ch4.xhtml_pch4ex852)![Image](img/923pro01.jpg)](#ch4.xhtml_pch4ex853)![Image](img/924pro01.jpg)](#ch4.xhtml_pch4ex854)![Image](img/925pro01.jpg)](#ch4.xhtml_pch4ex855)![Image](img/926pro01.jpg)](#ch4.xhtml_pch4ex856)![Image](img/927pro01.jpg)](#ch4.xhtml_pch4ex857)![Image](img/928pro01.jpg)](#ch4.xhtml_pch4ex858)![Image](img/929pro01.jpg)](#ch4.xhtml_pch4ex859)![Image](img/930pro01.jpg)](#ch4.xhtml_pch4ex860)![Image](img/931pro01.jpg)](#ch4.xhtml_pch4ex861)![Image](img/932pro01.jpg)](#ch4.xhtml_pch4ex862)![Image](img/933pro01.jpg)](#ch4.xhtml_pch4ex863)![Image](img/934pro01.jpg)](#ch4.xhtml_pch4ex864)![Image](img/935pro01.jpg)](#ch4.xhtml_pch4ex865)![Image](img/936pro01.jpg)](#ch4.xhtml_pch4ex866)![Image](img/937pro01.jpg)](#ch4.xhtml_pch4ex867)![Image](img/938pro01.jpg)](#ch4.xhtml_pch4ex868)![Image](img/939pro01.jpg)](#ch4.xhtml_pch4ex869)![Image](img/940pro01.jpg)](#ch4.xhtml_pch4ex870)![Image](img/941pro01.jpg)](#ch4.xhtml_pch4ex871)![Image](img/942pro01.jpg)](#ch4.xhtml_pch4ex872)![Image](img/943pro01.jpg)](#ch4.xhtml_pch4ex873)![Image](img/944pro01.jpg)](#ch4.xhtml_pch4ex874)![Image](img/945pro01.jpg)](#ch4.xhtml_pch4ex875)![Image](img/946pro01.jpg)](#ch4.xhtml_pch4ex876)![Image](img/947pro01.jpg)](#ch4.xhtml_pch4ex877)![Image](img/948pro01.jpg)](#ch4.xhtml_pch4ex878)![Image](img/949pro01.jpg)](#ch4.xhtml_pch4ex879)![Image](img/950pro01.jpg)](#ch4.xhtml_pch4ex880)![Image](img/951pro01.jpg)](#ch4.xhtml_pch4ex881)![Image](img/952pro01.jpg)](#ch4.xhtml_pch4ex882)![Image](img/953pro01.jpg)](#ch4.xhtml_pch4ex883)![Image](img/954pro01.jpg)](#ch4.xhtml_pch4ex884)![Image](img/955pro01.jpg)](#ch4.xhtml_pch4ex885)![Image](img/956pro01.jpg)](#ch4.xhtml_pch4ex886)![Image](img/957pro01.jpg)](#ch4.xhtml_pch4ex887)![Image](img/958pro01.jpg)](#ch4.xhtml_pch4ex888)![Image](img/959pro01.jpg)](#ch4.xhtml_pch4ex889)![Image](img/960pro01.jpg)](#ch4.xhtml_pch4ex890)![Image](img/961pro01.jpg)](#ch4.xhtml_pch4ex891)![Image](img/962pro01.jpg)](#ch4.xhtml_pch4ex892)![Image](img/963pro01.jpg)](#ch4.xhtml_pch4ex893)![Image](img/964pro01.jpg)](#ch4.xhtml_pch4ex894)![Image](img/965pro01.jpg)](#ch4.xhtml_pch4ex895)![Image](img/966pro01.jpg)](#ch4.xhtml_pch4ex896)![Image](img/967pro01.jpg)](#ch4.xhtml_pch4ex897)![Image](img/968pro01.jpg)](#ch4.xhtml_pch4ex898)![Image](img/969pro01.jpg)](#ch4.xhtml_pch4ex899)![Image](img/970pro01.jpg)](#ch4.xhtml_pch4ex900)![Image](img/971pro01.jpg)](#ch4.xhtml_pch4ex901)![Image](img/972pro01.jpg)](#ch4.xhtml_pch4ex902)![Image](img/973pro01.jpg)](#ch4.xhtml_pch4ex903)![Image](img/974pro01.jpg)](#ch4.xhtml_pch4ex904)![Image](img/975pro01.jpg)](#ch4.xhtml_pch4ex905)![Image](img/976pro01.jpg)](#ch4.xhtml_pch4ex906)![Image](img/977pro01.jpg)](#ch4.xhtml_pch4ex907)![Image](img/978pro01.jpg)](#ch4.xhtml_pch4ex908)![Image](img/979pro01.jpg)](#ch4.xhtml_pch4ex909)![Image](img/980pro01.jpg)](#ch4.xhtml_pch4ex910)![Image](img/981pro01.jpg)](#ch4.xhtml_pch4ex911)![Image](img/982pro01.jpg)](#ch4.xhtml_pch4ex912)![Image](img/983pro01.jpg)](#ch4.xhtml_pch4ex913)![Image](img/984pro01.jpg)](#ch4.xhtml_pch4ex914)![Image](img/985pro01.jpg)](#ch4.xhtml_pch4ex915)![Image](img/986pro01.jpg)](#ch4.xhtml_pch4ex916)![Image](img/987pro01.jpg)](#ch4.xhtml_pch4ex917)![Image](img/988pro01.jpg)](#ch4.xhtml_pch4ex918)![Image](img/989pro01.jpg)](#ch4.xhtml_pch4ex919)![Image](img/990pro01.jpg)](#ch4.xhtml_pch4ex920)![Image](img/991pro01.jpg)](#ch4.xhtml_pch4ex921)![Image](img/992pro01.jpg)](#ch4.xhtml_pch4ex922)![Image](img/993pro01.jpg)](#ch4.xhtml_pch4ex923)![Image](img/994pro01.jpg)](#ch4.xhtml_pch4ex924)![Image](img/995pro01.jpg)](#ch4.xhtml_pch4ex925)![Image](img/996pro01.jpg)](#ch4.xhtml_pch4ex926)![Image](img/997pro01.jpg)](#ch4.xhtml_pch4ex927)![Image](img/998pro01.jpg)](#ch4.xhtml_pch4ex928)![Image](img/999pro01.jpg)](#ch4.xhtml_pch4ex929)![Image](img/1000pro01.jpg)
