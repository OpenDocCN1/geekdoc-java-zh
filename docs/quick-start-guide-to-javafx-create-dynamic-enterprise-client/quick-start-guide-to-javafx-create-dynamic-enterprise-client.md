
# JavaFX 快速启动指南：创建动态企业级客户端应用程序

![](img/f5bc6249660e63bd0b6a2dc95983edb7_0_0.png)

# 关于作者

J.F. DiMarzio 是一位资深开发者。他从 1984 年开始在 TRS-80 Color Computer II 上使用 BASIC 语言进行开发。以来，DiMarzio 曾在美国国防部和华特迪士尼公司等企业的部门工作。他继续努力突破技术边界，并在新的、新兴的平台上进行开发。

DiMarzio 还是一个高产的成功作家。在过去的 12 年里，他出版了 11 本书，其中包括第一版《JavaFX: A Beginner's Guide》。他的书籍已被翻译成四种语言并在全球出版。DiMarzio 的写作风格非常易于阅读和理解，这使得他所介绍的主题信息更易于记忆。

# 关于技术编辑

Simon Ritter 是甲骨文公司（Oracle Corporation）Java 技术布道团队的经理。Simon 自 1984 年起进入 IT 行业，拥有英国布鲁内大学（Brunel University）物理学学士学位。

Simon 最初在 AT&T UNIX System Labs 后的 Novell 从事 UNIX 开发工作，随后于 1996 年加入太阳公司（Sun）。期间，他开始接触 Java 技术，并从事了 Java 开发和咨询工作。在作为太阳公司收购的一部分转入甲骨文后，他现在专注于用于客户端应用程序的 Java 平台以及嵌入式 Java。他还继续开发突破 Java 应用边界的演示程序，例如手势界面、嵌入式机器人控制器和车载系统。可以在 Twitter 上关注 Simon (@speakjava)，并访问他的博客 blogs.oracle.com/speakjava。

| Brandi Shainer | Simon Ritter | Jean Bodeaux |
|---|---|---|
| Ted Law | | |
| 采购协调员 | | |
| Amanda Russell | | |

# 引言

## 为什么选择这本书？

欢迎阅读《JavaFX 快速上手指南》。本书旨在为你进入 JavaFX 8 开发这一令人兴奋的新领域提供最佳起步阶段。JavaFX 是一个功能丰富的环境工具，对于任何想要为不同背景的用户创建沉浸式、交互式环境的人来说，学习 JavaFX 是必不可少的。

如果你熟悉 JavaFX 的之前的版本，那么这本书是你的必备。随着 Java 8 的发布，该平台发生了重大变化。《JavaFX 快速上手指南》涵盖了 JavaFX 的变化，并为你在这个不可或缺的平台上应对现实世界的开发情况做好准备。

本书将以逻辑的方式带你了解 JavaFX 8。它从解释 JavaFX 背后的技术开始。你将迅速进入安装 JavaFX 开发环境和工具的阶段。虽然 JavaFX 有多种开发环境可用，但本书的重点是教你 NetBeans 的基础知识。NetBeans 提供了一个功能丰富且易于学习的产品，能够让你迅速上手 JavaFX 开发。在读完这本书后，你将熟练地学习更复杂的示例，以测试你日益增长的开发丰富 JavaFX 应用的知识。

某些章节还包含“尝试一下”部分，以帮助你练习所学内容。“尝试一下”部分的结构类似于教科书，你将获得需要独立完成的任务。此外，每个章节都有一个“自测”部分，提供问答式问题来进一步增强你的学习体验。充分利用章节问题和“尝试一下”练习，将让你有机会精炼新习得的技能并创建你自己的应用程序。

虽然这本书不是高级程序员的参考书，但你应该具备某些技能才能从《JavaFX 快速上手指南》中获益。鉴于 JavaFX 现在已集成在 Java 中，其中最重要的技能是 Java 编程基础。对 Java 类和基本类型的了解将帮助你更容易地理解书中的某些概念。

对书中任何材料的任何意见、问题或建议，可以直接发送给作者：jfddimarzio@jfdimarzio.com。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_18_0.png)

# 第 1 章 JavaFX 简介

## 核心技能与概念

- 安装 JavaFX
- 安装 NetBeans
- 使用 NetBeans

欢迎阅读《JavaFX 快速上手指南》。我相信你已经迫不及待开启 JavaFX 开发这一精彩世界的旅程，而这里是完美的开始地点。在开始之前，你需要一个功能完善的开发环境。本章涵盖了创建和建立 JavaFX 开发环境所需的基础知识，使你能够创建内容丰富的交互式应用程序。它还回答了你可能对 JavaFX 的作用以及它是如何实现的许多问题。

## 什么是 JavaFX？

如果你曾经玩过 Adobe Flash 游戏，或者见过 Microsoft Silverlight 应用程序，你对与 JavaFX 类似的产品已经有很好的认识了。我知道，将 JavaFX 与这些其他环境比较是不公平的，但如果你以前没见过 JavaFX，我必须找些东西来做比较。现在 JavaFX 已经处于第三次激动人心的迭代中，你可能在某个地方遇到过它。

JavaFX 以类似于 Flash 或 Silverlight 的方式向用户提供全功能的交互式体验。然而，JavaFX 与其他平台的区别之一是 JavaFX 是平台独立的。由于 JavaFX 现在已与 Java 运行时完全集成，任何 Java 可以提供 JavaFX 体验的设备或系统都可以支持。

> **注意**
>
> 在 JavaFX 第 1、2 以及现在的 3 版本之间，平台发生了许多变化。如果你对旧版本的 JavaFX 有一些经验，甚至可能对本书的第一版有了解，你应该密切关注，因为你以前使用的很多内容现在已经大不相同。此外，JavaFX 的第三个版本现在正式称为 JavaFX 8，因为现在它是 Java 8 的一部分了。

## JavaFX 开发需要什么？

在投入开发之前，你应该检查本节列出的需求列表。将它们视为获得成功且富有成效的学习过程的先决条件。你至少应该具备以下技能的基础知识，并能够访问列出的软件。

### 必要的技能与知识

跟随本书学习不需要预先的开发经验。即使你只创建过一个应用程序或开发过一个基础网页，你仍然拥有学习 JavaFX 的技能。书中的示例和课程是专门为教你 JavaFX 开发而设计的。

尽管如此，你在 Java 开发方面的任何经验都将帮助你更快地掌握 JavaFX 的概念。虽然对运行概念的基本了解并非必不可少，但它将帮助你更快地进入状态：

- **Java 开发** JavaFX 和 Java 之间共享不仅仅是根名称。如果你曾经写过 Java Applet——更重要的是，曾将 Java Applet 部署到网页上——你就能轻松理解 JavaFX 的部署过程。之前的 JavaFX 版本使用一种名为 JavaFX Script 的专用语言。为了获得更统一、跨平台的 Java 体验，这种语言已经发生了更改。`JavaFX Script` 语言被 Java API 取代，以促进更统一和简化的编程体验。

- **层级样式表 (CSS)** JavaFX 应用的外观和感觉可以使用层级样式表或 CSS 进行修改。像 HTML 这样的开发平台可以使用 CSS 作为美化外观的一种。

- **NetBeans** 虽然 JavaFX 可以在任何集成开发环境 (IDE) 甚至是简单的文本编辑器中开发，但本书推荐的开发方法是 NetBeans。如果你以前从未用过 NetBeans——本书将引导你完成一切。

这些技能并非必须，缺乏这些领域的知识也不会影响你学习 Java。

### 必要的软件

本节作为你将在书中一直使用的软件的简要介绍。JavaFX 使用了一些不同的软件元素，到本章结束时你将对它们非常熟悉。如果你还没有任何这些软件元素或者没听说过其中一两个，不要担心。在本章结束时，你将下载并安装所有用于辅助 JavaFX 开发的软件。

- `JavaFX SDK` `JavaFX SDK`（软件开发包）是 JavaFX 开发的主要包。
- `Java SE JDK` `Java SE JDK`（标准版 Java 开发包）用于将你的 JavaFX 代码编译为执行代码。
- `NetBeans` `NetBeans` 是你创建 Java 应用的开发环境。将 `NetBeans` 视为一个特殊的文本编辑器，可以使用 `JavaFX SDK` 和 `Java SE JDK` 将其编译为应用程序。

这里列出的软件都是免费的并可以轻松下载。本章的后续将引导你下载并安装所需的软件。

### 必要的硬件

本节概述了运行 JavaFX 的某些硬件需求。请记住，JavaFX 以及一般的 Java 运行在各种硬件和配置上。然而，为了充分利用 JavaFX，有一些硬件建议。

通常情况下，JavaFX 会运行在任何支持的系统的硬件上。为了享受新硬件加速管道的性能，你需要遵循这些建议。

| 显卡 | GPU |
|---|---|
| NVIDIA | 移动 GPU：GeForce 8M 和 100M 系列或更高、NVS 2100M 系列或更高以及 Mobility Quadro FX 300M 系列或更高；桌面 GPU：GeForce 8 和 100 系列或更高；工作站 GPU：Quadro FX 300 系列或更高 |
| ATI | 移动 GPU：Mobility Radeon HD 3000、4000 和 50000；桌面 GPU：Radeon HD 2400、3000、4000、5000 和 6000 系列 |
| Intel | 移动 GPU：GMA 4500MHD 和 GMA HD；桌面 GPU：GMA 4500 和 GMA HD |

## 下载并安装所需软件

最简单的方法是下载并安装最新版本的 NetBeans。在本书编写时，最新版本是 NetBeans 7.1.2。此版本可以与最新版本的 Java（以及 JavaFX）捆绑下载。这提供了一种通过一次操作安装所有所需软件的便捷方法。

### NetBeans

`NetBeans` 是一个开源集成开发环境（IDE），可用于许多不同平台上的开发。`NetBeans` 可用于 C/C++、Java、JavaScript 和 PHP 开发，以及 JavaFX 开发。在遵循本书中的示例时，你将在 `NetBeans` 工作空间内完成所有的 JavaFX 开发。

第一步是下载适用于 JavaFX 的最新版 NetBeans 版本。你可以从 `www.netbeans.org` 或从 JavaFX 下载页面提供的包中下载最新版本的 `NetBeans`。

> **注意**
>
> 在本书编写时，最新版本的 NetBeans 是适用于 JavaFX 的 NetBeans 7.1.2 Beta 版。`NetBeans` 可以下载不同语言的版本，但根据本书的需要，你需要下载专门为 JavaFX 设计的 NetBeans 7.1.2 版本。当你访问 NetBeans 下载页面时，这一点会非常容易理解。

一旦进入 NetBeans 下载页面，可选包的列表可能会让你感到无从。不要担心，因为你只需要关注一种版本的 NetBeans 7.1.2。你需要下载的是适用于 JavaFX 的 NetBeans IDE（见图 1-1）。

> **注意**
>
> 来自 NetBeans 标记为“All”（全部）的下载项是适用于所有可用技术的 NetBeans 版本。如果你恰好下载了这个版本，本书中的所有示例仍然可以运行，但你应该尽量坚持适用于 JavaFX 的 NetBeans IDE。

只需按照安装向导操作，你就应该能够顺利地准备好 NetBeans 开发环境。安装向导会推荐 `NetBeans IDE` 和 `Java JDK` 的默认安装位置；只需接受这些位置，剩余的安装过程将迎刃而解。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_23_0.png)

> **注意**
>
> 如果你的电脑从未安装过 Java，你可能需要在安装 NetBeans 之前手动安装最新的 JDK。

`NetBeans` 安装完成后，`NetBeans IDE` 将自动启动。如果 `NetBeans` 没有重新启动，你可能需要手动启动它。`NetBeans IDE` 将打开到开发启动页（见图 1-2）。`NetBeans` 启动页旨在为你提供关于在 `NetBeans` 和 JavaFX 中开发的提示和新闻。

此时，`NetBeans` 已经配置完毕并准备可以使用。`NetBeans` 安装程序会要求你注册 `NetBeans`。这一步是建议性的而非强制性的。注册产品将让你获得升级新闻和 `NetBeans` 论坛的信息。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_24_0.png)

图 1-2 NetBeans 默认启动页

## 专家问答

**问：** 开发 JavaFX 必须使用 NetBeans 吗？

**答：** 不，JavaFX 可以在 NetBeans 之外开发。编写 JavaFX 真正需要的 `Java JDK` 和 `JavaFX SDK`。然而，在 NetBeans 之外开发需要具备相当良好的 Java 命令行编译知识。

**问：** 可以使用其他 IDE 进行 JavaFX 开发吗？

**答：** 可以，你也可以使用 Eclipse。Eclipse 是另一个开源 IDE，它需要使用插件才能与 JavaFX 工作。不过，在本书编写时，JavaFX 2（及以上版本）还没有适用于 Eclipse 的插件。

## 配置你的 NetBeans

开发者应该熟练使用自己的 IDE。尝试自定义你的 `NetBeans IDE` 的外观和感受，让它成为你工作时更舒适的地方。当你的 IDE 拥有熟悉的界面和感受时，你更有可能进行创造性的开发。

打开你的 `NetBeans IDE`，从菜单栏选择 `Tools | Options`。探索为你提供的选项。通过设置不同的选项并留意它们对 IDE 的影响来尝试这些选项。找到最适合你和你开发方法的舒适选项。

## 第 1 章自测

1. 你在本书中使用的开源开发环境名称是什么？
2. 正确或错误？你应该下载适用于所有开发者（All Developers）版本的 NetBeans。
3. 正确或错误？如果需要（如果你已安装 JRE），系统将自动为你安装 Java JDK。
4. 安装过程中，哪些 NetBeans 设置可以接受默认值？
5. JavaFX SDK 和 Java JDK 之间的区别是什么？
6. NetBeans 启动页的目的是什么？
7. 正确或错误？在使用之前你必须成功注册 NetBeans。
8. 在哪个网站可以找到 NetBeans？
9. 写出两个功能与 JavaFX 极其相似的其他应用程序。
10. 正确或错误？JavaFX 是用 JavaFX Script 开发的。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_26_0.png)

# 第 2 章 场景设置

## 技能与概念

- 在 NetBeans 中创建 JavaFX 项目
- 什么是 Stage（舞台）？
- 什么是 Scene（场景）？
- 运行应用程序

在本章中，你将学习如何在 NetBeans 中设置 JavaFX 项目。本章将逐步引导你完成创建项目、了解 Stage 和 Scene 以及运行应用程序。

## 创建新的 JavaFX 项目

> **注意**
>
> 如果你尚未打开，请打开 NetBeans。你正在创建一个 JavaFX 项目。

打开你的 `NetBeans IDE` 后，点击 `File | New Project`（或按下 `CTRL+SHIFT+N`），如图 2-1 所示。

选择 New Project 将打开新项目向导。注意 New Project 包含多个类别。你需要选择 JavaFX 类别和 JavaFX 项目类型。

向导的下一步是 Name and Location（名称和位置）步骤。`NetBeans` 正在为你的项目寻找名称。将你的项目命名为 `JavaFXBeginners`。这是一个很好的描述性名称，便于识别。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_28_0.png)

图 2-1 创建新项目

![](img/f5bc6249660e63bd0b6a2dc95983edb7_28_1.png)

图 2-2 新项目选择窗口

![](img/f5bc6249660e63bd0b6a2dc95983edb7_29_0.png)

图 2-3 名称和位置步骤

你应该接受此向导中的剩余默认值。`NetBeans` 将自动选择默认版本的 JavaFX 以及创建主项目设置所需的选项。

点击 Finish 按钮创建你的空项目。在后续章节中，你将为项目添加包和文件。

## (不完全) 空的 JavaFX 项目

一旦创建了项目，新项目向导会将你返回 `NetBeans IDE`，因为屏幕左侧是项目资源框架。你的 `JavaFXBeginners` 项目将在此框架中。

点击 `JavaFXBeginners` 文件夹旁边的加号。这将展开 Source Packages（源包）文件夹。`Source Packages` 文件夹将包含项目的包。

Java 包是所有相关的类（在本例中为 JavaFX 源文件）完整集合。包中的所有文件将被编译成一个 JAR（Java 归档）文件，并在其他项目中被引用。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_29_1.png)

图 2-4 带有新项目的 NetBeans IDE

例如，如果你正在构建一组用于计算形状面积的 Java 类，你可以将它们构建到一个特定的“面积计算器”包中。这个命名空间以及其中所有的类都可以被编译成一个 JAR 文件。然后，你只需要包含该 JAR 文件并引用该命名空间，就可以在任何需要计算面积的项目中使用该 JAR 文件。

在 JavaFX 中，你需要遵循包的命名规范。包使用层级域名结构命名，该结构代表了你作为开发者。就像反向网址一样，命名空间名称应该以顶级域名开始，然后是相关的域名。对于本项目，我们将使用以下：

`javafxforbeginners`

> **提示**
>
> 按照惯例，所有的 Java 命名空间和项目名称都应该是小写。有关 Java 命名规范的更多信息，请访问 `http://java.sun.com/docs/codeconv/html/CodeConventions.doc`。



如果你检查 JavaFXForBeginners 项目的源包（Source Packages）文件夹，你会发现为你的源文件有一个名为 `javafxforbeginners` 的包。NetBeans 在项目创建过程中创建了这个包，并在包中放置了三个示例文件。可以通过展开项目资源器中的包视图来查看这些文件。让我们检查 NetBeans 放置在你的 JavaFX 包中的示例文件。

## 检查项目文件

在查看了新创建的项目和包（以及项目中的三个文件）后，你可能想从哪里开始输入代码。例如，如果你在写一个文档或备忘录，你可能会将其输入到文本文件（txt 或 .docx）中。如果你在 Microsoft Office 中创建电子表格，你会将其输入到 Excel 文件（xlsx）中。要创建一个 JavaFX FXML 应用程序，你需要将代码添加到 JavaFX 文件（java）或 FXML 标记文件（fxml）中。

## 注意

在 JavaFX 的早期版本中，你本会将 JavaFX Script 写到 .fx 文件中。JavaFX 现在有自己的 Java SDK，代码被写在 Java .java 文件中。因此，在本书书中，当你的代码文件被称为 Java 文件而不是 JavaFX 文件时，这并不是错误；你确实是在用 Java 编写你的 JavaFX。

查看 `javafxbeginners` 包；你会很快发现 NetBeans 为你提供了两个 .java 文件和一个 .fxml 文件。双击 `JavaForBeginners.java` 文件在 NetBeans 编辑器中打开它。该文件看起来应该类似于图 2-5所示。

## 注意

你的屏幕可能与图 2-5 略有不同。

你的 Java 文件将在 NetBeans IDE 的主面板中打开。在接下来的章节中，你将对此文件中的代码以及 NetBeans IDE 进行快速浏览，并将你编译你的第一个 JavaFX FXML 应用程序。

## 在 NetBeans 中探索项目

你现在应该已经在 NetBeans IDE 中打开了 JavaFX FXML 项目的框架，并已经为你生成了一些示例文件。你的 NetBeans JavaFX FXML 项目看起来应该像图 2-5 所示。你可能认为一个空项目不会那么有趣，在很大情况下你是的。然而，在开始编码之前，你应该熟悉 IDE 的一些功能和区域。

# 第 2 章：设置场景

15

![](img/f5bc6249660e63bd0b6a2dc95983edb7_32_0.png)

图 2-5 JavaFXForBeginners.java 文件

在 JavaFX 的大部分开发工作中，你将集中在 NetBeans IDE 的两个区域。NetBeans IDE 的左侧显示了三个标签页，标记为 Projects（项目）、Files（文件）和 Services（服务）。图 2-6 所示的这组资源管理器将是你导航项目的主要机制。

项目从很小开始并最终使用许多文件（从代码到图像和配置）并不罕见。资源管理器可以帮助跟踪这些文件。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_32_1.png)

图 2-6 项目、文件和服务资源管理器

## 第 2 章：搭建场景

用于创建单行注释。请注意，单行注释以 `//` 开头而不是 `/*`。此外，由于它们只占一行，因此不需要关闭。因此，该行上的任何内容都将被视为注释。

在下一节中，你将学习包（package）语句。

## package 语句

在起始注释之后是下面这一行：

```
package javafxforbeginners;
```

这一行虽然对你的代码有直接影响，但它可以教你一些关于 Java 编程的关键点。这行的行的核心目的是告诉编译器，此行下的所有代码都属于 `javafxforbeginners` 包。包声明必须位于 Java 文件的顶部。

这行代码有三个你应该注意的组成部分。行的第一个单词 `package` 是 Java 关键字。关键字是对于 Java 编译器具有预定义含义的特殊命令。它们也被称为“保留字”。因此，你不能在代码的其他地方将它们用作变量名或其他预定义用途之外的任何东西。`package` 关键字告诉编译器，关键字后的任何内容都是包名。

你的包名紧随 `package` 关键字之后（在本例中为 `javafxforbeginners`）。因为关键字的目的是告诉编译器其后的所有内容都是包名，所以编译器需要知道文件名何时该结束。否则，根据定义，编译器会认为文件中的所有代码都是包名。因此，Java 专门留了一个特殊字符作为语句终止符：分号（`;`）。语句终止符告诉编译器它何时到达了特定行代码的末尾。尽管该规则有非常具体的例外，但你仍然需要使用带有分号的代码语句来让编译器知道你已完成。如果你在应该使用分号的地方没有使用，这是在预料之中的，当你尝试编译时，编译器会给出一个错误。

## 提示

编译是将你的代码从人类可读的文本转换为包含字节码的类文件的过程，这些字节码可以由 Java 虚拟机执行。

在本章的最后部分，你将检查 `JavaFXForBeginners.java` 文件中的功能代码。

## 你的第一个舞台

所有的 JavaFX 应用程序都构建在 Stage（舞台）上。将这个容器命名为 `Stage` 非常合适。将 `Stage` 视为你应用程序中其他对象的字体。就像戏剧表演一样，动作发生在舞台上——JavaFX 也不例外。你所有的动作都将在 `Stage` 上发生。

## 应用程序入口点

包语句之后是一组导入（import）语句。这些导入语句用于帮助编译器解析对方法的引用，而无需完全限定路径。也就是说，如果不使用 `import` 语句，你必须写出外部方法的完整路径。这可能让你的代码非常冗长并且可能难以管理。

```
import javafx.application.Application;
import javafx.fxml.FXMLoader;
import javafx.scene.Parent;
import javafx.scene.Scene;
import javafx.scene.Stage;
```

在导入语句之后，你将看到文件的代码。代码以 `JavaFXBeginners` 类的类声明开始。

```
public class JavaFXBeginners extends Application {
    public static void main(String[] args) {
        Application.launch(JavaFXBeginners.class, args);
    }

    @Override
    public void start(Stage stage) throws Exception {
        Parent root = FXMLoader.load(getClass().getResource("Sample.fxml"));

        stage.setScene(new Scene(root));
        stage.show();
    }
}
```

`JavaFXBeginners` 类继承自 `Application`。这意味着 `JavaFXBeginners` 类继承了 `Application` 类所有的公共、受保护和包作用范围的变量和方法。了解这一点很重要，因为你的主应用程序类必须继承 `Application` 才能正确运行。

在 `JavaFXBeginners` 类中，你将看到两个方法：`main` 方法和 `start()` 方法。`main()` 方法在你的应用程序启动时执行。在 `main()` 方法内部有一个对 `launch()` 的调用。这里有一个有趣的实是

## 第 2 章：搭建场景

在最新版本的 Java FX 中，`main()` 不再是必须的。包含它只是为了向后兼容。`main()` 方法是应用程序的入口点，或者说是 Java 虚拟机开始执行的点。在这种情况下，`JavaFXBeginners` 类被传递为 JavaFX 应用程序的起点。为什么不自动启动 JavaFX 应用程序呢？这种分离允许你从同一个 `main()` 运行其他 Java 方法或触发其他 JavaFX 应用程序。

`launch()` 方法现在会查看 `JavaFXForBeginners` 类，确保它继承 `Application`，然后尝试调用 `JavaFXForBeginners` 从 `Application` 继承的 `start()` 方法。你的 JavaFX 应用程序必须重写 `start()` 方法来执行任何你想运行的代码。

在 NetBeans 提供的示例代码中，你可以看到 `start()` 方法加载了一个名为 `Sample.fxml` 的文件，将 `Scene` 设置在 `Stage` 上，并将 `Stage` 显示给世界。这就是你的类中启动一个基础 JavaFX 应用程序所需的所有代码。

让我们看看 `Sample.fxml` 文件中包含什么，看看这个文件在应用程序中的作用。

## Sample.fxml 文件

由 NetBeans 在创建 JavaFX FXML 应用程序期间创建 `Sample.fxml` 包含以下内容：

```xml
<?xml version="1.0" encoding="UTF-8"?>

<?import java.lang.*?>
<?import javafx.scene.*?>
<?import javafx.scene.layout?>

<AnchorPane height="200" width="320" fx:controller="javafxforbeginners.Sample" xmlns:fx="http://javafx.com/fxml">
  <children>
    <Button fx:id="button" onAction="#handleButtonAction" layoutX="126" layoutY="90" text="Click Me!" />
    <Label fx:id="label" layoutX="120" layoutY="20" text="Hello, World!" />
  </children>
</AnchorPane>
```

FXML 是一种基于 XML 的用户界面（UI）标记语言。FXML 是创建简单、快速且灵活的 JavaFX UI 的语言。如果你有 XML 或任何标记语言的经验，FXML 看起来会非常熟悉并且容易上手。

## JavaFX 快速入门

在该文件中有两个需要注意的地方。第一个是控制器赋值：

```
fx:controller="javafxforbeginners.Sample"
```

这一行告诉 JavaFX 一个名为 `Sample` 的类是 `javafxforbeginners` 包的一部分，该包包含了 FXML 中所有元素代码。快速查看项目管理器，你会发现你确实有一个名为 `Sample.java` 的文件。

# 第 2 章：设置场景... 23

![](img/f5bc6249660e63bd0b6a2dc95983edb7_40_0.png)

**图 2-8** 你的第一个 JavaFX 应用程序

## 编译你的 JavaFX 程序

要编译并运行你的 JavaFX 程序，请按 F6 键。你也可以点击 NetBeans 栏上的绿色大箭头。这两种方法中的任何一种都会将你的脚本编译为可执行应用程序。

你的代码将根据选定的运行配置（Run Configuration）进行编译和运行，结果将单独窗口显示。

## 注意

目前，你只有一个运行配置：<default>。随着学习深入，你将创建其他配置。

在这种情况下，你的第一个 JavaFX 程序将创建一个带有单个按钮的非常有趣的窗口。点击该按钮将产生图 2-8 所示的消息。

在下一章中，你将创建你自己的“Hello World”应用程序。

## 第 2 章自测

- 1. 列出所有项目的框架名称是什么？
- 2. 用于创建新 JavaFX 项目的向导名称是什么？
- 3. 命名空间（namespace）的另一种称法是什么？
- 4. NetBeans IDE 的哪个面板允许你在代码示例之间导航？
- 5. 真或假？调面板（Palette）面板包含预定义的复用代码片段。
- 6. JavaFX 代码文件分配了什么扩展名？
- 7. Java 语言中，“package” 是什么种类型的单词？
- 8. FXML 是基于哪种标记语言？
- 9. 注释的开始和结束字符是什么？
- 10. 真或假？使用 FXML 时不能使用代码后台文件（code-behind file）。

## 第 3 章

Hello World

## 核心技能与概念

- 学习什么是 MVC
- 使用 JavaFX Scene Builder
- 值的绑定

在本章中，你将开始在你的 JavaFX 程序中编写代码。从这里开始，前两章所有的准备工作将开始产生回报。你在前两章学习基础知识时投入的所有时间和精力，都将帮助你掌握本章介绍的 Java、JavaFX 和 FXML。

学习新语言最棒的部分是能够以一种新颖且令人兴奋的方式表达你的想法和愿景。这正是你在这章中要做的。你将学习如何启动你可能（或可能）知道如何在其他语言中做的事情，并在 JavaFX 中赋予它们生命。但在之前，我们需要讨论一些关键概念。

## 什么是 MVC？

从 2 版本开始，JavaFX 一直遵循模型-视图-控制器（MVC）设计模式，该模式旨在将应用程序的用户界面（UI）与业务逻辑分离。这允许用户界面独立于控制它们的逻辑进行设计和构建。MVC 并不是 JavaFX 或 FXML 所独有的。这种设计模式已经存在多年，并用于几乎所有的主要的框架。然而，如果你不熟悉它，不要担心，在学习本书中的示例时，你将学到大部分所需的的知识。

当你使用 FXML 时，.fxml 文件代表 MVC 中的“视图（view）”。这意味着 FXML 文件是 UI 所表述的数据或逻辑的物理视图。你可以在不需要了解相关 Java 文件底层数据的情况下，在 FXML 文件中设计和创建用户界面。在本章中，当你接触到一个名为 JavaFX Scene Builder 的新工具时，将更深入地了解这一点。

与 .fxml 文件紧密耦合的 java 文件是 MVC 模式中的“控制器（controller）”。控制器从业务逻辑中获取数据和信息并传递给视图。在 NetBeans 为你创建的默认 Hello World 程序中，`Sample.java` 文件是 `Sample.fxml` 视图的控制器。

最后，你项目中任何包含在视图中显示的逻辑或数据的支持 Java 文件都是 MVC 模式中的“模型（models）”。模型可以分布在项目中的任意数量文件中，只要它们都包含相同的命名空间中。

在本章的下一节中，你将学习如何使用 JavaFX Scene Builder 来设计和创建 MVC 模式中引用的 FXML 视图。

## 使用 JavaFX Scene Builder

Oracle 提供了一个工具，用于图形化地设计和开发你的 JavaFX 程序的 UI。JavaFX Scene Builder 设计用于直接与你的 FXML 文件配合，并允许你添加、删除和操作 FXML 中的元素。在本节中，你将使用 JavaFX Scene Builder 修改 `Sample.fxml` 文件并创建一个新的 Hello World 应用程序。

## 注意

在 http://www.oracle.com/technetwork/java/javafx/overview/index.html 下载 JavaFX Scene Builder。

下载并安装 JavaFX Scene Builder 后，使用它打开 JavaFXForBeginners 项目中的 `Sample.fxml` 文件。你应该能看到类似于图 3-1 所示的屏幕。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_44.png)

图 3-1 Sample.fxml 在设计器中

## JavaFX 快速上手

记得 NetBeans 为你创建的那个 Hello World 应用程序吗？该应用程序有一个文本为“Click Me!”的按钮。你在 Scene Builder 中清晰地看到它。

## 使用容器

Scene Builder 的左侧有两个视图：库（Library）和层次级（Hierarchy）。Scene Builder 展示了这些视图。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_45.png)

图 3-2 库和层次级

你现在关注的视图是层次级视图，它显示了 FXML 文件中的所有元素。查看 `Sample.fxml`，你应该看到一个 `AnchorPane`。点击层次级视图中的这些元素将高亮设计器中相应的元素。设计器如图 3-3 所示。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_46.png)

图 3-3 检查器视图

## 使用控件

检查器视图包含高亮元素的可分配属性。在检查器视图中，你可以设置、查看和修改任何属性。这使得 JavaFX Scene Builder 在设计和创建 JavaFX 应用程序时成为宝贵的工具。

为了在本章中创建 Hello World 应用程序，你需要一个空白画布。因此，在层次级视图中点击按钮元素和标签元素并选择删除。这将从 `Sample.fxml` 中删除这些元素。

在删除元素时，可能会收到如图 3-4 所示的错误。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_47.png)

图 3-4 警告

如果你收到此错误，点击删除按钮并继续。此错误只是告诉你你正在删除的元素与代码有关。我们将在本节的后续部分处理代码。然而，如果我们不处理代码，应用程序将无法正确编译或运行。



现在你要在 `Sample.fxml` 中添加一个新的 `GridPane` 元素。网格提供了一种整齐组织页面元素的良好方法。点击库视图中的 2x3 项目并将其拖到设计器中。当你与 `AnchorPane` 的中心对齐时，将看到水平和垂直对齐线，如图 3-5 所示。当 `GridPane` 与 `AnchorPane` 的中心对齐时放下它。在 `GridPane` 锚定到你的 FXML 后，是时候添加一些控件了。

你将添加到 `GridPane` 的第一个控件是 `Label`。点击库中的 `Label` 控件并拖到 `GridPane` 的右下单元格中。一旦标签锚定到你的网格中，选择它使其属性在检查器视图中可见。在继续之前，你需要设置一些属性。

目前，`Label` 控件的 `Text` 属性设置为“Label”。这意味着当控件渲染时，除非更改文本，否则 `Label` 将显示“Label”。让我们通过删除 `Text` 属性中的文本来更改它。接下来，在检查器视图底部有一个折叠面板，标记为 `Layout`。点击 `Layout` 旁边的箭头展开它。

# 第3章：你好世界

![](img/f5bc6249660e63bd0b6a2dc95983edb7_48_0.png)

图 3-5 居中 GridPane

当 `Layout` 窗格展开后，你需要设置 `GridPane` 约束。理想情况下，你希望 `Label` 能够扩展以适应显示的文本，并保持在所放置的 `GridPane` 单元格内居中。要做到这一点，请将 `Hgrow` 和 `Vgrow` 属性设置为 `ALWAYS`，并将 `Halignment` 和 `Valignment` 属性设置为 `CENTER`。如图 3-6 所示。

| GridPane 约束 (GridPane Constraints) | |
|---|---|
| 行索引 (Row Index) | 2 [ ] |
| 列索引 (Column Index) | 1 [ ] |
| 行跨度 (Row Span) | | |
| 列跨度 (Column Span) | | |
| Hgrow | ALWAYS [ ] |
| Vgrow | ALWAYS [ ] |
| 垂直对齐 (Valignment) | CENTER [ ] |
| 水平对齐 (Halignment) | CENTER [ ] |
| 边距 (Margin) | TOP LEFT RIGHT BOTTOM FILL |

图 3-6 GridPane 约束

在 `Label` 旁边，在右上角的单元格添加一个 `TextField`。你现在唯一想要编辑的 `TextField` 属性是 `Size`。就像你对 `Label` 做的那样，删除 `TextField` 属性中的文本。保存你对 `Sample.fxml` 文件所做的更改。如果它尚未打开，请打开 NetBeans 你的 `JavaFXForBeginners` 项目。你会发现 `Sample.fxml` 的代码现在反映了你在 Java Scene Builder 中做的更改。`Sample.fxml` 文件的代码如下：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<?import java.lang.*?>
<?import javafx.scene.*?>
<?import javafx.scene.control.*?>
<?import javafx.scene.layout.*?>
<AnchorPane id="AnchorPane" prefHeight="200.0" prefWidth="320.0"
xmlns:fx="http://javafx.com/fxml" controller="javafxforbeginners.Sample">
<children>
<GridPane layoutX="60.0" layoutY="55.0">
<children>
<GridPane.columnIndex="1" alignment="CENTER">
GridPane.hgrow="ALWAYS" GridPane.rowIndex="2" GridPane.alignment="CENTER"
GridPane.vgrow="ALWAYS" />
<TextField prefWidth="200.0" GridPane.columnIndex="1"
GridPane.rowIndex="0" />
</children>
<constraints>
<Constraints hgrow="SOMETIMES" minWidth="10.0" maxWidth="100.0" />
<Constraints hgrow="SOMETIMES" minWidth="10.0" prefWidth="100.0" maxWidth="100.0" />
<Constraints minHeight="10.0" prefHeight="30.0" vgrow="SOMETIMES" />
<Constraints minHeight="10.0" prefHeight="30.0" vgrow="SOMETIMES" />
<Constraints minHeight="10.0" prefHeight="30.0" vgrow="SOMETIMES" />
</constraints>
</GridPane>
</children>
</AnchorPane>
```

现在可以自由编译并运行你的项目了。即使控制器中存在有的示例代码，它仍然可以编译和运行。当你的 JavaFX 启动时，你应该看到一个可以输入文本的 `TextField`。在下一节中，你将学习在将此 `TextField` 转换为世界时如何使用绑定（binding）。

## 创建你的你好世界应用程序

人类表达最常见的形式是使用单词。通过句子向他人传达思想的主要方法每天都被各种信息视图所冲击。无论你想在 JavaFX 中创建什么种类型的应用程序或丰富环境，传达观点的最佳方式都是使用单词。在屏幕上编写文本是开发中一项常见的日常任务。

## 使用 JavaFX 绑定

绑定允许你以这种方式链接属性和值，使得当值发生变化时，属性会动态更新。你不需要编写代码来监听属性的变化、响应该变化、将值写入另一个属性并重绘应用程序，你只需要将属性绑定到值，剩下的交给处理即可。你将把 `Sample.fxml` 文件中 `Label` 的 `text` 属性绑定到 `TextField` 的值。通过绑定这些控件，在 `TextField` 中输入的任何内容都将动态显示在 `Label` 中。让我们来看看这种绑定是如何实现的。绑定中所使用的语法如下：

```
${control.value}
```

$（美元符号）运算符在绑定中用于变量解析。$ 运算符告诉 JavaFX 随后的任何内容都应被视为变量。要解析控制器的属性值，你必须将控制器名称和属性封装在括号中：

```
${...}
```

## 注意

显然，在某些情况下你想要使用 $ 但并不意味着让它解析为变量，例如当你想要编写金额时。在这些情况下，你需要在美元符号（$）之前放置转义字符（\）来转义默认功能。查看你在 NetBeans 中 `Sample.fxml` 文件中当前的控制器代码：

```xml
<children>
<Label GridPane.columnIndex="1" alignment="CENTER"
GridPane.hgrow="ALWAYS" GridPane.rowIndex="2" GridPane.alignment="CENTER"
GridPane.vgrow="ALWAYS" text="" />
<TextField prefWidth="200.0" GridPane.columnIndex="1"
GridPane.rowIndex="0" />
</children>
```

## JavaFX 绑定的快速上手

在某些情况下你需要给 `TextField` 分配一个 ID。没有 ID，JavaFX 无法理解你想要绑定的什么。添加：

```xml
<children>
<Label GridPane.columnIndex="1" alignment="CENTER"
GridPane.hgrow="ALWAYS" GridPane.rowIndex="2" GridPane.alignment="CENTER"
GridPane.vgrow="ALWAYS" text="" />
<TextField prefWidth="200.0" GridPane.columnIndex="1"
GridPane.rowIndex="0" />
</children>
```

# 第3章：你好世界

35

![](img/f5bc6249660e63bd0b6a2dc95983edb7_52_0.png)

图 3-7 绑定的你好世界应用程序

## 方法与属性简介

在绑定到控制器的值之前，你需要理解两个 Java 概念：方法和属性。这两个概念的结合允许你将值从控制器绑定到视图上的 `Label`。在示例中，当你从控制器绑定到视图时，你将绑定到控制器上的一个方法。该方法反过来将引用控制器上的一个属性，产生发送到视图的值。这听起来可能复杂，但并没有那么糟糕。下一节包含关于方法的快速介绍。

### Java 方法

Java 方法是语句的序列，可以通过引用方法名来调用。当方法执行完毕时，它会将值返回给调用它的代码。从方法返回的值可以是特定数据类型（如 `String`），也可以是空。所有方法都有一个所谓的“签名”。签名使得方法在声明它的方法的类中是唯一的。签名由方法名、传递给方法的参数类型和数量以及其返回类型组成。这种复杂的“签名”允许你在同一个类中拥有多个同相同但参数不同的方法。

声明方法的语法如下：

```
<modifier>return type<method name>(<parameters>
{
  body
}
```

修饰符可以是 `public`、`private`、`protected` 或包范围（不声明修饰符）。修饰符决定了对方法设置的执行安全性。简单来说，`public` 修饰符表示方法可以从定义所在的类外部执行，而 `private` 修饰符则将方法的执行限制在同一个类的代码中。为了方便起见，你在本书书中只需要处理这两种修饰符。

返回类型是方法执行完毕后返回的值的数据类型。如前所述，这可以是任何有效的数据类型，例如 `String` 或 `int`。但是，如果你的方法不返回任何值，该怎么办呢？在某些情况下，你可能希望方法执行某些计算并向你返回计算结果。在其他情况下，你可以创建一个处理某些代码但实际上不需要返回任何内容的方法。在这种情况下，你使用返回类型 `void` 来告诉 Java 你的方法不返回值。

方法名是在代码的其他区域调用你的方法时使用的名称。方法名可以是任何内容，但请尽量遵循一些标准指南。根据编码标准，方法名应该是动词或动作词，例如 "get"、"run"、"lock" 甚至 "delete"。如果你的方法名包含多个单词，第一个单词应该小写，后续单词的首字母应该大写，如 `getMyValue`。

## 注意

返回类型、方法名和参数共同组成了方法的**签名（signature）**。了解这一点很重要，因为你不能拥有两个（相互可见）具有相同签名的方法。

在方法名之后是一对括号，括号可以是空的（意味着运行该方法不需要任何参数），也可以包含一组参数。如果定义了参数，则在调用方法时必须提供这些参数的值。

最后，在参数之后是方法的体（body）。方法体是执行方法中所有工作的代码块。

一个简单的方法声明可能如下：

```
public String getMessage()
{
    String message = "FOO";
    return message;
}
```

在下一节中，你将学习属性，然后将属性与方法结合起来创建一个新的绑定。

### JavaFX 属性

属性（Property）是一个键值对，允许你存储和召回一段数据。将属性视为存储值的方式，稍后可以对这些值进行操作和检索。虽然这绝对是一个更高级的话题，但它可能帮助你了解在 Java 中属性是存储在哈希表中的。你可以想象一个键（key）被用于从表中存储和检索特定的值——这就是基本的属性。

当你定义一个属性时，通常需要定义一个 getter（获取方法）和一个 setter（设置方法）。getter 为你检索属性的值，而 setter 则负责设置和修改它。创建属性所需的代码初看起来看起来可能有点令人生畏，但如果你花几时间查看一下，所有的部分都将变得清晰易懂。

接下来，我们将构建一个带有 getter 和 setter 的属性，然后构建一个方法来调用它们。

## 构建你的属性和方法

让我们构建一个默认值为 "Hello World" 的属性。首先，打开你在 NetBeans 中创建的 `Sample.java` 文件。找到以下代码行并将它们从文件中删除（它们对于我们正要做的操作是非必需的）：

```
import javafx.event.ActionEvent;
import javafx.fxml.FXML;
import javafx.scene.control.Label;
...
@FXML
private Label label;

@FXML
private void handleButtonClickAction(ActionEvent event) {
    System.out.println("You clicked me!");
    label.setText("Hello");
}
```

移除这些项目后，你的文件应该像这样：

```java
package javafxforbeginners;

import java.net.URL;
import java.util.ResourceBundle;
import javafx.fxml.Initializable;

public class Sample implements Initializable {

    @Override
    public void initialize(URL url, ResourceBundle rb) {}
```

// TODO

```
}
```

现在，让我们创建我们的属性。你将创建一个包含字符串值 "Hello World" 的属性。

首先，你需要向文件中添加一些新的导入（import）。导入以下行以便访问创建 `StringProperty` 的代码：

```
import javafx.beans.property.SimpleStringProperty;
```



# 第 3 章：Hello World

这就是创建参数所需的全部内容。你完成的 `Sample.java` 应该如下：

```java
package javafxforbeginners;

import java.net.URL;
import java.util.ResourceBundle;
import javafx.beans.SimpleStringProperty;
import javafx.beans.StringProperty;
import javafx.fxml.Initializable;

public class Sample implements Initializable {

    private StringProperty helloMessage =
        new SimpleStringProperty("Hello World");

    public String getHelloMessage() {
        return helloMessage.get();
    }

    public void setHelloMessage(String newString) {
        helloMessage.set(newString);
    }

    @Override
    public void initialize(URL url, ResourceBundle rb) {
        // TODO
    }
}
```

是时候绑定到属性了。当 `Sample.java` 中的代码完成后，切换回 `Sample.fxml` 来实现 Label 的绑定。

## 绑定 helloMessage 属性

当 `Sample.java` 中的代码完成后，切换回 `Sample.fxml` 来实现 Label 的绑定。绑定属性的语法如下：

```
${helloMessage}
```

该语句表示从定义的控制器中获取 `helloMessage` 属性。在这种情况下，查看 `AnchorPane` 的控制器属性，你可以看到 `Sample` 类被定义为视图的控制器：

```
fx:controller="javafxforbeginners.Sample"
```

## 注意

控制器属性指向的是类，而不是文件。`Sample` 类恰好位于名为 `Sample.java` 的文件中，但并不一定必须如此。

修改你的 Label，使 `text` 属性指向新的绑定：

```xml
<Label GridPane.columnIndex="1" GridPane.halignment="CENTER"
    GPane.hgrow="ALWAYS" GridPane.rowIndex="2" GridPane.
    valignment="CENTER"
    GPane.vgrow="ALWAYS" text="${controller.helloMessage}" />
```

编译并运行你的应用程序。你应该能在 Label 上看到打印出的 "Hello World"。

在下一章，你将学习 JavaFX 布局。

## 第 3 章自测

1. MVC 模式的目的是什么？
2. MVC 代表什么？
3. 在 JavaFX 中，FXML 代表 MVC 的哪部分？
4. 使用什么工具编辑 FXML 文件？
5. 什么是 JavaFX 绑定？
6. 错误？绑定语法是 `#{value}`。
7. `$` 运算符在 JavaFX 中被称为什么？
8. JavaFX 中的方法是什么？
9. JavaFX 中的属性是什么？
10. 错误？要绑定到控制器的属性，你必须告诉 FXML 你的属性是什么。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_58_0.png)

# 第 4 章：使用 JavaFX 布局

## 核心技能与概念

- 在 Scene 中排列节点
- 使用 `HBox`
- 嵌套布局

在整本书中，你已经学习了如何创建和使用节点。从本质上，如果没有将这些节点放置在屏幕上的能力，JavaFX 将变得非常不好。为了让任何用户界面（UI）变得直观且易用，必须在逻辑上将节点放置在屏幕上。

到本书的这里，你已经手动在 Scene 的上下文中放置了节点。然后，使用目标位置的 x 和 y 坐标，你移动了节点并将它们置于逻辑位置。然而，在屏幕上手动移动节点是一项枯燥的任务，最终会消耗开发功能所需的时间。

JavaFX 提供了许多实用的工具来帮助你组织节点在屏幕上的布局。布局可以将你的节点自动组织成预定义的模式，从而为你的应用程序提供专业的外观和更高的可用性。

在本章中，你将学习如何使用布局来组织各种节点。你学习第一个布局是 `HBox`。

在开始之前，创建一个名为 Chapter4 的新空 JavaFX 应用程序。.java 文件应该如下所示：

```java
package Chapter4;

import javafx.application.Application;
import javafx.stage.Stage;

/**
 *
 * @author J F DiMartio
 */
public class Chapter4 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.show();
    }
}
```

## HBox

`HBox` 是一种水平布局，你可以用它在屏幕上放置相对位置的节点。也就是说，`HBox` 布局将你的节点水平地排列在一起。为了演示这一点，让我们创建一个包含 `Text` 和 `Button` 元素的 Scene，如下所示：

```java
Text text = new Text();
Button btn = new Button();
text.setText("Sample Text");
btn.setText("Button");
```

你的完整文件应该如下所示：

```java
package Chapter4;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.scene.text.Text;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter4 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Text text = new Text();
        Button btn = new Button();
        text.setText("Sample Text");
        btn.setText("Button");

        StackPane root = new StackPane();
        root.getChildren().add(btn);
        root.getChildren().add(text);

        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

注意，代码在场景图中使用 `StackPane` 作为根节点。`StackPane` 组织其子节点，使其在视觉上“堆叠”在一起。这是通过更改每个子节点的 z 序来实现的，栈中“较低”的节点具有较低的 z 序。

编译并运行此程序。你可以看到，如果你修改了节点的布局，它们将简单地杂乱在一起，如图 4-1 所示。

这些节点的布局非常不协调，不利于形成非常实用的设计。让我们使用 `HBox` 布局来组织屏幕上的这些节点。`HBox` 属于 `javafx.scene.layout` 包。在将 `HBox` 添加到你的 Scene 之前，你必须导入此类：

```java
import javafx.scene.layout.HBox;
```

![](img/f5bc6249660e63bd0b6a2dc95983edb7_61_0.png)

图 4-1 没有布局的节点

在导入正确的包后，将 `HBox` 添加到你的 Scene：

```java
HBox root = new HBox();
```

添加所有你想让 `HBox` 持有的节点，就像你对 `StackPane` 做的那样。`HBox` 将在其内容内水平地放置所有节点。

```java
public void start(Stage primaryStage) {
    Text text = new Text();
    Button btn = new Button();
    text.setText("Sample Text");
    btn.setText("Button");

    HBox root = new HBox();
    root.getChildren().add(btn);
    root.getChildren().add(text);

    primaryStage.setScene(new Scene(root, 300, 250));
    primaryStage.show();
}
```

注意，你仍然没有设置 `Text` 和 `Button` 的 x 和 y 坐标位置。在正常情况下，这会导致节点堆叠在一起。然而，`HBox` 会为你处理放置工作，并将节点整齐地排列在一起。你的 .java 文件的完整代码应该如下：

```java
package Chapter4;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.HBox;
import javafx.scene.text.Text;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter4 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Text text = new Text();
        Button btn = new Button();
        text.setText("Sample Text");
        btn.setText("Button");

        HBox root = new HBox();
        root.getChildren().add(btn);
        root.getChildren().add(text);

        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```



# 第 4 章：使用 JavaFX 布局

## HBox

`HBox` 是一种水平布局，你可以用它在屏幕上放置相对位置的节点。也就是说，`HBox` 布局将你的节点水平地排列在一起。为了演示这一点，让我们创建一个包含 `Text` 和 `Button` 元素的 `Scene`，如下所示：

```java
Text text = new Text();
Button btn = new Button();
text.setText("Sample Text");
btn.setText("Button");
```

你的完整文件应该如下所示：

```java
package Chapter4;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.scene.text.Text;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter4 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Text text = new Text();
        Button btn = new Button();
        text.setText("Sample Text");
        btn.setText("Button");
        StackPane root = new StackPane();
        root.getChildren().add(btn);
        root.getChildren().add(text);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

注意，代码在场景图中使用 `StackPane` 作为根节点。`StackPane` 组织其子节点，使其在视觉上“堆叠”在一起。这是通过更改每个子节点的 z 序来实现的，栈中“较低”的节点具有较低的 z 序。

编译并运行此程序。你可以看到，如果你修改了节点的布局，它们将简单地杂乱在一起，如图 4-1 所示。

![图 4-1 没有布局的节点](img/f5bc6249660e63bd0b6a2dc95983edb7_61_0.png)

这些节点的布局非常不协调，不利于形成非常实用的设计。让我们使用 `HBox` 布局来组织屏幕上的这些节点。`HBox` 属于 `javafx.scene.layout` 包。在将 `HBox` 添加到你的 `Scene` 之前，你必须导入此类：

```java
import javafx.scene.layout.HBox;
```

在导入正确的包后，将 `HBox` 添加到你的 `Scene`：

```java
HBox root = new HBox();
```

添加所有你想让 `HBox` 持有的节点，就像你对 `StackPane` 做的那样。`HBox` 将在其内容内水平地放置所有节点。

```java
public void start(Stage primaryStage) {
    Text text = new Text();
    Button btn = new Button();
    text.setText("Sample Text");
    btn.setText("Button");
    HBox root = new HBox();
    root.getChildren().add(btn);
    root.getChildren().add(text);
    primaryStage.setScene(new Scene(root, 300, 250));
    primaryStage.show();
}
```

注意，你仍然没有设置 `Text` 和 `Button` 的 x 和 y 坐标位置。在正常情况下，这会导致节点堆叠在一起。然而，`HBox` 会为你处理放置工作，并将节点整齐地排列在一起。你的 `.java` 文件的完整代码应该如下所示：

```java
package Chapter4;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.HBox;
import javafx.scene.text.Text;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter4 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Text text = new Text();
        Button btn = new Button();
        text.setText("Sample Text");
        btn.setText("Button");
        HBox root = new HBox();
        root.getChildren().add(btn);
        root.getChildren().add(text);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

## VBox

`VBox` 是一种垂直布局，你可以用它在屏幕上放置相对位置的节点。也就是说，`VBox` 布局将你的节点垂直地排列在一起。

## 嵌套布局

布局最灵活的方面之一是它们可以嵌套。也就是说，你可以将布局放置在内部。你可以通过组合两个或更多现有布局来创建非常实用的 UI。

例如，假设你想创建一个 `Scene`，其中水平排列着一个 `Text` 节点和一个紧随其后的 `Button` 节点。在这些节点的正下方，你希望再放置一个 `Text` 节点，后面跟着另一个 `Button` 节点。这可以通过在 `VBox` 中嵌套两个 `HBox` 元素轻松实现。

`VBox` 垂直方向组织节点。在这种情况下，你希望垂直方向上排列两个“组”节点。你将在 `VBox` 内部创建两个 `HBox` 元素，用以代表堆叠在一起的两个水平节点分组。困惑吗？别担心，在看到代码后，你会变得得更加清晰。首先，按照如下方式创建你的 `VBox` 实例：

```java
VBox root = new VBox();
```

现在，创建两个独立的 `HBox` 实例，并将它们作为子节点添加到你的 `VBox` 中：

```java
HBox row1 = new HBox();
HBox row2 = new HBox();

root.getChildren().add(row1);
root.getChildren().add(row2);
```

这些 `HBox` 实例为你提供了一个放置想要堆叠节点的地方。让我们在每个 `HBox` 中放入一个 `Text` 和一个 `Button`：

```java
Text text1 = new Text();
Button btn1 = new Button();
Text text2 = new Text();
Button btn2 = new Button();

text1.setText("Sample Text 1");
btn1.setText("Button 1");
text2.setText("Sample Text 2");
btn2.setText("Button 2");

row1.getChildren().add(text1);
row1.getChildren().add(btn1);
row2.getChildren().add(text2);
row2.getChildren().add(btn2);

root.getChildren().add(row1);
root.getChildren().add(row2);
```

将两个不同的布局嵌套在一起就是你需要的全部了。这个过程并不限于两个布局。多个布局可以相互嵌套，以产生更多样化的节点布局。此示例的完成 `.java` 文件产生了两个 `Text` 和两个 `Button` 元素的列式效果。这里是完整代码：

```java
package Chapter4;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.HBox;
import javafx.scene.layout.VBox;
import javafx.scene.text.Text;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter4 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Text text1 = new Text();
        Button btn1 = new Button();
        Text text2 = new Text();
        Button btn2 = new Button();
        text1.setText("Sample Text 1");
        btn1.setText("Button 1");
        text2.setText("Sample Text 2");
        btn2.setText("Button 2");
        VBox root = new VBox();
        HBox row1 = new HBox();
        HBox row2 = new HBox();
        row1.getChildren().add(text1);
        row1.getChildren().add(btn1);
        row2.getChildren().add(text2);
        row2.getChildren().add(btn2);
        root.getChildren().add(row1);
        root.getChildren().add(row2);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

![图 4-4 嵌套布局](img/f5bc6249660e63bd0b6a2dc95983edb7_68_0.png)

编译并运行此程序。你将看到图 4-4 所示的布局。
现在你可以尝试其他布局了。尝试嵌套这些布局以产生原创且吸引人的自定义布局。

## 使用其他布局尝试

使用本章提供的示例，创建一个使用 `FlowPane`、`GridPane` 或 `TilePane` 布局显示三张图片的 JavaFX 程序。注意每个布局是如何改变图像显示方式的。

在下一章中，你将在屏幕上绘制形状。

## 第 4 章自测

1. 哪种布局在 Scene 中水平方向组织你的节点？
2. 正确或错误？`HBox` 位于 `javafx.scene` 包中。
3. 哪个属性保存了供布局组织的节点？
4. 正确或错误？你必须确保设置放置在布局中的每个节点的 x 坐标和 y 坐标。
5. 效果可以应用于布局吗？
6. 哪种布局在 Scene 中垂直方向组织节点？
7. 组合以产生新布局的布局称为什么？
8. 正确或错误？为了嵌套布局，一个必须继承自另一个。
9. 正确或错误？只有两个布局可以嵌套。
10. 列出 `VBox` 之外的三种布局。

![图片](img/f5bc6249660e63bd0b6a2dc95983edb7_70.png)

# 第 5 章：创建形状

## 关键技能与概念

- 在屏幕上绘制线条
- 使用上下文（context）
- 创建形状

> **注意**
> 如果你对游戏开发感兴趣，多边形是非常重要的。

## JavaFX 场景图

场景图是一个包含节点的树状容器。场景图中有三种类型的节点。场景图的基础节点——持有所有节点的节点——是根节点。根节点没有父节点并可以包含子节点。还有分支节点和叶子节点。分支节点可以包含其他类型的节点。而叶子节点不能包含任何节点。

## JavaFX 快速上手指南

在继续本章节之前，请确保你的 `Chapter5.java` 文件中的代码如下：

```java
package Chapter5;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter5 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        StackPane root = new StackPane();
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

## 线

线是形状最基本的形式。几乎你能想象到的、绘制或创建的任何形状由一条或多条线组成。从作为直线集合的正方形和三角形，到作为曲线集合的圆和椭圆，理解线条绘制的基础知识至关重要。鉴于你将绘制几乎所有其他形状都基于线，因此从本章开始学习线条是非常合逻辑的。

什么是线？这看起来像是一个基础问题。从上学时代起，我们一直在用铅笔、蜡笔笔和标记笔在纸上画线。你可以利用用蜡笔笔在纸上画线的经验来理解 JavaFX 中的“线”是什么。

当你在纸上画一条线时，你将蜡笔笔放在一点，拖动到另一个点，然后抬起蜡笔笔。你画的线与你使用的蜡笔笔一样粗。线的颜色也与蜡笔相同。同样的逻辑也适用于在 JavaFX 中画线。

在 JavaFX 中画线时，你必须告诉编译器线的起点和终点。你需要指定的数值是起始 X、起始 Y 以及结束 X 和 结束 Y。编译器将能够获取这些信息并在屏幕上的这两个点之间画一条线。

> **注意**
> 起点和终点使用笛卡尔坐标系表示。

你必须首先在代码中指定一个 `import` 语句。你需要的 `import` 语句引用了绘制线条的代码。线条所在的包是编译器理解你的代码意图并相应绘制线条所需的。

在你的 `Chapter5.java` 文件的顶部，现有的 `import` 语句下方包含以下语句：

```java
import javafx.scene.shape.Line;
```

接下来，在 `start()` 方法中，如下所示实例化一个新的 `Line` 节点：

```java
Line line = new Line();
```

现在你可以设置起始和结束的 x 和 y 坐标。在实例化 `Line` 节点后，输入 `line.`，所示：

```java
line.
```



当你这样做时，应该弹出一个上下文菜单。如果上下文菜单没有自动出现，按下 `CTRL-SPACEBAR`。此快捷键组合将调出图 5-1 所示的上下文菜单。

上下文菜单是一个非常有价值的工具，显示了脚本特定位置可用的所有选项。可以使用上下文菜单来发现你否则不会察觉的元素或属性。上下文菜单甚至可以查看可以赋值给属性的某些值。你应该记住 `CTRL-SPACEBAR` 快捷键组合，因为你会发现自己经常使用它。

# JavaFX 快速上手指南

![](img/f5bc6249660e63bd0b6a2dc95983edb7_75_0.png)

图 5-1 上下菜单

如果在上下文菜单处于某个属性或方法时按下 `ENTER` 键（如图 5-1 所示），该属性或方法将插入到你的代码中。
滚动你的上下文菜单或开始输入，直到看到 `setStartX`。`startX` 属性是你画线需要指定的四个属性之一。确保 `setStartX` 属性被高亮，然后按下 `ENTER` 键。

给 `setStartX` 方法传递值 `10`。Java 文件中的每行代码都以分号结尾（某些除外）。使用 `ENTER` 键在每行代码后移动到新行。接下来，使用上下文菜单插入对 `setY` 的调用，并同样为其赋值为 `10`。

你将画一条从 `x10, y10` 延伸到 `x150, y150` 的线。鉴于你刚刚将 `10, 10` 分配给了起始 X 和起始 Y，请使用上下文菜单完成对结束 X 和结束 Y 的正确值的赋值。你的代码应该像这样：

```java
package Chapter5;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.scene.shape.Line;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter5 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Line line = new Line();
        StackPane root = new StackPane();
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

```java
line1.setX(10);
line1.setY(10);
line1.setEndX(100);
line1.setEndY(100);
line1.setStrokeWidth(15);
line1.setStroke(Color.TOMATO);
```

```java
line2.setX(10);
line2.setY(100);
line2.setEndX(100);
line2.setEndY(100);
line2.setStrokeWidth(15);
line2.setStroke(Color.TOMATO);
```

```java
line3.setX(100);
line3.setY(100);
line3.setEndX(100);
line3.setEndY(10);
line3.setStrokeWidth(15);
line3.setStroke(Color.TOMATO);
```

```java
AnchorPane root = new AnchorPane();
```

```java
root.getChildren().add(line1);
root.getChildren().add(line2);
root.getChildren().add(line3);
```

```java
primaryStage.setScene(new Scene(root, 300, 250));
primaryStage.show();
```

运行你的代码，并将结果与图 5-3 所示的结果进行比较。

为你能想到的每一个形状和配置绘制单独的线条对于开发者来说并不是非常高效的时间利用。想象一下如果你必须一个一个地绘制每条线来形成简单的形状将会将会什么样。幸运的是，你可以使用另一种类型的线条，叫做折线（polyline）。它允许你在的一条线中指定多一组点，其中最后一组是端点。通过指定多个端点，你可以用更少的代码绘制出更复杂的线条。让我们尝试使用 `Polyline` 节点绘制相同的 U 形三线型配置。

使用 `Polyline` 节点的第一步是导入 `Polyline` 包。使用折线的代码与使用直线（line）的代码不同。出于这个原因，你需要导入一个单独的类来处理折线：

```java
import javafx.scene.shape.Polyline;
```

# 第 5 章：创建形状

![](img/f5bc6249660e63bd0b6a2dc95983edb7_80_0.png)

导入包后，实例化一个新的 `Polyline`。调出上下文菜单查看可用方法。

注意，没有 `setStartX` 和 `setStartY` 的方法。相反，`Polyline` 接受一个点数组。`getPoints()` 方法返回构成你的 `Polyline` 的所有点的 `ObservableList`。`ObservableList` 的方法之一是 `add()`。因此，你可以使用 `getPoints()` 的 `add()` 方法添加新的点数组。

当你将点数组传递给 `Polyline` 节点时，可以理解为两个值将是起始点的 x 和 y 坐标，最后两个值将是端点。`Polyline` 类会直能地在这些点之间绘制你的线条，并在你数组中的所有其他点处停止。你可以轻松地使用 `Polyline` 中的点数组来复现你用 `Line` 创建的“U”字形线条布局。

与 `Line` 示例中使用的点匹配的点数组看起来如下：

```java
new Double[] {10.0, 10.0,
10.0, 100.0,
100.0, 100.0,
100.0, 10.0}
```

注意数组中的每个值都用逗号隔开。

## 提示

为了让数组在视觉上易于理解，你可以将每个 x、y 对分到新的一行。数组内部的空白会被编译器忽略，可以添加空白来使你的数组易于阅读。

运行以下代码。它应该会产生与上一个示例相同的三线 U 形——但代码要少得多：

```java
package Chapter5;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.AnchorPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Polyline;
import javafx.stage.Stage;

/**
 * @author J F F DiMarzio
 */
public class Chapter5 extends Application {

    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Polyline polyline = new Polyline();
        polyline.getPoints().addAll(new Double[]{
            10.0, 10.0,
            10.0, 100.0,
            100.0, 100.0,
            100.0, 10.0
        });
        polyline.setStrokeWidth(15);
        polyline.setStroke(Color.TOMATO);
        AnchorPane root = new AnchorPane();
        root.getChildren().add(polyline);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

完成这一节后，你学习了如何创建简单的线条并将它们绘制到屏幕上。在下一节中，你将开始应用迄为止学到知识，并开始创建更复杂的矩形和曲线对象。

## 矩形

`Rectangle` 节点用于表示正方形或矩形。它用于绘制任何平行的四边形。鉴于矩形和正方形之间的唯一区别是边长，使用同一个元素是有道理的。`Polyline` 通过仅要求指定一个点来完善了这一过程。当你创建一个矩形时，你只需要指定形状左上角的点。创建矩形所需的代码在一个与核心 JavaFX 代码分开的包中。在创建矩形之前，你需要导入 `javafx.scene.shape.Rectangle`。因此，请在你的文件中插入以下导入语句：

```java
import javafx.scene.shape.Rectangle;
```

你将绘制一个从 x10, y10 开始的矩形。它的宽为 100 像素，高为 150 像素。

## 注意

不要被 *height*（高度）这个术语搞混。矩形的高度实际上是从起始点向下计算的（而不是像名称暗示的那样从起始点向上）。因此，从 1,1 开始且高度为 1 的矩形将向下延伸。

## 提示

为了保持数组在视觉上易于理解，你可以将每个 x、y 对分到新的一行。数组内部的空白会被编译器忽略，并可以添加空白来使你的数组易于读。

运行以下代码。它应该产生与之前的示例相同的三线 U 形——但代码要少得多：

```java
rectangle.setFill(null);
rectangle.setStroke(Color.BLACK);
rectangle.setStrokeWidth(5);
rectangle.setArcHeight(20);
rectangle.setArcWidth(20);
```

```java
AnchorPane root = new AnchorPane();
root.getChildren().add(rectangle);
```

```java
primaryStage.setScene(new Scene(root, 300, 250, 250));
primaryStage.show();
```

现在你已经学习了如何在屏幕上绘制矩形，接下来可以继续学习更复杂的形状——多边形（polygon）。下一节将讨论如何使用 JavaFX 在屏幕上绘制多边形或多边形状的过程。

## 多边形

多边形之于矩形犹如折线（polyline）之于直线（line）。多边形节点的设置方式与 `Polyline` 类似（在本章的节节中讨论过）。`Line` 和 `Rectangle` 接受固定数量的坐标来确定一个点，而 `Polyline` 和 `Polygon` 接受一个点数组。

多边形将在你在 `points` 数组中指定的所有点之间绘制线条，方式与 `Polyline` 相同。

> 注意
> 适用于矩形的颜色规则也适用于 `Polygon` 节点。默认情况下，所有多边形都填充色块。此外，线条颜色和填充颜色分别由 stroke（描边）和 fill（填充）属性控制。

下面的示例代码使用 `Polygon` 元素在屏幕上绘制了一个简单的小八边形：

```java
package Chapter5;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.AnchorPane;
import javafx.scene.shape.Polygon;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter5 extends Application {
    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Polygon polygon = new Polygon();
        polygon.getPoints().addAll(new Double[]{
            90.0, 80.0,
            190.0, 80.0,
            240.0, 130.0,
            240.0, 220.0,
            190.0, 270.0,
            90.0, 270.0,
            40.0, 220.0,
            40.0, 130.0
        });
        AnchorPane root = new AnchorPane();
        root.getChildren().add(polygon);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

注意，不需要指定多边形的终点与起点相同。JavaFX 会自动将你数组中的最后一个点与第一个点连接起来。

在本章的下一节中，你将学习如何创建曲线形状，如弧（arc）、圆和椭圆。

## 弧

虽然弧在表面上看起来是一个简单的形状，但对计算机来说可能非常复杂。人们看着弧会想：“它只是圆的一部分。”但对计算机来说，弧是由复杂的半径、中心点、角度和周长组成的。

`Arc` 元素需要七个基本属性。与绘制直线相比，绘制弧所需的属性与你目前为止为止的不同。为了开始，导入以下类：

```java
import javafx.scene.shape.Arc;
import javafx.scene.shape.ArcType;
```

首先要求的属性是 `centerX` 和 `centerY`：

```java
arc.setCenterX(125);
arc.setCenterY(125);
```

想象一下圆。弧是圆的一个段。JavaFX 认为弧是一个它只需要绘制部分的圆。因此，`centerX` 和 `centerY` 属性代表了如果弧完成后的圆心。

接下来两个属性是 `radiusX` 和 `radiusY`：



```java
arc.setRadiusX(50);
arc.setRadiusY(50);
```

每个圆从中心延伸。这个距离就是半径。`Arc` 节点需要你指定半径。然而，属性的命名可能具有误导性，因为 `radiusX` 和 `radiusY` 并不代表一个点，而是代表沿 x 和 y 轴的半径。两个独立的半径让你创建弧。

> **提示**
>
> 要制作圆弧，将 `radiusX` 和 `radiusY` 属性设置为相同的值。

下一个要求的属性是 `startAngle`：

```java
arc.setStartAngle(45);
```

`startAngle` 代表从你的中心点到弧的起始点的不可见线。这条线位于给定的角度。因此，`startAngle` 为 45 意味着弧将从中心点的 45 度角开始。

创建弧所需的下一个属性是 `length`：

```java
arc.setLength(270);
```

你为止处理的其他长度相关的属性（如宽度和高度）是基于像素长度的。弧的 `length` 属性表示弧从中心点移动的度数。因此，如果你有一个 270，它将从起点延伸。

下一个要求的属性是 `type`：

```java
arc.setType(ArcType.OPEN);
```

`Arc` 的 `type` 属性描述了弧的绘制方式。可以分配三种不同的 `ArcType` 值：

- `ArcType.OPEN` 将弧绘制为开启
- `ArcType.CHORD` 在连接端点时绘制弧
- `ArcType.ROUND` 绘制弧并圆化端点

你需要的最后一个属性是 `fill` 和 `stroke`。要创建一个弧的黑色边缘，如示例所示，将 `fill` 设置为 `null` 并 `stroke` 设置为 `Color.BLACK`：

```java
package Chapter5;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.AnchorPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Arc;
import javafx.scene.shape.ArcType;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter5 extends Application {

    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Arc arc = new Arc();
        arc.setCenterX(125);
        arc.setCenterY(125);
        arc.setRadiusX(50);
        arc.setRadiusY(50);
        arc.setStartAngle(45);
        arc.setLength(270);
        arc.setType(ArcType.OPEN);
        arc.setFill(null);
        arc.setStroke(Color.BLACK);

        AnchorPane root = new AnchorPane();
        root.getChildren().add(arc);

        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

再次，JavaFX 提供了另一个 Builder 类让这个过程变得简单。`ArcBuilder` 可以如下使用：

```java
arcBuilder.create().centerX(125).centerY(125)
    .radiusX(50).radiusY(50).startAngle(45)
    .length(270).type(ArcType.OPEN)
    .stroke(Color.BLACK).build();
```

在下一节中，你将创建圆和椭圆。

## 圆和椭圆

创建弧之后，使用 JavaFX 创建圆似乎会简单得多。`Arc` 节点需要七个属性来控制角度、长度和其他特征，而 `Circle` 节点只需要三个。但在创建圆之前，你必须导入相应的包：

```java
import javafx.scene.shape.Circle;
```

创建圆三个属性是 `centerX`、`centerY`、`radius`。这些属性的功能与弧完全相同。

> **注意**
>
> `Circle` 节点对半径只有一个值，而不是像 `Arc` 那样有一对高度和宽度，因为圆不能是“方形”。因此，它在所有轴上始终具有相同的半径值。

拥有一组简单的属性使得在应用程序中创建和使用圆变得容易。以下代码创建一个圆的黑色边缘：

```java
    @Override
public void start(Stage primaryStage) {
    Circle circle = new Circle();

    circle.setCenterX(125);
    circle.setCenterY(125);
    circle.setRadius(50);
    circle.setFill(null);
    circle.setStroke(Color.BLACK);

    AnchorPane root = new AnchorPane();
    root.getChildren().add(circle);

    primaryStage.setScene(new Scene(root, 300, 250));
    primaryStage.show();
}
```

## JavaFX 快速上手指南

```java
primaryStage.setScene(new Scene(root, 300, 250));
primaryStage.show();
}
```

你可以使用同样的过程来创建一个椭圆。椭圆与圆唯一的区别在于，由于椭圆是长形的，`Ellipse` 元素接受一对 x, y 径对，而不是一组径向长度。以下是代码：

```java
package Chapter5;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.AnchorPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Ellipse;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter5 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Ellipse ellipse = new Ellipse();

        ellipse.setCenterX(125);
        ellipse.setCenterY(125);
        ellipse.setRadiusX(35);
        ellipse.setRadiusY(20);
        ellipse.setFill(null);
        ellipse.setStroke(Color.BLACK);

        AnchorPane root = new AnchorPane();
        root.getChildren().add(ellipse);

        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

## 第 5 章：创建形状

## 尝试：创建多个形状

在进入下一章之前，花些时间练习你新的形状构建技能。虽然这看起来像是一项非常基础的任务，但在整个开发生涯中，你会有很多创建简单形状的需求。从设计新按钮到创建掩罩，你始终需要创建简单形状。

尝试在同一个 `Scene` 中添加多个形状。尝试调整形状的尺寸和位置，防止它们重叠。继续操作它们，以控制形状如何相互接触或覆盖。

这个练习对未来的开发非常有帮助，因为它能让你充分掌握元素是如何放置在 `Scene` 中的。

在本章中，你学习了如何使用 Java Scene Builder 创建一些基本形状。你创建了线、折线、矩形、圆弧、圆和椭圆。你还学习了一个非常有价值的工具：上下文菜单。这些技能将在本书的剩余部分为你提供极大帮助。

在下一章中，你将学习如何处理和创建比本章涉及更多的颜色。你还将学习如何应用不透明度和旋转等效果。

## 第 5 章自测

1. 绘制一条线需要哪四个属性？
2. 如何访问上下文菜单？
3. 处理颜色时需要哪个包？
4. 哪个属性控制用于绘制形状的线条的厚度？
5. 绘制折线需要哪个包？
6. `Polyline` 节点的 `points` 属性分配的是什么类型的值？
7. 正或错？`Rectangle` 节点的 `height` 属性是从起始点到矩形顶部的像素数。
8. `Rectangle` 节点的 `fill` 属性的默认值是什么？
9. 正或错？`RadiusX` 和 `radiusY` 组成半径扩展到的点。
10. 哪个属性配置圆的半径？

![](img/f5bc6249660e63bd0b6a2dc95983edb7_94_0.png)

## 第 6 章

### 使用颜色和渐变

## 核心技能与概念

- 创建混合颜色
- 为形状应用颜色
- 使用渐变

在本章中，你将更深入地探索 JavaFX 中提供的强大颜色和渐变工具。在第 5 章中，你学习了如何将一些基础的、预定义的颜色应用到形状上。在本章中，你学习了如何混合自己的颜色，并将这些颜色应用到形状并在渐变中使用它们。

## 使用颜色

`Color` 类是一个非常强大的类。在上一章中，你只使用了 `Color` 类的一小部分来为 `Line` 节点填充了纯色。你只使用了 `Color` 类 148 种定义颜色中的一或两种。这仅仅是 `Color` 类能力的一个小样本。

该类有四种不同的用法，每种方式都为创建任何情况下所需的颜色提供了可靠的方法。你可以调用 `Color` 类来使用预定义颜色、RGB 值、HSB 值或 Web 十六进制值。

在本节中，你将学习更多关于提供的预定义颜色以及其他颜色方法。

## 预定义颜色

包含在 `javafx.scene.paint.Color` 包中的 `Color` 类具有许多可以在节点属性上立即使用的预定义颜色。在上一章中，你使用了一个预定义颜色（`Color.TOMATO`）来填充线条。事实上，所有形状都使用 `Color.BLACK` 预定义颜色作为填充色。`Color` 类提供了以下预定义颜色：

| ALICEBLUE | ANTIQUEWHITE | AQUA |
| AQUAMARINE | AZURE | BEIGE |
| BISQUE | BLACK | BLANCHEDALMOND |
| BLUE | BLUEVIOLET | BROWN |
| BURLYWOOD | CADETBLUE | CHARTREUSE |
| CHOCOLATE | CORAL | CYAN |
| DARKBLUE | DARKCYAN | DARKGOLDENROD |
| DARKGRAY | DARKGREEN | DARKKHAKI |
| DARKMAGENTA | DARKOLIVEGREEN | DARKORANGE |
| DARKORCHID | DARKRED | DARKSALMON |
| DARKSEAGREEN | DARKSLATEBLUE | DARKSLATEGRAY |
| DARKTURQUOISE | DARKVIOLET | DEEPPINK |
| DEEPSKYBLUE | DIMGRAY | DODGERBLUE |
| FIREBRICK | FLORALWHITE | FORESTGREEN |
| FUCHSIA | GAINSBORO | GHOSTWHITE |
| GOLD | GOLDENROD | GRAY |
| GREEN | GREENYELLOW | GREY |
| HOTPINK | INDIANRED | INDIGO |
| IVORY | KHAKI | LAVENDER |
| LAVENDERBLUSH | LAWNGREEN | LEMONCHIFFON |
| LIGHTBLUE | LIGHTCORAL | LIGHTCYAN |
| LIGHTGOLDENRODYELLOW | LIGHTGRAY | LIGHTGREEN |
| LIGHTGREY | LIGHTPINK | LIGHTSALMON |
| LIGHTSEAGREEN | LIGHTSKYBLUE | LIGHTSLATEGRAY |
| LIGHTSTEELBLUE | LIGHTYELLOW | LIME |
| LIMEGREEN | LINEN | MAGENTA |
| MAROON | MEDIUMAQUAMARINE | MEDIUMBLUE |
| MEDIUMORCHID | MEDIUMPURPLE | MEDIUMSEAGREEN |
| MEDIUMSLATEBLUE | MEDIUMSPRINGGREEN | MEDIUMTURQUOISE |
| MEDIUMVIOLETRED | MIDNIGHTBLUE | MINTCREAM |
| MISTYROSE | MOCCASIN | NAVAJOWHITE |
| NAVY | OLDLACE | OLIVE |
| OLIVEDRAB | ORANGE | ORANGERED |
| ORCHID | PALEGOLDENROD | PALEGREEN |
| PALETURQUOISE | PALEVIOLETRED | PAPAYAWHIP |
| PEACHPUFF | PERU | PINK |
| PLUM | POWDERBLUE | PURPLE |
| RED | ROSYBROWN | ROYALBLUE |
| SADDLEBROWN | SALMON | SANDYBROWN |
| SEAGREEN | SEASHELL | SIENNA |
| SILVER | SKYBLUE | SLATEBLUE |
| SLATEGRAY | SNOW | SPRINGGREEN |
| STEELBLUE | TAN | TEAL |
| THISTLE | TOMATO | TRANSPARENT |
| TURQUOISE | VIOLET | WHEAT |
| WHITE | WHITESMOKE | YELLOW |
| YELLOWGREEN | | |

预定义颜色通过 `Color` 类的常量进行访问。例如，在 `Color` 类中，常量 `BLUE` 与创建蓝色所需的数值相关。让我们看看下面这行代码（它与形状相关）：

```java
ellipse.setFill(Color.BLUE);
```

当你将填充属性赋值为 `Color.BLUE` 时，`Color` 类会传递创建蓝色所需的数值。它提供了大量的预定义颜色供你的脚本使用。

## 混合颜色

如果你查看了预定义颜色但没有找到确切的，你始终可以混合或指定自己的颜色。如果只能使用预定义颜色而无法自定义，`Color` 类将是一个非常有限的工具。

出于这个原因，`Color` 类有三个非常有用的方法来混合自己的颜色：

```java
Color.rgb();
Color.hsb();
Color.web();
```

让我们看看这些每个方法以及如何使用它们。

## Color.rgb

`Color` 类允许你使用想要创建的颜色的 RGB（红、绿、蓝）值。大多数颜色都是由不同量的红、绿、蓝混合而成的。用于创建颜色的红、绿、蓝分量使用 0 到 255 之间的值定义（0 表示不含该颜色，255 表示指定颜色的全量）。以下代码将把矩形的内部填充为紫色：



# 第 6 章：使用颜色和渐变

```java
Rectangle rectangle = new Rectangle();
rectangle.setX(10);
rectangle.setY(10);
rectangle.setHeight(150);
rectangle.setWidth(150);
rectangle.setFill(Color.rgb(255, 0, 255));
```

在对 `Color` 类的此方法调用中，你指定的 RGB 值为 255 红色、0 绿色和 255 蓝色。这产生了紫色。然而，尝试以下代码看看得到什么：

```java
Rectangle rectangle = new Rectangle();
Color purple = new Color(1, 0, 1, 1);
rectangle.setX(10);
rectangle.setY(10);
rectangle.setHeight(150);
rectangle.setWidth(150);
rectangle.setFill(purple);
```

这段代码也产生了一个填充为紫色的矩形。`Color` 类的默认构造函数也接受 RGB 值来创建颜色。那么区别在哪里？最终结果是相同的：你得到的颜色都是紫色。区别在于 `Color` 类的默认构造函数接受 0 到 1 之间的浮点数作为红、绿、蓝的值。请记住，`Color` 类的 `rgb` 方法接受 0 到 255 之间的值。最后一个值是 Alpha（不透明度），它应该是 1 以实现完全不透明。

## Color.hsb

`Color` 类还有一个用于 HSB（色相、饱和度、亮度）颜色的方法。在 HSB 颜色模型中，颜色或色相由 0 到 360 之间的数字表示。这个数字对应于色轮 360 度中的某一个。

饱和度和亮度属性由 0 到 1 之间的数字表示。值 0 表示没有饱和度和亮度，而值 1 表示完全饱和度和完全亮度。要创建你刚刚用 `rgb` 方法创建的相同紫色，请使用以下代码：

```java
rectangle = new Rectangle();
rectangle.setX(10);
rectangle.setY(10);
rectangle.setHeight(150);
rectangle.setWidth(150);
rectangle.setFill(Color.hsb(300, 1, 1));
```

## Color.web

最后，`Color` 类还可以使用 Web 十六进制值为你创建颜色。`Color` 类的 `web` 方法接受标准的十六进制值。这是一个示例：

```java
Rectangle rectangle = new Rectangle();
rectangle.setX(10);
rectangle.setY(10);
rectangle.setHeight(150);
rectangle.setWidth(150);
rectangle.setFill(Color.web("#FF00FF"));
```

## alpha 属性

你应该注意的 `Color` 类的最后一个属性是 alpha 属性。`Color` 类的每个方法都有一个可选的 alpha 属性。alpha 值控制所创建颜色的透明度。alpha 值是 0 到 1 之间的值，0 是透明的，1 是不透明的。alpha 值可以添加到 `Color` 类的任何方法中。通过将 alpha 值设置为 0，你将实现完全透明：

```java
Rectangle rectangle = new Rectangle();
rectangle.setX(10);
rectangle.setY(10);
rectangle.setHeight(150);
rectangle.setWidth(150);
rectangle.setFill(Color.web("#FF00FF", 0));
```

与 0 的完全透明相反，你可以将 alpha 值设置为 1 以获得完全不透明的颜色：

```java
Rectangle rectangle = new Rectangle();
rectangle.setX(10);
rectangle.setY(10);
rectangle.setHeight(150);
rectangle.setWidth(150);
rectangle.setFill(Color.web("#FF00FF", 1));
```

最后，将 alpha 值设置为 .5 将为你提供 50% 的透明度：

```java
Rectangle rectangle = new Rectangle();
rectangle.setX(10);
rectangle.setY(10);
rectangle.setHeight(150);
rectangle.setWidth(150);
rectangle.setFill(Color.web("#FF00FF", 0.5));
```

在下一节中，你将学习如何创建和使用渐变。渐变为填充形状提供了一种创意且引人注目的方式。

## 使用渐变

你可以使用两种渐变来填充形状：线性渐变（`LinearGradient`）和径向渐变（`RadialGradient`）。线性渐变是从形状的一侧到另一侧沿直线填充的渐变。径向渐变从一个点开始渐变，渐变从该点向外辐射填充形状。

让我们先看看如何向矩形应用线性渐变。

## 线性渐变

`LinearGradient` 类包含在 `javafx.scene.paint` 包中：

```java
import javafx.scene.paint.LinearGradient;
```

你需要了解七个参数。`LinearGradient` 构造函数接受 `startX`、`startY`、`endX`、`endY`、`proportional`、`cycleMethod` 和 `stops`。`proportional` 是一个布尔值，表示起始点和终点是否相对于形状边界成比例（0 到 1 之间）。`cycleMethod` 是一个枚举值，可以是 `NO_CYCLE`（默认）、`REPEAT` 或 `REFLECT`。

（注：由于原文在后续部分似乎存在描述错乱或截断，此处根据上下文逻辑进行了意译和补全）

![](img/f5bc6249660e63bd0b6a2dc95983edb7_104_0.png)

图 6-4 圆形中的径向渐变

映射到的对象。`FocusAngle`（聚焦角度）还与下一个参数 `FocusDistance`（聚焦距离）一起使用，以确定渐变的精确聚焦位置。`FocusDistance` 是从中心点沿着 `FocusAngle` 到渐变焦点的距离。

`RadialGradient` 类也像 `LinearGradient` 类一样，也接受一个停止点（`stops`）数组来产生两种以上颜色的渐变。以下代码生成图 6-4 所示的渐变：

```java
Circle circle = new Circle();
Stop[] gradientStops = new Stop[] {
    new Stop(0, Color.BLACK),
    new Stop(1, Color.WHITE)
};
RadialGradient lg = new RadialGradient(0.1, 0.1, 5, 7,
    true, CycleMethod.NO_CYCLE, gradientStops);

circle.setRadius(70);
circle.setCenterX(100);
circle.setCenterY(100);
circle.setFill(lg);
```

## 创建自定义渐变

使用你在第 5 章中学习的技能，创建一个包含多个形状的新 Scene。一旦形状就位，就使用在本章中学习的技能为每个形状添加不同的渐变。通过在每个形状上混合不同的颜色来更改渐变。这是练习多种技术并获得即时结果的极好方法。

在本章中，你学习了如何创建颜色、制作渐变并将它们应用到形状上。`LinearGradient` 和 `RadialGradient` 为你的形状添加视觉趣味提供了简单的方法。

在下一章中，你将学习如何在应用程序中使用图像。

## 第 6 章自测

1. `Color` 类中有多少预定义颜色？
2. `Color` 类中用于混合颜色的三种方法是什么？
3. 正确或错误？RGB 代表折射、渐变和模糊。
4. Hue（色相）的接受取值范围是什么？
5. `LinearGradient` 的代码在哪个包中？
6. `proportional`（比例）参数的默认值是多少？
7. 当 `proportional` 设置为 `true` 时，`startX` 的接受取值范围是什么？
8. 正确或错误？`stops` 参数告诉渐变在哪个点停止。
9. 正确或错误？渐变可以由两种及以上的颜色组成。
10. 哪种渐变最适合曲线形状？

# 第 7 章：使用图像

![](img/f5bc6249660e63bd0b6a2dc95983edb7_106_0.png)

## 关键技能与概念

- 使用 `ImageView`
- 加载图像
- 加载图像占位符

很有可能如果你正在使用 JavaFX 创建应用程序，你将需要与图像进行某种形式的交互。即使你的应用程序与图像或图像处理没有相关，你可能需要一个启动界面、背景，甚至是一个用于控件的图像。

本章教你如何处理图像并将其加载到 JavaFX 中。到本章结束时，你能够将图像文件添加到项目中并将其加载到屏幕上。此过程的第一步是学习 `ImageView` 节点。

## ImageView 节点

在屏幕上显示图像之前，你需要向场景图添加一个 `ImageView` 节点。所有的图像都使用 `ImageView` 节点显示。把它想象成冲洗照片的胶片。`ImageView` 节点的唯一目的是使用 `Image` 类显示你的图像。

创建一个名为 `Chapter7` 的新 JavaFX 应用程序（就像你在之前的章节中所做的那样并删除 `Chapter7.java` 中所有的 Hello World 代码。

`ImageView` 的类是 `javafx.scene.image.ImageView`。

在使用 `ImageView` 之前你必须导入此包。实例化一个新的 `ImageView` 并将其添加到 `Scene` 中，如下所示：

```java
package Chapter7;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.image.ImageView;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter7 extends Application {
    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        ImageView imageView = new ImageView();

        StackPane root = new StackPane();
        root.getChildren().add(imageView);

        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

目前情况下，`ImageView` 什么都不会做。请记住，虽然 `ImageView` 本身是一个节点，但如果没有要显示的图像，它实际上并做不了什么。现在应用程序将编译并运行，但你将看到一个空白的 UI；你需要添加一张图像让 `ImageView` 显示。在下一节中，你将使用 `Image` 类来帮助 `ImageView` 在屏幕上显示某些内容。

> **提示**
>
> `ImageView` 具有影响图像显示方式的属性。然而，如果没有要显示的图像，讨论这些属性就没有意义。

## Image 类

`Image` 类用于获取图像并使用 `ImageView` 显示它们。在开始之前，你必须导入此包：

```java
import javafx.scene.image.Image;
```

`Image` 类可以从各种源读取图像。在本节中，你将处理两个源：网络和本地文件。首先，要从网上显示图像，你使用构造函数：

```java
Image butterfly = new Image("http://examplearzio.com/butterfly.png");
```

创建 `Image` 对象后，你可以使用宽度和高度。你想设置宽度和比例来告诉 `ImageView`，如下：

```java
@Override
public void start(Stage primaryStage) {
    Image butterfly = new Image("http://examplearzio.com/butterfly.png");
    ImageView imageView = new ImageView();

    imageView.setImage(butterfly);
    imageView.setFitWidth(300);
    imageView.setPreserveRatio(true);

    StackPane root = new StackPane();
    root.getChildren().add(imageView);

    primaryStage.setScene(new Scene(root, 300, 250));
    primaryStage.show();
}
```

编译并运行此代码后，你的应用程序看起来应该像图 7-1 所示。JavaFX 在显示网站图像方面做得很好，涉及的设置非常直观。

如果你想显示本地的图像，概念仍然相同，但过程略有不同。你需要提前考虑图像如何与应用程序一起分发。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_110_0.png)

图 7-1 使用网络图像

![](img/f5bc6249660e63bd0b6a2dc95983edb7_111_0.png)

图 7-2 向包中添加图像

你可以通过在 `Image` 构造函数指定指定文件的完整路径，引用 `images` 文件夹中的新图像。以下代码显示了使用 `ImageView` 显示 `images` 文件夹中的 `butterfly.png` 文件：

> **注意**
>
> 将此代码中的路径替换为指向你的项目和图像文件夹的路径。

```java
@Override
public void start(Stage primaryStage) {
    Image butterfly = new Image(Chapter7.this.getClass()
        .getResource("images/butterfly.png")
        .toExternalForm());
    ImageView imageView = new ImageView(butterfly);

    imageView.setFitWidth(300);
    imageView.setPreserveRatio(true);

    StackPane root = new StackPane();
    root.getChildren().add(imageView);

    primaryStage.setScene(new Scene(root, 300, 250));
    primaryStage.show();
}
```

到目前，你已经学习了如何使用 `Image` 类和 `ImageView` 节点显示图像。诚然，这并不是书中最令人兴奋的代码——它非常基础。然而，一旦图像加载到 `Scene` 中，真正的乐趣就开始了。

以下代码加载图像，并使其在水平和垂直方向上移动：

```java
Image butterfly = new Image("file:C:/Users/J F DiMarzio/" +
    "Documents/NetBeansProjects/Chapter7/" + 
    "src/Chapter7/images/butterfly.png");
ImageView imageView = new ImageView(butterfly);

imageView.setTranslateX(30);
imageView.setTranslateY(30);
imageView.setRotate(45);
```

`ImageView` 继承了 `Node` 的方法，可以用于设置图像的 X 和 Y 平移。`setTranslateX()` 方法将图像相对于其左上角位置在 X 笛卡尔坐标系上移动相应数量的点。同理，`setTranslateY()` 和 `setTranslateZ()` 将分别沿 Y 和 Z 坐标移动图像。最后，`setRotate()` 方法将图像绕其中心点旋转指定的度数。

将之前的代码添加到你的 Java 文件中，使其看起来如下：

```java
@Override
public void start(Stage primaryStage) {
    Image butterfly = new Image("file:C:/Users/J F DiMarzio/" +
        "Documents/NetBeansProjects/Chapter7/" + 
        "src/Chapter7/images/butterfly.png");
    ImageView imageView = new ImageView(butterfly);

    imageView.setTranslateX(30);
    imageView.setTranslateY(30);
    imageView.setRotate(45);

    StackPane root = new StackPane();
    root.getChildren().add(imageView);

    primaryStage.setScene(new Scene(root, 300, 250));
    primaryStage.show();
}
```



# 第 7 章：使用图像

```java
imageView = new ImageView();

imageView.setImage(butterfly);
imageView.translateX(30);
imageView.translateY(30);
imageView.setRotate(45);

imageView.setFixedWidth(300);
imageView.setPreserveRatio(true);

StackPane root = new StackPane();
root.getChildren().add(imageView);

primaryStage.setScene(new Scene(root, 300, 250));
primaryStage.show();
```

使用你的 Desktop 配置文件运行此代码，你将看到图像经过了旋转和移动，如图 7-3 所示。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_113_0.png)

**图 7-3** 旋转并移动的蝴蝶图像

## 尝试：处理不同类型的图像

在进入下一章之前，花些时间探索 JavaFX 如何显示和处理不同的图像及图像类型。使用在本章中学的技能，尝试向 JavaFX 显示不同类型的图像。哪些图像文件可以显示？哪些图像文件不能显示？

为了进一步研究，请尝试更改图像的大小。注意哪种类型的图像允许你在最短的时间内加载最大的图像。这项技能将在将来帮助你，因为你可能需要将来自不同开发者或来源的不同类型的图像整合到一个应用程序中。

## Canvas

JavaFX 提供了另一种用于在屏幕上绘制的 API。`Canvas` API 是 `Node` 的另一个子类，可用于场景图中绘制屏幕并显示形状、颜色和纹理。

`Canvas` API 在渲染对象到屏幕时使用 `GraphicsContext`。`GraphicsContext` 类实现了 `Canvas` API 的绘制调用。在本节提供的示例中，仅使用了少量用于在 Canvas 上绘制、填充和写入可用方法。

让我们使用 `Canvas` API 在屏幕上画两个圆。第一个圆是红色填充圆，第二个圆是黑色的空心轮廓圆。

首先，设置一个新的 `Stage`。为新 Stage 实例化 `Canvas`、`Group` 和 `GraphicsContext`，如下：

```java
public static void main(String[] args) {
    launch(args);
}

@Override
public void start(Stage primaryStage) {
    primaryStage.setTitle("Drawing Operations Test");
    Group root = new Group();
    Canvas canvas = new Canvas(800, 600);
    GraphicsContext gc = canvas.getGraphicsContext2D();
    root.getChildren().add(canvas);
    primaryStage.setScene(new Scene(root, 800, 600));
    primaryStage.show();
}
```

设置好 Stage 和 Canvas 后，创建一个名为 `drawCircles()` 的新方法。`drawCircles()` 方法接受来自 Canvas 的 `GraphicsContext`。然后，使用 `GraphicsContext`，`drawCircles()` 方法将设置所需的调用来创建示例中的两个圆：

```java
private void drawCircles(GraphicsContext gc) {
    gc.setFill(Color.RED);
    gc.setStroke(Color.BLACK);
    gc.setLineWidth(2);
    gc.fillOval(50, 50, 300, 300);
    gc.strokeOval(50, 50, 300, 300);
}
```

`drawCircles()` 方法使用 `GraphicsContext` 在 Canvas 上画两个圆。首先，调用 `setFill()` 和 `setStroke()` 将相应的画笔设置为红色（RED）和黑色（BLACK）。然后，使用 `setLineWidth()` 方法将画笔宽度设置为 2 像素。最后，通过调用 `fillOval()` 和 `strokeOval()` 画圆。

编译并运行以下代码，可以在 Canvas 上看到两个圆：

```java
public class Application {

    /**
     * @param args
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Drawing Operations Test");
        Group root = new Group();
        Canvas canvas = new Canvas(800, 600);
        GraphicsContext gc = canvas.getGraphicsContext2D();
        root.getChildren().add(canvas);
        primaryStage.setScene(new Scene(root, 800, 600));
        primaryStage.show();
        drawCircles(gc);
    }

    private void drawCircles(GraphicsContext gc) {
        gc.setFill(Color.RED);
        gc.setStroke(Color.BLACK);
        gc.setLineWidth(2);
        gc.fillOval(50, 50, 300, 300);
        gc.strokeOval(50, 50, 300, 300);
    }
}
```

# 第 8 章：应用效果与变换

```java
/**
 * @param args the command line arguments
 */
public static void main(String[] args) {
    launch(args);
}

@Override
public void start(Stage primaryStage) {
    Image image = new Image("http://jfdimario.com/butterfly.png");
    ImageView imageView = new ImageView();

    imageView.setImage(image);
    applyEffects(imageView);

    StackPane root = new StackPane();
    root.getChildren().add(imageView);
    primaryStage.setScene(new Scene(root, 800, 600));
    primaryStage.show();
}

private void applyEffects(ImageView imageView) {
}
```

这段代码与你在之前章节中使用的代码之间的主要区别在于包含了一个名为 `applyEffects()` 的方法，你所有的效果代码都将放在这里。该方法将使用你即将添加的代码对 `ImageView` 应用某种特定的效果。

```java
private void applyEffects(ImageView imageView) {
}
```

该方法接受你的 `ImageView` 作为参数。你将编写代码对传递到 `applyEffects()` 的 `ImageView` 应用效果。该方法将返回到代码主体，你的图像将以应用效果的形式进行渲染。

## 注意事项

这种使用通用方法为图像应用特定效果的设计在实际的应用程序中可能并不实用。然而，通过分离代码，这种设计非常适合学习效果的工作原理。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_121_0.png)

**图 8-1** 应用效果前的图像

编译后，这个 JavaFX 应用程序目前的状态应该产生一张与图 8-1 类似的图像。这个 java 文件在当前状态下将作为你学习本章其余内容的基础。你在本章中学习到的所有效果和变换都是通过此应用程序进行演示的。本章的第一部分介绍了效果，随后是关于变换的讨论。

## 效果

JavaFX 能够渲染出惊艳且复杂的效果。图像和效果可以进行混合、模糊、投影处理。此类效果可以非常有吸引力，并用于创建能够吸引用户的应用程序。

这些效果可以应用于 JavaFX 中的几乎任何节点。JavaFX 中为你提供的所有标准效果都在 `javafx.scene.effect` 包中。如果你还没有这样做，请导入此包以开始使用 JavaFX 效果：

```java
import javafx.scene.effect.*;
```

提示

到此为止，你已经显式指定了想要从每个包中导入的项。然而，`*` 符号告诉 JavaFX 导入特定包内的所有项。因此，`import javafx.scene.effect.*` 语句将使你能够访问 effect 包中的所有效果。

你将使用的第一个效果是 Bloom（发光）。

## Bloom

Bloom 会提取图像中对比度较高的区域，通过覆盖这些高对比度区域并将其溢出到周围图像中，使其看起来像在发光。应用到节点上的 Bloom 数量由 `threshold`（阈值）参数控制，该参数接受 0 到 1 之间的值，其中 0 表示没有任何效果。

使用 `Chapter8.java` 文件中的 `applyEffects()` 方法对 `butterfly.png` 图像应用 Bloom 效果。每个 `ImageView` 节点都有一个 `effect` 参数。该参数用于设置你想应用到该 `ImageView` 的效果。

提示

在本章中你操作 `ImageView` 是因为你刚刚在第 7 章中处理过它。然而，`ImageView` 并不是你可以应用效果的唯一节点。每个节点都包含一个 `effect` 参数，你可以在上面应用效果。

> 你现在可以编辑 `applyEffects()` 方法来为图像应用 Bloom 效果。向 `applyEffects()` 方法中添加以下行：

```java
bloom = new Bloom();
bloom.setThreshold(.5);
imageView.setEffect(bloom);
```

这会将 `ImageView` 的 `effect` 属性设置为 Bloom 效果。阈值设置为 .5，以便让你直观地了解 Bloom 效果可以做什么。你可以根据喜好调整阈值以达到所需的效果。你的 `applyEffects()` 方法现在看起来应该是这样的：

```java
private void applyEffects(ImageView imageView)
{
  Bloom bloom = new Bloom();
bloom.setThreshold(.5);
imageView.setEffect(bloom);
```

这里显示了完整的应用程序：

```java
package Chapter8;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.effect.Bloom;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.StackPane;
import javafx.scene.stage.Stage;
```

```java
/**
 * @author J F DiMarzio
 */
public class Chapter8 extends Application {

/**

 * @param args the command line arguments

 */

public static void main(String[] args) {

    launch(args);

}

@Override

public void start(Stage primaryStage) {

    Image image = new Image("http://jfdimarzio.com/butterfly.png");

    ImageView imageView = new ImageView();

    imageView.setImage(image);

    applyEffects(imageView);

    StackPane root = new StackPane();

    root.getChildren().add(imageView);

    primaryStage.setScene(new Scene(root, 800, 600));

    primaryStage.show();

}

private void applyEffects(ImageView imageView) {

    Bloom bloom = new Bloom();

    bloom.setThreshold(.5);

    imageView.setEffect(bloom);

}

}
```

![](img/f5bc6249660e63bd0b6a2dc95983edb7_124_0.png)

**图 8-2** 应用 Bloom 效果的蝴蝶

编译你的应用并运行它，以产生类似于 8-2 的图像。接下来，你将学习 ColorAdjust。

## ColorAdjust

顾如名，ColorAdjust 效果允许你调整节点的颜色。就像你调整电视机画面一样，JavaFX 允许你调整图像。ColorAdjust 包含了允许你调整对比度、亮度、色调和饱和度的参数。

ColorAdjust 效果的所有参数（`input` 除外）都接受 double 值。你可以为对比度、亮度、色调和饱和度分配 -1.0 到 1.0 之间的值。然而，你不一定需要为所有参数赋值。例如，如果你只想调整图像的对比度，只需为对比度指定一个值，JavaFX 将自动为其他参数赋值。（注意，JavaFX 不会自动为对比度分配 0，因为它的默认值为 1。）

## JavaFX 快速上手指南

在之前的章节中，你使用了 `LineBuilder` 和 `RectangleBuilder`。在本例中，你可以使用 `ColorAdjustBuilder` 来清理代码并让生活更轻松。

对于此示例，你为每个参数分配 .5，然后将效果应用到蝴蝶。向 `applyEffects()` 添加以下代码：

```java
ColorAdjust colorAdjust = new ColorAdjust();

colorAdjust.setBrightness(.5);

colorAdjust.setContrast(.5);

colorAdjust.setHue(.5);

colorAdjust.setSaturation(.5);
```

如果你跟了之前的例子，ColorAdjust 效果的结构看起来会很熟悉。整体而言，一旦操作几次，应用效果并不复杂。你完整的 `applyEffects()` 方法应该是这样的：

```java
private void applyEffects(ImageView imageView)

{

    ColorAdjust colorAdjust = new ColorAdjustBuilder.create().brightness(.5).contrast(.5)

    .hue(.5).saturation(.5).build();

    imageView.setEffect(colorAdjust);

}
```

## GaussianBlur

GaussianBlur 为节点提供了非常平滑的模糊效果。在后台，该效果基于所谓的高斯算法运行。该算法从每个像素按圆形模式运行，以平滑外观。由于该算法以圆形模式运行，你需要处理的参数是 `radius`（半径）参数，它控制了高斯算法从每个像素向外应用的范围。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_126_0.png)

**图 8-3** 使用 ColorAdjust 修改后的蝴蝶

你可以为 GaussianBlur 的半径指定一个 0 到 63 之间的值。值 0 会对原始图像产生几乎或完全的模糊，而值 63 则会产生极度模糊。以下代码实现了一个半径为 10 的 GaussianBlur（默认值）：

```java
GaussianBlur blur = new GaussianBlur();

blur.setRadius(10);
```

按照如下所示将 GaussianBlur 应用到你的 `applyEffects()` 函数中：

```java
private void applyEffects(ImageView imageView)

{

    GaussianBlur blur = new GaussianBlur();

    imageView.setEffect(blur);

}
```



运行你完成的程序，它将以半径 10 模糊背景。结果如图 8-4 所示。

注意，蝴蝶被轻微模糊了，但仍然可识别。现在将半径改为 60 并重新编译程序。结果如图 8-5 所示。

当你尝试调整图像大小时，`GaussianBlur` 特别有效。有时图像在缩放时可能会失真，特别是当图像在缩放之前非常清晰时。在缩放图像之前（在不自动执行的系统中）应用非常轻微的 `GaussianBlur` 可以使调整后的图像失真变少。

你接下来将学习 `Glow` 效果。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_127_0.png)

图 8-4 GaussianBlur 半径为 10 的蝴蝶

# 第 8 章：应用效果与变换

![](img/f5bc6249660e63bd0b6a2dc95983edb7_128_0.png)

图 8-5 GaussianBlur 半径为 60 的蝴蝶

## Glow

`Glow` 效果顾名思义，让你的节点看起来像在发光。应用到节点上的发光量由 `level` 参数控制。你可以应用于节点的发光强度范围是从 0 到 1。如果 `Glow` 效果未指定级别，JavaFX 将使用 `.3` 的默认值。

在本章前面的部分，你学习了 `Bloom` 效果，它为你的节点应用了类似于 `Glow` 的效果。`Bloom` 和 `Glow` 的区别在于发光的应用方式。`Bloom` 只对图像的高对比部分应用发光，而 `Glow` 则作用于整个图像。

以下代码展示了如何使用级别为 `.5` 的 `Glow` 使用 `applyEffects()` 方法：

```java
Glow glow = new Glow();
glow.setLevel(.5);
```

用此代码替换你当前 `.java` 文件中的 `applyEffects()` 方法。你完整的 java 文件应该看起来像这样：

```java
package Chapter8;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.effect.Glow;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * @author Java J F DiMarzio
 */
public class Chapter8 extends Application {

    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Image image = new Image("http://jdimarzio.com/butterfly.png");
        ImageView imageView = new ImageView();
        imageView.setImage(image);
        applyEffects(imageView);
        StackPane root = new StackPane();
        root.getChildren().add(imageView);
        primaryStage.setScene(new Scene(root, 800, 600));
        primaryStage.show();
    }

    private void applyEffects(ImageView imageView) {
        Glow glow = new Glow();
        glow.setLevel(.5);
        imageView.setEffect(glow);
    }
}
```

编译并运行你的程序。你的蝴蝶应该像图 8-6 所示的那样发光。

你接下来学习的效果是 `DropShadow` 效果。

# 第 8 章：应用效果与变换

![](img/f5bc6249660e63bd0b6a2dc95983edb7_130_0.png)

图 8-6 Glow 级别为 .5 的蝴蝶

## DropShadow

`DropShadow` 效果通过在阴影颜色中复制节点，并在源节点下方按特定量偏移“阴影”图像，在节点下方创建一个阴影。配置 `DropShadow` 需要相当多的参数：

- `radius` 用法类似于 `GaussianBlur` 的半径参数。
- `height`/`width` 可以代替半径使用，效果相同。
- `spread` 阴影的透明度。值 0 创建非常轻微的、散开的阴影，而值 1 会产生深色、锐利的阴影。
- `blurType` 创建阴影的算法。它可以设置为 `Gaussian`、`ONE_PASS_BOX`、`TWO_PASS_BOX` 或 `THREE_PASS_BOX`。这些模糊类型使用框模糊来平滑图像。你可以指定模糊是一次、两次还是三次。图像会随着每次通过变得越来越平滑。因此，三次的模糊会比一次的平滑得多。

要使用 `DropShadow` 效果，请如下所示修改你的 `applyEffects()` 方法：

```java
private void applyEffects(ImageView imageView) {
    DropShadow shadow = new DropShadow();
    shadow.setBlurType(BlurType.THREE_PASS_BOX);
    shadow.setColor(Color.BLACK);
    shadow.setOffsetX(10);
    shadow.setOffsetY(10);
    shadow.setRadius(10);
    shadow.setSpread(.2);
    imageView.setEffect(shadow);
}
```

此脚本在蝴蝶下方产生了一个如图 8-7 所示的阴影。`DropShadow` 效果通过创建原始图像的模糊副本来工作。该副本放置在原始图像下方并进行偏移以便可见。如果你想控制这个过程，可以使用 `Shadow` 效果。

`Shadow` 效果根据你的原始图像创建一个模糊的彩色图像。然而，它不会将未修改的图像副本重新添加到场景中。你只剩下图像的阴影。你必须手动向场景中添加另一个图像实例来完成效果。

不过，使用 `Shadow` 效果而非 `DropShadow` 效果也有其优势。例如，如果你想将阴影投影到偏离原始图像的位置，它会非常有用。

你接下来将学习 `Lighting` 效果。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_133_0.png)

图 8-7 带有 DropShadow 的蝴蝶

## Lighting

`Lighting` 效果无疑是 JavaFX 提供的最复杂的效果。`Lighting` 可为原本扁平的物体增加一个现实的维度。尽管 `Lighting` 的设置非常复杂，但如果使用正确，回报将是非常丰厚的。

`Lighting` 效果的主要参数是 `Light`，它代表来自 `javafx.scene.effect.light` 包的光源类型。三种不同的类可以用于 `Light`：

- `Distant`（平行光）
- `Point`（点光源）
- `Spot`（聚光灯）

# 第 8 章：应用效果与变换

## 注意

`Lighting` 与 `Light` 之间的关系定义了 `Lighting` 如何使用效果。

这些 `Light` 类型都有一套自己的参数来控制特定的光。

## Distant

`Distant` 类接受三个参数来配置和控制光：方位（`azimuth`）、高度（`elevation`）和颜色（`color`）。

```java
Light.Distant distant = new Light.Distant();
distant.setAzimuth(45);
distant.setElevation(45);
distant.setColor(Color.RED);
```

方位是光照射到物体角度，而高度是光源的高度。

更新你的 `applyEffects()` 方法以使用 `Distant`。将方位设置为 45，高度设置为 45，颜色设置为 RED，所示。不要忘记导入 `javafx.scene.paint.Color` 包以操作光的颜色。

```java
private void applyEffects(ImageView imageView) {
    Lighting lighting = new Lighting();
    lighting.setLight(new Light.Distant(45, 45, Color.RED));
    imageView.setEffect(lighting);
}
```

编译你的程序并运行，为蝴蝶应用红色的 `distant` 效果。结果如图 8-8 所示。

## PointLight

`Point` 光类接受四个参数：

```java
Light.Point point = new Light.Point();
point.setX();
point.setY();
point.setZ();
point.setColor();
```

![](img/f5bc249660e63bd0b6a2dc95983edb7_135_0.png)

应用了红色点光的蝴蝶

在此处提供的 `x`、`y`、`z` 坐标表示光在 3D 空间中的位置。就像你对 `Distant` 执行的那样，编辑你的 `applyEffects()` 方法使用位置在 `x150, y50, z250` 的 `Point`，所示：

```java
private void applyEffects(ImageView imageView) {
    Lighting lighting = new Lighting();
    lighting.setLight(new Light.Point(150, 50, 50, Color.YELLOW));
    imageView.setEffect(lighting);
}
```

编译并运行你的程序后，你的图像应该像图 8-9 一样。

![](img/f5bc249660e63bd0b6a2dc95983edb7_136_0.png)

黄色点光的蝴蝶

## Spot

`Spot` 接受与 `Point` 相同的参数，增加了 `SpecularExponent`（高光指数）。`SpecularExponent` 控制光束的聚焦，就像某些手电筒一样。然而，`Spot` 还增加了其他属性来引导光指向的方向。新属性是 `pointsAtX`、`pointsAtY` 和 `pointsAtZ`。

下面的 `applyEffects()` 方法将为蝴蝶应用 `Spot` 光效果。注意添加的三个属性并不是构造函数的一部分。

```java
private void applyEffects(ImageView imageView) {
    Lighting lighting = new Lighting();
    Light.Spot spot = new Light.Spot(150, 50, 50, 1, Color.WHITE);
    spot.setPointsAtX(400);
    spot.setPointsAtY(400);
    spot.setPointsAtZ(-10);
    lighting.setLight(spot);
    imageView.setEffect(lighting);
}
```

编译你的程序：图像将像图 8-10 所示。接下来，你将学习 `SepiaTone` 效果。

## SepiaTone

`SepiaTone` 效果旨在模拟旧银版摄影（Daguerretype）胶片的外观。早期胶片用深褐色（Sepia）染色以给打印件添加颜色。这个过程可以通过 `SepiaTone` 效果模拟，它接受一个 `level` 参数来调整应用于节点上的效果量。`level` 可以是 0 到 1 之间的值。

![](img/f5bc249660e63bd0b6a2dc95983edb7_137_0.png)

应用了 `Spot` 光的蝴蝶

# 第 8 章：应用效果与变换

查看以下完整的 `.java` 代码：

```java
package javafx.application.Application;

import javafx.scene.Scene;
import javafx.scene.effect.SepiaTone;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter8 extends Application {

    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Image image = new Image("http://jfarzio.com/butterfly.png");
        ImageView imageView = new ImageView();
        imageView.setImage(image);
        applyEffects(imageView);
        StackPane root = new StackPane();
        root.getChildren().add(imageView);
        primaryStage.setScene(new Scene(root, 800, 600));
        primaryStage.show();
    }

    private void applyEffects(ImageView imageView) {
        SepiaTone sepia = new SepiaTone();
        sepia.setLevel(1);
        imageView.setEffect(sepia);
    }
}
```

此代码显示了图 8-11。在下一节中，你将学习变换以及它们与效果的区别。

![](img/f5bc249660e63bd0b6a2dc95983edb7_139_png)

应用了深褐色调的蝴蝶

## 变换

变换并不改变效果的做法。变换是仿射的（意味着直线保持不变），并且可以用于平移、旋转、缩放或扭斜。

# 第 8 章：应用效果与变换

## XY 变换

在这一节你一直在处理平移。查看以下代码，它沿着 x 轴移动了 50 像素，沿着 y 轴移动了 50 像素：

```java
public void start(Stage primaryStage) {
    Image image = new Image("http://jfarzio.com/butterfly.png");
    ImageView imageView = new ImageView();
    imageView.setImage(image);
    applyEffects(imageView);
    StackPane root = new StackPane();
    root.getChildren().add(imageView);
    primaryStage.setScene(new Scene(root, 800, 600));
    primaryStage.show();
}

private void applyEffects(ImageView imageView) {
    imageView.setTranslateX(-50);
    imageView.setTranslateY(-50);
}
```

`ImageView` 拥有 `translateX` 和 `translateY` 属性。图 8-12 显示了这一点。

![](img/f5bc249660e63bd0b6a2dc95983edb7_141_png)

平移的蝴蝶

## 旋转

旋转 `ImageView` 就如绕轴旋转一样简单。`ImageView` 有一个名为 `rotate` 的属性。只需将 `ImageView` 的 `rotate` 属性设置为你想旋转的角度数即可。例如，查看以下代码，它将蝴蝶旋转 45 度。结果如图 8-13 所示。

```java
public void start(Stage primaryStage) {
    Image image = new Image("http://jfarzio.com/butterfly.png");
    ImageView imageView = new ImageView();
    imageView.setImage(image);
    applyEffects(imageView);
    StackPane root = new StackPane();
    root.getChildren().add(imageView);
    primaryStage.setScene(new Scene(root, 800, 600));
```



```java
primaryStage.show();
}

private void applyEffects(ImageView imageView) {
  imageView.setRotate(45);
}
```

![](img/f5bc249660e63bd0b6a2dc95983edb7_142_png)

旋转 45 度的蝴蝶

# 透视变换

接下来，你将学习 `PerspectiveTransform`——它是效果包中的一个成员，用于变换节点的透视。该变换是一种非仿射变换，可以将任意四边形映射到另一个任意四边形，同时保持直线的直性。与仿射变换不同，源行的平行性在输出中并不一定能保持。这是通过让你控制节点每个角的 x 和 y 坐标来实现的。

```java
private void applyEffects(ImageView imageView) {
    PerspectiveTransform transform = new PerspectiveTransform();
    transform.setLlx(100);
    transform.setLly(350);
    transform.setLrx(400);
    transform.setLry(550);
    transform.setUlx(100);
    transform.setUly(100);
    transform.setUrx(400);
    transform.setUry(100);
    imageView.setEffect(transform);
}
```

在这个示例中，每个顶角的坐标都已设置好。在使用 `PerspectiveTransform` 时，获得所需的效果需要一些练习，因此你可能想要尝试不同的坐标。前面的代码生成了图 8-14 所示的结果。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_143_0.png)

图 8-14 使用 PerspectiveTransform 的蝴蝶

## 第 8 章：应用效果和变换

### 尝试：组合多种效果

“好东西再多也不过分”这句话对于 JavaFX 效果来说尤为真实。在处理图像时，很少只需要应用一种效果。通常，你需要对图像应用多种效果以获得理想的视觉效果。

利用你在本章中学的技能，创建一个包含图像的新项目。同时对同一图像应用多种效果，并调整这些效果的属性以创建新颖且令人兴奋的图像。

效果和变换章节到此结束。在下一章中，你将开始处理一些基础动画。

## 第 8 章自测

1. 在 JavaFX 中使用效果需要包含哪个包？
2. 哪种效果只调整节点的高对比度区域使其发光？
3. 对或错？如果未指定，`ColorAdjust` 的所有参数默认值均为 0。
4. 创建 `GaussianBlur` 效果需要指定哪个参数？
5. `Glow`（发光）和 `Bloom`（光溢）之间有什么区别？
6. 对或错？对于 `DropShadow` 效果，不需要同时指定半径和高度/宽度？
7. 哪种效果提取图像中的所有不透明区域并使其透明？
8. `Lighting` 效果中可以使用哪三种不同的光？
9. 以下代码的作用是什么？

```java
imageView.setRotate(45);
```

10. 创建 `PerspectiveTransform` 效果需要设置多少参数？

![](img/f5bc6249660e63bd0b6a2dc95983edb7_146_0.png)

# 第 9 章：基础动画

## 关键技能与概念

- 使用 Timelines（时间线）
- 创建路径（Paths）
- 使用 KeyFrames（关键帧）和 KeyValues（关键值）

本章向你介绍 JavaFX 基础动画的世界。无论你是想创建动画文本和飞入效果，还是为创建游戏积累知识，基础动画都是很好的起点。

在处理基础 JavaFX 动画时，你需要掌握三个基础主题：

- Timelines
- KeyFrames 和 KeyValues
- Paths

开始本章之前，打开 NetBeans 并创建一个名为 `Chapter9` 的空 JavaFX 应用程序。根据之前的章节，在移除 "Hello World" 代码后，`Chapter9.java` 文件的内容如下：

```java
package Chapter9;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter9 extends Application {
    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        StackPane root = new StackPane();
        primaryStage.setScene(new Scene(root, 600, 480));
        primaryStage.show();
    }
}
```

## Timelines

所有的动画，无论是“传统的”手绘动画还是基于计算机的动画，都由时机控制。发生什么动作以及何时发生、从房间一侧走到另一侧所需的时间，以及对话与角色口型动作同步，都是由某种节奏感控制的动作。动画的时机决定了每个动作何时开始、何时结束以及持续多久。

在 JavaFX 中，动画可以是在屏幕上移动对象，也可以是如鼠标上按钮上的高亮显示，或者菜单中面板的展开。

时机对于平滑动画至关重要。如果每个动画帧之间时间太长，在用户看来就会很缓慢且卡顿；如果每帧之间时间太短，动画就会太快。这就是为什么时机至关重要的原因。

在 JavaFX 中，动画的时机由 `Timeline` 控制。`Timeline` 接受一组 `KeyFrames` 和 `KeyValues` 来随着时间修改应用程序的属性。定义 JavaFX `Timeline` 的类是 `javafx.animation.Timeline`。

`Timeline` 的作用是通过时间将动画帧分解为“停止点”。这意味着如果你告诉 `Timeline` 你希望一个对象在 1 秒后和 5 秒后变化，`Timeline` 将负责产生一组平滑递增的值，你可以将其应用到对象上。这现在听起来可能有点困惑，但当你看到 `Timeline` 运行起来时，就会变得非常清晰。

```java
import javafx.scene.image.ImageView;
import javafx.stage.Stage;
import javafx.util.Duration;
```

```java
/**
 * @author J F DiMarzio
 */
```

```java
public class Chapter9 extends Application {
  /**
   * @param args the command line arguments
   */
  public static void main(String[] args) {
    launch(args);
  }

  @Override
  public void start(Stage primaryStage) {
    ImageView imageView = new ImageView();
    Image ball = new Image("http://jfdmarzio.com/ball.png");
    imageView.setImage(ball);
    primaryStage.setHeight(480);
    primaryStage.setWidth(600);
    Group group = new Group();
    Scene scene = new Scene(group);
    group.getChildren().add(imageView);
    primaryStage.setScene(scene);
    primaryStage.show();

    Timeline timeline = new Timeline();
    KeyValue keyValue = new KeyValue(imageView.translateYProperty(), 370);
    KeyFrame frame = new KeyFrame(Duration.seconds(2), keyValue);
    timeline.getKeyFrames().add(frame);
    timeline.play();
  }
}
```

运行此程序，你将看到球体从屏幕顶部移动到底部。这种过程对于简单的运动很有用，但如果你想以更复杂的方式移动球呢？本章的下一节将介绍如何沿着路径制作图像动画。

## 沿路径动画

如果你想进行大量的数学计算——以及一些复杂的计算——可以使用上一节中解释的动画样式创建许多运动。然而，如果你真的想做一些复杂的动画，例如让对象在屏幕上沿曲线运动，你将使用路径动画。这是 JavaFX 创建动画的另一种方法，允许你沿着预定义的路径移动对象。在本节中，你将学习如何利用之前章节中学到的知识创建一个路径，然后使用该路径来对球进行动画。

这里的概念是你可以使用线条、弧和点来创建一个路径。JavaFX 将让你的图像沿着这条路径移动。开始之前，如所示设置你的 `Chapter9.java` 文件：

```java
package Chapter9;

import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter9 extends Application {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        ImageView imageView = new ImageView();
        Image ball = new Image("http://jfdimarzio.com/ball.png");
        imageView.setImage(ball);
        primaryStage.setHeight(480);
        primaryStage.setWidth(600);
        Group group = new Group();
        Scene scene = new Scene(group);
        group.getChildren().add(imageView);
        primaryStage.setScene(scene);
        primaryStage.show();
    }
}
```

与你之前看到的类似，这段代码获取了你一直在使用的同一个球体图像并创建一个组。在上一节中，你向这段代码中添加了 `Timeline` 来让球体图像在 y 轴上上下移动。在这个示例中，你将制作球围绕一个抽象路径移动的动画。

下一步是创建你想让球体图像沿运行的路径。你使用 `Path` 节点，它接受一个元素集合来创建路径。你可以轻松地创建一个元素组，构成一个抽象形状的路径。下面的代码定义了一个包含一些基础线条形状的小型元素数组：

```java
Path path = new Path();
ArcTo arc1 = new ArcTo();
ArcTo arc2 = new ArcTo();

arc1.setX(350);
arc1.setY(350);
arc1.setRadiusX(150);
arc1.setRadiusY(300);

arc2.setX(150);
arc2.setY(250);
arc2.setRadiusX(150);
arc2.setRadiusY(300);

path.getElements().addAll(new MoveTo(150f, 150f), arc1, arc2);
```

这里发生的事情并没有复杂或棘手的地方。你创建了一个元素集合并将其添加到 `Path` 中。`Path` 包含的元素是 `MoveTo` 和两个 `ArcTo` 实例。这些元素的组合创建了一个球可以遵循的路径。

`MoveTo` 元素的作用正如其名：它将你移动到笛卡尔网格上的特定点。在这种情况下，它将你移动到 x150, y150。你将其指定为第一个元素，以便在开始“绘图”之前干净地移动路径的起点。

接下来的两个元素绘制弧。第一个 `ArcTo` 元素从路径的最后位置绘制一个弧。第二个 `ArcTo` 从末端开始绘制另一个弧。

完整的路径动画代码如下：

```java
import javafx.animation.PathTransition;
import javafx.animation.PathTransition.OrientationType;
import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.shape.ArcTo;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.Path;
import javafx.stage.Stage;
import javafx.util.Duration;

public class Chapter9 extends Application {
    @Override
    public void start(Stage primaryStage) {
        ImageView imageView = new ImageView();
        Image ball = new Image("http://jfdimarzio.com/ball.png");
        imageView.setImage(ball);

        Path path = new Path();
        ArcTo arc1 = new ArcTo();
        arc1.setX(350);
        arc1.setY(350);
        arc1.setRadiusX(150);
        arc1.setRadiusY(300);

        ArcTo arc2 = new ArcTo();
        arc2.setX(150);
        arc2.setY(250);
        arc2.setRadiusX(150);
        arc2.setRadiusY(300);

        path.getElements().addAll(new MoveTo(150f, 150f), arc1, arc2);

        PathTransition pathTransition = new PathTransition();
        pathTransition.setDuration(Duration.seconds(4));
        pathTransition.setPath(path);
        pathTransition.setNode(imageView);
        pathTransition.setOrientation(OrientationType.ORTHOGONAL_TO_TANGENT);
        pathTransition.setCycleCount(PathTransition.INDEFINITE);
        pathTransition.setAutoReverse(true);
        pathTransition.play();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```



编译并运行前面的代码。你将看到小球沿椭圆路径动画的图像。

## 创建路径动画

在之前的章节中，“尝试一试”部分侧重于介绍可能未在章节中直接涵盖的功能。然而，本章涵盖的技能非常重要，因此本部分将重点关注增强这些技能。

创建一个新项目并向其添加一个图像或形状。然后，尝试创建一个路径并在其上对图像进行动画。尝试不同大小和长度的路径。调整 `Timeline` 的速度以改变动画的感受。

你对 JavaFX 动画能力越熟悉，你的应用程序就会越出色。

## 第 9 章自测

1. 为什么时机对动画很重要？
2. 什么控制着 JavaFX 动画中的计时器？
3. 正确还是错误？`Timeline` 包含一个 `KeyFrames` 的子集合。
4. 你如何启动 `Timeline`？
5. 正确还是错误？关键帧（`keyframe`）是你想要定义一个或多个键值（`keyvalues`）的节点。
6. `Animation` 的哪个属性设置了 `Timeline` 执行的次数？
7. `ArcTo` 的目的是什么？
8. 路径是由什么组创建的？
9. 使用哪个构建器类从路径创建动画？
10. 哪个 `PathTransition.OrientationType` 会在节点沿路径移动时改变其方向？

![](img/f5bc6249660e63bd0b6a2dc95983edb7_158_0.png)

## 第 10 章

## 使用事件

## 关键技能与概念

- 响应鼠标事件
- 使用匿名内部类
- 捕获键事件

本章为你介绍 JavaFX 事件。在处理事件时所需的概念对于制作丰富的交互式应用程序非常关键。事件允许你的应用程序响应用户的操作。

## 什么是事件？

事件提供在 JavaFX 中与用户交互的方法。作为开发者，你可以使用许多类型的事件使用户能够与你的环境交互并做出反应。事件可以由于用户以某种方式与你的环境交互而触发，你可以为这些事件注册监听器，并使用与事件相关的数据编写操作。

在本章中，你将发现并利用两组常见的事件：鼠标事件和键盘事件。

## 鼠标事件

鼠标事件是任何指针样式输入操作的通用术语。此类输入的提供者不非得是物理鼠标。任何在环境中移动指针的设备都会产生鼠标事件。鼠标、手写笔、轨迹球、触控板或任何导航工具在你的 JavaFX 环境中移动指针时，都会产生鼠标事件。

以下是生成鼠标事件的 `EventHandler` 类型属性列表：

- `onMouseClicked`
- `onPressed`
- `onMouseReleased`
- `onDragged`
- `onDragEntered`
- `onMouseDragExited`
- `onMouseDragOver`
- `onMouseDragReleased`
- `onMouseEnter`
- `onMouseExited`
- `onMouseMoved`

虽然这些操作中的某些命名可能足够描述性，足以让你判断出它们在监听什么操作，但某些操作名称相似且令人混淆。因此，在我们深入围绕它们构建代码之前，让我们通过描述每个操作是什么来消除任何困惑：

- `onMouseClicked`：如果检测到完整的鼠标点击（用户按下并释放鼠标按钮），则使用此属性。
- `onMousePressed`：当用户按下鼠标按钮时使用此属性。与 `onClick` 不同，用户不需要释放按钮即可触发此事件。
- `onMouseReleased`：用于 `onClick` 事件的后半部分。当鼠标按钮被释放时使用此属性。
- `onMouseDrag*`：当按下鼠标按钮并移动鼠标时使用这些属性。鼠标拖拽相关的事件对象包含了鼠标的 x 和 y 位置。
- `onMouseEnter`：当鼠标指针进入事件所附的节点时使用此属性。
- `onMouseExited`：当鼠标指针离开事件所附的节点时使用此属性。
- `onMouseMoved`：当鼠标在给定节点的边界内移动时使用此属性。

JavaFX 将 `onMouseReleased` 事件的完成识别为鼠标点击事件的逻辑结束。然而，如果你在按下鼠标按钮和释放按钮之间移动鼠标（即执行了有意的或无意的鼠标拖拽），将按顺序触发以下事件：

- Mouse pressed
- Mouse dragged
- Mouse released

在这种情况下，**不会**触发鼠标点击事件。

注意，“鼠标点击（`mouse clicked`）”是一个特定的事件，它封装了连续的鼠标按下和鼠标释放事件。如果在“鼠标按下”和“鼠标释放”之间触发了任何事件，该操作将不再被视为鼠标点击事件。

那么，为什么鼠标按下在两种情况下仍然会触发呢？JavaFX 预测鼠标按下事件后会发生什么。在操作完成之前，它无法确定该操作是鼠标点击事件还是鼠标释放事件；因此，`onMouseClicked` 始终会触发。

现在你已经理解了每个事件在何时触发，让我们讨论一下如何注册它们。这里的逻辑是，当 `onMouseClicked` 被触发时——即当用户在圆形节点范围内按下鼠标按钮时——事件被捕获并写入标签的文本中。为圆形节点的 `onMouseClicked` 事件复制相同的匿名类。你完成的代码应该像所示：

```java
package Chapter10;

import javafx.application.Application;
import javafx.event.EventHandler;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.input.MouseEvent;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter10 extends Application {

    /**
     * @param args command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Group group = new Group();
        Scene scene = new Scene(group);
        primaryStage.setHeight(350);
        primaryStage.setWidth(350);

        Circle circle = new Circle();
        final Label label = new Label();
        circle.setCenterX(150);
        circle.setCenterY(150);
        circle.setRadius(50);
        circle.setFill(Color.BLUE);

        circle.setOnPressed(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg) {
                label.setText(arg.toString());
            }
        });

        circle.setOnMouseClicked(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg) {
                label.setText(arg.toString());
            }
        });

        label.setText("Test");
        group.getChildren().add(circle);
        group.getChildren().add(label);
        primaryStage.setScene(scene);
        primaryStage.show();
    }
}
```

编译并运行代码。你将在屏幕上看到一个如图 10-1 所示的蓝色圆圈。

现在，将鼠标移动到圆圈内点击鼠标键。这将触发圆圈的 `onMousePressed` 事件并在屏幕上写入以下信息：

```
MouseEvent [source = Circle@10fe9e3, target = Circle@10fe9e3, eventType = MOUSE_PRESSED, consumed = false, x = 163.0, y = 171.0, button = PRIMARY, primaryStageDown]
```

在不移动的情况下释放鼠标键。你应该看到以下信息：

```
MouseEvent [source = Circle@10fe9e3, target = Circle@10fe9e3, eventType = MOUSE_CLICKED, consumed = false, x = 163.0, y = 171.0, button = PRIMARY]
```

这表明 `onMouseClicked` 事件已触发。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_165_0.png)

图 10-1 一个蓝色圆圈

尝试将剩余的鼠标事件添加到应用程序中（如下所示）并测试不同的场景。你应该看到大量非常有用的信息，你可以在应用程序中对其进行操作。

```java
package Chapter10;

import javafx.application.Application;
import javafx.event.EventHandler;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.input.MouseEvent;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter10 extends Application {

    /**
     * @param args command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Group group = new Group();
        Scene scene = new Scene(group);
        primaryStage.setHeight(350);
        primaryStage.setWidth(350);

        Circle circle = new Circle();
        final Label label = new Label();

        circle.setCenterX(150);
        circle.setCenterY(150);
        circle.setRadius(50);
        circle.setFill(Color.BLUE);

        circle.setOnMousePressed(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg) {
                label.setText(arg.toString());
            }
        });

        circle.setOnMouseClicked(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseDragEntered(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseDragExited(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseDragOver(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseDragReleased(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseDragged(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseEntered(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseExited(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseMoved(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        circle.setOnMouseReleased(new EventHandler<MouseEvent>() {
            @Override
            public void handle(MouseEvent arg0) {
                label.setText(arg0.toString());
            }
        });

        group.getChildren().add(circle);
        group.getChildren().add(label);
        primaryStage.setScene(scene);
        primaryStage.show();
    }
}
```

应用编译并运行后，点击圆形，然后按下键盘上的数字 2。你应该能看到以下内容（如果你缩放了窗口大小）：

```
KeyEvent[source = Circle@1f77d1c, target = Circle@1f77d1c, eventType = KEY_PRESSED, consumed = false, character = , text = 2, code = DIGIT2]

KeyEvent[source = Circle@1f77d1c, target = Circle@1f77d1c, eventType = KEY_TYPED, consumed = false, character = 2, text = , code = UNDEFINED]

KeyEvent[source = Circle@914cd55, target = Circle@914cd55, eventType = KEY_RELEASED, consumed = false, character = , text = 2, code = DIGIT2]
```

注意 `KeyEvent` 的 `character` 属性。该属性仅对 `KeyTyped` 可用。因此，如果你仅使用 `character` 属性，你只会在 `KeyTyped` 中看到它。现在在模拟器中按下上箭头并比较输出：



KeyEvent[source = Circle@914cd55, target = Circle@914cd55, eventType = KEY_PRESSED, consumed = false, character = , text = , code = UP]

KeyEvent[source = Circle@914cd55, target = Circle@914cd55, eventType = KEY_RELEASED, consumed = false, character = , text = , code = UP]

注意，方向箭头不会在 `KeyTyped` 事件上触发。它们只会在 `keyPressed` 和 `keyReleased` 事件上触发。

```
System.out.println(arg0.toString())
```

注意哪些事件被触发以及触发顺序非常重要。当你尝试处理用户输入时，这会让你的工作变得更容易。

# 问专家

Q：Mouse 和 onKey 事件的重要性是什么？

答：使用本章描述的事件是让用户与应用程序交互的最佳方式之一。你不可避免需要创建一个某种程度用户交互的应用。能够对 `onMouse` 和 `onKey` 做出反应是你从用户那里收集信息的强大工具之一。

## 第 10 章自测

- 1. 对或错？`onMouse*` 属性是 Node 类的属性。
- 2. `onMouseEnter` 何时触发？
- 3. 对或错？当拖动鼠标时，将调用鼠标释放的监听器方法。
- 4. 对或错？任何继承自 Node 的类都可以为鼠标事件注册监听器。
- 5. 当使用事件时，匿名内部类的目的是什么？
- 6. 当鼠标指针离开监听器所在的节点时，会调用哪个鼠标事件监听器？
- 7. 当用户与键盘交互时，会调用哪三个事件监听器方法？
- 8. 键事件监听器方法按什么顺序被调用？
- 9. 哪个属性允许节点接受焦点？
- 10. 对或错？导航按钮将触发 `KeyErrorTyped` 事件。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_174_0.png)

# 第 11 章：自定义节点与子类化

## 核心技能与概念

- 子类化 Node
- 创建自定义节点
- 重写默认的 Node 方法

FX 带有许多出色的工具。在整本书中，你学习了形状、效果和方法——这仅是部分。然而，如果你发现 JavaFX 中的节点并不完全符合你的需求怎么办？还有另一种方法从 JavaFX 中获取你需要的内容：你始终可以创建一个完全符合你需求的节点。这可以通过对现有节点进行子类化或创建一个完全全新的节点来实现。在本章中，你将学习这两种从 JavaFX 中获取精确所需内容的方法。首先，让我们讨论对现有节点进行子类化。

## 子类化 Node

在学习重写 Node 方法之前，需要回答一个关键问题：什么是重写？
类（例如 `Node` 和 `Button`）包含方法和属性。作为开发者，你可以获取这些方法并将它们的默认操作更改为你任何想要的操作。例如，假设你有一个 `Dog` 类，其中包含名为 `displayBreed()` 的方法，如下：

```java
public class Dog {
    public void displayBreed() {
        System.out.println("Chihuahua");
    }
}
```

你可以扩展此类并重写 `displayBreed()` 方法以输出不同的内容，如下：

```java
public class MyDog extends Dog {
    @Override
    public void displayBreed() {
        System.out.println("Elkhound");
    }
}

public class YourDog extends Dog {
}
```

在这里，调用 `Dog.displayBreed()` 会打印行“Chihuahua”。调用 `YourDog.displayBreed()` 也会打印“Chihuahua”。但是，由于 `MyDog` 重写了 `displayBreed()` 方法，调用 `MyDog.getBreed()` 将打印“Elkhound”。

通过重写，你可以创建具有新功能或扩展功能的节点。在接下来的章节中，你可以创建具有新功能或扩展功能的节点。

为了准备此练习，请创建 Chapter11：

```java
package chapter11;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;
import javafx.scene.shape.Circle;

/**
 * @author OCRprocessor
 */
public class Chapter11 extends Application {
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        StackPane root = new StackPane();
        primaryStage.setTitle("Chapter 11");
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

## 创建节点

现在创建 Chapter11: RoundButton 接口：

```java
package chapter11;

/**
 * @author OCRprocessor
 */
public interface RoundButton {
    public final int PLUS = 1;
    public final int MINUS = 2;
    void setLayout(int type);
}
```

第一步是让 RoundButton 成为一个按钮。如下：

```java
package chapter11;

/**
 * @author OCRprocessor
 */
public class RoundButton extends javafx.scene.control.Button implements RoundButton {
}
```

## 注意

此时，假设你正在使用 NetBeans，IDE 会提示你需要添加 RoundButton 的方法。让 NetBeans 为你实现 `setLayout()` 方法；否则你需要自己实现。

如果你在这里就停止，你将拥有一个名为 RoundButton 的功能完整的按钮。你可以像使用其他按钮一样在应用程序中使用它。但在这里停止并不会给你真正的圆形按钮。你拥只是 Button 的副本。

这个按钮之所以只需要很少的代码就能工作，是因为你告诉它扩展 Button 的功能到 RoundButton。因此，Button 的所有方法和属性现在都是 RoundButton 的一部分。在当前状态下，圆形按钮看起来用起来和 Button 完全一样。

然而，在这个示例中，你想创建一个圆形的按钮。因此，你需要在 RoundButton 类中添加代码使按钮变为圆形。这是通过设置 Button 的 `clip` 属性实现的。

要重写 `setLayout` 方法，添加以下代码将按钮的裁剪区域设置为圆形：

```java
@Override
public void setLayout(int type) {
    Circle roundButtonClip = new Circle();
    roundButtonClip.centerX(18);
    roundButtonClip.centerY(12);
    roundButtonClip.setRadius(8);
    this.setClip(roundButtonClip);
}
```

接下来，添加一个快速的 `if` 语句来判断按钮是类型 1 还是 2。此此目的是让用户选择按钮文本应该是 + 还是 -。

```java
@Override
public void setType(int type) {
    Circle roundButtonClip = new Circle();
    roundButtonClip.setCenterX(18);
    roundButtonClip.setCenterY(18);
    roundButtonClip.setRadius(8);
    this.setClip(roundButtonClip);
    if (type == 1) {
        this.setText(" +");
    } else {
        this.setText(" -");
    }
}
```

完成后的类看起来如下：

```java
package javafx.scene.shape.Circle;

/**
 * @author J F DiMarzio
 */
public final class RoundButton extends javafx.scene.control.Button implements RoundButtonAPI {
    @Override
    public void setType(int type) {
        Circle roundButtonClip = new Circle();
        roundButtonClip.setCenterX(18);
        roundButtonClip.setCenterY(18);
        roundButtonClip.setRadius(8);
        this.setClip(roundButtonClip);
        if (type == 1) {
            this.setText(" +");
        } else {
            this.setText(" -");
        }
    }

    public RoundButton() {
    }
}
```

```java
public RoundButton(int type) {
    this.setType(type);
}
```

与你在书中书中构建的其他示例不同，你现在无法直接编译并运行这个类。你现在拥有的是一个可以从另一个应用程序调用的类。你可以在 `Chapter11.java` 中添加一些代码并使用你的新按钮。`Chapter11.java` 文件目前应该如下：

```java
package Chapter11;
```

```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;
```

```java
/**
 * @author J F DiMarzio
 */
public class Chapter11 extends Application {
```

```java
/**
 * @param args the command line arguments
 */
public static void main(String[] args) {
    launch(args);
}
```

```java
@Override
public void start(Stage primaryStage) {
    StackPane root = new StackPane();
```

```java
    primaryStage.setScene(new Scene(root, 300, 250));
    primaryStage.show();
}
```

现在你只需要在内容的 `start()` 方法中调用你的新 `RoundButton` 即可。这非常简单。你可以像调用任何其他节点一样调用 `RoundButton`。记得向构造函数传递按钮类型：

```java
RoundButton btn = new RoundButton(RoundButton.PLUS);
```

# 164 JavaFX 快速上手指南

这将创建一个带有 `+` 文本的圆形按钮。完整的 `Chapter11.java` 如下：

```java
package Chapter11;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter11 extends Application {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        RoundButton btn = new RoundButton(RoundButton.PLUS);
        StackPane root = new StackPane();
        root.getChildren().add(btn);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

## 注意

某些节点（包括此 `RoundButton` 在内）在 Mac 和 PC 上的渲染方式不同。在将你的结果与本章中的图片进行比较时，请考虑这一点。

编译并运行此应用程序。你将看到一个与图 11-1 类似的圆形按钮。

为了查看通过对现有节点子类化来创建自己的节点的优点之一，请看一个 `buttonType` 为 0 的第二个按钮，如下。注意 `StackPane` 已被替换为 `HBox`。这将允许你将按钮并排放置，而不是重叠在一起。

# 第 11 章：自定义节点与子类化 165

![](img/f5bc6249660e63bd0b6a2dc95983edb7_182_0.png)

图 11-1 一个 RoundButton

```java
package Chapter11;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.HBox;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter11 extends Application {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        RoundButton btn = new RoundButton(RoundButton.PLUS);
        RoundButton btn2 = new RoundButton(RoundButton.MINUS);
        HBox root = new HBox();
        root.getChildren().add(btn);
        root.getChildren().add(btn2);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

![](img/f5bc6249660e63bd0b6a2dc95983edb7_182_0.png)

图 11-2 一个 RoundButton

编译并运行此应用程序。你将看到一个与图 11-1 类似的圆形按钮。

为了查看通过对现有节点子类化来创建自己的优点之一，请看一个 `buttonType` 为 0 的第二个按钮，如下。注意 `StackPane` 已被替换为 `HBox`。这将允许你将按钮并排放置，而不是重叠在一起。

# 第 11 章：自定义节点与子类化

1. 继承另一个类的过程是什么？
2. 在示例示例，`YourDog` 会打印什么？

```java
public class YourDog extends Dog {
    @Override
    public void displayBreed() {
```



System.out.println("Elound");

}

}

```

3. 将文件在同一个包内。
4. 继承另一个的过程被称为子类化。
5. 你使用哪个关键字来实现接口？
6. 你像实例化标准节点一样实例化自定义节点吗？
7. `HBox` 的目的是什么？
8. 什么以 `@` 开头的注解可以用于更改继承方法的功能？
9. 为你的类创建 API 接口是一个很好的做法。
10. 某些节点（包括此 `RoundButton` 在内）在 Mac 和 PC 上的渲染方式不同。在将你的结果与本章中的图片进行比较时，请考虑这一点。

# 第 11 章：自定义节点与子类化

## 技能与概念
- 渲染 HTML
- JavaScript 与 JavaFX 之间的通信

随着围绕流媒体的业务和网站日益丰富，JavaFX 允许你充分利用嵌入视频和音频是自然的。在过去，编写播放任何媒体的应用程序意味着编写控件、为要的文件寻找正确的解码器并编写读取媒体文件的解析器。这是一项艰巨的工作，只有在你对自己的能力完全自信时才会尝试。

与其要求你通过 JavaFX 直接链接要流的媒体，有一个更健壮的解决方案在等待你。JavaFX 包含了 `WebView`。JavaFX WebView 基于无处不在的开源 WebKit——允许显示 HTML5、CSS 和 JavaScript。

在本章的第一部分，你将学习使用 WebView 渲染 HTML。然而，在开始之前，你需要创建一个名为 `Chapter 12` 的新 JavaFX 项目。你的脚本应该如下：

```java
package chapter12;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter12 extends Application {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }
}
```

# 第 12 章：使用 WebView

```java
@Override
public void start(Stage primaryStage) {
}
```

你还需要创建一个名为 `HTMLoader` 的第二个空 Java 类。该类将包含 WebView 的设置。在整个章节中，你将不断向这个第二个文件中添加内容。将文件命名为 `HTMLoader.class` 并按照如下方式进行设置：

```java
package chapter12;

/**
 * @author J F DiMarzio
 */
public class HTMLoader extends Region {
}
```

让我们为 `HTMLoader` 添加一些代码来显示网页。

# 渲染 HTML

`WebView` 节点基于开源的 WebKit 架构。你可以轻松地在 JavaFX 应用程序中使用 `WebView` 来渲染 HTML。本节的示例将在 `WebView` 中渲染一个网站。

> 提示
> 注意 `HTMLoader` 类继承自 `Region`。继承 `Region` 允许我们的类包含子节点并对这些节点应用 CSS 样式。

让我们先实例化 `WebView` 和 `WebEngine`。`WebEngine` 允许你管理 `WebView`。你将使用 `WebEngine` 来应用样式表、指向网页，并在 JavaScript 和 Java 之间提供通信路径（在书的后续章节）。

向你的 `HTMLoader` 类导入以下包：

```java
import javafx.scene.web.WebEngine;
import javafx.scene.web.WebView;
```

接下来，实例化 `WebView` 和 `WebEngine`：

```java
public class HTMLoader extends Region {
    final WebView browser = new WebView();
    final WebEngine webEngine = browser.getEngine();
    // ...
}
```

`HTMLoader` 的其余工作将在构造函数中完成。为 `HTMLoader` 类创建一个构造函数：

```java
public HTMLLoader() {
}
```

在构造函数中，使用 `WebEngine` 的 `load()` 方法加载 jfdimarzio.com 网站。然后，使用 `HTMLoader` 的 `getChildren().add()` 方法将 `WebView` 添加到 `HTMLoader`/`Region`：

```java
public HTMLLoader() {
    webEngine.load("http://jfdimarzio.com");
    getChildren().add(browser);
}
```

实例化一个 `HTMLoader` 并将其添加到你的 `Scene` 中：

```java
public void start(Stage primaryStage) {
    primaryStage.setTitle("WebView");
    Scene scene;
    scene = new Scene(new HTMLoader(), 800, 600);
    primaryStage.setScene(scene);
    primaryStage.show();
}
```

编译并运行本章的代码，你应该能看到一个渲染了网页的 JavaFX 应用程序，如图 12-1 所示。

## JavaScript 与 JavaFX 之间的通信

在上一节中，你使用了 `WebEngine` 来管理 `WebView`。`WebEngine` 还可以执行其他功能。`WebEngine` 能够执行的最有用功能之一是促进 JavaScript 和 JavaFX 之间的通信。

这并不是说 `WebEngine` 可以在不受防备的页面上任意执行 JavaScript。相反，`WebEngine` 可用于增强页面上的现有功能。例如，可以使用 `WebEngine` 对页面执行 JavaScript。这本身并不非常令人兴奋。然而，`WebEngine` 也促进了相反的行为——你可以从 JavaScript 通信到 JavaFX。

# 第 12 章：...使用 WebView 173

![](img/f5bc6249660e63bd0b6a2dc95983edb7_190_0.png)

图 12-1 渲染网页

首先，让我们检查 JavaFX 到 JavaScript 的通信。取一个简单的 HTML 页面，其中包含一个 JavaScript 函数，如 jfdimarzio.com/test.html 所示，显示如下：

```html
<!DOCTYPE html>
<html>
<head>
<script>
function displayJavaFX() {
  document.getElementById("javafx").innerHTML='JavaFX to ;';
}
</script>
</head>
<body>
<h1>Chapter 12</h1>
<p id="javafx"></p>
<p>JavaScript communication</p>
<p><button type="button" onclick="displayJavaFX()">Show Text</button></p>
</body>
</html>
```

# JavaScript 通信

Show Text

图 12-2 JavaScript 执行前的演示页面

此页面显示文本 "JavaScript communication" 和一个标记为 "Show Text" 的按钮，如图 12-2 所示。

如果你点击 "Show Text" 按钮，它会触发 `displayJavaFX()` 函数并显示文本 "JavaFX to,"，如图 12-3 所示。

使用 `WebEngine`，你可以在 `WebView` 中加载 jdimarzio.com/test.html 页面并执行 `showJavaScript()` 函数——而无需点击页面上的按钮。第一步是使用 `WebEngine` 将页面加载到 `WebView` 中。修改 `HTMLLoader` 以显示页面：

```java
webEngine.load("http://jdimarzio.com/test.html");
```

在执行 JavaScript 之前，必须确保页面已由 `WebView` 完全加载。幸运得好，你恰好为此目的调用了一个监听器：

```java
webEngine.getLoadWorker().stateProperty().addListener(
    new ChangeNotifier<State>() {
        @Override
        public void changed(ObservableValue<? extends State> ov,
            State oldState, State newState) {
            if (newState == State.SUCCEEDED) {
                // ...
            }
        }
    });
```

# JavaScript 通信

JavaFX to

Show Text

图 12-3 JavaScript 执行后的演示页面

# 第 12 章：使用 WebView

在上一节中，你使用了 `WebEngine` 来管理 `WebView`。`WebEngine` 还可以执行其他功能。`WebEngine` 能够执行的最有用功能之一是促进 JavaScript 和 JavaFX 之间的通信。

这并不是说 `WebEngine` 可以在不受防备的页面上任意执行 JavaScript。相反，`WebEngine` 可用于增强页面上的现有功能。例如，可以使用 `WebEngine` 对页面执行 JavaScript。这本身并不非常令人兴奋。然而，`WebEngine` 也促进了相反的行为——你可以从 JavaScript 通信到 JavaFX。

> 提示：请记住，使用此方法时你不需要了解 `alert()` 的内容或目的。任何执行 `alert()` 的页面都会被此监听器拦截。

```java
webEngine.setOnAlert(new EventHandler<WebEvent<String>>() {
    @Override
    public void handle(WebEvent<String> arg0) {
        lblHello.setText(arg0.getData());
    }
});
```

编译并运行新代码，你应该能在屏幕底部的工具栏中看到 alert 的结果，如图 12-5 所示。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_195_0.png)

图 12-5 JavaScript 到 JavaFX 通信的结果 own

## 第 12 章自测

- 1. 在 JavaFX 应用中使用哪种节点来持有或渲染网页？
- 2. 哪些包包含了与 `WebView` 和 `WebEngine` 工作所需的节点？
- 3. `WebEngine` 的哪个方法用于将网页加载到 `WebView` 中？
- 4. 正确或错误？JavaFX 内部禁止 JavaScript 到 JavaFX 的通信。
- 5. 使用什么方法针对已加载到 `WebView` 的页面执行 JavaScript？

# 第 13 章

使用 CSS 为你的 JavaFX 样式样式化

## 核心技能与概念

- 将 CSS 文件添加到你的程序包中
- 使用 CSS 类
- 访问 Node 属性

在本章中，你将学习如何使用级联样式表（CSS）来轻松地更改 JavaFX 应用的外观和感受。如果你不完全了解什么是 CSS，这个非常快速的复习将对你有帮助。

CSS 是一种样式语言，允许你将对象的样式元素与对象本身分离。尽管 CSS 的创建时间远早于 JavaFX，但 JavaFX 已经包含了使用这种样式语言的能力。事实上，JavaFX CSS 是基于 W3C 2.1 CSS 标准的。这意味着你可以创建所有对象（或 JavaFX 中的节点），而无需担心它们的布局、外观或感受。你所做的只是定义节点的功能。然后，在节点的 style 属性中或在单独的文件中，你可以定义更改节点外观和感受的样式。

这里你应该注意的 CSS 的重要特性是，你所有的 CSS 样式都可以包含在一个与 java 文件分离的文件中。将你的代码和 .css 文件分离，允许你更改样式——甚至是整个整个的外观和感受——而无需更改或重新编译应用程序。这对你意味着什么？你可以通过修改 .css 文件来更改你设计的应用程序的外观和感受，而不触动你的应用程序代码。

# 专家问

问：JavaFX 中使用的 CSS 与网页上使用的 CSS 之间有区别吗？

答：有区别。JavaFX 支持新的 JavaFX 特有元素。目前尚不清楚 JavaFX 未来将支持多少标准 CSS 元素（如果支持的话）。

# 第 13 章：使用 CSS 为你的 JavaFX 样式化 183

本章的剩余部分将教你如何在应用程序中利用这个非常有用的工具。在开始之前，请设置一个名为 `Chapter13` 的新空 JavaFX 应用，如下所示：

```java
package chapter13;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.scene.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter13 extends Application {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        StackPane root = new StackPane();
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

在本章的第一节中，你将学习如何将样式表添加到你的 JavaFX 程序包中供脚本使用。

# 将样式表添加到你的程序包中

第一步是从 NetBeans 的项目视图（位于 IDE 的左侧）右键点击你的程序包名称。从右键菜单中选择 New | Other，这将打开新文件向导（见图 13-1）。

在向导中，你希望从 Categories（类别）区域选择 Other，然后在 File Types（文件类型）区域选择 Cascading Style Sheet（级联样式表），如图 13-2 所示。

# 184 JavaFX 快速入门指南

![](img/f5bc6249660e63bd0b6a2dc95983edb7_201_0.png)

**图 13-1** 从上下文菜单中选择 New | Other 的结果

最后，点击 Next 按钮，将文件命名为 **default**，然后点击 Finish 按钮，如图 13-3 所示。

现在你的程序包文件列表中有一个名为 `default.css` 的文件。如果还没有打开，请打开你的样式表。它应该显示如下：

```css
/*
Document      : default
Created on     : Oct 13, 2012, 11:48:53 AM
Author         : J F DiMarzio
Description   :
    样式表的目的。
*/

root {
    display: block;
}
```

# 第 13 章：... 使用 CSS 为你的 JavaFX 样式化

![](img/f5bc6249660e63bd0b6a2dc95983edb7_202_0.png)

图 13-2 选择级联样式表

> 提示：请记住，使用此方法时你不需要了解 `alert()` 的内容或目的。本章的目的并不是教你 CSS 语言。相反，你只是在学习如何在 JavaFX 使用 CSS。如果你需要关于 CSS 以及如何使用 CSS 属性的更多说明，请在本章之前尝试使用许多在线资源。

将样式表插入你的程序包后，你可以使用此样式更改 `Label` 的字体。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_203_0.png)

## 创建样式

JavaFX 将自动识别以节点命名的任何样式类。例如，如果你想创建一个适用于所有 label 的样式类，创建一个名为 `.label` 的样式类。让我们创建这个样式类。

更改字体颜色的 Node 属性是 `textFill`。要从 CSS 访问此属性，你需要添加 `-fx-` 作为前缀。因此，样式声明如下：

```css
.label {
  -fx-text-fill: red;
}
```



# 第 13 章：使用 CSS 为你的 JavaFX 样式化

此样式声明任何 `Label` 节点的 `TextFill` 属性都将设置为红色。让我们为 `Label` 节点再创建一个声明，然后你就可以将此样式表应用到脚本。

要更改 `Label` 节点的字体，使用 `-fx-font` 样式，如下：

```css
.label {
  -fx-text-fill: red;
}
```

总之，此样式将所有 label 的字体更改为红色、粗体、14 磅 Courier。完整的 CSS 文件看起来如下：

```css
/*
Document      : default
Created on    : Oct 13, 2012, 11:48:53 AM
Author        : J F DiMarzio
Description:
  样式表的目的如下所示。
*/

root {
  display: block;
}

.label {
  -fx-text-fill: red;
  -fx-font: bold 14pt "Courier";
}
```

```java
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;
```

```java
/**
 *
 * @author J F DiMarzio
 */
```

```java
public class Chapter13 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        StackPane root = new StackPane();
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

要在此脚本中使用样式表，你需要将其应用到根节点。根节点有一个名为 `Stylesheets` 的属性。注意该属性名称是复数形式。这是因为你可以向单个项目应用多个样式表。

使用属性的 get 方法（getter）和设置方法（setter）来添加样式表，如下：

```java
root.getStylesheets().add(Chapter13.class.getResource("default.css").toExternalForm());
```

现在，为场景添加一个 `Label` 节点：

```java
package chapter13;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;
```

```java
/**
 *
 * @author J F DiMarzio
 */
```

```java
public class Chapter13 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Label label = new Label();
        label.setText("This is a test");
        StackPane root = new StackPane();
        root.getChildren().add(label);
        root.getStylesheets().add(chapter13.Chapter13.class
            .getResource("default.css").toExternalForm());
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

注意，在代码中你并没有以任何方式修改 `Label` 节点。通常情况下，这将导致具有标准黑色字体的标签。然而，字体最终将变为红色、**加粗**并使用 Courier 字体，因为你应用了 `default.css` 文件。

编译并运行此应用。你将看到类似于图 13-4 所示的结果。在本章的最后章节中，你将学习如何创建可以独立于节点应用的样式类。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_206_0.png)

图 13-4 应用了样式的 Label

# 创建独立的样式类

再次打开 `default.css` 文件。你将向此文件添加一个样式类，该类可以应用于任何节点，无论其类型如何。也就是说，你之前创建的样式只能应用于所有的标签，而现在你将创建一个可以应用于你所希望的任何节点的样式类。

让我们创建一个让任何节点旋转 90 度的类。在你的 `default.css` 文件中添加以下类：

```css
.rotate {
    -fx-rotate: 90;
}
```

注意这里，旋转节点的 `Node` 属性被称为 `rotate`。因此，该样式的表声明为 `-fx-rotate`。你的完整 `default.css` 现在应该看起来像这样：

```css
/*
Document : default
Created on : Oct 13, 2012, 11:48:53 AM
Author : J F DiMarzio
Description:
    样式表的目的见下文。
*/

root {
    display: block;
}

label {
    -fx-text-fill: red;
    -fx-font: bold 14pt "Courier";
}

.rotate {
    -fx-rotate: 90;
}
```

现在你需要修改 `Chapter13.java` 来使用这个新类。你创建的 `.rotate` 类是一个独立的类，如果你想使用它，就需要显式地调用它——不像 `.label` 类，后者会内生地应用于所有标签。节点的 `StyleClass` 属性允许你指定当前样式表中的你想应用于该节点的类。修改你 `Chapter13.java` 文件中的 `Label` 代码，包含对 `StyleClass` 属性 getter 和 setter 的调用：

```java
package chapter13;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Label;
```

```java
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;
```

```java
/**
 *
 * @author J F DiMarzio
 */
public class Chapter13 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        Label label = new Label();
        label.setText("This is a test");
        label.getStyleClass().add("rotate");
        StackPane root = new StackPane();
        root.getChildren().add(label);
        root.getStylesheets().add(chapter13.Chapter13.class.getResource("default.css").toExternalForm());
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

使用新的 `default.css` 编译并运行此应用。你将看到标签文本发生了变化，如图 13-5 所示。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_208_0.png)

图 13-5 应用了 .rotate 类的 Label

# 尝试：实验

对样式和节点进行实验。使用本章涵盖的示例，创建一个可以改变节点位置或颜色的样式类。

# 第 13 章自测

1. 什么是层级样式表 (CSS)？
2. 层级样式表使用什么文件扩展名？
3. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。
4. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。
5. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。
6. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。
7. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。
8. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。
9. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。
10. 在本章的最后章节，你将学习如何创建可以独立于节点应用的样式类。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_210_0.png)

# 第 14 章：嵌入媒体

## 关键技能与概念

- 向应用添加视频
- 反向绑定
- 使用 `MediaPlayer`

在后续章节中，你将学习如何向应用添加视频和音频文件。

## 播放

在后续章节中，你将学习如何向应用添加视频和音频文件。

# 专家问答

问：`MediaPlayer` 可以播放什么类型的文件？

答：简短的回答是，如果该文件被 Mac 上的 QuickTime 或 Windows 上的 Media Player 支持，那么 `MediaPlayer` 节点就能处理它。具体支持的文件格式包括 MP3、MP4 和 FLV。

要逻辑化地命名所有内容，并将所有相关类放在公共包中。`javafx.scene.media` 包也不例外。

在你的 `MediaView` 文件中导入以下类：

```java
import javafx.scene.media.MediaPlayer;
```

为什么要费力多此一个步骤来对 `MediaPlayer` 进行子类化？虽然你可以直接将 `MediaPlayer` 添加到 `MediaView` 中并完成任务，但默认的 `MediaPlayer` 是非常简单的。随着你对本章内容的学习，你将为 `MediaView` 添加功能，以扩展 `MediaPlayer` 的可用性。

现在，你将设置一个默认的 `MediaPlayer`，只需展示加载和播放视频文件是多么简单：

```java
private MediaPlayer _player;
```

你需要的第二个东西是一个 `Media` 对象。`Media` 对象代表了使用 `MediaPlayer` 播放的媒体源。在这个示例中，你将硬编码一个从 Oracle 网站流出的示例视频文件。这节省了你不断分配该属性的精力。

要使用 `Media` 类，请包含以下导入语句：

```java
import javafx.scene.media.Media;
```

然后添加代码来创建 `Media` 类：

```java
private Media _media;
```

接下来，为 `MediaView` 创建一个空构造函数：

```java
package Chapter14;

import javafx.scene.media.Media;
import javafx.scene.media.MediaPlayer;
```

```java
/**
 * @author J F DiMarzio
 */
public class MyMediaView extends javafx.scene.media.MediaView {

    private MediaPlayer _player;
    private Media _media;

    public MyMediaView() {
    }
}
```

在构造函数内部，你需要实例化 `Media`，然后使用你想播放的 `Media` 实例化 `MediaPlayer`：

```java
_media = new Media("http://download.oracle.com/" + "otdocs/products/javafx/oow2010-2.flv");
_player = new MediaPlayer(_media);
```

你在这里需要设置 `MediaPlayer` 的两个属性。第一个是 `autoPlay` 属性。将 `autoPlay` 设置为 `true` 将告诉媒体文件在没有用户干预的情况下播放。第二个属性是 `cycleCount`，它告诉 `MediaPlayer` 播放当前 `Media` 的次数。

```java
_player.setAutoPlay(true);
_player.setCycleCount(MediaPlayer.INDEFINITE);
```

最后，设置 `MediaView` 使用新的 `MediaPlayer`，这样你就准备好开始播放了：

```java
this.setMediaPlayer(_player);
```

已完成的 `MyMediaView` 类如下：

```java
package Chapter14;

import javafx.scene.media.Media;
import javafx.scene.media.MediaPlayer;

/**
 * @author J F DiMarzio
 */
public class MyMediaView extends MediaView {

    private MediaPlayer _player;
    private Media _media;

    public MyMediaView() {
        _media = new Media("http://download.oracle.com/otndocs/products/javafx/oow2010-2.flv");
        _player = new MediaPlayer(_media);
        _player.setAutoPlay(true);
        _player.setCycleCount(MediaPlayer.INDEFINITE);
        this.setMediaPlayer(_player);
    }
}
```

现在你可以使用 `MyMediaView` 在你的应用中流传输此视频。让我们如下为第 14 章添加一个 `MyMediaView`：

```java
package Chapter14;

import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter14 extends Application {

    /**



# 第 14 章：嵌入媒体

这段代码非常自言自会。你正在创建一个 `MyMediaView`（你在本节之前创建的 MediaPlayer），并将其放置在你的 `Scene` 中。

编译并运行此示例。一旦应用程序加载，你将看到一个示例视频开始播放。文件会自动播放，是因为你将 `autoPlay` 属性设置为 `true`。

如果你更仔细地观察视频播放，可能会发现它非常简单：没有播放和暂停视频的控制控件。也没有指示视频进度的控制控件，或者允许用户跳过视频的控件。简而言之，播放窗口中没有任何控制控件。

为了让用户能够控制视频的播放，你将自己编写控制控件。在本节的剩余部分中，你将在 `MediaPlayer` 上编写一些控件并将它们展示给用户。

## 提示

由于你考虑得周全并且已经创建了自定义的 `MediaPlayer`，创建控制控件的过程将简单得多。

让我们创建一个快速按钮来控制视频的播放。

## 创建播放/暂停按钮

在本节中，你将使用在本节之前创建的 `MediaPlayer` 创建一个播放/暂停按钮。如果你需要了解 `RoundButton` 的工作原理，请参考第 11 章。

接下来，让我们更改 `MediaView` 中的一个设置。将 `autoplay` 属性从 `true` 改为 `false`，如下所示。这会让视频在点击将添加的播放按钮之前不播放。

```java
package Chapter14;

import javafx.scene.media.Media;
import javafx.scene.media.MediaPlayer;
```

```java
/**
 * @author J F DiMarzio
 */
public class MyMediaView extends MediaView {

    private MediaPlayer _player;
    private Media _media = new Media("http://download.oracle.com/otndocs/products/javafx/oow2010-2.flv");

    public MyMediaView() {
        _player = new MediaPlayer(_media);
        _player.setCycleCount(MediaPlayer.INDEFINITE);
        this.setMediaPlayer(_player);
    }
}
```

现在按钮已经就绪，我们需要一种方法让它连接到 `MediaView`。`play()` 和 `pause()` 方法包含在 `MediaPlayer` 中；但是，你的 `MediaView` 继承自 `MediaView`，后者只是一个容器。那么，如何控制播放呢？简单。你将创建一个新的接口，允许你的 `MediaView` 暴露 MediaPlayer 的 `play()` 和 `pause()` 方法。

你在第 11 章为 `RoundButton` 创建了一个接口。为此项目创建一个名为 `MyMediaViewAPI` 的新接口。该接口有两个方法：`playMedia()` 和 `pauseMedia()`，如下：

```java
package Chapter14;

/**
 * @author J F DiMarzio
 */
public interface MyMediaViewAPI {

    public void playMedia();

    public void pauseMedia();
}
```

现在，修改 `MyMediaView` 类使其实现新的 `MyMediaViewAPI`。当你这样做时，NetBeans 应该添加这两个方法的重写（override）。

```java
/**
 * @author J F DiMarzio
 */
public class MyMediaView extends javafx.scene.media.MediaView implements MyMediaViewAPI {

    private MediaPlayer _player;
    private Media _media = new Media("http://download.oracle.com/otndocs/products/javafx/oow2010-2.flv");

    public MyMediaView() {
        _player = new MediaPlayer(_media);
        _player.setAutoPlay(false);
        _player.setCycleCount(javafx.scene.media.MediaPlayer.INDEFINITE);
        this.setMediaPlayer(_player);
    }

    @Override
    public void playMedia() {
    }

    @Override
    public void pauseMedia() {
    }
}
```

在 `MyMediaView` 的 `playMedia()` 和 `pauseMedia()` 方法中分别调用 `MediaPlayer` 的 `play()` 和 `pause()` 方法：

```java
@Override
public void playMedia() {
    _player.play();
}

@Override
public void pauseMedia() {
    _player.pause();
}
```

你可以直接从应用中调用 `MyMediaView` 的 `playMedia()` 和 `pauseMedia()` 方法来控制文件的播放。
在你的 `Chapter14.java` 中添加两个 `RoundButton`——一个用于播放，一个用于暂停：

```java
package Chapter14;

import javafx.application.Application;
import javafx.scene.Group;
```

```java
import javafx.scene.Scene;
import javafx.scene.layout.HBox;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter14 extends Application {

    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        final MyMediaPlayer mp = new MyMediaPlayer();
        RoundButton play = new RoundButton(RoundButtonAPI.PLAY);
        RoundButton pause = new RoundButton(RoundButtonAPI.PAUSE);
        HBox hBox = new HBox();
        hBox.getChildren().add(play);
        hBox.getChildren().add(pause);
        Group root = new Group();
        root.getChildren().add(mp);
        primaryStage.setScene(new Scene(root, 540, 209));
        primaryStage.show();
    }
}
```

最后一步是添加两个处理器（每个 `RoundButton` 一个），它们将调用 `MyMediaPlayer` 的相应方法——`playMedia()` 或 `pauseMedia()`：

```java
play.setOnAction(new EventHandler<ActionEvent>() {
    @Override
    public void handle(ActionEvent event) {
        mp.playMedia();
    }
});

pause.setOnAction(new EventHandler<ActionEvent>() {
    @Override
    public void handle(ActionEvent event) {
        mp.pauseMedia();
    }
});
```

`Chapter14.java` 应用的完整代码应该如下：

```java
package Chapter14;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.layout.HBox;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter14 extends Application {

    /**
     * @param args 命令行参数
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        final MyMediaPlayer mp = new MyMediaPlayer();
        RoundedButton play = new RoundedButton(RoundedAPI.PLAY);
        RoundedButton pause = new RoundedButton(RoundedAPI.PAUSE);

        play.setOnAction(new EventHandler<ActionEvent>() {
            @Override
            public void handle(ActionEvent event) {
                mp.playMedia();
            }
        });

        pause.setOnAction(new EventHandler<ActionEvent>() {
            @Override
            public void handle(ActionEvent event) {
                mp.pauseMedia();
            }
        });

        HBox hBox = new HBox();
        hBox.getChildren().add(play);
        hBox.getChildren().add(pause);

        Group root = new Group();
        root.getChildren().add(mp);

        primaryStage.setScene(new Scene(root, 540, 209));
        primaryStage.show();
    }
}
```

## JavaFX 快速上手指南

现在让我们设置 `Slider`（滑动块）的初始参数。最大值（Max，条上的最高值）、最小值（Min，条上的最低值）以及值（Value，滑动块的当前位置）。

考虑到视频在用户点击按钮之前不会开始播放，你可以在此按钮的事件处理器中设置这些初始值。

```java
play.setOnAction(new EventHandler<ActionEvent>() {
    @Override
    public void handle(ActionEvent event) {
        mp.playMedia();
        progressBar.setMax(mp.getTotalTime());
        progressBar.setMin(0);
        progressBar.setValue(mp.getCurrentTime());
    }
});
```

这是复杂的部分。你需要为 `progressBar` 编写一个监听器，每当移动滑动块时，它就会触发。然后，它将使用 `setCurrentTime()` 方法将 `progressBar` 的当前值写入 `MyMediaView`，以便用户手动快进或后退视频。

为 `progressBar` 的 `valueProperty()` 属性添加一个监听器。这将允许你在通过移动滑动块改变值时执行代码。

```java
progressBar.valueProperty().addListener(new InvalidationListener() {
    @Override
    public void invalidated(Observable arg0) {
        if (progressBar.isValueChanging()) {
            mp.setCurrentTime(progressBar.getValue());
        }
    }
});
```

最后，你需要为 `MyMediaView` 添加一种更新 `progressBar` 上滑动块位置的方法。这可以通过另一个属性监听器来实现。这次，你将监听 `MediaPlayer` 的 `currentTime` 变化。当 `currentTime` 改变时，你想更新 `progressBar` 的值，从而在视频播放时让滑动块向前移动。

```java
mp.getMediaPlayer().currentTimeProperty()
    .addListener(new InvalidationListener() {
        @Override
        public void invalidated(Observable arg0) {
            progressBar.setValue(mp.getCurrentTime().toMillis());
        }
    });
```

你现在拥有了获取和设置视频当前播放时间所需的数值。
完整的 `Chapter14.java` 文件现在应该是这样的：

```java
package Chapter14;

import javafx.application.Application;
import javafx.beans.InvalidationListener;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Slider;
import javafx.scene.layout.HBox;
import javafx.stage.Stage;

/**
 * @author J F DiMarzio
 */
public class Chapter14 extends Application {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        final Slider progressBar = new Slider();
        final MyMediaView mp = new MyMediaView();
    }
}
```



```java
RoundButton play = new RoundButton(RoundButtonAPI.PLAY);

RoundButton pause = new RoundButton(RoundButtonAPI.PAUSE);

play.setOnAction(new EventHandler<ActionEvent>() {

    @Override
    public void handle(ActionEvent event) {
        mp.playMedia();
        progressBar.setMax(mp.getTotalRunTime());
        progressBar.setMin(0);
        progressBar.setValue(mp.getCurrentTime());
    }
});

pause.setOnAction(new EventHandler<ActionEvent>() {

    @Override
    public void handle(ActionEvent event) {
        mp.pauseMedia();
    }
});

progressBar.valueProperty().addListener(new InvalidationListener() {

    @Override
    public void invalidated(javafx.beans.Observable arg0) {
        if (progressBar.isValueChanging()) {
            mp.setCurrentTime(progressBar.getValue());
        }
    }
});

mp.getMediaPlayer().currentTimeProperty().addListener(new InvalidationListener() {

    @Override
    public void invalidated(javafx.beans.Observable arg0) {
        progressBar.setValue(mp.getCurrentTime());
    }
});

HBox hBox = new HBox();
hBox.getChildren().add(play);
hBox.getChildren().add(pause);
hBox.getChildren().add(progressBar);

Group root = new Group();
root.getChildren().add(hBox);

primaryStage.setScene(new Scene(root, 540, 209));
primaryStage.show();
}
}
```

编译并运行这些类。你现在已经获取和设置视频当前播放时间所需的数值。你现在有了一个播放/暂停按钮以及一个允许用户更改视频当前位置的进度条。

在本书的最后一个章节中，你将学习使用 CSS 为 UI 增加更多个性化。

## 第 14 章自测

- 哪个节点被用于持有 `MediaPlayer`？
- 哪个包包含了处理媒体文件所需的节点？
- `MediaPlayer` 的哪个属性在加载后会指示关联媒体对象播放？
- `MediaPlayer` 可以播放哪些媒体格式？
- `MediaPlayer` 的哪个方法可以暂停媒体播放？
- 正确或错误？`MediaPlayer.mediaLength()` 将给出总运行时间。
- `MediaPlayer.currentTime` 是什么类型？
- 你可以绑定到 `MediaPlayer` 的哪个属性来控制音量？

# 附录 A：JavaFX 的打包与部署

本书的大部分内容都在介绍 JavaFX 的基础。你已经学习了如何使用 JavaFX API 并创建了一些应用程序。在本章中，你将学习如何部署你创建的应用程序。

## JavaFX 打包工具

在本书中你创建了可以在 NetBeans 中运行的应用程序，但仍然有一个待解决的问题：你需要部署这些应用程序以便他人执行。

## 注意

在示例中，你将使用 `Chapter12.java`。

```html
{
  javafx : '2.0+'
},
{
  return false;
}
</script>
```

```html
<script>
function javafxEmbed() {
  dtjava.embed({
    url : 'Chapter12.jnlp',
    placeholder : 'javafx-app-placeholder',
    width : 800,
    height : 600,
    jnlp_content : ''
    {
      javafx : '2.0+'
    }
  });
}
</script>
```

```html
<!-- 页面加载后，将 FX 应用程序嵌入网页中 -->
dtjava.addOnLoadCallback(javafxEmbed);
</script>
```

```html
<head><body>
<h2><b>第12章</b> 的测试页面</h2>h</h2>
<b>WebStart:</b><a href='Chapter12.jnlp' onclick="return launchApplication('Chapter12.jnlp');">点击以作为 webstart 启动此应用</a><br><br>
n
```

```html
<!-- Applet 将插入在此处 -->
<div id='javafx-app-placeholder'></div>
</body></html>
```

HTML 的脚本部分中有一段 JavaScript，它允许编译后的项目在打开此页面时运行。使用浏览器打开该 HTML 文件，你应该能看到如图 A-4 所示的功能完备应用程序。

在本附录中，你学习了如何编译和构建 `.java` 文件，以便它们能够在 NetBeans IDE 之外执行。如你所见，分发过程非常简单——这增加了 JavaFX 的易用性和易访问性。

## 附录 A：JavaFX 的打包与部署

![](img/f5bc6249660e63bd0b6a2dc95983edb7_234_0.png)

图 A-2 构建项目

![](img/f5bc6249660e63bd0b6a2dc95983edb7_234_1.png)

图 A-3 dist 文件夹

## 自包含应用程序包

部署 JavaFX 应用程序的第二方法是创建一个自包含的应用程序包，它是一个可执行文件（Windows 下为 `.exe`），包含了在目标平台上运行你的应用程序所需的所有文件。

这种部署方法的优点是，生成的包对于习惯于执行 Windows 应用程序的人来说，是一个熟悉的格式。如果你计划在以 Windows 应用程序为主的环境中部署你的应用程序，且用户习惯于安装和使用此类可执行包，那么这就是你应该使用的方法。

幸运的是，NetBeans 让创建自包含的应用程序包变得简单。在你的 NetBeans 项目目录中，你会找到一个 `build.xml` 文件。按照如下方式修改要部署的项目的 `build.xml` 中对应的 `<target name="post-jfx-deploy">` 标签：

```xml
<target name="post-jfx-deploy">
<fx:deploy width="${javafx.run.width}" height="${javafx.run.height}"
nativeBundles="all" />
```

![](img/f5bc6249660e63bd0b6a2dc95983edb7_235_0.png)

图 A-4 一个分发的应用

## 附录 A：JavaFX 21 的打包与部署

```xml
outfile="${basedir}/${dist.dir}"
<fx:application name="${application.title}"
      mainClass="${javafx.main.class}"/>
<fx:resources>
<fx:fileset dir="${basedir}/${dist.dir}"
      includes="*.jar"/>
</fx:resources>
<fx:info title="${application.title}"
      vendor="${application.vendor}"/>
</fx:deploy>
</target>
```

这些指令将生成一个 `.exe` 文件格式的自包含应用程序包。

## Web Start

JavaFX 提供了将应用程序部署为 Web Start 的选项，主要是为了保持与旧平台的兼容性。将应用程序部署为 Web Start 非常简单，点击一个选项即可完成。

在 NetBeans 中，右键点击项目并进入项目属性。在 Run 选项下，点击“Run: as Web Start”选项。现在，当应用程序被部署时，作为 Web Start 运行的代码将被添加到 dist 文件夹中的 `<application name>.html` 文件中。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_238_0.png)

# 附录 B

### Swing 的世界（The Swing of Things）

本书的大部分内容是 JavaFX 开发的基础知识。你已经学习了如何使用 JavaFX 并创建一些引人注目的应用程序。

诚然，你只接触了 JavaFX 所能提供的冰山一角，它是一门深度且丰富的语言。无疑，你对所学的一些内容可能还有疑问。这是三个附录中的第二个，旨在填补书中课程可能留下的空白。在本附录中，我们简要介绍 JavaFX 的基础知识以及与 Swing 的兼容性。

## JavaFX Swing 兼容性

JavaFX 8 为你提供了一种新的节点类型，用于 JavaFX 到 Swing 的兼容性。在以下代码中，`JFXPanel` 被放置在：

```java
final JFXPanel javafxPanel = new JFXPanel();
```

由于 `JFXPanel` 继承自 `JComponent`，因此它可以在任何地方使用。与 `SwingNode` 的关键在于 `getContent()` 方法一样，向 `JFXPanel` 添加 JavaFX 内容的关键在于 `setScene()` 方法：

```java
Scene myScene = createScene();
javafxPanel.setScene(myScene);
```



在前面的代码段中，`myScene` 可以像任何场景一样被添加。这允许 JavaFX 内容集成到你的 Swing 应用程序中。

![](img/f5bc6249660e63bd0b6a2dc95983edb7_242_0.png)

## 附录 B：Swing 的世界

## 附录 C：自测答案

### 第 3 章

- 1. MVC 模式的作用是什么？
  MVC 允许用户界面的设计和构建独立于控制它的逻辑。

- 2. 什么是 MVC 的全称？
  模型-视图-控制器（Model View Controller）。

- 3. 在 JavaFX 中，FXML 代表 MVC 的哪部分？
  视图（The View）。

- 4. 使用什么工具来编辑 FXML 文件？
  JavaFX Scene Builder。

- 5. JavaFX 中的绑定（binding）是指什么？
  绑定是一种概念，你可以通过这种方式链接属性和值，使属性随着值的变化而动态更新。

- 6. 对或错？绑定的语法是 `#{value}`。
  错误，绑定使用的语法是 `${value}`。

- 7. `$` 运算符在 JavaFX 中被称为什么？
  Java 变量解析（variable resolution）。

- 8. Java 中的方法（method）是指什么？
  Java 中的一个方法是一段代码，可以被其他代码段调用以执行特定的功能。

- 9. JavaFX 中的属性（property）是指什么？
  属性是一个键:值对（key:value pair），允许你存储和回溯一段数据。

- 10. 对或错？为了绑定到控制器（controller）上的属性，你必须告诉 FXML 你的属性在哪个文件中。
  正确，你需要指定属性在哪个文件中。

### 第 4 章

- 1. 哪种布局在场景（Scene）中水平组织你的节点？
  `HBox`。

- 2. 对或错？`HBox` 位于 `javafx.scene` 包中。
  错误。`HBox` 位于 `javafx.scene.layout` 包中。

- 3. 哪一个属性持有供布局组织的节点？
  `children`（子节点）。

- 4. 对或错？你必须确保设置放置在布局中的每个节点的 x- 和 y- 坐标。
  错误。布局会为你处理 x- 坐标和 y- 坐标。

- 5. 效果（effects）可以应用于布局上吗？
  可以。因为布局继承自 `Node`，它们可以使用效果。

- 6. 哪种布局在场景（Scene）中垂直组织节点？
  `VBox`。

- 7. 组合以产生新布局的布局名称是什么？
  嵌套布局（Nested layouts）。

- 8. 对或错？为了让布局嵌套，一个必须继承自另一个。
  错误。只需要将一个布局添加到另一个布局的内容中即可。

- 9. 对或错？只能嵌套两个布局。
  错误。可以嵌套多个布局。

- 10. 列举除 `VBox` 和 `HBox` 之外的三个布局。
  `FlowPane`、`StackPane` 和 `TilePane`。

### 第 5 章

- 1. 绘制线条需要哪些属性？
  `startX`, `startY`, `endX`, `endY`。

- 2. 如何访问菜单？
  `CTRL+SPACE`。

- 3. 在处理颜色时需要哪个包？
  `javafx.scene.paint`。

- 4. 哪个属性控制线条的厚度？
  `strokeWidth`。

- 5. 绘制折线（polyline）需要哪个包？
  `javafx.scene.shape`。

- 6. 折线（polyline）的属性是什么？
  数组（array）。

- 7. 填充颜色（fill）的默认值是什么？
  `BLACK`（黑色）。

- 8. 矩形（Rectangle）的属性是？
  `radius`（半径）。

- 9. 对或错？绑定到控制器上的属性需要指定哪个文件。
  正确。

- 10. 矩形（Rectangle）的属性是？
  `Color`（颜色）。

### 第 6 章

- 1. `Color` 类中有多少种预定义颜色？
  14种。

- 2. `Color` 类中有哪三种方法？
  `rgb`, `hsb` 和 `web`。

- 3. 对或错？未指定的参数默认为 0。
  错误。默认值为1。

- 4. 色相（Hue）的范围是？
  0–360。

- 5. 渐变（Gradients）在哪个包中？
  `javafx.scene.paint`。

- 6. 对或错？渐变参数可以包含多个停止点（stops）。
  正确。

- 7. 渐变的范围是？
  0–1。

- 8. 弧线形状（curvilinear shapes）使用的是？
  `ImageView`。

### 第 7 章

- 1. 哪个节点用于显示图像？
  `ImageView`。

- 2. 哪个类用于绘制图像？
  `ImageView`。

- 3. 对或错？渐变是由停止点（stops）组成的。
  正确。

- 4. 使用什么方法定位图像？
  `file`（文件）。

- 5. 对或错？为了有图像，需要设置为 true。
  错误。

- 6. 哪个方法允许在 x 轴上移动图像？
  `translateX()`。

- 7. 哪个类用于显示图像？
  `ImageView`。

- 8. 哪个节点用于显示图像？
  `ImageView`。

### 附录 C：自测答案

- 9. 对或错？鼠标松开监听器在鼠标拖动时调用。
  错误。鼠标松开只有在 `onPressed` 后接 `onDragged` 才会调用。

### 第 8 章

- 1. 使用效果需要包含哪个包？
  `javafx.scene.effect`。

- 2. 哪种效果调整对比度？
  `ColorAdjust`。

- 3. 对或错？未指定的参数默认为 0。
  错误。对比度默认为1。

- 4. 创建高斯模糊（GaussianBlur）需要哪个参数？
  `radius`。

- 5. 发光（Glow）和泛光（Bloom）的区别是什么？
  `Glow` 应用整个图像，而 `Bloom` 只应用于区域。

- 6. 对或错？阴影（DropShadow）需要同时指定半径和宽度。
  正确。

- 7. 哪种效果将所有不透明区域变为透明？
  `InvertMask`。

- 8. 光效果（Lighting Effect）可以使用哪三种光？
  `Distant`（远距离光）、`Point`（点光）和 `Spot`（聚光灯）。

- 9. 以下代码做了什么？
  ```
  imageView.setRotate(45);
  ```
  将图像旋转45度。

- 10. 创建 `PerspectiveTransform` 需要多少个参数？
  8个。

### 第 9 章

- 1. 为什么时间对动画很重要？
  时间对于平滑动画至关重要。

- 2. 什么控制计时器？
  `Timeline`。

- 3. 对或错？`Timeline` 包含关键帧（KeyFrames）集合。
  正确。

- 4. 如何启动 `Timeline`？
  使用 `.play()` 或 `playFromStart()`。

- 5. 对或错？关键帧（keyframe）是你将一个或多个键值（keyvalues）设置为定义值的点。
  正确。

- 6. `Animation` 的哪个属性设置执行次数？
  `cycleCount`。

- 7. `ArcTo` 的作用是什么？
  `ArcTo` 从点的最后一个位置绘制一个圆弧。

- 8. 路径是由一组什么创建的？
  `PathElements`。

- 9. 使用什么构建器类从路径创建动画？
  `PathTransitionBuilder()`。

- 10. 哪种 `PathTransition.OrientationType` 会在沿路径移动时改变节点的方向？
  `ORTHOGONAL_TO_TANGENT`。

### 第 10 章

- 1. 对或错？`onMouse*` 属性是 `Node` 类的属性。
  正确。

- 2. `onMouseClicked` 何时触发？
  当鼠标指针进入附加了事件监听器的 `Node` 时。

- 4. 正确或错误？任何继承自 `Node` 的类都可以注册鼠标事件监听器。
  正确。

- 5. 当使用事件时，匿名内部类的目的是什么？
  匿名内部类的目的是在事件触发时立即执行某个操作。

- 6. 当鼠标指针离开所绑定的事件监听器的节点时，会调用哪个鼠标事件监听器？
  `onMouseExited`。

- 7. 当用户与键盘交互时，会调用哪三个事件监听方法？
  `onKeyPressed`, `onKeyReleased` 和 `onKeyTyped`。

- 8. 事件监听器方法按什么顺序被调用？
  先调用 `onKeyTyped`，然后是 `onKeyReleased`。

- 9. 哪个属性允许节点接受焦点？
  `focusTraversable`。

- 10. 正确或错误？导航按钮将触发 `onTyped` 事件。
  正确。

### 第 11 章

- 1. 哪种过程允许你从一个类中获取方法并更改它们的默认行为？
  重写（Overriding）。

- 2. 在创建类时，使用哪个关键字强制你的类继承另一个类的方法和属性？
  `extends`。

- 3. 在以下示例中，调用 `YourDog.displayBreed()` 将打印什么？

```
public class MyDog extends Dog {

  @Override
  public void displayBreed() {
    System.out.println("Elkhound");
  }
}

public class YourDog extends Dog {
}
```



# JavaFX 快速入门指南

## 自测答案

### 第 4 章

- **4. 正确或错误？** 确保所有文件都在同一个包中会使引用它们变得更容易。
  **正确。**

- **5. 正确或错误？** 继承另一个类的过程被称为子类化（subclassing）。
  **正确。**

- **6. 使用哪个关键字来实现一个接口？**
  `implements`。

- **7. 正确或错误？** 实例化自定义节点的方法与实例化标准节点的方法相同？
  **正确。** 所有类/节点的实例化方式都是相同的。

- **8. `HBox` 的目的是什么？**
  `HBox` 的目的是自动水平布局节点。

- **9. 哪种以 `@` 开头的关键字注解可以更改被继承方法的默认功能？**
  `@Override`。

- **10. 正确或错误？** 为你的自定义类创建 API 接口是一种良好的编码规范。
  **正确。** 你应该尽可能遵循良好的编码实践。

### 第 12 章

- **1. 哪个节点用于在 JavaFX 应用中持有或渲染网页？**
  `WebView`。

- **2. 哪些包包含了处理 `WebView` 和 `WebEngine` 所需节点？**
  `javafx.scene.web`。

- **3. `WebEngine` 的哪个方法用于将网页加载到 `WebView` 中？**
  `load()`。

- **4. 正确或错误？** 在 Java 内部禁止 JavaScript 到 Java 的通信。
  **错误。**

- **5. 使用哪个方法针对加载到 `WebView` 的页面执行 JavaScript？**
  `executeScript()`。

### 第 13 章

- **1. 什么是级联样式表 (CSS)？**
  CSS 是一种样式语言，允许你将对象的样式元素与对象本身分离。

- **2. 级联样式表使用什么扩展名？**
  `.css`。

- **3. 哪个向导可以帮助你创建并将 CSS 添加到你的包中？**
  新文件向导（New File Wizard）。

- **4. 如果你使用向导创建 CSS，默认添加哪个类？**
  `root`。

- **5. 正确或错误？** 为了创建一个适用于特定类型所有节点的 CSS 类，该类的名称应为节点类型的小写名称。
  **正确。**

- **6. 每个 `Node` 属性前都添加了什么前缀以便从 CSS 类中调用它？**
  `-fx-`。

- **7. `Scene` 的哪个属性允许你为你的脚本应用样式表？**
  `styleSheets`。

- **8. 正确或错误？** 你只能向一个 `Scene` 添加一个样式表。
  **错误。** 你可以向任何特定的 `Scene` 添加多个样式表。

- **9. 哪个 `Node` 属性允许你为节点分配特定的 CSS 类？**
  `styleClass`。

- **10. 正确或错误？** 如果你有一个应用了节点层级 CSS 类且具有 `styleClass` 属性的节点，那么 `styleClass` 中的样式将覆盖节点应用样式中的样式。
  **正确。**

### 第 14 章

- **1. 哪个节点用于持有 `MediaPlayer`？**
  `MediaView`。

- **2. 哪个包包含了处理媒体文件所需的所有节点？**
  `javafx.scene.media`。

- **3. `MediaPlayer` 的哪个属性告诉关联的媒体对象在加载后播放？**
  `autoPlay`。

- **4. `MediaPlayer` 可以播放哪些媒体格式？**
  MP3, MP4 和 FLV。

- **5. `MediaPlayer` 的哪个方法会暂停媒体播放？**
  `pause()`。

- **6. 正确或错误？** `MediaPlayer.mediaLength()` 将给你媒体文件的总运行时间。
  **错误。** `MediaPlayer.media.duration.toMillis()` 将给出以毫秒为单位的运行时间。

- **7. `MediaPlayer.currentTime` 是什么类型？**
  `Duration`。

- **8. 在控制播放音量时，你可以绑定 `MediaPlayer` 的哪个属性？**
  `volume`。

---

## 索引

### 符号

- `@Override` 注解
- `-fx-` 前缀 (CSS)
- `.css` 扩展名
- `autoPlay` 属性 (`MediaPlayer`)
- `build.xml` 文件
- `Duration` 类型
- `executeScript()` 方法 (`WebEngine`)
- `HBox` 布局
- `implements` 关键字
- `javafx.scene.media` 包
- `javafx.scene.web` 包
- `load()` 方法 (`WebEngine`)
- `MediaView` 节点
- `pause()` 方法 (`MediaPlayer`)
- `root` 类 (CSS 默认)
- `styleClass` 属性 (`Node`)
- `styleSheets` 属性 (`Scene`)
- `subclassing` (子类化)
- `volume` 属性 (`MediaPlayer`)
- `WebView` 节点

### A

- `add()` 方法
  - `children`, 172
  - `points`, 63
- `alphaGradient`, 82–83
- `AnchorPane`
  - `elements`, 29
  - `lines`, 61
- `angles`
  - `arcs`, 70
  - `azimuth`, 117
  - `RadialGradients`, 86–87
  - `rotation`, 123
- `animation`
  - 概览, 130–131
  - 路径动画, 136–140
  - 时间线 (`timelines`), 131–135
- `anonymous inner classes` (匿名内部类), 146
- `Application` 类
  - 扩展 (`extending`), 20
  - 设置 (`setting`), 214
  - 入口点 (`entry points`), 20–21
  - 自包含 (`self-contained`), 218–219
- `applyEffects()` 方法
  - `Bloom`, 105
  - `ColorAdjust`, 108
  - 描述, 103
  - `Distant`, 117
  - `DropShadow`, 114
  - `GaussianBlur`, 109
  - `Glow`, 111–112
  - `PerspectiveTransform`, 125–126
  - `Point light`, 118
  - `Spot`, 119
- 应用级联样式表, 187–189
- `Arc` 属性, 71
- `ArcBuilder`, 72
- `arcHeight` 设置, 67
- `arcs` (弧形)
  - 动画, 137–138
  - 绘制, 69–72
  - 圆角矩形, 67
- `ArcTo()` 方法, 137–138
- `arcWidth` 设置, 67
- `arrays of colors` 用于 `LinearGradients`, 84
- `arrays of points` (点数组), 68
- `asterisks (*)` (星号)
  - 注释用, 18–19
  - 包用, 105
- `audio media` (音频媒体)
  - 相关类, 194–195
  - 嵌入式, 170
- `auto-start` for NetBeans, 6
- `AutoPlay` 设置, 197, 200
- `AutoReverse` 设置, 138
- `azimuth` 设置, 117

### B

- `ball animation` (球动画)
  - 编译, 13
- `bindings` (绑定)
  - 创建, 39–40
  - 概览, 33–35
- `Bloom effect` (绽放效果), 105–107
- `DropShadow` (投影), 113–114
- `GaussianBlur` (高斯模糊), 108–110
- `blurType` 设置, 113–114
- `borders` for nodes, 66
- `brightness` 设置
- `code` (代码)
  - 应用程序入口点, 20–21
  - 注释中, 17–19
  - 编译, 23
  - 语句, 19
  - 片段 (`snippets`), 16–17
- `code-behind` (代码隐藏), 22
- `codecs` (编解码器), 170
- `ColorAdjust`, 107
- `HSB` 颜色, 81–82
- `build.xml` file, 218
- `projects` (项目), 214–215
- `properties and methods` (属性和方法), 37–40
- `alpha` 设置, 82–83
- `Distant light` (远光), 117
- `DropShadow` (投影), 110
- `fonts` (字体), 186
- `HSB` 颜色, 81–82
- `LinearGradients` (线性渐变), 84
- `lines` (线条), 60–83
- `polygons` (多边形), 68
- `predefined colors` (预定义颜色), 78–80
- `rectangles` (矩形), 65–67
- `RGB` 颜色, 80–81
- `web` 颜色, 82
- `deleting` (删除), 30
- `Play/Pause` (播放/暂停), 199–205
- `RoundButton` (圆形按钮), 159–266
- `Canvas API`, 97–99
- `lines` (线条), 57
- `translations` (平移), 95

### C

- `Canvas API` (画布 API)
- `Cartesian coordinate system` (笛卡尔坐标系)
  - `lines` (线条), 57
  - `translations` (平移), 95
- `Cascading Style Sheets (CSS)` (层叠样式表)
  - 添加, 183–185
  - 描述, 3
  - 概览, 182–183
  - 样式应用, 187–189
  - 创建, 185–186
- `ColorAdjust effect` (颜色调整效果), 107–108
- `ColorAdjustBuilder`, 108
- 组合效果 (`combining effects`), 127
- `commas (,)` 用于数组, 63
- `comments` (注释) 选项
- `center points` for `arcs` (弧形中心点), 70–71
- `centerX` 设置
- `Cascading Style Sheets` (层叠样式表), 185
- JavaScript 与 JavaFX 通信, 172–178
- Swing 兼容性 (`compatibility of swing`), 222–223
- 编译应用程序 (`compiling applications`), 23
- 描述, 19
- `JAR files` (JAR 文件), 13
- `arcs` (弧形), 70
- `circles` (圆形), 73
- `centerY` 设置, 70
- `circles` (圆形), 73
- `child nodes` for `scene graphs` (场景图子节点), 34
- 配置 NetBeans, 239
- `defaults` (默认值)
  - `scene graphs` (场景图), 54
  - `Cascading Style Sheets` (层叠样式表), 190–191
  - 使用, 28–30
  - 新项目, 12
- `context menus` (上下文菜单), 57–58
- `degrees` (度数), 70–71
- `contrast` 设置, 107–108
- `color wheel` (色轮), 81
- 图像旋转 (`image rotation`), 95, 123, 125
- `properties` (属性), 40
- 部署 (`deploying`)
  - JavaFX Packager 工具, 214–216
- `controls` (控件)
  - JavaFX, 214
  - 绑定属性和值, 33–34
  - 自包含应用程序包, 218–219
  - 使用, 30–32
- `convenience methods` (便利方法), 146
- `dist folder` (dist 文件夹), 215
- `Distant` 类, 117
- `distributed applications` (分布式应用), 216, 218
- `coordinates` (坐标)
  - `lines` (线条), 57
- `dollar sign ($)` 运算符, 33
- `PerspectiveTransform` (透视变换), 124–125
- `JavaFX Scene Builder`, 27–28
- `Point light` (点光源), 118
- 所需软件 (`required software`), 5–7
- `polyline start points` (折线起点), 63
- `draw events` (绘制事件), 143
- `rectangles` (矩形), 65–66
- `drawing shapes` (绘制形状)
  - `translations` (平移), 95
  - `arcs` (弧形), 69–72
  - 注释中的版权信息, 18
  - `circles` (圆形), 72–74
- `Create File dialog` (创建文件对话框), 93
- `ellipses` (椭圆), 74
- `method` (方法)
  - `lines` (线条), 56–64
  - `ArcBuilder`, 72
  - 概览, 55–56
  - `ColorAdjustBuilder`, 108
  - `polygons` (多边形), 68–69
  - `LineBuilder`, 61
  - `rectangles` (矩形), 65–68
  - `PathTransitionBuilder`, 138
  - `DropShadow effect` (投影效果), 113–115
  - `RectangleBuilder`, 66
- 创建日期在注释中, 18

### D

- `degrees` (度数), 70–71
- `deploying` (部署), 214–216
- `DropShadow effect` (投影效果), 113–115

### E

- `end points` (端点)
  - `LinearGradients` (线性渐变), 83
  - `lines` (线条), 57
  - `polylines` (折线), 63
- `endX` 设置, 83
- `endY` 设置, 83
- `entered events` (进入事件), 143
- 转义字符 (`\`)
- `EventHandler for mouse events` (鼠标事件处理器), 142
- `events` (事件)
  - 用于 CSS 的 `-fx` 前缀, 186
- `FXML` 标记文件, 14, 21, 26
- 描述 (`description`), 142
- `key` (键) 事件, 151–154
- `mouse` (鼠标) 事件, 142–151
- 可执行应用程序, 编译, 33
- `executeScript()` 方法, 175–176
- `execution security` (执行安全性), 36
- `exiting mouse events` (退出鼠标事件), 143
- `explorers` (资源管理器), 15–16
- `ending classes` (结束类), 20
- `Gaussian algorithm` (高斯算法), 108
- `GaussianBlur` (高斯模糊), 108–110
- `getChildren()` 方法
  - `HTMLoader`, 172
  - `lines` (线条), 59
- `getCurrent()` 方法, 207
- `getDuration()` 方法, 207
- `getHelloMessage()` 方法, 38
- `getMediaPlayer()` 方法, 208
- `getPoints()` 方法, 63
- `getStylesheets` 方法, 188
- `getters for properties` (属性访问器), 37–38
- `getTotalRunningTime()` 方法, 207
- `Glow effect` (发光效果), 111–113
- `gradients` (渐变)

### F

- `custom` (自定义), 87–88
- `LinearGradients` (线性渐变), 83–86
- `RadialGradients` (径向渐变), 86–87
- `F6` 键, 23
- `files` (文件)
  - `Cascading Style Sheets` (层叠样式表), 182
  - `projects` (项目), 14
- `Files tab` (文件标签页), 15
- `graphics cards` (显卡), 4
- `GraphicsContext` (图形上下文), 97
- `GridPanes` (网格布局), 30–32
- `groups, nodes` (组、节点), 163
- `fill setting` (填充设置)
  - `arcs` (弧形), 71
  - `Cascading Style Sheets` (层叠样式表), 187
  - `color` (颜色), 80
  - `polygons` (多边形), 68
  - `rectangles` (矩形), 65–67
- `fillOval()` 方法, 98
- `FlowPane` 布局, 51
- `MediaPlayer` 对 `FLV` 文件的支持, 196
- `focus` (焦点)

### H

- `Halignment property` (水平对齐属性), 31
- `hardware requirements` (硬件要求), 4
- `HBox` 布局, 43–46
- `height` (高度)
  - `arcs` (弧形), 71
  - `DropShadow` (投影), 113
  - `images` (图像), 92
  - `rectangles` (矩形), 65–66
- 节点间的传递 (`passing between nodes`), 153
- `RadialGradients` (径向渐变), 86–87
- `FocusAngle` 设置, 86–87
- `FocusDistance` 设置, 87
- `focusTraversable` 设置, 153
- `Hgrow property` (Hgrow 属性), 31
- `Hierarchy view` (层级结构视图), 28–29
- `horizontal layout` (水平布局), 43–46
- `HSB` (色相、饱和度、亮度) 颜色, 81–82
- `hsb()` 方法, 80–82
- `HTML files` (HTML 文件)
  - 构建过程中, 215
  - 渲染 (`rendering`), 171–178
- `folders` (文件夹)
  - `images` (图像), 93
  - `packages` (包), 12
- `fonts` (字体), 186–187
- `.fx` 文件, 14

### I

- `HTMLoader` 类, 171–172
- `HSB` 颜色, 81–82
- `ColorAdjust` 的 `hue` 设置, 107
- CSS 中的连字符 (`-`), 186
- `javafx.scene.effect` 包, 105
- `javafx.scene.effect.light` 包, 116
- `JavaFX Graphics API` (JavaFX 图形 API), 54–55
- `javafx.scene.image.ImageView` 包, 90
- `javafx.scene.layout.HBox` 包, 44
- `javafx.scene.layout.VBox` 包, 47
- `javafx.scene.media` 包, 195–196
- `javafx.scene.media.MediaPlayer` 包, 196
- `javafx.scene.paint.Paint` 包, 83, 86
- `javafx.scene.paint.Color` 包, 60, 78, 117
- `javafx.scene.paint.LinearGradient` 包, 83
- `javafx.scene.paint.RadialGradient` 包, 86
- `javafx.scene.paint.Stop` 包, 84
- `javafx.scene.shape.ArcType` 包, 70
- `javafx.scene.shape.Circle` 包, 72
- `javafx.scene.shape.Line` 包, 57
- `javafx.scene.shape.Polyline` 包, 62
- `javafx.scene.shape.Rectangle` 包, 65
- `JavaFX Language` (JavaFX 语言), 3
- `JavaScript` 与 `JavaFX` 通信, 172–178
- `Component class` (组件类), 223
- `Image class` (图像类), 91–96
- `Canvas` (画布), 97–99
- `ImageView` 节点, 90–91
- `import statements` (导入语句)
  - `lines` (线条), 57
  - 目的 (`purpose`), 20
- `independent style classes` (独立样式类), 190–191
- `instance elements` (实例元素), 20
- `JavaFX Scene Builder`, 27–28
- 下载与安装, 27–28
- `JavaFX FXML Application` (JavaFX FXML 应用程序), 14
- `JavaFX Scene Builder`, 55
- `containers` (容器), 28–30
- `javafx.scene.control.Button` 包, 160
- `Cascading Style Sheets` (层叠样式表), 186–187
- `Text property` (Text 属性), 30
- `TextField property` (TextField 属性), 32
- `Layout pane` (布局面板), 30
- `miscellaneous` (杂项), 51
- `nested` (嵌套), 48–51

### L

- `layouts` (布局) (续)
  - 概览 (`overview`), 42–43
  - `VBox`, 47–48
- `leaf nodes in scene graphs` (场景图中的叶子节点), 54
- `length of video` (视频长度), 205
- `length setting for arcs` (弧形长度设置), 70
- `Light setting` (光照设置), 116–117
- `Lighting effect` (光照效果), 116–120
- `LinearGradients class` (线性渐变类), 83–86
- `LineBuilder class` (LineBuilder 类), 61
- `lines, drawing` (绘制线条), 56–64
- `listeners` (监听器)
- `moved events` (移动事件), 143
- `MoveTo()` 方法, 137–138
- `MediaPlayer` 对 `MP3` 文件的支持, 196
- `MediaPlayer` 对 `MP4` 文件的支持, 196
- `multiline comments` (多行注释), 18
- `multiple effects` (多效果), 127
- `multiple projects` (多个项目), 16
- `multiple shapes` (多个形状), 75
- `MVC (Model-View-Controller) design pattern` (模型-视图-控制器设计模式), 26–27
- `progress indicators` (进度指示器), 208
- `registering` (注册), 144
- `WebEngine` 的 `load()` 方法, 172
- `local image files` (本地图像文件), 92
- `location` (位置), 10, 12
- `lowercase characters in package names` (包名中的小写字母), 143
- `names` (命名)
  - `ID`, 34
  - `methods` (方法), 35–36
  - `packages` (包), 13
  - `projects` (项目), 10, 12
- `namespaces` (命名空间)
  - 编译 (`compiling`), 13
  - 作为包 (`packages as`), 12
- `nested layouts` (嵌套布局), 48–51
- `main()` 方法, 20–21
- `Max setting for Sliders` (滑块最大设置), 208
- `Media class` (Media 类), 196–197
- `MediaPlayer class` (MediaPlayer 类), 194–195
  - `file support` (文件支持), 196
  - `Play/Pause button` (播放/暂停按钮), 199–205
  - `playing video` (播放视频), 195–199
- `MediaView class` (MediaView 类), 194
  - `Play/Pause button` (播放/暂停按钮), 199–205
  - `playing video` (播放视频), 195–199
- `NetBeans`
  - 配置 (`configuring`), 8
  - 描述 (`description`), 3–4
  - 下载与安装 (`downloading and installing`), 5–7
  - 新项目 (`new projects`), 10–12
  - 项目中的 (`projects in`), 14–17
- `New File Wizard` (新文件向导), 183–185
- `New Project Wizard` (新项目向导), 10–12
- `new projects` (新项目), 10–12
- `NO_CYCLE value for gradient fill` (渐变填充的 NO_CYCLE 值), 84
- `nodes` (节点), 42
  - `context` (上下文), 57–58
- `methods` (方法)
  - `building` (构建), 37–39
  - `convenience` (便利性), 146
  - `declaring` (声明), 35–36
  - `inheriting` (继承), 20
  - `overriding` (覆盖), 158–159
  - 概览 (`overview`), 35–36
- `milliseconds to` (毫秒), 207
- `Min setting for Sliders` (滑块最小设置), 208
- `mixing colors` (混合颜色), 80–83
- `MVC design pattern` (MVC 设计模式), 26–27
- `modification in comments` (注释中的修改), 18
- `modifiers for methods` (方法修饰符), 36
- `mouse events` (鼠标事件), 142–151
  - `Cascading Style Sheets` (层叠样式表) 用于, 186
- `groups` (组), 132
- `HBox`, 43–46
- `nested layouts` (嵌套布局), 48–50
- `scene graphs` (场景图), 54–55
- `subclassing` (子类化), 158–159
- `VBox`, 44–48
- `observable arcs` (可观测弧形), 70
- `offset setting` (偏移设置), 84, 86

### O

- `onKeyPressed` 事件, 152
- `onKeyReleased` 事件, 152
- `onKeyTyped` 事件, 152
- `onMouseClicked` 事件, 143–144
- `onMouseDragged` 事件, 143
- `onMouseEntered` 事件, 143
- `onMouseExited` 事件, 143
- `onMouseMoved` 事件, 143
- `onMousePressed` 事件, 143–144, 148
- `onMouseReleased` 事件, 143–144
- `opacity of color` (颜色透明度), 82
- `ArcType` 的 `OPEN` 值, 71
- `orientation in PathTransition` (PathTransition 中的方向), 138
- `ORTHOGONAL_TO_TANGENT` 方向, 138
- `overriding methods` (覆盖方法), 21, 146, 158–159

### P

- `package statement` (包语句), 19
- `modifier scope` (修饰符范围), 36
- `self-contained applications` (自包含应用程序), 218–219
- `Source Packages folder` (源包文件夹), 12
- `Palette section` (调色板部分)
  - 显示 (`displaying`), 16
  - `snippets` (代码片段), 16–17
- `parameters` (参数)
  - 创建 (`creating`), 39
  - `methods` (方法), 35
- `parent nodes for scene graphs` (场景图父节点), 54
- `parentheses for methods` (方法括号), 36
- `passing arrays` (传递数组), 63
- `path animation` (路径动画), 136–140
- `PathTransition class` (PathTransition 类), 138
- `pause()` 方法, 201–202
- `play()` 方法, 201–203
- `PerspectiveTransform` (透视变换), 124–126
- `play()` 方法, 201–202
- `Play/Pause button` (播放/暂停按钮), 199–205
- `playing video` (播放视频), 195–199
- `playMedia()` 方法, 201–203
- 文件夹的加号 (`+`), 12
- `point in time of playback` (播放时间点), 205
- `Point light class` (点光源类), 117–118
- `predefined colors` (预定义颜色), 78–80
- `pressed events` (按下事件)
  - `key` (键), 152
  - `mouse` (鼠标), 143–144, 148
- `private modifiers` (私有修饰符), 36
- `progress indicators` (进度指示器), 205–210
- `projects` (项目)
  - `building` (构建), 214–215, 217
  - `creating` (创建), 10–12
  - `files` (文件), 14
  - 在 NetBeans 中, 14
- `Projects explorer frame` (项目资源管理器框架), 12
- `Projects option` (项目选项), 10
- `Projects tab` (项目标签页), 15
- `properties` (属性)
  - `binding` (绑定), 33–34, 39–40
  - `building` (构建), 37–40
  - `description` (描述), 37
  - `Inspector view` (检查器视图), 30
  - `Properties dialog box` (属性对话框), 214
- `protected methods` (保护方法), 36
- `public modifiers` (公有修饰符), 36

### R

- `RadialGradients` (径向渐变), 86–87
- `radius setting` (半径设置)
  - `arcs` (弧形), 70
  - `circles` (圆形), 73
  - `DropShadow` (投影), 113
  - `GaussianBlur` (高斯模糊), 109–110
  - `RadialGradients` (径向渐变), 86
- `radiusX`, 70
- `radiusY`, 70
- `arcs` (弧形), 70–71
- `LinearGradients` (线性渐变), 86

### S

- `Scene Builder` (场景生成器), 55
- `containers` (容器), 28–30
- `javafx.scene.control.Button` 包, 160
- `Scene Builder` (场景生成器), 27–28
- `Cascading Style Sheets` (层叠样式表), 186–187
- `Text property` (Text 属性), 30
- `TextField property` (TextField 属性), 32
- `Layout pane` (布局面板), 30
- `miscellaneous` (杂项), 51
- `nested` (嵌套), 48–51
- `layouts` (布局) (续)
  - 概览 (`overview`), 42–43
  - `VBox`, 47–48
- `leaf nodes in scene graphs` (场景图中的叶子节点), 54
- `length of video` (视频长度), 205
- `length setting for arcs` (弧形长度设置), 70
- `Light setting` (光照设置), 116–117
- `Lighting effect` (光照效果), 116–120
- `LinearGradients class` (线性渐变类), 83–86
- `LineBuilder class` (LineBuilder 类), 61
- `lines, drawing` (绘制线条), 56–64
- `listeners` (监听器)
- `moved events` (移动事件), 143
- `MoveTo()` 方法, 137–138
- `MediaPlayer` 对 `MP3` 文件的支持, 196
- `MediaPlayer` 对 `MP4` 文件的支持, 196
- `multiline comments` (多行注释), 18
- `multiple effects` (多效果), 127
- `multiple projects` (多个项目), 16
- `multiple shapes` (多个形状), 75
- `MVC design pattern` (MVC 设计模式), 26–27
- `progress indicators` (进度指示器), 208
- `registering` (注册), 144
- `WebEngine` 的 `load()` 方法, 172
- `local image files` (本地图像文件), 92
- `location` (位置), 10, 12
- `lowercase characters in package names` (包名中的小写字母), 143
- `names` (命名)
  - `ID`, 34
  - `methods` (方法), 35–36
  - `packages` (包), 13
  - `projects` (项目), 10, 12
- `namespaces` (命名空间)
  - 编译 (`compiling`), 13
  - 作为包 (`packages as`), 12
- `nested layouts` (嵌套布局), 48–51
- `main()` 方法, 20–21
- `Max setting for Sliders` (滑块最大设置), 208
- `Media class` (Media 类), 196–197
- `MediaPlayer class` (MediaPlayer 类), 194–195
  - `file support` (文件支持), 196
  - `Play/Pause button` (播放/暂停按钮), 199–205
  - `playing video` (播放视频), 195–199
- `MediaView class` (MediaView 类), 194
  - `Play/Pause button` (播放/暂停按钮), 199–205
  - `playing video` (播放视频), 195–199
- `NetBeans`
  - 配置 (`configuring`), 8
  - 描述 (`description`), 3–4
  - 下载与安装 (`downloading and installing`), 5–7
  - 新项目 (`new projects`), 10–12
  - 项目中的 (`projects in`), 14–17
- `New File Wizard` (新文件向导), 183–185
- `New Project Wizard` (新项目向导), 10–12
- `new projects` (新项目), 10–12
- `NO_CYCLE value for gradient fill` (渐变填充的 NO_CYCLE 值), 84
- `nodes` (节点), 42
  - `context` (上下文), 57–58
- `methods` (方法)
  - `building` (构建), 37–39
  - `convenience` (便利性), 146
  - `declaring` (声明), 35–36
  - `inheriting` (继承), 20
  - `overriding` (覆盖), 158–159
  - 概览 (`overview`), 35–36
- `milliseconds to` (毫秒), 207
- `Min setting for Sliders` (滑块最小设置), 208
- `mixing colors` (混合颜色), 80–83
- `MVC design pattern` (MVC 设计模式), 26–27
- `modification in comments` (注释中的修改), 18
- `modifiers for methods` (方法修饰符), 36
- `mouse events` (鼠标事件), 142–151
  - `Cascading Style Sheets` (层叠样式表) 用于, 186
- `groups` (组), 132
- `HBox`, 43–46
- `nested layouts` (嵌套布局), 48–50
- `scene graphs` (场景图), 54–55
- `subclassing` (子类化), 158–159
- `VBox`, 44–48
- `observable arcs` (可观测弧形), 70
- `offset setting` (偏移设置), 84, 86

### T

- `setWidth()` 方法, 66
- `setX()` 方法, 66
- `setY()` 方法, 66
- `shadow effects` (阴影效果), 115
- `shapes` (形状), 54
- `polylines` (多折线), 63
- `rectangles` (矩形), 65
- `startAngle` 设置, 70
- `startX` 设置
  - `arcs` (弧形), 69–72
  - `circles` (圆形), 72–74
  - 创建 (`creating`), 166
  - `ellipses` (椭圆), 74
- `Graphics API` (图形 API), 55–55
- `lines` (线条), 56–64
- `multiple` (多重), 75
- 概览 (`overview`), 55–56
- `polygons` (多边形), 68–69
- `rectangles` (矩形), 65–68
- `LinearGradients` (线性渐变), 83
- `lines` (线条), 58
- `startY` 设置, 83
- `statement terminators` (语句终止符), 19
- `stops for LinearGradients` (线性渐变停止点), 84
- `StringProperty` 类, 38
- `StringWidth()` 方法, 59
- `stroke` (描边)
  - `arcs` (弧形), 71
  - `rectangles` (矩形), 65–67
- `strokeOval()` 方法, 98
- `strokeWidth` 设置
- `JavaFX()` 方法, 174–176
- `method signatures` (方法签名), 35
- `single-line comments` (单行注释), 18–19
- `image dimensions` (图像尺寸), 97
- `skill requirements` (技能要求), 3
- `slashes (/)` (斜杠)
  - `lines` (线条), 59
  - `rectangles` (矩形), 65–66
- `stylesheets` (样式表). 参见 `Cascading Style Sheets (CSS)`
  - 注释 (`comments`), 18–19
  - 作为转义字符, 33
- `StyleClass` 属性, 190
- `independent style classes` (独立类的样式), 190–191
- `style events` (样式事件) 用于 142
- `subclassing` (子类化), 158–159
- `Swing compatibility` (Swing 兼容性), 222–223
- `SwingNode`, 222–223
- `Sliders` (滑块), 207–208
- `snippets` (代码片段), 16–17
- `software` (软件)
  - 安装 (`installation`), 5–7
  - 要求 (`requirements`), 3–4
- `SDK` (软件开发包), 4
- `Source Packages folder` (源包文件夹), 12
- `SpecularExponent` 设置, 119
- `Spot class` (Spot 类), 119–120
- `spread` 设置, 113
- `StackPane`, 132
  - `groups` (组), 132
  - `HBox layout` (HBox 布局), 44–45
  - `root node` (根节点), 59
- `build.xml` 的 `<target>` 标签, 218
- `terminators, statement` (终止符，语句), 19
- `Text property` (Text 属性), 30
- `TextField property` (TextField 属性)
  - 用于 `ID`, 34
  - `label` (标签), 32
  - `line thickness` (线的厚度), 59
- `threshold setting` for `Bloom effect` (绽放效果阈值设置), 105
- `TilePane layout` (TilePane 布局), 51
- `timelines` (时间线), 131–135
- `ToggleButton` (切换按钮), 64
- `Stage` (舞台), 20
  - `application entry points` (应用程序入口点), 20–21
- `Cascading Style Sheets` (层叠样式表), 187–188
- `Standard Edition JDK` (标准 Java 开发包), 4
- `start()` 方法, 20–21
  - NetBeans 中的 `start page` (起始页), 6–7
  - `starting points` (起点)
- `toMillis()` 方法, 207
- `trackball events` (轨迹球事件), 142
- `trackpad events` (轨迹板事件), 142
- `transformations` (变换), 122
  - `PerspectiveTransform` (透视变换), 124–126
  - `rotation` (旋转), 123–124
  - `XY`, 123–124
  - `translate` 设置, 123
  - `translateY` 设置, 123
  - `LinearGradients` (线性渐变), 83
  - `lines` (线条), 57–58
- 图像的转换 (`image transformations`), 95–96
- `color transparency` (颜色透明度), 82
- `tree containers` (树状容器), 54
- `ArcType` 的 `type` 设置, 71
- `typed events` (输入事件), 152
- `types` (类型)
  - `images` (图像), 97
  - `methods` (方法), 35
  - `arcs` (弧形), 71
  - `DropShadow` (投影), 13
  - `images` (图像), 92
  - `lines` (线条), 59
  - `rectangles` (矩形), 65–66

### U

- `url setting` for `images` (图像的 url 设置), 92

### V

- `Valignment property` (垂直对齐属性), 31
- `value setting` for `Sliders` (滑块的值设置), 208
- `valueProperty`, 208
- `value binding` (值绑定), 33–34
- `variables` (变量)
  - `binding` (绑定), 33
  - `inheriting` (继承), 32
- `VBox layout` (VBox 布局), 47–48
- `verbs in methods` (方法中的动词), 36
- `comments` (注释), 18
- `NetBeans`, 5
- `Vgrow property` (Vgrow 属性), 31
- `video` (视频), 194–195
  - `embedded` (嵌入), 170
  - `Play/Pause button` (播放/暂停按钮), 199–205
  - `playing` (播放), 195
  - `progress indicators` (进度指示), 205
- `View` in `MVC` (MVC 中的视图), 26
- `void return type` (void 返回类型), 38
- `image transformations` (图像转换), 95
- `XML markup language` (XML 标记语言), 21
- `XY transformations` (XY 变换), 123–124

### W

- `Web files` (Web 文件), 92–93
- `web()` 方法, 80, 82–83
- `Web applications` (Web 应用), 219

### X

- `x-axis setting` for `LinearGradients` (线性渐变的 x 轴设置), 83
- `x coordinates` (x 坐标)
  - `lines` (线条), 57
  - `PerspectiveTransform` (透视变换), 124–125
  - `Point light` (点光源), 118
  - `polyline start points` (折线起点), 63
  - `rectangles` (矩形), 65–66

### Y

- `y-axis setting` for `LinearGradients` (线性渐变的 y 轴设置), 83
- `y coordinates` (y 坐标)
  - `lines` (线条), 57
  - `PerspectiveTransform` (透视变换), 124–125
  - `Point light` (点光源), 118
  - `polyline start points` (折线起点), 63
  - `rectangles` (矩形), 65–66
  - `image transformations` (图像转换), 95

### Z

- `z coordinate` for `Point light` (点光源的 z 坐标), 118
- `stack order` (栈顺序), 44

---

## 广告与版权信息

> 我可以将 Java 代码复制到 HTML 扩展中吗？Java 用户组非常棒...
> 我是用这种方式编写代码的...你参加 JavaOne 了吗？
> 限制性赋值是如何工作的？
> 我提交了 JavaOne 征稿...
> 如果你想重新格式化代码，请尝试这种方法...
> 哪里可以找到 Java ME 日志的技术文章？
> Oracle Technology Network 是一个共享代码的地方。
> 来到这个地方，与其他 IT 专业人士合作 Java 的一切。
> Oracle Technology Network 是全球最大的使用 Java 和行业标准技术的开发者、管理员和架构师社区。
> 注册免费会员，即可访问：
> - 讨论论坛和实践实验室
> - 免费下载的软件和示例代码
> - 产品文档
> - 成员贡献的内容
>
> 利用我们的全球知识网络。
> 立即加入 ► 访问 oracle.com/technology/java

![Oracle Technology Network](img/f5bc6249660e63bd0b6a2dc9598edb7_264_0.png)
![Oracle Technology Network](img/f5bc6249660e63bd0b6a2dc9598edb7_264_1.png)

Copyright © 2013, Oracle 或其关联公司保留所有权利。Oracle 和 Java 是 Oracle 或其关联公司的注册商标。其他名称可能是其所有者的商标。

# 我们的技术。您的未来。

通过 Oracle 认证快速提升您的职业。
超过 150 万份认证证明了这些顶级行业认可证书作为领先最佳途径之一的重要性。
并保持领先。

**ORACLE 认证计划**
certification.oracle.com

# 硬件与软件
为协同工作而设计

![Hardware and Software](img/f5bc6249660e63bd0b6a2dc9598edb7_266_0.png)

# ORACLE ACE 计划

# 需要帮助？需要咨询？需要专业意见？
保持联系
oracle.com/technology/oracle
- oraclesaces
- @oracleace
- blogs.oracle.com/oracle

你需要一个 Oracle ACE
Oracle 合作伙伴、开发者和客户向 Oracle ACE 和 Oracle ACE 主管寻求专注的产品专业知识、系统和解决方案讨论，以及对各种数据中心实现的专业意见。
他们的资历与 Oracle 产品和技术专家、社区爱好者和解决方案倡导者一样强大。
现在是了解关于这个精英群体的好时机——或推荐一位值得的同事。
有关 Oracle ACE 计划的更多信息，请访问：
oracle.com/technology/oracle

# ORACLE

![Oracle Logo](img/f5bc6249660e63bd0b6a2dc9598edb7_267_0.png)

# 通过 Oracle Publishing Group 接触超过 700,000 名 Oracle 客户

## 与对您的业务最重要的受众建立

### Oracle 杂志
全球最大的出版物
发行量：550,000
受众：IT经理、DBA、程序员和开发者

### Profit
帮助企业级领导者使用 Oracle 技术改善业务的洞察
发行量：100,000
受众：高管和业务经理

### Java 杂志
关于 Java 技术、Java 语言和基于 Java 应用的核心
发行量：125,000 稳定增长
受众：企业和独立开发者、程序员和架构师

![Magazines](img/f5bc6249660e63bd0b6a2dc9598edb7_267_1.png)

欲获取更多信息或免费订阅：
扫描二维码访问 Oracle 在线。

# 入门 JavaFX

通过 Oracle Press 的这本实用教程，快速开发并部署交互式客户端应用程序。专注于在 NetBeans IDE 中操作，《JavaFX 快速入门指南》介绍了如何使用 JavaFX 布局、绘制形状、使用颜色和渐变工具、加载图像、应用效果和变换、嵌入媒体。您还将了解使用 JavaFX 事件、子类化现有节点、创建自定义节点、使用 `WebView` 以及使用 CSS 样式化您的应用程序。为了便于学习，书中具有：

- **关键技能与概念**——章节开头列出的特定技能列表
- **专家问答**——问答章节，充满了额外信息和有用技巧
- **尝试此处**——动手练习，向你展示如何应用技能
- **注释**——与主题相关的额外信息
- **提示**——有用的提醒或替代方法
- **警告**——要避免的错误和陷阱
- **注释语法**——带有说明所所示编程技术的示例代码
- **自测**——章节末的测试，以强化你的技能

书中的代码示例可以在 www.OraclePressBooks.com 下载。

获取完整的 Oracle Press 书籍，请访问 www.OraclePressBooks.com。

# 了解更多。更多：

MHPROFESSIONAL.COM

在 Twitter 上关注我们 @OraclePress

电子书可用

编程/JavaFX

$40.00 USD

ISBN 978-0-07-180896-5
MHID 0-07-180896-5

54000
