
# Java 入门指南：掌握你的 Java 技能

## 引言

Java 是世界上最流行的编程语言之一，主要源于它的多功能性和兼容性。Java 可用于许多领域，包括软件开发、移动应用程序和大型系统开发。截至 2019 年，88% 的智能手机市场份额运行在 Android 上，而该移动操作系统是用 Java 编写的。对于开发者来说，了解 Java 将为你开启很多大门。

## 什么是 Java？

Java 是一种流行的编程语言，创建于 1995 年。它由 Oracle 所有，有超过 30 亿台设备运行 Java。

它被用于：

- 移动应用程序（特别是 Android 应用）
- 桌面应用程序
- Web 应用程序
- Web 服务器和应用服务器
- 游戏
- 数据库连接

还有更多、更多！

### 为什么使用 Java？

- Java 可以在不同的平台（Windows, Mac, Linux, Raspberry Pi 等）上运行
- 它是世界上最流行的编程语言之一
- 它易于学习且简单易用
- 它是开源免费的
- 它安全、快速且强大
- 它拥有庞大的社区支持（数千名开发者）
- Java 是一种面向对象的语言，提供了清晰的结构并允许代码重用，降低了开发成本
- 由于 Java 与 C++ 和 C# 相似，程序员很容易切换到 Java

## Java 历史

Java 创建于太阳微系统公司（Sun Microsystems），当时 James Gosling 领导着研究人员小组，试图创建一种允许消费级设备相互交互的新语言。该语言的工作始于 1991 年，不久后团队的重心转向了一个新的空白领域——万维网。Java 于 1995 年首次发布，其交互能力表明它特别适用于 Web。

Java 与其他编程语言的工作方式的区别是革命性的。其他语言的代码首先由编译器翻译成特定类型计算机的指令。而 Java 编译器将代码转换为被称为字节码（Bytecode）的内容，然后由称为 Java 运行环境（`JRE`）或 Java 虚拟机软件解释。`JRE` 充当虚拟计算机，解释字节码并将其翻译给主机计算机。因此，Java 代码可以在多个平台上以相同的方式编写（“编写一次，到处运行”），这有助于它在互联网上流行，因为互联网上许多不同类型的计算机可能会获取同一个 Web 页面。

目前，Java 用于网络编程、移动设备、游戏、电子商务解决方案等。以下是描述 Java 历史的要点。

### 从 Oak 到 Java 的历史

1. James Gosling、Mike Sheridan 和 Patrick Naughton 于 1991 年 6 月启动了 Java 语言项目。这个工程师小组被称为 Green Team（绿色小组）。
2. 最初设计用于电子应用中机顶盒的小型嵌入式系统。
3. 最初，它被 James Gosling 称为 "Greentalk"，文件扩展名为 `.gt`。
4. 之后，它被称为 Oak，并作为 Green 项目的一部分进行开发。

### 为什么 Java 名为 "Oak"？

5. 为什么是 Oak？Oak 是力量的象征，被选为美国、法国、德国等许多国家的国树。
6. 1995 年，Oak 被更名为 Java，因为它是根据 Oak 命名的。

### 为什么 Java 名为 "Java"？

为什么他们选择 Java 作为语言？团队聚集在一起选择新名字。建议的词有 "Relay"、"Silk"、"Stalk"。他们希望反映互联网：Relay、Mocha、Java，并且简单易读。根据 James Gosling 的说法，“Java 是和 Stalk 一样热门的选择”。由于 Java 是独特的，大多数团队成员倾向于 Java。

8. Java 是印度尼西亚的一个岛屿，那里是产第一批咖啡的地方（被称为 java）。它是一种咖啡豆。Java 这个名字是 James Gosling 在办公室附近喝咖啡时选定的。
9. 注意，Java 只是一个名字，而不是一种语言。
10. 最初由 James Gosling 在太阳微系统公司（现为 Oracle 公司的子公司）开发，并于 1995 年发布。
11. 1995 年，《时代》杂志将 Java 称为 1995 年最佳产品之一。
12. `JDK 1.0` 发布（1996 年 1 月 23 日）。在 Java 首次发布后，该语言增加了许多功能。现在 Java 已用于 Windows 应用程序、Web 应用程序、企业应用程序、移动应用程序等。每个版本都为 Java 增加了新功能。

尽管名称相似，设计在 Web 浏览器中运行的 JavaScript 语言并不是 Java 的一部分。JavaScript 于 1995 年在 Netscape 公司开发，被构想为 Java 的伙伴。在 Netscape 获得 Sun 的营销许可之前，最初被称为 Mocha，然后是 Live。

### Java 版本历史

目前已发布了许多 Java 版本。Java 目前稳定版本是 Java SE 10。

- JDK Alpha 和 Beta (1995)
- `JDK 1.0` (1996 年 1 月 23 日)
- `JDK 1.1` (1997 年 2 月 19 日)
- `J2SE 1.2` (1998 年 12 月 8 日)
- `J2SE 1.3` (2000 年 5 月 8 日)
- `J2SE 1.4` (2002 年 2 月 6 日)
- `J2SE 5.0` (2004 年 9 月 30 日)
- `Java SE 6` (2006 年 12 月 11 日)
- `Java SE 7` (2011 年 7 月 28 日)
- `Java SE 8` (2014 年 3 月 18 日)
- `Java SE 9` (2017 年 9 月 21 日)
- `Java SE 10` (2018 年 3 月 20 日)

与 C 和 C++ 在内的许多其他编程语言不同，Java 在编译时并不是编译成特定平台的机器码，而是编译成与平台无关的字节码。这些字节码通过网络分发，并在运行所在的平台通过虚拟机（`JVM`）进行解释。

Java 是平台独立的，因为它与 C、C++ 等语言不同，这些语言被编译成特定平台的机器码，而 Java 是一种“编写一次，到处运行”的语言。平台是指程序运行的硬件或软件环境。

平台有两种类型：基于软件的和基于硬件的。Java 提供了一个基于软件的平台。

Java 平台与大多数其他平台不同，它是一个运行在其他硬件平台之上的软件平台。它包含两个组件：

- 运行环境 (Runtime Environment)
- API (应用程序编程接口)

Java 代码可以在多个平台上运行，例如 Windows、Linux、Sun Solaris、Mac/OS 等。Java 代码由编译器编译并转换为字节码。这种字节码是与平台无关的代码，因为它可以在多个平台上运行，即“编写一次，到处运行”（WORA）。

## 3. 简单

Java 的设计易于学习。如果你理解了 Java OOP（面向对象编程）的基本概念，就会很容易掌握。Java 非常容易学习，其语法简单、简洁且易于理解。根据 Sun 公司的说法，Java 语言是一种简单的编程语言，因为它：

- Java 语法基于 C++（因此程序员在学习过 C++ 之后学习它更容易）。
- Java 删除了许多复杂且很少使用的特性，例如显式指针、操作符重载等。
- 不需要删除未引用的对象，因为 Java 有自动垃圾回收机制。

## 4. 安全

凭借 Java 的安全特性，能够开发出无病毒、防篡改的系统。身份验证技术基于公钥加密。通过 Java，我们可以开发无病毒系统。Java 是安全的，是因为：

- 没有显式指针
- Java 程序运行在虚拟机沙箱中。
- 类加载器：Java 中的 ClassLoader 是 Java 运行环境（`JRE`）的一部分，用于动态将 Java 类加载到 Java 虚拟机。它通过将本地文件系统的类包与从网络源导入的类包分离来增加安全性。
- 字节码验证器 (BytecodeVerifier)：它检查代码段中是否存在违反对象访问权的非法代码。
- 安全管理器 (Security Manager)：它决定类可以访问哪些资源，例如对本地磁盘的读取和写入。

Java 语言默认提供了这些安全性。应用程序开发者也可以通过 `SSL`、`JAAS`、`Cryptography` 等显式地提供某些安全性。

## 5. 架构中立

Java 编译器生成架构无关的对象文件格式，这使得编译后的代码在存在 Java 运行时的情况下可以在许多处理器上执行。例如，基本类型的大小是固定的。在 C 语言中，`int` 数据类型在 32 位架构中占用 2 字节内存，在 64 位架构中占用 4 字节内存。但在 Java 中，32 位和 64 位架构都占用 4 字节内存。

## 6. 可移植

架构中立和具有独立的规范方面使得 Java 具有可移植性。Java 编译器用 ANSI C 编写，边界是 POSIX 子集。

## 7. 健壮

Java 主要在编译阶段和运行时检查方面做出努力以消除易出错的情况。健壮意味着 Java 是强大的：

- 它使用了强大的内存管理。
- 没有未使用的指针。
- Java 中有运行在 Java 虚拟机上的自动垃圾收集。
- Java 中有异常处理和类型检查。这一切使得 Java 变得健壮。

## 8. 多线程

凭借 Java 的多线程特性，编写可以同时执行许多任务的程序。这种设计允许开发者构建运行流畅的应用程序。

## 9. 解释型

Java 字节码被翻译成原生机器指令且不存储在任何地方。开发更快，链接是增量且轻量级的。

## 10. 高性能

通过即时编译器（Just-In-Time compiler），Java 实现了高性能。

## 11. 分布式

Java 为网络环境设计。Java 是分布式的，因为它便于用户分发应用程序。`RMI` 和 `EJB` 用于构建分布式应用程序。Java 的这一特性允许从互联网上的任何机器访问方法。

## 12. 动态

Java 被认为比 C 或 C++ 更具动态，因为它是为动态环境设计的。Java 程序可以携带大量的运行时信息，这些信息可以在运行时验证和解析对象。

## Java 与 C++

### 1. 平台独立性

C++ 是一种依赖平台的语言。用 C++ 编写的源码需要在每个平台上进行编译。Java 是平台独立的，一旦编译成字节码，就可以在任何平台上执行。

### 2. 编译器和解释器

C++ 是一种编译型语言。用 C++ 编写的源程序被编译成目标代码，然后可以执行以产生输出。Java 既是编译语言也是解释型语言。Java 源码的编译输出是平台无关的字节码。

### 3. 跨平台应用

在某个操作系统上编译的 C++ 程序不会在另一个操作系统上运行。你需要为不同的操作系统重新编译程序以便其运行。相反，Java 程序可以在任何安装了 `JVM` 的平台上运行，而不需要重新编译。

### 4. 内存安全

C++ 不是一种内存安全的语言。你可以进行内存管理，这是一个巨大的优势。但在程序执行时可能会发生内存错误，并出现崩溃等严重问题。相反，Java 不允许内存操作，它是系统控制的。因此这类问题不会出现。

### 5. 指针

C++ 拥有完整的指针支持。Java 有有限的指针支持。Java 对指针的支持是有限的。最初 Java 完全没有指针，但后续版本开始提供有限的指针支持。在 Java 中使用指针不像在 C++ 中那样随意。

### 6. 线程

C++ 不支持线程，但 Java 支持。Java 通过类提供了内置的线程支持。我们可以继承类并重写 `run()` 方法。

### 7. 性能

C++ 程序通常更快，因为它们不需要被解释。相反，Java 并不快，因为它们需要先被解释，这需要时间。但请记住 `JVM` 会优化你的代码。这提高了程序的性能。因此，如果 C++ 程序没有针对性能优化，Java 程序运行可能比 C++ 程序快。但如果 C++ 程序经过高度优化，它将比 Java 代码快得多。

### 8. 接近硬件程度

与 Java 相比，C++ 是一种低级语言，更接近硬件。Java 并不接近硬件。

### 9. 作用域解析运算符

C++ 支持作用域解析运算符，而 Java 没有这些运算符。作用域解析运算符用于访问全局变量和在类外部定义方法。

C++ 支持作用域解析运算符，因为它使用它来访问全局变量。它还允许我们在类外部定义函数，并使用作用域解析运算符访问它们。

相比之下，Java 不支持作用域解析运算符。Java 也不允许在外部定义函数。

### 10. 默认参数

在 C++ 中你可以拥有默认参数，而在 Java 中没有这种东西。

## C++ 和 Java 的相似之处

这两种语言在语法和语言特性方面非常相似。它们如此相似，如果你向你展示项目中的部分 C++ 代码并问它是 C++ 还是 Java 代码，你可能会感到困惑。

执行：在编译时，Java 源代码或 `.java` 文件转换为字节码或 `.class` 文件。在运行时，JVM（Java 虚拟机）会加载 `.class` 文件并在解释器的帮助下将其转换为机器码。对方法调用进行编译（使用即时编译 de JIT 编译器）后，JVM 将执行优化后的代码。因此，Java 既是编译型语言也是解释型语言。

另一方面，C++ 仅使用编译器执行代码。C++ 编译器将源代码编译转换为机器码。这就是为什么 `c++` 比 Java 快，但它不是平台无关的。

特性：C++ 和 Java 都具有多种面向对象的编程特性，提供了许多实用的编程功能。某些特性由一种支持，而另一些不支持。

下表显示了两种编程语言支持和不支持的功能：

应用：C++ 和 Java 都有广泛的应用领域。以下是这两种语言的应用：

### C++ 编程语言的应用

- 适用于开发大型软件（如，客运系统）。
- `MySQL` 是用 C++ 编写的。
- 对于游戏，C++ 主要用于游戏开发。
- Google Chrome 浏览器、文件系统、播放器都是用 C++ 编写的。
- Adobe Photoshop、Illustrator 这些流行的应用程序使用 C++ 编写脚本。
- 高级计算和图形学——实时仿真、高性能计算。C++ 用于如 MRI 机等先进医疗设备。

### Java 编程语言的应用

- 桌面 GUI 应用开发。
- Android 和移动应用开发。
- Java 在嵌入式系统中的应用，如 SIM 卡、磁盘等。
- Java EE（企业级）为运行大型软件提供了 API 和环境。
- 网络应用和 Web 服务，如互联网、Web 开发。

环境：C++ 是依赖平台的，而 Java 是平台无关的。你必须在相同的平台上编写和运行 C++ 代码。Java 具有 WORA（一次编写，随处运行）特性，我们可以在这里编写代码并在任何地方运行。

## 如何在 Java 中设置路径

设置 `java` 等工具需要设置路径。如果你将 Java 源文件保存在 `bin` 目录内，则不需要设置路径，因为工具在当前目录中可用。然而，如果你的 Java 文件在 `bin` 文件夹之外，则有必要设置 JDK 的路径。

在 Java 中设置路径有两种方法：

- 临时
- 永久

### 1) 如何在 Windows 中设置 JDK 的临时路径

要设置 JDK 的临时路径，你需要遵循以下步骤：

- 打开命令提示符。
- 复制 JDK `bin` 目录的路径。
- 在命令提示符中输入：`set path=copied_path`

### 2) 如何在 Windows 中设置 JDK 的永久路径

要设置 JDK 的永久路径，你需要遵循以下步骤：

转到此电脑属性 -> 高级选项卡 -> 环境变量 -> 用户变量新建 -> 在变量名中输入路径 -> 在变量值中输入 `bin` 文件夹的路径 -> 确定 -> 确定 -> 确定

**示例：**

1. 转到此电脑属性。
2. 点击高级选项卡。
3. 点击环境变量。
4. 点击用户变量新建。
5. 在变量名中输入路径。
6. 复制 `bin` 文件夹的路径。
7. 将 `bin` 文件夹的路径粘贴到变量值中。
8. 点击确定按钮。
9. 点击确定按钮。

现在你的永久路径已设置。你现在可以在任何驱动器执行任何 Java 程序。

### 为 Linux 设置 JAVA 路径

1. 登录你的账户并打开 `.bash_profile` 文件。
2. 使用语法 `export JAVA_HOME=<path-to-java>` 设置 `JAVA_HOME`。如果你的路径设置为 `/usr/java/jdk1.5.0_07/bin/java`，则如下设置：

```bash
export JAVA_HOME=/usr/java/jdk1.5.0_07/bin/java
```

3. 如下设置 `PATH`：

```bash
export PATH=$PATH:/usr/java/jdk1.5.0_07/bin
```

请随意替换 `/usr/java/jdk1.5.0_07` 为你的设置值并重新登录以使更改生效。或者，使用以下命令激活路径设置：

```bash
source ~/.bash_profile
```

或

```bash
. ~/.bash_profile
```

验证新设置：

```bash
echo $JAVA_HOME
echo $PATH
```

## Java 中的数据类型和变量

Java 中的变量是在程序执行期间存储数据的容器。变量被分配了类型和它可以容纳的值数量。变量是数据内存位置的名称。Java 变量有类型：局部、实例和静态。

在 Java 中，有不同类型的变量，例如：

- `String`：存储文本如 "Hello"。String 值被双引号包围。
- `int`：存储整数（不带小数）如 123。
- `float`：存储带有小数的浮点数，如 19.99。
- `char`：存储单个字符，如 'A' 或 'B'。Char 值被单引号包围。
- `boolean`：存储具有两种状态的值：true 或 false

为了在程序中使用变量，你需要执行两个步骤：

- 变量声明
- 变量初始化

### 变量声明

`type variable = value;`



`type` 是 Java 类型之一（如 `int` 或 `String`），`variable` 是变量的名称（如 `x` 或 `name`）。等号用于给变量赋值。

**示例**

创建一个类型为 `String` 名为 `name` 的变量并赋值为 "John"：

```java
String name = "John";
System.out.println(name);
```

## 变量的类型

在 Java 中，有三种变量：

- 局部变量
- 实例变量
- 静态变量

### 1) 局部变量

在方法体内部定义的变量称为局部变量。你只可以在该方法中使用此变量，类中的其他方法甚至不知道该变量的存在。局部变量不能用 `static` 关键字定义。

### 2) 实例变量

在类内部但在方法体外部定义的变量称为实例变量。它没有被声明为静态。它被称为实例是因为它的值是实例特定的，并且不在实例之间共享。

### 3) 静态变量

声明为 `static` 的变量称为静态变量。它不能是局部变量。你可以创建一个静态变量的副本并在类的所有实例之间共享。静态变量的内存分配只在类加载到内存时发生一次。

**理解 Java 变量类型的示例**

```java
class A{
    int data=50;//实例变量
    static int m=100;//静态变量
    void method(){
        int n=90;//局部变量
    }
}//类的结束
```

# Java 变量示例：收缩（强制转换）

```java
class Simple{
    public static void main(String[] args){
        float f=10.5f;
        //int a=f;//编译时错误
        int a=(int)f;
        System.out.println(f);
        System.out.println(a);
    }
}
```

输出：

```
10.5
10
```

变量名称（唯一标识符）的通用规则如下：

- 名称可以包含字母、数字、下划线和美元符号
- 名称必须以字母开头
- 名称应该以小写字母开头，且不能包含空格
- 名称也可以以 `$` 和 `_` 开头（但在本教程中不会使用它们）
- 名称是区分大小写的（`myVar` 和 `myvar` 是不同的变量）
- 不能使用保留字（如 Java 关键字，如 `int` 或 `boolean`）作为名称

## JAVA 中的数据类型

数据类型定义了变量可以取的值，例如，如果一个变量的数据类型为 `int`，它就只能取整数值。在 Java 中，我们将数据类型分为两类：

1. 基本数据类型
2. 非基本数据类型 – 数组（Arrays）和 `Strings` 是非基本数据类型，我们将在后面的教程中讨论它们。在这里我们将讨论 Java 中的基本数据类型和字面量。

Java 是一种静态类型语言。如果变量的数据类型在编译时已知，则该语言是静态类型的。这意味着在使用变量之前必须指定变量的类型（声明变量）。

## Java 基本数据类型

在 Java 语言中，基本数据类型是数据操作的构建块。这些是 Java 语言中提供的基础数据类型。

共有 8 种基本数据类型：

- `boolean` 数据类型
- `byte` 数据类型
- `char` 数据类型
- `short` 数据类型
- `int` 数据类型
- `long` 数据类型
- `float` 数据类型
- `double` 数据类型

### Boolean 数据类型

Boolean 数据类型仅存储两个可能的值：`true` 和 `false`。该数据类型用于跟踪真/假状态的简单标志位。`Boolean` 数据类型指定了一位信息，但其“大小”无法精确定义。

示例：`boolean one = false`

语法：

```java
boolean booleanVar;
```

大小：取决于虚拟机

值：`true`, `false`

默认值：`false`

### 2. byte

`byte` 数据类型是 8 位的符号补码整数。`byte` 数据类型有助于在大型数组中节省内存。它可以存储 -128 到 127 之间的整数。主要用于节省内存，以及当你确定数字一定会在 `byte` 数据类型指定的范围内时使用。

该数据类型的默认大小：1 字节

默认值：0

语法：

```java
byte byteVar;
```

大小：1 字节（8 位）

值：-128 到 127

默认值：0

### 3. char

存储字符。`char` 数据类型是单个 16 位 Unicode 字符。它的取值范围在 `'\u0000'`（或 0）到 `'\uff'`（或 65535）之间。`char` 数据类型用于存储字符。

大小：2 字节

```java
class JavaExample {
    public static void main(String[] args) {
        char ch = 'Z';
        System.out.println(ch);
    }
}
```

输出：`Z`

### Short 数据类型

`short` 数据类型是 16 位的符号补码整数。它的取值范围在 -32768 到 32767 之间。它的最小值为 -32768，最大值为 32767。它的默认值为 0。`short` 数据也可以像 `byte` 数据一样节省内存。`short` 数据比 `int` 小 2 倍。

示例：`short s = 10000`, `short r = -5000`

### int

当 `short` 不足以容纳该数字时使用：

```java
class JavaExample {
    public static void main(String[] args) {
        short num;
        num = 150;
        System.out.println(num);
    }
}
```

输出：`150`

### 4. long

当 `int` 不足以容纳该值时使用，它的范围比 `int` 数据大，范围从 -9223372036854775808 到 9223372036854775807。

大小：8 字节

默认值：0

示例：

```java
class JavaExample {
    public static void main(String[] args) {
        long num = -123325262L;
        System.out.println(num);
    }
}
```

输出：`-123325262`

### 5. double

足够容纳 15 位小数。

大小：8 字节。

示例：

```java
class JavaExample {
    public static void main(String[] args) {
        double num = -4293737.9;
        System.out.println(num);
    }
}
```

输出：`-4293737.9`

### 6. float

足够容纳 6 到 7 位小数。

大小：4 字节。

```java
class JavaExample {
    public static void main(String[] args) {
        float num = 19.98f;
        System.out.println(num);
    }
}
```

输出：`19.98`

# Java 运算符

Java 运算符用于执行操作。例如：`+`、`-`、`*`、`/` 等。Java 中有很多类型的运算符，如下：

- 一元运算符
- 算术运算符
- 移位运算符
- 关系运算符
- 位运算符
- 逻辑运算符
- 三元运算符
- 赋值运算符

## 一元运算符

Java 一元运算符只需要一个操作数。一元运算符用于执行各种操作，例如：

- 递增/递减值
- 取反表达式
- 取反值

### 一元运算符示例：++ 和 --

```java
class OperatorExample {
    public static void main(String[] args) {
        int x = 10;
        System.out.println(x++); // 10
        System.out.println(++x); // 12
        System.out.println(x--); // 11
        System.out.println(--x); // 10
    }
}
```

输出：

```
10
12
11
10
```

### 一元运算符示例 2：++ 和 --

```java
class OperatorExample {
    public static void main(String[] args) {
        int a = 10;
        int b = 10;
        System.out.println(a++ + a); // 22
        System.out.println(b++); // 21
    }
}
```

输出：

```
22
21
```

### 一元运算符：~ 和 !

```java
class Operator {
    public static void main(String[] args) {
        int a = 10;
        int b = -10;
        boolean c = true;
        boolean d = false;
        System.out.println(~a); // -11
        System.out.println(~b); // 9
        System.out.println(!c); // false
        System.out.println(!d); // true
    }
}
```

输出：

```
-11
9
false
true
```

## 算术运算符

算术运算符用于执行数学运算。

| 运算符 | 说明 | 示例 |
| :--- | :--- | :--- |
| `+` | 相加 | `x + y` |
| `-` | 从另一个值中减去一个 | `x - y` |
| `*` | 两个值相乘 | `x * y` |
| `/` | 一个值除以另一个 | `x / y` |
| `%` | 返回余数 | `x % y` |
| `++` | 变量加 1 | `++x` |
| `--` | 变量减 1 | `--x` |

### 左移运算符

Java 左移运算符 `<<` 用于将值中的所有位左移指定的次数。

```java
class OperatorExample {
    public static void main(String[] args) {
        System.out.println(10<<2); // 10*2²=40
        System.out.println(10<<3); // 10*2³=80
        System.out.println(20<<2); // 20*2²=80
        System.out.println(15<<4); // 15*2⁴=240
    }
}
```

输出：

```
40
80
80
240
```

### 右移运算符

Java 右移运算符 `>>` 用于将左操作数的值右移右操作数所指定的位数。

```java
class OperatorExample {
    public static void main(String[] args) {
        System.out.println(10>>2); // 10/2²=2
        System.out.println(20>>2); // 20/2²=5
        System.out.println(20>>3); // 20/2³=2
    }
}
```

输出：

```
2
5
2
```

### Java 移位运算符示例：>> vs >>>

```java
class OperatorExample {
    public static void main(String[] args) {
        // 对于正数，>> 和 >>> 效果相同
        System.out.println(20>>2);
        System.out.println(20>>>2);
        // 对于负数，>>> 将符号位（最高位）更改为 0
        System.out.println(-20>>2);
        System.out.println(-20>>>2);
    }
}
```

输出：

```
5
5
-5
1073741819
```

# Java AND 运算符示例：逻辑 && 与按位 &

逻辑运算符 `&&` 在第一个条件为假时，不会检查第二个条件。它只在第一个条件为真时才会检查第二个条件。

按位运算符 `&` 无论第一个条件为真为假，都会检查两个条件。

```java
class OperatorExample {
    public static void main(String args[]) {
        int a=10;
        int b=5;
        int c=20;
        System.out.println(a<b&&a<c); // false && true = false
        System.out.println(a<b&a<c); // false & true = false
    }
}
```

**输出：**

```
false
false
```

# Java AND 运算符示例：逻辑 && 对比按位 &

```java
class OperatorExample {
    public static void main(String args[]) {
        int a=10;
        int b=5;
        int c=20;
        System.out.println(a<b&&a++<c); // false && true = false
        System.out.println(a); // 10 因为第二个条件没有被检查
        System.out.println(a<b&a++<c); // false && true = false
        System.out.println(a); // 11 因为第二个条件被检查了
    }
}
```

**输出：**

```
false
10
false
11
```

# Java OR 运算符示例：逻辑 || 与按位 |

逻辑运算符 `||` 在第一个条件为真时，不会检查第二个条件。它只在第一个条件为假时才会检查第二个条件。

按位运算符 `|` 无论第一个条件为真为假，都会检查两个条件。

```java
class OperatorExample {
    public static void main(String args[]) {
        int a=10;
        int b=5;
        int c=20;
        System.out.println(a>b||a<c); // true || true = true
        System.out.println(a>b|a<c); // true | true = true
        // || vs |
        System.out.println(a>b||a++<c); // true || true = true
        System.out.println(a); // 10 因为第二个条件没有被检查
        System.out.println(a>b|a++<c); // true | true = true
        System.out.println(a); // 11 因为第二个条件被检查了
    }
}
```

**输出：**

```
true
true
true
10
true
11
```

## JAVA 关键字

Java 关键字也称为保留字。关键字是作为代码关键标识的特定单词。这些是 Java 预定义的单词，因此不能用作变量或对象名。

### Java 关键字列表

下面列出了 Java 关键字或保留字的列表：

- `abstract`: Java `abstract` 关键字用于声明抽象类。抽象类可以提供接口的实现。它可以包含抽象方法和非抽象方法。
- `boolean`: Java `boolean` 关键字用于将变量声明为布尔类型。它可以持有 True（真）和 False（假）值。
- `break`: Java `break` 关键字用于跳出循环或 switch 语句。它在指定的条件下中断程序的当前流。
- `byte`: Java `byte` 用于声明可以持有 8 位数据的变量。
- `case`: Java `case` 与 switch 语句配合使用，标记文本块。
- `catch`: Java `catch` 用于捕获语句生成的异常。它必须在 try 块之后使用。
- `char`: Java `char` 用于声明可以持有无符号 16 位字符的变量。
- `class`: Java `class` 用于声明一个类。
- `continue`: Java `continue` 用于继续循环。它继续程序的当前流，并在指定的条件下跳过剩余代码。



- `default`：Java `default` 关键字用于指定 `switch` 语句中的默认块。
- `do`：Java `do` 用于控制语句中声明循环。它可以多次迭代程序的某部分。
- `double`：Java `double` 用于声明可以持有 64 位浮点数的变量。
- `else`：Java `else` 用于指示 `if` 语句中的备选分支。
- `enum`：Java `enum` 用于定义一组固定常量。枚举构造函数始终是私有的或默认的。
- `extends`：Java `extends` 用于指示一个类派自另一个类或接口。
- `final`：Java `final` 用于指示一个变量持有常量值。它应用于变量，并用于限制用户。
- `finally`：Java `finally` 指示 `try-catch` 结构中的代码块。无论异常是否被处理，该块始终会被执行。
- `float`：Java `float` 用于声明可以持有 32 位浮点数的变量。
- `for`：Java `for` 用于启动 `for` 循环。它用于在某些条件变为真时重复执行一组指令/函数。如果迭代次数是固定，建议使用 `for` 循环。
- `if`：Java `if` 测试条件。如果条件为真，则执行 `if` 块。
- `implements`：Java `implements` 用于实现接口。
- `import`：Java `import` 使类和接口对当前代码可用且可访问。
- `instanceof`：Java `instanceof` 用于测试一个对象是否是某个类或接口的实例。
- `int`：Java `int` 用于声明可以持有 32 位整数的变量。
- `interface`：Java `interface` 用于声明接口。它可以包含抽象方法。
- `long`：Java `long` 用于声明可以持有 64 位整数的变量。
- `native`：Java `native` 用于指定某个方法是使用 JNI（Java Native）的本地代码。
- `new`：Java `new` 用于创建对象。
- `null`：Java `null` 用于指示引用不指向任何内容。它代表垃圾值。
- `package`：Java `package` 用于声明包含类的包。
- `private`：Java `private` 是一个访问修饰符。它用于指示方法或变量仅在类内可访问。
- `protected`：Java `protected` 是访问修饰符。它可以在包内访问，并通过继承在包外访问。它不能应用于类本身。
- `public`：Java `public` 是访问修饰符。它用于指示项目随处可用。它在所有修饰符中范围最大。
- `return`：Java `return` 用于在方法执行完成时返回。
- `short`：Java `short` 用于声明可以持有 16 位整数的变量。
- `static`：Java `static` 用于指示变量或方法是类方法。Java 中的 `static` 关键字主要用于内存管理。
- `strictfp`：Java `strictfp` 用于限制浮点运算以确保移植性。
- `super`：Java `super` 是一个引用变量，用于引用父类对象。它可以调用父类方法。
- `switch`：Java `switch` 关键字包含一个根据测试值执行代码的语句。`switch` 语句测试变量与多个值的相等性。
- `synchronized`：Java `synchronized` 用于指定多线程代码中的关键区域或方法。
- `this`：Java `this` 关键字可以在方法或构造函数中引用当前对象。
- `throw`：Java `throw` 关键字用于显式抛出异常。它主要用于抛出自定义异常。它后面跟着一个实例。
- `throws`：`throws` 关键字用于声明异常。检查异常可以通过 `throws` 传播。
- `transient`：Java `transient` 关键字用于序列化。如果你定义任何数据成员为 `transient`，它将不会被序列化。
- `try`：Java `try` 用于启动一个测试异常的代码块。`try` 块必须后跟 `catch` 或 `finally` 块。
- `void`：Java `void` 关键字用于指定方法没有返回值。
- `volatile`：Java `volatile` 用于指示变量可能会异步变化。
- `while`：Java `while` 用于启动 `while` 循环。该循环多次迭代程序的某部分。如果迭代次数不是固定，建议使用 `while` 循环。

# Java 中的继承

继承是面向对象编程（OOP）的一个重要支柱。在 Java 中，它是允许一个类继承另一个类的特征（字段和方法）的机制。

## 重要术语

- **超类（Super Class）**：被继承特征的类被称为超类（或基类、或父类）。
- **子类（Sub Class）**：继承另一个类的类被称为子类（或派生类、扩展类或子类）。子类除了继承父类的字段和方法外，还可以添加自己的字段和方法。
- **可重用性（Reusability）**：继承支持“可重用性”的概念，即：当我们想要创建一个新类，而已经有一个类包含了我们需要的某些代码时，我们可以从现有类派生出新类。通过这样做，我们重用了现有类的字段和方法。

# Java 中的构造函数链（Constructor chaining）

在同一个类的一个构造函数中调用另一个构造函数被称为构造函数链。构造函数链的真正目的是你可以通过一系列不同的构造函数传递参数，但只在一个地方完成初始化。这允许你从单点位置维护你的初始化逻辑，同时为用户提供多个构造函数。如果我们不进行链式调用，且两个不同的构造函数需要特定的参数，你就必须初始化该参数两次；当初始化发生变化时，你必须在每个构造函数中修改它，而不是只在一个地方。

构造函数链可以通过两种方式实现：

- **同一类内部**：可以使用 `this()` 关键字调用同一类中的构造函数。
- **来自基类**：通过使用 `super()` 关键字调用基类的构造函数。

构造函数链通过继承发生。子类构造函数的任务是首先调用超类的构造函数。这确保了子类对象的创建是从超类成员变量初始化开始的。继承链中可能存在任意数量的类。每个构造函数都会向上调用，直到到达最顶部的类。

## 为什么我们需要构造函数链？

当我们想要在单个构造函数中执行多个任务，而不是为每个任务在构造函数中编写代码时，就会使用这个过程。通过为每个任务创建一个单独构造函数并让它们成链，使程序具有可读性。

## 构造函数的需要

假设有五个任务要执行。有两种方法：在一个构造函数中执行所有任务，或者在一个构造函数中分离任务。通过使用构造函数链机制，我们可以在一个构造函数中实现多个任务。因此，当我们遇到此类问题时，我们应该使用构造函数链。通过链式调用，我们可以使程序易读易懂。

## 构造函数链的规则

- `this()` 表达式应该总是构造函数的第一行。
- 必须至少有一个不带 `this()` 关键字的构造函数。构造函数链可以按任何顺序实现。

如果改变构造函数的顺序会发生什么？什么都不会发生，构造函数链可以按任何顺序实现。Java 程序使用 `this()` 关键字演示了构造函数链以及构造函数顺序的变化。

```java
class Temp {
    // 默认构造函数 1
    Temp() {
        System.out.println("default");
    }
    // 参数化构造函数 2
    Temp(int x) {
        // 调用默认构造函数
        this();
        System.out.println(x);
    }
    // 参数化构造函数 3
    Temp(int x, int y) {
        // 调用参数化构造函数 2
        this(5);
        System.out.println(x * y);
    }
    public static void main(String[] args) {
        // 调用参数化构造函数 3
        new Temp(8, 10);
    }
}
```

输出：

```
default
5
80
```

# Java 数组（Array）

Java 数组是一个包含相似数据类型元素的对象。此外，数组的元素存储在连续的内存位置中。它是一种存储相似元素的数据结构。我们只能在 Java 数组中存储一组固定的元素。

Java 数组是基于索引的，数组的元素存储在索引 0 处，第二个元素存储在索引 1 处。与 C/C++ 不同，我们可以使用 `length` 成员获取数组的长度。在 C/C++ 中，我们需要使用 `sizeof`。在 Java 中，数组是动态创建的类的对象。Java 数组继承了 `Object` 类并实现了 `Serializable`。像 C/C++ 一样，我们也可以创建多维数组。此外，Java 提供了 C/C++ 中不具备的特性。

## 数组变量

在程序中使用数组有三个步骤：

1. 声明你的数组
2. 构造你的数组
3. 初始化你的数组

## Java 数组：引用传递（Pass by reference）

数组通过引用或原始对象的指针传递给函数。这意味着函数内部对数组执行的任何操作都会影响原始数组。

步骤 1）将以下代码复制到编辑器：

```java
class ArrayDemo {
    public static void passByReference(String a[]) {
        a[0] = "Changed";
    }
    public static void main(String[] args) {
        String [] b={"Apple", "Mango", "Orange"};
        System.out.println("Before Call " + b[0]);
        ArrayDemo.passByReference(b);
        System.out.println("After Call " + b[0]);
    }
}
```

步骤 2）保存、编译并运行代码。观察输出。

输出：

```
Before Call Apple
After Call Changed
```

# 多维数组（Multidimensional arrays）

多维数组实际上是数组的数组。要声明多维数组变量，使用另一组方括号指定每个额外的索引。

例如：`int twoD[][] = new int[4][5];`

当你为多维数组分配内存时，只需要指定第一个维度（最左侧）的内存。你可以单独分配其余维度。在 Java 中，多维数组中每个数组的长度由你控制。

示例：

```java
public class Guru99 {
    public static void main(String[] args) {
        // 创建二维数组
        int[][] twoD = new int[4][4];
        // 为其赋值三个元素
        twoD[0][0] = 1;
        twoD[1][1] = 2;
        twoD[3][2] = 3;
        System.out.print(twoD[0][0] + " ");
    }
}
```

输出：

```
1
```

二维数组。在许多应用程序中，组织信息的自然方法是使用矩形数字表格。此类表格的数学抽象是矩阵；Java 实现是多维数组。

Java 中的多维数组。要引用多维数组 `a[][]` 的第 `i` 行第 `j` 列元素，我们使用符号 `a[i][j]`；声明多维数组时增加一对括号；创建数组时，指定行数后跟列数，如下：

`double[][] a = new double[m][n];`

我们将此类数组称为 `m` 行 `n` 列数组。按照惯例，第一维是行数，第二维是列数。

默认初始化。与一维数组一样，Java 将数字数组中的所有项初始化为 0，布尔数组初始化为 `false`。多维数组的默认初始化非常有用，因为它隐藏了比一维数组更多的代码。访问多维数组中的每个元素，我们需要嵌套循环：

```java
double[][] a;
a = new double[m][n];
for (int i = 0; i < m; i++)
    for (int j = 0; j < n; j++)
        a[i][j] = 0;
```

# 内存表示

Java 将二维数组表示为“数组的数组”。一个具有 `m` 行 `n` 列的矩阵实际上是一个长度为 `m` 的数组，其中每个条目都是一个长度为 `n` 的数组。在 Java 二维数组中，我们可以使用代码 `a[i]` 来引用第 `i` 行（这是一个一维数组）。这使得不规则数组（ragged arrays）成为可能。

## 在编译时设置值

以下代码初始化了 11x4 的数组 `a[][]`：

```java
double[][] a = {
    { 99.0, 85.0, 98.0, 0.0 },
    { 98.0, 57.0, 79.0, 0.0 },
    { 92.0, 77.0, 74.0, 0.0 },
    { 94.0, 62.0, 81.0, 0.0 },
    { 99.0, 94.0, 92.0, 0.0 },
    { 80.0, 76.5, 67.0, 0.0 },
    { 76.0, 58.5, 90.5, 0.0 },
    { 92.0, 66.0, 91.0, 0.0 },
    { 97.0, 70.5, 66.5, 0.0 },
    { 89.0, 89.5, 81.0, 0.0 },
    { 0.0, 0.0, 0.0, 0.0 }
};
```

## 不规则数组

二维数组中的所有行并不要求长度相同——行长度不均匀的数组被称为不规则数组（ragged array）。不规则数组的存在使得在处理数组的代码需要更加小心。例如，以下代码打印了不规则数组的内容：

```java
for (int i = 0; i < a.length; i++) {
    for (int j = 0; j < a[i].length; j++) {
        System.out.print(a[i][j] + " ");
    }
    System.out.println();
}
```

## 矩阵操作

科学和工程中的典型应用涉及使用矩阵操作数实现各种数学运算。例如，我们可以如下相加两个 `n x n` 矩阵：

```java
double[][] c = new double[n][n];
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        c[i][j] = a[i][j] + b[i][j];
    }
}
```

同样，我们可以乘以两个矩阵。`a[]` 和 `b[]` 积中的每个条目 `c[i][j]` 是通过计算 `a[]` 的第 `i` 行与 `b[]` 的第 `j` 列之间的点积得到的。

```java
double[][] c = new double[n][n];
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        for (int k = 0; k < n; k++) {
            c[i][j] += a[i][k]*b[k][j];
        }
    }
}
```

# Java 的优缺点

## 优点

1. **简单**：与其他语言相比，Java 更容易使用、编译、调试和学习。Java 比 C++ 不复杂；因此，Java 使用自动内存分配和垃圾回收。
2. **面向对象**：允许你构建标准且可用的代码。
3. **平台无关**：Java 代码可以在任何不需要安装特殊软件的机器运行，但机器上需要存在 `JVM`。
4. **分布式计算**：分布式计算涉及多个服务器协同工作。它有助于在提供数据功能的网络上开发应用程序。
5. **安全**：Java 没有显式指针。除了这一点，它还有一个用于定义类访问权限的安全管理器。
6. **内存分配**：在 Java 中，内存被分为两个部分：堆和栈。每当我们声明变量时，`JVM` 会从栈或堆中分配内存。这有助于保存信息并轻松恢复它们。
7. **多线程**：它具有程序同时执行许多任务的潜力。

## 缺点

1. **性能**：Java 在运行时需要被解释，这使其可以在每个操作系统上运行，但同时也使得它比 C 和 C++ 等语言慢。另一方面，C++ 程序需要直接在每个操作系统上编译为二进制文件，因此运行速度更快。
2. **内存消耗**：由于 Java 程序运行在 Java 虚拟机之上，因此消耗了更多内存。
3. **成本**：由于对处理和内存有较高要求，Java 编程语言略贵。我们需要更好的硬件来运行 Java 程序。
4. **交互性较差**：Java 在与机器直接交互方面欠缺，由于缺少显式指针，对于需要与机器快速直接运行的软件来说，它的可行性较低。
5. **垃圾回收**：Java 提供了无法由程序员控制的自动垃圾回收。它没有提供 `delete()` 和 `free()` 类的方法来释放内存。

然而，尽管存在各种缺点，由于其优点，Java 仍然是最常用的编程语言之一，使其平台无关、安全且健壮的编程语言。

# 结论

Java 仍然是开发者需要掌握的“核心”编程语言。鉴于其易用性、持续更新、庞大的社区以及许多应用，Java 过去是并将继续是技术领域最流行的编程语言。
