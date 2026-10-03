
# Java：Java 入门指南 - 学习 Java 的快速简单方法

## 引言

如果你对编程至少有一点点兴趣，那么你可能听说过 Java。它是一种遵循 C 和 C++ 风格的编程语言。这些也是非常常见的语言，因此任何已经拥有这些语言经验的人，在学习 Java 时都会感到很从容。

然而，这些语言之间存在一些重要的区别，将在下一章中讨论。

## 本书将教你什么？

编程世界有很多需要学习的内容，而且许多语言之间都有相似之处。正如所提到的，如果你已经熟悉另一种语言，你会发现开始学习 Java 会变得更容易。然而，对于其他人来说，在开始时需要学习一些基础知识。这些起初看起来可能非常寻常，但在开始创建自己的应用程序之前，你需要对基础知识建立稳固的理解。

虽然这本书对初学者很有帮助，但对于已经熟悉计算机使用、甚至可能懂编程的人来说，也是一个极佳的资源。

如果你认真地学习计算机编程，请理解这并不容易。你将学习许多技术术语，并且需要很长时间才能完全理解编程的基础。

## Java 简史

Java 诞生于 1991 年，所以与某些语言相比，它相当新。在太阳微系统公司（Sun Microsystems）工作期间，詹姆斯·高林（James Gosling）和他的团队开始开发 Java。它最初的设计是为了用于家用电器，例如微波炉，这些设备需要包含自己的计算机处理器。

新的 Java 语言必须与各种不同的计算机处理器配合。这是因为它需要兼容各种类型的电器。网景公司（Netscape Incorporated）于 1995 年发布了其 Netscape 浏览器的版本。他们让浏览器兼容 Java 应用程序。

至于“Java”这个名字，是由它的创造者命名的。最初，它被称为“Oak”（橡树）。但很快发现已经有一个同名的编程语言了。在花长时间尝试一个合适的名称来代替 Oak 之后，高林的开发团队决定休息一下，去喝杯咖啡。由于 java 是这种流行饮料的另一种术呼，这为他们为编程语言起一个新名字提供了灵感。

2010 年，太阳微系统被一家名为甲骨文（Oracle）的软件公司收购。从那时起，他们继续开发 Java 及相关产品。

人们经常认为 Java 是一种仅用于互联网应用程序的编程语言。然而，它实际上旨在用于各种目的，运行在许多不同的平台上。这就是为什么那些了解其力量的人认为它是如此流行的原因之一。

## Java 的流行程度

Java 如此流行的原因之一，是因为它太流行了。基本上，它是世界上最常用的编程语言之一。许多程序员在职业生涯的某个阶段都过过 Java 的经验。如果你正在考虑进入编程领域，但无法决定先学哪种语言，Java 是你的推荐选择。

由于 Java 目前特别流行，因此对于那些依赖自由职业程序员和顾问的人来说，它是一个很棒的选择。未来找人帮助维护你的代码将非常容易。这消除了对创建未来仍可访问的代码的一些顾虑。这种无处不在对许多人非常有吸引力，特别是那些为企业外包编程工作的人。

除了流行之外，Java 还非常棒，因为它对于跨平台应用程序易于使用。这意味着它可以为各种不同的操作系统和平台创建程序。Java 在系统的服务器端占据主导地位。

看看 Java 可以做的一些不同事情，以及为什么它是一门非常值得学习的编程语言：

### 平台无关性

这是 Java 如此流行的关键原因之一。平台无关性指的是它在系列不同计算机上运行的能力。如果你有一个能够运行适当 `JRE`（Java 运行环境）的系统，它就能运行 Java 应用程序。这包括 Windows、Mac、Linux、Unix、计算机主机，甚至是许多移动设备。

### Java API

实际上学习 Java 非常简单，因为该语言中只有 50 个不同的关键字。然而，有一个包含成千上万不同类的库。此外，用于程序的方法数量要多得多。库的内容赋予了 Java 各种功能。没有库，Java 将无法拥有其功能，因此它和语言本身一样重要。这个类库被称为 `Java API`。你并不局限于某一个库。

在开始恐慌之前，请理解没有必要学习整个 `Java API`。程序员通常只学习它的小部分。如果有人需要使用一些不熟悉的类，很容易查到它们的详细信息。

### 面向对象

Java 本质上是面向对象的语言。使用它编写的程序将由对象组成。这些是代表抽象概念或真实对象的程序元素。

对象有两个基本特征：

- 对象有自己的行为。这意味着它能够执行特定的任务，这些任务被称为方法。例如，如果一个对象代表应用程序中的一个车辆，它的方法可能包括启动、行驶、停止和碰撞。
- 它们还有自己的状态，基本上就是数据。例如，如果一个对象代表一本书，它可能有关于作者、标题和出版者的数据。

#### 类

类与对象密切相关，因为类是用于创建对象而编写的代码。类描述了定义对象行为和状态的方法与数据。当程序运行时，对象是通过类来创建的。

想象一下你正在开发一个处理工资的应用程序。企业中的员工需要用对象来表示。为了创建这些对象，你需要创建一个类，用来定义让每个员工都成为对象的方法和数据。你可能会将这个类命名为“Employees”（员工）。虽然你的类名不会出现在运行工资应用程序的用户界面，但在编码过程中它对你非常有帮助。

## 入门指南

有几种不同的方法可以获取开始 Java 编程所需的内容。你需要准备这三样基础物品：

- `Java API`
- `Java` 编译器
- `Java` 虚拟机

你可以直接从 Oracle 网站下载它们，该公司是收购了太阳系统（Sun Microsystems）的公司。他们提供了两个不同的下载供你选择：

- 软件开发包 (`SDK`)。它包含了你需要的三个工具。你可以用它来编写 Java 应用程序。请确保获取与你的计算机和操作系统兼容的版本。
- `Java` 运行环境 (`JRE`)。它只包含一个虚拟机和一个应用程序编程语言。然而，对于学习 Java 来说，这是不够的。`JRE` 仅用于运行 Java 应用程序，但不包含实际的编译器。

或者，你可以选择作为商业包的一部分来获取。有很多选择，包括 Borland JBuilder 和 Visual C++。目前，在你开始学习 Java 之初，建议直接从 Oracle 获取 `Java` 运行环境。

即使你决定使用第三方的 `Java` 开发工具，也应该同时使用 Oracle 的 `Java` 运行环境。这是确保你的程序具有尽可能兼容性的最佳方法。

### 使用专用 IDE

这些工具允许你创建代码，并且它们提供了许多让 `Java` 开发变得更简单的功能，尽管它们也可以处理其他编程语言。如果你愿意，也可以简单地使用文本编辑器。然而，专用的 `IDE`（集成开发环境）会让学习过程变得简单得多，因此本书将使用它作为教学工具。

#### NetBeans

有很多工具供你选择。有些需要付费，但也有一些非常棒的免费选择。出于本书的目的，你应该下载 `NetBeans IDE`，它是一个开源的免费软件。确保你下载的是与你的操作系统兼容的 `NetBeans` 版本。完成安装过程，你就可以开始编写你的第一段 `Java` 代码了。

为了遵循书中包含的指令，你需要下载并安装 `NetBeans IDE`。

稍后，当你对 `Java` 编程更加熟悉时，你可能想寻找其他工具使用，但这完全取决于个人选择。

### 使用文本编辑器

计算机程序是用代码创建的，而代码是由原始形式的文本组成的。要编写和编辑代码（即文本），你需要一个文本编辑器。你可能熟悉文字处理器，它们也可以创建文本。然而，它们非常适合创建格式化文本，如信件、报告、书籍等。你需要处理纯的、未格式化的文本，因此像 Word 这样的工具是不可以的。

有很多用于编写代码的文本编辑器，包括你可能已经用过的 Windows 自带的 `Notepad`（记事本）。这些工具很小且通常是免费的，尽管也有付费的商业文本编辑器。

虽然你可以使用 `Notepad` 这样非常基础的编辑器，但使用具有更多功能的工具会容易得多。专门为编码设计的文本编辑器对编程最有用。以下是可以在文本编辑器中寻找的一些优秀功能：

- 代码语法高亮。
- 方便运行和编译程序的快捷键。
- 有帮助的代码补全功能。
- 程序的预览。
- 许多其他让工作更简单的有用功能。

虽然在今天这被认为有点“老派”，但许多程序员仍然在使用简单的文本编辑器。它允许他们处理各种不同的编程语言，而无需切换正在使用的软件。如上所述，某些术语是通用的。

### 学习术语（缩写）

在理解 `Java` 之前，你会遇到一些缩写。先不要急着记忆它们。以下是一些在你开始学习 `Java` 时重要的术语。你会经常看到这些术语。

- `CPU` - 中央处理器：这是计算机的“大脑”。它包含控制单元。
- `CRT` - 阴极射线管：这是一种使用电子束激发荧光粉点的显示器。
- `ALU` - 算术逻辑单元：这是 `CPU` 中处理数学方程的部分。
- `LAN` - 局域网：这是一系列连接的计算机，可以共享存储空间。与互联网不同，它是局部的，位于建筑、学校甚至家庭内部。
- `IDE` - 集成开发环境：这是一个用于创建和编译所有必要组件的环境。
- `DOS` - 磁盘操作系统：这是 IBM 使用的第一个操作系统。名称中的“磁盘”部分是因为存储设备包含旋转磁盘。
- `OOP` - 面向对象编程：这是 `Java` 的一项特性。它涉及到使用小部分来创建一个更大的软件。
- `ROM` - 只读存储器：这是系统上“硬接线”的内存，因此无法被更改。它包含了让系统在没有操作系统的情况下也能运行的信息。
- `RAM` - 随机访问存储器：与用于存储的普通内存不同，`RAM` 是临时的。你可以把它想象成计算机用于执行任务的短期记忆。在计算机关机后，这些数据将会丢失。

### 编程语言基础

现在你对 `Java` 的核心元素已经熟悉了一些，让我们来看看编程语言的基础。

#### 变量

你已经知道任何对象的状态都存储在字段（`field`）中。你会发现 `Java` 中变量和字段都被用到了。然而，对于编程初学者来说，它们看起来可能是一样的。重要的是要接受它们是不同的，并且你应该像那样去对待它们。

变量是任何编程语言中不可或缺的一部分，`Java` 也不例外。变量基本上是一个存储位置、一个与该位置关联的符号名称，以及特定数量的信息（称为值）。这种思考变量的方式相当技术化，但从一开始就学习正确的术语是有帮助的。

这里有一种更简单的思考变量的方式：它们是存储信息以便稍后使用的方法。为了访问这些信息，会使用特定的名称。例如，想象一个网站要求你提供姓名。会出现一个文本框，要求你输入姓名。那个框就代表变量。网站所有者可能给那个框命名为“usernames”（用户名），这就是符号名称。至于你输入的名称，那就是值。这些信息存储在任何地方，就是存储位置。

##### 变量类型

现在你已经知道什么是变量，就可以学习不同的类型了。对于 `Java` 来说，仅仅知道某个东西是变量是不够的。它还需要知道你想用变量存储什么种类型的信息。

这里是一些重要的变量类型：

- **整数（Integer）**。这只是不包含任何小数的数字。例如 5、10、50，甚至有 -5、10 等。如果你尝试使用整数来存储任何带有小数的数字，会导致你的应用程序报错。因此，整数是只能存储整数的变量。
- **字符串（String）**。这用于包含字符字符串的数据。`Java` 会按照你输入的内容原样存储此类数据，而无需考虑其含义或现实世界的价值。例如，如果你将字符串 1 和 5 相加，你不会得到 6。你会得到 15，因为 `Java` 只是简单地将两个变量拼接在一起。

本书不会过深探讨变量类型。现在，更重要的是你理解变量的用途，以及知道有不同的类型可选择。

##### 控制结构

控制结构是指任何查看变量、分析它们，然后根据变量的元素选择执行操作的代码块。

更简单的解释是，计算机在运行应用程序代码时会查看代码的每一行。它从顶部开始，向下运行，通常从左侧移动到右侧。这种方式就像人读书一样，被称为代码流（`code flow`）。

当计算机在代码中移动时，它可能会遇到某些需要做选择的区域。应用程序通常不像书籍那样线性地运行。它们经常会随着不同事件的发生（例如对象之间的相互作用）而跳转。计算机实际上无法自己做出这些选择，因此它需要一套严格的规则来告诉它做什么。这些决策被称为控制结构。

在控制结构内部，计算机将根据你的变量状态做出某些决策。你在书前面的部分已经看过了状态。所以，现在你可以看到对象如何影响计算机在运行不同代码时的反应方式。如果你正在运行赛车游戏，而你的汽车对象的状态显示它已经撞上了墙，计算机就会导致你的汽车撞毁。情况会比这要复杂得多，但目前这是一个很好的例子。

##### 语法

这个词在书中已经出现过，但你可能已经听过它。在人类口语和书语言中，它有自己的定义。然而，对于编程来说，它有点不同。编程语言的语法基本上是定义不同符号如何工作，以及它们以某些方式组合使用时会做什么的规则。

`Java` 使用括号、大括号、变量等不同的符号。你可以将语法想象成编程语言遵循的句法规则。你需要以特定的方式使用某些符号，并妥善地放置内容。如果你没有使用正确的语法，`Java` 将无法理解你想要做什么。这会导致你在运行应用程序时产生错误。

使用正确的语法是你应该尽早学习的内容。始终确保你的输入正确，并检查你的语法是否正确。

##### 数据结构

在计算机编程世界中，数据结构是在计算机内部组织和存储数据的方式。它的实现方式允许计算机高效地使用它。你可以简单地将数据存储在大堆中，计算机也可以使用它。编码和存储数据有许多不同的方法。然而，如果执行得不够高效，你可能会得到一个非常不稳定的应用程序。它可能运行极慢，或者可能无法正常工作。

计算机编程的一个很大部分是尝试创建高效的代码，使其运行良好。这样做还可以让人们更容易对代码进行升级和维护。反过来，也可以更容易改进应用程序、创建额外功能或修复问题。

##### 算术运算符

`Java` 有五种基本的算术运算符。这些是：

- 加法 `+`
- 减法 `-`
- 除法 `/`
- 乘法 `*`
- 取模 `%`

你可能在学校的数学课上就认识它们了。为了了解在 `Java` 中如何使用它们，请看这些示例，它们使用了命名运算符 `op1` 和 `op2`：

| 用途 | 如果为真，将返回 |
| :--- | :--- |
| `op1 + op2` | `op1` 加上 `op2` |
| `op1 - op2` | `op1` 减去 `op2` |
| `op1 / op2` | `op1` 除以 `op2` |
| `op1 * op2` | `op1` 乘以 `op2` |
| `op1 % op2` | 用 `op1` 除以 `op2` 求余数 |

## 你的第一个应用程序：Hello World

一旦你安装了上一节介绍的软件，就可以开始编写一个非常简单的应用程序了。记住，你需要 `NetBeans IDE`，你也被要求下载它。起初，你可能无法理解你所做的一切，但只需按照详细说明完成步骤即可。理解会在之后产生，但每个人都必须从某个地方开始。

你将制作一种人们在初开始学习编程时常见的应用程序。这使得它成为完美的第一个代码片段。它被称为“Hello World”，极其简单。这听起来可能过于基础，但它是掌握 `Java` 一些基本部分的绝佳方法。

### 创建你的 IDE 项目

通过创建 `IDE` 项目，你正在创建一个构建应用程序的环境。使用像 `NetBeans` 这样的 `IDE` 的好处之一是可以避免配置问题。如果你在文本编辑器中创建代码，可能会遇到问题。

要创建 `IDE` 项目，请遵循以下步骤：

1. 启动 `NetBeans IDE`。
2. 点击 `File > New Project`。`New Project` 向导打开。
3. 点击 `Java` 类别展开它，选择 `Java Application` 并点击 `Next`。
4. `Name and Location` 部分打开。输入以下信息：
    - 在 `Project Name` 处输入 `"Hello App"`。
    - 在 `Create Main Class` 处输入 `"helloworldapp.HelloWorld"`。
5. 点击 `Finish`。

你创建了项目，可以看到几个窗口，包括：

- `Navigator` 窗口（导航窗口），你可以在不同类之间轻松导航。
- `Source Editor` 窗口（源代码编辑器），你可以在这里查看刚刚创建的文件 `HelloWorld.java`。
- `Projects` 窗口（项目窗口），显示项目每个组件的层级布局。这包括代码所需的库、源文件等。

你可能需要添加你拥有的 `JDK` 版本。这可能是因为你有一个尚未列在 `NetBeans` 中的新版本，但不常见。

1. 点击 `Tools`。
2. 进入 `Java Platform` 并选择它。
3. 你将看到 `JDK` 版本的列表，并轻松判断你的版本是否已经在列表中。

现在你要在生成的源文件中添加一些代码。在 `New Project` 向导中创建项目时，你勾选了 `Create Main Class` 复选框。这导致 `IDE` 自动生成了一个类。

在源编辑器中，找到以下行：

```java
// TODO code application logic here
```

你需要将该行替换为以下内容：

```java
System.out.println("Hello World!"); // 显示字符串。
```

下一步将向你展示如何为代码添加注释。当你添加注释时，它们不会被视为实际代码的一部分。它们仅供你阅读。

找到以下四行：

```java
/**
 * @author
 */
```

将它们替换为以下四行：

```java
/**
 * 此程序简单地打印“Hello World!”
 *
 */
```

在编写代码时，请务必小心输入完全正确的内容。请确保你使用了正确的大小写，因为 `Java` 启动器和编译器都是区分大小写的。

例如，当你选择名称 `HelloWorldApp` 时，它与输入 `hellellowapp` 是不同的。

接下来，你将保存你的新程序。点击 `File > Save`。

### 将源编译为 .class 文件

你现在将运行你的第一个应用程序。在 `NetBeans` 主菜单中，点击 `Run > Build Project (Hello World App)`。



输出窗口不会在源代码编辑器下方显示构建后的代码。你应该能够看到打印出的“Hello World!”。但重要的是，你应该看到“BUILD SUCCESSFUL”字样。如果是，你就刚刚创建了第一个成功的应用程序。

如果你看到“BUILD FAILED”字样怎么办？你的代码可能存在某种语法错误。别担心，因为使用专门的 IDE（如 Netbeans）处理此类错误会容易得多。错误将显示在你的输出窗口中，并以超链接的形式显示。如果你想找到错误来源，双击该超链接。这将方便你修改错误。之后，你可以再次运行项目，并查看是否解决了问题。

在导航窗口中，你点击 **Files** 选项卡，然后展开 `Hello World App > build > classes > hellapp`。这是为你的项目生成的类文件。

一旦你构建了项目，并确认没有问题，你就可以正式运行它了。在主菜单中，点击 **Run > Run Main Project**。

程序将在你的输出窗口中打印文本“Hello World!”，以及其他构建脚本输出。

你刚刚运行了你的第一个程序。恭喜你！

### Hello World! 是如何工作的

你应该理解 Hello World 应用程序做了什么，但可能急于知道它是如何工作的。再次看看你使用的那些代码：

```java
class HelloWorldApp {
    System.out.println("Hello World!"); // 显示字符串。
}
```

你的应用程序由三个基本部分组成，分别是：

- 你的 `HelloWorldApp` 类。
- 源代码中的注释。
- 你的主方法（main method）。

这些解释将让你对你的代码有一个初步的了解。然而，可能需要一些时间你才能真正理解它是怎么的。

### 你的 HelloWorldApp 类

看这一行：

```java
class HelloWorldApp
```

这创建了一个类定义，告诉代码后续代码应使用哪个类。随后的花括号将包含你想要用于该特定类的代码。这以后可能会变得复杂得多，但现在你只需要学习基础知识。

### 源代码中的注释

看看你代码中 `//` 之后写的文本。那是注释，编译器将完全忽略它。它们仅供程序员阅读。你可能觉得不需要在代码中添加注释，因为你已经知道为什么要做某些事情。请记住，很多代码会变得非常长且复杂。很容易迷失方向，或者忘记为什么要做某些事情，所以创建注释总是重要的。当其他程序员需要处理你创建的代码时，注释也很有帮助，这样他们可以轻松地找到路并理解一切。

有三种不同类型的注释，它们的作用方式略有不同：

```java
/** 你的文档 */
```

编译器将忽略 `/**` 和 `*/` 之间的所有内容，但该注释将被视为“文档注释”（doc comment）。它是 documentation comment 的缩写。所有的文档注释以后可以使用自动化工具编译，从而创建参考文档。

```java
// 文本
```

`//` 之后整行的所有内容都会被编译器忽略。

```java
/* 你的注释 */
```

当你使用这种类型的注释时，`/*` 和 `*/` 之间的所有内容都将被你的编译器忽略。

### 你的主方法

最后，看看这一行实际上告诉你的应用程序 `HelloWorldApp` 类作用的代码：

```java
System.out.println("Hello World!");
```

`System` 类来自 Java 的基础库。它只是告诉系统将“Hello World!”作为标准输出。这就是为什么当你运行应用程序时，屏幕上会打印这些词。

## 更多定义

## 对象

你已经处理过对象，并对它们有了一定的了解。现在你已经完成了一项编程练习，是时候查看关于对象的更多理论以及它们的作用了。在 Java 中，对象是至关重要的，因为它是一种面向对象的语言。它不是唯一以此方式工作的语言，但它是 Java 最受欢迎的功能之一。

为了更好地理解对象，现在环顾四周。你可能会看到许多不同的对象，从你正在使用的电脑，到你的椅子、你的狗，甚至是周围的其他的人。把狗看作一个对象，它有它自己的状态（名称、品种、颜色）以及行为（摇尾巴）。

# Java 代码示例

本节假设你对编程略有了解，或者你愿意自己尝试。如你所见，代码中包含了注释，以便你看到它们的作用。在这里你可以尽情发挥，并玩玩一些预构建好的代码。首先，将它们粘贴到你的 Netbeans 源码编辑器窗口中，编译并运行它们。你会发现它们可以工作，然后你可以通过不断尝试来体验它们是如何工作的。

## 调用方法

这里是一个调用同一类内方法的代码示例。

```java
/* CallingMethodsInSameClass.java
 *
* 演示了如何从同一类中的方法
* 到该类的静态方法
*/
public class CallingMethodsInSameClass {
    public static void main(String[] args) {
        printOne();
        printOne();
        printTwo();
    }

    public static void printOne() {
        System.out.println("Hello World");
    }

    public static void printTwo() {
        printOne();
        printOne();
    }
}
```

### 字符串示例

这里展示了一些不同的字符串操作。

```java
public class StringExample {
    public static void main(String[] args) {
        String s1 = "Computer Science";
        int x = 307;
        String s2 = s1 + " " + x;
        String s3 = s2.substring(10,17);
        String s4 = "is fun";
        String s5 = s2 + s4;

        System.out.println("s1: " + s1);
        System.out.println("s2: " + s2);
        System.out.println("s3: " + s3);
        System.out.println("s4: " + s4);
        System.out.println("s5: " + s5);

        // 显示优先级的的影响
        x = 3;
        int y = 5;
        String s6 = x + y + "total";
        String s7 = "total " + x + y;
        String s8 = " " + x + y + "total";
        System.out.println("s6: " + s6);
        System.out.println("s7: " + s7);
        System.out.println("s8: " + s8);
    }
}
```

### 值参数

Java 中的所有参数都是通过值传递的。这段示例代码向你展示值参数的行为。

```java
public class PrimitiveParameters {
    public static void main(String[] args) {
        go();
    }

    public static void go() {
        int x = 3;
        int y = 2;
        System.out.println("in method go. x: " + x + " y: " + y + ")");
        falseSwap(x,y);
        System.out.println("in method go. x: " + x + " y: " + y + ")");
        moreParameters(x,y);
        System.out.println("in method go. x: " + x + " y: " + y + ")");
    }

    public static void falseSwap(int x, int y) {
        System.out.println("in method falseSwap. x: " + x + " y: " + y + ")");
        int temp = x;
        x = y;
        y = temp;
        System.out.println("in method falseSwap. x: " + x + " y: " + y + ")");
    }

    public static void moreParameters(int a, int b) {
        System.out.println("in method moreParameters. a: " + a + " b: " + b);
        a = a * b;
        b = 12;
        System.out.println("in method moreParameters. a: " + a + " b: " + b);
        falseSwap(b,a);
        System.out.println("in method moreParameters. a: " + a + " b: " + b);
    }
}
```

### 作为值参数的指针

```java
import java.awt.Rectangle;

public class ObjectAsParameters {
    public static void main(String[] args) {
        go();
    }

    public static void go() {
        Rectangle r1 = new Rectangle(0,0,5);
        System.out.println("in method go. " + r1);
        // 原可以是
        r1.setSize(10,5);
        System.out.println("in method go. " + r1);
        altertee(r1);
        System.out.println("in method go. " + r1);
    }

    public static void altertee(Rectangle r) {
        System.out.println("in method altertee. " + r);
        r.setSize(20,30);
    }

    public static void alterPointer(Rectangle r) {
        System.out.println("in method alterPointer. " + r);
        r = new Rectangle(1,1,1);
    }
}
```

### 数组示例



# Java 代码示例集合

## 数组操作示例

```java
public class ArrayExamples {
    public static void main(String[] args) {
        int[] list = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        showList(list);
        findPairs(list, 10);
        showList(list);
        int min = findMin(list);
        System.out.println(min);
        int[] subArray = goodResize(list, 5);
        showList(subArray);
        badResize(list, 5);
        showList(list);
    }

    public static void showList(int[] list) {
        for (int i = 0; i < list.length; i++) {
            System.out.print(list[i] + " ");
        }
        System.out.println();
    }

    public static void findPairs(int[] list, int target) {
        for (int i = 0; i < list.length; i++) {
            for (int j = i + 1; j < list.length; j++) {
                if (list[i] + list[j] == target) {
                    System.out.println("indices " + i + " and " + j + " have values " + list[i] + ", " + list[j]);
                }
            }
        }
    }

    public static int findMin(int[] list) {
        int min = list[0];
        for (int i = 1; i < list.length; i++) {
            if (list[i] < min) {
                min = list[i];
            }
        }
        return min;
    }

    public static void badResize(int[] list, int newSize) {
        int[] temp = new int[newSize];
        int limit = Math.min(list.length, newSize);
        for (int i = 0; i < limit; i++) {
            temp[i] = list[i];
        }
        // 噢！！修改了指针而不是参数。这破坏了参数和参数的关系
        list = temp;
    }

    public static int[] goodResize(int[] list, int newSize) {
        int[] result = new int[newSize];
        int limit = Math.min(list.length, newSize);
        for (int i = 0; i < limit; i++) {
            result[i] = list[i];
        }
        return result;
    }

    public static void bubblesort(int[] list) {
        int temp;
        boolean changed = true;
        for (int i = 0; i < list.length && changed; i++) {
            changed = false;
            for (int j = 0; j < list.length - i - 1; j++) {
                if (list[j] > list[j+1]) {
                    temp = list[j];
                    list[j] = list[j+1];
                    list[j+1] = temp;
                    changed = true;
                }
            }
        }
    }
}
```

## 可以存储任何内容的列表，而不仅仅是整数

### `GenericList` 类实现

```java
/**
 * 一个提供简单列表的类。
 * List 会自动调整大小。用于演示
 * Java 中类的各种
 * 设计和实现细节。
 *
 * @author scottim
 *
 */
public class GenericList {
    // 默认大小的类常量
    private static final int DEFAULT_CAP = 10;

    // 实例变量
    // iValues 存储列表的元素
    // 可能有额外的容量
    private Object[] iValues;
    private int iSize;

    /**
     * 默认的 add 方法。将 x 添加到此列表的末尾。
     * 列表的大小增加 1。
     * @param x 要添加到此列表末尾的值。
     */
    public void add(Object x) {
        insert(iSize, x);
    }

    public Object get(int pos) {
        return iValues[pos];
    }

    /**
     * 在位置 pos 插入 obj。
     * 插入后：get(pos)= x, size()= 旧 size() + 1
     * @param 0 <= pos <= size
     * @param obj 要添加的元素。
     */
    public void insert(int pos, Object obj) {
        ensureCapacity();
        for (int i = iSize; i > pos; i--) {
            iValues[i] = iValues[i - 1];
        }
        iValues[pos] = obj;
        iSize++;
    }

    public Object remove(int pos) {
        Object removedValue = iValues[pos];
        for (int i = pos; i < iSize - 1; i++) {
            iValues[i] = iValues[i + 1];
        }
        iValues[iSize - 1] = null;
        iSize--;
        return removedValue;
    }

    private void ensureCapacity() {
        // 是否有额外的可用容量？
        // 如果没有，则调整大小
        if (iSize == iValues.length)
            resize();
    }

    public int size() {
        return iSize;
    }

    // 因子为 2 缩放内部存储容器
    private void resize() {
        Object[] temp = new Object[iValues.length * 2];
        System.arraycopy(iValues, 0, temp, 0, iValues.length);
        iValues = temp;
    }

    /**
     * 返回此列表的字符串版本。包含大小和
     * 元素。
     */
    public String toString() {
        // 我们可以使用 StringBuilder 来让此更高效。
        // 查看替代版本
        String result = "size: " + iSize + ", elements: [";
        for (int i = 0; i < iSize - 1; i++)
            result += iValues[i].toString() + ", ";
        if (iSize > 0)
            result += iValues[iSize - 1];
        result += "]";
        return result;
    }

    // 实际上并不会有这个和 toString
    // 包含它们仅为了测试
    public String toStringUsingStringBuffer() {
        StringBuilder result = new StringBuilder();
        result.append("size: ");
        result.append(iSize);
        result.append(", elements: [");
        for (int i = 0; i < iSize - 1; i++) {
            result.append(iValues[i]);
            result.append(", ");
        }
        if (iSize > 0) {
            result.append(iValues[iSize - 1]);
        }
        result.append("]");
        return result.toString();
    }

    /**
     * 默认构造函数。创建一个空列表。
     */
    public GenericList() {
        // 重定向到单整数构造函数
        this(DEFAULT_CAP);
        // 其他语句可以放在这里
    }

    /**
     * 构造函数，允许类的用户指定
     * 初始容量，以防他们向新列表添加
     * 许多元素。创建一个空列表。
     * @param initialCap > 0
     */
    public GenericList(int initialCap) {
        assert initialCap > 0 : "违反前置条件。GenericListVer1(initialCap):"
            + "initialCap 必须大于 0。initialCap 的值为: " + initialCap;
        iValues = new Object[initialCap];
        iSize = 0;
    }

    /**
     * 如果此 IntList 等于其他，则返回 true。
     * 前提：无
     * @param other 要与此比较的对象
     * @return 如果 other 是一个非空的 IntList 对象，
     * 且与此 IntList 大小相同并在相同顺序具有
     * 相同的元素，否则返回 false。
     */
    public boolean equals(Object other) {
        boolean result;
        if (other == null)
            // 我们知道这个不是空，所以不能相等
            result = false;
        else if (this == other)
            // 快速检查此和其他是否引用同一个 IntList 对象
            result = true;
        else if (this.getClass() != other.getClass())
            // other 不是 IntList，它们不相等
            result = false;
        else {
            // other 是一个 IntList
            GenericList otherList = (GenericList) other;
            result = this.size() == otherList.size();
            int i = 0;
            while (result && i < iSize) {
                result = this.iValues[i].equals(otherList.iValues[i]);
                i++;
            }
        }
        return result;
    }
}
```

## 将整数写入文件

向文件写入 100 个随机整数，每行一个。

```java
import java.io.PrintStream;
import java.io.IOException;
import java.io.File;
import java.util.Random;

public class WriteToFile {
    public static void main(String[] args) {
        try {
            PrintStream writer = new PrintStream(new File("randInts.txt"));
            Random r = new Random();
            final int LIMIT = 100;
            for (int i = 0; i < LIMIT; i++) {
                writer.println(r.nextInt());
            }
            writer.close();
        } catch (IOException e) {
        }
    }
}
```

## 单词计数代码

```java
import java.io.File;
import java.io.IOException;
import java.util.Map;
import java.util.Scanner;
import java.util.TreeMap;

public class SimpleWordCounter {

    public static void main(String[] args) {
        try {
            File f = new File("ciaFactBook2008.txt");
            Scanner sc = new Scanner(f);
            // sc.useDelimiter("[^a-zA-Z']+")
            Map<String, Integer> wordCount = new TreeMap<>();
            while (sc.hasNext()) {
                String word = sc.next();
                wordCount.put(word, wordCount.getOrDefault(word, 0) + 1);
            }
            System.out.println(wordCount.size());
        } catch (IOException e) {
            System.out.println("无法读取文件.");
        }
    }
}
```

## 使用 `Scanner` 类从文件读取整数

```java
import java.util.Scanner;

public class ScannerAndKeyboard {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        System.out.print("输入你的名字: ");
        String name = s.nextLine();
        System.out.println("Hello " + name + "!");
    }
}
```

版权所有 2015 © 版权权利
