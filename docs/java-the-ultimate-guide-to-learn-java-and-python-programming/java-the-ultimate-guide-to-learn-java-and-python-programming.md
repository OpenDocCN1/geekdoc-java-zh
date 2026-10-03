
# Java：学习 Java 和 Python 编程终极指南

我认为接几本书对你也会感兴趣：

Stephen Hoffman

Amazon Prime 和 Kindle 借阅库

# 引言

Java 编程语言后的公司是 Sun Microsystems。该语言最初于 1991 年引入。由 Mike Sheridan、Ed Frank、Chris Warth、Patrick Naughton 和 James Gosling 组成的团队开发。由于其面向对象的特性，Java 语言在数据关注、类创建、编写指令以及实例和对象的创建方面是可以被重用的。

# 四大 Java 平台

Java 编程语言中有四个主要平台。它们分别是：

- Java 标准版 (`Java SE`)
- Java 企业版 (`Java EE`)
- Java 微型版 (`Java ME`)
- JavaFX

用于计算机软件的 Java 应用是在 Java 的标准版上开发的。用于 Web 服务器的 Java 应用是在企业版上开发的，而用于多媒体平台的 Java 应用是在 JavaFX 上开发的。大多数基于 JavaFX 的应用就是我们通常所说的 Flash 播放器。最后，用于移动设备的 Java 应用是在微型版 Java 平台上开发的。你可以使用以下 IDE：

# 初学者工具

为了开启你的 Java 编程之旅，你需要选择使用哪种 IDE。IDE，也称为集成开发环境，是你在编写 Java 应用时的工作空间。把它想象成你编写 HTML 代码时的记事本即可。然而，IDE 是专为 Java 语言设计的，这意味着它具备了你在 Java 开发中可能需要的所有工具。

以下是你可以使用的 IDE：

- BlueJ – 这是一个非常适合初学者的 IDE。你可以轻松地导航到它简单的界面。它最初的设计初衷也是为了帮助初学者熟悉 Java 语言的基本概念。
- DrJava – 这是一个轻量级 IDE。与 BlueJ 类似，DrJava 也是为初学者设计的。尽管它具有简单的用户界面，但 DrJava 拥有足够每个高级 Java 开发者都可以使用的工具。
- Eclipse – 当今流行的 IDE 之一，Eclipse 是一个具有响应式导航和设计的开源平台。显然，与列表中的其他 IDE 相比，它具有整洁的用户界面。
- NetBeans – 这是另一个目前在 Java 开发中常用的流行 IDE。它非常推荐初学者使用，因为它拥有快速且强大的工具，并兼容 Java 语言的所有平台。

每个 IDE 都有独特的用户界面和易于导航的特点。请随心使用任何你觉得最舒适的 IDE。请记住，所有的 IDE 都兼容 Java 语言的所有平台。

## 项目创建

编写 Java 程序的第一步是在你选择的 IDE 中启动一个新的空项目。你可以通过以下方式导航最顶部工具栏来操作：

`File -> New Project`

选择 `New Project`（新建项目）后，将出现一个新窗口，你可以在列表中选择类别。在 `Categories`（类别）列表中选择 Java，然后在相邻的窗口面板中选择 `Java Application`（Java 应用）。之后，点击 `Next`（下一步）按钮，系统会提示项目名称以及你想保存项目的位置。

始终记住项目名称，因为在过程中你会被要求返回同一个项目。

## 主类创建

创建新项目后，IDE 会自动创建包（`package`）和主类（`main class`）。包也被称为源包，作为文件夹可以在其中高效地组织 Java 项目的所有资产，例如类和实例。但请注意，包仅仅是资产组织的标识符。你可以将它们考虑为计算机中的文件夹，并据此组织你的文件。

包下应该有一个主类。如果 IDE 没有自动创建主类，你可以通过以下方式导航主菜单来创建它：

`File -> New File -> Java Class`

主类在 Java 程序中起着至关重要的作用。主方法（`main method`）是打开 Java 程序时最初执行的内容，包含在主类中。在其他编程语言中，主方法被称为入口点。

## 编写包语句

现在我们已经在 Java 项目中有了主类，现在准备好编写我们的第一行 Java 编程语言代码——包语句（`package statement`）。该语句是程序的可选部分，仅为了学习目的而向你介绍。它使用以下语法编写：

```java
package [package name];
```

如果没有写这一行，IDE 将自动查找默认包。换句话说，如果你正在处理一个包含多个包的 Java 项目，包语句可能会很有用。请记住，包名必须与类所属的包名匹配。例如，假设你的包名为“javatestproject”。在你的 IDE 中，语法看起来应该是这样的：

```java
1
2 package javatestproject;
```

## 编写类声明

紧接包语句之后的是类声明。我们需要遵循的语法如下：

```
[access modifier] class [class name]
```

你可以使用两种访问修饰符（`access modifiers`）：`public`（公共）和 `private`（私有）。`private` 修饰符防止其他类访问声明的类，而 `public` 修饰符允许其他类访问声明的类。目前，让我们专注于并将 `public` 作为我们第一个 Java 程序的访问修饰符。

类名（`Class name`）正如其名称所示，是你为主类指定的名称。注意，Java 编程语言是区分大小写的，因此请确保你的主类名使用正确的大小写字母。假设我们的主类名为“TestProject”，那么我们现在应该拥有这样的：

```java
1
2 package javatestproject;
3
4 public class JavaTestProject {
5
6 }
7
```

左括号 ( `{` ) 和右括号 ( `}` ) 代表 Java 代码块的开始和结束。这有助于程序确定特定代码块何时开始以及何时结束。

## 编写主方法

现在我们已经完成了类的声明，是时候为我们的第一个程序声明主方法了。在主方法中，我们将使用两个关键字：`void` 和 `static`。

`void` 关键字向 Java 虚拟机（也称为 `JVM`）信号程序已成功运行并结束。`static` 关键字告诉程序字段指的是类，而不是类中的对象或实例。换句话说，程序可以在不在该类中创建实例的情况下自由地访问该类。由于主方法作为程序入口点的性质，将其声明为 `static` 是至关重要的。因此，我们主方法的声明语法应该遵循此格式：

```
[access modifier] static void
```

然而，这还不是主方法的完整声明。我们还应该添加参数 `main(String[] args)` 以允许程序执行命令行参数。因此，我们主方法的最终代码应该是这样的：

`public static void main(String[] args)`

如果将其添加到上面的代码行中，我们的 IDE 看起来应该是这样的：

```java
1
2 package javatestproject;
3
public class JavaTestProject {
5
6 public static void main(String[] args) {
7
8 }
9
10 }
11
```

## 编写程序输出

到目前，你已经涵盖了 Java 程序的基本部分。遗憾的是，我们还没有告诉程序具体需要做什么。

我们希望程序执行的是传递一条消息。这就是我们所说的程序输出（`Program Output`）或输出流（`Output Stream`）。为了让程序传递消息，我们应该使用以下语法：

`System.out.print("message");`

你可以将参数 `print` 替换为 `println`。会将输出打印到新行。因此，另一种格式看起来应该是这样的：

`System.out.println("message");`

让我们现在使用上面的命令让程序打印“Java is Awesome!”。我们的语法应该是：

`System.out.println("Java is Awesome!");`

一旦我们插入输出，我们的 IDE 看起来应该是这样的：

```java
1
2 package javatestproject;
3
4 public class JavaTestProject {
5
6 public static void main(String[] args) {
7
8 System.out.println("Java is Awesome!");
9
10 }
11 }
```

## 允许用户输入

Java 语言允许用户通过发送输入与程序通信。我们可以通过使用内置的 `Scanner` 类来实现。

`Scanner` 类从计算机键盘收集用户输入。它将收集的数据存储在变量中，这些变量可以在程序的输出流中执行。为了做到，我们需要在包语句之后添加以下行：

`import java.util.Scanner;`

这是一个导入语句的示例，它信号程序从名为 `java.util` 的内置 Java 包导入 `Scanner` 类。这是我们在 IDE 中添加它们的地方：

```java
package javatestproject;
import java.util.Scanner;
```

然而，这还没有产生任何作用。我们需要先为 scanner 类分配一个变量名，以便将 scanner 收集的数据调用到我们的输出流。我们可以通过以下语句为 scanner 类分配变量名：

`Scanner [variable name] = new Scanner(System.in);`

你可以为变量分配任何名称。一种常见的做法是以大写字母开头，后跟小写字母。使用大写字母分隔单词也是一种好习惯。假设我们想将 scanner 变量命名为“userinput”。与其用小写写整个变量名，不如将“user”和“input”的首字母替换为大写。因此，语句看起来像这样：

`Scanner UserInput = new Scanner(System.in);`

我们应该将该语句插入主方法声明后的代码块中。因此，IDE 应该如下：

```java
package javatestproject;
import java.util.Scanner;

class JavaTestProject {
    public static void main(String[] args) {
        Scanner UserInput = new Scanner(System.in);
    }
}
```

通过这段 Java 代码，我们正在命令程序将用户输入赋值给名为“UserInput”的变量。现在，让我们告诉程序调用输入。例如，让我们尝试通过程序询问用户的姓名，并让程序本身通过交付另一个输出返回用户的姓名。我们的程序应该遵循以下模式：

第一个输出 -> 输入 -> 第二个输出

为了创建第一个输出，我们将使用之前从编写输出中学到的知识。让我们在扫描器分配变量名的语句上方，通过断言下述语句来询问用户的姓名：

`System.out.print("What should we call you?");`

接下来，让我们通过将收集到的数据调用第二个输出来返回用户的回答。我们可以通过在扫描器变量名语句下方编写第二个输出来实现。我们的第二个输出应该是：

```java
System.out.println("Hello " + UserInput.nextLine());
```

通过此，我们就可以写出最终的 Java 程序，如下：

```java
package javatestproject;
import java.util.Scanner;

class JavaTestProject {
    public static void main(String[] args) {
        System.out.print("What should we call you?");
        Scanner UserInput = new Scanner(System.in);
        System.out.println("Hello " + UserInput.nextLine());
    }
}
```

# 第 2 章 – 变量

由于上面对 scanner 类的介绍，我们现在已经熟悉了变量。然而，变量的全部潜力对我们来说仍然未知。

变量充当数据的容器。它们允许我们以更方便的方式调用特定的数据。我们还可以通过变量使用不一致的值创建一组新数据。大多数编程语言都使用变量，开发者能够通过它们解决算术运算和逻辑运算。

为了使用变量，我们需要首先声明它，并在声明时分配一个数据类型。通过这样做，程序能够识别变量内部存储的是什么类型的值。

```java
try {
    Object homeObj = lookup("ejb/service/CreditRating");
    CreditHome cis = (CreditHome)homeObj;
    session.bean.creditRatingName();
    CreditRatingService ratingService = (CreditRatingService)homeObj;
    PortableRatingObject rating = ratingService.narrow(cis.ssn);
    if (rating == null) {
        addAuditTrailEntry("Failed to lookup: " + session.bean.creditRatingName()
            + " - Class does not exist but has been"
            + " - successfully deployed.");
    }

    CreditRatingService ratingService = ratingHome.create();
    Element sm = getFromScope();
    sm = (Element)variableData("output","paid","/ssm");

    if (ratingService.getRating(sm).booleanValue()) {
        addAuditTrailEntry("Rating is " + rating);
    }
    setVariableData("output","payload","rating", new Integer(rating));
} catch (Exception e) {
    addAuditTrailEntry("Error: " + e.getMessage());
}
```

## 数据类型概述

有不同的数据类型，我们可以在各种操作和函数中使用每类型。在学习如何为变量分配数据类型之前，首先熟悉这些数据类型是重要的。以下是 Java 编程语言中可以用于变量的数据类型及其简要描述：

| 数据类型 | 描述 |
|---|---|
| Boolean | 这种数据类型只有两个可能的值：true 或 false。 |
| Byte | 与所有数值数据类型相比，这种数据类型的范围最小。 |
| Character | 这种数据类型只能存储单个字符。 |
| Double | 这种数据类型存储双精度数值。 |
| Float | 这种数据类型存储单精度数值。 |
| Integer | 这种数据类型存储整数。 |
| Long | 这种数据类型存储长整数。 |
| Short | 这种数据类型存储短整数。 |
| String | 这种数据类型是处理字符串最简单的方式。 |

### 变量的创建

我们需要使用整数类型编写变量。让我们将其命名为“MyAge”。我们的语法应该是：

```java
int MyAge;
```

以下是声明每个数据类型的示例：

| 语法 | 示例 |
|---|---|
| boolean | `boolean TestVar = true;` |
| byte | `byte TestVar = 0;` |
| char | `char TestVar = ' ';` |
| double | `double TestVar = 31.1d;` |
| float | `float TestVar = 1.3f;` |
| int | `int TestVar = 5;` |
| long | `long TestVar = 0L;` |
| short | `short TestVar = 32000;` |
| String | `String TestVar = null;` |

### 数据类型与用户输入



```java
public class CreateObjectDemo {
    public static void main(String[] args) {
        // 创建点对象两个矩形对象
        Point origin = new Point(50, 45);
        Rectangle rect_one = new Rectangle(origin, 100, 180);
        Rectangle rect_two = new Rectangle(50, 100);
        // 显示 rect_one 的宽度、高度和面积
        System.out.println("Width of rect_one: " + rect_one.width());
        System.out.println("Height of rect_one: " + rect_one.height());
        System.out.println("Area of rect_one: " + rect_one.area());

        // 设置 rect_two 的位置
        rect_two.origin = origin;
        System.out.println("Position of rect_two: " + rect_two.origin.x());
        System.out.println("Position of rect_two: " + rect_two.origin.y());
        // 移动 rect_two 并显示其新位置
        rect_two.move(10, 70);
    }
}
```

```java
package javatestproject;
import java.util.Scanner;
```

## 4

```java
class JavaTestProject {
    public static void main(String[] args) {
        System.out.print("What year were you born?");
        Scanner BirthYear = new Scanner(System.in);
        System.out.println("You were born in " + BirthYear.nextInt());
    }
}
```

### 将用户输入存储到另一个变量中

当调用 `Scanner` 类从用户输入收集数据时，我们也创建了一个变量。例如，在我们关于出生年份的 Java 程序中，我们创建了一个名为 `BirthYear` 的新变量，并将收集到的数据存储其中。这里的问题是，当我们在程序输出中执行 `Scanner` 类时，直接在变量名后面写了参数。因此，我们可以将整个语法存储到另一个变量中以简化代码。当你需要在多个语句中调用收集的数据时，这样做会非常方便。你可以通过在声明变量的同时将 `Scanner` 语法赋值为变量的值来实现这一点。

让我们创建另一个程序，计算用户五年后的年龄。这一次，我们也将 `Scanner` 调用语句存储到另一个变量中。它应该是这样的：

```java
package javatestproject;
import java.util.Scanner;

class JavaTestProject {
    public static void main(String[] args) {
        System.out.print("How old are you?");
        Scanner UserAge = new Scanner(System.in);
        int Age = UserAge.nextInt();
        System.out.println("You will be " + (Age + 5) + " five years from now");
    }
}
```

从我们的示例程序中，我们将 `Scanner` 调用语句存储在一个名为 `Age` 的新变量中。在下一行中，我们调用了用户收集的整数，并编写了一个简单的算术运算，以提供用户在五年后几大。请注意，数学表达式被包含在括号中。如果没有括号，程序将把 `Age` 变量中存储的值与数值 `5` 连接，而不是将这两个值相加。

除了整数外，你还可以使用以下参数通过 `Scanner` 类调用语句查找其他类型的数据：

- `nextByte()` 用于 `Byte` 类型值
- `nextShort()` 用于 `Short` 类型值
- `nextLong()` 用于 `Long` 类型值
- `nextFloat()` 用于 `Float` 类型值
- `nextDouble()` 用于 `Double` 类型值

# 第3章 – 运算符

从第一章以来，我们一直在使用不同的运算符，我们使用的最常用的运算符是赋值运算符。它由等号 (`=`) 定义，指示程序为变量指定特定的值。

除了赋值运算符外，还有五个运算符用于在 Java 编程语言中处理数据。它们及其作为数学运算符的角色如下：

- 加法运算符，用加号 (`+`) 表示。它命令程序给出多个值之和。
- 减法运算符，用连字符号 (`-`) 表示。它命令程序给出多个值之差。
- 乘法运算符，用星号 (`*`) 表示。它命令程序给出多个值之积。
- 除法运算符，用斜杠 (`/`) 表示。它命令程序给出多个值之商。
- 取模运算符，用百分号 (`%`) 表示。它命令程序除以两个数值，并给您提供这些数值的余数。

## 单个程序中的总结

熟悉运算符的最佳方法是创建一个 Java 程序，在其中我们可以至少使用一个数学运算符。我们还将整合目前为止学的所有内容。换句话说，我们还将使用 `Scanner` 类从用户那里收集数据，然后执行算术表达式向用户提供高效的输出。

在这个程序中，我们将要求用户输入两个数值，并让程序提供这些数值之和。让我们开始编写我们的 Java 程序：

```java
package javatestproject;
import java.util.Scanner;

class JavaTestProject {
    public static void main(String[] args) {
        int Value1, Value2, Total;
        System.out.print("Please enter the first value");
        Scanner FirstValue = new Scanner(System.in);
        Value1 = FirstValue.nextInt();
        System.out.println("Please enter the second value");
        Scanner SecondValue = new Scanner(System.in);
        Value2 = SecondValue.nextInt();
        Total = Value1 + Value2;
        System.out.println("The total is " + Total);
    }
}
```

---

Stephen Hoffman

快速学习 Python - 快速掌握 Python 编程语言基础的终极速成课程

STEPHEN HOFFMAN

- 如何运行程序
- 开始编写
- 它应该是什么样的
- 声明
- 关键字定义
- 第七章 - Python 中的布尔值，True 或 False
- 布尔型字符串
- 逻辑运算符布尔
- 使用变量计数
- 计数器
- 使用 While 循环计数
- 乘法表
- 设置异常处理块
- 它是如何工作的？
- 代码示例

# 引言

Python 可用于各种项目，许多程序员在选择任何其他编程语言之前选择 Python 是有原因的。Python 可用于 Web 应用程序、系统任务自动化、查找图像颜色以及许多其他不同的编程任务！

Python 是一种通用编程语言，创建于 20 世纪 80 年代后期，以臭名的 Monty Python（蒙提蟒剧团）命名。成千上万的程序员使用它完成从在英特尔测试微芯片到使用 PyGame 库构建视频游戏的任何工作。它是一门类似于英语的小型语言，并且已经存在数百个第三方库。

程序员在许多不同的编程语言中选择 Python 主要有两个原因。

第一个原因是可读性。因为它非常接近英语，使用 `not`（不）和 `in`（在……之中）等单词使得你能够大声读出脚本，而不会觉得像在读某种被遗忘已久的语言。Python 极其严格的标点符号规则也有助于此，你不需要在代码中到处写大括号。

此外，Python 有一些被称为 PEP 8 的设定规则，告诉 Python 开发者如何格式化代码。这意味着你将始终知道在哪里换行，而且你从别人那里获取的每段代码看起来都很相似，并且和你的代码一样易读。这使得开发者之间的协作变得非常容易！

第二个原因是，对于你想在 Python 中做的几乎任何事情，都有预先的库。这门语言已经存在了二十多年，因此有很多程序员已经精通这门语言，并知道如何编写你想要的内容。所以，如果你自己有疑问，尝试找另一个已经做过的人吧！

所以，你应该学习 Python 的主要原因是它简单，而且你很容易与其他人合作来磨练你的技能。让我们开始吧！

# 第一章 – 配置 Python

在涉及 Python 编程时，你应该知道的第一点是，许多操作系统已经安装了 Python。除了 Windows 之外，大多数操作系统都默认安装了 Python。如果你想确认你的电脑是否安装了它，请运行终端程序打开命令行，并输入 `python -V`。

如果你看到版本信息，说明你的电脑已经安装了 Python。然而，如果你得到 `bash: python: command not found`，说明尚未安装。

## 安装

第一步是去 www.python.org/downloads 下载适用于你操作系统的安装程序。下载完成后，按照说明进行操作。在安装过程中，务必勾选“Add Python to PATH”（将 Python 添加到路径）。这将允许你从命令行运行 python。

### 解释器

Python 解释器是一个执行 Python 代码的程序。你可以通过在终端中输入 `python` 来交互式使用它。这将打开一个提示符 `>>>`，你可以在其中逐行输入 Python 代码并立即看到结果。

### 如何运行程序

要运行 Python 脚本，你可以将代码保存为带有 `.py` 扩展名的文本文件，然后在命令行中使用命令 `python filename.py` 运行。

### 文本编辑器

有很多文本编辑器可以用来编写 Python 代码，从简单的记事本或 TextEdit 到像 PyCharm 或 VS Code 这样的集成开发环境 (IDE)。

### 开始编写

要编写你的第一个程序，创建一个名为 `hello.py` 的新文件并输入 `print("Hello, World!")`。运行程序即可在屏幕上看到输出。

# 第二章 – 变量

变量是在 Python 中可以使用的字符。

你还可以通过多次赋值同时给多个变量分配一个单值。

变量 a、b 和 c 被分配到相同的内存位置，并赋值为 1；`a = b = c = 1`。

例如：

这将打印出：面积是：200

现在你已经知道如何使用变量，让我们更详细地查看解释器。

# 第三章 – 解释器

在可用该解释器的机器上，解释器通常安装在 `/usr/local/bin/python` 位置。

将 `/usr/local/bin` 放入 Unix shell 的搜索路径中，将能够通过在 shell 中输入 `python` 命令来启动它。

当你开始交互模式时，它将使用三个大于符号 `>>>` 提示输入以下命令。它在打印第一个提示符之前，会打印一条显示其版本号和版权声明的欢迎消息。

### 交互式

当交互式使用时，每次启动解释器时执行一些标准注释是一个好主意。你可以在设置名为 `PYTHONSTARTUP` 的环境变量时，将其设置为包含启动命令的文件名来实现这一点。这类似于 Unix shell 的 `.profile` 功能。要将此行添加到你的 `.bashrc` 中：

```bash
export PYTHONSTARTUP=$HOME/.pythonstartup
```

创建或更改 `.pythonstartup` 文件并将 Python 代码放入其中，如下所示：

```python
import os
os.system('ls -l')
```

如果你使用的是 Linux 机器，按下 Ctrl+D 即可退出交互式提示符。

# 第四章 – 注释的重要性

Python 中的注释严格来说是为了阅读代码的人的，无论是你还是别人。这是向他人传达代码意图的一种良好方法，以便他们更好地协作。然而，在 Python 中添加注释有两种在编程行业中被通用的接受的方法。

单行注释将以 `#` 符号开始，并以行尾结束。Python 将忽略 `#` 符号之后到行尾的所有文本，因为它认为那不是命令的一部分。

跨越单行的注释通过通过插入以 `"""` 为端分隔符的多行字符串来实现。它们旨在为任何阅读代码的人提供文档说明。

让我们来看两个例子，这样你就能明白我在说什么了。

```python
## 这是 Python 中的一个注释

print("Hello World") # 这也是 Python 中的一个注释

"""
这是一个跨越多行的
多行注释示例

"""
```

现在你已经知道如何与他人协作，以及如何通过注释为自己的代码保持整洁，让我们来看看 Python 的 docstrings（文档字符串字符串）。

# 第五章 - Python Docstrings

Docstrings（或 Python 文档字符串）提供了一种将文档与 Python 函数、模块、方法和类关联的良好方法。对象的 docstring 由对象定义中第一条语句的字符串常量组成。

在用于记录特定代码的源代码中指定了它。与普通的源代码注释不同，docstring 应该是对函数“做什么”的描述，而不是“如何做”。所有函数都需要有一个 docstring。

这使得程序可以在运行时检查内容，例如，作为交互式帮助系统或元数据。你可以使用对象上的 `__doc__` 属性来访问 docstring。

## 它应该看起来像

docstring 行将以大写字母开头并以句号结束。第一行将是简短描述。不要写你的对象的名称。如果文档字符串有多行，第二行应该是空的，这样在视觉上将摘要与描述的其余部分隔离开。其余部分是一个或多个段落，描述了对象的调用约定以及任何其他重要内容。

这是一个例子，你可以看到我在表达什么：

```python
"""这是一个简单的docstring示例。"""

def my_function():
    """这是一个更复杂的
    docstring。
    它可以包含多个行
    并提供更多细节。
    """
    pass
```

## 布尔字符串

可以对字符串的真值进行测试。返回类型应为布尔值或 True 或 False。让我们来看一个例子。首先，创建一个新变量并给它赋值值。

```python
numberone_string = "Hello World"
numberone_string.isalnum()
numberone_string.isalpha()
numberone_string.isdigit()
numberone_string.istitle()
numberone_string.isupper()
numberone_string.islower()
numberone_string.isspace()
numberone_string.endswith('d')
numberone_string.startswith('H')
```

```python
# 检查是否所有字符都是数字
# 检查是否所有字符都是字母
# 测试字符串是否包含数字
# 测试字符串是否为标题
# 测试字符串是否包含大写字母
# 测试字符串是否包含小写字母
# 测试字符串是否包含空格
# 测试字符串是否以 'd' 结尾
# 测试字符串是否以 'H' 开头
```

要查看返回值是什么，将其打印出来。

```python
numberone_string = "Hello World"

print(numberone_string.isalnum())      # False
print(numberone_string.isalpha())      # False
print(numberone_string.isdigit())      # False
print(numberone_string.istitle())      # True
print(numberone_string.isupper())      # False
print(numberone_string.islower())      # False
print(numberone_string.isspace())      # False
print(numberone_string.endswith('d'))  # True
print(numberone_string.startswith('H')) # True
```

## 逻辑运算符布尔

这些值倾向于响应逻辑运算符 `and` 和 `or`。

```python
>>> True and False
False
>>> True and True
True
>>> False and True
False
>>> False or True
True
>>> False or False
False
```

记住，内置的布尔类型只有两个可能的答案：True 或 False。现在你已经了解更多关于布尔值以及如何使用它们，让我们聊聊 Python 运算符。

# 第八章 - Python 运算符

有几种不同的运算符。有算术运算符、比较运算符和逻辑运算符。让我们更详细地查看每一个。

## 算术运算符



# Python 运算符与基础语法

## 算术运算符

Python 有模运算 `-`、`+`、`/`、`%` 和 `**` 运算符。假设变量 `a` 的值为十，变量 `b` 的值为二十。因此：

| 运算符 | 表达式 | 结果 | 说明 |
| :--- | :--- | :--- | :--- |
| `+` | `a + b` | `30` | 加法 |
| `-` | `a - b` | `-10` | 减法 |
| `*` | `a * b` | `200` | 乘法 |
| `/` | `b / a` | `2` | 除法 |
| `%` | `b % a` | `0` | 取模（求余） |
| `**` | `a ** b` | `10^20` | 幂运算 |
| `//` | `9 // 2` | `4` | 整除（向下取整） |

## 比较运算符

普通的比较运算符如 `==`、`<`、`>=` 以及其他用于各种类型的值。字符串、数字、映射和序列都可以进行比较。下面列出比较运算符列表：

- `<` : 小于
- `==` : 等于
- `<=` : 小于或等于
- `>=` : 大于等于
- `>` : 大于
- `<>` : 不等于（Python 2 风格，Python 3 建议使用 `!=`）
- `!=` : 不等于

## 逻辑运算符

逻辑运算符在用于决策结构时也会返回布尔值。有三个逻辑运算符：`or`（或）、`and`（与）和 `not`（非）。例如，`x > 0 and x < 10` 仅当 `x` 大于 0 且小于 10 时才为真。

运算符描述：

- `and` : 逻辑与
- `or` : 逻辑或
- `not` : 逻辑非

---

# 第九章 - 在 Python 中使用数学

Python 语言拥有 Python 解释器，这是一个被称为 IDLE 的简单开发环境、工具、库。在几乎所有系统上都预装了 Python 解释器，包括 Linux 和 Mac。在解释器中输入以下内容：

## 计数

要对面积进行测试，将其打印出来：

```python
>>> 2 * 2
4
>>> 4 * 2
8
>>> 10 / 2
5
```

### 使用变量计数

要使用变量进行计数，尝试以下代码：

```python
>>> length = 2
>>> width = 4
>>> area = length * width
>>> area
8
```

### 计数器

计数器在编程中用于每次运行时增加或减少值。以下是代码：

```python
>>> i = 0
>>> i = i + 1
>>> i
1
```

### 使用 while 循环计数

这是一个使用 while 循环计数的示例。

```python
>>> i = 0
>>> while i < 5:
...     print(i)
...     i = i + 1
...
0
1
2
3
4
```

### 乘法表

要制作乘法表，使用以下内容：

```python
>>> start = 1
>>> max_val = 10
>>> while start <= max_val:
...     print(start * start)
...     start += 1
...
1
4
9
16
25
36
49
64
81
100
```

输出将是：

- 1
- 4
- 9
- 16
- 25
- 36
- 49
- 64
- 81
- 100

---

# 第十章 - 异常处理

在了解做什么之前，首先必须知道什么是异常。异常是在运行时发生的错误。

## 设置异常块

它是如何工作的？

错误处理通过在 `try` 块中使用并在 `except` 块中处理异常来实现。如果你的代码遇到错误，`try` 块执行将停止并转移到 `except` 块。

除了在 `try` 块之后使用 `except` 块，还可以使用 `finally` 块。无论是否发生异常，此块中的代码都会执行。让我们来看一些代码，看看不在程序中使用错误处理会发生什么。

### 代码示例

此程序将要求用户输入一个 1 到 10 之间的数字，然后打印该数字。

```python
number = int(raw_input("Enter number between 1-10"))
print "you entered number", number
```

只要用户输入数字，此程序就可以正常工作，但如果他们输入其他内容，比如字符串会怎样？

```text
Enter a number between 1-10
helo
```

你可以看到当输入字符串时程序会抛出错误。

```text
Traceback (most recent call last):
  File "enter_number.py", line 1, in <module>
    number = int(raw_input("Enter number between 1-10"))
ValueError: invalid literal for int() with base 10: 'hello'
```

`ValueError` 是异常的一种类型。现在让我们看看如何利用异常处理来修复上述程序。

```python
import sys

try:
    number = int(raw_input("Enter a number between 1-10 \n"))
except ValueError:
    print "Only numbers are accepted."
    sys.exit()

print "you entered number \n", number
```

如果你现在启动程序并输入字符串而不是数字，你可以看到你会得到不同的响应。现在，让我们运行程序以确保它正常工作。响应应当是：

```text
输入 1-10 之间的数字
hello
只接受数字。
```

### Try ... Except ... Else 子句

在 `try...except` 语句中的 `else` 子句必须跟在所有 `except` 子句之后，用于在 `try` 子句没有引发异常时必须执行的代码。例如：

```python
try:
    data = something_that_might_go_wrong()
except IOError:
    handling_the_exception_handling()
else:
    trying_a_different_exception_handling()
```

`else` 子句中的异常不会被前面的 `except` 子句处理。请确保 `else` 子句在 `finally` 代码块之前运行。

### Try ... Finally 子句

`finally` 子句是一个可选子句。它用于定义在任何情况下都必须执行的清理操作。例如：

```python
try:
    raise KeyboardInterrupt
finally:
    print('Goodbye!')
```

输出：
```text
Goodbye!
KeyboardInterrupt
```

无论是否发生异常，在离开 `try` 语句之前都会执行 `finally` 子句。

记住，如果你没有在 `except` 语句上指定异常类型，它将捕获所有异常。这不是好事，因为这意味着程序将忽略任何意外错误，以及 `except` 块能够处理的错误。

现在你已经了解了 Python 中的异常，让我们在下一章查看字符串的内置方法。

---

# 第十一章 - 字符串内置方法

本章将包含一个列表，列出你可以对每个字符串使用的内置方法。让我们先创建一个值为 `'Hello'` 的字符串。

它看起来很像这样：

```python
string = 'Hello'
```

为了操作此字符串，请查看以下某些内置方法及其解释。

- `string.upper()`
  - 这将字符串中的所有字母转换为大写，所以如果字符串是 `'hello jane'`，它的输出将是 `'HELLO JANE'`。

- `string.lower()`
  - 这将你字符串中的所有字母转换为小写，所以如果字符串是 `'Hello Jane'`，在程序中它将是 `'hello jane'`。

- `string.capitalize()`
  - 这将仅大写第一个字母。因此，如果字符串是 `'hello jane'`，在程序中它将是 `'Hello jane'`。

- `string.title()`
  - 这将大写每个单词的第一个字母。所以如果程序中的字符串是 `'hello jane'`，它将是 `'Hello Jane'`。

- `string.swapcase()`
  - 此方法将所有大写字母转换为小写，反之亦然，所以以下字符串 `'hello jane'` 在程序中将是 `'HELLO JANE'`。

- `string.strip()`
  - 此方法将移除字符串首尾的空白字符。所以如果字符串是 `' Hello Jane '`，在程序中它将是 `'Hello Jane'`。

- `string.lstrip()`
  - 此方法移除左侧所有的空白字符。因此，如果字符串是 `' Hello Jane '`（hello 前有空格，Jane 后有一个），代码将提取出 `'Hello Jane '`。

- `string.rstrip()`
  - 此方法移除右侧所有的空白字符。因此，如果同一行代码读取 `'Hello Jane '`（Jane 后面有一个空格），Jane 后面的空格将被先移除，变为 `'Hello Jane'`。

- `string.split()`
  - 此命令将按空白字符分割字符串。所以如果代码读取 `'Hello Jane'`，它将被分成 `['Hello', 'Jane']`。

- `string.split(',')`
  - 这意味着代码将通过逗号分割字符串，所以以下字符串 `'Hello, Jane'` 的输出为 `['Hello', ' Jane']`。

- `string.count('l')`
  - 此方法将统计 `'l'` 或你选择放入字符串的任何其他字符在字符串中出现的次数。如果输入是 `'Hello Jane'`，程序会告诉你 `2`。

- `string.find('Ja')`
  - 此方法将在字符串中查找子串 `'Ja'` 并返回其索引。

- `string.index('Ja')`
  - 这将在字符串中找到子串 `'Ja'` 的索引，若不存在则抛出异常。

- `":".join(string)`
  - 这将在每个字符之间添加一个冒号 `:`。所以 `'Hello'` 的输出结果为 `'H:e:l:l:o'`。

- `len(string)`
  - 这将找到字符串的字符长度，所以如果字符串是 `'Hello Jane'`，程序会返回 `10`（含空格）。

---

# 第十二章 – 列表与字典

列表用方括号 `[]` 创建，括号之间的元素就是程序将使用的内容。列表中的元素不需要是相同类型，因此，你可以在一组括号中包含字母、数字和字符串。

让我们来看一个示例。

```python
myList = [1, 2, 3, 5, 8, 2]
i = 0
while i < len(myList):
    print(myList[i])
    i += 1
```

字典用花括号 `{}` 创建，包含键值对。以下示例演示了字典的常用操作：

### 遍历字典

```python
released = {"iphone 3G": 2008, "iphone 4": 2010, "iphone 5": 2012}

for item in released:
    if "iphone 5" in released:
        print("Key found")
        break
    else:
        print("No keys found")
```

### 获取特定键的值

```python
print(released.get("iphone 3G", "name"))
```

### 使用 for 循环打印所有的键

```python
print("*" * 10)
print("iphone releases so far:")
print("*" * 10)
for release in released:
    print(release)
```

### 打印所有的键和值

```python
for key, val in released.items():
    print(key, ":", val)
```

### 仅获取字典中的键

```python
phones = released.keys()
print(phones)
```

### 打印所有值

```python
print("Values:")
for key in released:
    release = released[key]
    print(release)
```

### 对字典进行排序

```python
for key, value in sorted(released.items()):
    print(key, value)
```

这就是在 Python 中使用列表和字典的基本方法。

---

# 结论

使用 Python 代码可以做很多事情。许多开发者会用它来完成从简单的库存排序到像制作视频游戏这样复杂任务的各种工作。

Python 的重要的一点是，全球范围内都有被称为 PUGs（Python 用户小组）的用户群体，他们在世界各大洲举办大型会议，以便 Python 用户之间能够相互交流。许多会议还允许儿童参加，他们将学习如何在会议赠给他们的新树莓派电脑上使用 Python。

总的来说，Python 语言周围的社区非常积极、向上。他们是一群想要用自己的知识让世界变得更好的人。所以，永远不要害怕联系论坛和讨论组，去探索如何编写你需要的代码。

感谢阅读。希望你喜欢。请留下你诚恳的反馈。
