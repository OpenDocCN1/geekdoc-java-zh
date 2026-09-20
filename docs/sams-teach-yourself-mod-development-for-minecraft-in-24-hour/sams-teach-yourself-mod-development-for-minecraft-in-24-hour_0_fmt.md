
# Sams 24 小时教你 Minecraft Mod 开发

## 关于本书

ePUB 是一种开放的行业标准电子书格式。然而，阅读设备和应用程序对 ePUB 及其许多功能的支持程度不同。请使用您的设备或应用设置来根据您的喜好自定义显示效果。您可以自定义的设置通常包括字体、字号、单栏或双栏、横屏或竖屏模式，以及可以点击或触摸放大的图片。有关您的阅读设备或应用的设置和功能的更多信息，请访问设备制造商的网站。

许多书目包含编程代码或配置示例。为了优化这些元素的显示，请在单栏横屏模式下查看电子书，并将字体大小调整为最小设置。除了以流式文本格式显示代码和配置外，我们还包含了代码图像，模仿印刷书籍中的显示效果；因此，当流式格式可能会损害代码列表的显示时，您将看到“点击此处查看代码图像”链接。点击链接查看高保真代码图像。要返回上一页，请点击设备或应用上的后退按钮。

### 工作坊

### 问答

### 练习

### 总结

### 工作坊

### 总结

### 练习

### 问答

## 使用实体

### 渲染投掷物

### 总结

### 问答

### 工作坊

content)

## 生成粒子

## 关于作者

`Jimmy Koene` 维护着世界上最流行的 Minecraft Mod 网站之一（[www.wuppy29.com/minecraft/modding-tutorials/forge-modding/](http://www.wuppy29.com/minecraft/modding-tutorials/forge-modding/)）。他是极少数持续维护并更新在线教程的 Minecraft Mod 制作者之一。他还是一名资深的 `Java` 和 `C++` 程序员，编写过一个下载量超过 30,000 次的安卓 Minecraft 应用以及其他各种小型应用。他还维护了几个涵盖 Minecraft 许多方面的 Mod，范围从对食物运作方式的微调到完全改变游戏体验的 Mod。

## 献辞

致 Minecraft Mod 社区，让 Minecraft 成为最畅销且最神奇的游戏之一。感谢让我开始制作 Mod 的社区，是他们促成了本书的诞生。

## 谢谢

首先，我要感谢 `Rick Kughen`，是他主动找我提议写一本关于 Minecraft Mod 开发的书。在他给我发邮件并分享他的想法之前，我从未想过这是可能的。开发像 Minecraft 这样游戏的 Mod，面临的最大问题之一就是你正在处理的代码会不断变化。Minecraft 或 `Forge`（本书中所使用的应用程序编程接口 `API`）的每一次更新都可能改变大量的代码。幸运的是，电子书可以很容易地更新，`Rick Kughen` 告诉我可以有一个在线数据库，让我可以频繁地为书籍添加更新和更改。这使得这本书的编写成为可能。

我应该感谢的其他还包括创建 Minecraft 的 `Markus “Notch” Persson`。没有他的创意，我永远不会开始编程，这本书也永远写不出来。还有很多人帮助创建了 Minecraft 和 Mod 社区，他们包括 `Jeb`、`Dinnerbone`、`Searge`、`ProfMobius`、`R4wk`、`CodeWarrior`、`ZeuX`、`Risugami`、`cpw`、`AbrarSyed` 和 `LexManos`。他们是 `MCP`、`MCEdit`、`Techne`、`ModLoader` 和 `Forge` 的创建者。本书中（间接）使用了所有工具。最后，我要感谢编辑 `Mark Renfrow` 和 `Rick Kughen`、审稿员以及其他参与任何书籍相关工作的所有人。没有这些人，这本书就不可能完成。我特别想感谢 `Forge` 的创建者 `LexManos`，他在该领域的专业知识提供了很大帮助。

## 我们想听听你的声音！

作为本书的读者，我们非常重视你的意见，并想知道你喜欢或不喜欢的地方，以及我们可以做得更好的地方。

每一小时都涵盖了 Minecraft Mod 开发的一个重要方面，包括各种物品、方块和实体。通过跟随每一小时的进度、积极参与“动手试一”活动，并完成每小时结束的工作坊和练习，你将从这些主题中学到很多知识。你还将获得关于如何使用开发环境的信息、自学方法，以及贯穿书中各处的“笔记”和“提示”提供的许多其他主题。

邮箱：consumer@amsublishing.com (mailto:consumer@amsublishing.com)

邮寄：Sams Publishing, ATTN: Reader Feedback, 800 East 96th Street, Indianapolis, IN 46240 USA

## 读者服务

访问我们的网站并在 `informit.com/register` (http://informit.com/register) 注册本书，以便方便获取本书可能提供的任何更新、下载或勘误。

## 引言

Minecraft 是一个非常棒的游戏。它是最畅销的 PC 游戏之一，而且极其受欢迎。它受欢迎的众多原因之一就是有了 Mod。如果你拿着这本书，你可能已经对 Minecraft 感兴趣，并且可能已经玩过一些 Mod。本书将教你如何自己创建这些内容。

自己制作 Mod 有两个巨大的优势。首先，你可以按照自己的想法改进游戏，塑造 Mod 以使其完全符合你的需求，并让游戏玩起来更有趣。其次，制作 Mod 是进入编程领域的简单途径，这是一个蓬勃发展的行业，而且根据许多人（包括我在内），制作 Mod 是一件非常有趣的事情。

### 谁应该读这本书

这本书是为任何喜欢 Minecraft 且不害怕编程和 Minecraft 相关知识的人编写的。

如果你期望的是一份关于如何开始编程的完整指南，那么这本书并不适合你。但是，如果你想进入编程或已经知道如何编程，这本书无疑会对你有帮助。

在开始阅读这本书之前，熟悉一些 `Java` 可能会有所帮助；然而，`Java` 的基础知识将在书中随用时对其进行解释。因此，没有必要具备先行的编程知识。不过，如果你有玩《我的世界》（Minecraft）的经验将会很有帮助，因为游戏中的许多术语在书中也会用到。此外，玩过《我的世界》可以让你洞察游戏某些层面的运作方式，这能让你更容易理解你正在创建的内容。当你读到这本书的最后一小时时，建议你学习 `Java`，但到那时你应该已经对它有了相当的理解，这会让学习变得更容易。最后一小时之后是一个附录，其中包含了更多的代码，你可能在自己的模组中需要这些代码。

### 本书的结构

要在短短 24 小时内学会《我的世界》提供的所有内容似乎任务量很大——确实如此。这本书并没有涵盖《我的世界》中每一个物品的创建。相反，它涵盖了最常用部分的创建，这为你提供了制作更特定内容的知识。接下来的分解列出了你在每一小时中将学到的细节：

![Image](img/image00525.jpeg) 在第 1 小时，“设置我的世界开发环境”，你将搭建开始开发《我的世界》模组的环境。在这一小时中，你将学习书中用的大部分程序。

![Image](img/image00525.jpeg) 在第 2 小时，“为 Forge 创建基础内容”，你开始编写代码。在这一小时中，你创建了模组的框架，你将在所有其他小时在此基础上进行构建。

![Image](img/image00525.jpeg) 第 3 小时，“处理配方和其他小型修改内容”，这是你第一次以合成配方、熔炼配方等形式为《我的世界》添加自定义内容的章节。

![Image](img/image00525.jpeg) 在第 4 小时，“创建你的第一个物品”，你创建了第一个物品。从这一小时开始，你为模组添加了第一个真正独特且有趣的内容。在开始添加独特内容之前还有四个小时，时间很长，但这是必要的，因为没有代码或模组类你就无法进行模组开发。

![Image](img/image00525.jpeg) 在第 5 小时，“智能地创建多个物品”，你扩展了在第 4 小时中编写的代码，以确保你的模组看起来整洁并与其他模组良好协作。

![Image](img/image00525.jpeg) 在第 6 小时，“烹饪食物物品”，你的目标是创建一个玩家可以食用并能回血玩家的物品。这是你可以创建的许多自定义物品类型之一。

![Image](img/image00525.jpeg) 第 7 小时，“制作你自己的工具”，这是另一个包含自定义物品类型的章节。这次，你学习了如何制作自定义的镐、铲和完全全新的工具。

![Image](img/image00525.jpeg) 在第 8 小时，“创建盔甲”，你学习了另一种自定义物品类型——盔甲。你学习了如何创建盔甲，然后学习如何对其自定义。

![Image](img/image00525.jpeg) 在第 9 小时，“创建你的第一个方块”，与第 4 小时类似，你学习了《我的世界》的另一个重要方面。在这一小时中，你学习了构成世界的东西——方块。

![Image](img/image00525.jpeg) 在第 10 小时，“智能地创建多个方块”，你学习了在第 5 小时中关于物品的相同内容，但是针对方块的。

![Image](img/image00525.jpeg) 在第 11 小时，“让你的方块变得独特”，你学习了让方块有趣的各种方法。你学习了如何制作半方块、植物以及其他几种物品。

![Image](img/image00525.jpeg) 在第 12 小时，“创建方块实体”，你学习了《我的世界》中最复杂的部分之一——方块实体。

![Image](img/image00525.jpeg) 在第 13 小时，“生成矿石”，这是你学习生成内容的第一个重要小时。在这一小时中，你学习了世界所构成的东西——矿石。

![Image](img/image00525.jpeg) 在第 14 小时，“生成植物”，你使用了在第 13 小时中学习的知识。

![Image](img/image00525.jpeg) 在第 15 小时，“使用 MCEit”，你学习了使用名为 MCEit 的程序来创建结构。

![Image](img/image00525.jpeg) 在第 16 小时，“生成你的结构”，你使用了在第 15 小时中创建的内容。

![Image](img/image00525.jpeg) 在第 17 小时，“学习实体”，你学习了什么是实体，有哪些种实体，以及如何创建它们。

![Image](img/image00525.jpeg) 在第 18 小时，“使用 Techne 创建实体”，你为实体创建一个模型。这使用了 `Techne`，它是专门为模组设计的建模软件。

![Image](img/image00525.jpeg) 在第 19 小时，“编码生物”，你将在第 18 小时中创建的模型与第 17 小时中的代码结合，创建一个类似于僵尸但又不同的生物。

![Image](img/image00525.jpeg) 在第 20 小时，“创建投掷物”，你学习了一种可以被玩家投掷的实体。

![Image](img/image00525.jpeg) 在第 21 小时，“修改原版我的世界”，你学习如何修改游戏，使得多个模组可以编辑同一个内容而不破坏游戏。

![Image](img/image00525.jpeg) 在第 22 小时，“结构化你的模组”，你学习了如何整理一下你的模组。此时，几个文件看起来非常拥挤，这会影响你的体验。在这一小时之后，你应该能够在一个更容易使用的环境中继续工作。

![Image](img/image00525.jpeg) 在第 23 小时，“发布你的模组”，这是一个非常重要的小时。在这一小时中，你学习了如何在开发环境之外使用你的模组并将其分给用户。

![Image](img/image00525.jpeg) 在第 24 小时，“接下来做什么”，你学习了在完成这本书后如何继续《我的世界》模组开发。这本书的意图不仅仅是作为你复制书中内容的指南，它的意图是让你学会自己创建东西。

### 使用的约定

本书使用了一些约定，以便你更容易理解所解释的内容。

### 动手尝试一下

“亲手尝试”（Try It Yourself）活动是书中最重要的约定之一。“亲手尝试”活动提供了实操机会，让你能够积极体验并参与该小时中涵盖的主题。这些实践活动提供了“在做中学习”的机会。这是学习 Minecraft 组开发的最佳方式。

### 注意（Notes）

`Note` 元素提供了额外的信息。这些有趣的逸闻提供了补充内容，或扩展了附近文本中提供的信息。

### 提示（Tips）

`Tip` 元素提供了制作模组时可能有用的额外信息。这些信息的范围从如何更好地使用程序的技巧，到你可能想要在代码中更改的某些内容。提示识别了对你有所帮助的实用小技巧或专家建议。

### 警告（Cautions）

`Caution` 元素用于警告你：你可能采取的某个以后可能会产生严重后果。这些告诫文本会警告你潜在的危险，并对你想要避免的结果提供提前预警。

### 代码列表（Code Listings）

代码列表是你在这书中发现的另一个有用元素。代码列表提供了与当前主题相关的代码示例。你可以通过检查示例代码来感受你的代码应该如何编写。

在书中，正式的代码列表始终由两条线包围，以显示代码的开始和结束。列表周围的文本解释了如果代码本身不直观的话，这些代码应该放在哪里。

当一行代码太长无法在一行文本中显示时，它将换行到下一行。在这种情况下，延续部分前面有一个代码延续箭头 `![Image](img/image00526.jpeg)`。

### 下载代码和资源（Downloading the Code and Resources）

有时你的模组就是无法运行，无论你如何查看它，都找不到错误。在这种情况下，直接将书中使用的代码复制到你的工作区中可能会有所帮助。检查示例代码并与你编写的代码进行比较，可能帮助你定位并修正代码中的错误。此外，并不是每个人都擅长制作纹理，所以你可能想要获得书中使用的纹理。这两者都可以通过注册书籍来访问：

1. 访问 `www.informit.com/title/9780672337192`。

2. 点击“注册你的产品”（Register Your Product）并登录或创建新账户。

3. 输入此 ISBN：`9780672337192`。这是纸质书籍的 ISBN，必须用于注册每个版本。

4. 点击你账户页面“注册产品”部分中的“访问奖励内容”（Access Bonus Content）链接，这将带你进入可以下载可用内容的页面。

此外，正如致谢（Acknowledgments）中提到的，用于制作 Minecraft 模组的代码经常会变化。为了确保这本书在未来仍然有用，提供了在线更新和勘误表，可以在 `www.informit.com/title/9780672337192` 的“更新”（Updates）选项卡中找到它们。

# 第一部分：引言

## 第 1 小时：设置 Minecraft 开发环境

在本小时中将到：

- ![Image](img/image00525.jpeg) 理解 Minecraft 是如何编写的以及你将用它做什么
- ![Image](img/image00525.jpeg) 学习 Forge
- ![Image](img/image00525.jpeg) 安装 JDK
- ![Image](img/image00525.jpeg) 安装 Eclipse
- ![Image](img/image00525.jpeg) 安装 Forge

在本小时中，你将学习 Minecraft 是如何编写的，以及在开始编写 Minecraft 代码之前需要什么。这包括编写它时使用的语言、你将用于编写代码的新程序，以及关于应用程序接口（`API`）的信息，该 API 将用于编写模组。最后，你将学习如何设置你的开发环境。

### 理解 Minecraft 是如何编写的以及你将用它做什么

如果你以前玩过 Minecraft，你就知道 Minecraft 是用 `Java` 写的。`Java` 是一种运行在每种计算机上的编程语言。无论你用的是 `Mac` 还是 `PC`，或者运行的是 `Linux` 还是 `Windows`，它都能无视操作系统运行。这意味着你可以在任何操作系统上开发 Minecraft 模组。

> **注意：关于 Java**
>
> 因为 Minecraft 是用 `Java` 写的，所以也将用 `Java` 编写。一些模组制作者认为你必须熟悉 `Java` 才能编写最基本的模组。然而，这本书并没有此要求。学习它仍然是一个明智的主意，但你可以在完全没有任何 `Java` 先验知识的情况下阅读整本书。

这意味着你将不得不设置一些与 `Java` 相关的内容。如果你想玩 Minecraft，你需要 Java 运行环境（`JRE`），但大多数计算机已经安装了它，因为它被许多程序使用。对于制作模组，你需要 Java 开发工具包（`JDK`）。设置这个稍微多花一点，但你将在本小时内学会如何操作。

除了 `JDK` 之外，你还需要一个编写代码的地方。你可以在 `Word`、记事本或其他任何文本编辑器中编写代码。但是，许多集成开发环境（`IDE`）可以提高你的编码速度。`IDE` 提供了如格式化和自动补全等工具。由于你在编写 `Java`，有很多 `IDE` 可供选择。在书中将介绍了 `Eclipse` 的设置，它是最常用的 `IDE`。

> **注意：其他 IDE**
>
> 除了 `Eclipse` 还有其他 `IDE`。还有 `IntelliJ IDEA` 和 `NetBeans`。或者，你可以使用 `NotePad++`。但是，只有 `Eclipse` 和 `IDEA` 自带了所需的开发环境。对于其他的，你需要手动设置。

### 获取源码

除了编程语言和编写代码的程序之外，开始 Minecraft 开发还需要另一个东西：你还需要一种将 Minecraft 代码转换为可读源码的方法。这可以通过 Mod Coder Pack（`MCP`）完成，它是由社区编写的。在模组社区像现在这么大之前，Minecraft 模组是使用这套工具编写的。然而，如果你这样编写代码，用户无法同时使用多个模组。为了让用户能够使用多个模组，编写了一个 `API`。对于当前的 Minecraft 版本，只有一个 `API` 仍在更新。这个 `API` 称为 `Forge`。

### 学习 Forge



`Forge` 是一个 `API`，正如前面提到的，它可以让多个模组能够在游戏中运行。然而，`Forge` 的功能远不止于此，它让模组编写变得简单得多，并为你提供了许多更改 Minecraft 某些方面（只能通过 `Forge` 修改）的工具。

`Forge` 是一个编写得很好的程序。`Forge` 的功能可以比作在不知道每个人名字的情况下尝试将所有人聚集在一起。它可以在 Minecraft 显式知道它们的情况下定位并加载模组。为了实现这一点，`Forge` 要求用户和模组制作者执行一些操作以使模组变得可识别。

编写 Minecraft mod 还有其他方法。`Forge` 并不是必须的，但它能确保 mod 的编写尽可能简单。它还确保了可以同时使用多个 mod。

## 设置 JDK

必须按照特定的顺序进行设置。首先，你设置编程语言的要求，然后是 IDE，最后是设置你想要编程的内容。这意味着你首先从安装 `JDK` 开始。首先，访问以下 URL 中的 Oracle 网站下载 `JDK`：[www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)。选择适用于你系统的 `JDK` 版本。但请务必下载 JDK 7 版本。如果你尝试使用 JDK 8，它可能无法运行。

每个操作系统（OS）的 JDK 设置方法均不相同。请务必根据你的操作系统阅读相应的说明。

注意：准确性

请非常仔细地遵循接下来的步骤。如果你在这些步骤中犯了任何微小的错误，此之后的所有步骤都将无法运行。

### Windows

为 Windows 设置 JDK 需要的工作最多。你从 Oracle 下载的是一个可执行文件，它安装了大部分 JDK，但为了让它真正运行还需要额外的设置。要设置 JDK，请遵循以下步骤：

**1.** 运行 `JDK` 的可执行文件进行安装。按照安装程序给出的说明操作。当提示选择要安装哪些组件时，直接点击“下一步”（Next）。安装路径并不重要，但建议使用标准位置。

**2.** 接下来，导航到你刚刚安装 `JDK` 的文件夹。使用标准路径，这应该是 `C:/Program Files/Java`。如果你在 64 位机器上安装了 32 位版本的 Java，你必须进入 `C:/Program Files (x86)/Java`。在这个文件夹中，可能会找到多个版本的 Java。很可能有一个 `JRE` 文件夹和一个 `JDK` 文件夹。进入 `JDK` 文件夹，然后进入 `bin` 文件夹。现在点击 Windows 资源管理器顶部的路径并复制文件路径。你稍后需要这个路径。

**3.** 现在你必须经过几个窗口，从图 1.1 开始。

![Image](img/image00527.jpeg)

**图 1.1** 导航到计算机属性。

首先点击 Windows 图标（图中标记为 1 的位置）。然后右键点击“计算机”，如图中数字 2 所示。最后，点击出现的右键菜单底部的“属性”（数字 3）。

**4.** 此操作后，会打开一个新窗口，如图 1.2 所示。

![Image](img/image00528.jpeg)

**图 1.2** 控制面板，系统属性。

在此窗口中，点击左侧的“高级系统设置”，在图 1.2 中高亮显示。

**5.** 接下来，打开系统属性窗口，如图 1.3 所示。

![Image](img/image00529.jpeg)

**图 1.3** 系统属性窗口，高级选项卡。

在此窗口中，确保你处于“高级”选项卡上，这应该是默认值。现在点击图中高亮显示的“环境变量”按钮。

**6.** 执行此操作后将打开“环境变量”窗口，如图 1.4 所示。

![Image](img/image00530.jpeg)

**图 1.4** 环境变量窗口。

在此窗口中，你只需要关心顶部部分的设置。下部分对于设置 JDK 并不重要。“用户变量”框（图中 1 框）显示了你的电脑到目前为止所有的变量。你可以通过点击“新建”按钮（图中 2 框）在其中添加新变量。

**7.** 打开“新建用户变量”窗口，在其中添加新变量。图 1.5 显示了此窗口。

![Image](img/image00531.jpeg)

**图 1.5** 添加用户变量。

要添加新的用户变量，请输入“变量名”和“变量值”。对于名称，输入 `PATH`。对于值，粘贴你之前复制的 Java 路径，并在后面跟上 `;%PATH%`。这很重要，因为它将新变量 `PATH` 与系统级变量 `PATH` 结合在一起，后者包含了重要的位置，例如 Windows 的安装位置。

如果你已经有一个 `PATH` 值，选中它并点击“编辑”。然后移动到变量的末尾添加一个分号（`;`），然后粘贴之前的路径。

注意：添加第二个 PATH 值

请非常小心，不要创建第二个 `PATH` 变量。如果你已经有了一个，请编辑那一个。在编辑时，请确保第一个值、分号（`;`）和新值之间没有空格，否则它们都将无法正常工作。

**8.** 最后，在“新建用户变量”窗口、“环境变量”窗口和“系统属性”窗口中点击“确定”，然后关闭控制面板。你的 Java 应该已安装正确。

**9.** 要检查 JDK 是否可用，在任何地方打开提示符并运行 `javac`。此命令应该输出如下信息：

```
C:\Users\Jimmy>javac
Usage: javac <options> <source files>
```

### Mac

**1.** 双击 `.dmg` 文件启动 JDK。

**2.** 应该弹出一个 Finder 窗口，其中包含 `.pkg` 文件。双击该包启动安装程序。

**3.** 按照安装程序的说明操作。

### Linux

如果你有 `.tar.gz` 文件，请完成以下步骤：

**1.** 将 `.tar.gz` 文件剪切并粘贴到你想安装 JDK 的位置。

**2.** 在终端中使用以下命令解压并安装 JDK：

```bash
% tar zxvf jdk-7u<version>-linux-x64.tar.gz
```

如果你下载的是 `.rpm` 文件，运行它即可安装。

设置的最后一步是下载并安装 Forge。执行此操作，请访问 [minecraftforge.net](http://minecraftforge.net) 网站。进入下载页面（[files.minecraftforge.net/](http://files.minecraftforge.net/)），获取你所需的 Forge 的 `src` 版本。当你点击 `src` 版本时，它会带你进入一个 `adf.ly` 链接。请确保等待五秒，然后点击右上角的巨大按钮下载 Forge。其他任何按钮都可能包含间谍软件。通常，最好的版本是适用于你将开发的 Minecraft 版本的最新发布版。在写作期间，Minecraft `1.7.10` 对应的版本是 `10.13.0.1152`。如果你正在为更高版本的 Forge 编写 mod，情况可能会略有不同。如果发生这种情况，本书的网站（[www.informit.com/title/9780672337192](http://www.informit.com/title/9780672337192)）可能会提供相关信息的更新，因此请务必注册你的书籍以获取最新信息。

***

注意：Adfly 与 Mod 制作者

当你阅读此书时会发现，制作 mod 需要很长时间。mod 制作者通常希望为他们的工作获得少许报酬。可以通过捐赠来实现，几乎每个 mod 制作者的 mod 页面上都有捐赠选项，但很少有捐赠。因此，许多 mod 制作者会将 mod 下载放在一个 `adf.ly` 链接之后。这是一个带有广告的网站，你必须等待五秒，之后就可以继续并下载 mod。在 `adf.ly` 网站上你应该小心，因为只有右上角的链接是可靠的。其他的都是广告，并可能对你的电脑造成危害。

***

一旦从 Forge 下载网站下载了 `src` 文件，使用 winRar、7Zip 或其他可以打开此类文件的程序打开 `.zip` 文件。现在，进入你之前解压 Eclipse 的文件夹，在同一个父文件夹中创建一个 `forge` 文件夹。在该文件夹中，粘贴 Forge `.zip` 文件中的所有文件。这些文件中应该包含 `gradlew.bat`。如果该文件不存在，说明你下载了错误的 Forge 版本。

接下来，使用你的命令提示符或终端运行两个命令。

***

注意：可能的问题

如果以下任一命令不起作用，你可能犯了以下错误之一：

![Image](img/image00525.jpeg) 你安装的是 `JDK 8`；请改用 `JDK 7`。

![Image](img/image00525.jpeg) 你没有正确安装 `JDK`。

![Image](img/image00525.jpeg) 你没有在正确的文件夹中运行命令。确保你在包含 `gradlew.bat` 文件的文件夹中运行。

![Image](img/image00525.jpeg) 你的防火墙阻止了下载。如果是这种情况，请尝试将其关闭几分钟。

***

第一个命令如下：

```
gradlew setupDecompWorkspace
```

在 Mac 上，在所有命令前加上不带引号的 `"./"`。根据你的网络连接速度，这需要几分钟时间才能完成。之后，运行以下命令：

```
gradlew eclipse
```

一旦命令提示符完成，Forge 就可以使用了。剩下的唯一工作就是打开你的开发环境（Eclipse）来开始编码。启动 Eclipse 后，会弹出一个窗口。这个窗口会为你启动 Eclipse。过段时间后，工作空间启动器窗口会在它上方打开，并有一个 `Browse`（浏览）按钮。它看起来像图 1.6。

![Image](img/image00532.jpeg)

**图 1.6** Eclipse 的启动。

点击 `Browse` 按钮后（如图 1.6 所示），会打开一个窗口，如图 1.7 所示。

**图 1.7** Eclipse 中的选择工作空间目录窗口。

现在进入你安装 Forge 的文件夹，并选择其中的 `Eclipse` 文件夹。最后，在图 1.6 所示的工作启动器窗口上再次点击 `OK`。完成后，Eclipse 将加载它需要的内容，然后打开一个你在其中编写所有代码的窗口。在左侧，你会看到名为 `Minecraft` 的项目。点击它左侧的小箭头。当你这样做时，它会显示许多文件和文件夹，但你不需要担心大部分内容。你唯一要做的是导航到 `src/main/java` 文件夹并点击其左侧的箭头。这会打开另一个下拉菜单，在其中你应该看到一个名为 `com.example.examplemod` 的棕色包。再次点击它左侧的箭头，它会显示一个名为 `ExampleMod` 的文件。双击该文件，中间窗口将显示该文件的代码。它看起来像列表 1.1。

**列表 1.1** Example 中的 ExampleMod

```java
package com.example.examplemod;

import net.minecraft.init.Blocks;
import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.event.FMLInitializationEvent;

@Mod(modid = MODID, version = VERSION)
public class ExampleMod {

    public static final String MODID = "examplemod";
    public static final String VERSION = "1.0";

    @EventHandler
    public void init(FMLInitializationEvent event) {
        System.out.println("DIRT >> "+Blocks.dirt.getLocalizedName());
    }
}
```

***

这是第 2 小节

***

### 动手尝试：启动 Minecraft

设置完成后，你可能想要启动 Minecraft

1. 点击顶部的绿色箭头启动 Minecraft。

2. 在底部菜单中启动 mod。

***

### 总结

在这一小时中，你学习了开始工作之前的要求和所需的准备工作。你学习了 Minecraft 是用 `Java` 编写的，它可以运行在任何操作系统上。这一小时还涵盖了几个你将使用的程序，包括 IDE `Eclipse` 以及 API `Forge`。最后，你设置了所需的元素。

### 问答

问 为什么我们必须使用 `Eclipse`？

答 你并不必须使用 `Eclipse`。然而，`Eclipse` 和 `Intelliij IDEA` 是仅两个已经为你配置好所有内容的 IDE。对于其他所有 IDE，你必须手动进行配置。这并不意味着你必须使用它们，但强烈建议使用。可以使用 `NetBeans` 或基础文本编辑器，但 Forge 没有为这些工具提供实用的工作空间设置。

问 为什么选择 Forge？

答 Forge 是更新最频繁的 API，努力兼容尽可能多的 mod。此外，它是开源的，允许社区提交反馈、错误修复和新功能请求。它还为最终 mod 作者提供了最简单的设置，并引导社区向行业标准的编程形式发展。

### 工作坊

现在设置已经完成，你很快就会开始编码。不过，首先你需要回答一些问题。

### 测验

1 Minecraft 用什么语言编写的？

2 使用的 API 名称是什么？

A. Modloader

B. Forge

C. Eclipse

D. Java

### 答案

1 Java。

2 答案是 B。`Eclipse` 是使用的 IDE，`Java` 是编程语言。答案 A 是另一个不再更新的 API 名称，但它也是对 Forge 功能的一种描述。

### 练习题

尝试修改 `ExampleMod` 类中的一些代码，以找出每个部分的作用。你可能会在接下来的一小时内发现这些信息有用。

## 第 2 小时：为 Forge 创建基础

在本小时内你将学习：

![Image](img/image00525.jpeg) 理解 `ExampleMod` 中的 Java

![Image](img/image00525.jpeg) 创建你自己的包

![Image](img/image00525.jpeg) 创建你自己的类文件

![Image](img/image00525.jpeg) 创建 mod 文件

在这个小时内，你首先将学习一些基础 Java。`ExampleMod` 中使用的所有代码行都将得到解释。一旦你理解了所有代码，就是时候首次创建你自定义的 `package`（包）了。包基本上是 Java 代码的文件夹。它可以用于更好地组织你的代码。然而，它也应用了关于哪些代码片段可以访问和不能访问的某些规则。当你按照当前的约定创建一个包后，就是时候创建你自己的 `mod file`（mod 文件）了。你的 mod 文件是你代码中最重要的文件。对于简单的 mod，它包含了所有代码，但即使对于最大的 mod，mod 文件中的微小错误也会导致整个 mod 禁用。

### 理解 ExampleMod 中的 Java

在第 1 小时“设置 Minecraft 开发环境”结束时，Forge 的设置已经完成。此项设置中包含了一个示例 mod。`ExampleMod` 文件如列表 2.1 所示。

```java
package com.example.examplemod;

import net.minecraft.init.Blocks;

import cpw.mods.fml.common.Mod;

import cpw.mods.fml.common.Mod.EventHandler;

import cpw.mods.fml.common.event.FMLInitializationEvent;

@Mod(modid = ExampleMod.MODID, version = ExampleMod.VERSION)
public class ExampleMod
{
    public static final String MODID = "examplemod";
    public static final String VERSION = "1.0";

    @EventHandler
    public void init(FMLInitializationEvent event)
    {
        // some example code
        System.out.println("DIRT BLOCK >> "+Blocks.dirt.getUnlocalizedName());
    }
}
```

在编写你自己的 mod 之前，了解所有代码实际的作用是非常有用的。这样，以后编写 mod 就可以做得更快、更高效。在第 3 小时“使用配方和其他小型修改”中，你将创建你的第一个自定义代码。

### 包（Packages）和导入（Imports）详解

`ExampleMod` 的第一行是 `package` 行。正如本节引言所述，包基本上是 Java 的文件夹。代码如下：

```java
package com.example.examplemod;
```

这并不是 `ExampleMod` 的完整文件路径，而只是它的一部分。这是因为这段 Java 代码无论位于什么路径下，在任何地方都能工作。然而，包中的三个文件夹无论如何都会保持不变。通常，正确的路径会由你的集成开发环境 (IDE) 处理好。在 Eclipse 中，你为此创建一个包。



文件夹路径在代码中变为包的方法非常简单。在文件资源管理器窗口中，文件夹中的文件夹通常用 `/` 隔开。在 Java 中，这是用点 `.` 完成。在这种情况下，`ExampleMod` 文件将位于 `.../com/example/examplemod` 文件夹中，在 Java 中为 `com.example.examplemod`，其中 `...` 是它可能所在的任何文件夹。如果你去安装 Forge 的地方，你会发现这个文件夹结构位于 `src/main/java`。在 Eclipse 中，你会看到一个带有包图标的文件夹位于该位置。这样的文件夹被称为 `source folder`（源文件夹）。每当你更改源文件夹内部的文件夹时，包就会改变，你必须在代码中处理这一点。

### 提示：在 Eclipse 中重命名

你可以通过点击 Eclipse 左侧包资源管理器（Package Explorer）中的包并按下 `Alt+Shift+R` 来轻松更改文件夹所在的包。这会弹出一个窗口，你可以在其中更改包名。它会自动更改被更改文件中每个文件包含包声明的代码行。

你在 `ExampleMod` 中应该熟悉的下一个内容是一组行。它们都以 `import` 开头，在 `ExampleMod` 中，它们看起来如下：

```java
package com.example.examplemod;

import net.minecraft.init.Blocks;
import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.Mod.EventHandler;
import cpw.mods.fml.common.event.FMLInitializationEvent;
```

`import` 非常有用，因为它允许程序员更流畅地引用其他类。以 `Blocks.dirt` 为例。如果没有导入，代码必须是 `net.minecraft.init.Blocks`。将导入想象为说“我熟悉这个，所以从现在起我将使用它们的名称”。每当你使用新类时，它都会带有下划线，因为 Java 不知道你的意思，你必须为它添加导入。通常，IDE 也会处理这一点。如果它没有为你完成，你可以尝试以下几种操作：

- 将鼠标悬停在新的文件（现在是红色的）上，选择 Import（导入）。
- 按 `Ctrl+Shift+O`，这将导入文件。如果有多个同名的文件，它会显示一个屏幕让你选择哪一个。
- 在源代码的任何地方点击右键，选择 `Source`（源），然后选择 `Organize Imports`（组织导入）。这与 `Ctrl+Shift+O` 相同。它还会删除任何未使用的导入。

在本书过程中选择正确的导入时，正确的选择总是与 Minecraft 相关的包之一，例如 `net.minecraft`、`cpw.mods.fml` 或 `net.minecraftforge`，除非另有说明。

### @Mod 和类

接下来是 `@Mod` 行，如下：

点击此处查看代码图片

```java
@Mod(modid = ExampleMod.MODID, version = ExampleMod.VERSION)
```

这一行比到此为止的其他行都要复杂一点。因此，它必须拆分成部分以便于理解。第一部分是 `@Mod`。这部分是一个注解。Java 中的注解是一种功能，允许编码人员为方法、类和字段附加额外信息，其他程序可以读取这些信息。

`@Mod` 需要两个参数。在 Java 中，`parameters`（参数）是随某些内容一起发送的信息组。在这种情况下，它需要两个参数发送给 `Mod` 以供 Forge 使用。这两个参数都是 `String` 类型。Java 中的 `String` 是一个用于存储字符组的类。要声明一个 `String`，你只需要输入你想要的字符并用引号括起来即可。`String` 是 Java 中 `constant`（常量）的一个示例。常量可以赋值给 `variables`（变量）。稍后将解释声明变量的代码。首先，理解 `@Mod` 这一行的代码至关重要。

## @Mod 注解

注解后的括号内包含几项内容。其中的第一个内容是 `modid`。它是 `Mod` 中的一个变量，用于跟踪 `mod ID`（模组 ID）。在 Forge 中，每个模组都有一个 mod ID。这是一个 `String`，且每个模组的 ID 必须不同。它被用于许多不同的地方，其中大部分由 Forge 处理，以确保该模组能与其他模组协同工作。要设置 `modid`，在该变量后跟着一个等号。等号右侧是它将被设置的值。在这种情况下，它会查找 `ExampleMod` 文件并选择 `MODID` 变量。这看起来可能很奇怪，明明代码就在当前文件中，却必须指定去 `ExampleMod` 文件查找。然而，根据 Java 的规定，当它读取 `@Mod` 这一行时，它还没有进入 `ExampleMod` 文件。

在 Java 中，实际的 `ExampleMod` 类从 `public class` 开头的行下方的大括号开始。那之前的所有内容都不被视为类的一部分。然而，包（package）、导入（imports）以及有时的注释放置在上方，且同样重要。类的开始看起来如下：

```java
public class ExampleMod
{
```

尽管实际的类定义行只有一行，但紧随其下方的行也包含在前面的代码片段中。这是由于 Java 的工作机制。正如你可能注意到的——而且当你自己编程时一定会发现的——Java 频繁使用不同类型的括号。括号之间的代码可以被视为一组代码。在 `ExampleMod` 的情况下，你可以将 `ExampleMod` 下方的左括号到底部右括号之间的所有代码视为一个代码组，可以称为 `ExampleMod` 类组。里面还有更小的代码组，即方法（methods）。稍后将解释。这种编码方式被称为面向对象编程 (OOP)。因为 Java 是一种 OOP 语言，代码始终会有这种结构。

`public class` 这一行对 Java 来说非常重要。它定义了类的开始位置以及类的名称。一个需要注意的重要点是，如果你更改了 `ExampleMod` 所在的文件名，那么 `public class ExampleMod` 的名称必须改为新的文件名。

## 类中的字段 (Fields)

现在你已经对类及其创建方式有了基本的了解，你需要理解类是由哪些部分组成的。在 Java 中，有几类内容可以存在于类文件中。这些是 `fields`（字段）、`methods`（方法）以及可能的其他类。所有这些都位于 `ExampleMod` 中。以下代码片段展示了 `ExampleMod` 中的字段：

点击此处查看代码图片

```java
public static final String MODID = "examplemod";
public static final String VERSION = "1.0";
```

在前面的代码片段中有两个不同的字段、变量或 `objects`（对象）。它们有许多共同点。前三个单词是你赋予 Java 字段的属性。`Public` 意味着该字段可以在每一个其他 Java 文件中访问。这本书几乎总是使用 `public` 字段。`Public` 使字段变得可见，更重要的是让它在任何地方都可用。可选的变量可见性名称有 `protected`（仅对包和子类可见）和 `private`（使其仅在类本身中可见）。

在 `public` 之后的是单词 `static`。这意味着你可以通过 `ExampleMod.MODID` 来引用该对象。如果一个字段不是静态的（static），你不能以这种方式使用它。如果它不是静态的（不需要该单词），你只能通过文件的对象来引用它。一个例子是 `init` 方法中的 `event` 参数，它很快就会被介绍。如果你使用 `event` 后跟一个点，你就可以访问任何非静态字段和方法。你不能用这种方式使用静态方法和字段。静态字段必须以完整的类名作头。正如你预期的那样，Minecraft 并没有为游戏中的每一个泥块（dirt block）准备一个独立的文件。它为每个方块使用同一个文件。这也是 OOP 代码风格的一部分。

如果你在类中为泥块设置了一个静态字段，那么这个字段对于每一个泥块来说都是相同的。非静态字段对于所有泥块可以是不同的。泥块中可能的静态字段示例是纹理（texture），因为每个泥块都有相同的纹理。泥块中可能的非静态字段示例是 x 坐标，因为每个方块的坐标都是不同的。

在 `static` 之后的是单词 `final`。`Final` 意味着字段可以初始化一次，之后永远不再更改。`final` 字段的名称应该始终全大写。如果不这样做，你的代码不会崩溃，但这是 Java 的惯例，应该始终遵守。

在三个紫色单词的右侧是单词 `String`。这个单词是实际使用的对象。在这种情况下，它创建了一个 `String` 类的对象，这是一个用于单词的标准 Java 类。

一旦你写了它应该是什么类型的字段，就需要一个名称。顶部的字段名称为 `MODID`。在名称之后，你使用 `=` 号将字段设置为某个值。等号之后的内容对于任何对象都可能不同。对于 `String`，你使用一对引号以及你想要存储其中的单词。

## 类中的方法 (Methods)

`ExampleMod` 中的接下来的以及最后几行必须作为一个组进行解释：

点击此处查看代码图片

```java
@EventHandler
public void init(FMLInitializationEvent event)
{
    // 示例代码
    System.out.println("DIRT BLOCK >> " + Blocks.dirt.getUnlocalizedName());
}
```

这段代码是一个方法。方法名是 `init`。它接收一个参数并包含两行代码。最后，它在上方还有一个注解。和变量一样，方法也可以是静态的，也可以是非静态的。这些关键字在方法上的行为与变量相同。`init` 方法没有 `static` 关键字。因此它是非静态的，这意味着它对于 `ExampleMod` 的每个实例都是不同的。

该注解是给 Forge 用的。配合参数，它确保 Forge 在设置期间读取此方法。`@EventHandler` 用于注册每一个 `FMLInitializationEvent`。有三种初始化事件：`PreInit`、`Init` 和 `PostInit`。你编写的所有代码都必须放在特定的初始化事件中。

注释之后的一行指定了该方法的类型。紫色的名称和变量一样，是你赋予方法的某些属性。`Public`、`protected`、`private` 和 `static` 的工作方式与变量完全相同。对于方法，你还有一点需要注意，那就是“返回类型”。每个方法都有返回某些内容的选项。这可以数字、一个 `String`、一个 `Block` 或者什么都没有。在这种情况下，返回类型为 `void`，意味着空。如果你的方法的返回类型是 `void` 以外的任何类型，你必须用 `return` 语句结束方法。稍后你会发现一些需要这样的方法，届时只需返回方法所需的任何内容即可。

在这种情况下，有两个紫色的关键字，之后是方法名。方法名为 `init`。方法名之后是一个括号。圆括号内是方法的参数。这一部分的第一个词是一个名为 `FMLInitializationEvent` 的类；第二个词是引用它的变量名。前一个代码段中的变量名为 `event`。

这一行之后是一个大括号，定义了方法的开始。三行之后是一个右括号，定义了方法的结束。这个方法包含两行，但只有其中一行是代码。第一行是注释。注释是你可以在文件中编写有用内容。注释说明了某物的作用、是否有任何需要修复的错误等。你可以在这些注释中写任何内容，Java 永远不会使用它们。在 Java 中，可以通过输入 `//` 创建注释。这会将该符号右侧的所有内容变成注释。

有时你可能想要一个较长的注释，或者只想让行中的一小部分作为注释。这可以通过 `/*` 和 `*/` 实现。第一个和第二个注释符号之间的任何内容 Java 都不会使用。

该方法的第二行实际上执行了某些操作。它也是一行你将经常编写的类似代码。`System.out.println` 将你在其后面括号中写的 `String` 打印到控制台。在 Eclipse 中，控制台位于底部。控制台的另一个例子是命令提示符。

这个 `syso`（编程中通常对 `System.out.println` 的简称）由两部分组成。第一部分是 `DIRT BLOCK >>`，它将完全按照那样打印在控制台上。在这个 `String` 之后是一个 `+`，这意味着将有第二个 `String` 与第一个拼接并一起打印。这里的第二个 `String` 是泥块的未本地化名称。该名称通过使用 `Blocks.dirt.getUnlocalizedName()` 来访问。`Blocks` 是一个包含所有 `Block` 对象的文件。其中一个 `Block` 对象就是 `dirt`。从这个 `dirt` 对象，通过 `getUnlocalizedName` 方法返回未本地化名称。该方法是一个返回类型的示例，类型为 `String`。在这种情况下，`System` 是类，`out` 是静态字段，而 `println` 是非静态方法。

### 提示：Eclipse 输入快捷键

在 Eclipse 中，你可以通过输入 `syso` 然后按 `Ctrl+Space` 轻松地输入 `System.out.println`。这会自动将 `syso` 变为 `System.out.println`。

### 创建你自己的包

现在你已经了解了 Java 基础并理解了 `ExampleMod` 中的代码，是时候创建你自己的 Mod 了。在开始创建你自己的 Mod 之前，你需要一个包含所有 Mod 文件和代码的包。要创建你自己的包，你需要理解 Eclipse 左侧的“项目资源管理器”（Project Explorer），如图 图 2.1 所示。

![Image](img/image00534.jpeg)

**图 2.1** 项目资源管理器

此屏幕上有许多选项，但你只需要关注的三个部分已图中用黑色高亮显示。首先，确保包名与你刚刚创建的相同。接下来，输入你将创建的类名称。因为这将是你的模组（mod）的基类，名称通常与模组相同。正如图 2.5 所示，在本书中，mod 类被称为 `SamsMod`。从现在起，如果本书提到主类、模组文件或 `SamsMod` 文件，指的都是这个主文件。当你选好类名称后，只需点击“完成（Finish）”，无需担心所有其他选项。图 2.6 显示了打开了 `SamsMod` 类的完整 Eclipse 程序。

![Image](img/image00539.jpeg)

**图 2.6** 打开了模组文件的 Eclipse。

以下列表引用了图 2.6 中显示的数字，并解释了这些区域的含义：

**1.** 这是你花费大部分时间的地方。它是代码窗口，你将在其中编写和阅读你所有的代码。

**2.** 此区域包含文件的大纲（Outline）。大纲包含了所有重要的 Java 部分，包括变量、方法和类。

**3.** 底部区域有几个不同的窗口。你最经常查看两个窗口是控制台（Console）和标记（Markers）。标记包含了代码中所有的错误和警告。控制台是 Minecraft 显示系统输出以及其他关于你的模组信息的地方。

**4.** 这里是你可以开始游戏的地方。通常，你将使用普通的绿色箭头，它会启动游戏。左侧的按钮是调试模式，允许你在玩游戏时更改部分代码。右侧的按钮会在运行前构建所有内容。

### 创建模组文件

在这一小时内，你要做的最后一件事实际上是创建模组文件。最简单的方法是复制 `ExampleMod` 的代码并将其粘贴到你的模组文件中。当你这样做时，你会得到两个错误。按照以下步骤操作以修复错误，然后进行几处修改：

**1.** 将鼠标悬停在包名行的错误上，选择“更改包声明（Change Package Declaration）”选项。或者，手动重写这一行。

**2.** 接下来，将鼠标悬停在 `ExampleMod` 下方的错误上，选择“重命名类型为（Rename Type To）”选项。也可以手动重写。

**3.** 最后，将 `MODID` 变量更改为你模组的 modid。modid 应该是每个模组都不同的。通常一个 modid 的格式为 `[你的名字]_[模组名称]`。此外，确保所有字母都是小写。

**4.** 移除 `init` 方法中的注释。你不需要这样做，但该注释不是必须的。

***

注意：让你的模组变得有趣

本书将引导你完成制作模组的编码工作。然而，还有另一件事你可能需要考虑，那就是确保人们想要玩你的模组。在创建模组时，你可以做出的重要事情之一就是确保它有一个单一且独特的构思。如果一个模组杂乱无章且没有任何关联，那么它可能不好玩。

一个专注的模组示例是：它只为游戏添加一些本该在原版中就有的配方。

***

模组文件现在看起来应该像列表 2.2。拥有不同的类名、包名和 modid 是正常的。

**列表 2.2 自定义模组文件**

点击此处查看代码图片

***



```java
package com.wuppy.samsmod;

import net.minecraft.init.Blocks;

import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.Mod.EventHandler;
import cpw.mods.fml.common.event.FMLInitializationEvent;

@Mod(modid = SamsMod.MODID, version = SamsMod.VERSION)
public class SamsMod
{
    public static final String MODID = "wuppy29_samsmod";
    public static final String VERSION = "1.0";

    @EventHandler
    public void init(FMLInitializationEvent event)
    {
        System.out.println("DIRT BLOCK >> "+Blocks.dirt.getUnlocalizedName());
    }
}
```

这与 `ExampleMod` 的功能完全相同，但这让你离创建自己的模组又近了一大步。在下一个小时里，你将学习如何创建自己的配方，以及进行一些其他小的修改。

### 动手尝试：向控制台打印内容

此时，你可能想向控制台打印一些自定义内容。

1. 将 `Blocks.dirt` 更改为 `Blocks.cobblestone`。

2. 将 `"DIRT BLOCK >> "` 更改为 `"Cobblestone >>"`。

### 总结

这一小时内，你学习了 `ExampleMod`。所有的包，包括导入等对你来说都是清晰的。你现在应该能够创建自己的模组文件。

### 问答

**Q.** 为什么需要包？

**A.** 它将你的代码与其他代码隔离开。

**Q.** 我在哪里可以找到物品？

**A.** 你可以在 `Items` 类中找到它们。

**Q.** `void` 是什么意思？

**A.** 表示没有返回值。

### 工作坊

你的模组文件现在可以使用了。通过回答以下问题确保你理解了所有的代码。

### 测验

**Q.** 下面的 modid 有什么问题？`"test_ModId"`

**A.** Mod ID 应该是小写。

**Q.** 下面的代码输出什么？

```java
System.out.println("Testing: " + "Answer");
```

**A.** 输出 `Testing: Answer`。

### 练习

你现在已经完成了模组的骨架，这意味着模组可以快速成长。现在，尝试打印一些不同的名称：

1. 创建一个打印 `"Hello World!"` 的 `System.out.println`。

2. 让控制台显示 `"I am getting an apple with the name"` 加上苹果物品的本地化名称。

3. 弄清楚下面这行代码输出什么：

```java
System.out.println("Testing Blocks: " + Blocks.bedrock.getUnlocalizedName() + " And testing Items: " + Items.book.getUnlocalizedName());
```

2. `System.out.println("I am getting an apple with the name" + Items.apple.getUnlocalizedName());`

3. 输出为：`Testing Blocks: tile.bedrock And testing Items: item.book`

# 第 3 小时：使用配方与其他小型修改

在本小时你将学习：

- ![Image](img/image00525.jpeg) 学习 Minecraft 中的配方系统
- ![Image](img/image00525.jpeg) 制作配方
- ![Image](img/image00525.jpeg) 创建无形配方
- ![Image](img/image00525.jpeg) 创建熔炼配方
- ![Image](img/image00525.jpeg) 使用特殊的 `ItemStack`
- ![Image](img/image00525.jpeg) 更改地下城的生物生成点
- ![Image](img/image00525.jpeg) 更改箱子物品
- ![Image](img/image00525.jpeg) 在 mod 文件检查结果

在本小时中，你将有机会编写自己的代码，真正开始制作自己的 mod。这一小时包含了一些最基础的 Minecraft 修改，包括配方、地下城可能性以及生成的箱子。得益于 Forge，你可以在 Minecraft 中添加各种配方。你还可以更改地下城中生成的生物。这可以用于添加你自己的生物，你也可以创建（例如）苦力爬地下城。最后，Forge 还允许你更改任何原版生成箱子的内容。原版（Vanilla）是指没有安装任何 mod 的 Minecraft。

## 学习 Minecraft 中的配方

在 Minecraft 中，有多种类型的配方。熔炼铁矿石与用它制作铁镐之间是有区别的。这应该是逻辑性的，因为你在不同的方块中进行这些操作。然而，制作木板等物品与制作镐之间也存在区别。

配方有三种类型：

- **合成（Crafting）**配方是在特定图案中使用某些物品或方块的配方。这些配方的另一个称为标准配方或形状配方。合成配方的一个例子是铁镐。
- **无形（Shapeless）**配方是没有定义形状的配方。它们也需要特定的物品和方块，但图案并不重要。无形配方的例子是更改羊毛的颜色。
- **熔炼（Smelting）**配方全部在熔炉中使用。熔炼配方没有形状，且输入永远不会超过一个物品或方块。熔炼配方的例子是金锭。

对于所有类型的配方，你只能返回一个物品或方块，但你可以返回多个相同的物品或方块。

### 制作配方

在本节中，你终于开始实际对游戏进行 mod 开发了。配方可能不是巨大的变化，但几个组合配方可以改变游戏的玩法——特别是当与自定义物品结合时，这些将在第 4 小时的“制作你的第一个物品”中解释。

你必须在 mod 文件中添加配方代码。列表 3.1 是来自第 2 小时“为 Forge 建立基础”的 mod 文件，但去掉了 `System.out.println` 行。

**列表 3.1 清洁的 mod 文件**

点击此处查看代码图像。

```java
package com.wuppy.samsmod;

import net.minecraft.init.Blocks;

import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.Mod.EventHandler;
import cpw.mods.fml.common.event.FMLInitializationEvent;

@Mod(modid = SamsMod.MODID, version = SamsMod.VERSION)
public class SamsMod
{
    public static final String MODID = "wuppy29_samsmod";
    public static final String VERSION = "1.0";

    @EventHandler
    public void init(FMLInitializationEvent event)
    {
}
```

以下代码段展示了使用较小网格、空隙和多个组件的示例：

点击此处查看代码图片。

```java
GameRegistry.addRecipe(new ItemStack(Items.arrow),
    "YZ",
    "X ",
    'X', Items.flint, 'Y', Items.stick, 'Z', Blocks.leaves
);
```

这允许你在玩家物品栏中使用叶子合成箭头。图 3.2 显示了该配方的制作过程。

![Image](img/image00541.jpeg)

**图 3.2** 玩家物品栏中较小的配方。

此外，你可能希望在配方中拥有额外的选项。例如，你可能希望返回的 `ItemStack` 大小大于 1。对于配方，你可能感兴趣的另外两点是使用的物品和结果物品或区块的元数据（metadata）。你可以在以下代码段的单个配方中看到这些内容：

点击此处查看代码图片。

```java
GameRegistry.addRecipe(new ItemStack(Items.dye, 2, 1),
    "XY",
    'X', Items.redstone, 'Y', new ItemStack(Items.dye, 1, 1)
);
```

此配方中使用的每个 `ItemStack` 现在都有三个参数。第一个仍然物品或区块。第二个是堆叠大小。结果物品或区块的堆叠大小可以大于 1，但使用的物品和区块的堆叠大小始终为 1。第三个参数是物品的伤害值（damage）。元数据从 0 开始计数，直到 15。此配方将一个石头和一个染料组合以制作两个染料。因此，伤害值为 1。

这个配方看起来可能不符合逻辑，因为它只有在染料位于右侧时才有效。对于这类配方，我们通常使用无形配方。

### 创建无形配方

无形配方的工作方式与标准配方类似。它们也设置在 `GameRegistry` 中并采用相同的参数。以下代码是一个无形配方的示例：

点击此处查看代码图片。

```java
GameRegistry.addShelessRecipe(new ItemStack(Items.dye, 2, 1),
    Items.redstone, new ItemStack(Items.dye, 1, 1)
);
```

在无形配方中，不需要字母或制作网格。只需将 `Item`、`Block` 或 `ItemStack` 对象放在输入 `ItemStack` 之后并用逗号分隔即可。除此之外，它的工作方式完全相同。在游戏中，你可以在玩家物品栏中制作这个配方，它看起来与图 3.3 相似。

![Image](img/image00542.jpeg)

**图 3.3** 无形配方。

### 创建熔炼配方

Minecraft 中的最后配方类型是熔炼配方。熔炼配方只有一个输入和一个输出槽。输入可以只有堆叠大小为 1，而输出可以大于 1。另一个需要注意的是，熔炼配方会产生经验。数量也需要为熔炼配方进行设置。以下代码是熔炼配方的示例：

点击此处查看代码图片。

```java
GameRegistry.addSmelting(Blocks.stone, new ItemStack(Blocks.stone), 0.1F);
```

第一个参数可以是 `Item`、`Block` 或 `ItemStack`，但大小始终为 1。第二个参数必须是 `ItemStack`，在这里你可以对它进行任何操作。最后一个参数是你从熔炼获得经验的 `float` 值。在 Java 中，`float` 基本上是一个数字。原版熔炼配方具有在 0.1F 到 1F 之间的经验，其中 0.1F 是圆石变成石砖的配方，1F 是钻石矿石的配方。图 3.4 显示了游戏中的此配方。

![Image](img/image00543.jpeg)

**图 3.4** 熔炼配方。

### 使用特殊的 `ItemStack`

在配方中使用特殊的 `ItemStack` 是可能的。要做到这一点，你必须首先创建一个 `ItemStack` 对象，然后将其用于配方。以下示例代码通过一把石剑和火燧创建一个锐利度为 1 的石剑。此代码使用了新类，请确保已导入它。

点击此处查看代码图片。

```java
ItemStack enchantedSword = new ItemStack(Items.stone_sword);
enchantedSword.setDamage(1);
GameRegistry.addShelessRecipe(enchantedSword, Items.stone_sword, Items.flint);
```

在 `Forge` 中，可以使用另一个非常实用的文件来更改几乎任何原版生成箱子的内容。

## 移除物品

以下代码段展示了如何从箱子中移除物品的示例（请务确保已导入新文件）：

点击此处查看代码图片。

```java
ChestGenHooks.removeItem(ChestGenHooks.DUNGEON_CHEST, new ItemStack(Items.saddle));
```

`removeItem` 是 `ChestGenHooks` 中的一个方法，接受两个参数。第一个参数是 `String`。该 `String` 指定了要从哪个箱子中移除物品。你可以手动输入它，但建议使用 `ChestGenHooks` 类中的变量之一，因为这些变量可能会变化，使用变量可以防止代码在你不经意觉的情况下崩溃。

第二个参数是必须从箱子中移除的物品 `ItemStack`。

## 添加物品

就像处理地牢怪物一样，你也可以在此处向箱子中添加新物品。以下代码展示了如何操作：

点击此处查看代码图片。

```java
ChestGenHooks.addItem(ChestGenHooks.DUNGEON_CHEST, new WeightedRandomChestContent(new ItemStack(Blocks.cobblestone), 25, 50, 10));
```

此方法需要两个参数。第一个与 `removeItem` 相同，是指定箱子的字符串。第二个参数是 `WeightedRandomChestContent`。这是另一个需要四个参数的文件。

`WeightedRandomChestContent` 的第一个参数是包含要生成的物品或方块的 `ItemStack`。第二个参数是生成时的最小堆叠数量。第三个参数是最大堆叠数量。最后一个参数是它被选中的概率。例如，火药的几概率为 10，而金苹果的几概率为 1。

## 检查 Mod 文件中的结果

完成所有这些操作后，Mod 文件看起来应该如下所示：

点击此处查看代码图片。



```java
package com.wuppy.samsmod;

import net.minecraft.enchantment.Enchantment;
import net.minecraft.init.Blocks;
import net.minecraft.init.Items;
import net.minecraft.item.ItemStack;
import net.minecraft.util.WeightedRandomChestContent;
import net.minecraftforge.common.ChestGenHooks;
import net.minecraftforge.common.DungeonHooks;
import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.Mod.EventHandler;
import cpw.mods.fml.common.event.FMLInitializationEvent;
import cpw.mods.fml.common.registry.GameRegistry;

@Mod(modid = SamsMod.MODID, version = SamsMod.VERSION)
public class SamsMod
{
    public static final String MODID = "wuppy29_samsmod";
    public static final String VERSION = "1.0";

    @EventHandler
    public void init(FMLInitializationEvent event)
    {
        //Recipes
        GameRegistry.addRecipe(new ItemStack(Items.apple),
            "XXX",
            "XXX",
            "XXX",
            'X', Blocks.leaves
        );
        GameRegistry.addRecipe(new ItemStack(Items.arrow),
            "YZ",
            "X ",
            'X', Items.flint, 'Y', Items.stick, 'Z', Blocks.leaves
        );
        GameRegistry.addShapelessRecipe(new ItemStack(Items.dye, 2, 1),
            Items.redstone, new ItemStack(Items.dye, 1, 1)
        );
        GameRegistry.addSmelting(Blocks.stone, new ItemStack(Blocks.stonebrick), 0.1F);
        ItemStack enchantedSwordItemStack = new ItemStack(Items.stone_sword);
        enchantedSwordItemStack.addEnchantment(Enchantment.sharpness, 1);
        GameRegistry.addShapelessRecipe(enchantedSwordItemStack,
            Items.flint, Items.stone_sword
        );
        //Dungeon changes
        DungeonHooks.remove("Spider");
        DungeonHooks.add("Creeper", 100);
        ChestGenHooks.removeItem(ChestGenHooks.DUNGEON_CHEST, new ItemStack(Items.saddle));
        ChestGenHooks.addItem(ChestGenHooks.DUNGEON_CHEST, new WeightedRandomChestContent(new ItemStack(Blocks.cobblestone), 25, 50, 10));
    }
}
```

物品在《我的世界》中非常重要，但基础物品的作用并不大。玩家可以持有它，可以把它掉在地面上并在配方中使用，但除了这些之外，最基础的物品并没有多少功能。然而，你可以*通过*基础物品*创造*极其有趣且实用的东西。要做到这一点，你首先需要知道如何制作基础物品，本小时涵盖了这一点。接下来的三个小时涵盖了一些特殊物品。第 6 小节“制作食物物品”将解释如何创建食物物品。第 7 小节“制作你自己的工具”涵盖了具体如何制作铁镐和其他各种工具，而第 8 小节“创建护甲”详细介绍了如何创建护甲。尽管本书侧重于这些物品，但你可以制作的不同类型的物品以及你用它们做的事情是无尽的。

现在你已经知道物品是什么了，你应该应该熟悉一些特殊情况。例如，蘑菇看起来像物品，但它们实际上是方块，因为它们可以被放置。

方块是一个无法移动的 1 × 1 × 1 米立方体。如果你对方块有更详细的解释，请阅读第 9 小节“制作你的第一个方块”的开头。

***

**注意：方块与物品**

《我的世界》的一个有趣事实是，当你拥有方块时，它们实际上都是物品。

***

箭头看起来不像物品，但它确实是。当箭头在背包中时，它是物品。然而，当用弓或发射器发射箭头时，它变成了一个实体。正如提到的，物品可以是工具、食物以及许多东西。物品还可以用于例如例如生成实体，这就是《我的世界》中实体蛋的作用。

简而言之，实体是《我的世界》世界中移动的东西。如果你想知道更多关于实体的信息，请阅读第 17 小节“学习实体”的开头。

了解你可以用物品做什么和不能做什么是非常重要的。想象你编写了一个大型而复杂的物品。然后你发现你想对它做的事情通过物品是无法实现的，而你实际上需要的是一个方块。如果你熟悉物品可以做什么和不能做什么，你就可以提前计划创建你需要的东西——并避免以后的挫败！

### 创建基础物品

是时候开始创建你自己的物品了。要开始之前，从你的 mod 文件开始。在两个 `String` 变量下方、`init` 方法上方，创建一个名为 `preInit` 的新方法。该方法的参数必须是 `FMLPreInitializationEvent`。不要忘记在方法上方添加 `@EventHandler` 注解，否则你的物品将在不显示任何错误的情况下无法工作。一旦完成，文件看起来应该像列表 4.1 所示。

**列表 4.1 带有 preInit 方法的 Mod 文件**

点击此处查看代码图片

***

```java
package com.wuppy.samsmod;

import net.minecraft.enchantment.Enchantment;

import net.minecraft.init.Blocks;

import net.minecraft.init.Items;

import net.minecraft.item.ItemStack;

import net.minecraft.util.WeightedRandomChestContent;

import net.minecraftforge.common.ChestGenHooks;

import net.minecraftforge.common.DungeonHooks;

import cpw.mods.fml.common.Mod;

import cpw.mods.fml.common.Mod.EventHandler;

import cpw.mods.fml.common.event.FMLInitializationEvent;

import cpw.mods.fml.common.event.FMLPreInitializationEvent;

import cpw.mods.fml.common.registry.GameRegistry;

@Mod(modid = SamsMod.MODID, version = SamsMod.VERSION)

public class SamsMod
{
    public static final String MODID = "wuppy29_samsmod";

    public static final String VERSION = "1.0";

    @EventHandler
    public void preInit(FMLPreInitializationEvent event)
    {
    }

    @EventHandler
    public void init(FMLInitializationEvent event)
    {
        //Recipes
        GameRegistry.addRecipe(new ItemStack(Items.apple),
                "XXX",
                "XXX",
                "XXX",
                'X', Blocks.leaves);
        GameRegistry.addRecipe(new ItemStack(Items.arrow),
                "YZ",
                "X ",
                'X', Items.flint, 'Y', Items.stick, 'Z', Blocks.leaves);
        GameRegistry.addShelessRecipe(new ItemStack(Items.dye, 2, 1),
                Items.redstone, new ItemStack(Items.dye, 1, 1));
        GameRegistry.addSmelting(Blocks.stone, new ItemStack(Blocks.stonebrick), 0.1F);
        ItemStack enchantedItemStack = new ItemStack(Blocks.stonebrick);
        enchantedItemStack.addEnchantment(Enchantment.sharpness, 1);
        GameRegistry.addShelessRecipe(enchantedItemStack,
                Items.flint);
        GameRegistry.addSmelting(Blocks.stonebrick, new ItemStack(Blocks.stonebrick), 0.1F);
        DungeonHooks.removeDungeon("Spider");
        DungeonHooks.addDungeon("Creeper");
        ChestGenHooks.addItem(new ItemStack(Items.saddle));
    }
}
```

*(注：由于原文代码块中存在逻辑混乱和重复错误，翻译时已根据代码逻辑进行了最小化修正以保持可读性)*

第二行代码通过 `GameRegistry` 文件将物品注册到 Forge 中，这确保了 Minecraft 知道该物品的存在并可以使用它。这次使用的方法是 `registerItem`，它接受两个参数。第一个参数是一个 `Item` 对象，第二个参数是它的名称。名称可以是你想要的任何内容，但最好的命名方式是使用物品的实际名称。确保物品注册表中没有重复的名称非常重要。如果有另一个名为 `Key` 的物品，它可能无法正常工作。不过，Forge 会自动在你处注册时使用的名称前面添加 `modid`。这确保了多个模组可以拥有名为 `Key` 的物品而不会产生冲突。如果书中提到了 `item registry line`，指的就是这一行。

以下代码显示了添加物品后的 `preInit` 方法和新变量。文件中的其他代码均相同，除了有几个新新导入（imports）外：

点击此处查看代码图片

```java
public static Item key;

@EventHandler
public void preInit(FMLPreInitializationEvent event)
{
    key = new ItemKey();
    GameRegistry.registerItem(key, "Key");
}
```

### 创建物品文件

为了修复物品初始化行中类名下方的错误，你需要根据初始化行中使用的名称创建一个物品文件。要创建这样的文件，将鼠标悬停在错误上并点击 `Create Class ‘...’.`。这将打开“New Java Class”窗口。在此窗口中，点击 Finish。现在你将拥有一个文件，它的内容应该像列表 4.2。

**列表 4.2 空物品文件**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.item.Item;

public class ItemKey extends Item
{

}
```

要使物品具有完全完备的功能，你必须向此文件中添加一个构造函数。构造函数是一个没有返回类型的方法，且方法名必须与类文件名完全相同。构造函数是 Java 中的一种特殊方法，用于为类创建对象。每当 `Item` 对象被创建时，此方法都会运行。`ItemKey` 的空构造函数如下：

```java
public ItemKey()
{
}
```

构造函数中必须有两行代码，Minecraft 才能识别它为一个物品并实际使用它。第一行确保物品具有某种名称：

点击此处查看代码图片

```java
setUnlocalizedName(SamsMod.MODID + "_" + "key");
```

这会将物品的未本地名称设置为某个值。物品需要一个未本地名称，否则它不会出现在任何地方。没有名称就不是一个物品。确保每个模组中每个物品的未本地名称都是是重要的。为了确保这一点，请使用你的模组的 `modid` 后跟一个下划线，最后是模组文件中物品变量的名称。这确保了不可能出现重复，因为每个安装的模组其 `modid` 都是不同的，而且你不能有两个同名的变量。

当你有一个物品时，它不会自动显示在创造模式（Creative）菜单中。这非常有用，因为并不是所有东西都应该出现在创造模式标签页中。然而，对于大多数物品，你可能希望它在某个地方可见。要做到这一点，你需要以下代码：

点击此处查看代码图片

```java
setCreativeTab(CreativeTabs.tabMisc);
```

此方法需要一个参数，即一个 `CreativeTab`。要获取正确的 `CreativeTab`，你可能需要查看列出所有标签的文件。`ItemKey` 将被添加到杂项（Miscellaneous）标签页中。

如果你现在启动游戏，你会发现创造模式菜单中有一个具有奇怪紫紫色纹理的物品。它的名称也很奇怪。

### 修复名称

要修复物品的名称，你必须为它添加本地化（localization）。默认情况下，Minecraft 中的物品名称为 `item.unlocalizedname.name`。这不是一个理想的名称，几乎总是应该被更改。你通过添加本地化来实现这一点。Minecraft 为每种语言都有不同的本地化。如果你使用不同于 `en_US`（默认的美国英语）的本地化来玩 Minecraft，它会首先尝试查找该语言下的本地化。如果没找到，它会尝试从 `en_US` 的本地化中获取。如果那里也找不到，则使用默认名称。

修复物品名称将是大量工作。首先，导航到第 1 小时中“设置 Minecraft 开发环境”创建的 forge 文件夹。然后进入 `src/main/resources`。图 4.1 显示了正确的文件夹结构。

![Image](img/image00545.jpeg)

**图 4.1** 资源的文件夹结构。

在此文件夹中，你需要创建几个自定义文件夹。第一个文件夹是 `assets`。在 `assets` 文件夹中，你需要创建一个以你的 modid 命名的文件夹，这与模组文件中的 `MODID` 相同。你需要创建的最后一个文件夹是 `lang`。如果你现在进入 Eclipse，你应该看到一个带有你使用的名称的包。正如书中所示，文件夹结构为 `assets/wuppy29_samsmod/lang`。它看起来应该像图 4.2。

![Image](img/image0546.jpeg)

**图 4.2** lang 的文件夹结构。

**注意：文件夹结构**

确保文件夹结构遵循完全相同的结构并正确列出 `modid`。如果文件夹名称有细微错误，名称和纹理将无法工作。

一旦你确定文件夹结构正确，你需要添加一个文件。该文件应命名为 `en_US.lang`。

**注意：文件扩展名**

创建后，双击文件扩展名确保是 `.lang` 而不是 `.txt`。如果是 `.txt`，你的名称本地化将无法工作。

使用你喜欢的文本编辑器打开文件。如果你在游戏中查看物品名称，它是 `item.UnlocalizedName.name`。创建的 `.lang` 文件用于为物品添加本地化名称。要为键创建本地化名称，你需要在 `.lang` 文件中加入：

点击此处查看代码图片

```text
item.wuppy29_samsmod_key.name=Key
```

第一部分是未本地化时的显示名称。之后，添加一个等号，然后在另一侧添加名称。确保未本地化名称、等号和本地化名称之间没有空格。如果有，它将无法工作或看起来很奇怪。在该文件中，未本地化和本地化名称本身可以包含空格。

**注意：翻译**



如果你想让你的模具有多种本地化，你必须添加额外的`.lang`文件。该文件的名称是语言代码，例如`en`或`nl`，后面跟着国家代码，例如`US`或`NL`。所有的语言文件名都可以在 Minecraft wiki 的[`minecraft.gamepedia.com/Language`](http://minecraft.gamepedia.com/Language)获取。

现在当你启动游戏并查看创建的物品时，名称将被修复了。

### 添加纹理

要修复物品上奇怪的紫色纹理，你必须完成几件事。首先，你必须亲自创建一个新的物品纹理。虽然具体如何创建最佳纹理不在本书的涵盖范围内，但本节将介绍基础知识。你需要使用一种你喜欢的图像编辑器软件，例如`GIMP`、`Photoshop`或`Paint`。在这些程序中的某一个，为你想要的物品创建一个 16×16 像素的图像。你在里面放什么其实并不重要。然而，重要的是保存时的文件格式和文件名。文件格式必须是`.png`。文件名必须是你可以在代码中轻松使用的名称。在书中，除非另有说明，否则名称将与变量名相同。密钥使用的物品纹理称为`key.png`，如图 4.3 所示。

![Image](img/image00547.jpeg)

**图 4.3** 密钥纹理。

现在你已经有了物品的纹理，需要把它放在 Forge 能够找到它的地方。这个位置与`.lang`文件的位置非常相似。在 forge 文件夹中，打开以下文件夹：`src\main\resources\assets\wuppy29_samsmod`，将`wuppy29_samsmod`部分替换为你模组的`modid`。路径看起来类似于图 4.4。

![Image](img/image00548.jpeg)

**图 4.4** Modid 文件夹结构。

在这个文件夹中，应该是你早之前创建的`lang`文件夹。这次，创建一个名为`textures`的文件夹。在该文件夹中，创建一个名为`items`的最终文件夹。将你之前创建的纹理文件放在其中。对于`ItemKey`，纹理如图 4.3 所示。它的文件夹结构应该类似于图 4.5。

![Image](img/image00549.jpeg)

**图 4.5** 物品纹理文件夹结构。

现在纹理已经准备好可以使用了。现在，你只需要告诉 Forge 为该物品获取该纹理。为了做到这一点，你需要在构造函数中添加一行代码。它看起来如下所示：

点击此处查看代码图片

```java
setTextureName(SamsMod.MODID + ":" + "key");
```

纹理名称必须首先是`modid`，它应该存储在你模组文件的一个变量中。然后你需要一个冒号和物品的未本地化名称。

现在，构造函数看起来像这样：

点击此处查看代码图片

```java
public ItemKey()
{
    setUnlocalizedName(SamsMod.MODID + "_" + "key");
    setTextureName(SamsMod.MODID + ":" + "key");
    setCreativeTab(CreativeTabs.tabMisc);
}
```

一旦添加了这行代码，你的物品就可以正常工作了。图 4.6 显示了游戏中的密钥。

![Image](img/image00550.jpeg)

**图 4.6** Minecraft 中的`ItemKey`。

这个文件的代码写得很好，因为同一个`String`被使用了两次。如果你想更改物品的名称，必须更改两个位置的名称。为了让这简单一点，创建一个包含`key`的`private String`。然后将`String`变量放入这些方法中。

***

### 动手尝试：重命名你的物品

更改你的物品名称并相应更改所有内容。

1. 修改`String`名称。
2. 修改本地化和纹理。

***

完成“动手尝试”活动以及本小时内的所有其他任务后，整个物品文件应该像列表 4.3 所示。

**列表 4.3 完成的 ItemKey 文件**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.item.Item;

public class ItemKey extends Item
{
    private String name = "key";

    public ItemKey()
    {
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
        setCreativeTab(CreativeTabs.tabMisc);
    }
}
```

***

现在当你启动游戏时，你应该看到具有正确名称和正确纹理的物品。

### 总结

在本小时中，你学习了如何创建一个物品。到此时，你应该理解 Minecraft 中的物品是什么以及你能对它们做什么。你还应该能够添加一个基础物品并赋予它纹理。

### 问答

**问。向 Minecraft 中添加的物品有数量限制吗？**

**答。** 有的，但几乎是不可能的。然而，你应该总是尽可能少少不同的物品。第 5 小节“在 Minecraft 中创建多个物品”。

要向同一个文件添加多个项目，你需要对在第 4 小节](#part0016.xhtml_ch04)中创建的项目文件进行细小的修改。列表 5.1 显示了第 4 小节结束的文件。

### 列表 5.1 来自第 4 小节的 ItemKey 文件

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.creativetab.CreativeTabs;

import net.minecraft.item.Item;

public class ItemKey extends Item
{
    private String name = "key";
    public ItemKey()
    {
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
        setCreativeTab(CreativeTabs.tabMisc);
    }
}
```

将此文件转换为可以注册多个项目的文件非常简单。你不能让多个项目具有相同的本地化名称；`name`变量必须为每个`ItemKey`实例是不同的。以下步骤可以实现这一点：

1. `String name`变量。
2. 为构造函数添加一个名为`itemName`的`String`。
3. 在使用`name`的地方使用`itemName`。

完成后，项目文件应该像列表 5.2 所示。

### 列表 5.2 用于多个项目的 ItemKey 文件

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.creativetab.CreativeTabs;

import net.minecraft.item.Item;

public class ItemKey extends Item
{
    public ItemKey(String itemName)
    {
        setUnlocalizedName(SamsMod.MODID + "_" + itemName);
        setTextureName(SamsMod.MODID + ":" + itemName);
        setCreativeTab(CreativeTabs.tabMisc);
    }
}
```

当你拥有这样的文件时，mod 文件中的`ItemKey()`部分会出现错误。该错误是因为构造函数中缺少`String`。要修复此问题，请在括号中添加`String`。对于该项目，`itemName`将是`greyKey`。这意味着纹理和本地化名称必须从`key`改为`greyKey`。为了清晰起见，项目变量也将重命名为`greyKey`。更改此项后，`preInit`行应该如下：

点击此处查看代码图片

```java
public static Item greyKey;

@EventHandler
public void preInit(FMLInitializationEvent event)
{
    greyKey = new ItemKey("greyKey");
    GameRegistry.registerItem(greyKey, "GreyKey");
}
```

要添加第二个项目，只需复制项目代码并在每处更改名称。以下代码包含了名为`redKey`的第二个项目。本地化和纹理已按相同名称添加。

点击此处查看代码图片

```java
public static Item greyKey;
public static Item redKey;

@EventHandler
public void preInit(FMLInitializationEvent event)
{
    greyKey = new ItemKey("greyKey");
    redKey = new ItemKey("redKey");
    GameRegistry.registerItem(greyKey, "GreyKey");
    GameRegistry.registerItem(redKey, "RedKey");
}
```

`en_US.lang`文件如下：

点击此处查看代码图片

```text
item.wuppy_samsmod_greyKey.name=Grey Key
item.wuppy_samsmod_redKey.name=Red Key
```

最后，`redKey.png`已添加到 items 文件夹中，与现有纹理相同的位置。它看起来图 5.1。

![Image](img/image00551.jpeg)

**图 5.1** 红色项目。

文件夹路径应该被添加并看起来像图 5.2。

![Image](img/image00552.jpeg)

**图 5.2** 项目纹理路径。

### 动手尝试：创建项目

你将在本书中使用几个项目，例如从方块或实体掉落。创建一个名为`samdust`的项目另一个`samingot`。使用你在`ItemKey`中中学的知识，使用单个项目文件`ItemSamGeneric`创建它们。

项目在 mod 文件中如下所示：

点击此处查看代码图片

```java
public static Item samdust;
public static Item samingot;
```

以下代码需要添加到`preInit`方法中：

点击此处查看代码图片

```java
samdust = new ItemSamGeneric("samdust");
samingot = new ItemSamGeneric("samingot");
GameRegistry.registerItem(samdust, "SamDust");
GameRegistry.registerItem(samingot, "SamIngot");
```

最后，`ItemSamGeneric`将看起来像列表 5.3。

### 列表 5.3 ItemSamGeneric

点击此处查看代码图片

```java
package com.wuppy.samsmod.items;

import com.wuppy.samsmod.SamsMod;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.item.Item;

public class ItemSamGeneric extends Item
{
    public ItemSamGeneric(String name)
    {
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
        setCreativeTab(CreativeTabs.tabMisc);
    }
}
```

这些项目的纹理显示在图 5.3 和 5.4 中。图 5.5 和 5.6 显示了游戏中的项目。

![Image](img/image00553.jpeg)

**图 5.3** 尘纹理。

![Image](img/image00554.jpeg)

**图 5.4** 锭纹理。

![Image](img/image00555.jpeg)

**图 5.5** 尘在游戏中。

![Image](img/image00556.jpeg)

**图 5.6** 锭在游戏中。

现在你已经了解了什么是元数据，你应该在项目尝试中添加它。目前有两个项目几乎完全相同。使用不同的项目 ID 是浪费的。对于单个 mod 你不会达到限制，但许多人会同时运行 100 多个 mod。在这种情况下，项目总数可能会接近限制（30000）。因此，明智地使用尽可能少的不同项目。实现这一点最简单的方法是使用元数据。

### 为项目添加元数据

元数据同时用于项目和方块。它可以用于在不使用多个项目 ID 的情况下拥有多个项目。元数据的例子是染料。它们本质上是同一个项目。与其使用 16 个不同的 ID，所有的都保存在一个中。现在你知道元数据是什么，你应该在两个关键项目中添加它。要在项目中使用元数据，你必须更改几处。首先，你需要对构造函数进行一些更改。其次，你需要创建一个让每个项目具有不同名称的方法，这比现在要复杂一点。第三，你需要添加多个图像。最后，你需要告诉 Minecraft 有多少个元数据以及应该添加到创意菜单的数量。

### 修改构造函数

在构造函数中删除`setTextureName`行。构造函数的参数也应该被删除。完成这些操作后，构造函数应该如下所示：

点击此处查看代码图片

```java
public ItemKey()
{
    setUnlocalizedName(SamsMod.MODID + "_" + "key");
    setCreativeTab(CreativeTabs.tabMisc);
}
```

### 注意：移除名称

不要忘记更改任何对已构造函数的引用。在这种情况下，更改项目初始化行。

你需要在构造函数中添加一个方法，名为`setHasSubTypes`。该方法接受一个参数，类型为`boolean`。`boolean`可以可以是`true`也可以是`false`。在这个方法中，它必须是`true`。

你必须将`setUnlocalizedName`方法中的代码改回原来的样子，即使用`MODID + "_"`并以物品名称结尾。这意味着`ItemKey`只能用于一个带有元数据（metadata）的特定物品。让`ItemKey`支持多个带有元数据的物品将工作量巨大，在这种情况下，编写多个文件要简单得多。带有元数据的`ItemKey`的未本地化名称为`key`。

完成这些操作后，构造函数应该看起来像下面的代码。这段代码会在`SamsMod`中产生一个错误，你稍后会修复它。

点击此处查看图片

```java
public ItemKey()
{
    setUnlocalizedName(SamsMod.MODID + "_" + "key");
    setHasSubtypes(true);
    setCreativeTab(CreativeTabs.tabMisc);
}
```

`setHasSubTypes`确保物品可以拥有元数据。你还必须确保每个元数据都有不同的名称。

### 修复名称

现在你需要在`ItemKey`文件中添加一个新变量。使用元数据时，你需要一个可以存储每个子物品名称的变量。为了实现这一点，可以使用`String`数组。首先，像你处理`String name`那样创建一个基础的`String`变量。现在你必须将此变量改为`String`数组。这样做的方法是在`String`后面添加`[]`。现在，在逗号之后添加等号，然后两个大括号。在大括号中添加元数据的名称。因为它们是`String`类型，请用引号括元数据名称，并用逗号分隔不同的值。对于一个灰色和一个红色的钥匙，名称变量看起来如下代码段：

点击此处查看图片

```java
private String[] name = {"grey", "red"};
```

接下来，为你之前从构造函数中删除的`setUnlocalizedName`方法添加一个替换项。你需要用来替换它的方法叫做`getUnlocalizedName`。与普通物品使用的`setUnlocalizedName`的区别在于，前者使用了`setUnlocalizedName`，而这里的`getUnlocalizedName`被重写成了其他内容。带有元数据的物品的`getUnlocalizedName`代码应该像这样：

点击此处查看图片

```java
public String getUnlocalizedName(ItemStack par1ItemStack)
{
    int metadata = MathHelper.clamp_int(par1ItemStack.getItemDamage(), 0, 15);
    return super.getUnlocalizedName() + "." + name[metadata];
}
```



`getUnlocalizedName` 是一个返回 `String` 的方法。该方法在 Minecraft 中被频繁使用。该方法接受一个参数，即 `ItemStack`。由于你正在编写方法，不需要担心它从哪里来。Minecraft 会在某处带着 `ItemStack` 调用 `getUnlocalizedName`。通常情况下，它会使用 `Item` 类中的方法，但如果是 `ItemKey`，它将使用 `ItemKey` 中的那个。

此方法中有两行。第一行基本上获取参数中 `ItemStack` 的元数据并将其存储在变量中。第二行稍微复杂一点。它以 `super.getUnlocalizedName` 开始。这会让 `Item` 中的 `getUnlocalizedName` 执行。像普通物品一样，它返回物品的标准未本地化名称。然而，对于每个元数据物品，结果都是相同的，这会产生问题，因为 Minecraft 将无法将它们区分。为了修复这个问题，后面跟着一个点，最后是 `name` 变量中设置的名称。

如之前所述，此方法是从 `Item` 类中的另一个方法重写而。如果 Minecraft 发生更新且 `Item` 类中的方法名称发生了变化，此方法将停止工作。然而，它不会通过你它没有在工作。为了确保你能注意到这种变化，应该在方法上方添加一个 `@Override` 注解。这可以确保如果方法发生了变化，它会报错。这听起来可能很糟糕，但它让跟踪 Minecraft 代码中的更改并在你的代码中相应进行更改变得容易得得多。因此，对于任何重写自你代码之外其他方法的方法，都应该添加 `@Override` 注解。

### 修复纹理

要修复纹理，你需要一个新的变量和两个新方法。变量很简单。它应该是一个私有的 `IIcon[]`。名称并不重要，但本书中将使用 `icons` 作为名称。`IIcon` 的一个问题是该文件只存在于 Minecraft 客户端。如果你尝试在服务器上创建此变量，它将会崩溃并提示找不到文件。为了修复这个问题，你必须在上方添加一个注解，指定它只能在客户端使用。该变量及其注解的形式如下：

```java
@SideOnly(Side.CLIENT)
private IIcon[] icons;
```

### 注册图像

现在你有一个空的 `IIcon` 数组。它必须被填充。它看起来如下：

点击此处查看图片

```java
@SideOnly(Side.CLIENT)
@Override
public void registerIcons(IIconRegistry par1Registry)
{
    icons = new IIcon[name.length];
    for(int i = 0; i < name.length; i++)
    {
        icons[i] = par1Registry.registerIcon(SamsMod.MODID + ":key" + name[i]);
    }
}
```

这个方法看起来可能很复杂，但其实很简单。你应该注意到，这个方法有两个注解：`@SideOnly` 和 `@Override`。你始终可以在方法、变量或类上拥有多个注解。在这种情况下，它确保该方法只在客户端运行，并且当该方法在后续版本中不再存在时报错。

### 使用图像

现在文件已经注册了多个图标，但如果不告诉它，物品不知道如何使用该数组。为了告诉它使用图标数组并为每个元数据提供不同的纹理，你需要以下方法：

点击此处查看图片

```java
@Override
public IIcon getIconFromDamage(int par1)
{
    return icons[par1];
}
```

这是一个非常简单的方法，其功能正如其名义所示。它根据伤害值（damage value）获取图标。该方法中的 `par1` 参数是元数据，它根据该数字返回 `icons` 数组中的索引。

如果你尝试使用一个没有名称且因此没有分配纹理的物品，该方法将会崩溃，所以请确保这种情况不会发生。

最后，你必须添加另一个方法，以确保物品的每个元数据都能创造模式（Creative menu）中显示。该方法的形式如下：

点击此处查看代码图片

```java
@SuppressWarnings({ "unchecked", "rawtypes" })
@SideOnly(Side.CLIENT)
@Override
public void getSubItems(Item par1, CreativeTabs par2CreativeTabs, List par3List)
{
    for (int x = 0; x < name.length; x++)
    {
        par3List.add(new ItemStack(this, 1, x));
    }
}
```

该方法包含一个你尚未见过的新注解，叫做 `@SuppressWarnings`。Minecraft 的编码方式使得 Java 有相当多的警告。这些警告大部分完全不是问题，但对于许多人来说，到处都是黄色横线会非常困恼。`@SuppressWarnings` 注解确保 `getSubItems` 方法中不会出现那些黄线。

该方法包含一个 `for` 循环。第二个数字确保了循环次数不会超过物品的最大元数据。在 `for` 循环中，它将一个大小为 1 且带有循环体内部元数据的 `ItemKey ItemStack` 添加到 `par3List` 中。这确保了它出现在创造模式中。

### 添加元数据后的代码

整个 `ItemKey` 文件应该看起来像列表 5.4。

### 列表 5.4 带有元数据的 ItemKey

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import java.util.List;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.item.Item;
import net.minecraft.item.ItemStack;
import net.minecraft.util.IIcon;
import net.minecraft.util.MathHelper;
import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class ItemKey extends Item
{
    private String[] name = {"grey", "red"};

    @SideOnly(Side.CLIENT)
    private IIcon[] icons;

    public ItemKey()
    {
        setUnlocalizedName(SamsMod.MODID + "_" + "key");
        setHasSubtypes(true);
        setCreativeTab(CreativeTabs.tabMisc);
    }

    @Override
    public String getUnlocalizedName(ItemStack par1ItemStack)
    {
        int metadata = MathHelper.clamp_int(par1ItemStack.getItemDamage(), 0, 15);
        return super.getUnlocalizedName() + "." + name[metadata];
    }

    @SideOnly(Side.CLIENT)
    @Override
    public void registerIcons(IIconRegister par1IconRegister)
    {
        icons = new IIcon[name.length];
        for(int i = 0; i < icons.length; i++)
        {
            icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "key" + " " + name[i]);
        }
    }

    @Override
    public IIcon getIconFromDamage(int par1)
    {
        return icons[par1];
    }

    @SuppressWarnings({ "unchecked", "types" })
    @SideOnly(Side.CLIENT)
    @Override
    public void getSubItems(Item par1, CreativeTabs par2CreativeTabs, List par3List)
    {
        for (int x = 0; x < name.length; x++)
        {
            par3List.add(new ItemStack(this, 1, x));
        }
    }
}
```

你还需要对 mod 文件进行几处更改。当你向 mod 文件中添加物品时，你使用了两次 `ItemKey`，这现在已不可行，因为两个物品都通过元数据合并在一起了。任何与 `redKey` 相关的代码将被删除，而 `greyKey` 将更改为 `key`。`GreyKey` 的 `registerItem` 名称也将更改为 `Key`。mod 文件应该看起来像列表 5.5。

### 列表 5.5 带有元数据的 Mod 文件

点击此处查看代码图片

```java
package com.wuppy.amsmod;

import net.minecraft.enchantment.Enchantment;
import net.minecraft.init.Blocks;
import net.minecraft.init.Items;
import net.minecraft.item.Item;
import net.minecraft.item.ItemStack;
import net.minecraft.util.WeightedRandom;
import net.forge.common.ChestGenHooks;
import net.forge.common.DungeonHooks;
import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.Mod.EventHandler;
import cpw.mods.fml.common.event.FMLInitializationEvent;
import cpw.mods.fml.common.event.FMLPreInitializationEvent;
import cpw.mods.fml.common.registry.GameRegistry;

@Mod(modid = SamsMod.MODID, version = SamsMod.VERSION)
public class SamsMod
{
    public static final String MODID = "wuppy29_amsmod";
    public static final String VERSION = "1.0";
    public static Item key;

    @EventHandler
    public void preInit(FMLPreInitializationEvent event)
    {
        key = new ItemKey();
        GameRegistry.registerItem(key, "Key");
    }

    @EventHandler
    public void init(FMLInitializationEvent event)
    {
        //Recipes
        GameRegistry.addRecipe(new ItemStack(Items.apple),
            "XXX",
            "XXX",
            "XXX",
            'X', Blocks.leaves
        );
        GameRegistry.addRecipe(new ItemStack(Items.arrow),
            "YZ",
            "X ",
            'X', Items.flint, 'Y', Items.stick, 'Z', Blocks.leaves
        );
        GameRegistry.addShapeless(new ItemStack(Items.apple),
            Items.flint, Items.stick, Blocks.leaves
        );
    }
}
```

如果你现在启动游戏，你会发现两个物品都显示在创造模式中。然而，名称现在还没有生效。要修复这个问题，你必须更改 `.lang` 文件。对于 `ItemKey`，`.lang` 文件如下：

点击此处查看代码图片

```text
item.wuppy29_amsmod_key.grey.name=Grey Key

item.wuppy29_amsmod_key.red.name=Red Key
```

## Q. 物品的元数据最大数量是多少？

## A.

**一个物品的最大元数据数量大约也是 32,000 个。不过，你必须修改 `getUnlocalizedName` 方法中的元数据变量，使其不再限制为 15。**

## Q. 方块之类的东西有元数据吗？

## A.

**是的，有的。这在第 10 节 “智能地创建多个方块”中有所介绍。**

### 工作坊

现在你已经知道如何智能地向 Minecraft 中添加多个物品。大多数模组都包含大量物品，因此掌握这些技术非常重要。

### 测验

1. 如果你没有为物品的每个元数据使用不同的名称，会发生什么？
2. 如果你的物品显示黑色和紫色的纹理，你的哪里有问题？
3. 你该如何判断纹理名称是否错误？

### 答案

1. 对 Minecraft 来说，它们都是同一个，正因为如此，会发生一些非常奇怪的事情。
2. 物品的纹理要么名称不对，要么不在正确的文件夹中。确保检查文件夹结构是否遵循正确的规则。或者，确保纹理名称与物品的未本地化名称（unlocalized names）一致。
3. 使用 `System.out.println` 打印出 `registerIcons` 方法中冒号后面的部分。

### 练习

在本小时创建的物品添加第三个元数据。*提示：*你只需要编辑该物品文件即可。同时不要忘记编辑 `.lang` 文件并添加新纹理。

# 第 6 节 制作食物物品

在本节你将学习到：

- ![Image](img/image00525.jpeg) 理解 Minecraft 中的食物
- ![Image](img/image00525.jpeg) 创建一个食物物品
- ![Image](img/image00525.jpeg) 添加药水效果

在本节中，你将学习如何制作你的第一个特殊物品：你将创建一个食物——浆果。你将在第 11 节 “让你的方块独一无二”中，当你为它创建一个灌木时使用这个物品。然后，在第 14 节 “生成植物”中，你将学习如何让灌木出现在世界中以便最终可以使用。然而，在制作食物物品之前，你应该了解关于 Minecraft 食物的一些知识。

### 理解 Minecraft 中的食物

当你玩 Minecraft 时，会在图形用户界面（GUI）中看到一个饥饿条。然而，游戏中实际上有两个条。可见的饥饿条在代码中被称为 `foodLevel`。另一个不可见的条被称为 `foodSaturationLevel`（饱和度）。这些数值的工作方式是：只要饱和度高于零，`foodLevel` 就会保持不变，而 `foodSaturationLevel` 会下降。当 `foodLevel` 降到某个水平以下时，它要么停止下降，要么让你挨饿，这取决于你所玩的难度等级。当 `foodSaturationLevel` 变为零时，除了 `foodLevel` 开始下降外，什么都不会发生。

当你吃掉一个食物物品时，饱和度和饥饿值都会增加。某些食物物品会让饱和度增加很多，但饥饿值只增加一点。另一些食物物品会让饱和度增加一点，但饥饿值增加很多。当 `foodLevel` 为 1 且饱和度增加时，`foodLevel` 保持不变；即使你应该因为 `foodLevel` 受到饥饿伤害，你也不会受到伤害。在制作合适的食物物品时，确保你的物品在饥饿值和饱和度之间达到平衡是非常重要的。

你应该知道关于食物的另一个重要细节：你可以在 Minecraft 中使用骨头驯服狼。当你有一个宠物狼时，可以使用某些类型的食物治愈它。在创建食物物品时，你可以设置是否可以使用该食物来治愈狼。因此，在创建食物物品时，确定狼是否应该食用它是很重要的。

### 创建食物物品

现在你已经了解 Minecraft 中食物是如何运作的，是时候创建你自己的食物物品了。要做到这一点，你需要在模文件中添加新物品。

### 模文件

首先，在模文件中添加一个新物品：

```java
public static Item berry;
```

然后，在 `preInit` 方法中：

```java
berry = GameRegistry.registerItem(berry, "Berry");
```

### 创建物品类

创建 `ItemBerry` 类，看起来应该是这样的：



```java
package com.wuppy.smod;

import net.minecraft.item.ItemFood;

public class ItemBerry extends ItemFood {

    public ItemBerry(int food, float saturation, boolean wolfFood) {
        super(food, saturation);
    }
}
```

## 注意：Super

切勿在构造函数中的 `super` 行之前添加代码，否则你将得到错误。

---

你必须在 mod 文件的物品初始化行中添加名称。对于浆果物品，名称将为 `berry`。不要忘记为物品添加本地化和纹理，就像你对基础物品做的那样。图 6.1 显示了浆果的纹理。

![Image]

**图 6.1** 浆果纹理。

浆果的本地化看起来如下：

点击此处查看代码图像

```text
item.wuppy29_samsmod_berry.name=Berry
```

现在当你启动游戏时，你应该能够食用该物品，而且它应该具有正确的纹理和正确的名称。

---

## 动手尝试：显示行号

你可能已经注意到，大文件有时看起来非常复杂。然而，如果你犯了错误，错误日志通常会返回问题所在的代码行。

你的 Eclipse 界面应该类似于图 6.2。

![Image]

**图 6.2** Eclipse 界面。

在阅读代码、编写代码和修复崩溃时，在屏幕上显示行号将很有用。请完成以下步骤来实现。

1. 点击 Eclipse 界面顶部的 `Window` 菜单。
2. 选择 `Preferences` 选项，如图 6.3 所示。在此窗口中，你需要找到行号的选项。

   ![Image]

   **图 6.3** `Window` 菜单上的 `Preferences` 命令。

   `Preferences` 窗口打开了，如图 6.4 所示。

   ![Image]

   **图 6.4** `Preferences` 窗口。

3. 展开 `General` 选项、`Editors` 选项，然后点击 `Text Editors`。不要展开 `Text Editors`，只需点击单词本身。`Text Editors` 选项出现在右侧面板中，如图 6.5 所示。

   ![Image]

   **图 6.5** `Text Editors` 选项。

4. 勾选 `Show Line Numbers` 复选框，如图 6.5 中高亮所示。
5. 最后，点击 `Apply` 然后点击 `OK` 保存这些设置并显示行号。

如图 6.2 所示的相同类现在应该像图 6.6。你应该看到行号现在显示在代码的左侧。

![Image]

**图 6.6** 显示行号的 Eclipse 界面。

---

## 添加药水效果

蜘蛛眼和腐肉等物品在物品被食用时会给玩家提供药水效果。你可以使用 `setPotionEffect` 方法来实现。例如，`setPotionEffect` 方法可能如下所示：

```java
setPotionEffect(Potion.moveSpeed.id, 15, 0, 1F);
```

该方法有四个参数。

- 第一个参数是一个数字。此数字用于选择使用哪种药水效果。实现此点的方法不是直接输入数字，而是从 `Potion` 类中选择药水并在末尾添加 `.id`。这会将药水转换为药水的 ID，从而使其在该方法可用。
- 第二个参数是药水的持续时间（以秒为单位）。在这种情况下，药水影响玩家 15 秒。
- 第三个参数是药水的等级。这些等级从 0 开始，最高等级取决于药水类型。虽然你在游戏中创建的药水等级通常不会超过 1（在游戏中显示为 II），但某些药水可以获得更高的等级，因此也更有效。
- 最后一个参数是效果发生的概率。这个数字的范围从 `0F` 到 `1F`，值越高概率越高。`1F` 表示以 100% 的概率给玩家提供效果。

---

## 动手尝试：玩玩药水

通过不同的药水类型、持续时间和等级来玩玩药水吧。有一些隐藏的药水，你通常在 Minecraft 中无法使用。其中一个例子是跳跃高度药水。

---

如果你尝试在同一个物品上使用多个药水效果，将会遇到一些问题。一个物品可以拥有的药水最大数量是一个。通过遵循本节结束练习中的说明，可以向此物品添加第二个药水效果。

如果你有一个主要用于药水效果的食物物品，你可能想制作它。

为在本小时创建的食物物品添加第二个药水效果。要做到这一点，你需要复制并更改 `setPotionEffect` 方法名称，更改变量名称并将其添加到文件中，然后重写 `onFoodEaten` 方法以使用第二个药水效果。最后，不要忘记在构造函数中使用新的药水效果方法。

新的 `ItemBerry` 文件应该与列表 6.4 相似。

### 列表 6.4 带有第二个药水效果的 ItemBerry

点击此处查看代码图像

```java
package com.wuppy.samsmod;

import net.minecraft.entity.player.EntityPlayer;
import net.minecraft.item.ItemFood;
import net.minecraft.item.ItemStack;
import net.minecraft.potion.Potion;
import net.minecraft.potion.PotionEffect;
import net.minecraft.world.World;

public class ItemBerry extends ItemFood
{
    private int secondpotionId;
    private int secondpotionDuration;
    private int secondpotionAmplifier;
    private float secondpotionEffectProbability;

    public ItemBerry(int food, float saturation, boolean wolfFood, String name)
    {
        super(food, saturation, wolfFood);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
        setPotionEffect(Potion.moveSpeed.id, 15, 0, 1F);
        setSecondPotionEffect(Potion.digSpeed.id, 15, 0, 1F);
        setAlwaysEdible();
    }

    protected void onFoodEaten(ItemStack par1ItemStack, World par2World, EntityPlayer par3EntityPlayer)
    {
        super.onFoodEaten(par1ItemStack, par2World, par3EntityPlayer);
        if (!par2World.isRemote && this.secondpotionId > 0 && par2World.rand.nextFloat() < this.secondpotionEffectProbability)
        {
            par3EntityPlayer.addPotionEffect(new PotionEffect(this.secondpotionId, this.secondpotionDuration * 20, this.secondpotionAmplifier));
        }
    }

    public ItemFood setSecondPotionEffect(int par1, int par2, int par3, float par4)
    {
        this.secondpotionId = par1;
        this.secondpotionDuration = par2;
        this.secondpotionAmplifier = par3;
        this.secondpotionEffectProbability = par4;
        return this;
    }
}
```

## 第 7 小时：制作自己的工具

### 你在本小时内将学到：

- ![Image](img/image00525.jpeg) 创建一个 `ToolMaterial`
- ![Image](img/image00525.jpeg) 创建一个铁镐
- ![Image](img/image00525.jpeg) 为挖掘不同的方块创建特殊工具

本小时涵盖了另一种特殊的物品类型：工具。工具在 Minecraft 中非常常用，因为它们几乎是你除创造模式之外可以用来移除方块的唯一物品。此外，剑在 Minecraft 中被视为工具，并用于战斗。没有工具，你在 Minecraft 中就做不了什么。因此，了解如何制作它们是有帮助的。你可以在 [`minecraft.gamepedia.com/Tools`](http://minecraft.gamepedia.com/Tools) 找到更多关于工具的信息。

### 创建 ToolMaterial

在创建自定义工具之前，你必须创建一个自定义的 `ToolMaterial`。正如其名所示，`ToolMaterial` 是制作工具工具的材料。这种材料对工具非常重要。它告诉 Minecraft 该工具可以挖掘哪些方块、会造成多大的伤害、挖掘速度有多快、可以使用多久以及其他几点内容。要创建你自己的 `ToolMaterial`，请在 mod 文件中 `Item` 变量下方添加以下代码：

点击此处查看代码图像

```java
ToolMaterial samium = EnumHelper.addToolMaterial("samium", 3, 1000, 9.5F, 3.5F, 10);
```

通过这段代码，你创建了一个名为 `samium` 的 `ToolMaterial`。你使用一个名为 `EnumHelper` 的文件创建它。在该文件中有一个名为 `addToolMaterial` 的方法，它接受六个参数。

第一个参数是材料的名称。名字并不重要。唯一需要记住的是它应该是唯一的名称，并且你可以很容易识别出它是你想要的 `ToolMaterial`。

第二个参数是工具的挖掘等级。挖掘等级决定了你可以挖掘哪种类型的方块。如果你进入 `Item` 内部的 `ToolMaterial` 类，你将看到什么材料具有哪个挖掘等级。如果材料的挖掘等级较高，它就能挖掘更多方块。挖掘等级 3 意味着你可以像钻石镐一样挖掘。这意味着你可以挖掘除了基岩（无法破坏）之外的所有东西。

第三个参数是工具的使用次数。这个参数决定了工具在损坏前可以使用多少次。

第四个参数是工具的挖掘速度。这个参数告诉 Minecraft 挖掘速度有多快。在 `ToolMaterial` 类中，你可以看到不同的挖掘速度。数值越高，工具挖掘得越快。

第五个参数是工具造成的伤害。这个参数决定了工具对实体造成的伤害。在 `ToolMaterial` 类中，你可以看到不同的伤害值。数值越高，工具造成的伤害越大。

第六个参数是工具的附魔性。这个参数决定了工具获得附魔的概率。在 `ToolMaterial` 类中，你可以看到不同的附魔概率。

### 创建铁镐

现在你已经有了 `ToolMaterial`，是时候在工具中使用它了。

### Mod 文件代码

要将工具添加到 mod 文件，请在 mod 中添加以下代码：

点击此处查看代码图像

```java
public static Item sampickaxe;
ToolMaterial samium = EnumHelper.addToolMaterial("samium", 3, 1000, 9.5F, 3.5F, 10);
```

此外，在 `preInit` 方法中添加以下代码：

点击此处查看代码图像

```java
sampickaxe = new ItemSamPickaxe(samium, "sampickaxe");
GameRegistry.registerItem(sampickaxe, "SamPickaxe");
```

这些代码对你来说应该很熟悉了。唯一不同的是 `ItemSamPickaxe` 将 `ToolMaterial` 作为其第一个参数。这是创建工具所需的，因为 `ItemSamPickaxe` 类将被扩展。

### 创建 ItemSamPickaxe 类

与之前的小小时创建的其他物品一样，将鼠标悬停在 `ItemSamPickaxe` 上并选择 Create Class。然后将继承类型从 `ItemTool` 改为 `ItemPickaxe`。这会在 `ItemSamPickaxe` 下产生错误，提示它应该有一个带有参数 `ToolMaterial` 的构造函数。不要这样做。相反，请添加列表 7.1 所示的代码。

### 列表 7.1 ItemPickaxe 构造函数

点击此处查看代码图像

```java
package com.wuppy.samsmod;

import net.minecraft.item.ItemPickaxe;

public class ItemSamPickaxe extends ItemPickaxe
{
    public ItemSamPickaxe(ToolMaterial material, String name)
    {
        super(material);
    }
}
```

这段代码确保了 mod 文件中使用的 `name` 参数仍然可以使用。它还确保了 `ItemPickaxe` 中仅带 `ToolMaterial` 的构造函数也被调用，这是必要的。

现在，就像任何其他物品文件一样，在构造函数中添加以下两行代码：

点击此处查看代码图像

```java
setUnlocalizedName(SamsMod.MODID + "_" + name);
setTextureName(SamsMod.MODID + ":" + name);
```

此外，与其他项目一样，不要忘记添加本地化内容，其格式类似于下面针对铁镐的代码段。请将以下代码添加到 `en_US.lang` 文件中：

点击此处查看代码图片

```text
item.wuppy29_samsmod_sampickaxe.name=Sam's Pickaxe
```

并且不要忘记添加纹理。Sam 的铁镐使用了图 7.1 所示的纹理。

![Image](img/image00565.jpeg)

**图 7.1** Sam 的铁镐的纹理。

图 7.1 将作为 `sampickaxe.png` 保存在 `items` 文件夹中。

现在，你在 Minecraft 中拥有了一个功能完整的铁镐。完整的 `SamsPickaxe` 类显示在列表 7.2 中。

**列表 7.2** 完成的 SamsPickaxe

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.item.Item.ToolMaterial;
import net.minecraft.item.ItemPickaxe;

public class ItemSamPickaxe extends ItemPickaxe
{
    public ItemSamPickaxe(ToolMaterial material, String name)
    {
        super(material);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
    }
}
```

## 动手尝试：创建其他工具

尝试在 Minecraft 中创建所有其他工具。如果你在某处卡住了，可以查看 mod 类中的代码以及列表 7.3 到 7.8 中的 `Item` 类。

在 mod 文件中添加其他工具的代码在列表 7.3 和 7.4 中所示。

**列表 7.3** 在 `preInit` 方法之外包含所有工具代码的 Mod 文件

点击此处查看代码图片

```java
public static Item sampickaxe;

public static Item samaxe;

public static Item samhoe;

public static Item samshovel;

public static Item samsword;

ToolMaterial samium = EnumHelper.addToolMaterial("samium", 3, 1000, 9.5F, 3.5F, 10);
```

**列表 7.4** `preInit` 中的所有新代码

点击此处查看代码图片



```java
sampickaxe = new ItemSamPickaxe(samium, "sampickaxe");

samaxe = new ItemSamAxe(samium, "samaxe");

samhoe = new ItemSamHoe(samium, "samhoe");

samshovel = new ItemSamShovel(samium, "samshovel");

samsword = new ItemSamSword(samium, "samsword");

GameRegistry.registerItem(sampickaxe, "SamPickaxe");

GameRegistry.registerItem(samaxe, "SamsAxe");

GameRegistry.registerItem(samhoe, "SamsHoe");

GameRegistry.registerItem(samshovel, "SamsShovel");

GameRegistry.registerItem(samsword, "SamsSword");
```

列表 7.5 到 7.8 包含了四个新工具的代码。

### 列表 7.5 `ItemSamAxe` 类

点击此处查看代码图片。

```java
package com.wuppy.samsmod;

import net.minecraft.item.Item.ToolMaterial;

import net.minecraft.item.ItemAxe;

public class ItemSamAxe extends ItemAxe

{
    public ItemSamAxe(ToolMaterial material, String name)
    {
        super(material);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
    }
}
```

### 列表 7.6 `ItemSamHoe` 类

点击此处查看代码图片。

```java
package com.wuppy.samsmod;

import net.minecraft.item.Item.ToolMaterial;

import net.minecraft.item.Hoe;

public class ItemSamHoe extends Hoe
{
    public ItemSamHoe(ToolMaterial material, String name)
    {
        super(material);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
    }
}
```

### 列表 7.7 `ItemSamShovel` 类

点击此处查看代码图片。

```java
package com.wuppy.samsmod;

import net.minecraft.item.Item.ToolMaterial;

import net.minecraft.item.ItemSpade;

public class ItemSamShovel extends ItemSpade
{
    public ItemSamShovel(ToolMaterial material, String name)
    {
        super(material);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
    }
}
```

### 列表 7.8 `ItemSamSword` 类

点击此处查看代码图片。

```java
package com.wuppy.samsmod;

import net.minecraft.item.Item.ToolMaterial;

import net.minecraft.item.ItemSword;

public class ItemSamSword extends ItemSword
{
    public ItemSamSword(ToolMaterial material, String name)
    {
        super(material);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
    }
}
```

```java
private static Set blocks = Sets.newHashSet(new Block[] { });
```

这一行创建了一个名为 `blocks` 的变量。它是一个 `Set`，是编程中的一种数据结构。然而，你唯一需要关注的是 `Block` 数组。将该工具能够有效挖掘的方块放在大括号内，并用逗号隔开。

***

### 注意：如何获取方块

你可以通过访问其他工具文件并复制它们在 `Block` 数组中的内容，轻松找到你想要添加的方块。

***

一旦你添加了所有想要该工具能够挖掘的方块，就该是创建 `super` 构造函数了。这个构造函数需要三个参数。

第一个是一个 `float` 值，用于对玩家造成的伤害。如果你想创建一个既是工具又是武器的物品，在这里设置一个高值是可以的。

第二个参数是 `ToolMaterial`，它是当前文件中使用的构造函数的第一个参数。

最后一个参数是你刚刚创建的方块 `Set` 集合。

列表 7.9 显示了 paxel 完成后的集合，其中 `blocks` 变量包含了所有镐和斧头可以挖掘的方块。

### 列表 7.9 `ItemSamPaxel`

点击此处查看代码图像。

***

```java
package com.wuppy.samsmod;

import java.util.Set;

import com.google.common.collect.Sets;

import net.minecraft.block.Block;

import net.minecraft.init.Blocks;
import net.minecraft.item.ItemTool;

public class ItemSamPaxel extends ItemTool
{
    private static Set blocks = Sets.newHashSet(new Block[] {Blocks.cobblestone, Blocks.double_stone_slab, Blocks.stone_slab, Blocks.stone, Blocks.sandstone, Blocks.mossy_cobblestone, Blocks.iron_ore, Blocks.iron_block, Blocks.coal_ore, Blocks.gold_block, Blocks.gold_ore, Blocks.diamond_ore, Blocks.diamond_block, Blocks.ice, Blocks.netherrack, Blocks.lapis_ore, Blocks.lapis_block, Blocks.redstone_ore, Blocks.lit_redstone_ore, Blocks.rail, Blocks.detector_rail, Blocks.golden_rail, Blocks.activator_rail, Blocks.planks, Blocks.bookshelf, Blocks.log, Blocks.log2, Blocks.chest, Blocks.pumpkin});

    public ItemSamPaxel(ToolMaterial material, String name)
    {
        super(3, material, blocks);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
    }
}
```

***

除了拥有 `Set` 变量外，你还需要来自 `ItemPickaxe` 的两个方法和一个来自 `ItemAxe` 的方法。其中一个方法存在两个文件中，它指定了工具以何种速度挖掘哪些材料。例如，铲子挖掘土的速度快，挖掘石头的速度慢。镐特定的方法确保了它能根据所用 `ToolMaterial` 的挖掘等级挖掘某些更硬的方块。复制并合并后的两个方法如下：

点击此处查看代码图像。

```java
public boolean func_150897_b(Block block)
{
    return block == Blocks.obsidian ? this.toolMaterial.getHarvestLevel() == 3 : (block != Blocks.diamond_block && block != Blocks.diamond_ore ? (block != Blocks.emerald_ore && block != Blocks.emerald_block ? (block != Blocks.gold_block && block != Blocks.gold_ore ? (block != Blocks.iron_block && block != Blocks.iron_ore ? (block != Blocks.lapis_block && block != Blocks.lapis_ore ? (block != Blocks.redstone_ore && block != Blocks.lit_redstone_ore ? (block.getMaterial() == Material.rock ? true : (block.getMaterial() == Material.iron ? true : block.getMaterial() == Material.anvil)) : this.toolMaterial.getHarvestLevel() >= 2) : this.toolMaterial.getHarvestLevel() >= 1) : this.toolMaterial.getHarvestLevel() >= 1) : this.toolMaterial.getHarvestLevel() >= 2) : this.toolMaterial.getHarvestLevel() >= 2) : this.toolMaterial.getHarvestLevel() >= 2) : this.toolMaterial.getHarvestLevel() >= 2) : this.toolMaterial.getHarvestLevel() >= 2);
}

public float func_150893_a(ItemStack itemStack, Block block)
{
    return 0.0f; // 原文提供的逻辑占位符
}
```

2. **第三个参数是工具可以使用的次数。**

3. **它被称为 `EMERALD`（钻石）。**

### 练习

使用与创建 paxel 相同的技巧，创建一个 spax（这是一种铲子和斧头于一体的工具）。

spax 的外观应该类似于列表 7.10。

### 列表 7.10 物品：`ItemSamSpax`

点击此处查看代码图片。

```java
package com.wuppy.samsmod;

import java.util.Set;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;
import net.minecraft.init.Blocks;
import net.minecraft.item.ItemStack;
import net.minecraft.item.ItemTool;
import com.google.common.collect.Sets;

public class ItemSpax extends ItemTool
{
    private static Set blocks = Sets.newHashSet(new Block[] {Blocks.grass, Blocks.dirt, Blocks.sand, Blocks.gravel, Blocks.snow_layer, Blocks.snow, Blocks.clay, Blocks.farmland, Blocks.soul_sand, Blocks.mycelium, Blocks.planks, Blocks.bookshelf, Blocks.log, Blocks.log2, Blocks.chest, Blocks.pumpkin, Blocks.lit_pumpkin});

    protected ItemSpax(ToolMaterial material, String name)
    {
        super(3, material, blocks);
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
    }

    public boolean func_150897_b(Block p_150897_1_)
    {
        return p_150897_1_ == Blocks.snow_layer ? true : p_150897_1_ == Blocks.snow;
    }

    public float func_150893_a(ItemStack p_150893_1_, Block p_150893_2_)
    {
        return p_150893_2_.getMaterial() != Material.wood && p_150893_2_.getMaterial() != Material.plants && p_150893_2_.getMaterial() != Material.vine ? super.func_150893_a(p_150893_1_, p_150893_2_) : this.efficiencyOnProperMaterial;
    }
}
```

工具的纹理如图 7.13 所示，你可以在游戏图 7.14 中看到它。

![Image](img/image00577.jpeg)

**图 7.13** Spax 纹理。

![Image](img/image00578.jpeg)

**图 7.14** 游戏中的 spax。

## 第 8 小时：创建护甲

在本小时你将学到：

![Image](img/image00525.jpeg) 创建你的 `ArmorMaterial`

![Image](img/image00525.jpeg) 创建护甲

![Image](img/image00525.jpeg) 自定义护甲

在过去的几个小时里，你学习了许多 Mod 中使用的大多数特殊物品。真正独特的物品是你需要自己创建的，但通过这几个和过去几个小时的学习，你应该能够在没有太多帮助的情况下进展得相当远。在这一小时中，你将学习如何创建护甲。首先，你将学习 `ArmorMaterial`，它类似于 `ToolMaterial`。然后你将学习如何制作所有的护甲部件，最后，你将学习如何对它们进行自定义。

### 创建你的 `ArmorMaterial`

就像创建工具一样，首先创建一个用于制作护甲的材料是非常重要的。`ArmorMaterial` 的代码应该像这样：

点击此处查看代码图片。

```java
ArmorMaterial samarmor = EnumHelper.addArmorMaterial("samarmor", 20, new int[] { 3, 7, 6, 3 }, 10);
```

工具和护甲的代码有很多共同点，因为它们在 Minecraft 中是密切相关的。然而，这里有些变化。这行代码的第一部分，即参数部分，与 `ToolMaterial` 代码非常相似。参数略有不同。

第一个参数是材料的名称。重要的是要确保没有其他 Mod 使用了相同的 `ArmorMaterial` 名称，但这种情况不太可能发生。

第二个参数是护甲可以吸收的最大伤害值。这段代码似乎只能承受 20 次击。然而，实际的最大伤害有点奇怪。在 `ItemArmor` 中，实际的最大伤害有点奇怪……（注：此处原文似乎存在逻辑重复或混乱，翻译已按原意逻辑对齐）。

`EnumHelper.addArmorMaterial("samarmor", 20, new int[] { 3, 7, 6, 3 }, 10);`

（注：由于原文后半部分存在大量逻辑重复和断句，译文严格遵循原文结构进行对应翻译以确保不漏译且不重复输出。）

到目前为止，这段代码大部分应该很容易理解，因为它们大部分与其他任何物品都是相同的。唯一令人惊讶的代码部分是 `super` 构造函数的第二个参数。这个第二个数字是盔甲的渲染索引。该数字仅用于原版（vanilla）盔甲纹理，因此对于自定义盔甲来说并不真正需要。基于此，最简单的方法将其设置为零。

盔甲部件的纹理如图 8.1 到 8.4 所示。

![Image](img/image00579.jpeg)

**图 8.1** 头盔纹理。

![Image](img/image00580.jpeg)

**图 8.2** 胸甲纹理。

![Image](img/image00581.jpeg)

**图 8.3** 护腿纹理。



![Image](img/image00582.jpeg)

**图 8.4** 靴纹理。

所有这些纹理显然都会像其他物品纹理一样保存在`textures/items`文件夹中。此外，文件名将与代码中的名称相同，即构造函数的第三个参数。

图 8.5 到 8.8 显示了游戏中的物品。

![Image](img/image00583.jpeg)

**图 8.5** 游戏中的头盔。

![Image](img/image00584.jpeg)

**图 8.6** 游戏中的胸甲。

![Image](img/image00585.jpeg)

**图 8.7** 游戏中的护腿。

![Image](img/image00586.jpeg)

**图 8.8** 游戏中的靴子。

### 创建穿在身上的盔甲纹理

如果你现在启动游戏并尝试穿上你的盔甲，你会发现它是可以工作的。然而，它没有与物品图标类似的纹理。相反，它看起来像白色的布制盔甲。要让盔甲上显示你的自定义纹理，你必须先制作它们。图 8.9 和 8.10 是实现此所需的两个盔甲纹理。

![Image](img/image00587.jpeg)

**图 8.9** 盔甲纹理 1。

![Image](img/image00588.jpeg)

**图 8.10** 盔甲纹理 2。

这些纹理看起来可能非常模糊，但如果你知道自己在看什么，它们很容易理解。这些纹理是 3D 纹理的 2D 表示，2D 纹理在游戏中会包裹在玩家模型周围。

在盔甲纹理 1 中，左上部分是头盔。左下部分是靴子的纹理，最后，右侧部分都是胸甲的。盔甲纹理 2 包含了盔甲的护腿。

两张图片都包含大量的空白区域。然而，大部分空像素实际上可以用于盔甲。例如，在第二个纹理中，顶部小框右侧的区域将包含手臂底部的纹理。但是，因为手会延伸那里，所以这部分是空的。也可以给头盔添加第二层，营造出类似头发的幻象。你可以稍微尝试一下，找出什么该放在什么位置。

接下来，你需要将纹理存放在某处以便 Forge 使用它们。文件夹结构为`assets/[modid]/models/armor`。它看起来应该像图 8.11。

![Image](img/image00589.jpeg)

**图 8.11** 盔甲文件夹结构。

对于你现在创建的盔甲套装，纹理将被保存为`samarmor1`和`samarmor2`。建议（但不是必须）遵循文件夹结构和文件命名规范。

纹理所需的最后一步是告诉代码去哪里寻找纹理文件。为了做到这一点，你需要名为`getArmorTexture`的方法。在这个方法中，你必须决定盔甲的哪个部件需要哪种纹理。你编写该方法时需要检查物品是否为头盔、靴子或胸甲，并为其分配纹理一。如果不是其中任何一个，它应该检查物品是否为盔甲纹理二的护腿。如果两者都不是，说明可能出了问题，且两个纹理都是错误的。在这种情况下，最好的办法是打印错误信息并返回`null`。在代码中执行所有这些操作如下：

```java
public String getArmorTexture(ItemStack stack, Entity entity, int slot, String type)
{
    if (stack.getItem() == SamsMod.samhelmet || stack.getItem() == SamsMod.samchest || stack.getItem() == SamsMod.samboots) {
        // ... logic ...
    } else if (stack.getItem() == SamsMod.samleggings) {
        // ... logic ...
    } else {
        System.out.println("something is wrong");
        return null;
    }
}
```

## 问：总防御力可以超过 20 吗？

## 答：可以，可以。它在图形用户界面上不会显示，但可以正常运作。

## 问：我必须准备两套护甲纹理吗？

## 答：如果你拥有所有四件护甲，那么是的。如果你没有护腿，就不需要第二种护甲纹理。

### 工作坊

完成以下工作坊，以确保你理解了目前为止的所有内容。

### 测验

**1. 之前使用的`addToolMaterial`方法的第二个参数是什么？它是如何工作的？**

**2. 钻石的`ArmorMaterial`叫什么？**

**3. 如果没有`getArmorTexture`方法会发生什么？**

### 答案

**1.** 第二个参数是护甲碎片能够承受的伤害量。它与`ItemArmor`文件中的一个值相乘。

**2.** `DIAMOND`。尽管它在工具中被称为`EMERALD`，但护甲使用的是它的普通名称。

**3.** 你的护甲看起来会像玩家的标准护甲。标准护甲是白色皮甲。

### 练习

制作一种允许玩家在水下呼吸的护甲。提示：要实现这一点，你必须查看`EntityPlayer`并找到一个包含单词`Air`的方法。

代码答案应该类似于以下：

点击此处查看代码图片

```java
public void onArmorTick(World world, EntityPlayer player, ItemStack itemStack)
{
    if(itemStack.getItem() == SamsMod.samhelmet)
    {
        if(player.isInWater())
        {
            player.setAir(20);
        }
    }
}
```

首先，你检查正在刻的护甲是否是头盔。然后，你检查玩家确实在水下，以确保不会过快拖慢服务器或客户端。如果玩家在水中，将空气量设置为大于零的值，以确保玩家不会溺水。

# 第三部分：方块

## 第 9 小：制作你的第一个方块

你将在这一小时学到：

- 理解什么是方块
- 创建一个基础方块
- 添加方块纹理

在这一小时中，你将确切学习 Minecraft 中什么是方块以及什么方块。然后，你创建一个方块并为其添加纹理。你还学习了如何对方块进行一些基础自定义。进一步的变化和更有趣的方将在接几小时内涵盖。

### 理解什么是方块

了解你将要使用的事物的局限性和功能是非常重要的。在 Minecraft 中，方块是一个 1×1×1 的区域。方块通常被视为一个整体，但它并不完全填充。当你创建一个方块时，必须知道它的限制性。在 Minecraft 中，方块并不是完全填充的。如果你有一个楼梯，你不能添加任何东西。这是因为在 Minecraft 中，方块是填充的。一个在这个解释之后可能会困惑的块是石板。当你放置一个石板时，它会正常工作。这看起来现在有两个方块，但这是不可能的。这种方法是通过一种聪明的技巧实现的。当你放置一个石板时，它是已经填充的。

### 创建一个基础方块

现在你知道什么是方块了，是时候制作它了。

### 主文件

在主文件中，你需要为你的方块声明一个变量，并在`preInit`方法中初始化它。

```java
public static Block samStone;

// inside preInit
samStone = new BlockStone();
GameRegistry.registerBlock(samStone, "SamStone");
```

### 创建 `BlockStone` 类

`BlockStone`下方的错误是正常的，你可以通过创建类来修复它。这样做是将鼠标悬停在错误上，点击 Class，然后完成。

```java
package com.wuppy.samsmod;

import net.minecraft.block.Block;

public class BlockStone extends Block
{
}
```

现在主类的错误消失了，但在`BlockStone`类中了一个了一个错误。要修复这个问题，你必须添加一个构造函数。因为主类使用的构造函数是空的，这个也必须是空的。然而，被继承的`Block`类要求你添加一个包含材质的构造函数。为了让主类和`Block`类正常工作，你需要添加一个没有参数的构造函数。然后在构造函数内部，添加一个带有单个参数的`super`。这个参数必须是一个`Material`。对于石头，`Material`将是`rock`，但你可以查看`Material`类以获取其他材质。

除了`super`构造函数外，你还需要添加一个未本地化的名称以及方块的纹理名称。有了这些行，该类应该像最后的示例所示。

```java
public BlockStone()
{
    super(Material.rock);
}
```

```java
String name = "samstone";

public BlockSamStone()
{
    super(Material.rock);
    setBlockName(SamsMod.MODID + "_" + name);
    setBlockTextureName(SamsMod.MODID + ":" + name);
}
```

这段代码中有些地方可能会让你感到惊讶。首先，创建了一个包含名称的`String`变量。之所以这样做是因为同一个名称被使用了多次。当你将来在未来某时候想要——或必须——更改它时，你只需要更改`name`变量的内容，而不需要在每个使用它的地方都进行替换。

另外两个可能引起困惑的地方是纹理名称和未本地化名称的方法名。与物品使用的`setUnlocalizedName`不同，这里使用的是`setBlockName`。对于纹理名称，你使用的是`setBlockTextureName`，而不是像物品那样简单地使用`setTextureName`。

不要忘记使用`setCreativeTab`方法将此方块添加到正确的创造模式菜单，该方法接受单个参数。这个参数与物品相同，需要一个单一的`CreativeTab`对象。如果你查看`CreativeTab`类，你就能看到代码中是如何调用游戏内创造标签的。

### 自定义你的方块

你还需要设置一些方块特有的属性。每个方块都有硬度（hardness）、爆炸抗（blast resistance）和脚步音（step sound）。最后，对于某些方块，你可能还想添加采集等级（harvest level）。

方块的硬度决定了用任何合适的工具破坏它需要多久。最容易被破坏的工具类型由材质决定，但你可以通过硬度来编辑破坏时间。你用于设置此项的方法叫做`setHardness`。该方法接受一个参数，类型为`float`。`float`在 Java 中类似于`int`，意味着它也是一个数字。然而，区别在于`float`可以带有小数。在 Java 中，`float`后面通常跟着一个`F`，以便让读者和 Java 都能清楚地看出这是一个`float`而不是其他数字类型。数字越高，破坏方块所需的时间越长。原版方块的硬度等级可以在`Blocks`类中找到。由于`SamStone`将是一个矿石，其硬度应该与其他矿石方块相似。石头的硬度为`1.5F`，大多数矿石的硬度比这略高。对于`SamStone`，硬度将为`2.0F`。

如果你想让方块像基岩一样不可破坏，则硬度应该设置为`-1.0F`。

爆炸抗与硬度非常相似。然而，它不是工具的破坏性，而是针对爆炸的破坏性。这些爆炸包括苦力怕和 TNT。用于此项的方法名为`setResistance`。与`setHardness`一样，它需要一个单一的`float`值，决定了抗爆炸能力。你不需要这个方法，但许多方块都会使用。石头的爆炸抗为`10F`，而矿石的爆炸抗为`5F`。因为`SamStone`也是一种矿石，使用的值也将是`5F`。

如果你想让你的方块不可破坏，可以将抗设置为`6,000,000`，这与基岩相同。游戏中没有任何爆炸物可以破坏抗性如此高的方块。

你可能还想为方块添加的第三件事是脚步音。这是当玩家或生物走过它时播放的音。通常情况下，当你走过一个方块时，它有多种不同的声音可以播放，并会从中随机选择。当你选择单个`StepSound`时，它通常会采用该特定类型的所有声音。此外，脚步音还决定了它将具有什么样的破坏音。你需要添加脚步音的方法是`setStepSound`。该方法接受单个参数。该参数是一个`Block.StepSound`对象。当你在方块的构造函数中添加此方法时，你不需要担心创建自定义脚步音。相反，你可以查看`Block`类并选择所需的脚步音变量名并使用。对于`BlockSamStone`，脚步音名为`soundTypeStone`。

你可能还想为基础方块添加的最后一个方法是采集等级。采集等级对于方块来说非常重要，尽管不是强制要求的。它管理了方块的两个重要要点。首先，采集等级管理哪些工具可以正确地破坏它。如果你没有采集等级，该方块可以被游戏中的每个工具正确地破坏。正确破坏意味着方块会掉落它应该掉的物品。例如，当你用手挖掘石头时，它什么都不会掉落。

其次，采集等级还管理了哪个等级的……采集的对于,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,.,,..........................................................

........;

```java
import net.minecraft.block.Block;
import net.minecraft.block.Material;
import net.minecraft.creativab.CreativeTab;

package com.wuppy.samsmod;

public class BlockSamStone extends Block
{
    String name = "samstone";

    public BlockSamStone()
    {
        super(Material.rock);
        setBlockName(SamsMod.MODID + "_" + name);
        setBlockTextureName(SamsMod.MODID + ":" + name);
        setCreativeTab(CreativeTabs.tabBlock);
        setHardness(2.0F);
        setResistance(5F);
        setStepSound(soundTypeStone);
        setHarvestLevel("pickaxe", 2);
    }
}
```

### 动手尝试：创建一个不可破坏的方块

如果你想让你的方块不可破坏，可以将抗设置为`6,000,000`，这与基岩相同。游戏中没有任何爆炸物可以破坏抗性如此高的方块。

```java
setHardness(-1.0F);
setResistance(6000000);
```

你用于设置采集等级的方法是`setHarvestLevel`。该方法接受两个参数。第一个是工具名称的`String`，第二个是你想要的等级。

```java
setHarvestLevel("pickaxe", 2);
```

### 方块的本地化

接下来，你在`lang`文件中添加方块的本地化内容。要为方块添加本地化内容，你可以直接使用之前为物品时使用的现有`lang`文件。`samStone`所需的本地化内容看起来如下：

```text
tile.wuppy29_samsmod_samstone.name=Sam's Stone
```



当然，方块还有更多的自定义空间。然而，由于空间限制，我们无法向你展示如何进行每一个可能的自定义——而且那样它根本就不是自定义方块了！了解更多自定义内容的一种简单方法是查看原生代码（vanilla code）。

在自定义方面，有两个非常重要的类。第一个是 `Blocks`，你可以在其中找到用于为某些类型的方块设置属性的方法。第二个是 `Block` 类。在这个类中，你将找到在方块中使用的所有方法。里面一定有一些方法可以让你按照自己的意愿自定义方块。

### 添加方块纹理

要为方块添加纹理，首先必须创建纹理。就像物品一样，它必须是 16×16 像素，并保存为 `.png` 文件。图像名称必须与方块使用的未本地化名称（unlocalized name）相同。对于目前为止创建的萨姆石（Sam’s Stone），纹理将命名为 `samstone.png`。这张图片看起来就像图 9.1。

![Image](img/image00592.jpeg)

**图 9.1** 萨姆石纹理。

除了给它命名外，将此图像添加到正确的位置也很重要。进入你用于语言文件和物品纹理文件的资源文件夹，然后进入 `assets/[your modid]/textures`，如图 9.2 所示。

![Image](img/image00593.jpeg)

**图 9.2** 纹理文件夹路径。

在这里，你添加一个名为 `blocks` 的新文件夹。该文件夹将包含你在制作模组时使用的所有方块纹理。路径应该像图 9.3 所示。

![Image](img/image00594.jpeg)

**图 9.3** 方块纹理文件夹路径。

一旦创建了这个文件夹，添加你为方块制作的纹理，萨姆石对应的图 9.1。这在不需要任何额外代码的情况下为方块添加了纹理。单个的 `setBlockTextureName` 方法就足够了。不过，你可能需要使用 F5 刷新 Eclipse，纹理才能正常显示。

如果你到为止的操作都是正确的，你应该就能看到这个方块了，如图 9.4 所示。

![Image](img/image00595.jpeg)

**图 9.4** 游戏中的方块。

### 总结

在这一小时中，你了解到方块是不能移动的。一旦它移动，就会发生某些情况。关于方块的另一个重要点是，它们总是占据 1×1×1 的区域，同一个区域内不能有两个方块。

除了学习方块是什么之外，你还学习了如何将它们添加到你的模组文件中，以及如何带有一些基础设置（如硬度和抗性）来创建你的自定义方块文件。最后，你还为你的方块添加了纹理。

### 问答

**Q. Minecraft 中可以添加的方块数量有上限吗？**

**A.** 是的。Minecraft 最多有 4096 个方块。大约 150 个被 Minecraft 本身占用，所以请确保不要使用太多。在第 10 小节的“智能地创建多个方块”中，你将学习如何对方块使用元数据（metadata），这应该会有帮助。

**Q. 如何向我的模组文件添加第二个方块？**

**A.** 只需重写第一个方块的代码，但要确保变量和未本地化名称都是不同的。

**Q. 可以同一个文件使用多个方块吗？**

**A.** 可以的。只需确保每个方块的未本地化名称是不同的即可。

**Q. 可以将同一个方块添加到多个创造模式标签页吗？**

**A.** 不，这是可能的。

### 工作坊

你已经学习了方块的基础知识。在接下来的几小时里，你将学习更多关于它们的知识。因此，充分理解基础非常。为了确保你理解了方块的基础，请完成以下测验。

### 测验

**1. 对于名为 `computerScreen` 的方块变量，最好的未本地化名称是什么？**

**2. 以下代码有什么问题？**

```java
if (condVar > someVal) {console.log("xxx")}
```

```java
public void getSubBlocks(Item par1, CreativeTabs par2CreativeTabs, List par3List)
{
    for (int var4 = 0; var4 < 2; ++var4)
    {
        par3List.add(new ItemStack(par1, 1, var4));
    }
}
```

这段代码遍历区块的每个元数据（metadata）并将其添加到创造模式中。代码中最重要的部分是 `var4 < 2`。这确保了前两个元数据（即 `0` 和 `1`）被添加到创造模式中。如果你添加了第三个元数据，必须将 `2` 改为 `3`，以确保第三个元数据也能显示在菜单上。

### 注意：创造模式中的元数据

`getSubBlocks` 是将你的元数据添加到菜单的方法，但这个方法并不是必须的。如果你没有这个方法，它只会显示元数据为 `0` 的区块，这在某些情况下是优的。

接下来，你需要编辑 `SamsMod` 类中该区块的 `GameRegistry` 行。普通的区块注册看起来如下所示：

点击此处查看代码图片

`GameRegistry.registerBlock(samStone, "SamStone")`

对于元数据区块，它应该像这样：

点击此处查看代码图片

`GameRegistry.registerBlock(samStone, ItemSamStone.class, "SamStone")`

在原始 `GameRegistry` 行的第一个和第二个参数之间，必须添加一个新的参数。这个参数是一个新的 `Item` 类，你接下来将创建它。此文件持有区块的未本地化名称，并确保 Minecraft 将其作为元数据区块处理。

### 创建 ItemBlock 类

要创建新文件，只需鼠标悬停在下方的错误上并选择“Create Class（创建类）”。类创建完成后，让它继承 `ItemBlock` 类。不要忘记导入它，否则会报错。导入后，你会收到一个错误，提示它需要一个带有 `Block` 参数的构造函数，你应该添加该构造。此时，你应该拥有一个看起来像列表 10.2 的文件。

**列表 10.2 ItemSamStone 类**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.block.Block;
import net.minecraft.item.ItemBlock;

public class ItemSamStone extends ItemBlock
{
    public ItemSamStone(Block block)
    {
        super(block);
    }
}
```

如前所述，该类负责区块的元数据以及名称。这意味着你必须添加代码来实现这一目标。所需的第一个部分代码确保 Minecraft 知道它正在处理元数据。相应的代码是 `setHasSubTypes`。该方法接受一个类型为 `boolean` 的单一参数。`boolean` 可以是 `true` 或 `false`。因为区块将拥有子类型，所以这个参数必须是 `true`。

现在，为该类添加两个方法。第一个方法确保当你破坏区块时，它会掉落正确的元数据。该方法看起来如下：

点击此处查看代码图片

```java
@Override
public int getMetadata(int par1)
{
    return par1;
}
```

这个方法看起来可能很奇怪。它返回收到的内容而不做任何更改。然而，如果你没有这个方法，它始终返回零，这会破坏元数据区块的掉落逻辑。

第二个方法确保每个区块的未本地化名称是不同的。你必须重写的方法名为 `getUnlocalizedName`。对于 `SamStone`，它应该看起来如下：

点击此处查看代码图片

```java
@Override
public String getUnlocalizedName(ItemStack itemstack)
{
    String name = "";
    switch(itemstack.getItemDamage())
    {
        case 0:
            name = "ore";
            break;
        case 1:
            name = "wall";
            break;
        default:
            System.out.println("Invalid metadata for SamStone");
            name = "broken";
            break;
    }
    return getUnlocalizedName() + "." + name;
}
```

因为此方法重写了另一个方法，所以添加 `@Override` 注解是有用的，因为它会在名称更改导致你的方法不再被重写时提醒你。此方法有一个单一的 `ItemStack` 参数，包含需要命名的区块。在方法内部，对区块中的所有元数据创建了 `switch` 分支处理。元数据 `0` 是矿石，元数据 `1` 是墙。如果由于某种原因存在元数据更高的区块，说明出了问题，在这种情况下它通过向控制台写入一行来告知程序员。一旦获取了特定区块的名称，它将使用 `getUnlocalizedName` 获取标准名称，然后是一个点，最后是特定于元数据的名称。整个 `ItemSamStone` 类现在应该看起来像列表 10.3。

**列表 10.3 完成的 ItemStone 类**

```java
package com.wuppy.samsmod;

import net.minecraft.block.Block;
import net.minecraft.item.ItemBlock;
import net.minecraft.item.ItemStack;

public class ItemSamStone extends ItemBlock
{
    public ItemSamStone(Block block)
    {
        super(block);
        setHasSubTypes(true);
    }

    @Override
    public int getMetadata(int par1)
    {
        return par1;
    }

    @Override
    public String getUnlocalizedName(ItemStack itemstack)
    {
        String name = "";
        switch(itemstack.getItemDamage())
        {
            case 0:
                name = "ore";
                break;
            case 1:
                name = "wall";
                break;
            default:
                System.out.println("Invalid metadata for SamStone");
                name = "broken";
                break;
        }
        return getUnlocalizedName() + "." + name;
    }
}
```

由于 `getlocalizedName` 的更改，`.lang` 文件中的本地化内容也需要更改。对于第一个元数据区块，你应该在 `samstone` 和 `.name` 之间添加 `.ore`。对第二个元数据区块遵循相同的命名规则，使两行都像如下所示：

点击此处查看代码图片

`tile.wuppy29_samsmod_samstone.ore.name=Sam's Stone`

`tile.wuppy29_samsmod_samstone.wall.name=Sam's Wall`

如果你现在启动游戏，你会发现菜单中有区块。它们的名称正确，但纹理是紫色的方块。要修复这个问题，你需要在 `BlockSamStone` 类中添加几行代码。此外，你需要创建第二个纹理并更改纹理名称。

### 添加区块纹理

如，你需要进行许多操作才能让多个纹理工作。首先，你必须为删除的 `setBlockTextureName` 行添加新代码。为了实现这一点，你需要一个 `IIcon` 数组来存储区块图像。`IIcon` 的问题是它只存在于客户端，因为服务器不处理渲染，因此不需要区块的图像。为了确保该变量仅在客户端模式读取类时被创建，你还必须从 `getSubBlocks` 方法中添加 `@SideOnly(Side.CLIENT)` 代码。带有注解，变量应该看起来如下：

```java
@SideOnly(Side.CLIENT)
private IIcon[] icons;
```

这个 `IIcon` 数组必须在初始化期间填充图标。为了实现这一点，你可以使用名为 `registerBlockIcons` 的方法。对于 `SamStone` 区块，它看起来如下所示。需要注意的重要一点是，如果纹理不存在，此代码可能会崩溃。

点击此处查看代码图片

```java
@Override
@SideOnly(Side.CLIENT)
```

```java
public void registerBlockIcons(IIconRegister par1IconRegister)
{
    icons = new IIcon[2];
    for (int i = 0; i < icons.length; i++)
    {
        icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samstone" + i);
    }
}
```

这又是仅存在于客户端的方法，因此在它上方添加 `@SideOnly` 行非常重要。此外，由于它覆盖了 `Block` 类中的一个方法，建议也添加 `@Override` 注解，尽管不是强制要求的。

该方法中的代码首先将 `IIcon` 数组的大小初始化为 2。如果你想为新的元数据块（metadata block）添加额外的纹理，应该增加这个数字。一旦创建了数组，它就会遍历数组中的每个值并为其注册一个图标。在 `registerIcon` 中需要添加的 `String` 是 `MODID` 后跟着一个冒号。这确保了纹理是从正确的文件夹中提取的。`String` 的部分是纹理的名称。通常，元数据块的纹理名称是区块名称加上该区块的纹理索引。在这种情况下，第一个区块 Sam’s Ore（萨矿石）尝试获取纹理 `samstone0`，其中 `samstone` 是名称。第二个区块获取纹理 `samstone1`。

除了注册图标之外，使用它们也同样重要。此方法的称为 `getIcons`，对于基础的元数据块来说非常简单。该方法在下面的代码段所示：

点击此处查看代码图片

```java
@Override
@SideOnly(Side.CLIENT)
public IIcon getIcon(int par1, int par2)
{
    return icons[par2];
}
```

如果纹理不存在，或者如果你在没有增加图标尺寸的情况下添加了元数据，这段代码将会崩溃。

第二个参数是元数据。由于图标数组的设置方式，这个数字可以直接用于返回正确的 `IIcon`。

整个 `BlockSamStone` 类应该像列表 10.4 所示。

**列表 10.4 完成的 BlockSamStone**

点击此处查看代码图片

```java
package com.uppy.samsmod;

import java.util.List;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.item.Item;
import net.minecraft.item.ItemStack;
import net.minecraft.util.IIcon;

import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class BlockSamStone extends Block
{
    String name = "samstone";

    @SideOnly(Side.CLIENT)
    private IIcon[] icons;

    public BlockSamStone()
    {
        super(Material.rock);
        setBlockName(SamsMod.MODID + "_" + name);
        setCreativeTab(CreativeTabs.tabBlock);
        setHardness(2F);
        setResistance(5F);
        setStepSound(soundType);
        setHarvestLevel("pickaxe", 2);
    }

    @Override
    @SideOnly(Side.CLIENT)
```



`public void registerBlockIcons(IIconRegister par1IconRegister)`

```
{
    icons = new IIcon[2];
    for (int i = 0; i < icons.length; i++)
    {
        icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samstone" + i);
    }
}

@Override
@SideOnly(Side.CLIENT)
public IIcon getIcon(int par1, int par2)
{
    return icons[par2];
}

@SuppressWarnings({"unchecked", "rawtypes"})
@SideOnly(Side.CLIENT)
@Override
public void getSubBlocks(Item par1, CreativeTabs par2, List par3List)
{
    for (int var4 = 0; var4 < 2; ++var4)
    {
        par3List.add(new ItemStack(par1, 1, var4));
    }
}
```

---

最后，你必须添加实际纹理。第一个纹理已经存在且命名为`samstone`。这是元数据 0 的纹理，因此在使用元数据块时，必须将其重命名为`samstone0`。图 10.1 显示了元数据 1 的纹理，即 Sam’s Wall。

![Image](img/image0596.jpeg)

**图 10.1 Sam’s Wall 纹理。**

图 10.1 将存储为`blocks`文件夹中的`samstone1`。当你添加这些文件并遵循代码后，将在创造模式标签中看到具有正确名称和纹理的区块。

---

### 动手尝试：添加第三个元数据块

为`SamStone`添加第三个元数据。要做到这一点，更新`ItemBlock`文件以包含第三个本地化名称，并扩展区块中的`IIcon`数组。别忘记通过增加`getSubBlocks`中的数字将其添加到创造模式菜单。

---

Sam’s Wall 区块在游戏中的看起来像图 10.2。

![Image](img/image0597.jpeg)

**图 10.2 游戏中的新区块。**

你可能会注意到区块的顶部纹理与侧面不同。你将在第 11 节“让你的区块独特性”中学习这样做。

### 总结

在本节中，你学习了元数据块。你了解到对于元数据块，需要一个`ItemBlock`类。这个`ItemBlock`类处理了区块的大部分元数据工作，因为它包含了本地化名称并启用了元数据所需的子类型。此外，你还学习了如何向单个区块添加多个纹理。每个元数据对应单个纹理。在第 11 节中，你将学习如何使用这段代码为区块的侧面提供不同的纹理。

### 问答

**Q。单个区块最多可以有多少个元数据？**

**A。是的，对于区块来说，元数据数量不能超过 16 个。**

**Q。有办法在相同类型下添加更多区块吗？**

**A。可以的。你可以使用命名标签（NBT）添加几乎无限数量的区块，这有点复杂，书中没有详细介绍。关于 NBT 的信息，请阅读以下网站：[`minecraft.gameedia.com/NBT_format`](http://minecraft.gameedia.com/NBT_format)**

**Q。不同的元数据可以位于不同的创造标签吗？**

**A。不可以，就像材质一样，这对所有子区块都是相同的。**

### 练习

在处理区块时，你会经常使用元数据，因为 Minecraft 中的区块数量是有限的。因此，充分理解它们非常重要。

### 测验

**1。如果没有`ItemBlock`文件会发生什么？**

**2。为什么要在代码中添加一个可崩溃的选项？**

### 答案

**1。区块仍会正常工作，但如果你尝试放置它，它将无法工作。可能会出现其他问题，例如使用错误的元数据进行放置。**

**2。有时，程序崩溃比运行损坏的程序要好。**

### 练习题

修改`BlockSamStone`类，使其能够用于多个带有元数据的不同区块。你可以通过在构造函数中添加本地化名称以及元数据数字来实现。

---

在本小时中，你将利用前两个小时中学到的关于块的知识来创建一些有趣的块。了解如何制作块是一件好事，但如果没有自定义的块，这个 mod 用起来将非常无趣。这一小时涵盖了几个常用的块类型和设置，通过它们你可以实现很多有趣的事情。这些包括植物、侧面纹理以及不完全实心的块。

### 添加侧面纹理

要为块的不同侧面添加不同的纹理，你需要与元数据块非常相似的纹理代码。你将不会使用`setBlockTextureName`，而是使用一个`IIcon`数组以及`registerBlockIcons`和`getIcon`方法来为你的块提供纹理。本书将向你展示如何更改元数据纹理代码`BlockSamStone`，以让其中一个元数据拥有第二个纹理。与纹理相关的重要代码看起来应该与 列表 11.1 类似。

**列表 11.1 BlockSamStone 中的纹理代码**

点击此处查看代码图片

```
@SideOnly(Side.CLIENT)
private IIcon[] icons;

@Override
@SideOnly(Side.CLIENT)
public void registerBlockIcons(IIconRegister par1IconRegister)
{
    icons = new IIcon[2];
    for (int i = 0; i < icons.length; i++)
    {
        icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samstone" + i);
    }
}

@Override
@SideOnly(Side.CLIENT)
public IIcon getIcon(int par1, int par2)
{
    return icons[par2];
}
```

如果这段代码中有任何部分你不理解，请重读 第 10 小节，“以智能的方式创建多个块](#part0023.xhtml_ch10)”，它解释了此处所有的代码。

所添加的纹理看起来如 图 11.1 所示。它被放置在 Sam 之墙（Sam’s Wall）的顶部和底部，这是第二个块。

![Image](img/image00598.jpeg)

**图 11.1** Sam 之墙的辅助纹理。

图 11.1 显示`samstone2.png`是因为它是`BlockSamStone`中使用的第三个纹理。如果你想添加带有自定义纹理的第三个元数据，对应的图像应为`samstone3.png`。

由于现在了一个额外的图像，它也必须在`BlockSamStone`类中注册。这样做非常简单。在`registerIcons`方法中，`IIcon`数组的大小必须从 2 增加到 3，这会自动加载刚刚添加的`samstone2.png`图像。

接下来，必须编辑`getIcon`方法，使其首先检查元数据，然后对于每个元数据根据侧面选择正确的纹理。如 第 10 小节 所述，`getIcon`的第二个参数是元数据。第一个是块的侧面。`getIcon`的新代码应该像 列表 11.2 所示。

**列表 11.2 使用新纹理的 getIcon**

点击此处查看代码图片

```
@Override
@SideOnly(Side.CLIENT)
public IIcon getIcon(int par1, int par2)
{
    switch(par2)
    {
    case 0:
        return icons[0];
    case 1:
        if(ForgeDirection.getOrientation(par1) == ForgeDirection.UP || ForgeDirection.getOrientation(par1) == ForgeDirection.DOWN)
            return icons[2];
        else
            return icons[1];
    default:
        System.out.println("Problems with the icon for BlockSamStone");
        return null;
    }
}
```

首先，对元数据`par2`进行了`switch`语句。如果是元数据 0，则选择纹理 0。否则，是元数据 1。在这种情况下，需要一个`if`和`else`语句来检查侧面。`ForgeDirection`是 Forge 创建的一个类，用于轻松获取侧面。`getOrientation`方法接收一个整数并将其转换为`ForgeDirection`，这要易读得多。Minecraft 中的顶部和底部纹理是 0 和 1，但有了`ForgeDirection`，你不需要记住这些数字。相反，你可以轻松将它们转换为侧面。如果侧面是顶部或底部，则对块应用第三个纹理。如果都不是两者，则使用第二个纹理。当元数据不是 0 或 1 时，说明有问题并应该修复。因此，会为程序员打印一条消息并返回`null`，这可能会导致崩溃。现在，该块看起来应该如 图 11.2 所示。

![Image](img/image00599.jpeg)

**图 11.2** 块

### 制作半块

现在我们学习如何制作半块。半块在 Minecraft 中是不常见的，但现在 mod 中非常常见。为了确保块是 1x1x1，你需要在构造函数中使用一行代码。

你需要添加到构造函数中的代码如下：点击此处查看代码图片

```
this.setBounds(0.0F, 0.0F, 0.0F, 1.0F, 0.5F, 1.0F);
```

此方法包含六个浮点值。前三个是起始位置，后三个是结束位置。起始位置是左下角，结束位置是顶部。在这种情况下，块的高度只有一半。

### 你自己尝试：创建不同形状

尝试创建一些形状不同的块，例如：

![Image](img/image00591.jpeg) 只有一半的块

![Image](img/image00591.jpeg) 四分之一

![Image](img/image00591.jpeg) 空中的半块

如果你启动游戏并将此块与其他块放在一起，你会发现它变成了蓝色并且你可以看到它的世界。这显然不是你想要的，所以你需要添加一个方法来防止这种情况。该方法如下：点击此处查看代码图片

```java
@Override
public boolean isOpaque()
{
    return false;
}
```

当你重启游戏并将此块放在另一个块旁边，你会发现它看起来恢复正常。

### 注意：其他形状

正如你可能已经发现，你只能使用`setBounds`创建正方形块。然而，游戏中的某些块并不是正方形。这些块不是使用`setBounds`创建的，而是使用`ISimpleRenderingHandler`，这是 Forge 中的一个用于自定义渲染的类。`ISimpleRenderingHandler`的示例可以在 附录 A，“附加代码片段](#part0041.xhtml_app01)”找到。

有了这些新代码，`BlockSamStone`看起来应该像 列表 11.3。

**列表 11.3 半块的 BlockSamStone**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import java.util.List;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.item.Item;
import net.minecraft.item.ItemStack;
import net.minecraft.util.Facing;
import net.minecraft.util.IIcon;
import net.minecraft.world.IBlockAccess;
import net.minecraftforge.common.util.ForgeDirection;
import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class BlockSamStone extends Block
{
    String name = "samstone";
    @SideOnly(Side.CLIENT)
    private IIcon[] icons;
}
```

```java
public BlockSamStone()
{
    super(Material.rock);
    setBlockName(SamsMod.MODID + "_" + name);
    setCreativeTab(CreativeTabs.tabBlock);
    setHardness(2F);
    setResistance(5F);
    setStepSound(soundTypeStone);
    setHarvestLevel("pickaxe", 2);
    this.setBlockBounds(0.0F, 0.0F, 0.0F, 1.0F, 0.5F, 1.0F);
}

@Override
public boolean isOpaqueCube()
{
    return false;
}

@Override
@SideOnly(Side.CLIENT)
public void registerBlockIcons(IIconRegister par1IconRegister)
{
    icons = new IIcon[3];
    for (int i = 0; i < icons.length; i++)
    {
        icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samstone" + i);
    }
}

@Override
@SideOnly(Side.CLIENT)
public IIcon getIcon(int par1, int par2)
{
    switch(par2)
    {
        case 0:
            return icons[0];
        case 1:
            if(ForgeDirection.getOrientation(par1) == ForgeDirection.UP || ForgeDirection.getOrientation(par1) == ForgeDirection.DOWN)
                return icons[2];
            else
                return icons[1];
        default:
            System.out.println("Problems with getting the icon for BlockSamStone");
            return null;
    }
}

@SuppressWarnings({"unchecked", "rawtypes"})
@SideOnly(Side.CLIENT)
@Override
public void getSubBlocks(Item par1, CreativeTabs par2, List par3List)
{
    for (int var4 = 0; var4 < 2; ++var4)
    {
        par3List.add(new ItemStack(par1, 1, var4));
    }
}
```

## 自自己尝试：基于元数据的区块

使用`setBlockBoundsOnState`方法来确保第二个元数据区块具有半形状。要实现这一点，你不需要构造函数中的那行代码。相反，将其与`IBlockAccess`变量结合以查找元数据并在那里使用`setBlockBounds`。

仅对第二个元数据为半块区块的代码示例如下：

```java
public void setBlockBoundsOnState(IBlockAccess world, int x, int y, int z)
{
    if(world.getBlockMetadata(x, y, z) == 1)
    {
        setBlockBounds(0F, 0F, 0F, 1F, 0.5F, 1F);
    }
}
```



必须移除构造函数中的 `setBlockBounds` 行。

### 创建植物

你可能想要添加到你的 mod 中的下一种独特类型的区块是植物。植物是元数据区块，但它们需要大量的特殊代码。

#### 编写基础代码

要添加植物，你需要结合到目前为止所学的大部分信息。然而，与任何其他区块一样，你使用类似的代码将其添加到你的 mod 类中：

```java
public static Block samPlant;
```

在 `preInit` 方法中添加以下代码：

```java
samPlant = new BlockSamPlant();

GameRegistry.registerBlock(samPlant, "SamPlant");
```

此外，`BlockSamPlant` 类的开头与标准区块也相似。你需要添加一个构造函数，添加一个带有 `Material` 的 `super`，设置未本地化名称等。添加这些基础代码后，`BlockSamPlant` 类应该如列表 11.4 所示。

**列表 11.4 BlockSamPlant 中的基础**

```java
package com.wuppy.samsmod;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;
import net.minecraft.creativetab.CreativeTabs;

public class BlockSamPlant extends Block
{
    public BlockSamPlant()
    {
        super(Material.plants);
        setBlockName(SamsMod.MODID + "_" + "plant");
        setCreativeTab((CreativeTabs)null);
        setHardness(0.0F);
        setStepSound(soundTypeGrass);
    }
}
```

注意，`BlockSamPlant` 没有 `setBlockTextureName` 行。这是因为植物通常有多个纹理，这意味着你必须使用另一种注册纹理的方法。此文件中的另一行有趣的代码是 `setCreativeTab` 方法。这行代码简单地确保 `BlockSamPlant` 不出现在创造模式菜单中。两行代码旨在让它看起来像植物——硬度（这让这种植物可以立即被破坏）以及形状（它与小麦相同）。此外，在 `lang` 文件中添加了如下本地化内容：

`tile.samplant.name=Sam’s Plant`

现在，添加与多个图标相关的代码，它应该如列表 11.5 所示。

**列表 11.5 BlockSamPlant 的图标代码**

```java
@SideOnly(Side.CLIENT)
private IIcon[] icons;

@Override
@SideOnly(Side.CLIENT)
public void registerBlockIcons(IIconRegister par1IconRegister)
{
    icons = new IIcon[3];

    for (int i = 0; i < icons.length; i++)
    {
        icons[i] = par1IconRegister.registerIcon(
            SamsMod.MODID + ":" + "samplant" + i
        );
    }
}

@Override
@SideOnly(Side.CLIENT)
public IIcon getIcon(int par1, int par2)
{
    if (par2 < 0 || par2 >= 3)
    {
        System.out.println("Something is wrong with the metadata for BlockSamPlant!");
        return icons[0];
    }
    else
    {
        return icons[par2];
    }
}
```

`BlockSamPlant` 有三个阶段，这意味着 `IIcon` 数组在索引 0、1、2 处有图像。这些纹理也必须制作，参见图 11.3、11.4 和 11.5。

在 `getIcon` 方法中，检查元数据。如果由于某种原因小于 0 或大于或等于 3，则将其设置为第一个图像。如果不是，它将根据元数据返回图像。

尽管作物具有元数据，但通常不需要为它制作 `ItemBlock` 类，因为你不会处理拿起和放置不同的元数据。相反，大多数植物通过种子工作。

#### 使其成为作物

在 `BlockSamPlant` 完全作为作物工作之前，你需要在类中添加几个方法。

##### 使它看起来像作物

以下方法确保了新区块看起来像作物：

```java
@Override
public int getRenderType()
{
    return 6;
}
```

还有其他的渲染类型，可以通过查看自定义渲染区块来找到。

##### 确保游戏知道它是植物

现在是时候让 `BlockSamPlant` 被识别并作为作物工作了。要这样做，将扩展类从 `Block` 更改为 `BlockBush`。该类还需要实现 `IGrowable`，使类行变为：

```java
public class BlockSamPlant extends BlockBush implements IGrowable
```

当你添加这段代码时，可能会遇到一些错误。首先，你必须导入 `BlockBush` 和 `IGrowable` 类。一旦完成这些操作，它会要求你添加几个方法，它们看起来如下：

点击此处查看代码图片

```java
@Override
public boolean func_149851_a(World var1, int var2, int var3, int var4, boolean var5)
{
    // TODO Auto-generated method stub
    return false;
}

@Override
public boolean func_149852_a(World var1, Random var2, int var3, int var4, int var5)
{
    // TODO Auto-generated method stub
    return false;
}

@Override
public void func_149853_b(World var1, Random var2, int var3, int var4, int var5)
{
    // TODO Auto-generated method stub
}
```

遗憾的是，这些方法尚未被本地化，因此它们具有不清晰的 `func` 名称。

首先，必须编写 `func_149851_a`。这是一个检查是否可以使用骨粉肥料的方法。对于作物来说，只要元数据（metadata）不在顶层或更高层（即为 2），就允许使用骨粉。该方法应该如下：

点击此处查看代码图片

```java
@Override
public boolean func_149851_a(World world, int x, int y, int z, boolean var5)
{
    return world.getBlockMetadata(x, y, z) != 2;
}
```

如果在应用骨粉时通过了此函数的检查，则会检查下一个函数，即 `func_149852_a`。此方法应该包含一个让骨粉成功的随机概率。如果你想让骨粉总是生效，只需始终返回 `true` 即可。否则，可以使用方法中的 `rand` 变量创建一个简单的随机数。对于这种植物，它看起来如下：

点击此处查看代码图片

```java
@Override
public boolean func_149852_a(World world, Random rand, int x, int y, int z)
{
    return true;
}
```

在运行完这两个检查后，就是时候实际编写应用骨粉时应该发生的情况了。你在 `func_149853_b` 方法中完成操作。对于 `BlockSamPlant` 骨粉，只需将生长阶段增加一。在这种情况下，方法如下：

点击此处查看代码图片

```java
@Override
public void func_149853_b(World world, Random rand, int x, int y, int z)
{
    int next = world.getBlockMetadata(x, y, z) + 1;

    if (next > 2)
    {
        next = 2;
    }

    world.setBlockMetadataWithNotify(x, y, z, next, 2);
}
```

在 `func_149853_b` 方法中，获取了元数据并对其增加。尽管你在之前的方法中检查过元数据，但在这里再次检查是明智的，因为可能有其他 mod 使用相同的方法来制作不同的植物生长材料（这是可能发生的），而且它们没有正确使用元数据检查方法。然后，使用 `setBlockMetadataWithNotify` 设置元数据。此方法确保现有方块的元数据被更改。在 `setBlockMetadataWithNotify` 行中，使用了位置以及新的元数据。然而，还有一个额外的数字，即 2。这个数字基本上一直应该是 2，以确保客户端知道方块确实存在。

### 动手尝试：制作随机植物

为骨粉制作一种更随机的植物。让骨粉每三次只生效一次。但是，当它生效时，让它向元数据增加 0 到 2 之间的值。

相应的代码应该如下：

点击此处查看代码图片

```java
@Override
public boolean func_149852_a(World world, Random rand, int x, int y, int z)
{
    if (rand.nextInt(3) == 0)
    {
        return true;
    }
    else
    {
        return false;
    }
}

@Override
public void func_149853_b(World world, Random rand, int x, int y, int z)
{
    int next = world.getBlockMetadata(x, y, z) + rand.nextInt(3);

    if (next > 2)
    {
        next = 2;
    }

    world.setBlockMetadataWithNotify(x, y, z, next, 2);
}
```

### 自然生长

接下来是一个非常重要的方法。此方法确保植物在没有骨粉的情况下生长。该方法名为 `updateTick`，处理方块的生长。对于 `BlockSamPlant`，代码应如下：

```java
public void updateTick(World world, int x, int y, int z, Random rand)
{
    super.updateTick(world, x, y, z);

    if (world.getValue(x, y, z) >= 9)
    {
        int l = world.getBlockMetadata(x, y, z);

        if (l < 2)
        {
            if (rand.nextInt(5) == 0)
            {
                l++;
            }

            world.setBlockMetadataWithNotify(x, y, z, l, 2);
        }
    }
}
```

简单来说，这确保了它只会生长。如果你跳过此步，Minecraft 可能会崩溃。所有的检查都完成了，元数据增加了。然后调用 `setBlockMetadataWithNotify`。这同步了服务器和客户端。这里的最后一个数字应该是 2。

现在你有了可以工作的植物，最好能有一种获取它们的方法。这有两种方式实现：首先通过种子，其次通过世界生成。

### 添加种子

要添加种子，你需要在主文件中为每个物品添加基础代码。然而，种子的构造函数必须不同。请注意以下代码存在错误。

在类中添加以下代码：

`public static Item samseed;`

这是 `preInit` 方法所需的代码：

点击此处查看代码图片

```java
samseed = new ItemSamSeed(samPlant);

GameRegistry.registerItem(samseed, "SamSeed");
```

你应该熟悉这里的所有代码。创建了一个 `Item` 对象，随后将其设置为 `ItemSamSeed`（稍后会创建），然后注册该物品。唯一的额外代码是 `ItemSamSeed` 的参数是 `samPlant`。这个参数应该是那个被种子种植的植物。

现在要修复 `ItemPlant` 下的错误，必须创建该类，你可以通过将鼠标悬停在错误上并点击“创建类”来轻松实现。标准类应该如列表 11.6 所示。

**列表 11.6 标准 ItemPlant 类**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.item.Item;

public class ItemSamPlant extends Item
```

在这个类中，你添加了多个方法。就像任何其他物品或方块一样，你从构造函数开始。此构造函数有一个参数，即 `Block`。目前它看起来如下：

点击此处查看代码图片

```java
public ItemSamSeed(Block plant)
{
}
```

接下来，你创建两个私有变量。一个是一个 `Block`，命名为 `plant`。另一个必须是 `String`，包含种子的名称。只需要初始化该 `String`。名称为 `"samseed"`。接下来，这两个变量都必须被使用。对于 `Block` 变量，这意味着将其设置为构造函数中的 `plant` 参数。对于名称，这意味着设置未本地化名称（unlocalized name）和纹理名称（texture name）。带有变量的构造函数应该类似于列表 11.7。

### 列表 11.7 ItemSam 的构造函数

```java
private Block plant;

private String name = "samseed";

public ItemSamSeed(Block plant)
{
    this.plant = plant;
    setUnlocalizedName(SamsMod.MODID + "_" + name);
    setTextureName(SamsMod.MODID + ":" + name);
    setCreativeTab(CreativeTabs.tabMaterials);
}
```

与名称相关的代码与其他任何物品非常相似。它只是像其他物品一样设置了未本地化名称和纹理名称。唯一可能奇怪的代码行是 `this.plant = plant`。它看起来像是变量正在被赋值为自身，但实际上是将类中的 `plant` 设置为参数中的 `plant`。每当你在一段代码前加上前缀（无论是变量还是方法）时，它都会尝试在类中查找它，而不是在方法本身。在这种情况下，它找到了类的 `plant` 变量。

额外的一行代码是 `setCreativeTab` 这一行，尽管你现在应该已经理解它了。因为现在设置了未本地化名称和纹理名称，所以需要本地化文件和纹理。`ItemSamSeed` 的本地化内容如下：

```text
item.wuppy29_samsmod_samseed.name=Sam’s Seed
```

纹理类似于图 11.6 并保存为 `samseed.png`。

![图像](img/image0060.jpeg)

**图 11.6** Sam’s Seed 的纹理。

现在，Sam’s Seed 物品的基本代码已经完成。接下来，确保它实际上是一个种子非常重要。你通过让它实现 `IPlantable` 接口来实现这一点。当你向类行添加 `extends IPlantable` 代码时，它首先会在下方显示一个错误，告诉你应该导入它。导入此文件后，类名下方会出现另一个错误。要修复这个错误，请添加未实现的方法。当你这样做时，添加的代码应该类似于此所示：

```java
@Override
public EnumPlantType getPlantType(IBlockAccess world, int x, int y, int z)
{
    // TODO Auto-generated method stub
    return null;
}

@Override
public Block getPlant(IBlockAccess world, int x, int y, int z)
{
    // TODO Auto-generated method stub
    return null;
}

@Override
public int getPlantMetadata(IBlockAccess world, int x, int y, int z)
{
    // TODO Auto-generated method stub
    return 0;
}
```



这些方法都非常容易填充。第一个方法 `getPlantType` 要求你返回一个 `EnumPlantType`，以确保 Java 知道正在添加哪种植物。在 Sam’s Seed 的情况下，此方法看起来所示：

```java
@Override
public EnumPlantType getPlantType(IBlockAccess world, int x, int y, int z)
{
    return EnumPlantType.Crop;
}
```

要找到其他植物类型，请前往 `EnumPlantType` 类并选择最适合你正在创建的植物的一个。

`getPlant` 方法决定了在使用种子时放置哪种植物，而 `getPlantMetadata` 则设置放置时的植物元数据。对于 Sam’s Seed，这两个方法都应该如下所示：

```java
@Override
public Block getPlant(IBlockAccess world, int x, int y, int z)
{
    return plant;
}

@Override
public int getPlantMetadata(IBlockAccess world, int x, int y, int z)
{
    return 0;
}
```

这些方法中没有是直接用于植物的，但某些模组可能会使用它们，因此添加这段代码是重要的。现在是时候让种子在右键点击时真正生长了。实现该功能的方法如下所示：

```java
public boolean onItemUse(ItemStack par1ItemStack, EntityPlayer par2EntityPlayer, World par3World, int par4, int par5, int par6, int par7, float par8, float par9, float par10)
{
    if (par7 != 1)
    {
        return false;
    }
    else if (par2EntityPlayer.canEdit(par4, par5, par6, par1ItemStack) && par2EntityPlayer.canEdit(par4, par5 + 1, par6, par1ItemStack))
    {
        if(par3World.getBlock(par4, par5, par6) == Blocks.dirt || par3World.getBlock(par4, par5, par6) == Blocks.grass)
        {
            if (par3World.isAirBlock(par4, par5 + 1, par6))
                {
                    par3World.setBlock(par4, par5 + 1, par6, this.plant);
                    --par1ItemStack.stackSize;
                    return true;
                }
                else
                {
                    return false;
                }
            }
            else
            {
                return false;
            }
        }
        else
        {
            return false;
        }
}
```

首先，要确保玩家点击的是方块的顶部。因为大多数植物只能放置在方块上方。接下来，要检查玩家和上方的方块是否可以编辑。如果是这样，则检查放置植物的地方是否是空气。

如果这些条件都满足，植物将被放置，种子堆数量减少一。其他选项将返回 `false` 且什么都不做。`ItemSeed` 应该类似于列表 11.8。

### 列表 11.8 Finished ItemSam

```java
package com.wuppy.samsmod;

import net.minecraft.block.Block;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.entity.player.EntityPlayer;
import net.minecraft.init.Blocks;
import net.minecraft.item.Item;
import net.minecraft.item.ItemStack;
import net.minecraft.world.IBlockAccess;
import net.minecraft.world.World;
import net.minecraft.forge.common.EnumPlantType;
import net.minecraft.forge.common.IPlantable;

public class ItemSamSeed implements IPlantable
{
    private Block plant;
    private String name = "seed";

    public ItemSamSeed(Block plant)
    {
        this.plant = plant;
        setUnlocalizedName(SamsMod.MODID + "_" + name);
        setTextureName(SamsMod.MODID + ":" + name);
        setCreativeTab(CreativeTabs.tabMaterials);
    }

    public boolean onItemUse(ItemStack par1ItemStack, EntityPlayer par2EntityPlayer, World par3World, int par4, int par5, int par6, int par7, float par8, float par9, float par10)
    {
        if (par7 != 1)
        {
            return false;
        }
        else if (par2EntityPlayer.canEdit(par4, par5, par6, par1ItemStack) && par2EntityPlayer.canEdit(par4, par5 + 1, par6, par1ItemStack))
        {
            if(par3World.getBlock(par4, par5, par6) == Blocks.dirt || par3World.getBlock(par4, par5, par6) == Blocks.grass)
            {
                if (par3World.isAirBlock(par4, par5 + 1, par6))
                {
                    par3World.setBlock(par4, par5 + 1, par6, this.plant);
                    --par1ItemStack.stackSize;
                    return true;
                }
                else
                {
                    return false;
                }
            }
            else
            {
                return false;
            }
        }
        else
        {
            return false;
        }
    }
}
```

```java
            return true;
        }
    else
    {
        return false;
    }
}
else
{
    return false;
}
}
else
{
    return false;
}
}

@Override
    public EnumPlantType getPlant(IBlockAccess world, int x, int z)
    {
        return EnumPlantType.Crop;
    }
@Override
    public Block getPlant(IBlockAccess world, int x, int z)
    {
        return plant;
    }
@Override
    public int getMetadata(IBlockAccess world, int x, int z)
    {
        return 0;
    }
}
```

### 自定义植物

接下来，如果能给植物增加一些自定义，使其与所有现有植物区别开来，那就太好了。为此你可以添加的方法之一是 `canPlaceOn`。该方法决定了植物可以在哪些区块上生长。`SamPlant` 能够在 `dirt` 和 `grass` 上生长，所以代码看起来如下：

```java
protected boolean canPlaceOn(Block block)
{
    if(block == Blocks.dirt || block == Blocks.grass)
        return true;
    else
        return false;
}
```

在此段代码中，`Block` 参数是植物放置的区块。它简单地检查其是否为 `dirt` 或 `grass` 并返回 `true`，从而允许植物被放置。任何其他区块都会返回 `false`。

你可能想为植物添加的另一个自定义功能是物品的掉落。你可以通过多种方式向区块添加掉落物。如果只有一个掉落物，可以通过 `getItemDropped` 和 `getQuantity` 来实现，这两个方法分别要求你返回一个 `Item` 和一个 `int` 来设置掉落物。

如果你想掉落多个物品，做法会稍有不同。首先，你添加此方法：

```java
public void dropBlockAsItemWithChance(World world, int par1, int par2, int par3, int par4, float par5, int par6)
{
    super.dropBlockAsItemWithChance(world, par1, par2, par3, par4, par5, 0);
}
```

这确保了调用一个不同的方法。该方法是 `getDrops`，它允许你向被破坏的区块添加多个掉落物。

对于 Sam 的植物，其如下如下：

```java
@Override
public ArrayList<ItemStack> getDrops(World world, int x, int y, int z, int metadata, int fortune)
{
    ArrayList<ItemStack> ret = new ArrayList<ItemStack>();
    if (metadata >= 2)
    {
        for (int i = 0; i < 3 + fortune; ++i)
        {
            if (world.rand.nextInt(15) <= 7)
            {
                ret.add(new ItemStack(SamsMod.berry, 1, 0));
            }
        }
    }
    for (int i = 0; i < 1+ fortune; i++)
    {
        ret.add(new ItemStack(SamsMod.seed, 1 + world.rand.nextInt(1 + fortune), 0));
    }
    return ret;
}
```

该方法检查植物是否完全成熟；如果是，它将通过一个 `for` 循环，将浆果添加到掉落的物品中。如果玩家使用带有 `fortune`（幸运）的物品进行采集，掉落概率会更高。种子也是如此。不过，种子没有随机性。种子总是掉落 1 颗加上幸运等级的数量。整个 `BlockPlant` 类看起来应该如列表 1.9 所示。

### 1.9 完成的 BlockPlant



```java
package com.uppy.amsmod;

import java.util.ArrayList;
import java.util.Random;

import net.minecraft.block.Block;
import net.minecraft.block.Bush;
import net.minecraft.block.IGrowable;
import net.minecraft.block.material.Material;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativab.CreativeTabs;
import net.minecraft.init.Blocks;
import net.minecraft.init.Items;
import net.minecraft.item.Item;
import net.minecraft.item.ItemStack;
import net.minecraft.util.IIcon;
import net.minecraft.world.World;

import cpw.mods.fml.launcher.Side;
import cpw.mods.fml.launcher.SideOnly;

public class BlockSamPlant extends Bush implements IGrowable
{
    @SideOnly(Side.CLIENT)
    private IIcon[] icons;

    public BlockSamPlant()
    {
        super(Material.plants);
        setBlockName(SamsMod.MODID + "_" + "samplant");
        setCreativeTab((CreativeTabs)null);
        setHardness(0.0F);
        setBlockBounds(0F, 0.0F, 0F, 1F, 0.25F, 1F);
        setStepSound(soundTypeGrass);
    }

    @Override
    @SideOnly(Side.CLIENT)
    public void registerBlockIcons(IIconRegister par1IconRegister)
    {
        icons = new IIcon[3];

        for (int i = 0; i < icons.length; i++)
        {
            icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samplant");
        }
    }

    @Override
    @SideOnly(Side.CLIENT)
    public IIcon getIcon(int par1, int par2)
    {
        if (par2 < 0 || par2 >= 3)
        {
            System.out.println("Something is wrong with the metadata for SamPlant!");
            return icons[0];
        }
        else
        {
            return icons[par2];
        }
    }

    @Override
    public int getRenderType()
    {
        return 6;
    }

    public void updateTick(World world, int x, int y, int z, Random rand)
    {
        super.updateTick(world, x, y, z);

        if (world.getBlockLight(x, y + 1, z) >= 9)
        {
            int l = world.getBlockMetadata(x, y, z);

            if (l < 2)
            {
                if (rand.nextInt(5) == 0)
                {
                    ++l;
                    world.setBlockMetadataWithNotify(x, y, z, l, 2);
                }
            }
        }
    }

    protected boolean canPlaceOn(Block block)
    {
        if (block == Blocks.dirt || block == Blocks.grass)
        {
            return true;
        }
        else
        {
            return false;
        }
    }

    public void dropBlockAsItemWithChance(
        World world,
        int par1,
        int par2,
        int par3,
        int par4,
        float par5,
        int par6
    )
    {
        super.dropBlockAsItemWithChance(world, par1, par2, par3, par4, par5, 0);
    }

    @Override
    public ArrayList<ItemStack> getDrops(
        World world,
        int x,
        int y,
        int z,
        int metadata,
        int fortune
    )
    {
        ArrayList<ItemStack> ret = new ArrayList<ItemStack>();

        if (metadata >= 2)
        {
            for (int i = 0; i < 3 + fortune; ++i)
            {
                if (world.rand.nextInt(15) <= 7)
                {
                    ret.add(new ItemStack(SamsMod.berry, 1, 0));
                }
            }
        }

        for (int i = 0; i < 1 + fortune; i++)
        {
            ret.add(new ItemStack(
                SamsMod.seed,
                1 + world.rand.nextInt(1 + fortune),
                0
            ));
        }

        return ret;
    }
}
```

```java
public void func_149853_b(World world, Random rand, int x, int y, int z)
{
    int next = world.getBlockMetadata(x, y, z) + 1;

    if (next > 2)
    {
        next = 2;
    }

    world.setBlockMetadataWithNotify(x, y, z, next, 2);
}
```

***

图 11.7 显示了游戏中的植物。

![Image](img/image00604.jpeg)

**图 11.7** 游戏中的植物。

图 11.8 显示了游戏中用于种植这种植物的种子物品。

![Image](img/image00605.jpeg)

**图 11.8** 游戏中的种子。

## 总结

在本小时中，你学习了许多关于自定义区块的知识。首先，你学习了如何根据区块的侧面显示不同的纹理。之后，你制作了半块和特殊形状的区块。最后，你创建了到目前为止最困难的区块——植物。这种植物只在光照下生长，并且只能放置在土壤或草地上。它被破坏时会掉落浆果和种子。

## 问答

**Q. 游戏中可以添加的植物数量有上限吗？**

**A.** 植物被视为普通区块，因此适用相同的最大数量限制。

**Q. 还有其他可能的自定义方式吗？**

**A.** 当然有。了解如何自定义你的区块有两种方法：首先是查看 `Block` 类，可以在其中找到许多有趣的自定义方法。或者，查看一个已存在的原版区块（vanilla block）的代码，看看它是如何被编码的。

## 工作坊

在本小时中，你学习了如何为你的区块创建许多特定的内容。了解如何自定义它们非常重要，因为这让你的 Mod 变得独特且实用。请通过以下工作坊来确保你理解了这些自定义内容。

## 测验

**1. 为什么作物不需要 `ItemBlock` 文件？**

**2. 你将如何增加作物的生长速度？**

## 答案

**1.** 因为作物在放置时元数据始终为 0，所以实际上并不需要 `ItemBlock` 文件。

**2.** 你可以通过编辑 `updateTick` 方法来实现。

## 练习题

修改植物的掉落逻辑，使其在掉落所有现有物品的同时，总是也会掉落一个金苹果。

列表 11.10 显示了实现该功能所需的代码。

**列表 11.10 带有金苹果的掉落物**

点击此处查看代码图像

***

```java
@Override
public ArrayList<ItemStack> getDrops(
    World world,
    int x,
    int y,
    int z,
    int metadata,
    int fortune
)
{
    ArrayList<ItemStack> ret = new ArrayList<ItemStack>();

    if (metadata >= 2)
    {
        for (int i = 0; i < 3 + fortune; ++i)
        {
            if (world.rand.nextInt(15) <= 7)
            {
                ret.add(new ItemStack(SamsMod.berry, 1, 0));
            }
        }
    }

    for (int i = 0; i < 1 + fortune; i++)
    {
        ret.add(new ItemStack(
            SamsMod.seed,
            1 + world.rand.nextInt(1 + fortune),
            0
        ));
    }

    ret.add(new ItemStack(Items.golden_apple, 1, 0));
    return ret;
}
```

***

## 第 12 小时：创建方实体（Tile Entity）

### 本小时你将学习到

- 理解方实体
- 创建方实体
- 创建另一个方实体
- 服务器同步

***

在本小时中，你将学习如何制作方实体。尽管名称中包含“实体（Entity）”，但方实体实际上可以被看作一个区块。首先，你需要了解什么是方实体，因为它非常复杂。在了解什么是方实体之后，就是时候使用并创建一个基础的方实体了。

## 理解什么是方实体

Minecraft 中的方实体可以被视为一种实体，它与所在的区块占据相同的位置。方实体可以存储有关区块的额外信息，还可以打开界面、持有物品以及许多其他功能。

方实体可以被认为是 Minecraft 最难的部分之一。如果不计算世界生成或所有内容在屏幕上的显示方式，方实体是最复杂的。因为它们很复杂，所以也具有极高的自定义性。你基本上可以使用方实体做任何事情。很多 Mod 都使用它们来实现某些有趣的行为。例如多区块结构（multiblock structure），即多个区块协作完成单项任务。另一个例子可以是制作传输液体或能量的管道。

所有这些示例以及泛指的方实体存在的问题是，它们过于复杂且具体，无法进行恰当的解释。由于方实体重要且常见，拥有基础的理解至关重要。虽然方实体的复杂性超出了本书的范围，但本小时涵盖了如何创建方实体的基础代码。

你在本小时中创建的方实体非常简单。该区块有 10 个纹理。所有纹理都是黑色的，上面有一个从 0 到 9 的白色数字。方实体每秒更新一次纹理。尽管这听起来非常简单，但这项任务需要大量的工作。

## 创建方实体区块

要创建一个作为方实体的区块，你首先需要一个基础区块。在本小时中创建的方实体代码如下：

```java
public static Block samTE;
```

此外，将此代码添加到 `preInit` 方法中：

```java
samTE = new BlockSamTE();
GameRegistry.registerBlock(samTE, "SamTE");
```

当你添加这些后，`BlockSamTE` 下会出现一个错误，你可以通过创建文件来修复。在添加 `BlockSamTE` 类后，进行简单的清理并添加最基础的构造函数以移除所有错误，该类看起来应该像列表 12.1。

**列表 12.1 基础 `BlockSamTE` 类**

```java
package com.wuppy.samsmod;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;

public class BlockSamTE extends Block
{
    public BlockSamTE()
    {
        super(Material.rock);
    }
}
```

***

你现在必须在此区块中添加两个必要的变量：

```java
private String name = "samte";
private IIcon[] icons;
```

第一个变量正如其名一样，保存区块的名称。它的用法与任何其他区块相同。`IIcon` 数组也是如此，它用于存储此区块的纹理。

为了确保区块能够正常运行并经过合理的自定义，构造函数应该如下所示：

```java
public BlockSamTE()
{
    super(Material.rock);
    setBlockName(SamsMod.MODID + "_" + name);
    setCreativeTab(CreativeTabs.tabBlock);
    setHardness(2F);
    setResistance(5F);
    setStepSound(soundTypeStone);
    setHarvestLevel("pickaxe", 2);
}
```

这些代码在之前几节关于方块（blocks）的内容已经解释过了，因此这段代码中没有任何内容会让你感到意外。以下代码处理方块的 10 种不同纹理。代码在之前的章节中也涵盖过。如果你需要复习，请再次阅读第 10 节和“智能地创建多个方块”。

点击此处查看代码图像

```java
@Override
@SideOnly(Side.CLIENT)
public void registerBlockIcons(IIconRegister par1IconRegister)
{
    icons = new IIcon[10];

    for (int i = 0; i < icons.length; i++)
    {
        icons[i] = par1IconRegister.registerIcon(
            SamsMod.MODID + ":" + "samte" + i
        );
    }
}

@Override
@SideOnly(Side.CLIENT)
public IIcon getIcon(int par1, int par2)
{
    return icons[par2];
}
```

尽管这个方块有 10 个不同的元数据（metadatas），但它始终作为元数据 0 掉落，且不会以不同于元数据 0 的任何形式放置。因此，不需要 `ItemBlock`。此外，只有元数据 0 的方块会显示在创造模式列表中，所以这里不需要 `getSubBlocks` 方法。

方块纹理如图 12.1。

![Image](img/image0060.jpeg)

**图 12.1** 瓷砖实体（tile entity）纹理。

这些纹理被保存为独立的 16×16 像素纹理。

该方块还需要在 `en_US.lang` 文件中本地化，其看起来应该是这样的：

点击此处查看代码图像

```text
tile.wuppy29_samsmod_samte.name=Sam’s TileEntity
```

## 为方块添加瓷砖实体（Tile Entity）

现在方块的基础代码已经添加，是时候把它变成一个也具有瓷砖实体的方块了。要做到这一点，类应该继承 `BlockContainer` 而不是 `Block`。一旦你更改了继承类型，`BlockSamTE` 部分就会出现错误，你可以通过添加未实现的方法来修复它。这个方法只有一个，并且应该如下所示：

点击此处查看代码图像

```java
@Override
public TileEntity createNewTileEntity(World var1, int var2)
{
    // TODO Auto-generated method stub
    return null;
}
```



你应该在这个方法中编写的内容非常简单。它只需要返回你正在创建的 `TileEntity` 类即可。在 `BlockSamTE` 的情况下，它被称为 `TileEntitySam`。由于该类尚未创建，以下代码包含一个错误：

[点击此处查看代码图像]

```java
@Override
public TileEntity createNewTileEntity(World var1, int var2)
{
    return new TileEntitySam();
}
```

到此时，`BlockSamTE` 已经完成了，它看起来像列表 12.2。

**列表 12.2 完成的 `BlockSamTE`**

[点击此处查看代码图像]

```java
package com.wuppy.samsmod;

import net.minecraft.block.BlockContainer;
import net.minecraft.block.material.Material;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.tileentity.TileEntity;
import net.minecraft.util.IIcon;
import net.minecraft.world.World;
import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class BlockSamTE extends BlockContainer
{
    private String name = "samte";
    private IIcon[] icons;

    public BlockSamTE()
    {
        super(Material.rock);
        setBlockName(SamsMod.MODID + "_" + name);
        setCreativeTab(CreativeTabs.tabBlock);
        setHardness(2F);
        setResistance(5F);
        setSound(TypeStone);
        setHarvestLevel("pickaxe", 2);
    }

    @Override
    @SideOnly(Side.CLIENT)
    public void registerBlockIcons(IIconRegister par1IconRegister)
    {
        icons = new IIcon[10];
        for (int i = 0; i < icons.length; i++)
        {
            icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samte" + i);
        }
    }

    @Override
    @SideOnly(Side.CLIENT)
    public IIcon getIcon(int par1, int par2)
    {
        return icons[par2];
    }

    @Override
    public TileEntity createNewTileEntity(World var1, int var2)
    {
        return new TileEntitySam();
    }
}
```

### 为方块添加一个瓷砖实体（Tile Entity）

现在方块的基础代码已经添加，是时候把它变成一个也具有瓷砖实体的方块了。要做到这一点，类应该继承 `BlockContainer` 而不是 `Block`。一旦你更改了继承类型，`BlockSamTE` 部分就会出现错误，你可以通过添加未实现的方法来修复它。这个方法只有一个，并且应该如下所示：

[点击此处查看代码图像]

```java
@Override
public TileEntity createNewTileEntity(World var1, int var2)
{
    // TODO Auto-generated method stub
    return null;
}
```

你应该在这个方法中编写的内容非常简单。它只需要返回你正在创建的 `TileEntity` 类即可。在 `BlockSamTE` 的情况下，它被称为 `TileEntitySam`。由于该类尚未创建，以下代码包含一个错误：

[点击此处查看代码图像]

```java
@Override
public TileEntity createNewTileEntity(World var1, int var2)
{
    return new TileEntitySam();
}
```

到此时，`BlockSamTE` 已经完成了，它看起来像列表 12.2。

**列表 12.2 完成的 `BlockSamTE`**

[点击此处查看代码图像]

```java
package com.wuppy.samsmod;

import net.minecraft.block.BlockContainer;
import net.minecraft.block.material.Material;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.tileentity.TileEntity;
import net.minecraft.util.IIcon;
import net.minecraft.world.World;
import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class BlockSamTE extends BlockContainer
{
    private String name = "samte";
    private IIcon[] icons;

    public BlockSamTE()
    {
        super(Material.rock);
        setBlockName(SamsMod.MODID + "_" + name);
        setCreativeTab(CreativeTabs.tabBlock);
        setHardness(2F);
        setResistance(5F);
        setSound(TypeStone);
        setHarvestLevel("pickaxe", 2);
    }

    @Override
    @SideOnly(Side.CLIENT)
    public void registerBlockIcons(IIconRegister par1IconRegister)
    {
        icons = new IIcon[10];
        for (int i = 0; i < icons.length; i++)
        {
            icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samte" + i);
        }
    }

    @Override
    @SideOnly(Side.CLIENT)
    public IIcon getIcon(int par1, int par2)
    {
        return icons[par2];
    }

    @Override
    public TileEntity createNewTileEntity(World var1, int var2)
    {
        return new TileEntitySam();
    }
}
```

[点击此处查看代码图片]

```java
private int metadata;

@Override
public void updateEntity()
{
    counter++;
    if(counter == 20)
    {
        counter = 0;
        metadata = worldObj.getBlockMetadata(xCoord, yCoord, zCoord);
    }
}
```

注意 `counter` 变量和 `metadata` 变量初始化的区别。`counter` 在创建时被初始化为 0，因为无论 tile entity（实体实体）的初始状态如何，它总是从零开始。`metadata` 并没有在创建时初始化，而是在 `counter` 达到 20 时才初始化。这是因为在运行第一次更新时，`metadata` 并不总是 0。虽然区块在放置时 `metadata` 始终为 0，但当游戏停止并重启时，它可能不再是 0。因此，在开始时初始化它并不是明智的，而是在使用 `getBlockMetadata` 方法获取值后才进行初始化。

现在 `metadata` 已经存在了，我们应该将其增加 1。只需通过在 `metadata` 行上加上 `+1` 即可实现，代码应该如下所示：

[点击此处查看代码图片]

```java
metadata = worldObj.getBlockMetadata(xCoord, yCoord, zCoord) + 1;
```

然而，因为现在 `metadata` 增加了，所以需要一个检查来确保它不会超过 9，如果是，则将其设置为 0。添加此检查后，`updateEntity` 方法应该如下：

[点击此处查看代码图片]

```java
@Override
public void updateEntity()
{
    counter++;
    if(counter == 20)
    {
        counter = 0;
        metadata = worldObj.getBlockMetadata(xCoord, yCoord, zCoord) + 1;
        if(metadata > 9)
            metadata = 0;
    }
}
```

只剩一行代码了，这相对简单。这行代码实际上改变了区块的 `metadata`。对于这一点，可以使用 `World` 中的 `setBlockMetadataWithNotify` 方法。`setBlockMetadataWithNotify` 的参数与 `setBlock` 相同，只是缺少了 `Block` 参数。`updateEntity` 方法如下：

[点击此处查看代码图片]

```java
@Override
public void updateEntity()
{
    counter++;
    if(counter == 20)
    {
        counter = 0;
        metadata = worldObj.getBlockMetadata(xCoord, yCoord, zCoord) + 1;
        if(metadata > 9)
            metadata = 0;
        if(!worldObj.isRemote)
            worldObj.setBlockMetadataWithNotify(xCoord, yCoord, zCoord, metadata, 2);
    }
    super.updateEntity();
}
```

在方法的最后，使用 `super.updateEntity()` 是为了确保扩展类中的任何 `updateEntity` 代码也会运行。此外，在 `setBlockMetadataWithNotify` 之上添加了一个检查。在 Minecraft 中，存在客户端和服务器，当你只是在玩游戏时也是如此。大多数逻辑，尤其是可能导致异步问题的逻辑，应该在服务器上处理。因此，`metadata` 的更改应该只在服务器上运行，你可以通过在 `if` 语句中添加 `!worldObj.isRemote` 来。

### 服务器同步

tile entity 可以做的另一件事与服务器同步，并与玩家交互。此 tile entity 的玩家交互和服务器同步很简单。当区块被右键点击时，计数器切换 metadata。因为这改变了区块的工作方式，它必须在服务器和客户端之间进行同步。此项需要一个 `Boolean` 来检查计数器是否应该改变。变量应该如下：

[点击此处查看代码图片]

```java
private boolean counterEnabled = true;
```

该变量也应该在 `updateEntity` 方法中使用，以确保当它为 `true` 时才启用计数器。在那里有该检查，代码如下：

[点击此处查看代码图片]

```java
@Override
public void updateEntity()
{
    if(counterEnabled)
    {
        counter++;
        if(counter == 20)
        {
            counter = 0;
            metadata = worldObj.getBlockMetadata(xCoord, yCoord, zCoord) + 1;
            if(metadata > 9)
                metadata = 0;
            if(!worldObj.isRemote)
                worldObj.setBlockMetadataWithNotify(xCoord, yCoord, zCoord, metadata, 2);
        }
    }
    super.updateEntity();
}
```

所以 `counterEnabled` 基于右键点击区块。为了确保此工作，需要两点：首先是 `Block` 类中右键点击区块运行时的方法，其次是 tile entity 中响应该操作的方法。

***

### 注意：Eclipse 代码自动补全

此时，你应该已经知道当输入 `syso` 并按下 `Ctrl+Space` 时，它会自动将其替换为 `System.out.println`，这节省了时间。然而，`Ctrl+Space` 组合键也可以用于 Eclipse 中的几乎所有其他地方。图 12.2

**图 12.2** Eclipse 中的自动补全。

当你输入类名或变量名的一半时，可以按下 `Ctrl+Space`，让 Eclipse 尝试自动补全。如果只有一个选项，它会立即像 `syso` 一样生成。如果有多个选项（例如 tile entity 中的单词计数），会弹出一个窗口，你可以通过鼠标或方向键进行导航。一旦你找到了所需的条目，点击它或按回车即可自动为你放置。

***

#### 为你的区块添加右键点击功能

`BlockSamTE` 需要的方法名为 `onBlockActivated`。在这里，你应该检查区块上的 tile entity 是否实际上是 `TileEntitySam`。尽管它应该一直在那里且没有其他 tile entity 可以取代它的位置，但应该进行检查，以防出现错误。例如，假设某个 mod 无意中或故意更改了你的 tile entity。该方法应该如下所示。

[点击此处查看代码图片]

```java
@Override
public boolean onBlockActivated(World world, int x, int y, int z, EntityPlayer player, int side, float hitX, float hitY, float hitZ)
{
    TileEntity entity = world.getTileEntity(x, y, z);
    if(entity != null)
    {
        if(entity instanceof TileEntitySam)
        {
            TileEntitySam samEntity = (TileEntitySam) entity;
            if(!world.isRemote)
                samEntity.editCounter();
            return true;
        }
    }
    return false;
}
```

此方法中的所有变量通过其名称都应该是清晰的。最后四个参数可能需要更多解释。`side` 参数是击击中的区块侧面。最后三个参数是右键点击区块的精确坐标。

当右键点击方块时，将使用 `getTileEntity` 获取该位置上的实体实体（tile entity）。之后，会检查该实体是否为空且是否为 `TileEntitySam`。如果是，则会创建一个变量来存储该 `TileEntitySam`。然后会检查代码是否运行在服务器端，并调用实体实体中的一个新方法，即 `editCounter`。`editCounter` 包含了更改变量的逻辑。`BlockSamTE` 现在看起来应该像列表 12.4 所示。

### 列表 12.4 在 `BlockSamTE` 中右键点击

[点击此处查看代码图片]



```java
package com.wuppy.samsmod;

import net.minecraft.block.BlockContainer;

import net.minecraft.block.material.Material;

import net.minecraft.client.renderer.texture.IIconRegister;

import net.minecraft.creativetab.CreativeTabs;

import net.minecraft.entity.player.EntityPlayer;

import net.minecraft.tileentity.TileEntity;

import net.minecraft.util.IIcon;

import net.minecraft.world.World;

import cpw.mods.fml.relauncher.Side;

import cpw.mods.fml.relauncher.SideOnly;

public class BlockSamTE extends BlockContainer

{
    private String name = "samte";

    private IIcon[] icons;

    public BlockSamTE()
    {
        super(Material.rock);
        setBlockName(SamsMod.MODID + "_" + name);
        setCreativeTab(CreativeTabs.tabBlock);
        setHardness(2F);
        setResistance(5F);
        setStepSound(soundTypeStone);
        setHarvestLevel("pickaxe", 2);
    }

    @Override
    @SideOnly(Side.CLIENT)
    public void registerBlockIcons(IIconRegister par1IconRegister)
    {
        icons = new IIcon[10];
        for (int i = 0; i < icons.length; i++)
        {
            icons[i] = par1IconRegister.registerIcon(SamsMod.MODID + ":" + "samte" + i);
        }
    }

    @Override
    @SideOnly(Side.CLIENT)
    public IIcon getIcon(int par1, int par2)
    {
        return icons[par2];
    }

    @Override
    public TileEntity createNewTileEntity(World var1, int var2)
    {
        return new TileEntitySam();
    }

    @Override
    public boolean onBlockActivated(World world, int x, int y, int z, EntityPlayer player, int side, float hitX, float hitY, float hitZ)
    {
        TileEntity entity = world.getTileEntity(x, y, z);
        if(entity != null)
        {
            if(entity instanceof TileEntitySam)
            {
                TileEntitySam samEntity = (TileEntitySam) entity;
                if(!world.Remote)
                {
                    samEntity.editCounter();
                    return true;
                }
            }
        }
        return false;
    }
}
```

人们可能会好奇，为什么仅仅切换`counterEnabled`变量就需要`TileEntity`中的一个方法。然而，有几个步骤是确保其正常运行所必需。`TileEntitySam`中的`editCounter`方法应该像这样所示：点击此处查看代码图片。

```java
public void editCounter()
{
    counterEnabled = !counterEnabled;
    markDirty();
    worldObj.markForUpdate(xCoord, yCoord, zCoord);
}
```

首先，变量被切换。然后调用了两个方法，以确保客户端和服务器的同步。

### 发送数据

接下来，你需要告诉 Minecraft 要同步什么内容。为了做到这一点，需要四个新方法。其中一个方法写入所需的数据，一个方法读取数据，另外两个方法仅用于确保数据包（在客户端和服务器之间传输的数据称为数据包）是可用的。`TileEntitySam`中的四个新方法如下所示：点击此处查看代码图片。

```java
@Override
public void readFromNBT(NBTTagCompound tag)
{
    super.readFromNBT(tag);
    counter = tag.getInteger("counter");
    counterEnabled = tag.getBoolean("counterEnabled");
}

@Override
public void writeToNBT(NBTTagCompound tag)
{
    super.writeToNBT(tag);
    tag.setInteger("counter", counter);
    tag.setBoolean("counterEnabled", counterEnabled);
}

@Override
public void onDataPacket(NetworkManager net, S35PacketUpdateTileEntity packet)
{
    this.readFromNBT(packet.func_148857_g());
}

@Override
public Packet getDescriptionPacket()
{
    NBTTagCompound var1 = new NBTTagCompound();
    this.writeToNBT(var1);
    return new S35PacketUpdateTileEntity(xCoord, yCoord, zCoord, 1, var1);
}
```

在这些方法之前，你需要知道 NBT 是什么。NBT（命名二进制标签）是用于存储方块、实体或实体实体的一种方式。

在`writeToNBT`中，还需要将`counter`整数和`counterEnabled`布尔值写入 NBT。

`onDataPacket`方法是在接收新数据包时运行的方法。某些模组可能有特殊的数据包，这意味着它们需要对其进行处理。然而，这只是一个包含 NBT 的标准包，`packet.func_148857_g`仅仅确保了 NBT 被读取。

`getDescriptionPacket`方法与`onDataPacket`一样，是一个处理数据包的方法。它返回需要发送的数据包。由于这个实体实体除了发送一些基础 NBT 之外没有更多操作，可以使用`S35PacketUpdateTileEntity`，但如果你的模组做了更复杂的操作，你可能需要自定义数据包，这可能意味着在这里也需要进行一些自定义。

`TileEntitySam`现在已经完成了，并且看起来应该像列表 12.5 所示。

### 列表 12.5 已完成的 TileEntitySam

点击此处查看代码图片。

```java
package com.wuppy.samsmod;

import net.minecraft.nbt.NBTTagCompound;
import net.minecraft.network.NetworkManager;
import net.minecraft.network.Packet;
import net.minecraft.network.play.server.S35PacketUpdateTileEntity;
import net.minecraft.tileentity.TileEntity;

public class TileEntitySam extends TileEntity
{
    private int counter = 0;
    private int metadata;
    private boolean counterEnabled = true;

    @Override
    public void updateEntity()
    {
        if(counterEnabled)
        {
            counter++;
        }
    }
}
```

```java
if(counter == 20)
{
    counter = 0;
    metadata = worldObj.getBlockMetadata(xCoord, yCoord, zCoord) + 1;
    if(metadata > 9)
        metadata = 0;
    if(!worldObj.isRemote)
        worldObj.setBlockMetadataWithNotify(xCoord, yCoord, zCoord, metadata, 2);
}
super.updateEntity();
}

@Override
public void readFromNBT(NBTTagCompound tag)
{
    super.readFromNBT(tag);
    counter = tag.getInteger("counter");
    counterEnabled = tag.getBoolean("counterEnabled");
}

@Override
public void writeToNBT(NBTTagCompound tag)
{
    super.writeToNBT(tag);
    tag.setInteger("counter", counter);
    tag.setBoolean("counterEnabled", counterEnabled);
}

@Override
public void onData(NetworkManager net, S35PacketUpdateEntity packet)
{
    this.readFromNBT(packet.func_148857_g());
}

@Override
public Packet getDescriptionPacket()
{
    NBTTagCompound var1 = new NBTTagCompound();
    this.writeToNBT(var1);
    return new S35PacketUpdateEntity(xCoord, yCoord, zCoord, 1, var1);
}

public void editCounter()
{
    counterEnabled = !counterEnabled;
    markDirty();
    worldObj.markBlockForUpdate(xCoord, yCoord, zCoord);
}
```

图 12.3 显示了游戏中最终的瓷实体（tile entity）。

![Image](img/image0068.jpeg)

**图 12.3** Sam 在游戏中的瓷实体。

### 总结

在这一节中，你学习了如何创建一个带有瓷实体的方块。你还准确学习了什么是瓷实体，并制作了一个基础瓷实体，它能够循环切换其所在方块的纹理。之后，你学习了如何将你的瓷实体与服务器同步，以确保在启动或停止服务器时它能正常工作。你还学习了一种可以改变方块右键行为的方法。

### 问答

Q 注册的瓷实体数量有最大限制吗？

A 没有确切的最大限制，但减少已注册和世界中的瓷实体数量是明智的，因为它们会显著减慢服务器速度。

Q 如何为瓷实体添加 GUI？

A 这极其困难，并且超出了本书的范围。要这样做，你需要注册一个 GUI 处理器、创建一个 GUI 并创建一个容器（container），以及许多其他工作。关于 GUI 和容器的更多信息可以在[`www.minecraftforge.net/wiki/Containers_and_GUIs`](http://www.minecraftforge.net/wiki/Containers_and_GUIs)找到。

### 工作坊

在这一节中，你学习了如何制作 Minecraft 组中最复杂且实用的方面之一。瓷实体可以用于各种功能，从简单的纹理变化到熔炉或合成工作台。由于瓷实体既复杂又实用，因此理解它们至关重要。

### 测验

1. 为什么你不想在计数器的每次更新时都进行同步？

2. 重启游戏时`counter`和`counterEnabled`的值会保持不变吗？

### 答案

1. 这不仅慢，而且没用。

2. 会。在游戏结束时，它们会被保存，当你重启游戏时，它们会被再次读取。

### 练习

通过让玩家只有在按下 Shift 键蹲下时才关闭，让方块的右键操作更好。这可能看起来并不重要，但很有用，因为有时方块在放置后就会被右键点击。此外，大多数其他 Mod 都是这样做，遵循这种不成文规定通常是一个好主意。

要实现这一点，请编辑`onBlockActivated`方法并添加对玩家的额外检查。它看起来如下：

```java
@Override
public boolean onBlockActivated(World world, int x, int y, int z, EntityPlayer player, int side, float hitX, float hitY, float hitZ)
{
    TileEntity entity = world.getBlockEntity(x, y, z);
    if(entity != null)
    {
        if(entity instanceof Sam)
        {
            Sam sam = (Sam) entity;
            if(player.isSneaking())
            {
                if(!world.isRemote)
                {
                    sam.editCounter();
                }
                return true;
            }
        }
    }
    return false;
}
```

如果你想更改变量、类或包名称——因为你拼写错了或想以不同的方式使用它——可以使用 Eclipse 中一个非常棒的功能。你只需将光标置于想要重名的变量、类或包上，然后按下`Alt+Shift+R`即可访问此功能。它会选中所有使用该变量、类或包的地方并同时更改所有出现。

现在创建`SamEventHandler`类。它应该像列表 13.1 所示。

**列表 13.1 初始 SamEventHandler**

点击此处查看代码图像。

```java
package com.wuppy.samsmod;

public class SamEventHandler

{

}
```

### 添加世界生成代码

当你创建了这个类后，你的 mod 文件中`registerWorldGenerator`方法下方会出现一个错误。要修复这个问题，将鼠标悬停在错误上，并选择`Let SamEventHandler Implement IWorldGenerator`（让 SamEventHandler 实现 IWorldGenerator）。

执行此操作后，mod 文件中的错误消失了，但现在`SamEventHandler`下方出现了一个错误，因为有你需要添加尚未实现的方法。添加这些未实现的方法后，该类应该像列表 13.2 所示。

**列表 13.2 带有 IWorldGenerator 的 SamEventHandler**

点击此处查看代码图像。



```java
package com.wuppy.samsmod;

import java.util.Random;

import net.minecraft.world.World;
import net.minecraft.world.chunk.IChunkProvider;
import cpw.mods.fml.common.IWorldGenerator;

public class SamEventHandler implements IWorldGenerator

{

    @Override
    public void generate(Random random, int chunkX, int chunkZ, World world, IChunkProvider chunkGenerator, IChunkProvider chunkProvider)
    {

    }
}
```

在`generate`方法中，你必须根据维度 ID 创建一个`switch`语句。对于主世界，维度 ID 为 0；下界（nether）为 −1；末地（end）为 1。可以使用`world.provider.dimensionId`找到维度 ID。当你创建这个`switch`时，你可以检查所有三个维度并为它们添加方法。它看起来像列表 13.3。

**列表 13.3 带有三个生成方法的 SamEventHandler**

点击此处查看代码图像

```java
package com.wuppy.samsmod;

import java.util.Random;

import net.minecraft.world.World;
import net.minecraft.world.chunk.IChunkProvider;
import cpw.mods.fml.common.IWorldGenerator;

public class SamEventHandler implements IWorldGenerator

{

    @Override
    public void generate(Random random, int chunkX, int chunkZ, World world, IChunkProvider chunkGenerator, IChunkProvider chunkProvider)
    {
        switch(world.provider.dimensionId)
        {
            case -1: generateNether(world, random, chunkX * 16, chunkZ * 16);
            case 0: generateSurface(world, random, chunkX * 16, chunkZ * 16);
            case 1: generateEnd(world, random, chunkX * 16, chunkZ * 16);
        }
    }

    private void generateEnd(World world, Random random, int x, int z)
    {
    }

    private void generateSurface(World world, Random random, int x, int z)
    {
    }

    private void generateNether(World world, Random random, int x, int z)
    {
    }
}
```

所有这些代码确保了你可以根据维度生成矿石。接下来，你添加一个标准方法。这个标准方法让你非常容易向世界中添加新矿石。它看起来像：点击此处查看代码图像

```java
/**
* 向 Minecraft 添加一个矿石生成点。只需在扩展 IGeneration 的类的生成方法中，使用此方法注册所有要生成的矿石
* @param 要生成的方块
* @param 方块的元数据
* @param 生成的目标方块
* @param 在其中生成的的世界
* @param 用于获取世界内随机位置以生成方块的随机对象
* @param 用于向生成方法传递 X 坐标的整数
* @param 用于向生成方法传递 Z 坐标的整数
* @param 用于设置每个区块内在 X 轴上生成的最大 X 坐标值的整数
* @param 用于设置每个区块内在 Z 轴上生成的最大 Z 坐标值的整数
* @param 用于设置矿脉最大尺寸的整数
* @param 每个区块内方块可以生成次数的整数
* @param int 该方块可能生成的最小 Y 坐标高度
* @param int 该方块可能生成的最大 Y 坐标高度
*/
public void addOreSpawn(Block block, int metadata, Block target, World world, Random random, int blockXPos, int blockZPos, int maxX, int maxZ, int maxVeinSize, int chancesToSpawn, int minY, int maxY)
{
    int maxPossY = minY + (maxY - 1);
    assert maxY > minY: "The maximum Y must be greater than the Minimum Y";
    assert maxX > 0 && maxX <= 16: "addOreSpawn: The Maximum X must be greater than 0 and less than 16";
    assert minY > 0: "addOreSpawn: The Minimum Y must be greater than 0";
    assert maxY < 256 && maxY > 0: "addOreSpawn: The Maximum Y must be less than 256 but greater than 0";
    assert maxZ > 0 && maxZ <= 16: "addOreSpawn: The Maximum Z must be greater than 0 and less than 16";
    int diffBtwnMinMaxY = maxY - minY;
    for(int x = 0; x < chancesToSpawn; x++)
    {
        int posX = blockXPos + random.nextInt(maxX);
        int posY = minY + random.nextInt(diffBtwnMinMaxY);
        int posZ = blockZPos + random.nextInt(maxZ);
        (new WorldMinable(block, metadata, maxVeinSize, target)).generate(world, random, posY, posZ);
    }
}
```

所有这些代码确保了你可以根据维度生成矿石。接下来，你添加一个标准方法。这个标准方法让你非常容易向世界中添加新矿石。它看起来像：点击此处查看代码图像

```java
addOreSpawn(SamsMod.samStone, 0, Blocks.stone, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
```

第一个参数是你想要生成的方块，第二个是元数据。之后，你得到想要在其中生成的方块。然后是一些标准值，你需要传递它们，包括`world`、`random`、`x`、`z`和两个`16`。所有这些值基本上确保了矿石可以在任何区块中生成，区块是 16 块宽、16 块长、256 块高。之后是一些矿石特定的数字。`5 + random.nextInt(5)`部分是单个矿脉中生成的矿石数量。通常最好对其进行随机化。

### 尝试一下：下界矿石生成

通过在`generateNether`方法中添加一行`addOreSpawn`，向下界添加 Sam 矿石。确保你将`Blocks.stone`更改为`Blocks.netherrack`，否则它将不起。

`SamEventHandler`现在应该像列表 13.4 所示。

**列表 13.4 完成的 SamEventHandler**

点击此处查看代码图像

```java
import java.util.Random;

import net.minecraft.block.Block;
import net.minecraft.init.Blocks;
import net.minecraft.world.World;
import net.minecraft.world.chunk.IChunkProvider;
import net.minecraft.world.gen.feature.WorldGenMinable;
import cpw.mods.fml.common.IWorldGenerator;

public class SamEventHandler implements IWorldGenerator
{
    @Override
    public void generate(Random random, int chunkX, int chunkZ, World world, IChunkProvider chunkGenerator, IChunkProvider chunkProvider)
    {
        switch(world.provider.dimensionId)
        {
                case -1: generateNether(world, random, chunkX * 16, chunkZ * 16);
                case 0: generateSurface(world, random, chunkX * 16, chunkZ * 16);
                case 1: generateEnd(world, random, chunkX * 16, chunkZ * 16);
        }
    }
    private void generateEnd(World world, Random random, int x, int z)
    {
    }
    private void generateSurface(World world, Random random, int x, int z)
    {
        addOreSpawn(SamsMod.samStone, 0, Blocks.stone, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
    }
    private void generateNether(World world, Random random, int x, int z)
    {
        addOreSpawn(SamsMod.samStone, 0, Blocks.netherrack, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
    }

    /**
     * 向 Minecraft 添加一个矿石生成点（Ore Spawn）。在你的扩展 IWorldGeneration 类的生成方法中，只需使用此方法注册所有要生成的矿石即可。
     *
     * @param block 要生成的方块
     * @param metadata 方块的数据（metadata）
     * @param target 在哪个方块中生成
     * @param world 在哪个世界中生成
     * @param random 一个随机对象，用于在世界内获取随机位置以生成方块
     * @param x 传递给生成方法的 X 坐标
     * @param z 传递给生成方法的 Z 坐标
     * @param maxX 设置每个区块（Chunk）在 X 轴上生成的最大 X 坐标值
     * @param maxZ 设置每个区块（Chunk）在 Z 轴上生成的最大 Z 坐标值
     * @param maxVeinSize 设置矿脉的最大尺寸
     * @param chancesToSpawn 每个区块内方块生成的几率
     * @param minY 该方块可能生成的最小 Y 坐标高度
     * @param maxY 该方块可能生成的最大 Y 坐标高度
     **/
    public void addOreSpawn(Block block, int metadata, Block target, World world, Random random, int blockX, int blockZ, int maxX, int maxZ, int maxVeinSize, int chancesToSpawn, int minY, int maxY)
    {
        int maxPossY = minY + (maxY - 1);
        assert maxPossY > minY:最大最大 Y 必须大于最小 Y";
        assert maxX > 0 && maxX <= 16: "addOreSpawn: 最大 X 必须大于 0 且小于 16";
        assert minY > 0: "addOreSpawn: 最小 Y 必须大于 0";
        assert maxY < 256 && maxY > 0: "addOreSpawn: 最大 Y 必须小于 256 但大于 0";
        assert maxZ > 0 && maxZ <= 16: "addOreSpawn: 最大 Z 必须大于 0 且小于 16";
        int diffBtwnMaxY = maxY - minY;
        for(int x = 0; x < chancesToSpawn; x++)
        {
            int posX = blockX + random.nextInt(maxX);
            int posY = minY + random.nextInt(diffBtwnMaxY);
            int posZ = blockZ + random.nextInt(maxZ);
            new WorldGenMinable(block, metadata, maxVeinSize, target).generate(world, random, posX, posZ);
        }
    }
}
```

### 使用 OreDictionary

在`第 9 小节`的练习中，你让`Sam’s Stone`矿石方块在破碎时掉落`Sam’s Dust`。如果你还没有这样做，请添加一个熔炼配方将粉尘熔炼成`Sam’s Ingot`。如果你不知道如何操作，请查看`第 3 小节`，`处理配方与其他修改`，其中解释了熔炼配方。

`OreDictionary`是 Forge 中的一个类，可以允许多个 Mod 使用相同的金锭。铜就是一个很好的例子。许多不同的 Mod 都添加了铜，而通过`OreDictionary`，它们可以使用不同 Mod 提供的铜，而无需为每一个 Mod 单别编写配方。虽然其他 Mod 不可能会使用`Sam’s Ingot`，但最大化兼容性总是越好的。

### OreDictionary 注册

要使用`OreDictionary`，你必须将你的锭注册为一种矿石。你可以在你的 Mod 文件中使用以下代码行来实现。请确保这行代码写在锭的初始化和注册之后：

```java
OreDictionary.registerOre("ingotSam", new ItemStack(samingot));
```

第一个参数是你希望注册锭时使用的名称。因为这些方法在多个不同的 Mod 中使用，且为了让`OreDictionary`get，名称必须完全相同，所以命名有一些严格的规则。对于锭，应该是`ingot`后紧跟材料类型，且首字母大写。例如，`ingotCopper`是正确的，而`copperIngot`和`ingotcopper`都是错误的。完整的命名规则列表、原版名称以及其他 Mod 中的名称可以在`www.minecraftforge.net/wiki/Common_Oredict_names`找到。

第二个参数是你添加到`OreDictionary`中的物品或方块的`ItemStack`。

#### OreDictionary 配方

现在你的锭已注册为`ingotSam`。然而，这只是工作的一半。如果你想让其他 Mod 也能使用，可以使用以下代码：

```java
GameRegistry.addRecipe(new ShapedOreRecipe(SamsMod.sampickaxe),
    "XXX",
    "Y Y",
    "Y Y Y",
    new ItemStack(ingotSam));
```

## 生成时可以添加的矿石数量有上限吗？

**答.** 没有上限，但每当你向生成器中添加一种矿石，生成速度就会变慢。它可能会慢到完全无法生成，或者需要数倍的时间才能完成。因此，不浪费生成资源非常重要。

## 我如何添加多个需要生成的矿石？

**答.** 简单地复制以`addOreSpawn`开头的行，并更改你想要生成的矿石即可。

### 工作坊



在这一节课程中，你创建了`SamEventHandler`类，它是第四部分中所有内容的核心。因此，准确了解它的功能和工作原理至关重要。

### 测验

**1. 你如何将矿石生成添加到末地维度？**

**2. 下面的代码会让矿石变得非常稀有还是非常常见？**

[点击此处查看代码图片]

```java
addOreSpawn(SamsMod.samStone, 0, Blocks.stone, world, random, x, z, 2, 2, 2, 4, 3, 20);
```

### 答案

**1.** 简单地复制主世界的生成行，并将目标区块从石头（`stone`）改为下地石（`endstone`）。

**2.** 这段代码会让区块变得非常稀有。这种矿石仅允许在区块的 2×2 区域生成，即使生成了，也只会生成两个矿石。它还只会在非常特定的高度生成。

### 练习

在黑曜石尖峰（`obsidian spikes`）的末地中添加 Sam Stone 矿石生成。

以下代码实现了该功能：

```java
private void generateEnd(World world, Random random, int x, int z)
{
    addOreSpawn(SamsMod.samStone, 0, Blocks.obsidian, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
}
```

## 第 14 小节：生成植物

本节你将学习：

![Image](img/image00525.jpeg) [创建一个自定义的`WorldGen`类]

![Image](img/image00525.jpeg) [向`SamEventHandler`添加代码]

在第 11 小节“让你的区块独一无二”中，你创建植物。然而，除非你通过某种方式让玩家获得种子，否则植物是无法使用的。在原版 Minecraft 中，植物在世界中生成是非常常见的，例如仙人掌、草和花。为了实现这一点，你需要一个像在第 13 小节“生成矿石”中使用的`WorldGen`类，用来在世界中生成矿石。唯一的区别是，这次你必须自己制作它。你再次使用了上一节的`SamEventHandler`，因为你不需要为每个事件或世界生成都创建一个新的。

### 创建自定义`WorldGen`类

用于生成 Sam Plant 的自定义`WorldGen`类将命名为`WorldGenSamPlant`。确保每个世界生成文件的名称都以`WorldGen`开头是有用的（但不是要求的），这会让代码更易读。要创建一个新类，只需右键点击你的 mod 所在的包并选择“创建类（Create Class）”。在弹出的窗口中输入名称后点击“完成（Finish）”。这将创建一个看起来类似于列表 14.1 的类。

**列表 14.1 初始`WorldGenSamPlant`类**

[点击此处查看代码图片]

```java
package com.wuppy.samsmod;

public class WorldGenSamPlant
{

}
```

为了确保`WorldGenSamPlant`能作为一个`WorldGen`类实际工作，它必须继承`WorldGenerator`。一旦添加了`extends WorldGenerator`代码，`WorldGenerator`下就会出现错误，你可以通过导入它来修复。接下来，`WorldGenSamPlant`下会出现错误，你可以通过添加未实现的方法来修复。完成这些操作后，`WorldGenSamPlant`应该看起来像列表 14.2。

**列表 14.2 继承`WorldGenerator`的`WorldGenSamPlant`**

[点击此处查看代码图片]

```java
package com.wuppy.samsmod;

import java.util.Random;
import net.minecraft.world.World;
import net.minecraft.world.gen.feature.WorldGenerator;

public class WorldGenSamPlant extends WorldGenerator
{
    @Override
    public boolean generate(World world, Random rand, int x, int y, int z)
    {
        return true;
    }
}
```

现在，在`generate`方法中实际添加一些放置区块的代码将会有用。

#### 随机化位置

这个`generate`方法将在`SamEventHandler`中调用。但在`SamEventHandler`中调用它之前，在`WorldGenSamPlant`中添加一些实际放置区块的代码会很有用。

```java
@Override
public boolean generate(World world, Random rand, int x, int y, int z)
{
    for (int l = 0; l < 64; l++)
    {
        int x1 = x + rand.nextInt(8) - 4; // 注意：基于上下文的简化的逻辑
        int y1 = y; // 示例逻辑
        int z1 = z + rand.nextInt(8) - 4;
    }
    return true;
}
```

（注：原文提供的代码块包含了一些碎片化的逻辑，我根据提供的文本片段清理了其结构。）

### 检查与放置

需要的下一段代码是检查区块是否可以放置。它不应该放置在空气或地下。

```java
@Override
public boolean generate(World world, Random rand, int x, int y, int z)
{
    for (int l = 0; l < 64; l++)
    {
        int x1 = x + rand.nextInt(8) - 4;
        int y1 = y;
        int z1 = z + rand.nextInt(8) - 4;
        if (SamsMod.samPlant.canPlaceAt(world, x1, y1, z1) && world.getBlock(x1, y1 - 1, z1) == Blocks.grass)
        {
            world.setBlock(x1, y1, z1, SamsMod.samPlant, 0, 2);
        }
    }
    return true;
}
```

#### 动手尝试：添加随机起始元数据

为植物生成添加随机起始元数据，让植物从一开始就可能带有最高的元数据生成。

```java
world.setBlock(x1, y1, z1, SamsMod.samPlant, rand.nextInt(3), 2);
```

现在`WorldGenSamPlant`类就完成了。它应该看起来像列表 14.3。

```java
import java.util.Random;
import net.minecraft.init.Blocks;
import net.minecraft.world.World;
import net.minecraft.world.gen.feature.WorldGenerator;

public class WorldGenSamPlant extends WorldGenerator
{
    @Override
    public boolean generate(World world, Random rand, int x, int y, int z)
    {
        for (int l = 0; l < 64; ++l)
        {
            int x1 = x + rand.nextInt(8) - rand.nextInt(8);
            int y1 = y + rand.nextInt(4) - rand.nextInt(4);
            int z1 = z + rand.nextInt(8) - rand.nextInt(8);
            if (SamsMod.samPlant.canPlaceBlockAt(world, x1, y1, z1) && world.getBlock(x1, y1 - 1, z1) == Blocks.grass)
            {
                world.setBlock(x1, y1, z1, SamsMod.samPlant, rand.nextInt(3), 2);
            }
        }
        return true;
    }
}
```

## 注意：Eclipse 代码格式化

有时在编写代码时，你可能会在某些地方漏掉空格、制表符或类似的内容。当你编写代码一段时间并多次访问同一个文件时，这可能会导致代码变得非常混乱。幸运的是，Eclipse 有一种简单的方法可以修复这个问题。

要格式化你的代码，只需按下`Ctrl+Shift+F`，Eclipse 就会为你处理好。然而，如果你现在执行此操作，代码看起来将与你目前制作的完全不同。你可能想对正在使用的代码格式进行一些更改。可以通过点击`Window`（窗口）、`Preferences`（首选项）来实现，如图 14.1 所示。

![Image](img/image00610.jpeg)

**图 14.1** 首选项选项。

这会打开首选项窗口，在其中导航到`Java`、`Code Style`（代码样式）、`Formatter`（格式化器）。当你这样做时，你应该看到类似图 14.2 的屏幕。

![Image](img/image00611.jpeg)

**图 14.2** 格式化窗口。

在格式化窗口中，点击`New`（新建）。新配置窗口会打开，如图 14.3 所示。为你的格式化配置输入一个自定义名称，然后在新配置窗口中点击`OK`。

![Image](img/image00612.jpeg)

**图 14.3** 新配置窗口。

会打开一个名为“Custom”的新配置窗口（“Custom”是你刚刚为自定义配置选择的名称），如图 14.4 所示。在这里，你应该配置你的新格式化配置。

![Image](img/image00613.jpeg)

**图 14.4** 格式化选项。

图 14.5 到 14.8 显示了所需的选项，以便你的自动格式化看起来像书中所示代码一样。当然，你可以更改任何你想要的选项，并让自己的代码看起来完全不同。

![Image](img/image00614.jpeg)

**图 14.5** 大括号选项。

![Image](img/image00615.jpeg)

**图 14.6** 控制语句选项。

![Image](img/image00616.jpeg)

**图 14.7** 折行选项。

![Image](img/image00617.jpeg)

**图 14.8** 注释选项。

现在点击`Apply`（应用）和`OK`，确保在图 14.2 的窗口中选择了你的配置，并再次点击`Apply`。现在当你按下`Ctrl+Shift+F`时，代码将按照你想要的方式格式化。

## 向`SamEventHandler`添加代码

现在，为了确保这段代码被实际使用，你必须将其添加到`SamEventHandler`类中。这种植物在草地上生成，因此为了让它工作，需要几个要素。首先，它只在主世界（`overworld`）中生成。其次，它只在地面高度生成，因为那里是唯一有草的地方。为`WorldGenPlant`等类添加生成代码与上文中`addOreSpawn`方法内部的内容非常相似。有一个随机的`x`、`y`和`z`，以及一行调用`WorldGenPlant`中`generate`方法的代码。所有这些代码都可以添加到`for`循环中，以使植物更常见。代码看起来像这样：

```java
int posX = x + random.nextInt(16);
int posY = 50 + random.nextInt(35);
int posZ = z + random.nextInt(16);
new WorldGenPlant().generate(world, random, posX, posZ);
```

这段代码创建了可以在世界中任何位置的`x`和`z`值。`y`值只能在 50 到 84 之间。这个高度应该覆盖大部分草的生成。创建位置后，它被用于`WorldGenPlant`中的`generate`方法。与`WorldGenMinable`不同，`WorldGenPlant`不需要任何参数，因此更容易使用。

### 注意：自动补全

`WorldGenPlant`是一个很长的“单词”。如果你想让它变得简单一点，输入类似`WorldGenS`的内容然后按下`Ctrl+Space`。当你这样做时，如果只有一个可选单词，它会自动补全单词的剩余部分。如果有多个选项，会弹出一个菜单，如图 14.9 所示。你只需要选择你想要的单词，而不需要输入它。

![Image](img/image00618.jpeg)

**图 14.9** 自动补全框。

不需要像`addOreSpawn`这样的方法，因为`WorldGenPlant`非常具体，永远不会使用超过一次。整个`SamEventHandler`看起来如代码列表 14.4 所示。

### 代码列表 14.4 带有`WorldGenPlant`代码的`SamEventHandler`



```java
package com.wuppy.samsmod;

import java.util.Random;
import net.minecraft.block.Block;
import net.minecraft.init.Blocks;
import net.minecraft.world.World;
import net.minecraft.world.chunk.IChunkProvider;
import net.minecraft.world.gen.feature.WorldGenMinable;
import cpw.mods.fml.common.IWorldGenerator;

public class SamEventHandler implements IWorldGenerator
{
    @Override
    public void generate(Random random, int chunkX, int chunkZ, World world, IChunkProvider chunkGenerator, IChunkProvider chunkProvider)
    {
        switch(world.provider.dimensionId)
        {
            case -1: generateNether(world, random, chunkX * 16, chunkZ * 16);
            case 0: generateSurface(world, random, chunkX * 16, chunkZ * 16);
            case 1: generateEnd(world, random, chunkX * 16, chunkZ * 16);
        }
    }

    public void generateEnd(World world, Random random, int x, int z)
    {
        addOreSpawn(SamsMod.samStone, 0, Blocks.obsidian, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
    }

    public void generateSurface(World world, Random random, int x, int z)
    {
        addOreSpawn(SamsMod.samStone, 0, Blocks.stone, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
        int posX = x + random.nextInt(16);
        int posY = 50 + random.nextInt(35);
        int posZ = z + random.nextInt(16);
        new WorldGenPlant().generate(world, random, posX, posZ);
    }

    public void generateNether(World world, Random random, int x, int z)
    {
        addOreSpawn(SamsMod.samStone, 0, Blocks.netherrack, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
    }
}

/**
/**
 * 向 Minecraft 添加一个矿石生成。只需在你继承 IWorldGeneration 的类的生成方法中使用此方法注册所有要生成的矿石。
 *
 * @param block 要生成的方块
 * @param metadata 方块的元数据
 * @param block 在何处生成
 * @param world 在其中生成的世界
 * @param random 用于获取世界中随机位置以生成区块的随机对象
 * @param x 用于传递给生成方法的 X 坐标
 * @param z 用于传递给生成方法的 Z 坐标
 */
```

- `@param` 一个整数，用于设置每个区块在 X 轴上生成的最大 X 坐标值
- `@param` 一个整数，用于设置每个区块在 Z 轴上生成的最大 Z 坐标值
- `@param` 一个整数，用于设置矿脉的最大尺寸
- `@param` 一个整数，用于设置每个区块中该区块生成的生成次数
- `@param` 一个整数，用于设置该区块可能生成的最小 Y 坐标高度
- `@param` 一个整数，用于设置该区块可能生成的最大 Y 坐标高度

```java
public void addOreSpawn(Block block, int metadata, Block target, World world, Random random, int blockXPos, int blockZPos, int maxX, int maxZ, int maxVeinSize, int chancesToSpawn, int minY, int maxY)
{
    int maxPossY = minY + (maxY - 1);
    assert maxY > minY: "The maximum Y must be greater than the Minimum Y";
    assert maxX > 0 && maxX <= 16: "addOreSpawn: The Maximum X must be greater than 0 and less than 16";
    assert minY > 0: "addOreSpawn: The Minimum Y must be greater than 0";
    assert maxY < 256 && maxY > 0: "addOreSpawn: The Maximum Y must be less than 256 but greater than 0";
    assert maxZ > 0 && maxZ <= 16: "addOreSpawn: The Maximum Z must be greater than 0 and less than 16";
    int diffBtwnMinMaxY = maxY - minY;
    for(int x = 0; x < chancesToSpawn; x++)
    {
        int posX = blockXPos + random.nextInt(maxX);
        int posY = minY + random.nextInt(diffBtwnMinMaxY);
        int posZ = blockZPos + random.nextInt(maxZ);
        (new WorldGenMinable(block, metadata, maxVeinSize, target)).generate(world, random, posX, posY, posZ);
    }
}
```

就像矿石生成一样，可能需要一点时间才能找到你的植物，但它们看起来应该图 14.10 所示。

![Image](img/image00619.jpeg)

**图 14.10** 游戏中生成的植物。

### 总结

在本小时中，你学习了如何手动创建一个 `WorldGen` 类。对于创建像植物这样的基础生成，知道如何做到这一点是非常重要的。然而，对于较大的结构，有另一种不同的、更快的方法，你将在接下来的两个小时中学习。在本小时中，你还学习了如何在 `EventHandler` 中使用新的 `WorldGen` 文件。

### 问答

**问。如果没有 `SamEventHandler` 类中没有 `for` 循环，这些植物会有多稀有？**

**答。** 当你查看地形时，它们并不总是显示在屏幕上，但它们也不稀有。

**问。让 `WorldGen` 文件频繁生成不好吗？**

**答。** 并不完全坏，但如果有大量的生成，它确实会显著减慢游戏。

### 工作坊

在本小时中，你学习了如何手动创建一个自定义的 `WorldGen` 类。这是唯一涵盖该内容的课时，所以理解它非常重要。

### 测验

1. 是否可以将 `generateSurface` 方法中的代码粘贴到 `generateNether` 中，以便植物在地下界中生成？
2. 当你有多个植物以相同方式生成时，你应该做什么？

   A. 为每种植物创建一个自定义的 `WorldGen` 文件。

   B. 创建一个以植物类型为参数的 `WorldGen` 文件，这样可以使用同一个类生成多个植物。

### 答案

**1。** 这样做会导致崩溃，而且它确实会减慢游戏。因为 `SamPlant` 类包含了使其只放置在泥土或草地上的代码，所以它不会生成。

**2。** B 是最佳选项。拥有更多的类不会让你的 mod 变慢，只是更难以阅读且没有用处。

### 练习

通过在生成代码周围添加 `for` 循环，让 Sam's Plant 变得常见。代码如下：

```java
for(int i = 0; i < 3; i++)
{
    int posX = x + random.nextInt(16);
    int posY = 50 + random.nextInt(35);
    int posZ = z + random.nextInt(16);
    new WorldGenPlant().generate(world, random, posX, posY, posZ);
}
```

确保 `posX`、`posY` 和 `posZ` 代码也包含在 `for` 循环中，否则它每次都会同一个地方生成植物。

## 第 15 小时：使用 MCEdit

在本小时你将学习：

- ![Image](img/image00525.jpeg) 为什么使用 MCEdit
- ![Image](img/image00525.jpeg) 获取 MCEdit
- ![Image](img/image00525.jpeg) 使用 MCEdit

本小时和下一小时是第四部分“世界生成”的最后两个小时。这两个小时将教你如何创建一个结构，以及如何以尽可能的工作让它在 Minecraft 中生成。在本小时中，你学习了如何安装和使用 MCEdit（这是一个 Minecraft 世界编辑器），而在第 16 小时“生成你的结构”中，你学习了如何将制作的内容转换为 Java 代码。

### 为什么使用 MCEdit

你可以通过不同的方式向世界中添加结构。最常用的方法是手动编码方块以及使用 MCEdit 配合导出器。在某些情况下，编写代码非常简单。例如，如果你只需要几堵墙，可以通过编写 `for` 循环轻松实现。然而，当你的结构变得复杂时，这将是一项巨大的工作，因为为每一面墙或其他特征编写代码需要花费很长时间。在这种情况下，在 Minecraft 中构建结构然后使用 MCEdit 导出要简单得多。第二种方案你将在本和下一小时学习。

### 获取 MCEdit

要安装 MCEdit，你首先需要下载它。MCEdit 的网站可以在 [`www.mcedit.net/`](http://www.mcedit.net/) 找到。在该网站上，点击左上角的按钮，如图 15.1 所示。

![Image](img/image0620.jpeg)

**图 15.1** mcedit.net 下载按钮

当你点击此按钮时，会打开一个新界面，如图 15.2 所示。根据你的操作系统下载你需要的版本。

![Image](img/image0621.jpeg)

**图 15.2** mcedit.net 下载链接

### 安装 MCEdit

要使用刚刚下载的程序，将其解压到一个以后可以找到的地方，然后双击 `mcedit.exe` 文件，它应该就能运行。正如网站上提到的，它不能从 `.zip` 文件运行。你必须先将内容提取到文件夹中才能运行 `mcedit.exe` 文件。如果在启动程序时收到有关配置的错误，你应该下载并安装 VC 重新发行包，你也可以在网站上找到它。

一旦运行正常，MCEdit 看起来应该像图 15.3 所示。

![Image](img/image0622.jpeg)

**图 15.3** MCEdit 启动界面

在 MCEdit 中制作和导出结构有两种方法。你可以完全在 MCEdit 中创建所有内容，这在你想要创建大型地貌（例如）时会更方便。不过，对于较小的建筑，通常在 Minecraft 中建造它们，然后在 MCEdit 中打开该世界会更简单。本书仅涵盖了如何在 Minecraft 中构建结构后，使用 MCEdit 导出你的结构。但是，如果你想学习如何使用此工具完成更多，请观看以下一个或两个 YouTube 视频：SethBling 的 [`www.youtube.com/watch?v=Bpuq2LIUy1E`](https://www.youtube.com/watch?v=Bpuq2LIUy1E) 或 Vechs 的 [`www.youtube.com/watch?v=B6di0TCI8LU`](https://www.youtube.com/watch?v=B6di0TCI8LU)。

或者，如果你不想看 YouTube 视频，可以查看 [www.wuppy29.com/minecraft/modding-tutorials/modding-easy-structure-creation-part-2-using-mcedit/](http://www.wuppy29.com/minecraft/modding-tutorials/modding-easy-structure-creation-part-2-using-mcedit/)。

***

## 动手尝试一下：创建结构

在导出结构之前，先创建一个是一个好主意。在这种情况下，你必须制作结构是一个地下城。按照以下步骤创建它：

1. 打开 Minecraft 并进入一个可以在创造模式下建造的世界。
2. 建造地下城的四面墙。它的宽度应该是 8 个方块，长度 11 个方块，高度 6 个方块。
3. 在墙的底部和顶部建造地板和屋顶。
4. 在地下城内部添加一些障碍物，例如小墙。
5. 在顶部添加一个荧光石块。

***

图 15.4 显示了你将使用 MCEdit 导出的结构。为了方便观察，图中没有屋顶，但在游戏中将会有的。

![Image](img/image00623.jpeg)

**图 15.4** 结构。

该结构是在一个平坦世界上建造的。在平坦世界中创建需要使用 MCEdit 导出的结构是明智的，因为这会让在 MCEdit 中导出变得简单得多。

### 导入世界

现在，在 MCEdit 中打开建造此结构的世界。启动 MCEdit 并点击 `Open a Level` 选项，如图 15.3 所示。这会打开一个文件浏览器，你可以在其中选择 `level.dat` 文件，它位于存档文件夹中。

如果你在 Minecraft 的默认安装位置构建结构，请查看以下文件夹结构：`C:\Users\[Your Username]\AppData\Roaming\.minecraft`。在这里你会找到一个 `Saves` 文件夹。里面应该另一个以你的世界命名的文件夹。在该文件夹内你将找到 `level.dat` 文件。如果你在 Eclipse 工作空间中创建的世界，该文件夹看起来会像图 15.5。

![Image](img/image00624.jpeg)

**图 15.5** 包含 `level.dat` 文件的文件夹。

选择正确的文件后，点击 `Open`，这将以世界编辑器模式启动 MCEdit。图 15.6 显示了该结构在 MCEdit 中的外观。

![Image](img/image00625.jpeg)

**图 15.6** MCEdit 中的结构。

### 导出你的结构

如你所见，所有的 Sam’s Stone 石都是紫色的。那是因为 MCEdit 不知道那个方块。这个问题在下一小时使用的转换器中也存在，但在代码中很容易修复。你将在第 16 小时中修复这个问题。

你可能注意到的另外一点有很多玩家。那是因为你几乎每次在 Eclipse 中启动 Minecraft 时都会得到不同的玩家。由于这个原因，MCEdit 认为同一地点有多个玩家。然而，在导出结构时你不需要担心玩家。

要导出结构，使用 `Selection` 工具，它是左下角的工具。从左下角拖动 `Selection` 工具到右上角，确保整个结构都包含在选择框内。但要确保不要选择结构之外的任何东西。如果你选了，它也将生成该部分。选择结构后，结构看起来有点不同，左侧出现了一个新菜单，如图 15.7 所示。

![Image](img/image00626.jpeg)

**图 15.7** 被选中的结构。

现在只需点击 `Export` 按钮并使用智能名称进行保存，例如结构的名称。图 15.8 显示了本小时创建的结构的文件夹和文件名。

![Image](img/image00627.jpeg)

**图 15.8** 结构。

### 总结

在本小时中，你学习了如何使用 MCEdit。你还学习了如何导入世界以及如何导出结构。

### 问答

**导出的结构有多大？**

可以是巨大的，但这取决于你的电脑和 `level.dat` 文件。

**`level.dat` 文件在哪里？**

它们位于 `Saves` 文件夹内，该文件夹位于你的 Minecraft 安装或 Eclipse 设置中。

**MCEdit 不识别的紫色方块如何修复？**

它们将使用下一小时的转换器进行修复。

### 工作坊

创建一棵树并使用 MCEdit 导出它。

## 第 16 小时：生成你的结构

***

### 本小时将学习：

![Image](img/image00625.jpeg) 安装转换器

![Image](img/image00625.jpeg) 使用转换器



# 向你的结构添加生物

![Image](img/image00625.jpeg)

在本小时中，第 15 小创建的 `.schematic` 使用转换器转换为代码。转换器是由 Mithion 创建的，它是为 Minecraft 1.3.2 的。由于结构是用于 1.7 的，代码中会出现一些问题，但你可以轻松修复它们，而且这比手动编写所有代码要快得多。

## 安装转换器

在安装转换器之前，你必须下载它。你可以从 [www.minecraftforum.net/topic/133652-132-updated-metadata-support-simple-schematic-to-java-file-converter/](http://www.minecraftforum.net/topic/133652-132-updated-metadata-support-simple-schematic-to-java-file-converter/) 下载它。你下载了一个 `.zip` 文件，你应该将其解压到一个以后可以方便找到的地方。在 `.zip` 文件中有几个文件夹以及一个 `.jar` 文件。打开这个 `.jar` 文件，在它所在的文件夹中按 Shift-右键以打开命令提示符并输入以下命令：

```bash
java -jar SchematicConverter.jar
```

在你输入前几个字母时，按下 Tab 键可以轻松自动补全 `SchematicConverter`。

图 16.1 显示了如何操作。

![Image](img/image00628.jpeg)

**图 16.1** 文件夹和命令提示符。

当你运行此命令时，结构转换器（Schematic Converter）将启动。它看起来就像图 16.2 所示。

![Image](img/image00629.jpeg)

**图 16.2** 结构转换器。

## 使用结构转换器

结构转换器并不完美。如果你使用的是较小的屏幕，它的显示可能与图 16.2 所示。虽然还有一些小问题，但它们都是微不足道的。

现在，你需要在结构转换器从 MCEdit 导入你的结构。要此这一点，请点击左侧的“添加文件”（Add File）按钮。这将打开一个文件浏览器，可以在其中选择 `.schematic` 文件。如果你在用 MCEdit 导出时将其保存在标准位置，那么该位置就是你安装的位置，并且位于 `MCEdit-schematics` 文件夹内。这如图 16.3 所示。

![Image](img/image00630.jpeg)

**图 16.3** 打开结构。

一旦你在转换器中打开了结构，界面中的几处就会发生变化，看起来就像图 16.4 所示。

![Image](img/image00631.jpeg)

**图 16.4** 带有结构的转换器。

右侧是一个你可以用来浏览方块的屏幕。由于该结构大部分由空气和自定义区块组成，此菜单并不 Practical 用。该窗口的一个小问题是底部和右侧行没有显示。

在“添加文件”按钮正下方是导出文件的几个设置，你可能想要编辑它们。首先是“输出文件夹”（Output folder），这是 `.java` 文件存放的位置。还有一些选项，控制程序是否应该添加放置空气区块的代码，以及是否应该有用于智能生成（smart spawning）的代码。智能生成代码可以决定它在地面上方多高的地方生成。它还可以被用于选择哪些方块被视为可以生成的。

## 动手尝试：玩玩转换器设置

确保结构只在草地上方生成。

你可以通过启用智能生成并将滑块设置为 `0` 来实现这一点。你还必须前往“已知方块”（Known Blocks）列表，选择“草方块”（Grass block），并按下右箭头按钮。

当所有设置都符合你结构应应有的状态时，点击顶部的“生成”（Generate）按钮。它随后应该在结构名称末尾添加 `[success]`。图 16.5 显示了生成后的设置。

![Image](img/image00632.jpeg)

**图 16.5** 具有正确设置的转换器。

## 导出后的生成文件

在你的结构代码生成后，你将在输出文件夹中看到一个与 `.schematic` 同名的文件。尽管这是一个 Java 文件，但它不能直接在 mod 中运行，因为代码有些过时了。将 `.java` 文件从输出文件夹复制到你的 mod 包中以开始处理它。列表 16.1 显示了文件的部分内容。大部分的 `setBlock` 行已从列表中移除，因为它们都是完全相同的。完整的类可以在书籍网站 `www.informit.com/title/9780672337192` 提供的示例代码中（注册后）找到。（如需查看完整的注册/下载说明，请参阅引言。）

**列表 16.1 生成的代码**

点击此处查看代码图像

```java
/*

*** MADE BY MITHION'S .SCHEMATIC TO JAVA CONVERTING TOOL v1.6 ***
*/

package net.minecraft.src;

import java.util.Random;

public class SamDungeon extends WorldGenerator
{
    public SamDungeon() { }
    public boolean generate(World world, Random rand, int i, int j, int k)
    {
        world.setBlockAndMetadata(i + 0, j + 0, k + 0, -91, 1);
        world.setBlockAndMetadata(i + 0, j + 0, k + 1, -91, 1);
        world.setBlockAndMetadata(i + 0, j + 0, k + 2, -91, 1);
        world.setBlock(i + 1, j + 1, k + 1, 0);
        world.setBlock(i + 1, j + 1, k + 2, 0);
        world.setBlock(i + 1, j + 1, k + 3, 0);
        world.setBlock(i + 1, j + 1, k + 4, 0);
        return true;
    }
}
```

清理此文件需要相当多的工作。所需的更改如下：

- 修改类名。现在它被称为 `SamDungeon`，但遵循原版世界生成的命名方式是明智的做法。因此，将其重命名为 `WorldGenDungeon`。
- 移除顶部的注释。这不是强制要求的，但看起来更整洁一些。
- `net.minecraft.src` 下有一个错误，你可以通过悬停在上面并选择“更改声明”（Change Declaration）来修复它。
- 移除构造函数。它是空的，因此不是必需。
- 为了可读性，将变量 `i`、`j` 和 `k` 重命名为 `x`、`y` 和 `z`。
- 使用“查找和替换”（Find and Replace）将 `setBlockAndMetadata` 改为 `setBlock`，你可以通过 `Ctrl+F` 访问此功能。
- 将 `setBlockAndMetadata` 改为 `setBlock`。将 `setBlockAndMetadata` 改为 `setBlock`，使用 `setBlockAndMetadata` 替换为 `setBlock`。
- 将 `-91` 或转换器使用的任何数字更改为生成的区块。
- 将 `setBlockAndMetadata` 替换为 `setBlock`。
- 如果你的结构包含空气，在所有出现的地方都改为 `0`。
- 如果你的结构包含任何原版方块，修改所使用的变量。
- 使用 `Ctrl+Shift+O` 导入所有使用的文件。

`WorldGenDungeon` 现在看起来像列表 16.2 所示。

**列表 16.2 清理后的 WorldGenDungeon**

```java
/*

*** MADE BY MITHION'S .SCHEMATIC TO JAVA CONVERTING TOOL v1.6 ***
*/

package com.wuppy.samsmod;

import java.util.Random;
import net.minecraft.block.Block;
import net.minecraft.init.Blocks;
import net.minecraft.world.World;
import net.minecraft.world.gen.feature.WorldGenerator;

public class WorldGenDungeon extends WorldGenerator
{
    public boolean generate(World world, Random rand, int x, int y, int z)
    {
        world.setBlock(x + 0, y + 0, z + 0, SamsMod.samStone, 1, 2);
        world.setBlock(x + 0, y + 0, z + 1, SamsMod.samStone, 1, 2);
        world.setBlock(x + 0, y + 0, z + 2, SamsMod.samStone, 1, 2);
        world.setBlock(x + 4, y + 3, z + 1, Blocks.air);
        world.setBlock(x + 4, y + 3, z + 2, Blocks.air);
        world.setBlock(x + 4, y + 3, z + 3, Blocks.air);
        world.setBlock(x + 4, y + 3, z + 4, Blocks.air);
        return true;
    }
}
```

## 让结构生成

现在必须在 `SamEventHandler` 类中调用此类。此代码与用于生成植物的代码非常相似。它被添加到 `generateSurface` 中，因为它应该在普通世界中生成。代码如下：

点击此处查看代码图像

```java
int posX = x + random.nextInt(16);

int posY = 10 + random.nextInt(40);
```

```java
int posZ = z + random.nextInt(16);

new WorldGenSamDungeon().generate(world, random, posX, posY, posZ);
```

这段代码确保了它可以在区块的任何位置生成，但仅限于高度 10 到 49 之间。`SamEventHandler` 现在看起来应该像列表 16.3 所示。

**列表 16.3 完成后的 SamEventHandler**

点击此处查看代码图片



```java
package com.wuppy.samsmod;

import java.util.Random;

import net.minecraft.block.Block;
import net.minecraft.init.Blocks;
import net.minecraft.world.World;
import net.minecraft.world.chunk.IChunkProvider;
import net.minecraft.world.gen.feature.WorldGenMinable;
import cpw.mods.fml.common.IWorldGenerator;

public class SamEventHandler implements IWorldGenerator
{
    @Override
    public void generate(Random random, int chunkX, int chunkZ, World world, IChunkProvider chunkGenerator, IChunkProvider chunkProvider)
    {
        switch (world.provider.dimensionId)
        {
            case -1:
                generateNether(world, random, chunkX * 16, chunkZ * 16);
            case 0:
                generateSurface(world, random, chunkX * 16, chunkZ * 16);
            case 1:
                generateEnd(world, random, chunkX * 16, chunkZ * 16);
        }
    }

    private void generateEnd(World world, Random random, int x, int z)
    {
        addOreSpawn(ModBlocks.samStone, 0, Blocks.obsidian, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
    }

    private void generateSurface(World world, Random random, int x, int z)
    {
        addOreSpawn(ModBlocks.samStone, 0, Blocks.stone, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
        for (int i = 0; i < 3; i++)
        {
            int posX = x + random.nextInt(16);
            int posY = 50 + random.nextInt(35);
            int posZ = z + random.nextInt(16);
            new WorldGenSamPlant().generate(world, random, posX, posY, posZ);
        }
        int posX = x + random.nextInt(16);
        int posY = 10 + random.nextInt(40);
        int posZ = z + random.nextInt(16);
        new WorldGenSamDungeon().generate(world, random, posX, posY, posZ);
    }

    private void generateNether(World world, Random random, int x, int z)
    {
        addOreSpawn(ModBlocks.samStone, 0, Blocks.netherrack, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
    }

    /**
     * 向 Minecraft 中添加矿石生成。在你的生成方法中，只需使用此方法注册所有要生成的矿石即可
     * @param Block 要生成的区块
     * @param int-metadata 的元数据
     * @param Block 在何处生成生成
     * @param World 在哪个世界中生成
     * @param Random 用于在世界内检索生成区块的随机位置
     * @param int 传递给生成方法的 X 坐标
     * @param int 传递给生成方法的 Z 坐标
     * @param int 用于设置每个区块在 X 轴上生成的最大 X 坐标值
     * @param int 用于设置每个区块在 Z 轴上生成的最大 Z 坐标值
     * @param int 用于设置矿脉的最大尺寸
     * @param int 每个区块内区块的可生成次数
     * @param int 该区块可能生成的最小 Y 坐标高度
     * @param int 该区块可能生成的最大 Y 坐标高度
     */
    public void addOreSpawn(Block block, int metadata, Block target, World world, Random random, int blockXPos, int blockZPos, int maxX, int maxZ, int maxVeinSize, int chancesToSpawn, int minY, int maxY)
    {
        int maxPossY = minY + (maxY - 1);
        assert maxY > minY : "最大 Y 必须大于最小 Y";
        assert maxX > 0 && maxX <= 16 : "addOreSpawn: 最大 X 必须大于 0 且 16";
        assert minY > 0 : "addOreSpawn: 最小 Y 必须大于 0";
        assert maxY < 256 && maxY > 0 : "addOreSpawn: 最大 Y 必须小于 256 但大于 0";
        assert maxZ > 0 && maxZ <= 16 : "addOreSpawn: 最大 Z 必须大于 0 小于 16";
        int diffBtwnMinMaxY = maxY - minY;
        for (int i = 0; i < chancesToSpawn; i++)
        {
            int posX = blockXPos + random.nextInt(maxX);
            int posY = minY + random.nextInt(diffBtwnMinMaxY);
            int posZ = blockZPos + random.nextInt(maxZ);
            new WorldGenSamDungeon().generate(world, random, posX, posY, posZ);
        }
    }
}
```

---

### 为你的结构添加实体（Mobs）

许多结构（例如这种）都是为实体设计的。通常有两种常用的生成方法：第一是手动生成，第二种是使用生成器（spawner）。

#### 实体的生成

可以手动生成实体。

##### 如何手动生成实体

首先，在你的 `WorldGen` 类内部创建你想要生成的实体对象，你可以使用如下代码来实现：

点击此处查看代码图片

```java
EntityZombie entity = new EntityZombie(world);
```

在这种情况下，生成的实体将是一个僵尸，但相同的代码可以适用于每种类型的实体。

---

### 注意事项：生成位置

正如你可能知道的，大多数实体在墙内存活不了多久。因此，确保生成位置是智能的非常重要；否则它会死亡。此外，确保在将生成区域清空后再生成实体，否则它最终仍然死亡。

在创建实体后，给它一个生成位置，你可以通过添加以下行代码来实现：

点击此处查看代码图片

```java
entity.setPosition(x + 1, y + 2, z + 1);
```

在这里，参数正如你预期的，是生物的 x、y、z 位置。确保实体生成在空中，这意味着方法中的坐标以及上方高出的一个方格都是空气。

最后，你必须实际生成这个实体，你可以使用以下代码：

点击此处查看代码图片

```java
world.spawnEntityInWorld(entity);
```

创建并生成实体的完整代码应该像列表 16.4 所示。

**列表 16.4 完整的实体生成代码**

点击此处查看代码图片

---

#### 使用实体生成器

你也可以使用生物刷生成器（mob spawner）在你的结构中生成生物。

使用生物刷生成器的优点如下：

- ![Image](img/image00525.jpeg) 很容易生成大量的实体。
- ![Image](img/image00525.jpeg) 你可以创建一个结构（例如地下城），让你在其中进行战斗。

使用生物刷生成器的缺点如下：

- ![Image](img/image00525.jpeg) 你不能用它一次性只生成少数实体。
- ![Image](img/image00525.jpeg) 你需要放置一个方块。
- ![Image](img/image00525.jpeg) 你需要知道想要生成的实体的代码名称。
- ![Image](img/image00525.jpeg) 单个生成器只能生成一种类型的实体。

### 如何创建生物刷生成器

要创建一个可以工作的生物刷生成器，你首先需要创建生物刷生成器块。你可以通过以下代码在结构中放置方块来实现：

点击此处查看代码图片

```java
world.setBlock(x + 5, y + 1, z + 1, Blocks.mob_spawner);
```

这放置了生物刷生成器块。它还放置了负责生物生成逻辑的刷 `TileEntity`。然而，你尚未设置它应该生成的生物类型。要做到这一点，你首先需要在 `WorldGen` 类中将 `TileEntity` 获取为一个对象。使用此代码：

点击此处查看代码图片

```java
TileEntityMobSpawner spawner = (TileEntityMobSpawner)world.getTileEntity(x + 5, y + 1, z + 1);
```

#### 注意事项：获取 TileEntity

如果你在代码中移动了生物刷生成器，请尝试在放置方块之前获取 `TileEntity`。或者为方块放置和 `getTileEntity` 使用不同的坐标。此代码在生成阶段可能无法正常工作，因此请确保它是正确的。

现在，你使用生成器 `TileEntity` 来设置它将生成的生物。你可以使用以下代码来实现：

点击此处查看代码图片

```java
if (spawner != null)
{
    spawner.func_145881_a().setEntityName("Skeleton");
}
else
{
    System.err.println("Failed to fetch mob spawner entity at (" + x + ", " + y + ", " + z + ")");
}
```

首先，会进行检查以确保实际上找到了生成器。如果你没有这个检查，这段代码可能会导致崩溃。

`if` 语句中的代码只是设置了它将生成的生物类型。在这种情况下，它生成的是骨骼。

#### 提示：实体名称

你可以通过查看 `EntityList` 类的底部找到游戏中每一个实体的实体名称。

如果由于某种原因没有找到生成器，它将作为错误打印在日志中。这确保了你能够收到警报并修复它。

完整的生物刷生成器代码应该看起来所示 列表 16.5。

**列表 16.5 生物刷生成器代码**

点击此处查看代码图片

```java
world.setBlock(x + 5, y + 1, z + 1, Blocks.mob_spawner);
TileEntityMobSpawner spawner = (TileEntityMobSpawner)world.getTileEntity(x + 5, y + 1, z + 1);
if (spawner != null)
{
    spawner.func_145881_a().setEntityName("Skeleton");
}
else
{
    System.err.println("Failed to fetch mob spawner entity at (" + x + ", " + y + ", " + z + ")");
}
```

### 总结

在本小时中，你完成了这本书的“世界生成”部分。在过去的两个小时里，你学习了如何为矿石、植物和结构添加世界生成。在本小时，你学习了如何安装和使用转换器，以及如何编辑导出文件使其能够无错误地生成到世界。最后，你还学习了实体生成选项以及如何对它们进行编码。

### 问答

**Q。文件大小有限制吗？**

**A。** 没有实际限制，但如果文件变得过长，不仅生成时间更长，在 Eclipse 中加载的时间也会更长。如果文件大小太大，甚至可能导致游戏崩溃。

**Q。可以添加的 `WorldGen` 文件数量有限制吗？**

**A。** 没有实际限制，但如果文件变得过长，不仅生成时间更长，在 Eclipse 中加载的时间也会更长。如果文件大小太大，甚至可能导致游戏崩溃。

在处理服务器和客户端时，代理（Proxies）非常重要。有一个 `CommonProxy`，其代码专注于服务器端；而 `ClientProxy` 则包含了客户端的代码。正如你从早些章节中解释的 `@SideOnly(Side.CLIENT)` 代码所了解的，某些代码只在客户端上运行。如果这些代码在服务器上运行，Minecraft 就会崩溃。代理可以被视为上方带有 `@SideOnly` 注解的整个类。

然而，在 Forge 中，你必须对某些客户端或服务器代码使用代理，这些代码只能在 Minecraft 启动的特定时刻运行。这主要包括渲染的注册，这也是本本书使用代理的地方。

### 在你的 Mod 中添加代理

创建代理的首要要求是向 mod 文件中添加一些代码。在变量列表中添加以下两行：

点击此处查看代码图片

```java
@SidedProxy(clientSide = "com.wuppy.samsmod.ClientProxySam", serverSide = "com.wuppy.samsmod.CommonProxySam")
public static CommonProxySam proxy;
```

这段代码在 `CommonProxySam` 处有一个错误，你稍后通过创建文件来修复它。首先，了解这段代码的作用以及它是如何工作的是重要的。

`@SidedProxy` 注解包含两个参数：`clientSide` 和 `serverSide`。它们都接受一个 `String`，应包含引用客户端和服务器代理的 `String`。该 `String` 将是包名，后跟类名，中间用点分隔。在这种情况下，两个名为 `ClientProxySam` 和 `CommonProxySam` 的类被添加到了 `com.wuppy.samsmod` 包中。

直接在 `@SidedProxy` 注解下方添加 `CommonProxy` 变量。

添加此代码后，在 `preInit` 方法中添加如下单行代码：

```java
proxy.registerRendering();
```

将此作为 `preInit` 方法的第一行是一个好主意。`registerRendering` 包含了注册渲染的代码，它并不依赖 `preInit` 之后的任何代码。然而，有些代码是依赖的。如果渲染尚未注册，这些代码可能会崩溃，因此用这一行代码启动 `preInit` 是重要的。

### 编写 CommonProxy

现在，将鼠标悬停在 `CommonProxySam` 下方的错误上并选择“Create Class”（创建类）。列表 17.1 显示了出现的文件。

**列表 17.1 初始 CommonProxySam**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

public class CommonProxySam
{

}
```

`CommonProxySam` 下方的错误现在消失了，但 `registerRendering` 处有一个错误。将鼠标悬停在错误上并选择“Create Method”（创建方法）。在稍微清理一下类后，它看起来应该像列表 17.2。

**列表 17.2 带有 registerRendering 方法的 CommonProxySam**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

public class CommonProxySam
{
    public void registerRendering()
    {

    }
}
```

由于所有的渲染都在客户端完成，此方法在 `CommonProxy` 中是空的。

### 创建 ClientProxy



要创建 `ClientProxySam`，右键点击 `com.wuppy.samsmod` 包并选择 New Class（新建）。类名将为 `ClientProxySam`。Listing 17.3 显示了结果类。

**列表 17.3 初始 `ClientProxySam`**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

public class ClientProxySam
{

}
```

该类必须扩展 `CommonProxy`。它还必须重写 `CommonProxy` 中的方法。这样做之后，它看起来像 Listing 17.4。

**列表 17.4 带有 `registerRendering` 的 `ClientProxy`**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

public class ClientProxySam extends CommonProxySam
{
    @Override
    public void registerRendering()
    {

    }
}
```

该类目前将保持为空，但在第 19 小时中是需要的。

### 创建基础实体

在创建生物之前，了解实体所需的基础代码是很重要的。

Minecraft 中的每个实体（`TileEntity` 除外）都必须使用 `EntityRegistry` 进行注册。对于 `EntitySamMob`（将在几小时后创建的生物），`EntityRegistry` 将如下：

点击此处查看代码图片

```java
EntityRegistry.registerModEntity(EntitySamMob.class, "sammob", 0, this, 80, 3, true);
```

这段代码包含一个错误，你稍后通过创建 `EntitySamMob` 类来修复它。`registerModEntity` 是注册实体所需的方法。其中的第一个参数是你想要注册的 `Entity` 类。

第二个参数是你想要注册的名称。两个不同的 mod 在这里可以使用相同的名称，但在注册表中不能有两个同名的生物。第三个参数是生物的 ID。第四个参数是 `this`。第五个参数是追踪范围——这是实体距离玩家仍能更新的最大距离。第六个参数是更新频率。最后一个参数表示在更新时是否应随实体发送速度信息。

### 创建 `EntitySamMob` 类

要创建 `EntitySamMob` 类，只需将鼠标悬停在错误上并选择“Create Class”。Listing 17.5 显示了结果类。

**列表 17.5 空的 `EntitySamMob` 类**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

public class EntitySamMob
{

}
```

要让 `EntitySamMob` 成为一个实体，你需要扩展 `Entity`，这通过在 `EntitySamMob` 之后添加以下代码来实现。不要忘记导入 `Entity` 类。

```java
extends Entity
```

在导入 `Entity` 类时，确保你获取的是 `Minecraft` 包中的那一个。一旦这样做，你会在 `EntitySamMob` 下得到一个错误，你可以通过添加构造函数来修复它。添加构造函数后，`EntitySamMob` 处会出现第二个错误，你可以通过悬停在上方并选择“Add Unimplemented Methods”（添加未实现的方法）来修复它。

稍微清理一下类后，它看起来应该像 Listing 17.6。

**列表 17.6 带有所需方法的 `EntitySamMob`**

```java
package com.wuppy.samsmod;

import net.minecraft.entity.Entity;
import net.minecraft.nbt.NBTTagCompound;
import net.minecraft.world.World;

public class EntitySamMob extends Entity {

    public EntitySamMob(World par1World) {
        super(par1World);
    }

    @Override
    protected void entityInit() {
    }

    @Override
    protected void readEntityFromNBT(NBTTagCompound tag) {
    }

    @Override
    protected void writeEntityToNBT(NBTTagCompound tag) {
    }
}
```

### 总结

在这一节中，你首先学习了什么是实体（entity）。实体在 Minecraft 中被频繁使用，有很多类型，因此理解基础知识非常重要。接下来，你学习了如何创建代理（proxies），它们用于注册后续几小时内创建的实体的渲染代码。最后，你创建了第一个 `Entity` 类并注册了它。该实体目前还没有任何功能，但将在第 19 小节中添加功能。

### 问答

**Q. 可注册实体的数量有限制吗？**

**A.** 没有。但是，如果有大量的实体需要注册，Minecraft 启动时将会花费更长的时间。

**Q. 为什么即使代理是空的，我也必须创建它们？**

**A.** 它们现在是空的，但在接下来的几小时内将添加一些非常重要的代码。

### 工作坊

在这一节中，你为实体奠定了基础。接下来的几节将涵盖如何创建你自己的实体，但完全理解本节涵盖的代码至关重要。请通过完成此测验来检查你的掌握程度。

### 测验

1. `ClientProxy` 是做什么用的？
2. 为什么 `CommonProxy` 中的方法必须在 `preInit` 方法的开始处调用？
3. 在 `ClientProxy` 中注册区块是一个好主意吗？

### 答案

1. 创建它的目的是为了仅在客户端侧运行注册代码。
2. 方法中的其他代码将依赖于代理中的代码。
3. 不，这会非常糟糕。如果区块只在客户端注册，它们将与服务器不同步，从而导致崩溃和许多其他问题。

### 练习题

为第二个生物创建一个 `registerEntity`。确保它有不同的名称和 ID。

## 第 18 小节：使用 Techne 创建实体模型

你将在这一节中学习到：

- 什么是模型？
- 下载并安装 Techne
- 使用 Techne

在这一节中，你学习了如何在 Techne 中创建一个基础模型，Techne 是一个专门为 Minecraft 模型设计的建模程序。在第 19 小节“编码生物”中，该模型将用于实体以创建一个生物。在 Techne 中创建模型之前，首先安装 Techne 并理解 Minecraft 中的模型是什么是重要的。最后，你导出创建的模型。

### 什么是模型？

Minecraft 中的模型由三部分组成。第一是模型的形状。Minecraft 中的每一个模型都是立方体的集合。第二部分是纹理。第三部分是动画。

Minecraft 中的模型由三部分组成。第一是模型的形状。Minecraft 中的每一个模型都是立方体的集合。第二部分是纹理。第三部分是动画。

**图 18.3** 带有所选立方体的 Techne。

一旦你选择了一个立方体，屏幕上的所有其他部分都将变为激活并可以使用。窗口中除了实际看到模型的部分外，最重要的部分位于左上角。在这里，你可以为每个立方体设置名称、位置、旋转以及其他几个属性。

顶部是名称，每个立方体的名称都必须不同，否则你会遇到问题。此名称不仅在 `Techne` 中使用，也会出现在你之后导出的代码中。

下方是尺寸，即立方体的 `x`、`y` 和 `z` 尺寸。

接下来是两组 `x`、`y` 和 `z` 值，这看起来可能有点困惑。它们分别是 `position`（位置）和 `offset`（偏移）。编辑正确的其中一个非常重要，否则你的模型可能会表现得异常。`position` 是立方体中蓝球所在的位置。蓝球是立方体绕其旋转的点。这个 `position` 非常重要，因为它决定了行走时手臂是绕着移动，还是会一直掉落。蓝球可以看作是立方体的关节。当 `offset` 正常时，此球位于立方体的中心。为了将关节移动到逻辑位置（例如右臂的左上角），可以使用 `offset`。

`Texture offset`（纹理偏移）用于纹理的位置。整个模型有一个纹理，它被切割成每个立方体的若干部分。由于每个立方体可能有不同的纹理，因此必须使用 `texture offset` 来确保立方体使用图像中正确部分的纹理。可以在右上看到纹理。选中的立方体颜色透明度略低，你可以轻松地看到立方体是从纹理的哪个部分获取的。

`rotation`（旋转）用于旋转身体部位。它始终围绕蓝球旋转，并可以在每个方向旋转。`ModelBiped` 的每个值旋转均为 0，但当玩家行走时，身体部位确实会移动。你在这里设置的每个值稍后可以在代码中编辑，或者在 Minecraft 运行时由代码编辑。不过，在 `Techne` 中将旋转值设置为标准值是一个好主意。

你的模型还有两个选项。第一，`mirror texture`（镜像纹理）允许两只手臂使用相同的纹理区域并对其进行镜像。第二，`GlScale`（全局缩放）允许让每个部分看起来比实际大或更小。这通常被设置为 1，使其看起来很正常。这只是 `Techne` 中的一个视觉辅助，不会影响你的模型。

### 添加和删除立方体

要添加立方体，可以使用 `GlScale` 正下方的蓝色立方体。这会在原点添加一个尺寸为 1, 1, 1 的新立方体。下方还有几个你可以使用的选项来删除、复制和粘贴立方体。

屏幕上的最后一个选项是 `Load Texture`（加载纹理）。你可以用它将模型纹理加载到模型上。由于在此之前使用的模型与 `ModelBiped` 完全相同，你可以使用像僵尸这样的纹理来显示带有纹理的模型。

### 尝试一下：添加僵尸纹理

为模型添加僵尸纹理。请按照以下步骤操作：

1. 进入 Minecraft 的安装位置，默认路径为 `C:\Users\[username]\AppData\Roaming\.minecraft\versions`。
2. 选择你想要纹理的 Minecraft 版本，并用 7zip 或 Winrar 打开 `.jar` 文件。
3. 所有纹理可以在 `assets/minecraft/textures` 中找到。进入这些文件夹。
4. 对于僵尸纹理，进入 `entity/zombies` 并选择 `zombie.png`。
5. 现在将其复制到你可以轻松找到的文件夹中。
6. 在 `Techne` 中选择 `Load Texture`。
7. 选择 `zombie.png` 文件，Techne 看起来就像图 18.4。

![Image](img/image0063.jpeg)

**图 18.4** Techne 中的僵尸。

这一小时制作的生物与带有标准玩家纹理的 `ModelBiped` 非常。。区别是头部有一个帽子。在 `Techne` 中，这个模型看起来像图 18.5。

![Image](img/image00637.jpeg)

**图 18.5** Sam 的生物模型。

### 导出你的模型

创建模型后，如果它能在 Minecraft 中被实际使用就太好了。你可以通过导出来实现。你可以使用右上角的 `File`（文件）-> `Export As`（导出为）进行导出。模型必须同时导出为 `Texturemap` 和 `Java`。别忘了也将你的模型保存为 `Techne` 文件，以便稍后进行编辑。图 18.6 显示了可以导出的菜单。

![Image](img/image00638.jpeg)

**图 18.6** Sam 的生物模型。

导出的模型 Java 类看起来与列表 18.1 类似。

**列表 18.1 导出的模型**

点击查看代码



```java
// Date: 2014/4/6 10:20 PM
// Template version 1
// generated by Techne
package net.minecraft;
public class ModelModel extends ModelBase
{
  ModelRenderer cap;
  ModelRenderer head;
  ModelRenderer body;
  ModelRenderer rightarm;
  ModelRenderer leftarm;
  ModelRenderer rightleg;
  ModelRenderer leftleg;

  public ModelModel()
  {
    cap = new ModelRenderer(this, 8, 8, 8, 0, 0, 0);
    head = new ModelRenderer(this, 8, 8, 8, 0, 0, 0);
    body = new ModelRenderer(this, 8, 12, 12, 0, 0, 0);
    rightarm = new ModelRenderer(this, 4, 8, 4, 0, 0, 0);
    leftarm = new ModelRenderer(this, 4, 8, 4, 0, 0, 0);
    rightleg = new ModelRenderer(this, 4, 12, 4, 0, 0, 0);
    leftleg = new ModelRenderer(this, 4, 12, 4, 0, 0, 0);

    cap.addBox(-4, 8, -4, 8, 8, 8);
    head.addBox(-4, 0, -4, 8, 8, 8);
    body.addBox(-4, 0, -4, 8, 12, 8);
    rightarm.addBox(-4, 0, -4, 4, 8, 4);
    leftarm.addBox(-4, 0, -4, 4, 8, 4);
    rightleg.addBox(-4, 0, -4, 4, 12, 4);
    leftleg.addBox(-4, 0, -4, 4, 12, 4);

    cap.pivotOffset(0, 24, 0);
    head.pivotOffset(0, 16, 0);
    body.pivotOffset(0, 12, 0);
    rightarm.pivotOffset(5, 12, 0);
    leftarm.pivotOffset(-5, 12, 0);
    rightleg.pivotOffset(2, 12, 0);
    leftleg.pivotOffset(-2, 12, 0);
  }

  public void setModelParts(ModelBiped model)
  {
    cap = model.cap;
    head = model.head;
    body = model.body;
    rightarm = model.rightarm;
    leftarm = model.leftarm;
    rightleg = model.rightleg;
    leftleg = model.leftleg;
  }

  public void renderModel(AbstractRenderBuffer buffer, float x, float y, float z, float groundRotation, float groundY, float groundZ)
  {
    cap.render(buffer, x, y, z, groundRotation, groundY, groundZ);
    head.render(buffer, x, y, z, groundRotation, groundY, groundZ);
    body.render(buffer, x, y, z, groundRotation, groundY, groundZ);
    rightarm.render(buffer, x, y, z, groundRotation, groundY, groundZ);
    leftarm.render(buffer, x, y, z, groundRotation, groundY, groundZ);
    rightleg.render(buffer, x, y, z, groundRotation, groundY, groundZ);
    leftleg.render(buffer, x, y, z, groundRotation, groundY, groundZ);
  }

  public void setRotation(ModelBiped model)
  {
    cap.rotateX = model.cap.rotateX;
    cap.rotateY = model.cap.rotateY;
    cap.rotateZ = model.cap.rotateZ;
    head.rotateX = model.head.rotateX;
    head.rotateY = model.head.rotateY;
    head.rotateZ = model.head.rotateZ;
    body.rotateX = model.body.rotateX;
    body.rotateY = model.body.rotateY;
    body.rotateZ = model.body.rotateZ;
    rightarm.rotateX = model.rightarm.rotateX;
    rightarm.rotateY = model.rightarm.rotateY;
    rightarm.rotateZ = model.rightarm.rotateZ;
    leftarm.rotateX = model.leftarm.rotateX;
    leftarm.rotateY = model.leftarm.rotateY;
    leftarm.rotateZ = model.leftarm.rotateZ;
    rightleg.rotateX = model.rightleg.rotateX;
    rightleg.rotateY = model.rightleg.rotateY;
    rightleg.rotateZ = model.rightleg.rotateZ;
    leftleg.rotateX = model.leftleg.rotateX;
    leftleg.rotateY = model.leftleg.rotateY;
    leftleg.rotateZ = model.leftleg.rotateZ;
  }

  public void setRotation(ModelBiped model)
  {
    cap.rotateX = model.rotateX;
    cap.rotateY = model.rotateY;
    cap.rotateZ = model.rotateZ;
    head.rotateX = model.rotateX;
    head.rotateY = model.rotateY;
    head.rotateZ = model.rotateZ;
    body.rotateX = model.rotateX;
    body.rotateY = model.rotateY;
    body.rotateZ = model.rotateZ;
    rightarm.rotateX = model.rotateX;
    rightarm.rotateY = model.rotateY;
    rightarm.rotateZ = model.rotateZ;
    leftarm.rotateX = model.rotateX;
    leftarm.rotateY = model.rotateY;
    leftarm.rotateZ = model.rotateZ;
    rightleg.rotateX = model.rotateX;
    rightleg.rotateY = model.rotateY;
    rightleg.rotateZ = model.rotateZ;
    leftleg.rotateX = model.rotateX;
    leftleg.rotateY = model.rotateY;
    leftleg.rotateZ = model.rotateZ;
  }
}
```

***

当这个模型在第 19 小时被添加到 Eclipse 时，你需要做一些工作，因为现在有几处错误。

纹理从 Techne 导出后，看起来类似于图 18.7。

![Image](img/image00639.jpeg)

**图 18.7** 导出的 Sam 的生物纹理。

这看起来可能非常模糊，但在 Techne 中可以看到哪个立方体对应纹理中的哪个部分。每个区域的颜色与 Techne 模型视图底部方向立方体的相同。为生物制作纹理最简单的方法是在 Techne 中导入纹理并查看效果。当你编辑加载的纹理文件时，`Techne` 会自动为你更新，这样你就能看到更改。

编辑纹理后，该生物看起来就像图 18.8。

![Image](img/image00640.jpeg)

**图 18.8** 完成的 Sam 的生物纹理。

`.techne` 文件本身可以在本书的示例文件中找到（请参见介绍部分获取下载文件的说明）。

在第 19 节中，你将使用这些文件让生物真正运行起来。

***

### 注意：其他建模软件

Techne 是唯一可以将模型导出为 Minecraft 代码格式的常用建模软件。然而，Forge 也允许你使用 `.obj` 文件。大多数现代建模程序（包括 Blender 和 Maya）都支持这种扩展名。如果你使用 `.obj` 文件，则必须使用一个名为 `AdvancedModelLoader` 的类来加载该模型。

### 总结

在本节中，你首先学习了 Minecraft 中的模型是什么以及你如何使用它们。接下来，你学习了 Techne，这是一个你可以在其中轻松创建模型的工具。你学习了如何安装 Techne、界面是如何工作的，以及如何使用它创建自己的模型。此外，你还将模型从 Techne 导出为 `.png` 和 `.java` 文件，你可以使用它们来为你的生物编写代码和制作纹理。

### 问答

**问。模型立方体的数量有上限吗？**

**答。** 没有上限，但当立方体更多时，渲染所需的时间更长，因此请尝试在性能和外观之间平衡。

**问。这种模型可以用于生物以外的其他用途吗？**

**答。** 是的。它们也可以用于方块和物品。

### 工作坊

在本节中，你学习了模型以及如何在 Techne 中创建它们。许多不同的 Mod 都使用模型，因此很好地理解这些非常重要。完成问答来测试你的理解程度。

### 测验

**1。为什么你必须使用 Techne？**

**2。你需要从 Techne 导出什么？**

### 答案

**1。** 因为这样更简单。你可以手写模型，但那将花费非常长时间。Techne 让你的模型可视化变得非常容易。

**2。** 你需要导出纹理和代码。然而，不要忘记将模型保存为 `.techne` 文件，否则你以后将无法编辑它。

### 练习题

编辑 `ModelBiped`，使其在身体中间只有一条腿。

## 第 19 节 编写生物代码

***

你将在本节中学习到：

![Image](img/image00525.jpeg) 渲染生物

![Image](img/image00525.jpeg) 让生物生成

![Image](img/image00525.jpeg) 让 `EntitySamMob` 成为一个生物

***

在本节中，你将结合你在第 17 节和第 18 节中所做的内容，分别是“关于实体”和“使用 Techne 创建实体模型”，来创建一个生物。本节涵盖了合并这些代码并添加更多内容，以使实体像生物一样工作。

要创建一个生物，必须创建很多类。首先，你需要一个 Mod 文件，你已经创建了。你还需要在第 17 节中创建的 `CommonProxy` 和 `ClientProxy`。此外，你还需要 `Entity`、`Model` 和 `Render` 类。本节涵盖了所有文件，从 `Model` 开始。

### 渲染生物

生物的一个非常重要的方面是它是可见的。为了实现这一点，你创建了 `Model` 和 `Render` 文件。你还向 `ClientProxy` 添加一行代码。

### 完成模型类

在第 18 节中，你在 Techne 中创建了一个模型并从中导出了代码。现在是时候将此模型添加到你的工作区了。要这样做，在 Eclipse 中右键点击你的包并选择 New（新建）、Class（类）。该类名为 `ModelSamMob`。对于所有与同一生物相关的类使用非常相似的名字是一个好主意。在本节中创建的生物有 `EntitySamMob`、`ModelSamMob` 和 `RenderSamMob` 作为它的类，你在整个节中创建了它们。这样，在 Mod 中有多个生物的情况下，很容易看出哪些类属于哪个生物。

***

### 注意：关于 Techne

你不被强制使用 Techne。自己编写模型是完全可以的。如果你这样做，必须编写所有的代码，这可能会花费大量时间。

***

接下来，从导出的 `.java` 文件中复制代码并粘贴到 `ModelSamMob` 中。这段代码有很多问题。要修复所有问题，请按照以下列表操作：

![Image](img/image00525.jpeg) 移除顶部的注释。它没有添加添加，并且可能让你的类难以阅读。

![Image](img/image00525.jpeg) 修改包声明。导出的文件包名为 `net.minecraft.src`，你应该将其更改为该类所在的包。当你将鼠标悬停在它上面时，可以选择 Change Declaration（更改声明）将其更改为正确的包。

![Image](img/image00525.jpeg) 将类和构造函数的名称从 `Model` 改为 `ModelSamMob`，或者你的 `Model` 文件的名称。你可以通过将鼠标悬停在 `Model` 下方的错误上并选择 Rename Type（重命名类型）来轻松完成这一点。

![Image](img/image00525.jpeg) 使用 `Ctrl+Shift+O` 或右键点击选择 Source（源）、Organize Imports（组织导入）导入所有使用的文件。

***

### 注意：Techne 并非完美

与其他任何事物一样，Techne 并不完美。你的导出代码可能包含某些错误。如果你尝试使用比 Techne 创建的不同版本的导出代码，可能会遇到问题。

你可能想要检查的是 `[bodypart].mirror = true;` 是否在身体部分初始化之前使用。这有时会发生并导致崩溃。

***

该类现在看起来像列表 19.1 且不再留有任何错误。

**列表 19.1 完成的 `ModelSamMob`**

点击此处查看代码

***

```java
package com.wuppy.samsmod.render;

import net.minecraft.client.model.ModelBase;
import net.minecraft.client.model.ModelRenderer;
import net.minecraft.entity.Entity;

public class ModelSamMob extends ModelBase
{
    // fields
    ModelRenderer cap;
    ModelRenderer head;
    ModelRenderer body;
    ModelRenderer rightarm;
    ModelRenderer leftarm;
    ModelRenderer rightleg;
    ModelRenderer leftleg;
    public ModelSamMob()
    {
        textureWidth = 64;
        textureHeight = 32;
        cap = new ModelRenderer(this, 35, 0);
        cap.addBox(-3F, -10F, -3F, 6, 2, 6);
        cap.setRotationPoint(0F, 0F, 0F);
        cap.setTextureSize(64, 32);
        cap.mirror = true;
        setRotation(cap, 0F, 0F, 0F);
        head = new ModelRenderer(this, 0, 0);
        head.addBox(-4F, -8F, -4F, 8, 8, 8);
        head.setRotationPoint(0F, 0F, 0F);
        head.setTextureSize(64, 32);
        head.mirror = true;
    }
}
```

***

### 移动身体部位

一旦你完成了这一节，你将拥有一个功能完备的生物（mob）。它会走动并攻击敌人。当原版（vanilla）生物移动时，它们的腿（在某些情况下还有手臂）会移动。如果身体部位没有正确移动，这些生物在移动时看起来会非常奇怪。

因此，为了确保这个生物看起来不奇怪，当玩家移动时，身体部位应该旋转。你可以使用 `setRotationAngles` 做到这一点。在这个方法中，你可以使用基础三角函数为每个身体部位设置旋转。



因为这个模型几乎与 `ModelBiped` 完全相同（后者用于玩家等普通实体），所以该类中的旋转逻辑可以很容易地复制到这里。`ModelBiped` 中的代码变量名略有不同，你需要将它们更改为 `ModelSamMob` 中的名称。你可以删除某些行，例如设置潜行或持弓等动作的旋转行，因为自定义的生物不需要执行这些操作。

你还添加了两行代码。这两行代码确保了帽子（cap）的旋转方式与头部完全一致。这确保了帽子不会穿入头部。由于头部和帽子的旋转点相同，头部的旋转角度可以直接复制到帽子的旋转上。

`ModelSamMob` 中的 `setRotationAngles` 现在看起来应该像列表 19.2。

**列表 19.2 添加到 `ModelSamMob` 的 `setRotationAngles`**

点击此处查看代码图像

***

```java
        return null;

    }
}
```

***

将 `getEntityTexture` 中的 `null` 替换为以下代码：

点击此处查看代码图片

```java
new ResourceLocation(SamsMod.MODID, "textures/models/sammob.png")
```

这将获取位于 `SamsMod` textures 文件夹中的纹理。在该文件夹中有一个名为 `textures` 的文件夹。在该文件夹内另一个名为 `models` 的文件夹——在这个文件夹中，放置上一小时内创建的生物纹理。在这种情况下，文件名为 `sammob.png`。在大多数情况下，最好在代码中为纹理命名与生物相同的名称。纹理看起来所示图 19.1。

![Image](img/image00641.jpeg)

**图 19.1** 实体纹理。

### 渲染生物

现在 `Render` 和 `Model` 类已经完成，这意味着你现在可以实际渲染该生物了。要做到这一点，请向 `ClientProxy` 中添加以下行代码：

点击此处查看代码图片

```java
RenderingRegistry.registerEntityRenderingHandler(EntitySamMob.class, new RenderSamMob(new ModelSamMob(), 0.5F));
```

要注册一个生物，你必须访问 `RenderingRegistry` 类。对于实体，所需的方法是 `registerEntityRenderingHandler`。该方法接受两个参数。第一个参数是它应该注册渲染的 `Entity` 类。

其次，它需要一个用于进行渲染的类。在这种情况下，该类是 `RenderSamMob`。`RenderSamMob` 同样接受两个参数。第一个参数是它应该渲染的模型，在本例中为 `ModelSamMob`。第二个参数是阴影大小。如果你将其调大，生物下方的阴影圆也会随之变大。`0.5F` 是类似于玩家模型的默认值。

`ClientProxy` 现在看起来应该像代码列表 19.5。

**代码列表 19.5 带有 `RenderingRegistry` 的 `ClientProxySam`**

点击此处查看代码图片

***

```java
package com.wuppy.samsmod;

import cpw.mods.fml.client.registry.RenderingRegistry;

public class ClientProxySam extends CommonProxySam
{
    @Override
    public void registerRendering()
    {
        RenderingRegistry.registerEntityRenderingHandler(EntitySamMob.class, new RenderSamMob(new ModelSamMob(), 0.5F));
    }
}
```

尽管你没有向 `CommonProxy` 中添加任何代码，但不要将其删除，因为没有它，`ClientProxy` 将无法工作。

### 让生物生成

让生物生成有两种方法。一种是生物蛋，它允许你通过物品生成生物；另一种是自然生成，它能确保（例如）牛会在草地上行走。

### 添加生物蛋

为你的每一个生物都提供一个生物蛋是明智的。这会让测试变得容易得多。在某些情况下它也能帮助用户。然而，生物蛋最好的部分是它只需要很少的代码，而且不会使用任何新物品。新的生物蛋会被添加到原版的生物蛋中。

要将你的生物添加到生物蛋中，请在 mod 类中添加以下代码：

点击此处查看代码图片

```java
static int startEntityId = 300;

@SuppressWarnings("unchecked")
public static void registerEntityEgg(Class<? extends Entity> entity, int primaryColor, int secondaryColor)
{
    int id = getUniqueEntityId();
    EntityList.IDtoClassMapping.put(id, entity);
    EntityList.entityEggs.put(id, new EntityEggInfo(id, primaryColor, secondaryColor));
}

public static int getUniqueEntityId()
{
    do
    {
        startEntityId++;
    }
    while (EntityList.getStringFromID(startEntityId) != null);
}
```

点击此处查看代码图像

```java
package com.wuppy.samsmod;

import net.minecraft.entity.monster.EntityMob;

import net.minecraft.world.World;

public class EntitySamMob extends EntityMob
{
    public EntitySamMob(World par1World)
    {
        super(par1World);
    }
}
```

你可以使用 `EntityMob` 执行很多事情。虽然要涵盖实体的所有可能是不可能的，但接下来的章节涵盖了一些最重要的部分。

### 为生物添加 AI

Minecraft 包含许多 `EntityAI` 类，你可以使用这些类来让你的生物移动得更加自然。一个生物可以有许多不同的 `EntityAI` 类供其选择；可以给它分配一个数字，告诉生物在何时使用哪一个。数字越小，它执行某项 AI 的概率就越高。例如，僵尸通常会在周围游荡，但一旦它们有了要攻击的目标玩家，这种行为就不再发生了。在相同的数字下也可能存在两个不同的 AI——此时，生物可能会根据 `AI` 类中的检查结果执行其中某一个。例如，僵尸通常会环顾四周，但一旦目标玩家靠近，它就会看向玩家。这两个 `EntityAI` 选项的数字是相同的，但在任何给定时间只能发生其中一个。列表 19.7 包含了 `EntitySamMob` 的 `AI`。

**代码列表 19.7 `EntitySamMob` AI 代码**

点击此处查看代码图像

```java
public EntitySamMob(World par1World)
{
    super(par1World);
    this.getNavigator().setBreakDoors(true);
    this.tasks.addTask(0, new EntityAISwimming(this));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityPlayer.class, 1.0D, false));
    this.tasks.addTask(3, new EntityAIWander(this, 1.0D));
    this.tasks.addTask(4, new EntityAIWatchClosest(this, EntityPlayer.class, 8.0F));
    this.tasks.addTask(4, new EntityAILookIdle(this));
    this.targetTasks.addTask(1, new EntityAIHurtByTarget(this, true));
    this.targetTasks.addTask(2, new EntityAINearestAttackableTarget(this, EntityPlayer.class, 0, true));
}
```

这段代码包含三个不同的部分。首先，有一行关于破坏门的代码。这仅仅是确保了 Sam 的生物在追逐玩家时可以像僵尸一样破坏门。

其次，有五个 `AI` 任务。优先级为 0（最高）的是 `EntityAISwimming`。如果这个任务不是优先级 0，生物可能会溺死，因为它在水里会执行其他事情。这个 `AI` 只在生物处于水中时运行，所以它不会影响在陆地上的行为。

第三，是 `AttackOnCollide`，它接受四个参数。第一个参数是 `this`，然后是它应该攻击的实体、攻击速度，最后是 `false`。这个 `AI` 不会让实体朝目标实体移动，而只会在与实体碰撞时伤害玩家。

如果它不需要游泳或在碰撞时伤害玩家，它就会使用 `EntityAIWander` 随机走动。它还会使用 `EntityAIWatchClosest` 查看最近的目标，或者只是使用 `EntityAILookIdle` 环顾四周。

最后的新新点是 `targetTasks`。这些任务实际上告诉实体应该向哪个方向移动。它通常将 `EntityAIHurtByTarget` 作为第一个任务。之后，可以多次使用 `EntityAINearestAttackableTarget`。某些生物只攻击玩家，而其他生物会攻击玩家、村民等。在这种情况下，只有当 `EntityPlayer` 足够近时，它才会追逐。

这里有很多不同的 `EntityAI` 类，你也可以创建自己的。此外，你还可以以不同的方式组合它们，让生物的行为产生不同差异。

### 尝试一下：攻击村民

让 `EntitySamMob` 攻击村民。要做到这一点，向 `tasks` 中添加另外两个 `EntityAI`，向 `targetTasks` 中添加一个。

首先，为 `EntityVillager` 添加一个 `EntityAIAttackOnCollide`。

然后，在 `targetTasks` 中为村民添加一个 `EntityAINearestAttackableTarget`。

添加这些后，构造函数看起来应该是这样的：

点击此处查看代码图像

```java
public EntitySamMob(World par1World)
{
    super(par1World);
    this.getNavigator().setBreakDoors(true);
    this.tasks.addTask(0, new EntityAISwimming(this));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityPlayer.class, 1.0D, false));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityVillager.class, 1.0D, false));
    this.tasks.addTask(3, new EntityAIWander(this, 1.0D));
    this.tasks.addTask(4, new EntityAIWatchClosest(this, EntityPlayer.class, 8.0F));
    this.tasks.addTask(4, new EntityAILookIdle(this));
    this.targetTasks.addTask(1, new EntityAIHurtByTarget(this, true));
    this.targetTasks.addTask(2, new EntityAINearestAttackableTarget(this, EntityPlayer.class, 0, true));
}
```

这里有很多不同的 `EntityAI` 类，你也可以创建自己的。此外，你还可以以不同的方式组合它们，让生物的行为产生不同差异。

### 尝试一下：攻击村民

让 `EntitySamMob` 攻击村民。要做到这一点，向 `tasks` 中添加另外两个 `EntityAI`，向 `targetTasks` 中添加一个。

首先，为 `EntityVillager` 添加一个 `EntityAIAttackOnCollide`。

然后，在 `targetTasks` 中为村民添加一个 `EntityAINearestAttackableTarget`。

添加这些后，构造函数看起来应该是这样的：

点击此处查看代码图像

```java
public EntitySamMob(World par1World)
{
    super(par1World);
    this.getNavigator().setBreakDoors(true);
    this.tasks.addTask(0, new EntityAISwimming(this));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityPlayer.class, 1.0D, false));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityVillager.class, 1.0D, false));
    this.tasks.addTask(3, new EntityAIWander(this, 1.0D));
    this.tasks.addTask(4, new EntityAIWatchClosest(this, EntityPlayer.class, 8.0F));
    this.tasks.addTask(4, new EntityAILookIdle(this));
    this.targetTasks.addTask(1, new EntityAIHurtByTarget(this, true));
    this.targetTasks.addTask(2, new EntityAINearestAttackableTarget(this, EntityPlayer.class, 0, true));
}
```

（注：由于用户提供的文本在后部分出现了重复段落，以下是根据您的要求重新整理并翻译的完整逻辑部分）

点击此处查看代码图像

```java
package com.wuppy.samsmod;

import net.minecraft.entity.monster.EntityMob;

import net.minecraft.world.World;

public class EntitySamMob extends EntityMob
{
    public EntitySamMob(World par1World)
    {
        super(par1World);
    }
}
```

你可以使用 `EntityMob` 执行很多事情。虽然要涵盖实体的所有可能是不可能的，但接下来的章节涵盖了一些最重要的部分。

### 为生物添加 AI

Minecraft 包含许多 `EntityAI` 类，你可以使用这些类来让你的生物移动得更加自然。一个生物可以有许多不同的 `EntityAI` 类供其选择；可以给它分配一个数字，告诉生物在何时使用哪一个。数字越小，它执行某项 AI 的概率就越高。例如，僵尸通常会在周围游荡，但一旦它们有了要攻击的目标玩家，这种行为就不再发生了。在相同的数字下也可能存在两个不同的 AI——此时，生物可能会根据 `AI` 类中的检查结果执行其中某一个。例如，僵尸通常会环顾四周，但一旦目标玩家靠近，它就会看向玩家。这两个 `EntityAI` 选项的数字是相同的，但在任何给定时间只能发生其中一个。列表 19.7 包含了 `EntitySamMob` 的 `AI`。

**代码列表 19.7 `EntitySamMob` AI 代码**

点击此处查看代码图像



```java
public EntitySamMob(World par1World)
{
    super(par1World);
    this.getNavigator().setBreakDoors(true);
    this.tasks.addTask(0, new EntityAISwimming(this));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityPlayer.class, 1.0D, false));
    this.tasks.addTask(3, new EntityAIWander(this, 1.0D));
    this.tasks.addTask(4, new EntityAIWatchClosest(this, EntityPlayer.class, 8.0F));
    this.tasks.addTask(4, new EntityAILookIdle(this));
    this.targetTasks.addTask(1, new EntityAIHurtByTarget(this, true));
    this.targetTasks.addTask(2, new EntityAINearestAttackableTarget(this, EntityPlayer.class, 0, true));
}
```

这段代码包含三个不同的部分。

首先，有一行关于破坏门的代码。这仅仅是确保了 Sam 的生物在追逐玩家时可以像僵尸一样破坏门。

其次，有五个`AI`任务。优先级为 0（最高）的是`EntityAISwimming`。如果这个任务不是优先级 0，生物可能会溺死，因为它在水里会执行其他事情。这个`AI`只在生物处于水中时运行，所以它不会影响在陆地上的行为。

第三，是`AttackOnCollide`，它接受四个参数。第一个参数是`this`，然后是它应该攻击的实体、攻击速度，最后是`false`。这个`AI`不会让实体朝目标实体移动，而只会在与实体碰撞时伤害玩家。

如果它不需要游泳或在碰撞时伤害玩家，它就会使用`EntityAIWander`随机走动。它还会使用`EntityAIWatchClosest`查看最近的目标，或者只是使用`EntityAILookIdle`环顾四周。

最后的新新点是`targetTasks`。这些任务实际上告诉实体应该向哪个方向移动。它通常将`EntityAIHurtByTarget`作为第一个任务。之后，可以多次使用`EntityAINearestAttackableTarget`。某些生物只攻击玩家，而其他生物会攻击玩家、村民等。在这种情况下，只有当`EntityPlayer`足够近时，它才会追逐。

这里有很多不同的`EntityAI`类，你也可以创建自己的。此外，你还可以以不同的方式组合它们，让生物的行为产生不同差异。

### 尝试一下：攻击村民

让`EntitySamMob`攻击村民。要做到这一点，向`tasks`中添加另外两个`EntityAI`，向`targetTasks`中添加一个。

首先，为`EntityVillager`添加一个`EntityAIAttackOnCollide`。

然后，在`targetTasks`中为村民添加一个`EntityAINearestAttackableTarget`。

添加这些后，构造函数看起来应该是这样的：

点击此处查看代码图像

```java
public EntitySamMob(World par1World)
{
    super(par1World);
    this.getNavigator().setBreakDoors(true);
    this.tasks.addTask(0, new EntityAISwimming(this));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityPlayer.class, 1.0D, false));
    this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityVillager.class, 1.0D, false));
    this.tasks.addTask(3, new EntityAIWander(this, 1.0D));
    this.tasks.addTask(4, new EntityAIWatchClosest(this, EntityPlayer.class, 8.0F));
    this.tasks.addTask(4, new EntityAILookIdle(this));
    this.targetTasks.addTask(1, new EntityAIHurtByTarget(this, true));
    this.targetTasks.addTask(2, new EntityAINearestAttackableTarget(this, EntityPlayer.class, 0, true));
}
```

```java
public class EntitySamMob extends EntityMob {

    public EntitySamMob(World par1World) {
        super(par1World);
        this.getNavigator().setBreakDoors(true);
        this.tasks.addTask(0, new EntityAISwimming(this));
        this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityPlayer.class, 1.0D, false));
        this.tasks.addTask(2, new EntityAIAttackOnCollide(this, EntityVillager.class, 1.0D, false));
        this.tasks.addTask(3, new EntityAIWander(this, 1.0D));
        this.tasks.addTask(4, new EntityAIWatchClosest(this, EntityPlayer.class, 8.0F));
        this.tasks.addTask(4, new EntityAIWatchClosest(this, EntityVillager.class, 8.0F));
        this.tasks.addTask(4, new EntityAILookIdle(this));
        this.targetTasks.addTask(1, new EntityAIHurtByTarget(this, true));
        this.targetTasks.addTask(2, new EntityAINearestAttackableTarget(this, EntityPlayer.class, 0, true));
        this.targetTasks.addTask(2, new EntityAINearestAttackableTarget(this, EntityVillager.class, 0, true));
    }

    protected void applyEntityAttributes() {
        super.applyEntityAttributes();
        this.getEntityAttribute(SharedMonsterAttributes.attackDamage).setBaseValue(3.0D);
    }

    protected Item getDropItem() {
        return SamsMod.samdust;
    }

    protected void dropRareDrop(int par1) {
        switch (this.rand.nextInt(2)) {
            case 0:
                this.dropItem(SamsMod.samsword, 1);
                break;
            case 1:
                this.dropItem(Item.getItemFromBlock(SamsMod.samTE), 1);
                break;
        }
    }
}
```

`图 19.3`显示了游戏中生成的`EntitySamMob`。

### 总结

在本节中，你学习了如何结合前几节创建的类和资源来创建一个功能完备的实体。到目前，你应该已经知道如何将模型导入 Minecraft，并对身体部位有了基本的理解。你还学习了如何创建一个基础的`Render`类，以及如何确保 Minecraft 使用`Model`和`Render`类来渲染你的实体。最后，你学习了如何使用`AI`、属性和掉落物来自定义你的实体。

### 问答

**Q**：每次生物死亡时，可以掉落多个一个物品或方块吗？

**A**：可以的。但是，要实现这一点，你必须找到调用`getDropItem`的方法，重写它并添加第二个物品。

**Q**：还有其他类型的实体吗？

**A**：是的。还有投掷物实体（throwables），它们将在下一节中介绍，此外还有像牛之类的实体。它们的工作方式与本节介绍的生物非常相似，但你必须更改`EnumCreatureType`，并将扩展类从`Mob`改为`Animal`。

**Q**：通常情况下，Minecraft 编程需要大量的数学知识，特别是三角函数吗？

**A**：不需要，在为 Minecraft 模组时不需要那么多数学。只有在进行旋转和自定义渲染时才需要数学。

### 工作坊

在本节中，你学习了实体和生物的编码。实体对于大多数模组来说非常重要，因为你可以用它们做很多事情。使用测验确保你完全理解了这些主题。

### 测验

**Q**：`EntityAI`之前的数字起什么作用？

**A**：它设置`AI`的优先级；数字越小，运行的可能性越高。

**Q**：如果不为实体属性赋值会发生什么？

**A**：它将使用默认值。

### 练习题

通过编辑其中一个实体属性来更改生物的速度。你可以将此代码添加到`applyEntityAttributes`方法中：

```java
this.getEntityAttribute(SharedMonsterAttributes.movementSpeed).setBaseValue(1.0D);
```

## 第 20 小节：创建一个投掷物

本节你将学习：

- 注册一个投掷物实体
- 创建`Entity`类
- 使用该实体
- 渲染实体

在本节中，你再次创建了一个实体。然而，这一次，这个实体不会没有玩家影响的情况下移动和工作，而是由玩家投掷。这听起来可能相当复杂，但 Minecraft 已经有了投掷物，例如雪球，所以大部分代码已经为你写写了。

### 注册投掷物实体

在创建新的实体文件之前，你必须像注册生物一样注册它。以下代码在`EntitySamThrowable`下方有一个错误，必须被添加到`preInit`方法中：

```java
EntityRegistry.registerModEntity(EntitySamThrowable.class, "samthrow", 1, this, 80, 3, true);
```

由于投掷物不会正常生成，因此该实体不需要添加`addSpawn`。

### 注意：实体注册数字

`registerModEntity`的第三个参数是你注册的实体的 ID。如你所知，这个 ID 对于每个模组都是唯一的，这意味着不同的模组可以拥有 ID 为 0 的实体。但是，你不能在同一个模组中使用两次相同的 ID，所以如果你不想遇到问题，请确保每个实体的 ID 都是不同的。

### 创建实体类

现在将鼠标悬停在`EntitySamThrowable`上并选择“创建类”（Create Class）。`列表 20.1`显示了生成的类。

```java
package com.wuppy.sams;
public class EntitySamThrowable {}
```

现在让这个类继承`EntityThrowable`。在完成操作并导入`EntityThrowable`后，它要求你添加构造函数。有三个选择，你必须全部添加。你还必须添加未实现的方法`onImpact`。在添加这些之后，`EntitySamThrowable`看起来像`列表 20.2`。

```java
package com.wuppy.samsmod;

import net.minecraft.entity.EntityLivingBase;
import net.minecraft.entity.projectile.EntityThrowable;
import net.minecraft.util.MovingObjectPosition;
import net.minecraft.world.World;

public class EntitySamThrowable extends EntityThrowable {

    public EntitySamThrowable(World par1World) {
        super(par1World);
    }

    public EntitySamThrowable(World par1World, EntityLivingBase par2EntityLivingBase) {
        super(par1World, par2EntityLivingBase);
    }

    public EntitySamThrowable(World par1World, double par2, double par4, double par6) {
        super(par1World, par2, par4, par6);
    }

    @Override
    protected void onImpact(MovingObjectPosition position) {

    }
}
```

第一个数字确保实体以合理的速度下落。另外两个数字与实体的旋转有关。

你可以通过重写`EntityThrowable`中的方法来编辑可投掷物的细节，但本书中只使用了`onImpact`，这在几乎所有情况下都是你需要的。

正如其名所示，`onImpact`是在投掷物与方块等物体发生碰撞时运行的方法。你可以添加代码来让投掷物变得独一无二。你在这一小时内创建的投掷物非常简单。当它与方块碰撞时，会发生爆炸。首先，添加基础的`onImpact`代码，该方法看起来如下：

```java
@Override
protected void onImpact(MovingObjectPosition position)
{
    if (!this.worldObj.isRemote)
    {
        this.setDead();
    }
}
```

首先，有一个检查确保大括号内的代码只在服务器上运行。这是始终要求的，因为`this.setDead()`应该只在服务器上调用。

在投掷物被杀死之前，它必须创建一个爆炸。通过在`this.setDead()`之前的`if`语句中添加以下行来实现：

```java
worldObj.newExplosion(this, position.blockX, position.blockY, position.blockZ, 3F, true, true);
```

第一个参数是爆炸的实体。接下来的三个是碰撞方块的`x`、`y`和`z`位置。`3F`是爆炸的威力。这个值越大，破坏的方块就越多。最后两个布尔值分别决定爆炸是否包含火焰和烟雾。

---

### 动手尝试一下：创建一个大型随机爆炸

创建一个带有某种随机性的大型爆炸。确保它的力量在 5 到 7 之间。

以下代码应该实现此功能：

```java
worldObj.newExplosion(this, position.blockX, position.blockY, position.blockZ, 5 + rand.nextInt(3), true, true);
```

---

`EntitySamThrowable`现在看起来应该像`Listing 20.3`所示。

**列表 20.3 EntitySamThrowable 完成**

---



```java
package com.wuppy.samsmod;

import net.minecraft.entity.EntityLivingBase;
import net.minecraft.entity.projectile.EntityThrowable;
import net.minecraft.util.MovingObjectPosition;
import net.minecraft.world.World;

public class EntitySamThrowable extends EntityThrowable
{
    public EntitySamThrowable(World par1World)
    {
        super(par1World);
    }
    public EntitySamThrowable(World par1World, EntityLivingBase par2EntityLivingBase)
    {
        super(par1World, par2EntityLivingBase);
    }
    public EntitySamThrowable(World par1World, double par2, double par4, double par6)
    {
        super(par1World, par2, par4, par6);
    }
    @Override
    protected void onImpact(MovingObjectPosition position)
    {
        if (!this.worldObj.isRemote)
        {
            worldObj.newExplosion(this, position.blockX, position.blockY, position.blockZ, 5 + rand.nextInt(3), true, true);
            this.setDead();
        }
    }
    @Override
    protected float getGravityVelocity()
    {
        return 0.07F;
    }
    @Override
    protected float func_70182_d()
    {
        return 0.7F;
    }
    @Override
    protected float func_70183_g()
    {
        return -20.0F;
    }
}
```

***

### 使用该实体

现在，投掷物已经完成并准备好使用了，但还没有方法可以生成它或以任何方式测试它。这个投掷物将由物品生成。为了实现这一点，必须创建一个新物品。你可以通过向类中添加以下行来实现：

```java
public static Item samthrow;
```

以及`preInit`方法：

```java
samthrow = new Item();
GameRegistry.registerItem(samthrow, "Throwable");
```

`samthrow`变量已注册。你可以通过创建`Item`类来修复这个问题：

```java
package com.wuppy.samsmod;

import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.item.Item;

public class ItemThrow extends Item
{
    public ItemThrow()
    {
        setCreativeTab(CreativeTabs.tabSpawn);
        setLocalizedName(MODID + ":Throwable");
        setTextureName(MODID);
    }
}
```

`en_US.lang`文件中的本地化内容如下：

```text
item.samthrow=Sam Throwable
```

### 让物品可以投掷

在 Minecraft 中，物品在右键点击时会被投出。要实现这一点，你使用`onItemRightClick`方法。为了让这个物品正常投掷，当右键点击时，应该移除`ItemStack`中的一个物品，但前提是玩家不在创造模式下。`onItemRightClick`的代码如下：

```java
@Override
public ItemStack onItemRightClick(ItemStack par1ItemStack, World par2World, EntityPlayer par3EntityPlayer)
{
    if (!par3EntityPlayer.capabilities.isCreative)
    {
        par1ItemStack.stackSize--;
    }
    return par1ItemStack;
}
```

除了减少`ItemStack`之外，如果能实际生成实体也将很有用。为了添加代码，必须进行检查以确保实体在服务器上生成，这是通过`World`中的`isRemote`变量实现的。在确保方法只在服务器上运行后，需要使用`spawnEntityInWorld`生成实体。整个`onItemRightClick`应该如下：

```java
@Override
public ItemStack onItemRightClick(ItemStack par1ItemStack, World par2World, EntityPlayer par3EntityPlayer)
{
    if (!par3EntityPlayer.capabilities.isCreative)
    {
        par1ItemStack.stackSize--;
    }
    if (!par2World.isRemote)
    {
        par2World.spawnEntityInWorld(new EntitySamThrowable(par2World, par3EntityPlayer));
    }
    return par1ItemStack;
}
```

之前创建的`EntitySamThrowable`两个参数确保了它在正确的位置生成。

### 渲染实体

现在当你右键点击物品时，会生成一个白框。为了让它看起来像被投出的物品，需要一个`Render`类。

幸运的是，Minecraft 有一个名为`RenderSnowball`的类，它能够按照雪球应有的方式渲染投掷物。然而，这里有一个小问题：`RenderSnowball`接收一个物品参数，即投掷物要渲染成的物品。到目前为止，渲染是在`registerRendering`方法中完成的，该方法在`preInit`阶段开始时被调用。然而，此时，所需的物品`samthrow`尚未初始化，因此为`null`，这会导致崩溃。为了修复这个问题，你在`Common`和`Client`代理中都添加第二个方法。你还必须在 mod 类中调用此方法。在初始化并注册物品之后，在`preInit`方法中添加以下行是非常关重要的：

```java
proxy.registerItemRenders();
```

带有新方法后，`CommonProxy`看起来类似于列表 20.6。

**列表 20.6 带有`registerItemRenders`方法的`CommonProxySam`**

点击此处查看代码图像

***

```java
package com.wuppy.samsmod;

public class CommonProxySam
{
    public void registerRendering()
    {
    }
    public void registerItemRenders()
    {
    }
}
```

***

`ClientProxy`看起来类似于列表 20.7。

**列表 20.7 带有新方法的`ClientProxySam`**

点击此处查看代码图像

***

```java
package com.wuppy.samsmod;

import net.minecraft.client.renderer.entity.RenderSnowball;
import cpw.mods.fml.client.registry.RenderingRegistry;

public class ClientProxySam extends CommonProxySam
{
    @Override
    public void registerRendering()
    {
            RenderingRegistry.registerEntityRenderingHandler(EntitySamMob.class, new RenderSamMob(new ModelSamMob(), 0.5F));
    }
    @Override
    public void registerItemRenders()
    {
            RenderingRegistry.registerEntityRenderingHandler(EntitySamThrowable.class, new RenderSnowball(SamsMod.samthrow));
    }
}
```

***

投掷物的`RenderingRegistry`已经添加。它接收两个参数：首先是将被渲染的`Entity`类，第二个是渲染该实体的`Render`类。在这种情况下，`Render`类是`RenderSnowball`，它需要一个参数，即它看起来像的物品。现在当你启动游戏并投出其中一个实体时，它将看起来是应有的样子。

投掷物品看起来应该像图 20.2。

![图像](img/image00645.jpeg)

**图 20.2** 游戏中的投掷物品。

图 20.3 显示了右键点击投掷物品时发生的情况，这会生成实体。

![图像](img/image00646.jpeg)

**图 20.3** 游戏中的投掷实体。

一旦图 20.3 中的实体接触地面，就会发生类似图 20.4 所示的情况。

![图像](img/image00647.jpeg)

**图 20.4** 结果。

### 总结

在本节中，你学习了如何创建投掷物。你学习了`Entity`类、如何使用`onRightClick`生成实体，最后如何进行渲染。你还学习了在 Minecraft 中添加物品，因此`onRightClick`等方法是非常重要的。

### 问答

**问：为什么使用`RenderSnowball`而不是自定义的？**

答：`RenderSnowball`已经按照它应有的方式渲染了。

**问：`RenderingRegistry`是如何工作的？**

答：它在客户端中处理渲染。

**问：如果你在服务器端添加了`RenderingRegistry`会发生什么？**

答：游戏会崩溃。

### 练习

在本节中，你学习了如何处理投掷物。

### 验

**问：为什么在服务器端要检查这一点？**

答：因为渲染是在客户端处理的。

**问：如果你添加了`RenderingRegistry`会发生什么？**

答：这会抛出空指针异常。

### 答案

修改`onRightClick`以让它不会生成：

```java
@Override
public ItemStack onItemRightClick(ItemStack par1ItemStack, World par2World, EntityPlayer par3Player)
{
    if (par3Player.capabilities.isCreative)
    {
        par1ItemStack.stackSize--;
    }
    if (!par2World.isRemote)
    {
        par2World.spawnEntityIn(SamThrowable);
    }
    return par1ItemStack;
}
```

`removeSpawn`是`EntityRegistry`中的一个方法，接受三个参数。第一个是必须移除的实体。第二个是该实体的类型，第三个是它必须被移除的生物群系（biome）。由于这段代码会遍历所有可能的生物群系，`EntityZombie`将从游戏中完全移除。如果你想修改僵尸的某些特性，这会非常有用。某些特性可以使用 Forge 事件进行编辑，但如果无法实现，你可以使用这段代码移除一个生物实体，然后在原来的位置添加你修改后的实体。

## 在不替换的情况下更改实体

在不需要将其替换为自定义实体的情况下更改实体行为的一个示例，是使用一个名为`LivingDropsEvent`的 Forge 事件，它可以让实体在死亡时掉落新的物品或方块。

在之前的一个小时节中，为世界生成创建了一个`EventHandler`。要将此类注册为调用此类事件的类，请在`preInit`方法的末尾添加以下行代码：

```java
MinecraftForge.EVENT_BUS.register(handler);
```

这使得处理器（一个`SamEventHandler`实例）能够与如`LivingDropsEvent`等事件进行交互。

在`SamEventHandler`类中，你可以添加如下所示的方法：

```java
@SubscribeEvent
public void addDrops(LivingDropsEvent event)
{

}
```

对于任何没有使用如`IWorldGenerator`接口实现的事件，上方都必须使用`@SubscribeEvent`。这些方法可以有任何方法名称，但始终只能有一个参数，即你想要使用的事件。在这种情况下，事件是`LivingDropsEvent`，它用于在僵尸死亡时掉落 Sam 的靴子（Sam’s Boots），但也可以用于任何类型的实体、物品或方块。

```java
@SubscribeEvent
public void addDrops(LivingDropsEvent event)
{
    if(event.entity instanceof EntityZombie)
        event.drops.add(new EntityItem(event.entity.worldObj, event.entity.posX, event.entity.posY, event.entity.posZ, new ItemStack(SamsMod.samboots)));
}
```

`LivingDropsEvent`有几个必须包含在此处的对象。首先，它有一个名为`entity`的对象，可以用于检查杀死的是哪种实体以及该实体所在的位置。`LivingDropsEvent`还有一个名为`drops`的对象，它是一个`EntityItem`数组，包含了实体对象死亡时应该掉落的物品和方块。要添加掉落物，使用`drops.add`。它需要一个参数：`EntityItem`。

`EntityItem`是一个接受五个参数的类：首先是世界，可以通过访问实体中的`worldObj`来传递。接下来的三个参数是`EntityItem`应掉落的位置。你可以通过实体对象中的`posX`、`posY`和`posZ`找到这些位置。最后一个参数是要掉落的物品的`ItemStack`。在这种情况下，新的`ItemStack`是 Sam 的靴子。

### 尝试一下：随机化掉落

将僵尸死亡时的掉落随机化。让它每 10 次才掉落一次 Sam 的靴子。再添加第二个随机掉落物，使其每 15 次掉落一次 Sam 的头盔（Sam’s Helmet）。你需要的`Random`对象可以在`World`中找到。

首先，在之前显示的代码中创建一个`if`语句。这个`if`语句应该包含`rand.nextInt(10)`，这意味着有 10 种选择。然后，应该检查它是否等于 0，使得该语句内的代码每 10 次运行一次。

接下来，在之前的`events.drops.add`行前添加一个制表符，确保这段代码位于你刚刚编写的`if`语句内。

现在，在你创建的那个`if`语句下方添加另一个`if`语句，但位于`instanceof EntityZombie`语句内部。这应该包含一个`rand.nextInt(15)`，使其发生的概率更低。

最后，复制`samboots`掉落的代码，将其粘贴到`if`语句中并将其改为`samhelmet`。

以下代码应为你的结果：



```java
@SubscribeEvent
public void addDrops(LivingDropsEvent event)
{
    if(event.entity instanceof EntityZombie)
        if(event.entity.worldObj.rand.nextInt(10) == 0)
            event.drops.add(new EntityItem(event.entity.worldObj, event.entity.posX, event.entity.posY, event.entity.posZ, new ItemStack(SamsMod.samboots)));
        if(event.entity.worldObj.rand.nextInt(15) == 0)
            event.drops.add(new EntityItem(event.entity.worldObj, event.entity.posX, event.entity.posY, event.entity.posZ, new ItemStack(SamsMod.samhelmet)));
}
```

整个`SamEventHandler`现在应该像列表 2.1 所示。

### 列表 2.1 带有 `LivingDropsEvent` 的 `SamEventHandler`

```java
package com.uppy.amsmod;
import java.util.Random;
import net.minecraft.block.Block;
import net.minecraft.entity.item.EntityItem;
import net.minecraft.entity.monster.EntityZombie;
import net.minecraft.init.Blocks;
import net.minecraft.item.ItemStack;
import net.minecraft.world.World;
import net.minecraft.world.chunk.IChunkProvider;
import net.minecraft.world.gen.feature.WorldGenable;
import net.minecraft.forge.event.entity.living.LivingDropsEvent;
import cpw.mods.fml.common.IWorldGenerator;
import cpw.mods.fml.common.event.SubscribeEvent;

public class SamEventHandler implements IWorldGenerator
{
    @SubscribeEvent
    public void addDrops(LivingDropsEvent event)
    {
        if(event.entity instanceof EntityZombie)
            if(event.entity.worldObj.rand.nextInt(10) == 0)
                event.drops.add(new EntityItem(event.entity.worldObj, event.entity.posX, event.entity.posY, event.entity.posZ, new ItemStack(SamsMod.samboots)));
            if(event.entity.worldObj.rand.nextInt(15) == 0)
                event.drops.add(new EntityItem(event.entity.worldObj, event.entity.posX, event.entity.posY, event.entity.posZ, new ItemStack(SamsMod.samhelmet)));
    }

    @Override
    public void generate(Random random, int chunkX, int chunkZ, World world, IChunkProvider chunkGenerator, IChunkProvider chunkProvider)
    {
        switch(world.provider.dimensionId)
        {
            case -1: generateNether(world, random, chunkX * 16, chunkZ * 16);
            case 0: generateSurface(world, random, chunkX * 16, chunkZ * 16);
            case 1: generateEnd(world, random, chunkX * 16, chunkZ * 16);
        }
    }

    private void generateEnd(World world, Random random, int x, int z)
    {
        addOreSpawn(SamsMod.samStone, 0, Blocks.obsidian, world, random, x, z, 16, 16, 5, 20);
    }

    private void generateSurface(World world, Random random, int x, int z)
    {
        addOreSpawn(SamsMod.samStone, 0, Blocks.stone, world, random, x, z, 16, 16, 5, 20);

        for(int i = 0; i < 3; i++)
        {
            int posX = x + random.nextInt(16);
            int posY = 50 + random.nextInt(35);
            int posZ = z + random.nextInt(16);
            new WorldGenSamPlant().generate(world, random, posX, posY, posZ);
        }

        int posX = x + random.nextInt(16);
        int posY = 10 + random.nextInt(40);
        int posZ = z + random.nextInt(16);
        new WorldGenSamDungeon().generate(world, random, posX, posY, posZ);
    }

    private void generateNether(World world, Random random, int x, int z)
    {
    }
}
```

```java
addOreSpawn(SamsMod.samStone, 0, Blocks.netherrack, world, random, x, z, 16, 16, 5 + random.nextInt(5), 4, 20, 60);
```

```java
/**
 * 在 Minecraft 中添加矿石生成点。只需在你扩展的 IWorldGeneration 类的生成方法中，使用此方法注册所有要生成的矿石。
 *
 * @param block 要生成的方块
 * @param metadata 方块的元数据
 * @param target 要生成的目标区块
 * @param world 要生成的世界
 * @param random 一个随机对象，用于在世界内获取随机位置以生成方块
 * @param int 用于传递生成方法 X 坐标的整数
 * @param int 用于传递生成方法 Z 坐标的整数
 * @param int 用于设置每个区块（Chunk）在 X 轴上生成的最大 X 坐标值
 * @param int 用于设置每个区块（Chunk）在 Z 轴上生成的最大 Z 坐标值
 * @param int 用于设置矿脉最大尺寸的整数
 * @param int 每个区块方块可生成的次数整数
 * @param int 该方块可能生成的最小 Y 坐标高度整数
 * @param int 该方块可能生成的最大 Y 坐标高度整数
 */
public void addOreSpawn(Block block, int metadata, Block target, World world, Random random, int blockXPos, int blockZPos, int maxX, int maxZ, int maxVeinSize, int chancesToSpawn, int minY, int maxY)
{
    int maxPossY = minY + (maxY - 1);

    assert maxY > minY: "最大 Y 必须大于最小 Y";
    assert maxX > 0 && maxX <= 16: "addOreSpawn: 最大 X 必须大于 0 且小于 16";
    assert minY > 0: "addOreSpawn: 最小 Y 必须大于 0";
    assert maxY < 256 && maxY > 0: "addOreSpawn: 最大 Y 必须小于 256 但大于 0";
    assert maxZ > 0 && maxZ <= 16: "addOreSpawn: 最大 Z 必须大于 0 且小于 16";

    int diffBtwnMinMaxY = maxY - minY;

    for(int x = 0; x < chancesToSpawn; x++)
    {
        int posX = blockXPos + random.nextInt(maxX);
        int posY = minY + random.nextInt(diffBtwnMinMaxY);
        int posZ = blockZPos + random.nextInt(maxZ);

        (new WorldGenMinable(block, metadata, maxVeinSize, target)).generate(world, random, posX, posY, posZ);
    }
}
```

### 编辑方块掉落

添加新的方块掉落的方法与添加新的实体掉落非常相似。所需的事件名为`HarvestDropsEvent`，它位于`BlockEvent`内部。为 Minecraft 中的红花添加 Sam 浆果（Sam’s Berries）掉落的方法如下：

```java
@SubscribeEvent
public void addBlockDrops(BlockEvent.HarvestDropsEvent event)
{
    if(event.block == Blocks.red_flower)
        event.drops.add(new ItemStack(SamsMod.berry));
}
```

与`LivingDropsEvent`不同，`HarvestDropsEvent`拥有一个`ItemStack`的掉落`ArrayList`，这使得比为实体向方块添加掉落容易得多。

### 其他事件

现在你已经看到了代码中使用的两个事件。然而，在 Forge 和 Forge Mod Loader (FML) 的事件包中还可以找到更多事件，它们的工作原理都与此类似。Forge 中的每个事件工作方式如下：

- 你需要一个可以使用任意名称的方法。
- 该方法上方需要有`@SubscribeEvent`注解。
- 唯一允许的参数是你想要使用的事件。
- 该方法所在的类必须被注册为`Event`类。

如果你正在使用 Forge 事件，必须像之前所示对其进行注册，例如：

```java
MinecraftForge.EVENT_BUS.register(handler);
```

如果你想用 FML 事件，请按如下方式注册处理程序：

```java
FMLCommonHandler.instance().bus().register(handler);
```

#### 注意：`EventHandler` 注册

同一个`EventHandler`可以同时被注册为 FML 和 Forge 事件类。你不需要为它准备两个不同的类。

事件还可以用于改变掉落之外的许多其他事情。可以完全重写某些结构的生成方式，改变 Minecraft 中食物的运作方式，以及许多其他示例——这一切都无需编辑任何类文件。

### 赋予你的护甲投掷能力

利用事件可以做的另一个有趣事情是：让玩家在穿着全套盔甲时空手右键点击扔蛋。此功能将会添加。要实现这一点，请使用一个名为`PlayerInteractEvent`的事件。该事件位于 fml 文件夹中，这意味着该事件类必须像之前所示使用 FML 的`EVENT_BUS`进行注册。

`SamEventHandler`内部的方法如下：

```java
@SubscribeEvent
public void throwEggs(PlayerInteractEvent event)
{
}
```

在该方法内部，你必须在扔蛋之前检查几件事。该方法中的代码逻辑应该如下所示：

1. 玩家正在点击右键吗？
2. 玩家手空的吗？
3. 玩家穿了正确的盔甲吗？
4. 扔蛋。

首先，你可以使用事件内部的`action`变量检查右键点击。进入`PlayerInteractEvent`，你会看到三种可能的动作：`RIGHT_CLICK_AIR`、`RIGHT_CLICK_BLOCK`和`LEFT_CLICK_BLOCK`。为了确保只有在右键点击时才扔蛋，它必须是右键点击动作之一。你可以通过向方法添加以下`if`语句来实现：

```java
@SubscribeEvent
public void throwEggs(PlayerInteractEvent event)
{
    if (event.action == PlayerInteractEvent.Action.RIGHT_CLICK_AIR || event.action == PlayerInteractEvent.Action.RIGHT_CLICK_BLOCK)
    {
    }
}
```

现在你需要进行第二次检查，确保玩家手中没有物品。要执行这一点，你需要访问`EntityPlayer`。幸运的是，事件拥有这个变量。`EntityPlayer`中有一个名为`getCurrentEquippedItem`的方法，它返回玩家持有的物品或`null`。因为你不希望玩家在执行此操作时持有任何物品，所以当前装备物品必须为`null`，你可以使用以下`if`语句进行检查：

```java
@SubscribeEvent
public void throwEggs(PlayerInteractEvent event)
{
    if (event.action == PlayerInteractEvent.Action.RIGHT_CLICK_AIR || event.action == PlayerInteractEvent.Action.RIGHT_CLICK_BLOCK)
    {
        if (event.entityPlayer.getCurrentEquippedItem() == null)
        {
        }
    }
}
```

现在你必须实际检查从`getCurrentArmor`返回的项。你可以通过几种方法来实现。你可以检查返回的项是否与任何盔甲部件相同。然而，你也可以使用 Java 中现有的名为`instanceof`特性让这变得好得多。`instanceof`是 Java 的一个运算符，用于检查操作符前的对象是否是操作符后类的实例（也就是说，如果它扩展了该类）。由于 Sam 盔甲套组中的所有物品都是在`ItemSamArmor`中制作的，你可以使用以下检查：

点击此处查看代码图片

```java
if (event.entityPlayer.getCurrentArmor(i).getItem() instanceof ItemSamArmor)
{
}
```

但是，该项也有可能是`null`。如果发生这种情况，该方法会导致你的游戏崩溃。这将非常糟糕，因为这段代码会在玩家右键点击时运行——这意味着玩家将无法玩游戏。为了防止这种崩溃，必须在检查当前盔甲不为`null`之后运行这段代码。它看起来应该是这样：

点击此处查看代码图片

```java
if (event.entityPlayer.getCurrentArmor(i) == null)
{
    return;
}
else if (event.entityPlayer.getCurrentArmor(i).getItem() instanceof ItemSamArmor)
{
}
```

现在必须创建一个`boolean`变量，用于保存是否穿了全套盔甲的信息。

这可能相当困难，因为如果单件盔甲是 Sam 的盔甲，就不应该将其设置为`true`。每一件物品都必须是 Sam 盔甲的一部分。否则，不应该生成蛋。有几种方法可以实现这一点，以下代码是可能的解决方案之一：

点击此处查看代码图片

```java
boolean fullSuit = true;

for (int i = 0; i < 4; i++)
{
```



`if (event.entityPlayer.getCurrentArmor(i) == null)`

```
{
    fullSuit = false;
    return;
}
else if (!(event.entityPlayer.getCurrentArmor(i).getItem() instanceof ItemSamArmor))
{
    fullSuit = false;
}
```

该 `boolean` 初始化为 `true`。然后它像之前所示，遍历每一件盔甲部件。如果任何一个盔甲部件是空的，它就会变为 `false`。如果任何物品不是 `ItemSamArmor` 的实例，注意语句周围的感叹号；它也会变为 `false`。

现在，只有当玩家穿着全套盔甲时，`boolean fullSuit` 才为 `true`，这意味着可以使用以下代码生成蛋：

点击此处查看代码图片

```java
if (fullSuit)
{
    event.entityPlayer.worldObj.spawnEntityInWorld(new EntityEgg(event.entityPlayer.worldObj, event.entityPlayer));
}
```

整个 `PlayerInteractEvent` 方法现在看起来应该像列表 21.2。

**列表 21.2 全套蛋的投掷代码**

点击此处查看代码图片

```java
@SubscribeEvent
public void throwEggs(PlayerInteractEvent event)
{
    if (event.action == PlayerInteractEvent.Action.RIGHT_CLICK_AIR || event.action == PlayerInteractEvent.Action.RIGHT_CLICK_BLOCK)
    {
        if (event.entityPlayer.getCurrentEquippedItem() == null)
        {
            boolean fullSuit = true;
            for (int i = 0; i < 4; i++)
            {
                if (event.entityPlayer.getCurrentArmor(i) == null)
                {
                    fullSuit = false;
                    return;
                }
                else if (!(event.entityPlayer.getCurrentArmor(i).getItem() instanceof ItemSamArmor))
                {
                    fullSuit = false;
                }
            }
        }
        if (fullSuit)
        {
            event.entityPlayer.worldObj.spawnEntityInWorld(new EntityEgg(event.entityPlayer.worldObj, event.entityPlayer));
        }
    }
}
```

现在，当你右键点击并满足所有要求时，玩家会投出一个蛋，如图 21.1 所示。

![Image](img/image00648.jpeg)

**图 21.1** 玩家穿着全盔甲投掷蛋。

### 总结

在这一小时中，你学习了如何间接地修改 Minecraft。你可以通过这些方式实现，例如从游戏中移除实体或使用事件、反射和字节码操作来修改某些功能。你还学习了如何实现前两种。你可以通过移除每个自然生成点来轻松移除实体。你可以在注册在 `EVENT_BUS` 中的类中使用事件。它们很容易使用，而且通过它们可以做很多事情。

### 问答

**问. 为什么要避免直接修改 Minecraft 类？**

**答. 这增加了与其他 mod 的兼容性。当两个 mod 修改同一个类时，很可能会导致崩溃。使用事件，这个问题就完全解决了。**

**问. 订阅的事件数量有限制吗？**

**答. 没有，但如果你添加得太多，游戏会变慢。**

**问. 可以对同一个事件进行多次订阅吗？**

**答. 可以，但如果你在同一个 mod 中有，最好将它们放在同一个方法里。**

### 工作坊

在这一小时中，你学习了间接修改 Minecraft。这对 mod 开发非常重要，请通过完成以下测验来确保你理解了它们。

### 测验

**问. `LivingDropsEvent` 和 `HarvestDropEvent` 中的 `ArrayList` 有什么区别？**

**问. 如果你不将 `Event` 类注册到 `EVENT_BUS` 会发生什么？**

### 答案

**答. `LivingDropsEvent` 需要 `EntityItems`，而 `HarvestDropEvent` 需要 `ItemStack`。**

**答. 什么都不会发生。所有订阅的事件都不会运行。**

### 练习

使用 `LivingEvent` 中的 `LivingJumpEvent` 事件，在实体跳跃时打印出“jump”。

以下代码可以实现这一点：

点击此处查看代码图片

```java
@SubscribeEvent
public void printJump(LivingEvent.LivingJumpEvent event)
{
    System.out.println("jump");
}
```

这个方法看起来可能没用，但如果你检查玩家跳跃，然后检查玩家是否穿着特定类型的靴子，这个方法就可以用于，例如在跳跃时治疗玩家。

构建你的 Mod 并借此清理代码是非常用的。它们能通过让代码更易读来帮助你。当代码更易读时，添加新功能会变得容易得多。当出现 bug 或需要更新时，也能让你更容易找到错误所在的位置。此外，如果你让你的 Mod 开源（这通常是个好主意），也能帮助他人，因为他们可以轻松理解你的代码，并可能帮助你更新或修复其中的某些部分。

## 如何构建你的 Mod

你已经采取了一些操作来构建你的 Mod，并使其更容易易读和发现 bug。例如，在你的 Mod 文件中对所有的方块和物品变量分组，并为每个方法添加 `@Override`。然而，要让它看起来真正整洁，还需要更多的操作。

### 清理包（Package）

当你查看包中的类时，它看起来应该类似于图 22.1。

![Image](img/image0064.jpeg)

**图 22.1** 包中的类。

这看起来完全没有组织性。为了让它看起来更好，可以创建子包。一些常用的子包有 `blocks`、`items`、`generation` 和 `render`。在完全清理之后，包列表看起来类似于图 22.2。

![Image](img/image00650.jpeg)

**图 22.2** 在子包中整理的类。

此处的所有内容都是可选的。例如，包的数量、名称以及每个包中的文件对每个人来说都可以不同。这实际上取决于你的个人偏好。然而，建议的这种方法如图 22.2 所示。你可以通过将文件从一个包拖到另一个包来移动文件。

通常情况下，一个包中的类数量至少为三个，因为为每个类创建一个子包只会让代码阅读变得更加困难。

**注意：更改代理（Proxies）**

当你更改任一个代理的包名或文件名时，你必须更改 Mod 文件中的 `@SidedProxy` 行，以确保它们仍然能被找到。对于这个 Mod，该行代码现在应该像这样：

点击此处查看代码图像

```java
@SidedProxy(clientSide = "com.wuppy.samsmod.proxies.ClientProxySam", serverSide = "com.wuppy.samsmod.proxies.CommonProxySam")
```

另一个需要注意的是，有一个名为 `items.tools` 的包。这意味着子包 `items` 有另一个名为 `tools` 的子包。在这种情况下，这是很有用的，因为有很多不同的工具，这样它们也得到了适当的组织。

**注意：文件夹中的包**

包在你的系统中由文件夹表示。到目前为止，所有编写的代码都位于 `com/wuppy/samsmod` 文件夹（或你的包名）。添加所有这些子包也意味着 `samsmod` 文件夹中现在会有几个文件夹。

### 清理 Mod 类

在本书中，Mod 类几乎每小时都有新代码。即使你保持该类尽可能整洁，它看起来仍然会非常拥挤，并且变得越来越难以阅读。如果你保持该类合理的整洁，它看起来应该类似于代码列表 22.1。

**代码列表 22.1 SamsMod 类**

点击此处查看代码图像

```java
package com.wuppy.samsmod;

import net.minecraft.block.Block;
import net.minecraft.enchantment.Enchantment;
import net.minecraft.entity.Entity;
import net.minecraft.entity.EntityList;
import net.minecraft.entity.EntityList.EntityEggInfo;
import net.minecraft.entity.EnumCreatureType;
import net.minecraft.init.Blocks;
import net.minecraft.init.Items;
import net.minecraft.item.Item;
import net.minecraft.item.Item.ToolMaterial;
import net.minecraft.item.ItemArmor.ArmorMaterial;
import net.minecraft.item.ItemStack;
import net.minecraft.util.WeightedRandomChestContent;
import net.minecraft.world.biome.BiomeGenBase;
import net.minecraftforge.common.ChestGenHooks;
import net.minecraftforge.common.DungeonHooks;
import net.minecraftforge.common.MinecraftForge;
import net.minecraftforge.common.util.EnumHelper;
import com.wuppy.samsmod.blocks.BlockSamPlant;
import com.wuppy.samsmod.blocks.BlockSamStone;
import com.wuppy.samsmod.blocks.BlockSamTE;
import com.wuppy.samsmod.entity.EntitySamMob;
import com.wuppy.samsmod.entity.EntitySamThrowable;
import com.wuppy.samsmod.handlers.SamEventHandler;
import com.wuppy.samsmod.items.ItemBerry;
import com.wuppy.samsmod.items.ItemKey;
import com.wuppy.samsmod.items.ItemSamArmor;
import com.wuppy.samsmod.items.ItemGeneric;
import com.wuppy.samsmod.items.ItemSeed;
import com.wuppy.samsmod.items.ItemSamStone;
import com.wuppy.samsmod.items.ItemThrow;
import com.wuppy.samsmod.items.tools.ItemSamAxe;
import com.wuppy.samsmod.items.tools.ItemSamHoe;
import com.wuppy.samsmod.items.tools.ItemSamPaxel;
import com.wuppy.samsmod.items.tools.ItemSamPickaxe;
import com.wuppy.samsmod.items.tools.ItemSamShovel;
import com.wuppy.samsmod.items.tools.ItemSamSpax;
import com.wuppy.samsmod.items.tools.ItemSamSword;
import com.wuppy.samsmod.proxies.CommonProxySam;
import com.wuppy.samsmod.tile_entities.TileEntitySam;
import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.EventHandler;
import cpw.mods.fml.common.SidedProxy;
import cpw.mods.fml.common.event.FMLInitializationEvent;
import cpw.mods.fml.common.registry.BlockRegistry;
import cpw.mods.fml.common.registry.EntityRegistry;
import cpw.mods.fml.common.registry.ItemRegistry;
import cpw.mods.fml.common.registry.TileEntityRegistry;

@Mod(modid = SamsMod.MODID, version = SamsMod.VERSION)
public class SamsMod
{
    public static final String MODID = "samsmod";
    public static final String VERSION = "1.0";

    // 方块
    public static Block samStone;
    public static Block samPlant;
    public static Block samTE;

    // 物品
    public static Item key;
    public static Item berry;
    public static Item samseed;
    public static Item samdust;
    public static Item sining;
    public static Item samthrow;

    // 工具
    public static Item sampickaxe;
    public static Item samaxe;
    public static Item samhoe;
    public static Item samshovel;
    public static Item samsword;
    public static Item sampaxel;
    public static Item samspax;
    public ToolMaterial samium = EnumHelper.addToolMaterial("samium", 1000, 9.5F, 3.5F);

    // 铠甲
    public static Item samhelmet;
    public static Item samchest;
    public static Item samleggings;
    public static Item samboots;
    public ArmorMaterial samarmor = EnumHelper.addArmorMaterial("samarmor", 20, new int[] { 3, 7, 6, 3 }, 10);

    SamEventHandler handler = new SamEventHandler();

    @SidedProxy(clientSide = "com.wuppy.samsmod.proxies.ClientProxySam", serverSide = "com.wuppy.samsmod.proxies.CommonProxySam")
    public static CommonProxySam proxy;

    @EventHandler
    public void preInit(FMLInitializationEvent event)
    {
        proxy.registerRendering();

        // 方块初始化
        samStone = new BlockSamStone();
        samPlant = new BlockSamPlant();
        samTE = new BlockSamTE();
        BlockRegistry.registerBlock(samStone, "SamStone");
```



`BlockRegistry.registerBlock(samPlant, "SamPlant");`

`BlockRegistry.registerBlock(samTE, "SamTE");`

`TileEntityRegistry.registerTileEntity(TileEntitySam.class, "TE_samTE");`

// 物品初始化

`key = new ItemKey();`

`berry = new ItemBerry(3, 0.3F, true, "berry");`

`samseed = new ItemSamSeed(samPlant);`

`samdust = new ItemSamGeneric("samdust");`

`sining = new ItemSamGeneric("sining");`

`samthrow = new ItemSamThrow("samthrow");`

`ItemRegistry.registerItem(key, "key");`

`ItemRegistry.registerItem(berry, "berry");`

`ItemRegistry.registerItem(samseed, "samseed");`

`ItemRegistry.registerItem(samdust, "samdust");`

`ItemRegistry.registerItem(sining, "sining");`

`ItemRegistry.registerItem(samthrow, "samthrow");`

// 工具初始化

`sampickaxe = new ItemSamPickaxe(samium, "sampickaxe");`

`samaxe = new ItemSamAxe(samium, "samaxe");`

`samhoe = new ItemSamHoe(samium, "samhoe");`

`samshovel = new ItemSamShovel(samium, "samshovel");`

`samsword = new ItemSamSword(samium, "samsword");`

`sampaxel = new ItemSamPaxel(samium, "sampaxel");`

`samspax = new ItemSamSpax(samium, "samspax");`

`ItemRegistry.registerItem(sampickaxe, "sampickaxe");`

`ItemRegistry.registerItem(samaxe, "samaxe");`

`ItemRegistry.registerItem(samhoe, "samhoe");`

`ItemRegistry.registerItem(samshovel, "samshovel");`

`ItemRegistry.registerItem(samsword, "samsword");`

`ItemRegistry.registerItem(sampaxel, "sampaxel");`

`ItemRegistry.registerItem(samspax, "samspax");`

```
samshovel = new ItemSamShovel(samium, "samshovel");
samsword = new ItemSamSword(samium, "samsword");
sampaxel = new ItemSamPaxel(samium, "sampaxel");
samspax = new ItemSamSpax(samium, "samspax");
```

//armor

`samhelmet = new ItemSamArmor(samarmor, 0, "samhelmet");`

`samchest = new ItemSamArmor(samarmor, 1, "samchestplate");`

`samleggings = new ItemSamArmor(samarmor, 2, "samleggings");`

`samboots = new ItemSamArmor(samarmor, 3, "samboots");`

//Item registry

`GameRegistry.registerItem(key, "Key");`

`GameRegistry.registerItem(berry, "Berry");`

`GameRegistry.registerItem(samseed, "SamSeed");`

`GameRegistry.registerItem(samdust, "SamDust");`

`GameRegistry.registerItem(samingot, "SamIngot");`

`GameRegistry.registerItem(samthrow, "SamThrowable");`

//tools

`GameRegistry.registerItem(sampickaxe, "SamPickaxe");`

`GameRegistry.registerItem(samaxe, "SamsAxe");`

`GameRegistry.registerItem(samhoe, "SamsHoe");`

`GameRegistry.registerItem(samshovel, "SamsShovel");`

`GameRegistry.registerItem(samsword, "SamsSword");`

`GameRegistry.registerItem(sampaxel, "SamsPaxel");`

`GameRegistry.registerItem(samspax, "SamsSpax");`

//armor

`GameRegistry.registerItem(samhelmet, "SamsHelmet");`

`GameRegistry.registerItem(samchest, "SamsChest");`

`GameRegistry.registerItem(samleggings, "SamsLeggings");`

`GameRegistry.registerItem(samboots, "SamsBoots");`

`proxy.registerItemRenders();`

`EntityRegistry.registerModEntity(EntitySamMob.class, "sammob", 0, this, 80, 3, true);`

`EntityRegistry.registerModEntity(EntitySamThrowable.class, "samthrow", 1, this, 80, 3, true);`

```
for (int i = 0; i < BiomeGenBase.getBiomeGenArray().length; i++)
{
    if (BiomeGenBase.getBiomeGenArray()[i] != null)
    {
        EntityRegistry.addSpawn(EntitySamMob.class, 0, 1, 3, EnumCreatureType.monster, BiomeGenBase.getBiomeGenArray()[i]);
    }
}
```

`registerEgg(EntitySamMob.class, 0xd8bb9d, 0xa63c1a);`

`GameRegistry.registerGenerator(handler, 0);`

`MinecraftForge.EVENT_BUS.register(handler);`

```
@EventHandler
public void init(FMLInitializationEvent event)
{
```

//Recipes

`GameRegistry.addRecipe(new ItemStack(Items.apple), "XXX", "XXX", "XXX", 'X', Blocks.leaves);`

`GameRegistry.addRecipe(new ItemStack(Items.arrow), "YZ", "X ", 'X', Items.flint, 'Y', Items.stick, 'Z', Blocks.leaves);`

`GameRegistry.addShapelessRecipe(new ItemStack(Items.dye, 2, 1), Items.redstone, new ItemStack(Items.dye, 1, 1));`

`GameRegistry.addSmelting(Blocks.stone, new ItemStack(Blocks.stonebrick), 0.1F);`

`ItemStack enchantedSwordItemStack = new ItemStack(Items.stone_sword);`

`enchantedSwordItemStack.addEnchantment(Enchantment.sharpness, 1);`

`GameRegistry.addShapelessRecipe(enchantedSwordItemStack, Items.flint, Items.stone_sword);`

//Dungeon changes

`DungeonHooks.removeDungeonMob("Spider");`

`DungeonHooks.addDungeonMob("Creeper", 100);`

`ChestGenHooks.removeItem(ChestGenHooks.DUNGEON_CHEST, new ItemStack(Items.saddle));`

`ChestGenHooks.addItem(ChestGenHooks.DUNGEON_CHEST, new WeightedRandomChestContent(new ItemStack(Blocks.cobblestone), 25, 50, 10));`

```
}
```

`static int startEntityId = 300;`

```
@SuppressWarnings("unchecked")
public static void registerEntityEgg(Class<? extends Entity> entity, int primaryColor, int secondaryColor)
{
    int id = getUniqueEntityId();
    EntityList.IDToMapping.put(id, entity);
    EntityList.entityEggs.put(id, new EntityEgg(id, primaryColor, secondaryColor));
}

public static int getUniqueEntityId()
{
    do
    {
        startEntityId++;
    } while (EntityList.getStringFromID(startEntityId) != null);
    return startEntityId;
}
```

清理这个庞大文件的简单方法是将其拆分成若干部分。这通常通过名为 `ModBlocks`、`ModItems` 等类来实现。对于 `SamsMod`，`ModBlocks` 如列表 22.2 所示。

### 列表 22.2 SamsMod 的 ModBlocks

```java
package com.wuppy.samsmod.blocks;

import com.wuppy.samsmod.items.ItemSamStone;
import cpw.mods.fml.common.registry.GameRegistry;
import net.minecraft.block.Block;

public class ModBlocks
{
    public static Block samStone;
    public static Block samPlant;
    public static Block samTE;

    public static void loadBlocks()
    {
        samStone = new BlockSamStone();
        samPlant = new BlockSamPlant();
        samTE = new BlockSamTE();
        GameRegistry.registerBlock(samStone, "SamStone");
        GameRegistry.registerBlock(samPlant, "SamPlant");
        GameRegistry.registerBlock(samTE, "SamTE");
    }
}
```

你应该从该类中移除该代码。取而代之，在该类中添加以下行：
`ModBlocks.loadBlocks();`

当你这样做时，对对象的引用就会失效。例如代码尝试在 `SamsMod` 类中引用 `samStone`，但那里并没有。相反，它在 `ModBlocks` 中。这意味着在你的模块中引用对象的地方，都应该改为 `ModBlocks`。一个例子是 `ItemSamSeed` 的初始化行：

```java
samseed = new ItemSamSeed(samPlant);
```

这尝试在 `SamsMod` 中访问 `samPlant`，那里已不存在了。将代码改为：

将移动到 `ModBlocks`、`ModItems` 等类中的所有代码后，代码中的某些内容可能需要更改。例如，在 `ModItems` 中，护甲和工具必须是静态的，而 `ModEntities` 需要传递类来注册实体。具体代码可以在本书的示例文件中找到（有关如何访问文件的信息）。

清理完成后，`SamsMod` 如列表 22.3 所示。

### 列表 22.3 清理后的 SamsMod

```java
package com.wuppy.samsmod;

import net.minecraft.init.Blocks;
import net.minecraft.init.Items;
import net.minecraft.item.ItemStack;
import net.minecraft.util.WeightedRandomChestContent;
import net.minecraftforge.common.ChestGenHooks;
import net.minecraftforge.common.DungeonHooks;
import net.minecraftforge.common.MinecraftForge;
import com.wuppy.samsmod.blocks.ModBlocks;
import com.wuppy.samsmod.entity.ModEntities;
import com.wuppy.samsmod.handlers.RecipeHandler;
import com.wuppy.samsmod.handlers.SamEventHandler;
import com.wuppy.samsmod.items.ModItems;
import com.wuppy.samsmod.proxies.CommonProxy;
import com.wuppy.samsmod.tileentities.TileEntitySam;
import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.EventHandler;
import cpw.mods.fml.common.SidedProxy;
import cpw.mods.fml.common.event.FMLInitializationEvent;
import cpw.mods.fml.common.event.FMLPreInitializationEvent;
import cpw.mods.fml.common.registry.GameRegistry;

@Mod(modid = SamsMod.MODID, version = SamsMod.VERSION)
public class SamsMod
{
```

```java
    public static final String MODID = "wuppy29_samsmod";
    public static final String VERSION = "1.0";
    SamEventHandler handler = new SamEventHandler();

    @SidedProxy(clientSide = "com.wuppy.samsmod.proxies.ClientProxySam", serverSide = "com.wuppy.samsmod.proxies.CommonProxySam")
    public static CommonProxySam proxy;

    @EventHandler
    public void preInit(FMLPreInitializationEvent event)
    {
        proxy.registerRendering();
```



```java
ModBlocks.loadBlocks();

GameRegistry.registerTileEntity(TileEntitySam.class, "TE_samTE");

ModItems.loadItems();

proxy.registerItemRenders();

ModEntities.loadEntities(this);

GameRegistry.registerWorldGenerator(handler, 0);

MinecraftForge.EVENT_BUS.register(handler);
}

@EventHandler
public void init(FMLInitializationEvent event)
{
    RecipeHandler.registerRecipes();

    //Dungeon changes

    DungeonHooks.removeDungeonMob("Spider");

    DungeonHooks.addDungeonMob("Creeper", 100);

    ChestGenHooks.removeItem(ChestGenHooks.DUNGEON_CHEST, new ItemStack(Items.saddle));

    ChestGenHooks.addItem(ChestGenHooks.DUNGEON_CHEST, new WeightedRandomChestContent(new ItemStack(Blocks.cobblestone), 25, 50, 10));
}
}
```

正如你所看到的，并不是每一行代码现在都放在不同的类中。这一小时内完成的所有工作都是为了提高代码的可读性；添加许多只有几行代码的类并不能提高可读性。

### 总结

在这一小时中，你学习了为什么清理你的模组很重要。之后，你学到了可以通过为某些类型的类创建子包来实现这一点。这使得代码更易读，因为你正在寻找的代码被归类在一起了。此外，通过创建多个类来承担目前已经变得庞大的模组主类的工作，你的代码也可以因此变得更易读。

### 问答

**Q. 将模组类的所有内容拆分到不同的 `init` 类中是一个好主意吗？**

**A.** 不会。如果你这样做，初始版本会更易读。

**Q. 模组可以有的子包数量有上限吗？**

**A.** 没有，但如果太多了，会让模组变得更难读。

### 工作坊

在这一小时中，你学习了如何让你的模组更易于读，从而更容易编写代码。这很重要，因为可以提高模组的生产力和准确性。通过测验测试你的理解程度。

### 测验

**1. 一个包中合理的类数量是多少个？**

**2. 为什么创建子包并将模组类拆分到其他类中如此有用？**

### 答案

**1.** 至少两个是一个好主意，但对此没有准确的规则。

**2.** 这让你自己读起来更费力。这直接加快了开发速度并减少了 Bug 的产生。此外，如果你将其开源（在下一小时会涵盖），它也能通过让其他人更容易读懂来帮助他们。

### 练习题

如果你还没有这样做，请遵循这一小时的指令来结构化你的模组。

## 第 23 小时：发布你的模组

你这一小时将学到：

- ![Image](img/image00525.jpeg) 导出你的模组
- ![Image](img/image00525.jpeg) 制作你的模组

你的模组现在准备好发布了，这样其他人就可以使用。然而，在用户可以使用该模组之前，还需要完成几项工作。首先，你必须将 Eclipse 中的代码转换为 Minecraft 可以使用的计算机代码，而无需集成开发环境 (IDE) 的帮助。接下来，你必须添加一个 `mcmod.info` 文件为用户提供信息。最后，确保用户能够找到这个模组是一个好主意。

### 导出你的模组

使用 Forge 导出你的模组，请打开安装 Forge 的文件夹。确保你在包含 `gradlew` 文件的文件夹中。现在打开命令提示符或终端并运行以下命令：

```bash
gradlew build
```

这将你的人类可读的 `.java` 文件转换为 `.class` 文件。`.class` 文件人类不可读，但电脑可以读取。这些类被用在 Minecraft 中。该命令大约需要一分钟，此时会生成一个名为 `build` 的新文件夹。在 `build` 内部，有许多不同的文件夹，其中一个叫做 `libs`。打开 `libs` 文件夹，然后打开 `modid-1.0.jar` 文件。

为了让你的模组能够被识别，你需要修改 `.jar` 文件内部的 `mcmod.info` 文件。

为了让你的模组显示正确，你需要修改 `mcmod.info` 文件中的字段。

这是 `mcmod.info` 文件的结构：

```json
{
  "modid": "你的 ModID",
  "name": "模组名称",
  "description": "模组描述",
  "version": "版本号",
  "mcversion": "Minecraft 版本",
  "url": "项目网址",
  "updateUrl": "更新地址",
  "authors": ["作者名"],
  "credits": "致谢",
  "logoFile": "图标文件名",
  "screenshots": [],
  "dependencies": []
}
```

每个字段的含义如下：

- `modid`：模组的唯一标识，必须与代码中的 `MODID` 一致。
- `name`：模组在游戏中显示的名称。
- `description`：模组的简短描述。
- `version`：模组的版本号。
- `mcversion`：模组支持的 Minecraft 版本。
- `url`：模组的项目页面或下载地址（可选）。
- `updateUrl`：更新检查地址（可选）。
- `authors`：作者姓名列表。
- `credits`：致谢信息。
- `logoFile`：模组图标的文件名（放在 `assets` 文件夹下）。
- `screenshots`：截图文件名列表。
- `dependencies`：依赖项列表。

### 创建 `mcmod.info` 文件

最后，有一个 `mcmod.info` 文件，它是示例 1 的默认值。你需要将其中的内容替换为你自己的信息。

```json
{
  "modid": "examplemod",
  "name": "Example Mod",
  "description": "这是一个示例模组。",
  "version": "1.0",
  "mcversion": "1.12.2",
  "url": "",
  "updateUrl": "",
  "authors": ["ExampleAuthor"],
  "credits": "Example Credits",
  "logoFile": "",
  "screenshots": [],
  "dependencies": []
}
```

将此文件保存为 `mcmod.info` 并放在你的 `.jar` 根目录下。这样，你的模组就会出现在 Minecraft 的模组列表中。

现在你的 mod 准备好发布了。唯一需要做的就是更改 `.jar` 文件的名称。最初，它的名称是 `modid-1.0.jar`。推荐的保存此类文件的格式是 `[Mod 名称]-[Minecraft 版本]-[Mod 版本]`。对于 Sam’s Mod 的首次发布，文件将命名为 `Sams Mod-1.7.10-1.0.jar`。

到此时，你可以做两件事。第一种也是最快的方法是立即开始将你的 mod 发布到各种常用的网站上。另一种选择是在发布之前先让别人给你的 mod 提供意见。这对你很有帮助，因为用户可能会发现漏洞，或者对你 mod 中的某些功能提供评论或建议。如果你不认识玩模组版 Minecraft 的朋友，你也可以互联网中继聊天（IRC）上询问，这是一种在线聊天程序。第 24 小节、“下一步](#part0040.xhtml_ch24)”向你展示了如何连接到它。一些实用的频道有 `#Direwolf20` 和 `#FTB`。不过，获取第二意见并不是要求的。

### 上传到最常用的网站

你应该发布 mod 的第一个、也是最重要的网站，应该是你在玩 Minecraft 时很可能已经访问过的网站。这个网站叫做 `minecraftforum.net`。只需创建一个账户并在以下子论坛发布你的 mod 即可：[www.minecraftforum.net/forum/51-minecraft-mods/](http://www.minecraftforum.net/forum/51-minecraft-mods/)。这是很多人寻找新 Minecraft mod 的地方，也是让你的 mod 传出去起点。

在标题中放入 mod 的名称是一个好主意。在帖子正文中，明智的做法是提到 mod 的思路、提供一些外观图片并并出一个下载链接。你可以将你的 mod 上传到几乎任何文件托管服务，例如 [dropbox.com](http://dropbox.com)。许多人喜欢的另外一点是你的 mod 是开源的。就像本小时的其他所有内容一样，这并不是强制要求的，但仍然建议。提供源代码最常用的方法是在 GitHub 上创建一个仓库。

### 设置 GitHub 仓库

要设置 GitHub 仓库，你必须首先在电脑上安装 GitHub。你可以使用 Windows 版 GitHub 应用程序 ([`windows.github.com/`](https://windows.github.com/)) 或 Mac 版 ([`mac.github.com/`](https://mac.github.com/))。或者，你可以安装 `Git`，它可以在每个系统上运行。这是一个类似于命令行程序，可以像 GitHub 应用程序一样使用，但它要求你手动编写命令，并且没有带有良好的界面。你可以在 [`help.github.com/articles/set-up-git#platform-all`](https://help.github.com/articles/set-up-git#platform-all) 找到如何设置 `Git`。

一旦设置好 `Git`，你就必须设置一个仓库，你可以按照 [`help.github.com/articles/create-a-repo`](https://help.github.com/articles/create-a-repo) 上的说明轻松完成。（仓库是一个通常所有人都可以访问的在线源码仓库。）

接下来，你需要将代码获取到你的 GitHub 仓库中。你可以直接上传整个 `forge` 文件夹，但那是不法的。相反，你应该只上传源代码和资源。你可以通过编写一个详尽的 `.gitignore` 文件，或者为你的 GitHub 仓库本地副本创建一个不同的文件夹并将正确的文件夹手动复制进去。你可以在带有 Minecraft 源码的 GitHub 仓库示例中找到 [`github.com/wuppy29/WuppyMods`](https://github.com/wuppy29/WuppyMods)。

### 其他网站

除了最知名的网站外，还有一些常用的网站，你可能想在那里添加你的 mod。

### 将你的 mod 添加到 `modlist.mcf.li`

`modlist.mcf.li` 是一个正如其名一样包含 mod 列表的网站。它做的并不多，只是提供一个 mod 列表，并附上获取它们的链接以及一些基础信息（如 Minecraft 版本、名称和描述），但它是获得更多曝光的一种不错方法。想要获取额外 mod 的人经常访问这个 mod 列表。该网站还有一个包含 Android 应用程序，其中包含了网站上的所有内容。

### 使用 Planet Minecraft

[planetminecraft.com](http://planetminecraft.com) 与 Minecraft 论坛非常相似，但它更侧重于展示创作，例如供玩家使用的 mod 和地图，它的它更不像一个论坛。

### 更多网站

显然，有很多不同的网站可以让你发布 mod。然而，在本小时内涵盖所有这些网站是不可能的，也有点没意义。之前的几个是最常用的，因此它们也是最重要的。你不应该把你的 mod 发布在太多的网站上。

### 总结

在本小时中，你学习了如何导出你的 mod。接下来，你学习了如何编辑 `mod.info` 文件使其准备好发布。你学到了让你的 mod 开源是一个好主意，最后，你了解了你可能放置它的几个网站。

### 问答

**问。有方法可以将 `modid-1.0` 改为更有用的名称吗？**

**答。有的，你可以在 `build.gradle` 文件中这样做。**

```gradle
buildscript {
    dependencies {
        classpath 'net.minecraftforge:ForgeGradle:1.2-SNAPSHOT'
    }
}

apply plugin: 'forge'

version = "1.0"

group = "com.yourname.modid"

archivesBaseName = "modid"

minecraft {
    version = "1.7.10-152"
    assetDir = "eclipse"
}

processResources {
    from(sourceSets.main.srcDirs) {
        include 'mcmod.info'
        expand 'version': project.version, 'mcversion': project.minecraft
    }

    from(sourceSets.main.srcDirs) {
        exclude 'mcmod.info'
    }
}
```



`version` 和 `archivesBaseName` 是保存你的 mod 的 `.jar` 文件的两个变量。

**问：**有办法不使用命令行就导出我的 mod 吗？

**答：**遗憾的是没有，以后可能也不会有。

### 工作坊

在本小时中，你学习了如何将你的 mod 从只有你可以在 Eclipse 中使用的东西，变成所有人都可以下载和享受的东西。虽然你不需要经常这样做，但当你希望别人使用你的 mod 时，这是最重要的部分。与其拥有一个只有几个功能的 mod，不如拥有一个无法运行的巨大 mod。测试你的理解情况，以确保你可以导出功能完整的 mod。

### 测验

1. 为什么应该让你的 mod 开源？
2. 写在 `mcmod.info` 中的信息会显示在哪里？

### 答案

1. 这可以帮助你的 mod 开发，因为别人可以帮助你修复漏洞，同时也通过在制作模组时提供一些源码来帮助他人。
2. 这些信息将显示在 Minecraft 的 Mods 菜单中。

### 练习

在 `minecraftforum.net` 上为你的模创建一个帖子，包含一些该模的基本信息、几张截图和一个下载链接。

## 第 24 小时：接下来是什么

在本小时你将学习：

- 使用 IRC
- 使用开源模组
- 学习 Java

在过去的 23 小时里，你学习了如何设置开始模组开发所需的一切，创建了实际的项目，然后将其导出并发布供他人使用。这就是这本书将教给你的全部，但还剩最后一个小时。在这个小时里，你将学习如何在没有这本书的情况下继续自己创建新内容。

### 使用 IRC

互联网中继聊天（IRC）是一种在线聊天程序，许多 Minecraft 模组开发者用它来互相获取支持。除了很有用之外，与其他 Minecraft 模组开发者聊天也非常有趣。

### 安装 IRC

你可以通过网页客户端访问 IRC，但某些频道为了防止垃圾邮件发送者不允许这样做。因此，在你的电脑上下载一个程序是一个好主意。这不仅是连接某些通道的要求，而且简单更好用。你可以使用许多不同的客户端，但本书涵盖了 `HexChat`。你可以从 [`hexchat.github.io/downloads.html`](http://hexchat.github.io/downloads.html) 下载 `HexChat`。然后按照下载文件中的指令安装 `HexChat`。

#### 添加必要的设置

当你第一次启动 `HexChat` 时，`Network List`（网络列表）窗口会打开。按照以下列表执行所有操作，以确保你可以使用它。

1. 点击 `Network List` 窗口中的 `Add`。这将创建一个名为 `New Network` 的新网络。
2. 将此名称更改为 `EsperNet`。
3. 点击 `Edit`。
4. 当 `HexChat: Edit EsperNet` 对话框打开时，点击 `Add`。
5. 输入 `irc.esper.net/6667`。这是你将与他人聊天时使用的服务器。

> **提示：其他 IRC 客户端**
>
> 许多 Minecraft 模组开发者使用 `HexChat`，但也有其他替代方案，例如用于 PC 的 `mIRC`、`Mibbit`` 或 `KiwiIRC`，以及无数手机客户端。

> **注意：其他网络**
>
> 你可以为 IRC 使用许多不同的网络。Minecraft 社区中常用的是 `EsperNet`，因为在上面创建自己的频道非常容易。
>
> 另一个常用且稍专业一点的 IRC 网络是 `freenode`，它比 `EsperNet` 更严格。

6. 关闭 `HexChat: Edit EsperNet` 窗口。
7. 在 `Nick Name`（昵称）、`Second Choice`、`Third Choice` 和 `User Name` 框中输入你的用户名。
8. 点击右下角的 `Connect`。
9. 当你连接到 `EsperNet` 时，输入以下命令：`/msg NickServ register <password> <email>`，其中 `<password>` 和 `<email>` 是你的个人邮箱地址和密码。这将向你发送一封邮件，其中包含另一个你需要粘贴到 `HexChat` 中的命令。
10. 检查你的收件箱。你应该收到一封包含命令的邮件。
11. 回到 `HexChat: Edit EsperNet` 窗口，勾选 `Connect to This Network Automatically`（自动连接到此网络）框框。
12. 从 `Login Method`（登录方法）下拉菜单选择 `/MSG NickServ + Password`。在 `Password` 框中输入你刚刚注册的密码。这确保你不需要每次登录都注册；下次登录时，它会自动处理。
13. 最后，点击 `Close`，你的 IRC 程序就设置好了。

### 加入频道

现在必要的设置已完成，你可以开始在有趣的频道中与人聊天。对于使用 Forge 的 Minecraft 模组开发来说，最重要的频道之一是 `#minecraftforge`。要加入此频道，在屏幕底部用户名右侧的输入区域输入 `/join #minecraftforge`。这将让你进入频道，你可以在那里与各种人聊天。你可能想右键点击屏幕左侧的 `#minecraftforge` 频道并选择 `Autojoin and Settings`、`Hide Join/Part Messages`，但这并非必须。

> **警告：小心你的信息**
>
> 在互联网上聊天时，良好的做法是永远不要泄露个人信息——例如你的家庭地址、电话号码、当前位置——并且永远不要答应与在网上认识的人面谈。你在频道中互动的绝大多数人都是友好的，但最好还是留个心。

你可能还想加入许多其他有趣的频道。有关于 Minecraft 模组开发的频道，也有关于玩 Minecraft 的频道。建议的频道有 `#Direwolf20`、`#FTB`、`#MinecraftForgeTuts` 和 `#ModJam`。你可能还想加入一些关于 Minecraft 模组开发的频道，以及关于玩 Minecraft 的频道。

24.1 图 24.1 显示了你想要的功能。

![图 24.1：`HexChat` 的设置。](img/image00525.jpeg)

> **注意：其他网络**
>
> 你可以为 IRC 使用许多不同的网络。Minecraft 社区中常用的是 `EsperNet`，因为在上面创建自己的频道非常容易。
>
> 另一个常用且稍专业一点的 IRC 网络是 `freenode`，它比 `EsperNet` 更严格。

通过在屏幕底部用户名右侧的输入区域输入 `/join [channel]` 来访问其他频道。你可能还想查看一下是否有关于你感兴趣的频道。发现新频道最简单的方法是尝试或询问他人。

当你编写代码时，在代码段之前包含注释是有帮助的，这可以说明接下来的代码的作用或任何可能有助于读者了解代码的其他信息。当你几周后再次回到同一段代码，但不完全记得它是做什么的时，这会对你很有帮助。此外，当其他人阅读你的代码时，这也有帮助。

不过，不要过度注释，否则你可能会降低代码的可读性。

## 使用代码

现在你已经知道如何寻找新代码以及如何理解它。然而，知道如何使用这些代码同样重要。

### 你不能对代码做什么

你不能直接复制别人的代码。如果你这样做，原始模组作者（modder）可能不会喜欢。这可能导致作者将模组改为闭源，而这是没有人会喜欢的。因此，在查看代码时，尊重模组作者的意愿是非常重要的。有些模组在源码中包含许可证，你必须遵守，但即使它们没有，你也不应该直接复制代码。那是对原作者的不尊重，也意味着你的模组缺乏原创性，结果就是它是无聊的。

### 你可以对代码做什么

你可以也应该对代码做的是从中学习。你可以利用代码来发现他人是如何编写代码的。通过这些信息，你可以改进自己的模组。在制作模组时，最好的想法总是从已经有的东西开始，然后根据你的需求进行调整。不过，你应该始终寻找代码中的许可证。有些开源模组允许这样做，但另一些不允许。

### 注意事项：复制代码

虽然复制代码通常不是违法的，但这并不礼貌。如果你确实从另一个模组中复制了代码，请务必给予应有的致谢。当模组作者在制作时互相尊重时，社区就能真正成长。如果这种情况没有发生，就会出现问题，而没有人喜欢这些问题。

在使用开源代码之前，请务必查看它使用的许可证，以确保你想要的操作是被允许的。

## 学习 Java

在完成这本书后，你继续学习可以做的最好的事情之一就是学习 Java。如果你还没有学习 Java，我强烈建议你现在就开始学习。你可以通过几种不同的资源来学习 Java。一个免费的选项是由 thenewboston 在 YouTube 上制作的播放列表：`https://www.youtube.com/playlist?list=PLFE2CE09D83EE3E28`。这个资源很好，是因为它是免费的。虽然它并不总是完全准确，但它是目前最好的免费资源之一。

另一个更准确、可能更适合学习的资源是 Rogers Cadenhead 编写的 `Sams Teach Yourself Java in 24 Hours`。

当你遵循任何关于学习 Java 的资源时，你会发现你已经掌握了一些基础知识。然而，如果你想真正精通 Minecraft 模组制作，你需要的不仅仅是 Java 的基础知识。

创建 Minecraft 模组并不需要博大的 Java 知识。但是，如果你想创建真正独特且有趣的模组，你确实需要了解 Java——你了解的 Java 越多，你能创建的模组就越出色。此外，如果你需要自己将模组更新到新版本的 Minecraft，你需要精通 Java。正因如此，学习 Java 是一个非常好的主意——学得越早，对你越有利。

### 总结

在这一小时中，你学习了如何安装 IRC 以及如何加入 Minecraft 模组开发中最重要的频道。然后，你学习了如何使用其他开源模组来获取如何改进你模组的知识。最后，你了解到学习 Java 是一个好主意，这样你就可以在没有帮助的情况下开发模组了。

### 问答

#### Q. 为什么使用 `HexChat`？

**A.** `HexChat` 是许多不同的 IRC 客户端之一。它们都有自己的优缺点，对于不同的人，最好的客户端可能不同。你需要在电脑上有一个 IRC 程序来连接某些频道，而 `HexChat` 通常被认为是最好的。

#### Q. 为什么我不能直接从其他模组复制代码？

**A.** 通常，模组作者不会喜欢的。然而，在某些情况下，如果你不遵守模组作者提供的许可证中的规则，这可能被视为抄袭。此外，它会让你的模组缺乏原创性。

### 工作坊

在这一小时中，你学习了在完成这本书后如何继续你的模组开发。请通过完成最后的测验来确保你知道如何这样做。

### 测验

1. 为什么你需要学习 Java？
2. 为什么在加入 `#minecraftforge` 之前必须向 `NickServ` 注册？

### 答案

1. 你需要擅长 Java 来制作更好的模组。
2. 只有注册后才能加入。

### 练习

## 附录 A：其他代码

此附录提供了你可能需要的各种代码。

### 配置（Configs）

配置可以用于你的模组。附录 A.1 展示了一个 `Config` 类示例。

```java
package com.wuppy.smod;

import net.minecraft.config.Configuration;

import cpw.mods.fml.common.event.FMLInitializationEvent;

public class Config
{
    public static boolean spawnDungeon;

    public static void load(FMLInitializationEvent event)
    {
        Configuration config = new Configuration(event.getSuggestedFile());

        config.load();

        spawnDungeon = config.get(Configuration.GENERAL, "spawnDungeon", true).getBoolean(true);

        config.save();
    }
}
```

该方法在模组文件的 `preInit` 中通过以下行调用：

```java
Config.load(event);
```

该 `boolean` 使用在你在第 16 小节创建的代码中：

```java
if (Config.spawnDungeon)
{
    int posX = x + random.nextInt(16);
    int posY = 10 + random.nextInt(40);
    int posZ = z + random.nextInt(16);

    new WorldGenSamungeon().generate(world, random, posX, posY, posZ);
}
```

### 旋转方块

如果你在模组中创建一个像木头那样的根据放置方式旋转的方块，这需要你像附录 A.2 那样编写你的方块。

```java
package com.wuppy.smod.blocks;

import net.minecraft.block.BlockLog;
import net.minecraft.block.BlockRotatedPillar;
import net.minecraft.block.material.Material;

import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.util.IIcon;

import com.wuppy.samsmod.SamsMod;

import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class BlockRotateExample extends BlockRotatedPillar
{
    public BlockRotateExample()
    {
        super(Material.rock);

        setResistance(1.0F);

        setBlockName(SamsMod.MODID + "_" + "rotateExample");
    }
}
```

```java
setCreativeTab(CreativeTabs.tabBlock);
}

@SideOnly(Side.CLIENT)
private IIcon[] iconArray;

@SideOnly(Side.CLIENT)
@Override
public void registerBlockIcons(IIconRegister par1IconRegister)
{
    iconArray = new IIcon[2];

    for (int i = 0; i < this.iconArray.length; ++i)
    {
        this.iconArray[i] = par1IconRegister.registerIcon(
            SamsMod.MODID + ":" + (this.getUnlocalizedName().substring(5)) + i
        );
    }
}

@SideOnly(Side.CLIENT)
@Override
protected IIcon getTopIcon(int p_150161_1_)
{
    return iconArray[1];
}

@SideOnly(Side.CLIENT)
@Override
protected IIcon getSideIcon(int p_150163_1_)
{
    return iconArray[0];
}
```

### 自定义方块渲染

你可能想要一个具有自定义形状的方块。为了实现这一点，你需要一个像列表 A.3 这样的方块。

**列表 A.3 自定义渲染方块类**

点击此处查看代码图片。

```java
package com.wuppy.samsmod.blocks;

import java.util.Random;

import com.wuppy.samsmod.SamsMod;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.init.Items;
import net.minecraft.item.Item;
import net.minecraft.world.IBlockAccess;
import net.minecraft.world.World;

import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class BlockCustomRenderWoodExample extends Block
{
    public BlockCustomRenderWoodExample()
```



以下是排版后的内容：

```java
{

    super(Material.wood);

    setHardness(2.0F);

    setStepSound(soundTypeWood);

    setBlockName(SamsMod.MODID + "_" + "customwood");

    setCreativeTab(CreativeTabs.tabBlock);

    setHarvestLevel("axe", 1);

}

@Override

public void setBlockBoundsOnState(IBlockAccess world, int x, int y, int z)

{

    setBlockBounds(0.33f, 0.33f, 0.33f, 0.66f, 0.66f);

}

@Override

public boolean isOpaque()

{

    return false;

}

@Override

public boolean renderAsBlock()

{

    return false;

}

@Override

public int getRenderType()

{

    return RenderCustomExample.renderId;

}

@Override

public boolean shouldSideRendered(IBlockAccess par1BlockAccess, int par2, int par3, int par4)

{

    return true;

}

/**

 * 返回销毁时掉落物品的 ID。

 */

@Override

public Item getItemDropped(int par1, Random par2Random, int par3)

{

    return Items.stick;

}

/**

 * 将包含的物品释放到世界中，并根据情况通知邻居更新

 */

@Override

public void breakBlock(World world, int x, int y, int z, Block block, int meta)

{

    byte b0 = 4;

    int i1 = b0 + 1;

    if (world.checkChunksExist(x - i1, y - i1, z - i1, x + i1, y + i1, z + i1))

    {

        for (int j1 = -b0; j1 <= b0; ++j1)

        {

            for (int k1 = -b0; k1 <= b0; ++k1)

            {

                for (int l1 = -b0; l1 <= b0; ++l1)

                {

                    Block blockleave = world.getBlock(x + j1, y + k1, z + l1);

                    if (blockleave.isLeaves(world, x + j1, y + k1, z + l1))

                    {

                        blockleave.beginLeavesDecay(world, x + j1, y + k1, z + l1);

                    }

                }

            }

        }

    }

}

@SideOnly(Side.CLIENT)

@Override

/**

 * 当此方法被调用时，你的方块应该向给定的 IconRegister 注册所有需要的图标。

 * 这是你注册图标的唯一机会。

 */

public void registerBlockIcons(IIconRegister par1IconRegister)

{

    blockIcon = par1IconRegister.registerIcon(SamsMod.MODID + ":" + (this.getUnlocalizedName().substring(5)));

}

}
```

正如其名，这个方块也可以作为木头工作。这里与此相关的的方法是`breakBlock`。

该方块在没有连接到任何东西时将是一个小立方体。一旦附近有方块或叶子，它就会与它们连接，形成分支。列表 A.4 显示了`RenderCustomWoodExample`类。

**列表 A.4 自定义渲染类**

点击此处查看代码图片

```java
package com.wuppy.samsmod.blocks;

import net.minecraft.block.Block;

import net.minecraft.client.renderer.RenderBlocks;

import net.minecraft.client.renderer.Tessellator;

import net.minecraft.init.Blocks;

import net.minecraft.world.IBlockAccess;

import org.lwjgl.opengl.GL11;

import cpw.mods.fml.client.registry.ISimpleBlockRenderingHandler;

import cpw.mods.fml.client.registry.RenderingRegistry;

public class RenderCustomWoodExample implements ISimpleBlockRenderingHandler

{

    public static int renderId = RenderingRegistry.getNextAvailableId();

    @Override

    public void renderInventoryBlock(Block block, int metadata, int modelID, RenderBlocks renderer)

    {

        if (modelID == renderId)

        {

            renderer.setRenderBounds(0.5f, 0f, 0.15f, 1f, 0.5f);

            renderInvBlock(metadata);

        }

    }

    @Override

    public boolean renderWorldBlock(IBlockAccess world, int x, int y, int z, Block block, int modelID, RenderBlocks renderer)

    {

        if (modelID == renderId)

        {

            // 中间木块

            renderer.setRenderBounds(0.33f, 0.33f, 0.33f, 0.66f, 0.66f);

            renderer.renderStandardBlock(block, x, y, z);

            // 顶部

            if (world.getBlock(x, y + 1, z) == ModBlocks.customWoodExample)

            {

                renderer.setRenderBounds(0.33f, 0.66f, 0.33f, 1f, 0.66f);

                renderer.renderStandardBlock(block, x, y, z);

            }

            if (world.getBlock(x, y + 1, z) == Blocks.leaves)

            {

                renderer.setRenderBounds(0.33f, 0.66f, 0.33f, 1.15f, 0.66f);

                renderer.renderStandardBlock(block, x, y, z);

            }

            // 底部

            if (!world.isBlock(x, y - 1, z))

            {

                renderer.setRenderBounds(0.33f, 0f, 0.33f, 0.66f, 0.66f);

                renderer.renderStandardBlock(block, x, y, z);

            }

            // 左侧

            if (world.getBlock(x + 1, y, z) == ModBlocks.customWoodExample)

            {

                renderer.setRenderBounds(0.33f, 0.33f, 0.33f, 1f, 0.66f);

                renderer.renderStandardBlock(block, x, y, z);

            }

            if (world.getBlock(x + 1, y, z) == Blocks.leaves)

            {

                renderer.setRenderBounds(0.33f, 0.33f, 0.33f, 1.15f, 0.66f);

                renderer.renderStandardBlock(block, x, y, z);

            }

            // 右侧

        }

        return true;

    }

    private void renderInvBlock(int metadata)

    {

        // 实现逻辑

    }

}
```

```java
if(world.getBlock(x - 1, y, z) == ModBlocks.customWoodExample)

{

    renderer.setRenderBounds(0f, 0.33f, 0.33f, 0.33f, 0.66f, 0.66f);

    renderer.renderStandardBlock(block, x, y, z);

}

if(world.getBlock(x - 1, y, z) == Blocks.leaves)

{

    renderer.setRenderBounds(-0.15f, 0.33f, 0.33f, 0.33f, 0.66f, 0.66f);

    renderer.renderStandardBlock(block, x, y, z);

}

// 前面

if(world.getBlock(x, y, z + 1) == ModBlocks.customWoodExample)

{

    renderer.setRenderBounds(0.33f, 0.33f, 0.33f, 0.66f, 0.66f, 1f);

    renderer.renderStandardBlock(block, x, y, z);

}

if(world.getBlock(x, y, z + 1) == Blocks.leaves)

{

    renderer.setRenderBounds(0.33f, 0.33f, 0.33f, 0.66f, 0.66f, 1.5f);

    renderer.renderStandardBlock(block, x, y, z);

}

// 后面

if(world.getBlock(x, y, z - 1) == ModBlocks.customExample)

{

    renderer.setRenderBounds(0.33f, 0.33f, 0f, 0.66f, 0.66f, 0.33f);

    renderer.renderStandardBlock(block, x, y, z);

}

if(world.getBlock(x, y, z - 1) == Blocks.leaves)

{

    renderer.setRenderBounds(0.33f, 0.33f, -0.15f, 0.66f, 0.66f, 0.33f);

    renderer.renderStandardBlock(block, x, y, z);

}

return true;

@Override

public int getRenderId()

{

    return renderId;

}

public static void renderInvBlock(RenderBlocks renderblocks, Block block, int meta)

{

    Tessellator tessellator = Tessellator.instance;

    GL11.glTranslatef(-0.5F, -0.5F, -0.5F);

    tessellator.startDrawingQuads();

    tessellator.setNormal(0.0F, -1F, 0.0F);

    renderblocks.renderFaceYNeg(block, 0.0D, 0.0D, 0.0D, block.getIcon(0, meta));

    tessellator.draw();

    tessellator.startDrawingQuads();

    tessellator.setNormal(0.0F, 1.0F, 0.0F);

    renderblocks.renderFaceYPos(block, 0.0D, 0.0D, 0.0D, block.getIcon(1, meta));

    tessellator.draw();

    tessellator.startDrawingQuads();

    tessellator.setNormal(0.0F, 0.0F, -1F);

    renderblocks.renderFaceXPos(block, 0.0D, 0.0D, 0.0D, block.getIcon(2, meta));

    tessellator.draw();

    tessellator.startDrawingQuads();

    tessellator.setNormal(0.0F, 0.0F, 1.0F);

    renderblocks.renderFaceXNeg(block, 0.0D, 0.0D, 0.0D, block.getIcon(3, meta));

    tessellator.draw();

    tessellator.startDrawingQuads();

    tessellator.setNormal(-1F, 0.0F, 0.0F);

    renderblocks.renderFaceZNeg(block, 0.0D, 0.0D, 0.0D, block.getIcon(4, meta));

    tessellator.draw();

    tessellator.startDrawingQuads();

    tessellator.setNormal(1.0F, 0.0F, 0.0F);

    renderblocks.renderFaceZPos(block, 0.0D, 0.0D, 0.0D, block.getIcon(5, meta));

    tessellator.draw();

    GL11.glTranslatef(0.5F, 0.5F, 0.5F);

}

@Override

public boolean shouldRender3DInInventory(int modelId)

{

    return false;

}
```

这个自定义的`Render`类还必须使用以下代码在你的`ClientProxy`中注册：

```java
RenderingRegistry.registerBlockHandler(new RenderCustomWoodExample());
```

### 自定义树木生成

当你为自定义树创建方块时，你可能也想生成它。

**自定义树木生成**

当你为自定义树创建方块时，你可能也想生成它。

**自定义树木生成类**

```java
package com.wuppy.smod.generation;
```



```java
import java.util.Random;

import net.minecraft.block.Block;
import net.minecraft.init.Blocks;
import net.minecraft.world.World;
import net.minecraft.world.generator.WorldGenerator;

import com.wuppy.smod.block.ModBlocks;

public class WorldGenCustomExample extends WorldGenerator
{
    int height;
    Block wood = ModBlocks.customWoodExample;
    Block leaf = Blocks.leaves;

    public boolean generate(World world, Random random, int x, int y, int z)
    {
        if (world.getBlock(x - 1, y, z) == ModBlocks.customWoodExample)
        {
            y--;
        }

        if (world.getBlock(x - 1, y, z) == Blocks.leaves)
        {
            return false;
        }

        height = random.nextInt(5);

        for (int i = 0; i < height; i++)
        {
            world.setBlock(x, y + i, z, wood);

            if (i > 0)
            {
                world.setBlock(x + 1, y + i, z, leaf);
                world.setBlock(x - 1, y + i, z, leaf);
                world.setBlock(x, y + i, z + 1, leaf);
                world.setBlock(x, y + i, z - 1, leaf);
            }
        }

        return true;
    }
}
```

```java
setBlock(world, x, y + 1, z - i, leaf);

if (i > 0)
{
    setBlock(world, x - 1, y, z - i, leaf);
    setBlock(world, x + 1, y, z - i, leaf);
}

setBlock(world, x + left, y, z, leaf);
setBlock(world, x - right, y, z, leaf);
setBlock(world, x, y, z + front, leaf);
setBlock(world, x, y, z - back, leaf);

return true;
}
else
{
    return false;
}

public void setBlock(World world, int x, int y, int z, Block block)
{
    world.setBlock(x, y + height, z, block);
}
```

### 自动更新检查

当你更新你的模（mod）时，你可能希望人们知道这件事。以下代码可以帮助你通过控制台打印信息来告诉玩家你的模已更新。列表 A.6 展示了 `UpdateChecker` 类。

**列表 A.6 类：`UpdateChecker`**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class UpdateChecker
{
    public static String updates = "";
    public static boolean outdated = false;

    public static void checkForUpdates()
    {
        int currentVersion = SamsMod.modVersion;
        int nextVersion = getNew();

        if (currentVersion < nextVersion)
        {
            updates = getUpdate(nextVersion);
            outdated = true;
        }
        else
        {
            outdated = false;
        }
    }

    public static int getNew()
    {
        try
        {
            URL url = new URL("http://uppy29.com/mods/sm/new.txt");
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();

            connection.setRequestMethod("POST");
            connection.setRequestProperty("Content-Type", "application/x-www-form-urlencoded");
            connection.setRequestProperty("Content-Language", "en-US");
            connection.setRequestProperty("User-Agent", "Mozilla/5.0 (Windows NT 5.1) AppleWebKit/35.1 (KHTML, like) Chrome/17.0.963.5 Safari/35.1");
            connection.setUseaches(false);
            connection.setDoInput(true);
            connection.setDoOutput(true);

            InputStream is = connection.getInputStream();
            BufferedReader br = new BufferedReader(new InputStreamReader(is));

            String line;
            StringBuffer response = new StringBuffer();

            while ((line = br.readLine()) != null)
            {
                response.append(line);
            }

            br.close();

            return Integer.parseInt(response.toString());
        }
        catch (IOException e)
        {
            e.printStackTrace();
        }

        return -1;
    }

    private static String getUpdate(int version)
    {
        try
        {
            URL url = new URL("http://uppy29.com/mods/sm/" + version + ".txt");
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();

            connection.setRequestMethod("POST");
            connection.setRequestProperty("Content-Type", "application/x-www-form-urlencoded");
            connection.setRequestProperty("Content-Language", "en-US");
            connection.setRequestProperty("User-Agent", "Mozilla/5.0 (Windows NT 5.1) AppleWebKit/35.1 (KHTML, like) Chrome/17.0.963.5 Safari/35.1");
            connection.setUseaches(false);
            connection.setDoInput(true);
            connection.setDoOutput(true);

            InputStream is = connection.getInputStream();
            BufferedReader br = new BufferedReader(new InputStreamReader(is));

            String line;
            StringBuffer response = new StringBuffer();

            while ((line = br.readLine()) != null)
            {
                response.append(line);
            }

            br.close();

            return response.toString();
        }
        catch (IOException e)
        {
            e.printStackTrace();
        }

        return "Error";
    }
}
```

`modVersion` 是一个从 1 开始并在每当新版本发布时增加的数字。该模组有一个名为 `newest.txt` 的文件，其中包含最新的版本号。如果该数字比代码中的 `modVersion` 高，它将访问 `[versionnumber].txt` 获取更改内容。我将所有这些内容都放在我的网站上，但你也可以把它们放在 Dropbox 或类似的地方。

以下事件代码将在聊天框中打印更改：

点击此处查看代码图片

```java
@SubscribeEvent
public void check(PlayerEvent event)
{
    if (UpdateChecker.outdated)
    {
        event.player.addChatComponent(new ChatComponent("SamsMod is outdated."));
        event.player.addChatComponent(new ChatComponent("Changelog: "));
        event.player.addChatComponent(new ChatComponent(UpdateChecker.updates));
    }
}
```

### 自定义标签页

当你有很多物品或方块时，创建 `CreativeTab` 可能很有用，这可以让原版的标签页更容易使用，并让你的东西更容易找到。要实现这一点，模应该调用以下行代码：

点击此处查看代码图片

```java
public static CreativeTabs exampleTab = new CreativeTab("example");
```

`ExampleTab` 类应该类似于列表 A.7 所示。

**列表 A.7 Tab 类**

点击此处查看代码图片

```java
package com.wuppy.samsmod;

import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.item.Item;

import com.wuppy.samsmod.items.ModItems;

import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

public class ExampleTab extends CreativeTabs
{
    public ExampleTab(int par1, String par2Str)
    {
        super(par1, par2Str);
    }

    @Override
    @SideOnly(Side.CLIENT)
    public Item getTabItem()
    {
        return ModItems.sampickaxe;
    }
}
```

### 自定义 TNT

TNT 是方块和实体的结合。列表 A.8 展示了 TNT 方块。

**列表 A.8 自定义 TNT 方块示例**

点击此处查看代码图片

```java
package com.wuppy.samsmod.blocks;

import net.minecraft.block.BlockTNT;
import net.minecraft.client.renderer.texture.IIconRegister;
import net.minecraft.creativetab.CreativeTabs;
import net.minecraft.entity.EntityLiving;
import net.minecraft.util.IIcon;
import net.minecraft.world.Explosion;
import net.minecraft.world.World;

import com.wuppy.samsmod.SamsMod;
import com.wuppy.samsmod.entity.EntityExampleTNTPrimed;

import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;
```

`Listing A.9` 显示了 TNT 块的实体。

### 列表 A.9 TNT 实体

（此处为代码块，保持不翻译）

```java
/**
 * 实际上渲染给参数。这是一个同步桥接方法，它总是将其参数向下转型，然后
 * 交给工作函数，由该函数执行实际工作。在大多数情况下，Render 类是泛型的
 * (Render<T extends Entity>)，且该方法的签名为 public void doRender(T entity, double d, double d1,
 * double d2, float f, float f1)。但 JAD 是 1.5 之前的，所以没有这样做。
 */
public void doRender(Entity par1Entity, double par2, double par4, double par6, float par8, float par9)
{
    this.renderPrimedTNT((EntityExampleTNTPrimed) par1Entity, par2, par4, par6, par8, par9);
}
```

***

该实体必须像其他实体一样注册，并且在 `ClientProxy` 中需要渲染注册表，如下：

点击此处查看代码图像

```java
RenderingRegistry.registerEntityRenderingHandler(EntityExampleTNTPrimed.class, new RenderExampleTNTPrimed());
```

### 改变生物行为

有一些简单的技巧可以用来编辑原版生物的行为。下面你可以看到一个示例，它让洞穴蜘蛛在高度 40 以下的任何地方生成，而不仅仅是在矿井的生成器中。

以下代码用在模类的 `preInit` 方法中：

点击此处查看代码图像

```java
EntityRegistry.registerModEntity(EntityCaveSpiderCustom.class, "cavespidercustom", 0, this, 80, 3, true);
```



```java
for (int i = 0; i < BiomeGenBase.getBiomeGenArray().length; i++)
{
    if (BiomeGenBase.getBiomeGenArray()[i] != null)
    {
        EntityRegistry.addSpawn(EntityCaveSpiderCustom.class, 4, 3, 5, EnumCreatureType.monster, BiomeGenBase.getBiomeGenArray()[i]);
    }
}
```

以下 `Render` 类将用在 `ClientProxy` 中：

点击此处查看代码图像

```java
RenderingRegistry.registerEntityRenderingHandler(EntityCaveSpiderCustom.class, new RenderSpider());
```

列表 A.11 显示了 `EntityCaveSpiderCustom` 类。

**列表 A.11 EntityCaveSpiderCustom 类**

点击此处查看代码图像

```java
package com.wuppy.samsmod.entity;

import net.minecraft.entity.monster.EntityCaveSpider;
import net.minecraft.world.World;

public class EntityCaveSpiderCustom extends EntityCaveSpider
{
    public EntityCaveSpiderCustom(World par1World)
    {
        super(par1World);
    }

    @Override
    public boolean getCanSpawnHere()
    {
        if (this.posY < 40.0)
            return true;
        else
            return false;
    }
}
```

这个生物看起来和行动起来与 `EntityCaveSpider` 完全一样，尽管它实际上是不同的实体。这是一个非常具体的例子，但同样的概念可以用于许多不同的场景。

### 衣服

你可以让你的护甲看起来像衣服。你可以通过创建普通护甲并然后添加一些自定义代码来实现这一点。首先，应该将穿戴的护甲纹理切割成四部分——每个部分一个，而不是将头盔、胸甲、靴子合为一个，裤子为另一个。这应该在 `getArmorTexture` 方法中进行代码。

列表 A.12 显示了你必须添加到 `ItemArmor` 文件中的方法，以使其看起来像衣服。

**列表 A.12 用于衣服的 getArmorModel 方法**

点击此处查看代码图像

```java
@Override
@SideOnly(Side.CLIENT)
public ModelBiped getArmorModel(EntityLivingBase entityLiving, ItemStack itemstack, int armorSlot)
{
    ModelBiped armorModel = null;

    if (itemstack != null)
    {
        if (stack.getItem() instanceof ElsaArmor)
        {
            float f = 0.1F;
            armorModel = new ModelBiped(f);
            ItemStack stack2 = ((EntityPlayer) entityLiving).inventory.getCurrentItem();
            armorModel.heldItemRight = stack2 != null ? 1 : 0;
            armorModel.isSneak = entityLiving.isSneaking();

            if (stack2 != null && ((EntityPlayer) entityLiving).getItemInCount() > 0)
            {
                EnumAction enumaction = stack2.getItemUseAction();

                if (enumaction == EnumAction.block)
                {
                    armorModel.heldItemRight = 3;
                }
                else if (enumaction == EnumAction.bow)
                {
                    armorModel.aimedBow = true;
                }
            }
        }
    }

    return armorModel;
}
```

### 护甲效果

列表 A.13 中的以下代码是护甲效果的示例。在这种情况下，当你穿靴子时，护甲会将水变为冰，并将岩浆变为黑岩。

**列表 A.13 用于方的 onArmorTick**

点击此处查看代码图像

```java
@Override
public void onArmorTick(World world, EntityPlayer player, ItemStack itemStack)
{
    if (itemStack.getItem() instanceof ElsaArmor)
    {
        if (armorType == 3)
        {
            int x = (int) player.posX;
            int y = (int) player.posY - 1;
            int z = (int) player.posZ;
            Block block = world.getBlock(x, y, z);

            // 水
            if (block == Blocks.water || block == Blocks.flowing_water)
            {
                world.setBlock(x, y, z, Blocks.ice);
            }

            if (world.getBlock(x + 1, y, z) == Blocks.water || world.getBlock(x + 1, y, z) == Blocks.flowing_water)
            {
                world.setBlock(x + 1, y, z, Blocks.ice);
            }

            if (world.getBlock(x - 1, y, z) == Blocks.water || world.getBlock(x - 1, y, z) == Blocks.flowing_water)
            {
                world.setBlock(x - 1, y, z, Blocks.ice);
            }

            if (world.getBlock(x, y, z + 1) == Blocks.water || world.getBlock(x, y, z + 1) == Blocks.flowing_water)
            {
                world.setBlock(x, y, z + 1, Blocks.ice);
            }

            if (world.getBlock(x, y, z - 1) == Blocks.water || world.getBlock(x, y, z - 1) == Blocks.flowing_water)
            {
                world.setBlock(x, y, z - 1, Blocks.ice);
            }

            // 岩浆
            if (block == Blocks.lava || block == Blocks.flowing_lava)
            {
                world.setBlock(x, y, z, Blocks.obsidian);
            }

            if (world.getBlock(x + 1, y, z) == Blocks.lava || world.getBlock(x + 1, y, z) == Blocks.flowing_lava)
            {
                world.setBlock(x + 1, y, z, Blocks.obsidian);
            }

            if (world.getBlock(x - 1, y, z) == Blocks.lava || world.getBlock(x - 1, y, z) == Blocks.flowing_lava)
            {
                world.setBlock(x - 1, y, z, Blocks.obsidian);
            }

            if (world.getBlock(x, y, z + 1) == Blocks.lava || world.getBlock(x, y, z + 1) == Blocks.flowing_lava)
            {
                world.setBlock(x, y, z + 1, Blocks.obsidian);
            }
        }
    }
}
```

```java
world.setBlock(x, y, z - 1, Blocks.obsidian);
```

# 创建自定义维度

Minecraft 中原本只有三个维度，添加一个自定义维度可以使 Mod 变得非常有趣且庞大。然而，对于一个维度，你需要编写大量的代码。

自定义维度所需的 Mod 类代码看起来如下：

点击此处查看代码图片

```java
public static int dimension = 5;

DimensionManager.registerProviderType(dimension, WorldProviderExample.class, false);
DimensionManager.registerDimension(dimension, dimension);
```

建议将维度 ID（dimension ID）设置为可配置，以便与其他 Mod 保持兼容性。

## WorldProviderExample（世界提供者示例）

`WorldProvider` 包含了你维度的几个重要设置。它主要设置了 `WorldChunkManager`，这是一个主要处理生物群的类。在这种情况下，使用了 `WorldChunkManagerHell`，这意味着该维度将只有一个生物群。你可以创建一个自定义的 `WorldChunkManager`，但这非常复杂，而且只有少数人成功运行过它。

### A.14 WorldProviderExample 类

点击此处查看代码图片

```java
package com.wuppy.samsmod.dimension;

import net.minecraft.util.ChunkCoordinates;
import net.minecraft.world.WorldProvider;
import net.minecraft.world.biome.BiomeGenBase;
import net.minecraft.world.biome.WorldChunkManagerHell;
import net.minecraft.world.chunk.Chunk;
import net.minecraft.world.chunk.IChunkProvider;

public class WorldProviderExample extends WorldProvider
{
    public void registerWorldChunkManager()
    {
        this.worldChunkMgr = new WorldChunkManagerHell(BiomeGenBase.beach, 0.1F);
        this.dimensionId = SamsMod.dimension;
    }

    @Override
    public String getSaveFolder()
    {
        return "DIM-Example";
    }

    @Override
    public String getWelcomeMessage()
    {
        return "Entering The Example Dimension";
    }

    @Override
    public String getDepartMessage()
    {
        return "Leaving The Example Dimension";
    }

    @Override
    public boolean canRespawnHere()
    {
        return true;
    }

    @Override
    public IChunkProvider createChunkGenerator()
    {
        return new ChunkProviderExample(worldObj, worldObj.getSeed(), true);
    }

    @Override
    public String getDimensionName()
    {
        return "Example";
    }

    /**
     * 获取用于进入此维度的硬编码传送位置。
     */
    @Override
    public ChunkCoordinates getEntrancePortal()
    {
        return null;
    }

    @Override
    public boolean canDoLightning(Chunk chunk)
    {
        return true;
    }

    @Override
    public boolean canDoRain(Chunk chunk)
    {
        return false;
    }
}
```

## ChunkProvider（区块提供者）

在 `WorldProvider` 中所示的 `ChunkProviderExample` 是一个巨大的类，它为你生成维度。它放置了基岩、石头、泥土、沙子、水以及你在 Minecraft 世界中看到的几乎所有东西。这是你维度中一个非常重要的类，因为它定义了它的样貌。自定义维度的类可以在 Listing.15 中找到。

### A.15 ChunkProvider

点击此处查看代码图片

```java
package com.wuppy.samsmod.dimension;

import static net.minecraftforge.event.terraingen.InitMapGenEvent.EventType.CAVE;
import static net.minecraftforge.event.terraingen.InitMapGenEvent.EventType.MINESHAF;
import static net.minecraftforge.event.terraingen.InitMapGenEvent.EventType.RAVINE;
import static net.minecraftforge.event.terraingen.InitMapGenEvent.EventType.SCATTERED_FEATURE;
import static net.minecraftforge.event.terraingen.InitMapGenEvent.EventType.STRONGHOLD;
import static net.minecraftforge.event.terraingen.InitMapGenEvent.EventType.VILLAGE;
import static net.minecraftforge.event.terraingen.PopulateChunkEvent.EventType.ANIMALS;
```



```java
import static net.minecraftforge.event.terraingen.PopulateChunkEvent.EventType.DUNGEON;
import static net.minecraftforge.event.terraingen.PopulateChunkEvent.EventType.ICE;
import static net.minecraftforge.event.terraingen.PopulateChunkEvent.EventType.LAKE;
import static net.minecraftforge.event.terraingen.PopulateChunkEvent.EventType.LAVA;

import java.util.List;
import java.util.Random;

import net.minecraft.block.Block;
import net.minecraft.block.BlockFalling;
import net.minecraft.entity.EnumCreatureType;
import net.minecraft.init.Blocks;
import net.minecraft.util.IProgressUpdate;
import net.minecraft.util.MathHelper;
import net.minecraft.world.ChunkPosition;
import net.minecraft.world.SpawnerAnimals;
import net.minecraft.world.World;
import net.minecraft.world.WorldType;
import net.minecraft.world.biome.BiomeGenBase;
import net.minecraft.world.chunk.Chunk;
import net.minecraft.world.chunk.IChunkProvider;
import net.minecraft.world.gen.MapGenBase;
import net.minecraft.world.gen.MapGenCaves;
import net.minecraft.world.gen.MapGenRavine;
import net.minecraft.world.gen.NoiseGenerator;
import net.minecraft.world.gen.NoiseGeneratorOctaves;
import net.minecraft.world.gen.NoiseGeneratorPerlin;
import net.minecraft.world.gen.feature.WorldGenDungeons;
import net.minecraft.world.gen.feature.WorldGenLakes;
import net.minecraft.world.gen.structure.MapGenMineshaft;
import net.minecraft.world.gen.structure.MapGenScatteredFeature;
import net.minecraft.world.gen.structure.MapGenStronghold;
import net.minecraft.world.gen.structure.MapGenVillage;
import net.minecraftforge.common.MinecraftForge;
import net.minecraftforge.event.terraingen.ChunkProviderEvent;
import net.minecraftforge.event.terraingen.PopulateChunkEvent;
import net.minecraftforge.event.terraingen.TerrainGen;

import cpw.mods.fml.common.eventhandler.Result;

public class ChunkProviderExample implements IChunkProvider {
    /** 随机数生成器 */
    private Random rand;

    private NoiseGeneratorOctaves field_14731_j;
    private NoiseGeneratorOctaves field_14732_k;
    private NoiseGeneratorOctaves field_14729_l;
    private NoiseGeneratorPerlin field_14730_m;

    /** 用于地形的 NoiseGeneratorOctaves */
    public NoiseGeneratorOctaves noiseGen5;

    /** 用于地形的 NoiseGeneratorOctaves */
    public NoiseGeneratorOctaves noiseGen6;

    public NoiseGeneratorOctaves mobSpawnerNoise;

    /** 对世界对象的引用 */
    private World worldObj;

    /** 是否生成地图结构（例如要塞） */
    private final boolean mapFeaturesEnabled;

    private WorldType field_14735_p;
    private final double[] field_14734_q;
    private final float[] parabolicField;
    private double[] stoneNoise = new double[256];

    private MapGenBase caveGenerator = new MapGenCaves();

    /** 要塞生成器 */
    private MapGenStronghold strongholdGenerator = new MapGenStronghold();

    /** 村庄生成器 */
    private MapGenVillage villageGenerator = new MapGenVillage();

    /** 废矿井生成器 */
    private MapGenMineshaft mineshaftGenerator = new MapGenMineshaft();

    private MapGenScatteredFeature scatteredFeatureGenerator =
        new MapGenScatteredFeature();

    /** 峡谷生成器 */
    private MapGenBase ravineGenerator = new MapGenRavine();

    /** 用于生成区块的生物群 */
    private BiomeGenBase[] biomesForGeneration;

    private double[] field_14727_d;
    private double[] field_14728_e;
    private double[] field_14725_f;
    private double[] field_14726_g;
}
```

```java
int[][] field_73219_j = new int[32][32];

private static final String __OBFID = "CL_00000396";

{
    caveGenerator = TerrainGen.getModdedMapGen(caveGenerator, CAVE);

    strongholdGenerator =
        (MapGenStronghold) TerrainGen.getModdedMapGen(strongholdGenerator, STRONGHOLD);

    villageGenerator =
        (MapGenVillage) TerrainGen.getModdedMapGen(villageGenerator, VILLAGE);

    mineshaftGenerator =
        (MapGenMineshaft) TerrainGen.getModdedMapGen(mineshaftGenerator, MINESHAFT);

    scatteredFeatureGenerator =
        (MapGenScatteredFeature) TerrainGen.getModdedMapGen(
            scatteredFeatureGenerator,
            SCATTERED_FEATURE
        );

    ravineGenerator = TerrainGen.getModdedMapGen(ravineGenerator, RAVINE);
}

public ChunkProviderExample(World par1World, long par2, boolean par4) {
    this.worldObj = par1World;
    this.mapFeaturesEnabled = par4;
    this.field_147435_p = par1World.getWorldInfo().getTerrainType();
    this.rand = new Random(par2);

    this.field_147431_j = new NoiseGeneratorOctaves(this.rand, 16);
    this.field_147432_k = new NoiseGeneratorOctaves(this.rand, 16);
    this.field_147429_l = new NoiseGeneratorOctaves(this.rand, 8);
    this.field_147430_m = new NoiseGeneratorPerlin(this.rand, 4);
    this.noiseGen5 = new NoiseGeneratorOctaves(this.rand, 10);
    this.noiseGen6 = new NoiseGeneratorOctaves(this.rand, 16);
    this.mobSpawnerNoise = new NoiseGeneratorOctaves(this.rand, 8);

    this.field_147434_q = new double[825];
    this.parabolicField = new float[25];

    for (int j = -2; j <= 2; ++j) {
        for (int k = -2; k <= 2; ++k) {
            float f = 10.0F / MathHelper.sqrt_float(
                (float) (j * j + k * k) + 0.2F
            );

            this.parabolicField[j + 2 + (k + 2) * 5] = f;
        }
    }

    NoiseGenerator[] noiseGens = {
        field_147431_j,
        field_147432_k,
        field_147429_l,
        field_147430_m,
        noiseGen5,
        noiseGen6,
        mobSpawnerNoise
    };

    noiseGens = TerrainGen.getModdedNoiseGenerators(
        par1World,
        this.rand,
        noiseGens
    );

    this.field_147431_j = (NoiseGeneratorOctaves) noiseGens[0];
    this.field_147432_k = (NoiseGeneratorOctaves) noiseGens[1];
    this.field_147429_l = (NoiseGeneratorOctaves) noiseGens[2];
    this.field_147430_m = (NoiseGeneratorPerlin) noiseGens[3];
    this.noiseGen5 = (NoiseGeneratorOctaves) noiseGens[4];
    this.noiseGen6 = (NoiseGeneratorOctaves) noiseGens[5];
    this.mobSpawnerNoise = (NoiseGeneratorOctaves) noiseGens[6];
}

public void func_147424_a(
    int p_147424_1_,
    int p_147424_2_,
    Block[] p_147424_3_
) {
    byte b0 = 63;

    this.biomesForGeneration =
        this.worldObj.getWorldChunkManager().getBiomesForGeneration(
            this.biomesForGeneration,
            p_147424_1_ * 4,
            p_147424_2_ * 4,
            10,
            10
        );

    this.func_147423_a(p_147424_1_ * 4, 0, p_147424_2_ * 4);

    for (int k = 0; k < 4; ++k) {
        int l = k * 5;
        int i1 = (k + 1) * 5;

        for (int j1 = 0; j1 < 4; ++j1) {
            int k1 = (l + j1) * 33;
            int l1 = (l + j1 + 1) * 33;
            int i2 = (i1 + j1) * 33;
            int j2 = (i1 + j1 + 1) * 33;

            for (int k2 = 0; k2 < 32; ++k2) {
                double d0 = 0.125D;
                double d1 = this.field_147434_q[k1 + k2];
                double d2 = this.field_147434_q[l1 + k2];
                double d3 = this.field_147434_q[i2 + k2];
                double d4 = this.field_147434_q[j2 + k2];
                double d5 =
                    (this.field_147434_q[k1 + k2 + 1] - d1) * d0;
                double d6 =
                    (this.field_147434_q[l1 + k2 + 1] - d2) * d0;
                double d7 =
                    (this.field_147434_q[i2 + k2 + 1] - d3) * d0;
                double d8 =
                    (this.field_147434_q[j2 + k2 + 1] - d4) * d0;

                for (int l2 = 0; l2 < 8; ++l2) {
                    double d9 = 0.125D;
                    double d10 = this.field_147434_q[l1 + k2];

                    doubledouble11 = =...
                }
            }
        }
    }
}
```

```text
444

2

2

222222

11111111111111111111111

111111

1111

11

1

12

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1

1
```



1



111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111

111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111

111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111

111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111

111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111

111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111

111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111



```java
this.villageGenerator.func_151539_a(this, this.worldObj, par1, par2, ablock);
this.strongholdGenerator.func_151539_a(this, this.worldObj, par1, par2, ablock);
this.scatteredFeatureGenerator.func_151539_a(this, this.worldObj, par1, par2, ablock);

Chunk chunk = new Chunk(this.worldObj, ablock, abyte, par1, par2);
byte[] abyte1 = chunk.getBiomeArray();
for (int k = 0; k < abyte1.length; ++k)
{
    abyte1[k] = (byte)this.biomesForGeneration[k].biomeID;
}
chunk.generateSkylightMap();
return chunk;

private void func_147423_a(int p_147423_1_, int p_147423_2_, int p_147423_3_)
{
    double d0 = 684.412D;
    double d1 = 684.412D;
    double d2 = 512.0D;
    double d3 = 512.0D;
    this.field_147426_g = this.noiseGen6.generateNoiseOctaves(this.field_147426_g, p_147423_1_, p_147423_3_, 5, 5, 200.0D, 200.0D, 0.5D);
    this.field_147427_d = this.field_147429_l.generateNoiseOctaves(this.field_147427_d, p_147423_1_, p_147423_2_, p_147423_3_, 5, 33, 5, 8.555150000000001D, 4.277575000000001D, 8.555150000000001D);
    this.field_147428_e = this.field_147431_j.generateNoiseOctaves(this.field_147428_e, p_147423_1_, p_147423_2_, p_147423_3_, 5, 33, 5, 684.412D, 684.412D, 684.412D);
    this.field_147425_f = this.field_147432_k.generateNoiseOctaves(this.field_147425_f, p_147423_1_, p_147423_2_, p_147423_3_, 5, 33, 5, 684.412D, 684.412D, 684.412D);
    boolean flag1 = false;
    boolean flag = false;
    int l = 0;
    int i1 = 0;
    double d4 = 8.5D;
    for (int j1 = 0; j1 < 5; ++j1)
    {
        for (int k1 = 0; k1 < 5; ++k1)
        {
            float f = 0.0F;
            float f1 = 0.0F;
            float f2 = 0.0F;
            byte b0 = 2;
            BiomeGen biomegen = this.biomesForGeneration[j1 + 2 + (k1 + 2) * 10];
            for (int l1 = -b0; l1 <= b0; ++l1)
            {
                for (int i2 = -b0; i2 <= b0; ++i2)
                {
                    BiomeGen biomegen1 = this.biomesForGeneration[j1 + l1 + 2 + (k1 + i2 + 2) * 10];
                    float f3 = biomegen1.rootHeight;
                    float f4 = biomegen1.heightVariation;
                    if (this.field_147435_p == WorldType.AMPLIFIED && f3 > 0.0F)
                    {
                        f3 = 1.0F + f3 * 2.0F;
                        f4 = 1.0F + f4 * 4.0F;
                    }
                    float f5 = this.parabolicField[l1 + 2 + (i2 + 2) * 5] / (f3 + 2.0F);
                    if (biomegen1.rootHeight > biomegen.rootHeight)
                    {
                        f5 /= 2.0F;
                    }
                    f += f4 * f5;
                    f1 += f3 * f5;
                    f2 += f5;
                }
            }
        }
    }
    f /= f2;
    f1 /= f2;
    f = f * 0.9F + 0.1F;
    f1 = (f1 * 4.0F - 1.F) / 8.0F;
    double d2 = this.field_147426_g[i1] / 800.0D;
    if (d2 < 0.0D)
    {
        d2 = -d2 * 0.3D;
    }
    d2 = d2 * 3.0D - 2.0D;
    if (d2 < 0.0D)
    {
        d2 /= 2.0D;
        if (d2 < -1.0D)
        {
            d2 = -1.0D;
        }
        d2 /= 1.4D;
        d2 /= 2.0D;
    }
    else
    {
        if (d2 > 1.0D)
        {
            d2 = 1.0D;
        }
        d2 /= 8.0D;
    }
    ++i1;
    double d13 = (double)f1;
    double d14 = (double)f;
    d13 += d2 * 0.2D;
    d13 = d13 * 8.5D / 8.0D;
    double d5 = 8.5D + d13 * 4.0D;
    for (int j2 = 0; j2 < 33; ++j2)
    {
        double d6 = ((double)j2 - d5) * 2.0D * 28.0D / 256.0D / d14;
        if (d6 < 0.0D)
        {
            d6 *= 4.0D;
        }
        double d7 = this.field_147428_e[l] / 52.0D;
        double d8 = this.field_147425_f[l] / 52.0D;
        double d9 = (this.field_147427_d[l] / 10.0D + 1.D) / 2.0D;
        double d10 = MathHelper.denormalize(d7, d8, d9) - d6;
        if (j2 > 29)
        {
            double d11 = (double)(float)(j2 - 29) / 3.0F;
            d10 = d10 * (1.0D - d11) - -10.0D * d11;
        }
        this.field_147434_q[l] = d10;
        ++l;
    }
}

/**
 * Checks to see if a chunk exists at x, y
 */
public boolean chunkExists(int par1, int par2)
{
    return true;
}

/**
 * Populates chunk with ores etc etc
 */
public void populate(IChunkProvider par1IChunkProvider, int par2, int par3)
{
    BlockFalling.fallInstantly = true;
    int k = par2 * 16;
    int l = par3 * 16;
    BiomeGenBase biomegenbase = this.worldObj.getBiomeGenForCoords(k + 16, l + 16);
    this.rand.setSeed(this.worldObj.getSeed());
    long i1 = this.rand.nextLong() / 2L * 2L + 1L;
    long j1 = this.rand.nextLong() / 2L * 2L + 1L;
    this.rand.setSeed((long)par2 * i1 + (long)par3 * j1 ^ this.worldObj.getSeed());
    boolean flag = false;
    MinecraftForge.EVENT_BUS.post(new PopulateChunk.Pre(par1IChunkProvider, worldObj, rand, par2, par3, flag));
    if (this.mapFeatures)
    {
        this.mineshaftGenerator.generateStructuresInChunk(this.worldObj, this.rand, par2, par3);
        this.villageGenerator.generateStructuresInChunk(this.worldObj, this.rand, par2, par3);
        this.strongholdGenerator.generateStructuresInChunk(this.worldObj, this.rand, par2, par3);
        this.scatteredFeatureGenerator.generateStructuresInChunk(this.worldObj, this.rand, par2, par3);
    }
    int k1;
    int l1;
    int i2;
    if (biomegenbase != BiomeGenBase.desert && biomegenbase != BiomeGenBase.Hills && !flag && this.rand.nextInt(4) == 0)
    {
        k1 = k + this.rand.nextInt(16) + 8;
        l1 = this.rand.nextInt(256);
        i2 = l + this.rand.nextInt(16) + 8;
        (new WorldGenLakes(Blocks.water)).generate(this.worldObj, this.rand, k1, l1, i2);
    }
    if (TerrainGen.populate(par1IChunkProvider, worldObj, rand, par2, par3, LAVA) && !flag && this.rand.nextInt(8) == 0)
    {
        k1 = k + this.rand.nextInt(16) + 8;
        l1 = this.rand.nextInt(this.rand.nextInt(248) + 8);
        i2 = l + this.rand.nextInt(16) + 8;
        if (l1 < 63 || this.rand.nextInt(10) == 0)
        {
            (new WorldGenLakes(Blocks.lava)).generate(this.worldObj, this.rand, k1, l1, i2);
        }
    }
    boolean doGen = TerrainGen.populate(par1IChunkProvider, worldObj, rand, par2, par3, DUNGEON);
    for (k1 = 0; doGen && k1 < 8; ++k1)
    {
        l1 = k + this.rand.nextInt(16) + 8;
        i2 = this.rand.nextInt(256);
        int j2 = l + this.rand.nextInt(16) + 8;
        (new WorldGenDungeons()).generate(this.worldObj, this.rand, l1, i2, j2);
    }

    biomegenbase.decorate(this.worldObj, this.rand, k, l);
}
```

```java
if (TerrainGen.populate(par1IChunkProvider, worldObj, rand, par2, par3, flag, ANIMALS))
{
    SpawnerAnimals.performWorldGenSpawning(this.worldObj, biomegenbase, k + 8, l + 8, 16, 16, this.rand);
}
k += 8;
l += 8;
doGen = TerrainGen.populate(par1IChunkProvider, worldObj, rand, par2, par3, flag, ICE);
for (k1 = 0; doGen && k1 < 16; ++k1)
{
    for (l1 = 0; l1 < 16; ++l1)
    {
        i2 = this.worldObj.getPrecipitationHeight(k + k1, l + l1);
        if (this.worldObj.isBlockFreezable(k1 + k, i2 - 1, l1 + l))
        {
            this.worldObj.setBlock(k1 + k, i2 - 1, l1 + l, Blocks.ice, 0, 2);
        }
        if (this.worldObj.func_147478_e(k1 + k, i2, l1 + l, true))
        {
            this.worldObj.setBlock(k1 + k, i2, l1 + l, Blocks.snow_layer, 0, 2);
        }
    }
}
MinecraftForge.EVENT_BUS.post(new PopulateChunkEvent.Post(par1IChunkProvider, worldObj, rand, par2, par3, flag));
BlockFalling.fallInstantly = false;
```

/**

 * 两种操作模式：如果传递 `true`，则一次性保存所有区块。如果传递 `false`，则最多保存两个区块。

 * 如果所有区块都已保存，返回 `true`。

 */

public boolean saveChunks(boolean par1, IProgressUpdate par2IProgressUpdate)

{

    return true;

}

/**

 * 保存不与任何区块关联的额外数据。不会在自动保存时保存，仅在世界卸载时保存。目前尚未

* 实现。

 */

public void saveExtraData() {}

/**

 * 卸载标记为要卸载的区块。不能保证卸载每一个此类区块。

 */

public boolean unloadQueuedChunks()

{

    return false;

}

/**

 * 返回 `IChunkProvider` 是否支持保存。

 */

public boolean canSave()

{

    return true;

}

/**

 * 将实例数据转换为可读的字符串。

 */

public String makeString()

{

    return "RandomLevelSource";

}

/**

 * 返回可以在给定位置生成的指定类型生物列表。

 */



```java
public List getPossibleCreatures(EnumCreatureType par1EnumCreatureType, int par2, int par3, int par4) {
    BiomeGenBase biomegenbase = this.worldObj.getBiomeGenForCoords(par2, par4);

    return par1EnumCreatureType == EnumCreatureType.monster
        && this.scatteredFeatureGenerator.func_143030_a(par2, par3, par4)
        ? this.scatteredFeatureGenerator.getScatteredFeatureSpawnList()
        : biomegenbase.getSpawnableList(par1EnumCreatureType);
}

public ChunkPosition func_147416_a(World p_147416_1_, String p_147416_2_, int p_147416_3_, int p_147416_4_, int p_147416_5_) {
    return "Stronghold".equals(p_147416_2_) && this.strongholdGenerator != null
        ? this.strongholdGenerator.func_151545_a(
            p_147416_1_,
            p_147416_3_,
            p_147416_4_,
            p_147416_5_
        )
        : null;
}

public int getLoadedCount() {
    return 0;
}

public void recreateStructures(int par1, int par2) {
    if (this.mapFeatures) {
        this.mineshaftGenerator.func_151539_a(this, this.worldObj, par1, par2, (Block[])[]);
        this.villageGenerator.func_151539_a(this, this.worldObj, par1, par2, (Block[])[]);
        this.strongholdGenerator.func_151539_a(this, this.worldObj, par1, par2, (Block[])[]);
        this.scatteredFeatureGenerator.func_151539_a(this, this.worldObj, par1, par2, (Block[])[]);
    }
}
```

### 自定义群系

自定义群系确实可以让一个 Mod 脱颖而出。为了让群系工作，必须添加以下代码：

```java
static BiomeGenBase example = new BiomeGenExample(5).setBiomeName("Example");

BiomeManager.addBiome(example);
```

#### BiomeGenExample

```java
package com.uppy.smod;

import java.util.Random;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;
import net.minecraft.init.Blocks;
import net.minecraft.world.World;
import net.minecraft.world.biome.BiomeGenBase;
import net.minecraft.world.gen.feature.WorldGenAbstract;
import net.minecraft.world.gen.feature.WorldGenDesert;
import net.minecraft.world.gen.feature.WorldGenJungle;
import net.minecraft.world.gen.feature.WorldGenShrub;
import net.minecraft.world.gen.feature.WorldGenTrees;

public class BiomeGenExample extends BiomeGenBase {
    public BiomeGenExample(int par1) {
        super(par1);

        this.spawnableCreatureList.clear();
        this.topBlock = Blocks.grass;
        this.fillerBlock = Blocks.dirt;
        this.spawnableCreatureList.clear();
        this.spawnableMonsterList.clear();
        this.spawnableWaterCreatureList.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();

        this.theBiomeDecorator.cactiPerChunk = 0;
        this.theBiomeDecorator.deadBushPerChunk = 3;
        this.flowers.clear();
    }
}
```



```java
this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cactiPerChunk = 0;
this.theBiomeDecorator.deadBushPerChunk = 3;
this.flowers.clear();

this.theBiomeDecorator.cacti.Chunk = 0;
this.theBiomeDecorator.deadBush.Chunk = 3;
this.clear();

this.theBiomeDecorator.cacti.Chunk = 0;
this.theBiomeDecorator.deadBush.Chunk = 3;
this...clear();

this.theBiomeDecorator.c..Chunk = 0;
this.theBiomeDecorator.dead.Chunk = 3;
this.....
this..BiomeDecorator.... = 0;
.theBiome...
.
 = 3;
....
}

@Override
public void decorate(World par1World, Random par2Random, int par3, int par4)
{
    super.decorate(par1World, par2Random, par3, par4);

    if (par2Random.nextInt(1000) == 0)
    {
        int k = par3 + par2Random.nextInt(16) + 8;
        int l = par4 + par2Random.nextInt(16) + 8;

        WorldGenDesert worlderts = new WorldGenDesert();
        worlderts.generate(par1World, par2Random, k, par1World.getHeight(k), l);
    }
}
}
```

### 自定义 AI

如果你有一个生物，你希望它是独特的。让你的生物独特的简单方法是为它添加 `AI`。这可以是完全自定义的，也可以现有 `AI` 的适配。你也将看到 `AI` 的示例。

#### 受伤时逃跑

以下 `AI` 代码会让生物在受伤时逃跑，在情况下，设置为心形。

```java
package com.uppy.smod.ai;

import net.minecraft.entity.Creature;
import net.minecraft.entity.ai.EntityIBase;
import net.minecraft.entity.ai.RandomPositionGenerator;
import net.minecraft.util.Vec3;

public class EntityIFleeOnHurt extends EntityIBase
{
    private Creature theEntityCreature;
    private double speed;
    private double randPosX;
    private double randPosZ;

    public EntityIFleeOnHurt(Creature par1Creature, double par2)
    {
        this.theEntityCreature = par1Creature;
        this.speed = par2;
        this.setMutexBits(1);
    }

    /**
     * 返回 EntityIBase 是否开始执行。
     */

    @Override
    public boolean shouldExecute()
    {
```



```java
if (this.theEntityCreature.getHealth() > 4F)
{
    return false;
}
else
{
    Vec3 vec3 = RandomPositionGenerator.findRandomTarget(this.theEntityCreature, 5, 4);

    if (vec3 == null)
    {
        return false;
    }
}
```

```java
this.randPosX = vec3.xCoord;
this.randPosY = vec3.yCoord;
this.randPosZ = vec3.zCoord;

return true;
}

/**
 * 执行单次性任务或开始执行连续任务
 */
@Override
public void startExecuting()
{
    this.theEntityCreature.getNavigator().tryMoveToXYZ(this.randPosX, this.randPosY, this.randPosZ, this.speed);
}

/**
 * 返回正在执行中的 EntityAIBase 是否应该继续执行
 */
@Override
public boolean continueExecuting()
{
    return !this.theEntityCreature.getNavigator().noPath();
}
```

#### 夜间攻击

以下列表 A.18 中的 AI 代码将确保使用此 AI 的实体仅在夜间伤害目标。这是对 `EntityAIAttackOnCollide` 的适配版本。

**列表 A.18 EntityAIAttackOnCollideNight**

点击此处查看代码图像

```java
package com.wuppy.samsmod.ai;

import net.minecraft.entity.EntityCreature;
import net.minecraft.entity.EntityLivingBase;
import net.minecraft.entity.ai.EntityAIBase;
import net.minecraft.pathfinding.PathEntity;
import net.minecraft.pathfinding.PathPoint;
import net.minecraft.util.MathHelper;
import net.minecraft.world.World;

@SuppressWarnings("rawtypes")
public class EntityAIAttackOnCollideNight extends EntityAIBase
{
    World worldObj;
    EntityCreature attacker;

    /**
     * 递减的刻数数量，允许实体在刻数达到 0 时进行攻击。
     */
    int attackTick;

    /** 生物靠近目标的速度 */
    double speedTowardsTarget;

    /**
     * 当为 true 时，生物将继续追逐目标，即使它现在无法找到目标的路径。
     */
    boolean longMemory;

    /** 我们的实体的 PathEntity。 */
    PathEntity entityPathEntity;

    Class classTarget;
    private int field_75445_i;
    private int failedPathFindingPenalty;

    public EntityAIAttackOnCollideNight(EntityCreature par1EntityCreature, Class par2Class, double par3, boolean par5)
    {
        this(par1EntityCreature, par3, par5);
        this.classTarget = par2Class;
    }

    public EntityAIAttackOnCollideNight(EntityCreature par1EntityCreature, double par2, boolean par4)
    {
        this.attacker = par1EntityCreature;
        this.worldObj = par1EntityCreature.worldObj;
        this.speedTowardsTarget = par2;
        this.longMemory = par4;
        this.setBits(3);
    }

    /**
     * 返回 EntityAIBase 是否应该开始执行。
     */
    @SuppressWarnings("unchecked")
    @Override
    public boolean shouldExecute()
    {
        EntityLivingBase livingbase = this.attacker.getAttackTarget();

        if (livingbase == null)
        {
            return false;
        }
        else if (!livingbase.isAlive())
        {
            return false;
        }
        else if (this.classTarget != null && !this.classTarget.isAssignableFrom(livingbase.getClass()))
        {
            return false;
        }
        else if (this.worldObj.isDaytime())
        {
            return false;
        }
        else
        {
            if (--this.field_75445_i <= 0)
            {
                this.entityPathEntity = this.attacker.getNavigator().getPathToEntityLiving(livingbase);
                this.field_75445_i = 4 + this.attacker.RNG().nextInt(7);
                return this.entityPathEntity != null;
            }
            else
            {
                return true;
            }
        }
    }

    /**
     * 返回正在执行中的 EntityAIBase 是否应该继续执行。
     */
    @Override
    public boolean continueExecuting()
    {
        EntityLivingBase entitylivingbase = this.attacker.getAttackTarget();

        return entitylivingbase == null
            ? false
            : (!entitylivingbase.isEntityAlive()
                ? false
                : (!this.longMemory
                    ? !this.attacker.getNavigator().noPath()
                    : this.attacker.isWithinHomeDistance(
                        MathHelper.floor_double(entitylivingbase.posX),
                        MathHelper.floor_double(entitylivingbase.posY),
                        MathHelper.floor_double(entitylivingbase.posZ)
                    )));
    }

    /**
     * 执行单次性任务或开始执行连续任务。
     */
    @Override
    public void startExecuting()
    {
        this.attacker.getNavigator().setPath(this.entityPathEntity, this.speedTowardsTarget);
        this.field_75445_i = 0;
    }

    /**
     * 重置任务。
     */
    @Override
    public void resetTask()
    {
        this.attacker.getNavigator().clearPath();
    }

    /**
     * 更新任务。
     */
    @Override
    public void updateTask()
    {
        EntityLivingBase entitylivingbase = this.attacker.getAttackTarget();

        this.attacker.getLookHelper().setPositionWithEntity(livingbase, 30.0F, 30.0F);

        if ((this.longMemory || this.attacker.getEntitySenses().canSee(livingbase)) && --this.field_75445_i <= 0)
        {
            this.field_75445_i = failedPathFindingPenalty + 4 + this.attacker.RNG().nextInt(7);
            this.attacker.getNavigator().tryMoveToEntityLiving(livingbase, this.speedTowardsTarget);

            if (this.attacker.getNavigator().getPath() != null)
            {
                PathPoint finalPathPoint = this.attacker.getNavigator().getPath().getFinalPoint();

                if (finalPathPoint != null && entitylivingbase.getDistanceSq(finalPathPoint.xCoord, finalPathPoint.yCoord, finalPathPoint.zCoord) < 1)
                {
                    failedPathPenalty = 0;
                }
                else
                {
                    failedPathPenalty += 10;
                }
            }
            else
            {
                failedPathPenalty += 10;
            }
        }

        this.attackTick = Math.max(this.attackTick - 1, 0);

        double d0 = (double)(this.attacker.width * 2.0F) * (this.attacker.width * 2.0F);

        if (this.attacker.getDistanceSq(entitylivingbase.posX, entitylivingbase.minY, entitylivingbase.posZ) <= d0)
        {
            if (this.attackTick <= 0)
            {
                this.attackTick = 20;

                if (this.attacker.getHeldItem() != null)
                {
                    this.attacker.swingItem();
                }

                this.attacker.attackEntity(livingbase);
            }
        }
    }
}
```

#### 使用你的自定义 AI

你的自定义 AI 代码可以像任何其他 AI 一样使用。不需要以任何方式对其注册。以下代码像任何其他 `EntityAI` 一样使用了 `EntityAIFleeOnurt`：

点击此处查看代码图像

```java
this.tasks.addTask(0, new EntityAIFleeHurt(this, 1.1D));
```

## 生成粒子

有时你想在你的区块或物品周围生成粒子以让它们看起来更好看。列表 A.19 显示了一个名为 `randomDisplayTick` 的方法，这是一个用于区块生成自定义粒子的方法。实体和物品也有类似的方法。

**列表 A.19 生成粒子**

点击此处查看代码图像

```java
@SideOnly(Side.CLIENT)
@Override
public void randomDisplayTick(World par1World, int par2, int par3, int par4, Random par5Random)
{
    super.randomDisplayTick(par1World, par2, par3, par4, par5Random);

    if (par5Random.nextInt(2) == 0)
    {
        double var1 = (double)((float)par2 + par1World.rand.nextFloat());
        double var2 = (double)((float)par3 + par1World.rand.nextFloat());
    }
}
```

```java
double var3 = (double)((float)par4 + par1World.rand.nextFloat());

par1World.spawnParticle("smoke", var1, var2, var3, 0.0D, 0.0D, 0.0D);
par1World.spawnParticle("flame", var1, var2, var3, 0.0D, 0.0D, 0.0D);
}
```

### 播放声音

为你的物品、方块或实体添加特定的音效通常是个好主意。以下代码将播放声音：

点击此处查看代码图像

```java
worldObj.playSound(x, y, z, "step.wood", 1F, 1F, true);
```

声音名称的完整列表可以在 [`minecraft.gamepedia.com/Sounds.json`](http://minecraft.gamepedia.com/Sounds.json) 找到。

### 为物品使用模型

有时，你希望你的物品看起来比普通的扁平图片更华丽。在这种情况下，你可以尝试为你的物品使用自定义模型。要实现这一点，你需要一个自定义的 `Render` 类，它在列表 A.20 中有所示。

**列表 A.20 RenderExampleItem**

点击此处查看代码图像

```java
package com.wuppy.samsmod;

import net.minecraft.client.Minecraft;
import net.minecraft.item.ItemStack;
import net.minecraft.util.ResourceLocation;
import net.minecraftforge.client.IItemRenderer;
import org.lwjgl.opengl.GL11;

public class RenderExampleItem implements IItemRenderer
{
    private ModelExample model;
```



```java
public RenderExampleItem()
{
    model = new ModelExample();
}

@Override
public boolean handleRenderType(ItemStack item, ItemRenderType type)
{
    return true;
}

@Override
public boolean shouldUseRenderHelper(ItemRenderType type, ItemStack item, ItemRendererHelper helper)
{
    return true;
}

@Override
public void renderItem(ItemRenderType type, ItemStack item, Object... data)
{
    GL11.glPushMatrix();
    GL11.glScalef(-1F, -1F, 1F);

    switch (type)
    {
        case INVENTORY:
            GL11.glTranslatef(0, 0.12F, 0);
            break;

        case EQUIPPED:
            GL11.glTranslatef(-0.8F, -0.2F, 0.7F);
            break;

        case EQUIPPED_FIRST_PERSON:
            GL11.glTranslatef(0, -0.7F, 0.7F);
            break;

        default:
            Minecraft.getMinecraft().renderEngine.bindTexture(
                new ResourceLocation("textures/entity/zombie.png")
            );
    }

    model.render(null, 0.0F, 0.0F, -0.1F, 0.0F, 0.0F, 0.025F);
    GL11.glPopMatrix();
}
```

此`Render`类可以使用任何类型的模型；只需确保在构造函数中设置了它即可。在这种情况下使用的纹理是僵尸纹理，但你可以使用任何需要的纹理。为了让你的模型看起来好看，你可能需要更改`render`方法中的某些值。你需要使用以下代码为你想要以此方式渲染的物品注册此`Render`类：点击此处查看代码图片。

```java
MinecraftForgeClient.registerItemRenderer(SamsMod.exampleItem, new RenderExampleItem());
```



### 符号

- `{}`（括号），27
- `//` 注释，27
- `/* */` 注释，27
- `2x2` 网格空间，42-43
- `3x3` 网格空间，42

### A

- `addArmorMaterial` 方法，111-112
- `addBlockDrops` 方法，302
- `addDungeonMob` 方法，48
- `adding`。另参见向创造模式菜单添加方块，126
- `items`，54-57
- `to` 创造模式，126
- `finished` ItemKey，64-65
- `item` 文件，57-58
- `multiple` 物品，67-70
- `names`，58-61
- `pre` 方法，54-57
- `textures`，61-64
- `variables`，56
- `local` 物品，58-61
- `to` 物品，72-73
- `constructors`，72-73
- `getIconFromDamage` 方法，76-77
- `image` 注册，75-76
- `item` 名字，73-74
- `mod` 文件 ItemKey，79-80
- `textures`，75
- `mods` 到网站，328-329
- `textures` 到方块，139-143
- `addItem` 方法，49
- `addRecipe` 方法，41
- `addSheless` 方法，40
- `addSpawn` 方法，27
- `addSpawn` 方法，38
- `addTool` 方法，95
- `applyEntityAttributes` 方法，278
- `alternative`，26
- `AI`，313
- `AI`，390
- `attacking`，386
- `fleeing`，384
- `annotations`，23
- `@Sided`，246
- `@SubscribeEvent`，298

人工智能。参见 `AI`（人工智能）

`assets` 文件夹，58-59

攻击村民，277

夜间攻击，386-390

# 音频

`playSound` 方法，391

脚步声，126-127

Eclipse 中的自动补全，184-185

自动更新检查，353-356

# 斧

代码列表，99

游戏内，101

纹理，101

### B

基础值，278

#### 行为，更改

实体行为，298-302

生物行为，363-364

#### 浆果物品

`ItemBerry` 类，84-86

mod 文件代码，84

`BiomeGenBase` 方法，383

`BiomeGenExample` 类，383-384

生物群系，自定义，383-384

抗爆性，126

Blender，263

`Block` 类，129

`BlockCustomRenderWoodExample` 类，343-346

`BlockRotateExample` 类，342-343

# 方块

添加到创造模式菜单，126

`BlockSamStone` 类，124-126

创建，124-126

自定义，126-129

游戏内，131

半块，148-151

纹理，129-131，141-142

与物品相比，53-54

与方实体相比，123-124

## 自定义方块渲染

`BlockCustomRenderWoodExample` 类，343-346

`RenderCustomWoodExample` 类，346-350

自定义，126-129

抗爆性，126

硬度，126

采集等级，127-128

本地化，128-129

脚步声，126-127

编辑，302-303

随机化，299

解释，123-124

半块，148-151

初始化，124

元数据，135

方块边界，152

方块注册，136

创造模式菜单中，135-136

`ItemBlock` 类，136-138

`ItemSam` 类，137-139

纹理，139-143

mod 文件代码，124

名称，126

植物，152

创建，152-155

作物，155-157

自定义，165-171

游戏内，170-171

自然生长，158-159

随机植物，157-158

种子，159-165

注册，124，136

旋转，342-343

石质阶，123

纹理，129-131

添加，139-143

侧面纹理，145-147

方实体块，176-180

TNT 方块，357-359

不可破坏方块，127

`Blocks` 类，129

`BlockSamPlant` 类，167-170

`BlockSamPlant` 构造函数，153

IIcon 代码，153-154

`BlockSamPlant` 构造函数，153

`BlockSamStone` 类，124-126

自定义，126-129

游戏内，131

半块，148-151

纹理，129-131

Sam 的墙，141-142

侧面纹理，145-147

`BlockSamTE` 类，176-180

右键点击，185-188

`BlockSamTE` 构造函数，177

`BlockTNTExample` 类，357-359

身体部分，渲染，268-270

靴子。参见 `armor`

边界（方块），148-151

大括号 `{}`，27

大括号选项（代码格式），213

### C

Cadenhead, Rogers，338

`canPlaceBlockOn` 方法，165

#### 更改

实体行为，298-302

生物行为，363-364

代理，313

通道（IRC），加入，335

聊天。参见 `IRC`（网络中聊天）

检查更新，353-356

`checkUpdate` 方法，355-356

箱子物品，49

添加，49

移除，49

`ChestGenHooks` 类

- `addItem` 方法，49
- `removeItem` 方法，49

胸甲。参见 `armor`

`ChunkProviderExample` 类，369-382

类。另见 `methods`

AdvancedModelLoader，263

# `BiomeGenExample`，383-384

# `Block`，129

# `BlockCustomRenderWoodExample`，343-346

# `BlockRotateExample`，342-343

# `Blocks`，129

# `BlockSamPlant`，167-170

## `BlockSamPlant` 构造函数，153

## `IIcon` 代码，153-154

# `BlockSamStone` 类

## 创建，124-126

## 定制，126-129

## 游戏内，131

## 纹理，141-142

# `BlockSamTE`

## 半方块，148-151

## 有方向纹理，145-147

## 纹理，129-131

## 创建，176-180

## 右键点击，185-188

# `BlockTNTExample`，357-359

# `ChestGenHooks`

## `addItem` 方法，49

## `removeItem` 方法，49

# `ChunkProviderExample`，369-382

# `ClientProxySam`，248，272，291

# `CommonProxySam`，247

# `Config`，341-342

## 创建，31-33

# `DungeonHooks`，48

## `addDungeonMob` 方法，48

## `removeDungeonMob` 方法，48

# `Entity`，245，250

# `EntityAI`，276

## `EntityAIAttackOnCollideNight`，386-390

## `EntityAIFleeOnHurt`，384-386

# `EntityCaveSpiderCustom`，363-364

# `EntityExamplePrimed`，359-361

# `EntityFX`，245

# `EntityMob`，275

# `EntitySamMob`，249-250

## `AI`，276-277

## `base` 值，278

## 掉落物，278-280

## 继承 `EntityMob` 的 `EntitySamMob`，275

## 完成的 `EntitySamMob`，279-280

## 游戏内，280

# `EntitySamThrowable`，284-287

# `EntityThrowable`，284

# `EventHandler`，195-202

# `ExampleMod`，24-25

# `ExampleTab`，356

## `fields`，25-26

## `final` 字段，25-26

## `public` 字段，25

## `static` 字段，25

# `ForgeDirection`，147

## 导入，23

# `ISimpleBlockRenderingHandler`，149

# `ItemBerry`，84-86

## 构造函数，85

## 空的 `Item` 文件，84

## `potion` 效果，89-91

## 纹理，85-86

# `ItemBlock`，136-138

# `ItemSamArmor`

## 护甲部件纹理，114，116-118

## 创建，113-118

## 游戏内，114

## 语言化，113

## mod 文件代码，112-113

# `ItemSamAxe`

## 代码列表，99

## 游戏内，101

## 纹理，101

# `ItemSamHoe`

## 代码列表，99

## 游戏内，101

## 纹理，101

# `ItemSamPaxel`

## 代码列表，104-105

## 创建，104-105

## `func_150893_a` 方法，105-106

## `func_150897_b` 方法，105-106

## 游戏内，107

## `hitEntity` 方法，106-107

## 语言化，107

## mod 文件代码，103

## 纹理，107

# `ItemSamPickaxe`，97-98，101

# `ItemSamPlant`，160

# `ItemSamSeed`，159-165

# `ItemSamShovel`

## 代码列表，100

## 游戏内，101

## 纹理，101

# `ItemSamStone`，137-139

# `ItemSamSword`

## 代码列表，100

## 游戏内，101

## 纹理，101

# `ItemSamThrow`，287-290

# `IWorldGenerator`，196-197

# `ModBlocks`，319-320

# `ModelSamMob`

## 完成的 `ModelSamMob`，266-268

## `setRotationAngles` 方法，268-270

# `OreDictionary`，202-204

## 合配方，203-204

## `registerOre` 方法，202-203

## `public` 类，24-25

# `Render`，270-271

# `RenderCustomWoodExample`，346-350

# `RenderExampleItem`，391-393

# `RenderExamplePrimed`，361-363

# `RenderingRegistry`，272

# `RenderLiving`，271

# `RenderSamMob`，270-271

# `SamDungeon`，235

# `SamEventHandler`，195-202

## `addOreSpawn` 方法，198-200

## 完成的 `SamEventHandler` 类，200-202，237-239

## 生成方法，197-198

## 初始 `SamEventHandler` 类，196

## `IWorldGenerator` 类，196-197

## 带有 `WorldGenSamPlant` 代码，215-219

# 清理，320-322

# 代码列表，314-319

# `ModBlocks`，319-320

# 字符串，24

# `TileEntityMobSpawner`（实体生成器实体），241-243

# `TileEntitySam`，180-183，190-192

# `ToolMaterial`（工具材质），95-96

# `UpdateChecker`（更新检查器），353-356

# `WorldGen`（世界生成），207-215

## 检查与放置，209

## 完成的 `WorldGenSamPlant`，210

## 初始的 `WorldGenSamPlant` 类，207

## 随机起始元数据，210

## 随机化位置，208-209

## `WorldGenSamPlant` 继承自 `WorldGenerator`，208

# `WorldGenCustomTreeExample`（世界生成自定义树示例），350-352

# `WorldGenSamDungeon`（世界生成示例地下城），236

# `WorldGenSamPlant`

## 检查与放置，209

## 完成的 `WorldGenSamPlant`，210

## 初始 `WorldGenSamPlant` 类，207

## 随机起始元数据，210

## 随机化位置，208-209

## `WorldGenSamPlant` 继承 `WorldGenerator`，208

# `WorldProviderExample`（世界提供者示例），367-369

# 清理

## Mod 类，314-322

## 包，312-313

## 客户端代理，272

## `ClientProxySam` 类，248，272，291

## 衣服，364-365

# 代码格式化

## 格式化窗口，211-212

## 格式化选项，212-215

## 新配置窗口，211

## 偏好窗口，211

# 命令

## `gradlew eclipse`，17

## `gradlew setupDecompWorkspace`，17

## 注释，27，213，337

## `CommonProxySam` 类，247

## 电脑属性窗口，10

## `Config` 类，341-342

## 配置，341-342

## 配置中。参见设置

## 构造函数，57

## `BlockSamPlant`，153

## `BlockSamStone`，125

## `BlockSamTE`（实体块），177

## `ItemBerry`，85

## `ItemSamArmor`，113

## `ItemSamPickaxe`，97

## `ItemSamPlant`，160

## 元数据，72-73

## 控制语句（代码格式化），213

## 复制代码，338

# 合成格

## `2x2` 格，42-43

## `3x3` 格，42

## 合成配方，40-41

## `GameRegistry`（游戏注册表），41-42

## 替代形状，42-44

## `createNewTile` 方法，178

## 创建。参见添加

## `addArmorMaterial` 方法，111-112

## `ArmorMaterial`（护甲材质），111-112

## `ItemSamArmor` 类，113-118

## mod 文件，112-113

## 块，124

## `BlockSamStone` 类，124-126

## 自定义块，126-129

## 半块块，148-151

## 侧面纹理，145-147

## 纹理，129-131，145

## 箱子物品，49

## 类，31-33

## 立方块，257-258

## 掉落物，278-280

## 实体。参见实体

## 实体模型，253

## 添加/移除立方块，257-258

## 下载并安装 `Techne`，253-254

## 编辑立方体属性，256-257

## 导出模型，259-263

## 模型特征，253-254

## `Techne` 模型创建，255

## 物品，54-57

## 完成的 `ItemKey` 文件，64-65，67

## 食物，84-89

## 物品文件，57

## `ItemGeneric` 示例，69-71

## 名字，58-61

## `preInit` 方法，54-57

## 纹理，61-64

## 变量，56

## `mod.info` 文件，326-327

## 实体生成器，241-243

## 实体。参见实体

# `addOreSpawn` 方法，[198-200]

# 完成 `SamEventHandler` 类，[200-202]

# 生成方法，[197-198]

# 初始 `SamEventHandler` 类，[196]

# `IWorldGenerator` 类，[196-197]

# 方块实体（tile entities），[180-183]

# 方块实体块，[176-180]

# `ToolMaterial`，[95-96]

## 工具

- 斧头，[99]
- 锄头，[99]
- 多功能镐（paxel），[103-107]
- 矿镐，[96-98]
- 铲子，[100]
- 剑，[100]

## 变量，[56]

# `WorldGen` 类，[207-215]

### 检查与放置，[209]

### 完成的 `WorldGenSamPlant`，[210]

### 初始 `WorldGenSamPlant` 类，[207]

### 随机起始元数据，[210]

### 随机化位置，[208-209]

### `WorldGenSamPlant` 继承 `WorldGenerator`

## 创造菜单

- 添加方块到，[126]
- 添加物品到，[58]
- 方块注册表，[136]
- 元数据中的，[135-136]

## `CreativeTabs`，自定义，[356]

## 作物，创建，[155-157]

## 立方体

- 添加/移除，[257-258]
- 编辑立方体属性，[256-257]

## 自定义

### AI，[384]

- 添加自定义 AI，[390]
- 夜间攻击，[386-390]
- 受到伤害时逃跑，[384-386]

### 护甲，[119]

- 衣服，[364-365]
- 效果，[365-367]
- 生物群系，[383-384]
- 方块，[126-129]
- 爆炸抗性，[126]
- 硬度，[126]
- 采集等级，[127-128]
- 本地化，[128-129]
- 步进音效，[126-127]
- 纹理，[129-131]
- `CreativeTabs`，[356]
- 维度，[367]
- `ChunkProvider` 类，[369-382]
- `WorldProvider` 类，[367-369]
- `ItemStacks`，[46]
- 植物，[165-171]
- `Render` 类，[391-393]
- `ToolMaterial`，[95-96]
- 工具（`ItemSamP` 类），[103-107]
- 代码列表，[104-105]
- 创建，[104-105]
- `func_150893_a` 方法，[105-106]
- `func_150897_b` 方法，[105-106]
- 游戏内，[107]
- `hitEntity` 方法，[106-107]
- 本地化，[107]
- Mod 文件代码，[103]
- 纹理，[107]
- 树木生成，[350-352]

### D

## 声明 Strings，[24]

## 开发环境

### Eclipse，设置，[16]

### Forge

- 解释，[8-9]
- 设置，[16-19]
- JDK（Java 开发包），设置，[9-15]
- MCP（Mod Coder Pack），[8]
- 概览，[7-8]

## 字典，`OreDictionary` 类，[202-204]

- 配方，[203-204]
- `registerOre` 方法，[202-203]
- 自定义维度，[367]
- `ChunkProvider` 类，[369-382]
- `WorldProvider` 类，[367-369]
- 显示行号，[86-89]

## 下载

- `MCdit`，[223-224]
- `Schematic` 转换器，[231]
- `Techne`，[253-254]
- `dropBlockAsItemWithChance` 方法，[166]

## 掉落

- 添加，[278-280]
- 编辑，[302-303]
- 随机化，[299]
- `DungeonHooks` 类，[48]
- `addDungeonMob` 方法，[48]
- `removeDungeonMob` 方法，[48]

## 地牢

- 生物。参见 `mobs`
- `SamDungeon` 类，[235]
- `WorldGenSamDungeon` 类，[236]
- 尘物品，[70-72]

### E

## Eclipse

- 自动补全，[184-185]
- 代码格式化
- 格式化窗口，[211-212]
- 格式化选项，[212-215]
- 新配置窗口，[211]
- 首选项窗口，[211]
- 行号，显示，[86-89]
- 设置，[16]
- `eclipse.exe` 文件，[16]
- `eclipse.org`，[16]
- `editCounter` 方法，[188]

## 编辑

- 方块掉落，[302-303]
- 立方体属性，[256-257]
- 效果（护甲），[365-367]
- 扔蛋能力，[303-307]
- 空物品文件，[57]
- `en_US.lang` 文件，[60]
- `enchantedSwordItemStack`，[41-42]

## 实体

### AI

- 添加到生物，[276-277]
- 夜间攻击，[386-390]
- 受到伤害时逃跑，[384-386]
- 改变行为，[298-302]

## 与区块相比，[123-124]

## 创建基础实体，[248-250]

### `EntitySamMob` 类，[249-250]

### `registerModEntity` 方法，[248-249]

### `Entity` 类，[245，250]

## 实体模型，使用 `Techne` 创建，[253]

### 添加/移除立方体，[257-258]

### 下载并安装 `Techne`，[253-254]

### 编辑立方体属性，[256-257]

### 导出模型，[259-263]

### 模型特性，[253-254]

### `Techne` 模型创建界面，[255]

### `EntitySamMob` 类，[249-250]

### `EntitySamThrowable` 类，[284-287]

### 解释，[54，245-246]

生物。参见生物

## 代理

### `ClientProxySam` 类，[248]

### `CommonProxySam` 类，[247]

### 创建，[246-247]

解释，[246]

### 移除，[297-298]

## 中的可投掷实体，[283-293，291-293]

### `ItemSamThrow` 类，[287-290]

### 注册，[283]

### 渲染，[290-291]

## 砖实体

### 添加到区块，[176-180]

### 创建，[180-183]

解释，[175-176]

### 服务器同步，[183-192]

### `TileEntitySam` 类，[180-183，190-192]

### `TNT` 实体，[359-361]

### `Entity` 类，[245，250]

### 实体模型，使用 `Techne` 创建，[253]

### 添加/移除立方体，[257-258]

### 下载并安装 `Techne`，[253-254]

### 编辑立方体属性，[256-257]

### 导出模型，[259-263]

### 模型特性，[253-254]

### `Techne` 模型创建界面，[255]

### `EntitySamMob` 类，[249-250]

### `EntitySamThrowable` 类，[284-287]

### 解释，[54，245-246]

### `EntityAI` 类，[276]

### `EntityIAackOnCollide` 类，[386-390]

### `EntityIFleeOnHurt` 类，[384-386]

### `EntityCustom` 类，[363-364]

### `EntityPrimed` 类，[359-361]

### `EntityFX` 类，[245]

### `EntityList` 文件，[48]

### `EntityMob` 类，[275]

### `EntitySamMob` 类，[249-250]

### AI，[276-277]

### 基础值，[278]

### 掉落，[278-280]

### `EntitySamMob` 继承 `EntityMob`，[275]

### 游戏中的 `EntitySamMob`，[279-280]

### `EntitySamThrowable` 类，[284-287]

### `EntityThrowable` 类，[284]

### 环境变量窗口，[13]

### `@EventHandler`，[26]

### `EventHandler` 类

### 创建，[195-202]

### `addOreSpawn` 方法，[198-200]

### 完成 `SamEventHandler` 类，[200-202]

### 生成方法，[197-198]

### 初始 `SamEventHandler` 类，[196]

### `IWorldGenerator` 类，[196-197]

解释，[195]

## 事件

### 抛蛋示例，[303-307]

### 初始化事件，[26]

### `LivingDropEvents`，[298-302]

### `PlayerInteractEvent`，[303-307]

### 注册，[303]

### 检查文件中的配方，[49-51]

## `ExampleMod`

### 代码列表，[18-19，21-22]

### `ExampleMod` 类，[24-25]

### 字段，[25-26]

### 方法，[26-27]

### 导入，[22-23]

### `@Mod` 行，[23-24]

### 包，[22-23]

### `ExampleTab` 类，[356]

### 爆炸，[286]

### 导出（Medit），[229]

## 导出

### 来自 `Techne` 的模型，[259-263]

### 使用 `Forge` 的 Mod，[325-327]

### 来自 `Medit` 的结构，[228-229]

## 继承

### `Entity` 类，[250]

### `EntityMob` 类，[275]

### `EntityThrowable` 类，[284]

### `RenderLiving` 类，[271]

### 扩展（文件），[60]

### F

### 字段，[25-26]

### 最终字段，[25-26]

### 公有字段，[25]

### 静态字段，[25]

### 文件

### `eclipse.exe`，[16]

### `en_US.lang`，[60]

### `EntityList`，[48]

### 文件扩展名，[60]

### `GameRegistry`，[41-42]

### `ItemKey`，[64-65，67-68]

### `ItemSamGeneric`，[69-71]

### `level.dat`，[227]

### `mcmod.info`，创建，[326-327]

检查配方结果，[49-51]

带有元数据的 mod 文件，[79-80]

带有 `preInit` 方法 mod 文件，[54-57]

`.obj` 文件，[263]

`final fields`，[25-26]

`final` 关键字，[25-26]

`寻找开源模组`，[336-337]

`受伤时逃跑`，[384-386]

## 文件夹

`assets`，[58-59]

文件夹结构，[60]

`lang`，[58-59]

源文件夹，[22]

## 食品

创建，[84]

`ItemBerry` 类，[84-86]

mod 文件代码，[84]

解释，[83-84]

`foodLevel`，[83-84]

`foodSaturationLevel`，[83-84]

药水效果，[89-91]

`foodSaturationLevel`，[83-84]

## Forge

箱子物品，[49]

添加，[49]

移除，[49]

`EventHandler` 类，[195]

解释，[8-9]

带有导出 mod，[325-327]

地下城中的生物群生成，[48]

添加生物组，[48]

移除生物组，[48]

设置，[16-19]

`ForgeDirection` 类，[147]

`forgeSrc` 库，[28-29]

`Formatter` 窗口，[211-212]

`代码格式`

`Formatter` 窗口，[211-212]

格式选项，[212-215]

新配置档窗口，[211]

偏好窗口，[211]

`func_149851_a` 方法，[155-156]

`func_149852_a` 方法，[155-156]

`func_149853_b` 方法，[155-157]

`func_150893_a` 方法，[105-106]

`func_150897_b` 方法，[105-106]

### G

`GameRegistry`，[41-42]

`generate` 方法，[197-198]

`generateEnd` 方法，[197-198]

`generateNether` 方法，[197，200]

`generateSurface` 方法，[197-198]

## 矿石生成

`EventHandler` 类，[195]

地界矿石生成，[200]

`OreDictionary` 类，[202-204]

游戏中的结果，[204]

`EventHandler` 类，[195-202]

植物，[207]

游戏中的结果，[219]

`EventHandler` 类，[215-219]

`WorldGen` 类，[207-215]

结构，[231-239]

树，[350-352]

`getArmorModel` 方法，[364-365]

`getArmorTexture` 方法，[117-118]

`getBlockData` 方法，[182]

`getCurrentArmor` 方法，[305]

`getDescriptionPacket` 方法，[188]

`getDropItem` 方法，[278]

`getDrops` 方法，[166-167]

`getIcon` 方法，[140，146-147]

`getIconFromDamage` 方法，[76-77]

`getItemDropped` 方法，[165-166]

`getMetadata` 方法，[137]

`getPlant` 方法，[161-162]

`getPlantMetadata` 方法，[161-162]

`getPlantType` 方法，[161-162]

`getQuantity` 方法，[165-166]

`getRenderType` 方法，[155]

`getSubBlocks` 方法，[135-136]

`getSubItems` 方法，[76-77]

`getUnlocalizedName` 方法，[74，137-138]

`GitHub 仓库`，[328-329]

`GlScale`，[257]

`gradlew eclipse` 命令，[17]

`gradlew setupcompWorkspace` 命令，[17]

`greyKey` 物品，[68]

### H

`half blocks`，[148-151]

`hardness of blocks`，[126]

`harvest level`，[127-128]

`helmet`。参见 `armor`

## HexChat

Edit EsperNet 窗口，[334]

安装，[333]

设置，[334-335]

`hitEntity` 方法，[106-107]

## hoe

代码列表，[99]

游戏中的，[101]

贴图，[101]

`受伤时逃跑`，[384-386]

### I

`IDEA（IntelliJ）`，[8]

`IDEs（集成开发环境）`，[8]

`IIcon`，[75，139，153-154]

图片注册，[75-76]

`import` 关键字，[23]

## 类，[23]

解释，[22-23]

世界，[227]

`ingot` 物品，[70-72]

`Init` 事件，[26]

`init` 方法，[26]

`初始化事件`，[26]

`初始化方块`，[124]

# MCEdit，[225]

# Schematic 转换器，[231-232]

# Techne，[253-254]

# 集成开发环境（IDEs），[8]

## IntelliJ IDEA，[8]

## 互联网中继聊天。查看 `IRC`（Internet Relay Chat）

## IRC（互联网中继聊天），[333]

- 安装，[333-335]
- 加入频道，[335]
- 设置，[334-335]

# ISimpleBlockRenderingHandler，[149]

## 项目文件，创建，[57-58]

## `ItemBerry` 类，[84-86]

- 构造函数，[85]
- 空的 `ItemBerry` 文件，[84]
- 药水效果，[89-91]
- 纹理，[85-86]

## `ItemBlock` 类，[136-138]

## `ItemKey`

- 添加到创造模式菜单，[58]
- 创建，[54-57]
- 完成的 `ItemKey` 文件，[64-65，67]
- 项目文件，[57-58]
- 名称，[58-61]
- `preInit` 方法，[54-57]
- 纹理，[61-64]
- 变量，[56]
- 多个项目的 `ItemKey` 文件，[68]

### 元数据

- 构造函数，[72-73]
- 项目名称，[73-74]
- 带有元数据的 `ItemKey`，[77-78]
- 带有元数据键的 mod 文件，[79-80]
- 纹理，[75]
- 多个项目，添加到同一个文件，[67-70]

### 名称

- 本地化，[58-61]
- 未本地化的名称，[58]

# 项目

- 添加到创造模式菜单，[58]
- 护甲，[111]
- 护甲碎片纹理，[114，116-118]
- `ArmorMaterial`，[111-112]
- 衣服，[364-365]
- 创建，[112-118]
- 定制，[119]
- 效果，[365-367]
- 游戏内，[114]
- 本地化，[113]
- 与方块对比，[53-54]
- 与实体对比，[54]
- 创建，[54-57]
- 完成的 `ItemKey` 文件，[64-65，67]
- 项目文件，[57-58]
- `ItemSamGeneric` 示例，[69-71]
- 名称，[58-61]
- `preInit` 方法，[54-57]
- 纹理，[61-64]
- 变量，[56]
- 解释，[53-54]
- 食物项目，[84-89]
- 创建，[84-89]
- 解释，[83-84]
- `foodLevel`，[83-84]
- `foodSaturation`，[83-84]
- `ItemBerry` 类，[84-86]
- mod 文件代码，[84]
- 药水效果，[89-91]
- `ItemKey`，[54-57]
- 添加到创造模式菜单，[58]
- 完成的 `ItemKey` 文件，[64-65，67]
- 项目文件，[57-58]
- 多个项目的 `ItemKey` 文件，[68]
- 本地化，[58-61]
- 元数据。查看 `metadata`
- 多个项目，添加到同一个文件，[67-70]
- 名称，[58-61]
- `preInit` 方法，[54-57]
- 纹理，[61-64]
- 未本地化的名称，[58]
- 变量，[56]
- 元数据，添加，[72]
- 构造函数，[72-73]
- `getIconFromDamage`，[76-77]
- 注册，[75-76]
- 名称，[73-74]
- 带有元数据的 `ItemKey`，[77-78]
- 带有元数据键的 mod 文件，[79-80]
- 纹理，[75]
- 模型，[391-393]
- 多个项目，添加到同一个文件，[67-70]
- 名称本地化，[58-61]
- 元数据，[73-74]
- 未本地化的名称，[58]
- `samdust`，[70-72]
- `samingot`，[70-72]
- 工具。查看 `tools`

## `ItemSamArmor` 类

- 护甲碎片纹理，[114，116-118]
- 创建，[113-118]
- 游戏内，[114]
- 本地化，[113]
- mod 文件代码，[112-113]

## `ItemSamAxe` 类

- 代码列表，[99]
- 游戏内，[101]
- 纹理，[101]

## `ItemSamGeneric` 类，[69-71]

## `ItemSamHoe` 类

- 代码列表，[99]
- 游戏内，[101]
- 纹理，[101]

## `ItemSamPaxel` 类

- 代码列表，[99]
- 创建，[104-105]
- `func_150893_a()`，[105-106]
- `func_150897_b()`，[105-106]
- 游戏内，[107]
- `hitEntity()`，[106-107]
- 本地化，[107]
- mod 文件代码，[103]
- 纹理，[107]

# `ItemSamPickaxe` 类，[97-98，101]

# `ItemSamPlant` 类，[160]

# `ItemSamPlant` 构造函数，[160]

# `ItemSamSeed` 类，[158-165]

# `ItemSamShovel` 类

- 代码列表，[100]
- 游戏内，[101]
- 纹理，[101]

# `ItemSamStone` 类，[137-139]

# `ItemSamSword` 类

- 代码列表，[100]
- 游戏内，[101]
- 纹理，[101]

# `ItemSamThrow` 类，[287-290]

# `ItemStack` 参数

- 自定义 `ItemStacks`，[46]
- 解释，[41-42]

# `IWorldGenerator` 类，[196-197]

## J

- `.jar` 文件，重命名，[328]
- `Java`，[7，338]
- `Java Development Kit`。参见 `JDK`（Java Development Kit）
- `Java Runtime Environment（JRE）`，[7-8]

### `JDK（Java Development Kit）`

- 概述，[7-8]
- 安装，[9-15]
- Linux，[15]
- Mac，[15]
- Windows，[9-15]

- 加入 IRC 频道，[335]
- `JRE（Java Runtime Environment）`，[7-8]

## K

- `key items`。参见 `ItemKey`
- `keywords`
  - `final`，[25-26]
  - `import`，[23]
  - `public`，[24-25]
  - `static`，[25]
- `KiwiIRC`，[334]
- 创建击退的剑，[47]
- `knockbackItemStack`，[47]

## L

- `lang folder`，[58-59]
- `leggings`。参见 `armor`
- `level.dat` 文件，[227]
- `libraries, forgeSrc`，[28-29]
- 显示行号，[86-89]
- 换行选项（代码格式），[213]
- Linux，JDK（Java Development Kit）安装，[15]
- `LivingDropEvents`，[298-302]
- `loadBlocks` 方法，[320]
- `loadConfig` 方法，[342]
- `localizations`，[107]
  - 添加物品名称，[58-61]
  - 护甲，[113]
  - 方块，[128-129]
  - `ItemSamPickaxe` 类，[125]
  - `ItemSamStone` 类，[139]
  - 随机位置，[208-209]
  - 生成位置，[241]

## M

- Mac 电脑，JDK（Java Development Kit）安装，[15]
- 公开 mods，[328-329]
- 手动生成生物，[240-241]
- `material`
  - `ArmorMaterial`，[111-112]
  - `ToolMaterial`，[95-96]
- `Maya`，[263]
- `MCEdit`
  - 优势，[223]
  - 生成结构，[225-227]
  - 下载，[223-224]
  - 导出结构，[225-228-229]
  - 世界，[227]
  - 安装，[225]
- `mcmod.info` 文件，[326-327]
- `MCP（Mod Coder）`，[8]
- `metadata`
  - 添加方块，[135]
  - 基于元数据的方块，[152]
  - 方块注册，[136]
  - 创造模式，[135-136]
  - `ItemBlock` 类，[136-138]
  - `ItemSamStone` 类，[137-139]
  - 纹理，[139-143]
  - 添加物品，[72-73]
  - 构造函数，[72-73]
  - `getIconFromDamage` 方法，[76-77]
  - 注册，[75-76]
  - 物品名称，[73-74]
  - 带有元数据的 `ItemKey`，[77-78]
  - 带有元数据的 mod 文件，[79-80]
  - 纹理，[75]
- `methods`。参见特定方法（例如 `addBlockDrops` 方法）
  - 构造函数，[57]
  - 解释，[26-27]
  - 名称，[26-27]
  - 返回类型，[26]
- `Mibbit`，[334]
- `mIRC`，[334]
- 镜像纹理，[257]
- 生成生物，[241-243]
- `mobs`，[48，257-258]
  - 添加，[48，240]
  - 手动生成实体，[240-241]
  - 生成生物，[241-243]
  - AI，[276-277]
  - 改变行为，[363-364]
  - 自定义 AI，[384]
  - 夜间攻击，[384-390]
  - 受伤时逃跑，[384-390]
  - 带有 `Techne` 的实体模型
  - 添加/移除方块，[257-258]
  - 下载并安装 `Techne`，[253-254]
  - 编辑立方属性，[256-257]
  - 导出模型，[259-263]
  - 模型特性，[253-254]
  - `Techne` 模型创建界面，[255]

# `EntitySamMob` 类，[249-250]

- AI，[276-277]
- 基础值，[278]
- 掉落，[278-280]
- `EntitySamMob` 继承 `EntityMob`

# `ModelSamMob`

- 完成了 `ModelSamMob`，[266-268]
- `setRotationAngles` 方法，[268-270]

# 渲染

- 移除，[48]
- 渲染
- 客户端代理，[272]
- 模型类，[265-268]
- 移动身体部位，[268-270]
- `registerEntityRenderingHandler` 方法，[272]
- `Render` 类，[270-271]
- `RenderingRegistry` 类，[272]
- `RenderSamMob` 类，[270-271]

# 生成

- 自然产生，[274-275]
- 刷怪蛋，[273-274]

# Mod 类与文件

- Mod 类，清理，[314-322]
- `Mod Coder Pack（MCP）`，[8]
- Mod 文件
- 创建，[34-35]
- 在检查配方结果，[49-51]
- 物品。查看 `items`
- 行号，显示，[86-89]
- 元数据键，[79-80]
- `preInit` 方法，[54-57]
- 工具。查看 `tools`
- `@Mod` 行，[23-24]
- `ModBlocks` 类，[319-320]

# 模型（实体）

- 使用 `Techne` 创建，[253]
- 添加/移除立方体，[257-258]
- 下载并安装 `Techne`，[253-254]
- 编辑立方体属性，[256-257]
- 导出模型，[259-263]
- 模型特性，[253-254]
- `Techne` 模型创建界面，[255]

# 模型（物品）

- 模型（物品），[391-393]
- `ModelSamMob` 类
- 完成了 `ModelSamMob`，[266-268]
- `setRotationAngles` 方法，[268-270]
- `modid` 变量，[24]
- `modlist.mcf.li`，[329，337]
- 移动身体部位，[268-270]
- 多个物品，添加到同一文件，[67-70]
- 多个本地化，添加到物品名称中，[61]

# N

- 命名二进制标签（NBT），[189]
- 名字
- 方块名称，[126]
- 物品名称，[58-61]
- 本地化，[58-61]
- 元数据，[73-74]
- 未本地化的名称，[58]
- 方法名，[26-27]
- 贴图名称，[63]
- 命名包，[30]
- 自然生长（植物），[158-159]
- 自然生成，[274-275]
- NBT（命名二进制标签），[189]
- `NetBeans`，[8]
- 地界矿石生成，[200]
- 网络列表，[334]
- 新 Java 类，[31]
- 新 Java 包，[29]
- 新配置，[211]
- 新变量，[14]
- `newEx`，[285]
- 夜间攻击，[386-390]
- 数字（行），显示，[86-89]
- `.obj` 文件，[263]
- `onArmorTick` 方法，[119，365-367]
- `onDataPacket` 方法，[188-190]
- `onImpact` 方法，[285]
- `onItemRightClick` 方法，[289-290]
- `onItemUse` 方法，[162-163]
- 打开层级（MCE），[227]
- 复制代码，[338]
- 查找，[336-337]
- 如何使用，[337-338]
- 理解代码，[337]
- Oracle NetBeans，[8]
- `OreDictionary` 类，[202-204]
- 配方，[203-204]
- `registerOre` 方法，[202-203]

# 矿石生成

- `EventHandler` 类，[195]
- 地界矿石生成，[200]
- `OreDictionary` 类，[202-204]
- 游戏中的结果，[204]
- `SamEventHandler` 类，[195-202]
- `addOreSpawn` 方法，[198-200]
- 完成了 `SamEventHandler` 类，[200-202]
- 生成方法，[197-198]
- 初始 `SamEventHandler` 类，[196]
- `IWorldGenerator` 类，[196-197]

# 重写

- `@Override` 注解，[138]
- 包，[21]
- 清理，[312-313]
- 创建，[27-30]
- 重命名，[22-23]
- 粒子，生成，[390-391]
- `PATH` 变量，[14]
- `ItemSamPaxel` 类
- 代码列表，[104-105]
- 创建，[104-105]
- `func150893_a` 方法，[105-106]
- `func150897_b` 方法，[105-106]
- 游戏中的，[107]
- `hitEntity` 方法，[106-107]
- 本地化，[107]
- 贴图，[107]
- Mod 文件代码，[103]
- 镐头，[96]
- 游戏中的，[101]
- `ItemSamPickaxe` 类，[97-98]
- Mod 文件代码，[96]

- 作物，[155-157]
- 自定义，[165-171]
- 游戏内，[170-171]
- 自然生长，[158-159]
- 随机植物，[157-158]
- 游戏中的结果，[219]
- `SamEventHandler` 类，[215-219]
- 种子，[159-165]
- `WorldGen` 类，[207-215]
- 检查与放置，[209]
- 完成的 `WorldGenSamPlant`，[210]
- 初始 `WorldGenSamPlant` 类，[207]
- 随机起始元数据，[210]
- 随机化位置，[208-209]
- `WorldGenSamPlant` 继承 `WorldGenerator`，[208]

## `PlayerInteractEvent`，[303-307]

### 播放声音

- `playSound` 方法，[391]
- 步法声，[391]
- `playSound` 方法，[391]

## `PostInit` 事件，[26]

## `potion` 效果，[89-91]

## `Preferences` 窗口，[211]

## `PreInit` 事件，[26]

## `preInit` 方法，[54-57]

- 护甲代码，[113]
- 工具代码，[98-99]

## 代理

- 更改，[313]
- `ClientProxySam` 类，[248，272]
- `CommonProxySam` 类，[247]
- 创建，[246-247]
- 解释，[246]

## 公有类，[24-25]

## 公有字段，[25]

## 公有关键字，[24-25]

### Q-R

- 创建随机植物，[157-158]
- `randomDisplayTick` 方法，[390-391]
- 随机化掉落，[299]
- 随机化位置，[208-209]
- `readFromNBT` 方法，[188-190]

## 配方

- 箱子物品，[49]
- 添加，[49]
- 移除，[49]
- 合成配方，[40-41]
- 解释，[39]
- `GameRegistry`，[41-42]
- 配方的形状，[42-44]
- 自定义 `ItemStacks`，[46]
- 在 mod 文件中检查，[49-51]
- 解释，[39-40]
- `ItemStacks`，[41-42]
- 地城中的生物刷生成，[48]
- 添加生物，[48]
- 更改行为，[363-364]
- 自定义 AI，[384-390]
- 移除生物，[48]
- `OreDictionary` 类，[203-204]
- 创建无形状配方，[44]
- 解释，[39]
- 创建熔炼配方，[45]
- 解释，[40]

## `redKey` 物品，[69]

- `registerBlock` 方法，[124，136]
- `registerBlockHandler` 方法，[350]
- `registerBlockIcons` 方法，[177]
- `registerDimension` 方法，[367]
- `registerEntityEgg` 方法，[273]
- `registerEntityRenderingHandler` 方法，[272，363]
- `registerIcons` 方法，[75-76，146]

## 注册

- 方块，[124，136]
- 事件，[303]
- 图像，[75-76]
- 矿石，[202-203]
- `Render` 类，[393]
- 可投掷实体，[283]
- `registerItem` 方法，[56-57]
- `registerItemRenderer` 方法，[393]
- `registerItemRenders` 方法，[290]
- `registerModEntity` 方法，[248，249，283，363]
- `registerOre` 方法，[202-203]
- `registerRendering` 方法，[247-248]
- `registerTileEntity` 方法，[180]
- 使用 Forge 发布 mod，[325-327]
- 将 mod 上传到网站，[328-329]
- `removeDungeonMob` 方法，[48]
- `removeItem` 方法，[49]
- `removeSpawn` 方法，[297-298]

## 移除

- 箱子物品，[49]
- 立方，[257-258]
- 实体，[297-298]
- 生物，[48]

## 重命名

- `.jar` 文件，[328]
- 包，[22]
- `Render` 类，[270-271]
- `RenderCustomWoodExample` 类，[346-350]
- `RenderExampleItem` 类，[391-393]
- `RenderExampleTNTPrimed` 类，[361-363]

## 渲染

- 方块
- `BlockCustomRenderWoodExample` 类，[343-346]
- `RenderCustomWoodExample` 类，[346-350]
- 自定义 `Render` 类，[391-393]
- `getRenderType` 方法，[155]

## 生物

- 客户端代理，[272]
- 模型类，[265-268]
- 移动身体部位，[268-270]
- `registerEntityRenderingHandler` 方法，[272]
- `Render` 类，[270-271]
- `RenderingRegistry` 类，[272]
- 可投掷实体，[290-291]
- TNT，[361-363]

## `RenderingRegistry` 类，[272]

## `RenderLiving` 类，继承，[271]

## `RenderSamMob` 类，[270-271]

## 仓库（GitHub），[328-329]

## 返回类型，[26]

## 在 `BlockSamTE` 中右键点击，[185-188]

## 旋转

区块，[342-343]

实体模型，[257]

### S

### `SamDungeon` 类，[235]

### `samdust` 物品，[70-72]

### `SamEventHandler` 类，[195-202]

`addOreSpawn` 方法，[198-200]

完成的 `SamEventHandler` 类，[200-202，237-239]

生成方法，[197-198]

初始化的 `SamEventHandler` 类，[196]

`IWorldGenerator` 类，[196-197]

带有 `WorldGenSamPlant` 代码，[215-219]

### `samingot` 物品，[70-72]

### `samium ToolMaterial`，[95-96]

### Sam 的 24 小时自学 Java（Cadenhead），[338]

### `Sam’s Wall` 纹理，[142-143]

### `SamsMod` 类

清理，[320-322]

代码列表，[314-319]

创建，[31-33]

`ModBlocks`，[319-320]

### 图纸转换器（Schematic Converter）

下载，[231]

使用生成结构，[231-239]

导出后的生成文件，[234-237]

`SamEventHandler` 类，[237-239]

安装，[231-232]

### 种子，创建，[159-165]

### 选择工作目录窗口，[18]

### 选择工具（MCEdit），[228]

### 通过服务器同步发送数据，[188-192]

### 服务器同步，区块实体，[183-185]

在 `BlockSamTE` 中右键点击，[185-188]

发送数据，[188-192]

`setAlwaysEdible` 方法，[90]

`setBlock` 方法，[242]

`setBlockBoundsOnState` 方法，[152]

`setBlockBounds` 方法，[148]

`setBlockMetadataWithNotify` 方法，[182]

`setBlockName` 方法，[126]

`setBlockTexture` 方法，[131，139-140]

`setCreativeTab` 方法，[58]

`setHardness` 方法，[126]

`setLevel` 方法，[127-128]

`setHasSubTypes` 方法，[73，137]

`setPosition` 方法，[241]

`setPotion` 方法，[89-90]

`setResistance` 方法，[126]

`setRotationAngles` 方法，[268-270]

`setStepSound` 方法，[126-127]

`textureName` 方法，[63]

### 设置

Eclipse，[16]

Forge，[16-19]

GitHub 仓库，[328-329]

IRC（Internet Relay），[334-335]

JDK（Java Development Kit），[9-15]

Linux，[15]

Mac，[15]

Windows，[9-15]

`setUnlocalizedName` 方法，[58，73]

### 配方的形状

替代形状，[42-44]

解释，[42]

`ShapedOreRecipe` 类，[203]

无形配方，[39]

形状，创建，[148-151]

### 铲子

代码列表，[100]

在游戏内，[101]

纹理，[101]

### 显示行号选择框，[88]

侧面纹理，添加到区块中，[145-147]

`@Sided` 注解，[246，313]

`@SideOnly` 注解，[139-140]

### 合金，[45]

解释，[40]

`playSound` 方法，[391]

step sounds，[126-127]

`stoneType`，[126-127]

`source`，[22]

### 静态字段，[25]

`static` keyword，[25]

stone slabs，[123]

String，声明，[24]

### 结构

将实体添加到结构，[240]

手动生成实体，[241-241]

mob 生物生成器，创建，[241-243]

在 MCEdit 中创建，[225-227]

从 MCEdit 导出，[228-229]

生成，[231-239]

### 结构化 Mod

清理 Mod 类，[314-322]

清理包，[312-313]

重要性，[311]

`@SubscribeEvent`，[298]

### 剑

附魔剑，[41-42]

`ItemSamSword`

代码列表，[100]

在游戏内，[101]

纹理，[101]

# 同步（服务器），[183-192]

# `syso`，[27]

# 系统属性窗口，[11]

# `System.out.println`（`syso`），[27]

## T

### 选项卡，`CreativeTabs`，[356]

## Techne

- 使用创建实体模型，[253]
- 添加/移除立方体，[257-258]
- 编辑立方体属性，[256-257]
- 导出模型，[259-263]
- 模型特性，[253-254]
- Techne 模型创建界面，[255]
- 下载，[253-254]
- 安装，[253-254]

## 纹理

- 添加到方块，[129-131]
- `Sam’s Wall` 纹理，[139-143]
- 多面纹理，[145-147]
- 添加到实体模型，[256-257]
- 添加到物品，[61-64]

## 护甲

- 护甲部件纹理，[114]
- 游戏内，[114]
- 穿在身上的护甲纹理，[116-118]
- `ItemBerry` 类，[85-86]
- `ItemSamAxe`，[101]
- `ItemSamPaxel` 类，[107]
- `ItemSamPickaxe` 类，[97]
- `ItemSamSeed` 类，[161]
- 元数据（metadata），[75]
- 镜面纹理，[257]
- 僵尸纹理，[257-258]

## 可投掷实体，[283-293]

- `EntitySamThrowable` 类，[284-287]
- 游戏内，[291-293]
- `ItemSamThrow` 类，[287-290]
- 注册，[283]
- 渲染，[290-291]

## `throwEggs` 方法，[303-307]

## tile 实体

- 添加到方块，[176-180]
- 与方块对比，[123-124]
- 创建，[180-183]
- 解释，[175-176]
- 服务器同步，[183-185]
- 右点击 `BlockSamTE`，[185-188]
- 发送数据，[188-192]
- `TileEntitySam` 类，[180-183，190-192]
- `TileEntityMob` 类，[241-243]
- `TileEntitySam` 类，[180-183，190-192]

## TNT

- 自定义 TNT 方块，[357-359]
- `RenderPrimed` 类，[361-363]
- TNT 实体，[359-361]

## `ToolMaterial`，创建，[95-96]

## 工具

- 自定义工具（paxel 示例），[103]
- `ItemSamPaxel` 类，[104-107]
- mod 文件代码，[103]
- 解释，[95]
- 游戏内，[101]
- `ItemSamAxe` 代码列表，[99]，游戏内，[101]，纹理，[101]
- `ItemSamHoe` 代码列表，[99]，游戏内，[101]，纹理，[101]
- `ItemSamShovel` 代码列表，[100]，游戏内，[101]，纹理，[101]
- `ItemSamSword` 代码列表，[100]，游戏内，[101]，纹理，[101]

## MCEdit

- 添加，[223]
- 优势，[223]
- 创建结构，[225-227]
- 下载，[223-224]
- 导出结构，[228-229]
- 导入世界，[227]
- 安装，[225]
- 在线资源，[225-226]
- 带有 `preInit` 代码的 mod 文件，[98-99]
- 带有外部 `preInit` 代码的 mod 文件，[98]
- 铁镐，[96]
- 游戏内，[101]
- `ItemSamPickaxe` 类，[97-98]
- mod 文件代码，[96]
- 纹理，[101]
- `ToolMaterial`，[95-96]
- 树木生成，[350-352]

## U-V

- 不破坏方块，[127]
- 本地化物品名称，[58]
- `UpdateChecker` 类，[353-356]
- `updateEntity` 方法，[180-184，245-246]
- 更新检查，[353-356]
- `updateTick` 方法，[158-159]
- 上传 mod 到网站，[328-329]

## 变量

- 创建，[56]
- `modid`，[24]
- `PATH`，[14]

## W-X-Y-Z

### 网站

- `eclipse.org`，[16]
- `modlist.mcf.li`，[329]
- `planetminecraft.com`，[329]
- 上传到，[328-329]

## `WeightedRandomChestContent` 参数（`addItem` 方法），[49]

## 窗口

- 计算机属性，[10]
- 环境变量，[13]
- `Formatter`，[211-212]
- HexChat：编辑 EsperNet，[334]
- 网络列表，[334]
- 新 Java 类，[31]
- 新 Java 包，[29]
- 新配置，[211]
- 新用户变量，[14]
- 偏好，[211]
- 选择工作区目录，[10]

- 下载，[223-224]
- 导出结构，[228-229]
- 导入世界，[227]
- 安装，[225]
- 在线资源，[225-226]

## 矿石

- `EventHandler` 类，[195]
- 下界矿石生成，[200]
- `OreDictionary` 类，[202-204]
- 游戏内结果，[204]
- `SamEventHandler` 类，[195-202]

## 植物

- 植物，[207]
- 游戏内结果，[219]
- `SamEventHandler` 类，[215-219]
- `WorldGen` 类，[207-215]

结构。参见结构

### `WorldGen` 类

- `WorldGen` 类，[207-215]
- 检查与放置，[209]
- 完成的 `WorldGenSamPlant`，[210]
- 初始 `WorldGenSamPlant` 类，[207]
- 随机起始元数据，[210]
- 随机化位置，[208-209]
- `WorldGenSamPlant` 继承 `WorldGenerator`，[208]

### 特定类

- `WorldGenCustomTreeExample` 类，[350-352]
- `WorldGenSamDungeon` 类，[236]
- `WorldGenSamPlant` 类
  - 检查与放置，[209]
  - 完成的 `WorldGenSamPlant`，[210]
  - 初始 `WorldGenSamPlant` 类，[207]
  - 随机起始元数据，[210]
  - 随机化位置，[208-209]
  - `WorldGenSamPlant` 继承 `WorldGenerator`，[208]
- `WorldProviderExample` 类，[367-369]
- 穿过的护甲纹理，[116-118]
- `writeToNBT` 方法，[188-190]
- 僵尸纹理，[257-258]

![Image](img/image00653.jpeg)
![Image](img/image00654.jpeg)
![Image](img/image00655.jpeg)
![Image](img/image00656.jpeg)#part0012.xhtml_p015pro01)
![Image](img/image00657.jpeg)#part0012.xhtml_p015pro02)
![Image](img/image00658.jpeg)#part0012.xhtml_p01lis01)
![Image](img/image00659.jpeg)#part0013.xhtml_p02lis01)
![Image](img/image00660.jpeg)#part0013.xhtml_p022pro01)
![Image](img/image00661.jpeg)#part0013.xhtml_p023pro01)
![Image](img/image00662.jpeg)#part0013.xhtml_p023pro02)
![Image](img/image00663.jpeg)#part0013.xhtml_p025pro01)
![Image](img/image00664.jpeg)#part0013.xhtml_p026pro01)
![Image](img/image00665.jpeg)#part0013.xhtml_p02lis02)
![Image](img/image00666.jpeg)#part0013.xhtml_p036pro01)
![Image](img/image00667.jpeg)#part0013.xhtml_p037pro01)
![Image](img/image00668.jpeg)#part0014.xhtml_p03lis01)
![Image](img/image00669.jpeg)#part0014.xhtml_p041pro01)
![Image](img/image00670.jpeg)#part0014.xhtml_p043pro01)
![Image](img/image00671.jpeg)#part0014.xhtml_p044pro01)
![Image](img/image00672.jpeg)#part0014.xhtml_p044pro02)
![Image](img/image00673.jpeg)#part0014.xhtml_p045pro01)
![Image](img/image00674.jpeg)#part0014.xhtml_p046pro01)
![Image](img/image00675.jpeg)#part0014.xhtml_p047pro01)
![Image](img/image00676.jpeg)#part0014.xhtml_p048pro01)
![Image](img/image00677.jpeg)#part0014.xhtml_p048pro02)
![Image](img/image00678.jpeg)#part0014.xhtml_p049pro01)
![Image](img/image00679.jpeg)#part0014.xhtml_p049pro02)
![Image](img/image00680.jpeg)#part0014.xhtml_p049pro03)
![Image](img/image00681.jpeg)#part0014.xhtml_p049pro03)
![Image](img/image00682.jpeg)#part0014.xhtml_p049pro03)
![Image](img/image00683.jpeg)#part0014.xhtml_p049pro03)
![Image](img/image00684.jpeg)#part0014.xhtml_p052pro01)
![Image](img/image00685.jpeg)#part0016.xhtml_p04lis01)
![Image](img/image00686.jpeg)#part0016.xhtml_p04lis01)
![Image](img/image00687.jpeg)#part0016.xhtml_p04lis01)
![Image](img/image00688.jpeg)#part0016.xhtml_p04lis01)
![Image](img/image00689.jpeg)#part0016.xhtml_p056pro01)
![Image](img/image00690.jpeg)#part0016.xhtml_p057pro01)
![Image](img/image00691.jpeg)#part0016.xhtml_p04lis02)
![Image](img/image00692.jpeg)#part0016.xhtml_p058pro01)
![Image](img/image00693.jpeg)#part0016.xhtml_p058pro02)
![Image](img/image00694.jpeg)#part0016.xhtml_p061pro01)
![Image](img/image00695.jpeg)#part0016.xhtml_p063pro01)
![Image](img/image00696.jpeg)#part0016.xhtml_p063pro02)
![Image](img/image00697.jpeg)#part0016.xhtml_p04lis03)
![Image](img/image00698.jpeg)#part0016.xhtml_p066pro01)
![Image](img/image00699.jpeg)#part0016.xhtml_p066pro02)
![Image](img/image00700.jpeg)#part0017.xhtml_p05lis01)
![Image](img/image00701.jpeg)#part0017.xhtml_p05lis02)
![Image](img/image00702.jpeg)#part0017.xhtml_p068pro01)
![Image](img/image00703.jpeg)#part0017.xhtml_p069pro01)
![Image](img/image00704.jpeg)#part0017.xhtml_p069pro02)
![Image](img/image00705.jpeg)#part0017.xhtml_p070pro01)
![Image](img/image00706.jpeg)#part0017.xhtml_p070pro02)
![Image](img/image00707.jpeg)#part0017.xhtml_p05lis03)
![Image](img/image00708.jpeg)#part0017.xhtml_p073pro01)
![Image](img/image00709.jpeg)#part0017.xhtml_p073pro02)
![Image](img/image00710.jpeg)#part0017.xhtml_p074pro01)
![Image](img/image00711.jpeg)#part0017.xhtml_p074pro02)
![Image](img/image00712.jpeg)#part0017.xhtml_p075pro01)
![Image](img/image00713.jpeg)#part0017.xhtml_p076pro01)
![Image](img/image00714.jpeg)#part0017.xhtml_p076pro02)
![Image](img/image00715.jpeg)#part0017.xhtml_p05lis04)
![Image](img/image00716.jpeg)#part0017.xhtml_p05lis04)
![Image](img/image00717.jpeg)#part0017.xhtml_p05lis05)
![Image](img/image00718.jpeg)#part0017.xhtml_p05lis05)
![Image](img/image00719.jpeg)#part0017.xhtml_p05lis05)
![Image](img/image00720.jpeg)#part0017.xhtml_p08lis01)
![Image](img/image00721.jpeg)#part0018.xhtml_p08lis01)
![Image](img/image00722.jpeg)#part0018.xhtml_p08lis02)
![Image](img/image00723.jpeg)#part0018.xhtml_p08lis02)
![Image](img/image00724.jpeg)#part0018.xhtml_p08lis02)
![Image](img/image00725.jpeg)#part0018.xhtml_p08lis03)
![Image](img/image00726.jpeg)#part0018.xhtml_p08lis03)
![Image](img/image00727.jpeg)#part0018.xhtml_p08lis03)
![Image](img/image00728.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00729.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00730.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00731.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00732.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00733.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00734.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00735.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00736.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00737.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00738.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00739.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00740.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00741.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00742.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00743.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00744.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00745.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00746.jpeg)#part0018.xhtml_p12lis03)
![Image](img/image00747.jpeg)#part0019.xhtml_p12lis04)
![Image](img/image00748.jpeg)#part0019.xhtml_p12lis04)
![Image](img/image00749.jpeg)#part0019.xhtml_p12lis04)
![Image](img/image00750.jpeg)#part0019.xhtml_p12lis04)
![Image](img/image00751.jpeg)#part0019.xhtml_p12lis03)
![Image](img/image00752.jpeg)#part0019.xhtml_p12lis03)
![Image](img/image00753.jpeg)#part0020.xhtml_p11pro01)
![Image](img/image00754.jpeg)#part0020.xhtml_p08lis01)
![Image](img/image00755.jpeg)#part0020.xhtml_p08lis02)
![Image](img/image00756.jpeg)#part0020.xhtml_p13pro01)
![Image](img/image00757.jpeg)#part0020.xhtml_p13pro02)
![Image](img/image00758.jpeg)#part0020.xhtml_p18pro01)
![Image](img/image00759.jpeg)#part0020.xhtml_p19pro01)
![Image](img/image00760.jpeg)#part0020.xhtml_p11pro01)
![Image](img/image00761.jpeg)#part0022.xhtml_p24pro01)
![Image](img/image00762.jpeg)#part0022.xhtml_p09lis01)
![Image](img/image00763.jpeg)#part0022.xhtml_p25pro01)
![Image](img/image00764.jpeg)#part0022.xhtml_p09lis02)
![Image](img/image00765.jpeg)#part0022.xhtml_p27pro01)
![Image](img/image00766.jpeg)#part0022.xhtml_p09lis03)
![Image](img/image00767.jpeg)#part0022.xhtml_p28pro01)
![Image](img/image00768.jpeg)#part0022.xhtml_p33pro01)
![Image](img/image00769.jpeg)#part0022.xhtml_p34pro01)
![Image](img/image00770.jpeg)#part0022.xhtml_p13lis04)
![Image](img/image00771.jpeg)#part0023.xhtml_p16lis01)
![Image](img/image00772.jpeg)#part0023.xhtml_p36pro02)
![Image](img/image00773.jpeg)#part0023.xhtml_p10lis02)
![Image](img/image00774.jpeg)#part0023.xhtml_p37pro01)
![Image](img/image00775.jpeg)#part0023.xhtml_p37pro02)
![Image](img/image00776.jpeg)#part0023.xhtml_p10lis03)
![Image](img/image00777.jpeg)#part0023.xhtml_p10lis03)
![Image](img/image00778.jpeg)#part0023.xhtml_p39pro01)
![Image](img/image00779.jpeg)#part0023.xhtml_p40pro02)
![Image](img/image00780.jpeg)#part0023.xhtml_p14pro03)
![Image](img/image00781.jpeg)#part0023.xhtml_p10lis04)
![Image](img/image00782.jpeg)#part0023.xhtml_p10lis04)
![Image](img/image00783.jpeg)#part0024.xhtml_p11lis01)
![Image](img/image00784.jpeg)#part0024.xhtml_p11lis02)
![Image](img/image00785.jpeg)#part0024.xhtml_p148pro01)
![Image](img/image00786.jpeg)#part0024.xhtml_p149pro01)
![Image](img/image00787.jpeg)#part0024.xhtml_p11lis03)
![Image](img/image00788.jpeg)#part0024.xhtml_p11lis03)
![Image](img/image00789.jpeg)#part0024.xhtml_p11lis03)
![Image](img/image00790.jpeg)#part0024.xhtml_p15pro01)
![Image](img/image00791.jpeg)#part0024.xhtml_p15pro02)
![Image](img/image00792.jpeg)#part0024.xhtml_p11lis04)
![Image](img/image00793.jpeg)#part0024.xhtml_p15pro01)
![Image](img/image00794.jpeg)#part0024.xhtml_p11lis05)
![Image](img/image00795.jpeg)#part0024.xhtml_p15pro01)
![Image](img/image00796.jpeg)#part0024.xhtml_p15pro02)
![Image](img/image00797.jpeg)#part0024.xhtml_p16pro01)
![Image](img/image00798.jpeg)#part0024.xhtml_p16pro02)
![Image](img/image00799.jpeg)#part0024.xhtml_p16pro03)
![Image](img/image00800.jpeg)#part0024.xhtml_p15pro01)
![Image](img/image00801.jpeg)#part0024.xhtml_p15pro02)
![Image](img/image00802.jpeg)#part0024.xhtml_p18pro01)
![Image](img/image00803.jpeg)#part0024.xhtml_p18pro02)
![Image](img/image00804.jpeg)#part0024.xhtml_p11lis06)
![Image](img/image00805.jpeg)#part0024.xhtml_p16pro01)
![Image](img/image00806.jpeg)#part0032.xhtml_p24pro01)
![Image](img/image00807.jpeg)#part0032.xhtml_p17lis01)
![Image](img/image00808.jpeg)#part0032.xhtml_p17lis02)
![Image](img/image00809.jpeg)#part0032.xhtml_p17lis03)
![Image](img/image00810.jpeg)#part0032.xhtml_p17lis04)
![Image](img/image00811.jpeg)#part0032.xhtml_p24pro01)
![Image](img/image00812.jpeg)#part0032.xhtml_p29pro01)
![Image](img/image00813.jpeg)#part0032.xhtml_p17lis05)
![Image](img/image00814.jpeg)#part0032.xhtml_p17lis06)
![Image](img/image00815.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00816.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00817.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00818.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00819.jpeg)#part0033.xhtml_p19lis01)
![Image](img/image00820.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00821.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00822.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00823.jpeg)#part0034.xhtml_p19lis02)
![Image](img/image00824.jpeg)#part0034.xhtml_p19lis02)
![Image](img/image00825.jpeg)#part0034.xhtml_p19lis03)
![Image](img/image00826.jpeg)#part0034.xhtml_p19lis04)
![Image](img/image00827.jpeg)#part0034.xhtml_p27pro01)
![Image](img/image00828.jpeg)#part0034.xhtml_p27201)
![Image](img/image00829.jpeg)#part0034.xhtml_p19lis05)
![Image](img/image00830.jpeg)#part0034.xhtml_p27301)
![Image](img/image00831.jpeg)#part0034.xhtml_p27302)
![Image](img/image00832.jpeg)#part0034.xhtml_p27401)
![Image](img/image00833.jpeg)#part0034.xhtml_p27501)
![Image](img/image00834.jpeg)#part0034.xhtml_p19lis06)
![Image](img/image00835.jpeg)#part0034.xhtml_p19lis07)
![Image](img/image00836.jpeg)#part0034.xhtml_p27701)
![Image](img/image00837.jpeg)#part0034.xhtml_p27801)
![Image](img/image00838.jpeg)#part0034.xhtml_p27802)
![Image](img/image00839.jpeg)#part0034.xhtml_p27803)
![Image](img/image00840.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00841.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00842.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00843.jpeg)#part0034.xhtml_p28201)
![Image](img/image00844.jpeg)#part0035.xhtml_p28301)
![Image](img/image00845.jpeg)#part0035.xhtml_p20lis01)
![Image](img/image00846.jpeg)#part0035.xhtml_p20lis02)
![Image](img/image00847.jpeg)#part0035.xhtml_p28501)
![Image](img/image00848.jpeg)#part0035.xhtml_p28502)
![Image](img/image00849.jpeg)#part0035.xhtml_p28601)
![Image](img/image00850.jpeg)#part0035.xhtml_p28602)
![Image](img/image00851.jpeg)#part0035.xhtml_p20lis03)
![Image](img/image00852.jpeg)#part0035.xhtml_p20lis03)
![Image](img/image00853.jpeg)#part0035.xhtml_p28701)
![Image](img/image00854.jpeg)#part0035.xhtml_p28702)
![Image](img/image00855.jpeg)#part0035.xhtml_p20lis04)
![Image](img/image00856.jpeg)#part0035.xhtml_p20lis05)
![Image](img/image00857.jpeg)#part0035.xhtml_p28801)
![Image](img/image00858.jpeg)#part0035.xhtml_p28901)
![Image](img/image00859.jpeg)#part0035.xhtml_p28902)
![Image](img/image00860.jpeg)#part0035.xhtml_p20lis06)
![Image](img/image00861.jpeg)#part0035.xhtml_p20lis07)
![Image](img/image00862.jpeg)#part0035.xhtml_p29401)
![Image](img/image00863.jpeg)#part0037.xhtml_p29701)
![Image](img/image00864.jpeg)#part0037.xhtml_p29801)
![Image](img/image00865.jpeg)#part0037.xhtml_p29802)
![Image](img/image00866.jpeg)#part0037.xhtml_p29803)
![Image](img/image00867.jpeg)#part0037.xhtml_p29901)
![Image](img/image00868.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00869.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00870.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00871.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00872.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00873.jpeg)#part0037.xhtml_p30201)
![Image](img/image00874.jpeg)#part0037.xhtml_p30301)
![Image](img/image00875.jpeg)#part0037.xhtml_p30302)
![Image](img/image00876.jpeg)#part0037.xhtml_p30401)
![Image](img/image00877.jpeg)#part0037.xhtml_p30402)
![Image](img/image00878.jpeg)#part0037.xhtml_p30403)
![Image](img/image00879.jpeg)#part0037.xhtml_p30502)
![Image](img/image00880.jpeg)#part0037.xhtml_p30503)
![Image](img/image00881.jpeg)#part0037.xhtml_p30601)
![Image](img/image00882.jpeg)#part0037.xhtml_p30602)
![Image](img/image00883.jpeg)#part0037.xhtml_p21lis02)
![Image](img/image00884.jpeg)#part0037.xhtml_p21lis02)
![Image](img/image00885.jpeg)#part0037.xhtml_p30901)
![Image](img/image00886.jpeg)#part0038.xhtml_p31301)
![Image](img/image00887.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00888.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00889.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00890.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00891.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00892.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00893.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00894.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00895.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00896.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00897.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00898.jpeg)#part0038.xhtml_p32002)
![Image](img/image00899.jpeg.part0038.xhtml_p32003)
![Image](img/image01000.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01001.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01002.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01003.jpeg)#part0039.xhtml_p23lis01)
![Image](img/image01004.jpeg)#part0039.xhtml_p23lis02)
![Image](img/image01005.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01006.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01007.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01008.jpeg)#part0041.xhtml_p02lis01)
![Image](img/image01009.jpeg)#part0041.xhtml_p02lis02)
![Image](img/image01010.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01011.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01012.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01013.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01014.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01015.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01016.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01017.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01018.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01019.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01020.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01021.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01022.jpeg)#part0041.xhtml_p35001)
![Image](img/image01023.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01024.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01025.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01026.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01027.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01028.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01029.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01030.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01031.jpeg)#part0041.xhtml_p35501)
![Image](img/image01032.jpeg)#part0041.xhtml_p35601)
![Image](img/image01033.jpeg)#part0041.xhtml_p07lis07)
![Image](img/image01034.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01035.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01036.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01037.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01038.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01039.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01040.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01041.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01042.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01043.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01044.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01045.jpeg)#part0041.xhtml_p36301)
![Image](img/image01046.jpeg)#part0041.xhtml_p36302)
![Image](img/image01047.jpeg)#part0041.xhtml_p36303)
![Image](img/image01048.jpeg)#part0041.xhtml_p11lis11)
![Image](img/image01049.jpeg)#part0041.xhtml_p12lis12)
![Image](img/image01050.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01051.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01052.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01053.jpeg)#part0042.xhtml_p14lis14)
![Image](img/image01054.jpeg)#part0042.xhtml_p14lis14)
![Image](img/image01055.jpeg)#part0042.xhtml_p15lis15)
![Image](img/image01056.jpeg)#part0042.xhtml_p15lis15)
![Image](img/image00857.jpeg)#part0025.xhtml_p19401)
![Image](img/image00858.jpeg)#part0027.xhtml_p19501)
![Image](img/image00859.jpeg)#part0027.xhtml_p19601)
![Image](img/image00860.jpeg)#part0027.xhtml_p13lis01)
![Image](img/image00861.jpeg)#part0027.xhtml_p13lis02)
![Image](img/image00862.jpeg)#part0027.xhtml_p13lis03)
![Image](img/image00863.jpeg)#part0027.xhtml_p13lis03)
![Image](img/image00864.jpeg)#part0027.xhtml_p19801)
![Image](img/image00865.jpeg)#part0027.xhtml_p19801)
![Image](img/image00866.jpeg)#part0027.xhtml_p19901)
![Image](img/image00867.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00868.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00869.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00870.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00871.jpeg)#part0027.xhtml_p20201)
![Image](img/image00872.jpeg)#part0027.xhtml_p20301)
![Image](img/image00873.jpeg)#part0027.xhtml_p20302)
![Image](img/image00874.jpeg)#part0027.xhtml_p20501)
![Image](img/image00875.jpeg)#part0027.xhtml_p20502)
![Image](img/image00876.jpeg)#part0028.xhtml_p14lis01)
![Image](img/image00877.jpeg)#part0028.xhtml_p14lis02)
![Image](img/image00878.jpeg)#part0028.xhtml_p20801)
![Image](img/image00879.jpeg)#part0028.xhtml_p20901)
![Image](img/image00880.jpeg)#part0028.xhtml_p20902)
![Image](img/image00881.jpeg)#part0028.xhtml_p21001)
![Image](img/image00882.jpeg)#part0028.xhtml_p14lis03)
![Image](img/image00883.jpeg)#part0028.xhtml_p21501)
![Image](img/image00884.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00885.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00886.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00887.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00888.jpeg)#part0028.xhtml_p22101)
![Image](img/image00889.jpeg)#part0030.xhtml_p23101)
![Image](img/image00890.jpeg)#part0030.xhtml_p16lis01)
![Image](img/image00891.jpeg)#part0030.xhtml_p16lis02)
![Image](img/image00892.jpeg)#part0030.xhtml_p23701)
![Image](img/image00893.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00894.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00895.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00896.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00897.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00898.jpeg)#part0030.xhtml_p24001)
![Image](img/image00899.jpeg)#part0030.xhtml_p24101)
![Image](img/image00900.jpeg)#part0030.xhtml_p24102)
![Image](img/image00901.jpeg)#part0030.xhtml_p16lis04)
![Image](img/image00902.jpeg)#part0030.xhtml_p24201)
![Image](img/image00903.jpeg)#part0030.xhtml_p24202)
![Image](img/image00904.jpeg)#part0030.xhtml_p24203)
![Image](img/image00905.jpeg)#part0030.xhtml_p16lis05)
![Image](img/image00906.jpeg)#part0032.xhtml_p24601)
![Image](img/image00907.jpeg)#part0032.xhtml_p17lis01)
![Image](img/image00908.jpeg)#part0032.xhtml_p17lis02)
![Image](img/image00909.jpeg)#part0032.xhtml_p17lis03)
![Image](img/image00910.jpeg)#part0032.xhtml_p17lis04)
![Image](img/image00911.jpeg)#part0032.xhtml_p24801)
![Image](img/image00912.jpeg)#part0032.xhtml_p24901)
![Image](img/image00913.jpeg)#part0032.xhtml_p17lis05)
![Image](img/image00914.jpeg)#part0032.xhtml_p17lis06)
![Image](img/image00915.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00916.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00917.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00918.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00919.jpeg)#part0033.xhtml_p19lis01)
![Image](img/image00920.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00921.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00922.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00923.jpeg)#part0034.xhtml_p19lis02)
![Image](img/image00924.jpeg)#part0034.xhtml_p19lis02)
![Image](img/image00925.jpeg)#part0034.xhtml_p19lis03)
![Image](img/image00926.jpeg)#part0034.xhtml_p19lis04)
![Image](img/image00927.jpeg)#part0034.xhtml_p27101)
![Image](img/image00928.jpeg)#part0034.xhtml_p27201)
![Image](img/image00929.jpeg)#part0034.xhtml_p19lis05)
![Image](img/image00930.jpeg)#part0034.xhtml_p27301)
![Image](img/image00931.jpeg)#part0034.xhtml_p27302)
![Image](img/image00932.jpeg)#part0034.xhtml_p27401)
![Image](img/image00933.jpeg)#part0034.xhtml_p27501)
![Image](img/image00934.jpeg)#part0034.xhtml_p19lis06)
![Image](img/image00935.jpeg)#part0034.xhtml_p19lis07)
![Image](img/image00936.jpeg)#part0034.xhtml_p27701)
![Image](img/image00937.jpeg)#part0034.xhtml_p27801)
![Image](img/image00938.jpeg)#part0034.xhtml_p27802)
![Image](img/image00939.jpeg)#part0034.xhtml_p27803)
![Image](img/image00940.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00941.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00942.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00943.jpeg)#part0034.xhtml_p28201)
![Image](img/image00944.jpeg)#part0035.xhtml_p28301)
![Image](img/image00945.jpeg)#part0035.xhtml_p20lis01)
![Image](img/image00946.jpeg)#part0035.xhtml_p20lis02)
![Image](img/image00947.jpeg)#part0035.xhtml_p28501)
![Image](img/image00948.jpeg)#part0035.xhtml_p28502)
![Image](img/image00949.jpeg)#part0035.xhtml_p28601)
![Image](img/image00950.jpeg)#part0035.xhtml_p28602)
![Image](img/image00951.jpeg)#part0035.xhtml_p20lis03)
![Image](img/image00952.jpeg)#part0035.xhtml_p20lis03)
![Image](img/image00953.jpeg)#part0035.xhtml_p28701)
![Image](img/image00954.jpeg)#part0035.xhtml_p28702)
![Image](img/image00955.jpeg)#part0035.xhtml_p20lis04)
![Image](img/image00956.jpeg)#part0035.xhtml_p20lis05)
![Image](img/image00957.jpeg)#part0035.xhtml_p28801)
![Image](img/image00958.jpeg)#part0035.xhtml_p28901)
![Image](img/image00959.jpeg)#part0035.xhtml_p28902)
![Image](img/image00960.jpeg)#part0035.xhtml_p20lis06)
![Image](img/image00961.jpeg)#part0035.xhtml_p20lis07)
![Image](img/image00962.jpeg)#part0035.xhtml_p29401)
![Image](img/image00963.jpeg)#part0037.xhtml_p29701)
![Image](img/image00964.jpeg)#part0037.xhtml_p29801)
![Image](img/image00965.jpeg)#part0037.xhtml_p29802)
![Image](img/image00966.jpeg)#part0037.xhtml_p29803)
![Image](img/image00967.jpeg)#part0037.xhtml_p29901)
![Image](img/image00968.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00969.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00970.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00971.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00972.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00973.jpeg)#part0037.xhtml_p30201)
![Image](img/image00974.jpeg)#part0037.xhtml_p30301)
![Image](img/image00975.jpeg)#part0037.xhtml_p30302)
![Image](img/image00976.jpeg)#part0037.xhtml_p30401)
![Image](img/image00977.jpeg)#part0037.xhtml_p30402)
![Image](img/image00978.jpeg)#part0037.xhtml_p30403)
![Image](img/image00979.jpeg)#part0037.xhtml_p30502)
![Image](img/image00980.jpeg)#part0037.xhtml_p30503)
![Image](img/image00981.jpeg)#part0037.xhtml_p30601)
![Image](img/image00982.jpeg)#part0037.xhtml_p30602)
![Image](img/image00983.jpeg)#part0037.xhtml_p21lis02)
![Image](img/image00984.jpeg)#part0037.xhtml_p21lis02)
![Image](img/image00985.jpeg)#part0037.xhtml_p30901)
![Image](img/image00986.jpeg)#part0038.xhtml_p31301)
![Image](img/image00987.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00988.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00989.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00990.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00991.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00992.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00993.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00994.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00995.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00996.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00997.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00998.jpeg)#part0038.xhtml_p32002)
![Image](img/image00999.jpeg)#part0038.xhtml_p32003)
![Image](img/image01000.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01001.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01002.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01003.jpeg)#part0039.xhtml_p23lis01)
![Image](img/image01004.jpeg)#part0039.xhtml_p23lis02)
![Image](img/image01005.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01006.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01007.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01008.jpeg)#part0041.xhtml_p02lis01)
![Image](img/image01009.jpeg)#part0041.xhtml_p02lis02)
![Image](img/image01010.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01011.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01012.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01013.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01014.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01015.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01016.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01017.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01018.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01019.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01020.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01021.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01022.jpeg)#part0041.xhtml_p35001)
![Image](img/image01023.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01024.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01025.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01026.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01027.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01028.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01029.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01030.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01031.jpeg)#part0041.xhtml_p35501)
![Image](img/image01032.jpeg)#part0041.xhtml_p35601)
![Image](img/image01033.jpeg)#part0041.xhtml_p07lis07)
![Image](img/image01034.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01035.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01036.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01037.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01038.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01039.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01040.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01041.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01042.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01043.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01044.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01045.jpeg)#part0041.xhtml_p36301)
![Image](img/image01046.jpeg)#part0041.xhtml_p36302)
![Image](img/image01047.jpeg)#part0041.xhtml_p36303)
![Image](img/image01048.jpeg)#part0041.xhtml_p11lis11)
![Image](img/image01049.jpeg)#part0041.xhtml_p12lis12)
![Image](img/image01050.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01051.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01052.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01053.jpeg)#part0042.xhtml_p14lis14)
![Image](img/image01054.jpeg)#part0042.xhtml_p14lis14)
![Image](img/image01055.jpeg)#part0042.xhtml_p15lis15)
![Image](img/image01056.jpeg)#part0042.xhtml_p15lis15)
![Image](img/image00857.jpeg)#part0025.xhtml_p19401)
![Image](img/image00858.jpeg)#part0027.xhtml_p19501)
![Image](img/image00859.jpeg)#part0027.xhtml_p19601)
![Image](img/image00860.jpeg)#part0027.xhtml_p13lis01)
![Image](img/image00861.jpeg)#part0027.xhtml_p13lis02)
![Image](img/image00862.jpeg)#part0027.xhtml_p13lis03)
![Image](img/image00863.jpeg)#part0027.xhtml_p13lis03)
![Image](img/image00864.jpeg)#part0027.xhtml_p19801)
![Image](img/image00865.jpeg)#part0027.xhtml_p19801)
![Image](img/image00866.jpeg)#part0027.xhtml_p19901)
![Image](img/image00867.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00868.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00869.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00870.jpeg)#part0027.xhtml_p13lis04)
![Image](img/image00871.jpeg)#part0027.xhtml_p20201)
![Image](img/image00872.jpeg)#part0027.xhtml_p20301)
![Image](img/image00873.jpeg)#part0027.xhtml_p20302)
![Image](img/image00874.jpeg)#part0027.xhtml_p20501)
![Image](img/image00875.jpeg)#part0027.xhtml_p20502)
![Image](img/image00876.jpeg)#part0028.xhtml_p14lis01)
![Image](img/image00877.jpeg)#part0028.xhtml_p14lis02)
![Image](img/image00878.jpeg)#part0028.xhtml_p20801)
![Image](img/image00879.jpeg)#part0028.xhtml_p20901)
![Image](img/image00880.jpeg)#part0028.xhtml_p20902)
![Image](img/image00881.jpeg)#part0028.xhtml_p21001)
![Image](img/image00882.jpeg)#part0028.xhtml_p14lis03)
![Image](img/image00883.jpeg)#part0028.xhtml_p21501)
![Image](img/image00884.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00885.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00886.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00887.jpeg)#part0028.xhtml_p14lis04)
![Image](img/image00888.jpeg)#part0028.xhtml_p22101)
![Image](img/image00889.jpeg)#part0030.xhtml_p23101)
![Image](img/image00890.jpeg)#part0030.xhtml_p16lis01)
![Image](img/image00891.jpeg)#part0030.xhtml_p16lis02)
![Image](img/image00892.jpeg)#part0030.xhtml_p23701)
![Image](img/image00893.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00894.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00895.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00896.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00897.jpeg)#part0030.xhtml_p16lis03)
![Image](img/image00898.jpeg)#part0030.xhtml_p24001)
![Image](img/image00899.jpeg)#part0030.xhtml_p24101)
![Image](img/image00900.jpeg)#part0030.xhtml_p24102)
![Image](img/image00901.jpeg)#part0030.xhtml_p16lis04)
![Image](img/image00902.jpeg)#part0030.xhtml_p24201)
![Image](img/image00903.jpeg)#part0030.xhtml_p24202)
![Image](img/image00904.jpeg)#part0030.xhtml_p24203)
![Image](img/image00905.jpeg)#part0030.xhtml_p16lis05)
![Image](img/image00906.jpeg)#part0032.xhtml_p24601)
![Image](img/image00907.jpeg)#part0032.xhtml_p17lis01)
![Image](img/image00908.jpeg)#part0032.xhtml_p17lis02)
![Image](img/image00909.jpeg)#part0032.xhtml_p17lis03)
![Image](img/image00910.jpeg)#part0032.xhtml_p17lis04)
![Image](img/image00911.jpeg)#part0032.xhtml_p24801)
![Image](img/image00912.jpeg)#part0032.xhtml_p24901)
![Image](img/image00913.jpeg)#part0032.xhtml_p17lis05)
![Image](img/image00914.jpeg)#part0032.xhtml_p17lis06)
![Image](img/image00915.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00916.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00917.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00918.jpeg)#part0033.xhtml_p18lis01)
![Image](img/image00919.jpeg)#part0033.xhtml_p19lis01)
![Image](img/image00920.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00921.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00922.jpeg)#part0034.xhtml_p19lis01)
![Image](img/image00923.jpeg)#part0034.xhtml_p19lis02)
![Image](img/image00924.jpeg)#part0034.xhtml_p19lis02)
![Image](img/image00925.jpeg)#part0034.xhtml_p19lis03)
![Image](img/image00926.jpeg)#part0034.xhtml_p19lis04)
![Image](img/image00927.jpeg)#part0034.xhtml_p27101)
![Image](img/image00928.jpeg)#part0034.xhtml_p27201)
![Image](img/image00929.jpeg)#part0034.xhtml_p19lis05)
![Image](img/image00930.jpeg)#part0034.xhtml_p27301)
![Image](img/image00931.jpeg)#part0034.xhtml_p27302)
![Image](img/image00932.jpeg)#part0034.xhtml_p27401)
![Image](img/image00933.jpeg)#part0034.xhtml_p27501)
![Image](img/image00934.jpeg)#part0034.xhtml_p19lis06)
![Image](img/image00935.jpeg)#part0034.xhtml_p19lis07)
![Image](img/image00936.jpeg)#part0034.xhtml_p27701)
![Image](img/image00937.jpeg)#part0034.xhtml_p27801)
![Image](img/image00938.jpeg)#part0034.xhtml_p27802)
![Image](img/image00939.jpeg)#part0034.xhtml_p27803)
![Image](img/image00940.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00941.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00942.jpeg)#part0034.xhtml_p19lis08)
![Image](img/image00943.jpeg)#part0034.xhtml_p28201)
![Image](img/image00944.jpeg)#part0035.xhtml_p28301)
![Image](img/image00945.jpeg)#part0035.xhtml_p20lis01)
![Image](img/image00946.jpeg)#part0035.xhtml_p20lis02)
![Image](img/image00947.jpeg)#part0035.xhtml_p28501)
![Image](img/image00948.jpeg)#part0035.xhtml_p28502)
![Image](img/image00949.jpeg)#part0035.xhtml_p28601)
![Image](img/image00950.jpeg)#part0035.xhtml_p28602)
![Image](img/image00951.jpeg)#part0035.xhtml_p20lis03)
![Image](img/image00952.jpeg)#part0035.xhtml_p20lis03)
![Image](img/image00953.jpeg)#part0035.xhtml_p28701)
![Image](img/image00954.jpeg)#part0035.xhtml_p28702)
![Image](img/image00955.jpeg)#part0035.xhtml_p20lis04)
![Image](img/image00956.jpeg)#part0035.xhtml_p20lis05)
![Image](img/image00957.jpeg)#part0035.xhtml_p28801)
![Image](img/image00958.jpeg)#part0035.xhtml_p28901)
![Image](img/image00959.jpeg)#part0035.xhtml_p28902)
![Image](img/image00960.jpeg)#part0035.xhtml_p20lis06)
![Image](img/image00961.jpeg)#part0035.xhtml_p20lis07)
![Image](img/image00962.jpeg)#part0035.xhtml_p29401)
![Image](img/image00963.jpeg)#part0037.xhtml_p29701)
![Image](img/image00964.jpeg)#part0037.xhtml_p29801)
![Image](img/image00965.jpeg)#part0037.xhtml_p29802)
![Image](img/image00966.jpeg)#part0037.xhtml_p29803)
![Image](img/image00967.jpeg)#part0037.xhtml_p29901)
![Image](img/image00968.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00969.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00970.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00971.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00972.jpeg)#part0037.xhtml_p21lis01)
![Image](img/image00973.jpeg)#part0037.xhtml_p30201)
![Image](img/image00974.jpeg)#part0037.xhtml_p30301)
![Image](img/image00975.jpeg)#part0037.xhtml_p30302)
![Image](img/image00976.jpeg)#part0037.xhtml_p30401)
![Image](img/image00977.jpeg)#part0037.xhtml_p30402)
![Image](img/image00978.jpeg)#part0037.xhtml_p30403)
![Image](img/image00979.jpeg)#part0037.xhtml_p30502)
![Image](img/image00980.jpeg)#part0037.xhtml_p30503)
![Image](img/image00981.jpeg)#part0037.xhtml_p30601)
![Image](img/image00982.jpeg)#part0037.xhtml_p30602)
![Image](img/image00983.jpeg)#part0037.xhtml_p21lis02)
![Image](img/image00984.jpeg)#part0037.xhtml_p21lis02)
![Image](img/image00985.jpeg)#part0037.xhtml_p30901)
![Image](img/image00986.jpeg)#part0038.xhtml_p31301)
![Image](img/image00987.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00988.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00989.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00990.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00991.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00992.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00993.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00994.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00995.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00996.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00997.jpeg)#part0038.xhtml_p22lis01)
![Image](img/image00998.jpeg)#part0038.xhtml_p32002)
![Image](img/image00999.jpeg)#part0038.xhtml_p32003)
![Image](img/image01000.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01001.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01002.jpeg)#part0038.xhtml_p22lis03)
![Image](img/image01003.jpeg)#part0039.xhtml_p23lis01)
![Image](img/image01004.jpeg)#part0039.xhtml_p23lis02)
![Image](img/image01005.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01006.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01007.jpeg)#part0039.xhtml_p23lis03)
![Image](img/image01008.jpeg)#part0041.xhtml_p02lis01)
![Image](img/image01009.jpeg)#part0041.xhtml_p02lis02)
![Image](img/image01010.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01011.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01012.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01013.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01014.jpeg)#part0041.xhtml_p03lis03)
![Image](img/image01015.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01016.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01017.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01018.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01019.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01020.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01021.jpeg)#part0041.xhtml_p04lis04)
![Image](img/image01022.jpeg)#part0041.xhtml_p35001)
![Image](img/image01023.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01024.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01025.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01026.jpeg)#part0041.xhtml_p05lis05)
![Image](img/image01027.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01028.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01029.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01030.jpeg)#part0041.xhtml_p06lis06)
![Image](img/image01031.jpeg)#part0041.xhtml_p35501)
![Image](img/image01032.jpeg)#part0041.xhtml_p35601)
![Image](img/image01033.jpeg)#part0041.xhtml_p07lis07)
![Image](img/image01034.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01035.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01036.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01037.jpeg)#part0041.xhtml_p08lis08)
![Image](img/image01038.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01039.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01040.jpeg)#part0041.xhtml_p09lis09)
![Image](img/image01041.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01042.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01043.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01044.jpeg)#part0041.xhtml_p10lis10)
![Image](img/image01045.jpeg)#part0041.xhtml_p36301)
![Image](img/image01046.jpeg)#part0041.xhtml_p36302)
![Image](img/image01047.jpeg)#part0041.xhtml_p36303)
![Image](img/image01048.jpeg)#part0041.xhtml_p11lis11)
![Image](img/image01049.jpeg)#part0041.xhtml_p12lis12)
![Image](img/image01050.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01051.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01052.jpeg)#part0042.xhtml_p13lis13)
![Image](img/image01053.jpeg)#part0042.xhtml_p14lis14)
![Image](img/image01054.jpeg)#part0042.xhtml_p14lis14)
![Image](img/image01055.jpeg)#part0042.xhtml_p15lis15)
![Image](img/image01056.jpeg)#part0042.xhtml_p15lis15)
