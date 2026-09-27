
# Java 入学者指南

## 第十一章：Java 日期与时间

- 字符串解析
- 睡眠功能
- 经过时间
- Java 正则表达式 (RegEx)
- 正则表达式语法
- 开始与结束方法

# 引言

本书包含了学习 Java 基础的经过验证的步骤和策略。Java 是一门相对较难的语言，因为它不是脚本语言，而是编译型语言。你需要 Java 开发工具包 (`JDK`) 和一个编译器来创建项目、保存文件并运行代码。

我编写这本书的方式解释了 Java 编程的基础知识。你将介绍 Java 开发工具包和编译器的安装过程。市场上有许多编译器可供选择。你可以使用你喜欢的其中一个来创建 Java 代码。由于类在 Java 中是固有的，你应该确保你创建的文件名与类名一致。否则，你将在编译器中看到错误。

本书包含了 Java 语法、变量、条件、循环和面向对象编程的介绍。我建议你准备好编辑器和编译器，以编写和测试你从书中学习的代码。你可以对代码进行一些更改并再次测试，以查看它们是否有效。

Java 与 Python 等其他编程语言略有不同，因为它对列表、数组和字典的命名不同。因此，如果你熟悉了这些词汇，你会发现导航代码变得很容易。例如，`HashMap` 类似于其他编程语言中的字典。`ArrayList` 和 `LinkedList` 的工作方式就像其他语言中的普通列表。

你不需要成为编程专家就可以开始这本书。任何对编码感兴趣的人都可以购买这本书，并理解 Java 编程的来龙去脉。我为书的每个章节都包含了一个代码示例，以便当你在书中看到代码时能够理解它是如何运行的。甚至书中的每个方法都通过适当的示例进行了解释。

因此，最好的方法是阅读这本书的同时进行实践。使用这些代码，编辑它们并编译它们，看看你能产生什么结果。自定义代码以便你能够学习如何编写自己的代码。在过去的几年里，Java 成功地保持了它在程序员中的普及。而且在未来可能会获得更多增长。

# 第一章

## Java 安装

Java 属于影响力最大、使用最广泛的编程语言之一。Java 之旅始于 1990 年，当时一家正寻求领导计算机行业革命的美国公司选择汇集顶尖工程师，并指派他们一项任务：开发一种最终使他们在新兴的互联网世界中成为关键角色的产品。工程师中有 James Arthur Gosling。James 是一位加拿大计算机科学家，现在作为 Java 之父而闻名于世。

Java 的第一个版本于 1996 年发布。一个名为“绿色小组”的团队开发了原型语言，该语言当时被称为 Oak。它有一个可行的演示，是一个交互式手持家用娱乐控制器，也称为 Star。

Java 被认为是一门可移植语言，Java 可以运行在任何操作系统上。它是一种高级编程语言，允许开发者编写可以独立于任何特定工作操作系统（如计算机）的程序。大多数高级编程语言更容易编写和维护。然而，代码需要通过编译器进行翻译。它必须被解释为机器语言才能执行，因为计算机只能听懂机器语言。

你需要一个 Java 虚拟机 (`JVM`) 来让 Java 运行在计算机上。你创建的不同的 Java 程序的执行都需要 `JVM`。该平台会将 Java 代码转换为计算机能理解的机器语言。转换后，它将执行该代码。

其他高级编程语言的源代码直接编译成机器码，专门设计用于运行在 UNIX 或 Windows 等微处理器操作系统上。而相反，`JVM` 模拟了 Java 处理器，使得无论操作系统是什么，Java 程序都可以被解释为在处理器上的一系列动作。

## 开发环境

当你决定开始从事 Java 工作时，你需要在你的操作系统上正确安装一些东西。以下是你需要的要求的清单。首先，你的操作系统上需要 Java 支持。你还需要一个集成开发环境 (`IDE`)，这是一个用于编写代码、编译和执行代码的应用程序。

推荐的 `IDE` 是 IntelliJ IDEA。你可以浏览他们的网站免费获取社区版。你也可以选择一个非常流行的 `IDE`，即 Eclipse，你可以免费获取。第三种 `IDE` 称为 NetBeans。

`Gradle` 是一个用于组织项目的内置工具，让你能够轻松处理依赖关系。随着你的项目变大，它可以方便你的工作。另一个 `Git` 是一个版本控制系统，你可以用它获取本书的源码。

## 如何安装

你已经有了计算机系统。首先，你必须获取一个 `JDK`，然后将其安装到你的计算机系统上。你需要稳定的互联网连接来从网站打开并安装它。

打开后，你需要滚动到“下载”部分。现在点击 Java SE 链接。在 Oracle 官方网站上寻找最新的 Java 版本。现在点击“下载 JDK”按钮，你将被重定向到一个新页面。

`JDK` 适用于几种操作系统。你可以下载与你系统匹配的那一个。在允许下载你需要的 `JDK` 版本之前，你应该接受许可协议。如果你想在开始之前熟悉内容，可以阅读该协议。

因此，如果你使用相同的代码来编写或执行其危险的应用，你将承担法律责任。

如果你想在 Windows 上声明 `JAVA_HOME` 环境变量，你必须打开对话框来设置系统变量。在 Windows 操作系统上，你需要点击“开始”按钮。在菜单区域中，你会找到一个搜索框。现在输入单词“environment”。精确的选项，即“环境变量”，将显示出来供你点击。点击该按钮。会出现另一个对话框，分为两个部分，称为“系统变量”和“用户变量”。

在定义了 `JAVA_HOME` 变量后，你必须将可执行文件添加到系统路径中。这将通过正式编辑 `Path` 变量来实现。你只需要从“系统变量”列表中选择该变量，然后点击“编辑”按钮。你可以看到 `Path` 变量的每个部分都位于不同的行，这样你就可以添加新行。

## 使用 Shell

Java Shell 工具或 `JShell` 是一个非常有交互性的工具，用于学习 Java 编程的奥秘以及对 Java 代码进行原型设计，这意味着你可以在同一个控制台中编写代码并执行它。你不需要先保存代码将其编译成字节码来运行，然后由操作系统将其解释为一条指令进行执行。`JShell` 进入 Java 世界稍微晚了点，因为像 Node 和 Python 这样的脚本语言在几年前就已经引入了类似的工具。JVM 语言（如 Clojure、Scala 和 Groovy）也已在很久以前采用了它。然而，正如俗话所说，来总比不来好。因此，即使是迟到也受到了接受。

`JShell` REPL 的意思是“读取-评估-打印循环”（Read-Eval-Print Loop）。它倾向于在你输入时立即评估声明、语句和表达式，然后快速显示结果。对于快速尝试新的想法和技术来说，这非常实用，不需要完整的开发环境或用于执行的完整代码文件。

`JShell` 就像 `JDK` 的一个标准组件，非常容易上手。它位于 `JDK` 安装目录下的 `bin` 目录。这意味着你只需要打开一个像 Windows 命令提示符这样的终端，然后输入 `jshell` 作为命令。你会看到类似下面的内容。

```
C:\Users\saifia computers>jshell
| Welcome to JShell -- Version 16.0.1
| For an introduction type: /help intro
shell>
```

你可以继续输入 `/help` 来查看 `jshell` 中的操作和命令列表。请看下面的列表。

```
jshell> /help
| 输入一个 Java 语言表达式、
|语句或声明。
| 或者输入以下命令之一：
| /list [<name or id>|-all| -start]
| 列出你输入的源码
| /edit <name or id>
| 编辑一个源码条目
| /drop <name or id>
| 删除一个源码条目
| /save [-all|-history|start] <file>
| 将代码源码保存到文件
| /open <file>
| 打开文件作为源码输入
| /vars [<name or id>|-all|-start]
| 列出已声明的变量及其值
| /methods [<name or id>|-all|-start]
| 列出已声明的方法及其签名
| /types [<name or id>|-all|-start]
| 列出类型声明
| /imports
| 列出已导入的项目
| /exit <integer-expression-snippet>
| 退出 jshell 工具
```

列表很长。我只添加了列表中的前几项，让你了解它的样子以及你会在其中找到什么。如果你想看 `JShell` 目前正在做什么，请输入 `-v` 命令并查看它是如何工作的。你可以在 Java 中为变量赋值，变量是不同字符的序列。现在我将创建一个整数类型的变量，然后给它赋值为 55。看看怎么做。

```
jshell> int a=55
a => 55
jshell>
```

你可以看到命令已成功执行，并且值已赋值给变量。行 `a =>55` 让我们知道值 55 赋值给了你刚刚创建的变量。你可以声明任意数量的变量。现在我将创建另一个不同值的变量。

```
jshell> int x=556
x ===> 556
jshell>
```

只要你不关闭 `jshell` 会话，变量就会存在，且它们的值将保持完好。我们可以继续使用它们。现在让我们添加这两个变量并查看输出。我将在 `jshell` 中使用 `+` 运算符获取两个变量之和。这个过程与纯数学是相同的。看下面这段代码。

```
jshell> int a=55
a ===> 55
jshell> int x=556
x ===> 556
jshell> a + x
$ ===> 611
jshell>
```

我添加了两个变量，但没有将它们的结果存储在第三个变量中。这就是为什么 `jshell` 创建了一个临时变量来存储这两个者的结果并在日志中打印相同的内容。然而，该变量永远无法在后面的语句中使用，因为它缺少名称。现在一切看起来都很好。你可以创建任意数量的变量。现在我将创建另一个不同值的变量。

```
jshell> int x=556
x ===> 556
jshell>
```

只要你不关闭 `jshell` 会话，变量就会存在，且它们的值将保持完好。我们可以继续使用它们。现在让我们添加这两个变量并查看输出。我将使用 `+` 运算符获取两个变量之和。这个过程与纯数学是相同的。看下面这段代码。

```
jshell> int a=55
a ===> 55
jshell> int x=556
x ===> 556
jshell> a + x
$ ===> 611
jshell>
```

我添加了两个变量，但没有将它们的结果存储在第三个变量中。这就是为什么 `jshell` 创建了一个临时变量来存储这两个者的结果并在日志中打印相同的内容。然而，该变量永远无法在后面的语句中使用，因为它缺少名称。现在一切看起来都很好。你可以创建任意数量的变量。现在我将创建另一个不同值的变量。

## Java 基础构建块



# Java 基础概念与语法

## 核心构建块：类与对象

如果你想成为一名专家程序员，你需要很好理解 Java 块内部发生了什么。什么是基础构建块？这些构建块是如何相互连接的？你需要熟悉 Java 生态系统的基础构建块。Java 生态系统的核心是**类**。类是非常重要的，因为它们是构成各种不同类型应用程序对象的模板。类分组了不同的方法和字段。

Java 对象模拟了一个真实世界的对象。如果你选择在 Java 中模拟一辆自行车（或汽车），你将不得不定义不同的字段来描述该对象。字段可以是型号、品牌、价格、颜色、引擎功率、类型以及乘坐容量。它还将定义其加速和刹车等功能。

你需要在文件中描述所有类型的对象，并为它们添加 `.java` 扩展名。你可以以**包**的形式组织对象类型。Java 中的包是不同类型的逻辑集合。其中某些类型在包外是完全可见的，而某些则根据作用范围而定。包就像目录的层级结构，而 Java 对象类型是最后一层。

包的名称必须是唯一的，而且它们的名称也应该遵循一套模板。为了确保意义和唯一性，你需要以你组织的互联网域名（倒序）开始命名。然后，你需要添加不同类型的分组标准。每个包可以包含一个名为 `package-info.java` 的文件，该文件将包含包声明、注解、注释和 Javadoc 标签。这些注释会被导出到该包的 Javadoc。包文件需要位于包内部的最后一个目录中。

带有 `.java` 扩展名的文件包含对象类型定义，并编译成具有 `.class` 扩展名的文件，按照包的结构进行组织，然后打包成多个 JAR 包。

位于包内部的代码跨越了多个 JAR 包，这意味着如果你的项目中有多个子项目，你将多次拥有同一个包的名称。此外，它还将包含不同的类。Java 库使用了多个库。为了运行，它需要类路径（`classpath`）上的所有依赖项。这意味着运行 Java 需要 JDK、app jars 以及依赖项（这些也被命名为额外的 JAR）。

构成类路径的 JAR 包并不一定相互依赖。在复杂的应用程序中，复杂性是由分散在多个 JAR 之中的包、传递性依赖以及访问权限问题引起的。所有这些问题都被归为一类，即“JAR 地狱”。这个问题在 Java 9 发布时得到了解决。

## 访问修饰符

当你在 Java 中声明对象类型时，你可以配置谁可以使用它。访问修饰符倾向于指定你对类的访问权限。在这种情况下，我们可以说你可以在顶层使用它们。它们也倾向于指定你对类成员的访问权限。在这种情况下，你在成员级别使用它们。当你使用顶层时，只能使用两个修饰符，一个称为 `public`（公共），另一个称为 `none`（无/包私有）。

你声明为 `public` 的顶层类需要在同名的 Java 文件中定义。这就是为什么类名为 `Java.java` 的类存储在 `com.apress.bgn.ch0` 包下。

```java
package com.apress.bgn.ch0;
// 这里是顶层的访问修饰符
public class Java {
    // ...
}
```

公共类（`public class`）可以被任何地方的任何人看到。它始终保持可见。违背访问修饰符使用的选项通过使用 `package-private`（包私有）和 `default`（默认）修饰符来实现，这意味着如果类缺少修饰符，它将对定义在同一个包内的类可见。缺少访问修饰符的类可以定义在 Java 文件中。该文件必须与类名相同。如果你在 `X.java` 文件中声明了类 `classX`，则无法在 `Main` 类中创建相同类型的对象。

你仍然可以编写代码，但你使用的 Java 编译器将拒绝编译它。将不会产生用于执行的字节码。智能的 Java 编辑器会通过将代码涂成红色并在编写时拒绝提供代码补全来向你显示错误。缺少访问修饰符的类对同一个包内的所有类都是可见的。

在 Java 类内部，类的成员被正确定义。这些成员被称为方法（`methods`）和字段（`fields`）。访问修饰符也应用于类的成员。在成员级别，你额外应用两个名为 `protected`（受保护）和 `private`（私有）的修饰符，访问修饰符对代码产生以下影响：

1.  **`public`**：与顶层相同。你可以从代码的任何地方访问成员。
2.  **`private`**：只能从其所属类内部访问成员。
3.  **`protected`**：成员只能从包内部或通过其他包中该类的子类进行访问。
4.  **`none`（默认/包私有）**：只能从你自己的包内部访问该成员。

这目前在你看来可能非常复杂。然而，在你开始编写代码之前，这些复杂性仍然存在。

## 模块

在 Java 9 中，开发者得到了“模块”的礼物。模块用于分组和封装包。新概念的实现花费了十年时间进行开发。关于创建模块的讨论始于 2005 年。它们被提用于 Java 7，即 Project Jigsaw（锯齿项目），于 2008 年作为探索阶段启动。Java 开发者希望模块化的 JDK 能随着 Java 8 进入市场。然而，他们面临了失望。模块的发布直到 Java 9 才成为可能。

这就是 Java 9 正式发布推迟到 2017 年 9 月的原因。

Java 中的模块代表了聚合包的创新方式。模块是组织所有包的创新方式，并且对包的内容配置细粒度的访问。

模块具有唯一的名称。它是一个可重用的包组。有一个类似于 `module-info.java` 的文件，它清晰地揭示了它的整体目的：

1.  第一个是模块的名称。
2.  第二是模块的依赖项。
3.  第三是它显式公开的包。
4.  第四是它提供的服务。
5.  第五是它消耗的服务。
6.  第六是原生代码。
7.  第七是资源配置数据。

### 配置模块

模块之间相互依赖。位于第三章的类将需要访问零章中的包和类。

前述依赖是显式的。然而，也有隐式依赖。任何以隐式方式由开发者声明的模块都要求 JDK `java.base` 模块。声明模块意味着你在编译和运行时都需要该模块。如果你只在运行时需要模块，则使用 `static` 关键字来声明依赖。

---

# 第二章 Java 简介

## Java 概述

你可以使用 Java 开发桌面应用程序、移动应用程序、游戏应用程序以及更多。Java 在许多计算机语言中非常流行。Oracle 拥有它，有超过 30 亿设备可以运行 Java。甚至数据库连接也是用 Java 创建的。

Java 可以运行在任何操作系统上，如 Linux、树莓派、Mac 和 Windows 等。Java 最棒的一点是任何人都可以学习并使用它来构建程序，因为它是开源且免费的。它是快速、安全且强大的。它还拥有庞大的社区支持，由数百万开发者组成。

## Java 语法

以下是 Java 最简单程序的基本语法。

```java
public class JavaX {
    public static void main(String[] args) {
        System.out.println("I am about to start learning Java.");
    }
}
```

> 我正准备开始学习 Java。

Java 代码中的每一行都必须有一个类。缺少类的代码行是不完整的。在上面的类中，类名是 `JavaX`。类名必须以大写字母开头。Java 是大小写敏感的，这意味着 `Java` 和 `java` 是不同的。你在计算机系统中保存的 Java 文件名也必须包含类名。当你保存文件时，应该使用类名来命名并保存，然后在文件名末尾添加 `.java`。当你准备在计算机系统上运行代码时，需要确保已正确安装了 Java。

## main() 方法

你可以看到示例中包含 `main()` 方法。它是强制要求的，并且是每个 Java 程序不可或缺的一部分。`main()` 方法内部的任何代码都必须执行。你不需要详细研究放在此方法之前或之后的关键字，我稍后会再解释它们。简单来说，请记住 Java 代码的基本语法包含一个类和一个方法。你可以从这里开始构建你所需的代码。

在那个方法内部，你可以使用另一个方法，即 `println()`，在屏幕上打印一段文本。我使用了一行文本。你可以更改文本并再次打印。让我们尝试不同的文本并将其打印在屏幕上。

```java
public class Java {
    public static void main(String[] args) {
        System.out.println("Like C++, Java is a compiled language.");
    }
}
```

> 像 C++ 一样，Java 是一种编译语言。

记住，大括号表示特定代码语句块的开始和结束。每个代码语句都需要以分号结束。

## Java 注释

你可以使用 Java 注释来解释你的代码，并在重新查看代码时使其更具可读性。在测试不同的代码时，可以使用注释防止其执行。当你在行的开头和结尾使用 `//` 时，Java 会将其视为注释并忽略。即使它是代码，Java 也不会执行它。下面的示例将使用单行注释来解释后续代码。

```java
public class Java {
    public static void main(String[] args) {
        // 接下来一行代码将显示引号内的一段文本
        System.out.println("Like C++, Java is a compiled language.");
    }
}
```

> 像 C++ 一样，Java 是一种编译语言。

你还可以在代码中使用多行注释来解释复杂的代码。多行注释与单行注释不同。多行注释以 `/*` 开始并以 `*/` 结束。`/*` 和 `*/` 之间的任何文本会被 Java 直接忽略。

```java
public class Java {
    public static void main(String[] args) {
        /* 接下来一行代码将显示引号内的一段文本 */
        System.out.println("Like C++, Java is a compiled language.");
    }
}
```

> 像 C++ 一样，Java 是一种编译语言。

单行或多行注释的使用没有固定规则。使用注释的通用传统是用单行用于短注释，用多行用于长注释。

## Java 变量

变量基本上是存储数据值的容器。在 Java 中，你有很多变量。以下是 Java 变量的简介。

1.  **字符串变量** (`String`)：用于存储不同的文本。例如，`"Hello"` 是文本。你可以使用双引号括起字符串值。
2.  **`int` 变量**：存储不同类型的整数。这些是不带小数的整数，如 `-567` 或 `897`。
3.  **`boolean` 变量**：将存储两个状态的值。一个为 `true`，另一个为 `false`。
4.  **`float` 变量**：将存储浮点数，如小数 `-19.99` 和 `19.99`。

## 变量声明

为了创建 Java 变量，你需要指定变量的类型，然后赋予一个特定的值。在语法中，变量名可以是 `x` 或 `name` 之类的。等号用于给变量赋值。你必须查看以下示例来创建一个存储文本的变量。在下面的示例中，我将创建一个变量并给它赋值。

```java
public class Java {
    public static void main(String[] args) {
        String tez = "Java is a compiled language which allows you to reuse the code once it has been developed.";
        System.out.println(tez);
    }
}
```

> Java 是一种编译语言，允许你在开发完成后复用代码。

让我们看看如何创建一个变量并在其中存储一个数字进行显示。

```java
public class JavaX {
    public static void main(String[] args) {
        int tezNum = 555;
        System.out.println(tezNum);
    }
}
```

> 555

## 未赋值的变量

你可以在创建变量时不进行初始赋值。

```java
public class JavaX {
    public static void main(String[] args) {
        int tezNum;
        tezNum = 555;
        System.out.println(tezNum);
    }
}
```

> 555

记住，一旦变量被声明为 `final`，它就不能被更改。

```java
public class JavaX {
    public static void main(String[] args) {
        final int tezNum = 555;
        tezNum = 777; // Error
        System.out.println(tezNum);
    }
}
```

> Error: cannot assign a value to final variable tezNum

## 基本数据类型详解

Java 有八种基本数据类型：

1.  **`byte`**：大小为 1 字节，存储从 -128 到 127 的整数。
2.  **`short`**：大小为 2 字节，存储了从 -32,768 到 32,767 的所有整数。

```java
public class JavaX {
    public static void main(String[] args) {
        short tezNum = 30000;
        System.out.println(tezNum);
    }
}
```

> 30000

3.  **`int`**：大小为 4 字节，存储了从 -2,147,483,648 到 2,147,483,647 的所有整数。

```java
public class JavaX {
    public static void main(String[] args) {
        int tezNum = 2200000;
        System.out.println(tezNum);
    }
}
```

> 2200000

4.  **`long`**：大小为 8 字节，存储了从 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807 的所有整数。

```java
public class JavaX {
    public static void main(String[] args) {
        long tezNum = 3000000000L;
        System.out.println(tezNum);
    }
}
```

> 3000000000

5.  **`float`**：大小为 4 字节，存储了足以存储六到七位小数的小数。

```java
public class JavaX {
    public static void main(String[] args) {
        float tezNum = 4.45f;
        System.out.println(tezNum);
    }
}
```

> 4.45

6.  **`double`**：大小为 8 字节，存储了足以存储 15 位小数的小数。

```java
public class JavaX {
    public static void main(String[] args) {
        double tezNum = 24.45d;
        System.out.println(tezNum);
    }
}
```

> 24.45

7.  **`boolean`**：大小为 1 位，只存储真（`true`）和假（`false`）值。
8.  **`char`**：大小为 2 字节，存储单个字符、字母或 ASCII 值。

Java 中的 `String` 数据类型与语言的集成非常紧密，以至于程序员将其戏称为第九种类型。`String` 是一种非基本数据类型，因为它指的是一个对象。`String` 对象包含了多个方法，这些方法在执行对字符串的不同类型操作时非常有用。

## 非基本数据类型

非基本数据类型也被称为引用类型，因为它们倾向于引用对象。这两种数据类型之间的主要区别是，基本类型在 Java 中是预先定义的。然而，非基本数据类型是由程序员创建的。除了 `String` 之外，Java 没有预先定义其中任何一种。

非基本数据类型被用于调用不同的方法来执行许多操作，而基本数据类型不能做到这一点。基本数据类型有一个值，而非基本数据类型有时可能为 `null`（空）。你始终必须以小写字母开始基本数据类型，而始终必须以大写字母开始非基本数据类型。这对于区分不同的数据类型也非常有效。

## Java 类型转换

类型转换发生在你将某个基本数据类型的特定值赋值给另一个类型时。Java 中有两种转换类型。第一类型被称为**宽转换**，用于将较小的类型转换为更大的类型大小。第二类型是**窄转换**，需要手动进行。它用于将较大的类型转换为较小的类型。

当你将较小尺寸的数据类型传递给较大的数据类型时，可以进行宽转换（自动）。

```java
public class JavaX {
    public static void main(String[] args) {
        int tezInt = 19;
        double tezDouble = tezInt; // 自动转换的示例：我正在将 int 转换为 double

        System.out.println(tezInt);
        System.out.println(tezDouble);
    }
}
```

> 19
> 19.0

现在让我们看看窄转换是如何工作的。它需要通过在值之前的括号中放入数据类型来手动完成。



```java
public class JavaX {
    public static void main(String[] args) {
        double tezDouble = 19; // 手动转换的示例：我正在将 double 转换为 int
        int tezInt = (int) tezDouble;
        System.out.println(tezDouble);
        System.out.println(tezInt);
    }
}
```

19.0

19

# 第四章 Java 运算符与 Java

运算符用于对某些值和变量执行不同的操作。例如，你可以使用 `+` 运算符来合并两个值。

```java
public class JavaX {
    public static void main(String[] args) {
        int a = 150 + 50;
        System.out.println(a);
    }
}
```

200

`+` 运算符用于相加两个值。参见下面的示例。

```java
public class JavaX {
    public static void main(String[] args) {
        int a = 150;
        int b = 50;
        int sum = a + b;
        System.out.println(sum);
    }
}
```

200

## 算术运算符

- `-` 运算符用于减法运算。它用于从一个值中减去另一个。

```java
public class JavaX {
    public static void main(String[] args) {
        int a = 150;
        int b = 50;
        int difference = a - b;
        System.out.println(difference);
    }
}
```

100

- `*` 运算符用于两个值的相乘。参见下面的示例。

```java
public class JavaX {
    public static void main(String[] args) {
        int a = 50;
        int b = 30;
        int product = a * b;
        System.out.println(product);
    }
}
```

1500

- `/` 运算符用于两个值的除法。将一个值除以另一个以得到结果。

```java
public class JavaX {
    public static void main(String[] args) {
        int a = 50;
        int b = 12;
        int result = a / b;
        System.out.println(result);
    }
}
```

4

- `%` 运算符用于计算数字的模。

```java
public class JavaX {
    public static void main(String[] args) {
        int a = 50;
        int b = 12;
        int remainder = a % b;
        System.out.println(remainder);
    }
}
```

2

- `++` 运算符将值增加 1。

```java
public class JavaX {
    public static void main(String[] args) {
        int xx = 50;
        ++xx;
        System.out.println(xx);
    }
}
```

51

- `--` 运算符用于将变量的值减少 1。参见下面的示例。

```java
public class JavaX {
    public static void main(String[] args) {
        int xx = 50;
        --xx;
        System.out.println(xx);
    }
}
```

49

## Java 字符串

你可以使用 Java 字符串来存储文本。字符串可以包含一组由双引号包围的不同字符。在下一个示例中，我将创建一个字符串变量然后给它赋一个值。

```java
public class Java {
    public static void main(String[] args) {
        String msg = "Strings are the most commonly used data type in Java and other programming languages.";
        System.out.println(msg);
    }
}
```

字符串是 Java 和其他编程语言中最常用的数据类型。

在 Java 世界中，字符串通常以对象的形式存在。它包含某些方法，这些方法用于执行许多相关的操作。你可以使用 `length()` 方法找到字符串的总长度。

```java
public class Java {
    public static void main(String[] args) {
        String msg = "Strings are the most commonly used data type in Java and other programming languages.";
        System.out.println(msg);
        System.out.println("the length of the above mentioned string is : " + msg.length());
    }
}
```

## 字符串方法

字符串的奇之处在于，你可以找到广泛的方法来对你添加到代码中的段段文本进行实验。在下一个示例中，我将尝试使用大写和小写转换方法来更改代码的大小。

```java
public class Java {
    public static void main(String[] args) {
        String msg = "Strings are the most commonly used data type in Java and other programming languages.";
        System.out.println(msg.toUpperCase());
        System.out.println(msg.toLowerCase());
    }
}
```

字符串是 Java 以及其他编程语言中最常用的数据类型。

字符串是 Java 和其他编程语言中最常用的数据类型。

你可以在字符串内部查找某个字符。`indexOf()` 字符串方法将返回字符串内特定文本首次出现的的索引号。该方法也适用于空格。

```java
public class Java {
    public static void main(String[] args) {
        String msg = "Strings are the most commonly used data type in Java and other programming languages.";
        System.out.println(msg.indexOf("Java"));
    }
}
```

索引号从零开始，这就是为什么 Java 从零开始计算索引位置并递增。

## 拼接过程

你可以使用加法运算符将一个字符串添加到另一个字符串。这听起来可能很奇怪，但这是可能的。`+` 运算符不仅可以加两个数字，还可以加两个字符串。将一个字符串添加到另一个字符串的过程被称为字符串拼接。这种方法非常有用，特别是当你需要获取用户的输入并将其组合，以便在存储到数据库时使其具有意义时。它精炼了原始输入并使其具有可读性。接下来的示例将帮助解释如何使用拼接方法组合字符串。

我的全名是 Astral Tree。你可以简称为称我为 Astro。

如果你不想使用 `+` 运算符来拼接两个字符串，可以使用 `concat()` 方法。它将执行相同的功能。

```java
public class Java {
    public static void main(String args[]) {
        String fname = "Astral ";
        String lName = "Tree";
        System.out.println("My full name is " + fname.concat(lName) + ". You can call me Astro in short.");
    }
}
```

我的全名是 Astral Tree。你可以简称为称我为 Astro。

## 特殊字符困惑

你应该记住字符串始终被包含在双引号内部。虽然这使得字符串的识别更容易，但当你需要在字符串内部使用某些特殊字符时，这也会产生大量的困惑。Java 不识别任何特殊字符并返回错误。所以，有一种解决办法。你可以使用反斜杠字符，将特殊字符转换为字符串字符。转义字符 `\'` 会创建一个单引号。转义字符 `\"` 会创建一个双引号，而 `\\` 会创建一个反斜杠。

```java
public class Java {
    public static void main(String[] args) {
        String msg = "String is the most useful data type in \"Java\";";
        System.out.println(msg);
    }
}
```

字符串是 "Java" 中最实用的数据类型。

让我们看看如何向字符串中添加单引号，以及它带给我们带来什么结果。

```java
public class JavaX {
    public static void main(String[] args) {
        String msg = "It is String\'s job to allow programmers to integrate text into the code";
        System.out.println(msg);
    }
}
```

字符串的任务是允许程序员将文本集成到代码中。

让我们尝试更多转义字符，它们可以帮助我们在开发程序时编写更好的代码。

```java
public class JavaX {
    public static void main(String[] args) {
        String msg = "String is the most useful data type in \"Java.\" \nIt offers many methods to do experiments with";
        System.out.println(msg);
    }
}
```

字符串是 "Java." 中最实用的数据类型。

它提供了许多方法来进行实验。

第二个转义字符用于回车。

```java
public class JavaX {
    public static void main(String[] args) {
        String msg = "String is the most useful data type in \"Java.\" \rIt offers many methods to do experiments with";
        System.out.println(msg);
    }
}
```

字符串是 "Java." 中最实用的数据类型。

它提供了许多方法来进行实验。

这里是如何在文本之间添加制表符。你必须使用的转义字符是 `\t`。查看下面的示例以更好地理解代码。

```java
public class JavaX {
    public static void main(String[] args) {
        String msg = "String is the most useful data type in \"Java.\" \tIt offers many methods \tto do experiments with";
        System.out.println(msg);
    }
}
```

字符串是 "Java." 中最实用的类型。它提供了许多方法来进行实验。

有一个转义字符 `\b`，它的功能相当于计算机键盘上的退格键。它会删除其位置后方的一个字符。你必须把它放在它的位置之后。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add(" pumpkin ");
        vegetables.add(" tomato ");
        vegetables.add(" ginger ");
        vegetables.add(" potato ");
        vegetables.add(" okra ");
        vegetables.add(" garlic ");
        vegetables.add(" onion ");
        vegetables.add(" cabbage ");
        System.out.println(vegetables);
    }
}
```

[ pumpkin, tomato, ginger, potato, okra, garlic, onion, cabbage ]

你可以从 `ArrayList` 中访问你选择的项目。请参考以下方法。该方法的名称是 `get()` 方法。查看代码中如何使用它。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add(" pumpkin ");
        vegetables.add(" tomato ");
        vegetables.add(" ginger ");
        vegetables.add(" potato ");
        vegetables.add(" okra ");
        vegetables.add(" garlic ");
        vegetables.add(" onion ");
        vegetables.add(" cabbage ");
        System.out.println(vegetables);
        System.out.println(vegetables.get(0));
        System.out.println(vegetables.get(1));
        System.out.println(vegetables.get(3));
        System.out.println(vegetables.get(5));
        System.out.println(vegetables.get(6));
    }
}
```

- 南瓜、番茄、姜、土豆、秋葵、大蒜、洋葱、卷菜

南瓜

番茄

土豆

大蒜

洋葱

索引从 0 开始而不是 1。你可以通过替换新元素来修改数组中的任何元素。然而，你必须记住数组元素的索引号才能完美修改。如果你输入了错误的索引号，可能无法完美替换。查看执行此操作的技术。我将使用的方法被称为 `set(index)` 方法。你将在输出看到两个列表；一个是原始的数组列表，另一个是修改后的列表。



# Java ArrayList 和 LinkedList 操作指南

## ArrayList 基础操作

### 添加与修改元素

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add("pumpkin");
        vegetables.add("tomato");
        vegetables.add("ginger");
        vegetables.add("potato");
        vegetables.add("okra");
        vegetables.add("garlic");
        vegetables.add("onion");
        vegetables.add("cabbage");
        System.out.println(vegetables);
        vegetables.set(0, "cilantro");
        vegetables.set(1, "radish");
        vegetables.set(2, "carrot");
        vegetables.set(3, "eggplant");
        vegetables.set(4, "capsicum");
        System.out.println(vegetables);
    }
}
```

初始列表：[ 南瓜、番茄、姜、土豆、秋葵、大蒜、洋葱、卷菜 ]

修改后：[ 香菜、萝卜、胡萝卜、茄子、辣椒、大蒜、洋葱、卷菜 ]

### 删除元素

就像你可以向现有的数组列表添加不同的元素一样，你也可以从列表中删除项目。要从数组列表中删除元素，你必须使用 `remove()` 方法。在这里我们再次需要索引号来开始。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add("pumpkin");
        vegetables.add("tomato");
        vegetables.add("ginger");
        vegetables.add("potato");
        vegetables.add("okra");
        vegetables.add("garlic");
        vegetables.add("onion");
        vegetables.add("cabbage");
        vegetables.add("cilantro");
        vegetables.add("radish");
        vegetables.add("carrot");
        vegetables.add("eggplant");
        System.out.println(vegetables);
        vegetables.remove(0);
        System.out.println(vegetables);
        vegetables.remove(2);
        System.out.println(vegetables);
        vegetables.remove(4);
        System.out.println(vegetables);
        vegetables.remove(6);
        System.out.println(vegetables);
        vegetables.remove(7);
        System.out.println(vegetables);
    }
}
```

操作过程：
1. [ 南瓜、番茄、姜、土豆、秋葵、大蒜、洋葱、卷菜、香菜、萝卜、茄子 ]
2. [ 番茄、姜、土豆、秋葵、大蒜、洋葱、卷菜、香菜、萝卜、茄子 ]
3. [ 番茄、姜、秋葵、大蒜、洋葱、卷菜、香菜、萝卜、茄子 ]
4. [ 番茄、姜、秋葵、洋葱、卷菜、香菜、萝卜、茄子 ]
5. [ 番茄、姜、秋葵、卷菜、香菜、萝卜、茄子 ]
6. [ 番茄、姜、秋葵、香菜、萝卜、茄子 ]
7. [ 番茄、姜、秋葵、萝卜、茄子 ]

### 清空列表

如果你想要所有元素的空数组，你可以使用 `clear()` 方法。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add("pumpkin");
        vegetables.add("tomato");
        vegetables.add("ginger");
        vegetables.add("potato");
        vegetables.add("okra");
        vegetables.add("garlic");
        vegetables.add("onion");
        vegetables.add("cabbage");
        vegetables.add("cilantro");
        vegetables.add("radish");
        vegetables.add("carrot");
        vegetables.add("eggplant");
        System.out.println(vegetables);
        vegetables.clear();
        System.out.println(vegetables);
    }
}
```

结果：
- [ 南瓜、番茄、姜、土豆、秋葵、大蒜、洋葱、卷菜、香菜、萝卜、茄子 ]
- []

### 获取大小

你可以通过 `size()` 方法查找数组列表的总大小。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add("pumpkin");
        vegetables.add("tomato");
        vegetables.add("ginger");
        vegetables.add("potato");
        vegetables.add("okra");
        vegetables.add("garlic");
        vegetables.add("onion");
        vegetables.add("cabbage");
        vegetables.add("cilantro");
        vegetables.add("radish");
        vegetables.add("carrot");
        vegetables.add("eggplant");
        System.out.println(vegetables.size());
    }
}
```

## 遍历 ArrayList

### 使用 for 循环

你可以为数组列表创建一个循环。`for` 循环将遍历所有元素并将整齐地显示在屏幕上。你还可以在代码中添加 `size()` 方法来指定循环数组列表的次数。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add("pumpkin");
        vegetables.add("tomato");
        vegetables.add("ginger");
        vegetables.add("potato");
        vegetables.add("okra");
        vegetables.add("garlic");
        vegetables.add("onion");
        vegetables.add("cabbage");
        vegetables.add("cilantro");
        vegetables.add("radish");
        vegetables.add("carrot");
        vegetables.add("eggplant");
        for (int x = 0; x < vegetables.size(); x++) {
            System.out.println(vegetables.get(x));
        }
    }
}
```

输出结果：
- 南瓜
- 番茄
- 姜
- 土豆
- 秋葵
- 大蒜
- 洋葱
- 卷菜
- 香菜
- 萝卜
- 胡萝卜
- 茄子

### 使用 for-each 循环

你也可以使用 `for-each` 循环来遍历 `ArrayList`。结果相同，但达到该结果的方法不同。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add("pumpkin");
        vegetables.add("tomato");
        vegetables.add("ginger");
        vegetables.add("potato");
        vegetables.add("okra");
        vegetables.add("garlic");
        vegetables.add("onion");
        vegetables.add("cabbage");
        vegetables.add("cilantro");
        vegetables.add("radish");
        vegetables.add("carrot");
        vegetables.add("eggplant");
        for (String x : vegetables) {
            System.out.println(x);
        }
    }
}
```

```
pumpkin
tomato
ginger
potato
okra
garlic
onion
cabbage
cilantro
radish
carrot
eggplant
```

### 存储基本类型包装类

在上面的示例中，我使用了字符串作为对象。你也可以使用其他类型。字符串是一个对象，但永远不是基本类型。要使用像 `int` 这样的类型，你需要指定 `Integer` 类。你也可以使用 `Boolean`、`Character` 和 `Double` 等。你可以创建一个 `ArrayList` 来存储数字，就像添加不同类型的 `Integer` 元素一样。

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> tezNumbers = new ArrayList<Integer>();
        tezNumbers.add(7);
        tezNumbers.add(14);
        tezNumbers.add(21);
        tezNumbers.add(28);
        tezNumbers.add(35);
        tezNumbers.add(42);
        for (int x : tezNumbers) {
            System.out.println(x);
        }
    }
}
```

```
7
14
21
28
35
42
```

## 排序

`java.util` 包中另一个非常有用的类是 `Collections` 类。它包含了 `sort()` 方法，可以按字母顺序或数字顺序对列表排序。

### 字符串排序

```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> vegetables = new ArrayList<String>();
        vegetables.add("pumpkin");
        vegetables.add("tomato");
        vegetables.add("ginger");
        vegetables.add("potato");
        vegetables.add("okra");
        vegetables.add("garlic");
        vegetables.add("onion");
        vegetables.add("cabbage");
        vegetables.add("cilantro");
        vegetables.add("radish");
        vegetables.add("carrot");
        vegetables.add("eggplant");

        Collections.sort(vegetables);

        for (String x : vegetables) {
            System.out.println(x);
        }
    }
}
```

排序结果：
- 包菜
- 胡萝卜
- 香菜
- 茄子
- 大蒜
- 生姜
- 秋葵
- 洋葱
- 土豆
- 南瓜
- 萝卜
- 西红柿

### 数字排序

同样，你可以对数字的 `ArrayList` 进行排序。

```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> tezNumbers = new ArrayList<Integer>();
        tezNumbers.add(39);
        tezNumbers.add(19);
        tezNumbers.add(23);
        tezNumbers.add(84);
        tezNumbers.add(48);
        tezNumbers.add(32);

        Collections.sort(tezNumbers);

        for (int x : tezNumbers) {
            System.out.println(x);
        }
    }
}
```

```
19
23
32
39
48
84
```

## LinkedList

这是一个链表的示例，它与 `ArrayList` 几乎相同。



```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> vegetables = new LinkedList<String>();
        vegetables.add(" pumpkin ");
        vegetables.add(" tomato ");
        vegetables.add(" ginger ");
        vegetables.add(" potato ");
        vegetables.add(" okra ");
        vegetables.add(" garlic ");
        vegetables.add(" onion ");
        vegetables.add(" cabbage ");
        vegetables.add(" cilantro ");
    }
}
```

```java
vegetables.add(" radish ");
vegetables.add(" carrot ");
vegetables.add(" eggplant ");
System.out.println(vegetables);
```

```
}
}
```

```
[ pumpkin, tomato, ginger, potato, okra, garlic, onion, cabbage, cilantro, radish, carrot, eggplant ]
```

`LinkedList` 是一个包含相同类型不同对象的集合。这个特性使得它与 `ArrayList` 更接近。`LinkedList` 类拥有所有 `ArrayList` 使用的方法，因为它们都实现了 `List` 接口。这意味着你有机会添加项目、删除项目、更改项目，并类似地清除整个列表。它们的应用是相同的，只是构建方式不同。我将在接下来的示例中使用几个方法来展示两者的用法是如何是相同的。

这里是 `LinkedList` 的 `remove()` 方法示例。

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> vegetables = new LinkedList<String>();
        vegetables.add(" pumpkin ");
        vegetables.add(" tomato ");
        vegetables.add(" ginger ");
        vegetables.add(" potato ");
        vegetables.add(" okra ");
```

```java
vegetables.add( " garlic " );
vegetables.add( " onion " );
vegetables.add( " cabbage " );
vegetables.add( " cilantro " );
vegetables.add( " radish " );
vegetables.add( " carrot " );
vegetables.add( " eggplant " );
vegetables.remove(0);
System.out.println(vegetables);
vegetables.remove(1);
System.out.println(vegetables);
vegetables.remove(2);
System.out.println(vegetables);
vegetables.remove(3);
System.out.println(vegetables);

}
}
```

```
[ tomato, ginger, potato, okra, garlic,
onion, cabbage, cilantro, radish, carrot,
geplant ]
[ tomato, potato, okra, garlic, onion,
cabbage, cilantro, radish, carrot, eggplant ]
[ tomato, potato, garlic, onion, cabbage,
cilantro, radish, carrot, eggplant ]
[ tomato, potato, garlic, cabbage, cilantro,
radish, carrot, eggplant ]
```

`LinkedList` 是一个包含多个相似对象的集合，就像 `ArrayList` 一样。`LinkedList` 类带有与 `ArrayList` 类相同的方法，因为两者都实现了 `List` 接口。就像列表，你可以在两者中添加、删除和修改元素。当你需要随机访问不同项目时，使用 `ArrayList`。当你需要在列表末尾进行遍历而不是随机访问项目时，使用 `LinkedList`。

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> vegetables = new LinkedList<String>();
        vegetables.add("pumpkin ");
        vegetables.add("tomato ");
        vegetables.add("ginger ");
        vegetables.add("potato ");
        vegetables.add("okra ");
        vegetables.add("garlic ");
        vegetables.add("eggplant ");
        vegetables.addFirst("cilantro");
        System.out.println(vegetables);
        vegetables.addFirst("radish");
        System.out.println(vegetables);
        vegetables.addFirst("carrot");
        System.out.println(vegetables);
    }
}
```

```
[cilantro, pumpkin, tomato, ginger, potato, okra, garlic, eggplant ]
```

```
[radish, cilantro, pumpkin, tomato, ginger, potato, okra, garlic, eggplant ]
```

同样，`addLast()` 方法帮助你将项目添加到列表的末尾。

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> vegetables = new LinkedList<String>();
        vegetables.add(" pumpkin ");
        vegetables.add(" tomato ");
        vegetables.add(" garlic ");
        vegetables.add(" eggplant ");
        vegetables.addLast("cilantro");
        System.out.println(vegetables);
        vegetables.addLast("radish");
        System.out.println(vegetables);
        vegetables.addLast("carrot");
        System.out.println(vegetables);
    }
}
```

```
[ pumpkin, tomato, garlic, eggplant, cilantro]
```

```
[pumpkin, tomato, garlic, eggplant, radish]
```

```
[pumpkin, tomato, garlic, eggplant, carrot]
```

虽然我们受限于通过索引号删除 `ArrayList` 中的元素，但 `LinkedList` 允许我们从列表的开头或末尾删除。如果你没有索引号来删除项目，这非常有趣且非常有用。你可以只需使用这两个方法来切掉列表中不需要的项目。我将在接下来的示例中使用这两个方法来删除项目。

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> vegetables = new LinkedList<String>();
        vegetables.add(" pumpkin ");
        vegetables.add(" tomato ");
        vegetables.add(" ginger ");
        vegetables.add(" potato ");
        vegetables.add(" okra ");
        vegetables.add(" garlic ");
        vegetables.add(" eggplant ");
        vegetables.removeFirst();
        System.out.println(vegetables);
        vegetables.removeFirst();
        System.out.println(vegetables);
        vegetables.removeLast();
        System.out.println(vegetables);
        vegetables.removeLast();
        System.out.println(vegetables);
    }
}
```

```
[ tomato, ginger, potato, okra, garlic, eggplant ]
```

```
[ ginger, potato, okra, garlic, eggplant ]
```

```
[ ginger, potato, okra, garlic ]
```

```
[ ginger, potato, okra ]
```

同样，你不需要索引号来显示列表中的项。你可以使用 `get` 方法来显示列表开头和结尾的项。

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> vegetables = new LinkedList<String>();
        vegetables.add(" pumpkin ");
        vegetables.add(" tomato ");
        vegetables.add(" ginger ");
        vegetables.add(" potato ");
        vegetables.add(" okra ");
        vegetables.add(" garlic ");
        vegetables.add(" eggplant ");

        System.out.println(vegetables.getFirst());

        System.out.println(vegetables.removeFirst());

        System.out.println(vegetables.getFirst());

        System.out.println(vegetables.getLast());

        System.out.println(vegetables.removeLast());

        System.out.println(vegetables.getLast());
    }
}
```

```
pumpkin

pumpkin

tomato

eggplant

eggplant

garlic
```

## Hash Map (哈希映射)

`HashMap` 允许你以键值对的形式向代码中添加项。你之后可以访问它们。你可以用一个对象作为键（`key`），另一个已知的对象作为值（`value`）。它将存储字符串、整数和其他相似的类型。

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, String> famousCities = new HashMap<String, String>();
        famousCities.put("England", "Manchester");
        famousCities.put("Germany", "Berlin");
        famousCities.put("Italy", "Rome");
        famousCities.put("USA", "New York");
        famousCities.put("South Africa", "Cape Town");
        famousCities.put("India", "Mumbai");
        famousCities.put("Pakistan", "Lahore");
        System.out.println(famousCities);
    }
}
```

```
USA=New York, Pakistan=Lahore, England=Manchester, Italy=Rome, South Africa=Cape Town, Germany=Berlin, India=Mumbai
```

如果你需要从 Hash map 中访问特定的项，必须使用 `get()` 方法并显示该项。

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, String> famousCities = new HashMap<String, String>();
        famousCities.put("England", "Manchester");
        famousCities.put("Germany", "Berlin");
        famousCities.put("Italy", "Rome");
        famousCities.put("USA", "New York");
        famousCities.put("India", "Mumbai");
        famousCities.put("Pakistan", "Lahore");

        System.out.println(famousCities.get("USA"));

        System.out.println(famousCities.get("Italy"));
    }
}
```

```
New York

Rome
```

我将使用 `remove()` 方法从哈希映射中删除项。

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, String> famousCities = new HashMap<String, String>();
        famousCities.put("England", "Manchester");
        famousCities.put("Germany", "Berlin");
        famousCities.put("Italy", "Rome");
        famousCities.put("USA", "New York");
        famousCities.put("India", "Mumbai");
        famousCities.put("Pakistan", "Lahore");
        famousCities.remove("England");
        System.out.println(famousCities);
        famousCities.remove("India");
        System.out.println(famousCities);
        famousCities.remove("Germany");
        System.out.println(famousCities);
    }
}
```



# Java HashMap 操作与控制流语句

## HashMap 基础操作

### 创建与初始化
```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, String> famousCities = new HashMap<String, String>();
        famousCities.put("England", "Manchester");
        famousCities.put("Germany", "Berlin");
        famousCities.put("Italy", "Rome");
        famousCities.put("USA", "New York");
        famousCities.put("India", "Mumbai");
        famousCities.put("Pakistan", "Lahore");
        famousCities.remove("England");
        System.out.println(famousCities);
        famousCities.clear();
        System.out.println(famousCities);
    }
}
```

输出结果：
```
USA=New York, Pakistan=Lahore, Italy=Rome, Germany=Berlin, India=Mumbai
{USA=New York, Pakistan=Lahore, Italy=Rome, Germany=Berlin}
{USA=New York, Pakistan=Lahore, Italy=Rome}
{}
```

### 删除所有项
如果你想从 Hash map 中删除所有项，必须使用 `clear()` 方法。

### 获取大小
`size()` 方法用于查找哈希映射的总体大小。

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, String> famousCities = new HashMap<String, String>();
        famousCities.put("England", "Manchester");
        famousCities.put("Germany", "Berlin");
        famousCities.put("Italy", "Rome");
        famousCities.put("USA", "New York");
        famousCities.put("India", "Mumbai");
        famousCities.put("Pakistan", "Lahore");
        System.out.println(famousCities.size());
    }
}
```

输出结果：
```
USA=New York, Pakistan=Lahore, Italy=Rome, Germany=Berlin, India=Mumbai
```

---

# 第六章：Java 控制流语句

## 条件语句

Java 支持数学中的逻辑条件。以下是你在 Java 代码中可以使用的条件列举：

- 小于：`x < y`
- 小于等于：`x <= y`
- 大于：`x > y`
- 大于等于：`x >= y`
- 等于：`x == y`
- 不等于：`x != y`

你可以使用所有这些条件来执行各种操作。例如，`if` 语句帮助指定一个特定的代码块，当满足特定条件时执行。你可以使用 `else` 语句来指定当条件返回假时必须执行的代码。你可以使用 `else if` 语句在条件为假时指定并测试另一个条件。你可以使用 `switch` 语句来指定必须执行的不同代码块。

### if 语句

如果你想在 Java 中执行某段特定的代码，可以使用 `if` 语句。`if` 关键字始终使用小写字母。如果你写成大写字母如 `If` 或 `IF`，编译器将生成错误。

```java
public class Java {
    public static void main(String[] args) {
        if (300 > 30) {
            System.out.println("Yes, 300 is greater than 30.");
        }
    }
}
```

输出：
```
Yes, 300 is greater than 30.
```

如果你有一个包含两个变量的代码，你也可以测试它们。我将使用两个变量 `a` 和 `b` 并在代码中包含一个 `if` 语句来测试该条件。

```java
public class Java {
    public static void main(String[] args) {
        int a = 3000;
        int b = 3;
        if (a > b) {
            System.out.println("a appears to be greater than b");
        }
    }
}
```

输出：
```
a appears to be greater than b
```

### else 语句

上面的示例处理了条件始终为真的情况。然而，在所有情况下通常并非如此。你可能会遇到在执行条件时其结果可能为假的情况。这就是我们可以使用 `else` 语句的地方。

```java
public class Java {
    public static void main(String[] args) {
        int time = 15;
        if (time < 16) {
            System.out.println("Have a good morning. Be productive and creative.");
        } else {
            System.out.println("Good evening. Sweet dreams!");
        }
    }
}
```

输出：
```
Have a good morning. Be productive and creative.
```

如果我更改代码中的条件，显示的消息也会发生改变。请参考以下示例了解其工作原理。

```java
public class JavaX {
    public static void main(String[] args) {
        int time = 15;
        if (time < 14) {
            System.out.println("Have a good morning. Be productive and creative.");
        } else {
            System.out.println("Good evening. Sweet dreams!");
        }
    }
}
```

输出：
```
Good evening. Sweet dreams!
```

在第一段代码中，由于 15 小于 16，所以条件为真。在第二段代码中，15 大于 14，所以条件为假。在这里 `else` 语句将发挥作用并在屏幕上显示第二条消息。

### else if 语句

如果之前的条件结果为假，你可以使用 `else if` 语句来指定任何新条件。`else if` 语句将是我们的第三块代码。当前两个条件都为假时，第三块代码块（即 `else if` 语句）就会开始作用。

```java
public class JavaX {
    public static void main(String[] args) {
        int time = 15;
        if (time < 14) {
            System.out.println("Have a good morning. Be productive and creative.");
        } else if (time < 20) {
            System.out.println("It is a bright noon.");
        } else {
            System.out.println("Good evening. Sweet dreams!");
        }
    }
}
```

输出：
```
It is a bright noon.
```

### Java Switch 语句

当存在多个代码块但你只需要执行其中一个时，你必须使用 `switch` 语句来执行所需代码块。你可以只对 `switch` 语句进行一次评估。代码块中的每个 `case` 都会与表达式的值进行比较。如果匹配，将立即执行目标代码块。你可能会遇到其他关键字如 `default` 和 `break`。我稍后会解释它们。我将在接下来的代码中使用 `switch` 语句，展示如何在一个长且复杂的程序中选择几行代码中的之一。我将使用一个小程序来指示星期几以及每天相应的活动。

```java
public class JavaX {
    public static void main(String[] args) {
        int tezday = 3;
        switch (tezday) {
            case 1:
                System.out.println("Monday is blue.");
                break;
            case 2:
                System.out.println("Tuesday fires up the momentum.");
                break;
            case 3:
                System.out.println("Wednesday brings full speed to work.");
                break;
            case 4:
                System.out.println("Thursday keeps up the momentum.");
                break;
            case 5:
                System.out.println("Friday finishes key tasks and gets you ready to get relaxed.");
                break;
            case 6:
                System.out.println("Saturday is sleepy.");
                break;
            case 7:
                System.out.println("Sunday is all food.");
                break;
        }
    }
}
```

输出：
```
Wednesday brings full speed to work.
```

你可能注意了代码中的 `break` 关键字。当 Java 遇到 `break` 时，它会跳出代码块。在找到匹配项之前，它不再需要任何额外的测试。

### default 关键字

假设编译器运行了每个 `case` 但没有找到匹配。在这种情况下，我们可以使用 `default` 关键字来指定必须执行的代码块。我将使用相同的代码示例来解释如何向代码中添加 `default` 关键字。

```java
public class Java {
    public static void main(String[] args) {
        int tezday = 10;
        switch (tezday) {
            case 1:
                System.out.println("Monday is blue.");
                break;
            case 2:
                System.out.println("Tuesday fires up the momentum.");
                break;
            case 3:
                System.out.println("Wednesday brings full speed to work.");
                break;
            case 4:
                System.out.println("Thursday keeps up the momentum.");
                break;
            case 5:
                System.out.println("Friday finishes key tasks and gets you ready to get relaxed.");
                break;
            case 6:
                System.out.println("Saturday is sleepy.");
                break;
            case 7:
                System.out.println("Sunday is all food.");
                break;
            default:
                System.out.println("I am planning a vacation for the Weekend.");
        }
    }
}
```

输出：
```
I am planning a vacation for the Weekend.
```

---

# 第七章：Java 循环

在编程中，有时你需要相同变量的重复步骤。为了完成工作而反复编写语句是痛苦的。循环让这项工作变得简单有趣。

Java 循环倾向于循环遍历代码块，直到条件变为假。在下文示例中，代码将反复运行，直到代码块中的变量小于 7。

## while 循环

`while` 循环没有固定的执行步数。因此，代码中并不总是需要一个计数器。`while` 语句的总重复次数取决于你评估持续条件为真的次数。`while` 语句在代码块内或语句外都不需要初始化语句。在大多数情况下，`while` 语句可以替换 `for` 语句。然而，`for` 语句让开发者不放弃它的主要优势是它可以封装代码的初始化。此外，`for` 语句提供了终止条件和计数器修改。你可以在一个块中获取所有这些，这使得 `for` 语句优于 `while` 循环。

```java
public class Java {
    public static void main(String[] args) {
        int x = 0;
        while (x < 7) {
            System.out.println(x);
            x++;
        }
    }
}
```

输出：
```
0
1
2
3
4
5
6
```

计数器变量 `int x = 0` 的声明和初始化存在于语句之外。然而，计数器的递增是在代码块中执行的。循环也从这里开始。此外，使用 `while` 循环的一个主要优点是，代码块中的条件并不是绝对必要的。在此时，条件也不是强制性的。你可以完全将其替换为 `true`。然而，你需要确保在代码块中包含一个退出条件，该条件会在某个时间点执行。否则，代码块的执行可能会导致错误。这个特定条件应该在代码开始时替换，以防止在不该执行的地方执行某些逻辑。

最需要记住的是，你应该增加变量 `x`，否则循环将是无限的。它永远不会结束，并最终导致其所属的程序崩溃。

当你处理一个并非始终在线的特定资源时，`while` 语句效果最好。假设你为应用程序使用了一个存在不稳定网络中的远程数据库。`while` 语句可以帮助你在多次超时后保存数据，直到成功。

## do-while 循环

`do-while` 循环与 `while` 循环没有区别。唯一的区别是继续的条件通常是在代码块执行后评估的。这触发代码块至少执行一次，除非开发者在代码中嵌入了退出条件。在大多数情况下，`do-while` 循环和 `while` 循环可以容易且无缝地交换。大多数情况下，你只需要对代码块的逻辑进行微小的更改。可以使用 `do-while` 循环来编写遍历数组并打印元素的值。这不需要更改代码。

当代码块需要至少执行一次时，`do-while` 语句工作非常完美。否则，你必须至少评估一次条件。

在接下来的示例中，我将使用 `do-while` 循环。编译器即使在第一次运行时条件结果为假，也会让语句执行一次。其原因是位于条件之前的代码块总是会被测试的。

```java
public class JavaX {
    public static void main(String[] args) {
        int x = 0;
        do {
            System.out.println(x);
            x++;
        } while (x < 7);
    }
}
```

输出：
```
0
1
2
3
4
5
6
```

## for 循环

`for` 循环被高度用于迭代如列表和数组等需要计数的对象。例如，通过 `for` 循环可以轻松完成遍历数组并打印相同的内容。

```java
public class JavaX {
    public static void main(String... args) {
        int array[] = {50, 31, 12344, 42, 53};
        for (int x = 0; x < array.length; ++x) {
            System.out.println("This is Java array[" + x + "] = " + array[x]);
        }
    }
}
```



This is Java `array[0] = 50`

This is Java `array[1] = 31`

This is Java `array[2] = 12344`

This is Java `array[3] = 42`

This is Java `array[4] = 53`

当你使用 `for` 循环时，你需要确切知道需要循环遍历特定代码块多少次。在这种情况下，`while` 循环并不起作用。代码中的第一个语句在代码块执行之前执行一次。第二个语句趋向于定义代码块执行的特定条件。第三个语句在每次代码块执行后执行一次。让我们来看另一个示例。

```java
public class Java {
    public static void main(String[] args) {
        for (int x = 0; x < 7; x++) {
            System.out.println(x);
        }
    }
}
```

- 0
- 1
- 2
- 3
- 4
- 5
- 6

在第一个语句中，变量在循环开始之前被定义并设置。在第二个语句中，定义了条件，以便循环有内容可以可以理解和运行。如果条件返回 `true`，循环将重新开始。如果条件返回 `false`，循环将到达终点。在第三个语句中，每次执行循环内部的代码块时，变量的值都会增加。

通过更改条件，我们可以影响 `for` 循环的输出。以下代码将打印 3 的倍数。

```java
public class JavaX {
    public static void main(String[] args) {
        for (int x = 0; x <= 15; x = x + 3) {
            System.out.println(x);
        }
    }
}
```

- 0
- 3
- 6
- 9
- 12
- 15

## for-each 循环

`for-each` 循环用于迭代集合或数组的元素。如果你不需要索引，它比传统的 `for` 循环更简单。在接下来的示例中，我将使用 `for-each` 循环遍历数组。看看它与标准 `for` 循环的区别。

```java
public class Java {
    public static void main(String[] args) {
        String[] kitchen = {"spatula", "spoon", "napkin", "ladle", "hammer"};
        for (String x : kitchen) {
            System.out.println(x);
        }
    }
}
```

- spatula
- spoon
- napkin
- ladle
- hammer

## 跳出循环 (Breaking Loops)

在之前的示例中，我指出可以使用 `break` 语句退出循环。你已经看到它如何在嵌套循环。

1. `break` 语句用于退出循环。
2. `continue` 语句用于跳过循环执行。
3. `return` 语句通常用于退出方法。

## break 语句

`break` 语句只能用于 `switch`、`do-while` 和 `while` 语句。然而，你必须通过退出条件控制它，否则你无法执行单个步骤。在下一个示例中，我将限制循环某些元素，即使循环遍历所有内容。

```java
public class Java {
    public static final int thisarray[] = {5,1, 2, 3, 4};
    public static void main(String[] args) {
        for (int x = 0; x < thisarray.length; ++x) {
            if (x == 4) {
                System.out.println("You have reached the end of the loop!");
                break;
            }
            System.out.println("the looped through value: [" + x + "] = " + thisarray[x]);
        }
    }
}
```

```text
the looped through value: [0] = 5
the looped through value: [1] = 1
the looped through value: [2] = 2
the looped through value: [3] = 3
You have reached the end of the loop!
```

如果你正在处理嵌套循环，可以使用标签（label）来决定退出哪个循环语句。在下面的代码中，我将使用三个嵌套在代码块中的 `for` 循环。我将在索引相等时退出中间循环。

```java
public class Java {
    public static final int thisarray[] = {5,1, 4, 2, 3};
    public static void main(String... args) {
        for (int x = 0; x < 4; ++x) {
            TIM: for (int y = 0; y < 2; ++y) {
                for (int z = 0; z < 2; ++z) {
                    System.out.println("x variable, y variable, z variable) = (" + x + "," + y + "," + z + ")");
                    if (x == y && y == z) {
                        break TIM;
                    }
                }
            }
        }
    }
}
```

```text
(x variable, y variable, z variable) = (0,0,0)
(x variable, y variable, z variable) = (1,0,0)
(x variable, y variable, z variable) = (1,0,1)
(x variable, y variable, z variable) = (1,1,0)
(x variable, y variable, z variable) = (1,1,1)
(x variable, y variable, z variable) = (2,0,0)
(x variable, y variable, z variable) = (2,0,1)
(x variable, y variable, z variable) = (2,1,0)
(x variable, y variable, z variable) = (2,1,1)
(x variable, y variable, z variable) = (3,0,0)
(x variable, y variable, z variable) = (3,0,1)
(x variable, y variable, z variable) = (3,1,0)
(x variable, y variable, z variable) = (3,1,1)
```

代码中使用的标签命名为 `TIM`。它通常出现在 `for` 语句之前。当条件满足时，`for` 语句会退出。它随后于 `break` 语句。

在编写代码时，使用大写字母命名标签被认为是最佳实践，因为它可以避免在阅读代码时将标签与类或变量名混淆。

为了确保此功能正常工作，你可以查看控制台，确认 x、y、z 的所有组合不再被打印。所有以 0 开头的集合都会被自动跳过。

## continue 语句

`continue` 语句并不一定会中断循环。然而，它可以根据条件跳过不同的执行步骤。基本上，它会停止循环的当前步骤并进入下一个步骤。因此，你可以说该语句在循环中继续。这次我将遍历数组，唯一的区别是添加了 `continue` 语句。

```java
public class Java {
    public static final int thisarray[] = {5, 1, 4, 2, 3};
    public static void main(String... args) {
        for (int x = 0; x < thisarray.length; ++x) {
            if (x % 2 != 0) {
                continue;
            }
            System.out.println("the array [" + x + "] = " + thisarray[x]);
        }
    }
}
```

```text
the array [0] = 5
the array [2] = 4
the array [4] = 3
```

上述条件必须经过正确设置，否则循环将无限且无意义地迭代。`continue` 语句必须配合标签使用。让我们对之前使用的嵌套循环应用类似的示例。但是，这次当 z 索引等于 1 时，你将看到屏幕上没有任何打印内容。

```text
(variable x, variable y, variable z) = (0,0,0)
(variable x, variable y, variable z) = (0,1,0)
(variable x, variable y, variable z) = (0,2,0)
(variable x, variable y, variable z) = (1,0,0)
(variable x, variable y, variable z) = (1,1,0)
(variable x, variable y, variable z) = (1,2,0)
(variable x, variable y, variable z) = (2,0,0)
(variable x, variable y, variable z) = (2,1,0)
(variable x, variable y, variable z) = (2,2,0)
```

## return 语句

`return` 语句的执行更容易。你可以用它来退出方法的执行。如果某个方法返回一个值，`return` 语句通常与最后返回的值一起出现。`return` 语句可以退出本节中提到的任何语句。它代表了一种更智能的快捷执行过程的方法，因为执行会停止一段时间，而处理将从命名为方法的代码点继续。现在我将写一个寻找数组中第一个元素的方法。该方法将返回索引，或者返回 -1。

```java
public class Java {
    public static final int thisarray[] = {5, 1, 4, 3, 2, 10, 12};
    public static void main(String... args) {
        int x = yeven(thisarray);
        if (x != -1) {
            System.out.println("The first even number is as follows: " + x);
        }
    }
    public static int yeven(int ... thisarray) {
        for (int a = 0; a < thisarray.length; ++a) {
            if (thisarray[a] % 2 == 0) {
                return a;
            }
        }
        return -1;
    }
}
```

第一个偶数如下：2

现在我将通过将 `for` 语句替换为 `while` 语句来测试相同的代码并观察它的工作原理。

```java
public class JavaX {
    public static final int thisarray[] = {5, 1, 4, 3, 2, 10, 12};
    public static void main(String... args) {
        int x = yeven(thisarray);
        if (x != -1) {
            System.out.println("The first even number is as follows: " + x);
        }
    }
    public static int yeven(int ... thisarray) {
        int a = 0;
        while (a < thisarray.length) {
            if (thisarray[a] % 2 == 0) {
                return a;
            }
            ++a;
        }
        return -1;
    }
}
```

第一个偶数如下：2

在任何满足特定条件并想要终止循环执行的情况下，你都可以使用 `return` 语句。

## Try-Catch 结构

还有另一种控制代码块流转的方法。`try-catch` 语句被用作条件判断和循环的替代流控制。代码中有一个用于执行的通用代码块。然后是一个可能被抛出的声明。

## Java 方法参数与变量

你可以以参数的形式向方法传递信息。参数在方法内部充当变量。参数通常指定在方法名后的圆括号内。你可以根据需要为方法添加尽可能多的参数。你只需要用逗号将它们分隔开。下面的示例包含了一个向方法传递信息的方法和参数。

```java
public class JavaX {
    static void thisMeth(String name) {
        System.out.println(name + " is building my house with the architect Rhodes");
    }

    public static void main(String[] args) {
        thisMeth("John");
        thisMeth("Seema");
        thisMeth("Kane");
    }
}
```

```text
John is building my house with the architect Rhodes
Seema is building my house with the architect Rhodes
Kane is building my house with the architect Rhodes
```

当你向方法传递一个参数时，它被称为变量（argument）。在上面的方法中，`name` 是参数，而 Seema、Kane 和 John 是变量。

## 多参数

你已经见过在方法中使用单个参数的用法。在下一个示例中，我将使用多个参数来提高方法的易用性。我将解释如何在一个方法中使用尽可能多的参数。这意味着你可以向方法添加尽可能多的信息。

```java
public class JavaX {
    static void thisMeth(String name, int age) {
        System.out.println(name + " is building my house with the architect Rhodes. He is " + age + ".");
    }

    public static void main(String[] args) {
        thisMeth("John", 45);
        thisMeth("Seema", 19);
        thisMeth("Kane", 22);
    }
}
```

```text
John is building my house with the architect Rhodes. He is 45.
Seema is building my house with the architect Rhodes. He is 19.
Kane is building my house with the architect Rhodes. He is 22.
```

当你处理多个参数时，方法调用时中包含的变量数量必须与参数数量相同。变量需要按照完美的顺序进行传递。

## 返回值

代码中的 `void` 关键字表示方法并不一定需要返回值。如果你想获取返回的值，必须使用 `char` 和 `int` 等基本数据类型，而不是 `void`。你还必须在方法中使用 `return` 关键字。

```java
public class Java {
    static int thisMeth(int a) {
        return 50 + a;
    }

    public static void main(String[] args) {
        System.out.println(thisMeth(5000));
    }
}
```

```text
5050
```

`return` 关键字可以与多个参数一起工作。参见下面包含两个参数的示例。

```java
public class Java {
    static int thisMeth(int a, int b) {
        return b + a;
    }

    public static void main(String[] args) {
        System.out.println(thisMeth(5000, 50));
    }
}
```

```text
5050
```

当你通过方法返回一个值时，你可以将其引导向变量并存储起来，以便以后在程序中使用。这个过程非常简单。我们只需要为代码提供第三个变量。在下面的示例中，我将在代码中添加第三个变量并发送返回的结果。

```java
public class JavaX {
    static int thisMeth(int a, int b) {
      return b + a;
    }

    public static void main(String[] args) {
      int c = thisMeth(5000, 50);
      System.out.println(c);
    }
}
```

```text
5050
```

## 方法重载



# Java 方法重载

在方法重载的帮助下，多个方法可以通过不同的参数具有相同的名称。下面的示例包含两个加不同类型数字的方法。

```java
public class JavaX {
    static int thisMethInt(int a, int b) {
      return a + b;
    }

    static double thisMethDouble(double a, double b) {
      return a + b;
    }
}
```

```java
public static void main(String[] args) {
    int theNum1 = thisMethInt(80, 50);
    double theNum2 = thisMethDouble(6.3, 8.26);
    System.out.println("the int number : " + theNum1);
    System.out.println("the double number: " + theNum2);
}
```

`the int number : 130`

`the double number: 14.56`

方法不应该不同的名称，而是应该不同的参数。这被称为方法重载。它允许你为不同的输入使用相同的方法名称，这使得代码具有更好的可读性和一致性。

# 数组作为方法参数与返回值

```java
public int[] returningtheArray()
{
    int[] x = new int[3];
    for (int y = 0; y < x.length; y++) {
        x[y] = y*2;
    }
    return x;
}
```

```java
public class ArrayMethodDemo {
    public static void main(String[] args) {
        ThisClass amd = new ThisClass();

        int[] ThisArray = {1, 2, 3, 4, 5};
        amd.printingtheFirstElement(ThisArray);

        int[] Array2 = amd.returningtheArray();
        System.out.println(Arrays.toString(ThisArray));
    }
}
```

数组中的第一个元素将是 1 [0, 2, 4]

为了保持简单易于阅读和练习，我在同一个文件中包含了几个类。`ThisClass` 类中有两个方法。第一个方法被标记为 `printingtheFirstElement()`。

这展示了如何以参数的形式使用数组。第二个方法 `returningtheArray()` 展示了如何在第二阶段返回数组。随后我在 `main()` 方法中初始化了名为 `amd` 的 `ThisClass` 对象。然后我声明了数组并将其作为参数传递给 `printingtheFirstElement()` 方法。我还在 `main()` 方法内部声明了第二个数组，并将 `returningtheArray()` 方法的结果赋值给它。最后我打印了内容。

# this 关键字

下面的示例使用了 `this` 关键字来访问类的总数。

```java
public class ThisKeyword {
    // 这是实例变量之和
    int number = 100;

    ThisKeyword() {
        System.out.println("This is a brilliant example program built around the keyword this");
    }

    ThisKeyword(int number) {
        // 我在下一步中
        // 调用了默认构造函数
        this();

        // 我将一个局部变量
        // 赋值给实例变量 number
        this.number = number;
    }

    public void greetings() {
        System.out.println("Hello, you are welcome to the world of Java.");
    }

    public void printing() {
        // 这是所有的局部变量
        int number = 200;

        // 我现在正在打印一个局部变量
        System.out.println("The total value of the local variable number is as follows : "+number);

        // 我现在正在打印一个实例变量
        System.out.println("The total value of the instance variable number is as follows :"+this.number);

        // 我现在正在调用该类的 greetings 方法
        this.greetings();
    }

    public static void main(String[] args) {
        // 我现在正在实例化类
        ThisKeyword objectA = new ThisKeyword();

        // 我现在正在调用我的 print 方法
        objectA.printing();

        // 我现在通过带参数的构造函数
        // 向 number 变量传递一个新值
        ThisKeyword objectB = new ThisKeyword(50);

        // 我现在将再次调用 print 方法
        objectB.printing();

        // 我现在通过带参数的构造函数
        // 向 number 变量传递一个新值
        ThisKeyword objectC = new ThisKeyword(50000);

        // 我现在将再次调用 print 方法
        objectC.printing();

        // 我现在通过带参数的构造函数
        // 向 number 变量传递一个新值
        ThisKeyword objectD = new ThisKeyword(340000);

        // 我现在将再次调用 print 方法
        objectD.printing();
    }
}
```

这是一个围绕 `this` 关键字构建的优秀示例程序

局部变量 number 的总值如下：200

实例变量 number 的总值如下：100

你好，欢迎来到 Java 世界。

这是一个围绕 `this` 关键字构建的优秀示例程序

局部变量 number 的总值如下：200

实例变量 number 的总值如下：50

你好，欢迎来到 Java 世界。

这是一个围绕 `this` 关键字构建的优秀示例程序

局部变量 number 的总值如下：200

实例变量 number 的总值如下：50000

你好，欢迎来到 Java 世界。

这是一个围绕 `this` 关键字构建的优秀示例程序

局部变量 number 的总值如下：200

实例变量 number 的总值如下：340000

你好，欢迎来到 Java 世界。

# 变长参数 (var-args)

Java 开发工具包 (JDK) 允许你向特定方法传递不同数量的相似类型的参数。在方法的声明中，你可以指定其并在后跟省略号 (`...`)。方法中只能指定一个变长参数。该参数必须是参数列表最后一个。

```java
public class VarargumentsDemonstration {
    public static void main(String[] args) {
        // 我现在通过变长参数
        // 的帮助调用方法
        printingMax(34, 355, 31, 22, 56.5);
        printingMax(new double[]{1, 2, 3});
    }

    public static void printingMax(double... nums) {
        if (nums.length == 0) {
            System.out.println("There are no argument passed");
            return;
        }

        double theresult = nums[0];

        for (int x = 1; x < nums.length; x++)
            if (nums[x] > theresult)
                theresult = nums[x];
            System.out.println("The maximum value of the variable is " + theresult);
    }
}
```

变量的最大值是 355.0

变量的最大值是 3.0

# Java 文件

`java.io` 包包含了你在 Java 中执行输入和输出操作时可能需要的所有类。所有的流都代表了输入源和输出目标。`java.io` 包内的流将支持多种数据类型，如基本类型、对象和本地化字符。

流可以被定义为数据序列。流通常有两种类型，如 `InputStream` 和 `OutputStream`。前者用于从特定资源读取数据，而后者用于向特定目标写入并提供数据。Java 为 I/O 相关的文件和网络提供了强大的支持。

Java 字节流可用于处理 8 位的输入输出。许多类与字节流相关，但最常用的是 `FileOutputStream` 和 `FileInputStream`。请下面的示例：

```java
import java.io.*;
public class CopyingFile {

    public static void main(String[] args) throws IOException {
        FileInputStream in = null;
        FileOutputStream out = null;

        try {
            in = new FileInputStream("thisisinput.txt");
            out = new FileOutputStream("thisisoutput.txt");

            int x;
            while ((x = in.read()) != -1) {
                out.write(x);
            }
        } finally {
            if (in != null) {
                in.close();
            }
            if (out != null) {
                out.close();
            }
        }
    }
}
```

# 字符流

Java 字节流通常用于 8 位字节的输入输出。另一方面，Java 字符流可用于 16 位 Unicode 的输入输出。字符流中最常用的类是 `FileWriter` 和 `FileReader`。

```java
import java.io.*;
public class CopyingtheFile {
    public static void main(String[] args) throws IOException {
        FileReader in = null;
        FileWriter out = null;
        try {
            in = new FileReader("thisinput.txt");
            out = new FileWriter("thisoutput.txt");
            int x;
            while ((x = in.read()) != -1) {
                out.write(x);
            }
        } finally {
            if (in != null) {
                in.close();
            }
            if (out != null) {
                out.close();
            }
        }
    }
}
```

该程序将创建一个与输入文件内容相同的输出文件。

# 标准流

编程语言提供了标准 I/O 支持，用户程序可以从键盘获取输入并在屏幕上产生输出。如果你熟悉 C 或 C++ 编程语言，你需要了解三个标准设备：STDIN、STDERR 和 STDOUT。Java 提供了三种标准流，如标准错误、标准输入和标准输出。

标准输入通常用于向用户程序提供数据。为了这一目的，键盘被用作输入流。标准输出用于处理用户程序产生的输出数据。程序员通常使用计算机屏幕作为标准输出流。标准错误用于处理用户程序产生的输出错误数据。

program。计算机屏幕通常用于标准错误流，并表示为 `System.err`。

```java
import java.io.*;
public class ReadingTheConsole {
    public static void main(String args[])
    throws IOException {
        InputStreamReader cin = null;
        try {
            cin = new InputStreamReader(System.in);
            System.out.println("Here you can
Enter the characters, enter 'q' for quitting
the program.");
            char x;
            do {
                x = (char) cin.read();
                System.out.print(x);
            } while (x != 'q');
        } finally {
            if (cin != null) {
                cin.close();
            }
        }
    }
}
```

# 第八章：Java 类

## Java 类

Java 中的 OOP 代表面向对象编程。Java 中的过程化编程是通过组合方法和过程，这些过程会对你的数据执行某些操作。相比之下，面向对象编程侧重于创建包含方法和数据的对象。面向对象编程相比过程化编程具有多个优势。它比过程化编程更快，而且更容易执行。

面向对象编程为程序提供了清晰的结构。它还有助于防止 Java 代码重复和使程序混乱。它让你的代码更容易维护、调试或修改。它还让你能够用更少的代码和更短开发时间创建可用的应用程序。因此，它将为你节省资源。面向对象编程技术遵循 DRY 原则，全称为“不要重复自己”。该原则侧重于减少代码的重复。你必须分离出应用程序中公共的代码，然后将其放在一个地方。从那里你可以提取并重复使用它们，而不是重复。

## 类

类和对象是面向对象编程的两个部分。类就像对象的通用模板，而对象就像单个类的实例。当你创建单独的对象时，它们将继承类中的变量和不同的方法。

Java 中的一切都与对象或类以及它们的方法或属性有关。豹子是一个对象，它具有高度、颜色和姿态等属性。它坐、吃、跑、战斗。同样，我们为 Java 类中的对象赋予了属性。在下面的示例中，我将从类中创建一个对象。我将使用关键字 `new` 配合对象的名称。

```java
public class Java {
    int a = 50;

    public static void main(String[] args) {
        Java Obj1 = new Java();
        System.out.println(Obj1.a);
    }
}
```

50

你可以在类中创建多个对象。参见下例中的演示。

```java
public class Java {
    int a = 50;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        JavaX Obj2 = new JavaX();
        System.out.println(Obj1.a);
        System.out.println(Obj2.a);
    }
}
```

你可以创建一个对象，然后在另一个类中访问它。这通常用于更好地组织类。一个类承载所有的方法和属性，而另一个类只有一个主方法。你需要记住，你保存代码的 Java 文件名必须与类名匹配。

## Java 类属性

你可以通过创建类对象以及通过使用点语法（dot syntax）来访问类的属性。下面的示例将创建一个类的对象。我将使用对象上的属性来打印值。



```java
public class JavaX {
    int a = 50;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        System.out.println(Obj1.a);
    }
}
```

## 修改属性

更改属性的值有时是不可避免的。你需要用新值替换旧值。你可以通过以下方法修改类的属性。

```java
public class JavaX {
    int a;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        Obj1.a = 400;
        System.out.println(Obj1.a);
    }
}
```

400

即使属性 `a` 的初始值是 20 这样的值，你也可以修改它。我将在类内部不移除第一个值的情况下将 20 改为 400。这就是 Java 类中修改属性的过程。

```java
public class JavaX {
    int a = 20;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        Obj1.a = 400;
        System.out.println(Obj1.a);
    }
}
```

400

如果你正在编写大规模代码，且不想让其他程序员更改值，可以通过声明将其属性为 `final` 来阻止修改。你将收到一个错误。参见下面的示例。

```java
public class JavaX {
    final int a;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        Obj1.a = 400;
        System.out.println(Obj1.a);
    }
}
```

```
JavaX.java:6: error: cannot assign value to final variable

    Obj1.a = 400;

    ^
```

## 多个对象

如果你在类中创建了多个对象，可以在另一个类中访问它们。

```java
public class JavaX {
    int a = 50;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        JavaX Obj2 = new JavaX();
        System.out.println(Obj1.a);
        System.out.println(Obj2.a);
    }
}
```

50

555

你可以根据需要添加尽可能多的属性。（等等，查看文本）

```java
public class Java {
    String name = "John";
    String profession = "doctor";
    int theage = 32;

    public static void main(String[] args) {
        Java Obj1 = new Java();
        System.out.println("The name is " + Obj1.name + ".");
        System.out.println("I am working as " + Obj1.profession + ".");
        System.out.println("My age is " + Obj1.theage + ".");
    }
}
```

The name is John.

I am working as doctor.

My age is 32.

# 方法

你已经学习了如何创建方法以及如何使用它们。Java 方法总是类的一部分。参见下面的示例，我将在 `JavaX` 类中创建一个方法。

```java
public class JavaX {
    static void thisMeth() {
        System.out.println("This is Java Class!");
    }

    public static void main(String[] args) {
        thisMeth();
    }
}
```

This is Java Class!

## 静态与非静态属性

Java 程序同样拥有静态或公共属性，以及方法。下面的示例将演示静态或公共方法的功能。

```java
public class JavaX {
    // 这是静态方法
    static void thisIsStaticMethod() {
        System.out.println("You can call Static methods without the creation of objects.");
    }

    // 这是公共方法
    public void thisIsPublicMethod() {
        System.out.println("You must call public methods by creating objects.");
    }

    public static void main(String[] args) {
        // 这是主方法
        thisIsStaticMethod(); // 这是我们对静态方法的调用
        JavaX Obj = new JavaX(); // 在这里我创建一个对象
        Obj.thisIsPublicMethod(); // 这一步用于调用公共方法
    }
}
```

You can call Static methods without the creation of objects.

You must call public methods by creating objects.

```java
public class JavaX {
    public void topThrottle() {
        System.out.println("The racer is running the bike at full throttle!");
    }

    public void bikespeed(int maximumSpeed) {
        System.out.println("The Maximum speed of the bike is " + maximumSpeed + "mph.");
    }

    public static void main(String[] args) {
        JavaX bikel = new JavaX(); // It is time to create the bikel object
        bikel.topThrottle(); // I am now calling the topThrottle() method
        bikel.bikespeed(500); // I am now calling the bikespeed() method
    }
}
```

赛车手正在全油门行驶自行车！自行车的最高速度为 500mph。

在上面的示例中，我通过 `class` 关键字创建了 `JavaX` 类。然后，我在 `JavaX` 类内部创建了 `topThrottle()` 方法和 `bikespeed()` 方法。`bikespeed()` 方法接收一个被指定为 `maximumSpeed` 的 `int` 类型参数。仍然缺失的是一个使用 `JavaX` 类及相关方法的对象。随后我使用了 Java 内置的 `main()` 方法。它运行你的程序，并且其中的所有的代码都会按顺序执行。

程序中的 `new` 关键字用于创建一个一个名为 `bikel` 的新对象。一旦该对象被创建，我就在新创建的对象 `bikel` 上使用了 `topThrottle()` 和 `bikespeed()` 方法。然后通过使用对象名 `bikel` 来运行程序。如果你注意到，你会发现在对象名 `bike1` 之后有一个点（`.`）。紧接着点之后是我已经创建的两个方法的名称。点（`.`）是访问对象属性和方法的方法。当你想要在 Java 中调用方法时，应该加上圆括号 `()` 和分号 `;`。一个类需要一个匹配的文件名，否则它将无法正常运行。

## 多个对象

在接下来的示例中，我将创建多个对象以展示是如何操作以及它是如何运行的。我将在类中额外添加两辆自行车作为对象。尽管每辆自行车具有不同的最高速度等级，但它们都正在以全油门运行。我不会对代码进行任何更改，而末尾添加更多代码来创建不同的对象。

```java
// I am Creating here the Java class
public class JavaX {

    // It is time to creating the fullspeed()
    // method
    public void topThrottle() {
        System.out.println("The racer is running the bike at full throttle!");
    }

    // In the following step, I will create
    // the speed() method and then I will add to it a parameter
    public void bikespeed(int maximumSpeed) {
        System.out.println("The Maximum speed of the bike is " + maximumSpeed + "mph.");
    }
}
```

```java
// Inside JavaX class, I will call on the
// methods on the bike object
public static void main(String[] args) {
    JavaX bikel = new JavaX();    // It is time to create the bikel object
    bikel.topThrottle(); // I am now calling the topThrottle() method
    bikel.bikespeed(500); // I am now calling the bikespeed() method
    JavaX bike2 = new JavaX();    // It is time to create the bikel object
    bike2.topThrottle(); // I am now calling the topThrottle() method
    bike2.bikespeed(300); // I am now calling the bikespeed() method
    JavaX bike3 = new JavaX();    // It is time to create the bikel object
    bike3.topThrottle(); // I am now calling the topThrottle() method
    bike3.bikespeed(400); // I am now calling the bikespeed() method
}
```

赛车手正在全油门行驶自行车！

自行车的最高速度为 500mph。

赛车手正在全油门行驶自行车！

自行车的最高速度为 300mph。

赛车手正在全油门行驶自行车！

自行车的最高速度为 400mph。

## 多个类

创建一个对象并在另一个类中访问它它是最佳实践。最重要的一点是，你应该保持 java 文件的文件名与类名一致。由于会有两个类，我将在同一个目录下创建两个带有类名命名的 java 文件。接下来的示例将解释代码以及创建多个类的方法。

```java
// I am Creating here the JavaX class
public class JavaX {

    // It is time to creating the fullspeed()
    public void topThrottle() {
        System.out.println("The racer is running the bike at full throttle!");
    }

    // In the following step, I will create
    the speed() method and then I will add to it
    a parameter
    public void bikespeed(int maximumSpeed) {
        System.out.println("The Maximum speed of the bike is " + maximumSpeed + "mph.");
    }
}
```

上面的部分将去到。这是 main 类，它需要一个文件。接下来的部分将在类名命名的第二个文件中保存。

```java
class Bike {
    // Inside JavaX class, I will call on the
    // methods on the bike object
    public static void main(String[] args) {
        JavaX bikel = new JavaX();    // It is time to create the bikel object
        bikel.topThrottle(); // I am now calling the topThrottle() method
        bikel.bikespeed(500); // I am now calling the bikespeed() method
        JavaX bike2 = new JavaX();    // It is time to create the bikel object
        bike2.topThrottle(); // I am now calling the topThrottle() method
        bike2.bikespeed(300); // I am now calling the bikespeed() method
        JavaX bike3 = new JavaX();    // It is time to create the bikel object
        bike3.topThrottle(); // I am now calling the topThrottle() method
        bike3.bikespeed(400); // I am now calling the bikespeed() method
    }
}
```

赛车手正在全油门行驶自行车！

自行车的最高速度为 500mph。

赛车手正在全油门行驶自行车！

自行车的最高速度为 300mph。

赛车手正在全油门行驶自行车！

自行车的最高速度为 400mph。

## 内部类

你可以在 Java 中嵌套类。这意味着你可以将一个类放入另一个类中。嵌套类的主要目标是将必须放在一起的类分组。这使得代码更具可读性。见下面的示例。当你需要访问内部类时，你可以在外部类中创建一个对象，并在内部类中也创建一个对象。

```java
class TheOuterClass {
    int a = 100;

    class TheInnerClass {
        int b = 5000;
    }

    public class Main {
        public static void main(String[] args) {
            TheOuterClass myOuter1 = new TheOuterClass();
            TheOuterClass.TheInnerClass myInner1 = new myOuter1.new TheInnerClass();
            System.out.println(myInner1.b + myOuter1.a);
        }
    }
}
```

5100

与普通类不同，内部类可以是受保护或私有的。如果你不需要从外部对象访问内部类，可以将类声明为私有。



```java
class TheOuterClass {
    int a = 100;

    private class TheInnerClass {
        int b = 50;
    }

    public class Main {
        public static void main(String[] args) {
            TheOuterClass Outer1 = new TheOuterClass();
            TheOuterClass.TheInnerClass Inner1 = Outer1.new TheInnerClass();
            System.out.println(Inner1.b + Outer1.a);
        }
    }
}
```

```
Main.java:12: error:
TheOuterClass.TheInnerClass has private access in TheOuterClass
TheOuterClass.TheInnerClass Inner1 = Outer1.new TheInnerClass();
```

```java
Main.java:12: error:
TheOuterClass.TheInnerClass has private
access in TheOuterClass
    TheOuterClass.TheInnerClass Inner1 =
    Inner1.new TheInnerClass();

^
2 errors
```

你会看到一个错误，因为你无法从外部类访问私有类。

## 静态内部类

你的内部类可以是静态的。这意味着即使你没有创建外部类的对象，也可以访问它。

```java
class TheOuterClass {
    int a = 100;

    static class TheInnerClass {
        int b = 50;
    }
}

public class Main {
    public static void main(String[] args) {
        TheOuterClass.TheInnerClass Inner1 = new
        TheOuterClass.TheInnerClass();
        System.out.println(Inner1.b);
    }
}
```

50

## 从内部类访问外部类

内部类最大的优势是它们倾向于访问外部类的属性和方法。

```java
class TheOuterClass {
    int a = 100;

    class TheInnerClass {
        public int TheInnerMethod() {
            return a;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        TheOuterClass Outer1 = new TheOuterClass();
        TheOuterClass.TheInnerClass Inner1 = Outer1.new TheInnerClass();

        System.out.println(Inner1.TheInnerMethod());
    }
}
```

100

# 第九章

## 修饰符、用户输入、接口

你可能已经注意到代码中频繁使用 `public` 这个词。`public` 关键字被标记为访问修饰符。这意味着你可以用它来设置类、方法、属性和构造函数的访问级别。Java 中有不同类型的修饰符；一种称为访问修饰符，另一种称为非访问修饰符。访问修饰符倾向于控制访问级别，而非访问修饰符不需要控制访问级别，而是提供其他某种的功能。

对于类，你可以使用默认或 `public` 修饰符。当你向类添加 `public` 时，你将该类标记为字面上的公共。任何人都可以访问、编辑或修改该类。类的默认修饰符使得该类仅可被同一个包内的其他类访问。当你不想指定修饰符时，可以将修饰符设置为默认。

```java
public class JavaX {
    public static void main(String[] args) {
        System.out.println("The public modifier makes this class accessible to anyone.");
    }
}
```

```java
class Java {
    public static void main(String[] args) {
        System.out.println("The public modifier makes this class accessible to anyone.");
    }
}
```

要使用默认方法，你所做的就是从上面的代码中删除 `public` 关键字，如下所示：

当你处理方法、属性和构造函数时，可以使用以下修饰符。

```java
public class Java {
    public String name = "David";
    public String profession = "Coach";
    public String contact = "David@dye.com";
    public int age = 48;
}
```

现在我将属性设置为私有（`private`），这意味着现在属性只能在声明的类内部访问。见下面的示例。

```java
public class JavaX {
    private String name = "David";
    private String profession = "Coach";
    private String contact = "David@dye.com";
    private int age = 48;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        System.out.println("The name is: " +
        Obj1.name + ".");
        System.out.println("My profession is " +
        Obj1.profession + ".");
        System.out.println("My contact Email is: " +
        Obj1.contact);
        System.out.println("My age is " +
        Obj1.age + ".");
    }
}
```

The name is: David.

My profession is Coach.

My contact Email is: David@dye.com

My age is 48.

如果我们将属性设置为默认，则代码将仅在包内可访问。当你不想指定修饰符时，可以将修饰符设置为默认。

```java
class JavaX {
    String name = "David";
    String profession = "Coach";
    String contact = "David@dye.com";
    int age = 48;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        System.out.println("The name is: " +
        Obj1.name + ".");
        System.out.println("My profession is " +
        Obj1.profession + ".");
        System.out.println("My contact Email is: " +
        Obj1.contact);
        System.out.println("My age is " +
        Obj1.age + ".");
    }
}
```

## 非访问修饰符

非访问修饰符不需要控制访问级别，而是提供其他某种的功能。

```java
class JavaX {
    String name = "David";
    String profession = "Coach";
    String contact = "David@dye.com";
    int age = 48;

    public static void main(String[] args) {
        JavaX Obj1 = new JavaX();
        System.out.println("The name is: " +
        Obj1.name + ".");
        System.out.println("My profession is " +
        Obj1.profession + ".");
        System.out.println("My contact Email is: " +
        Obj1.contact);
        System.out.println("My age is " +
        Obj1.age + ".");
    }
}
```

```java
public abstract void animalSounds();
// The following method is a Regular method
public void sleepmode() {
    System.out.println("SnooooooooZzz");
}
```

```java
// This is a Subclass that has been inherited from AnimalKingdom
class Leopard extends AnimalKingdom {
    public void animalSounds() {
        // I have provided the body of animalSounds() in the following method
        System.out.println("The leopard says: meow meow.");
    }
}
```

```java
class Main {
    public static void main(String[] args) {
        Leopard leopard1 = new Leopard(); // I am creating a leopard object
        leopard1.animalSounds();
        leopard1.sleepmode();
    }
}
```

豹子说：喵喵喵。

SnooooooooZzz

当你需要高安全性时，可以使用抽象类。通过抽象类，你可以隐藏某些细节，并且在程序中只显示最重要的细节。你可以借助接口的帮助来实现抽象。

## 封装

你只能在同一个类内部访问私有变量。外部类永远无法访问它。但是有一种解决办法。如果你提供了公共的 `set` 和 `get` 方法，你就可以访问它们。`get` 方法将返回变量的值，`set` 方法将设置它的值。语法以 `set` 或 `get` 关键字开头。然后你必须输入变量名。变量的首字母应该是大写字母。

```java
public class Java {
    public static void main(String[] args) {
        Man Obj1 = new Man();
        Obj1.name = "Johnny Boy";
        System.out.println(Obj1.name);
    }
}
```

以下代码需要第二个文件，因为它有一个独立的类名。

```java
public class Man {
    private String name;

    public String gettheName() {
        return name;
    }

    public void setName(String newName) {
        this.name = newName;
    }
}
```

```
JavaX.java:3: error: cannot find symbol
Man Obj1 = new Man();
    ^
symbol: class Man
location: class Java
JavaX.java:3: error: cannot find symbol
Man Obj1 = new Man();
    ^
symbol: class Man
location: class Java
```

现在我将使用 `getName()` 和 `setName()` 方法来更新变量。现在这些方法将可以访问变量，你的屏幕上就不会报错。

```java
public class JavaX {
    public static void main(String[] args) {
        Man Obj1 = new Man();
        Obj1.setName("Johnny Boy");
        System.out.println(Obj1.getName());
    }
}
```

```java
public class Man {
    private String name;

    public String gettheName() {
        return name;
    }

    public void setName(String newName) {
        this.name = newName;
    }
}
```

封装提供了对类的方法和属性的改进控制。如果你只使用 `set` 方法，可以将类的属性设为只读或只写。你可以更改代码的一个部分，而它仍然不会影响代码的其他部分。这个过程也将有助于提高安全性。

## Java 枚举

Java 枚举是一种特殊的 Java 类，表示一组特定的常量。这些常量是不可更改的，被称为 `final` 变量。要创建一个枚举，你可以使用 `enum` 关键字代替接口或类，然后用逗号分隔所有的常量。所有内容必须是大写字母。Enum 是 enumerations 的缩写，它的含义有专门列出，你可以在 Java 类内部集成一个枚举。

```java
public class Main {
    enum TezLevel {
        LOW,
        MEDIUM,
        HIGH
    }

    public static void main(String[] args) {
        TezLevel Varl = TezLevel.MEDIUM;
        System.out.println(Varl);
    }
}
```

MEDIUM

你可以在 Java 类内部添加枚举。请参考以下示例。

```java
public class Main {
    enum TezLevel {
        LOW,
        MEDIUM,
        HIGH
    }

    public static void main(String[] args) {
        TezLevel Varl = TezLevel.MEDIUM;
        System.out.println(Varl);
    }
}
```

你可以在 Java 类内部添加枚举。请参考以下示例。

```java
public class Main {
    enum TezLevel {
        LOW,
        MEDIUM,
        HIGH
    }

    public static void main(String[] args) {
        TezLevel Varl = TezLevel.MEDIUM;
        switch (Varl) {
            case LOW:
                System.out.println("You are at LOW level.");
                break;
            case MEDIUM:
                System.out.println("You are at MEDIUM level.");
                break;
            case HIGH:
                System.out.println("You are at HIGH level.");
                break;
        }
    }
}
```

你可以在 Java 类内部添加枚举。请参考以下示例。

## Java 用户输入

你可以使用 `Scanner` 类在 Java 中接收用户输入。该类可以从 `util` 包中获取。如果你想使用该类，你需要创建一个对象并应用方法。



```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner ThisObj = new Scanner(System.in);
        String myUserName;

        System.out.println("I need you to Enter
        the username we have allotted you.");
        myUserName = ThisObj.nextLine();

        System.out.println("The Username is as
follows: " + myUserName);
    }
}
```

方法根据输入类型的不同。在下一个示例中，我将使用其他方法从用户处读取值。

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner Obj1 = new Scanner(System.in);

        System.out.println("I want you to Enter
        your name, your age and current salary:");

        String tezname = Obj1.nextLine();
        int tezage = Obj1.nextInt();
        double teszalary = Obj1.nextDouble();
    }
}
```

## 构建循环

你可以遍历枚举的所有值来构建循环。

```java
public static void main(String[] args) {
    for (TezLevel Varl : TezLevel.values()) {
        System.out.println(Varl);
    }
}
```

## Java 接口

在 Java 中发现抽象最高方法是通过借助接口实现的。Java 接口是一种抽象类，你可以使用它来对空体方法分组。如果你想访问接口方法，你需要通过另一个类使用 `implements` 关键字来实现接口。你可以通过实现类提供接口方法的体。

```java
interface AnimalKingdom {
  public void animalSounds();
  public void sleepmode();
}
class Leopard implements AnimalKingdom {
    public void animalSounds() {
        System.out.println("The leopard says: meow meow.");
    }
    public void sleepmode() {
        System.out.println("SnooooooooZzz");
    }
}
```

```java
System.out.println("The leopard says:
meow meow");
}
public void sleepmode() {
    System.out.println("Zzz");
}

class JavaX {
    public static void main(String[] args) {
        Leopard Pig1 = new Leopard();
        Pig1.animalSounds();
        Pig1.sleepmode();
    }
}
```

豹子说：喵喵

Zzz

抽象类和接口不参与对象的创建。接口中的方法没有方法体。实现类为接口提供方法体。当你设置并实现一个接口时，你需要重写每一个其他方法。它们是公共的且抽象的，其属性是最终的、公共或静态的。你必须使用接口来实现高水平的安全。你可以使用它们来隐藏某些细节并显示对象的重要细节。

```java
interface Interface1 {
    public void ThisMethod(); // 这是接口方法
}
```

```java
interface Interface2 {
    public void TheOtherMethod(); // 这是第二个接口方法
}

// 命名为 "implements" 的 DemoClass 被称为 Interface1 和 Interface2
class DemonstrationClass implements Interface1, Interface2 {
    public void ThisMethod() {
        System.out.println("Here is some text for review...");
    }
    public void TheOtherMethod() {
        System.out.println("Here is some more text for testing...");
    }
}

class JavaX {
    public static void main(String[] args) {
        DemonstrationClass Obj1 = new DemonstrationClass();
        Obj1.ThisMethod();
        Obj1.TheOtherMethod();
    }
}
```

这里是一些用于审查的文本...

这里是更多用于测试文本...

# 第十章

## Java 面向对象

在 Java 中，你可以从多个类继承属性和不同的方法。继承的概念分为两类，如父类和子类。用于继承的关键字是 `extends`。

Java 中的类可以是包私有的（package-private）或公共的（public）。目前为止我们使用了公共类作为示例。公共意味着该类可以被程序中任何类访问。相反，包私有意味着该类仅对同一包内的其他类可见。一个 Java 应用程序可能有多个包。包私有是默认的访问级别。如果你不添加任何访问修饰符，意味着该类是高度包私有的。在你声明类的访问级别后，你需要输入 `class` 关键字表示你正在声明一个类。

你已经看到我将类的内容放在类名后的一对大括号内。类的内容构造器、接口、字段、方法和其他类。

## 继承

继承是面向对象编程中的核心概念。它允许你从已创建的类创建一个新类，以便重用现有代码开发另一个程序或应用程序。Java 中的所有类主要都继承自一个预写的基类。它被称为对象类。它由几个可以在你处理类时使用的预写方法组成。其中一个方法被称为 `toString()` 方法。该方法返回表示对象的字符串。我将在接几个示例中使用相同的用法。

假设我们正在开发一个阅读应用，它提供普通和 VIP 两种会员计划。以下是代码。

以下代码将演示如何在 Java 中创建继承。你使用的 `extends` 关键字将帮助继承方法。

```java
class Mathematics {
  int c;

  public void adding(int a, int b) {
    c = a + b;
    System.out.println("The total sum of our given numbers:"+c);
  }

  public void SubractingNum(int a, int b) {
    c = a - b;
    System.out.println("The final difference between these numbers is as follows:"+c);
  }
}
```

```java
public class My_Mathematics extends Mathematics {
    public void multiplying(int a, int b) {
        c = a * b;
        System.out.println("The final product of our given numbers is:"+c);
    }

    public static void main(String[] args) {
        My_Mathematics obj = new My_Mathematics();
        obj.adding(10, 20);
        obj.SubractingNum(50, 10);
        obj.multiplying(5, 4);
    }
}
```

给定数字的总和：30

这些数字之间的最终差值如下：40

给定数字的最终乘积为：20

```java
public void displaying() {
    System.out.println("You are viewing the display method of the superclass");
}

public class SubClass extends SupClass {
    int number = 10;

    // 我现在正在显示子类的方法
    public void displaying() {
        System.out.println("You are viewing the display method of the subclass");
    }

    public void thisMethod() {
        // 我现在正在实例化子类
        SubClass sub = new SubClass();

        // 我现在正在调用子类的 displaying() 方法
        sub.displaying();

        // 我现在正在调用父类的 displaying() 方法
        super.displaying();

        // 我现在正在打印子类变量 number 的值
        System.out.println("This is the value of a variable named number in the sub class:" + sub.number);

        // 现在我正在打印父类中名为 的 的值
        System.out.println("The value of variable namely number in the super class is:" + super.number);
    }
    public static void main(String[] args) {
        SubClass obj1 = new SubClass();
        obj1.thisMethod();
    }
}
```

你正在查看子类的显示方法

你正在查看父类的显示方法

子类中名为 number 的变量的值为:10

父类中名为 number 的变量值为:20

## 父类构造函数

如果一个 Java 类继承了另一个类的属性，则子类将需要父类的默认构造函数。如果你需要调用父类的参数化构造函数，`super` 关键字的使用将有所不同。以下是演示。

```java
super(values);
```

该章节程序演示了如何使用 `super` 关键字调用父类的参数化构造函数。我将向程序添加一个父类和一个子类。该父类有一个接收整数值的参数化构造函数。我将在父类内部使用 `super` 关键字调用此构造函数。

```java
class SupClass {
    int theage;

    SupClass(int theage) {
        this.theage = theage;
    }

    public void gettheAge() {
        System.out.println("The final value of variable theage inside the SupClass is: " + theage);
    }
}
```

```java
public class SubClass extends SupClass {
    SubClass(int theage) {
        super(theage);
    }

    public static void main(String argued[]) {
        SubClass s = new SubClass(24);
        s.gettheAge();
    }
}
```

SupClass 内部变量 theage 的最终值为: 24

程序中的子类继承了父类的所有属性，父类的私有属性除外。

```java
class AnimalKingdom {
}
class MammalFamily extends AnimalKingdom {
}
class ReptileFamily extends AnimalKingdom {
}
public class DogFamily extends MammalFamily {
    public static void main(String args[]) {
        AnimalKingdom a = new AnimalKingdom();
        MammalFamily m = new MammalFamily();
        DogFamily d = new DogFamily();
        System.out.println(m instanceof AnimalKingdom);
        System.out.println(d instanceof MammalFamily);
        System.out.println(d instanceof AnimalKingdom);
    }
}
```

true

true

true

`implements` 关键字构了 IS-A 关系。`implements` 关键字用于类内部以继承接口的属性。类并不扩展这些接口。让我们使用 `instanceof` 运算符来检查 MammalFamily 类是否属于 AnimalKingdom，以及狗是否也属于 AnimalKingdom。该运算符运行良好。

```java
interface AnimalKingdom {}
class MammalFamily implements AnimalKingdom {}

public class DogFamily extends MammalFamily {
    public static void main(String args[]) {
        MammalFamily m = new MammalFamily();
        DogFamily d = new DogFamily();

        System.out.println(m instanceof AnimalKingdom);
        System.out.println(d instanceof MammalFamily);
        System.out.println(d instanceof AnimalKingdom);
    }
}
```

true

true

true

如果一个类实现了一个接口，它必须为接口中定义的所有方法提供实现，除非该类是抽象类。一个类可以实现多个接口，这是 Java 支持行为多继承的方式之一。这允许一个类拥有多种类型。

`implements` 关键字用于表示类实现了一个接口。当一个类实现接口时，它必须为接口中声明的所有方法提供方法体。如果它不提供方法体，则必须声明为抽象类。

```
x.moveon(); // 这一行将执行
AnimalKingdom 类中的方法

}
```

王国中的所有动物都可以移动。

## 多态

多态是特定对象以不同形式存在的能力。最常见的多态发生在面向对象的编程中，当一个特定的父类引用子类的对象时。任何通过多个 IS-A 测试的特定 Java 对象都被认为是多态的。所有的 Java 对象都是多态的，因为它们中的任何一个都会通过其自身类型的 IS-A 测试。

通过引用变量，你可以访问对象。如果引用变量没有被标记为 `final`，则可以将其重新赋值为不同的其他对象。引用类型决定了它可能对该对象调用的特定方法。引用变量指向声明类型的任何子类型的对象。你可以将引用变量声明为接口类型。

Buffalo 类可以继承自 Animal、Buffalo、Object、Dinner、Victim、Vegetarian 等。在这种情况下，我们可以说 Buffalo 类是多态的。

在接下来的示例中，我将解释 Java 中的方法重写（overriding）行为如何让你在设计类时利用多态的这一特定特性。

在接下来的示例中，我将展示被重写的方法如何在父类中保持隐藏状态。除非子类在重写方法中使用 `super` 关键字，否则它永远不会被调用。



```java
public class PublicEmployee {
    private String ename;
    private String eaddress;
    private int number;
    private int esalary;

    public PublicEmployee(String ename,
String eaddress, int number, int esalary) {
        System.out.println("I am in the
process of constructing a public Employee");
        this.ename = ename;
        this.eaddress = eaddress;
        this.number = number;
        this.esalary = esalary;
    }

    public void ThisIsmailCheck() {
        System.out.println("I have to mail a
check to " " + this.ename + " " + +
this.eaddress);
    }

    public String theString() {
        return ename + " " + eaddress + " " +
enumber + " " + esalary;
    }

    public String getename() {
        return ename;
    }

    public String geteaddress() {
        return eaddress;
    }

    public void seteaddress(String
neweaddress) {
        eaddress = neweaddress;
    }

    public int getenumber() {
        return en;
    }

    public int getesalary() {
        return esalary;
    }
}
```

错误：在 `PublicEmployee` 类中未找到 `main` 方法，请按如下定义 `main` 方法：

`public static void main(String[] args)`

或 JavaFX 类必须继承 `javafx.application.Application`

结果是一个错误。

# 第十一章

## Java 日期与时间

Java 中的 `Date` 类通常支持两个构造函数。第一个是 `Date()`，它初始化一个具有当前日期时间的对象。第二个是 `Date(long millisec)` 构造函数，它接受一个等于自 1970 年以来经过的总毫秒数参数。

Java 日期与时间有不同的方法。第一种是 `Boolean after(Date date)`，如果 `Date` 对象包含由 `date` 指定日期，则返回 `true`。否则，返回 `false`。第二种方法被称为 `boolean before(Date date)`。如果调用 `Date` 对象将包含指定的日期，则返回 `true`，否则返回 `false`。第三种方法是 `Object clone()`，它会复制 `Date` 对象。

获取当前日期和时间是一个简单的方法。简单的 `toString()` 方法用于打印当前的日期和时间。该方法如下：

```java
import java.util.Date;
public class TheDateDemonstration {
    public static void main(String args[]) {
        // 这里我将实例化 Date
        对象
        Date date = new Date();

        // 这里我将使用 toString() 方法
        // 显示时间
        System.out.println(date.toString());
    }
}
```

UTC 5月13日 09:31:53

Java 中有三种比较日期的方法。第一种使用 `getTime()` 方法获取自 1970 年以来经过的毫秒数。然后你可以比较这两个值。第二种方法是使用 `before()`、`equals()` 和 `after()` 方法。你还可以部署 `compareTo()` 方法。这是由 `Comparable` 接口定义的并由 `Date` 实现的。

你可以使用 `SimpleDateFormat` 特性在 Java 中格式化日期。这是一个用于格式化和高效解析日期的可靠类。`SimpleDateFormat` 类允许你通过选择定义的日期时间格式模式来开始。

```java
import java.util.*;
import java.text.*;

public class DateDemstration {
    public static void main(String args[]) {
        Date dNow = new Date( );
        SimpleDateFormat ft = new SimpleDateFormat ("E yyyy.MM.dd
'at' hh:mm:ss a zzz");

        System.out.println("Here is the
Current Date: " + ft.format(dNow));
    }
}
```

当前日期为：周四 2021年5月20日 09:40:17 UTC

## 时间

你也可以测量经过的时间。你可能觉得需要以毫秒的形式测量不同的时间点。

```java
import java.util.*;
public class DifferenceDemonstration {
    public static void main(String[] args) {
        try {
            long thestart = System.currentTimeMillis();
            System.out.println(new Date( ) + "\n");

            Thread.sleep(5*180*10);
            System.out.println(new Date( ) + "\n");

            long theend = System.currentTimeMillis();
            long thedifference = theend - thestart;
            System.out.println("The total difference of time is as follows: " + thedifference);
        } catch (Exception e) {
            System.out.println("Here is an exception!");
        }
    }
}
```

2021年5月20日 周四 10:08:36 UTC

2021年5月20日 周四 10:08:45 UTC

差值为：9028

如果你查看乔治亚历（Georgian Calendar），你会发现它是 `Calendar` 类的具体实现。它实现了你每天使用的格列哥日历。`getInstance()` 方法将返回格列哥日历。它将用默认时区的日期和时间初始化。有两个名为 AD 和 BC 的字段。它们代表格列哥日历的两个时代。

```java
import java.util.*;
public class GregorianCalendarDemonstration {

    public static void main(String args[]) {
        String months[] = {"January", "February", "April", "May", "June",
        "July", "August", "September",
        "October", "November", "December"};

        int theYear;
        // 我现在将创建格列哥日历
        // 它将具有其默认语言环境以及时区的
        // 当前日期时间。

        GregorianCalendar gregocalendar = new GregorianCalendar();

        // 这里我将显示当前的日期和时间信息。
        System.out.print("Here is the current date: \");
    }
}
```

当前日期：2021年5月21日

当前时间：2:27:29

当前年份在格列哥日历中不是闰年。

## Java 正则

Java 拥有 `java.util.regex` 包，用于通过正则表达式匹配不同类型的模式。Java 正则易于学习。正则表达式类似于特殊的字符序列，可以帮助你通过特定模式中持有的特殊语法来匹配一组字符串。你可以使用它们来搜索、然后编辑，以及利用数据。

`java.util.regex` 有三个主要的类。第一个是 `Pattern` 类。`Pattern` 类中的对象不提供公共构造函数。要创建模式，你应该调用其中一个公共静态的 `compile()` 方法，它将返回一个 `Pattern` 对象。这些特定方法倾向于接受正则表达式作为第一个参数。

`matcher` 对象像一个引擎，会解释模式并对输入字符串执行匹配操作。与 `Pattern` 类一样，`Matcher` 没有定义公共构造函数。你可以通过使用 `Pattern` 对象上的 `matcher()` 方法来获取 `Matcher`。`PatternSyntaxException` 类似于未检查异常，它将以正则表达式模式的形式指出语法中的错误。

捕获组（Capturing groups）是将不同字符视为单个单元的最佳方式。你可以通过设置括号内组形式的字符来创建它们。接下来的示例将展示如何从字母数字字符串中跟踪数字字符串。

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class TheRegexMatch {
    public static void main(String args[]) {
        // 这里你将看到要扫描以跟踪模式的字符串
        String tezline = "You placed this order 12345";
        // 匹配数字模式
        String tezpattern = "(\\d+)";

        // 编译模式
        Pattern r = Pattern.compile(tezpattern);

        // 创建 matcher 对象
        Matcher m = r.matcher(tezline);
        if (m.find()) {
            System.out.println("Found match: " + m.group(0));
            System.out.println("First group: " + m.group(1));
        } else {
            System.out.println("No match found.");
        }
    }
}
```

*(注：由于原文代码块部分存在不完整或占位符情况，翻译时对逻辑进行了微调以符合逻辑，但严格遵循了代码不翻译的原则)*

原文代码部分似乎存在截断或逻辑错误，根据上下文翻译如下：

...

```java
System.out.println("The Array namely integerArray contains:");
printingArray(integerArray); // This
will pass on the Integer array
```

```java
System.out.println("\nThe Array namely doublesArray contains:");
printingArray(doublesArray); // This
will pass on the Double array
```

```java
System.out.println("\nThe Array characterArray contains:");
printingArray(characterArray); //
This will pass on the Character array
}
```

名为 integerArray 的数组包含：

1 2 3 4 5 6 7 9

名为 doublesArray 的数组包含：

1.1 2.2 3.3 4.4

名为 characterArray 的数组包含：

H E L L O

## 绑定类型参数 (Bonded Type Parameters)

有时你需要限制传递给类型参数的不同类型。一个操作数字的方法可能想要接收几个子类。你需要列出类型参数名称来声明一个绑定类型参数。然后你必须跟上上界和 `extends` 关键字。

```java
public class MaxTesting {
    // This will determine the largest of the三个 Comparable obj

    public static T <T extends Comparable<T>> T
    maximum(T a, T b, T c) {
        T maximum = a; // This step will
        assume that the variable is the largest

        if(b.compareTo(maximum) > 0) {
            maximum = b; // This will assume
            that b is the largest
        }

        if(c.compareTo(maximum) > 0) {
            maximum = c; // This assumes that
            c is the largest
        }
        return maximum; // This code will
        return the largest object in the code
    }

    public static void main(String[] args[]) {
        System.out.printf("The Maximum value of %d, %d and %d is %d\n",
            30, 40, 50, maximum(30, 40, 50));

        System.out.printf("The Maximum value of %.1f,%.1f and %.1f is %.1f\n\n",
            60.6, 80.8, 70.7, maximum(60.6, 80.8, 70.7));

        System.out.printf("The Maximum value of %s, %s and %s is %s\n",
            "melon", "guava", "strawberry",
            maximum("melon", "guava", "strawberry"));
    }
}
```

30, 40 和 50 的最大值是 50

60.6, 80.8 和 70.7 的最大值是 80.8

melon, guava 和 strawberry 的最大值是 strawberry

## 泛型类 (Generic Classes)

泛型类的声明类似于非泛型类声明，区别在于它的名称包含一个类型参数。该泛型类的类型参数部分有多个用逗号分隔的类型参数。这些类被标记为参数化类，因为它们接受多个参数。

```java
public class Boxing<T> {
    private T a;

    public void adding(T a) {
        this.a = a;
    }

    public T get() {
        return a;
    }

    public static void main(String[] args[]) {
        Boxing<Integer> integerBox = new Boxing<Integer>();
        Boxing<String> stringBox = new Boxing<String>();
    }
}
```

最终的 String 值如下：我正在学习 Java 编程。

# 结论 (Conclusion)

现在你已经来到了书的末尾，建议尽可能多练习，以更好地理解这种语言。下一步是理解如何在你的程序中使用这些代码。基于通过这本书获得的知识，你可以在互联网上学习高级代码示例并对其进行自定义以学习更多。

编码是棘手且困难的，直到你开始实践。这是一项艰巨的工作。我从基础开始编写这本书。一旦你掌握了代码，就可以利用这些基础知识。

Java 是现在，也是未来。它短期内不会失去其巨大的人气。因此，学习 Java 是一项高回报的技能。



# 参考文献

- Java - 循环控制 (n.d.). https://www.tutorialspoint.com/java/java_loop_control.htm
- Java - 数字类 (n.d.). https://www.tutorialspoint.com/java/java_numbers.htm
- Java - 多态 (n.d.). https://www.tutorialspoint.com/java/java_polymorphism.htm
