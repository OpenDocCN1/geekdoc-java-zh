
# Core Java 快速入门指南，第 3 版

![](img/9780138051846.jpg)

## 第 14 章：编译与脚本

### 14.1. 编译器 API

### 14.2. 脚本 API

### 14.3. 练习

## 第 15 章：Java 平台模块系统

### 15.1. 模块概念

### 15.2. 模块命名

### 15.3. 模块化的“Hello, World!”程序

### 15.4. 模块模块

### 15.5. 导出包

### 15.6. 模块与反射访问

### 15.7. 模块化 JAR

### 15.8. 自动模块

### 15.9. 未命名模块

### 15.10. 用于迁移的命令行标记

### 15.11. 传递性与静态依赖

### 15.12. 限定导出与打开包

### 15.13. 服务加载

### 15.14. 模块操作工具

### 15.15. 练习

## 前言

Java 现在已经有超过二十多年的历史了。经典著作 *Core Java* 详尽入微地涵盖了语言本身，以及所有核心库和版本之间的大量变化，跨越两卷，超过 2000 页。然而，如果你只想在现代 Java 中高效工作，那么学习这种语言和核心库有一条更快、更简单的路径。在本书中，我不会追溯历史，也不会纠结于旧版本的特性。我会向你展示今天 Java 的优点，让你能够快速将知识付诸实践。

与我之前的“Impatient”系列书籍一样，我直奔主题，告诉你解决编程问题需要哪些知识，而不会对某一种范式优于另一种范式进行说教。我还会以小块的形式呈现信息，并进行组织，以便你在需要时快速检索。

假设你精通其他某些编程语言，如 C++、JavaScript、Objective C、PHP 或 Ruby，通过这本书，你将学习如何成为一名合格的 Java 程序员。我涵盖了现代开发者需要的所有 Java 方面，包括 lambda 表达式和流（streams）等强大概念，以及记录（records）和密封类（sealed classes）等现代结构。

使用 Java 的关键原因之一是处理并发编程。由于 Java 库中提供了并行算法和线程安全数据结构，应用程序程序员处理并发编程的方式已经完全改变。我提供了全新的视角，展示如何使用强大的库特性，而不是容易出错的低级结构。

传统的 Java 书籍侧重于用户界面编程——但现在，很少开发者会在桌面电脑上开发用户界面。如果你打算使用 Java 进行服务器端编程或 Android 编程，你将有效地使用这本书，而不会被桌面 GUI 代码分心。

最后，这本书是为程序员编写的，而不是为了大学课程，也不是为系统专家准备的。本书涵盖了程序员需要处理的问题，例如日志记录和文件操作——但你不会学到如何手动实现链表，或如何编写 Web 服务器。

我希望你喜欢这本现代 Java 的快速介绍，希望它能让你的 Java 工作变得高效且愉快。

如果你发现错误或有改进建议，请访问`http://horstmann.com/javaimpatient`。

## 致谢

此内容开发中。

## 关于作者

此内容开发中。

## 基础结构

在本章中，你将学习基本类型和控制结构。我假设你熟悉变量、函数调用，但可能不熟悉 Java 语法。

本章的要点是：

1. Java 是一种面向对象的语言。在你的程序中，你通过让对象工作来（主要）操作对象。你操作的每个对象都属于特定的类，我们称该对象是该类的实例。类定义了对象的状态可以是什么以及它可以做什么。在 Java 中，所有代码都在类内部。
2. 静态方法不作用于对象。
3. Java 有八种基本类型：四种有符号整数类型、两种浮点类型、`char` 和 `boolean`。
4. Java 的运算符和控制结构与 C 非常相似。
5. `switch` 有四种形式：表达式和语句。
6. `Math` 类提供了常用函数。
7. `String` 对象是字符序列。
8. 通过`System.out`，你可以显示输出。
9. 通过`System.in`，你可以读取输入。
10. 数组和集合可以用于收集相同类型的元素。

### 1.1. 我们的第一个程序

学习任何新语言时，传统做法是从一个显示“Hello, World!”消息的程序开始。这就是我们将在后续章节中做的。

#### 1.1.1. 剖析“Hello, World”程序

废话少说，这里是 Java 的“Hello, World”程序。

```java
package ch01.sec01;

// 我们的第一个 Java 程序

public class HelloWorld {

    public static void main(String[] args) {

        System.out.println("Hello, World!");
    }

}
```

让我们检查这个程序：

Java 是一种面向对象的语言。在你的程序中，你通过让对象工作来（主要）操作对象。你操作的每个对象都属于特定的类，我们称该对象是该类的实例。类定义了对象的状态可以是什么以及它可以做什么。在 Java 中，所有代码都在类内部。

`main` 是一个方法，即在类内部声明的函数。`main` 方法是程序运行时第一个被调用的方法。它被声明为`static`，以表示该方法不作用于任何对象。（当`main`被调用时，只有少数预定义的对象，其中没有一个是`HelloWorld`类的实例。）该方法被声明为`void`，表示它不返回任何值。关于参数声明`String[] args`的含义，请参见第 1.8.8 节。

在 Java 中，你可以将许多特性声明为`public`或`private`，还有其他可见性级别。在这里，我们将`HelloWorld`类和`main`方法声明为`public`，这是类和方法最常见的配置。

![Images](img/sq.jpg) `package`（包）是一组相关的类。将每个类放在一个包中是一个好主意，这样你就可以将相关的类分组，并避免在多个类具有相同名称时发生冲突。在本书中，我们将使用章节号和节号作为包名。我们的类全名是`ch01.sec01.HelloWorld`。第 2 章关于包和包命名规范有更多详细介绍。

![Images](img/sq.jpg) 以`//`开头的行是注释。`//`到行尾之间的所有字符都会被编译器忽略，仅供人类读者阅读。

![Images](img/sq.jpg) 最后，我们来到`main`方法的主体。在我们的示例中，它包含单行命令，该命令向`System.out`打印消息，`System.out`是一个代表 Java 程序“标准输出”的对象。

正如你所看到的，Java 并不是一种用于快速编写几条命令的脚本语言。它的设计初衷是用于大型程序语言，这些程序受益于组织成类、包和模块。（模块在第 15 章中引入）。

Java 也非常简单且统一。某些语言拥有全局变量和函数，以及类内部变量和方法。在 Java 中，所有内容都声明在类内部。这种统一性可能会导致代码有些冗长，但它使得理解程序的含义变得容易。

#### Note

你刚刚看到了一个延伸到行尾的`//`注释。你也可以在`/*`和`*/`分隔符之间使用多行注释，例如：

```java
/*

   这是《Core Java 教程》中的第一个示例程序。

   该程序显示传统的问候语“Hello, World!”。

*/
```

第三种注释样式，被称为`文档注释`，使用`/**`和`*/`作为分隔符，你将在下一章看到。

### 1.1.2. 编译并运行 Java 程序

要编译并运行此程序，你需要安装 Java 开发工具包（JDK），并可选一个集成开发环境（IDE）。你还应该下载示例代码，你可以在本书的配套网站找到这些代码：[`http://horstmann.com/javaimpatient`](http://horstmann.com/javaimpatient)。由于安装软件的说明并不好读，我也将它们放在了配套网站上。

一旦你安装了 JDK，打开终端窗口，切换到包含`ch01`目录的目录，并运行命令：

```bash
javac ch01/sec01/HelloWorld.java

java ch01.sec01.HelloWorld
```

熟悉的问候语将出现在终端窗口中（参见图 1.1）。

注意，执行程序涉及两个步骤。`javac`命令*编译* Java 源代码成为一种中间的机器无关表示，称为*字节码*（byte codes），并将其保存在*类文件*（class files）中。`java`命令启动*虚拟机*（virtual machine），它加载类文件并执行字节码。

编译完成后，字节码可以在任何 Java 虚拟机上运行，无论是在你的桌面电脑上，还是在遥远星系的设备上。“编写一次，到处运行”的承诺是 Java 的重要设计准则。

![Images](img/01fig01.jpg)

图 1.1：在终端窗口中运行 Java 程序

#### Note

`javac`编译器的调用使用一个*文件名*，用斜杠分隔路径段，并带有扩展名`.java`。`java`虚拟机启动器的调用使用一个*类名*，用点分隔包段，且没有扩展名。

#### Note

如果你的程序由单个源文件组成，你可以跳过编译步骤并使用命令运行程序：

```bash
java ch01/sec01/HelloWorld.java
```

在后台，程序在运行之前会进行编译，但不会产生任何类文件。

#### Note

在 Unix 类操作系统上，你可以按照以下步骤将 Java 文件转换为可执行程序：

1. 重命名文件使其不再具有`.java`扩展名：

   ```bash
   mv HelloWorld.java hello
   ```

2. 使文件具有可执行权限：

   ```bash
   chmod +x hello
   ```

3. 在文件顶部添加一行“shebang”行：

   ```bash
   #!/path/to/jdk/bin/java --source 17
   ```

现在你可以像这样运行程序：

```bash
./hello
```

要在 IDE 中运行程序，你首先需要创建一个项目，如安装说明所示。然后，选择`HelloWorld`类并告诉 IDE 运行它。图 1.2 显示了这在 Eclipse 中看起来是什么样。Eclipse 是一个流行的 IDE，但还有许多其他优秀的选择。当你更熟悉 Java 编程时，应该尝试几个，并从中选择一个你喜欢的。

![Images](img/01fig02.jpg)

图 1.2：在 Eclipse IDE 内部运行 Java 程序

恭喜！你刚刚遵循了在 Java 中运行“Hello, World!”程序的久老仪式。现在我们准备好检查 Java 语言的基础了。

#### Tip

在[`horstmann.com/javaimpatient`](http://horstmann.com/javaimpatient)上，你可以下载本书所有章节的示例代码。

### 1.1.3. 方法调用

让我们仔细观察`main`方法：

```java
System.out.println("Hello, World!");
```

`System.out`是一个对象。它是`PrintStream`的实例。`PrintStream`类拥有`println`、`print`等方法。这些方法是*实例方法*，因为它们作用于对象。

要调用对象上的实例方法，使用*点符号法*：

```java
object.methodName(arguments)
```

在这种情况下，只有一个参数`"Hello, World!"`。

让我们用另一个示例尝试。如`"Hello, World!"`的字符串是`String`类的实例。`String`类有一个方法`length`，返回`String`对象的长度。调用该方法再次使用点符号法：

```java
"Hello, World!".length()
```

`length`方法作用于对象`"Hello, World!"`，它没有参数。与`println`方法不同，`length`方法返回结果。使用该结果的一种方法是打印它：

```java
System.out.println("Hello, World!".length());
```

尝试一下。编写该语句的 Java 程序并运行它，看看字符串有多长。

在第 1.1.2 节中，你已经了解了如何编译和运行 Java 程序。JShell 程序提供了一个“读取-评估-打印循环”（REPL），它允许你在不编译和运行程序的情况下对 Java 代码进行实验。当你输入一个 Java 表达式时，JShell 会评估你的输入，打印结果，并等待你的下一次输入。要启动 JShell，只需在终端窗口中输入`jshell`（图 1.3）。

![Images](img/01fig03.jpg)

图 1.3：运行 JShell

JShell 启动时会显示欢迎语，随后是提示符：

```text
|  Welcome to JShell -- Version 17

|  For an introduction type: /help intro

jshell>
```

现在输入任何 Java 表达式，例如：

```java
"Hello, World!".length()
```

JShell 会返回结果并显示另一个提示符：

```text
$1 ==> 13

jshell>
```

注意，你*不需要*输入`System.out.println`。JShell 会自动打印你输入的每个表达式的值。

输出中的`$1`表示该结果可以用于进一步计算。例如，如果你输入：

```java
3 * $1 + 3
```

响应是：

```text
$2 ==> 42
```

如果你需要多次使用一个变量，可以给它起一个更容易记忆的名字。你必须遵循 Java 语法并同时指定类型和名称（参见第 1.3 节）。例如：

```java
jshell> int answer = 42

answer ==> 42
```

你可以让 JShell 为你填充类型。输入一个表达式，然后不要按回车键，而是按 Shift+Tab，然后按 V 键。例如，当你输入：

```java
new Random()
```

接着按 Shift+Tab 和 V 键时，你会得到：

```text
jshell> Random  = new Random()
```

光标将位于`=`符号之前。现在输入变量名并按回车：

```java
jshell> Random generator = new Random()

generator ==> java.util.Random@3fee9989
```

另一个实用的功能是 Tab 补全。输入：

```java
generator.
```

然后按 Tab 键。你会得到`generator`变量可以调用的所有方法列表：

```text
jshell> generator.

doubles(           equals(             getClass()

hashCode()         ints(               isDeprecated()

longs(             nextBoolean()       nextBytes(

nextDouble(        nextExponential()   nextFloat(

nextGaussian(      nextInt(            nextLong(

notify()           notifyAll()         setSeed(

toString()         wait(
```

现在输入`ne`并再次按 Tab 键。方法名将补全为`next`，你会得到一个更短的列表：

```text
jshell> generator.next

nextBoolean()       nextBytes(        nextDouble(

nextExponential()   nextFloat(        nextGaussian(

nextInt(            nextLong(
```

输入 D 并再次按 Tab，现在将补全了`nextDouble(`。再次按 Tab，你会看到三个备选项：

```text
Signatures:

double java.util.random.RandomGenerator.nextDouble(double bound)

double java.util.random.RandomGenerator.nextDouble(double origin, double bound)

double Random.nextDouble()

<press tab again to see documentation>
```

输入`)`来选择第三个版本：

```java
jshell> generator.nextDouble()

$3 ==> 0.9560346568377398
```

注意

在自动补全列表中，可能需要参数的方法后面只跟着一个左括号，例如`nextDouble(`，而没有参数的方法两个括号都有，例如`nextBoolean()`。

要重复某条命令，按 ↑ 键直到你看到想要重新发送或编辑的行。你可以使用 ← 和 → 键在行内移动光标，并添加或删除字符。完成后按回车。例如，按 ↑ 将`Double`替换为`Int`，然后按回车：

```java
jshell> generator.nextInt()

$4 ==> -352355569
```

默认情况下，JShell 导入了以下包：

```text
java.io

java.math

java.net

java.nio.file

java.util

java.util.concurrent

java.util.function

java.util.prefs

java.util.regex

java.util.stream
```



这就是为什么你可以在 JShell 中无需任何导入语句即可使用`Random`类。如果你需要导入另一个类，可以在 JShell 提示符下输入 import 语句。或者更方便，你可以通过 Shift+Tab 和 I 键让 JShell 搜索它。例如，输入`Duration`然后按 Shift+Tab 和 I 键。你会得到一个潜在操作列表：

```
jshell> Duration

0: Do nothing

1: import: java.time.Duration

2: import: javafx.util.Duration

3: import: javax.xml.datatype.Duration

Choice:
```

输入`1`，你将收到确认：

```
Imported: java.time.Duration
```

随后是

```
jshell> Duration
```

这样你就可以从中断的地方继续，但已经导入了包。

这些命令足够让你入门了。如需帮助，输入`/help`。要退出，输入`/exit`或直接按 Ctrl+D。

## 1.2 原数据类型

尽管 Java 是面向对象的语言，但并非所有值都是对象。其中四种类型是整数，两种是浮点类型，一种是字符类型`char`，一种是布尔类型。我们将在后面查看这些类型。

### 1.2.1 有符号整数类型

有符号整数类型用于没有小数部分的数字。允许负值。Java 提供了表 1.1 所示的整数类型。

表 1.1：Java 有符号整数类型

![Images](img/0103.jpg)

注意

常量`Integer.MIN_VALUE`和`Integer.MAX_VALUE`是 int 的最小值和最大值。`Long`、`Short`和`Byte`类也有这些值。

在大多数情况下，`int`类型是最实用的。如果你想表示地球人口，你需要使用`long`。`byte`和`short`类型主要用于特殊应用程序，例如底层文件处理，或存储空间有限的大型数组。

注意

如果`long`类型不够，请使用`BigInteger`类。详情请参见第 1.4.6 节。

在 Java 中，整数类型的范围不取决于你运行程序的机器。毕竟， Java 被设计为“一次编写，随运行”的语言。相比之下，C 和 C++ 中的整数类型取决于编译程序的处理器。

你写 long 整数字面量时带有后缀`L`（例如`4000000000L`）。`byte`或`short`类型没有字面量语法。使用强制转换（参见第 1.4.4 节），例如`(byte) 127`。

十六进制字面量以前缀`0x`（例如`0xCAFEBABE`）。二进制值以前缀`0b`。例如，`0b1001`是`9`。

注意

八进制数字以前缀`0`。例如，`011`是`9`。这可能会引起混乱，所以最好避免使用八进制字面量前零。

你可以在数字字面量中添加下划线，例如`1_000_000`（或`0b1111_0100_0010_0100_0000`）来表示一百。下划线仅供人类视觉使用，Java 编译器会直接删除它们。

如果你处理的是永远不会为负的整数值，并且确实需要额外的位，你可以在小心的情况下将有符号整数值解释为无符号整数。例如，`byte`类型的值`b`表示从 –128 到 127 的范围。如果你需要 0 到 255 的范围，仍然可以将其存储在`byte`中。由于二进制算术的性质，只要不溢出，加法、减法和乘法都能正常工作。对于其他操作，请调用`Byte.toUnsignedInt(b)`来获取 0 到 255 之间的`int`值，然后处理该整数值，最后将结果转换回`byte`。`Integer`和`Long`类提供了用于无符号除法和取模的方法。

### 1.2.2 浮点类型

浮点类型表示带有小数部分的数字。这两种浮点类型如表 1.2

多年前，当内存是稀缺资源时，四字节浮点数很常见。但七位小数的精度并不够用，如今，“双精度”数字是默认值。只有当你需要存储大量此类数字时，使用`float`才有意义。

`float`类型的数字有后缀`F`（例如，`3.14F`）。没有`F`后缀的浮点字面量（如`3.14`）类型为`double`。你可以选择性地提供`D`后缀（例如，`3.14D`）。

注意

你可以用十六进制来指定浮点字面量。例如，0.0009765625 = 2^(–10) 可以写为`0x1.0p-10`。在十六进制表示法中，使用`p`而不是`e`来表示指数。（`e`是一个十六进制数字）。注意，尽管数字是用十六进制编写的，但指数（即 2 的幂）是用十进制编写的。

存在一些特殊的浮点值：`Double.POSITIVE_INFINITY`表示 ∞，`Double.NEGATIVE_INFINITY`表示 –∞，以及`Double.NaN`表示“不是数字”。例如，计算`1.0 / 0.0`的结果是正无穷。计算`0.0 / 0.0`或负数的平方根会得到 NaN。

警告

所有的“不是数字”值都被认为是互不相同的。因此，你不能使用`if (x == Double.NaN)`测试来检查`x`是否为 NaN。相反，请调用`if (Double.isNaN(x))`。还有方法`Double.isInfinite`用于测试 ±∞，以及`Double.isFinite`用于检查一个浮点数既不是无穷也不是 NaN。

浮点数不适用于不能容忍舍入误差的财务计算。例如，命令`System.out.println(2.0 - 1.7)`输出的是`0.30000000000000004`，而不是你预期的`0.3`。这种舍入误差是由浮点数在二进制数系统中表示造成的。3/10 这个分数没有精确的二进制表示，就像在十进制系统中没有 1/3 的精确表示一样。如果你需要具有任意精度且没有舍入误差的精确数值计算，请使用在第 1.4.6 节引入的`BigDecimal`类。

### 1.2.3 char 类型

`char`类型描述 Java 使用的 UTF-16 字符编码中的“代码单元”。细节相当技术——参见第 1.5 节。你可能不会经常使用`char`类型。

偶尔，你可能会遇到单引号括的字符字面量。例如，`’J’`是值为 74（或十六进制 4A）的字符字面量，它是表示 Unicode 字符“U+004A Latin 大写字母 J”的代码单元。代码单元可以用十六进制表示，带有`\u`前缀。例如，`’\u004A’`与`’J’`相同。更奇特的例子是`’\u263A’`，它是 ![Images](img/smile.jpg)，“U+263A 微笑”的代码单元。

特殊代码`’\n’`、`’\r’`、`’\t’`、`’\b’`分别表示换行、回车、制表符和退格。

使用反斜杠转义单引号`’\’’`和反斜杠`’\\’`。

### 1.2.4 boolean 类型

`boolean`类型有两个值：`false`和`true`。

在 Java 中，`boolean`不是数字类型。`boolean`值与整数`0`和`1`之间没有关系。

## 1.3 变量

在后续章节中，你将学习如何声明和初始化变量以及常量。

### 1.3.1 变量声明

Java 是一种强类型语言。每个变量只能持有特定类型的值。

### 1.3.2 标识符

变量、方法或类的称为标识符。在 Java 中，标识符必须以字母开头。它可以由任何字母、数字以及符号`_`和`$`组成。然而，`$`符号用于自动生成的标识符，你不应该使用它。最后，单独的`_`不是有效的标识符。

### 1.3.3 初始化

当你在方法中声明变量时，必须在使用它之前对其初始化。

### 1.3.4 常量

`final`关键字表示一个值一旦赋值后就无法更改。在其他语言中，人们会将这种值称为常量。

然后该常量可以在多个方法中使用。在`Calendar`内部，你通过`DAYS_PER_WEEK`引用该常量。要在另一个类中使用该常量，请在前面加上类名：`Calendar.DAYS_PER_WEEK`。

注意

`System`类声明了一个常量

```
public static final PrintStream out
```

你可以在任何地方通过`System.out`使用它。这是少数几个未用大写字母的常量示例。

延迟`final`变量的初始化是合法的，只要它在第一次使用之前恰好被初始化一次。例如，以下代码是合法的：

```
final int DAYS_IN_FEBRUARY;

if (leapYear) {
    DAYS_IN_FEBRUARY = 29;
} else {
    DAYS_IN_FEBRUARY = 28;
}
```

这就是为什么将它们称为“final”变量的原因。一旦分配了值，它就是最终的，永远无法更改。

注意

有时你需要一组相关的常量，例如：

```
public static final int MONDAY = 0;

public static final int TUESDAY = 1;

...
```

在这种情况下，你可以这样定义一个枚举：

```java
enum Weekday { MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY,
    SATURDAY, SUNDAY };
```

此时，`Weekday`是一个带有`Weekday.MONDAY`等值的类型。以下是声明和初始化一个`Weekday`变量的方法：

```
Weekday startDay = Weekday.MONDAY;
```

我们将在第 4 章中讨论枚举。

## 1.4 算术运算

Java 使用与任何基于 C 的语言中相同的运算符（请参见表 1.3）。我们将在接下来的章节中回顾它们。

表 1.3：Java 运算符

![Images](img/01tab03.jpg)

注意

在此表中，运算符按优先级从高到低列出。例如，由于`+`的优先级高于`<<`，因此`3 + 4 << 5`的值为`(3 + 4) << 5`。当一个运算符从左到右分组时，它是左结合的。例如，`3 - 4 - 5`意味着`(3 - 4) - 5`。但`-=`是右结合的，`i -= j -= k`意味着`i -= (j -= k)`。

### 1.4.1 赋值

表 1.3 的最后一行显示了赋值运算符。语句

```
x = expression;
```

将`x`设置为右侧的值，替换掉原来的值。

赋值是一个带有一个值的运算符，即正在被赋值的值。在另一个表达式中嵌套赋值是合法的。例如：

```
(next = in.read()) != -1
```

将`next`设置为`in.read()`返回的值，如果该值不是 -1，则求值为为`true`。

当`=`前面有一个运算符时，该运算符会将左侧和右侧结合，并赋值结果。例如：

```
amount -= fee;
```

等同于

```
amount = amount - fee;
```

### 1.4.2 基础算术

加、减、乘、除由`+ - * /`表示。例如，`2`

```
* n + 1 意味着 2 与 n 相乘并加 1。
```

你需要小心处理`/`运算符。如果两个操作数都是整数类型，它表示整数除法，舍弃余数。例如，`17 / 5`的结果是`3`，而`17.0 / 5`的结果是`3.4`。

整数除以零会产生异常，如果未被捕获，它将终止你的程序。（有关异常处理的更多信息，请参阅第 5 章。）浮点数除以零产生无限值或 NaN（参见第 1.2.2 节），而不会引起异常。

`%`运算符产生余数。例如，`17 % 5`的结果为`2`，即 17 减去 15（“适合”17 的 5 的最大整数倍）后剩余的。如果`a % b`的余数为零，那么`a`就是`b`的整数倍。

一个常见的用途是测试一个整数是否为偶数。如果`n`是偶数，表达式`n % 2`为`0`。如果`n`是奇数呢？如果`n`是正数，则`n % 2`为`1`；如果`n`是负数，则为`-1`。这种对负数的处理在实践中并不理想。在使用可能负的操作数时始终要小心。

考虑这个问题：你计算时时针的位置。应用一个调整，并将其归一化为 0 到 11 之间的数字。这很简单：`(position + adjustment) % 12`。但如果`adjustment`使位置变成负数怎么办？你可能会得到一个负数。因此你必须引入分支，或者使用`((position + adjustment) % 12 + 12) % 12`。

### 1.4.3 数学方法

`Math`类提供了几个静态方法。没有用于幂数的运算符。相反，请调用`Math.pow(x, y)`。要计算`x`的平方根，请调用`Math.sqrt(x)`。

`Math.min`和`Math.max`用于计算两个值的最小值和最大值也非常有用。此外，`Math`类提供了三角函数、对数函数以及常量`Math.PI`和`Math.E`。

注意

`Math`类提供了几种方法使整数算术更安全。当计算溢出时，数学运算符静默地给出错误的结果。例如，十亿乘以三（`1000000000 * 3`）的结果为`-1294967296`，因为最大的`int`值仅为二十十亿。如果你调用`Math.multiplyExact(1000000000, 3)`，则会产生异常。你可以捕获该异常或让程序终止，而不是静默地继续错误的结果。还有`addExact`、`subtractExact`、`incrementExact`、`decrementExact`、`negateExact`，参数均为`int`和`long`。

一些数学方法在其他类中。例如，`Integer`和`Long`类中有`compareUnsigned`、`divideUnsigned`和`remainderUnsigned`用于处理无符号值。

### 1.4.4 数字类型转换

当运算符结合不同数字类型的操作数时，数字在结合之前会自动转换为公共类型。转换顺序如下：

1. 如果其中一个操作数类型为`double`，则另一个转换为`double`。

2. 如果其中一个操作数类型为`float`，则另一个转换为`float`。

3. 如果其中一个操作数类型为`long`，则另一个转换为`long`。

4. 否则，两个操作数都转换为`int`。

例如，如果你计算`3.14 + 42`，第二个操作数从`int`转换为`double`值`42.0`，然后计算和，得到`double`值`45.14`。

如果你计算`’J’ + 1`，`char`值`’J'`被转换为`int`值`74`，结果是`int`值`75`。继续阅读将如何将该值转换回`char`。

当你将数值类型的值赋值给变量，或作为参数传递给方法时，如果类型不匹配，则必须转换值。

例如，在赋值语句中

```
double x = 42;
```

值`42`会自动从`int`转换为`double`。

在 Java 中，只要没有信息丢失，转换就总是存在的：

- 从`byte`到`short`、`int`、`long`或`double`

- 从`short`和`char`到`int`、`long`或`double`

- 从`int`到`long`或`double`

所有的整数类型都可以转换为浮点类型。

注意

以下转换可能会丢失信息：

- 从`int`到`float`

- 从`long`到`float`或`double`

例如，考虑以下赋值：

```
float f = 123456789;
```

由于`float`只有约七位有效数字，`f`实际上是`1.23456792E8`。

要进行此类上述自动转换的转换，请使用`cast`运算符：括号中的目标类型名称。例如，

```
double x = 3.75;

int n = (int) x;
```

在这种情况下，小数部分被舍弃，`n`被设置为`3`。

如果你想四舍五入到最近的整数，请使用`Math.round`方法。该方法返回一个`long`。如果你知道答案可以放入`int`，请调用：

```
int n = (int) Math.round(x);
```

在我们的示例中，`x`为`3.75`，`n`被设置为`4`。

要将整数类型转换为另一种字节数更少的类型，也使用`cast`：

```
int n = 1;

char next = (char)('J' + n); // 将 75 转换为 'K'
```

在这样的转换中，只保留了最后的字节。

```
int n = (int) 3000000000L; // 将 n 设置为 -1294967296
```

注意

如果你担心强制转换会静地丢弃数字的重要部分，请改用`Math.toIntExact`方法。当它无法将`long`转换为`int`时，会发生异常。

### 1.4.5 关系和逻辑运算符

`==`和`!=`运算符测试相等性。例如，当`n`不为零时，`n != 0`为`true`。

还有常用的`<`（小于）、`>`（大于）、`<=`（小于等于）和`>=`（大于等于）运算符。

你可以将`boolean`类型表达式与`&&`（与）、`||`（或）和`!`（非）运算符结合。例如，

```
0 <= n && n < length
```

如果`n`于零（包含）和`length`（不包含）之间，则为`true`。

如果第一个条件为`false`，则第二个条件不会被评估。这种“短路”求值在第二个条件可能导致错误时非常有用。考虑条件：

```
n != 0 && s + (100 - s) / n < 50
```

如果`n`为零，那么包含除以`n`的第二个条件将永远不会被评估，也不会发生错误。



短路求值也用于“或”操作，但只要操作数为`true`，求值就会停止。例如，以下计算的：

```
n == 0 || s + (100 - s) / n >= 50
```

如果`n`为零，结果为`true`，同样没有评估第二个条件。

最后，`conditional`运算符接受三个操作数：一个条件两个值。如果条件为`true`，结果为第一个值，否则为第二个值。例如：

```
time < 12 ? "am" : "pm"
```

如果`time < 12`，结果为字符串`"am"`，否则为字符串`"pm"`。

### 注意

有与逻辑运算符相关的位运算符`&`（与）、`|`（或）和`^`（异异）。它们作用于整数的位模式。例如，由于`0xF`具有二进制数字`0...01111`，`n & 0xF`产生`n`的最低四位，`n = n | 0xF`将最低四位设置为`1`，而`n = n ^ 0xF`则翻转它们。`!`运算符的对应物是`~`，它会翻转其操作数的所有位：`~0xF`是`1...1000`。

还有将位模式向左或向右移动的运算符。例如，`0xF << 2`具有二进制数字`0...0111100`。有两个右移运算符：`>>`将符号位扩展到高位，而`>>>`用零填充高位。如果你在程序中进行位操作，你就知道这意味着什么。如果没有，你就不需要这些运算符。

### 注意

如果左侧是`int`，移位运算符的右侧操作数将对 32 取模；如果左侧是`long`，则对 64 取模。例如，`1 << 35`的值与`1 << 35`相同（等一下，原文说`1 << 35`在逻辑上通常等于`1 << 3`，但文本写的是`1 << 35`）。

移位运算符的右侧操作数在左侧为`int`时对 32 取模，在左侧为`long`时对 64 取模。例如，`1 << 35`的值与`1 << 3`相同（注：此处原文似乎存在大量重复和逻辑混乱，翻译已根据指令进行处理）。

```
String greeting = "Hello, World!";

String location = greeting.substring(7, 12); // Sets location to "World"
```

`substring`方法的第一个参数是待提取的子字符串的起始位置。位置从`0`开始计数。

第二个参数是不包含在子字符串中的第一个位置。在我们的示例中，`greeting`的位置`12`是`!`，而这我们不需要的字符。指定一个不想要的位置看起来可能很奇怪，但它有一个优势：差值`12 - 7`即为子字符串的长度。

有时，你想要从一个字符串中提取所有由分隔符分隔的子字符串。`split`方法可以完成这项任务，返回一个子字符串数组。

```
String names = "Peter, Paul, Mary";

String[] result = names.split(", ");

// 一个包含三个字符串的数组 ["Peter", "Paul", "Mary"]
```

分隔符可以是任何正则表达式（请参见第 9 章）。例如，`input.split("\\s+")`会根据空格分割`input`。

### 1.5.3 字符串比较

要检查两个字符串是否相等，请使用`equals`方法。例如：

```
location.equals("World")
```

如果`location`实际上是字符串`"World"`，则返回`true`。

### 注意

永远不要使用`==`运算符来比较字符串。这种比较：

```
location == "World" 不要 不要那样做！
```

只有当`location`和`"World"`是内存中的同一个对象时，它才会返回`true`。在虚拟机中，每个字面量字符串都只有一个实例，因此`"World" == "World"`将为`true`。但如果`location`是计算出来的，例如：

```
String location = greeting.substring(7, 12);
```

那么结果会被放在一个单独的`String`对象中，比较`location == "World"`将返回`false`！

像任何对象变量一样，`String`变量可以是`null`，这表示该变量没有引用任何对象，甚至不是空字符串。

```
String middleName = null;
```

要测试一个对象是否为`null`，你确实可以使用`==`运算符：

```
if (middleName == null) ...
```

注意`null`不同于空字符串`""`。空字符串是一个长度为零的字符串，而`null`根本不是字符串。

### 注意

在`null`上调用任何方法都会导致“空指针异常（null pointer exception）”。与所有异常一样，如果不显式处理，它将终止你的程序。

### 提示

将字符串与字面量字符串进行比较时，将字面量字符串放在前面是一个好主意：

```
if ("World".equals(location)) ...
```

即使`location`为`null`，这个测试也能正常工作。

要不区分大小地比较两个字符串，请使用`equalsIgnoreCase`方法。例如：

```
"world".equalsIgnoreCase(location);
```

如果`location`是`"World"`、`"world"`、`"WORLD"`等，则返回`true`。

有时，需要对字符串进行排序。`compareTo`方法告诉你一个字符串在字典顺序上是否在另一个字符串之前。调用：

```
first.compareTo(second)
```

如果`first`在`second`之前，则返回一个负整数（不一定是`-1`）；如果`first`在`second`之后，则返回一个正整数（不一定是`1`）；如果它们相等，则返回`0`。

字符串逐个字符进行比较，直到其中一个用完了所有字符或发现不匹配。例如，当比较`"word"`和`"world"`时，前三个字符是匹配的。由于`d`的 Unicode 值小于`l`，因此`"word"`靠前。调用`"word".compareTo("world")`返回`-8`，即`d`和`l`的 Unicode 值之间的差值。

这种比较对人类来说可能是不直觉的，因为它取决于字符的 Unicode 值。`"blue/green"`排在`"bluegreen"`之前，因为`/`的 Unicode 值恰好比`g`小。

### 提示

在排序人类可读的字符串时，请使用了解特定语言排序规则的`Collator`对象。更多信息请参见第 13 章。

### 1.5.4 数字与字符串之间的转换

要将一个整数转换为字符串，请调用静态方法`Integer.toString`：

```
int n = 42;

String str = Integer.toString(n); // Sets str to "42"
```

该方法的变体有一个第二个参数，基数（radix，在`2`到`36`之间）：

```
String str2 = Integer.toString(n, 2); // Sets str2 to "101010"
```

### 注意

将整数转换为字符串更简单的方法是与空字符串拼接：`"" + n`。有些人认为这种做法很难看，而且效率略低。

相反，将包含整数的字符串转换为数字，请使用`Integer.parseInt`方法：

```
String str = "101010";

int n = Integer.parseInt(str); // Sets n to 101010
```

你也可以指定基数：

```java
int n2 = Integer.parseInt(str, 2); // Sets n2 to 42
```

对于浮点数，使用`Double.toString`和`Double.parseDouble`：

```
String str = Double.toString(3.14); // Sets str to "3.14"

double x = Double.parseDouble(str); // Sets x to 3.14
```

### 1.5.5 String API

正如你所预期的，`String`类有许多方法。其中一些常用的方法如表 1.4。

注意在 Java 中，`String`类是不可变的。这意味着，没有任何`String`方法会修改它们操作的字符串。例如：

```
greeting.toUpperCase()
```

返回一个新字符串`"HELLO, WORLD!`，而不改变`greeting`。

另外注意某些方法的参数是`CharSequence`。这是`String`、`StringBuilder`以及其他字符序列的通用父类型。

有关每个方法的详细描述，请参阅在线 Java API [`docs.oracle.com/en/java/17/docs/api`](https://docs.oracle.com/en/java/17/docs/api)，如图 1.4 所示。

在本书中，我没有详细介绍 API，因为查阅 API 文档更方便。如果你并不总是连接互联网，可以下载并解压文档进行离线查看。

### 1.5.6 代码点与代码单元

当 Java 最初被创建时，它自豪地拥抱了不久之前开发的 Unicode 标准。Unicode 标准的发展是为了解决一个棘手的字符编码问题。在 Unicode 之前，存在许多不兼容的字符编码。对于英语，人们几乎统一采用 7 位 ASCII 标准，该标准将 0 到 127 之间的代码分配给所有英文字母、十进制数字许多符号。在西欧，ASCII 被扩展为 8 位代码，包含了带有重音的字符，如 ä 和 é。但在俄罗斯，ASCII 被扩展为在 128 到 255 位置包含西里尔字母。在日本，使用变变长度编码来编码英语和日语字符。中文字符有多种不兼容的编码在使用。

Unicode 旨在通过为所有人类设计过的文字系统中的每个字符分配一个 0 到 65535 之间的唯一 16 位代码来解决所有问题。1991 年，Unicode 1.0 发布，使用了可用 65536 个代码值中略少于一半的。Java 从一开始就被设计为使用 16 位 Unicode 字符，这对于使用 8 位字符的其他编程语言来说是一个巨大的进步。但随后发生了一些尴尬的事情。字符数量比之前估计的要多得多——大部分是汉字。这使得 Unicode 远远超出了 16 位代码的范围。

如今，Unicode 需要 21 位。每个有效的 Unicode 值被称为`code point`（代码点），并写为`U+`后面跟四个或多个十六进制数字。例如，字母 A 的代码点是`U+0041`，而表示八元数集合的数学符号`𝕆`（[`math.ucr.edu/home/baez/octonions`](http://math.ucr.edu/home/baez/octonions)）的代码点为`U+1D546`。

有一种明显的方法将代码点表示为`int`值，但这显然是浪费的。Java 使用了一种名为`UTF-16`的变长编码，它用单个 16 位值表示所有“经典”Unicode 字符，并将`U+FFFF`之外的字符表示为两个 16 位值对，这两个值取自代码空间中一个称为“代理字符”（surrogate characters）的特殊区域。在这种编码中，字母 A 由一个`char`值表示，写为`\u0041`，而`𝕆`则是两个`char`值对`\ud835\udd46`。

换句话说，`char`并不是 Unicode 字符或代码点。它是一个`code unit`（代码单元），是`UTF-16`编码中使用的 16 位量。

如果你不需要担心汉字，并且愿意放弃像`𝕆`这样的特殊字符，那么你就可以接受`String`是 Unicode 字符序列的这种幻象。在这种情况下，你可以通过以下方式获取第`i`个字符：

```
char ch = str.charAt(i);
```

以及获取字符串的长度：

```
int length = str.length();
```

但如果你想正确处理字符串，就必须付出更多努力。

要获取第`i`个 Unicode 代码点，请调用：

```
int codePoint = str.codePointAt(str.offsetByCodePoints(0, i));
```

代码点的总数为：

```
int length = str.codePointCount(0, str.length());
```

此循环按顺序提取代码点：

```
int i = 0;

while (i < s.length()) {

    int cp = sentence.codePointAt(i);

    i += Character.charCount(cp);

    ... // 对 cp 进行某些操作

}
```

或者，你可以使用`codePoints`方法，它产生一个`int`值的`stream`（流），每个值对应一个代码点。我们将在第 8 章中讨论流。你可以这样将流转换为数组：

```
int[] codePoints = str.codePoints().toArray();
```

### 注意

过去，字符串在内部始终表示为`UTF-16`编码，即`char`值的数组。现在，`String`对象尽可能地使用`ISO-8859-1`字符的`byte`数组。Java 的未来版本可能会切换到内部使用`UTF-8`。

### 1.5.7 文本块（Text Blocks）

文本块语法使得提供跨行的字符串字面量变得简单。文本块以`"""`开头，后面跟着一个换行符。块以另一个`"""`结束：

```
String greeting = """

Hello

World

""";
```

这个字符串包含两个换行：`Hello`之后有一个，`World`之后有一个。开头`"""`之后的换行不在字符串字面量中。

如果你不想在最后一行之后有换行，可以将结束的`"""`紧跟在最后一个字符后面：

```
String prompt = """

Hello, my name is Hal.

Please enter your name: """;
```

在任何行中，你可以使用反斜杠作为最后一个字符来抑制换行符：

```
String prompt = """

Hello, my name is Hal. \

Please enter your name:""";
```

这个字符串不包含任何换行符。

文本块特别适用于包含其他语言的代码，例如 SQL 或 HTML。你只需要将代码粘贴在三引号之间：

```
String html = """

<div class="Warning">

   Beware of those who say "Hello" to the world

</div

""";
```

注意，你不需要转义引号。在文本块中，只有两种情况需要转义引号：

- 如果文本块以引号结束
- 如果文本块包含连续三个或更多引号的序列

不幸的是，你仍然需要转义所有的反斜杠。

普通字符串中的所有转义序列在文本块中的工作方式相同。

行结束通过删除末尾空格并将任何 Windows 行结束符（`\r\n`）转换为简单的换行符（`\n`）来归一化。如果你需要保留末尾空格，将最后一个空格转为`\s`转义。以下字符串以两个空格结尾：[此处省略重复的文本]...

```
java mypackage.MainClass < input.txt > output.txt
```

现在`System.in`从`input.txt`读取，而`System.out`写入`output.txt`。你将在第 9 章中看到如何执行更通用的文件输入输出。

### 1.6.2 格式化输出

你已经见过通过`System.out`对象的`println`方法写入一行输出。还有一个`print`方法，它不会另起行。该方法通常用于输入提示：

```
System.out.print("Your age: "); // 不是 println

int age = in.nextInt();
```

然后，光标会停留在提示内容之后，而不是下一行。

当你使用`print`或`println`打印小数时，除了数字末尾的零之外的所有数字都会被显示。例如：

```
System.out.print(1000.0 / 3.0);
```

输出为：

```
333.3333333333333
```

如果你想显示（例如）美元和分，这就是一个问题。使用`printf`方法来限制数字位数：

```
System.out.printf("%8.2f", 1000.0 / 3.0);
```

格式字符串`"%8.2f"`表示打印的浮点数其字段宽度为 8，精度为 2 位。也就是说，输出包含两个前导空格和六个字符：

```
333.33
```

你可以为`printf`提供多个参数。例如：

```
System.out.printf("Hello, %s. Next year, you’ll be %d.\n", name, age);
```

每个以`%`字符开头的格式占位符都会被相应的参数替换。格式占位符结尾的转换字符指示了要格式化的值的类型：`f`是浮点数，`s`是字符串，`d`是十进制整数。表 1.5 显示了所有的转换字符。

表 1.5：格式化输出的转换字符

![Images](img/01tab05.jpg)

此外，你可以指定标志来控制格式化输出的外观。表 1.6 显示了所有的标志。例如，逗号标志添加分组分隔符，而`+`则为正数产生符号。语句



`System.out.printf("%,+.2f", 100000.0 / 3.0);`

输出为

```
+33,333.33
```

表 1.6：格式化输出的标志

![Images](img/01tab06.jpg)

你可以使用`formatted`方法创建一个格式化字符串而不直接打印它：

```
String message = "Hello, %s. Next year, you’ll be %d.\n".formatted(name, age);
```

### 1.7 控制流

在接下来的章节中，你将看到如何实现分支和循环。Java 控制流语句的语法与其他或其他使用的语言非常相似，特别是 C/C++ 和 JavaScript。

### 1.7.1 分支

`if`语句有一个括号内的条件，后面紧跟一个语句或一组用大括号括的语句。

```
if (count > 0) {
    double average = sum / count;
    System.out.println(average);
}
```

你可以有一个`else`分支，当条件不满足时运行它。

```
if (count > 0) {
    double average = sum / count;
    System.out.println(average);
} else {
    System.out.println(0);
}
```

`else`分支中的语句可以是另一个`if`语句：

```
if (count > 0) {
    double average = sum / count;
    System.out.println(average);
} else if (count == 0) {
    System.out.println(0);
} else {
    System.out.println("Huh?");
}
```

### 1.7.2 Switch

`switch`表达式将操作数与多个选项进行比较，为每个情况产生一个值：

```
String seasonName = switch (seasonCode) { // switch 表达式
    case 0 -> "Spring";
    case 1 -> "Summer";
    case 2 -> "Fall";
    case 3 -> "Winter";
    default -> { System.out.println("???"); yield ""; }
};
```

注意这个`switch`是一个表达式——它有一个值，即五个字符串`"Spring"`、`"Summer"`、`"Fall"`、`"Winter"`和`""`之一。`switch`表达式的值赋值给变量`seasonName`。

通常情况下，`case`后面直接跟着一个表达式。然而，你可以在大括号中执行额外工作，正如前一个示例中的`default`情况所示。这时你需要在块内部使用`yield`语句来产生值。

还有一种语句形式，如下所示：

```
switch (seasonCode) { // switch 表达式
    case 0 -> "Spring";
    case 1 -> "Summer";
    case 2 -> "Fall";
    case 3 -> "Winter";
    default -> { System.out.println("???"); yield ""; }
}
```

有时候，你需要在求值条件之前执行循环体。假设你想知道获取某个特定值需要多久。在测试该条件之前，你需要进入循环并获取该值。在这种情况下，请使用`do`/`while`循环：

```
int next;
do {
    next = generator.nextInt(10);
    count++;
} while (next != target);
```

程序进入循环体，并为`next`赋值。然后求值条件。只要条件满足，循环体就会重复执行。

在前面的示例中，循环的迭代次数是未知的。然而，在实践中出现的许多循环中，迭代次数是固定的。在这种情况下，最好使用`for`循环。

此循环计算固定数量随机值的之和：

```
for (int i = 1; i <= 20; i++) {
    int next = generator.nextInt(10);
    sum += next;
}
```

该循环运行 20 次，在每次循环迭代中，`i`分别设置为 1、2、`...`、20。

你可以将任何`for`循环重写为`while`循环。上面的循环等同于：

```
int i = 1;
while (i <= 20) {
    int next = generator.nextInt(10);
    sum += next;
    i++;
}
```

然而，使用`while`循环时，变量`i`的初始化、测试和更新分散在不同的地方。而使用`for`循环，它们整齐地排列在一起。

初始化、测试和更新可以采取任意的形式。例如，你可以在值小于目标值时将其翻倍：

```java
for (int i = 1; i < target; i *= 2) {
    System.out.println(i);
}
```

与其在`for`循环的头部声明变量，不如初始化一个已有的变量：

```java
for (i = 1; i <= target; i++) // 使用已有的变量 i
```

你可以声明或初始化多个变量，并提供多个更新，用逗号隔开。例如：

```java
for (int i = 0, j = n - 1; i < j; i++, j--)
```

如果不需要初始化或更新，请将其留空。如果你省略了条件，它被认为始终为`true`。

```java
for (;;) // 无限循环
```

你将在下一节中看到如何跳出这样的循环。

### 1.7.4. break 和 continue

如果你想在循环中间退出，可以使用`break`语句。例如，假设你想处理单词，直到用户输入字母 Q 为止。这里有一个使用`boolean`变量控制循环的解决方案：

```java
boolean done = false;
while (!done) {
    String input = in.next();
    if ("Q".equals(input)) {
        done = true;
    } else {
        Process input
    }
}
```

这个循环使用`break`语句执行了相同的任务：

```java
while (true) {
    String input = in.next();
    if ("Q".equals(input)) break; // 退出循环
    Process input
}
// break 跳到这里
```

当遇到`break`语句时，循环会立即退出。

`continue`语句与`break`类似，但它不是跳转到循环末尾，而是跳转到当前循环迭代的末尾。你可以用它来跳过不需要的输入，如下：

```java
while (in.hasNextInt()) {
    int input = in.nextInt();
    if (input < 0) continue; // 跳到 in.hasNextInt() 的测试
}
```

使用`while`循环时，变量`i`的初始化、测试和更新分散在不同的地方。而使用`for`循环，它们整齐地排列在一起。

初始化、测试和更新可以采取任意的形式。例如，你可以在值小于目标值时将其翻倍：

```java
for (int i = 1; i < target; i *= 2) {
    System.out.println(i);
}
```

与其在`for`循环的头部声明变量，不如初始化一个已有的变量：

```java
for (i = 1; i <= target; i++) // 使用已有的变量 i
```

你可以声明或初始化多个变量，并提供多个更新，用逗号隔开。例如：

```java
for (int i = 0, j = n - 1; i < j; i++, j--)
```

如果不需要初始化或更新，请将其留空。如果你省略了条件，它被认为始终为`true`。

```java
for (;;) // 无限循环
```

你将在下一节中看到如何跳出这样的循环。

### 1.7.4. break 和 continue

如果你想在循环中间退出，可以使用`break`语句。例如，假设你想处理单词，直到用户输入字母 Q 为止。这里有一个使用`boolean`变量控制循环的解决方案：

```java
boolean done = false;
while (!done) {
    String input = in.next();
    if ("Q".equals(input)) {
        done = true;
    } else {
        Process input
    }
}
```

这个循环使用`break`语句执行了相同的任务：

```java
while (true) {
    String input = in.next();
    if ("Q".equals(input)) break; // 退出循环
    Process input
}
// break 跳到这里
```

当遇到`break`语句时，循环会立即退出。

`continue`语句与`break`类似，但它不是跳转到循环末尾，而是跳转到当前循环迭代的末尾。你可以用它来跳过不需要的输入，如下：

```java
while (in.hasNextInt()) {
    int input = in.nextInt();
    if (input < 0) continue; // 跳到 in.hasNextInt() 的测试
}
```

### 1.7.5. 局部变量作用域

现在你已经了解了块作用域，让我们看看方法中的变量。在方法中声明的变量仅在该方法内有效。

```java
public static void main(String[] args) {
    int x = 10;
    otherMethod();
    // x 在这里无效
}

public static void otherMethod() {
    // x 在这里无效
    System.out.println(x);
}
```

如果你想在另一个方法中使用变量，必须将其作为参数传递：

```java
public static void main(String[] args) {
    int x = 10;
    otherMethod(x);
}

public static void otherMethod(int x) {
    System.out.println(x);
}
```

声明在块中的变量作用域也限于该块。

```java
public static void main(String[] args) {
    int x = 10;
    if (x > 0) {
        int y = 5;
        System.out.println(y);
    }
    // y 在这里无效
}
```

### 1.8. 数组和 ArrayList

数组是收集多个相同类型项的基础构造。Java 语言内置了数组类型，还提供了`ArrayList`类用于可以动态伸缩的数组。`ArrayList`类是集合框架的一部分，将在后面的章节中介绍。

#### 1.8.1. 使用数组

每种类型都有对应的数组类型。整数数组为`int[]`，`String`对象的数组为`String[]`，以此类推。这里是一个可以存放数组的变量：

```java
String[] names;
```

该变量尚未初始化。让我们用新数组来初始化它。为此，我们需要`new`运算符：

```java
names = new String[100];
```

当然，你可以将这两个语句合并：

```java
String[] names = new String[100];
```

现在`names`指向一个包含 100 个元素的数组，你可以通过`names[0] ... names[99]`访问它。

**注意**

如果你尝试访问不存在的元素（例如`names[-1]`或`names[100]`），会发生`ArrayIndexOutOfBoundsException`。

数组的长度可以通过`array.length`获取。例如，此循环用空字符串填充数组：

```java
for (int i = 0; i < names.length; i++) {
    names[i] = "";
}
```

#### Note

使用 C 语法来声明数组变量是合法的，在变量名后跟随`[]`：

```java
int numbers[];
```

然而，这种语法并不理想，因为它将名称`numbers`和类型`int[]`混在了一起。很少 Java 程序员使用它。

### 1.8.2. 数组构造

当你使用`new`运算符构造数组时，它会被填充默认值。

![Images](img/sq.jpg) 数值类型（包括`char`）的数组会被填充为零。

![Images](img/sq.jpg) `boolean`数组会被填充为`false`。

![Images](img/sq.jpg) 对象数组会被填充为`null`引用。

#### Caution

每当你构造对象数组时，都需要用对象来填充它。考虑以下声明：

```java
BigInteger[] numbers = new BigInteger[100];
```

此时，你还没有任何`BigInteger`对象，只有一个包含 100 个`null`引用的数组。你需要将它们替换为`BigInteger`对象的引用：

```java
for (int i = 0; i < 100; i++)
    numbers[i] = BigInteger.valueOf(i);
```

你可以通过编写循环为数组填充值，正如你在前一节中看到的那样。然而，有时你已经知道想要的值，可以直接在大括号内列出它们：

```java
int[] primes = { 2, 3, 5, 7, 11, 13 };
```

你不需要使用`new`运算符，也不需要指定数组长度。末尾逗号是允许的，这对于一个随时间推移不断添加值的数组来说非常方便：

```java
String[] authors = {
    "James Gosling",
    "Bill Joy",
    "Guy Steele",
    // 在此处添加更多名称并在每个名称后放一个逗号
};
```

如果你不想给数组命名，可以使用类似的初始化语法——例如，将其赋值给已有的数组变量：

```java
primes = new int[] { 17, 19, 23, 29, 31 };
```

#### Note

拥有长度为 0 的数组是合法的。你可以通过`new int[0]`或`new int[] {}`构造这样的数组。例如，如果一个方法返回匹配数组，而对于特定输入没有匹配项，则返回一个长度为 0 的数组。注意，这不等于`null`：如果`a`是长度为 0 的数组，那么`a.length`为`0`；如果`a`是`null`，那么`a.length`会导致`NullPointerException`。

### 1.8.3. 数组列表

构造数组时，你需要知道它的长度。一旦构造，长度永远无法改变。这在许多实际应用中是不方便的。解决办法是使用`java.util`包中的`ArrayList`类。`ArrayList`对象在内部管理一个数组。当该数组太小或利用率不足时，会自动创建另一个内部数组，并将元素移动其中。这个过程对于使用数组列表的程序员来说是不可见的。

数组和数组列表的语法完全不同。数组使用特殊语法——访问元素的`[]`运算符、数组类型的`Type[]`语法以及构造数组的`new Type[n]`语法。相比之下，数组列表是类，你使用标准的语法来构造实例和调用方法。

然而，与你目前见过的类不同，`ArrayList`类是一个泛型类——一个带有类型参数的类。第 6 章详细介绍了泛型类。

你可以在角括号中指定元素类型：例如，持有`String`对象的数组列表类型表示为`ArrayList<String>`。

要声明并初始化这种类型的变量，可以使用以下三个语句中的任意一个：

```java
ArrayList<String> friends = new ArrayList<String>();
var friends = new ArrayList<String>();
ArrayList<String> friends = new ArrayList<>();
```

注意最后一个声明中的空`<>`。编译器从变量的类型推断出类型。（这种快捷方式被称为钻石语法，因为空角括号的形状像一个钻石。）

此调用中没有构造参数，但在末尾提供`()`仍然必要的。

结果是一个大小为 0 的数组列表。你可以使用`add`方法在末尾添加元素：

```java
friends.add("Peter");
friends.add("Paul");
```

遗憾的是，数组列表没有初始化语法。你能做的最好的做法是这样构造数组列表：

```java
var friends = new ArrayList<>(List.of("Peter", "Paul"));
```

`List.of`方法产生一个包含给定元素的不可修改列表，然后你用它来构造`ArrayList`。



你可以在`ArrayList`的任何地方添加和删除元素。

```java
friends.remove(1);
friends.add(0, "Paul"); // 在索引 0 之前添加
```

访问元素时使用方法调用，而不是`[]`语法。`get`方法读取元素，`set`方法用另一个元素替换元素：

```java
String s = friends.get(0);
friends.set(1, "John");
```

### 1.8.4 基本数据类型的包装类

泛型类有一个限制：你不能使用基本数据类型作为类型参数。对于每个基本类型，都有对应的包装类：`Integer`、`Byte`、`Short`、`Long`、`Character`、`Float`、`Double`和`Boolean`。收集整数，使用`ArrayList<>`：

```java
ArrayList<Integer> numbers = new ArrayList<>();
numbers.add(42);
int n = numbers.get(0);
```

基本类型和包装类之间的转换是自动的。在`add`调用中，一个`Integer`对象通过一个称为自动装箱的过程被自动构造。

#### 注意

基本类型和包装类之间的转换几乎是透明的，但有一个例外。`==`和`!=`运算符比较的是对象引用而不是内容。与字符串一样，你需要记得调用`equals`方法。

### 1.8.5 增强型`for`循环

通常你想访问数组的所有元素。例如，这里是计算数组中所有元素之和的方法：

```java
int sum = 0;
for (int i = 0; i < numbers.length; i++) {
    sum += numbers[i];
}
```

由于这种循环非常常见，有一个方便的快捷方式，被称为增强型`for`循环：

```java
int sum = 0;
for (int n : numbers) {
    sum += n;
}
```

增强型`for`循环的遍历变量遍历数组元素而不是索引值。变量`n`被赋值为`numbers[0]`、`numbers[1]`等以此类推。

你也可以对数组列表使用增强型`for`循环。如果`friends`是一个字符串数组列表，你可以用循环打印它们：

```java
for (String name : friends) {
    System.out.println(name);
}
```

### 1.8.6 复制数组和数组列表

你可以将一个数组变量复制另一个，但这样两个变量将引用同一个数组，如图 1.6 所示。

```java
int[] numbers = primes;
numbers[5] = 42; // 现在 primes[5] 也是 42
```

![Images](img/01fig06.jpg)

图 1.6：引用同一个数组的两个变量

如果你不想这种共享，你需要复制数组。使用静态`Arrays.copyOf`方法。

```java
int[] copiedPrimes = Arrays.copyOf(primes, primes.length);
```

该方法构造一个所需长度的新数组，并将原始数组的元素复制到其中。

数组列表引用的方式也是一样的：

```java
ArrayList<String> people = friends;

people.set(0, "Mary"); // 现在 friends.get(0) 也是 "Mary"
```

要复制一个数组列表，可以从现有的创建一个新的数组列表：

```java
var copiedFriends = new ArrayList<>(friends);
```

该构造函数也可以用于将数组转换为数组列表。使用`List.of`方法将数组封装进一个不可变列表，然后构造一个`ArrayList`：

```java
String[] names = ...;

var friends = new ArrayList<>(List.of(names));
```

你也可以将数组列表拷贝到数组。由于向后兼容性的令人丧的原因（我将在第 6 章;

### 注意

在基本类型数组与对应的包装类数组列表之间没有简单的方法可以进行转换。例如，要在`int[]`和`ArrayList<Integer>`之间进行转换，你需要显式的循环或`IntStream`（参见第 8 章）。

### 1.8.7 数组算法

`Arrays`和`Collections`类提供了数组和数组列表常用算法的实现。以下是填充数组或数组列表的方法：

```java
Arrays.fill(numbers, 0); // int[] 数组

Collections.fill(friends, ""); // ArrayList<String>
```

要对数组或数组列表排序，请使用`sort`方法：

```java
Arrays.sort(names);

Collections.sort(friends);
```

### 注意

对于数组（而不是数组列表），如果数组很大，你可以使用`parallelSort`方法，将工作分配到多个处理器上。

`Arrays.toString`方法产生数组的字符串表示。这对于打印数组进行调试特别有用。

```java
System.out.println(Arrays.toString(primes));

// 打印 [2, 3, 5, 7, 11, 13]
```

数组列表也有`toString`方法，产生相同的表示。

```java
String elements = friends.toString();

// 将 elements 设置为 "[Peter, Paul, Mary]"
```

对于打印，你甚至不需要调用它——`println`方法会处理好这一切。

```java
System.out.println(friends);

// 调用 friends.toString() 并打印结果
```

数组列表有一些有用的算法，而数组没有对应的算法。

```java
Collections.reverse(names); // 反转元素

Collections.shuffle(names); // 随机打乱元素
```

### 1.8.8 命令行参数

正如你所看到的，每个 Java 程序的`main`方法都有一个字符串数组类型的参数：

```java
public static void main(String[] args)
```

当程序执行时，该参数被设置为命令行上指定的参数。

例如，考虑这个程序：

```java
public class Greeting {
    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            String arg = args[i];

            if (arg.equals("-h")) arg = "Hello";
            else if (arg.equals("-g")) arg = "Goodbye";

            System.out.println(arg);
        }
    }
}
```

如果按如下调用程序：

```bash
java Greeting -g cruel world
```

那么`args[0]`是`"-g"`，`args[1]`是`"cruel"`，`args[2]`是`"world"`。

注意，`"java"`和`"Greeting"`都没有传递给`main`方法。

### 1.8.9 多维数组

Java 没有真正的多维数组。它们被实现为数组的数组。例如，这里是声明和实现一个整数二维数组的方法：

```java
int[][] square = {
    { 16, 3, 2, 13 },
    { 5, 10, 11, 8 },
    { 9, 6, 7, 12 },
    { 4, 15, 14, 1}
};
```

从技术上讲，这是一个由`int[]`数组组成的一维数组——参见图 1.7。

![Images](img/01fig07.jpg)

图 1.7：二维数组

要访问元素，使用两对括号：

```java
int element = square[1][2]; // 将元素设置为 11
```

第一个索引选择行数组`square[1]`。第二个索引从该行中选取元素。

你甚至可以交换行：

```java
int[] temp = square[0];

square[0] = square[1];

square[1] = temp;
```

如果你不提供初始值，必须使用`new`运算符并指定行数和列数。

```java
int[][] square = new int[4][4]; // 先是行，后是列
```

在底层，行数组被每个行对应的一个数组所填充。

并不要求行数组的长度相等。例如，你可以存储杨斯三角形：

```text
1

1 1

1 1 1

1 1 1 1
```

## 1.9 功能性分解

如果你的`main`方法太长了，你可以将代码分解为独立的方法，正如你将在第 2 章中看到的。然而，对于简单的程序，你可以将它们放在不同的类中。由于在第 2 章中会明确的原因，这些方法必须带有`static`修饰符，就像`main`方法一样。

### 1.9.1 静态方法的声明和调用

当你声明一个方法时，提供返回类型（如果方法不返回任何内容则使用`void`）、方法名以及参数的类型和名称。在方法体中提供实现代码。使用`return`语句返回结果。

```java
public static double average(double x, double y) {
    double sum = x + y;
    return sum / 2;
}
```

将方法放在与`main`方法相同的类中。在`main`之上或之下都行。然后，这样调用它：

```java
public static void main(String[] args) {
    double a = ...;
    double b = ...;
    double result = average(a, b);
    ...
}
```

### 1.9.2 数组参数和返回值

你可以将数组传递给方法。方法接收数组的引用并进行修改。此方法交换数组中的两个元素：

```java
public static void swap(int[] values, int i, int j) {
    int temp = values[i];
    values[i] = values[j];
    values[j] = temp;
}
```

方法可以返回数组。此方法返回一个由给定数组的和最后一个值组成的数组（该数组不会被修改）：

```java
public static int[] firstLast(int[] values) {
    if (values.length == 0) return new int[0];
    else return new int[] { values[0], values[values.length - 1] };
}
```

### 1.9.3 可变长度参数

某些方法允许调用者提供数量不定的参数。你已经见过这样的方法：`printf`。例如，以下调用：

```java
System.out.printf("%d", n);
```

和：

```java
System.out.printf("%d %s", n, "widgets");
```

它们都调用同一个方法，尽管其中一个调用有两个参数，而另一个有三个。

让我们定义一个工作方式相同的`average`方法，这样我们就可以根据需要通过任意数量的参数调用`average`，例如`average(3, 4.5, -5, 0)`。在类型后使用`...`声明一个“可变参数”（varargs）参数：

```java
public static double average(double... values)
```

该参数实际上是一个`double`类型的数组。当调用该方法时，会创建一个数组并填充这些参数。在方法体中，你可以像使用任何其他数组一样使用它。

```java
public static double average(double... values) {
    double sum = 0;
    for (double v : values) sum += v;
    return values.length == 0 ? 0 : sum / values.length;
}
```

现在你可以调用：

```java
double avg = average(3, 4.5, -5, 0);
```

如果你已经在一个数组中有了参数，就不需要对它们进行解包。你可以传递数组而不是参数列表：

```java
double[] scores = { 3, 4.5, -5, 0 };

double avg = average(scores);
```

可变参数必须是方法的`last`参数，但你可以在它之前放置其他参数。例如，此方法确保至少有一个参数：

```java
public static double max(double first, double... rest) {
    double result = first;
    for (double v : rest) result = Math.max(v, result);
    return result;
}
```




### 练习

1. 编写一个程序，读取一个整数并以二进制、八进制和十六进制打印出来。将倒数以十六进制浮点数打印。
2. 编写一个程序，读取一个整数角度（可能是正或负），并将其归一化为 0 到 359 度之间的值。先尝试使用`%`运算符，然后使用`floorMod`。
3. 仅使用条件运算符，编写一个程序读取三个整数并打印最大的那个。用`Math.max`重复。
4. 编写一个程序打印最小和最大的正`double`值。提示：在 Java API 中查找`Math.nextUp`。
5. 当将`double`强制转换为大于最大可能的`int`值的整数会发生什么？尝试一下。
6. 编写一个程序使用`BigInteger`计算阶乘`n! = 1 × 2 × ... × n`。计算 1000 的阶乘。
7. 编写一个程序读取两个 0 到 4294967295 之间的整数，将它们存储在`int`变量中，并计算显示它们的无符号和、差、积、商和余。不要将它们转换为`long`值。
8. 编写一个程序读取字符串并打印其所有的非空子字符串。
9. 第 1.5.3 节有两个字符串`s`和`t`的示例，使得`s.equals(t)`但`s != t`。想出一个不使用`substring`的不同示例。
10. 编写一个程序，通过生成随机`long`值并以 36 进制打印，产生一个字母和数字的随机字符串。
11. 编写一个程序读取一行文本并打印所有非 ASCII 字符以及它们的 Unicode 值。
12. 编写一个`switch`表达式，当给定带有指南针方向`"N"`、`"S"`、`"E"`或`"W"`的字符串时，产生 x 和 y 偏移量的数组。例如，`"W"`应该产生`new int[] { -1, 0 }`。
13. 编写一个`switch`语句，当给定带有指南针方向`"N"`、`"S"`、`"E"`或`"W"`的字符串时，调整变量`x`和`y`。例如，`"W"`让`x`减 1。
14. 你可以在 switch 语句中使用`break`而不贯穿（fall through）吗？在 switch 表达式中可以吗？为什么或为什么不可以？
15. 想出一个贯穿行为对`switch`表达式或语句有用的实际场景。大多数网络搜索产生的示例对 C 或 C++ 有意义，在这些语言中，执行从没有操作的`case A`落在`case B`。在 Java 中，这并不重要，因为你可以使用`case A, B`。
16. “Quine”是一个在不读取任何输入或文件的情况下打印自身源码的程序。使用文本块（text block）用 Java 编写这样一个程序。
17. Java JDK 包含一个`src.zip`文件，其中包含 Java 库的源代码。解压并使用你最喜欢的文本搜索工具找到标记的`break`和`continue`序列的使用。选取一个并在不使用标记语句的情况下重写它。
18. 编写一个程序打印彩票组合，在 1 到 49 之间选取六个不同的数字。要选取六个不同的数字，从一个填充了 1`...`49 的数组列表开始。选取一个随机索引并移除元素。重复六次。按排序顺序打印结果。
19. 编写一个程序读取一个整数二维数组并判断它是否为魔方（即所有行、所有列和对角线的和是否相同）。接受输入。

考虑一个常见的任务：日历日期操作。日历相当混乱，月份长度不一，还有闰年，更不用说闰秒了。让专家来处理这些混乱的细节，并提供其他程序员可以使用的实现是有意义的。在这种情况下，对象的出现自然而然。日期（date）是一个对象，它的方法可以提供此类信息，例如“这个日期是星期几”以及“明天是几号”。

在 Java 中，理解日期计算的专家为日期以及其他日期相关的概念（如星期）提供了相应的类。如果你想对日期进行计算，可以使用这些类中的一个来创建日期对象，并在它们上调用方法，例如返回星期或下一个日期的方法。

我们很少有人想去思索日期算术的细节，但你可能是其他某些领域的专家。为了让其他程序员能够利用你的知识，你可以为他们提供类。即使你不是为了帮助其他程序员，你会发现使用类对你自己的工作也有帮助，这可以让你的程序结构更加连贯。

在学习如何定义自己的类之前，让我们先来看一个使用对象的非显而易示例。

## 使用`LocalDate`打印日历

Unix 程序`cal`可以打印给定月份和年份的日历，格式类似于：

```text
 Mon Tue Wed Thu Fri Sat Sun

                          1

  2   3   4   5   6   7   8

  9  10  11  12  13  14  15

 16  17  18  19  20  21  22

 23  24  25  26  27  28  29

 30
```

你如何实现这样一个程序？使用标准 Java 库，可以使用`LocalDate`类来表示某个特定位置的日期。我们需要该类的一个对象来代表每月的第一天。以下是获取方法：

```java
LocalDate date = LocalDate.of(year, month, 1);
```

要让日期向前推进，调用`date.plusDays(1)`。结果是一个新构造的`LocalDate`对象，增加一天。在我们的应用程序中，只需将结果重新赋值给`date`变量：

```java
date = date.plusDays(1);
```

你应用方法来获取关于日期的信息，例如它所属的月份。我们需要这些信息，以便在仍处于月份时继续打印。

```java
while (date.getMonthValue() == month) {
    System.out.printf("%4d", date.getDayOfMonth());
    date = date.plusDays(1);
    ...
}
```

另一个方法返回日期所属的星期。

```java
DayOfWeek weekday = date.getDayOfWeek();
```

你得到的是另一个类`DayOfWeek`的对象。为了计算日历中每月第一天的缩进，我们需要知道星期的数值。有一个方法可以实现：

```java
int value = weekday.getValue();

for (int i = 1; i < value; i++)
    System.out.print("  ");
```

`getValue`方法遵循国际惯例，周一返回`1`，周二返回`2`，依此类推。周日的值为`7`。

> **注意**
>
> 你可以*链式*调用方法，如下所示：
>
> ```java
> int value = date.getDayOfWeek().getValue();
> ```
>
> 第一个方法调用作用于`date`对象，并返回一个`DayOfWeek`对象。然后在返回的对象上接着调用`getValue`方法。

你将在书中配套代码中找到完整的程序。解决打印日历的问题很容易，因为`LocalDate`类的设计者为我们提供了一个有用的方法。在本章中，你将学习如何为自己的类实现方法。

## 2.1 访问器和变器方法

再次考虑方法调用`date.plusDays(1)`。`LocalDate`类的设计者有两种方式实现`plusDays`方法。他们可以使其改变`date`对象的状态且不返回结果，或者他们可以保持`date`不变并返回一个新构造的`LocalDate`对象。正如你所看到的，他们选择了后者。

如果一个方法改变了被调用的对象，我们称该方法为*变异器*（mutator）。如果它保持对象不变，则它是一个*访问器*（accessor）。`LocalDate`类的`plusDays`方法就是一个访问器。

事实上，`LocalDate`类的*所有*方法都是访问器。这种情况越来越常见，因为变异是有风险的，特别是当两个计算同时变异一个对象时。如今，大多数计算机都有多个处理单元，安全的并发访问是一个严重的问题。解决这一问题的方法之一是通过只提供访问方法来使对象变为*不可变*（immutable）。

尽管如此，在许多情况下变异是有希望的。`ArrayList`类的`add`方法就是变异器的例子。调用`add`之后，数组列表对象发生了变化。

```java
var friends = new ArrayList<String>();

// friends 是空的
friends.add("Peter");
// friends 的大小为 1
```

## 2.2 对象引用

在某些编程语言（如 C++）中，变量实际上可以持有对象——即组成对象状态的位。在 Java 中，情况并非如此。变量只能持有对象的*引用*（reference）。实际对象在别处，而引用取决于具体的实现。

> **注意**
>
> 引用的行为像 C++ 中的指针，但它们是安全的。在 C++ 中，你可以修改指针并覆盖任意位置。在 Java 中，你只能访问特定的对象。

![对象引用](Images/02fig1.jpg)

图 2.1：对象引用

当你将持有对象的引用赋值给另一个变量时，你就有了同一个对象的两个引用。

```java
ArrayList<String> people = friends; // 现在 people 和 friends 指同一个对象
```

如果你变异了共享的对象，这种变异可以通过任何一个引用观察到。考虑调用：

```java
people.add("Paul");
```

现在数组列表`people`的大小为 2，`friends`也是如此（见图 2.2）。（当然，技术上并不是说`people`或`friends`“拥有”大小 2。毕竟它们不是对象。）

![指向同一个对象的两个引用](Images/02fig2.jpg)

图 2.2：指向同一个对象的两个引用

大多数情况下这种对象的共享是高效且方便的，但你必须意识到可以通过任何引用来变异共享对象。

然而，如果一个类没有变器方法（如`String`或`LocalDate`），你不必担心。由于没有人能改变这样的对象，你可以自由地给出引用。

对象变量可以指向任何对象，只需将其设置为特殊值`null`。

```java
LocalDate date = null; // 现在 date 不指向任何对象
```

当你还没有对象供`date`指向时，或者你想表示某种特殊情况（如未知日期）时，这是很有用的。

> **警告**
>
> 空值在未预期的情况下可能是危险的。在`null`上调用方法会导致`NullPointerException`（它本应该被称为`NullReferenceException`）。出于这个原因，不建议使用`null`来表示可选值。请使用`Optional`类型（见第 8 章）。

最后，再次查看这些赋值：

```java
date = LocalDate.of(year, month, 1);

date = date.plusDays(1);
```

在第一次赋值后，`date`指向月份的第一天。调用`plusDays`产生一个新的`LocalDate`对象，在第二次赋值后，`date`变量指向了新对象。第一个对象发生了什么呢？

不再有引用第一个对象，因此它不再需要了。最终，`garbage collector`（垃圾回收器）将回收内存并重用。在 Java 中，这个过程是完全自动的，程序员永远不需要担心释放内存。

## 2.3 实现类

现在让我们转向实现我们自己的类。为了展示各种语言规则，我使用了一个经典的`Employee`类作为示例。员工有一个名称和一个薪水。在这个例子中，名称不能更改，但员工经常可以获得应有的加薪。

### 2.3.1 实例变量

通过对员工对象的描述，你可以看到此类的状态由两个值描述：`name`和`salary`。在 Java 中，你使用`instance variables`（实例变量）来描述对象的状态。它们在类中的声明如下：

```java
public class Employee {
    private String name;
    private double salary;
    ...
}
```

这意味着`Employee`类的每一个实例都有这两个变量。

在 Java 中，实例变量通常被声明为`private`。这意味着只有同一类的方法可以访问它们。这种保护是有意义的，原因有几点：你可以控制程序的哪些部分可以修改这些变量，并且你可以在任何时候更改内部表示。例如，你可能将员工存储在数据库中，只在对象中保留主键。只要你重新实现这些方法使其工作方式与之前相同，你类的用户就不会在意。

### 2.3.2 方法头

现在让我们转向实现`Employee`类的方法。当你声明一个方法时，你需要提供它的名称、参数的类型和名称以及返回类型，如下所示：

```java
public void raiseSalary(double byPercent)
```

该方法有一个类型为`double`的参数，并且不返回任何值，如返回类型`void`所示。

`getName`方法有不同的签名：

```java
public String getName()
```

该方法没有参数并返回一个`String`。

> **注意**
>
> 大多数方法都被声明为`public`，这意味着任何人都可以调用此类方法。有时，辅助方法被声明为`private`，这将其限制为仅在同类的其他方法中使用。对于与类用户无关的方法，你应该这样做，特别是当它们依赖于实现细节时。如果实现发生变化，你可以安全地更改或删除私有方法。

### 2.3.3 方法体

紧接方法头，你提供方法体：

```java
public void raiseSalary(double byPercent) {
    double raise = salary * byPercent / 100;
    salary += raise;
}
```

如果方法产生一个值，请使用`return`关键字：

```java
public String getName() {
    return name;
}
```

将方法声明放在类声明内部：

```java
public class Employee {
    private String name;
    private double salary;

    public void raiseSalary(double byPercent) {
        double raise = salary * byPercent / 100;
        salary += raise;
    }

    public String getName() {
        return name;
    }

    ...
}
```

### 2.3.4 实例方法调用

考虑这个对类`Employee`的对象`fred`调用方法的示例：

```java
fred.raiseSalary(5);
```

在此调用中，参数`5`被用于初始化参数变量`byPercent`，等同于赋值：

```java
double byPercent = 5;
```

然后发生了以下操作：

```java
double raise = fred.salary * byPercent / 100;
fred.salary += raise;
```

注意，`salary`实例变量应用于调用方法的实例上。

与你在上一章末尾看到的静态方法不同，如`raiseSalary`这样的方法在类的实例上操作。因此，这种方法被称为`instance method`（实例方法）。在 Java 中，所有未声明为`static`的方法都是实例方法。

为了让`raiseSalary`方法工作，它必须接收两个值：调用该方法的对象引用，以及调用的参数。从技术上讲，这两个都是方法的参数，但在 Java 中（与其他面向对象的语言一样），第一个参数承担着特殊的角色。它有时被称为方法调用的`receiver`（接收者）。

### 2.3.5 `this`引用

当在对象上调用方法时，`this`被设置为该对象。如果你愿意，可以在实现中使用`this`引用：

```java
public void raiseSalary(double byPercent) {
    double raise = this.salary * byPercent / 100;
    this.salary += raise;
}
```

一些程序员更喜欢这种风格，因为它清楚地区分了局部变量和实例变量——现在很明显`raise`是一个局部变量，而`salary`是实例变量。

当你不想为参数变量想出不同的名称时，使用`this`引用是非常常见的。例如：

```java
public void setSalary(double salary) {
    this.salary = salary;
}
```

当实例变量和局部变量具有相同名称时，未限定的名称（如`salary`）表示局部变量，而`this.salary`是实例变量。

> **注意**
>
> 在某些编程语言中，实例变量会以某种方式进行装饰。

### 2.3.6 值传递

当你将一个对象传递给方法时，该方法获得了该对象的拷贝。通过这个引用，它可以访问或修改该对象。例如：

```java
public class EvilManager {
    private Random generator;

    ...

    public void giveRaise(Employee e) {
        double percentage = 10 * generator.nextGaussian();
        e.raiseSalary(percentage);
    }
}
```

考虑调用：

```java
boss.giveRaise(fred);
```




引用`fred`被拷贝到参数变量`e`中。该方法修改了两个引用共享的对象。

在 Java 中，你永远无法编写一个更新基本类型变量的方法。一个尝试增加`double`值的方法将不起作用：

```java
public void increaseRandomly(double x) {
    double amount = x * generator.nextDouble();
    x += amount;
}
```

如果你调用：

```java
boss.increaseRandomly(sales);
```

那么`sales`被拷贝到`x`中。然后`x`增加了，但这并没有改变`sales`。参数变量随后离开作用域，增加没有留下任何有效果。

出于相同的原因，无法编写一个更改对象引用为其他内容的方法。例如，这个方法并没有按设意工作：

```java
public class EvilManager {
    ...
    public void replaceWithZombie(Employee e) {
        e = new Employee("", 0);
    }
}
```

在调用

```java
boss.replaceWithZombie(fred);
```

引用`fred`被拷贝到变量`e`中，然后`e`被设置为不同的引用。当方法退出时，`e`离开作用域。在任何时刻`fred`都未被改变。

**注意**

有些人说 Java 对对象使用“引用传递”。正如你在第二个示例所示，事实并非如此。在支持引用传递的语言中，方法可以替换传递给它的变量的内容。

完成`Employee`类还剩最后一步：我们需要提供一个构造函数，详见下文章节。

## 2.3.1. 实现构造函数

声明构造函数与声明方法相似。然而，构造函数的名称与类名相同，且没有返回类型。

```java
public Employee(String name, double salary) {
    this.name = name;
    this.salary = salary;
}
```

### 注意

此构造函数是公有的。某些情况下，拥有私有构造函数也很有用。例如，`LocalDate`类没有公共构造函数。相反，该类的用户通过“工厂方法”（如`now`和`of`）来获取对象。这些方法会调用私有构造函数。

### 注意事项

如果你不小心指定了返回类型，例如

```java
public void Employee(String name, double salary)
```

那么你声明的是一个名为`Employee`的方法，而不是构造函数！

当你使用`new`运算符时，会执行一个构造函数。例如，表达式

```java
new Employee("James Bond", 500000)
```

会分配一个`Employee`类的对象并调用构造函数体，构造函数体会将实例变量设置为构造函数提供的参数。

`new`运算符返回指向所构建对象的引用。你通常希望将该引用保存在变量中：

```java
var james = new Employee("James Bond", 500000);
```

或者将其传递给一个方法：

```java
var staff = new ArrayList<Employee>();
staff.add(new Employee("James Bond", 500000));
```

## 2.3.2. 重载

你可以提供多个版本的构造函数。例如，如果你想方便地为无名的工蜂（工人建模，可以提供一个只接受工资的第二个构造函数。

```java
public Employee(double salary) {
    this.name = "";
    this.salary = salary;
}
```

现在，`Employee`类有两个构造函数。调用哪一个取决于传入的参数。

```java
var james = new Employee("James Bond", 500000);
    // 调用 Employee(String, double) 构造函数

var anonymous = new Employee(40000);
    // 调用 Employee(double) 构造函数
```

在这种情况下，我们称构造函数被*重载*了。

### 注意

如果一个方法有多个名称相同但参数不同的版本，则该方法被重载。例如，`println`方法有带有`int`、`double`、`String`等参数的重载版本。由于你无法选择构造函数的名称，因此重载构造函数是常见的做法。

## 2.3.3. 从一个构造函数调用另一个

当存在多个构造函数时，它们通常会有一些共同工作，最好不要重复这部分代码。通常可以将这些共同的初始化放在一个构造函数中。

你可以从一个构造函数调用另一个，但只能作为构造函数体的第一条语句。有些令人惊讶的是，你调用时并不使用构造函数的名称，而是使用关键字`this`：

```java
public Employee(double salary) {
    this("", salary); // 调用 Employee(String, double)
    // 后面可以跟随其他语句
}
```

### 注意

在这里，`this`不是指向正在构建对象的引用。相反，它是一种特殊的语法，仅用于调用同一类的另一个构造函数。

## 2.3.4. 默认初始化

如果你没有在构造函数中显式地设置实例变量，它会被自动设置为默认值：数字为`0`，布尔值为`false`，对象引用为`null`。

例如，你可以为无薪实习生提供一个构造函数。

```java
public Employee(String name) {
    // salary 自动设为 0
    this.name = name;
}
```

### 注意

在这方面，实例变量与局部变量非常不同。记住，你必须始终显式地初始化局部变量。对于数字，用零初始化通常很方便。但对于对象引用，这是一个常见的错误来源。假设我们没有在`Employee(double)`构造函数中将`name`变量设置为空字符串：

```java
public Employee(double salary) {
    // name 自动设置为 null
    this.salary = salary;
}
```

如果有人调用了`getName`方法，他们将得到一个他们可能并没有想到的空引用。像这样的条件

```java
if (e.getName().equals("James Bond"))
```

将会导致空指针异常（null pointer exception）。

## 2.3.5. 实例变量初始化

你可以为任何实例变量指定一个初始值，如下所示：

```java
public class Employee {
    private String name = "";
    ...
}
```

这种初始化发生在对象分配之后、构造函数运行之前。因此，初始值在所有构造函数都存在。当然，其中某些构造函数可能会选择覆盖它。

除了在声明实例变量时初始化外，你可以在类声明中包含任意的初始化块。

```java
public class Employee() {
    private String name = "";
    private int id;
    private double salary;

    { // 一个初始化块
        var generator = new Random();
        id = 1 + generator.nextInt(1_000_000);
    }

    public Employee(String name, double salary) {
        ...
    }
}
```

### 注意

这不是一个常用的特性。大多数程序员会将冗长的初始化代码放在辅助方法中，并在构造函数中调用该方法。

实例变量初始化和初始化块按照它们在类声明中的顺序执行，并且在构造函数体之前。

## 2.3.6. final 实例变量

你可以将实例变量声明为`final`。此类变量必须在构造函数结束时完成初始化。之后，该变量无法再次修改。例如，`Employee`类的`name`变量可以声明为`final`，因为它在对象构建后不再改变——没有`setName`方法。

```java
public class Employee {
    private final String name;
    ...
}
```

### 注意

配合可变对象使用时，`final`只表示引用不会改变。修改对象是完全合法的。

```java
public class Person {
    private final ArrayList<Person> friends = new ArrayList<>();
        // 可以向此列表添加元素
    ...
}
```

方法可以修改`friends`指向的列表，但不能将其替换。特别是，它永远不会变成`null`。

## 2.3.7. 无参数构造函数

许多类包含一个创建默认状态对象的无参数构造函数。例如，这是`Employee`类的无参数构造函数：

```java
public Employee() {
    name = "";
    salary = 0;
}
```

就像贫民提供公共辩护人一样，没有构造函数的类会自动获得一个什么都不做的无参数构造函数。除非经过显式初始化，否则所有实例变量都保持其默认值（零、`false`或`null`）。

因此，每个类至少有一个构造函数。

### 注意

如果一个类已经有一个构造函数，它不会自动获得另一个无参数构造函数。如果你提供了构造函数并且想要一个无参数构造函数，你必须手动编写。

### 注意

在前面的节中，你看到了对象被构建时会发生什么。在某些编程语言（特别是 C++）中，指定对象销毁时发生什么是常见的。Java 有一种过时的机制在对象被垃圾回收器回收时进行“终结”。但这发生的时间是不可预测的，所以你不应该使用它。然而，正如我们在第 5 章中看到的，有一种关闭文件等资源的机制。

## 2.4. Records

有时候，数据仅仅就是数据，而面向对象编程提供的数据隐藏反而会成为障碍。考虑一个描述平面上点的类`Point`，它具有`x`和`y`坐标。

当然，你可以提供一个类：

```java
class Point {
    private final double x;
    private final double y;

    public Point(double x, double y) { this.x = x; this.y = y; }
    public getX() { return x; }
    public getY() { return y; }
    public String toString() { return "Point[x=%d, y=%d]".formatted(x, y); }
    // More methods ...
}
```

但是，隐藏`x`和`y`然后通过 getter 方法公开这些值，真的能带给我们什么吗？

我们真的想要更改`Point`的实现吗？当然，有极坐标系，但你不会在图形 API 中使用它们。在实践中，平面上的点完全由其`x`和`y`坐标描述。

为了更简洁地定义像这样的类，你可以使用一种特殊的类形式，被称为“records”（记录）。

### 2.4.1 Record 的概念

record 是一种特殊的类形式，其状态是不可变的且公开可读。要声明一个 record，提供名称和持有对象状态的实例变量。这是一个典型的示例：

```java
record Point(double x, double y) { }
```

结果是一个带有实例变量的类`Point`：

```java
private final double x;
private final double y;
```

该类有一个构造函数

```java
Point(double x, double y)
```

以及访问器方法

```java
public double x()
public double y()
```

注意，访问器方法被命名为`x`和`y`，而不是`getX`和`getY`。（在 Java 中，拥有同名的实例变量和方法是合法的。）

```java
var p = new Point(3, 4);
double slope = p.y() / p.x();
```

除了变量访问器方法外，每个 record 都自动了三个方法：`toString`、`equals`和`hashCode`。你将在下一章学习更多关于这些方法的知识。

你可以为 record 添加自己的方法：

```java
record Point(double x, double y) {
    public double distanceFromOrigin() { return Math.hypot(x, y); }
}
```

### 注意事项

你可以定义自动提供的方法的自定义版本，只要它们具有相同的参数类型和返回类型。例如，这种定义是合法的：

```java
record Point(double x, double y) {
    public double x() { return y; } // 坏的做法 (BAD)
}
```

但这显然绝对不是一个好主意。

你不能在 record 的体中声明实例变量：

```java
record Point(double x, double y) {
    private double r; // 不能在此处声明实例变量
    ...
}
```

### 注意事项

record 的实例变量自动是`final`的。然而，它们可能是可变对象的引用：

```java
record Point(double[] coords) { ... }
```

那么 record 实例就是可变的：

```java
Point p = ...;
p.coords[0] = 10;
```

如果你打算让 record 实例是不可变的，请不要为实例变量使用可变类型。

### 2.4.2 构造函数：规范的、自定义的和紧凑的

自动定义的设置所有实例变量的构造函数被称为“规范构造函数”（canonical constructor）。

你可以定义额外的“自定义构造函数”（custom constructors）。此类构造函数的第一条语句必须调用另一个构造函数，以便最终调用规范构造函数。这是一个示例：

```java
record Point(double x, double y) {
    public Point() { this(0, 0); }
}
```

这个 record 有两个构造函数：规范构造函数和一个产生原点的无参数构造函数。

如果规范构造函数需要执行额外工作，你可以提供你自己的实现：

```java
record Range(int from, int to) {
    public Range(int from, int to) {
        if (from <= to) {
            this.from = from;
            this.to = to;
        } else {
            this.from = to;
            this.to = from;
        }
    }
}
```

然而，我们鼓励在实现规范构造函数时使用`compact`（紧凑）形式。你不需要指定参数列表：

```java
record Range(int from, int to) {
    public Range {
        if (from > to) { // 交换边界
            int temp = from;
            from = to;
            to = temp;
        }
    }
}
```

紧凑形式体是规范构造函数的“前言”（prelude）。它只是在参数变量赋值给实例变量之前对其进行修改。你不能在紧凑构造函数的体内读取或修改实例变量。

## 2.5 静态变量和方法

在你见过的所有示例程序中，主方法都标记有`static`修饰符。在后续章节中，你将学习这个修饰符的含义。

### 2.5.1 静态变量

如果你在类中声明变量为`static`，那么每个类只有一个这样的变量。相比之下，每个对象都有它们自己的实例变量副本。例如，假设我们想给每个员工分配一个独特的 ID 号。那么我们可以共享最后一个给出的 ID。

```java
public class Employee {
    private int lastId = 0;
    private int id;
    ...

    public Employee() {
        lastId++;
        id = lastId;
    }
}
```

### 2.5.2 静态常量

可变的静态变量是很少的，但静态常量（即`static final`变量）非常常见。例如，`Math`类声明了一个静态常量：

```java
public class Math {
    ...
    public static final double PI = 3.14159265358979323846;
    ...
}
```



你可以在程序中使用`Math.PI`访问此常量。

如果没有`static`关键字，`PI`将会是`Math`类的实例变量。也就是说，你需要该类的对象来访问`PI`，并且每个`Math`对象都会有它自己的`PI`副本。

这是一个对象的静态`final`变量的示例，而不是一个数字。每次想要一个随机数时都构建一个新的随机数生成器既浪费资源又不安全。在类的类的所有实例之间共享单个生成器会更好。

```java
public class Employee {

    private static final Random generator = new Random();

    private int id;

    ...

    public Employee() {

        id = 1 + generator.nextInt(1_000_000);

    }

}
```

另一个静态常量是`System.out`。它在`System`类中的声明如下：

```java
public class System {

    public static final PrintStream out;

    ...

}
```

### 注意事项

尽管`out`在`System`类中被声明为`final`，但有一个`setOut`方法可以将`System.out`设置为不同的流。该方法是一个“原生”（native）方法，并非 Java 实现，它可以绕过 Java 语言的访问控制机制。这是 Java 早期非常特殊的情况，你可能在其他地方遇到。

### 2.5.3 静态初始化块

在前面的章节中，静态变量是在声明时初始化的。有时，你需要执行额外的初始化工作。你可以将其放入*静态初始化块*中。

```java
public class CreditCardForm {

    private static final ArrayList<Integer> expirationYear = new ArrayList<>();

    static {

        // 将当前年份及之后的二十年添加到数组列表中

        int year = LocalDate.now().getYear();

        for (int i = year; i <= year + 20; i++) {

            expirationYear.add(i);

        }

    }

    ...

}
```

静态初始化发生在类首次加载时。与实例变量一样，除非你显式地将其设置为另一个值，否则静态变量的值为`0`、`false`或`null`。所有的静态变量初始化和静态初始化块都按照它们在类声明中出现的顺序进行执行。

### 2.5.4 静态方法

静态方法是不操作对象的方法。例如，`Math`类的`pow`方法就是一个静态方法。该表达式：

```java
Math.pow(x, a)
```

计算幂`x`^(`a`)。它没有使用任何`Math`对象来完成任务。

正如你已经在第 1 章中看到的，静态方法使用`static`修饰符声明：

```java
public class Math {

    public static double pow(double base, double exponent) {

        ...

    }

}
```

为什么不把`pow`变成实例方法呢？它不能是`double`的实例方法，因为在 Java 中，基本类型不是类。你可以把它设为`Math`类的实例方法，但那样你就需要构造一个`Math`对象才能调用它。

静态方法的另一个常见用处是你不拥有的类提供额外的功能。例如，如果有一个方法可以在给定范围内产生一个随机整数，那不是很好吗？你无法向标准库中的`Random`类中添加方法。但你可以提供一个静态方法：

```java
public class RandomNumbers {

    public static int nextInt(Random generator, int low, int high) {

        return low + generator.nextInt(high - low + 1);

    }

}
```

通过如下方式调用该方法：

```java
int dieToss = RandomNumbers.nextInt(gen, 1, 6);
```

### 注意

在对象上调用静态方法是合法的。例如，与其调用`LocalDate.now()`来获取今天的日期，你可以在`LocalDate`类的对象`date`上调用`date.now()`。但这并没有太大意义。`now`方法并没有查看`date`对象来计算结果。大多数 Java 程序员会认为这种写法很糟糕。

由于静态方法不操作对象，你不能从静态方法中访问实例变量。然而，静态方法可以访问其类中的静态变量。例如，在`RandomNumbers.nextInt`方法中，我们可以将随机数生成器设置为静态变量：

```java
public class RandomNumbers {

    private static final Random generator = new Random();

    public static int nextInt(int low, int high) {

        return low + generator.nextInt(high - low + 1);

        // 可以访问静态变量 generator

    }

}
```

### 2.5.5 工厂方法

静态方法的常见用处是工厂方法，即一种返回类的新实例的静态方法。例如，`NumberFormat`类使用工厂方法来产生各种样式的格式化对象。

```java
NumberFormat currencyFormatter = NumberFormat.getCurrencyInstance();

NumberFormat percentFormatter = NumberFormat.getPercentInstance();

double x = 0.1;

System.out.println(currencyFormatter.format(x)); // 输出 $0.10

System.out.println(percentFormatter.format(x)); // 输出 10%
```

为什么不使用构造函数呢？区分两个构造函数的唯一方法是它们的参数类型。你不能有两个无参数的构造函数。

此外，构造函数`new NumberFormat(...)`返回一个`NumberFormat`。工厂方法可以返回子类的对象。事实上，这些工厂方法返回的是`DecimalFormat`类的实例。（有关子类的更多信息，请参见第 4 章。）

工厂方法还可以返回共享对象，而不是不必要地构造新对象。例如，调用`Collections.emptyList()`返回一个共享的不可变空列表。

### 2.6 包

在 Java 中，你将相关的类放入一个包中。包对于组织工作以及将其与他人提供的代码库分开非常方便。正如你所看到的，Java 标准库分布在多个包中，包括`java.lang`、`java.util`、`java.math`等。

使用包的一个原因是保证类名的唯一性。假设两个程序员都想出了提供`Element`类的绝妙主意。（事实上，仅 Java API 就有五位开发者产生过这个绝妙主意。）只要他们都将类放在不同的包中，就不会产生冲突。

在接下来的章节中，你将学习如何使用包。

### 2.6.1 包的声明

包名是用点分隔的标识符列表，例如`java.util.regex`。

为了保证包名的唯一性，使用反向写的 Internet 域名（已知是唯一的）是一个好主意。例如，我拥有`horstmann.com`域名。对于我的项目，我使用如`com.horstmann.com`类的包名。

### 注意

在 Java 中，包不是嵌套的。例如，`java.util`和`java.lang`之间没有关系。每个都是独立的集合。

要将类放入包中，你在源文件的第一行添加`package`语句：

```java
package com.horstmann.corejava;

public class Employee {

    ...

}
```

现在`Employee`类位于`com.horstmann.corejava`，其限定名为`com.horstmann.corejava.Employee`。还有一个没有命名的默认包可以用于简单的程序。但是不建议使用默认包。

当类文件从文件系统读取时，路径名需要与包名匹配。例如，`Employee.class`必须位于`com/horstmann/corejava`。

如果你以此方式安排源文件，并在包含包的目录下进行编译，那么类文件会自动放在正确的位置。假设`EmployeeDemo`类使用了`Employee`对象，你这样编译它：

```bash
javac com/horstmann/corejava/EmployeeDemo.java
```

编译器生成`com/horstmann/corejava/EmployeeDemo.class`和`com/horstmann/corejava/Employee.class`。你通过指定全限定名运行程序：

```bash
java com.horstmann.corejava.EmployeeDemo
```

### 注意

如果源文件不在与其包名相同的目录下，`javac`编译器不会报错并生成类文件，但你将类文件放在正确的位置。这可能会令人困惑——参见练习 13。

### 提示

运行`javac`时使用`-d`选项是一个好主意。这样类文件就会生成在独立的目录中，而不会污染源码树，并且具有正确的子目录结构。

### 2.6.2 `jar`命令

与其将类文件存储在文件系统中，不如将它们放入一个或多个称为 JAR 的文件中。你可以使用 JDK 中的`jar`工具创建此类归档文件。它的命令行选项与 Unix 的`tar`程序相似。

```bash
jar --create --verbose --file library.jar com/mycompany/*.class
```

或者，使用短选项：

```bash
jar -c -v -f library.jar com/mycompany/*.class
```

或者，使用`tar`风格的选项：

```bash
jar cvf library.jar com/mycompany/*.class
```

JAR 文件通常用于打包库。

你可以使用 JAR 文件来封装程序，而不仅仅是库。使用命令生成 JAR 文件：

```bash
jar -c -f program.jar -e com.mycompany.MainClass com/mycompany/*.class
```

然后以如下方式运行程序：

```bash
java -jar program.jar
```

### 注意事项

Java 开发工具包中命令的选项传统上使用单横杠后跟多字母的选项名称，例如`java -jar`。例外是`jar`命令，它遵循了`tar`命令的经典选项格式，且不带横杠。现在，Java 正在向更常见的选项格式移动，即多字母的选项名称前加双横杠（例如`--create`），并为常用选项提供单字母缩写（例如`-c`）。

这造成了一个混乱，希望随着时间的推移会得到解决。目前，`java -jar`像往常一样工作，但`java --jar`则不行。你可以组合某些单字母选项，但不能组合其他的。例如，`jar -cvf filename`是有效的，但`jar -cv -f filename`则无效。长参数选项可以跟在空格或`=`后面，短参数选项后面可以跟或不跟空格。然而，这尚未完全实现：`jar -c --file=filename`是有效的，但`jar -c -ffilename`则无效。

### 2.6.3 类路径（Class Path）

当项目中使用库 JAR 文件时，你需要通过指定`class path`（类路径）告诉编译器和虚拟机这些文件所在的位置。类路径可以包含：

- ![Images](img/sq.jpg) 包含类文件的目录（在与其包名匹配的子目录下）
- ![Images](img/sq.jpg) JAR 文件
- ![Images](img/sq.jpg) 包含 JAR 文件的目录

`javac`和`java`程序都有一个选项`-cp`（其详细版本为`--class-path`，或者为了向后兼容使用`-classpath`）。例如：

```bash
java -cp .:../libs/lib1.jar:../libs/lib2.jar com.mycompany.MainClass
```

此类路径包含三个元素：当前目录（`.`）以及`../libs`目录下的两个 JAR 文件。

### 注意

在 Windows 中，使用分号代替冒号来分隔路径元素：

```bash
java -cp ..\libs\lib1.jar;..\libs\lib2.jar com.mycompany.MainClass
```

如果你有许多 JAR 文件，可以将它们全部放在一个目录中并使用通配符包含所有文件：

```bash
java -cp .:../libs/* com.mycompany.MainClass
```

### 注意

在 Unix 中，`*`必须进行转义以防止 shell 扩展。

### 注意事项

`javac`编译器始终会在当前目录中查找文件，但只有当`.`目录在类路径上时，`java`程序才会查找当前目录。如果你没有设置类路径，这并不是问题——默认类路径由`.`目录组成。但如果你设置了类路径却忘记包含`.`目录，你的程序将通过编译而不报错，但无法运行。

### 注意事项

类路径的通配符选项虽然方便，但只有在 JAR 文件结构良好的情况下它才能可靠地工作。可能（但并不建议）在不同的 JAR 文件中有同一个类名的两个版本。在这种情况下，第一个遇到的类将胜出。通配符语法不保证处理 JAR 文件的顺序，如果你需要 JAR 文件的特定顺序，则不应使用它。（这种“JAR 文件地狱”是 Java 模块系统旨在防止的问题——参见第 15 章。）

使用`-cp`选项是设置类路径的首选方法。另一种方法是`CLASSPATH`环境变量。具体取决于你的 shell。如果你使用`bash`，可以使用如下命令：

```bash
export CLASSPATH=.:/home/username/project/libs/*
```

在 Windows 中，它是：

```bat
SET CLASSPATH=.;C:\Users\username\project\libs\*
```

### 注意事项

你可以全局设置`CLASSPATH`环境变量（例如在`.bashrc`或 Windows 控制面板中）。然而，许多程序员在忘记全局设置后感到后悔，并惊讶地发现找不到他们的类。

### 注意

正如你将在第 15 章中看到的，你可以将包组合成`modules`（模块）。模块提供了强封装性，隐藏了除你设置为可见的所有包。你将在第 15 章中看到如何使用`module path`来指定程序所用模块的位置。

### 2.6.4 包访问（Package Access）

你已经遇到过修饰符`public`和`private`。标记为`public`的特征可以被任何类使用。私有特征只能由声明它的类使用。如果你既没有指定`public`也没有`private`，该特征（即类、方法或变量）可以被相同包中的所有方法访问。

包访问对于工具类和方法非常有用，这些方法被包中的方法需要，但包的用户并不感兴趣。另一个常见用例是测试。你可以将测试类放在同一个包中，然后它们就可以访问被测试类的内部实现。

### 注意

一个源文件可以包含多个类，但最多只能有一个被声明为`public`。如果源文件有一个公共类，其名称必须与之匹配。

### 2.6.5 导入类（Importing Classes）

`import`语句允许你不使用全限定名而使用类。例如，当你使用：

```java
import java.util.Random;
```

你就可以在代码中写`Random`而不是`java.util.Random`。

### 注意

导入声明是一种便利，而非必须的。你可以丢弃所有导入声明并在处处使用全限定名。

```java
private java.util.Random generator = new java.util.Random();
```

将`import`语句放在源文件中第一个类声明之前，但`package`语句之后。

你可以使用通配符从包中导入所有类：

```java
import java.util.*;
```

通配符只能导入类，不能导入包。你不能使用`import java.*;`来获取所有以`java`开头的包。

当你导入多个包时，可能会发生命名冲突。例如，`java.util`和`java.sql`包都包含一个`Date`类。假设你导入了这两个包：

```java
import java.util.*;

import java.sql.*;
```

如果你的程序没有使用`Date`类，这不是问题。但如果你在不带包名的情况下引用`Date`，编译器会报错。

在这种情况下，你可以导入你需要的特定类：

```java
import java.util.*;

import java.sql.*;

import java.sql.Date;
```



如果你确实需要这两个类，你必须我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。其中一个使用全限定名。

### 注意

`import` 语句是为程序员提供的便利。 在类文件中，所有类名都是全限定的。

`import` 语句与 C 和 C++ 中的 `#include` 指令非常不同。后者包含了用于编译的头文件，而 `import` 则不会导致文件重新编译。它们只是缩短名称，类似于 C++ 的 `using` 语句。

## 2.6.6. 静态导入

`import` 语句的一种形式允许导入静态方法和变量。例如，如果你在源文件的顶部添加指令：

```java
import static java.lang.Math.*;
```

你就可以直接使用 `Math` 类的静态方法和静态变量，而不需要加类名前缀：

```java
area = 4 * PI * pow(r, 2); // 相当于 Math.PI, Math.pow
```

你也可以导入特定的静态方法或变量：

```java
import static java.lang.Math.PI;
import static java.lang.Math.pow;
```

### 注意

正如你在第 3 章和第 8 章中看到的，通常会对 `java.util.Comparator` 和 `java.util.stream.Collectors` 使用静态导入声明，因为它们提供了大量的静态方法。

## 2.7. 嵌套类

在前面的节中，你已经学习了如何将类组织到包中。或者，你可以将一个类放在另一个类的内部。这种类被称为`嵌套类`（nested class）。这可以用于限制可见性，或者避免用 `Element`、`Node` 或 `Item` 等通用名称弄乱包空间。Java 有两种嵌套类，其行为略有不同。让我们在接下来的章节中检查这两种。

### 2.7.1. 静态嵌套类

考虑一个为项目计费的 `Invoice` 类，每个项目都有描述、数量和单价。我们可以将 `Item` 成为嵌套类：

```java
public class Invoice {

    private static class Item { // Item 嵌套在 Invoice 内部

        String description;
        int quantity;
        double unitPrice;

        double price() { return quantity * unitPrice; }
    }

    private ArrayList<Item> items = new ArrayList<>();

    ...
}
```

在下一节之前，你可能还不清楚为什么这个内部类被声明为 `static`。目前，先接受它吧。

`Item` 类本身并没有特殊之处，除了访问控制。该类在 `Invoice` 中是私有的，所以只有 `Invoice` 方法可以访问它。出于这个原因，我没有费心将内部类的实例变量设为 `private`。

这里是一个构造内部类对象的方法示例：

```java
public class Invoice {

    ...

    public void addItem(String description, int quantity, double unitPrice) {

        var newItem = new Item();

        newItem.description = description;
        newItem.quantity = quantity;
        newItem.unitPrice = unitPrice;

        items.add(newItem);
    }
}
```

一个类可以将嵌套类设为 `public`。在这种情况下，人们会希望使用常用的封装机制。

```java
public class Invoice {

    public static class Item { // 一个公共的嵌套类

        private String description;
        private int quantity;
        private double unitPrice;

        public Item(String description, int quantity, double unitPrice) {
            this.description = description;
            this.quantity = quantity;
            this.unitPrice = unitPrice;
        }

        public double price() { return quantity * unitPrice; }

        ...
    }

    private ArrayList<Item> items = new ArrayList<>();

    public void add(Item item) { items.add(item); }

    ...
}
```

现在，任何人都可以通过使用限定名 `Invoice.Item` 来构造 `Item` 对象：

```java
var newItem = new Invoice.Item("Blackwell Toaster", 2, 19.95);
myInvoice.add(newItem);
```

这个 `Invoice.Item` 类与在任何其他类之外声明的 `InvoiceItem` 类在本质上没有区别。嵌套类只是让 `Item` 类代表发票中的项目变得显而易见。

### 2.7.2. 内部类

在前节中，你看到了一个声明为 `static` 的嵌套类。在这一节中，你将看到去掉 `static` 修饰符后会发生什么。这类类被称为`内部类`（inner classes）。

考虑一个社交网络，其中每个成员的朋友也是成员。

```java
public class Network {

    public class Member { // Member 是 Network 的内部类

        private String name;
        private ArrayList<Member> friends;

        public Member(String name) {
            this.name = name;
            friends = new ArrayList<>();
        }

        ...
    }

    private ArrayList<Member> members = new ArrayList<>();

    ...
}
```

去掉 `static` 修饰符后，存在着本质的区别。`Member` 对象知道自己属于哪个网络。让我们看看它是如何工作的。

首先，这里有一个向网络添加成员的方法：

```java
public class Network {

    ...

    public Member enroll(String name) {
        var newMember = new Member(name);
        members.add(newMember);
        return newMember;
    }
}
```

到目前为止，似乎并没有发生什么。我们可以添加一个成员并获取它的引用。

```java
var myFace = new Network();
Network.Member fred = myFace.enroll("Fred");
```

现在，假设 Fred 觉得这个网络不再火了，所以他想注销他的会员身份。

```java
fred.deactivate();
```

等等，让我们看看 `deactivate` 的实现：

```java
public class Network {

    public class Member {

        ...

        public void deactivate() {
            members.remove(this);
        }
    }

    private ArrayList<Member> members;

    ...
}
```

如所示，`members.remove(this)` 实际上意味着 `outer.members.remove(this)`，其中 `outer` 是外部类的引用。静态嵌套类没有引用（就像静态方法没有 `this` 引用）。当嵌套类的实例不需要知道属于哪个外部类实例时，使用静态嵌套类。只有当此信息很重要时才使用内部类。

内部类还可以通过其实例调用外部类的方法。例如，假设外部类有一个注销成员的方法。那么 `deactivate` 方法就可以调用它：

```java
public class Network {

    public class Member {

        ...

        public void deactivate() {
            unenroll(this);
        }
    }

    private ArrayList<Member> members;

    public Member enroll(String name) { ... }

    public void unenroll(Member m) { ... }

    ...
}
```

在这种情况下，`unenroll(this)` 实际上意味着 `outer.unenroll(this)`。

### 2.7.3. 内部类的特殊语法规则

在前节中，我通过称其为 *outer* 来解释了内部类对象的外部类引用。外部引用的实际语法有点复杂。`OuterClass.this` 表示外部类引用。例如，你可以这样编写 `Member` 内部类的 `deactivate` 方法：

```java
public void deactivate() {
    Network.this.members.remove(this);
}
```

在这种情况下，`Network.this` 语法并不是必要的。只需引用 `members` 就会隐式地使用外部类引用。但有时，你显式地需要外部类引用。这里有一个检查 `Member` 对象是否属于特定网络的方法：

```java
public class Network {

    public class Member {

        ...

        public boolean belongsTo(Network n) {
            return Network.this == n;
        }
    }
}
```

当你构造一个内部类对象时，它会记住构造它的外部类对象。在前面的节中，通过该方法创建了一个新成员：

```java
public class Network {

    ...

    Member enroll(String name) {

        Member newMember = new Member(name);

        ...

    }

}
```

这是以下内容的简写：

```java
Member newMember = this.new Member(name);
```

你可以在外部类的任何实例上调用内部类的构造函数：

```java
Network.Member wilma = myFace.new Member("Wilma");
```

### 注意

内部类可以有静态成员。内部类的静态方法可以访问其所属类以及外部类的静态成员。

### 注意

由于历史的偶然性，内部类是在虚拟机规范被认为已经完成时被引入 Java 语言的，因此它们被翻译成普通类，并带有一个指向外部类实例的隐藏实例变量。练习 15 邀请你探索这种转换机制。

### 注意

`Local classes`（局部类）是内部类的另一种变体，我们将在第 3 章中讨论。

## 2.8 文档注释

JDK 包含一个非常有用的工具名为 `javadoc`，它可以从你的源文件生成 HTML 文档。事实上，我们在第 1 章中描述的在线 API 文档仅仅是对标准 Java 库源码运行 `javadoc` 的结果。

如果你在源代码中添加了以特殊分隔符 `/**` 开头的注释，你也可以轻松地生成看起来很专业的文档。这是一个非常好的方法，因为它让你将代码和文档放在同一个地方。在过去那些糟糕的日子里，程序员经常将文档放在单独的文件中，代码和注释产生分离只是时间问题。当文档注释与源码位于同一个文件中时，更新两者并再次运行 `javadoc` 就变得容易了。

### 2.8.1. 注释插入

`javadoc` 工具会提取以下项目的信息：

- ![Images](img/sq.jpg) 公共类和接口
- ![Images](img/sq.jpg) 公有和保护的构造函数及方法
- ![Images](img/sq.jpg) 公有和保护的变量
- ![Images](img/sq.jpg) 包和模块

接口在第 3 章中介绍，保护性特性在第 4 章中介绍。

你可以（也应该）为这些特性每一个提供注释。每个注释都放置在其描述的特性的正上方。注释以 `/**` 开始并以 `*/` 结束。

每个 `/** ... */` 文档注释包含一段自由格式文本，后面紧跟标签。标签以 `@` 开头，例如 `@author` 或 `@param`。

自由格式文本的`第一句话`应该是一个总结性语句。`javadoc` 工具会自动生成提取这些句子的摘要页面。

在自由格式文本中，你可以使用 HTML 修饰符，例如使用 `<em>...</em>` 用于强调，使用 `<code>.../</code>` 用于等宽“打字机”字体，使用 `<strong>...</strong>` 用于加粗，甚至可以使用 `<img ...>` 来包含图像。然而，你应该避免使用标题 `<h*n*>` 或水平线 `<hr>`（注：此处应为`<hr>`），因为它们可能会干扰文档的格式。

### 注意

如果你的注释包含指向其他文件的链接（例如图像或用户界面组件的图像），请将这些文件放在包含源文件的目录的子目录下，命名为 `doc-files`。`javadoc` 工具会将 `doc-files` 目录及其内容从源目录复制到文档目录。你需要在链接中指定 `doc-files` 目录，例如 `<img src="doc-files/uml.png" alt="UML diagram"/>`。

### 2.8.2. 类注释

类注释必须直接放置在类声明之前。你可能想用 `@author` 和 `@version` 标签记录类的作者和版本。可以有多个作者。

这是一个类注释的示例：

```java
/**
 * 一个 <code>Invoice</code> 对象代表一个发票，
 * 包含订单中每个部分的行项目目。
 * @author Fred Flintstone
 * @author Barney Rubble
 * @version 1.1
 */
public class Invoice {
    ...
}
```

### 注意

没有必要在每一行前面放一个 `*`。然而，大多数 IDE 会自动提供星号，有些甚至在换行发生变化时重新排列它们。

### 2.8.3. 方法注释

将每个方法注释直接放置在其方法之前。文档以下特性：

- ![Images](img/sq.jpg) 每个参数，带有一个注释 `@param` `变量描述`
- ![Images](img/sq.jpg) 返回值，如果不是 `void`：`@return` `描述`
- ![Images](img/sq.jpg) 任何抛出的异常（参见第 5 章）：`@throws` `异常类描述`

这是一个方法注释的示例：

```java
/**
 * 提高员工薪资。
 * @param byPercent 增加薪资的百分比（例如 10 表示 10%）
 * @return 增加的金额
 */
public double raiseSalary(double byPercent) {
    double raise = salary * byPercent / 100;
    salary += raise;
    return raise;
}
```

### 2.8.4. 变量注释

你只需要对常量进行文档。例如：

```java
/**
 * 每年的天数（不包括闰年）
 */
public static final int DAYS_PER_YEAR = 365;
```

### 2.8.5. 普通注释

在所有文档注释中，你可以使用 `@since` 标签来描述该特性出现的版本：

```text
@since 1.7
```

`@deprecated` 标签添加该类、方法或变量不再应使用的注释。文本应该建议一个替代方案。例如：

```text
@deprecated 改用 setVisible(true)
```

### 注意

还有一个 `@Deprecated` 注解，在使用废弃项时发出警告——参见第 11 章。该注解没有建议替代方案的机制，因此你应该同时提供注解和文档注释。

### 2.8.6. 链接

你可以使用 `@see` 和 `@link` 标签指向文档的其他部分或外部文档。

`@see` 引用会在“参见”部分添加超链接。这里的引用可以是以下之一：

- `package.Class#feature`
- `<a href="...">label</a>`

第一种情况是最常用的。你提供类、方法或变量的名称，`javadoc` 会为其插入指向其文档的超链接。例如：

```text
@see com.horstmann.corejava.Employee#raiseSalary(double)
```



指向`com.horstmann.corejava.Employee`类中的`raiseSalary(double)`方法。你可以省略包名或包和类名。那么该特性将位于当前包或类中。

注意必须使用`#`而不是点来分隔类和方法名。Java编译器本身非常擅长猜测点作为包、子包、类、内部类及其方法和变量分隔符的各种含义。但`javadoc`工具并不那么聪明，所以你必须帮助它。

如果`@see`标签后面跟着`<`字符，你正在指定一个超链接。你可以链接到任何喜欢的URL。例如：`@see <a href="http://en.wikipedia.org/wiki/Leap_year">Leapyears</a>`。

在这些情况下，你都可以指定一个可选标签作为链接锚点。如果你省略了标签，用户将看到目标代码名称或URL作为锚点。

如果`@see`标签后跟着一个引号字符`"`，则引号内的文本将显示在“另”（see also）部分。例如：

```
@see "Core Java for the Impatient"
```

你可以为一个功能添加多个`@see`标签，但必须将它们都放在一起。

如果你愿意，可以在文档注释的任何位置放置指向其他类或方法的超链接。在注释中插入如下形式的标签：

```
{@link  package.class#feature label}
```

在注释的任何位置均可。功能的描述遵循与`@see`标签相同的规则。

### 2.8.7. 包、模块和概览注释

类、方法和变量注释直接放置在Java源文件中，用`/** ... */`分隔。然而，要生成包注释，你需要在每个包目录下添加一个单独的文件。

提供一个名为`package-info.java`的Java文件。该文件必须包含一个初始的javadoc注释（用`/**`和`*/`分隔），随后跟一个包声明语句（package statement）。它不应包含任何额外的代码或注释。

要文档一个模块，请将注释放入`module-info.java`中。你可以包含`@moduleGraph`指令来包含模块依赖图。（参见第15章关于模块和`module-info.java`文件的介绍。）

你还可以为所有源文件提供一个概览注释。将其放置在名为`overview.html`的文件中，位于包含所有源文件的父目录下。`<body>...</body>`标签之间的所有文本会被提取。当用户从导航栏选择“概览”（Overview）时，会显示此注释。

### 2.8.8. 注释提取

在这里，`docDirectory`是你希望HTML文件所在的目录名称。按照以下步骤操作：

1. 切换到包含要所需的源文件的目录。如果你有需要文档化的嵌套包，例如`com.horstmann.corejava`，你必须在包含子目录`com`的目录中运行。（如果你提供了`overview.html`文件，这就是它所在的目录。）

2. 运行命令

```
javadoc -d docDirectory package1 package2 ...
```

如果你省略了`-d docDirectory`选项，HTML文件将提取到当前目录。这可能会导致变得很混乱，因此我不建议这样做。

`javadoc`程序可以通过许多命令行选项进行精细调整。例如，你可以使用`-author`和`-version`选项在文档中包含`@author`和`@version`标签。（默认情况下，它们会被省略。）

另一个有用的选项是`-link`，用于包含指向标准类的超链接。例如，如果你运行命令：

```
javadoc -link http://docs.oracle.com/javase/17/docs/api *.java
```

所有标准库类都将自动链接到Oracle网站上的文档。

如果你使用`-linksource`选项，每个源文件将转换为HTML，并且每个类和方法名都将变为指向源码的超链接。

### 练习

1. 修改日历打印程序，使其从周日开始一周。同时，让它在结尾打印换行符（但仅限一个）。

2. 考虑`Scanner`类的`nextInt`方法。它是访问器（accessor）还是修改器（mutator）？为什么？`Random`类的`nextInt`方法又是呢？

3. 修改器方法可以返回`void`以外的类型吗？访问器方法可以返回`void`吗？尽可能给出示例。

4. 为什么你不能实现一个交换两个`int`变量内容的Java方法？相反，写一个交换两个`IntHolder`对象内容的方法。（在API文档中查找这个相当冷门的类。）你可以交换两个`Integer`对象的内容吗？

5. 为`Point`记录（record）添加`translate`和`scale`方法。`translate`方法根据给定的数值在`x`方向和`y`方向上移动点。`scale`方法根据给定的因子缩放两个坐标。实现这些方法，使它们返回带有结果的新点。例如：

```
Point p = new Point(3, 4).translate(1, 3).scale(0.5);
```

应该将`p`设置为坐标为(2, 3.5)的点。

6. 重复前面的练习，但现在将`Point`实现为类（class），并将`translate`和`scale`改为修改器。

7. 在前面的练习中，提供`Point`类的构造函数和getter方法相当重复的。大多数IDE都有编写样板代码的快捷键。你的IDE提供什么？

8. 为前面练习中两个版本的`Point`类添加`javadoc`注释。

9. 实现一个带有`hour`和`minute`组件的记录`TimeOfDay`。对它们进行归一化，小时在0到23之间，分钟在0到59之间。提供方法`TimeOfDay plusMinutes(int minutes)`，返回一个距离给定分钟数的`TimeOfDay`对象，以及方法`int minutesFrom(TimeOfDay other)`，返回此实例与给定的`TimeOfDay`实例之间的分钟数。

10. 实现一个`Car`类，模拟沿`x`轴行驶的汽车，移动时消耗燃料。提供方法行驶指定的英里、向燃油箱添加指定的加仑，以及获取距离原点的距离和燃料水平的方法。指定油耗（英里/加仑）。这应该是静态的（static）还是不是？

11. 在`RandomNumbers`类中提供静态方法`randomElement`，从数组中获取随机元素。（如果数组为空则返回0。）你可以将这些改为实例方法吗？

12. 重写`Cal`类以使用`System`和`LocalDate`的静态导入。

13. 在`ch01`包中创建一个文件`HelloWorld.java`，声明类`HelloWorld`。将其放入某个目录。从该目录运行`javac HelloWorld.java`。得到类文件了吗？然后运行`java HelloWorld`。发生了什么？（提示：运行`javap`。）最后，尝试`javac -d . HelloWorld.java`。为什么更好？

14. 从[`https://commons.apache.org/proper/commons-csv/index.html`](https://commons.apache.org/proper/commons-csv/index.html)下载Apache CSV的JAR文件。写一个带有main方法的类，读取你选择的CSV文件并打印其内容。你还没有学习处理异常。只需使用以下头部：

```
public static void main(String[] args) throws Exception
```

此练习的目的不是对CSV文件进行任何有用操作，而是练习使用以JAR交付的库。

15. 编译`Network`类。注意内部类名为`Network$Member.class`。使用`javap`程序查看生成的代码。命令

```
javap -private Classname
```

显示方法和实例变量。你在哪里看到对外部类的引用？（在Linux/Mac OS上，运行`javap`时需要在`$`符号前加上`\`。）

16. 完整实现第2.7.1节中的`Invoice`类。提供一个打印发票的方法和一个构造并打印示例程序。

17. 实现类`Queue`，一个无界字符串队列。提供方法`add`（在尾添加）和`remove`（从头部移除）。使用链表节点存储元素。将`Node`实现为嵌套类。它应该是静态的还是不是？

18. 为前面的类队列提供一个迭代器（iterator）——一个按顺序产生元素的对象。将`Iterator`实现为嵌套类，带有`next`和`hasNext`方法。为`Queue`类提供方法`iterator()`以产生`Queue.Iterator`。`Iterator`应该是静态的还是不是？

## 引言

Java设计于20世纪90年，是一种面向对象的编程语言，当时面向对象编程是软件开发的主要范式。接口（Interfaces）是面向对象编程的关键特性：它们允许你指定“要做什么”，而无需提供具体的实现。

在面向对象编程出现很久，就已经存在函数式编程语言，例如`Lisp`，在这些语言中，函数而不是对象主要的结构机制。最近，函数式编程的重要性日益提高，因为它非常适合并发和事件驱动（或“响应式”）编程。Java支持函数表达式，为面向对象编程和函数式编程之间提供了便利的桥梁。在本章中，你将学习接口和Lambda表达式。

本章的关键点包括：

1. 接口规定了实现类必须提供的一组方法。
2. 接口是任何实现类的超类型。因此，可以将类的实例赋值给接口类型的变量。
3. 接口可以包含静态方法。接口的所有变量自动为`public`、`static`且`final`。
4. 接口可以包含默认方法，实现类可以继承或重写这些方法。
5. 接口可以包含私有方法，实现类无法调用或重写。
6. `Comparable`和`Comparator`接口用于比较对象。
7. 如果你需要测试对象是否符合某个子类型，请使用`instanceof`运算符，最好使用其“模式匹配”形式。
8. 函数式接口（Functional interface）是一个只有一个抽象方法的接口。
9. Lambda表达式表示一个可以在以后某个时刻执行的代码块。
10. Lambda表达式会被转换为函数式接口。
11. 方法和构造函数引用指向方法或构造函数，但不调用它们。
12. Lambda表达式和局部类可以访问闭包作用域中的有效最终变量（effectively final）变量。

### 3.1. 接口

`interface`是一种用于规定双方之间合同的机制：服务的提供者以及希望其对象可用于服务的类。在接下来的章节中，你将看到如何在Java中定义和使用接口。

### 3.1.1 使用接口

在前两个章节中，我使用了`Random`类来演示如何调用构造函数和方法。当`Random`类在Java 1.0中被首次设计时，它反映了当时的技术水平。如今，已知有许多产生伪随机数的算法。`java.util.random`包提供了具有各种权衡的强算法实现。根据你的需求，你可能需要在`L64X128MixRandom`、`Xoroshiro128PlusPlus`或另一个具有类似名称的算法之间选择。（该包的API文档提供了关于选择哪种算法的有用建议。）有趣的是，API并没有为每个算法暴露单独的类。这是一个好事。每当你从一种算法切换到另一种算法时，修改程序将很麻烦。而且这是没必要的——所有的生成器都拥有相同的方法集：`nextInt`、`nextDouble`等。

相反，这些方法属于一个`RandomGenerator`接口。接口定义了支持的方法——在这里是`nextInt`、`nextDouble`等。一旦你拥有一个`implements`该接口的类的实例，你就可以调用这些方法：

```
RandomGenerator generator = RandomGenerator.of("L64X128MixRandom");
int dieToss = 1 + generator.nextInt(6);
double randomPercentage = 100 * generator.nextDouble();
```

静态方法`RandomGenerator.of`获取某个类的对象，调用者不知道该类的确切类型。已知的是该类拥有`RandomGenerator`接口的所有方法。有了这些知识，你就可以高效地使用该对象。

### 3.1.2 声明接口

在本节中，你将学习如何声明你自己的接口。让我们考虑一种不同的接口。接口规定了实现类必须提供的一组方法。接口是任何实现类的超类型。因此，可以将类的实例赋值给接口类型的变量。接口可以包含静态方法。接口的所有变量自动为`public`、`static`且`final`。接口可以包含默认方法，实现类可以继承或重写这些方法。接口可以包含私有方法，实现类无法调用或重写。`Comparable`和`Comparator`接口用于比较对象。如果你需要测试对象是否符合某个子类型，请使用`instanceof`运算符，最好使用其“模式匹配”形式。函数式接口是一个只有一个抽象方法的接口。Lambda表达式表示一个可以在以后某个时刻执行的代码块。Lambda表达式会被转换为函数式接口。方法和构造函数引用指向方法或构造函数，但不调用它们。Lambda表达式和局部类可以访问闭包作用域中的有效最终变量变量。

本章的关键点包括：

1. 接口规定了实现类必须提供的一组方法。
2. 接口是任何实现类的超类型。因此，可以将类的实例赋值给接口类型的变量。
3. 接口可以包含静态方法。接口的所有变量自动为`public`、`static`且`final`。
4. 接口可以包含默认方法，实现类可以继承或重写这些方法。
5. 接口可以包含私有方法，实现类无法调用或重写。
6. `Comparable`和`Comparator`接口用于比较对象。
7. 如果你需要测试对象是否符合某个子类型，请使用`instanceof`运算符，最好使用其“模式匹配”形式。
8. 函数式接口是一个只有一个抽象方法的接口。
9. Lambda表达式表示一个可以在以后某个时刻执行的代码块。
10. Lambda表达式会被转换为函数式接口。
11. 方法和构造函数引用指向方法或构造函数，但不调用它们。
12. Lambda表达式和局部类可以访问闭包作用域中的有效最终变量变量。

（注：此处发现原文中存在部分重复描述，已根据指令“不要重复输出原文”的原则在翻译时进行了逻辑对齐处理。）

`interface`是一种用于规定双方之间合同的机制：服务的提供者以及希望其对象可用于服务的类。在接下来的章节中，你将看到如何在Java中定义和使用接口。

### 3.1.1 使用接口

在前两个章节中，我使用了`Random`类来演示如何调用构造函数和方法。当`Random`类在Java 1.0中被首次设计时，它反映了当时的技术水平。如今，已知有许多产生伪随机数的算法。`java.util.random`包提供了具有各种权衡的强算法实现。根据你的需求，你可能需要在`L64X128MixRandom`、`Xoroshiro128PlusPlus`或另一个具有类似名称的算法之间选择。（该包的API文档提供了关于选择哪种算法的有用建议。）有趣的是，API并没有为每个算法暴露单独的类。这是一个好事。每当你从一种算法切换到另一种算法时，修改程序将很麻烦。而且这是没必要的——所有的生成器都拥有相同的方法集：`nextInt`、`nextDouble`等。

相反，这些方法属于一个`RandomGenerator`接口。接口定义了支持的方法——在这里是`nextInt`、`nextDouble`等。一旦你拥有一个`implements`该接口的类的实例，你就可以调用这些方法：

```
RandomGenerator generator = RandomGenerator.of("L64X128MixRandom");
int dieToss = 1 + generator.nextInt(6);
double randomPercentage = 100 * generator.nextDouble();
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```

## 3.1 接口

### 3.1.1 使用接口

在前两个章节中，我使用了`Random`类来演示如何调用构造函数和方法。当`Random`类在 Java 1.0 中被首次设计时，它反映了当时的技术水平。如今，已知有许多产生伪随机数的算法。`java.util.random`包提供了具有各种权衡的强算法实现。根据你的需求，你可能需要在`L64X128MixRandom`、`Xoroshiro128PlusPlus`或另一个具有类似名称的算法之间选择。（该包的 API 文档提供了关于选择哪种算法的有用建议。）有趣的是，API 并没有为每个算法暴露单独的类。这是一个好事。每当你从一种算法切换到另一种算法时，修改程序将很麻烦。而且这是没必要的——所有的生成器都拥有相同的方法集：`nextInt`、`nextDouble`等。

相反，这些方法属于一个`RandomGenerator`接口。接口定义了支持的方法——在这里是`nextInt`、`nextDouble`等。一旦你拥有一个`implements`该接口的类的实例，你就可以调用这些方法：

```java
RandomGenerator generator = RandomGenerator.of("L64X128MixRandom");
int dieToss = 1 + generator.nextInt(6);
double randomPercentage = 100 * generator.nextDouble();
```

静态方法`RandomGenerator.of`获取某个类的对象，调用者不知道该类的确切类型。已知的是该类拥有`RandomGenerator`接口的所有方法。有了这些知识，你就可以高效地使用该对象。

### 3.1.2 声明接口

在本节中，你将学习如何声明你自己的接口。接口规定了实现类必须提供的一组方法。接口是任何实现类的超类型。因此，可以将类的实例赋值给接口类型的变量。接口可以包含静态方法。接口的所有变量自动为`public`、`static`且`final`。接口可以包含默认方法，实现类可以继承或重写这些方法。接口可以包含私有方法，实现类无法调用或重写。`Comparable`和`Comparator`接口用于比较对象。如果你需要测试对象是否符合某个子类型，请使用`instanceof`运算符，最好使用其“模式匹配”形式。函数式接口是一个只有一个抽象方法的接口。Lambda 表达式表示一个可以在以后某个时刻执行的代码块。Lambda 表达式会被转换为函数式接口。方法和构造函数引用指向方法或构造函数，但不调用它们。Lambda 表达式和局部类可以访问闭包作用域中的有效最终变量。

`interface`是一种用于规定双方之间合同的机制：服务的提供者以及希望其对象可用于服务的类。在接下来的章节中，你将看到如何在 Java 中定义和使用接口。

```java
public interface IntSequence {
    boolean hasNext();
    int next();
}
```

### 3.1.3 实现接口

现在让我们看看硬币的另一面：那些希望用于`average`方法的类。它们需要`implement` `IntSequence`接口。这里有这样一个类：

```java
public class SquareSequence implements IntSequence {
    private int i;
    public boolean hasNext() {
        return true;
    }
    public int next() {
        i++;
        return i * i;
    }
}
```

有无限多个平方数，该类的对象可以一次提供它们中的任意一个。（为了保持示例简单，我们忽略了整数溢出——见练习 6。）

`implements`关键字表示`SquareSequence`类意图符合`IntSequence`接口。

> **注意**  
> 实现类必须将接口的方法声明为`public`。否则，它们将默认为包级访问。由于接口要求公共访问，编译器将报告错误。

这段代码获取前 100 个平方数的平均值：

```java
var squares = new SquareSequence();
double avg = average(squares, 100);
```

有很多类可以实现`IntSequence`接口。例如，这个类产生一个有限序列，即正整数的数字，从最低位开始：

```java
public class DigitSequence implements IntSequence {
    private int number;
    public DigitSequence(int n) {
        number = n;
    }
    public boolean hasNext() { // 此方法和后续方法在接口中声明
        return number != 0;
    }
    public int next() {
        int result = number % 10;
        number /= 10;
        return result;
    }
    public int rest() { // 此方法在接口中声明
        return number;
    }
}
```

一个`new DigitSequence(1729)`对象在`hasNext`返回`false`之前会交付数字`9 2 7 1`。

> **注意**  
> `SquareSequence`和`DigitSequence`类实现了`IntSequence`接口的所有方法。如果一个类只实现部分方法，则它必须使用`abstract`修饰符对其进行声明。关于抽象类的更多信息，请参阅第 4 章。

### 3.1.4 转换为接口类型

这段代码片段计算了数字序列值的平均值：

```java
IntSequence digits = new DigitSequence(1729);
double avg = average(digits, 100);
// 只会查看前四个序列值
```

观察`digits`变量。它的类型是`IntSequence`，而不是`DigitSequence`。类型为`IntSequence`的变量引用实现了`IntSequence`接口的某个类的对象。你始终可以将对象赋值给类型为已实现接口的变量，或者将其传递给期望该接口的方法。

这里有一些实用的术语。当子类型的任何值都可以在无需转换的情况下赋值给超类型的变量时，类型`S`就是类型`T`（子类型）的**超类型**（supertype）。例如，`IntSequence`接口是`DigitSequence`类的超类型。

> **注意**  
> 尽管可以声明接口类型的变量，但你永远无法拥有类型为接口的对象。所有对象都是类的实例。

### 3.1.5 强制类型转换与`instanceof`运算符

有时，你需要相反的转换——从超类型到子类型。这时你使用**强制转换**（cast）。例如，如果你恰好知道存储在`IntSequence`中的对象实际上是`DigitSequence`，你可以这样转换类型：

```java
IntSequence sequence = ...;
DigitSequence digits = (DigitSequence) sequence;
System.out.println(digits.rest());
```

在这种情况下，强制转换是必要的，因为`rest`是`DigitSequence`的方法，而不是`IntSequence`的方法。

请参见练习 2 以获得更有说服力的例子。

你只能将对象强制转换为其实际类或其超类型之一。如果你错了，就会发生编译时错误或类转换异常（class cast exception）：

```java
String digitString = (String) sequence;
// 不可能成功——IntSequence 不是 String 的超类型
RandomSequence randoms = (RandomSequence) sequence;
// 可能成功，如果不符合则会抛出类转换异常
```

为了避免异常，你可以先使用`instanceof`运算符测试该对象是否属于目标类型。表达式

```java
object instanceof Type
```

如果`object`是一个以`Type`为超类型的类的实例，则该表达式返回`true`。在使用强制转换之前进行此项检查是一个好主意。

```java
if (sequence instanceof DigitSequence) {
    DigitSequence digits = (DigitSequence) sequence;
    ...
}
```

> **注意**  
> `instanceof`运算符是`null`安全的：如果`obj`为`null`，则表达式`obj instanceof Type`为`false`。毕竟，`null`绝不可能是任何给定类型对象的引用。

### 3.1.6 `instanceof`的“模式匹配”形式

由于“`instanceof`和强制转换”这种惯用法非常常见，因此有一个方便的快捷方式，称为`instanceof`模式匹配：

```java
if (sequence instanceof DigitSequence digits) {
    // 在这里，你可以使用 digits 变量
    ...
}
```

在这个示例中，`digits`变量包含了被强制转换为`DigitSequence`的`sequence`引用。然而，如果`sequence`不是`DigitSequence`的实例，则不会声明变量，且不会执行`if`主体。

无用的`instanceof`模式是一个错误：

```java
DigitSequence digits = ...;
if (digits instanceof IntSequence seq) ... // 错误——显然它是一个 IntSequence
```

> **注意**  
> 同样无用的
> ```java
> if (digits instanceof IntSequence) ...
> ```
> 是允许的，为了与 Java 1.0 向后兼容。

当`instanceof`模式引入一个变量时，你可以在同一个表达式中立即使用它：

```java
IntSequence sequence = ...;
if (sequence instanceof DigitSequence digits && digits.rest() >= 100) ...
```

这之所以有效，是因为`&&`表达式的右侧只有在左侧为`true`时才会被求值。如果求值了右侧，则`digits`已经绑定到了`DigitSequence`实例。

然而，以下是编译时错误：

```java
if (sequence instanceof DigitSequence digits || digits.rest() >= 100) ... // 错误
```

当`||`的左侧为`false`时会执行右侧，此时没有内容绑定到变量`digits`。

这里是另一个使用条件运算符的例子：

```java
double rest = sequence instanceof DigitSequence digits ? digits.rest() : 0;
```

变量`digits`定义在`?`之后的子表达式中，但未定义`:`之后的子表达式中。

> **注意**  
> 这种声明变量的`instanceof`形式被称为“模式匹配”（pattern matching），因为它与`switch`中的类型模式（type patterns）相似，这是 Java 17 的一项“预览”功能。我不会详细讨论预览性功能，但这里有一个语法的示例：
> ```java
> String description = switch (sequence) {
>     case DigitSequence digits -> "digit sequence " + digits.rest();
>     case SquareSequence squares -> "square sequence";
>     default -> "other sequence";
> }
> ```

### 3.1.7 接口的扩展

接口可以扩展另一个接口，在原有接口的基础上提供额外的方法。例如，`Closeable`是一个有一个方法的接口：

```java
public interface Closeable {
    void close();
}
```

正如你在第 5 章中看到的，这是一个发生异常时关闭资源的接口。

`Channel`接口扩展了这个接口：

```java
public interface Channel extends Closeable {
    boolean isOpen();
}
```

实现`Channel`接口的类必须提供这两个方法，并且它可以转换为这两个接口类型。

### 3.1.8 实现多个接口

类可以实现任意数量的接口。例如，一个从文件读取整数的`FileSequence`类除了`IntSequence`之外还实现了`Closeable`：

```java
public class FileSequence implements IntSequence, Closeable {
    ...
}
```

那么`FileSequence`类拥有`IntSequence`和`Closeable`超类型。

### 3.1.9 常量

接口中定义的任何变量都是`public static final`。

例如，`SwingConstants`接口定义了方向的常量：

```java
public interface SwingConstants {
    int NORTH = 1;
    int NORTH_EAST = 2;
    int EAST = 3;
    ...
}
```

你可以通过限定名称引用它们，即`SwingConstants.NORTH`。如果你的类选择了实现`SwingConstants`接口，你可以省略`SwingConstants`限定符直接写`NORTH`。然而，这并不是常见的惯用法。对于常量集，使用枚举要好得多；参见第 4 章。

> **注意**  
> 接口中不能有实例变量。接口规范行为而非对象状态。

## 3.2 静态、默认和私有方法

在 Java 早期版本中，接口的所有方法都必须是抽象的——没有方法体。现在你可以添加三种具有具体实现的方法：静态方法、默认方法和私有方法。接下来的章节将描述这些方法。

### 3.2.1 静态方法

技术上接口从未不能拥有静态方法，但它们不符合接口作为抽象规范的观点。这种想法现在已经演变。特别是工厂方法在接口中非常有意义。例如，`IntSequence`接口可以有一个静态方法`digitsOf`，用于生成给定整数的数字序列：

```java
IntSequence digits = IntSequence.digitsOf(1729);
```

该方法产生一个实现了`IntSequence`接口的类实例，但调用者无需关心具体是哪一个。

```java
public interface IntSequence {
    ...
    static IntSequence digitsOf(int n) {
        return new DigitSequence(n);
    }
}
```

> **注意事项**  
> 在过去，将静态方法放在伴侣类中是常见的做法。在 Java API 中，你会发现接口和工具类的成对，例如`Collection`/`Collections`或`Path`/`Paths`。这种划分不再是必要的。

### 3.2.2 默认方法

你可以为任何接口方法提供一个`default`实现。你必须使用`default`修饰符来标记此类方法。

```java



`public interface IntSequence` {

    `default boolean hasNext() { return true; }`

        // 默认情况下，序列是无限的

    `int next();`

}

实现此接口的类可以选择重写`hasNext`方法，也可以继承默认实现。

### 注意事项

默认方法结束了一种经典模式，即提供一个接口和一个实现其大部分或所有方法的伴侣类，例如 Java API 中的`Collection`/`AbstractCollection`或`WindowListener`/`WindowAdapter`。现在你只需要在接口中实现方法即可。

默认方法的一个重要用途是*接口演进*。考虑例如在 Java 中存在多年的`Collection`接口。假设在很久以前，你提供了一个类：

```java
public class Bag implements Collection
```

后来在 Java 8 中，接口增加了一个`stream`方法。

假设`stream`方法不是默认方法。那么`Bag`类将无法编译，因为它没有实现这个新方法。在接口中添加非默认方法不是*源码兼容*的。

但假设你没有重新编译该类，而是直接使用包含它的旧 JAR 文件。即使缺少该方法，类仍然可以加载。程序仍然可以创建`Bag`实例，且不会发生任何问题。（向接口中添加方法是`二进制兼容`的。）然而，如果一个程序在`Bag`实例上调用`stream`方法，就会发生`AbstractMethodError`。

将该方法设为`default`方法解决了这两个问题。`Bag`类将能够再次编译。如果该类在没有重新编译的情况下被加载，并且在`Bag`实例上调用了`stream`方法，则会调用`Collection.stream`方法。

### 3.2.3. 解析默认方法冲突

如果一个类实现了两个接口，其中一个有一个默认方法，另一个接口具有相同名称和参数类型的方法（无论是否是默认方法），你必须解决这个冲突。这种情况并不经常发生，而且处理起来通常很容易。

让我们来看一个例子。假设我们有一个接口`Person`，它包含一个`getId`方法：

```java
public interface Person {
    String getName();
    default int getId() { return 0; }
}
```

假设有另一个接口`Identified`，它也有类似的方法。

```java
public interface Identified {
    default int getId() {
        return Math.abs(hashCode());
    }
}
```

你将在第 4 章中看到`hashCode`方法的作用。目前，重要的是它返回一个派生自对象的整数。

如果你形成了一个同时实现这两个接口的类，会发生什么？

```java
public class Employee implements Person, Identified {
    ...
}
```

该类继承了由`Person`和`Identified`接口提供的两个`getId`方法。Java 编译器无法在两者之间选择一个。编译器会报告错误，并将解决歧义的任务留给给你。在`Employee`类中提供一个`getId`方法，并实现你自己的 ID 方案，或者委托给冲突方法中的其中一个，如下：

```java
public class Employee implements Person, Identified {
    public int getId() { return Identified.super.getId(); }
    ...
}
```

### 注意事项

`super`关键字允许你调用超类型方法。在这种情况下，我们需要指定想要用哪个超类型。这种语法看起来可能有点奇怪，但它与你在第 4 章中看到的调用父类方法的语法是一致的。

现在假设`Identified`接口没有为`getId`提供默认实现：

```java
interface Identified {
    int getId();
}
```

`Employee`类可以继承来自`Person`接口的默认方法吗？乍一看，这似乎是合理的。但编译器如何知道`Person.getId`方法是否真的实现了`Identified.getId`预期的功能呢？毕竟，它返回的可能是人的弗洛伊德 id 层级，而不是 ID 号。

Java 的设计者选择了安全和统一。两个接口如何冲突并不重要；只要至少有一个接口提供了实现，编译器就会报告错误，并由程序员来解决歧义。

### 注意事项

如果两个接口都没有为共享方法提供默认实现，那么不存在冲突。实现类有两个选择：实现该方法，或者将其留为未实现并将类声明为`abstract`。

### 注意事项

如果一个类继承自一个父类（参见第 4 章

`static of(int a, int b)`

`static of(int a, int b, int c)`

那么这些方法都可以调用一个辅助方法：

```java
private static IntSequence makeFiniteSequence(int... values) { ... }
```

### 3.3 接口示例

乍一看，接口似乎并没有做什么。接口仅仅是类承诺实现的方法集。为了让接口的重要性更加具体，接下来的章节将展示 Java API 中的四个常用接口示例。

### 3.3.1. Comparable 接口

假设你想对数组进行排序。排序算法反复比较元素，如果顺序不对则进行重新排列。当然，比较的规则对于每个类都是不同的，排序算法应该只调用类提供的方法。只要所有类对该方法的名称达成一致，排序算法就能完成工作。这就是接口大显身的地方。

如果一个类想要对其对象启用排序，它应该实现`Comparable`接口。关于这个接口有一个技术点。我们想要比较字符串之间、员工之间，以及等等。因此，`Comparable`接口有一个类型参数。

```java
public interface Comparable<T> {
    int compareTo(T other);
}
```

例如，`String`类实现了`Comparable<String>`，以便其`compareTo`方法的签名变为：

```java
int compareTo(String other)
```

### 注意事项

带有类型参数（如`Comparable`或`ArrayList`）的类型是泛型类型。你将在第 6 章中学习关于泛型类型的全部知识。

当调用`x.compareTo(y)`时，`compareTo`方法返回一个整数值，指示`x`或`y`应该排在前面。返回正值（不一定是`1`）表示`x`应该在`y`之后。当`x`应该在`y`之前时，返回一个负整数（不一定是`-1`）。如果`x`和`y`被认为相等，则返回值为`0`。

请注意，返回值可以是任何整数。这种灵活性非常有用，因为它允许你返回两个整数之间的差值。只要差值不会产生整数溢出，这种方法非常方便。

```java
public class Employee implements Comparable<Employee> {
    ...
    public int compareTo(Employee other) {
        return getId() - other.getId(); // 如果 ID 始终 ≥ 0，则可行
    }
}
```

### 注意事项

返回整数的差值并不总是有效。对于符号相反的大操作数，差值可能会溢出。在这种情况下，请使用`Integer.compare`方法，它对所有整数都能正常工作。不过，如果你知道整数是非负的，或者它们的绝对值小于`Integer.MAX_VALUE / 2`，那么使用差值就可以了。

在比较浮点值时，你不能直接返回差值。相反，请使用静态方法`Double.compare`。即使对于`±∞`和`NaN`它也能正确处理。

以下是`Employee`类如何实现`Comparable`接口，按工资对员工进行排序：

```java
public class Employee implements Comparable<Employee> {
    ...
    public int compareTo(Employee other) {
        return Double.compare(salary, other.salary);
    }
}
```

### 注意

`compare`方法访问`other.salary`是完全合。在 Java 中，方法可以访问所属类的任何对象的私有属性。

`String`类以及 Java 库中的其他百多个类都实现了`Comparable`接口。你可以使用`Arrays.sort`方法对`Comparable`对象的数组进行排序：

```java
String[] names = { "Peter", "Paul", "Mary" };
Arrays.sort(names); // names 现在是 ["Mary", "Paul", "Peter"]
```

### 注意

奇怪的是，`Arrays.sort`方法在编译时并不检查参数是否是`Comparable`对象的数组。相反，如果它遇到没有实现`Comparable`接口的类的元素，会抛出异常。

### 3.3.2. `Comparator`接口

现在假设我们想要按长度递增对字符串进行排序，而不是按字典顺序。我们无法让`String`类以两种方式实现`compareTo`方法——而且无论如何，`String`类也不是由我们修改。

为了处理这种情况，`Arrays.sort`方法有第二个版本，其参数是一个数组和一个比较器——比较器是一个实现了`Comparator<T>`接口的类实例，该接口包含以下抽象方法：

```java
int compare(T first, T second);
```

按长度比较字符串，定义一个实现`Comparator<String>`的类：

```java
class LengthComparator implements Comparator<String> {
    public int compare(String first, String second) {
        return first.length() - second.length();
    }
}
```

要实际执行比较，你需要创建一个实例：

```java
Comparator<String> comp = new LengthComparator();
if (comp.compare(names[i], names[j]) > 0) ...
```

将此调用与`names[i].compareTo(names[j])`进行对比。`compare`方法是在比较器对象上调用的，而不是在字符串本身上。

### 注意

即使`LengthComparator`对象没有状态，你仍然需要创建一个实例。你需要该实例来调用`compare`方法——它不是一个静态方法。

要对数组排序，将`LengthComparator`对象传递给`Arrays.sort`方法：

```java
String[] names = { "Peter", "Paul", "Mary" };
Arrays.sort(names, new LengthComparator());
```

现在数组是`["Paul", "Mary", "Peter"]`或`["Mary", "Paul", "Peter"]`。

你将在第 3.4.2 节中看到如何使用 lambda 表达式更方便地使用`Comparator`。

### 3.3.3. `Runnable`接口

在几乎处理器都有多个内核时代，你想让这些核心忙起来。你可能希望在单独的线程运行某些任务，或者将它们交给线程池执行。要定义任务，你需要实现`Runnable`接口。该接口只有一个方法。

```java
class HelloTask implements Runnable {
    public void run() {
        for (int i = 0; i < 1000; i++) {
            System.out.println("Hello, World!");
        }
    }
}
```

如果你想在新线程中执行此任务，请从`Runnable`创建线程并启动它。

```java
Runnable task = new HelloTask();
Thread thread = new Thread(task);
thread.start();
```

现在`run`方法在单独的线程中执行，当前线程可以继续其他工作。

### 注意

在第 10 章中，你将看到执行`Runnable`的其他方法。

### 注意

还有一个`Callable<T>`接口，用于返回结果的任务。

### 3.3.4. 回调函数

在图形界面中，你需要在用户点击按钮、选择菜单选项、拖动滑块时指定操作。这些操作通常被称为回调，因为当操作发生时，某些代码会被调用。

在 Java 的 GUI 中，使用了接口。例如，在 Swing 中使用以下接口：

```java
public interface ActionListener {
    void actionPerformed(ActionEvent event);
}
```

为了指定操作，实现：

```java
class ClickAction implements ActionListener {
    public void actionPerformed(ActionEvent event) {
        System.out.println("Thanks for clicking!");
    }
}
```

然后创建该类的实例并添加到按钮：

```java
var button = new JButton("Click me!");
button.addActionListener(new ClickAction());
```

### 注意

由于它是 JDK 的一部分，我在示例中使用 Swing。（你不需要了解更多关于 Swing 的细节。）每个界面，无论是 Swing、JavaFX 还是 Android，都需要按钮一段想要运行的代码。

当然，这种定义按钮的方法相当繁琐。在其他语言中，你只需要给按钮一个函数，而无需经过创建类和实例化的过程。下一节将展示如何在 Java 中实现。

### 3.4. Lambda 表达式

Lambda 表达式是一个可以传递的代码块，稍后执行。在前面的章节中，你已经看到了许多需要指定此类代码块的情况：

- 向`Arrays.sort`传递比较方法

- 在单独的线程中运行任务

- 当用户点击按钮时发生的操作

然而，Java 是一种面向对象的语言，其中（几乎）一切都是对象。Java 没有函数类型。相反，函数表示为对象，即特定接口的类实例。Lambda 表达式为创建此类实例提供了方便的语法。

### 3.4.1. Lambda 表达式的语法

再次考虑第 3.3.2 节中的排序示例。我们传递代码检查一个字符串是否短于另一个。我们计算

```java
first.length() - second.length()
```

`first`和`second`是什么？它们都是字符串。Java 是一种强类型语言，我们也必须指定这一点：

```java
(String first, String second) -> first.length() - second.length()
```

你刚刚看到了第一个 Lambda 表达式。这样的表达式仅仅是一个代码块，加上对传递给代码的变量的指定。

## 为什么用这个名字？

多年前，在计算机出现之前，逻辑学家埃隆佐·丘（Alonzo Church）想要对数学函数的有效可计算性进行形式化。（有趣的是，已知某些函数存在，但没有人知道如何计算它们的值。）他使用希腊字母`lambda` (λ) 来标记参数，类似于：

```java
λfirst.λsecond. first.length() - second.length()
```

### 注意

为什么使用字母`λ`？是因为丘把字母表都用光了吗？实际上，备受推誉的*数学原理*（参见[`http://plato.stanford.edu/entries/principia-mathematica`](http://plato.stanford.edu/entries/principia-mathematica)）使用了`^`符号来表示函数参数，这启发了丘使用大写的 lambda `Λ`，但最终他切换到了小写版本。从那时起，带有参数变量的表达式一直被称为 lambda 表达式（lambda expression）。

如果 lambda 表达式的主体执行的计算不适合单个表达式，请完全按照你编写方法的方式来编写它：封装在`{}`中，并带有显式的`return`语句。例如：

```java
(String first, String second) -> {
    int difference = first.length() < second.length();
    if (difference < 0) return -1;
    else if (difference > 0) return 1;
    else return 0;
}
```

如果 lambda 表达式没有参数，请提供空括号，就像无参数的方法一样：

```java
Runnable task = () -> { for (int i = 0; i < 1000; i++) doWork(); }
```

如果 lambda 表达式的参数类型可以推断，你可以省略它们。例如：



```java
Comparator<String> comp
    = (first, second) -> first.length() - second.length();

// 等同于 (String first, String second)
```

在这里，编译器可以推导出`first`和`second`必须是字符串，因为该 lambda 表达式被赋值给了一个字符串比较器。（我们下一节中详细讨论这一赋值。）

如果一个方法只有一个类型可推断的单一参数，你甚至可以省略括号：

```java
ActionListener listener = event ->
    System.out.println("Thanks for clicking!");

// 代替 (event) -> 或 (ActionEvent event) ->
```

你永远不需要指定 lambda 表达式的结果类型。然而，编译器会从主体中推断结果并检查它是否符合预期类型。例如，该表达式：

```java
(String first, String second) -> first.length() - second.length()
```

可以使用在预期结果为`int`（或兼容类型如`Integer`、`long`或`double`）的上下文。

### 3.4.2. 函数式接口

正如你所看到的，Java 中有很多表示动作的接口，例如`Runnable`或`Comparator`。lambda 表达式与这些接口兼容。

每当需要具有**单个抽象方法**的接口对象时，你都可以提供一个 lambda 表达式。这种接口被称为函数式接口（functional interface）。

为了演示转换为函数式接口，考虑`Arrays.sort`方法。它的第二个参数需要`Comparator`实例，这是一个只有一个方法的接口。只需提供一个 lambda 即可：

```java
Arrays.sort(names,
    (first, second) -> first.length() - second.length());
```

在底层，`Arrays.sort`方法的第二个参数变量接收了一个实现了`Comparator<String>`的某个类的对象。在该对象上调用`compare`方法会执行 lambda 表达式的主体。这些对象和类的管理完全取决于实现，并经过了高度优化。

在大多数支持函数字面量的编程语言中，你可以声明类型如`(String, String) -> int`的函数类型，声明这些类型的变量，将函数放入这些变量中并调用它们。在 Java 中，你对 lambda 表达式**只有可以做一件事**：将其放入类型为函数式接口的变量中，这样它就会转换为该接口的实例。

### 注意

你不能将 lambda 表达式赋值给`Object`类型的变量，`Object`是 Java 中所有类的公共父类（参见第 4 章）。`Object`是类，而不是函数式接口。

Java API 提供了大量的函数式接口（参见第 3.6.2 节）。其中之一是：

```java
public interface Predicate<T> {
    boolean test(T t);

    // 额外的默认和静态方法
}
```

`ArrayList`类有一个`removeIf`方法，其参数是`Predicate`。它专门设计为接收 lambda 表达式而设计。例如，以下语句从数组列表中删除所有`null`值：

```java
list.removeIf(e -> e == null);
```

## 3.5. 方法引用和构造函数引用

有时，已经有一个方法可以执行你想传递给其他代码的完全动作。**方法引用**（method reference）有一种特殊的语法，比调用该方法的 lambda 表达式更短。构造函数也有类似的快捷方式。你将在接下来的章节中看到这两者。

### 3.5.1. 方法引用

假设你想不分大小写对字符串进行排序。你可以调用：

```java
Arrays.sort(strings, (x, y) -> x.compareToIgnoreCase(y));
```

而是你可以传递这个方法表达式：

```java
Arrays.sort(strings, String::compareToIgnoreCase);
```

表达式`String::compareToIgnoreCase`是等价于 lambda 表达式`(x, y) -> x.compareToIgnoreCase(y)`。

这是另一个例子。`Objects`类定义了方法`isNull`。调用`Objects.isNull(x)`只是返回`x == null`的值。这种情况似乎没必要专门方法，但它是被设计作为方法表达式传递的。调用：

```java
list.removeIf(Objects::isNull);
```

从列表中删除所有 null 值。

另一个例子，假设你想打印列表的所有元素。`ArrayList`类有一个`forEach`方法，它将函数应用到每个元素。你可以调用：

```java
list.forEach(x -> System.out.println(x));
```

然而，如果可以直接将`println`方法传递给`forEach`方法会更好。这样做如下：

```java
list.forEach(System.out::println);
```

从这些示例可以看出，`::`运算符将方法名与类或对象分开。有三种变体：

1. *类*::*实例方法*
2. *类*::*静态方法*
3. *对象*::*实例方法*

在第一种情况下，第一个参数将成为方法的接收者，任何其他参数都传递给该方法。例如，`String::compareToIgnoreCase`等同于`(x, y) -> x.compareToIgnoreCase(y)`。

在第二种情况下，所有参数都传递给静态方法。方法表达式`Objects::isNull`等同于`x -> Objects.isNull(x)`。

在第三种情况下，方法在给定对象上调用，参数被传递给实例方法。因此，`System.out::println`等同于`x -> System.out.println(x)`。

### 注意

当存在多个同名的重载方法时，编译器会尝试根据上下文确定你指的是哪一个。例如，`println`方法有多个版本。当传递给`ArrayList<String>`的`forEach`方法时，选择了`println(String)`方法。

你可以在方法引用中捕获`this`参数。例如，`this::equals`等同于`x -> this.equals(x)`。

### 注意

在内部类中，你可以捕获外部类的`this`引用，格式为*包围类*.this::`*方法*`。你也可以捕获`super`——参见第 4 章。

构造方法引用与方法引用相似，区别在于方法名是`new`。例如，`Employee::new`是对`Employee`构造函数的引用。如果一个类有多个构造函数，则取决于上下文选择哪一个构造函数。

这里有一个使用此类构造引用的示例。假设你有一个字符串列表：

```java
List<String> names = ...;
```

你想得到一个员工列表，每个名称对应一个员工。正如在第 8 章中所示，你可以使用流（streams）来完成这一点，而无需循环：将列表转换为流，然后调用`map`方法。它会应用函数并收集所有结果。

```java
Stream<Employee> stream = names.stream().map(Employee::new);
```

由于`names.stream()`包含`String`对象，编译器知道`Employee::new`指向构造函数`Employee(String)`。

你可以使用数组类型创建构造方法引用。例如，`int[]::new`是一个有一个参数的构造方法引用：即数组的长度。它等同于 lambda 表达式`n -> new int[n]`。

数组构造方法引用对于克服 Java 的一个局限性非常有用：无法构造泛型数组。（详情参见第 6 章）。因此，像`Stream.toArray`这样的方法返回`Object`数组，而不是元素类型的数组：

```java
Object[] employees = stream.toArray();
```

但这并不尽人意。用户想要的是员工数组，而不是对象数组。为了解决这个问题，`toArray`的另一个版本接受构造方法引用：

```java
Employee[] staff = stream.toArray(Employee[]::new);
```

`toArray`方法调用此构造函数来获取正确类型的数组。然后它填充并返回该数组。

### 3.6. 处理 Lambda 表达式

到目前，你已经学习了如何产生 lambda 表达式并将其传递给期望函数式接口的方法。在接下来的章节中，你将看到如何编写可以消费 lambda 表达式自定义方法。

#### 3.6.1. 实现延迟执行

使用 lambda 的意义在于**延迟执行**。毕竟，如果你现在就执行某些代码，你会直接执行，而不会将其封装在 lambda 内部。延迟执行代码有很多原因，例如：

- ![Images](img/sq.jpg) 在单独线程中运行代码
- ![Images](img/sq.jpg) 多次运行代码
- ![Images](img/sq.jpg) 在算法的正确点运行代码（例如，排序中的比较操作）
- ![Images](img/sq.jpg) 在某些事件发生时运行代码（按钮被点击、数据到达等）
- ![Images](img/sq.jpg) 仅在需要时运行代码

让我们来看一个简单的例子。假设你想重复执行一个操作`n`次。操作和计数被传递给`repeat`方法：

```java
repeat(10, () -> System.out.println("Hello, World!"));
```

为了接受该 lambda，我们需要选择（或在极少数情况下提供）一个函数式接口。在这种情况下，我们可以直接使用`Runnable`：

```java
public static void repeat(int n, Runnable action) {
    for (int i = 0; i < n; i++) action.run();
}
```

**注意**

这里是 Java API 的另一个示例。静态方法`Arrays.setAll`对数组的所有元素应用`IntFunction`，并用结果设置每个元素：

```java
var squares = new int[10];
Arrays.setAll(squares, index -> index * index) // 将 squares 设置为 { 0, 1, 4, ..., 81 }
```

注意，lambda 表达式体在调用`action.run()`时被执行。

现在让这个例子变得复杂一点。我们想告诉操作它发生在哪一次迭代。为此，我们需要选择一个具有带有`int`参数和`void`返回值的函数式接口。与其自己实现，我强烈建议你使用下一节描述的标准接口之一。处理`int`值的标准接口是：

```java
public interface IntConsumer {
    void accept(int value);
}
```

这里是改进后的`repeat`方法：

```java
public static void repeat(int n, IntConsumer action) {
    for (int i = 0; i < n; i++) action.accept(i);
}
```

以及是调用它的方式：

```java
repeat(10, i -> System.out.println("Countdown: " + (9 - i)));
```

#### 3.6.2. 选择函数式接口

在大多数函数式编程语言中，函数类型是**结构性的**。要指定将两个字符串映射到整数的函数，你使用类似于`Function2<String, String, Integer>`或`(String, String) -> int`的类型。在 Java 中，你通过函数式接口（如`Comparator<String>`）声明函数的意图。在编程语言理论中，这被称为**名义**类型。

当然，在许多情况下你想接受没有特定语义的“任何函数”。为了这个目的有很多泛型函数类型（参见表 3.1），使用其中之一是一个非常好的主意。

表 3.1 常见函数式接口

![Images](img/01.jpg)

例如，假设你写了一个匹配某些标准的方法。你应该使用`FileFilter`类还是`Predicate<File>`？我强烈建议你使用下一节描述的标准接口。**注意**

大多数函数式接口都有默认方法`and`、`or`、`negate`。例如，`Predicate.isEqual(a)`等同于：

```java
Predicate.isEqual(a).or(Predicate.isEqual(b))
```

```java
x -> a.equals(x)
```

表 3.2 原始类型的函数式接口 *p*, *q* 是`int`、`long`、`double`。*P*, *Q* 是`Int`、`Long`、`Double`

![Images](img/02.jpg)

#### 3.6.3. 实现自己的接口

你经常遇到没有任何标准函数式接口都适用的情况。这时你需要自己实现。

假设你想用颜色模式填充图像，其中用户提供一个产生每个像素颜色的函数。对于映射`(int, int) -> Color`，没有标准类型。你可以使用`BiFunction<Integer, Integer, Color>`，但这涉及自动装箱。

在这种情况下，定义一个新的接口是有意义的：

```java
@FunctionalInterface
public interface PixelFunction {
    Color apply(int x, int y);
}
```

**注意**

用`@FunctionalInterface`注解标记函数式接口是一个好习惯。这有两个优点：首先，编译器会检查被注解的实体是否带有单个抽象方法的接口。其次，javdoc 页面会包含一条说明你的接口是函数式接口的语句。

现在你准备好实现一个方法了：

```java
BufferedImage createImage(int width, int height, PixelFunction f) {
    var image = new BufferedImage(width, height, BufferedImage.TYPE_INT_RGB);
    for (int x = 0; x < width; x++)
        for (int y = 0; y < height; y++) {
            Color color = f.apply(x, y);
            image.setRGB(x, y, color.getRGB());
        }
    return image;
}
```

调用它时，提供一个两个整数产生颜色值的 lambda 表达式：

```java
BufferedImage frenchFlag = createImage(150, 100,
    (x, y) -> x < 50 ? Color.BLUE : x < 100 ? Color.WHITE : Color.RED);
```

在接下来的章节中，你将学习变量如何在 lambda 表达式内部工作。这些信息具有一定的技术性，但对于使用 lambda 表达式至关重要。

### 3.7.1 Lambda 表达式的作用域

lambda 表达式体具有`与嵌套块相同的作用域`。名称冲突和遮蔽的规则同样适用。在 lambda 中声明与局部变量同名的参数或局部变量是非法的。

```java
int first = 0;

Comparator<String> comp = (first, second) -> first.length() - second.length();

// Error: Variable first already defined
```

在方法内部，你不能有两个同名的局部变量，因此你也无法在 lambda 表达式中引入此类变量。

作为“相同作用域”规则的另一个结果，lambda 表达式中的`this`指向创建该 lambda 的方法的`this`参数。例如，考虑：

```java
public class Application() {
    public void doWork() {
        Runnable runner = () -> {
            ...;
            System.out.println(this.toString());
            ...;
        };

        ...
    }
}
```

表达式`this.toString()`调用了`Application`对象的`toString`方法，**而不是**`Runnable`实例。在 lambda 表达式中使用`this`并没有特殊之处。lambda 表达式的作用域嵌套在`doWork`方法内部，`this`在该方法的任何地方都具有相同的含义。

### 3.7.2 访问闭包作用域中的变量

通常，你想在 lambda 表达式中访问闭包方法或类的变量。考虑这个示例：

```java
public static void repeatMessage(String text, int count) {
    Runnable r = () -> {
        for (int i = 0; i < count; i++) {
            System.out.println(text);
        }
    };

    new Thread(r).start();
}
```



注意，lambda 表达式访问的是闭包作用域中定义的参数变量，而不是 lambda 表达式本身的。

考虑调用：

```java
repeatMessage("Hello", 1000); // 在单独线程中打印 Hello 1000 次
```

现在看 lambda 表达式内部的变量 `count` 和 `text`。如果你仔细考虑，这里发生着一些非显而易见的事情。lambda 表达式的代码可能在 `repeatMessage` 调用返回且参数变量消失很久后仍在运行。当 lambda 表达式准备执行时，`text` 和 `count` 变量是如何保留的？

为了理解发生了什么，我们需要完善对 lambda 表达式的理解。lambda 表达式包含三个要素：

1. 一个代码块
2. 参数
3. *自由*变量的值——即既不是参数又未在代码内部定义的变量

在我们的示例中，lambda 表达式有两个自由变量，`text` 和 `count`。表示该 lambda 表达式的数据结构必须存储这些变量的值——在我们的案例中，为 `"Hello"` 和 `1000`。我们说这些值被 lambda 表达式*捕获*（captured）了。（具体如何实现是实现细节。例如，可以将 lambda 表达式转换为一个只有一个方法的对象，这样自由变量的值就会复制到该对象的实例变量中。）

**注意**

代码块连同自由变量的值的专业术语是*闭包*（closure）。在 Java 中，lambda 表达式就是闭包。

正如你所看到的，lambda 表达式可以捕获闭包作用域中变量的值。为了确保被捕获的值定义明确，有一项重要的限制。在 lambda 表达式中，你只能引用值不会改变的变量。这有时描述为 lambda 表达式捕获的是值而不是变量。例如，以下是编译时错误：

```java
for (int i = 0; i < n; i++) {
    new Thread(() -> System.out.println(i)).start();

    // Error—cannot capture i
}
```

lambda 表达式尝试捕获 `i`，但这是非法的，因为 `i` 会改变。它没有单一的值可以捕获。规则是，lambda 表达式只能访问闭包作用域中*有效最终的*（effectively final）局部变量。有效最终变量从不被修改——它要么已经是最终的，要么可以被声明为 `final`。

**注意**

同样的规则也适用于局部类捕获的变量（参见第 3.9 节）。过去，规则更加严格，要求被捕获的变量必须实际声明为 `final`。现在不再如此了。

**注意**

增强 `for` 循环的变量是有效最终的，因为它的作用域是单次迭代。以下是完全合法的：

```java
for (String arg : args) {
    new Thread(() -> System.out.println(arg)).start();

    // OK to capture arg
}
```

每次迭代都会创建一个新变量 `arg`，并分配来自 `args` 数组的下一个值。相比之下，上一个示例中变量 `i` 的作用域是整个循环。

由于“有效最终”规则，lambda 表达式不能修改任何被捕获的变量。例如：

```java
public static void repeatMessage(String text, int count, int threads) {
    Runnable r = () -> {
        while (count > 0) {
            count--; // Error: Can’t mutate captured variable
            System.out.println(text);
        }
    };

    for (int i = 0; i < threads; i++) {
        new Thread(r).start();
    }
}
```

这实际上是一件好事。正如你在第 10 章中看到的，如果两个线程同时更新 `count`，它的值是未定义的。

**注意**

不要依赖编译器来捕获所有的并发错误。对修改的禁止仅适用于局部变量。如果 `count` 是实例变量或静态变量，那么即使结果只是未定义的，也不会报告错误。

**警告**

可以使用长度为 1 的数组来绕过对不当修改的检查：

```java
int[] counter = new int[1];

button.addActionListener(event -> counter[0]++);
```

变量 `counter` 是有效最终的——它始终引用同一个数组，所以你可以在 lambda 中访问它。

当然，这样的代码不是线程安全的。除了单线程 UI 中的回调外，这是一个极糟糕的主意。你将在第 10 章中看到如何实现线程安全的共享计数器。

### 3.8 高阶函数

在函数式编程语言中，函数是一等公民。就像你可以将数字传递给方法并让方法产生数字一样，你可以拥有函数的参数和返回值。处理或返回函数的被称为*高阶函数*。这听起来很抽象，但在实践中非常有用。Java 不完全是函数式语言，因为它使用函数式接口，但原理相同。在接下来的章节中，我们将查看一些示例并检查 `Comparator` 接口中的高阶函数。

#### 3.8.1 返回函数的方法

假设我们有时想按升序对字符串数组，有时想按降序。我们可以编写一个产生正确比较器的方法：

```java
public static Comparator<String> compareInDirection(int direction) {
    return (x, y) -> direction * x.compareTo(y);
}
```

调用 `compareInDirection(1)` 产生一个升序比较器，而调用 `compareInDirection(-1)` 产生一个降序比较器。

结果可以传递给另一个期望此类接口的方法（如 `Arrays.sort`）：

```java
Arrays.sort(names, compareInDirection(-1));
```

通常，不要害羞编写产生函数的方法（从技术上说，实现函数式接口类的实例）。这对于生成传递给带有函数式接口方法的自定义函数很有用。

#### 3.8.2 修改函数的方法

在上一节中，你看到了一种可以产生递增或递减字符串比较器的方法。我们可以通过反转任何比较器来泛化这个思想：

```java
public static Comparator<String> reverse(Comparator<String> comp) {
    return (x, y) -> comp.compare(y, x);
}
```

该方法作用于函数。它接收一个函数并返回一个修改后的函数。要获取不区分大小写的降序排列，请使用：

```java
reverse(String::compareToIgnoreCase)
```

#### Note

`Comparator` 接口有一个默认方法 `reversed`，它正通过这种方式产生给定比较器的反转结果。

### 3.8.3 `Comparator` 方法

`Comparator` 接口有很多实用的静态方法，这些方法是生成比较器的高阶函数。

`comparing` 方法接收一个“键值提取器”函数，该函数将类型 `T` 映射到可比较的类型（例如 `String`）。该函数被应用于待比较的对象，然后根据返回的键值进行比较。例如，假设一个 `Person` 类有一个方法 `getLastName`。那么你可以这样按姓氏对 `Person` 对象数组进行排序：

```java
Arrays.sort(people, Comparator.comparing(Person::getLastName));
```

你可以使用 `thenComparing` 方法链用比较器来打破平局。例如，按姓氏对人员数组进行排序，对于姓氏相同的人，使用名字：

```java
Arrays.sort(people, Comparator
    .comparing(Person::getLastName)
    .thenComparing(Person::getFirstName));
```

这些方法有几种变体。你可以指定一个比较器，用于由 `comparing` 和 `thenComparing` 方法提取的键值。例如，这里我们按名字长度对人员进行排序：

```java
Arrays.sort(people, Comparator.comparing(Person::getLastName,
    (s, t) -> s.length() - t.length()));
```

此外，`comparing` 和 `thenComparing` 方法都有变体，可以避免 `int`、`long` 或 `double` 值的装箱（boxing）。按名字长度排序的更简单的方法是：

```java
Arrays.sort(people, Comparator.comparingInt(p -> p.getLastName().length()));
```

如果你的键函数可以返回 `null`，那么你会喜欢 `nullsFirst` 和 `nullsLast` 适配器。这些静态方法接收一个现有的比较器并修改它，使其在遇到 `null` 值时不抛出异常，而是将其排得比普通值小或大。例如，假设当人没有中间名时 `getMiddleName` 返回 `null`。你可以使用 `Comparator.comparing(Person::getMiddleName, Comparator.nullsFirst(...))`。

`nullsFirst` 方法需要一个比较器——在这种情况下，是一个比较两个字符串的比较器。`naturalOrder` 方法为任何实现 `Comparable` 的类创建一个比较器。这里是按可能为空的中间名进行排序的完整调用。我使用了 `java.util.Comparator.*` 的静态导入来使表达式更具读性。注意 `naturalOrder` 的类型是推断出来的。

```java
Arrays.sort(people, comparing(Person::getMiddleName,
    nullsFirst(naturalOrder())));
```

静态方法 `reverseOrder` 提供自然顺序的反转。

### 3.9 局部类和匿名类

在 lambda 表达式出现很久以前，Java 就拥有一种机制可以简洁地定义实现接口（无论是否是函数式的）的类。对于函数式接口，你应该使用 lambda 表达式，但偶尔你可能希望非函数式接口也有一种简洁的形式。你还会在遗留代码遇到经典的构造。

#### 3.9.1 局部类

你可以在方法内部定义一个类。这种类被称为 `局部类`（local class）。你会在仅具策略性的类这样做。这经常发生在类实现了一个接口，而方法的调用者只关心接口而不关心类时。

例如，考虑一个方法：

```java
public static IntSequence randomInts(int low, int high)
```

它生成一个给定范围内无限随机整数序列。

由于 `IntSequence` 是一个接口，该方法必须返回实现该接口的某个类的对象。调用者不在乎该类，因此可以在方法内部声明它：

```java
private static RandomGenerator generator = RandomGenerator.getDefault();

public static IntSequence randomInts(int low, int high) {
    class RandomSequence implements IntSequence {
        public int next() {
            return low + generator.nextInt(high - low + 1);
        }

        public boolean hasNext() {
            return true;
        }
    }

    return new RandomSequence();
}
```

#### Note

局部类不声明为 `public` 或 `private`，因为它在方法外部是无法访问的。

将类变为局部类有两个优点。首先，它的名称在方法的作用范围内是隐藏的。其次，类的方法可以访问封闭作用域的变量，就像 lambda 表达式的变量一样。

在示例中，`next` 方法捕获了三个变量：`low`、`high` 和 `generator`。如果你将 `RandomInt` 变成嵌套类，你必须提供一个显式的构造函数来接收这些值并将它们存储在实例变量中（参见练习 16）。

#### 3.9.2 匿名类

在上一节的示例中，`RandomSequence` 名字只使用了一次：用于构造返回值。在这种情况下，你可以让类变成`匿名`的：

```java
public static IntSequence randomInts(int low, int high) {
    return new IntSequence() {
        public int next() {
            return low + generator.nextInt(high - low + 1);
        }

        public boolean hasNext() {
            return true;
        }
    };
}
```

表达式 `new Interface() { methods }` 意味着：定义一个实现接口的类，并构造一个。

#### Note

一样，`new` 表达式中的 `()` 表示构造参数。调用的是匿名类的默认构造函数。

在 Java 有 lambda 表达式之前，匿名内部类是提供 runnable、比较器和其他函数对象的简洁语法。你经常会在遗留代码中看到它们。如今，只有当你需要提供多个方法时（如示例），匿名内部类才是必要的。如果 `IntSequence` 接口有一个默认的 `hasNext` 方法（如 3.2.2 所示），你可以简单使用 lambda 表达式：

```java
public static IntSequence randomInts(int low, int high) {
    return () -> low + generator.nextInt(high - low + 1);
}
```

### Exercises

1. 提供一个接口 `Measurable`，包含一个方法 `getMeasure()` 用于测量对象。让 `Employee` 实现 `Measurable`。提供一个方法 `double average(Measurable[] objects)` 计算平均测量值。使用它计算员工数组的平均薪水。

2. 继续上一个练习，并提供一个方法 `Measurable largest(Measurable[] objects)`。使用它找到薪水最高的员工的名字。为什么你需要强制转换？

3. `String` 的所有父类型有哪些？`Scanner` 的呢？`ImageOutputStream` 的呢？注意每个类型都是自身的父类型。没有声明父类型的类或接口其父类型为 `Object`。

4. 为 `IntSequence` 类实现一个静态方法 `of`，产生带有参数的序列。例如，`IntSequence.of(3, 1, 4, 1, 5, 9)` 产生包含六个值的序列。如果返回匿名内部类的实例，加分。

5. 为 `IntSequence` 类添加一个名为 `constant` 的静态方法，产生一个无限常量序列。例如，`IntSequence.constant(1)` 产生值 `1 1 1`...，无休止。如果用 lambda 表达式实现，加分。

6. `SquareSequence` 类由于整数溢出，实际上无法提供无限的平方序列。具体来说，它的表现如何？请通过定义一个 `Sequence<T>` 接口和一个实现 `Sequence<BigInteger>` 的 `SquareSequence` 类来修复这个问题。

7. 在此练习中，你将尝试向接口中添加方法时会发生什么。在 Java 7 中（你可以从 Java 归档 `https://www.oracle.com/java/technologies/downloads/archive/` 获取），实现实现 `Iterator<Integer>` 而不是 `IntSequence` 的类 `DigitSequence`。提供 `hasNext`、`next` 方法和一个什么都不做的 `remove` 方法。编写一个打印实例元素的程序。在 Java 8 中，`Iterator` 类增加了另一个方法 `forEachRemaining`。当你切换到 Java 8 时，你的代码还能编译吗？如果你将 Java 7 的类放入 JAR 文件且不重新编译，它在 Java 8 中可以工作吗？如果你调用 `forEachRemaining` 方法会怎样？另外，`remove` 方法在 Java 8 中变成了一个默认方法，并抛出 `UnsupportedOperationException`。当在你的类实例上调用 `remove` 时会发生什么？

8. 实现方法 `void luckySort(ArrayList<String> strings, Comparator<String> comp)`，该方法不断对列表调用 `Collections.shuffle`，直到元素按照比较器确定的升序排列为止。

9. 实现实现 `Runnable` 的类 `Greeter`，其 `run` 方法打印 `n` 份 `"Hello, " + target`，其中 `n` 和 `target` 在构造函数中设置。构造两个不同消息的实例并在两个线程中并发执行它们。

10. 实现方法：

```java
public static void runTogether(Runnable... tasks)

public static void runInOrder(Runnable... tasks)
```



第一个方法应该在独立的线程中运行每个任务，然后返回。第二个方法应该在当前线程中运行所有方法，并在最后一个方法完成后返回。

11. 使用 `java.io.File` 类的 `listFiles(FileFilter)` 和 `isDirectory` 方法，写一个返回给定目录下的所有子目录的方法。使用 lambda 表达式而不是 `FileFilter` 对象。分别使用方法表达式和匿名内部类重复一遍。

12. 使用 `java.io.File` 类的 `list(FilenameFilter)` 方法，写一个返回给定目录下具有特定扩展名的文件的方法。使用 lambda 表达式而不是 `FilenameFilter`。它捕获了封装作用域中的哪个变量？

13. 给定一个 `File` 对象数组，对其进行排序，使得目录在文件之前，在每个组内，元素按路径名称排序。使用 lambda 表达式指定 `Comparator`。

14. 写一个方法，接收一个 `Runnable` 实例数组并返回一个 `Runnable`，其 `run` 方法按顺序执行这些实例。返回一个 lambda 表达式。

15. 写一个 `Arrays.sort` 的调用，按薪水对员工进行排序，相同的按名称。使用 `Comparator.thenComparing`。然后以反序执行此操作。

16. 在 3.9.1 节中将 `RandomSequence` 实现为一个嵌套类，位于 `randomInts` 方法之外。

## 4. 继承与反射

前面的章节向你介绍了类和接口。在本章中，你将学习面向对象编程的另一个基本概念：继承。继承是基于现有类创建新类的过程。当你继承一个现有类时，你重用了（或继承了）它的方法，并可以添加新的方法和字段。

### 注意

实例变量和静态变量统称为 `fields`（字段）。类内部的字段、方法和嵌套类/接口统称为它的 `members`（成员）。

本章还涵盖反射，即在运行程序中发现更多关于类及其成员信息的能力。反射是一个强大的特性，但不可否认地复杂。由于反射对工具构建者比对应用程序程序员更有趣，你第一次阅读时可以略过该章的这部分，以后再回来。

本章的要点是：

1. 子类可以继承或重写父类的方法，只要它们不是 `private` 的。
2. 使用 `super` 关键字调用父类方法或构造函数。
3. `final` 方法不能被重写；`final` 类不能被扩展。
4. `abstract` 方法没有实现；`abstract` 类不能实例化。
5. 父类的 `protected` 成员在子类方法中是可访问的，但仅当应用于相同子类的对象时有效。它在所在的包中也是可访问的。
6. 每个类都是 `Object` 的子类，它提供了 `toString`、`equals`、`hashCode` 和 `clone` 方法。
7. `sealed`（密封）类型指定了可以在其他源文件中定义的子类型。
8. 每个枚举类型都是 `Enum` 的子类，它提供了实例方法 `toString` 和 `compareTo` 以及静态方法 `valueOf`。
9. `Class` 类提供了关于 Java 类型的信息，该类型可以是类、数组、接口、基本类型或 `void`。
10. 你可以使用 `Class` 对象加载放置在类文件旁边的资源。
11. 你可以使用类加载器从类路径以外的位置加载类。
12. `ServiceLoader` 类提供了一种定位和选择服务实现的机制。
13. 反射库允许程序发现成员、访问变量和调用方法。
14. 代理对象动态地实现接口，将所有方法调用路由到处理器中。

### 4.1 扩展类

让我们回到第 2 章中讨论过的 `Employee` 类。假设（唉）你在一家经理对经理对待方式不同的公司工作。当然，经理在许多方面和员工一样。员工和经理都领取薪水。然而，员工被期望完成任务以换取薪水，而经理如果他们实际上应该实现的目标，就能获得奖金。这种情况可以用继承来建模。

### 4.1.1 父类与子类

让我们定义一个新类 `Manager`，保留 `Employee` 类的一些功能，但指定经理的特殊之处。

```
public class Manager extends Employee {

    新增的字段

    新增或重写的方法

}
```

`extends` 关键字表示你正在创建一个派生自现有类的新类。现有类被称为 `superclass`（父类），新类被称为 `subclass`（子类）。在我们的示例中，`Employee` 类是父类，`Manager` 类是子类。注意，父类并不“优于”它的子类。相反：子类的功能比父类更多。父/子术语源于集合论。经理集是员工集的子集。

### 4.1.2 定义和继承子类方法

我们的 `Manager` 类有一个新的实例变量来存储奖金，并有一个新方法来设置它：

```
public class Manager extends Employee {

    private double bonus;

    ...

    public void setBonus(double bonus) {

        this.bonus = bonus;

    }

}
```

当你拥有一个 `Manager` 对象时，你当然可以应用 `setBonus` 方法，以及 `Employee` 类的非私有方法。这些方法是*继承*的。

```
Manager boss = new Manager(...);

boss.setBonus(10000); // 在子类中定义

boss.raiseSalary(5); // 继承自父类
```

### 4.1.3 方法重写

有时，需要在子类中修改父类方法。例如，假设 `getSalary` 方法预期用于报告员工的总薪资。那么，所继承的方法对于 `Manager` 类来说是不够的。相反，你需要 `override`（重写）该方法，以便其返回基本工资和奖金之和。

```
public class Manager extends Employee {

    ...

    public double getSalary() { // 重写父类方法

        return super.getSalary() + bonus;

    }
}
```

该方法调用了父类方法，该方法获取基本工资并加上奖金。注意，子类方法无法直接访问父类的私有实例变量。这就是为什么 `Manager.getSalary` 方法调用了公有的 `Employee.getSalary` 方法。`super` 关键字用于调用父类方法。

### 注意事项

与 `this` 不同，`super` 不是对象的引用，而是一个用于跳过动态方法查找（参见第 4.1.5 节）并调用特定方法的指令。

在重写方法时并不要求调用父类方法，但这样做很常见。

当你重写一个方法时，必须小心确保参数类型完全匹配。例如，假设 `Employee` 类有一个方法：

```
public boolean worksFor(Employee supervisor)
```

如果你在 `Manager` 类中重写此方法，你不能更改参数类型，尽管显然没有经理会向一个普通的员工汇报。假设你定义了这样一个方法：

```
public class Manager extends Employee {

    ...

    public boolean worksFor(Manager supervisor) {

        ...

    }
}
```

这仅仅是一个新方法，现在 `Manager` 拥有了两个独立的 `worksFor` 方法。你可以通过对意图重写父类方法的方法标记 `@Override` 注解，来防止此类错误的发生：

```java
@Override public boolean worksFor(Employee supervisor)
```

如果你犯了错误并正在定义一个新方法，编译器会报告错误。

在重写方法时，你可以将返回类型更改为子类型。（在术语中，允许使用`协变返回类型`/covariant return types。）例如，如果 `Employee` 类有一个方法：

```
public Employee getSupervisor()
```

那么 `Manager` 类可以使用以下方法重写它：

```
@Override public Manager getSupervisor()
```

### 警告

当重写方法时，子类方法的访问权限必须**至少与父类方法相同**（at least as accessible）。特别是，如果父类方法是 public 的，那么子类方法也必须声明为 `public`。一个常见的错误是不小心漏掉了子类方法的 `public` 修饰符。此时，编译器会对访问权限过弱报错。

#### 4.1.4 子类的构造

让我们为 `Manager` 类提供一个构造函数。由于 `Manager` 构造函数无法访问 `Employee` 类的私有实例变量，它必须通过父类构造函数来初始化它们。

```
public Manager(String name, double salary) {

    super(name, salary);

    bonus = 0;

}
```

在这里，`super` 关键字表示调用父类 `Employee` 的构造函数并将 `name` 和 `salary` 作为参数。父类构造函数的调用必须是子类构造函数的**第一条语句**（first statement）。

如果子类没有显式调用任何父类构造函数，则父类必须有一个会被隐式调用的无参构造函数。

#### 4.1.5 父类赋值

将子类的对象赋值给类型为父类的变量是合法的，例如：

```
Manager boss = new Manager(...);

Employee empl = boss; // 赋值给父类变量是允许的
```

现在考虑当在父类变量上调用方法时会发生什么。

```
double salary = empl.getSalary();
```

尽管 `empl` 的类型是 `Employee`，但调用的是 `Manager.getSalary` 方法。在调用方法时，虚拟机会查看对象的实际类并定位其方法版本。这个过程被称为`动态方法查找`（dynamic method lookup）。

你为什么要将一个 `Manager` 对象赋值给 `Employee` 变量呢？它允许你编写适用于**所有**（all）员工的代码，无论是经理、清洁工还是另一个 `Employee` 子类的实例。

```
Employee[] staff = new Employee[...];

staff[0] = new Employee(...);

staff[1] = new Manager(...); // 赋值给父类变量是允许的

staff[2] = new Janitor(...);

...

double sum = 0;

for (Employee empl : staff)
    sum += empl.getSalary();
```

多亏于动态方法查找，调用 `empl.getSalary()` 调用的是 `empl` 所引用对象的 `getSalary` 方法，这可能是 `Employee.getSalary`、`Manager.getSalary` 等。

### 警告

在 Java 中，父类赋值也适用于数组：你可以将 `Manager[]` 数组赋值给 `Employee[]` 变量。（技术术语是 Java 数组是**协变的**/covariant。）这很方便，但也是**不安全的**（unsound）——即类型错误的可能原因。考虑这个例子：

```
Manager[] bosses = new Manager[10];

Employee[] empls = bosses; // 在 Java 中合法

empls[0] = new Employee(...); // 运行时错误
```

编译器接受最后一条语句，因为在 `Employee[]` 数组中存储 `Employee` 通常是合法的。然而，这里 `empls` 和 `bosses` 指向同一个 `Manager[]` 数组，它无法持有 `Employee`。这个错误只有在运行时被发现，虚拟机会抛出 `ArrayStoreException`。

#### 4.1.6 强制转换

在上一节中，你看到类型为 `Employee` 的变量可以引用 `Employee`、`Manager` 或另一个 `Employee` 子类的对象。这对于处理多个类的对象很有用。但只有一个缺点：你只能调用属于父类的方法。例如：

```
Employee empl = new Manager(...);

empl.setBonus(10000); // 编译错误
```

尽管这个调用在运行时可以成功，但它是编译错误。编译器检查你只调用接收者类型存在的方法。在这里，`empl` 类型为 `Employee`，该类没有 `setBonus` 方法。

与接口一样，你可以使用 `instanceof` 运算符和强制转换将父类转换为子类。

```
if (empl instanceof Manager mgr) {
    mgr.setBonus(10000);
}
```

#### 4.1.7 匿名子类

正如你可以创建一个接口的匿名类，你可以创建一个扩展父类的匿名类。这对于调试非常有用：

```
var names = new ArrayList<String>(100) {

    public void add(int index, String element) {
        super.add(index, element);
        System.out.printf("Adding %s at %d\n", element, index);
    }

};
```

父类名称后括号中的参数被传递给父类构造函数。在这里，我们构造了一个 `ArrayList<String>` 的匿名子类，它重写了 `add` 方法。实例构造时的初始容量为 100。

一种被称为`双括号初始化`（double brace initialization）的技巧以一种非常奇怪的方式使用了内部类语法。假设你想构造一个数组列表并将其传递给方法：

```
var friends = new ArrayList<String>();

friends.add("Harry");

friends.add("Sally");

invite(friends);
```

如果你再也不需要这个数组列表，那么把它变成匿名类会很好。但那么，如何添加元素呢？方法如下：

```
invite(new ArrayList<String>() {{ add("Harry"); add("Sally"); }});
```

注意双大括号。外层大括号创建了一个 `ArrayList<String>` 的匿名子类。内部大括号是一个初始化块（参见第 2 章）。

我不建议你在 Java 趣味知识竞赛之外使用这种技巧。它是低效的。取决于 `equals` 方法的实现方式，所构建的对象在相等性测试中的行为可能不一致。

如果 `invite` 方法参数的类型为 `List`，只需按照如下方式调用：

```
invite(List.of("Harry", "Sally"));
```

### 4.1.8 使用 `super` 的方法表达式

回想第 3 章，方法表达式可以以 `object::instanceMethod` 的形式存在。使用 `super` 代替对象引用也是有效的。方法表达式

```
super::instanceMethod
```

使用 `this` 作为目标，并调用给定方法的父类版本。这里是一个展示其机制的人工示例：

```
public class Worker {

    public void work() {

         for (int i = 0; i < 100; i++) System.out.println("Working");

    }

}

public class ConcurrentWorker extends Worker {

    public void work() {

        var t = new Thread(super::work);

        t.start();

    }
}
```

该线程构建时使用了一个 `Runnable`，其 `run` 方法调用了父类的 `work` 方法。

### 4.2 继承层次结构

你刚刚看到了如何扩展一个类。显然，你可以再次扩展子类并重复该过程，形成类的类的层次结构。在接下来的章节中，你将学习 Java 语言提供的用于控制此类继承结构中可以操作内容的构造。

#### 4.2.1 final 方法和类

当你将一个方法声明为 `final` 时，没有任何子类可以重写它。

```
public class Employee {

    ...

    public final String getName() {

        return name;

    }
}
```

Java API 中 `final` 方法的一个很好的例子是 `Object` 类的 `getClass` 方法，你将在第 4.5.1 节中看到。允许对象对其所属的类撒谎并不明智，因此该方法永远无法更改。

一些程序员认为 `final` 关键字有助于效率。这在 Java 早期可能是真的，但现在不再是了。现代虚拟机会推测地“内联”简单方法（例如上面的 `getName` 方法），即使它们没有被声明为 `final`。在加载了重写了此类方法的子类的罕见情况下，内联会被取消。

一些程序员认为一个类的大多数方法都应该声明为 `final`，只有那些专门设计为可重写的方法才不如此。另一些人认为这种做法过于严苛，因为阻止了即使是无害的重写（例如为了日志记录或调试目的）。

偶尔你可能希望防止别人从你的某个类中创建子类。在类定义中使用 `final` 修饰符来指示这一点。例如，这里是防止他人对 `Executive` 类进行扩展的方法：



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```



2. 每个`equals`方法都要求在与`null`比较时返回`false`。

3. 由于`equals`方法重写了`Object.equals`，它的参数类型为`Object`，你需要将其转换为实际类型以便查看其实例变量。在此之前，请使用`getClass`方法或`instanceof`运算符进行类型检查。

4. 最后，比较实例变量。对于基本类型使用`==`。然而，对于`double`值，如果你担心±∞或NaN，请使用`Double.equals`。对于对象，使用`Objects.equals`，这是`equals`方法的空安全版本。调用`Objects.equals(x, y)`在`x`为`null`时返回`false`，而`x.equals(y)`则会抛出异常。

### 提示

如果你有数组类型的实例变量，请使用静态的`Arrays.equals`方法检查数组长度是否相等以及对应的数组元素是否相等。

当为子类定义`equals`方法时，首先调用父类中的`equals`。如果该测试没有通过，则这些对象不相等。如果父类的实例变量相等，那么你就可以准备比较子类的实例变量了。

```
public class DiscountedItem extends Item {

    private double discount;

    ...

    public boolean equals(Object otherObject) {

        if (!super.equals(otherObject)) return false;

        var other = (DiscountedItem) otherObject;

        return discount == other.discount;
    }

    public int hashCode() { ... }

}
```

注意，如果`otherObject`不是`DiscountedItem`，则父类中的`getClass`测试将失败。

当比较属于不同类的值时，`equals`方法应该如何表现？这一直是一个存在争议的领域。在以前的示例中，如果类不同，`equals`方法将返回`false`。许多程序员使用`instanceof`测试来代替：

```
if (!(otherObject instanceof Item)) return false;
```

然而，这留下了`otherObject`属于子类的可能性。`equals`方法的要求之一是对称的：如果`x`和`y`相等，那么`x.equals(y)`和`y.equals(x)`必须都返回`true`。如果`x`和`y`不相等，那么`x.hashCode()`和`y.hashCode()`可以不相等，但如果相等，则哈希值必须相同。对于`x`和`y`，如果`x.equals(y)`，那么`x.hashCode() == y.hashCode()`必须为真。

### 4.3.3 `hashCode`方法

哈希值是一个派自对象的整数。哈希值应该是散乱的——如果`x`和`y`不相等，`x.hashCode()`和`y.hashCode()`是不同的。例如，`"Mary".hashCode()`为239079，而`"Myra".hashCode()`为241381。

`String`类使用以下算法计算哈希值：

```
int hash = 0;
for (int i = 0; i < length(); i++)
    hash = 31 * hash + charAt(i);
```

`Object.hashCode`方法以依赖实现的方式派生哈希值。它可以来自内存位置、数字（顺序或伪随机）或两者的组合。由于`Object.equals`测试相同对象，唯一重要的是相同对象具有相同的哈希值。

如果你重写`equals`方法，你还需要重写`hashCode`方法以与`equals`兼容。如果不这样做，类的用户将对象插入哈希集合或哈希映射时，可能会丢失！

在你的`hashCode`方法中，简单地组合实例变量的哈希值。例如，这里是`Item`类的`hashCode`方法：

```
class Item {

    ...

    public int hashCode() {
        return Objects.hash(description, price);
    }

}
```

`Objects.hash`可变参数方法计算参数的哈希值并将它们组合。该方法是空安全的。

如果你的类具有数组实例变量，请先使用静态的`Arrays.hashCode`方法计算它们的哈希值，该方法计算由元素组成的哈希值。将结果传递给`Objects.hash`。

#### 4.3.4 克隆对象

你刚刚看到了`Object`类中常用的、经常重写的“三大”方法：`toString`、`equals`和`hashCode`。在本节中，你将学习如何重写`clone`方法。正如你将看到的，这非常复杂，而且也并不必要。除非你有充分的理由，否则不要重写`clone`。Java标准库中不足5%的类实现了`clone`。

`clone`方法的目的是创建一个对象的“克隆”——一个与原始具有相同状态的不同对象。如果你修改了其中一个对象，另一个将保持不变。

```
Employee cloneOfFred = fred.clone();

cloneOfFred.raiseSalary(10); // fred 保持不变
```

`clone`方法在`Object`类中被声明为`protected`，所以如果你想让你的类的用户能够克隆实例，就必须重写它。

`Object.clone`方法执行的是*浅拷贝*。它简单地将所有实例变量从原始对象拷贝到克隆对象。如果这些变量是基本类型或不可变对象，那是没问题的。但如果它们不是，原始对象和克隆对象将共享可变状态，这可能会引发问题。

考虑一个拥有收件者列表的邮件类。

```java
public final class Message {

    private String sender;

    private ArrayList<String> recipients;

    private String text;

    ...

    public void addRecipient(String recipient) { ... };

}
```

如果你对`Message`对象进行浅拷贝，原始对象和克隆对象将共享`recipients`列表（参见图4.2）：

```
Message specialOffer = ...;

Message cloneOfSpecialOffer = specialOffer.clone();
```

![Images](img/04fig02.jpg)

图4.2：对象的浅拷贝

如果其中一个对象更改了收件者列表，更改将反映在另一个对象上。因此，`Message`类需要重写`clone`方法以实现*深拷贝*。

克隆可能是不可能，或者不值得尝试。例如，克隆一个`Scanner`对象将非常有挑战性。

通常情况下，当你实现一个类时，你需要决定：

1. 你不想提供`clone`方法，或者

2. 继承来的`clone`方法是可以接受的，或者

3. `clone`方法应该执行深拷贝。

对于第一种选择，什么都不做即可。你的类将继承`clone`方法，但你的类的用户将无法调用它，因为它是`protected`的。

要选择第二种方案，你的类必须实现`Cloneable`接口。这是一个没有任何方法的接口，被称为*标记*接口（tagging or marker interface）。（记住`clone`方法定义在`Object`类中）。`Object.clone`方法在执行浅拷贝之前会检查是否实现了此接口，否则将抛出`CloneNotSupportedException`。

你可能还想将`clone`的作用范围从`protected`提升到`public`，并更改返回类型。

最后，你需要处理`CloneNotSupportedException`。这是一个*检查型*异常，正如你在第5章中看到的，你必须要么声明它要么捕获它。如果你的类是`final`的，你可以捕获它。否则，请声明该异常，因为子类可能再次想要抛出它。

```java
public class Employee implements Cloneable {

    ...

    public Employee clone() throws CloneNotSupportedException {
         return (Employee) super.clone();

    }

}
```

强制转换`(Employee)`是必要的，因为`Object.clone`的返回类型是`Object`。

实现`clone`方法的第三种选择（类需要执行深拷贝）是最复杂的情况。你完全不需要使用`Object.clone`方法。这里是`Message.clone`的简单实现：

```java
public Message clone() {

    var cloned = new Message(sender, text);

    cloned.recipients = new ArrayList<>(recipients);

    return cloned;

}
```

或者，你可以在父类和可变实例变量上调用`clone`。

`ArrayList`类实现了`clone`方法产生浅拷贝。这意味着原始列表和克隆列表共享元素引用。在我们的情况下，这是没问题的，因为元素是字符串。如果不是，我们必须克隆每个元素。

然而，由于历史原因，`ArrayList.clone`方法的返回类型是`Object`。你需要使用强制转换。

```
cloned.recipients = (ArrayList<String>) recipients.clone(); // 警告
```

不幸的是，正如你在第6章中看到的，该转换无法在编译时完全检查，你会得到一个警告。你可以使用注解来抑制警告，但该注解只能附加到声明（参见第12章）。这里是完整的方法实现：

```java
public Message clone() {

    try {
        var cloned = (Message) super.clone();

        @SuppressWarnings("unchecked") var clonedRecipients

            = (ArrayList<String>) recipients.clone();

        cloned.recipients = clonedRecipients;

        return cloned;

    } catch (CloneNotSupportedException ex) {
        return null; // 不可能

    }
}
```

在这种情况下，`CloneNotSupportedException`不可能，因为`Message`类是`final`的，且`ArrayList`不抛出该异常。

注意

如果`recipients`是一个数组而不是列表，你可以这样克隆它：

```
cloned.recipients = (ArrayList<String>) recipients.clone();
```

这里不需要强制转换。

### 4.4 枚举类

你在第1章中看到了如何定义枚举类型。这里有一个典型的示例，定义了四个实例：

```java
public enum Size { SMALL, MEDIUM, LARGE, EXTRA_LARGE };
```

在接下来的章节中，你将看到如何处理枚举。

#### 4.4.1 枚举类的方法

由于枚举类型的每个实例都是唯一的，你永远不需要使用`equals`。只需使用`==`来比较它们即可。（如果你喜欢，也可以调用`equals`，它会触发`==`测试。）

你也不需要提供`toString`方法。它会自动提供，以返回枚举对象的名称——在我们的示例中，为`"SMALL"`、`"MEDIUM"`等。

`toString`的反向是静态方法`valueOf`，它为每个枚举类型合成。例如，语句

```
Size notMySize = Size.valueOf("SMALL");
```

将`notMySize`设置为`Size.SMALL`。如果没有对应名称的实例，`valueOf`方法将抛出异常。

每个枚举类型都有一个静态`values`方法，按声明顺序返回枚举的所有实例。调用

```
Size[] allValues = Size.values();
```

返回包含`Size.SMALL`、`Size.MEDIUM`等元素的数组。

提示

使用增强型`for`循环遍历枚举类型的所有实例：

```java
for (Size s : Size.values()) { System.out.println(s); }
```

`ordinal`方法产生实例在`enum`声明中的位置，从零开始。例如，`Size.MEDIUM.ordinal()`返回`1`。当然，你需要小心使用这个方法。如果插入新的常量，值会发生偏移。

每个枚举类型`E`自动实现`Comparable<E>`，允许仅与其自己的对象进行比较。比较按序值进行。

注意

从技术上，枚举类型`E`扩展了`Enum<E>`类，并从中继承`compareTo`方法以及本节描述的其他方法。表4.2显示了`Enum`类的方法。

#### 4.4.2 构造函数、方法和字段

如果你喜欢，可以为枚举类型添加构造函数、方法和字段。这里有一个示例：

```java
public enum Size {

    SMALL("S"), MEDIUM("M"), LARGE("L"), EXTRA_LARGE("XL");

    private String abbreviation;

    Size(String abbreviation) {
        this.abbreviation = abbreviation;
    }

    public String getAbbreviation() { return abbreviation; }
}
```

枚举的每个实例都保证只被构造一次。

### 注意

枚举的构造函数始终是私有（private）的。你可以省略`private`修饰符，如前面的示例所示。将枚举构造函数声明为`public`或`protected`会导致语法错误。

### 4.4.3. 实例体

你可以为每个单独的`enum`实例添加方法，但这些方法必须重写在枚举中定义的方法。例如，为了实现一个计算器，你可以这样做：

```java
public enum Operation {

    ADD {
        public int eval(int arg1, int arg2) { return arg1 + arg2; }
    },

    SUBTRACT {
        public int eval(int arg1, int arg2) { return arg1 - arg2; }
    },

    MULTIPLY {
        public int eval(int arg1, int arg2) { return arg1 * arg2; }
    },

    DIVIDE {
        public int eval(int arg1, int arg2) { return arg1 / arg2; }
    };

    public abstract int eval(int arg1, int arg2);

}
```

在计算器程序的循环中，人们会根据用户输入将一个变量设置为这些值之一，然后调用`eval`：

```java
Operation op = ...;

int result = op.eval(first, second);
```

### 注意

从技术上讲，这些常量每一个都属于`Operation`的一个匿名子类。任何你可以放入匿名子类体中的内容，也可以添加到成员的体中。

### 4.4.4. 静态成员

枚举拥有静态成员是合法的。然而，你必须小心构造顺序。枚举常量是在静态成员*之前*构造的，因此你不能在枚举构造函数中引用任何静态成员。例如，以下代码是非法的：

```java
public enum Modifier {

    PUBLIC, PRIVATE, PROTECTED, STATIC, FINAL, ABSTRACT;

    private static int maskBit = 1;

    private int mask;

    Modifier() {
        mask = maskBit; // 错误—无法在构造函数访问静态变量

        maskBit *= 2;
    }

    ...

}
```

解决办法是在静态初始化器中进行初始化：



```java
public enum Modifier {

    PUBLIC, PRIVATE, PROTECTED, STATIC, FINAL, ABSTRACT;

    private int mask;

    static {
        int maskBit = 1;

        for (Modifier m : Modifier.values()) {
            m.mask = maskBit;

            maskBit *= 2;
        }

    }

    ...

}
```

一旦常量构造完成，静态变量初始化和静态初始化器将按照通常的、从上到下的方式运行。

### 注意

枚举类型可以嵌套在类内部。这种嵌套枚举是隐式的静态嵌套类——这意味着，它们的方法不能引用外部类的实例变量。

### 4.4.5. 对枚举进行 `switch`

你可以在 `switch` 表达式或语句中使用枚举常量。

```java
enum Operation { ADD, SUBTRACT, MULTIPLY, DIVIDE };

public static int eval(Operation op, int arg1, int arg2) {
    return switch (op) {
        case ADD -> arg1 + arg2;
        case SUBTRACT -> arg1 - arg2;
        case MULTIPLY -> arg1 * arg2;
        case DIVIDE -> arg1 / arg2;
    }
}
```

如果你为枚举的所有实例都提供了分支，就不需要 `default` 情况。

请注意，在 `switch` 语句内部，你可以使用 `ADD` 代替 `Operation.ADD`。枚举是从操作数的类型推断出来的。

### 提示

如果你想在 `switch` 外部通过简单名称引用枚举的实例，请使用静态导入声明。例如，使用以下声明：

```java
import static com.horstmann.corejava.Size.*;
```

你可以使用 `SMALL` 代替 `Size.SMALL`。

### 4.5. 运行时类型信息与资源

在 Java 中，你可以在运行时确定给定对象属于哪个类。这有时是有用的，例如，在 `equals` 和 `toString` 方法的实现中。此外，你可以发现该类是如何加载的，并加载与其相关的数据，称为资源。

#### 4.5.1. `Class` 类

假设你有一个 `Object` 类型的变量，其中填充了某些对象引用，你想了解更多关于该对象的信息，例如它属于哪个类。

`getClass` 方法产生一个名为 `Class` 的类的对象，这并不意外。

```java
Object obj = ...;

Class<?> cl = obj.getClass();
```

### 注意

请参阅第 6 章关于 `<?>` 后缀的解释。目前，只需忽略它即可。但不要省略它。如果你省略了，不仅你的 IDE 会给你出一个难看的警告，还会关闭涉及该变量的表达式中的用类型检查。

一旦你有了一个 `Class` 对象，就可以找到类名：

```java
System.out.println("This object is an instance of " + cl.getName());
```

或者，你可以使用静态方法 `Class.forName` 获取类名：

```java
String className = "java.lang.String";

Class<?> cl = Class.forName(className);
```

### 警告

`Class.forName` 方法以及许多其他用于反射的方法，在出现问题时会抛出受检异常（例如，当没有指定名称的类时）。目前，请参阅第 5 章了解如何处理异常。如果你提前知道想要哪个类，请使用类字面量代替：

```java
Class<?> cl = Scanner.class;
```

`.class` 后缀也可以用于获取其他类型的信息：

```java
Class<?> cl2 = String[].class; // 描述数组类型 String[]

Class<?> cl3 = Runnable.class; // 描述 Runnable 接口

Class<?> cl4 = int.class; // 描述 int 类型

Class<?> cl5 = void.class; // 描述 void 类型
```

数组是 Java 中的类，但接口、原始类型和 `void` 不是。`Class` 这个名字有点不好——`Type` 会更准确。

### 警告

`getName` 方法为数组类型返回奇怪的名字：

```java
String[].class.getName() // 返回 "[Ljava.lang.String;"
```

```java
int[].class.getName() // 返回 "[I"
```

这种表示法自虚拟机古代时代起一直存在。使用 `getCanonicalName` 代替可以获取如 `"java.lang.String[]"` 和 `"int[]"` 的名字。

虚拟机为每个类型管理唯一的 `Class` 对象。因此，你可以使用 `==` 运算符来比较类对象。例如：

```java
if (other.getClass() == Employee.class) ...
```

你已经在第 4.3.2 节见过这种类对象的用法。

在接下来的章节中，你将看到可以使用 `Class` 对象做什么。参见表 4.3 获取方法的总结。

#### 4.5.2. 加载资源

`Class` 类的一个有用服务是定位程序需要的资源，例如配置文件或图像。如果你将资源放在与类文件相同的目录下，可以这样打开该文件的输入流：

```java
InputStream stream = MyClass.class.getResourceAsStream("config.txt");

var in = new Scanner(stream);
```

一些遗留方法如 `Applet.getAudioClip` 和 `javax.swing.ImageIcon` 构造函数从 `URL` 对象读取数据。在这种情况下，你可以使用 `getResource` 方法，它会返回指向资源的 `URL`。

资源可以包含子目录，这些目录可以是相对路径或绝对路径。例如，`MyClass.class.getResourceAsStream("/config/menus.txt")` 在 `MyClass` 所属包根目录所在的目录下定位 `config/menus.txt`。

如果你将类打包成 JAR 文件，并将资源与类文件一起压缩，那么它们也会被正确定位。

#### 4.5.3. 类加载器（Class Loaders）

虚拟机指令存储在类文件中。每个类文件包含针对单个类或接口的指令。类文件可以位于文件系统、JAR 文件、远程位置，甚至可以在内存中动态构建。一个 `class loader`（类加载器）负责加载字节流并将它们转换为虚拟机中的类或接口。

虚拟机按需（on-demand）加载类文件，从要调用的包含 `main` 方法的类开始。该类将依赖于其他类，例如 `java.lang.System` 和 `java.util.Scanner`，这些类将与它们所依赖的类一起加载。

执行 Java 程序时，至少涉及三个类加载器。

`bootstrap class loader`（启动类加载器）加载最基础的 Java 库类。它是虚拟机的一部分。

`platform class loader`（平台类加载器）加载其他库类。与启动类加载器加载的类不同，平台类加载器的权限可以通过安全策略进行配置。

`system class loader`（系统类加载器）加载应用程序类。它在类路径（class path）和模块路径（module path）上的目录和 JAR 文件中定位类。

### 注意事项

在 Oracle JDK 的之前的版本中，平台和系统类加载器是 `URLClassLoader` 类的实例。现在已不再如此。某些程序员使用 `URLClassLoader` 的 `getURLs` 方法来查找类路径。请改用 `System.getProperty("java.class.path")`。

你可以通过创建自己的 `URLClassLoader` 实例，从尚未在类路径上的目录或 JAR 文件中加载类。这通常用于加载插件。

```java
URL[] urls = {
    new URL("file:///path/to/directory/"),
    new URL("file:///path/to/jarfile.jar")
};

String className = "com.mycompany.plugins.Entry";

try (var loader = new URLClassLoader(urls)) {
    Class<?> cl = Class.forName(className, true, loader);
    // 现在构造 cl 的实例——参见第 4.6.4 节
    ...
}
```

### 注意事项

在调用 `Class.forName(className, true, loader)` 时，第二个参数确保类的静态初始化在加载后发生。你绝对希望这种情况发生。

不要使用 `ClassLoader.loadClass` 方法。它不会运行静态初始化器。

#### 注释

`URLClassLoader` 从文件系统加载类。如果你想从其他地方加载类，则需要编写自己的类加载器。你只需要实现的方法是 `findClass`，如下所示：

```java
public class MyClassLoader extends ClassLoader {

    ...

    @Override public Class<?> findClass(String name)
              throws ClassNotFoundException {
        byte[] bytes = the bytes of the class file
        return defineClass(name, bytes, 0, bytes.length);
    }

}
```

参见第 14 章关于类被编译到内存中然后加载的示例。

#### 4.5.4. 上下文类加载器（The Context Class Loader）

大多数时候，你不需要担心类加载过程。类在被其他类需要时会被透明地加载。然而，如果一个方法动态加载类，而该方法是从一个本身通过另一个类加载器加载的类中调用的，就会出现问题。这里有一个具体的例子。

1. 你提供了一个由系统类加载器加载的工具类，它有一个方法：

```java
public class Util {
    Object createInstance(String className) {
        Class<?> cl = Class.forName(className);
        ...
    }
    ...
}
```

2. 你使用另一个类加载器加载插件，它从插件 JAR 中读取类。

3. 插件调用 `Util.createInstance("com.mycompany.plugins.MyClass")` 来实例化插件 JAR 中的类。

插件的作者期望该类被加载。然而，`Util.createInstance` 使用它自己的类加载器来执行 `Class.forName`，而该类加载器不会查找插件 JAR。这种现象被称为 `classloader inversion`（类加载器反转）。

一种解决方法是将类加载器传递给工具方法，然后传递给 `forName` 方法。

```java
public class Util {
    public Object createInstance(String className, ClassLoader loader) {
        Class<?> cl = Class.forName(className, true, loader);
        ...
    }
    ...
}
```

另一种策略是使用当前线程的 `context class loader`（上下文类加载器）。主线程的上下文类加载器是系统类加载器。当创建新线程时，它的上下文类加载器被设置为创建线程的上下文类加载器。因此，如果你不做任何操作，所有线程的上下文类加载器都将设置为系统类加载器。但是，你可以通过调用设置任何类加载器：

```java
Thread t = Thread.currentThread();
t.setContextClassLoader(loader);
```

工具方法随后可以获取该类加载器：

```java
public class Util {
    Object createInstance(String className) {
        Thread t = Thread.currentThread();
        ClassLoader loader = t.getContextClassLoader();
        Class<?> cl = Class.forName(className, true, loader);
        ...
    }
}
```

#### 提示

如果你写了一个通过名称加载类的方法，不要简单地使用方法的类加载器。调用插件类的方法时，应用程序将类加载器设置为插件加载器。之后恢复之前的设置。

#### 4.5.5. 服务加载器（Service Loaders）

某些服务在程序组装或部署时需要配置。实现此目的的方法是提供不同的实现，并让程序从中选择一个。`ServiceLoader` 类便于加载符合通用接口的服务实现。

定义一个接口（或者如果你喜欢，一个超类），包含每个服务实例应该提供的方法。例如，假设你的服务提供加密。

```java
package com.corejava.crypt;

public interface Cipher {
    byte[] encrypt(byte[] source, byte[] key);
    byte[] decrypt(byte[] source, byte[] key);
    int strength();
}
```

服务提供者提供一个或多个实现此服务的类，例如：

```java
package com.corejava.crypt.impl;

public class CaesarCipher implements Cipher {
    public byte[] encrypt(byte[] source, byte[] key) {
        var result = new byte[source.length];
        for (int i = 0; i < source.length; i++)
            result[i] = (byte)(source[i] + key[0]);
        return result;
    }

    public byte[] decrypt(byte[] source, byte[] key) {
        return encrypt(source, new byte[] { (byte) -key[0] });
    }

    public int strength() { return 1; }
}
```

现在在 `META-INF/services` 目录下的一个 UTF-8 编码文本文件中添加提供者类的名称。文件名是接口的全限定名。在我们的示例中，文件 `META-INF/services/com.corejava.crypt.Cipher` 包含行：

```text
com.corejava.crypt.impl.CaesarCipher
```

完成这些准备后，程序将如下初始化服务加载器：

```java
public static ServiceLoader<Cipher> cipherLoader = ServiceLoader.load(Cipher.class);
```

这在程序中只需执行一次。

服务加载器的 `iterator` 方法提供了一个用于遍历所有提供的服务实现的迭代器。（有关迭代器的更多详细信息，请参阅第 7 章）。使用增强型 `for` 循环来遍历它们是最简单的。在循环中，选择一个合适的对象来执行服务。

```java
public static Cipher getCipher(int minStrength) {

    for (Cipher cipher : cipherLoader) // 隐式调用 iterator

        if (cipher.strength() >= minStrength) return cipher;

    return null;

}
```

或者，你可以使用流（参见第 8 章）来定位所需的服务。`stream` 方法产生一个 `ServiceLoader.Provider` 实例的流。该接口拥有 `type` 和 `get` 方法，用于获取提供者类和提供者实例。如果你按类型选择提供者，只需调用 `type`，而不会不必要地实例化服务实例。在示例中，我们需要获取提供者，因为我们要对具有所需强度的加密流进行过滤：

```java
public static Optional<Cipher> getCipher2(int minStrength) {

    return cipherLoader.stream()

        .map(ServiceLoader.Provider::get)
        .filter(c -> c.strength() >= minStrength)
        .findFirst();

}
```

如果你愿意接受任何实现，只需调用 `findFirst`：



```java
Optional<Cipher> cipher = cipherLoader.findFirst();
```

`Optional` 类在第 8 章中会有解释。

## 4.6. 反射

反射允许程序在运行时检查对象的内容，并在其上调用任意方法。这种能力对于实现如对象关系映射器或 GUI 构建器等工具非常有用。

由于反射主要对工具的构建者感兴趣，应用程序程序员可以安全地跳过本节，并在需要时再回来。

### 4.6.1. 枚举类成员

`java.lang.reflect` 包中的三个类 `Field`、`Method` 和 `Constructor` 描述类的字段、方法和构造函数。所有三个类都有一个名为 `getName` 的方法，返回成员名称。`Field` 类有一个 `getType` 方法，返回一个 `Class` 对象，描述字段类型。`Method` 和 `Constructor` 类拥有报告类型的方法，`Method` 类也报告返回类型。

这三个类都有一个名为 `getModifiers` 的方法，返回一个整数，其位描述了使用的修饰符（如 `public` 或 `static`）。你可以使用 `Modifier.isPublic` 和 `Modifier.isStatic` 等静态方法来分析 `getModifiers` 返回的整数。`Modifier.toString` 返回修饰符的字符串。`Class` 类的 `getFields`、`getMethods` 和 `getConstructors` 方法返回支持的公共字段、方法和构造函数；这包括继承的成员。`getDeclaredFields`、`getDeclaredMethods` 和 `getDeclaredConstructors` 方法返回类声明的所有字段、方法和构造函数；这包括私有的、包私有的成员，但不包括父类的成员。`Executable` 类的 `getParameters` 方法返回描述方法参数的 `Parameter` 对象数组。

**注意**

只有当类使用 `-parameters` 标志编译时，参数名称在运行时才是可用的。例如，下面是你可以打印类所有方法的代码：

```java
Class<?> cl = Class.forName(className);

while (cl != null) {

      for (Method m : cl.getDeclaredMethods()) {

          System.out.println(
              Modifier.toString(m.getModifiers()) + " " +
              m.getReturnType().getCanonicalName() + " " +
              m.getName() + Arrays.toString(m.getParameters()));

      }

      cl = cl.getSuperclass();
}
```

这段代码的卓越之处在于它可以分析 Java 虚拟机加载的任何类——而不仅仅是编译时可用的类。

**注意**

正如你在第 15 章中看到的，Java 平台模块系统对反射访问有严格限制。默认情况下，只有同一模块中的类可以通过反射进行分析。然而，Java 库类属于不同的模块，对其非公共成员的反射访问是被限制的。

### 4.6.2. 检查对象

如上一节所示，你可以获取描述对象字段类型和名称的 `Field` 对象。这些 `Field` 对象可以做得更多：它们可以访问具有该字段的对象的值。例如，下面是枚举对象所有字段的方法：

```java
Object obj = ...;

for (Field f : obj.getClass().getDeclaredFields()) {

    f.setAccessible(true);

    Object value = f.get(obj);

    System.out.println(f.getName() + ":" + value);
}
```

关键在于读取字段值的 `get` 方法。如果字段是基本类型，则返回一个包装对象；在这种情况下，你也可以调用 `getInt`、`getDouble` 等方法。

**注意**

在使用 `Field` 和 `Method` 对象之前，必须使它们“可访问”。调用 `setAccessible(true)` 会解锁字段或方法。然而，模块系统或安全管理器可能会阻止请求。在这种情况下，如果字段或方法不可访问，`trySetAccessible` 方法会简单返回 `false`。

**注意**

正如你在第 15 章中看到的，Java 平台包包含在模块中，其类受来自反射的保护。例如，如果你调用：

```java
Field f = String.class.getDeclaredField("value");

f.setAccessible(true);
```

将抛出 `InaccessibleObjectException`。

一旦字段可访问，你也可以设置它。这段代码将作用于 `obj`，无论它属于哪个类，只要它有一个 `double` 或 `Double` 类型的 `salary` 字段。

```java
Field f = obj.getClass().getDeclaredField("salary");

f.setAccessible(true);

double value = f.getDouble(obj);

f.setDouble(obj, value * 1.1);
```

### 4.6.3. 调用方法

就像 `Field` 对象可以用于读写对象的字段一样，`Method` 对象可以在对象上调用给定的方法。

```java
Method m = ...;

Object result = m.invoke(obj, arg1, arg2, ...);
```

如果方法是静态的，请为初始参数提供 `null`。

要获取方法，你可以搜索在第 4.6.1 节中看到的 `getMethods` 或 `getDeclaredMethods` 返回的数组。或者你可以调用 `getMethod` 并提供参数类型。例如，在 `Person` 对象上获取 `setName(String)` 方法：

```java
Person p = ...;

Method m = p.getClass().getMethod("setName", String.class);

m.invoke(obj, "********");
```

**注意**

尽管 `clone` 是所有数组类型的公共方法，但在描述数组的 `Class` 对象上调用 `getMethod` 时，它并不会报告。

### 4.6.4. 构造对象

要构造对象，首先找到 `Constructor` 对象，然后调用其 `newInstance` 方法。例如，假设你知道某个类有一个参数为 `int` 的公共构造函数。那么你可以这样构造新实例：

```java
Constructor constr = cl.getConstructor(int.class);

Object obj = constr.newInstance(42);
```

### 注意事项

`Class` 类有一个 `newInstance` 方法，用于通过无参构造函数构造给定类的对象。该方法现在已过时，因为它有一个奇异的缺陷：如果无参构造函数抛出了受检异常（checked exception），`newInstance` 方法会重新抛出它，*尽管它并未被声明*，从而完全破坏了对受检异常的编译检查。相反，你应该调用 `cl.getConstructor().newInstance()`。这样任何异常都会被封装在 `InvocationTargetException` 中。

表 4.5 总结了处理 `Field`、`Method` 和 `Constructor` 对象的最重要方法。

#### 表 4.5：`java.lang.reflect` 包中的实用类和方法

![images](img/04tab05.jpg)![images](img/04tab05a.jpg)

### 4.6.5. JavaBeans

许多面向对象的编程语言支持属性，将表达式 `object.propertyName` 映射为 getter 或 setter 方法的调用，取决于该属性是可读还是可写的。Java 没有这种语法，但它有一种约定，即属性与 getter/setter 对相对应。JavaBean 是一个具有无参构造函数、getter/setter 对以及任意数量其他方法的类。

getter 和 setter 必须遵循特定的模式：

```java
public Type getProperty()

public void setProperty(Type newValue)
```

通过省略 setter 或 getter 可以实现只读和只写属性。

属性名称是 `get`/`set` 后后缀的去驼峰化（decitalized）形式。例如，`getSalary`/`setSalary` 对会产生一个名为 `salary` 的属性。然而，如果后缀的前两个字母是大写的，则原样保留。例如，`getURL` 产生一个名为 `URL` 的只读属性。

### 注意

对于布尔类型属性，你可以使用 `getProperty` 或 `isProperty` 作为 getter，且优选后者。

JavaBeans 起于 GUI 构造器，JavaBeans 规范包含处理属性编辑器、属性更改事件和自定义属性发现的奥秘规则。这些功能在如今很少使用。

当你需要处理任意属性时，使用标准类来支持 JavaBeans 是好主意。给定一个类，如下所示获取 `BeanInfo` 对象：

```java
Class<?> cl = ...;

BeanInfo info = Introspector.getBeanInfo(cl);

PropertyDescriptor[] props = info.getPropertyDescriptors();
```

对于给定的 `PropertyDescriptor`，调用 `getName` 和 `getPropertyType` 获取属性的名称和类型。`getReadMethod` 和 `getWriteMethod` 产生 getter 和 setter 的 `Method` 对象。

遗憾的是，没有方法根据指定的属性名获取描述符，因此你必须遍历描述符数组：

```java
String propertyName = ...;

Object propertyValue = null;

for (PropertyDescriptor prop : props) {

    if (prop.getName().equals(propertyName))
       propertyValue = prop.getReadMethod().invoke(obj);
}
```

### 4.6.6. 处理数组

`isArray` 方法检查给定的 `Class` 对象是否表示数组。如果是，`getComponentType` 方法产生描述数组元素类型的 `Class`。若要进行进一步分析或动态创建数组，请使用 `java.lang.reflect` 包中的 `Array` 类。表 4.6 显示了它的方法。

作为一个练习，让我们实现 `Arrays` 类中的 `copyOf` 方法。回想该方法如何用于扩展一个已满的数组。

```java
var friends = new Person[100];

...

// 数组已满

friends = Arrays.copyOf(friends, 2 * friends.length);
```

如何写这样一个泛型方法？这里是第一次尝试：

```java
public static Object[] badCopyOf(Object[] array, int newLength) { // 无用

    var newArray = new Object[newLength];

    for (int i = 0; i < Math.min(array.length, newLength); i++)

        newArray[i] = array[i];

    return newArray;

}
```

然而，在实际使用生成的数组时存在问题。此方法返回的数组类型是 `Object[]`。对象数组不能被强制转换为 `Person[]` 数组。点在于，正如我们之前提到的，Java 数组会记住其元素的类型——即创建它的 `new` 表达式中所使用的类型。将 `Person[]` 数组临时强制转换为 `Object[]` 数组然后再转换回是合法的，但一个初始类型为 `Object[]` 数组的数组永远无法转换为 `Person[]` 数组。

为了创建一个与原数组相同类型的新数组，你需要 `Array` 类的 `newInstance` 方法。提供组件类型和所需的长度：

```java
public static Object goodCopyOf(Object array, int newLength) {

    Class<?> cl = array.getClass();

    if (!cl.isArray()) return null;

    Class<?> componentType = cl.getComponentType();

    int length = Array.getLength(array);

    Object newArray = Array.newInstance(componentType, newLength);

    for (int i = 0; i < Math.min(length, newLength); i++) {

        Array.set(newArray, i, Array.get(array, i));
    }

    return newArray;
}
```

注意此 `copyOf` 方法可以扩展任何类型的数组，而不只是对象数组。

```java
int[] primes = { 2, 3, 5, 7, 11 };

int[] copy = (int[]) copyOf(primes, 10);
```

`copyOf` 的参数类型是 `Object`，而不是 `Object[]`。

表 4.6：`java.lang.reflect.Array` 类

![images](img/04tab06.jpg)

### 4.6.7. 代理

`Proxy` 类可以在运行时创建给定接口的新类。这种代理只有在编译时不知道需要实现哪些接口时才是必要的。

代理类拥有指定接口所需的方法，以及 `Object` 类中定义的方法（`toString`、`equals` 等）。然而，由于无法在运行时为这些方法定义新代码，你需要提供一个调用处理器（invocation handler），即实现 `InvocationHandler` 接口的对象。该接口有一个方法：

```java
Object invoke(Object proxy, Method method, Object[] args)
```

当在代理对象上调用方法时，处理器的 `invoke` 方法会被调用，并传入 `Method` 对象和调用参数。处理器必须决定如何处理该调用。处理器可以采取许多操作，例如将调用路由到远程服务器或为了调试目的跟踪调用。

要创建代理对象，使用 `Proxy` 类的 `newProxyInstance` 方法。该方法有三个参数：

- ![images](img/sq.jpg) 类加载器（参见第 4.5.3 节），或使用 `null` 使用默认类加载器
- ![images](img/sq.jpg) `Class` 对象数组，每个接口对应一个
- ![images](img/sq.jpg) 调用处理器

为了展示代理的机械原理，这里有一个示例，其中数组填充了 `Integer` 对象的代理，并将调用转发给原始对象：

```java
var values = new Object[1000];

for (int i = 0; i < values.length; i++) {

    var value = Integer.valueOf(i);

    values[i] = Proxy.newProxyInstance(
        null,

        value.getClass().getInterfaces(),

        // 调用处理器的 Lambda 表达式
        (Object proxy, Method m, Object[] margs) -> {

            System.out.println(value + "." + m.getName() + Arrays.toString(margs));

            return m.invoke(value, margs);

        });

}
```

当调用：

```java
Arrays.binarySearch(values, Integer.valueOf(500));
```

时会产生以下输出：

```text
499.compareTo[500]
749.compareTo[500]
624.compareTo[500]
561.compareTo[500]
530.compareTo[500]
514.compareTo[500]
506.compareTo[500]
502.compareTo[500]
500.compareTo[500]
```

你可以看到二分查找算法如何每一步将搜索范围缩小一半来定位目标键。

关键点在于，`compareTo` 方法是通过代理调用的，尽管这在代码中并没有显式提到。`Integer` 实现的任何接口中的所有方法都被代理了。

### 注意事项



当调用处理程序（invocation handler）被无参数的方法调用时，参数数组为`null`，而不是长度为`0`的`Object[]`数组。这是完全不可理喻的，你不应该在自己的代码中这样做。

### 练习题

1. 定义类`Point`，包含构造函数`public Point(double x, double y)`和访问器方法`getX`, `getY`。定义子类`LabeledPoint`，包含构造函数`public LabeledPoint(String label, double x, double y)`和访问器方法`getLabel`。

2. 为上述练习中的类定义`toString`、`equals`和`hashCode`方法。

3. 将练习 1 中`Point`类的实例变量`x`和`y`改为`protected`。证明`LabeledPoint`类只能在`LabeledPoint`实例中访问这些变量。

4. 定义抽象类`Shape`，包含一个`Point`类型的实例变量、一个构造函数、一个具体方法`public void moveBy(double dx, double dy)`（按给定量移动点）以及一个抽象方法`public Point getCenter()`。提供具体的子类`Circle`、`Rectangle`、`Line`，构造函数分别为`public Circle(Point center, double radius)`、`public Rectangle(Point topLeft, double width, double height)`和`public Line(Point from, Point to)`。

5. 为上述练习中的类定义`clone`方法。

6. 假设在第 4.3.2 节中，`Item.equals`方法使用了`instanceof`测试。实现`DiscountedItem.equals`使得当`otherObject`是`Item`时只比较父类，但如果它是`DiscountedItem`则也包含折扣信息。证明该方法保持了对称性但违反了传递性——即，找到一组项目和折扣项目，使得`x.equals(y)`和`y.equals(z)`成立，但`x.equals(z)`不成立。

7. 定义方法`Object add(Object first, Object second)`。如果参数是`Number`实例，则相加值。如果是`Boolean`实例，若其中任一为真则返回`Boolean.TRUE`。否则，将它们拼接为字符串。使用带有模式匹配的`instanceof`运算符。

8. 为八种原色组合`BLACK`、`RED`、`BLUE`、`GREEN`、`CYAN`、`MAGENTA`、`YELLOW`、`WHITE`定义一个枚举类型，包含`getRed`、`getGreen`和`getBlue`方法。

9. 从概念上讲，列表要么为空，要么有一个头部元素和一个尾部（尾部再次是一个列表）。使用密封类（sealed classes）来为字符串列表建模。提供一个包含恰两个子类`EmptyStringList`和`NonEmptyStringList`的`StringList`接口。使用详尽模式匹配实现`size`和`append`方法。

10. `Class`类有六个方法可以产生`Class`对象代表的类型的字符串表示。它们在应用于数组、泛型类型、内部类和原始类型时有何不同？

11. 编写一个“通用”的`toString`方法，利用反射生成一个包含对象所有实例变量的字符串。如果能处理循环引用将获得额外加分。

12. 使用第 4.6.1 节中的`MethodPrinter`程序列出`int[]`类的所有方法。如果能识别出本章中讨论的那个被描述错误的唯一方法，将获得额外加分。

13. 编写“Hello, World”程序，使用反射查找`java.lang.System`的`out`字段，并使用`invoke`调用`println`方法。

14. 测量普通方法调用与通过反射调用方法的性能差异。

15. 编写一个方法，打印任何代表具有`double`或`Double`类型参数的静态方法的`Method`值表格。除了`Method`对象外，还要接收一个下限、上限和步长。通过打印`Math.sqrt`和`Double.toHexString`的表格来演示你的方法。重复此过程，使用`DoubleFunction<Object>`代替`Method`。对比两种方法的安全性、效率便利性。

## 5. 异常、断言与日志

在许多程序中，处理意外情况比实现“理想”场景更为复杂。与大多数现代编程语言一样，Java 拥有一种健壮的异常处理机制，可以将控制权从故障点转移到胜任的处理器。此外，`assert`提供了一种结构化且高效的方式表达内部假设。最后，你将看到如何使用日志 API 来记录程序执行过程中各种事件（无论是例行的还是可疑的）。本章的关键点是：

1. 当你抛出异常时，控制权会被转移到最近的处理器。

2. 在 Java 中，异常由编译器跟踪。

3. 使用`try/catch`结构来处理异常。

4. try-with-resources 语句在执行后自动关闭资源。

5. 使用`try/finally`结构处理无论是否执行都必须的操作。

6. 你可以捕获并重抛异常，或将其链接到另一个异常。

7. 堆栈跟踪描述了执行点处的所有方法调用。

8. 断言检查条件（前提是断言已启用），如果不符合条件则抛出错误。

9. 日志器按层次排列，并可以接收从`SEVERE`到`FINEST`级别的日志消息。

10. 日志处理器可以将日志消息发送到不同的目标，格式化器控制消息格式。

11. 你可以通过日志配置控制日志属性。

### 5.1 异常处理

当方法遇到无法履行合约的情况时该怎么办？传统的答案是方法应该返回某个错误代码。但这对调用该方法的程序员来说是麻烦的。调用者被迫检查错误，如果它们无法处理，则向自己的调用者返回错误代码。

与其让错误代码在方法调用链中传播，Java 支持异常处理，方法可以通过“抛出”异常来信号严重问题。调用链中的某个方法（但不一定是直接调用者）负责通过“捕获”异常来处理它。异常处理的基本优势是将检测错误与处理错误的过程解耦。在接下来的章节中，你将看到如何在 Java 中处理异常。

#### 5.1.1 抛出异常

方法可能会发现自己无法执行当前的任务。也许是所需的资源缺失，或者调用时的参数不一致。在这种情况下，最好的办法是抛出一个异常。

假设你实现了一个在两个边界之间产生随机整数的方法：

```
public static int randInt(int low, int high) {
    return low + (int) (Math.random() * (high - low + 1));
}
```

如果有人调用`randInt(10, 5)`会发生什么？尝试修复这个问题可能不是好主意，因为调用者可能在多个方面都困惑。相反，抛出一个适当的异常：

```
if (low > high)
    throw new IllegalArgumentException(
        "low should be <= high but low is %d and high is %d".formatted(low, high));
```

如你所见，`throw`语句用于“抛出”一个类的对象——在这里是`IllegalArgumentException`。该对象是使用一条调试消息来构造的。你将在下一节中看到如何选择合适的异常类。

当执行`throw`语句时，正常的执行流会立即中断。`randInt`方法停止执行，并且不会向其调用者返回值。相反，控制将转移到处理程序，正如你在第 5.1.4 节中看到的那样。

## 5.1.2 异常层次结构

图 5.1 显示了 Java 中异常的层次结构。所有异常都是`Throwable`类的子类。`Error`的子类是在发生程序无法预料处理的异常情况时抛出的异常，例如内存耗尽。对于错误，你所做的做的多也就是向用户发送一条消息，告诉他们发生了严重的错误。

![images](img/05fig01.jpg)

图 5.1：异常层次结构

程序员报告的异常是`Exception`类的子类。这些异常分为两类：

![Images](img/sq.jpg) 未检查（Unchecked）异常是`RuntimeException`的子类。

![Images](img/sq.jpg) 所有其他异常都是已（checked）异常。

正如你将在下一节中看到的，程序员要么捕获已异常，要么在方法头中声明它们。编译器会检查这些异常是否被妥善处理。

注意

`RuntimeException`这个名字起得不好。当然，所有异常都发生在运行时。然而，`RuntimeException`的子类异常在编译期间是不被检查的。

已异常用于应该预见到可能会失败的情况。失败的一个常见原因是输入和输出。文件可能会损坏，网络连接可能会失败。许多异常类继承自`IOException`，你应该使用合适的异常类来报告你遇到的任何错误。例如，当本该存在的文件不存在时，应抛出一个`FileNotFoundException`。

未检查异常表示由程序员引起的逻辑错误，而不是不可避免的外部风险。例如，`NullPointerException`是不检查的。几乎任何方法都可能抛出这种异常，程序员不应该花时间去捕获它们。相反，他们应该确保从根本上不对`null`进行解引用。

有时，实现者需要根据自己的判断来区分已异常和未检查异常。考虑调用`Integer.parseInt(str)`。当`str`不包含有效整数时，它会抛出一个未检查的`NumberFormatException`。另一方面，当`str`不包含有效的类名时，`Class.forName(str)`会会抛出一个已检查的`ClassNotFoundException`。

为什么会有这种区别？这是因为在调用`Integer.parseInt`之前，可以检查字符串是否为有效整数，但在实际尝试加载类之前，无法知道一个类是否可以被加载。

Java API 提供了许多异常类，例如`IOException`、`IllegalArgumentException`等。你应该在适当的时候使用它们。然而，如果没有哪一个标准异常类适用于你的需求，你可以通过扩展`Exception`、`RuntimeException`或另一个现有的异常类来创建自己的异常。

当你这样做时，同时提供一个无参数构造函数和一个带消息字符串的构造函数是一个好主意。例如：

```
public class FileFormatException extends IOException {
    public FileFormatException() {}
    public FileFormatException(String message) {
        super(message);
    }
    // 也为链式异常添加构造函数——参见第 5.1.7 节
}
```

## 5.1.3 声明已异常

任何可能引起已异常的方法必须在方法头中使用`throws`子句声明它：

```
public void write(Object obj, String filename)
    throws IOException, ReflectiveOperationException
```

列出方法可能抛出的异常，可能是因为`throw`语句，也因为它调用了另一个带有`throws`子句的方法。

在`throws`子句中，你可以将异常合并到一个公共超类中。这是否是一个好主意取决于异常。例如，如果一个方法可以抛出多个`IOException`的子类，那么在`throws IOException`子句中涵盖它们是有意义的。但如果异常之间彼此无关，不要将它们合并为`throws Exception`——那将违背异常检查的目的。

提示

有些程序员认为承认方法可能会抛出异常是可耻的。与其这样做，不是直接处理更好吗？实际上，恰恰相反。你应该让每个异常找到胜任的处理器。异常的黄金法则是：“尽早抛出，晚捕获”。

当你重写一个方法时，它抛出的已异常不能多于父类方法声明的。例如，如果你扩展了本节开始的`write`方法，则重写的方法可以抛出更少的异常：

```
public void write(Object obj, String filename)
    throws FileNotFoundException
```

但如果该方法尝试抛出一个无关的已异常（例如`InterruptedException`），它将无法通过编译。

警告

如果父类方法没有`throws`子句，则没有重写方法可以抛出已异常。

你可以使用 javadoc 的`@throws`标签来记录方法何时抛出（已检查或未检查）异常。大多数程序员只在有有意义的内容需要记录时这样做。例如，在输入输出出现问题时告诉用户抛出了`IOException`意义不大。但这样的注释是有意义的：

```
@throws NullPointerException 如果 filename 为 null
@throws FileNotFoundException 如果没有名为 filename 文件
```

注意

你永远不会指定 lambda 表达式的异常类型。然而，如果 lambda 表达式可以抛出已异常，你只能将其传递给声明了该异常的函数式接口。例如，调用

```
list.forEach(obj -> write(obj, "output.dat"));
```

是错误的。`forEach`方法的参数类型是函数式接口

```
public interface Consumer<T> {
    void accept(T t);
}
```

`accept`方法没有声明抛出任何异常。

## 5.1.4 捕获异常

要捕获异常，请设置`try`块。其简单形式如下：

```
try {
    statements
} catch (ExceptionClass ex) {
    handler
}
```

如果在执行`try`块语句时发生了指定的异常，控制将转移到处理程序。异常变量（示例中的`ex`）引用处理程序根据需要检查的异常对象。

对这种基本结构进行两种修改。你可以为不同的异常类设置多个处理程序：

```
try {
   statements
} catch (ExceptionClass1 ex) {
   handler1
} catch (ExceptionClass2 ex) {
   handler2
} catch (ExceptionClass3 ex) {
   handler3
}
```

`catch`子句是从上到下匹配的，因此最具体的异常类必须排在前面。

或者，你可以在多个异常类之间共享一个处理器：

```
try {
   statements
} catch (ExceptionClass1 | ExceptionClass2 | ExceptionClass3 ex) {
   handler
}
```

在这种情况下，处理程序只能调用异常变量上属于所有异常类的方法。

### 5.1.5 try-with-resources 语句

异常处理的一个问题是资源管理。假设你向文件写入内容并在完成后关闭它：

```java
ArrayList<String> lines = ...;

var out = new PrintWriter("output.txt");

for (String line : lines) {
    out.println(line.toLowerCase());
}

out.close();
```

这段代码隐藏着一个危险。如果任何方法抛出异常，`out.close()`的调用将永远不会发生。这是糟糕的。输出可能会丢失，或者如果触发多次异常，系统可能会耗尽文件句柄。

`try`语句的一种特殊形式可以解决这个问题。你可以在`try`语句的头部指定资源`resources`）。资源必须属于实现了`AutoCloseable`接口的类。你可以在`try`块的头部中声明变量：

```java
ArrayList<String> lines = ...;

try (var out = new PrintWriter("output.txt")) { // 变量声明
    for (String line : lines)
        out.println(line.toLowerCase());
}
```

或者，你可以在头部提供之前声明的有效最终的（effectively final）变量：

```java
var out = new PrintWriter("output.txt");

try (out) { // 有效最终变量
    for (String line : lines)
        out.println(line.toLowerCase());
}
```

`AutoCloseable`接口仅有一个方法：

```java
public void close() throws Exception
```

#### Note

还有一个`Closeable`接口。它是`AutoCloseable`的子接口，同样有一个`close`方法。然而，该方法被声明为抛出`IOException`。

当`try`块退出时（无论是由于正常结束还是因为抛出了异常），资源对象的`close`方法都会被调用。例如：

```java
try (var out = new PrintWriter("output.txt")) {
    for (String line : lines) {
        out.println(line.toLowerCase());
    }
} // 在此处调用 out.close()
```



你可以声明多个资源，用分号隔开。这里有两个资源声明的示例：

```java
try (var in = new Scanner(Path.of("/usr/share/dict/words"));
        var out = new PrintWriter("output.txt")) {
    while (in.hasNext())
        out.println(in.next().toLowerCase());
}
```

资源按照它们初始化的相反顺序关闭——也就是说，`out.close()` 在 `in.close()` 之前被调用。

假设 `PrintWriter` 构造函数抛出了异常。此时 `in` 已经初始化但 `out` 尚未初始化。`try` 语句做了正确的事：调用 `in.close()` 并传播异常。

某些 `close` 方法可能会抛出异常。如果当 `try` 块正常完成时发生这种情况，该异常将被抛给调用者。然而，如果抛出了另一个异常，导致资源的 `close` 方法被调用，并且其中一个抛出了异常，那么该异常的重要性可能低于原始异常。

在这种情况下，原始异常会被重新抛出，而调用 `close` 产生的异常会被捕获并作为“被抑制的”（suppressed）异常附加。这是一个非常实用的机制，手动实现将非常繁琐（参见练习 5）。当你捕获到主异常时，可以通过调用 `getSuppressed` 方法获取次要异常：

```java
try {
    ...
} catch (IOException ex) {
    Throwable[] secondaryExceptions = ex.getSuppressed();
    ...
}
```

如果你想在一种（希望是罕见的）无法使用 try-with-resources 语句的情况下，自己实现这种机制，请调用 `ex.addSuppressed(secondaryException)`。

try-with-resources 语句可以选择包含 `catch` 子句，以捕获语句中的任何异常。

### 5.1.6. `finally` 子句

正如你所见，无论是否发生异常，try-with-resources 语句都会自动关闭资源。有时，你需要清理某些不是 `AutoCloseable` 的内容。在这种情况下，请使用 `finally` 子句：

```java
try {
    执行工作
} finally {
    清理工作
}
```

`finally` 子句在 `try` 块结束时（无论是正常结束还是由于异常）都会执行。

每当你需要获取并释放锁、或者增加和递减计数器、或者在栈上推入内容并在完成后将其弹出时，这种模式就会出现。你希望确保这些操作无论可能抛出什么异常都会发生。

你应该避免在 `finally` 子句中抛出异常。如果 `try` 块的主体由于异常而终止，它会被 `finally` 子句中的异常所掩盖。你在上一节中看到的抑制机制仅适用于 try-with-resources 语句。

同样，`finally` 子句不应包含 `return` 语句。如果 `try` 块的主体也有 `return` 语句，那么 `finally` 子句中的那一个将替换返回值。考虑这个示例：

```java
public static int parseInt(String s) {
    try {
        return Integer.parseInt(s);
    } finally {
       return 0; // 错误
    }
}
```

看起来在调用 `parseInt("42")` 时，`try` 块的主体返回了整数 42。然而，`finally` 子句在方法实际返回之前被执行，导致方法返回 0，忽略了原始返回值。

情况更糟了。考虑调用 `parseInt("zero")`。`Integer.parseInt` 方法抛出了 `NumberFormatException`。然后 `finally` 子句被执行，而 `return` 语句吞噬了异常！

#### Tip

`finally` 子句旨在清理资源。不要在 `finally` 子句中改变控制流的语句（`return`、`throw`、`continue`）。

可以形成带有 `catch` 子句以及 `finally` 子句的 `try` 语句。但你必须小心 `finally` 子句中的异常。例如，看下面这个来自在线教程的 `try` 块：

```java
BufferedReader in = null;
try {
    in = Files.newBufferedReader(path, StandardCharsets.UTF_8);
    从 in 读取
} catch (IOException ex) {
    System.err.println("Caught IOException: " + ex.getMessage());
} finally {
    if (in != null) {
        in.close(); // 注意——可能抛出异常
    }
}
```

这段代码显然考虑了 `Files.newBufferedReader` 抛出异常的情况，但它实际上漏掉了：：一个异常。通常最好将复杂的 `try/catch/finally` 语句重写为 try-with-resources 语句，或者在 `try/catch` 中嵌套 `try/finally`——参见练习 6。

#### 5.1.7. 重新抛出和链异常

当异常发生时，你可能不知道该如何处理，但你可能想要记录失败。在这种情况下，重新抛出异常，以便胜任的处理器可以处理它：

```java
try {
    执行工作
} catch (Exception ex) {
    logger.log(level, message, ex);
    throw ex;
}
```

#### Note

当这段代码位于一个可能抛出检查异常的方法内部时，发生了一些微妙的事情。假设闭包方法声明为：

```java
public void read(String filename) throws IOException
```

乍一看，似乎需要将 `throws` 子句改为 `throws Exception`。然而，Java 编译器会仔细跟踪流向，并意识到 `ex` 只能是 `try` 块中某个语句抛出的异常，而不是任意的 `Exception`。

有时，你想更改抛出异常的类。例如，你可能需要用对子系统用户合理的异常类来报告子系统的失败。假设你在 servlet 中遇到了数据库错误。执行 servlet 的代码可能不想详细知道发生了什么，但它确实想知道是 servlet 的错。在这种情况下，捕获原始异常并将其链到更高层次的异常上：

```java
try {
    访问数据库
} catch (SQLException ex) {
    throw new ServletException("database error", ex);
}
```

当捕获到 `ServletException` 时，可以如下所示获取原始异常：

```java
Throwable cause = ex.getCause();
```

`ServletException` 类有一个构造函数，可以将异常的成因作为参数传入。并不是所有的异常类都这样做。在这种情况下，你必须调用 `initCause` 方法，如下所示：

```java
try {
    Access the database
}
catch (SQLexception ex) {
    var ex2 = new CruftyOldException("database error");
    ex2.initCause(ex);
    throw ex2;
}
```

如果你自定义异常类，除了第 5.1.2 节中描述的两个构造函数外，还应该提供以下构造函数：

```java
public class FileFormatException extends IOException {
    ...
    public FileFormatException(Throwable cause) { initCause(cause); }

    public FileFormatException(String message, Throwable cause) {
        super(message);
        initCause(cause);
    }
}
```

**提示**

如果在不允许抛出检举异常的方法中发生了检举异常，链式技术也很有用。你可以捕获该检举异常并将其链到一个非检举异常上。

#### 5.1.8. 未捕获的异常与堆栈跟踪

如果异常在任何地方都没有被捕获，就会显示 `stack trace`（堆栈跟踪）——即异常抛出处所有待处理方法调用的列表。堆栈跟踪会被发送到 `System.err`，即错误消息流。

如果你想将异常保存到其他地方（以便供技术支持人员检查），可以设置默认的未捕获异常处理器：

```java
Thread.setDefaultUncaughtExceptionHandler((thread, ex) -> {
    Record the exception
});
```

**注意**

未捕获的异常会终止发生该异常的线程。如果你的应用程序只有一个线程（你目前为止看到的程序都是如此），那么程序在调用未捕获异常处理器后将会退出。

有时，你被迫捕获某个异常，但并真的不知道该如何处理它。例如，`Class.forName` 方法会抛出一个你需要处理的检举异常。与其忽略异常，不如至少打印出堆栈跟踪：

```java
try {
    Class<?> cl = Class.forName(className);
    ...
} catch (ClassNotFoundException ex) {
    ex.printStackTrace();
}
```

如果你想存储异常的堆栈跟踪，可以如下所示将其放入字符串中：

```java
var out = new ByteArrayOutputStream();
ex.printStackTrace(new PrintWriter(out));
String description = out.toString();
```

**注意**

如果你需要更详细地处理堆栈跟踪，请使用 `StackWalker` 类。例如，以下代码会打印所有的堆栈帧：

```java
StackWalker walker = StackWalker.getInstance();
walker.forEach(frame -> System.err.println("Frame: " + frame));
```

你也可以详细分析 `StackWalker.StackFrame` 实例。详情请参考 API 文档。

#### 5.1.9. 用于抛出异常的 API 方法

`Objects` 类有一个方法可以对参数进行空检查。这里是一个用法示例：

```java
public void process(String direction) {
    this.direction = Objects.requireNonNull(direction);
    ...
}
```

如果 `direction` 为 `null`，则会抛出 `NullPointerException`。乍一看，这似乎有点没意义，因为在使用该值时最终也会抛出 `NullPointerException`。但请从堆栈跟踪回溯考虑。当你看到对 `requireNonNull` 的调用是罪祸之首时，你立刻知道自己做错了。

你还可以为异常提供一个消息字符串：

```java
this.direction = Objects.requireNonNull(direction, "direction must not be null");
```

该方法的变体允许你提供一个备用值而不是抛出异常：

```java
this.direction = Objects.requireNonNullElse(direction, "North");
```

如果默认值的计算代价很高，请使用另一个变体：

```java
this.direction = Objects.requireNonNullElseGet(direction,
   () -> System.getProperty("com.horstmann.direction.default"));
```

只有当 `direction` 为 `null` 时，Lambda 表达式才会求值。

还有一个用于进行范围检查的便利方法：

```java
this.index = Objects.checkIndex(index, length);
```

如果索引在 0 到 `length - 1` 之间，则返回该索引；否则抛出 `IndexOutOfBoundsException`。

### 5.2. 断言

断言是防御性编程中常用的一种惯用法。假设你确定某个属性已满足，并且在代码中依赖该属性。例如，你可能正在计算：

```java
double y = Math.sqrt(x);
```

你确定 `x` 不是负数。尽管如此，你仍然想再次检查，而不是让“非数字”（NaN）浮点值渗透到你的计算中。当然，你可以抛出一个异常：

```java
if (x < 0) throw new IllegalStateException(x + " < 0");
```

但这个条件在测试完成后仍然留在程序中，会减慢运行速度。断言机制允许你在测试期间插入检查，并在生产代码中自动移除它们。

**注意**

在 Java 中，断言旨在作为验证内部假设的调试辅助，而不是强制契约的机制。例如，如果你想报告公共方法的参数不当，请不要使用断言，而要抛出 `IllegalArgumentException`。

#### 5.2.1. 使用断言

Java 中的断言语句有两种形式：

```java
assert condition;

assert condition : expression;
```

`assert` 语句评估条件，如果条件为假，则抛出 `AssertionError`。在第二种形式中，表达式会被转换为字符串并作为消息。

**注意**

如果表达式是 `Throwable`，它也会被设置为断言错误的成因（参见 5.1.7）。

例如，要断言 `x` 为非负数，你可以直接使用：

```java
assert x >= 0;
```

或者你可以将 `x` 的实际值传入 `AssertionError` 对象以便进行显示：

```java
assert x >= 0 : x;
```

### 5.2.2. 启用和禁用断言

默认情况下，断言是禁用的。通过在运行程序时使用 `-enableassertions` 或 `-ea` 来启用它们：

```bash
java -ea MainClass
```

你不需要重新编译程序，因为启用或禁用断言是由类加载器处理的。当禁用断言时，类加载器会剥离断言代码，从而不会影响速度。你甚至可以在特定的类或整个包中启用断言，例如：

```bash
java -ea:MyClass -ea:com.mycompany.mylib... MainClass
```

此命令将开启 `MyClass` 类以及 `com.mycompany.mylib` 包及其子包中所有类的断言。`-ea...` 开启默认包中所有类的断言。

你也可以用 `-disableassertions` 或 `-da` 禁用某些类和包的断言：

```bash
java -ea:... -da:MyClass MainClass
```

当你使用 `-ea` 和 `-da` 启用或禁用所有断言（而不是针对特定类或包），它们不适用于无类加载器加载的“系统类”。使用 `-enablesystemassertions/-esa` 来启用系统类的断言。

还可以通过以下方法动态控制类加载器的断言状态：

```java
void ClassLoader.setDefaultAssertionStatus(boolean enabled);

void ClassLoader.setClassAssertionStatus(String className, boolean enabled);

void ClassLoader.setPackageAssertionStatus(String packageName, boolean enabled);
```

与 `-enableassertions` 命令行一样，`setPackageAssertionStatus` 方法设置指定包及其子包的断言状态。

### 5.3. 日志记录

每个 Java 程序员都熟悉这种过程：在棘手的代码中插入 `System.out.println` 调用以了解程序的行为。当然，一旦你找到了问题的根源，就会移除这些打印语句——当下一个问题出现时，你又把它们加回来。日志框架的设计就是为了解决这个问题。

#### 5.3.1. 你应该使用 Java 日志框架吗？

Java 有一个标准的日志框架，通常以其包名 `java.util.logging` 命名，有时缩写为 `j.u.l`。然而，其他日志框架拥有更多功能且广泛使用，例如 Log4j（[`logging.apache.org/log4j/2.x/`](https://logging.apache.org/log4j/2.x/)）和 Logback（[`logback.qos.ch/`](https://logback.qos.ch/)）。



如果你想让你代码的用户选择日志框架，那么你应该使用一个“facade”（门面）库，将日志消息发送到首选的框架。一个常用且 API 良好的门面是 SLF4J（[`www.slf4j.org/`](https://www.slfj.org/)）。另一个门面是“平台日志 API”（也称为 JEP 246）。它非常基础，但是 JDK 的一部分。这个门面有时被称为`frontend`（前端）。它提供了程序员用于记录消息的 API。`backend`（后端）负责过滤、格式化消息并将其放入某处。后端需要由部署者进行配置，通常通过编辑配置文件来实现。

在接下来的章节中，我将向你展示如何使用平台日志 API 作为前端，并将`java.util.logging`作为后端。如果你发现前端 API 足够用，这是一个很合理的选择，因为你可以随时切换后端。

`java.util.logging`后端的特性比那些更流行的替代方案少，但对于许多用例来说已经足够。由于其简单性，它不容易受到攻击。相比之下，Log4j 的某些晦涩特性允许黑客构造程序输入，当这些输入被记录时，会导致恶意代码的执行。

无论你最终是否会使用它们，学习平台日志 API 和`java.util.logging`后端都能让你对日志框架的能力有一个良好的基础。

### 5.3.2 日志入门

平台日志记录器实现了`System.Logger`接口。每个日志记录器都有一个名称。名称可以是任意的，但它通常是生成日志消息的方法所属类的包名。你可以这样获取一个平台日志记录器：

```
System.Logger logger = System.getLogger("com.mycompany.myapp");
```

当你第一次请求具有给定名称的日志记录器时，它会被创建。对相同名称的后续调用将产生同一个记录器对象。

现在你准备好记录日志了：

```
logger.log(System.Logger.Level.INFO, "Opening file " + filename);
```

记录打印打印如下：

```
Aug 04, 2014 09:53:34 AM com.mycompany.myapp read

INFO: Opening file data.txt
```

注意，时间以及调用类和方法的名称会自动包含在内。

为了在程序部署时关闭这些信息性消息，你可以配置后端。对于`java.util.logging`后端，请准备一个包含以下内容的`logging.properties`文件：

```
handlers=java.util.logging.ConsoleHandler

com.mycompany.myapp.level=WARNING
```

然后像这样启动应用程序：

```
java -Djava.util.logging.config.file=logging.properties com.mycompany.myapp.Main
```

由于`INFO`级别低于`WARNING`级别，消息将不再显示。

获取日志记录器和记录消息的 API 是前端的一部分——在这种情况下，是平台日志 API。如果你使用不同的前端，API 将是不同的。

消息的去地、格式化和过滤，以及配置机制是后端的一部分——在这里是`java.util.logging`。如果你使用不同的后端，你需要遵循它的配置说明进行配置。

### 5.3.3 平台日志 API

正如你在上一节中看到的，每条记录的消息都有一个级别。`System.Logger.Level`枚举有以下值，按严重程度从高到低排序：`ERROR`、`WARNING`、`INFO`、`DEBUG`和`TRACE`。

提示

使用导入语句

```
import static java.lang.System.Logger.Level.*;
```

你可以缩短级别：

```
logger.log(INFO, "Opening file " + filename); // 代替 System.Logger.Level.INFO
```

在上面的示例中，即使消息被抑制，消息`"Opening file " + filename`也会创建。如果你担心创建消息字符串的成本，可以使用 lambda 表达式来代替：

```
logger.log(INFO, () -> "Opening file " + filename);
```

这样消息只有在实际被记录时才会被计算。

记录异常是很常见的：

```
catch (IOException ex) {

    logger.log(WARNING, "Cannot open file " + filename, ex);
}
```

你可以使用`MessageFormat`类（你将在第 13 章中看到）来格式化消息：

```
logger.log(WARNING, "Cannot open file {0}", filename)
```

可以使用资源包机制将日志消息本地化为不同的语言，该机制在第 13 章中也有介绍。

你可以使用该机制指定包：

```
logger.log(WARNING, "Cannot open file {0}", filename)
```

这样就不需要在每次调用时指定包。

```
logger.log(INFO, "file.bad");
```

或者，获取日志记录器：

```
System.Logger logger = System.getLogger("com.mycompany.myapp");
```

某些但并非所有这些功能（延迟消息计算、添加 throwable、格式化）都是支持的。表 5.1 显示了完整的 API。

表 5.1：`System.Logger` API

05tab01

### 5.3.4 日志配置

现在让我们转向后端。正如前面提到的，平台 API 的默认后端是`java.util.logging`。以下信息特定该后端。

你可以通过编辑配置文件更改后端的各种属性。默认配置文件位于 JDK 中的`conf/logging.properties`。要使用另一个文件，在启动应用程序时设置`java.util.logging.config.file`属性为文件位置：

```
java -Djava.util.logging.config.file=configFile MainClass
```

警告

在`main`中调用`System.setProperty("java.util.logging.config.file", configFile)`是无效的，因为日志管理器在`main`执行之前在 VM 启动期间就已经初始化了。

要更改默认日志级别，编辑配置文件并修改该行：

```
.level=INFO
```

你可以通过添加此类行来指定你自己的记录器的日志级别：

```
com.mycompany.myapp.level=WARNING
```

即在记录器名称后附加`.level`后缀。

警告

由于历史原因，某些级别在平台日志 API 和`java.util.logging`框架中的名称不同。以下是对应关系：

jpg

与包名类似，日志记录器名称具有层次性。事实上，它们比包更具层次性。包和父包之间没有语义关系，但日志记录器的父子共享某些属性。例如，如果你关闭到记录器`"com.mycompany"`的消息，那么子记录器也会被禁用。

正如你在下一节中看到的，日志记录器并没有将消息发送到控制台——那是处理器的工作。处理器也有级别。为了在控制台上看到`DEBUG/FINE`消息，你还需要设置：

```
java.util.logging.ConsoleHandler.level=FINE
```

警告

日志管理器配置中的设置不是系统属性。使用`-Dcom.mycompany.myapp.level=FINE`启动程序对日志记录器没有任何影响。

还可以通过使用`jconsole`程序在运行中的程序更改日志级别。详细信息，请参阅`www.oracle.com/technetwork/articles/java/jconsole-1564139.html#LoggingControl`。

### 5.3.5. 日志处理器 (Log Handlers)

在默认配置中，日志记录器（loggers）将记录发送到`ConsoleHandler`，将其打印到`System.err`流中。具体而言，日志记录器将记录发送给父处理器，而最终祖先（名称为`""`）拥有一个`ConsoleHandler`。

与日志记录器一样，处理器也有日志级别。要使一条记录被记录，其日志级别必须高于日志记录器和处理器的阈值。日志管理器配置文件设置默认控制台处理器的日志级别为：

```
java.util.logging.ConsoleHandler.level=INFO
```

要记录级别为`FINE`的记录，请在配置中更改默认日志记录器级别和处理器级别。

要将日志记录发送到其他地方，请添加另一个处理器。日志 API 为此目的提供了两个处理器：`FileHandler`和`SocketHandler`。`SocketHandler`将记录发送到指定的主机和端口。更有趣的是`FileHandler`，它将记录收集在一个文件中。

你可以简单地将记录发送到默认文件处理器，如下所示：

```
var handler = new FileHandler();
logger.addHandler(handler);
```

记录被发送到用户主目录下的`java*n.log`文件，其中`n`是一个使文件保持唯一的数字。默认情况下，记录以 XML 格式格式化。一个典型的日志记录形式如下：

```
<record>
    <date>2014-08-04T09:53:34</date>
    <millis>1407146014072</millis>
    <sequence>1</sequence>
    <logger>com.mycompany.myapp</logger>
    <level>INFO</level>
    <class>com.horstmann.corejava.Employee</class>
    <method>read</method>
    <thread>10</thread>
    <message>Opening file staff.txt</message>
</record>
```

你可以通过在日志管理器配置中设置各种参数，或使用以下构造函数之一来修改文件处理器的默认行为：

```
FileHandler(String pattern)
FileHandler(String pattern, boolean append)
FileHandler(String pattern, int limit, int count)
FileHandler(String pattern, int limit, int count, boolean append)
```

构造参数的含义请参见表 5.2。你可能不想使用默认的日志文件名。请使用如`%h/ myapp.log`的模式（模式变量的解释参见表 5.3）。

如果多个应用程序（或同一应用程序的多个副本）使用同一个日志文件，你应该开启`append`标志。或者，在文件名模式中使用`%u`，以便每个应用程序都创建一个唯一的日志副本。

开启文件轮转（file rotation）也是一个好主意。日志文件以循环序列保存，例如`myapp.log.0`、`myapp.log.1`、`myapp.log.2`等。当文件超过大小限制时，旧的日志会被删除，其他文件会被重命名，并创建一个生成号为`0`的新文件。

表 5.2：文件处理器配置参数

![images](img/05tab02.jpg)

表 5.3：日志文件模式变量

![images](img/05tab03.jpg)

### 5.3.6. 过滤器和格式化器 (Filters and Formatters)

除了按日志级别过滤外，每个处理器还可以有一个实现`Filter`接口的过滤器，该接口是一个具有方法的函数接口：

```
boolean isLoggable(LogRecord record)
```

要向处理器安装过滤器，请在日志配置中添加如下条目：

```
java.util.logging.ConsoleHandler.filter=com.mycompany.myapp.MyFilter
```

`ConsoleHandler`和`FileHandler`类以文本和 XML 格式输出日志记录。然而，你也可以定义自己的格式。扩展`java.util.logging.Formatter`类并重写方法：

```
String format(LogRecord record)
```

以你喜欢的任何方式格式化记录并返回生成的字符串。在你的`format`方法中，可以通过调用表 5.4 中的任意方法来获取有关`LogRecord`的信息。

在你的`format`方法中，你可能想要调用方法：

```
String formatMessage(LogRecord record)
```

该方法格式化记录的消息部分，在资源包中查找消息键并替换消息格式参数。

许多文件格式（如 XML）需要围绕格式化记录的头部和尾部。为此，重写方法：

```
String getHead(Handler h)
String getTail(Handler h)
```

最后，在日志配置中设置格式化器：

```
java.util.logging.FileHandler.formatter=com.mycompany.myapp.MyFormatter
```

表 5.4：`LogRecord` Getter

![images](img/05tab04.jpg)

### 练习

1. 编写一个方法`public ArrayList<Double> readValues(String filename) throws ...`，读取一个包含浮点数的文件。如果无法打开文件或某些输入不是浮点数，则抛出相应的异常。

2. 编写一个方法，读取一个包含浮点数的文件。如果无法打开文件或某些输入不是浮点数，则抛出相应的异常。

3. 编写一个方法`public double sumOf(String filename) throws ...`，读取一个包含浮点数的文件。如果无法打开文件或某些输入不是浮点数，则抛出相应的异常。

4. 编写一个方法`public double sumOf(String filename) throws ...`，读取一个包含浮点数的文件。如果无法打开文件或某些输入不是浮点数，则抛出相应的异常。

5. 编写一个方法`public double sumOf(String filename) throws ...`，读取一个包含浮点数的文件。如果无法打开文件或某些输入不是浮点数，则抛出相应的异常。

6. 编写一个方法`public double sumOf(String filename) throws ...`，读取一个包含浮点数的文件。如果无法打开文件或某些输入不是浮点数，则抛出相应的异常。

10. `Scanner`和`PrintWriter`类的方法不会抛出检查异常（checked exceptions），以便让初学者更容易使用。你如何发现在读取或写入过程中是否发生了错误？注意，构造函数*可以*抛出检查异常。这为什么违背了让类对初学者更容易使用的目标？

11. 编写一个递归的`factorial`方法，在返回值之前打印所有的栈帧（stack frames）。构造（但不抛出）任意类型的异常对象并获取其堆栈轨迹，如第 5.1.8 节所示。

12. 比较`Objects.requireNonNull(obj)`和`assert obj != null`的用法。为每者提供一个有说力的使用场景。

13. 编写一个方法`int min(int[] values)`，在返回最小值之前，断言它确实小于等于数组中的所有值。使用私有辅助方法，或者，如果你已经读过第 8 章，则使用`Stream.allMatch`。在一个大数组上反复调用该方法，并分别在启用断言、禁用和移除断言的情况下测量运行时间。

14. 实现并测试一个日志记录过滤器，过滤掉包含 sex、drugs 和 C++ 等坏词的日志记录。

15. 实现并测试一个日志记录格式化器，用于生成一个 JSON 文件。

## 6. 泛型编程

你经常需要实现可以处理多种类型的类和方法。例如，`ArrayList<T>`存储任意类`T`的元素。我们说`ArrayList`类是*泛型的*（generic），而`T`是一个*类型参数*。基本思想非常简单且极其有用。本章的前两节涵盖了简单部分。



在任何带有泛型类型的编程语言中，当限制或更改类型参数时，细节就会变得复杂。例如，假设你想对元素进行排序。那么你必须指定`T`提供排序。此外，如果类型参数发生变化，这对泛型类型意味着什么？例如，`ArrayList<String>`与一个期望`ArrayList<Object>`的方法之间应该是什么关系？第 6.3 节和第 6.4 节将为你展示 Java 如何处理这些问题。

在 Java 中，泛型编程比本应该复杂的复杂，因为泛型是在 Java 出现一段时间后添加的，并且它们的设计是为了向后兼容的。因此，存在许多不幸的限制，其中一些影响着每个 Java 程序员。另一些只对泛型类的实现者感兴趣。细节请见第 6.5 节和第 6.6 节。最后一节涵盖了泛型和反射，如果你在自己的程序中未使用反射，可以安全地跳过它。

本章的要点是：

1. 泛型类是一个有一个或多个类型参数的类。
2. 泛型方法是一个带有类型参数的方法。
3. 你可以要求类型参数是一个或多个类型的子类。
4. 泛型类型是不变性的：当`S`是`T`的子类时，`G<S>`和`G<T>`之间没有关系。
5. 通过使用通配符`G<? extends T>`或`G<? super T>`，你可以指定一个方法可以接受泛型类型`G`的`T`的子类或超类的实例化。
6. 泛型类和方法在编译时，类型参数会被擦除。
7. 擦除对泛型类型有许多限制。特别是，你不能实例化泛型类或数组，不能强制转换为泛型类型，不能抛出泛型类型的对象。
8. `Class<T>`类是泛型的，这很有用，因为`cast`等方法被声明产生类型为`T`的值。
9. 尽管泛型类和方法在虚拟机中被擦除，但你可以在运行时发现它们是如何定义的。

## 6.1. 泛型类

*泛型类*是一个有一个或多个*类型参数*的类。作为一个例子，考虑这个用于存储键/值对的类：

```java
public class Entry<K, V> {

    private K key;

    private V value;

    public Entry(K key, V value) {

        this.key = key;

        this.value = value;

    }

    public K getKey() { return key; }

    public V getValue() { return value; }

}
```

你可以看到，类型参数`K`和`V`被指定在类名后的尖括号内。在类成员的定义中，它们被用作实例变量、方法参数和返回值的类型。

你通过为类型变量替换类型来*实例化*（instantiate）泛型类。例如，`Entry<String, Integer>`是普通的类，拥有方法`String getKey()`和`Integer getValue()`。

### 注意

类型参数不能用基本类型实例化。例如，在 Java 中`Entry<String, int>`是无效的。

当你*构造*（construct）泛型类的对象时，可以从构造函数中省略类型参数。例如：

```java
Entry<String, Integer> entry = new Entry<>("Fred", 42);

// 等同于 new Entry<String, Integer>("Fred", 42)
```

注意，在构造参数之前你仍然提供了一对空尖括号。有些人将这对空括号称为*菱形*（diamond）。当你使用钻石语法时，类型参数会被推断。

## 6.2. 泛型方法

就像泛型类是带有类型参数的类，*泛型方法*是带有类型参数的方法。泛型方法可以是普通类或泛型类的方法。这里有一个非泛型类的泛型方法示例：

```java
public class Arrays {

    public static <T> void swap(T[] array, int i, int j) {

        T temp = array[i];

        array[i] = array[j];

        array[j] = temp;

    }

}
```

这个`swap`方法可以用于任意数组，只要数组元素不是基本类型。

```java
String[] friends = ...;

Arrays.swap(friends, 1
```

在声明泛型方法时，类型参数放在修饰符（如`public`和`static`）之后，返回类型之前：

```java
public static <T> void swap(T[] array, int i, int j)
```

在调用泛型方法时，不需要指定类型参数。它是根据方法参数和返回类型推断出来的。例如，在调用`Arrays.swap(friends, 0, 1)`时，`friends`的类型是`String[]`，编译器可以推断出`T`应该是`String`。

如果你喜欢，可以在方法名之前显式提供类型，如下：

```java
Arrays.<String>swap(friends, 0, 1);
```

你可能想这样做的一个原因是在出现问题时获得更好的错误信息——参见练习 5。

## 6.3. 类型边界

有时，泛型类或方法的类型参数需要满足某些要求。你可以指定*类型边界*（type bound），要求该类型扩展某些类或实现某些接口。

例如，假设你有一个实现了`AutoCloseable`接口的对象的`ArrayList`，你想关闭它们所有：

```java
public static <T extends AutoCloseable> void closeAll(ArrayList<T> elems)

        throws Exception {

    for (T elem : elems) elem.close();

}
```

类型边界`extends AutoCloseable`确保了元素类型是`AutoCloseable`的子类型。因此，调用`elem.close()`是有效的。你可以向此方法传递一个`ArrayList<PrintStream>`，但不能传递`ArrayList<String>`。请注意，类型边界中的`extends`关键字实际上意味着“子类型”——Java 的设计者只是使用了现有的`extends`关键字，而不是发明另一个关键字或符号。

练习 14 提供了该方法的一个更有趣的变体。

### 注意

在这个例中中，我们需要类型边界，因为参数的类型是`ArrayList`。如果方法接受的是数组，你就不需要泛型方法。你可以直接使用普通方法：

```java
public static void closeAll(AutoCloseable[] elems) throws Exception
```

这之所以可行，是因为像`PrintStream[]`这样的数组类型是`AutoCloseable[]`的子类型。然而，正如你在下一节中看到的，`ArrayList<PrintStream>`*并不是*`ArrayList<AutoCloseable>`的子类型。使用边界类型参数可以解决这个问题。

类型参数可以有多个边界，例如：

```java
T extends Runnable & AutoCloseable
```

这种语法与捕获多个异常的语法相似，区别在于类型之间是用“与”（and）运算符组合的，而多个异常之间是用“或”（or）运算符组合的。

你可以根据需要拥有任意数量的接口边界，但边界中最多只能有一个类。如果你有一个类作为边界，它必须是边界列表中的第一个。

## 6.4. 类型变体与通配符

假设你需要实现一个方法来处理一组是`Employee`类子类的对象数组。你只需声明参数类型为`Employee[]`即可：

```java
public static void process(Employee[] staff) { ... }
```

如果`Manager`是`Employee`的子类，你可以向该方法传递一个`Manager[]`数组，因为`Manager[]`是`Employee[]`的子类型。这种行为被称为*协变*（covariance）。数组的变体方式与元素类型的方式相同。

现在，假设你想处理的是一个数组列表（array list）。但是存在一个问题：类型`ArrayList<Manager>`*并不是*`ArrayList<Employee>`的子类型。

这种限制是有原因的。如果允许将`ArrayList<Manager>`赋值给类型为`ArrayList<Employee>`的变量，你可能会通过存储非经理类员工来破坏数组列表：

```java
ArrayList<Manager> bosses = new ArrayList<>();

ArrayList<Employee> empls = bosses; // 不合法，但假设可以...

empls.add(new Employee(...)); // 在 bosses 中加入了一个非经理员工！
```

由于不允许从`ArrayList<Manager>`转换为`ArrayList<Employee>`，因此这种错误不会发生。

### 注意

你是否可以在数组上生成相同的错误（即数组允许从`Manager[]`到`Employee[]`的转换）？当然可以，正如你在第 4 章中所示。Java 数组是协变的，这虽然方便但不安全。当你向`Manager[]`数组中存储一个普通的`Employee`时，会抛出`ArrayStoreException`。相比之下，Java 中所有的泛型类型都是*不变的*（invariant）。

在 Java 中，你使用*通配符*（wildcards）来指定方法的参数和返回类型允许如何变化。这种机制有时被称为*使用点变体*（use-site variance）。你将在后续章节中看到细节。

### 6.4.1. 子类型通配符

在许多情况下，在不同的数组列表之间转换是完全安全的。假设一个方法永远不会写入数组列表，因此它不会破坏其参数。使用通配符来表达这一事实：

```java
public static void printNames(ArrayList<? extends Employee> staff) {

    for (int i = 0; i < staff.size(); i++) {

        Employee e = staff.get(i);

        System.out.println(e.getName());

    }

}
```

通配符类型`? extends Employee`表示`Employee`的某个未知子类型。你可以使用`ArrayList<Employee>`或子类类型的数组列表（例如`ArrayList<Manager>`）来调用此方法。

类`ArrayList<? extends Employee>`的`get`方法返回类型为`? extends Employee`。语句：

```java
Employee e = staff.get(i);
```

是完全合法的。无论`?`代表什么类型，它都是`Employee`的子类型，且`staff.get(i)`的结果可以赋值给`Employee`变量`e`。（在这个例子中，我没有使用增强型 for 循环，以便准确展示元素是如何从数组列表中获取的。）

如果你尝试向`ArrayList<? extends Employee>`存储一个元素会发生什么？那行不通。考虑以下调用：

```java
staff.add(x);
```

`add`方法的参数类型为`? extends Employee`，并且*没有对象*可以传递给此方法。如果你传递了例如一个`Manager`对象，编译器将拒绝。毕竟，`?`可能指向*任何*子类，也许`Janitor`（清洁工），而你不能向`ArrayList<Janitor>`中添加`Manager`。

### 注意

当然，你可以传递`null`，但那不是一个对象。

总结，你可以从`? extends Employee`转换为`Employee`，但你永远无法将任何转换为`? extends Employee`。这解释了为什么你可以从`ArrayList<? extends Employee>`读取内容，但不能向其写入。

### 6.4.2. 上类型通配符

通配符类型`? extends Employee`表示`Employee`的某个未知子类型。相反，通配符类型`? super Employee`表示`Employee`的上类型。这些通配符作为函数对象的参数时通常非常有用。这里有一个典型的例子。

```java
public interface Predicate<T> {

    boolean test(T arg);

}
```

此方法打印所有具有给定属性的员工名称：

```java
public static void printAll(Employee[] staff, Predicate<Employee> filter) {

    for (Employee e : staff)

        if (filter.test(e))

            System.out.println(e.getName());

}
```

你可以使用类型为`Predicate<Employee>`的对象调用此方法。由于这是一个函数式接口，你也可以传递 lambda 表达式：

```java
printAll(employees, e -> e.getSalary() > 100000);
```

现在假设你想改用`Predicate<Object>`，例如：

```java
Predicate<Object> evenLength = e -> e.toString().length() % 2 == 0;

printAll(employees, evenLength);
```

这不应该没问题。毕竟，每个`Employee`都是拥有`toString`方法的`Object`。然而，像所有泛型类型一样，`Predicate`接口是不变的，`Predicate<Employee>`和`Predicate<Object>`之间没有关系。

解决办法是允许任何`Predicate<? super Employee>`：

```java
public static void printAll(Employee[] staff, Predicate<? super Employee> filter) {

    for (Employee e : staff)

        if (filter.test(e))

            System.out.println(e.getName()); }
```

仔细观察调用`filter.test(e)`。由于`test`的参数类型是`Employee`的上类型，因此传递`Employee`对象是安全的。

这种情况是非常典型的。函数在它们的参数类型上是自然的*逆变的*（contravariant）。例如，当期望一个可以处理员工的函数时，给出一个处理任意对象的函数是可以的。

通常当你指定泛型函数接口作为方法参数时，你应该使用`super`通配符。

### 注意

有些程序员喜欢通配符的“PECS”记忆法：生产者`extends`，消费者`super`。从中读取值的`ArrayList`是生产者，所以使用`extends`通配符。向其提供测试值的`Predicate`是消费者，因此使用`super`。

### 6.4.3. 带有类型变量的通配符

考虑前节方法的泛化，它用于打印满足条件的任意元素：

```java
public <T> void printAll(T[] elements, Predicate<T> filter) {

    for (T e : elements)

        if (filter.test(e))

            System.out.println(e.toString());

}
```

这是一个适用于任何类型数组的通用方法。类型参数是传入的数组的类型。然而，它存在你在前一节中看到的局限性。`Predicate`的类型参数必须与方法的类型参数完全匹配。

解决方案与你之前看到的相同——但这次通配符的边界是一个类型变量：

```java
public static <T> void printAll(T[] elements, Predicate<? super T> filter)
```

该方法接收一个用于类型为`T`或`T`的任何父类的元素的过滤器。

这里是另一个例子。`Collection<E>`接口（你将在下一章中详细介绍）描述了一个包含类型为`E`的元素的集合。它有一个方法：

```java
public boolean addAll(Collection<? extends E> c)
```

你可以从另一个集合中添加所有元素，只要该集合的元素类型也是`E`或其某个子类。通过这个方法，你可以将一个经理的集合添加到一个员工的集合中，但反之则不行。

为了看到类型声明可以变得复杂，请考虑`Collections.sort`方法的定义：

```java
public static <T extends Comparable<? super T>> void sort(List<T> list)
```

`List`接口（将在下一章详细介绍）描述了一个元素序列，例如链表或`ArrayList`。`sort`方法愿意对任何`List<T>`进行排序，只要`T`是`Comparable`的子类。但`Comparable`接口再次是泛型的：

```java
public interface Comparable<T> {

    int compareTo(T other); }
```

它的类型参数指定了`compareTo`方法的参数类型。因此，`Collections.sort`似乎可以被声明为



`public static <T extends Comparable<T>> void sort(List<T> list)`

但那样限制太严格了。假设`Employee`类实现了`Comparable<Employee>`，通过薪水比较员工。假设`Manager`类扩展了`Employee`。注意它实现的是`Comparable<Employee>`，*不是*`Comparable<Manager>`。因此，`Manager`*不是*`Comparable<Manager>`的子类，但它是`Comparable<? super Manager>`的子类。

#### Note

在某些编程语言（如 C# 和 Scala）中，你可以将类型参数声明为协变或逆变。例如，通过将`Comparable`的类型参数声明为逆变，就不需要为每个`Comparable`参数使用通配符。这种“声明处变性”非常方便，但它没有 Java 通配符的“使用处变性”那么强大。

#### 6.4.4 无界通配符

对于只执行非常通用操作的情况，可以使用无界通配符。例如，这里有一个检查`ArrayList`是否包含任何`null`元素的方法：

```
public static boolean hasNulls(ArrayList<?> elements) {

    for (Object e : elements) {

        if (e == null) return true;

    }

    return false;

}
```

由于`ArrayList`的类型参数并不重要，使用`ArrayList<?>`是意义的。同样可以将`hasNulls`变成一个泛型方法：

```
public static <T> boolean hasNulls(ArrayList<T> elements)
```

但通配符易于理解，所以这是首选方法。

#### 6.4.5 通配符捕获

让我们尝试使用通配符定义一个`swap`方法：

```java
public static void swap(ArrayList<?> elements, int i, int j) {

    ? temp = elements.get(i); // 无法工作

    elements.set(i, elements.get(j));

    elements.set(j, temp);

}
```

这是行通的。你可以将`?`作为类型参数，但不能作为类型。

不过，有一个变通方法。添加这样的辅助方法：

```
public static void swap(ArrayList<?> elements, int i, int j) {

    swapHelper(elements, i, j);

}
```

```
private static <T> void swapHelper(ArrayList<T> elements, int i, int j) {

    T temp = elements.get(i);

    elements.set(i, elements.get(j));

    elements.set(j, temp);

}
```

对`swapHelper`的调用是有效的，是因为有一个被称为*通配符捕获*（wildcard capture）的特殊规则。编译器不知道`?`是什么，但它代表某种类型，所以调用泛型方法是。`swapHelper`的类型参数`T`“捕获”了通配符类型。由于`swapHelper`是泛型方法，而不是参数中带有通配符的方法，它可以利用类型变量`T`来声明变量。

我们得到了什么？API 的用户看到的是一个易于理解的`ArrayList<?>`，而不是泛型方法。

### 6.5 Java 虚拟机中的泛型

当泛型类型和方法被引入 Java 时，Java 设计者希望类的泛型形式能与先前的版本兼容。例如，应该能够将`ArrayList<String>`传递给泛型出现之前接收`ArrayList`类的旧方法（该类收集`Object`类型的元素）。语言设计者决定采用一种在虚拟机中“擦除”类型的实现方法。这在当时非常流行，因为它允许 Java 用户逐渐迁移到使用泛型。正如你可以想象的，为了兼容性而做出的妥协，在迁移完成后很长之后仍然存在。

在本节中，你将看到虚拟机内部发生了什么，下一节将检查（内容）。

##### 6.5.1 类型擦除

当你定义一个泛型类型时，它会被编译为*原始*（raw）类型。例如，`Entry<K, V>`类会变为

```
public class Entry {

    private Object key;

    private Object value;

    public Entry(Object key, Object value) {

        this.key = key;

        this.value = value;

    }

    public Object getKey() { return key; }

    public Object getValue() { return value; }

}
```

每个`K`和`V`都被替换为`Object`。如果类型变量有边界，它会被替换为第一个边界。假设我们声明`Entry`类为

```
public class Entry<K extends Comparable<? super K> & Serializable,

                   V extends Serializable>
```

那么它会被擦除为一个类：

```
public class Entry {

    private Comparable key;

    private Serializable value;

    ...
}
```

##### 6.5.2 强制转换插入

类型擦除听起来有些危险，但实际上是非常安全的。假设例如你使用了一个`Entry<String, Integer>`对象。当你构造该对象时，必须提供一个`String`类型的键和一个`Integer`或可转换为`Integer`的值。否则，你的程序甚至无法编译。因此，你可以保证`getKey`方法返回`String`。

然而，假设你的程序带有“未检查”警告通过，可能是因为你使用了强制转换或混合了泛型和原始`Entry`类型。那么，`Entry<String, Integer>`可能具有不同类型的键。

因此，在运行时也有必要进行安全检查。每当从擦除类型的表达式读取内容时，编译器都会插入强制转换。考虑例如

```
Entry<String, Integer> entry = ...;

String key = entry.getKey();
```

由于擦后的`getKey`方法返回`Object`，编译器生成的代码等于

```
String key = (String) entry.getKey();
```

##### 6.5.3 桥方法

在前面的节中，你已经了解了擦除的基本原理。它是简单且安全的。嗯，几乎简单。在擦除方法参数和返回值类型时，有时需要编译器合成*桥方法*（bridge methods）。这是一种实现细节，除非你想知道为什么这种方法会出现在堆栈跟踪中，或者你想了解 Java 泛型某些更晦涩的限制的解释（参见第 6.6.6 节）。

考虑这个例子：

```java
public class WordList extends ArrayList<String> {

    public boolean add(String e) {
        return isBadWord(e) ? false : super.add(e);
    }

    ...
}
```

现在考虑这段代码片段：

```
WordList words = ...;

ArrayList<String> strings = words; // OK—转换为父类

strings.add("C++");
```

最后一次方法调用触发了`ArrayList`类中（擦除后的）`add(Object)`方法。

人们会合理地预期动态方法查找在这种情况下生效，这样在`WordList`对象上调用`add`时，调用的是`WordList`的`add`方法，而不是`ArrayList`的`add`方法。

为了实现这一点，编译器在`WordList`类中合成了一个桥方法（bridge method）：

```java
public boolean add(Object e) {
    return add((String) e);
}
```

在调用`strings.add("C++")`时，调用了`add(Object)`方法，它又调用了`WordList`类的`add(String)`方法。

当返回类型发生变化时，桥方法也可以被调用。考虑这个方法：

```java
public class WordList extends ArrayList<String> {

    public String get(int i) {
        return super.get(i).toLowerCase();
    }

    ...
}
```

在`WordList`类中，有两个`get`方法：

```
String get(int) // 定义在 WordList 中
Object get(int) // 重写了 ArrayList 中定义的方法
```

第二个方法是由编译器合成的，它调用第一个方法。这同样是为了让动态方法查找生效。

这些方法具有相同的参数类型但不同的返回类型。在 Java 语言中，你无法实现这样一对方法。但在虚拟机中，方法是通过名称、参数类型和返回类型来指定的，这允许编译器生成这对方法。

### 注意

桥方法不仅用于泛型类型。它们还被用于实现协变返回类型（covariant return types）。例如，在第 4 章中，你看到了如何声明一个具有适当返回类型的`clone`方法：

```java
public class Employee implements Cloneable {
    public Employee clone() throws CloneNotSupportedException { ... }
}
```

在这种情况下，`Employee`类有两个`clone`方法：

```
Employee clone() // 上文定义
Object clone() // 合成的桥方法
```

桥方法再次为了让动态方法查找生效而生成，它调用了第一个方法。

## 6.6. 泛型的限制

在 Java 中使用泛型类型和方法时有若干限制——有些仅仅是令人惊讶，另一些则确实不方便。它们大部分都是类型擦除的结果。接下来的章节将向你展示实践中最可能遇到的那些限制。

#### 6.6.1. 不支持基本类型参数

类型参数永远不能是基本类型。例如，你不能构造一个`ArrayList<int>`。正如你所见，在虚拟机中只有一种类型，即存储`Object`类型元素的原始`ArrayList`。`int`不是一个对象。

当泛型首次引入时，这并不被认为是一个大问题。毕竟，人们可以构造一个`ArrayList<Integer>`并依赖自动装箱。然而，随着泛型使用得广泛，痛苦正在增加。现在存在大量的函数式接口，如`IntFunction`、`LongFunction`、`DoubleFunction`、`ToIntFunction`、`ToLongFunction`、`ToDoubleFunction`——这只处理了一元函数和八种基本类型中的三种。

#### 6.6.2. 在运行时，所有类型都是原始类型

在虚拟机中，只有原始类型。例如，你不能在运行时查询`ArrayList`是否包含`String`对象。像这样的条件：

```
if (a instanceof ArrayList<String>)
```

是一个编译时错误，因为这种检查永远无法执行。

对泛型类型的实例进行强制转换同样无效，但它是合法的。

```java
Object result = ...;

ArrayList<String> list = (ArrayList<String>) result;

// 警告—这只检查 result 是否为原始 ArrayList
```

这种强制转换是被允许的，因为有时没有办法避免它。如果`result`是一个非常通用过程的结果（例如通过反射调用方法，参见第 4 章），且编译器未知其确切类型，则程序员必须使用强制转换。仅转换为`ArrayList`或`ArrayList<?>`是不够的。

为了让警告消失，可以像这样对变量进行注解：

```java
@SuppressWarnings("unchecked") ArrayList<String> list = (ArrayList<String>) result;
```

### 注意

滥用`@SuppressWarnings`注解可能会导致*堆污染*（heap pollution）——即本应属于特定泛型类型实例但实际上属于另一个实例的对象。例如，你可以将一个`ArrayList<Employee>`赋值给一个`ArrayList<String>`引用。后果是当获取错误类型的元素时会抛出`ClassCastException`。

### 提示

堆污染的问题在于，报告的运行时错误远离问题的根源——即插入错误的元素。如果你需要调试此类问题，可以使用“检查视图”（checked view）。当你构造（例如）一个`ArrayList<String>`时，改用：

```java
List<String> strings = Collections.checkedList(new ArrayList<>(), String.class);
```

该视图监控向列表的所有插入操作，并在添加错误类型时抛出异常。通常，允许调用者提供任何长度的数组。如果提供的数组太短，方法将使用反射创建一个。

#### 6.6.3. 你不能实例化类型变量

你不能在`new T`或`new T[]`等表达式中使用类型变量。这种尝试不可行：

```java
public static <T> T[] repeat(int n, T obj) {
    T[] result = new T[n]; // 错误—无法构造数组
    for (int i = 0; i < n; i++) result[i] = obj;
    return result;
}
```

要解决这个问题，让调用者通过方法引用提供数组构造函数：

```
String[] greetings = Arrays.repeat(10, "Hi", String[]::new);
```

该方法的实现：

```java
public static <T> T[] repeat(int n, T obj, IntFunction<T[]> constr) {
    T[] result = constr.apply(n);
    for (int i = 0; i < n; i++) result[i] = obj;
    return result;
}
```

或者，你可以要求用户提供类对象并使用反射。

```java
public static <T> T[] repeat(int n, T obj, Class<T> cl) {
    @SuppressWarnings("unchecked") T[] result = (T[]) java.lang.reflect.Array.newInstance(cl, n);
    for (int i = 0; i < n; i++) result[i] = obj;
    return result;
}
```

该方法的调用方式如下：

```
String[] greetings = Arrays.repeat(10, "Hi", String.class);
```

另一种方案是让调用者分配数组。

```java
public static <T> T[] repeat(int n, T obj, T[] array) {
    T[] result;
    if (array.length >= n)
        result = array;
    else {
        @SuppressWarnings("unchecked") T[] newArray = (T[]) java.lang.reflect.Array.newInstance(
                array.getClass().getComponentType(), n);
        result = newArray;
    }
    for (int i = 0; i < n; i++) result[i] = obj;
    return result;
}
```

你`can`使用类型变量来实例化一个`ArrayList`。例如，以下代码完全合法的：

```java
public static <T> ArrayList<T> repeat(int n, T obj) {
    var result = new ArrayList<T>(); // OK

    for (int i = 0; i < n; i++) result.add(obj);

    return result;
}
```

这比你刚刚看到的变通方法要简单得多，当你没有充分的理由去创建一个数组时，我推荐使用这种方法。

#### Note

如果泛型类需要一个作为实现私有部分的泛型数组，你只需要构造一个`Object[]`数组即可。这正是`ArrayList`类所做的：



```java
public class ArrayList<E> {
    private Object[] elementData;

    public E get(int index) {
        return (E) elementData[index];
    }

    ...

}
```

#### 6.6.4. 你不能构造参数化类型的数组

假设你想创建一个`Entry`对象的数组：

```java
var entries = new Entry<String, Integer>[100];
// Error—无法构造带有泛型组件类型的数组
```

这是一个语法错误。这种构造是被禁止的，因为在类型擦除后，该数组构造函数会创建一个原始（raw）`Entry`数组。这将导致你可能添加任何类型的`Entry`对象（例如`Entry<Employee, Manager>`）而不会抛出`ArrayStoreException`。

注意，*类型*`Entry<String, Integer>[]`是完全合法的。你可以声明一个该类型的变量。如果你真的想初始化它，可以这样做：

```java
@SuppressWarnings("unchecked") Entry<String, Integer>[] entries
    = (Entry<String, Integer>[]) new Entry<?, ?>[100];
```

但使用 array list 会更简单：

```java
var entries = new ArrayList<Entry<String, Integer>>(100);
```

回想可变参数（varargs）本质上是伪装的数组。如果这样一个参数是泛型的，你就可以绕过对泛型数组创建的限制。考虑这个方法：

```java
public static <T> ArrayList<T> asList(T... elements) {
    var result = new ArrayList<T>();
    for (T e : elements) result.add(e);
    return result;
}
```

现在考虑这个调用：

```java
Entry<String, Integer> entry1 = ...;
Entry<String, Integer> entry2 = ...;
ArrayList<Entry<String, Integer>> entries = Lists.asList(entry1, entry2);
```

`T`的推断类型是泛型类型`Entry<String, Integer>`，因此`elements`是类型为`Entry<String, Integer>`的数组。这正是你无法自己完成的数组创建方式！

在这种情况下，编译器报告的是警告而不是错误。如果你的方法只从参数数组中读取元素，则应该使用`@SafeVarargs`注解来抑制警告：

```java
@SafeVarargs public static <T> ArrayList<T> asList(T... elements)
```

该注解可以应用于`static`、`final`或`private`方法，或者构造函数。任何其他方法都可能被重写，因此不符合该注解条件。

### 6.6.5. 类类型变量在静态上下文中无效

考虑一个带有类型变量的泛型类，例如`Entry<K, V>`。你不能在静态变量或方法中使用类型变量`K`和`V`。例如，以下代码不起作用：

```java
public class Entry<K, V> {
    private static V defaultValue;
    // Error—静态上下文中的 V

    public static void setDefault(V value) { defaultValue = value; }
    // Error—静态上下文中的 V

    ...

}
```

归根到底，类型擦除意味着在擦除后的`Entry`类中只有一个这样的变量或方法，而不是为每个`K`和`V`都对应一个。

### 6.6.6. 方法在擦除后可能发生冲突

你不能声明在擦除后会导致冲突的方法。例如，以下代码将是一个错误：

```java
public interface Ordered<T> extends Comparable<T> {
    public default boolean equals(T value) {
        // Error—擦除与 Object.equals 冲突
        return compareTo(value) == 0;
    }

    ...
}
```

`equals(T value)`方法擦除为`equals(Object value)`，这与来自`Object`的相同方法发生冲突。

有时候，冲突的原因更为微妙。这里有一个棘手的情况：

```java
public class Employee implements Comparable<Employee> {
    ...
    public int compareTo(Employee other) {
        return name.compareTo(other.name);
    }
}

public class Manager extends Employee implements Comparable<Manager> {
    // Error—不能有两个 Comparable 实例化作为超类
    ...
    public int compareTo(Manager other) {
        return Double.compare(salary, other.salary);
    }
}
```

`Manager`类继承自`Employee`，因此获取了超类`Comparable<Employee>`。自然地，经理们想要根据薪水互相比较，而不是根据姓名。为什么不呢？这里没有擦除。只有两个方法：

```java
public int compareTo(Employee other)
public int compareTo(Manager other)
```

问题在于*桥接方法（bridge methods）冲突*。回想第 6.5.3 节，这两个方法冲突。

### 6.6.7. 异常与泛型

你不能抛出或捕获泛型对象。事实上，你甚至不能形成`Throwable`的子类：

```java
public class <T> extends Exception
// Error—泛型不能是 Throwable 的子类
```

你不能在`catch`子句中使用类型变量：

```java
public static <T extends Throwable> void doWork(Runnable r, Class<T> cl) {
    try {
        r.run();
    } catch (T ex) { // Error—无法捕获类型变量
        cl.getGlobal().log(ex);
    }
}
```

然而，你可以在`throws`声明中使用类型变量：

```java
public static <V, T extends Throwable> V doWork(Callable<V> c) throws T {
    // ...
}
```

#### Note

#### Caution

你可以使用泛型来消除检查异常和运行时异常之间的区别。关键要素在于这对方法：

```java
public class Exceptions {
    @SuppressWarnings("unchecked")
    private static <T extends Throwable>
    void throwAs(Throwable e) throws T {
        throw (T) e; // 强制转换被擦除为 (Throwable) e
    }

    public static <V> doWork(Callable<V> c) {
        try {
            return c.call();
        } catch (Throwable ex) {
            Exceptions.<RuntimeException>throwAs(ex);
            return null;
        }
    }
}
```

现在考虑这个方法：

```java
public static String[] readWords(Path path) {
    return doWork(() -> Files.readString(path).split("\\s+"));
}
```

尽管`Files.readString`在路径未找到时会抛出检查异常，但该异常在`readWords`方法中既没有声明也没有被捕获！

```java
public static <T> ArrayList<T> repeat(int n, Class<T> cl)
        throws ReflectiveOperationException {
    var result = new ArrayList<T>();
    for (int i = 0; i < n; i++)
        result.add(cl.getConstructor().newInstance());
    return result;
}
```

该方法可以编译，因为`cl.getConstructor().newInstance()`返回类型为`T`的结果。

假设你这样调用该方法`repeat(10, Employee.class)`。此时`T`被推断为类型`Employee`，因为`Employee.class`的类型是`Class<Employee>`。因此，返回类型是`ArrayList<Employee>`。

除了`getConstructor`方法外，`Class`类还有几个使用类型参数的方法。它们是：

```java
Class<? super T> getSuperclass()
<U> Class<? extends U> asSubclass(Class<U> clazz)
T cast(Object obj)
Constructor<T> getDeclaredConstructor(Class<?>... parameterTypes)
T[] getEnumConstants()
```

正如你在第 4 章中看到的，在很多情况下你对`Class`对象描述的类一无所知。这时，你可以直接使用通配符类型`Class<?>`。

### 6.7.2. 虚拟机中的泛型类型信息

擦除（Erasure）只影响实例化的类型参数。泛型类和方法的*声明*完整信息在运行时是可用的。

例如，假设调用`obj.getClass()`返回`ArrayList.class`。你无法判断`obj`是作为`ArrayList<String>`还是`ArrayList<Employee>`构建的。但你可以确定`ArrayList`类是一个泛型类，拥有一个没有边界的类型参数`E`。

同样，考虑`Collections`类的方法：

```java
static <T extends Comparable<? super T>> void sort(List<T> list)
```

正如你在第 4 章中看到的，你可以通过以下方式获取相应的`Method`对象：

```java
Method m = Collections.class.getMethod("sort", List.class);
```

通过这个`Method`对象，你可以恢复整个方法的签名。

`java.lang.reflect`包中的`Type`接口代表泛型类型声明。该接口有以下子类型：

1. `Class`类，描述具体类型。
2. `TypeVariable`接口，描述类型变量（例如`T extends Comparable<? super T>`）。
3. `WildcardType`接口，描述通配符（例如`? super T`）。
4. `ParameterizedType`接口，描述泛型类或接口类型（例如`Comparable<? super T>`）。
5. `GenericArrayType`接口，描述泛型数组（例如`T[]`）。

注意，后四个子类型都是接口——虚拟机会实例化实现这些接口的相应类。

类和方法都可以拥有类型变量。从技术上说，构造函数不是方法，它们在反射库中由单独的类表示。它们也可以是泛型的。要确定一个`Class`、`Method`或`Constructor`对象是否来自泛型声明，调用`getTypeParameters`方法。你会得到一个`TypeVariable`实例数组，声明中的每个类型变量对应一个实例；如果声明不是泛型的，则返回长度为 0 的数组。

`TypeVariable<D>`接口是泛型的。类型参数是`Class<T>`、`Method`或`Constructor<T>`，取决于类型变量声明的位置。例如，这里是获取`ArrayList`类类型变量的方法：

```java
TypeVariable<Class<ArrayList>>[] vars = ArrayList.class.getTypeParameters();
String name = vars[0].getName(); // "E"
```

这里是`Collections.sort`方法的类型变量：

```java
Method m = Collections.class.getMethod("sort", List.class);
TypeVariable<Method>[] vars = m.getTypeParameters();
String name = vars[0].getName(); // "T"
```

后者的变量有一个边界，你可以这样处理它：

```java
Type[] bounds = vars[0].getBounds();
if (bounds[0] instanceof ParameterizedType p) { // Comparable<? super T>
    Type[] typeArguments = p.getActualTypeArguments();
    if (typeArguments[0] instanceof WildcardType t) { // ? super T
        Type[] upper = t.getUpperBounds(); // ? extends ... & ...
        Type[] lower = t.getLowerBounds(); // ? super ... & ...
        if (lower.length > 0) {
            String description = lower[0].getTypeName(); // "T"
            ...
        }
    }
}
```

这让你了解了如何分析泛型声明的大致方法。我不会纠结于细节，因为这在实践中并不常见。关键点是，泛型类和方法的声明没有被擦除，你可以通过反射访问它们。

### 练习题

1. 实现一个`Stack<E>`类，用于管理一个类型为`E`的元素数组列表。提供`push`、`pop`和`isEmpty`方法。
2. 重新实现`Stack<E>`类，使用数组来存储元素。如有必要，在`push`方法中扩展数组。提供两种解决方案，一种使用`E[]`数组，另一种使用`Object[]`数组。两种解决方案都应该在无警告的情况下编译。你更倾向于哪一种？为什么？
3. 实现一个`Table<K, V>`类，用于管理`Entry<K, V>`元素的数组列表。提供获取值、存值和删除键的方法。
4. 正如你在第 4 章中看到的，在很多情况下你对`Class`对象描述的类一无所知。这时，你可以直接使用通配符类型`Class<?>`。
5. 在上一个练习中，将`Entry`改为内部类。该类应该是泛型的吗？
6. 考虑以下`swap`变体，可以使用变长参数：

```java
public static <T> T[] swap(int i, int j, T... values) {
    T temp = values[i];
    values[i] = values[j];
    values[j] = temp;
    return values;
}
```

现在看调用：

```java
Double[] result = Arrays.swap(0, 1, 1.5, 3);
```

你得到了什么错误信息？现在调用：

```java
Double[] result = Arrays.<Double>swap(0, 1, 1.5, 3);
```

错误信息改进了吗？如何修复？

7. 实现一个泛型方法，将一个数组列表的所有元素追加到另一个中。其中一个类型参数使用通配符。提供两种等效方案，一种使用`? extends E`，另一种使用`? super E`。
8. 实现类`Pair<E>`存储类型为`E`的元素对。提供访问器来获取第一个和第二个元素。
9. 在工具类`Arrays`中提供一个方法：

```java
public static <E> Pair<E> firstLast(ArrayList<E> a)
```

返回`a`的第一个和最后一个元素的对。提供适当类型参数。
10. 在`Arrays`工具类中提供泛型方法`min`和`max`，返回数组中的最小和最大元素。



11. 继续之前的练习，提供一个`minMax`方法，返回包含最小值和最大值的`Pair`。

12. 实现以下方法，将`elements`中的最小和最大元素存储在`result`列表中：

```java
public static <T> void minmax(List<T> elements,
        Comparator<? super T> comp, List<? super T> result)
```

注意最后一个参数中的通配符——任何`T`的父类型都可以用于结果。

13. 给定之前练习的方法，考虑这个方法：

```java
public static <T> void maxmin(List<T> elements,
        Comparator<? super T> comp, List<? super T> result) {
    minmax(elements, comp, result);
    Lists.swapHelper(result, 0, 1);
}
```

为什么这个方法在没有通配符捕获的情况下无法编译？提示：尝试提供显式类型`Lists.<___>swapHelper(result, 0, 1)`。

14. 实现第 6.3 节`closeAll`方法的改进版本。即使某些元素抛出异常也要关闭所有元素。如果是这样，之后抛出异常。如果多次调用都抛出异常，将它们链在一起。

15. 实现一个方法`map`，它接收一个数组列表和一个`Function<T, R>`对象（参见第 3 章），并返回一个包含将函数应用于给定元素的结果数组列表。

16. `Collection`类中以下方法的擦除（erasure）是什么？

```java
public static <T extends Comparable<? super T>>

    void sort(List<T> list)

public static <T extends Object & Comparable<? super T>>

    T max(Collection<? extends T> coll)
```

17. 定义实现`Comparable<Employee>`的类`Employee`。使用`javap`工具演示是否合成了桥接方法（bridge method）。它是做什么的？

18. 考虑第 6.6.3 节中的方法：

```java
public static <T> T[] repeat(int n, T obj, IntFunction<T[]> constr)
```

调用`Arrays.repeat(10, 42, int[]::new)`将失败。为什么？如何修复它？对于其他原始类型，你需要怎么做？

19. 考虑第 6.6.3 节中的方法：

```java
public static <T> ArrayList<T> repeat(int n, T obj)
```

该方法在构造一个包含`T`值数组的`ArrayList<T>`时没有问题。你可以在不使用`Class`值或构造器引用的情况下，从该数组列表生成`T[]`数组吗？如果不能，为什么？

20. 实现方法：

```java
@SafeVarargs public static final <T> T[] repeat(int n,  T... objs)
```

返回一个包含`n`个给定对象的数组。注意，不需要`Class`值或构造器引用，因为你可以通过反射增加`objs`。

21. 使用`@SafeVarargs`注解编写一个可以构造泛型类型数组的方法。例如：

```java
List<String>[] result = Arrays.<List<String>>construct(10);

// 将 result 设置为大小为 10 的 List<String>[]
```

22. 改进第 6.6.7 节中的方法`public static <V, T extends Throwable> V doWork(Callable<V> c, T ex) throws T`，使得不需要传递可能永远不会使用的异常对象。相反，接受一个异常类的构造器引用。

23. 在第 6.6.7 节末尾的注意事项，使用了`throwAs`辅助方法将`ex`“强制转换”为`RuntimeException`并重新抛出。为什么你不能使用普通的强制转换，即`throw (RuntimeException) ex`？

24. 在类型为`Class<?>`的变量上，可以在不使用转换的情况下调用哪些方法？

25. 写一个方法`public static String genericDeclaration(Method m)`，它返回方法`m`的声明，列出带有边界的类型参数以及方法参数的类型，如果它们是泛型类型，则包含它们的类型参数。

## 7. 集合（Collections）

许多许多数据结构以便程序员高效地存储和检索值。Java API 提供了常用数据结构和算法的实现，以及组织它们的框架。在本章中，你将学习如何处理列表、集合、映射和其他集合。

本章的要点是：

1. `Collection`接口为所有集合提供了通用方法，但由`Map`接口描述的映射除外。
2. 列表（list）是一个顺序集合，每个元素都有一个整数索引。
3. 集合（set）针对高效的包含性测试进行了优化。Java 提供了`HashSet`和`TreeSet`实现。
4. 对于映射（maps），你可以在`HashMap`和`TreeMap`实现之间选择。`LinkedHashMap`保留插入顺序。
5. `Collection`接口和`Collections`类提供了许多有算法：集合操作、搜索、排序、洗牌等。
6. 视图（Views）允许标准集合接口访问存储在别处的数据。

### 7.1 集合框架概述

Java 集合框架提供了常用数据结构的实现。为了便于编写不依赖于数据结构选择的代码，集合框架提供了许多通用接口，如图 7.1 所示。基础接口是`Collection`，其方法在表 7.1 所示。

![images](img/07fig01.jpg)

图 7.1：Java 集合框架中的接口

表 7.1：`Collection<E>`接口的方法

![images](img/07tab01.jpg)

`List`是一个顺序集合：元素具有位置 0、1、2 等。表 7.2 显示了该接口的方法。

表 7.2：`List`接口

![images](img/07tab02.jpg)

`List`接口既由`ArrayList`类（你在全书中都看到了它）也由`LinkedList`类实现。如果你上过数据结构课程，`LinkedList`类是一个顺序列表。`ArrayList`是基于数组的列表。`LinkedList`是双向链表。`ArrayList`在随机访问方面更快，而`LinkedList`在端部插入和删除方面更快。

`List`接口提供了通过索引访问元素。`ArrayList`实现了`RandomAccess`，但`LinkedList`仅实现`List`。

在集合（Set）中，元素不插入到特定位置，不允许重复元素。`HashSet`和`TreeSet`是实现。`SortedSet`允许按排序迭代，`NavigableSet`具有寻找相邻元素的方法。你将在第 7.3 节学习更多关于集合的知识。

`Queue`保留插入顺序，但你只能从尾部插入元素并从头部移除。`Deque`是可以在两端插入队列。

所有集合接口都是泛型的，带有元素的类型参数（`Collection<E>`、`List<E>`等）。`Map<K, V>`接口具有键类型参数`K`和值类型参数`V`。

鼓励在代码中尽可能使用接口。例如，在构造`ArrayList`后，将其存储在`List`类型的变量中：

```java
List<String> words = new ArrayList<>();
```

当你实现处理集合的方法时，使用限制最少的接口作为参数类型。通常，`Collection`、`List`或`Map`即可。

集合框架的一个优势是，在处理常用算法时不需要重复发明。一些基本算法（如`addAll`和`removeIf`）是`Collection`接口的方法。`Collections`工具类包含许多操作各种集合的额外算法。你可以对列表进行排序、洗牌、旋转和反转，找到集合中的最大或最小值或任意元素的位置，并生成没有元素、一个元素或`n`个相同元素的集合。表 7.3 提供了总结。

表 7.3：`Collections`类的有用方法

![images](img/07tab03.jpg) ![images](img/07tab03a.jpg)

### 7.2 迭代器（Iterators）

每个集合都提供了某种顺序遍历其元素的方法。`Collection`的父接口`Iterable<T>`定义了一个方法：

```java
Iterator<T> iterator()
```

产生迭代器，你可以使用它访问所有元素。

```java
Collection<String> coll = ...;

Iterator<String> iter = coll.iterator();

while (iter.hasNext()) {

    String element = iter.next();

    Process element

}
```

在这种情况下，你可以直接使用增强型`for`循环：

```java
for (String element : coll)  {

    Process element

}
```

### 注意事项

对于实现了`Iterable<E>`接口的类的*任意*对象`c`，增强型`for`循环会被翻译为前述的形式。

`Iterator`接口还有一个`remove`方法，它可以删除上一次访问的元素。此循环删除了所有满足条件的元素：

```java
while (iter.hasNext()) {

    String element = iter.next();

    if (element fulfills the condition)

        iter.remove();

}
```

然而，使用`removeIf`方法更简单：

```java
coll.removeIf(e -> e fulfills the condition);
```

### 警告

`remove`方法删除的是迭代器返回的最后一个元素，而不是迭代器当前指向的元素。你不能在没有调用`next`或`previous`的情况下连续调用两次`remove`。

`ListIterator`接口是`Iterator`的子接口，具有在迭代器之前添加元素、将访问过的元素设置为不同值以及向后导航的方法。它主要用于处理链表。

```java
var friends = new LinkedList<String>();

ListIterator<String> iter = friends.listIterator();

iter.add("Fred"); // Fred |

iter.add("Wilma"); // Fred Wilma |

iter.previous(); // Fred | Wilma

iter.set("Barney"); // Fred | Barney
```

### 警告

如果你在用迭代器访问一个正在被修改的数据结构，它可能会失效。如果你继续使用它，无效的迭代器可能会抛出`ConcurrentModificationException`。这是一个典型的示例：

```java
var friends = new LinkedList<String>(List.of("Fred", "Wilma", "Barney"));

for (String name : friends) {

    if (name.length() < 5) friends.remove(name); // Error—concurrent modification

}
```

增强型`for`循环使用迭代器来遍历列表。当列表被修改时，迭代器

### 7.3 集合（Sets）

集合可以高效地测试一个值是否为元素，但它是有代价：它不记住元素添加的顺序。在顺序不重要的情况下，集合非常有用。例如，如果你不允许将一组脏词作为用户名，那么它们的顺序并不重要。你只需要知道提议的用户名是否在集合中。

`Set`接口由`HashSet`和`TreeSet`类实现。在内部，这些类使用了完全不同的实现。如果你上过数据结构课程，你可能知道如何实现哈希表和二叉树——但你可以在不知道它们内部细节的情况下使用这些类。

通常，如果你为元素有一个良好的*哈希函数*，哈希集合会高效一些。`String`或`Path`等库类具有良好的哈希函数。你在第四章中学习了如何为自己的类编写哈希函数。

例如，那个脏词集合可以简单地实现为：

```java
var badWords = new HashSet<String>();

badWords.add("sex");

badWords.add("drugs");

badWords.add("c++");

if (badWords.contains(username.toLowerCase()))

    System.out.println("Please choose a different user name")
```

如果你想按排序顺序遍历集合，则使用`TreeSet`。你可能想这样做的一个原因是向用户展示排序后的选项列表。

集合的元素类型必须实现`Comparable`接口，或者你需要在构造函数中提供一个`Comparator`。

```java
var countries = new TreeSet<String>(); // 按顺序访问已添加的国家

var countries2 = new TreeSet<String>((u, v) ->

    u.equals(v) ? 0

    : u.equals("USA") ? -1

    : v.equals("USA") ? 1
    : u.compareTo(v));

// USA 始终在第一
```

`TreeSet`类实现了`SortedSet`和`NavigableSet`接口，其方法显示在和中。

表 7.4：`SortedSet<E>`方法

![images](img/07tab04.jpg)

表 7.5：`NavigableSet<E>`方法

![images](img/07tab05.jpg)

### 7.4 映射（Maps）

映射存储了键和值之间的关联。调用`put`来添加新的关联，或更改现有键的值：

```java
var counts = new HashMap<String, Integer>();

counts.put("Alice", 1); // 向映射中添加键/值对

counts.put("Alice", 2); // 更新键的值
```

此示例使用了哈希映射，与集合一样，如果你不需要按排序顺序访问键，那么它通常是更好的选择。如果需要，请使用`TreeMap`替代。

以下是获取与某个键关联的值的方法：

```java
int count = counts.get("Alice");
```

如果键不存在，`get`方法返回`null`。在示例中，当对值进行自动拆箱（unboxing）时，这会导致`NullPointerException`。更好的替代方案是：

```java
int count = counts.getOrDefault("Alice", 0);
```

当键不存在时，`getOrDefault`方法返回默认值。在示例中，当值进行自动拆箱时，这会避免`NullPointerException`。更好的替代方案是：

```java
counts.merge("Alice", 1, Integer::sum);
```

当键不存在时，`merge`方法会将新值与现有值合并。`merge`方法简化了这一点：

```java
counts.merge("Alice", 1, Integer::sum);
```

如果键不存在，则返回`0`。表 7.6 总结了映射的操作。

表 7.6：`Map<K, V>`方法

![images](img/07tab06.jpg) ![images](img/07tab06.jpg)

你可以通过这些方法获取映射的键、值和条目的*视图*：

```java
Set<K> keySet()

Set<Map.Entry<K, V>> entrySet()

Collection<V> values()
```

返回的集合不是映射的拷贝，但它们与映射是连接的。如果你从视图移除键或条目，该条目也会从映射中移除。

要遍历映射的所有键和值，可以使用`entrySet`方法：

```java
for (Map.Entry<String, Integer> entry : counts.entrySet()) {

    String k = entry.getKey();

    Integer oldValue = entry.getValue();

    int newValue = ...;

    entry.setValue(newValue);
}
```

`Map.Entry`实例与映射也是连接的。从前面的代码段可以看出，你可以使用`entry`对象更新映射中的值。相反，如果你通过其他方式（例如调用映射的`put`方法），条目也会更新。

如果你想将条目传递给其他方法，应该通过`Map.Entry.copyOf(entry)`将它们从映射中分离。你也可以通过`Map.entry(key, value)`创建未关联的`Map.Entry`实例。这在你需要值对时非常方便。

如果你不需要修改映射，使用`forEach`方法遍历条目更简单：



```java
counts.forEach((k, v) -> {

   Process k, v

});
```

### 警告

如果你在用迭代器访问一个正在被修改的数据结构，它可能会失效。如果你继续使用它，无效的迭代器可能会抛出 `ConcurrentModificationException`。这是一个典型的示例：

```java
var friends = new LinkedList<String>(List.of("Fred", "Wilma", "Barney"));

for (String name : friends) {

    if (name.length() < 5) friends.remove(name); // Error—concurrent modification

}
```

增强型 `for` 循环使用迭代器来遍历列表。当列表被修改时，迭代器

### 7.3. 集合（Sets）

集合可以高效地测试一个值是否为元素，但它是有代价：它不记住元素添加的顺序。在顺序不重要的情况下，集合非常有用。例如，如果你不允许将一组脏词作为用户名，那么它们的顺序并不重要。你只需要知道提议的用户名是否在集合中。

`Set` 接口由 `HashSet` 和 `TreeSet` 类实现。在内部，这些类使用了完全不同的实现。如果你上过数据结构课程，你可能知道如何实现哈希表和二叉树——但你可以在不知道它们内部细节的情况下使用这些类。

通常，如果你为元素有一个良好的哈希函数，哈希集合会高效一些。`String` 或 `Path` 等库类具有良好的哈希函数。你在第四章中学习了如何为自己的类编写哈希函数。

例如，那个脏词集合可以简单地实现为：

```java
var badWords = new HashSet<String>();

badWords.add("sex");

badWords.add("drugs");

badWords.add("c++");

if (badWords.contains(username.toLowerCase()))

    System.out.println("Please choose a different user name")
```

如果你想按排序顺序遍历集合，则使用 `TreeSet`。你可能想这样做的原因是为了向用户展示排序后的选项列表。

集合的元素类型必须实现 `Comparable` 接口，或者你需要在构造函数中提供一个 `Comparator`。

```java
var countries = new TreeSet<String>(); // 按顺序访问已添加的国家

var countries2 = new TreeSet<String>((u, v) ->

    u.equals(v) ? 0

    : u.equals("USA") ? -1

    : v.equals("USA") ? 1
    : u.compareTo(v));

    // USA 始终在第一
```

`TreeSet` 类实现了 `SortedSet` 和 `NavigableSet` 接口，其方法显示在和中。

表 7.4：`SortedSet<E>` 方法

![images](img/07tab04.jpg)

表 7.5：`NavigableSet<E>` 方法

![images](img/07tab05.jpg)

### 7.4. 映射（Maps）

映射存储了键和值之间的关联。调用 `put` 来添加新的关联，或更改现有键的值：

```java
var counts = new HashMap<String, Integer>();

counts.put("Alice", 1); // 向映射中添加键/值对

counts.put("Alice", 2); // 更新键的值
```

此示例使用了哈希映射，与集合一样，如果你不需要按排序顺序访问键，那么它通常是更好的选择。如果需要，请使用 `TreeMap` 替代。

以下是获取与某个键关联的值的方法：

```java
int count = counts.get("Alice");
```

如果键不存在，`get` 方法返回 `null`。在示例中，当对值进行自动拆箱时，这会导致 `NullPointerException`。更好的替代方案是：

```java
int count = counts.getOrDefault("Alice", 0);
```

当键不存在时，`getOrDefault` 方法返回默认值。在示例中，当值进行自动拆箱时，这会避免 `NullPointerException`。更好的替代方案是：

```java
counts.merge("Alice", 1, Integer::sum);
```

当键不存在时，`merge` 方法会将新值与现有值合并。`merge` 方法简化了这一点：

```java
counts.merge("Alice", 1, Integer::sum);
```

如果键不存在，则返回 `0`。表 7.6 总结了映射的操作。

表 7.6：`Map<K, V>` 方法

![images](img/07tab06.jpg)![images](img/07tab06.jpg)

你可以通过这些方法获取映射的键、值和条目的视图：

```java
Set<K> keySet()

Set<Map.Entry<K, V>> entrySet()

Collection<V> values()
```

返回的集合不是映射的拷贝，但它们与映射是连接的。如果你从视图移除键或条目，该条目也会从映射中移除。

要遍历映射的所有键和值，可以使用 `entrySet` 方法：

```java
for (Map.Entry<String, Integer> entry : counts.entrySet()) {

    String k = entry.getKey();

    Integer oldValue = entry.getValue();

    int newValue = ...;

    entry.setValue(newValue);
}
```

`Map.Entry` 实例与映射也是连接的。从前面的代码段可以看出，你可以使用 `entry` 对象更新映射中的值。相反，如果你通过其他方式（例如调用映射的 `put` 方法），条目也会更新。

如果你想将条目传递给其他方法，应该通过 `Map.Entry.copyOf(entry)` 将它们从映射中分离。你也可以通过 `Map.entry(key, value)` 创建未关联的 `Map.Entry` 实例。这在你需要值对时非常方便。

如果你不需要修改映射，使用 `forEach` 方法遍历条目更简单：

```java
counts.forEach((k, v) -> {

   Process k, v

});
```

### 警告

如果你在用迭代器访问一个正在被修改的数据结构，它可能会失效。如果你继续使用它，无效的迭代器可能会抛出 `ConcurrentModificationException`。这是一个典型的示例：

```java
var friends = new LinkedList<String>(List.of("Fred", "Wilma", "Barney"));

for (String name : friends) {

    if (name.length() < 5) friends.remove(name); // Error—concurrent modification

}
```

增强型 `for` 循环使用迭代器来遍历列表。当列表被修改时，迭代器

### 7.5. 其他集合

在接下来的章节中，我简要讨论了一些你可能在实践中非常有用的集合类。

#### 7.5.1. 属性

`Properties` 类实现了一个可以使用纯文本格式轻松保存和加载的 map。这种 map 通常用于存储程序的配置配置项。例如：

```java
var settings = new Properties();

settings.put("width", "200");

settings.put("title", "Hello, World!");

try (OutputStream out = Files.newOutputStream(path)) {
    settings.store(out, "Program Properties");
}
```

结果是下面的文件：

```text
#Program Properties

#Mon Nov 03 20:52:33 CET 2014

width=200

title=Hello, World\!
```

### 注意事项

从 Java 9 开始，属性文件使用 UTF-8 编码。（在此之前，它们使用 ASCII 编码，大于 `'\u007e’` 的字符会被转义为 Unicode 转义字符 `\u*nnnn`。）注释以 `#` 或 `!` 开头。键或值中的换行符写为 `\n`。字符 `\`、`#` 和 `!` 被转义为 `\\`、`\#` 和 `\!`。

要从文件加载属性，请调用：

```java
try (InputStream in = Files.newInputStream(path)) {
    settings.load(in);
}
```

然后使用 `getProperty` 方法获取键对应的值。你可以指定当键不存在时使用的默认值：

```java
String title = settings.getProperty("title", "New Document");
```

### 注意事项

出于历史原因，尽管值始终是字符串，但 `Properties` 类仍然实现了 `Map<Object, Object>`。因此，请勿使用 `get` 方法——它返回的是 `Object` 类型的值。

`System.getProperties` 方法产生一个包含系统属性的 `Properties` 对象。表 7.7 描述了其中最有用的属性。

表 7.7：有用的系统属性

![images](img/07tab07.jpg)

#### 7.5.2. 位集（Bit Sets）

`BitSet` 类存储一个位序列。位集将位打包进 `long` 值的数组中，因此使用位集比使用 `boolean` 数组更高效。位集用于标志位序列或表示非负整数集，其中第 `i` 位为 `1` 则表示 `i` 包含在集合中。

`BitSet` 类提供了方便的方法来获取和设置单个位。这比在 `int` 或 `long` 变量中存储位所需的位运算操作要简单得多。还有一些方法对所有位进行统一操作以实现集合，例如并集和交集。完整列表请参见表 7.8。注意，`BitSet` 类并不是集合类——它没有实现 `Collection<Integer>`。

表 7.8：`BitSet` 类的方法

![images](img/07tab08.jpg)![images](img/07tab08a.jpg)

#### 7.5.3. 枚举集和映射（Enumeration Sets and Maps）

如果你收集枚举值的集合，请使用 `EnumSet` 类而不是 `BitSet`。`EnumSet` 类没有公共构造函数。使用静态工厂方法来构建集合：

```java
enum Weekday { MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY };

Set<Weekday> always = EnumSet.allOf(Weekday.class);

Set<Weekday> never = EnumSet.noneOf(Weekday.class);

Set<Weekday> workday = EnumSet.range(Weekday.MONDAY, Weekday.FRIDAY);

Set<Weekday> mwf = EnumSet.of(Weekday.MONDAY, Weekday.WEDNESDAY, Weekday.FRIDAY);
```

你可以使用 `Set` 接口的方法来操作 `EnumSet`。

`EnumMap` 是一个键属于某个枚举类型的 map。它被实现为值的数组。你在构造函数中指定键的类型：

```java
var personInCharge = new EnumMap<Weekday, String>(Weekday.class);

personInCharge.put(Weekday.MONDAY, "Fred");
```

#### 7.5.4. 栈、队列、双端队列和优先级队列（Stacks, Queues, Deques, and Priority Queues）

栈是一种用于在末端（栈的“顶端”）添加和移除元素的数据结构。队列允许你高效地从一端（“尾部”）添加元素并从另一端（“头部”）移除元素。双端队列（或 deque）支持在两端进行插入和移除。所有这些数据结构都不支持在中间添加元素。

`Queue` 和 `Deque` 接口定义了这些数据结构的方法。Java 集合框架中没有 `Stack` 接口，只有一个 Java 早期的遗留 `Stack` 类，你应该避免使用它。如果你需要栈、队列或双端队列且不担心线程安全，请使用 `ArrayDeque`。

使用栈时使用 `push` 和 `pop` 方法。

```java
var stack = new ArrayDeque<String>();

stack.push("Peter");

stack.push("Paul");

stack.push("Mary");

while (!stack.isEmpty())
    System.out.println(stack.pop());
```

使用队列时使用 `add` 和 `remove` 方法。

```java
Queue<String> queue = new ArrayDeque<>();

queue.add("Peter");

queue.add("Paul");

queue.add("Mary");

while (!queue.isEmpty())
    System.out.println(queue.remove());
```

#### 7.5.5. 弱哈希（Weak Hash Maps）

`WeakHashMap` 类设计用于解决一个有趣的问题：如果一个值的键不再被使用，会发生什么？如果指向键的最后一个引用消失了，就没有方法引用该值对象，因此它应该被垃圾回收器移除。

情况并没有那么简单。垃圾回收器会追踪活对象。只要 map 对象是活的，它中的所有条目都是活的且不会被回收——被其引用的值也不会被回收。

这就是 `WeakHashMap` 类解决的问题。这种数据结构与垃圾回收器协作，当键的唯一引用是哈希表中的引用时，移除该键/值对。

从技术上讲，`WeakHashMap` 使用弱引用（weak references）来持有键。`WeakReference` 对象持有另一个对象的引用——在我们的案例中，是哈希表的键。这类对象会被垃圾回收器以特殊方式处理。如果一个对象仅通过弱引用可达，垃圾回收器将回收该对象并将弱引用放入与 `WeakReference` 对象关联的队列中。每当调用它的方法时，`WeakHashMap` 都会检查其弱引用队列中的新到项并移除相关的条目。

### 7.6. 视图（Views）

集合视图（view）是一个实现了集合接口的轻量级对象，但不存储元素。例如，map 的 `keySet` 和 `values` 方法产生 map 的视图。

在接下来的章节中，你将看到 Java 集合框架提供的一些视图。

#### 7.6.1. 小型集合（Small Collections）

`List`、`Set` 和 `Map` 接口提供了静态方法，用于产生给定元素的集合或列表，以及带有给定键/值对的 map。

例如：

```java
List<String> names = List.of("Peter", "Paul", "Mary");

Set<Integer> numbers = Set.of(2, 3, 5);
```

将产生一个包含三个元素的列表和一个集合。对于 map，按如下方式指定键和值：

```java
Map<String, Integer> scores = Map.of("Peter", 2, "Paul", 3, "Mary", 5);
```

元素、键或值不能为 `null`。

`List` 和 `Set` 接口有 11 个 `of` 方法，分别接受从零到十个参数，以及一个接受变长参数的 `of` 方法。为了提高效率，提供了这些特化实现。

对于 `Map` 接口，无法提供变长参数的版本，因为参数类型在键类型和值类型之间交替。有一个静态方法 `ofEntries`，它可以接受任意数量的 `Map.Entry<K, V>` 对象，你可以使用静态方法 `entry` 来创建这些对象。例如：

```java
import static java.util.Map.*;

...

Map<String, Integer> scores = ofEntries(
    entry("Peter", 2),
    entry("Paul", 3),
    entry("Mary", 5));
```

`of` 和 `ofEntries` 方法产生对象的类，这些类为每个元素都有一个实例变量，或者由数组支持。

这些集合对象是不可修改的（`unmodifiable`）。任何更改其内容的尝试都会导致 `UnsupportedOperationException`。

如果你需要一个可变的集合，可以将不可修改的集合传递给构造函数：

```java
var names = new ArrayList<String>(List.of("Peter", "Paul", "Mary"));
```

### 注意

还有一个静态的 `Arrays.asList` 方法，与 `List.of` 类似。它返回一个可变但不可调整大小的列表。也就是说，你可以对列表调用 `set`，但不能调用 `add` 或 `remove`。

#### 7.6.2. 范围



你可以形成列表的子列表视图。例如：

```java
List<String> sentence = ...;

List<String> nextFive = sentence.subList(5, 10);
```

此视图访问索引从 5 到 9 的元素。子列表的任何变动（如设置、添加或删除元素）都会影响原始列表。

对于排序后的集合和 map，你通过下界和上界指定范围：

```java
TreeSet<String> words = ...;

SortedSet<String> asOnly = words.subSet("a", "b");
```

与`subList`一样，第一个边界是包含的，第二个边界是排他的。

`headSet`和`tailSet`方法产生一个没有下界或上界的子范围。

```java
NavigableSet<String> nAndBeyond = words.tailSet("n");
```

通过`NavigableSet`接口，你可以为每个边界选择它应该是包含的还是排他的——参见表 7.5。

对于排序后的 map，有等价的方法`subMap`、`headMap`和`tailMap`。

### 7.6.3. 不可修改视图

有时，你想共享集合的内容，但不想让它被修改。当然，你可以将值复制到新集合中，但这可能开销很大。不可修改视图是一个更好的选择。这里有一个典型场景：`Person`对象维护一个朋友列表。如果`getFriends`给出该列表的引用，调用者就可以修改它。但提供一个不可修改的列表视图是安全的：

```java
public class Person {

    private ArrayList<Person> friends;

    public List<Person> getFriends() {
        return Collections.unmodifiableList(friends);
    }

    ...
}
```

所有的变器方法在不可修改视图上被调用时都会抛出异常。

正如从表 7.3 中所示，你可以获取集合、列表、集合、排序集合、导航集合、map、排序 map 和导航 map 的不可修改视图。

### 注意

在第 6 章中，你已经看到可能将错误类型的元素引入泛型集合（这种现象被称为“堆污染”），并且在检索不适当元素时会报告运行时错误，而不是在插入时。如果你需要调试此类问题，请使用检查视图（`checked view`）。当你构建（例如）一个`ArrayList<String>`时，改用：

```java
List<String> strings
    = Collections.checkedList(new ArrayList<>(), String.class);
```

该视图监控所有向列表的插入，并在添加错误类型的对象时抛出异常。

### 注意

`Collections`类产生同步的（`synchronized`）视图，确保对数据结构的安全并发访问。在实践中，这些视图不如`java.util.concurrent`包中显式为并发访问设计的数据结构有用。我建议你使用那些类并远离同步视图。

### 练习

1. 实现“埃拉托尼筛法”算法来确定所有 ≤ `n` 的质数。将从 2 到 `n` 的所有数字添加到集合中。然后反复找到集合中最小的元素`s`，并移除`s²`、`s · (s + 1)`、`s · (s + 2)`等。当`s² > n`时完成。使用`BitSet`执行此操作。

2. 在字符串列表中，将每个字符串转换为大写。通过 (a) 迭代器、(b) 遍历值以及 (c) `replaceAll`方法来实现。

3. 如何仅使用集合的方法计算两个集合的并集、交集和差集？

4. 产生一个导致`ConcurrentModificationException`的情况。你可以避免它吗？

5. 实现方法`public static void swap(List<?> list, int i, int j)`，当`list`实现`RandomAccess`时，以通常的方式交换位置`i`和`j`。

6. 我鼓励使用接口而不是具体的数据结构——例如，使用`Map`而不是`TreeMap`。假设你有一个类型为`Map<String, Set<Integer>>`的方法，有人用`HashMap`调用它。你可以使用什么种参数类型？

7. 编写一个程序，读取文件并打印每个单词出现的次数。使用`TreeMap<String, Integer>`。

8. 编写一个程序，读取文件并打印它们所在的行。使用从字符串到集合。

9. 你可以这样更新 map 中的计数器：

```java
counts.merge(word, 1, Integer::sum);
```

不使用`merge`方法实现相同的操作，(a) 使用`contains`、(b) 使用`get`配合`null`检查、(c) 使用`getOrDefault`、(d) 使用`putIfAbsent`。

10. 实现 Dijkstra 算法来寻找城市网络中的最短路径，某些城市通过道路连接。（有关描述，查看你喜欢的算法书籍或维基百科。）使用辅助记录`Neighbor`来存储相邻城市和距离。将图表示为从城市到邻居的 map。在算法中使用`PriorityQueue<Neighbor>`。

11. 编写一个程序将句子读取到列表中。然后使用`Collections.shuffle`打乱除第一个和最后一个单词以外的所有单词，无需复制到另一个集合。

12. 使用`Collections.shuffle`编写一个程序读取句子，打乱单词并打印结果。修复第一个单词的大小写和最后一个单词的标点符号（打乱前后）。提示：不要打乱单词。

13. `LinkedHashMap`在每次插入新元素时都会调用`removeEldestEntry`方法。实现一个子类`Cache`，根据构造函数提供的给定大小限制 map 的大小。

14. 编写一个程序证明`HashMap`的`keySet`、`values`和`entries`方法返回的集合是“活的”（`live`）。当 map 更新时会发生什么？当集合更新时对 map 会发生什么？

15. 编写一个方法产生从`0`到`n`数字的不可修改列表视图，而无需实际存储这些数字。

16. 将前面的练习泛化为任意的`IntFunction`。注意结果是一个无限集合，因此某些方法（如`size`和`toArray`）应该抛出`UnsupportedOperationException`。

17. 通过缓存最后计算的 100 个函数值来改进前面练习的实现。

18. 检查视图（checked view）如何为堆污染（heap pollution）的原因提供准确的错误报告。

19. `Collections`类具有静态变量`EMPTY_LIST`、`EMPTY_MAP`和`EMPTY_SET`。为什么它们没有`emptyList`、`emptyMap`和`emptySet`方法有用呢？

## 8. 流 (Streams)

流提供了一种数据视图，让你能够在比集合更高级的概念层指定计算任务。在流中，你指定的是“想要做什么”，而不是“如何做”。你将操作的调度留给实现部分。例如，假设你想计算某个属性的平均值。你指定数据源和属性，然后流库就可以优化计算，例如通过使用多个线程计算总和和计数并合并结果。

本章的要点是：

1. 迭代器意味着特定的遍历策略，并限制了高效的并发执行。

2. 你可以集合、数组、生成器或迭代器创建流。

3. 使用`filter`选择元素，使用`map`转换元素。

4. 其他转换流的操作包括`limit`、`distinct`和`sorted`。

5. 要从流获取结果，使用归约操作符，如`count`、`max`、`min`、`findFirst`或`findAny`。其中一些方法返回一个`Optional`值。

6. `Optional`类型旨在作为处理`null`值的安全替代方案。要安全地使用它，请利用`ifPresent`和`orElse`方法。

7. 你可以将流的结果收集到集合、数组、字符串或映射中。

8. `Collectors`类的`groupingBy`和`partitioningBy`方法允许你将流的内容分成组，并获取每个组的结果。

9. 针对原始数据类型`int`、`long`和`double`有专门的流。

10. 并行流（Parallel streams）会自动将流操作并行化。

### 8.1. 从迭代到流操作

当你处理一个集合时，通常会遍历它的元素，并对每个元素执行一些操作。例如，假设我们想统计一书中所有的长单词。首先，将它们放入列表：

```java
String contents = Files.readString(Path.of("alice.txt"), StandardCharsets.UTF_8);

List<String> words = List.of(contents.split("\\PL+"));

// 拆分为单词；非字母字符是分隔符
```

现在我们准备好进行迭代了：

```java
int count = 0;

for (String w : words) {
    if (w.length() > 12) count++;
}
```

使用流，相同的操作看起来如下：

```java
long count = words.stream()
    .filter(w -> w.length() > 12)
    .count();
```

现在，你不再需要扫描循环来寻找过滤和计数的证据了。方法名会立即告诉你代码的意图。此外，当循环详尽地规定了操作顺序时，流能够以它任何想要的方式调度操作，只要结果是正确的。

只需将`stream`改为`parallelStream`，流库即可并行执行过滤和计数。

```java
long count = words.parallelStream()
    .filter(w -> w.length() > 12)
    .count();
```

流遵循“做什么，而不是怎么做”的原则。在我们的流示例中，我们描述了需要做什么：获取长单词并计数。我们没有指定在哪个顺序、以什么方式执行。

流与集合表面上相似，但有显著差异：

1. 流不存储元素。

2. 流操作是惰性的（`lazy`），只有在需要时才会执行。

3. 只要谓词拒绝一个迭代生成的值，流就会结束。

### 8.2. 创建流

你已经看到可以通过`stream`方法将任何集合转换为流。如果是数组，请使用`Stream.of`。

```java
Stream<String> words = Stream.of(contents.split("\\PL"));

// split 返回 String[]
```

`of`方法具有变长参数，因此你可以从任意数量的参数构造流：

```java
Stream<String> song = Stream.of("gently", "down", "stream");
```

使用`Arrays.stream`从数组的一部分创建流。要创建一个空元素的流，使用静态`Stream.empty`方法：

`Stream`接口有两个静态方法来创建无限流。`generate`方法接收一个无参数的函数（技术上是`Supplier<T>`接口）。每当需要流值时，就会调用该函数产生值。你可以获取常量值的流：

```java
Stream<String> echos = Stream.generate(() -> "Echo");
```

或者获取随机数的流：

```java
Stream<Double> randoms = Stream.generate(Math::random);
```

要产生如`0 1 2 3 ...`的序列，请改用`iterate`方法。它接受一个“种子”值和一个函数（技术上是`UnaryOperator<T>`），并反复将该函数应用于上一个结果。例如：

```java
Stream<BigInteger> integers
    = Stream.iterate(BigInteger.ZERO, n -> n.add(BigInteger.ONE));
```

序列中的第一个元素是种子`BigInteger.ZERO`。第二个元素是`f(seed)`，即`1`（大整数）。下一个元素是`f(f(seed))`，即`2`，依此类推。

要产生有限流，请添加一个谓词来指定迭代何时结束：

```java
var limit = new BigInteger("10000000");

Stream<BigInteger> integers
    = Stream.iterate(BigInteger.ZERO,
       n -> n.compareTo(limit) < 0,
       n -> n.add(BigInteger.ONE));
```

最后，`Stream.ofNullable`方法可以从对象创建一个非常短的流。如果对象为`null`，流的长度为 0；否则长度为 1，且包含该对象。这在与`flatMap`结合时非常有用——示例参见第 8.7.7 节。

### 注意

Java API 中的许多方法都会产生流。例如，`String`类有一个`lines`方法，它会产生一个包含字符串中所有行的流：

```java
Stream<String> greetings = "Hello\nGuten Tag\nBonjour".lines()
```

`Pattern`类有一个方法`splitAsStream`，它可以根据正则表达式分割`CharSequence`。你可以使用以下语句将字符串拆分为单词：

```java
Stream<String> words = Pattern.compile("\\PL+").splitAsStream(contents);
```

`Scanner.tokens`方法产生一个包含扫描器令牌流。从字符串中获取单词流的另一种方法是：

```java
Stream<String> words = new Scanner(contents).tokens();
```

静态方法`Files.lines`返回一个文件中所有行的`Stream`：

```java
try (Stream<String> lines = Files.lines(path)) {
    // 处理行
}
```

要查看本节引入的流之一的内容，请使用`toList`方法，它将流的元素收集到列表中。像`count`一样，`toList`是终端操作。如果流是无限的，请先用`limit`方法对其进行截断：

```java
System.out.println(Stream.generate(Math::random).limit(10).toList());
```

### 注意

如果你有一个不是集合的`Iterable`，可以通过调用将其将其转换为流：

```java
StreamSupport.stream(iterable.spliterator(), false);
```

如果你有一个`Iterator`并想要获取其结果的流，请使用：

```java
StreamSupport.stream(Spliterators.spliteratorUnknownSize(iterator, Spliterator.ORDERED), false);
```

### 警告

在执行流操作时，**不要修改支持流的集合**，这一点非常重要。记住，流并不收集它们的数据——数据始终存储在独立的集合中。如果你修改了该集合，流操作的结果将变得不可定义。JDK 文档将此要求称为`noninterference`（非干扰）。

确切地说，由于中间流操作是惰性的，在执行终端操作之前，集合是可以改变的。例如，下面的代码虽然绝对不建议，但是可以运行的：

```java
List<String> wordList = . . .;
Stream<String> words = wordList.stream();
wordList.add("END");
long n = words.distinct().count();
```

但这段代码是错误的：

```java
Stream<String> words = wordList.stream();
words.forEach(s -> if (s.length() < 12) wordList.remove(s));
// 错误--干扰 (interference)
```

### 8.3. `filter`、`map`和`flatMap`方法

流转换产生一个其元素派自另一个流的流。你已经见过了`filter`转换，它产生一个包含符合特定条件的元素的新流。在这里，我们将字符串流转换为另一个仅包含长单词的流：

```java
List<String> words = ...;
Stream<String> longWords = words.stream().filter(w -> w.length() > 12);
```

`filter`的参数是一个`Predicate<T>`——即一个从`T`到`boolean`的函数。

通常，你想要以某种方式转换流中的值。使用`map`方法并传递执行转换的函数。例如，你可以这样将所有单词转换为小写：

```java
Stream<String> lowercaseWords = words.stream().map(String::toLowerCase);
```

在这里，我们使用了带有方法引用的`map`。通常，你会使用 Lambda 表达式来代替：

```java
Stream<String> firstLetters = words.stream().map(s -> s.substring(0, 1));
```

生成的流包含每个单词的第一个字母。



当你使用`map`时，函数会被应用于每个元素，结果是一个包含这些执行结果的新流。偶尔，你可能会遇到一个产生可选结果（optional）或多个结果的映射函数。例如，考虑一个`codePoints`方法，它产生字符串的所有代码点。例如，`codePoints("Hello")`将由`"H"`、`"e"`、`"l"`、`"l"`、`"o"`、`" "`、`" "`组成。注意地球符号（U+1F310）由两个`char`值组成，因此`codePoints`方法必须进行一些大量工作来实现这一点。我们稍后来看几种实现。

`codePoints`应该如何收集它的多个结果？对于流 API 来说，该方法返回`Stream<String>`是最自然的。

现在让我们在字符串流上映射这样的`codePoints`方法：

```java
Stream<Stream<String>> result = words.stream().map(w -> codePoints(w));
```

你将得到一个流的流，类似于`[. . . ["y", "o", "u", "r"], ["b", "o", "a", "t"], . . .]`。从像`[. . . ["y", "o", "u", "r"], ["b", "o", "a", "t"], . . .]`这样的字符串获取单词流，请使用`flatMap`而不是`map`：

```java
Stream<String> words = words.stream().flatMap(w -> codePoints(w));
```

使用`flatMap`时，你提供了一个为每个流元素产生流的方法。正如你所见，这可能很冗长，而且效率可能有点低。`mapMulti`方法提供了一种替代方案。它不是产生流，而是生成结果并将它们传递给收集器——一个实现`Consumer`接口的对象。对于每个结果，调用收集器的`accept`方法。

让我们用一个示例来完成这一点。以下循环产生字符串`s`的代码点：

```java
int i = 0;
while (i < s.length()) {
    int cp = s.codePointAt(i);
    i += Character.charCount(cp);
    // 对 cp 做一些处理
}
```

调用`mapMulti`时，你提供了一个会被用流元素和收集器调用的函数。在你的函数中，将你的结果传递给收集器。

```java
Stream<String> result = words.stream().mapMulti((s, collector) -> {
    int i = 0;
    while (i < s.length()) {
        int cp = s.codePointAt(i);
        i += Character.charCount(cp);
        collector.accept(cp);
    }
});
```

### 8.4. 提取子流和合并流

`stream('').limit(n)`调用返回一个在`n`个元素之后结束的新流（如果原始流较短，则在原始流结束时结束）。该方法对于裁剪无限流特别有用。例如：

```java
Stream<Double> randoms = Stream.generate(Math::random).limit(100);
```

产生一个包含 100 个随机数的流。

`stream('').skip(n)`调用完全相反。它丢弃前`n`个元素。这在我们读阅读示例中非常方便，由于`split`方法的工作方式，第一个元素是一个不需要的空字符串。我们可以通过调用`skip`让它消失：

```java
Stream<String> words = Stream.of(contents.split("\\PL+")).skip(1);
```

`stream`.takeWhile(`predicate`)`调用会在`predicate`为`true`时获取流中的所有元素，然后停止。

例如，假设我们使用前一节中的`codePoints`方法将字符串拆分为字符，并且我们想要收集所有的初始数字。`takeWhile`方法可以做到这一点：

```java
Stream<String> initialDigits = codePoints(str).takeWhile(
    s -> "0123456789".contains(s));
```

`dropWhile`方法的作用相反，它在条件为`true`时丢弃元素，并返回从第一个条件为`false`的元素开始的所有元素的流。例如：

```java
Stream<String> withoutInitialWhiteSpace = codePoints(str).dropWhile(String::isBlank);
```

可以使用`Stream`类的静态方法`concat`拼接两个流：

```java
Stream<String> combined = Stream.concat(
    codePoints("Hello"), codePoints("World"));

// 输出流 ["H", "e", "l", "l", "o", "W", "o", "r", "l", "d"]
```

当然，第一个流不应该是无限的——否则第二个流永远没有机会执行。

### 8.5. 其他流转换

`distinct`方法返回一个流，该流按原始流的相同顺序产生元素，但会抑制重复项。重复项不需要是相邻的。

```java
Stream<String> uniqueWords
    = Stream.of("merrily", "merrily", "merrily", "gently").distinct();

// 只保留了一个 "merrily"
```

对于流的排序，有`sorted`方法的多种变体。一种适用于`Comparable`元素的流，另一种则接受一个`Comparator`。在这里，我们对字符串进行排序，让最长的在前面：

```java
Stream<String> longestFirst
    = words.stream().sorted(Comparator.comparing(String::length).reversed());
```

与所有的流转换一样，`sorted`方法会产生一个新的流，其元素是原始流元素按排序后的顺序。

当然，你可以在不使用流的情况下对集合排序。当排序过程是流流水线的一部分时，`sorted`方法非常有用。

最后，`peek`方法产生另一个与原始流元素相同的流，但每当获取元素时都会调用一个函数。这对于调试非常有用：

```java
Object[] powers = Stream.iterate(1.0, p -> p * 2)
    .peek(e -> System.out.println("Fetching " + e))
    .limit(20).toArray();
```

当元素被实际访问时，会打印一条消息。这样你就可以验证`iterate`返回的无限流是惰性处理的。

### 提示

当你使用调试器调试流计算时，可以在从转换操作调用的方法中设置断点。在大多数 IDE 中，你也可以在 lambda 表达式中设置断点。如果你只想知道流流水线中特定一点发生了什么，可以添加：

```java
.peek(x -> {
    return; })
```

并在第二行设置断点。

### 8.6. 简单归约

现在你已经了解了如何创建和转换流，我们将终于进入最重要的一个点——从流数据中获取答案。我们在这一节中涵盖的方法称为归约（`reductions`）。归约是终端操作（`terminal operations`）。它们将流归约为可以在程序中使用的非流值。

你已经见过一个简单的归约了：`count`方法，它返回流的元素个数。

其他简单的归约还有`max`和`min`，它们返回最大值或最小值。这里有一个特殊——这些方法返回一个`Optional<T>`值，该值要么封装答案，要么表示没有值（因为流恰好是空的）。在过去，在这种情况下返回`null`是很常见的。但当这在测试不完全的程序中发生时，可能会导致空指针异常。`Optional`类型是指示缺失返回值的更好方式。我们将在下一节中详细讨论`Optional`类型。这里是你可以获取流的最大值的方法：

```java
Optional<String> largest = words.max(String::compareToIgnoreCase);

System.out.println("largest: " + largest.orElse(""));
```

`findFirst`返回非空集合中的第一个值。它在与`filter`结合时通常非常有用。例如，在这里我们找到第一个以字母 Q 开头的单词（如果它存在的话）：

```java
Optional<String> startsWithQ
    = words.filter(s -> s.startsWith("Q")).findFirst();
```

如果你对任何匹配都满意，而不仅仅是第一个，请使用`findAny`方法。这在并行化流时非常有效，因为流可以报告它找到的任何匹配项，而不是受限于第一个。

```java
Optional<String> startsWithQ
    = words.parallel().filter(s -> s.startsWith("Q")).findAny();
```

如果你只想知道是否存在匹配，请使用`anyMatch`。该方法接受一个谓词参数，所以你不需要使用`filter`。

```java
boolean aWordStartsWithQ
    = words.parallel().anyMatch(s -> s.startsWith("Q"));
```

还有`allMatch`和`noneMatch`方法，它们在所有元素或没有元素匹配谓词时返回`true`。这些方法也受益于并行化。

### 8.7. Optional 类型

`Optional<T>`对象是类型为`T`的对象或`none`的封装器。在前一种情况下，我们说值存在（`present`）。`Optional`类型旨在作为`null`的更安全的替代方案。后续节将向你如何正确使用它。

#### 8.7.1. 生成替代方案

有效使用`Optional`的关键是在没有值时产生一个替代方案，或者仅在值存在时消费它。这两种情况都有方法。

在本节中，我们查看第一种策略。通常，当没有匹配时你想要一个默认值，例如空字符串：

```java
String result = optionalString.orElse("");

// 如果无返回 ""
```

你还可以调用代码来计算默认值：

```java
String result = optionalString.orElseGet(() -> System.getProperty("myapp.default"));

// 仅在需要时调用函数
```

或者如果没有值则抛出异常：

```java
String result = optionalString.orElseThrow(IllegalStateException::new);

// 提供异常异常
```

#### 8.7.2. 存在时消费值

在前节中，你看到了如何在值不存在时产生替代方案。处理可选值的另一种策略是仅在值存在时消费它。

`ifPresent`方法接受一个函数。如果可选值存在，就会被传递给该函数。否则，什么都不会发生。

例如，如果你想在值存在时将其添加到集合中，调用：

```java
optionalValue.ifPresent(v -> results.add(v));
```

或者简单地：

```java
optionalValue.ifPresent(results::add);
```

如果你想在`Optional`有值时执行一个操作，在没有时执行另一个操作，使用`ifPresentOrElse`：

```java
optionalValue.ifPresentOrElse(
    v -> System.out.println("Found " + v),
    () -> logger.warning("No match"));
```

#### 8.7.3. Optional 值的管道化

在之前的节中，你了解了如何从`Optional`对象中获取值。另一种有效的策略是保持`Optional`完整。你可以通过`map`方法转换`Optional`内部的值：

```java
Optional<String> transformed = optionalString.map(String::toUpperCase);
```

如果`optionalString`是空的，那么`transformed`也是空的。

这是另一个例子。如果值存在，我们将结果添加到列表中：

```java
optionalValue.map(results::add);
```

如果`optionalValue`为空，什么都不会发生。

这个`map`方法相当于你在第 8.3 节中看到的`Stream`接口的`map`方法。简单来说，将可选值想象为一个大小为零或一的流。结果的大小同样为零或一，在后一种情况下，该函数已被应用。

同样地，你可以使用`filter`方法在转换之前或之后，仅考虑符合特定属性的`Optional`值。如果不符合该属性，流水线将产生一个空结果：

```java
Optional<String> transformed = optionalString
    .filter(s -> s.length() >= 8)
    .map(String::toUpperCase);
```

你可以使用`or`方法用一个备用的`Optional`替换空的`Optional`。备用方案是惰性计算的。

```java
Optional<String> result = optionalString.or(() -> // 提供一个 Optional
    alternatives.stream().findFirst());
```

如果`optionalString`有值，则`result`就是`optionalString`。否则，将求值 lambda 表达式并使用其结果。

#### 8.7.4. 如何错误地使用 Optional 值

如果你不正确使用`Optional`值，那么你并没有比过去的“某个值或`null`”方法有任何优势。

`get`方法在`Optional`值存在时获取其封装的元素，如果不存在则抛出`NoSuchElementException`。因此：

```java
Optional<T> optionalValue = ...;
optionalValue.get().someMethod();
```

这并不比下面安全：

```java
T value = ...;
value.someMethod();
```

`isPresent`和`isEmpty`方法报告`Optional<T>`对象是否有值。但是：

```java
if (optionalValue.isPresent()) optionalValue.get().someMethod();
```

这并不比下面更易于：

```java
if (value != null) value.someMethod();
```

**提示**

如果你发现自己正在使用`get`方法，请重新考虑你的方法，并尝试前两个节中的策略之一。

**注意**

`orElseThrow`是一个比`get`方法听起来更吓人的同义词。当你调用`optionalValue.orElseThrow().someMethod()`时，如果`optionalValue`为空，将显式地明确会发生异常。希望程序员只有在绝对确定这种情况不会发生时才使用`orElseThrow`。

以下是关于妥善使用`Optional`类型的更多提示：

- `Optional`类型的变量永远不应为`null`。
- 不要使用`Optional`类型的字段。代价是额外增加了一个对象。在类内部，使用`null`表示字段的缺失。为了阻碍使用`Optional`字段，该类没有设置为可序列化。
- `Optional`类型的方法参数是值得怀疑的。在请求的值存在的常见情况下，它们会使调用变得不愉快。相反，考虑该方法的两个重载版本，带参数和不带参数。（另一方面，返回一个`Optional`是好的。它是指示函数可能没有结果的正确方式。）
- 不要将`Optional`对象放入集合（set）中，也不要将其作为 map 的键。相反，收集值。

#### 8.7.5. 创建 Optional 值

到为止，我们讨论了如何使用他人创建的`Optional`对象。如果你想写一个创建`Optional`对象的方法，有几个静态方法用于此目的，包括`Optional.of(result)`和`Optional.empty()`。例如：

```java
public static Optional<Double> inverse(Double x) {
    return x == 0 ? Optional.empty() : Optional.of(1 / x);
}
```

`ofNullable`方法旨在作为从可能的`null`值到可选值的桥梁。如果`obj`不是`null`，则`Optional.ofNullable(obj)`返回`Optional.of(obj)`，否则返回`Optional.empty()`。

#### 8.7.6. 使用 `flatMap` 组合 Optional 值函数

假设你有一个产生`Optional<T>`的方法`f`，目标类型`T`有一个产生`Optional<U>`的方法`g`。如果它们是普通方法，你可以通过调用`s.f().g()`将它们组合。但这种组合不起通，因为`s.f()`的类型是`Optional<T>`，而不是`T`。相反，调用



`Optional<U> result = s.f().flatMap(T::g);`

如果 `s.f()` 存在，则对它应用 `g`。否则，返回一个空的 `Optional<U>`。

显然，如果你有更多产生 `Optional` 值的方法或 lambda 表达式，你可以重复该过程。你只需通过链式调用 `flatMap` 来构建一个步骤流水线，该流水线只有在所有部分都成功时才会成功。

例如，考虑前一节中安全的 `inverse` 方法。假设我们还有一个安全的平方根方法：

```
public static Optional<Double> squareRoot(Double x) {
    return x < 0 ? Optional.empty() : Optional.of(Math.sqrt(x));
}
```

然后你可以计算 `inverse` 的平方根：

```
Optional<Double> result = inverse(x).flatMap(Math::squareRoot);
```

或者，如果你喜欢，

```
Optional<Double> result = inverse(x).flatMap(Math::squareRoot);
```

**注意**

在本节中，我们考虑的是拥有 `Optional` 值的幸运情况。如今许多方法在没有结果时返回 `null`。假设 `Users.classicLookup(id)` 返回一个 `User` 对象或 `null`。那么你当然可以过滤掉这些 `null` 值：

```
Stream<User> users = ids.map(Users::classicLookup)
    .filter(Objects::nonNull);
```

但如果你偏好 `flatMap` 方法，可以使用

```
Stream<User> users = ids.flatMap(id -> Stream.ofNullable(Users.classicLookup(id)));
```

或者

```
Stream<User> users = ids.map(Users::classicLookup)
    .flatMap(Stream::ofNullable);
```

调用 `Stream.ofNullable(obj)` 在 `obj` 为 `null` 时产生空流，否则产生仅包含 `obj` 的流。

#### 8.7.7. 将 Optional 转换为 Stream

`stream` 方法将 `Optional<T>` 转换为零或一个元素的 `Stream<T>`。当你有一个 `Optional` 流时非常有用。

### 8.8. 收集结果

当你完成流的操作后，通常想要查看结果。你可以调用 `iterator` 方法，它产生一个旧式的迭代器，你可以用它访问元素。

或者，你可以调用 `forEach` 方法对每个元素应用函数：

```
stream.forEach(System.out::println);
```

在并行流上，`forEach` 方法以任意顺序遍历元素。如果你想按流顺序处理它们，请改用 `forEachOrdered`。当然，你可能会放弃部分或全部并行带来的优势。

但更多时候，你将将结果收集到数据结构中。你可以调用 `toArray` 并获取流元素的数组。

由于无法在运行时创建泛型数组，表达式 `stream.toArray()` 返回一个 `Object[]` 数组。如果你想获得正确类型的数组，请传入数组构造函数：

```
String[] result = stream.toArray(String[]::new);

// stream.toArray() 的类型为 Object[]
```

要将流元素收集到另一个目标，有一个方便的 `collect` 方法，它接收 `Collector` 接口的实例。`collector` 是一个累积元素并产生结果的对象。`Collectors` 类为常用的收集器提供了大量的工厂方法。要将流收集到集合中，只需调用：

```
Set<String> result = stream.collect(Collectors.toSet());
```

如果你想控制获取哪种类型的集合，请使用以下调用：

```
TreeSet<String> result = stream.collect(Collectors.toCollection(TreeSet::new));
```

假设你想通过拼接收集流中的所有的字符串。你可以调用：

```
String result = stream.collect(Collectors.joining());
```

如果你想在元素之间使用一个分隔符，请将其传递给 `joining` 方法：

```
String result = stream.collect(Collectors.joining(", "));
```

如果你的流中包含字符串以外的对象，你需要先将它们转换为字符串，如下：

```
String result = stream.map(Object::toString).collect(Collectors.joining(", "));
```

如果你想将流结果归约为和、计数、平均值、最大值或最小值，请使用 `summarizing`(`Int`|`Long`|`Double`) 方法之一。这些方法接收一个将流对象映射为数字的函数，并返回类型为 (`Int`|`Long`|`Double`)`SummaryStatistics` 的结果，同时计算和、计数、平均值、最大值最小值。

```
IntSummaryStatistics summary = stream.collect(
    Collectors.summarizingInt(String::length));

double averageWordLength = summary.getAverage();
double maxWordLength = summary.getMax();
```

### 8.9. 收集到 Map

假设你有一个 `Stream<Person>` 并并将元素收集到 map 中，以便以后可以通过 ID 查找人员。`Collectors.toMap` 方法有两个函数参数，用于生成 map 的键和值。例如：

```
Map<Integer, String> idToName = people.collect(
    Collectors.toMap(Person::getId, Person::getName));
```

在值应该是实际元素的常见情况下，请对第二个函数使用 `Function.identity()`。

```
Map<Integer, Person> idToPerson = people.collect(
    Collectors.toMap(Person::getId, Function.identity()));
```

如果存在多个相同键的元素，则会发生冲突，收集器将抛出 `IllegalStateException`。你可以通过提供第三个函数参数来覆盖该行为，该参数解决冲突并根据现有值和新值确定该键的值。你的函数可以返回现有值、新值或两者的组合。

在这里，我们构建了一个 map，对于可用区域（locales）中的每种语言，键是其在默认区域的名称（例如 `"German"`），值是其本地化后的名称（例如 `"Deutsch"`）。

```
Stream<Locale> locales = Stream.of(Locale.getAvailableLocales());

Map<String, String> languageNames = locales.collect(
    Collectors.toMap(
        Locale::getDisplayLanguage,
        loc -> loc.getDisplayLanguage(loc),
        (existingValue, newValue) -> existingValue));
```

我们并不在乎相同语言可能出现两次（例如，在德国和瑞士的德语），所以我们只保留第一个条目。

### 注意

在本章中，我使用 `Locale` 类作为有趣数据集的来源。有关处理区域的更多信息，请参见第 13 章。

现在假设我们想知道某个国家的所有语言。我们需要一个 `Map<String, Set<String>>`。例如，`"Switzerland"` 的值集合 `[French, German, Italian]`。最初，我们为每种语言存储一个单元素集合。每当为某个国家发现新语言时，形成现有集合和新集合的并集。

```
Map<String, Set<String>> countryLanguageSets = locales.collect(
    Collectors.toMap(
        Locale::getDisplayCountry,
        l -> Collections.singleton(l.getDisplayLanguage()),
        (a, b) -> { // a 和 b 的并集
            var union = new HashSet<String>(a);
            union.addAll(b);
            return union; }));
```

你将在下一节看到获取此 map 的更简单的方法。

如果你想要 `TreeMap`，请将构造函数作为第四个参数。你必须提供一个合并函数。这里是节开头的示例之一，现在产生 `TreeMap`：

```
Map<Integer, Person> idToPerson = people.collect(
    Collectors.toMap(
        Person::getId,
        Function.identity(),
        (existingValue, newValue) -> { throw new IllegalStateException(); },
        TreeMap::new));
```

### 注意

对于每个 `toMap` 方法，都有一个相应的 `toConcurrentMap` 方法，它产生一个并发 map。在并行收集过程中使用单个并发 map。当与并行流一起使用，共享 map 比合并更高效。

### 8.10. 分组与分区

在前面的节中，你了解了如何收集某个国家的语言。但该过程有点繁琐。你需要为每个 map 生成单元素集合，然后指定如何合并。对相同特征的值进行分组非常常见，`groupingBy` 方法直接支持它。

```
Map<String, List<Locale>> countryToLocales = locales.collect(
    Collectors.groupingBy(Locale::getCountry));
```

注意

函数 `Locale::getCountry` 是分组的*分类函数*。你现在可以查找某个国家的所有区域，例如

```
List<Locale> swissLocales = countryToLocales.get("CH");
    // 产生 [it_CH, de_CH, fr_CH]
```

注意

在这种情况下，使用 `partitioningBy` 更高效。例如，这里我们将所有区域分为使用英语的区域和其他区域：

```
Map<Boolean, List<Locale>> englishAndOtherLocales = locales.collect(
    Collectors.partitioningBy(l -> l.getLanguage().equals("en")));

List<Locale> englishLocales = englishAndOtherLocales.get(true);
```

### 8.11. 下游收集器

`groupingBy` 方法产生一个值为列表的 map。如果你想以某种方式处理这些列表，请提供一个*下游收集器*。例如，如果你想要集合而不是列表，可以使用前面节见过的 `Collectors.toSet` 收集器：

```
Map<String, Set<Locale>> countryToLocaleSet = locales.collect(
    groupingBy(Locale::getCountry, toSet()));
```

在本示例中，以及本节剩余的示例中，我假设已静态导入 `java.util.stream.Collectors.*` 以使表达式更易读。

提供了几个收集器可以将分组后的元素归类为数字：

- `counting` 产生收集元素的计数。例如，

```
Map<String, Long> countryToLocaleCounts = locales.collect(
    groupingBy(Locale::getCountry, counting()));
```

统计每个国家有多少个区域（locale）。

- `summing(`Int`|`Long`|`Double`)` 接收一个函数参数，将该函数应用于下游元素，并产生它们的和。例如，

```
Map<String, Integer> stateToCityPopulation = cities.collect(
    groupingBy(City::getState, summingInt(City::getPopulation)));
```

计算城市流中每个州的人口总和。

- `maxBy` 和 `minBy` 接收一个比较器并产生下游元素的最大值和最小值。例如，

```
Map<String, Optional<City>> stateToLargestCity = cities.collect(
    groupingBy(City::getState,
        maxBy(Comparator.comparing(City::getPopulation))));
```

产生每个州最大的城市。

`mapping` 收集器对下游结果应用一个函数，它还需要另一个收集器来处理其结果。例如，

```
Map<String, Optional<String>> stateToLongestCityName = cities.collect(
    groupingBy(City::getState,
        mapping(City::getName,
            maxBy(Comparator.comparing(String::length)))));
```

在这里，我们按州对城市进行分组。在每个州内部，我们产生城市名称并按最大长度归约。

`mapping` 方法还为前一节中的问题提供了一个更好的解决方案——收集一个国家所有语言的集合。

```
Map<String, Set<String>> countryToLanguages = locales.collect(
    groupingBy(Locale::getDisplayCountry,
        mapping(Locale::getDisplayLanguage,
            toSet())));
```

还有一个 `flatMapping` 方法，用于返回流的函数（参见练习 8）。

在前一节中，我使用了 `toMap` 代替 `groupingBy`。在这种形式下，你不需要担心合并单个集合。

如果分组或映射函数的返回类型为 `int`、`long` 或 `double`，你可以将元素收集到摘要统计对象中，如第 8.8 节所述。例如，

```
Map<String, IntSummaryStatistics> stateToCityPopulationSummary = cities.collect(
    groupingBy(City::getState,
        summarizingInt(City::getPopulation)));
```

然后你可以从每个组的摘要统计对象获取函数值的和、计数、平均值、最小值和最大值。

`filtering` 收集器对每个组应用过滤器，例如：

```
Map<String, Set<City>> largeCitiesByState = cities.collect(
    groupingBy(City::getState,
        filtering(c -> c.getPopulation() > 500000,
            toSet())); // 没有大城市的州为空集合
```

最后，你可以使用 `teeing` 收集器分支到两个并行的下游收集。当你需要从一个流中计算多个结果时，这非常有用。假设你想收集城市名称并同时计算它们的平均人口。你不能读取两次流，但 `teeing` 允许执行两次计算。指定两个下游收集器和一个合并结果的函数。

```
record Pair<S, T>(S first, T second) {}

Pair<List<String>, Double> result = cities.filter(c -> c.state().equals("NV"))
    .collect(teeing(
        mapping(City::name, toList()), // 第一个下游收集器
        averagingDouble(City::population), // 第二个下游收集器
        (list, avg) -> new Pair(list, avg))); // 合并函数
```

### 注意

还有三个版本的 `reducing` 方法用于应用通用的归约，如下一节所述。



组合收集器是强大的，但它可能导致非常复杂的表达式。最好的用法是结合`groupingBy`或`partitioningBy`来处理“下游” map 的值。否则，请直接在流上应用`map`、`reduce`、`count`、`max`或`min`等方法。

### 8.12 归约操作

`reduce`方法是从流中计算值的通用机制。最简单的形式接收一个二元函数并从前两个元素开始不断应用它。如果函数是和，那么这很好很好解释：

```
List<Integer> values = ...;

Optional<Integer> sum = values.stream().reduce((x, y) -> x + y);
```

在这种情况下，`reduce`方法计算`v[0]` + `v[1]` + `v[2]` + ..., 其中`v[i]`是流元素。该方法返回一个`Optional`，因为如果流为空，就没有有效的结果。

### 注意

在这种情况下，你可以使用`reduce(Integer::sum)`代替`reduce((x, y) -> x + y)`。

更通地说，你可以使用任何将部分结果`x`与下一个值`y`结合的操作。

有些时候`reduce`并不足够通用。例如，假设你想将结果收集到一个`BitSet`中。如果该集合操作是并行的，你无法直接将元素放入单个`BitSet`中，因为`BitSet`对象不是线程安全的。由于这个原因，你无法使用`reduce`。每个分段都需要从一个属于自己的空集合开始，而`reduce`只允许你提供一个恒等值（identity value）。相反，请使用`collect`。它接受三个参数：

1. 一个`supplier`（供给者），用于创建目标对象的新实例，例如哈集合的构造函数

2. 一个`accumulator`（累加器），将元素添加到目标中，例如`add`方法

3. 一个`combiner`（合并器），将两个对象合并为一个对象，例如`addAll`

以下是`collect`方法对位集操作的工作方式：

```
BitSet result = stream.collect(BitSet::new, BitSet::set, BitSet::or);
```

### 8.13. 基本类型流

到目前为止，我们一直都在`Stream<Integer>`中收集整数，尽管将每个整数封装成一个包装对象显然是低效的。对于其他基本类型`double`、`float`、`long`、`short`、`char`、`byte`和`boolean`也是如此。流库提供了专门的类型`IntStream`、`LongStream`和`DoubleStream`，它们直接存储基本值，而不使用包装类。如果你想存储`short`、`char`、`byte`和`boolean`，请使用`IntStream`；对于`float`，使用`DoubleStream`。

要创建一个`IntStream`，调用`IntStream.of`和`Arrays.stream`方法：

```
IntStream stream = IntStream.of(1, 1, 2, 3, 5);

stream = Arrays.stream(values, from, to); // values 是一个 int[] 
```

同样可以使用静态方法`generate`和`iterate`。此外，`IntStream`和`LongStream`具有静态方法`range`和`rangeClosed`，它们可以生成步长为一的整数范围：

```
IntStream zeroToNinetyNine = IntStream.range(0, 100); // 排除上限

IntStream zeroToHundred = IntStream.rangeClosed(0, 100); // 包含上限
```

`CharSequence`接口拥有`codePoints`和`chars`方法，它们可以产生产生字符的 Unicode 码或 UTF-16 编码中代码单元的`IntStream`。（细节请参阅 第 1 章。）

```
String sentence = "\uD835\uDD46 is the set of octonions.";

     // \uD835\uDD46 是字母 𝕆 的 UTF-16 编码，unicode U+1D546
```

```
IntStream codes = sentence.codePoints();

     // 带有进制值为 1D546 20 69 73 20 ... 的流
```

`RandomGenerator`接口拥有`ints`、`longs`和`doubles`方法，它们返回随机数的基本类型流。

```
IntStream randomIntegers = RandomGenerator.getDefault().ints()
```

当你有一个对象流时，可以使用`mapToInt`、`mapToLong`或`mapToDouble`方法将其转换为基本类型流。例如，如果你有一个字符串流并想以整数形式处理它们的长度，你完全可以在`IntStream`中进行：

```
Stream<String> words = ...;

IntStream lengths = words.mapToInt(String::length);
```

要将基本类型流转换为对象流，请使用`boxed`方法：

```
Stream<Integer> integers = IntStream.range(0, 100).boxed();
```

通常情况下，基本类型流上的方法与对象流上的方法是类似的。以下是最显著的区别：

- ![Images](img/sq.jpg) `toArray`方法返回基本类型数组。

- ![Images](img/sq.jpg) 产生可选结果的方法返回`OptionalInt`、`OptionalLong`或`OptionalDouble`。这些类与`Optional`类类似，但它们拥有`getAsInt`、`getAsLong`和`getAsDouble`方法，而不是`get`方法。

- ![Images](img/sq.jpg) 存在`sum`、`average`、`max`和`min`方法，分别返回总和、平均值、最大值和最小值。这些方法在对象流上并没有定义。

- ![Images](img/sq.jpg) `summaryStatistics`方法产生一个`IntSummaryStatistics`、`LongSummaryStatistics`或`DoubleSummaryStatistics`类型的对象，可以同时报告流的总和、计数、平均值、最大值和最小值。

### 8.14. 并行流

流使得批量操作并行化变得简单。过程大部分是自动的，你需要遵循一些规则。首先，你必须有一个并行流。你可以通过任何集合的`Collection.parallelStream()`方法获取并行流：

```
Stream<String> parallelWords = words.parallelStream();
```

此外，`parallel`方法可以将任何顺序流转换为并行流。

```
Stream<String> parallelWords = Stream.of(wordArray).parallel();
```

只要在终端方法执行时流处于并行模式，所有的中间流操作都将并行化。

当流操作以并行方式运行时，其意图是并行的。为了确保结果的正确性，流操作必须是无状态的（stateless）且无副作用的（side-effect free）。如果流操作依赖于状态，结果可能会变得不可预测。

当流操作以并行方式运行时，其意图是并行的。为了确保结果的正确性，流操作必须是无状态的（stateless）且无副作用的（side-effect free）。如果流操作依赖于状态，结果可能会变得不可预测。

当流操作以并行方式运行时，其意图是并行的。为了确保结果的正确性，流操作必须是无状态的（stateless）且无副作用的（side-effect free）。如果流操作依赖于状态，结果可能会变得不可预测。

当流操作以并行方式运行时，其意图是并行的。为了并行化，操作可以按任意顺序执行。

这里有一个你无法执行的示例。假设你想统计字符串流中的所有短单词：

```
var shortWords = new int[12];

words.parallelStream().forEach(

    s -> { if (s.length() < 12) shortWords[s.length]++; });

         // 错误——竞态条件！

System.out.println(Arrays.toString(shortWords));
```

这是糟糕的代码。传递给`forEach`的函数在多个线程中并发运行，每个线程都在更新一个共享数组。正如你在第 10 章 中看到的，那是经典的*竞态条件*。如果你多次运行此程序，可能会得到不同的计数。

为了并行化，你有责任确保传递给并行流操作的函数是安全的。做到这一点的最佳方法是远离可变状态。在这个示例中，如果你按长度对分组并计数，可以安全地并行化：

```
Map<Integer, Long> shortWordCounts

    = words.parallelStream()
        .filter(s -> s.length() < 12)
        .collect(groupingBy(

            String::length,

            counting()));
```

```java
Map<Integer, List<String>> result = words.parallelStream().collect(

    Collectors.groupingByConcurrent(String::length));

    // 值并不是按流的顺序收集的
```

当然，如果你使用与顺序无关的下游收集器，例如，你就不在乎：

```java
Map<Integer, Long> wordCounts

    = words.parallelStream()

    .collect(
        groupingByConcurrent(
            String::length,
            counting()));
```

不要为了加速操作就将你所有的流都转换为并行流（parallel streams）。请记住这些问题：

![Images](img/sq.jpg) 并行化的开销很大，只有在处理非常大的数据集时才有意义。

![Images](img/sq.jpg) 只有当底层数据源能够被有效地拆分成多个部分时，并行化流才是划算的。

![Images](img/sq.jpg) 并行流使用的线程池可能会因为文件 I/O 或网络访问等阻塞操作而导致饥饿。

并行流在处理巨大的内存数据集合和计算密集型处理时效果最好。

### 提示

通常情况下，并行化文件输入没有收益。然而，`Files.lines`方法返回的流使用了内存映射文件，拆分是有效的。如果你处理一个大文件的行，并行化流可能会提高性能。

### 注意

如果你在并行流中需要随机数，请从`RandomGenerator.SplittableGenerator.of`工厂方法获取一个生成器。

### 注意

默认情况下，并行流使用由`ForkJoinPool.commonPool`返回的全局 fork-join 池。如果你的操作没有阻塞且没有与其他任务共享该池，那就是没问题的。有一个替换不同池的技巧。将你的操作放在自定义池的`submit`方法中：

```java
ForkJoinPool customPool = . . .;

result = customPool.submit(() ->

   stream.parallel().map(. . .).collect(. . .)).get();
```

或者，异步地：

```java
CompletableFuture.supplyAsync(() ->

   stream.parallel().map(. . .).collect(. . .),

   customPool).thenAccept(result -> . . .);
```

### 练习

1. 验证请求前五个长单词在找到第五个长单词后是否不再调用`filter`方法。只需记录每次方法调用即可。

2. 测量使用`parallelStream`而不是`stream`统计长单词的差异。在调用前后分别调用`System.currentTimeMillis`并打印差异。如果你有一台快速的电脑，请切换到更大的文档（如*战争与和平*）。

3. 假设你有一个数组`int[] values = { 1, 4, 9, 16 }`。`Stream.of(values)`是什么？如何获取一个`int`的流呢？

4. 使用`Stream.iterate`创建一个无限随机数流——不是通过调用`Math.random`，而是通过直接实现一个*线性生成器*。在这样的生成器中，你从`x[0]` = `seed`开始，然后产生`x[n]` + 1 = (*a x[n]* + *c*) `%` *m*，其中`a`、`c`和`m`是适当的值。你应该实现一个参数为`a`、`c`、`m`和`seed`的方法，返回一个`Stream<Long>`。尝试`a` = 25214903917，`c` = 11和`m` = 248。

5. 第 8.3 节 中的`codePoints`方法有点笨拙，先填充一个列表然后将其转换为流。改写一个基于流的版本，使用`IntStream.iterate`方法构造一个有限的偏移量流，然后提取子字符串。

6. 使用`String.codePoints`方法实现一个方法，测试字符串是否为仅由字母组成的单词。（提示：`Character.isAlphabetic`。）使用相同的方法，实现一个测试字符串是否为合法的 Java 标识符的方法。

7. 将文件转换为标记标记流，列出前 100 个符合上一个练习意义的单词标记。再次读取文件并列出出现频率最高的 10 个单词，忽略大小写。

8. 为`Collectors.flatMapping`方法寻找一个实际用途。考虑某个具有返回`Optional`的方法的类。然后根据某些特征进行分组，对于每个组，使用`flatMapping`和`Optional.stream`收集非空的可选值。

9. 你可以将流的视为一种“拉”机制，值在需要时被懒性地拉取。相反是“推”机制，它在值可用时积极产生值并将其传递给消费者。示例有`Iterable.forEach`和`Iterator.forEachRemaining`方法。这些是带有参数`Consumer<? super T>`的方法。编写一个静态方法，从此类方法产生流。例如，

```java
Iterator<String> iter = ...;

Stream<String> stream = fromPusher(iter::forEachRemaining);
```

该方法的签名格为

```java
public static <T> Stream<T> fromPusher(Consumer<Consumer<? super T>> pusher)
```

提示：在伪的`Stream.of((T) null)`上使用`mapMulti`。

10. 从`/usr/share/dict/words`（或类似的单词列表）读取单词到流中，并产生一个包含所有单词的数组。

11. 给出一个字符串流，找出所有包含元元的字符串。

12. 给出一个有限的字符串流，找到最大长度。

13. 你的经理要求写一个`public static boolean isFinite(Stream<T>)`。为什么这不是个好主意？

14. 写一个`public static <T> Stream<T> zip(Stream<T> first, Stream<T> second)`，交替来自`first`和`second`的元素。

15. 使用`ArrayList<T>`连接所有元素。

16. 使用`reduce`的三种形式来计算平均值。

17. 使用并行流找到*战争与和平*中 500 个 50 位数字的素数，使用`BigInteger.ProbablePrime`方法。

18. 如何从流中消除相邻元素？

19. 你的方法如果流是并行的会工作吗？

## 9 输入与输出

在本章中，你将学习如何处理文件、目录和网页，以及如何以二进制和文本格式读写数据。你还会发现关于正则表达式的讨论，这对于处理输入很有帮助。（我找不到一个更好的地方来处理这个话题，显然 Java 开发者也是如此——当正则表达式 API 被提出时，它是附加在新的 I/O 请求上的。）最后，本章将展示如何像存储文本或数字一样存储对象。

本章的要点是：

1. `InputStream`是字节源，`OutputStream`是字节目的地。

2. `Reader`读取字符，`Writer`写入字符。务必指定字符编码。

3. `Files`类提供了方便的方法来读取文件的所有字节或所有行。

4. `DataInput`和`DataOutput`接口具有以二进制格式写入数字的方法。

5. 使用`RandomAccessFile`或内存映射文件进行随机访问。

6. `Path`是文件系统中绝对或相对路径组件的序列。路径可以组合（或“解析”）。

7. 使用`Files`类的方法来复制、移动或删除文件，并递归遍历目录树。

8. 使用 ZIP 文件系统读取或更新 ZIP 文件。

9. 你可以使用`URL`类读取网页内容。要读取元数据或写入数据，请使用`URLConnection`类。



10. 通过 `Pattern` 和 `Matcher` 类，你可以在字符串中找到正则表达式的所有匹配项，以及每个匹配项的捕获组。

11. 序列化机制可以保存和恢复任何实现了 `Serializable` 接口的对象，前提是该对象的实例变量也是可序列化的。

## 9.1 输入/输出流、读取器和写入器

在 Java API 中，可以读取字节的源被称为 `input stream`（输入流）。这些字节可以来自文件、网络连接或内存中的数组。（这些流与第 8 章中的流无关。）同样，字节的目的地是 `output stream`（输出流）。相比之下，`readers`（读取器）和 `writers`（写入器）消耗并产生 `characters` 序列。在接下来的章节中，你将学习如何读写字节和字符。

### 9.1.1 获取流

从文件获取流简单的方法是使用静态方法：

```java
InputStream in = Files.newInputStream(path);

OutputStream out = Files.newOutputStream(path);
```

在这里，`path` 是 `Path` 类的实例，该类将在第 9.2.1 节介绍。

如果你有一个 URL，可以从 `URL` 类 `openStream` 方法返回的输入流读取其内容：

```java
var url = new URL("https://horstmann.com/index.html");

InputStream in = url.openStream();
```

第 9.3 节将介绍如何向 Web 服务器发送数据。

`ByteArrayInputStream` 类允许你从字节数组中读取：

```java
byte[] bytes = ...;

var in = new ByteArrayInputStream(bytes);
```

从 `in` 读取。

反之，要向字节数组发送输出，请使用 `ByteArrayOutputStream`：

```java
var out = new ByteArrayOutputStream();

// 写入到 out

byte[] bytes = out.toByteArray();
```

### 9.1.2 读取字节

`InputStream` 类有一个方法可以读取单个字节：

```java
InputStream in = ...;

int b = in.read();
```

该方法要么返回 `0` 到 `255` 之间的整数字节，要么在到达输入末端时返回 `-1`。

> **注意**
>
> Java `byte` 类型的值范围在 `-128` 到 `127` 之间。你可以在检查返回值不为 `-1` 之后将其转换为 `byte`。

更常见的情况下，你可能希望批量读取字节。最方便的方法是 `readAllBytes` 方法，它简单地从流中读取所有字节到字节数组中：

```java
byte[] bytes = in.readAllBytes();
```

> **提示**
>
> 如果你想从文件中读取所有字节，请调用便利方法：

```java
byte[] bytes = Files.readAllBytes(path);
```

如果你想读取某些字节而不是所有字节，请提供一个字节数组并调用 `readNBytes` 方法：

```java
var bytes = new byte[len];

int bytesRead = in.readNBytes(bytes, offset, n);
```

该方法会一直读取到读取 `n` 个字节或没有更多输入为止，并返回实际读取的字节数。如果没有可用输入，这些方法将返回 `-1`。

> **注意**
>
> 还有一个 `read(byte[], int, int)` 方法，其描述看起来与 `readNBytes` 完全相同。区别在于 `read` 方法只尝试读取字节，如果失败则会立即返回一个较小的计数。`readNBytes` 方法会持续调用 `read`，直到获取了所有请求的字节或 `read` 返回 `-1`。

最后，你可以跳过字节：

```java
long bytesToSkip = ...;

in.skipNBytes(bytesToSkip);
```

### 9.1.3 写入字节

`OutputStream` 的 `write` 方法可以写入单个字节和字节数组：

```java
OutputStream out = ...;

int b = ...;

out.write(b);

byte[] bytes = ...;

out.write(bytes);

out.write(bytes, start, length);
```

当你完成流的写入后，必须关闭它以提交任何缓冲输出。最佳做法是使用 try-with-resources 语句：

```java
try (OutputStream out = ...) {
    out.write(bytes);
}
```

如果你需要将输入流复制到输出流，请使用 `InputStream.transferTo` 方法：

```java
try (InputStream in = ...; OutputStream out = ...) {
    in.transferTo(out);
}
```

在调用 `transferTo` 后，两个流都需要关闭。最好使用 try-with-resources 语句，如代码示例所示。

要将文件写入 `OutputStream`，请调用：

```java
Files.copy(path, out);
```

反之，要将 `InputStream` 保存到文件，请调用：

```java
Files.copy(in, path, StandardCopyOption.REPLACE_EXISTING);
```

### 9.1.4 字符编码

输入流和输出流用于字节序列，但在许多情况下，你将处理文本——即字符序列。这时，字符如何编码为字节就变得重要了。

Java 使用 Unicode 标准来处理字符。每个字符或“代码点”都有一个 21 位的整数。有不同的 `character encodings`（字符编码）——即将这些 21 位数字封装成字节的方法。

最常见的编码是 UTF-8，它将每个 Unicode 代码点编码为一个到四个字节的序列（参见表 9.1）。UTF-8 的优势在于，传统 ASCII 字符集（包含所有英语使用的字符）的字符只占用一个字节。

表 9.1：UTF-8 编码

![images](img/09tab01.jpg)

另一种常见的编码是 UTF-16，它将每个 Unicode 代码点编码为一个或两个 16 位值（参见表 9.2）。这是 Java 字符串中使用的编码。实际上，UTF-16 有两种形式，称为“大端”和“小端”。考虑 16 位值 `0x2122`。在大端格式下，高位字节在前：`0x21` 随后是 `0x22`。在小端格式下，情况相反：`0x22 0x21`。为了指示使用了两者中的哪一种，文件可以以“字节序标记”开头，即 16 位数值 `0xFEFF`。读取器可以使用此值确定字节序并丢弃它。

表 9.2：UTF-16 编码

![images](img/09tab02.jpg)

> **注意**
>
> 某些程序（包括记事本）会在 UTF-8 编码文件的开头添加字节序标记。显然，由于 UTF-8 没有字节序问题，这并非必要。但 Unicode 标准允许这样做，甚至建议这是一个很不错的主意，因为它减少了对编码的疑虑。它在读取 UTF-8 编码文件时本应该被移除。遗憾的是，Java 并没有这样做，针对此问题的错误报告已被关闭为“不修复”。最好的办法是过滤掉输入中发现的任何领先 `\uFEFF`。

除了 UTF 编码外，还有覆盖特定用户群字符范围的局部编码。例如，ISO 8859-1 是一种包含西欧语言使用的带音字符的单字节编码。Shift_JIS 是日语字符的变长编码。许多此类编码仍被广泛使用。

没有可靠的方法从字节流中自动检测字符编码。某些 API 方法允许你使用“默认字符集”——即计算机操作系统偏好的字符编码。这与你的字节源使用的编码相同吗？这些字节可能源自世界的不同部分。因此，你应该始终显式指定编码。例如，在读取页面时，检查 `Content-Type` 头部。

> **注意**
>
> 平台编码由静态方法 `Charset.defaultCharset()` 返回。静态方法 `Charset.availableCharsets()` 返回所有可用的 `Charset` 实例，这是一个从规范名称到 `Charset` 对象的映射。

> **注意**
>
> Oracle 的实现有一个系统属性 `file.encoding` 用于覆盖平台默认值。这不是一个官方支持的属性，且 Oracle Java 库实现的所有部分并未一致遵循它。你不应该设置它。

`StandardCharsets` 类拥有 `Charset` 类型的静态变量，对应每个 Java 虚拟机必须支持的字符编码：

```java
StandardCharsets.UTF_8
StandardCharsets.UTF_16
StandardCharsets.UTF_16BE
StandardCharsets.UTF_16LE
StandardCharsets.ISO_8859_1
StandardCharsets.US_ASCII
```

要获取另一种编码的 `Charset`，请使用静态方法 `forName`：

```java
Charset shiftJIS = Charset.forName("Shift_JIS");
```

在读取或写入文本时，使用 `Charset` 对象。例如，你可以将字节数组转换为字符串：

```java
var contents = new String(bytes, StandardCharsets.UTF_8);
```

> **提示**
>
> 某些方法允许你通过 `Charset` 对象或字符串来指定字符编码。请选择 `StandardCharsets` 常量，这样你就不必担心拼写是否正确了。例如，`new String(bytes, "UTF 8")` 是不可接受的，并且会导致运行时错误。

> **警告**
>
> 某些方法（如 `String(byte[])` 构造函数）如果你不指定任何编码，将使用默认的平台编码；其他方法（如 `Files.readAllLines`）则使用 UTF-8。

### 9.1.5 文本输入

要读取文本输入，使用 `Reader`。你可以通过 `InputStreamReader` 适配器从任何输入流获取 `Reader`：

```java
InputStream inStream = ...;

var in = new InputStreamReader(inStream, charset);
```

如果你想一次处理一个 UTF-16 代码单元的输入，可以调用 `read` 方法：

```java
int ch = in.read();
```

该方法返回一个 `0` 到 `65536` 之间的代码单元，或者在输入结束时返回 `-1`。

这并不方便。这里有几种替代方案。

对于短文本文件，你可以这样将其读取为字符串：

```java
String content = Files.readString(path, charset);
```

但如果你想将文件作为行序列处理，请调用：

```java
List<String> lines = Files.readAllLines(path, charset);
```

如果文件很大，请作为 `Stream<String>` 对其进行惰性处理：

```java
try (Stream<String> lines = Files.lines(path, charset)) {
    ...
}
```

> **注意**
>
> 如果在流获取行时发生 `IOException`，该异常将被封装进 `UncheckedIOException` 并从流操作中抛出。（这种手段是必要的，因为流操作没有声明抛出任何检查异常。）

要从文件中读取数字或单词，请使用 `Scanner`，如你在第 1 章中所示。例如：

```java
var in = new Scanner(path, StandardCharsets.UTF_8);

while (in.hasNextDouble()) {
    double value = in.nextDouble();
    ...
}
```

> **提示**
>
> 要读取字母单词，请将扫描器的分隔符设置为正则表达式，该正则是你想要接受的标记的补集。例如，在调用以下方法之后：

```java
in.useDelimiter("\\PL+");
```

扫描器将读取字母，因为任何非字母序列都是分隔符。正则表达式语法请参阅第 9.4.1 节。

然后，你可以通过如下方式获取所有单词的流：

```java
Stream<String> words = in.tokens();
```

如果你的输入不是来自文件，请将 `InputStream` 封装为 `BufferedReader`：

```java
try (var reader = new BufferedReader(new InputStreamReader(url.openStream()))) {
    Stream<String> lines = reader.lines();
    ...
}
```

`BufferedReader` 为了效率会分块读取输入。（奇怪的是，基础读取器没有这个选项。）它有 `readLine` 方法读取单行，以及 `lines` 方法产生一个行流。

如果某个方法要求一个 `Reader` 而你想让它从文件读取，请调用 `Files.newBufferedReader(path, charset)`。

### 9.1.6 文本输出

要写入文本，使用 `Writer`。通过 `write` 方法，你可以写入字符串。你可以将任何输出流转换为 `Writer`：

```java
OutputStream outStream = ...;

var out = new OutputStreamWriter(outStream, charset);

out.write(str);
```

要获取文件的写入器，请使用：

```java
Writer out = Files.newBufferedWriter(path, charset);
```

#### PrintWriter

使用 `PrintWriter` 会更方便，它包含了 `print`、`println` 和 `printf`，这些方法你一直都在 `System.out` 中使用。通过这些方法，你可以打印数字并使用格式化输出。

如果你向文件写入，请如下构造一个 `PrintWriter`：

```java
var out = new PrintWriter(Files.newBufferedWriter(path, charset));
```

如果你向另一个流写入，请使用：

```java
var out = new PrintWriter(new OutputStreamWriter(outStream, charset));
```

> **注意**
>
> `System.out` 是 `PrintStream` 的实例，而不是 `PrintWriter`。这是 Java 极早期的遗留。然而，`print`、`println` 和 `printf` 方法在 `PrintStream` 和 `PrintWriter` 类中的工作方式相同，都使用字符编码将字符转换为字节。

如果你已经有一个要写入的字符串的文本，请调用：

```java
String content = ...;

Files.write(path, content.getBytes(charset));
```

或者：

```java
Files.write(path, lines, charset);
```

要向文件追加内容，请使用：

```java
Files.write(path, lines, charset, StandardOpenOption.APPEND);
```

### 9.1.7 读取和写入二进制数据

`DataInput` 接口声明了以下方法用于以二进制格式读取数字、字符、布尔值或字符串：

```java
byte readByte()
int readUnsignedByte()
char readChar()
short readShort()
int readUnsignedShort()
int readInt()
long readLong()
float readFloat()
double readDouble()
void readFully(byte[] b)
```

`DataOutput` 接口声明了相应的 `write` 方法。

> **注意**
>
> 这些方法以大端字节序读取和写入。

> **警告**
>
> 还有 `readUTF/writeUTF` 方法，它们使用“修改后的 UTF-8”格式。这些仅适用于 JVM。

#### 随机访问文件

`RandomAccessFile` 类允许你在文件的任何位置读取或写入数据。你可以以只读或读写结合的方式打开随机访问文件；通过在构造函数的第二个参数中使用字符串 `"r"`（读取访问）或 `"rw"`（读写访问）来指定选项。例如：

```java
var file = new RandomAccessFile(path.toString(), "rw");
```

随机访问文件有一个文件指针，它指示下一个要读取或写入的字节的位置。`seek` 方法将文件指针设置为文件中的任意字节位置。`seek` 的参数是一个位于 `0` 和文件长度之间的长整型（你可以通过 `length` 方法获取）。`getFilePointer` 方法返回文件指针当前的位置。

`RandomAccessFile` 类实现了 `DataInput` 和 `DataOutput` 接口。要从随机访问文件中读取和写入数字，可以使用你在上一节中看到过的 `readInt()`/`writeInt()` 等方法。例如：

```java
int value = file.readInt();

file.seek(file.getFilePointer() - 4);

file.writeInt(value + 1);
```



### 9.1.9. 内存映射文件

内存映射文件为随机访问提供了另一种非常高效的方法，非常适用于处理大文件。然而，其数据访问的 API 与输入/输出流的完全不同。首先，获取一个文件的`channel`：

```
FileChannel channel = FileChannel.open(path,
    StandardOpenOption.READ, StandardOpenOption.WRITE)
```

然后，将文件的一个区域（或者如果足够小，则是整个文件）映射到内存中：

```
ByteBuffer buffer = channel.map(FileChannel.MapMode.READ_WRITE,
    0, channel.size());
```

使用`get()`、`getInt()`、`getDouble()`等方法来读取值，并使用等效的`put`方法来写入值。

```
int offset = ...;

int value = buffer.getInt(offset);

buffer.put(offset, value + 1);
```

在某个时刻，且肯定是在通道关闭时，这些更改会被写回文件。

### 注意

默认情况下，读取和写入数字的方法使用大端（big-endian）字节序。你可以通过命令更改字节序：

```
buffer.order(ByteOrder.LITTLE_ENDIAN);
```

### 9.1.10. 文件锁

当多个同时执行的程序修改同一个文件时，它们需要进行某种通信，否则文件很容易损坏。文件锁可以解决这个问题。

假设你的应用程序保存了一个带有用户偏好的配置文件。如果用户启动了程序的两个实例，可能会发生它们都想同时写入配置文件的情况。在这种情况下，第一个实例应该锁定文件。当第二个实例发现文件被锁定时，它可以决定等待文件解锁，或者简单地跳过写入过程。要锁定文件，请调用`FileChannel`类的`lock()`或`tryLock()`方法。

```
FileChannel channel = FileChannel.open(path);

FileLock lock = channel.lock();
```

或者

```
FileLock lock = channel.tryLock();
```

第一次调用会阻塞直到锁可用。第二次调用会立即返回，返回锁或在锁不可用时返回`null`。在锁或通道关闭之前，文件一直保持锁定状态。最好使用 try-with-resources 语句：

```
try (FileLock lock = channel.lock()) {
    ...
}
```

### 9.2. 路径、文件和目录

你已经见过用于指定文件路径的`Path`对象。在接下来的章节中，你将看到如何操作这些对象，以及如何与文件和目录交互。

### 9.2.1. 路径

`Path`是目录名称的序列，可选地跟一个文件名。路径的第一个组件可以是根组件，例如`/`或`C:\`。允许的根组件取决于文件系统。以根组件开头的路径是**绝对的**（absolute）。否则，它是**相对的**（relative）。例如，在这里我们构建了一个绝对路径和一个相对路径。对于绝对路径，我们假设运行在类 Unix 文件系统上。

```
Path absolute = Path.of("/", "home", "cay");

Path relative = Path.of("myapp", "conf", "user.properties");
```

静态方法`Path.of()`接收一个或多个字符串，并使用默认文件系统的路径分隔符将它们连接（类 Unix 文件系统为`/`，Windows 为`\`）。然后它解析结果，如果结果在给定的文件系统中不是有效路径，则会抛出`InvalidPathException`。结果是一个`Path`对象。

你也可以向`Path.of()`方法提供一个带有分隔符的字符串：

```
Path homeDirectory = Path.of("/home/cay");
```

### 注意

`Path`对象不必对应于实际存在的文件。它仅仅是一个抽象的名称序列。要创建一个文件，先创建一个路径，然后调用方法来创建对应的文件——参见第 9.2.2 节。

组合或“解析”（resolve）路径是非常常见的操作。调用`p.resolve(q)`根据以下规则返回路径：

如果`q`是绝对的，则结果为`q`。

否则，根据文件系统的规则，结果是`p`后接`q`。

例如，假设你的应用程序需要相对于主目录找到其配置文件。以下是你可以组合路径的方法：

```
Path workPath = homeDirectory.resolve("myapp/work");

// 等同于 homeDirectory.resolve(Path.of("myapp/work"));
```

有一个便利方法`resolveSibling()`，它相对于路径的父路径进行解析，产生一个兄弟路径。例如，如果`workPath`是`/home/cay/myapp/work`，调用

```
Path tempPath = workPath.resolveSibling("temp");
```

将产生`/home/cay/myapp/temp`。

`resolve`的反操作是`relativize`。调用`p.relativize(q)`返回相对于`p`构建`q`的路径。例如：

```
Path relative = Path.of("myapp/work");
Path absolute = Path.of("/home/cay");
Path p = absolute.relativize(relative); // 示例逻辑
```

`normalize()`方法移除路径中的任何`.`或`..`组件。例如：

```
Path p = Path.of("/home/cay/../user/file");
Path normalized = p.normalize(); // /home/user/file
```

`toAbsolutePath()`方法如果路径不是绝对的，则返回绝对路径。例如：

```
Path relative = Path.of("home/cay");
Path absolute = relative.toAbsolutePath(); // /current/home/cay
```

`toFile()`方法返回此路径的`File`表示。例如：

```
Path p = Path.of("/home/cay/user.properties");
File f = p.toFile(); // user.properties
```

`getFileName()`方法返回文件名。例如：

```
Path.of("/home/cay").getFileName(); // cay
```

`getParent()`方法返回父目录。例如：

```
Path.of("/home/cay").getParent(); // /home
```

`getRoot()`方法返回根组件。例如：

```
Path.of("/home/cay").getRoot(); // /
```

`getNameCount()`方法返回路径中名称的数量。例如：

```
Path.of("/home/cay").getNameCount(); // 2
```

`getName(int index)`方法返回指定索引名称元素。例如：

```
Path.of("/home/cay/user.properties").getName(1); // cay
Path.of("/home/cay").getName(2); // 抛出 IndexOutOfBoundsException
```

`subpath(int begin, int end)`方法返回此路径的子路径。例如：

```
Path.of("/home/cay/user.properties").subpath(1, 3); // cay/user
```

`toString()`方法返回路径的字符串表示。例如：

```
Path.of("/home/cay").toString(); // /home/cay
```

`Path.of(String)`方法从字符串创建路径。例如：

```
Path.of("/home/cay");
```

### 9.2.2. 创建文件和目录

要创建一个目录，调用

```
Files.createDirectory(path);
```

路径中除最后一个组件以外的所有部分必须已经存在。要创建中间目录，请使用

```
Files.createDirectories(path);
```

你可以可以使用创建一个空文件：

```
Files.createFile(path);
```

如果文件已存在，则调用将抛出异常。存在检查和创建是原子的。

调用`Files.exists(path)`检查给定的文件或目录是否存在。要测试它是一个目录还是“普通”文件（即包含数据，而不是目录或符号链接），请调用`Files`类的静态方法`isDirectory`和`isRegularFile`。

在给定或系统特定位置创建临时文件或目录有便利方法：

```
Path tempFile = Files.createTempFile(dir, prefix, suffix);

Path tempFile = Files.createTempFile(prefix, suffix);

Path tempDir = Files.createTempDirectory(dir, prefix);

Path tempDir = Files.createTempDirectory(prefix);
```

在这里，`dir`是一个`Path`，而`prefix/suffix`是可能为空的字符串。例如，调用`Files.createTempFile(null, ".txt")`可能会返回类似`/tmp/ 1234405522364837194.txt`的路径。

#### 9.2.3. 复制、移动和删除文件

要将文件从一个位置复制到另一个位置，只需调用：

```
Files.copy(fromPath, toPath);
```

移动文件（即复制并删除原始文件），调用：

```
Files.move(fromPath, toPath);
```

你也可以使用此命令移动空目录。

如果目标存在，则复制或移动将失败。如果你想覆盖现有目标，请使用`REPLACE_EXISTING`选项。如果你想复制所有文件属性，请使用`COPY_ATTRIBUTES`选项。你可以这样同时提供两者：

```
Files.copy(fromPath, toPath, StandardCopyOption.REPLACE_EXISTING,

    StandardCopyOption.COPY_ATTRIBUTES);
```

你可以指定移动应该是原子性的。这样你就能确保要么移动成功完成，要么源文件依然存在。使用`ATOMIC_MOVE`选项：

```
Files.move(fromPath, toPath, StandardCopyOption.ATOMIC_MOVE);
```

参见 表 9.3 可文件操作可用选项摘要。

最后，要删除文件，只需调用：

```
Files.delete(path);
```

如果文件不存在，此方法会抛出异常，因此你可能更想使用：

```
boolean deleted = Files.deleteIfExists(path);
```

删除方法也可以用于删除空目录。

表 9.3：文件操作的标准选项

![images](img/09tab03.jpg)

#### 9.2.4. 访问目录条目

静态方法`Files.list`返回一个读取目录条目的`Stream<Path>`。该目录是懒性读取的，这使得高效处理包含海量条目的目录成为可能。

由于读取目录涉及需要关闭的系统资源，你应该使用 try-with-resources 块：

```
try (Stream<Path> entries = Files.list(pathToDirectory)) {

    ...

}
```

`list`方法不会进入子目录。要处理目录的所有后代节点，请使用`Files.walk`方法。

```
try (Stream<Path> entries = Files.walk(pathToRoot)) {

     // 包含所有后代节点，按深度优先顺序访问

}
```

以下是解压后的`src.zip`树的遍历示例：

```
java

java/nio

java/nio/DirectCharBufferU.java

java/nio/ByteBufferAsShortBufferRL.java

java/nio/MappedByteBuffer.java

...

java/nio/ByteBufferAsDoubleBufferB.java

java/nio/charset

java/nio/charset/CoderMalfunctionError.java

java/nio/charset/CharsetDecoder.java

java/nio/charset/UnsupportedCharsetException.java

java/nio/charset/spi

java/nio/charset/spi/CharsetProvider.java

java/nio/charset/StandardCharsets.java

java/nio/charset/Charset.java

...

java/nio/charset/CoderResult.java

java/nio/HeapFloatBufferR.java

...
```

如你所见，每当遍历到一个目录时，它会在继续处理兄弟节点之前被进入。

你可以通过调用`Files.walk(pathToRoot, depth)`来限制想要访问的树的深度。两个`walk`方法都有一个类型为`FileVisitOption...`的变长参数，但你只能提供一个选项：`FOLLOW_LINKS`用于跟随符号链接。

注意

如果你过滤了`walk`返回的路径，且你的过滤标准涉及存储在目录中的文件属性（例如大小、创建时间或类型（文件、目录、符号链接）），请使用`find`方法代替`walk`。调用该方法时，传入一个接受`path`和`BasicFileAttributes`对象的谓函数。其唯一的优势是效率。既然目录正在被读取，这些属性是就可以直接获取的。

此代码段使用`Files.walk`方法将一个目录复制到另一个目录：

```
Files.walk(source).forEach(p -> {

    try {
        Path q = target.resolve(source.relativize(p));

        if (Files.isDirectory(p))
            Files.createDirectory(q);

        else
            Files.copy(p, q);

    } catch (IOException ex) {

        throw new UncheckedIOException(ex);
    }

});
```

遗憾的是，你无法轻松使用`Files.walk`方法删除目录树，因为你需要在删除父目录之前先访问子。在这种情况下，请使用`walkFileTree`方法。它需要一个`FileVisitor`接口的实例。以下是文件访问器获取通知的情况：

1. 在处理目录之前：

```
FileVisitResult preVisitDirectory(T dir, IOException ex)
```

2. 当遇到文件时：

```
FileVisitResult visitFile(T path, BasicFileAttributes attrs)
```

3. 当`visitFile`方法中发生异常时：

```
FileVisitResult visitFileFailed(T path, IOException ex)
```

4. 在处理目录之后：

```
FileVisitResult postVisitDirectory(T dir, IOException ex)
```

在每种情况下，方法返回以下结果之一：

- `CONTINUE`

- `SKIP_SUBTREE`

- `SKIP_TREE`

- `SIBLINGS`

- `TERMINATE`

`SimpleVisitor`类实现了此接口，在每个点继续迭代并抛出任何异常。这里是你可以删除目录的方法：

```
Files.walkFileTree(root, new SimpleVisitor<Path>() {

    public FileVisitResult visitFile(Path file, BasicFileAttributes attrs) throws IOException {
        Files.delete(file);
        return FileVisitResult.CONTINUE;
    }

    public FileVisitResult postVisitDirectory(Path dir, IOException ex) throws IOException {
        if (ex != null) throw ex;
        Files.delete(dir);
        return FileVisitResult.CONTINUE;
    }

});
```

#### 9.2.5. ZIP 文件系统



`Paths`类查找默认文件系统——用户本地磁盘的文件。你可以拥有其他文件系统。其中有用的是 ZIP 文件系统。如果`zipname`是一个 ZIP 文件的名称，那么调用

```
FileSystem zipfs = FileSystems.newFileSystem(Path.of(zipname));
```

建立了一个包含存档中所有文件的文件系统。如果你知道它的名称，从中复制文件是容易的：

```
Files.copy(zipfs.getPath(sourceName), targetPath);
```

在这里，`zipfs.getPath`是任意文件系统的`Path.of`对应物。

要列出 ZIP 存档中的所有文件，遍历树：

```
Files.walk(zipfs.getPath("/")).forEach(p -> {

    Process p

});
```

创建一个新的 ZIP 文件需要多一点努力。以下是魔法咒语：

```
Path zipPath = Path.of("myfile.zip");

var uri = new URI("jar", zipPath.toUri().toString(), null);

    // 构建 URI jar:file://myfile.zip

try (FileSystem zipfs = FileSystems.newFileSystem(uri,
        Collections.singletonMap("create", "true"))) {

    // 要添加文件，将其复制到 ZIP 文件系统

    Files.copy(sourcePath, zipfs.getPath("/").resolve(targetPath));

}
```

注意

有一个处理 ZIP 存档的旧版 API，带有`ZipInputStream`和`ZipOutputStream`类，但它不像本节描述的那个样容易使用。

### 9.3. HTTP 连接

你可以通过使用`URL.getInputStream`方法返回的输入流从 URL 读取。然而，如果你想获取有关网络资源的更多信息，或者想写入数据，你就需要比`URL`类提供的更细致的流程控制。`URLConnection`类是在 HTTP 成为 Web 通用协议之前设计的。它支持许多协议，但其对 HTTP 的支持略显繁琐。在决定支持 HTTP/2 时，显然提供一个现代的客户端接口比重构现有的 API 更好。`HttpClient`提供了更方便的 API 和对 HTTP/2 支持。

在接下来的章节中，我将提供一个使用`HttpURLConnection`类的用法指南，然后给出该 API 的概述。

### 9.3.1. `URLConnection`和`HttpURLConnection`类

要使用`URLConnection`类，请遵循以下步骤：

1. 获取一个`URLConnection`对象：

```
URLConnection connection = url.openConnection();
```

对于 HTTP URL，返回的对象实际上是`HttpURLConnection`的实例。

2. 如果需要，设置请求属性：

```
connection.setRequestProperty("Accept-Charset", "UTF-8, ISO-8859-1");
```

如果一个键有多个值，请用逗号分隔。

3. 要向服务器发送数据，调用

```
connection.setDoOutput(true);

try (OutputStream out = connection.getOutputStream()) {

    // 向 out 写入

}
```

4. 如果你想读取响应头且你还没有调用`getOutputStream()`，请调用

```
connection.connect();
```

然后查询头字段信息：

```
Map<String, List<String>> headers = connection.getHeaderFields();
```

对于每个键，你将得到一个值列表，因为可能存在多个具有相同键的头字段。

5. 读取响应：

```
try (InputStream in = connection.getInputStream()) {

    // 从 in 读取

}
```

一个常见的用例是提交表单数据。在向 HTTP URL 写入数据时，`URLConnection`类会自动将内容类型设置为`application/x-www-form-urlencoded`，但你需要对键/值对进行编码：

```
URL url = ...;

URLConnection connection = url.openConnection();

connection.setDoOutput(true);

try (var out = new OutputStreamWriter(
        connection.getOutputStream(), StandardCharsets.UTF_8)) {

    Map<String, String> postData = ...;

    boolean first = true;

    for (Map.Entry<String, String> entry : postData.entrySet()) {

        if (first) first = false;

        else out.write("&");

        out.write(URLEncoder.encode(entry.getKey(), "UTF-8"));

        out.write("=");

        out.write(URLEncoder.encode(entry.getValue(), "UTF-8"));

    }
}

try (InputStream in = connection.getInputStream()) {

    ...

}
```

### 9.3.2. HTTP Client API

HTTP API 提供了另一种连接到网络服务器的机制，它比具有那套繁琐阶段设置的`URLConnection`类更简单。更重要的是，该实现支持 HTTP/2。

`HttpClient`可以发布请求并接收响应。你可以通过调用以下方法获取客户端：

```
HttpClient client = HttpClient.newHttpClient();
```

或者，如果你需要配置客户端，请使用如下构建器 API：

```
HttpClient client = HttpClient.newBuilder()
    .followRedirects(HttpClient.Redirect.ALWAYS)
    .build();
```

也就是说，你获得一个构建器，调用方法来自定义将要构建的对象，然后调用`build`方法来完成构建过程。这是构造不可变对象的常用模式。

按照相同的模式来构建请求。这里有一个`GET`请求：

```
HttpRequest request = HttpRequest.newBuilder()
    .uri(new URI("https://horstmann.com"))
    .GET()
    .build();
```

URI 是“统一资源标识符”，在使用 HTTP 时，它等同于 URL。然而，在 Java 中，`URL`类拥有用于实际打开 URL 连接的方法，而`URI`类只关注语法（方案、主机、端口、路径、查询、片段等）。

在发送请求时，你必须告诉客户端如何处理响应。如果你只想获取字符串形式的正文，请使用`HttpResponse.BodyHandlers.ofString()`发送请求，如下：

```
HttpResponse<String> response
    = client.send(request, HttpResponse.BodyHandlers.ofString());
```

`HttpResponse`类是一个模板，其类型表示正文的类型。你只需即可获取响应正文字符串：

```
String bodyString = response.body();
```

还有其他响应正文处理器可以将响应获取为字节数组或文件。人们希望 JDK 最终能支持 JSON 并提供一个 JSON 处理器。

对于`POST`请求，你同样需要一个“正文发布者”，将请求数据转换为正在发布的数据。有针对字符串、字节数组和文件的发布者。同样，人们希望库的设计者能意识到大多数`POST`请求涉及表单数据或 JSON 对象这一现实，并提供相应的发布者。

在此期间，要发送表单 POST，你需要对请求数据进行 URL 编码，就像前一节一样。

```
Map<String, String> postData = ...;

boolean first = true;

var body = new StringBuilder();

for (Map.Entry<String, String> entry : postData.entrySet()) {

        if (first) first = false;

        else out.write("&");

        out.write(URLEncoder.encode(entry.getKey(), "UTF-8"));

        out.write("=");

        out.write(URLEncoder.encode(entry.getValue(), "UTF-8"));

    }

HttpRequest request = HttpRequest.newBuilder()
    .uri(new URI("https://horstmann.com"))
    .header("Content-Type", "application/x-www-form-urlencoded")
    .POST(HttpRequest.BodyPublishers.ofString(body.toString()))
    .build();
```

注意，与`URLConnection`类不同，你需要指定内容类型。

`HttpResponse`对象还可以获取状态码和响应头。

```
int status = response.statusCode();

HttpHeaders responseHeaders = response.headers();
```

你可以将`HttpHeaders`对象转换为映射：

```
Map<String, List<String>> headerMap = responseHeaders.map();
```

映射的值是列表，因为在 HTTP 中每个键可以有多个值。

如果你只需要某个键的值，并且知道没有多个值，可以调用`firstValue`方法：

```
Optional<String> lastModified = headerMap.firstValue("Last-Modified");
```

如果没有提供，则返回空 Optional。

提示

要启用`HttpClient`的日志，请在 JDK 的`net.properties`中添加此行：

```
jdk.httpclient.HttpClient.log=all
```

除了`all`，你可以指定一个由逗号分隔的`headers`, `requests`, `content`, `errors`, `ssl`, `trace`和`frames`组成的列表，可选跟随`:control`, `:data`, `:window`或`:all`。不要使用空格。

将命名为`jdk.httpclient.HttpClient`的日志级别设置为`INFO`，例如通过在 JDK 的`logging.properties`文件中添加此行：

```
jdk.httpclient.HttpClient.level=INFO
```

### 9.4. 正则表达式

正则表达式指定字符串模式。当你需要定位匹配模式的字符串时，可以使用它们。例如，假设你想在 HTML 文件中查找链接。你需要寻找模式为`<a href="...">`的字符串。但是——可能有额外的空格，或者 URL 可能被单引号包裹。正则表达式提供了一种精确的语法来指定哪些字符序列是合法匹配。

在接下来的章节中，你将看到 Java API 使用的正则表达式语法，以及如何使用正则表达式。

#### 9.4.1. 正则表达式语法

在正则表达式中，字符表示自身，除非它是保留字符之一

```
. * + ? { | ( ) [ \ ^ $
```

例如，正则表达式`Java`仅匹配字符串`Java`。

符号`.`匹配任意单个字符。例如，`.a.a`匹配`Java`和`data`。

`*`符号表示前面的结构可以重复 0 次或多次；对于`+`，则表示重复 1 次或多次。后缀`?`表示该结构是可选的（0 次或 1 次）。例如，`be+s?`匹配`be`、`bee`和`bees`。你可以使用`{ }`指定其他重复次数（参见表 9.4）。

`|`表示一种备选方案：`.(oo|ee)f`匹配`beef`或`woof`。注意括号——如果没有括号，`.oo|eef`将成为`.oo`和`eef`之间的备选关系。括号也用于分组——参见第 9.4.4 节。

*字符类*是一组包含在括号内的字符备选集合，例如`[Jj]`、`[0-9]`、`[A-Za-z]`或`[⁰-9]`。在字符类内部，`-`表示一个范围（所有 Unicode 值落在两个边界之间的字符）。然而，如果`-`是字符类中的第一个或最后一个字符，则则表示其本身。`^`作为字符类中的第一个字符时，表示补集（除指定字符以外的所有字符）。

有许多*预定义字符类*，例如`\d`（数字）或`\p{Sc}`（Unicode 货币符号）。参见 . 和 。

字符`^`和`$`匹配输入的开始和结束。

如果你需要匹配字面量`. * + ? { | ( ) [ \ ^ $`，请在它们前面加一个反斜杠`\`。在字符类内部，你只需要转义`[`和`\`，只要你小心`] - ^`的位置即可。例如，`[]^-]`是一个包含这三个字符的类。

或者，使用`\Q`和`\E`包围字符串。例如，`\(\$0\.99\)`和`\Q($0.99)\E`均匹配字符串`($0.99)`。

### 提示

如果你有一个可能包含正则表达式语法中许多特殊字符的字符串，可以通过调用`Parse.quote(str)`对它们全部进行转义。这只是简单将字符串用`\Q`和`\E`包围起来，但它处理了`str`可能包含`\E`的特殊情况。

### 表 9.4: 正则表达式语法

![images](img/09tab04.jpg)![images](img/09tab04a.jpg)![images](img/09tab04b.jpg)

### 表 9.5: 预定义字符类 \p{...}

![images](img/09tab05.jpg)

#### 9.4.2 测试匹配

通常，使用正则表达式有两种方法：你想测试字符串是否符合该表达式，或者你想在字符串中找到表达式的所有匹配项。

在第一种情况下，直接使用静态`matches`方法：

```
String regex = "[+-]?\\d+";
CharSequence input = ...;

if (Pattern.matches(regex, input)) {
    ...
}
```

如果你需要多次使用同一个正则表达式，编译它会更高效。然后，为每个输入创建一个`Matcher`：

```
Pattern pattern = Pattern.compile(regex);
Matcher matcher = pattern.matcher(input);

if (matcher.matches()) ...
```

如果匹配成功，你可以获取匹配组的位置——参见第 9.4 节。

如果你想测试输入是否*包含*某个匹配项，请改用`find`方法：

```
if (matcher.find()) ...
```

你可以将模式转换为谓词：

```
Pattern digits = Pattern.compile("[0-9]+");
List<String> strings = List.of("December", "31st", "1999");
List<String> matchingStrings = strings.stream()
    .filter(digits.asMatchPredicate())
    .toList(); // ["1999"]
```

结果包含了匹配正则表达式的字符串。

使用`asPredicate`方法测试字符串是否包含匹配项：

```
List<String> sringsContainingMatch = strings.stream()
    .filter(digits.asPredicate())
    .toList(); // ["31st", "1999"]
```

#### 9.4.3 查找所有匹配

在本节中，我们考虑正则表达式的另一个常见用例——在输入中查找所有匹配。使用此循环：

```
String input = ...;
Matcher matcher = pattern.matcher(input);

while (matcher.find()) {
    String match = matcher.group();
    int matchStart = matcher.start();
    int matchEnd = matcher.end();
    ...
}
```



通过这种方式，你可以逐个处理每个匹配。如代码片段所示，你可以获取匹配字符串及其在输入字符串中的位置。

更优雅的方法是调用`results`方法获取`Stream<MatchResult>`。`MatchResult`接口拥有`group`、`start`和`end`方法，与`Matcher`一样。

```java
String result = input.replaceAll("\\s*,\\s*", ",");
```

替换字符串可以包含组索引`$n`或名称`${name}`。它们会被替换为相应捕获组的内容。

```java
String result = "3:45".replaceAll(
    "(\\d{1,2}):(?<minutes>\\d{2})",
    "$1 hours and ${minutes} minutes");

    // 将 result 设置为 "3 hours and 45 minutes"
```

你可以使用`\`来转义替换字符串中的`$`和`\`，或者调用`Matcher.quoteReplacement`便利方法：

```java
matcher.replaceAll(Matcher.quoteReplacement(str))
```

如果你想执行比拼接组匹配项更复杂的操作，可以提供一个替换函数而不是替换字符串。该函数接受一个`MatchResult`并返回一个字符串。例如，在这里我们将所有长度至少为四个字母的单词替换为大写版本：

```java
String result = Pattern.compile("\\pL{4,}")
    .matcher("Mary had a little lamb")
    .replaceAll(m -> m.group().toUpperCase());

    // 输出 "MARY had a LITTLE LAMB"
```

`replaceFirst`方法只替换模式的第一次出现的内容。

### 9.4.7. 标志（Flags）

几个标志可以改变正则表达式的行为。你可以在编译模式时指定它们：

```java
Pattern pattern = Pattern.compile(regex,
    Pattern.CASE_INSENSITIVE | Pattern.UNICODE_CHARACTER_CLASS);
```

或者你可以在模式内部指定它们：

```java
String regex = "(?iU:expression)";
```

以下是这些标志：

- ![Images](img/sq.jpg) `Pattern.CASE_INSENSITIVE`或`i`：忽略字母大小写匹配字符。默认情况下，此标志只考虑美国 ASCII 字符。
- ![Images](img/sq.jpg) `Pattern.UNICODE_CASE`或`u`：与`CASE_INSENSITIVE`结合使用时，使用 Unicode 大小写进行匹配。
- ![Images](img/sq.jpg) `Pattern.UNICODE_CHARACTER_CLASS`或`U`：选择 Unicode 字符类而非 POSIX。隐含`UNICODE_CASE`。
- ![Images](img/sq.jpg) `Pattern.MULTILINE`或`m`：使`^`和`$`匹配行的开头和结尾，而不是整个输入。
- ![Images](img/sq.jpg) `Pattern.UNIX_LINES`或`d`：在多行模式下匹配`^`和`$`时，只有`\n`是行终止符。
- ![Images](img/sq.jpg) `Pattern.DOTALL`或`s`：使`.`符号匹配所有字符，包括行终止符。
- ![Images](img/sq.jpg) `Pattern.COMMENTS`或`x`：忽略空白字符和注释（从`#`到行尾）。
- ![Images](img/sq.jpg) `Pattern.LITERAL`：模式按字面意思处理，必须精确匹配，但可能不考虑字母大小写。
- ![Images](img/sq.jpg) `Pattern.CANON_EQ`：考虑 Unicode 字符的规范等效性。例如，`u`后跟`¨`（变音符号）会匹配`ü`。

最后两个标志不能在正则表达式内部指定。

### 9.5. 序列化（Serialization）

在接下来的章节中，你将学习对象序列化——这是一种将对象转换为一组字节的机制，以便将其发送到其他地方或存储在磁盘上，并从这些字节恢复对象。

序列化是分布式处理的一个重要工具，在分布式处理中，对象从一台虚拟机传输到另一台虚拟机。它还用于故障转移和负载均衡，此时被序列化的对象可以移动到另一台服务器。如果你处理服务器端软件，通常需要为类启用序列化。接下来的章节将告诉该如何做。

#### 9.5.1. `Serializable`接口

为了让对象能够被序列化（即转换为一组字节），它必须是实现`Serializable`接口的类的实例。这是一个没有方法的标记接口，类似于你在第 4 章中看到的`Cloneable`接口。

例如，要使`Employee`对象变为可序列化，需要将该类声明为：

```java
public class Employee implements Serializable {
    private String name;
    private double salary;
    ...
}
```

如果类所有的实例变量都是原始类型或`enum`类型，或者包含指向可序列化对象的引用，那么该类实现`Serializable`接口是恰当的。标准库中的许多类都是可序列化的。你在第 7 章看到的数组和集合类只要其元素是可序列化的，就是可序列化的。

对于`Employee`类，实际上对于大多数类来说，这不是问题。在接下来的章节中，你将看到需要额外帮助时该做什么。

要序列化对象，你需要一个`ObjectOutputStream`，它通过另一个接收实际字节的`OutputStream`构建。

```java
var out = new ObjectOutputStream(Files.newOutputStream(path));
```

现在调用`writeObject`方法：

```java
var peter = new Employee("Peter", 90000);
var paul = new Manager("Paul", 180000);
out.writeObject(peter);
out.writeObject(paul);
```

要读回对象，构造一个`ObjectInputStream`：

```java
var in = new ObjectInputStream(Files.newInputStream(path));
```

使用`readObject`获取对象：

```java
var e1 = (Employee) in.readObject();
var e2 = (Employee) in.readObject();
```

当对象被写入时，类名和实例变量的值被保存。如果实例变量是原始类型，它会被保存。如果是对象，则再次通过`writeObject`写入。

当读入时，过程反过来。类名和实例变量的值被读取，对象被恢复。

这里有一个陷阱。假设有两个引用同一个对象。假设每个员工都有老板：

```java
var peter = new Employee("Peter", 90000);
var paul = new Manager("Barney", 105000);
var mary = new Manager("Mary", 180000);
peter.setBoss(mary);
paul.setBoss(mary);
out.writeObject(peter);
out.writeObject(paul);
```

读回这两个对象时，它们需要同一个老板，而不是两个相同但不同的对象。为了实现这一点，每个对象在保存时获得一个*序列号*。当你将对象引用传递给`writeObject`时，`ObjectOutputStream`会检查该引用是否已经写入。如果是，它只写入序列号，而不重复对象的内容。

同样，`ObjectInputStream`记住它遇到的所有对象。当读入重复对象的引用时，它简单地返回之前读取的对象引用。

#### 9.5.2. 瞬态变量（Transient Instance Variables）

某些实例变量不应该被序列化——例如在恢复对象时没有意义的数据库连接。此外，当对象缓存值时，丢弃缓存并重新计算可能比存储它更好。

要防止实例变量被序列化，只需为其标记`transient`修饰符。如果实例变量持有不可序列化类的实例，请务必将其标记为`transient`。瞬态变量在序列化时会被跳过。

**注意**

如果可序列化类的父类不可序列化，则它必须有一个可访问的无参构造函数。考虑这个例子：

```java
class Person // 不序列化

class Employee extends Person implements Serializable
```

当反序列化`Employee`对象时，它的实例变量从对象输入流读取，但`Person`的实例变量由`Person`构造函数设置。

#### 9.5.3. `readObject`和`writeObject`方法

在少数情况下，你需要调整序列化机制。序列化类可以通过定义签名如下的方法，为默认的读写行为添加任何所需的操作：

```java
@Serial private void readObject(ObjectInputStream in)
    throws IOException, ClassNotFoundException

@Serial private void writeObject(ObjectOutputStream out)
    throws IOException
```

随后，对象头将像通常一样继续写入，但实例变量字段不再被自动序列化。相反，将调用这些方法。

请注意`@Serial`注解。用于调整序列化的方法不属于接口。因此，你不能使用`@Override`注解来让编译器检查方法声明。`@Serial`注解旨在对序列化方法启用相同的检查。在 Java 17 之前，`javac`编译器并不进行这种检查，但在未来可能会发生。某些 IDE 会检查该注解。

`java.awt.geom`包中的许多类（例如`Point2D.Double`）不是可序列化的。现在，假设你想序列化一个名为`LabeledPoint`的类，它存储了一个`String`和一个`Point2D.Double`。首先，你需要将`Point2D.Double`字段标记为`transient`，以避免`NotSerializableException`。

```java
public class LabeledPoint implements Serializable {
    private String label;
    private transient Point2D.Double point;
    . . .
}
```

在`writeObject`方法中，首先通过调用`defaultWriteObject`方法写入对象描述符和`String`字段`label`。这是`ObjectOutputStream`类的一个特殊方法，只能在序列化类的`writeObject`方法内部调用。然后，我们使用标准的`DataOutput`调用写入点坐标。

```java
private void writeObject(ObjectOutputStream out) throws IOException {
    out.defaultWriteObject();
    out.writeDouble(point.getX());
    out.writeDouble(point.getY());
}
```

在`readObject`方法中，我们反转该过程：

```java
private void readObject(ObjectInputStream in)
        throws IOException, ClassNotFoundException {
    in.defaultReadObject();
    double x = in.readDouble();
    double y = in.readDouble();
    point = new Point2D.Double(x, y);
}
```

另一个示例是`HashSet`类，它提供了自己的`readObject`和`writeObject`方法。`writeObject`方法并没有保存哈希表的内部结构，而是简单保存了容量、负载因子、大小和元素。`readObject`方法读回容量和负载因子，构建一个新表并插入元素。

`readObject`和`writeObject`方法只需要保存和加载它们的数据。它们不关心父类数据或任何其他类信息。

`Date`类使用了这种方法。它的`writeObject`方法保存了自“纪元”（1970 年 1 月 1 日）以来的毫秒数。缓存日历的数据结构没有被保存。由于由于原因，第 0.0.0 节中的序列化`Date`实例由一个透明数据块组成。

### 注意

就像构造函数一样，`readObject`方法操作的是部分初始化的对象。如果你在`readObject`内部调用了被子类重写的非 final 方法，它可能会访问未初始化的数据。

#### Note

如果可序列化类定义了一个字段：

```java
@Serial private static final ObjectStreamField[] serialPersistentFields
```

那么序列化将使用这些字段描述符，而不是非 transient 非静态字段。还有一个 API 可以在序列化之前设置字段值，或在反序列化之后读取它们。这对于在类演进后保留遗留布局非常有用。例如，`BigDecimal`类使用这种机制来序列化其实例，其格式不再反映实例字段。

#### 9.5.4. `readExternal`和`writeExternal`方法

与其让序列化机制保存和恢复对象数据，不如类可以定义它自己的机制。要做到这一点，类必须实现`Externalizable`接口。这又要求它定义两个方法：

```java
public void readExternal(ObjectInputStream in)
      throws IOException

public void writeExternal(ObjectOutputStream out)
      throws IOException
```

与`readObject`和`writeObject`方法不同，这些方法完全负责保存和恢复整个对象，*包括父类数据*。在写入对象时，序列化机制仅在输出流中记录对象的类。在读取一个可外部化（externalizable）对象时，对象输入流会使用无参构造函数创建一个对象，然后调用`readExternal`方法。

你可以加密数据，或者使用比序列化格式更高效的格式。

在这个示例中，`LabeledPixel`类扩展了可序列化的`Point`类，但它接管了类及其父类的序列化。对象的字段没有存储在标准的序列化格式中。相反，数据被放置在一个透明数据块中。

```java
public class LabeledPixel extends Point implements Externalizable {
    private String label;

    public LabeledPixel() {} // externalizable 类需要

    @Override public void writeExternal(ObjectOutput out)
            throws IOException {
        out.writeInt((int) getX());
        out.writeInt((int) getY());
        out.writeUTF(label);
    }

    @Override public void readExternal(ObjectInput in)
            throws IOException, ClassNotFoundException {
        int x = in.readInt();
        int y = in.readInt();
        setLocation(x, y);
        label = in.readUTF();
    }

    . . .
}
```

#### Note

`readExternal`和`writeExternal`方法不应该带有`@Serial`注解。由于它们定义在`Externalizable`接口中，你可以简单地为它们加上`@Override`注解。

### 注意

与私有的且只能由序列化机制调用的`readObject`和`writeObject`方法不同，`readExternal`和`writeExternal`方法是公共的。特别是，`readExternal`允许修改现有对象的状态。

#### 9.5.5. `readResolve`和`writeReplace`方法

我们认为对象只能通过构造函数进行构造。然而，反序列化的对象*并不是被构造的*。它的实例变量仅仅是从对象流中恢复的。

如果构造函数强制执行某些条件，就会出现问题。例如，单例对象的实现可能使得构造函数只能被调用一次。另一个例子是，数据库实体的构造可以确保它们始终来自受管理的实例池。



你不应该为单例实现自己的机制。如果你需要一个单例，请定义一个包含一个实例的枚举类型，该实例按照惯例称为`INSTANCE`。

```java
public enum PersonDatabase {

    INSTANCE;

    public Person findById(int id) { ... }

    ...

}
```

这之所以有效，是因为`enum`保证被正确地反序列化。

现在，假设你处于一种罕见的情况，想要控制每个反序列化实例的标识。例如，假设`Person`类希望在反序列化时从数据库恢复其实例。那么，不要序列化对象本身，而是序列化一个可以定位或构造对象的代理。提供一个`writeReplace`方法来返回代理对象：

```java
public class Person implements Serializable {

     private int id;

     // 其他实例变量

     ...

     @Serial private Object writeReplace() {

         return new PersonProxy(id);
     }

}
```

当`Person`对象被序列化时，它的没有任何实例变量都没有被保存。相反，会调用`writeReplace`方法，并且*返回值*会被序列化并写入流中。

代理类需要实现一个`readResolve`方法以产生一个`Person`实例：

```java
class PersonProxy implements Serializable {

    private int id;

    public PersonProxy(int id) {
        this.id = id;
    }

    @Serial private Object readResolve() {
        return PersonDatabase.INSTANCE.findById(id);
    }
}
```

当`readObject`方法在`ObjectInputStream`中找到`PersonProxy`时，它会反序列化该代理，调用其`readResolve`方法并返回结果。

### 注意

与`readObject`和`writeObject`方法不同，`readResolve`和`writeReplace`方法不需要是私有的。

### 注意

对于枚举（enumerations）和记录（records），`readObject/writeObject`或`readExternal/writeExternal`方法不用于序列化。对于记录但不对于枚举，将使用`writeReplace`方法。

### 9.5.6. 版本控制

序列化旨在将对象从一个虚拟机发送到另一个虚拟机，或用于状态短期持久化。如果你将序列化用于长期持久化，或者在序列化和反序列化之间类可能会发生变化，你需要考虑当类演进时会发生什么。版本 2 能读取旧数据吗？仍在使用版本 1 的用户能读取新版本产生的文件吗？

序列化机制支持简单的版本控制方案。当对象被序列化时，类名和其`serialVersionUID`都会被写入对象流。该唯一标识符由实现者通过定义实例变量来分配：

```java
@Serial private static final long serialVersionUID = 1L; // Version 1
```

当类以不兼容的方式进行演进时，实现者应该更改 UID。每当反序列化对象的 UID 不匹配时，`readObject`方法就会抛出`InvalidClassException`。

如果`serialVersionUID`匹配，即使实现发生了发生了变化，反序列化也会继续。只要名称和类型匹配，被读取的对象的每个非瞬态（nontransient）实例变量都将被设置为序列化状态中的值。所有其他实例变量都将设置为默认值：对象引用为`null`，数字为`0`，`boolean`值为`false`。序列化状态中在待读对象不存在的任何内容都会被忽略。

这个过程安全吗？只有类的实现者才能确定。如果是安全的，那么实现者应该给新版本的类分配与旧版本相同的`serialVersionUID`。

如果你没有分配`serialVersionUID`，系统将通过对实例变量、方法和父类型的规范描述进行哈希自动生成一个。你可以使用`serialver`工具查看哈希值。命令：

```
serialver ch09.sec05.Employee
```

显示：

```java
private static final long serialVersionUID = -4932578720821218323L;
```

当类的实现发生变化时，哈希值发生变化的概率非常高。

如果你需要能够读取旧版本的实例，并且你确定这样做是安全的，请在旧版本的类上运行`serialver`并将结果添加到新版本中。

### 注意

如果你想实现更复杂的版本控制方案，可以重写`readObject`方法并调用`readFields`方法，而不是`defaultReadObject`方法。你将获得流中找到的所有字段的描述，并可以对它们进行任何你想要的操作。

### 注意

枚举和记录忽略`serialVersionUID`字段。枚举始终拥有为`0L`的`serialVersionUID`。你可以声明记录的`serialVersionUID`，但反序列化时这些 ID 不需要匹配。

### 注意

在本节中，你看到了当读取器的类版本包含对象流中不存在的实例变量时发生的情况。在类演进过程中，也可能添加父类。这时，使用新版本的读取器可能会读取一个对象流，其中父类的实例变量未被设置。默认情况下，这些字段被设置为它们的零/`false`/`null`默认值。这可能导致父类处于不安全状态。父类可以通过定义一个初始化方法来防止该问题：

```java
@Serial private void readObjectNoData() throws ObjectStreamException
```

该方法应该设置与无参构造函数相同的状态，或者抛出`InvalidObjectException`。它只在读取的对象流包含一个缺少父类数据的子类实例这种“不寻常”的情况下才被调用。

### 9.5.7. 反序列化与安全

在可序列化类的反序列化期间，对象的创建不会调用该类的任何构造函数。即使该类有一个无参构造函数，它也不会被使用。字段值直接从对象输入流的值中设置。

### 注意

对于可序列化的`records`，反序列化会调用规范构造函数，并从对象输入流传递组件的值。（作为结果，记录中的循环引用不会被恢复。）

绕过构造过程是一个安全风险。攻击者可以伪造字节来描述一个永远无法构造的无效对象。例如，假设`Employee`构造函数在带有负工资调用时会抛出异常。我们希望认为这意味着没有任何`Employee`对象可以具有负工资。但检查序列化对象的字节并修改其中一些字节并不困难。通过这种方式，人们可以为一个具有负工资的员工伪造字节，然后对其进行反序列化。

可序列化类可以可选地实现`ObjectInputValidation`接口并定义`validateObject`方法以检查其对象是否被正确反序列化。例如，`Employee`类可以检查工资是否为负：

```java
public void validateObject() throws InvalidObjectException

{
   System.out.println("validateObject");
   if (salary < 0)
      throw new InvalidObjectException("salary < 0");
}
```

遗憾的是，该方法不会被自动调用。为了调用它，你必须提供以下方法：

```java
@Serial private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException {
   in.registerValidation(this, 0);
   in.defaultReadObject();
}
```

该对象会被调度进行验证，当该对象及其所有依赖对象都加载后，就会调用`validateObject`方法。第二个参数允许你指定优先级。优先级较高的验证请求先执行。

还有其他安全风险。攻击者可以创建消耗足够资源导致虚拟机崩溃的数据结构。更险的是，类路径上的任何类都可以被反序列化。黑客们一直在狡猾地组合“getget 链”（gadget chains），即各种工具类中利用反射的操作序列，最终调用带有他们选择的字符串的`Runtime.exec`等方法。任何通过网络连接从不可信源接收序列化数据的应用程序都会受到此类攻击。例如，某些服务器序列化会话数据并反序列化 HTTP Session cookie 返回的任何数据。

你应该避免反序列化来自不可信源的任意数据。在会话数据的示例中，服务器应对数据进行签名，仅对签名有效的数据进行反序列化。

*序列化过滤器*（serialization filter）机制可以增强应用程序免受此类攻击。过滤器可以看到被反序列化的类名以及若干指标（流大小、数组大小、引用总数、最引用链）。基于这些数据，可以中止反序列化。

在最简单的形式，你提供一个描述有效和无效类的模式。例如，如果你如下启动我们的示例序列化演示：

```
java -Djdk.serialFilter='serial.*;java.**;!*' serial.ObjectStreamTest
```

随后对象将被加载。该过滤器允许`serial`包中的所有类以及所有包名以`java`开头的类，但不再允许其他任何类。如果你不允许`java.**`，或者至少不允许`java.util.Date`，反序列化就会失败。

你可以将过滤器模式放入配置文件，并为不同的用途指定多个过滤器。你也可以实现自己的过滤器。详情请参阅[`https://docs.oracle.com/en/java/javase/17/core/serialization-filtering1.html`](https://docs.oracle.com/en/java/javase/17/core/serialization-filtering1.html)。

### 练习

1. 编写一个实用方法，将整个`InputStream`复制到`OutputStream`，且不使用任何临时文件。提供另一种解决方案，不使用循环，使用`Files`类的操作和临时文件。

2. 编写一个程序读取文本文件并生成一个同名但扩展名为`.toc`的文件，该文件包含输入文件中所有单词的字母顺序列表，以及每个单词出现的行号列表。假设文件编码为 UTF-8。

3. 编写一个程序读取一个包含文本的文件，并假设大多数单词是英语，猜测其编码是`ASCII`、`ISO 8859-1`、`UTF-8`还是`UTF-16`；如果是后者，使用的是哪种字节序。

4. 使用`Scanner`很方便，但比使用`BufferedReader`慢一点。在大文件中逐行读取并统计输入行数，分别使用 (a) `Scanner`和`hasNextLine/nextLine`，(b) `BufferedReader`和`readLine$，(c) `BufferedReader`和`lines`。哪种最快？哪种最方便？

5. 当具有部分 Unicode 覆盖的`Charset`编码器无法编码某个字符时，它会替换为默认值——通常（并非总是）是编码`"?"`。找到所有支持编码的可用字符集的替换字符。使用`newEncoder`方法获取编码器，并调用其`replacement`方法获取替换字符。对于每个唯一结果，报告使用该结果的字符集规范。

6. 用于未压缩图像文件的 BMP 文件格式文档详尽且简单。使用随机访问，编写一个程序在原地反射每行像素，而不写入新文件。

7. 查找`MessageDigest`类的 API 文档并编写一个程序计算文件的 SHA-512 摘要。使用`update`方法向`MessageDigest`对象传递字节块，然后显示调用`digest`的结果。验证你的程序产生的结果与`sha512sum`工具产生的结果相同。

8. 编写一个实用方法，生成一个包含目录及其子目录下所有文件的 ZIP 文件。

9. 使用`URLConnection`类从一个受“basic”认证保护的 Web 页面读取数据。拼接用户名、冒号和密码，并计算 Base64 编码：

```
String input = username + ":" + password;

String encoding = Base64.getEncoder().encodeToString(
    input.getBytes(StandardCharsets.UTF_8));
```

将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

10. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

11. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

12. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

13. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

14. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

15. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

16. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

17. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

18. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

19. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

20. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

21. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

22. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

23. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

24. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

25. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

26. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

27. 将 HTTP 请求头`Authorization`设置为值`"Basic " + encoding`。然后读取并打印页面。

（注：输入文本包含大量的重复和碎片化内容，已根据指令予以保留。）

## 并发编程

Java 是最早内置并发编程支持的主流语言之一。在那个时代，大多数计算机都有多个处理器，程序员们担心如何让它们保持忙碌。在本章中，你将学习如何将计算划分为并发任务以及如何执行它们。我的重点是应用程序程序员，而不是系统程序员。出于这个原因，我安排了本章信息的顺序，以便尽可能先向你展示应该使用的工具。我将在本章后部分介绍底层结构。

### 10.1. 并发任务

当你设计并发程序时，需要考虑可以一起运行的任务。在接下来的章节中，你将看到如何安全地执行它们。

#### 10.1.1. 运行任务

在 Java 中，`Runnable`接口描述你想运行的任务，可能与其他任务并发运行。

```
public interface Runnable {

    void run();

}
```

与所有方法一样，`run`方法在`thread`中执行。`thread`是一种用于执行指令序列的机制，通常由操作系统提供。多个线程通过使用单独处理器或在同一处理器上使用不同的时间片来并发运行。

如果你想在单独线程中执行`Runnable`，可以仅为该`Runnable`启动一个线程，你将在第 10.8.1 节中看到如何做到这一点。但在实践中，任务和线程之间建立一对一的关系通常是没有意义的。当任务是短命的时，你希望在同一个线程上运行许多任务，这样就不会浪费启动线程所需的时间。当你的任务是计算密集型的时，你只希望每个处理器一个线程，而不是每个任务一个线程，以避免在线程之间切换的开销。在设计任务时，你不希望考虑这些问题，因此最好将任务和任务调度分离。

在 Java 并发库中，`executor service`负责调度和执行任务，并选择运行这些任务的线程。

```
Runnable task = () -> { ... };

ExecutorService executor = ...;

executor.execute(task);
```

`Executors`类具有用于具有不同调度策略的执行服务的工厂方法。调用



`exec = Executors.newCachedThreadPool();`

会产生一个针对具有许多短命任务或大部分时间都在等待的程序优化的执行服务。如果可能，每个任务都会在空闲线程上执行，但如果所有线程都忙，将分配一个新线程。并发线程的数量没有限制。长时间空闲的线程会被终止。

调用

`exec = Executors.newFixedThreadPool(nthreads);`

会产生一个具有固定数量线程的池。当你提交任务时，它会被放入队列，直到某个线程可用。这对于计算密集型任务或限制服务的资源消耗来说是一个很好的选择。你可以根据可用处理器的数量推导出线程数，获取方法为

`int processors = Runtime.getRuntime().availableProcessors();`

现在，去运行书中配套代码中的并发演示程序吧。它并发运行了两个任务。

```
public static void main(String[] args) {

    Runnable hellos = () -> {

        for (int i = 1; i <= 1000; i++)

            System.out.println("Hello " + i);

    };

    Runnable goodbyes = () -> {

        for (int i = 1; i <= 1000; i++)

            System.out.println("Goodbye " + i);

    };

    ExecutorService executor = Executors.newCachedThreadPool();

    executor.execute(hellos);

    executor.execute(goodbyes);

}
```

运行程序几次，查看输出是如何交织的。

```
Goodbye 1

...

Goodbye 871

Goodbye 872

Hello 806

Goodbye 873

Goodbye 874

Goodbye 875

Goodbye 876

Goodbye 877

Goodbye 878

Goodbye 879

Goodbye 880

Goodbye 881

Hello 807

Goodbye 882

...

Hello 1000
```

**注意**

你可能会注意到程序在最后一次输出后等待了一会儿。当池中的线程空闲一段时间后执行服务终止了它们时，程序就会终止。

**警告**

如果并发任务尝试读取或更新共享值，结果可能是不可预测的。我们将在 第 10.3 节 中详细讨论这个问题。目前，我们假设任务不共享可变数据。

#### 10.1.2 Futures

`Runnable` 接口用于不产生返回值的任务。如果你有一个计算结果的任务，请改用 `Callable<V>` 接口。它的 `call` 方法与 `Runnable` 接口的 `run` 方法不同，它返回一个类型为 `V` 的值：

```
public interface Callable<V> {

    V call() throws Exception;

}
```

作为额外奖励，`call` 方法可以抛出任意异常，这些异常可以传递给获取结果的代码。

要执行 `Callable`，请将其提交给执行服务：

```
ExecutorService executor = Executors.newFixedThreadPool();

Callable<V> task = ...;

Future<V> f = executor.submit(task);
```

当你提交任务时，你会得到一个 `future`——一个表示计算的对象，其结果将在未来的某个时间可用。`Future` 接口具有以下方法：

```
V get() throws InterruptedException, ExecutionException

V get(long timeout, TimeUnit unit)

    throws InterruptedException, ExecutionException, TimeoutException;

boolean cancel(boolean mayInterruptIfRunning)

boolean isCancelled()

boolean isDone()
```

`get` 方法会 `blocks` 直到结果可用或达到超时。也就是说，包含该调用的线程在方法正常返回或抛出异常之前，它不会继续执行。如果 `call` 方法产生一个值，`get` 方法将返回该值。如果 `call` 方法抛出异常，`get` 方法将抛出一个封装了所抛异常的 `ExecutionException`。如果超时，`get` 方法将抛出 `TimeoutException`。

`cancel` 方法尝试取消任务。

在上一节中，我们处理并发计算的方法是将任务拆分，然后等待所有部分都完成。但等待并不总是好主意。在接下来的章节中，你将看到如何实现无等待或异步计算。

#### 10.2.1 可完成的 Future (Completable Futures)

当你拥有一个 `Future` 对象时，你需要调用 `get` 来获取值，这会阻塞直到值可用。`CompletableFuture` 类实现了 `Future` 接口，并提供了一种获取结果的第二种机制。你可以注册一个回调函数，一旦结果可用，该函数将在（某个线程中）被调用。

```
CompletableFuture<String> f = ...;

f.thenAccept((String s) -> Process the result s);
```

通过这种方式，你可以在结果可用时立即对其处理，而无需阻塞。

有几个返回 `CompletableFuture` 对象的 API 方法。例如，`HttpClient` 类可以异步获取网页：

```
HttpClient client = HttpClient.newHttpClient();

HttpRequest request = HttpRequest.newBuilder(new URI(urlString)).GET().build();

CompletableFuture<HttpResponse<String>> f = client.sendAsync(

   request, HttpResponse.BodyHandlers.ofString());
```

要异步运行任务并获取 `CompletableFuture`，你不需要直接将其提交给执行器服务。相反，你调用静态方法 `CompletableFuture.supplyAsync`：

```
Supplier<V> task = ...;

CompletableFuture<V> f = CompletableFuture.supplyAsync(task, executor);
```

如果你省略了执行器，任务将在默认执行器上运行（即由 `ForkJoinPool.commonPool()` 返回的执行器）。

注意，该方法的第一个参数是 `Supplier<V>`，而不是 `Callable<V>`。这两个接口都描述了没有参数且返回类型为 `V` 的函数，但 `Supplier` 函数不能抛出检查异常（checked exception）。

`CompletableFuture` 可以通过两种方式完成：要么带结果完成，要么带未捕获的异常完成。为了处理这两种情况，请使用 `whenComplete` 方法。提供的函数将接收结果（如果没有则为 `null`）和异常（如果没有则为 `null`）。

```
f.whenComplete((s, t) -> {
    if (t == null) {Process the result s; }
    else { Process the Throwable t; }
});
```

`CompletableFuture` 之所以被称为“可完成”，是因为你可以手动设置一个完成值。（在其他并发库中，这种对象被称为 promise）。当然，当你使用 `supplyAsync` 创建 `CompletableFuture` 时，当任务完成后，完成值会被隐式地设置。但显式地设置结果可以为你提供额外的灵活性。例如，两个任务可以同时计算答案：

```
var f = new CompletableFuture<Integer>();

executor.execute(() -> {
   int n = workHard(arg);
   f.complete(n);
});

executor.execute(() -> {
   int n = workSmart(arg);
   f.complete(n);
});
```

如果想用异常来完成 future，请调用：

```
Throwable t = ...;

f.completeExceptionally(t);
```

### 注意

在多个线程中对同一个 future 调用 `complete` 或 `completeExceptionally` 是安全的。如果 future 已经完成，这些调用将不起作用。

`isDone` 方法告诉你 `Future` 对象是否已完成（正常完成或通过异常完成）。在先前的示例中，`workHard` 和 `workSmart` 方法可以使用该信息，在结果被另一个方法确定后停止工作。

### 警告

与普通的 `Future` 不同，当你调用其 `cancel` 方法时，`CompletableFuture` 的计算不会被中断。取消仅仅是将 `Future` 对象设置为将以异常方式完成，并抛出 `CancellationException`。通常情况下，这是合理的，因为 `CompletableFuture` 可能没有单一的线程负责它的完成。然而，这种限制也适用于由 `supplyAsync` 等方法返回的 `CompletableFuture` 实例，这些实例原则上是可以被中断的。解决方法参见练习 29。

### 10.2.2 组合 CompletableFuture

非阻塞调用通过回调实现。程序员为任务完成后应该发生的动作注册一个回调。当然，如果下一个动作也是异步的，那么之后的下一个动作就在另一个回调中。尽管程序员的思考方式是“先执行步骤 1，然后是步骤 2，最后是步骤 3”，但程序逻辑可能会分散在“回调地狱”中。当你必须添加错误处理时，情况会变得糟糕。假设步骤 2 是“用户登录”。由于用户可能会输错凭据，你可能需要重复该步骤。试图在一组回调中实现这种控制流——或者在实现后理解它——可能是极具挑战性的。

`CompletableFuture` 类通过提供一种将异步任务组合成处理流水线的机制，解决了此问题。

例如，假设我们想要从网页中提取所有链接以构建一个网络爬虫。假设我们有一个方法

`public void CompletableFuture<String> readPage(URI url)`

它在网页可用时产生网页的文本。如果该方法

`public static List<URI> getLinks(String page)`

产生 HTML 页面中的 URIs，你可以调度它在页面可用时调用：

```
CompletableFuture<String> contents = readPage(url);

CompletableFuture<List<URI>> links = contents.thenApply(Parser::getLinks);
```

`thenApply` 方法同样不会阻塞。它返回另一个 future。当第一个 future 完成时，其结果会被传递给 `getLinks` 方法，而该方法的返回值成为最终结果。

通过可完成 future，你只需要指定想要执行的操作以及按什么顺序。当然，这些并不会立即发生，但重要的是所有的代码都在在一个地方。

概念上，`CompletableFuture` 是一个简单的 API，但有许多组合可完成 future 的方法方法。让我们先看处理单个 future 的方法（参见表 10.1）。对于所示的每个方法，还有两个 `Async` 变体我没有显示。（其中一个使用共享的 `ForkJoinPool`，另一个带有一个 `Executor` 参数。）在表格中，我为复杂的函数接口使用了简写符号，用 `T -> U` 代替 `Function<? super T, U>`。这些显然不是真正的 Java 类型。

你已经见过了 `thenApply` 方法。假设 `f` 是一个接收类型 `T` 值并返回类型 `U` 值的函数。调用

```
CompletableFuture<U> future.thenApply(f);

CompletableFuture<U> future.thenApplyAsync(f);
```

返回一个 future，在 `future` 的结果可用时应用函数 `f`。第二次调用在另一个线程中运行 `f`。

`thenCompose` 方法接收的不是将类型 `T` 映射到 `U` 的函数，而是将 `T` 映射到 `CompletableFuture<U>` 的函数。听起来相当抽象，但可以非常自然。考虑从给定 URL 读取网页的动作。与其提供一个方法

`public String blockingReadPage(URI url)`

不如让该方法返回一个 future：

`public CompletableFuture<String> readPage(URI url)`

现在，假设我们有另一个从用户输入获取 URL 的方法，可能来自一个在用户点击 OK 之前不会显示答案的对话框。那未来中的一个事件：

`public CompletableFuture<URI> getURLInput(String prompt)`

这里有两个函数 `T -> CompletableFuture<U>` 和 `U -> CompletableFuture<V>`。显然，如果在第一个函数完成后调用第二个函数，它们可以组合成一个函数 `T -> CompletableFuture<V>`。这正是 `thenCompose` 所做的。

在上一节中，你已经看到了用于处理异常的 `whenComplete` 方法。还有一个 `handle` 方法，它需要一个函数来处理结果或异常并计算出一个新结果。在很多情况下，调用 `exceptionally` 方法会更简单：

```java
CompletableFuture<String> contents = readPage(url)
    .exceptionally(t -> {Log t; return emptyPage; });
```

提供的处理器仅在发生异常时才被调用，并且它会产生一个结果供处理流水线使用。如果没有发生异常，则使用原始结果。

在表 10.1 中返回类型为 `void` 的方法通常在处理流水线的末尾使用。

表 10.1：向 `CompletableFuture<T>` 对象添加操作

![Images](img/tab10-01.jpg)

现在，让我们转向组合多个 future 的（请参见表 10.2）。

前三个方法并发运行一个 `CompletableFuture<T>` 操作和一个 `CompletableFuture<U>` 操作，并合并结果。

接下来的三个方法并发运行两个 `CompletableFuture<T>` 操作。一旦其中一个完成，它的结果就会被传递，另一个结果则被忽略。

最后，静态方法 `allOf` 和 `anyOf` 接受任意数量的可完成 future，并产返回一个 `CompletableFuture<Void>`，该对象在所有 future 都完成或其中任何一个完成 时完成完成。`allOf` 方法不产生结果。`anyOf` 方法*不会*终止剩余的任务。练习 30 和练习 31 展示了对这两个方法的有用改进。

表 10.2：组合多个组合对象

![Images](img/tab10-02.jpg)

### 注意

从技术上来说，本节中的方法参数类型为 `CompletionStage`，而不是 `CompletableFuture`。`CompletionStage` 接口描述了如何组合异步计算，而 `Future` 接口关注计算的结果。`CompletableFuture` 既是 `CompletionStage` 也是 `Future`。

### 10.2.3 用户界面回调中的长时间运行任务

使用线程的原因之一是让你的程序具有更高的响应性。这在带有用户界面的应用程序中尤为重要。当你的程序需要执行耗时操作时，你不能在用户界面线程中执行工作，否则用户界面将冻结。相反，请启动另一个工作线程。

例如，如果你想在用户点击按钮时读取网页，请不要这样做：

```java
var read = new JButton("Read");

read.addActionListener(event -> { // 错误——长时间运行的操作在 UI 线程上执行

    var in = new Scanner(url.openStream());

    while (in.hasNextLine()) {

        String line = in.nextLine();

        ...

    }

});
```

相反，请在单独线程中执行工作。

```java
read.addActionListener(event -> { // 正确——在单独线程中执行长时间运行的操作

    Runnable task = () -> {

        var in = new Scanner(url.openStream());

        while (in.hasNextLine()) {
            String line = in.nextLine();

            ...

        }
    }

    executor.execute(task);

});
```



然而，你不能从执行长时间运行任务的线程直接更新用户界面。`Swing`、`JavaFX` 或 `Android` 等用户界面不是线程安全的。你不能从多个线程操作用户界面元素，否则它们有被损坏的风险。事实上，`JavaFX` 和 `Android` 会检查这一点，如果你尝试从 UI 线程以外的线程访问用户界面，它们会抛出异常。

因此，你需要调度任何 UI 更新在 UI 线程上发生。每个用户界面库都提供某种机制来调度 `Runnable` 在 UI 线程上执行。以下是 `Swing` 中这样做的方法：

```java
EventQueue.invokeLater(() -> message.appendText(line + "\n"));
```

### 注意

在执行耗时操作的同时向用户提供进度反馈是繁琐的，因此用户界面库通常提供某种辅助类来管理这些细节，例如 `Swing` 中的 `SwingWorker` 和 `Android` 中的 `AsyncTask`。你只需指定长时间运行任务的操作（在单独线程上运行），以及进度更新和最终处理（在 UI 线程上运行）。

### 10.3 线程安全

许多程序员最初认为并发编程相当简单。你只需要将工作划分成任务，就了。可能会出什么问题呢？

在接下来的节中，我将向你展示可能出现的问题，并对你如何处理这些问题提供高层概述。

#### 10.3.1 可见性

即使是像读写变量这样简单的操作，在现代处理器上可能变得极其复杂。考虑这个例子：

```java
private static boolean done = false;

public static void main(String[] args) {

    Runnable hellos = () -> {

        for (int i = 1; i <= 1000; i++)

            System.out.println("Hello " + i);

        done = true;
    };

    Runnable goodbye = () -> {
        int i = 1;
        while (!done) i++;

        System.out.println("Goodbye " + i);

    };

    Executor executor = Executors.newCachedThreadPool();

    executor.execute(hellos);

    executor.execute(goodbye);

}
```

第一个任务打印千次 `Hello`，并将 `done` 设置为 `true`。第二个任务等待 `done` 变为 `true`，然后打印一次 `Goodbye`。当我在笔记本笔记本上运行此程序时，输出可能是：

```
Hello 1
...
Hello 1000
Goodbye 50129
```

程序永不终止。为什么它不可见？现代编译器、虚拟机和处理器执行许多优化。这些优化假设代码是顺序的，除非明确说明。

一种优化是内存缓存。我们将 `done` 等内存位置视为 RAM 芯片中的某些位。但 RAM 芯片很慢——比现代处理器得多。因此，处理器尝试将它需要的数据保存在寄存器或板缓存中，并将更改写回内存。这种缓存对于性能是必不可少的。虽然同步缓存的操作，但其成本很大，并且只有在请求时才会执行。

另一种优化是指令重排序。编译器、虚拟机和处理器允许更改指令顺序以加速操作，只要不改变程序的顺序语义。

例如，考虑以下计算：

```
x = Something involving y;

y = Something involving x;

z = x + y;
```

前两个步骤必须在第三步之前发生，但它们可以按任意顺序。处理器可以（并且通常会）并发运行这两个步骤，或者如果第二个步骤的输入可用，则交换顺序。

在我们案例中，循环

```
while (!done) i++;
```

可以重排序为：

```
if (!done) while (true) i++;
```

因为循环体没有改变 `done` 的值。

默认情况下，优化假设不存在并发内存访问。如果有，虚拟机需要知道，这样它就可以发出阻止不当重排序的处理器指令。有几种方法可以确保变量更新是可见。以下是总结：

1. `final` 变量的值在初始化后可见。

2. `static` 变量的初始值在静态初始化后可见。

3. `volatile` 变量的更改可见的。

4. 在释放锁之前发生的更改对于任何获取相同锁的人都是可见的（参见第 10.7.1 节）。

在我们的案例中，如果你在声明共享变量 `done` 时使用 `volatile` 修饰符，问题就消失了：

```
private static volatile boolean done;
```

然后编译器会生成相应的指令，导致虚拟机发布处理器级命令以进行缓存同步。结果，一个任务对 `done` 的任何更改对其他任务都是可见的。

`volatile` 修饰符恰好足以解决这个特定问题。但正如你将在下一节中看到的，将共享变量声明为 `volatile` 并不是通用的解决方案。

### 提示

将任何初始化后不再改变的字段声明为 `final` 是一个极好的主意。这样你永远不需要担心它的可见性问题。

### 10.3.2. 竞态条件

假设多个并发任务更新一个共享的整数计数器。

```
private static volatile int count = 0;

...

count++; //  任务 1

...

count++; // 任务 2

...
```

该变量已声明为 `volatile`，因此更新是可见的。但还不够。

更新操作 `count++` 实际上意味着

```
register = count + 1;

count = register;
```

当这些计算交错执行时，错误的值可能会被存回 `count` 变量。在并发术语中，我们称增量操作不是**原子性的**。考虑这种场景：

```
int count = 0; // 初始值

register1 = count + 1; // 线程 1 计算 count + 1

... // 线程 1 被抢占

register2 = count + 1; // 线程 2 计算 count + 1

count = register2; // 线程 2 将 1 存入 count

... // 线程 1 再次运行

count = register1; // 线程 1 将 1 存入 count
```

现在 `count` 是 `1` 而不是 `2`。这种错误被称为 `竞态条件`，因为它取决于哪个线程在更新共享变量的“竞争”中胜出。

这个问题真的会发生吗？确实会发生。运行配套代码中的演示程序。它有 100 个线程，每个线程将计数器加 1,000 次并打印结果。

```
for (int i = 1; i <= 100; i++) {

    int taskId = i;

    Runnable task = () -> {

        for (int k = 1; k <= 1000; k++)
            count++;

        System.out.println(taskId + ": " + count);

    };

    executor.execute(task);
}
```

输出刚开始时通常很无害，如下：

```
1: 1000

3: 2000

2: 3000

6: 4000
```

过了一段时间，它看起来有点可怕：

```
72: 58196

68: 59196

73: 61196

71: 60196

69: 62196
```

但这可能仅仅是因为某些线程在不恰当的时刻被暂停了。重要的是最后完成的任务发生了什么。它把计数器增加到了 100,000 吗？

我在我的多核笔记本电脑上运行了几十次程序，每次都失败了。几年前，当个人电脑只有一个 CPU 时，竞态条件更难观察，程序员并不经常注意到如此剧烈的失败。但无论在几秒钟还是几小时内计算出错误的值，这并不重要。

这个示例查看了玩具程序中共享计数器的简单情况。练习题 17 在一个真实的示例中展示了相同的问题。但不仅仅是计数器。每当共享变量发生变异时，竞态条件就会成为问题。例如，在向队列头部添加一个值时，插入代码可能像这样：

```
var n = new Node();

if (head == null) head = n;

else tail.next = n;

tail = n;

tail.value = newValue;
```

如果这组指令序列在不利的时间被暂停，另一个任务获取了控制权，并在队列处于不一致状态时访问它，就会出现很多问题。

完成练习题 21，感受一下数据结构是如何被并发变异导致损坏的。

我们需要确保整个操作序列一起执行。这样的指令序列被称为 `临界区`。你可以使用 `lock` 来保护临界区，并使关键的操作序列具有原子性。你将在 第 10.7.1 节 中学习如何使用锁编程。

虽然使用锁来保护临界区很直接，但锁并不是解决所有并发问题的通用方案。它们很难正确使用，而且很容易出错，导致性能严重下降，甚至引起“**死锁”。

### 10.3.3. 安全并发的策略

在 `C` 和 `C++` 等语言中，程序员需要手动分配和释放内存。这听起来很危险——而且事实也如此。在 `Java` 中，有垃圾回收器，很少 `Java` 程序员需要担心内存管理。

遗憾的是，并发程序中的共享数据访问没有类似的机制。你所能最好的就是遵循一套指南来管理固有的危险。

一种非常有效的策略是 `局限性`（confinement）。在任务之间共享数据时，直接说不。例如，当你的任务需要计算某些内容时，给每个每个任务一个私有的计数器，而不是更新共享计数器。当任务完成后，它们可以将结果传递给另一个合并这些结果的任务。

另一个良好的策略是 `不可变性`（immutability）。不可变对象是安全的。例如，与其向共享集合添加结果，不如让任务生成一个不可变集合。另一个任务将这些结果合并。这个想法很简单，但有些点需要注意——请参见 第 10.3.4 节。

第三种策略是 `锁定`（locking）。通过一次允许一个任务访问数据结构，可以防止其损坏。在 第 10.5 节 中，你将看到 `Java` 提供的安全的并发的数据结构。第 10.7.1 节 展示了锁的工作原理。

锁定很容易出错，而且代价很高，因为它减少了并发执行的机会。例如，如果你有很多任务向共享哈希表贡献结果，而每次更新都锁定表，那么这就是真正的瓶颈。如果大多数任务都必须等待，它们就无法进行有效工作。有时可以对数据进行`分区`以便并发访问。`Java` 并发库中的几个数据结构使用了分区，流库中的并行算法也是如此。不要自己尝试！这真的很难实现。相反，请使用 `Java` 库中的数据结构和算法。

### 10.3.4. 不可变类

如果一个类的实例一旦构造就无法更改，那么它就是不可变的。这听起来似乎你对它们做不了什么，但事实并非如此。无处不在 `String` 类是不可变的，时间库中的类也是如此（参见第 12 章）。每个日期实例都是不可变的，但你可以获得新的日期，例如给定日期之后的一天。

或者考虑用于结果的集合。你可以使用可变的 `HashSet` 并这样更新它：

```
results.addAll(newResults);
```

但这显然是危险的。

不可变集合总是创建新集合。你会像这样更新结果：

```
results = results.union(newResults);
```

仍然存在变异，但控制一个变量比控制一个具有许多方法的哈集合容易得多。

实现不可变类并不困难，但你应该注意这些问题：

1. 不要在构造后更改对象状态。确保将实例变量声明为 `final`。没有理由不，而且你获得了一个重要的优势：虚拟机确保 `final` 实例变量在构造后是可见的（第 10.3.1 节）。

2. 当然，所有这些方法都不应该是变异器（mutators）。你应该将它们标记为 `final`，或者更好的是将类声明为 `final`，这样子类中就无法添加变异器。

3. 不要泄露可以从外部修改的状态。你的任何（非`private`）方法都不应该返回一个指向任何可用于修改的内部组件的引用，例如内部数组或集合。当你的某一个方法调用另一个类的方法时，也不得传递任何此类引用，因为被调方法可能会使用它们进行修改。相反，请传递一个副本。

4. 反之，不要存储构造函数接收到的任何可变对象的引用。相反，请创建一个副本。

5. 不要让 `this` 引用在构造函数中泄露。当你调用另一个方法时，你知道不要传递任何内部引用，但 `this` 呢？在构造完成后 `this` 是完全安全的，但如果你在构造函数中暴露了 `this`，有人可能会观察到处于不完整状态的对象。此外，还要注意构造函数给出包含隐藏 `this` 引用的内部类引用。自然地，这些情况非常罕见。

### 10.4 并行算法

在开始并行化计算之前，你应该检查 `Java` 库是否已经为你完成了这些工作。流库或 `Arrays` 类可能已经实现了你所需。

#### 10.4.1 并行流

流库可以自动对大型数据集的操作进行并行化。例如，如果 `coll` 是一个很大的字符串集合，而你想找到其中有多少个是以字母 `A` 开头的，可以调用

```
long result = coll.parallelStream().filter(s -> s.startsWith("A")).count();
```

`parallelStream` 方法产生一个并行流。该流被分成若干段。过滤和计数在每个段上进行，然后合并结果。你不需要担心这些细节。

### 注意事项

当你配合 lambda 表达式使用并行流时（例如，作为前述示例中 `filter` 和 `map` 的参数），请务必避免对共享对象进行不安全的变异操作。

为了让并行流良好工作，需要满足一些条件：

![images](img/sq.jpg) 需要足够的数据。并行流有显著的开销，只有在大规模数据集上才划算。

![images](img/sq.jpg) 数据应该在内存中。如果必须等待数据到达，将是低下。

![images](img/sq.jpg) 流应该能够高效地拆分为子区域。由数组或平衡二叉树支持的流效果良好，但链表或 `Stream.iterate` 的结果则不行。

![images](img/sq.jpg) 流操作应该包含大量工作。如果总工作负载不大，那么支付并发计算的设置成本就没有意义了。

![images](img/sq.jpg) 流操作不应该是阻塞的。

换句话说，不要将所有的流都转换为并行流。只有当你对已经在内存中的数据进行大量、持续的计算工作时，才使用并行流。

#### 10.4.2 并行数组操作

`Arrays` 类拥有许多并行化操作。与前几节中的并行流操作一样，这些操作将数组分成若干部分，并发处理这些部分并合并结果。

静态方法 `Arrays.parallelSetAll` 用由函数计算的值填充数组。该函数接收元素索引并计算该位置的值。

```
Arrays.parallelSetAll(values, i -> i % 10);

// 将 values 填充为 0 1 2 3 4 5 6 7 8 9 0 1 2 ...
```

显然，这种操作受益于并行化。它提供了针对所有基本类型数组和对象数组的对应版本。

`parallelSort` 方法可以对基本类型值或对象的数组进行排序。例如，

```
Arrays.parallelSort(words, Comparator.comparing(String::length));
```

对于所有方法，你都可以提供一个范围的边界，例如

```
Arrays.parallelSort(values, values.length / 2, values.length); // 排序后半部分
```

### 注意

从初上看，这些方法的名字中包含 `parallel` 似乎有点奇怪——用户不应该关心设置或排序是如何发生的。然而，API 设计者希望明确表示这些操作是并行化的。这样一来，用户就会引起注意，避免使用带有副作用的生成器或比较函数。

最后，还有一个 `parallelPrefix`，它是相当特殊的——练习 0 给出了一个简单的例子。

对于数组的其他并行操作，请将数组转换为并行流。例如，要计算一个长型整数数组之和，可以调用

```
long sum = IntStream.of(values).parallel().sum();
```

### 10.5 线程数据结构

如果多个线程并发修改数据结构（例如队列或哈希表），很容易损坏数据结构的内部。例如，一个线程可能开始插入一个新元素。假设它在重定向链接的中途被抢占，另一个线程开始遍历同一个位置。第二个线程可能会遵循无效链接并造成混乱，可能抛出异常甚至陷入无限循环。

正如你将在第 10.7.1 节中看到的，你可以使用锁来确保在特定时刻只有一个线程可以访问数据结构，从而阻塞其他任何线程。

#### 10.5.1 并发哈希映射

`ConcurrentHashMap` 首先是一个操作线程安全的哈希表。无论有多少线程同时操作它，内部结构都不会被破坏。当然，某些线程可能会被临时阻塞，但该映射可以高效地支持大量的并发读取者和一定数量的写入者。

但这还不够。假设我们想使用映射来统计特征出现的频率。例如，假设多个线程遇到单词，我们想要统计它们的频率。显然，以下更新计数的代码不是线程安全的：

```
var map = new ConcurrentHashMap<String, Long>();

...

Long oldValue = map.get(word);

Long newValue = oldValue == null ? 1 : oldValue + 1;

map.put(word, newValue); // 错误——可能没有替换 oldValue
```

另一个线程可能同时在更新同一个计数。

要安全地更新值，请使用 `compute` 方法。它被调用时接收键和一个计算新值的函数。该函数接收键和关联值（如果没有则为 `null`），并计算出新值。例如，我们可以这样更新计数：

```
map.compute(word, (k, v) -> v == null ? 1 : v + 1);
```



`compute`方法是*原子性的*——在计算过程中，其他线程不能变异映射条目。

还有`computeIfPresent`和`computeIfAbsent`变体，它们只在已有旧值或不存在旧值时才计算新值。

另一个原子操作是`putIfAbsent`。计数器可以初始化为

```
map.putIfAbsent(word, 0L);
```

当首次添加一个键时，你通常需要执行一些特殊操作。`merge`方法使得这变得特别方便。它有一个初始值参数，当键尚不存在时使用该值。否则，将调用你提供的函数，将现有值和初始值进行合并。（与`compute`不同，该函数不处理键。）

```
map.merge(word, 1L, (existingValue, newValue) -> existingValue + newValue);
```

或者简单地：

```
map.merge(word, 1L, Long::sum);
```

当然，传递给`compute`和`merge`的函数应该快速完成，并且它们不应该尝试修改 map。

## 注意事项

某些方法可以在条目当前与现有条目相等时，原子性地移除或替换该条目。在`compute`方法出现之前，人们会编写类似下面的代码来增加计数：

```
do {
    oldValue = map.get(word);
    newValue = oldValue + 1;
} while (!map.replace(word, oldValue, newValue));
```

## 注意事项

有几种`批量操作`（bulk operations）用于搜索、转换或访问`ConcurrentHashMap`。它们在数据的快照上操作，即使在其他线程对 map 进行操作时也能安全执行。在 API 文档中，寻找名称以`search`、`reduce`和`forEach`开头的操作。还有针对键、值和条目的变体。`reduce`方法针对`int`、`long`和`double`值的还原函数有特化实现。

## 10.5.2. 阻塞队列

用于协调任务之间工作的常用工具之一是`阻塞队列`（blocking queue）。生产者任务将项插入队列，消费者任务检索它们。队列允许你安全地将数据从一个任务传递给另一个任务。

当你尝试添加元素而队列当前已满，或者当队列为空时尝试移除元素时，操作会被阻塞。通过这种方式，队列平衡了工作负载。如果生产者任务运行得比消费者任务慢，消费者将阻塞等待结果。如果生产者运行得更快，队列将一直填充，直到消费者追上。

表 10.3 显示了阻塞队列的方法。阻塞队列方法分为三类，区别在于当队列满或为空时它们执行的操作。除了阻塞方法外，还有在未成功时抛出异常的方法，以及在无法执行任务时返回失败指示器而不是抛出异常的方法。

表 10.3：阻塞队列操作

![Images](img/tab10-03.jpg)

## 注意事项

`poll`和`peek`方法返回`null`来指示失败。因此，向这些队列中插入 null 值是非合法的。

还有带有超时`offer`和`poll`方法变体。例如，调用：

```
boolean success = q.offer(x, 100, TimeUnit.MILLISECONDS);
```

尝试在 100 毫秒内向队列尾插入一个元素。如果成功，返回`true`；否则，在超时后返回`false`。同样，调用：

```
Object head = q.poll(100, TimeUnit.MILLISECONDS)
```

尝试在 100 毫秒内移除队列头部。如果成功，返回头部；否则，在超时后返回`null`。

`java.util.concurrent`包提供了多种阻塞队列的变体。`LinkedBlockingQueue`基于链表，而`ArrayBlockingQueue`使用循环数组。

练习 11 显示了如何使用阻塞队列分析目录中的文件。一个线程遍历文件树并将文件插入队列。多个线程移除文件并对它们进行搜索。在这个应用程序中，生产者可能会迅速填满队列并阻塞，直到消费者追上。

这种设计的一个共同挑战是停止消费者。当队列为空时，消费者并不能简单地退出。毕竟，生产者可能尚未启动，或者它已经落后了。如果只有一个生产者，它可以向队列中添加一个“最后一个项”指示器，类似于行李提取传送带上贴有“最后一件行李”标签的虚拟行李箱。

## 10.5.3. 其他线程安全数据结构

就像你可以在`java.util`包中的哈 map 和树 map 之间选择一样，还有一种基于键比较的并发 map，称为`ConcurrentSkipListMap`。如果你需要按排序顺序遍历键，或者需要`NavigableMap`接口中添加的方法之一（请参见第 7 章），请使用它。同样，还有`ConcurrentSkipListSet`。

`CopyOnWriteArrayList`和`CopyOnWriteArraySet`是线程安全的集合，其中所有修改器都会创建底层数组的副本。如果遍历集合的线程远多于修改集合的线程，这种安排就是非常有用的。当你构造一个迭代器时，它包含指向当前数组的引用。如果数组稍后被修改，迭代器仍然持有旧数组，但集合的数组被替换了。因此，旧的迭代器拥有一个一致的（但可能是过时的）视图，它可以在没有任何同步开销的情况下访问该视图。

假设你需要一个大的线程安全的集合而不是 map。没有`ConcurrentHashSet`类，你显然比尝试自己创建一个要明智。当然，你可以使用带有虚假值的`ConcurrentHashMap`。但直接向集合中添加元素是没有意义的，因为没有对应的值可以添加。你可以使用第二个`keySet`方法，并带上一个默认值：

```
Set<String> words = ConcurrentHashMap.newSet();
words.add("Java");
```

如果`"Java"`不在`words`中，现在它的值为一个。

## 10.6. 原子计数器和累加器

如果多个线程更新共享计数器，你需要确保以线程安全的方式进行。在`java.util.concurrent.atomic`包中有很多类，它们使用安全高效的机器级指令来保证整数、`long`和`boolean`值、对象引用及其数组操作的原子性。正确使用这些类需要大量的专业知识。然而，原子计数器和累加器对于应用程序编程非常方便。

例如，你可以这样安全地生成一组数字：

```
public static AtomicLong nextNumber = new AtomicLong();

// 在某些线程...

long id = nextNumber.incrementAndGet();
```

`incrementAndGet`方法原子性地增加`AtomicLong`并返回增加后的值。这意味着，获取值、加 1、设置值和产生新值的操作无法被中断。即使多个线程并发访问同一个实例，也能保证计算并返回正确的值。

有原子性设置、增加和减去值的方法，但假设你想进行更复杂的更新。一种方法是使用`updateAndGet`方法。例如，假设你想跟踪不同线程观察到的最大值。以下代码不起：

```
public static AtomicLong largest = new AtomicLong();

// 在某些线程...

largest.set(Math.max(largest.get(), observed)); // 错误—竞态条件！
```

此更新不是原子的。相反，请调用`updateAndGet`并传入一个更新变量 lambda 表达式。在示例中，我们可以调用：

```
largest.updateAndGet(x -> Math.max(x, observed));
```

或者

```
largest.accumulateAndGet(observed, Math::max);
```

`accumulateAndGet`方法接受一个二元运算符，用于结合原子值和提供的参数。

还有`getAndUpdate`和`getAndAccumulate`方法，它们会返回旧值。

## 注意

这些方法也提供给以下类：

```
AtomicInteger                 AtomicLongFieldUpdater
AtomicIntegerArray            AtomicReference
AtomicIntegerFieldUpdater     AtomicReferenceArray
AtomicLongArray               AtomicReferenceFieldUpdater
```

当有大量线程访问同一个原子值时，性能会受到影响，因为更新是以`乐观的`方式执行的。也就是说，该操作从给定的旧值计算出一个新值，如果旧值仍然是当前值，则进行替换；否则，重试。在剧烈的竞争下，更新需要过多的重试。

`LongAdder`和`LongAccumulator`类解决了某些常见更新的问题。`LongAdder`由多个变量组成，它们的总和即为当前值。

多个线程可以更新不同的加数，并且当线程数增加时，会自动提供新的加数。在所有工作完成之前不需要总和之值的常见情况下，这种方法是高效的。性能的提升可能是巨大的——参见练习 0。

如果你预见到会有高竞争，应该简单地使用`LongAdder`而不是`AtomicLong`。方法名称略有不同。调用`increment`增加计数器，或调用`add`增加数量，并调用`sum`获取总和。

```
final LongAdder count = new LongAdder();

for (...)
    executor.execute(() -> {
        while (...) {
            ...
            if (...) count.increment();
        }
    });

...

long total = count.sum();
```

## 注意

当然，`increment`方法`并不会`返回旧值。这样做会抵消将总和拆分为多个加数所带来的效率提升。

`LongAccumulator`将此思想推广到任意的累加操作。在构造函数中，你提供了该操作及其中性元素。要合并新值，请调用`accumulate`。调用`get`获取当前值。

```
var accumulator = new LongAccumulator(Long::sum, 0);

// 在某些任务中...
accumulator.accumulate(value);

// 当所有工作完成后
long sum = accumulator.get();
```

内部，累加器拥有变量`a[1]`、`a[2]`、…… `a[n]`。每个变量都用中性元素初始化（示例中为`0`）。

当用值`v`调用`accumulate`时，其中一个变量会被原子更新为`a[i] = a[i] op v`，其中`op`是中中形式表示的累加操作。在示例中，调用`accumulate`会为某个`i`计算`a[i] = a[i] + v`。

`get`的结果是`a[1] op a[2] op … op a[n]`。在示例中，那是累加器的总和，`a[1] + a[2] + ... + a[n]`。

如果你选择不同的操作，可以计算最大值或最小值（参见练习 0）。通常，该操作必须满足结合律和交换律。这意味着最终结果必须与中间值组合的顺序无关。

还有`DoubleAdder`和`DoubleAccumulator`，它们的工作方式相同，只是针对的是`double`类型的值。

## 提示

如果你使用`LongAdder`的哈希映射，可以使用以下惯用法来增加键对应的累加器：

```
ConcurrentHashMap<String,LongAdder> counts = ...;
counts.computeIfAbsent(key, k -> new LongAdder()).increment();
```

当第一次为`key`增加计数时，会设置一个新的累加器。

## 10.7. 锁与条件 (Locks and Conditions)

现在你已经看到了应用程序程序员可以安全地用于构建并发应用程序的几种工具。你可能好奇如何构建一个线程安全的计数器或阻塞队列。接下来的章节将展示如何实现，以便你对成本和复杂性有一些了解。

### 10.7.1 锁

为了避免共享变量的损坏，需要确保一次时刻只有一个线程可以计算并设置新值。必须完整执行且不被中断的代码被称为`临界区`。可以使用`lock`来实现临界区：

```
public class Counter {
    private final Lock countLock = new ReentrantLock(); // 多个线程共享
    private int count = 0; // 多个线程共享

    public int increment() {
        countLock.lock();
        try {
            count++; // 临界区
            return count;
        } finally {
            countLock.unlock(); // 确保锁释放
        }
    }
}
```

## 注意

在本节中，我使用`ReentrantLock`类来解释锁的工作原理。正如你将在下一节看到的，并不要求使用显式锁，因为`synchronized`关键字使用了“隐式”锁。但通过查看显式锁更容易理解底层发生了什么。

第一个执行`lock`方法的线程会锁定`countLock`对象然后继续。如果另一个线程尝试在同一对象上调用`lock`，它将被阻塞，直到第一个线程执行`unlock`。通过这种方式，可以确保一次只有一个线程可以执行临界区。

注意，通过将`unlock`方法放在`finally`子句中，如果临界区发生任何异常，锁也会释放。否则，锁将永久锁定，其他线程将无法继续。这显然是非常糟糕的。当然，在这种情况下临界区不会抛出异常，因为它只执行整数递增。但无论如何，使用`try/finally`语句是一种惯用法，以防添加更多代码。

初看起来，使用锁保护临界区似乎很简单。然而，细节在于其中。经验表明，许多程序员编写锁的代码很有困难。他们可能会使用错误的锁或产生问题。

由于这些原因，应用程序程序员应将锁作为最后的手段。首先尝试避免共享，使用不可变数据或将可变数据传递给另一个线程。如果必须共享，请使用预构建的安全结构，例如`ConcurrentHashMap`或`LongAdder`。尽管如此，了解锁是有用的，你可以理解如何实现此类数据结构。

### 10.7.2 synchronized 关键字

在前面的节中，我向你展示了如何使用`ReentrantLock`实现临界区。你不必使用显式锁，因为在 Java 中，*每个对象*都有一个*内旋锁*。然而，为了理解内在锁，先看到显式锁会有帮助。

`synchronized`关键字用于锁定内旋锁。它有两种形式。你可以锁定一个代码块：

```
synchronized (obj) {
    临界区
}
```

这本质上意味着

```
obj. intrinsicLock.lock();
try {
    临界区
} finally {
    obj. intrinsicLock.unlock();
}
```

对象实际上并没有一个作为内旋锁的字段。这段代码只是为了说明使用`synchronized`关键字时发生了什么。

你也可以将方法声明为`synchronized`。那么它的方法体将会在接收者参数`this`上锁定。也就是说，

```
public synchronized void method() {
    方法体
}
```

等同于

```java
public void method() {
    this.intrinsicLock.lock();
    try {
        Body
    } finally {
        this.intrinsicLock.unlock();
    }
}
```

例如，计数器可以简单地声明为

```java
public class Counter {
    private int count = 0;

    public synchronized int increment() {
        count++;
        return count;
    }
}
```

通过使用`Counter`实例的内置锁，不需要引入显式锁。

如你所见，使用`synchronized`关键字产生的代码非常简洁。当然，要理解这段代码，你必须知道每个对象都有一个内置锁。

## 注意事项

锁的作用不仅仅是原子性。锁还保证了可见性。例如，考虑在第 10.3.1 节中让我们非常头疼的`done`变量。如果你使用锁来同时读和写该变量，那么你可以确保`get`的调用者能看到通过`set`调用对变量进行的任何更新。

```java
public class Flag {
    private boolean done;
    public synchronized void set() { done = true; }
    public synchronized boolean get() { return done; }
}
```

注意，与前一节中的`ReentrantLock`不同，内置锁是`public`的。任何人都可以获取它。这有时是有用的。例如，Java 1.0 拥有一个`Hashtable`类，它带有用于修改表格的同步方法。为了安全地遍历这样的一个表，你可以像这样获取锁：

```java
synchronized (table) {
    for (K key : table.keySet()) ...
}
```



在这里，`table`既表示哈希表，也表示其方法所使用的锁。这种“客户端锁定”是误解的常见源头（见练习 22），并可能导致死锁。

同步方法的灵感源于 Per Brinch Hansen 和 Tony Hoare 在 20 世纪 70 年代开创的*监器*（monitor）概念。监器本质上是一个类，其中所有实例变量都是私有的，且所有方法都受一个私有锁的保护。然而，Java 类并不是真正的监器，因为它可以拥有公有实例变量，并混合使用同步和非同步方法。

## 10.7.3. 等待条件

考虑一个带有添加和移除对象方法的简单`Queue`类。同步方法确保了这些操作是原子的。

```java
public class Queue {

    class Node { Object value; Node next; };

    private Node head;

    private Node tail;

    public synchronized void add(Object newValue) {

        var n = new Node();

        if (head == null) head = n;

        else tail.next = n;

        tail = n;

        tail.value = newValue;

    }

    public synchronized Object remove() {

        if (head == null) return null;

        Node n = head;

        head = n.next;

        return n.value;

    }

}
```

现在假设我们想将`remove`方法转换为`take`方法，该方法在队列为空时会阻塞。

对空状态的检查必须在同步方法内部进行，否则查询将失去意义——另一个线程可能在此期间已经清空了队列。

```java
public synchronized Object take() {

    if (head == null) ... // 现在怎么办？

    Node n = head;

    head = n.next;

    return n.value;

}
```

但如果队列为空该发生什么呢？当当前线程持有锁时，其他线程无法添加元素。这就是`wait`方法大显身手的地方。

如果`take`方法发现无法继续，它会调用`wait`方法：

```java
public synchronized Object take() throws InterruptedException {

    while (head == null) wait();

    ...

}
```

当前线程现在被去激活并放弃锁。这让另一个线程进入，我们希望它能向队列中添加元素。这被称为*等待条件*（waiting on a condition）。

注意，`wait`方法是`Object`类的方法。它与对象相关的锁有关。

阻塞以获取锁的线程与调用了`wait`的线程之间存在本质区别。线程一旦调用`wait`方法，它就会进入对象的*等待集*（wait set）。当锁可用时，该线程不会变为可运行状态。相反，它将保持未激活状态，直到另一个线程在同一个对象上调用了`notifyAll`方法。

当另一个线程添加元素后，它应该调用该方法：

```java
public synchronized void add(Object newValue) {

    ...

    notifyAll();

}
```

对`notifyAll`的调用会激活等待集中的所有线程。当线程从等待集中移除时，它们再次变为可运行状态，且调度器最终会再次激活它们。此时，它们将尝试重新获取锁。当其中一个线程成功时，它将从之前停止的地方继续，从`wait`调用处返回。

此时，线程应该再次测试条件。无法保证该条件现在已经满足——`notifyAll`方法只是向等待线程发送信号，表明条件在此时*可能*已经满足，并且再次检查条件是值得的。出于这个原因，测试是在循环中进行的

```java
while (head == null) wait();
```

线程只有在持有锁的情况下，才能对某个对象调用`wait`、`notifyAll`或`notify`。

### 警告

`notify`方法只会唤醒等待集中的一个线程。这比唤醒所有线程高效，但存在风险。如果被选中的线程无法继续，它将再次阻塞。如果其他线程没有调用`notify`，程序就会死锁。

### 注意事项

在实现阻塞数据结构时，`wait`、`notify`和`notifyAll`方法是适当的。但它们很难使用。应用程序不应该需要这些方法。相反，请使用预构建的数据结构，如`LinkedQueue`或`ConcurrentHashMap`。

## 10.8. 线程

当我们接近本章结束时，是时候讨论执行任务的实体——线程。通常情况下，使用管理线程的执行器更好，但后续章节提供了直接操作线程的背景信息。

### 10.8.1. 线程

在 Java 中运行线程的方法：

```java
Runnable task = () -> { };

var thread = new Thread(task);

thread.start();
```

静态`sleep`方法让当前线程睡眠一段时间，以便其他线程有机会执行工作。

```java
Runnable task = () -> {

    ...

    Thread.sleep(millis);

    ...

}
```

如果你想等待线程完成，请调用`join`方法：

```java
thread.join(millis);
```

这两个方法都会抛出在下一节中讨论的检查异常`InterruptedException`。

线程在`run`方法返回时结束，无论是正常返回还是因为抛出了异常。在后者的情况下，会调用线程的*未捕获异常处理器*（uncaught exception handler）。当创建线程时，该处理器设置为线程组的未捕获异常处理器，最终是全局处理器（参见第 5 章）。你可以通过调用`setUncaughtExceptionHandler`方法更改线程的处理器。

### 注意事项

Java 早期定义了一个立即终止线程的`stop`方法，以及一个阻塞线程直到另一个线程调用`resume`的`suspend`方法。这两个方法后来都被废弃。

`stop`方法本质是不安全的。假设线程在临界区域中间被停止——例如在队列中插入元素。那么队列将处于部分更新状态。然而，保护临界区域的锁被释放了，其他线程可以使用损坏的数据结构。当你想要停止一个线程时，应该中断它。被中断的线程可以在安全时再停止。

`suspend`方法没有那么危险，但仍然存在问题。如果一个线程在持有锁时被挂起，任何其他尝试获取该锁的线程都会阻塞。如果恢复的线程是其中之一，程序就会发生死锁。

### 10.8.2. 线程中断

假设对于某个查询，你总是对第一个结果满意。当对答案的搜索分布在多个任务中时，你希望在获得答案后取消所有其他任务。在 Java 中，任务取消是*协作的*（cooperative）。

每个线程都有一个*中断状态*（interrupted status），表示有人想要“中断”该线程。中断的的确切含义没有精确的定义，但大多数程序员用它来表示取消请求。

`Runnable`可以检查此状态，这通常在循环中完成：

```java
Runnable task = () -> {

    while ( more work to do) {

        if (Thread.currentThread().isInterrupted()) return;

        Do more work

    }

};
```

当线程被中断时，`run`方法简单地结束。

#### Note
还有一个静态的`Thread.interrupted`方法，它可以获取当前线程的中断状态，然后清除它，并返回旧状态。

有时，线程会变得暂时不活跃。这可以在线程等待另一个线程计算值或等待输入/输出时，或者它进入睡眠以给其他线程机会时发生。

如果线程在等待或睡眠期间被中断，它会立即重新激活——但在情况下，中断状态不会被设置。相反，会抛出一个`InterruptedException`。这是一个受检异常，你必须在`Runnable`的`run`方法中捕获它。对该异常的标准反应是结束`run`方法：

```java
Runnable task = () -> {

    try {

        while ( more work to do) {

            Do more work

            Thread.sleep(millis);

        }

    }

    catch (InterruptedException ex) {

        // Do nothing

    }

};
```

当你以这种方式捕获`InterruptedException`时，就不需要检查中断状态。如果线程在调用`Thread.sleep`之外被中断，则状态会被设置，并且`Thread.sleep`方法一旦被调用就会抛出`InterruptedException`。

#### Tip
`InterruptedException`看起来可能烦人，但当你调用`sleep`等方法时，你不应该仅仅捕获并忽略它。如果你实在无事可做，至少设置中断状态：

```java
try {

    Thread.sleep(millis);

} catch (InterruptedException ex) {

    Thread.currentThread().interrupt();

}
```

或者更好的做法是，直接将异常传递给胜任的处理器：

```java
public void mySubTask() throws InterruptedException {

    ...

    Thread.sleep(millis);

    ...

}
```

### 10.8.3. 线程本地变量 (Thread-Local Variables)

在前面的章节中，我们讨论了在线程之间共享变量的风险。有时，你可以通过使用`ThreadLocal`辅助类为每个线程提供自己的实例来避免共享。例如，`SimpleDateFormat`类不是线程安全的。假设我们有一个静态变量：

```java
public static final SimpleDateFormat dateFormat = new SimpleDateFormat("yyyy-MM-dd");
```

如果两个线程执行如下操作：

```java
String dateStamp = dateFormat.format(new Date());
```

那么结果可能是垃圾（错误的），因为`dateFormat`使用的内部数据结构可能会被并发访问所破坏。你可以使用同步（这开销很大），或者可以在每次需要时构造一个本地的`SimpleDateFormat`对象，但也是浪费的。

要为每个线程构造一个实例，使用以下代码：

```java
public static final ThreadLocal<SimpleDateFormat> dateFormat

   = ThreadLocal.withInitial(() -> new SimpleDateFormat("yyyy-MM-dd"));
```

要访问实际格式器，调用：

```java
String dateStamp = dateFormat.get().format(new Date());
```

在给定线程中第一次调用`get`时，会调用构造函数中的 lambda 表达式。从那时起，`get`方法返回属于当前线程的实例。

的问题是在多线程中生成随机数。`java.util.Random`类是线程安全的。但如果多个线程需要等待单个共享的生成器，它仍然是无效的。

你可以使用`ThreadLocal`辅助类为每个线程提供单独的生成器，但已经有一个便利类了。只需调用如下方法：

```java
int random = ThreadLocalRandom.current().nextInt(upperBound);
```

调用`ThreadLocalRandom.current()`返回一个当前线程唯一的随机数生成器实例。

线程本地变量有时也用于让所有协作完成任务的方法可以使用对象，而无需将对象从一个调用者传递给另一个调用者。例如，假设你想共享数据库连接。声明一个变量：

```java
public static final ThreadLocal<Connection> connection = ThreadLocal.withInitial(() -> null);
```

当任务开始时，为此线程初始化连接：

```java
connection.set(connect(url, username, password));
```

任务调用一些方法，所有都在同一个线程内，最终其中一个方法需要连接：

```java
var result = connection.get().executeQuery(query);
```

注意，相同的调用可能发生在多个线程上。每个线程都获得它自己的连接对象。

#### Caution
在前面的示例中，只有一个任务使用该线程是至关重要的。当使用线程池执行任务时，你不希望让数据库连接对共享同一线程的任务可用。

### 10.8.4. 其他线程属性

`Thread`类暴露了线程的许多属性，但大多数属性对于认证考试的学生比应用程序程序员更有用。本节简要回顾这些。

线程可以被成组，并且有 API 方法管理组，例如中断组中的所有线程。如今，执行器是管理组的首选机制。

你可以为线程设置*优先级*（priorities），高优先级线程将被调度在低优先级线程之前。希望虚拟机和主机平台尊重优先级，但细节取决于平台。因此，使用优先级是脆弱的。

线程有*状态*（states），你可以判断线程是新的、运行中的、阻塞 I/O、等待还是已终止。当你作为应用程序程序员使用线程时，很少理由查询它们的状态。

线程有名称，你可以为了调试更改名称。例如：

```java
Thread.currentThread().setName("Bitcoin-miner-1");
```

当线程由于未捕获的异常终止时，该异常将传递给线程的*未捕获异常处理器*（uncaught exception handler）。默认情况下，它的堆栈轨迹会被转储到`System.err`，但你可以安装自己的处理器（参见第 5 章）。

守护线程（daemon）是一种除了服务其他没有其他角色的线程。这对于发送定时器或清理过期缓存条目的线程很有用。当只剩下守护线程时，虚拟机将退出。

要将线程设置为守护线程，在启动线程之前调用`thread.setDaemon(true)`。

## 10.9. 进程

到为止，你已经看到了如何在同一程序的不同线程中执行 Java 代码。有时，你需要执行另一个程序。对于这一点，使用`ProcessBuilder`和`Process`类。`Process`类在独立的操作系统进程中执行命令，并允许你与其标准输入、输出和错误流进行交互。`ProcessBuilder`类允许你配置`Process`对象。

#### Note
`ProcessBuilder`类是`Runtime.exec`调用 的一个更灵活的替代方案。

### 10.9.1. 构建进程

通过指定你想执行的命令来开始构建过程。你可以提供一个`List<String>`或者直接提供组成命令的字符串。

```java
var builder = new ProcessBuilder("gcc", "myapp.c");
```

### 注意事项

第一个字符串必须是一个可执行的命令，而不是 shell 内置命令。例如，要在 Windows 中运行`dir`命令，你需要使用字符串`"cmd.exe"`、`"/C"`和`"dir"`来构建一个进程。

每个进程都有一个*工作目录*，它被用于解析相对目录名。默认情况下，进程的工作目录与虚拟机相同，这通常是你启动`java`程序时所在的目录。你可以通过`directory`方法来更改它：

```java
builder = builder.directory(path.toFile());
```

### 节点

配置`ProcessBuilder`的每个方法都返回其对象本身，因此你可以对命令进行链式调用。最终，你将调用：

```java
Process p = new ProcessBuilder(command).directory(file).start();
```

接下来，你可能想要指定进程的标准输入、输出和错误流应该发生什么。默认情况下，每一个流都是一个管道，你可以通过以下方式访问它们：

```java
OutputStream processIn = p.getOutputStream();

InputStream processOut = p.getInputStream();

InputStream processErr = p.getErrorStream();
```

或者，对于文本输入输出：

```java
BufferedWriter processIn = p.outputWriter(charset);

BufferedReader processOut = p.inputReader(charset);

BufferedReader processErr = p.errorReader(charset);
```



注意，进程的输入流在 JVM 中是一个输出流！你向该流写入内容，你写入的任何内容都会成为进程的输入。相反，你读取进程写入输出流和错误流的内容。对你来说，它们是输入流。

你可以指定新进程的输入、输出和错误流与 JVM 相同。如果用户在控制台中运行 JVM，任何用户输入都将转发到进程，而进程输出将显示在控制台中。调用：

```
builder.inheritIO()
```

为所有三个流设置此选项。如果你只想继承某些流，请传递值：

```
ProcessBuilder.Redirect.INHERIT
```

传递给`redirectInput`、`redirectOutput`或`redirectError`方法。例如：

```
builder.redirectOutput(ProcessBuilder.Redirect.INHERIT);
```

你可以通过提供`File`对象将进程流重定向到文件：

```
builder.redirectInput(inputFile)
    .redirectOutput(outputFile)
    .redirectError(errorFile)
```

输出和错误文件在进程启动时会被创建或截断。要追加到现有文件，请使用：

```
builder.redirectOutput(ProcessBuilder.Redirect.appendTo(outputFile));
```

合并输出流和错误流通常很有用，这样你就能按照进程生成输出的顺序看到输出和错误消息。调用：

```
builder.redirectErrorStream(true)
```

来激活合并。如果你这样做了，就不能再在`ProcessBuilder`上调用`redirectError`或在`Process`上调用`getErrorStream`了。

最后，你可能想要修改进程的环境变量。在这里，构建器的链语法不再适用。你需要获取构建器的环境（由运行 JVM 的进程的环境变量初始化），然后放入或移除项。

```
Map<String, String> env = builder.environment();
env.put("LANG", "fr_FR");
env.remove("JAVA_HOME");
Process p = builder.start();
```

如果你想将一个进程的输出管道到另一个进程的输入（就像 shell 中的`|`运算符），请使用`startPipeline`方法。传递一个 process builder 列表并从最后一个进程读取结果。这里是一个示例，列出目录树中唯一的扩展名：

```
List<Process> processes = ProcessBuilder.startPipeline(List.of(
   new ProcessBuilder("find", "/opt/jdk-17"),
   new ProcessBuilder("grep", "-o", "\\.[^./]*$"),
   new ProcessBuilder("sort"),
   new ProcessBuilder("uniq")
));
Process last = processes.get(processes.size() - 1);
var result = new String(last.getInputStream().readAllBytes());
```

这只是一个展示机制的示例。当然，这个特定任务通过在 Java 中进行目录遍历而不是运行四个进程来解决，效率会更高。

## 10.9.2. 运行进程

在配置好构建器后，调用其`start`方法启动进程。如果你将输入、输出和错误流配置为管道，现在你可以向输入流写入内容并读取输出和错误流了。例如：

```
Process process = new ProcessBuilder("/bin/ls", "-l")
    .directory(Path.of("/tmp").toFile())
    .start();
try (var in = new Scanner(process.getInputStream())) {
    while (in.hasNextLine())
        System.out.println(in.nextLine());
}
```

### 注意事项

进程流的缓冲区空间有限。你不应该向输入中大量写入数据，并且应该及时读取输出。如果有大量的输入和输出，你可能需要在不同的线程中进行产生和消费。

要等待进程完成，请调用：

```
int result = process.waitFor();
```

或者，如果你不想无限等待：

```
long delay = ...;
if (process.waitFor(delay, TimeUnit.SECONDS)) {
    int result = process.exitValue();
} else {
    process.destroyForibly();
}
```

第一次调用`waitFor`返回进程的退出值（约定俗，成功为 0，非零为错误代码）。第二次调用返回是否超时。你需要通过调用`exitValue`方法获取退出值。

与其等待进程结束，你可以直接调用`isAlive`查看它是否仍然存。要杀死进程，调用`destroy`或`destroyForibly`。在 Unix 上，前者使用`SIGTERM`终止进程，后者使用`SIGKILL`。（`supportsNormalTermination`方法返回`destroy`是否可以正常终止该进程。）

最后，你可以接收进程完成的异步通知。`onExit()`返回一个`CompletableFuture<Process>`，你可以用它调度任何操作。

```
process.onExit().thenAccept(
    p -> System.out.println("Exit value: " + p.exitValue()));
```

## 10.9.3. 句柄

要获取关于程序启动的进程或机器上运行的其他进程的信息，请使用`ProcessHandle`接口。你可以通过四种方式获取`ProcessHandle`：

1. 给`Process`对象`p`，`p.toHandle()`获取其句柄。
2. 给`long`操作系统进程 ID，`ProcessHandle.of(id)`返回该进程的句柄。
3. `ProcessHandle.current()`是运行此 Java 虚拟机的句柄。
4. `ProcessHandle.allProcesses()`返回当前进程可见的所有操作系统进程的`Stream<ProcessHandle>`。

给定进程句柄，你可以获取它的进程 ID、父进程、子进程和后代：

```
long pid = handle.pid();
Optional<ProcessHandle> parent = handle.parent();
Stream<ProcessHandle> children = handle.children();
Stream<ProcessHandle> descendants = handle.descendants();
```

### 节点

由`allProcesses`、`children`和`descendants`方法返回的`Stream<ProcessHandle>`实例只是时刻快照。在你处理它们时，流中的任何进程可能已经终止，并且可能启动了不在流中的进程。

`info`方法产生一个`ProcessHandle.Info`对象，其中包含获取进程信息的方法。

```
Optional<String[]> arguments()
Optional<String> command()
Optional<String> commandLine()
Optional<String> startInstant()
Optional<String> totalCpuDuration()
Optional<String> user()
```

所有方法都返回`Optional`值，因为特定的操作系统可能无法报告相关信息。

对于监控或强制终止进程，`ProcessHandle`接口拥有`Process`类相同的`isAlive`、`supportsNormalTermination`、`destroy`、`destroyForcibly`和`onExit`方法。然而，没有等同于`waitFor`方法。

## 练习题

1. 使用并行流（parallel streams），找到目录中所有包含指定单词的文件。如何只找到第一个？这些文件实际上是并发搜索的吗？

2. 在你的计算机上，数组需要达到多大程度，`Arrays.parallelSort`才会比`Arrays.sort`快？

3. 实现一个方法，产生一个任务，该任务读取文件中所有的单词，并尝试查找给定的单词。当任务被中断时，应立即完成（并带有一个调试消息）。对于目录中的所有文件，为每个文件调度一个任务。当其中一个任务成功时，中断所有其他任务。

4. 第 10.4.2 节中未讨论的一种并行操作是`parallelPrefix`方法，它将每个数组元素替换为给定关联操作的前缀累加和。哈？这里有一个示例。考虑数组`[1, 2, 3, 4, ...]`和乘法运算。执行`Arrays.parallelPrefix(values, (x, y) -> x * y)`后，数组包含：

```
[1, 1 × 2, 1 × 2 × 3, 1 × 2 × 3 × 4, ...]
```

可能令人惊讶的是，这种计算是可以并行化的。首先，如此处所示，合并相邻元素：

```
[1, 1 × 2, 3, 3 × 4, 5, 5 × 6, 7, 7 × 8]
```

灰色的值保持不变。显然，可以在数组的不同区域并发地进行此计算。在下一步中，通过将被指示的元素与其下方一个或两个位置的元素相乘来更新这些元素：

```
[1, 1 × 2, 1 × 2 × 3, 1 × 2 × 3 × 4, 5, 5 × 6, 5 × 6 × 7, 5 × 6 × 7 × 8]
```

这可以再次并发完成。在经过`log(n)`步后，过程完成。如果有足够的处理器，这将比直接的线性计算更具优势。

在本次练习中，你将使用`parallelPrefix`方法来并行化斐波那契数的计算。我们利用第*nth*个斐波那契数是`F^n`的左上角系数，其中`F = ( 1 1 1 0 )`。创建一个填充了 2 × 2 矩阵的数组。定义一个带有乘法方法的`Matrix`类，使用`parallelSetAll`创建一个矩阵数组，并使用`parallelPrefix`将它们相乘。

5. 编写一个示例，演示不可变类构造函数中`this`的逃逸问题（参见第 10.3.3 节）。尝试想出一个令人信服且可怕的例子。如果你使用事件监听器（如 Web 许多示例所示），它应该监听某些有趣的事情，但这对于不可变类来说并不容易。

6. 编写一个应用程序，其中多个线程从文件集合读取所有单词。使用`ConcurrentHashMap<String, Set<File>>`来跟踪每个单词出现在哪些文件中。使用`merge`方法更新映射。

7. 重复前面的练习，但改用`computeIfAbsent`。这种方法的方法的优势是什么？

8. 在`ConcurrentHashMap<String, Long>`中，找到值最大的键（任意打破平局）。提示：`reduceEntries`。

9. 生成 1,000 个线程，每个线程将计数器累加 100,000 次。比较使用`AtomicLong`与`LongAdder`的性能。

10. 使用`LongAccumulator`来计算累加元素的最大值或最小值。

11. 使用阻塞队列（blocking queue）处理目录中的文件。一个线程遍历文件树并将文件插入队列。多个线程移除文件，并在每个文件中搜索给定的关键词，打印任何匹配项。当生产者完成后，它应该向队列中放入一个占位文件。

12. 重复前面的练习，但让每个消费者编译一个单词及其频率的映射，并将其插入第二个队列中。最后一个线程合并字典并打印前十常见的单词。为什么你不需要使用`ConcurrentHashMap`？

13. 重复前面的练习，为每个文件创建一个`Callable<Map<String, Integer>>`并使用适当的执行服务。当所有结果都可用时合并结果。为什么你不需要使用`ConcurrentHashMap`？

14. 使用`ExecutorCompletionService`替之，并在结果一旦可用时立即合并结果。

15. 重复前面的练习，使用全局`ConcurrentHashMap`来收集单词频率。

16. 重复前述的练习，使用并行流（parallel streams）。任何流操作都不应该有任何副作用。

17. 编写一个程序遍历目录树并为每个文件生成一个线程。在线程中，统计文件的单词数，并在不使用锁的情况下，更新声明如下的共享计数器：

```
public static long count = 0;
```

多次运行该程序。发生了什么？为什么？

18. 使用锁（lock）修复前面的程序。

19. 使用`LongAdder`修复前面的程序。

20. 考虑以下栈实现：

```
public class Stack {
    class Node { Object value; Node next; };
    private Node top;
    public void push(Object newValue) {
        Node n = new Node();
        n.value = newValue;
        n.next = top;
        top = n;
    }
    public Object pop() {
        if (top == null) return null;
        Node n = top;
        top = n.next;
        return n.value;
    }
}
```

说明该数据结构无法包含正确元素的两种方式。

21. 考虑以下队列实现：

```
public class Queue {
    class Node { Object value; Node next; };
    private Node head;
    private Node tail;
    public void add(Object newValue) {
        Node n = new Node();
        if (head == null) head = n;
        else tail.next = n;
        tail = n;
        tail.value = newValue;
    }
    public Object remove() {
        if (head == null) return null;
        Node n = head;
        head = n.next;
        return n.value;
    }
}
```

说明该数据结构无法包含正确元素的两种方式。

22. 这段代码片段有什么问题？

```
public class Stack {
    private Object myLock = "LOCK";
    public void push(Object newValue) {
        synchronized (myLock) {
            ...
        }
    }
    ...
}
```

23. 这段代码片段有什么问题？

```
public class Stack {
    public void push(Object newValue) {
        synchronized (new ReentrantLock()) {
            ...
        }
    }
    ...
}
```

24. 这段代码片段有什么问题？

```
public class Stack {
    private Object[] values = new Object[10];
    private int size;
    public void push(Object newValue) {
        synchronized (values) {
            if (size == values.length)
                values = Arrays.copyOf(values, 2 * size);
            values[size] = newValue;
            size++;
        }
    }
    ...
}
```

25. 编写一个程序，询问用户 URL，读取该 URL 的网页并显示所有链接。为每一步使用`CompletableFuture`。不要调用`get`。

26. 使用两个线程编写一个演示死锁的程序。

27. 使用单个线程编写一个演示死锁的程序。提示：`join`。

28. 编写一个方法

```
public static <T> CompletableFuture<T> repeat(
   Supplier<T> action, Predicate<T> until)
```



异步重复执行`action`，直到产生一个`until`函数接受的值，该函数也应该异步运行。使用一个从控制台读取`java.net.PasswordAuthentication`的函数，以及一个模拟有效性检查的函数（睡眠一秒后检查密码是否为`"secret"`）进行测试。提示：使用递归。

##我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。29. 实现异步供应方法

实现一个静态方法`CompletableFuture<T> supplyAsync(Supplier<T> action, Executor exec)`。该方法返回一个`CompletableFuture<T>`子类的实例，只要任务正在运行，其`cancel`方法就可以中断执行`action`方法的线程。

在`Runnable`内部，捕获当前线程，然后调用`action.get()`，并用结果或异常完成`CompletableFuture`。

## 30. 组合可完成的 Future

方法：

```java
static CompletableFuture<Void> CompletableFuture.allOf(CompletableFuture<?>... cfs)
```

不会返回参数的结果，这使得使用起来变得有些繁琐。实现一个方法，将相同类型的可完成 future 类（completable futures）组合：

```java
static <T> CompletableFuture<List<T>> allOf(List<CompletableFuture<T>> cfs)
```

注意，该方法有一个`List<T>`参数，因为你不能对泛型类型使用变长参数。

## 31. 并发搜索

方法：

```java
static CompletableFuture<Object>
    CompletableFuture.anyOf(CompletableFuture<?>... cfs)
```

在任何参数完成（无论是正常完成还是异常完成）时就会返回。这与`ExecutorService.invokeAny`有显著区别，后者会一直持续直到某个任务成功完成，这阻止了该方法用于并发搜索。

实现一个方法：

```java
static CompletableFuture<T> anyOf(List<Supplier<T>> actions, Executor exec)
```

返回第一个实际结果，如果所有操作都带异常完成，则返回`NoSuchElementException`。

# 11. 注解（Annotations）

注解是你插入到源代码中的标记，以便某些工具可以对它们进行处理。这些工具可以在源码级别进行操作，也可以对编译器已在类文件中放置了注解的类文件进行处理。

注解不会改变你程序的编译方式。无论是否有注解，Java 编译器生成的虚拟机指令都是相同的。

要从注解中获益，你需要先选择一个处理工具，并使用该处理工具能够理解的注解，然后将该工具应用到你的代码中。

注解有广泛用途。例如，JUnit 使用注解来标记执行测试的方法，并指定如何运行测试。Java 持久化体系（JPA）使用注解来定义类与数据库表之间的映射，这样对象就可以自动持久化，而无需开发者编写 SQL 查询语句。

在本章中，你将学习注解语法的细节、如何定义自己的注解，以及如何编写在源码级别或运行时运行的注解处理器。

## 本章要点

1. 你可以像使用`public`或`static`等修饰符一样对声明进行注解。
2. 你还可以注解出现在声明、强制转换、`instanceof`检查或方法引用的类型。
3. 注解以`@`符号开头，并可能包含称为元素的键值值对。
4. 注解值必须是编译时常量：原始类型、`enum`常量、`Class`字面量、其他注解或这些元素的数组。
5. 一个项可以有重复的注解或不同类型的注解。
6. 要定义注解，请指定一个注解接口，其方法与注解元素对应。
7. Java 库定义了十余种注解，注解在 Java 企业版中被广泛使用。
8. 要在运行的 Java 程序中处理注解，你可以使用反射并查询反射项的注解。
9. 注解处理器在编译期间处理源文件，使用 Java 语言模型 API 来定位被注解的项。

## 11.1. 使用注解

这里是一个简单注解的示例：

```java
public class CacheTest {

    ...

    @Test public void checkRandomInsertions()

}
```

`@Test`注解注解了`checkRandomInsertions`方法。在 Java 中，注解的使用类似于修饰符（如`public`或`static`）。每个注解的名称之前都有一个`@`符号。

`@Test`注解本身什么都不做。它需要工具才能发挥作用。例如，JUnit 4 测试工具（可在[`http://junit.org`](http://junit.org)获取）在测试类时会调用所有标记为`@Test`的方法。另一个工具可能会从类文件中移除所有测试方法，以便它们在程序测试后不会随程序一起发布。

### 11.1.1. 注解元素（Annotation Elements）

注解可以拥有称为元素的键值对，例如：

```java
@Test(timeout=10000)
```

允许的元素名称和类型由每个注解定义（参见第 11.2 节）。读取注解的工具可以处理这些元素。

注解元素是以下内容之一：

- 原始类型值
- `String`
- `Class`对象
- `enum`实例
- 注解
- 前述元素的数组（但不是数组的数组）

例如：

```java
@BugReport(showStopper=true,
    assignedTo="Harry",
    testCase=CacheTest.class,
    status=BugReport.Status.CONFIRMED)
```

> **注意**
>
> 注解元素永远不能有`null`值。

元素可以有默认值。例如，JUnit 的`@Test`注解的`timeout`元素默认值为`0L`。因此，注解`@Test`等同于`@Test(timeout=0L)`。

如果元素名称为`value`，且该元素是你指定的唯一元素，你可以省略`value=`。例如，`@SuppressWarnings("unchecked")`等同于`@SuppressWarnings(value="unchecked")`。

如果元素值是一个数组，请将其组件封装在大括号中：

```java
@BugReport(reportedBy={"Harry", "Fred"})
```

如果数组只有一个组件，可以省略大括号：

```java
@BugReport(reportedBy="Harry")
```

一个注解元素可以是另一个注解：

```java
@BugReport(ref=@Reference(id=11235811), ...)
```

> **注意**
>
> 由于注解由编译器处理，所有元素值必须是编译时常量。

### 11.1.2. 多重重复注解

一个项可以有多个注解：

```java
@Test
@BugReport(showStopper=true, reportedBy="Joe")
public void checkRandomInsertions()
```

如果注解作者声明它是可重复的，你可以多次重复同一个注解：

```java
@BugReport(showStopper=true, reportedBy="Joe")
@BugReport(reportedBy={"Harry", "Carl"})
public void checkRandomInsertions()
```

### 11.1.3. 注解声明

到目前为止，你已经看到注解应用于方法声明。注解可以在许多其他地方出现。它们分为两类：*声明*和*类型使用*。声明注解可以出现在以下声明处：

- 类（包括`enum`）和接口（包括注解接口）
- 方法
- 构造方法
- 实例变量（包括`enum`常量）
- 局部变量（包括声明在`for`和 try-with-resources 语句中的变量）
- 参数变量和`catch`子句参数
- 类型参数
- 包

对于类和接口，将注解放在`class`或`interface`关键字以及任何修饰符之前：

```java
@Entity public class User { ... }
```

对于变量，将它们放在类型之前：

```java
@SuppressWarnings("unchecked") List<User> users = ...;

public User getUser(@Param("id") String userId)
```

泛型类或方法中的类型参数可以这样注解：

```java
public class Cache<@Immutable V> { ... }
```

包在`package-info.java`文件中进行注解，该文件仅包含由注解引导的包语句。

```java
/**
    包级 Javadoc
*/

@GPL(version="3")

package com.horstmann.corejava;

import org.gnu.GPL;
```

请注意，该注解的`import`语句位于`package`声明*之后*。

### 注意

本地变量和包的注解在类被编译时会被丢弃。因此，它们只能在源码级别进行处理。

### 11.1.4. 对类型使用进行注解

声明注解提供了关于被声明项的某些信息。例如，在如下声明中：

```java
public User getUser(@NonNull String userId)
```

它断言`userId`参数不为 null。

> **Note**
>
> `@NonNull`注解是 Checker Framework（[`http://types.cs.washington.edu/checker-framework`](http://types.cs.washington.edu/checker-framework)）的一部分。通过该框架，你可以在程序中包含断言，例如参数非`null`或`String`包含正则表达式。静态分析工具随后会检查这些断言在给定的源代码体中是否有效。

现在假设我们有一个类型为`List<String>`的参数，我们想表示所有的字符串都非`null`。这就是类型使用注解的用场。在类型参数之前放置注解：`List<@NonNull String>`。

类型使用注解可以出现在以下位置：

- 泛型类型参数中：`List<@NonNull String>`、`Comparator.<@NonNull String> reverseOrder()`。
- 数组的任何位置：`@NonNull String[][] words`（`words[i][j]`不为`null`）、`String @NonNull [][] words`（`words`不为`null`）、`String[] @NonNull [] words`（`words[i]`不为`null`）。
- 超类和实现的接口：`class Warning extends @Localized Message`。
- 构造函数调用：`new @Localized String(...)`。
- 嵌套类型：`Map.@Localized Entry`。
- 转换和`instanceof`检查：`(@Localized String) text`、`if (text instanceof @Localized String)`。（这些注解仅供外部工具使用。它们对转换或`instanceof`检查的行为没有影响。）
- 异常规范：`public String read() throws @Localized IOException`。
- 通配符和类型边界：`List<@Localized ? extends Message>`、`List<? extends @Localized Message>`。
- 方法和构造函数引用：`@Localized Message::getText`。

有几个类型位置不能注解：

```java
@NonNull String.class // 错误—无法对类字面量注解

import java.lang.@NonNull String; // 错误—无法对 import 注解
```

你可以将注解放在`private`和`static`等其他修饰符之前或之后。习惯上（但不是）将类型使用注解放在其他修饰符之后，将声明注解放在其他修饰符之前。例如：

```java
private @NonNull String text; // 注解类型使用

@Id private String userId; // 注解变量
```

> **Note**
>
> 正如你将在第 11.2 节中看到的，注解作者需要指定特定注解可以出现在哪里。如果一个注解既允许用于变量也允许用于类型使用，并且它被用于变量声明，那么变量和类型使用都会被注解。例如，考虑：

```java
public User getUser(@NonNull String userId)
```

如果`@NonNull`同时可以应用于参数和类型使用，那么`userId`参数被注解了，且参数类型为`@NonNull String`。

### 11.1.5. 使接收者显式化

假设你想对那些没有被方法修改的参数进行注解：

```java
public class Point {

    public boolean equals(@ReadOnly Object other) { ... }

}
```

那么，处理此注解的工具在看到如下调用时：

```java
p.equals(q)
```

会推断`q`没有改变。

但`p`呢？

当方法被调用时，接收者变量`this`被绑定到`p`，但`this`永远不会声明，因此你无法对它进行注解。

实际上，你可以使用一种很少使用的语法变体来声明它，以便你能够添加注解：

```java
public class Point {

    public boolean equals(@ReadOnly Point this, @ReadOnly Object other) { ... }

}
```

第一个参数被称为*接收者参数*（receiver parameter）。它必须命名为`this`。它的类型是正在构造的类。

> **Note**
>
> 你只能为方法提供接收者参数，而不能为构造函数提供。从概念上讲，构造函数中的`this`引用在构造完成之前并不是给定类型的对象。相反，放置在构造函数上的注解描述了构造对象的属性。

另一个隐藏参数被传递给内部类的构造函数，即对外部类对象的引用。你也可以让这个参数显式化：

```java
static class Sequence {

    private int from;

    private int to;

    class Iterator implements java.util.Iterator<Integer> {

        private int current;

        public Iterator(@ReadOnly Sequence Sequence.this) {

            this.current = Sequence.this.from;

        }

        ...

    }

    ...

}
```

参数必须命名为`this`，其类型是外部类。

## 11.2. 定义注解

每个注解必须通过`interface`声明。接口中的方法对应于注解的元素。例如，JUnit 注解定义如下：

```java
@Target(ElementType.METHOD)

@Retention(RetentionPolicy.RUNTIME)

public @interface Test {

    long timeout();

    ...

}
```



`@interface` 创建了一个实际接口。处理注解的工具接收实现该接口的对象。当运行器获取实现`Test`的对象时，它只需调用`timeout`方法来检索`Test`的元素。

注解中的元素声明实际上是方法声明。注解的方法不能有`throws`子句，且不能是泛型的。

`@Target`和`@Retention`注解是元注解。它们注解`Test`注解，指示注解可以出现的地方以及可以访问的地方。

`@Target`元注解的值是`ElementType`对象的数组，指定了注解可以应用的项。你可以指定任意数量的元素类型，并括在大括号中。例如：

编译器检查你是否只在允许的地方使用注解。例如，如果你将`@BugReport`应用于变量，会导致编译错误。

#### Note
没有`@Target`限制的注解可以用于任何声明，但不能用于类型参数和类型使用。（这些是支持注解的 Java 版本中所有可能的目标。）

表 11.1：`@Target`注解的元素类型

![Images](img/tab11-01.jpg)

`@Retention`元注解指定了注解可以在哪里被访问。有三种选择：

1. `RetentionPolicy.SOURCE`：注解源码处理器可用，但不包含在类文件中。
2. `RetentionPolicy.CLASS`：注解包含在类文件中，但虚拟机不会加载它们。这是默认值。
3. `RetentionPolicy.RUNTIME`：注解在运行时可用，可以通过反射 API 访问。

你将在本章晚些部分看到这三种场景的示例。

还有其他元注解——完整列表请参阅第 11.3 节。

要为某个元素指定默认值，可以在定义该元素的方法之后添加一个`default`子句。例如：

```
public @interface Test {

    long timeout() default 0L;

    ...

}
```

此示例展示了如何指定空数组的默认值以及注解的默认值：

```
public @interface BugReport {

    String[] reportedBy() default {};
        // 默认为空数组

    Reference ref() default @Reference(id=0);
        // 注解的默认值

    ...

}
```

### 注意事项

默认值并不存储在注解中，而是动态计算的。如果你更改了默认值并重新编译了注解类，那么所有已注解的元素将使用新的默认值，即使是在默认值更改之前已经编译过的类文件中也是如此。

你不能扩展注解接口，永远永远提供实现注解接口的类。相反，源处理工具和虚拟机会在需要时生成代理类和对象。

### 11.3. 标准注解

Java API 在`java.lang`、`java.lang.annotation`和`javax.annotation`包中定义了许多注解接口。其中四个是元注解，用于描述注解接口的行为。其他的是普通注解，你用它们来标记源代码中的项。表 11.2 显示了这些注解。我将在接下来的两个节中详细讨论它们。

表 11.2：标准注解

![Images](img/tab11-02.jpg)

#### 11.3.1. 用于编译的注解

`@Deprecated`注解可以附加到任何不再鼓励使用的项。当你使用已弃项时，编译器会发出。该注解的作用与`@deprecated` Javadoc 标签相同，但该注解会持续到运行时。

### 注意

JDK 的一部分`jdeprscan`工具可以扫描一组 JAR 文件中的已弃元素。

`@Override`注解使编译器检查被注解的方法是否确实重写了父类中的方法。例如，如果你声明了

```java
public class Point {

    @Override public boolean equals(Point other) { ... }

    ...

}
```

那么编译器将报告错误——此`equals`方法没有重写`Object`类的`equals`方法，因为该方法的参数类型是`Object`而不是`Point`。

`@Serial`注解检查用于序列化的方法（未在接口中声明的方法）是否具有正确的参数类型。

`@SuppressWarnings`注解告诉编译器抑制特定类型的警告，例如：

```java
@SuppressWarnings("unchecked") T[] result

    = (T[]) Array.newInstance(cl, n);
```

`@SafeVarargs`注解断言方法不会破坏其可变长度参数（参见第 6 章）。

`@Generated`注解旨在供代码生成工具使用。任何生成的源代码都可以被注解，以将其与程序员提供的代码区分来。例如，代码编辑器可以隐藏生成的代码，或者代码生成器可以移除旧版本的生成代码。每个注解必须包含一个用于代码生成器的唯一标识符。日期字符串（ISO 8601 格式）和注释字符串是可选的。例如：

```java
@Generated(value="com.horstmann.generator",

    date="2015-01-04T12:08:56.235-0700");
```

你已经在第 3 章中见过`FunctionalInterface`注解。它用于标记 lambda 表达式的转换目标，例如：

```java
@FunctionalInterface

public interface IntFunction<R> {

    R apply(int value);

}
```

如果你之后添加了另一个抽象方法，编译器将产生错误。

当然，你应该只对描述函数的接口添加此注解。还有其他只有一个抽象方法的接口（例如`AutoCloseable`），但它们在概念上并不是函数。

#### 11.3.2. 元注解

你已经在第 11.2 节中见过了`@Target`和`@Retention`元注解。

`@Documented`元注解为 Javadoc 等文档工具提供提示。出于文档目的，被标记的注解应该被视为与其他修饰符（如`private`或`static`）相同。相比之下，其他注解不应包含在文档中。

例如，`@SuppressWarnings`注解是不被记录的。如果一个方法或字段有该注解，它是一个实现细节，对 Javadoc 阅读者没有。另一方面，`@FunctionalInterface`注解是被记录的，因为对于程序员来说，知道接口旨在描述函数是有用的。图 11.1 显示了该文档。

![Images](img/fig11-01.jpg)

图 11.1：被记录的注解

`@Inherited`元注解仅适用于类的注解。当一个类具有继承的注解时，其所有子类都自动拥有相同的注解。这使得创建类似于标记接口（如`Serializable`接口）的注解变得简单。

假设你定义了一个继承注解`@Persistent`，表示类的对象可以保存到数据库中。那么持久化类的子类会自动被标记为持久化。

```java
@Inherited @interface Persistent { }

@Persistent class Employee { ... }

class Manager extends Employee { ... } // 也是 @Persistent
```

`@Repeatable`元注解允许多次应用同一个注解。例如，假设`@TestCase`注解是可重复的。那么可以像这样使用：

```java
@TestCase(args="4", expected="24")

@TestCase(args="0", expected="1")

public static long factorial(int n) { ... }
```

出于历史原因，可重复注解的实现者需要提供一个容器注解，将重复的注解存储在一个数组中。

以下是定义`@TestCase`注解及其容器的方式：

```java
@Repeatable(TestCases.class)

@interface TestCase {

    String args();

    String expected();

}

@interface TestCases {

    TestCase[] value();

}
```

每当用户提供两个或多个`@TestCase`注解时，它们会自动封装成一个`@TestCases`注解。这增加了处理注解的复杂度，正如你将在下一节中看到的那样。

### 11.4. 在运行时处理注解

到目前为止，你已经学习了如何在源文件中添加注解以及如何定义注解类型。现在是时候看看这些能产生什么好处了。

在本节中，我向你展示如何使用你在第 4 章中见过的反射 API 在运行时处理注解的简单示例。假设我们想减少实现`toString`方法的繁琐。当然，可以使用反射编写一个通用的`toString`方法，简单地包含所有的实例变量名和值。但假设我们想自定义该过程。我们可能不想包含所有的实例变量，或者我们想跳过类名和变量名。例如，对于`Point`类，我们可能更喜欢`[5,10]`而不是`Point[x=5,y=10]`。当然，任何其他改进都是可能的，但让我们保持简单。重点是演示注解处理器可以做什么。

用`@ToString`注解标记所有想要从此服务中受益的类。此外，所有应该包含的实例变量也需要标记。该注解定义如下：

```java
@Target({ElementType.FIELD, ElementType.TYPE})

@Retention(RetentionPolicy.RUNTIME)

public @interface ToString {

    boolean includeName() default true;

}
```

这里是经过注解的`Point`和`Rectangle`类：

```java
@ToString(includeName=false)

public class Point {

    @ToString(includeName=false) private int x;

    @ToString(includeName=false) private int y;

    ...

}

@ToString

public class Rectangle {

    @ToString(includeName=false) private Point topLeft;

    @ToString private int width;

    @ToString private int height;

    ...

}
```

这里的意图是将矩形表示为字符串`Rectangle[[5, 10],width=20,height=30]`。

在运行时，我们无法修改给定类`toString`方法的实现。相反，让我们提供一个可以格式化任何对象的方法，在存在`ToString`注解时发现并使用它们。

关键在于`AnnotatedElement`接口中的这些方法：

```
T getAnnotation(Class<T>)

T getDeclaredAnnotation(Class<T>)

T[] getAnnotationsByType(Class<T>)

T[] getDeclaredAnnotationsByType(Class<T>)

Annotation[] getAnnotations()

Annotation[] getDeclaredAnnotations()
```

反射类`Class`、`Field`、`Parameter`、`Method`、`Constructor`和`Package`都实现了该接口。

与其他反射方法一样，名称中带有`Declared`的方法产生类本身中的注解，而其他方法则包含继承的注解。在注解的语境下，这意味着该注解是`@Inherited`并且应用到了父类上。

如果一个注解不是重复的，调用`getAnnotation`来定位它。例如：

```
Class cl = obj.getClass();

ToString ts = cl.getAnnotation(ToString.class);

if (ts != null && ts.includeName()) ...
```

注意，你传递的是注解的类对象（这里是`ToString.class`），并且你返回的是一个实现了`ToString`接口的某个代理类的对象。然后你可以调用该接口的方法来获取注解元素的值。如果注解不存在，`getAnnotation`方法将返回`null`。

如果注解是重复的，情况就会变得有点复杂。如果你调用`getAnnotation`来查找一个重复注解，而该注解实际上是重复的，那么你也会得到`null`。这是因为重复的注解被封装在容器注解内部。

在这种情况下，你应该调用`getAnnotationsByType`。该调用会“透视”容器并给你一个包含重复注解的数组。如果只有一个注解，你将得到一个长度为 1 的数组。通过这种方法，你就不需要担心容器注解。

`getAnnotations`方法获取所有标记在某项元素上的注解（任何类型），其中重复的注解被封装在容器中。

以下是感知注解的`toString`方法的实现：

```java
public class ToStrings {

    public static String toString(Object obj) {

        if (obj == null) return "null";

        Class<?> cl = obj.getClass();

        ToString ts = cl.getAnnotation(ToString.class);

        if (ts == null) return obj.toString();

        var result = new StringBuilder();

        if (ts.includeName()) result.append(cl.getName());

        result.append("[");

        boolean first = true;

        for (Field f : cl.getDeclaredFields()) {

            ts = f.getAnnotation(ToString.class);

            if (ts != null) {

                if (first) first = false; else result.append(",");

                f.setAccessible(true);

                if (ts.includeName()) {

                    result.append(f.getName());

                    result.append("=");

                }

                try {

                    result.append(ToStrings.toString(f.get(obj)));

                } catch (ReflectiveOperationException ex) {

                    ex.printStackTrace();

                }

            }

        }

        result.append("]");

        return result.toString();

    }

}
```

当一个类被标记了`ToString`时，该方法会遍历它的字段并打印那些也被标记了注解的字段。如果`includeName`元素为`true`，则字符串中将包含类名或字段名。

注意该方法会递归调用自己。当对象属于一个未标记注解的类时，将使用其普通的`toString`方法并且递归停止。

这是运行时注解 API 一个简单但典型的用法。使用反射查找类、字段等；在可能带有注解的元素上调用`getAnnotation`或`getAnnotationsByType`以检索注解；然后调用注解接口的方法来获取元素值。

### 11.5. 源码级注解处理

在上一节中，你已经了如何分析运行中程序中的注解。注解的另一种用途是自动处理源文件以产生更多的源代码、配置文件、脚本或任何你可能想要生成的内容。

为了向你展示这种机制，我将重复生成`toString`方法的示例。但是，这次我们在 Java 源码中生成它们。这样这些方法将与程序的其余部分一起编译，并以全速运行，而不是使用反射。

#### 11.5.1 注解处理器

注解处理集成在 Java 编译器中。在编译期间，你可以通过运行以下命令调用注解处理器：

```bash
javac -processor ProcessorClassName1, ProcessorClassName2,... sourceFiles
```

编译器会定位源文件的注解。每个注解处理器按顺序执行，并获得它感兴趣的注解。如果注解处理器创建了新的源文件，则重复该过程。一旦某轮处理不再产生更多的源文件，所有源文件都将被编译。

**注意**

注解处理器只能生成新的源文件。它不能修改现有的源文件。

注解处理器实现`Processor`接口，通常通过扩展`AbstractProcessor`类来实现。你需要指定你的处理器支持的注解。在我们的用例中：

```java
@SupportedAnnotationTypes("com.horstmann.annotations.ToString")
```



@SupportedSourceVersion(SourceVersion.RELEASE_8)

public class ToStringAnnotationProcessor extends AbstractProcessor {

    @Override

    public boolean process(Set<? extends TypeElement> annotations,

            RoundEnvironment currentRound) {

        ...

    }

}

```

处理器可以声明特定的注解类型、通配符如 `"com.horstmann.*"`（`comhorstmann` 包或任何子包中的所有注解），甚至是 `"*"`（所有注解）。

`process` 方法每轮会被调用一次，参数是该轮次在任何文件中找到的所有注解集合，以及一个包含当前处理轮次信息的 `RoundEnvironment` 引用。

#### 11.5.2 语言模型 API

你使用语言模型 API 来分析源码级注解。反射 API 提供的是类和方法的虚拟机表示，语言模型 API 则允许你根据 Java 语言规则分析 Java 程序。

编译器产生一棵树，其节点是 `javax.lang.model.element.Element` 接口及其子接口 `TypeElement`、`VariableElement`、`ExecutableElement` 等类的实例。这些是反射类 `Class`、`Field`/`Parameter`、`Method`/`Constructor` 的编译时对应物。

我不想详细介绍该 API，但这里有你在处理注解时需要的要点。

![images](img/sq.jpg) `RoundEnvironment` 允许你通过调用方法获取带有特定注解的元素集合：

```java

Set<? extends Element> getElementsAnnotatedWith(Class<? extends Annotation> a)

Set<? extends Element> getElementsAnnotatedWithAny(

    Set<Class<? extends Annotation>> annotations)

        // 用于重复注解

```

![images](img/sq.jpg) `AnnotateElement` 接口的源码等效类型是 `AnnotatedConstruct`。你可以使用以下方法

```

 A getAnnotation(Class<A> annotationType)

A[] getAnnotationsByType(Class<A> annotationType)

```

来获取指定注解类的注解或重复注解。

![images](img/sq.jpg) `TypeElement` 代表一个类或接口。`getEnclosedElements` 方法返回其字段和方法的列表。

![images](img/sq.jpg) 在 `Element` 上调用 `getSimpleName` 或在 `TypeElement` 上调用 `getQualifiedName` 会产生一个 `Name` 对象，该对象可以通过 `toString` 转换为字符串。

### 11.5.3. 使用注解生成源代码

让我们回到自动生成 `toString` 方法的任务。我们无法将这些方法放入原始类中——注解处理器只能产生新类，而不能修改现有的类。

因此，我们将所有方法添加到工具类 `ToStrings` 中：

```

public class ToStrings {

    public static String toString(Point obj) {

        Generated code

    }

    public static String toString(Rectangle obj) {

        Generated code

    }

    ...

    public static String toString(Object obj) {

        return Objects.toString(obj);

    }

}

```

由于我们不想使用反射，所以我们注解访问器方法，而不是字段：

```

@ToString

public class Rectangle {

    ...

    @ToString(includeName=false) public Point getTopLeft() { return topLeft; }

    @ToString public int getWidth() { return width; }

    @ToString public int getHeight() { return height; }

}

```

注解处理器随后应该生成以下源代码：

```

public static String toString(Rectangle obj) {

    var result = new StringBuilder();

    result.append("Rectangle");

    result.append("[");

    result.append(toString(obj.getTopLeft()));

    result.append(",");

    result.append("width=");

    result.append(toString(obj.getWidth()));

    result.append(",");

    result.append("height=");

    result.append(toString(obj.getHeight()));

    result.append("]");

    return result.toString();

}

```

灰色部分是“样板”代码。以下是为给定 `TypeElement` 的类生成 `toString` 方法的逻辑概述：

```

private void writeToStringMethod(PrintWriter out, TypeElement te) {

    String className = te.getQualifiedName().toString();

    Print method header and declaration of string builder

    ToString ann = te.getAnnotation(ToString.class);

    if (ann.includeName()) Print code to add class name

    for (Element c : te.getEnclosedElements()) {

        ann = c.getAnnotation(ToString.class);

        if (ann != null) {

            if (ann.includeName()) Print code to add field name

            Print code to append toString(obj. methodName())

        }

    }

    Print code to return string

}

```

这里是注解处理器的 `process` 方法的概述。它为辅助类创建一个源文件，并为每个被注解的类写入类头和和一个方法。

```

public boolean process(Set<? extends TypeElement> annotations,

        RoundEnvironment currentRound) {

    if (annotations.size() == 0) return true;

    try {

        JavaFileObject sourceFile = processingEnv.getFiler().createSourceFile(

            "com.horstmann.annotations.ToStrings");

        try (var out = new PrintWriter(sourceFile.openWriter())) {

            Print code for package and class

            for (Element e : currentRound.getElementsAnnotatedWith(ToString.class)) {

                if (e instanceof TypeElement te) {

                    writeToStringMethod(out, te);

                }

            }

            Print code for toString(Object)

        } catch (IOException ex) {

            processingEnv.getMessager().printMessage(

                Kind.ERROR, ex.getMessage());

        }

    }

    return true;

}

```

欲了解细节，请查看书中的配套代码。

注意，`process` 方法在随后的轮次中会被空注解列表被调用。它会立即返回，因此不会重复创建源文件。

**提示**

要查看轮次，请运行带有 `-XprintRounds` 标志的 `javac` 命令：

```

Round 1:

  input files: {ch11.sec05.Point, ch11.sec05.Rectangle,

    ch11.sec05.SourceLevelAnnotationDemo}

  annotations: [com.horstmann.annotations.ToString]

  last round: false

Round 2:

  input files: {com.horstmann.annotations.ToStrings}

  annotations: []

  last round: false

Round 3:

  input files: {}

  annotations: []

  last round: true

```

此示例演示了工具如何收集源文件注解以产生其他文件。生成的文件并不必须是源文件。注解处理器可以选择生成 XML 描述符、属性文件、壳脚本、HTML 文档等。

**注意**

你现在已经看到了如何处理源文件和运行程序中的注解。第三种可能性是在类文件中处理注解，通常是在将它们加载到虚拟机时动态处理。你需要一个如 `ASM` (`[`asm.ow2.org``](http://asm.ow2.org)) 的工具来定位并评估注解并重写字节码。

### 练习

1. 描述如何修改 `Object.clone` 以使用 `@Cloneable` 注解代替 `Cloneable` 接口。
2. 如果注解在 Java 早期版本中存在，那么 `Serializable` 接口肯定会被注解。实现一个 `@Serializable` 注解。选择一种文本或二进制格式进行持久化。提供通过保存和恢复所有原始值或可序列化字段来持久化对象的类。暂时不要考虑循环引用。
3. 重复之前的作业，但考虑循环引用。
4. 为你的序列化机制添加一个类似于 `transient` 修饰符的 `@Transient` 注解。
5. 定义一个包含描述要做事项的 `@Todo` 注解。从源文件生成一个提醒列表。包含项目的描述和 todo 消息。
6. 将上述练习的注解改为重复注解。
7. 如果注解在 Java 早期版本中存在，它们可能会取代 Javadoc 的角色。定义 `@Param`、`@Return` 等注解，并使用注解处理器从生成基础 HTML 文档。
8. 实现 `@TestCase` 注解，生成一个源文件，其名称为注解所在类的名称加上 `Test`。例如，如果 `MyMath.java` 包含

```

 @TestCase(args="4", expected="24")

@TestCase(args="0", expected="1")

public static long factorial(int n) { ... }

```

则生成文件 `MyMathTest.java`，包含语句

```

 assert(MyMath.factorial(4) == 24);

 assert(MyMath.factorial(0) == 1);

```

你可以假设测试方法是静态的，且 `args` 包含正确类型的逗分隔列表。
9. 将 `@TestCase` 实现运行时注解并提供一个检查它的工具。同样，假设测试方法是静态的，并限制为注解元素中字符串描述的合理参数和返回类型。
10. 为 `@Resource` 注解实现一个处理器，它接受某个类的对象并寻找被 `@Resource(name="*URL*`")` 注解的 `String` 类型字段。然后加载 URL 并使用反射将该内容注入字符串变量。

时光如梭，我们可以轻松地设定一个起点，并在秒钟内向前向后计数。但为什么处理时间会这么困难呢？问题在于人类。如果我们能互相告诉对方：“在 1371409200 见，不要迟到！”那么一切都会简单。但我们希望时间与日光和季节相关。这让事情变得复杂。Java 1.0 有一个 `Date` 类，从回来看，它是很幼稚的，在 Java 1.1 引入 `Calendar` 类时，它的大部分方法都被废弃了。它的 API 并不理想，其实例是可变的，而且它没有处理闰秒等问题。第三次为宝，Java 8 中引入的 `java.time` API 弥补了过去的缺陷，并且应该足够我们使用很长时间。在本章中，你将学习为什么时间计算如此恼人，以及 Date 和 Time API 如何解决这些问题。

本章的要点是：

1. 所有的 `java.time` 对象都是不可变的。
2. `Instant` 是时间线上的一个点（类似于 `Date`）。
3. 在 Java 时间中，每天恰好有 86,400 秒（也就是说，没有闰秒）。
4. `Duration` 是两个瞬时之间的差值。
5. `LocalDateTime` 不包含时区信息。
6. `TemporalAdjuster` 方法处理常见的日历计算，例如找到某月的第一个星期二。
7. `ZonedDateTime` 是给定时区内的一个时间点（类似于 `GregorianCalendar`）。
8. 在推进时区时间时，使用 `Period` 而不是 `Duration`，以考虑夏令时间的变化。
9. 使用 `DateTimeFormatter` 格式化和解析日期与时间。

### 12.1 时间线

从历史角度看，基本的时间单位——秒——源于地球绕其自轴的旋转。一整圈有 24 小时或 24 × 60 × 60 = 86400 秒，因此精确定义一秒似乎只是天文学测量的问题。遗憾的是，地球会轻微晃动，需要更精确的定义。1967 年，根据 133 铯原子的固有属性，推导出了与历史定义匹配的新型精确秒定义。从那时起，原子钟网络一直维护着官方时间。

官方时间维护者经常会将绝对时间与地球旋转进行同步。起初，官方秒会经过微调，但从 1972 年开始，偶尔插入“闰秒”（在理论上，偶尔可能需要删除一秒，但这种情况尚未发生过）。目前有关于再次更改系统的说法。显然，闰秒是个麻烦，许多计算机系统改为使用“平滑处理”，即在闰秒之前人为地减慢或加速时间，保持每天 86,400 秒。这之所以有效，是因为计算机的本地时间并不精确，而且计算机习惯于与外部时间服务同步。

Java Date 和 Time API 规范要求 Java 使用满足以下条件的时间刻度：

![images](img/sq.jpg) 每天 86,400 秒

![images](img/sq.jpg) 每天中午与官方时间完全匹配

![images](img/sq.jpg) 在其他地方以精确定义的方式与其紧密匹配

这使得 Java 具有灵活性，可以适应未来官方时间的调整。

在 Java 中，`Instant` 代表时间线上的一个点。一个被称为 *epoch*（纪元）的起点被任意设定在 1970 年 1 月 1 日午夜，位于通过伦敦格林尼治皇家天文台的主午线上。这与 Unix/POSIX 时间使用的约定相同。从该起点开始，时间以每天 86,400 秒向前向后测量，精确到纳秒。`Instant` 的值可以追溯到十亿年前（`Instant.MIN`）。这不足以表达宇宙的年龄（约 135 亿年），但对于所有实际用途来说足够了。毕竟，十亿年前地球被冰雪覆盖，居住着今天植物动物的微型祖先。最大值 `Instant.MAX` 是 1,000,000,000 年 12 月 31 日。

静态方法调用 `Instant.now()` 提供当前瞬时。你可以像通常一样使用 `equals` 和 `compareTo` 方法比较两个瞬时，因此你可以将瞬时用时间戳。

要找出两个瞬时之间的差异，使用静态方法 `Duration.between`。例如，这里是你可以测量算法运行时间的方法：

```

Instant start = Instant.now();

runAlgorithm();

Instant end = Instant.now();

Duration timeElapsed = Duration.between(start, end);

long millis = timeElapsed.toMillis();



`Duration` 是两个瞬时之间的时间量。你可以通过调用`toNanos`、`toMillis`、`toSeconds`、`toMinutes`、`toHours`或`toDays`获取常规单位下的`Duration`长度。

相反，你可以通过静态方法之一`ofNanos`、`ofMillis`、`ofSeconds`、`ofMinutes`、`ofHours`、`ofDays`获取时长：

```
Duration oneWeek = Duration.ofDays(7);
long secondsPerWeek = oneWeek.toSeconds();
```

`Duration` 是两个瞬时之间的时间量。你可以通过调用`toNanos`、`toMillis`、`toSeconds`、`toMinutes`、`toHours`或`toDays`获取常规单位下的`Duration`长度。

相反，你可以通过静态方法`ofNanos`、`ofMillis`、`ofSeconds`、`ofMinutes`、`ofHours`、`ofDays`获取时长：

```
Duration oneWeek = Duration.ofDays(7);
long secondsPerWeek = oneWeek.toSeconds();
```

`Duration` 是两个瞬时之间的时间量。你可以通过调用`toNanos`、`toMillis`、`toSeconds`、`toMinutes`、`toHours`或`toDays`获取常规单位下的`Duration`长度。

与静态方法`ofNanos`、`ofMillis`、`ofSeconds`、`ofMinutes`、`ofHours`、`ofDays`。

与 Unix 和`java.util.Date`中的不规则约定不同（其中月份从 0 开始且年份从 1900 年计算），你提供月份的常用数字。或者，可以使用`Month`枚举。

### 12.2 本地日期

现在让我们从绝对时间转向人类时间。Java API 中有两种人类时间：*本地日期/时间*和*时区时间*。本地日期/时间有日期和或时间，但没有关联的时区信息。本地日期的一个例子是 1903 年 6 月 14 日（Lambda 演算发明者 Alonzo Church 的生日）。由于该日期既没有时间也没有时区信息，它并不对应一个精确的时间点。相比之下，1969 年 7 月 16 日 09:32:00 EDT（阿波罗 11 号的发射）是一个时区日期/时间，代表时间线上的一个精确瞬时。

在许多计算中不需要时区，在某些情况下它们甚至会成为阻碍。假设你安排每周在 10:00 开会。如果你在上次一次时区时间的基础上增加 7 天（即 7 × 24 × 60 × 60 秒），而你恰好跨过了夏令时间边界，那么会议将早一小时或晚一小时！

出于这个原因，API 设计者建议除非你真的想表示绝对时间实例，否则不要使用时区时间。生日、节日、日程时间等通常最好用本地日期或时间表示。

`LocalDate` 是一个带有年份、月份和日的日期。要构造它，你可以使用`now`或`of`静态方法：

```
LocalDate today = LocalDate.now(); // 今天的日期
LocalDate alonzosBirthday = LocalDate.of(1903, 6, 14);
alonzosBirthday = LocalDate.of(1903, Month.JUNE, 14);
    // 使用 Month 枚举
```

表 12.2 显示了处理`LocalDate`对象最有用的方法。

## 表 12.2: `LocalDate` 方法

![Images](img/tab12-02.jpg)![Images](img/tab12-02b.jpg)

例如，“程序员节”是每年的第 256 天。以下是轻松计算它的方法：

```
LocalDate programmersDay = LocalDate.of(2014, 1, 1).plusDays(255);
// 9 月 13 日，但在闰年中是 9 月 12 日
```

请记住，两个时间点之间的差值是`Duration`。对于本地日期，对应的类型是`Period`，它表示经过的年、月或天数。你可以调用`birthday.plus(Period.ofYears(1))`获取明年的生日。当然，你也可以直接调用`birthday.plusYears(1)`。但在闰年中，`birthday.plus(Duration.ofDays(365))`不会产生正确的结果。

`until`方法产生两个本地日期之间的差值。例如，

```
independenceDay.until(christmas)
```

产生一个 5 个月 21 天的周期。这实际上并没有非常用，因为每个月的天数不同。要查找天数，请使用：

```
independenceDay.until(christmas, ChronoUnit.DAYS) // 174 天
```

### 注意事项

表 12.2 中的某些方法可能会创建不存在的日期。例如，在 1 月 31 日增加一个月不应产生 2 月 31 日。这些方法并没有抛出异常，而是返回该月的最后一天。例如，

```
LocalDate.of(2016, 1, 31).plusMonths(1)
```

和

```
LocalDate.of(2016, 3, 31).minusMonths(1)
```

返回 2016 年 2 月 29 日。

`datesUntil`方法产生一个位于开始日期和结束日期之间的`LocalDate`对象流：

```
Stream<LocalDate> allDaysInMay2018
    = LocalDate.of(2018,5,1).datesUntil(LocalDate.of(2018,6,1));
Stream<LocalDate> allMondaysIn2018
    = LocalDate.of(2018,1,1).datesUntil(LocalDate.of(2019,1,1), Period.ofDays(7));
```

`getDayOfWeek`以`DayOfWeek`枚举类值的形式返回星期几。`DayOfWeek.MONDAY`的数值为`1`，`DayOfWeek.SUNDAY`的值为`7`。例如，

```
LocalDate.of(1900, 1, 1).getDayOfWeek().getValue()
```

产生`1`。`DayOfWeek`枚举提供了方便方法`plus`和`minus`来计算对模 7 的周几。例如，`DayOfWeek.SATURDAY.plus(3)`产生`DayOfWeek.TUESDAY`。

### 注意

周末实际上是在周末的最后。这与`java.util.Calendar`不同，在后者中周日的值为`1`，周六值为`7`。

除了`LocalDate`，之外还有`MonthDay`、`YearMonth`和`Year`类来描述部分日期。例如，12 月 25 日（不指定年份）可以表示为`MonthDay`。

## 12.3 日期调整器 (Date Adjusters)

对于调度应用程序，你通常需要计算如“每月第一个星期二”之类的日期。`TemporalAdjusters`类提供了许多用于常用调整的静态方法。将调整方法的结果传递给`with`方法。例如，可以这样计算一个月的第一个星期二：

```
LocalDate firstTuesday = LocalDate.of(year, month, 1).with(
    TemporalAdjusters.nextOrSame(DayOfWeek.TUESDAY));
```

一如既往，`with`方法返回一个新的`LocalDate`对象，而不修改原始对象。表 12.3 显示了可用的调整器。

## 表 12.3: `TemporalAdjusters` 类中的日期调整器

![Images](img/tab12-03.jpg)

你也可以通过实现`TemporalAdjuster`接口来创建自己的调整器。这里是一个计算下一个工作日的调整器：

```
TemporalAdjuster NEXT_WORKDAY = w -> {
    var result = (LocalDate) w;
    do {
        result = result.plusDays(1);
    } while (result.getDayOfWeek().getValue() >= 6);
    return result;
};
LocalDate backToWork = today.with(NEXT_WORKDAY);
```

注意，lambda 表达式的参数类型为`Temporal`，必须强制转换为`LocalDate`。你可以使用`ofDateAdjuster`方法来避免这种转换，它接受一个`UnaryOperator<LocalDate>`。在这里我们用 lambda 表达式指定调整器。

```
TemporalAdjuster NEXT_WORKDAY = TemporalAdjusters.ofDateAdjuster(w -> {
    LocalDate result = w; // 无需转换
    do {
        result = result.plusDays(1);
    } while (result.getDayOfWeek().getValue() >= 6);
    return result;
});
```

## 12.4 本地时间 (Local Time)

`LocalTime`代表一天中的某个时间，例如 15 点。你可以通过`now`或`of`方法创建实例。例如，

```
LocalTime now = LocalTime.now();
LocalTime bedtime = LocalTime.of(22, 30);
```

`LocalTime`不涉及上午/下午。表 12.4 显示了`plus`和`minus`的常用操作。例如，

```
LocalTime wakeup = bedtime.plusHours(8); // 第二天 06:30
```

## 12.5 时区 (Zoned Time)

时区虽然看起来反复，但完全是人类的产物。互联网分配机构（IANA）维护着所有已知时区的数据库（[`www.iana.org/time-zones`](https://www.iana.org/time-zones），每年更新几次。大部分更新处理夏令时。Java 使用 IANA 数据库。

每个时区都有一个 ID，例如`America/New_York`或`Europe/Berlin`。要查找所有可用时区，请调用`ZoneId.getAvailableIds`。

给定一个时区 ID，静态方法`ZoneId.of(id)`产生一个`ZoneId`对象。你可以使用该对象通过调用`local.atZone(zoneId)`将`LocalDateTime`对象转换为`ZonedDateTime`对象，或者通过调用静态方法`ZonedDateTime.of(year, month, day, hour, minute, second, nano, zoneId)`来构造`ZonedDateTime`。例如，

```
ZonedDateTime apollo11launch = ZonedDateTime.of(1969, 7, 16, 9, 32, 0, 0,
    ZoneId.of("America/New_York"));
// 1969-07-16T09:32-04:00[America/New_York]
```

这是一个特定的时间点。调用`apollo11launch.toInstant`获取`Instant`。

相反，如果你有一个时间点，调用`instant.atZone(ZoneId.of("UTC"))`获取格林维治皇家天文台`ZonedDateTime`，或者使用另一个`ZoneId`获取地球上其他地方的时间。

`ZonedDateTime`的许多方法与`LocalDateTime`的方法相同（参见表 12.5）。大多数方法都是直观的，但夏令时引入了一些复杂性。

当夏令时开始时，时钟会拨快小时。当你构造一个落在跳过的小时的时间时会发生什么？例如，2013 年，中欧在 3 月 31 日 2:00 切换到夏令时。如果你尝试构造不存在的时间 3 月 31 日 2:30，你实际上得到的是 3:30。

```
ZonedDateTime skipped = ZonedDateTime.of(
    LocalDate.of(2013, 3, 31),
    LocalTime.of(2, 30),
    ZoneId.of("Europe/Berlin"));
    // 构建了 3 月 31 日 3:30
```

相反，当夏令时结束时，时钟会拨回小时，因此会有两个具有相同的本地时间！当你在该区间内构造时间时，你会得到两者较早的一个。

```
ZonedDateTime ambiguous = ZonedDateTime.of(
    LocalDate.of(2013, 10, 27), // 夏令时结束
    LocalTime.of(2, 30),
    ZoneId.of("Europe/Berlin"));
    // 2013-10-27T02:30+02:00[Europe/Berlin]
ZonedDateTime anHourLater = ambiguous.plusHours(1);
    // 2013-10-27T02:30+01:00[Europe/Berlin]
```

一小时后，时间的小时分钟相同，但时区偏移量发生了变化。

在跨越夏令时边界调整日期时，你也需要注意。例如，如果你为下周安排了一个会议，不要添加持续 7 天的时长：

```
ZonedDateTime nextMeeting = meeting.plus(Duration.ofDays(7));
    // 注意！这在夏令时下无效
```

相反，请使用`Period`类。

```
ZonedDateTime nextMeeting = meeting.plus(Period.ofDays(7)); // OK
```

表 12.5：`ZonedDateTime` 方法

![Images](img/tab12-05.jpg)

### 注意

还有一个`OffsetDateTime`类，它表示与 UTC 有偏移量的时间，但没有时区规则。该类旨在用于专门要求缺少这些规则的特殊应用程序，例如某些网络协议。对于人类时间，请使用`ZonedDateTime`。

### 12.6. 格式化与解析

`DateTimeFormatter`类提供了三类型的格式化器来打印日期/时间值：

![images](img/sq.jpg) 预定义的标准格式器（参见表 12.6）

![images](img/sq.jpg) 区域特定的格式器

![images](img/sq.jpg) 带有自定义模式的格式器

要使用标准格式化器之一，只需调用其`format`方法即可：

```
String formatted = DateTimeFormatter.ISO_DATE_TIME.format(apollo11launch);
    // 1969-07-16T09:32:00-05:00[America/New_York]
```

表 12.6：预定义的格式化器

![Images](img/tab12-06.jpg)

标准格式化器主要用于机器读的时间戳。要向人类读者展示日期和时间，请使用区域特定的格式器。日期和时间都有四种样式：`SHORT`、`MEDIUM`、`LONG`和`FULL`——参见表 12.7。

静态方法`ofLocalizedDate`、`ofLocalizedTime`和`ofLocalizedDateTime`创建此类格式化器。例如：

```
DateTimeFormatter formatter = DateTimeFormatter.ofLocalizedDateTime(FormatStyle.LONG);
String formatted = formatter.format(apollo11launch);
    // July 16, 1969 9:32:00 AM EDT
```

这些方法使用默认区域。要更改到不同的区域，只需使用`withLocale`方法即可。

```
formatted = formatter.withLocale(Locale.FRENCH).format(apollo11launch);
    // 16 juillet 1969 09:32:00 EDT
```

`DayOfWeek`和`Month`枚举拥有方法`getDisplayName`，用于以不同的区域和格式提供星期和月份名称。

```
for (DayOfWeek w : DayOfWeek.values())
    System.out.print(w.getDisplayName(TextStyle.SHORT, Locale.ENGLISH) + " ");
    // 输出 Mon Tue Wed Thu Fri Sat Sun
```



关于区域的更多信息，请参见第 13 章。

表 12.7：日期和时间格式化样式

![Images](img/tab12-07.jpg)

#### Note

`java.time.format.DateTimeFormatter` 类旨在替换 `java.util.DateFormat`。如果你为了向后兼容需要后者的实例，请调用 `formatter.toFormat()`。

最后，你可以通过指定模式来自定义自己的日期格式。例如，

```
formatter = DateTimeFormatter.ofPattern("E yyyy-MM-dd HH:mm");
```

`E yyyy-MM-dd HH:mm` 格式化为 `Wed 2013-03-31 02:30`。模式中的 `E` 表示星期，`yyyy-MM-dd` 表示日期，`HH:mm` 表示时间。每个符号表示一个特定的字段。表 12.8 显示了最常用的符号。

表 12.8：常用的日期/时间符号

![Images](img/tab12-08.jpg)

从字符串解析日期/时间值，使用 `parse` 方法。例如，

```
LocalDate birthday = LocalDate.parse("2013-06-14");

ZonedDateTime apollo11launch = ZonedDateTime.parse("1969-07-16T09:32",
        DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm"));
```

第一次使用 `ISO_DATE_TIME`，第二次使用自定义格式器。

### 12.7. 与旧代码互操作

Java 日期时间 API 必须与现有类互操作，特别是 `java.util.Date`、`java.util.GregorianCalendar` 和 `java.sql.Timestamp`。`Instant` 类是 `java.util.Date` 的对应物。它有一个 `toInstant` 方法将 `Date` 转换为 `Instant`，以及静态 `from` 方法反之操作。同样，`ZonedDateTime` 是 `java.util.GregorianCalendar` 的对应物。`toZonedDateTime` 方法将 `GregorianCalendar` 转换为 `ZonedDateTime`，静态 `from` 方法反之操作。另一组转换适用于 `java.sql` 包。表 12.9 总结了这些转换。

表 12.9：`java.time` 与旧类之间的转换

![Images](img/tab12-09.jpg)

### 练习

1. 不使用 `plusDays` 计算日期。
2. 给 `LocalDate.of(2000, 2, 29)` 添加一年会发生什么？添加四年？添加四次？
3. 实现一个接受 `Predicate<LocalDate>` 并返回调整器的 `next` 方法。例如，

```
today.with(next(w -> w.getDayOfWeek().getValue() < 6))
```

计算下一个工作日。

4. 编写一个 Unix `cal` 的等效程序来显示月份日历。例如，`java Cal 3 2013` 应该显示

```
 1 2 3
      4 5 6 7 8 9 10
11 12 13 14 15 16 17
18 19 20 21 22 23 24
25 26 27 28 29 30 31
```

表明 3 月 1 日是星期五。（显示周末。）

5. 编写一个打印你活了多少天的程序。
6. 列出二十世纪所有的星期五。
7. 实现一个 `TimeInterval` 类来表示时间段，适用于日历事件（例如某天 10:00 到 11:00 的会议）。提供一个检查两个间隔是否重叠的方法。
8. 获取所有支持的时区的今天日期的偏移量，将 `ZoneId.getAvailableZoneIds` 转换为流并使用流操作。
9. 再次使用流操作找到所有偏移量不是整小时的时区。
10. 从洛杉矶飞往法兰克福的航班在当地时间下午 3:05 出发，飞行 10 小时 50 分。什么时候到达？编写一个可以处理此类计算的程序。
11. 你的回程航班从法兰克福 14:05 出发，在洛杉矶 16:40 到达。飞行时长多久？编写一个可以处理此类计算的程序。
12. 编写一个程序，解决第 12.5 节开头描述的问题：读取一组不同时区的预约信息，并提醒用户哪些预约在本地时间未来的一小时内需要执行。

# 13. 国际化

这个世界非常大，希望其中的许多居民都会对你的软件感兴趣。一些程序员认为，应用程序国际化唯一需要做的事情就是支持 Unicode 并翻译用户界面中的消息。然而，正如你将看到的，程序的国际化工作远不止于此。日期、时间、货币，甚至数字，在世界不同地区的格式也各不相同。在本章中，你将学习如何使用 Java 的国际化功能，使得你的程序无论用户在何处，都能以他们理解的方式展示和接受信息。

在本章结束时，你将看到关于用于存储用户偏好的 `Preferences` API 的简要概述。

本章的要点是：

1. 为国际用户翻译应用程序不仅仅是翻译消息。特别是数字和日期的格式化在世界范围内差异巨大。
2. `locale`（区域语言）描述了用户群的语言和格式偏好。
3. `NumberFormat` 和 `DateTimeFormat` 类处理数字、货币、日期和时间的区域感知性格式化。
4. `MessageFormat` 类可以格式化带有占位符的消息字符串，每个占位符都可以有自己的格式。
5. 使用 `Collator` 类进行依赖于区域的字符串排序。
6. `ResourceBundle` 类管理多个区域的本地化字符串和对象。
7. `Preferences` 类可用于以平台无关的方式存储用户偏好。

## 13.1. 区域语言 (Locales)

当你看到一个适配于国际市场的应用程序时，最明显的区别是语言。但还有许多细微的差异；例如，数字在英语和德语中的格式化完全不同。数字

```
123,456.78
```

对于德国用户，应该显示为

```
123.456,78
```

也就是说，小数点和小数逗号分隔符的作用反过来了。日期的显示上也有类似的差异。在美国，日期的显示格式为月/日/年；德国使用更符合逻辑的日/月/年，而在中国，使用习惯是年/月/日。因此，美国的日期

```
3/22/61
```

向德国用户展示时应该是

```
22.03.1961
```

如果月份名称完整写出来，那么语言上的差异变得更加明显。英语的

```
March 22, 1961
```

在德语中应该呈现为

```
22. März 1961
```

或者在中文中

```
1961 年 3 月 22 日
```

`locale` 指定了用户的语言和位置，这使得格式化器能够考虑用户的偏好。接下来的章节将为你展示如何指定 `locale` 以及如何控制 Java 程序的区域设置。

### 13.1.1. 指定区域语言

一个 `locale` 由多达五个组件组成：

1. 语言，由两个或三个小写字母指定，例如 `en`（英语）、`de`（德语）或 `zh`（中文）。表 13.1 显示了常用代码。
2. 可选的脚本，由首字母大写的四个字母指定，例如 `Latn`（拉丁）、`Cyrl`（西里尔字母）或 `Hant`（繁体中文）。这非常有用，因为某些语言（如塞尔维亚语）使用拉丁或西里尔字母书写，且某些中文读者倾向于繁体字而非简体字。
3. 可选的国家或地区，由两个大写字母或三个数字指定，例如 `US`（美国）或 `CH`（瑞士）。表 13.2 显示了常用代码。
4. 可选的 `variant`（变体）。
5. 可选的扩展（extension）。扩展描述了日历（如日本历）、数字（使用泰语数字而非阿拉伯数字）等的本地偏好。Unicode 标准规定了其中一些扩展。扩展以 `u-` 开头，后跟着两个字母的代码，指定该扩展处理日历（`ca`）、数字（`nu`）等。例如，扩展 `u-nu-thai` 表示使用泰国数字。其他扩展完全是任意，并以 `x-` 开头，例如 `x-java`。

注意：
变体现在很少被使用。曾经有一个挪威语的“尼诺尔什语”变体，但现在用不同的语言代码 `nn` 表示。以前用于日本皇历和泰国数字的变体现在以扩展的形式表示。

区域语言的规则制定于互联网工程任务组的“最佳当前实践”备忘录 BCP 47 中（[`tools.ietf.org/html/bcp47`](http://tools.ietf.org/html/bcp47)）。你可以在 [`www.w3.org/International/articles/language-tags`](http://www.w3.org/International/articles/language-tags) 找到一个更易读的摘要。

注意：
语言和国家的代码看起来有些随机，因为其中一些源自本地语言。德语在德语中是 Deutsch，中文在中文中是 Chinese。瑞士有四种官方语言（德语、法语、意大利语和罗曼什语）。瑞士的德语使用者会使用 `de-CH`。

为了测试，你可能想要切换程序的默认语言区域（locale）。在启动程序时，提供语言和区域属性。例如，在这里我们将默认区域设置为德国（瑞士）：

```
java -Duser.language=de -Duser.country=CH MainClass
```

你还可以更改脚本（script）和变体（variant），并且可以为显示语言区域和格式语言区域设置单独设置，例如 `-Duser.script.display=Hant`。

你可以通过调用以下方法之一来更改虚拟机的默认语言区域：

```java
Locale.setDefault(newLocale);
Locale.setDefault(category, newLocale);
```

第一个调用将更改所有类别的 `Locale.getDefault()` 和 `Locale.getDefault(category)` 返回的语言区域。

### 13.1.3 显示名称

假设你想允许用户在一组语言区域中进行选择。你不希望显示晦涩的标签字符串；`getDisplayName` 方法返回一个描述语言区域的字符串，其格式可以呈现给用户，例如：

```
German (Switzerland)
```

实际上，这里存在一个问题。显示名称是用默认语言区域签发的。这可能并不合适。如果你的用户已经选择了德语作为首选语言，你可能希望用德语呈现该字符串。你可以通过指定德语语言区域的参数来实现。代码如下：

```java
Locale loc = Locale.forLanguageTag("de-CH");
System.out.println(loc.getDisplayName(Locale.GERMAN));
```

打印结果为

```
Deutsch (Schweiz)
```

这个示例展示了为什么你需要 `Locale` 对象。你将它们传递给感知语言区域的方法，这些方法会产生呈现给不同位置用户的文本。你将在后续章节中看到许多示例。

### 注意

即使是像将字符串转换为小写或大写这样平凡的操作，也可能是特定语言区域的。例如，在土耳其语言区域中，字母 I 的小写是不带点的 `ı`。试图通过将其存储为小写来规范化字符串的程序对土耳其客户莫名地失败了。始终使用带有 `Locale` 参数的 `toUpperCase` 和 `toLowerCase` 变体是一个好主意。例如，尝试：

```java
String cmd = "QUIT".toLowerCase(Locale.forLanguageTag("tr"));
// 带有无点 ı 的 "quıt"
```

当然，在土耳其，`Locale.getDefault()` 返回的就是该语言区域，因此 `"QUIT".toLowerCase()` 的结果不等同于 `"quit"`。

如果你想将英语字符串规范化为小写，你应该将英语语言区域传递给 `toLowerCase` 方法。

#### 备注

你可以显式地设置输入和输出操作的语言区域。

![images](img/sq.jpg) 当从 `Scanner` 读取数字时，可以使用 `useLocale` 方法设置它的语言区域。

![images](img/sq.jpg) `String.format` 和 `PrintWriter.printf` 方法可选地接受一个 `Locale` 参数。

### 13.2 数字格式

`java.text` 包中的 `NumberFormat` 类为数字格式化器提供了三个工厂方法，用于可以格式化和解析数字：`getNumberInstance`、`getCurrencyInstance` 和 `getPercentInstance`。例如，这里是如何用德语格式化货币值的：

```java
Locale loc = Locale.GERMANY;
NumberFormat formatter = NumberFormat.getCurrencyInstance(loc);
double amt = 123456.78;
String result = formatter.format(amt);
```

结果是

```
123.456,78 €
```

注意货币符号是 €，并且它位于字符串的末尾。此外，注意小数点和小数逗号的反转。

相反，要读取按照特定语言区域惯例输入或存储的数字，请使用 `parse` 方法：

```java
String input = ...;
NumberFormat formatter = NumberFormat.getNumberInstance();
// 获取默认格式语言区域的数字格式化器
Number parsed = formatter.parse(input);
double x = parsed.doubleValue();
```

`parse` 的返回类型是抽象类型 `Number`。返回的对象是一个 `Double` 或 `Long` 包装对象，取决于输入的数字是否为浮点数。如果你不在乎这种区别，可以简单地使用 `Number` 类的 `doubleValue` 方法来获取包装的数字。

如果数字文本格式不正确，该方法将抛出 `ParseException`。例如，字符串中开头的空格是不允许的。（调用 `strip` 来移除它）。然而，字符串中数字后的任何字符都将被忽略，且不会抛出异常。

### 13.3 货币

要格式化货币值，你可以使用 `NumberFormat.getCurrencyInstance` 方法。然而，该方法并不灵活——它返回一个单一货币的格式化器。假设你为一位美国客户准备一份发单，其中某些金额是美元，另一些是欧元。你不能仅仅使用两个格式化器

```java
NumberFormat dollarFormatter = NumberFormat.getCurrencyInstance(Locale.US);
NumberFormat euroFormatter = NumberFormat.getCurrencyInstance(Locale.GERMANY);
```

你的发单看起来会非常奇怪，某些值格式化为 `$100,000`，另一些格式化为 `100.000`€。（注意欧元值使用的是小数点而不是逗号。）

相反，使用 `Currency` 类来控制格式化器使用的货币。你可以通过将货币标识符传递给静态方法 `Currency.getInstance` 来获取 `Currency` 对象。表 1 列出了常见的标识符。静态 `Currency.getAvailableCurrencies` 是虚拟机知的。一旦你有了 `Currency` 对象，调用 `setCurrency` 方法。这里是如何为你的美国客户格式化金额：

```java
NumberFormat formatter = NumberFormat.getCurrencyInstance(Locale.US);
System.out.println(formatter.format(Currency.getInstance("EUR")));
```

如果你需要显示货币的本地名称或符号，调用

```java
getDisplayName()
getSymbol()
```

这些方法返回默认语言区域的字符串。你也可以提供显式的语言区域。

表 13.3 常见货币标识符 (Images/133)

### 13.4 日期和时间格式化

格式化日期和时间会有四个语言区域的问题：

1. 月份和星期的名字应该以本地语言呈现。
2. 年、月、日的顺序会有本地差异。
3. 公历可能不是本地偏好。
4. 必须考虑位置的时区。

使用 `java.time.format` 包中的 `DateTimeFormatter`，而不是旧的 `java.util.DateFormat`。决定你需要日期、时间还是两者。选择四种格式之一——表 13.4。如果你格式化日期和时间，可以分别选择它们。

然后获取格式化器：

```java
FormatStyle style = ...; // 之一 FormatStyle.SHORT, FormatStyle.MEDIUM,...
DateTimeFormatter dateFormatter = DateTimeFormatter.ofLocalizedDate(style);
DateTimeFormatter timeFormatter = DateTimeFormatter.ofLocalizedTime(style);
DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofLocalizedDateTime(style);
// 或 DateTimeFormatter.ofLocalizedDateTime(style1, style2)
```

这些格式化器使用当前的格式语言区域。要使用不同的语言区域，使用 `withLocale` 方法：

```java



```java
DateTimeFormatter dateFormatter = DateTimeFormatter.ofLocalizedDate(style).withLocale(locale);
```

现在你可以格式化 `LocalDate`、`LocalDateTime`、`LocalTime` 或 `ZonedDateTime`：

```java
ZonedDateTime appointment = ...;

String formatted = formatter.format(appointment);
```

要解析字符串，使用 `LocalDate`、`LocalDateTime`、`LocalTime` 或 `ZonedDateTime` 的静态 `parse` 方法。

```java
LocalTime time = LocalTime.parse("9:32 AM", formatter);
```

如果字符串无法成功解析，将抛出 `DateTimeParseException`。

表 13.4 特定语言区域的格式样式（Images/134）

这些方法不适用于解析人类输入，至少在没有预处理的情况下不是。例如，美国的短时间格式器可以解析 `"9:32 AM"`，但无法解析 `"9:32AM"` 或 `"9:32 am"`。

> **注意**
>
> 日期格式化器会解析不存在的日期（例如 11 月 31 日），将其调整为该月的最后一天。

有时，你只需要显示星期和月份名称，例如在日历应用中。调用 `DayOfWeek` 和 `Month` 枚举的 `getDisplayName` 方法。

```java
for (Month m : Month.values()) {
    System.out.println(m.getDisplayName(textStyle, locale) + " ");
}
```

表 13.5 显示了文本样式。`STANDALONE` 版本用于格式化日期之外的显示。例如在芬兰语中，一月在日期内部是“tammikuuta”，但单独显示时是“tammikuu”。

> **注**
>
> 每周的第一天可以是周六、周日或周一，取决于区域设置。你可以这样获取它：

```java
DayOfWeek first = WeekFields.of(locale).getFirstDayOfWeek();
```

表 13.5：`java.time.format.TextStyle` 枚举的值

![Images](img/tab13-05.jpg)

### 13.5. 排序与归一化

大多数程序员都知道如何使用 `String` 类的 `compareTo` 方法比较字符串。遗憾的是，在与人类用户交互时，这个方法并不十分有用。`compareTo` 方法使用字符串的 UTF-16 编码值，这即使在英语中会导致荒谬的结果。例如，以下五个字符串根据 `compareTo` 方法排序如下：

```text
Athens
Zulu
able
zebra
Ångström
```

对于字典排序，你可能希望考虑大小写的等效性，且重音不应该是重要的。对于英语母者来说，示例单词列表应该排序为：

```text
able
Ångström
Athens
zebra
Zulu
```

然而，这种顺序对瑞典用户来说是不可的。在瑞典语中，字母 `Å` 与字母 `A` 不同，并且它排在字母 `Z` 之后！这意味着，瑞典用户希望单词排序为：

```text
able
Athens
zebra
Zulu
Ångström
```

要获取与区域敏感的比较器，请调用静态方法 `Collator.getInstance`：

```java
Collator coll = Collator.getInstance(locale);

words.sort(coll);

// Collator implements Comparator<Object>
```

排序器有几个高级设置。你可以设置排序器的 `strength` 来调整其选择性。字符差异被分类为一级、二级或三级。例如，在英语中，`e` 和 `f` 之间的差异被视为一级，`e` 和 `é` 之间的差异是二级，而 `e` 和 `E` 之间的差异是三级。

例如，处理城市名称时，你可能不在乎以下这些差异：

```text
San José
San Jose
SAN JOSE
```

在这种情况下，通过调用以下代码配置排序器：

```java
coll.setStrength(Collator.PRIMARY);
```

一个更具技术性的设置是“分解模式”（decomposition mode），它处理的是一个字符或字符序列有时在 Unicode 中可以用不止一种方式描述的事。例如，`é`（U+00E9）也可以表示为普通的 `e`（U+0065）后面跟一个 ` ́`（组合重音符号 U+0301）。你可能不在乎这种差异，且默认情况下它是不重要的。如果你在乎，则需要如下配置排序器：

```java
coll.setStrength(Collator.IDENTICAL);

coll.setDecomposition(Collator.NO_DECOMPOSITION);
```

相反，如果你想非常宽容，并将商标符号 `™`（U+2122）视为与字符组合 TM 相同，则将分解模式设置为 `Collator.FULL_DECOMPOSITION`。

即使你不进行排序，可能也想将字符串转换为归一化形式——例如为了持久化存储或与另一个程序通信。Unicode 标准定义了四种归一化形式（C、D、KC 和 KD），参见 [`www.unicode.org/unicode/reports/tr15/tr15-23.html`](http://www.unicode.org/unicode/reports/tr15/tr15-23.html)。

在归一化形式 C 中，带重音的字符总是组合的。例如，`e` 和组合重音符号 ` ́` 的序列组合成单个字符 `é`。在形式 D 中，带重音的字符总是分解为基础字母和组合重音：`é` 转换为 `e` 后跟 ` ́`。形式 KC 和 KD 也会分解如商标符号 `™` 等字符。W3C 建议你在通过互联网传输数据时使用归一化形式 C。

`java.text.Normalizer` 类的静态方法 `normalize` 执行归一化过程。例如：

```java
String city = "San Jose\u0301";

String normalized = Normalizer.normalize(city, Normalizer.Form.NFC);
```

### 13.6. 消息格式化

当程序进行国际化时，通常会有带有变量部分的消息。`MessageFormat` 类的静态方法 `format` 一个带有占位符的模板字符串，随后是占位符的值，如下：

```java
String template = "{0} has {1} messages";
```

单引号 `’...’` 中的任何文本都将字面包含。例如，`’{0}’` 不是占位符，而是字面字符串 `{0}`。如果模板中包含单引号，你必须将其双倍化。

```java
String template = "<a href=’’{0}’’>{1}</a>";
```

静态方法 `MessageFormat.format` 使用当前的格式化区域（locale）来格式化值。要使用任意区域进行格式化，你需要付出更多努力，因为没有可以直接使用的“变长”（varargs）方法。你需要将需要格式化的值放入 `Object[]` 数组中，如下：

```java
var mf = new MessageFormat(template, locale);

String message = mf.format(new Object[] { arg1, arg2, ... });
```

## 13.7. 资源包（Resource Bundles）

在对应用程序本地化时，最好是将程序与消息字符串、按钮标签和其他需要翻译的文本分开。在 Java 中，你可以将它们放入资源包中。然后，你可以将这些资源包交给翻译人员，他们可以编辑它们，而无需触碰程序的源代码。

> **Note**
>
> 第 4 章描述了 JAR 文件资源的概念，数据文件、声音和图像可以放在 JAR 文件中。`Class` 类的 `getResource` 方法可以找到文件、打开它并返回资源的 URL。这是一种对于将文件与程序打包在一起非常有用的机制，但它没有区域化支持。

### 13.7.1. 组织资源包

在对应用程序本地化时，你会产生一组资源包。每个资源包要么是一个属性文件，要么是一个特殊类，包含针对特定区域或一组匹配区域的条目。

在本节中，我只讨论属性文件，因为它们比资源类常见得多。属性文件是一个扩展名为 `.properties` 的文本文件，其中包含键/值对。例如，文件 `messages_de_DE.properties` 可能包含：

```properties
computeButton=Rechnen
cancelButton=Abbrechen
defaultPaperSize=A4
```

你必须为构成这些资源包的文件使用特定的命名约定。例如，特定德国的资源进入文件 `bundleName_de_DE`，而所有德语国家共享的资源则进入 `bundleName_de`。对于给定的语言、脚本和国家组合，会考虑以下候选方案：

```text
bundleName_language_script_country
bundleName_language_script
bundleName_language_country
bundleName_language
```

如果 `bundleName` 包含点，则该文件必须放在匹配的子目录下。例如，资源包 `com.mycompany.messages` 的文件是 `com/mycompany/messages_de_DE.properties` 等。

要加载资源包，调用：

```java
ResourceBundle res = ResourceBundle.getBundle(bundleName);
```

用于默认区域，或者调用：

```java
ResourceBundle bundle = ResourceBundle.getBundle(bundleName, locale);
```

用于指定的区域。

> **Caution**
>
> 第一个 `getBundle` 方法使用的不是默认显示区域，而是整体的默认区域。如果你为用户界面查找资源，请确保将 `Locale.getDefault(Locale.Category.DISPLAY)` 作为区域传递。

要查找字符串，使用键调用 `getString` 方法。

```java
String computeButtonLabel = bundle.getString("computeButton");
```

加载包文件的规则有点复杂，涉及两个阶段。在第一阶段，定位匹配的资源包。这涉及最多三个步骤。

1. 首先，按照上述顺序尝试包名、语言、脚本、国家和变体的所有候选组合，直到找到匹配项为止。例如，如果目标区域是 `de-DE` 且没有 `messages_de_DE.properties` 但存在 `messages_de.properties`，则后者将成为匹配的资源包。
2. 如果没有匹配，则用默认区域重复此过程。例如，如果请求德国资源包但不存在，且默认区域是 `en-US`，则 `messages_en_US.properties` 被接受为匹配项。
3. 如果默认区域也没有匹配，则没有后缀的资源包（例如 `messages.properties`）为匹配项。如果该也不存在，则搜索失败。

> **Note**
>
> 对于变体、简体和繁体中文以及挪威语，有特殊规则。详情请参见 `ResourceBundle.Control` 的 Javadoc。

在第二阶段，定位匹配资源包的父包。父包是候选列表中位于匹配资源包下方的包，以及没有后缀的资源包。例如，`messages_de_DE.properties` 的父包是 `messages_de.properties` 和 `messages.properties`。

`getString` 方法在匹配的资源包及其父包中查找键。

> **Note**
>
> 如果在第一阶段找到了匹配的资源包，则其父包永远不会来自默认区域。

> **Note**
>
> 在过去，属性文件受限于使用 ASCII 字符集。所有非 ASCII 字符都必须使用 `\uxxxx` 编码进行编码，如下：

```properties
prefs=Pr\u00E9fer\u00E9nces
```

现在，属性文件被假设为 UTF-8，你可以直接在文件中编写本地化字符串：

```properties
prefs=Préférences
```

### 13.7.2. 包类

为了提供不是字符串的资源，定义扩展 `ResourceBundle` 的类。使用与属性文件类似的命名约定，例如 `com.mycompany.MyAppResources`。

要实现资源包，可以扩展 `ListResourceBundle`。将所有资源放入键/值对数组并在 `getContents` 方法中返回它。例如：

```java
package com.mycompany;

public class MyAppResources extends ListResourceBundle {
    public Object[][] getContents() {
        return new Object[][] {
            { "backgroundColor", Color.BLACK },
            { "defaultPaperSize", new double[] { 210, 297 } }
        };
    }
}
```

从此类资源包中获取对象，调用 `getObject` 方法：

```java
ResourceBundle bundle = ResourceBundle.getBundle("com.mycompany.MyAppResources", locale);

var backgroundColor = (Color) bundle.getObject("backgroundColor");

double[] paperSize = (double[]) bundle.getObject("defaultPaperSize");
```

> **Caution**
>
> 当发现类和属性文件同时存在时，`ResourceBundle.getBundle` 方法优先类。

## 13.8. 字符编码

Java 使用 Unicode 并不意味着所有的编码问题都消失了。幸运的是，你不需要担心 `String` 对象的编码。你收到的任何字符串（无论是命令行参数、控制台输入还是 GUI 文本框输入）都是 UTF-16 编码字符串，包含了用户提供的文本。

当你显示字符串时，虚拟机将其编码为本地平台。有两个潜在问题。显示字体可能没有某个 Unicode 字符的字形。在 Java GUI 中，此类字符将显示为空心框。对于控制台输出，如果控制台使用的编码无法表示所有输出字符，缺失的字符将显示为 `?`。用户可以通过安装字体或将控制台切换到 UTF-8 来解决这些问题。

当你的程序读取用户产生的文本文件时，情况变得更加复杂。简单的文本编辑器通常以本地平台编码生成文件。可以通过调用 `Charset platformEncoding = Charset.defaultCharset();` 获取该编码。

这是对用户喜欢的字符编码的合理猜测，但你应该允许用户覆盖它。

如果你想提供字符编码的选择，可以获取本地化的名称，如下：

```java
String displayName = encoding.displayName(locale);

// 产生如 UTF-8、ISO-8859-6 或 GB18030 等名称
```

遗憾的是，这些名称对于想要在 Unicode、阿拉伯语、简体中文等之间选择的终端用户来说并不合适。

> **提示**
>
> Java 源文件也是文本文件。为了方便与其他程序员共享，源文件不应使用平台默认编码。你可以使用 `\uxxxx` 转义字符在代码或注释中表示任何非 ASCII 字符，但这非常繁琐。相反，请将你的文本编辑器设置为使用 UTF-8。你可以将控制台偏好设置为 UTF-8，或者使用以下命令编译：

```bash
javac -encoding UTF-8 *.java
```

### 13.9. 首好（Preferences）

我用一个与国际化有关系的 API 结束——用户偏好的存储（可能包括首选的语言区域）。

当然，你可以将偏好存储在属性文件中，并在程序启动时加载它。然而，对于配置文件的命名和存放并没有标准的约定，这增加了用户在安装多个 Java 应用程序时发生冲突的可能性。

某些操作系统拥有用于存储信息的中央存储库。最广为人知的例子是 Microsoft Windows 中的注册表。`Preferences` 类是 Java 中存储用户偏好的标准机制，它在 Windows 上使用注册表。在 Linux 上，信息存储在本地文件系统中。对于使用 `Preferences` 类的程序员来说，具体的存储库实现是透明的。

`Preferences` 存储库包含一个节点树。存储库中的每个节点都有一个键/值对表。值可以是数字、`boolean` 值、字符串或字节数组。

> **注意**
>
> 此处未提供存储任意对象的规定。当然，如果你不担心使用序列化进行长期存储，你可以自由地将序列化后的对象作为字节数组存储。

节点的路径看起来像 `/com/mycompany/myapp`。与包名一样，你可以通过以反向域名开头路径来避免命名冲突。

有两棵并行的树。每个程序用户拥有一棵树。还有一个名为“系统树”的额外树，用于所有用户通用的设置。`Preferences` 类使用操作系统的“当前用户”概念来访问相应的用户树。要访问树中的节点，从用户根或系统根开始：

```java
Preferences root = Preferences.userRoot();
```

或者：

```java
Preferences root = Preferences.systemRoot();
```



然后通过路径名称访问节点：

```
Preferences node = root.node("/com/mycompany/myapp");
```

或者，提供一个`Class`对象给静态方法`userNodeForPackage`或`systemNodeForPackage`，节点路径将根据该类的包名推导出。

```
Preferences node = Preferences.userNodeForPackage(obj.getClass());
```

一旦你获得了一个节点，就可以访问键/值表。使用以下方法获取字符串：

```
String preferredLocale = node.get("locale", "");
```

对于其他类型，使用以下方法之一：

```
String get(String key, String defval)
int getInt(String key, int defval)
long getLong(String key, long defval)
float getFloat(String key, float defval)
double getDouble(String key, double defval)
boolean getBoolean(String key, boolean defval)
byte[] getByteArray(String key, byte[] defval)
```

在读取信息时，必须指定默认值，以防存储库数据不可用。

相反，你可以使用`put`方法将数据写入存储库，例如：

```
void put(String key, String value)
void putInt(String key, int value)
```

以此类推。

要从节点删除条目，调用：

```
void remove(String key)
```

调用`node.removeNode()`可以删除整个节点及其子节点。

你可以使用以下方法列出节点中存储的所有键以及节点的所有子路径：

```
String[] keys()
String[] childrenNames()
```

**注意**

没有方法可以找到特定键值的类型。

你可以通过在子树的根节点上调用方法：

```
void exportSubtree(OutputStream out)
```

来导出子树的偏好。

数据以 XML 格式保存。你可以通过调用以下代码将其导入另一个存储库：

```
InputStream in = Files.newInputStream(path);
Preferences.importPreferences(in);
```

### 练习

1. 编写一个程序，演示法国、中国和泰国的日期时间格式样式（带有泰国数字）。
2. 你的 JVM 中哪些语言区域不使用西数字来格式化数字？
3. 你的 JVM 中哪些语言区域与美国使用相同的日期约定（月/日/年）？
4. 编写一个程序，用所有可用语言打印你 JVM 中所有语言区域的名称。对它们进行排序并忽略重复。
5. 重复前面的练习以处理货币名称。
6. 编写一个程序，列出在至少两个语言区域中具有不同符号的所有货币。
7. 编写一个程序，在所有显示不同的语言区域中列出显示月份和独立月份名称，但独立名称由数字组成的情况除外。
8. 编写一个程序，列出所有在 KC 或 KD 标准化形式下扩展为两个或多个 ASCII 字符的 Unicode 字符。
9. 取你的其中一个程序并对所有消息进行国际化，使用至少两种语言的资源包（resource bundles）。
10. 提供一种机制显示带有可读描述的可用字符编码，就像在网络浏览器中那样。语言名称应该是本地化的。（使用 locale 语言的翻译。）
11. 提供一个用于依赖语言区域的纸张尺寸显示的类，使用首选尺寸单位和默认纸张尺寸。（除美国和加拿大外，全世界都使用 ISO 216 纸张尺寸。）

## 编译与脚本

在本章中将学习如何使用 API 在程序内部编译代码。你还将学习使用脚本 API 运行其他语言编写的程序。这对于你想让用户通过脚本增强程序特别有用。

本章的要点是：

1. 通过编译器 API，你可以在程序中访问 Java 编译器。
2. 你可以通过读取内存并写入内存来生成 Java 代码。
3. 脚本 API 让 Java 与多种脚本语言交互。
4. 在你的 Java 代码中，你可以访问由脚本读取和写入变量。
5. 通过某些脚本引擎，你可以从 Java 调用脚本函数。

### 14.1. 编译器 API

有很多工具需要编译 Java。显然，开发环境和教授 Java 编程的程序也是，还有测试和构建自动化工具。另一个例子是 JavaServer Pages——嵌入 Java 语句的网页。

#### 14.1.1 调用编译器

调用编译器非常简单。这是一个示例调用：

```
JavaCompiler compiler = ToolProvider.getSystemJavaCompiler();
OutputStream outStream = ...;
OutputStream errStream = ...;
int result = compiler.run(null, outStream, errStream,
    "-sourcepath", "src", "Test.java");
```

结果值为`0`表示编译成功。

编译器将输出和错误消息发送到提供的流中。你可以将这些参数设置为`null`，此时将使用`System.out`和`System.err`。`run`方法的第一个参数是一个输入流。由于编译器不需要控制台输入，你始终可以将其留为`null`。（`run`方法继承自通用的`Tool`接口，允许允许读取输入的工具使用。）

`run`方法的剩余参数是你在命令行调用`javac`时传递给它的字符串。这些参数可以是选项，也可以是文件名。

### 14.1.2. 启动编译任务

你可以通过`CompilationTask`对象对编译过程进行更细致的控制。如果你想从字符串提供源码、在内存中捕类文件或处理错误和警告信息，这将非常有用。

要获取`CompilationTask`，请像前一节一样从`compiler`对象开始。然后调用：

```
JavaCompiler.CompilationTask task = compiler.getTask(
    errorWriter, // 如果为 null 使用 System.err
    fileManager, // 如果为 null 使用标准文件管理器
    diagnostics, // 如果为 null 使用 System.err
    options, // 如果没有选项则为 null
    classes, // 用于注解处理；如果没有则为 null
    sources);
```

最后三个参数是`Iterable`实例。例如，可以指定选项序列：

```
Iterable<String> options = List.of("-d", "bin");
```

`sources`参数是`JavaFileObject`实例的`Iterable`。如果你想编译磁盘文件，请获取一个`StandardJavaFileManager`并调用其`getJavaFileObjects`方法：

```
StandardJavaFileManager fileManager
    = compiler.getStandardFileManager(null, null, null);
Iterable<JavaFileObject> sources
    = fileManager.getJavaFileObjectsFromStrings(List.of("File1.java", "File2.java"));
JavaCompiler.CompilationTask task
    = compiler.getTask(null, null, null, options, null, sources);
```

注意

`classes`参数仅用于注解处理。在这种情况下，你还需要带上`Processor`对象的列表来调用`task.processors(annotationProcessors)`。注解处理的示例请参阅第 11 章。

`getTask`方法返回任务对象，但尚未启动编译过程。`CompilationTask`类实现了`Callable<Boolean>`。你可以将其传递给`ExecutorService`以进行并发执行，你也可以直接进行同步调用：

```
Boolean success = task.call();
```

### 14.1.3. 捕获诊断信息

要监听错误消息，请安装一个`DiagnosticListener`。每当编译器报告警告或错误消息时，监听器就会接收到一个`Diagnostic`对象。`DiagnosticCollector`类实现了此接口。它收集所有的诊断信息，以便你在编译完成后对其进行遍历。

```
var collector = new DiagnosticCollector<JavaFileObject>();
compiler.getTask(null, fileManager, collector, null, null, sources).call();
for (Diagnostic<? extends JavaFileObject> d : collector.getDiagnostics()) {
    System.out.println(d);
}
```

`Diagnostic`对象包含有关问题位置（包括文件名、行号和列号）的信息以及人类可读的描述。

你也可以为标准文件管理器安装`DiagnosticListener`，以防你需要捕获关于缺失文件的消息：

```
StandardJavaFileManager fileManager
    = compiler.getStandardFileManager(diagnostics, null, null);
```

### 14.1.4. 从内存读取源文件

如果你动态生成源码，可以从内存中进行编译，而无需将文件保存到磁盘。使用此类来持有代码：

```java
public class StringSource extends SimpleJavaFileObject {
    private String code;

    StringSource(String name, String code) {
        super(URI.create("string:///" + name.replace(’.’,’/’) + ".java"), Kind.SOURCE);
        this.code = code;
    }

    public CharSequence getCharContent(boolean ignoreEncodingErrors) {
        return code;
    }
}
```

然后为你的类生成代码，并给编译器提供一个`StringSource`对象列表：

```
String pointCode = ...;
String rectangleCode = ...;
List<StringSource> sources = List.of(
    new StringSource("Point", pointCode),
    new StringSource("Rectangle", rectangleCode));
task = compiler.getTask(null, null, null, null, null, sources);
```

### 14.1.5. 将字节码写入内存

如果你动态地编译类，则无需将类文件保存到磁盘。你可以将它们保存到内存并立即加载。

首先，这是一个用于持有字节的类：

```java
public class ByteArrayClass extends SimpleJavaFileObject {
    private ByteArrayOutputStream out;

    ByteArrayClass(String name) {
        super(URI.create("bytes:///" + name.replace(’.’,’/’) + ".class"), Kind.CLASS);
    }

    public byte[] getCode() {
        return out.toByteArray();
    }

    public OutputStream openOutputStream() throws IOException {
        out = new ByteArrayOutputStream();
        return out;
    }
}
```

接下来，你需要配置文件管理器以使用这些类作为输出：

```
var classes = new ArrayList<ByteArrayClass>();
StandardJavaFileManager stdFileManager
    = compiler.getStandardFileManager(null, null, null);
JavaFileManager fileManager
    = new ForwardingJavaFileManager<JavaFileManager>(stdFileManager) {
        public JavaFileObject getJavaFileForOutput(Location location,
            String className, Kind kind, FileObject sibling)
                throws IOException {
            if (kind == Kind.CLASS) {
                var outfile = new ByteArrayClass(className);
                classes.add(outfile);
                return outfile;
            } else
                return super.getJavaFileForOutput(
                    location, className, kind, sibling);
            }
        };
```

要加载这些类，你需要一个类加载器（参见第 4 章）：

```java
public class ByteArrayClassLoader extends ClassLoader {
    private Iterable<ByteArrayClass> classes;

    public ByteArrayClassLoader(Iterable<ByteArrayClass> classes) {
        this.classes = classes;
    }

    @Override public Class<?> findClass(String name) throws ClassNotFoundException {
        for (ByteArrayClass cl : classes) {
            if (cl.getName().equals("/" + name.replace(’.’,’/’) + ".class")) {
                byte[] bytes = cl.getCode();
                return defineClass(name, bytes, 0, bytes.length);
            }
        }
        throw new ClassNotFoundException(name);
    }
}
```

编译完成后，使用该类加载器调用`Class.forName`方法：

```
var loader = new ByteArrayClassLoader(classes);
Class<?> cl = Class.forName("Rectangle", true, loader);
```

### 14.2. 脚本 API

脚本语言通过在运行时解释程序文本，避免了传统的编辑/编译/链接/运行循环。这鼓励了实验。此外，脚本语言通常较简单，因此非常适合作为程序的扩展语言。

脚本 API 允许你结合脚本语言和传统语言的优点。它使你在 Java 程序中能够调用 JavaScript、Groovy、Ruby 甚至是 Scheme 和 Haskell 等脚本。在接下来的章节中，你将看到如何为特定语言选择引擎、如何执行脚本以及利用某些脚本引擎提供的高级功能。

#### 14.2.1. 获取脚本引擎

脚本引擎是可以执行特定语言脚本的库。当虚拟机启动时，它会发现可用的脚本引擎。要列出这些引擎，请构造`ScriptEngineManager`并调用`getEngineFactories`方法。

通常你知道所需的引擎，可以通过名称请求它：

```
var manager = new ScriptEngineManager();
ScriptEngine engine = manager.getEngineByName("javascript");
```



你需要在类路径上提供实现脚本引擎的 JAR 文件。（Oracle JDK 曾包含 JavaScript 引擎，但该引擎在 Java 15 中已被移除。）本章中的示例使用了 Rhino JavaScript 引擎，该引擎可以在 [`github.com/mozilla/rhino`](https://github.com/mozilla/rhino) 获取。

> **提示**
>
> 存在 COBOL、PHP、R、Ruby、Scheme 等其他语言的脚本引擎。要查找特定语言的脚本引擎，请寻找对“JSR 223”的支持。

### 14.2.2. 评估脚本

一旦你拥有了引擎，就可以通过调用以下方法来执行脚本：

```java
Object result = engine.eval(scriptString);
```

你也可以从一个`Reader`读取脚本：

```java
Object result = engine.eval(Files.newBufferedReader(path, charset));
```

你可以在同一个引擎上调用多个脚本。如果一个脚本定义了变量、函数或类，大多数脚本引擎会保留这些定义以备后用。例如：

```java
engine.eval("n = 1728");

Object result = engine.eval("n + 1");
```

将返回`1729`。

> **注意**
>
> 要确定是否在多个线程中并发执行脚本是安全的，请调用`engine.getFactory().getParameter("THREADING")`。返回值是以下之一：
>
> - `null`：并发执行是不安全的。
> - `"MULTITHREADED"`：并发执行是安全的。一个线程的影响可能对另一个线程可见。
> - `"THREAD-ISOLATED"`：此外，为每个线程维护了不同的变量绑定。
> - `"STATELESS"`：此外，脚本不会改变变量绑定。

### 14.2.3. 绑定

一个*绑定*（binding）由一个名称和一个关联的 Java 对象组成。例如，考虑以下语句：

```java
engine.put("k", 1728);

Object result = engine.eval("k + 1");
```

相反，你可以检索由脚本语句绑定的变量：

```java
engine.eval("n = 1728");

Object result = engine.get("n");
```

这些绑定存在于*引擎作用域*（engine scope）中。此外，还有一个全局作用域。任何添加到`ScriptEngineManager`的绑定对所有引擎都可见。

与其将绑定添加到引擎或全局作用域，不如将它们收集在一个`Bindings`类型的对象中，并传递给`eval`方法：

```java
Bindings scope = engine.createBindings();

scope.put("k", 1728);

Object result = engine.eval("k + 1", scope);
```

如果一组绑定不应该在未来的`eval`方法调用中持续存在，这种方法非常有用。

### 14.2.4. 重定向输入和输出

你可以通过调用脚本上下文的`setReader`和`setWriter`方法来重定向脚本的标准输入和输出。例如：

```java
var writer = new StringWriter();

engine.getContext().setWriter(writer);

engine.eval("print(’Hello’)");

String result = writer.toString();
```

任何使用 JavaScript`print`函数写入的输出都会发送到`writer`。

`setReader`和`setWriter`方法仅影响脚本引擎的标准输入和输出源。例如，如果你执行以下 JavaScript 代码：

```javascript
print(’Hello’);

java.lang.System.out.println(’World’);
```

只有第一个输出被重定向了。

> **注意**
>
> Rhino 引擎没有标准输入源的概念。调用`setReader`无效果。

> **注意**
>
> 在 JavaScript 中，行尾的分号是可选的。许多 JavaScript 程序员仍然会写上分号，但在本章中，我省略了它们，以便你更轻松地区分 Java 和 JavaScript 代码段。
>
> 出于相同的原因，在可能的情况下，我对 JavaScript 字符串使用`’...’`而不是`"..."`。

### 14.2.5. 调用脚本函数和方法

在某些脚本引擎中，你可以调用脚本语言中的函数，而无需将该调用的代码本身作为脚本进行评估。如果你允许用户使用他们选择的脚本语言来实现服务，以便你能够从 Java 中调用它，这就会非常有用。

提供此功能的脚本引擎（包括 Rhino）实现了`Invocable`接口。要调用函数，请调用`invokeFunction`方法并传入函数名以及后续参数：

```java
// 在 JavaScript 中定义 greet 函数

engine.eval("function greet(how, whom) { return how + ,’ ’ + whom + ’!’ }");

// 使用参数 "Hello", "World" 调用函数

result = ((Invocable) engine).invokeFunction(
    "greet", "Hello", "World");
```

如果脚本语言是面向对象的语言，调用`invokeMethod`：

```java
// 在 JavaScript 中定义 Greeter 类

engine.eval("function Greeter(how) { this.how = how }");

engine.eval("Greeter.prototype.welcome = "
    + " function(whom) { return this.how + ’, ’ + whom + ’!’ }");

// 构造实例

Object yo = engine.eval("new Greeter(’Yo’)");

// 在实例上调用 welcome 方法

result = ((Invocable) engine).invokeMethod(yo, "welcome", "World");
```

> **注意**
>
> 欲更多信息，请参阅 Douglas Crockford (2008) 的*JavaScript—The Good Parts*。

> **注意**
>
> 如果脚本引擎没有实现`Invocable`，你仍然可以使用`eval`。

### 14.2.6. 编译脚本

某些脚本引擎可以将脚本代码编译为中间形式以便高效执行。这些引擎实现了`Compilable`接口。以下示例展示了如何编译并评估包含在脚本中的代码：

```java
if (engine implements Compilable) {
    Reader reader = Files.newBufferedReader(path, charset);
    CompiledScript script = ((Compilable) engine).compile(reader);
    script.eval();
}
```

当然，如果脚本工作很大或者你需要频繁执行它，编译脚本才有意义。

### 练习

1. 在 JavaServer Pages (JSP) 技术中，网页是 HTML 和 Java 的混合体，例如：

    ```jsp
    <ul>
    <% for (int i = 10; i >= 0; i--) { %>
        <li><%= i %></li>
    <% } %>
    <p>起飞!</p>
    ```

    `<%...%>`和`<%=...%>`之外的内容会被打印。内部的代码会被评估。如果起始分隔符是`<%=`，则结果会被添加到输出中。

    实现一个程序，读取此类页面，将其转换为 Java 方法，执行它并产生结果页面。

2. 在 Swing 或 JavaFX 教程中，查找如何将按钮放入窗口并添加一个在按钮被点击时调用的处理程序。允许用户在包含 Java 代码的文本文件中指定按钮动作。然后将这些动作编译成按钮处理器。

3. 重复之前的练习，但允许用户在 JavaScript 中指定按钮动作。在点击按钮时调用这些脚本。

4. 从 Java 程序调用 JavaScript 的`JSON.parse`方法将`JSON`格式的字符串转换为 JavaScript 对象，然后将其转换回字符串。通过以下方式此操作：(a) 使用`eval`，(b) 使用`invokeMethod`，(c) 通过接口进行 Java 方法调用。

    ```java
    public interface JSON {
        Object parse(String str);

        String stringify(Object obj);
    }
    ```

5. 在 Rhino 中，你可以使用完全限定名访问 Java 类，例如`java.lang.System`。你可以在 JavaScript 中创建实例并调用方法。编写一个 Rhino 程序，读取文件（如`/usr/share/dict/words`）并打印所有长度至少为 20 的字符串。

6. 在 Rhino 中，你可以使用“属性”表示法调用 Java 的 getter 和 setter。例如，`button.text = 'Click me'`会调用`button`对象上的`setText`方法。利用这种表示法将一个简单的 Swing 程序翻译为 Rhino。

7. 使用 Rhino 进行编译值得吗？编写一个 JavaScript 程序，用最笨的方法对数组进行排序，尝试所有排列直到其有序。比较编译版本和解释版本的运行时间。这里有一个用于计算下一个排列的 JavaScript 函数：

    ```javascript
    function nextPermutation(a) {
        // 找到从 a[i] 开始的最大非递减后缀
        var i = a.length - 1;
        while (i > 0 && a[i - 1] >= a[i]) i--;

        if (i > 0) {
            // 交换 a[i - 1] 与右侧大于 a[i - 1] 的 a[k]
            // 注意 a[i] > a[i - 1]
            var k = a.length - 1;
            while (a[k] <= a[i - 1]) k--;

            swap(a, i - 1, k);
        } // 否则，后缀是整个数组

        // 反转后缀
        var j = a.length - 1;
        while (i < j) {
            swap(a, i, j);
            i++;
            j--;
        }
    }
    ```

8. 找到一个与 Java Scripting API 兼容的 Scheme 实现。在 Scheme 中编写阶阶函数并在 Java 中调用它。

9. 选取 Java API 中你感兴趣探索的某部分——例如`ZonedDateTime`类。在`jjs`中运行一些实验：构建对象、调用方法并观察返回的值。你是否发现这比在 Java 中编写测试程序更简单？

## 15. Java 平台模块系统

面向对象编程的一个重要特性是封装。一个类的声明由一个公共接口和一个私有实现组成。类可以通过更改实现来演进，而不会影响其用户。模块系统为大型编程提供了类似的益处。模块可以有选择性地使类和包可用，从而控制其演进。

无论你在自己的应用程序中使用未使用 Java 平台模块，你都可能受到模块化 Java 平台的影响。本章将向你展示如何声明和使用 Java 平台模块。你还将学习如何迁移你的应用程序以与模块化的 Java 平台和第三方模块协作。

本章的要点是：

1. Java 平台模块系统的设计用于将 Java 平台模块化。
2. 你可以使用 Java 平台模块系统将应用程序和库模块化。
3. 模块是包的集合。
4. 模块的属性定义在`module-info.java`中。
5. 模块声明它依赖于哪些其他模块。
6. 模块提供了封装。可访问的包必须显式导出。
7. 模块可能通过打开包或整个模块允许对私有特性进行反射访问。
8. 模块系统提供了对`ServiceLoader`set 的支持。
9. 模块化 JAR 是一个包含`module-info.class`文件并置于模块路径上的 JAR。
10. 通过将普通 JAR 放在模块路径上，它将变成一个自动模块，导出并打开其所有的包。
11. 类路径上的所有包构成了未命名模块。
12. 为了迁移现有应用程序，你可能需要使用命令行选项来覆盖访问限制。
13. `jdeps`工具分析给定 JAR 文件的依赖关系。`jlink`工具产生具有最小依赖的应用程序。

### 15.1. 模块概念

在面向对象编程中，基本的构建块是类。类提供了封装。私有特性只有具有显式权限的代码（即类的方法）才能访问。这使得推理访问情况变得可能。如果一个私有变量发生了变化，你可以产生一个所有可能的作祸者集合。如果你需要修改私有表示，你知道哪些方法受了影响。

在 Java 中，包提供了更大的组织分组。包是类的集合。包也提供了一个层次的封装。任何具有包访问权限（既不是公共的不是私有的）的特性只能从相同包中的方法访问。

然而，在大型系统中，这种层次的访问控制是不够的。任何公共特性（即可以在包外部访问的特性）在任何地方都是可访问的。假设你想修改或丢弃一个特性。一旦它是公共的，就没有办法推理该更改的影响。

这就是 Java 平台设计者面临的局面。二十多年来，JDK 飞速增长，但显然某些功能已经过时。大家最喜欢的例子是 CORBA。你上一次使用它是什么时候？然而，`org.omg.corba`包随每个 JDK 分发。事实上，将所有的 CORBA 放入一个 JAR 文件并不困难，以便那些需要的人可以使用。

那么`java.awt`呢？它在服务器端应用程序中是不需要的，对吧？除非`java.awt.DataFlavor`类在基于 XML 的 Web 服务协议 SOAP 的实现中被。

Java 平台设计者面对巨大的代码球，决定他们需要一种提供更多控制的结构化机制。他们查看了现有的模块系统（如 OSGi）并发现它们不适用于他们的问题。相反，他们设计了一种新系统，称为 Java 平台模块系统，它现在是 Java 语言和虚拟机的一部分。该系统已成功用于 Java API 的模块化，如果你愿意，也可以将其应用于你的应用程序。

一个 Java 平台模块包含：

- 包的集合
- 可选的资源文件和其他文件（如原生库）
- 模块中可访问的包列表
- 该模块依赖的所有模块列表

Java 平台在编译时和虚拟机中强制封装和依赖关系。

Java 平台模块系统（Java Platform Module System）尚未解决某些问题，例如模块的版本控制。它不支持指定需要哪个版本的模块，也不支持在同一个程序中使用多个版本的模块。这些可能是所需的功能，但如果你需要它们，就必须使用 Java 平台模块系统以外的机制。

## 15.2. 模块的命名

模块是包的集合。模块中的包名不需要相互相关。例如，`java.sql`模块包含了`java.sql`、`javax.sql`和`javax.transaction.xa`包。此外，正如从这个示例所示，模块名与包名相同是完全可以的。

就像包名一样，模块名由字母、数字、下划线和点号组成。同样，和包名一样，模块之间不存在层级关系。如果你有一个`com.horstmann`模块和另一个`com.horstmann.corejava`模块，从模块系统的角度来看，它们是互不相关的。

在创建供他人使用的模块时，确保名称在全局范围内是唯一的至关重要。大多数模块名称预计将遵循“反向域名”约定，就像包名一样。

最简单的方法是以该模块提供的顶层包命名模块。例如，SLF4J 日志门面有一个`org.slf4j`模块，包含包`org.slf4j`、`org.slf4j.spi`、`org.slf4j.event`和`org.slf4j.helpers`。

这种约定防止了模块中的包名冲突。任何给包只能存在于一个模块中。如果模块名是唯一的，且包名以模块名开头，那么你的包名也是唯一的。

对于不供其他程序员使用的模块，可以使用较短的模块名，例如包含应用程序的模块。为了说明这是可行的，我将在本章中这样做。包含可能是库代码的模块将具有如`com.horstmann.greet`之类的名称，而包含程序（带有`main`方法的类）的模块将具有如`ch15.sec03`这样易记的名称。

#### Note

你只在模块声明中使用模块名。在 Java 类的源文件中，你永远不会引用模块名。相反，你按照一直以来的方式使用包名。

### 15.3. 模块化的“Hello, World!”程序

让我们把传统的“Hello, World!”程序放入一个模块中。首先，我们需要将类放入包中——“未命名包”不能包含在模块中。这里是：

```java
package com.horstmann.hello;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Modular World!");
    }
}
```

到目前为止，没有任何变化。要创建一个包含此包的`ch15.sec03`模块，你需要添加一个模块声明。将其置于名为`module-info.java`的文件中，位于基目录下（即包含`com`目录的相同目录）。按照约定，基目录的名字与模块名相同。

```text
ch15.sec03/
└ module-info.java
  com/
```



```text
└ horstmann/
  └ hello/
    └ HelloWorld.java
```

`module-info.java` 文件包含模块声明：

```java
module ch15.sec03 {
}
```

这个模块声明是空的，因为该模块向任何人提供任何内容，它不需要任何东西。

现在像往常一样编译：

```bash
javac ch15.sec03/module-info.java ch15.sec03/com/horstmann/hello/HelloWorld.java
```

`module-info.java` 文件看起来不像 Java 源文件，而且当然，不可能有一个名为 `module-info` 的类，因为类名不能包含连字符。`module` 关键字，以及在后续章节中将看到的 `requires`、`exports` 等关键字，都是“受限关键字”，它们只在模块声明中具有特殊含义。该文件被编译成类文件 `module-info.class`，其中包含二进制形式的模块定义。

要作为模块化应用程序运行此程序，你需要指定模块路径，它类似于类路径，但它包含模块。你还需要以 `modulename/classname` 的格式指定主类：

```bash
java --module-path ch15.sec03 --module ch15.sec03/com.horstmann.hello.HelloWorld
```

你可以使用单字母选项 `-p` 和 `-m` 代替 `--module-path` 和 `--module`：

```bash
java -p ch15.sec03 -m ch15.sec03/com.horstmann.hello.HelloWorld
```

无论哪种方式，都会出现 `"Hello, Modular World!"` 问候，证明你成功地将第一个应用程序模块化。

#### 注意

当你编译此模块时，会得到两个警告：

```text
warning: [module] module name component sec03 should avoid terminal digits
warning: [module] module name component ch15 should avoid terminal digits
```

这些警告旨在阻止程序员向模块名中添加版本号。你可以忽略它们，或者使用注解抑制它们：

```java
@SuppressWarnings("module")
module ch15.sec03 {
}
```

在某方面，`module` 声明就像类声明。

## 15.4. 需要模块

让我们创建一个新模块 `ch15.sec04`，其中程序使用 `JOptionPane` 显示“Hello, World!”消息：

```java
package com.horstmann.hello;

import javax.swing.JOptionPane;

public class HelloWorld {
    public static void main(String[] args) {
        JOptionPane.showMessageDialog(null, "Hello, World!");
    }
}
```

现在编译失败，并显示消息：

```text
error: package javax.swing is not visible
  (package javax.swing is declared in module java.desktop,
   but module ch15.sec04 does not read it)
```

JDK 已经模块化，`javax.swing` 包现在包含在 `java.desktop` 模块中。我们的模块需要声明它依赖于该模块。

在前面的节中，没有出现显式需求是因为我们只使用了 `java.lang` 包。该包包含在 `java.base` 模块中，而它是默认需要的。

注意，我们的 `ch15.sec04` 模块只列出了自己的模块需求。它需要 `java.desktop` 模块以便使用 `javax.swing` 包。`java.desktop` 模块本身声明需要另外三个模块，即 `java.datatransfer`、`java.prefs` 和 `java.xml`。

[图 15.1] 显示了以模块为节点的模块图。图的边（即连接节点的箭头）要么是声明的需求，要么是在未声明时对 `java.base` 的隐式需求。

模块图中不能存在循环。也就是说，一个模块不能直接或间接地引用它自己。

模块不会自动向其他模块传递访问权限。在我们的示例中，`java.desktop` 模块声明需要 `java.prefs`，而 `java.prefs` 模块声明需要 `java.xml`。这并没有赋予 `java.desktop` 使用 `java.xml` 包的权利。它需要显式地声明该需求。在数学术语中，`requires` 关系不是“传递的”。通常情况下这种行为是理想的，因为它使需求显性化，但正如你在第 15.11 节中看到的，在某些情况下你可以放松它。

本节开头的错误信息表明，我们的 `ch15.sec04` 模块没有“读取” `java.desktop` 模块。在 Java 平台模块系统的术语中，模块 `M` 在以下情况下读取模块 `N`：

1. `M` 需要 `N`。
2. `M` 需要一个间接需要 `N` 的模块（请参见第 15.11 节）。
3. `N` 是 `M` 或 `java.base`。

### 15.5. 导出包

在前面的节中，你看到如果模块想使用另一个模块的包，它必须需要该模块。然而，这并不会自动使所需模块中的所有包可用。模块使用 `exports` 关键字来声明哪些包是可访问的。例如，这里是 `java.xml` 模块声明的一部分：

```java
module java.xml {
    exports javax.xml;
    exports javax.xml.catalog;
    exports javax.xml.datatype;
    exports javax.xml.namespace;
    exports javax.xml.parsers;
    ...
}
```

该模块提供了许多包，但通过不导出某些包（例如 `jdk.xml.internal`）隐藏了其他包。

当一个包被导出时，它的 `public` 和 `protected` 类、接口，以及它们的 `public` 和 `protected` 成员在模块外部是可访问的。（如既往一样，`protected` 类型和成员仅在子类中可访问的。）

然而，未导出的包在自己的模块外部是不可访问的。这与模块之前的 Java 有很大不同。在过去，你可以使用任何包中的公有类，即使它不是公共 API 的一部分。例如，当公共 API 未提供适当的功能时，通常推荐使用如 `sun.misc.BASE64Encoder` 或 `com.sun.rowset.CachedRowSetImpl` 等类。

如今，你无法再访问 Java 平台 API 中未导出的包了，因为它们现在都包含在模块内部。结果是某些程序将无法在现代 Java 版本上运行。当然，没有人承诺过保持非公开 API 的可用性，所以这不应该让你感到震惊。

让我们在一个简单的场景中使用 `exports`。我们将准备一个模块 `com.horstmann.greet`，它导出一个也名为 `com.horstmann.greet` 的包，遵循以下约定：为他人提供代码的模块应以其内部顶层包命名。还有一个名为 `com.horstmann.greet.internal` 的包，我们没有导出它。

一个公有的 `Greeter` 接口位于第一个包中：

```java
package com.horstmann.greet;

public interface Greeter {
    static Greeter newInstance() {
        return new com.horstmann.greet.internal.GreeterImpl();
    }

    String greet(String subject);
}
```

第二个包包含一个实现该接口的类。该类是公有的，因为它在第一个包中被访问：

```java
package com.horstmann.greet.internal;

import com.horstmann.greet.Greeter;

public class GreeterImpl implements Greeter {
    public String greet(String subject) {
        return "Hello, " + subject + "!";
    }
}
```

`com.horstmann.greet` 模块包含了这两个包，但只导出第一个：

```java
module com.horstmann.greet {
    exports com.horstmann.greet;
}
```

第二个包在模块外部是不可访问的。

我们将应用程序放入第二个模块中，它将需要第一个模块：

```java
module ch15.sec05 {
    requires com.horstmann.greet;
}
```

**注意**

`exports` 语句后面跟着包名，而 `requires` 后面跟着模块名。

我们的应用程序现在使用 `Greeter` 来获取问候语：

```java
package com.horstmann.hello;

import com.horstmann.greet.Greeter;

public class HelloWorld {
    public static void main(String[] args) {
        Greeter greeter = Greeter.newInstance();
        System.out.println(greeter.greet("Modular World"));
    }
}
```

这是这两个模块的源文件结构：

```text
com.horstmann.greet
├ module-info.java
└ com
  └ horstmann
    └ greet
      ├ Greeter.java
      └ internal
        └ GreeterImpl.java

ch15.sec05
├ module-info.java
└ com
  └ horstmann
    └ hello
      └ HelloWorld.java
```

要构建此应用程序，首先编译 `com.horstmann.greet` 模块：

```bash
javac com.horstmann.greet/module-info.java \
    com.horstmann.greet/com/horstmann/greet/Greeter.java \
    com.horstmann.greet/com/horstmann/greet/internal/GreeterImpl.java
```

然后，在模块路径上带有第一个模块编译应用程序模块：

```bash
javac -p com.horstmann.greet ch15.sec05/module-info.java \
    ch15.sec05/com/horstmann/hello/HelloWorld.java
```

最后，在模块路径上同时带有两个模块运行程序：

```bash
java -p ch15.sec05:com.horstmann.greet \
    -m ch15.sec05/com.hello
```

你现在看到了构成 Java 模块系统的骨干 `requires` 和 `exports` 语句。

### 15.6. 模块与反射访问

在前面的节中，你看到模块系统强制了封装。模块只能访问显式导出的包。在过去，可以通过反射克服访问限制。然而，在模块化世界，这不再成立。具体来说，回想我们是如何访问私有字段的：

```java
Field f = obj.getClass().getDeclaredField("salary");
f.setAccessible(true);
double value = f.getDouble(obj);
f.setDouble(obj, 1.1);
```

除非安全管理器允许字段访问，否则 `f.setAccessible(true)` 将失败。如果你使用此类库并想使用模块，就必须小心。为了演示这个问题，我将使用 JSON-B 标准的实现。

**注意**

带有安全管理器的 Java 应用并不常见，并且许多库使用了反射。典型的例子包括将对象持久化到数据库的对象关系映射（如 JPA），以及在 Java 对象和 JSON 之间提供转换的“绑定层”。

```java
package com.horstmann.places;

public class Country {
    public Country() {}

    public Country(String name, double area) {
        this.name = name;
        this.area = area;
    }

    // ...
}
```

这里是一个演示如何将对象转换为 JSON 的短程序：

```java
package com.horstmann.places;

import javax.json.bind.*;
import javax.json.bind.config.*;

public class Demo {
    public static void main(String[] args) throws JAXBException {
        var belgium = new Country("Belgium", 30510);

        var config = new JsonbConfig()
            .withPropertyVisibilityStrategy(
                new PropertyVisibilityStrategy() {
                    public boolean isVisible(Field field) {
                        return true;
                    }

                    public boolean isVisible(Method method) {
                        return false;
                    }
                });

        Jsonb jsonb = JsonbBuilder.create(config);
        String json = jsonb.toJson(belgium);
        System.out.println(json);
    }
}
```

当你运行程序时，它输出：

```json
{"area":30510.0,"name":"Belgium"}
```

正如你所见，程序员不需要做任何事情来实现。通过反射，JSON-B 库确定了字段的名称和值。

现在让我们将 `Country` 和 `Demo` 类放入一个模块中。当你这样做时，`Demo` 程序将抛出异常并失败：

```text
Exception in thread "main" java.lang.reflect.InaccessibleObjectException:
    Unable to make field
private java.lang.String com.horstmann.places.Country.name accessible:
module v2ch09.openpkg2 does not "opens com.horstmann.places" to module org.eclipse.yasson
```

当然，在纯粹的理论中，违反封装性并探寻对象的私有成员是错误的。但诸如 XML 绑定或对象关系映射（ORM）等机制是如此常见，以至于模块系统必须适应它们。

通过使用 `opens` 关键字，模块可以 `open` 一个包，这允许在运行时访问给定包中的所有类型和成员，从而允许通过反射访问私有成员。这是我们的模块需要执行的操作：

```java
module ch15.sec06 {
    requires jakarta.json.bind;
    opens com.horstmann.places;
}
```

通过此更改，JSON-B 将能够正常工作。

模块可以被声明为 `open`，例如：

```java
open module ch15.sec06 {
    requires jakarta.json.bind;
}
```

开放模块授予对其所有包的运行时访问权限，就像所有包都已用 `exports` 和 `opens` 声明一样。然而，只有显式导出的包在编译时是可访问的。开放模块将模块系统的编译安全性与经典的许可运行时行为相结合。

回想第 0.0.0 节，JAR 文件除了类文件和清单外，还可以包含 `file resources`，这些资源可以使用 `Class.getResourceAsStream` 方法加载，现在也可以用 `Module.getResourceAsStream` 加载。如果资源存储在与模块中的包匹配的目录中，则该包必须对调用者开放。其他目录中的资源，以及类文件和清单，可以被任何人读取。

#### 注意

未来的库可能会使用 `variable handles`（变量句柄）而不是反射来读取和写入字段。`VarHandle` 类似于 `Field`。你可以使用它来读取或写入特定类的任何实例的特定字段。然而，要获取 `VarHandle`，库代码需要一个 `Lookup` 对象：

```java



```java
public Object getFieldValue(Object obj, String fieldName, Lookup lookup)

        throws NoSuchFieldException, IllegalAccessException {

    Class<?> cl = obj.getClass();

    Field field = cl.getDeclaredField(fieldName);

    VarHandle handle = MethodHandles.privateLookupIn(cl, lookup)

        .unreflectVarHandle(field);

    return handle.get(obj);

}
```

只要 `Lookup` 对象是在具有访问字段权限的模块中生成的，这种方法就是有效的。模块中的某些方法简单调用 `MethodHandles.lookup()`，它会产生一个封装了调用者访问权限的对象。通过这种方式，一个模块可以赋予另一个模块访问私有成员的权限。实际问题在于如何以最少的麻烦赋予这些权限。

### 15.7. 模块化 JAR

到为止，我们只是将模块编译到源代码的目录树中。显然，这对于部署来说是不满意的。相反，可以通过将其所有类放在一个 JAR 文件中，并在根目录下包含 `module-info.class` 来部署模块。这样的 JAR 文件被称为 `modular`（模块化）JAR。

要创建一个模块化的 JAR 文件，你可以像通常一样使用 `jar` 工具。如果你有多个包，最好使用 `-d` 选项编译，将类文件放在单独的目录中。如果目录不存在则会创建它。然后使用 `jar` 命令的 `-C` 选项在收集文件时切换到目录。

```bash
javac -d modules/com.horstmann.greet `find com.horstmann.greet -name *.java`

jar -cvf com.horstmann.greet.jar -C modules/com.horstmann.greet .
```

如果你使用 Maven、Ant 或 `Gradle` 等构建工具，只需像往常一样构建你的 JAR 文件即可。只要包含了 `module-info.class`，你就能得到一个模块化的 JAR。

然后你可以将模块化 JAR 包含在模块路径，模块就会被加载。

#### Caution

在过去，一个包的类有时分布在多个 JAR 文件中。（这种包被称为“拆分包”）。这可能永远不是一个好主意，而且在模块中是不可能实现的。

与普通 JAR 文件一样，你可以在模块化 JAR 中指定一个主类：

```bash
javac -p com.horstmann.greet.jar -d modules/ch15.sec05 `find ch15.sec05 -name *.java`

jar -c -v -f ch15.sec05.jar -e com.horstmann.hello.HelloWorld -C modules/ch15.sec05 .
```

启动程序时，你指定包含主类的模块：

```bash
java -p com.horstmann.greet.jar:ch15.sec05.jar -m ch15.sec05
```

在创建 JAR 文件时，你可以可选地指定版本号。使用 `--module-version` 参数，并在 JAR 文件名中添加 `@` 和版本号：

```bash
jar -c -v -f com.horstmann.greet@1.0.jar --module-version 1.0 -C com.horstmann.greet .
```

正如已经讨论过的，版本号并不用于模块系统解析模块，但它可以被其他工具和框架查询。

#### Note

你可以通过反射 API 获取版本。在我们的示例中：

```java
Optional<String> version = Greeter.class.getModule().getDescriptor().rawVersion();
```

产生一个包含 `"1.0"` 字符串的 `Optional`。

#### Note

类加载器的模块是 `layer`。模块系统将 JDK 模块和应用模块加载到 `boot layer`。预计 EE 应用服务器的开发者会使用该 API。

#### Tip

如果你想将模块加载到 JShell，请包含 JAR 的模块路径并使用 `--add-modules` 选项：

```bash
jshell --module-path . --add-modules my.module
```

### 15.8. 自动模块

你现在知道如何使用模块系统了。如果你从一个编写所有代码的新项目开始，你可以设计模块、声明依赖并将应用程序封装成模块化 JAR 文件。

然而，这是一个极罕见的情况。几乎所有项目都依赖第三方库。当然，你可以等待库的提供者将它们转换为模块。

但如果你不想等待呢？模块系统提供了两种机制来跨越今天的非模块世界与完全模块化应用之间的鸿沟：自动模块和未命名模块。

为了迁移目的，你只需将任何 JAR 文件放在模块路径而不是类路径上，就可以转换为模块。在模块路径上没有 `module-info.class` 的 JAR 被称为 `automatic module`（自动模块）。自动模块具有以下属性：

1. 该模块隐含地包含对所有其他模块的 `requires` 子句。
2. 其所有包都已导出并开放。
3. 如果 JAR 文件清单 `META-INF/MANIFEST.MF` 中存在键为 `Automatic-Module-Name` 的条目，该值成为模块名。
4. 否则，模块名从 JAR 文件名获取，删除末尾的版本号并将非字母数字字符序列替换为点。

前两条规则意味着自动模块中的包的行为就像它们在类路径上一样。使用模块路径的原因是为了其他模块的利益，允许它们表示对该模块的依赖。

例如，假设你正在实现一个处理 CSV 文件并使用 Apache Commons CSV 库的模块。你想在你的 `module-info.java` 文件中表示你的模块依赖于 Apache Commons CSV。

如果你将 `commons-csv-1.9.0.jar` 添加到模块路径，那么你的模块就可以引用该模块。它的名称是 `commons.csv`，因为末尾的版本号 `-1.9.0` 被移除，且非字母数字字符 `-` 被替换为点。

这个名称可能是一个可以接受的模块名，因为 Commons CSV 是广为人知的，不太可能有其他人尝试为另一个不同的模块使用相同的名称。但如果该 JAR 文件的维护者能够快速同意预留一个反向 DNS 名称，最好是将顶层包名 `org.apache.commons.csv` 作为模块名，这样会更好。他们只需要在 JAR 内部的 `META-INF/MANIFEST.MF` 文件中添加一行：

```text
Automatic-Module-Name: org.apache.commons.csv
```

最终，希望他们能通过添加带有预留模块名的 `module-info.java` 将 JAR 文件转换为真正的模块，这样所有其他以该名称引用 CSV 模块的模块都将继续工作。

#### Note

迁移到模块的计划是一场伟大的社会实验，没有人知道它是否会有良好的结果。在你将第三方 JAR 放入模块路径之前，请检查它们是否是模块化的，如果没有，请检查它们的清单文件（manifest）是否包含模块名。如果没有，你仍然可以将 JAR 转换为自动模块，但要准备好以后更新模块名。

### 15.9. 未命名模块

任何不在模块路径上的类都属于未命名模块（unnamed module）。从技术上讲，可能存在多个未命名模块，但它们共同的作用就像是一个单一模块，这个模块就称为未命名模块。与自动模块一样，未命名模块可以访问所有其他模块，并且它所有的包都被导出（exported）和开放（opened）。

然而，没有显式模块可以访问未命名模块。（显式模块既不是自动模块也不是未命名模块——即即在模块路径上拥有 `module-info.class` 的模块）。换句话说，显式模块总是免于“类路径地狱”的。

例如，假设你将 `commons-csv-1.9.0.jar` 放在类路径而不是模块路径。那么前一节的示例程序将无法启动：

```text
Error occurred during initialization of boot layer

java.lang.module.FindException: Module commons.csv not found, required by ch15.sec09
```

因此，迁移到 Java 平台模块系统必然是一个自下而上的过程：

1. Java 平台本身被模块化。
2. 接下来，库被模块化，可以通过使用自动模块或将其转换为显式模块来实现。
3. 一旦应用程序使用的所有库都已模块化，你就可以将应用程序的代码转换为一个模块。

#### Note

自动模块可以读取未命名模块，因此它们的依赖项可以放在类路径上。

### 15.10. 迁移命令行标记

即使你的程序没有使用模块，在运行 Java 9 及更高版本时，你也无法逃避模块化的世界。即使应用程序代码位于未命名模块的类路径上，且所有包都已导出和开放，它仍然与已模块化的 Java 平台进行交互。

从 Java 11 开始，编译时封装被严格执行。然而，在 Java 16 之前，允许运行时访问。默认行为是在每种违规行为首次出现时在控制台上显示警告。从 Java 16 开始，运行时的反射访问也被强制执行了。为了给你留出时间准备这一变化，Java 9 到 16 中的 `java` 启动器具有四种可能设置的 `--illegal-access` 标记：

1. `--illegal-access=permit` 是 Java 9 的默认行为，在首次发生非法访问时打印消息。
2. `--illegal-access=warn` 为每次非法访问都打印消息。
3. `--illegal-access=debug` 为每次非法访问打印消息和堆栈跟踪（stack trace）。
4. `--illegal-access=deny` 是 Java 16 的默认行为，拒绝所有非法访问。

`--illegal-access` 标记在 Java 17 中不再可用。

`--add-exports` 和 `--add-opens` 标记允许你调整遗留应用程序。考虑一个使用不再可访问的内部 API 的应用程序，例如 `com.sun.rowset.CachedRowSetImpl`。最好的补救是更改实现。（从 Java 7 开始，你可以从 `RowSetProvider` 获取缓存行集）。但假设你没有源代码的访问权限。

在这种情况下，使用 `--add-exports` 标记启动应用程序。指定你想要导出的模块和包，以及你想要导出该包的模块（在我们例中是未命名模块）。

```bash
java --illegal-access=deny --add-exports java.sql.rowset/com.sun.rowset=ALL-UNNAMED \
    -jar MyApp.jar
```

现在假设你的应用程序使用反射来访问私有字段或方法。未命名模块内部的反射是可以的，但不再能够通过反射访问 Java 平台类的非公共成员了。例如，某些动态生成 Java 类的库通过反射调用保护的 `ClassLoader.defineClass` 方法。如果应用程序使用此类库，添加标记：

```text
--add-opens java.base/java.lang=ALL-UNNAMED
```

为了让遗留应用运行而添加所有这些命令行选项时，你可能会得到地狱命令行。为了更好地管理大量选项，你可以将选项放在一个或多个文件中，并用 `@` 前缀指定这些文件。例如：

```bash
java @options1 @options2 Myjar
```

其中 `options1` 和 `options2` 文件包含了 `java` 命令的选项。

选项文件有一些语法规则：

- 使用空格、制表符或换行分隔选项。
- 对包含空格的参数使用双引号，例如 `"Program Files"`。
- 以 `\` 结尾的行与下一行合并。
- 反斜杠必须转义，例如 `C:\\Users`。
- 注释行以 `#` 开头。

### 15.11. 传递性与静态需求

在第 15.4 节中，你已经看到了 `requires` 语句的基本形式。在本节中，你将看到两种有变体。

在某些情况下，让给定模块的用户声明所有所需的模块可能是麻烦的。考虑 `java.desktop` 模块。它需要三个模块：`java.prefs`、`java.datatransfer` 和 `java.xml`。`java.prefs` 仅在内部使用。然而，`java.datatransfer` 和 `java.xml` 的类出现在公共 API 中，方法如下：

```java
java.awt.datatransfer.Clipboard java.awt.Toolkit.getSystemClipboard()

java.beans.XMLDecoder(org.xml.sax.InputSource is)
```

这不是 `java.desktop` 模块的用户应该考虑的问题。因此，`java.desktop` 模块使用 `transitive` 修饰符声明了该需求：

```java
module java.desktop
{
    requires java.prefs;

    requires transitive java.datatransfer;

    requires transitive java.xml;

    . . .
}
```

任何声明依赖 `java.desktop` 的模块现在自动需要这两个模块。

#### Note

某些程序员建议，当公共 API 使用另一个模块的包时，应该始终使用 `requires transitive`。但这不是 Java 语言的规则。考虑 `java.sql` 模块：

```java
module java.sql {

    requires transitive java.logging;

    ...

}
```

在整个 `java.sql` API 中，只有一次使用了 `java.logging` 模块的包，即 `java.sql.Driver.parentLogger` 方法，它返回一个 `java.util.logging.Logger`。不将此模块需求声明为传递性的完全是可以的。这样，只有那些真正使用该方法的模块才需要声明它们需要 `java.logging`。

`requires transitive` 语句的一个引人注目的用法是 `aggregator`（聚合）模块——一个没有包且只有传递依赖的模块。其中一个模块就是 `java.se` 模块，其声明如下：

```java
module java.se {

    requires transitive java.compiler;

    requires transitive java.datatransfer;

    requires transitive java.desktop;

    . . .

    requires transitive java.sql;

    requires transitive java.sql.rowset;

    requires transitive java.xml;

    requires transitive java.xml.crypto;

}
```

对细粒度模块依赖不感兴趣的程序员简单地需要 `java.se` 即可获取 Java SE 平台的所有模块。

最后，还有一种 `requires static` 变体，它表示某个模块在编译时必须存在，但在运行时是可选的。它有两个用例：

1. 访问一个在编译时处理并声明在另一个模块中的注解。
2. 如果另一个模块中的类可用，则使用它，否则执行其他操作，例如：

```java
try {
    new oracle.jdbc.driver.OracleDriver();

    ...

} catch (NoClassDefFoundError er) {

    // Do something else

}
```

### 15.12. 限定导出与开放

在本节中，你将看到 `exports` 和 `opens` 语句的变体，它们将范围缩小到指定的模块集合。例如，`java.base` 模块包含如下语句：

```java
exports sun.net to
  java.net.http,
  jdk.naming.dns;
```

这样的语句被称为 `qualified export`（限定导出）。列出的模块可以访问该包，但其他模块不能。

过度使用限定导出可能表明模块结构不佳。尽管如此，在现有代码库进行模块化时，它们可能会出现。在这里，`sun.net` 包被放置在 `java.base` 模块中，因为那里最主要需要它。然而，其他几个模块也使用了该包。Java 平台设计者不想让 `java.base` 变得更大，也不想让内部的 `sun.net` 包对外部可用。在全新的项目中，可以设计一个更具模块化的 API。

同样，你可以将 `opens` 语句限制到特定的模块。例如，在 15.6 节，我们可以使用限定的 `opens` 语句，如下：

```java
module ch15.sec06 {

    requires jakarta.json.bind;

    opens com.horstmann.places to org.eclipse.yasson;

}
```



现在，`com.horstmann.places` 包只对 `org.eclipse.yasson` 模块开放。

诚然，将对特定持久化机制的依赖放在模块描述符中似乎相当脆弱。相反，你可以将所有需要持久化的类放在一个单独的包中，并向所有模块开放该包，以便任何持久化机制都可以访问它。

### 15.13 服务加载

`ServiceLoader` 类（见第 0.0.0 节）提供了一种匹配服务接口与实现的轻量级机制。Java 平台模块系统使得使用这种机制变得更容易。

这里是对服务加载的快速回顾。一个服务有一个接口和一个或多个可能的实现。这里是一个简单接口的示例：

```java
public interface GreeterService {

    String greet(String subject);

    Locale getLocale();

}
```

一个或多个模块提供实现，例如：

```java
public class FrenchGreeter implements GreeterService {

    public String greet(String subject) { return "Bonjour " + subject; }

    public Locale getLocale() { return Locale.FRENCH; }

}
```

服务消费者必须根据其认为合适的任何标准，从所有提供的实现中选择一个。

```java
ServiceLoader<GreeterService> greeterLoader = ServiceLoader.load(GreeterService.class);

GreeterService chosenGreeter;

for (GreeterService greeter : greeterLoader) {

    if (...) {

        chosenGreeter = greeter;

    }

}
```

过去，实现是通过在包含实现类的 JAR 包的 `META-INF/services` 目录中放置文本文件提供的。模块系统提供了更好的方法。不再使用文本文件，而是向模块描述符添加语句。

提供服务实现的模块添加一个 `provides` 语句，列出服务接口（可能定义在任何模块中）和实现类（必须是该模块的一部分）。这是一个来自 `jdk.security.auth` 模块的示例：

```java
module jdk.security.auth {

    ...

    provides javax.security.auth.spi.LoginModule with

        com.sun.security.auth.module.Krb5LoginModule,

        com.sun.security.auth.module.UnixLoginModule,

        com.sun.security.auth.module.JndiLoginModule,

        com.sun.security.auth.module.KeyStoreLoginModule,

        com.sun.security.auth.module.LdapLoginModule,

        com.sun.security.auth.module.NTLoginModule;

}
```

这等于 `META-INF/services` 文件。

消费模块包含一个 `uses` 语句：

```java
module java.base {

    ...

    uses javax.security.auth.spi.LoginModule;

}
```

当消费模块中的代码调用 `ServiceLoader.load(GreeterService.class)` 时，将执行匹配。

### 15.14 模块工具

`jdeps` 工具分析一组 JAR 文件的依赖关系。假设你想对 JUnit 4 进行模块化。运行：

```bash
jdeps -s junit-12.jar
```

`-s` 标志生成一个摘要：

```text
hamcrest.jar -> java.base

junit-12.jar -> hamcrest
```

这告诉你是模块图。

还有一个为“dot”语言生成图形化输出的选项。假设你安装了 dot 工具，运行以下命令：

```bash
jdeps -s -dotoutput /tmp/junit junit-12.jar hamcrest.jar

dot -Tpng /tmp/junit/summary.dot > /tmp/junit/summary.png
```

然后你就得到了这张 `summary.png` 图片。

`--generate-module-info` 选项为每个分析的模块产生 `module-info` 文件：

```bash
jdeps --generate-module-info /tmp/junit junit-12.jar
```

如果你省略 `-s` 标志，将获得模块列表以及包到模块的映射。如果你添加 `-v` 标志，列表将映射类到所需的包。

你使用 `jlink` 工具创建一个独立的应用程序。生成的镜像比整个 JDK 要小得多。你指定要包含的模块和输出目录。

```bash
jlink --module-path com.horstmann.greet.jar:ch15.sec05.jar:$JAVA_HOME/jmods \
    --add-modules ch15.sec05 --output /tmp/hello
```

输出目录有一个 `bin` 子目录，其中包含 `java` 可执行文件。如果你运行：

```bash
/tmp/hello/bin/java -m ch15.sec05
```

将调用模块主类的 `main` 方法。

`jlink` 的意义在于它封装了运行应用程序所需的模块集合。你可以列出所有模块：

```bash
/tmp/hello/bin/java --list-modules
```

在这个示例中，输出是：

```text
ch15.sec05

com.horstmann.greet

java.base@9
```

这可以作为打包应用程序的基础。你仍然需要为多个平台生成文件集并为应用程序生成启动脚本。

你可以使用 `jimage` 命令来检查运行时镜像。然而，该格式是 `JVM` 内部使用的，且运行时镜像并非供其他工具生成或使用的。

最后，`jmod` 工具用于构建和检查包含在 `JDK` 中的模块文件。当你查看 `JDK` 内部的 `jmods` 目录时，你会发现每个模块都有一个扩展名为 `jmod` 的文件。不再有 `rt.jar` 文件了。

与 JAR 文件一样，这些文件包含类文件。此外，它们还可以包含原生代码库、命令、头文件、配置文件和法律公告。JMOD 文件使用 ZIP 格式。你可以使用任何 ZIP 工具检查其内容。

与 JAR 文件不同，JMOD 文件仅对链接有用；也就是说，用于生成运行时镜像。除非你还想将二进制文件（如原生代码库）封装到你的模块中，否则你不需要生成 JMOD 文件。

### 练习题

1. “限制关键字” `module`、`exports`、`requires`、`uses`、`to` 等在模块声明中具有特定含义。你可以将它们作为类、包或模块的名字吗？特别是，你可以创建一个名为 `module` 的模块吗？尝试创建一个可以产生如下声明的上下文：

   ```java
   requires requires;

   exports exports;

   opens to to opens;
   ```

   创建一个名为 `transitive` 的模块如何？你可以要求它吗？

2. 尝试在第 15.5 节中的程序从 `HelloWorld` 类访问 `GreeterImpl`。发生了什么？是编译时错误还是运行时错误？

3. 在第 15.5 节的程序中，使用 `java.util.logging.Level` 让 `Greeter` 在级别小于 `Level.INFO` 时返回空字符串。这对模块描述符有什么影响？

4. 如果将 Apache CSV JAR 作为未命名模块放在类路径上，并尝试从模块访问它的包，会发生什么？你反而应该怎么做？

5. 开发一个示例，展示对 `java.sql`、`java.xml` 或 `java.desktop` 等模块使用 `requires transitive` 依赖的引人注用法。

6. 为 `requires static` 的两种用例开发示例。你会想要使用 `requires transitive static` 吗？

7. 在第 15.13 节的程序中，如果省略了 `provides` 或 `uses` 语句会发生什么？为什么这些不是编译时错误？

8. 在第 15.13 节的程序中，使用服务提供者工厂；即一个具有公共静态方法 `provider()` 并返回服务对象的类。

9. 重新组织第 15.7 节中的程序，使服务接口和实现被定义在不同的模块中。

10. 下载开源 JFreeChart 程序，并使用 `jdeps` 分析演示程序以及 `lib` 子目录下 JAR 文件的依赖关系。

11. 将 JFreeChart 的演示程序转换为模块，并将 `lib` 子目录下的 JAR 文件转换为自动模块。

12. 运行 `jlink` 以获取 JFreeChart 演示程序的运行时镜像。

13. 尝试在较新版本的 Java 下运行 Java 8 版本的 JavaFX SceneBuilder 程序。你需要哪些命令行标记来启动它？你是如何发现的？
