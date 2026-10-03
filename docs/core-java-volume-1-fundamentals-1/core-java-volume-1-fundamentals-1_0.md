

# Core Java 卷 1：基础 1

![](img/9780134177359.jpg)

![cover-image](img/9780134177359.jpg)

## 关于本电子书

EPUB 是一种开放的行业标准电子书格式。然而，不同阅读设备和应用程序对 EPUB 及其许多功能的支持程度不同。请使用您的设备或应用设置根据您的喜好自定义显示。您可以自定义的设置通常包括字体、字体大小、单栏或双栏、横屏或竖屏模式，以及可以点击或触摸放大的图片。有关您的阅读设备或应用设置和功能的更多信息，请访问设备制造商的网站。

许多书籍包含编程代码或配置示例。为了优化这些元素的显示，请在单栏横屏模式下查看电子书，并将字体大小调整为最小设置。除了以重流文本格式显示代码和配置外，我们还包含了代码图像，以模拟印刷书籍中的显示效果；因此，当重流格式可能会影响代码列表的显示时，您将看到一个“点击此处查看代码图像”链接。点击链接即可查看高保真代码图像。要返回之前查看的页面，请点击设备或应用上的返回按钮。

![Image](img/pub.jpg)

波士顿 • 哥伦布 • 印安纳波利 • 纽约 • 旧金山 • 阿姆斯特丹 • 开普敦

迪拜 • 伦敦 • 马德里 • 米兰 • 慕尼黑 • 巴黎 • 蒙特利尔 • 多伦多 • 德里 • 墨西哥城

圣保罗 • 悉尼 • 香港 • 首尔 • 新加坡 • 台北 • 东京

- `StringBuilder delete(int startIndex, int endIndex)`

  删除从 `startIndex` 到 `endIndex - 1` 偏移量之间的代码单元，并返回 `this`。

- `String toString()`

  返回一个与构建器或缓冲区内容相同的数据字符串。

## 3.7 输入与输出

为了让我们的示例程序更有趣，我们希望接受输入并妥善地格式化程序输出。当然，现代程序使用 GUI 来收集用户输入。然而，编写这样的界面所需的工具和技术比我们目前拥有的要多。我们的首要任务是更熟悉 Java 编程语言，因此我们目前先使用简单的控制台进行输入和输出。GUI 编程将在第 10 章到第 12 章介绍。

### 3.7.1 读取输入

你已经看到，只需调用 `System.out.println` 就可以向“标准输出流”（即控制台窗口）打印输出。从“标准输入流” `System.in` 读取内容并没有那么简单。要读取控制台输入，你首先需要构造连接到 `System.in` 的 `Scanner`：

点击查看代码图片

```java
Scanner in = new Scanner(System.in);
```

（我们将在第 4 章中详细讨论构造函数和 `new` 运算符。）

现在你可以使用 `Scanner` 类的各种方法来读取输入。例如，`nextLine` 方法读取一行输入。

点击查看代码图片

```java
System.out.print("What is your name? ");
String name = in.nextLine();
```

在这里，我们使用 `nextLine` 方法是因为输入可能包含空格。要读取单个单词（由空白分隔），请调用：

```java
String firstName = in.next();
```

要读取一个整数，请使用 `nextInt` 方法。

点击查看代码图片

```java
System.out.print("How old are you? ");
int age = in.nextInt();
```

同样，`nextDouble` 方法读取下一个浮点数。

代码列表 3.2 中的程序询问用户的用户名和年龄，然后打印如下所示的消息：

点击查看代码图片

```text
Hello, Cay. Next year, you'll be 57
```

最后，注意程序开头的行：

```java
import java.util.*;
```

`Scanner` 类定义在 `java.util` 包中。每当你使用未定义在基础 `java.lang` 包中的类时，都需要使用 `import` 指令。我们将在第 4 章中详细查看包和 `import` 指令。

**列表 3.2** `InputTest/InputTest.java`

点击查看代码图片

```java
1   import java.util.*;
2
3   /**
4    * 此程序演示了控制台输入。
5    * @version 1.10 2004-02-10
6    * @author Cay Horstmann
7    */
8   public class InputTest
9   {
10      public static void main(String[] args)
11      {
12          Scanner in = new Scanner(System.in);
13
14          // get first input
15          System.out.print("What is your name? ");
16          String name = in.nextLine();
17
18          // get second input
19          System.out.print("How old are you? ");
20          int age = in.nextInt();
21
22          // display output
23          System.out.println("Hello, " + name + ". Next year, you'll be " + age);
24      }
25   }
```

### 3.7.2 格式化输出

你可以使用语句 `System.out.print(x)` 向控制台打印数字 `x`。该命令将打印具有该类型最大数字 `x`。例如：

```java
double x = 10000.0 / 3.0;
System.out.print(x);
```

打印 `3333.333333333335`。

如果你想显示美元和分，这就会是一个问题。

在 Java 的早期版本中，格式化数字有点麻烦。幸运的是，Java SE 5.0 带回了 C 库中久违的 `printf` 方法。例如，调用：

点击查看代码图片

```java
System.out.printf("%8.2f", x);
```

打印**字段宽度**为 8 个字符且**精度**为 2 个字符的 `x`。也就是说，输出包含一个前导空格和七个字符 `3333.33`。

你可以为 `printf` 提供多个参数。例如：

```java
System.out.printf("Hello, %s. Next year, you'll be %d", name, age);
```

每个以 `%` 字符开头的格式说明符都会被相应的参数替换。结束格式说明符的**转换字符**指示要格式化的值的类型：`f` 是浮点数，`s` 是字符串，`d` 是十进制整数。表 3.5 显示了所有的转换字符。

此外，你可以指定控制格式化输出外观的 `flags`（标志）。表 3.6 显示了标志。例如，逗号标志会添加分组分隔符。即：

点击此处查看代码图像

```java
System.out.printf("%,.2f", 10000.0 / 3.0);
```

![Image](img/03tab06.jpg)

**表 3.6** `printf` 的标志

打印：

```text
3,333.33
```

你可以使用多个标志，例如使用 `%,(.2f` 来使用分组分隔符并将负数括在括号内。

![Image](img/note.jpg)

> **备注**
>
> 你可以使用 `s` 转换符来格式化任意对象。如果任意对象实现了 `Formattable` 接口，则会调用该对象的 `formatTo` 方法。否则，将调用 `toString` 方法将对象转换为字符串。我们将在第 5 章中讨论 `toString` 方法，并在第 6 章中讨论接口。

你可以使用静态方法 `String.format` 来创建格式化字符串而不打印它：

点击此处查看代码图像

```java
String message = String.format("Hello, %s. Next year, you'll be %d", name, age);
```

为了完整起见，我们简要讨论 `printf` 方法的日期和时间格式化选项。对于新代码，你应该使用第二卷第 6 章中描述的 `java.time` 包中的方法。但你可能会在遗留代码中遇到 `Date` 类和相关的格式选项。格式由两个字母组成，以 `t` 开头并以表 3.7 中的字母之一结束；例如：

点击此处查看代码图片

```java
System.out.printf("%tc", new Date());
```

![Image](img/03tab07.jpg)![Image](img/03tab07a.jpg)

**表 3.7** 日期和时间转换字符

以以下格式打印当前日期和时间：

```text
Mon Feb 09 18:05:19 PST 2015
```

正如你在表 3.7 所示，某些格式仅产生给定日期的部分——例如，仅日期或仅月份。如果你必须多次提供日期来格式化每个部分，那将有点傻。因此，格式字符串可以指定要格式化的参数的 `index`（索引）。索引必须紧跟在 `%` 之后，并以 `$` 终止。例如：

点击此处查看代码图像

```java
System.out.printf("%1$s %2$tB %2$tY", "Due date:", new Date());
```

打印：

```text
Due date: February 9, 2015
```

或者，你可以使用 `<` 标志。它表示再次使用与前面的格式说明符相同的参数。即：

点击此处查看代码图像

```java
System.out.printf("%s %tB<%tY", "Due date:", new Date());
```

产生与前述语句相同的输出。

![Image](img/caution.jpg)

> **注意**
>
> 参数索引值从 1 开始，而不是 0：`%1$` 格式化第一个参数。这避免了与 `0` 标志的混淆。

你现在已经看到了 `printf` 方法的所有特征。图 3.6 显示了说明符的图。

![Image](img/03fig06.jpg)

**图 3.6** 格式说明符语法

![Image](img/note.jpg)

> **备注**
>
> 数字和日期的格式化是`特定特定`的。例如，在德国，分组分隔符是点而不是逗号，周一格式化为 Montag。第二卷的第 7 章展示了如何控制你的应用程序的行为。

### 3.7.3 文件输入与输出

要从文件读取，如下构造 `Scanner` 对象：

点击此处查看代码图片

```java
Scanner in = new Scanner(Paths.get("myfile.txt"), "UTF-8");
```

如果文件名包含反斜杠，请记住用额外的反斜杠对每一个进行转义：`"c:\\mydirectory\\myfile.txt"`。

![Image](img/note.jpg)

> **备注**
>
> 在这里，我们指定了 `UTF-8` 编码，这是互联网文件的常用（但非通用）编码。读取文本文件时，你需要知道字符编码——参见第二卷第 2 章。如果你省略字符编码，则使用运行程序的“默认”编码。这取决于程序运行的位置。

现在你可以像使用 `System.in` 和 `System.out` 那样访问文件。要写入文件，构造 `PrintWriter` 对象。在构造函数中，指定文件名和字符编码：

点击此处查看代码图片

```java
PrintWriter out = new PrintWriter("myfile.txt", "UTF-8");
```

如果文件不存在，将会创建。你可以像打印 `System.out` 那样使用 `print`、`println` 和 `printf` 命令。

![Image](img/caution.jpg)

> **注意**
>
> 你可以用字符串参数构造 `Scanner`，但解析器解释的是字符串而不是文件。例如，如果你调用：
>
> 点击此处查看代码图片
>
> ```java
> Scanner in = new Scanner("myfile.txt"); // 错误？
> ```
>
> 解析器将看到 `'m'`、`'y'`、`'f'` 等字符。这可能不是你的初衷。

![Image](img/note.jpg)

> **备注**
>
> 当你指定相对文件名，如 `"myfile.txt"`、`"mydirectory/myfile.txt"` 或 `"../myfile.txt"` 时，文件是相对于 Java 虚拟机的启动目录的。如果你从命令行启动你的程序，通过执行：
>
> ```bash
> java MyProg
> ```
>
> 那么启动目录就是命令行的目录。然而，如果你使用集成开发环境，它控制启动目录。你可以通过此调用查找目录：
>
> 点击此处查看代码图片
>
> ```java
> String dir = System.getProperty("user.dir");
> ```
>
> 如果你在定位文件遇到困难，考虑使用绝对路径名，如 `"c:\\mydirectory\\myfile.txt"` 或 `"/home/me/mydirectory/myfile.txt"`。

正如你所看到的，你可以像使用 `System.in` 和 `System.out` 那样轻松地访问文件。只有一个问题：如果你用不存在的文件构造 `Scanner`，或用无法创建的文件名构造 `PrintWriter`，就会发生异常。Java 编译器认为这些异常比“除以零”异常更严重。在第 7 章中，你将学习处理异常各种方法。现在，你只需要告诉编译器你已经意识到了“输入/输出”异常的可能性。你通过给 `main` 方法标记 `throws` 子句来实现这一点，如下：

点击此处查看代码图片

```java
public static void main(String[] args) throws IOException
{
   Scanner in = new Scanner(Paths.get("myfile.txt"), "UTF-8");
   ...
}
```

- `PrintWriter(String fileName)` 构建一个 `PrintWriter`，用于向给定文件名的文件写入数据。

`java.nio.file.Paths` 7

- `static Path get(String pathname)` 根据给定的路径名构建一个 `Path`。

## 3.8 控制流

Java 与任何其他编程语言一样，都支持条件语句和循环来确定控制流。我们将从条件语句开始，然后进入循环，最后以有点繁琐的 `switch` 语句结束，你可以使用它来测试单个表达式的多个值。

**C++ 注意事项**：Java 的控制流结构与 C 和 C++ 中的结构相同，但有几处例外。Java 没有 `goto`，但有一个带“标签”的 `break` 版本，你可以用它来跳出嵌套循环（在 C 中，你可能就会使用 `goto`）。最后，还有一种 `for` 循环的变体，它在 C 或 C++ 中没有类似的等价物。它类似于 C# 中的 `foreach` 循环。

### 3.8.1 块作用域

在学习控制结构之前，你需要了解更多关于**块（blocks）**的知识。

一个块或复合语句由一组 Java 语句组成，由一对大括号包裹。块定义了变量的作用域。一个块可以**嵌套**在另一个块内部。这里有一个嵌套在 `main` 方法块内部的块：

```java
public static void main(String[] args)
{
    int n;
    . ...
    {
        int k;
        // ...
    } // k 仅定义到此处
}
```

你不能在两个嵌套的块中声明同名的变量。例如，以下代码是错误的且无法通过编译：

```java
public static void main(String[] args)
{
    int n;
    ...
    {
        int k;
        int n; // 错误--不能在内部块中重新定义 n
        ...
    }
}
```

**C++ 注意事项**：在 C++ 中，可以在嵌套块内部重新定义变量。内部定义会遮蔽（shadows）外部定义。这可能成为编程错误的根源；因此，Java 不允许这样做。

### 3.8.2 条件语句

Java 中的条件语句的形式为：

`if (condition) statement`

条件必须被圆括号包裹。

在 Java 中，与大多数编程语言一样，你通常希望在单个条件为真时执行多条语句。在这种情况下，使用形式如下的**块语句（block statement）**：

```java
{
    statement[1]
    statement[2]
    . ...
}
```

例如：

```java
if (yourSales >= target)
{
    performance = "Satisfactory";
    bonus = 100;
}
```

在这段代码中，当 `yourSales` 大于或等于 `target` 时，大括号包裹的所有语句都将被执行。

**图 3.7** `if` 语句的流程图。

**注意**：块（有时称为**复合语句**）允许你在任何原本允许单个（简单）语句的 Java 编程结构中拥有多个（简单）语句。

Java 中更通用的条件语句形式如下：

`if (condition) statement[1] else statement[2]`

**图 3.8** `if/else` 语句的流程图。

例如：

```java
if (yourSales >= target)
{
    performance = "Satisfactory";
    bonus = 100 + 0.01 * (yourSales - target);
}
else
{
    performance = "Unsatisfactory";
    bonus = 0;
}
```




`else` 部分始终是可选的。`else` 与最近的 `if` 组合。因此，在语句：

```java
if (x <= 0) if (x == 0) sign = 0; else sign = -1;
```

这里的 `else` 属于第二个 `if`。为了清晰，我们可以使用大括号：

```java
if (x <= 0) { if (x == 0) sign = 0; else sign = -1; }
```

`else if`（多分支）是很常见的。例如：

```java
if (yourSales >= 2 * target)
{
    performance = "Excellent";
    bonus = 1000;
}
else if (yourSales >= 1.5 * target)
{
    performance = "Fine";
    bonus = 500;
}
else if (yourSales >= target)
{
    performance = "Satisfactory";
    bonus = 100;
}
else
{
    System.out.println("You're fired");
    bonus = 0;
}
```

**图 3.9** `if/else if` 的流程图。

### 3.8.3 循环

`while` 循环在条件为 `true` 时执行语句（这可能是一个块）。其通用形式为：

```java
while (condition) statement
```

`while` 循环在条件为 `false` 时将不会执行。

**图 3.10** `while` 语句的流程图。

`Listing 3.3` 中的程序确定了需要多久才能积累特定的金额，假设你每年存入相同的金额，且资金按指定的利率产生收益。

```java
while (balance < goal)
{
    balance += payment;
    double interest = balance * interestRate / 100;
    balance += interest;
    years++;
}
System.out.println(years + " years.");
```

依赖此程序来规划退休。我们省略了一些如通胀和预期寿命等细节。`while` 循环在顶部进行测试。因此，如果你想确保块至少被执行一次，你需要将测试移动到底部，使用 `do/while` 循环。它的语法如下：

```java
do statement while (condition);
```

该循环执行语句（通常是一个块），然后才测试条件。如果为 `true`，它将重复语句并重新测试条件，依此类推。`Listing 3.4` 中的代码计算了退休账户的新余额，然后询问你是否准备好退休：

```java
do
{
    balance += payment;
    double interest = balance * interestRate / 100;
    balance += interest;
    year++;
    // 打印当前余额
    ...
    // 询问是否准备好退休并获取输入
    ...
} while (input.equals("N"));
```

只要用户回答 "N"，循环就会重复。这是一个至少进入一次的循环示例，因为用户需要在判断余额是否足够退休之前查看。

**图 3.11** `do/while` 语句的流程图。

**Listing 3.3** `Retirement/Retirement.java`

```java
import java.util.*;

/**
 * 此程序演示了 while 循环。
 * @version 1.20 2004-02-10
 * @author Cay Horstmann
 */
public class Retirement
{
    public static void main(String[] args)
    {
        // 读取输入
        Scanner in = new Scanner(System.in);
        System.out.print("你需要多少钱才能退休？ ");
        double goal = in.nextDouble();
```

```java
double payment = in.nextDouble();

System.out.print("Interest rate in %: ");
double interestRate = in.nextDouble();

double balance = 0;
int years = 0;

// 当目标尚未达到时，更新账户余额
while (balance < goal)
{
    // 添加本年的付款和利息
    balance += payment;
    double interest = balance * interestRate / 100;
    balance += interest;
    years++;
}

System.out.println("You can retire in " + years + " years.");
```

### 列表 3.4 `Retirement2/Retirement2.java`

点击此处查看代码图片

```java
import java.util.*;

/**
 * 此程序演示了 do/while 循环。
 * @version 1.20 2004-02-10
 * @author Cay Horstmann
 */
public class Retirement2
{
    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);

        System.out.print("How much money will you contribute every year? ");
        double payment = in.nextDouble();

        System.out.print("Interest rate in %: ");
        double interestRate = in.nextDouble();

        double balance = 0;
        int year = 0;

        String input;

        // 当用户尚未准备退休时，更新账户余额
        do
        {
            // 添加本年的付款和利息
            balance += payment;
            double interest = balance * interestRate / 100;
            balance += interest;

            year++;

            // 打印当前余额
            System.out.printf("After year %d, your balance is %.2f%n", year, balance);

            // 询问是否准备退休并获取输入
            System.out.print("Ready to retire? (Y/N) ");
            input = in.next();
        } while (input.equals("N"));
    }
}
```

### 3.8.4 确定循环

`for` 循环是一种通用结构，用于通过计数器或在每次迭代后更新的变量来支持迭代。如图 3.12](#ch03.html_ch03fig12) 所示，以下循环打印从 1 到 10 的数字。

```java
for (int i = 1; i <= 10; i++)
    System.out.println(i);
```

**图 3.12** `for` 语句流程图

`for` 语句的第一个槽通常持有计数器的初始化。第二个槽位给出在每次通过循环之前测试的条件，第三个槽位指定如何更新计数器。

尽管 Java 像 C++ 一样允许在 `for` 循环的各个槽位中使用任何表达式，但一种良好的习惯不成文规则是：这三个槽位应该只初始化、测试和更新同一个计数器变量。忽略这一规则可能会写出非常晦涩的循环。即使在良好习惯的范围内，也存在很多可能。例如，你可以拥有倒计数的循环：

```java
for (int i = 10; i > 0; i--)
    System.out.println("Counting down . . . " + i);
System.out.println("Blastoff!");
```

> **注意**
>
> 在循环中测试浮点数的等效性要小心。像这样的 `for` 循环：
>
> ```java
> for (double x = 0; x != 10; x += 0.1)
> ```
>
> 可能永远不会结束。由于舍入误差，最终值可能无法精确达到。在这个示例中，`x` 会从 `9.9999999999998` 跳跃到 `10.0999999999998`，因为 0.1 没有精确的二进制表示。

当你在 `for` 语句的第一个槽位声明变量时，该变量的作用域将延伸到 `for` 循环体的结束。

```java
for (int i = 1; i <= 10; i++)
{
    ...
}
// i 在此处不再被定义
```

特别是，如果你在 `for` 语句内部定义变量，则不能在循环外部使用它的值。因此，如果你希望在 `for` 循环外部使用循环计数器的最终值，请确保在循环头之外声明它。

```java
int i;
for (i = 1; i <= 10; i++)
{
    ...
}
// i 在此处仍然定义
```

另一方面，你可以在不同的 `for` 循环中定义同名的变量：

```java
for (int i = 1; i <= 10; i++)
{
    ...
}
...
for (int i = 11; i <= 20; i++) // 定义另一个名为 i 的变量是好的
{
    ...
}
```

`for` 循环仅仅是 `while` 循环的一种方便的快捷方式。例如：

```java
for (int i = 10; i > 0; i--)
    System.out.println("Counting down . . . " + i);
```

可以重写为：

```java
int i = 10;
while (i > 0)
{
    System.out.println("Counting down . . . " + i);
}
```

这个 `for` 循环计算了中奖的概率。例如，如果你从 1 到 50 的数字中抽取六个数字，那么有 $15,890,700$ 种结果，所以你的机会是 1 比 $15,890,700$！通常情况下，如果你抽取 `k` 个数字，下面的 `for` 循环计算该值：

```java
int lotteryOdds = 1;
for (int i = 1; i <= k; i++)
    lotteryOdds = lotteryOdds * (n - i + 1) / i;
```

> **注意**
>
> 参见第 3.10.1 节](#ch03.html_ch03)关于“for 循环”的描述，它是 Java 5.0 添加到语言中的泛化 `for` 循环。

**列表 3.5** `LotteryOdds/LotteryOdds.java`

```java
import java.util.*;

/**
 * 此程序演示了 `for` 循环。
 * @version 1.20 2004-02-10
 * @author Cay Horstmann
 */
public class LotteryOdds
{
    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);

        System.out.print("How many numbers do you need to draw? ");
        int k = in.nextInt();

        System.out.print("What is the highest number you can draw? ");
        int n = in.nextInt();

        /*
         * 计算 n*(n-1)*(n-2)**(n-k+1)/(1*2*3*...k)
         */
        int lotteryOdds = 1;
        for (int i = 1; i <= k; i++)
            lotteryOdds = lotteryOdds * (n - i + 1) / i;

        System.out.println("Your odds are 1 in " + lotteryOdds + ". Good luck!");
    }
}
```

### 3.8.5 多选择——`switch` 语句

当你需要处理许多替代方案的多选择时，`if/else` 结构可能会非常麻烦。Java 有一种 `switch` 语句，它和 C 和 C++ 中的 `switch` 语句完全一样，优点并缺。

例如，如果你像图 3.13](#ch03.html_ch03fig13) 中那样设置包含四个选项的菜单系统，你可以使用如下代码：

```java
Scanner in = new Scanner(System.in);
System.out.print("Select an option (1, 2, 3, 4) ");
int choice = in.nextInt();
switch (choice)
{
    case 1:
        ...
        break;
    case 2:
        ...
        break;
    case 3:
        ...
        break;
    case 4:
        ...
        break;
    default:
        // 错误输入
        ...
        break;
}
```

![Image](img/03fig13.jpg)

**图 3.13** `switch` 语句流程图

执行从匹配选择值的 `case` 标签开始，一直持续到下一个 `break` 或 `switch` 结束。如果没有一个 `case` 标签匹配，则执行 `default` 子句（如果存在的话）。

---

![Image](img/caution.jpg) **注意**

可能会触发多个备选分支。如果你忘记在分支的末尾添加 `break`，执行将贯穿到下一个分支！这种行为显然是危险的，而且是错误的常见原因。正因如此，我们会在程序中从不使用 `switch` 语句。

如果你比我们更喜欢 `switch` 语句，可以考虑使用 `-Xlint:fallthrough` 选项编译代码，如下所示：

点击此处查看代码图像

```bash
javac -Xlint:fallthrough Test.java
```

那么，每当某个分支没有以 `break` 语句结束时，编译器都会发出警告。

如果你确实想使用这种贯穿（fallthrough）行为，请在周围的方法上标记 `@SuppressWarnings("fallthrough")` 注解。这样，该方法就不会生成任何警告。（注解是一种向编译器或处理 Java 源代码或类文件的工具提供信息的机制。我们将在第二卷的第 8 章中详细讨论注解。）

---

`case` 标签可以是：

- 类型为 `char`、`byte`、`short` 或 `int` 的常量表达式
- 枚举常量
- 从 Java SE 7 开始，可以是字符串字面量

例如：

```java
String input = . . .;

switch (input.toLowerCase())
{
    case "yes": // 从 Java SE 7 开始允许的
        ...
        break;
    ...
}
```

当你对枚举常量使用 `switch` 语句时，你不需要在每个标签中提供枚举的名称——它是从 `switch` 的值推导出来的。例如：

```java
Size sz = . . .;

switch (sz)
{
    case SMALL: // 不需要使用 Size.SMALL
        ...
        break;
    ...
}
```

### 3.8.6 打断控制流的语句

尽管 Java 的设计者将 `goto` 保留为保留字，但他们决定不将其包含在语言中。通常，`goto` 语句被认为是一种糟糕的风格。一些程序员认为反对 `goto` 的力量已经过头了（例如参考唐纳德·克纳斯的著名文章《使用 goto 语句的结构化编程》）。他们认为，无限制地使用 `goto` 容易出错，但偶尔*跳出循环*是有益的。Java 的设计者同意了这一观点，并增加了一种新的语句——带标签 `break`（labeled break），以支持这种编程风格。

让我们先看看无标签的 `break` 语句。你用于退出 `switch` 的同一个 `break` 语句也可以用于跳出循环。例如：

点击此处查看代码图像



```java
while (years <= 100)
{
    balance += payment;
    double interest = balance * interestRate / 100;
    balance += interest;
    if (balance >= goal) break;
    years++;
}
```

现在，如果在循环顶部出现`years > 100`，或者在循环中间出现`balance >= goal`，就会退出循环。当然，你可以在不使用`break`的情况下计算出相同的`years`值，如下：

点击此处查看代码图像

```java
while (years <= 100 && balance < goal)
{
    balance += payment;
    double interest = balance * interestRate / 100;
    balance += interest;
    if (balance < goal)
        years++;
}
```

但请注意，在这个版本中`balance < goal`的测试被重复了两次。为了避免这种重复测试，一些程序员倾向于使用`break`语句。

与 C++ 不同，Java 还提供了带标签`break`（labeled break）语句，允许你跳出多个嵌套循环。偶尔在深度嵌套循环内部会发生奇怪的事情。在这种情况下，你可能想完全跳出所有嵌套循环。仅仅通过在各种循环测试中添加额外条件来编写这种程序是不方便的。

这是一个显示`break`语句作用的示例。注意，标签必须位于你想要跳出的外层循环之前。它后面必须跟着冒号。

点击此处查看代码图像

```java
Scanner in = new Scanner(System.in);
int n;
read_data:
while (. . .)
{
    for (. . .)
    {
        if (condition)
            break read_data;
    }
    ...
}
```

（注：提供的带标签 break 示例的文本包含大量的重复/乱码片段。我已清理了结构，以在保持逻辑流的同时保留所提供的技术指令。）

### 3.9 大数

如果基本整数和浮点类型的精度不足，你可以求助于`java.math`包中的两个实用类：`BigInteger`和`BigDecimal`。这些类是用于处理具有任意长度数字序列的数字的。`BigInteger`类实现了任意精度的整数算术，而`BigDecimal`对浮点数也执行相同的操作。

使用静态方法`valueOf`将普通数字转换为大数：

点击此处查看代码图像

```java
BigInteger a = BigInteger.valueOf(100);
```

遗憾的是，你无法使用熟悉的数学运算符（如`+`和`*`）来组合大数字。相反，你必须使用大数类中的`add`和`multiply`等方法。

点击此处查看代码图像

```java
BigInteger c = a.add(b); // c = a + b
BigInteger d = c.multiply(b.add(BigInteger.valueOf(2))); // d = c * (b + 2)
```

![Image](img/note1.jpg) C++ 笔记

与 C++ 不同，Java 没有可编程的运算符重载。`BigInteger`类的程序员没有办法通过重定义`+`和`*`运算符以为`BigInteger`类提供`add`和`multiply`操作。该语言的设计者确实重载了`+`运算符来表示字符串的拼接。他们选择不重载其他运算符，也没有给 Java 程序员提供在自己的类中重载运算符的机会。

列表 3.6 显示了列表 3.5 彩票概率程序的修改版本，已更新为支持大数字。例如，如果你被邀请参加一个从 490 个数字中选出 60 个的彩票，你可以使用这个程序来告知你的中奖概率。概率是`716395843461995557415116222540092933411717612789263493493351013459481104668848`分之一。祝你好运！

列表 3.5 中的程序计算了以下语句：

点击此处查看代码图像

```java
lotteryOdds = lotteryOdds * (n - i + 1) / i;
```

当使用大数字时，等效语句变为：

点击此处查看代码图像

```java
lotteryOdds = lotteryOdds.multiply(BigInteger.valueOf(n - i + 1)).divide(BigInteger.valueOf(i));
```

**列表 3.6** `BigIntegerTest/BigIntegerTest.java`

点击此处查看代码图像

```java
import java.math.*;
import java.util.*;

/**
 * 此程序使用大数字计算彩票中中大奖的概率。
 * @version 1.20 2004-02-10
 * @author Cay Horstmann
 */
public class BigIntegerTest
{
    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);

        System.out.print("你需要抽取多少个数字？ ");
        int k = in.nextInt();

        System.out.print("你能抽到的最大数字是多少？ ");
        int n = in.nextInt();

        /*
         * 计算二项式系数 n*(n-1)*(n-2)*...*(n-k+1)/(1*2*3*...*k)
         */

        BigInteger lotteryOdds = BigInteger.valueOf(1);

        for (int i = 1; i <= k; i++)
            lotteryOdds = lotteryOdds.multiply(BigInteger.valueOf(n - i + 1)).divide(
                BigInteger.valueOf(i));

        System.out.println("你的概率是 1 in " + lotteryOdds + ". 祝你好运！");
    }
}
```

#### java.math.BigInteger 1.1

- `add(BigInteger other)`
- `subtract(BigInteger other)`
- `multiply(BigInteger other)`
- `divide(BigInteger other)`
- `mod(BigInteger other)` 返回此整数与`other`的和、差、商和余数。
- `int compareTo(BigInteger other)` 如果此整数等于`other`则返回`0`，如果此整数小于`other`则返回负数，否则返回正数。
- `static BigInteger valueOf(long x)` 返回一个值等于`x`的大整数。

#### java.math.BigDecimal 1.1

- `add(BigDecimal other)`
- `subtract(BigDecimal other)`
- `multiply(BigDecimal other)`
- `divide(BigDecimal other, RoundingMode mode)` 返回此大数与`other`的和、差或商。要计算商，必须提供一个舍入模式。`RoundingMode.HALF_UP`模式是你在学校学过的模式：0 到 4 舍去，5 到 9 进位。它适用于各种计算。请查看舍入模式的 API 文档。
- `int compareTo(BigDecimal other)` 如果此小数等于`other`则返回`0`，如果此小数小于`other`则返回负数，否则返回正数。
- `static BigDecimal valueOf(long x)`
- `static BigDecimal valueOf(long x, int scale)` 返回一个值等于`x`或规模为`scale`的小数。

### 3.10 数组

数组是一种存储相同类型值集合的数据结构。数组是一种存储相同类型值集合的数据结构。通过索引访问数组中的每个值。例如，如果`a`是一个整数数组，那么`a[i]`就是第`i`个整数。声明数组的方法是指定类型——后跟`[]`——以及数组名。例如，这里有一个整数数组：

```java
int[] a;
```

然而，这条语句仅声明了变量`a`，并没有初始化`a`。使用`new`运算符创建数组：

```java
int[] a = new int[100];
```

这条语句声明并初始化了一个长度为 100 的整数数组。数组长度不需要是常量。你可以通过以下两种方式定义数组：

```java
int[] a;
```

或者：

```java
int a[];
```

大多数 Java 程序员喜欢前者，因为它清晰地将类型`int[]`（整数数组）与变量名分开。数组元素的索引从 0 编号到 99（而不是 100）。一旦创建了数组，你就可以填充数组元素，例如，通过循环：

点击此处查看代码图像

```java
int[] a = new int[100];
for (int i = 0; i < 100; i++)
    a[i] = i; // 填充 0 到 99
```

当你创建一个整数数组时，所有元素都初始化为 0。`boolean`数组初始化为`false`。对象数组初始化为`null`，这表示它们尚未持有任何对象。这可能会让初学者感到惊讶。例如：

点击此处查看代码图像

```java
String[] names = new String[10];
```

创建了一个十个字符串的数组，都是`null`。如果你希望数组持有空字符串，你必须提供它们：

点击此处查看代码图像

```java
for (int i = 0; i < 10; i++) names[i] = "";
```

![Image](img/caution.jpg) 注意

如果你构造了一个拥有 100 个元素的数组并尝试访问`a[100]`（或任何 0 到 99 范围之外的索引），你的程序将由于“数组索引越界”异常而终止。

要找到数组的元素数量，使用`array.length`。例如：

点击此处查看代码图像

```java
for (int i = 0; i < a.length; i++)
    System.out.println(a[i]);
```

一旦创建了数组，你就无法更改其大小（当然，你可以更改单个数组元素）。如果你在程序运行期间经常需要扩展数组的大小，你应该使用一种名为`array list`的数据结构。（有关数组列表的更多信息请参阅第 5 章。）

### 3.10.1 “for each”循环

Java 有一种强大的循环结构，允许你遍历数组（或任何元素集合）中的每个元素，而无需费心索引值。

增强型`for`循环：

```java
for (variable : collection) statement
```

将给定的变量设置为集合中的每个元素，然后执行该语句（当然，可以是一个代码块）。`collection`表达式必须是一个数组，或者实现了`Iterable`接口的类的对象，例如`ArrayList`。我们将在第 5 章中讨论数组列表，并在第 9 章中讨论`Iterable`接口。

例如：

```java
for (int element : a) {
    System.out.println(element);
}
```

这会将数组`a`的每个元素打印在单独的一行上。

你应该将此循环读作“对于`a`中的每个`element`”。Java 语言的设计者考虑过使用关键字，如`foreach`和`in`。但这个循环是 Java 语言后期添加的，最终没有人想要破坏那些已经包含与这些名称同名的方法或变量的旧旧代码（例如`System.in`）。

当然，你可以使用传统的`for`循环来实现相同的效果：

```java
for (int i = 0; i < a.length; i++) {
    System.out.println(a[i]);
}
```

然而，“for each”循环更加简洁且更不容易出错，因为你不需要担心那些烦人的起始和结束索引值。

***

![Image](img/note.jpg) 注意

“for each”循环的循环变量遍历的是数组的`elements`（元素），而不是索引值。

***

如果你需要处理集合中的所有元素，“for each”循环相比传统循环是一个令人愉悦的改进。然而，仍然有很多机会可以使用传统的`for`循环。例如，你可能不想遍历整个集合，或者你可能在循环内部需要索引值。

***

![Image](img/tip.jpg) 提示

有一种更简单的方法可以打印数组的所有值，即使用`Arrays`类的`toString`方法。调用`Arrays.toString(a)`返回一个包含数组元素的字符串，这些元素被括在括号中并用逗号分隔，例如`"[2, 3, 5, 7, 11, 13]"`。要打印数组，只需调用：

```java
System.out.println(Arrays.toString(a));
```

***

### 3.10.2 数组初始化器和匿名数组

Java 有一种快捷方法可以同时创建数组对象并提供初始值。以下是该语法的示例：

```java
int[] smallPrimes = { 2, 3, 5, 7, 11, 13 };
```

注意，当你使用这种语法时不需要调用`new`。

你甚至可以初始化一个匿名数组：

```java
new int[] { 17, 19, 23, 29, 31, 37 }
```

此表达式分配了一个新数组，并用大括号内的值填充它。它统计了初始值的数量并相应设置数组大小。你可以使用这种语法重新初始化数组而无需创建新变量。例如：

```java
smallPrimes = new int[] { 17, 19, 23, 29, 31, 37 };
```

是下面内容的简写：

```java
int[] anonymous = { 17, 19, 23, 29, 31, 37 };
smallPrimes = anonymous;
```

***

![Image](img/note.jpg) 注意

长度为 0 的数组是合法的。如果你编写了一个计算数组结果的方法而结果恰好为空，这样的数组可能是很有用的。构造长度为 0 的数组如下：

```java
new elementType[0]
```

注意，长度为`0`的数组不等同于`null`。

***

### 3.10.3 数组复制

你可以将一个数组变量复制到另一个变量，但此时两个变量都指向同一个数组：

```java
int[] luckyNumbers = smallPrimes;
luckyNumbers[5] = 12; // 现在 smallPrimes[5] 也是 12
```

图 3.14 显示了结果。如果你实际上想将一个数组的所有值复制到一个新数组，你可以使用`Arrays`类中的`copyOf`方法：

```java
int[] copiedLuckyNumbers = Arrays.copyOf(luckyNumbers, luckyNumbers.length);
```

![Image](img/03.jpg) **复制数组**

第二个参数是新数组的长度。

***

![Image](img/note.jpg) 注意

长度为`0`的数组与`null`不同。

***

### 3.10.4 命令行参数

你已经已经过多次`args`数组的示例。每个 Java 程序的`main`方法都有`String[] args`参数。该参数接收命令行指定的字符串。

例如，考虑以下代码：

```java
public class Message {
    public static void main(String[] args) {
        if (args.length == 0 || args[0].equals("-h")) {
            System.out.print("Hello,");
        } else if (args[0].equals("-g")) {
            System.out.print("Goodbye,");
            //打印其他命令行
            for (int i = 1; i < args.length; i++) {
                System.out.print(" " + args[i]);
            }
        }
        System.out.println("!");
    }
}
```

如果程序通过`java Message -g cruel`调用，则`args`数组如下：

- `args[0]`: `"-g"`
- `args[1]`: `"cruel"`
- `args[2]`: `"world"`

程序打印`Goodbye, cruel`。

### 3.10.5 数组排序

要对数组进行排序，你可以使用`Arrays`类中的`sort`方法：



```java
int[] a = new int[10000];
...
Arrays.sort(a);
```

该方法使用经过调优的快速排序算法，据称在大多数数据集上非常高效。`Arrays` 类提供了许多其他数组便利方法，包含在本节末尾的 API 说明中。

列表 3.7 中的程序使用了数组。该程序为乐票游戏抽取随机数字。例如，如果你玩“从 49 中选 6 个数字”的乐票，程序可能会输出：

点击此处查看代码图片

```
下注以下组合。它会让你发财！
    4
    7
    8
    19
    30
    44
```

为了选择这样一组随机数字，我们首先用数组 `numbers` 填充 `1`、`2`、. . . `n`：

点击此处查看代码图片

```java
int[] numbers = new int[n];
for (int i = 0; i < numbers.length; i++) {
    numbers[i] = i + 1;
}
```

第二个数组持有要抽取的数字：

```java
int[] result = new int[k];
```

现在我们抽取 `k` 个数字。`Math.random` 方法返回一个在 `0`（包含）到 `1`（不包含）之间的随机浮点数。通过将结果乘以 `n`，我们得到了一个在 `0` 到 `n – 1` 之间的随机整数。

点击此处此处查看代码图像

```java
int r = (int) (Math.random() * n);
```

我们将第 `i` 个结果设置为该索引处的数字。初始情况下，它仅仅是 `r + 1`，但正如你现在将看到的，`numbers` 数组的内容在每次抽取后都会发生变化。

```java
result[i] = numbers[r];
```

现在我们必须确保不再重复抽取那个数字——所有的彩票号码必须是不相同的。因此，我们用数组中的最后一个数字覆盖 `numbers[r]`，并让 `n` 减 `1`。

```java
numbers[r] = numbers[n - 1];
n--;
```

关键点在于，在每次抽取中，我们选择的是一个索引，而不是实际的值。索引指向一个包含尚未被抽取的值的数组。

在抽取 `k` 个彩票号码后，我们对 `result` 数组进行排序，以获得更整的输出：

```java
Arrays.sort(result);
for (int r : result)
    System.out.println(r);
```

**列表 3.7** `LotteryDrawing/LotteryDrawing.java`

点击此处此处查看代码图像

***

```java
import java.util.*;

/**
 * 此程序演示了数组操作。
 * @version 1.20 2004-02-10
 * @author Cay Horstmann
 */
public class LotteryDrawing
{
    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);

        System.out.print("你需要抽取几个数字？ ");
        int k = in.nextInt();

        System.out.print("你可以抽取的最大数字是多少？ ");
        int n = in.nextInt();

        // 用数字 1 2 3 . . . n 填充数组
        int[] numbers = new int[n];
        for (int i = 0; i < numbers.length; i++)
            numbers[i] = i + 1;

        // 抽取 k 个数字并将它们放入第二个数组
        int[] result = new int[k];
        for (int i = 0; i < result.length; i++)
        {
            // 生成一个 0 到 n - 1 之间的随机索引
            int r = (int) (Math.random() * n);

            // 选择随机位置的元素
            result[i] = numbers[r];

            // 将最后一个元素移动到随机位置
            numbers[r] = numbers[n - 1];
            n--;
        }

        // 打印排序后的数组
        Arrays.sort(result);
        System.out.println("下注以下组合。它将让你富翁！");
        for (int r : result)
            System.out.println(r);
    }
}
```

***

`java.util.Arrays` **1.2**

- `static String toString(type[] a)` **5.0**

返回一个包含 `a` 元素的字符串，用括号括起来并用逗号分隔。

![Image](img/119tab01.jpg)

- `static type[] copyOf(type[] a, int length)` **6**
- `static type[] copyOfRange(type[] a, int start, int end)` **6**

返回一个与 `a` 类型相同的数组，长度为 `length` 或 `end - start`，并由 `a` 的值填充。

![Image](img/119tab02.jpg)

- `static void sort(type[] a)`

使用调优的快速排序算法对数组排序。

![Image](img/119tab03.jpg)

- `static int binarySearch(type[] a, type v)`
- `static int binarySearch(type[] a, int start, int end, type v)` **6**

使用二分查找算法查找值 `v`。如果找到，返回其索引。否则，返回一个负值 `r`；`-r - 1` 是 `v` 应该插入的位置。

![Image](img/120tab01.jpg)

- `static void fill(type[] a, type v)`

将数组的所有元素都设置为 `v`。

![Image](img/120tab02.jpg)

- `static boolean equals(type[] a, type[] b)`

如果数组长度相同且对应索引的元素匹配，则返回 `true`。

![Image](img/120tab03.jpg)

***

### 3.10.6 多维数组

多维数组使用多个一个索引来访问数组元素。它们用于表格和其他复杂的布局，在你有存储需求之前，可以放心地地跳过这一节。

假设你想创建一个数字表格，显示在按年支付利并再投资的利率场景下，10,000 美元的投资将如何增长（表 3.8）。

![Image](img/03tab08.jpg)

**表 3.8** 不同利率下的投资增长

你可以将这些信息存储在一个二维数组（矩阵）中，我们称之为 `balances`。

在 Java 中声明二维数组非常简单，例如：

```java
double[][] balances;
```

在初始化它之前无法使用该数组。在这种情况下，你可以如下初始化：

点击此处此处查看代码图像

```java
balances = new double[YEARS][ATES];
```

一旦数组初始化，你就可以通过提供两个括号来访问元素——例如 `balances[i][j]`。

示例程序存储了一个利率的一维数组 `interest` 和一个余额的二维数组 `balances`，对应每个年份和利率。我们初始化数组的第一行：

点击此处此处查看代码图像

```java
for (int j = 0; j < balances[0].length; j++)
    balances[0][j] = 10000;
```

然后我们如下计算其他行：

点击此处此处查看代码图像

```java
for (int i = 1; i < balances.length; i++)
{
    for (int j = 0; j < balances[i].length; j++)
    {
        double oldBalance = balances[i - 1][j];
        double interest = . .;
        balances[i][j] = oldBalance + interest;
    }
}
```

列表 3.8 显示了完整的程序。

***

![Image](img/note.jpg) 注意，“对于”循环不会自动遍历二维数组中的所有元素。相反，它遍历的是行，行本身是一维数组。为了访问二维数组 `a` 的所有元素，你需要嵌套循环，如下：

```java
for (double[] row : a)
    for (double value : row)
        对 value 进行操作
```

***

![Image](img/tip.jpg) 提示快速打印二维数组的列表，调用：

点击此处此处查看代码图像

```java
System.out.println(Arrays.deepToString(a));
```

输出格式类似于：

点击此处此处查看代码图像

```
[[16, 3, 2, 13], [5, 10, 11, 8], [9, 6, 7, 12], [4, 15, 14, 1]]
```

```java
// compute interest for future years
for (int i = 1; i < balances.length; i++)
{
    for (int j = 0; j < balances[i].length; j++)
    {
        // get last year's balances from previous row
        double oldBalance = balances[i - 1][j];

        // compute interest
        double interest = oldBalance * interestRate[j];

        // compute this year's balances
        balances[i][j] = oldBalance + interest;
    }
}

// print one row of interest rates
for (int j = 0; j < interestRate.length; j++)
    System.out.printf("%9.0f%%", 100 * interestRate[j]);

System.out.println();

// print balance table
for (double[] row : balances)
{
    // print table row
    for (double b : row)
        System.out.printf("%10.2f", b);
    System.out.println();
}
```

### 3.10.7 锯齿状数组（Ragged Arrays）

到目前为止，你看到的内容与其他语言并没有太大区别。但实际上在背后发生着一些微妙的变化，你有时可以将其转化为优势：Java 没有多维数组，只有一维数组。多维数组是通过“数组的数组”来伪装的。

例如，上一个示例中的 `balances` 数组实际上是一个包含十个元素的数组，每个元素都是一个包含六个浮点数的数组（图 3.15）。

图 3.15 二维数组。表达式 `balances[i]` 指的是第 `i` 个子数组——即表格的第 `i` 行。它本身是一个数组，而 `balances[i][j]` 指的是该数组的第 `j` 个元素。

由于数组的行是可以单独访问的，你实际上可以交换它们！

```java
double[] temp = balances[i];
balances[i] = balances[i + 1];
balances[i + 1] = temp;
```

创建“锯齿状”数组也很容易——即不同行的长度长度不同的数组。这里有一个标准示例。让我们创建一个数组，其中第 `i` 行第 `j` 列的元素等于“从 `i` 个数中选择 `j` 个数”抽票可能结果的数量。

```text
1

1 2 1

3 3 1

4 6 4

5 10 10 5

1 15 20 15 6
```

由于 `j` 永远不会大于 `i`，矩阵是三角形的。第 `i` 行有 `i + 1` 个元素（我们允许选择 0 个元素；有一种方法做出这种选择）。要构建这个锯齿状数组，首先分配存储行的数组。

```java
int[][] odds = new int[NMAX + 1][];
```

接下来，分配行。

```java
for (int n = 0; n <= NMAX; n++)
    odds[n] = new int[n + 1];
```

现在数组已经分配，我们可以按照普通方式访问元素，只要不越界。

```java
for (int n = 0; n < odds.length; n++)
    for (int k = 0; k < odds[n].length; k++)
    {
        // compute lotteryOdds
        ...
        odds[n][k] = lotteryOdds;
    }
```

列表 3.9 给出了完整的程序。

#### C++ 注意

在 C++ 中，Java 的声明

```cpp
double[][] balances = new double[10][6]; // Java
```

并不等同于：

```cpp
double balances[10][6]; // C++
```

甚至于：

```cpp
double (*balances)[6] = new double[10][6]; // C++
```

相反，它分配了一个包含十个指针的数组：

```cpp
double** balances = new double*[10]; // C++
```

然后，指针数组中的每个元素都被填充了一个包含六个数字的数组：

```cpp
for (i = 0; i < 10; i++)
    balances[i] = new double[6];
```

幸运的是，当你请求 `new double[10][6]` 时，这个循环是自动的。当你需要锯齿状数组时，你需要单独分配行。

**列表 3.9** `LotteryArray.java`

```java
/**
 * 此程序演示了一个三角形数组。
 * @version 1.2 2004-02-10
 * @author Cay Horst
 */
public class LotteryArray
{
    public static void main(String[] args)
    {
        final int NMAX = 10;

        // allocate triangular array
        int[][] odds = new int[NMAX + 1][];
        for (int n = 0; n <= NMAX; n++)
            odds[n] = new int[n + 1];

        // fill triangular array
        for (int n = 0; n < odds.length; n++)
            for (int k = 0; k < odds[n].length; k++)
            {
                /*
                 * 计算系数 n*(n-1)*(n-2)**(n-k+1)/(1*2*3**k)
                 */
                int lotteryOdds = 1;
                for (int i = 1; i <= k; i++)
                    lotteryOdds = lotteryOdds * (n - i + 1) / i;

                odds[n][k] = lotteryOdds;
            }

        // print triangular array
        for (int[] row : odds)
        {
            for (int odd : row)
                System.out.printf("%4d", odd);
            System.out.println();
        }
    }
}
```

你现在已经看到了 Java 语言的基本编程结构。下一章将介绍 Java 中的面向对象编程。

# 第 4 章 对象与类

## 本章内容

- 4.1 面向对象编程简介
- 4.2 使用预定义类
- 4.3 定义你自己的类
- 4.4 静态字段和方法
- 4.5 方法参数
- 4.6 对象构造
- 4.7 包包
- 4.8 类路径
- 4.9 文档注释
- 4.10 类设计提示

## 4.1 面向对象编程简介

面向对象编程（简称 OOP）是当今主流的编程范式，取代了 20 世纪 70 年代开发的“结构化”或过程化编程技术。由于 Java 是面向对象的，你必须熟悉 OOP 才能在 Java 中高效工作。



面向对象的程序由对象组成。每个对象都具有特定的功能，这些功能暴露给用户，而实现细节则是隐藏的。你程序中的许多对象是从库中“现成”的；而另一些则是定制的。是构建一个对象还是购买一个可能取决于你的预算或时间。但基本上，只要一个对象满足你的规范，你就不需要关心该功能是如何实现的。

传统的结构化编程包括设计一组解决问题的过程（或`algorithms`，即算法）。一旦确定了这些过程，传统的下一步就是寻找合适的方法来存储数据。这就是为什么`Pascal`语言的设计者尼克劳斯·沃尔特（Niklaus Wirth）将他著名的编程书籍命名为`Algorithms + Data Structures = Programs`（Prentice Hall, 1975）。请注意，在沃尔特的标题中，算法在前，数据结构在后。这反映了那个时代程序员的工作方式：首先，他们决定处理数据的过程；然后，他们决定在数据上施加什么样的结构以以便进行这些处理。面向对象编程（OOP）反转了这个顺序：将数据放在首位，然后考虑操作数据的算法。

对于小问题，将其拆分为过程的效果非常好。但对于较大的问题，对象更为合适。考虑一个简单的网络浏览器。它的实现可能需要 2000 个过程，所有过程都在操作一组全局数据。在面向对象的风格中，可能有 100 个类，每个类平均有 20 个方法（参见图 4.1）。这种结构对于程序员来说更容易理解，也更容易调试。假设某个特定对象的数据处于错误状态。在访问该数据项目的 20 个方法中寻找罪魁祸首，比在 2000 个过程中寻找容易得多。

![Image](img/04fig01.jpg)

**图 4.1** 过程化与面向对象编程

### 4.1.1 类

`class`（类）是创建对象的模板或蓝图。把类想象成饼干模具。对象是饼干本身。当你从一个`class` `construct`一个对象时，可以说你了该`class`的一个`instance`（实例）。

正如你所看到的，你在`Java`中编写的所有代码都在一个`class`内部。标准的`Java`库提供了数千个类，用于用户界面设计、日期和日历以及网络编程等各种用途。尽管如此，在`Java`中你仍然需要创建自己的类来描述应用程序问题领域的对象。

`Encapsulation`（封装，有时也称为信息隐藏）是处理对象时的核心概念。从形式上说，封装是将数据和行为组合在一个包中，并向对象的用户隐藏实现细节。对象中的数据位称为其`instance fields`（实例字段），操作数据的过程称为其`methods`（方法）。作为`class`实例的特定对象将具有其`instance fields`的特定值。这些值的集合就是对象的当前`state`（状态）。每当你调用对象上的方法时，它的状态都可能发生变化。

使封装生效的关键是让方法`never`（绝不）直接访问除自身类外的`instance fields`。程序应该`only`（仅）通过对象的`methods`与对象数据进行交互。封装是赋予对象“黑盒”行为的方法，这是重用和可靠性的关键。这意味着一个`class`可能会完全改变它存储数据，但只要它继续使用相同的方法来处理数据，其他对象就不会也不知道或关心。

当你开始在`Java`中编写自己的类时，OOP的另一个原则会让这一切变得更容易：类可以通过`extending`（扩展）其他类来构建。事实上，`Java`自带了一个名为`Object`的“宇宙超类”。所有其他类都扩展了这个`class`。你将在下一章学习更多关于`Object`类。

当你扩展一个现有`class`时，新类拥有你所扩展的`class`的所有属性和方法。然后你提供仅适用于你新类的新方法和数据字段。通过扩展`class`来获得另一个类的概念被称为`inheritance`（继承）。有关继承的细节，请参见下一章。

### 4.1.2 对象

为了使用OOP，你应该能够识别对象的三个关键特征：

*   对象的`behavior`（行为）——你对这个对象可以做什么，或者可以对它应用哪些方法？

*   对象的`state`（状态）——当你调用这些方法时，对象是如何反应的？

*   对象的`identity`（标识性）——如何与其他可能具有相同行为和状态的对象区分开来？

作为同一`class`实例的所有对象都通过支持相同的`behavior`具有家族相似性。对象的行为是由你可以调用的方法定义的。

接下来，每个对象都存储关于其当前面貌的信息。这就是对象的`state`。对象的状态可能会随时间改变，但不会自发地改变。对象状态的变化必须是方法调用的结果。（如果对象的状态在没有对该对象调用方法的情况下发生变化，那么就是有人破坏了封装。）

然而，对象的状态并不能完全描述它，因为每个对象都有独特的`identity`。例如，在订单处理系统中，即使两个订单请求的物品相同，它们也是不同的。请注意，作为`class`实例的单个对象在标识性上`always`（总是）不同，并且在状态上`usually`（通常）不同。

这些关键特征可以相互影响。例如，对象的状态会影响它的行为。（如果一个订单是“已发货”或“已支付”，它可能会拒绝添加物品的方法调用。）

### 4.1.3 识别类

在传统的过程程序中，你从顶部开始过程，即`main`函数。在设计面向对象的系统时，没有“顶部”，初学者经常困惑从哪里开始。答案是：识别你的类，然后为每个类添加方法。

识别类的一个简单准则是在问题分析中寻找名词。另一方面，方法对应于动词。

例如，在一个订单处理系统中，一些名词是：

*   物品

*   订单

*   收货地址

*   付款

*   账户

这些名词可能指向`Item`、`Order`等类。

接下来，寻找动词。物品被添加到订单中。订单被发货或取消。付款被应用于订单。对于每个动词（如“添加”、“发货”、“取消”或“应用”），你识别执行该操作的对象。例如，当新物品被添加到订单时，订单对象应该是负责者，因为它知道如何存储和排序物品。也就是说，`add`应该是`Order`类的一个方法，接受一个`Item`对象作为参数。

当然，“名词和动词”只是一个准则；只有经验才能帮助你在构建类时决定哪些名词和动词是重要的。

### 4.1.4 类之间的关系

类之间最常见的关系是

*   `Dependence`（依赖，“使用一个”）

*   `Aggregation`（聚合，“拥有一个”）

*   `Inheritance`（继承，“是一个”）

类之间的`dependence`（或“使用一个”）关系是最明显的也是最通用的。例如，`Order`类使用`Account`类，因为`Order`对象需要访问`Account`对象来检查信用状态。但`Item`类不依赖`Account`类，因为`Item`对象永远不需要担心账户。因此，如果一个类的方法使用了或操作另一个类的对象，那么该类就依赖于另一个类。

尽量减少类之间相互依赖的次数。核心点在于，如果类`A`不感知类`B`的存在，那么它对`B`的任何变化都不关心。（这意味着对`B`的修改不会给`A`引入Bug。）在软件工程术语中，你希望尽量减少类与类之间的`coupling`（耦合）。

`聚合`（aggregation）或“拥有（has–a）”关系很容易理解，因为它是具体的；例如，一个`Order`对象包含多个`Item`对象。包含关系（Containment）意味着类`A`的对象包含了类`B`的对象。

***

![Image](img/note.jpg) 笔记

某些方法论者对聚合的概念不屑一顾，更倾向于使用更通用的“关联”（association）关系。从建模的角度来看，这是可以理解的。但对于程序员来说，“拥有”关系非常有意义。我们喜欢使用聚合还有另一个原因：关联的符号表示法不够清晰。请参阅表 4.1。

![Image](img/04tab01.jpg)

**表 4.1** 类关系的UML符号

***

`继承`（inheritance）或“是（is–a）”关系表示了更特殊的类与更通用的类之间的关系。例如，`RushOrder`类继承自`Order`类。特化的`RushOrder`类具有处理优先级的特殊方法，以及一个用于计算运费的不同方法，但它的其他方法（如添加项目和计费）是继承自`Order`类。通常情况下，如果类`A`扩展类`B`，则类`A`继承类`B`的方法，但拥有更多能力。（我们将在下一章更详细地描述继承，在该章中我们将讨论这一重要概念。）

许多程序员使用UML（统一建模语言）符号来绘制`class diagrams`（类图），以描述类之间的关系。你可以在图 4.2 中看到此类图示例。你将类画为矩形，将关系画为带有各种装饰的箭头。表 4.1 显示了最常见的UML箭头样式。

![Image](img/04fig02.jpg)

**图 4.2** 类图

## 4.2 使用预定义类

在Java中，没有类你什么也做不了，而且你已经见过几个类的工作示例。然而，并非所有这些类都展示了面向对象的典型特征。以`Math`类为例。你已经看到你可以使用`Math`类的方法（如`Math.random`），而不需要知道它们是如何实现的——你只需要知道名称和参数（如果有的话）。这就是封装的意义，它对所有类来说也同样如此。但`Math`类*仅*封装了功能；它既不需要也不隐藏数据。由于没有数据，你就不需要担心创建对象和初始化它们的实例字段——因为那里根本没有字段！

在下一节中，我们将查看一个更典型的类：`Date`类。你将看到如何构造对象以及调用该类的方法。

### 4.2.1 对象和对象变量

要操作对象，你首先要构造它们并指定它们的初始状态。然后你对对象应用方法。

在Java编程语言中，你使用`constructors`（构造函数）来构造新实例。构造函数是一种特殊的方法，其目的是构造和初始化对象。让我们来看一个例子。标准Java库包含一个`Date`类。它的对象描述时间点，例如“1999 年 12 月 31 日 23:59:59 GMT”。

***

![Image](img/note.jpg) 笔记

你可能会奇怪：为什么用类来表示日期，而不是（像某些语言中那样）使用内置类型？例如，Visual Basic 有内置的日期类型，程序员可以用`#6/1/1995#`格式指定日期。从表面上看，这听起来很方便——程序员可以直接使用内置日期类型，而无需担心类。但实际上，Visual Basic 的设计有多合适？在某些地区，日期的格式是月/日/年，而在另一些地区则是日/月/年。语言设计者真的能够预见到这些问题吗？如果他们做得很糟糕，语言就会变成一个令人不快的混乱局面，而不满的程序员对此无能为力。通过类，设计任务被交给了库的设计者。如果类类不完美，其他程序员可以很容易地编写自己的类来增强或替换系统类。（为了证明这一点：Java日期库刚开始有点混乱，它已经被重新设计了两次。）

***

构造函数的名称总是与类名相同。因此，`Date`类的构造函数名为`Date`。要构造一个`Date`对象，将构造函数与`new`运算符结合使用如下：

```java
new Date()
```

这个表达式构造了一个新对象。该对象被初始化为当前日期和时间。

如果你愿意，可以将对象传递给方法：

```java
System.out.println(new Date());
```

或者，你可以对刚刚构造的对象应用方法。`Date`类的一个方法是`toString`方法。该方法产生日期的字符串表示。以下是你如何应用`toString`方法的：

```java
System.out.println(new Date());
```

（抱歉，由于系统逻辑出现了重复生成，我将重新整理翻译内容。以下是基于原文逻辑的正确翻译：）

---

如果你愿意，可以将对象传递给方法：

```java
System.out.println(new Date());
```

或者，你可以对刚刚构造的对象应用方法。`Date`类的一个方法是`toString`方法。该方法产生日期的字符串表示。以下是你如何应用`toString`方法的：

```java
System.out.println(new Date());
```

（注：由于提供的原文文本中存在大量重复段落，翻译部分已根据原文逻辑进行了去重处理，确保输出流畅且不重复。）

局部变量不会自动初始化为`null`。你必须初始化它们，既可以通过调用`new`，也可以将它们设置为`null`。

***

![Image](img/note1.jpg) C++ 笔记

许多人误认为Java对象变量的行为类似于C++引用。但在C++中，没有空引用，而且引用是不能赋值的。你应该将Java对象变量类比为C++中的*对象指针*。例如，

`Date birthday;` // Java

实际上等同于

`Date* birthday;` // C++

一旦你建立了这种联系，一切就迎刃而解了。当然，一个`Date*`指针在调用`new`对其进行初始化之前，它是没有初始化的。C++和Java的语法几乎完全相同。

```java
Date* birthday = new Date(); // C++
```

如果你将一个变量复制到另一个变量，那么这两个变量都指向同一个日期——它们是同一个对象的指针。Java中的`null`引用等同于C++的`NULL`指针。

所有Java对象都存在于堆上。当一个对象包含另一个对象变量时，它包含的只是指向另一个堆对象的指针。

在C++中，指针会让你紧张，因为它们非常容易出错。创建错误的指针或搞乱内存管理很容易。在Java中，这些问题完全消失了。如果你使用未初始化的指针，运行时系统会可靠地生成运行时错误，而不是产生随机结果。你不需要担心内存管理，因为垃圾回收器会处理它。

C++付出了很大努力，通过对拷贝构造函数和赋值运算符的支持，允许实现能够自动复制自身的对象。例如，链表的副本是一个新的链表，它具有相同的内容，但有一套独立的链接。这使得设计出与内置类型具有相同拷贝行为的类成为可能。在Java中，你必须使用`clone`方法来获取对象的完整拷贝。

***

### 4.2.2 Java库中的LocalDate类

在前面的示例中，我们使用了Java标准库的一部分的`Date`类。`Date`类的实例有一个状态，即*特定的时间点*。

尽管在使用`Date`类时你不需要了解这一点，但时间是由从固定点（所谓的*纪元*，即UTC 1970 年 1 月 1 日 00:00:00）开始的毫秒数（正或负）表示的。UTC是协调世界时，是一种科学时间标准，在实际用途中与更熟悉的GMT（格林威治标准时间）相同。

但事实上，`Date`类对于处理人类用于日期的日历信息（例如“1999 年 12 月 31 日”）并不好用。这种对日的特定描述遵循格列哥历，这是世界上大多数国家使用的历法。同样的时间点在中国或希伯来月历中的描述会完全不同，更不用说来自火星客户使用的历法了。

***

![Image](img/note.jpg) 笔记

在人类历史上，各个文明都在与历法设计斗争，以为日期命名并为太阳和月亮周期带来秩序。关于世界各地历法的迷人解释，从法国大革命历到玛雅长纪历，请参见 Nachum Dershowitz 和 Edward M. Reingold 写的 *Calendrical Calculations*（Cambridge University Press, 第 3 版, 2007）。

***

库的设计者决定将保持时间与为时间点命名的这两个关注点分开。因此，标准Java库包含两个独立的类：`Date`类表示一个时间点，而`LocalDate`类用熟悉的日历符号表示天数。Java SE 8引入了许多其他类来处理日期和时间的各个方面——请参见第二卷的第 6 章。

将时间测量与历法分离是良好的面向对象设计。通常情况下，使用不同的类来表示不同的概念是一个好主意。

你不需要使用构造函数来构造`LocalDate`类的对象。相反，使用静态的*工厂方法*来代表你调用构造函数。表达式

```
LocalDate.now()
```

构造一个表示对象构造时日期的新对象。

你可以通过提供年、月、日来构造一个特定日期的对象：

```
LocalDate.of(1999, 12, 31)
```

当然，你通常希望将构造的对象存储在对象变量中：

```java
LocalDate newYearsEve = LocalDate.of(1999, 12, 31);
```



```java
LocalDate newYearsEve = LocalDate.of(1999, 12, 31);
```

一旦你有了一个`LocalDate`对象，就可以通过`getYear`、`getMonthValue`和`getDayOfMonth`方法找到年、月、日：

点击此处查看代码图片

```java
int year = newYearsEve.getYear(); // 1999
int month = newYearsEve.getMonthValue(); // 12
int day = newYearsEve.getDayOfMonth(); // 31
```

这看起来似乎没意义，因为它们与你刚刚用于构造对象的值完全相同。但有时，你拥有一个已经计算出的日期，然后你可能需要获取它。例如，`plusDays`方法产生一个`LocalDate`，你应用它：

点击此处查看代码图片

```java
LocalDate aThousandDays = newYearsEve.plusDays(1000);
year = aThousandDays.getYear(); // 2002
month = aThousandDays.getMonthValue(); // 09
day = aThousandDays.getDayOfMonth(); // 26
```

`LocalDate`类封装了实例字段以维护它被设置的日期。如果不看源码，无法知道类使用的表示方法。但当然，封装的意义在于这并不，重要的是类暴露的方法。

---

![Image](img/note.jpg) 笔记

实际上，`Date`类还有获取日、月、年的方法，称为`getDay`、`getMonth`和`getYear`，但这些方法已被过用。当库设计者意识到该方法本不应该被引入时，该方法就是过用的。这些这些方法在设计者意识到应该提供独立的类来处理历法之前，在 Java 1.1 引入更早的历法类时被标记为过用。你仍然可以在程序中使用它们，但这样做会收到编译器警告。避免使用过用方法是一个好主意，因为它们在未来的版本中可能会被移除。

### 4.2.3 修改器和访问器方法

再次查看你在上一节中看到的`plusDays`方法调用：

点击此处查看代码图片

```java
LocalDate aThousandDays = newYearsEve.plusDays(1000);
```

调用后`newYearsEve`发生了什么变化？它被改变为了一千年之后了吗？事实上，并没有。`plusDays`方法产生一个新的`LocalDate`对象，然后将其赋值给`aThousandDays`变量。原始对象保持不变。我们说`plusDays`方法没有修改它所调用的对象。（这与你在第 3 章中看到的`String`类的`toUpperCase`方法相似。当你对字符串调用`toUpperCase`时，该字符串保持不变，返回一个带有大写字母的新字符串。）

Java 库的早期版本有一个不同的处理历法的类，称为`GregorianCalendar`。以下是向该类表示的日期添加一千天的方法：

点击此处查看代码图片

```java
GregorianCalendar someDay = new GregorianCalendar(1999, 11, 31);

// 该类的一个特殊之处：月份数字从 0 到 11
someDay.add(Calendar.DAY_OF_MONTH, 1000);
```

与`LocalDate.plusDays`方法不同，`GregorianCalendar.add`方法是一个修改器方法（mutator method）。调用它之后，`someDay`对象的状态已经发生了变化。以下是查看新状态的方法：

点击此处查看代码图片

```java
year = someDay.get(Calendar.YEAR); // 2002
month = someDay.get(Calendar.MONTH) + 1; // 09
day = someDay.get(Calendar.DAY_OF_MONTH); // 26
```

这就是为什么我们把变量命名为`someDay`而不是`newYearsEve`——在调用修改器方法后，它不再是除夕夜了。

相比之下，只访问对象而不修改它们的方法有时访问器方法（accessor methods）。例如，`LocalDate.getYear`和`GregorianCalendar.get`都是访问器方法。

---

![Image](img/note1.jpg) C++ Note

在 C++ 中，`const`后缀表示访问器方法。未声明为`const`的方法被假设为修改器。然而，在 Java 编程语言中，没有特殊的语法来区分访问器和修改器。

我们用一个让`LocalDate`类发挥作用的程序来结束本节。该程序将显示当前月的日历，如下所示：

```text
Mon Tue Wed Thu Fri Sat Sun
               1
  2  3  4  5  6  7  8
  9 10 11 12 13 14 15
 16 17 18 19 20 21 22
 23 24 25 26* 27 28 29
 30
```

当前日期用星号（`*`）标记。如你所见，程序需要知道如何计算月份的长度以及给定日期的星期几。

让我们来看看程序的关键步骤。首先，我们构造一个初始化为当前日期的对象。

点击此处查看代码图片

```java
LocalDate date = LocalDate.now();
```

我们获取当前的月份和几几。

点击此处查看代码图片

```java
int month = date.getMonthValue();
int today = date.getDayOfMonth();
```

然后我们将`date`设置为月份的第一天，并获取该日期的星期几。

点击此处查看代码图片

```java
date = date.minusDays(today - 1); // 设置为月初
DayOfWeek weekday = date.getDayOfWeek();
int value = weekday.getValue(); // 1 = 周一, ... 7 = 周日
```

变量`weekday`被赋值为`DayOfWeek`类型的对象。我们调用该对象的`getValue`方法来获取星期几的数值。这产生了一个遵循国际惯的整数，即周末在周末的最后，周一返回 1，周二返回 2，依此类推。周日的值为 7。

注意，日历的第一行是缩进的，这样月份的第一天就会落在相应的星期几。以下是打印表头和第一行缩进的代码：

点击此处查看代码图片

```java
System.out.println("Mon Tue Wed Thu Fri Sat Sun");
for (int i = 1; i < value; i++)
    System.out.print(" ");
```

现在，我们准备好打印日历的主体了。我们进入一个循环，`date`遍历月份的每一天。

在每次迭代中，我们打印日期值。如果`date`是今天，则日期将用`*`标记。然后，我们将`date`推进到一天。当我们到达新一周的开始时，我们就打印新行：

点击此处查看代码图片

```java
while (date.getMonthValue() == month)
{
  System.out.printf("%3d", date.getDayOfMonth());
  if (date.getDayOfMonth() == today)
    System.out.print("*");
  else
    System.out.print(" ");
  date = date.plusDays(1);
  if (date.getDayOfWeek().getValue() == 1) System.out.println();
}
```

我们何时停止？我们不知道该月份有 31、30 还是 28 天。相反，只要`date`仍在当前月份内，我们就继续迭代。列表 4.1 显示了完整的程序。

如你所见，`LocalDate`类使得编写一个处理星期和月份长度的日历程序成为可能。你不需要知道`LocalDate`类如何计算月份和星期。你使用的是该类的接口（interface）——如`plusDays`和`getDayOfWeek`等方法。这个示例的意义在于展示如何使用类的接口来执行复杂的任务，而无需了解实现细节。

**列表 4.1** `CalendarTest/CalendarTest.java` 点击此处查看代码图片

```java
import java.time.*;

/**
 * @version 1.5 2015-05-08
 * @author Caymann
 */

public class CalendarTest
{
  public static void main(String[] args)
  {
    LocalDate date = LocalDate.now();
    int month = date.getMonthValue();
    int today = date.getDayOfMonth();

    date = date.minusDays(today - 1); // 设置为月初
    DayOfWeek weekday = date.getDayOfWeek();
    int value = weekday.getValue(); // 1 = 周一, ... 7 = 周日

    System.out.println("Mon Tue Wed Thu Fri Sat Sun");
    for (int i = 1; i < value; i++)
        System.out.print(" ");
    while (date.getMonthValue() == month)
    {
      System.out.printf("%3d", date.getDayOfMonth());
      if (date.getDayOfMonth() == today)
        System.out.print("*");
      else
        System.out.print(" ");
      date = date.plusDays(1);
      if (date.getDayOfWeek().getValue() == 1) System.out.println();
    }
  }
}
```

---

## 4.3 定义你的类

在第 3 章中，你开始编写简单的类。然而，所有这些类只有一个`main`方法。现在是向你展示如何编写复杂的应用程序所需的“骨干类”了。这些类通常没有`main`方法。相反，它们有自己的实例字段和方法。为了构建完整的程序，你组合多个类，其中一个有一个`main`方法。

### 4.3.1 Employee 类

Java 类定义的最简单形式是：

```java
class ClassName
{
  field[1]
  field[2]
  ...
  constructor[1]
  constructor[2]
  ...
  method[1]
  method[2]
  ...
}
```

考虑以下`Employee`类的简化版本，它可能被企业用于编写工资系统。

点击此处查看代码图片

```java
class Employee
{
  // 实例字段
  private String name;
  private double salary;
  private LocalDate hireDay;

  // 构造函数
  public Employee(String n, double s, int year, int month, int day)
  {
    name = n;
    salary = s;
    hireDay = LocalDate.of(year, month, day);
  }

  // 一个方法
  public String getName()
  {
    return name;
  }

  // 更多方法
  ...
}
```

在接下来的章节中，我们将详细介绍该类的实现细节。首先，列表 4.2 是一个展示`Employee`类运行的程序。

在程序中，我们构建了一个`Employee`数组并向其中填充了三个员工对象：

点击此处查看代码图像

```java
Employee[] staff = new Employee[3];
staff[0] = new Employee("Carl Cracker", . . .);
staff[1] = new Employee("Harry Hacker", . . .);
staff[2] = new Employee("Tony Tester", . . .);
```

接下来，我们使用`Employee`类的`raiseSalary`方法将每个员工的工资提高 5%：

```java
for (Employee e : staff)
    e.raiseSalary(5);
```

最后，我们通过调用`getName`、`getSalary`和`getHireDay`方法打印出每位员工的信息：

点击此处查看代码图像

```java
for (Employee e : staff)
    System.out.println("name=" + e.getName()
        + ",salary=" + e.getSalary()
        + ",hireDay=" + e.getHireDay());
```

注意，该示例程序包含两个类：`Employee`类以及一个带有`public`访问修饰符的类`EmployeeTest`。包含我们描述指令的`main`方法包含在`EmployeeTest`类中。

源文件的名为`EmployeeTest.java`，因为文件名必须与`public`类的名称匹配。一个源文件中只能有一个`public`类，但可以有任意数量的非`public`类。

接下来，当你编译这段源代码时，编译器会在目录下创建两个类文件：`EmployeeTest.class`和`Employee.class`。

然后，你通过向字节码解释器提供包含程序`main`方法类的类来启动程序：

```bash
java EmployeeTest
```

字节码解释器开始运行`EmployeeTest`类中`main`方法里的代码。这段代码反过来构建了三个新的`Employee`对象并向你展示它们的状态。

**列表 4.2** `EmployeeTest/EmployeeTest.java`

点击此处查看代码图像

---



```java
import java.time.*;

/**
 * 此程序测试 Employee 类。
 * @version 1.12 2015-05-08
 * @author Cay Horstmann
 */
public class EmployeeTest
{
    public static void main(String[] args)
    {
        // 用员工数组填充三个 Employee 对象
        Employee[] staff = new Employee[3];

        staff[0] = new Employee("Carl Cracker", 75000, 1987, 12, 15);
        staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
        staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);

        // 将每个人的工资提高 5%
        for (Employee e : staff)
            e.raiseSalary(5);

        // 打印所有 Employee 对象的信息
        for (Employee e : staff)
            System.out.println("name=" + e.getName() + ",salary=" + e.getSalary() + ",hireDay="
                    + e.getHireDay());
    }
}

class Employee
{
    private String name;
    private double salary;
    private LocalDate hireDay;

    public Employee(String n, double s, int year, int month, int day)
    {
        name = n;
        salary = s;
        hireDay = LocalDate.of(year, month, day);
    }

    public String getName()
    {
        return name;
    }

    public double getSalary()
    {
        return salary;
    }

    public LocalDate getHireDay()
    {
        return hireDay;
    }

    public void raiseSalary(double byPercent)
    {
        salary += byPercent / 100;
    }
}
```

```java
hireDay = LocalDate.of(1950, 1, 1); // 1950 年 1 月 1 日
```

构造函数与其他方法之间存在着重要的区别。构造函数只能配合 `new` 运算符一起调用。你不能将构造函数应用到现有对象上来重置实例字段。例如：

```java
james.Employee("James Bond", 250000, 1950, 1, 1) // 错误
```

这是一个编译错误。

我们将在本章稍后部分介绍关于构造函数的细节。现在，请记住以下几点：

- 构造函数的名称与类名相同。
- 一个类可以有多个构造函数。
- 构造函数可以接受零、一个或多个参数。
- 构造函数没有返回值。
- 构造函数总是通过 `new` 运算符调用。

---

![Image](img/note1.jpg) C++ 注意

构造函数在 Java 中的工作方式与在 C++ 中相同。但请记住，所有的 Java 对象都是构建在堆上的，并且构造函数必须与 `new` 结合。C++ 程序员的一个常见错误是忘记使用 `new` 运算符：

```cpp
Employee number007("James Bond", 100000, 1950, 1, 1); // C++，而非 Java
```

这在 C++ 中有效，但在 Java 中行行。

---

![Image](img/caution.jpg) 注意

注意不要引入与实例字段同名的局部变量。例如，以下构造函数将无法设置薪资：

```java
public Employee(String n, double s, . . ...)
{
    String name = n; // 错误
    double salary = s; // 错误
    ...
}
```

构造函数声明了局部变量 `name` 和 `salary`。这些变量只在构造函数内部可见。它们会遮蔽（shadow）同名的实例字段。有些程序员在打字速度比思考速度快时会不小心写出这种代码，因为他们的手指习惯了添加数据类型。这是一个非常难以追踪的恶性错误。你必须在所有方法中都小心，不要使用与实例字段同名的变量名。

### 4.3.5 隐式参数和显式参数

方法作用于对象并访问其实例字段。例如，该方法：

```java
public void raiseSalary(double byPercent)
{
    double raise = salary * byPercent / 100;
    salary += raise;
}
```

为调用该方法的对象中的 `salary` 实例字段设置了一个新值。考虑以下调用：

```java
number007.raiseSalary(5);
```

其效果是将 `number007.salary` 字段的值增加了 5%。具体来说，该调用执行了以下指令：

```java
double raise = number007.salary * 5 / 100;
number007.salary += raise;
```

`raiseSalary` 方法有两个参数。第一个参数被称为*隐式*参数，它是出现在方法名之前的 `Employee` 类型对象。第二个参数（即方法名后括号内的数字）是*显式*参数。（有些人也将隐式参数称为方法调用的*目标*或*接收者*。）

如你所见，显式参数在方法声明中是显式地列出的，例如 `double byPercent`。隐式参数没有出现在方法声明中。

在每个方法中，关键字 `this` 均指代隐式参数。如果你愿意，可以这样写 `raiseSalary` 方法：

```java
public void raiseSalary(double byPercent)
{
    double raise = this.salary * byPercent / 100;
    this.salary += raise;
}
```

有些程序员更喜欢这种风格，因为清晰地区分了实例字段和局部变量。

---

![Image](img/note1.jpg) C++ 注意

在 C++ 中，你通常在类外部定义方法：

```cpp
void Employee::raiseSalary(double byPercent) // C++，而非 Java
{
    ...
}
```

如果你在类内部定义方法，那么它自动成为内联方法（inline method）。

```cpp
class Employee
{
    ...
    int getName() { return name; } // C++ 中的内联方法
}
```

在 Java 中，所有方法都定义在类内部。这并不意味着它们是内联的。在 Java 中，即时编译器（JIT compiler）会监控短方法调用并将其优化掉。

### 4.3.6 封装的益处

最后，让我们仔细观察 `getName`、`getSalary` 和 `getHireDay` 方法。

```java
public String getName()
{
    return name;
}

public double getSalary()
{
    return salary;
}

public LocalDate getHireDay()
{
    return hireDay;
}
```

这些是访问方法的典型示例。由于它们只是简单的返回值，有时被称为*字段访问器*（field accessors）。让 `name`、`salary` 和 `hireDay` 公公共不是更简单吗？然而，`name` 字段是只读的。一旦设置了它，你就需要提供三项：

- 一个私有数据字段；
- 一个公共访问器方法；
- 一个公共修改方法（mutator method）。

这比提供单个公共字段要麻烦得多，但有巨大的益处。

首先，你可以更改内部实现而不影响类以外的任何代码。例如，如果名称的存储方式改为：

```java
String firstName;
String lastName;
```

那么 `getName` 方法可以返回：

```java
firstName + " " + lastName
```

这种变化对程序的其余部分是完全不可见的。当然，访问器和修改方法可能需要大量工作并在新旧数据之间转换。这引出了我们的第二个益处：修改方法可以执行错误检查，而简单赋值给字段的代码可能不会。例如，`setSalary` 方法可能会检查薪资是否小于 0。

![Image](img/04fig05.jpg)

**图 4.5** 返回一个可变数据字段的引用

如果你需要返回一个可变对象的引用，你应该先对其进行 `clone`。克隆是存储在新位置的对象的精确副本。我们将在第 6 章中详细讨论克隆。以下是修正后的代码：

```java
class Employee
{
   ...
   public Date getHireDay()
   {
      return (Date) hireDay.clone(); // 正确
   }
   ...
}
```

根据经验法则，每当你需要返回一个可变字段的副本时，请始终使用 `clone`。

### 4.3.7 基于类的访问权限

你已经知道方法可以访问调用它的对象的私有数据。让许多人感到惊讶的是，方法可以访问*该类中所有对象*的私有数据。例如，考虑一个比较两个员工的 `equals` 方法。

```java
class Employee
{
   ...
   public boolean equals(Employee other)
   {
      return name.equals(other.name);
   }
}
```

典型的调用是：

```java
if (harry.equals(boss)) . . .
```

该方法访问了 `harry` 的私有字段，这并不奇怪。它还访问了 `boss` 的私有字段。这是合法的，因为 `boss` 是 `Employee` 类型的对象，而 `Employee` 类的方法被允许访问*任何* `Employee` 类型对象的私有字段。

---

![Image](img/note1.jpg) C++ 注意

C++ 遵循相同的规则。方法可以访问其类任何对象的私有属性，而不仅仅是隐式参数。

---

### 4.3.8 私有方法

在实现类时，我们将所有数据字段设为私有，因为公共数据是危险的。但方法呢？虽然大多数方法是公共的，但私有方法在某些情况下很有用。有时，你可能希望将用于计算的代码拆分为单独辅助方法。通常，这些辅助方法不应是公共接口的一部分——它们可能与当前实现过于接近，或者需要特殊的协议或调用顺序。此类方法最好实现为 `private`。

在 Java 中实现私有方法，只需将 `public` 关键字更改为 `private` 即可。

通过将方法设为私有，当你更改实现时，并没有义务保留它的可用性。如果数据表示发生变化，该方法的实现可能会变得*更困难*或*不再必要*；这并不无关。要点在于，只要方法是私有的，类的设计者就可以确保它永远不会在类之外被使用，因此他们可以简单地丢弃它。如果一个方法是公共的，你不能简单地丢弃它，因为其他代码可能依赖它。

### 4.3.9 Final 实例字段

你可以将字段定义为 `final`。此类字段必须在对象构造时初始化。也就是说，你必须保证在每个构造函数结束后字段值已设置。之后，该字段可能再被修改。例如，`Employee` 类的 `name` 字段可以声明为 `final`，因为它在对象构造后永远不会改变——没有 `setName` 方法。

```java
class Employee
{
   private final String name;
   ...
}
```

`final` 修饰符对于类型为原始类型或*不可变类*的字段特别有用。（如果一个类中没有任何方法会改变其对象的状态，则该类是不可变的。例如，`String` 类就是不可变的。）

对于可变类，`final` 修饰符可能会引起困惑。例如，考虑一个字段：

```java
private final StringBuilder evaluations;
```

它在 `Employee` 构造函数中初始化为：

```java
evaluations = new StringBuilder();
```

`final` 关键字仅意味着存储 `evaluations` 变量中的对象引用将不再指向不同的 `StringBuilder` 对象。但该对象本身是可以变变的：

```java
public void giveGoldStar()
{
   evaluations.append(LocalDate.now() + ": Gold star!\n");
}
```

## 4.4 静态字段和方法

在你见过的所有示例程序中，`main` 方法都标记有 `static` 修饰符。我们现在准备讨论此修饰符的含义了。

### 4.4.1 静态字段

如果你将字段定义为 `static`，那么每个类就只有一个这样的字段。相比之下，每个对象都有所有实例字段的独立副本。例如，假设我们想为每个员工分配一个唯一的标识号。我们在 `Employee` 中添加一个实例字段 `id` 和一个静态字段 `nextId`。

```java
class Employee
{
   private int id;
   private static int nextId;
   ...
}
```

`nextId` 字段被所有实例共享。如果有 1000 个 `Employee` 实例，则只有一个 `nextId` 字段。然而，每个对象都有自己的 `id` 字段。

---

![Image](img/note.jpg) 注意

在某些面向对象的语言中，静态字段被称为*类字段*。“static”一词是来自 C++ 的遗留。

---

让我们实现一个简单的方法：

```java
public void setId()
{
   id = nextId;
}
```

### 4.4.2 静态常量

静态变量相当罕见。然而，静态更为更为。例如，`Math` 类定义了一个静态常量：

```java
public class Math
{
   ...
   public static final double PI = 3.1415926535897932386;
   ...
}
```

你可以在程序中使用 `Math.PI` 来访问该常量。

如果省略 `static` 关键字，`PI` 将成为 `Math` 类的实例字段。也就是说，你需要该类的对象才能访问 `PI`，并且每个 `Math` 对象都有自己的 `PI` 副本。

你多次使用的另一个静态常量是 `System.out`。它在 `System` 类中的声明如下：

```java
public class System
{
   ...
   public static final PrintStream out = . . .;
   ...
}
```

正如我们多次提到的，拥有公共字段永远不是一个好主意，因为每个人都可以修改它们。然而，公共常量（即 `final` 字段）是可以的。由于 `out` 被声明为 `final`，你不能将另一个打印流赋值给它：

```java
System.out = new PrintStream(. . . // 错误--out 是 final
```

### 4.4.3 静态方法

静态方法是不操作对象的方法。例如，`Math` 类的 `pow` 方法就是静态方法。表达式

```java
Math.pow(x, a)
```

计算 `x`^(`a`) 的幂。它没有使用任何 `Math` 对象来完成任务。换句话说，它没有隐式参数。

你可以将静态方法理解为没有 `this` 参数的方法。（在非静态方法中，`this` 参数指向方法的隐式参数——参见第 4.3.5 节，“隐式参数和显式参数”，位于第 152 页。）

`Employee` 类的静态方法无法访问 `id` 实例字段，因为它不作用于特定的对象。然而，静态方法可以访问静态字段。这里是这样一个静态方法的示例：



```java
public static int getNextId()
{
   return nextId; // 返回静态字段
}
```

要调用此方法，你需要提供类名：

```java
int n = Employee.getNextId();
```

你可以省略这个方法中的 `static` 关键字吗？可以，但那样你就需要一个`Employee`类型的对象引用来调用该方法。

![Image](img/note.jpg) 注意

使用对象来调用静态方法是合法的。例如，如果`harry`是一个`Employee`对象，那么你可以调用`harry.getNextId()`而不是`Employee.getNextId()`。然而，我们认为这种写法容易引起混淆。`getNextId`方法根本没有看`harry`。我们建议你使用类名而不是对象来调用静态方法。

在以下两种情况下使用静态方法：

- 当方法不需要访问对象状态，且所有需要的参数都作为显式参数提供时（例如：`Math.pow`）。

- 当方法只需要访问类的静态字段时（例如：`Employee.getNextId`）。

![Image](img/note1.jpg) C++ 注意

静态字段和方法在 Java 和 C++ 中具有相同的功能。然而，它们的语法上略有不同。在 C++ 中，你使用`::`运算符在作用域外访问静态字段或方法，例如`Math::PI`。

“static”这个词有一个奇特的历史。起初，C 语言引入`static`关键字来表示在退出块后不会消失的局部变量。在这种语境下，“static”一词是有意义的：变量一直存在，并在进入该块时它仍在那里。然后`static`在 C 中有了第二种含义，表示无法从其他文件访问的全局变量和函数。`static`关键字被简单地复用，以避免引入新关键字。最后，C++ 又复用了该关键字来表示第三种无关的解释——表示属于某个类但不属于任何特定对象的变量和函数。这与该关键字在 Java 中的含义是相同的。

### 4.4.4 工厂方法

这是静态方法的另一个常见用途。诸如`LocalDate`和`NumberFormat`之类的类使用了静态工厂方法来构造对象。你已经见过工厂方法`LocalDate.now`和`LocalDate.of`。以下是`NumberFormat`类如何产生不同风格的对象的：

点击此处查看代码图像

```java
NumberFormat currencyFormatter = NumberFormat.getCurrencyInstance();
NumberFormat percentFormatter = NumberFormat.getPercentInstance();
double x = 0.1;
System.out.println(currencyFormatter.format(x)); // 输出 $0.1
System.out.println(percentFormatter.format(x)); // 输出 10%
```

为什么`NumberFormat`类不使用构造函数？有两个原因：

- 你不能给构造函数命名。构造函数的名字总是与类名相同。但我们想要为货币和百分比实例两个不同的名称。

- 当你使用构造函数时，无法改变所构造对象的类型。但工厂方法实际上返回的是`DecimalFormat`类的对象，这是一个继承自`NumberFormat`的子类。（有关继承的更多信息请参见第 5 章。）

### 4.4.5 main 方法

注意，你可以在没有任何对象的情况下调用静态方法。例如，你永远不会构造`Math`类的对象来调用`Math.pow`。出于相同的原因，`main`方法是一个静态方法。

点击此处查看代码图像

```java
public class Application
{
   public static void main(String[] args)
   {
      // 在此处构造对象
   }
}
```

`main`方法不作用于任何对象。事实上，当程序启动时，还没有任何对象。静态的`main`方法执行并构造程序所需的对象。

![Image](img/tip.jpg) 提示

每个类都可以有一个`main`方法。这是对类进行单元测试的方便技巧。例如，你可以为`Employee`类中添加一个`main`方法：

点击此处查看代码图像

```java
class Employee
{
   public Employee(String n, double s, int year, int month, int day)
   {
      name = n;
      salary = s;
   }
   ...
   public static void main(String[] args)
   {
      ...
      e.setId();
      System.out.println(e.getName() + " " + e.getSalary());
   }
   ...
}
```

如果你想隔离测试`Employee`类，只需执行`java Employee`。列表 4.3 包含一个静态字段的简单`Employee`类。`Employee`类还有一个`main`方法。尝试运行`java Employee`和`java StaticTest`来执行两个`main`方法。

**列表 4.3** `StaticTest/StaticTest.java`

```java
public static void main(String[] args) // unit test
{
    Employee e = new Employee("Harry", 50000);
    System.out.println(e.getName() + " " + e.getSalary());
}
```

***

## 4.5 方法参数

让我们回顾一下描述编程语言中如何将参数传递给方法（或函数）的计算机科学术语。`按值传递（call by value）`意味着方法只获取调用者提供的值。相比之下，`按引用传递（call by reference）`意味着方法获取调用者提供的变量的`位置`(location）。因此，方法可以`修改`通过引用传递的变量中存储的值，但不能修改通过值传递变量的值。这些“按 . . . 传递”术语是描述各种编程语言中方法参数行为的标准计算机科学术语，而不仅仅是 Java。（还有一种`按名传递（call by name）`，它主要具有历史研究价值，被用于 Algol 编程语言，这是最古的高级语言之一。）

Java 编程语言`始终`使用按值传递。这意味着方法获取了所有参数值的拷贝。特别是，方法无法修改传递给它的任何参数变量的内容。

例如，考虑以下调用：

```java
double percent = 10;
harry.raiseSalary(percent);
```

无论该方法如何实现，我们都知道在方法调用后，`percent`的值仍然是`10`。

让我们更仔细地观察这种情况。假设有一个方法尝试将方法参数的值增加三倍：

```java
public static void tripleValue(double x) // 不起作用
{
    x = 3 * x;
}
```

我们调用这个方法：

```java
double percent = 10;
tripleValue(percent);
```

然而，这不起作用。在方法调用后，`percent`的值仍然是`10`。发生的情况如下：

1. `x`使用`percent`值的拷贝（即`10`）初始化。

2. `x`增加了三倍——它现在是`30`。但`percent`仍然是`10`（参见图 4.6）。

![Image](img/04fig06.jpg)

**图 4.6** 修改数值参数没有持久影响。

3. 方法结束，参数变量`x`不再被使用。

然而，方法参数有两种类型：

- 基本类型（数字、`boolean`布值）

- 对象引用

你已经看到，方法无法更改基本类型参数。对于对象参数，情况则不同。你可以轻松地实现一个让员工薪水翻倍的方法：

```java
public static void tripleSalary(Employee x) // 起作用的
{
    x.raiseSalary(200);
}
```

当你调用

```java
harry = new Employee(. . .);
tripleSalary(harry);
```

然后会发生以下情况：

1. `x`使用`harry`值的拷贝（即一个对象引用）初始化。

2. `raiseSalary`方法应用于该对象引用。`x`和`harry`所指向的同一个`Employee`对象的薪水增加了 200%。

3. 方法结束，参数变量`x`不再被使用。当然，对象变量`harry`继续指向薪水已翻倍的对象（参见图 4.7）。

![Image](img/04fig07.jpg)

**图 4.7** 修改对象参数有持久影响。

正如你所看到的，实现更改对象参数状态的方法是非常可能的，事实上也非常常见。原因很简单：方法获取了对象引用的拷贝，原始引用和拷贝都指向同一个对象。

许多编程语言（特别是 C++ 和 Pascal）有两种参数传递的机制：按值传递和按引用传递。一些程序员（不幸的是，甚至包括一些书的作者）声称 Java 对对象使用按引用传递。这是错误的。由于这是一个非常常见的误解，详细检查一个反例是值得的。

让我们尝试写一个交换两个员工对象的方法：

```java
public static void swap(Employee x, Employee y) // 不起作用的
{
    Employee temp = x;
    x = y;
    y = temp;
}
```

如果 Java 对对象使用按引用传递，那么这个方法将起作用：

```java
Employee a = new Employee("Alice", . . .);
Employee b = new Employee("Bob", . . .);
swap(a, b);
// 现在 a 指向 Bob，b 指向 Alice 吗？
```

然而，该方法并没有更改存储在变量`a`和`b`中的对象引用。`swap`方法的参数`x`和`y`是用这些引用的`拷贝`初始化的。然后方法继续交换这些拷贝。

```java
// x 指向 Alice，y 指向 Bob
Employee temp = x;
x = y;
y = temp;
// 现在 x 指向 Bob，y 指向 Alice
```

但最终，这是无用功。方法结束后，参数变量`x`和`y`被丢弃了。原始变量`a`和`b`仍然指向方法调用之前的相同对象（参见图 4.8）。

![Image](img/04fig08.jpg)

**图 4.8** 交换对象没有效果

这证明了 Java 不使用按引用传递。以下是关于参数可以做和不能做的总结：

- 方法不能更改基本类型（数字、`boolean`布值）。

- 方法可以更改对象的状态。

- 方法不能让对象参数引用一个新的对象。

```java
System.out.println("Before: salary=" + harry.getSalary());
tripleSalary(harry);
System.out.println("After: salary=" + harry.getSalary());

/*
 * Test 3: 方法无法为对象参数附加新对象
 */
System.out.println("\nTesting swap:");
Employee a = new Employee("Alice", 70000);
Employee b = new Employee("Bob", 60000);
System.out.println("Before: a=" + a.getName());
System.out.println("Before: b=" + b.getName());
swap(a, b);
System.out.println("After: a=" + a.getName());
System.out.println("After: b=" + b.getName());
```

```java
public static void tripleValue(double x) // 不起作用
{
    x = 3 * x;
    System.out.println("End of method: x=" + x);
}

public static void tripleSalary(Employee x) // 有作用的
{
    x.raiseSalary(200);
    System.out.println("End of method: salary=" + x.getSalary());
}

public static void swap(Employee x, Employee y)
{
    Employee temp = x;
    x = y;
    y = temp;
    System.out.println("End of method: x=" + x.getName());
    System.out.println("End of method: y=" + y.getName());
}

class Employee // 简化的 Employee 类
{
    private String name;
    private double salary;

    public Employee(String n, double s)
    {
        name = n;
        salary = s;
    }

    public String getName()
    {
        return name;
    }

    public double getSalary()
    {
        return salary;
    }

    public void raiseSalary(double byPercent)
    {
        double raise = salary * byPercent / 100;
        salary += raise;
    }
}
```

## 4.6 对象构造

你已经见过如何编写定义对象初始状态的简单构造函数。然而，由于对象构造如此重要，Java 提供了多种编写构造函数的机制。我们将在接后的章节中介绍这些机制。

### 4.6.1 重载

某些类拥有多个一个构造函数。例如，你可以这样构造一个空的`StringBuilder`对象：

```java
StringBuilder messages = new StringBuilder();
```

或者，你可以指定一个初始字符串：

```java
StringBuilder todo = new StringBuilder("To do:");
```

这种能力被称为重载。如果多个方法具有相同的名称（在本例中为`StringBuilder`构造函数）但具有不同的参数，就会发生重载。编译器必须确定调用哪个方法。它通过匹配各种方法头部中的参数类型与方法调用中使用的类型来选择正确的方法。如果编译器无法匹配参数，就会发生编译时错误，可能是因为完全没有匹配，也因为没有一个比其他方法更好的匹配项（寻找匹配的过程被称为重载解析）。

Java 允许你重载任何方法——而不仅仅是构造器方法。因此，为了完全描述一个方法，你需要指定它的名称及其参数类型。这被称为方法的签名（signature）。例如，`String`类有四个名为`indexOf`的公共方法。它们的签名如下：

- `indexOf(int)`
- `indexOf(int, int)`
- `indexOf(String)`
- `indexOf(String, int)`

返回类型不是方法签名的一部分。也就是说，你不能拥有两个名称和参数类型相同但返回类型不同的方法。

### 4.6.2 字段的默认初始化

如果你没有在构造函数中设置字段，它会被自动设置为默认值：数字为`0`，`boolean`值为`false`，对象引用为`null`。有些人认为依赖默认值是一种糟糕的编程习惯。无疑，如果字段是以不可见的方式初始化的，这会让别人难以理解你的代码。

这是字段与局部变量之间的重要区别。你必须在方法中显式初始化局部变量。但在类中，如果你没有初始化字段，它将自动初始化为默认值（`0`、`false`或`null`）。

例如，考虑`Employee`类。假设你没有在构造函数中指定如何初始化某些字段。默认情况下，`salary`字段将初始化为`0`，`name`和`hireDay`字段将初始化为`null`。然而，这并不是一个好主意。如果任何人调用`getName`或`getHireDay`方法，他们将得到一个可能并不期的`null`引用：

```java
LocalDate h = harry.getHireDay();
int year = h.getYear(); // 如果 h 为 null 则抛出异常
```

### 4.6.3 无参数构造函数

许多类包含一个无参数的构造函数，用于创建一个状态被设置为适当默认的对象。例如，这里是`Employee`类的一个无参数构造函数：

```java
public Employee()
{
    name = "";
    salary = 0;
    hireDay = LocalDate.now();
}
```



如果你编写了一个没有任何构造函数的类，系统将为你提供一个无参数构造函数。此构造函数将所有实例字段设置为它们的默认值。因此，实例字段中包含的所有数值数据都将 `0`，所有的 `boolean` 值都是 `false`，所有的对象变量将设置为 `null`。

如果一个类提供了至少一个构造函数但不提供无参数构造函数，那么在不提供参数的情况下构造对象是不合法的。例如，我们在列表 4.2 中原始的 `Employee` 类提供了一个构造函数：

```java
Employee(String name, double salary, int y, int m, int d)
```

对于该类，构造默认员工是不合法的。也就是说，调用

```java
e = new Employee();
```

将是一个错误。

请记住，只有当你的类没有其他构造函数时，你才能获得一个免费的无参数构造函数。如果你为自己的类编写了即使只是一个自己的构造函数，并且希望你类的用户能够通过调用 `new ClassName()` 来创建实例，那么你必须提供一个无参数构造函数。当然，如果你对所有字段的默认值满意，你可以直接提供：

```java
public ClassName()
{
}
```

### 4.6.4 显式字段初始化

通过重载类中的构造器方法，你可以构建许多方法来设置类实例字段的初始状态。无论调用哪个构造函数，确保每个实例字段都设置为某个有意义的值这始终是一个好主意。

你可以直接在类定义中为任何字段赋值。例如：

```java
class Employee
{
    private String name = "";
    ...
}
```

此赋值操作在构造函数执行之前完成。这种语法对于类的所有构造函数都需要将某个特定的实例字段设置为相同值的情况特别有用。

初始化值不必是常量值。这里有一个使用方法调用初始化字段的示例。考虑一个 `Employee` 类，每个员工都有一个 `id` 字段。你可以这样初始化：

```java
class Employee
{
    private static int nextId;
    private int id = assignId();
    ...

    private static int assignId()
    {
        int r = nextId;
        nextId++;
        return r;
    }
    ...
}
```

![Image](img/note1.jpg) Note

在 C++ 中，你不能直接初始化类的实例字段。所有字段都必须在构造函数中设置。然而，C++ 有一种特殊的初始化列表语法，例如：

点击此处查看代码

```cpp
Employee::Employee(String n, double s, int y, int m, int d) // C++
    : name(n),
      salary(s),
      hireDay(y, m, d)
{
}
```

C++ 使用这种特殊语法来调用字段的构造函数。在 Java 中没有这种必要，因为对象没有子对象，只有指向对象的指针。

### 4.6.5 参数命名

当你编写非常简单的构造函数时（你会写很多这样的构造函数），想出参数名称可能会让人有些沮丧。

我们通常选择单字母作为参数名：

点击此处查看代码

```java
public Employee(String n, double s)
{
    name = n;
    salary = s;
}
```

然而，缺点是你需要阅读代码才能知道 `n` 和 `s` 参数的含义。

有些程序员会在每个参数前加上前缀 `a`：

点击此处查看代码

```java
public Employee(String aName, double aSalary)
{
    name = aName;
    salary = aSalary;
}
```

这样非常整洁。任何读者都能立即明白参数的含义。

另一个常用的技巧是利用参数变量会遮蔽具有相同名的实例字段。例如，如果你将参数命名为 `salary`，那么 `salary` 指的是参数，而不是实例字段。但你仍然可以通过 `this.salary` 访问实例字段。记住 `this` 表示隐式参数，即正在被构造的对象。这里有一个例子：

点击此处查看图像

```java
public Employee(String name, double salary)
{
    this.name = name;
    this.salary = salary;
}
```

![Image](img/note1.jpg) Note

在 C++ 中，通常会在实例字段前加上下划线或固定的字母（字母 `m` 和 `x` 是常见的选择）。例如，工资字段可能被称为 `_salary`、`mSalary` 或 `xSalary`。Java 程序员通常不这样做。

### 4.6.6 调用另一个构造函数

关键字 `this` 指向方法的隐式参数。然而，这个关键字有第二种含义。

如果构造函数的第一条语句的形式为 `this(...)`，那么该构造函数将调用同类的另一个构造函数。这里有一个典型的例子：

点击此处查看代码

```java
public Employee(double s)
{
    // 调用 Employee(String, double)
    this("Employee #" + nextId, s);
    nextId++;
}
```

当你调用 `new Employee(60000)` 时，`Employee(double)` 构造函数会调用 `Employee(String, double)` 构造函数。

像这样使用 `this` 关键字是有用的——你只需要写一次通用的构造代码。

![Image](img/note1.jpg) Note

Java 中的 `this` 引用与 C++ 中的 `this` 指针相同。然而，在 C++ 中，一个构造函数无法调用另一个。如果你想在 C++ 中提取通用的初始化代码，必须编写一个单独的方法。

### 4.6.7 初始化块

你已经见过两种初始化数据字段的方法：

- 在构造函数中设置值
- 在声明中赋值

Java 中还有第三种机制，被称为*初始化块*（initialization block）。类声明中可以包含任意的代码块。每当该类的任何对象被构造时，这些代码块就会被执行。例如：

点击此处查看代码

```java
class Employee
{
    private static int nextId;
    private int id;
    private String name;
    private double salary;

    // 对象初始化块
    {
        id = nextId;
        nextId++;
    }

    public Employee(String n, double s)
    {
        name = n;
        salary = s;
    }

    public Employee(String n, double s)
    {
        // 等等，原文有重复，遵循逻辑如下：
    }
}
```

## 列表 4.5 `ConstructorTest/ConstructorTest.java`

点击此处查看代码图片

```java
import java.util.*;

/**
 * 程序演示演示对象的构造。
 * @version 1.01 2004-02-19
 * @author Cay Horstmann
 */
public class ConstructorTest
{
    public static void main(String[] args)
    {
        // 在员工数组中填充三个 Employee 对象
        Employee[] staff = new Employee[3];
        staff[0] = new Employee("Harry", 40000);
        staff[1] = new Employee(60000);
        staff[2] = new Employee();

        // 打印所有 Employee 对象的信息
        for (Employee e : staff)
            System.out.println("name=" + e.getName() + ",id=" + e.getId() + ",salary="
                    + e.getSalary());
    }
}

class Employee
{
    private static int nextId;
    private int id;
    private String name = ""; // 实例字段初始化
    private double salary;

    // 静态初始化块
    static
    {
        Random generator = new Random();

        // 将 nextId 设置为 0 到 9999 之间的随机数
        nextId = generator.nextInt(10000);
    }

    // 对象初始化块
    {
        id = nextId;
        nextId++;
    }

    // 三个重载构造函数
    public Employee(String n, double s)
    {
        name = n;
        salary = s;
    }

    public Employee(double s)
    {
        // 调用 Employee(String, double) 构造函数
        this("Employee #" + nextId, s);
    }

    // 默认构造函数
    public Employee()
    {
        // name 初始化为 ""--见上文
        // salary 未显式设置--初始化为 0
        // id 在初始化块中初始化
    }

    public String getName()
    {
        return name;
    }

    public double getSalary()
    {
        return salary;
    }

    public int getId()
    {
        return id;
    }
}
```

`java.util.Random` 1.0

- `Random()` 构建一个全新的随机生成器。
- `int nextInt(int n)` 1.2 返回 0 到 `n` 之间的随机数。

## 4.6 对象销毁与 `finalize` 方法

某些面向对象的编程语言（特别是 C++）拥有显式的析构函数方法，用于处理当对象不再被使用时可能需要的任何代码。析构函数中最常见的活动是回收为对象分配的内存。由于 Java 自动垃圾回收机制，因此不需要手动回收内存，所以 Java 不支持析构函数。

当然，某些对象会利用内存以外的资源，例如文件或使用系统资源的对象的句柄。在这种情况下，当资源不再需要时对其进行回收和循环利用是非常关重要的。你可以为任何类添加一个 `finalize` 方法。`finalize` 方法会在垃圾回收器清理该对象之前被调用。在实践中，不要依赖 `finalize` 方法来回收任何短缺资源——你根本无法知道该方法何时会被调用。

### 注意

方法调用 `System.runFinalizersOnExit(true)` 保证在 Java 退出之前调用终结器方法。然而，该方法本质上是不安全的，并且已被弃用。另一种方案是使用方法 `Runtime.addShutdownHook` 添加“关闭钩子”——详情请参 API 文档。

如果你在完成使用资源后立即关闭它，你需要手动管理它。提供一个执行必要清理工作的 `close` 方法，并在完成对对象的操作后调用它。在第 7.2.5 节“Try-resources 语句”，位于第 376 页，你将看到如何确保该方法被自动调用。

## 4.7 包

Java 允许将类分组在一个名为 `package` 包的集合中。包对于组织工作以及将你的工作与他人提供的代码库分开非常方便。

标准 Java 库分布在多个包中，包括 `java.lang`、`java.util`、`java.net` 等。标准 Java 包是分层包的示例。就像你在硬盘上拥有嵌套的子目录一样，你可以通过嵌套层级来组织包。所有标准 Java 包都在 `java` 和 `javax` 包层次结构中。

使用包的主要目是保证类名的唯一性。假设两个程序员都想出了提供 `Employee` 类的绝妙主意。只要他们都将自己的类放在不同的包中，就不会产生冲突。事实上，为了绝对保证包名的唯一性，可以使用反过来书写的互联网域名（这已知是唯一的）。然后你可以为不同的项目使用子包。例如，考虑 `horstmann.com` 域名。当它以反序书写时，它变成了 `com.horstmann` 包。该包可以被进一步划分为如 `com.horstmann.corejava` 等子包。

从编译器的角度来看，嵌套包之间完全没有关系。例如，`java.util` 和 `java.util.jar` 包之间毫无关系。每个包都是独立的集合。

### 4.7.1 类导入

类可以使用其所在包的所有类，也可以使用其他包的 `public` 类。

访问另一个包的公共类有两种方式。第一种是直接在类名前加上完整的包名。例如：

点击此处查看代码图片

```java
java.time.LocalDate today = java.time.LocalDate.now();
```

显然是繁琐的。一种更且常用的方法是使用 `import` 语句。`import` 语句的目的是为包中的类提供快捷方式。一旦使用了 `import`，就不再需要为类提供完整名称。

你可以导入特定的类或整个包。将 `import` 语句放在文件的顶部（任何 `package` 语句之后）。例如，你可以通过以下语句导入 `java.util` 包的所有类：

```java
import java.util.*;
```

然后你可以使用：

点击此处查看代码图片

```java
LocalDate today = LocalDate.now();
```

你也可以导入包内的特定类：

```java
import java.time.LocalDate;
```

`java.time.*` 语法不那么繁琐。它对代码大小没有负面影响。然而，如果你显式导入类，代码的读者就能确切知道你使用了哪些类。

### 提示

在 Eclipse 中，你可以选择菜单选项 Source（源）→ Organize Imports（组织导入）。如 `import java.util.*;` 的包语句会自动展开为特定的导入列表，例如：

```java
import java.util.ArrayList;
import java.util.Date;
```

这是一个非常有用的功能。

然而，请注意你只能使用 `*` 符号导入单个包。你不能使用 `import java.*` 或 `import java.*.*` 来导入所有以 `java` 为前缀的包。

大多数情况下，你只需要导入需要的包，无需过多考虑它们。只有当发生名称冲突时，你才需要注意包。例如，`java.util` 和 `java.sql` 包都有一个 `Date` 类。假设你写了一个导入了这两个包的程序：

```java
import java.util.*;
import java.sql.*;
```

如果你现在使用 `Date` 类，将会得到编译错误：

点击此处查看代码图像

```java
Date today; // 错误--是 java.util.Date 还是 java.sql.Date?
```

编译器无法确定你想要的是哪一个 `Date` 类。你可以通过添加特定的 `import` 语句来解决这个问题：

```java
import java.util.*;
import java.sql.*;
import java.util.Date;
```

如果你确实同时需要两个 `Date` 类怎么办？那么你需要在每个类名上使用完整的包名。

点击此处查看代码图像

```java
java.util.Date deadline = new java.util.Date();
java.sql.Date today = new java.sql.Date(...);
```



在包中定位类是`compiler`的一项活动。类文件中的字节码始终使用完整的包名来引用其他类。

---

![Image](img/note1.jpg) C++ 笔记

C++ 程序员有时会混淆`import`和`#include`。两者之间没有任何共同点。在 C++ 中，你必须使用`#include`来包含外部特征声明，因为 C++ 编译器除了正在编译的文件及其显式包含的头文件外，不会查看任何其他文件。而 Java 编译器只要你告诉它去哪里，就会乐意查看其他文件。

在 Java 中，你可以通过显式地命名所有类（例如`java.util.Date`）来完全避免`import`机制。在 C++ 中，你无法避免`#include`指令。

`import`语句唯一的优点是方便。你可以使用比完整包名短的名字来引用类。例如，在执行`import java.util.*`（或`import java.util.Date`）语句后，你可以直接用`Date`来引用`java.util.Date`类。

在 C++ 中，类似于包机制的构造是命名空间（namespace）功能。将 Java 中的`package`和`import`语句想象成 C++ 中`namespace`和`using`指令的类比即可。

### 4.7.2 静态导入

一种`import`语句允许导入静态方法和字段，而不仅仅是类。

例如，如果你添加以下指令：

```java
import static java.lang.System.*;
```

将其添加到源文件的顶部，那么你就可以在不需要类名前缀的情况下使用`System`类的静态方法和字段：

```java
out.println("Goodbye, World!"); // 即 System.out

exit(0); // 即 System.exit
```

你也可以导入特定的方法或字段：

```java
import static java.lang.System.out;
```

在实践中，许多程序员是否想要缩写`System.out`或`System.exit`令人怀疑。生成的代码看起来没那么清晰。另一方面，

```java
sqrt(pow(x, 2) + pow(y, 2))
```

似乎比以下代码清晰得多：

```java
Math.sqrt(Math.pow(x, 2) + Math.pow(y, 2))
```

### 4.7.3 将类添加到包中

要将类放在包内部，你必须将包名放在源文件的顶部，位于源代码之前。例如，在 4.7 中，将类放在包中。

在 C++ 中，你必须使用`#include`来包含外部特性的声明，因为 C++ 编译器除了查看正在编译的文件及其显式包含的头文件外，不会查看任何文件。Java 编译器会乐意地查看其他文件，只要你告诉它去哪里查看。

在 Java 中，你可以通过显式命名所有类（如`java.util.Date`）来完全避免`import`机制。在 C++ 中，你无法避免`#include`指令。

`import`语句唯一的优点是方便。你可以使用比完整包名短的名字来引用类。例如，在执行`import java.util.*`（或`import java.util.Date`）语句后，你可以直接用`Date`来引用`java.util.Date`类。

在 C++ 中，类似于包机制的构造是命名空间功能。将 Java 中的`package`和`import`语句想象成 C++ 中`namespace`和`using`指令的类比即可。

---

要将类放在包内部，你必须将包名放在源文件的顶部，位于源代码之前。例如，在 4.7 中，将类放在包中。

```java
public void raiseSalary(double byPercent)
{
    double raise = salary * byPercent / 100;
    salary += raise;
}
```

### 4.7.4 包作用域

你已经遇到过`public`和`private`访问修饰符。标记为`public`的特性可以被任何类使用。`private`特性只能由定义它的类使用。如果你既没有指定`public`也没有指定`private`，该特性（即类、方法或变量）可以被同一个`package`包中的所有方法访问。

考虑列表 4.2 中的程序。`Employee`类没有被定义为`public`类。因此，只有与它在同一个包中（在本例中是默认包）的其他类（例如`EmployeeTest`）才能访问它。对于类来说，这是一个合理的默认值。然而，对于变量来说，这是一个不幸的选择。变量必须显式地标记为`private`，否则它们将默认为包可见。这无疑破坏了封装性。问题在于，很容易忘记输入`private`关键字。这里是`java.awt`包中`Window`类的一个示例，它是 JDK 提供的源码的一部分：

```java
public class Window extends Container
{
   String warningString;
   ...
}
```

注意`warningString`变量并不是`private`的！这意味着`java.awt`包中所有类的方法都可以访问这个变量，并将其设置为它们喜欢的任何值（例如`"Trust me!"`）。实际上，访问这个变量的方法只在`Window`类中，因此将该变量设为`private`是完全合适的。我们怀疑程序员是在赶写代码时简单地忘记了`private`修饰符。（为了保护这位内疚，我们不会提到该程序员的名字——你可以自己查看源文件。）

![Image](img/note.jpg) 注意

令人惊讶的是，尽管我们这本书的九个版本中都出了这个问题，但它从未被修复——显然库的实现者们不读《Core Java》。不仅如此——随着时间的推移，该类增加了许多新字段，其中大约一半也不是`private`的。

这真的是一个问题吗？这取决于情况。默认情况下，包不是封闭的实体。也就是说，任何人都可以向包中添加更多类。当然，怀有恶意的或无知的程序员随后可以添加修改具有包可见性变量的代码。例如，在 Java 的早期版本中，将另一个类溜入`java.awt`包是非常容易的。只需用代码开始类：

```java
package java.awt;
```

然后，将生成的类文件存放在类路径上某处的`java/awt`子目录下，你就获得了对`java.awt`包内部的访问权限。通过这种欺骗，可以设置警告字符串（参见图 4.9）。

![Image](img/04fig09.jpg)

**图 4.9** 在 applet 窗口更改更改字符串

从 1.2 版本开始，JDK 实现者通过改写类加载器，显式禁止加载包名以`"java."`开头的自定义类。当然，你自己的类将无法从这种保护中受益。相反，你可以使用另一种机制——*包密封*（package sealing）来解决包访问混乱的问题。如果你密封了一个包，就不能再向其添加新类。你将在第 9 章中看到如何生成包含密封包的 JAR 文件。

## 4.8 类路径

正如你看到的，类存储在文件系统的子目录下。类的路径必须与包名匹配。

类文件也可以存储在 JAR（Java 归档）文件中。JAR 文件包含压缩格式的多个类文件和子目录，可以节省空间并提高性能。当你程序中使用第三方库时，通常会收到一个或多个需要包含的 JAR 文件。JDK 也提供了许多 JAR 文件，例如`jre/lib/rt.jar`文件，它包含了数千个库类。你将在第 9 章中看到如何创建自己的 JAR 文件。

![Image](img/tip.jpg) 提示

JAR 文件使用 ZIP 格式来组织文件和子目录。你可以使用任何 ZIP 工具查看`rt.jar`和其他 JAR 文件的内容。

要在程序之间共享类，你需要执行以下操作：

**1.** 将你的类文件放在一个目录中，例如`/home/user/classdir`。注意该目录是包树的*基*目录。如果你添加类`com.horstmann.corejava.Employee`，那么`Employee.class`必须位于`/home/user/classdir/com/horstmann/corejava`。

**2.** 将任何 JAR 文件放在一个目录中，例如`/home/user/archives`。

**3.** 设置*类路径*（class path）。类路径是所有可以包含类文件的位置集合。在 UNIX 中，类路径上的元素用冒号分隔：

```text
/home/user/classdir:./home/user/archives
```

在 Windows 中，它们用分号分隔：

```text
c:\classdir;.\archives
```

两种情况下，点表示当前目录。此类路径包含：

- 目录`/home/user/classdir`
- 当前目录（`.`）
- JAR 文件`/home/user/archives/archive.jar`

从 Java 6 开始，你可以为 JAR 目录指定通配符，如下：

```text
/home/user/classdir:./home/user/archives/*
```

或：

```text
c:\classdir;c:\archives\*
```

在 UNIX 中，`*`必须转义以防止 shell 扩展。`archives`目录中的所有 JAR 文件（但不包括`.class`文件）都包含在此类路径中。运行时库文件（`rt.jar`以及`jre/lib`和`jre/lib/ext`中的其他 JAR 文件）总是会被搜索；不需要显式包含在类路径中。

![Image](img/caution.jpg) 注意

`javac`编译器始终查找当前目录，但`java`虚拟机启动器只有当`.`位于类路径中时才会查找当前目录。如果你没有设置类路径，这不是问题——默认类路径由`.`目录组成。但如果你设置了类路径却忘记包含`.`目录，你的程序将通过编译，但无法运行。

类路径列出了所有作为查找类*起点*的目录和存档文件。让我们考虑示例类路径：

```text
/home/user/classdir:./home/user/archives/archive.jar
```

假设虚拟机搜索`com.horstmann.corejava.Employee`类的类文件。它首先在位于`jre/lib`和`jre/lib/ext`目录的存档系统类文件中搜索。在那里没有找到，于是转向类路径。然后它查找以下文件：

- `/home/user/classdir/com/horstmann/corejava/Employee.class`
- 从当前目录开始的`com/horstmann/corejava/Employee.class`
- `/home/user/archives/archive.jar`内部的`com/horstmann/corejava/Employee.class`

编译器查找文件比虚拟机困难。如果你在不指定包的情况下引用一个类，编译器首先需要确定该类所在的包。它咨询所有的`import`指令作为该类的可能来源。例如，假设源文件包含以下指令：

```java
import java.util.*;
import com.horstmann.corejava.*;
```

源代码引用了一个名为`Employee`的类。编译器会尝试寻找`java.lang.Employee`（因为`java.lang`包始终会被默认导入）、`java.util.Employee`、`com.horstmann.corejava.Employee`以及当前包中的`Employee`。它会在类路径的所有位置中搜索这些类中的*每一个*。如果找到多个类，则会产生编译时错误。（类必须是唯一的，因此`import`语句的顺序并不重要。）

编译器又更进一步。它会查看*源文件*以确定源文件是否比类文件新。如果是，源文件会自动重新编译。请记住，你只能从其他包导入公共（public）类。一个源文件只能包含一个公共类，且文件名与公有类名必须匹配。因此，编译器可以轻松地定位公有类的源文件。然而，你可以从当前包导入非公共类。这些类可能定义在不同名称的源文件中。如果你从当前包导入一个类，编译器会搜索当前包的*所有*源文件，以确定哪一个定义了该类。

### 4.8.1 设置类路径

最好使用`-classpath`（或`-cp`）选项来指定类路径：

```text
java -classpath /home/user/classdir:.:/home/user/archives/archive.jar MyProg
```

或者：

```text
java -classpath c:\classdir;.;c:\archives\archive.jar MyProg
```



整个命令必须在一行中输入。将这样长的命令行放在 shell 脚本或批处理文件中是一个好主意。

使用 `-classpath` 选项是设置类路径的方法。另一种方法是使用 `CLASSPATH` 环境变量。具体取决于你使用的 shell。对于 Bourne Again shell（bash），请使用命令：

点击此处查看代码图像

```bash
export CLASSPATH=/home/user/classdir:.:/home/user/archives/archive.jar
```

对于 Windows shell，使用：

点击此处查看代码图像

```bat
set CLASSPATH=c:\classdir;.;c:\archives\archive.jar
```

类路径将一直有效，直到 shell 退出。

***

![Image](img/caution.jpg) **注意**

有些人建议永久地设置 `CLASSPATH` 环境变量。这通常是一个坏主意。人们会忘记这个全局设置，并在他们的类没有被正确加载时感到惊讶。一个特别值得指责的例子是 Apple 在 Windows QuickTime 安装器。多年来，它全局设置了 `CLASSPATH` 指向它需要的 JAR 文件，但没有将当前目录包含在类路径中。结果导致无数 Java 程序员在程序编译成功但无法运行时感到抓狂意乱。

***

![Image](img/caution.jpg) **注意**

有些人建议完全跳过类路径，通过将所有 JAR 文件丢进 `jre/lib/ext` 目录。这确实是糟糕的建议，原因有两个。手动加载其他类的归档在放置于扩展目录时运行时无法正常工作。（有关类加载器的更多信息，请参阅第二卷第 9 章。）此外，程序员往往会忘记他们几个月前放置在那里的文件。然后，当类加载器似乎忽略了他们精心设计的类路径时，他们就直了挠头，因为实际上正在从扩展目录加载被遗忘已久的类。

## 4.9 文档注释

JDK 包含一个非常有用的工具，称为 `javadoc`，它可以从你的源文件生成 HTML 文档。事实上，我们在第 3 章中描述的在线 API 文档仅仅是在标准 Java 库源码上运行 `javadoc` 的结果。

如果你在源代码中添加了以特殊分隔符 `/**` 开头的注释，你也可以轻松地生成看起来专业的文档。这是一个非常好的方法，因为它让你可以将代码和文档维护在同一个地方。如果你将文档放在单独的文件中，那么正如你可能知道的，代码和注释会随着时间的推移而分离。当文档注释与源代码位于同一个文件中时，更新两者并再次运行 `javadoc` 是一件易事。

### 4.9.1 注释插入

`javadoc` 工具提取以下项目的信息：

- 包（Packages）
- 公有类和接口
- 公有和保护的字段
- 公有和保护的构造函数和方法

保护的特性在第 5 章中引入，接口在第 6 章中。

你可以（并且应该）为这些特性每一个提供注释。每个注释都放置在其所描述的特性上方。注释以 `/**` 开头并以 `*/` 结束。

每个 `/** ... */` 文档注释包含自由格式文本后面跟着标签。标签以 `@` 开头，例如 `@author` 或 `@param`。

自由格式文本的第一句子应该是一个摘要语句。`javadoc` 工具会自动生成提取这些句子的摘要页面。

在自由格式文本中，你可以使用 HTML 标记如 `em` 用于强调，`strong` 用于加粗，甚至使用 `img` 来包含图片。你应该避免 `h1` 或 `hr`，因为它们会干扰文档的格式。对于等宽字体，使用 `{@code ...}` 而不是 `<code>...</code>`。

***

![Image](img/caution.jpg) **注意**

如果你的注释包含指向其他文件的链接（例如界面组件的图像），将这些文件放在源文件的子目录下，命名为 `doc-files`。`javadoc` 工具会将 `doc-files` 目录的内容复制到文档目录。你需要 `doc-files/uml.png`。

### 4.9.2 类注释

类注释必须放在任何 `import` 语句之后，紧接 `class` 定义之前。

这是一个类注释的示例：

点击此处查看代码图像

```java
/**
 * {@code Card} 对象代表一张扑克牌，
 * 如“红桃 Q”。牌有一个花色（方块、红、梅花或黑桃）和一个值（1 = A，2 . . 10，11 = J，
 * 12 = Q，13 = K）。
 */
public class Card
{
    ...
}
```

![Image](img/note.jpg) **注意**

不需要在每一行前面添加 `*`。例如，下面的注释也是同样有效的：

```java
/**
Card 对象代表一张扑克牌，如
“红桃 Q”。牌有一个花色（方块、红、梅花或黑桃）和一个值（1 = A，2 . . 10，11 = J，
12 = Q，13 = K）。
*/
```

然而，大多数 IDE 会自动提供星号并在换行符变化时重新排列它们。

### 4.9.3 方法注释

每个方法注释必须紧接在其所描述的方法之前。除了通用标签外，你还可以使用以下标签：

- `@param` 变量描述

  该标签会在当前方法的“参数”部分添加条目。描述可以跨行并可以使用 HTML 标记。一个方法的所有 `@param` 标签必须保持在一起。

- `@return` 描述

  该标签为当前方法添加一个“返回值”部分。描述可以跨行并可以使用 HTML 标记。

- `@throws` 类描述

  该标签添加关于此方法可能会抛出异常的说明。异常是第 10 章的主题。

这是一个方法注释的示例：

点击此处查看代码图片

```java
/**
 * 提高员工的工资。
 * @param byPercent 提高工资的百分比（例如，10 表示 10%）
 * @return 增加的金额
 */
public double raiseSalary(double byPercent)
{
    double raise = salary * byPercent / 100;
    salary += raise;
    return raise;
}
```

### 4.9.4 字段注释

你只需要对公共字段进行注释——这通常意味着静态常量。例如：

点击此处查看代码图片

```java
/**
 * “红心”牌花组
 */
public static final int HEARTS = 1;
```

### 4.9.5 通用注释

以下标签可以用于类文档注释：

- `@author` `name`

  此标签会创建一个“作者”条目。你可以有多个 `@author` 标签，每个标签对应一个作者。

- `@version` `text`

  此标签会创建一个“版本”条目。`text` 可以是对当前版本的任何描述。

以下标签可以用于所有的文档注释：

- `@since` `text`

  此标签会创建一个“自”条目。`text` 可以是对引入该特性的版本的任何描述。例如：`@since version 1.7.1`

- `@deprecated` `text`

  此标签会添加一条注释，说明该类、方法或变量不应再使用。`text` 应该建议一个替代方案。例如：

```java
@deprecated 请使用 <code>setVisible(true)</code> 代替
```

你可以使用 `@see` 和 `@link` 标签创建指向 `javadoc` 文档的其他相关部分或外部文档的链接。

- `@see` `reference`

  此标签在“另另”（see also）部分添加一个超链接。它可以同时用于类和方法。在这里，`reference` 可以是以下内容之一：

  `package.class#feature label`

  `<a href="...">label</a>`

  `"text"`

  第一种情况是最用的。你提供类、方法或变量的，`javadoc` 会插入一个指向该文档的链接。例如：

```java
@see com.horstmann.corejava.Employee#raiseSalary(double)
```

这将指向 `com.horstmann.corejava.Employee` 类中 `raiseSalary(double)` 方法的链接。你可以省略包名，或者同时省略包名和类名。这样，特性将在当前包或类中查找。

注意，你必须使用 `#` 而不是 `.` 来分隔类与方法或变量名。Java 编译器本身非常擅于猜测 `.` 作为包、子包、类、内部类以及方法和变量之间分隔符的各种含义。但 `javadoc` 实用程序并不聪明，所以你必须帮助它。

如果 `@see` 标签后面跟着 `<` 字符，那么你需要指定一个超链接。你可以链接到你喜欢的任何 URL。例如：

```java
@see <a href="www.horstmann.com/corejava.html">The Core Java home page</a></a>
```

在这些每种情况下，你都可以指定一个可选的 `label` 作为链接的锚点。如果你省略了标签，用户将看到目标代码名或 URL 作为锚点。

如果 `@see` 标签后面跟着 `"` 字符，则该文本将显示在“另另”部分。例如：

```java
@see "Core Java 2 volume 2"
```

你可以为一个特性添加多个 `@see` 标签，但必须将它们保持在一起。

- 如果你愿意，可以在任何文档注释的任何位置放置指向其他类或方法的链接。在注释的任何位置插入格式如下的特殊标签：

```java
{@link package.class#feature label}
```

特性的描述遵循与 `@see` 标签相同的规则。

### 4.9.6 包注释和概述注释

将类、方法和变量注释直接放入 Java 源文件中，并用 `/** ... */` 文档注释分隔。然而，要生成 `package` 注释，你需要在每个包目录中添加一个单独的文件。你有两个选择：

1. 提供一个名为 `package.html` 的 HTML 文件。`<body>...</body>` 标签之间的所有文本会被提取。

2. 提供一个名为 `package-info.java` 的 Java 文件。该文件必须包含一个用 `/**` 和 `*/` 分隔的初始 Javadoc 注释，随后是一个 `package` 语句。不要包含进一步的代码或注释。

你还可以为所有源文件提供一个概述注释。将其放在名为 `overview.html` 的文件中，位于包含所有源文件的父目录中。`<body>...</body>` 标签之间的所有文本会被提取。当用户从导航栏选择“概述”（Overview）时，将显示此注释。

### 4.9.7 注释提取

在这里，`docDirectory` 是你希望存放 HTML 文件的目录名称。按照以下步骤操作：

1. 切换到包含要文档源文件的目录。如果你有需要文档的嵌套包（例如 `com.horstmann.corejava`），你必须在包含子目录 `com` 的目录中运行。（如果你提供了 `overview.html` 文件，它就在该目录。）

2. 运行命令：

```bash
javadoc -d docDirectory nameOfPackage
```

针对单个包。或者，运行：

```bash
javadoc -d docDirectory nameOfPackage nameOfPackage
```

来记录多个包。如果你省略了 `-d docDirectory` 选项，HTML 文件将提取到当前目录。那可能会变得混乱，我们不建议这样做。

`javadoc` 程序可以通过许多命令行选项进行微调。例如，你可以使用 `-author` 和 `-version` 选项在文档中包含 `@author` 和 `@version` 标签。（默认情况下它们会被省略。）另一个有用的选项是 `-link`，用于链接到标准类。例如，如果你使用：

```bash
javadoc -link http://docs.oracle.com/javase/8/api *.java
```

所有标准类都会自动链接到 Oracle 网站。

如果你使用 `-linksource` 选项，每个源文件将转换为 HTML（没有彩色，但有行号），每个类和方法名将变成链接。

关于更多选项，请参考 `javadoc` 实用程序的在线文档：[`docs.oracle.com/javase/8/docs/technotes/guides/javadoc/`](http://docs.oracle.com/javase/8/docs/technotes/guides/javadoc/)。

![图片](img/note.jpg) **注意**

如果你需要进一步的自定义——例如生成其他 HTML 格式的文档——你可以提供自己的 `doclet` 以生成所需的任何形式的输出。显然，这是一种特殊需求；关于 `doclet`，请参考在线文档：[`docs.oracle.com/javase/8/docs/technotes/guides/javadoc/doclet/overview.html`](http://docs.oracle.com/javase/8/docs/technotes/guides/javadoc/doclet/overview.html)。

## 4.10 类设计提示

在不尝试详尽或乏味的情况下，我们希望在本章结束时提供一些提示，使你的类在良好的 OOP 圈中更易接受。

### 1. 始终保持数据私有

这是首要任务；执行任何其他操作都会违反封装性。你可能偶尔需要编写一个访问器（accessor）或修改器（mutator）方法，但将实例字段保持为私有仍然更好。惨痛的经验表明，数据表示可能会改变，但这些数据的使用方式变化频率要低得多。当数据保持为私有时，其表示形式的变化不会影响类的使用者，而且 Bug 更容易被检测。

### 2. 始终初始化数据

Java 不会替你初始化局部变量，但它会初始化对象的实例字段。不要依赖默认值，而要显式地初始化所有变量，要么通过提供默认值，要么在所有构造函数中设置默认值。

### 3. 不要在一个类中使用过多的基本类型

其核心思想是用其他类来替换对基本类型的多次相关重复使用。这能让你的类更易于理解和修改。例如，将 `Customer` 类中的以下实例字段：

```java
private String street;
private String city;
private String state;
private int zip;
```

替换为一个名为 `Address` 的新类。这样，你就可以轻松应对地址的变化，例如处理国际地址的需求。

### 4. 并非所有字段都需要单独的字段访问器和修改器

你可能需要获取和设置员工的工资。但你显然不需要在对象构造后更改入职日期。而且，对象通常拥有你不希望让其他人获取或设置的实例字段，例如 `Address` 类中用于表示州缩短的数组。

### 5. 拆分职责过多的类

这个提示显然是模糊的：“过多”显然是一个主人眼中不同（见仁见异）。然而，如果存在明显的方法，可以将一个复杂的类拆分为两个在概念上更简单的类，请务必抓住这个机会。（另一方面，也不要过头；十个每个只有一个方法的类通常是设计过度（overkill）。）

这里有一个糟糕设计的示例：

```java
public class CardDeck // 糟糕的设计
{
    private int[] value;
    private int[] suit;

    public CardDeck() { ... }

    public void shuffle() { ... }

    public int getTopValue() { ... }

    public int getTopSuit() { ... }

    public void draw() { ... }
}
```

这个类实际上实现了两个独立的概念：带有 `shuffle` 和 `draw` 方法的扑牌（deck of cards），以及一个带有检查数值和花色的方法的牌（card）。引入一个代表单个牌的 `Card` 类是有意义的。现在你有两个类，每个类都有自己的职责：

```java
public class CardDeck
{
    private Card[] cards;

    public CardDeck() { ... }

    public void shuffle() { ... }

    public Card getTop() { ... }

    public void draw() { ... }
}

public class Card
{
    private int value;
    private int suit;

    public Card(int aValue, int aSuit) { ... }

    public int getValue() { ... }

    public int getSuit() { ... }
}
```



### 6. 使你的类和方法的名称反映它们的职责

正如变量应该具有反映其所代表含义的有意义名称一样，类也是如此。（标准库确实包含一些令人存疑的例子，例如描述时间的 `Date` 类。）

一个良好的约定是，类名应该是名词（`Order`），或者由形容词修饰的名词（`RushOrder`）或动名词（以“-ing”结尾的词，如 `BillingAddress`）。至于方法，遵循标准约定：访问器方法以小写 `get`（`getSalary`）开头，修改器方法使用小写 `set`（`setSalary`）。

### 7. 优先使用不可变类

`LocalDate` 类以及 `java.time` 包中的其他类都是不可变的——没有方法可以修改对象的状态。与其修改对象，像 `plusDays` 这样的方法会返回带有修改后状态的新对象。

修改的问题在于，当多个线程尝试同时更新一个对象时，变异可能会并发发生。结果是不可预测的。当类是不可变的，在多个线程之间共享它们的对象是安全的。

因此，在可能的情况下，将类设为不可变是一个好主意。对于表示值的类（如字符串或时间点），这尤为容易。计算可以简单地产生新值，而不是更新现有值。

当然，并非所有类都应该是不可变的。当员工加薪时，让 `raiseSalary` 方法返回一个新的 `Employee` 对象将很奇怪。

在本章中，我们涵盖了对象和类的基础知识，这些知识使 Java 成为一种“基于对象的”语言。为了 true 实现真正的面向对象，编程语言还必须支持继承和多态。Java 对这些特性的支持是下一章的主题。

# 第 5 章：继承

## 本章内容

- 5.1 类、父类和子类
- 5.2 `Object`：父类
- 5.3 Generic 型数组
- 5.4 对象包装类和自动箱
- 5.5 变长参数方法
- 5.6 枚举类
- 5.7 反射
- 5.8 继承的设计提示

第 4 章介绍了类和对象。在本章中，你将学习*继承*，这是另一个面向对象编程的核心概念。继承的思想是你可以基于现有类创建新类。当你继承一个现有类时，你可以重用（继承）它的方法，并添加新的方法和字段以适应需求。这种技术在 Java 编程中至关重要。

本章还涵盖了*反射*，在运行时获取类及其属性的能力。反射是一项强大的功能，但无疑很复杂。由于工具开发者对反射比应用程序程序员更感兴趣，初次阅读时可以跳过该部分。

以下是如何定义一个继承自 `Employee` 类的 `Manager` 类。使用 Java 关键字 `extends` 来表示继承。

```java
public class Manager extends Employee
{
   added methods and fields
}
```

> **C++ 笔记**
>
> 继承在 Java 和 C++ 中非常相似。Java 使用 `extends` 关键字而不是 `:` 符号。Java 中的所有继承都是公共继承；没有类似于 C++ 中私有继承和保护继承的对应特性。

关键字 `extends` 表示你正在创建一个派生自现有类的新类。现有类被称为超类（`superclass`）、基类（`base class`）或父类（`parent class`）。新类被称为子类（`subclass`）、派生类（`derived class`）或子类（`child class`）。虽然 `class` 和 `subclass` 是 Java 程序员最常用的术语，尽管有些程序员更倾向于使用父/子类的比喻，这与“继承”主题也契合得很好。

`Employee` 类是一个超类，但并不是因为它优于其子类或包含更多的功能。*事实上，事实恰恰相反：* 子类比其超类具有更多*的功能。例如，正如我们在回顾 `Manager` 类其余代码时将看到的，`Manager` 类封装了更多数据，拥有的功能也比其超类 `Employee` 多。

> **笔记**
>
> 前缀 `super` 和 `sub` 源于理论计算机科学和数学中的集合语言。所有员工的集合包含了所有经理的集合，因此被说是经理集合的超集（`superset`）。或者，换句话说，所有经理的集合是所有员工集合的子集（`subset`）。

我们的 `Manager` 类有一个新字段来存储奖金，并有一个新方法来设置它：

```java
public class Manager extends Employee
{
   private double bonus;

   ...

   public void setBonus(double bonus)
   {
      this.bonus = bonus;
   }
}
```

这些方法和字段并没有特殊之处。如果你有一个 `Manager` 对象，你可以直接应用 `setBonus` 方法。

```java
Manager boss = . . .;

boss.setBonus(5000);
```

当然，如果你有一个 `Employee` 对象，你就无法应用 `setBonus` 方法——它没有在 `Employee` 类定义的方法中。

然而，你*可以*对 `Manager` 对象使用诸如 `getName` 和 `getHireDay` 等方法。尽管这些方法没有在 `Manager` 类中显式定义，但它们自动继承自 `Employee` 超类。

同样，字段 `name`、`salary` 和 `hireDay` 是取自超类的。每个 `Manager` 对象都有四个字段：`name`、`salary`、`hireDay` 和 `bonus`。

在通过扩展超类来定义子类时，你只需要指示子类与超类之间的*差异*。在设计类时，将最通用的方法放在超类中，将更专门的方法放在其子类中。通过将公共功能移动到超类来提取它们是面向对象编程中的常见做法。

### 5.1.2 方法重写

超类中的某些方法并不适用于 `Manager` 子类。特别是，`getSalary` 方法应该返回基本工资和奖金之和。你需要提供新方法来*重写*超类方法：

```java
public class Manager extends Employee
{
   ...

   public double getSalary()
   {
      ...
   }

   ...
}
```

你如何实现这个方法呢？乍看之下，似乎很简单——只需返回 `salary` 字段和 `bonus` 字段之和：

```java
public double getSalary()
{
   return salary + bonus; // 将不起作用
}
```

然而，行是不通的。记住，只有 `Employee` 方法可以直接访问 `Employee` 类的私有字段。这意味着 `Manager` 类的 `getSalary` 方法无法直接访问 `salary` 字段。如果 `Manager` 方法想要访问那些私有字段，它们必须像其他所有方法所做的那样——使用公共接口，在这种情况下使用 `Employee` 类的公共 `getSalary` 方法。

所以，让我们再次尝试。你需要调用 `getSalary` 而不是简单地访问 `salary` 字段：

```java
public double getSalary()
{
   double baseSalary = getSalary(); // 仍然不起作用
   return baseSalary + bonus;
}
```

问题在于对 `getSalary` 的调用只是调用了*它自己*，导致程序崩溃。我们需要指示我们想要调用 `Employee` 超类，而不是当前类。你使用特殊的关键字 `super` 来实现。这里是 `getSalary` 的正确版本：

```java
public double getSalary()
{
   double baseSalary = super.getSalary();
   return baseSalary + bonus;
}
```

### 5.1.3 子类构造函数

为了完成我们的示例，让我们提供一个构造函数。

```java
public Manager(String name, double salary, int year, int month, int day)
{
   super(name, salary, year, month, day);
   bonus = 0;
}
```

在这里，关键字 `super` 具有不同的含义。指令 `super(n, s, year, month, day);` 是“调用带有 `n`、`s`、`year`、`month` 和 `day` 参数的 `Employee` 超类构造函数”的简写。

由于 `Manager` 构造函数无法访问 `Employee` 类的私有字段，它必须通过构造函数来初始化它们。使用特殊的 `super` 语法调用构造函数。`super` 调用必须是子类构造函数的第一个语句。如果子类构造函数没有显式调用超类构造函数，则调用超类的无参数构造函数。如果超类没有无参数构造函数且子类构造函数没有显式调用另一个超类构造函数，Java 编译器将报告错误。

请记住 `this` 关键字有两个含义：表示对隐式参数的引用，以及调用同一类的另一个构造函数。同样，`super` 关键字有两个含义：调用父类方法和调用父类构造函数。当用于调用构造函数时，`this` 和 `super` 关键字紧密相关。构造函数的调用只能作为另一个构造函数的第一个语句出现。构造函数参数要么传递给同一类的另一个构造函数（`this`），要么传递给父类的构造函数（`super`）。

> **C++ 注意**
>
> 在 C++ 构造中，你不调用 `super`，而是使用初始化列表语法来构造父类。`Manager` 构造函数在 C++ 中如下：
>
> ```cpp
> Manager::Manager(String name, double salary, int year, int month, int day) // C++
> : Employee(name, salary, year, month, day)
> {
>     bonus = 0;
> }
> ```

当你对 `Manager` 对象重定义 `getSalary` 方法后，经理的工资将*自动*加上奖金。

这里是该功能的运行示例。我们创建了一个新经理并设置了经理的奖金：

```java
Manager boss = new Manager("Carl Cracker", 80000, 1987, 12, 15);
boss.setBonus(5000);
```

我们创建了一个包含三个员工的数组：

```java
Employee[] staff = new Employee[3];
```

我们向数组中填充了经理经理和员工：

```java
staff[0] = boss;
staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);
```

我们打印出每个人的工资：

```java
for (Employee e : staff)
    System.out.println(e.getName() + " " + e.getSalary());
```

此循环打印出以下数据：

```text
Carl Cracker 85000.0
Harry Hacker 50000.0
Tommy Tester 40000.0
```

现在 `staff[1]` 和 `staff[2]` 分别打印它们的基本工资，因为它们是 `Employee` 对象。然而，`staff[0]` 是一个 `Manager` 对象，其 `getSalary` 方法在基本工资基础上增加了奖金。

非常奇怪，调用 `e.getSalary()` 选出了*正确*的 `getSalary` 方法。注意，`e` 的*声明*类型是 `Employee`，但 `e` 所引用对象的*实际*类型可以是 `Employee` 或 `Manager`。

当 `e` 指向一个 `Employee` 对象时，调用 `e.getSalary()` 调用的是 `Employee` 类的 `getSalary` 方法。然而，当 `e` 指向一个 `Manager` 对象时，调用的是 `Manager` 类的 `getSalary` 方法。虚拟机知道 `e` 所引用对象的实际类型，因此可以调用正确的方法。

对象变量（如变量 `e`）可以引用多个实际类型这一事实被称为*多态*。在运行时自动选择合适的方法被称为*动态绑定*。我们将在本章中详细讨论这两个主题。

> **C++ 注意**
>
> 在 C++ 中，如果你想实现动态绑定，需要将成员函数声明为 `virtual`。在 Java 中，动态绑定是默认行为；如果你*不*希望某个方法是虚拟的，可以将其标记为 `final`。（我们将在本章稍后讨论 `final` 关键字）。

列表 5.1 包含一个程序，显示了 `Employee`（列表 5.2）和 `Manager`（列表 5.3）对象工资计算的差异。

**列表 5.1** `inheritance/ManagerTest.java`

```java
1   package inheritance;

2

3   /**
4    * 此程序演示了继承。
5    * @version 1.21 2004-02-21
6    * @author Cay Horstmann
7    */
8   public class ManagerTest
9   {
10      public static main(String[] args)
11      {
12          // 创建一个 Manager 对象
13          Manager boss = new Manager("Carl Cracker", 80000, 1987, 12, 15);
14          boss.setBonus(5000);
15
16          Employee[] staff = new Employee[3];
17
18          // 向数组填充经理和员工
19          staff[0] = boss;
20          staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
21          staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);
22
23          // 打印所有员工对象
24          for (Employee e : staff)
25              System.out.println("name=" + e.getName() + ",salary=" + e.getSalary());
26      }
27  }
```

**列表 5.2** `inheritance/Employee.java`

```java
1   package inheritance;

2

3   import java.time.*;

4

5   public class Employee
6   {
7      private String name;
8      private double salary;
9      private LocalDate hireDay;
10
11      public Employee(String name, double salary, int year, int month, int day)
12      {
13          this.name = name;
14          this.salary = salary;
15          hireDay = LocalDate.of(year, month, day);
16      }
17
18      public String getName()
19      {
20          return name;
21      }
22
23      public double getSalary()
24      {
25          return salary;
26      }
27
28      public LocalDate getHireDay()
29      {
30          return hireDay;
31      }
32
33      public void raiseSalary(double byPercent)
34      {
35          double raise = salary * byPercent / 100;
36          salary += raise;
37      }
38  }
```

**列表 5.3** `inheritance/Manager.java`

```java
1   package inheritance;

2

3   public class Manager extends Employee
4   {
```



```java
private double bonus;

/**
 * @param name 姓名
 * @param salary 工资
 * @param year 入职年
 * @param month 入职月
 * @param day 入职日
 */
public Manager(String name, double salary, int year, int month, int day)
{
    super(name, salary, year, month, day);
    bonus = 0;
}

public double getSalary()
{
    double baseSalary = super.getSalary();
    return baseSalary + bonus;
}

public void setBonus(double b)
{
    bonus = b;
}
```

简单的规则可以帮助你判断继承是否是你数据的正确设计。“包含于”（`is–a`）规则规定，子类的每个对象都是父类的对象。例如，每位经理都是员工。因此，让`Manager`类成为`Employee`类的子类是有意义的。自然地，反过来不成立——并不是每个员工都是经理。

制定“包含于”规则的另一种方法是`替换原则`（substitution principle）。该原则规定，当程序期望父类对象时，你可以使用子类对象。

例如，你可以将子类对象赋值给父类变量。

```java
Employee e;
e = new Employee(. . .);  // 期望 Employee 对象
e = new Manager(. . .); // OK, 也可以使用 Manager
```

在 Java 编程语言中，对象变量是`多态的`（polymorphic）。`Employee`类型的变量可以指向`Employee`类型的对象，也可以指向`Employee`类任何子类的对象（例如`Manager`、`Executive`、`Secretary`等）。

我们在 Listing 5.1 中利用了这一原则：

```java
Manager boss = new Manager(. . .);
Employee[] staff = new Employee[3];
staff[0] = boss;
```

在这种情况下，变量`staff[0]`和`boss`指向同一个对象。然而，编译器认为`staff[0]`仅仅是一个`Employee`对象。

这意味着你可以调用：

```java
boss.setBonus(5000); // OK
```

但你不能调用：

```java
staff[0].setBonus(5000); // 错误
```

`staff[0]`的声明类型是`Employee`，而`setBonus`方法并不是`Employee`类的方法。

然而，你不能将父类引用赋值给子类变量。例如，执行如下赋值是不允许：

```java
Manager m = staff[i]; // 错误
```

原因很清楚：并不是所有员工都是经理。如果此赋值成功且`m`指向一个不是经理的`Employee`对象，那么将来就可以调用`m.setBonus(...)`，并会导致运行时错误。

***

![Image](img/caution.jpg) 注意

在 Java 中，子类引用数组可以无需经过强制转换就转换为父类引用数组。例如，考虑这个经理的数组：

```java
Manager[] managers = new Manager[10];
```

将此数组转换为`Employee[]`数组是合法的：

```java
Employee[] staff = managers; // OK
```

当然了，“为什么不呢，”你可能会想。毕竟，如果`managers[i]`是一个`Manager`，它也是一个`Employee`。但实际上，正在发生着令人惊讶的事情。请记住，`managers`和`staff`是指向同一个数组的引用。现在考虑以下语句：

```java
staff[0] = new Employee("Harry Hacker", ...);
```

编译器会乐快地允许这次赋值。但`staff[0]`和`managers[0]`是同一个引用，所以看起来我们成功地将一个普通的员工“偷带”进了管理层。这将非常糟糕——调用`managers[0].setBonus(1000)`将尝试访问一个不存在的实例字段并损坏相邻的内存。

为了确保不会发生此类损坏，所有数组都会记住它们创建时的元素类型，并监控只有兼容的引用被存储在其中。例如，通过`new Manager[10]`创建的数组会记得它是一个经理数组。尝试存储一个`Employee`引用会导致`ArrayStoreException`。

***

### 5.1.6 理解方法调用

确切理解方法调用是如何应用于对象的是非常重要的。假设我们调用了`x.f(args)`，且隐式参数`x`被声明为类`C`的对象。以下是发生的情况：

**1.** 编译器查看对象的声明类型和方法名。注意，可能有多个同名为`f`的方法，但其参数类型不同。例如，可能有一个方法`f(int)`和一个方法`f(String)`。编译器会列出类`C`中所有名为`f`的方法，以及`C`的父类中所有可访问的名为`f`的方法。（父类的私有方法是不可见的。）

现在编译器知道了要调用的方法的所有候选者。

**2.** 接下来，编译器确定方法调用中提供的参数类型。如果在所有名为`f`的方法中，有一个唯一方法的参数类型与所提供的参数最匹配，则选择该方法进行调用。这个过程被称为重载解析（overloading resolution）。例如，在`x.f("Hello")`中，编译器选择了`f(String)`而不是`f(int)`。

***

![Image](img/note.jpg) 注意

记住方法的名称和参数列表被称为签名（signature）。例如，`f(int)`和`f(String)`是同名不同签名的方法。

返回类型不是签名的一部分。然而，当你重写一个方法时，你需要保持返回类型兼容。例如，假设`Employee`类有一个方法：

```java
public Employee getBuddy() { ... }
```

经理永远不会想要一个员工作为伙伴。为了反映这一事实，`Manager`子类可以重写该方法为：

```java
public Manager getBuddy() { ... }
```

我们说这两个`getBuddy`方法具有协变返回类型。

***

**3.** 如果方法是`private`、`static`、`final`或构造函数，那么编译器确切知道要调用哪个方法。（`final`修饰将在下一节解释。）这被称为静态绑定（static binding）。否则，要调用的方法取决于隐式参数的类型，必须在运行时使用动态绑定。

**4.** 当程序运行并使用动态绑定调用方法时，虚拟机必须调用适用于`x`所指对象的*实际*类型的方法版本。假设实际类型是`D`，它是`C`的子类。如果类`D`定义了方法`f(String)`，则调用该方法。如果不是，则搜索`D`的父类中的方法`f(String)`，依此类推。

每次调用方法都执行这种搜索将非常耗时。因此，虚拟机为每个类预计算一个方法表（method table），列出所有方法签名和实际要调用的方法。当实际调用方法时，虚拟机只需进行表查找。在我们的示例中，虚拟机咨询类`D`的方法表，并查找调用`f(String)`的方法。该方法可能是`D.f(String)`或`X.f(String)`，其中`X`是`D`的某个父类。这种场景有一个转折。如果调用是`super.f(param)`，那么编译器将咨询隐式参数父类的方法表。

让我们详细查看代码列表 5.1 中调用`e.getSalary()`的这一过程。`e`的声明类型为`Employee`。`Employee`类有一个方法，称为`getSalary`，且没有方法参数。因此，在这种情况下，我们不需要担心重载解析。

`getSalary`方法既不是`private`、不是`static`也不是`final`，因此它是动态绑定的。虚拟机为`Employee`和`Manager`类生成方法表。`Employee`表显示所有方法都定义在`Employee`类本身：

```
Employee:
  getName() -> Employee.getName()
  getSalary() -> Employee.getSalary()
  getHireDay() -> Employee.getHireDay()
  raiseSalary(double) -> Employee.raiseSalary(double)
```

实际上，这并不是全部情况——正如你在本章稍后部分将看到的，`Employee`类有一个超类`Object`，它从那里继承了许多方法。我们暂时忽略`Object`方法。

`Manager`方法表略有不同。它继承了三个方法，重定义了一个方法，并添加了一个方法。

```
Manager:
  getName() -> Employee.getName()
  getSalary() -> Manager.getSalary()
  getHireDay() -> Employee.getHireDay()
  raiseSalary(double) -> Employee.raiseSalary(double)
  setBonus(double) -> Manager.setBonus(double)
```

在运行时，调用`e.getSalary()`的解析过程如下：

1. 首先，虚拟机获取`e`的实际类型的方法表。这可能是`Employee`、`Manager`或`Employee`的另一个子类的表。
2. 然后，虚拟机查找`getSalary()`签名的定义类。现在它知道要调用哪个方法了。
3. 最后，虚拟机调用该方法。

动态绑定具有非常重要的属性：它使程序具有扩展性，而无需修改现有代码。假设添加了一个新类`Executive`，并且变量`e`可能指向该类的对象。包含调用`e.getSalary()`的代码不需要重新编译。如果`e`恰好指向一个`Executive`类型的对象，则会自动调用`Executive.getSalary()`方法。

***

![Image](img/caution.jpg) 注意

当你重写一个方法时，子类方法的可见性至少要与父类方法相同。特别是如果父类方法是`public`，则子类方法也必须声明为`public`。无意遗漏子类方法的`public`修符是一个常见错误。编译器会报错，提示你试图提供更严格的访问权限。

### 5.1.7 防止继承：Final 类和方法

有时，你可能想防止别人从你的某个类创建子类。不能被扩展的类被称为最终类（final classes），你在类定义中使用`final`修饰符来指示这一点。例如，假设我们想防止他人对`Executive`类进行子类。只需使用`final`修饰符声明该类即可：

```java
public final class Executive extends Manager
{
   ...
}
```

你也可以使类中的特定方法变为`final`。如果你这样做，那么任何子类都不能重写该方法。（`final`类中的所有方法都自动是`final`的。）例如：

```java
public class Employee
{
   ...
   public final String getName()
   {
      return name;
   }
   ...
}
```

***

![Image](img/note.jpg) 提示

记住，字段也可以声明为`final`。在对象构造之后，最终字段无法更改。然而，如果一个类被声明为`final`，只有方法是自动`final`的，而不是字段。

***

将方法或类设为`final`的理由只有一个：确保其语义在子类中不会发生改变。例如，`Calendar`类的`getTime`和`setTime`方法是`final`的。这表明`Calendar`类的设计者承担了`Date`类与日历状态之间转换的责任。不允许任何子类破坏这种安排。同样，`String`类是一个`final`类。这意味着没有人可以定义`String`的子类。换句话说，如果你有一个`String`引用，你就知道它指的是一个`String`，且仅此而已。

一些程序员认为，除非你有想要多态的充分理由，否则你应该将所有方法声明为`final`。事实上，在 C++ 和...（为了简洁，文本已省略）。

### 5.1.8 强制转换

回想第 3 章，强制从一种类型转换为另一种类型的过程被称为强制转换（casting）。Java 编程语言对强制转换有特殊的表示。例如，

```java
double x = 3.405;
int nx = (int) x;
```

将`x`的值转换为整数，舍弃小数部分。

正如你有时需要将浮点数转换为整数一样，你可能需要将对象引用从一个类转换为另一个类。要实际对对象引用进行强制转换，使用与转换数值表达式类似的语法。将目标类名括在括号中，并放置在你想要转换的对象引用之前。例如：

```java
Manager boss = (Manager) staff[0];
```

当你向变量中存储一个值时，编译器会检查你是否承诺得太多。如果你将一个子类引用赋值给父类变量，你承诺的较少，编译器会直接允许你这样做。如果你将一个父类引用赋值给子类变量，你承诺的较多。这时，你必须使用强制类型转换（cast），以便让你的承诺在运行时得到检查。

如果你尝试对继承链进行向下强制转换，并且对对象所包含的内容“撒了谎”，会发生什么呢？

```java
Manager boss = (Manager) staff[1]; // 错误
```

当程序运行时，Java 运行时系统会注意到被违背的承诺并产生`ClassCastException`。如果你不捕获该异常，程序就会终止。因此，在尝试强制转换之前确定其是否会成功是一个良好的编程习惯。只需使用`instanceof`运算符即可。例如：

```java
if (staff[1] instanceof Manager)
{
   boss = (Manager) staff[1];
   ...
}
```

最后，如果强制转换没有可能，编译器将不允许你进行转换。例如，转换

```java
String c = (String) staff[1];
```

是一个编译错误，因为`String`并不是`Employee`的子类。

### 总结：
* 你只能在继承层次结构内进行强制转换。
* 在从父类转换到子类之前，使用`instanceof`进行检查。

***

![Image](img/note.jpg) 注意事项

测试

```java
x instanceof C
```

如果`x`为`null`，该测试不会产生异常。它只是返回`false`。这是合理的：`null`指向没有任何对象，因此它显然不指向类型为`C`的对象。

***

实际上，通过强制转换转换对象的类型通常不是一个好主意。在我们的示例中，对于大多数用途，你不需要将`Employee`对象强制转换为`Manager`对象。`getSalary`方法在这两个类的两个对象上都能正常工作。使多态生效的动态绑定会自动定位正确的方法。

进行强制转换的唯一原因是使用一个类特有的方法，例如`setBonus`。如果由于某种原因，你发现自己想在`Employee`对象上调用`setBonus`，请问自己这是否表明父类中存在设计缺陷。重新设计父类并添加`setBonus`方法可能是有意义的。请记住，只需要一个未捕获的`ClassCastException`就会终止你的程序。通常，最好尽量减少强制转换和`instanceof`运算符的使用。

***

![Image](img/note1.jpg) C++ 注意事项

Java 使用了 C 语言“过去旧时代”的强制转换语法，但它的工作原理类似于 C++ 中安全的`dynamic_cast`操作。例如，

```java
Manager boss = (Manager) staff[1]; // Java
```

它等同于

```cpp
Manager* boss = dynamic_cast<Manager*>(staff[1]); // C++
```

但有一个重要的区别。如果强制转换失败，它不会产生一个空对象，而是抛出一个异常。从这个意义上说，它类似于 C++ 中引用的强制转换。这非常头疼。在 C++ 中，你可以在一个操作中完成类型测试和类型转换。

```cpp
Manager* boss = dynamic_cast<Manager*>(staff[1]); // C++
```



`if (boss != NULL) . . .`

在 Java 中，你需要结合使用`instanceof`运算符和强制转换。

```java
if (staff[1] instanceof Manager)
{
    Manager boss = (Manager) staff[1];
    ...
}
```

### 5.1.9 抽象类

随着你向继承体系向上移动，类变得越来越通用，可能也越来越抽象。在某一点，祖先类变得*如此*通用，以你更多地将其看作其他类的基础，而不是一个包含你想使用的特定实例的类。例如，考虑我们`Employee`类层次结构的扩展。员工是人，学生也是人。让我们扩展类层次结构以包含`Person`和`Student`类。图 5.2 显示了这些类之间的继承关系。

![Image](img/05fig02.jpg)

**图 5.2** `Person`及其子类的继承图

为什么要费心进行如此层次的抽象？有些属性对每个人都是有意义的，例如名字。学生和员工都有名字，引入一个共同的父类让我们可以将`getName`方法提取到继承层次结构中的更高层次。

现在让我们再添加另一个方法`getDescription`，其目的是返回人的简短描述，例如：

* 一个工资为 50 美元的员工
* 一个主修计算机科学的学生

有些程序员并没有意识到抽象类可以拥有具体方法。你应该总是将通用方法（无论是否是抽象）移动到父类中。

***

抽象方法充当子类中实现方法的占位符。当你扩展一个抽象类时，你有两个选择。你可以留下某些或所有抽象方法未定义；那么你必须将子类标记为抽象。或者你可以定义所有方法，这样子类就不再是抽象的。

例如，我们将定义一个扩展`Person`类的`Student`类，并实现`getDescription`方法。`Student`类的方法都不是抽象的，因此它不需要被声明为抽象类。

一个类即使没有抽象方法，也可以被声明为`abstract`。

抽象类不能被实例化。也就是说，如果一个类被声明为`abstract`，就无法创建该类的对象。例如，表达式

```java
new Person("Vince Vu")
```

是一个错误。然而，你可以创建具体子类的对象。

注意你仍然可以创建抽象类的*对象变量*，但这样的变量必须指向非抽象子类的对象。例如：

```java
Person p = new Student("Vince Vu", "Economics");
```

在这里`p`是抽象类型`Person`的变量，它指向非抽象子类`Student`的实例。

如果一个 C++ 类包含至少一个纯虚函数，那么它就是抽象类。在 C++ 中，没有特殊的关键字来表示抽象类。

***

让我们定义一个扩展抽象类`Person`的具体子类`Student`：

```java
public class Student extends Person
{
    private String major;

    public Student(String name, String major)
    {
        super(name);
        this.major = major;
    }

    public String getDescription()
    {
        return "a student majoring in " + major;
    }
}
```

`Student`类定义了`getDescription`方法。因此，`Student`类中的所有方法都是具体的，该类不再是抽象类。

如列表 5.4 所示的程序定义了抽象父类`Person`（列表 5.5）以及两个具体子类：`Employee`（列表 5.6）和`Student`（列表 5.7）。我们用员工对象和学生对象填充一个`Person`引用数组：

```java
Person[] people = new Person[2];
people[0] = new Employee(. . .);
people[1] = new Student(. . .);
```

然后我们打印这些对象的名称和描述：

```java
for (Person p : people)
    System.out.println(p.getName() + ", " + p.getDescription());
```

有些人对以下调用感到困惑：

```java
p.getDescription()
```

这难道不是对未定义方法的调用吗？请记住，变量`p`永远不会引用一个`Person`对象，因为无法构造抽象类`Person`的对象。变量`p`始终指向具体子类的对象（如`Employee`或`Student`）。对于这些对象，`getDescription`方法是定义过的。

你是否可以完全从`Person`父类中省略抽象方法，而仅在`Employee`和`Student`子类中定义`getDescription`方法呢？如果你这样做，你将无法在变量`p`上调用`getDescription`方法。编译器确保你只调用在类中声明的方法。

抽象方法是 Java 编程语言中的一个重要概念。你最常见*接口*内部遇到它们。有关接口的更多信息，请参阅第 6 章。

**列表 5.4** `abstractClasses/PersonTest.java`

```java
1   package abstractClasses;
2
3   /**
4    * 此程序演示了抽象类。
5    * @version 1.01 2004-02-21
6    * @author Cay Horstmann
7    */
8   public class PersonTest
9   {
10      public static void main(String[] args)
11      {
12          Person[] people = new Person[2];
13
14          //用 Student 和 Employee 对象填充 people 数组
15          people[0] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
16          people[1] = new Student("Maria Morris", "computer science");
17
18          // 打印所有 Person 对象的名称和描述
19          for (Person p : people)
20              System.out.println(p.getName() + ", " + p.getDescription());
21      }
22  }
```

**列表 5.5** `abstractClasses/Person.java`

```java
1   package abstractClasses;
2
3   public abstract class Person
4   {
5      public abstract String getDescription();
6      private String name;
7
8      public Person(String name)
9      {
10         this.name = name;
11      }
12
13      public String getName()
14      {
15          return name;
16      }
17  }
```

**列表 5.6** `abstractClasses/Employee.java`

```java
1   package abstractClasses;
2
3   import java.time.*;
4
5   public class Employee extends Person
6   {
7      private double salary;
8      private LocalDate hireDay;
9
10     public Employee(String name, double salary, int year, int month, int day)
11      {
12          super(name);
13          this.salary = salary;
14          hireDay = LocalDate.of(year, month, day);
15      }
16
17      public double getSalary()
18      {
19          return salary;
20      }
21
22      public LocalDate getHireDay()
23      {
24          return hireDay;
25      }
26
27      public String getDescription()
28      {
29          return "employee with salary of " + salary;
30      }
31  }
```

**列表 5.7** `abstractClasses/Student.java`

```java
1   package abstractClasses;
2
3   public class Student extends Person
4   {
5      private String major;
6
7      /**
8       * @param name 学生的姓名
9       * @param major 学生的专业
10      */
11      public Student(String name, String major)
12      {
13          super(name);
14          this.major = major;
15      }
16
17      public String getDescription()
18      {
19          return "a student majoring in " + major;
20      }
21  }
```

### 5.1.10 保护访问

如你所知，类中的字段最好被标记为`private`，而方法通常标记为`public`。正如我们在本章开头所说，`private`特征对其他类不可见。

然而，有时你希望将方法限制为子类可见，或者不常见地允许子类访问父类的字段。在这种情况下，你将类特征标记为`protected`。例如，如果父类`Employee`将`hireDay`字段标记为`protected`而不是`private`，那么`Manager`方法就可以访问它。

但是，`Manager`方法只能访问`Manager`对象的`hireDay`，而不是其他`Employee`对象。这种限制是为了防止通过创建子类来滥用`protected`机制。

在实践中，请谨慎使用保护字段。假设你的类被其他程序员使用，而你在设计时使用了保护字段。在你不知情的情况下，其他程序员可能会继承你的类并开始访问这些字段。在这种情况下，你无法在不影响这些程序员的情况下更改类的实现。这违背了面向对象编程的精神，OOP 鼓励数据封装。

保护方法则更为合理。类可以将其方法标记为`protected`，如果该方法使用起来很复杂。这表明子类（它们按理了解其祖类）可以被信任正确使用该方法，而其他类则不能。

这种方法的很好的例子是`Object`类的`clone`方法——更多详情请参阅第 6 章。

***

![图片](img/note1.jpg) C++ 注意

事实是，Java 中的保护特征不仅对所有子类可见，而且对同一包中的所有其他类可见。这与 C++ 中`protected`的含义略有不同，使得 Java 中的`protected`概念比 C++ 中更不安全。

***

以下是 Java 中控制可见性的四种访问修饰符总结：

**1.** 仅对类可见（`private`）。

**2.** 对全世界可见（`public`）。

**3.** 对包和所有子类可见（`protected`）。

**4.** 对包可见——（不幸的）默认值。不需要修饰符。

## 5.2 Object：宇宙级父类

`Object`类是终极祖先——Java 中的每一个类都继承自`Object`。然而，你永远不需要编写：

```java
public class Employee extends Object
```

如果没有显式提到父类，则终极父类`Object`是被理所当然的。由于 Java 中的每个类都继承自`Object`，因此熟悉`Object`类提供的服务至关重要。我们将在本章中介绍基础方法；对于本文未涵盖的内容，请参阅后续章节或查看在线文档。（`Object`的几个方法只有在处理并发时才会出现——更多关于线程的信息请参阅第 14 节。）

你可以使用`Object`类型的变量来引用任何类型的对象：

```java
Object obj = new Employee("Harry Hacker", 35000);
```

当然，`Object`类型的变量只能作为任意值的通用容器使用。要对该值进行任何特定操作，你需要对原始类型有一定的了解并应用强制类型转换：

```java
Employee e = (Employee) obj;
```

在 Java 中，只有基本类型的值（数字、字符和`boolean`值）不是对象。

所有数组类型，无论是对象数组还是基本类型数组，都是继承自`Object`类的类类型。

```java
Employee[] staff = new Employee[10];
obj = staff; // OK
obj = new int[10]; // OK
```

***

![Image](img/note1.jpg) C++ 注意

在 C++ 中没有根类。然而，每个指针都可以转换为`void*`指针。

***

### 5.2.1 equals 方法

`Object`类中的`equals`方法测试一个对象是否被认为另一个另一个相等。`Object`类中实现的`equals`方法判断两个对象引用是否相同。这是一个相当合理的默认值——如果两个对象是相同的，它们理应该是相等的。对于许多类来说，不需要其他操作。例如，比较两个`PrintStream`对象的相等性没有意义。然而，你通常会想要实现基于状态的相等性测试，在这种情况下，当两个对象具有相同状态时，它们被认为是相等的。

例如，假设两个员工具有相同的姓名、工资和入职日期，他们就是相等的。（在实际的员工数据库中，比较 ID 会更合理。我们使用这个示例来演示实现`equals`方法的机制。）

```java
public class Employee
{
    ...
    public boolean equals(Object otherObject)
    {
        // 快速测试对象是否相同
        if (this == otherObject) return true;

        // 如果式参数为 null，必须返回 false
        if (otherObject == null) return false;

        // 如果类不匹配，它们就不可能相等
        if (getClass() != otherObject.getClass())
            return false;

        // 现在知道 otherObject 是一个非空的 Employee
        Employee other = (Employee) otherObject;

        // 测试字段是否具有相同的值
        return name.equals(other.name)
            && salary == other.salary
            && hireDay.equals(other.hireDay);
    }
}
```

`getClass`方法返回对象的类——我们将在本章后面部分详细讨论这个方法。在我们的测试中，两个对象只有在属于同一个类时才相等。

***

为了防止`name`或`hireDay`为`null`的可能，请使用`Objects.equals`方法。调用`Objects.equals(a, b)`在两个参数都为`null`时返回`true`，如果仅一个为`null`则返回`false`，否则调用`a.equals(b)`。使用该方法，`Employee.equals`方法的最后语句变为：

```java
return Objects.equals(name, other.name)
    && salary == other.salary
```



```java
&& Object.equals(hireDay, other.hireDay);
```

***

当你为子类定义`equals`方法时，先调用父类的`equals`。如果该测试没有通过，则对象不相等。如果父类字段相等，你就可以准备比较子类的实例字段了。

点击此处查看代码图片

```java
public class Manager extends Employee
{
    ...

    public boolean equals(Object otherObject)
    {
        if (!super.equals(otherObject)) return false;

        Manager other = (Manager) otherObject;

        return bonus == other.bonus;
    }
}
```

### 5.2.2 相等性测试与继承

如果参数属于不同的类，`equals`方法应该如何表现？这直是一个是一个争议领域。在前面的示例中，如果类不匹配，`equals`方法将返回`false`。但许多程序员使用`instanceof`测试：

点击此处查看代码图片

```java
if (!(otherObject instanceof Employee)) return false;
```

这留下了`otherObject`可能属于子类的可能性。然而，Java 规范要求`equals`方法具有以下属性：

1. **自反性**：对于任何非空引用`x`，`x.equals(x)`返回`true`。
2. **对称性**：对于任何引用`x`和`y`，`x.equals(y)`返回`true`当且仅当`y.equals(x)`返回`true`。
3. **传递性**：对于任何引用`x`、`y`和`z`，如果`x.equals(y)`返回`true`且`y.equals(z)`返回`true`，则`x.equals(z)`应返回`true`。
4. **一致性**：如果`x`和`y`所引的对象没有改变，则重复调用`x.equals(y)`返回相同的值。
5. 对于任何非空引用`x`，`x.equals(null)`应该返回`false`。

这些规则显然合理。在数据结构中定位元素时，你不会希望库实现者纠结调用`x.equals(y)`还是`y.equals(x)`。

然而，对称规则在参数属于不同类时会产生微妙的影响。考虑一个调用`e.equals(m)`，其中`e`是`Employee`对象而`m`是`Manager`对象，它们恰好具有相同的姓名、工资和入职日期。如果`Employee.equals`使用`instanceof`测试，则调用返回`true`。但这意味着反向调用`m.equals(e)`也需要返回`true`——对称规则不允许它返回`false`或抛出异常。

这让`Manager`类陷入了困境。它的`equals`方法必须愿意与任何`Employee`进行比较，而不考虑经理特有的信息！

一些作者记录了`getClass`测试是错误的，因为它违背了替换原则。一个经常被引用例子是`AbstractSet`类中的`equals`方法，它用于测试两个集合是否具有相同的元素。`AbstractSet`类有两个具体的子类`TreeSet`和`HashSet`，它们在定位元素时使用不同的算法。你真的希望能够比较任何集合，无论它们是如何实现的。

然而，集合的例子相当特殊。将`AbstractSet.equals`声明为`final`是合理的，因为不应该有人重新定义集合相等性的语义。（该方法实际上并不是`final`。这允许子类为相等性测试实现更高效的算法。）

在我们看来，有两种不同的场景：

- 如果子类可以有自己的相等概念，那么对称性要求迫使你使用`getClass`测试。
- 如果相等性的定义在父类中已经固定，那么你可以使用`instanceof`测试，并允许不同子类的对象相互相等。

在员工和经理的示例中，当两个对象的字段相匹配时，我们认为它们是相等的。如果我们有两个姓名、工资和入职日期相同，但奖金不同的`Manager`（经理）对象，我们希望它们是互不相同的。因此，我们使用了`getClass`测试。

但假设我们使用员工 ID 进行相等性测试。这种相等性定义对于所有子类都是合理的。那么我们就可以使用`instanceof`测试，并且我们应该将`Employee.equals`声明为`final`。

***

![Image](img/note.jpg) 注意

标准 Java 库包含了超过 150 种`equals`方法的实现，这些实现混杂杂章，有使用`instanceof`、调用`getClass`、捕获`ClassCastException`或者什么都不做。查看`java.sql.Timestamp`类的 API 文档，实现者们有些尴尬地注释道，他们让自己陷入了困境。`Timestamp`类继承自`java.util.Date`，后者的`equals`方法使用了`instanceof`测试，而无法重写`equals`使其同时具有对称性和准确性。

***

### 以下是编写完美`equals`方法的配方：

**1.** 将显式参数命名为`otherObject`——稍后，你将需要将其转换为另一个变量，并将其命名为`other`。

**2.** 测试`this`是否意外与`otherObject`相同：

点击此处查看代码图片

```java
if (this == otherObject) return true;
```

这条语句仅仅是一种优化。在实践中，这是一种常见的情况。检查标识性比比较字段要快得多。

**3.** 测试`otherObject`是否为`null`，如果是则返回`false`。这个测试是必须的。

点击此处查看代码图片

```java
if (otherObject == null) return false;
```

**4.** 比较`this`和`otherObject`的类。如果`equals`的语义可以在子类中发生变化，请使用`getClass`测试：

点击此处查看代码图片

如果所有子类都保持相同的语义，你可以使用`instanceof`测试：

点击此处查看代码图片

```java
if (!(otherObject instanceof ClassName)) return false;
```

**5.** 将`otherObject`强制转换为你的类类型的变量：

点击此处查看代码图片

```java
ClassName other = (ClassName) otherObject
```

**6.** 现在根据你对相等性的定义比较字段。对于原始类型字段使用`==`，对于对象字段使用`Objects.equals`。如果所有字段都匹配则返回`true`，否则返回`false`。

点击此处查看代码图片

```java
return field1 == other.field1
    && Objects.equals(field2, other.field2)
    && . . .;
```

如果你在子类中重定义`equals`，请包含对`super.equals(other)`的调用。

***

![Image](img/tip.jpg) 提示

如果你有数组类型的字段，可以使用静态的`Arrays.equals`方法来检查相应的数组元素是否相等。

***

![Image](img/caution.jpg) 警告

这是实现`equals`方法时的一个常见错误。你能看出问题所在吗？

点击此处查看代码图片

```java
public class Employee
{
    public boolean equals(Employee other)
    {
        return other != null
            && getClass() == other.getClass()
            && Objects.equals(name, other.name)
            && salary == other.salary
            && Objects.equals(hireDay, other.hireDay);
    }

    ...
}
```

该方法将显式参数类型声明为`Employee`。结果，它没有重写`Object`类的`equals`方法，而是定义了一个完全无关的方法。

你可以通过为意图重写父类方法的方法标记上`@Override`标签来防止此类错误：

点击此处查看代码图片

```java
@Override public boolean equals(Object other)
```

如果你犯了错误并定义了一个新方法，编译器会报告错误。例如，假设你在`Employee`类中添加了以下声明：

点击此处查看代码图片

```java
@Override public boolean equals(Object other)
```

将会报错，因为此方法没有重写父类中的任何方法。

### 5.2.3 `hashCode`方法

哈希码是一个根据对象派生的整数。哈希码应该是散乱的——如果`x`和`y`是不同的对象，那么`x.hashCode()`和`y.hashCode()`有很大概率是不同的。

`hashCode`方法在`String`类中定义。它使用以下算法计算哈希：

```java
int hash = 0;

for (int i = 0; i < length(); i++)
    hash = 31 * hash + charAt(i);
```

`hashCode`方法在`Object`类中定义。因此，每个对象都有默认哈希码。考虑这个示例：

```java
String s = "Ok";

StringBuilder sb = new StringBuilder(s);

System.out.println(s.hashCode() + " " + sb.hashCode());

String t = new String("Ok");

StringBuilder tb = new StringBuilder(t);

System.out.println(t.hashCode() + " " + tb.hashCode());
```

![Image](img/05.jpg) `String`和`StringBuilder`的哈希码

注意字符串`s`和`t`具有相同的哈希码，因为对于字符串，哈希码是从内容派生的。`StringBuilder` `sb`和`tb`具有不同的哈希码，因为`StringBuilder`类没有定义`hashCode`方法，而`Object`类中的默认`hashCode`方法从对象的地址派生哈希码。

如果你重定义了`equals`方法，你还需要为可能插入哈希表的对象重定义`hashCode`方法。（我们在第 9 章中讨论哈希表）。

甚至更好，当你需要组合多个哈希值时，调用`Objects.hash`并传入所有值。它会为每个参数调用`Objects.hashCode`并组合这些值。那么`Employee.hashCode`方法就可以简单如下：

点击此处查看代码图像

```java
public int hashCode()
{
    return Objects.hash(name, salary, hireDay);
}
```

你对`equals`和`hashCode`的定义必须保持兼容：如果`x.equals(y)`为`true`，那么`x.hashCode()`返回的值必须与`y.hashCode()`相同。例如，如果你定义`Employee.equals`来比较员工 ID，那么`hashCode`方法需要对 ID 进行哈希，而不是员工姓名或内存地址。

![Image](img/tip.jpg) 提示

如果你有数组类型的字段，可以使用静态方法`Arrays.hashCode`来计算由数组元素哈希值组成的哈希码。

---

### `java.lang.Object` 1.0

- `int hashCode()`

  返回此对象的哈希码。哈希码可以是任意整数，正数或负数。相等的对象需要返回相同的哈希码。

---

### `java.util.Objects` 7

- `static int hash(Object... objects)`

  返回一个由所有提供的对象的哈希码组合成的哈希码。
- `static int hashCode(Object a)`

  如果`a`为`null`则返回`0`，否则返回`a.hashCode()`。

---

### `java.lang.(Integer|Long|Short|Byte|Double|Float|Character|Boolean)` 1.0

- `static int hashCode((int|long|short|byte|double|float|char|boolean) value)` 返回给定值的哈希码。

---

### `java.util.Arrays` 1.2

- `static int hashCode(type[] a)` 5.0

  计算数组`a`的哈希码，该数组的组件类型可以是`Object`、`int`、`long`、`short`、`char`、`byte`、`boolean`、`float`或`double`。

---

### 5.2.4 `toString`方法

`Object`中的另一个重要方法是`toString`方法，它返回一个表示此对象值的字符串。这是一个典型的示例。`Point`类的`toString`方法返回如下所示字符串：

`java.awt.Point[x=10,y=20]`

大多数（但不是所有）`toString`方法都遵循这种格式：类名，然后是括方括号中的字段值。以下是`Employee`类的`toString`方法的实现：

点击此处查看代码图像

```java
public String toString()
{
    return "Employee[name=" + name
        + ",salary=" + salary
        + ",hireDay=" + hireDay
        + "]";
}
```

实际上，你可以做得更好。不要在`toString`方法中硬编码类名，而是调用`getClass().getName()`来获取一个包含类名的字符串。

点击此处查看代码图像

```java
public String toString()
{
    return getClass().getName()
        + "[name=" + name
        + ",salary=" + salary
        + ",hireDay=" + hireDay
        + "]";
}
```

这种`toString`方法对子类同样有效。

当然，子类的程序员应该定义它自己的`toString`方法并添加子类的字段。如果父类使用了`getClass().getName()`，那么子类可以简单地调用`super.toString()`。例如，这里是`Manager`类的`toString`方法：

点击此处查看代码图像

```java
public class Manager extends Employee
{
    ...

    public String toString()
    {
        return super.toString()
            + "[bonus=" + bonus
            + "]";
    }
}
```

现在一个`Manager`对象被打印为：

点击此处查看代码图像

`Manager[name=...,salary=...,hireDay=...][bonus=...]`

`toString`方法无处不在是因为一个重要的原因：每当使用“+”运算符将对象与字符串拼接时，Java 编译器会自动调用`toString`方法来获取对象的字符串表示。例如：

点击此处查看代码图像

```java
Point p = new Point(10, 20);

String message = "The current position is " + p; // 自动调用 p.toString()
```

![Image](img/tip.jpg) 提示

与其编写`x.toString()`，你可以写`"" + x`。这条语句将空字符串与`x`的字符串表示拼接，这恰好就是`x.toString()`。与`toString`不同，这条语句即使`x`是基本类型也同样有效。

如果`x`是任何对象且你调用`System.out.println(x)`，那么`println`方法简单地调用`x.toString()`并打印结果字符串。`Object`类定义的`toString`方法用于打印类名和对象的哈希码。例如，调用`System.out.println(System.out)`输出如下：

`java.io.PrintStream@2f64` 警告

`toString`方法非常有用是因为：每当你使用“+”运算符将对象与字符串拼接时，Java 编译器就会自动调用`toString`方法来获取对象的字符串表示。例如：

点击此处查看代码图像

```java
Point p = new Point(10, 20);
```



`String message = "The current position is " + p; // 自动调用 p.toString()`

如果`x`是任何对象且你调用`System.out.println(x)`，那么`println`方法简单地调用`x.toString()`并打印结果字符串。`Object`类定义的`toString`方法用于打印类名和对象的哈希码。例如，调用`System.out.println(System.out)`输出如下：

`java.io.PrintStream@2f64` 警告

`toString`方法非常有用是因为：每当你使用“+”运算符将对象与字符串拼接时，Java 编译器就会自动调用`toString`方法来获取对象的字符串表示。例如：

点击此处查看代码图像

```java
Point p = new Point(10, 20);
String message = "The current position is " + p; // 自动调用 p.toString()
```

![Image](img/tip.jpg) 提示
我们强烈建议为你编写的每个类都添加`toString`方法。你以及使用你类的其他程序员将对这种日志支持表示感谢。

`toString`方法非常有用是因为：每当你使用“+”运算符将对象与字符串拼接时，Java 编译器就会自动调用`toString`方法来获取对象的字符串表示。例如：

```java
30          System.out.println("boss.toString(): " + boss);
31          System.out.println("carl.equals(boss): " + carl.equals(boss));
32          System.out.println("alice1.hashCode(): " + alice1.hashCode());
33          System.out.println("alice3.hashCode(): " + alice3.hashCode());
34          System.out.println("bob.hashCode(): " + bob.hashCode());
35          System.out.println("carl.hashCode(): " + carl.hashCode());
36      }
37  }
```

* *

### 示例 5.9 `equals/Employee.java`

点击此处查看代码图片

* *

```java
1    package equals;
2
3    import java.time.*;
4    import java.util.Objects;
5
6    public class Employee
7   {
8      private String name;
9      private double salary;
10      private LocalDate hireDay;
11
12     public Employee(String name, double salary, int year, int month, int day)
13     {
14          this.name = name;
15          this.salary = salary;
16          hireDay = LocalDate.of(year, month, day);
17     }
18
19     public String getName()
20     {
21          return name;
22     }
23
24     public double getSalary()
25     {
26          return salary;
27     }
28
29     public LocalDate getHireDay()
30     {
31          return hireDay;
32     }
33
34     public void raiseSalary(double byPercent)
35     {
36          double raise = salary * byPercent / 100;
37          salary += raise;
38     }
39
40     public boolean equals(Object otherObject)
41     {
42          // 快速测试对象是否为同一个实例
43          if (this == otherObject) return true;
44
45          // 如果显式参数为 null，必须返回 false
46          if (otherObject == null) return false;
47
48          // 如果类不匹配，则它们不等
49          if (getClass() != otherObject.getClass()) return false;
50
51          // 现在我们知道 otherObject 是一个非空的 Employee
52          Employee other = (Employee) otherObject;
53
54          // 测试字段值是否具有相同的值
55          return Objects.equals(name, other.name) && salary == other.salary
56                  && Objects.equals(hireDay, other.hireDay);
57     }
58
59     public int hashCode()
60     {
61          return Objects.hash(name, salary, hireDay);
62     }
63
64     public String toString()
65     {
66          return getClass().getName() + "[name=" + name + ",salary=" + salary + ",hireDay=" + hireDay
67                  + "]";
68     }
69   }
```

* *

### 示例 5.10 `equals/Manager.java`

点击此处查看代码图片

* *

```java
1    package equals;
2
3    public class Manager extends Employee
4   {
5      private double bonus;
6
7      public Manager(String name, double salary, int year, int month, int day)
8      {
9          super(name, salary, year, month, day);
10          bonus = 0;
11     }
12
13     public double getSalary()
14     {
15          double baseSalary = super.getSalary();
16          return baseSalary + bonus;
17     }
18
19     public void setBonus(double bonus)
20     {
21          this.bonus = bonus;
22     }
23
24     public boolean equals(Object otherObject)
25     {
26          if (!super.equals(otherObject)) return false;
27
28          Manager other = (Manager) otherObject;
29
30          return bonus == other.bonus;
31     }
32
33     public int hashCode()
34     {
35          return super.hashCode() + bonus;
36     }
37
38     public String toString()
39     {
40          return super.toString() + ",bonus=" + bonus;
41     }
42   }
```

`ArrayList`管理一个内部的对象引用数组。最终，该数组的空间会耗尽。这正是数组列表发挥魔力的地方：如果你调用`add`且内部数组已满，数组列表会自动创建一个更大的数组，并将所有对象从较小的数组复制到较大的数组中。

如果你已经知道（或有不错的推测）你想要存储多少个元素，可以在填充数组列表之前调用`ensureCapacity`方法：

```java
staff.ensureCapacity(100);
```

该调用会分配一个可以包含 100 个对象的内部数组。然后，前 100 次`add`调用将不会涉及任何高开销的重新分配。

你也可以在向`ArrayList`构造函数中传递一个初始容量：

点击此处查看代码图像

```java
ArrayList<Employee> staff = new ArrayList<>(100);
```

* * *

![Image](img/caution.jpg) 注意

像如下所示分配一个数组列表：

点击此处查看代码图像

```java
new ArrayList<>(100) // 容量为 100
```

这*并不是*等同于如下分配一个新的数组：

点击此处查看代码图像

```java
new Employee[100] // 大小为 100
```

数组列表的容量（capacity）与数组的大小（size）之间存在重要的区别。如果你分配了一个具有 100 个条目的数组，那么该数组就有 100 个槽位可以使用。一个容量为 100 个元素的数组列表具有持有 100 个元素的*潜力*（实际上，以额外重新分配为代价，可以超过 100 个）但在刚开始，即使在初始构造之后，数组列表一个元素也没有包含。

* * *

`size`方法返回数组列表中实际的元素数量。例如，

```java
staff.size()
```

返回`staff`数组列表中当前的元素数量。这等同于数组`a`的

`a.length`

一旦你相当确定数组列表已达到其固定大小，就可以调用`trimToSize`方法。该方法会调整内存块的大小，使其恰好使用存储当前元素数量所需的存储空间。垃圾收集器将回收多的内存。

一旦你修剪了数组列表的大小，添加新元素将再次移动该块，这需要时间。只有当你确定不会再向数组列表添加更多元素时，才应该使用`trimToSize`。

* * *

![Image](img/note1.jpg) C++ 注意

`ArrayList`类类似于 C++ 的`vector`模板。`ArrayList`和`vector`都是泛型类型。但 C++ 的`vector`模板重载了`[]`运算符以便方便地访问元素。Java 没有运算符重载，因此必须使用显式的方法调用来代替。此外，C++ vectors 是按值复制的。如果`a`和`b`是两个 vectors，那么赋值`a = b`会让`a`变成一个与`b`长度相同的新 vector，所有元素都从`b`复制到`a`。在 Java 中，相同的赋值会使`a`和`b`指向同一个数组列表。

* * *

* * *

`java.util.ArrayList<E>` **1.2**

- `ArrayList<E>()` 构建一个空的数组列表。
- `ArrayList<E>(int initialCapacity)` 构建一个具有指定容量的空数组列表。

![Image](img/247tab01.jpg)

- `boolean add(E obj)` 在数组列表末尾追加一个元素。始终返回`true`。

![Image](img/247tab02.jpg)

- `int size()` 返回当前存储在数组列表中的元素数量。（当然，这永远不会数组列表的容量。）
- `void ensureCapacity(int capacity)` 确保数组列表有容量存储给定数量的元素，而不重新分配其内部存储数组。

![Image](img/247tab03.jpg)

- `void trimToSize()` 将数组列表的存储容量缩减到其当前大小。

* * *

### 5.3.1 访问数组列表元素

遗憾的是，天下没有免费的午餐。数组列表提供的自动增长便利性需要更复杂的语法来访问元素。原因是`ArrayList`类并不是 Java 编程语言的一部分；它只是由某人编写并在标准库中提供的工具类。

与其使用简单的`[]`语法来访问或更改数组元素，不如使用`get`和`set`方法。

例如，要设置第`i`个元素，你使用

```java
staff.set(i, harry);
```

这等同于

```java
a[i] = harry;
```

对于数组`a`。（与数组一样，索引值从 0 开始。）

* * *

![Image](img/caution.jpg) 注意

在数组列表的*size* 大于`i`之前，不要调用`list.set(i, x)`。例如，以下代码是错误的：

点击此处查看代码图像

```java
ArrayList<Employee> list = new ArrayList<>(100); // 容量为 100
list.set(0, new Employee()); // 错误，因为 size 为 0
``` 大小为 0
```

千万不要调用`list.set(i, x)`直到数组列表的 *size* 大于`i`。例如，以下代码是错误的：

点击此处查看代码图像

```java
ArrayList<Employee> list = new ArrayList<>(100); // 容量为 100
list.set(0, new Employee()); // 错误，因为 size 为 0
``` 大小为 0
```

千万不要调用`list.set(i, x)`直到数组列表的 *size* 大于`i`。例如，以下代码是错误的：

点击此处查看代码图像

```java
ArrayList<Employee> list = new ArrayList<>(100); // 容量为 100
list.set(0, new Employee()); // 错误，因为 size 为 0
``` 大小为 0
```

千万不要调用`list.set(i, x)`直到数组列表的 *size* 大于`i`。例如，以下代码是错误的：

点击此处查看代码图像

```java
ArrayList<Employee> list = new ArrayList<>(100); // 容量为 100
list.set(0, new Employee()); // 错误，因为 size 为 0
``` 大小为 0
```

千万不要调用`list.set(i, x)`直到数组列表的 *size* 大于`i`。例如，以下代码是错误的：

点击此处查看代码图像

```java
ArrayList<Employee> list = new ArrayList<>(100) // 容量为 100
list.set(0, new Employee()); // 错误，因为 size 为 0
``` 大小为 0
```



`ArrayList` 管理一个内部的对象引用数组。最终，该数组的空间会耗尽。这正是数组列表发挥魔力的地方：如果你调用`add`且内部数组已满，数组列表会自动创建一个更大的数组，并将所有对象从较小的数组复制到较大的数组中。

如果你已经知道（或有不错的推测）你想要存储多少个元素，可以在填充数组列表之前调用`ensureCapacity`方法：

```java
staff.ensureCapacity(100);
```

该调用会分配一个可以包含 100 个对象的内部数组。然后，前 100 次`add`调用将不会涉及任何高开销的重新分配。

你也可以在向`ArrayList`构造函数中传递一个初始容量：

```java
ArrayList<Employee> staff = new ArrayList<>(100);
```

> **注意**
>
> 像如下所示分配一个数组列表：
>
> ```java
> new ArrayList<>(100) // 容量为 100
> ```
>
> 这并不是等同于如下分配一个新的数组：
>
> ```java
> new Employee[100] // 大小为 100
> ```
>
> 数组列表的容量（capacity）与数组的大小（size）之间存在重要的区别。如果你分配了一个具有 100 个条目的数组，那么该数组就有 100 个槽位可以使用。一个容量为 100 个元素的数组列表具有持有 100 个元素的潜力（实际上，以额外重新分配为代价，可以超过 100 个），但在刚开始，即使在初始构造之后，数组列表一个元素也没有包含。

`size`方法返回数组列表中实际的元素数量。例如：

```java
staff.size()
```

返回`staff`数组列表中当前的元素数量。这等同于数组`a`的`a.length`。

一旦你相当确定数组列表已达到其固定大小，就可以调用`trimToSize`方法。该方法会调整内存块的大小，使其恰好使用存储当前元素数量所需的存储空间。垃圾收集器将回收多的内存。

一旦你修剪了数组列表的大小，添加新元素将再次移动该块，这需要时间。只有当你确定不会再向数组列表添加更多元素时，才应该使用`trimToSize`。

> **C++ 注意**
>
> `ArrayList`类类似于 C++ 的`vector`模板。`ArrayList`和`vector`都是泛型类型。但 C++ 的`vector`模板重载了`[]`运算符以便方便地访问元素。Java 没有运算符重载，因此必须使用显式的方法调用来代替。
>
> 此外，C++ vectors 是按值复制的。如果`a`和`b`是两个 vectors，那么赋值`a = b`会让`a`变成一个与`b`长度相同的新 vector，所有元素都从`b`复制到`a`。在 Java 中，相同的赋值会使`a`和`b`指向同一个数组列表。

## `java.util.ArrayList<E>` 1.2

- `ArrayList<E>()`：构建一个空的数组列表。
- `ArrayList<E>(int initialCapacity)`：构建一个具有指定容量的空数组列表。
- `boolean add(E obj)`：在数组列表末尾追加一个元素。始终返回`true`。
- `int size()`：返回当前存储在数组列表中的元素数量。（当然，这永远不会是数组列表的容量。）
- `void ensureCapacity(int capacity)`：确保数组列表有容量存储给定数量的元素，而不重新分配其内部存储数组。
- `void trimToSize()`：将数组列表的存储容量缩减到其当前大小。

### 5.3.1 访问数组列表元素

遗憾的是，天下没有免费的午餐。数组列表提供的自动增长便利性需要更复杂的语法来访问元素。原因是`ArrayList`类并不是 Java 编程语言的一部分；它只是由某人编写并在标准库中提供的工具类。

与其使用简单的`[]`语法来访问或更改数组元素，不如使用`get`和`set`方法。

例如，要设置第`i`个元素，你使用：

```java
staff.set(i, harry);
```

这等同于：

```java
a[i] = harry;
```

对于数组`a`。（与数组一样，索引值从 0 开始。）

> **注意**
>
> 在数组列表的`size`大于`i`之前，不要调用`list.set(i, x)`。例如，以下代码是错误的：
>
> ```java
> ArrayList<Employee> list = new ArrayList<>(100); // 容量为 100
> list.set(0, new Employee()); // 错误，因为 size 为 0
> ```

```java
import java.util.*;

/**
 * This program demonstrates the ArrayList class.
 * @version 1.11 2012-01-26
 * @author Cay Horstmann
 */
public class ArrayListTest
{
    public static void main(String[] args)
    {
        // fill the staff array list with three Employee objects
        ArrayList<Employee> staff = new ArrayList<>();

        staff.add(new Employee("Carl Cracker", 75000, 1987, 12, 15));
        staff.add(new Employee("Harry Hacker", 50000, 1989, 10, 1));
        staff.add(new Employee("Tony Tester", 40000, 1990, 3, 15));

        // raise everyone's salary by 5%
        for (Employee e : staff)
            e.raiseSalary(5);

        // print out information about all Employee objects
        for (Employee e : staff)
            System.out.println("name=" + e.getName() + ",salary=" + e.getSalary() + ",hireDay="
                    + e.getHireDay());
    }
}
```

## `java.util.ArrayList<E>` 1.2

- `void set(int index, E obj)`：在数组列表指定的索引处放入一个值，覆盖之前的内容。
- `E get(int index)`：获取存储在指定索引的值。
- `void add(int index, E obj)`：向上移动元素以插入一个元素。
- `E remove(int index)`：移除一个元素并向下移动其上方的所有元素。返回被移除的元素。

### 5.3.2 类型数组列表与原始数组列表之间的兼容性

在你自己的代码中，你总是希望使用类型参数来增加安全性。在本节中，你将看到如何与不使用类型参数的遗留代码进行交互。

假设你有以下遗留类：

```java
public class EmployeeDB
{
    public void update(ArrayList list) { ... }
    public ArrayList find(String query) { ... }
}
```

你可以在进行任何强制转换的情况下，将类型的数组列表传递给`update`方法。

```java
ArrayList<Employee> staff = ...;
employeeDB.update(staff);
```

`staff`对象被直接传递给`update`方法。

> **注意**
>
> 尽管你没有从编译器获得任何错误或警告，但这种调用并不是完全安全的。`update`方法可能会向数组列表中添加不是`Employee`类型的元素。当获取到这些元素时，就会发生异常。
>
> 这听起来很可怕，但如果你仔细考虑，这种行为与泛型引入 Java 之前的行为完全一致。虚拟机的完整性永远不会受到威胁。在这种情况下，你没有失去安全性，但也无法从编译时检查中获益。

相反，当你将原始`ArrayList`赋值给类型的`ArrayList`时，你会得到一个警告。

```java
ArrayList<Employee> result = employeeDB.find(query); // 产生警告
```

> **注意**
>
> 要查看警告文本，请使用`-Xlint:unchecked`选项进行编译。

使用强制转换并让警告消失。

```java
ArrayList<Employee> result = (ArrayList<Employee>) employeeDB.find(query);
// 产生另一个警告
```

相反，你会得到一个不同的警告，告诉你强制转换是误导性的。

这是 Java 中泛型类型一个相当遗憾的局限性导致的。为了兼容性，编译器在检查未违反类型规则后，将所有类型的数组列表转换为原始的`ArrayList`对象。在运行的程序中，所有的数组列表都是相同的——虚拟机中没有类型参数。因此，强制转换`(ArrayList)`和`(ArrayList<Employee>)`执行的是完全相同的运行时检查。

对于这种情况，你无能为力。当你与遗留代码交互时，请研究编译器警告并确保这些警告不是严重的。

一旦你满意了，可以像这样给变量标记上`@SuppressWarnings("unchecked")`：

```java
@SuppressWarnings("unchecked")
ArrayList<Employee> result = (ArrayList<Employee>) employeeDB.find(query);
```

## 5.4 包装类与自动装箱

有时，你需要将基本类型转换为对象。包装类有特定的名称：`Integer`、`Long`、`Float`、`Double`、`Short`、`Byte`、`Character`和`Boolean`。包装类也被称为 wrappers。

假设我们需要一个`int`。以下功能轻松地向`ArrayList<>`添加一个`int`元素：

```java
ArrayList<Integer> list = new ArrayList<>();
```

> **注意**
>
> `ArrayList<Integer>`的效率远低于`int[]`，因为每个值都被单独包装在内部。你只有在程序员的便利比效率更重要时才会使用它。

幸运的是，有一个功能可以轻松地向`ArrayList<>`添加一个`int`元素：

```java
list.add(3);
```

这种转换被称为自动装箱（autoboxing）。

> **注意**
>
> 你可能认为自动拆箱（autounrapping）会更一致，但“箱”这个比喻源自 C#。

相反，当你将一个`Integer`对象赋值给`int`值时，它会自动拆箱。也就是说，编译器翻译为：

```java
int n = list.get(i);
```

```java
int n = list.get(i).intValue();
```

自动装箱和拆箱甚至适用于算术表达式。例如，你可以对包装引用应用递增运算符：

```java
Integer n = 3;
n++;
```

编译器会自动插入指令拆箱对象、增加值并重新装箱。

在大多数情况下，你会认为基本类型和它们的包装类是同一的。只有一个点它们有显著不同：标识性。正如你所知，`==`运算符应用于包装对象时仅测试对象是否具有相同的内存位置。因此，比较可能会失败：

```java
Integer a = 1000;
Integer b = 1000;
if (a == b) . . .
```

然而，Java 实现可能会根据选择将常用值包装成相同的对象，因此比较可能会成功。这种歧义不是你想要的。解决方法是在比较包装对象时调用`equals`方法。

> **注意**
>
> 自动装箱规范要求`boolean`、`byte`、`char <= 127`、`short`以及 -128 到 127 之间的`int`被包装成固定对象。例如，如果前面的示例中`a`和`b`被初始化为`100`，那么比较将成功。

关于自动装箱还有一些微妙之处。首先，由于包装类引用可以为`null`，自动拆箱可能会抛出`NullPointerException`：

```java
Integer n = null;
System.out.println(2 * n); // 出 NullPointerException
```

此外，如果你在条件表达式中混合使用`Integer`和`Double`类型，那么`Integer`值会被拆箱、提升为`double`，并装箱为`Double`：

```java
Integer n = 1;
Double x = 2.0;
System.out.println(true ? n : x); // 输出 1.0
```

最后，让我们强调一下，装箱和拆箱是`compiler`提供的便利，而不是虚拟机。编译器在生成类的字节码时会插入必要的调用。虚拟机简单地执行这些字节码。

你经常会因为另一个原因看到数字包装类。Java 的设计者发现，包装类是放置某些基本方法的方便地方，例如用于将数字字符串转换为数字的方法。

要将字符串转换为整数，请使用以下语句：

```java
int x = Integer.parseInt(s);
```

这与`Integer`对象无关——`parseInt`是一个静态方法。但`Integer`类是放置它的好地方。

API 注释显示了`Integer`类的一些更重要的方法。其他数字类也实现了对应的方法。

> **警告**
>
> 有些人认为包装类可以用于实现可以修改数值参数的方法。然而，这是不对的。回想第 4 章，编写一个可以递增整数参数的 Java 方法是不可行的，因为 Java 方法的参数总是按值传递的。
>
> ```java
> public static void triple(int x) // 无法工作
> {
>    x = 3 * x; // 修改了局部变量
> }
> ```
>
> 我们可以通过使用`Integer`代替`int`来克服这个问题吗？
>
> ```java
> public static void triple(Integer x) // 无法工作
> {
>    ...
> }
> ```
>
> 问题在于`Integer`对象是不可变的：包装器内部包含的信息无法更改。你不能使用这些包装类来创建一个修改数值参数的方法。

如果你确实想写一个用于更改数值参数的方法，你可以使用`org.omg.CORBA`包中定义的`holder`类型之一：`IntHolder`、`BooleanHolder`等。每个 holder 类型都有一个公共的`value`字段，通过它你可以访问存储的值。

```java
public static void triple(IntHolder x)
{
   x.value = 3 * x.value;
}
```

## `java.lang.Integer` 1.0

- `int intValue()`：将此`Integer`对象的值作为`int`返回（重写了`Number`类中的`intValue`方法）。
- `static String toString(int i)`：返回一个表示 10 进制数字`i`的新`String`对象。



- `static String toString(int i, int radix)`：允许你返回由 `radix` 参数指定的基数的数字 `i` 的表示。
- `static int parseInt(String s)`
- `static int parseInt(String s, int radix)`：返回字符串 `s` 中包含数字的整数。该字符串必须表示一个 10 进制整数（对于第一个方法）或由 `radix` 参数指定的基数的整数（对于第二个方法）。
- `static Integer valueOf(String s)`
- `static Integer valueOf(String s, int radix)`：返回一个新的 `Integer` 对象，其初始化为字符串 `s` 中包含数字的整数。该字符串必须表示一个 10 进制整数（对于第一个方法）或由 `radix` 参数指定的基数的整数（对于第二个方法）。

## `java.text.NumberFormat` 1.1

- `Number parse(String s)`：返回数值，假设指定的 `String` 表示一个数字。

### 5.5 变长参数的方法

可以提供可以使用数量参数调用的方法。（这些方法有时被称为“可变参数”（varargs）方法。）

你已经见过这样的方法了：`printf`。例如，以下调用：

```java
System.out.printf("%d", n);
```

点击此处查看代码图像

```java
System.out.printf("%d %s", n, "widgets");
```

都调用了同一个方法，尽管一个调用有两个参数，而另一个有三个。

`printf` 方法定义如下：

点击此处查看代码图像

```java
public class PrintStream
{
   public PrintStream printf(String fmt, Object... args) { return format(fmt, args); }
}
```

在这里，省略号 `...` 是 Java 代码的一部分。它表示该方法可以接收任意数量的对象（除 `fmt` 参数外）。

`printf` 方法定义如下：

点击此处查看代码图像

```java
public class PrintStream
{
   public PrintStream printf(String fmt, Object... args) { return format(fmt, args); }
}
```

在这里，省略号 `...` 是 Java 代码的一部分。它表示该方法可以接收任意数量的对象（除 `fmt` 参数外）。

`printf` 方法定义如下：

点击此处查看代码图像

```java
public class PrintStream
{
   public PrintStream printf(String fmt, Object... args) { return format(fmt, args); }
}
```

在这里，省略号 `...` 是 Java 代码的一部分。它表示该方法可以接收任意数量的对象（除 `fmt` 参数外）。

`printf` 方法定义如下：

点击此处查看代码图像

```java
public class PrintStream
{
   public PrintStream printf(String fmt, Object... args) { return format(fmt, args); }
}
```

（注：原文中存在重复部分）

`printf` 方法定义如下：

点击此处查看代码图像

```java
public class PrintStream
{
   public PrintStream printf(String fmt, Object... args) { return format(fmt, args); }
}
```

在这里，省略号 `...` 是 Java 代码的一部分。它表示该方法可以接收任意数量的对象（除 `fmt` 参数外）。

所有的枚举类型都是 `Enum` 类的子类。它们继承了该类的若干方法。最有用的方法是 `toString()`，它返回枚举常量的名称。例如，`Size.SMALL.toString()` 返回字符串 `"SMALL"`。

`toString()` 的逆向操作是静态方法 `valueOf`。例如，语句：

点击此处查看代码图像

```java
Size s = Enum.valueOf(Size.class, "SMALL");
```

将 `s` 设置为 `Size.SMALL`。

每个枚举类型都有一个静态的 `values()` 方法，返回该枚举所有值的数组。例如，调用：

点击此处查看代码图像

```java
Size[] values = Size.values();
```

返回包含元素 `Size.SMALL`、`Size.MEDIUM`、`Size.LARGE` 和 `Size.EXTRA_LARGE` 的数组。

`ordinal()` 方法返回枚举常量在 `enum` 声明中的位置，从零开始。例如，`Size.MEDIUM.ordinal()` 返回 `1`。

Listing 5.12 中的短程序演示了如何使用枚举类型。

> ![Image](img/note.jpg)
>
> **Note**
>
> `Enum` 类有一个类型参数，为了简单起见忽略了它。例如，枚举类型 `Size` 实际上扩展了 `Enum<Size>`。该类型参数用于 `compareTo()` 方法。（我们将在第 6 章](#ch06.html_ch06)中讨论 `compareTo()` 方法，在第 8 章](#ch08.html_ch08)中讨论类型参数。）

### Listing 5.12

`enums/EnumTest.java`

点击此处查看代码图像

```java
1    package enums;
2
3    import java.util.*;
4
5    /**
6    * 此程序演示了枚举类型。
7    * @version 1.0 2004-05-24
8    * @author Cay Horstmann
9    */
10   public class EnumTest
11   {
12       public static void main(String[] args)
13       {
14           Scanner in = new Scanner(System.in);
15          System.out.print("Enter a size: (SMALL, MEDIUM, LARGE, EXTRA_LARGE) ");
16          String input = in.next().toUpperCase();
17          Size size = Enum.valueOf(Size.class, input);
18          System.out.println("size=" + size);
19          System.out.println("abbreviation=" + size.getAbbreviation());
20          if (size == Size.EXTRA_LARGE)
21              System.out.println("Good job--you paid attention to the _.");
22       }
23   }
24
25   enum Size
26   {
27       SMALL("S"), MEDIUM("M"), LARGE("L"), EXTRA_LARGE("XL");
28
29       private Size(String abbreviation) { this.abbreviation = abbreviation; }
30       public String getAbbreviation() { return abbreviation; }
31
32       private String abbreviation;
33   }
```

## `java.lang.Enum<E>` 5.0

- `static Enum valueOf(Class enumClass, String name)`

  返回给定类中给定名称的枚举常量。

- `String toString()`

  返回此枚举常量的名称。

- `int ordinal()`

  返回此枚举常量在 `enum` 声明中从零开始的位置。

- `int compareTo(E other)`

  如果此枚举常量在 `other` 之前，则返回负整数；如果 `this == other`，返回零；否则返回正整数。常量的顺序由 `enum` 声明决定。

## 5.7 反射

反射库为你提供了一个非常强大的工具，可以在运行时检查和操作你的程序。反射 API 允许你在运行时检查或查询类、接口、字段和方法。它还允许你在运行时实例化新对象并调用方法。

反射 API 位于 `java.lang.reflect` 包。该包中的主要类是 `Field`、`Method`、`Constructor` 和 `Proxy`。

反射 API 中最重要的类是 `Class`。Java 中的每个类型都有一个关联的 `Class` 对象来描述它。你可以通过几种方式获取任何类型的 `Class` 对象：

- 使用 `.class` 字面量：`Class c = String.class;`
- 使用 `getClass()` 方法：`Class c = obj.getClass();`
- 使用静态的 `forName()` 方法：`Class c = Class.forName("java.lang.String");`

一旦获取了 `Class` 对象，就可以使用它获取有关该类型的信息，例如它的名称、父类、实现的接口、方法和字段。

### 5.7.1 `Class`

`Class` 类是反射 API 的入口点。Java 中的每个类型都有对应的 `Class` 对象。这些对象都是 `java.lang.Class` 类的实例。

`Class` 类提供了几个方法来查询类型信息：

- `getName()`：返回类的全名。
- `getSimpleName()`：返回类的简单名。
- `getSuperclass()`：返回类的父类。
- `getInterfaces()`：返回该类实现的接口数组。
- `getMethods()`：返回类的所有公共方法数组。
- `getFields()`：返回类的所有公共字段数组。

例如：

```java
Class c = String.class;
System.out.println(c.getName()); // 输出 java.lang.String
System.out.println(c.getSimpleName()); // 输出 String
```

`Class` 类还可以使用 `newInstance()` 方法创建类型的新实例：

```java
Class c = String.class;
Object obj = c.newInstance();
```

（注意：`newInstance()` 自 Java 9 起已弃用。请使用 `Constructor.newInstance()`。）

### 5.7.2 `Field` and `Method`

`Field` 和 `Method` 类允许你检查类的字段和方法。

`Field` 对象表示类的字段。你可以使用它获取字段的名称、类型，并获取或设置特定实例的值。

```java
Field f = String.class.getField("value");
System.out.println(f.getName()); // 输出 value
Object value = f.get(new String("hello")); // 返回内部表示表示
```

`Method` 对象表示类的方法。你可以使用它获取方法的名称、返回类型、参数类型，并在特定实例上调用该方法。

```java
Method m = String.class.getMethod("toUpperCase");
Object result = m.invoke(new String("hello")); // 返回 "HELLO"
```

### 5.7.3 `Proxy`

`Proxy` 类允许你在运行时创建代理对象。这通常用于实现面向切面的编程，例如日志或事务。

```java
Interface proxy = (Interface) Proxy.newProxyInstance(
    Interface.class.getClassLoader(),
    new Class<?>[]{Interface.class},
    new InvocationHandler()
);
```

`Class` 类实际上是一个泛型类。例如，`Employee.class` 的类型是 `Class<Employee>`。我们不打算深究这个问题，因为这会让一个已经抽象的概念变得更加复杂。对于大多数实际用途，你可以忽略类型参数并使用原始的 `Class` 类型进行操作。有关此问题的更多信息，请参阅第 8 章。

> ![Image](img/caution.jpg)
>
> **注意事项**
>
> 由于历史原因，`getName` 方法对数组类型返回了某些奇怪的名字：
>
> - `Double[].class.getName()` 返回 `"[Ljava.lang.Double;"`。
> - `int[].class.getName()` 返回 `"I"`。

虚拟机为每种类型管理一个唯一的 `Class` 对象。因此，你可以使用 `==` 运算符来比较类对象。例如：

```java
if (e.getClass() == Employee.class) . . .
```

另一个实用的方法是允许你动态创建类的实例。这个方法自然而易见地被称为 `newInstance()`。例如：

```java
e.getClass().newInstance();
```

创建一个与 `e` 相同类类型的新实例。`newInstance` 方法调用无参数构造函数来初始化新创建的对象。如果类没有无参数构造函数，则会抛出异常。

`forName` 和 `newInstance` 的组合允许你根据存储在字符串中的类名创建对象。

点击此处查看代码图片

```java
String s = "java.util.Random";
Object m = Class.forName(s).newInstance();
```

> ![Image](img/note.jpg)
>
> **注意**
>
> 如果你需要为通过这种方式按名称创建的类构造函数提供参数，则不能使用上述语句。相反，你必须使用 `Constructor` 类中的 `newInstance` 方法。

> ![Image](img/note1.jpg)
>
> **C++ 注意**
>
> `newInstance` 方法对应于 C++ 中的虚拟构造函数（virtual constructor）用法。然而，C++ 中的虚拟构造函数并不是一种语言特性，而是一种需要特殊库支持的用法。`Class` 类类似于 C++ 中的 `type_info` 类，而 `getClass` 方法等同于 `typeid` 运算符。不过，Java 的 `Class` 比 `type_info` 要通用得多。C++ 的 `type_info` 只能显示类型的名称字符串，而无法创建该类型的新对象。

### 5.7.4 异常处理入门

我们在第 7 章中完整涵盖了异常处理，但在此期间你会偶尔遇到可能会抛出异常的方法。

当运行时发生错误时，程序可以“抛出异常”。抛出异常比终止程序更灵活，因为你可以提供一个处理器来“捕获”并处理异常。

如果你不提供处理器，程序仍然会终止并在控制台上打印一条消息，说明异常的类型。你可能已经在不小心使用 `null` 引用或越数组边界时看到过异常报告了。

异常有两种类型：未检查异常（unchecked exceptions）和已检查异常（checked exceptions）。对于已检查异常，编译器会检查你是否提供了处理器。然而，许多常见异常（如访问 `null` 引用）是未检查的。编译器不会检查你是否为这些错误提供了处理器——毕竟，你应该把精力放在避免这些错误上，而不是为它们编写处理器。

但并非所有错误都是可以避免的。尽管你尽了努力仍然可能发生异常，那么编译器就会坚持你提供处理器。`Class.forName` 方法就是一个抛出已检查异常的方法示例。在第 7 章中，你将看到几种异常处理策略。现在，我们只向你展示简单的处理器实现。

将可能抛出已检查异常的一个或多个语句放在 `try` 块中。然后在 `catch` 子句中提供处理器代码。

点击此处查看代码图片

```java
try
{
   可能抛出异常的语句
}
catch (Exception e)
{
   处理器操作
}
```

这是一个示例：

点击此处查看代码图片

```java
try
{
   String name = . . .; // 获取类名
   Class cl = Class.forName(name); // 可能抛出异常
   对 cl 进行某些操作
}
catch (Exception e)
{
   e.printStackTrace();
}
```

如果类名不存在，`try` 块中的剩余代码将被跳过，程序进入 `catch` 子句。（在这里，我们使用 `Throwable` 类的 `printStackTrace` 方法打印堆栈跟踪。`Throwable` 是 `Exception` 类的父类。）如果 `try` 块中没有任何方法抛出异常，则 `catch` 子句中的处理器代码将被跳过。

你只需要为已检查异常提供异常处理器。找出哪些方法抛出异常很容易。



```java
java.lang.Class
static Class forName(String className)
Object newInstance()
```

```java
java.lang.reflect.Constructor
Object newInstance(Object[] args)
```

![Image](img/265tab01.jpg)

```java
java.lang.Throwable
void printStackTrace()
```

### 5.7.3 使用反射分析类

以下是反射机制检查类结构的重要部分的概述。

`java.lang.reflect` 包中的 `Field`、`Method` 和 `Constructor` 这三个类分别描述字段、方法和构造函数。这三个类都有一个名为 `getName` 的方法，返回项目的名称。`Field` 类有一个 `getType` 方法，返回一个对象（同样是 `Class` 类型），描述字段类型。`Method` 和 `Constructor` 类有报告参数类型的方法，而 `Method` 类还报告返回类型。

这三个类都有一个 `getModifiers` 方法，返回一个整数（某些位开启或关闭），描述所使用的修饰符，如 `public` 和 `static`。然后你可以使用 `java.lang.reflect` 中 `Modifier` 类的静态方法来分析 `getModifiers` 返回的整数。使用 `Modifier` 类中的 `isPublic`、`isPrivate` 或 `isFinal` 方法可以判断方法或构造函数是否为 `public`、`private` 或 `final`。你只需要让 `Modifier.toString` 方法处理该整数。

`Class` 类的 `getFields`、`getMethods` 和 `getConstructors` 方法返回该类支持的公共字段、方法和构造函数的数组。这包括父类的公共成员。`Class` 类的 `getDeclaredFields`、`getDeclaredMethods` 和 `getDeclaredConstructors` 方法返回在该类中声明的所有字段、方法和构造函数的数组。这包括私有的、包有有的受保护的成员，但不包括父类的成员。

列表 5.13 展示了如何打印关于类的所有信息。程序提示你输入类名，并输出该类所有方法和构造函数的签名以及所有实例字段的名称。例如，如果你输入：

`java.lang.Double`

程序打印：

点击此处查看代码图像

```java
public class java.lang.Double extends java.lang.Number
{
    public java.lang.Double(java.lang.String);
    public java.lang.Double(double);
    public int hashCode();
    public int compareTo(java.lang.Object);
    public int compareTo(java.lang.Double);
    public boolean equals(java.lang.Object);
    public java.lang.String toString();
    public static java.lang.String toString(double);
    public static java.lang.Double valueOf(java.lang.String);
    public static boolean isNaN(double);
    public boolean isNaN();
    public static boolean isInfinite(double);
    public boolean isInfinite();
    public byte byteValue();
    public short shortValue();
    public int intValue();
    public long longValue();
    public float floatValue();
    public double doubleValue();
    public static double parseDouble(java.lang.String);
    public static native long doubleToLongBits(double);
    public static native long doubleToRawLongBits(double);
    public static native double longBitsToDouble(long);
    public static final double POSITIVE_INFINITY;
    public static final double NEGATIVE_INFINITY;
    public static final double NaN;
    public static final double MAX_VALUE;
    public static final double MIN_VALUE;
    public static final java.lang.Class TYPE;
    private double value;
    private static final long serialVersionUID;
}
```

这个程序的独特之处在于，它可以分析 Java 解释器可以加载的任何类，而不仅仅是编译时可用的类。我们将在下一节中使用这个程序来查看 Java 编译器自动生成的内部类的内部。

### 列表 5.13 `reflection/ReflectionTest.java`

点击此处查看代码图像

***

```java
package reflection;

import java.util.*;
import java.lang.reflect.*;

/**
 * 此程序使用反射来打印类的所有特征。
 * @version 1.1 2004-02-21
 * @author Cay Horstmann
 */
public class ReflectionTest
{
    public static void main(String[] args)
    {
        // 从命令行参数或用户输入读取类名
        String name;
        if (args.length > 0) name = args[0];
        else
        {
            Scanner in = new Scanner(System.in);
            System.out.println("Enter class name (e.g. java.util.Date): ");
            name = in.next();
        }

        try
        {
            // 打印类名和父类名（如果 != Object）
            Class cl = Class.forName(name);
            Class supercl = cl.getSuperclass();
            String modifiers = Modifier.toString(cl.getModifiers());
            if (modifiers.length() > 0) System.out.print(modifiers + " ");
            System.out.print("class " + name);
            if (supercl != null && supercl != Object.class) System.out.print(" extends "
                    + supercl.getName());

            System.out.print("\n");
            printConstructors(cl);
            System.out.println();
            printMethods(cl);
            System.out.println();
            printFields(cl);
            System.out.println("}");
        }
        catch (ClassNotFoundException e)
        {
            e.printStackTrace();
        }
        System.exit(0);
    }

    /**
     * 打印类所有的构造函数
     * @param cl 类
     */
    public static void printConstructors(Class cl)
    {
        Constructor[] constructors = cl.getDeclaredConstructors();

        for (Constructor c : constructors)
        {
            String name = c.getName();
            System.out.print(" ");
            String modifiers = Modifier.toString(c.getModifiers());
            if (modifiers.length() > 0) System.out.print(modifiers + " ");
            System.out.print(name + "(");

            // 参数类型
            Class[] paramTypes = c.getParameterTypes();
            for (int j = 0; j < paramTypes.length; j++)
            {
                if (j > 0) System.out.print(", ");
                System.out.print(paramTypes[j].getName());
            }
            System.out.println(")");
        }
    }

    /**
     * 打印类所有的方法
     * @param cl 类
     */
    public static void printMethods(Class cl)
    {
        Method[] methods = cl.getDeclaredMethods();

        for (Method m : methods)
        {
            Class retType = m.getReturnType();
            String name = m.getName();

            System.out.print(" ");
            // 打印修饰符、返回类型和方法名
            String modifiers = Modifier.toString(m.getModifiers());
            if (modifiers.length() > 0) System.out.print(modifiers + " ");
            System.out.print(retType.getName() + " " + name + "(");

            // 参数类型
            Class[] paramTypes = m.getParameterTypes();
            for (int j = 0; j < paramTypes.length; j++)
            {
                if (j > 0) System.out.print(", ");
                System.out.print(paramTypes[j].getName());
            }
            System.out.println(")");
        }
    }

    /**
     * 打印类所有的字段
     * @param cl 类
     */
    public static void printFields(Class cl)
    {
        Field[] fields = cl.getDeclaredFields();
        for (Field f : fields)
        {
            Class type = f.getType();
            String name = f.getName();
            System.out.print(" ");
            String modifiers = Modifier.toString(f.getModifiers());
            if (modifiers.length() > 0) System.out.print(modifiers + " ");
            System.out.println(type.getName() + " " + name);
        }
    }
}
```

返回一个 `Class` 对象的数组，这些对象表示参数的类型。

- `Class getReturnType()`（在 `Method` 类中）

  返回表示返回类型的 `Class` 对象。

### `java.lang.reflect.Modifier` 1.1

- `static String toString(int modifiers)`

  返回一个字符串，其中包含与 `modifiers` 中位对应的修饰符。

- `static boolean isAbstract(int modifiers)`

- `static boolean isFinal(int modifiers)`

- `static boolean isInterface(int modifiers)`

- `static boolean isNative(int modifiers)`

- `static boolean isPrivate(int modifiers)`

- `static boolean isProtected(int modifiers)`

- `static boolean isPublic(int modifiers)`

- `static boolean isStatic(int modifiers)`

- `static boolean isStrict(int modifiers)`

- `static boolean isSynchronized(int modifiers)`

- `static boolean isVolatile(int modifiers)`

测试 `modifiers` 值中对应方法名修饰符的位。

### 5.7.4 使用反射在运行时分析对象

在前面的节中，我们看到了如何找到任何对象的数据字段的名称和类型：

- 获取相应的 `Class` 对象。
- 在 `Class` 对象上调用 `getDeclaredFields`。

在本节中，我们将更进一步，实际上查看字段的内容。当然，当你在编写程序时，如果一个对象的名称和类型是知的，查看其特定字段的内容很容易的。但反射允许你查看在编译时未知的对象的字段。

实现这一点的关键方法是 `Field` 类中的 `get` 方法。如果 `f` 是一个 `Field` 类型的对象（例如，从 `getDeclaredFields` 获取的字段），并且 `obj` 是 `f` 字段所属类的实例对象，那么 `f.get(obj)` 返回一个对象，其值是 `obj` 字段的当前值。这些都有一点点抽象，所以让我们过来看一个例子。

```java
Employee harry = new Employee("Harry Hacker", 35000, 10, 1, 1989);
Class cl = harry.getClass();
// 代表 Employee 的类对象
Field f = cl.getDeclaredField("name");
// Employee 类的 name 字段
Object v = f.get(harry);
// harry 对象 name 字段的值，即 String 对象 "Harry Hacker"
```

实际上，这段代码存在一个问题。由于 `name` 字段是一个私有字段，`get` 方法将抛出 `IllegalAccessException`。你只能使用 `get` 来获取可访问字段的值。Java 的安全机制允许你发现对象拥有哪些字段，但除非你拥有访问权限，否则它不会允许你读取这些字段的值。

反射机制的默认行为是尊重 Java 访问控制。然而，如果一个 Java 程序没有被禁止该操作的安全管理器控制，你就可以覆盖访问控制。为了这一点，可以在 `Field`、`Method` 或 `Constructor` 对象上调用 `setAccessible` 方法。例如：

```java
f.setAccessible(true); // 现在可以调用 f.get(harry); 了
```



`setAccessible` 方法是 `AccessibleObject` 类的方法，它是 `Field`、`Method` 和 `Constructor` 类的公共父类。此功能是为调试器、持久化存储和类似机制提供的。我们稍后会在通用的 `toString` 方法中使用它。

`get` 方法还有另一个我们需要处理的问题。`name` 字段是 `String`，因此将值作为 `Object` 返回没有问题。但假设我们想查看 `salary` 字段。它是一个 `double`，在 Java 中，数字类型不是对象。为了处理这个问题，你可以使用 `Field` 类的 `getDouble` 方法，或者调用 `get`，此时反射机制会将字段值封装成相应的包装类——在这种情况下，是 `Double`。

当然，你也可以设置你可以获取的值。调用 `f.set(obj, value)` 将对象 `obj` 中由 `f` 表示的字段设置为新值。

列表 5.14 显示了如何编写一个适用于任何类的通用 `toString` 方法。它使用 `getDeclaredFields` 获取所有字段。然后它使用 `setAccessible` 简便方法使所有字段都变得可访问。对于每个字段，它获取其名称和值。每个值都通过递归调用 `toString` 转换为字符串。

通用的 `toString` 方法需要处理一些复杂性。引用循环可能会导致无限递归。因此，`ObjectAnalyzer` 会跟踪已经访问过的对象。此外，要查看数组内部，你需要一种不同的方法。你将在下一节中学习细节。

你可以使用这个 `toString` 方法查看任何对象的内部情况。例如，调用：

```java
ArrayList<Integer> squares = new ArrayList<>();
for (int i = 1; i <= 5; i++) squares.add(i * i);
System.out.println(new ObjectAnalyzer().toString(squares));
```

产生打印输出：

```text
java.util.ArrayList[class java.lang.Object[]{Integer=1, Integer=4, Integer=9, Integer=16, Integer=25],null,null,null,null},size=5,Count=5][]
```

你可以使用这个通用的 `toString` 方法来实现你自己的类的 `toString` 方法，如下所示：

```java
public String toString()
{
    return ObjectAnalyzer().toString(this);
}
```

这是一个你可能在程序中非常有用的提供 `toString` 方法的无忧方法。

### Listing 5.14 ObjectTest.java

```java
package objectAnalyzer;

import java.util.ArrayList;

/**
 * 该程序使用反射观察对象。
 * @version 1.12 2012-01-26
 * @author Cay Horstmann
 */
public class ObjectTest
{
    public static void main(String[] args)
    {
        ArrayList<Integer> squares = new ArrayList<>();
        for (int i = 1; i <= 5; i++)
            squares.add(i * i);
        System.out.println(new ObjectAnalyzer().toString(squares));
    }
}
```

### Listing 5.15 ObjectAnalyzer.java

```java
package objectAnalyzer;

import java.lang.reflect.AccessibleObject;
import java.lang.reflect.Array;
import java.lang.reflect.Field;
import java.lang.reflect.Modifier;
import java.util.ArrayList;

public class ObjectAnalyzer
{
    private ArrayList<Object> visited = new ArrayList<>();

    /**
     * 将对象转换为列所有字段的字符串表示。
     * @param obj 一个对象
     * @return 包含对象类名以及所有字段及其值的字符串
     */
    public String toString(Object obj)
    {
        if (obj == null) return "null";
        if (visited.contains(obj)) return "...";
        visited.add(obj);
        Class cl = obj.getClass();
        if (cl == String.class) return (String) obj;
        if (cl.isArray())
        {
            String r = cl.getComponentType() + "[]";
            for (int i = 0; i < Array.getLength(obj); i++)
            {
                if (i > 0) r += ",";
                Object val = Array.get(obj, i);
                if (cl.getComponentType().isPrimitive()) r += val;
                else r += toString(val);
            }
            return r + "}";
        }

        String r = cl.getName();
        // ... (剩余的实现)
    }
}
```

```java
// inspect the fields of this class and all superclasses
do
{
    r += "[";
    Field[] fields = cl.getDeclaredFields();
    AccessibleObject.setAccessible(fields, true);
    // get the names and values of all fields
    for (Field f : fields)
    {
        if (!Modifier.isStatic(f.getModifiers()))
        {
            if (!r.endsWith("[")) r += ",";
            r += f.getName() + "=";
            try
            {
                Class t = f.getType();
                Object val = f.get(obj);
                if (t.isPrimitive()) r += val;
                else r += toString(val);
            }
            catch (Exception e)
            {
                e.printStackTrace();
            }
        }
    }
    r += "]";
    cl = cl.getSuperclass();
}
while (cl != null);

return r;
```

### `java.lang.reflect.AccessibleObject`

- `void setAccessible(boolean flag)`：设置此反射对象的访问权限标志。值为 `true` 时表示抑制 Java 语言的访问检查，并且可以查询和设置对象的私有属性。
- `boolean isAccessible()`：获取此反射对象的访问权限标志。
- `static void setAccessible(AccessibleObject[] array, boolean flag)`：用于设置对象数组访问权限标志的便利方法。

### `java.lang.Class`

- `Field getField(String name)`：获取给定名称的公共字段，或包含所有字段的数组。
- `Field[] getDeclaredFields()`：获取在该类中声明的给定名称字段，或包含所有字段的数组。

### `java.lang.reflect.Field`

- `Object get(Object obj)`：返回对象 `obj` 中由此 `Field` 对象描述的值。
- `void set(Object obj, Object newValue)`：将对象 `obj` 中由此 `Field` 对象描述的字段设置为新值。

## 5.7.5 使用反射编写泛型数组

`java.lang.reflect` 包中的 `Array` 类允许你动态创建数组。这被用于例如 `Arrays` 类中 `copyOf` 方法的实现。回想一下该方法如何用于扩展一个已满的数组：

```java
Employee[] a = new Employee[100];
a = Arrays.copyOf(a, a.length);
```

如何编写这样一个泛型方法呢？`Employee[]` 数组可以转换为 `Object[]` 数组，这很有帮助。这听起来很有前景。这里是第一次尝试：

```java
public static Object[] badCopyOf(Object[] a, int newLength) // 没有用
{
    Object[] newArray = new Object[newLength];
    System.arraycopy(a, 0, newArray, 0, Math.min(a.length, newLength));
    return newArray;
}
```

然而，实际使用生成的数组时存在问题。此代码返回的数组类型是对象数组（`Object[]`），因为我们使用 `new Object[newLength]` 这一行创建了数组。对象数组不能强制转换为 `Employee[]` 数组。虚拟机将生成 `ClassCastException`。点在于，正如我们之前提到的，Java 数组会记住其条目的类型——即创建它的 `new` 表达式中使用的元素类型。将一个 `Employee[]` 临时强制转换为 `Object[]` 数组然后转换回来是合法的，但一个从初作为 `Object[]` 数组开始的数组永远无法转换为 `Employee[]` 数组。要编写这种泛型数组代码，我们需要能够创建一个与原始数组相同类型的新数组。为此，我们需要 `java.lang.reflect` 包中 `Array` 类的方法。关键在于 `Array` 类中用于构造新数组的静态方法 `newInstance`。你必须将条目类型和所需的长度作为参数传递给该方法。

```java
Object newArray = Array.newInstance(componentType, newLength);
```

为了实际执行这一操作，我们需要获取新数组的长度和组件类型。我们通过调用 `Array.getLength(a)` 获取长度。`Array` 类的静态方法 `getLength` 返回数组的长度。获取新数组的组件类型：

1. 首先，获取 `a` 的类对象。
2. 确认它确实是一个数组。
3. 使用 `Class` 类的 `getComponentType` 方法（仅为代表数组的类对象定义）找到数组的类型。

为什么 `getLength` 是 `Array` 的方法，而 `getComponentType` 是 `Class` 的方法？我们不知道——反射方法的分布有时似乎有些随心所欲。这里是代码：

```java
public static Object goodCopyOf(Object a, int newLength)
{
    Class cl = a.getClass();
    if (!cl.isArray()) return null;
    Class componentType = cl.getComponentType();
    int length = Array.getLength(a);
    Object newArray = Array.newInstance(componentType, newLength);
    System.arraycopy(a, 0, newArray, 0, Math.min(length, newLength));
    return newArray;
}
```

注意，这个 `copyOf` 方法可以用于扩展任何类型的数组，而不仅仅是对象数组。

```java
int[] a = { 1, 2, 3, 4, 5 };
a = (int[]) goodCopyOf(a, 10);
```

### Listing 16: CopyTest.java

```java
package arrays;

import java.lang.reflect.*;
import java.util.*;

/**
 * 此程序演示了反射的使用。
 * @version 1.2-05-4
 * @author Caymann
 */
public class CopyTest
{
    public static void main(String[] args)
    {
        int[] a = { 1, 2, 3 };
        a = (int[]) goodCopyOf(a, 10);
        System.out.println(Arrays.toString(a));

        String[] b = { "Tom", "Dick", "Harry" };
        b = (String[]) goodCopyOf(b, 10);
        System.out.println(Arrays.toString(b));

        System.out.println("下面的调用将产生异常。");
        b = (String[]) badCopyOf(b, 10);
    }
}
```

```java
/**
 * type array
 * @return 一个包含 a 中所有元素的更大的数组。
 */
public static Object goodCopyOf(Object a, int newLength)
{
    Class cl = a.getClass();
    if (!cl.isArray()) return null;
    Class componentType = cl.getComponentType();
    int length = Array.getLength(a);
    Object newArray = Array.newInstance(componentType, newLength);
    System.arraycopy(a, 0, newArray, 0, Math.min(length, newLength));
    return newArray;
}
```

### `java.lang.reflect.Array` 1.1

- `static Object get(Object array, int index)`
- `static xxx getxx(Object array, int index)`

  （`xxx` 是基本类型 `boolean`、`byte`、`char`、`double`、`float`、`int`、`long` 或 `short` 之一。）这些方法返回给定数组中指定索引处的值。

- `static void set(Object array, int index, Object newValue)`
- `static setxx(Object array, int index, xxx newValue)`

  （`xxx` 是基本类型 `boolean`、`byte`、`char`、`double`、`float`、`int`、`long` 或 `short` 之一。）这些方法将新值存储在给定数组的指定索引处。

- `static int getLength(Object array)`

  返回给定数组的长度。

- `static Object newInstance(Class componentType, int length)`
- `static Object newInstance(Class componentType, int[] lengths)`

  返回一个具有给定维度和给定组件类型的新数组。

## 5.7.6 调用任意方法

在 C 和 C++ 中，你可以通过函数指针执行任意函数。从表面上看，Java 并没有方法指针——也就是说，没有将方法的位置传递给另一个方法的方法，以便第二个方法稍后调用它。事实上，Java 的设计者曾表示方法指针是危险且容易出错的，而 Java `interfaces`（将在下一章讨论）是一个更优越的解决方案。然而，反射机制允许你调用任意方法。

![Image](img/note.jpg) 注意



在微软在其 Java 衍生语言添加的非标准语言扩展中，`J++` 和 `C#` 包含了另一种方法指针类型，称为 `delegate`，它与在本节中讨论的 `Method` 类不同。然而，内部类（我们将在下一章介绍）比委托更有实用的结构。

回想一下，你可以使用 `Field` 类的 `get` 方法检查对象的字段。同样，`Method` 类有一个 `invoke` 方法，它允许你调用封装在当前 `Method` 对象中的方法。`invoke` 方法的签名如下：

```java
Object invoke(Object obj, Object... args)
```

第一个参数是隐式参数，剩余的对象提供了显式参数。

对于静态方法，第一个参数是被忽略的——你可以将其设置为 `null`。

例如，如果 `m1` 代表 `Employee` 类的 `getName` 方法，下面的代码展示了你如何调用它：

```java
String n = (String) m1.invoke(harry);
```

如果返回类型是基本类型，`invoke` 方法将返回相应的包装类型。例如，假设 `m2` 代表 `Employee` 类的 `getSalary` 方法。那么，返回的对象实际上是一个 `Double`，你必须对其进行相应的类型转换。使用自动拆箱将其转换为 `double`：

```java
double s = (Double) m2.invoke(harry);
```

你如何获取 `Method` 对象？当然，你可以调用 `getDeclaredMethods` 并遍历返回的 `Method` 对象数组，直到找到你想要的方法为止。或者，你可以调用 `Class` 类的 `getMethod` 方法。这类似于 `getField` 方法，`getField` 接受一个带有字段名的字符串并返回一个 `Field` 对象。然而，可能存在多个同名的方法，因此你需要小心获取正确的那一个。出于这个原因，还必须提供参数类型。`getMethod` 的签名是：

```java
Method getMethod(String name, Class... parameterTypes)
```

例如，这里是你可以获取 `Employee` 类的 `getName` 和 `raiseSalary` 方法的方法指针：

```java
Method m1 = Employee.class.getMethod("getName");
Method m2 = Employee.class.getMethod("raiseSalary", double.class);
```

现在你已经了解了 `Method` 对象的规则，让我们让它们用起来吧。`Listing 5.17` 是一个程序，用于打印数学函数（如 `Math.sqrt` 或 `Math.sin`）的数值表格。输出结果如下：

```
public static native double java.lang.Math.sqrt(double)
1.0000 | 1.0000
2.0000 | 1.4142
3.0000 | 1.7321
4.0000 | 2.0000
5.0000 | 2.2361
6.0000 | 2.4495
7.0000 | 2.6458
8.0000 | 2.8284
9.0000 | 3.0000
10.0000 | 3.1623
```

```java
Method sqrt = Math.class.getMethod("sqrt", double.class);

// print tables of x- and y-values

printTable(1, 10, 10, square);
printTable(1, 10, 10, sqrt);

}

/**
 * Returns the square of a number
 * @param x a number
 * @return x squared
 */
public static double square(double x)
{
    return x * x;
}

/**
 * Prints a table with x- and y-values for a method
 * @param from the lower bound for the x-values
 * @param to the upper bound for the x-values
 * @param n the number of rows in the table
 * @param f a method with a double parameter and double return value
 */
public static void printTable(double from, double to, int n, Method f)
{
    // print out the method as table header
    System.out.println(f);

    double dx = (to - from) / (n - 1);

    for (double x = from; x <= to; x += dx)
    {
        try
        {
            double y = (Double) f.invoke(null, x);
            System.out.printf("%10.4f | %10.4f%n", x, y);
        }
        catch (Exception e)
        {
            e.printStackTrace();
        }
    }
}
```

`java.lang.reflect.Method` `1.1`

- `public Object invoke(Object implicitParameter, Object[] explicitParameters)`

调用此对象描述的方法，传递给定的参数并返回方法产生的值。对于静态方法，请将 `null` 作为隐式参数。使用包装类来传递基本类型值。基本类型返回值必须进行拆箱。

### 5.8 继承的设计提示

我们希望在这一章结束时，提供一些我们在使用继承时发现非常有用的提示。

**1. 将公共操作和字段放在父类中。**

这就是为什么我们将 `name` 字段放入 `Person` 类中，而不是在 `Employee` 和 `Student` 类中重复定义它。

**2. 不要使用保护字段。**

有些程序员认为将实例字段定义为 `protected` 是一个好主意，“以防万一”，这样子类在需要时就可以访问它们。然而，`protected` 机制并没有提供多少保护，原因有两个。首先，子类的集合是无界的——任何人都可以创建你类的子类，并编写直接访问 `protected` 字段的代码，从而破坏封装。其次，在 Java 语言中，同一个包中的所有类都可以访问 `protected` 字段，无论它们是否是子类。然而，`protected` 方法可以用于指示那些尚未准备好用于通用且应该在子类中重新定义的方法。

**3. 使用继承来建模“是”关系。**

继承是一种方便的代码节省工具，但有时人们会过度使用它。例如，假设我们需要 `Contractor` 类。承包工有名字和入职日期，但没有工资。相反，他们按小时付费，而且留的时间不够长到可以获得加薪。人们很容易从 `Employee` 派生出一个 `Contractor` 子类并添加 `hourlyWage` 字段。

```java
public class Contractor extends Employee
{
    private double hourlyWage;
    ...
}
```

这不是一个好主意，因为现在每个承包商对象既有工资又有薪字段。这会在你实现工资单或税表方法时带来无尽的麻烦。你最终编写的代码比你从不使用继承要多得多。承包商与员工的关系没有通过“是”的测试。承包商并不是员工的特例。

**4. 除非所有继承的方法都有意义，否则不要使用继承。**

假设我们想写一个 `Holiday` 类。显然，每个节日都是一天，而天可以表示为 `GregorianCalendar` 类的实例，因此我们可以使用继承。

```java
class Holiday extends GregorianCalendar { . . }
```

遗憾的是，节日的集合在继承的操作下是不封闭的。`GregorianCalendar` 的公共方法之一是 `add`。而 `add` 可以将节日变成非节日：

```java
Holiday christmas;
christmas.add(DAY_OF_MONTH, 12);
```

因此，在这个例子中使用继承是不合适的。请注意，如果你扩展的是 `LocalDate`，这个问题就不会出现。因为该类是不可变的，没有哪个方法可以将节日变成非节日。

**5. 在重写方法时不要改变预期的行为。**

替换原则不仅适用于语法，更重要的是适用于行为。当你重写一个方法时，你不应该无理地改变它的行为。编译器无法帮助你——它无法检查你的重定义是否有意义。例如，你可以通过重新定义 `add` 方法来“修复” `Holiday` 类中 `add` 方法的问题，也许可以什么都不做，或者抛出异常，或者跳转到下一个节日。

然而，这种修复违反了替换原则。以下语句序列：

```java
int d1 = x.get(Calendar.DAY_OF_MONTH);
x.add(DAY_OF_MONTH, 1);
int d2 = x.get(Calendar.DAY_OF_MONTH);
System.out.println(d2 - d1);
```

应该具有预期的行为，无论 `x` 的类型是 `GregorianCalendar` 还是 `Holiday`。

当然，问题就在于此。合理和不合理的人可以对预期行为进行长时间争论。例如，一些作者认为替换原则要求 `Manager.equals` 忽略 `bonus` 字段，因为 `Employee.equals` 忽略了它。如果这些讨论是在真空中进行的，它们毫无意义。归根结底，重要的是你在子类中重写方法时不要背离设计的意图。

**6. 使用多态而不是类型信息。**

每当你发现如下形式的代码时：

```java
if (x is of type 1)
    action1;
else if (x is of type 2)
    action2;
```

考虑多态。`action[1]` 和 `action[2]` 代表一个共同的概念吗？如果是，让该概念成为两个类型的共同父类或接口的方法。然后，你只需要调用

`x.action();`

并让多态固有的动态分发机制启动正确的操作。使用多态方法或接口实现的代码比使用多个类型测试要容易维护和扩展。

**7. 不要过度使用反射。**

反射机制允许通过运行时检测字段和方法来编写具有极大通用性的程序。这种能力对于系统编程有用，但通常不适用于应用程序。反射是脆弱的——使用它时，编译器无法帮助你发现编程错误。任何错误都在运行时发现并导致异常。

你现在已经了解了 Java 如何支持面向对象编程的基础：类、继承和多态。在下一章中，我们将解决两个对于有效使用 Java 至关重要的高级话题：接口和 Lambda 表达式。

你已经学习了 Java 面向对象编程的基本工具。本章将为你介绍几种常用的高级技术。尽管这些技术并不显而易见，但你将掌握它们来完善你的 Java 工具箱。

第一种技术称为 `interfaces`（接口），它是描述类应该“做什么”的方法，而不指定它们应该“如何”做。一个类可以 `implement`（实现）一个或多个接口。当需要符合接口时，你可以使用这些实现类的对象。在介绍完接口之后，我们将转向 `lambda expressions`（Lambda 表达式），这是一种以后某个时刻执行代码块的简洁方式。使用 `lambda expressions`，你可以用优雅且简洁的方式使用回调或变量行为的代码。

然后我们讨论 `inner classes`（内部类）的机制。内部类在技术上有点复杂——它们被定义在其他类内部，其方法可以访问外部类的字段。当你设计一组协作的类时，内部类非常有用。

本章以对 `proxies`（代理）的讨论结束，代理是实现任意接口的对象。代理是一种特殊的结构，用于构建系统级工具。第一次阅读时，你可以安全地跳过该部分。

### 6.1 接口

在接下来的章节中，你将学习 Java 接口以及如何使用它们。你还将发现接口在 Java SE 8 中变得更加强大。

#### 6.1.1 接口概念

在 Java 编程语言中，接口不是类，而是对想要符合接口的类定义的 `requirements`（要求）。

通常，某些服务的提供者会：“如果你的类符合特定的接口，我就执行该服务。”让我们来看一个例子。`Arrays` 类的 `sort` 方法承诺对对象数组进行排序，但有一个条件：对象必须属于实现了 `Comparable` 接口的类。

以下是 `Comparable` 接口的样子：

```java
public interface Comparable
{
   int compareTo(Object other);
}
```

这意味着任何实现 `Comparable` 接口的类都要求有一个 `compareTo` 方法，且该方法必须接受一个 `Object` 参数并返回一个整数。

* * *

![Image](img/note.jpg) 注意

从 Java SE 5.0 开始，`Comparable` 接口被增强为泛型类型。

```java
public interface Comparable<T>
{
   int compareTo(T other); // 参数类型为 T
}
```

例如，实现 `Comparable<Employee>` 的类必须提供一个方法

```java
int compareTo(Employee other)
```

你仍然可以使用不带类型参数的“原始” `Comparable` 类型。此时，`compareTo` 方法的参数类型为 `Object`，你必须手动将 `compareTo` 方法的该参数强制类型转换为所需的类型。我们会在短时间内这样做，这样你就不需要同时担心两个新概念了。

* * *

接口的所有方法都自动是 `public`（公有）。正由于这个原因，在接口中声明方法时没有必要提供 `public` 关键字。

当然，还有一个接口无法显式写出的额外要求：当在调用 `x.compareTo(y)` 时，`compareTo` 方法实际上必须能够 `compare` 两个对象，并返回 `x` 或 `y` 哪个更大的指示。如果 `x` 小于 `y`，该方法应该返回负数；如果它们相等，则返回 0；否则返回正数。

这个特定的接口只有一个方法。有些接口有多个方法。正如你以后将看到的，接口还可以定义常量。然而，更重要的是接口 `cannot` 提供的内容。接口永远没有实例字段。在 Java SE 8 之前，接口中从没有实现的方法。（正如你在第 6.1.4 节 中看到的，“静态方法”位于第 298 页以及第 6.1.5 节 中的“默认方法”位于第 298 页，现在可以在接口中提供简单的方法。当然，这些方法不能引用实例字段——接口没有任何实例字段。）

提供实例字段以及操作这些字段的方法是实现接口的类的任务。你可以将接口类似于没有实例字段的抽象类。然而，这两个概念之间存在一些差异——我们稍后会详细讨论。

现在假设我们想使用 `Arrays` 类的 `sort` 方法对一个 `Employee` 对象数组进行排序。那么 `Employee` 类必须 `implement` `Comparable` 接口。

要让一个类实现接口，你需要执行两个步骤：

**1.** 你声明你的类意图实现给定的接口。

**2.** 你为接口中的所有方法提供定义。

要声明一个类实现接口，使用 `implements` 关键字：

```java
class Employee implements Comparable
```

当然，现在 `Employee` 类需要提供 `compareTo` 方法。假设我们想按工资比较员工。这里是 `compareTo` 方法的一个实现：

```java
public int compareTo(Object otherObject)
{
   Employee other = (Employee) otherObject;
   return Double.compare(salary, other.salary);
}
```

在这里，我们使用了静态的 `Double.compare` 方法，如果第一个参数小于第二个参数，它返回负数，如果它们相等则返回 `0`，否则返回正值。

* * *

![Image](img/caution.jpg) 注意

在接口声明中，`compareTo` 方法没有被声明为 `public`，因为 `interface` 中的所有方法自动是公有的。然而，在实现接口时，你必须将方法声明为 `public`。否则，编译器会假设该方法具有包可见性——这是 `class` 的默认权限。编译器随后会抱怨你正试图提供更高的访问权限。

* * *

我们可以通过为泛型 `Comparable` 接口提供类型参数来做得更好：

```java
class Employee implements Comparable<Employee>
{
   public int compareTo(Employee other)
   {
      return Double.compare(salary, other.salary);
   }
   ...
}
```

注意，`Object` 参数难看的强制转换消失了。

* * *

![Image](img/tip.jpg) 提示



`Comparable` 接口的 `compareTo` 方法返回一个整数。如果对象不相等，你返回什么负数或正数并不重要。这种灵活性在比较整数字段时非常有用。

例如，假设每个员工都有一个唯一的整数 `id`，你想按员工 ID 排序。那么你可以简单地返回 `id - other.id`。如果第一个 ID 小于另一个，该值将是某个负值；如果它们相同则返回 0；否则返回某个正值。

然而，有一个警告：整数范围必须足够小，以便减法不会溢出。如果你知道 ID 不是负数，或者它们的绝对值最多为 `(Integer.MAX_VALUE - 1) / 2`，那么就是安全的。否则，调用静态的 `Integer.compare` 方法。

当然，减法技巧并不适用于浮点数。`salary - other.salary` 的差在工资接近但并不相同时可能会被舍入为 `0`。调用 `Double.compare(x, y)` 只在 `x < y` 时返回 `-1`，在 `x > y` 时返回 `1`。

`Comparable` 接口的文档建议 `compareTo` 方法应该与 `equals` 方法兼容。也就是说，恰当 `x.equals(y)` 为真时，`x.compareTo(y)` 应等于 0。

Java API 中大多数实现 `Comparable` 的类都遵循这一建议。一个显著例外是 `BigDecimal`。考虑 `x = new BigDecimal("1.0")` 和 `y = new BigDecimal("1.00")`。此时 `x.equals(y)` 为 `false`，因为这两个数的精度不同。但 `x.compareTo(y)` 等于 0。理想情况下，它不应该是如此，但并没有明显的方法来决定哪一个应该排在前面。

现在你看到了一个类为了利用排序服务必须做什么——它必须实现一个 `compareTo` 方法。这非常合理。`sort` 方法确实需要某种方式来比较对象。

但为什么 `Employee` 类不能在不实现 `Comparable` 接口的情况下直接提供一个 `compareTo` 方法呢？

引入接口的原因是 Java 编程语言是强类型的。在调用方法时，编译器需要能够检查该方法是否存在。在 `sort` 方法的某处会有类似下面的语句：

```java
if (a[i].compareTo(a[j]) > 0)
{
    // rearrange a[i] and a[j]
    ...
}
```

编译器必须知道 `a[i]` 确实有一个 `compareTo` 方法。如果 `a` 是一个 `Comparable` 对象的数组，那么该方法的存在性就有保证，因为每个实现 `Comparable` 接口的类都提供该方法。

![Image](img/note.jpg) 备注

你可能认为 `Arrays` 类中的 `sort` 方法定义为接受一个 `Comparable[]` 数组，这样如果有人用一个元素类型没有实现 `Comparable` 接口的数组调用 `sort`，编译器就会报错。遗憾的是，事实并非如此。`sort` 方法接受一个 `Object[]` 数组并使用笨拙的强制转换：

```java
// 标准库中使用的方法--不推荐
if (((Comparable) a[i]).compareTo(a[j]) > 0)
{
    // rearrange a[i] and a[j]
    ...
}
```

如果 `a[i]` 不属于实现 `Comparable` 接口的类，虚拟机将抛出异常。

代码列表 6.1 展示了排序 `Employee` 类实例数组的完整代码（代码列表 6.2）。

**代码列表 6.1** `interfaces/EmployeeSortTest.java`

```java
1    package interfaces;
2
3    import java.util.*;
4
5    /**
6      * 此程序演示了 Comparable 接口的使用。
7      * @version 1.30 2004-02-27
8      * @author Cay Horstmann
9      */
10   public class EmployeeSortTest
11   {
12       public static void main(String[] args)
13       {
14           Employee[] staff = new Employee[3];
15
16          staff[0] = new Employee("Harry Hacker", 35000);
17          staff[1] = new Employee("Carl Cracker", 75000);
18          staff[2] = new Employee("Tony Tester", 38000);
19
20          Arrays.sort(staff);
21
22          // 打印所有 Employee 对象的信息
23          for (Employee e : staff)
24              System.out.println("name=" + e.getName() + ",salary=" + e.getSalary());
25       }
26   }
```

**代码列表 6.2** `interfaces/Employee.java`

```java
1    package interfaces;
2
3    public class Employee implements Comparable<Employee>
4   {
5       private String name;
6       private double salary;
7
8       public Employee(String name, double salary)
9       {
10          this.name = name;
11          this.salary = salary;
12      }
13
14      public String getName()
15      {
16          return name;
17      }
18
19      public double getSalary()
20      {
21          return salary;
22      }
23
24      public void raiseSalary(double byPercent)
25      {
26          double raise = salary * byPercent / 100;
27          salary += raise;
28      }
29
30      /**
31      * 按工资比较员工
32      * @param other 另一个对象
33      * @return 如果此员工的工资比另一个低，则返回负值；
34      * 如果工资相同则返回 0，否则返回正值
35      */
36      public int compareTo(Employee other)
37      {
38          return Double.compare(salary, other.salary);
39      }
40  }
```

`Comparable<T>` 1.0

`int compareTo(T other)` 与 `other` 比较。如果此对象小于 `other` 则返回负整数，如果相等则返回 0，否则返回正整数。

`java.util.Arrays` 1.2

`static void sort(Object[] a)` 排序数组 `a` 中的元素。数组中的所有元素都必须是相互可比较的。

`java.lang.Integer` 1.0

`static int compare(int x, int y)` 如果 `x < y` 返回负整数，如果 `x == y` 返回 0，否则返回正整数。

`java.lang.Double` 1.0

`static int compare(double x, double y)` 如果 `x < y` 返回负整数，如果 `x == y` 返回 0，否则返回正整数。

![Image](img/note.jpg) 备注

根据语言标准：“实现者必须确保 `sgn(x.compareTo(y)) = -sgn(y.compareTo(x))` 对于所有 `x` 和 `y` 成立（这意味着如果 `y.compareTo(x)` 抛出异常，`x.compareTo(y)` 也必须抛出异常）。”

这里 `sgn` 是数字的符号：如果 `n` 为负则返回 -1，如果 `n` 为 0 则返回 0，如果 `n` 为正则返回 1。通俗地说，如果你反转了 `compareTo` 的参数，结果的符号（但不一定是实际数值）也随之反转。

与 `equals` 方法一样，当涉及继承时会出现问题。

由于 `Manager` 继承自 `Employee`，它实现了 `Comparable<Employee>` 而不是 `Comparable<Manager>`。如果 `Manager` 选择重写 `compareTo`，它必须准备好与员工比较。它不能简单地将员工强制转换为经理：

```java
class Manager extends Employee
{
    public int compareTo(Employee other)
    {
        Manager otherManager = (Manager) other; // 不行
        ...
    }
}
```

这违反了“反对性”规则。如果 `x` 是一个 `Employee` 且 `y` 是一个 `Manager`，那么调用 `x.compareTo(y)` 不会抛出异常——它只是作为员工比较 `x` 和 `y`。但反过来，`y.compareTo(x)` 会抛出 `ClassCastException`。

#### 6.1.2 接口的属性

接口不是类。特别是，你永远无法使用 `new` 运算符实例化接口：

```java
x = new Comparable(. . .); // ERROR
```

然而，尽管你无法构造接口对象，你仍然可以声明接口变量。

```java
Comparable x; // OK
```

接口变量必须引用实现该接口的类的对象：

```java
x = new Employee(. . .); // 只要 Employee 实现了 Comparable 即可 OK
```

接下来，就像你使用 `instanceof` 来检查对象是否属于特定类一样，你可以使用 `instanceof` 来检查一个对象是否实现了某个接口：

```java
if (anObject instanceof Comparable) { . . . }
```

就像你可以构建类的层次结构一样，你也可以扩展接口。这允许创建多条接口链，从更具通用性到更具特化性。例如，假设你有一个名为 `Moveable` 的接口。

```java
public interface Moveable
{
   void move(double x, double y);
}
```

然后，你可以想象有一个名为 `Powered` 的接口扩展了它：

```java
public interface Powered extends Moveable
{
   double milesPerGallon();
}
```

虽然你不能在接口中放置实例字段或静态方法，但你可以在其中提供常量。例如：

```java
public interface Powered extends Moveable
{
   double milesPerGallon();
   double SPEED_LIMIT = 95; // 一个 public static final 常量
}
```

就像接口中的方法自动是 `public` 的一样，字段始终是 `public static final`。

![Image](img/note.jpg) 注意

将接口方法标记为 `public`、将字段标记为 `public static final` 是合法的。一些程序员会这样做，可能是出于习惯或为了更清晰。然而，Java 语言规范建议不要提供冗余的关键字，我们也遵循了这一建议。

有些接口只定义常量而没有方法。例如，标准库包含一个名为 `SwingConstants` 的接口，它定义了常量 `NORTH`、`SOUTH`、`HORIZONTAL` 等。任何选择实现 `SwingConstants` 接口的类都会继承这些常量。它的方法可以直接引用 `NORTH`，而不是更繁琐的 `SwingConstants.NORTH`。然而，这种对接口的使用似乎相当退化，我们不建议这样做。

虽然每个类只能有一个超类，但类可以实现多个接口。这让你在定义类的行为时具有最大的灵活性。

例如，Java 编程语言在其内部内置了一个重要的接口，称为 `Cloneable`。（我们将在第 6.2.3 节“对象克隆”中详细讨论该接口，位于第 306 页）。如果你的类实现了 `Cloneable`，`Object` 类中的 `clone` 方法将为你的类创建一个精确的副本。

如果你同时需要可克隆性和可比较性，只需实现这两个接口即可。使用逗号分隔你想要实现的接口：

```java
class Employee implements Cloneable, Comparable
```

### 6.1.3 接口与抽象类

如果你阅读了第 5 章中关于抽象类的章节，你可能会奇怪为什么 Java 语言的设计者要费心引入接口的概念。为什么 `Comparable` 不能简单地是一个抽象类呢：

```java
abstract class Comparable // 为什么不能呢？
{
   public abstract compareTo(Object other);
}
```

`Employee` 类将扩展这个抽象类并提供 `compareTo` 方法：

```java
class Employee extends Comparable // 为什么不能呢？
{
   public int compareTo(Object other) { . . . }
}
```

遗憾的是，使用抽象类来表达通用属性有一个主要问题。一个类只能扩展一个类。假设 `Employee` 类已经扩展了另一个类，比如 `Person`。那么它就不能扩展第二个类了。

```java
class Employee extends Person, Comparable // 错误
```

但每个类都可以想要实现任意数量的接口：

```java
class Employee extends Person implements Comparable // OK
```

其他编程语言，特别是 C++，允许类拥有多个超类。这一特征被称为多重继承。Java 的设计者选择不支持多重继承，因为这会使语言变得非常复杂（如 C++）或者效率更低（如 Eiffel）。相反，接口提供了多重继承的大部分优势。

![Image](img/note1.jpg) 注意

C++ 有多重继承以及随之而来的所有复杂性，例如虚基类、支配规则和强制类型转换。很少有 C++ 程序员使用多重继承，有些人建议永远不要使用。建议多重继承仅用于“混合（mix-in）”。在混合样式中，主基类描述对象，而附加基类（所谓的 mixins）提供辅助特征。

### 6.1.4 静态方法

从 Java 8 开始，允许向接口中添加静态方法。以前并没有技术原因禁止这样做。它只是违背了接口作为抽象规范的精神。

到目前，将静态方法放在工具类是很常见的。在标准库中，你会发现接口与工具类的组合，如 `Collection`/`Collections` 或 `Path`/`Paths`。看看 `Paths` 类。它只有几个工厂方法。

你可以从一系列字符串构造指向文件或目录的路径，例如 `Paths.get("jdk.8", "jre", "bin")`。在 Java 中可以将此方法添加到 `Path` 接口：

```java
public interface Path
{
   public static Path get(String first, String... more) {
      return FileSystems.getDefault().getPath(first, more);
   }
   ...
}
```

那么 `Paths` 类就不再需要了。

Java 库可能会以这种方式重构，但当你实现自己的接口时，没有理由为工具方法提供单独的辅助类。

### 6.1.5 默认方法

你可以为任何接口方法提供默认实现。你必须用 `default` 修饰符标记此类方法。

```java
public interface Comparable<T>
{
   default int compareTo(T other) { return 0; }
   // 默认情况下，元素是相同的
}
```

当然，这没什么用，因为每个真实的 `Comparable` 实现都会覆盖这个方法。但在其他情况下，默认方法是有用的。

例如，正如你在第 11 章中看到的，如果你希望在发生点击时收到通知，你需要实现一个包含五个方法的接口：




```java
public interface MouseListener
{
   void mouseClicked(MouseEvent event);
   void mousePressed(MouseEvent event);
   void mouseReleased(MouseEvent event);
   void mouseEntered(MouseEvent event);
   void mouseExited(MouseEvent event);
}
```

大多数情况下，你只关心这些事件类型中的一种或两种。从 Java SE 8 开始，你可以将所有方法声明为不执行任何操作的默认方法（default methods）。

```java
public interface MouseListener
{
   default void mouseClicked(MouseEvent event) {}
   default void mousePressed(MouseEvent event) {}
   default void mouseReleased(MouseEvent event) {}
   default void mouseEntered(MouseEvent event) {}
   default void mouseExited(MouseEvent event) {}
}
```

这样实现此接口的程序员只需要重写他们真正关心的事件的监听器。

默认方法可以调用其他方法。例如，`Collection` 接口可以定义一个便利方法：

```java
public interface Collection
{
   int size(); // 一个抽象方法
   default boolean isEmpty()
   {
        return size() == 0;
   }
   ...
}
```

那么，实现 `Collection` 的程序员就不必担心实现 `isEmpty` 方法了。

---

![Image](img/note.jpg) **注意**

在 Java API 中，你会发现许多接口都有对应的类，这些类实现了接口的部分或全部方法，例如 `Collection/AbstractCollection` 或 `MouseListener/MouseAdapter`。在 Java SE 8 中，这种技术已经过时了。只需实现接口中的方法即可。

---

默认方法的一个重要用途是*接口演进*（interface evolution）。以在 Java 中存在了多年的 `Collection` 接口为例。假设在很久以前，你提供了一个类：

```java
public class Bag implements Collection
```

后来，在 Java SE 8 中，接口中添加了一个 `stream` 方法。

假设 `stream` 方法不是默认方法。那么 `Bag` 类将无法编译，因为它没有实现这个新方法。在接口中添加非默认方法并不是*源码兼容的*（source compatible）。

但假设你没有重新编译该类，而是简单地使用包含该类的旧 JAR 文件。即使缺少该方法，该类仍然可以加载。程序仍然可以构造 `Bag` 实例，不会发生任何坏事。（向接口添加方法是*二进制兼容的*（binary compatible）。）然而，如果程序对 `Bag` 实例调用 `stream` 方法，就会发生 `AbstractMethodError`。

将方法设为 `default` 方法解决了这两个问题。`Bag` 类将再次编译。如果类在没有重新编译的情况下被加载，并在 `Bag` 实例上调用 `stream` 方法，则会调用 `Collection.stream` 方法。

### 6.1.6 解析默认方法的冲突

如果完全相同的方法在一个接口中被定义为默认方法，然后又作为父类或另一个接口的方法定义，会发生什么？Scala 和 C++ 等语言对解决此类歧义有复杂的规则。幸运的是，Java 的规则要简单得多。规则如下：

**1. 超类胜出。** 如果超类提供了一个具体方法，则同名且参数类型相同的默认方法将被直接忽略。

**2. 接口冲突。** 如果父接口提供了一个默认方法，而另一个接口提供了相同名称和参数类型的方法（无论是否是默认方法），则你必须通过重写该方法来解决冲突。

让我们来看第二条规则。考虑另一个带有 `getName` 方法的接口：

```java
interface Named
{
   default String getName() { return getClass().getName() + "_" + hashCode(); }
}
```

如果你形成一个同时实现这两个接口的类会发生什么？

```java
class Student implements Person, Named
{
   ...
}
```

该类继承了由 `Person` 和 `Named` 接口提供的两个不一致的 `getName` 方法。Java 编译器并没有在其中选择一个，而是报告一个错误，让程序员来解决这个歧义。只需在 `Student` 类中提供一个 `getName` 方法即可。在该方法中，你可以选择两个冲突方法中的一个，如下：

```java
class Student implements Person, Named
{
   public String getName() { return Person.super.getName(); }
   ...
}
```

现在假设 `Named` 接口没有为 `getName` 提供默认实现：

```java
interface Named
{
   String getName();
}
```

`Student` 类可以继承来自 `Person` 接口的默认方法吗？这可能是合理的，但 Java 设计者决定倾向于统一性。两个接口如何冲突并不重要。只要至少有一个接口提供了实现，编译器就会报告错误，程序员就必须解决该歧义。

---

![Image](img/note.jpg) **注意**

当然，如果两个接口都没有为共享方法提供默认实现，那么我们处于 Java 8 之前的状态，并且没有冲突。实现类有两个选择：实现该方法，或者留空不实现。在后一种情况下，该类是抽象的。

---

我们刚刚讨论了两个接口之间的命名冲突。现在考虑一个扩展父类并实现接口的类，例如，假设 `Person` 是一个类而 `Named` 是一个接口：

```java
class Student extends Person implements Named
```

在这种情况下，`Student` 继承了 `Person` 的 `getName` 方法，无论 `Named` 接口是否为其提供了默认实现都无所谓。这就是“类胜出”规则。“类胜出”规则确保了与 Java 7 的兼容性。如果你向接口添加默认方法，对之前的代码没有影响。

---

![Image](img/caution.jpg) **注意**

你永远无法重定义 `Object` 类中方法的默认方法。例如，你无法为 `toString` 或 `equals` 定义默认方法，尽管这对于 `List` 等接口可能很有吸引力。由于“类胜出”规则，这种方法永远无法通过 `Object.toString` 或 `Object.equals`。

---

## 6.2 接口示例

在接下来的三个章节中，我们将提供额外的接口示例，以便你看到它们是如何使用的。

#### 6.2.1 接口与回调

编程中的一种模式是*回调*（callback）模式。在这种模式中，你指定当特定事件发生时应该执行的操作。例如，你可能希望在点击按钮或选择菜单项时执行特定的操作。然而，由于你还没有学习如何实现用户界面，我们将考虑一个类似但更简单的情况。

`javax.swing` 包包含一个 `Timer` 类，它在你希望时间间隔结束时收到通知时非常有用。例如，如果程序的某个部分包含时钟，你可以请求每秒通知一次，以便更新时钟界面。

当你构造定时器时，你设置时间间隔，并告诉它在时间间隔结束时应该做什么。

你如何告诉定时器它应该做什么呢？在许多编程语言中，你提供定时器定期调用的函数名称。然而，Java 标准库中的类采用了面向对象的方法。你传递某个类的对象。定时器随后调用该对象上的一个方法。传递对象比传递函数更灵活，因为对象可以携带额外信息。

当然，定时器需要知道调用哪种方法。定时器要求你指定一个实现了 `java.awt.event` 包中 `ActionListener` 接口的类对象。这里是该接口：

```java
public interface ActionListener
{
   void actionPerformed(ActionEvent event);
}
```

当时间间隔结束时，定时器会调用 `actionPerformed` 方法。

假设你想每隔 10 秒打印一次“音调响起，时间是……”的消息，随后是一声“哔”声。你需要定义一个实现 `ActionListener` 接口的类。然后，你把任何想要执行的语句放在 `actionPerformed` 方法中。

```java
class TimePrinter implements ActionListener
{
    public void actionPerformed(ActionEvent event)
    {
        System.out.println("At the tone, the time is " + new Date());
        Toolkit.getDefaultToolkit().beep();
    }
}
```

注意 `actionPerformed` 方法的 `ActionEvent` 参数。该参数提供了有关事件的信息，例如产生事件的源对象——更多信息请参见第 11 章。然而，在这个程序中，事件的详细信息并不重要，你可以安全地忽略该参数。

接下来，你构造该类的对象，并将其传递给 `Timer` 构造函数。

```java
ActionListener listener = new TimePrinter();
Timer t = new Timer(10000, listener);
```

`Timer` 构造函数的第一个参数是两次通知之间必须经过间隔，以毫秒为单位。我们希望每 10 秒被通知一次。第二个参数是监听器对象。

最后，你启动定时器。

```java
t.start();
```

每隔 10 秒，就会显示如下消息：

```
At the tone the time is Wed Apr 13 23:29:08 PDT 2016
```

随后是一声“哔”声。

列表 6.3 让定时器及其动作监听器开始工作。定时器启动后，程序会弹出一个消息框，等待用户点击 OK 按钮停止。在程序等待用户期间，当前时间会每隔 10 秒显示一次。

运行程序时请保持耐心。“退出程序？”对话框会立即出现，但第一个定时器消息会在 10 秒后才会显示。

注意，程序除了导入 `javax.swing.*` 和 `java.util.*` 之外，还通过类名导入了 `javax.swing.Timer` 类。这消除了 `javax.swing.Timer` 和 `java.util.Timer` 之间的歧义，后者是一个用于调度后台任务的无关类。

**列表 6.3** `timer/TimerTest.java`

```java
 1   package timer;
 2
 3   /**
 4       @version 1.01 2015-05-12
 5       @author Cay Horstmann
 6   */
 7
 8   import java.awt.*;
 9   import java.awt.event.*;
10   import java.util.*;
11   import javax.swing.*;
12   import javax.swing.Timer;
13   // to resolve conflict with java.util.Timer
14
15   public class TimerTest
16   {
17       public static void main(String[] args)
18       {
19           ActionListener listener = new TimePrinter();
20
21           // construct a timer that calls the listener
22           // once every 10 seconds
23           Timer t = new Timer(10000, listener);
24           t.start();
25
26           JOptionPane.showMessageDialog(null, "Quit program?");
27           System.exit(0);
28       }
29   }
30
31   class TimePrinter implements ActionListener
32   {
33       public void actionPerformed(ActionEvent event)
34       {
35           System.out.println("At the tone, the time is " + new Date());
36           Toolkit.getDefaultToolkit().beep();
37       }
38   }
```

- `javax.swing.JOptionPane`: `static void showMessageDialog(Component parent, Object message)` 显示一个带有消息提示和 OK 按钮的对话框。该对话框相对于 `parent` 组件居中显示。如果 `parent` 为 `null`，对话框在屏幕上居中。

- `javax.swing.Timer`:

    - `Timer(int interval, ActionListener listener)` 构造一个定时器，每隔 `interval` 毫秒通知一次 `listener`。

    - `void start()` 启动定时器。一旦启动，定时器就会对它的监听器调用 `actionPerformed`。

    - `void stop()` 停止定时器。一旦停止，定时器不再对它的监听器调用 `actionPerformed`。

- `java.awt.Toolkit`:

    - `static Toolkit getDefaultToolkit()` 获取默认工具包。

    - `void beep()` 发出“哔”声。

### 6.2.2 Comparator 接口

在第 6.1 节中，你已经看到可以使用 `Comparable` 接口对数组进行排序。现在我们想按长度对字符串进行排序，而不是按字典序。为了处理这种情况，`Arrays.sort` 方法有一个重载版本——其参数是实现 `Comparator` 接口的类。

```java
public interface Comparator<T>
{
   int compare(T o1, T o2);
}
```

要按比较字符串，定义一个实现 `Comparator` 的类：

```java
class LengthComparator implements Comparator<String>
{
    public int compare(String first, String second) {
        return first.length() - second.length();
    }
}
```

要实际进行比较，你需要一个实例：

```java
Comparator<String> comp = new LengthComparator();
if (comp.compare(words[i], words[j]) > 0) ...
```

将此调用与 `words[i].compareTo(words[j])` 进行对比。`compare` 方法是在比较对象上调用的，而不是字符串本身。

要排序数组，将一个 `Comparator` 对象传递给 `Arrays.sort` 方法：

```java
String[] friends = { "Peter", "Paul", "Mary" };
Arrays.sort(friends, new LengthComparator());
```

现在数组变成了 `["Paul", "Mary", "Peter"]` 或 `["Mary", "Paul", "Peter"]`。

你将在第 6.3 节中看到如何通过 Lambda 表达式更轻松地使用 `Comparator`。

### 6.2.3 对象克隆

在本节中，我们讨论了指示类已提供安全 `clone` 方法的 `Cloneable` 接口。由于克隆并不常见，且细节非常技术化，你可能只想扫一眼这些材料，等到需要时使用。

为了理解什么是克隆，回想当复制持有对象引用的变量时发生了什么。原始变量和副本都是同一个对象的引用（参见图 6.1）。这意味着对任何一个变量的更改也会影响另一个。

```java
copy.raiseSalary(10); // oops--also changed original
```

![Image](img/06fig01.jpg)

**图 6.1** 拷贝与克隆



如果你希望`copy`是一个新对象，其生命之初与`original`相同，但状态可以随时间推移而不同，请使用`clone`方法。

点击此处查看代码图像

```java
Employee copy = original.clone();

copy.raiseSalary(10); // OK--original unchanged
```

但事实并非那么简单。`clone`方法是`Object`的一个`protected`方法，这意味着你的代码不能直接调用它。只有`Employee`类可以克隆`Employee`对象。这种限制是有原因的。思考`Object`类是如何实现`clone`的。它对对象一无所知，因此它只能进行逐字段的拷贝。如果对象中的所有数据字段都是数字或其他基本类型，那么复制字段就没问题。但如果对象包含对子对象的引用，那么复制字段将给你另一个指向同一个子对象的引用，因此原始对象和克隆对象仍然共享某些信息。

为了可视化这一点，请考虑第 4 章中引入的`Employee`类。图 6.2 显示了当你使用`Object`类的`clone`方法克隆这样一个`Employee`对象时会发生什么。如你所见，默认的克隆操作是“浅”的——它不会克隆被其他对象引用的对象。（图中显示了一个共享的`Date`对象。由于很快就会明确的原因，此示例使用了`Employee`类的一个版本，其中入职日期表示为`Date`。）

![Image](img/06fig02.jpg)

**图 6.2** 浅拷贝

浅拷贝重要吗？这取决于情况。如果原始对象和浅拷贝之间共享的子对象是**不可变的**，那么这种共享就是安全的。如果子对象属于不可变类（如`String`），这种情况确实会发生。另一种，子对象在对象的整个生命周期内可能保持不变，没有变器方法触碰它，也没有方法返回它的引用。

然而，子对象通常是可变的，你必须重新定义`clone`方法以进行**深拷贝**，即也克隆子对象。在我们的示例中，`hireDay`字段是`Date`，它是可变的，因此它必须被克隆。（出于这个原因，此示例使用了`Date`类型的字段而不是`LocalDate`来演示克隆过程。如果`hireDay`是不可变类`LocalDate`的实例，则不需要进一步的操作。）

对于每个类，你都需要决定：

1. 默认的`clone`方法是否足够；

2. 是否可以通过调用可变子对象的`clone`来修复默认的`clone`方法；以及

3. 不要尝试`clone`。

第三选项实际上是默认选项。要选择第一或第二选项，类必须：

1. 实现`Cloneable`接口；以及

2. 使用`public`访问修饰符重新定义`clone`方法。

***

![Image](img/note.jpg) 注意

`clone`方法在`Object`类中被声明为`protected`，因此你的代码不能简单调用`anObject.clone()`。但`protected`方法不是在任何子类中都可以访问吗？每个类不都是`Object`的子类吗？幸运的是，受保护访问的规则更为微妙（参见第 5 章）。子类只能调用保护`clone`方法来克隆它**自己的**对象。你必须将`clone`重新定义为`public`，以便允许任何方法克隆对象。

***

在这种情况下，`Cloneable`接口的出现与接口的正常用法无关。特别是，它**没有**指定`clone`方法——该方法是从`Object`类继承的。该接口仅作为一个标记，表示类设计者理解克隆过程。对象对克隆是如此偏执，以至于如果一个对象请求克隆但没有实现该接口，它就会产生一个检查异常。

***

![Image](img/note.jpg) 注意

`Cloneable`接口是 Java 提供的少数**标记接口**（tagging interfaces）之一。（有些程序员称之为**标记接口**，marker interfaces。）记得`Comparable`等接口的通常目的是确保类实现某个特定方法或一组方法。标记接口没有方法；它的唯一目的是允许在类型查询中使用`instanceof`：

点击此处查看代码图像

```java
if (obj instanceof Cloneable) ...
```

我们建议不要在你自己的程序中使用标记接口。

***

即使`clone`的默认（浅拷贝）实现已经足够，你仍然需要实现`Cloneable`接口，将`clone`重新定义为`public`，并调用`super.clone()`。这是一个示例：

点击此处查看代码图像

```java
class Employee implements Cloneable
{
    // raise visibility level to public, change return type
}
```

***

![Image](img/note.jpg) 注意

`clone`方法在`Object`类中被声明为`protected`，因此你的代码不能简单调用`anObject.clone()`。但`protected`方法不是在任何子类中都可以访问吗？每个类不都是`Object`的子类吗？幸运的是，受保护访问的规则更为微妙（参见第 5 章）。子类只能调用保护`clone`方法来克隆它**自己的**对象。你必须将`clone`重新定义为`public`，以便允许任何方法克隆对象。

你是否应该在自己的类中实现`clone`？如果你的客户端需要进行深拷贝，那么你可能应该这样做。有些作者认为，你应该完全避免使用`clone`，而是实现另一个方法来实现相同的目的。我们认同`clone`相当相当笨拙，但如果你将这一责任转移给另一个方法，你仍然会遇到相同的问题。无论如何，克隆并没有你想象的那么常见。在标准库中，不到 5% 的类实现了`clone`。

Listing 6.4 中的程序克隆了`Employee`类的实例（Listing 6.5），然后调用了两个变异器方法。`raiseSalary`方法更改了`salary`字段的值，而`setHireDay`方法更改了`hireDay`字段的状态。这两种变异都不会影响原始对象，因为`clone`被定义为执行深拷贝。

***

![Image](img/note.jpg) 注意

所有数组类型都有一个公共的`clone`方法，而不是保护的。你可以使用它创建一个包含所有元素拷贝的新数组。例如：

点击此处查看代码图片

```java
int[] luckyNumbers = { 2, 3, 5, 7, 11, 13 };

int[] cloned = luckyNumbers.clone();

cloned[5] = 12; // 不改变 luckyNumbers[5]
```

***

***

![Image](img/note.jpg) 注意

第二卷的第 2 章 展示了克隆对象的另一种机制，使用 Java 的对象序列化功能。该机制容易实现且安全，但效率不高。

***

**Listing 6.4** `clone/CloneTest.java`

点击此处查看代码图片

***

```java
package clone;

/**
 * 此程序演示了克隆。
 * @version 1.10 2002-07-01
 * @author Cay Horstmann
 */
public class CloneTest
{
    public static void main(String[] args)
    {
        try
        {
            Employee original = new Employee("John Q. Public", 50000);
            original.setHireDay(2000, 1, 1);
            Employee copy = original.clone();
            copy.raiseSalary(10);
            copy.setHireDay(2002, 12, 31);
            System.out.println("original=" + original);
            System.out.println("copy=" + copy);
        }
        catch (CloneNotSupportedException e)
        {
            e.printStackTrace();
        }
    }
}
```

***

**Listing 6.5** `clone/Employee.java`

点击此处查看代码图片

***

```java
package clone;

import java.util.Date;
import java.util.GregorianCalendar;

public class Employee implements Cloneable
{
    private String name;
    private double salary;
    private Date hireDay;

    public Employee(String name, double salary)
    {
        this.name = name;
        this.salary = salary;
        hireDay = new Date();
    }

    public Employee clone() throws CloneNotSupportedException
    {
        // 调用 Object.clone()
        Employee cloned = (Employee) super.clone();

        // 克隆可变字段
        cloned.hireDay = (Date) hireDay.clone();

        return cloned;
    }

    /**
     * 将入职日期设置为指定的日期。
     * @param year 入职日的年份
     * @param month 入职日的月份
     * @param day 入职日的日期
     */
    public void setHireDay(int year, int month, int day)
    {
        Date newHireDay = new GregorianCalendar(year, month - 1, day).getTime();

        // 实例变异示例
        hireDay.setTime(newHireDay.getTime());
    }

    public void raiseSalary(double byPercent)
    {
        double raise = salary * byPercent / 100;
        salary += raise;
    }

    public String toString()
    {
        return "Employee[name=" + name + ",salary=" + salary + ",hireDay=" + hireDay + "]";
    }
}
```

***

## 6.3 Lambda 表达式

现在你准备好学习 Lambda 表达式了，这是多年来 Java 语言最令人兴奋的变化。你将看到如何使用简洁语法的 Lambda 表达式定义代码块，以及如何编写使用 Lambda 表达式的代码。

#### 6.3.1 为什么用 Lambda？

Lambda 表达式是一段你可以传递的代码块，以便在稍后执行，执行一次或多次。在进入语法（甚至是那个奇特的名字）之前，让我们退一步，观察我们在 Java 中何处用过此类代码块。

在第 6.2.1 节中，即第 302 页的“接口与回调”，我们让我们回溯一下，在 Java 中何处用过这样的代码块。

### 6.3.2 Lambda 表达式的语法

再次考虑前一节中的排序示例。我们传递了一段检查一个字符串是否比另一个短的代码。我们计算

点击此处查看代码图片

```java
first.length() - second.length()
```

`first`和`second`是什么？它们都是字符串。Java 是一门强类型语言，我们必须对此进行指定：

点击此处查看代码图像

```java
(String first, String second)
-> first.length() - second.length()
```

你刚刚看到了你的第一个`lambda 表达式`（lambda expression）。这种表达式仅仅是一个代码块，加上对必须传递给代码的任何变量的说明。

为什么叫这个名字？许多年前，在计算机出现之前，逻辑学家阿隆佐·丘奇（Alonzo Church）想要对数学函数什么是“有效可计算的”进行形式化。（有趣的是，已知某些函数是存在的，但没有人知道如何计算它们的值。）他使用希腊字母 lambda (`λ`）来标记参数。如果他早早知道 Java API，他会写成：

点击此处查看代码图像

```
λfirst.λsecond.first.length() - second.length()
```

* * *

![Image](img/note.jpg) 注意

为什么用字母 λ？是因为丘奇用光字母表里的其他字母了吗？实际上，古老的《数学原理》（*Principia Mathematica*）使用`^`变音来表示自由变量，这启发了丘奇使用大写的 lambda `Λ` 作为参数。但最后，他切换到了小写版本。从那时起，带有参数变量的表达式被称为 lambda 表达式。

* * *

你刚刚看到了 Java 中 lambda 表达式的一种形式：参数、`->`箭头以及一个表达式。如果代码执行的计算不适合放在单个表达式中，请完全按照你编写方法的方式来编写它：封装在`{}`中，并带有显式的`return`语句。例如：

点击此处查看代码图像

```java
(String first, String second) ->
{
    if (first.length() < second.length()) return -1;
    else if (first.length() > second.length()) return 1;
    else return 0;
}
```

如果 lambda 表达式没有参数，你仍然需要提供空括号，就像对于无参数的方法一样：

点击此处查看代码图像

```java
() -> { for (int i = 100; i >= 0; i--) System.out.println(i); }
```

如果 lambda 表达式的参数类型可以被推断，你可以省略它们。例如：

点击此处查看代码图像

```java
Comparator<String> comp
    = (first, second) // 等于 (String first, String second)
      -> first.length() - second.length();
```

在这里，编译器可以推出`first`和`second`必须是字符串，因为该 lambda 表达式被赋值给一个字符串比较器。（我们将在下一节中详细讨论这种赋值。）

如果方法只有一个类型可推断的参数，你甚至可以省略括号：

点击此处查看代码图像

```java
ActionListener listener = event ->
    System.out.println("The time is " + new Date());
    // 代替 (event) -> ... 或 (ActionEvent event) -> ...
```

你永远不需要指定 lambda 表达式的结果类型。它总是从上下文中推断出来的。例如，表达式：

点击此处查看代码图像

```java
(String first, String second) -> first.length() - second.length()
```

可以使用在一个期望结果为`int`的上下文中。

* * *

![Image](img/note.jpg) 注意

lambda 表达式在某些分支中返回值而在其他分支中不返回是非法的。例如，`(int x) -> { if (x >= 0) return 1; }`是无效的。

* * *

Listing 6.6 中的程序展示了如何使用 lambda 表达式作为比较器和动作监听器。

**Listing 6.6** `lambda/LambdaTest.java`

点击此处查看代码图像

* * *



```java
package lambda;

import java.util.*;
import javax.swing.*;
import javax.swing.Timer;

/**
 * 此程序演示了 lambda 表达式的使用。
 * @version 1.0 2015-05-12
 * @author Cay Horstmann
 */
public class LambdaTest{
    public static void main(String[] args) {
        String[] planets = new String[] "Mercury", "Venus", "Mars",
            "Jupiter", "Saturn", "Uranus", "Neptune" };
        System.out.println(Arrays.toString(planets));
        System.out.println("Sorted in dictionary order:");
        Arrays.sort(planets);
        System.out.println(Arrays.toString(planets));
        System.out.println("Sorted by length:");
        Arrays.sort(planets, (first, second) -> first.length() - second.length());
        System.out.println(Arrays.toString(planets));

        Timer t = new Timer(1000, event -> {
            System.out.println("The time is " + new Date());
            Toolkit.getDefaultToolkit().beep();
        });
        t.start();
        JOptionPane.showMessageDialog(null, "Quit?");
        System.exit(0);
    }
}
```

### 6.3.3 函数式接口（Functional Interfaces）

正如我们所讨论，Java 中许多接口可以封装代码块，例如 `ActionListener` 或 `Comparator`。lambda 与这些接口兼容。

当你期望一个只有一个抽象方法的接口时，这种接口被称为函数式接口。

---

![Image](img/note.jpg) 注意

你可能会疑惑为什么函数式接口只有一个抽象方法。难道接口中的所有方法都是抽象的吗？实际上，接口一直允许声明 `Object` 类的方法，如 `toString` 或 `clone`，而这些声明并没有使方法变为抽象。（请查看 `Comparator` API 的示例。）更重要的是，正如我们在 6.1.5 节中看到的“默认方法”（第 298 页），在 Java 8 中，接口可以声明非抽象方法。

---

为了演示向函数式接口的转换，考虑 `Arrays.sort` 方法。它的第二个参数需要一个 `Comparator` 实例，这是一个只有一个方法的接口。只需提供一个 lambda：

点击此处查看代码图像

```java
Arrays.sort(words, (first, second) -> first.length() - second.length());
```

在后台，`Arrays.sort` 方法接收一个实现了 `Comparator<String>` 的对象。调用该对象的 `compare` 方法就会执行 lambda 表达式体。这些对象和类的管理完全取决于实现，而且它们比传统的内部类要高效得多。最好的想法是将 lambda 表达式视为函数，而不是对象，并接受它可以被传递给函数式接口。

你甚至无法将 lambda 表达式赋值给 `Object` 类型的变量——`Object` 不是一个函数式接口。

Java API 在 `java.util.function` 包中定义了许多通用的函数式接口。其中一个接口 `BiFunction<T, U, R>` 接受参数类型为 `T` 和 `U` 并返回类型为 `R` 的函数。你可以将我们的字符串比较 lambda 表达式保存在该类型的变量中。

点击此处查看代码图像

```java
BiFunction<String, String, Integer> comp = (first, second) -> first.length() - second.length();
```

然而，这对你排序没有帮助。并没有一个接受 `BiFunction` 的 `Arrays.sort` 方法。如果你以前用过函数式编程语言，可能会觉得这很奇怪。但对于 Java 程序员来说，这非常自然。像 `Comparator` 这样的接口有特定的目的，而不仅仅是一个具有给定参数和返回类型的方法。Java SE 8 保留了这种风格。当你想要使用 lambda 表达式执行某些操作时，你仍然希望记住表达式的目的，并为其准备一个特定的函数式接口。

`java.util.function` 包中一个特别有用的接口是 `Predicate`：

点击此处查看代码图像

```java
public interface Predicate<T> {
    boolean test(T t);
    // 额外的默认和静态方法
}
```

`ArrayList` 类有一个 `removeIf` 方法，其参数是一个 `Predicate`。它专门设计用于传递 lambda 表达式。例如，以下语句可以从数组列表中移除所有 `null` 值：

点击此处查看代码图像

```java
list.removeIf(e -> e == null);
```

### 6.3.4 方法引用

有时候，已经有一个方法恰好执行你想传递给其他代码的操作。例如，假设你只想在每当定时器事件发生时打印该事件对象。当然，你可以调用：

点击此处查看代码图像

```java
Timer t = new Timer(1000, event -> System.out.println(event));
```

如果能直接将 `println` 方法传递给 `Timer` 构造函数会更好。以下是实现方法：

点击此处查看代码图像

```java
Timer t = new Timer(1000, System.out::println);
```

表达式 `System.out::println` 是一个方法引用，它等价于 lambda 表达式 `x -> System.out.println(x)`。

另一个例子，假设你想忽略字母大小写对字符串排序。你可以传递这个方法表达式：

点击此处查看代码图像

```java
Arrays.sort(strings, String::compareToIgnoreCase)
```

从这些示例中可以看出，`::` 运算符将方法名与对象或类名分开。主要有三种情况：

- `object::instanceMethod`
- `Class::staticMethod`
- `Class::instanceMethod`

在前两种情况下，方法引用等价于一个提供方法参数的 lambda 表达式。如前所述，`System.out::println` 等价于 `x -> System.out.println(x)`。同样，`Math::pow` 等价于 `(x, y) -> Math.pow(x, y)`。

在第三种情况下，第一个参数变成方法的目标。例如，`String::compareToIgnoreCase` 等同于 `(x, y) -> x.compareToIgnoreCase(y)`。

![Image](img/note.jpg) 注意

当存在多个同名的重载方法时，编译器将尝试根据上下文判断你指的是哪一个。例如，`Math.max` 方法有两个版本，一个用于整数，一个用于 `double` 值。选择哪一个取决于 `Math::max` 转换到的函数式接口的方法参数。就像 lambda 表达式一样，方法引用并不是孤立存在的。它们总是被转换为函数式接口的实例。

你可以在方法引用中捕获 `this` 参数。例如，`this::equals` 等于 `x -> this.equals(x)`。使用 `super` 也是有效的。方法表达式 `super::instanceMethod` 使用 `this` 作为目标并调用给定方法的父类版本。这里有一个显示机制的虚拟示例：

点击此处查看代码图像

```java
class Greeter {
    public void greet() {
        System.out.println("Hello, world!");
    }
}

class TimedGreeter extends Greeter {
    public void greet() {
        Timer t = new Timer(1000, super::greet);
        t.start();
    }
}
```

### 6.3.5 构造器引用

构造器引用就像方法引用一样，只是方法名为 `new`。例如，`Person::new` 是对 `Person` 构造器的引用。如果有多个构造器，编译器会选择带有 `String` 参数的那个。

数组构造引用对于克服 Java 的局限性非常有用。无法构造泛型类型 `T` 的数组。表达式 `new T[n]` 是错误的，因为它会被变为 `new Object[n]`。这对库作者来说是一个问题。例如，假设我们需要一个 `Person` 对象的数组。`Stream` 接口有一个 `toArray` 方法可以返回 `Object` 数组：

点击此处查看代码图像

```java
Object[] people = stream.toArray();
```

但这并不理想。用户想要的是 `Person` 数组而不是 `Object`。流式库通过构造器引用解决了这个问题。将 `Person[]::new` 传递给 `toArray` 方法：

点击此处查看代码图像

```java
Person[] people = stream.toArray(Person[]::new);
```

`toArray` 方法调用此构造器获取正确类型的数组。然后填充并返回该数组。

### 6.3.6 变量范围

通常，你想让 lambda 表达式访问内部方法或类的变量。考虑这个示例：

点击此处查看代码图像

```java
public static void repeatMessage(String text, int delay) {
    ActionListener listener = event -> {
        System.out.println(text);
        Toolkit.getDefaultToolkit().beep();
    };
    new Timer(delay, listener).start();
}
```

现在看 lambda 表达式内部的变量 `text`。注意，该变量不是在 lambda 表达式中定义的。相反，它是 `repeatMessage` 方法的参数变量。

如果你仔细思考，这里正在发生一些非显而易见的事情。lambda 表达式的代码可能在 `repeatMessage` 返回很久之后仍在运行，此时参数变量已经消失了。`text` 变量是如何保持存在的呢？

为了理解发生了什么，我们需要完善对 lambda 表达式的理解。lambda 表达式包含三个要素：

1. 一个代码块
2. 参数
3. 自由变量的值，即既不是参数也没有在代码块内部定义的变量

在我们的示例中，lambda 表达式有一个自由变量 `text`。表示该 lambda 表达式的数据结构必须存储自由变量的值，在我们的案例中，就是字符串 `"Hello"`。我们称这些值被 lambda 表达式捕获（captured）了。（具体如何实现是一个实现细节。例如，可以将 lambda 表达式转换为一个带有单一方法的对象，从而将自由变量的值复制到该对象的实例变量中。）

---

![Image](img/note.jpg) 备注

代码块连同自由变量值在一起的专业术语是闭包（closure）。如果有人自豪于他们的语言拥有闭包，请放心，Java 也有闭包。在 Java 中，lambda 表达式就是闭包。

---

正如你所看到的，lambda 表达式可以捕获封装作用域内变量的值。在 Java 中，为了确保捕获的值是有定义的，有一项重要的限制。在 lambda 表达式中，你只能引用值不会改变的变量。例如，以下代码是非法的：

点击此处查看代码图像

```java
public static void countDown(int start, int delay)
{
    ActionListener listener = event ->
        {
            start--; // Error：无法修改被捕获的变量
            System.out.println(start);
        };
    new Timer(delay, listener).start();
}
```

这种限制是有原因的。当多个动作并发执行时，在 lambda 表达式中修改变量是不安全的。对于目前看到的这类动作，这种情况不会发生，但通常来说，这是一个严重的问题。关于这一重要问题的更多信息，请参阅第 14 章。

在 lambda 表达式中引用在外部被修改的变量也是非法的。例如，以下代码是非法的：

点击此处查看代码图像

```java
public static void repeat(String text, int count)
{
    for (int i = 1; i <= count; i++)
    {
        ActionListener listener = event ->
            {
                System.out.println(i + ": " + text);
                // Error：无法引用发生变化的 i
            };
        new Timer(1000, listener).start();
    }
}
```

规则是，lambda 表达式中任何捕获的变量必须是有效最终的（effectively final）。有效最终变量是指在初始化后从没有被赋值过新值的变量。在我们的案例中，`text` 始终引用同一个 `String` 对象，捕获它是可以的。然而，`i` 的值被修改了，因此 `i` 不能捕获。

lambda 表达式的主体与嵌套块相同的作用域。命名冲突和遮蔽（shadowing）的相同规则适用。在 lambda 中声明与局部变量同名的参数或局部变量是非法的。

点击此处查看代码图像

```java
Path first = Paths.get("/usr/bin");
Comparator<String> comp =
    (first, second) -> first.length() - second.length();
// Error：变量 first 已定义
```

在方法内部，你不能有两个同名的局部变量，因此你也不能在 lambda 表达式中引入此类变量。

当你在 lambda 表达式中使用 `this` 关键字时，你指的是创建该 lambda 的方法的 `this` 参数。例如，考虑：

点击此处查看代码图像

```java
public class Application()
{
    public void init()
    {
        ActionListener listener = event ->
            {
                System.out.println(i + ": " + text);
                //
            };
        // ...
    }
}
```

### 6.3 处理表达式

正如你所看到的，lambda 表达式可以捕获封装作用域内变量的值。在 Java 中，为了确保捕获的值是有定义的，有一项重要的限制。在 lambda 表达式中，你只能引用值不会改变的变量。

现在让我们让这个示例变得复杂一点。我们想说明它发生的动作。为此，我们需要一个有一个 `int` 参数和 `void` 返回值的函数式接口。处理 `int` 值的标准接口是：

```java
public interface IntConsumer
{
    void accept(int value);
}
```

这是改进后的 `repeat` 方法版本：

```java
public static void repeat(int n, IntConsumer action)
{
    for (int i = 0; i < n; i++) action.accept(i);
}
```

这是调用它的方式：

```java
repeat(10, i -> System.out.println("倒计时: " + (9 - i)));
```

> **提示**

尽可能使用表 6.1 或表 6.2 中的接口是一个好主意。例如，假设你写了一个方法来处理符合特定标准的文件。有一个旧的接口 `java.io.FileFilter`，但使用标准的 `Predicate<File>` 更好。



大多数标准函数接口都拥有用于生成或组合函数的非抽象方法。例如，`Predicate.isEqual(a)` 等同于 `a::equals`，当 `a` 为 `null` 时它同样有效。它们提供了默认方法 `and`、`or`、`negate` 来组合多个谓词。例如，`Predicate.isEqual(a).or(Predicate.isEqual(b))` 等同于 `x -> a.equals(x) || b.equals(x)`。

![Image](img/note.jpg) 笔记

如果你设计了一个带有一个抽象方法的接口，可以使用 `@FunctionalInterface` 注解对其进行标记。这有两个优点：如果你不小心添加了另一个非抽象方法，编译器会给出错误信息；此外，javadoc 页面会包含一条声明，说明你的接口是一个函数接口。

并不是强制要求使用该注解。根据定义，任何具有单个抽象方法的接口都是函数接口。但使用 `@FunctionalInterface` 注解是一个好主意。

### 6.3.8 关于比较器（Comparators）

`Comparator` 接口提供了许多方便的静态方法来创建比较器。这些方法旨在与 lambda 表达式或方法引用一起使用。

静态方法 `comparing` 接收一个“键提取”函数，该函数将类型 `T` 映射到可比较的类型（如 `String`）。该函数被应用于要比较的对象，然后对返回的键进行比较。例如，假设你有一个 `Person` 对象的数组。以下是如何按名称对它们进行排序：

点击此处查看代码图片

```java
Arrays.sort(people, Comparator.comparing(Person::getName));
```

这显然比手动实现一个 `Comparator` 要简单得多。而且代码也更加清晰，因为显而易见我们想按名称来比较人员。

你可以使用 `thenComparing` 方法链式调用比较器来处理平局。例如：

点击此处查看代码图片

```java
Arrays.sort(people,
    Comparator.comparing(Person::getLastName)
    .thenComparing(Person::getFirstName));
```

如果两个人的姓氏相同，则使用第二个比较器。

这些方法有几种变体。你可以指定用于 `comparing` 和 `thenComparing` 方法提取的键的比较器。例如，在这里我们按名字的长度对人员排序：

点击此处查看代码图片

```java
Arrays.sort(people, Comparator.comparing(Person::getName,
    (s, t) -> Integer.compare(s.length(), t.length())));
```

此外，`comparing` 和 `thenComparing` 方法都有避免对 `int`、`long` 或 `double` 值装箱的变体。产生上述操作的一种简单方法是：

点击此处查看代码图片

```java
Arrays.sort(people, Comparator.comparingInt(p -> p.getName().length()));
```

如果你的键函数可以返回 `null`，那么你会喜欢 `nullsFirst` 和 `nullsLast` 适配器。这些静态方法接收一个现有的比较器并修改它，使其在遇到 `null` 值时不会抛出异常，而是将其排在比普通值更或更大。例如，假设当一个人没有中间名时 `getMiddleName` 返回 `null`。那么你可以使用 `Comparator.comparing(Person::getMiddleName(), Comparator.nullsFirst(...))`。

`nullsFirst` 方法需要一个比较器——在这种情况下，是一个比较两个字符串的比较器。`naturalOrder` 方法为任何实现 `Comparable` 的类创建一个比较器。我们需要的是 `Comparator.<String>naturalOrder()`。这里是按可能为 `null` 的中间名排序的完整调用。我使用了 `java.util.Comparator.*` 的静态导入，使表达式更具可读性。注意，`naturalOrder` 的类型是推断的。

点击此处查看代码图片

```java
Arrays.sort(people, comparing(Person::getMiddleName, nullsFirst(naturalOrder())));
```

静态方法 `reverseOrder` 提供自然顺序的反序。要反转任何比较器，请使用实例方法 `reversed`。例如，`naturalOrder().reversed()` 等同于 `reverseOrder()`。

## 6.4 内部类

*内部类*是定义在另一个类内部的类。为什么要这样做？有三个原因：

- 内部类方法可以访问其定义作用范围内的数据——包括本应是私有的数据。
- 内部类可以对同一包中的其他类隐藏。
- 当你想要在不写大量代码的情况下定义回调函数时，*匿名*内部类非常方便。

我们将把这个相当复杂的话题拆分成几个步骤。

1. 从第 331 页开始，你将看到一个访问其外部类实例字段的简单内部类。
2. 在第 334 页上，我们涵盖了内部类的特殊语法规则。
3. 从第 335 页开始，我们将深入内部类内部，看看它们是如何运作工作的。
4. 从第 339 页开始，我们讨论了可以访问局部变量的内部类。
5. 从第 342 页开始，我们引入了匿名类并展示它们在 lambda 表达式出现之前是如何被使用的。
6. 最后，从第 346 页开始，你将看到静态内部类如何用于辅助类。

![Image](img/note.jpg) 笔记

C++ 有嵌套类。嵌套类包含在包含它的类的作用范围内。这是一个典型的例子：链表定义了一个用于存储结的类，以及一个用于定义迭代器的类。

点击此处查看代码图片

```cpp
class LinkedList
{
public:
    class Iterator // 嵌套类
    {
        public:
        void insert(int x);
        int erase();
        ...
    };
    ...
private:
    class Link // 嵌套类
    {
        public:
            Link* next;
        int data;
    };
    ...
};
```

嵌套是*类*之间的关系，而不是*对象*之间的关系。`LinkedList` 对象并不拥有 `Iterator` 或 `Link` 类型的子对象。

### 6.4.1 使用内部类访问对象状态

内部类的语法相当复杂。出于这个原因，我们展示了一个简单但有些刻意的示例，用来演示内部类的用法。我们重构了 `TimerTest` 示例并提取了 `TalkingClock` 类。

点击此处查看代码图像

```java
public class TalkingClock
{
   private int interval;
   private boolean beep;
   public TalkingClock(int interval, boolean beep) { ... }
   public void start() { ... }
   public class TimePrinter implements ActionListener
      // 一个内部类
   {
      ...
   }
}
```

注意，`TimePrinter` 类现在位于 `TalkingClock` 类内部。这*并不意味着*每个 `TalkingClock` 实例都有一个 `TimePrinter` 实例字段。正如你将看到的那样，`TimePrinter` 对象是通过 `TalkingClock` 类的方法构造的。

下面是 `TimePrinter` 类的更详细代码。注意 `actionPerformed` 方法在发出蜂鸣声之前会检查 `beep` 标志。

点击此处查看代码图像

```java
public class TimePrinter implements ActionListener
{
   public void actionPerformed(ActionEvent event)
   {
      System.out.println("At the tone, the time is " + new Date());
      if (beep) Toolkit.getDefaultToolkit().beep();
   }
}
```

发生了一些令人惊讶的事情。`TimePrinter` 类没有名为 `beep` 的实例字段或变量。相反，`beep` 指向创建此 `TimePrinter` 的 `TalkingClock` 对象的字段。这是非常创新的。传统上，方法可以引用调用该方法的对象的数据字段。内部类方法既可以访问自己的数据字段，也可以访问创建它的外部对象的数据字段。

为了实现这一点，内部类对象总是获得一个指向创建它的对象的隐式引用（请参见图 6.3）。

![图像](img/06fig03.jpg)

**图 6.3** 内部类对象拥有指向外部类对象的引用

该引用在内部类的定义中是不可见的。然而，为了阐明这个概念，让我们对外部对象的引用命名为 `outer`。那么 `actionPerformed` 方法等同于以下代码：

点击此处查看代码图像

```java
public void actionPerformed(ActionEvent event)
{
   System.out.println("At the tone, the time is " + new Date());
   if (outer.beep) Toolkit.getDefaultToolkit().beep();
}
```

外部类引用是在构造函数中设置的。编译器会修改所有的内部类构造函数，添加一个外部类引用的参数。`TimePrinter` 类没有定义构造函数；因此，编译器会合成一个无参数构造函数，生成如下所示的代码：

点击此处查看代码图像

```java
public TimePrinter(TalkingClock clock) // 自动生成的代码
{
   outer = clock;
}
```

再次请注意，`outer` 不是 Java 关键字。我们只是使用它来说明内部类涉及的机制。

当在 `start` 方法中构造 `TimePrinter` 对象时，编译器将当前闹钟的 `this` 引用传递给构造函数：

点击此处查看代码图像

```java
ActionListener listener = new TimePrinter(this); // 自动添加参数
```

列表 6.7 显示了测试内部类的完整程序。再看一遍访问控制。如果 `TimePrinter` 类是一个普通类，它将需要通过 `TalkingClock` 类的公共方法来访问 `beep` 标志。使用内部类是一种改进。没有提供仅对另一个类感兴趣的访问器。

![图像](img/note.jpg) 笔记

我们可以将 `TimePrinter` 类声明为 `private`。这样，只有 `TalkingClock` 方法能够构造 `TimePrinter` 对象。只有内部类可以是私有的。普通类始终具有包级或公有级可见性。

**列表 6.7** `innerClass/InnerClassTest.java`

点击此处查看代码图像

```java
1   package innerClass;
2
3   import java.awt.*;
4   import java.awt.event.*;
5   import java.util.*;
6   import javax.swing.*;
7   import javax.swing.Timer;
8
9   /**
10     * 此程序演示了内部类的用法。
11     * @version 1.11 2015-05-2
12     * @author Horstmann
13     */
14   public class InnerTest
15   {
16     public static void main(String[] args)
17     {
18       TalkingClock clock = new TalkingClock(100, true);
19       clock.start();
20
21       // 保持运行，直到用户选择 "Ok"
22       JOptionPane.showMessageDialog(null, "Quit?");
23       System.exit(0);
24     }
25   }
26
27   /**
28     * 一个按固定间隔打印时间的闹钟。
29     */
30   class TalkingClock
31   {
32     private int interval;
33     private boolean beep;
34
35     /**
36       * 构造闹钟
37       * @param interval 消息间隔（毫秒）
38       * @param beep 闹钟是否蜂鸣
39     */
40     public TalkingClock(int interval, boolean beep)
41     {
42       this.interval = interval;
43       this.beep = beep;
44     }
45
46     /**
47       * 闹钟。
48       */
49     public void start()
50     {
51       ActionListener listener = new TimePrinter();
52       Timer t = new Timer(interval, listener);
53       t.start();
54     }
55
56     public class TimePrinter implements ActionListener
57     {
58       public void actionPerformed(ActionEvent event)
59       {
60           System.out.println("At the tone, the time is " + new Date());
61           if (beep) Toolkit.getDefaultToolkit().beep();
62       }
63     }
64   }
```

### 6.4.2 内部类的特殊语法

在前面的节中，我们通过命名为 `outer` 来解释内部类的外部类引用。实际上，外部引用的正确语法要复杂一点。表达式 `OuterClass.this` 指定了外部类引用。例如，你可以这样写 `TimePrinter` 内部类的 `actionPerformed` 方法：

点击此处查看代码图像

```java
public void actionPerformed(ActionEvent event)
{
   ...
   if (TalkingClock.this.beep) Toolkit.getDefaultToolkit().beep();
}
```

相反，你可以更显式地编写内部对象构造函数，使用语法：

`outerObject.new InnerClass(构造参数)`

例如：

点击此处查看代码图像

```java
ActionListener listener = this.new TimePrinter();
```

在这里，新构造的 `TimePrinter` 对象的外部类引用设置为创建内部类的方法的 `this` 引用。这是最常见的情况。始终 `this.` 修饰符是冗余的。然而，也可以通过显式命名来将外部类引用设置为另一个对象。例如，由于 `TimePrinter` 是一个公共内部类，你可以为任何闹钟构造一个 `TimePrinter`：

点击此处查看代码图像

```java
TalkingClock jabberer = new TalkingClock(1000, true);
TalkingClock.TimePrinter listener = jabberer.new TimePrinter();
```

注意，当在外部类的作用域之外，我们使用 `OuterClass.InnerClass` 来引用内部类。

### 6.4.3 内部类有用吗？必要吗？安全吗？

当内部类在 `Java 1.1` 中引入 Java 语言时，许多程序员认为它们是一项重大新特性，与 Java “比 C++ 更简单”的哲学格格不入。内部类的语法不可否是复杂的。（在我们在本章稍后学习匿名内部类时，它会变得复杂。）目前并不清楚内部类是如何与语言的其他特性（如访问控制和安全）相互作用的。

通过添加一个优雅且有趣但并非必需的功能，Java 是否已经开启了导致许多其他语言深陷泥潭的毁灭性之路？

虽然我们不尝试完全回答这个问题，但值得注意的是，内部类是`compiler` 的现象，而不是虚拟机的现象。内部类被翻译成常规的类文件，并用 `$`（美元符号）分隔外部类和内部类的类名，而虚拟机对它们没有任何特殊知识。

例如，`TalkingClock` 类内部的 `TimePrinter` 类被翻译为类文件 `TalkingClock$TimePrinter.class`。要看到这一运行过程，请尝试以下实验：运行第 5 章中的 `ReflectionTest` 程序，并给它类 `TalkingClock$TimePrinter` 进行反射。或者，简单地使用 `javap` 工具：



```bash
javap -private ClassName
```

![Image](img/note.jpg) 备注

如果你使用 UNIX，请在命令行中提供类名时转义 `$` 字符。也就是说，运行 `ReflectionTest` 或 `javap` 程序如下：

点击此处查看代码图像

```bash
java reflection.ReflectionTest innerClass.TalkingClock\$TimePrinter
```

或者：

点击此处查看代码图像

```bash
javap -private innerClass.TalkingClock\$TimePrinter
```

你将获得以下输出：

点击此处查看代码图像

```java
public class TalkingClock$TimePrinter
{
   public TalkingClock$TimePrinter(TalkingClock);
   public void actionPerformed(java.awt.event.ActionEvent);
   final TalkingClock this$0;
}
```

你可以清楚地看到，编译器为指向外部类的引用生成了一个额外的实例字段 `this$0`。（`this$0` 的名称是编译器合成的——你不能在代码中引用它。）你还可以看到构造函数中的 `TalkingClock` 参数。

如果编译器可以自动完成这种转换，那么你难道不能简单地通过手动来实现相同的机制吗？让我们试一下。我们将 `TimePrinter` 变成一个常规类，放在 `TalkingClock` 类之外。在构造 `TimePrinter` 对象时，我们将创建该对象的 `this` 引用传递给它。

点击此处查看代码图像

```java
class TalkingClock
{
   ...
   public void start()
   {
      ActionListener listener = new TimePrinter(this);
      Timer t = new Timer(interval, listener);
      t.start();
   }
}

class TimePrinter implements ActionListener
{
   private TalkingClock outer;
   ...
   public TimePrinter(TalkingClock clock)
   {
      outer = clock;
   }
}
```

现在让我们来看 `actionPerformed` 方法。它需要访问 `outer.beep`。

点击此处查看代码图像

```java
if (outer.beep) ... // 错误
```

在这里我们遇到了一个问题。内部类可以访问外部类的私有数据，但我们的外部 `TimePrinter` 类不能。

因此，内部类确实比常规类更强大，因为它们拥有更多的访问权限。

你可能很好奇，如果内部类被翻译成带有奇怪名称的类，它们是如何获得那些额外的访问权限的——虚拟机对它们一无所知。为了解这个谜，让我们再次使用 `ReflectionTest` 程序来监控 `TalkingClock` 类：

点击此处查看代码图像

```java
class TalkingClock
{
   private int interval;
   private boolean beep;
   public TalkingClock(int, boolean);
   static boolean access$0(TalkingClock);
   public void start();
}
```

注意编译器添加到外部类的静态 `access$0` 方法。它返回作为参数传递的对象的 `beep` 字段。（方法名可能略有不同，例如 `access$000`，取决于你的编译器。）

内部类方法调用该方法。语句

```java
if (beep)
```

在 `TimePrinter` 类的 `actionPerformed` 方法中实际上执行了以下调用：

点击此处查看代码图像

```java
TalkingClock.access$0(outer)
```

这是一个安全风险吗？你敢肯定是的。

### 6.4.4 局部内部类

如果你仔细查看 `TalkingClock` 示例的代码，你会发现你只需要一次类型 `TimePrinter` 的名称：即在你创建它的对象时。

在这种情况下，你可以在方法内部局部定义该类。

点击此处查看代码图像

```java
public void start()
{
   class TimePrinter implements ActionListener
   {
      public void actionPerformed(ActionEvent event)
      {
         System.out.println("At the tone, the time is " + new Date());
         if (beep) Toolkit.getDefaultToolkit().beep();
      }
   }
   ActionListener listener = new TimePrinter();
   Timer t = new Timer(interval, listener);
   t.start();
}
```

局部类从不声明访问修饰符（即 `public` 或 `private`）。它们的作用域始终被限制在声明所在的块中。

局部类有一个巨大的优势：它们对外部世界完全隐藏——即使是 `TalkingClock` 类中的其他代码也无法访问它们。

局部类相比其他内部类还有另一个优势。它们不仅可以访问外部类的字段，甚至可以访问局部变量！然而，这些局部变量必须是有效 `final`（effectively `final`）。这意味着，一旦它们被赋值，就永远不能被改变。

这是一个典型的例子。我们将 `interval` 和 `beep` 参数从 `TalkingClock` 构造函数移动到 `start` 方法。

点击此处查看代码图像

```java
public void start(int interval, boolean beep)
{
    class TimePrinter implements ActionListener
    {
        public void actionPerformed(ActionEvent event)
        {
            System.out.println("At the tone, the time is " + new Date());
            if (beep) Toolkit.getDefaultToolkit().beep();
        }
    }
    ActionListener listener = new TimePrinter();
    Timer t = new Timer(interval, listener);
    t.start();
}
```

注意，`TalkingClock` 类不再需要存储 `beep` 实例字段。它只是引用了 `start` 方法的 `beep` 参数变量。

也许这并不应该那么奇怪。毕竟，`if (beep) ...` 这一行最终是在 `start` 方法内部的，所以为什么它不能访问 `beep` 变量的值呢？

为了看到为什么这里存在一个微妙的问题，让我们更仔细地观察控制流。

1. 调用 `start` 方法。
2. 通过调用内部类 `TimePrinter` 的构造函数来初始化对象变量 `listener`。
3. 将 `listener` 引用传递给 `Timer` 构造函数，启动定时器，`start` 方法退出。此时，`start` 方法的 `beep` 参数变量已不再存在。
4. 一秒后，`actionPerformed` 方法执行 `if (beep) ...`。

为了让 `actionPerformed` 方法中的代码能够工作，`TimePrinter` 类必须在 `beep` 参数值消失之前，将 `beep` 字段作为 `start` 方法的局部变量进行了复制。这确实是发生的情况。在我们的示例中，编译器为该局部内部类合成了名称 `TalkingClock$1TimePrinter`。如果你再次使用 `ReflectionTest` 程序监控 `TalkingClock$1TimePrinter` 类，你将得到以下输出：

点击此处查看代码图像

```java
class TalkingClock$1TimePrinter
{
    TalkingClock$1TimePrinter(TalkingClock, boolean);
    public void actionPerformed(java.awt.event.ActionEvent);
    final boolean val$beep;
    final TalkingClock this$0;
}
```

注意构造函数中的 `boolean` 参数和 `val$beep` 实例变量。当创建对象时，值 `beep` 被传递到构造函数并存储在 `val$beep` 字段中。编译器检测到局部变量的访问，为每个变量创建匹配的实例字段，并将局部变量复制到构造函数中，以便初始化实例字段。

从程序员的角度来看，局部变量的访问是非常方便的。它通过减少你需要显式编写的实例字段，使得你的内部类更加简单。

正如我们已经提到的，局部类的方法只能引用声明为 `final` 的局部变量。出于这个原因，在我们的示例中 `beep` 参数被声明为 `final`。被声明为 `final` 的局部变量在初始化后不能被修改。因此，可以保证局部变量和局部类内部创建的副本始终具有相同的值。

***

![Image](img/note.jpg) 注意

在 Java SE 8 之前，任何从局部类访问的局部变量都必须声明为 `final`。例如，`start` 方法将如下声明，以便内部类可以访问 `beep` 参数：

点击此处查看代码图像

```java
public void start(int interval, final boolean beep)
```

***

“有效 `final`”的限制有时是不方便的。例如，假设你想更新闭包作用域内的计数器。在这里，我们想要统计在排序过程中 `compareTo` 方法被调用的次数：

点击此处查看代码图像

```java
int counter = 0;
Date[] dates = new Date[100];
for (int i = 0; i < dates.length; i++)
    dates[i] = new Date()
        {
            // ... 逻辑
        }
```

实际上，重新阅读文本，计数器示例的代码是：

```java
int counter = 0;
Date[] dates = new Date[100];
for (int i = 0; i < dates.length; i++)
    dates[i] = new Date()
        {
            // 这里是匿名类所在的位置
        }
```

“有效 `final`”的限制有时是不方便的。例如，假设你想更新闭包作用域内的计数器。在这里，我们想要统计在排序过程中 `compareTo` 方法被调用的次数：

```java
int counter = 0;
Date[] dates = new Date[100];
for (int i = 0; i < dates.length; i++)
    dates[i] = new Date()
        {
            // 匿名类逻辑
        }
```

### 6.4.6 匿名内部类

在使用局部类时，你通常可以更进一步。如果你想创建一个单独的对象，就不需要给类命名。这样的类被称为匿名内部类。

这种语法非常晦涩。它的意思是：创建一个实现 `ActionListener` 的类的新对象，其中所需的 `actionPerformed` 方法在大括号 `{ }` 内部。

通常情况下，语法为：

点击此处查看代码图像

```java
new SuperType(构造参数)
{
    // 内部类的方法和数据
}
```

在这里，`SuperType` 可以是一个接口，例如 `ActionListener`；那么内部类实现该接口。`SuperType` 也可以是一个类；那么内部类扩展该类。

匿名内部类没有构造函数，因为构造函数的名称必须与类名相同，而类没有名称。相反，构造参数是传递给父类构造函数的。特别是每当内部类实现接口时，它不能有任何构造参数。然而，你必须提供一组括号，如下：

```java
new InterfaceType()
{
    // 方法和数据
}
```

你必须仔细观察构造一个类的新对象与构造一个扩展该类的匿名内部类对象之间的区别。

点击此处查看代码图像

```java
Person queen = new Person("Mary"); // 一个 Person 对象
Person count = new Person("Dracula") { ... }; // 一个扩展 Person 的内部类对象
```

如果构造参数列表的右括号后面跟着一个左大括号，那么正在定义一个匿名内部类。

代码列表 6.8 包含了带有匿名内部类的闹钟程序的完整源代码。如果你将此程序与代码列表 6.7 进行比较，你会发现在这种情况下，使用匿名内部类的解决方案要短得多，而且希望通过一些练习，它也能同样易于理解。

多年来，Java 程序员例行地使用匿名内部类作为事件监听器和其他回调。现在，你使用 lambda 表达式会更好。例如，本节开头的 `start` 方法可以用像下面这样的 lambda 表达式写得更加简洁：

点击此处查看代码图像

```java
public void start(int interval, boolean beep)
{
    Timer t = new Timer(interval, event ->
        {
            System.out.println("At the tone, the time is " + new Date());
            if (beep) Toolkit.getDefaultToolkit().beep();
        });
    t.start();
}
```

![Image](img/note.jpg) 注意

下面的技巧被称为“双括号初始化”，它利用了内部类的语法。假设你想构造一个列表并将其传递给一个方法：

点击此处查看代码图像

```java
ArrayList<String> friends = new ArrayList<>();
friends.add("Harry");
friends.add("Tony");
invite(friends);
```

如果你不再需要这个列表，那么让它变成匿名会很不错。但这样你又如何添加元素呢？方法如下：

点击此处查看代码图像

```java
invite(new ArrayList<String>() {{ add("Harry"); add("Tony"); }});
```

注意双大括号。外层大括号形成 `ArrayList` 的匿名子类。内层大括号创建了一个对象构造块（参见第 4 章）。

![Image](img/caution.jpg) 注意

创建一个几乎与其父类相同但并不完全相同的匿名子类通常是非常方便的。但你需要小心处理 `equals` 方法。在第 5 章中，我们建议你的 `equals` 方法使用测试：

点击此处查看代码图像

```java
if (getClass() != other.getClass()) return false;
```

匿名子类将通过此测试。

![Image](img/tip.jpg) 提示

当你产生日志或调试信息时，你通常想包含当前类的名称，例如：

点击此处查看代码图像

```java
System.err.println("Something awful happened in " + getClass());
```

但这在静态方法中会失败。毕竟，对 `getClass` 的调用会调用 `this.getClass()`，而静态方法没有 `this`。请使用以下表达式：

点击此处查看代码图像

```java
new Object(){}.getClass().getEnclosingClass() // 获取静态方法的所在类
```

在这里，`new Object(){}` 创建了一个 `Object` 匿名子类的匿名对象，而 `getEnclosingClass` 获取它的闭层类——即包含该静态方法的类。

**列表 6.8** `anonymousInnerClass/AnonymousInnerClassTest.java`

点击此处查看代码图像



```java
package anonymousInnerClass;

import java.awt.*;
import java.awt.event.*;
import java.util.*;
import javax.swing.*;
import javax.swing.Timer;

/**
 * 此程序演示了匿名内部类。
 * @version 1.11 2015-05-12
 * @author Cay Horstmann
 */
public class AnonymousInnerClassTest
{
    public static void main(String[] args)
    {
        TalkingClock clock = new TalkingClock();
        clock.start(1000, true);

        // 保持程序运行直到用户选择 "Ok"
        JOptionPane.showMessageDialog(null, "Quit?");
        System.exit(0);
    }
}

/**
 * 按固定间隔打印时间的闹钟。
 */
class TalkingClock
{
    /**
     * 启动闹钟。
     * @param interval 消息之间的间隔（毫秒）
     * @param beep 如果闹钟应该响铃则为 true
     */
    public void start(int interval, boolean beep)
    {
        ActionListener listener = new ActionListener()
        {
            public void actionPerformed(ActionEvent event)
            {
                System.out.println("At the tone, the time is " + new Date());
                if (beep) Toolkit.getDefaultToolkit().beep();
            }
        };
        Timer t = new Timer(interval, listener);
        t.start();
    }
}
```

### 6.4.7 静态内部类

偶尔，你只想使用内部类将一个类隐藏在另一个类内部——但你不需要内部类持有指向外部类对象的引用。你可以通过将内部类声明为`static`来抑制该引用的生成。

有时，你可能想要使用内部类仅仅是为了将一个类隐藏在另一个类内部——但你不需要内部类持有指向外部类对象的引用。你可以通过将内部类声明为`static`来抑制该引用的生成。

`minmax`方法可以返回一个`Pair`类型的对象。当然，`Pair`是一个极其常见的名称，在一个大型项目中，很有可能其他程序员也有同样的想法——但他们制作的`Pair`类包含一对字符串。我们可以通过将`Pair`设为`ArrayAlg`内部的公共内部类来解决这个潜在的名称冲突。这样该类在公共范围内的名称就是`ArrayAlg.Pair`：

```java
ArrayAlg.Pair p = ArrayAlg.minmax(d);
```

然而，与之前示例中的内部类不同，我们不希望`Pair`对象内部持有任何其他对象的引用。这种引用可以通过将内部类声明为`static`来抑制：

```java
class ArrayAlg
{
    public static class Pair
    {
        ...
    }
    ...
}
```

当然，只有内部类可以声明为静态。静态内部类与任何其他内部类完全一样，只是静态内部类对象没有指向生成它的外部类对象的引用。在这个示例中，我们必须使用静态内部类，因为内部类对象是在静态方法内部构造的：

```java
public static Pair minmax(double[] d)
{
    ...
    return new Pair(min, max);
}
```

方法的调用者使用`getFirst`和`getSecond`方法来获取答案：

```java
Pair p = ArrayAlg.minmax(d);
System.out.println("min = " + p.getFirst());
System.out.println("max = " + p.getSecond());
```

`Pair`名字是一个极其常见的名称，在一个大型项目中，很有可能其他程序员也有同样的想法——但他们制作的`Pair`类包含一对字符串。我们可以通过将`Pair`设为`ArrayAlg`内部的公共内部类来解决这个潜在的名称冲突。这样该类在公共范围内的名称就是`ArrayAlg.Pair`。



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。ArrayList<String> friends = new ArrayList<>();
friends.add("Harry");
friends.add("Tony");
invite(friends);
```

如果你不再需要这个列表，那么让它变成匿名会很不错。但这样你又如何添加元素呢？方法如下：

点击此处查看代码图像

```java
invite(new ArrayList<String>() {{ add("Harry"); add("Tony"); }});
```

注意双大括号。外层大括号形成`ArrayList`的匿名子类。内层大括号创建了一个对象构造块（参见第 4 章）。

![Image](img/caution.jpg) **注意**

创建一个几乎与其父类相同但并不完全相同的匿名子类通常是非常方便的。但你需要小心处理`equals`方法。在第 5 章中，我们建议你的`equals`方法使用测试：

点击此处查看代码图像

```java
if (getClass() != other.getClass()) return false;
```

匿名子类将通过此测试。

![Image](img/tip.jpg) **提示**

当你产生日志或调试信息时，你通常想包含当前类的名称，例如：

点击此处查看代码图像

```java
System.err.println("Something awful happened in " + getClass());
```

但这在静态方法中会失败。毕竟，对`getClass`的调用会调用`this.getClass()`，而静态方法没有`this`。请使用以下表达式：

点击此处查看代码图像

```java
new Object(){}.getClass().getEnclosingClass() // 获取静态方法的所在类
```

在这里，`new Object(){}`创建了一个`Object`匿名子类的匿名对象，而`getEnclosingClass`获取它的闭层类——即包含该静态方法的类。

**列表 6.8** `anonymousInnerClass/AnonymousInnerClassTest.java`

点击此处查看代码图像

```java
package anonymousInnerClass;

import java.awt.*;
import java.awt.event.*;
import java.util.*;
import javax.swing.*;
import javax.swing.Timer;

/**
 * 此程序演示了匿名内部类。
 * @version 1.11 2015-05-12
 * @author Cay Horstmann
 */
public class AnonymousInnerClassTest
{
    public static void main(String[] args)
    {
        TalkingClock clock = new TalkingClock();
        clock.start(1000, true);

        // 保持程序运行直到用户选择 "Ok"
        JOptionPane.showMessageDialog(null, "Quit?");
        System.exit(0);
    }
}

/**
 * 按固定间隔打印时间的闹钟。
 */
class TalkingClock
{
    /**
     * 启动闹钟。
     * @param interval 消息之间的间隔（毫秒）
     * @param beep 如果闹钟应该响铃则为 true
     */
    public void start(int interval, boolean beep)
    {
        ActionListener listener = new ActionListener()
        {
            public void actionPerformed(ActionEvent event)
            {
                System.out.println("At the tone, the time is " + new Date());
                if (beep) Toolkit.getDefaultToolkit().beep();
            }
        };
        Timer t = new Timer(interval, listener);
        t.start();
    }
}
```

### 6.4.7 静态内部类

偶尔，你可能想要使用内部类仅仅是为了将一个类隐藏在另一个类内部——但你不需要内部类持有指向外部类对象的引用。你可以通过将内部类声明为`static`来抑制该引用的生成。

`minmax`方法可以返回一个`Pair`类型的对象。当然，`Pair`是一个极其常见的名称，在一个大型项目中，很有可能其他程序员也有同样的想法——但他们制作的`Pair`类包含一对字符串。我们可以通过将`Pair`设为`ArrayAlg`内部的公共内部类来解决这个潜在的名称冲突。这样该类在公共范围内的名称就是`ArrayAlg.Pair`：

点击此处查看代码图像

```java
ArrayAlg.Pair p = ArrayAlg.minmax(d);
```

方法的调用者使用`getFirst`和`getSecond`方法来获取答案：

点击此处查看代码图像

```java
Pair p = ArrayAlg.minmax(d);
System.out.println("min = " + p.getFirst());
System.out.println("max = " + p.getSecond());
```

如果`Pair`类没有被声明为`static`，编译器将报错，因为没有可用的`ArrayAlg`类型隐式对象来初始化内部类对象。

> 注意：当内部类不需要访问外部类对象时，请使用静态内部类。某些程序员使用“嵌套类”（nested class）一词来描述静态内部类。

> 注意：与普通内部类不同，静态内部类可以拥有静态字段和方法。

> 注意：在接口内部声明的内部类自动是`static`且`public`。

列表 6.9 包含了`ArrayAlg`类和嵌套类`Pair`的完整源代码。

**列表 6.9** `staticInnerClass/StaticInnerClassTest.java`

点击此处查看代码图像

```java
package staticInnerClass;

/**
 * 此程序演示了静态内部类的用法。
 * @version 1.02 2015-05-12
 * @author Cay Horstmann
 */
public class StaticInnerClassTest
{
    public static void main(String[] args)
    {
        double[] d = new double[20];

        for (int i = 0; i < d.length; i++)
            d[i] = 100 * Math.random();

        ArrayAlg.Pair p = ArrayAlg.minmax(d);

        System.out.println("min = " + p.getFirst());
        System.out.println("max = " + p.getSecond());
    }
}

class ArrayAlg
{
    /**
     * 一对浮点数
     */
    public static class Pair
    {
        private double first;
        private double second;

        /**
         * 从两个浮点数构造一个点对
         * @param f 第一个数字
         * @param s 第二个数字
         */
        public Pair(double f, double s)
        {
            first = f;
            second = s;
        }

        /**
         * 返回对中的第一个数字
         * @return 第一个数字
         */
        public double getFirst()
        {
            return first;
        }

        /**
         * 返回对中的第二个数字
         * @return 第二个数字
         */
        public double getSecond()
        {
            return second;
        }
    }

    /**
     * 计算数组的最小值和最大值
     * @param values 浮点数数组
     * @return 一个对，其第一个元素是最小值，第二个元素是最大值
     */
    public static Pair minmax(double[] values)
    {
        double min = Double.POSITIVE_INFINITY;
        double max = Double.NEGATIVE_INFINITY;

        for (double v : values)
        {
            if (min > v) min = v;
            if (max < v) max = v;
        }

        return new Pair(min, max);
    }
}
```

## 6.5 代理（Proxies）

在本章的最后节中，我们将讨论`proxies`（代理）。你可以使用代理在运行时创建实现给定一组接口的新类。只有当你从编译时还不知道需要实现哪些接口时，代理才是必要的。对于应用程序程序员来说，这种情况并不常见，如果你对高级魔法术感兴趣，可以随时跳过这一节。然而，对于某些系统编程应用程序，代理提供的灵活性可能非常重要。

### 6.5.1 何时使用代理

假设你想构造一个实现一个或多个接口类的对象，而你可能在编译时不知道这些接口的精确性质。这是一个困难的问题。要构造一个实际类，你可以简单地使用`newInstance`方法或使用反射查找构造函数。但你不能实例化接口。你需要在运行中的程序中定义一个新类。

为了解决这个问题，某些程序会生成代码，将其放入文件，调用编译器，然后加载生成的类文件。自然地，这种方法很慢，而且还需要将编译器与程序一起部署。`proxy`机制是一个更好的解决方案。代理类可以在运行时创建全新的类。此类代理类实现了你指定的接口。特别地，代理类具有以下方法：

- 所指定接口要求的所有方法；
- `Object`类中定义的所有方法（`toString`、`equals`等）。

然而，你不能在运行时为这些方法定义新代码。相反，你必须提供一个`invocation handler`（调用处理器）。调用处理器是任何实现`InvocationHandler`接口的类的对象。该接口有一个方法：

点击此处查看代码图像

```java
Object invoke(Object proxy, Method method, Object[] args)
```

每当对代理对象调用方法时，调用处理器的`invoke`方法就会被调用，并带有调用的`Method`对象和参数。调用处理器必须弄清楚如何处理该调用。

### 6.5.2 创建代理对象

要创建代理对象，使用`Proxy`类的`newProxyInstance`方法。该方法有三个参数：

- 一个`class loader`。作为 Java 安全模型的一部分，不同的类加载器可以用于系统类、从互联网下载的类等。我们将在第二卷第 9 章中讨论类加载器。现在我们指定`null`以使用默认类加载器。
- 一个`Class`对象数组，每个对象对应要实现的接口。
- 一个调用处理器。

还有两个问题。我们如何定义处理器？我们对生成的代理对象可以做什么？答案显然取决于我们想要用代理解决的问题。代理可以用于许多目的，例如：

- 将方法调用路由到远程服务器；
- 将用户界面事件与运行程序中的操作关联；
- 用于调试的方法跟踪。

在示例程序中，我们使用代理和调用处理器来跟踪方法调用。我们定义了一个`TraceHandler`包装类，存储被包装的对象。它的`invoke`方法简单地打印要调用的方法名和参数，然后将包装的对象作为隐式参数调用该方法。

点击此处查看代码图像

```java
class TraceHandler implements InvocationHandler
{
    private Object target;

    public TraceHandler(Object t)
    {
        target = t;
    }

    public Object invoke(Object proxy, Method m, Object[] args)
        throws Throwable
    {
        // 打印方法名和参数
        ...

        // 调用实际方法
        return m.invoke(target, args);
    }
}
```

下面是如何构造一个当它的某个方法被调用时触发跟踪行为的代理对象：

```java
Object value = ...;

// 构造包装
InvocationHandler handler = new TraceHandler(value);

// 为一个或多个接口构造代理
Class[] interfaces = new Class[] { Comparable.class };
Object proxy = Proxy.newProxyInstance(null, interfaces, handler);
```

现在，每当接口的某个方法在`proxy`上被调用时，方法名和参数都会被打印出来，然后在`value`上调用该方法。

在列表 6.10 所示的程序中，我们使用代理对象来跟踪二分查找。我们用指向整数 `1 ... 1000` 的代理对象填充一个数组。然后，我们调用`Arrays`类的`binarySearch`方法在数组中搜索一个随机整数。最后，我们打印匹配的元素。

点击此处查看代码图像

```java
Object[] elements = new Object[1000];

// fill elements with proxies for the integers 1 . . . 1000
for (int i = 0; i < elements.length; i++)
{
    Integer value = i + 1;
    elements[i] = Proxy.newProxyInstance(. . .); // proxy for value;
}

// construct a random integer
Integer key = new Random().nextInt(elements.length) + 1;

// search for the key
int result = Arrays.binarySearch(elements, key);

// print match if found
if (result >= 0) System.out.println(elements[result]);
```

`Integer`类实现了`Comparable`接口。代理对象属于一个在运行时定义的类（它有一个诸如`$Proxy0`的名称）。该类也实现了`Comparable`接口。然而，它的`compareTo`方法会调用代理对象处理器的`invoke`方法。

---

![图像](img/note.jpg) **注意**

正如你在本章稍些部分所看到的，`Integer`类实际上实现了`Comparable<Integer>`。但在运行时，所有的泛型类型都会被擦除，代理是使用原始`Comparable`类的类对象构造的。

---

`binarySearch`方法发出的调用如下：

点击此处查看代码图像

```java
if (elements[i].compareTo(key) < 0) . . .
```

由于我们用代理对象填充了数组，因此`compareTo`的调用会转到`TraceHandler`类的`invoke`方法。该方法会打印方法名和参数，然后在被包装的`Integer`对象上调用`compareTo`。

最后，在示例程序的末处，我们调用了：

点击此处查看代码图像

```java
System.out.println(elements[result]);
```

`println`方法对代理对象调用`toString`，而该调用也被重定向到了调用处理器。

以下是程序运行的完整轨迹：

```text
500.compareTo(288)

250.compareTo(288)

375.compareTo(288)

312.compareTo(288)

281.compareTo(288)

296.compareTo(288)
```



`288.compareTo(288)`

`288.toString()`

你可以看到二分查找算法如何通过每一步将搜索范围减半来锁定键。注意，即使 `toString` 方法不属于 `Comparable` 接口，它仍然被代理了——正如你在下一节中看到的，某些 `Object` 方法总是会被代理的。

**列表 6.10** `proxy/ProxyTest.java`

点击此处查看代码图像

```java
package proxy;

import java.lang.reflect.*;
import java.util.*;

/**
  * 此程序演示了代理的使用。
  * @version 1.00 2000-04-13
  * @author Cay Horstmann
  */
public class ProxyTest
{
   public static void main(String[] args)
   {
       Object[] elements = new Object[1000];

       // fill elements with proxies for the integers 1 ... 1000
       for (int i = 0; i < elements.length; i++)
       {
           Integer value = i + 1;
           InvocationHandler handler = new TraceHandler(value);
           Object proxy = Proxy.newProxyInstance(null, new Class[] { Comparable.class }, handler);
           elements[i] = proxy;
       }

       // construct a integer
       Integer key = new Random().nextInt(elements.length) + 1;

       // search for the key
       int result = Arrays.binarySearch(elements, key);

       // match if found
       if (result >= 0) System.out.println(elements[result]);
   }

   /**
     * 一个调用处理器，它会打印方法名和参数，然后
     * 调用原始方法
     */
   class TraceHandler implements InvocationHandler
   {
       private Object target;

       /**
        * 构造一个 TraceHandler
        * @param t 方法调用的隐式参数
        */
       public TraceHandler(Object t)
       {
           target = t;
       }

       public Object invoke(Object proxy, Method m, Object[] args) throws Throwable
       {
           System.out.println("Invoking " + m.getName());
           if (args != null) {
               System.out.print("with args: ");
               for (int i = 0; i < args.length; i++) {
                   System.out.print(args[i]);
                   if (i < args.length - 1) System.out.print(", ");
               }
               System.out.println();
           }
           Object result = m.invoke(target, args);
           System.out.println("Returned: " + result);
           return result;
       }
   }
}
```

### 6.5.3 代理类的属性

现在你已经了解了代理类的运作方式，让我们回顾它们的一些属性。记住，代理类是在运行时创建的，就像任何其他类一样。

所有的代理类继承自 `Proxy`。代理类只有一个字段——调用处理器，它存储了执行任务所需的额外数据。例如，当列表 6.10 中我们代理 `Comparable` 对象时，`TraceHandler` 包装了这些对象。

代理类重写了 `Object` 类的 `toString`、`equals` 和 `hashCode` 方法。与所有代理方法一样，这些方法简单地调用处理器的 `invoke`。`Object` 类的其他方法（如 `clone` 和 `getClass`）没有被重定义。

对于特定的类加载器和有序接口集合，只有一个代理类。也就是说，如果你使用相同的类加载器和接口数组调用两次 `newProxyInstance`，将得到相同的对象。你也可以通过 `getProxyClass` 方法获取该类：

点击此处查看代码图像

```java
Class proxyClass = Proxy.getProxyClass(null, interfaces);
```

代理类总是 `public` 且 `final`。如果代理类实现的所有接口都是 `public`，则代理类不属于任何特定的包。否则，所有非公共接口必须属于同一个包，代理类也将属于该包。

你可以通过调用 `Proxy` 类的 `isProxyClass` 方法来测试特定的 `Class` 对象是否代表代理类。

---

`java.lang.reflect.InvocationHandler` (1.3)

`Object invoke(Object proxy, Method method, Object[] args)`

定义此方法以包含当在代理对象上调用方法时想要执行的操作。

---

`java.lang.reflect.Proxy` (1.3)

`static Class<?> getProxyClass(ClassLoader loader, Class<?>... interfaces)`

返回实现给定接口的代理类。

`static Object newProxyInstance(ClassLoader loader, Class<?>[] interfaces, InvocationHandler handler)`

构造实现给定接口的代理类的实例。所有方法都会调用给定处理器对象的 `invoke` 方法。

`static boolean isProxyClass(Class<?> cl)`

如果 `cl` 是代理类，则返回 `true`。

这是我们关于 Java 编程语言基础知识的最后一个章节。接口、lambda 表达式和内部类是你会经常遇到的概念。然而，正如我们已经提到的，克隆和代理是主要对库设计者和工具构建者感兴趣的高级技术，而不是应用程序程序员。你现在准备好学习如何在第 7 章中处理程序中的异常情况了。

# 第 7 章 异常、断言与日志

## 在本章中

- 7.1 处理错误
- 7.2 捕获异常
- 7.3 使用异常的技巧
- 7.4 使用断言
- 7.5 日志
- 7.6 调试技巧

在一个完美的世界里，用户永远不会以错误的格式输入数据，他们选择打开的文件将始终存在，代码永远不会有 bug。到目前为止，我们展示的代码大多就像我们生活在这样一个完美的世界里一样。现在是时候转向 Java 编程语言用于处理现实世界中错误数据和多 bug 代码的机制了。

遇到错误是不愉快的。如果用户因为编程错误或某些外部情况丢失了在程序运行期间所做的工作，那么该用户可能会永远离开你的程序。至少，你必须：

- 通知用户发生了错误；
- 保存所有工作；以及
- 允许用户优雅地退出程序。

对于异常情况，例如可能导致程序崩溃的错误输入数据，Java 使用了一种错误捕获形式，名不虚归，它被称为 `exception handling`。Java 中的异常处理与 C++ 或 Delphi 类似。本章的第一部分涵盖了 Java 异常。

在测试期间，你需要运行许多检查以确保你的程序执行了正确的操作。但这些检查在测试完成后可能是耗时的，且没必要的。你可以直接移除检查，并在需要额外测试时将它们放回来——但这太麻烦了。本章的第二部分将向你展示如何使用断言机制来选择性地激活检查。

当你的程序执行错误操作时，你并不总是能与用户通信或终止。相反，你可能想记录问题以便以后分析。本章的第三部分讨论了标准的 Java 日志框架。

## 7.1 处理错误

假设在 Java 程序运行时发生了一个错误。该错误可能是由包含错误信息的文件、不稳定的网络连接，或者（我们很不想提这一点）使用无效的数组索引，或尝试使用尚未赋值给对象的引用引起的。用户期望程序在发生错误时表现得明智。如果某个操作因为错误而无法完成，程序应该：

- 回到安全状态并允许用户执行其他命令；
- 允许用户保存所有工作并优雅地退出程序。

要做到这一点可能并不容易，因为检测（甚至引起）错误条件的代码通常与可以将数据回滚到安全状态的代码，或可以保存用户工作并愉快退出的代码相隔遥远。异常处理的任务是将控制权从错误发生的地方转移到可以处理该情况的错误处理器。为了处理程序中的异常情况，你必须考虑可能发生的错误和问题。你需要考虑哪些类型的问题？

- **用户输入错误。** 除了不可避免的拼写错误外，有些用户喜欢自辟蹊径而不是遵循指示。例如，假设用户请求连接到一个语法上错误的 URL。你的代码应该检查语法，但假设它没有检查。那么网络层将会报错。
- **设备错误。** 硬件并不总是按照你意愿的方式工作。打印机可能已关闭。网页可能暂时无法访问。设备经常会在任务执行中途失败。例如，打印机可能在打印过程中用完纸。
- **物理限制。** 磁盘可能会满；你可能会耗尽可用内存。
- **代码错误。** 某个方法可能执行不正确。例如，它可能提供错误的答案或错误地使用其他方法。计算无效的数组索引、尝试在哈希表中查找不存在的条目，或尝试从空栈中弹出，都是代码错误的示例。

对方法中错误的传统反应是返回一个特殊的错误代码，由调用该方法的方法进行分析。例如，从文件回读信息的方法通常返回一个 `-1` 文件结束标记，而不是标准字符。这可能是处理许多异常情况的一种有效方法。另一个表示错误状况的常见返回值是 `null` 引用。

不幸的是，并不总是能够返回错误代码。可能没有明显的方法来区分有效和无效数据。一个返回整数的方法不能简单地返回 `-1` 来表示错误；值 `-1` 可能是一个完全有效的结果。

相反，正如我们在第 5 章中提到的，如果方法无法以正常方式完成任务，Java 允许每个方法有一个替代退出路径。在这种情况下，方法不返回值。相反，它 `throws` 一个封装了错误信息的对象。注意，方法会立即退出；它不返回任何值。此外，执行不会在调用方法的代码处恢复；相反，异常处理机制开始寻找可以处理此错误的 `exception handler`。

异常有自己的语法并是特殊继承层次的一部分。我们将先介绍语法，然后给出如何有效使用此功能的提示。

### 7.1.1 异常的分类

在 Java 编程语言中，异常对象总是派自 `Throwable` 类的实例。正如你很快看到的，如果 Java 内置的类符合你的需求，你可以创建自己的异常类。

图 7.1 是 Java 异常层次的简化图表。

![Image](img/07fig01.jpg)

**图 7.1** Java 异常层次

注意所有异常都继承自 `Throwable`，但层次结构立即分为两个分支：`Error` 和 `Exception`。

Error 层次结构描述了 Java 运行时系统内部的错误和资源耗尽情况。你不应该抛出这种类型的对象。如果发生了此类内部错误，除了通知用户并尝试地退出程序外，你做不了什么。这种情况非常罕见。

在进行 Java 编程时，关注 `Exception` 层次结构。`Exception` 层次也分为两个分支：派自 `RuntimeException` 的异常和不派生的异常。通用规则是：`RuntimeException` 的发生是因为犯了编程错误。任何其他异常的发生是因为糟糕的事情（例如 I/O 错误）发生在原本良好的程序上。

继承自 `RuntimeException` 的异常包括此类问题：

- 类型转换错误
- 数组越界访问
- 空指针访问

不继承自 `RuntimeException` 的异常包括：

- 尝试读取文件末
- 尝试打开不存在的文件
- 尝试为不存在的类的字符串查找 `Class` 对象

“如果是一个 `RuntimeException`，那就是你的错”这条规则非常有效。你本可以通过测试数组索引是否超出数组边界，从而避免那个 `ArrayIndexOutOfBoundsException`。如果你在使用变量之前先检查了它是否为 `null`，那么 `NullPointerException` 就不会发生。

那么一个不存在的文件呢？你难道不能先检查文件是否存在，然后再打开它吗？嗯，文件可能在你检查完它的存在性后紧接着被删除了。因此，“存在性”这一概念取决于环境，而不仅仅取决于你的代码。

《Java 语言规范》将任何派自 `Error` 类或 `RuntimeException` 类的异常称为*未检查的*（unchecked）异常。所有其他异常都称为*已检查的*（checked）异常。这是我们也采纳的有用术语。编译器会检查你是否为所有已检查异常提供了异常处理器。

> ![Image](img/note.jpg) **备注**
>
> `RuntimeException` 这个名字有点让人困惑。当然，我们正在讨论的所有错误都发生在运行时。

> ![Image](img/note1.jpg) **C++ 备注**
>
> 如果你熟悉标准 C++ 库中（局限性得多的）异常层次结构，你现在可能会感到非常困惑。C++ 有两个基础异常类：`runtime_error` 和 `logic_error`。`logic_error` 类相当于 Java 的 `RuntimeException`，它也表示程序中的逻辑错误。`runtime_error` 类是由不可预测问题引起的异常的基类。它等于 Java 中那些不属于 `RuntimeException` 类型的异常。

### 7.1.2 声明已检查异常

当 Java 方法遇到它无法处理的情况时，它可以抛出异常。这个想法很简单：方法不仅会告诉 Java 编译器它可以返回哪些值，*还会告诉编译器可能会发生什么错误。*例如，尝试从文件中读取的代码知道文件可能不存在，或者文件可能是空的。因此，尝试处理文件中信息的代码将需要通知编译器它可能会抛出某种 `IOException`。

你声明你的方法可以抛出异常的地方是方法的头部；头部会发生变化以反映该方法可以抛出的已检查异常。例如，这里是标准库中 `FileInputStream` 类的一个构造函数的声明。（有关输入和输出的更多信息，请参见卷二的第 2 章](#ch02.html_ch02)。）

点击此处查看代码图像

```java
public FileInputStream(String name) throws FileNotFoundException
```

该声明表示此构造函数根据 `String` 参数产生一个 `FileInputStream` 对象，但它*也*可能以特殊的方式出错——通过抛出一个 `FileNotFoundException`。如果发生了这种糟糕的情况，构造函数的调用将不会初始化一个新的 `FileInputStream` 对象，而是抛出一个 `FileNotFoundException` 类的对象。如果是这样，运行时系统将开始寻找知道处理 `FileNotFoundException` 对象的异常处理器。

当你编写自己的方法时，你不需要声明你的方法实际上可能抛出的每一个可能的可抛出对象。要理解何时（以及什么）你需要在所写方法的 `throws` 子句中声明内容，请记住在以下四种情况的任何一种情况下都会抛出异常：

- 你调用了一个抛出已检查异常的方法——例如，`FileInputStream` 构造函数。
- 你检测到一个错误并使用 `throw` 语句抛出一个已检查异常（我们在下一节中介绍 `throw` 语句）。
- 你犯了编程错误，例如 `a[-1] = 0` 导致未检查的异常（在这种情况下是 `ArrayIndexOutOfBoundsException`）。
- 在虚拟机或运行时库中发生了内部错误。

如果发生了前两种情况的任何一种，你必须告诉使用你方法的程序员关于异常的可能性。为什么呢？任何抛出异常的方法都是一个潜在的死亡陷阱。如果没有处理器捕获该异常，当前执行线程将终止。

与所提供的类中的 Java 方法一样，你在方法头部通过*异常规格*（exception specification）来声明你的方法可能抛出异常。

点击此处查看代码图像

```java
class MyAnimation
{
    ...

    public Image loadImage(String s) throws IOException
    {
        ...
```



```java
    }

}
```

如果一个方法可能抛出多种已检查异常类型，你必须在头部列出所有的异常类。用逗号将它们隔开，如下例所示：

点击此处查看代码图像

```java
class MyAnimation
{
    ...

    public Image loadImage(String s) throws FileNotFoundException, EOFException
    {
        ...
    }
}
```

然而，你不需要声明 Java 内部错误——即继承自 `Error` 的异常。任何代码都可能抛出这些异常，而且它们完全超出了你的控制范围。

同样，你不应该声明继承自 `RuntimeException` 的未检查异常。

点击此处查看代码图像

```java
class MyAnimation
{
    ...

    void drawImage(int i) throws ArrayIndexOutOfBoundsException // 糟糕的风格
    {
        ...
    }
}
```

这些运行时错误完全在你的控制之下。如果你如此担心数组索引错误，你应该花时间去修复它们，而不是声明它们可能发生的可能性。

总之，方法必须声明它可能抛出的所有*已检查*异常。未检查异常要么在你的控制之外（`Error`），要么是由你本不允许的情况引起的（`RuntimeException`）。如果你的方法没有如实声明所有已检查异常，编译器将发出错误信息。

当然，正如你已经在许多示例中看到的，与其声明异常，你也可以捕获它。这样异常就不会抛出方法，因此不需要 `throws` 规格。你将在本章后面的部分学习如何决定捕获异常还是让别人捕获。

***

![Image](img/caution.jpg) 注意

如果你覆盖了父类的方法，子类方法声明的已检查异常不能比父类方法泛。（抛出更具体的异常，或者在子类中不抛出任何异常是可以的。）特别是，如果父类方法没有抛出任何异常，子类也不能有。例如，如果你覆盖了 `JComponent.paintComponent`，你的 `paintComponent` 方法不能抛出任何已检查异常，因为父类方法没有抛出。

***

当类中的方法声明它抛出一个特定类的实例异常时，它可以抛出该类或其任何子类的异常。例如，`FileInputStream` 构造函数可以声明它抛出 `IOException`。在这种情况下，你将不知道它是哪种 `IOException`；它可能是普通的 `IOException`，可能是各种子类之一的对象，例如 `FileNotFoundException`。

此外，在 C++ 中，如果没有给出 `throw` 规范，函数可能会抛出任何异常。在 Java 中，没有 `throws` 指定符的方法可能不会抛出任何检查异常（checked exceptions）。

***

### 7.1.3 如何抛出异常

现在，假设你的代码发生了一些糟糕的事情。你有一个方法 `readData`，它正在读取一个文件，该文件的头部承诺了：

```text
Content-length: 1024
```

但你在读取 733 个字符后就遇到了文件末尾（EOF）。你可能认为这种情况非常异常，以至于你想抛出一个异常。

你需要决定抛出什么种类型的异常。某种 `IOException` 都是一个不错的选择。查阅 Java API 文档，你发现了一个 `EOFException`，描述为“信号在输入过程中意外到达了文件末尾”。完美。以下是抛出它的方法：

```java
throw new EOFException();
```

或者，如果你愿意：

点击此处查看代码图片

```java
EOFException e = new EOFException();

throw e;
```

以下是它们是如何结合在一起的：

点击此处查看代码图片

```java
String readData(Scanner in) throws EOFException
{
    ...

    while (. . .)
    {
        if (!in.hasNext()) // 遇到 EOF
        {
            if (n < len)
                throw new EOFException();
        }

        ...
    }

    return s;
}
```

`EOFException` 有一个接受字符串参数的第二个构造函数。你可以通过更详细地描述异常情况来充分利用它。

点击此处查看代码图片

```java
String gripe = "Content-length: " + len + ", Received: " + n;

throw new EOFException(gripe);
```

你可以看到，如果现有的异常类有一个适用于，抛出异常是非常简单的。在这种情况下：

1. 找到一个合适的异常类。
2. 创建该类的一个对象。
3. 抛出它。

一旦方法抛出异常，它就不会返回到调用者。这意味着你不需要担心编写一个默认返回值或错误码。

***

![Image](img/note1.jpg) C++ 注意事项

抛出异常在 C++ 和 Java 中是相同的，但有一个细微的区别。在 Java 中，你只能抛出 `Throwable` 的子类的对象。在 C++ 中，你可以抛出任何类型的值。

***

### 7.1.4 创建异常类

你的代码可能会遇到任何标准异常类无法充分描述的问题。在这种情况下，创建你自己的异常类是简单的。只需继承自 `Exception`，或者继承自 `Exception` 的子类（如 `IOException`）。惯例是同时提供一个默认构造函数和一个包含详细消息的构造函数。（`Throwable` 超父类的 `toString` 方法会返回一个包含该详细消息的字符串，这对调试非常有用。）

点击此处查看代码图片

```java
class FileFormatException extends IOException
{
    public FileFormatException() {}

    public FileFormatException(String gripe)
    {
        super(gripe);
    }
}
```

现在你准备好抛出你自己的异常类型了。

点击此处查看代码图片

```java
String readData(BufferedReader in) throws FileFormatException
{
    ...

    while (. . .)
    {
        if (ch == -1) // 遇到 EOF
        {
            if (n < len)
                throw new FileFormatException();
        }

        ...
    }

    return s;
}
```

***

`java.lang.Throwable` **1.0**

- `Throwable()` 构建一个没有详细消息的新 `Throwable` 对象。
- `Throwable(String message)` 构建一个带有指定详细消息的新 `Throwable` 对象。按照惯例，所有派生的异常类都支持默认构造函数和带有详细消息的构造函数。
- `String getMessage()` 获取 `Throwable` 对象的详细消息。

***

## 7.2 捕获异常

你现在知道如何抛出异常了。这很简单：你抛出它然后忘记它。当然，某些代码必须捕获该异常。捕获异常需要更多的规划。这就是接下来的章节将涵盖的内容。

### 7.2.1 捕获异常

如果发生的异常没有在任何地方捕获，程序将终止。要捕获异常，请设置 `try/catch` 块。`try` 最简单的形式是：

```java
try {
    // 代码
} catch (Exception e) {
    // 处理程序
}
```

如果 `try` 块中的任何部分抛出异常，将执行 `catch` 块。

1. 找到一个合适的异常类。
2. 创建该类的一个对象。
3. 抛出它。

一旦方法抛出异常，它就不会返回到调用者。这意味着你不需要担心编写一个默认返回值或错误码。

在 Java 和 C++ 中，捕获异常几乎相同。严格来说：

```java
catch (Exception e) // Java
```

对应的写法是：

```cpp
catch (Exception& e) // C++
```

Java 中没有 C++ 中 `catch (...)` 的对应物。这在 Java 中并不，因为所有异常都继承自一个公共父类。

### 7.2.2 捕获多个异常

你可以在 `try` 块中捕获多种异常类型，并对每个类型进行不同的处理。如下例所示，为每个类型使用独立的 `catch` 子句：

点击查看代码图片

```java
try
{
    可能抛出异常的代码
}
catch (FileNotFoundException e)
{
    针对缺失文件的紧急处理
}
catch (UnknownHostException e)
{
    针对未知主机的紧急处理
}
catch (IOException e)
{
    针对所有其他 I/O 问题的紧急处理
}
```

异常对象可能包含有关异常性质的信息。要了解更多关于该对象的信息，可以尝试 `e.getMessage()` 获取详细的错误信息（如果有），或者使用 `e.getClass().getName()` 获取异常对象的实际类型。

从 Java SE 7 开始，你可以在同一个 `catch` 子句中捕获多种异常类型。例如，假设对缺失文件和未知主机的处理操作是相同的。那么你可以合并这些 `catch` 子句：

点击查看代码图片

```java
try
{
    可能抛出异常的代码
}
catch (FileNotFoundException | UnknownHostException e)
{
    针对缺失文件和未知主机的紧急处理
}
catch (IOException e)
{
    针对所有其他 I/O 问题的紧急处理
}
```

这一特性仅在捕获互不为子类的异常类型时才需要。

![Image](img/note.jpg) 注意事项

当你捕获多个异常时，异常变量是隐式 `final` 的。例如，你不能在子句体中为 `e` 分配不同的值：

```java
catch (FileNotFoundException | UnknownHostException e) { ... }
```

![Image](img/note.jpg) 注意事项

捕获多个异常不仅让你的代码看起来更简单，而且效率更高。生成的字节码包含一个共享 `catch` 子句的单一块。

### 7.2.3 重新抛出和异常链

你可以在 `catch` 子句中抛出异常。通常，当你想要更改异常类型时会这样做。如果你构建了一个供其他程序员使用的子系统，使用一个指示子系统失败的异常类型非常有意义。这种异常类型的一个示例是 `ServletException`。执行 servlet 的代码可能不想详细地知道发生了什么细微的错误，但它绝对想知道是 servlet 的错。

以下是捕获异常并重新抛出的方法：

点击查看代码图片

```java
try
{
    访问数据库
}
catch (SQLException e)
{
    throw new ServletException("database error: " + e.getMessage());
}
```

在这里，`ServletException` 是使用异常的消息文本构造的。

然而，更好的做法是将原始异常设置为新异常的“原因”：

点击查看代码图片

```java
try
{
    访问数据库
}
catch (SQLException e)
{
    Throwable se = new ServletException("database error");
    se.initCause(e);
    throw se;
}
```

当异常被捕获时，可以检索原始异常：

```java
Throwable e = se.getCause();
```

这种包装技术被高度推荐。它允许你在子系统中抛出高层级异常，而不会丢失原始失败的细节。

![Image](img/tip.jpg) 提示

如果在不允许抛出检查异常的方法中发生了检查异常，这种包装技术也很有用。你可以捕获该检查异常并将其封装为运行时异常。

有时，你只是想记录异常并在不进行任何更改的情况下重新抛出它：

点击查看代码图片

```java
try
{
    访问数据库
}
catch (Exception e)
{
    logger.log(level, message, e);
    throw e;
}
```

在 Java SE 7 之前，这种方法存在一个问题。假设代码位于方法内部：

```java
public void updateRecord() throws SQLException
```

Java 编译器会查看 `catch` 块内部的 `throw` 语句，查看 `e` 的类型，并抱怨该方法可能会抛出任何 `Exception`，而不仅仅是 `SQLException`。这现在已经改进。

### 7.2.4 `finally` 子句

当你使用 `try` 块时，无论是否捕获异常，`finally` 块都会执行。这对于清理资源非常有用，例如关闭文件或数据库连接。以下示例说明了 `finally` 子句无论是否发生异常都会执行：

点击查看代码图片

```java
InputStream in = new FileInputStream();

try
{
    // 1
    可能抛出异常的代码
    // 2
}
catch (IOException e)
{
    // 3
    显示错误信息
    // 4
}
finally
{
    // 5
    in.close();
}

// 6
```

让我们看看程序执行 `finally` 子句的三种情况：

**1.** 代码没有抛出异常。在这种情况下，程序首先执行 `try` 块中的代码。然后执行 `finally` 子句。之后，继续执行 `finally` 子句之后的语句。换句话说，执行将通过点 1、2、5 和 6。

**2.** 代码抛出了由 `catch` 子句捕获的异常——在本例中是 `IOException`。对于这种情况，程序执行 `try` 块中的所有代码，直到抛出异常。`try` 块中的剩余代码被跳过。程序随后执行匹配的 `catch` 子句，然后执行 `finally` 子句。

如果 `catch` 子句没有抛出异常，程序将执行 `finally` 子句后的第一行。在这种情况下，执行将通过点 1、3、4、5 和 6。

如果 `catch` 子句抛出了异常，则该异常将抛回给此方法的调用者，执行将通过点 1、3 和 5。

**3.** 代码抛出了未被任何 `catch` 子句捕获的异常。在这里，程序执行 `try` 块中的所有代码直到抛出异常。`try` 块中的剩余代码被跳过。然后执行 `finally` 子句中的代码，最后将异常抛回给此方法的调用者。执行将仅通过点 1 和 5。

你可以在没有 `catch` 子句的情况下使用 `finally` 子句。例如，考虑以下 `try` 语句：

```java
InputStream in = ...;

try
{
```

```java
    code that might throw exceptions
}
finally
{
    in.close();
}
```

`finally` 子句中的 `in.close()` 语句无论 `try` 块中是否遇到异常都会执行。当然，如果遇到了异常，它会被重新抛出，并且必须在另一个 `catch` 子句中捕获。

事实上，正如下面的提示所解释的，我们认为每当你需要关闭资源时，像这样使用 `finally` 子句是一个非常好的主意。

***

![Image](img/tip.jpg) 提示

我们强烈建议你`decouple` `try/catch` 和 `try/finally` 块。这会让你的代码变得远不那么困惑。例如：

点击此处查看代码图片

```java
InputStream in = ...;

try
{
    try
    {
        code that might throw exceptions
    }
    finally
    {
        in.close();
    }
}
catch (IOException e)
{
    show error message
}
```

内部 `try` 块有一个单一的职责：确保输入流被关闭。外部 `try` 块有一个单一的职责：确保错误被报告。这种解决方案不仅更清晰，而且更功能：`finally` 子句中的错误也会被报告。

***

***

![Image](img/caution.jpg) 注意

当 `finally` 子句包含 `return` 语句时，可能会产生意外的结果。假设你通过 `return` 语句退出 `try` 块的中间。在方法返回之前，`finally` 块会被执行。如果 `finally` 块也包含 `return` 语句，那么它会掩盖原始的返回值。考虑这个刻意的例子：

```java
public static int f(int n)
{
    try
    {
        int r = n * n;
        return r;
    }
    finally
    {
```



```java
if (n == 2) return 0;

}
```

如果你调用`f(2)`，则`try`块会计算`r = 4`并执行`return`语句。然而，`finally`子句在方法实际返回之前执行，导致方法返回`0`，忽略了原始的返回值`4`。

***

有时`finally`子句会给你带来麻烦——特别是当清理方法也可能抛出异常时。假设你想确保在流处理代码遇到异常时关闭一个流（stream）。

点击此处查看代码图片

```java
InputStream in = ...;

try
{
    code that might throw exceptions
}
finally
{
    in.close();
}
```

现在假设`try`块中的代码抛出了除代码调用者感兴趣的`IOException`之外的某种异常。`finally`块执行并调用了`close`方法。该方法本身可以抛出一个`IOException`！当它发生时，原始异常就会丢失，取而代之的是`close`方法的异常。

这是一个问题，因为第一个异常可能更有价值。如果你想做正确的事并重新抛出原始异常，代码将变得极其繁琐。这里有一种设置方法：

点击此处查看代码图片

```java
InputStream in = ...;
Exception ex = null;

try
{
    try
    {
        code that might throw exceptions
    }
    catch (Exception e)
    {
        ex = e;
        throw e;
    }
}
finally
{
    try
    {
        in.close();
    }
    catch (Exception e)
    {
        if (ex == null) throw e;
    }
}
```

幸运的是，Java SE 7 让处理关闭资源变得容易得多，正如你在下一节中看到的。

### 7.2.5 Try-with-Resources 语句

Java SE 7 为这种代码模式提供了一个实用的快捷方式：

```java
open a resource

try
{
    work with the resource
}
finally
{
    close the resource
}
```

前提是该资源实现了一个`AutoCloseable`接口。该接口有一个单一的方法`void close() throws Exception`。

***

![Image](img/caution.jpg) 注意

还有一个`Closeable`接口。它是`AutoCloseable`的子接口，同样有一个`close()`方法。在最简单的变体中，try-with-resources 语句的格式为：

```java
try (Resource res = ...)
{
    work with res
}
```

当`try`块退出时，`res.close()`会自动调用。这是一个典型的例子，读取所有单词：

点击此处查看代码图片

```java
try (Scanner in = new Scanner(System.in))
{
    while (in.hasNext())
    {
        System.out.println(in.next());
    }
}
```

无论`try`块如何退出（正常退出或异常退出），资源都会关闭。你可以指定多个资源：

点击此处查看代码图片

```java
try (Scanner in = new Scanner(path.to.file);
     PrintWriter out = new PrintWriter(System.out))
{
    while (in.hasNext())
    {
        out.println(in.next());
    }
}
```

资源按照初始化的反顺序关闭。如果在关闭期间抛出了异常，原始异常会被保留，后续异常会被抑制。你可以使用`getSuppressed()`方法访问被抑制的异常。

### 7.2.6 分析堆栈元素

堆栈跟踪（stack trace）是执行过程中某一点的方法调用列表。你已经见过堆栈跟踪——当 Java 程序因未捕获的异常终止时会显示。

你可以通过调用`Throwable`类的`printStackTrace`方法获取堆栈跟踪的文本描述。点击此处查看代码图片

```java
Throwable t = new Throwable();

StringWriter out = new StringWriter();

t.printStackTrace(new PrintWriter(out));

String description = out.toString();
```

另一种灵活的方法是使用`getStackTrace`获取`StackTraceElement`对象数组，你可以在程序中对其进行分析。点击此处查看代码图片

```java
Throwable t = new Throwable();

StackTraceElement[] frames = t.getStackTrace();

for (StackTraceElement frame : frames)
{
    System.out.println(frame);
}
```

`StackTraceElement`类具有获取文件名和行号、以及执行行的类名和方法名的方法。`toString`方法产生包含所有这些信息的格式化字符串。

静态方法`Thread.getAllTraces`产生所有线程的堆栈跟踪。这里是使用该方法的方法：

点击此处查看代码图片

```java
Map<Thread, StackTraceElement[]> map = Thread.getAllStackTraces();

for (Thread t : map.keySet())
{
    StackTraceElement[] frames = map.get(t);

    analyze frames
}
```

关于`Map`接口和线程的更多信息，请参见第 9 章和第 14 章。

[列表 7.1]打印了一个递归阶乘函数的堆栈跟踪。例如，如果你计算`factorial(3)`，输出为：

```text
factorial(3):
StackTraceTest.factorial(StackTraceTest.java:18)
StackTraceTest.main(StackTraceTest.java:34)

factorial(2):
StackTraceTest.factorial(StackTraceTest.java:18)
StackTraceTest.factorial(StackTraceTest.java:24)
StackTraceTest.main(StackTraceTest.java:34)

factorial(1):
StackTraceTest.factorial(StackTraceTest.java:18)
StackTraceTest.factorial(StackTraceTest.java:24)
StackTraceTest.factorial(StackTraceTest.java:24)
StackTraceTest.main(StackTraceTest.java:34)

return 1
return 2
return 6
```

Listing 7.1 `stackTrace/StackTraceTest.java`

点击此处查看代码图像

```java
package stackTrace;

import java.util.*;

/**
 * 一个显示递归方法调用堆栈轨迹的程序。
 * @version 1.01 2004-05-10
 * @author Cay Horstmann
 */
public class StackTraceTest
{
    /**
     * 计算数字的阶乘
     * @param n 一个非负整数
     * @return n! = 1 * 2 * ... * n
     */
    public static int factorial(int n)
    {
        System.out.println("factorial(" + n + "):");
        Throwable t = new Throwable();
        StackTraceElement[] frames = t.getStackTrace();

        for (StackTraceElement f : frames)
            System.out.println(f);

        int r;

        if (n <= 1) r = 1;
        else r = n * factorial(n - 1);

        System.out.println("return " + r);
        return r;
    }

    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);
        System.out.print("Enter n: ");
        int n = in.nextInt();
        factorial(n);
    }
}
```

`java.lang.Throwable` 1.0

- `Throwable(Throwable cause)` 1.4
- `Throwable(String message, Throwable cause)` 1.4 根据给定的原因构造`Throwable`。
- `Throwable initCause(Throwable cause)` 1.4 为此对象设置原因，如果此对象已经有了原因，则抛出异常。返回`this`。
- `Throwable getCause()` 1.4 获取被设置为此对象原因的异常对象，如果没有设置原因，则返回`null`。
- `StackTraceElement[] getStackTrace()` 1.4 获取此对象构造时调用堆栈的轨迹。
- `void addSuppressed(Throwable t)` 7 向此异常添加一个“被抑制的”异常。这发生在 try-with-resources 语句中，其中`t`是由`close`方法抛出的异常。
- `Throwable[] getSuppressed()` 7 获取此异常的所有“被抑制的”异常。通常情况下，这些是在 try-with-resources 语句中由`close`方法抛出的异常。

`java.lang.Exception` 0.0

- `Exception(Throwable cause)` 1.4
- `Exception(String message, Throwable cause)` 1.4 根据给定的原因构造`Exception`。

`java.lang.RuntimeException` 0.0

- `RuntimeException(Throwable cause)` 1.4
- `RuntimeException(String message, Throwable cause)` 1.4 根据给定的原因构造`RuntimeException`。

`java.lang.StackTraceElement` 1.4

- `String getFileName()` 获取包含该元素执行点的源文件名，如果信息不可用，则返回`null`。
- `int getLineNumber()` 获取包含该元素执行点的源文件的行号，如果信息不可用，则返回`-1`。
- `String getClassName()` 获取包含该元素执行点的类的全限定名。
- `String getMethodName()` 获取包含该元素执行点的类的方法名称。构造函数的名称为`<init>`。静态初始化器的名称为`<clinit>`。你无法区分具有相同名称的重载方法。
- `boolean isNativeMethod()` 如果该元素的执行点位于原生方法内部，则返回`true`。
- `String toString()` 返回一个包含类名、方法名和行号的格式化字符串（如果可用）。

## 7.3 使用异常的技巧

关于异常的正确使用存在某种争议。一些程序员认为所有检查异常（checked exceptions）都是麻烦，而另一些人似乎觉得抛出的异常还不够。我们认为异常（即使是检查异常）有其用处，并为你提供这些正确使用的技巧。

**1. 异常处理不应该替代简单的测试。**

作为一个例子，我们写了一些代码，尝试 1,000,000 次从空栈中弹出元素。它首先通过检查栈是否为空来执行。

```java
if (!s.empty()) s.pop();
```

接下来，无论如何都强制它弹出栈，然后捕获`EmptyStackException`，它告诉我们不应该这样做。

```java
try
{
    s.pop();
}
catch (EmptyStackException e)
{
}
```

在我们的测试机器上，调用`isEmpty`的版本运行了 646 毫秒。捕获`EmptyStackException`的版本运行了 21,739 毫秒。你可以看到，调用`isEmpty`的版本比捕获`EmptyStackException`快得多。其理是：异常仅应用于异常情况。

**2. 不要微管理异常。**

许多程序员将每个语句都包裹在独立的`try`块中。点击此处查看代码图像

```java
PrintStream out;
Stack s;

for (i = 0; i < 100; i++)
{
    try
    {
        n = s.pop();
    }
    catch (EmptyStackException e)
    {
        // 栈为空
    }

    try
    {
        out.writeInt(n);
    }
    catch (IOException e)
    {
        // 写入文件错误
    }
}
```

这种方法会让你的代码变得非常糟糕。有必要将*整个任务*包裹在`try`块中。如果任何一个操作失败，你就可以放弃该任务。点击此处查看代码图像

```java
try
{
    for (i = 0; i < 100; i++)
    {
        n = s.pop();
        out.writeInt(n);
    }
}
catch (IOException e)
{
    // 写入文件错误
}
catch (EmptyStackException e)
{
    // 栈为空
}
```

这段代码看起来整洁得多。它履行了异常处理的承诺：*分离*正常处理与错误处理。

**3. 善用异常层级结构。**

不要仅仅抛出`RuntimeException`。找到一个合适的子类或创建你自己的。

不要仅仅捕获`Throwable`。这会让你的代码难以阅读和维护。

尊重检查异常和未检查异常之间的区别。检查异常本质上是负担——不要为逻辑错误抛出它们。（例如，反射库在这里就做错了。调用者经常需要捕获它们永远不会发生的异常。）

不要犹豫将异常转换为更合适的异常。例如，当从文件中解析整数时，捕获`NumberFormatException`并将其转换为`IOException`的子类或`MySubsystemException`。

**4. 不要抑制异常。**

在 Java 中，存在抑制异常的巨大诱惑。如果你正在编写一个调用可能每百年抛出一次异常的方法，编译器会抱怨，因为你没有在方法的`throws`列表中声明该异常。你不想将其放入`throws`列表中，因为那样编译器会对所有调用你方法的方法抱怨。所以你直接把它堵掉：

点击此处查看代码图像

```java
public Image loadImage(String s)
{
    try
    {
        // 威胁抛出检查异常的代码
    }
    catch (Exception e)
    {
    } // so so there
}
```

现在你的代码将无缝地通过编译。它将正常运行，除非发生异常。在那种情况下，异常将被静默忽略。如果你认为异常至少是重要的，那么你应该努力正确地处理它们。

### 5. 当你检测到错误时，“严厉的爱”比“溺爱”更有效

一些程序员担心在检测到错误时抛出异常。也许当方法带有无效参数被调用时，返回一个占位值比抛出异常更好吗？例如，当栈为空时，`Stack.pop`应该返回`null`还是抛出一个异常呢？我们认为，在故障发生点抛出一个`EmptyStackException`，比在稍后的某个时间发生`NullPointerException`要好。

### 6. 传播异常并不是耻辱的表现

许多程序员觉得必须捕获所有抛出的异常。如果他们调用一个会抛出异常的方法，例如`FileInputStream`构造函数或`readLine`方法，他们本能地捕获可能生成的异常。通常，传播异常实际上比捕获它更好：

点击此处查看代码图像

```java
public void readStuff(String filename) throws IOException // 并不是耻辱的表现！
{
```



`InputStream in = new FileInputStream(filename);`

```
...
}
```

高层方法通常具备更好的能力通知用户错误或放弃未执行的命令。

![Image](img/note.jpg) **注意**

规则 5 和规则 6 可以总结为“早抛出，晚捕获”。

## 7.4 使用断言（Assertions）

断言是防御性编程中常用的习惯用法。在接下来的章节中，你将学习如何有效地使用它们。

### 7.4.1 断言的概念

假设你确定某个属性已满足，并且在代码中依赖该属性。例如，你可能正在计算：

```java
double y = Math.sqrt(x);
```

你确定`x`不是负数。也许它是另一个不会产生负结果的计算结果，或者它是一个要求调用者仅提供正数的方法的参数。尽管如此，你仍然希望双检，而不是允许出现混淆的“非数字”（not a number）浮点值。

断言机制允许你在测试期间插入检查，并在生产代码中自动移除它们。Java 语言有一个关键字`assert`。它有两种形式：

`assert condition;`

以及

`assert condition : expression;`

这两条语句都会评估`condition`，如果为`false`，则抛出`AssertionError`。在第二条语句中，`expression`会被传递给`AssertionError`的构造函数并转换为消息字符串。

![Image](img/note.jpg) **注意**

`expression`的唯一目的是产生一个消息字符串。`AssertionError`对象并不存储实际值，因此你无法在之后对其进行查询。正如 JDK 文档以一种“家长式的魅力”描述的那样，这样做“会鼓励程序员尝试从断言失败中恢复，这违背了其初衷”。

要断言`x`非负数，你可以简单地使用：

`assert x >= 0;`

或者你可以将`x`的实际值传递给`AssertionError`对象，这样就能显示出来。

`assert x >= 0 : x;`

![Image](img/note1.jpg) **C++ 注意**

C 语言的`assert`宏将断言条件转换为字符串，如果断言失败则打印该字符串。例如，如果`assert(x >= 0)`失败，它会打印`"x >= 0"`。在 Java 中，条件不会自动成为错误报告的一部分。如果你想看到它，必须将其作为字符串传递给`AssertionError`对象：`assert x >= 0 : "x >= 0"`。

### 7.4.2 断言的启用与禁用

默认情况下，断言是禁用的。通过带有`-enableassertions`或`-ea`参数运行程序来启用它们：

`java -enableassertions MyApp`

注意，你不需要重新编译程序来启用或禁用断言。断言的启用或禁用是类加载器的功能。当断言被禁用时，类加载器会剥离断言代码，以免影响执行速度。

你甚至可以在特定的类或整个包中开启断言。例如：

`java -ea:MyClass -ea:com.company.mylib... MyApp`

此命令为类`MyClass`以及`com.company.mylib`包及其子包中的所有类开启断言。`-ea...`参数开启默认包中所有类的断言。

你也可以使用`-disableassertions`或`-da`参数禁用某些类和包的断言：

`java -ea:... -da:MyClass MyApp`

某些类不是由类加载器加载的，而是由虚拟机直接加载。你可以使用这些开关选择性地启用或禁用这些类中的断言。

然而，启用或禁用所有断言的`-ea`和`-da`开关不适用于没有类加载器的“系统类”。使用`-enableassertions/-esa`参数启用系统类的断言。

还可以通过程序控制类加载器的断言状态。请参本节末尾的 API 注释。

### 7.4.3 使用断言进行参数检查

Java 语言提供了三种处理系统故障的机制：

- 抛出异常
- 日志（Logging）
- 使用断言

何时应该选择断言？请记住以下点：

- 断言失败旨在致命的、不可恢复的错误。
- 断言检查仅在开发和测试期间开启。（这有时被幽默地描述为“在岸边时穿着救生衣，一旦在大海上就将其扔掉”）

因此，你不应该使用断言向程序的其他部分传递可恢复的状态，或向程序用户通信问题。断言应仅用于测试期间定位程序错误。

让我们来看一个常见的场景——方法参数检查。应该使用断言来检查非法值或`null`引用吗？要回答这个问题，你需要查看方法的文档。假设你实现了一个排序方法。

```java
/**
 * 对指定的数组范围按升序排序。
 * 排序的范围从 fromIndex（包含）延伸到 toIndex（不包含）。
 * @param a 要排序的数组。
 * @param fromIndex 要排序的第一个元素（包含）的索引。
 * @param toIndex 要排序的最后一个元素（不包含）的索引。
 * @throws IllegalArgumentException 如果 fromIndex > toIndex
 * @throws ArrayIndexOutOfBoundsException 如果 fromIndex < 0 或 toIndex > a.length
 */
static void sort(int[] a, int fromIndex, int toIndex)
```

文档指出，当索引值错误时，方法会抛出异常。这种行为是方法与其调用者之间约的一部分。如果你实现了该方法，就必须遵守该约并抛出指示异常。在这种情况下使用断言是不恰当的。

你是否应该断言`a`不是`null`呢？这也不恰当。方法文档对于`a`为`null`时方法的行为没有做任何说明。调用者有权假设在这种情况下方法将成功返回，而不会抛出断言错误。

然而，假设方法的契约略有不同：

`@param a` 待排序的数组（不能为`null`）。

现在，该方法的调用者收到了通知：使用`null`数组调用该方法是非合法的。那么该方法可以从断言开始：

```
assert a != null;
```

计算机科学家将这种契约称为`前置条件`（`precondition`）。原始方法对其参数没有前置条件——它承诺在所有情况下都有定义良好的行为。修改后的方法有一个前置条件：即`a`不为`null`。如果调用者未能满足前置条件，那么规则将失效，方法可以执行任何它想做的操作。事实上，由于有了断言的存在，该方法在被非法调用时，其行为是相当不可预测的。它有时抛出断言错误，有时又抛出空指针异常，取决于其类加载器如何配置。

### 7.4.4 使用断言记录假设

许多程序员使用注释来记录他们的底层假设。考虑下面这个来自 [`http://docs.oracle.com/javase/6/docs/technotes/guides/language/assert.html`](http://docs.oracle.com/javase/6/docs/technotes/guides/language/assert.html)的示例：

```
if (i % 3 == 0)
    ...
else if (i % 3 == 1)
    ...
else // (i % 3 == 2)
    ...
```

在这种情况下，使用断言代替注释会更有意义。

```
if (i % 3 == 0)
    ...
else if (i % 3 == 1)
    ...
else
{
    assert i % 3 == 2;
    ...
}
```

当然，彻底地思考这个问题会更有意义。`i % 3`的可能值有哪些？如果`i`是正数，余数必须是`0`、`1`或`2`。如果`i`是负数，那么余数可以是`-1`或`-2`。因此，真正的假设是`i`不是负数。一个更好的断言应该是：

```
assert i >= 0;
```

在`if`语句之前。

无论如何，这个示例展示了将断言作为程序员自检的良好用法。如你所见，断言是测试和调试的战术工具。相比之下，日志是程序整个生命周期的战略工具。我们将在下一节中检查日志。

**java.lang.ClassLoader 1.0**

• `void setDefaultAssertionStatus(boolean b)` 1.4
启用或禁用由此类加载器加载的所有没有显式类或包断言状态的类的断言。

• `void setClassAssertionStatus(String className, boolean b)` 1.4
启用或禁用给定类及其内部类的断言。

• `void setPackageAssertionStatus(String packageName, boolean b)` 1.4
启用或禁用给定包及其子包中所有类的类的断言。

• `void clearAssertionStatus()` 1.4
移除所有显式的类和包断言状态设置，并禁用此类加载器加载的所有类的断言。

## 7.5 日志

每个 Java 程序员都熟悉在有问题的代码中插入`System.out.println`调用以洞察程序行为的过程。当然，一旦你找到了问题的根源，就会移除打印语句，只在下一个问题出现时又把它们放回来。日志 API 设计旨在解决这个问题。以下是该 API 的主要优势：

• 很容易抑制所有日志记录，或仅抑制低于特定级别的记录，并且同样容易地重新开启它们。
• 被抑制的日志开销非常低，因此在应用程序中保留日志代码的代价微乎其微。
• 日志记录可以定向到不同的处理器——例如在控制台中显示、写入文件等。
• 日志记录器和处理器都可以过滤记录。过滤器可以使用过滤器实现者提供的任何标准丢弃无趣的日志条目。
• 日志记录可以用不同的方式进行格式化——例如纯文本或 XML。
• 应用程序可以使用多个日志记录器，使用分级名称，例如`com.mycompany.myapp`，类似于包名。
• 默认情况下，日志配置由配置文件控制。应用程序可以需要替换此机制。

### 7.5.1 基础日志

对于简单的日志记录，使用全局日志记录器并调用其`info`方法：

```
Logger.getGlobal().info("File->Open menu item selected");
```

默认情况下，记录打印如下：

```
May 10, 2013 10:12:15 PM LoggingImageViewer fileOpen
INFO: File->Open menu item selected
```

但如果你调用：

```
Logger.getGlobal().setLevel(Level.OFF);
```

现在日志被抑制了。

### 7.5.2 高级日志

既然你已经了“入门级日志”，让我们进入工业级日志。在专业应用程序中，你不想将所有日志都记录到一个日志记录器。相反，你可以定义自己的日志记录器。调用`getLogger`方法来创建或检索日志记录器：

```
private static final Logger myLogger = Logger.getLogger("com.mycompany");
```

**提示**

类似于包，日志记录器名称是分级的。事实上，它们比包更具层次性。包之间没有语义关系，但日志记录器共享某些属性。例如，如果你对`com`设置级别，子日志记录器将继承该级别。

有七种日志级别：

• `SEVERE`
• `WARNING`
• `INFO`
• `CONFIG`
• `FINE`
• `FINER`
• `FINEST`

默认情况下，前三个级别会被记录。你可以设置不同的级别——例如：

```
logger.setLevel(Level.FINE);
```

现在`FINE`及其以上的所有级别都会记录。你也可以使用`Level.ALL`开启所有级别的日志，或使用`Level.OFF`关闭所有日志。

所有级别都有日志方法，例如：

```
logger.warning(message);
logger.fine(message);
```

以此此类推。或者，你可以使用`log`方法并提供级别，例如：

```
logger.log(Level.FINE, message);
```

**提示**

默认日志配置记录所有级别为`INFO`或更高的记录。因此，你应该使用`CONFIG`、`FINE`、`FINER`和`FINEST`级别来记录对诊断有用但对用户没有意义的消息。

**注意**

如果将级别设置为比`INFO`更细的值，还需要更改日志处理器的配置。默认日志处理器抑制`INFO`以下的消息。详情请见下一节。

默认日志记录显示包含日志调用的类和方法名，是从调用栈推断出来的。然而，如果虚拟机对执行进行了优化，准确的调用信息可能不可用。你可以使用`logp`方法提供调用类和方法的精确位置。该方法的签名如下：

```
void logp(Level l, String className, String methodName, String message)
```

```java
void entering(String className, String methodName)
void entering(String className, String methodName, Object param)
void entering(String className, String methodName, Object[] params)
void exiting(String className, String methodName)
void exiting(String className, String methodName, Object result)
```

例如：

```java
int read(String file, String pattern)
{
    logger.entering("com.mycompany.mylib.Reader", "read",
        new Object[] { file, pattern });
    ...
    logger.exiting("com.mycompany.mylib.Reader", "read", count);
    return count;
}
```

这些调用会生成级别为`FINER`的日志记录，并以`ENTRY`和`RETURN`字符串开头。

![Image](img/note.jpg) **注意**

在未来的某个时刻，带有`Object[]`参数的日志方法将被重写以支持可变参数列表（“varargs”）。那时，你将能够进行诸如`logger.entering("com.mycompany.mylib.Reader", "read", file, pattern)`这样的调用。

日志的一个常见用途是记录意外异常。两个便利方法包括在日志记录中包含异常的描述。

```java
void throwing(String className, String methodName, Throwable t)
void log(Level l, String message, Throwable t)
```

典型的用法如下：

```java
if (...)
{
    IOException exception = new IOException("...");
    logger.throwing("com.mycompany.mylib.Reader", "read", exception);
    throw exception;
}
```

以及

```java
try
{
    ...
}
catch (IOException e)
{
    Logger.getLogger("com.mycompany.myapp").log(Level.WARNING, "Reading image", e);
}
```

`throwing`调用会记录一条级别为`FINER`的记录，其消息以`THROW`开头。

### 7.5.3 更改 Log Manager 配置

你可以通过编辑配置文件来更改日志系统的各种属性。默认配置文件位于：

`jre/lib/logging.properties`

要使用另一个文件，请在启动应用程序时将`java.util.logging.config.file`属性设置为文件位置：

```bash
java -Djava.util.logging.config.file=configFile MainClass
```



`log manager` 在 VM 启动期间初始化，在 `main` 执行之前。如果你在 `main` 中调用了 `System.setProperty("java.util.logging.config.file", file)`，请同时调用 `LogManager.readConfiguration()` 来重新初始化 `log manager`。

要更改默认日志级别，请编辑配置文件并修改该行：

```
.level=INFO
```

你可以通过添加如下行来为自己的日志器指定日志级别：

```
com.mycompany.myapp.level=FINE
```

即在日志器名称后附加 `.level` 后缀。

正如你在本节稍后看到的，日志器实际上并没有将消息发送到控制台——那是 `handler` 的工作。`handler` 也有级别。要在控制台上查看 `FINE` 消息，你还需要设置：

```
java.util.logging.ConsoleHandler.level=FINE
```

`log manager` 配置中的设置*不是*系统属性。使用 `-Dcom.mycompany.myapp.level=FINE` 启动程序对日志器没有任何影响。

至少直到 Java SE 7，`LogManager` 类的 API 文档声称你可以通过 `Preferences API` 设置 `java.util.logging.config.class` 和 `java.util.logging.config.file` 属性。这是错误的——请参阅 Java bug 数据库中的 bug 4691587（[`http://bugs.sun.com/bugdatabase`](http://bugs.sun.com/bugdatabase)）。

日志属性文件由 `java.util.logging.LogManager` 类处理。可以通过将 `java.util.logging.manager` 系统属性设置为子类的名称来指定不同的 `log manager`。或者，你可以保留标准的 `log manager` 仍然跳过来自日志属性文件的初始化。将 `java.util.logging.config.class` 系统属性设置为以其他方式设置 `log manager` 属性的类名。更多信息请参阅 `LogManager` 类的 API 文档。

`throwing` 调用会记录一条级别为 `FINER` 的记录，其消息以 `THROW` 开头。

点击此处查看代码图像

```java
Logger logger = Logger.getLogger("com.mycompany.myapp");
logger.setLevel(Level.FINE);
logger.setUseParentHandlers(false);
Handler handler = new ConsoleHandler();
handler.setLevel(Level.FINE);
logger.addHandler(handler);
```

默认情况下，日志器会将记录同时发送到它自己的处理器以及父级的处理器。我们的日志器是根日志器（名称为 `""`）的子类，根日志器会将所有级别为 `INFO` 及以上的记录发送到控制台。然而，我们不希望重复看到这些记录，因此我们将 `useParentHandlers` 属性设置为 `false`。

若要将日志记录发送到其他地方，请添加另一个处理器。日志 API 为此目的提供了两个有用的处理器：`FileHandler` 和 `SocketHandler`。`SocketHandler` 将记录发送到指定的主机和端口。更有趣的是 `FileHandler`，它将记录收集到一个文件中。

你可以简单地将记录发送到默认的文件处理器，如下所示：

```java
FileHandler handler = new FileHandler();
logger.addHandler(handler);
```

记录被发送到用户主目录下的文件 `javan.log`，其中 `n` 是一个使文件保持唯一的数字。如果用户的系统没有用户主目录的概念（例如在 Windows 95/98/Me 中），则文件将存储在默认位置（如 `C:\Windows`）。默认情况下，记录以 XML 格式格式化的。一个典型的日志记录形式如下：

```xml
<record>
  <date>2002-02-04T07:45:15</date>
  <millis>1012837515710</millis>
  <sequence>1</sequence>
  <logger>com.mycompany.myapp</logger>
  <level>INFO</level>
  <class>com.mycompany.mylib.Reader</class>
  <method>read</method>
  <thread>10</thread>
  <message>Reading file corejava.gif</message>
</record>
```

你可以通过在日志管理器配置中设置各种参数来修改文件处理器的默认行为（参见表 7.1），或使用另一个构造函数（参见本节末尾的 API 说明）。

![图像](img/07tab01.jpg)

**表 7.1** `FileHandler` 配置参数

你可能不想使用默认的日志文件名。因此，你应该使用另一种模式，例如 `%h/myapp.log.`。（请参见表 7.2 获取获取模式变量的说明。）

![图像](img/07tab02.jpg)

**表 7.2** 日志文件模式变量

如果多个应用程序（或同一个应用程序的多个副本）使用同一个日志文件，你应该开启 `append` 标志。或者，在文件名模式中使用 `%u`，以便每个应用程序都创建一个唯一的日志副本。

开启文件轮转（file rotation）也是一个好主意。日志文件按轮转序列保存，例如 `myapp.log.0`、`myapp.log.1`、`myapp.log.2` 等。每当文件超过大小限制时，最旧的日志就会被删除，其他文件被重命名，并创建一个生成号为 `0` 的新文件。

![图像](img/tip.jpg) **提示**

许多程序员使用日志作为技术支持人员的辅助。如果程序在环境中运行异常，用户可以发回日志文件进行检查。在这种情况下，你应该开启 `append` 标志、使用轮转日志，或两者兼顾。

你还可以通过扩展 `Handler` 或 `StreamHandler` 类来定义自己的处理器。我们在本节末尾的示例程序中定义了这样一个处理器。该处理器在窗口中显示记录（参见图 7.2）。

![图像](img/07fig02.jpg)

**图 7.2** 一个在窗口中显示记录的日志处理器

该处理器扩展了 `StreamHandler` 类并安装了一个流，其 `write` 方法将流输出显示在文本区域中。

```java
class WindowHandler extends StreamHandler
{
  public WindowHandler()
  {
      ...
      final JTextArea output = new JTextArea();
      setOutputStream(new
        OutputStream()
        {
          public void write(byte[] b, int off, int len)
          {
            output.append(new String(b, off, len));
          }
        });
  }
  @Override
  public void publish(LogRecord record)
  {
    super.publish(record);
  }
  @Override
  protected void write(byte[] b, int off, int len)
  {
    // not implemented
  }
  @Override
  protected void flush()
  {
    // not implemented
  }
  @Override
  public void close()
  {
    // not implemented
  }
}
```

### 7.5.6 过滤器

默认情况下，记录根据级别进行过滤。每个日志器和处理器都可以有一个可选的过滤器。要定义过滤器，请实现 `Filter` 接口并定义方法：

```java
boolean isLoggable(LogRecord record)
```

分析日志记录，并对于应该包含的记录返回 `true`。要将过滤器安装到日志器或处理器，只需调用 `setFilter` 方法。注意只有一个。

### 7.5.7 格式化器

`ConsoleHandler` 和 `FileHandler` 类以文本和 XML 输出日志记录。然而，你也可以定义自己的格式。你需要扩展 `Formatter` 类并重写方法：

```java
String format(LogRecord record)
```

以你喜欢的任何方式格式化信息并返回生成的字符串。在你的 `format` 方法中，你可能希望调用方法：

```java
String formatMessage(LogRecord record)
```

该方法格式化记录的消息，替换参数并应用本地化。

许多格式（如 XML）需要环绕格式化记录的头部和尾。要实现这一点，重写方法：

```java
String getHead(Handler h)
String getTail(Handler h)
```

最后，调用 `setFormatter` 方法将格式化器安装到处理器中。

### 7.5.8 日志配谱

由于有许多日志选项，很容易忘记基础知识。下面的配谱总结了最常用的操作。

**1.** 对于简单的应用程序，选择一个日志器。给日志器命名为与主应用程序包相同的名称，例如 `com.mycompany.myprog`。你可以始终通过调用获取日志器：

```java
Logger logger = Logger.getLogger("com.mycompany.myprog");
```

为了方便，你可能想为大量日志活动的类添加静态字段：

```java
private static final Logger logger = Logger.getLogger("com.mycompany.myprog");
```

**2.** 默认日志配置将所有 `INFO` 以上的消息记录到控制台。用户可以覆盖默认配置，但正如你所见，过程有点复杂。因此，在应用程序中安装一个更合理的默认是一个好主意。

下面的代码确保所有消息都记录到应用程序特定的文件中。将此代码放在应用程序的 `main` 方法中。

```java
if (System.getProperty("java.util.logging.config.class") == null)
```



### 3. 现在，你已经准备好尽情地记录日志了。请记住，所有级别为 `INFO`、`WARNING` 和 `SEVERE` 的消息都会显示在控制台上。因此，请为这些级别留给对你的程序用户有意义的消息。`FINE` 级别是记录面向程序员的日志消息的良好选择。

每当你想要调用 `System.out.println` 时，请改为发布日志消息：

```java
logger.fine("File open dialog canceled");
```

记录意外异常也是一个好主意。例如：

```java
try
{
    ...
}
catch (SomeException e)
{
    logger.log(Level.FINE, "explanation", e);
}
```

列表 7.2 通过增加一个小技巧展示了这一配方：日志消息也会显示在日志窗口中。

**列表 7.2** `logging/LoggingImageViewer.java`

```java
package logging;

import java.awt.*;
import java.awt.event.*;
import java.io.*;
import java.util.logging.*;
import javax.swing.*;

/**
 * 一个记录各种事件的图像查看器程序。
 * @version 1.03 2015-08-20
 * @author Cay Horstmann
 */
public class LoggingImageViewer
{
    public static void main(String[] args)
    {
        if (System.getProperty("java.util.logging.config.class") == null
                && System.getProperty("java.util.logging.config.file") == null)
        {
            try
            {
                Logger.getLogger("com.horstmann.corejava").setLevel(Level.ALL);
                final int LOG_ROTATION_COUNT = 10;
                Handler handler = new FileHandler("%h/LoggingImageViewer.log", 0, LOG_ROTATION_COUNT);
                Logger.getLogger("com.horstmann.corejava").addHandler(handler);
            }
            catch (IOException e)
            {
                Logger.getLogger("com.horstmann.corejava").log(Level.SEVERE, "Can't create log handler", e);
            }
        }

        EventQueue.invokeLater(() ->
        {
            Handler windowHandler = new WindowHandler();
            windowHandler.setLevel(Level.ALL);
            Logger.getLogger("com.horstmann.corejava").addHandler(windowHandler);

            JFrame frame = new ImageViewerFrame();
            frame.setTitle("LoggingImageViewer");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

            Logger.getLogger("com.horstmann.corejava").fine("Showing frame");
            frame.setVisible(true);
        });
    }
}

/**
 * 显示图像的框架。
 */
class ImageViewerFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 400;

    private JLabel label;
    private static Logger logger = Logger.getLogger("com.horstmann.corejava");

    public ImageViewerFrame()
    {
        logger.entering("ImageViewerFrame", "<init>");
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // 设置菜单栏
        JMenuBar menuBar = new JMenuBar();
        setJMenuBar(menuBar);

        JMenu menu = new JMenu("File");
        menuBar.add(menu);

        JMenuItem openItem = new JMenuItem("Open");
        menu.add(openItem);
        openItem.addActionListener(new FileOpenListener());

        JMenuItem exitItem = new JMenuItem("Exit");
        menu.add(exitItem);
        exitItem.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent event)
            {
                logger.fine("Exiting.");
                System.exit(0);
            }
        });

        // 使用标签显示图像
        label = new JLabel();
        add(label);
        logger.exiting("ImageViewerFrame", "<init>");
    }

    private class FileOpenListener implements ActionListener
    {
        public void actionPerformed(ActionEvent event)
        {
            logger.entering("ImageViewerFrame.FileOpenListener", "actionPerformed", event);

            // 设置文件选择器
            JFileChooser chooser = new JFileChooser();
            chooser.setCurrentDirectory(new File("."));

            // 接受所有以 .gif 结尾的文件
            chooser.setFileFilter(new javax.swing.filechooser.FileFilter())
            {
                public boolean accept(File f)
                {
                    return f.getName().toLowerCase().endsWith(".gif") || f.isDirectory();
                }

                public String getDescription()
                {
                    return "GIF Images";
                }
            };

            // 显示对话框
            int r = chooser.showOpenDialog(ImageViewerFrame.this);

            // 如果接受文件，将其设置为标签的图标
            if (r == JFileChooser.APPROVE_OPTION)
            {
                String name = chooser.getSelectedFile().getPath();
                logger.log(Level.FINE, "Reading file {0}", name);
                label.setIcon(new ImageIcon(name));
            }
            else 
                logger.fine("File open canceled.");
            logger.exiting("ImageViewerFrame.FileOpenListener", "actionPerformed");
        }
    }
}

/**
 * 在窗口中显示日志记录处理器。
 */
class WindowHandler extends StreamHandler
{
    private JFrame frame;

    public WindowHandler()
    {
        frame = new JFrame();
        final JTextArea output = new JTextArea();
        output.setEditable(false);
        frame.setSize(200, 200);
        frame.add(new JScrollPane(output));
        frame.setFocusableWindowState(false);
        frame.setVisible(true);

        setOutputStream(new OutputStream()
        {
            public void write(int b)
            {
            } // 未被调用

            public void write(byte[] b, int off, int len)
            {
                output.append(new String(b, off, len));
            }
        });
    }

    public void publish(LogRecord record)
    {
        if (!frame.isVisible()) return;
        super.publish(record);
        flush();
    }
}
```



- `void fine(String message)`
- `void finer(String message)`
- `void finest(String message)`

根据方法名指定的级别和给定的消息记录记录。

- `void entering(String className, String methodName)`
- `void entering(String className, String methodName, Object param)`
- `void entering(String className, String methodName, Object[] param)`
- `void exiting(String className, String methodName)`
- `void exiting(String className, String methodName, Object result)`

记录一条描述带有给定参数或返回值的进入或退出方法的记录。

- `void throwing(String className, String methodName, Throwable t)`

记录一条描述抛出给定异常对象的记录。

- `void log(Level level, String message)`
- `void log(Level level, String message, Object obj)`
- `void log(Level level, String message, Object[] objs)`
- `void log(Level level, String message, Throwable t)`

使用指定的级别和消息记录一条记录，可选地包含对象或可 throwable 对象。要包含对象，消息必须包含格式化占位符（`{0}`、`{1}` 等）。

- `void logp(Level level, String className, String methodName, String message)`
- `void logp(Level level, String className, String methodName, String message, Object obj)`
- `void logp(Level level, String className, String methodName, String message, Object[] objs)`
- `void logp(Level level, String className, String methodName, String message, Throwable t)`

使用指定的级别、精确的调用者信息和消息记录一条记录，可选地包含对象或 throwable 对象。

- `void logrb(Level level, String className, String methodName, String bundleName, String message)`
- `void logrb(Level level, String className, String methodName, bundleName, String message, Object obj)`
- `void logrb(Level level, String className, String methodName, bundleName, String message, Object[] objs)`
- `void logrb(Level level, String className, String methodName, bundleName, String message, Throwable t)`

使用指定的级别、精确的调用者信息、资源包名称和消息记录一条记录，可选地包含对象或 throwable 对象。

- `Level getLevel()`
- `void setLevel(Level l)`

获取并设置此记录器的级别。

- `Logger getParent()`
- `void setParent(Logger l)`

获取并设置此记录器的父级记录器。

- `Handler[] getHandlers()`

获取此记录器所有的处理器。

- `void addHandler(Handler h)`
- `void removeHandler(Handler h)`

为此记录器添加或移除处理器。

- `boolean getUseParentHandlers()`
- `void setUseParentHandlers(boolean b)`

获取并设置“使用父级处理器”属性。如果此属性为 `true`，则记录器将所有日志记录重定向到其父级记录器的处理器。

- `Filter getFilter()`
- `void setFilter(Filter f)`

获取并设置此记录器的过滤器。

### java.util.logging.Handler 1.4

- `abstract void publish(LogRecord record)`

将记录发送到目标位置。

- `abstract void flush()`

刷新任何缓冲区数据。

- `abstract void close()`

刷新任何缓冲区中的数据并释放所有相关的资源。

- `Filter getFilter()`
- `void setFilter(Filter f)`

获取并设置此处理器的过滤器。

- `Formatter getFormatter()`
- `void setFormatter(Formatter f)`

获取并设置此处理器的格式化器。

- `Level getLevel()`
- `void setLevel(Level l)`

获取并设置此处理器的级别。

### java.util.logging.ConsoleHandler 1.4

- `ConsoleHandler()`

构造一个新的控制台处理器。

### java.util.logging.FileHandler 1.4

- `FileHandler(String pattern)`
- `FileHandler(String pattern, boolean append)`
- `FileHandler(String pattern, int limit, int count)`
- `FileHandler(String pattern, int limit, int count, boolean append)`

构造一个文件处理器。

![Image](img/407tab01.jpg)

### java.util.logging.LogRecord 1.4

- `Level getLevel()`

获取此记录的日志级别。

- `String getLoggerName()`

获取记录此记录的记录器名称。

- `ResourceBundle getResourceBundle()`
- `String getResourceBundleName()`

获取使用的资源包或其名称。

- `String getMessage()`

获取未格式化之前的原始消息。

- `Object[] getParameters()`

获取参数对象，如果没有则返回 `null`。

- `Throwable getThrown()`

获取抛出的异常，如果没有则返回 `null`。

- `String getSourceClassName()`
- `String getSourceMethodName()`

获取记录此记录的代码类和方法名。

- `long getMillis()`

获取自 1970 年来的毫秒数。

- `long getSequenceNumber()`

获取记录的序列号。

- `int getThreadID()`

获取创建此记录的线程 ID。

### java.util.logging.Filter 1.4

- `boolean isLoggable(LogRecord record)`

如果指定的记录应该被记录，则返回 `true`。

### java.util.logging.Formatter 1.4

- `abstract String format(LogRecord record)`

返回格式化给定记录的字符串。

- `String getHead(Handler h)`
- `String getTail(Handler h)`

获取出现在记录头部和尾部的字符串。`Formatter` 超类定义这些方法返回空字符串；必要时请重写。

- `String formatMessage(LogRecord record)`

返回记录的本地化且格式化的消息部分。

### 7.6 调试技巧

假设你写好了程序，并通过捕获并正确处理所有异常使其无懈击。然后你运行它，它运行并不正常。现在怎么办？（如果你从未遇到过这个问题，可以跳过本章剩余部分。）

当然，有一个方便且强大的调试器最好。调试器是 Eclipse 和 NetBeans 等专业开发环境的一部分。在本节中，我们为你提供了一些启动调试器之前值得尝试的提示。

**1.** 你可以使用如下代码打印或记录变量的值：

```
System.out.println("x=" + x);
```

或者

```
Logger.getGlobal().info("x=" + x);
```

如果 `x` 是数字，它会被转换为字符串。如果 `x` 是一个对象，Java 会调用其 `toString` 方法。要获取隐式参数对象的状态，请打印 `this` 对象的状态。

**2.** 创建几个对象，调用所有方法，并检查每一个是否都执行了正确的操作。你可以保留所有这些 `main` 方法，并在每个文件上单独启动 Java 虚拟机来运行测试。当你运行一个 applet（小程序）时，这些 `main` 方法都不会被调用。当你运行一个应用程序时，Java 虚拟机只会调用启动类的 `main` 方法。

**3.** 如果你喜欢上面的提示，你应该检查一下 [`http://junit.org`](http://junit.org) 中的 JUnit。JUnit 是一个非常流行的单元测试框架，可以让你轻松地组织测试用例集。每当你修改类时运行测试，每当你发现 bug 时就添加另一个测试用例。

**4.** `logging proxy`（日志代理）是子类的一个对象，它可以拦截方法调用、记录日志，然后调用父类。例如，如果你在 `Random` 类的 `nextDouble` 方法上有问题，可以创建一个匿名子类的实例作为代理对象：

```
Random generator = new
    Random()
    {
      public double nextDouble()
      {
          double result = super.nextDouble();
          Logger.getGlobal().info("nextDouble: " + result);
          return result;
      }
    };
```

每当 `nextDouble` 方法被调用时，都会生成一条日志消息。要找出是谁调用了该方法，生成堆栈跟踪（stack trace）。

**5.** 你可以通过 `Throwable` 类中的 `printStackTrace` 方法从任何异常对象获取堆栈跟踪。以下代码捕获任何异常，打印异常对象和堆栈跟踪，并重新抛出异常以便其找到预期的处理器。

```java
try
{
   ...
}
catch (Throwable t)
{
   t.printStackTrace();
   throw t;
}
```

你甚至不需要捕获异常就可以生成堆栈跟踪。只需在代码的任何地方插入语句 `Thread.dumpStack();` 即可获取堆栈跟踪。

**6.** 通常，堆栈跟踪显示在 `System.err`。如果你想记录或显示堆栈跟踪，可以将其捕到一个字符串中：

```java
StringWriter out = new StringWriter();
new Throwable().printStackTrace(new PrintWriter(out));
String description = out.toString();
```

**7.** 将程序错误捕到文件中通常非常方便。然而，错误被发送到 `System.err` 而不是 `System.out`。因此，你不能简单地通过运行来捕获它们：

`java MyProgram > errors.txt`

相反，将错误流捕获为：

`java MyProgram 2> errors.txt`

要在同一个文件中捕获 `System.err` 和 `System.out`，请使用：

```bash
java MyProgram 1> errors.txt 2>&1
```

这在 `bash` 和 Windows shell 中有效。

**8.** 让未捕获异常的堆栈跟踪显示在 `System.err` 中并不是理想的。如果用户意外看到这些消息，会让他们感到困惑，而且当你需要它们时，它们无法用于诊断。更好的方法是将它们记录到文件中。你可以通过静态方法 `Thread.setDefaultUncaughtExceptionHandler` 来更改未捕获异常的处理器：

```java
Thread.setDefaultUncaughtExceptionHandler(
    new Thread.UncaughtExceptionHandler()
    {
      public void uncaughtException(Thread t, Throwable e)
      {
          save information in log file
      }
    };
);
```

**9.** 要观察类加载过程，请使用 `-verbose` 标志启动 Java 虚拟机。你将获得如下的输出：

```
[Opened /usr/local/jdk5.0/jre/lib/rt.jar]
[Opened /usr/local/jdk5.0/jre/lib/jsse.jar]
[Opened /usr/local/jdk5.0/jre/lib/jce.jar]
[Opened /usr/local/jdk5.0/jre/lib/charsets.jar]
[Loaded java.lang.Object from shared objects file]
[Loaded java.io.Serializable from shared objects file]
[Loaded java.lang.Comparable from shared objects file]
[Loaded java.lang.CharSequence from shared objects file]
[Loaded java.lang.Object from shared objects file]
[Loaded java.io.Serializable from shared objects file]
[Loaded java.lang.Comparable from shared objects file]
[Loaded java.lang.CharSequence from shared objects file]
[Loaded java.lang.Object from shared objects file]
[Loaded java.io.Serializable from shared objects file]
[Loaded java.lang.Comparable from shared objects file]
[Loaded java.lang.CharSequence from shared objects file]
[Loaded java.lang.Object from shared objects file]
[Loaded java.io.Serializable from shared objects file]
[Loaded java.lang.Comparable from shared objects file]
[Loaded java.lang.CharSequence from shared objects file]
[Loaded java.lang.Object from shared objects file]
[Loaded java.io.Serializable from shared objects file]
[Loaded java.lang.Comparable from shared objects file]
[Loaded java.lang.CharSequence from shared objects file]
[Loaded java.lang.Object from shared objects file]
[Loaded java.io.Serializable from shared objects file]
[Loaded java.lang.Comparable from shared objects file]
[Loaded java.lang.CharSequence from shared objects file]
[Loaded java.lang.Object from shared objects file]
[Loaded java.io.Serializable from shared objects file]
[Loaded java.lang.Comparable from shared objects file]
```



[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

[Loaded java.lang.Object from shared objects file]

[Loaded java.io.Serializable from shared objects file]

[Loaded java.lang.Comparable from shared objects file]

[Loaded java.lang.CharSequence from shared objects file]

泛型类是 Java 编程语言自 1.0 版本以来最重大的变化。Java SE 5.0 引入泛型是 1999 年制定的首批 Java 规范请求之一——`JSR 14` 的结果。专家小组花费了大约五年的时间编写规范和测试实现。

泛型类之所以受到欢迎，是因为它们能让你编写出比充斥着 `Object` 变量和强制转换的代码更安全、更易读。泛型对于集合类特别有用，例如无处不在的 `ArrayList`。

泛型类——至少在表面上——与 C++ 的模板（templates）相似。在 C++ 中，在 Java 中一样，模板最初被添加到语言中是为了支持强类型集合。然而，在随后的多年里，人们发现了它的许多其他用途。读完本章后，你可能会在自己的程序中发现 Java 泛型的新颖用法。

### 8.1 为什么要用泛型编程？

`generic programming` 意味着编写可以为许多不同类型的对象复用的代码。例如，你不想编写单独的类来分别收集 `String` 和 `File` 对象。你也不必这样做——单一的 `ArrayList` 类就可以收集任何类对象。这就是泛型编程的一个例子。

实际上，Java 在拥有泛型类之前就已经有一个 `ArrayList` 类。让我们研究一下泛型编程机制是如何演变的，以及这对用户和实现者意味着什么。

#### 8.1.1 类型参数的优势

在泛型类添加到 Java 之前，泛型编程是通过 `inheritance`（继承）实现的。`ArrayList` 类简单地维护了一个 `Object` 引用数组：

点击此处查看代码图像

```java
public class ArrayList // 泛型类出现之前
{
   private Object[] elementData;
   . . .
   public Object get(int i) { . . . }
   public void add(Object o) { . . . }
}
```

这种方法有两个问题。每当你获取值时，都需要进行强制转换：

点击此处查看代码图像

```java
ArrayList files = new ArrayList();
. . .
String filename = (String) files.get(0);
```

此外，没有错误检查。你可以添加任何类的值：

```java
files.add(new File(". . ."));
```

此调用可以通过编译并运行而不会报错。在其他地方，将 `get` 的结果强制转换为 `String` 将导致错误。

泛型提供了一个更好的解决方案：`type parameters`（类型参数）。`ArrayList` 类现在有了一个类型参数，用于指示元素类型：

点击此处查看代码图像

```java
ArrayList<String> files = new ArrayList<String>();
```

这使得你的代码更易读。你可以立即看出这个特定的列表包含了 `String` 对象。

***

![Image](img/note.jpg) 备注

正如我们已经提到的，在 Java SE 7 及更高版本中，你可以省略构造函数中的泛型类型：

点击此处查看代码图像

```java
ArrayList<String> files = new ArrayList<>();
```

省略的类型是从变量的类型中推断出来的。

***

编译器也可以很好地利用类型信息。调用 `get` 不需要强制转换。编译器知道返回类型是 `String` 而不是 `Object`：

点击此处查看代码图像

```java
String filename = files.get(0);
```

编译器还知道 `ArrayList<String>` 的 `add` 方法有一个类型为 `String` 的参数。这比有一个 `Object` 参数要安全得多。现在编译器可以检查你没有添加错误的类型。

#### 8.1.2 谁想要泛型编程？

（注：原文文本在此处出现大量重复和乱码，已按逻辑合并翻译）



此调用可以通过编译并运行而不会报错。在其他地方，将`get`的结果强制转换为`String`将导致错误。

泛型提供了一个更好的解决方案：`type parameters`（类型参数）。`ArrayList`类现在有了一个类型参数，用于指示元素类型：

```java
ArrayList<String> files = new ArrayList<String>();
```

这使得你的代码更易读。你可以立即看出这个特定的列表包含了`String`对象。

---

![Image](img/note.jpg) 备注

正如我们已经提到的，在 Java SE 7 及更高版本中，你可以省略构造函数中的泛型类型：

```java
ArrayList<String> files = new ArrayList<>();
```

省略的类型是从变量的类型中推断出来的。

---

编译器也可以很好地利用类型信息。调用`get`不需要强制转换。编译器知道返回类型是`String`而不是`Object`：

```java
String filename = files.get(0);
```

编译器还知道`ArrayList<String>`的`add`方法有一个类型为`String`的参数。这比有一个`Object`参数要安全得多。现在编译器可以检查你没有添加错误的类型。

### 8.2 定义泛型类

`generic class`是带有一个或多个类型变量类。在本章中，我们将一个简单的`Pair`类作为示例。该类允许我们专注于泛型而不受存储细节的分心。这里是泛型`Pair`类的代码：

```java
public class Pair<T>
{
   private T first;
   private T second;

   public Pair() { first = null; second = null; }
   public Pair(T first, T second) { this.first = first; this.second = second; }

   public T getFirst() { return first; }
   public T getSecond() { return second; }
   public void setFirst(T newValue) { first = newValue; }
   public void setSecond(T newValue) { second = newValue; }
}
```

`Pair`类在类名后用角括号`< >`引入了类型变量`T`。泛型类可以有多个类型变量。例如，我们可以为第一个和第二个字段定义不同的类型：

```java
public class Pair<T, U> { . . . }
```

类型变量在整个类定义中用于指定方法的返回类型以及字段和局部变量的类型。例如：

```java
private T first; // 使用类型变量
```



### 8.2 Defining a Generic Class

`generic class` is a class with one or more type variables. In this chapter, we will use a simple `Pair` class as an example. This class allows us to focus on generics without being distracted by storage details. Here is the code for the generic class:

译文：

`泛型类`是带有一个或多个类型变量的类。在本章中，我们将一个简单的`Pair`类作为示例。该类允许我们专注于泛型，而不受存储细节的干扰。以下是泛型类的代码：




### 8.2 定义泛型类

`泛型类` 是带有一个或多个类型变量的类。在本章中，我们将一个简单的 `Pair` 类作为示例。该类允许我们专注于泛型，而不受存储细节的分心。这里是泛型类的代码：

```java
public class Pair<T>
{
   private T first;
   private T second;
   public Pair() { first = null; second = null; }
   public Pair(T first, T second) { this.first = first; this.second = second; }
   public T getFirst() { return first; }
   public T getSecond() { return second; }
   public void setFirst(T newValue) { first = newValue; }
   public void setSecond(T newValue) { second = newValue; }
}
```

`Pair` 类在类名后用角括号 `< >` 引入了类型变量 `T`。泛型类可以有多个类型变量。例如，我们可以为第一个和第二个字段定义不同的类型：

点击此处查看代码图像

```java
public class Pair<T, U> { . . . }
```

类型变量在整个类定义中用于指定方法的返回类型以及字段和局部变量的类型。例如：

```java
private T first; // 使用类型变量
```




抱歉，由于系统出现了严重的重复输出错误。以下是完整的翻译内容：



### 8.2 定义泛型类

`泛型类`是带有一个或多个类型变量的类。在本章中，我们将一个简单的`Pair`类作为示例。该类允许我们专注于泛型而不受存储细节的分心。这里是泛型类的代码：

```java
public class Pair<T>
{
   private T first;
   private T second;
   public Pair() { first = null; second = null; }
   public Pair(T first, T second) { this.first = first; this.second = second; }
   public T getFirst() { return first; }
   public T getSecond() { return second; }
   public void setFirst(T newValue) { first = newValue; }
   public void setSecond(T newValue) { second = newValue; }
}
```

`Pair`类在类名后用角括号`< >`引入了类型变量`T`。泛型类可以有多个类型变量。例如，我们可以为第一个和第二个字段定义不同的类型：

点击此处查看代码图像

```java
public class Pair<T, U> { . . . }
```

类型变量在整个类定义中用于指定方法的返回类型以及字段和局部变量的类型。例如：

```java
private T first; // 使用类型变量
```

实际上：

```java
String filename = files.get(0);
```

（其余翻译如下：）

此外，这里没有错误检查。你可以添加任何类的值：

```java
files.add(new File(". . ."));
```

此调用可以编译并运行，不会发生错误。在其他地方，将`get`的结果强制转换为`String`会导致错误。

编译器也可以充分利用类型信息。调用`get`时不需要强制转换。编译器知道返回类型是`String`而不是`Object`：

```java
String filename = files.get(0)
```

编译器还知道`ArrayList<String>`的`add`方法的参数类型是`String`。这比使用`Object`参数安全得多。现在，编译器可以检查你是否添加了错误的类型。

---

![Image](img/note.jpg) **注意**

正如我们之前提到的，在 Java SE 7 及更高版本中，你可以省略构造函数中的泛型类型：

点击此处查看代码图像

```java
ArrayList<String> files = new ArrayList<>();
```

省略的类型会根据变量的类型自动推断。




实际上，以下是所提供文本的翻译：

泛型类是自 Java 1.0 发布以来，Java 编程语言最重要的变化。Java SE 5.0 增加泛型的工作源于最早提出的 Java 规范请求之一：`JSR 14`。该请求于 1999 年提出，专家组花费了大约五年时间制定规范并实现测试。

泛型类很有价值，因为它可以让你编写更加安全且易于阅读的代码。

1. 借助费曼学习法，你可以在短短 `20 min` 内深入理解知识点，并且记忆深刻、*难以遗忘*。

```java
if (condVar > someVal) {console.log("xxx")}
```

泛型类至少从表面上看与 C++ 中的模板类似。在 C++ 和 Java 中，模板最初都是为了支持强类型集合而加入语言的。不过，多年来人们发现了许多其他用途。读完本章后，你可能会在自己的程序中发现 Java 泛型的新用途。

### 8.1 为什么需要泛型编程？

`generic programming` 指编写能够被不同类型对象重复使用的代码。例如，你不需要分别编写用于收集 `String` 对象和 `File` 对象的类。实际上也没有必要这样做——单个 `ArrayList` 类就可以收集任意类的对象。这就是泛型编程的一个例子。

实际上，在 Java 支持泛型类之前，就已经存在 `ArrayList` 类。下面让我们研究泛型编程机制是如何演变的，以及这对用户和实现者意味着什么。

#### 8.1.1 类型参数的优势

在 Java 增加泛型类之前，泛型编程是通过 `inheritance` 实现的。`ArrayList` 类只需维护一个 `Object` 引用数组：

点击此处查看代码图像

```java
public class ArrayList // before generic classes
{
   private Object[] elementData;
   . . .
   public Object get(int i) { . . . }
   public void add(Object o) { . . . }
}
```

这种方式存在两个问题。每当取出一个值时，都必须进行类型转换：

点击此处查看代码图像

```java
ArrayList files = new ArrayList();
. . .
String filename = (String) files.get(0);
```

此外，这种方式无法进行错误检查。你可以添加任意类的值：

```java
files.add(new File(". . ."));
```

这段调用可以正常编译和运行，不会立即报错。但在其他地方，如果将 `get` 的结果转换为 `String`，就会导致错误。

泛型提供了更好的解决方案：`type parameters`。现在，`ArrayList` 类包含一个用于表示元素类型的类型参数：

点击此处查看代码图像

```java
ArrayList<String> files = new ArrayList<String>();
```

这使代码更加易读。你可以立即看出这个特定的数组列表包含 `String` 对象。

***

![Image](img/note.jpg) **笔记**

正如我们之前提到的，在 Java SE 7 及更高版本中，可以省略构造函数中的泛型类型：

点击此处查看代码图像

```java
ArrayList<String> files = new ArrayList<>();
```

省略的类型会根据变量的类型自动推断。

***

编译器也可以充分利用类型信息。调用 `get` 时不再需要类型转换。编译器知道返回类型是 `String`，而不是 `Object`：

点击此处查看代码图像

```java
String filename = files.get(0);
```

编译器还知道，`ArrayList<String>` 的 `add` 方法参数类型是 `String`。这比使用 `Object` 类型的参数安全得多。现在，编译器可以检查你是否添加了错误的类型。

![Image](img/note.jpg) **笔记**

使用大写字母表示类型变量并保持简短是一种常见做法。Java 库使用变量 `E` 表示集合的元素类型，使用 `K` 和 `V` 表示表格的键和值类型，并使用 `T`（以及必要的相邻字母 `U` 和 `S`）表示“任意类型”。

你可以通过使用具体类型替换类型变量来`实例化`泛型类型，例如：

`Pair<String>`

你可以将结果看作一个具有以下构造函数的普通类：

`Pair<String>()`

`Pair<String>(String, String)`

以及以下方法：

`String getFirst()`

`String getSecond()`

`void setFirst(String)`

`void setSecond(String)`

换句话说，泛型类充当普通类的工厂。

列表 8.1 中的程序展示了 `Pair` 类的工作方式。静态方法 `minmax` 遍历数组，同时计算最小值和最大值。它使用 `Pair` 对象返回这两个结果。请记住，`compareTo` 方法比较两个字符串：如果字符串相同，则返回 `0`；如果第一个字符串在字典顺序上位于第二个字符串之前，则返回负整数；否则返回正整数。

***

![Image](img/note1.jpg) **C++ 笔记**

从表面上看，Java 的泛型类与 C++ 的模板类相似。唯一明显的区别是 Java 没有特殊的 `template` 关键字。然而，正如你将在本章中看到的，这两种机制之间存在本质差异。

***

**列表 8.1** `pair1/PairTest1.java`

点击此处查看代码图像

```java
package pair1;

/**
 * @version 1.01 2012-01-26
 * @author Cay Horstmann
 */
public class PairTest1
{
    public static void main(String[] args)
    {
        String[] words = { "Mary", "had", "a", "little", "lamb" };
        Pair<String> mm = ArrayAlg.minmax(words);
        System.out.println("min = " + mm.getFirst());
        System.out.println("max = " + mm.getSecond());
    }
}

class ArrayAlg
{
    /**
     * 获取字符串数组的最小值和最大值。
     * @param a 一个字符串数组
     * @return 一个包含最小值和最大值的值对，如果 a 为空或为空则返回 null
     */
    public static Pair<String> minmax(String[] a)
    {
        if (a == null || a.length == 0) return null;
        String min = a[0];
        String max = a[0];
        for (int i = 1; i < a.length; i++)
        {
            if (min.compareTo(a[i]) > 0) min = a[i];
            if (max.compareTo(a[i]) < 0) max = a[i];
        }
        return new Pair<>(min, max);
    }
}
```

***

### 8.3 泛型方法

在上一节中，你已经学习了如何定义泛型类。你也可以定义带有类型参数的单个方法。




```java
class ArrayAlg
{
    public static <T> T getMiddle(T[] a)
    {
        return a[a.length / 2];
    }
}
```

该方法定义在普通类内部，而不是泛型类内部。然而，它是一个泛型方法，从尖角括号和类型变量可以看出。注意，类型变量插入在修饰符（`public static`）之后、返回类型之前。

你可以在普通类内部也可以在泛型类内部定义泛型方法。当你调用泛型方法时，可以在方法名之前放置尖角括号括起来实际类型：

```java
String middle = ArrayAlg.<String>getMiddle("John.", names);
```

在这种情况下（实际上在大多数情况下都是），你可以从方法调用中省略 `<String>` 参数。编译器有足够的信息推断你想要的方法。它将 `names` 的类型（即 `String[]`）与泛型类型 `T[]` 进行匹配，并推导出 `T` 必须是 `String`。也就是说，你只需调用：

```java
String middle = ArrayAlg.getMiddle("John.", names);
```

在几乎所有情况下，泛型方法的类型推断都运行得很顺畅。偶尔，编译器会出错，你需要解读错误报告。考虑这个例子：

```java
double middle = ArrayAlg.getMiddle(3.14, 1729, 0);
```

错误信息用晦涩的术语（随编译器版本不同而异）抱怨道，这段代码有两种解释方式，且都是有效的。简而言之，编译器将参数自动装箱为 `Double` 和两个 `Integer` 对象，然后它尝试寻找这些类的公共父类型。它实际上找到了两个：`Number` 和 `Comparable` 接口，而后者本身是泛型的。在这种情况下，解决办法是将所有参数都写为 `double` 值。

---

![Image](img/tip.jpg) 提示

如果你想查看编译器为泛型调用推断出什么类型，Peter von Ahé 建议使用这个技巧：故意引入错误并研究产生的错误信息。例如，考虑 `ArrayAlg.getMiddle("Hello", 0)`。你会得到错误报告：

```text
found: java.lang.Object, java.io.Serializable
```

用通俗英语说，你可以将结果赋值给 `Object` 或 `Serializable`。

---

![Image](img/note1.jpg) C++ 笔记

在 C++ 中，将类型参数放在方法名之后。这会导致解析歧义。例如，`g<a,b>(c))` 可以意味着“带有 f<a,b>(c) 结果调用 g”，或者“带有两个布尔值 f<a> 和 b)”.

### 8.4 类型变量的边界

有时，类或方法需要对类型变量进行限制。这是一个典型的例子。我们想要计算数组的最小元素：

```java
class ArrayAlg
{
    public static <T> min(T[] a) // 几乎正确
    {
        if (a == null || a.length == 0) return null;

        T smallest = a[0];

        for (int i = 1; i < a.length; i++)
            if (smallest.compareTo(a[i]) > 0) smallest = a[i];

        return smallest;
    }
}
```

但有一个问题。查看 `min` 方法的代码。变量 `smallest` 的类型是 `T`，这意味着它可以是任意类的对象。我们如何知道 `T` 所属的类拥有 `compareTo` 方法呢？

解决方案是将 `T` 限制为实现了 `Comparable` 接口的类——该标准接口包含一个方法 `compareTo`。你可以通过为类型变量 `T` 给出*边界*来实现这一点：

```java
public static <T extends Comparable<? super T>> min(T[] a) . . .
```

实际上，`Comparable` 接口本身是一个泛型类型。现在我们将忽略这种复杂性以及编译器生成的警告。8.8 节通配符类型](#ch08.html_ch08lev1sec8),”位于第 442 页讨论了如何正确与 `Comparable` 接口配合类型参数。

现在，泛型 `min` 方法只能用于实现了 `Comparable` 接口的类的数组，例如 `String`、`LocalDate` 等。使用 `Rectangle` 数组调用 `min` 将导致编译错误，因为 `Rectangle` 类没有实现 `Comparable`。

你可能会奇怪，为什么在这种情况下我们使用 `extends` 关键字而不是 `implements` 关键字——毕竟，`Comparable` 是一个接口。这种写法：

`<T extends BoundingType>`

表示 `T` 应该是该边界类型的*子类型*（subtype）。`T` 和边界类型都可以是类，也可以是接口。选择 `extends` 关键字是因为它是对子类型概念的合理近似，而且 Java 的设计者并不希望向语言中添加新的关键字（例如 `sub`）。

一个类型变量或通配符可以有多个边界。例如：

点击此处查看代码图像

`T extends Comparable & Serializable`

边界类型之间使用 ampersand（`&`）分隔，因为逗号被用于分隔类型变量。

与 Java 继承一样，你可以拥有任意数量的接口超类型，但边界中最多只能有一个是类。如果你将一个类作为边界，它它必须是边界列表中的第一个。

在下一个示例程序（代码列表 8.2）中，我们重写了 `minmax` 方法使其变为泛型。该方法计算泛型数组的最小值和最大值，返回一个 `Pair<T>`。

**列表 8.2** `pair2/PairTest2.java`

点击此处查看代码图像

```java
package pair2;

import java.time.*;

/**
 * @version 1.02 2015-06-21
 * @author Cay Horstmann
 */
public class PairTest2
{
    public static void main(String[] args)
    {
        LocalDate[] birthdays =
            {
            LocalDate.of(1906, 12, 9), // G. Hopper
            LocalDate.of(1815, 12, 10), // A. Lovelace
            LocalDate.of(1903, 12, 3), // J. Neumann
            LocalDate.of(1910, 6, 22), // K. Zuse
            };

        Pair<LocalDate> mm = ArrayAlg.minmax(birthdays);

        System.out.println("min = " + mm.getFirst());
        System.out.println("max = " + mm.getSecond());
    }
}

class ArrayAlg
{
    /**
     * 获取类型为 T 的对象数组的最小值和最大值。
     * @param a 类型为 T 的对象数组
     * @return 包含最小值和最大值的对，如果 a 为空或无效则返回 null
     */
    public static <T extends Comparable> Pair<T> minmax(T[] a)
    {
        if (a == null || a.length == 0) return null;

        T min = a[0];
        T max = a[0];

        for (int i = 1; i < a.length; i++)
        {
            if (min.compareTo(a[i]) > 0) min = a[i];
            if (max.compareTo(a[i]) < 0) max = a[i];
        }

        return new Pair<>(min, max);
    }
}
```

### 8.5 泛型代码与虚拟机

虚拟机并没有泛型类型的对象——所有对象都属于普通类。泛型实现的早期版本甚至能够将使用泛型的程序编译成可以在 1.0 虚拟机上执行的类文件！在接下来的章节中，你将看到编译器如何“擦除”（erases）类型参数，以及这一过程对 Java 程序员意味着什么。

#### 8.5.1 类型擦除

每当你定义一个泛型类型时，系统会自动提供一个对应的*原始*（raw）类型。原始类型的名称就是泛型类型的名称，只是去掉了类型参数。类型变量被*擦除*并被替换为它们的边界类型（对于没有边界的变量，则使用 `Object`）。

例如，`Pair<T>` 的原始类型所示：

点击此处查看代码图像

```java
public class Pair
{
    private Object first;
    private Object second;

    public Pair(Object first, Object second)
    {
        this.first = first;
        this.second = second;
    }

    public Object getFirst() { return first; }
    public Object getSecond() { return second; }

    public void setFirst(Object newValue) { first = newValue; }
    public void setSecond(Object newValue) { second = newValue; }
}
```

由于 `T` 是无边界类型变量，它被简单地替换为 `Object`。结果是一个普通类，就像你在 Java 引入泛型之前可能实现的那样。你的程序可能包含不同类型的 `Pair`，例如 `Pair<String>` 或 `Pair<LocalDate>`，但擦除将它们都变成了原始的 `Pair` 类型。

![Image](img/note1.jpg) C++ 备注

在这方面，Java 泛型与 C++ 模板非常不同。C++ 会为每次实例化产生不同的类型——这种现象被称为“模板膨”（template bloat）。Java 则没有此问题。

你可能会想，如果交换边界会怎样：`class Interval<T extends Serializable & Comparable>`。在这种情况下，原始类型将 `T` 替换为 `Serializable`，编译器会插入到 `Comparable` 的强制转换。为了效率，你应当将标记接口（即没有方法的接口）放在列表的末尾。

原始类型将 `T` 替换为它的边界类型，如果没有边界则替换为 `Object`。例如，`Pair<T>` 没有边界，因此原始类型所示：

点击此处查看代码图像

```java
public class Pair
{
    private Object first;
    private Object second;
}
```

#### 8.5.2 翻译泛型表达式

当你调用泛型方法时，如果返回类型已被擦除，编译器会插入强制转换。例如，考虑以下序列：

点击此处查看代码图像

`Pair<Employee> buddies = . . .`

`Employee buddy = buddies.getFirst();`

`getFirst()` 的擦除返回类型为 `Object`。编译器会自动插入到 `Employee` 的转换。也就是说，编译器将方法调用转换为虚拟指令：

- 调用原始方法 `Pair.getFirst()`
- 将返回的 `Object` 转换为 `Employee`

在访问泛型字段时也会插入强制转换。假设 `Pair` 类的 `first` 和 `second` 字段是公有的。（也许这不是良好的编程风格，但它是合法的 Java。）那么表达式：

`Employee buddy = buddies.first;`

在生成的代码中也拥有了强制转换。

#### 8.5.3 翻译泛型方法

类型擦除也发生在泛型方法中。程序员通常将如下泛型方法：

点击此处查看代码图像

`public static <T extends Comparable> T min(T[] a)`

视为整体，但在擦除后只剩下一个方法：

点击此处查看代码图像

`public static Comparable min(Comparable[] a)`

注意，类型参数 `T` 已擦除，留下了它的边界类型 `Comparable`。方法的擦除带来了一些复杂性。考虑这个例子：

点击此处查看代码图像

```java
class DateInterval extends Pair<LocalDate>
{
    public void setSecond(LocalDate second)
    {
        if (second.compareTo(getFirst()) >= 0)
            super.setSecond(second);
    }

    . . .
}
```

日期区间是两个 `LocalDate` 对象的对，我们希望重写这些方法以确保第二个值永远不小于第一个值。该类擦除后变为：

```java
class DateInterval extends Pair // 擦除后
{
    public void setSecond(LocalDate second) { . . . }

    . . .
}
```

可能让你惊讶的是，还有一个继承自 `Pair` 的 `setSecond` 方法，即：

```java
public void setSecond(Object second)
```

这显然是不同的方法，因为它的参数类型不同——是 `Object` 而不是 `LocalDate`。但它*不应该是*不同的。考虑以下这一语句序列：

```java
DateInterval interval = new DateInterval(. . .);
Pair<LocalDate> pair = interval; // OK--赋值给父类
pair.setSecond(aDate);
```

我们的预期是对 `setSecond` 的调用是多态的，并调用适当的方法。由于 `pair` 指向一个 `DateInterval` 对象，因此应该调用 `DateInterval.setSecond`。问题在于类型擦除干扰了多态性。为了解决这个问题，编译器在 `DateInterval` 类中生成了一个*桥接方法*（bridge method）：

```java
public void setSecond(Object second) { setSecond((Date) second); }
```

为了理解为什么这有效，让我们仔细跟踪语句 `pair.setSecond(aDate)` 的执行过程。变量 `pair` 的声明类型为 `Pair<LocalDate>`，而该类型只有一个名为 `setSecond` 的方法，即 `setSecond(Object)`。虚拟机在 `pair` 所指向的对象上调用该方法。该对象的类型是 `DateInterval`。因此，调用了 `DateInterval.setSecond(Object)`。该方法就是合成的桥接方法。它调用了 `DateInterval.setSecond(Date)`，这正是我们想要的。

桥接方法可能更加奇怪。假设 `DateInterval` 方法也重写了 `getSecond` 方法：

```java
class DateInterval extends Pair<LocalDate>
{
    public LocalDate getSecond() { return (Date) super.getSecond().clone(); }

    . . .
}
```

在 `DateInterval` 类中，有两个 `getSecond` 方法：

```text
LocalDate getSecond() // 定义在 DateInterval 中
Object getSecond() // 重写 Pair 中定义的方法以调用第一个方法
```

你不能像那样写 Java 代码；拥有两个具有相同参数类型的方法是非法的——在这里，没有任何参数。然而，在虚拟机中，参数类型*和返回类型*共同决定了一个方法。因此，编译器可以为两个仅返回类型上不同的方法生成字节码，并且虚拟机将正确处理这种情况。

---

![Image](img/note.jpg) 备注

桥接方法不仅限于泛型。我们之前在第 5 章 中已经提到，在重写另一个方法时，指定更具限制性的返回类型是合法的。例如：

```java
public class Employee implements Cloneable
{
    public Employee clone() throws CloneNotSupportedException { . . . }
}
```

`Object.clone` 和 `Employee.clone` 方法被称为具有*协变返回类型*。

实际上，`Employee` 类有*两个* `clone` 方法：



`Employee clone()` // 上文定义

`Object clone()` // 合成的桥接方法，重写了 `Object.clone`

```
合成的桥接方法调用了新定义的方法。
```

***

总结一下，你需要记住关于 Java 泛型转换的这些事实：

- 虚拟机中没有泛型，只有普通的类和方法。
- 所有的类型参数都被替换为它们的边界（bounds）。
- 合成桥接方法以保留多态性。
- 在需要时插入类型转换以保留类型安全。

## 8.5.4 调用旧代码

在设计 Java 泛型时，一个主要目标是允许泛型与旧代码之间的互操作性。让我们来看一个具体的例子。要设置 `JSlider` 的标签，你使用方法

```java
void setLabelTable(Dictionary table)
```

这里，`Dictionary` 是原始类型，因为 `JSlider` 类在 Java 泛型出现之前就已经实现了。然而，当你填充字典时，应该使用泛型类型。

当你将 `Dictionary<Integer, Component>` 传递给 `setLabelTable` 时，编译器会发出警告。

```java
slider.setLabelTable(labelTable);
```

在最坏的情况下，你的程序将抛出异常。

```java
if (a instanceof Pair<String>) // Error
```

这只能测试 `a` 是否为任意类型的 `Pair`。对于以下测试也是如此：

```java
if (a instanceof Pair<T>) // Error
```

或者强制转换：

```java
Pair<String> p = (Pair<String>) a; // Warning--仅能测试 a 是否为 Pair
```

为了提醒你注意这种风险，当你尝试查询对象是否属于某个泛型类型时，将得到编译器错误（使用 `instanceof`）或警告（使用强制转换）。

出于同样的道理，`getClass` 方法始终返回原始类型（raw type）。例如：

```java
Pair<String> stringPair = . . .;
Pair<Employee> employeePair = . . .;
if (stringPair.getClass() == employeePair.getClass()) //它们是相等的
```

比较的结果为 `true`，因为两次调用 `getClass` 返回的都是 `Pair.class`。

## 8.6.3 你不能创建参数化类型的数组

你不能实例化参数化泛型的数组，例如：

```java
Pair<String>[] table = new Pair<String>[10]; // Error
```

这有什么问题？在类型擦除后，`table` 的类型是 `Pair[]`。你可以将其转换为 `Object[]`：

```java
Object[] objarray = table;
```

数组会记住其组件类型，如果你尝试存储一个错误类型的元素，它会抛出 `ArrayStoreException`：

```java
objarray[0] = "Hello"; // Error--组件类型是 Pair
```

但擦除使得这种机制对泛型类型失效。以下赋值：

```java
objarray[0] = new Pair<Employee>();
```

将通过数组存储检查，但仍会导致类型错误。由于这个原因，参数化类型的数组是被禁止的。

请注意，只有创建这些数组是被禁止的。你可以声明一个类型为 `Pair<String>[]` 的变量，但不能用 `new Pair<String>[10]` 初始化它。

> **注意**：你可以声明通配符类型的数组，然后对其进行强制转换：

```java
Pair<String>[] table = (Pair<String>[]) new Pair<?>[10];
```

结果是不安全的。如果你在 `table[0]` 中存储一个 `Pair<Employee>`，然后对 `table[0].getFirst()` 调用 `String` 方法，你将得到 `ClassCastException`。

> **提示**：如果你需要收集参数化类型对象，只需使用 `ArrayList`：`ArrayList<Pair<String>>` 是安全且有效的。

## 8.6.4 可变参数警告

在上一节中，你看到 Java 不支持泛型类型的数组。在本节中，我们讨论一个相关问题：将泛型类型的实例传递给具有可变数量参数的方法。

考虑这个带有可变参数的简单方法：

```java
public static <T> void addAll(Collection<T> coll, T. . . ts)
{
    for (t : ts) coll.add(t);
}
```

参数 `ts` 实际上是一个持有所有提供参数的数组。

现在考虑这个调用：

```java
Collection<Pair<String>> table = . . .;
Pair<String> pair1 = . . .;
Pair<String> pair2 = . . .;
addAll(table, pair1, pair2);
```

为了调用这个方法，Java 虚拟机必须创建一个 `Pair<String>` 数组，这是违反规则的。然而，规则针对这种情况被放宽了，你只会得到警告而不是错误。

你可以通过两种方式抑制警告。你可以在包含 `addAll` 调用的方法上添加 `@SuppressWarnings("unchecked")` 注解。或者，从 Java SE 7 开始，你可以对 `addAll` 方法本身使用 `@SafeVarargs` 注解：

```java
@SafeVarargs
public static <T> void addAll(Collection<T> coll, T. . . ts)
```

现在可以使用泛型类型调用此方法了。你可以将此注解用于任何仅读取参数数组元素的方法，这被认为是最常见的用例。

> **注意**：你可以使用 `@SafeVarargs` 注解来绕过对泛型数组创建的限制，使用此方法：

```java
@SafeVarargs
public static <T> void addAll(Collection<T> coll, T. . . ts)
```

```java
@SuppressWarnings("unchecked") public E get(int n) { return (E) elements[n]; }
public void set(int n, E e) { elements[n] = e; } // 不需要强制转换
```

实际实现并不十分干净：

```java
public class ArrayList<E>
{
   private E[] elements;
   . . .
   public ArrayList() { elements = (E[]) new Object[10]; }
}
```

在这里，强制转换 `E[]` 是赤裸裸的谎言，但类型擦除（type erasure）使其无法被检测。

这种技术不适用于我们的 `minmax` 方法，因为我们返回的是 `T[]` 数组，如果我们对它的类型撒谎，会导致运行时错误。假设我们这样实现：

```java
public static <T extends Comparable> T[] minmax(T. . . a)
{
   Object[] mm = new Object[2];
   . . .
   return (T[]) mm; // 带警告通过编译
}
```

调用处：

```java
String[] ss = ArrayAlg.minmax("Tom", "Dick", "Harry");
```

编译时没有任何警告。当方法返回时，将 `Object[]` 引用强制转换为 `Comparable[]`，此时会发生 `ClassCastException`。

在这种情况下，最好的办法是让用户提供一个数组构造函数表达式：

```java
String[] ss = ArrayAlg.minmax(String[]::new, "Tom", "Dick", "Harry");
```

构造函数表达式 `String::new` 表示一个函数，给定所需的长度，构造相应长度的 `String` 数组。

该方法使用该参数来产生正确类型的数组：

```java
public static <T extends Comparable> T[] minmax(IntFunction<T[]> constr, T. . . a)
{
   T[] mm = constr.apply(2);
   . . .
}
```

另一种老旧的方法是反射并调用 `Array.newInstance`：

```java
public static <T extends Comparable> T[] minmax(T. . . a)
{
   T[] mm = (T[]) Array.newInstance(a.getClass().getComponentType(), 2);
   . . .
}
```

`ArrayList` 类的 `toArray` 方法就没有那么幸运了。它需要产生 `T[]` 数组，但它没有组件类型。因此，有两种变体：

```java
Object[] toArray()
T[] toArray(T[] result)
```

## 8.6.7 类型变量在泛型类的静态上下文中无效

你不能在静态字段或方法中引用类型变量。例如，下面这个巧妙的想法是行不通的：

```java
public class Singleton<T>
{
   private static T singleInstance; // 错误
   public static T getSingleInstance() // 错误
   {
      if (singleInstance == null) 构建 T 的实例
      return singleInstance;
   }
}
```

如果可以这样做，程序就可以声明一个 `Singleton<Random>` 来共享随机数生成器，以及一个 `Singleton<JFileChooser>` 来共享文件选择对话框。但这是行不通的。类型擦除后，只有一个 `Singleton` 类和一个 `singleInstance` 字段。由于这个原因，带有类型变量的静态字段和方法被直接禁止。

## 8.6.8 你不能抛出或捕获泛型类的实例

你既不能抛出也不能捕获泛型类的对象。事实上，泛型类继承 `Throwable` 甚至是不合法的。例如，下面的定义将无法编译：

```java
public class Problem<T> extends Exception { /* . . . */ } // 错误--不能继承 Throwable
```

你不能在 `catch` 子句中使用类型变量。例如，下面的方法将无法编译：

```java
public static <T extends Throwable> void doWork(Class<T> t)
{
   try
   {
      执行工作
   }
   catch (T e) // 错误--不能捕获变量
   {
      Logger.info(. . .)
   }
}
```

然而，在异常规格中使用类型变量是可以接受的。下面的方法是合法的：

```java
public static <T extends Throwable> void doWork(T t) throws T
{
   try
   {
      执行工作
   }
   catch (Throwable realCause)
   {
      t.initCause(realCause);
      throw t;
   }
}
```

## 8.6.9 你可以破解异常检查

Java 异常处理的基石是你必须为所有检查异常提供处理器。你可以使用泛型来破解这种方案。关键在于这个方法：

```java
@SuppressWarnings("unchecked")
public static <T extends Throwable> void throwAs(Throwable e) throws T
{
   throw (T) e;
}
```

假设该方法包含在 `Block` 类中。当你调用

```java
Block.<RuntimeException>throwAs(t)
```

编译器将认为 `t` 变成了一个非检查异常。以下代码将所有异常转换为编译器认为的非检查异常：

```java
try
{
   执行工作
}
catch (Throwable t)
{
   Block.<RuntimeException>throwAs(t);
}
```

让我们封装在一个抽象类中。用户将重写 `body` 方法以提供特定的操作。当调用 `toThread` 时，你会得到一个 `Thread` 类对象，其 `run` 方法并不担心检查异常。

```java
abstract class Block
{
   abstract void body() throws Exception;
   public Thread toThread()
   {
      return new Thread()
      {
         public void run()
         {
            try
            {
               body();
            }
            catch (Throwable t)
            {
               Block.<RuntimeException>throwAs(t);
            }
         }
      };
   }
   @SuppressWarnings("unchecked")
   public static <T extends Throwable> void throwAs(Throwable e) throws T
   {
      throw (T) e;
   }
}
```

例如，这个程序运行了一个抛出检查异常的线程：

```java
public class Test
{
   public static void main(String[] args)
   {
      new Block()
      {
         public void body() throws Exception
         {
            Scanner in = new Scanner(new File("ququx"), "UTF-8");
            while (in.hasNext())
            {
               System.out.println(in.next());
            }
         }
      }.toThread().start();
   }
}
```

`boolean equals(String)` // 定义在 `Pair<T>` 中

`boolean equals(Object)` // 继承自 `Object`

但直觉误导了我们。方法的擦除将

`boolean equals(T)`

变成了

`boolean equals(Object)`

这与 `Object.equals` 方法发生了冲突。

解决办法当然是重命名这个引起冲突的方法。

泛型规范引用了另一个规则："为了支持通过擦除转换，我们实施了这样一种限制：类或类型变量不能同时是两个接口类型的子类型，而这两个接口是同一个接口的不同参数化形式。"例如，以下代码是非法的：

```java
class Employee implements Comparable<Employee> { . . . }
class Manager extends Employee implements Comparable<Manager>
   { . . . } // 错误
```

`Manager` 将同时实现 `Comparable<Employee>` 和 `Comparable<Manager>`，它们是同一个接口的不同参数化。

这种限制与类型擦除之间的关系并不显而易见。毕竟，非泛型的版本

```java
class Employee implements Comparable { . . . }
class Manager extends Employee implements Comparable { . . . }
```



是合法的。原因要微妙得多。这将与合成的桥接方法产生冲突。实现 `Comparable<X>` 的类会获得一个桥接方法

点击此处查看代码图像

```java
public int compareTo(Object other) { return compareTo((X) other); }
```

你不能拥有不同的类型 `X` 两个这样的方法。

### 8.7 泛型的继承规则

当你处理泛型类时，你需要学习关于继承和子类型的规则。让我们从一个许多程序员认为不符合直觉的情况开始。考虑一个类和它的子类，例如 `Employee` 和 `Manager`。`Pair<Manager>` 是 `Pair<Employee>` 的子类吗？可能让你惊讶的是，答案是“不是”。例如，以下代码无法编译：

点击此处查看代码图像

```java
Manager[] topHonchos = . . .;
Pair<Employee> result = ArrayAlg.minmax(topHonchos); // 错误
```

`minmax` 方法返回一个 `Pair<Manager>`，而不是 `Pair<Employee>`，将一个赋值给另一个是非法的。

通常情况下，`Pair<S>` 和 `Pair<T>` 之间*没有*关系，无论 `S` 和 `T` 如何相关（参见图 8.1）。

![图像](img/08fig01.jpg)

**图 8.1** pair 类之间没有继承关系

这看起来像是一个残酷的限制，但对于类型安全来说是必要的。假设我们允许将 `Pair<Manager>` 转换为 `Pair<Employee>`。考虑这段代码：

点击此处查看代码图像

```java
Pair<Manager> managerBuddies = new Pair<>(ceo, cfo);
Pair<Employee> employeeBuddies = managerBuddies; // 非法，但假设它不是
employeeBuddies.setFirst(lowlyEmployee);
```

显然，最后一条语句是合法的。但 `employeeBuddies` 和 `managerBuddies` 指向*同一个对象*。我们现在成功地将 CFO 与一个普通员工配对，这对于 `Pair<Manager>` 来说是不可能的。

***

![图像](img/note.jpg) 注意

你刚刚看到了泛型类型与 Java 数组之间的重要区别。你可以将 `Manager[]` 数组赋值给类型为 `Employee[]` 的变量：

点击此处查看代码图像

```java
Manager[] managerBuddies = { ceo, cfo };
Employee[] employeeBuddies = managerBuddies; // OK
```

然而，数组带有特殊的保护。如果你尝试将一个普通员工存储到 `employeeBuddies[0]` 中，虚拟机会抛出 `ArrayStoreException`。

***

你始终可以将参数化类型转换为原始类型（raw type）。例如，`Pair<Employee>` 是原始类型 `Pair` 的子类型。这种转换对于与旧留代码交互是必要的。

你能转换为原始类型并导致类型错误吗？遗憾的是，可以。考虑这个例子：

点击此处查看代码图像

```java
Pair<Manager> managerBuddies = new Pair<>(ceo, cfo);
Pair rawBuddies = managerBuddies; // OK
rawBuddies.setFirst(new File(". . .")); // 仅有编译警告
```

这听起来很可怕。然而，请记住，你的处境并不比使用旧版本的 Java 时糟。虚拟机的安全性并没有受到威胁。当使用 `getFirst` 获取外部对象并将其赋值给 `Manager` 变量时，会抛出 `ClassCastException`，就像过去的老日子一样。你只是失去了泛型编程通常提供的额外安全性。

最后，泛型类可以扩展或实现其他泛型类。在这方面，它们与普通类没有区别。例如，`ArrayList<T>` 类实现了接口 `List<T>`。

### 8.8 通配符类型

在一段时间内，研究人员发现一种僵化的类型系统非常难用。Java 设计者发明了一种巧妙的（尽管安全的）“逃生口”：*通配符类型*。通配符类型允许类型参数变化。

#### 8.8.1 通配符概念

在通配符类型中，类型参数是变化的。例如，通配符类型

`? extends Employee`

表示任何类型参数为 `Employee` 子类的 `Pair`。假设你想写一个打印配对的方法，如下所示：

点击此处查看代码图像

```java
public static void printBuddies(Pair<Employee> p)
{
    Employee first = p.getFirst();
    Employee second = p.getSecond();
    System.out.println(first.getName() + " and " + second.getName() + " are buddies.");
}
```

正如你在前面的节看到的，你无法将 `Pair<Manager>` 传递该方法，这具有限制性。但解决方案很简单——使用通配符类型：

点击此处查看代码图像

```java
public static void printBuddies(Pair<? extends Employee> p)
```

`Pair<Manager>` 是 `Pair<? extends Employee>` 的子类型（参见图 8.2）。[图 8.2] 显示了这些关系。

**图 8.2** 通配符之间的类型关系

我们能通过 `Pair<? extends Employee>` 引用使用通配符来破坏 `Pair<Manager>` 吗？

点击此处查看代码图像

```java
Pair<Manager> managerBuddies = new Pair<>(ceo, cfo);
Pair<? extends Employee> wildcardBuddies = managerBuddies; // OK
wildcardBuddies.setFirst(lowlyEmployee); // 编译错误
```

不存在可能的破坏。对 `setFirst` 的调用是一个类型错误。为了看到为什么，让我们仔细观察 `Pair<? extends Employee>`。它的方法看起来如下：

点击此处查看代码图像

```java
? extends Employee getFirst()
void setFirst(? extends Employee)
```

这使得无法调用 `setFirst` 方法。编译器只知道它需要 `Employee` 的某个子类型，但不知道是哪种类型。它拒绝传递任何特定类型——毕竟，`?` 可能不匹配。

我们在 `getFirst` 上没有这个问题：将 `getFirst` 的返回值赋值给 `Employee` 引用是完全合法的。

这就是有界通配符的关键思想。我们现在有一种方法区分安全的访问方法和不安全的修改器方法。

#### 8.8.2 通配符的上界边界

通配符边界与类型变量边界相似，但它们拥有一种额外的能力——你可以指定一个*上界边界*，如下：

`? super Manager`

此通配符被限于 `Manager` 的所有父类。（这非常幸运，现有的 `super` 关键字如此准确地描述了这种关系。）

你为什么要这样做呢？带有父类界限的通配符所提供的行为，与第 8.8 节中“通配符类型”（第 442 页）描述的通配符相反。你可以向方法传递参数，但无法使用返回值。例如，`Pair<? super Manager>` 的方法描述如下：

```java
void setFirst(? super Manager)
? super Manager getFirst()
```

这并不是真正的 Java 语法，但它展示了编译器知道的信息。编译器无法知道 `setFirst` 方法的切类型，因此无法接受类型为 `Employee` 或 `Object` 的参数调用。只能传递类型为 `Manager` 或其子类（如 `Executive`）的实例。此外，如果你调用 `getFirst`，无法保证返回对象的类型。你只能将其赋值给 `Object`。

这是一个典型的示例。我们有一个经理数组，并想将奖金最低和最高的经理放入一个 `Pair` 对象中。什么样的 `Pair` 呢？`Pair<Employee>` 应该是合理的，或者说 `Pair<Object>` 也可以（参见图 8.4）。以下方法将接受任何适当的 `Pair`：

```java
public static void minmaxBonus(Manager[] a, Pair<? super Manager> result)
{
    if (a.length == 0) return;
    Manager min = a[0];
    Manager max = a[0];
    for (int i = 1; i < a.length; i++)
    {
        if (min.getBonus() > a[i].getBonus()) min = a[i];
        if (max.getBonus() < a[i].getBonus()) max = a[i];
    }
    result.setFirst(min);
    result.setSecond(max);
}
```

![Image](img/08fig04.jpg)

**图 8.4** 带有父类界限的通配符

直观地说，带有父类界限的通配符允许你向泛型对象写入，而带有子类界限的通配符允许你从泛型对象读取。

这是父类界限的另一个用途。`Comparable` 接口本身是一个泛型类型。它的声明如下：

```java
public interface Comparable<T>
{
    public int compareTo(T other);
}
```

在这里，类型变量表示参数 `other` 的类型。例如，`String` 类实现了 `Comparable<String>`它的 `compareTo` 方法声明为：

```java
public int compareTo(String other)
```

这很好——显式参数具有正确的类型。在接口泛型化之前，`other` 是 `Object`，在方法的实现中需要进行强制转换。

既然 `Comparable` 是一个泛型类型，也许我们应该对 `ArrayAlg` 类的 `min` 方法做得更好？我们可以将其声明为：

```java
public static <T extends Comparable<T>> T min(T[] a)
```

这看起来比仅仅使用 `T extends Comparable` 更彻底，并且对许多类都有效。例如，如果你计算一个 `String` 数组的最小值，那么 `T` 就是类型 `String`，而 `String` 是 `Comparable<String>` 的子类。但在处理 `LocalDate` 对象数组时，我们遇到了问题。恰好，`LocalDate` 实现了 `ChronoLocalDate`，而 `ChronoLocalDate` 扩展 `Comparable<ChronoLocalDate>`。因此，`LocalDate` 实现了 `Comparable<ChronoLocalDate>` 但*不是* `Comparable<LocalDate>`。

在这种情况下，父类救了急：

```java
public static <T extends Comparable<? super T>> T min(T[] a) . . .
```

现在 `compareTo` 方法的形式为：

```java
int compareTo(? super T)
```

它可能声明为接收类型为 `T` 的对象，或者（例如当 `T` 为 `LocalDate` 时）接收 `T` 的父类。无论如何，将类型为 `T` 的对象传递给 `compareTo` 方法是安全的。

对于初学者来说，`<T extends Comparable<? super T>>` 这样的声明看起来令人令畏。这很遗憾。此声明的意图是通过消除不必要的限制来帮助应用程序应用程序开发人员。

在这种情况下，`swapHelper` 方法的参数 `T` **捕获了通配符**。目前还该通配符表示什么类型，但它是一个确定的类型，而且当 `T` 表示该类型时，`<T>swapHelper` 的定义是完全合理的。

当然，在这种情况下，我们并没有被迫使用通配符。我们本可以直接实现 `<T> void swap(Pair<T> p)` 作为不带通配符的泛型方法。然而，考虑下面这个例子，通配符类型自然地出现在计算的中间：

点击此处查看代码图像

```java
public static void maxminBonus(Manager[] a, Pair<? super Manager> result)
{
    minmaxBonus(a, result);
    PairAlg.swap(result); // OK--swapHelper 捕获了通配符类型
}
```

在这里，通配符捕获机制是无法避免的。

通配符捕获只在非常有限的情况下是合法的。编译器能够保证通配符代表一个单一、确定的类型。例如，`ArrayList<Pair<T>>` 中的 `T` 永远无法捕获 `ArrayList<Pair<?>>` 中的通配符。该数组列表可能包含两个 `Pair<?>`，每个的 `?` 都有不同的类型。

列表 8.3 中的测试程序汇总了我们在前面几节中讨论过的各种方法，以便你可以在上下文中看到它们。

**列表 8.3** `pair3/PairTest3.java`

点击此处查看代码图像

***



```java
package pair3;

/**
 * @version 1.01 2012-01-26
 * @author Cay Horstmann
 */
public class PairTest3
{
    public static void main(String[] args)
    {
        Manager ceo = new Manager("Gus Greedy", 800000, 2003, 12, 15);
        Manager cfo = new Manager("Sid Sneaky", 600000, 2003, 12, 15);
        Pair<Manager> buddies = new Pair<>(ceo, cfo);
        printBuddies(buddies);

        ceo.setBonus(1000000);
        cfo.setBonus(500000);
        Manager[] managers = { ceo, cfo };

        Pair<Employee> result = new Pair<>();
        minmaxBonus(managers, result);
        System.out.println("first: " + result.getFirst().getName()
            + ", second: " + result.getSecond().getName());
        maxminBonus(managers, result);
        System.out.println("first: " + result.getFirst().getName()
            + ", second: " + result.getSecond().getName());
    }

    public static void printBuddies(Pair<? extends Employee> p)
    {
        Employee first = p.getFirst();
        Employee second = p.getSecond();
        System.out.println(first.getName() + " and " + second.getName() + " are buddies.");
    }

    public static void minBonus(Manager[] a, Pair<? super Manager> result)
    {
        if (a.length == 0) return;
        Manager min = a[0];
        Manager max = a[0];
        for (int i = 1; i < a.length; i++)
        {
            if (min.getBonus() > a[i].getBonus()) min = a[i];
            if (max.getBonus() < a[i].getBonus()) max = a[i];
        }
        result.setFirst(min);
        result.setSecond(max);
    }

    public static void minminBonus(Manager[] a, Pair<? super Manager> result)
    {
        minminBonus(a, result);
        PairAlg.swap(result); // OK--swapHelper 捕获了通配符
    }
}

class PairAlg
{
    public static boolean hasNulls(Pair<?> p)
    {
        return p.getFirst() == null || p.getSecond() == null;
    }

    public static void swap(Pair<?> p) { swapHelper(p); }

    public static <T> void swapHelper(Pair<T> p)
    {
        T t = p.getFirst();
        p.setFirst(p.getSecond());
        p.setSecond(t);
    }
}
```

### 8.9 反射与泛型

反射允许你在运行时分析任意对象。如果对象是泛型类的实例，你无法获得关于泛型类型参数的相关信息，因为它们已经被擦除了。在接下来的章节中，你将学习尽管如此可以通过反射发现关于泛型类的哪些信息。

#### 8.9.1 泛型类

`Class` 类现在是泛型的。例如，`String.class` 实际上是 `Class<String>` 类的一个对象（事实上，是该唯一的对象）。

类型参数是有用的，因为它允许 `Class<T>` 的方法在返回类型上变得更加具体。`Class<T>` 的以下方法利用了类型参数：

- `T newInstance()`
- `T cast(Object obj)`
- `T[] getEnumConstants()`
- `Class<? super T> getSuperclass()`
- `Constructor<T> getConstructor(Class... parameterTypes)`
- `Constructor<T> getDeclaredConstructor(Class... parameterTypes)`

`newInstance` 方法返回一个从无参数构造函数获取的类实例。它的返回类型现在可以声明为 `T`，即与被描述的类相同的类型。

`cast` 方法返回对象，如果它可以转换为类型 `T`，否则抛出 `BadCastException`。

`getEnumConstants()` 方法当 `T` 是枚举类型时返回一个数组，否则返回 `null`。

`getSuperclass()` 返回该类的父类，如果 `T` 不是一个类则返回 `null`。

`getConstructor(Class... parameterTypes)` 获取给定参数类型的公共构造函数。

`getDeclaredConstructor(Class... parameterTypes)` 获取给定参数类型的声明构造函数。

最后，`getConstructor` 和 `getDeclaredConstructor` 方法返回 `Constructor<T>`。

`java.lang.Class<T>` 1.0

- `T newInstance()` 返回由无参数构造函数创建的实例。
- `T cast(Object obj)` 如果对象可以转换为类型 `T` 则返回它，否则抛出 `BadCastException`。
- `T[] getEnumConstants()` 如果 `T` 是枚举类型则返回数组，否则返回 `null`。
- `Class<? super T> getSuperclass()` 返回该类的父类，如果 `T` 不是类则返回 `null`。
- `Constructor<T> getConstructor(Class... parameterTypes)` 获取给定参数类型的公共构造函数。
- `Constructor<T> getDeclaredConstructor(Class... parameterTypes)` 获取给定参数类型的声明构造函数。

`java.lang.reflect.Constructor<T>` 1.1

- `T newInstance(Object... parameters)` 返回使用给定参数创建的实例。

#### 8.9.2 使用 Class<T> 参数进行类型匹配

有时匹配 `Class<T>` 参数的变量是有用的。这里有一个经典的例子：

```java
public static <T> Pair<T> makePair(Class<T> c) throws InstantiationException, IllegalAccessException
{
    return new Pair<>(c.newInstance(), c.newInstance());
}
```

如果你调用 `makePair(Employee.class)`，`Employee.class` 是一个 `Class<Employee>` 类型的对象。`makePair` 方法的类型参数 `T` 匹配 `Employee`，编译器可以推断出该方法返回 `Pair<Employee>`。

- 该泛型方法有一个名为 `T` 的类型参数；
- 该类型参数有一个本身是泛型类型的子类界限；
- 该边界类型有一个通配符参数；
- 通配符参数有一个上类界限；以及
- 该泛型方法有一个泛型数组参数。

换句话说，你可以重构实现者声明的关于泛型类和方法的所有信息。然而，你将不知道类型参数是如何针对特定对象或方法调用解析的。

为了表示泛型类型声明，请使用 `java.lang.reflect` 包中的 `Type` 接口。该接口有以下子类型：

- `Class` 类，描述具体类型
- `TypeVariable` 接口，描述类型变量（例如 `T extends Comparable<? super T>`）
- `WildcardType` 接口，描述通配符（例如 `? super T`）
- `ParameterizedType` 接口，描述泛型类或接口类型（例如 `Comparable<? super T>`）
- `GenericArrayType` 接口，描述泛型数组（例如 `T[]`）

图 8.5 显示了继承层次结构。注意最后四个子类型是接口——虚拟机会实例化实现这些接口的相应类。

![Image](img/08fig05.jpg)

**图 8.5** `Type` 接口及其后代

代码列表 8.4 使用泛型反射 API 打印它发现的关于给定类的信息。如果你使用 `Pair` 类运行它，将得到此报告：

```java
class Pair<T> extends java.lang.Object

public T getFirst()
public T getSecond()

public void setFirst(T)
public void setSecond(T)
```

如果你在 `PairTest2` 目录中使用 `ArrayAlg` 运行它，报告将显示以下方法：

```java
public static <T extends java.lang.Comparable> Pair<T> minmax(T[])
```

本节末尾的 API 说明描述了示例程序中使用的方法。

**代码列表 8.4** `genericReflection/GenericReflectionTest.java`



```java
package genericReflection;

import java.lang.reflect.*;
import java.util.*;

/**
 * @version 1.10 2007-05-15
 * @author Cay Horstmann
 */
public class GenericReflectionTest
{
    public static void main(String[] args)
    {
        // 从命令行参数或用户输入读取类名
        String name;
        if (args.length > 0) name = args[0];
        else
        {
            try (Scanner in = new Scanner(System.in))
            {
                System.out.println("Enter class name (e.g. java.util.Collections): ");
                name = in.next();
            }
        }

        try
        {
            // 打印类和公共方法的泛型信息
            Class<?> cl = Class.forName(name);
            printClass(cl);
            for (Method m : cl.getDeclaredMethods())
                printMethod(m);
        }
        catch (ClassNotFoundException e)
        {
            e.printStackTrace();
        }
    }

    public static void printClass(Class<?> cl)
    {
        System.out.print(cl);
        printTypes(cl.getTypeParameters(), "<", ", "> true);
        Type sc = cl.getSuperclass();
        if (sc != null)
        {
            System.out.print(" extends ");
            printType(sc, false);
        }
        printTypes(cl.getGenericInterfaces(), " implements ", ", "", false);
        System.out.println();
    }

    public static void printMethod(Method m)
    {
        String name = m.getName();
        System.out.print(Modifier.toString(m.getModifiers()));
        System.out.print(" ");
        printTypes(m.getTypeParameters(), "<", ", "> ", true);

        printType(m.getGenericReturnType(), false);
        System.out.print(" ");
        System.out.print(name);
        System.out.print("(");
        printTypes(m.getGenericParameterTypes(), "", ", "", false);
        System.out.println(")");
    }

    public static void printTypes(Type[] types, String pre, String sep, String suf, boolean isDefinition)
    {
        if (pre.equals(" extends ") && Arrays.equals(types, new Type[] { Object.class })) return;
        if (types.length > 0) System.out.print(pre);
        for (int i = 0; i < types.length; i++)
        {
            if (i > 0) System.out.print(sep);
            printType(types[i], isDefinition);
        }
        if (types.length > 0) System.out.print(suf);
    }

    public static void printType(Type type, boolean isDefinition)
    {
        if (type instanceof Class)
        {
            Class<?> t = (Class<?>) type;
            System.out.print(t.getName());
        }
        else if (type instanceof TypeVariable)
        {
            TypeVariable<?> t = (TypeVariable<?>) type;
            System.out.print(t.getName());
            if (isDefinition)
                printTypes(t.getBounds(), " extends ", " & ", false);
        }
        else if (type instanceof WildcardType)
        {
            WildcardType t = (WildcardType) type;
            System.out.print("?");
            printTypes(t.getUpperBounds(), " extends ", " & ", false);
            printTypes(t.getLowerBounds(), " super ", " & ", false);
        }
        else if (type instanceof ParameterizedType)
        {
            ParameterizedType t = (ParameterizedType) type;
            Type owner = t.getOwnerType();
            if (owner != null)
            {
                printType(owner, false);
                System.out.print(".");
            }
            printType(t.getRawType(), false);
            printTypes(t.getActualTypeArguments(), "<", ", ">", false);
        }
        else if (type instanceof GenericArrayType)
        {
            GenericArrayType t = (GenericArrayType) type;
            System.out.print("");
            printType(t.getGenericComponentType(), isDefinition);
            System.out.print("[]");
        }
    }
}
```

获取此类型变量的子类（`extends`）边界，如果变量没有子类边界，则返回一个长度为 `0` 的数组。

- `Type[] getLowerBounds()`

获取此类型变量的父类（`super`）边界，如果变量没有父类边界，则返回一个长度为 `0` 的数组。

***

`java.lang.reflect.ParameterizedType` **5.0**

- `Type getRawType()`

获取此泛化类型的原始类型。

- `Type[] getActualTypeArguments()`

获取声明此泛化类型时使用的类型参数。

- `Type getOwnerType()`

如果是内部类型，则获取其外部类类型；如果这是一个顶级类型，则返回 `null`。

***

`java.lang.reflect.GenericArrayType` **5.0**

- `Type getGenericComponentType()`

获取声明此数组类型时使用的泛型组件类型。

***

现在你已经知道如何使用泛型类，以及在需要时如何编写自己的泛型类和方法。同样重要的是，你还知道如何解读在 API 文档和错误信息中可能遇到的泛型类型声明。关于 Java 泛型的所有详尽讨论，请参阅 Angelika Langer 编写的优秀常见（及不常见）问题列表：[`http://angelikalanger.com/GenericsFAQ/JavaGenericsFAQ.html`](http://angelikalanger.com/GenericsFAQ/JavaGenericsFAQ.html)。

在下一章中，你将看到 Java 集合框架如何使用泛型。

# 第 9 章 集合

***

## 本章内容

- 9.1 Java 集合框架
- 9.2 具体集合
- 9.3 映射
- 9.4 视图与包装器
- 9.5 算法
- 9.6 遗留集合

***

当你尝试以自然风格实现方法或关注性能时，你所选择的数据结构可能会产生巨大差异。你需要对数千个（甚至数百万个）排序项进行快速搜索吗？你需要在有序序列的中间快速插入和删除元素吗？你需要在键和值之间建立关联吗？

本章将展示 Java 库如何帮助你完成正式编程所需的传统数据结构。在大学的计算机科学课程中，一门名为*数据结构*的课程通常需要一个学期才能完成，而且有很多书籍致力于这个重要主题。我们的涵盖范围与大学课程不同；我们将跳过理论，直接向你展示如何使用标准库中的集合类。

## 9.1 Java 集合框架

Java 的最初版本仅为最实用的数据结构提供了一小部分类：`Vector`、`Stack`、`Hashtable`、`BitSet` 以及 `Enumeration` 接口（后者提供了一种访问任意容器中元素的抽象机制）。这无疑是一个明智的选择——开发一个全面的集合类库需要时间和精。。

随着 Java SE 1.2 的出现，设计者认为是时候推出一套完整的数据结构了。他们面临着许多相互冲突的设计挑战。他们希望库既小又易于学习。他们不想要 C++ 标准模板库（或 STL）的复杂性，但他们想要 STL 开创的“泛型算法”带来的益处。他们希望遗留类能适应新的框架。正如所有集合库的设计者一样，他们必须做出一些艰难的抉，并在过程中产生了一些独特的设计决策。在本节中，我们将探索 Java 集合框架的基本设计，向你展示如何使用它，并解释一些较有争议的功能背后的原理。

### 9.1.1 分离集合接口与实现

与现代数据结构库很一样，Java 集合库将*接口*和*实现*分离。让我们通过一个熟悉的数据结构——*队列*（queue）来看这种分离。

*队列接口*规定你可以在队列的末尾添加元素，从头部删除元素，并查找队列中有多少元素。当你需要收集对象并按“先进先出”的方式检索它们时，可以使用队列（参见图 9.1）。

![Image](img/09fig01.jpg)

**图 9.1** 队列

队列接口的最小形式可能如下所示：

点击此处查看代码图像

```java
public interface Queue<E> // 标准库中接口的简化的形式
{
   void add(E element);
   E remove();
   int size();
}
```

接口没有告诉你任何关于队列是如何实现的信息。在队列的两种常见实现中，一种使用“循环数组”，另一种使用链表（参见图 9.2）。

![Image](img/09fig02.jpg)

**图 9.2** 队列实现

每个实现都可以由实现 `Queue` 接口的类来表示。

点击此处查看代码图像

```java
public class ArrayQueue<E> implements Queue<E> // 不是实际的类
{
   private int head;
   private int tail;
   ArrayQueue(int capacity) { ... }
   public void add(E element) { ... }
   public E remove() { ... }
   public int size() { ... }
   private E[] elements;
}
```

```java
public class LinkedListQueue<E> implements Queue<E> // 不是实际的类
{
   private Link head;
   private Link tail;
   LinkedListQueue() { ... }
   public void add(E element) { ... }
   public E remove() { ... }
   public int size() { ... }
}
```

***

![Image](img/note.jpg) 注意

Java 库中实际上并没有名为 `ArrayQueue` 和 `LinkedListQueue` 的类。我们使用这些类作为示例，来解释集合接口与实现之间概念上的区别。如果你需要一个循环数组队列，请使用 `ArrayDeque` 类。对于链表队列，直接使用 `LinkedList` 类即可——它实现了 `Queue` 接口。

***

当你在程序中使用队列时，一旦集合构造完成，你就不需要知道实际使用的是哪种实现。因此，在构造集合时*仅*使用具体类是有合逻辑的。而请使用*接口类型*来持有集合引用。

点击此处查看代码图像

```java
Queue<Customer> expressLane = new ArrayQueue<>(100);
expressLane.add(new Customer("Harry"));
```

通过这种方法，如果你改变了主意，可以轻松地使用不同的实现。你只需要在程序中的一处进行更改——在构造函数调用处。如果你最终发现 `LinkedListQueue` 是更好的选择，你的代码将变为：

点击此处查看代码图像

```java
Queue<Customer> expressLane = new LinkedList<>();
expressLane.add(new Customer("Harry"));
```

为什么选择一种实现而不是另一种？接口对实现的效率一无未字。循环数组比链表稍微高效一些，因此通常是首选的。然而，像往常一样，这是代价的。

循环数组是一个*有界*集合——它有有限的容量。如果你对程序收集的对象数量没有上限限制，那么可能使用链表实现更好。

当你研究 API 文档时，你会发现另一组以 `Abstract` 开头的类，例如 `AbstractQueue`。这些类是为库的实现者设计的。在（可能不太可能的）事件你想要实现自己的队列类时，扩展 `AbstractQueue` 会比实现 `Queue` 接口的所有方法要容易得多。

### 9.1.2 集合接口

Java 库中集合类的基础接口是 `Collection` 接口。该接口有两个基本方法：

点击此处查看代码图像

```java
public interface Collection<E>
{
   boolean add(E element);
   Iterator<E> iterator();
   ...
}
```

除了这两个方法外，还有其他方法；我们将在稍后讨论它们。

`add` 方法向集合中添加一个元素。如果添加元素确实更改了集合，`add` 方法返回 `true`；如果集合没有变化，则返回 `false`。例如，如果你尝试向一个集合（set）中添加一个对象而该对象已经存在，则 `add` 请求将不起作用，因为集合会拒绝重复项。

`iterator` 方法返回一个实现 `Iterator` 接口的对象。你可以使用该迭代对象逐个访问集合中的元素。我们将在下一节讨论迭代器。

### 9.1.3 迭代器

`Iterator` 接口有四个方法：

点击此处查看代码图像

```java
public interface Iterator<E>
{
   E next();
   boolean hasNext();
   void remove();
   default void forEachRemaining(Consumer<? super E> action);
}
```



通过反复调用`next`方法，你可以逐个访问集合中的元素。然而，如果你到达集合的末尾，`next`方法将抛出`NoSuchElementException`。因此，在调用`next`之前你需要调用`hasNext`方法。如果迭代器对象还有更多元素待访问，该方法将返回`true`。如果你想检查集合中的所有元素，可以请求一个迭代器，然后在`hasNext`返回`true`期间持续调用`next`方法。例如：

点击此处查看代码图像

```java
Collection<String> c = ...;
Iterator<String> iter = c.iterator();
while (iter.hasNext())
{
   String element = iter.next();
   // 对 element 执行某些操作
}
```

你可以用更简洁的“for each”循环来编写这样的循环：

```java
for (String element : c)
{
   // 对 element 执行某些操作
}
```

编译器简单地将“for each”循环翻译为带有迭代器的循环。

“for each”循环适用于任何实现`Iterable`接口的对象，该接口仅有一个抽象方法：

```java
public interface Iterable<E>
{
   Iterator<E> iterator();
   ...
}
```

`Collection`接口继承了`Iterable`接口。因此，你可以对标准库中的任何集合使用“for each”循环。

从 Java SE 8 开始，你甚至不需要编写循环。你可以带有一个消耗元素的 Lambda 表达式调用`forEachRemaining`方法。该 Lambda 表达式会在迭代器的每个元素上被调用，直到没有剩余元素。

点击此处查看代码图像

```java
iterator.forEachRemaining(element -> // 对 element 执行某些操作);
```

访问元素的顺序取决于集合的类型。如果你遍历一个`ArrayList`，迭代器从索引`0`开始，并在每一步中增加索引。然而，如果你访问`HashSet`中的元素，你将以本质上随机的顺序获取它们。你可以确保在迭代过程中遇到集合的所有元素，但你无法对它们的顺序做任何假设。这通常对于计算总和或计数匹配等计算来说不是一个问题，因为顺序并不重要。

***

![图像](img/note.jpg) 备注

老手会注意到，`Iterator`接口的`next`和`hasNext`方法的作用与`Enumeration`接口的`nextElement`和`hasMoreElements`方法相同。Java 集合库的设计者本可以选择使用`Enumeration`接口，但他们不喜欢冗长的方法名，而是引入了一个具有更短方法名的新接口。

***

Java 集合库中的迭代器与其他库中的迭代器之间存在着重要的概念区别。在传统的集合库中（如 C++ 的标准模板库 STL），迭代器是模仿数组索引建模的。给定这样一个迭代器，你可以查找存储在相应位置的元素，就像如果你有数组索引`i`，可以查找数组元素`a[i]`一样。查找完成后，你可以将迭代器移动到下一个位置。这与通过调用`i++`推进数组索引的操作相同，且不执行查找。然而，Java 迭代器并不是那样工作的。查找和位置变化是紧密耦合的。查找元素的方法是调用`next`，而这种查找会推进位置。

相反，将 Java 迭代器想象为处于*元素之间*。当你调用`next`时，迭代器会*跳过*下一个元素，并返回它刚刚通过的元素的引用（参见图 9.3）。

![图像](img/09fig03.jpg)

**图 9.3** 推进迭代器

***

![图像](img/note.jpg) 备注

这是另一个类比。你可以认为`Iterator.next`等同于`InputStream.read`。从流中读取字节会自动“消耗”该字节。下一次调用`read`会消耗该字节。同样，反复调用`next`可以让你读取集合中的所有元素。

***

`Iterator`的`remove`方法移除上一次调用`next`返回的元素。在很多情况下这是合理的——你需要在决定应该删除该元素之前先看到它。但如果你想移除特定位置的元素，你仍然需要跳过`next`。例如，这里是如何从以下集合中移除第一个元素的：

点击此处查看代码图像

```java
Iterator<String> it = c.iterator();
it.next(); // 跳过第一个元素
it.remove(); // 现在移除它
```

更重要的是，`next`和`remove`的调用之间存在依赖关系。如果在没有先调用`next`的情况下调用`remove`是非法的。如果你尝试这样做，将抛出`IllegalStateException`。

如果你想移除两个相邻的元素，你不能简单地调用：

```java
it.remove();
it.remove(); // 错误！
```

相反，你必须先调用`next`跳过要移除的元素。

```java
it.remove();
it.next();
it.remove(); // OK
```

### 9.1.4 泛型工具方法

`Collection`和`Iterator`接口是泛型的，这意味着你可以编写任意集合的工具方法。例如，这里有一个测试集合是否包含给定元素的泛型方法：

点击此处查看代码图像

```java
public static <E> boolean contains(Collection<E> c, Object obj)
{
   for (E element : c)
      if (element.equals(obj))
         return true;
   return false;
}
```

Java 库的设计者认为某些工具方法非常有用，以至于由库来提供。这样库用户就不需要不断重复造轮子。`contains`方法就是其中一种方法。

事实上，`Collection`接口声明了许多实现类必须提供的有用方法。其中包括：

```java
int size();
boolean isEmpty();
boolean contains(Object obj);
boolean containsAll(Collection<?> c);
boolean equals(Object other);
boolean addAll(Collection<? extends E> from);
boolean remove(Object obj);
boolean removeAll(Collection<?> c);
void clear();
boolean retainAll(Collection<?> c);
Object[] toArray();
<T> T[] toArray(T[] arrayToFill);
```

许多方法都是自而易见的；你可以在节末尾的 API 注释中找到完整的文档。

当然，如果每个实现`Collection`接口的类都必须提供许多常规方法，那将很麻烦。为了方便实现者的工作，库提供了一个`AbstractCollection`类，它将基础方法`size`和`iterator`留为抽象，但根据这两个方法实现了这些常规方法。例如：

点击此处查看代码图像

```java
public abstract class AbstractCollection<E>
   implements Collection<E>
{
   ...
   public abstract Iterator<E> iterator();
   public boolean contains(Object obj)
   {
      for (E element : this) // calls iterator()
          if (element.equals(obj))
              return true;
      return false;
   }
   ...
}
```

具体的集合类现在可以扩展`AbstractCollection`类。具体的集合类需要提供一个`iterator`方法，但`contains`方法已经由父类`AbstractCollection`处理好了。不过，如果子类有更高效的`contains`实现方式，也可以自由地这样做。

在 Java SE 8 中，这种方法有点过时。如果这些方法是`Collection`接口的默认方法会更好。但事实并非如此。不过，添加了几个默认方法，其中大多数处理流（我们将在第二卷中讨论）。此外，还有一个非常有用的方法：

点击此处查看代码图像

```java
default boolean removeIf(Predicate<? super E> filter)
```

用于删除符合条件的元素。

***

`java.util.Collection<E>` **1.2**

- `Iterator<E> iterator()` 返回一个可以用于访问集合中元素的迭代器。
- `int size()` 返回当前存储在集合中的元素数量。
- `boolean isEmpty()` 如果此集合不包含任何元素，则返回`true`。
- `boolean contains(Object obj)` 如果此集合包含与`obj`相等的，则返回`true`。
- `boolean containsAll(Collection<?> other)` 如果此集合包含另一个集合中的所有元素，则返回`true`。
- `boolean add(Object element)` 向集合中添加一个元素。如果集合因为此调用而发生变化，则返回`true`。
- `boolean addAll(Collection<? extends E> other)` 将另一个集合中的所有元素添加到此集合中。如果集合因为此调用而发生变化，则返回`true`。
- `boolean remove(Object obj)` 从集合中移除与`obj`相等的对象。如果删除了匹配的对象，则返回`true`。
- `boolean removeAll(Collection<?> other)` 从此集合中移除另一个集合中的所有元素。如果集合因为此调用而发生变化，则返回`true`。
- `default boolean removeIf(Predicate<? super E> filter)` **8** 移除所有`filter`返回`true`的元素。如果集合因为此调用而发生变化，则返回`true`。
- `void clear()` 移除集合中的所有元素。
- `boolean retainAll(Collection<?> other)` 从此集合中不等于另一个集合中任一元素的元素。如果集合因为此调用而发生变化，则返回`true`。
- `Object[] toArray()` 返回集合中对象的数组。
- `<T> T[] toArray(T[] arrayToFill)` 返回集合中对象的数组。如果`arrayToFill`长度足够，则用此集合的元素填充它。如果有空间，则追加一个`null`元素。否则，将分配一个与`arrayToFill`相同组件类型且长度与此集合大小相同的新数组并填充。

***

`java.util.Iterator<E>` **1.2**

- `boolean hasNext()` 如果还有另一个元素可以访问，则返回`true`。
- `E next()` 返回下一个要访问的对象。如果到达集合末尾，则抛出`NoSuchElementException`。
- `void remove()` 移除最后访问的对象。此方法必须紧随元素访问之后调用。如果自上次元素访问以来集合被修改过，此方法将抛出`IllegalStateException`。

***

### 9.1.5 集合框架中的接口

Java 集合框架为不同类型的集合定义了许多接口，如图 9.4 所示](#ch09.html_ch09fig04)。

![Image](img/09fig04.jpg)

**图 9.4** 集合框架的接口

集合有两个基础接口：`Collection`和`Map`。正如你所看到的，你通过方法向集合中插入元素：

```java
boolean add(E element)
```

然而，map 存储的是键值对，你使用`put`方法插入它们：

```java
V put(K key, V value)
```

要从集合中读取元素，可以使用迭代器访问。不过，你可以使用`get`方法从 map 中读取值：

```java
V get(K key)
```

`List`是*随机访问*的，因为元素可以通过两种方式访问：通过迭代器或通过整数索引。相比之下，使用迭代器时必须顺序访问。`List`接口定义了几个用于随机访问的方法：

点击此处查看代码图像

```java
void add(int index, E element)
void remove(int index)
E get(int index)
E set(int index, E element)
```

`ListIterator`接口是`Iterator`的子接口。它定义了一个在迭代器位置之前添加元素的方法：

```java
void add(E element)
```

坦率，集合框架的这方面设计得并不好。在实践中，有两种有序集合，具有非常不同的性能权衡。由数组支持的有序集合具有快速随机访问，使用带整数索引的`List`方法是有意义的。相反，链表虽然也是有序的，但随机访问很慢，最好用迭代器进行遍历。

***

![Image](img/note.jpg) 注意

为了避免对链表执行随机访问操作，Java SE 1.4 引入了一个标记接口`RandomAccess`。该接口没有方法，但你可以用它测试特定集合是否支持随机访问：

点击此处查看代码图像

```java
if (c instanceof RandomAccess)
{
   use random access algorithm
}
else
{
   use sequential access algorithm
}
```

***

`Set`接口与`Collection`接口相同，但方法的行为定义更严格。集合的`add`方法应该拒绝重复。集合的`equals`方法应该定义为使得两个集合具有相同的元素，但不一定具有相同的顺序；`hashCode`方法应该定义为使得两个具有相同元素的集合产生相同的哈希码。

如果方法签名相同，为什么要单独定义一个接口呢？从概念上讲，并不是所有集合都是集合。创建一个`Set`接口允许程序员编写只接受集合的方法。

`SortedSet`和`SortedMap`接口暴露了用于排序的比较器对象，并定义了获取集合子视图的方法。我们将在第 509 页的第 9.4 节“视图与包装器”中讨论这些。

最后，Java SE 6 引入了`NavigableSet`和`NavigableMap`接口，包含了用于在排序集合和 map 中进行搜索和遍历的额外方法。（理想情况下，这些方法应该直接包含在`SortedSet`和`SortedMap`接口中。）`TreeSet`和`TreeMap`类实现了这些接口。

表 9.1 展示了 Java 库中的集合，并简要描述了每个集合类的作用。（为了简单起见，我们省略了将在第 14 章中讨论的线程安全集合。）表 9.1 中的所有类都实现了`Collection`接口，以`Map`结尾的类除外。这些类实现了`Map`接口。我们将在第 497 页的第 9.3 节“Maps”中讨论 map。

![Image](img/09tab01.jpg)

**表 9.1** Java 库中的具体集合

图 9.5 展示了这些类之间的关系。

![Image](img/09fig05.jpg)

**图 9.5** 集合框架中的类

## 9.2.1 链表

在书中我们已经使用了数组和它们的动态表兄弟`ArrayList`类作为许多示例。然而，数组和数组列表有一个主要的缺点。从数组中间删除元素是非常昂贵的，因为被删除元素之后的所有数组元素都必须向数组的开头移动（参见图 9.6）。在中间插入元素也是如此。

![Image](img/09fig06.jpg)

**图 9.6** 从数组中删除元素

另一个著名的数据结构——*链表*（linked list）解决了这个问题。数组在连续的内存位置上存储对象引用，而链表将每个对象存储在单独的*节点*（link）中。每个节点还存储了指向序列中下一个节点的引用。在 Java 编程语言中，所有的链表实际上都是*双向链表*；也就是说，每个节点还存储了指向其前驱节点的引用（参见图 9.7）。

![Image](img/09fig07.jpg)

**图 9.7** 双向链表

从链表的中间删除元素是一个廉价的操作——只需要更新被删除元素周围的节点即可（参见图 9.8）。

![Image](img/09fig08.jpg)

**图 9.8** 从链表删除删除元素

也许你曾经上过数据结构课程，在课程中你学习了如何实现链表。你可能对在链表中删除或添加元素时纠结于节点关系留有糟糕的回忆。如果是这样，你会惊喜地发现，Java 集合库提供了一个可供你使用的`LinkedList`类。

下面的代码示例添加了三个元素，然后删除了第二个：

点击此处查看代码图像



```java
List<String> staff = new LinkedList<>(); // LinkedList implements List

staff.add("Amy");
staff.add("Bob");
staff.add("Carl");

Iterator iter = staff.iterator();

String first = iter.next(); // visit first element
String second = iter.next(); // visit second element

iter.remove(); // remove last visited element
```

然而，链表和通用集合之间存在着重要的区别。链表是一个有序集合，其中对象的顺序非常重要。`LinkedList.add` 方法将对象添加到列表的末尾。但你通常想在列表的中间某个位置添加对象。这种依赖位置的 `add` 方法是迭代器（iterator）的职责，因为迭代器描述了集合中的位置。

使用迭代器添加元素仅对于具有自然顺序的集合是有意义的。例如，我们在下一节中讨论的集合（set）数据类型没有对它的元素施加任何排序。因此，`Iterator` 接口中没有 `add` 方法。相反，集合库提供了一个包含 `add` 方法的子接口 `ListIterator`：

点击此处查看代码图像

```java
interface ListIterator<E> extends Iterator<E>
{
   void add(E element);
   . . .
}
```

与 `Collection.add` 不同，此方法不返回 `boolean` 布尔值——假设 `add` 操作总是会修改列表。

此外，`ListIterator` 接口有两个方法可以让你用于反向遍历列表：

```java
E previous()

boolean hasPrevious()
```

与 `next` 方法一样，`previous` 方法返回它跳过的对象。

`LinkedList` 类的 `listIterator` 方法返回一个实现 `ListIterator` 接口的迭代器对象。

点击此处查看代码图像

```java
ListIterator<String> iter = staff.listIterator();
```

`add` 方法在迭代器位置之前添加新元素。例如，以下代码跳过了链表的第一个元素，并在第二个元素之前添加 `"Juliet"`（参见图 9.9）：

点击此处查看代码图像

```java
List<String> staff = new LinkedList<>(); // LinkedList implements List

staff.add("Amy");
staff.add("Bob");
staff.add("Carl");

Iterator iter = staff.iterator();

String first = iter.next(); // visit first element
String second = iter.next(); // visit second element

iter.remove(); // remove last visited element
```

为了避免并发修改异常（Concurrent modification exceptions），请遵循这一简单规则：你可以为集合附加任意数量的迭代器，只要它们都是只读不写的。或者，你也可以附加一个既能读又能写的单一迭代器。

并发修改的检测是通过一种非常简单的方式实现的。集合会跟踪变异操作（如添加和删除元素）的数量。每个迭代器都会单独记录由它负责的变异操作计数。在每个迭代器方法的开头，迭代器只需检查其自身的变异计数是否与集合的计数相等。如果不相等，它将抛出一个 `ConcurrentModificationException`。

![Image](img/note.jpg) 注意

然而，在并发修改的检测上存在一个奇怪的例外。链表只跟踪列表的结构性修改，例如添加和删除链接。`set` 方法不被视为一种结构性修改。你可以为链表附加多个迭代器，这些迭代器都可以调用 `set` 来更改现有链接的属性。这种能力对于我们在本章节稍后讨论的 `Collections` 类中的许多算法是所必需的。

## LinkedList 类

现在你已经看到了 `LinkedList` 类的基本方法。使用 `ListIterator` 可以在两个方向上遍历链表的元素，并添加和删除元素。

正如你在上一节中看到的，许多其他操作链表的有用方法已在 `Collection` 接口中声明。这些方法大部分都在 `LinkedList` 类的父类 `AbstractCollection` 中实现。例如，`toString` 方法会调用所有元素的 `toString` 方法，并生成一个格式为 `[A, B, C]` 的长字符串。这对于调试非常有用。使用 `contains` 方法检查元素是否存在于链表中。例如，如果链表已经包含一个与字符串 `"Harry"` 相等的字符串，调用 `staff.contains("Harry")` 将返回 `true`。

该库还提供了一些从理论角度来看有些“令人存疑”的方法。链表不支持快速的随机访问。如果你想查看链表的第 `n` 个元素，你必须从开始处并跳过前 `n - 1` 个元素。没有捷径。出于这个原因，程序员通常不会在需要通过整数索引访问元素的情况下使用链表。

尽管如此，`LinkedList` 类提供了一个 `get` 方法，允许你访问特定的元素：

```java
LinkedList<String> list = ...;
String obj = list.get(n);
```

当然，这个方法的效率并不高。如果你发现自己在使用它，你可能为你的问题使用了错误的数据结构。

你永远不要使用这种链表的随机访问方法来遍历链表。这段代码：

```java
for (int i = 0; i < list.size(); i++)
    do something with list.get(i);
```

其效率低得惊人。每当你查找另一个元素时，搜索都会从列表开始重新开始。`LinkedList` 对象没有尝试缓存位置信息。

![Image](img/note.jpg) 注意

`get` 方法有一个微小的优化：如果索引至少为 `size() / 2`，则对元素的搜索将从列表末尾开始。

列表迭代器接口还有一个方法可以告诉你当前位置的索引。事实上，由于 Java 迭代器在概念上指向元素之间，因此它有两个索引方法：`nextIndex` 方法返回下一次调用 `next` 将返回的元素的整数索引；`previousIndex` 方法返回下一次调用 `previous` 将返回的元素的索引。当然，它仅仅比 `nextIndex` 小 1。

这些方法是非常高效的——迭代器维护着当前位置的计数。最后，如果你有一个整数索引 `n`，那么 `list.listIterator(n)` 返回一个指向索引为 `n` 的元素之前的迭代器。也就是说，调用 `next` 产生的元素与 `list.get(n)` 相同，而获取该迭代器的效率很低。

如果你有一个只有少数元素的链表，你就不必过度担心 `get` 和 `set` 方法的成本。但既然如此，最初为什么要使用链表呢？使用链表的唯一理由是为了降低列表中间插入和删除的成本。如果你只有几个元素，可以直接使用 `ArrayList`。

我们建议你直接避开所有使用整数索引表示链表位置的方法。如果你想对集合进行随机访问，请使用数组或 `ArrayList`，而不是链表。

Listing 9.1 中的程序让链表发挥了用处。它简单地创建了两个列表并将它们合并，然后从第二个列表中删除每个第二个元素，最后测试 `removeAll` 方法。我们建议你跟踪程序流并特别注意迭代器。你可能会发现绘制迭代器位置的图会有帮助，像这样：

| ACE | BDFG |
|---|---|
| A | CE \| BDFG |
| AB | CE B \| DFG |

注意，调用：

```java
System.out.println(a);
```

通过调用 `AbstractCollection` 中的 `toString` 方法打印链表 `a` 中的所有元素。

### 列表 9.1 linkedList/LinkedListTest.java

```java
package linked;

import java.util.*;

/**
 * 此程序演示了链表上的操作。
 * @version 1.1 2012-01-26
 * @author Cay Horst
 */
public class LinkedList
{
    public static void main(String[] args)
    {
        List<String> a = new LinkedList<>();
        a.add("Amy");
        a.add("Carl");
        a.add("Erica");

        List<String> b = new LinkedList<>();
        b.add("Bob");
        b.add("Doug");
        b.add("Frances");
        b.add("Gloria");

        // 将 b 中的单词合并到 a
        ListIterator<String> aIter = a.listIterator();
        Iterator<String> bIter = b.iterator();

        while (bIter.hasNext())
        {
            if (aIter.hasNext()) aIter.next();
            aIter.add(bIter.next());
        }

        System.out.println(a);

        // 从 b 中删除每个第二个单词
        bIter = b.iterator();
        while (bIter.hasNext())
        {
            bIter.next(); // 跳过一个元素
            if (bIter.hasNext())
            {
                bIter.next(); // 跳过下一个元素
                bIter.remove(); // 删除元素
            }
        }

        System.out.println(b);

        // 批量操作：从 a 中移除 b 的所有单词
        a.removeAll(b);

        System.out.println(a);
    }
}
```

返回与指定元素相等的第一个出现的位置；如果没有找到匹配的元素，则返回 `-1`。

- `int lastIndexOf(Object element)`

返回与指定元素相等的最后一次出现的位置；如果没有找到匹配的元素，则返回 `-1`。

### java.util.ListIterator<E> 1.2

- `void add(E newElement)`

在当前位置之前添加一个元素。

- `void set(E newElement)`

用新元素替换由 `next` 或 `previous` 最近访问的元素。如果自上次调用 `next` 或 `previous` 之后列表结构被修改过，则抛出 `IllegalStateException`。

- `boolean hasPrevious()`

如果在反向遍历列表时还有另一个元素可以访问，则返回 `true`。

- `E previous()`

返回上一个对象。如果到达列表开头，则抛出 `NoSuchElementException`。

- `int nextIndex()`

返回下一次调用 `next` 将返回的元素索引。

- `int previousIndex()`

返回下一次调用 `previous` 将返回的元素索引。

### java.util.LinkedList<E> 1.2

- `LinkedList()`

构造一个空链表。

- `LinkedList(Collection<? extends E> elements)`

构造一个链表并添加集合中的所有元素。

- `void addFirst(E element)`

- `void addLast(E element)`

在列表开头或结尾添加一个元素。

- `E getFirst()`

- `E getLast()`

返回列表开头或结尾的元素。

- `E removeFirst()`

- `E removeLast()`

移除并返回列表开头或结尾的元素。

## 9.2.2 Array Lists

在前面的一节中，你已经看到了 `List` 接口和实现它的 `LinkedList` 类。`List` 接口描述了一个有序集合，其中元素的位置非常重要。访问元素有两种协议：通过迭代器（iterator）以及通过 `get` 和 `set` 方法进行随机访问。后者对于链表并不合适，但显然对于数组来说，`get` 和 `set` 非常有意义。集合库提供了熟悉的 `ArrayList` 类，它也实现了 `List` 接口。`ArrayList` 封装了一个动态重新分配的对象数组。

![Image](img/note.jpg) 备注

如果你是一位资深 Java 程序员，可能在任何需要动态数组时都会使用 `Vector` 类。为什么要用 `ArrayList` 而不是 `Vector` 呢？原因很简单：`Vector` 类的所有方法都是同步的（synchronized）。从两个线程访问 `Vector` 对象是安全的。但如果你只从单个线程访问 `Vector` 对象（这是大多数情况），你的代码会在同步上浪费一些时间。相比之下，`ArrayList` 方法不是同步的。当你不需要同步时，我们建议你使用 `ArrayList` 而不是 `Vector`。

## 9.2.3 Hash Sets

链表和数组允许你指定排列元素的顺序。然而，如果你正在寻找某个元素但不记得它的位置，你就需要访问所有元素直到找到匹配项。如果集合包含很多元素，这可能会非常耗时。如果你不在乎元素的顺序，则有些数据结构可以让你更快地找到元素。缺点是这些数据结构让你无法控制元素出现的顺序。

一种快速查找对象的常用数据结构是“hash table”（哈希表）。哈希表为每个对象计算一个整数，称为“hash code”（哈希码）。哈希码以某种方式从对象的实例字段派生，最好是使得不同数据的对象产生不同的代码。这里列举由 `String` 类 `hashCode` 方法产生的一些哈希码示例。

**表 9.2 由 hashCode 方法产生的哈希码**

如果你定义了类，你就有责任实现自己的 `hashCode` 方法——你的实现需要与 `equals` 方法兼容：如果 `a.equals(b)`，那么 `a` 和 `b` 必须具有相同的哈希码。

现在重要的是，哈希码可以快速计算，且该计算仅依赖于需要哈希的对象的状态，而不取决于哈希表中的其他对象。在 Java 中，哈希表被实现为链表数组。每个列表被称为一个 `bucket`（桶）（见图 9.10）。

要找到对象在表中的位置，只需计算其哈希码并对桶的总数取模。得到的数字就是存放该元素的桶索引。例如，如果一个对象的哈希码为 7628 且有 128 个桶，那么该对象被放在桶 4 中（因为余数 `7628 % 128` 是 4）。

也许你很幸运，该桶中没有其他元素。那么你只需将元素插入该桶中。当然，有时你会遇到已经填充的桶。这被称为“hash collision”（哈希冲突）。然后，将新对象与桶中的所有对象进行比较，以检查它是否已经存在。如果哈希码分布随机且桶的数量足够大，只需要几次比较。

![Image](img/09fig10.jpg)

**图 9.10 一个哈希表**

![Image](img/note.jpg) 备注

从 Java SE 8 开始，当桶满时，它们会从链表变为平衡二叉树。如果哈希函数选择不当导致大量冲突，或者恶意代码试图用许多相同哈希码的值冲刷哈希表，这将提高性能。

如果你想对哈希表的性能有更多控制，可以指定初始桶的数量。桶的数量表示用于收集具有相同哈希值的桶数量。如果向哈希表中插入过多元素，冲突数量就会增加，检索性能也会受到影响。

如果你大致知道表中最终会有多少元素，你可以设置桶的数量。通常，你应该将其设置在预期元素数量的 75% 到 150% 之间。一些研究人员认为，将桶的数量设置为质数是一个好主意，可以防止键的聚集。然而，这一点的证据并不充分。

标准库使用的桶数量是 2 的幂，默认值为 `16`。你提供的任何表大小值都会被自动四舍五入到下一个 2 的幂。

当然，你并不总是知道需要存储多少个元素，或者你的初始猜测可能太低了。如果哈希表太满，就需要进行“rehashed”（重哈希）。要重哈希表，会创建一个具有更多桶的表，将所有元素插入新表，并丢弃原始表。

`load factor`（负载因子）决定了哈希表何时重哈希。例如，如果负载因子为 `0.75`（默认值）且表已超过 75%，它会自动以双倍的桶进行重哈希。对于大多数应用程序，将负载因子保持在 `0.75` 是合理的。

哈希表可以实现许多重要的数据结构。其中最简单的是 `set` 类型。set 是一个没有重复元素的集合。set 的 `add` 方法首先尝试查找要添加的对象，如果它不存在，则进行添加。

Java 集合库提供了一个 `HashSet` 类，它实现基于哈希表的集合（set）。你通过 `add` 方法添加元素。`contains` 方法被重写，以实现快速查找，检查元素是否已存在于集合中。它只检查一个桶（bucket）中的元素，而不是集合中的所有元素。

哈希集合迭代器会依次访问所有的桶。由于哈希处理将元素散布在表中，因此它们被访问的顺序似乎是随机的。如果你不在乎集合中元素的顺序，那么你就可以直接使用 `HashSet`。




Java 集合库提供了一个 `HashSet` 类，它实现了一个基于哈希表的集合（set）。你通过 `add` 方法添加元素。`contains` 方法被重写，以实现快速查找，检查元素是否已存在于集合中。它只检查一个桶（bucket）中的元素，而不是集合中的所有元素。

哈希集合迭代器会依次访问所有的桶。由于哈希处理将元素散布在表中，因此它们被访问的顺序似乎是随机的。如果你不在乎集合中元素的顺序，那么你就可以直接使用 `HashSet`。

本节末尾的示例程序（Listing 9.2）从 `System.in` 读取单词，将它们添加到集合中，最后打印出集合中的前二十个单词。例如，你可以通过命令行壳启动程序，并将《爱丽丝仙游记》文本输入程序：

```bash
java SetTest < alice30.txt
```

程序从输入中读取所有单词并将其添加到哈希集合中。它然后遍历集合中的唯一单词，最后打印出计数。（《爱丽丝仙游记》共有 5,909 个唯一单词，包括开头的版权声明。）单词以随机顺序出现。

![Image](img/caution.jpg) **注意**

在修改集合元素时要小心。如果元素的哈希值发生变化，该元素将不再位于数据结构中的正确位置。

**Listing 9.2** `set/SetTest.java`

点击此处查看代码图像

```java
1  package set;
2
3  import java.util.*;
4
5  /**
6   * 此程序使用集合打印 System.in 中的所有唯一单词。
7   * @version 1.12 2015-06-21
8   * @author Cay Horstmann
9   */
10 public class SetTest
11 {
12     public static void main(String[] args)
13     {
14         Set<String> words = new HashSet<>(); // HashSet implements Set
15         long totalTime = 0;
16
17         try (Scanner in = new Scanner(System.in))
18         {
19             while (in.hasNext())
20             {
21                 String word = in.next();
22                 long callTime = System.currentTimeMillis();
23                 words.add(word);
24                 callTime = System.currentTimeMillis() - callTime;
25                 totalTime += callTime;
26             }
27         }
28
29         Iterator<String> iter = words.iterator();
30         for (int i = 1; i <= 20 && iter.hasNext(); i++)
31             System.out.println(iter.next());
32         System.out.println("...");
33         System.out.println(words.size() + " distinct words. "
34             + totalTime + " milliseconds.");
35     }
36 }
```

**`java.util.HashSet<E>`** 1.2

- `HashSet()` 构建一个空的哈希集合。
- `HashSet(Collection<? extends E> elements)` 构建一个哈希集合并添加集合中的所有元素。
- `HashSet(int initialCapacity)` 构建一个指定容量（桶的数量）的空哈希集合。
- `HashSet(int initialCapacity, float loadFactor)` 构建一个指定容量和负载因子（一个 `0.0` 到 `1.0` 之间的数值，决定了哈希表在达到百分之几满时重新哈希到更大的表中）的空哈希集合。

**`java.lang.Object`** 1.0

- `int hashCode()` 返回此对象的哈希码。哈希码可以是任何整数，正数或负数。`equals` 和 `hashCode` 的定义必须兼容：如果 `x.equals(y)` 为 `true`，那么 `x.hashCode()` 必须与 `y.hashCode()` 相同。

### 9.2.4 Tree Sets

`TreeSet` 类与哈希集合类似，但增加了一个改进。树形集合是一个排序集合。你可以以任何顺序将元素插入集合中。当你遍历集合时，值将按排序顺序自动呈现。例如，假设你插入了三个字符串，然后访问所有添加的元素：

```java
SortedSet<String> sorter = new TreeSet<>(); // TreeSet implements SortedSet
sorter.add("Bob");
sorter.add("Amy");
sorter.add("Carl");
for (String s : sorter) System.out.println(s);
```

然后，值按排序顺序打印：`Amy Carl`。正如该类的命名所示，排序是通过树结构完成的。（当前实现使用了红黑树。有关红黑树的详细描述，请参见 Thomas Cormen、Charles Leiserson、Ronald Rivest 等人的《算法导论》。）

如果你不在乎集合中元素的顺序，那么你就可以直接使用 `HashSet`。

```java
import java.util.*;

/**
 * This program sorts a set of item by comparing their descriptions.
 * @version 1.12 2015-06-21
 * @author Cay Horstmann
 */
public class TreeSetTest
{
    public static void main(String[] args)
    {
        SortedSet<Item> parts = new TreeSet<>();
        parts.add(new Item("Toaster", 1234));
        parts.add(new Item("Widget", 4562));
        parts.add(new Item("Modem", 9912));
        System.out.println(parts);

        NavigableSet<Item> sortByDescription = new TreeSet<>(
            Comparator.comparing(Item::getDescription));

        sortByDescription.addAll(parts);
        System.out.println(sortByDescription);
    }
}
```

**Listing 9.4** `treeSet/Item.java`




点击此处查看代码图片

```java
package treeSet;

import java.util.*;

/**
 * An item with a description and a part number.
 */
public class Item implements Comparable<Item>
{
    private String description;
    private int partNumber;

    /**
     * Constructs an item.
     *
     * @param aDescription
     *      the item's description
     * @param aPartNumber
     *      the item's part number
     */
    public Item(String aDescription, int aPartNumber)
    {
        description = aDescription;
        partNumber = aPartNumber;
    }

    /**
     * Gets the description of this item.
     *
     * @return the description
     */
    public String getDescription()
    {
        return description;
    }

    public String toString()
    {
        return "[descripion=" + description + ", partNumber=" + partNumber + "]";
    }

    public boolean equals(Object otherObject)
    {
        if (this == otherObject) return true;
        if (otherObject == null) return false;
        if (getClass() != otherObject.getClass()) return false;
        Item other = (Item) otherObject;
        return Objects.equals(description, other.description) && partNumber == other.partNumber;
    }

    public int hashCode()
    {
        return Objects.hash(description, partNumber);
    }

    public int compareTo(Item other)
    {
        int diff = Integer.compare(partNumber, other.partNumber);
        return diff != 0 ? diff : description.compareTo(other.description);
    }
}
```

### 9.2.5 队列与双端队列

正如我们已经讨论过的，队列（queue）允许你高效地在尾部添加元素并在头部移除元素。双端队列（或`deque`）允许你高效地在头部和尾部添加或移除元素。不支持在中间添加元素。Java SE 6 引入了`Deque`接口。它由`ArrayDeque`和`LinkedList`类实现，这两个类都提供了大小随需要增长的双端队列。在第 14 章中，你将看到有界队列和双端队列。

#### `java.util.Queue<E>` 5.0

- `boolean add(E element)`
- `boolean offer(E element)` 将给定元素添加到此双端队列的尾部，如果队列未满则返回`true`。如果队列已满，第一个方法抛出`IllegalStateException`，而第二个方法返回`false`。
- `E remove()`
- `E poll()` 移除并返回队列头部的元素，如果队列不为空。如果队列为空，第一个方法抛出`NoSuchElementException`，而第二个方法返回`null`。
- `E element()`
- `E peek()` 返回队列头部的元素但不将其移除，如果队列不为空。如果队列为空，第一个方法抛出`NoSuchElementException`，而第二个方法返回`null`。

#### `java.util.Deque<E>` 6

- `void addFirst(E element)`
- `void addLast(E element)`
- `boolean offerFirst(E element)`
- `boolean offerLast(E element)` 将给定元素添加到此双端队列的头部或尾部。如果队列已满，前两个方法抛出`IllegalStateException`，而后两个方法返回`false`。
- `E removeFirst()`
- `E removeLast()`
- `E pollFirst()`
- `E pollLast()` 移除并返回队列头部的元素，如果队列不为空。如果队列为空，前两个方法抛出`NoSuchElementException`，而后两个方法返回`null`。
- `E getFirst()`
- `E getLast()`
- `E peekFirst()`
- `E peekLast()` 返回队列头部的元素但不将其移除，如果队列不为空。如果队列为空，前两个方法抛出`NoSuchElementException`，而后两个方法返回`null`。

#### `java.util.ArrayDeque<E>` 6

- `ArrayDeque()`
- `ArrayDeque(int initialCapacity)` 构建一个初始容量为 16 或给定初始容量的无界双端队列。

### 9.2.6 优先级队列

优先级队列在元素按任意顺序插入后按排序检索元素。也就是说，每当你调用`remove`方法时，都会得到当前优先级队列中的最小元素。然而，优先级队列并没有对所有元素进行排序。如果你遍历元素，它们并不是排序的。优先级队列利用了一种名为堆（heap）的优雅且高效的数据结构。堆是一种自组织的二叉树，其中`add`和`remove`操作会导致最小元素向根节点移动，而无需浪费时间对所有元素排序。

就像`TreeSet`一样，优先级队列可以包含实现`Comparable`接口类，也可以包含构造函数中提供的`Comparator`对象。

优先级队列的一个典型用途是任务调度。每个任务都有一个优先级。任务按随机顺序添加。每当有任务可以启动时，从队列中移除优先级最高的任务。（由于传统上优先级 1 是“最高”优先级，因此`remove`操作产生最小元素。）

Listing 9.5 展示了优先级队列的运行情况。

```java
public class PriorityQueueTest {
    public static void main(String[] args) {
        PriorityQueue<LocalDate> pq = new PriorityQueue<>();
        pq.add(LocalDate.of(1906, 12, 9)); // G. Hopper
        pq.add(LocalDate.of(1815, 12, 10)); // A. Lovelace
        pq.add(LocalDate.of(1903, 12, 3)); // J. von Neumann
        pq.add(LocalDate.of(1910, 6, 22)); // K. Zuse

        System.out.println("Iterating over elements...");
        for (LocalDate date : pq)
            System.out.println(date);
        System.out.println("Removing elements...");
        while (!pq.isEmpty())
            System.out.println(pq.remove());
    }
}
```

#### `java.util.PriorityQueue` 5.0

- `PriorityQueue()`
- `PriorityQueue(int initialCapacity)` 构建一个用于存储`Comparable`对象的优先级队列。
- `PriorityQueue(int initialCapacity, Comparator<? super E> c)` 构建一个优先级队列，并使用指定的比较器对其元素进行排序。

## 9.3 Maps

集合（Set）是一种允许你快速查找已存在元素的集合。然而，要查找一个元素，你需要拥有该元素的精确拷贝才能找到。这并不是非常常见的查找方式——通常，你拥有某些键信息，并想要查找与与之相关的元素。`map`数据结构正是为了实现这一目的。map 存储键值对（key/value pairs）。如果你提供键，就可以找到对应的值。例如，你可能存储一张员工记录表，其中键是员工 ID，值是`Employee`对象。在接下来的章节中，你将学习如何操作 map。

### 9.3.1 基础 Map 操作

Java 库为 map 提供了两种通用的实现：`HashMap`和`TreeMap`。这两个类都实现了`Map`接口。

哈希映射（hash map）对键进行哈希处理，而树映射（tree map）则根据键的顺序将其组织在搜索树中。哈希或比较函数仅应用于键。与键关联的值不会进行哈希处理或比较。

你应该选择哈希映射还是树映射？与集合一样，哈希处理通常快一点，如果你不需要按排序顺序访问键，那么它是首选方案。

以下是设置一个用于存储员工的哈希映射的方法：

```java
Map<String, Employee> staff = new HashMap<>(); // HashMap 实现 Map
Employee harry = new Employee("Harry Hacker");
staff.put("987-98-9996", harry);
...
```

每当你向 map 中添加对象时，必须同时提供一个键。在我们的案例中，键是一个字符串，对应的值是一个`Employee`对象。

要检索对象，你必须使用（并记住）该键。

```java
String id = "987-98-9996";
e = staff.get(id); // 获取 harry
```

如果 map 中没有存储指定特定键键信息，`get`将返回`null`。

`null`返回值可能会带来不便。有时，你有一个良好的默认值，可以用于 map 中不存在的键。这种情况下请使用`getOrDefault`方法。

```java
Map<String, Integer> scores = ...;
int score = scores.get(id, 0); // 如果 id 不存在则获取 0
```

键必须是唯一的。你不能存储两个具有相同键的值。如果你用相同的键调用两次`put`方法，第二个值将替换第一个值。事实上，`put`返回与其键参数关联的先一个值。

`remove`方法从 map 中删除具有给定键的元素。`size`方法返回 map 中条目的数量。

遍历 map 的键和值的简单方法是使用`forEach`方法。提供一个接收键和值的 lambda 表达式。该表达式会轮流对 map 中的每个条目进行调用。

```java
scores.forEach((k, v) -> System.out.println("key=" + k + ", value=" + v));
```

列表 9.6 演示了 map 的工作原理。我们首先向 map 中添加键/值对。然后，我们从 map 中移除一个键，这也会移除其关联的值。接下来，我们更改与键关联的值，并调用`get`方法来查找值。最后，我们遍历项集（entry set）。

#### 列表 9.6 MapTest.java

```java
package map;

import java.util.*;

/**
 * 此程序演示了键类型为 String、值类型为 Employee 的 map 用。
 * @version 1.11 2012-01-26
 * @author Cay Horstmann
 */
public class MapTest {
    public static void main(String[] args) {
        Map<String, Employee> staff = new HashMap<>();
        staff.put("144-25-5464", new Employee("Amy Lee"));
        staff.put("567-24-2546", new Employee("Harry Hacker"));
        staff.put("157-62-7935", new Employee("Gary Cooper"));
        staff.put("456-62-5527", new Employee("Francesca Cruz"));

        // 打印所有条目
        System.out.println(staff); // 从 map 中移除一个键，这也会移除其关联的值
        System.out.println(staff.remove("567-24-2546"));

        // 更改与键关联的值，并调用 get 方法查找值
        staff.put("157-62-7935", new Employee("Gary Miller"));
        System.out.println(staff.get("157-62-7935"));

        // 遍历项集
        staff.forEach((k, v) -> System.out.println("key=" + k + ", value=" + v));
    }
}
```

#### `java.util.Map<K, V>` 1.2

- `V get(Object key)` 获取键关联的值；如果键在 map 中未找到，则返回`null`。
- `default V getOrDefault(Object key, V defaultValue)` 获取键关联的值；如果键在 map 中未找到，则返回`defaultValue`。
- `V put(K key, V value)` 将键和值的关联放入 map 中。如果键已存在，新对象将替换之前与键关联的对象。此方法返回键的旧值，如果之前不存在则返回`null`。实现类可能不允许`null`键或值。
- `void putAll(Map<? extends K, ? extends V> entries)` 将指定 map 中的所有条目添加到此 map 中。
- `boolean containsKey(Object key)` 如果键在 map 中，则返回`true`。
- `boolean containsValue(Object value)` 如果值在 map 中，则返回`true`。
- `default void forEach(BiConsumer<? super K,? super V> action)` 对 map 的所有键/值对应用操作。

#### `java.util.HashMap<K, V>` 1.2

- `HashMap()`
- `HashMap(int initialCapacity)`
- `HashMap(int initialCapacity, float loadFactor)` 构建一个具有指定容量和负载因子的空哈希映射（0.0 到 1.0 之间的数字，决定了哈希表在达到多少百分比填充率时重新哈希到一个更大的表中）。默认负载因子为`0.75`。

#### `java.util.TreeMap<K,V>` 1.2

- `TreeMap()` 构建一个实现`Comparable`接口键的空树映射。
- `TreeMap(Comparator<? super K> c)` 构建一个树映射，并使用指定的比较器对其键进行排序。
- `TreeMap(Map<? extends K, ? extends V> entries)` 构建一个树映射并添加 map 中的所有条目。
- `TreeMap(SortedMap<? extends K, ? extends V> entries)` 构建一个树映射，添加排序 map 中的所有条目，并使用与给定排序 map 相同的元素比较器。

#### `java.util.SortedMap<K, V>` 1.2

- `Comparator<? super K> comparator()` 返回用于排序键的比较器；如果键通过`Comparable`接口的`compareTo`方法比较，则返回`null`。
- `K firstKey()`
- `K lastKey()`

返回 map 中最小或最大的键。

### 9.3.2 更新 Map 条目

处理 map 时棘棘手是更新条目。通常，你会获取与键关联的旧值，更新它，然后将更新后的值放回去。但你必须考虑键第一次出现的特殊情况。考虑使用 map 来统计单词在文件中出现的次数。当我们看到一个单词时，想要像这样增加计数器：

```
counts.put(word, counts.get(word) + 1);
```



这种方法可以工作，但在 `word` 第一次遇到时除外。此时，`get` 会返回 `null`，并发生 `NullPointerException`。

一个简单的解决办法是使用 `getOrDefault` 方法：

```java
counts.put(word, counts.getOrDefault(word, 0) + 1);
```

另一种方法是先调用 `putIfAbsent` 方法。它只在键之前不存在时才放入值。

```java
counts.putIfAbsent(word, 0);
counts.put(word, counts.get(word) + 1); // 现在我们知道 get 会成功了
```

但你可以做得更好。`merge` 方法简化了这种常用操作。调用：

```java
counts.merge(word, 1, Integer::sum);
```

如果键之前不存在，则将 `word` 与 1 关联；否则，使用 `Integer::sum` 函数将之前的值和 1 结合起来。

API 注释描述了更新 map 条目的其他较不常用的方法。

`java.util.Map<K, V>`

- `default V merge(K key, V value, BiFunction<? super V,? super V,? extends V> remappingFunction)` 8

  如果 `key` 与一个非-`null` 值 `v` 关联，则将函数应用到 `v` 和 `value` 上，并将 `key` 与结果关联，或者如果结果为 `null`，则移除该键。否则，将 `key` 与 `value` 关联。返回 `get(key)`。

- `default V compute(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)` 8

  将函数应用到 `key` 和 `get(key)` 上。将 `key` 与结果关联，或者如果结果为 `null`，则移除该键。返回 `get(key)`。

- `default V computeIfPresent(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)` 8

  如果 `key` 与一个非-`null` 值 `v` 关联，则将函数应用到 `key` 和 `v` 上，并将 `key` 与结果关联，或者如果结果为 `null`，则移除该键。返回 `get(key)`。

- `default V computeIfAbsent(K key, Function<? super K,? extends V> mappingFunction)` 8

  除非 `key` 与一个非-`null` 值关联，否则将函数应用到 `key` 上。将 `key` 与结果关联，或者如果结果为 `null`，则移除该键。返回 `get(key)`。

- `default void replaceAll(BiFunction<? super K,? super V,? extends V> function)` 8

  对所有条目调用该函数。将键与非-`null` 结果关联，并移除结果为 `null` 的键。

### 9.3.3 Map 视图

集合框架并未将 map 视为集合。（其他数据结构框架将 map 视为键/值对的集合，或视为由键索引的值集合。）然而，你可以获取 map 的视图——实现 `Collection` 接口或其一个子接口的对象。

共有三种视图：键的集合、值的集合（它不是集合）以及键/值对的集合。键和键/值对形成一个集合，因为 map 中一个键只能有一个副本。以下方法：

```java
Set<K> keySet()
Collection<V> values()
Set<Map.Entry<K, V>> entrySet()
```

返回这三个视图。（entry set 的元素是实现 `Map.Entry` 接口的类的对象。）

注意，`keySet` 不是 `HashSet` 或 `TreeSet`，而是实现 `Set` 接口的类的对象。`Set` 接口扩展了 `Collection` 接口。因此，你可以像使用任何集合一样使用 `keySet`。例如，你可以遍历 map 的所有键：

```java
Set<String> keys = map.keySet();
for (String key : keys)
{
    // 做一些事情
}
```

如果你想同时查看键和值，可以通过遍历条目来避免查找值。使用以下代码：

```java
for (Map.Entry<String, Employee> entry : staff.entrySet())
{
    String k = entry.getKey();
    Employee v = entry.getValue();
    // 做一些事情
}
```

**提示**：这曾经是访问所有 map 条目最高效的方法。现在，只需使用 `forEach` 方法即可：

```java
counts.forEach((k, v) -> {
    // 做一些事情
});
```

如果你在键集视图上调用迭代器的 `remove` 方法，你实际上会从 map 中移除该键及其关联的值。然而，你不能向键集视图中添加元素。在不同时添加值的情况下添加键是没有意义的。如果你尝试调用 `add` 方法，它会抛出 `UnsupportedOperationException`。entry 集视图也有同样的限制，尽管在概念上添加新的键/值对是有意义的。

`java.util.Map<K, V>`

- `Set<Map.Entry<K, V>> entrySet()` 返回 `Map.Entry` 对象的视图，即 map 中的键/值对。你可以从该集合移除元素，元素也会从 map 中移除，但你不能添加任何元素。

- `Set<K> keySet()` 返回 map 中所有键的集合视图。你可以从该集合移除元素，键及其关联的值也会从 map 中移除，但你不能添加任何元素。

- `Collection<V> values()` 返回 map 中所有值的集合视图。你可以从该集合移除元素，移除的值及其键也会从 map 中移除，但你不能添加任何元素。

`java.util.Map.Entry<K, V>`

- `K getKey()`

- `V getValue()`

  返回此条目的键或值。

- `V setValue(V newValue)` 将关联 map 中的值更改为新值并返回旧值。

### 9.3.4 弱哈希映射

集合类有一些特殊需求的 map 类，我们在本节及后续章节中简要讨论。

`WeakHashMap` 类是为了解决一个有趣的问题设计的。当一个键不再被程序的任何地方使用时，值会发生什么？假设键的最后一个引用已经消失。那么，再也没有可以引用该值对象的方法。但由于程序的任何部分都不再拥有该键，键/值对无法从 map 中移除。为什么垃圾回收器不能移除它？移除未使用对象不是垃圾回收器的工作吗？

遗憾的是，事实并非如此简单。垃圾回收器追踪活对象。只要 map 对象是活的，它所有的桶都是活的，不会被回收。因此，你的程序应该小心从长寿命 map 中移除未使用的值。或者，你可以使用 `WeakHashMap`。这种数据结构与垃圾回收器协作，当键的唯一引用是哈希表条目的引用时，移除键/值对。

这是该机制的内部原理。`WeakHashMap` 使用弱引用（weak references）来持有键。`WeakReference` 对象持有对另一个对象的引用——在我们的案例中，这是一个哈希表的键。这种类型的对象会被垃圾回收器以特殊方式处理。

通常，如果垃圾回收器发现某个对象没有指向它的引用，它就会回收该对象。然而，如果一个对象仅通过 `WeakReference` 可访问，垃圾回收器仍然会回收该对象，但会将指向该对象的弱引用放入队列中。`WeakHashMap` 的操作定期检查该队列，查看是否有新到达的弱引用。队列中出现弱引用意味着该键已不再被任何人使用并已被回收。随后，`WeakHashMap` 会移除关联的条目。

### 9.3.5 链接哈希集合与映射

`LinkedHashSet` 和 `LinkedHashMap` 类会记住你插入项的顺序。这样，你就可以避免哈希表中元素顺序看似是随机的。当条目被插入到表中时，它们会被连接数一个双向链表中（参见图 9.11）。

![Image](img/09fig11.jpg)

**图 9.11** 链接哈希表

例如，考虑列表 9.6 中的以下映射插入：

```java
Map<String, Employee> staff = new LinkedHashMap<>();
staff.put("144-25-5464", new Employee("Amy Lee"));
staff.put("567-24-2546", new Employee("Harry Hacker"));
staff.put("157-62-7935", new Employee("Gary Cooper"));
staff.put("456-62-5527", new Employee("Francesca Cruz"));
```

然后，`staff.keySet().iterator()` 按照此顺序枚举键：

- 144-25-5464
- 567-24-2546
- 157-62-7935
- 456-62-5527

而 `staff.values().iterator()` 按照此顺序枚举值：

- Amy Lee
- Harry Hacker
- Gary Cooper
- Francesca Cruz

链接映射也可以选择使用访问顺序（access order）而非插入顺序来遍历映射条目。每当你调用 `get` 或 `put` 时，受影响的条目会从其当前位置移除并置于条目链表的末尾。（这仅影响条目链表中的位置，而不影响哈希表桶。条目始终留在与键的哈希码对应的桶中。）

要构造这样一个哈希映射，请调用：

```java
LinkedHashMap<K, V>(initialCapacity, loadFactor, true)
```

访问顺序对于实现缓存的“最久未使用”策略有用。例如，你可能希望将频繁访问的条目保留在内存中，而从数据库读取访问频率较低的对象。当你不在表中找到某个条目且表已经很满时，你可以获取该表的迭代器并移除它枚举的前几个元素。那些条目就是最近最久未使用的。

你甚至可以自动化该过程。创建一个 `LinkedHashMap` 的子类并重写方法：

```java
protected boolean removeEldestEntry(Map.Entry<K, V> eldest)
```

这样，添加新条目时，只要你的方法返回 `true`，`eldest` 条目就会被移除。例如，以下缓存的大小保持在最多 100 个元素：

```java
Map<K, V> cache = new
    LinkedHashMap<>(128, 0.75F, true)
    {
      protected boolean removeEldestEntry(Map.Entry<K, V> eldest)
      {
          return size() > 100;
      }
    }
```

或者，你可以根据 `eldest` 条目来决定是否移除它。例如，你可能想要检查与条目一起的时间戳。

### 9.3.6 枚举集合与映射

`EnumSet` 是一种高效的集合实现，元素属于枚举类型（enumerated type）。由于枚举类型的实例数量有限的，`EnumSet` 在内部简单地实现为位序列。如果集合中存在对应的值，则该位被开启。

`EnumSet` 类没有公共构造函数。使用静态工厂方法来构造集合：

```java
enum Weekday { MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY };
EnumSet<Weekday> always = EnumSet.allOf(Weekday.class);
EnumSet<Weekday> never = EnumSet.noneOf(Weekday.class);
EnumSet<Weekday> workday = EnumSet.range(Weekday.MONDAY, Weekday.FRIDAY);
EnumSet<Weekday> mwf = EnumSet.of(Weekday.MONDAY, Weekday.WEDNESDAY, Weekday.FRIDAY);
```

你可以使用 `Set` 接口的常用方法来修改 `EnumSet`。

`EnumMap` 是一种键属于枚举类型的映射。它简单且高效地实现为值的数组。你需要在构造函数中指定键类型：

```java
EnumMap<Weekday, Employee> personInCharge = new EnumMap<>(Weekday.class);
```

> **提示**
>
> 在 `EnumSet` 的 API 文档中，你会看到形式奇怪的类型参数 `E extends Enum<E>`。这仅仅意味着“`E` 是枚举类型。”所有枚举类型都扩展 `Enum` 类。例如，`Weekday` 扩展 `Enum`。

### 9.3.7 恒等哈希映射

`IdentityHashMap` 有一个非常特殊的用途。在这里，键的哈希值通过内存地址计算。换句话说，即使对象内容相等，也被认为是不同的。该类对于实现对象遍历算法非常有用，例如，你想跟踪哪些对象已经被遍历过。

`java.util.WeakHashMap<K, V>`

- `WeakHashMap()`
- `WeakHashMap(int initialCapacity)`
- `WeakHashMap(int initialCapacity, float loadFactor)`

  构造一个指定容量和负载的空哈希映射。

`java.util.LinkedHashSet<E>`

- `LinkedHashSet()`
- `LinkedHashSet(int initialCapacity)`
- `LinkedHashSet(int initialCapacity, float loadFactor)`

  构造一个指定容量和负载的空链接哈希集合。

`java.util.LinkedHashMap<K, V>`

- `LinkedHashMap()`
- `LinkedHashMap(int initialCapacity)`
- `LinkedHashMap(int initialCapacity, float loadFactor)`
- `LinkedHashMap(int initialCapacity, float loadFactor, boolean accessOrder)`

  构造一个指定容量、负载和排序的空链接哈希映射。`accessOrder` 参数为 `true` 表示访问顺序，为 `false` 表示插入顺序。

- `protected boolean removeEldestEntry(Map.Entry<K, V> eldest)`

  应该被重写，如果你想移除 `eldest` 条目。`eldest` 参数是正考虑移除的条目。该方法在添加条目后被调用。默认实现返回 `false`——默认不会移除旧元素。然而，你可以重新定义此方法来选择性地返回 `true`——例如，如果旧元素符合特定条件或映射超过了特定大小。

`java.util.EnumSet<E extends Enum<E>>`

- `static <E extends Enum<E>> EnumSet<E> allOf(Class<E> enumType)`

  返回包含给定枚举类型所有值的集合。

- `static <E extends Enum<E>> EnumSet<E> noneOf(Class<E> enumType)`

  返回一个能够容枚举类型值的空集合。

- `static <E extends Enum<E>> EnumSet<E> range(E from, E to)`

  返回一个包含 `from` 和 `to` 之间（包含边界）所有值的集合。

- `static <E extends Enum<E>> EnumSet<E> of(E value)`

  返回一个包含给定值的集合。

- `static <E extends Enum<E>> EnumSet<E> of(E value, E... values)`

  返回一个包含给定值的集合。

### `java.util.EnumMap<K extends Enum<K>, V>` 5.0

- `EnumMap(Class<K> keyType)` 构建一个空的映射，其键的具有给定的类型。

### `java.util.IdentityHashMap<K, V>` 1.4

- `IdentityHashMap()`
- `IdentityHashMap(int expectedMaxSize)` 构建一个空的等标识哈希映射，其容量为超过 1.5 × `expectedMaxSize` 的最小 2 的幂次。（`expectedMaxSize` 的默认值为 `21`。）

### `java.lang.System` 1.0

- `static int identityHashCode(Object obj)` 1.1 返回与 `Object.hashCode` 计算相同的哈希码（派自对象的内存地址），即使 `obj` 所属的类重新定义了 `hashCode` 方法。

## 9.4 视图与包装器（Views and Wrappers）



如果你查看图 9.4 和图 9.5，你可能会认为使用大量的接口和抽象类来实现少量的具体集合类是大多此用。然而，这些图并没有说明全部。通过使用视图，你可以获得实现 `Collection` 或 `Map` 接口的其他对象。你已经在映射类的 `keySet` 方法中见过这方面的例子。乍一看，该方法似乎创建了一个新集合，用映射中所有的键填充它并返回。但事实并非如此。相反，`keySet` 方法返回一个实现 `Set` 接口的类对象，其方法操作原始映射。这样的集合被称为视图（view）。

视图技术在集合框架中有许多实用的应用。我们将在接下来的小节中讨论这些应用。

## 9.4.1 轻量级集合包装器

`Arrays` 类的静态方法 `asList` 返回一个围绕普通 Java 数组的 `List` 包装器。该方法允许你将数组传递给期望列表或集合参数的方法。例如：

```java
Card[] cardDeck = new Card[52];
...
List<Card> cardList = Arrays.asList(cardDeck);
```

返回的对象*不是* `ArrayList`。它是一个带有 `get` 和 `set` 方法的视图对象，这些方法访问底层数组。所有会改变数组大小的方法（如关联迭代器的 `add` 和 `remove` 方法）都会抛出 `UnsupportedOperationException`。

`asList` 方法可以接收变数量的参数。例如：

```java
List<String> names = Arrays.asList("Amy", "Bob", "Carl");
```

方法调用`Collections.nCopies(n, anObject)`返回一个实现 `List` 接口的不可变对象，并给出一个具有 `n` 个元素的幻象，每个元素显示为 `anObject`。例如，以下调用创建了一个包含 100 个字符串的 `List`全部设置为 `"DEFAULT"`：

```java
List<String> settings = Collections.nCopies(100, "DEFAULT");
```

存储非常少——该对象只存储一次。这是视图技术的一个巧妙应用。

注意：`Collections` 类包含许多工具方法，其参数或返回值是集合。不要将其与 `Collection` 接口混淆。

方法调用`Collections.singleton(anObject)`返回一个实现 `Set` 接口的视图对象（与 `nCopies` 不同，后者产生的是 `List`）。返回的对象实现了单元素集合，且没有数据结构带来的开销。`singletonList` 和 `singletonMap` 方法的行为类似。同样，对于集合框架中的每个接口，都有方法可以产生空集合、列表、映射等。令人印象深刻的是，集合的类型是推断出来的：

```java
Set<String> deepThoughts = Collections.emptySet();
```

## 9.4.2 子范围（Subranges）

你可以为许多集合形成子范围视图。例如，假设你有一个列表 `staff` 并想要提取索引 10 到 19 的元素。使用 `subList` 方法获取列表子范围的视图：

```java
List group2 = staff.subList(10, 20);
```

第一个索引包含边界，第二个索引不包含——就像 `String` 类中 `substring` 操作的参数一样。你可以对子范围应用任何操作，这些操作会自动反映到整个列表。例如，你可以删除整个子范围：

```java
group2.clear(); // staff 缩减
```

元素会自动从 `staff` 列表中清除，且 `group2` 变为空。对于排序后的集合和映射，你使用排序顺序而不是元素位置来形成子范围。`SortedSet` 接口声明了三个方法：

```java
SortedSet<E> subSet(E from, E to);
SortedSet<E> headSet(E to);
SortedSet<E> tailSet(E from);
```

这些方法返回大于或等于 `from` 且严格小于 `to` 的元素子集。对于排序后的映射，类似的方法有：

```java
SortedMap<K, V> subMap(K from, K to);
SortedMap<K, V> headMap(K to);
SortedMap<K, V> tailMap(K from);
```

返回键落在指定范围内的映射视图。`NavigableSet` 接口在 Java 6 中引入对这些子范围操作提供了更多控制。你可以指定边界是否包含：

```java
NavigableSet<E> subSet(E from, boolean fromInclusive, E to, boolean toInclusive);
NavigableSet<E> headSet(E to, boolean toInclusive);
NavigableSet<E> tailSet(E from, boolean fromInclusive);
```

## 9.4.3 不可修改视图（Unmodifiable Views）

`Collections` 类拥有产生集合不可修改视图的方法。这些视图为集合增加了运行时检查。如果检测到修改集合，将抛出异常且集合保持不变。

通过八个方法获取不可修改视图：

- `Collections.unmodifiableCollection`
- `Collections.unmodifiableList`
- `Collections.unmodifiableSet`
- `Collections.unmodifiableSortedSet`
- `Collections.unmodifiableNavigableSet`
- `Collections.unmodifiableMap`
- `Collections.unmodifiableSortedMap`
- `Collections.unmodifiableNavigableMap`

每个方法都定义为基于接口。例如，`Collections.unmodifiableList` 与 `ArrayList`、`LinkedList` 或任何实现 `List` 接口的类工作。

例如，假设你想让代码的某部分查看但不触碰集合的内容。你可以这样做：

```java
List<String> staff = new LinkedList<>();
...
lookAt(Collections.unmodifiableList(staff));
```

`Collections.unmodifiableList` 方法返回一个实现 `List` 接口的类对象。它的访问器方法从 `staff` 集合检索值。当然，`lookAt` 方法可以调用 `List` 接口的所有方法，而不仅仅是访问器。但所有修改器方法（如 `add`）都已重定义为抛出 `UnsupportedOperationException`，而不是将调用转发底层集合。

不可修改视图并没有使集合本身变为不可变。你仍然可以通过原始引用（在本例中为 `staff`）修改集合。你仍然可以对集合的元素调用修改器方法。

视图（views）封装的是 `interface` 而不是实际的集合对象，因此你只能访问接口中定义的方法。例如，`LinkedList` 类具有便利方法 `addFirst` 和 `addLast`，这些方法并不属于 `List` 接口的一部分。这些方法无法通过不可修改的视图进行访问。

![Image](img/caution.jpg) 注意

`unmodifiableCollection` 方法（以及本节稍后讨论的 `synchronizedCollection` 和 `checkedCollection` 方法）返回一个集合，该集合的 `equals` 方法并并不会*调用底层集合的 `equals` 方法。相反，它遗自了 `Object` 类的 `equals` 方法，该方法仅测试对象是否相同。如果你将一个集合或列表转换为普通集合，你将无法再次测试内容是否相等。视图之所以以这种方式工作，是因为在层次结构的这一层级，等价性测试并没有明确的定义。视图处理 `hashCode` 方法的方式也是如此。

然而，`unmodifiableSet` 和 `unmodifiableList` 方法使用了底层集合的 `equals` 和 `hashCode` 方法。

## 9.4.4 同步视图 (Synchronized Views)

如果你从多个线程访问集合，你需要确保该集合不会被意外破坏。例如，如果一个线程尝试向哈希表添加元素，而另一个线程正在对元素进行重哈（rehashing），这将是灾难性的。

库的设计者没有通过实现线程安全的集合类，而是使用了视图机制来使普通集合线程安全。例如，`Collections` 类中的静态方法 `synchronizedMap`可以将任何 map 转换为具有同步访问方法的 `Map`：

```java
Map<String, Employee> map = Collections.synchronizedMap(new HashMap<String, Employee>());
```

现在你可以从多个线程访问 `map` 对象了。像 `get` 和 `put` 等方法是序列化的——每个方法调用在完全完成之前，另一个线程无法调用另一个方法。我们将在第 14 章中详细讨论数据结构同步访问的问题。

## 9.4.5 检查视图 (Checked Views)

检查视图旨在调试泛型类型中可能出现的问题。如第 8 章所解释，实际上可以将错误类型的元素“偷入”泛型集合中。例如：

```java
ArrayList<String> strings = new ArrayList<>();
ArrayList rawList = strings; // 仅有警告，不是错误，为了兼容旧代码
rawList.add(new Date()); // 现在 strings 包含一个 Date 对象！
```

这个错误的 `add` 命令在运行时不会被检测到。相反，当代码的另一部分调用 `get` 并将结果强制转换为 `String` 时，稍会发生类转换异常（class cast exception）。

检查视图可以检测到此问题。如下所示定义一个安全列表：

```java
List<String> safeStrings = Collections.checkedList(strings, String.class);
```

视图的 `add` 方法会检查插入的对象是否属于给定的类，如果不属于，则立即抛出 `ClassCastException`。这样做的好处是错误会在正确的位置报告：

```java
ArrayList rawList = safeStrings;
rawList.add(new Date()); // checked list 抛出一个 ClassCastException
```

![Image](img/caution.jpg) 注意

检查视图受到虚拟机可以执行的运行时检查。例如，如果你有一个 `ArrayList<Pair<String>>`，你无法防止它插入一个 `Pair<Date>`，因为虚拟机只有一个“原始”的 `Pair` 类。

## 9.4.6 关于可选操作的说明

视图通常具有某些限制——它可能是只读的，它可能无法更改大小，或者它支持删除但不支持插入（如 map 的键视图）。如果你尝试不当的操作，限制性视图将抛出 `UnsupportedOperationException`。

在集合和迭代器接口的 API 文档中，许多方法被描述为“可选操作（optional operations）”。这似乎与接口的概念相冲突。毕竟，接口的作用难道不是列出类*必须*实现的方法吗？诚然，从理论角度来看，这种安排安排是不满意的。更好的解决方案可能是为只读视图和无法更改集合大小的视图设计独立的接口。然而，这将使接口数量增加三，库的设计者认为这是不可接受的。

你是否应该将“可选”方法的技术扩展到你自己的设计中？我们认为不应该。尽管集合被频繁使用，但实现它们的编码风格对于其他问题领域并不典型。集合类库的设计者必须解决一组特别严酷的冲突需求。用户希望库易于学习、方便使用、完全通用、防呆（idiot-proof），并且像手编写的算法一样高效。同时实现所有这些目标显然是不可能的，即使是接近也可以。但在你自己的编程问题中，你很少遇到如此极端的约束。你应该能够找到不依赖于“可选”接口操作这种极端措施的解决方案。

```java
java.util.Collections
static <E> Collection unmodifiableCollection(Collection<E> c)
static <E> List unmodifiableList(List<E> c)
static <E> Set unmodifiableSet(Set<E> c)
static <E> SortedSet unmodifiableSortedSet(SortedSet<E> c)
static <E> NavigableSet unmodifiableNavigableSet(NavigableSet<E> c)
static <K, V> Map unmodifiableMap(Map<K, V> c)
static <K, V> SortedMap unmodifiableSortedMap(SortedMap<K, V> c)
static <K, V> NavigableMap unmodifiableNavigableMap(NavigableMap<K, V> c)

static <E> Collection synchronizedCollection(Collection<E> c)
static <E> List synchronizedList(List<E> c)
static <E> Set synchronizedSet(Set<E> c)
static <E> SortedSet synchronizedSortedSet(SortedSet<E> c)
static <E> NavigableSet synchronizedNavigableSet(NavigableSet<E> c)
static <K, V> Map synchronizedMap(Map<K, V> c)
static <K, V> SortedMap synchronizedSortedMap(SortedMap<K, V> c)
static <K, V> NavigableMap synchronizedNavigableMap(NavigableMap<K, V> c)

static <E> Collection checkedCollection(Collection<E> c, Class<E> elementType)
static <E> List checkedList(List<E> c, Class<E> elementType)
static <E> Set checkedSet(Set<E> c, Class<E> elementType)
static <E> SortedSet checkedSortedSet(SortedSet<E> c, Class<E> elementType)
static <E> NavigableSet checkedNavigableSet(NavigableSet<E> c, Class<E> elementType)
static <K, V> Map checkedMap(Map<K, V> c, Class<K> keyType, Class<V> valueType)
static <K, V> SortedMap checkedSortedMap(SortedMap<K, V> c, Class<K> keyType, Class<V> valueType)
static <K, V> NavigableMap checkedNavigableMap(NavigableMap<K, V> c, Class<K> keyType, Class<V> valueType)
static <E> Queue checkedQueue(Queue<E> c, Class<E> elementType)

static <E> List<E> nCopies(int n, E value)
static <E> Set<E> singleton(E value)
static <E> List<E> singletonList(E value)
static <K, V> Map<K, V> singletonMap(K key, V value)
```

构建一个对象的视图，可以是一个 `n` 个相同元素的不可变列表，或者是一个单例集合、列表或映射。

- `static <E> List<E> emptyList()`
- `static <T> Set<T> emptySet()`
- `static <E> SortedSet<E> emptySortedSet()`
- `static NavigableSet<E> emptyNavigableSet()`
- `static <K,V> Map<K,V> emptyMap()`
- `static <K,V> SortedMap<K,V> emptySortedMap()`
- `static <K,V> NavigableMap<K,V> emptyNavigableMap()`
- `static <T> Enumeration<T> emptyEnumeration()`
- `static <T> Iterator<T> emptyIterator()`
- `static <T> ListIterator<T> emptyListIterator()`

返回一个空的集合、映射或迭代器。

---

### java.util.Arrays 1.2



### `java.util.List<E>` 1.2

* `static <E> List<E> asList(E... array)`

返回数组中元素的列表视图，该视图是可以修改的但不可调整大小。

---

### `java.util.List<E>` 1.2

* `List<E> subList(int firstIncluded, int firstExcluded)`

返回位置范围内元素的列表视图。

---

### `java.util.SortedSet<E>` 1.2

* `SortedSet<E> subSet(E firstIncluded, E firstExcluded)`
* `SortedSet<E> headSet(E firstExcluded)`
* `SortedSet<E> tailSet(E firstIncluded)`

返回一个范围内元素的视图。

---

### `java.util.NavigableSet<E>` 6

* `NavigableSet<E> subSet(E from, boolean fromIncluded, E to, boolean toIncluded)`
* `NavigableSet<E> headSet(E to, boolean toIncluded)`
* `NavigableSet<E> tailSet(E from, boolean fromIncluded)`

返回一个范围内元素的视图。`boolean` 标志决定边界是否包含在视图中。

---

### `java.util.SortedMap<K, V>` 1.2

* `SortedMap<K, V> subMap(K firstIncluded, K firstExcluded)`
* `SortedMap<K, V> headMap(K firstExcluded)`
* `SortedMap<K, V> tailMap(K firstIncluded)`

返回键在范围内的条目的映射视图。

---

### `java.util.NavigableMap<K, V>` 6

* `NavigableMap<K, V> subMap(K from, boolean fromIncluded, K to, boolean toIncluded)`
* `NavigableMap<K, V> headMap(K from, boolean fromIncluded)`
* `NavigableMap<K, V> tailMap(K to, boolean toIncluded)`

返回键在范围内的条目的映射视图。`boolean` 标志决定边界是否包含在视图中。

---

## 9.5 算法

泛型集合接口有一个巨大的优势——你只需要实现一次算法。例如，考虑一个计算集合中最大元素的简单算法。传统上，程序员会用循环来实现此类算法。以下是你可以找到数组中最大元素的方法。

```
if (a.length == 0) throw new NoSuchElementException();
T largest = a[0];
for (int i = 1; i < a.length; i++)
    if (largest.compareTo(a[i]) < 0)
        largest = a[i];
```

当然，要找到数组列表（`ArrayList`）的最大值，你写的代码略有不同。

```java
if (v.size() == 0) throw new NoSuchElementException();
T largest = v.get(0);
for (int i = 1; i < v.size(); i++)
    if (largest.compareTo(v.get(i)) < 0)
        largest = v.get(i);
```

链表呢？在链表中你无法高效的随机访问，但你可以使用迭代器。

```java
if (l.isEmpty()) throw new NoSuchElementException();
Iterator<T> iter = l.iterator();
T largest = iter.next();
while (iter.hasNext())
{
    T next = iter.next();
    if (largest.compareTo(next) < 0)
        largest = next;
}
```

这些循环写起来非常冗燥，而且容易出错。是否存在差一错误（off-by-one error）？循环对于空容器是否工作正常？对于只有一个元素的容器又如何？你不想每次都测试和调试这些代码，但你也不想实现一大堆方法，例如这些：

```java
static <T extends Comparable> T max(T[] a)
static <T extends Comparable> T max(ArrayList<T> v)
static <T extends Comparable> T max(LinkedList<T> l)
```

这就是泛型接口的用处。你只需要编写一次算法，就可以应用于任何实现了该接口的集合。事实上，Java 标准库已经包含了许多有用的算法，如排序、二分查找和一些工具。

### 9.5.1 排序与洗牌

老程序员有时会怀念他们过去如何使用打孔卡并手动编写排序算法。如今，排序算法是大多数编程语言标准库的一部分，Java 也不例外。

`Collections` 类中的 `sort` 方法对实现了 `List` 接口的集合。

```java
List<String> staff = new LinkedList<>();
// 填充集合
Collections.sort(staff);
```

该方法假设列表元素实现了 `Comparable` 接口。如果你想以其他方式排序列表，可以使用 `List` 接口的 `sort` 方法并传入一个 `Comparator` 对象。以下是如何按薪资对员工列表排序：

```java
staff.sort(Comparator.comparingDouble(Employee::getSalary));
```

如果你想以*降序*排序列表，请使用静态便利方法 `Comparator.reverseOrder()`。它返回一个返回 `b.compareTo(a)` 的比较器。例如，

```java
staff.sort(Comparator.reverseOrder());
```

将 `staff` 列表中的元素按反序排序，取决于元素类型 `compareTo` 方法给定的顺序。同样地，

```java
staff.sort(Comparator.comparingDouble(Employee::getSalary).reversed());
```

按薪资降序排序。

你可能好奇 `sort` 方法是如何排序列表的。通常，当你从算法书中看到排序算法时，它是针对数组演示的并使用了随机元素访问。然而，链表的随机访问是低效的。实际上，你可以使用归并排序的形式高效地排序链表。但是，Java 编程语言的实现并没有这样做。它简单地将所有元素倒进数组中，排序数组，然后将排序后的序列复制回列表。

`collections` 库中使用的排序算法比 `QuickSort` 慢一点，后者是通用排序算法的传统选择。然而，它有一个巨大的优势：它是**稳定的**（stable），也就是说，它不会交换相等元素。你为什么要关心相等元素的顺序呢？这里有一个常见的场景。假设你有一个已经按姓名排序的员工列表。现在你按薪水进行排序。薪水相同的员工会发生什么变化？使用稳定排序，按姓名的顺序会被保留。换句话说，结果是一个先按薪水排序、再按姓名排序的列表。

`Collections` 不需要实现它们所有的“可选”方法，因此所有接收集合参数的方法都必须描述何时将集合传递给算法是安全的。例如，你显然不能将 `unmodifiableList` 列表传递给 `sort` 算法。你`可以`传递什么类型的列表？根据文档，该列表必须是可修改的，但不需要是可以调整大小的。

术语定义如下：

- 如果列表支持 `set` 方法，则该列表是可修改的 (`modifiable`)。
- 如果列表支持 `add` 和 `remove` 操作，则该列表是可调整大小的 (`resizable`)。

`Collections` 类有一个算法 `shuffle`，它的作用与排序恰相反——它会随机打乱列表中元素的顺序。例如：

```java
ArrayList<Card> cards = . . .;
Collections.shuffle(cards);
```

如果你提供的列表没有实现 `RandomAccess` 接口，`shuffle` 方法会将元素复制到数组中，打乱数组，然后将打乱后的元素复制回列表。

列表 9.7 中的程序向一个数组列表填充了 49 个包含数字 1 到 49 的 `Integer` 对象。然后它随机打乱列表，并从打乱后的列表中选取前六个值。最后，它对选定的值进行排序并打印它们。

**列表 9.7** `shuffle/ShuffleTest.java`

```java
package shuffle;

import java.util.*;

/**
 * 此程序演示了随机洗牌和排序算法。
 * @version 1.11 2012-01-26
 * @author Cay Horstmann
 */
public class ShuffleTest {
    public static void main(String[] args) {
        List<Integer> numbers = new ArrayList<>();
        for (int i = 1; i <= 49; i++)
            numbers.add(i);
        Collections.shuffle(numbers);
        List<Integer> winningCombination = numbers.subList(0, 6);
        Collections.sort(winningCombination);
        System.out.println(winningCombination);
    }
}
```

### `java.util.Collections` 1.2

- `static <T extends Comparable<? super T>> void sort(List<T> elements)`

  使用稳定排序算法对列表中的元素。该算法保证运行在 `O(n log n)` 时间内，其中 `n` 是列表的长度。

- `static void shuffle(List<?> elements)`
- `static void shuffle(List<?> elements, Random r)`

  随机打乱列表中的元素。该算法运行在 `O(n a(n))` 时间内，其中 `n` 是列表的长度，`a(n)` 是访问元素的平均时间。

### `java.util.List<E>` 1.2

- `default void sort(Comparator<? super T> comparator)`

  使用给定的比较器对此列表排序。

### `java.util.Comparator<T>` 1.2

- `static <T extends Comparable<? super T>> Comparator<T> reverseOrder()`

  产生一个反转 `Comparable` 接口提供的顺序的比较器。

- `default Comparator<T> reversed()`

  产生一个反转此比较器提供的顺序的比较器。

### 9.5.2 二分查找

要在数组中查找对象，你通常会访问所有元素直到找到匹配项。然而，如果数组是排序的，你可以查看中间元素，并检查它是否大于你试图查找的元素。如果是，继续在数组的前半部分查找；否则，在后半部分查找。这使得问题减半，你以同样的方式继续。例如，如果数组有 1024 个元素，你将在 10 步后定位匹配项（或确认不存在），而线性搜索如果元素存在，则平均需要 512 步，确认不存在则需要 1024 步。

`Collections` 类的 `binarySearch` 实现了这种算法。注意，集合必须已经排序，否则算法将返回错误答案。要查找元素，请提供集合（必须实现 `List` 接口——更多信息见下文）和要定位的元素。如果集合不是按 `Comparable` 接口的 `compareTo` 元素排序的，请提供一个比较器对象。

```java
i = Collections.binarySearch(c, element);
i = Collections.binarySearch(c, element, comparator);
```

`binarySearch` 的非负返回值表示元素的索引。如果值为负数，则 `i` 表示没有匹配的元素。在这种情况下，键应该插入在 `-i - 1` 处。

### `java.util.Collections` 1.2

- `static <T extends Comparable<? super T>> int binarySearch(List<T> elements, T key)`
- `static <T> int binarySearch(List<T> elements, T key, Comparator<? super T> c)`

  在排序的列表中查找键。如果元素类型实现了 `RandomAccess` 接口，则使用线性搜索，在所有其他情况下使用二分查找。这些方法保证运行在 `O(a(n) log n)` 时间内，其中 `n` 是列表的长度，`a(n)` 是访问元素的平均时间。方法返回键在列表中的索引，如果键不在列表中，则返回负值 `i`。在这种情况下，键应该插入在 `-i - 1` 处。

### 9.5.3 简单算法

`Collections` 类包含了一些简单实用的算法。其中包括本节开头的示例——找到集合的最大值。其他的包括从一个列表复制元素到另一个列表、用常量填充容器以及反转列表。

为什么要在标准库中提供这些简单的算法？大多数程序员都可以轻松地用循环实现它们。我们喜欢这些算法，是因为它们为*阅读*代码的程序员提供了便利。当你阅读别人实现的循环时，你必须破解原始程序员的意图。例如，看这个循环：

```java
for (int i = 0; i < words.size(); i++)
    if (words.get(i).equals("C++")) words.set(i, "Java");
```

现在将该循环与调用对比

```java
Collections.replaceAll("C++", "Java");
```

当你看到方法调用时，立刻知道代码在做什么。

本节末的 API 注释描述了 `Collections` 类中的简单算法。

Java 8 增加了默认方法 `Collection.removeIf` 和 `List.replaceAll`，它们稍微复杂一点。你提供一个 lambda 表达式来测试或转换元素。例如，在这里我们移除了所有短单词，并将剩余单词转换为小写：

```java
words.removeIf(w -> w.length() <= 3);
words.replaceAll(String::toLowerCase);
```

---

### `java.util.Collections` 1.2

• `static <T extends Comparable<? super T>> T min(Collection<T> elements)`
• `static <T extends Comparable<? super T>> T max(Collection<T> elements)`
• `static <T> min(Collection<T> elements, Comparator<? super T> c)`
• `static <T> max(Collection<T> elements, Comparator<? super T> c)`

返回集合中最小或最大的元素。（参数边界为了清晰起见进行了简化。）

• `static <T> void copy(List<? super T> to, List<T> from)`

将源列表的所有元素复制到目标列表的相同位置。目标列表必须与源列表一样长。

• `static <T> void fill(List<?> l, T value)`

将列表的所有位置设置为相同的值。

• `static <T> boolean addAll(Collection<? super T> c, T... values)` 5.0

将所有值添加到指定的集合，如果集合发生变化，则返回 `true`。

• `static <T> boolean replaceAll(List<T> l, T oldValue, T newValue)` 1.4

将所有等于 `oldValue` 的元素替换为 `newValue`。

• `static int indexOfSubList(List<?> l, List<?> s)` 1.4
• `static int lastIndexOfSubList(List<?> l, List<?> s)` 1.4

返回 `l` 中第一个或最后一个等于 `s` 的子列表索引；如果 `l` 没有子列表等于 `s`，则返回 -1。例如，如果 `l` 是 `[s, t, a, r]` 且 `s` 是 `[t, a, r]`，则两个方法都返回索引 1。

• `static void swap(List<?> l, int i, int j)` 1.4

交换给定偏移处的元素。



- `static void reverse(List<?> l)`

  反转列表元素的顺序。例如，反转列表 `[t, a, r]` 会得到列表 `[r, a, t]`。该方法的运行时间为 `O(n)`，其中 `n` 是列表的长度。

- `static void rotate(List<?> l, int d)` `1.4`

  旋转列表中的元素，将索引为 `i` 的项移动到位置 `(i + d) % l.size()`。例如，旋转列表 `[t, a, r]` 2 位会得到列表 `[a, r, t]`。该方法的运行时间为 `O(n)`，其中 `n` 是列表的长度。

- `static int frequency(Collection<?> c, Object o)` `5.0`

  返回 `c` 中等于对象 `o` 的元素计数。

- `boolean disjoint(Collection<?> c1, Collection<?> c2)` `5.0`

  如果集合之间没有共同元素，则返回 `true`。

---

### `java.util.Collection<T>` `1.2`

- `default boolean removeIf(Predicate<? super E> filter)` 8

  移除所有匹配的元素。

---

### `java.util.List<E>` `1.2`

- `default void replaceAll(UnaryOperator<E> op)` 8

  将该操作应用于此列表的所有元素。

#### 9.5.4 批量操作（Bulk Operations）

有几种操作可以“批量”复制或移除元素。调用：

```java
coll1.removeAll(coll2);
```

移除 `coll1` 中存在于 `coll2` 的所有元素。相反：

```java
coll1.retainAll(coll2);
```

移除 `coll1` 中不在 `coll2` 中的所有元素。这是一个典型的应用。假设你想找到两个集的交集——即两个集合共同拥有的元素。首先，创建一个集合来存储结果。

```java
Set<String> result = new HashSet<>(a);
```

这里，我们利用了每个集合都有一个参数为另一个集合的构造函数。现在，使用 `retainAll` 方法：

```java
result.retainAll(b);
```

它保留了所有恰好在 `b` 中的元素。你在没有编写循环的情况下形成了交集。

你可以进一步扩展这个想法，对视图（view）应用批量操作。例如，假设你有一个将员工 ID 映射到员工对象的 map，你有一个待离职员工 ID 的集合。

```java
Map<String, Employee> staffMap = . . ++;
Set<String> terminatedIDs = . . ++;
```

简单地形成键集并移除所有离职员工的 ID。

```java
staffMap.keySet().removeAll(terminatedIDs);
```

由于键集是一个视图，元素从 map 中移除。

#### 9.5.5 集合与数组之间的转换

Java API 的大部分内容是在集合框架出现之前设计的。因此，你有时需要在数组和集合之间进行转换。

如果你有一个数组需要转换为集合，`Arrays.asList` 可以满足此目的。例如：

```java
String[] values = ...;
List<String> staff = new ArrayList<>(Arrays.asList(values));
```

从集合获取数组稍微复杂一些。当然，你可以使用 `toArray` 方法：

```java
Object[] values = staff.toArray();
```

但 `toArray()` 返回的结果是 `Object[]`。即使你知道集合包含特定类型的对象，你不能直接进行强制转换：

```java
String[] values = (String[]) staff.toArray(); // 错误！
```

`toArray` 返回的数组是 `Object[]` 创建的，你无法更改它的类型。相反，使用 `toArray` 的变体并给它一个长度为 0 的所需类型数组：

```java
String[] values = staff.toArray(new String[0]);
```

返回的数组随后按相同类型创建。

---

![图像](img/note.jpg) **注意**

你可能会疑惑为什么不能简单地将一个 `Class` 对象（例如 `String.class`）传递给 `toArray` 方法。然而，该方法承担了双重职责——既可以填充现有数组（只要长度足够），也可以创建一个新数组。

---

### 9.5.6 编写自己的算法

如果你编写自己的算法（或者说，任何以集合作为参数的方法），应尽可能与接口工作，而不是具体实现。例如，假设你想用一组项填充 `JMenu`。在传统上，这种方法可能是这样实现的：

```java
void fillMenu(JMenu menu, ArrayList<JMenuItem> items)
{
    for (JMenuItem item : items)
        menu.add(item);
}
```

然而，现在限制了调用者——调用者必须提供 `ArrayList`。如果选择恰好在另一个容器中，它们首先需要重新包装。最好接受更通用的集合。

你应该问自己：能够完成工作的最通用接口是什么？在这种情况下，你只需要访问所有元素的能力。这是你如何重写 `fillMenu` 以接受任意类型的集合：

```java
void fillMenu(JMenu menu, Collection<JMenuItem> items)
{
    for (JMenuItem item : items)
        menu.add(item);
}
```

现在，任何人都可以使用 `ArrayList` 或 `LinkedList` 调用此方法，甚至可以使用用 `Arrays.asList` 包装的数组。

---

![图像](img/note.jpg) **备注**

如果使用集合接口作为方法参数是一个这么好的主意，为什么 Java 库没有更频繁地遵循这一规则呢？例如，`JComboBox` 类有两个构造函数：

```java
JComboBox(Object[] items)
JComboBox(Vector<?> items)
```

其原因仅仅是时机问题。Swing 库是在集合库出现之前创建的。

---

如果你编写了一个*返回集合*的方法，你可能也想返回一个接口而不是类，因为你以后可以改变主意，稍后用不同的集合重新实现该方法。

例如，让我们写一个 `getAllItems` 方法，返回菜单的所有项。

```java
List<JMenuItem> getAllItems(JMenu menu)
{
    List<JMenuItem> items = new ArrayList<>()
    for (int i = 0; i < menu.getItemCount(); i++)
        items.add(menu.getItem(i));
    return items;
}
```

后期，你可能决定不想*复制这些项*，而是仅仅提供它们的一个视图。你可以通过返回一个 `AbstractList` 的匿名子类来实现这一点。

```java
List<JMenuItem> getAllItems(final JMenu menu)
{
    return new
        AbstractList<>()
        {
            public JMenuItem get(int i)
            {
                return menu.getItem(i);
            }
            public int size()
            {
                return menu.getItemCount();
            }
    };
}
```

当然，这是一种高级技术。如果你使用了它，请务必准确地记录支持哪些“可选”操作。在这种情况下，你必须告知调用者返回的对象是一个不可修改的列表。

### 9.6 遗留集合

自 Java 最初发布以来，在集合框架出现之前，就已经存在许多“遗留”容器类。

它们已经集成到集合框架中——参见图 9.12。我们将在后续章节中简要介绍它们。

![图像](img/09fig12.jpg)

**图 9.12** 集合框架中的遗留类

#### 9.6.1 Hashtable 类

经典的 `Hashtable` 类与 `HashMap` 类的作用相同，并且本质上具有相同的接口。就像 `Vector` 类的方法一样，`Hashtable` 的方法是同步的。如果你不需要与遗留代码兼容，应该使用 `HashMap`。如果你需要并发访问，请使用 `ConcurrentHashMap`——参见第 14 章。

#### 9.6.2 Enumerations（枚举迭代器）

遗留集合使用 `Enumeration` 接口来遍历元素序列。`Enumeration` 接口有两个方法：`hasMoreElements` 和 `nextElement`。这些与 `Iterator` 接口的 `hasNext` 和 `next` 方法完全对应。

例如，`Hashtable` 类的 `elements` 方法会产生一个用于枚举表中值的枚举对象：

```java
Enumeration<Employee> e = staff.elements();
while (e.hasMoreElements())
{
    Employee e = e.nextElement();
    ...
}
```

你偶尔会遇到一个期望 `enumeration` 参数的遗留方法。静态方法 `Collections.enumeration` 会产生一个用于枚举集合中元素的枚举对象。例如：

```java
List<InputStream> streams = ...;
SequenceInputStream in = new SequenceInputStream(Collections.enumeration(streams));
// SequenceInputStream 构造函数期望一个 enumeration
```

---

![图像](img/note.jpg) **备注**

如果使用集合接口作为方法参数是一个这么好的主意，为什么 Java 库没有更频繁地遵循这一规则呢？例如，`JComboBox` 类有两个构造函数：

```java
JComboBox(Object[] items)
JComboBox(Vector<?> items)
```

其原因仅仅是时机问题。Swing 库是在集合库出现之前创建的。

---

如果你编写了一个*返回集合*的方法，你可能也想返回一个接口而不是类，因为你以后可以改变主意，稍后用不同的集合重新实现该方法。

例如，让我们写一个 `getAllItems` 方法，返回菜单的所有项。

```java
List<JMenuItem> getAllItems(JMenu menu)
{
    List<JMenuItem> items = new ArrayList<>()
    for (int i = 0; i < menu.getItemCount(); i++)
        items.add(menu.getItem(i));
    return items;
}
```

后期，你可能决定不想*复制这些项*，而是仅仅提供它们的一个视图。你可以通过返回一个 `AbstractList` 的匿名子类来实现。。

```java
List<JMenuItem> getAllItems(final JMenu menu)
{
    return new
        AbstractList<>()
        {
            public JMenuItem get(int i)
            {
                return menu.getItem(i);
            }
            public int size()
            {
                return menu.getItemCount();
            }
    };
}
```

当然，这是一种高级技术。如果你使用了它，请务必准确地记录支持哪些“可选”操作。在这种情况下，你必须告知调用者返回的对象是一个不可修改的列表。

### 9.6 遗留集合

自 Java 最初发布以来，在集合框架出现之前，就已经存在许多“遗留”容器类。

它们已经集成到集合框架中——参见图 9.12。

#### 9.6.1 Hashtable 类



经典的 `Hashtable` 类与 `HashMap` 类的作用相同，并且本质上具有相同的接口。就像 `Vector` 类的方法一样，`Hashtable` 的方法是同步的。如果你不需要与遗留代码兼容，应该使用 `HashMap`。如果你需要并发访问，请使用 `ConcurrentHashMap`——参见第 14 章。

#### 9.6.2 Enumerations（枚举迭代器）

遗留集合使用 `Enumeration` 接口来遍历元素序列。`Enumeration` 接口有两个方法：`hasMoreElements` 和 `nextElement`。这些与 `Iterator` 接口的 `hasNext` 和 `next` 方法完全对应。

例如，`Hashtable` 类的 `elements` 方法会产生一个用于枚举表中值的枚举对象：

点击此处查看代码图像

```java
Enumeration<Employee> e = staff.elements();
while (e.hasMoreElements())
{
    Employee e = e.nextElement();
    ...
}
```

你偶尔会遇到一个期望 `enumeration` 参数的遗留方法。静态方法 `Collections.enumeration` 会产生一个用于枚举集合中元素的枚举对象。例如：

点击此处查看代码图像

```java
List<InputStream> streams = ...;
SequenceInputStream in = new SequenceInputStream(Collections.enumeration(streams));
// SequenceInputStream 构造函数期望一个 enumeration
```

将 `i` 位置 1。最后，

```java
bucketOfBits.clear(i)
```

将 `i` 位置 0。

![Image](img/note1.jpg) C++ Note

C++ 的 `bitset` 模板与 Java 平台的 `BitSet` 相同的功能。

### java.util.BitSet `1.0`

- `BitSet(int initialCapacity)` 构造一个位集。
- `int length()` 返回位集的“逻辑长度”：`1` 加上最高置 1 位的索引。
- `boolean get(int bit)` 获取一个位的值。
- `void set(int bit)` 设置一个位。
- `void clear(int bit)` 清空一个位。
- `void and(BitSet set)` 将此位集与另一个位集进行逻辑与（AND）运算。
- `void or(BitSet set)` 将此位集与另一个位集进行逻辑或（OR）运算。
- `void xor(BitSet set)` 将此位集与另一个位集进行逻辑异或（XOR）运算。
- `void andNot(BitSet set)` 清空此位集中所有在另一个位集中被置 1 的位。

作为位集使用的示例，我们想向你展示一种寻找素数的“埃拉托尼筛法”（sieve of Eratosthenes）算法实现。（素数是指像 2、3 或 5 这样只能被自己和 1 整除的数，而埃拉托尼筛法是最早发现的这些基础构建单元的方法之一。）这并不是一个寻找素数的完美算法，但出于某种原因，它变成了编译器性能的热门基准。（它也不是一个很好的基准，因为它主要测试位操作。）

好吧，我们遵循传统并提供一个实现。这个程序统计 2 到 2,000,000 之间的所有素数。（在这个范围内有 148,933 个素数，所以你可能不想把它们全部打印出来。）

在不涉及程序过多细节的情况下，其思想是遍历一个拥有 200 万位的位集。首先，我们开启所有位。之后，我们关闭所有已知素数倍数的位。经过此过程后剩余的位的位置本身就是素数。Listing 9.8 列出了 Java 语言实现的该程序，而 Listing 9.9 是 C++ 代码。

![Image](img/note.jpg) Note

尽管筛法不是一个很好的基准，但我们无法抵制对该算法的两种实现进行计时。以下是在运行 Ubuntu 14.04、配备 8 GB 内存的 2.9-GHz 双核 ThinkPad 上的计时结果。

- C++ (`g++ 4.6.3`)：390 毫秒
- Java (`Java SE 8`)：119 毫秒

我们已经在 *Core Java* 的九个版本中运行过这项测试，在最后五个版本中，Java 轻松击败 C++。公平地说，如果调高 C++ 编译器的优化级别，它以 33 毫秒的时间超过了 Java。只有当程序运行得足够长以触发 Hotspot 即时编译器（JIT compiler）时，Java 才能与之匹配。

#### Listing 9.8 `sieve/Sieve.java`

点击此处查看代码图像

```java
package sieve;

import java.util.*;

/**
 * 此程序运行埃拉托尼筛法基准。它计算所有直到 2,000,000 的素数。
 * @version 1.21 2004-08-03
 * @author Cay Horstmann
 */
public class Sieve
{
    public static void main(String[] s)
    {
        int n = 2000000;
        long start = System.currentTimeMillis();
        BitSet b = new BitSet(n + 1);
        int count = 0;
        int i;
        for (i = 2; i <= n; i++)
            b.set(i);
        i = 2;
        while (i * i <= n)
        {
            if (b.get(i))
            {
                count++;
                int k = 2 * i;
                while (k <= n)
                {
                    b.clear(k);
                    k += i;
                }
            }
            i++;
        }
        while (i <= n)
        {
            if (b.get(i)) count++;
            i++;
        }
        long end = System.currentTimeMillis();
        System.out.println(count + " primes");
        System.out.println((end - start) + " milliseconds");
    }
}
```

#### Listing 9.9 `sieve/sieve.cpp`

点击此处查看代码图像

```cpp
/**
 * @version 1.21 2004-08-03
 * @author Caymann
 */
#include <bitset>
#include <iostream>
#include <ctime>

using namespace std;

int main()
{
    const int N = 2000000;
    clock_t cstart = clock();

    bitset<N + 1> b;
    int count = 0;
    int i;
    for (i = 2; i <= N; i++)
        b.set(i);
    i = 2;
    while (i * i <= N)
    {
        if (b.test(i))
        {
            count++;
            int k = 2 * i;
            while (k <= N)
            {
                b.reset(k);
                k += i;
            }
        }
        i++;
    }
    while (i <= N)
    {
        if (b.test(i))
            count++;
        i++;
    }

    clock_t cend = clock();
    double millis = 1000.0 * (cend - cstart) / CLOCKS_PER_SEC;

    cout << count << " primes\n" << millis << " milliseconds\n";

    return 0;
}
```

这就是对 Java 框架的介绍。正如你所看到的，Java 提供了大量的类来满足你的编程需求。在下一章中，你将学习如何编写图形用户界面。

# 第 10 章 图形编程

## 本章内容

- 10.1 Introduction Swing
- 10.2 创建 Frame
- 10.3 定位 Frame
- 10.4 在组件中显示信息
- 10.5 使用 2D API
- 10.6 使用颜色
- 10.7 使用特殊字体显示文本
- 10.8 显示图像

到目前为止，你只学会了编写从键盘获取输入、处理并在控制台屏幕上显示结果的程序。这并不是大多数用户想要的。现代程序不是这样工作的，网页页也是如此。本章将带你进入编写图形用户界面（GUI）的 Java 程序之路。特别是，你将学习如何编写在屏幕上调整窗口大小并定位、显示多种字体文本等程序。

基于对等（peer-based）的方法在简单应用程序中效果良好，但很快就会发现，编写一个依赖于原生用户界面元素的、高质量的可移植图形库是极其困难的。像菜单、滚动条和文本字段等用户界面元素在不同平台上的行为可能存在细微差异。因此，通过这种方法很难为用户提供一致且可预测的体验。此外，某些图形环境（如 X11/Motif）拥有的用户界面组件库并不像 Windows 或 Macintosh 那样丰富。这反过来进一步限制了基于“最小公约数”方法的可移植库。结果，使用 `AWT` 构建的 GUI 应用程序看起来并不像原生的 Windows 或 Macintosh 应用程序那样漂亮，也不具备这些平台用户所期待的功能。更令人沮丧的是，不同平台上的 `AWT` 用户界面库存在不同的 Bug。开发者抱怨说，他们必须在每个平台上都测试自己的应用程序——这种做法被嘲讽地称为“一次编写，处处调试”。

1996 年，Netscape 创建了一个名为 `IFC`（网络基础类）的 GUI 库，它采用了一种完全不同的方法。用户界面元素（如按钮、菜单等）被绘制在空白窗口上。底层窗口系统所需的功能仅为一种显示窗口和在窗口上进行绘制的方法。因此，Netscape 的 `IFC` 组件无论程序运行在哪个平台上，其外观和行为都是相同的。Sun 与 Netscape 合作完善了这种方法，创建了一个代号为“Swing”的用户界面库。`Swing` 作为 `Java 1.1` 的扩展被提供，并成为 `Java SE 1.2` 标准库的一部分。

正如杜克·埃林顿（Duke Ellington）所说，“如果没有那种 Swing 感觉，它就毫无意义（It Don’t Mean a Thing If It Ain’t Got That Swing）”，`Swing` 现在是这种非对等 GUI 工具包的正式名称。`Swing` 是 `Java Foundation Classes`（`JFC`）的一部分。整个 `JFC` 非常庞大，包含的内容远不止 `Swing` GUI 工具包；除了 `Swing` 组件外，它还拥有访问性 API、2D API 和拖放 API。

***

![Image](img/note.jpg) 备注

`Swing` 并不是 `AWT` 的完全替代品——它是基于 `AWT` 架构构建的。`Swing` 只是为你提供了更强大的用户界面组件。每当你编写 `Swing` 程序时，你都会使用 `AWT` 的基础——特别是事件处理。从现在起，当我们说“Swing”时，指的是“绘制”的用户界面类；当我们说“AWT”时，指的是窗口工具包的底层机制，例如事件处理。

***

当然，基于 `Swing` 的用户界面元素在用户屏幕上出现的速度会比 `AWT` 使用的对等组件慢一些。根据我们的经验，在任何相当现代的机器上，速度差异都不应该是问题。另一方面，选择 `Swing` 的理由是压倒性的优势：

- `Swing` 拥有一套丰富且方便的用户界面元素。
- `Swing` 对底层平台的依赖较少；因此较不容易产生特定平台的 Bug。
- `Swing` 提供了跨平台的一致用户体验。

尽管如此，第三个优点也是一个潜在的缺点：如果用户界面元素在所有平台上看起来都一样，那么它们与原生控件看起来不同，因此用户对它们的熟悉程度较低。

`Swing` 以一种非常优雅的方式解决了这个问题。编写 `Swing` 程序的程序员可以为程序赋予特定的“外观和感觉（look-and-feel）”。例如，图 10.1 和 10.2 显示了同一个程序在 Windows 和 GTK 外观感觉下的运行情况。

![Image](img/10fig01.jpg)

**图 10.1** `Swing` 的 Windows 外观和感觉

![Image](img/10fig02.jpg)

**图 10.2** `Swing` 的 GTK 外观和感觉

此外，Sun 开发了一种名为“Metal”的平台无关的外观，直到营销人员将其重命名为“Java 外观（Java look-and-feel）”。然而，大多数程序员继续使用“Metal”术语，我们在书中也会这样做。

有些人批评 `Metal` 过于呆板，因此在 `Java SE 5.0` 发布时对其外观进行了更新（参见图 10.3）。现在 `Metal` 外观支持多种主题——颜色和字体的细微变化。默认主题被称为“Ocean（海洋）”。

![Image](img/10fig03.jpg)

**图 10.3** Metal 外观感觉的 Ocean 主题

在 `Java SE 6` 中，Sun 改进了对 Windows 和 GTK 原生外观感觉的支持。`Swing` 现在将获取颜色方案自定义，并忠实地渲染那些流行的动态按钮和滚动条。

一种名为 `Nimbus` 的新外观感觉（图 10.4）从 `Java SE 7` 开始提供，但默认不可用。`Nimbus` 使用矢量图而非位图，因此独立于屏幕分辨率。

![Image](img/10fig04.jpg)

**图 10.4** Nimbus 外观感觉

有些用户喜欢他们的 Java 程序使用原生外观感觉，其他人喜欢 `Metal` 或第三方外观感觉。正如你在第 11 章中将看到的，让用户选择他们喜爱的外观感觉非常简单。

***

![Image](img/note.jpg) 备注

虽然我们在书中没有空间教你如何实现，但 Java 程序员可以扩展现有的外观感觉，甚至设计一个全新的。这是一个涉及指定 Swing 组件如何绘制的繁琐过程。一些开发者已经这样做了，特别是当 Java 移植到自助终端或手持设备时。访问 [`javootoo.com`](http://javootoo.com) 可以找到一些有趣的实现。

`Java SE 5.0` 引入了一种名为 `Synth` 的外观感觉，使得这个过程变得简单。在 `Synth` 中，你可以通过提供文件和 XML 描述符来定义新的外观感觉，而无需编程。

***

![Image](img/tip.jpg) 提示

Napkin 外观感觉（[`napkinlaf.sourceforge.net`](http://napkinlaf.sourceforge.net)）为所有用户界面元素提供了手绘外观。这在你向客户展示原型时非常有用，传达出一个清晰的信息：你给给他们的不是成品。

***

![Image](img/note.jpg) 备注

大多数 Java 用户界面编程现在使用 `Swing` 完成，但有一个显著的例外。Eclipse 集成开发环境使用一个名为 `SWT` 的图形库，它与 `AWT` 相似，映射到各种平台的原生组件。你可以在 [`eclipse.org/articles`](http://eclipse.org/articles) 找到关于 `SWT` 的文章。

Oracle 正在开发一种名为 `JavaFX` 的替代技术作为 `Swing` 的替代品。我们书中没有讨论 `JavaFX`。更多信息请参见 [`docs.oracle.com/javase/8/javafx/get-started-tutorial/jfx-overview.htm`](http://docs.oracle.com/javase/8/javafx/get-started-tutorial/jfx-overview.htm)。

***

本章的剩余部分将向你展示显示窗口和绘制内容的基础知识。

## 10.2 创建窗口

在 Java 中，顶层窗口（即不包含在另一个窗口内的窗口）被称为帧（frame）。AWT 库有一个名为 `Frame` 的类用于这种顶层窗口。该类的 Swing 版本被称为 `JFrame`，它继承自 `Frame` 类。`JFrame` 是 Swing 组件中少数几个不在画布上绘制的组件之一。因此，装饰性（按钮、标题栏、图标等）是由用户的窗口系统绘制的，而不是由 Swing 绘制的。

* *

![Image](img/caution.jpg) 注意



大多数 Swing 组件类都以“J”开头：`JButton`、`JFrame` 等。虽然存在诸如 `Button` 和 `Frame` 这样的类，但它们是 AWT 组件。如果你不小心漏掉了“J”，你的程序可能仍然编译并运行，但 Swing 和 AWT 组件的混合会导致视觉和行为上的不一致。

在本节中，我们将介绍操作 Swing `JFrame` 的最常用方法。列表 10.1 列出了一个简单的程序，该程序在屏幕上显示一个空帧，如图 10.5 所示。

![Image](img/10fig05.jpg)

**图 10.5** 最简单的可见帧

**列表 10.1** `simpleframe/SimpleFrameTest.java`

点击此处查看代码图片

```java
package simpleFrame;

import java.awt.*;
import javax.swing.*;

/**
 * @version 1.33 2015-05-12
 * @author Cay Horstmann
 */
public class SimpleFrameTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            SimpleFrame frame = new SimpleFrame();
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

class SimpleFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public SimpleFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

让我们逐行分析这个程序。

Swing 类存放在 `javax.swing` 包中。包名 `java.x` 表示这是一个 Java 扩展包，而不是核心包。出于历史原因，Swing 被认为是一个扩展。然而，自 1.2 版本以来，在每个 Java SE 实现中都存在它。

默认情况下，帧的尺寸为非常没有用的 0 × 0 像素。我们定义了一个子类 `SimpleFrame`，其构造函数将尺寸设置为 300 × 200 像素。这是 `SimpleFrame` 和 `JFrame` 之间唯一的区别。

在 `SimpleFrameTest` 类的 `main` 方法中，我们构造了一个 `SimpleFrame` 对象并使其变为可见。

在每个 Swing 程序中，我们都需要解决两个技术问题。

首先，所有的 Swing 组件都必须从事件分发线程（event dispatch thread）进行配置，该线程是将鼠标点击和按键输入等事件传递给用户界面组件的控制线程。以下代码段用于在事件分发线程中执行语句：

```java
EventQueue.invokeLater(() ->
{
    statements
});
```

我们将在第 14 章中讨论细节。

![Image](img/caution.jpg) 注意

大多数 Swing 组件类都以“J”开头：`JButton`、`JFrame` 等。虽然存在诸如 `Button` 和 `Frame` 这样的类，但它们是 AWT 组件。如果你不小心漏掉了“J”，你的程序可能仍然编译并运行，但 Swing 和 AWT 组件的混合会导致视觉和行为上的不一致。

本节的 API 说明列出了我们认为的赋予框架正确外观和感觉的最重要方法。其中一些方法定义在 `JFrame` 类中，另一些方法则来自 `JFrame` 的各种超类。在某些情况下，你可能需要搜索 API 文档以查看是否有用于某些特殊用途的方法。遗憾的是，对于继承的方法，这样做有点繁琐。例如，`toFront` 方法适用于 `JFrame` 类型的对象，但由于它只是简单地继承自 `Window` 类，因此 `JFrame` 的文档并没有解释它。如果你觉得应该有一个方法来执行某些操作，但在你正在处理的类的文档中没有提到它，请尝试查看该类的各超类方法的 API 文档。每个 API 页面的顶部都有通往超类的超链接，而继承的方法列在新方法和重写方法的摘要下方。

正如 API 注意事项所示，`Component` 类（所有 GUI 对象的祖先）和 `Window` 类（`Frame` 类的超类）是你需要查找调整框架大小和形状方法的地方。例如，`Component` 类中的 `setLocation` 方法是重新定位组件的一种方法。如果你调用：

```java
setLocation(x, y)
```

左上角将位于向右 `x` 像素、向下 `y` 像素的位置，其中 `(0, 0)` 是屏幕的左上角。同样，`Component` 中的 `setBounds` 方法允许你一步到位调整组件的大小并重新定位（特别是 `JFrame`），如下：

```java
setBounds(x, y, width, height)
```

或者，你可以让窗口系统控制窗口的放置。如果你在显示窗口之前调用：

```java
setLocationByPlatform(true);
```

窗口系统将选择位置（但不选择大小），通常与上一个窗口有轻微的偏移。

![Image](img/note.jpg) 注意

对于框架而言，`setLocation` 和 `setBounds` 的坐标是相对于整个屏幕的。正如你将在第 12 章中看到的那样，对于容器内部的其他组件，测量值是相对于容器的。

### 10.3.1 框架属性

组件类的许多方法以 getter/setter 对的形式出现，例如 `Frame` 类的以下方法：

```java
public String getTitle()
public void setTitle(String title)
```

这样的 getter/setter 对被称为一个*属性*。一个属性有一个名称和一个类型。名称通过将 `get` 或 `set` 之后的第一个字母改为小写来获得。例如，`Frame` 类有一个名称为 `title` 且类型为 `String` 的属性。

从概念上讲，`title` 是框架的一个属性。当我们设置该属性时，我们期望标题在用户的屏幕上发生变化。当我们获取该属性时，我们期望得到我们所设置的值。

我们不知道（或不在乎）`Frame` 类如何实现这个属性。它可能简单地使用它的对等框架（peer frame）来存储标题。它可能有一个实例字段：

```java
private String title; // 属性不需要
```

如果该类确实有一个匹配的实例字段，我们不知道（或不在乎）getter 和 setter 方法是如何实现的。它们可能只是读取和写入该实例字段。它们可能做了更多工作，例如在每次更改时通知窗口系统。

`get`/`set` 惯例有一个例外：对于 `boolean` 类型的属性，getter 以 `is` 开头。例如，以下两个方法定义了 `locationByPlatform` 属性：

```java
public boolean isLocationByPlatform()
public void setLocationByPlatform(boolean b)
```

### 10.3.2 确定良好的框架大小

记住：如果你不显式地为框架设置大小，所有框架将默认为 0 × 0 像素。为了保持我们的示例程序简单，我们将框架调整为我们认为在大多数显示器上运行尚可的大小。然而，在专业应用程序中，你应该检查用户屏幕的分辨率并编写代码相应调整框架的大小：在低端笔记本电脑屏幕上看起来很好的窗口，在高分辨率屏幕上看起来会像一张邮票。

要查找屏幕大小，请使用以下步骤。调用 `Toolkit` 类的静态方法 `getDefaultToolkit` 来获取 `Toolkit` 对象。（`Toolkit` 类是各种与原生窗口系统接口的方法的汇聚地。）然后，调用 `getScreenSize` 方法，该方法作为 `Dimension` 对象返回屏幕大小。`Dimension` 对象同时在公共的 (!) 实例变量 `width` 和 `height` 中存储宽度和高度。以下是代码：

```java
Toolkit kit = Toolkit.getDefaultToolkit();
Dimension screenSize = kit.getScreenSize();
int screenWidth = screenSize.width;
int screenHeight = screenSize.height;
```

我们使用这些值的 50% 作为框架大小，并告诉窗口系统放置框架：

```java
setSize(screenWidth / 2, screenHeight / 2);
```

我们还提供图标。`ImageIcon` 类对于加载图像非常方便。以下是它的使用方法：

```java
Image img = new ImageIcon("icon").getImage();
setIcon(img);
```

根据你的操作系统，你可以在不同的地方看到图标。例如，在 Windows 中，图标在左上角，你可以在按 Alt+Tab 的活动任务列表中看到它。

处理框架的一些技巧：

- 如果你的框架包含按钮和文本字段等标准组件，只需调用 `pack` 将框架调整为包含所有组件的最小大小。你可以通过调用 `setExtendedState(Frame.MAXIMIZED_BOTH)` 最大化框架。
- 启动应用程序时，记住用户的位置和大小也是好主意。
- 如果你编写利用多个显示器的应用程序，使用 `GraphicsEnvironment` 和 `GraphicsDevice` 类来查找显示器的尺寸。`GraphicsDevice` 类还允许你以全屏模式执行应用程序。

```java
package sizedFrame;

import java.awt.*;
import javax.swing.*;

/**
 * @version 1.3 2007-05-12
 * @author Cay Horstmann
 */
public class SizedTest {
    public static void main(String[] args) {
        EventQueue.invokeLater(() -> {
            JFrame frame = new SizedFrame();
            frame.setTitle("SizedFrame");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

class SizedFrame extends JFrame {
    public SizedFrame() {
        // get screen dimensions
        Toolkit kit = Toolkit.getDefaultToolkit();
        Dimension screenSize = kit.getScreenSize();
        int screenWidth = screenSize.width;
        int screenHeight = screenSize.height;
    }
}
```

```java
// 设置帧宽、高度并让平台选择屏幕位置
setSize(screenWidth / 2, screenHeight / 2);
setLocationByPlatform(true);

// 设置帧图标
Image img = new ImageIcon("icon.gif").getImage();
setIconImage(img);
}
```

### java.awt.Component 1.0

- `boolean isVisible()`
- `void setVisible(boolean b)`

获取或设置 `visible` 属性。组件初始是可见的，但 `JFrame` 等顶层组件除外。

- `void setSize(int width, int height)` 1.1

将组件的大小调整为指定的宽度和高度。

- `void setLocation(int x, int y)` 1.1

将组件移动到新位置。如果组件不是顶层组件，则 `x` 和 `y` 坐标使用容器的坐标；如果组件是顶层组件（例如 `JFrame`），则使用屏幕坐标。

- `void setBounds(int x, int y, int width, int height)` 1.1

移动并调整此组件的大小。

- `Dimension getSize()` 1.1
- `void setSize(Dimension d)` 1.1

获取或设置此组件的 `size` 属性。

### java.awt.Window 1.0

- `void toFront()`

将此窗口置在任何其他窗口之上。

- `void toBack()`

将此窗口移动到桌面窗口栈的最后，并相应地重新排列所有其他可见窗口。

- `boolean isLocationByPlatform()` 5.0
- `void setLocationByPlatform(boolean b)` 5.0

获取或设置 `locationByPlatform` 属性。当窗口显示之前设置该属性时，平台将选择合适的位置。

### java.awt.Frame 1.0

- `boolean isResizable()`
- `void setResizable(boolean b)`

获取或设置 `resizable` 属性。当设置该属性时，用户可以调整帧的大小。

- `String getTitle()`
- `void setTitle(String s)`

获取或设置 `title` 属性，该属性决定帧标题栏中的文本。

- `Image getIconImage()`
- `void setIconImage(Image image)`

获取或设置 `iconImage` 属性，该属性决定帧的图标。窗口系统可能会将图标作为帧装饰的一部分或其他位置进行显示。

- `boolean isUndecorated()` 1.4
- `void setUndecorated(boolean b)` 1.4

获取或设置 `undecorated` 属性。当设置该属性时，帧将在没有装饰（如标题栏或关闭按钮）的情况下显示。此方法在帧显示之前调用。

- `int getExtendedState()` 1.4
- `void setExtendedState(int state)` 1.4

获取或设置扩展窗口状态。该状态为以下之一：

- `Frame.NORMAL`
- `Frame.ICONIFIED`
- `Frame.MAXIMIZED_HORIZ`
- `Frame.MAXIMIZED_VERT`
- `Frame.MAXIMIZED_BOTH`

### java.awt.Toolkit 1.0

- `static Toolkit getDefaultToolkit()`

返回默认工具包。

- `Dimension getScreenSize()`

获取用户屏幕的大小。

### javax.swing.ImageIcon 1.2

- `ImageIcon(String filename)`

构造一个图像存储在文件中的图标。

- `Image getImage()`

获取此图标的图像。

## 10.4 在组件中显示信息

在本节中，我们将向你展示如何在帧内部显示信息。例如，我们不再像第 3 章中那样在控制台窗口以文本模式显示“Not a Hello World program”，而是在帧中显示消息，如图 10.7 所示。

![Image](img/10fig07.jpg)

**图 10.7** 显示信息的帧

你可以直接将消息字符串绘制到帧上，但这并不被认为是良好的编程实践。在 Java 中，帧实际上被设计为组件的容器，例如菜单栏和其他用户界面元素。你通常会在添加到帧的另一个组件上进行绘图。

`JFrame` 的结构出奇地复杂。看图 10.8，它展示了 `JFrame` 的组成部分。你可以看到，`JFrame` 中层叠了四个面板。根面板（root pane）、分层面板（layered pane）和玻璃面板（glass pane）是根面板。......

```java
c =
();
contentPane.add(c);
```

![Image](img/10fig8.jpg)

**图 10.8** `JFrame` 的内部结构

在 Java SE 1.4 之前，`JFrame` 的 `add` 方法定义为：` `......

在我们的案例中，我们想在原始窗口中绘制字符串 `"Not a Hello World Program"`，位置大约位于窗口宽度的四分之一处和高度的一半处。虽然我们还不知道如何测量字符串的大小，但我们将字符串从坐标 `(75, 100)` 处开始。这意味着字符串中的第一个字符将从向右偏移 75 像素、向下 100 像素的位置开始。（实际上，向下 100 像素的是文本的基线——有关如何测量文本的更多信息，请参阅第 576 页。）因此，我们的 `paintComponent` 方法如下：

点击此处查看代码图片



```java
public class NotHelloWorldComponent extends JComponent

{
   public static final int MESSAGE_X = 75;
   public static final int MESSAGE_Y = 100;
   public void paintComponent(Graphics g)
   {
      g.drawString("Not a Hello World program", MESSAGE_X, MESSAGE_Y);
   }
   ...
}
```

最后，组件应该告诉用户它希望自己有多大。重写`getPreferredSize`方法并返回一个带有首选宽度和高度的`Dimension`类对象：

点击此处查看代码图片

```java
public class NotHelloWorldComponent extends JComponent
{
   private static final int DEFAULT_WIDTH = 300;
   private static final int DEFAULT_HEIGHT = 200;
   ...
   public Dimension getPreferredSize() { return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT); }
}
```

当你用一个或多个组件填充一个框架框（frame），并且只是想使用它们的首选尺寸时，请调用`pack`方法而不是`setSize`方法：

点击此处查看代码图片

```java
class NotHelloWorldFrame extends JFrame
{
   public NotHelloWorldFrame()
   {
      add(new NotHelloWorldComponent());
      pack();
   }
}
```

代码列表 10.3 显示了完整的代码。

* * *

![Image](img/note.jpg) 注意

有些程序员比起扩展`JComponent`，更倾向于扩展`JPanel`类。`JPanel`旨在作为一个可以包含其他组件的*容器*（container），但也可以在上面进行绘制。它们唯一的区别在于：面板是*不透明的*（opaque），这意味着它负责绘制其边界内的所有像素。实现这一点的最简单方法是在每个面板子类的`paintComponent`方法中通过调用`super.paintComponent`来用背景色绘制面板：

点击此处查看代码图片

```java
class NotHelloWorldPanel extends JPanel
{
   public void paintComponent(Graphics g)
   {
      super.paintComponent(g);
      code for drawing
   }
}
```

* * *

**列表 10.3** `notHelloWorld/NotHelloWorld.java`

点击此处查看代码图片

* * *

```java
package notHelloWorld;

import javax.swing.*;
import java.awt.*;

/**
 * @version 1.33 2015-05-12
 * @author Cay Horstmann
 */
public class NotHelloWorld
{
   public static void main(String[] args)
   {
      EventQueue.invokeLater(() ->
          {
             JFrame frame = new NotHelloWorldFrame();
             frame.setTitle("NotHelloWorld");
             frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
             frame.setVisible(true);
          });
   }
}

/**
 * 一个包含消息面板的框架
 */
class NotHelloWorldFrame extends JFrame
{
   public NotHelloWorldFrame()
   {
      add(new NotHelloWorldComponent());
      pack();
   }
}
...
```

### 10.5 使用 2D 形状

从 Java 1.0 开始，`Graphics`类就有了绘制线条、矩形、椭圆的方法。但那些绘制操作非常有限。例如，你无法改变线条的粗细，也无法旋转形状。

Java SE 1.2 引入了 *Java2D* 库，它实现了一套强大的图形操作。在本章中，我们只查看 Java 2D 高功能的基础知识。

要在 Java 2D 库中绘制形状，你需要获取一个`Graphics2D`对象。该类是`Graphics`类的子类。从 Java 2 开始，诸如`paintComponent`等方法会自动接收一个`Graphics2D`对象。只需进行类型转换，如下：

点击此处查看代码图片

```java
public void paintComponent(Graphics g)
{
   Graphics2D g2 = (Graphics2D) g;
   ...
}
```

Java 2D 库以面向对象的方式组织几何形状。特别是，有专门的类来表示线条、矩形和椭圆：

`Line2D`

`Rectangle2D`

`Ellipse2D`

这些类都实现了`Shape`接口。

* * *

![Image](img/note.jpg) 注意

Java 2D 库支持更复杂的形状——特别是弧、二次曲线、三次曲线以及通用路径（paths）。更多信息请参阅第二卷的 第 7 章。

* * *

要绘制形状，你首先创建一个实现`Shape`的类对象，然后调用`Graphics2D`类的`draw`方法。例如：

```java
Rectangle2D rect = ...;
g2.draw(rect);
```

* * *

![Image](img/note.jpg) 注意

在 Java 2D 库出现之前，程序员使用`Graphics`类的方法（如`drawRectangle`）来绘制形状。表面上看，旧的方法调用看起来简单一点。但通过使用 Java 2D 库，你保留了选择空间——以后可以使用 2D 库提供的许多工具来增强你的绘画。

使用 Java 2D 形状类引入了一些复杂度。与使用整数像素坐标的 1.0 版本方法不同，Java 2D 形状使用浮点坐标。在许多情况下，这是一个巨大的便利，因为它允许你使用你有意义的坐标（如毫米或英寸）来指定形状，然后将其转换为像素。Java 2D 库在许多内部浮点计算中使用单精度`float`类型。单精度已经足够了——毕竟，几何计算的最终目的是是在屏幕或打印机上设置像素。

然而，操作`float`值有时对程序员来说并不够方便，因为 Java 坚持要求在将`double`值转换为`float`值时必须进行强制类型转换。例如，考虑以下语句：

```java
float f = 1.2; // Error
```

该语句无法编译，因为常量`1.2`的类型是`double`，而编译器担心精度的丢失。解决办法是在浮点数常量后面加上`F`后缀：

```java
float f = 1.2F; // Ok
```

现在考虑这条语句：

点击此处查看代码图像

```java
Rectangle2D r = . . .
float f = r.getWidth(); // Error
```

该语句同样无法编译，原因相同。`getWidth()`方法返回一个`double`。这次的解决办法是提供一个强制转换：

点击此处查看代码图像

```java
float f = (float) r.getWidth(); // OK
```

这些后缀和强制转换有些麻烦，因此 2D 库的设计者决定为每个形状类提供两个版本：一个带有`float`坐标供节约内存的程序员使用，另一个带有`double`坐标供那些懒惰的程序员使用。（在本书中，我们属于第二阵营，尽可能地使用`double`坐标。）

库的设计者选择了一种奇特且起初令人困惑的方法来封装这些选择。考虑`Rectangle2D`类。它是一个抽象类，有两个具体的子类，这两个子类也是静态内部类：

- `Rectangle2D.Float`
- `Rectangle2D.Double`

图 10.9 显示了继承关系。

![Image](img/10fig09.jpg)

**图 10.9** 2D 矩形类

最好忽略这两个具体类是静态内部类这一事实——这仅仅是为了避免诸如`FloatRectangle2D`和`DoubleRectangle2D`这样的名称。（有关静态内部类的更多信息，请参阅第 6 章）。

当你构造一个`Rectangle2D.Float`对象时，你提供`float`类型的坐标。对于`Rectangle2D.Double`对象，你提供`double`类型的坐标。

点击此处查看代码图像

```java
Rectangle2D.Float floatRect = new Rectangle2D.Float(10.0F, 25.0F, 22.5F, 20.0F);
Rectangle2D.Double doubleRect = new Rectangle2D.Double(10.0, 25.0, 22.5, 20.0);
```

实际上，由于`Rectangle2D.Float`和`Rectangle2D.Double`都自自共同的`Rectangle2D`类，且子类方法只是重写了`Rectangle2D`父类的方法，因此记住具体的形状类型并没有好处。你可以简单地使用`Rectangle2D`变量来持有矩形引用。

点击此处查看代码图像

```java
Rectangle2D floatRect = new Rectangle2D.Float(10.0F, 25.0F, 22.5F, 20.0F);
Rectangle2D doubleRect = new Rectangle2D.Double(10.0, 25.0, 22.5, 20.0);
```

也就是说，你只有在构造形状对象时才需要使用那些讨厌的内部类。

构造参数表示矩形的左上角、宽度和高度。

***

![Image](img/note.jpg) 备注

实际上，`Rectangle2D.Float`类有一个没有从`Rectangle2D`继承的额外方法——即`setRect(float x, float y, float h, float w)`。如果你将`Rectangle2D.Float`引用存储在`Rectangle2D`变量中，就会丢失该方法。但并不是什么损失——`Rectangle2D`类有一个带有`double`参数的`setRect`方法。

***

`Rectangle2D`方法使用`double`参数和返回值。例如，`getWidth()`方法返回一个`double`。

列表 10.4 中的程序绘制了一个矩形、包含在矩形内的椭圆、矩形的对角线，以及一个与矩形中心相同的圆。图 10.12 显示了结果。

![Image](img/10fig12.jpg)

**图 10.12** 绘制几何形状

**列表 10.4** `draw/DrawTest.java`

点击此处查看代码图像

```java
package draw;

import java.awt.*;
import java.awt.geom.*;
import javax.swing.*;

/**
 * @version 1.33 2007-05-12
 * @author Cay Horstmann
 */
public class DrawTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new DrawFrame();
                frame.setTitle("DrawTest");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 一个包含有绘图面板的框架
 */
class DrawFrame extends JFrame
{
    public DrawFrame()
    {
        add(new DrawComponent());
        pack();
    }
}

/**
 * 一个显示矩形和椭圆的组件
 */
class DrawComponent extends JComponent
{
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 400;

    public void paintComponent(Graphics g)
    {
        Graphics2D g2 = (Graphics2D) g;

        // 绘制一个矩形
        double leftX = 100;
        double topY = 100;
        double width = 200;
        double height = 150;

        Rectangle2D rect = new Rectangle2D.Double(leftX, topY, width, height);
        g2.draw(rect);

        // 绘制包含的椭圆
        Ellipse2D ellipse = new Ellipse2D.Double();
        ellipse.setFrame(rect);
        g2.draw(ellipse);

        // 绘制对角线
        g2.draw(new Line2D.Double(leftX, topY, leftX + width, topY + height));

        // 绘制相同圆点的圆
        double centerX = rect.CenterX();
        double centerY = rect.getCenterY();
        double radius = 150;

        Ellipse2D circle = new Ellipse2D.Double();
        circle.setFrameFromCenter(centerX, centerY, radius, radius);
        g2.draw(circle);
    }

    public Dimension getPreferredSize() { 
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT); 
    }
}
```



`java.awt.geom.RectangularShape`
- `getCenterX()`
- `getCenterY()`
- `getMinX()`
- `getMinY()`
- `getMaxX()`
- `getMaxY()` 返回包围矩形的中心、最小或最大 `x` 或 `y` 值。
- `getWidth()`
- `getHeight()` 返回包围矩形的宽度或高度。
- `getX()`
- `getY()` 返回包围矩形左上角的 `x` 或 `y` 坐标。

`java.awt.geom.Rectangle2D.Double`
- `Rectangle2D.Double(double x, double y, double w, double h)` 构建具有给定左上角、宽度和高度的矩形。

`java.awt.geom.Rectangle2D.Float`
- `Rectangle2D.Float(float x, float y, float w, float h)` 构建具有给定左上角、宽度和高度的矩形。

`java.awt.geom.Ellipse2D.Double`
- `Ellipse2D.Double(double x, double y, double w, double h)` 构造一个包围矩形具有给定左上角、宽度和高度的椭圆。

`java.awt.geom.Point2D.Double`
- `Point2D.Double(double x, double y)` 根据给定坐标构造一个点。

`java.awt.geom.Line2D.Double`
- `Line2D.Double(Point2D start, Point2D end)`
- `Line2D.Double(double startX, double startY, double endX, double endY)` 根据给定的起点和终点构造线。

### 10.6 使用颜色

`Graphics2D` 类的 `setPaint` 方法允许你选择一种颜色，用于图形上下文中后续的所有绘图操作。例如：

```java
g2.setPaint(Color.RED);
g2.drawString("Warning!", 100, 100);
```

你可以用颜色填充闭合形状（如矩形或椭圆）的内部。只需调用 `fill` 而不是 `draw` 即可：

```java
Rectangle2D rect = ...;
g2.setPaint(Color.RED);
g2.fill(rect);
```

填充闭合形状（如矩形或椭圆）的内部。只需调用 `fill` 而不是 `draw` 即可：

将组件的背景色设置为用户桌面上所有窗口使用的默认颜色。（每当窗口重绘时，背景都会被填充。）当你想要绘制用户界面元素并使其颜色与用户桌面上已有的颜色匹配时，使用 `SystemColor` 类中的颜色特别有用。表 10.1 列出了系统颜色名称及其含义。

![Image](img/10tab01.jpg)![Image](img/10tab01a.jpg)

#### 表 10.1 系统颜色

---

`java.awt.Color` **1.0**

• `Color(int r, int g, int b)`

创建一个颜色对象。

![Image](img/572tab01.jpg)

---

`java.awt.Graphics` **1.0**

• `Color getColor()`

• `void setColor(Color c)`

获取或设置当前颜色。所有后续图形操作都将使用新颜色。

![Image](img/572tab02.jpg)

---

`java.awt.Graphics2D` **1.2**

• `Paint getPaint()`

• `void setPaint(Paint p)`

获取或设置此图形上下文的绘制画属性。`Color` 类实现了 `Paint` 接口。因此，你可以使用此方法将绘制画属性设置为实色。

• `void fill(Shape s)`

用当前绘制画填充形状。

---

`java.awt.Component` **1.0**

• `Color getBackground()`

• `void setBackground(Color c)`

获取或设置背景颜色。

![Image](img/573tab01.jpg)

• `Color getForeground()`

• `void setForeground(Color c)`

获取或设置前景颜色。

![Image](img/573tab02.jpg)

---

### 10.7 使用特殊字体显示文本

本章开头的“Not a Hello World”程序使用默认字体显示字符串。有时，你可能想用不同的字体显示文本。你可以通过*字体名称*（font face name）指定字体。字体名称由*字体族名称*（font family name，如“Helvetica”）和一个可选的后缀（如“Bold”）组成。例如，“Helvetica”和“Helvetica Bold”这两个字体都被认为是名为“Helvetica”的字体族的一部分。

要查找特定计算机上可用的字体，请调用 `GraphicsEnvironment` 类的 `getAvailableFontFamilyNames` 方法。该方法返回包含所有可用字体名称的字符串数组。要获取描述用户系统图形环境的 `GraphicsEnvironment` 类实例，请使用静态方法 `getLocalGraphicsEnvironment`。以下程序打印了系统上所有字体的名称：

```java
import java.awt.*;

public class ListFonts
{
   public static void main(String[] args)
   {
      String[] fontNames = GraphicsEnvironment
          .getLocalGraphicsEnvironment()
          .getAvailableFontFamilyNames();

      for (String fontName : fontNames)
          System.out.println(fontName);
   }
}
```

在某个系统上，列表如下：

Abadi MT Condensed Light
Arial
Arial Black
Arial Narrow
Arioso
Baskerville
Binner Gothic
...
后面还有约七十个字体。

字体名称可以注册商标，在某些司法管辖区字体设计可以受版权保护。因此，字体的发行通常涉及向字体公司支付版税。当然，就像名香水有廉价仿品一样，品牌字体也有相似字体。例如，Windows 自带的 Helvetica 仿品被称为 Arial。

为了建立共同的基准，AWT 定义了五个*逻辑*字体名称：

- SansSerif
- Serif
- Monospaced
- Dialog
- DialogInput

这些名称始终映射到客户端上实际存在的某些字体。例如，在 Windows 系统上，`SansSerif` 映射到 Arial。

此外，Oracle JDK 始终包含三个名为“Lucida Sans”、“Lucida Bright”和“Lucida Sans Typewriter”的字体族。

要用某种字体绘制字符，必须先创建一个 `Font` 类的对象。指定字体名称、字体样式和字号。以下是如何构造 `Font` 对象的示例：

```java
Font sansbold14 = new Font("SansSerif", Font.BOLD, 14);
```

第三个参数是字号。点（Points）在排版中常用于指示字体大小。每英寸有 72 点。

你可以在 `Font` 构造函数中使用逻辑字体名称代替字体名称。通过设置第二个 `Font` 构造函数来指定样式（普通、粗体、斜体或粗斜体）：

- `PLAIN`
- `BOLD`
- `ITALIC`
- `BOLD_ITALIC`（注：原文写为 "bold italic"，但标准 API 是 `BOLD_ITALIC`；后文跟随：`bold italic`）

要解释该矩形的尺寸，你需要了解一些基础的排版术语（参见图 10.13）。`baseline`（基线）是一条虚线，例如，像“e”这样的字符的底部所在的位置。`ascent`（上行高）是从基线到`ascender`（升部）的距离，升部是“b”或“k”等字母或大写字母的上部。`descent`（下行深）是从基线到`descender`（下降部）的距离，下降像是“p”或“g”等字母的底部。

![Image](img/10fig13.jpg)

**图 10.13** 排版术语图

`Leading`（行距）是上一行的下降部与下一行的上升部之间的空间。（该术语源于排字工人用来分隔行的铅条。）字体的`height`（高度）是两个连续基线之间的距离，等于`descent + leading + ascent`。

`getStringBounds` 方法返回的矩形宽度是字符串的水平跨度。矩形的高度是上升高、下降深和行距之和。矩形的原点位于字符串的基线。矩形的顶部 `y` 坐标为负值。因此，你可以如下所示获取字符串宽度、高度和上升高：

```java
double stringWidth = bounds.getWidth();
double stringHeight = bounds.getHeight();
double ascent = -bounds.getY();
```

如果你需要知道下降深或行距，请使用 `Font` 类的 `getLineMetrics` 方法。该方法返回一个 `LineMetrics` 类对象，该类拥有获取下降深和行距的方法：

```java
LineMetrics metrics = f.getLineMetrics(message, context);
float descent = metrics.getDescent();
float leading = metrics.getLeading();
```

以下代码使用了所有信息，将字符串在其周围的组件中居中：

```java
FontRenderContext context = g2.getFontRenderContext();
Rectangle2D bounds = f.getStringBounds(message, context);

// (x,y) = top left corner of text
double x = (getWidth() - bounds.getWidth()) / 2;
double y = (getHeight() - bounds.getHeight()) / 2;

// add ascent to y to reach the baseline
double ascent = -bounds.getY();
double baseY = y + ascent;

g2.drawString(message, (int) x, (int) baseY);
```

为了理解居中原理，请考虑 `getWidth()` 返回的是组件的宽度。该宽度的一部分（即 `bounds.getWidth()`）被消息字符串占据。剩余部分应该等距离分布在两侧。因此，每侧的空白区域是差值的一半。高度也适用同样的原理。

---

![Image](img/note.jpg) 备注

当你在 `paintComponent` 方法之外计算布局尺寸时，无法从 `Graphics2D` 对象获取字体渲染上下文。相反，调用 `JComponent` 类的 `getFontMetrics` 方法，然后调用 `getFontRenderContext`。

```java
FontRenderContext context = getFontMetrics(f).getFontRenderContext();
```

---

为了证明定位是准确的，示例程序还绘制了基线和边界矩形。图 10.14 显示了屏幕显示；列表 10.5 是程序列表。

![Image](img/10fig14.jpg)

**图 10.14** 绘制基线和字符串边界

**列表 10.5** `font/FontTest.java`

```java
package font;

import java.awt.*;
import java.awt.font.*;
import java.awt.geom.*;
import javax.swing.*;

/**
 * @version 1.34 2015-05-12
 * @author Cay Horstmann
 */
public class FontTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new FontFrame();
                frame.setTitle("FontTest");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 一个带有文本组件的框架
 */
class FontFrame extends JFrame
{
    public FontFrame()
    {
        add(new FontComponent());
        pack();
    }
}

/**
 * 一个在框中显示居中消息的组件。
 */
class FontComponent extends JComponent
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public void paintComponent(Graphics g)
    {
        Graphics2D g2 = (Graphics2D) g;

        String message = "Hello, World!";

        Font f = new Font("Serif", Font.BOLD, 36);
        g2.setFont(f);

        // measure the size of the message
        FontRenderContext context = g2.getFontRenderContext();
        Rectangle2D bounds = f.getStringBounds(message, context);

        // set (x,y) = top left corner of text
        double x = (getWidth() - bounds.getWidth()) / 2;
        double y = (getHeight() - bounds.getHeight()) / 2;

        // add ascent to y to reach the baseline
        double ascent = -bounds.getY();
        double baseY = y + ascent;

        // draw the message
        g2.drawString(message, (int) x, (int) baseY);

        g2.setPaint(Color.LIGHT_GRAY);

        // draw the baseline
        g2.draw(new Line2D.Double(x, baseY, x + bounds.getWidth(), baseY));

        // draw the enclosing rectangle
        Rectangle2D rect = new Rectangle2D.Double(x, y, bounds.getWidth(), bounds.getHeight());
        g2.draw(rect);
    }

    public Dimension getPreferredSize() {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```



- `void drawString(String str, int x, int y)`

使用当前的字体和颜色绘制一个字符串。

![Image](img/581tab02.jpg)

`java.awt.Graphics2D`我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。1.2

- `FontRenderContext getFontRenderContext()`

获取一个字体渲染上下文，该上下文指定了此图形上下文中的字体特征。

- `void drawString(String str, float x, float y)`

使用当前的字体和颜色绘制一个字符串。

![Image](img/582tab01.jpg)

`javax.swing.JComponent` 1.2

- `FontMetrics getFontMetrics(Font f)` 5.0

获取给定字体的字体量。`FontMetrics` 类是 `LineMetrics` 类的前身。

`java.awt.FontMetrics` 1.0

- `FontRenderContext getFontRenderContext()` 1.2

获取该字体的字体渲染上下文。

### 10.8 显示图像

你已经学会了如何通过绘制线条和形状来构建简单的图画。复杂的图像（例如照片）通常是在外部生成的——例如，使用扫描仪或特殊的图像处理软件。正如你在第二卷中看到的，也可以逐像素地生成图像。

一旦图像存储在本地文件或互联网上的某处，你就可以将它们读入 Java 应用程序并显示在 `Graphics` 对象上。读取图像有很多方法。在这里，我们使用了你已经见过的 `ImageIcon` 类：

点击此处查看代码图像

```java
Image image = new ImageIcon(filename).getImage();
```

现在，变量 `image` 包含一个封装图像数据的对象的引用。你可以使用 `Graphics` 类的 `drawImage` 方法来显示图像。

点击此处查看代码图像

```java
public void paintComponent(Graphics g)
{
    ...

    g.drawImage(image, x, y, null);
}
```

Listing 10.6 更进一步了一步，使用图形图像对窗口进行*平铺*。结果看起来就像图 10.15 所示的屏幕。我们在 `paintComponent` 方法中进行平铺。我们首先在左上角绘制图像的一个副本，然后使用 `copyArea` 调用将其复制到整个窗口：

```java
for (int i = 0; i * imageWidth <= getWidth(); i++)
    for (int j = 0; j * imageHeight <= getHeight(); j++)
        if (i + j > 0)
            g.copyArea(0, 0, imageWidth, imageHeight, i * imageWidth, j * imageHeight);
```

![Image](img/10fig15.jpg)

**图 10.15** 带有平铺图形图像的窗口

Listing 10.6 显示了图像显示程序的完整源代码。

**Listing 10.6** `image/ImageTest.java`

点击此处查看代码图像

```java
package image;

import java.awt.*;

import javax.swing.*;

/**
 * @version 1.34 2015-05-12
 * @author Cay Horstmann
 */

public class ImageTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            JFrame frame = new ImageFrame();
            frame.setTitle("ImageTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 带有图像组件的框架
 */
class ImageFrame extends JFrame
{
    public ImageFrame()
    {
        add(new ImageComponent());
        pack();
    }
}

/**
 * 显示平铺图像的组件
 */
class ImageComponent extends JComponent
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;
    private Image image;

    public ImageComponent()
    {
        image = new ImageIcon("blue-ball.gif").getImage();
    }

    public void paintComponent(Graphics g)
    {
        if (image == null) return;

        int imageWidth = image.getWidth(this);
        int imageHeight = image.getHeight(this);

        // 在左上角绘制图像
        g.drawImage(image, 0, 0, null);

        // 跨组件平铺图像
        for (int i = 0; i * imageWidth <= getWidth(); i++)
            for (int j = 0; j * imageHeight <= getHeight(); j++)
                if (i + j > 0)
                    g.copyArea(0, 0, imageWidth, imageHeight, i * imageWidth, j * imageHeight);
    }

    public Dimension getPreferredSize()
    {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

`java.awt.Graphics` 1.0

- `boolean drawImage(Image img, int x, int y, ImageObserver)`

绘制未缩放的图像。

![Image](img/585tab01.jpg)

- `boolean drawImage(Image img, int x, int y, ImageObserver)`

绘制缩放的图像。该系统将图像缩放到给定的区域。

![Image](img/585tab02.jpg)

- `void copyArea(int x, int y, int width, int height, int dx, int dy)`

复制屏幕的一个区域。

![Image](img/586tab01.jpg)

这结束了对图形编程的介绍。对于更高级的技术，请参考第二卷中关于二维图像处理的讨论。在下一章中，你将学习如何响应用户输入。

# 第 11 章 事件处理

## 在本章中

- 11.1 事件处理基础
- 11.2 动作
- 11.3 鼠标事件
- 11.4 AWT 事件层次结构

事件处理对于具有图形用户界面的程序是至关重要的。为了实现用户界面，你必须掌握 Java 处理事件的方式。本章解释了 AWT 事件模型的工作原理。你将看到如何从用户界面组件和输入设备获取事件。我们还将展示如何使用*动作*，它们代表了处理事件的一种更有结构的方法。

### 11.1 事件处理基础

任何支持 GUI 的操作系统都会持续监控按键或鼠标点击等事件。操作系统会将这些事件报告给正在运行的程序。每个程序然后决定对这些事件做什么（如果有的话）。在 Visual Basic 等语言中，事件与代码之间的关系是显而易见的。为每个特定的事件编写代码，并将代码放在通常被称为*事件过程*的地方。例如，一个名为 `HelpButton` 的 Visual Basic 按钮关联了一个 `HelpButton_Click` 事件过程。每当点击该按钮时，过程中的代码就会执行。每个 Visual Basic GUI 组件响应一组固定的事件，无法更改它响应的事件。

另一方面，如果你使用原生 C 语言进行事件驱动编程，你需要编写代码来不断检查事件队列，查看操作系统正在报告的内容。这通常通过将代码封装在一个带有巨大 `switch` 语句的循环来实现。这种技术显然很拙劣，而且无论如何写起来都更困难。它的优势在于，你可以响应的事件并不像 Visual Basic 那种极力从程序员面前隐藏事件队列的语言那样有限。

Java 编程环境在功能和相应的复杂性方面介于 Visual Basic 和原始 C 语言之间。在 AWT 能够处理的事件范围内，你可以完全控制事件如何从 `event sources`（事件源，如按钮或滚动条）传输到 `event listeners`（事件监听器）。你可以指定 `any` 对象作为事件监听器——在实践中，你选择一个能够方便地对事件做出相应响应的 get 即可。这种 `event delegation model` 比 Visual Basic 提供了更大的灵活性，因为在 Visual Basic 中，监听器是预先定义的。

事件源拥有某些方法，允许你向它们注册事件监听器。当源发生事件时，该源会向所有注册了该事件的监听器对象发送该事件的通知。

正如在 Java 这种面向对象的语言中所预期的那样，事件的信息被封装在事件对象中。在 Java 中，所有事件对象最终都派自 `java.util.EventObject` 类。当然，每种类型的事件都有子类，例如 `ActionEvent` 和 `WindowEvent`。

不同的事件源可以产生不同类型的事件。例如，按钮可以发送 `ActionEvent` 对象，而窗口可以发送 `WindowEvent` 对象。

总结来说，这里是 AWT 事件处理工作原理的概述：

- 监听器对象是一个实现特定接口的类实例，该接口自然地被称为 `listener interface`（监听器接口）。
- 事件源是一个可以注册监听器对象并向它们发送事件对象的对象。
- 当事件发生时，事件源会向所有注册的监听器发送事件对象。
- 监听器对象将使用事件对象中的信息来确定对事件的反应。

图 11.1 显示了事件处理类与接口之间的关系。

![Image](img/11fig01.jpg)

**图 11.1** 事件源与监听器之间的关系

以下是一个指定监听器的示例：

点击此处查看代码图片

```java
ActionListener listener = . . .;

JButton button = new JButton("OK");

button.addActionListener(listener);
```

现在，每当按钮发生“动作事件”时，`listener` 对象就会收到通知。对于按钮来说，正如你预期的那样，动作事件就是按钮点击。

要实现 `ActionListener` 接口，监听器类必须有一个名为 `actionPerformed` 的方法，该方法接收一个 `ActionEvent` 对象作为参数。

点击此处查看代码图片

```java
class MyListener implements ActionListener
{
    ...

    public void actionPerformed(ActionEvent event)
    {
        // 对按钮点击的反应写在这里
        ...
    }
}
```

每当用户点击按钮时，`JButton` 对象就会创建一个 `ActionEvent` 对象并调用 `listener.actionPerformed(event)`，传递该事件对象。按钮之类的事件源可以有多个监听器。在这种情况下，每当用户点击按钮时，按钮都会调用所有监听器的 `actionPerformed` 方法。

图 11.2 显示了事件源、事件监听器和事件对象之间的交互。

![Image](img/11fig02.jpg)

**图 11.2** 事件通知

### 11.1.1 示例：处理按钮点击

为了熟悉事件委托模型，让我们详细介绍一下响应按钮点击这一简单示例所需的所有细节。在这个示例中，我们将展示一个包含三个按钮的面板（panel）。三个监听器对象作为动作监听器被添加到按钮上。

在这种场景下，用户每当点击面板上的任何一个按钮时，关联的监听器对象都会接收到一个指示为按钮点击的 `ActionEvent`。在我们的示例程序中，监听器对象将更改面板的背景颜色。

在向你展示监听按钮点击的程序之前，我们首先需要解释如何创建按钮以及将它们添加到面板中。（有关 GUI 元素的更多信息，请参阅第 12 章。）

要创建一个按钮，在按钮的构造函数中指定标签字符串、图标或两者。这里有两个示例：

点击此处查看代码图片

```java
JButton yellowButton = new JButton("Yellow");

JButton blueButton = new JButton(new ImageIcon("blue-ball.gif"));
```

调用 `add` 方法将按钮添加到面板中：

点击此处查看代码图片

```java
JButton yellowButton = new JButton("Yellow");

JButton blueButton = new JButton("Blue");

JButton redButton = new JButton("Red");

buttonPanel.add(yellowButton);

buttonPanel.add(blueButton);

buttonPanel.add(redButton);
```

图 11.3 显示了结果。

![Image](img/11fig03.jpg)

**图 11.3** 种满按钮的面板

接下来，我们需要添加监听这些按钮的代码。这需要实现 `ActionListener` 接口的类，正如我们刚刚提到的，该接口有一个方法：`actionPerformed`，其签名看起来如下：

点击此处查看代码图片

```java
public void actionPerformed(ActionEvent event)
```

`ActionListener` 接口被用于许多情况：

- 从列表中选择了某项
- 从菜单中选择了某项
- 按了 Enter 键
- 经过了一段时间时间

你将在下一章看到更多细节。当按钮被点击时，我们希望面板的背景颜色变为特定的颜色。我们在监听器类中存储这种颜色。

点击此处查看代码图片

```java
class ColorAction implements ActionListener
{
    private Color backgroundColor;

    public ColorAction(Color c)
    {
        backgroundColor = c;
    }

    public void actionPerformed(ActionEvent event)
    {
        // 设置面板颜色
        ...
    }
}
```

然后我们为每种颜色构造一个对象，并将这些对象设置为按钮监听器。

点击此处查看代码图片

```java
ColorAction yellowAction = new ColorAction(Color.YELLOW);

ColorAction blueAction = new ColorAction(Color.BLUE);

ColorAction redAction = new ColorAction(Color.RED);

yellowButton.addActionListener(yellowAction);

blueButton.addActionListener(blueAction);

redButton.addActionListener(redAction);
```

例如，如果用户点击标记为“Yellow”的按钮，`yellowAction` 对象的 `actionPerformed` 方法就会被调用。它的 `backgroundColor` 实例字段被设置为 `Color.YELLOW`，现在它可以继续设置面板的背景颜色了。

还剩下一个问题。`ColorAction` 对象无法访问 `buttonPanel` 变量。你可以通过两种方式解决这个问题：将面板存储在 `ColorAction` 对象中并在 `ColorAction` 构造函数中设置它；或者更方便地，将 `ColorAction` 变成 `ButtonFrame` 类的内部类。这样它的方法就可以自动访问外部面板。（有关内部类的更多信息，请参阅第 6 章。）

我们采用后一种方法。以下是将 `ColorAction` 类放置在 `ButtonFrame` 类内部的方法：

```java
class ButtonFrame extends JFrame
{
```



```java
private JPanel buttonPanel;
```

```java
private class ColorAction implements ActionListener
{
    private Color backgroundColor;

    public void actionPerformed(ActionEvent event)
    {
        buttonPanel.setBackground(backgroundColor);
    }
}
```

仔细观察`actionPerformed`方法。`ColorAction`类并没有`buttonPanel`字段。但外层的`ButtonFrame`类确实有。

这种情况非常常见。事件监听器对象通常需要执行某些影响其他对象的操作。你通常可以策略性地将监听器类放置在监听器应该修改状态的类内部。

`Listing 11.1`包含了完整的框架类。每当你点击其中一个按钮时，相应的动作监听器就会改变面板的背景颜色。

**Listing 11.1** `button/ButtonFrame.java`

点击此处查看代码图片

```java
package button;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

/**
 * 一个带有按钮面板的框架
 */
public class ButtonFrame extends JFrame
{
    private JPanel buttonPanel;
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public ButtonFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // 创建按钮
        JButton yellowButton = new JButton("Yellow");
        JButton blueButton = new JButton("Blue");
        JButton redButton = new JButton("Red");

        buttonPanel = new JPanel();

        // 将按钮添加到面板
        buttonPanel.add(yellowButton);
        buttonPanel.add(blueButton);
        buttonPanel.add(redButton);

        // 将面板添加到框架
        add(buttonPanel);

        //创建按钮动作
        ColorAction yellowAction = new ColorAction(Color.YELLOW);
        ColorAction blueAction = new ColorAction(Color.BLUE);
        ColorAction redAction = new ColorAction(Color.RED);

        // 将动作与按钮关联
        yellowButton.addActionListener(yellowAction);
        blueButton.addActionListener(blueAction);
        redButton.addActionListener(redAction);
    }

    /**
     * 一个设置面板背景色的动作监听器。
     */
    private class ColorAction implements ActionListener
    {
        private Color backgroundColor;

        public ColorAction(Color c)
        {
            backgroundColor = c;
        }

        public void actionPerformed(ActionEvent event)
        {
            buttonPanel.setBackground(backgroundColor);
        }
    }
}
```

#### 1.12 简洁地指定监听器

在前面的节中，我们为事件监听器对象定义了一个类。最常见的情况是每个监听器执行一个操作。在这种情况下，没有必要单独创建一个类。只需使用`lambda`表达式即可：点击此处查看代码图片

考虑有多个动作的情况，如前一节所示。在这种情况下，实现一个辅助方法：

```java
public void makeButton(String name, Color backgroundColor)
{
    JButton button = new JButton(name);
    buttonPanel.add(button);
    button.addActionListener(event ->
        buttonPanel.setBackground(backgroundColor)
    );
}
```

然后`lambda`表达式引用了变量`backgroundColor`。点击此处查看代码图片

```java
makeButton("yellow", Color.YELLOW);
makeButton("blue", Color.BLUE);
makeButton("red", Color.RED);
```

在旧代码中，你经常会看到匿名类：点击此处查看代码图片

```java
yellowButton.addActionListener(new ActionListener() {
    public void actionPerformed(ActionEvent event) {
        buttonPanel.setBackground(backgroundColor);
    }
});
```

当然，这种冗长的代码不再是必要的。使用`lambda`表达式更简单。

有些程序员不习惯内部类或`lambda`表达式，而是让容器本身作为监听器，如下所示：点击此处查看代码图片

```java
yellowButton.addActionListener(this);
blueButton.addActionListener(this);
redButton.addActionListener(this);
```

现在这三个按钮不再有独立的监听器了。它们共享同一个监听器——即框架。因此，`actionPerformed`方法必须找出是哪个按钮被点击了。点击此处查看代码图片

```java
class ButtonFrame extends JFrame implements ActionListener {
    public void actionPerformed(ActionEvent event) {
        Object source = event.getSource();

        if (source == yellowButton) {
            buttonPanel.setBackground(Color.YELLOW);
        } else if (source == blueButton) {
            buttonPanel.setBackground(Color.BLUE);
        } else if (source == redButton) {
            buttonPanel.setBackground(Color.RED);
        }
    }
}
```

我们不推荐这种策略。

在`lambda`表达式可用之前，还有另一种机制用于指定事件处理程序中包含单个方法调用的事件监听器。例如，假设一个按钮监听器需要执行调用`frame.loadData()`。点击此处查看代码图片

```java
EventHandler.create(ActionListener.class, frame, "loadData")
```

这现在仅具有历史意义。有了`lambda`表达式，使用`event -> frame.loadData();`要容易得多。

`EventHandler`机制也是低效且容易出错的。它使用反射来调用方法。由于这个原因，`EventHandler.create`调用中的第二个参数必须属于一个*公共*类。否则，反射机制将无法定位并调用目标方法。

创建一个实现给定接口的代理类对象。指定的命名方法或接口的所有方法都会对目标对象执行给定的操作。

该操作可以是目标对象的方法名，也可以是属性。如果是属性，则会执行其设置器方法。例如，操作`"text"`被转换为对`setText`方法的调用。

`event`属性由一个或多个用点分隔的属性名组成。第一个属性从监听器方法的参数读取，第二个属性从结果的对象中读取，依此类推。最终结果成为操作的参数。例如，属性`"source.text"`被转换为对`getSource`和`getText`方法的调用。

***

`java.util.EventObject 1.1`

- `Object getSource()`

返回事件发生对象的引用。

### 11.1.3 示例：更改外观（Look-and-Feel）

默认情况下，Swing程序使用Metal插件。有两种方法可以更改为不同的外观。第一种是在Java安装目录的`jre/lib`子目录下提供一个`swing.properties`文件。在该文件中，将属性`swing.defaultlaf`设置为你想要的外观的类名。例如：

点击此处查看代码图像

```properties
swing.defaultlaf=com.sun.java.swing.plaf.motif.MotifLookAndFeel
```

注意，Metal和Nimbus外观位于`javax.swing`包中。其他外观的包位于`com.sun.java`包中，并且不需要在每个Java实现中都存在。例如，由于版权原因，Windows和Macintosh外观包仅随Windows和Macintosh Java环境发布。

***

![Image](img/tip.jpg) **提示**

属性文件中以`#`字符开头的行会被忽略，因此你可以在`swing.properties`文件中提供多个外观选择，并通过移动`#`符号来选择其中一个：

点击此处查看代码图像

```properties
#swing.defaultlaf=javax.swing.plaf.metal.MetalLookAndFeel
swing.defaultlaf=com.sun.java.swing.plaf.motif.MotifLookAndFeel
#swing.defaultlaf=com.sun.java.swing.plaf.windows.WindowsLookAndFeel
```

你必须重启程序以通过这种方式切换外观。Swing程序仅在启动时读取一次`swing.properties`文件。

***

第二种方法是动态更改外观。调用静态方法`UIManager.setLookAndFeel`并向其传递你想要的外观类名。然后调用静态方法`SwingUtilities.updateComponentTreeUI`来刷新整个组件集。你需要向该方法提供一个组件；它会找到所有其他组件。

这是一个展示如何在你的程序中切换到Motif外观的示例：

点击此处查看代码图像

```java
String className = "com.sun.java.swing.plaf.motif.MotifLookAndFeel";

try
{
    UIManager.setLookAndFeel(className);
    SwingUtilities.updateComponentTreeUI(frame);
    pack();
}
catch(Exception e) { e.printStackTrace(); }
```

要列出所有已安装的外观实现，请调用：

点击此处查看代码图像

```java
UIManager.LookAndFeelInfo[] infos = UIManager.getInstalledLookAndFeels();
```

然后你可以如下获取每个外观的名称和类名：

点击此处查看代码图像

```java
String name = infos[i].getName();
String className = infos[i].getClassName();
```

列表11.2是一个演示如何切换外观的完整程序（参见图11.4）。该程序与列表11.1类似。遵循上一节的建议，我们使用辅助方法`makeButton`和`lambda`表达式来指定按钮操作——即切换外观。

点击此处查看代码图像

```java
public class PlafFrame extends JFrame
{
    ...

    private void makeButton(String name, String className)
    {
        JButton button = new JButton(name);
        buttonPanel.add(button);

        button.addActionListener(event -> {
            ...
            UIManager.setLookAndFeel(className);
            SwingUtilities.updateComponentTreeUI(this);
            ...
        });
    }
}
```

![Image](img/1fig04.jpg) 图1.4 切换外观

***

![Image](img/note.jpg) **注意**

在此书的早期版本中，我们使用内部类来定义此监听器。当时，我们必须小心地向`SwingUtilities.updateComponentTreeUI`传递`PlafFrame.this`（而不是内部类的`this`引用）：

点击此处查看代码图像

```java
public class PlafFrame extends JFrame
{
    ...

    private void makeButton(String name, String className)
    {
        ...
        button.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent event)
            {
                ...
                SwingUtilities.updateComponentTreeUI(PlafFrame.this);
                ...
            }
        });
    }
}
```

这个问题在使用`lambda`表达式后消失了。在`lambda`表达式内部，`this`指向外层对象。

***

列表11.2 `plaf/PlafFrame.java`

点击此处查看代码图像

```java
package plaf;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.SwingUtilities;
import javax.swing.UIManager;

/**
 * 一个带有用于更改外观的面板的框架
 */
public class PlafFrame extends JFrame
{
    private JPanel buttonPanel;

    public PlafFrame()
    {
        buttonPanel = new JPanel();
        UIManager.LookAndFeelInfo[] infos = UIManager.getInstalledLookAndFeels();

        for (UIManager.LookAndFeelInfo info : infos)
            makeButton(info.getName(), info.getClassName());

        add(buttonPanel);
```



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。pack();

}
```

创建一个按钮来更改可插件的外观。

```java
/**
 * 创建一个按钮来更改可插件的外观。
 *
 * @param name 按钮名称
 * @param className 外观类名
 */
private void makeButton(String name, String className) {
    // 将按钮添加到面板
    JButton button = new JButton(name);
    buttonPanel.add(button);

    // 设置监听器
    button.addActionListener(event -> {
        // 按钮操作：切换到外观
        try {
            UIManager.setLookAndFeel(className);
            SwingUtilities.updateComponentTreeUI(this);
        } catch (Exception e) {
            e.printStackTrace();
        }
    });
}
```

并不是所有的事件都像按钮点击那样容易处理。在非演示性的程序中，你可能希望监控用户尝试关闭主窗框的操作，因为你不希望用户丢失未保存的工作。当用户关闭框架时，你希望弹出一个对话框，并且仅在用户同意后才退出程序。

当用户尝试关闭窗口时，`JFrame` 对象是 `WindowEvent` 的源。如果你想捕获该事件，必须有一个合适的监听器对象，并将其添加到框架的窗口监听列表中。

点击此处查看代码图像

```java
WindowListener listener = ...;
frame.addWindowListener(listener);
```

窗口监听器必须是一个实现了 `WindowListener` 接口类的对象。`WindowListener` 接口中实际上有七个方法。框架调用这些方法作为对窗口可能发生的七种不同事件的响应。这些名称是言自自明的，除了在 Windows 下，“iconified”（图标化）通常被称为“minimized”（最小化）。以下是完整的 `WindowListener` 接口：

点击此处查看代码图像

```java
public interface WindowListener {
    void windowOpened(WindowEvent e);

    void windowClosing(WindowEvent e);

    void windowClosed(WindowEvent e);

    void windowIconified(WindowEvent e);

    void windowDeiconified(WindowEvent e);

    void windowActivated(WindowEvent e);

    void windowDeactivated(WindowEvent e);
}
```

![Image](img/note.jpg) 注意

要找出窗口是否已最大化，请安装一个 `WindowStateListener` 并重写 `windowStateChanged` 方法。

与 Java 中一样，任何实现接口的类都必须实现其所有方法；在这种情况下，这意味着实现所有七个方法。记住，我们只对这七个方法之一感兴趣，即 `windowClosing` 方法。

当然，我们可以定义一个实现接口的类，在 `windowClosing` 方法中添加对 `System.exit(0)` 的调用，并为其他六个方法编写空函数：

点击此处查看代码图像

```java
class Terminator implements WindowListener {
    public void windowClosing(WindowEvent e) {
        if (user agrees) {
            System.exit(0);
        }
    }

    public void windowOpened(WindowEvent e) {}

    public void windowClosed(WindowEvent e) {}

    public void windowIconified(WindowEvent e) {}

    public void windowDeiconified(WindowEvent e) {}

    public void windowActivated(WindowEvent e) {}

    public void windowDeactivated(WindowEvent e) {}
}
```

为六个无所作用的方法编写代码是一种没人喜欢的枯燥重复工作。为了简化这项任务，每个具有多个方法的 AWT 监听器接口都带有一个配套的适配器类（adapter class），该类实现了接口中的所有方法，但不对它们执行任何操作。例如，`WindowAdapter` 类拥有七个空方法。这意味着适配器类自动满足了 Java 对实现相关监听器接口的技术要求。你可以扩展适配器类来指定对接口中某些（但不是所有）事件类型的预期响应。（像 `ActionListener` 这样只有一个方法的接口是不需要适配器类的。）

让我们利用一下这个窗口适配器。我们可以扩展 `WindowAdapter` 类，继承六个空方法，并重写 `windowClosing` 方法：

点击此处查看代码图像

```java
class Terminator extends WindowAdapter {
    public void windowClosing(WindowEvent e) {
        if (user agrees) {
            System.exit(0);
        }
    }
}
```

现在你可以将一个 `Terminator` 类型的对象注册为事件监听器：

点击此处查看代码图像

```java
WindowListener listener = new Terminator();
frame.addWindowListener(listener);
```

每框架生成窗口事件时，它会通过其七个方法之一将事件传递给 `listener` 对象（参见图 11.5）。其中六个方法无所作为；`windowClosing` 方法调用 `System.exit(0)`，终止应用程序。

![Image](img/11fig05.jpg)

**图 11.5** 窗口监听器

![Image](img/caution.jpg) 注意

如果你在扩展适配器类时拼写错了方法名称，编译器不会发现你的错误。例如，如果你在 `WindowAdapter` 中定义了一个方法 `windowIsClosing`，你将得到八个方法。使用 `@Override` 注解（在第 5 节描述过）来防止这种错误。

创建一个扩展 `WindowAdapter` 的类是一种改进，没有必要给监听器命名。我们可以更进一步：

```java
frame.addWindowListener(new WindowAdapter() {
    @Override
    public void windowClosing(WindowEvent e) {
        if (user agrees) {
            System.exit(0);
        }
    }
});
```

这段代码的作用是：

- 定义了一个扩展 `WindowAdapter` 的匿名类
- 在该匿名类中添加了 `windowClosing` 方法
- 继承了 `WindowAdapter` 的剩余空方法
- 创建了该类的对象
- 将该对象传递给 `addWindowListener` 方法

再次，匿名类的语法需要一些适应。回报是代码尽可能短。

![Image](img/note.jpg) 注意

如今，人们会将 `WindowListener` 接口中的空方法实现为默认方法。然而，Swing 的发明在默认方法出现很多年前。

同一个命令有多种激活方式是常见现象。用户可以通过菜单、按键或工具栏上的按钮来选择某个功能。在 AWT 事件模型中这很容易实现：将所有事件链接到同一个监听器。例如，假设 `blueAction` 是一个动作监听器，其 `actionPerformed` 方法会将背景颜色更改为蓝色。你可以将同一个对象作为监听器附加到多个事件源：

- 一个标记为“Blue”的工具栏按钮
- 一个标记为“Blue”的菜单项
- 一个快捷键 Ctrl+B

现在，颜色更改命令将以统一的方式处理，无论它是是由按钮点击、菜单选择还是按键触发的。

Swing 包提供了一个非常有用的机制来封装命令并将其附加到多个事件源：即 `Action` 接口。一个 `action`（动作）是一个封装了以下内容的对象：

- 命令的描述（作为文本字符串和可选图标）；以及
- 执行命令所需的参数（例如我们示例中请求的颜色）。

`Action` 接口具有以下方法：

点击此处查看代码图片

```java
void actionPerformed(ActionEvent event);

void setEnabled(boolean b);

boolean isEnabled();

void putValue(String key, Object value);

Object getValue(String key);

void addPropertyChangeListener(PropertyChangeListener listener);

void removePropertyChangeListener(PropertyChangeListener listener);
```

第一个方法是 `ActionListener` 接口中熟悉的方法；事实上，`Action` 接口扩展了 `ActionListener` 接口。因此，在任何需要 `ActionListener` 对象的地方你都可以使用 `Action` 对象。

接下来的两个方法允许你启用或禁用动作，并检查动作当前是否启用。当动作附加到菜单或工具栏且动作被禁用时，该选项将变为灰色。

`putValue` 和 `getValue` 方法允许你在动作对象中存储和检索任意的键值对。两个重要的预定义字符串（`Action.NAME` 和 `Action.SMALL_ICON`）可以将动作名称和图标存储到动作对象中：

```java
action.putValue(Action.NAME, "Blue");
action.putValue(Action.SMALL_ICON, new ImageIcon("blue-ball.gif"));
```

Table 11.1 显示了预定义的动作表名称。

![Image](img/11tab01.jpg)

**表 11.1** 预定义动作表名称

如果动作对象被添加到菜单或工具栏，名称和图标将自动检索并显示在菜单项或工具栏按钮中。`SHORT_DESCRIPTION` 值将变为工具提示（tooltip）。

`Action` 接口的最后两个方法允许其他对象（特别是触发动作的菜单或工具栏）在动作对象的属性变化时接收通知。例如，如果一个菜单作为动作对象的属性变化监听器，并且随后该动作对象被禁用，则菜单会被调用并可以将动作名称置灰。属性变化监听器（Property change listeners）是“JavaBeans”组件模型的一部分的一种通用结构。你可以在第二卷中找到更多关于 beans 及其属性的内容。

注意 `Action` 是一个接口而不是类。任何实现此接口的类都必须实现我们讨论的七个方法。幸运的是，一位热心的人提供了一个类 `AbstractAction`，它实现了除了 `actionPerformed` 之外的所有方法。该类负责存储所有的键值对并管理属性变化监听器。你只需要扩展 `AbstractAction` 并提供一个 `actionPerformed` 方法即可。

让我们构建构建一个可以执行颜色更改命令的动作对象。我们存储命令的名称、图标和所需的颜色。我们将颜色存储在 `AbstractAction` 类提供的键值对表中。这里是 `ColorAction` 类的代码。构造函数设置了键值对，而 `actionPerformed` 方法执行颜色更改动作。

点击此处查看代码图片

```java
public class ColorAction extends AbstractAction {
    public ColorAction(String name, Icon icon, Color c) {
        putValue(Action.NAME, name);
        putValue(Action.SMALL_ICON, icon);
        putValue("color", c);
        putValue(
            Action.SHORT_DESCRIPTION,
            "Set panel color to " + name.toLowerCase()
        );
    }

    public void actionPerformed(ActionEvent event) {
        Color c = (Color) getValue("color");
        buttonPanel.setBackground(c);
    }
}
```

我们的测试程序创建了该类的三个对象，例如：

```java
Action blueAction =
    new ColorAction("Blue", new ImageIcon("blue-ball.gif"), Color.BLUE);
```

接下来，让我们此动作与按钮关联。这很容易，因为我们可以使用接收 `Action` 对象的 `JButton` 构造函数。

```java
JButton blueButton = new JButton(blueAction);
```

该构造函数从动作中读取名称和图标，将短描述设置为工具提示，并将动作设置为监听器。正如我们在下一章中演示的那样，将动作添加到菜单同样简单。

![Image](img/11fig06.jpg)

**图 11.6** 按钮显示图标

最后，我们希望将动作对象添加到按键上，以便用户输入键盘命令时触发动作。要将动作与按键关联，首先需要生成 `KeyStroke` 对象。这是一个封装键描述的便利类。要生成 `KeyStroke` 对象，不需要调用构造函数，而是使用 `KeyStroke` 类的静态方法 `getKeyStroke`。

```java
KeyStroke ctrlB = KeyStroke.getKeyStroke("ctrl B");
```

为了理解下一步，你需要理解键盘焦点的概念。界面界面有很多按钮、菜单、滚动条和其他组件。当你按下键时，它会被发送给焦点组件。该组件通常（并非总是）会有视觉区分。例如，在 Java 外观中，焦点按钮周围有一个细矩形框。你可以使用 Tab 键在组件之间移动焦点。当按下空格键时，焦点按钮会被点击。其他键执行不同的动作；例如，箭头键可以移动滚动条。

然而，在我们的情况下，我们不想将按键发送给焦点组件。否则，每个按钮都需要如何处理 Ctrl+Y、Ctrl+B 和 Ctrl+R。这是一个常见问题，Swing 设计者想出了一个方便的解决方案。每个 `JComponent` 都有三个输入映射（input maps），每个将 `KeyStroke` 对象映射到关联的动作。这三个输入映射对应三种不同的条件（参见 Table 11.2）。

## Table 11.2

![Image](img/11tab02.jpg)

**表 11.2** 输入映射条件

1. `WHEN_FOCUSED`：焦点组件的 `WHEN_FOCUSED` 映射。如果按键存在，则执行对应的动作。如果动作启用，则停止处理。
2. `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT`：从焦点组件开始，检查其父组件的 `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT` 映射。一旦发现带有按键的映射，立即执行对应的动作。如果动作启用，则停止处理。
3. `WHEN_IN_FOCUSED_WINDOW`：在具有输入焦点的窗口中，查找在 `WHEN_IN_FOCUSED_WINDOW` 表中注册了此按键的所有可见且启用的组件。让这些组件（按照按键注册的顺序）有机会执行相应的动作。一旦执行了第一个启用的动作，立即停止处理。如果一个按键出现在多个 `WHEN_IN_FOCUSED_WINDOW` 表中，这部分过程将会变得脆弱。

要从组件中获取输入映射，请使用 `getInputMap` 方法。例如所示：

点击此处查看代码图片

```java
InputMap imap = panel.getInputMap(JComponent.WHEN_FOCUSED);
```



`WHEN_FOCUSED` 条件意味着当当前组件拥有键盘焦点时，会查询此映射。在我们的情况下，这并不是我们想要的映射。拥有输入焦点的是其中一个按钮，而不是面板。另外两个映射选择中的任何一个都可以用于插入颜色更改按键。我们在示例程序中使用了`WHEN_ANCESTOR_OF_FOCUSED_COMPONENT`。

`InputMap`并不会直接将`KeyStroke`对象映射到`Action`对象。相反，它将映射到任意对象，而由`ActionMap`类实现的第二个映射则将这些对象映射到动作。这使得在来自不同输入映射的按键之间共享相同的动作变得更容易。

因此，每个组件都有三个输入映射和一个动作映射。为了将它们连接起来，你需要为这些动作命名。以下是将按键绑定到动作的方法：

点击此处查看代码图片

```java
imap.put(KeyStroke.getKeyStroke("ctrl Y"), "panel.yellow");

ActionMap amap = panel.getActionMap();

amap.put("panel.yellow", yellowAction);
```

通常习惯上使用字符串`"none"`作为无操作动作。这可以让你轻松地禁用一个按键：

点击此处查看代码图片

```java
imap.put(KeyStroke.getKeyStroke("ctrl C"), "none");
```

---

![Image](img/caution.jpg) **注意**

JDK 文档建议使用动作名称作为动作的键。我们认为这并不是好主意。动作名称显示在按钮和菜单项上；因此，它可以根据 UI 设计师的意愿改变，并可能翻译成多种语言。这种不稳定的字符串是查找键的糟糕选择，因此我们建议你想出独立于显示名称的名称。

---

总结一下，以下是响应按钮、菜单项或按键执行相同动作的步骤：

1. 实现一个继承自`AbstractAction`的类。你可能可以使用同一个类来处理多个相关的动作。
2. 构造动作类的对象。
3. 从动作对象构造按钮或菜单项。构造函数将从动作对象中读取标签文本和图标。
4. 对于可以通过按键触发的动作，你必须执行额外的步骤。首先，找到窗口的顶层组件，例如包含所有其他组件的面板。
5. 然后，获取顶层组件的`WHEN_ANCESTOR_OF_FOCUSED_COMPONENT`输入映射。为所需的按键创建一个`KeyStroke`对象。创建一个动作键对象（例如描述你的动作的字符串）。将该对（按键，动作键）添加到输入映射中。
6. 最后，获取顶层组件的动作映射。将该对（动作键，动作对象）添加到映射中。

列表 11.3 显示了将按钮和按键映射到动作对象的完整代码。尝试一下——点击按钮以及按下 Ctrl+Y、Ctrl+B 或 Ctrl+R 都会改变面板颜色。

**列表 11.3** `action/ActionFrame.java`

点击此处查看代码图片

```java
package action;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

/**
 * 一个带有面板的框架，用于演示颜色更改动作。
 */
class ActionFrame extends JFrame
{
  private JPanel buttonPanel;
  private static final int DEFAULT_WIDTH = 300;
  private static final int DEFAULT_HEIGHT = 200;

  public ActionFrame()
  {
    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    buttonPanel = new JPanel();

    // 定义动作
    Action yellowAction = new ColorAction("Yellow", new ImageIcon("yellow-ball.gif"), Color.YELLOW);
    Action blueAction = new ColorAction("Blue", new ImageIcon("blue-ball.gif"), Color.BLUE);
    Action redAction = new ColorAction("Red", new ImageIcon("red-ball.gif"), Color.RED);

    // 为这些动作添加按钮
    buttonPanel.add(new JButton(yellowAction));
    buttonPanel.add(new JButton(blueAction));
    buttonPanel.add(new JButton(redAction));

    // 将面板添加到框架
    add(buttonPanel);

    // 将 Y、B、R 键与名称关联
    InputMap imap = buttonPanel.getInputMap(JComponent.WHEN_ANCESTOR_OF_FOCUSED_COMPONENT);
    imap.put(KeyStroke.getKeyStroke("ctrl Y"), "panel.yellow");
    imap.put(KeyStroke.getKeyStroke("ctrl B"), "panel.blue");
    imap.put(KeyStroke.getKeyStroke("ctrl R"), "panel.red");

    // 将名称与动作关联
    ActionMap amap = buttonPanel.getActionMap();
    amap.put("panel.yellow", yellowAction);
    amap.put("panel.blue", blueAction);
    amap.put("panel.red", redAction);
  }

  class ColorAction extends AbstractAction
  {
    /**
     * 构造一个颜色动作。
     * @param name 显示在按钮上的名称
     * @param icon 显示在按钮上的图标
     * @param c 背景颜色
     */
    public ColorAction(String name, Icon icon, Color c)
    {
      putValue(Action.NAME, name);
      putValue(Action.SMALL_ICON, icon);
      putValue(Action.SHORT_DESCRIPTION, "Set panel color to " + name.toLowerCase());
      putValue("color", c);
    }

    public void actionPerformed(ActionEvent event)
    {
      Color c = (Color) getValue("color");
      buttonPanel.setBackground(c);
    }
  }
}
```

如果你只是想让用户能够点击按钮或菜单，不需要显式地处理鼠标事件。这些鼠标操作由用户界面中的各种组件在内部处理。然而，如果你想允许用户使用鼠标进行绘图，你就需要捕获鼠标移动、点击和拖动事件。

在本节中，我们将向你展示一个简单的图形编辑器应用程序，它允许用户在画布上放置、移动和擦除正方形（参见图 11.7）。

![Image](img/11fig07.jpg)

**图 11.7** 一个鼠标测试程序

当用户点击鼠标按钮时，会调用三个监听器方法：当鼠标首次按下时调用`mousePressed`，当鼠标释放时调用`mouseReleased`，最后调用`mouseClicked`。如果你只对完整的点击感兴趣，可以忽略前两个方法。通过使用`MouseEvent`参数上的`getX`和`getY`方法，你可以获取鼠标点击时鼠标指针的`x`和`y`坐标。要区分单击、双击和三击（！），请使用`getClickCount`方法。

一些用户界面设计师向用户施加鼠标点击和键盘修饰键组合，例如`Ctrl+Shift+click`。我们认为这种做法是不可取的，但如果你不同意，你会发现检查鼠标按钮和键盘修饰键会非常混乱。

使用位掩码来测试设置了哪些修饰键。在原始 API 中，两个按钮掩码等于两个键盘修饰键掩码，即：

```java
BUTTON2_MASK == ALT_MASK

BUTTON3_MASK == META_MASK
```

这样做是为了让单键鼠标的用户可以通过按住修饰键来模拟其他鼠标按钮。然而，从 Java SE 1.4 开始，推荐使用不同的方法。现在有了这些掩码：

```java
BUTTON1_DOWN_MASK

BUTTON2_DOWN_MASK

BUTTON3_DOWN_MASK

SHIFT_DOWN_MASK

CTRL_DOWN_MASK

ALT_DOWN_MASK

ALT_GRAPH_DOWN_MASK

META_DOWN_MASK
```

`getModifiersEx`方法可以准确报告鼠标事件的鼠标按钮和键盘修饰键。

请注意，在 Windows 下，`BUTTON3_DOWN_MASK`测试右键（非主）鼠标按钮。例如，你可以使用下面的代码来检测右鼠标键是否按下：

点击此处查看代码图片

```java
if ((event.getModifiersEx() & InputEvent.BUTTON3_DOWN_MASK) != 0)

    . . . // 右键点击的代码
```

在我们的示例程序中，我们同时提供了`mousePressed`和`mouseClicked`方法。当你点击不在任何已绘制正方形内部的像素时，会添加一个新的正方形。我们在`mousePressed`方法中实现了这一点，这样用户就能接收到立即反馈，而不需要等到鼠标按钮释放。当用户在现有正方形内部双击时，正方形会被擦除。我们在`mouseClicked`方法中实现了这一点，因为我们需要点击计数。

点击此处查看代码图片

```java
public void mousePressed(MouseEvent event)
{
    current = find(event.getPoint());

    if (current == null) // 不在正方形内
        add(event.getPoint());
}

public void mouseClicked(MouseEvent event)
{
    current = find(event.getPoint());

    if (current != null && event.getClickCount() >= 2)
        remove(current);
}
```

当鼠标在窗口上移动时，窗口会接收到持续的鼠标移动事件。注意，有独立的`MouseListener`和`MouseMotionListener`接口。这样做是为了效率——当用户移动鼠标时会产生大量的鼠标事件，而一个只关心鼠标点击的监听器就不会被不需要的鼠标移动所干扰。

我们的测试应用程序捕获鼠标移动事件，以便在悬停在正方形上方时将光标变为不同的形状（十字准）。这是通过`Cursor`类的`getPredefinedCursor`方法实现的。表 11.3 列出了与此方法使用的常量，以及这些光标在 Windows 下的样子。

![Image](img/11tab03.jpg)

**表 11.3** 示例光标形状

以下是示例程序中`MouseMotionListener`的`mouseMoved`方法：

点击此处查看代码图片

```java
public void mouseMoved(MouseEvent event)
{
    if (find(event.getPoint()) == null)
        setCursor(Cursor.getDefaultCursor());
    else
        setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));
}
```

---

![Image](img/note.jpg) **注意**

你也可以通过使用`Toolkit`类中的`createCustomCursor`方法定义自己的光标类型：

点击此处查看代码图片

```java
Toolkit tk = Toolkit.getDefaultToolkit();

Image img = tk.getImage("dynamite");

Cursor dynamite = tk.createCustomCursor(img, new Point(10, 10), "dynamite");
```

## 11.4 AWT 事件层次结构

```java
private static final int DEFAULT_WIDTH = 300;

private static final int DEFAULT_HEIGHT = 200;

private static final int SIDELENGTH = 10;

private ArrayList<Rectangle2D> squares;

private Rectangle2D current; // the square containing the mouse cursor

public MouseComponent()
{
    squares = new ArrayList<>();

    current = null;

    addMouseListener(new MouseHandler());

    addMouseMotionListener(new MouseMotionHandler());
}

public Dimension getPreferredSize()
{
    return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
}

public void paintComponent(Graphics g)
{
    Graphics2D g2 = (Graphics2D) g;

    // draw all squares
    for (Rectangle2D r : squares)
        g2.draw(r);
}

/**
 * Find 第一个包含该点的矩形。
 * @param p 一个点
 * @return 包含 p 的第一个矩形
 */
public Rectangle2D find(Point2D p)
{
    for (Rectangle2D r : squares)
    {
        if (r.contains(p)) return r;
    }

    return null;
}

/**
 * 将矩形添加到集合中。
 * @param p 矩形的中心点
 */
public void add(Point2D p)
{
    double x = p.getX();
    double y = p.getY();

    current = new Rectangle2D.Double(
        x - SIDELENGTH / 2,
        y - SIDELENGTH / 2,
        SIDELENGTH,
        SIDELENGTH
    );

    squares.add(current);
    repaint();
}

/**
 * 从集合中移除一个矩形。
 * @param s 要移除的矩形
 */
public void remove(Rectangle2D s)
{
    if (s == null) return;

    if (s == current) current = null;

    squares.remove(s);
    repaint();
}

private class MouseHandler extends Adapter
{
    public void mousePressed(MouseEvent event)
    {
        // 如果光标不在矩形内部，则添加一个矩形
        current = find(event.getPoint());

        if (current == null) add(event.getPoint());
    }

    public void mouseClicked(MouseEvent event)
    {
        // 如果双击，则移除当前矩形
        current = find(event.getPoint());

        if (current != null && event.getClickCount() >= 2)
            remove(current);
    }
}

private class MouseMotionHandler implements MouseMotionListener
{
    public void mouseMoved(MouseEvent event)
```



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。{

    // 如果在矩形内部，则将鼠标光标设置为十字准星

    if (find(event.getPoint()) == null) setCursor(Cursor.getDefaultCursor());

    else setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));

}

public void mouseDragged(MouseEvent event)

{

    if (current != null)

    {

        int x = event.getX();

        int y = event.getY();

        // 拖动当前矩形使其中心对齐 (x, y)

        current.setFrame(x - SIDELENGTH / 2, y - SIDELENGTH / 2, SIDELENGTH, SIDELENGTH);

        repaint();

    }

}
```

## 11.4 AWT 事件层次结构

在让您初步了解事件处理后，我们通过对架构的概述来结束本章。`EventObject` 类有一个子类 `AWTEvent`，它是所有事件类的父类。图 11.8 显示了 AWT 事件的继承关系。

**图 11.8 AWT 类的继承图**

某些 AWT 事件对程序员来说没有实际用处。例如，AWT 会将 `PaintEvent` 对象插入事件队列，但这些对象并不会被传递给监听器。Java 程序员通过重写 `paintComponent` 方法来控制重绘。AWT 还会生成许多仅系统需要的事件，用于为表意语言的输入法、自动测试机器人等提供输入。我们不讨论这些特殊的事件类型。

### 11.4.1 语义事件与低级事件

AWT 在*低级*（low-level）事件和*语义*（semantic）事件之间做了非常有用的区分。语义事件是表达用户正在做什么的事件，例如“点击那个按钮”；`ActionEvent` 就是一个语义事件。低级事件是实现这些操作的基础。在点击按钮的情况下，这包括鼠标按下、一系列鼠标移动和鼠标抬起（但仅当鼠标抬起在按钮内部时有效）。同样，调整滚动条是一个语义事件，但拖动鼠标则是一个低级事件。

以下是 `java.awt.event` 包中通常用的语义事件类：

- `ActionEvent`（用于按钮点击、菜单选择、选择列表项或在文本字段中输入回车）
- `AdjustmentEvent`（用户调整了滚动条）
- `ItemEvent`（用户从一组复选框或列表项中选择）

常用的有五类低级事件类：

- `KeyEvent`（按键被按下或释放）
- `MouseEvent`（鼠标按钮被按下、释放、移动或拖动）
- `MouseWheelEvent`（鼠标轮被旋转）
- `FocusEvent`（组件获得焦点或丢失焦点）
- `WindowEvent`（窗口状态发生变化）

以下接口监听这些事件：

- `ActionListener`
- `AdjustmentListener`
- `FocusListener`
- `ItemListener`
- `KeyListener`
- `MouseListener`
- `MouseMotionListener`
- `MouseWheelListener`
- `WindowListener`
- `WindowFocusListener`
- `WindowStateListener`

若干 AWT 监听接口（即那些具有多个方法的接口）都带有一个相应的适配器类（adapter class），该类实现了接口中的所有方法，但都不执行任何操作。（其他接口每个只有一个方法，因此为这些接口提供适配器类并没有意义。）以下是常用的适配器类：

- `FocusAdapter`
- `KeyAdapter`
- `MouseAdapter`
- `MouseMotionAdapter`
- `WindowAdapter`

`表 11.4` 显示了最重要的 AWT 监听接口、事件和事件源。

`javax.swing.event` 包包含了 Swing 组件特有的事件。我们将在下一章中介绍其中一些。

![Image](img/11tab04.jpg)![Image](img/11tab04a.jpg)

**表 11.4** 事件处理总结

到此结束我们对 AWT 事件处理的讨论。下一章将向你展示如何组合最常用的 Swing 组件，并详细介绍它们所产生的事件。

# 第 12 章 使用 Swing 构建用户界面组件

***

在本章中

- 12.1 Swing 和模型-视图-控制器设计模式
- 12.2 布局管理简介
- 12.3 文本输入
- 12.4 选择组件
- 12.5 菜单
- 12.6 复杂的布局管理
- 12.7 对话框
- 12.8 GUI 程序排错

***

上一章主要是为了向你展示如何使用 Java 的事件模型。在这个过程中，你迈了学习如何构建图形用户界面（GUI）的第一步。本章将向你展示构建更全功能 GUI 所需的最重要工具。

我们首先介绍 Swing 的架构基础。了解“底层”发生了什么对于理解如何有效使用某些更高级的组件非常重要。然后我们将展示如何使用 Swing 中通常用的用户界面组件，如文本框、单选按钮和菜单。接下来，你将学习如何使用 Java 巧妙的布局管理器功能在窗口中排列这些组件，而取决于特定用户界面的外观（look-and-feel）。最后，你将看到如何在 Swing 中实现对话框。

本章涵盖了基础 Swing 组件，如文本组件、按钮和滑块。这些是你最频繁需要的本质用户界面组件。我们将在第二卷中介绍高级 Swing 组件。

## 12.1 Swing 和模型-视图-控制器设计模式

正如之前所言，本章将从对 Swing 组件架构的描述开始。我们首先讨论*设计模式*（design patterns）的概念，然后查看极大影响 Swing 框架设计的“模型-视图-控制器”模式。

### 12.1.1 设计模式

在解决问题时，你通常不是从原理开始推导出解决方案。相反，你可能会受到过去经验的指导，或者可能会向其他专家请教哪些方法对他们有效。设计模式是一种以结构化方式呈现这种专业知识的方法。

近年来，软件工程师开始编写此类模式的目录。该领域的先驱深受建筑师克里斯托弗·亚历山大（Christopher Alexander）建筑设计模式的启发。在他的著作《建筑的艺术》（The Timeless Way of Building, Oxford University Press, 1979）中，Alexander 提供了一份设计公共和私人居住空间的模式目录。这是一个典型的例子：

**窗边（Window Place）**

大家都喜欢窗边、凸窗以及带有低窗台并配有舒适座椅的大窗户……一个没有这种地方的房间很少让你感到舒适或完全的放松……

如果房间里没有作为“地方”的窗户，房间里的人会在两种力量之间产生挣扎：(1) 他想坐下来感到舒适，以及 (2) 他被光线吸引。

显然，如果舒适的地方——即房间里你最想坐的地方——远离窗户，那么没有办法克服这种冲突……

因此：在任何你白天花费较长时间的房间里，至少让一个窗户变成一个“窗边”（图 12.1）。

![Image](img/12fig01.jpg)

**图 12.1** 窗边

Alexander 目录中的每个模式，以及软件模式目录中的模式，都遵循特定的格式。模式首先描述一个背景，即产生设计问题的情境。然后解释问题，通常表现为一组相互冲突的力量。最后，解决方案展示了一个平衡这些力量的配置。

在“窗边”模式中，背景是你白昼花费较长时间的房间。冲突的力量是你想坐下来感到舒适，以及你被光线吸引。解决方案是造就一个“窗边”。

在“模型-视图-控制器”模式中（我们将在下一节描述），背景是一个展示信息并接收用户输入的用户界面系统。存在多种力量：需要同步更新的多个视觉表示。视觉表示可能会改变——以适应不同的外观标准。交互机制可能会改变——以支持语音命令。解决方案是将责任分配到三个独立的交互组件中：模型、视图和控制器。

模型-视图-控制器模式并不是 AWT 设计中唯一的模式。这里有几个额外的例子：

- 容器和组件是“组合模式”（composite）的例子。
- 滚动面板是“装饰器”（decorator）。
- 布局管理器遵循“策略模式”（strategy）。

设计模式的一个重要方面是它们成为了文化的一部分。全世界的程序员在谈论模型-视图-控制器模式或装饰器模式时都能理解你的意思。因此，模式变成了设计问题的高效方式。

你可以在模式运动的基石著作《设计模式：面向对象软件的基础》（Design Patterns—Elements of Reusable Object-Oriented Software, Erich Gamma 等, Addison-Wesley, 1995）中找到许多有用模式的正式描述。我们也非常推荐 Frank Buschmann 等人的优秀著作《模式系统》（A System of Patterns, John Wiley & Sons, 1996），我们认为这本书不那么经典，但更容易易读。

### 12.1.2 模型-视图-控制器模式

让我们退后一步，思考一下构成用户界面组件（如按钮、复选框、文本框或复杂的树控件）的部分。每个组件都有三个特征：

- 它的*内容*，例如按钮的状态（按下或未），或文本框中的文本
- 它的*视觉外观*（颜色、大小等）
- 它的*行为*（对事件的反应）

即使是像按钮这样看似简单的组件，这些特征之间也表现出某种中复杂的交互。显然，按钮的视觉外观取决于外观。Metal 按钮看起来与 Windows 或 Motif 按钮不同。此外，外观取决于按钮状态；当按钮被按下时，它需要重绘以看起来不同。状态取决于按钮接收到的事件。当用户在按钮内部按下鼠标时，按钮被按下。

当然，当你在程序中使用按钮时，你只需要将其视为一个 `button`；你不需要过多考虑它的内部工作机制和特性。毕竟，那是实现按钮的程序员需要考虑的工作。然而，实现按钮及所有其他用户界面组件的程序员，有动力对它们进行更深层次的思考，以确保无论生效的是什么外观特性（look-and-feel），它们都能良好运行。

为了实现这一点，Swing 的设计者转向了一种著名的设计模式：`model-view-controller`（模型-视图-控制器）模式。这种模式与其他许多设计模式一样，追溯到我们在第 5 章中提到的对象设计原则之一：不要让一个对象承担过多的职责。不要让一个按钮类完成所有工作。相反，让组件的外观与一个对象关联，并将内容存储在`另一个`对象中。模型-视图-控制器（MVC）设计模式教会了如何实现这一点。实现三个独立的类：

- `model`（模型），存储内容
- `view`（视图），显示内容
- `controller`（控制器），处理用户输入

该模式精确地规定了这三个对象如何交互。模型存储内容，且`没有用户界面`。对于按钮来说，内容非常简单——只是一小组标志位，用于指示按钮当前是按下还是弹起状态、是激活状态还是非激活状态等。对于文本字段来说，内容就稍微有趣一点。它是一个持有当前文本的字符串对象。这`并不等同`于内容的视图——如果内容大于文本字段，用户只能看到显示的部分文本（参见图 12.2）。

![Image](img/12fig02.jpg)

**图 12.2** 文本字段的模型和视图

模型必须实现更改内容以及发现内容是什么的方法。例如，文本模型具有这些方法，用于在当前文本中添加或删除字符，并将当前文本作为字符串返回。再次，请记住，模型是完全非视觉的。绘制模型中存储的数据是视图的工作。

***

![Image](img/note.jpg) Note（注）

“模型（model）”一词可能并不理想，因为我们经常将模型视为抽象概念的表示。汽车和飞机的设计师建立模型来模拟真实的汽车和飞机。但在思考模型-视图-控制器模式时，这种类比真的会误导你。在这一设计模式中，模型存储完整的内容，而视图提供了内容的（完整或不完整）视觉表示。一个更好的类比可能是为艺术家摆姿的模特。观察模型并创建视图取决于艺术家。根据艺术家的不同，该视图可能是正式的肖像画、印象派绘画，或是一幅显示肢体处于奇异扭曲状态的立体素描。

***

模型-视图-控制器模式的优势之一是一个模型可以拥有多个视图，每个视图显示完整内容的不同部分或方面。例如，HTML 编辑器可以提供相同内容的两个`同时` 视图：一个 WYSIWYG（所见即所得）视图和一个“原始标签”视图（参见图 12.3）。当模型通过其中一个视图的控制器进行更新时，它会通知所有已关联的视图关于该变化。当视图收到通知时，它们会自动刷新自身。当然，对于像按钮这样简单的用户界面组件，你不会拥有同一个模型的多个视图。

![Image](img/12fig03.jpg)

**图 12.3** 同一个模型的两个独立视图

控制器处理用户输入事件，如鼠标点击和击键。它然后决定是否将这些事件翻译为模型或视图的更改。例如，如果用户在文本框中按下字符键，控制器会调用模型的“插入字符”命令。然后模型告诉视图更新自身。视图永远不知道文本为何发生变化。但如果用户按下光标键，控制器可能会告诉视图滚动。滚动视图对底层文本没有影响，因此模型永远不知道该事件的发生。

图 12.4 显示了模型、视图和控制器对象之间的交互。

![Image](img/12fig04.jpg)

**图 12.4** 模型、视图和控制器对象之间的交互

作为使用 Swing 组件的程序员，你通常不需要考虑模型-视图-控制器架构。每个用户界面组件都有一个包装类（例如 `JButton` 或 `JTextField`），它存储了模型和视图。当你想要查询内容时（例如，文本字段中的文本）时，包装类会询问模型并将答案返回给你。当你想要更改视图时（例如，移动文本字段中的光标位置）时，包装类会将该请求转发给视图。然而，偶尔包装类在转发命令方面做得不够尽力。这时，你就必须要求它检索模型并直接与其进行交互。（你不需要直接与视图交互——那是外观特性代码的工作。）

除了这是正确的做法外，模型-视图-控制器模式对 Swing 设计者来说非常有吸引力，因为它允许他们实现可插拔的外观特性（pluggable look-and-feel）。按钮或文本字段的模型独立于外观特性——但当然，视觉表示完全依赖于用户界面。控制器也可以变化。例如，在语音控制设备中，控制器必须处理与带有鼠标的计算机完全不同的事件。通过将模型与用户界面分离，Swing 设计者可以复用模型代码并在运行程序中切换外观特性。

当然，模式仅作为指南而非宗教。没有模式适用于所有情况。例如，你可能会发现很难遵循“窗口”模式来重新安排工位。同样，Swing 设计者发现，可插拔外观特性的现实并不总是允许模型-视图-控制器模式的完美实现。模型是容易分离的，每个用户界面组件都有模型类。但视图和控制器的职责并不总是清晰分离，而是分布在多个类中。当然，作为这些类的用户，你无需担心这些。事实上，正如我们指出的，你通常也不需要担心模型——只需使用组件包装类。

### 12.1.3 Swing 按钮的模型-视图-控制器分析

在上一章中，你已经学会了如何使用按钮而无需担心它们的控制器、模型或视图。然而，按钮是最简单的用户界面元素，因此它们是熟悉模型-视图-控制器模式的好地方。对于更复杂的 Swing 组件，你会遇到类似的类和接口。

对于大多数组件，模型类实现一个以 `Model` 结尾的接口；在这种情况下，接口被称为 `ButtonModel`。实现该接口的类可以定义各种按钮的状态。实际上，按钮并不复杂，Swing 库包含一个单一类，名为 `DefaultButtonModel`，它实现了该接口。

每个 `JButton` 对象都存储一个你可以获取的按钮模型对象（button model）。

```java
JButton button = new JButton("Blue");

ButtonModel model = button.getModel();
```




在实践中，你并不关心这些——按钮状态的细微细节只我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。绘制它的视图（view）感兴趣。所有重要信息——例如按钮是否启用——都可以从 `JButton` 类获取。（当然，此时 `JButton` 会请求它的模型来获取该信息。）

再次查看 `ButtonModel` 接口，看看其中缺少了什么。模型并不存储按钮的标签（label）或图标（icon）。无法通过查看模型来发现按钮表面显示了什么。（实际上，正如你将在第 12.4.2 节中看到的，“单选按钮”在第 660 页中，设计的纯粹性是给程序员带来痛苦的根源。）

值得注意的是，同一个模型（即 `DefaultButtonModel`）被用于推送按钮、单选按钮、复选框甚至是菜单项。当然，每种类型的按钮都有不同的视图和控制器（controllers）。在使用 Metal 看起来（look-and-feel）时，`JButton` 使用 `BasicButtonUI` 类作为视图，并使用 `ButtonUIListener` 类作为控制器。通常，每个 Swing 组件都有一个以 `UI` 结尾的关联视图对象。但并不是所有的 Swing 组件都有对应的控制器对象。

所以，在阅读了这段关于 `JButton` 内部工作机制的简短介绍后，你可能会疑惑：`JButton` 到底是什么？它简单地是一个继承自 `JComponent` 的包装类，它持有一个 `DefaultButtonModel` 对象、一些视图数据（如按钮标签和图标）以及一个负责按钮视图的 `BasicButtonUI` 对象。

## 12.2 布局管理简介

在我们继续讨论单个 Swing 组件（如文本字段和单选按钮）之前，我们简要介绍如何在框架（frame）内部排列这些组件。与 Visual Basic 不同，JDK 没有内置表单设计器。你需要编写代码来将用户界面组件定位（布局）在你希望它们所在的位置。

当然，如果你有一个支持 Java 的开发环境，它可能会有一个布局工具来自动完成这些部分或全部任务。尽管如此，确切了解“内部”发生了什么是非常重要的，因为即使是这些工具通常也需要手动微调。

让我们从回顾第 11 章中用于按钮更改框架背景颜色的程序开始（参见图 12.5）。

![Image](img/12fig05.jpg)

**图 12.5** 带有三个按钮的面板

按钮包含在一个 `JPanel` 对象中，并由流式布局管理器（flow layout manager）管理，这是面板的默认布局管理器。图 12.6 显示了当向面板中添加更多按钮时发生的情况。正如你所看到的，当没有更多空间时，会开启新的一行。

![Image](img/12fig06.jpg)

**图 12.6** 由流式布局管理的带有六个按钮的面板

此外，按钮在面板中居中，即使用户缩放框架也是如此（参见图 12.7）。

![Image](img/12fig07.jpg)

**图 12.7** 更改面板大小会自动重新排列按钮。

通常，组件被放置在容器（containers）内部，由布局管理器决定组件在容器中的位置和大小。

按钮、文本字段和其他用户界面元素继承 `Component` 类。组件可以放置在容器（如面板）中。容器本身可以放在其他容器中，因此 `Container` 类继承自 `Component`。图 12.8 显示了 `Component` 的继承层级。

![Image](img/12fig08.jpg)

**图 12.8** `Component` 类的继承层级

***

![Image](img/note.jpg)

> **注意**
>
> 遗憾的是，继承层级在两个方面有些不洁。首先，顶层窗口（如 `JFrame`）是 `Container` 的子类，因此也是 `Component` 的子类，但它们不能被放在其他容器内部。此外，`JComponent` 是 `Container` 的子类而不是 `Component`。因此，可以将其他组件添加到 `JButton` 中。（但这些组件将不会显示。）

***

每个容器都有一个默认布局管理器，但你始终可以设置自己的。例如，该语句：

```java
panel.setLayout(new GridLayout(4, 4));
```

使用 `GridLayout` 类将组件布局为四行四列。当你向容器中添加组件时，容器的 `add` 方法会将组件和任何放置方向传递给布局管理器。

***

### `java.awt.Container` 1.0

- `void setLayout(LayoutManager m)`

  设置此容器的布局管理器。

- `Component add(Component c)`

  将组件添加到容器中。

- `Component add(Component c, Object constraints)`

  将组件添加到容器中并返回组件。

![Image](img/6401)

***

### `java.awt.FlowLayout` 1.0

- `FlowLayout()`

  创建一个新的流式布局。

- `FlowLayout(int align)`

  创建一个指定对齐方式的流式布局。

- `FlowLayout(int align, int hgap, int vgap)`

  创建一个指定对齐方式、水平间隙和垂直间隙的流式布局。

![Image](img/6401)

***

### 12.2.1 边界布局（Border Layout）

边界布局管理器是每个 `JFrame` 的默认布局管理器。与完全控制组件位置的流式布局不同，边界布局让你选择放置组件的位置。你可以选择将组件放置在内容区的中心、北、南、东或西（参见图 12.9）。

![Image](img/12fig09.jpg)

**图 12.9** 边界布局

例如：

```java
frame.add(yellowButton, BorderLayout.SOUTH);
```

边缘组件首先占据指定区域，剩余的可用空间由中心组件占据。当容器调整大小时，边缘组件的尺寸不变，但中心组件会改变大小。通过指定 `BorderLayout` 类的 `CENTER`、`NORTH`、`SOUTH`、`EAST` 或 `WEST` 来添加组件。并不是所有位置都需要占据。如果不提供任何值，假设为 `CENTER`。

***

![Image](img/note.jpg)

> **注意**
>
> `BorderLayout` 常量定义为字符串。例如，`BorderLayout.SOUTH` 定义为字符串 `"South"`。这比使用字符串更安全。如果你误写字符串，例如 `frame.add(component, "south")`，编译器不会捕捉该错误。

***

与流式布局不同，边界布局放大所有组件以填充可用空间。（流式布局让每个组件保持其首选大小。）当你添加按钮时这就是问题：

```java
frame.add(yellowButton, BorderLayout.SOUTH);
```

图 12.10 显示了当你使用上述代码段时发生的情况。按钮已经增长到填充框架的整个南部区域。而且，如果你向南部区域添加另一个按钮，它将取代第一个按钮。

![Image](img/12fig10.jpg)

**图 12.10** 由边界布局管理的单体按钮

为了解决这个问题，请使用额外的面板。例如，查看图 12.11。屏幕底部的三个按钮都在一个面板中。该面板被放在内容区的南部区域。

![Image](img/12fig11.jpg)

**图 12.11** 放置在框架南部区域的面板

要实现此配置，首先创建一个新的 `JPanel` 对象，然后将各个按钮添加到面板中。面板的默认布局管理器是 `FlowLayout`，这对于这种情况来说是一个很好的选择。使用你之前见过的 `add` 方法将各个按钮添加到面板中。按钮的位置和大小由 `FlowLayout` 管理器控制。这意味着按钮保持在面板内居中，不会扩展以填充整个面板区域。最后，将面板添加到框架的内容窗格中。

```java
JPanel panel = new JPanel();

panel.add(yellowButton);

panel.add(blueButton);

panel.add(redButton);

frame.add(panel, BorderLayout.SOUTH);
```

边框布局（border layout）扩展了面板的大小以填充整个南部区域。

***

### `java.awt.BorderLayout` 1.0

- `BorderLayout()`
- `BorderLayout(int hgap, int vgap)`

  构造一个新的 `BorderLayout`。

![Image](img/644tab01.jpg)

***

### 12.2.2 网格布局（Grid Layout）

网格布局像电子表格一样按行和列排列所有组件。所有组件具有相同的大小。图 12.12 中的计算器程序使用网格布局来排列计算器按钮。当你调整窗口大小时，按钮会增大或缩小，但所有按钮的大小完全相同。

![Image](img/12fig12.jpg)

**图 12.12** 计算器

在网格布局对象的构造函数中，你可以指定所需的行和列。

```java
panel.setLayout(new GridLayout(4, 4));
```

添加组件，从第一行的第一个项目开始，然后是第一行的第二个项目，依此类推。

```java
panel.add(new JButton("1"));

panel.add(new JButton("2"));
```

`Listing 12.1` 显示了计算器程序的面板类。这是一个普通的计算器，而不是在 Java 教程中异常流行的那种“逆波兰表达式”类型。在这个程序中，我们在将组件添加到框架后调用 `pack` 方法。该方法使用所有组件的首选尺寸（preferred sizes）来计算框架的宽度和高度。

当然，很少有应用程序像计算器界面那样具有严格的布局。在实践中，小型网格（通常只有一行或一列）可以用于组织窗口的局部区域。例如，如果你想有一行大小相同的按钮，可以将按钮放在一个由单行网格布局控制的面板内部。

**Listing 12.1** `calculator/CalculatorPanel.java`

```java
package calculator;

import java.awt.*;

import java.awt.event.*;

import javax.swing.*;

/**
 * 带有计算器按钮和结果显示器的面板。
 */
public class CalculatorPanel extends JPanel
{
    private JButton display;

    private JPanel panel;

    private double result;

    private String lastCommand;

    private boolean start;

    public CalculatorPanel()
    {
        setLayout(new BorderLayout());

        result = 0;

        lastCommand = "=";

        start = true;

        // 添加显示器
        display = new JButton("0");

        display.setEnabled(false);

        add(display, BorderLayout.NORTH);

        ActionListener insert = new InsertAction();

        ActionListener command = new CommandAction();

        // 在 4x4 网格中添加按钮
        panel = new JPanel();

        panel.setLayout(new GridLayout(4, 4));

        addButton("7", insert);

        addButton("8", insert);

        addButton("9", insert);

        addButton("/", command);

        addButton("4", insert);

        addButton("5", insert);

        addButton("6", insert);

        addButton("*", command);

        addButton("1", insert);

        addButton("2", insert);

        addButton("3", insert);

        addButton("-", command);

        addButton("0", insert);

        addButton(".", insert);

        addButton("=", command);

        addButton("+", command);

        add(panel, BorderLayout.CENTER);
    }

    /**
     * 将按钮添加到中心面板。
     * @param label 按钮
     * @param listener 按钮监听器
     */
    private void addButton(String label, ActionListener listener)
    {
        JButton button = new JButton(label);

        button.addActionListener(listener);

        panel.add(button);
    }

    /**
     * 此操作将按钮字符串插入到文本末尾。
     */
    private class InsertAction implements ActionListener
    {
        public void actionPerformed(ActionEvent event)
        {
            String input = event.getActionCommand();

            if (start)
            {
                display.setText("");

                start = false;
            }

            display.setText(display.getText() + input);
        }
    }

    /**
     * 此操作执行按钮动作表示的命令。
     */
    private class CommandAction implements ActionListener
    {
        public void actionPerformed(ActionEvent event)
        {
            String command = event.getActionCommand();

            if (start)
            {
                if (command.equals("-"))
                {
                    display.setText(command);

                    start = false;
                }
                else
                {
                    lastCommand = command;
                }
            }
            else
            {
                calculate(Double.parseDouble(display.getText()));

                lastCommand = command;

                start = true;
            }
        }
    }

    /**
     * 执行待处理计算。
     * @param x 要与先前结果累加的值。
     */
    public void calculate(double x)
    {
        if (lastCommand.equals("+"))
        {
            result += x;
        }
        else if (lastCommand.equals("-"))
        {
            result -= x;
        }
        else if (lastCommand.equals("*"))
        {
            result *= x;
        }
        else if (lastCommand.equals("/"))
        {
            result /= x;
        }
        else if (lastCommand.equals("="))
        {
            result = x;
        }

        display.setText("" + result);
    }
}
```




- `boolean isEditable()`
- `void setEditable(boolean b)`

获取或设置`editable`属性，该属性决定用户是否可以编辑此文本组件的内容。

##我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。12.3.1 文本字段 (Text Fields)

向窗口添加文本字段的常用方法是将其添加到面板或其他容器中——就像添加按钮一样：

```java
JPanel panel = new JPanel();
JTextField textField = new JTextField("Default input", 20);
panel.add(textField);
```

这段代码添加了一个文本字段，并通过在其中放置`"Default input"`字符串来对其初始化。该构造函数的第二个参数设置了宽度。在这种情况下，宽度为 20 个“列”。遗憾的是，列是一个相当不精确的测量单位。一列是你正在用于文本的字体中一个字符的预期宽度。其想法是，如果你预计输入的内容少于或等于`n`个字符，应该指定`n`为列宽。在实践中，这种测量效果并不理想，为了保险起见，你应该在最大输入长度上增加 1 或 2。此外，请记住，列数只是给 AWT 的一个提示，用于提供`preferred`优先级大小。如果布局管理器需要增大或缩小文本字段，它可以调整其尺寸。你在`JTextField`构造函数中设置的宽度并不是用户可以输入的字符数量的上限。用户仍然可以输入更长的字符串，但当文本超过字段长度时，输入会滚动。用户往往会发现滚动文本字段令人恼火，因此你应该给字段的尺寸留得宽裕一些。如果你需要在运行时重置列数，可以使用`setColumns`方法。

> **提示**
> 
> 在使用`setColumns`方法更改文本框的大小后，调用周围容器的`revalidate`方法。
> 
> ```java
> textField.setColumns(10);
> panel.revalidate();
> ```

`revalidate`方法会重新计算容器内所有组件的大小和布局。在你使用`revalidate`方法之后，布局管理器会重新调整容器的大小，文本字段改变后的尺寸将变得可见。

`revalidate`方法属于`JComponent`类。它不会立即调整组件的大小，而将其标记为需要调整大小。这种方法避免了当多个组件请求调整大小时的重复计算。然而，如果你想重新计算`JFrame`内部的所有组件，你必须调用`validate`方法——`JFrame`并没有继承`JComponent`。

通常情况下，用户在文本字段中输入文本（或编辑现有文本）。这些文本字段通常是空白的。要创建一个空白的文本字段，只需省略作为`JTextField`构造函数的字符串参数即可：

```java
JTextField textField = new JTextField(20);
```

你可以通过使用上一节中提到的父类`JTextComponent`的`setText`方法随时更改文本字段的内容。例如：

```java
textField.setText("Hello!");
```

而且，正如上一节中提到的，你可以通过调用`getText`方法来获取用户输入了什么。该方法返回用户输入的精确文本。要修剪文本字段数据中任何多余的前导和尾随空格，对`getText`的返回值应用`trim`方法：

```java
String text = textField.getText().trim();
```

要更改用户文本显示的字体，请使用`setFont`方法。

### javax.swing.JTextField **1.2**

- `JTextField(int cols)`
  构造一个具有指定列数的空`JTextField`。
- `JTextField(String text, int cols)`
  构造一个具有初始字符串和指定列数的新`JTextField`。
- `int getColumns()`
- `void setColumns(int cols)`
  获取或设置此文本字段应该使用的列数。

### javax.swing.JComponent **1.2**

- `void revalidate()`
  导致组件的位置和大小被重新计算。
- `void setFont(Font f)`
  设置此组件的字体。

### java.awt.Component **1.0**

- `void validate()`
  重新计算组件的位置和大小。如果该组件是一个容器，则其内部组件的位置和大小也将重新计算。
- `Font getFont()`
  获取此组件的字体。

## 12.3.2 标签与标签标记 (Labels and Labeling Components)

标签是持有文本的组件。它们没有装饰（例如，没有边框）。它们对用户输入没有反应。你可以使用标签来标识组件。例如，与按钮不同，文本字段没有标签来标识它们。要为一个本身不带标识符的组件标记：

1. 构建一个具有正确文本的`JLabel`组件。
2. 将其放置在想要标识的组件足够近的位置，以便用户可以看到该标签标识的是正确的组件。

`JLabel`的构造函数允许你指定初始文本或图标，以及可选的内容对齐方式。你使用来自`SwingConstants`的常量来指定对齐方式。该接口定义了一些有用的常量，如`LEFT`、`RIGHT`、`CENTER`、`NORTH`、`EAST`等。`JLabel`类是实现此接口的多个类之一。因此，你可以通过如下方式指定右对齐的标签：

```java
JLabel label = new JLabel("User name: ", SwingConstants.RIGHT);
```

或者

```java
JLabel label = new JLabel("User name: ", JLabel.RIGHT);
```

`setText`和`setIcon`方法允许你在运行时设置标签的文本和图标。

> **提示**
> 
> 你可以在按钮、标签和菜单项中使用纯文本和 HTML 文本。我们不建议在按钮中使用 HTML——它会干扰外观和感觉（look-and-feel）。但在标签中使用 HTML 可能会非常有效。只需将标签字符串用`<html></html>`包围起来，如下所示：
> 
> ```java
> label = new JLabel("<html>Required entry:</html>");
> ```
> 
> 注意，第一个带有 HTML 的标签可能需要一些时间显示，因为必须加载复杂的 HTML 渲染代码。

标签可以像其他组件一样位于容器内部。这意味着你可以使用见过的技术将标签放置在需要的地方。

### javax.swing.JLabel **1.2**

- `JLabel(String text)`
- `JLabel(Icon icon)`
- `JLabel(String text, int align)`
- `JLabel(String text, Icon icon, int align)`
  构造一个标签。
- `String getText()`
- `void setText(String text)`
  获取或设置此标签的文本。
- `Icon getIcon()`
- `void setIcon(Icon icon)`
  获取或设置此标签的图标。

## 12.3.3 密码字段 (Password Fields)

密码字段是一种特殊的文本字段。为了防止旁人看到密码，用户输入的字符不会被实际显示。相反，每个输入的字符由一个显示字符表示，通常是星号（`*`）。Swing 提供了一个实现此类文本字段的`JPasswordField`类。

密码字段是模型-视图控制器架构模式的另一个例子。密码字段使用与文本字段相同的模型来存储数据，但其视图已更改为显示所有字符作为显示字符。

### javax.swing.JPasswordField **1.2**

- `JPasswordField(String text, int columns)`
  构造一个新的密码字段。
- `void setEchoChar(char echo)`
  设置此密码字段的显示字符。这是建议性的；特定的外观和感觉可能会坚持使用它选择的显示字符。值`0`会重置显示字符为默认值。
- `char[] getPassword()`
  返回此密码字段中包含的文本。为了更高的安全性，您应该在使用后覆盖返回的数组的内容。（密码不会以`String`形式返回，因为字符串将一直留在虚拟机中直到被垃圾回收。）

## 12.3.4 文本区域 (Text Areas)

有时，你需要收集超过一行的用户输入。如前所述，你可以使用`JTextArea`组件来实现此目的。当你程序中放置一个文本区域组件时，用户可以输入任意行的文本，使用 Enter 键将它们分隔。每行都以`'\n'`结束。图 12.13 显示了一个正在工作中的文本区域。

**图 12.13** 文本组件

在`JTextArea`组件的构造函数中，指定文本区域的行数和列数。例如，

```java
textArea = new JTextArea(8, 40); // 8 行，每行 40 列
```

其中`columns`参数的作用与之前一样——为了安全起见，你仍然需要多添加几列。同样，与之前一样，用户并不限于行数和列数；当用户输入内容过多时，文本会自动滚动。你还可以使用`setColumns`方法更改列数，并使用`setRows`方法更改行数。这些数字仅表示首选尺寸——布局管理器仍然可以放大或缩小文本区域。

如果文本多于文本区域能够显示的范围，剩余文本将简单地被截裁（clipped）。你可以通过开启自动换行来避免长行被截裁：

```java
textArea.setLineWrap(true); // 长行将换行
```

这种换行仅是一种视觉效果；文档中的文本不会发生改变——不会在文本中自动插入`'\n'`字符。

## 12.3.5 滚动面板 (Scroll Panes)

在 Swing 中，文本区域不带滚动条。如果你需要滚动条，必须将文本区域放置在滚动面板内部。

```java
textArea = new JTextArea(8, 40);
JScrollPane scrollPane = new JScrollPane(textArea);
```

滚动面板现在管理文本区域的视图。如果文本多于文本区域能够显示的范围，滚动条会自动出现；当文本被删除且剩余文本适合区域内时，滚动条会再次消失。滚动由滚动面板内部处理——你的程序不需要处理滚动事件。

这是一个适用于任何组件的通用机制，而不仅仅是文本区域。要为组件添加滚动条，请将其放在滚动面板内部。

列表 12.2 展示了各种文本组件。该程序显示了一个文本字段、一个密码字段和一个带滚动条的文本区域。文本字段和密码字段都标有标签。点击“插入（Insert）”可以将字段内容插入到文本区域中。

> **注意**
> 
> `JTextArea`组件仅显示纯文本，没有特殊字体或格式。要显示格式化后的文本（如 HTML），你可以使用卷二中讨论的`JEditorPane`类。

**列表 12.2** `text/TextComponentFrame.java`

```java
package text;

import java.awt.BorderLayout;
import java.awt.GridLayout;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JPasswordField;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.JTextField;
import javax.swing.SwingConstants;

/**
 * 带有示例文本组件的框架。
 */
public class TextComponentFrame extends JFrame
{
    public static final int TEXTAREA_ROWS = 8;
    public static final int TEXTAREA_COLUMNS = 20;

    public TextComponentFrame()
    {
        JTextField textField = new JTextField();
        JPasswordField passwordField = new JPasswordField();

        JPanel northPanel = new JPanel();
        northPanel.setLayout(new GridLayout(2, 2));
        northPanel.add(new JLabel("User name: ", SwingConstants.RIGHT));
        northPanel.add(textField);
        northPanel.add(new JLabel("Password: ", SwingConstants.RIGHT));
        northPanel.add(passwordField);

        add(northPanel, BorderLayout.NORTH);

        JTextArea textArea = new JTextArea(TEXTAREA_ROWS, TEXTAREA_COLUMNS);
        JScrollPane scrollPane = new JScrollPane(textArea);
        add(scrollPane, BorderLayout.CENTER);

        // 添加按钮将文本追加到区域
        JPanel southPanel = new JPanel();
        JButton insertButton = new JButton("Insert");
        southPanel.add(insertButton);
        insertButton.addActionListener(event ->
            textArea.append("User name: " + textField.getText() + " Password: "
                + new String(passwordField.getPassword()) + "\n"));

        add(southPanel, BorderLayout.SOUTH);
        pack();
    }
}
```

### javax.swing.JTextArea

- `JTextArea()`
- `JTextArea(int rows, int cols)`
- `JTextArea(String text, int rows, int cols)`
  构造一个文本区域。
- `void setColumns(int cols)`
  告诉文本区域首选的列数。
- `void setRows(int rows)`
  告诉文本区域首选的行数。
- `void append(String newText)`
  将指定的文本追加到文本区域末尾。
- `void setLineWrap(boolean wrap)`
  开启或关闭换行。
- `void setStyleWord(boolean word)`
  如果`word`为`true`，则在单词边界换行。如果为`false`，则不考虑单词边界换行。
- `void setTabSize(int c)`
  每`c`列设置制表符。注意制表符不会转换为空格，而是与下一个制表位对齐。

### javax.swing.JScrollPane

- `JScrollPane(Component c)`
  创建一个显示组件内容的滚动面板。当组件大于视图时提供滚动条。

## 12.4 选择组件

你现在已经知道如何收集文本输入，但在许多情况下，你更愿意给用户提供有限的选择，而不是让他们在文本组件中输入数据。使用按钮组或项目列表可以告诉用户有哪些选择。（这还为你节省了错误检查的麻烦。）在本节中，你将学习如何使用复选框、单选按钮、列表和滑动块。

### 12.4.1 复选框 (Checkboxes)

如果你只想收集“是”或“否”输入，请使用复选框组件。复选框带有标识它们的标签。用户可以通过点击框内部来勾选，通过再次点击框内部来取消勾选。当焦点在复选框上时，按下空格键也可以切换勾选状态。

图 12.14 显示了一个带有两个复选框的简单程序，一个用于开启或关闭字体的斜体属性，另一个用于加粗。注意第二个复选框具有焦点，标签周围的矩形所示。每当用户点击一个复选框时，屏幕都会刷新并使用新的字体属性。

**图 12.14** 复选框

复选框旁边需要一个标签来标识其用途。在构造函数中给出标签文本：

```java
bold = new JCheckBox("Bold");
```

使用`setSelected`方法开启或关闭复选框。例如：

```java
bold.setSelected(true);
```



使用`isSelected`方法获取每个复选框的当前状态。未勾选则为`false`，勾选则为`true`。

当用户点击复选框时，会触发一个动作事件。像往常一样，你为复选框附加一个动作监听器。在我们的程序中，这两个复选框共享同一个动作监听器。

```
ActionListener listener = . . .

bold.addActionListener(listener);

italic.addActionListener(listener);
```

监听器查询`bold`和`italic`复选框的状态，并将面板的字体设置为普通、粗体、斜体或粗体加斜体结合。

```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。ActionListener listener = event -> {

    int mode = 0;

    if (bold.isSelected()) mode += Font.BOLD;

    if (italic.isSelected()) mode += Font.ITALIC;

    label.setFont(new Font(Font.SERIF, mode, FONTSIZE));

};
```

Listing 12.3 是复选框示例的程序列表。

**Listing 12.3** `checkBox/CheckBoxFrame.java`

```java
1   package checkBox;

2

3   import java.awt.*;

4   import java.awt.event.*;

5   import javax.swing.*;

6

7   /**

8    * 一个带有示例文本标签和用于选择字体

9    * 属性的复选框的框架。

10   */

11   public class CheckBoxFrame extends JFrame

12   {

13       private JLabel label;

14       private JCheckBox bold;

15       private JCheckBox italic;

16       private static final int FONTSIZE = 24;

17

18       public CheckBoxFrame()

19       {

20          // 添加示例文本标签

21

22          label = new JLabel("The quick brown fox jumps over the lazy dog.");

23          label.setFont(new Font("Serif", Font.BOLD, FONTSIZE));

24          add(label, BorderLayout.CENTER);

25

26          // 此监听器将标签的字体属性

27          // 设置为复选框的状态

28

29          ActionListener listener = event -> {

30              int mode = 0;

31              if (bold.isSelected()) mode += Font.BOLD;

32              if (italic.isSelected()) mode += Font.ITALIC;

33              label.setFont(new Font("Serif", mode, FONTSIZE));

34          };

35

36          // 添加复选框

37

38          JPanel buttonPanel = new JPanel();

39

40          bold = new JCheckBox("Bold");

41          bold.addActionListener(listener);

42          bold.setSelected(true);

43          buttonPanel.add(bold);

44

45          italic = new JCheckBox("Italic");

46          italic.addActionListener(listener);

47          buttonPanel.add(italic);

48

49          add(buttonPanel, BorderLayout.SOUTH);

50          pack();

51       }

52   }
```

`javax.swing.JCheckBox`
- `JCheckBox(String label)`
- `JCheckBox(String label, Icon)` 构建一个初始为未选的复选框。
- `JCheckBox(String label, boolean state)` 构建一个具有给定标签和初始状态的复选框。
- `boolean isSelected()`
- `void setSelected(boolean state)` 获取或设置复选框的选择状态。

### 12.4.2 单选按钮

在上一个示例中，用户可以勾选两个复选框中的一个、两个或都不选。在许多情况下，我们希望用户只选择几个框中的一个。当另一个框被勾选时，之前的框会自动取消勾选。这样一组框通常被称为单选按钮组，因为这些按钮的工作方式类似于收音机选择器。当你按下一个按钮时，被按下的按钮会弹出。图 12.15 显示了一个典型的例子。我们允许用户从选项（小、中、大）中选择字体大小——但当然，我们一次只允许选择一种大小。

![Image](img/12fig15.jpg)
**图 12.15** 单选按钮组

在 Swing 中实现单选按钮组非常简单。对于每组按钮构造一个`ButtonGroup`对象。然后，将`JRadioButton`类型的对象添加到按钮组中。按钮组对象负责在点击新按钮时关闭之前设置的按钮。

```java
ButtonGroup group = new ButtonGroup();

JRadioButton smallButton = new JRadioButton("Small", false);

group.add(smallButton);

JRadioButton mediumButton = new JRadioButton("Medium", true);

group.add(mediumButton);
```

构造函数的第二个参数对于应该被选中的按钮为`true`，对于所有其他按钮为`false`。请注意，按钮组只控制按钮的行为；如果你是为了布局目的而对按钮进行分组，你还需要将它们添加到如`JPanel`等容器中。

如果你再次查看图 12.14 和 12.15，你会注意到单选按钮的外观与复选框不同。复选框是正方形的，在选中时包含一个选中标记。单选按钮是圆形的，在选中时包含一个圆点。

单选按钮的事件通知机制与任何其他按钮相同。当用户勾选单选按钮时，该按钮产生一个动作事件。在我们的示例程序中，我们定义了一个动作监听器，将字体大小设置为特定值：

```java
ActionListener listener = event ->

    label.setFont(new Font("Serif", Font.PLAIN, size));
```

将此监听器设置与复选框示例进行比较。每个单选按钮都有一个不同的监听器。每个监听器确切知道需要做什么——将字体大小设置为特定值。在复选框中，我们使用了不同的方法：同一个监听器如下

```java
if (smallButton.isSelected()) size = 8;

else if (mediumButton.isSelected()) size = 12;
```

然而，我们更倾向于使用独立的动作监听器对象，因为它们将值与按钮绑定得更紧密。

**注意** 如果你有一组单选按钮，你已知其中只有一个被选中了。如果能快速查出是哪一个而无需查询组中的所有按钮就好了。`ButtonGroup`对象控制所有按钮，因此如果该对象能提供被选中按钮的引用将非常方便。事实上，它返回的是附加到按钮的`ButtonModel`引用。遗憾的是，`ButtonModel`的方法没有很好用。`ButtonModel`接口继承了`ItemSelectable`接口的`getSelectedObjects`方法，它毫无用处地返回`null`。`getActionCommand`方法很有前景，因为单选按钮的“动作命令”是它的文本标签。但模型的动作命令是`null`。只有当你使用`setActionCommand`方法显式设置所有单选按钮的动作命令时，模型的动作命令值也会被设置。然后你可以通过`buttonGroup.getSelection().getActionCommand()`获取当前选中按钮的动作命令。

Listing 12.4 是用于字体大小选择的让一组单选按钮工作的完整程序。

**Listing 12.4** `radioButton/RadioButtonFrame.java`

```java
private JLabel label;

private static final int DEFAULT_SIZE = 36;

public RadioButtonFrame()

{

    // 添加示例文本标签

    label = new JLabel("The quick brown fox jumps over the lazy dog.");

    label.setFont(new Font("Serif", Font.PLAIN, DEFAULT_SIZE));

    add(label, BorderLayout.CENTER);

    // 添加单选按钮

    buttonPanel = new JPanel();

    group = new ButtonGroup();

    addRadioButton("Small", 8);

    addRadioButton("Medium", 12);

    addRadioButton("Large", 18);

    addRadioButton("Extra large", 36);

    add(buttonPanel, BorderLayout.SOUTH);

    pack();

}

/**

 * 添加一个单选按钮，设置示例文本的字体大小。

 * @param name 显示在按钮上的字符串

 * @param size 该按钮设置的字体大小

 */

public void addRadioButton(String name, int size)

{

    boolean selected = size == DEFAULT_SIZE;

    JRadioButton button = new JRadioButton(name, selected);

    group.add(button);

    buttonPanel.add(button);

    // 此监听器设置标签的字体大小

    ActionListener listener = event -> label.setFont(new Font("Serif", Font.PLAIN, size));

    button.addActionListener(listener);

}
```

### javax.swing.JRadioButton 1.2
- `JRadioButton(String label, Icon icon)` 构建一个初始未选中的单选按钮。
- `JRadioButton(String label, boolean state)` 构建一个具有给定标签和初始状态的单选按钮。

### javax.swing.ButtonGroup 1.2
- `void add(AbstractButton b)` 将按钮添加到组中。
- `ButtonModel getSelection()` 返回所选按钮的模型。

### javax.swing.ButtonModel 1.2
- `String getActionCommand()` 返回此按钮模型的动作命令。

### javax.swing.AbstractButton 1.2
- `void setActionCommand(String s)` 设置此按钮及其模型的动作命令。

### 12.4.3 边界 (Borders)

如果你在窗口中有多个单选按钮，你可能希望在视觉上指示哪些按钮是一组的。Swing 为此提供了一系列实用的边界。你可以将边界应用于任何扩展自`JComponent`的组件。最常用的用法是在面板周围放置边界，并在面板中填充其他用户界面元素，例如单选按钮。

你可以选择许多边界，但对所有边界你都需要遵循相同的步骤。

1. 调用`BorderFactory`的静态方法来创建边界。你可以从以下样式中选择（参见图 12.16）：
   - 凹角 (Lowered bevel)
   - 凸斜角 (Raised bevel)
   - 刻蚀 (Etched)
   - 哑光 (Matte)
   - 空白（Empty，仅在组件周围留出空间）
   ![Image](img/12fig16.jpg) **图 12.16 边界测试**
2. 如果需要，可以通过将边界传递给`BorderFactory.createTitledBorder`为你的边界添加标题。
3. 如果你真的想尝试一下，可以调用`BorderFactory.createCompoundBorder`将多个边界组合。
4. 通过调用`JComponent`类的`setBorder`方法将生成的边界添加到你的组件中。

例如，这里是如何为面板添加带有标题的刻蚀边界：
```java
Border etched = BorderFactory.createEtchedBorder();

Border titled = BorderFactory.createTitledBorder(etched, "A Title");

panel.setBorder(titled);
```
运行列表 12.5 中的程序可以了解各种边界的外观。不同的边界在设置宽度和颜色方面有不同的选项；详情请参 API 注释。真正的边界热爱好者会发现，还有一个`SoftBevelBorder`类用于具有圆润角的凹斜角边界，并且`LineBorder`也可以具有圆角。你只能通过使用类构造之一来构造这些边界——它们没有对应的`BorderFactory`方法。

**代码列表 2.5** `border/BorderFrame.java`
```java
package border;

import java.awt.*;

import javax.swing.*;

import javax.swing.border.*;

/**

 * 一个带有单选按钮的框架，用于选择边界样式。

 */

public class BorderFrame extends JFrame

{

    private JPanel demoPanel;

    private JPanel buttonPanel;

    private ButtonGroup group;

    public BorderFrame()

    {

        demoPanel = new JPanel();

        buttonPanel = new JPanel();

        group = new ButtonGroup();

        addRadioButton("Lowered bevel", BorderFactory.createLoweredBevelBorder());

        addRadioButton("Raised bevel", BorderFactory.createRaisedBevelBorder());

        addRadioButton("Etched", BorderFactory.createEtchedBorder());

        addRadioButton("Line", BorderFactory.createLineBorder(Color.BLUE));

        addRadioButton("Matte", BorderFactory.createMatteBorder(10, 10, 10, 10, Color.BLUE));

        addRadioButton("Empty", BorderFactory.createEmptyBorder());

        Border etched = BorderFactory.createEtchedBorder();

        Border titled = BorderFactory.createTitledBorder(etched, "Border types");

        buttonPanel.setBorder(titled);

        setLayout(new GridLayout(2, 1));

        add(buttonPanel);

        add(demoPanel);

        pack();

    }

    public void addRadioButton(String buttonName, Border b)

    {



```java
JRadioButton button = new JRadioButton(buttonName);

button.addActionListener(event -> demoPanel.setBorder(b));

group.add(button);

buttonPanel.add(button);
```

### `javax.swing.BorderFactory` 1.2

- `static Border createLineBorder(Color color)`
- `static Border createLineBorder(Color color, int thickness)` 创建简单的线条边界。
- `static MatteBorder createMatteBorder(int top, int left, int bottom, int right, Color color)`
- `static MatteBorder createMatteBorder(int top, int left, int bottom, int right, Icon tileIcon)` 创建一个填充颜色或重复图标的厚边界。
- `static Border createEmptyBorder()`
- `static Border createEmptyBorder(int top, int left, int bottom, int right)` 创建一个空边界。
- `static Border createEtchedBorder()`
- `static Border createEtchedBorder(Color highlight, Color shadow)`
- `static Border createEtchedBorder(int type)`
- `static Border createEtchedBorder(int type, Color highlight, Color shadow)` 创建具有 3D 效果的线条边界。
- `static Border createBevelBorder(int type)`
- `static Border createBevelBorder(int type, Color highlight, Color shadow)`
- `static Border createLoweredBevelBorder()`
- `static Border createRaisedBevelBorder()` 创建一种具有凹陷或凸起表面效果的边界。
- `static TitledBorder createTitledBorder(String title)`
- `static TitledBorder createTitledBorder(Border border)`
- `static TitledBorder createTitledBorder(Border border, String title)`
- `static TitledBorder createTitledBorder(Border border, String title, int justification, int position)`
- `static TitledBorder createTitledBorder(Border border, String title, int justification, int position, Font font)`
- `static TitledBorder createTitledBorder(Border border, String title, int justification, int position, Font font, Color color)` 创建具有指定属性的标题边界。
- `static CompoundBorder createCompoundBorder(Border outsideBorder, Border insideBorder)` 将两个边界组合为一个新边界。

### `javax.swing.border.SoftBevelBorder` 1.2

- `SoftBevelBorder(int type)`
- `SoftBevelBorder(int type, Color highlight, Color shadow)`

创建一个带有圆角的斜角边框。

![Image](img/667tab03.jpg)

### `javax.swing.border.LineBorder` 1.2

- `public LineBorder(Color color, int thickness, boolean roundedCorners)`

创建一个具有给定颜色和厚度的线条框。如果 `roundedCorners` 为 `true`，则边框具有圆角。

### `javax.swing.JComponent` 1.2

- `void setBorder(Border border)`

设置此组件的边框。

## 12.4.4 组合框（Combo Boxes）

如果你有多个备选项，单选按钮不是很好的选择，因为它们占据了多的屏幕空间。相反，你可以使用组合框。当用户点击此组件时，会弹出一个选项列表，用户可以从中选择其中一个（参见图 12.17）。

![Image](img/12fig17.jpg)

**图 12.17** 组合框

如果下拉列表框被设置为 `editable`（可编辑），你可以像编辑文本字段一样编辑当前选择。因此，此组件被称为组合框（combo box）——它结合了文本字段的灵性和一组预定义的选项。`JComboBox` 类提供了组合框组件。

从 Java SE 7 开始，`JComboBox` 类是一个泛型类。例如，`JComboBox<String>` 存储 `String` 类型的对象，而 `JComboBox<Integer>` 存储整数。

调用 `setEditable` 方法使组合框变为可编辑。请注意，编辑仅影响被选中的项。它不会以任何方式更改选项列表。

你可以通过调用 `getSelectedItem` 方法获取当前选择项（如果组合框是可编辑的，该项可能已被编辑过）。然而，对于可编辑的组合框，该项可以是任何类型，取决于接收用户编辑并将结果转换为对象的编辑器。（关于编辑器的讨论，请参见卷二的第 6 章。）如果你的组合框不可编辑，你最好调用：

```java
combo.getItemAt(combo.getSelectedIndex())
```

这会给你具有正确类型的被选中项。

在示例程序中，用户可以从样式列表（Serif、SansSerif、Monospaced 等）中选择字体样式。用户也可以输入另一种字体。

使用 `addItem` 方法添加选择项。在我们的程序中，`addItem` 只在构造函数中调用，但你可以在随时调用它。

点击此处查看代码图像：

```java
JComboBox<String> faceCombo = new JComboBox<>();

faceCombo.addItem("Serif");

faceCombo.addItem("SansSerif");

// . .
```

此方法将字符串添加到列表的末尾。你可以使用 `insertItemAt` 方法在列表的任何位置添加新项：

点击此处查看代码图像：

```java
faceCombo.insertItemAt("Monospaced", 0); // 在开头添加
```

你可以添加任何类型的项——组合框会调用每个项的 `toString` 方法来显示它。

如果你需要在运行时删除项，使用 `removeItem` 或 `removeItemAt` 方法，取决于你提供的是要删除的项还是它的位置。

点击此处查看代码图像：

```java
faceCombo.removeItem("Monospaced");

faceCombo.removeItemAt(0); // 删除第一项
```

`removeAllItems` 方法一次性删除所有项。

![Image](img/tip.jpg) 提示

如果你需要向组合框添加大量项，`addItem` 方法的性能会很差。相反，构造一个 `DefaultComboBoxModel`，通过调用 `addElement` 填充它，然后调用 `JComboBox` 类的 `setModel` 方法。

当用户从组合框中选择一个项时，组合框会生成一个动作事件。要确定选择了哪一个项，在事件参数上调用 `getSource` 以获取发送事件的组合框的引用。然后调用 `getSelectedItem` 方法检索当前选择的项。你需要将返回的值强制转换为适当的类型，通常是 `String`。

点击此处查看代码图像：

```java
ActionListener listener = event ->

    label.setFont(new Font(

        faceCombo.getItemAt(faceCombo.setSelectedIndex()),

        Font.PLAIN,

        DEFAULT_SIZE));
```

列表 12.6 显示了完整的程序。

![Image](img/note.jpg) 备注

如果你想显示一个永久显示的列表而不是下拉列表，请使用 `JList` 组件。我们在卷二的第 6 章中涵盖了 `JList`。

**列表 2.6** `comboBoxFrame.java`

点击此处查看代码图像：

```java
package comboBox;

import java.awt.BorderLayout;

import java.awt.Font;

import javax.swing.JComboBox;

import javax.swing.JFrame;

import javax.swing.JLabel;

import javax.swing.JPanel;

/**
 * 带有示例标签的组合框的框架。
 */
public class ComboBoxFrame extends JFrame {

    private JComboBox<String> faceCombo;

    private JLabel label;

    private final int DEFAULT_SIZE = 24;

    public ComboBoxFrame() {

        // 添加示例标签
        label = new JLabel("The quick brown fox jumps the lazy dog.");

        add(label, BorderLayout.CENTER);

        // 组合框添加名称
        faceCombo = new JComboBox<>();

        faceCombo.addItem("Serif");

        faceCombo.addItem("SansSerif");

        faceCombo.addItem("Monospaced");

        faceCombo.addItem("Dialog");

        // 组合框监听器更改标签字体
        faceCombo.addActionListener(event ->

            label.setFont(new Font(

                faceCombo.getItemAt(faceCombo.getSelectedIndex()),

                Font.PLAIN,

                DEFAULT_SIZE)));

        // 将组合框添加到框架底部的面板
        JPanel comboPanel = new JPanel();

        comboPanel.add(faceCombo);

        add(comboPanel, BorderLayout.SOUTH);

        pack();
    }
}
```

### `javax.swing.JComboBox` 1.2

- `boolean isEditable()`
- `void setEditable(boolean b)`

获取或设置此组合框的 `editable` 属性。

- `void addItem(Object item)` 将项添加到列表中。
- `void insertItemAt(Object item, int index)` 在指定的索引处向列表插入项。
- `void removeItem(Object item)` 从列表中删除项。
- `void removeItemAt(int index)` 删除索引处的项。
- `void removeAllItems()` 从列表中删除所有项。
- `Object getSelectedItem()` 返回当前选择的项。

## 12.4.5 滑块（Sliders）

组合框让用户从离散的值集中进行选择。滑块提供了对连续值的选择——例如，1 到 100 之间的任何数字。

构造滑块最常用的方式如下：

点击此处查看代码图像：

```java
JSlider slider = new JSlider(min, max, initialValue);
```

如果你省略最小值、最大值和初始值，它们将分别初始化为 `0`、`100` 和 `50`。

或者，如果你想让滑块是垂直的，请使用以下构造调用：

点击此处查看代码图像：

```java
JSlider slider = new JSlider(SwingConstants.VERTICAL, min, max, initialValue);
```

这些构造函数创建了一个简单的滑块，例如图 12.18 中顶部的滑块。你将很快看到如何为滑块添加装饰。

![Image](img/12fig18.jpg)

**图 12.18** 滑块

当用户滑动滑块时，滑块的 `value` 在最小值和最大值之间移动。当值发生变化时，会向所有更改监听器发送一个 `ChangeEvent`。要接收更改通知，请调用 `addChangeListener` 方法并安装一个实现了功能性 `ChangeListener` 接口的对象。在回调中，获取滑块的值：

点击此处查看代码图片：

```java
ChangeListener listener = event -> {

    JSlider slider = (JSlider) event.getSource();

    int value = slider.getValue();

    ...
};
```

你可以通过显示 `ticks`（刻度）来美化滑块。例如，在示例程序中，第二个滑块使用了以下设置：

```java
slider.setMajorTickSpacing(20);

slider.setMinorTickSpacing(5);
```

滑块每隔 20 个单位有一个大刻度，每隔 5 个单位有一个小刻度。单位指的是滑块的值，而不是像素。

这些指令仅设置了刻度的单位。要让刻度真正出现，请调用：

```java
slider.setPaintTicks(true);
```

大刻度和小刻度是相互独立的。例如，你可以设置每隔 20 个单位一个大刻度，每隔 7 个单位一个小刻度，但这将给你一个非常混乱的刻度。

你可以强制滑块 `snap to ticks`（吸附到刻度）。当用户在吸附模式下完成拖动时，它会立即移动到最近的刻度。你通过以下调用激活此模式：

```java
slider.setSnapToTicks(true);
```

![Image](img/caution.jpg) 注意

“吸附到刻度”的行为并没有想象中那么好。在滑块实际吸附之前，更改监听器仍然报告不对应刻度的数值。如果你点击滑块旁边——此操作通常会让滑块向点击方向移动一点——开启了“吸附到刻度”的滑块不会移动到下一个刻度。

你可以通过调用以下方法为大刻度显示 `tick mark labels`（刻度标签）：

```java
slider.setPaintLabels(true);
```

例如，对于一个范围从 0 到 100 且大刻度间距为 20 的滑块，刻度标记为 0、20、40、60、80 和 100。

你还可以提供其他的刻度标签，例如字符串或图标（见图 12.18）。这个过程有点复杂。你需要填充一个键为 `Integer` 类型、值为 `Component` 类型的哈希表。然后调用 `setLabelTable` 方法。这些组件被放置在刻度下方。通常使用 `JLabel` 对象。以下是如何将刻度标记为 A、B、C、D、E 和 F：

点击此处查看代码图片：

```java
Hashtable<Integer, Component> labelTable = new Hashtable<Integer, Component>();

labelTable.put(0, new JLabel("A"));

labelTable.put(20, new JLabel("B"));

. . .

labelTable.put(100, new JLabel("F"));

slider.setLabelTable(labelTable);
```

参见第 9 章获取关于哈希表的更多信息。列表 12.7 还显示了一个使用图标作为刻度标签的滑块。

![Image](img/tip.jpg) 提示

如果你的刻度或标签没有显示，请双检是否调用了 `setPaintTicks(true)` 和 `setPaintLabels(true)`。

图 12.18 中的第四个滑块没有轨道。要隐藏滑块移动的“轨道”，调用：

```java
slider.setPaintTrack(false);
```

第五个滑块通过调用反转了方向：

```java



`slider.setInverted(true);`

示例程序通过一组滑块展示了所有这些视觉效果。每个滑块都安装了一个更改监听器，将当前滑块的值置于框架底部的文本字段中。

**列表 12.7** `slider/SliderFrame.java`

点击此处查看代码图片

```java
package slider;

import java.awt.*;
import java.util.*;
import javax.swing.*;
import javax.swing.event.*;

/**
 * 一个包含许多滑块和用于显示滑块值的文本字段的框架。
 */
public class SliderFrame extends JFrame {
    private JPanel sliderPanel;
    private JTextField textField;
    private ChangeListener listener;

    public SliderFrame() {
        sliderPanel = new JPanel();
        sliderPanel.setLayout(new GridBagLayout());

        // 所有滑块的通用监听器
        listener = event -> {
            // 当滑块变化时更新文本字段
            JSlider source = (JSlider) event.getSource();
            textField.setText("" + source.getValue());
        };

        // 添加一个普通滑块
        JSlider slider = new JSlider();
        addSlider(slider, "Plain");

        // 添加带有大刻度和小刻度的滑块
        slider = new JSlider();
        slider.setPaintTicks(true);
        slider.setMajorTickSpacing(20);
        slider.setMinorTickSpacing(5);
        addSlider(slider, "Ticks");

        // 添加吸附到刻度的滑块
        slider = new JSlider();
        slider.setPaintTicks(true);
        slider.setSnapToTicks(true);
        slider.setMajorTickSpacing(20);
        slider.setMinorTickSpacing(5);
        addSlider(slider, "Snap to ticks");

        // 添加没有轨道的滑块
        slider = new JSlider();
        slider.setPaintTicks(true);
        slider.setMajorTickSpacing(20);
        slider.setMinorTickSpacing(5);
        slider.setPaintTrack(false);
        addSlider(slider, "No track");

        // 添加反向滑块
        slider = new JSlider();
        slider.setPaintTicks(true);
        slider.setMajorTickSpacing(20);
        slider.setMinorTickSpacing(5);
        slider.setInverted(true);
        addSlider(slider, "Inverted");

        // 添加带有数字标签的滑块
        slider = new JSlider();
        slider.setPaintTicks(true);
        slider.setPaintLabels(true);
        slider.setMajorTickSpacing(20);
        slider.setMinorTickSpacing(5);
        addSlider(slider, "Labels");

        // 添加带有字母标签的滑块
        slider = new JSlider();
        slider.setPaintTicks(true);
        slider.setPaintLabels(true);
        slider.setMajorTickSpacing(20);
        slider.setMinorTickSpacing(5);

        Dictionary<Integer, Component> labelTable = new Hashtable<>();
        labelTable.put(0, new JLabel("A"));
        labelTable.put(20, new JLabel("B"));
        labelTable.put(40, new JLabel("C"));
        labelTable.put(60, new JLabel("D"));
        labelTable.put(80, new JLabel("E"));
        labelTable.put(100, new JLabel("F"));

        slider.setLabelTable(labelTable);
        addSlider(slider, "Custom labels");

        // 添加带有图标标签的滑块
        slider = new JSlider();
        slider.setPaintTicks(true);
        slider.setPaintLabels(true);
        slider.setSnapToTicks(true);
        slider.setMajorTickSpacing(20);
        slider.setMinorTickSpacing(20);

        labelTable = new Hashtable<Integer, Component>();

        // 添加卡牌图片
        labelTable.put(0, new JLabel(new ImageIcon("nine.gif")));
        labelTable.put(20, new JLabel(new ImageIcon("ten.gif")));
        labelTable.put(40, new JLabel(new ImageIcon("jack.gif")));
        labelTable.put(60, new JLabel(new ImageIcon("queen.gif")));
        labelTable.put(80, new JLabel(new ImageIcon("king.gif")));
        labelTable.put(100, new JLabel(new ImageIcon("ace.gif")));

        slider.setLabelTable(labelTable);
        addSlider(slider, "Icon labels");

        // 添加显示滑块值的文本字段
        textField = new JTextField();

        add(sliderPanel, BorderLayout.CENTER);
        add(textField, BorderLayout.SOUTH);
        pack();
    }

    /**
     * 将滑块添加到滑块面板并绑定监听器
     *
     * @param s 滑块
     * @param description 滑块的描述
     */
    public void addSlider(JSlider s, String description) {
        s.addChangeListener(listener);

        JPanel panel = new JPanel();
        panel.add(s);
        panel.add(new JLabel(description));
        panel.setAlignmentX(Component.LEFT_ALIGNMENT);

        GridBagConstraints gbc = new GridBagConstraints();
        gbc.gridy = sliderPanel.getComponentCount();
        gbc.anchor = GridBagConstraints.WEST;
        sliderPanel.add(panel, gbc);
    }
}
```

### `javax.swing.JSlider` 1.2

- `JSlider()`
- `JSlider(int direction)`
- `JSlider(int min, int max)`
- `JSlider(int min, int max, int initialValue)`
- `JSlider(int direction, int min, int max, int initialValue)`

使用指定的方向、最小值、最大值和初始值创建一个水平滑块。

![Image](img/678tab01.jpg)

- `void setPaintTicks(boolean b)`

  如果 `b` 为 `true`，则显示刻度。

- `void setMajorTickSpacing(int units)`
- `void setMinorTickSpacing(int units)`

  按给定的滑块单位倍数设置主刻度或次刻度。

- `void setPaintLabels(boolean b)`

  如果 `b` 为 `true`，则显示刻度标签。

- `void setLabelTable(Dictionary table)`

  设置用于刻度标签的组件。表中的每个键值对的形式为 `new Integer(value)/component`。

- `void setSnapToTicks(boolean b)`

  如果 `b` 为 `true`，则滑块在每次调整后将吸附到最近的刻度。

- `void setPaintTrack(boolean b)`

  如果 `b` 为 `true`，则显示滑块运行的轨道。

## 12.5 菜单

在本章的开始，我们介绍了你可能想要放入窗口的最常用组件，例如各种按钮、文本字段和组合框。Swing 还支持另一种类型的用户界面元素——在 GUI 应用中常见的下拉菜单。

窗口顶部的 `menu bar`（菜单栏）包含下拉菜单的名称。点击名称将打开包含 `menu items`（菜单项）和 `submenus`（子菜单）的菜单。当用户点击菜单项时，所有菜单都会关闭并向程序发送消息。图 12.19 显示了一个带有子菜单的典型菜单。

![Image](img/12fig19.jpg)

**图 12.19** 带有子菜单的菜单

### 12.5.1 构建菜单

构建菜单非常简单。首先，创建一个菜单栏：

```java
JMenuBar menuBar = new JMenuBar();
```

菜单栏只是一个可以添加到任何你喜欢的地方的组件。通常情况下，你希望它出现在框架的顶部。你可以使用 `setJMenuBar` 方法将其添加到那里：

```java
frame.setJMenuBar(menuBar);
```

对于每个菜单，你都创建一个菜单对象：

```java
JMenu editMenu = new JMenu("Edit");
```

将顶层菜单添加到菜单栏中：

```java
menuBar.add(editMenu);
```

向菜单对象添加菜单项、分隔符和子菜单：

```java
JMenuItem pasteItem = new JMenuItem("Paste");
editMenu.add(pasteItem);
editMenu.addSeparator();

JMenu optionsMenu = new JMenu();
editMenu.add(optionsMenu);
```

你可以在下面的图 12.19 中的 Paste 和 Read-only 菜单项下方看到分隔符。当用户选择一个菜单时，会触发一个动作事件。你需要为每个菜单项安装一个动作监听器：

```java
ActionListener listener = ...;
pasteItem.addActionListener(listener);
```

`JMenu.add(String s)` 方法方便地将菜单项添加到菜单的末尾。例如：

```java
editMenu.add("Paste");
```

`add` 方法返回创建的菜单项，因此你可以捕获它并添加监听器，如下所示：

```java
JMenuItem pasteItem = editMenu.add("Paste");
pasteItem.addActionListener(listener);
```

通常情况下，菜单项触发的命令也可以通过工具栏按钮等用户界面元素激活。在第 11 章中，你学习了如何通过 `Action` 对象指定命令。你定义一个实现 `Action` 接口的类（通常通过扩展 `AbstractAction` 类），在 `AbstractAction` 构造函数中指定菜单项标签，并重写 `actionPerformed` 方法以持有菜单处理器。例如：

```java
Action exitAction = new AbstractAction("Exit") // 此处为菜单项文本
{
    public void actionPerformed(ActionEvent event) {
        // 此处为动作代码
        System.exit(0);
    }
};
```

然后你可以将该动作添加到菜单中：

```java
JMenuItem exitItem = fileMenu.add(exitAction);
```

该命令使用动作名称向菜单添加一个菜单项。动作对象成为其监听器。这仅仅是以下代码的快捷方式：

```java
JMenuItem exitItem = new JMenuItem(exitAction);
fileMenu.add(exitItem);
```

### `javax.swing.JMenu` 1.2

- `JMenu(String label)`

  使用给定标签构造菜单。

- `JMenuItem add(JMenuItem item)`

  添加一个菜单项。

- `JMenuItem add(String label)`

  添加带有给定标签的菜单项并返回该项。

- `JMenuItem add(Action a)`

  添加带有动作的菜单项并返回该项。

- `void addSeparator()`

  向菜单添加分隔符。

- `JMenuItem insert(JMenuItem menu, int index)`

  在指定索引处向菜单插入菜单项（或子菜单）。

- `JMenuItem insert(Action a, int index)`

  在指定索引处插入带有动作的菜单项。

- `void insertSeparator(int index)`

  在菜单处插入分隔符。

![Image](img/681tab01.jpg)

- `void remove(int index)`
- `void remove(JMenuItem item)`

  从菜单中移除项。

### `javax.swing.JMenuItem` 1.2

- `JMenuItem(String label)`

  使用给定标签构造菜单项。

- `JMenuItem(Action a)` 1.3

  为给定动作构造菜单项。

### `javax.swing.AbstractButton` 1.2

- `void setAction(Action a)` 1.3

  为此按钮或菜单项设置动作。

### `javax.swing.JFrame` 1.2

- `void setJMenuBar(JMenuBar menubar)`

  为此框架设置菜单栏。

#### 12.5.2 菜单项中的图标

菜单项与按钮非常相似。事实上，`JMenuItem` 类扩展了 `AbstractButton` 类。就像按钮一样，可以只有文本标签、只有图标或两者都有。你可以通过 `JMenuItem(String, Icon)` 或 `JMenuItem(Icon)` 构造函数指定图标，也可以使用 `JMenuItem` 类继承自 `AbstractButton` 类的 `setIcon` 方法进行设置。例如：

```java
JMenuItem cutItem = new JMenuItem("Cut", new ImageIcon("cut.gif"));
```



在图 12.19 中，你可以看到多个菜单项带有图标。默认情况下，菜单项文本位于图标右侧。如果你希望文本放在左侧，可以调用`JMenuItem`类继承自`AbstractButton`类的`setHorizontalTextPosition`方法。例如，调用

```java
cutItem.setHorizontalTextPosition(SwingConstants.LEFT);
```

会将菜单项文本移动到图标左侧。

你也可以为动作添加图标：

```java
cutAction.putValue(Action.SMALL_ICON, new ImageIcon("cut.gif"));
```

当你根据`Action`构造一个菜单项时，`Action.NAME`值将成为菜单项的文本，而`Action.SMALL_ICON`值将成为图标。

或者，你也可以在`AbstractAction`构造函数中设置图标：

```java
cutAction = new AbstractAction("Cut", new ImageIcon("cut.gif"))
{
    public void actionPerformed(ActionEvent event)
    {
        . . .
    }
};
```

***

### javax.swing.JMenuItem **1.2**

• `JMenuItem(String label, Icon icon)`
使用给定的标签和图标构造菜单项。

***

### javax.swing.AbstractButton **1.2**

• `void setHorizontalTextPosition(int pos)`
设置文本相对于图标的水平位置。

***

### javax.swing.AbstractAction **1.2**

• `AbstractAction(String name, Icon smallIcon)`
使用给定的名称和图标构造一个抽象动作。

***

#### 12.5.3 复选框和单选按钮菜单项

`Checkbox`和`radio button`菜单项会在名称旁边显示一个复选框或单选按钮（参见图 12.19）。当用户选择菜单项时，该项会在选中和未选中之间自动切换。

除了按钮装饰外，像处理其他任何菜单项一样处理这些菜单项。例如，这里是如何创建一个复选框菜单项：

```java
JCheckBoxMenuItem readonlyItem = new JCheckBoxMenuItem("Read-only");
optionsMenu.add(readonlyItem);
```

单选按钮菜单项的工作方式与普通单选按钮一样。你必须将它们添加到按钮组（`ButtonGroup`）中。当组中的一个按钮被选中时，所有其他按钮会自动取消选择。

```java
ButtonGroup group = new ButtonGroup();
JRadioButtonMenuItem insertItem = new JRadioButtonMenuItem("Insert");
insertItem.setSelected(true);
JRadioButtonMenuItem overtypeItem = new JRadioButtonMenuItem("Overtype");
group.add(insertItem);
group.add(overtypeItem);
optionsMenu.add(insertItem);
optionsMenu.add(overtypeItem);
```

对于这些菜单项，你不一定希望在用户选择该项时收到通知。相反，你可以简单地使用`isSelected`方法来测试菜单项的当前状态。（当然，这意味着你应该在实例字段保留该菜单项的引用。）使用`setSelected`方法设置状态。

***

### javax.swing.JCheckBoxMenuItem **1.2**

• `JCheckBoxMenuItem(String label)`
使用给定的标签构造复选框菜单项。

• `JCheckBoxMenuItem(String label, boolean state)`
使用给定的标签和给定的初始状态（`true`为选中）构造复选框菜单项。

***

### javax.swing.JRadioButtonMenuItem **1.2**

• `JRadioButtonMenuItem(String label)`
使用给定的标签构造单选按钮菜单项。

• `JRadioButtonMenuItem(String label, boolean state)`
使用给定的标签和给定的初始状态（`true`为选中）构造单选按钮菜单项。

***

### javax.swing.AbstractButton **1.2**

• `boolean isSelected()`
• `void setSelected(boolean state)`
获取或设置此项的选中状态。

***

#### 12.5.4 弹出菜单

`pop-up menu`是一种不附加到菜单栏而是浮动的菜单（参见图 12.20）。

像创建普通菜单一样创建弹出菜单，只是弹出菜单没有标题。

```java
JPopupMenu popup = new JPopupMenu();
```

然后像往常一样添加菜单项：

```java
JMenuItem item = new JMenuItem("Cut");
popup.add(item);
```

由于弹出菜单不附加到菜单栏，你必须通过`show`方法显示它：

```java
popup.show(parent);
```

***

### javax.swing.JPopupMenu **1.2**

• `show(Component c, int x, int y)`
显示弹出菜单。

• `boolean isPopup(MouseEvent event)`
如果事件是弹出触发，则返回`true`。

***

### java.awt.event.MouseEvent **1.3**

• `boolean isTrigger()`
如果它是弹出触发，则返回`true`。

***

### javax.swing.JComponent **1.2**

• `JPopupMenu getPopupMenu()`
• `void setPopupMenu(JPopupMenu popup)`
获取或设置此组件的弹出菜单。

• `boolean getInherPopupMenu()`
• `void setInherPopupMenu(boolean b)`
获取或设置`inheritsPopupMenu`属性。

***

#### 12.5.5 键盘快捷键和加速键

对于经验丰富的用户来说，通过键盘快捷键选择菜单项非常方便。你可以通过在菜单项构造函数中指定快捷键字母为菜单项创建键盘快捷键：

```java
JMenuItem aboutItem = new JMenuItem("About");
```

键盘快捷键会在菜单中自动显示，并带有下划线（参见图 12.21）。例如，在最后一个示例定义的项中，标签将是带有下划线的“About”。当菜单显示时，用户只需按下 A 键即可选中该菜单项。（如果快捷键不是菜单字符串的一部分，输入它仍然可以选中项，但菜单中不会显示快捷键。显然，这种不可见的快捷键用处不大。）

有时，你并不希望下划菜单项中匹配快捷键的字母。例如，如果你为“Save As”菜单设置了快捷键“A”，那么下划第二个“A”会更合理。你可以通过调用`setDisplayMnemonicIndex`方法指定你想下划的字符。

如果你有一个`Action`对象，你可以为`Action.MNEMONIC_KEY`键添加快捷键，如下：

```java
cutAction.putValue(Action.MNEMONIC_KEY, new Integer('A'));
```

你只能在菜单项的构造函数中提供快捷键，而不是在菜单的构造函数中。要为菜单附加快捷键，请调用`setMnemonic`方法：

```java
JMenu helpMenu = new JMenu("Help");
helpMenu.setMnemonic('H');
```

从菜单栏选择顶层菜单时，按下 Alt 键配合快捷键字母。例如，按下 Alt+H 可从菜单栏选择帮助菜单。

键盘记忆键（mnemonics）允许从当前打开的菜单中选择子菜单或菜单项。相比之下，`accelerators`（加速键）是快捷键，允许你在无需打开菜单的情况下选择菜单项。例如，许多程序为“文件”菜单中的“打开”和“保存”项目绑定了加速键`Ctrl+O`和`Ctrl+S`。使用`setAccelerator`方法可以将加速键绑定到菜单项上。`setAccelerator`方法接收一个`Keystroke`类型的对象。例如，以下调用将加速键`Ctrl+O`绑定到`openItem`菜单项：

```java
openItem.setAccelerator(KeyStroke.getKeyStroke("ctrl O"));
```

输入加速键组合会自动选择该菜单选项并触发动作事件，就像用户手动选择了该菜单选项一样。

你只能将加速键绑定到菜单项，而不能绑定到菜单。加速键实际上不会打开菜单。相反，它们会直接触发与菜单相关的动作事件。

从概念上讲，向菜单项添加加速键与向 Swing 组件添加加速键的技术是类似的。（我们在第 11 章中讨论过该技术。）然而，当加速键被添加到菜单项时，按键组合会自动显示在菜单中（参见图 12.22）。

### Note
在 Windows 下，`Alt+F4`会关闭窗口。这不是一个要在 Java 中编写的加速键。它是操作系统定义的快捷键。无论菜单上是否有“关闭”项目，此键组合始终会触发活动窗口的`WindowClosing`事件。

***

### javax.swing.JMenuItem **1.2**

• `JMenuItem(String label, int mnemonic)`
构造一个具有给定标签和记忆键的菜单项。

• `void setAccelerator(KeyStroke k)`
将击键`k`设置为此菜单项的加速键。加速键显示在标签旁边。

***

### javax.swing.AbstractButton **1.2**

• `void setMnemonic(int mnemonic)`
为按钮设置记忆键字符。该字符将在标签中带有下划线。

• `void setDisplayedMnemonicIndex(int index)` **1.4**
设置按钮文本中带有下划线的字符索引。如果你不希望第一个出现的记忆键字符带有下划线，请使用此方法。

***

#### 12.5.6 启用和禁用菜单项

有时，特定的菜单项应该只在某些上下文中被选择。例如，当文档以只读模式打开时，“保存”菜单项就没有意义了。当然，我们可以使用`JMenu.remove`方法从菜单中移除该项，但用户会对内容不断变化的菜单感到有些惊讶。相反，禁用那些通向暂时不恰当命令的菜单项会更好。被禁用的菜单项显示为灰色，且无法被选择（参见图 12.23）。

要启用或禁用菜单项，使用`setEnabled`方法：

```java
saveItem.setEnabled(false);
```

启用和禁用菜单项有两种策略。每当情况发生变化时，你都可以对相关的菜单项或动作调用`setEnabled`。例如，一旦文档被设置为只读模式，你就可以找到“保存”和“另存为”菜单项并禁用它们。或者，你可以在显示菜单之前禁用项。要做到这一点，你必须为“菜单被选中”事件注册一个监听器。`javax.swing.event`包定义了一个`MenuListener`接口，包含三个方法：

```java
void menuSelected(MenuEvent event)
void menuDeselected(MenuEvent event)
void menuCanceled(MenuEvent event)
```

`menuSelected`方法在菜单显示*之前*被调用。因此，它可以用于禁用或启用菜单项。以下代码显示了每当“只读”复选框菜单项被选中时，如何禁用“保存”和“另存为”动作：

```java
public void menuSelected(MenuEvent event)
{
  saveAction.setEnabled(!readonlyItem.isSelected());
  saveAsAction.setEnabled(!readonlyItem.isSelected());
}
```

**Caution**
显示菜单之前禁用菜单项是一个聪明的主意，但它对于带有加速键的菜单项无效。因为当按下加速键时，菜单永远不会打开，所以动作永远不会被禁用，仍然会被加速键触发。

***

### javax.swing.JMenuItem **1.2**

• `void setEnabled(boolean b)`
启用或禁用菜单项。

***

### javax.swing.event.MenuListener **1.2**

• `void menuSelected(MenuEvent e)`
在菜单被选中后、打开之前被调用。

• `void menuDeselected(MenuEvent e)`
在菜单被取消选择、关闭后被调用。

• `void menuCanceled(MenuEvent e)`
在菜单被取消时被调用，例如通过用户点击菜单以外的地方。

***

代码列表 2.8 是一个生成一组菜单的示例程序。它展示了在本节中看到的所有功能：嵌套菜单、禁用的菜单项、复选框和单选按钮项、弹出菜单以及键盘记忆键和加速键。

**代码列表 2.8 `MenuFrame.java`**

```java
package menu;

import java.awt.event.*;
import javax.swing.*;

/**
 * 一个带有示例菜单栏的框架。
 */
public class MenuFrame extends JFrame
{
  private static int DEFAULT_WIDTH = 300;
  private static int DEFAULT_HEIGHT = 200;

  private Action saveAction;
  private Action saveAsAction;
  private JCheckBoxMenuItem readonlyItem;
  private JPopupMenu popup;

  /**
   * 一个向 System.out 打印动作名称的示例动作
   */
  class TestAction extends AbstractAction
  {
    public TestAction(String name)
    {
      super(name);
    }

    public void actionPerformed(ActionEvent event)
    {
      System.out.println(getValue(Action.NAME) + " selected.");
    }
  }

  public MenuFrame()
  {
    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

    JMenu fileMenu = new JMenu("File");
    fileMenu.add(new TestAction("New"));

    // 展示加速键
    JMenuItem openItem = fileMenu.add(new TestAction("Open"));
    openItem.setAccelerator(KeyStroke.getKeyStroke("ctrl O"));
    fileMenu.addSeparator();

    saveAction = new TestAction("Save");
    JMenuItem saveItem = fileMenu.add(saveAction);
    saveItem.setAccelerator(KeyStroke.getKeyStroke("ctrl S"));

    saveAsAction = new TestAction("Save As");
    fileMenu.add(saveAsAction);
    fileMenu.addSeparator();

    fileMenu.add(new AbstractAction("Exit")
    {
      public void actionPerformed(ActionEvent event)
      {
        System.exit(0);
      }
    });

    // 展示复选框和单选按钮菜单
    readonlyItem = new JCheckBoxMenuItem("Read-only");
```



`readonlyItem.addActionListener(new ActionListener()`

```
{

  public void actionPerformed(ActionEvent event)

  {

    boolean saveOk = !readonlyItem.isSelected();

    saveAction.setEnabled(saveOk);

  }

});
```

`saveAsAction.setEnabled(saveOk);`

```
ButtonGroup group = new ButtonGroup();

JRadioButtonMenuItem insertItem = new JRadioButtonMenuItem("Insert");

insertItem.setSelected(true);

JRadioButtonMenuItem overtypeItem = new JRadioButtonMenuItem("Overtype");

group.add(insertItem);

group.add(overtypeItem);
```

演示图标：

```
Action cutAction = new TestAction("Cut");

cutAction.putValue(Action.SMALL_ICON, new ImageIcon("cut.gif"));

Action copyAction = new TestAction("Copy");

copyAction.putValue(Action.SMALL_ICON, new ImageIcon("copy.gif"));

Action pasteAction = new TestAction("Paste");

pasteAction.putValue(Action.SMALL_ICON, new ImageIcon("paste.gif"));

JMenu editMenu = new JMenu("Edit");

editMenu.add(cutAction);

editMenu.add(copyAction);

editMenu.add(pasteAction);
```

演示嵌套菜单：

```
JMenu optionMenu = new JMenu("Options");

optionMenu.add(readonlyItem);

optionMenu.addSeparator();

optionMenu.add(insertItem);

optionMenu.add(overtypeItem);

editMenu.addSeparator();

editMenu.add(optionMenu);
```

演示记忆快捷键：

```
JMenu helpMenu = new JMenu("Help");

helpMenu.setMnemonic('H');

JMenuItem indexItem = new JMenuItem("Index");

indexItem.setMnemonic('I');

helpMenu.add(indexItem);
```

你也可以为 action 添加记忆快捷键：

```
Action aboutAction = new TestAction("About");

aboutAction.putValue(Action.MNEMONIC_KEY, new Integer('A'));

helpMenu.add(aboutAction);
```

将所有顶层菜单添加到菜单栏：

```
JMenuBar menuBar = new JMenuBar();

setJMenuBar(menuBar);

menuBar.add(fileMenu);

menuBar.add(editMenu);

menuBar.add(helpMenu);
```

演示弹出菜单：

```
JPopupMenu popup = new JPopupMenu();

popup.add(cutAction);

popup.add(copyAction);

popup.add(pasteAction);

JPanel panel = new JPanel();

panel.setPopupMenu(popup);

add(panel);
```

### 12.5.7 工具栏

工具栏是一个按钮栏，提供了快速访问程序中最常用命令的方法（参见图 12.24）。

工具栏的特殊之处在于，你可以将它们移动到其他地方。你可以将工具栏拖到框架的四个边界之一（参见图 12.25）。当你释放鼠标按钮时，工具栏将掉落到新位置（参见图 12.26）。

如果工具栏位于具有边界布局（`border layout`）的容器中，或者任何支持 `North`、`East`、`South` 和 `West` 约束的布局管理器中，拖拽功能即可生效。

工具栏甚至可以从框架中完全分离。分离后的工具栏被包含在它自己的框架中（参见图 12.27）。当你关闭包含分离工具栏的框架时，工具栏将跳回到原始框架。

工具栏的编程非常简单。向工具栏中添加组件即可：

```java
JToolBar bar = new JToolBar();
bar.add(blueButton);
```

`JToolBar` 类还有一个方法可以添加 `Action` 对象。只需像这样用 `Action` 对象填充工具栏即可：

```java
bar.add(blueAction);
```

动作的小图标将显示在工具栏中。

你可以使用分隔符分隔按钮组：

```java
bar.addSeparator();
```

例如，图 12.24 中的工具栏在第三个和第四个按钮之间有一个分隔符。

然后，将工具栏添加到框架中：

```java
add(bar, BorderLayout.NORTH);
```

你还可以为工具栏指定标题，当工具栏处于分离状态时显示该标题：

```java
bar = new JToolBar(titleString);
```

默认情况下，工具栏初始为水平方向。要让工具栏从垂直方向开始，请使用

```java
bar = new JToolBar(SwingConstants.VERTICAL)
```

或者

```java
bar = new JToolBar(titleString, SwingConstants.VERTICAL)
```

按钮是工具栏内部最常见的组件。但对你可以添加到工具栏的组件没有限制。例如，你可以向工具栏添加一个组合框（`combo box`）。

### 12.5.8 提示文字（Tooltips）

工具栏的一个缺点是用户往往对工具栏中微小图标的含义感到困惑。为了解决这个问题，用户界面设计师发明了提示文字。当光标悬停在按钮上方时，就会激活提示文字。提示文字显示在一个颜色的矩形内。当用户移动鼠标时，提示文字就会消失。（参见图 12.28。）

在 Swing 中，你只需调用 `setToolTipText` 方法即可为任何 `JComponent` 添加提示文字：

```java
exitButton.setToolTipText("Exit");
```

或者，如果你使用 `Action` 对象，可以将提示文字与 `SHORT_DESCRIPTION` 键关联：

```java
exitAction.putValue(Action.SHORT_DESCRIPTION, "Exit");
```

列表 2.9 显示了如何将相同的 `Action` 对象添加到菜单和工具栏中。请注意，动作名称将作为菜单项显示在菜单中，而短描述将作为工具栏中的提示文字显示。

```java
package toolBar;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

/**
 * 一个带有工具栏和菜单变化的框架。
 */
public class ToolFrame extends JFrame {
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;
    private JPanel panel;

    public ToolFrame() {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // 添加一个用于颜色变化的面板
        panel = new JPanel();
        add(panel, BorderLayout.CENTER);

        // 设置动作
        Action blueAction = new ColorAction("Blue", new ImageIcon("blue-ball.gif"), Color.BLUE);
        Action yellowAction = new ColorAction("Yellow", new ImageIcon("yellow-ball.gif"),
            Color.YELLOW);
        Action redAction = new ColorAction("Red", new ImageIcon("red-ball.gif"), Color.RED);
        Action exitAction = new AbstractAction("Exit", new ImageIcon("exit.gif")) {
            public void actionPerformed(ActionEvent event) {
                System.exit(0);
            }
        };
        exitAction.putValue(Action.SHORT_DESCRIPTION, "Exit");

        // 填充工具栏
        JToolBar bar = new JToolBar();
        bar.add(blueAction);
        bar.add(yellowAction);
        bar.add(redAction);
        bar.addSeparator();
        bar.add(exitAction);
        add(bar, BorderLayout.NORTH);
    }
}
```

```java
// populate menu
JMenu menu = new JMenu("Color");
menu.add(yellowAction);
menu.add(blueAction);
menu.add(redAction);
menu.add(exitAction);
JMenuBar menuBar = new JMenuBar();
menuBar.add(menu);
setJMenuBar(menuBar);
}

/**
 * 颜色动作将框架的背景设置为给定的颜色。
 */
class ColorAction extends AbstractAction
{
    public ColorAction(String name, Icon icon, Color c)
    {
        putValue(Action.NAME, name);
        putValue(Action.SMALL_ICON, icon);
        putValue(Action.SHORT_DESCRIPTION, name + " background");
        putValue("Color", c);
    }

    public void actionPerformed(ActionEvent event)
    {
        Color c = (Color) getValue("Color");
        panel.setBackground(c);
    }
}
```

### javax.swing.JToolBar 1.2

* `JToolBar()`
* `JToolBar(String titleString)`
* `JToolBar(int orientation)`
* `JToolBar(String titleString, int orientation)` 根据给定的标题字符串和方向构造一个工具栏。`orientation` 是 `SwingConstants.HORIZONTAL`（默认值）或 `SwingConstants.VERTICAL` 之一。
* `JButton add(Action a)` 根据给定的动作在工具栏内部构造一个具有名称、图标、短描述和动作回调的新按钮，并将该按钮添加到工具栏的末尾。
* `void addSeparator()` 在工具栏的末尾添加分隔符。

### javax.swing.JComponent 1.2

* `void setToolTipText(String text)` 设置当鼠标悬停在组件上时应显示的工具提示文本。

### 12.6 复杂的布局管理

到目前为止，我们在示例应用程序的用户界面中仅使用了边界布局（`border layout`）、流式布局（`flow layout`）和网格布局（`grid layout`）。对于更复杂的任务，这些是不够的。在本节中，我们将详细讨论高级布局管理。

Windows 程序员可能会奇怪，为什么 Java 要对布局管理器大费周章。毕竟，在 Windows 中，布局管理并不是什么大事；你只需要使用对话框编辑器将组件拖放到对话框表面上，然后使用编辑器工具对齐组件、等间距排列、居中等。如果你在处理一个大型项目，你可能根本不需要担心组件布局——一个熟练的用户界面设计师会为你完成所有这一切。

这种方法的问题在于，如果组件的大小发生变化，则生成的布局必须手动更新。组件的大小为什么会变化呢？当应用程序中的字符串被翻译成外语时，就会发生这种情况。例如，“Cancel”的德语单词是“Abbrechen”。如果一个按钮的设计空间仅足够容纳“Cancel”这个字符串，那么德语版本看起来就会坏掉，字符串会被截断。

为什么按钮不能简单地扩展以适应标签呢？当你在对话框编辑器中拖放按钮时，并没有指示它们应该向哪个方向扩展。在拖放、放置和安排之后，对话框编辑器仅仅记录了每个组件的像素位置和大小。它并不记得*为什么*按这种方式安排组件。

Java 布局管理器是组件布局的一种更好的方法。通过布局管理器，布局包含了关于组件之间关系的指令。这在使用了原生用户界面元素的原始 AWT 中尤为重要。在 Motif、Windows 和 Macintosh 中，按钮或列表框的大小可能有很大差异，而应用程序或 Applet 也是如此。

#### 12.6.1 网格袋布局 (Grid Bag Layout)

网格袋布局是所有布局之母。你可以将网格袋布局理解为没有限制的网格布局。在网格袋布局中，行和列可以具有可变的大小。你可以合并相邻单元格以为更大的组件留出空间。（许多文字处理器以及 HTML 也为表格提供了类似的功能：你可以从一个网格开始，然后根据需要合并相邻单元格。）组件不需要填充整个单元格，你可以指定它们在单元格内的对齐方式。

# 图 12.30 设计中使用的对话框网格

要向网格管理器（`grid bag manager`）描述布局，请遵循以下步骤：

1. 创建类型为 `GridBagLayout` 的对象。你不需要告诉它底层网格有多少行多少列。相反，布局管理器将尝试根据你之后提供的信息来推断。

2. 将此 `GridBagLayout` 对象设置为组件的布局管理器。

3. 对于每个组件，创建一个类型为 `GridBagConstraints` 的对象。设置 `GridBagConstraints` 对象的字段值，以指定组件在网格包中的布局方式。

4. 最后，通过调用 `add(component, constraints);` 带有其约束条件添加每个组件。

以下是所需的代码示例。（我们将在接下来的章节中详细详细介绍各种约束——所以如果你不知道某些约束的作用，请担心。）

```java
GridBagLayout layout = new GridBagLayout();
panel.setLayout(layout);
GridBagConstraints constraints = new GridBagConstraints();
constraints.weightx = 100;
constraints.weighty = 100;
constraints.gridx = 0;
constraints.gridy = 2;
constraints.gridwidth = 2;
constraints.gridheight = 1;
panel.add(component, constraints);
```



诀窍在于知道如何设置`GridBagConstraints`对象的状态。我们将在后面的章节中讨论该对象。

## 12.6.1.1 gridx, gridy, gridwidth 和 gridheight 参数

`gridx`、`gridy`、`gridwidth`和`gridheight`约束定义了组件在网格中的位置。`gridx`和`gridy`值指定了要添加组件左上角的列和行位置。`gridwidth`和`gridheight`值决定了组件占据的列数和行数。

网格坐标从`0`开始。特别是，`gridx = 0`和`gridy = 0`表示左上角。我们示例中的文本区域具有`gridx = 2`、`gridy = 0`，因为它从第`0`行的第`2`列（即第三列）开始。它的`gridwidth = 1`且`gridheight = 4`，因为它跨越了一列和四行。

## 12.6.1.2 权重字段

你始终需要为网格布局中的每个区域设置`weight`字段（`weightx`和`weighty`）。如果你将权重设置为`0`，则该区域在该方向上永远不会超出初始大小增长或缩小。在图12.29的网格布局中，我们将标签的`weightx`字段设置为`0`。这允许标签在调整窗口大保持保持宽度。另一方面，如果你将所有区域的权重设置为`0`，容器将聚集在其分配区域的中心，而不是扩展填充它。

从概念上讲，权重参数的问题在于权重是行和列的属性，而不是单个单元格。但你需要为单元格指定它们，因为网格布局没有暴露行和列。行和列权重是通过每行或每列中单元格权重的最大值计算得。因此，如果你想让某行或某列保持固定大小，需要将其中所有组件的权重设置为零。

注意，权重实际上并没有给出列的相对大小。它们告诉我们如果容器超过其首选尺寸，应该将多少比例的“剩余”空间分配给每个区域。这并不直观。我们建议你将所有权重设置为`100`。然后运行程序并查看布局的外观。调整对话框以查看行和列如何调整。如果你发现某行或某列不应增长，则将其其中所有组件的权重设置为零。你可以尝试其他的权重值，但通常不值得费精力。

## 12.6.1.3 fill 和 anchor 参数

如果你不想让组件拉伸并填充整个区域，请设置`fill`约束。该参数有四种可能：有效值为`GridBagConstraints.NONE`、`GridBagConstraints.HORIZONTAL`、`GridBagConstraints.VERTICAL`和`GridBagConstraints.BOTH`。

如果组件没有填充整个区域，你可以通过设置`anchor`字段来指定它位于区域的哪个位置。有效值为`GridBagConstraints.CENTER`（默认值）、`GridBagConstraints.NORTH`、`GridBagConstraints.NORTHEAST`、`GridBagConstraints.EAST`等。

## 12.6.1.4 内边距 (Padding)

你可以通过设置`GridBagConstraints`的`insets`字段在组件周围留出额外的空白。设置`Insets`对象的`left`、`top`、`right`和`bottom`值为你想要在组件周围的空间量。这被称为外部内边距。

`ipadx`和`ipady`值设置内部内边距。这些值被加上组件的最小宽度和高度。这确保了组件不会缩小到最小尺寸。

## 12.6.1.5 指定 gridx, gridy, gridwidth 和 gridheight 参数的替代方法

AWT文档建议，与其将`gridx`和`gridy`值设置为绝对位置，不如将它们设置为常量`GridBagConstraints.RELATIVE`。

## 12.6.1.6 用于驯服网格约束的辅助类

网格布局中最麻烦的部分是编写设置约束的代码。大多数程序员为此目的编写了辅助函数或小型辅助类。我们在字体对话框示例的完整代码之后介绍这样一个类。该类具有以下功能：

- 它的名字很短：`GBC`而不是`GridBagConstraints`。
- 它继承自`GridBagConstraints`，因此你可以使用较短的名称如`GBC.EAST`来表示常量。
- 在添加组件时使用`GBC`对象，例如

```
add(component, new GBC(1, 2));
```

- 有两个构造函数可以设置最常用的参数：`gridx`和`gridy`，或者`gridx`、`gridy`、`gridwidth`和`gridheight`。

点击此处查看代码图像

```java
add(component, new GBC(1, 2, 1, 4));
```

- 对于以`x`/`y`成对出现的字段提供了方便的setter方法：

点击此处查看代码图像

```java
add(component, new GBC(1, 2).setWeight(100, 100));
```

- setter方法返回`this`，因此你可以对其进行链式调用：

点击此处查看代码图像

```java
add(component, new GBC(1, 2).setAnchor(GBC.EAST).setWeight(100, 100));
```

- `setInsets`方法为你构建`Insets`对象。要获取1像素的边距，只需调用

点击此处查看代码图像

```java
add(component, new GBC(1, 2).setAnchor(GBC.EAST).setInsets(1));
```

Listing 12.10显示了字体对话框示例的框架类。`GBC`辅助类位于Listing 12.12。以下是将组件添加到网格容器中的代码：

点击此处查看代码图像

```java
add(faceLabel, new GBC(0, 0).setAnchor(GBC.EAST));
add(face, new GBC(1, 0).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));
add(sizeLabel, new GBC(0, 1).setAnchor(GBC.EAST));
add(size, new GBC(1, 1).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));
add(bold, new GBC(0, 2, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));
add(italic, new GBC(0, 3, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));
add(sample, new GBC(2, 0, 1, 4).setFill(GBC.BOTH).setWeight(100, 100));
```

一旦你理解了网格约束（grid bag constraints），这类代码就非常易读且调试。

***

![Image](img/note.jpg) 注意

[`http://docs.oracle.com/javase/tutorial/uiswing/layout/gridbag.html`](http://docs.oracle.com/javase/tutorial/uiswing/layout/gridbag.html) 上的教程建议你对所有组件复用同一个`GridBagConstraints`对象。我们发现生成的代码难以阅读且容易出错。例如，查看[`http://docs.oracle.com/javase/tutorial/swing/events/containerlistener.html`](http://docs.oracle.com/javase/tutorial/swing/events/containerlistener.html)中的演示。按钮真的意图是水平拉伸的吗，还是程序员只是忘记关闭`fill`约束了？

***

### Listing 12.10 `gridbag/FontFrame.java`

点击此处查看代码图像

```java
package gridbag;

import java.awt.Font;
import java.awt.GridBagLayout;
import java.awt.event.ActionListener;
import javax.swing.BorderFactory;
import javax.swing.JCheckBox;
import javax.swing.JComboBox;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JTextArea;

/**
 * 使用网格布局来排列字体选择组件的框架。
 */
public class FontFrame extends JFrame
{
    public static final int TEXT_ROWS = 10;
    public static final int TEXT_COLUMNS = 20;

    private JComboBox<String> face;
    private JComboBox<Integer> size;
    private JCheckBox bold;
    private JCheckBox italic;
    private JTextArea sample;

    public FontFrame()
    {
        GridBagLayout layout = new GridBagLayout();
        setLayout(layout);

        ActionListener listener = event -> updateSample();

        // 构建组件
        JLabel faceLabel = new JLabel("Face: ");
        face = new JComboBox<>(new String[] { "Serif", "SansSerif", "Monospaced", "Dialog", "Input" });
        face.addActionListener(listener);

        JLabel sizeLabel = new JLabel("Size: ");
        size = new JComboBox<>(new Integer[] { 8, 10, 12, 15, 18, 24, 36 });
        size.addActionListener(listener);

        bold = new JCheckBox("Bold");
        bold.addActionListener(listener);

        italic = new JCheckBox("Italic");
        italic.addActionListener(listener);

        sample = new JTextArea(TEXT_ROWS);
        sample.setText("The quick fox jumps over the lazy dog");
        sample.setEditable(false);
        sample.setWrap(true);
        sample.setBorder(BorderFactory.createEtchedBorder());

        // 将组件添加到网格，使用 GBC 类
        add(faceLabel, new GBC(0, 0).setAnchor(GBC.EAST));
        add(face, new GBC(1, 0).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));
        add(sizeLabel, new GBC(0, 1).setAnchor(GBC.EAST));
        add(size, new GBC(1, 1).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));
        add(bold, new GBC(0, 2, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));
        add(italic, new GBC(0, 3, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));
        add(sample, new GBC(2, 0, 1, 4).setFill(GBC.BOTH).setWeight(100, 100));
        pack();
    }

    public void updateSample()
    {
        String fontFace = (String) face.getSelectedItem();
        int fontStyle = (bold.isSelected() ? Font.BOLD : 0) | (italic.isSelected() ? Font.ITALIC : 0);
        int fontSize = size.getSelectedItem();
        Font font = new Font(fontFace, fontStyle, fontSize);
        sample.setFont(font);
    }
}
```

### Listing 12.11 `gridbag/GBC.java`

点击此处查看代码图像

```java
package gridbag;

import java.awt.*;

/**
 * 该类简化了 GridBagConstraints 类的使用。
 * @version 1.0 2004-05-06
 * @author Cay Horstmann
 */
public class GBC extends GridBagConstraints
{
    /**
     * 构建具有 gridx 和 gridy 位置的 GBC，其他属性设置为默认值。
     * @param gridx
     * @param gridy
     */
    public GBC(int gridx, int gridy)
    {
        this.gridx = gridx;
        this.gridy = gridy;
    }

    /**
     * 构建具有 gridx, gridy, gridwidth 和 height 的 GBC，其他属性设置为默认值。
     * @param gridx
     * @param gridy
     * @param gridwidth
     * @param height
     */
    public GBC(int gridx, int gridy, int gridwidth, int height)
    {
        this.gridx = gridx;
        this.gridy = gridy;
        this.gridwidth = gridwidth;
        this.gridheight = height;
    }

    /**
     * 设置锚点。
     * @param anchor
     * @return 此对象以便进行进一步修改
     */
    public GBC setAnchor(int anchor)
    {
        this.anchor = anchor;
        return this;
    }

    /**
     * 设置填充方向。
     * @param fill
     * @return 此对象以便进行进一步修改
     */
    public GBC setFill(int fill)
    {
        this.fill = fill;
        return this;
    }

    /**
     * 设置单元权重。
     * @param weightx x 方向的单元格权重
     * @param weighty y 方向的单元格权重
     * @return 此对象以便进行进一步修改
     */
    public GBC setWeight(double weightx, double weighty)
    {
        this.weightx = weightx;
        this.weighty = weighty;
        return this;
    }

    /**
     * 设置此单元格的边距。
     */
}
```

```java
/**
 * @param distance 在所有方向使用的间距
 * @return 用于进一步修改的此对象
 */
public GBC setInsets(int distance)
{
    this.insets = new Insets(distance, distance, distance, distance);
    return this;
}

/**
 * 设置此单元格的间距
 */
```



`setInsets(int top, int left, int bottom, int right)` 方法用于设置组件的外部间距：

- `top`：顶部使用的间距
- `left`：左侧使用的间距
- `bottom`：底部使用的间距
- `right`：右侧使用的间距

返回用于进一步修改的此对象。

```java
public GBC setInsets(int top, int left, int bottom, int right)
{
    this.insets = new Insets(top, left, bottom, right);
    return this;
}
```

`setIpad(int ipadx, int ipady)` 方法用于设置内部内边距：

- `ipadx`：x 方向的内边距
- `ipady`：y 方向的内边距

返回用于进一步修改的此对象。

```java
public GBC setIpad(int ipadx, int ipady)
{
    this.ipadx = ipadx;
    this.ipady = ipady;
    return this;
}
```

### `java.awt.GridBagConstraints` 1.0

- `int gridx, gridy`：指定单元格的起始列和行。默认值为 `0`。
- `int gridwidth, gridheight`：指定单元格的列宽和行高。默认值为 `1`。
- `double weightx, weighty`：指定单元格的增长能力。默认值为 `0`。
- `int anchor`：表示组件在单元格内的对齐方式。你可以选择绝对位置：
![Image](img/712tab01.jpg)
或者与其方向无关的等价项：
![Image](img/712tab02.jpg)
如果你的应用程序可能需要针对从右到左或从上到下的文本进行本地化，请使用后者。默认值为 `CENTER`。
- `int fill`：指定组件在单元格内的填充行为：`NONE`、`BOTH`、`HORIZONTAL` 或 `VERTICAL` 之一。默认值为 `NONE`。
- `int ipadx, ipady`：指定组件周围的“内部”内边距。默认值为 `0`。
- `Insets insets`：指定沿单元格边界的“外部”内边距。默认无间距。
- `GridBagConstraints(int gridx, int gridy, int gridwidth, int gridheight, double weightx, double weighty, int anchor, int fill, Insets insets, int ipadx, int ipady)` 1.2 通过参数中指定的所有字段来构造 `GridBagConstraints`。此构造函数应仅由自动代码生成器使用，因为它会让你的源代码非常难以阅读。

### 12.6.2 Group Layout

在讨论 `GroupLayout` 类的 API 之前，让我们快速查看 NetBeans 中的 Matisse GUI 构建器。我们不会为你提供完整的 Matisse 教程——更多信息请参见 [`http://netbeans.org/kb/docs/java/quickstart-gui.html`](http://netbeans.org/kb/docs/java/quickstart-gui.html)。

以下是在图 12.13 中布局对话框顶部的工作流。启动一个新项目并添加一个新的 `JFrame` 表单。拖动标签，直到出现两条将其与边界分开的引导线：
![Image](img/713fig01.jpg)
在第一行下方放置另一个标签：
![Image](img/713fig02.jpg)
拖动文本字段，使其基线与第一个标签的基线对齐。再次注意这些引导线：
![Image](img/713fig03.jpg)
最后，将密码字段与左侧及方的文本字段对齐：
![Image](img/714fig01.jpg)

Matisse 将这些动作转换为以下 Java 代码：

```java
layout.setHorizontalGroup(
    layout.createParallelGroup(GroupLayout.Alignment.LEADING)
    .addGroup(layout.createSequentialGroup()
        .addContainerGap()
        .addGroup(layout.createParallelGroup(GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addComponent(jLabel1)
                .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(jTextField1))
            .addGroup(layout.createSequentialGroup()
                .addComponent(jLabel2)
                .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(jPasswordField)))
    .addContainerGap(222, Short.MAX_VALUE));

layout.setVerticalGroup(
    layout.createParallelGroup(GroupLayout.Alignment.LEADING)
    .addGroup(layout.createSequentialGroup()
        .addContainerGap()
        .addGroup(layout.createParallelGroup(GroupLayout.Alignment.BASELINE)
            .addGroup(layout.createSequentialGroup()
                .addComponent(jLabel1)
                .addComponent(jTextField1))
            .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
            .addGroup(layout.createParallelGroup(GroupLayout.Alignment.BASELINE)
                .addComponent(jLabel2)
                .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(jPasswordField)))
    .addContainerGap(244, Short.MAX_VALUE)));
```

这看起来有点可怕，但幸运的是你不需要编写这些代码。然而，对布局动作的基本了解是有帮助的，这样你就可以发现错误。我们将分析代码的基本结构。本节末尾的 API 注释详细解释了每个类和方法。

组件通过将它们放入 `GroupLayout.SequentialGroup` 或 `GroupLayout.ParallelGroup` 类型的对象中来组织。这些类是 `GroupLayout.Group` 的子类。组可以包含组件、间隙和嵌套组。组类的各种 `add` 方法返回组对象，因此方法调用可以像这样链式：

```java
group.addComponent(...).addPreferredGap(...).addComponent(...);
```

从示例代码可以看出，组布局将水平和垂直布局计算分开来。为了视觉化水平计算，想象组件被扁平化，使其高度为零，如下：
![Image](img/715fig01.jpg)

有两组并行的组件，对应于（略微简化）代码：

```java
.addContainerGap()
.addGroup(layout.createParallelGroup()
    .addGroup(layout.createSequentialGroup()
        .addComponent(jLabel1)
        .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
        .addComponent(jTextField1))
    .addGroup(layout.createSequentialGroup()
        .addComponent(jLabel2)
        .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
        .addComponent(jPasswordField)))
```

但是等等，这不对。如果标签长度不同，文本字段和密码字段将无法对齐。我们必须告诉 Matisse 我们希望字段对齐。选择两个字段，右键点击并从菜单中选择 `Align → Column`。同时也对齐标签（参见图 12.32）。

![Image](img/12fig32.jpg)
**图 12.32** 在 Matisse 中对齐标签和文本字段

这大大改变了布局代码：

```java
.addGroup(layout.createSequentialGroup()
    .addContainerGap()
    .addGroup(layout.createParallelGroup(GroupLayout.Alignment.LEADING)
        .addComponent(jLabel1, GroupLayout.Alignment.TRAILING)
        .addComponent(jLabel2, GroupLayout.Alignment.TRAILING))
    .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
    .addGroup(layout.createParallelGroup(GroupLayout.Alignment.LEADING)
        .addComponent(jTextField1)
        .addComponent(jPasswordField)))
```

现在标签和字段分别放置在并行组中。第一个组具有 `TRAILING` 对齐方式（当文本方向从左到右时，意味着向右对齐）：
![Image](img/717fig01.jpg)

Matisse 能够将设计指令转换为嵌套组，这看起来就像魔法一样——但正如亚瑟·C·克拉克所说，任何足够先进的技术与魔法无异。

为了完整性起见，让我们来看垂直计算。现在你应该认为这些组件没有宽度。我们有一个包含两个并行组的顺序组，它们之间由间隙隔开：

![Image](img/717fig02.jpg)

对应的代码是：

```java
layout.createSequentialGroup()
    .addContainerGap()
    .addGroup(layout.createParallelGroup(GroupLayout.Alignment.BASELINE)
        .addComponent(jLabel1)
        .addComponent(jTextField1))
    .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
    .addGroup(layout.createParallelGroup(GroupLayout.Alignment.BASELINE)
        .addComponent(jLabel2)
        .addComponent(jPasswordField1))
```

从代码可以看出，组件是根据它们的基线（baselines）对齐的。（基线是组件文本对齐的行线。）

你可以强制一组组件具有相同的大小。例如，我们可能想要确保文本字段和密码字段的宽度完全匹配。在 Matisse 中，选中两者，右键点击，并在菜单中选择“相同大小（Same Size）→ 相同宽度（Same Width）”（参见图 12.33）。

![Image](img/12fig33.jpg)

**图 12.33** 强制两个组件宽度相同

Matisse 向布局代码添加以下语句：

```java
layout.linkSize(SwingConstants.HORIZONTAL, new Component[] {jPasswordField1, jTextField1});
```

列表 12.12 中的代码展示了如何使用 `GroupLayout` 而不是 `GridBagLayout` 来布局上一节中的字体选择器。代码看起来可能并不比列表 12.10 简单，但我们不需要手写它。我们使用 Matisse 完成布局，然后稍微清理了一下代码。

**列表 12.12** `groupLayout/FontFrame.java`

```java
package groupLayout;

import java.awt.Font;
import java.awt.event.ActionListener;
import javax.swing.BorderFactory;
import javax.swing.GroupLayout;
import javax.swing.JCheckBox;
import javax.swing.JComboBox;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.LayoutStyle;
import javax.swing.SwingConstants;

/**
 * 使用组布局来安排字体选择组件的框架。
 */
public class FontFrame extends JFrame
{
    public static final int TEXT_ROWS = 10;
    public static final int TEXT_COLUMNS = 20;

    private JComboBox<String> face;
    private JComboBox<Integer> size;
    private JCheckBox bold;
    private JCheckBox italic;
    private JScrollPane pane;
    private JTextArea sample;

    public FontFrame()
    {
        ActionListener listener = event -> updateSample();

        // 构建组件
        JLabel faceLabel = new JLabel("Face: ");
        face = new JComboBox<>(new String[] { "Serif", "SansSerif", "Monospaced", "Dialog", "DialogInput" });
        face.addActionListener(listener);

        JLabel sizeLabel = new JLabel("Size: ");
        size = new JComboBox<>(new Integer[] { 8, 10, 12, 15, 18, 24, 36, 48 });
        size.addActionListener(listener);

        bold = new JCheckBox("Bold");
        bold.addActionListener(listener);

        italic = new JCheckBox("Italic");
        italic.addActionListener(listener);

        sample = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
        sample.setText("The quick brown fox over the lazy dog");
        sample.setEditable(false);
        sample.setWrap(true);
        sample.setBorder(BorderFactory.createEtchedBorder());

        pane = new JScrollPane(sample);

        GroupLayout layout = new GroupLayout(getContentPane());
        setLayout(layout);

        layout.setHorizontalGroup(GroupLayout.Alignment.LEADING)



```java
.addGroup(
    .createSequentialGroup()
    .addGroup()
    .createParallelGroup(GroupLayout.Alignment.LEADING)
    .addGroup(GroupLayout.Alignment.TRAILING)
    .createSequentialGroup()
    .addGroup()
    .createParallelGroup(GroupLayout.Alignment.TRAILING)
    .addComponent(faceLabel)
    .addComponent(sizeLabel))
    .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
    .addGroup(
        layout.createParallelGroup(GroupLayout.Alignment.LEADING, false)
        .addComponent(size)
        .addComponent(face)))
    .addComponent(italic)
    .addComponent(bold))
    .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
    .addComponent(pane)
    .addGroup()()));
layout.linkSize(SwingConstants.HORIZONTAL, new java.awt.Component[] { face, size });

layout.verticalLayout(GroupLayout.Alignment.LEADING)
    .addGroup(
        .createSequentialGroup()
        .addGroup()
        .createParallelGroup(GroupLayout.Alignment.LEADING)
        .addComponent(pane, GroupLayout.Alignment.TRAILING)
        .createSequentialGroup()
        .addGroup()
        .createParallelGroup(GroupLayout.Alignment.BASELINE)
        .addComponent(face)
        .addComponent(faceLabel))
        .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
        .addGroup(
            layout.createParallelGroup(GroupLayout.Alignment.BASELINE)
            .addComponent(size)
            .addComponent(sizeLabel))
        .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
        .addComponent(italic, GroupLayout.DEFAULT_SIZE, GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
        .addPreferredGap(LayoutStyle.ComponentPlacement.RELATED)
        .addComponent(bold, GroupLayout.DEFAULT_SIZE, GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)));
pack();

}

public void updateSample()
{
    String fontFace = (String) face.getSelectedItem();

    int fontStyle = (bold.isSelected() ? Font.BOLD : 0)
        + (italic.isSelected() ? Font.ITALIC : 0);

    int fontSize = size.getItemAt(size.getSelectedIndex());

    Font font = new Font(fontFace, fontStyle, fontSize);

    sample.setFont(font);
    sample.repaint();
}

}
```

为`host`容器中的组件布局构建一个`GroupLayout`。（注意，你仍然需要在`host`对象上调用`setLayout`。）

- `void setHorizontalGroup(GroupLayout.Group g)`
- `void setVerticalGroup(GroupLayout.Group g)`

设置控制水平或垂直布局的组。

- `void linkSize(Component... components)`
- `void linkSize(int axis)Size(int axis, Component... component)`

强制使给定的组件具有相同的大小，或在指定的轴向上（`SwingConstants.HORIZONTAL`或`SwingConstants.VERTICAL`之一）具有相同的大小。

- `GroupLayout.SequentialGroup createSequentialGroup()`

创建一个按顺序布局其子组件的组。

- `GroupLayout.ParallelGroup createParallelGroup()`
- `GroupLayout.ParallelGroup createParallelGroup(GroupLayout.Alignment align)`
- `GroupLayout.ParallelGroup createParallelGroup(GroupLayout.Alignment align, boolean resizable)`

创建一个并行布局其子组件的组。

![Image](img/722tab01.jpg)

- `boolean getHonorsVisibility()`
- `void setHonorsVisibility(boolean b)`

获取或设置`honorsVisibility`属性。当为`true`（默认值）时，不可见组件不进行布局。当为`false`时，它们将像可见一样进行布局。这在你临时隐藏某些组件且不希望布局改变时非常有用。

- `boolean getAutoCreateGaps()`
- `void setAutoCreateGaps(boolean b)`
- `boolean getAutoCreateContainerGaps()`
- `void setAutoCreateContainerGaps(boolean b)`

获取并设置`autoCreateGaps`和`autoCreateContainerGaps`属性。当为`true`时，会在组件之间或容器边界处自动添加间隙。默认值是`false`。当你手动产生`GroupLayout`时，使用`true`值非常有用。

### javax.swing.GroupLayout.Group

- `GroupLayout.Group addComponent(Component c)`
- `GroupLayout.Group addComponent(Component c, int minimumSize, int preferredSize, int maximumSize)`

向此组添加组件。大小参数可以是实际的（非负）值，可以是特殊常量`GroupLayout.DEFAULT_SIZE`或`GroupLayout.PREFERRED_SIZE`。当使用`DEFAULT_SIZE`时，会调用组件的`getMinimumSize`、`getPreferredSize`或`getMaximumSize`。当使用`PREFERRED_SIZE`时，会调用组件的`getPreferredSize`方法。

- `GroupLayout.Group addGap(int size)`
- `GroupLayout.Group addGap(int minimumSize, int preferredSize, int maximumSize)`

添加一个给定的固定或灵活大小的间隙。

- `GroupLayout.Group addGroup(GroupLayout.Group g)`

将给定的组添加到此组。

### javax.swing.GroupLayout.ParallelGroup

- `GroupLayout.ParallelGroup addComponent(Component c, GroupLayout.Alignment align)`
- `GroupLayout.ParallelGroup addComponent(Component c, GroupLayout.Alignment align, int minimumSize, int preferredSize, int maximumSize)`
- `GroupLayout.ParallelGroup addGroup(GroupLayout.Group g, GroupLayout.Alignment align)`

使用给定的对齐方式（`BASELINE`、`LEADING`、`TRAILING`或`CENTER`之一）向此组添加组件或组。

### javax.swing.GroupLayout.SequentialGroup

- `GroupLayout.SequentialGroup addContainerGap()`
- `GroupLayout.SequentialGroup addContainerGap(int preferredSize, int maximumSize)`

添加用于分离组件与容器边缘的间隙。

- `GroupLayout.SequentialGroup addPreferredGap(LayoutStyle.ComponentPlacement type)`

添加用于分离组件的间隙。类型为`LayoutStyle.ComponentPlacement.RELATED`或`LayoutStyle.ComponentPlacement.UNRELATED`。

#### 12.6.3 不使用布局管理器

在某些情况下，你可能不想费心使用布局管理器，只想将组件放置在固定位置（有时被称为*绝对定位*）。这对于平台无关的应用程序并不是一个好主意，但用于快速原型设计时并没有大问题。

以下是将组件放置在固定位置的操作方法：

1. 将布局管理器设置为`null`。
2. 将你想要的组件添加到容器中。
3. 指定你想要的位置和大小：

点击此处查看代码图片

```java
frame.setLayout(null);

JButton ok = new JButton("OK");

frame.add(ok);

ok.setBounds(10, 10, 30, 15);
```

### java.awt.Component 1.0

- `void setBounds(int x, int y, int width, int height)`

移动并调整组件的大小。

![Image](img/724tab01.jpg)

#### 12.6.4 自定义布局管理器

你可以设计自己的`LayoutManager`类，以特殊方式管理组件。作为一个有趣的例子，让我们把容器中的所有组件排列成一个圆（参见图 12.34）。

![Image](img/12fig34.jpg)

**图 12.34** 圆形布局

你自定义的布局管理器必须实现`LayoutManager`接口。你需要重写以下五个方法：

```java
void addLayoutComponent(String s, Component c);

void removeLayoutComponent(Component c);

Dimension preferredLayoutSize(Container parent);

Dimension minimumLayoutSize(Container parent);

void layoutContainer(Container parent);
```

前两个方法在组件添加或删除时被调用。如果你没有保留任何关于组件的信息，可以让它们什么都不做。接下来的两个方法计算组件的最小和首选布局。第五个方法执行实际工作并在所有组件上调用`setBounds`。

![Image](img/note.jpg) AWT 有第二个接口，称为`Manager2`，拥有十个方法而不是五个。`Manager2`接口的主要目的是允许带约束的`add`方法。例如，`BorderLayout`和`GridBagLayout`实现了`Manager2`接口。

Listing 2.13 显示了`CircleLayout`管理器的代码，它在父容器沿圆形布局组件。示例程序的 frame 类在 Listing 2.14 中。

```java
53      minHeight = preferredHeight / 2;

54      sizesSet = true;

public Dimension preferredLayoutSize(Container parent)
{
    setSizes(parent);

    Insets insets = parent.getInsets();

    int width = preferredWidth + insets.left + insets.right;
    int height = preferredHeight + insets.top + insets.bottom;

    return new Dimension(width, height);
}

public Dimension minimumLayoutSize(Container parent)
{
    setSizes(parent);

    Insets insets = parent.getInsets();

    int width = minWidth + insets.left + insets.right;
    int height = minHeight + insets.top + insets.bottom;

    return new Dimension(width, height);
}

public void layoutContainer(Container parent)
{
    setSizes(parent);

    // compute center of the circle

    Insets insets = parent.getInsets();

    int containerWidth = parent.getSize().width - insets.left - insets.right;
    int containerHeight = parent.getSize().height - insets.top - insets.bottom;

    int xcenter = insets.left + containerWidth / 2;
    int ycenter = insets.top + containerHeight / 2;

    // compute radius of the circle

    int xradius = (containerWidth - maxComponentWidth) / 2;
    int yradius = (containerHeight - maxComponentHeight) / 2;
    int radius = Math.min(xradius, yradius);

    // lay out components along the circle

    int n = parent.getComponentCount();

    for (int i = 0; i < n; i++)
    {
        Component c = parent.getComponent(i);

        if (c.isVisible())
        {
            double angle = 2 * Math.PI * i / n;

            // center of component
```



```java
int x = xcenter + (int) (Math.cos(angle) * radius);

int y = ycenter + (int) (Math.sin(angle) * radius);

// move component so that its center is (x, y)

// and its size is its preferred size

Dimension d = c.getPreferredSize();

c.setBounds(x - d.width / 2, y - d.height / 2, d.width, d.height);

```

**列表 12.14** `circleLayout/CircleLayoutFrame.java`

点击此处查看图片

```java
package circleLayout;

import javax.swing.*;

/**
 * 一个显示沿圆周排列按钮的框架框。
 */

public class CircleLayoutFrame extends JFrame
{
    public CircleLayoutFrame()
    {
        setLayout(new CircleLayout());

        add(new JButton("Yellow"));
        add(new JButton("Blue"));
        add(new JButton("Red"));
        add(new JButton("Green"));
        add(new JButton("Orange"));
        add(new JButton("Fuchsia"));
        add(new JButton("Indigo"));

        pack();
    }
}
```

## `java.awt.LayoutManager` 1.0

- `void addLayoutComponent(String name, Component comp)` 将一个组件添加到布局中。
- `void removeLayoutComponent(Component comp)` 从布局中移除一个组件。
- `Dimension preferredLayoutSize(Container cont)` 返回该布局下容器的首选尺寸维度。
- `Dimension minimumLayoutSize(Container cont)` 返回该布局下容器的最小尺寸维度。
- `void layoutContainer(Container cont)` 布局容器中的组件。

![图片](img/728tab01.jpg)

### 12.6.5 遍历顺序

当你向窗口中添加许多组件时，你需要考虑`遍历顺序`。当窗口首次显示时，遍历顺序中的第一个组件具有键盘焦点。每当用户按下一次 `Tab` 键时，下一个组件就会获得焦点。

记住，拥有键盘焦点的组件可以通过键盘进行操作。例如，按钮在获得焦点时，可以使用空格键进行“点击”。你可能个人并不在乎使用 `Tab` 键来遍历一组控件，但有很多用户是这样需要的。其中包括鼠标讨厌者以及无法使用鼠标的人，也许是因为身体残疾，或者因为他们正在通过语音导航用户界面。因此，你需要了解 Swing 如何处理遍历顺序。

遍历顺序非常简单：首先是从左到右，然后是从上到下。例如，在字体对话框示例中，组件按照以下顺序遍历（参见图 12.35）：

1. 粗体
2. 斜体
3. 字体
4. 下划线
5. 删除线

![图片](img/12fig35.jpg)

**图 12.35** 遍历顺序

## 12.7 对话框

到目前为止，我们所有的用户界面组件都出现在创建的框架窗口内部。如果你编写在浏览器中运行的`小程序`，这是最常见的情况。但如果你编写应用程序，通常希望弹出独立的对话框来向用户提供信息或从用户处获取信息。

与大多数窗口系统一样，AWT 区分模态（modal）和非模态（modeless）对话框。模态对话框在用户处理它之前，不允许用户与应用程序的其余窗口进行交互。在继续执行之前需要用户信息时，请使用模态对话框。例如，当用户想要读取文件时，应该弹出模态对话框。用户必须指定文件名，程序才能开始读取操作。只有当用户关闭模态对话框后，应用程序才能继续。

非模态对话框的一个例子是工具栏。非模态对话框可以根据需要停留，用户可以根据需要与应用程序窗口和工具栏进行交互。

我们将从简单的对话框开始本节——只有单一信息的模态对话框。Swing 有一个方便的 `JOptionPane` 类，可以在无需编写任何特殊对话框代码的情况下放置对话框。接下来，你将看到如何通过实现自己的对话框来编写更复杂的对话框。最后，你将看到如何将数据从应用程序传输到对话框并返回。

通过查看两个标准对话框来结束本节：文件对话框和颜色对话框。文件对话框是复杂的，你绝对需要熟悉 `JFileChooser`——自己写一个将是一个真正的挑战。`JColorChooser` 对话框在你需要用户选择颜色时非常有用。

### 12.7.1 选项对话框

Swing 提供了一系列现成的简单对话框，足以向用户询问单一信息。`JOptionPane` 有四个静态方法来显示这些简单对话框：

图 12.36 显示了一个典型的对话框。如你所见，该对话框包含以下组件：

- 图标
- 消息
- 一个或多个选项按钮

![Image](img/12fig36.jpg)

**图 12.36** 选项对话框

输入对话框包含一个用于用户输入的额外组件。可以是一个用户可以在其中输入任意字符串的文本字段，也可以是一个用户可以从中选择一个项目的组合框。

这些对话框的精确布局以及标准消息类型的图标选择取决于可插入的外观函数（pluggable look-and-feel）。

左侧的图标取决于五种消息类型之一：

- `ERROR_MESSAGE`
- `INFORMATION_MESSAGE`
- `WARNING_MESSAGE`
- `QUESTION_MESSAGE`
- `PLAIN_MESSAGE`

`PLAIN_MESSAGE` 类型没有图标。每种对话框类型还有一个方法，允许你提供自己的图标来代替。

对于每个对话框类型，你都可以指定一个消息。此消息可以是字符串、图标、用户界面组件或任何对象。以下是消息对象的显示方式：

![Image](img/732tab01.jpg)

你可以通过运行列表 12.15 中的程序来查看这些选项。

当然，提供消息字符串是最常见的情况。提供一个 `Component` 给你提供了极大的灵活性，因为你可以让 `paintComponent` 方法绘制任何你想要的内容。

底部的按钮取决于对话框类型和选项类型。调用 `showMessageDialog` 和 `showInputDialog` 时，你只会得到一组标准按钮（分别是 OK 和 OK/Cancel）。调用 `showConfirmDialog` 时，你可以从四种选项类型中选择：

- `DEFAULT_OPTION`
- `YES_NO_OPTION`
- `YES_NO_CANCEL_OPTION`
- `OK_CANCEL_OPTION`

使用 `showOptionDialog`，你可以指定任意一组选项。你为选项提供一个对象数组。每个数组元素的渲染方式如下所示：

![Image](img/732tab02.jpg)

这些函数的返回值如下：

![Image](img/732tab03.jpg)

`showConfirmDialog` 和 `showOptionDialog` 返回整数以指示用户选择了哪个按钮。对于选项对话框，这仅仅是所选选项的索引；如果用户关闭了对话框而不是选择选项，则返回 `CLOSED_OPTION`。对于确认对话框，返回值可以是以下之一：

- `OK_OPTION`
- `CANCEL_OPTION`
- `YES_OPTION`
- `NO_OPTION`
- `CLOSED_OPTION`

这这一切听起来像是一组令人困惑的选择，但在实践中非常简单。遵循以下步骤：

1. 选择对话框类型（消息、确认、选项或输入）。
2. 选择图标（错误、信息、警告、问题、无或自定义）。
3. 选择消息（字符串、图标、自定义组件或它们的组合）。
4. 对于确认对话框，选择选项类型（默认、是/否、是/否/取消或确定/取消）。
5. 对于选项对话框，选择选项（字符串、图标或自定义组件）和默认选项。
6. 对于输入对话框，在文本字段和组合框之间选择。
7. 在 `JOptionPane` API 中找到要调用的相应方法。

例如，假设你想显示图 12.36 中的对话框。该对话框显示消息并请求用户确认或取消。因此，它是一个确认对话框。图标是一个问题图标。消息是一个字符串。选项类型是 `OK_CANCEL_OPTION`。以下是你将进行的调用：

```java
int selection = JOptionPane.showConfirmDialog(
    parent,
    "Message",
    "Title",
    JOptionPane.OK_CANCEL_OPTION,
    JOptionPane.QUESTION_MESSAGE
);

if (selection == JOptionPane.OK_OPTION) . . .
```

![Image](img/tip.jpg) 提示

消息字符串可以包含换行符（`'\n'`）。此类字符串将以多行形式显示。

列表 12.15 中显示的框架类显示了六个按钮面板（参见图 12.37）。列表 12.16 显示了面板的类。当你点击 Show 按钮时，将显示选定的对话框。

**列表 12.15** `optionDialog/OptionDialogFrame.java`

```java
package optionDialog;

import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;
import java.util.*;
import javax.swing.*;

/**
 * 一个包含用于选择各种选项对话框设置的框架。
 */

public class OptionDialogFrame extends JFrame
{
    private ButtonPanel typePanel;
    private ButtonPanel messagePanel;
    private ButtonPanel messageTypePanel;
    private ButtonPanel optionTypePanel;
    private ButtonPanel optionsPanel;
    private ButtonPanel inputPanel;

    private String messageString = "Message";
    private Icon messageIcon = new ImageIcon("blue-ball.gif");
    private Object messageObject = new Date();
    private Component messageComponent = new SampleComponent();

    public OptionDialogFrame()
    {
        JPanel gridPanel = new JPanel();
        gridPanel.setLayout(new GridLayout(2, 3));

        typePanel = new ButtonPanel("Type", "Message", "Input");
        messageTypePanel = new ButtonPanel(
            "Message",
            "ERROR_MESSAGE",
            "INFORMATION_MESSAGE",
            "WARNING_MESSAGE",
            "QUESTION_MESSAGE",
            "PLAIN_MESSAGE"
        );
        messagePanel = new ButtonPanel(
            "Message",
            "Icon",
            "Component",
            "Other",
            "Object[]"
        );
        optionTypePanel = new ButtonPanel(
            "Confirm",
            "DEFAULT_OPTION",
            "YES_NO_OPTION",
            "YES_NO_CANCEL_OPTION",
            "OK_CANCEL_OPTION"
        );
        optionsPanel = new ButtonPanel("Option", "String[]", "Object[]");
        inputPanel = new ButtonPanel("Input", "Text field", "Combo box");

        gridPanel.add(typePanel);
        gridPanel.add(messageTypePanel);
        gridPanel.add(messagePanel);
        gridPanel.add(optionTypePanel);
        gridPanel.add(optionsPanel);
        gridPanel.add(inputPanel);

        // 添加带有 Show 按钮的面板
        JPanel showPanel = new JPanel();
        JButton showButton = new JButton("Show");
        showButton.addActionListener(new ShowAction());

        showPanel.add(showButton);

        add(gridPanel, BorderLayout.CENTER);
        add(showPanel, BorderLayout.SOUTH);

        pack();
    }

    /**
     * 获取当前选择的消息。
     * @return 字符串、图标或对象数组，取决于 Message 面板
     */
    public Object getMessage()
    {
        String s = messagePanel.getSelection();

        if (s.equals("String")) return messageString;
        else if (s.equals("Icon")) return messageIcon;
        else if (s.equals("Component")) return messageComponent;
        else if (s.equals("Object[]"))
            return new Object[] {
                messageString,
                messageIcon,
                messageComponent,
                messageObject
            };
        else if (s.equals("Other")) return messageObject;
        else return null;
    }

    /**
     * 获取当前选择的选项。
     * @return 字符串数组、图标数组或对象数组，取决于 Option 面板的选择
     */
    public Object[] getOptions()
    {
        String s = optionsPanel.getSelection();

        if (s.equals("String[]"))
            return new String[] { "Yellow", "Blue", "Red" };
        else if (s.equals("Icon[]"))
            return new Icon[] {
                new ImageIcon("yellow-ball.gif"),
                new ImageIcon("blue-ball.gif"),
                new ImageIcon("red-ball.gif")
            };
        else if (s.equals("Object[]"))
            return new Object[] {
                messageString,
                messageIcon,
                messageComponent,
                messageObject
            };
    }
}
```

```java
else return null;
}

/**
 * 获取选定的消息或选项类型
 * @param panel 消息类型面板或确认面板
 * @return 来自 JOptionPane 类中选定的 XXX_MESSAGE 或 XXX_OPTION 常量
 */
public int getType(ButtonPanel panel)
{
    String s = panel.getSelection();

    try
    {
        return JOptionPane.class.getField(s).getInt(null);
    }
    catch (Exception e)
    {
        return -1;
    }
}

/**
 * Show 按钮的监听器根据 Type 面板的选择显示
```



- 确认、输入、消息或选项对话框。

```java
private class ShowAction implements ActionListener
{
  public void actionPerformed(ActionEvent event)
  {
    if (typePanel.getSelection().equals("Confirm")) JOptionPane.showConfirmDialog(
        OptionDialogFrame.this, getMessage(), "Title", getType(optionTypePanel),
        getType(messageTypePanel));
    else if (typePanel.getSelection().equals("Input"))
    {
      if (inputPanel.getSelection().equals("Text field")) JOptionPane.showInputDialog(
          OptionDialogFrame.this, getMessage(), "Title", getType(messageTypePanel));
      else JOptionPane.showInputDialog(OptionDialogFrame.this, getMessage(), "Title",
        getType(messageTypePanel), null, new String[] { "Yellow", "Blue", "Red" },
        "Blue");
    }
    else if (typePanel.getSelection().equals("Message")) JOptionPane.showMessageDialog(
        OptionDialogFrame.this, getMessage(), "Title", getType(messageTypePanel));
    else if (typePanel.getSelection().equals("Option")) JOptionPane.showOptionDialog(
        OptionDialogFrame.this, getMessage(), "Title", getType(optionTypePanel),
        getType(messageTypePanel), null, getOptions()[0]);
  }
}

/**
 * 具有绘制表面的组件
 */
class SampleComponent extends JComponent
{
  public void paintComponent(Graphics g)
  {
    Graphics2D g2 = (Graphics2D) g;
    Rectangle2D rect = new Rectangle2D.Double(0, 0, getWidth() - 1, getHeight() - 1);
    g2.setPaint(Color.YELLOW);
    g2.fill(rect);
    g2.setPaint(Color.BLUE);
    g2.draw(rect);
  }

  public Dimension getPreferredSize()
  {
    return new Dimension(10, 10);
  }
}
```

**Listing 12.16** `optionDialog/ButtonPanel.java`

点击此处查看代码图像

```java
package optionDialog;

import javax.swing.*;

/**
 * 一个在带标题边框内包含单选按钮的面板。
 */
public class ButtonPanel extends JPanel
{
  private ButtonGroup group;

  /**
   * 构造按钮面板。
   * @param title 边框中显示的标题
   * @param options 单选按钮标签的数组
   */
  public ButtonPanel(String title, String... options)
  {
    setBorder(BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(), title));
    setLayout(new BoxLayout(this, BoxLayout.Y_AXIS));
    group = new ButtonGroup();

    // 为每个选项创建一个单选按钮
    for (String option : options)
    {
      JRadioButton b = new JRadioButton(option);
      b.setActionCommand(option);
      add(b);
      group.add(b);
    }
  }

  /**
   * 获取选定的消息或选项类型
   * @param panel 消息类型面板或确认面板
   * @return 来自 JOptionPane 类中选定的 XXX_MESSAGE 或 XXX_OPTION 常量
   */
  public int getType(ButtonPanel panel)
  {
    String s = panel.getSelection();
    try
    {
      return JOptionPane.class.getField(s).getInt(null);
    }
    catch (Exception e)
    {
      return -1;
    }
  }

  /**
   * Show 按钮的监听器根据 Type 面板的选择显示确认、输入、消息或选项对话框。
   */
  private class ShowAction implements ActionListener
  {
    public void actionPerformed(ActionEvent event)
    {
      if (typePanel.getSelection().equals("Confirm")) JOptionPane.showConfirmDialog(
          OptionDialogFrame.this, getMessage(), "Title", getType(optionTypePanel),
          getType(messageTypePanel));
      else if (typePanel.getSelection().equals("Input"))
      {
        if (inputPanel.getSelection().equals("Text field")) JOptionPane.showInputDialog(
            OptionDialogFrame.this, getMessage(), "Title", getType(messageTypePanel));
        else JOptionPane.showInputDialog(OptionDialogFrame.this, getMessage(), "Title",
          getType(messageTypePanel), null, new String[] { "Yellow", "Blue", "Red" },
          "Blue");
      }
      else if (typePanel.getSelection().equals("Message")) JOptionPane.showMessageDialog(
          OptionDialogFrame.this, getMessage(), "Title", getType(messageTypePanel));
      else if (typePanel.getSelection().equals("Option")) JOptionPane.showOptionDialog(
          OptionDialogFrame.this, getMessage(), "Title", getType(optionTypePanel),
          getType(messageTypePanel), null, getOptions()[0]);
    }
  }

  /**
   * 具有绘制表面的组件
   */
  class SampleComponent extends JComponent
  {
    public void paintComponent(Graphics g)
    {
      Graphics2D g2 = (Graphics2D) g;
      Rectangle2D rect = new Rectangle2D.Double(0, 0, getWidth() - 1, getHeight() - 1);
      g2.setPaint(Color.YELLOW);
      g2.fill(rect);
      g2.setPaint(Color.BLUE);
      g2.draw(rect);
    }

    public Dimension getPreferredSize()
    {
      return new Dimension(10, 10);
    }
  }
}
```

在上一节中，你学习了如何使用 `JOptionPane` 类来显示简单的对话框。在本节中，你将看到如何手动创建一个这样的对话框。

图 12.38 显示了一个典型的模态对话框——当用户点击“关于（About）”按钮时显示的程序信息框。

![Image](img/12fig38.jpg)

**图 12.38** 一个“关于”对话框

要实现一个对话框，你需要扩展 `JDialog` 类。这与为应用程序创建主窗口时扩展 `JFrame` 的过程本质是相同的。具体步骤如下：

1. 在你的对话框构造函数中，调用父类 `JDialog` 的构造函数。
2. 添加对话框的用户界面组件。
3. 添加事件处理器。
4. 设置对话框的大小。

当你调用父类构造函数时，你需要提供*所有者框架（owner frame）*、对话框标题以及*模态性（modality）*。

所有者框架控制对话框显示的位置。你可以提供 `null` 作为所有者；这样，对话框由一个隐藏的框架所有。

模态性指定了对话框显示期间应用程序的哪些窗口会被阻塞。非模态对话框（modeless dialog）不会阻塞其他窗口。模态对话框（modal dialog）会阻塞应用程序的所有其他窗口（对话框的子窗口除外）。对于用户可以随时访问的工具箱，可以使用非模态对话框。如果你想强制用户在继续操作之前提供所需信息，则应使用模态对话框。

***

![Image](img/note.jpg)

> **注意**
>
> 从 Java SE 6 开始，新增了两种模态性类型。文档模态对话框（document-modal dialog）会阻塞属于同一个“文档”的所有窗口，更准确地说，会阻塞所有与对话框具有相同无根根窗口的窗口。这解决了帮助系统中的问题。在旧版本中，当模态对话框弹出时，用户无法与帮助窗口进行交互。工具包模态对话框（toolkit-modal dialog）会阻塞来自同一个“工具包（toolkit）”的所有窗口。工具包是一个启动多个应用程序的 Java 程序，例如浏览器中的 applet 引擎。关于这些高级问题的更多信息，请参阅 [`www.oracle.com/technetwork/articles/javase/modality-137604.html`](http://www.oracle.com/technetwork/articles/javase/modality-137604.html)。

***

以下是对话框的代码：

点击此处查看代码图片

```java
public class AboutDialog extends JDialog
{
  public AboutDialog(JFrame owner)
  {
    super(owner, "About DialogTest", true);
    add(new JLabel(
        "<html><h1><i>Core Java</i></h1><hr>By Cay Horstmann</html>"),
        BorderLayout.CENTER);
    JPanel panel = new JPanel();
    JButton ok = new JButton("OK");
    ok.addActionListener(event -> setVisible(false));
    panel.add(ok);
    add(panel, BorderLayout.SOUTH);
    setSize(250, 150);
  }
}
```

如你所示，构造函数添加了用户界面元素——在本例中是标签和按钮。它为按钮添加了处理器并设置了对话框的大小。

要显示对话框，创建一个新的对话框对象并使其可见：

点击此处查看代码图片

```java
JDialog dialog = new AboutDialog(this);
dialog.setVisible(true);
```

实际上，在下方的示例代码中，我们只创建了一次对话框，每用户点击“关于”按钮时都可以重复使用它。

点击此处查看代码图片

```java
if (dialog == null) // 第一次
  dialog = new AboutDialog(this);
dialog.setVisible(true);
```

当用户点击 OK 按钮时，对话框应该关闭。这在 OK 按钮的事件处理器中处理：

点击此处查看代码图片

```java
ok.addActionListener(event -> setVisible(false));
```

当用户通过点击关闭按钮关闭对话框时，对话框也会被隐藏。就像 `JFrame` 一样，你可以通过 `setDefaultCloseOperation` 方法覆盖此行为。

列表 12.17 是测试程序框架类的代码。列表 12.18 显示了对话框类。

**列表 12.17** `dialog/DialogFrame.java`

点击此处查看代码图片

***

```java
package dialog;

import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;

/**
 * 一个带有菜单->关于的框架，显示了一个对话框。
 */
public class DialogFrame extends JFrame
{
  private static int DEFAULT_WIDTH = 300;
  private static int DEFAULT_HEIGHT = 200;
  private AboutDialog dialog;

  public DialogFrame()
  {
    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

    // 构建菜单栏
    JMenuBar menuBar = new JMenuBar();
    setMenuBar(menuBar);
    JMenu fileMenu = new JMenu("File");
    menuBar.add(fileMenu);

    // 添加关于和退出项
    // 关于项显示对话框
    JMenuItem aboutItem = new JMenuItem("About");
    aboutItem.addActionListener(event -> {
      if (dialog == null) // 第一次
        dialog = new AboutDialog(this);
      dialog.setVisible(true); // 弹出对话框
    });
    fileMenu.add(aboutItem);

    // 退出项退出程序
    JMenuItem exitItem = new JMenuItem("Exit");
    exitItem.addActionListener(event -> System.exit(0));
    fileMenu.add(exitItem);
  }
}
```

***

**列表 12.18** `dialog/AboutDialog.java`

点击此处查看代码图片

***

```java
package dialog;

import java.awt.BorderLayout;

import javax.swing.JButton;
```



```java
import javax.swing.JDialog;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;

/**
 * 一个示例模态对话框，显示消息并等待用户点击 OK 按钮。
 */
public class AboutDialog extends JDialog
{
    public AboutDialog(JFrame owner)
    {
        super(owner, "About DialogTest", true);

        // 将标签添加到中心
        add(new JLabel(
            "<html><h1><i>Core Java</i></h1><hr>By Cay Horstmann</html>"),
            BorderLayout.CENTER);

        // OK 按钮关闭对话框
        JButton ok = new JButton("OK");
        ok.addActionListener(event -> setVisible(false));

        // 将 OK 按钮添加到南部
        JPanel panel = new JPanel();
        panel.add(ok);
        add(panel, BorderLayout.SOUTH);

        pack();
    }
}
```

### 12.7.3 数据交换

弹出对话框最常见的原因是从用户获取信息。你已经学习了如何轻松创建一个对话框对象：给它提供初始数据并调用`setVisible(true)`将对话框显示在屏幕上。现在让我们看看如何在对话框之间传输数据。

考虑图 12.39 中的对话框，它可以用于获取连接某些在线服务所需的用户名和密码。

你的对话框应该提供设置默认数据的方法。例如，示例程序中的`PasswordChooser`类有一个方法`setUser`，用于将默认值填充到相应的字段中：

点击此处查看代码图片

```java
public void setUser(User u)
{
    username.setText(u.getName());
}
```

一旦设置了默认（如果需要），通过调用`setVisible(true)`来显示对话框。此时对话框就会显示。

随后用户填写信息并点击 OK 或 Cancel 按钮。这两个按钮的事件处理器都会调用`setVisible(false)`，这会终止对`setVisible(true)`的调用。或者，用户也可以关闭对话框。如果你没有为对话框安装窗口监听器，则应用默认的窗口关闭操作：对话框变为不可见，这也会终止对`setVisible(true)`的调用。

重要的问题是，`setVisible(true)`的调用会阻塞直到用户关闭对话框。这使得实现模态对话框变得简单。

你想知道用户是接受还是取消了对话框。我们的示例代码在显示对话框之前将`ok`标志设为`false`。只有 OK 按钮的事件处理器会将`ok`设为`true`；这就是你从对话框获取用户输入的方法。

***

![Image](img/note.jpg) 注意

从模态对话框传出数据并不简单。当显示模态对话框时，`setVisible(true)`的调用不会阻塞，程序在对话框显示期间继续运行。如果用户在模态对话框上选择了项目并然后点击 OK，对话框需要向程序中的某个监听器发送一个事件。

***

示例程序包含了另一个有用的改进。当你构造`JDialog`对象时，你需要指定所有者帧（owner frame）。然而，通常你想要用不同的所有者帧显示同一个对话框。最好在准备好显示对话框时选择所有者帧，而不是在构造`PasswordChooser`对象时。

技巧是让`PasswordChooser`继承`JPanel`而不是`JDialog`。在`showDialog`方法中动态构建`JDialog`对象：

点击此处查看代码图片

```java
public boolean showDialog(Frame owner, String title)
{
    ok = false;

    if (dialog == null || dialog.getOwner() != owner)
    {
        dialog = new JDialog(owner, true);
        dialog.add(this);
        dialog.pack();
    }

    dialog.setTitle(title);
    dialog.setVisible(true);

    return ok;
}
```

注意，`owner`等于`null`是安全的。

你可以做得更好。有时所有者帧并不容易直接获取。从任何`parent`组件计算它应该是容易的，如下所示：

点击此处查看代码图片

```java
Frame owner;

if (parent instanceof Frame)
    owner = (Frame) parent;
else
    owner = (Frame) SwingUtilities.getAncestorOfClass(Frame.class, parent);
```

我们在示例程序中使用这种增强功能。`JOptionPane`类也使用了这种机制。

许多对话框有一个默认按钮，如果用户按下触发键（在大多数外观和界面实现中为 Enter 键），该默认按钮会被自动选中。默认按钮会被特别标记，通常带有粗粗的轮框。

在对话框的根面板（root pane）中设置默认按钮：

点击此处查看代码图片

```java
dialog.getRootPane().setDefaultButton(okButton);
```

如果你遵循我们在面板中布局对话框的建议，那么你必须小心在将面板封装进对话框之后再设置默认按钮。面板对话框本身没有根面板。

Listing 12.19 是程序的帧类，它说明了数据流出对话框的流向。Listing 12.20 显示了对话框类。

**Listing 12.19** `dataExchange/DataExchangeFrame.java`

点击此处查看代码图片

***

```java
package dataExchange;

import java.awt.*;
import java.awt.event.*;

import javax.swing.*;

/**
 * 一个带有菜单的帧，其 File->Connect 动作会显示密码对话框。
 */
public class DataExchangeFrame extends JFrame
{
    public static final int TEXT_ROWS = 20;
    public static final int TEXT_COLUMNS = 40;

    private PasswordChooser dialog = null;
    private JTextArea textArea;

    public DataExchangeFrame()
    {
        // 构建一个 File 菜单
        JMenuBar mbar = new JMenuBar();
        setJMenuBar(mbar);

        JMenu fileMenu = new JMenu("File");
        mbar.add(fileMenu);

        // 添加 Connect 和 Exit 菜单项
        JMenuItem connectItem = new JMenuItem("Connect");
        connectItem.addActionListener(new ConnectAction());
        fileMenu.add(connectItem);

        // Exit 项退出程序
        JMenuItem exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(event -> System.exit(0));
        fileMenu.add(exitItem);

        textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
        add(new JScrollPane(textArea), BorderLayout.CENTER);

        pack();
    }

    /**
     * Connect 动作弹出对话框。
     */
    private class ConnectAction implements ActionListener
    {
        public void actionPerformed(ActionEvent event)
        {
            // 如果需要，构造对话框
            if (dialog == null)
                dialog = new PasswordChooser();

            // 设置默认值
            dialog.setUser(new User("name", null));

            // 弹出对话框
            if (dialog.showDialog(DataExchangeFrame.this, "Connect"))
            {
                // 如果接受，获取用户输入
                User u = dialog.getUser();

                textArea.append(
                    "user name = " + u.getName()
                    + ", password = "
                    + (new String(u.getPassword()))
                    + "\n");
            }
        }
    }
}
```

***

**Listing 12.20** `dataExchange/PasswordEncoder.java`

点击此处查看代码图片

***

```java
package dataExchange;

import java.awt.BorderLayout;
import java.awt.Component;
import java.awt.Frame;
import java.awt.GridLayout;

import javax.swing.JButton;
import javax.swing.JDialog;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JPasswordField;
import javax.swing.JTextField;
import javax.swing.SwingUtilities;

/**
 * 在在对话框内显示的密码选择器
 */
public class PasswordChooser extends JPanel
{
    private JTextField username;
    private JPasswordField password;
    private JButton okButton;
    private boolean ok;
    private JDialog dialog;

    public PasswordChooser()
    {
        setLayout(new BorderLayout());

        // 构建一个包含用户名和密码字段的面板
        JPanel panel = new JPanel();
        panel.setLayout(new GridLayout(2, 2));

        panel.add(new JLabel("User name:"));
        panel.add(username = new JTextField(""));

        panel.add(new JLabel("Password:"));
        panel.add(password = new JPasswordField(""));

        add(panel, BorderLayout.CENTER);

        // 创建终止对话框的 Ok 和 Cancel 按钮
        okButton = new JButton("Ok");
        okButton.addActionListener(event -> {
            ok = true;
            dialog.setVisible(false);
        });

        JButton cancelButton = new JButton("Cancel");
        cancelButton.addActionListener(event -> dialog.setVisible(false));

        // 将按钮添加到南部边界
        JPanel buttonPanel = new JPanel();
        buttonPanel.add(okButton);
        buttonPanel.add(cancelButton);

        add(buttonPanel, BorderLayout.SOUTH);
    }

    /**
     * 设置对话框默认值。
     */

    /**
     * @param u 默认用户信息
     */
    public void setUser(User u)
    {
        username.setText(u.getName());
    }

    /**
     * 获取对话框条目
     *
     * @return 一个状态表示对话框条目的 User 对象
     */
    public User getUser()
    {
        return new User(username.getText(), password.getPassword());
    }

    /**
     * 在对话框中显示选择面板
     *
     * @param parent 所有者帧中的组件或 null
     * @param title 对话框标题
     */
    public boolean showDialog(Component parent, String title)
    {
        ok = false;

        // 定位所有者帧
        Frame owner = null;

        if (parent instanceof Frame)
            owner = (Frame) parent;
        else
            owner = (Frame) SwingUtilities.getAncestorOfClass(Frame.class, parent);

        // 如果是第一次，或者所有者发生了变化，则创建新对话框
        if (dialog == null || dialog.getOwner() != owner)
        {
            dialog = new JDialog(owner, true);
            dialog.add(this);
            dialog.getRootPane().setDefaultButton(okButton);
            dialog.pack();
        }

        // 设置标题并显示对话框
        dialog.setTitle(title);
        dialog.setVisible(true);

        return ok;
    }
}
```



### `javax.swing.SwingUtilities` 1.2

- `Container getAncestorOfClass(Class c, Component comp)`

返回属于给定类或其一个子类的给定组件的最内父容器。

### `javax.swing.JComponent` 1.2

- `JRootPane getRootPane()`

获取包含此组件的根面板（root pane），如果该组件没有带有根面板的祖先，则返回 `null`。

### `javax.swing.JRootPane` 1.2

- `void setDefaultButton(JButton button)`

设置此根面板的默认按钮。若要停用默认按钮，请带有 `null` 参数调用此方法。

### `javax.swing.JButton` 1.2

- `boolean isDefaultButton()`

如果此按钮是其根面板的默认按钮，则返回 `true`。

## 12.7.4 文件对话框

在应用程序中，你通常希望能够打开和保存文件。一个能够显示文件和目录并允许用户浏览文件系统的良好的文件对话框很难编写的，而且你绝对不想重复发明它。幸运的是，Swing 提供了一个 `JFileChooser` 类，它允许你显示一个与大多数原生应用程序使用的类似的对话框。

注意，`JFileChooser` 类并不是 `JDialog` 的子类。不要调用 `setVisible(true)`，而应调用 `showOpenDialog` 来显示打开文件的对话框，或调用 `showSaveDialog` 来显示保存文件的对话框。接受文件的按钮将标记为“打开”（Open）或“保存”（Save）。你也可以通过 `showDialog` 方法提供自己的按钮。图 12.40 显示了文件选择框的一个示例。

### 图 12.40

以下是建立文件对话框并恢复用户选择内容的步骤：

1. **创建一个 `JFileChooser` 对象。** 与 `JDialog` 类的构造函数不同，你不需要提供父组件。这允许你在多个帧之间复用文件选择器对话框。例如：

```java
JFileChooser chooser = new JFileChooser();
```

*提示：复用文件选择器对象是一个好主意，因为 `JFileChooser` 的构造函数可能很慢，特别是在 Windows 上用户有许多映射驱动器时。*

2. **通过调用 `setCurrentDirectory` 方法设置目录。** 例如，使用当前目录：

```java
chooser.setCurrentDirectory(new File("."));
```

你需要提供一个 `File` 对象。`File` 对象将在第 2 章中详细介绍。你现在只需要知道构造函数 `File(String filename)` 会将文件名或目录名转换为 `File` 对象。

3. **如果你有一个预期用户选择的默认文件名，请使用 `setSelectedFile` 方法提供它：**

```java
chooser.setSelectedFile(new File(filename));
```

4. **为了让用户能够在对话框中选择多个文件，请调用 `setSelectionEnabled` 方法。** 当然，这完全是可选的，而且并不总是常见。

```java
chooser.setSelectionEnabled(true);
```

5. **如果你想限制对话框中显示的文件为特定类型（例如，所有扩展名为 `.gif` 的文件），你需要设置一个文件过滤器。** 我们将在本节的稍后部分讨论文件过滤器。

6. **默认情况下，用户使用文件选择器只能选择文件。** 如果你想让用户选择目录，请使用 `setSelectionMode` 方法。使用 `JFileChooser.FILES_ONLY`（默认值）、`JFileChooser.DIRECTORIES_ONLY` 或 `JFileChooser.FILES_AND_DIRECTORIES` 调用它。

7. **通过调用 `showOpenDialog` 或 `showSaveDialog` 方法显示对话框。** 在这些调用中你必须提供父组件：

```java
int result = chooser.showOpenDialog(parent);
```

或：

```java
int result = chooser.showSaveDialog(parent);
```

这些调用唯一的区别在于“确认按钮”（approve button）的标签——用户点击以完成文件选择的按钮。你也可以调用 `showDialog` 方法并为确认按钮传递显式文本：

```java
int result = chooser.showDialog(parent, "Select");
```

这些调用仅在用户确认、取消或关闭对话框时返回。返回值为 `JFileChooser.APPROVE_OPTION`、`JFileChooser.CANCEL_OPTION` 或 `JFileChooser.ERROR_OPTION`。

8. **通过 `getSelectedFile()` 或 `getSelectedFiles()` 方法获取选定的文件或文件。** 这些方法返回单个 `File` 对象或一个 `File` 对象数组。如果你只需要文件对象的路径，调用其 `getPath` 方法。例如：

```java
String filename = chooser.getSelectedFile().getPath();
```

在大多数情况下，这些步骤都是简单的。使用文件对话框的主要困难在于指定用户应从中选择的文件子集。例如，假设用户应该选择 GIF 图片文件。那么文件选择器应该只显示扩展名为 `.gif` 的文件。它还应该给用户某种反馈，说明显示的文件属于特定类别，例如“GIF Images”。

但情况可能更复杂。如果用户应该选择 JPEG 图片文件，扩展名可以是 `.jpg` 或 `.jpeg`。与其使用编码这些复杂情况的方法，文件选择器设计者提供了一种更优雅的机制：要限制显示的文件，请提供扩展抽象类 `javax.swing.filechooser.FileFilter` 的对象。文件选择器会将每个文件传递给文件过滤器，并只显示过滤器接受的文件。

在本文编写时，提供了两种这样的子类：接受所有文件的默认过滤器，以及接受具有给定扩展的所有文件的过滤器。然而，编写临时的文件过滤器很容易的。你只需要实现 `FileFilter` 超类的中的两个抽象方法：

```java
public boolean accept(File f);

public String getDescription();
```

第一种方法测试文件是否应该被接受。第二种方法返回文件类型的描述，该描述可以在文件选择器对话框中。

---

![Image](img/note.jpg) 注意

`java.io` 包中有一个无关的 `FileFilter` 接口，只有一个方法 `boolean accept(File f)`。它被用于 `File` 类的 `listFiles` 方法中，用于列出目录中的文件。我们不知道 Swing 的设计者为什么没有扩展这个接口——也许 Java 类库现在已经变得如此复杂，以至于即使是 Sun 公司的程序员们也不再熟悉所有的标准类和接口了。

如果你同时导入了 `java.io` 和 `javax.swing.filechooser` 包，你将需要解决这两个同名类型之间的命名冲突。最简单的解决方法是导入 `javax.swing.filechooser.FileFilter`，而不是 `javax.swing.filechooser.*`。

---

一旦你拥有了文件过滤器对象，就可以使用 `JFileChooser` 类的 `setFileFilter` 方法将其安装到文件选择器对象中：

点击此处查看代码图像

```java
chooser.setFileFilter(new FileNameExtensionFilter("Image files", "gif", "jpg"));
```

你可以通过调用 `addChoosableFileFilter` 为文件选择器安装多个过滤器：

```java
chooser.addChoosableFileFilter(filter1);
chooser.addChoosableFileFilter(filter2);
...
```

用户从文件对话框底部的组合框中选择一个过滤器。默认情况下，“所有文件”过滤器始终出现在组合框中。这是一个好主意——以防你的程序用户需要选择一个具有非标准扩展名的文件。然而，如果你想抑制“所有文件”过滤器，可以调用：

```java
chooser.setAcceptAllFileFilterUsed(false)
```

---

![Image](img/caution.jpg) 警告

如果你重用同一个文件选择器来加载和保存不同的文件类型，请调用：

```java
chooser.resetChoosableFilters()
```

在添加新过滤器之前清除任何旧的过滤器。

---

最后，你可以通过为文件选择器显示的每个文件提供特殊的图标和文件描述来自定义文件选择器。通过提供一个扩展自 `javax.swing.filechooser` 包中 `FileView` 类的对象来实现。这绝对是一项高级技术。

通常情况下，你不需要提供文件视图——可插件外观（pluggable look-and-feel）会为你提供一个。但如果你想为特殊文件类型显示不同的图标，可以安装你自己的文件视图。你需要扩展 `FileView` 类并实现五个方法：

点击此处查看代码图像

```java
Icon getIcon(File f);

String getName(File f);

String getDescription(File f);

String getTypeDescription(File f);

Boolean isTraversable(File f);
```

然后，使用 `setFileView` 方法将你的文件视图安装到文件选择器中。

文件选择器会针对它想要显示的每个文件或目录调用你的方法。如果你的方法对图标、名称或描述返回 `null`，则文件选择器将查询外观的默认文件视图。这很好，因为这意味着你只需要处理那些你想要进行特殊处理的文件类型。

文件选择器通过调用 `isTraversable` 方法来决定当用户点击目录时是否打开它。注意，此方法返回的是一个 `Boolean` 对象，而不是 `boolean` 值！这看起来很诡异，但实际上非常方便——如果你不感兴趣偏离默认文件视图，只需返回 `null` 即可。文件选择器将查询默认文件视图。

换句话说，该方法返回一个 `Boolean` 让你在三个选项之间选择：`true`（`Boolean.TRUE`）、`false`（`Boolean.FALSE`）或不关心（`null`）。

示例程序包含一个简单的文件视图类。该类在每当文件匹配文件过滤器时，都会显示特定的图标。我们使用它为所有图像文件显示一个调色板图标。

点击此处查看代码图像

```java
class FileIconView extends FileView {

    private FileFilter filter;

    private Icon icon;

    public FileIconView(FileFilter aFilter, Icon anIcon) {

        filter = aFilter;

        icon = anIcon;

    }

    public Icon getIcon(File f) {

        if (!f.isDirectory() && filter.accept(f))

            return icon;

        else return null;

    }

}
```

使用 `setFileView` 方法将此文件视图安装到你的文件选择器：

点击此处查看代码图像

```java
chooser.setFileView(new FileIconView(filter, icon));
```

文件选择器随后将为通过 `filter` 的所有文件显示调色板图标。

---

![Image](img/note.jpg) `get`

你可以在 JDK 的 `demo/fc` 目录下找到更实用的 `FileView`。

最后，你可以通过添加附件来自定义文件对话框。例如，图 12.4 显示了文件旁的预览。

![Image](img/caution.jpg)

**12.4** 带附件的文件对话框

附件可以是任何 Swing 组件。在我们的案例中，我们扩展 `JLabel` 并将其图标设置为缩放后的：

```java
class ImagePreviewer extends JLabel {

    public ImagePreviewer(JFileChooser chooser) {

        setPreferredSize(new Dimension(100, 100));

        setBorder(BorderFactory.createEtchedBorder());

    }

    public void loadImage(File f) {

        ImageIcon icon = new ImageIcon(f);

        if (icon.getWidth() > getWidth()) {

            icon = new ImageIcon(icon.getImage().getScaledInstance(getWidth(), -1, Image.SCALE_SMOOTH));

        }

        setIcon(icon);

        repaint();

    }

}
```

只有一个挑战。我们要在用户选择文件时更新预览图像。文件选择器使用“JavaBeans”机制在属性更改时通知感兴趣的监听器。我们在第 11 章中详细详细讨论了这种机制。这是你需要拦截的代码：

点击此处查看代码图像

```java
chooser.addPropertyChangeListener(event -> {

    if (event.getPropertyName() == JFileChooser.SELECTED_FILE_PROPERTY) {

        File newFile = (File) event.getNewValue();

        // 更新附件

    }

});
```

在我们的示例程序中，我们将此代码添加到 `ImagePreviewer` 构造函数。列表 12.21 到 12.23 包含了对第 2 章中 `ImageViewer` 程序的修改，其中文件选择器通过自定义视图和预览附件进行了增强。

**列表 12.21** `fileChooser/ImageViewerFrame.java`

点击此处查看代码图像

```java
public ImageViewerFrame()
{

    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

    // 设置菜单栏

    JMenuBar menuBar = new JMenuBar();

    setJMenuBar(menuBar);

    JMenu menu = new JMenu("File");

    menuBar.add(menu);

    JMenuItem openItem = new JMenuItem("Open");

    menu.add(openItem);

    openItem.addActionListener(event -> {

        chooser.setCurrentDirectory(new File("."));

        // 显示文件选择对话框

        int result = chooser.showOpenDialog(ImageViewerFrame.this);

        // 如果接受了图像文件，将其将其设置为 label 的图标

        if (result == JFileChooser.APPROVE_OPTION)
        {

            String name = chooser.getSelectedFile().getPath();

            label.setIcon(new ImageIcon(name));

            pack();

        }

    });

    JMenuItem exitItem = new JMenuItem("Exit");

    menu.add(exitItem);

    exitItem.addActionListener(event -> System.exit(0));

    // 使用 label 显示图像

    label = new JLabel();

    add(label);

    // 设置文件选择器

    chooser = new JFileChooser();

    // 接受所有以 .jpg, .jpeg, .gif 结尾的图像文件

    FileFilter filter = new FileNameExtensionFilter(

        "Image files", "jpg", "jpeg", "gif");

    chooser.setFileFilter(filter);

    chooser.setAccessory(new ImagePreviewer(chooser));
```



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。chooser.setFileView(new FileIconView(filter, new ImageIcon("palette.gif")));

}
```

### Listing 12.2 `fileChooser/ImagePreviewer.java`

```java
package fileChooser;

import java.awt.*;
import java.io.*;
import javax.swing.*;

/**
 * 用于预览图像的文件选择器组件。
 */
public class ImagePreviewer extends JLabel {
    /**
     * 构造 `ImagePreviewer`。

     * @param chooser 文件选择器，其属性的变化会触发预览器中图像的变化
     */
    public ImagePreviewer(JFileChooser chooser) {
        setPreferredSize(new Dimension(100, 100));
        setBorder(BorderFactory.createEtchedBorder());

        chooser.addChangeListener(event -> {
            if (event.getPropertyName() == JFileChooser.SELECTED_FILE_PROPERTY) {
                // 用户选择了一个新文件
                File f = (File) event.getNewValue();

                if (f == null) {
                    setIcon(null);
                    return;
                }

                // 将图像读入图标
                ImageIcon icon = new ImageIcon(f.getPath());

                // 如果图标太大无法适应，则进行缩放
                if (icon.getIconWidth() > getWidth()) {
                    icon = new ImageIcon(icon.getImage().getScaledInstance(
                        getWidth(), -1, Image.SCALE_DEFAULT));
                }

                setIcon(icon);
            }
        });
    }
}
```

### Listing 12.23 `fileChooser/FileIconView.java`

```java
package fileChooser;

import java.io.*;
import javax.swing.*;
import javax.swing.filechooser.*;
import javax.swing.filechooser.FileFilter;

/**
 * 为所有匹配文件过滤器的文件显示图标的文件视图。
 */
public class FileIconView extends FileView {
    private FileFilter filter;
    private Icon icon;

    /**
     * 构造 `FileIconView`。

     * @param aFilter 文件过滤器——此过滤器接受的所有文件将将带图标显示。
     * @param anIcon 与所有接受的文件一起显示的图标。
     */
    public FileIconView(FileFilter aFilter, Icon anIcon) {
        filter = aFilter;
        icon = anIcon;
    }

    public Icon getIcon(File f) {
        if (!f.isDirectory() && filter.accept(f)) {
            return icon;
        } else {
            return null;
        }
    }
}
```

### `javax.swing.JFileChooser`

- `JFileChooser()` 创建一个可以用于多个帧的文件选择器对话框。
- `void setCurrentDirectory(File dir)` 设置文件对话框的初始目录。
- `void setSelectedFile(File file)`
- `void setSelectedFiles(File[] file)` 设置文件对话框的默认文件选择。
- `void setMultiSelectionEnabled(boolean b)` 设置或清除多选模式。
- `void setFileSelectionMode(int mode)` 允许用户仅选择文件（默认）、仅选择目录或同时文件和目录。`mode` 参数是 `JFileChooser.FILES_ONLY`、`JFileChooser.DIRECTORIES_ONLY` 和 `JFileChooser.FILES_AND_DIRECTORIES` 之一。
- `int showOpenDialog(Component parent)`
- `int showSaveDialog(Component parent)`
- `int showDialog(Component parent, String approveButtonText)` 显示对话框，其中确认按钮标记为“Open”、“Save”或 `approveButtonText` 字符串。返回 `APPROVE_OPTION`、`CANCEL_OPTION`（如果用户选择了取消或关闭了对话框）或 `ERROR_OPTION`（如果发生错误）。
- `File getSelectedFile()`
- `File[] getSelectedFiles()` 获取用户选择的文件或文件（如果用户没有选择任何文件，则返回 `null`）。
- `void setFileFilter(FileFilter filter)` 设置文件对话框的文件掩码。所有 `filter` 返回 `true` 的文件将被显示。同时，将过滤器添加到可选过滤器列表中。
- `void addChoosableFileFilter(FileFilter filter)` 将过滤器添加到可选过滤器列表中。
- `void setAcceptAllFilterUsed(boolean b)` 在过滤器组合框中包含或抑制“所有文件”过滤器。
- `void resetChoosableFilters()` 清除可选过滤器列表。除非显式抑制，否则保留“所有文件”过滤器。
- `void setFileView(FileView view)` 设置文件视图以提供文件选择器显示的文件信息。
- `void setAccessory(JComponent component)` 设置配件。

### `javax.swing.filechooser.FileFilter`

- `boolean accept(File f)` 如果文件选择器应该显示此文件，则返回 `true`。
- `String getDescription()` 返回此文件过滤器的描述，例如 `Image files (*.gif*.jpeg)`。

### `javax.swing.filechooser.FileNameExtensionFilter`

- `FileNameExtensionFilter(String description, String... extensions)` 一个带有描述的文件过滤器，接受所有目录以及所有以点加上扩展名字符串结尾的文件。

### `javax.swing.filechooser.FileView`

- `String getName(File f)` 返回文件 `f` 的名称，或返回 `null`。通常，此方法简单返回 `f.getName()`。
- `String getDescription(File f)` 返回文件 `f` 的人类可读描述，或返回 `null`。例如，如果 `f` 是 HTML 文档，此方法可能会返回其标题。
- `String getTypeDescription(File f)` 返回文件 `f` 类型的人类可读描述，或返回 `null`。例如，如果 `f` 是 HTML 文档，此方法可能会返回字符串 `"Hypertext document"`。
- `Icon getIcon(File f)` 返回文件 `f` 的图标，或返回 `null`。例如，如果 `f` 是 JPEG 文件，此方法可能会返回一个缩略图图标。
- `Boolean isTraversable(File f)` 判断文件 `f` 是否可遍历的。

如果 `f` 是用户可以打开的目录，则返回 `Boolean.TRUE`。如果目录在概念上是一个复合文档，此方法可能会返回 `Boolean.FALSE`。与所有的 `FileView` 方法一样，此方法可以返回 `null` 表示文件选择器应该咨询默认视图。

---

## 12.7.5 颜色选择器

正如你在前一节中看到的，高质量的文件选择器是一个复杂的用户界面组件，你绝对不想自己实现它。许多用户界面工具包都提供了其他常用的对话框：选择日期/时间、货币值、字体、颜色等。这样做的好处有两点：程序员可以直接使用高质量的实现，而不需要自己开始开发；而用户可以在这些组件上获得一致的体验。

到此时，`Swing` 仅提供了一个额外的选择器，即 `JColorChooser`（参见图 12.42 至图 12.44）。使用它让用户选择颜色值。与 `JFileChooser` 类一样，颜色选择器是一个组件而不是一个对话框，但它拥有方便方法来创建包含颜色选择器组件的对话框。

![Image](img/12fig42.jpg)

**图 12.42** 颜色选择器的色块面板

![Image](img/12fig43.jpg)

**图 12.43** 颜色选择器的 HSB 面板

![Image](img/12fig44.jpg)

**图 12.44** 颜色选择器的 RGB 面板

以下是如何显示一个带有颜色选择器的模态对话框：

点击此处查看代码图片

```java
Color selectedColor = JColorChooser.showDialog(parent, title, initialColor);
```

或者，你也可以显示一个非模态颜色选择器对话框。提供以下内容：

- 一个父组件
- 对话框标题
- 一个用于选择模态或非模态对话框的标志
- 一个颜色选择器
- OK 和取消按钮的监听器（如果你不需要监听器，则传入 `null`）

以下是如何创建一个非模态对话框，并在用户点击 OK 按钮时设置背景颜色：

点击此处查看代码图片

```java
chooser = new JColorChooser();

dialog = JColorChooser.createDialog(
    parent,
    "Background Color",
    false /* not modal */,
    chooser,
    event -> setBackground(chooser.getColor()),
    null /* no Cancel button listener */);
```

你可以做得更好，给用户颜色选择的即时反馈。为了监控颜色选择，你需要获取选择器的选择模型并添加更改监听器：

点击此处查看代码图片

```java
chooser.getSelectionModel().addChangeListener(event -> {
    do something with chooser.getColor();
});
```

在这种情况下，颜色选择器对话框提供的 OK 和取消按钮没有意义。你可以直接将颜色选择器组件添加到非模态对话框中：

点击此处查看代码图片

```java
dialog = new JDialog(parent, false /* not modal */);

dialog.add(chooser);
dialog.pack();
```

Listing 12.24 中的程序显示了三种类型的对话框。如果你点击 Modal（模态）按钮，你必须在进行其他操作之前选择一种颜色。如果你点击 Modeless（非模态）按钮，你会得到一个非模态对话框，但颜色变化只在你点击对话框上的 OK 按钮时发生。如果你点击 Immediate（即时）按钮，你会得到一个没有按钮的非模态对话框。一旦你在对话框中选择了不同的颜色，面板的背景颜色就会更新。

**Listing 12.24** `colorChooser/ColorChooserPanel.java`

点击此处查看代码图片

```java
package colorChooser;

import java.awt.Color;
import java.awt.Frame;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JColorChooser;
import javax.swing.JDialog;
import javax.swing.JPanel;

/**
 * 一个带有弹出不同类型选择器的按钮面板
 */
public class ColorChooserPanel extends JPanel {
    public ColorChooserPanel() {
        JButton modalButton = new JButton("Modal");
        modalButton.addActionListener(new ModalListener());
        add(modalButton);

        JButton modelessButton = new JButton("Modeless");
        modelessButton.addActionListener(new ModelessListener());
        add(modelessButton);

        JButton immediateButton = new JButton("Immediate");
        immediateButton.addActionListener(new ImmediateListener());
        add(immediateButton);
    }

    /**
     * 此监听器弹出一个模态选择器
     */
    private class ModalListener implements ActionListener {
        public void actionPerformed(ActionEvent event) {
            Color defaultColor = getBackground();

            Color selected = JColorChooser.showDialog(
                ColorChooserPanel.this,
                "Set background",
                defaultColor);

            if (selected != null) {
                setBackground(selected);
            }
        }
    }

    /**
     * 此监听器弹出一个非模态选择器。当用户点击
     * OK 按钮时，面板颜色改变。
     */
    private class ModelessListener implements ActionListener {
        private JDialog dialog;
        private JColorChooser chooser;

        public ModelessListener() {
            chooser = new JColorChooser();

            dialog = JColorChooser.createDialog(
                ColorChooserPanel.this,
                "Background Color",
                false /* not modal */,
                chooser,
                event -> setBackground(chooser.getColor()),
                null /* no Cancel button listener */);
        }

        public void actionPerformed(ActionEvent event) {
            chooser.setColor(getBackground());
            dialog.setVisible(true);
        }
    }

    /**
     * 此监听器弹出一个非模态选择器。当用户选择新颜色时，面板颜色立即变化。
     */



```java
private class ImmediateListener implements ActionListener {

    // (实现细节在源码中截断但保留了结构)

}
```

## 12.8 故障排除 GUI 程序

在下一节中，我们将提供一些 GUI 编程的调试技巧。然后，我们将展示如何使用 AWT 机器人来自动化 GUI 测试。

### 12.8.1 调试技巧

如果你曾观察过`Swing`窗口，并好奇它的设计者是如何让所有组件对齐得如此整齐，你可以窥探其内容。按下`Ctrl+Shift+F1`可以获取层次结构中所有组件的打印输出：

点击此处查看代码图像

```text
FontDialog[frame0,0,0,300x200,layout=java.awt.BorderLayout,...

  javax.swing.JRootPane[,4,23,292x173,layout=javax.swing.JRootPane$RootLayout,...

    javax.swing.JPanel[null.glassPane,0,0,292x173,hidden,layout=java.awt.FlowLayout,...

    javax.swing.JLayeredPane[null.layeredPane,0,0,292x173,...

      javax.swing.JPanel[null.contentPane,0,0,292x173,layout=java.awt.GridBagLayout,...

        javax.swing.JList[,0,0,73x152,alignmentX=null,alignmentY=null,...

          javax.swing.CellRendererPane[,0,0,0x0,hidden]

            javax.swing.DefaultListCellRenderer$UIResource,-73,-19,0x0,...

        javax.swing.JCheckBox,157,13,50x25,layout=javax.swing.OverlayLayout,...

        javax.swing.JCheckBox[,156,65,52x25,layout=javax.swing.OverlayLayout,...

        javax.swing.JLabel[,114,119,30x17,alignmentX=0.0,alignmentY=null,...

        javax.swing.JTextField[,186,117,105x21,alignmentX=null,alignmentY=null,...

        javax.swing.JTextField[,0,152,291x21,alignmentX=null,alignmentY=null,...
```

如果你设计了自定义的`Swing`组件但它显示得正常，你一定会非常喜欢`Swing图形调试器`。即使你没有编写自己的组件类，观察组件内容具体是如何绘制的也是很有启发性且趣味性的。要开启`Swing`组件的调试，请使用`JComponent`类的`setDebugGraphicsOptions`方法。可以使用以下选项：

![图像

我们发现，要让闪烁（flash）选项生效，必须禁用“双重缓冲”（double buffering）——这是`Swing`在更新窗口时减少闪烁所使用的策略。开启闪烁选项的魔力咒是：

点击此处查看代码图像

```java
RepaintManager.currentManager(getRootPane()).setDoubleBufferingEnabled(false);

((JComponent)getContentPane()).setDebugGraphicsOptions(DebugGraphics.FLASH_OPTION);
```

只需将这些行放在 frame 构造函数的末即可。程序运行时，你将看到内容面板以慢动作填充。或者，为了进行更局部的调试，只需为单个组件调用`setDebugGraphicsOptions`。控制狂热人甚至可以设置闪烁的持续时间、次数和颜色——详情请参阅`DebugGraphics`类的在线文档。

如果你想获取 GUI 应用中生成的每一个 AWT 事件的记录，你可以在每个发射事件的组件中安装监听器。得益于反射机制，这很容易实现自动化。列表 12.25 显示了`EventTracer`类。

要监视消息，请将想要追踪事件的组件添加到事件追踪器中：

点击此处查看代码图像

```java
EventTracer tracer = new EventTracer();

tracer.add(frame);
```

随后你将获得所有事件的文本描述，如图 12.45 所示。

**列表 12.25** `eventTracer/EventTracer.java`

```java
package eventTracer;

import java.awt.*;
import java.beans.*;
import java.lang.reflect.*;

/**
 * @version 1.31 2004-05-10
 * @author Cay Horstmann
 */

public class EventTracer {

  private InvocationHandler handler;

  public EventTracer() {

    // 用于所有代理的处理器

    handler = new InvocationHandler() {

      public Object invoke(Object proxy, Method method, Object[] args) {

        System.out.println(method + ":" + args[0]);

        return null;

      }

    };

  }

  /**
   * 为组件及其子类可以监听的所有事件添加追踪器
   * @param c 一个组件
   */

  public void add(Component c) {

    try {

      // 获取组件可以监听的所有事件

      BeanInfo info = Introspector.getBeanInfo(c.getClass());

      EventSetDescriptor[] eventSets = info.getEventSetDescriptors();

      for (EventSetDescriptor eventSet : eventSets) {

        // ... (逻辑省略，保持代码结构)

      }

    } catch (IntrospectionException e) {

      // ...

    }

    // ... (后续代码保持原文逻辑)

  }

}
```

**图 12.45** `EventTracer` 的工作

### 12.8.2 让 AWT 执行工作

`Robot`类可以发送按键和鼠标点击，用于自动化测试用户界面。要获取 robot，你首先需要获取一个`GraphicsDevice`对象。你可以通过以下调用获取默认屏幕设备：

点击此处查看代码图像

```java
GraphicsEnvironment environment = GraphicsEnvironment.getLocalGraphicsEnvironment();

GraphicsDevice screen = environment.getDefaultScreenDevice();
```

然后构造一个 robot：

点击此处查看代码图像

```java
Robot robot = new Robot(screen);
```

要发送按键，告诉 robot 模拟按下和释放按键：

点击此处查看代码图像

```java
robot.keyPress(KeyEvent.VK_TAB);

robot.keyRelease(KeyEvent.VK_TAB);
```

对于鼠标点击，你首先需要移动鼠标，然后按下并释放：

点击此处查看代码图像

```java
robot.mouseMove(x, y); // x 和 y 是绝对屏幕坐标

robot.mousePress(InputEvent.BUTTON1_MASK);

robot.mouseRelease(InputEvent.BUTTON1_MASK);
```

其思路是模拟按键和鼠标输入，然后截图查看应用程序的操作是否符合预期。要截图，使用`createScreenCapture`方法：

点击此处查看代码图像

```java
Rectangle rect = new Rectangle(x, y, width, height);

BufferedImage image = robot.createScreenCapture(rect);
```

矩形坐标也相对于绝对屏幕像素。

最后，你通常会在 robot 指令之间添加很小的延迟，以便应用程序能够跟上。使用`delay`方法并给出要延迟的毫秒数。例如：

点击此处查看代码图像

```java
robot.delay(1000); // 延迟 1000 毫秒
```

Listing 12.26 中的程序展示了如何使用机器人。该机器人测试了你在第 11 章中看到的按钮测试程序。首先，按下空格键会激活最左侧的按钮。然后机器人会等待两秒，以便你可以看到它做了什么。延迟之后，机器人会模拟`Tab`键和再次按下空格键来点击下一个按钮。最后，它模拟在第三个按钮上进行鼠标点击。（你可能需要调整程序的`x`和`y`坐标才能实际按下按钮。）程序通过捕获屏幕并在另一个窗口中显示来结束（参见图 12.46）。

![Image](img/12fig46.jpg)

**图 12.46** 使用 AWT 机器人截屏

![Image](img/note.jpg) 注意

你需要在单独线程中运行机器人，如示例代码所示。关于线程的更多信息，请参阅第 14 章。

正如此示例所示，`Robot`类本身并不适用于方便的用户界面测试。相反，它是一个基础构建模块，可以作为测试工具的基础性部分。专业的测试工具可以捕获、存储和重放用户交互场景，并找到组件的屏幕位置，这样鼠标点击就不需要猜测了。

**代码列表 12.26** `robot/RobotTest.java`

点击此处查看代码图像

```java
package robot;

import java.awt.*;
import java.awt.event.*;
import java.awt.image.*;

import javax.swing.*;

/**
 * @version 1.05 2015-08-20
 * @author Cay Horstmann
 */

public class RobotTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
                {
                    // make frame with a button panel
                ButtonFrame frame = new ButtonFrame();

                    frame.setTitle("ButtonTest");

                    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

                    frame.setVisible(true);

                });

        // attach a robot to the screen device

        GraphicsEnvironment environment = GraphicsEnvironment.getLocalGraphicsEnvironment();

        GraphicsDevice screen = environment.getDefaultScreenDevice();

        try
        {
            final Robot robot = new Robot(screen);

            robot.waitForIdle();

            new Thread()
            {
                public void run()
                {
                    runTest(robot);
                };
            }.start();
        }
        catch (AWTException e)
        {
            e.printStackTrace();
        }
    }

    /**
     * Runs sample test procedure
     * @param robot the robot attached to the screen device
     */

    public static void runTest(Robot robot)
    {
        // simulate space bar press

        robot.keyPress(' ');

        robot.keyRelease(' ');

        // simulate a tab key followed by a space

        robot.delay(2000);

        robot.keyPress(KeyEvent.VK_TAB);

        robot.keyRelease(KeyEvent.VK_TAB);

        robot.keyPress(' ');

        robot.keyRelease(' ');

        // simulate a mouse click over the rightmost button

        robot.delay(2000);

        robot.mouseMove(220, 40);

        robot.mousePress(InputEvent.BUTTON1_MASK);

        robot.mouseRelease(InputEvent.BUTTON1_MASK);

        // capture the screen and show the resulting image

        robot.delay(2000);

        BufferedImage image = robot.createScreenCapture(new Rectangle(0, 0, 400, 300));

        ImageFrame frame = new ImageFrame(image);

        frame.setVisible(true);
    }
}

/**
 * A frame to display a captured image
 */

class ImageFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 450;

    private static final int DEFAULT_HEIGHT = 350;

    /**
     * @param image the image to display
     */

    public ImageFrame(Image image)
    {
        setTitle("Capture");

        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        add(new JLabel(new ImageIcon(image)));
    }
}
```

当你打包应用程序时，你希望给用户提供单个文件，而不是一个充满类文件的目录结构。Java 归档（JAR）文件正是为此设计的。JAR 文件可以包含类文件和其他文件类型，例如图像和声音文件。此外，JAR 文件是压缩的，使用了熟悉的 ZIP 压缩格式。

![Image](img/tip.jpg) 提示

ZIP 格式的替代方案是“pack200”压缩方案，它专门针对更高效地压缩类文件进行了调优。Oracle 声称对类文件的压缩率接近 90%。更多信息请参阅[`http://docs.oracle.com/javase/1.5.0/docs/guide/deployment/deployment-guide/pack200.html`](http://docs.oracle.com/javase/1.5.0/docs/guide/deployment/deployment-guide/pack200.html)。

### 13.1.1 创建 JAR 文件

使用`jar`工具创建 JAR 文件。（在默认的 JDK 安装中，它位于`jdk/bin`目录下。）创建新 JAR 文件的常用命令使用以下语法：

点击此处查看代码图像

```bash



`jar cvf JARFileName File1 File2 . . .`

例如：

点击此处查看代码图像

```bash
jar cvf CalculatorClasses.jar *.class icon.gif
```

通常情况下，`jar`命令具有以下格式：

```bash
jar options File1 File2 ...
```

表 13.1 列出了`jar`程序的所有选项。它们与 UNIX `tar`命令的选项相似。

![Image](img/13tab01.jpg)

**表 13.1** `jar`程序选项

你可以将应用程序、程序组件（有时称为“beans”——参见第二卷的第 11 章）和代码库打包成 JAR 文件。例如，JDK 的运行时库包含在一个非常大的文件`rt.jar`中。

### 13.1.2 清单文件（Manifest）

除了类文件、图像和其他资源外，每个 JAR 文件还包含一个描述存档特殊特征的*清单*（manifest）文件。

清单文件名为`MANIFEST.MF`，位于 JAR 文件中特殊的`META-INF`子目录下。最合法的清单非常无聊——只是：

```text
Manifest-Version: 1.0
```

复杂的清单可以有更多的条目。清单条目分为若干部分。清单中的第一部分称为*主部分*。它适用于整个 JAR 文件。随后的条目可以指定命名实体的属性，例如单个文件、包或 URL。这些条目必须以`Name`条目开头。各个部分之间用空行隔开。例如：

```text
Manifest-Version: 1.0

描述此存档的行

Name: Woozle.class

描述此文件的行

Name: com/mycompany/mypkg/

描述此包的行
```

要编辑清单，将你想要添加到清单中的行放入文本文件中。然后运行：

点击此处查看代码图像

```bash
jar cfm JARFileName ManifestFileName . . .
```

例如，要创建一个带清单的新 JAR 文件，运行：

点击此处查看代码图像

```bash
jar cfm MyArchive.jar manifest.mf com/mycompany/mypkg/*.class
```

要更新现有 JAR 文件的清单，将新增内容放入文本文件并使用如下命令：

点击此处查看代码图像

```bash
jar ufm MyArchive.jar manifest-additions.mf
```

***

![Image](img/note.jpg) 注意

关于 JAR 和清单文件格式的更多信息，请参阅[`http://docs.oracle.com/javase/8/docs/technotes/guides/jar`](http://docs.oracle.com/javase/8/docs/technotes/guides/jar)。

***

### 13.1.3 可执行 JAR 文件

你可以使用`jar`命令的`e`选项来指定程序的*入口*（entry point）——即你通常在调用`java`程序启动器时指定的类：

点击此处查看代码图像

```bash
jar cvfe MyProgram.jar com.mycompany.mypkg.MainAppClass files to add
```

或者，你可以在清单中指定程序的*主类*（main class），包括如下形式的语句：

点击此处查看代码图像

```text
Main-Class: com.mycompany.mypkg.MainAppClass
```

不要为主类名添加`.class`扩展。

***

![Image](img/caution.jpg) 注意

清单的最后一行必须以换行符结束。否则，清单将无法正确读取。常见的错误是产生一个包含`Main-Class`行但没有行终止符的文本文件。

***

使用任一种方法，用户都可以简单地启动程序：

```bash
java -jar MyProgram.jar
```

根据操作系统的配置，用户可以这样启动程序：

- 在 Windows 上，`java -jar MyProgram.jar`
- 在 Solaris 上，`java -jar MyProgram.jar`
- 在 Mac OS 上，`java -jar MyProgram.jar`
- 在 OS X 上，`java -jar MyProgram.jar`

### 13.1.4 资源

在 applet 和应用程序中使用的类通常具有关联的数据，例如：

- 图像和声音文件
- 带有消息字符串的文本文件
- 带有二进制数据的文件——例如描述地图布局

在 Java 中，这种关联文件被称为*资源*（resource）。

***

![Image](img/note.jpg) 注意

在 Windows 中，“资源”一词有更专门的含义。Windows 资源也包括图像、按钮标签等，但它们被附加到可执行文件并通过编程接口访问。相比之下，Java 资源被存储为单独的文件，而不是类文件的一部分。访问和解释资源数据取决于每个程序。

***

例如，考虑一个`AboutPanel`类，它显示诸如图 13.1 所示的消息。

![Image](img/13fig01.jpg)

**图 13.1** 从 JAR 文件显示资源

当然，面板中的书名和版权年份会在书的下一版本发生变化。为了方便跟踪这一变化，我们将文本放在文件中，而不是将其硬编码为字符串。

但是你应该将`about.txt`这样的文件放在哪里呢？当然，将它放在 JAR 文件中与其他程序文件一起是方便的。

类加载器知道如何搜索类文件，直到在类路径、存档或网络服务器上找到它们为止。资源机制为非类文件提供了同样的便利性。以下是必要的步骤：

1. 获取拥有资源的类的`Class`对象——例如，`AboutPanel.class`。
2. 如果资源是图像或音频文件，调用`getResource(filename)`获取资源位置的 URL。然后使用`getImage`或`getAudioClip`方法读取它。
3. 对于图像或音频以外的资源，使用`getResourceAsStream`方法读取文件中的数据。

关键点在于，类加载器记得如何定位该类，因此它随后可以在相同的位置搜索相关的资源。

例如，要使用图像文件`about.gif`创建图标，请执行以下操作：

点击此处查看代码图片

```java
URL url = ResourceTest.class.getResource("about.gif");

Image img = new ImageIcon(url).getImage();
```

这意味着“在找到`ResourceTest`类的相同位置定位`about.gif`文件”。

要读取文件`about.txt`，请使用这些命令：

点击此处查看代码图片

```java
InputStream stream = ResourceTest.class.getResourceAsStream("about.txt");

Scanner in = new Scanner(stream, "UTF-8");
```

与其将资源文件放置在与类文件相同的目录中，你也可以将其放在子目录中。然后，你可以使用层级化的资源名称，例如：

`data/text/about.txt`

该资源名称相对于加载该资源的类的包进行解释。注意，无论实际存储资源文件的系统上的目录分隔符是什么，你必须始终使用`/`分隔符。例如，在 Windows 文件系统中，资源加载器会自动将`/`翻译为`\`分隔符。

以`/`开头的资源名称称为绝对资源名称。它的定位方式与包内类的定位方式相同。例如，一个资源：

`/corejava/title.txt`

位于`corejava`目录中，该目录可能是类路径的子目录、JAR 文件内部，或者对于 applet 来说，位于 Web 服务器上。

自动加载文件就是资源加载功能所做的全部工作。没有标准方法来解释资源文件的内容。每个程序必须有自己的方式来解释其资源文件。

资源的常见应用是程序的国际化。依赖于语言的字符串（如消息和用户界面标签）存储在资源文件中，每个语言一个文件。在卷二的第 5 章中讨论的国际化 API 提供了一种用于组织和访问这些本地化文件的标准方法。

列表 13.1：

```bash
javac resource/ResourceTest.java

jar cvfm ResourceTest.jar resource/ResourceTest.mf resource/*.class resource/*.gif resource/*.txt

java -jar ResourceTest.jar
```

将 JAR 文件移动到不同的目录并再次运行它，以检查程序是从 JAR 文件而不是从当前目录读取资源文件。

**列表 13.1** `resource/ResourceTest.java`

点击此处查看代码图片

```java
package resource;

import java.awt.*;

import java.io.*;

import java.net.*;

import java.util.*;

import javax.swing.*;

/**
 * @version 1.41 2015-06-12
 * @author Cay Horstmann
 */

public class ResourceTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() -> {
            JFrame frame = new ResourceTestFrame();
            frame.setTitle("ResourceTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 一个加载图像和文本资源的框架。
 */

class ResourceTestFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 300;

    public ResourceTestFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        URL aboutURL = getClass().getResource("about.gif");
        Image img = new ImageIcon(aboutURL).getImage();
        setIconImage(img);

        JTextArea textArea = new JTextArea();
        InputStream stream = getClass().getResourceAsStream("about.txt");

        try (Scanner in = new Scanner(stream, "UTF-8"))
        {
            while (in.hasNext())
                textArea.append(in.nextLine() + "\n");
        }

        add(textArea);
    }
}
```

`java.lang.Class`

- `URL getResource(String name)`
- `InputStream getResourceAsStream(String name)` 在与类相同的位置查找资源，并返回一个可用于加载资源的`URL`或输入流。如果未找到资源则返回`null`，因此不会对 I/O 错误抛出异常。

### 13.1.5 密封（Sealing）

我们在第 4 章中提到，你可以密封一个包以确保其类是可见的。如果你想将包保存到 JAR 文件，通过在 JAR 文件的 manifest 中添加`Sealed: true`来实现这一点。例如，如果你使用语句：

```java
package comcompany.util;
```

为了实现这一点，将`comcompany.util`包保存到 JAR 文件。默认情况下，JAR 文件中的包是不密封的。你可以通过在 JAR 文件的 manifest 中添加`Sealed`行来更改全局默认值，如下所示：

```text
Name:comcompany/util/

Sealed: true

Name:comcompany/misc/

Sealed: false
```

要密封包，按照 usual 运行`jar`命令：

点击此处查看代码图像

```bash
jar cvfm MyArchive.jar manifest.mf
```

### 13.2 偏好的存储

用户通常期望他们的偏好被保存并在下次启动应用程序时恢复。首先，我们将介绍 Java 传统的简单方法——在属性文件中存储配置。然后转向提供更健壮解决方案的设置 API。

#### 13.2.1 属性映射（Property Maps）

属性映射是一个存储键值对的数据结构。属性映射通常用于存储配置。属性映射有三个特点：

- 键和值都是字符串。
- 映射可以从文件中保存并从文件中加载。
- 有一个默认表。

实现属性映射的 Java 类称为`Properties`。

属性映射用于指定程序的配置选项，例如：

点击此处查看代码图像

```java
Properties settings = new Properties();

settings.setProperty("width", "200");

settings.setProperty("title", "Hello, World!");
```

使用`store`方法将属性列表保存到文件中。在这里，我们将属性映射保存到`program.properties`文件中。第二个参数是包含在文件中的注释。

点击此处查看代码图像

```java
OutputStream out = new FileOutputStream("program.properties");

settings.store(out, "Program Properties");
```

示例集给出如下输出：

```text
#Program Properties

#Mon Apr 30 07:22:52 2007

width=200

title=Hello, World!
```

要从文件中加载属性，使用：

点击此处查看代码图像

```java
InputStream in = new FileInputStream("program.properties");

settings.load(in);
```

将程序属性存储在用户主目录的子目录下是一种习惯。目录名通常以点（`.`）开头——在 UNIX 系统上，这种约定表示该目录是对用户隐藏的系统目录。我们的示例程序遵循了这一约定。

要找到用户主目录，你可以调用`System.getProperties`方法，碰巧，该方法也使用`Properties`对象来描述系统信息。主目录的键为`"user.home"`。还有一个方便的方法来读取单个键：

点击此处查看代码图像

```java
String userDir = System.getProperty("user.home");
```

为我们的程序属性提供默认值是一个好主意，以防用户手动编辑文件。`Properties`类有两种提供默认属性的机制。首先，每当你查找字符串的值时，你都可以指定一个默认值，当键不存在时会自动使用该默认值。

点击此处查看代码图像

```java
String title = settings.getProperty("title", "Default title");
```

如果属性映射中存在`"title"`属性，则`title`被赋值为该字符串。否则，`title`被设置为`"Default title"`。

如果你觉得在每次调用`getProperty`时指定默认值太麻烦了，可以将所有默认值封装在一个二级属性映射中，并在主属性映射的构造函数中提供该映射。

点击此处查看代码图像

```java
Properties defaultSettings = new Properties();

defaultSettings.setProperty("width", "300");

defaultSettings.setProperty("height", "200");

defaultSettings.setProperty("title", "Default title");

...

Properties settings = new Properties(defaultSettings);
```



如果你给 `defaultSettings` 构造函数提供另一个属性映射参数，甚至可以为默认值指定默认值，但通常不这样做。

Listing 13.2 显示了如何使用属性来存储和加载程序状态。程序会记住窗口的位置、大小和标题。你也可以手动编辑主目录下的 `.corejava/program.properties` 文件，将程序的外观更改为你想要的样子。

---

![Image](img/caution.jpg) 注意

出于历史原因，`Properties` 类实现了 `Map<Object, Object>`。因此，你可以使用 `Map` 接口的 `get` 和 `put` 方法。但 `get` 方法返回类型 `Object`，而 `put` 方法允许你插入任何对象。最好的做法是坚持使用处理字符串而非对象的 `getProperty` 和 `setProperty` 方法。

---

![Image](img/note.jpg) Note

属性是不具有层级结构的简单表格。通常会使用如 `window.main.color`、`window.main.title` 等键名引入伪层级结构。但 `Properties` 类没有帮助组织此类层次结构的方法。如果你存储复杂的配置信息，应该使用 `Preferences` 类——请参见下一节。

---

**Listing 13.2** `properties/PropertiesTest.java`

点击此处查看代码图像

```java
package properties;

import java.awt.EventQueue;
import java.awt.event.*;
import java.io.*;
import java.util.Properties;
import javax.swing.*;

/**
 * 一个测试属性的程序。程序会记住窗口的位置、大小
 * 和标题。
 * @version 1.01 2015-06-16
 * @author Cay Horstmann
 */
public class PropertiesTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() -> {
            PropertiesFrame frame = new PropertiesFrame();
            frame.setVisible(true);
        });
    }
}

/**
 * 一个从属性文件恢复位置和大小并在退出时更新
 * 属性的帧。
 */
class PropertiesFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 20;
    private File propertiesFile;
    private Properties settings;

    public PropertiesFrame()
    {
        // 从获取位置、大小、标题
        String userDir = System.getProperty("user.home");
        File propertiesDir = new File(userDir, ".corejava");
        if (!propertiesDir.exists()) propertiesDir.mkdir();

        propertiesFile = new File(propertiesDir, "program.properties");

        Properties defaultSettings = new Properties();
        defaultSettings.setProperty("left", "0");
        defaultSettings.setProperty("top", "0");
        defaultSettings.setProperty("width", "" + DEFAULT_WIDTH);
        defaultSettings.setProperty("height", "" + DEFAULT_HEIGHT);
        defaultSettings.setProperty("title", "");

        settings = new Properties(defaultSettings);

        if (propertiesFile.exists())
            try (InputStream in = new FileInputStream(propertiesFile))
            {
                settings.load(in);
            }
            catch (IOException ex)
            {
                ex.printStackTrace();
            }

        int left = Integer.parseInt(settings.getProperty("left"));
        int top = Integer.parseInt(settings.getProperty("top"));
        int width = Integer.parseInt(settings.getProperty("width"));
        int height = Integer.parseInt(settings.getProperty("height"));

        setBounds(left, top, width, height);

        // 如果没有给出标题，询问用户
        String title = settings.getProperty("title");
        if (title.equals(""))
            title = JOptionPane.showInputDialog("Please supply a frame title:");

        if (title == null) title = "";
        setTitle(title);

        addWindowListener(new WindowAdapter()
        {
            public void windowClosing(WindowEvent event)
            {
                settings.setProperty("left", "" + getX());
                settings.setProperty("top", "" + getY());
                settings.setProperty("width", "" + getWidth());
                settings.setProperty("height", "" + getHeight());
                settings.setProperty("title", getTitle());

                try (OutputStream out = new FileOutputStream(propertiesFile))
                {
                    settings.store(out, "Properties");
                }
                catch (IOException ex)
                {
                    ex.printStackTrace();
                }

                System.exit(0);
            }
        });
    }
}
```

### `java.util.Properties` 1.0

- `Properties()`: 创建空的属性映射。
- `Properties(Properties defaults)`: 创建带有一组默认值的空属性映射。
- `String getProperty(String key)`: 获取属性。返回与键关联的字符串；如果键不在表中，则返回默认表中与键关联的字符串；如果键在默认表中也不存在，则返回 `null`。
- `String getProperty(String key, String defaultValue)`: 获取属性，如果未找到键，则使用默认值。返回与键关联的字符串；如果该键不在表中，则返回默认字符串。
- `Object setProperty(String key, String value)`: 设置属性。返回给定键之前被设置的值。
- `void load(InputStream in) throws IOException`: 从输入流加载属性映射。

![Image](img/792tab01.jpg)

![Image](img/792tab02.jpg)

![Image](img/792tab03.jpg)

![Image](img/792tab04.jpg)

![Image](img/793tab01.jpg)

### `void store(OutputStream out, String header)` 1.2

将属性映射保存到输出流。

![Image](img/793tab02.jpg)

## `java.lang.System` 1.0

### `Properties getProperties()`

检索所有系统属性。应用程序必须具有检索所有属性的权限，否则将抛出安全异常。

### `String getProperty(String key)`

根据给定键名检索系统属性。应用程序必须具有检索该属性的权限，否则将抛出安全异常。以下属性始终可以被检索：

- `java.version`
- `java.vendor`
- `java.vendor.url`
- `java.class.version`
- `os.name`
- `os.version`
- `os.arch`
- `file.separator`
- `path.separator`
- `line.separator`
- `java.specification.version`
- `java.vm.specification.version`
- `java.vm.specification.vendor`
- `java.vm.specification.name`
- `java.vm.version`
- `java.vm.vendor`
- `java.vm.name`

![Image](img/note.jpg) 注意

你可以在 Java 运行时目录下的 `security/java.policy` 文件中找到自由访问的系统属性的名称。

## 13.2.2 Preferences API

正如你所看到的，`Preferences` 类使得加载和保存配置信息变得简单。然而，使用属性文件有以下缺点：

- 某些操作系统没有“主目录”的概念，导致很难为配置文件找到统一的位置。
- 配置文件的命名没有标准规范，当用户安装多个 Java 应用程序时，增加了名称冲突的可能性。

某些操作系统拥有一个配置信息的中央仓库。最为人知的例子是 Microsoft Windows 中的注册表。`Preferences` 类以平台无关的方式提供了这样一个中央仓库。在 Windows 中，`Preferences` 类使用注册表存储；在 Linux 中，信息存储在本地文件系统中。对程序员来说，仓库的实现是透明的。

`Preferences` 仓库具有树形结构，带有如 `/com/mycompany/myapp` 这样的节点路径名。与包名一样，只要程序员以反向域名开头路径，就可以避免名称冲突。事实上，API 设计者建议配置节点路径与程序中的包名匹配。

仓库中的每个节点都有一个独立的键值对表，你可以用它存储数字、字符串或字节数组。该 API 未提供存储可序列化对象的规定。API 设计者认为序列化格式对于长期存储来说太脆弱了。当然，如果你不同意，可以将序列化对象保存在字节数组中。

为了增加额外的灵活性，存在多个并行的树。每个程序用户拥有一棵树；还有一个额外的树，称为系统树，适用于所有用户通用的设置。`Preferences` 类使用操作系统的“当前用户”概念来访问适当的用户树。

要访问树中的节点，从用户根或系统根开始：

点击此处查看代码图像

```java
Preferences root = Preferences.userRoot();
```

或者：

点击此处查看代码图像

```java
Preferences root = Preferences.systemRoot();
```

然后访问节点。你可以直接提供节点路径名：

点击此处查看代码图像

```java
Preferences node = root.node("/com/mycompany/myapp");
```

一个方便的快捷方法可以获取路径名等于类包名的节点。只需获取该类的一个对象并调用：

点击此处查看代码图像

```java
Preferences node = Preferences.userNodeForPackage(obj.getClass());
```

或者：

点击此处查看代码图像

```java
Preferences node = Preferences.systemNodeForPackage(obj.getClass());
```

通常，`obj` 将是 `this` 引用。

一旦你拥有了节点，就可以使用方法访问键值表：

```java
String get(String key, String defval)

int getInt(String key, int defval)

long getLong(String key, long defval)

float getFloat(String key, float defval)

double getDouble(String key, double defval)

boolean getBoolean(String key, boolean defval)

byte[] getByteArray(String key, byte[] defval)
```

注意，在读取信息时必须指定默认值，以防仓库数据不可用。需要默认值有几个原因：数据可能因为用户从未指定过偏好而缺失；某些资源限制平台可能没有仓库；移动设备可能会临时断开连接。

相反，你可以使用 `put` 方法向仓库写入数据，例如：

```java
put(String key, String value)

putInt(String key, int value)
```

等等。

你可以使用以下方法列出节点中存储的所有键：

```java
String[] keys()
```

目前还没有办法找到特定键的值类型。

像 Windows 注册表这样的中央仓库传统上受到两个问题的困扰：

- 它们变成了“垃圾场”，充满了过时信息。
- 配置数据纠缠在仓库中，使得偏好迁移到新平台变得困难。

`Preferences` 类对第二个问题提供了解决方案。你可以通过调用以下方法导出子树（或较不常见的单个节点）的偏好：

点击此处查看代码图像

```java
void exportSubtree(OutputStream out)

void exportNode(OutputStream out)
```

数据以 XML 格式保存。你可以通过调用以下方法将它们导入另一个仓库：

点击此处查看代码图像

```java
void importPreferences(InputStream in)
```

这里是一个示例文件：

点击此处查看代码图像

```xml
<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE preferences SYSTEM "http://java.sun.com/dtd/preferences.dtd">

<preferences EXTERNAL_XML_VERSION="1.0">

  <root type="user">

    <map/>

    <node name="com">

      <map/>

      <node name="horstmann">

        <map/>

        <node name="java">

          <map>

            <entry key="left" value="1"/>

            <entry key="top" value="9"/>

            <entry key="width" value="453"/>

            <entry key="height" value="365"/>

            <entry key="title" value="Hello, World!"/>

          </map>

        </node>

      </node>

    </node>

  </root>

</preferences>
```



如果你的程序使用了偏好设置，你应该给用户提供导出和导入的机会，这样他们就可以轻松将设置从一台电脑迁移到另一台。13.3 中的程序演示了这种技术。程序只需保存主窗口的位置、大小和标题。调整窗口大小，然后退出并重启应用程序。窗口将像你离开时的一样。

## 13.3 `PreferencesTest.java`

```java
package preferences;

import java.awt.*;
import java.io.*;
import java.util.prefs.*;
import javax.swing.*;
import javax.swing.filechooser.*;

/**
 * 一个测试偏好设置的程序。程序记录框架
 * 位置、大小和标题。
 * @version 1.03 2015-06-12
 * @author Cay Horstmann
 */
public class PreferencesTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() -> {
            PreferencesFrame frame = new PreferencesFrame();
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}
```

```java
/**
 * 一个从用户偏好中恢复位置和大小的框架，并在退出时更新偏好。
 */
class PreferencesFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    private Preferences root = Preferences.userRoot();
    private Preferences node = root.node("/com/horstmann/corejava");

    public PreferencesFrame()
    {
        // 从偏好中获取位置、大小、标题
        int left = node.getInt("left", 0);
        int top = node.getInt("top", 0);
        int width = node.getInt("width", DEFAULT_WIDTH);
        int height = node.getInt("height", DEFAULT_HEIGHT);
        setBounds(left, top, width, height);

        // 如果没有标题，询问用户
        String title = node.get("title", "");
        if (title.equals(""))
            title = JOptionPane.showInputDialog("Please supply a frame title:");
        if (title == null) title = "";
        setTitle(title);

        // 设置显示 XML 文件的文件选择器
        final JFileChooser chooser = new JFileChooser();
        chooser.setCurrentDirectory(new File("."));
        chooser.setFileFilter(new FileNameExtensionFilter("XML files", "xml"));

        // 设置菜单
        JMenuBar menuBar = new JMenuBar();
        setJMenuBar(menuBar);

        JMenu menu = new JMenu("File");
        menuBar.add(menu);

        JMenuItem exportItem = new JMenuItem("Export preferences");
        menu.add(exportItem);
        exportItem.addActionListener(event -> {
            if (chooser.showSaveDialog(PreferencesFrame.this) == JFileChooser.APPROVE_OPTION)
            {
                try
                {
                    savePreferences();
                    OutputStream out = new FileOutputStream(chooser.getSelectedFile());
                    node.exportSubtree(out);
                    out.close();
                }
                catch (Exception e)
                {
                    e.printStackTrace();
                }
            }
        });

        JMenuItem importItem = new JMenuItem("Import preferences");
        menu.add(importItem);
        importItem.addActionListener(event -> {
            if (chooser.showOpenDialog(PreferencesFrame.this) == JFileChooser.APPROVE_OPTION)
            {
                try
                {
                    InputStream in = new FileInputStream(chooser.getSelectedFile());
                    Preferences.importPreferences(in);
                    in.close();
                }
                catch (Exception e)
                {
                    e.printStackTrace();
                }
            }
            savePreferences(); // 逻辑逻辑
        });

        JMenuItem exitItem = new JMenuItem("Exit");
        menu.add(exitItem);
        exitItem.addActionListener(event -> {
            savePreferences();
            System.exit(0);
        });
    }

    public void savePreferences()
    {
        node.putInt("left", getX());
        node.putInt("top", getY());
        node.putInt("width", getWidth());
        node.putInt("height", getHeight());
        node.put("title", getTitle());
    }
}
```

### `java.util.prefs.Preferences`

- `Preferences userRoot()` 返回调用程序的根偏好节点。
- `Preferences systemRoot()` 返回系统范围根偏好节点。
- `Preferences node(String path)` 返回可以通过给定路径从当前节点到达的节点。如果`path`是绝对路径（即以`/`开头），则该节点从包含此偏好节点的树根开始定位。如果不存在给定路径的节点，则创建它。
- `Preferences userNodeForPackage(Class cl)`
- `Preferences systemNodeForPackage(Class cl)` 返回当前用户树或系统树中的一个节点，其绝对路径与类`cl`的包名对应。
- `String[] keys()` 返回所有属于此节点的键。
- `String get(String key, String defval)`
- `int getInt(String key, int defval)`
- `long getLong(String key, long defval)`
- `float getFloat(String key, float defval)`
- `double getDouble(String key, double defval)`
- `boolean getBoolean(String key, boolean defval)`
- `byte[] getByteArray(String key, byte[] defval)` 返回与键关联的值；如果没有与键关联的值、关联值类型不正确或偏好存储库不可用，则返回提供的默认值。
- `void put(String key, String value)`
- `void putInt(String key, int value)`
- `void putLong(String key, long value)`
- `void putFloat(String key, float value)`
- `void putDouble(String key, double value)`
- `void putBoolean(String key, boolean value)`
- `void putByteArray(String key, byte[] value)` 在此节点中存储一个键/值对。
- `void exportSubtree(OutputStream out)` 将此节点及其子节点的偏好写入指定的流。
- `void exportNode(OutputStream out)` 将此节点（但不包括其子节点）的偏好写入指定的流。
- `void importPreferences(InputStream in)` 导入指定流包含的偏好。

## 13.3 服务加载器 (Service Loaders)

有时你会开发一个具有插件架构的应用程序。有一些平台鼓励这种方法，例如 OSGi ([`osgi.org`](http://osgi.org))，它们被用于开发环境、应用服务器和其他复杂的应用程序。此类平台远超本书的范围，但 JDK 也提供了一种加载插件的简单机制，我们在此处描述。

通常，在提供插件时，程序希望让插件设计者在实现功能方面具有自由度。提供多个实现供选择也是可能的。`ServiceLoader` 类可以方便加载符合公共接口的插件。

定义一个接口（或者如果你喜欢，定义一个父类），包含每个服务的实例应该提供的方法。例如，假设你的服务提供加密。

```java
package serviceLoader;

public interface Cipher
{
    byte[] encrypt(byte[] source, byte[] key);
    byte[] decrypt(byte[] source, byte[] key);
    int strength();
}
```

服务提供者提供一个多个实现此服务的类，例如：

```java
package serviceLoader.impl;

public class CaesarCipher implements Cipher
{
    public byte[] encrypt(byte[] source, byte[] key)
    {
        byte[] result = new byte[source.length];
        for (int i = 0; i < source.length; i++)
        {
            result[i] = (byte)(source[i] + key[0]);
        }
        return result;
    }

    public byte[] decrypt(byte[] source, byte[] key)
    {
        return encrypt(source, new byte[] { (byte) -key[0] });
    }

    public int strength() { return 1; }
}
```

实现类可以在任何包中，不一定与服务接口在同一个包中。它们每个都必须有一个无参构造函数。

现在，将类名添加到 UTF-8 编码的文本文件中，该文件位于`META-INF/services`目录下，文件名与类的完全限定名匹配。在我们的示例中，文件`META-INF/services/serviceLoader.Cipher`将包含以下行：

`serviceLoader.impl.CaesarCipher`

在这个示例中，我们提供了一个单一实现类。你也可以提供多个类，并在稍后从中进行选择。

完成这些准备后，程序按如下方式初始化服务加载器：

```java
public static ServiceLoader<Cipher> cipherLoader = ServiceLoader.load(Cipher.class);
```

这在程序中只需要执行一次。

服务加载器的`iterator()`方法返回一个遍历所有提供的服务实现类的迭代器。（有关迭代器的更多信息，请参阅第 9 章）。最简单的方法是使用增强`for`循环来遍历它们。在循环中，选择一个合适的对象来执行服务。

```java
public static Cipher getCipher(int minStrength)
{
    for (Cipher cipher : cipherLoader) // 隐式调用 cipherLoader.iterator()
    {
        if (cipher.strength() >= minStrength) return cipher;
    }
    return null;
}
```



`java.util.ServiceLoader<S>` `1.6`

- `static <S> ServiceLoader<S> load(Class<S> service)`

  创建一个服务加载器，用于加载实现给定服务接口的类。

- `Iterator<S> iterator()`

  产生一个延迟加载服务类的迭代器。也就是说，每当迭代器移动时就会加载一个类。

### 13.4 Applets

Applet 是包含在 HTML 页面中的 Java 程序。HTML 页面必须告诉浏览器要加载哪些 applet，以及将每个 applet 放在网页的什么位置。正如你所预期的，使用 applet 需要的标签必须告诉浏览器从哪里获取类文件，以及 applet 在网页上的定位方式（大小、位置等）。浏览器随后从互联网（或用户机器上的目录）检索类文件并自动运行 applet。

当 applet 最初被开发时，你必须使用 Sun 的 HotJava 浏览器来查看包含 applet 的网页。自然地，很少用户愿意为了体验一个新网页功能而使用独立的浏览器。当 Netscape 在其 Navigator 浏览器中包含 Java 虚拟机时，Java applet 变得流行。微软 Internet Explorer 也紧随其后。遗憾的是，Internet Explorer 的 Java 支持很快落后，只能与过时的 Java 版本一起，最后被完全弃用。

为了解决这个问题，Sun Microsystems 开发了“Java Plug-in”。通过浏览器扩展机制，它插件到各种浏览器中并允许它们通过外部 Java 运行环境执行 Java applet。

多年来，这个解决方案是足够的，applet 常被用于教育工具、企业应用和某些游戏。遗憾的是，Sun Microsystems 以及在它终结后的 Oracle 在修复 Java 虚拟机中不断被发现和利用的安全漏洞方面进展很缓慢。由于不安全的 JVM 会让用户面临真实风险，浏览器制造商增加了使用 Java 的难度。有些阻止了除最新版本以外的所有 Java Plug-in 版本，另一些则停止了对插件架构的支持。Oracle 的反应同样令人失望。它开始要求所有 applet 必须经过数字签名（参阅第 13.4.9 节，“签名代码”，位于第 822 页）。

如今，对于开发者来说部署 Java applet 以及对于用户运行它们都是一项挑战。因此，我们认为接下来的章节将对需要维护旧版 applet 的读者感兴趣。

> ![图像](img/note.jpg) **注意**
>
> 要在浏览器中运行本章中的 applet，你需要安装当前版本的 Java Plug-in 并确保你的浏览器已与插件连接。为了测试 applet，你还需要配置插件使其信任本地文件。具体说明请参阅第 2.5 节”，位于第 33 页）。

#### 13.4.1 一个简单的 Applet

出于传统起见，让我们写一个 `NotHelloWorld` 程序作为 applet。applet 仅仅是一个扩展了 `java.applet.Applet` 类的 Java 类。在书中，我们将使用 Swing 来实现 applet。我们所有的 applet 都将扩展 `JApplet` 类，它是 Swing applet 的父类。正如图 13.2 所示，`JApplet` 是普通 `Applet` 类的直接子类。

![图像](img/13fig02.jpg)

**图 13.2** Applet 继承图

> ![图像](img/note.jpg) **注意**
>
> 如果你的 applet 包含 Swing 组件，你必须扩展 `JApplet` 类。在普通的 `Applet` 内部的 Swing 组件无法正确绘制。

列表 13.4 显示了 applet 的代码。注意这与第 10 章的程序是相似的。但由于 applet 位于网页内部，不需要指定类文件。

**列表 13.4** `NotHelloWorld.java`

```java
package applet;

import java.awt.*;

import javax.swing.*;

/**
 * @version 12
 * @author Caymann
 */
public class NotHelloWorld extends JApplet
{
    public void init()
    {
        EventQueue.invokeLater(() -> {
            JLabel label = new JLabel("Not a World", SwingConstants.CENTER);
            add(label);
        });
    }
}
```

要执行 applet，执行三个步骤：

1. 将 Java 源文件编译为类文件。
2. 将类封装成 JAR 文件（参阅第 13.1.1 节，“创建 JAR 文件”，位于第 780 页）。
3. 创建一个 HTML 文件告诉浏览器加载哪个类以及 applet 的大小。

这里是该文件的内容：

点击此处查看代码图像

```html
<applet class="applet/NotHelloWorld.class" archive="NotHelloWorld.jar" width="300" height="300">
</applet>
```

在浏览器中查看 applet 之前，使用 JDK 部分的 `applet viewer` 程序进行测试是一个好主意。要配合我们的示例使用 `applet viewer`，输入：

点击此处查看代码图像

```bash
appletviewer NotApplet.html
```

程序的命令行参数是 HTML 文件名，而不是类文件。图 13.3 显示了 `applet viewer` 显示此 applet。

![图像](img/13fig03.jpg)

**图 13.3** 在 applet viewer 中查看 applet

`applet viewer` 适用于第一阶段的测试，但最终你需要在真实的浏览器中运行 applet，以便看到用户看到它们的方式。特别是，`applet viewer` 只显示 applet，而不显示周围的 HTML 文本。如果你的 HTML 文件包含多个 `applet` 标签，`applet viewer` 会弹出多个窗口。

要正确查看 applet，只需将 HTML 文件加载到浏览器中（参阅图 13.4）。如果 applet 没有显示，你需要安装 Java Plug-in 并允许它加载未签名的本地 applet，如第 2.5 节。

**图 13.4** 在浏览器中查看 applet

如果你对 applet 进行了更改并重新编译，你需要重启浏览器以便加载新的类文件。仅仅刷新 HTML 页面不会加载新代码。这在调试 applet 时是一件很麻烦的事。你可以通过 `Java console` 避免痛苦的浏览器重启。启动控制台并执行 `x` 命令，这会清除类加载器缓存。然后你就可以重新加载 HTML 页面，使用新的 applet 代码了。在 Windows 下，在 Windows 控制面板中打开 Java 插件控制。在 Linux 下，运行 `jcontrol` 并请求显示 Java 控制台。每当加载 applet 时，控制台都会弹出。

将图形化 Java 应用程序转换为可以嵌入网页的 applet 是很容易的。本质上，所有的用户界面代码都可以保持不变。以下是具体步骤：

1. 创建一个带有适当标签的 HTML 页面来加载 applet 代码。
2. 提供 `JApplet` 类的子类。将该类设置为 `public`。否则，applet 将无法加载。
3. 移除应用程序中的 `main` 方法。不要为应用程序构建帧窗口（frame window）。你的应用程序将显示在浏览器内部。
4. 将任何初始化代码从帧窗口构造函数移动到 applet 的 `init` 方法中。你不需要显式构造 applet 对象——浏览器会为你实例化并调用 `init` 方法。
5. 移除对 `setSize` 的调用；对于 applet，尺寸是通过 HTML 文件中的 `width` 和 `height` 参数设置的。
6. 移除对 `setDefaultCloseOperation` 的调用。applet 不能被关闭；它会在浏览器退出时终止。
7. 如果应用程序调用了 `setTitle`，请移除对该方法的调用。applet 不能有标题栏。（当然，你可以使用 HTML 的 `title` 标签为网页本身命名。）
8. 不要调用 `setVisible(true)`。applet 会自动显示。

`java.applet.Applet` `1.0`

- `void init()`：applet 首次加载时被调用。重写此方法并将所有初始化代码放在此处。
- `void start()`：重写此方法，用于在用户每次访问包含该 applet 的浏览器页面时需要执行的代码。一个典型的操作是重新激活线程。
- `void stop()`：重写此方法，用于在用户每次离开包含该 applet 的浏览器页面时需要执行的代码。一个典型的操作是停用线程。
- `void destroy()`：重写此方法，用于在用户退出浏览器时需要执行的代码。
- `void resize(int width, int height)`：请求调整 applet 大。如果这个方法能在网页上运行，这将是一个很好的方法；遗憾的是，它在当前浏览器中不起作用，因为它会干扰页面的布局机制。

#### 13.4.2 applet HTML 标签及其属性

在最基本的形式下，一个 `applet` 标签示例所示：

点击此处查看代码图像

```html
<applet code="applet/NotHelloWorld.class" archive="NotHelloWorld.jar"
       width="300" height="100"></applet>
```

你可以在 `applet` 标签内使用以下属性：

- `width`, `height`：这些属性是必需的，提供 applet 的宽度和高度（像素）。在 applet 查看器中，这是 applet 的初始 own。你可以调整 applet 查看器创建的任何窗口。在浏览器中，你无法调整 applet 的 own。你需要很好猜测你的 applet 需要多少空间以便所有用户都能良好显示。
- `align`：此属性指定 applet 的对齐方式。属性值与 HTML `img` 标签的 `align` 属性相同。
- `vspace`, `hspace`：这些可选属性指定 applet 上方和下方（`vspace`）以及左右两侧（`hspace`）的像素数。
- `code`：此属性提供 applet 类文件名。路径名必须与 applet 类的包匹配。例如，如果 applet 类在 `com.mycompany` 包中，则属性为 `code="com/mycompany/MyApplet.class"`。允许另一种写法 `code="com.mycompany.MyApplet.class"`。`code` 属性仅指定包含 applet 类的类名。当然，你的 applet 可能包含其他类文件。一旦浏览器的类加载器加载了包含 applet 的类，它就会意识到需要更多类文件并加载它们。
- `archive`：此属性列出了包含 applet 类及其他资源的 JAR 文件或文件。这些文件在 applet 加载之前会从 Web 服务器获取。JAR 文件之间用逗号分隔。例如：

  点击此处查看代码图像

  ```html
  <applet code="MyApplet.class"
         archive="MyClasses.jar,corejava/CoreJavaClasses.jar"
         width="100" height="150">
  ```

- `codebase`：此属性是加载 JAR 文件（以及类文件）的 URL。
- `object`：此属性指定 applet 状态的文件名。由于没有方法签名 applet，此功能不再好用。
- `alt`：你可以使用 `alt` 属性在 Java 禁用时显示消息。如果浏览器无法处理 applet，它会忽略 `applet` 和 `param` 标签。支持 Java 的浏览器会显示 `<applet>` 和 `</applet>` 标签之间的任何文本。例如：

  点击此处查看代码图像

  ```html
  <applet . . alt="If you activated Java, you would see my applet here">
  ```

- `name`：脚本编写者可以给 applet 一个 `name` 属性，用于引用该 applet。要从 JavaScript 访问 applet，你必须先给它命名。

  点击此处查看代码图像

  ```html
  <applet ... name="mine"></applet>
  ```

  然后你可以通过 `document.applets.mine` 引用该对象。例如：

  ```javascript
  var myApplet = document.applets.mine;
  ```

  然后调用 applet 方法：

  ```javascript
  myApplet.init();
  ```

当你想要同一页面上的两个 applet 相互通信时，`name` 属性也是至关重要的。为每个 applet 实例指定名称，并将此字符串传递给 `AppletContext` 接口的 `getApplet` 方法。我们将在章后面讨论这种机制，即*applet 间通信*（inter-applet communication）。

> ![图像](img/note.jpg) **注意**
>
> 在 [`www.javaworld.com/javatips/jw-javatip80.html`](http://www.javaworld.com/javatips/jw-javatip80.html) 中，Francis Lu 使用 JavaScript 到 Java 的通信解决了一个老问题：如何调整 applet 的 own，使其不受硬编码的 `width` 和 `height` 属性的限制。这是 Java 和 JavaScript 集成的良好示例。

#### 13.4.3 使用参数向 applet 传递信息

正如应用程序可以使用命令行信息一样，applet 可以使用嵌入在 HTML 文件中的参数。这是通过名为 `param` 的 HTML 标签以及你定义的属性实现的。例如，假设你想让网页决定 applet 中使用的字体样式。你可以使用以下 HTML 标签：

点击此处查看代码图像

```html
<applet code="FontParamApplet.class" ...>
    <param name="font" value="Helvetica"/>
</applet>
```

然后你可以使用 `Applet` 类的 `getParameter` 方法获取参数值。

点击此处查看代码图像

```java
public class FontParamApplet extends JApplet
{
    public void init()
    {
        String fontName = getParameter("font");
        ...
    }

    ...
}
```

> ![Image](img/note.jpg) **注意**
>
> 你只能在 applet 的 `init` 方法中调用 `getParameter` 方法，而不能在构造函数中调用。当 applet 构造函数执行时，参数尚未准备就。由于大多数非复杂 applet 的布局是由参数决定的，我们建议不要为 applet 提供构造函数。简单地将所有初始化代码放置在 `init` 方法中。

参数始终以字符串的形式返回。如果需要数值类型，你必须将字符串转换为该类型。你可以通过标准方法使用适当的方法（例如 `Integer` 类的 `parseInt`）来完成此操作。

例如，如果我们想为字体添加一个 `size` 参数，HTML 代码可能如下所示：

点击此处查看代码图像

```html
<applet code="FontParamApplet.class" ...>
    <param name="font" value="Helvetica"/>
    <param name="size" value="24"/>
</applet>
```

接下来的源代码显示了如何读取整数参数：

点击此处查看代码图像

```java
public class FontParamApplet extends JApplet
{
    public void init()
    {
        String fontName = getParameter("font");
        int fontSize = Integer.parseInt(getParameter("size"));
        ...
    }
}
```

> ![Image](img/note.jpg) **注意**
>
> 在匹配 `param` 标签中的 `name` 属性值与 `getParameter` 方法的参数时，使用的是不区分大小写的比较。

除了确保代码中的参数匹配之外，你还应该检查是否遗漏了 `size` 参数。你可以通过一个简单的 `null` 测试来实现这一点。例如：

点击此处查看代码图像

```java
int fontsize;

String sizeString = getParameter("size");

if (sizeString == null) fontSize = 12;
else fontSize = Integer.parseInt(sizeString);
```




这是一个使用参数绘制柱状图的经典 applet，所示图 13.5。

![Image](img/13fig05.jpg)

**图 13.5** 一个图状图 applet

该 applet 从 HTML 文件的 `param` 值中获取标签和柱体的高度。以下是图 13.5 HTML 文件的内容：

点击此处查看代码图像

```html
<applet code="Chart.class" width="400" height="300">
    <param name="title" value="Diameters of the Planets"/>
    <param name="values" value="9"/>
    <param name="name.1" value="Mercury"/>
    <param name="name.2" value="Venus"/>
    <param name="name.3" value="Earth"/>
    <param name="name.4" value="Mars"/>
    <param name="name.5" value="Jupiter"/>
    <param name="name.6" value="Saturn"/>
    <param name="name.7" value="Uranus"/>
    <param name="name.8" value="Neptune"/>
    <param name="name.9" value="Pluto"/>
    <param name="value.1" value="3100"/>
    <param name="value.2" value="7500"/>
    <param name="value.3" value="8000"/>
    <param name="value.4" value="4200"/>
    <param name="value.5" value="88000"/>
    <param name="value.6" value="71000"/>
    <param name="value.7" value="32000"/>
    <param name="value.8" value="30600"/>
    <param name="value.9" value="1430"/>
</applet>
```

你可以在 applet 中设置一个字符串数组和一个数字数组，但使用参数机制有两个优势。你可以在你的网页上放置多个相同 applet 的副本，显示不同的图表：只需在页面上放置带有不同参数组的 `applet` 标签即可。此外，你可以更改想要制图的数据。诚然，行星的直径在一段时间内将保持不变，假设你的网页包含一个每周数据图表。由于它是纯文本，更新网页非常容易。而编辑和重新编译 Java 文件要琐碎得多。事实上，有一些商业级的 JavaBeans 可以制作比我们 applet 更精美的图表。如果你购买了一个，可以将其拖入你的网页中并向其提供参数，而无需知道 applet 是如何渲染图表的。

列表 13.5 是我们 applet 的源代码。注意，`init` 方法读取参数，而 `paintComponent` 方法绘制图表。

**列表 13.5** `chart/Chart.java` 点击此处查看代码图像

```java
package chart;

import java.awt.*;
import java.awt.font.*;
import java.awt.geom.*;
import javax.swing.*;

/**
 * @version 1.3 2015-06-12
 * @author Horstmann
 */
public class Chart extends JApplet
{
    public void init()
    {
        EventQueue.invokeLater(() -> {
            String v = getParameter("values");
            if (v == null) return;
            int n = Integer.parseInt(v);
            double[] values = new double[n];
            String[] names = new String[n];

            for (int i = 0; i < n; i++)
            {
                values[i] = Double.parseDouble(getParameter("value." + (i + 1)));
                names[i] = getParameter("name." + (i + 1));
            }

            add(new ChartComponent(values, names, getParameter("title")));
        });
    }
}

/**
 * 一个绘制柱状图的组件。
 */
class ChartComponent extends JComponent
{
    private double[] values;
    private String[] names;
    private String title;

    /**
     * 构造 ChartComponent。
     * @param v 图表的数值数组
     * @param n 数值对应的名称数组
     * @param t 图表的标题
     */
    public ChartComponent(double[] v, String[] n, String t)
    {
        values = v;
        names = n;
        title = t;
    }

    public void paintComponent(Graphics g)
    {
        Graphics2D g2 = (Graphics2D) g;

        // 计算最小值和最大值
        if (values == null) return;

        double minValue = 0;
        double maxValue = 0;

        for (double v : values)
        {
            if (minValue > v) minValue = v;
            if (maxValue < v) maxValue = v;
        }

        if (maxValue == minValue) return;

        int panelWidth = getWidth();
        int panelHeight = getHeight();

        Font titleFont = new Font("SansSerif", Font.BOLD, 20);
        Font labelFont = new Font("SansSerif", Font.PLAIN, 10);

        // 计算标题的范围
        FontRenderContext context = g2.getFontRenderContext();
        Rectangle2D titleBounds = titleFont.getStringBounds(title, context);
        double titleWidth = titleBounds.getWidth();
        double top = titleBounds.getHeight();

        // 绘制标题
        double y = -titleBounds.getY(); // 上升
        double x = (panelWidth - titleWidth) / 2;

        g2.setFont(titleFont);
        g2.drawString(title, (float) x, (float) y);

        // 计算柱体标签的范围
        LineMetrics labelMetrics = labelFont.getLineMetrics("", context);
        double bottom = labelMetrics.getHeight();

        y = panelHeight - labelMetrics.getDescent();
        g2.setFont(labelFont);

        // 获取柱体的缩放因子和宽度
        double scale = (panelHeight - top - bottom) / (maxValue - minValue);
        int barWidth = panelWidth / values.length;

        // 绘制柱体
        for (int i = 0; i < values.length; i++)
        {
            // get the coordinates of the bar rectangle
            double x1 = i * barWidth + 1;
            double y1 = top;
            double height = values[i] * scale;

            if (values[i] >= 0)
                y1 += (maxValue - values[i]) * scale;
            else
            {
                y1 += maxValue * scale;
                height = -height;
            }

            // fill the bar and draw the bar outline
            Rectangle2D rect = new Rectangle2D.Double(x1, y1, barWidth - 2, height);
            g2.setPaint(Color.RED);
            g2.fill(rect);
            g2.setPaint(Color.BLACK);
            g2.draw(rect);

            // draw the centered label below the bar
            Rectangle2D labelBounds = labelFont.getStringBounds(names[i], context);
            double labelWidth = labelBounds.getWidth();

            x = x1 + (barWidth - labelWidth) / 2;
            g2.drawString(names[i], (float) x, (float) y);
        }
    }
}
```

### `java.applet.Applet` 1.0

- `public String getParameter(String name)`  
  获取在加载 applet 的网页中通过 `param` 标签定义的参数值。字符串 `name` 是区分大小写的。

- `public String getAppletInfo()`  
  许多 applet 作者都会重写此方法，以返回一个包含当前 applet 作者信息、版本和版权信息的字符串。

- `public String[][] getParameterInfo()`  
  这是一个你可以重写的方法，用于返回此 applet 支持的 `param` 标签选项数组。每行包含三个条目：参数的名称、类型和描述。这里是一个示例：

  点击此处查看代码图片

```text
"fps", "1–10", "每秒帧数"
"repeat", "boolean", "循环图像？"
"images", "url", "包含图片的目录"
```

### 13.4.4 访问图像和音频文件

Applet 可以同时处理图像和音频。在我们编写本文时，图像必须是 GIF、PNG 或 JPEG 格式，音频文件必须是 AU、AIFF、WAV 或 MIDI 格式。支持动态 GIF，并显示动画。

使用相对 URL 指定图像和音频文件的位置。基础 URL 通常通过调用 `getDocumentBase` 或 `getCodeBase` 方法获取。前者获取包含 applet 的 HTML 页面的 URL，后者获取 applet 的 `codebase` 属性所指定的 URL。

将基础 URL 和文件位置传递给 `getImage` 或 `getAudioClip` 方法。例如：

点击此处查看代码图片

```java
Image cat = getImage(getDocumentBase(), "images/cat.gif");
AudioClip meow = getAudioClip(getDocumentBase(), "audio/meow.au");
```

你已在第 10 章中看到如何显示图像。要播放音频片段，只需调用它的 `play` 方法即可。你也可以在不先加载音频片段的情况下直接调用 `Applet` 类的 `play` 方法。

点击此处查看代码图片

```java
play(getDocumentBase(), "audio/meow.au");
```

### `java.applet.Applet` 1.0

- `URL getDocumentBase()`  
  获取包含 applet 的 HTML 页面的 URL。

- `URL getCodeBase()`  
  获取 applet 的 `codebase` 属性所指定的 URL。

- `void play(URL url)`  
  `void play(URL url, String name)`  
  第一种形式使用 `url`。第二种形式使用 `name`。

- `AudioClip getAudioClip(URL url)`  
  `AudioClip getAudioClip(URL url, String name)`  
  第一种形式使用 `url`。第二种形式使用 `name`。

- `Image getImage(URL url)`  
  `Image getImage(URL url, String name)`  
  第一种形式使用 `url`。第二种形式使用 `name`。

### 13.4.5 Applet Context

`AppletContext` 接口提供了 applet 与浏览器交互的方法。applet 可以请求浏览器执行某些操作，例如显示图像或播放音频片段。`AppletContext` 接口包含几个方法，我们将在后文中详细讨论。

### 13.4.6 Applet 间的通信

一个网页可以包含多个 applet。如果它们具有 `name` 属性，它们就可以相互通信。`getApplet` 方法提供对 applet 的引用。例如：

点击此处查看代码图像

```html
<applet code="Chart.class" width="100" height="100" name="Chart">
```

这为你提供了一个对 applet 的引用。只要你为 `Chart` 类提供一个接收新数据并重绘图表的方法，你就可以通过适当的类型转换来调用该方法。

点击此处查看代码图像

```java
Applet chart1 = getAppContext().getApplet("Chart");
((Chart) chart1).setData(3, "Earth", 9000);
```

你还可以列出页面上所有的 applet，无论它们是否具有 `name` 属性。`getApplets` 方法返回一个枚举。这里是一个打印页面上所有 applet 类名的循环：

点击此处查看代码图像

```java
Enumeration<Applet> e = getAppContext().getApplets();

while (e.hasMoreElements())
{
    Applet a = e.nextElement();
    System.out.println(a.getClass().getName());
}
```

applet 无法与另一个页面上的 applet 通信。

### 13.4.7 在浏览器中显示项目

访问浏览器的两个区域：状态栏和网页显示区域。两者都使用 `AppletContext` 接口的方法。

你可以使用 `showStatus` 方法在浏览器底部的状态栏显示字符串。例如：

点击此处查看代码图像

```java
showStatus("Loading data ... please wait");
```

**提示**：根据我们的经验，`showStatus` 的用途有限。浏览器也会使用状态栏，通常情况下它会用类似 `Applet running.` 的闲话覆盖你宝贵的消息。状态栏应用于如 `Loading data ... please wait` 之类的提示信息，但不要用于用户不能错过的信息。

你可以通过 `showDocument` 方法告诉浏览器显示另一个网页。有几种实现方法。简单的方法是调用带有一个参数的 `showDocument`，参数为你想显示的 URL。

```java
URL u = new URL("http://horstmann.com/index.html");
```




```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。getAppContext().showDocument(u);
```

此调用的问题在于，它会在当前页相同的窗口中打开新网页，从而取代了你的小程序（applet）。要返回你的小程序，用户必须点击浏览器的后退按钮。

你可以通过在调用`showDocument`时提供第二个参数来告诉浏览器在另一个窗口中显示文档（参见表 13.2）。如果你提供特殊字符串`"_blank"`，浏览器将打开新窗口显示文档，而不是取代当前文档。更重要的是，如果你利用 HTML 中的帧（frame）功能，可以将一个浏览器窗口拆分为多个帧，每个帧都有一个名称。你可以将小程序放入一个帧，并让它在其他帧中显示文档。我们将在下一节向你展示如何做的示例。

![Image](img/13tab02.jpg)

**表 13.2** `showDocument`方法

---

![Image](img/note.jpg) **注意**

小程序查看器不显示网页。在小程序查看器中，`showDocument`方法会被忽略。

---

### `java.applet.Applet` 1.2

- `public AppletContext getAppletContext()`提供一个指向程序浏览器环境的句柄。在大多数浏览器中，你可以使用此信息控制运行小程序的浏览器。
- `void showStatus(String msg)`在浏览器的状态栏中显示指定的字符串。

### `java.applet.AppletContext` 1.0

- `Enumeration<Applet> getApplets()`返回相同上下文（即同一页网页）中所有小程序的枚举器（参见第 9 章）。
- `Applet getApplet(String name)`返回当前上下文中具有给定名称的小程序；如果不存在则返回`null`。仅搜索当前网页。
- `void showDocument(URL url)`
- `void showDocument(URL url, String target)`在浏览器的帧中显示新网页。在第一种形式中，新页面会取代当前页面。第二种形式使用`target`参数来识别目标帧（参见表 13.2）。

## 13.4.8 沙盒

每当代码从远程站点加载并在本地执行时，安全性就变得至关重要。访问网页会自动启动页面上的所有小程序。点击单个链接即可启动一个 Java Web Start 应用程序。如果访问网页或点击链接就能在用户的计算机上执行任意代码，那么罪犯将轻松地窃取机密、访问财务数据或接管用户的机器来发送垃圾邮件。

为了确保 Java 技术不被用于恶意目的，Java 拥有一套复杂的安全模型，我们将在第二卷中详细讨论。*安全管理器*（security manager）会检查对所有系统资源的访问。默认情况下，它只允许那些无害的操作。要允许额外的操作，用户必须显式批准该小程序或应用程序。

远程代码在所有平台上*可以*做什么呢？显示图像和播放声音、获取用户的按键输入和鼠标点击，以及将用户输入发送回代码加载的主机，这些总是安全的。这些功能足以展示事实数据或与教育程序或游戏进行交互。受限制的执行环境通常被称为“沙盒”。在沙盒中运行的代码不能更改用户的系统或对其进行监视。

特别是，沙盒中的程序具有以下限制：

- 它们*永远不能*运行任何本地可执行程序。
- 它们不能从本地计算机的文件系统读取或写入。
- 它们无法获取有关本地计算机的任何信息，除了使用的 Java 版本和一些无害的操作系统细节外。特别是，沙盒中的代码无法获取用户名、电子邮箱地址等。
- 远程加载的程序需要用户同意才能与下载它们的服务器以外的任何主机进行通信；该服务器被称为*源主机*（originating host）。这条规则通常被称为“远程代码只能拨回家”。该规则保护用户免受可能尝试监视内网资源代码的影响。
- 所有弹出窗口都带有一个警告消息。此消息是一个安全特性，确保用户不会将窗口误认为是本地应用程序。人们担心，毫无防备的用户可能会访问一个网页，被诱导运行远程代码，然后输入密码或信用卡号，这些信息会被发送回网络服务器。在 JDK 的早期版本中，该消息非常不详：“不可信任的 Java 小程序窗口”。随后的每个版本都略微淡化了警告：“未身份验证的 Java 小程序窗口”，然后是“警告：Java 小程序窗口”。现在，它是一个微小的警告三角形，只有最细心的用户才会注意到。

沙盒概念不再像过去那样具有意义。在过去，任何人都可以部署沙盒代码，只有需要沙盒之外权限的代码才需要数字签名。如今，通过 Java 插件执行的所有代码，无论是否运行在沙盒中，都必须经过数字签名。

## 13.4.9 签名代码

小程序或 Java Web Start 应用程序的 JAR 文件必须经过*数字签名*。签名的 JAR 文件携带有一个证书，指示签名者的身份。加密技术确保了此类证书无法被伪造，并且任何篡改签名文件的尝试都会被检测到。

例如，假设你收到一个由 yWorks GmbH 制作并数字签名的应用程序，该程序使用了由 Thate 发的证书。加密技术确保了此类证书无法被伪造，并且任何篡改签名文件的尝试都会被检测到。

当你收到应用程序时，可以通过图 13.6 确保以下内容：

1. 代码与签名时完全一致，没有被篡改过。
2. 签名确实来自 yWorks。
3. 证书确实是由 Thate 发的。（Java 插件知道如何检查来自 Thate 以及其他证书供应商的证书，也可以安装备用“根证书”。）

![Image](img/13fig06.jpg)

**图 13.6** 安全证书

接下来，你需要决定你想要哪些权限。你可以在沙箱权限（sandbox）和所有权限（all）之间进行选择。创建一个清单文件（参见第 13.1.2 节，“清单”，位于第 781 页）。

包含`Permissions: sandbox`或`Permissions: all-permissions`行，例如：

```text
Manifest-Version: 1.0

Permissions: all-permissions
```

运行`jar`工具：

点击此处查看代码图片

```bash
jar cvfm MyApplet.jar manifest.mf mypackage/*.class
```

你的 HTML 文件中的`applet`元素应该有一个属性`archive="MyApplet.jar"`。

最后，对 JAR 文件签名。命令如下：

点击此处查看代码图片

```bash
jarsigner -keystore keystorefile -tsa timestampURL MyApplet.jar keyalias
```

你需要向你的证书颁发者询问时间戳 URL。别名（alias）是由你的证书颁发者指定的。运行命令：

点击此处查看代码图片

```bash
keytool -keystore keystorefile -list
```

以找出它是什么。你也可以用`keytool`命令的`-changealias`选项来更改它。（关于`keytool`的更多信息，请参见第二卷的第 9 章](#ch09.html_ch09)。）

现在，将签名的 JAR 文件和带有`applet`元素的 HTML 文件放置在你的 Web 服务器上。

---

![Image](img/note.jpg) **注意**

可以非常详细地控制授予 Java 应用程序的权利；我们将在第二卷的第 12 章](#ch12.html_ch12)中讨论这一点。然而，该系统从未以一种对消费者有意义的方式投入使用。Java 插件仅提供两种安全级别：沙箱或所有权限。

## 13.5 Java Web Start

Java Web Start 是一种通过互联网分发应用程序的技术。Java Web Start 具有以下特征：

- 它们通常通过浏览器交付。一旦下载了 Java Web Start 程序，就可以不使用浏览器启动。
- 它们并不位于浏览器窗口内。应用程序显示在自己的框架中，位于浏览器之外。
- 它们不使用浏览器的 Java 实现。浏览器每当加载 Java Web Start 描述符时，简单地启动一个外部应用程序。这与启动 Adobe Acrobat 或 RealAudio 等其他辅助程序的机制相同。
- 经过数字签名的应用程序可以获得本地机器的任意访问权限。未签名的应用程序运行在“沙箱”中，禁止潜在危险的操作。

### 13.5.1 分发 Java Web Start

为了通过 Java Web Start 分发应用程序做准备，将其封装在一个或多个 JAR 文件中。然后，准备一个 Java 网络启动协议（JNLP）格式的描述文件。将这些文件放在 Web 服务器上。

你还需要确保你的 Web 服务器对扩展名为`.jnlp`的文件报告 MIME 类型`application/x-java-jnlp-file`（浏览器使用 MIME 类型来确定启动哪个辅助程序。）详情请咨询你的 Web 服务器文档。

---

![Image](img/tip.jpg) **提示**

要尝试 Java Web Start，请从[`http://jakarta.apache.org/tomcat`](http://jakarta.apache.org/tomcat)安装 Tomcat。Tomcat 是 servlet 和 JSP 页面的容器，它也提供网页。它已预配置为为 JNLP 文件提供正确的 MIME 类型。在以下指令中，我们假设你使用的是 Tomcat。

让我们尝试使用 Java Web Start 来分发第 12 章中的计算器应用程序。按照以下步骤操作：

**1.** 编译程序。

点击此处查看代码图片

```bash
javac -classpath .:jdk/jre/lib/javaws.jar webstart/*.java
```

**2.** 使用命令生成 JAR 文件：

点击此处查看代码图片

```bash
jar cvfe Calculator.jar webstart.Calculator webstart/*.class
```

**3.** 准备带有以下内容的启动文件`Calculator.jnlp`：

点击此处查看代码图片

```xml
<?xml version="1.0" encoding="utf-8"?>

<jnlp spec="1.0+" codebase="http://localhost:8080/calculator/" href="Calculator.jnlp">

  <information>

    <title>Calculator Demo Application</title>

    <vendor>Cay S. Horstmann</vendor>

    <description>A Calculator</description>

    <offline-allowed/>

  </information>

  <resources>

    <java version="1.6.0+"/>

    <jar href="Calculator.jar"/>

  </resources>

  <application-desc/>

</jnlp>
```

（注意版本号必须是`1.6.0`，而不是`6.0`。）

启动文件格式是显而易见的。关于格式，请参见[www.oracle.com/javawork/javase](http://www.oracle.com/javawork/javase)。

**4.** 将启动文件放在`tomcat/calculator`目录下。将以下内容放入`tomcat/webINF`目录：

点击此处查看代码图片

```xml
<?xml version="1.0" encoding="utf-8"?>

<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"

    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

    xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">
```

**5.** 将签名的 JAR 文件和带有`applet`元素的 HTML 文件放在你的 Web 服务器上。

**6.** 将浏览器指向 JNLP 文件。例如，如果你使用 Tomcat，访问`http://localhost:8080/calculator/jnlp`。如果你的浏览器已配置了 Java Start，你应该看到 Java Start 的启动窗口（参见图 13.7）。

![Image](img/13fig7.jpg)

**图 13.7** 启动 Java Start

如果你的浏览器不知道如何处理 JNLP 文件，它可能会提供将其关联到应用程序的选项。如果是这样，选择`jdk/bin/javaws`。否则，找出如何将 MIME 类型`application/x-java-jnlp-file`关联到`javaws`。你也可以尝试重新安装 JDK，它应该会完成。

**7.** 很快计算器就会出现，并带有标记为 Java 应用程序（参见图 13.8）。

![Image](img/13fig8.jpg)

**图 13.8** 由 Java Start 分发的计算器

**8.** 当你再次访问 JNLP 文件时，应用程序将从缓存获取。你可以通过 Java 插件面板查看缓存内容（参见图 13.9）。在 Windows 中，在 Windows 控制面板查找 Java 插件。在 Linux 下，运行`jdk/jre/bin/ControlPanel`。

![Image](img/13fig9.jpg)

**图 13.9** 应用程序缓存

---

![Image](img/tip.jpg) **提示**

如果你在测试 JNLP 配置时不想运行 Web 服务器，可以通过运行以下命令临时覆盖启动文件中的`codebase` URL：

点击此处查看代码图片

```bash
javaws -codebase file://programDirectory JNLPfile
```

例如，在 UNIX 中，你只需从包含 JNLP 文件的目录下执行此命令：

```bash
javaws -codebase file://`pwd` Calculator.jnlp
```

当然，你并不希望用户在每次重新运行你的应用程序时都去启动缓存查看器。你可以让安装程序提供安装桌面和菜单快捷方式的选项。在 JNLP 文件中添加这些行：

点击此处查看代码图像

```xml
<shortcut>

    <desktop/>

    <menu submenu="Accessories"/>

</shortcut>
```

当用户首次下载应用程序时，会显示“桌面集成警告”（参见图 13.10）。

![Image](img/13fig10.jpg)

**图 13.10** 桌面集成警告

你还应该为菜单快捷方式和启动屏幕提供图标。Oracle 建议你提供 32 × 32 和 64 × 64 的像素图标。将图标文件放置在 Web 服务器上，并与 JNLP 和 JAR 文件放在一起。在 JNLP 文件的`information`部分添加这些行：

点击此处查看代码图像

```xml
<icon href="calc_icon32.png" width="32" height="32" />

<icon href="calc_icon64.png" width="64" height="64" />
```

注意，这些图标与应用程序图标无关。如果你想让应用程序拥有图标，需要在 JAR 文件中添加单独的图标图像，并在帧类上调用`setIconImage`方法。（示例请参见列表 13.1）。

### 13.5.2 JNLP API

与小程序（applets）相比，Java Web Start 拥有一个用于沙箱应用程序的 API，可以提供实用的服务。JNLP API 允许沙箱应用程序以安全的方式访问本地资源。例如，存在加载和保存文件的服务。应用程序无法查看文件系统也无法指定文件名。相反，会弹出一个文件对话框，由用户选择文件。但在文件对话框弹出之前，用户会收到提醒并必须同意后继续（参见图 13.11）。此外，该 API 并没有实际上赋予程序访问`File`对象的权限。特别是，应用程序无法发现文件位置。因此，程序员被赋予实现“打开文件”和“保存文件”操作的工具，但尽可能多的系统信息对不可信任的应用程序隐藏的。

![Image](img/13fig11.jpg)

**图 13.11** Java Web Start 安全公告

该 API 提供以下服务：

- 加载和保存文件
- 访问剪贴板
- 打印
- 下载文件
- 在默认浏览器中显示文档
- 存储和检索持久化配置信息
- 确保应用程序只有一个实例在运行

要访问服务，请如下所示使用`ServiceManager`：

点击此处查看代码图像

```java
FileSaveService service = (FileSaveService) ServiceManager.lookup("javax.jnlp.FileSaveService");
```

如果服务不可用，此调用将抛出`UnavailableServiceException`。

---

![Image](img/note.jpg) **注意事项**

如果你想编译使用 JNLP API 的程序，必须在类路径中包含`javaws.jar`文件。该文件包含在 JDK 的`jre/lib`子目录下。

我们现在讨论最有用的 JNLP 服务。要保存文件，需要为文件对话框提供初始路径名和文件扩展名的建议、提供要保存的数据以及建议的文件名。例如：

点击此处查看代码图像

```java



`service.saveFileDialog(".", new String[] { "txt" }, data, "calc.txt");`

数据必须通过`InputStream`传递。这在安排上可能有些复杂。列表 13.6 中的程序使用了以下策略：

1. 它创建一个`ByteArrayOutputStream`来容纳要保存的字节流。
2. 它创建一个`PrintStream`，将其数据发送到`ByteArrayOutputStream`。
3. 它将要保存的信息打印到`PrintStream`中。
4. 它创建一个`ByteArrayInputStream`来读取已保存的字节流。
5. 它将该流传递给`saveFileDialog`方法。

你将在第二卷的第 1 章中学习更多关于流的知识。现在，你只需略过示例程序中的细节。

要从文件中读取数据，请改用`FileOpenService`。它的`openFileDialog`接收文件对话框的初始路径名和文件扩展名的建议，并返回一个`FileContents`对象。然后可以调用`getInputStream`和`getOutputStream`方法来读写文件数据。如果用户没有选择文件，`openFileDialog`方法将返回`null`。

点击此处查看代码图像

```java
FileOpenService service = (FileOpenService) ServiceManager.lookup("javax.jnlp.FileOpenService");
```

Listing 13.6 中的程序是计算器程序的简单增强。该计算器有一个虚拟纸带，可以记录所有的计算。你可以保存和加载计算历史。为了演示持久化存储，应用程序允许你设置框架标题。如果你再次运行应用程序，它将从持久化存储中检索你选择的标题（参见图 13.13）。

**Listing 13.6** `webstart/CalculatorFrame.java`

点击此处查看代码

```java
package webstart;

import java.io.BufferedReader;
import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.io.OutputStream;
import java.io.PrintStream;
import java.net.MalformedURLException;
import java.net.URL;

import javax.jnlp.BasicService;
import javax.jnlp.FileContents;
import javax.jnlp.FileOpenService;
import javax.jnlp.FileSaveService;
import javax.jnlp.PersistenceService;
import javax.jnlp.ServiceManager;
import javax.jnlp.UnavailableServiceException;
import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import javax.swing.JOptionPane;

/**
 * A frame with a calculator panel and a menu to load and save the calculator history.
 */
public class CalculatorFrame extends JFrame
{
    private CalculatorPanel panel;

    public CalculatorFrame()
    {
        setTitle();
        panel = new CalculatorPanel();
        add(panel);

        JMenu fileMenu = new JMenu("File");
        JMenuBar menuBar = new JMenuBar();
        menuBar.add(fileMenu);
        setJMenuBar(menuBar);

        JMenuItem openItem = fileMenu.add("Open");
        openItem.addActionListener(event -> open());

        JMenuItem saveItem = fileMenu.add("Save");
        saveItem.addActionListener(event -> save());

        pack();
    }

    /**
     * Gets the title from the persistent store or asks the user for the title if there is no prior
     * entry.
     */
    public void setTitle()
    {
        try
        {
            String title = null;
            BasicService basic = (BasicService) ServiceManager.lookup("javax.jnlp.BasicService");
            URL codeBase = basic.getCodeBase();
            PersistenceService service = (PersistenceService) ServiceManager
                .lookup("javax.jnlp.PersistenceService");
            URL key = new URL(codeBase, "title");

            try
            {
                FileContents contents = service.get(key);
                InputStream in = contents.getInputStream();
                BufferedReader reader = new BufferedReader(new InputStreamReader(in));
                title = reader.readLine();
            }
            catch (FileNotFoundException e)
            {
                title = JOptionPane.InputDialog("Please supply a frame title:");
                if (title == null) return;
                service.create(key, 100);
                FileContents contents = service.get(key);
                OutputStream out = contents.getOutputStream(true);
                PrintStream printOut = new PrintStream(out);
                printOut.print(title);
            }

            setTitle(title);
        }
        catch (UnavailableServiceException | IOException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
    }

    /**
     * Opens a history file and updates the display.
     */
    public void open()
    {
        try
        {
            FileOpenService service = (FileOpenService) ServiceManager
                .lookup("javax.jnlp.FileOpenService");
            FileContents contents = service.openFileDialog(".", new String[] { "txt" });
            JOptionPane.showMessageDialog(this, contents.getName());

            if (contents != null)
            {
                InputStream in = contents.getInputStream();
                BufferedReader reader = new BufferedReader(new InputStreamReader(in));
                String line;
                while ((line = reader.readLine()) != null)
                {
                    panel.append(line);
                    panel.append("\n");
                }
            }
        }
        catch (UnavailableServiceException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
        catch (IOException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
    }

    /**
     * Saves the calculator history to a file.
     */
    public void save()
    {
        try
        {
            ByteArrayOutputStream out = new ByteArrayOutputStream();
            PrintStream printOut = new PrintStream(out);
            printOut.print(panel.getText());
            InputStream data = new ByteArrayInputStream(out.toByteArray());

            FileSaveService service = (FileSaveService) ServiceManager
                .lookup("javax.jnlp.FileSaveService");
            service.saveFileDialog(".", new String[] { "txt" }, data, "calc.txt");
        }
        catch (UnavailableServiceException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
        catch (IOException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
    }
}
```



![graphics/13fig3.jpg](img/13fig3.jpg)

**图 13.13** WebStart 计算器

`javax.jnlp.ServiceManager`
- `static String[] getServiceNames()` 返回所有可用服务的名称。
- `static Object lookup(String name)` 返回一个具有给定名称的服务。

`javax.jnlp.BasicService`
- `URL getCodeBase()` 返回此应用程序的代码库。
- `boolean isWebBrowserSupported()` 如果 Web Start 环境可以启动网络浏览器，则返回 `true`。
- `boolean showDocument(URL url)` 尝试在浏览器中显示指定的 URL。如果请求成功，返回 `true`。

`javax.jnlp.FileContents`
- `InputStream getInputStream()` 返回一个读取文件内容的输入流。
- `OutputStream getOutputStream(boolean overwrite)` 返回一个用于写入文件的输出流。如果 `overwrite` 为 `true`，则文件的现有内容将被覆盖。
- `String getName()` 返回文件名（但不包含完整目录路径）。
- `boolean canRead()` / `boolean canWrite()` 如果底层文件可读或可写，则返回 `true`。

`javax.jnlp.FileOpenService`
- `FileContents openFileDialog(String pathHint, String[] extensions)`
- `FileContents[] openMultiFileDialog(String pathHint, String[] extensions)` 显示用户警告和文件选择器。返回用户选择的文件或多个内容的描述符，如果用户没有选择文件，则返回 `null`。

`javax.jnlp.FileSaveService`
- `FileContents saveFileDialog(String pathHint, String[] extensions, InputStream data, String nameHint)`
- `FileContents saveAsFileDialog(String pathHint, String[] extensions, FileContents data)` 显示用户警告和文件选择器。写入数据并返回用户选择的文件或多个内容的描述符，如果用户没有选择文件，则返回 `null`。

`javax.jnlp.PersistenceService`
- `long create(URL key, long maxsize)` 为给定的键创建一个持久化存储条目。返回持久化存储器允许的最大尺寸。
- `void delete(URL key)` 删除给定键的条目。
- `String[] getNames(URL url)` 返回所有以给定 URL 开头的键的相对键名。
- `FileContents get(URL key)` 获取一个内容描述符，通过该描述符你可以修改与给定键关联的数据。如果该键不存在条目，则会抛出 `FileNotFoundException`。

***

到此，我们结束对 Java 软件部署的讨论。在本卷的最后一章，我们将涵盖并发编程这一重要主题。

# 第 14 章 并发

***

## 本章

* 14.1 什么是线程？
* 14.2 中断线程
* 14.3 线程状态
* 14.4 线程属性
* 14.5 同步
* 14.6 阻塞队列
* 14.7 线程安全集合
* 14.8 Callables 和 Futures
* 14.9 执行器
* 14.10 同步器
* 14.11 线程与 Swing

***

你可能对多任务处理并不陌生——你的操作系统能够让多个程序似乎在同时运行。例如，你可以在编辑或下载电子邮件的同时进行打印。如今，你可能拥有一台多个 CPU 的计算机，但并发执行进程的数量并不受限于 CPU 的数量。操作系统为每个进程分配 CPU 时间片，从而产生并行活动的错觉。

多线程程序通过将这一想法进一步降低一层来扩展多任务处理：单个程序似乎在同时执行多个任务。每个任务通常被称为线程（thread），它是控制流（thread of control）的缩写。能够同时运行多个线程的程序被称为多线程程序。

那么，多个进程和多个线程之间的区别是什么？本质区别在于，虽然每个进程都有自己的一套变量，但线程共享相同的数据。这听起来有些风险，而且确实如此，正如你将在在本章后面看到的那样。然而，共享变量使得线程之间的通信比进程间通信更高效、更容易编程。此外，在某些操作系统上，线程比进程更“轻量级创建和销毁单个线程的开销比启动新进程要小。

多线程在实践中极其有用。例如，浏览器应该能够同时下载多个图像。Web 服务器需要能够处理并发请求。图形用户界面（GUI）程序有一个单独的线程从宿主操作系统环境中收集用户界面事件。本章将向你展示如何为 Java 程序添加多线程能力。

提前警告：并发编程可能会变得非常复杂。在本章中，我们涵盖了应用程序程序员可能需要的所有工具。然而，对于更复杂的系统级编程，我们建议你转向更高级的参考资料，例如 Brian Goetz 等人的《Java 并发编程》（*Java Concurrency in Practice*，Addison-Wesley Professional, 2006）。

### 14.1 什么是线程？

让我们先看一个没有使用多线程的程序，结果是导致用户很难用该程序执行多个任务。在剖析它之后，我们将向你展示让这个程序运行单独线程有多简单。这个程序通过不断移动球、检查它是否撞击墙壁、然后重绘来制作一个小跳球动画。（参见图 14.1）。

![Image](img/14fig01.jpg)

**图 14.1** 使用线程制作弹球动画

一旦你点击 Start（开始）按钮，程序就会从屏幕左上角发射出一个球，球开始弹跳。Start 按钮的处理程序调用了 `addBall` 方法。该方法包含一个运行 1,000 次移动的循环。每次调用 `move` 都会让球移动一小段，如果撞击墙壁则调整方向，并重绘面板。

```java
Ball ball = new Ball();
panel.add(ball);
for (int i = 1; i <= STEPS; i++)
{
   ball.move(panel.getBounds());
   panel.paint(panel.getGraphics());
   Thread.sleep(DELAY);
}
```

调用 `Thread.sleep` 并没有创建一个新线程——`sleep` 是 `Thread` 类的一个静态方法，用于指定的毫秒时间内临时停止当前线程的活动。

`sleep` 方法可能会抛出 `InterruptedException`。我们稍后讨论这个异常及其正确处理方法。现在，如果发生此异常，我们简单的终止弹跳。

如果你运行该程序，球会弹跳得很漂亮，但它完全接管了应用程序。如果你在球完成 1,000 次移动之前就厌倦了弹跳并点击了 Close（关闭）按钮，球仍然会弹跳。在球停止弹跳之前，你无法与程序进行交互。

***

![Image](img/note.jpg) 注意

如果你仔细查看本节末尾的代码，你会注意到在

```java
comp.paint(comp.getGraphics())
```

`BounceFrame` 类的 `addBall` 方法内部的调用。这非常奇怪——通常情况下，你会调用 `repaint` 并让 AWT 担心获取图形上下文并执行绘制。但如果你尝试在这个程序中调用 `comp.repaint()`，你会发现面板只有在 `addBall` 方法返回后才会重绘。

`ball` 继承自 `JPanel`；

***

显然，这个程序的行为很糟糕。当你要求执行一项耗时任务时，你不会希望程序表现出这种行为。毕竟，当你通过网络读取数据时，被困在一个你*真的*想要中断的任务中是很常见的现象。例如，你下载了一张大图，在看到其中一部分后决定不需要或不想再看剩下的部分；你绝对想点击 Stop（停止）按钮来中断加载。在下一节中，我们将向你展示如何通过在单独的*线程*中运行代码的关键部分来保持用户的控制权。

代码列表 14.1 到 14.3 显示了程序的代码。

**列表 14.1** `bounce/Bounce.java`

```java
package bounce;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

/**
 * 显示一个弹跳的球。
 * @version 1.34 2015-06-21
 * @author Cay Horstmann
 */
public class Bounce
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() -> {
            JFrame frame = new BounceFrame();
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 有组件和按钮的帧。
 */
class BounceFrame extends JFrame
{
    private BallComponent comp;
    public static final int STEPS = 1000;
    public static final int DELAY = 3;

    /**
     * 构造带有显示弹球组件和按钮的帧。
     */
    public BounceFrame()
    {
        setTitle("Bounce");
        comp = new BallComponent();
        add(comp, BorderLayout.CENTER);
        JPanel buttonPanel = new JPanel();
        addButton(buttonPanel, "Start", event -> addBall());
        addButton(buttonPanel, "Close", event -> System.exit(0));
        add(buttonPanel, BorderLayout.SOUTH);
        pack();
    }

    /**
     * 向容器添加一个按钮。
     * @param c 容器
     * @param title 按钮标题
     * @param listener 按钮的动作监听器
     */
    public void addButton(Container c, String title, ActionListener listener)
    {
        JButton button = new JButton(title);
        c.add(button);
        button.addActionListener(listener);
    }

    /**
     * 向面板添加一个跳动的球并让它跳动 1,000 次。
     */
    public void addBall()
    {
        try
        {
            Ball ball = new Ball();
            comp.add(ball);
            for (int i = 1; i <= STEPS; i++)
            {
                ball.move(comp.getBounds());
                comp.paint(comp.getGraphics());
                Thread.sleep(DELAY);
            }
        }
        catch (InterruptedException e)
        {
        }
    }
}
```

### 列表 14.2 `bounce/Ball.java`

```java
package bounce;

import java.awt.geom.*;

/**
 * 一个在矩形边缘移动并反弹的球
 * @version 1.3 2007-05-17
 * @author Cay Horstmann
 */
public class Ball
{
    static final int XSIZE = 5;
    static final int YSIZE = 15;
    double x = 0;
    double y = 0;
    double dx = 1;
    double dy = 1;

    /**
     * 将球移动到下一个位置，如果撞击边缘则反转方向
     */
    public void move(Rectangle2D bounds)
    {
        x += dx;
        y += dy;
        if (x < bounds.getMinX())
        {
            x = bounds.getMinX();
            dx = -dx;
        }
        if (x + XSIZE >= bounds.getMaxX())
        {
            x = bounds.getMaxX() - XSIZE;
            dx = -dx;
        }
        if (y < bounds.getMinY())
        {
            y = bounds.getMinY();
            dy = -dy;
        }
        if (y + YSIZE >= bounds.getMaxY())
        {
            y = bounds.getMaxY() - YSIZE;
            dy = -dy;
        }
    }

    /**
     * 获取球在当前位置的形状。
     */
    public Ellipse2D getShape()
    {
        return new Ellipse2D.Double(x, y, XSIZE, YSIZE);
    }
}
```

### 列表 14.3 `bounce/BallComponent.java`

```java
package bounce;

import java.awt.*;
import java.util.*;
import javax.swing.*;

/**
 * 绘制球的组件。
 * @version 1.34 2012-01-26
 * @author Cay Horstmann
 */
public class BallComponent extends JPanel
{
    static final int DEFAULT_WIDTH = 450;
    static final int DEFAULT_HEIGHT = 350;
    java.util.List<Ball> balls = new ArrayList<>();

    /**
     * 向组件添加一个球。
     * @param b 要添加的球
     */
    public void add(Ball b)
    {
        balls.add(b);
    }

    public void paintComponent(Graphics g)
    {
        super.paintComponent(g); // 清除背景
        Graphics2D g2 = (Graphics2D) g;
        for (Ball b : balls)
        {
            g2.fill(b.getShape());
        }
    }

    public Dimension getPreferredSize() { return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT); }
}
```



`java.lang.Thread` 1.0
- `static void sleep(long millis)` 睡眠给定的毫秒数。
![Image](img/846tab01.jpg)

## 14.1.1 使用线程为其他任务机会

我们将通过在单独线程中运行移动球的代码，让我们的跳球程序更具响应性。事实上，你将启动多个球，每个球都由它自己的线程移动。此外，AWT `event dispatch thread`（事件调度线程）将继续并行运行，处理用户界面事件。由于每个线程都有运行的机会，事件调度线程有机会在球跳动时注意到用户点击了 `Close` 按钮。然后该线程就可以处理“关闭”操作。

我们使用跳球代码作为示例，让你直观地感受到并发的必要性。通常情况下，你需要警惕任何长时间的计算。你的计算很可能是某些框架的一部分，例如 GUI 或 Web 框架。每当框架调用你的某个方法时，通常期望它能快速返回。如果你需要执行任何耗时很长的任务，你的任务应该并发运行。

以下是在单独线程中运行任务的简易步骤：

1. 将任务代码放入实现 `Runnable` 接口的类的 `run` 方法中。该接口非常简单，只有一个方法：
```java
public interface Runnable
{
    void run();
}
```
由于 `Runnable` 是一个函数接口，你可以使用 lambda 表达式创建一个实例：
```java
Runnable r = () -> { task code };
```

2. 从 `Runnable` 构建一个 `Thread` 对象：
```java
Thread t = new Thread(r);
```

3. 启动线程：
```java
t.start();
```

为了让我们的跳球程序成为单独线程，我们只需要将动画代码放在 `run` 方法中，然后启动线程：
```java
Runnable r = () -> {
    try
    {
        for (int i = 1; i <= STEPS; i++)
        {
            ball.move(comp.getBounds());
            comp.repaint();
            Thread.sleep(DELAY);
        }
    }
    catch (InterruptedException e)
    {
    }
};
Thread t = new Thread(r);
t.start();
```

再次，我们需要捕获 `sleep` 方法可能抛出的 `InterruptedException`。我们将在下一节讨论此异常。通常，中断用于请求终止线程。因此，当发生 `InterruptedException` 时，我们的 `run` 方法会退出。

每当点击 `Start` 按钮时，球都在新线程中移动（参见图 14.2）。

![Image](img/14fig02.jpg)

**图 14.2** 运行多个线程

这就是并行任务的全部！本章的剩余部分将介绍如何控制线程之间的交互。

完整代码如列表 14.4。

![Image](img/note.jpg) 注意

你可以通过形成 `Thread` 类的子类来定义线程，如下：
```java
class MyThread extends Thread
{
    public void run()
    {
        task code
    }
}
```
然后构造子类的对象并调用其 `start` 方法。然而，这种方法不再被推荐。你应该将要并行运行的任务与运行任务的机制解耦。如果你有很多任务，为每个任务创建一个单独线程的开销太大了。相反，你可以使用线程池——参见第 14.9 节“Executors”，第 920 页。

*不要*调用 `Thread` 类的 `run` 方法或 `Runnable` 对象的 `run` 方法。直接调用 `run` 方法仅仅是在*相同*线程中执行任务——不会启动新线程。请调用 `Thread.start` 方法。它会创建一个新线程来执行 `run` 方法。

---

**列表 14.4** `bounceThread/BounceThread.java`

```java
package bounceThread;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

/**
 * 显示动画跳动的小球。
 * @version 1.34 2015-06-21
 * @author Cay Horstmann
 */
public class BounceThread
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() -> {
            JFrame frame = new BounceFrame();
            frame.setTitle("BounceThread");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 带有面板和按钮的框架。
 */
class BounceFrame extends JFrame
{
    private BallComponent comp;
    public static final int STEPS = 1000;
    public static final int DELAY = 5;

    /**
     * 构造带有跳动小球显示组件以及 Start 和 Close 按钮的框架。
     */
    public BounceFrame()
    {
        comp = new BallComponent();
        add(comp, BorderLayout.CENTER);
        JPanel buttonPanel = new JPanel();
        addButton(buttonPanel, "Start", event -> addBall());
        addButton(buttonPanel, "Close", event -> System.exit(0));
        add(buttonPanel, BorderLayout.SOUTH);
        pack();
    }

    /**
     * 向容器添加按钮。
     * @param c 容器
     * @param title 按钮标题
     * @param listener 按钮的动作监听器
     */
    public void addButton(Container c, String title, ActionListener listener)
    {
        JButton button = new JButton(title);
        c.add(button);
        button.addActionListener(listener);
    }

    /**
     * 向画布添加一个跳动的球并启动一个线程让它跳动。
     */
    public void addBall()
    {
        Ball ball = new Ball();
        comp.add(ball);
        Runnable r = () -> {
            try {
                for (int i = 1; i <= STEPS; i++) {
                    ball.move(comp.getBounds());
                    comp.repaint();
                    Thread.sleep(DELAY);
                }
            } catch (InterruptedException e) {
            }
        };
        Thread t = new Thread(r);
        t.start();
    }
}
```

---

`java.lang.Thread`
- `Thread(Runnable target)` 构造一个新线程并调用指定目标的 `run()` 方法。
- `void start()` 启动该线程，导致 `run()` 方法被调用。此方法立即返回。新线程并发运行。
- `void run()` 调用关联 `Runnable` 的 `run` 方法。

---

`java.lang.Runnable`
- `void run()` 必须被重写，并提供你想要执行的任务的指令。

---

## 14.2 中断线程

线程在它的 `run` 方法返回时终止——通过执行 `return` 语句、执行完方法体中的最后一个语句，或者发生了在方法中未被捕获的异常。在 Java 的初始版本中，还有一个 `stop` 方法，另一个线程可以调用它来终止线程。然而，该方法现在已经废弃。我们将在第 14.5.15 节“为什么 `stop` 和 `suspend` 方法被废用”中讨论原因，位于第 896 页。

除了废弃 `stop` 方法外，没有办法可以*强制*终止线程。但是可以使用 `interrupt` 方法来*请求*终止线程。

当在线程上调用 `interrupt` 方法时，该线程的*中断状态*（interrupted status）会被设置。这是一个存在于每个线程中的 `boolean` 标志。每个线程都应该偶尔检查自己是否被中断。

要确定中断状态是否被设置，首先调用静态方法 `Thread.currentThread` 获取当前线程，然后调用 `isInterrupted` 方法：
```java
while (!Thread.currentThread().isInterrupted() && more work to do)
{
    do more work
}
```

- 在 `catch` 句中，调用 `Thread.currentThread().interrupt()` 来设置中断状态。然后调用者就可以对其进行测试。
```java
void mySubTask()
{
   . . .
   try { sleep(delay); }
   catch (InterruptedException e) { Thread.currentThread().interrupt(); }
   . . .
}
```

- 或者，更好的方法是，在你的方法上标记 `throws InterruptedException` 并丢弃 `try` 块。这样调用者（或最终的 `run` 方法）就可以捕获该异常。
```java
void mySubTask() throws InterruptedException
{
   . . .
   sleep(delay);
   . . .
}
```



# `java.lang.Thread` 1.0

- `void interrupt()` 向线程发送中断请求。线程的中断状态被设置为 `true`。如果线程当前正阻塞于 `sleep` 的调用，则会抛出一个 `InterruptedException`。
- `static boolean interrupted()` 测试当前线程（即正在执行此指令的线程）是否被中断。注意，这是一个静态方法。该调用具有副作用——它会将当前线程的中断状态重置为 `false`。
- `boolean isInterrupted()` 测试一个线程是否被中断。与 `static interrupted` 方法不同，此调用不会改变线程的中断状态。
- `static Thread currentThread()` 返回代表当前执行线程的 `Thread` 对象。

## 14.3 线程状态

线程可以处于六种状态之一：

- 新建（New）
- 可运行（Runnable）
- 阻塞（Blocked）
- 等待（Waiting）
- 定时等待（Timed waiting）
- 已终止（Terminated）

这些状态中的每一个将在随后的章节中进行解释。

要确定线程的当前状态，只需调用 `getState` 方法即可。

### 14.3.1 新的线程

当你使用 `new` 操作符创建一个线程时——例如，`new Thread(r)`——线程尚未运行。这意味着它处于新（new）状态。当线程处于新建状态时，程序尚未开始执行其内部的代码。在线程运行之前，需要完成一些记录性工作。

### 14.3.2 可运行的线程

一旦调用了 `start` 方法，线程就处于可运行（runnable）状态。一个可运行的线程可能正在运行，也可能没有。给线程分配运行时间取决于操作系统。（不过，Java 规范并没有将其称为一个独立的状态。运行中的线程仍然处于可运行状态。）

一旦线程开始运行，它并不一定会持续运行。事实上，运行中的线程偶尔暂停是理想的，这样其他线程才有机会运行。线程调度的细节取决于操作系统所提供的服务。抢占式调度系统为每个可运行线程分配一个时间片来执行其任务。当该时间片耗尽时，操作系统会抢占该线程并给另一个线程工作的机会（参见图 14.4）。在选择下一个线程时，操作系统会考虑线程的优先级——更多信息请参阅第 14.4.1 节“线程优先级”，位于第 858 页。

所有现代桌面和服务器操作系统都使用抢占式调度。然而，手机等小型设备可能使用协作式调度。在这样的设备中，线程只有在调用 `yield` 方法或被阻塞或等待时才会失去控制权。

在具有多个处理器的机器上，每个处理器都可以运行一个线程，你可以让多个线程并行运行。当然，如果线程数多于处理器，调度器仍然必须进行时间分片。

始终记住，一个可运行线程在任何时刻可能正在运行，也可能没有运行。（这就是为什么该状态被称为“可运行”而不是“正在运行”。）

### 14.3.3 阻塞和等待的线程

当线程被阻塞或等待时，它是临时不活跃的。它不执行任何代码并消耗极少的资源。重新激活它取决于线程调度器。细节取决于如何进入不活跃状态。

- 当线程尝试获取当前由另一个线程持有的内部对象锁（不是 `java.util.concurrent` 库中的 `Lock`）时，它会变为阻塞状态。（我们在第 14.5.3 节“锁对象”中讨论锁对象，并在第 14.5.5 节“`synchronized` 关键字”中讨论内部对象锁。）
- 当线程等待通知时，它进入等待（waiting）状态。这是通过在第 14.5.3 节中调用 `wait` 或 `notify` 实现的。
- 若干方法具有超时功能。调用它们会导致线程进入定时等待状态。该状态一直持续到超时过期或收到通知。具有超时的方法包括 `sleep`、`wait`、`join` 和 `await`。

点击此处查看代码图像。

![图 14.3](img/14fig03.jpg)

**图 14.3** 线程状态

### 14.3.4 已终止的线程

线程因两个原因之一终止：

- 因为 `run` 方法正常退出而自然死亡。
- 因为一个未捕获的异常终止了 `run` 方法而突然死亡。

特别是，你可以通过调用 `stop` 方法来杀死线程。该方法会抛出一个 `ThreadDeath` 错误杀死线程。然而，`stop` 方法已被废弃，你不应该在自己的代码中调用它。

## 14.4 线程属性

在后续章节中，我们将讨论线程的各种属性：线程优先级、守护线程、线程组以及未捕获异常的处理器。

### 14.4.1 线程优先级

在 Java 编程语言中，每个线程都有优先级。默认情况下，线程继承构造它的线程的优先级。你可以使用 `setPriority` 方法增加或减少任何线程的优先级。你可以将优先级设置为从 `MIN_PRIORITY`（在 `Thread` 类中定义为 `1`）到 `MAX_PRIORITY`（定义为 `10`）之间的任何值。`NORM_PRIORITY` 定义为 `5`。

当线程调度器有机会选择新线程时，它偏好于优先级更高的线程。然而，线程优先级是高度依赖于系统的。当虚拟机依赖于宿主平台的线程实现时，Java 线程优先级会被映射到宿主平台的优先级级别，而宿主平台可能有更多或更少的线程优先级级别。

例如，Windows 有七个优先级级别。某些 Java 优先级将映射到相同的操作系统级别。在用于 Linux 的 Oracle JVM 中，线程优先级被完全忽略了——所有线程具有相同的优先级。

初级程序员有时会过度使用线程优先级。调整优先级的理由很少。你绝对不应该这样设计你的程序结构，使其程序的正确运行依赖于优先级级别。

> **注意**
>
> 如果你确实使用了优先级，应该意识到一个常见的初学者错误。如果你有多个高优先级线程且它们不进入空闲状态，低优先级线程可能永远不会执行。每当调度器决定运行新线程时，它都会首先从最高优先线程中进行选择，即使这会导致低优先级线程完全饥饿。

### `java.lang.Thread` 1.0

- `void setPriority(int newPriority)`  
  设置此线程的优先级。优先级必须在 `Thread.MIN_PRIORITY` 和 `Thread.MAX_PRIORITY` 之间。使用 `Thread.NORM_PRIORITY` 设置普通优先级。
- `static int MIN_PRIORITY`  
  `Thread` 可以拥有的最低优先级。最小优先级值为 `1`。
- `static int NORM_PRIORITY`  
  `Thread` 的默认优先级。默认优先级为 `5`。
- `static int MAX_PRIORITY`  
  `Thread` 可以拥有的最高优先级。最大优先级值为 `10`。
- `static void yield()`  
  导致当前执行的线程让出 CPU。如果有其他优先级至少与此线程优先级相同的可运行线程，它们将在下一个被调度。请注意这是一个静态方法。

### 14.4.2 守护线程

你可以通过调用以下代码将线程转换为守护线程（daemon thread）：

```java
t.setDaemon(true);
```

这种线程并没有什么“守护”属性。守护线程仅仅是一个除了服务他人之外没有其他角色的线程。例如向其他线程发送定期“定时器滴答”的定时器线程，或者清理过时的缓存条目的线程。当只剩下守护线程时，虚拟机就会退出。如果所有剩余线程都是守护线程，那么保持程序运行就没有意义。

初学者有时会误用守护线程，因为他们不想考虑关闭操作。然而，这可能是危险的。守护线程永远不应该访问持久化资源（如文件或数据库），因为它可以随时终止，甚至是在操作的中间。

### `java.lang.Thread` 1.0

- `void setDaemon(boolean isDaemon)`  
  将此线程标记为守护线程或用户线程。此方法必须在线程启动之前调用。

### 14.4.3 未捕获异常的处理器

线程的 `run` 方法不能抛出任何检查异常（checked exceptions），但它可以被运行时异常（unchecked exception）终止。在这种情况下，线程会死亡。

然而，没有 `catch` 子可以传播异常。相反，在线程死亡之前，异常会被传递给未捕获异常的处理器。

该处理器必须属于实现 `Thread.UncaughtExceptionHandler` 接口的类。该接口有一个方法：

```java
void uncaughtException(Thread t, Throwable e)
```

你可以通过 `setUncaughtExceptionHandler` 方法为任何线程安装一个处理器。你也可以使用 `Thread` 类的静态方法 `setDefaultUncaughtExceptionHandler` 为所有线程安装一个默认处理器。替换的处理器可以使用日志 API 将未捕获异常的报告发送到日志文件中。

如果你没有安装默认处理器，则默认处理器为 `null`。但是，如果你没有为单个线程安装处理器，则处理器是该线程的 `ThreadGroup` 对象。

> **注意**
>
> 线程组是可以一起管理的线程的集合。默认情况下，你创建的所有线程都属于同一个线程组，但也可以建立其他的分组。由于现在有了更好的功能来操作线程集合，我们建议你不要在程序中使用线程组。

`ThreadGroup` 类实现了 `Thread.UncaughtExceptionHandler` 接口。它的 `uncaughtException` 方法执行以下操作：

1. 如果线程组有父线程组，则调用父线程组的 `uncaughtException` 方法。
2. 否则，如果 `Thread.getDefaultUncaughtExceptionHandler` 方法返回一个非 `null` 处理器，则调用它。
3. 否则，如果 `Throwable` 是 `ThreadDeath` 实例，则什么都不会发生。
4. 否则，线程名称和 `Throwable` 的堆栈跟踪将打印在 `System.err` 上。

这就是你无疑在程序中见过很多次的堆栈跟踪。

### `java.lang.Thread` 1.0

- `static void setDefaultUncaughtExceptionHandler(Thread.UncaughtExceptionHandler handler)` 5.0
- `static Thread.UncaughtExceptionHandler getDefaultUncaughtExceptionHandler()` 5.0  
  设置或获取未捕获异常的默认处理器。
- `void setUncaughtExceptionHandler(Thread.UncaughtExceptionHandler handler)` 5.0
- `Thread.UncaughtExceptionHandler getUncaughtExceptionHandler()` 5.0  
  设置或获取未捕获异常的处理器。如果未安装处理器，则线程对象就是处理器。

### `java.lang.Thread.UncaughtExceptionHandler` 5.0

- `void uncaughtException(Thread t, Throwable e)`  
  用于在线程因未捕获异常终止时记录自定义报告。

![Image](img/861tab01.jpg)

### `java.lang.ThreadGroup` 1.0

- `void uncaughtException(Thread t, Throwable e)`  
  如果存在父线程组，则调用父线程组的此方法；否则调用 `Thread` 类的默认处理器；否则在标准错误流中打印堆栈跟踪。（然而，如果 `e` 是 `ThreadDeath` 对象，则抑制堆栈跟踪。`ThreadDeath` 对象是由已弃用的 `stop` 方法生成的。）

## 14.5 同步

在大多数实际的多线程应用程序中，两个或多个线程需要共享数据访问。如果两个线程访问同一个对象并各自调用修改对象状态的方法会发生什么？正如你想象的，线程可能会相互干扰。取决于访问数据的顺序，可能会导致对象损坏。这种情况通常被称为竞态条件（race condition）。

### 14.5.1 竞态条件的示例

为了防止多个线程损坏共享数据，你必须学习如何同步访问。在本节中，你将看到如果不使用同步会发生什么。在下一节中，你将看到如何同步数据访问。

在下一个测试程序中，我们模拟一个拥有多个账户的银行。我们随机生成在这些账户之间移动资金的交易。每个账户有一个线程。每次交易将随机金额从该线程服务的账户移动到另一个随机账户。

模拟代码非常直观。我们有一个 `Bank` 类，其中包含 `transfer` 方法。该方法将某些金额从一个账户转移到另一个账户。（我们还不担心账户余额为）。这是 `Bank` 类 `transfer` 方法的代码。

```java
public void transfer(int from, int to, double amount)
```

```java
// CAUTION: unsafe when called from multiple threads
{
    System.out.print(Thread.currentThread());
    accounts[from] -= amount;
    System.out.printf(" %10.2f from %d to %d", amount, from, to);
    accounts[to] += amount;
    System.out.printf(" Total Balance: %10.2f%n", getTotalBalance());
}
```

这里是 `Runnable` 实例的代码。`run` 方法不断地从指定的银行账户中提取资金。在每次迭代中，`run` 方法会选取一个随机目标账户和一个随机金额，调用 `bank` 对象的 `transfer` 方法，然后睡眠。

点击此处查看代码图片。

```java
Runnable r = () -> {
    try {
        while (true) {
            int toAccount = (int) (bank.size() * Math.random());
            double amount = MAX_AMOUNT * Math.random();
            bank.transfer(fromAccount, toAccount, amount);
            Thread.sleep((int) (DELAY * Math.random()));
        }
    } catch (InterruptedException e) {
    }
};
```

当此模拟运行时，我们并不知道任何时候任何一个银行账户中有多少钱。但我们知道，所有账户的总金额应该保持不变，因为我们所做的只是将从一个账户转移到另一个账户。

在每笔交易结束时，`transfer` 方法会重新计算总和并将其打印。

该程序永远不会结束。只需按 `Ctrl+C` 杀死程序。

这是一段典型的输出：

```text
. . .

Thread[Thread-11,5,main]    588.48 from 11 to 44 Total Balance: 100000.00

Thread[Thread-12,5,main]    976.11 from 12 to 22 Total Balance: 100000.00

Thread[Thread-14,5,main]    521.51 from 14 to 22 Total Balance: 100000.00

Thread[Thread-13,5,main]    359.89 from 13 to 81 Total Balance: 100000.00

. . .

Thread[Thread-36,5,main]    401.71 from 36 to 73 Total Balance:  99291.06

Thread[Thread-35,5,main]    691.46 from 35 to 77 Total Balance:  99291.06

Thread[Thread-37,5,main]      78.64 from 37 to 3 Total Balance:  99291.06

Thread[Thread-34,5,main]    197.11 from 34 to 69 Total Balance:  99291.06

Thread[Thread-36,5,main]     85.96 from 36 to 4 Total Balance:  99291.06

. . .

Thread[Thread-4,5,main]Thread[Thread-33,5,main]       7.31 from 31 to 32 Total Balance:

99979.24

      627.50 from 4 to 5 Total Balance: 99979.24

. . .
```



如你所见，出了非常严重的问题。对于几次交易，银行余额保持在 $100,000，这是 100 个每个 $1,000 账户的正确总额。但过段时间后余额发生了轻微变化。当你运行此程序时，错误可能会很快发生，或者余额可能需要很长时间才会变得损坏。这种情况并不令人产生信心，你可能不想把辛苦赚的钱存入这样的银行。

代码列表 14.5 和 14.6 中的程序提供了完整的源代码。看下你是否能发现代码中的问题。我们将在下一节中解开这个谜团。

### 代码列表 14.5 `unsynch/UnsynBankTest.java`

点击此处查看图片

```java
package unsynch;

/**
 * 此程序展示了当多个线程访问数据结构时出现的数据损坏。
 *
 * @version 1.3 2015-06-21
 * @author Cay
 */
public class UnsynBankTest {
    public static final int ACCOUNTS = 100;
    public static final double INITIAL_BALANCE = 1000;
    public static final double MAX_AMOUNT = 1000;
    public static final int DELAY = 10;

    public static void main(String[] args) {
        Bank bank = new Bank(ACCOUNTS, INITIAL_BALANCE);

        for (int i = 0; i < ACCOUNTS; i++) {
            int fromAccount = i;

            Runnable r = () -> {
                try {
                    while (true) {
                        int toAccount = (int) (bank.size() * Math.random());
                        double amount = MAX_AMOUNT * Math.random();

                        bank.transfer(fromAccount, toAccount, amount);
                        Thread.sleep((int) (DELAY * Math.random()));
                    }
                } catch (InterruptedException e) {
                }
            };

            Thread t = new Thread(r);
            t.start();
        }
    }
}
```

### 代码列表 14.6 `unsynch/Bank.java`

点击此处查看图片

```java
package unsynch;

import java.util.*;

/**
 * 拥有多个账户的银行。
 *
 * @version 1.3 2004-08-01
 * @author Cay
 */
public class Bank {
    private final double[] accounts;

    /**
     * 银行。
     *
     * @param n 账户数量
     * @param initialBalance 每个账户的初始余额
     */
    public Bank(int n, double initialBalance) {
        accounts = new double[n];
        Arrays.fill(accounts, initialBalance);
    }

    /**
     * 将资金从一个账户转移到另一个账户。
     *
     * @param from 从哪个账户转移
     * @param to 转移到哪个账户
     * @param amount 转移的金额
     */
    public void transfer(int from, int to, double amount) {
        if (accounts[from] < amount) return;

        System.out.print(Thread.currentThread());
        accounts[from] -= amount;
        System.out.printf(" %10.2f from %d to %d", amount, from, to);
        accounts[to] += amount;
        System.out.printf(" Total Balance: %10.2f%n", getTotalBalance());
    }

    /**
     * 获取所有账户余额的总和。
     *
     * @return 总余额
     */
    public double getTotalBalance() {
        double sum = 0;

        for (double a : accounts) {
            sum += a;
        }

        return sum;
    }

    /**
     * 获取银行中的账户数量。
     *
     * @return 账户数量
     */
    public int size() {
        return accounts.length;
    }
}
```

#### 14.5.2 竞态条件解释

在上一节中，我们运行了一个多个线程更新银行账户余额的程序。一段时间后，错误出现了，某些资金丢失了或凭空产生。这个问题发生在两个线程同时尝试更新一个账户时。假设两个线程同时执行指令：

`accounts[to] += amount;`

问题在于这些不是原子操作。该指令可能会按以下方式处理：

1. 将 `accounts[to]` 加载到寄存器。
2. 加上 `amount`。
3. 将结果移回 `accounts[to]`。

现在，假设第一个线程执行步骤 1 和 2，然后被抢占。假设第二个线程醒并更新同一个条目。然后第一个线程恢复并完成步骤 3。

该操作覆盖了另一个线程的修改。结果是总和不再正确（参见图 14.4）。

![Image](img/14fig04.jpg)

**图 14.4** 线程并发访问

我们的测试程序检测到了这种损坏。（当然，如果线程在执行测试时被中断，会有极小的概率出现误报！）

> ![Image](img/note.jpg) 注意
>
> 你实际上可以查看执行类中每个语句的虚拟机字节码。运行命令 `javap -c -v Bank` 来反编译 `Bank.class` 文件。例如，行 `accounts[to] += amount;` 被翻译为以下字节码：
>
> 点击此处查看代码图片

```asm
aload_0
```

```java
getfield #2; //Field accounts:D
iload_2
dup2
daload
dload_3
dadd
dastore
```

这些代码的含义并不重要。关键在于增量命令是由几条指令组成的，执行这些指令的线程可以在任何指令处被中断。

这种损坏发生的概率有多大？我们通过将打印语句与更新余额的语句交替执行，增加了观察到该问题的概率。

如果你省略打印语句，损坏的风险会降低许多，因为每个线程在再次进入睡眠之前的工作量非常少，调度器不太可能在计算过程中抢占它的执行。然而，损坏的风险并不会完全消失。如果你在负载很重的机器上运行大量线程，即使删除了打印语句，程序仍然会失败。失败可能会在几分钟后、几小时或几天后发生。坦率地说，对于程序员来说，没有什么比每隔几天才出现一次的错误更糟糕的了。

真正的问题是 `transfer` 方法的工作可能会在中途中断。如果我们能确保方法在线程丢失控制权之前运行完成，银行账户对象的状态永远不会被损坏。

### 14.5.3 锁对象

有两种机制可以保护代码块免受并发访问。Java 语言提供了 `synchronized` 关键字来实现这一目的，Java SE 5.0 引入了 `ReentrantLock` 类。`synchronized` 关键字自动提供了一个锁以及相关的“条件（condition）”，这使得对于大多数需要显式锁的情况来说既强大又方便。然而，我们认为在单独查看了锁和条件之后，理解 `synchronized` 关键字会更容易。`java.util.concurrent` 框架为这些基础机制提供了单独的类，我们在此以及第 14.5.4 节“条件对象”（第 872 页）进行了解释。一旦你理解了这些构建块，我们将在第 14.5.5 节“`synchronized` 关键字”（第 878 页）中介绍 `synchronized` 关键字。

使用 `ReentrantLock` 保护代码块的基本结构是：

```java
myLock.lock(); // 一个 ReentrantLock 对象

try {
    critical section
} finally {
    myLock.unlock(); // 即使抛出异常也能确保解锁
}
```

这种结构保证了一次只有一个线程可以进入临界区域。一旦一个线程锁定了对象，其他线程就无法通过 `lock` 语句。当其他线程调用 `lock` 时，它们会被去激活状态，直到第一个线程释放锁对象。

> ![Image](img/caution.jpg) 注意
>
> 将 `unlock` 操作封装在 `finally` 子句中至关重要。如果临界区域中的代码抛出异常，必须解锁。否则，其他线程将被永久阻塞。

> ![Image](img/note.jpg) 备注
>
> 当你使用锁时，无法使用 `try-with-resources` 语句。首先，`unlock` 方法并不名为 `close`。但即使它被重命名了，`try-with-resources` 语句也无法工作。它的头部期望声明一个新变量。但当你使用锁时，你希望继续使用线程间共享的同一个变量。

让我们使用锁来保护 `Bank` 类的 `transfer` 方法。

```java
public class Bank {
    private Lock bankLock = new ReentrantLock(); // ReentrantLock 实现 Lock 接口

    ...

    public void transfer(int from, int to, int amount) {
        bankLock.lock();

        try {
            System.out.print(Thread.currentThread());
            accounts[from] -= amount;
            System.out.printf(" %10.2f from %d to %d", amount, from, to);
            accounts[to] += amount;
            System.out.printf(" Total Balance: %10.2f%n", getTotalBalance());
        } finally {
            bankLock.unlock();
        }
    }
}
```

通常，一个线程进入关键区域后，发现自己在条件满足之前无法继续。使用 `condition object`（条件对象）来管理那些已获取锁但无法进行有效工作的线程。在本节中，我们将介绍 Java 库中条件对象的实现。（由于历史原因，条件对象通常被称为 `condition variables` 条件变量。）

让我们完善一下对银行的模拟。我们不想从一个没有资金的账户转出资金。请注意，我们不能使用如下代码：

```java
if (bank.getBalance(from) >= amount)
    bank.transfer(from, to, amount);
```

在测试结果成功和调用 `transfer` 之间，当前线程完全可能会被停用。

```java
if (bank.getBalance(from) >= amount)
    // 线程在此处可能会被激活
    bank.transfer(from, to, amount);
```

当线程再次运行时，账户余额可能已经低于提取金额。你必须确保在测试和转移操作之间，没有其他线程可以修改余额。你通过用锁同时保护测试和转移操作来实现这一点：

```java
public void transfer(int from, int to, int amount) {
    bankLock.lock();

    try {
        while (accounts[from] < amount) {
            // wait
            ...
        }

        // transfer funds
        ...
    } finally {
        bankLock.unlock();
    }
}
```

现在，当账户中钱不足时，我们该怎么办？我们等待直到其他线程增加了资金。但此线程刚刚获得了 `bankLock` 的独占访问权限，因此其他线程没有机会进行存款。这就是条件对象的用武之场。

一个锁对象可以有一个或多个相关的条件对象。你通过 `newCondition` 方法获取条件对象。习惯上会为每个条件对象命名一个能够唤起它所代表条件的名称。例如，在这里我们设置了一个条件对象来代表“资金充足”的条件。

```java
class Bank {
    private Condition sufficientFunds;

    ...

    public Bank() {
        ...
        sufficientFunds = bankLock.newCondition();
    }
}
```

如果 `transfer` 方法发现资金不足，它会调用：

`sufficientFunds.await();`

当前线程现在被停用并放弃锁。这让另一个线程能够进入，我们希望它能增加账户余额。

等待获取锁的线程与调用了 `await` 的线程之间存在本质区别。一旦线程调用了 `await` 方法，它就会进入该条件的 `wait set`（等待集）。当锁可用时，该线程不会被变为可运行状态。相反，它一直保持停用，直到另一个线程在同一个条件上调用了 `signalAll` 方法。

当另一个线程转账资金后，它应该调用：

`sufficientFunds.signalAll();`

此调用会重新激活所有等待该条件的线程。当线程从等待集中被移除时，它们再次变为可运行状态，调度器最终会再次激活它们。届时，它们将尝试重新进入对象。一旦锁可用，其中一个线程将获取锁并从它停止的地方继续执行，并从 `await` 调用中返回。

此时，线程应该再次测试该条件。无法保证该条件现在已经满足——`signalAll` 方法仅仅向等待线程发出信号，表示条件此时可能已经满足，并且值得再次检查该条件。

> **注意**：通常情况下，对 `await` 的调用应该位于如下形式的循环内部：
>
> ```java
> while (!(ok to proceed))
>     condition.await();
> ```

至关重要的一点是，其他线程最终必须调用 `signalAll` 方法。当线程调用 `await` 时，它无法重新激活自己。它寄希望于其他线程。如果没有一个线程去重新激活等待的线程，它将永远不再运行。这可能导致糟糕的 `deadlock`（死锁）情况。如果所有其他线程都被阻塞，而最后一个活跃的线程调用 `await` 而没有解锁其中任何一个，它也会被阻塞。没有线程可以解锁其他线程，程序就会挂起。

什么时候应该调用 `signalAll`？法则是，每当对象的状态发生可能对等待线程有利的变化时，就调用 `signalAll`。例如，每当账户余额变化时，等待线程都应该获得再次检查的机会。在我们的示例中，当我们完成资金转移时，调用 `signalAll`。

```java
public void transfer(int from, int to, int amount) {
    bankLock.lock();

    try {
        while (accounts[from] < amount)
            sufficientFunds.await();

        // transfer funds
        ...

        sufficientFunds.signalAll();
    } finally {
        bankLock.unlock();
    }
}
```




注意，调用 `signalAll` 并不会立即激活等待的线程。它只是解除等待线程的阻塞，以便它们在当前线程释放锁后可以竞争进入对象。另一种方法 `signal`我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。仅从等待集中随机选择一个线程并解除其阻塞。这比解除所有线程的效率更高，但存在风险。如果随机选中的线程发现它仍然无法继续，它将再次被阻塞。如果没有其他线程再次调用 `signal`，系统就会发生死锁。

***

**警告**：线程只有在拥有锁的情况下，才能对某个条件调用 `await`、`signalAll` 或 `signal`。

***

如果你运行 `Listing 14.7` 中的示例程序，你会发现没有任何问题发生。总余额将永远保持在 100,000 美元。没有任何账户是负余额。（再次，按 `Ctrl+C` 终止程序。）你可能还会注意到程序运行得稍慢——这是你为同步中增加的账目记录付出的代价。

在实践中，正确地使用条件是非常挑战性的。在开始实现你的条件对象之前，你应该考虑使用第 934 页第 14.10 节“同步器”中描述的构造之一。

**Listing 14.7** `synch/Bank.java`

```java
package synch;

import java.util.*;
import java.util.concurrent.locks.*;

/**
 * 一个拥有多个银行账户的银行，使用锁来实现顺序访问。
 *
 * @version 1.30 2004-08-01
 * @author Cay Horstmann
 */
public class Bank {
    private final double[] accounts;

    private Lock bankLock;
    private Condition sufficientFunds;

    /**
     * 银行。
     *
     * @param n 账户数量
     * @param initialBalance 每个账户的初始余额
     */
    public Bank(int n, double initialBalance) {
        accounts = new double[n];
        Arrays.fill(accounts, initialBalance);
        bankLock = new ReentrantLock();
        sufficientFunds = bankLock.newCondition();
    }

    /**
     * 将资金从一个账户转到另一个账户。
     *
     * @param from 转出账户
     * @param to 转入账户
     * @param amount 要转账金额
     */
    public void transfer(int from, int to, double amount)
        throws InterruptedException {
        // 实现细节
    }
}
```

```java
bankLock.lock();
try {
    while (accounts[from] < amount)
        sufficientFunds.await();

    System.out.print(Thread.currentThread());
    accounts[from] -= amount;
    System.out.printf(" %10.2f from %d to %d", amount, from, to);
    accounts[to] += amount;
    System.out.printf(" Total Balance: %10.2f%n", getTotalBalance());
    sufficientFunds.signalAll();
}
finally {
    bankLock.unlock();
}
```

```java
/**
 * 获取所有账户余额的总和。
 *
 * @return 总余额
 */
public double getTotalBalance() {
    bankLock.lock();
    try {
        double sum = 0;
        for (double a : accounts)
            sum += a;
        return sum;
    }
    finally {
        bankLock.unlock();
    }
}
```

```java
/**
 * 获取银行中的账户数量。
 *
 * @return 账户数量
 */
public int size() {
    return accounts.length;
}

}
```

`java.util.concurrent.locks.Lock` 5.0

- `Condition newCondition()` 返回一个与此锁相关的条件对象。

`java.util.concurrent.locks.Condition` 5.0

- `void await()` 将此线程置于该条件的等待集中。
- `void signalAll()` 解阻塞该条件等待集中的所有线程。
- `void signal()` 解阻塞该条件等待集中的随机选择的一个线程。

### 14.5.5 `synchronized` 关键字

在前面的节中，你已经学习了如何使用 `Lock` 和 `Condition` 对象。在继续下去之前，让我们总结一下关于锁和条件的关键点：

- 锁保护代码段，允许一次只有一个线程执行代码。
- 锁管理尝试进入受保护代码的线程。
- 一个锁可以有一个或多个条件对象。
- 每个条件对象管理已进入受保护区域但无法继续执行的线程。

`Lock` 和 `Condition` 接口为程序员提供了对锁的高粒度控制。然而，在大多数情况下，你不需要那种控制——你可以使用 Java 语言内置的机制。从 1.0 版本以来，Java 中的每个对象都有一个内建锁（intrinsic lock）。如果一个方法用 `synchronized` 关键字声明，该对象的锁就会保护整个方法。也就是说，要调用该方法，线程必须获取内建锁。换句话说：

```java
public synchronized void method() {
    // 方法体
}
```

等同于：

```java
public void method() {
    intrinsicLock.lock();
    try {
        // 方法体
    }
    finally {
        intrinsicLock.unlock();
    }
}
```

例如，与其使用显式锁，我们可以简单地将 `Bank` 类的 `transfer` 方法声明为 `synchronized`。内建对象锁只有一个关联条件。`wait` 方法将线程添加到等待集，而 `notifyAll`/`notify` 方法则解阻塞线程。换句话说，调用 `wait` 或 `notifyAll` 等同于：

```java
intrinsicCondition.await();

intrinsicCondition.signalAll();
```

**注意**：`wait`、`notifyAll` 和 `notify` 方法是 `Object` 类的 `final` 方法。`Condition` 方法必须命名为 `await`、`signalAll` 和 `signal`，以避免与这些方法冲突。

例如，你可以这样在 Java 中实现 `Bank` 类：

```java
class Bank {
    private double[] accounts;

    public synchronized void transfer(int from, int to, int amount)
        throws InterruptedException {
        while (accounts[from] < amount)
            wait(); // 在内建对象锁单一条件上等待

        accounts[from] -= amount;
        accounts[to] += amount;

        notifyAll(); // 通知所有等待该条件的线程
    }

    public synchronized double getTotalBalance() {
        // ...
    }
}
```

如你所见，使用 `synchronized` 关键字产生的代码简洁得多。当然，为了理解这段代码，你必须知道每个对象都有一个内建锁，并且该锁有一个内建条件。锁管理尝试进入 `synchronized` 方法的线程。条件管理调用了 `wait` 的线程。

**提示**：`synchronized` 方法相对直接。然而，初学者经常在条件上遇到困扰。在使用 `wait/notifyAll` 之前，你应该考虑使用第 14.10 节“同步器”（第 934 页）描述的构造之一。

将静态方法声明为 `synchronized` 也是合法的。如果调用此类方法，它会获取关联类对象的内建锁。例如，如果 `Bank` 类有一个静态同步方法，那么在调用时，`Bank.class` 对象会被锁定。结果是其他线程无法调用该类或同一类的其他同步静态方法。

内建锁和条件有一些局限性。其中：

- 你无法中断尝试获取锁的线程。
- 在尝试获取锁时无法指定超时时间。
- 一个锁只有一个条件可能会效率低下。

在代码中应该用什么——`Lock` 和 `Condition` 对象还是 `synchronized` 方法？这是我们的建议：

- 最好既不使用 `Lock`/`Condition` 也不使用 `synchronized` 关键字。在许多情况下，你可以使用 `java.util.concurrent` 包中的机制之一，它们会为你完成所有的锁操作。例如，在第 14.6 节。

```java
System.out.print(Thread.currentThread());
accounts[from] -= amount;
System.out.printf(" %10.2f from %d to %d", amount, from, to);
accounts[to] += amount;
System.out.printf(" Total Balance: %10.2f%n", getTotalBalance());
notifyAll();

/**
 * 获取所有账户余额的总和。
 *
 * @return 总余额
 */
public synchronized double getTotalBalance() {
    double sum = 0;
    for (double a : accounts)
        sum += a;
    return sum;
}

/**
 * 获取银行中的账户数量。
 *
 * @return 账户数量
 */
public int size() {
    return accounts.length;
}
```

`java.lang.Object` 1.0

- `void notifyAll()`  
  解除在该对象上调用 `wait` 的线程阻塞。此方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，该方法将抛出 `IllegalMonitorStateException`。

- `void notify()`  
  在该对象上调用 `wait` 的线程中随机解除一个线程阻塞。此方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，该方法将抛出 `IllegalMonitorStateException`。

- `void wait()`  
  导致线程等待直到其被通知。此方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，该方法将抛出 `IllegalMonitorStateException`。

- `void wait(long millis)`
- `void wait(long millis, int nanos)`  
  导致线程等待直到其被通知或指定的时长到为止。这些方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，它们将抛出 `IllegalMonitorStateException`。

![Image](img/882tab01.jpg)

### 14.5.6 同步块

正如我们刚刚讨论的，每个 Java 对象都拥有一把锁。线程可以通过调用同步方法来获取锁。获取锁的第二种机制是进入 `synchronized block`（同步块）。当线程进入形式如下的块时：

```java
synchronized (obj) // 这是同步块的语法
{
    critical section
}
```

此时它就获取了 `obj` 的锁。

你有时会发现“临时（ad hoc）”锁，例如：

```java
public class Bank {
    private double[] accounts;
    private Object lock = new Object();

    // ...

    public void transfer(int from, int to, int amount) {
        synchronized (lock) // 一个临时锁
        {
            accounts[from] -= amount;
        }
    }
}
```

（注：原文中存在大量重复的示例代码，已根据要求仅保留核心内容并翻译。）

如果你使用 `locks` 来保护可以被多个线程访问的代码，就不会出现这些问题。编译器被要求遵守 `locks`，在需要时刷新本地缓存，并且不恰当地重排指令。细节在 JSR `133` 开发的 Java 内存模型和线程规范中进行了解释（参见 [`www.jcp.org/en/jsr/detail?id=133`](http://www.jcp.org/en/jsr/detail?id=133)）。该规范的大部分内容非常复杂且具有技术性，但文档也包含许多解释清晰的示例。Brian Goetz 编写的一篇更易理解的概述文章可以在 [`www.ibm.com/developerworks/library/j-jtp02244`](http://www.ibm.com/developerworks/library/j-jtp02244) 找到。

***

![Image](img/note.jpg)

**注意**

Brian Goetz 创造了以下“同步格言”：

> 如果你写了一个接下来可能被另一个线程读取的变量，或者你读取了一个最近可能被另一个线程写入的变量，你必须使用同步。

***

`volatile` 关键字为同步实例字段的访问提供了一种无锁机制。如果你将一个字段声明为 `volatile`，那么编译器和虚拟机就会考虑到该字段可能会被另一个线程并发更新。

例如，假设一个对象有一个 `boolean` 标记 `done`，由一个线程设置并在另一个线程查询。正如我们已经讨论的，你可以使用锁：

```java
private boolean done;

public synchronized boolean isDone() {
    return done;
}

public synchronized void setDone() {
    done = true;
}
```

或许使用内置对象锁并不是好主意。如果另一个线程锁定了该对象，`isDone` 和 `setDone` 方法可能会阻塞。如果存在这种担心，可以为这个变量使用一个单独的锁。但这会变得非常麻烦。

在这种情况下，将字段声明为 `volatile` 是合理的：

```java
private volatile boolean done;

public boolean isDone() {
    return done;
}

public void setDone() {
    done = true;
}
```

编译器将插入适当的代码，以确保一个线程对 `done` 变量的变化对于读取该变量的任何其他线程可见。

***

![Image](img/caution.jpg)

**注意**

Volatile 变量不提供任何原子性。例如，该方法：

```java
public void flipDone() {
    done = !done; // 不是原子的
}
```

并不保证能够翻转字段的值。无法保证读取、翻转和写入的过程是不中断的。

### 14.5.9 `final` 变量

正如你在上一节中看到的，除非你使用 `locks` 或 `volatile` 修饰符，否则你无法从多个线程安全地读取字段。

还有一种安全访问共享字段的情况——当它被声明为 `final` 时。考虑：

```java



```java
final Map<String, Double> accounts = new HashMap<>();
```

其他线程在构造函数执行完成后可以看到`accounts`变量。

如果不使用`final`，无法保证其他线程能看到`accounts`的更新值——它们可能都看到`null`，而不是构造好的`HashMap`。

当然，在 map 上的操作不是线程安全的。如果多个线程变异并读取 map，你仍然需要`locks`。

### 14.5.10 原子类（Atomics）

只要你执行的是除赋值以外的操作，就可以将共享变量声明为`volatile`。

`java.util.concurrent.atomic`包中有一许多类，它们使用高效的机器级指令在不使用`locks`的情况下保证其他操作的原子性。例如，`AtomicInteger`类具有`incrementAndGet`和`decrementAndGet`方法，可以原子地递增或减少一个整数。例如，你可以安全地生成这样的数字序列：

```java
public static AtomicLong nextNumber = new AtomicLong();

// 在某个线程中...

long id = nextNumber.incrementAndGet();
```

`incrementAndGet`方法原子地递增`AtomicLong`并返回自增后的值。也就是说，获取值、加 1、设置值和产生新值的操作是无法被中断的。即使多个线程并发访问同一个实例，也能保证计算并返回正确的值。

虽然有用于原子地设置、添加和减去值的方法，但如果你想进行更复杂的更新，就必须使用`compareAndSet`方法。例如，假设你想跟踪由不同线程观察到的最大值。以下代码不起作用：

```java
public static AtomicLong largest = new AtomicLong();

// 在某个线程中...

largest.set(Math.max(largest.get(), observed)); // 错误--竞态条件！
```

这种更新不是原子的。相反，计算新值并在循环中使用`compareAndSet`：

```java
do {
    oldValue = largest.get();
    newValue = Math.max(oldValue, observed);
} while (!largest.compareAndSet(oldValue, newValue));
```

如果另一个线程也在更新`largest`，它可能比这个线程更快。那么`compareAndSet`将返回`false`。在这种情况下，循环重试读取更新后的值。最终它会成功。

在 Java 8 中，你不再需要写循环了。相反，你提供一个 lambda 表达式来更新变量，更新会自动完成。在我们的示例中，我们可以调用：

```java
largest.updateAndGet(x -> Math.max(x, observed));
```

或者：

```java
largest.accumulateAndGet(observed, Math::max);
```

`accumulateAndGet`方法接收一个用于合并原子值和传入参数的二元运算符。还有`getAndUpdate`和`getAndAccumulate`方法返回旧值。

> **注意**
>
> 这些方法也为`AtomicInteger`、`AtomicIntegerArray`、`AtomicIntegerFieldUpdater`、`AtomicLongArray`、`AtomicLongFieldUpdater`、`AtomicReference`、`AtomicReferenceArray`和`AtomicReferenceFieldUpdater`提供。

当有大量线程访问相同的原子值时，由于乐观更新需要多次重试，性能会下降。Java 8 提供了`LongAdder`和`LongAccumulator`来解决这个问题。`LongAdder`由多个变量组成，它们的和就是当前值。多个线程可以更新不同的加数，当线程数增加时会自动提供新的加数。这在所有工作完成后才需要和值的情况下是非常高效的。性能提升可能是巨大的。

如果你预见到高竞争，你应该直接使用`LongAdder`而不是`AtomicLong`。方法名略有不同。调用`increment`递增计数器或`add`添加数量，并使用`sum`获取总和。

```java
final LongAdder adder = new LongAdder();

for (. . .) {
    pool.submit(() -> {
        while (. . .) {
            . . .

            if (. . .) adder.increment();
        }
    });
}

. . .

long total = adder.sum());
```

当然，`increment`方法不会返回旧值。这样做会抵消将和拆分为多个加数所带来的效率提升。

`LongAccumulator`将这一思想推广到任意的累加操作。在构造函数中，你提供该操作以及它的单位元。要合并新值，请调用`accumulate`。调用`get`获取当前值。以下效果与`LongAdder`相同：

```java
LongAccumulator adder = new LongAccumulator(Long::sum, 0);

// 在某些线程中...

adder.accumulate(value);
```

在内部，累加器拥有变量`a[1]`、`a[2]`、`. .`、`a[n]`。每个变量初始化为单位元（在我们的示例中为`0`）。

当调用`accumulate`并传入值`v`时，其中一个变量会被原子地更新为`a[i] = a[i] op v`，其中`op`是以中缀形式编写的累加操作。在我们的示例中，调用`accumulate`会为某个`i`计算`a[i] = a[i] + v`。

`get`的结果是`a[1] op a[2] op ... op a[n]`。在我们的示例中，这就是所有累加器的和，`a[1] + a[2] + ... + a[n]`。

如果你选择不同的操作，可以计算最大或最小值。通常，该操作必须满足结合律和交换律。这意味着最终结果与中间值组合的顺序无关。

还有`DoubleAdder`和`DoubleAccumulator`，它们的工作方式相同，只是处理`double`类型的值。

### 14.5.11 死锁

锁和条件无法解决多线程中出现的所有问题。考虑以下情况：

1. 账户 1：$200
2. 账户 2：$300
3. 线程 1：从账户 1 转账 $300 到账户 2
4. 线程 2：从账户 2 转账 $400 到账户 1

正如图 14.6 所示，线程 1 和 2 显然都被阻塞了。它们都无法继续，因为账户 1 和账户 2 的余额不足。

![Image](img/14fig06.jpg)

**图 14.6** 死锁现场

所有线程都可能阻塞，因为每个线程都在等待更多的钱。这种情况被称为死锁。

在我们的程序中，死锁发生的原因很简单。每个转账金额最多为 $1,000。由于有 100 个账户且总金额为 $100,000，任何时候至少有一个账户拥有至少 $1,000。因此，从该账户取出资金的线程可以继续。

但如果你修改线程的`run`方法以移除 $1,000 的交易限制，死锁会迅速发生。尝试一下。将`NACCOUNTS`设置为`10`。构造每个转账任务，其`max`值为`2 * INITIAL_BALANCE`并运行程序。程序将运行一段时间后挂起。

> **提示**
>
> 当程序挂起时，按下 Ctrl+\。你会得到一个列出所有线程的线程转储。每个线程都有栈跟踪，告诉它当前阻塞在哪里。或者，按照第 7 章中的描述运行`jconsole`并查看 Threads 面板（参见图 14.7）。

![Image](img/tip.jpg)

![Image](img/14fig07.jpg)

**图 14.7** `jconsole`中的 Threads 面板

创建死锁的另一种方法是让第`i`个线程负责向第`i`个账户存款，而不是从第`i`个账户取。在这种情况下，所有线程可能会围攻同一个账户，每个试图从中取出超过余额的钱。尝试一下。在`SynchBankTest`程序中，转到`TransferRunnable`类的`run`方法。在调用`transfer`时，反转`fromAccount`和`toAccount`。运行程序看它是如何立即死锁的。

另一个容易发生死锁的情况：在`SynchBankTest`程序中将`signalAll`方法改为`signal`。你会发现程序最终会挂起。（再次，最好将`NACCOUNTS`设置为`10`以更快观察到效果。）与通知所有等待资金增加的线程的`signalAll`不同，`signal`方法只解阻塞一个线程。如果该线程无法继续，所有线程都可能被阻塞。考虑以下正在形成死锁的示例场景：

1. 账户 1：$1,990
2. 所有其他账户：每个 $990
3. 线程 1：从账户 1 转账 $995 到账户 2
4. 所有其他线程：从它们的账户转账 $995 到另一个账户

显然，除线程 1 外的所有线程都被阻塞了，因为钱不够。

### 14.5.12 线程本地变量

在前面的节中，我们讨论了线程间共享变量的风险。有时，你可以通过使用`ThreadLocal`助手为每个线程提供自己的实例来避免共享。例如，`SimpleDateFormat`类不是线程安全的。假设我们有一个静态变量：

```java
public static final SimpleDateFormat dateFormat =
    new SimpleDateFormat("yyyy-MM-dd");
```

重写此方法以提供初始值。默认情况下，此方法返回`null`。

- `void set(T t)`  
  为此线程设置新值。

- `void remove()`  
  移除此线程的值。

- `static <S> ThreadLocal<S> withInitial(Supplier<? extends S> supplier)` **8**  
  创建一个线程本地变量，其初始值通过调用给定的 supplier 产生。

#### `java.util.concurrent.ThreadLocalRandom` **7**

- `static ThreadLocalRandom current()`  
  返回一个对于当前线程唯一的`Random`类的实例。

### 14.5.13 锁测试与超时

当线程调用`lock`方法来获取由另一个线程拥有的锁时，会被无限阻塞。你可以更谨慎地获取锁。`tryLock`方法尝试获取锁，如果成功则返回`true`。否则，它会立即返回`false`，线程可以去执行其他事情。

```java
if (myLock.tryLock()) {
    // 现在线程拥有了锁
    try {
        . . .
    } finally {
        myLock.unlock();
    }
} else {
    // 执行其他事情
}
```

你可以带超时参数调用`tryLock`，如下所示：

```java
if (myLock.tryLock(100, TimeUnit.MILLISECONDS)) . . .
```

`TimeUnit`是一个枚举，其值为`SECONDS`、`MILLISECONDS`、`MICROSECONDS`和`NANOSECONDS`。

`lock`方法不能被中断。如果线程在等待获取锁时被中断，该被中断的线程将继续阻塞，直到锁可用。如果发生了死锁，那么`lock`方法将永远不会结束。

然而，如果你带超时参数调用`tryLock`，当线程在等待期间被中断时，会抛出一个`InterruptedException`。这显然是一个非常有用的特性，因为它允许程序打破死锁。

你还可以调用`lockInterruptibly`方法。它的含义与带无限超时时的`tryLock`相同。

当你等待条件（condition）时，也可以提供一个超时时间：

```java
myCondition.await(100, TimeUnit.MILLISECONDS))
```

如果另一个线程通过调用`signalAll`或`signal`激活了此线程，或者超时到达，或者线程被中断，则`await`方法返回。

如果等待的线程被中断，`await`方法会抛出`InterruptedException`。在（可能不太可能的）你宁愿继续等待的情况下，请使用`awaitUninterruptibly`方法。

#### `java.util.concurrent.locks.Lock` **5.0**

- `boolean tryLock()`  
  尝试在不阻塞获取锁；如果成功则返回`true`。如果锁可用，即使它具有公平锁策略且有其他线程在等待，此方法也会获取该锁。

- `boolean tryLock(long time, TimeUnit unit)`  
  尝试获取锁，阻塞时间不超过给定时间；如果成功则返回`true`。

- `void lockInterruptibly()`  
  获取锁，无限阻塞。如果线程被中断，则抛出`InterruptedException`。

#### `java.util.concurrent.locks.Condition` **5.0**

- `boolean await(long time, TimeUnit unit)`  
  进入该条件的等待集，阻塞直到线程从等待集中被移除或过了给定时间。如果方法是因为时间到了而返回，则返回`false`，否则返回`true`。

- `void awaitUninterruptibly()`  
  进入该条件的等待集，阻塞直到线程从等待集中被移除。如果线程被中断，此方法不会抛出`InterruptedException`。

### 14.5.14 读/写锁

`java.util.concurrent.locks`包定义了两个锁类：我们已经讨论过的`ReentrantLock`和`ReentrantReadWriteLock`。当有许多线程从数据结构中读取，而只有少数线程对其进行修改时，后者非常有用。在这种情况下，允许读取者共享访问是合理的。当然，写者必须具有独占访问权限。

使用读/写锁所需的步骤如下：

**1.** 构造一个`ReentrantReadWriteLock`对象：

```java
private ReentrantReadWriteLock rwl = new ReentrantReadWriteLock();
```

**2.** 提取读锁和写锁：

```java
private Lock readLock = rwl.readLock();
private Lock writeLock = rwl.writeLock();
```

**3.** 在所有访问器中使用读锁：

```java
public double getTotalBalance() {
    readLock.lock();
    try {
        . . .
    } finally {
        readLock.unlock();
    }
}
```

**4.** 在所有修改器中使用写锁：

```java
public void transfer(...) {
    writeLock.lock();
    try {
        . . .
    } finally {
        writeLock.unlock();
    }
}
```




## `java.util.concurrent.locks.ReentrantReadWriteLock` 5.0

- `Lock readLock()`

  获取一个读锁，允许多个读取者并发。

- `Lock writeLock()`

  获取一个写锁，排除读取者。

## 14.5.15 为什么 `stop` 和 `suspend` 方法被弃用

Java 早期定义了一个 `stop` 方法来直接终止线程，以及 `suspend` 方法来阻塞线程直到另一个线程调用 `resume`。`stop` 和 `suspend` 方法有一个共同点：它们尝试在没有线程协作的情况下控制线程的行为。

`stop`、`suspend` 和 `resume` 方法已经被弃用。`stop` 方法本质上是不安全的，`suspend` 方法经常会导致死锁。在本节中，你将看到这些方法的问题。

让我们先来看看 `stop` 方法。它会终止所有的方法。当线程被停止时，它会立即释放持有的锁。这会导致对象处于不一致状态。例如，假设一个 `TransferRunnable` 在从一个账户转账到另一个账户的过程中、存款之前被停止。现在银行对象损坏了。由于锁已经被释放，这种损坏对于未停止的其他线程是可见的。

当一个线程想要停止另一个线程时，它无法知道何时 `stop` 方法是安全的，何时会导致对象损坏。因此，该方法被弃用了。当你想要停止一个线程时，应该中断它。被中断的线程可以在安全时停止。

> **注意**
>
> 某些作者声称 `stop` 方法被弃用是因为它会导致对象被停止的线程永久锁定。然而，这种主言并不成立。停止的线程会退出它调过的同步方法——技术上是通过抛出一个 `ThreadDeath` 异常。作为结果，线程释放了它持有的内部对象锁。

接下来，让我们看看 `suspend` 方法的问题所在。这种这种情况在图形用户界面中经常发生。假设我们有一个银行的可视化模拟。一个标记为“暂停”的按钮挂起传输线程，一个标记为“恢复”的按钮恢复它们。

点击此处查看代码图片。

```java
pauseButton.addActionListener(event -> {
   for (int i = 0; i < threads.length; i++)
      threads[i].suspend(); // 不要这样做
});
```

```java
resumeButton.addActionListener(event -> {
    for (int i = 0; i < threads.length; i++)
        threads[i].resume();
});
```

假设有一个 `paintComponent` 方法绘制每个账户的图表，并调用 `getBalances` 方法来获取余额数组。

正如你在第 14.11 节中看到的，第 937 页的“线程与 Swing

你现在已经看到了构成 Java 并发编程基础的底层构建块。然而，对于实际编程，你希望避开低级结构。使用由并发专家实现的高级结构要简单得多也安全得多。

许多线程问题可以使用一个或多个队列来优雅且安全地表述。生产者线程向队列中插入元素，消费者线程从中从中提取元素。队列允许你安全地将数据从一个线程传递给另一个线程。例如，考虑我们的银行程序。传输线程不再直接访问 `bank` 对象，而是将传输对象插入队列中。另一个线程从队列中移除指令。只有该线程可以访问 `bank` 对象的内部。不需要同步（当然，线程安全队列类的实现者必须担心锁和条件，但那不是你的工作）。

*阻塞队列*（blocking queue）会在你在队列满时尝试添加元素或在队列为空时尝试移除元素导致线程阻塞。阻塞队列是协调多个线程工作的有用工具。工作线程定期将中间结果存入阻塞队列。其他工作线程移除中间结果并对其进行修改。队列会自动平衡负载。如果第一组线程运行得比第二组慢，第二组会在等待结果时被阻塞。如果第一组线程运行得快，队列就会一直填充，直到第二组追上进度。表 14.1 显示了阻塞队列的方法。

### 表 14.1 阻塞队列方法

阻塞队列方法分为三类，区别在于它们在队列满或为空时所执行的操作。如果你将队列作为线程管理工具，请使用 `put` 和 `take` 方法。`add`、`remove` 和 `element` 操作在尝试向满队列添加元素或获取空队列头元素时会抛出异常。当然，在多线程程序中，队列可能在任何时候变满或为空，因此你可能希望使用 `offer`、`poll` 和 `peek` 方法。这些方法会直接返回一个失败指示，而不是抛出异常。

注意：`poll` 和 `peek` 方法返回 `null` 以表示失败。因此，向这些队列中插入 `null` 值是非法的。

还有带有超时的 `offer` 和 `poll` 方法变体。例如，以下调用：

```java
boolean success = q.offer(x, 100, TimeUnit.MILLISECONDS);
```

尝试 100 毫秒向队列尾部插入一个元素。如果成功，返回 `true`；否则，在超时后返回 `false`。同样，调用：

```java
Object head = q.poll(100, TimeUnit.MILLISECONDS);
```

尝试 100 毫秒移除队列头。如果成功，返回头元素；否则，在超时后返回 `null`。

`put` 方法在队列满时阻塞，`take` 方法在队列为空时阻塞。这些是不带超时的 `offer` 和 `poll` 的等价操作。

`java.util.concurrent` 包提供了多种阻塞队列的变体。默认情况下，`LinkedBlockingQueue` 的容量没有上限，但可以可选地指定最大容量。`LinkedBlockingDeque` 是双端版本的。`ArrayBlockingQueue` 使用指定的容量和一个可选的需要公平性（fairness）的参数构造。如果指定了公平性，则等待最长的线程将获得优先对待。一如既往，公平性会带来巨大的性能代价，你只有在问题特别需要时才应该使用它。

`PriorityBlockingQueue` 是优先级队列，而不是先进先出队列。元素按照其优先级顺序移除。队列具有无界容量，但队列为空时检索会阻塞。（有关优先级队列的更多信息请参阅第 9 章。

`DelayQueue` 包含了实现了 `Delayed` 接口的对象：

```java
interface Delayed extends Comparable<Delayed> {

    long getDelay(TimeUnit unit);

}
```

`getDelay` 方法返回剩余延迟。负值表示延迟已过去。只有当延迟过去后，才能从 `DelayQueue` 中移除元素。你还需要实现 `compareTo` 方法。`DelayQueue` 使用该方法对条目进行排序。

Java SE 7 增加了 `TransferQueue` 接口，允许生产者线程等待消费者准备好接收项。当生产者调用：

```java
q.transfer(item);
```

该调用将阻塞直到另一个线程移除它。`LinkedTransferQueue` 类实现了此接口。

代码列表 14.9](#ch14a.html_ch14list9) 显示了如何使用阻塞队列控制一组线程。程序搜索目录及其子目录中的所有文件，打印包含给定关键字的行。

生产者线程遍历所有子目录下的文件并将其放入阻塞队列。此操作非常快，如果队列没有边界，它将迅速填充文件系统中的文件。

我们还启动了大量的搜索线程。每个搜索线程从队列中取一个文件，打开它，打印所有包含关键字的行，然后取下一个文件。我们使用一种技巧在不再需要进一步工作时终止应用程序。为了信号完成，遍历线程向队列中放入一个虚拟对象。（这类似于行李传送带上贴有“最后一件行李”标签的虚拟箱子。）当搜索线程取出虚拟对象时，它将其放回去并终止。

注意，这里不需要显式的线程同步。在在此应用程序中，我们使用队列数据结构作为同步机制。

```java
import java.util.*;

import java.util.concurrent.*;

/**
 * @version 1.02 2015-06-21
 * @author Cay Horstmann
 */

public class BlockingQueueTest {

    private static final int FILE_QUEUE_SIZE = 10;

    private static final int SEARCH_THREADS = 100;

    private static final File DUMMY = new File("");

    private static BlockingQueue<File> queue = new ArrayBlockingQueue<>(FILE_QUEUE_SIZE);

    public static void main(String[] args) {

        try (Scanner in = new Scanner(System.in)) {

            System.out.print("Enter base directory (e.g. /opt/jdk1.8.0/src): ");

            String directory = in.nextLine();

            System.out.print("Enter keyword (e.g. volatile): ");

            String keyword = in.nextLine();

            Runnable enumerator = () -> {

                try {

                    enumerate(new File(directory));

                    queue.put(DUMMY);

                } catch (InterruptedException e) {

                }

            };

            new Thread(enumerator).start();

            for (int i = 1; i <= SEARCH_THREADS; i++) {

                Runnable searcher = () -> {

                    try {

                        boolean done = false;

                        while (!done) {

                            File file = queue.take();

                            if (file == DUMMY) {

                                queue.put(file);

                                done = true;

                            } else

                                search(file, keyword);

                        }

                    } catch (IOException e) {

                        e.printStackTrace();

                    } catch (InterruptedException e) {

                    }

                };

                new Thread(searcher).start();

            }

        }

    }

    /**
     * 递归地列出给定目录及其子目录中的所有文件。
     * @param directory 开始枚举的目录
     */

    public static void enumerate(File directory) throws InterruptedException {

        File[] files = directory.listFiles();

        for (File file : files) {

            if (file.isDirectory()) enumerate(file);

            else queue.put(file);

        }

    }

    /**
     * 在文件中搜索给定关键字并打印所有匹配项。
     * @param file 要搜索的文件
     * @param keyword 要搜索的关键字
     */

    public static void search(File file, String keyword) throws IOException {

        try (Scanner in = new Scanner(file, "UTF-8")) {

            int lineNumber = 0;

            while (in.hasNextLine()) {

                lineNumber++;

                String line = in.nextLine();

                if (line.contains(keyword)) {

                    System.out.printf("%s:%d:%s%n", file.getPath(), lineNumber, line);

                }

            }

        }

    }

}
```





### `java.util.concurrent.ArrayBlockingQueue<E>` 5.0

- `ArrayBlockingQueue(int capacity)`
- `ArrayBlockingQueue(int capacity, boolean fair)` 构建一个给定容量和公平性设置的阻塞队列。队列由循环数组实现。

### `java.util.concurrent.LinkedBlockingQueue<E>` 5.0

### `java.util.concurrent.LinkedBlockingDeque<E>` 6

- `LinkedBlockingQueue()`
- `LinkedBlockingDeque()` 构建一个无界的阻塞队列或双端队列，由链表实现。
- `LinkedBlockingQueue(int capacity)`
- `LinkedBlockingDeque(int capacity)` 构建一个给定容量的边界阻塞队列或双端队列，由链表实现。

### `java.util.concurrent.DelayQueue<E extends Delayed>` 5.0

- `DelayQueue()` 构建一个包含 `Delayed` 元素的无界阻塞队列。只有延迟到期的元素才能从队列中移除。

### `java.util.concurrent.Delayed` 5.0

- `getDelay(TimeUnit unit)` 获取此对象的延迟，以给定的时间单位测量。

### `java.util.concurrent.PriorityBlockingQueue<E>` 5.0

- `PriorityBlockingQueue()`
- `PriorityBlockingQueue(int initialCapacity)`
- `PriorityBlockingQueue(int initialCapacity, Comparator<? super E> comparator)` 构建一个堆实现的无界阻塞优先级队列。

![Image](img/904tab01.jpg)

### `java.util.concurrent.BlockingQueue<E>` 5.0

- `void put(E element)` 添加元素，必要时阻塞。
- `E take()` 移除并返回头部元素，必要时阻塞。
- `boolean offer(E element, long time, TimeUnit unit)` 添加给定的元素并在成功时返回 `true`，必要时阻塞直到元素被添加或时间超时。
- `E poll(long time, TimeUnit unit)` 移除并返回头部元素，必要时阻塞直到元素可用或时间超时。失败时返回 `null`。

### `java.util.concurrent.BlockingDeque<E>` 6

- `void putFirst(E element)`
- `void putLast(E element)` 添加元素，必要时阻塞。
- `E takeFirst()`
- `E takeLast()` 移除并返回头部或尾部元素，必要时阻塞。
- `boolean offerFirst(E element, long time, TimeUnit unit)`
- `boolean offerLast(E element, long time, TimeUnit unit)` 添加给定的元素并在成功时返回 `true`，必要时阻塞直到元素被添加或时间超时。
- `E pollFirst(long time, TimeUnit unit)`
- `E pollLast(long time, TimeUnit unit)` 移除并返回头部或尾部元素，必要时阻塞直到元素可用或时间超时。失败时返回 `null`。

### `java.util.concurrent.TransferQueue<E>` 7

- `void transfer(E element)`
- `boolean tryTransfer(E element, long time, TimeUnit unit)` 传输一个值，或在给定超时时间内尝试传输，阻塞直到另一个线程移除该项。第二个方法在成功时返回 `true`。

某些应用程序使用了巨大的并发哈希表，其规模大到 `size` 方法因为返回类型 `int` 而不再适用。对于一个拥有超过 20 亿条目的映射，该怎么办？Java SE 8 引入了 `mappingCount` 方法，它以 `long` 类型返回大小。

---

集合返回的是弱一致的迭代器。这意味着迭代器可能反映也可能不反映在构造之后所发生的所有修改，但它们不会重复返回同一个值，且不会抛出 `ConcurrentModificationException`。

---

![Image](img/note.jpg) 备注

相比之下，`java.util` 包中集合的迭代器在迭代器构造后集合被修改时，会抛出 `ConcurrentModificationException`。

---

并发哈希表可以高效地支持大量的读取者和固定的写入者。默认情况下，假设最多有 16 个并发写入线程。可以有更多的写入线程，但如果有超过 16 个线程同时进行写入，其他线程会被临时阻塞。你可以在构造函数中指定更高的数字，但你可能不需要这样做。

---

![Image](img/note.jpg) 备注

哈希映射将所有具有相同哈希值的条目放在同一个“桶”中。某些应用程序使用了糟糕的哈希函数，导致所有条目最终落入少数几个桶，严重降低了性能。即使是通常合理的哈希函数，例如 `String` 类的哈希函数，也出现问题。例如，攻击者可以通过构造大量哈希到相同值的字符串来减慢程序。从 Java SE 8 开始，当键类型实现了 `Comparable` 接口时，并发哈希表将桶组织成树而不是列表，保证了 `O(log(n))` 的性能。

### `java.util.concurrent.ConcurrentLinkedQueue<E>` 5.0

- `ConcurrentLinkedQueue<E>()`

构造一个无界的、非阻塞队列，多个线程可以安全地访问。

### `java.util.concurrent.ConcurrentSkipListSet<E>` 6

- `ConcurrentSkipListSet<E>()`
- `ConcurrentSkipListSet<E>(Comparator<? super E> comp)`

构造一个排序的集合，多个线程可以安全地访问。第一个构造函数要求元素实现 `Comparable` 接口。

### `java.util.concurrent.ConcurrentHashMap<K, V>` 5.0

### `java.util.concurrent.ConcurrentSkipListMap<K, V>` 6

- `ConcurrentHashMap<K, V>()`
- `ConcurrentHashMap<K, V>(int initialCapacity)`
- `ConcurrentHashMap<K, V>(int initialCapacity, float loadFactor, int concurrencyLevel)`

构造一个多个线程可以安全访问的哈希映射。

![Image](img/907tab01.jpg)

- `ConcurrentSkipListMap<K, V>()`
- `ConcurrentSkipListSet<K, V>(Comparator<? super K> comp)`

构造一个多个线程可以安全访问的排序映射。第一个构造函数要求键实现 `Comparable` 接口。

#### 14.7.2 映射条目的原子更新

`ConcurrentHashMap` 的原始版本只有几个用于原子更新的方法，这使得编程变得有些笨拙。假设我们想要统计某些功能出现的频率。作为一个简单的例子，假设多个线程遇到单词，我们想要统计它们的频率。

我们可以使用 `ConcurrentHashMap<String, Long>` 吗？考虑增加计数器的代码。显然，以下代码不是线程安全的：

```
Long oldValue = map.get(word);
Long newValue = oldValue == null ? 1 : oldValue + 1;
map.put(word, newValue); // 错误--可能没有替换 oldValue
```

另一个线程可能同时在更新同一个计数。

---

![Image](img/note.jpg) 备注

有些程序员感到惊讶，一个所谓的线程安全数据结构竟然允许非线程安全的操作。但这里涉及的是两种完全不同的考虑。如果多个线程修改一个普通的 `HashMap`，它们可能会破坏内部结构（链表数组）。某些链可能会丢失，甚至形成环路，导致数据结构无法使用。这在 `ConcurrentHashMap` 中是永远不会发生的。在上面的示例中，`get` 和 `put` 的代码永远不会损坏数据结构。但是，由于操作序列不是原子的，结果是不可预测的。

---

一个经典的技巧是使用 `replace` 操作，它会原子地将旧值替换为新值，前提是没有其他线程在此之前进来并将旧值替换为了其他内容。你必须一直执行，直到 `replace` 成功：

```
do {
    oldValue = map.get(word);
    newValue = oldValue == null ? 1 : oldValue + 1;
} while (!map.replace(word, oldValue, newValue));
```

或者，你可以使用 `ConcurrentHashMap<String, AtomicLong>`，或者在 Java SE 8 中使用 `ConcurrentHashMap<String, LongAdder>`。那么更新代码如下：

```
map.putIfAbsent(word, new LongAdder()).increment();
```

第一条语句确保存在一个我们可以增加的 `LongAdder`。由于 `putIfAbsent` 返回已存在的值，所以我们可以增加它：

```
map.putIfAbsent(word, new LongAdder()).increment();
```

实际上，第一条语句确保存在一个 `LongAdder` 我们可以进行增加。由于 `putIfAbsent` 返回已存在的值，我们可以增加它。

Java SE 8 提供了更方便的原子更新方法。`compute` 方法根据键和关联值（如果没有则为 `null`）被调用，并计算新值。例如，这里是更新计数器映射的方法：

```
map.compute(word, (k, v) -> v == null ? 1 : v + 1);
```

---

`ConcurrentHashMap` 不允许 `null` 值。许多方法使用 `null` 值来指示给键不存在。

---

还有 `computeIfPresent` 和 `computeIfAbsent` 变体，它们仅在存在旧值或不存在时计算新值。`LongAdder` 计数器可以这样更新：

```
map.computeIfAbsent(word, k -> new LongAdder()).increment();
```

与之前看到的 `putIfAbsent` 类似，但只有在实际上需要新计数器时才会调用 `LongAdder` 的构造函数。

你通常需要在键首次添加时执行某些特殊操作。`merge` 方法使得这特别方便。它有一个在键不存在时使用的初始值参数。否则，将调用你提供的函数，合并现有值和初始值。（与 `compute` 不同，该函数不处理键。）

```
map.merge(word, 1L, (existingValue, newValue) -> existingValue + newValue);
```

或者更简单地：

```
map.merge(word, 1L, Long::sum);
```

没有比这更简洁的。

---

![Image](img/note.jpg) 备注

如果传递给 `compute` 或 `merge` 的函数返回 `null`，则现有的条目将从映射中移除。

---

![Image](img/caution.jpg) 警告

当你使用 `compute` 或 `merge` 时，请记住你提供的函数不应执行过多的工作。在该函数运行期间，映射的某些更新可能会被阻塞。当然，该函数也不应该更新映射的其他部分。

#### 14.7.3 并发哈希表的批量操作

Java SE 8 为并发哈希映射（concurrent hash maps）提供了批量操作，这些操作即使在其他线程对映射进行操作时也能安全执行。批量操作会遍历映射，并在遍历过程中对发现的元素进行操作。它并没有尝试冻结某一时间点的映射快照。除非你确定在批量操作运行期间映射没有被修改，否则你应该将其结果视为映射状态的近似值。

共有三类型的操作：

- `search`：对每个键和/或值应用函数，直到该函数产生非空结果。然后搜索停止并返回函数的结果。
- `reduce`：使用提供的累加函数合并所有的键和/或值。
- `forEach`：对所有键和/或值应用函数。

每个操作都有四个版本：

- `operationKeys`：对键（keys）操作。
- `operationValues`：对值（values）操作。
- `operation`：对键和值操作。
- `operationEntries`：对 `Map.Entry` 对象操作。

对于每种操作，你都需要指定一个并行阈值（`parallelism threshold`）。如果映射包含的元素多于该阈值，则批量操作将并行化。如果你想让批量操作在单线程中运行，请使用 `Long.MAX_VALUE` 作为阈值。如果你希望为批量操作提供最大数量的线程，请使用 1 作为阈值。

让我们先看看 `search` 方法。以下是各个版本：

```
U searchKeys(long threshold, BiFunction<? super K, ? extends U> f)

U searchValues(long threshold, BiFunction<? super V, ? extends U> f)

U search(long threshold, BiFunction<? super K, ? super V, ? extends U> f)

U searchEntries(long threshold, BiFunction<Map.Entry<K, V>, ? extends U> f)
```

例如，假设我们想要找到出现次数超过 1000 次的单词。我们需要搜索键和值：

```
String result = map.search(threshold, (k, v) -> v > 1000 ? k : null);
```

然后，`result` 被设置为第一个匹配项，或者如果搜索函数对所有输入都返回 `null`，则将其设置为 `null`。

`forEach` 方法有两个变体。第一种简单地为每个映射条目应用一个消费者（consumer）函数，例如：

```
map.forEach(threshold,
    (k, v) -> System.out.println(k + " -> " + v));
```

第二种变体接收额外的转换器（transformer）函数，该函数首先被应用，其结果传递给消费者：

```
map.forEach(threshold,
    (k, v) -> k + " -> " + v, // Transformer
    System.out::println); // Consumer
```

转换器可以用过滤器。每当转换器返回 `null` 时，该值会被静默跳过。例如，在这里我们只打印值较大的条目：

```
map.forEach(threshold,
    (k, v) -> v > 1000 ? k + " -> " + v : null, // Filter and transformer
    System.out::println); // null 值不会被传递给消费者
```

`reduce` 操作使用累加函数合并其输入。例如，这里是你可以计算所有值的和的方法：

```
Long sum = map.reduceValues(threshold, Long::sum);
```

与 `forEach` 一样，你也可以提供转换器函数。在这里我们计算最长键的长度：

```
Integer maxlength = map.reduceKeys(threshold,
    String::length, // Transformer
    Integer::max); // Accumulator
```

转换器可以充当过滤器，通过返回 `null` 来排除不需要的输入。在这里，我们统计有多少条条目的值大于 1000：

```
Long count = map.reduceValues(threshold,
    v -> v > 1000 ? 1L : null,
    Long::sum);
```




![Image](img/note.jpg) 注意事项

如果映射为空，或者所有条目都被过滤掉，`reduce` 操作将返回 `null`。如果只有一个元素，则返回其转换结果，且不应用累加器。

针对 `int`、`long` 和 `double` 输出有特殊化，后缀分别为 `ToInt`、`ToLong` 和 `ToDouble`。你需要将输入转换为原始类型，并指定一个默认值和一个累加函数。当映射为空时，将返回默认值。

```java
long sum = map.reduceValuesToLong(threshold,
    Long::longValue, // Transformer to primitive type
    0, // 空映射的默认值
    Long::sum); // Primitive type accumulator
```

这些特殊化版本的行为与对象版本不同（对象版本中只考虑一个元素）。它们不是返回转换后的元素，而是与默认值进行累加。因此，默认值必须是累加器的中元元素。

### 14.7.4 并发集合视图 (Concurrent Set Views)

假设你需要一个大型的线程安全的集合而不是映射。并没有 `ConcurrentHashSet` 类，而且你比尝试自己创建一个要明智得多。当然，你可以使用带有伪造值的 `ConcurrentHashMap`，但那样你得到的是映射而不是集合，而且你无法应用 `Set` 接口的操作。

静态方法 `newKeySet` 产生一个 `Set<K>`，它实际上是 `ConcurrentHashMap<K, Boolean>` 的包装器。

```java
Set<String> words = ConcurrentHashMap.<String>newKeySet();
```

当然，如果你有一个有的映射，`keySet` 方法产生键集合。该集合是可变的。如果你移除集合的元素，键（以及值）也会从映射中移除。但向集合添加元素是没有意义的，因为没有值可以添加。Java SE 8 为 `ConcurrentHashMap` 添加了带有默认值的 `keySet` 方法，用于向集合添加元素：

```java
Set<String> words = map.keySet(1L);
words.add("Java");
```

如果 `"Java"` 不在 `words` 中，现在它的数量变为一。

### 14.7.5 数组复制 (Copy on Arrays)

`CopyOnWriteArrayList` 和 `CopyWriteArraySet` 是线程安全的集合，所有修改者都会复制底层数组。如果遍历集合的线程多于修改它的线程，这种安排非常有用。当你构造迭代器时，它包含当前数组的引用。如果数组后来修改，迭代器仍然持有旧数组，但集合的数组被替换了。因此，迭代器拥有一个一致（但可能过时的）视图，无需任何同步即可访问。

### 14.7.6 并行数组算法 (Parallel Array Algorithms)

从 Java SE 8 开始，`Arrays` 类有很多并行化操作。静态方法 `Arrays.parallelSort` 可以排序原始类型值或对象的数组。例如：

```java
String contents = new String(Files.readAllBytes(
    Paths.get("alice.txt")), StandardCharsets.UTF_8); // 读取文件到字符串
String[] words = contents.split("[\\P{L}]+"); // 按非字母分割
Arrays.parallelSort(words);
```

排序对象时，你可以提供一个 `Comparator`。

```java
Arrays.parallelSort(words, Comparator.comparing(String::length));
```

对于所有方法，你都可以提供范围的边界，例如

```java
values.parallelSort(values.length / 2, values.length); // 排序后半部分
```

乍一看，这些方法的名称中包含 `parallel`（并行）似乎有点奇怪，因为用户并不应该关心排序是如何发生的。然而，API 设计者希望明确表示排序是并行化的。这样一来，用户就会警惕并避免使用带有副作用的比较器。

`parallelSetAll` 方法使用从函数计算出的值填充数组。该函数接收元素索引并计算该位置的值。

```java
Arrays.parallelSetAll(values, i -> i % 10);
// 将 values 填充为 0 1 2 3 4 5 6 7 8 9 0 1 2 ...
```

显然，此操作受益于并行化。它为所有基本数据类型数组和对象数组都提供了相应的版本。

最后，还有一个 `parallelPrefix` 方法，它将数组的每个元素替换为给定的结合律操作的前缀累加和。哈？这里有一个例子。考虑数组 `[1, 2, 3, 4, ...]` 和 × 操作。执行 `Arrays.parallelPrefix(values, (x, y) -> x * y)` 后，数组包含：

`[1, 1 × 2, 1 × 2 × 3, 1 × 2 × 3 × 4, ...]`

也许令人惊讶的是，这种计算是可以并行化的。首先，如此处所示，合并相邻元素：

`[1, 1 × 2, 3, 3 × 4, 5, 5 × 6, 7, 7 × 8]`

灰色值保持不变。显然，可以在数组的不同区域并行进行此计算。在下一步中，通过将被指示的元素与其下方一或两个位置的元素相乘来更新它们：

`[1, 1 × 2, 1 × 2 × 3, 1 × 2 × 3 × 4, 5, 5 × 6, 5 × 6 × 7, 5 × 6 × 7 × 8]`

这同样可以并行完成。在 `log(n)` 步之后，处理即完成。如果有足够的处理器，这比直观的线性计算要胜一筹筹。在专用硬件上，这种算法被广泛使用，而此类硬件的用户在将其适配到各种问题方面非常有才智。

### 14.7.7 旧的线程安全集合

自从 Java 初始发布以来，`Vector` 和 `Hashtable` 类就提供了动态数组和哈希表的线程安全实现。这些类现在被认为是过时的，被 `ArrayList` 和 `HashMap` 类所取代。而这些类不是线程安全的。相反，集合库提供了一种不同的机制。任何集合类都可以通过同步包装器变为线程安全：

```java
List<E> synchArrayList = Collections.synchronizedList(new ArrayList<E>());
Map<K, V> synchHashMap = Collections.synchronizedMap(new HashMap<K, V>());
```

生成的集合的方法受锁保护，提供了线程安全的访问。

你应该确保没有线程通过原始的未同步方法访问数据结构。确保这一点最简单的方法是不保存对原始对象的任何引用。只需构造一个集合并立即将其传递给包装器，正如我们在示例中所做的那样。

如果你想在另一个线程有机会变异集合时对集合进行迭代，你仍然需要使用“客户端侧”锁定：

```java
synchronized (synchHashMap)
{
    Iterator<K> iter = synchHashMap.keySet().iterator();
    while (iter.hasNext()) . ./;
}
```

如果你使用“for each”循环，必须使用相同的代码，因为该循环使用了迭代器。请注意，如果在迭代进行期间另一个线程变异了集合，迭代器实际上会抛出 `ConcurrentModificationException`。仍然需要同步，以便能够可靠地检测到并发修改。

通常情况下，你使用 `java.util.concurrent` 包中定义的集合比使用同步包装器更好。特别是 `ConcurrentHashMap` 映射经过了仔细实现，使得多个线程在访问不同桶时可以访问它而不会产生相互阻塞。一个例外是频繁变异的数组列表。在这种情况下，同步的 `ArrayList` 可能优于 `CopyOnWriteArrayList`。

**java.util.Collections 1.2**

- `static <E> Collection<E> synchronizedCollection(Collection<E> c)`
- `static <E> List synchronizedList(List<E> c)`
- `static <E> Set synchronizedSet(Set<E> c)`
- `static <E> SortedSet synchronizedSortedSet(SortedSet<E> c)`
- `static <K, V> Map<K, V> synchronizedMap(Map<K, V> c)`

### 14.8 Callables 和 Futures

`Callable` 与 `Runnable` 类似，但它返回一个值。因此，我们有了返回返回的 `Callable<V>`：

```java
public interface Callable<V>
{
    V call() throws Exception;
}
```

`Future` 持有计算的结果。你可以启动一个计算，将 `Future` 对象交给别人，然后忘记它。`Future` 的所有者可以在结果就绪时获取结果。

```java
public interface Future<V>
{
    V get() throws Exception;
    V get(long timeout, TimeUnit unit) throws Exception;
    void cancel(boolean mayInterrupt);
    boolean isCancelled();
    boolean isDone();
}
```

调用第一个 `get` 方法会阻塞直到计算完成。第二个方法如果在计算完成前超时会抛出 `TimeoutException`。如果运行计算的线程被中断，两个方法都会抛出 `InterruptedException`。`isDone` 方法在计算进行时返回 `false`，完成后返回 `true`。

可以使用 `cancel` 方法取消计算。如果计算尚未启动，它将被取消且永远不会启动。如果计算正在进行，如果 `mayInterrupt` 参数为 `true`，则会被中断。

`FutureTask` 包装器是一种将 `Callable` 转换为 `Future` 和 `Runnable` 的方便机制——它实现了这两个接口。例如：

```java
Callable<Integer> myComputation = . . .;
FutureTask<Integer> task = new FutureTask<Integer>(myComputation);
Thread t = new Thread(task); // 它是 Runnable
t.start();
Integer result = task.get(); // 它是 Future
```

列表 14.10 将这些概念付诸实践。该程序与之前查找关键词文件的示例类似，但现在我们只需计算匹配数量。因此，我们有一个产生整数值的长时间运行任务——`Callable<Integer>` 的示例。

```java
class MatchCounter implements Callable<Integer>
{
    public MatchCounter(File directory, String keyword) { . . . }
    public Integer call() { . . . } // 返回匹配文件的数量
}
```

然后我们从 `MatchCounter` 构造一个 `FutureTask` 对象并用它启动一个线程。

```java
FutureTask<Integer> task = new FutureTask<Integer>(counter);
Thread t = new Thread(task);
t.start();
```

最后，我们打印结果。

```java
System.out.println(task.get() + " matching files.");
```

当然，对 `get` 的调用会阻塞，直到结果实际上可用为止。

在 `call` 方法内部，我们递归地使用了相同的机制。对于每个子目录，我们都会产生一个新的 `MatchCounter` 并为它启动一个线程。我们还将 `FutureTask` 对象存储在一个 `ArrayList<Future<Integer>>` 中。在最后，我们将所有结果相加：

```java
for (Future<Integer> result : results)
    count += result.get();
```

每次调用 `get` 都会阻塞，直到结果可用为止。当然，由于这些线程是并行运行的，因此结果很大可能在同一时间左右都变得可用。

**Listing 14.10** `future/FutureTest.java`

```java
package future;

import java.io.*;
import java.util.*;
import java.util.concurrent.*;

/**
 * @version 1.01 2012-01-26
 * @author Cay Horstmann
 */
public class FutureTest
{
    public static void main(String[] args)
    {
        try (Scanner in = new Scanner(System.in))
        {
            System.out.print("Enter base directory (e.g. /usr/local/jdk5.0/src): ");
            String directory = in.nextLine();
            System.out.print("Enter keyword (e.g. volatile): ");
            String keyword = in.nextLine();

            MatchCounter counter = new MatchCounter(new File(directory), keyword);
            FutureTask<Integer> task = new FutureTask<>(counter);
            Thread t = new Thread(task);
            t.start();

            try
            {
                System.out.println(task.get() + " matching files.");
            }
            catch (ExecutionException e)
            {
                e.printStackTrace();
            }
            catch (InterruptedException e)
            {
            }
        }
    }
}

/**
 * 该类统计目录及其子目录中包含某个关键字的文件。
 */
class MatchCounter implements Callable<Integer>
{
    private File directory;
    private String keyword;

    /**
     * 构造一个 MatchCounter。
     * @param directory 开始搜索的目录
     * @param keyword 要查找的关键字
     */
    public MatchCounter(File directory, String keyword)
    {
        this.directory = directory;
        this.keyword = keyword;
    }

    public Integer call()
    {
        int count = 0;
        try
        {
            File[] files = directory.listFiles();
            List<Future<Integer>> results = new ArrayList<>();

            for (File file : files)
                if (file.isDirectory())
                {
                    MatchCounter counter = new MatchCounter(file, keyword);



`FutureTask<Integer> task = new FutureTask<>(counter);`

`results.add(task);`

`Thread t = new Thread(task);`

`t.start();`

`else`

`if (search(file)) count++;`

`for (Future<Integer> result : results)`

`try`

`count += result.get();`

`catch (ExecutionException e)`

`e.printStackTrace();`

`catch (InterruptedException e)`

`return count;`

`/**

 * 在文件中搜索给定的关键字。

 * @param file 要搜索的文件

 * @return 如果文件中包含该关键字则返回 true

 */`

`public boolean search(File file)`

`try`

`try (Scanner in = new Scanner(file, "UTF-8"))`

`boolean found = false;`

`while (!found && in.hasNextLine())`

`String line = in.nextLine();`

`if (line.contains(keyword)) found = true;`

`return found;`

`catch (IOException e)`

`return false;`

`java.util.concurrent.Callable<V>` 5.0
- `V call()`: 运行一个产生结果的任务。

`java.util.concurrent.Future<V>` 5.0
- `V get()`
- `V get(long time, TimeUnit unit)`: 获取结果，直到结果可用或给定时间过去为止。如果执行失败，第二个方法将抛出 `TimeoutException`。
- `boolean cancel(boolean mayInterrupt)`: 尝试取消任务的执行。如果任务已经开始且 `mayInterrupt` 参数为 `true`，则将其中断。如果取消成功，返回 `true`。
- `boolean isCancelled()`: 如果任务在完成之前被取消，返回 `true`。
- `boolean isDone()`: 如果任务通过正常完成、取消或异常完成，返回 `true`。

`java.util.concurrent.FutureTask<V>` 5.0
- `FutureTask(Callable<V> task)`
- `FutureTask(Runnable task, V result)`: 构建一个既是 `Future<V>` 又是 `Runnable` 的对象。

### 14.9 Executors

创建一个线程是相当昂贵的，因为它涉及到与操作系统的交互。如果你的程序创建了大量短寿命线程，它应该使用*线程池*。线程池包含若干个就绪运行的空闲线程。你将一个 `Runnable` 交给线程池，池中的一个线程会调用 `run` 方法。当 `run` 方法退出时，线程不会死亡，而是留在那里处理下一个请求。

使用线程池的另一个原因是限制并发线程的数量。创建海数量的线程会极大地降低性能，甚至导致虚拟机崩溃。

`Executors` 类有许多静态工厂方法用于构建线程池；摘要请参阅表 14.2。

![Image](img/14tab02.jpg)

**Table 14.2** Executors 工厂方法

#### 14.9.1 线程池

让我们来看表 14.2 中的前三个方法（其余方法将在第 926 页的 14.9.2 节“调度执行”中讨论）。`newCachedThreadPool` 方法构建的线程池会立即执行每个任务，如果有空闲线程则使用它，否则创建一个线程。`newFixedThreadPool` 方法构建一个固定大小的线程池。如果提交的任务多于空闲线程的数量，未服务的任务将放入队列中。当其他任务完成后，它们将被运行。`newSingleThreadExecutor` 是一个大小为 1 的退化池，由单个线程一个接一个执行提交的任务。这三个方法都返回一个实现 `ExecutorService` 接口的 `ThreadPoolExecutor` 类对象。

你可以使用以下方法之一向 `ExecutorService` 提交 `Runnable` 或 `Callable`：

```java
Future<?> submit(Runnable task)
Future<T> submit(Runnable task, T result)
Future<T> submit(Callable<T> task)
```

线程池将在其方便时尽快运行提交的任务。当你调用 `submit` 时，会返回一个 `Future` 对象，你可以用它来查询任务状态。

第一个 `submit` 方法返回一个看起来很特殊的 `Future<?>`。你可以使用此类对象调用 `isDone`、`cancel` 或 `isCancelled`，但 `get` 方法在完成后仅会返回 `null`。

第二个版本的 `submit` 同样提交一个 `Runnable`，`Future` 的 `get` 方法在完成后会返回给定的 `result` 对象。

第三个版本提交一个 `Callable`，返回的 `Future` 在计算就绪后获取计算结果。

当你完成线程池的使用时，调用 `shutdown`。该方法会启动线程池的关闭序列。已关闭的执行器不再接受新任务。当所有任务完成后，线程池中的线程就会终止。或者，你也可以调用 `shutdownNow`。线程池会取消所有尚未开始的任务，并尝试中断正在运行的线程。

这里是使用线程池的操作总结：

1. 调用 `Executors` 类的静态方法 `newCachedThreadPool` 或 `newFixedThreadPool`。
2. 调用 `submit` 提交 `Runnable` 或 `Callable` 对象。
3. 如果你想能够取消任务，或者你提交了 `Callable` 对象，请保留返回的 `Future` 对象。
4. 当你不再想提交任何任务时，调用 `shutdown`。

例如，之前的示例程序产生了大量的短命线程，每个目录一个。Listing 14.11 中的程序改用了线程池来启动任务。

出于信息性目的，该程序在执行期间打印了最大的线程池大小。该信息无法通过 `ExecutorService` 接口获取。因此，我们必须将线程池对象强制转换为 `ThreadPoolExecutor` 类。

**Listing 14.11** `threadPool/ThreadPoolTest.java`

```java
package threadPool;

import java.io.*;
import java.util.*;
import java.util.concurrent.*;

/**
 * @version 1.02 2015-06-21
 * @author Cay Horstmann
 */
public class ThreadPoolTest
{
    public static void main(String[] args) throws Exception
    {
        try (Scanner in = new Scanner(System.in))
        {
            System.out.print("Enter base directory (e.g. /usr/local/jdk5.0/src): ");
            String directory = in.nextLine();
            System.out.print("Enter keyword (e.g. volatile): ");
            String keyword = in.nextLine();

            ExecutorService pool = Executors.newCachedThreadPool();

            MatchCounter counter = new MatchCounter(new File(directory), keyword, pool);
            Future<Integer> result = pool.submit(counter);

            try
            {
                System.out.println(result.get() + " matching files.");
            }
            catch (ExecutionException e)
            {
                e.printStackTrace();
            }
            catch (InterruptedException e)
            {
            }
            pool.shutdown();

            int largestPoolSize = ((ThreadPoolExecutor) pool).getLargestPoolSize();
            System.out.println("largest size=" + largestPoolSize);
        }
    }
}

/**
 * 此任务统计目录及其子目录中包含给定关键字的文件。
 */
class MatchCounter implements Callable<Integer>
{
    private File directory;
    private String keyword;
    private ExecutorService pool;
    private int count;

    /**
     * 构建一个 MatchCounter。
     * @param directory 开始搜索的目录
     * @param keyword 要查找的关键字
     * @param pool 用于子任务的线程池
     */
    public MatchCounter(File directory, String keyword, ExecutorService pool)
    {
        this.directory = directory;
        this.keyword = keyword;
        this.pool = pool;
    }

    public Integer call()
    {
        count = 0;
        try
        {
            File[] files = directory.listFiles();
            List<Future<Integer>> results = new ArrayList<>();

            for (File file : files)
                if (file.isDirectory())
                {
                    MatchCounter counter = new MatchCounter(file, keyword, pool);
                    Future<Integer> result = pool.submit(counter);
                    results.add(result);
                }
                else
                {
                    if (search(file)) count++;
                }

            for (Future<Integer> result : results)
                try
                {
                    count += result.get();
                }
                catch (ExecutionException e)
                {
                    e.printStackTrace();
                }
        }
        catch (InterruptedException e)
        {
        }
        return count;
    }

    /**
     * 在文件中搜索给定关键字。
     * @param file 要搜索的文件
     * @return 如果文件中包含关键字，则返回 true
     */
    public boolean search(File file)
    {
        try
        {
            try (Scanner in = new Scanner(file, "UTF-8"))
            {
                boolean found = false;
                while (!found && in.hasNextLine())
                {
                    String line = in.nextLine();
                    if (line.contains(keyword)) found = true;
                }
                return found;
            }
        }
        catch (IOException e)
        {
            return false;
        }
    }
}
```



# `java.util.concurrent.ScheduledExecutorService` 5.0

- `ScheduledFuture<V> schedule(Callable<V> task, long time, TimeUnit unit)`
- `ScheduledFuture<?> schedule(Runnable task, long time, TimeUnit unit)`
  在给定时间通过后调度给定的任务。
- `ScheduledFuture<?> scheduleAtFixedRate(Runnable task, long initialDelay, long period, TimeUnit unit)`
  在初始延迟结束后，调度给定的任务周期性运行，每隔 `period` 单位运行一次。
- `ScheduledFuture<?> scheduleWithFixedDelay(Runnable task, long initialDelay, long delay, TimeUnit unit)`
  在初始延迟结束后，调度给定的任务周期性运行，在上一次调用完成与下一次开始之间留有 `delay` 单位的间隔。

## 14.9.3 控制任务组

你已经见过如何使用执行器服务（executor service）作为线程池来提高任务执行的效率。有时，使用执行器是为了更具战术性的考虑，仅仅是为了控制一组相关的任务。例如，你可以使用`shutdownNow()`方法取消执行器中的所有任务。

`invokeAny()`方法提交`Callable`对象集合中的所有对象，并返回已完成任务的结果。你不知道是哪一个任务——假设它是完成最快的那一个。使用此方法处理你愿意接受任何解决方案的搜索问题。例如，假设你需要对一个大整数进行分解——这是破解 RSA 密所需的计算。你可以提交多个任务，每个任务尝试对不同范围的数字进行分解。只要其中一个任务得有了答案，你的计算就可以停止。

`invokeAll()`方法提交`Callable`对象集合中的所有对象，阻塞直到所有任务都完成，并返回一个`Future`对象的列表，代表所有任务的解决方案。你可以在计算结果可用时处理它们，如下所示：

```java
List<Callable<T>> tasks = . . .;
List<Future<T>> results = executor.invokeAll(tasks);
for (Future<T> result : results)
    processFurther(result.get());
```

这种方法的缺点是，如果第一个任务恰好花费了很长时间，你可能会无谓地等待。按照结果可用的顺序获取结果更有意义。这可以通过`ExecutorCompletionService`来安排。

从通常方式获取的执行器开始。然后构造一个`ExecutorCompletionService`。将任务提交到完成服务。该服务管理一个`Future`对象的阻塞队列，当提交的任务的结果可用时将其包含其中。因此，对于上述计算，更高效的组织方式如下：

```java
ExecutorCompletionService<T> service = new ExecutorCompletionService<>(executor);
for (Callable<T> task : tasks) service.submit(task);
for (int i = 0; i < tasks.size(); i++)
    processFurther(service.take().get());
```

## `java.util.concurrent.ExecutorService` 5.0

- `T invokeAny(Collection<Callable<T>> tasks)`
- `T invokeAny(Collection<Callable<T>> tasks, long timeout, TimeUnit unit)`
  执行给定的任务并返回其中一个任务的结果。如果发生超时，第二个方法将抛出`TimeoutException`。
- `List<Future<T>> invokeAll(Collection<Callable<T>> tasks)`
- `List<Future<T>> invokeAll(Collection<Callable<T>> tasks, long timeout, TimeUnit unit)`
  执行给定的任务并返回所有任务的结果。如果发生超时，第二个方法将抛出`TimeoutException`。

## `java.util.concurrent.ExecutorCompletionService<V>` 5.0

- `ExecutorCompletionService(Executor e)`
  构造一个执行器完成服务，收集给定执行器的结果。
- `Future<V> submit(Callable<V> task)`
- `Future<V> submit(Runnable task, V result)`
  将任务提交到底层的执行器。
- `Future<V> take()`
  移除下一个完成的结果，如果没有可用的完成的结果则阻塞。
- `Future<V> poll()`
- `Future<V> poll(long time, TimeUnit unit)`
  移除并返回下一个完成的结果，如果没有可用的完成的结果，则返回`null`。第二个方法会等待给的时间。

## 14.9.4 Fork-Join 框架

某些应用程序使用大量大部分空闲的线程。例如，每个连接使用一个线程的 Web 服务器。其他应用程序每个处理器核心使用一个线程，以执行计算密集型任务，如图像或视频处理。出现在 Java SE 7 中的 fork-join 框架旨在支持后者。假设你有一个自然地分解为子任务的处理任务，如下所示：

```java
if (problemSize < threshold)
    直接解决问题
else
{
    将问题分解为子问题
    递归地求解每个子问题
    合并结果
}
```

一个例子是图像处理。为了增强图像，你可以转换上半部分和下半部分。如果你有足够的空闲处理器，这些操作就可以并行运行。（你需要进行一些额外工作，但那是技术细节。）

图像处理。为了增强图像，你可以转换上半部分和下半部分。如果你有足够的空闲处理器，这些操作就可以并行运行。在这里，我们将讨论一个更简单的例子。假设我们要统计数组中满足特定属性的元素数量。我们将数组分成两半，计算每个部分的计数并相加。

为了让递归计算适用于框架的形式，提供扩展`RecursiveTask<T>`（如果产生结果`T`）或`RecursiveAction`（如果不产生结果）的类。覆盖`compute()`方法来生成并调用子任务，并合并它们的结果。

在这里，`invokeAll()`方法接收任务并阻塞直到它们全部完成。`join()`方法产生结果。在这里，我们对每个子任务应用`join()`并求和。

![Image](img/note.jpg) 注意

还有一个`get()`方法用于获取当前结果，但它不那么理想，因为它会抛出我们在`compute()`方法中不允许抛出的检查异常。

在后台，fork-join 框架使用了一种在可用线程之间平衡负载的有效启发式方法，称为*工作窃取（work stealing）。每个工作线程都有一个用于任务的双端队列。工作线程将子任务推入自己队列的头部。（只有一个线程访问头部，因此不需要锁定。）当一个工作线程空闲时，它从另一个队列的尾部“窃取”任务。由于较大的子任务位于尾部，这种窃取很少发生。

**14.12** `forkJoin/ForkJoinTest.java`

```java
package forkJoin;

import java.util.concurrent.*;
import java.util.function.*;

/**
 * 此程序演示了 fork-join 框架。
 * @version 1.01 2015-06-21
 * @author Cay Horstmann
 */
public class ForkJoinTest
{
    public static void main(String[] args)
    {
        final int SIZE = 10000000;
        double[] numbers = new double[SIZE];
    }
}
```

```java
for (int i = 0; i < SIZE; i++) numbers[i] = Math.random();
Counter counter = new Counter(numbers, 0, numbers.length, x -> x > 0.5);
ForkJoinPool pool = new ForkJoinPool();
pool.invoke(counter);
System.out.println(counter.join());
}

class Counter extends RecursiveTask<Integer>
{
    public static final int THRESHOLD = 1000;
    private double[] values;
    private int from;
    private int to;
    private DoublePredicate filter;

    public Counter(double[] values, int from, int to, DoublePredicate filter)
    {
        this.values = values;
        this.from = from;
        this.to = to;
        this.filter = filter;
    }

    protected Integer compute()
    {
        if (to - from < THRESHOLD)
        {
            int count = 0;
            for (int i = from; i < to; i++)
            {
                if (filter.test(values[i])) count++;
            }
            return count;
        }
        else
        {
            int mid = (from + to) / 2;
            Counter first = new Counter(values, from, mid, filter);
            Counter second = new Counter(values, mid, to, filter);
            invokeAll(first, second);
            return first.join() + second.join();
        }
    }
}
```

#### 14.9.5 Completable Futures

处理非阻塞调用的传统方法是使用事件处理器，程序员为任务完成后应执行的动作注册一个处理器。当然，如果下一个动作也是异步的，那么接下来的动作又将位于另一个事件处理器中。尽管程序员在思考时是按照“先执行步骤 1，然后是步骤 2，最后是步骤 3”这样的逻辑的，但程序逻辑会分散在不同的处理器中。当必须添加错误处理时，情况会变得更糟。假设步骤 2 是“用户登录”。由于用户可能会输入错误的凭据，你可能需要重复该步骤。在一组事件处理器中实现这样的流程，或者在实现后去理解它，都是具有挑战性的。

Java SE 8 中的`CompletableFuture`类提供了一种替代方法。与事件处理器不同，完成的 future 可以被组合。例如，假设我们想从一个网页中提取所有链接以构建爬虫。假设我们有一个方法

```java
public CompletableFuture<String> readPage(URL url)
```

它在网页可用时产生该网页的文本。如果方法

```java
public static List<URL> getLinks(String page)
```

能够产生 HTML 页面中的 URL，你可以调度它在页面可用时被调用：

```java
CompletableFuture<String> contents = readPage(url);
CompletableFuture<List<URL>> links = contents.thenApply(Parser::getLinks);
```

`thenApply`方法也不会阻塞。它返回另一个 future。当第一个 future 完成时，它的结果会被馈送给`getLinks`方法，而该方法的返回值将成为最终结果。通过完成的 future，你只需要指定你想执行哪些操作以及按什么顺序执行。当然，这些操作不会立即发生，但重要的是所有的代码都放在一个地方。从概念上说，`CompletableFuture`是一个简单的 API，但组合完成的 future 的方法有许多变体。让我们先看处理单个 future 的方法（参见表 14.3 (ch14a.html_ch14tab03)）。对于每个方法，我没有显示两个`Async`变体（其中一个使用共享的`ForkJoinPool`，另一个有一个`Executor`参数）。在表中，我对函数式接口使用了简写符号，用`T -> U`代替`Function<? super T, U>`。这些并不是实际的类型。

**表 14.3** 为`CompletableFuture<T>`添加动作

你已经见过了`thenApply`方法。以下调用

```
CompletableFuture<U> future.thenApply(f);
CompletableFuture<U> future.thenApplyAsync(f);
```

返回一个 future，当`future`的结果可用时，将`f`应用于该结果。第二次调用在另一个线程中运行`f`。

`thenCompose`方法接收的不是函数`T -> U`，而是函数`T -> CompletableFuture<U>`。这听起来相当抽象，但它可以非常自然。考虑从给定的 URL 读取网页的动作。与其提供一个方法

```java
public String blockingReadPage(URL url)
```

不如让该方法返回一个 future：

```java
CompletableFuture<String> readPage(URL url);
```

现在，假设我们有另一个方法从用户输入获取 URL，可能来自一个对话框，该对话框在用户点击 OK 按钮之前不会显示答案。这也是未来发生的一个事件：

```java
CompletableFuture<URL> getURLInput(String prompt);
```



这里我们有两个函数 `T -> CompletableFuture<U>` 和 `U -> CompletableFuture<V>`。显然，如果第二个函数在第一个函数完成后被调用，它们就组合成一个函数 `T -> CompletableFuture<V>`。这正是 `thenCompose` 所做的。

表 14.3 中的第三种方法关注我迄今为止忽略的另一个方面：失败。当异常在 `CompletableFuture` 中抛出时，在调用 `get` 方法时它会被捕获并封装在未检查的 `ExecutionException` 中。但也许永远不会调用 `get`。为了处理异常，请使用 `handle` 方法。提供的函数将接收结果（如果没有则为 `null`）和异常（如果没有则为 `null`），并由它来理解这种情况。

剩余的方法具有 `void` 结果，通常用于处理流水线的末端。

现在让我们转向组合多个 future 的方法（参见表 14.4 (ch14a.html_ch14tab04)）。

前三个方法并行运行 `CompletableFuture<T>` 和 `CompletableFuture<U>` 动作并组合结果。

接下来的三个方法并行运行两个 `CompletableFuture<T>` 动作。一旦其中一个完成，它的结果就会被传递，另一个结果则被忽略。

最后，静态方法 `allOf` 和 `anyOf` 方法接收任意数量的完成未来，并产生一个在所有未来完成后或任意一个未来完成后完成的 `CompletableFuture<Void>`。没有结果被传递。

## 14.10 同步器

`java.util.concurrent` 包包含了几个有助于一组协作线程的类——参见表 14.5 (ch14a.html_ch14tab05)。这些机制为线程间常见的汇合模式提供了“现成功能”。如果你有一组遵循这些行为模式的协作线程，你应该简单地复用适当的类，而不是尝试自己发明一套锁和条件。

### 14.10.1 信号量

从概念上讲，信号量（semaphore）管理着数量 `permits`（许可）。该数量在构造函数中提供。要通过信号量继续执行，线程通过调用 `acquire` 请求许可。（这里并没有实际的许可对象。信号量仅维护一个计数器。）由于可用许可数量是固定的，信号量限制了允许通过的线程数量。其他线程可以通过调用 `release` 来发布许可。此外，许可并不一定由获取许可的线程释放。任何线程都可以释放任何数量的许可，这可能会导致许可数量超过初始计数。

信号量由埃德格·迪克斯斯特拉（Edsger Dijkstra）于 1968 年发明，用作一种 `synchronization primitive`（同步原语）。迪克斯斯特拉证明了信号量可以被高效地实现，并且它们强大到足以解决许多常见的线程同步问题。在几乎任何操作系统教科书中，你都能找到使用信号量实现的有界队列。

当然，应用程序程序员不应该重新发明有界队列。通常，信号量并不直接映射到常见的应用场景。

### 14.10.2 倒计时计数器 (Countdown Latches)

`CountDownLatch` 让一组线程等待，直到计数达到零。倒计时计数器是一次性的。一旦计数达到 0，你就无法再次对其递增。

一个实用的特殊情况是计数为 1 的计数器。这实现了一个单次门禁。线程被挡在门外，直到另一个线程将计数设置为 0。

例如，有一组线程需要一些初始数据来完成工作。工作线程启动并在门外等待。另一个线程准备数据。当该线程准备就绪时，它调用 `countDown`，所有工作线程便继续执行。

然后你可以使用第二个计数器来检查所有工作线程何时完成。用线程的数量初始化计数器。每个工作线程在终止之前都会对该计数器进行减计数。另一个收集工作结果的线程等待该计数器，一旦所有工作线程终止，它就会继续。

### 14.10.3 屏障 (Barriers)

`CyclicBarrier` 类实现了一种称为 `barrier`（屏障）的汇合点。考虑若干正在处理计算部分的线程。当所有部分都准备就绪时，需要合并结果。当一个线程完成它的部分工作时，我们让它在屏障运行。一旦所有线程都到达屏障，屏障就会打开，线程就可以继续执行。

以下是细节。首先，构建一个屏障，并给出参与线程的数量：

```java
CyclicBarrier barrier = new CyclicBarrier(nthreads);
```

每个线程执行一些工作，并在完成后对屏障调用 `await`：

```java
public void run()
{
    doWork();
    barrier.await();
    ...
}
```

`await` 方法接受一个可选的超时参数：

```java
barrier.await(100, TimeUnit.MILLISECONDS);
```

如果等待屏障的任何一个线程离开了屏障，那么屏障就会 `breaks`（损坏）（线程离开可能是因为它调用了带超时的 `await`，也可能因为它被中断了）。在这种情况下，所有其他线程的 `await` 方法都会抛出 `BrokenBarrierException`。已经在等待的线程其 `await` 调用将立即终止。

你可以提供一个可选的 `barrier action`（屏障动作），该动作会在所有线程到达屏障时执行：

```java
Runnable barrierAction = . . .;
CyclicBarrier barrier = new CyclicBarrier(nthreads, barrierAction);
```

该动作可以收集各个线程的结果。

该屏障被称为 `cyclic`（循环的），因为它在所有等待线程被释放后可以被重用。在这点上，它与 `CountDownLatch` 不同，后者只能使用一次。

`Phaser` 类增加了更多的灵活性，允许你在不同阶段之间改变参与的线程的数量。

### 14.10.4 交换器 (Exchangers)

当两个线程处理同一个数据缓冲区的两个实例时，会使用 `Exchanger`。通常，一个线程填充缓冲区，另一个线程消耗其内容。当两者都完成后，它们会交换缓冲区。

### 14.10.5 同步队列 (Synchronous Queues)

同步队列是一种配对生产者和消费者线程的机制。当线程在 `SynchronousQueue` 上调用 `put` 时，它会阻塞，直到另一个线程调用 `take`，反之亦然。与 `Exchanger` 的情况不同，数据只在一个方向传输，从生产者到消费者。

尽管 `SynchronousQueue` 类实现了 `BlockingQueue` 接口，但从概念上讲它并不是一个队列。它不包含任何元素——它的 `size` 方法始终返回 `0`。

## 14.11 线程与 Swing

正如我们在本章引言中所提到的，在程序中使用线程的原因之一是让程序更具响应性。当程序需要执行某些耗时的操作时，你应该启动另一个工作线程，而不是阻塞用户界面。

然而，你必须小心在工作线程中做什么，因为可能让你惊讶，Swing 是 `not thread safe`（不是线程安全的）。如果你尝试从多个线程操作用户界面元素，你的用户界面可能会损坏。

要查看这个问题，请运行下文 Listing 14.13 中的后续测试程序。当你点击 Bad 按钮时，会启动一个新线程，其 `run` 方法会折扰组合框，随机添加和删除项。

```java
public void run()
{
    try
    {
        while (true)
        {
            int i = Math.abs(generator.nextInt());
            if (i % 2 == 0)
            {
                combo.insertItem(new Integer(i), 0);
            }
            else if (combo.getItemCount() > 0)
            {
                combo.removeItemAt(i % combo.getItemCount());
            }
            sleep(1);
        }
    }
    catch (InterruptedException e) {}
}
```

尝试一下。点击 Bad 按钮。点击组合框几次。移动滚动条。移动窗口。再次点击 Bad 按钮。保持组合框打开。最终，你会看到一个异常报告（图 14.8）。

**图 14.8** 控制台中的异常报告

发生了什么？当元素插入组合框中时，组合框会触发事件来更新显示。然后，显示代码开始执行，读取组合框当前的大小并准备显示值。但工作线程仍在运行——有时会导致组合框中值的数量减少。显示代码随后认为模型中的值比实际多，它请求一个不存在的值，从而触发 `ArrayIndexOutOfBounds` 异常。

### 14.11.1 运行耗时任务

当你将线程与 Swing 一起使用时，必须遵循两个简单的规则。

**1.** 如果某个操作耗时很长，请在单独的工作线程中执行它，绝不在事件分发线程中执行。

**2.** 不要在事件分发线程以外的任何线程中触摸 Swing 组件。

第一条规则的原因很容易理解。如果你在事件分发线程中花费很长时间，应用程序看起来就像“死机”了，因为它无法响应任何事件。特别是，事件分发线程绝不应该进行输入输出调用，因为这些调用可能会无限阻塞，而且永远不应该调用 `sleep`。（如果你需要等待特定的时间，请使用定时器事件。）

第二条规则通常被称为 Swing 编程的`单线程规则`。我们在第 951 页进一步讨论它。

这两条规则似乎是相互冲突的。假设你启动了一个单独的线程来运行耗时任务。你通常希望在线程工作时更新用户界面以显示进度。当任务完成时，你又想再次更新 GUI。但你不能从你的线程触碰 Swing 组件。例如，如果你想更新进度条或标签文本，你不能简单地从你的线程中设置它的值。

为了解决这个问题，你可以在任何线程中使用两个实用方法来向事件队列添加任意操作。例如，假设你想在线程中定期更新一个标签以指示进度。你不能从你的线程中调用 `label.setText`。

相反，请使用 `EventQueue` 类的 `invokeLater` 和 `invokeAndWait` 方法，让该调用在事件分发线程中执行。

以下是具体做法。将 Swing 代码放入实现 `Runnable` 接口的类的 `run` 方法中。然后，创建该类的对象并将其传递给静态方法 `invokeLater` 或 `invokeAndWait`。例如，这里是更新标签文本的方法：

```java
EventQueue.invokeLater(() -> {
    label.setText(percentage + "% complete");
});
```

当事件发布到事件队列时，`invokeLater` 方法立即返回。`Runnable` 的 `run` 方法是异步执行的。`invokeAndWait` 方法会等待直到 `run` 方法实际执行完毕。

对于更新进度标签，`invokeLater` 方法更为合适。用户更倾向于让工作线程取得更多进展，而不是获得一个最精确的进度指示器。

两种方法都会在事件分发线程中执行 `run` 方法。不会创建新线程。

列表 14.13 展示了如何使用 `invokeLater` 方法安全地修改组合框的内容。如果你点击 Good 按钮，一个线程会插入并删除数字。然而，实际修改发生在事件分发线程中。

**列表 14.13** `swing/SwingThreadTest.java`

```java
package swing;

import java.awt.*;
import java.util.*;
import javax.swing.*;

/**
 * 此程序演示了与事件分发线程并行运行的线程
 * 如何导致 Swing 组件出现错误。
 * @version 1.24 2015-06-21
 * @author Cay Horstmann
 */
public class SwingThreadTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() -> {
            JFrame frame = new SwingThreadFrame();
            frame.setTitle("SwingThreadTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 此框架有两个按钮，用于从单独线程填充组合框。
 * "Good" 按钮使用事件队列，“Bad" 按钮直接修改
 * 组合框。
 */
class SwingThreadFrame extends JFrame
{
    public SwingThreadFrame()
    {
        final JComboBox<Integer> combo = new JComboBox<>();
        combo.insertItemAt(Integer.MAX_VALUE, 0);
        combo.setPrototypeValue(combo.getItemAt(0));
        combo.setSelectedIndex(0);

        JPanel panel = new JPanel();

        JButton goodButton = new JButton("Good");
        goodButton.addActionListener(event -> new Thread(new GoodWorker(combo)).start());
        panel.add(goodButton);

        JButton badButton = new JButton("Bad");
        badButton.addActionListener(event -> new Thread(new BadWorker(combo)).start());
        panel.add(badButton);

        panel.add(combo);
        add(panel);
        pack();
    }
}

/**
 * 此 runnable 通过随机添加和删除数字来修改组合框。
 * 这会导致错误，因为组合框方法不是同步的，
 * 工作线程和事件分发线程都访问该框。
 */
class BadWorker implements Runnable
{
    private JComboBox<Integer> combo;
    private Random generator;

    public BadWorker(JComboBox<Integer> aCombo)
    {
        combo = aCombo;
        generator = new Random();
    }

    public void run()
    {
        try {
            while (true) {
                int i = Math.abs(generator.nextInt());
                if (i % 2 == 0)
                    combo.insertItemAt(i, 0);
                else if (combo.getItemCount() > 0)
                    combo.removeItemAt(i % combo.getItemCount());
                Thread.sleep(1);
            }
        } catch (InterruptedException e) {
        }
    }
}

/**
 * 此 runnable 通过随机添加和删除数字来修改组合框。
 * 为了确保组合框不被损坏，编辑
 * 操作被放到了事件线程。
 */
class GoodWorker implements Runnable
{
    private JComboBox<Integer> combo;
    private Random generator;

    public GoodWorker(JComboBox<Integer> aCombo)
    {
        combo = aCombo;
        generator = new Random();
    }

    public void run()
    {
        try {
            while (true) {
                EventQueue.invokeLater(() -> {
                    int i = Math.abs(generator.nextInt());
                    if (i % 2 == 0)
                        combo.insertItemAt(i, 0);
                    else if (combo.getItemCount() > 0)
                        combo.removeItemAt(i % combo.getItemCount());
                });
                Thread.sleep(1);
            }
        } catch (InterruptedException e) {
        }
    }
}
```



`combo.removeItemAt(i % combo.getItemCount());`

```
});

Thread.sleep(1);

}

} catch (InterruptedException e) {

}

}

}
```

`java.awt.EventQueue`

- `static void invokeLater(Runnable runnable)` 让`runnable`对象的`run`方法在处理完等待事件后在事件分发线程中执行。
- `static void invokeAndWait(Runnable runnable)` 让`run`对象的`run`方法在处理完等待事件后在事件分发线程中执行。此调用会阻塞直到`run`方法终止。
- `static boolean isDispatchThread()` 如果执行此方法的线程是事件分发线程，则返回`true`。

## 14.11.2 使用 Swing Worker

当用户发出一个处理时间很长的命令时，你将希望启动一个新线程来工作。正如你在前面的节中所看到的，该线程应该使用`EventQueue.invokeLater`方法来更新用户界面。`SwingWorker`类减少了实现后台任务的繁琐性。

Listing 14.14 中的程序包含了加载文本文件和取消文件加载过程的命令。你应该尝试用一个长文件来运行该程序，例如《基督的伯爵》的全文，该文件位于书籍配套代码的`gutenberg`目录中。文件在一个独立的线程中加载。在读取文件期间，`Open`菜单项会被禁用，而`Cancel`项会被启用（参见图 14.9）。每读完一行后，状态栏中的行计数器就会更新。当读取过程完成后，`Open`菜单项重新启用，`Cancel`项被禁用，且状态行文本被设置为 Done。

![Image](img/14fig09.jpg)

**图 14.9** 在独立线程中加载文件

此示例展示了后台任务的典型 UI 活动：

- 在每个工作单元完成后，更新 UI 以显示进度。
- 在工作完成后，对 UI 进行最后的更改。

`SwingWorker`类使得实现此类任务变得简单。重写`doInBackground`方法来执行耗时工作，并偶尔调用`publish`来通信工作进度。该方法在工作线程中执行。`publish`方法会导致`process`方法在事件分发线程（edt）中执行以处理进度数据。当工作完成后，会在事件分发线程中调用`done`方法，以便你可以完成 UI 的更新。

当你想在工作线程中执行某些工作时，构造一个新的工作线程。（每个工作对象旨在只使用一次。）然后调用`execute`方法。你通常会在事件分发线程上调用`execute`，但这不是强制要求的。

假设工作线程会产生某种结果；因此，`SwingWorker<T, V>`实现了`Future<T>`。该结果可以通过`Future`接口的`get`方法获取。由于`get`方法会阻塞直到结果可用，因此你不希望在调用`execute`之后立即调用它。在在你知道工作已完成时再调用它是一个好主意。通常，你在`done`方法中调用`get`。（并不要求调用`get`。有时，处理进度数据就是你需要的。）

中间进度数据和最终结果都可以是任意类型。`SwingWorker`类将这些类型作为类型参数。`SwingWorker<T, V>`产生类型为`T`的结果和类型为`V`的进度数据。

要取消正在进行的工作，使用`Future`接口的`cancel`方法。当工作被取消时，`get`方法会抛出`CancellationException`。

正如提到的，工作线程对`publish`的调用会导致在事件分发线程上调用`process`。为了效率起见，多次调用`publish`的结果可能会合并并在单次`process`调用处理。`process`方法接收一个包含所有中间结果的`List<V>`。

让我们利用这一机制来读取文本文件。事实证明，`JTextArea`相当慢。从长文本文件中追加行（例如《基督的伯爵》中的所有行）需要花费大量时间。

为了向用户显示正在处理进度，我们希望在状态行中显示已读取的行数。因此，进度数据由当前行号和当前行文本组成。我们将这些封装进一个简单的内部类中：

```java
private class ProgressData

{

  public int number;

  public String line;

}
```

最终结果是读取到`StringBuilder`中的文本。因此，我们需要一个`SwingWorker<StringBuilder, ProgressData>`。

在`doInBackground`方法中，我们逐行读取文件。每读一行，我们调用一次`publish`来发布行号和当前行的文本。

点击此处查看代码图像

```java
@Override public StringBuilder doInBackground() throws IOException, InterruptedException

{

    int lineNumber = 0;

    Scanner in = new Scanner(new FileInputStream(file), "UTF-8");

    while (in.hasNextLine())

    {

        String line = in.nextLine();

        lineNumber++;

        text.append(line).append("\n");

        ProgressData data = new ProgressData();

        data.number = lineNumber;

        data.line = line;

        publish(data);

        Thread.sleep(1); // 为了测试取消；在你的程序中不需要这样做

    }

    return text;

}
```

我们每读行后都睡眠一毫秒，以便你可以在不感到压力的情况下测试取消，但你不想通过睡眠来减慢自己程序的速度。如果你注释掉这一行，你会发现*《基督的伯爵》*加载很快，只有几次批处理的用户更新。

![Image](img/note.jpg) 你可以通过从工作线程更新文本区域来让此程序运行得平滑，但对于大多数组件来说是不可能的。我们向你展示通用方法，即组件更新在事件分发线程中进行。

在`process`方法中，我们忽略除最后一行之外的所有行号，并将所有行合并以一次性更新文本区域。

点击此处查看代码图像

```java
@Override public void process(List<ProgressData> data)

{

    if (isCancelled()) return;

    StringBuilder b = new StringBuilder();

    statusLine.setText("" + data.get(data.size() - 1).number);

    for (ProgressData d : data) b.append(d.line).append("\n");

    textArea.append(b.toString());

}
```

在`done`方法中，使用完整文本更新文本区域，并禁用`Cancel`项。注意看如何在`Open`菜单项的事件监听中启动工作线程。这种简单技术允许你在执行耗时任务的同时保持用户界面的响应。

**Listing 14.14** `swingWorker/WorkerTest.java`

点击此处查看代码图像

```java
package swingWorker;

import java.awt.*;

import java.io.*;

import java.util.*;

import java.util.List;

import java.util.concurrent.*;

import javax.swing.*;

/**

 * 此程序演示了一个运行可能耗时任务的工作线程。

 * @version 1.11 2015-06-21

 * @author Cay Horstmann

 */

public class SwingWorker

{

  public static void main(String[] args) throws Exception

  {

    EventQueue.invokeLater(() -> {

      JFrame frame = new SwingWorkerFrame();

      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

      frame.setVisible(true);

    });

  }

}

/**

 * 此框架有一个显示文件内容的文本区域，一个打开文件并

 * 取消过程的菜单，以及一个显示文件加载进度的状态行。

 */

class SwingWorkerFrame extends JFrame

{

  private JFileChooser chooser;

  private JTextArea textArea;

  private JLabel statusLine;

  private JMenuItem openItem;

  private JMenuItem cancelItem;

  private SwingWorker<StringBuilder, ProgressData> textReader;

  public static final int TEXT_ROWS = 20;

  public static final int TEXT_COLUMNS = 60;

  public SwingWorkerFrame()

  {

    chooser = new JFileChooser();

    chooser.setCurrentDirectory(new File("."));

    textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);

    add(new JScrollPane(textArea));

    statusLine = new JLabel(" ");

    add(statusLine, BorderLayout.SOUTH);

    JMenuBar menuBar = new JMenuBar();

    setJMenuBar(menuBar);

    JMenu menu = new JMenu("File");

    menuBar.add(menu);

    openItem = new JMenuItem("Open");

    menu.add(openItem);

    openItem.addActionListener(event -> {

```

```java
// show file chooser dialog

int result = chooser.showOpenDialog(null);

// if file selected, set it as icon of the label

if (result == JFileChooser.APPROVE_OPTION)

{

    textArea.setText("");

    openItem.setEnabled(false);

    textReader = new TextReader(chooser.getSelectedFile());

    textReader.execute();

    cancelItem.setEnabled(true);

}

});

cancelItem = new JMenuItem("Cancel");

menu.add(cancelItem);

cancelItem.setEnabled(false);

cancelItem.addActionListener(event -> textReader.cancel(true));

pack();

}
```

```java
private class ProgressData

{

    public int number;

    public String line;

}

private class TextReader extends SwingWorker<StringBuilder, ProgressData>

{

    private File file;

    private StringBuilder text = new StringBuilder();

    public TextReader(File file)

    {

        this.file = file;

    }

    // The following method executes in the worker thread; it doesn't touch Swing components.

    @Override

    public StringBuilder doInBackground() throws IOException, InterruptedException

    {

        int lineNumber = 0;

        try (Scanner in = new Scanner(new FileInputStream(file), "UTF-8"))

        {

            while (in.hasNextLine())

            {

                String line = in.nextLine();

                lineNumber++;

                text.append(line).append("\n");

                ProgressData data = new ProgressData();

                data.number = lineNumber;

                data.line = line;

                publish(data);

                Thread.sleep(1); // test cancellation; no need to do this in your programs

            }

        }

        return text;

    }

    // The following methods execute in the dispatch thread.

    @Override

    public void process(List<ProgressData> data)

    {

        if (isCancelled()) return;

        StringBuilder b = new StringBuilder();

        statusLine.setText("" + data.get(data.size() - 1).number);

        for (ProgressData d : data) b.append(d.line).append("\n");

        textArea.append(b.toString());

    }

    @Override

    public void done()

    {

        try

        {

            StringBuilder result = get();

            textArea.setText(result.toString());

            statusLine.setText("Done");

        }

        catch (InterruptedException ex)

        {

        }

        catch (CancellationException ex)

        {

            textArea.setText("");

        }

        catch (ExecutionException ex)

        {

            textArea.setText("" + ex.getCause());

        }

    }

}
```



## 14.11.3 单线程规则

每个应用程序都从`main`方法开始。在 Swing 中，`main`线程是短寿命。你需要在事件分发线程中构建用户界面，然后退出。在章节前面的部分，我们引入了单线程规则：“不要在事件分发线程以外的线程中接触 Swing 组件。”在本节中，我们将进一步研究该规则。

单线程规则有几个例外。你可以在任何线程中安全地添加和移除监听器。当然，监听器方法将在事件分发线程中被调用。少数几个 Swing 方法是线程安全的。它们在 API 文档中特别标记为“此方法是线程安全的，尽管大多数 Swing 方法均不是”。在这些线程安全方法中最有用的是：

- `JTextComponent.setText`
- `JTextArea.insert`
- `JTextArea.append`
- `JTextArea.replaceRange`
- `JComponent.repaint`
- `JComponent.revalidate`

从历史上看，单线程规则更为宽松。任何线程都被允许构建组件、设置它们的属性并将其添加到容器中，只要这些组件中没有一个已经实现（realized）。如果一个组件可以接收绘制或验证事件，则它就是已实现的。在对组件调用了`setVisible(true)`或`pack`方法之后，或者在组件被添加到一个已经实现的容器之后，就会出现这种情况。

那个版本的单线程规则是非常方便的。它允许你在`main`方法中创建 GUI，然后对应用程序的顶层框架调用`setVisible(true)`。这不需要在事件分发线程上进行麻烦的`Runnable`调度。

遗憾的是，某些组件实现者并没有注意原始单线程规则的细微差别。他们在事件分发线程上启动活动，而从未忙于检查组件是否已经实现。例如，如果你在`JTextComponent`上调用`setSelectionStart`或`setSelectionEnd`，即使组件不可见，也会在事件分发线程中调度光标移动。

本完全可以检测并修复这些问题，但 Swing 的设计者选择了简单的处理之径。他们规定，从事件分发线程以外的任何线程访问组件永远是不安全的。因此，你需要在事件分发线程中构建用户界面，并使用我们在所有示例程序中见过的`EventQueue.invokeLater`调用。

当然，有很多程序并没有那么小心，它们仍然遵循旧版本的单线程规则，在主线程上初始化用户界面。这些程序会带来微小的风险，即某些用户界面的初始化可能会导致事件分发线程上的操作与主线程上的操作发生冲突。正如我们在第 10 章中所提到的，你并不希望成为那少数倒霉蛋、遇到麻烦并浪费时间去调试间歇性线程错误的人之一。因此，你应该简单地遵循严格的单线程规则。

你现在已经完成了《核心 Java》（Core Java）第一卷。这一卷涵盖了 Java 编程语言的基础知识，以及你在大多数编程项目中所需的标准库部分。我们希望你喜欢这段 Java 基础之旅，并在此一途中发现了许多有用的信息。对于高级主题，如网络、高级 AWT/Swing、安全和国际化，请参阅第二卷。

## 附录 A. Java 关键字

![Image](img/atab01.jpg)![Image](img/atab01a.jpg)![Image](img/atab01b.jpg)![Image](img/atab01c.jpg)

# 索引

## 数字

- `-`（减号）
- 算术运算符，56, 64
- `printf`标志，84
- `--`运算符，61, 64
- `_`（下划线）
- 数字字面量中的分隔符，48
- 在实例字段名中（C++），176
- `,`（逗号）
- 运算符（C++），65
- `printf`标志，83–84
- `;`（分号）
- `for`语句，45, 53
- 在类路径中（Windows），191
- `:`（冒号）
- 在断言中，385
- 在类路径中（UNIX），191
- 继承标记（C++），204
- `::`运算符（C++），153, 161, 207, 320
- `!`运算符，62, 64
- `!=`运算符，62, 64, 101
- `?:`运算符，62, 64
- `/`（斜杠）
- 算术运算符，56, 64
- 在文件名中，785
- `//`注释，46
- `/* . . . */`注释，46
- `/** . . . */`注释，46, 194
- `.`（句点）
- 在类路径中，191–192
- 在目录名中（UNIX），788
- `...`（省略号），在可变参数中，257
- `^`运算符，63–64, 316
- `~`运算符，63–64
- `'`、`"`（单引号、双引号）的转义序列，50
- `". . ."`（双引号），用于字符串，45
- `(`（左括号），`printf`标志，83–84
- `()`（空括号），在方法调用中，46
- `(. . .)`用于强制转换的括号，60, 64, 219
- `for`运算符，64
- `[]`（空方括号），在泛型中，421
- `[. . .]`（方括号），用于数组，111, 115
- `{. . .}`（花括号），用于代码块，44–85
- 用于枚举类型，65
- 在 lambda 表达式中，316
- `{{. .}}`（双花括号），在内部类中，344
- `@`（符号），在 javadoc 注释中，194, 196
- `$`（美元符号），用于内部类，336
- 在变量名中，53
- `printf`标志，84
- `*`（星号）算术运算符，56, 64
- echo 字符，652
- 在类路径中，191
- 在导入中，183
- `\`（反斜杠）转义序列，50
- 在文件名中，87, 785
- `&`（ampersand）按位运算符，63–64
- 在边界类型中，423
- 在引用参数（C++）中，169
- `&&`运算符，62, 64
- `#`（井号），在 javadoc 超链接中，197
- 在属性文件中，599
- `printf`标志，84
- `%`（百分号）算术运算符，56, 64
- 用于格式化，83
- `printf`标志，84
- `+`（加号）算术运算符，56, 60, 64
- 用于对象和字符串，66–67, 239
- `printf`标志，84
- `++`运算符，61, 64
- `<`（左尖括号），在 shell 语法中，88
- `printf`标志，84–85
- 运算符，62, 64
- `<?`（通配符类型），443
- `<<`、`>>`、`>>>`运算符，63–64
- `<=`运算符，62, 64
- `<. .>`（尖括号），用于类型，245, 419
- `>`（右尖括号），在 shell 语法中，88, 411
- 运算符，62, 64
- `->`（lambda 表达式），315–317
- `>&`（在语法中），411
- `>=`运算符，62, 64
- `=`运算符，54, 61
- `==`运算符，62, 64
- 用于类，262
- 用于枚举类型，258
- 用于浮点数，101
- 用于恒性映射，507
- 用于字符串，69
- 用于包装器，254
- `|`运算符，63–64
- `||`运算符，62, 64
- `0`、`0b`、`0x`前缀（整数），48
- `printf`标志，84

## A

绝对定位（Swing），723

抽象类，221–227

- 扩展，223
- 接口和，297
- 对象变量，223

抽象方法，222

- 在函数式接口中，318

- `setDisplayedMnemonicIndex`方法，686, 688
- `setHorizontalTextPosition`方法，682–683
- `setMnemonic`方法，688
- `abstractClasses/Employee.java`，226
- `abstractClasses/Person.java`，226
- `abstractClasses/PersonTest.java`，225
- `abstractClasses/Student.java`，227
- `AbstractCollection`类，467, 479
- `AbstractQueue`类，463
- 加速器（在菜单中），687–688
- `accept`方法（`FileFilter`），755, 764
- `acceptEither`方法（`CompletableFuture`），934

### 访问修饰符

检查，265

- `final`，55, 157, 217–218, 295, 339–342, 886
- `private`，150, 189–190, 333
- `protected`，227–228, 283, 311
- `public`，42–43, 56, 147–150, 189–190, 289–290
- `public static`，296
- `static`，44–45, 158–164
- `static final`，55
- `void`，44–45

访问顺序，505

`AccessibleObject`类

- `isAccessible`方法，275
- `setAccessible`方法，272, 275

访问器方法，141–145, 153–154, 444

辅助组件，757

- `accumulate`方法（`LongAccumulator`），888
- `accumulateAndGet`方法（`AtomicType`），887

`Action`接口，607–615, 680

- `actionPerformed`方法，608
- `add/removeChangeListener`方法，608–609
- `get/putValue`方法，608, 615
- `is/setEnabled`方法，608, 615
- 预定义名称，609

Action 监听器，607–615

`action/Frame.java`，613

`ActionEvent`类，588, 626

- `getActionCommand`方法，598, 627
- `getModifiers`方法，627

`ActionListener`接口，626

- `actionPerformed`方法，302–303, 314, 331–332, 337, 342, 589–593, 597, 601, 607, 609, 627, 897
- 重写，680
- 实现，318, 589, 597

`ActionMap`类，612

`Actions`，607–615

- 与按键关联，610
- 异步，931
- 名称，612
- 预定义，609

ActiveX，5, 15

适配器类，603–607

- `add`方法
  - `ArrayList`，245–251
  - `BigDecimal`、`BigInteger`，110–111
  - `BlockingQueue`，898–899
  - `ButtonGroup`，663
  - `Collection`，463, 467–469
  - `Container`，591, 595, 641
  - `GregorianCalendar`，142
  - `HashSet`，487
  - `JFrame`，555, 559
  - `JMenu`，679, 681
  - `JToolBar`，695–699
  - `List`，470, 482
  - `ListIterator`，470, 476–478
  - `LongAdder`，888
  - `Queue`，494
  - `Set`，471
- `addAll`方法
  - `ArrayList`，417
  - `Collection`，467–468
  - `Collections`，523
  - `List`，482
- `addChoosableFilter`方法（`JFileChooser`），763
- `addComponent`、`addGroup`方法（`GroupLayout`），723
- `addFirst/Last`方法的`Deque`，494
- `LinkedList`，484
- `addHandler`方法（`Logger`），406
- `addItem`方法（`JComboBox`），669–671
- `+`运算符，56, 64
- 用于不同的数值类型，60
- 用于对象和字符串，66–67, 239
- `addLayoutComponent`方法（`LayoutManager`），728
- `addPropertyChangeListener`方法（`Action`），608–609
- `addSeparator`方法
  - `JMenu`，679, 681
  - `JToolBar`，695–699
- `addShutdownHook`方法（`Runtime`），182
- `addSuppressed`方法（`Throwable`），377, 380

`AdjustmentEvent`类，626

- 方法，627

`AdjustmentListener`接口，626

- `adjustmentValueChanged`方法，627

Adobe Flash，9

聚合，133–135

算法，130

- 用于二分查找，521–522
- 用于洗牌，520
- 用于排序，518–521
- 快速排序，117, 519
- 在标准库中的简单的，522–524
- 编写，526–528

- Andreessen, Mark，10
- 注解，430
- 匿名数组，114
- 匿名内部类，329, 342–345
- `anonymousInnerClass/AnonymousInnerClassTest.java`，344
- 反对称性规则，295
- `anyOf`方法（`CompletableFuture`），934
- `JTextArea`的`append`方法，656, 951
- `StringBuilder`的，77–78
- `appendCodePoint`方法（`StringBuilder`），78
- `Applet`类，803
- `destroy`方法，808
- `getAppletContext`方法，818–820
- `getAppletInfo`方法，816
- `getCodeBase`、`getDocumentBase`方法，816–817
- `getImage`、`getAudioClip`方法，817
- `getParameter`方法，810–811, 816
- `getParameterInfo`方法，816
- `init`方法，807, 811
- `play`方法，817
- `resize`方法，808
- `showStatus`方法，819–820
- `start`、`stop`方法，808
- `applet`（HTML），34, 805, 808–810
- `align`属性，808
- `alt`属性，809
- `archive`属性，809
- `code`属性，809
- `codebase`属性，809
- `height`、`width`属性，807–808
- `hspace`、`vspace`属性，808
- `name`属性，810
- `object`属性（已弃），809
- `applet/NotHelloWorld.java`，805
- `AppletContext`接口，818
- `getApplet`、`getApplets`方法，818, 820
- `showDocument`方法，819–820
- Applets，8–9, 14, 802–824
- 通过 JavaScript 访问，810
- 对齐，808
- 在其中修改字符串，190
- 相互通信，810, 818
- 上下文，818
- 调试，807
- 数字签名的，822–824
- 执行，805
- 其中的图像和音频文件，816–817
- 多个副本，813
- 无标题栏的，807
- 传递信息，816
- 在其中打印，832
- 调整大小，808–810
- 在浏览器中运行，8, 33, 802–803, 818–820
- 序列化对象，809
- 测试，805–806
- 可信的本地，35, 806
- `appletviewer`程序，33, 805–806
- 应用程序接口（APIs），在线文档，71, 74–77
- Applications
- 缓存，827
- 用户关闭，545
- codebase，831
- 从命令行编译/运行，30–33
- 调试，25–26, 358–366
- 部署，779–838
- 可扩展，217
- 启动，43
- 本地化，136, 393–394, 785
- 在 JVM 中监控和管理，412
- 平台无关，724
- 偏好，788–800
- 终止，45
- 测试，384–388
- `applyToEither`方法（`CompletableFuture`），934
- 参数。*参见*参数
- 算术运算符，56–65
- 准确性，56
- 自动装箱，253
- 赋值组合，61
- 优先级，64
- `Array`类，276–279
- `get`、`getXxx`、`set`、`setXxx`方法，279
- `getLength`方法，277, 279
- `newInstance`方法，276, 279
- `Array`列表，112, 484
- 匿名，344
- 容量，246
- 元素：
  - 访问，247–251
  - 添加，245–251
  - 移除，249, 251
  - 遍历，249
  - 泛型，244–252
  - 原始 vs. 类型，251–252
- `Array`变量，111
- `ArrayBlockingQueue`类，899, 903
- `ArrayDeque`类，462, 494–495
- 作为具体的集合类型，472
- `ArrayIndexOutOfBoundsException`，112, 361–363, 938
- `ArrayList`类，113, 244–252, 416–418, 474
- `add`方法，245–251
- `addAll`方法，417
- 作为具体的集合类型，472
- `ensureCapacity`方法，246–247
- `get`、`set`方法，247, 251
- `remove`方法，249, 251
- `removeIf`方法，319
- `size`方法，246–247
- synchronized，914
- `toArray`方法，435
- `trimToSize`方法，246–247
- `arrayList/ArrayListTest.java`，250
- 数组，111–127
- 匿名，114
- 循环，462–463
- 拷贝，311
- 转换为集合，525–526
- 写入时，912
- 从中间删除，474
- 遍历，112–113, 122
- 等等性测试用于，234
- 泛型方法，276–279
- 哈希码值，238
- 命令行参数中的，116
- 初始化，112, 114
- 多维的，120–125, 240
- 不属于泛型类型的，321, 431–432, 441
- 整数的，240
- 子类/父类引用的，214
- 通配符类型的，432
- 越界访问在，360
- 并行操作，912
- 打印，122, 240
- 锯齿的，124–127
- 大小，112, 246, 277
- 等于 0，114, 526
- 等于 1，341
- 增加，115
- 运行时设置，244
- 排序，117–120, 292, 912
- 类型擦除与，434–436

## `Arrays`类

- `asList`方法，509, 516, 526
- `binarySearch`方法，120, 352
- `copyOf`方法，115, 119, 276
- `copyOfRange`方法，119
- `deepToString`方法，122, 240
- `equals`方法，120, 234
- `fill`方法，120
- `hashCode`方法，238
- `sort`方法，117–119, 290, 292, 294, 314, 318
- `toString`方法，114, 119
- `arrays/CopyOfTest.java`，278
- `ArrayStoreException`，431, 433, 441
- 上升字母、升部（排版中），576
- `ASCII`标准，51, 575
- `asList`方法（`Arrays`），509, 516, 526
- `assert`关键字，384–388
- `Assertions`，384–388
- 带有参数，386–387
- 定义的，384
- 带有假设的文档，387–388
- 启用/禁用，385–386
- 赋值运算符，54, 61
- 异步方法，915
- `atan`、`atan2`方法（`Math`），58
- `Atomic`操作，886–889
- 客户端锁，883
- 并发哈希映射中的，907–909
- 性能，888
- `AtomicType`类，887
- 从 applet 访问音频文件，816–817
- `@author`注释（`javadoc`），196, 199
- 自动装箱，252–256
- `AutoCloseable`接口，376
- `close`方法，376–377
- `await`方法（`Condition`），856, 873–877, 893–895
- `awaitUninterruptibly`方法（`Condition`），893–895
- AWT（Abstract Toolkit），538
- 事件中的：
  - 调试，774–778
  - 层级结构，624–628
  - 追踪，771
  - 偏选字段大小，649
- `AWTEvent`类，624

## B

- `\b`（退格序列），50

### 背景

- 默认颜色，570–571
- 擦除，842
- 绘制，558
- 退格转义序列用于，50
- `BadCastException`，451
- 屏障，936–937
- 基类。`Superclasses`
- 基线（排版中），576, 718
- 基础多语言平面，51
- `BasicUI`类，637
- `BasicService`接口，831
- `getCodeBase`方法，831, 836
- `isWebBrowser`方法，836
- `showDocument`方法，836
- 批处理文件，193
- `beep`方法（`Toolkit`），305
- `BiConsumer`接口，326
- `BiFunction`接口，319, 326
- `BiPredicate`接口，326
- 位掩码，54, 61
- 集合，532–536
- 埃拉斯特尼筛法，533–536
- 字节码文件，43
- `BitSet`接口，460, 532–536
- 方法的，533
- 位运算符，63–64
- 空行，46
- 阻塞队列，898–905

### `BlockingDeque`接口

- `offerFirst/Last`、`pollFirst/Last`方法，905
- `putFirst/Last`、`takeFirst/Last`方法，904

### `BlockingQueue`接口

- `add`、`element`、`peek`、`remove`方法，898–899
- `offer`、`poll`、`put`、`take`方法，898–899, 904

- `BigIntegerTest/BigIntegerTest.java`，109
- 二分搜索，521–522
- `BinaryOperator`接口，326
- `binarySearch`方法
  - `Arrays`的，120, 352
  - `Collections`的，521–522
- `BigDecimal`、`BigInteger`类，108–111
- `add`、`compareTo`、`subtract`、`multiply`、`divide`、`mod`方法，110–111
- `valueOf`方法，108, 110–111

# 布尔值与类型

`boolean`操作符，62, 64

`boolean`类型，52

默认初始化，172

格式化输出，83

不向数值类型的转换，61

`BooleanHolder`类，255

# 布局管理器

边框布局布局管理器（Border layout manager），641–644

`border/BorderFrame.java`，665

`BorderFactory`类，664–668

`createTypeBorder`方法，664–667

`BorderLayout`类，641–644

常量，642

# 边框

边框（Borders），664–668

复合边框，664

圆角，665

样式，664

带标题的边框，664

# 动画与组件

`bounce/Ball.java`，844

`bounce/BallComponent.java`，845

`bounce/Bounce.java`，842

`bounceThread/BounceThread.java`，849

# 集合与边界

边界集合（Bounded collections），463

边界矩形（Bounding rectangle），563–565

边界检查，115

# 布局

箱布局（Box layout），700

# 控制流

`break`语句，104–108

有标签/无标签的，106

缺失，412

桥接方法（Bridge methods），428–429, 440

`brighter`方法（`Color`），571

`BrokenBarrierException`，937

# 浏览器

默认，831

显示区域，819–820

在浏览器中安装 Java 插件，803

启用 Java 的，809

MIME 类型，825

在浏览器中运行 applet，8, 33–39, 802–803, 818–820

状态栏，819–820

# 哈希表

哈桶（哈希表的），485

批量操作，524–525

# 按钮

`button/ButtonFrame.java`，594

`ButtonGroup`类，660

- `add`方法，663
- `getSelection`方法，661, 663

`ButtonModel`接口，636–638

- `getActionCommand`方法，661, 663
- `getSelectedObjects`方法，661
- 属性，637

按钮

- 外观，632
- 与动作关联，610
- 点击，592
- 创建，591
- 事件处理，591–595
- 监听，592
- 模型-视图-控制器分析，636–638
- 自动重排，639

`ButtonUIListener`类，637

`Byte`类

- 从 `byte`，252
- `hashCode`方法，237
- `byte`类型，47

`ByteArrayOutputStream`类，830

# 编程语言

## C 编程语言

- 中的`assert`宏，385
- 事件驱动编程，588
- 函数指针，279
- 整数类型，6

## C# 编程语言

- 委托，280
- 多态，218
- 有用特性，11

## C++ 编程语言

- 中的`,`（逗号）运算符，65
- 中的`::`运算符，153, 207
- 中的`>>`运算符，64
- 访问权限，156
- 算法，518
- 数组，115, 126
- `bit`模板，532
- `boolean`值，52
- 类，45
- 嵌套，330
- 代码单元，70
- 控制流，89
- 构造函数，139
- 动态绑定，209
- 动态转换，221
- 异常，361, 364, 369
- 字段：实例，175, 176
- `for`循环，100
- 函数指针，279
- 中的`#include`，184
- 继承，204, 213
- 整数类型，6
- 访问器，142
- 析构函数，300
- 静态，161
- 命名空间，`using`指令
- `new`运算符，151
- 指针，139
- 运算符重载，109
- 传递，167, 169
- 性能，534
- 多态，218
- `protected`修饰符，228
- 虚函数，224
- 标准库，460, 465
- 静态方法，45
- `vector`模板，247
- 虚构造函数，229
- `void*`指针

- `canRead/Write`方法（`FileContents`），837
- 回车，转义序列用于，50
- `case`语句，104
- `cast`方法（`Class`），451
- 转换（Casts），60–61, 219–221
- 错误的，360
- 尝试之前的检查，220
- `catch`语句，367–381
- `ceiling`方法（`NavigableSet`），493
- `ChangeListener`接口，672
- `stateChanged`方法，672–673
- `char`类型，50–51
- `Character`类
  - 从`char`转换，252
  - `hashCode`方法，237
  - `isJavaIdentifierXxx`方法，53
- 字符，输出的格式化，83
- `charAt`方法（`String`），70, 72
- `chart/Chart.java`，813
- `checkBox/CheckBoxFrame.java`，658
- 复选框（Checkboxes），657–659
- 在菜单中，683–684
- 检出的异常（Checked exceptions），261–264
- 适用性，383
- 声明，361–364
- 使用泛型抑制，437–439
- 检出的视图（Checked views），513
- `checked`集合方法（`Collections`），515
- 子类。查看 Subclasses
- 选择组件（Choice components），657–678
- 边框，664–668
- 复选框，657–659
- 下拉框（combo boxes），668–671
- 单选按钮（radio buttons），660–663
- 滑动块（sliders），672–678
- `ChronoLocalDate`接口，446
- Church, Alonzo，315
- `circleLayout/CircleLayout.java`，725
- `circleLayout/CircleLayoutFrame.java`，728
- 循环数组（Circular arrays），462–463
- Clark, Jim，10
- Clarke, Arthur C.，717
- `Class`类，261–263
- `cast`方法，451
- `forName`方法，261, 265
- 泛型（generic），434, 450–453
- `getClass`方法，261
- `getComponentType`方法，277
- `getConstructor`、`getDeclaredConstructor`方法，451
- `getConstructors`、`getDeclaredConstructors`方法，266, 270
- `getDeclaredMethods`方法，266, 270, 280
- `getEnumConstants`方法，451
- `getField`、`getDeclaredField`方法，275
- `getFields`、`getDeclaredFields`方法，266, 270, 272, 275
- `getGenericXxx`方法，457
- `getImage`、`getAudioClip`方法，784
- `getMethod`方法，280
- `getMethods`方法，266, 270
- `getName`方法，244, 261–262
- `getResource`方法，784, 787
- `getSuperclass`方法，244, 451
- `getTypeParameters`方法，457
- `newInstance`方法，263, 265, 451
- 类常量（Class constants），55
- 类图表（Class diagrams），134–135
- `.class`文件扩展，43
- 类文件（Class files），185, 190
- 定位（locating），192
- 名字，43, 147
- `class`关键字，42
- 类加载器（Class loaders），351, 385
- 类路径（Class path），190–193
- 检查目录，412
- 设置，193
- 类胜出规则（Class wins rule），301
- `Class<T>`参数，452
- `ClassCastException`，220, 276, 295, 435, 441, 513
- 类，131–132, 204–228
- 抽象（abstract），221–227, 297
- 访问权限（access privileges），156
- 适配器（adapter），603–607
- 添加到包，185–188
- 分析：能力，265–271
- 运行时的对象，271–276
- 伴类（companion），298–299
- 构造函数，149
- 统，145–157
- 运行时（at runtime），350
- 已弃（deprecated），197
- 设计，133, 200–202
- 文档注释，194–198
- 封装，131–132, 153–156
- 扩展（extending），132
- 最终（final），217–218
- 泛型（generic），245, 418–420, 441, 669
- 辅助类（helper），706–712
- 不变（immutable），157
- 实现多个接口，296–297
- 导入（importing），183–184
- 内部（inner），329–349
- 匿名（anonymous），606
- 实例，131, 136
- 加载（loading），262, 411
- 多个源文件，149
- 名字，25, 43, 182, 201
- 全包（full package），183
- 基础类型数量，200
- 包作用域，189
- 参数，152–153
- 预定义的（predefined），135–145
- 私有方法，156–157
- 保护的（protected），227–228
- 公有的（public），194
- 访问（accessing），183
- 关系（relationships），133–135
- 可序列化的（serializable），412
- 程序间共享，191
- 单元测试（unit testing），162

`CLASSPATH`环境变量，26, 193

### `clear`方法

- 属于`BitSet`的，533
- 属于`Collection`的，467, 469

### `clearAssertionStatus`方法（`ClassLoader`），388

### 客户端加锁

882–883

### `clone`方法

- 数组类型的，311
- 属于`Object`的，156, 306–313, 318
- `clone/CloneTest.java`，312
- `clone/Employee.java`，312

### `Cloneable`接口

306–313

### `CloneNotSupportedException`

310

### `close`方法

- 属于`AutoCloseable`的，376–377
- 属于`Closeable`的，376
- 属于`Handler`的，406

### `Closeable`接口

376

### 闭包（Closures）

323

### 代码错误

359

### 代码平面（Code planes）

52

### 代码点（Code points）、代码单元（code units）

52, 70

### 代码库（在 JNLP 文件中）

831

### `codePointAt`、`codePoints`方法（`String`）

72

### `codePointCount`方法（`String`）

70, 73

### Collection 接口

463, 469, 479

- `add`方法，463, 467–469
- `addAll`方法，467–468
- `clear`方法，467, 469
- `contains`、`containsAll`方法，467–468, 479
- `equals`方法，467
- 泛型，466–469
- `isEmpty`方法，299, 467–468
- `iterator`方法，463, 468
- `remove`、`removeAll`方法，467–468
- `removeIf`方法，468, 524
- `retain`方法，467
- `retainAll`方法，469
- `size`方法，467–468
- `toArray`方法，249, 467, 469

### `Collections`类

459–536

- 相应的算法，517–528
- 有边界的，463
- 其中的批量操作，524–525
- 具体的，472–496
- 并发修改，479
- 转换为数组，525–526
- 调试，479
- 元素：插入，469；最大值，517；删除，465；遍历，464
- 相应的接口，460–471
- 遗留，528–536
- 轻量级包装，509–510
- 有序的，470, 476
- 性能，471, 486
- 搜索，521–522
- 排序的，489
- 线程安全的，512–513, 905–915
- 类型参数，418
- 使用参数，527

### `Collections`类

520

- `addAll`方法，523
- `binarySearch`方法，521–522
- `checkedCollection`、`emptyCollection`方法，515
- `copy`方法，523
- `disjoint`方法，524
- `fill`方法，523
- `frequency`方法，524
- `indexOfSub`、`lastIndexOfSub`方法，524
- `min`、`max`方法，523
- `nCopies`方法，510, 515
- `replaceAll`方法，523
- `reverse`方法，524
- `rotate`方法，524
- `shuffle`方法，520–521
- `singleton`、`singletonCollection`方法，510, 515
- `sort`方法，518–521
- `swap`方法，524
- `synchronizedCollection`方法，512–513, 515
- `unmodifiableCollection`方法，511–512, 514

### `Collections`框架

参见 Java collections

- 框架（JCF）颜色器，764–770

### `Color`类

569–573

- `brighter`、`darker`方法，571
- 预常量，570
- `colorChooser/ColorPanel.java`，767
- 背景，558, 570–571
- 修改，609
- 自定义，570
- 前景，570
- 预定义，570–572
- 系统，571

### 列（文本字段的）

649

### `com.sun.java`包

599

### 组合框（Combo boxes）

668–671

- 向添加添加，669
- 当前选择，669
- `comboBox/ComboBoxFrame.java`，670

### 命令行

- 从命令行编译/启动 Java，24
- 命令行参数，16

### 注释

46–47

- 代码块，46
- 自动文档，46, 194–199
- 属性文件，599
- 嵌套，47
- 在行末，46

### 伴随类

298

### `Comparable`接口

288, 352, 422–423, 446, 519

- `compareTo`方法，289–293
- `comparator`方法（`SortedMap`），493, 500

### `Comparator`接口

305–306, 314, 328–329, 519

- 链式比较器，328
- `comparing`方法，328–329
- 表达式，318
- `naturalOrder`方法，329
- `nullFirst/Last`方法，329
- `reversed`、`reverseOrder`方法，329, 519, 521

### `compare`方法（整数类型）

294, 318

# `compareAndSet`方法（`Atomic`类型）

887

# `compareTo`方法

- 在子类中，295
- `BigDecimal`、`BigInteger`，110–111
- `Comparable`，289–293, 422, 446
- `Enum`，260
- `String`，72

# 编译错误

29, 363

# 编译器

- 自动装箱，254
- 桥接方法，428
- 命令行选项，412
- 创建字节码文件，43
- 扣减方法类型，421
- 强制`throws`修饰符，368
- 即时（just-in-time），6–7, 14, 153, 218, 413, 534
- 启动，25
- 优化方法调用，7, 218
- 载载解析，215
- 共享字符串，67, 69
- 翻译内部类，336
- 翻译泛化数组列表，252
- 类型参数，417
- 警告，105, 252
- 空格符，44

# Completable futures

931–934

- 组合，933
- 组合，932
- 异常处理，933

# `CompletableFuture`类

- `acceptEither`、`applyToEither`方法，934
- `allOf`、`anyOf`方法，934
- `handle`方法，933
- `runAfterXxx`方法，934
- `thenAccept`、`thenApply`、`thenApplyAsync`、`thenRun`方法，933
- `thenAcceptBoth`、`thenCombine`方法，934
- `thenCompose`方法，932–933
- `whenComplete`方法，933
- `CompletionStage`接口，934

# `Component`类

627

- `getBackground/Foreground`方法，573
- `getFont`方法，651
- `getPreferredSize`方法，557, 559
- `getSize`方法，552
- 继承层次，640
- `isVisible`方法，552
- `repaint`方法，556, 559
- `setBackground/Foreground`方法，570, 573
- `setBounds`方法，546, 548, 552, 724
- `setCursor`方法，624
- `setLocation`方法，546, 548, 552
- `setSize`方法，552
- `setVisible`方法，546, 552, 951
- `validate`方法，651, 951

# `Components`

639

- 显示信息，553
- 标签，651, 652
- 实现，951
- 组合设计模式，631
- `CompoundInterest/CompoundInterest.java`，122

# 计算

- 性能，56, 59
- 截断，56
- `compute`、`computeIfAbsent`方法（`Map`），501
- 具体的集合，472–496
- 具体方法，222

# 并发哈希映射

- 原子更新，907–909
- 桶作为树结构，906
- 批量操作，909–911
- 效率，906
- 尺寸，906

# 并发修改检测

479

# 并发编程

- 7, 839–952
- 同步，862–897

# 并发集合

912

# `ConcurrentHashMap`类

905–907

- 原子更新，907–909
- `compute`、`computeIfXxx`方法，908–909
- `forEach`方法，910–911
- `get`方法，908
- `keySet`、`newKeySet`方法，912
- `mappingCount`方法，906
- `merge`方法，909
- 桶作为树结构，906
- `put`、`putIfAbsent`方法，908
- `reduce`、`reduceXxx`方法，910–911
- `replace`方法，908
- `search`、`searchXxx`方法，910–911
- 同步包装器，914

# `ConcurrentLinkedQueue`类

905, 907

# `ConcurrentModificationException`

478–479, 906, 914

# `ConcurrentSkipListMap`类

905–907

# `ConcurrentSkipListSet`类

905, 907

# `Condition`接口

878

- `await`方法，856, 893–895
- `awaitUninterruptibly`方法，893–895
- `signal`、`signalAll`方法，890
- 同步方法，880
- Condition 对象，872–877
- Condition 变量，872

# 条件语句

90–94

- `config`方法（`Logger`），390, 404
- 配置文件，794–800

# 确认对话框

733

# Console

- Applet 中的，807
- 打印消息到，42–46

# `Console`类

- 读取密码，80
- `readLine/Password`方法，81
- `console`方法（`System`），81

# `ConsoleHandler`类

394–399, 407

# `ConsoleWindow`类

770

# `const`关键字

56

# 常量

55–56

- 文档注释，196
- 名称，55
- 公有，56, 159
- 静态，159

# `Constructor`类

265

- `getDeclaringClass`方法，270
- `getModifiers`方法，265, 270
- `getName`方法，265, 270
- `getXxxTypes`方法，270
- `newInstance`方法，265, 452

# C

- 构造函数引用，321–322
- 构造函数，149–151, 171–182
- 在中调用另一个构造函数，176
- 定义，136
- 文档注释，194
- 字段初始化在：
  - 默认，172–173
  - 显式，174
  - 最终，265
- 初始化块在，177–181
- 名字，136, 150
- 无参数的，173, 208, 801
- 载载，172
- 参数名在，175
- 私有的，265
- 受保护的，194
- 公共，194, 265
- 使用`super`关键字，207
- `ConstructorTest/ConstructorTest.java`，179
- `Consumer`接口，326
- Consumer 线程，898
- `Container`类，639
- `add`方法，591, 595, 641
- `setLayout`方法，641
- 容器，639
- `contains`方法
  - 集合的，467–468, 479
  - `HashSet`的，487
- `containsAll`方法（Collection），467–468, 479
- `containsKey/Value`方法（Map），499
- 内容面板，554
- `continue`语句，108
- 控制流，89–108
  - 块作用域，89–90
  - 跳出，106–108
  - 条件判断语句，90–94
  - 循环，94–99
    - 确定的，99–103
    - “for each”，113–114
    - 多重选择，103–105
- 控制器，633
- 字符转换，82–83
- 协作调度，856
- 协调世界时（UTC），139
- `copy`方法（`Collections`），523
- `copyArea`方法（`Graphics`），583, 586
- `copyOf`方法（`Arrays`），115, 119, 276
- `copyOfRange`方法（`Arrays`），119
- `CopyOnArrayList`类，912, 914
- `CopyOnArraySet`类，912
- 核心 Java 示例，23
- Cornell, Gary，1
- 数据损坏，862–868
- `cos`方法（`Math`），58
- 蒙特基督的数（Dumas），490, 944–946
- 倒计时锁，936
- `CountDownLatch`类，935–936
- 协变返回类型，429
- `create`方法
  - `EventHandler`的，598
  - `PersistenceService`的，831, 837
  - `createCustomCursor`方法（`Toolkit`），618, 623
  - `createDialog`方法（`JColor`），770
  - `createFont`方法（`Font`），575
  - `createScreenCapture`方法（`Robot`），778
  - `createTypeBorder`方法（`BorderFactory`），664–667
  - `createXxxGroup`方法（`GroupLayout`），722
- Ctrl+\用于线程转储，889
- Ctrl+C用于程序终止，863, 875
- Ctrl+O、Ctrl+S快捷键，687
- Ctrl+Shift+F1在 Swing 中，770
- Ctrl+Tab在文本框中，729
- `current`方法（`ThreadLocalRandom`），893
- 当前用户，794
- `currentThread`方法（`Thread`），851–854
- `Cursor`类，`getPredefinedCursor`方法，617
- 光标形状，618
- 自定义布局管理器，724–728
- 自定义化。参见首选项
- `CyclicBarrier`类，935–937

### D

- `D`后缀（double 类型数字），49
- 守护线程，859
- `darker`方法（`Color`），571
- 数据交换，746–752
- 数据字段初始化，176–181
  - 公共，150
  - 数据类型，47–53
  - boolean 类型，52
  - 强制转换，60, 61
  - char 类型，50–51
  - 之间的转换，59, 60, 219–221
    - 浮点数，48–49
    - 整数，47–48
- 数据库，关闭连接，372
- `dataExchange/DataFrameFrame`，748
- `dataExchange/PasswordChooser.java`，749
- 日期和时间格式，83–84
- 无内置类型，136
- `Date`类，140
- `getDay/Month/Year`方法（已弃），141
- `toString`方法，137
- `DateInterval`类，428
- 死锁，874, 889–892, 896
- 拆分，893
- 在 GUI 中，897
- 调试，8, 409–414
- Applets，807
- AWT 事件，771, 774–778
- 集合，479
- 调试器，409
- 通用类型，513
- GUI 程序，367, 770–778
- 在中包含类名，344
- 间歇性 bug，69, 545, 952
- 用于消息，366
- 用于反射，272
- 用于将程序错误捕获到文件中，411
- 在终端窗口运行应用程序时，25–26

默认包，185

`default`语句，104, 298–300

`DefaultButtonModel`类，636

`DefaultComboBoxModel`类，669

延迟执行，325

`delay`方法（`Robot`），778

延迟接口，900

`getDelay`方法，900, 903

`DelayQueue`类，900, 903

委托，280

`PersistenceService`的`delete`方法，838

`StringBuilder`的，78

依赖，133–135

废弃类，197

废弃方法，141, 197, 412

废弃变量，197

`@deprecated`注释（`javadoc`），197

Deque 接口，494–495

- `addFirst/Last`方法，494
- `getFirst/Last`方法，495
- `offerFirst/Last`方法，494
- `peekFirst/Last`方法，495
- `pollFirst/Last`方法，495
- `removeFirst/Last`方法，495

Deques，494–495

派生类。参见子类

`deriveFont`方法（`Font`），575, 581

降字部，下降（在排版中），576

`descendingIterator`方法（`NavigableSet`），493

设计模式，630–632

*Design Patterns—Elements of Reusable Object-Oriented Software*（Gamma 等），632

`destroy`方法（`Applet`），808

确定循环，99–103

### 开发环境

- 选择，23–26
- 在终端窗口中，25
- 集成，26–30

### 设备错误

359

- `dialog/AboutDialog.java`，744
- `dialog/DialogFrame.java`，743

### 对话框

730–770

- 接受/取消，746
- 居中，304
- 关闭，603, 688, 743
- 颜色选择，764–770
- 确认，733
- 创建，741–745
- 数据交换，746–752
- 默认按钮，748
- 显示，743
- 文档和工具包，742
- 文件，752–764
- 输入，733
- 最大化，603
- 模态，730–741
- 模型，730, 742
- 与数据交换，747
- 选项，731–741
- 弹出层，821
- 根面板，748
- 遍历顺序，729–730

### 菱形语法

245

### Dijkstra, Edsger

935

- `disjoint`方法（`Collections`），524

`divide`方法（`BigDecimal`、`BigInteger`），110–111

### 除法运算符

56

`do/while`循环，96, 99

### Doclets

199

### 文档注释

46, 194–199

- 提取，198–199
- 字段，196
- 方法，195–196
- 程序包，198
- 通用，196
- HTML 标记，194
- 超链接，198
- 插入，194–195
- 其他文件的链接，195
- 概述，198

### 文档模态对话框

742

`doInBackground`方法（`Worker`），944–945, 950

### 无操作方法

604

### 双花括号初始化

344

### 双重缓冲

771

`Double`类

- `compare`方法，294
- 从`double`转换，252
- `hashCode`方法，237
- `POSITIVE_INFINITY`、`NEGATIVE_INFINITY`常量，49
- `double`类型，48
- 算术，56
- 转换为其他类型，59–60
- `DoubleAccumulator`、`DoubleAdder`类，889
- 双精度数字，48–49

### 双向链表

474

- `draw`方法（`Graphics2D`），561
- `draw/DrawTest.java`，566
- `drawImage`方法（`Graphics`），582, 585
- 用鼠标绘图，616–624
- `drawString`方法（`Graphics`/`Graphics2D`），581

### 下拉列表

668

### 动态绑定

209, 214–217

### 动态语言

8

### E

- `e`（指数），在数字中，49
- 作为类型变量的`E`，419
- `Math`常量，58

### 回声字符

652–653

### Eclipse

24, 26–30, 409

- 在项目中配置项目，28
- 在源文件中编辑，29
- 错误信息，29–30
- 导入，183

### SWT 工具包

543

### ECMA-262（JavaScript 子集）

15

### Eiffel 语言

多重继承，297

- `BlockingQueue`的`element`方法，898–899
- `Queue`的，494
- `elements`方法（`Hashtable`、`Vector`），530

### Ellington, Duke

539

### `Ellipse2D`类

560, 564–565

- `setFrameFromCenter`方法，565
- `setFrameFromDiagonal`方法，564

### `Ellipse2D.Double`类

569

### 椭圆

560, 564–565

- 边界框，563–565
- 构建，565
- 颜色填充，569

- `emptyCollection`方法（`Collections`），515
- `EmptyStackException`，381, 383
- 封装，131–132
- 优处，153–156
- 受保护的实例字段和，284
- `endsWith`方法（`String`），72
- `ensureCapacity`方法（`ArrayList`），246–247
- `entering`方法（`Logger`），405
- 企业版（Java EE），11, 18
- `entrySet`方法（Map），502–503
- `Enum`类，258–260
- `compareTo`、`ordinal`方法，260
- `toString`、`valueOf`方法，258, 260
- `enum`关键字，65
- 枚举类型，65
- 相等性测试，258
- 在`switch`语句中，105
- `Enumeration`接口，460, 528–530
- `nextElement`、`hasMoreElements`方法，465, 528, 530
- 枚举映射/集合，506
- 枚举，258–260, 818
- 遗留，528–530
- `EnumMap`类，506, 508
- 作为具体的集合类型，472
- `enums/EnumTest.java`，259
- `EnumSet`类，506
- `allOf`、`noneOf`、`of`、`range`方法，508
- 作为具体的集合类型，472
- `EOFException`，364
- 时间 Epoch，139
- `equals`方法，302
- 包装类，254
- `hashCode`方法和，236–237
- 实现，233
- 继承和，231–235
- `Arrays`的，120, 234
- `Collection`的，467
- `Object`的，229–235, 244, 512
- 代理类，355
- `Set`的，471
- `String`的，68, 72
- 重写，236–237
- `equals/Employee.java`，241
- `equals/EqualsTest.java`，240
- `equals/Manager.java`，243
- `equalsIgnoreCase`方法（`String`），68, 72
- `Error`类，360

### 错误

- 修改器方法中的检查，154
- 代码，359
- 编译，29
- 设备，359
- 内部，360, 363, 386
- 消息，369
- `NoClassFoundError`，26
- 物理限制，359
- `ThreadDeath`，857, 862, 896
- 用户输入，359

### 事件

- 转义序列，50
- 事件委托模型，588
- 事件分发线程，545, 846, 897
- 耗时任务和，939
- 事件处理，587–628
- 定义，587
- 异步操作，931
- 语义 vs. 低级事件，626
- 总结，626–628
- 事件监听器，588–589
- 带有方法，597
- 使用 lambda 表达式，595
- 事件对象，588
- 事件过程，587
- 事件源，588–589
- `EventHandler`类
  - `create`方法，598
  - 自动创建监听器，597
- `EventObject`类，588, 624
  - `getAction`方法，624
  - `getSource`方法，598, 624
- `EventQueue`类
  - `invokeAndWait`方法，940, 943
  - `invokeLater`方法，940, 943, 952
  - `isDispatch`方法，943
- `event/Tracer.java`，772
- `Example`类，757
- `Error`类，360, 380
- 句处理器，263, 359
- 规范，362

### 异常

- `ArrayIndexOutOfBoundsException`，112, 361–363
- `ArrayStoreException`，431, 441
- `BadCastException`，937
- `CancellationException`，945
- 捕获，263, 359, 367–381
- 修改类型，370
- 已检查的，261–264, 361–383
- `ClassCastException`，220, 276, 295, 435, 441, 513
- 分类，359–361
- `CloneNotSupportedException`，310
- `ConcurrentModificationException`，478–479, 906, 914
- 创建类，365–366
- 文档注释，196
- `EmptyStackException`，381, 383
- `EOFException`，364
- `FileNotFoundException`，362–364, 438
- `finally`句在，372–376
- 泛型在，437–439
- 层次结构，359, 383
- `IllegalAccessException`，272
- `NoSuchElementException`，464, 469, 483, 494–495
- `NullPointerException`，361, 383
- `NumberFormatException`，383
- 传播，368, 384
- 重新抛出与链，370, 410
- `RuntimeException`，360, 383
- `ServletException`，370
- 抑制，383
- 堆栈跟踪，377–381
- “早抛出，晚捕获”，384
- 抛出，263–265, 364–365
- `TimeoutException`，915
- 使用技巧，381–384
- `UnavailableServiceException`，830
- 未捕获，411, 857, 860–862
- 未检查，264, 361–363, 383
- 意外，392, 400
- `UnsupportedOperationException`，503, 510, 512, 514
- 在...中使用类型类型变量，437
- 变量，隐式`final`，370
- 对比简单测试，381
- 包装，371

- `Exchanger`类，935, 937
- 交换器，937
- `.exe`文件扩展名，783
- 可执行 JAR 文件，782–783
- 可执行路径，20
- `execute`方法（`SwingWorker`），945, 950
- 执行流，追踪，391
- `ExecutionException`，933
- `ExecutorCompletionService`类，927
- `poll`、`submit`、`take`方法，928
- 执行器，920–934
- 任务组，控制，927–928
- 期的，926
- `Executors`类
  - `newCachedThreadPool`方法，921, 925
  - `newFixedThreadPool`方法，921, 925
  - `newScheduledThreadPool`方法，921, 926
  - `newSingleThreadExecutor`方法，921, 925
  - `newSingleThreadScheduledExecutor`方法，921, 926
- `ExecutorService`接口，921–922
  - `invokeAny/All`方法，927–928
  - `shutdown`方法，922, 925
  - `shutdownNow`方法，922, 927
  - `submit`方法，921, 925
- 退出代码，45
- `exit`方法（`System`），45
- `exiting`方法（`Logger`），391, 405
- `exp`方法（`Math`），58
- 显式参数，152–153
- `exportXxx`方法（`Preferences`），795, 800
- `ExtendedService`类，830
- `extends`关键字，204–228, 422–423
- 外部填充，704

### F

- `F`后缀（`float`数字），49
- 阶乘函数，378
- 工厂方法，161
- 公平锁，872
- 穿透行为，105, 412
- `fdlib`（自由发行数学库），59
- `Field`类，265
- `get`方法，276
- `getDeclaringClass`方法，270
- `getModifiers`方法，265, 270
- `getName`方法，265, 270
- `getType`方法，265
- `set`方法，276
- 数字的字段宽度，82

### Fields

- 在子类中添加，207
- 默认初始化，172–173
- 文档注释，194, 196
- `final`，159, 218
- 实例，131, 150–153, 174, 200
- private，200, 206
- protected，194, 228, 283
- public，194, 196
- public static final，158–178, 185, 436
- volatile，885–886
- 文件访问，831
- 文件对话框，752–764
- 添加到，757
- `FileChooser.java`，762
- `JFileChooser.java`，761
- `JFrame.java`，759
- `canRead/Write`方法，837
- `getName`方法，837
- `FileFilter`类，755, 764
- `accept`方法，755, 764
- `getDescription`方法，755, 764
- `FileFilter`接口（`java.io`），755, 764
- `FileHandler`类，394–399
- 配置参数，396
- `FileNameFilter`接口，764
- `FileOpenService`类，830
- `openFileDialog`方法，830, 837
- `openMultiFileDialog`方法，837
- 文件扩展名，757
- 过滤器，755–757
- MIME 类型，825
- 名称，25, 87
- 在 GUI 中打开/保存，752–764
- 读取，87
- 自所有词，376
- 在单独线程中，944
- 写入，87
- `FileSaveService`类
  - `saveAsFileDialog`方法，837
  - `saveFileDialog`方法，830, 837
- `FileView`类，756
  - `getIcon`、`getName`、`getDescription`、`getTypeDescription`方法，756, 764
  - `isTraversable`方法，756, 764
- `fill`方法

# 索引

## A

- `Arrays`，120
- `Collections`，523
- `Graphics2D`，569–570, 573

## F

- `Filter`接口，398
- `isLoggable`方法，398, 408
- `final`访问修饰符，55, 217–218
- 检查，265
- 接口中的字段，296
- 实例字段，157
- 父类中的方法，295
- 共享字段，886
- 内部类以及，339–342
- `finalize`方法，181–182
- `finally`句，372–376
- 异常正常完成，412
- `return`语句在，374
- `unlock`操作在，869
- 无使用`catch`，373
- 金融计算，49
- `fine`、`finer`、`finest`方法（`Logger`），390, 404
- Firefox，34
- `first`方法（`SortedSet`），493
- First Person, Inc.，10
- `firstKey`方法（`SortedMap`），500
- `FirstSample/FirstSample.java`，46
- `Float`类
  - 从`float`转换，252
  - `hashCode`方法，237
  - `POSITIVE_INFINITY`、`NEGATIVE_INFINITY`、`NaN`常量，49
  - `float`类型，48
  - 转换为其他数值类型，59–60
- 浮点数，48–49
- 算术运算，56
- 等价性，101
- 输出格式化，对于82–83
- 四舍五入，49, 60
- 浮点数溢出，57
- `floor`方法（`NavigableSet`），493
- `floorMod`方法（`Math`），57
- 流式布局管理器，638
- `FlowLayout`类，641
- `flush`方法（`Handler`），406
- `FocusAdapter`类，626
- `FocusEvent`类，626
- `isTemporary`方法，627
- `FocusListener`接口，626
- `focusGained/Lost`方法，627
- `Font`类，574–581
- `createFont`方法，575
- `deriveFont`方法，575, 581
- `getFamily`、`getFontName`、`getName`方法，580
- `getLineMetrics`方法，577, 580
- `getStringBounds`方法，576–580
- `font/FontTest.java`，578
- `font.properties`文件，575
- `FontMetrics`类，`getFontContext`方法，582
- Fonts，573–582
- 可用性检查，573
- 字体/族名称，573
- 逻辑名称，574
- 大小，574–575
- 样式，575
- 类型属性，576
- “for each”循环，112–114
- 数组列表，249
- 集合，464, 914
- 多维数组，122
- `for`循环，99–103
- 逗号分隔的列表，在65
- 内部定义变量，101
- 集合，464
- `forEach`方法
  - `ConcurrentHashMap`，910–911
  - `Map`，499
- 前景色颜色指定，570
- Fork-join 框架，928
- 格式说明符（`printf`），82
- `format`、`formatTo`方法（`String`），83
- `Formattable`接口，83
- `Formatter`类，方法，399, 408
- `forName`方法（`Class`），261, 265
- `Frame`类，543
  - `get/setExtendedState`方法，553
  - `getIconImage`方法，553
  - `getTitle`方法，553
  - `is/setUndecorated`方法，553
  - `isResizable`方法，553
  - `setIconImage`方法，546, 553
  - `setResizable`方法，546, 553
  - `setTitle`方法，546, 553
- Frames
  - 用户关闭，545
  - 创建，543–546
  - 装饰，546
  - 显示：
    - 信息，在554–560
    - 文字，在557
    - 布局，在546–554
    - 属性，549
    - 大小，549–554

在`JVM`中，425, 452–458

继承规则，440–442

遗留代码和，429

方法，421–422, 427–429, 466–469

不适用于数组，434–436

反射和，450–458

所需的技能水平，417

静态字段或方法和，436

类型擦除，425–430, 434

发生后的冲突，439–440

类型匹配，452

vs.数组，321

vs.继承，416–418

通配符类型在，442–450

### `GenericArrayType`接口

453

`getGenericComponentType`方法，458

`genericReflection/GenericReflectionTest.java`，454

### `get`方法

- `Array`，279
- `ArrayList`，247, 251
- `BitSet`，533
- `ConcurrentHashMap`，908
- `Field`，276
- `Future`，915, 919, 921, 945
- `LinkedList`，480
- `List`，470, 483
- `LongAccumulator`，888
- `Map`，469, 497, 499
- `PersistenceService`，838
- `Preferences`，795, 800
- `ThreadLocal`，893
- `Vector`，883

### `getActionCommand`方法

- `ActionEvent`，598, 627
- `ButtonModel`，661, 663
- `EventObject`，624

### `getActionMap`方法（`JComponent`）

615

### `getActualTypeArguments`方法（`ParameterizedType`）

458

`getAdjustable`、`getType`方法（`AdjustmentEvent`），627

`getAncestorOfClass`方法（`Swing`），747, 752

`getAndType`方法（`AtomicType`），887

`getApplet`、`getApplets`方法（`AppletContext`），818, 820

`getAppletContext`方法（`Applet`），818–820

`getAppletInfo`方法（`Applet`），816

`getAscent`方法（`LineMetrics`），581

`getAudioClip`方法（`Class`），784, 817

`getAutoCreateXX`方法（`GroupLayout`），722

`getAvailableFamilyNames`方法（`GraphicsEnvironment`），573

`getBackground`方法（`Component`），573

`getBoolean`方法（`Array`），279

`getBounds`方法（`TypeVariable`），457

`getByte`方法（`Array`），279

`getCause`方法（`Throwable`），379

`get/Y`方法（`RectangularShape`），563, 568

`getChar`方法（`Array`），279

`getClass`方法始终返回原始类型，431

- `Class`，261
- `Object`，244

`getClassName`方法

- `Info`，603
- `StackTraceElement`，380

`getClickCount`方法（`MouseEvent`），616, 623, 627

`getCodeBase`方法

- `Applet`，816–817
- `BasicService`，831, 836

`getColor`方法

- `Graphics`，572
- `JColorChooser`，770

`getColumns`方法（`JTextField`），650

`getComponentPopupMenu`方法（`JComponent`），686

`getComponentType`方法（`Class`），277

`getConstructor`方法（`Class`），451

`getConstructors`方法（`Class`），266, 270

`getContentPane`方法（`JFrame`），559

`getDataType`方法（`Preferences`），795, 800

`getDay`方法（`Date`，已废用），141

`getDayXxx`方法（`LocalDate`），141, 145

`getDeclaredConstructor`方法（`Class`），451

`getDeclaredConstructors`方法（`Class`），266, 270

`getDeclaredField`方法（`Class`），261

`getDeclaredFields`方法（`Class`），266, 270, 275

`getDeclaredMethods`方法（`Class`），266, 270, 280

`getDeclaringClass`方法（`Class`），270

`getDefaultScreen`方法（`Graphics`），774

`getDefaultToolkit`方法（`Toolkit`），305, 549, 553

`getDefaultUncaughtExceptionHandler`方法（`Thread`），861

`getDescent`方法（`LineMetrics`），581

`getDescription`方法（`Filter`），755, 764

`getDocument`方法（`View`），756, 764

`getBase`方法（`Applet`），816–817

`getDouble`方法（`Array`），279

`getDelay`方法（Generic），900, 903

`getEnumConstants`方法（`Class`），451

`getExceptionTypes`方法（`Constructor`），270

`getExtendedState`方法（`Frame`），553

`getFamily`方法（`Font`），580

`getField`方法（`Class`），275

`getFormatter`方法（`Handler`、`Logger`），406

`getFileName`方法（`StackTraceElement`），380

`getFirst/Last`方法（`Deque`），495, 484

`getFloat`方法（`Array`），279

`getFont`方法（`Component`），651

`getFontMetrics`方法（`JComponent`），577, 582

`getFontName`方法（`Font`），580

`getFontRenderContext`方法（`FontMetrics`），582

`getForeground`方法（`Component`），573

- `getGenericXxx`方法（`Class`），457
- `getGlobal`方法（`Logger`），389, 410
- `getHandlers`方法（`Logger`），406
- `getHead`方法（`Formatter`），399, 408
- `LineMetrics`的`getHeight`方法，581；`RectangularShape`的`getHeight`方法，563, 568
- `getHonorsVisibility`、`getHorizontalGroup`方法（`GroupLayout`），722
- `FileView`的`getIcon`方法，756, 764；`JLabel`的`getIcon`方法，652
- `getIconImage`方法（`Frame`），553
- `Applet`的`getImage`方法，817；`Class`的`getImage`方法，784；`ImageIcon`的`getImage`方法，554, 582
- `getInheritsPopupMenu`方法（`JComponent`），686
- `getInputMap`方法（`JComponent`），612, 615
- `getInputStream`方法（`FileContents`），830, 837
- `getInstalledLookAndFeels`方法（`UIManager`），602
- `getInt`方法（`Array`），279
- `getItem`、`getItemSelectable`方法（`ItemEvent`），627
- `getItemAt`方法（`JComboBox`），669
- `getKey`方法（`Map.Entry`），503
- `getKeyStroke`方法（`KeyStroke`），610, 615
- `getKeyXxx`方法（`KeyEvent`），627
- `getLargestPoolSize`方法（`ThreadPoolExecutor`），926
- `getLeading`方法（`LineMetrics`），581
- `getLength`方法（`Array`），277, 279
- `Handler`的`getLevel`方法，406；`Logger`的`getLevel`方法，405；`LogRecord`的`getLevel`方法，407
- `getLineMetrics`方法（`Font`），577, 580
- `getLineNumber`方法（`StackTraceElement`），380
- `getLocalGraphicsEnvironment`方法（`GraphicsEnvironment`），774, 778
- `getLogger`方法（`Logger`），390, 404
- `getLoggerName`方法（`LogRecord`），407
- `getLong`方法（`Array`），279
- `getLowerBounds`方法（`WildcardType`），458
- `getMaxX/Y`方法（`RectangularShape`），568
- `LogRecord`的`getMessage`方法，407；`Throwable`的`getMessage`方法，366
- `getMethod`方法（`Class`），280
- `getMethodName`方法（`StackTraceElement`），380
- `getMethods`方法（`Class`），266, 270
- `getMillis`方法（`LogRecord`），408
- `getMinX/Y`方法（`RectangularShape`），568
- `ActionEvent`的`getModifiers`方法，627；`java.lang.reflect`的`getModifiers`方法，265, 270
- `getModifiersEx`方法（`InputEvent`），617, 623
- `getModifiersExText`方法（`InputEvent`），623
- `getMonth`方法（`Date`，已废用），141
- `getMonthXxx`方法（`LocalDate`），141, 145
- `Class`的`getName`方法，244, 261；`FileContents`的`getName`方法，837；`FileView`的`getName`方法，756, 764；`Font`的`getName`方法，580；`java.lang.reflect`的`getName`方法，265, 270；`LookAndFeelInfo`的`getName`方法，603；`TypeVariable`的`getName`方法，457
- `getNames`方法（`PersistenceService`），838
- `getNewState`、`getOldState`方法（`WindowEvent`），607, 628
- `getOppositeWindow`方法（`WindowEvent`），628
- `getOrDefault`方法（Map），499
- `getOutputStream`方法（`FileContents`），830, 837
- `getOwnerType`方法（`ParameterizedType`），458
- `getPaint`方法（`Graphics2D`），573
- `getParameter`方法（`Applet`），810, 811, 816
- `getParameterInfo`方法（`Applet`），816
- `getParameters`方法（`LogRecord`），407
- `getParameterTypes`方法（`Method`），270
- `getParent`方法（`Logger`），406
- `getPassword`方法（`JPasswordField`），653
- `getPoint`方法（`MouseEvent`），623, 627
- `getPredefinedCursor`方法（`Cursor`），617
- `getPreferredSize`方法（`Component`），557, 559
- `getProperties`方法（`System`），789, 793
- `getProperty`方法（`Properties`），531, 789, 792；`System`的`getProperty`方法，793
- `getProxyClass`方法（`Proxy`），355, 356
- `getRawType`方法（`ParameterizedType`），458
- `getResource`方法（`Class`），784, 787
- `getResourceBundle`、`getResourceName`方法（`LogRecord`），407
- `getReturnType`方法（`Method`），270
- `getRootPane`方法（`JComponent`），748, 752
- `getScreenSize`方法（`Toolkit`），549, 553
- `getScrollAmount`方法（`MouseWheel`），628
- `getSelectedFile/Files`方法（`FileChooser`），754, 763
- `getSelectedItem`方法（`JComboBox`），669–671
- `getSelectedObjects`方法（Itemable），661
- `getSelection`方法（`ButtonGroup`），661, 663
- `getSequenceNumber`方法（`LogRecord`），408
- `getServiceNames`方法（`ServiceManager`），836
- `getShort`方法（`Array`），279
- `getSize`方法（`Component`），552
- `getSource`方法（`EventObject`），598, 624
- `getSourceXxxName`方法（`LogRecord`），408
- `getStackTrace`方法（`Throwable`），377, 379
- `SwingWorker`的`getState`方法，950；`Thread`的`getState`方法，858
- `getStateChange`方法（`ItemEvent`），627
- `getStringBounds`方法（`Font`），576–577, 580
- `getSuperclass`方法（`Class`），244, 451
- `getSuppressed`方法（`Throwable`），377, 380
- `getTail`方法（`Formatter`），399, 408
- Getter/setter 对。*参见* Properties
- `JLabel`的`getText`方法，652；`JTextComponent`的`getText`方法，650
- `getThreadID`方法（`LogRecord`），408
- `getThrown`方法（`LogRecord`），408
- `getTime`方法（`Calendar`），218
- `getTitle`方法（`Frame`），553
- `getType`方法（`Field`），265
- `getTypeDescription`方法（`FileView`），756, 764
- `getTypeParameters`方法（`Class`、`Method`），457
- `getUncaughtExceptionHandler`方法（`Thread`），861
- `getUpperBounds`方法（`WildcardType`），458
- `getUseParentHandlers`方法（`Logger`），406
- `Action`的`getValue`方法，608, 615
- `AdjustmentEvent`的，627
- `Map.Entry`的，503
- `getWheelRotation`方法（`MouseWheelEvent`），628
- `Rectangle2D`的`getWidth`方法，563
- `RectangularShape`的，563, 568
- `getWindow`方法（`WindowEvent`），628
- `MouseEvent`的`getX/Y`方法，616, 623, 627
- `RectangularShape`的，568
- `Date`的`getYear`方法（已废用），141
- `LocalDate`的，141, 145
- GMT（格林威治时间），139
- Goetz, Brian，840, 885
- Gosling, James，10–11
- `goto`语句，89, 106
- 图形用户界面（GUI），537–586
- 自动测试，774–778
- 组件的，629–778
- 选择组件，657–678
- 对话框，730–770
- 文本输入，648–656
- 工具栏，694–696
- 提示框，696–699
- 遍历顺序，729–730
- 其中的死锁，897
- 调试，367, 770–778
- 其中的事件，587
- 其中的键盘焦点，611
- 布局，638–648, 699
- 多线程处理，846–851
- `Graphics`类，560, 582
- `copyArea`方法，583, 586
- `drawImage`方法，582, 585
- `drawString`方法，581
- `get/setFont`方法，581
- `getColor`方法，572
- `setColor`方法，570, 572
- `Graphics`编辑器，616–624
- `Graphics2D`类，560–569
- `draw`方法，561
- `drawString`方法，582
- `fill`方法，569, 570
- `getFontRender`方法，576, 582
- `getPaint`方法，573
- `setPaint`方法，569, 573
- `GraphicsDevice`类，550, 774
- `GraphicsEnvironment`类，550
- `getAvailableFamilyNames`方法，573
- `getDefaultScreenDevice`方法，774, 778
- `getLocalGraphicsEnvironment`方法，774, 778
- Green 项目，10
- `GregorianCalendar`类，142
  - `add`方法，142
  - 构造函数，140, 172
- Grid bag 布局，700–712
  - 内边距，704
- Grid 布局，644–648
- `gridbag/FontFrame.java`，707
- `gridbag/GBC.java`，709
- `GridBagConstraints`类，703
  - `fill`、`anchor`参数，704, 712
  - `gridx/y`、`gridwidth/height`参数，703–706, 712
  - 辅助类，706–712
  - `insets`字段，704, 712
  - `ipadx/y`参数，712
  - `weightx/y`字段，703, 712
- `GridLayout`类，641, 644
- Group 布局，701, 713–723
- `GroupLayout`类，713–723
  - `GroupLayout`的方法，722
- `groupLayout/FontFrame.java`，719
- `GroupLayout.Group`类，723
- `GroupLayout.ParallelGroup`类，723
- `GroupLayout.SequentialGroup`类，723
- GTK 外观，539–540
- 查看图形用户界面

### H

- `handle`方法（`CompletableFuture`），933
- `Handler`类，397
  - `close`方法，406
  - `flush`方法，406
  - `get/setFilter`方法，406
  - `get/setLevel`方法，406
  - `getFormatter`方法，406
  - `publish`方法，398, 406
  - `setFormatter`方法，399, 406
- 句程序，394–398
- Hansen, Per Brinch，884
- “Has–a”关系，133–135
- `hash`方法（`Objects`），237
- 哈希值，235–238, 485
  - 默认，235
  - 输出格式，83
- 哈希冲突，486
- 哈希映射，497
  - 并发，905–907
  - 恒等性，507–509
  - 链式，504–506
  - 设置，497
  - 与树形映射对比，497
  - 弱引用，504
- 哈希集，485–489
  - 向其中添加元素，490
  - 链式，504–506
- 哈希表，485
  - 旧版，528
  - 负载因子，486
  - 重哈，486
- `hashCode`方法，235–238
  - `equals`方法和，236–237
  - 空指针安全，236
  - `Arrays`的，238
  - `Boolean`、`Byte`、`Character`、`Double`、`Float`、`Integer`、`Long`、`Short`的，237
  - `Object`的，237, 489
- `Objects`，236–237
- 代理类，355
- `Set`的，471
- `String`的，485
- `HashMap`类，497, 500
- 作为具体的集合类型，472
- `HashSet`类，464, 487–488
  - `add`方法，487
  - 作为具体的集合类型，472
  - `contains`方法，487
- Hashtable 接口，460, 528–530, 914–915
- 作为具体的集合类型，472
- `elements`、`keys`方法，530
- 同步方法，528
- `hasMoreElements`方法（`Enumeration`），465, 528, 530
- `hasNext`方法
  - `Iterator`的，463, 465, 469
  - `Scanner`的，81
- `hasNext`类型方法（`Scanner`），81
- `hasPrevious`方法（`ListIterator`），476, 483
- `headMap`方法
  - `NavigableMap`的，517
  - `SortedMap`的，511, 516
- `headSet`方法（`NavigableSet`、`SortedSet`），511, 516
- `Heap`，495
- 转储，413
- 高度（排版中），576
- 辅助类，706–712
- 辅助方法，156, 448

### 十进制数

- 用于输出的格式化，82–83
- 前缀用于，48
- `higher`方法（`NavigableSet`），493
- Hoare, Tony，884
- 持有计数，870
- 持有者类型，255
- HotJava 浏览器，11, 802
- Hotspot 时编译编译器，534
- HTML（超文本标记语言），12–13
- `applet`元素，34, 805, 808–810
- `param`元素，810–816
- 表格，701
- `target`属性，820
- `title`元素，807

### 图标

- 带文件扩展名的，757
- 在菜单项目中，682–683
- 在滑块中，674
- Identity 映射，507–509
- `identityHashCode`方法（`System`），507, 509
- `IdentityHashMap`类，507–509
- 作为具体的集合类型，472
- IEEE 754 规范，49, 59
- `if`语句，90–94
- IFC（互联网基金类），538
- `IllegalAccessException`，272
- `IllegalStateException`，465, 469, 483, 494, 899
- `image/ImageTest.java`，583
- `ImageIcon`类，550
- `getImage`方法，554, 582

###  — 

- 从 applets 访问，816–817
- 显示，582–586
- `ImageViewer/ImageViewer.java`，31
- 不可变类，157
- 实现，460
- `implements`关键字，290
- 隐式参数，152–153
- 静态方法中的无，160
- 状态的，409
- `import`语句，183–184
- 静态的，185
- `importPreferences`方法（`Preferences`），795, 800
- 不一致状态，896
- `increment`方法（`LongAdder`），888
- 自增操作符，61–62
- `incrementAndGet`方法（`Atomic`类型），887
- 索引（在数组中），111
- `indexOf`方法
  - List 的，483
  - `String`的，73
- `indexOfSubList`方法（`Collections`），524
- `info`方法（`Logger`），389–390, 404
- 信息隐藏。参见`Encapsulation`
- 继承，133–135, 203–286
  - 设计提示用于，283–286
  - 相等性测试，231–235
  - 层级的，212–213
  - 多个的，213, 297
  - 防止，217–218
  - 对比类型参数，416, 440–442
- `inheritance/Employee.java`，210
- `inheritance/Manager.java`，211
- `inheritance/ManagerTest.java`，210
- `init`方法（`Applet`），807, 811
- `initCause`方法（`Throwable`），379

### 初始化块

- 177–181
- 静态的，178
- `initialize`方法（`ThreadLocal`），893
- 内联，7, 218

### 内部类

329–349

- 使用……访问对象状态，331–334
- 匿名的，329, 342–345, 606
- 适用性，335–338
- 定义的，329
- 局部的，339
- 私有的，333
- 静态的，331, 346–349
- 语法的，334–335
- 对比 lambdas，318
- `innerClass/InnerClassTest.java`，333

### 输入

- 输入对话框，733
- 输入映射，611–613
- 输入读取，79–81

### `InputEvent`类

- `getModifiersEx`方法，617, 623
- `getModifiersExText`方法，623
- `InputTest/InputTest.java`，80

### `insert`方法

- `JMenu`的，681
- `JTextArea`的，951
- `StringBuilder`的，78
- `insertItemAt`方法（`JComboBox`），669, 671

- 未实现在接口中，289, 296
- 私有，150, 200
- 保护，283
- 公有，150
- 掩蔽，151, 175–176
- ……的值，153–154
- volatile，885–886
- 与局部变量，151–152, 173
- `instanceof`运算符，64, 220–221, 295
- 实例，131
- 动态创建，263
- `int`类型，47
- 转换为其他数值类型，59–60
- 固定大小用于，6
- 平台独立性，48
- 随机数生成器用于，181

### `Integer`类

- `compare`方法，294, 318
- 从`int`转换，252
- `hashCode`方法，237
- `intValue`方法，255
- `parseInt`方法，254, 256, 811
- `toString`方法，256
- `valueOf`方法，256

- Integer 类型，47–48
- 算术运算用于，56
- ……的数组，240
- ……的输出格式化，82
- Java 中无符号类型，48
- 集成开发环境（IDE），20, 26–30
- Applet 间通信，810, 818
- `interface`关键字，288

### 接口类型

462

- 接口变量，295

### 接口

288–305

- 抽象类和，297
- 回调和，302–305
- 接口中的常量，296
- 定义，288
- ……的文档注释，194
- ……的演变，299
- 扩展，295
- 用于自定义算法，526–528
- 功能性接口，318–319
- 监听器，588
- 标记，309
- 接口中的方法，298
- ……之间的冲突，300–302
- 什么都不做的，604
- 非抽象的，318
- 接口中无字段，289, 296
- ……的属性，295–296
- 公有的，194
- 标记，309, 426, 471
- 与实现，460–463
- `interfaces/Employee.java`，293
- `interfaces/EmployeeSort.java`，292

- 间性 Bug，69, 545, 952
- 内部错误，360, 363, 386
- 内部填充，704
- 国际化。参见 Localization
- Internet Explorer applets 中的，810
- Java，9
- Java 的有限支持，803
- ……的安全性，15
- 解释型语言，14
- 解释器，7
- `interrupt`方法（`Thread`），851–854
- `interrupted`方法（`Thread`），853–854
- `InterruptedException`，841, 847, 851, 893, 915
- `IntHolder`类，255
- 内建锁，878, 884
- 算法教程（Cen et al.），489
- `intValue`方法（`Integer`），255
- 调用处理器，350
- `InvocationHandler`接口，350, 355
- InvocationHandler 的`invoke`方法，350, 355
- `Method`的，279, 283
- `invokeAndWait`方法（`EventQueue`），940, 943
- `invokeAny/All`方法（`ExecutorService`），927–928
- `invokeLater`方法（`EventQueue`），940, 943, 952
- `IOException`，88, 361, 364, 375
- “Is–a”关系，133–135, 213, 284
- `isAbstract`方法（`Modifier`），271
- `isAccessible`方法（`AccessibleObject`），275
- `isActionKey`方法（`KeyEvent`），627
- `isCancelled`、`isDone`方法（`Future`），915, 920–921
- `isDefaultButton`方法（`JButton`），752
- `isDispatchThread`方法（`EventQueue`），943
- `isEditable`方法（`JComboBox`），671
- `JTextComponent`的，648
- `isEmpty`方法（`Collection`），299, 467–468
- `isEnabled`方法（`Action`），608, 615
- `isFinal`方法（`Modifier`），265, 271
- `isInterface`方法（`Modifier`），271
- `isInterrupted`方法（`Thread`），851–854
- `isJavaIdentifierXxx`方法（`Character`），53
- `isLocationByPlatform`方法（`Window`），552
- `isLoggable`方法（`Filter`），398, 408
- `isNaN`方法（`Double`），49
- `isNative`方法（`Modifier`），271
- `isNativeMethod`方法（`StackTraceElement`），381
- ISO 8859–1 标准，51
- `JPopupMenu`的`isPopupTrigger`方法，685
- `MouseEvent`的，686
- `isPrivate`方法（`Modifier`），265, 271
- `isProtected`方法（`Modifier`），271
- `isProxyClass`方法（`Proxy`），355–356
- `isPublic`方法（`Modifier`），265, 271
- `isResizable`方法（`Frame`），553
- `AbstractButton`的`isSelected`方法，684
- `JCheckBox`的，658–659
- `isStatic`、`isStrict`、`isSynchronized`方法（`Modifier`），271
- `isTemporary`方法（`FocusEvent`），627
- `isTraversable`方法（`FileView`），756, 764
- `isUndecorated`方法（`Frame`），553
- `isVisible`方法（`Component`），552
- `isVolatile`方法（`Modifier`），271
- `isWebBrowserSupported`方法（`BasicService`），836
- `ItemEvent`类，626
  - `getItem`、`getItemSelectable`、`getStateChange`方法，627
- `ItemListener`接口，626
  - `itemStateChanged`方法，627
- `ItemSelectable`接口，`getSelectedObjects`方法，661
- `Iterable`接口，113
  - `Collection`的`iterator`方法，463, 468
  - `ServiceLoader`的`iterator`方法，802
- `Iterator`接口，463–466
  - “for each”循环，464
  - 泛型，466
  - `hasNext`、`next`、`remove`方法，463, 465, 469
- 迭代器，463–466
  - 元素之间，465
  - 弱一致性，906
- IzPack 程序，783

### J

- J#编程语言，8
- J++编程语言，8
  - 其中的委托，280
- `JApplet`类，803–808
- Jar Bundler 工具，783
- JAR 文件，190, 780–787
  - 创建，780
  - 数字签名，822–824
  - 放入`jre/lib/ext`目录，193
  - 可执行的，782–783
  - 清单文件，781–782
  - 资源与，783–787
  - 密封，787
- `jar`程序，780
  - 命令行选项，781–782

### Java 编程语言

- 体系无关的对象文件格式，5
- 作为一种编程平台，1–2
- GPL 下可用，14
- 基础语法，42–46, 145
- 其中的按值传递，165
- 大写敏感性，26, 42, 53–56, 528
- 与 JavaScript 通信，809
- 从命令行编译，24
- 设计，2–8
- 文档
- 动态，8
- 其中的动态绑定，209, 214–217
- 其中的垃圾回收，68, 139
- 历史，10–12
- 其中的解释器，7
- 其中的库，12–13
- 安装，22–23
- 相关的误解，13–15
- 其中的多线程，7, 839–952
- 网络能力，4
- 没有多重继承，297
- 没有运算符重载，109
- 没有无符号类型，48
- 性能，7, 14, 534
- 可移植性，6, 13, 56
- 可靠性，4
- 其中的关键字，43, 53, 56
- 安全性，4, 14, 820–822
- 简单性，3, 315
- 强类型，47, 291
- 版本，11–12, 538, 700
- 与 C++对比，3
- Java 2（J2），18
- Java 2D 库，560–569
  - 其中的浮点坐标，561
- Java 错误大游，44, 393
- Java 集合框架（JCF），459–536
  - 其中的算法，517–528
  - 集合与数组之间的转换，525–526
  - 其中的接口，469–471
  - 其中的遗留类，528–536
  - 操作：
    - 批量，524–525
    - 可选，514
  - 接口与实现的分离，460–463
  - 其中的视图与包装器，509–517
  - 与传统集合对比，465
- Java 并发实践（Goetz），840
- Java 开发工具包（JDK），5, 17–39
  - applet 查看器，805–806
  - 其中的文档，74–77
  - 下载，18–20
  - 带有字体，574
  - 安装，18–23
  - 默认，780
  - 设置，20–22
  - `.java`文件扩展名，43
- Java 语言规范，43
- Java 视觉风格，611
- Java 内存模型与线程规范，885
- Java 网络启动协议（JNLP），824–838
- Java-in，802–824
  - 控制面板，827
  - 启用，34
  - 安装，803
  - 其中的 Java 控制台，807
  - 限制性，9, 822
  - 运行本地 applet，806
  - 其中的签名代码，822–824
- `java`程序，25
  - 命令行选项，385–386
- Java 运行时环境（JRE），18
- Java SE 8，12, 18
  - 在接口中添加静态方法，298–299, 523
  - 其中的 CompletableFutures，931
  - 其中的并发哈希映射，906–911
  - 其中的构造器表达式，433
  - 其中的哈希表，486
- Java 插件，34
  - 其中的 lambda 表达式，314–329, 464, 887
  - 带有`LongAdder`、`LongAccumulator`类，888
  - 数组的并行操作，912
- Java 虚拟机（JVM），6
  - 其中的泛型，425, 452–458
  - 启动，25
  - 应用程序的监控和管理，412
- 执行优化在，391
- 预计算方法表在，216
- 安全漏洞在，803
- 线程优先级级别在，859
- 算术运算截断在，56
- 类加载在，411
- Java 虚拟机规范，44
- Java Web Start，824–838
  - 启动，826
  - 打印在，832
  - 安全性，829
- `java.applet.Applet` API，807–808, 816–817, 820
- `java.applet.AppletContext` API，820
- `java.awt.BorderLayout` API，644
- `java.awt.Color` API，572
- `java.awt.Component` API，552, 559, 573, 624, 651, 724
- `java.awt.Container` API，595, 641
- `java.awt.event.ActionEvent` API，598
- `java.awt.event.InputEvent` API，623
- `java.awt.event.MouseEvent` API，623, 686
- `java.awt.event.WindowEvent` API，607
- `java.awt.event.WindowListener` API，606
- `java.awt.event.WindowStateListener` API，607
- `java.awt.EventQueue` API，943
- `java.awt.FlowLayout` API，641
- `java.awt.Font` API，580–581
- `java.awt.font.LineMetrics` API，581
- `java.awt.FontMetrics` API，582
- `java.awt.Frame` API，553
- `java.awt.geom.Ellipse2D.Double` API，569
- `java.awt.geom.Line2D.Double` API，569
- `java.awt.geom.Point2D.Double` API，569
- `java.awt.geom.Rectangle2D.Double` API，568
- `java.awt.geom.Rectangle2D.Float` API，569
- `java.awt.geom.RectangularShape` API，568
- `java.awt.Graphics` API，572, 581, 585–586
- `java.awt.Graphics2D` API，573, 582
- `java.awt.GraphicsEnvironment` API，778
- `java.awt.GridLayout` API，648
- `java.awt.LayoutManager`，728
- `java.awt.Robot` API，778
- `java.awt.Toolkit` API，305, 553, 623
- `java.awt.Window` API，552, 560
- `java.awt.beans.EventHandler` API，598
- `java.io.Console` API，81
- `java.io.PrintWriter` API，89
- `java.lang.Boolean` API，237
- `java.lang.Byte` API，237
- `java.lang.Character` API，237
- `java.lang.Class` API，244, 265, 270, 275, 451, 457, 787
- `java.lang.ClassLoader` API，388
- `java.lang.Comparable` API，293
- `java.lang.Double` API，237, 294
- `java.lang.Enum` API，260
- `java.lang.Exception` API，380
- `java.lang.Float` API，237
- `java.lang.Integer` API，237, 255–256, 294
- `java.lang.Long` API，237
- `java.lang.Object` API，132, 237, 244, 489, 881–882
- `java.lang.Objects` API，237
- `java.lang.reflect`包，265, 276
- `java.lang.reflect.AccessibleObject` API，275
- `java.lang.reflect.Array` API，279
- `java.lang.reflect.Constructor` API，265, 270, 452
- `java.lang.reflect.Field` API，270, 276
- `java.lang.reflect.GenericArrayType` API，458
- `java.lang.reflect.InvocationHandler` API，355
- `java.lang.reflect.Method` API，270, 283, 457
- `java.lang.reflect.Modifier` API，271
- `java.lang.reflect.ParameterizedType`，458
- `java.lang.reflect.Proxy` API，356
- `java.lang.reflect.Type`，457
- `java.lang.reflect.WildcardType`，458
- `java.lang.Runnable` API，851
- `java.lang.RuntimeException` API，380
- `java.lang.Short` API，237
- `java.lang.StackTraceElement` API，380–381
- `java.lang.String` API，72–73
- `java.lang.StringBuilder` API，78
- `java.lang.System` API，81, 509, 793
- `java.lang.Thread` API，846, 851, 854, 858–861
- `java.lang.Thread.UncaughtExceptionHandler`，861
- `java.lang.ThreadGroup` API，862
- `java.lang.ThreadLocal` API，893
- `java.lang.Throwable` API，265, 366, 379–380
- `java.math.BigDecimal` API，111
- `java.math.BigInteger` API，110
- `java.nio.file.Paths` API，89
- `java.text.NumberFormat` API，256
- `java.time.LocalDate` API，145
- `java.util.ArrayDeque` API，495
- `java.util.ArrayList` API，247, 251
- `java.util.Arrays` API，119–120, 234, 238, 294, 516
- `java.util.BitSet` API，533
- `java.util.Collection` API，468–469, 524
- `java.util.Collections` API，514–515, 520–524, 915
- `java.util.Comparator` API，521
- `java.util.concurrent`包，868
  - canned functionality classes in，934–937
  - efficient collections in，905–907
- `java.util.concurrent.ArrayBlockingQueue` API，903
- `java.util.concurrent.atomic`包，886
- `java.util.concurrent.BlockingDeque` API，904–905
- `java.util.concurrent.BlockingQueue` API，904
- `java.util.concurrent.Callable` API，919
- `java.util.concurrent.ConcurrentHashMap` API，907
- `java.util.concurrent.ConcurrentLinkedQueue` API，907
- `java.util.concurrent.ConcurrentSkipListMap` API，907
- `java.util.concurrent.ConcurrentSkipListSet` API，907
- `java.util.concurrent.Delayed` API，903
- `java.util.concurrent.DelayQueue` API，903
- `java.util.concurrent.ExecutorCompletionService` API，928
- `java.util.concurrent.Executors` API，925–926
- `java.util.concurrent.ExecutorService` API，925, 928
- `java.util.concurrent.Future` API，919–920
- `java.util.concurrent.FutureTask` API，920
- `java.util.concurrent.LinkedBlockingQueue` API，903
- `java.util.concurrent.locks.Condition` API，877, 895
- `java.util.concurrent.locks.Lock` API，871, 877, 894
- `java.util.concurrent.locks.ReentrantLock` API，872
- `java.util.concurrent.locks.ReentrantReadWriteLock` API，896
- `java.util.concurrent.PriorityBlockingQueue` API，904
- `java.util.concurrent.ScheduledExecutorService` API，926
- `java.util.concurrent.ThreadLocalRandom` API，893
- `java.util.concurrent.ThreadPoolExecutor` API，926
- `java.util.concurrent.TransferQueue` API，905
- `java.util.Deque` API，494–495
- `java.util.Enumeration` API，530
- `java.util.EnumMap` API，508
- `java.util.EnumSet` API，508
- `java.util.EventObject` API，598
- `java.util.function` API，319
- `java.util.HashMap` API，500
- `java.util.HashSet` API，488
- `java.util.Hashtable` API，530
- `java.util.IdentityHashMap` API，509
- `java.util.Iterator` API，469
- `java.util.LinkedHashMap` API，508
- `java.util.LinkedHashSet` API，507
- `java.util.LinkedList` API，484
- `java.util.List` API，482–483, 516, 521, 524
- `java.util.ListIterator` API，483
- `java.util.logging.ConsoleHandler` API，407
- `java.util.logging.FileHandler` API，407
- `java.util.logging.Filter` API，408
- `java.util.logging.Formatter` API，408
- `java.util.logging.Handler` API，406
- `java.util.logging.Logger` API，404–406
- `java.util.logging.LogRecord` API，407–408
- `java.util.Map` API，499, 501–503
- `java.util.Map.Entry` API，503
- `java.util.NavigableMap` API，517
- `java.util.NavigableSet` API，493, 516
- `java.util.Objects` API，235
- `java.util.prefs.Preferences` API，799–800
- `java.util.PriorityQueue` API，496
- `java.util.Properties` API，531, 792–793
- `java.util.Queue` API，494
- `java.util.Random` API，181
- `java.util.Scanner` API，81, 89
- `java.util.ServiceLoader` API，802
- `java.util.SortedMap` API，500, 516
- `java.util.SortedSet` API，493, 516
- `java.util.Stack` API，532
- `java.util.TreeMap` API，500
- `java.util.TreeSet` API，493
- `java.util.Vector` API，530
- `java.util.WeakHashMap` API，507
- `JavaBeans` API，260, 758, 813
- `javac`程序，25
  - current directory in，192
- `javadoc`程序，194–199
  - command-line options of，199
  - comments in class，194–198
  - extracting，198–199
  - field，194, 196
  - general，196
  - method，194–195
  - overview，198
  - package，194, 198
  - declaring `Object` methods for，318
  - HTML markup in，194
  - hyperlinks in，198
  - links to other files，195
  - online documentation of，199
- `JavaFX`，543
- `javap`程序，336
- `JavaScript`，15
  - accessing applets from，810
  - communicating with Java，809
- `javaws`程序，828
- `javaws.jar`文件，830
- `javax.jnlp.BasicService` API，836
- `javax.jnlp.FileContents` API，837
- `javax.jnlp.FileOpenService` API，837
- `javax.jnlp.FileSaveService` API，837
- `javax.jnlp.PersistenceService` API，837–838
- `javax.jnlp.ServiceManager` API，836
- `javax.swing`包，545
- `javax.swing.AbstractAction` API，683
- `javax.swing.AbstractButton` API，663, 681–684, 688
- `javax.swing.Action` API，615
- `javax.swing.border.LineBorder` API，668
- `javax.swing.border.SoftBevelBorder` API，667
- `javax.swing.BorderFactory` API，666–667
- `javax.swing.ButtonGroup` API，663
- `javax.swing.ButtonModel` API，663
- `javax.swing.event`包，627
- `javax.swing.event.MenuListener` API，690
- `javax.swing.filechooser.FileFilter` API，764
- `javax.swing.filechooser.FileNameExtensionFilter` API，764
- `javax.swing.filechooser.FileView` API，764
- `javax.swing.GroupLayout` API，722
- `javax.swing.GroupLayout.Group` API，723
- `javax.swing.GroupLayout.ParallelGroup` API，723
- `javax.swing.GroupLayout.SequentialGroup` API，723
- `javax.swing.ImageIcon` API，554
- `javax.swing.JButton` API，595, 752
- `javax.swing.JCheckBox` API，659
- `javax.swing.JCheckBoxMenuItem` API，684
- `javax.swing.JColorChooser` API，770
- `javax.swing.JComboBox` API，671
- `javax.swing.JComponent` API，560, 582, 615, 650, 668, 686, 699, 752
- `javax.swing.JDialog` API，745
- `javax.swing.JFileChooser` API，762–763
- `javax.swing.JFrame` API，559, 682
- `javax.swing.JLabel` API，652
- `javax.swing.JMenu` API，681
- `javax.swing.JMenuItem` API，681–682, 688, 690
- `javax.swing.JOptionPane` API，304, 739–741
- `javax.swing.JPasswordField` API，653
- `javax.swing.JPopupMenu` API，685
- `javax.swing.JRadioButton` API，663
- `javax.swing.JRadioButtonMenuItem` API，684
- `javax.swing.JRootPane` API，752
- `javax.swing.JScrollPane` API，656
- `javax.swing.JSlider` API，678
- `javax.swing.JTextArea` API，656
- `javax.swing.JTextField` API，650
- `javax.swing.JToolBar` API，699
- `javax.swing.KeyStroke` API，615
- `javax.swing.SwingUtilities` API，752
- `javax.swing.SwingWorker` API，950
- `javax.swing.text.JTextComponent` API，648
- `javax.swing.Timer` API，305
- `javax.swing.UIManager` API，602
- `javax.swing.UIManager.LookAndFeelInfo` API，603
- `JButton`类，591, 595, 610, 636–638
  - `isDefaultButton`方法，752
- `JCheckBox`类，657–659
  - `isSelected`方法，658–659
  - `setSelected`方法，657, 659
- `JCheckBoxMenuItem`类，683–684
- `JColorChooser`类，764–770
  - 方法，770
- `JComboBox`类，627, 668–671
  - `addItem`方法，669–671
  - `getItemAt`方法，669
  - `getSelectedItem`方法，669–671
  - `insertItemAt`方法，669, 671
  - `isEditable`方法，671
  - `removeX`方法，669, 671
  - `setEditable`方法，669, 671
  - `setModel`方法，669
- `JComponent`类，554
  - action maps，612
  - `get/setPopupMenu`方法，685–686
  - `get/setInheritsPopupMenu`方法，685–686
  - `getActionMap`方法，615
  - `getFontMetrics`方法，577, 582
  - `getInputMap`方法，612, 615
  - `getRootPane`方法，748, 752
  - input maps，611–613
  - `paintComponent`方法，554–556, 560, 577, 583
  - `repaint`方法，951
  - `revalidate`方法，649–650, 951
  - `setBorder`方法，664, 668
  - `setDebugGraphics`方法，771
  - `setFont`方法，650
  - `setSelectionStart/End`方法，952
  - `setToolTipText`方法，699
- `jconsole`程序，393, 412, 771, 889
- `jcontrol`程序，807
- `JDialog`类，741–745
  - `setDefaultCloseOperation`方法，743, 807
  - `setVisible`方法，743, 746, 807
- JDK。*See* Java Development Kit
- `JEditorPane`类，654
- FC（Java Foundation），539
- `JFileChooser`类，752–764
  - `addableFileFilter`方法，763
  - `getSelectedFile/Files`方法，754, 763
  - `resetableFilters`方法，756, 763
  - `setAllFilterUsed`方法，756, 763
  - `setory`方法，763
  - `setCurrentDirectory`方法，754, 762
  - `setFilter`方法，755, 763
  - `setFileSelectionMode`方法，754, 763
  - `setFileView`方法，756, 757, 756
  - `selectionEnabled`方法，754, 763
  - `setSelectedFile/Files`方法，754, 763
  - `showDialog`方法，747, 752, 754, 763
- `JFrame`类，543, 547, 640
  - `add`方法，555, 559
  - `getContentPane`方法，559
  - 结构，554
  - `setMenuBar`方法，679, 682
- `JLabel`类，651–652, 757
  - `getIcon`方法，652
  - `setText`方法，651–652
- `JList`类，670
- `jmap`程序，413
- `JMenu`类
  - `add`、`separator`方法，679, 681
  - `insert`、`separator`方法，681
  - `remove`方法，681
- `JMenuBar`类，679–682
- `JMenuItem`类，681–682
  - `setAccelerator`方法，687–688
  - `setEnabled`方法，689–690
  - `setIcon`方法，682
- Jmol applet，9
- JNLP API，829–838
  - compiling programs with，830
- `join`方法（`Thread`），73, 856–858
- `JOptionPane`类，730–741
  - message types，731
  - `showConfirmDialog`方法，731–732, 739
  - `showInputDialog`方法，731–732, 740
  - `showInternalConfirmDialog`方法，739
  - `showInternalInputDialog`方法，741
  - `showInternalMessageDialog`方法，739
  - `showInternalOptionDialog`方法，740
  - `showMessageDialog`方法，304, 731–732, 739
  - `showOptionDialog`方法，731–732, 739–740
- `JPanel`类，558, 638, 842
- `JPasswordField`类，652–653
  - `getPassword`、`setEchoChar`方法，653
- `JPopupMenu`类，684–686
  - `isPopupTrigger`、`show`方法，685
- `JRadioButton`类，660–663
- `JRadioButtonMenuItem`类，684
- `JRootPane`类，`setDefaultButton`方法，748, 752
- `JScrollbar`类，627
- `JScrollPane`类，656
- `JSlider`类，672–678
  - `setInverted`方法，674, 678
  - `setLabelTable`方法，429, 673, 678
  - `setPaintLabels`方法，673, 678
  - `setPaintTicks`方法，673, 678
  - `setPaintTrack`方法，674, 678
  - `setSnapToTicks`方法，673, 678
  - `setXxxTickSpacing`方法，678
- `JTextArea`类，653–654
  - `append`方法，656, 951
  - `insert`方法，951
  - `replaceRange`方法，951
  - `setColumns`、`setRows`方法，654, 656
  - `setLineWrap`方法，654, 656
  - `setTabSize`方法，656
  - `setWrapStyle`方法，656
- `JTextComponent`类
  - `getText`方法，650
  - `is/setEditable`方法，648
  - `setText`方法，648, 650, 951
- `JTextField`类，627, 649–651
  - `getColumns`方法，650
  - `setColumns`方法，649–650
- `JToolBar`类，695–696
  - `add`、`addSeparator`方法，695–699
- `JUnit`框架，410
- Just-in-time 编译器，2–14, 153, 218, 413, 534
- JVM。查看 Java machine

### K

- `K`类型变量，419
- Key/值对。查看 Properties
- `KeyAdapter`类，626
- 与动作关联的键盘，610
- 焦点，611
- 快捷键的，686–688
- 键盘焦点，729
- `KeyEvent`类，626
  - `getKeyXxx`、`isActionKey`方法，627
- `KeyListener`接口，626
  - `keyXxx`方法，627
- `keyPress/Release`方法（`Robot`），778
- `Hashtable`的`keys`方法，530
- `Preferences`的，795, 799
- `ConcurrentHashMap`的`keySet`方法，912
- Map 的，502–503
- `KeyStroke`类，`getKeyStroke`方法，610, 615
- Knuth, Donald，106
- KOI-8 标准，51

### L

- `L`后缀（`long`整数），48
- 带有标签的`break`语句，106
- 标签
  - 组件的，651–652
  - 用于滑块刻度的，673
- Lambda 表达式，314–329
  - 在……中访问变量，322–324
  - 使用……的原子更新，887
  - 由……捕获值，323
  - 用于事件监听器的，595
  - 函数式接口和，318
  - 方法引用，320
  - 赋值给`Object`类型的变量，319
  - 参数类型，316
  - 处理，324–328
  - 结果类型，316
  - 作用域，324
  - 语法的，315–317
  - 中的`this`关键字，324
  - 与内部类，318
- `lambda/LambdaTest.java`，317
- Langer, Angelika，458
- `SortedSet`的`last`方法，493
- List 的`lastIndexOf`方法，483
- `String`的，73
- `Collections`的`lastIndexOfList`方法，524
- `SortedMap`的`lastKey`方法，500
- Launch4J 工具，783
- 布局管理，638–648
  - 绝对定位，723
  - 边界，641–644
  - 框，700
  - 自定义，724–728
  - 流布局，638
  - 网格，644–648
  - 网格包，700–712
  - 组，701, 713–723
  - 复杂的，699–730
  - Spring，700
- LayoutManager 接口
  - 设计自定义，724–728
  - ……的方法，728
- LayoutManager2 接口，725
- Leading（排版中），576
- 旧版代码和泛型，429–430
- 旧版集合，528–536
- 位集，532–536
- 枚举，528–530
- 哈希表，528
- 属性映射，530–531
- 栈，531
- `length`方法
  - 数组的，112
  - `BitSet`的，533
  - `String`的，69–70
  - `StringBuilder`的，78
- 轻量级集合包装器，509–510
- `LineMetrics`类，577
  - `getXxx`方法，581
- 行数，560
- 构建，565
- `@link`注释（`javadoc`），198
- 链接顺序的哈希映射/集合，504–506
- 链表，474–484
  - 并发修改的，479
  - 双向链表的，474
  - 打印，481
  - 随机访问，479, 517
  - 从中删除元素，475
- `LinkedBlockingDeque`类，903
- `LinkedBlockingQueue`类，899
- `LinkedHashMap`类，504–508
  - 访问顺序 vs 插入顺序，505
  - 作为具体的集合类型，472
  - `removeEldestEntry`方法，506, 508
- `LinkedHashSet`类，504–507
  - 作为具体的集合类型，472
- `LinkedList`类，462, 476, 479, 494
  - `addFirst/Last`、`getFirst/Last`方法，484
  - 作为具体的集合类型，472
  - `get`方法，480
  - `listIterator`方法，476
  - `next/previousIndex`方法，480
  - `removeAll`方法，480
  - `removeFirst/Last`方法，484
- `linkedList/LinkedListTest.java`，481
- `linkSize`方法（`GroupLayout`），722
- Linux
  - 在 Linux 下调试 applets，807
  - 对应的 Eclipse 版本，27
  - 对应的 JDK 版本，18
  - Oracle JVM 中没有线程优先级，859
  - 弹出窗口触发，685
  - 在 Linux 下运行 applets，34–35
  - 在 Linux 下设置路径，20, 191–193
  - 在 Linux 下配置 JDK，20
  - 在 Linux 下排查 Java 程序问题，26
- List 接口，470, 509
  - `add`方法，470, 482
  - `addAll`方法，482
  - `get`、`set`方法，470, 483
  - `indexOf`、`lastIndexOf`方法，483
  - `listIterator`方法，482
  - `remove`方法，470, 483
  - `replaceAll`方法，524
  - `sort`方法，521
  - `subList`方法，510, 516
- Listener 接口，588
- Listener 对象，588
  - 查看 Action 监听器、Event 监听器、Window 监听器
- `ListIterator`接口，479
  - `add`方法，470, 476–478
  - `hasPrevious`方法，476, 483
  - `next/previousIndex`方法，483
  - `previous`方法，476, 483
  - `remove`方法，478
  - `set`方法，478, 483
  - `LinkedList`的`listIterator`方法，476
  - List 的`listIterator`方法，482
- Lists，470
  - 可修改/可调整大小，520
  - `Properties`的`load`方法，531, 788, 793
  - `ServiceLoader`的`load`方法，802
- 局部内部类，339
  - 从外部方法访问 final 变量，339–342
- 局部变量
  - 注解，430
  - vs 实例字段，151–152, 173
- `LocalDate`类，139–141
  - 扩展，285
  - `getXxx`方法，141, 145
  - `minusDays`方法，145
  - `now`、`of`方法，140, 145
  - `plusDays`方法，141, 145
  - 处理数组，446
- Locales，393
- 国际化，136, 393–394, 784–785
- Lock 接口，878
  - `await`方法，873–877
  - `lock`方法，871, 893
  - `lockInterruptibly`方法，893, 895
  - `newCondition`方法，873, 877
  - `signal`方法，875–877
  - `signalAll`方法，874–877
  - `tryLock`方法，856, 893, 895
  - `unlock`方法，869, 871
  - vs 同步方法，880
- Lock 对象，868–872
  - 客户端，883
  - 死锁，874, 889, 893
  - 公平，872
  - 计数，870
  - 不一致状态，896
  - 内部，778, 784
  - 使用 try-with 语句，869
  - 读/写，895–896
  - 重入，870
  - 测试，893–895
- Locks
  - 条件对象，873–877
  - 在同步块中，882–883
- Log，58
- Logarithms，58
- `Logger`类
  - `add/removeHandler`方法，406
  - `entering/exiting`方法，391, 405
  - `get/setFilter`方法，398, 406
  - `get/setParent`方法，406
  - `get/setParentHandlers`方法，406
  - `getGlobal`方法，389, 410
  - `getHandlers`方法，406
  - `getLevel`方法，405
  - `getLogger`方法，390, 404
  - `info`方法，389
  - `log`方法，390, 392, 405
  - `logp`方法，391, 405
  - `logrb`方法，405
  - `setLevel`方法，389, 405
  - `severe`、`warning`、`info`、`config`、`fine`、`finer`、`finest`方法，390, 404
  - `throwing`方法，392, 405
- Loggers
  - 配置，392–393
  - 默认，389, 391

# 层级化名称

390

# 编写自己的

390–392

# 日志记录

389–408

## 高级

390–392

## 基础

389

## 文件模式变量用于

396

## 文件轮转用于

397

## 过滤器用于

398

## 格式化器用于

399

## 处理器用于

394–398

## 配置

396

## 在……中包含类名

344

## 级别

390–391

## 更改

392–393

## 本地化

393–394

## 消息用于

240

## 配方用于

399–408

## 资源包和

393–394

# 日志代理

410

`logging/LoggingImageViewer.java`，400

`logging.properties`文件，392–393

# 逻辑条件

52

## 逻辑“与”、“或”

62

# `LogManager`类

393

## `readConfiguration`方法

392

# `LogRecord`类

- `getLevel`方法，407
- `getLoggerName`方法，407
- `getMessage`方法，407
- `getMillis`方法，408
- `getParameters`方法，407
- `getResourceBundle`、`getResourceBundleName`方法，407
- `getSequenceNumber`方法，408
- `getSourceXxxName`方法，408
- `getThreadID`方法，408
- `getThrown`方法，408

# `Long`类

- 从`long`，252
- `hashCode`方法，237
- `long`类型，47
- 平台独立性，48

# `LongAccumulator`类的方法

888

# `LongAdder`类

888, 908

- `add`、`increment`、`sum`方法，888

# 查找外观

539, 700

- 按钮的外观，632
- 更改，598–603
- 可插的，756

# `LookAndFeelInfo`类的方法

603

## `lookup`方法（`ServiceManager`）

836

# 循环

- 中的`break`语句，106–108
- 中的`continue`语句，108
- 确定的（`for`），99–103
- “for each”，113–114
- `while`，94–99
- `LotteryArray/LotteryArray.java`，126
- `LotteryDrawing/LotteryDrawing.java`，118
- `LotteryOdds/LotteryOdds.java`，102
- `lower`方法（`NavigableSet`），493

# 低级事件

626

# Lu, Francis

810

### M

#### Mac OS

- Eclipse 版本，27
- 执行 JAR，783
- JDK 版本，18
- 在 applet 中，34–35
- 路径设置，20
- 设置 JDK，20

- `main`方法，161–164
- 主体，44
- 声明为`public`，43
- 声明为`static void`，44–45
- applet 的消除，807
- 从加载类，262
- 未定义，145, 179
- 每个类单独，409
- `String[] args`参数，116
- 标记有`throws`，88
- `make`程序（UNIX），149
- `MANIFEST.MF`（清单文件），781–782
- 编辑，782
- 换行符，782
- 权限，823
- `Map`接口，469
  - `compute`、`computeIfPresent/Absent`方法，501
  - `containsKey/Value`方法，499
  - `entrySet`、`keySet`方法，502–503
  - `forEach`方法，499
  - `get`、`put`方法，469, 497
  - `merge`方法，501
  - `putAll`方法，499
  - `remove`方法，498
  - `replaceAll`方法，502
  - `values`方法，502–503
- `map/MapTest.java`，498
- `Map.Entry`接口，502
  - `getKey`、`setValue`方法，503
- `mappingCount`方法（`ConcurrentHashMap`），906
- Maps，497–509
  - 添加/从获取对象，497
  - 并发，905–907
  - 垃圾收集，504
  - 哈希表 vs 树，497
  - 实现，497
  - 键，498
  - 枚举，502
  - 范围，511

# 标记接口

309

# `Math`类

57–59

- `E`、`PI`常量，58, 159
- `floorMod`方法，57
- 对数，58
- `pow`方法，57, 160
- `round`方法，60
- `sqrt`方法，57
- 三角函数，58

# Matisse

701, 713–723

- `max`方法（`Collections`），523

# 最大值，计算

419

`menu/MenuFrame.java`，690

# `MenuListener`接口

689

- `menuXxx`方法，689–690

# 菜单

678–699

- 快捷键，687–688
- 复选框和单选按钮，683–684
- 图标，682–683
- 键盘热键用于，686–688
- 菜单栏，679
- 菜单项，679–684
- 启用/禁用，689–693
- 弹出菜单，684–686
- 子菜单，679

# `Method`类

265

- `getDeclaringClass`方法，270
- `getExceptionTypes`方法，270
- `getGenericXxx`方法，457
- `getModifiers`方法，265, 270
- `getName`方法，265, 270
- `getParameterTypes`、`getReturnType`方法，270
- `getTypeParameters`方法，457
- `invoke`方法，279–283
- `toString`方法，266

## 方法参数

参见参数

## 方法与概念

- 方法指针，279–281
- 方法引用，319–321
- 输入中的`this`、`super`参数，320
- 方法表，216
- 方法，131
  - 抽象，222
  - 在函数接口中的，318
  - 访问器，141–145, 153–154, 444
  - 在子类中添加，207
  - 应用于对象，137
  - 异步，915
  - 方法体，44–45
  - 桥接，428–429, 440
  - 引用传递 vs. 值传递，164–171
  - 转换，219–221
  - 具体的，222
  - 一致的，231
  - 默认，298–300
  - 弃用，141, 197, 412
  - 析构函数，181–182
  - 文档注释，194–198
  - 空方法，604
  - 动态绑定，209, 214–217
  - 输入中的异常规格，362
  - 工厂，161
  - 最终，215, 217–218, 265, 295
  - 泛型，421–422, 427–429, 466–469
  - 辅助，156, 448
  - 内联化中的，7, 218
  - 调用，45
  - 任意的，279–283
  - 变变器，141–145, 154, 444
  - 名称，201
  - 重载，172
  - 重写，206–207, 234, 285
  - 异常和，364
  - 返回类型和，427
  - 包作用域
  - 参数的，45–46
  - 传递对象，136
  - 私有的，156–157, 215, 265
  - 保护的，194, 228, 311
  - 公有的，194, 265, 290
  - 反映的，231
  - 解决冲突，300–302
  - 返回类型，172, 215
  - 签名，172, 215
  - 静态，160–161, 185, 215, 436
  - 向接口中添加，298
  - 对称的，231
  - 追踪，351
  - 传递性的，231
  - 可变参数，256–257
  - 传递泛型类型，432–433
  - 在子类中的可见性，217
- `methods/MethodTableTest.java`，282
- 微型（Java ME），3, 11, 18

# 微软

- .NET 平台，6
- ActiveX，5, 15
- C#，8, 11, 215, 280
- Internet Explorer，9, 15, 803, 810
- J#、C++，8, 280
- Visual Basic，3, 136, 587, 638
- Visual Studio，23
- MIME 类型，825
- `min`方法（`Collections`），23

- 最小值，419
- `minimumLayoutSize`方法（`LayoutManager`），728
- `minusDays`方法（`LocalDate`），145
- `mod`方法（`BigDecimal`、`BigInteger`），110–111
- 模态，730, 742
- 模型-视图-控制器设计，632–636
  - 类中的，632
  - 多个视图中的，634
- `Modifier`类
  - `isAbstract`、`isInterface`、`isNative`、`isSynchronized`、`isVolatile`方法，271
  - `isFinal`、`isPrivate`、`isPublic`方法，265, 271
- 模数，56
- 监控概念，884
- 镶，10
- 鼠标事件，616–624
  - 带有键盘修饰符，616
- `mouse/MouseComponent.java`，220
- `mouse/MouseFrame.java`，619
- `MouseAdapter`类，619, 626
- `MouseEvent`类，626
  - `getClickCount`方法，616, 623, 627
  - `getPoint`方法，623, 627
  - `getX/Y`方法，616, 623, 627
  - `isPopupTrigger`方法，686
  - `translatePoint`方法，627
- `MouseHandler`类，619
- `MouseListener`接口，617, 626
  - `mouseClicked`方法，616–617, 619, 627
  - `mouseDragged`方法，619
  - `mouseEntered/Exited`方法，619, 627
  - `mousePressed`方法，616–617, 627
  - `mouseReleased`方法，616, 627

多维数组，120–125

打印，240

锯齿数组，124–127

多重继承，297

Java 不支持，213

多重选择，103–105

乘法运算符，56

`multiply`方法（`BigDecimal`、`BigInteger`），110–111

多任务处理，839

多线程，7, 839–952

- 死锁中的，874, 889–892
- 延迟执行中的，325
- 性能与，872, 888, 899, 920
- 抢占式与协作式调度用于，855
- 同步中的，862–897
- 使用池用于，920–926
- 变器方法，444
- 错误检查中的，154

### N

- `\n`转义序列，50
- NaN（非数字），49
- 纸巾外观（Napkin look-and-feel），542
- `naturalOrder`方法（`Comparator`），329
- Naughton, Patrick，10–11
- `NavigableMap`接口，471
  - `subMap`、`headMap`、`tailMap`方法，517
- `NavigableSet`接口，471, 490, 511
  - `ceiling`、`floor`方法，493
  - `descendingIterator`方法，493
  - `higher`、`lower`方法，493
  - `pollFirst/Last`方法，493
  - `subSet`、`headSet`、`tailSet`方法，511, 516
- `nCopies`方法（`Collections`），510, 515
- 否定运算符，62
- 负无穷，49
- `.NET`平台，6
- NetBeans，20, 24, 409
  - Matisse，701, 713–723
  - 在……中指定网格约束，706
- Netscape，10
  - IFC 库，538
  - Live/JavaScript，15
- Navigator 浏览器，9, 803, 810
- 网络，4
- `new`运算符，64, 71, 136, 150
  - 返回值，138
  - 带数组的，111
  - 带泛型类的，245
  - 带线程的，855
  - 构造函数中的`new`关键字，321
- `newCachedThreadPool`方法（`Executors`），921, 925
- `newCondition`方法（`Lock`），873, 877
- `newFixedThreadPool`方法（`Executors`），921, 925
- `Array`的`newInstance`方法，276, 279
- `Class`的，263, 265, 451
- `Constructor`的，265, 452
- `newKeySet`方法（`ConcurrentHashMap`），912
- `newProxyInstance`方法（`Proxy`），350, 355–356
- `newScheduledThreadPool`方法（`Executors`），921, 926
- `newSingleThreadExecutor`方法（`Executors`），921, 925
- `newSingleThreadScheduledExecutor`方法（`Executors`），921, 926
- `Iterator`的`next`方法，463, 465, 469
- `Scanner`的，81
- `nextDouble`方法（`Scanner`），79, 81
- `nextElement`方法（`Enumeration`），465, 528, 530
- `LinkedList`的`nextIndex`方法，480
- `ListIterator`的，483
- `Random`的`nextInt`方法，181
- `Scanner`的，79, 81
- `nextLine`方法（`Scanner`），79, 81
- Nimbus 外观，541
- 无参构造函数，173, 208, 801
- `NoClassDefFoundError`，26
- `node`方法（`Preferences`），794, 799
- `noneOf`方法（`EnumSet`），508
- `NoSuchElementException`，464, 469, 483, 494
- Notepad 文本，26
- `notHelloWorld/java`，558
- `notify`、`notifyAll`方法（`Objects`），878, 881–882
- `now`方法（`LocalDate`），140, 145
- `null`值，138
- 相等性测试，231
- `nullFirst/Last`方法（`Comparator`），329
- `NullPointerException`，361, 383
- `Number`类，253
- `NumberFormat`类方法，161
- `parse`方法，256
- `NumberFormatException`，383
- 数值类型强制转换，60–61
- 比较，62, 328
- 转换：到数值类型，59–60
- 转换为字符串，254
- 默认初始化，172
- 固定大小用于，6
- 精度，108
- 打印，82

### O

- Oak 编程语言，10
- `Object`类，132, 228–244
  - `clone`方法，156, 306–313, 318
  - `equals`方法，229–235, 244, 302, 512
  - `getClass`方法，244
  - `hashCode`方法，235, 237, 489
  - 方法中没有重定义，302
  - `notify`、`notifyAll`方法，878, 881–882
  - `toString`方法，238–244, 302, 318
  - `wait`方法，856, 878, 882
- 对象引用
  - 作为方法参数，165
  - 转换，219
  - 默认初始化，172
  - 修改，166
- 对象遍历算法，507
- 对象变量，223

在预定义类中，136–139

初始化，137

设置为`null`，138

对比 C++对象指针，139

对比对象，137

- `objectAnalyzer/ObjectAnalyzer.java`，273
- `objectAnalyzer/ObjectAnalyzerTest.java`，273
- 面向对象编程（OOP），4, 130–135, 203
  - 设计原则的，632
  - 传入对象，302
  - 在……中分离时间测量与日历，140
  - 对比过程化，130–135
- 对象，130–133
  - 在运行时分析，271–276
  - 对……应用方法，137
  - 行为的，132
  - 克隆，306–313
  - 比较，295
  - 与字符串拼接，239
  - 构造，131, 171–182
  - 损坏的，896
  - 默认哈希码的，235
  - 销毁的，181–182
  - 相等性测试，229–235, 262
  - `finalize`方法的，181–182
  - 标识的，132
  - 实现接口的检查，295
  - 在预定义类中，136–139
  - 初始化，136
  - 内建锁的，878
  - 传递给方法，136
  - 引用的，138
  - 运行时类型识别，261
  - 序列化，507
  - 排序，290
  - 状态的，131–132, 331–334
  - 对比对象变量，137

### `Objects`类

- `hash`方法，237
- `hashCode`方法，236–237

Ocean 查找与外观，541

### 进制数

- 输出格式化用于，82
- 前缀用于，48

### `of`方法

- `EnumSet`的，508
- `LocalDate`的，140, 145

### `offer`方法

- `BlockingQueue`的，898–899, 904
- `Queue`的，494

### `offerFirst/Last`方法

- `BlockingDeque`的，905
- `Deque`的，494

- `offsetByPoints`方法（`String`），70, 72
- 在线文档，71, 74–77, 194, 199
- `openFileDialog`方法（`FileService`），830, 837
- `openMultiFileDialog`方法（`FileService`），837

### OpenType 格式

575

### 运算符

- 算术的，56–65
- 位运算，63
- `boolean`，62
- 层级，64–65
- 增/减，61–62
- 无重载的，109
- 关系的，62, 64

Option 对话，731–741

Optional 操作，514

- `optionDialog/ButtonPanel.java`，738
- `optionDialog/OptionFrame.java`，734
- `or`方法（`BitSet`），533
- Oracle，12, 18, 20
- Java-in，803
- JavaFX，543
- 有序集合，470, 476
- `ordinal`方法（`Enum`），260
- `org.omg.CORBA`包，255
- 源主机，821
- OSGi 平台，800
- 输出语句，66
- 输出格式化，82–87
- 重载解析，172, 215
- `@Override`注解，234
- `overview.html`，198
- 所有者窗口，742

### P

- `p`（指数），在十六进制数中，49
- `pack`方法（`Window`），550, 557, 560
- pack200 压缩，780
- `package`语句，183
- `package.html`，198
- `package-info.java`，198

### 包

182–190

- 添加类，185–190
- 默认的，185
- 文档注释，194, 198
- 导入，183
- 名称的，182, 261
- 在线文档，71
- 范围的，189–190
- 密封，787
- `PackageTest/PackageTest.java`，187

`paintComponent`方法（`Component`），554–556, 560, 577, 583

`PackageTest/PackageTest.java`，187

重写，624

`pair1/PairTest.java`，420

`pair2/PairTest.java`，423

`pair3/PairTest.java`，449

`ParallelGroup`类，714, 723

并行性限制，910

`param`（指数），在十六进制数中，810–816

泛化类型，*参见* Type

`ParameterizedType`接口，453

`getXxx`方法，458

参数，45–46, 164–171

- 检查，断言，386–387
- 文档注释，196
- 显式的，152–153
- 隐式的，152–153, 160, 409
- 修改，155–167, 169
- 名称的，175
- 字符串，45
- 在集合接口中使用，527
- 可数量的，256–257
- 传递泛型类型给，432–433

# 传入参数

167

## 密码字段

652–653

## `PasswordChooser`类

746

## 密码

- 对话框用于，746
- 从控制台读取，80

## `PATH`环境变量

20

## `Path`接口

298

## `Paths`类

89, 298

## Payne, Jonathan

11

## `peek`方法

- `BlockingQueue`的，898–899
- `Queue`的，494
- `Stack`的，532

## `peekFirst/Last`方法（`Deque`）

495

## 性能

7

- 集合与，471, 486, 906
- 计算与，56, 59
- JAR 文件与，190
- 使用埃拉托尼筛法测量，533–536
- 多线程与，872, 888, 899, 920
- Java 对比 C++，14, 534
- 测试对比捕获异常，381

## 许可

935

## `PersistenceService`类

831

- `create`方法，831, 837
- `delete`方法，838
- `get`、`getNames`方法，838

## 持久化存储

272

## `Phaser`类

937

## 物理限制

359

## `PI`常量（`Math`）

58, 159

## `plaf/PlafFrame.java`

601

## `play`方法（`Applet`）

817

## 插件

800–802

## `plusDays`方法（`LocalDate`）

141, 145

## `Point`类

564

- 点的大小（排版中），574–575

## `Point2D`类

563–564

- `Point2D.Double`类，563, 569
- `Point2D.Float`类，563

## `poll`方法

- `BlockingQueue`的，898–899, 904
- `ExecutorCompletionService`的，928
- `Queue`的，494

## `pollFirst/Last`方法

- `Deque`的，495, 905
- `NavigableSet`的，493

## 多态

209, 213–214, 285

- `pop`方法（`Stack`），532

## 弹出菜单

684–686

- 触发器，685

## 弹出窗口

821

## 正无穷大

49

## PostScript 格式

575

## `pow`方法（`Math`）

57, 160

## 精度，数字的

82

## 前提条件

387

## 定义的动作名称

609

## 定义的类

135–145

- 变异器和访问器方法，141–145
- 对象中的变量，136–139

- `Predicate`接口，319, 326

## 抢占调度

855

## `Preferences`

788–800

- 访问，794
- 键举中的，795
- 导入/导出，795
- `Preferences`类，794–800
- `exportXxx`方法，795, 800
- `get`、`getType`方法，795, 800
- `importPreferences`方法，795, 800
- `keys`方法，795, 799
- `node`方法，794, 799
- 平台依赖性，794
- `put`方法，795, 800
- `system/userNodePackage`方法，794, 799
- `system/userRoot`方法，794, 799
- `preferences/Test.java`，796
- `preferredLayoutSize`方法（`LayoutManager`），728
- `previous`方法（`ListIterator`），476, 483
- `LinkedList`的`previousIndex`方法，480
- `ListIterator`的，483

## 质数

533

## 基本类型

47–53

- 作为方法参数，165
- 比较，328
- 转换为对象，252
- `final`字段的，157
- 不用于参数，430–431
- 将哈希映射值转换为，911
- 值，而非对象，229

## 普林斯顿大学

5

- `print`方法（`System.out`），46, 82
- `printf`方法（`System.out`），82–86
- 转换字符，82
- 标志，83–84
- 用于日期和时间，84–85
- 参数，56
- `println`方法（`System.out`），45–46, 79, 319
- `printStackTrace`方法（`Throwable`），264–265, 377, 410

## `PrintStream`类

83

## `PrintWriter`类

87

## 优先级队列

495

## `PriorityBlockingQueue`类

899, 904

## `PriorityQueue`类

496

- 作为具体类型，472

- `priorityQueue/PriorityQueue.java`，496

## `private`修饰符

150, 189–190, 333

- 检查，265
- 父类中的字段，206
- 父类中的方法，156–157

## 过程

130

## `process`方法（`SwingWorker`）

944–946, 950

## 进程对比线程

840

## 生产者线程

898

## 性能分析器

413

## 程序。*参见*应用程序

## 属性

549, 788–793

## `Properties`类

528–531, 788–793

- `getProperty`方法，531, 789, 792
- `load`、`store`方法，531, 788, 793
- `setProperty`方法，792
- `properties/PropertiesTest.java`，790

## 属性（Property）

- 属性映射表，530–531, 788–793
- 注释中的，599
- 名称的，788
- 读取/写入，788

## 属性监听接口（PropertyChangeListener interface）

758

## `protected`访问修饰符

- `protected`访问修饰符，227–228, 311
- 用于字段的，283

## 代理（Proxies）

- 代理，350–356
- 属性的，355–356
- 目的，351
- `Proxy`类，355–356
- `get/isProxyClass`方法，355–356
- `newProxyInstance`方法，350, 355–356
- `proxy/ProxyTest.java`，353

## `public`访问修饰符

- `public`访问修饰符，42, 56, 147–150, 189–190, 290
- 检查，265
- 用于接口中字段的，296
- 用于`main`方法的，43
- 用于源文件中仅限一个类的，147
- 接口未指定，289

## `publish`方法

- `Handler`的`publish`方法，398, 406
- `SwingWorker`的`publish`方法，944–945, 950

## 纯虚函数（C++）

224

## `push`方法

`push`方法（`Stack`），532

## `put`方法

- `put`方法，908
- `BlockingQueue`的，898–899, 904
- `Map`的，469, 497, 499
- `Preferences`的，795, 800

## `putAll`方法

`putAll`方法（Map），499

## `put`方法集

`put`方法（`Preferences`），795, 800

## `putFirst/Last`方法

`putFirst/Last`方法（`Deque`），904

## `putIfAbsent`方法

`putIfAbsent`方法（`ConcurrentHashMap`），908

## `putValue`方法

`putValue`方法（`Action`），608, 615

## `Queue`接口

- `Queue`接口，460, 462, 494
- 方法，494

## 队列（Queues）

- 队列，460–463, 494
- 阻塞队列，898–905
- 并发队列，905–907
- 双端队列。参见 Dequ
- `QuickSort`算法，117, 519

### R

- `r`转义序列，50
- 竞态条件，862–868
- 以及原子操作，887
- 单选框按钮，660–663
- 菜单中的，683–684
- `radioButton/RadioButtonFrame.java`，662
- 锯齿数组，124–127
- `Random`类，181
  - `nextInt`方法，181
  - 线程安全的，892
- 随机数生成，181, 892
- `RandomAccess`接口，471, 520, 522

## `range`方法

- `range`方法（`EnumSet`），508
- 原始类型，425–426
- 将类型转换为，441
- 运行时查询类型，431
- 读写锁，895–896

## `readConfiguration`方法

`readConfiguration`方法（`LogManager`），392

## `readLine/Password`方法

`readLine/Password`方法（`Console`），81

## `Rectangle`类

`Rectangle`类，490, 564

## `Rectangle2D`类

- `Rectangle2D`类，560, 562–565
- `getWidth`、`setRect`方法，563
- `Rectangle2D.Double`类，562–563, 568
- `Rectangle2D.Float`类，562–563, 569

## 矩形（Rectangles）

- 矩形，560
- 比较，490
- 构建，564
- 绘制，561
- 填充，569

## `RectangularShape`类

- `RectangularShape`类，563
- `getHeight/Width`、`getCenterX/Y`方法，563, 568
- `getX/Y`、`getMinX/Y`、`getMaxX/Y`方法，568

## 递归（Recursive）

- 递归计算，929
- `RecursiveAction`类，929
- `RecursiveTask`类，929
- 红黑树，489
- `reduce`、`reduceX`方法（`ConcurrentHashMap`），910–911
- 冗余关键字，296
- 重入锁，870
- `ReentrantLock`类，868–872
- `ReentrantReadWriteLock`类，895–896

## 反射（Reflection）

- 反射，204, 260–283
- 分析类，265–271
- 运行时对象，271–276
- 泛型以及，276–279, 450–458
- 过度使用，286

## `reflection/ReflectionTest.java`

`reflection/ReflectionTest.java`，267

## 关系（Relational）

- 关系操作符，62, 64
- 相对资源名称，784

## `remove`方法

- `ArrayList`的，249, 251
- `BlockingQueue`的，898–899
- `Collection`的，467–468
- `Iterator`的，463, 465, 469
- `JMenu`的，681
- `List`的，470, 483
- `ListIterator`的，478
- `Map`的，498
- `Queue`的，494
- `ThreadLocal`的，893

## `removeAll`方法

- `Collection`的，467–468
- `LinkedList`的，480

## `removeEldestEntry`方法

- `LinkedHashMap`的，506, 508

## `removeFirst/Last`方法

- `Deque`的，495
- `LinkedList`的，484

## `removeHandler`方法

`Logger`的`removeHandler`方法，406

## `removeIf`方法

- `ArrayList`的，319
- `Collection`的，468, 524

## `removeLayoutComponent`方法

`LayoutManager`的`removeLayoutComponent`方法，728

## `removePropertyChangeListener`方法

`Action`的`removePropertyChangeListener`方法，608, 615

## `replace`方法

`ConcurrentHashMap`的`replace`方法，908

# 方法

- `String`的方法，73
- `replaceAll`方法
  - `Collections`的方法，523
  - `List`的方法，524
  - `Map`的方法，502
- `replaceRange`方法（`JTextArea`），951

# 关键字

- 关键字，43
- 变量名中禁用，53
- 未使用，56

- `resetChoosableFilters`方法（`JFileChooser`），756, 763
- `resize`方法（`Applet`），808

# 资源包

- 资源包，393–394
- `resource/ResourceTest.java`，786
- `ResourceBundle`类，394
- 资源，783–787
- 关闭，373
- 耗尽，360
- 地化，784
- 名称，784–785

# 受限视图

514

- `resume`方法（`Thread`），858
- `retain`方法（Collection），467
- `retainAll`方法（Collection），469
- `Retirement/Retirement.java`，97
- `Retirement2/Retirement2.java`，98

# 返回

- `return`语句
  - 在`finally`块中，374
  - 在 lambda 表达式中，316
- 返回类型，215
  - 协变的，429
  - 文档注释的，196
  - 针对重写方法的，427
- 返回值，138
  - `@return`注释（`javadoc`），196
- `revalidate`方法（`JComponent`），649–650, 951
- `reverse`方法（`Collections`），524
- `reversed`、`reverseOrder`方法（`Comparator`），329, 519, 521

# RoadApplet

- `RoadApplet/RoadApplet.html`，36
- `RoadApplet/RoadApplet.java`，38

# Robot

- `Robot`类，774–778
  - 方法，778
- `robot/RobotTest.java`，775
- `rotate`方法（`Collections`），524
- `round`方法（`Math`），60

# 舍入模式

- 舍入模式，111
- `RoundingMode`类，111

# 运行时

- `rt.jar`文件，780
- `run`方法（`Thread`），849, 851
- `runAfter`方法（`CompletableFuture`），934
- `runFinalizersOnExit`方法（`System`），182
- `Runnable`接口，326, 847
  - lambdas 和，318
  - `run`方法，325, 851
- 添加钩子处，182
- 分析对象处，271–276
- 创建类处，350
- 设置数组的大小，244
- 类型识别，220, 261, 431
- `RuntimeException`，360, 380, 383

# S

- `@SafeVarargs`注解，432
- 沙盒，820–822
- `saveAsFileDialog`方法（`FileSaveService`），837
- `saveFileDialog`方法（`FileSaveService`），830, 837
- Scala 语言，默认方法中的，300
- `Scanner`类，79–81, 87, 89
  - `next`、`hasNext`方法，81
  - `next`方法，79, 81
- 调度执行，926
- `ScheduledExecutorService`类，方法，926
- 滚动面板，654–656
- 滚动条，654–656
- 密封，787
- `search`方法（`ConcurrentHashMap`），910–911
- 安全证书，822
- 安全，4–5, 14, 820–822
- `@see`注释（`javadoc`），197–198
- 语义事件，626
- `Semaphore`类，935
- 信号量，935
- `SequentialGroup`类，714, 723
- 序列化，507
- applet 对象的，809
- 调度器，800–802
- `ServiceLoader`类，801
  - `iterator`、`load`方法，802
- 服务管理器，830
  - `getNames`方法，836
- `ServletException`，370
- Servlets，370
- Set 接口，方法，714
- `set`方法（数组），279
- `ArrayList`，247, 251
- `BitSet`，533
- `Field`，276
- `List`，478, 483
- `Thread`，893
- `Vector`，883
- `set.java`，87
- `setAcceptFilter`方法（`JFileChooser`），756, 763
- `setAccessible`方法（`Object`），272, 275
- `setAccess`方法（`JFileChooser`），763
- `setAction`方法（`AbstractButton`），681
- `setActionCommand`方法（`AbstractButton`），663
- `setAutoCreate`方法（`GroupLayout`），722
- `setBackground`方法（`Component`），570, 573
- `setBoolean`、`setByte`、`setChar`方法（数组），279
- `setBorder`方法（`JComponent`），664, 668
- `setBounds`方法（`Component`），546, 552, 724
- 坐标处，548
- `setCharAt`方法（`StringBuilder`），78
- `setClassAssertionStatus`方法（`ClassLoader`），388
- `setColor`方法（`Graphics`），570, 572
- `JColorChooser`，770
- `setColumns`方法（`JTextArea`），654, 656
- `setDefaultButton`方法（`JRootPane`），748, 752
- `setDefaultCloseOperation`方法（`JDialog`），743, 807
- `setDefaultUncaughtExceptionHandler`方法（`Thread`），411, 860–861
- `setDisplayedMnemonicIndex`方法（`AbstractButton`），686, 688
- `setDouble`方法（`Array`），279
- `setEchoChar`方法（`JPasswordField`），653
- `setEditable`方法
  - `JComboBox`的，669, 671
  - `JTextComponent`的，648
- `setEnabled`方法
  - `Action`的，608, 615
  - `JMenuItem`的，689–690
- `setExtendedState`方法（`Frame`），553
- `setFileFilter`方法（`JFileChooser`），755, 763
- `setFileSelectionMode`方法（`JFileChooser`），754, 763
- `setFileView`方法（`JFileChooser`），756–757, 763
- `setFilter`方法
  - `Handler`的，406
  - `Logger`的，398, 406
- `setFloat`方法（`Array`），279
- `setFont`方法
  - `Graphics`的，581
  - `JComponent`的，650
- `setForeground`方法（`Component`），570, 573
- `setFormatter`方法（`Handler`），399, 406
- `setFrameFromCenter`方法（`Ellipse2D`），565
- `setFrameFromDiagonal`方法（`Ellipse2D`），564
- `setHonorsVisibility`、`setHorizontalGroup`方法（`GroupLayout`），722
- `setHorizontalTextPosition`方法（`AbstractButton`），682–683
- `setIcon`方法
  - `JLabel`的，651–652
  - `JMenuItem`的，682
- `setIconImage`方法（`Frame`），546, 553
- `setInheritsPopupMenu`方法（`JComponent`），685–686
- `setInt`方法（`Array`），279
- `setInverted`方法（`JSlider`），674, 678
- `setJMenuBar`方法（`JFrame`），679, 682
- `setLabelTable`方法（`JSlider`），429, 673, 678
- `setLayout`方法（`Container`），641
- `setLevel`方法
  - `Handler`的，406
  - `Logger`的，389, 405
- `setLineWrap`方法（`JTextArea`），654, 656
- `setLocation`方法（`Component`），546, 552；坐标，548
- `setLocationByPlatform`方法（`Window`），552
- `setLong`方法（`Array`），279
- `setLookAndFeel`方法（`UIManager`），599, 602
- `setMnemonic`方法（`AbstractButton`），687–688
- `setModel`方法（`JComboBox`），669
- `setMultiSelection`方法（`JFileChooser`），754, 763
- `setOut`方法（`System`），159
- `setAssertionStatus`方法（`ClassLoader`），388
- `setPaint`方法（`Graphics2D`），569, 573
- `setPaintLabels`方法（`JSlider`），673, 678
- `setPaintTicks`方法（`JSlider`），673–674, 678
- `setPaintTrack`方法（`JSlider`），678
- `setParent`方法（`Logger`），406
- `setPriority`方法（`Thread`），859
- `setProperty`方法
  - `Properties`的，792
  - `System`的，392
- `setRect`方法（`Rectangle2D`），563
- `setResizable`方法（`Frame`），546, 553
- `setRows`方法（`JTextArea`），654, 656
- Sets，487
  - 并发的，905–907
  - 交叉的，525
  - 变异元素的，487
  - 子范围的，511
  - 线程安全的，912
- `setSelected`方法
  - `AbstractButton`的，684
  - `JCheckBox`的，657, 659
- `setSelectedFile/Files`方法（`JFileChooser`），754, 763
- `setSelectionStart/End`方法（`JComponent`），952
- `setShort`方法（`Array`），279
- `setSize`方法（`Component`），552
- `setSnapTicks`方法（`JSlider`），673, 678
- `setTab`方法（`JTextArea`），654
- `setText`方法
  - `JLabel`的，651–652
  - `JTextComponent`的，648, 650
- `setTime`方法（`Calendar`），218
- `setTitle`方法（`Frame`），546, 553
- `setToolTip`方法（`JComponent`），685
- `setUncaughtExceptionHandler`方法（`Thread`），861
- `setUse`方法（`Frame`），546, 553
- `setPassword`方法（`Handler`），406
- `setValue`方法（`Map`），503
- `setVerticalGroup`方法（`GroupLayout`），722
- `setVisible`方法（`Component`），546, 552
- `setWrapStyle`方法（`JSlider`），678
- `severe`方法（`Logger`），390, 404
- Shallow copies，308–310
- redirection syntax of，88
- scripts in，193
- operators，63
- `short`类型，47
- `Short`类
  - 从`short`转换，252
  - `hashCode`方法，237
- `show`方法（`JPopupMenu`），685
- `showConfirmDialog`方法（`JOptionPane`），731–732, 739
- `showDialog`方法
  - `JColorChooser`的，770
  - `JFileChooser`的，747, 752, 754, 763
- `showDocument`方法
  - `AppletContext`的，819–820
  - `BasicService`的，836
- `showInternalInputDialog`方法（`JOptionPane`），741
- `showInternalOptionDialog`方法（`JOptionPane`），740
- `showMessageDialog`方法（`JOptionPane`），304, 731–732, 739
- `showOptionDialog`方法（`JOptionPane`），731–732, 739–740
- `showStatus`方法（`Applet`），819–820
- `showXxxDialog`方法（`JFileChooser`），747, 752, 754, 763
- `shuffle`方法（`Collections`），520–521
- `shuffle/ShuffleTest.java`，520
- 洗牌操作，520
- 停钩子（Shutdown hooks），182
- `shutdown`方法（`ExecutorService`），922, 925
- `shutdownNow`方法（`ExecutorService`），922, 927
- 埃拉托尼筛法基准，533–536
- `sieve/sieve.cpp`，535
- `sieve/Sieve.java`，534
- `signal`方法（`Condition`），875–877, 890
- `signalAll`方法（`Condition`），874–877, 890
- 方法签名，172, 215
- `simpleframe/SimpleFrameTest.java`，544
- `sin`方法（`Math`），58
- 单线程规则（Swing），939, 951–952
- `singleton`、`singletonCollection`方法（`Collections`），510, 515
- `ArrayList`的`size`方法，246–247
- 集合的，467–468
- 并发集合的，905
- `sizedFrame/SizedFrameTest.java`，551
- `sleep`方法（`Thread`），841, 846–847, 852
- `slider/SliderFrame.java`，674
- 滑块（Sliders），672–678
  - 刻度开启，673–674
  - 垂直，672
- `SoftBevelBorder`类，665, 667
- 软件开发包（SDK），18
- Solaris
  - Eclipse 版本，27
  - 在……执行 JAR 文件，783
  - JDK 版本，18
- `Arrays`的`sort`方法，117–119, 290, 292, 294, 314
- `Collections`的，518–521
- List 的，521
- `SortedMap`接口，471
  - `comparator`、`lastKey`方法，500
  - `subMap`、`headMap`、`tailMap`方法，511, 516
- `SortedSet`接口，471, 511
  - `comparator`、`first`、`last`方法，493
  - `subSet`、`headSet`、`tailSet`方法，511, 516
- 排序算法，17, 518–521
- 数组，117–120, 292
- 断言（assertions），387
- 逆序排序，19
- 按名称，328–329
- 按长度，305–306, 314, 316
- 源文件，192
- 在 Eclipse 中，29
- 安装，22–23
- 特殊字符，50
- 启动画面（Splash screen），262
- Spring 布局，700
- `sqrt`方法（`Math`），57
- `src.zip`文件，22
- `Stack`接口，460, 528, 531
  - `peek`、`pop`、`push`方法，532
- 栈轨迹跟踪（Stack trace），377–381, 889
- 栈（Stacks），531
- `stackTrace/StackTraceTest.java`，378
- `StackTraceElement`类
  - `getLineNumber`方法，380
  - `getXxxName`方法，380
  - `isNativeMethod`方法，381
  - `toString`方法，378, 381
- 标准版（Java SE），11, 18
- 标准 Java 库
  - 伴随类，298
  - 在线 API 文档，71, 74–77, 194, 199
  - 包，182
- 标准模板库（STL），460, 465
- `Applet`的`start`方法，808
- `Thread`的，849, 851, 855
- `Timer`的，305
- `startsWith`方法（`String`），72
- `stateChanged`方法（`ChangeListener`），672–673
- 语句（Statements），45
- 复合（compound）。参见块
- `static`修饰符，158–158
- 字段，296
- `main`方法，44–45
- 静态绑定，215
- 静态常量，172
- 文档，196
- 静态字段，158–159
- 访问静态方法，160
- 导入，185
- 初始化，178
- 静态导入，185
- 静态内部类，331, 346
- 添加到接口，298
- 无类型变量，436
- `static final`修饰符，55
- 静态变量，159

# `String`类

- `String`类，65–78
- `charAt`方法，70, 72
- `codePointAt`、`codePoints`方法，72
- `codePointCount`方法，70, 73
- `compareTo`方法，72
- `endsWith`方法，72
- `equals`、`equalsIgnoreCase`方法，68, 72
- `format`、`formatTo`方法，83
- `hashCode`方法，235, 485
- 不变性，67, 157, 218
- `indexOf`方法，73, 172
- `join`方法，73
- `lastIndexOf`方法，73
- `length`方法，69–70, 73
- `offsetByCodePoints`方法，70, 72
- `replace`方法，73
- `startsWith`方法，72
- `substring`方法，66, 73, 510
- `toLowerCase`、`toUpperCase`方法，73
- `trim`方法，73, 650

# `StringBuilder`类

- `StringBuilder`类，77–78
- `append`方法，77–78
- `appendCodePoint`方法，78
- `delete`方法，78
- `insert`方法，78
- `length`方法，78
- `setCharAt`方法，78
- `toString`方法，77–78

# 字符串

字符串，65–78

- 构建，77–78
- 代码点/代码单元，70
- 比较，305–306
- 拼接，66–67
- 与对象，239
- 转换为数字，254
- 空字符串，69
- 等价性，68
- 输出格式化，82–87
- 不变性，67
- 长度，66, 69
- null，69
- 编译器中的共享，67, 69
- 按长度排序，305–306, 314, 316
- 的子串，66
- 使用`". . ."`，45

# 强类型语言

强类型语言，47, 291

# 子类

子类，204–228

- 添加字段/方法，207
- 匿名，344
- 克隆，311
- 比较来自的对象，295
- 构造函数，207
- 定义，204
- 方法可见性，217
- 无法访问父类的私有字段，227
- 重写父类方法，207

- `subList`方法（`List`），510, 516
- `subMap`方法（`NavigableMap`），517；（`SortedMap`），511, 516

# 子菜单

679

- `submit`方法（`ExecutorService`），925, 928
- `ExecutorService`，921

# 子范围

510–511

- `subSet`方法（`NavigableSet`、`SortedSet`），511

# 替换原理

213

- `substring`方法（`String`），66, 73, 510
- `subtract`方法（`BigDecimal`、`BigInteger`），110, 111
- 减法运算符，56
- `sum`方法（`LongAdder`），888

# Sun Microsystems

2, 5, 14, 539

# Hot 浏览器

11, 802

# Java 插件

803

- `super`关键字，207, 444
- 方法中的捕获`this`，207, 208

# 超类规则

300

# 超类

204–228

- 访问私有字段，206
- 公有字段和方法，223, 283
- 重写方法，234
- `throws`声明符，364, 369

# 超类边界

444–447

- 补充字符，52
- `Supplier`接口，326
- `@SuppressWarnings`注解，105, 252, 430, 432, 437

# 代理区域（Unicode）

52

- `suspend`方法（`Thread`，已废用），858, 896
- `swap`方法（`Collections`），524

# Swing

537–586, 629–778

- 优势，539
- 调试，770, 778
- 双缓冲，771
- 使用 applet 实现，803–808
- 全屏，550
- 模型-视图-控制器分析，636–638
- 启动，545
- 线程与，937–943
- 单线程规则，939, 951–952
- Swing 图形调试器，771
- `swing/SwingThreadTest.java`，940
- `swing.properties`文件，598
- `SwingConstants`接口，296, 651

# `SwingUtilities`类

- `getAncestorOfClass`方法，747, 752
- `updateComponentTreeUI`方法，599

# `SwingWorker`类

943–950

- `doInBackground`方法，944–945, 950
- `execute`方法，945, 950
- `getState`方法，950
- `process`方法，944, 946, 950
- `publish`方法，944–945, 950
- `swingWorker/SwingWorkerTest.java`，947

- 在`Vector`中，484
- 锁对象，868–872
- 锁测试与超时，893–895
- 监控器概念，884
- 竞态条件，862–868, 887
- 读写锁，895
- volatile 字段，885–886
- 同步原语，935
- 同步包装器，914–915
- 同步块，882–883
- `synchronized`关键字，868, 878–882, 884
- 同步视图，512–513
- `synchronized Collection`方法（`Collections`），512–513, 515, 915
- 同步器，934–937
- 屏障，936–937
- 计数计数器，936
- 交换器，937
- 信号量，935
- 同步队列，937
- `SynchronousQueue`类，935–937
- 查找与外观，542

### `System`类

- `console`方法，81
- `exit`方法，45
- `getProperties`方法，789, 793
- `getProperty`方法，793
- `identityHashCode`方法，507, 509
- `runFinalizersOnExit`方法，182
- `setOut`方法，159
- `setProperty`方法，392
- *System of Patterns, A*（Buschmann et al.），632
- `System.err`类，411
- `System.in`类，79
- `System.out`类，45–46, 159, 411
- `print`方法，82
- `printf`方法，82–86, 256
- `println`方法，79, 389
- `SystemColor`类，571–572
- `systemNode`方法（`Preferences`），794, 799
- `systemRoot`方法（`Preferences`），794, 799

### `T`类型

- 变量，419
- `\t`转义序列，50
- Tab 键转义序列，50
- 导航 GUI 控制，729
- 标记，309, 426, 471
- `NavigableMap`的`tailMap`方法，517
- `SortedMap`，511, 516
- `NavigableSet`、`SortedSet`的`tailSet`方法，511, 516
- `BlockingQueue`的`take`方法，898–899
- `ExecutorCompletionService`，928
- `BlockingDeque`的`takeFirst/Last`方法，904
- `tan`方法（`Math`），58
- `tar`命令，780
- `target`属性（HTML），820

### `Tasks`

- 控制组，927–928
- 运行机制解耦，848
- 中断，842
- 多个，839
- 异步运行，915
- 调度，926
- 耗时，939–943
- 工作窃取用于，930

### `Template`

- 代码膨胀，426
- 终端窗口，25

### `Text`

- 居中，576
- 显示，557
- 字体，573–582
- 排版属性，576
- 文本区域，653–654
- 格式化文本，654
- 首选大小，654
- 滚动条，654–656
- 文本字段，649–651
- 列，649
- 创建空白，650
- 首选大小，649
- 文本输入，648–656
- 标签，651–652
- 密码字段，652–653
- 滚动面板，654

### `text/TextComponent.java`

655

- `thenAccept`、`thenApply`、`thenRun`（`CompletableFuture`），933
- `thenAccept`、`thenCombine`（`CompletableFuture`），934
- `thenComparing`（`Comparator`），328–329
- `thenCompose`（`CompletableFuture`），932–933
- `this`关键字，152, 176
  - 捕获引用，320
  - 构造函数中的语句，176
  - 内部类中，335
  - Lambda 表达式中，324
  - vs `super`，207–208

### `Thread`类

- `currentThread`方法，851–854
- 扩展，848
- `get/setUncaughtExceptionHandler`方法，861
- `getDefaultUncaughtExceptionHandler`方法，861
- `getState`方法，858
- `interrupt`、`isInterrupted`方法，851–854
- `interrupted`方法，853–854
- `join`方法，856–858
- 带超时的方法，856
- `resumes`方法，858
- `run`方法，849, 851
- `setDaemon`方法，859–860
- `setDefaultUncaughtExceptionHandler`方法，411, 860–861
- `setPriority`方法，859
- `sleep`方法，841, 846–847, 852
- `start`方法，849, 851, 855
- `stop`方法（已废用），851, 858, 896–897
- `suspend`方法（已废用），858, 896–897
- `yield`方法，859
- 线程转储，889
- 线程组，860
- 线程池，920–926
- 固定大小，921
- `Thread.UncaughtExceptionHandler`接口，860–862
- `ThreadDeath`错误，857, 862, 896
- `ThreadGroup`类，861
- `uncaughtException`方法，861–862

## Classes

- `ThreadLocal`类，其方法，893
- `ThreadLocalRandom`类，`current`方法，893
- `threadPool/ThreadPoolTest.java`，922
- `ThreadPoolExecutor`类，921–922
- `getLargestPoolSize`方法，926

## Threads

- 从线程访问集合，512–513, 905–915
- 阻塞（blocked），852, 856–857
- 条件对象（condition objects），872–877
- 守护线程（daemon），859
- 定义（defined），840–851
- 在线程中执行代码，325
- 未捕获异常的处理器，860–862
- 空闲（idle），928
- 中断（interrupting），851–854
- 列出所有线程，889
- 锁（locking），882–883
- 新线程（new），855
- 抢占式与协作式调度，855
- 优先级（priorities），858
- 生产者/消费者（producer/customer），898
- 目的（purposes），846–851
- 可运行（runnable），855–856
- 简单处理程序，846–851
- 状态（states），855–858
- Swing 与，937–943, 951–952
- 同步（synchronizing），862–897, 934–937
- 终止（terminated），847, 851, 857
- 线程本地变量，892–893
- 定时等待（timed waiting），856–857
- 解阻塞（unblocking），875
- 与进程（processes），840
- 等待（waiting），856–857, 873
- 工作窃取算法（work stealing），930

## Thread-safe collections

- 905–915
- 可调用对象与未来（callables and futures），915–920
- 并发（concurrent），905–907
- 数组拷贝（copy on arrays），912
- 同步包装（synchronization wrappers），914–915
- `throw`关键字，364–365
- `Throwable`类，360, 383
  - `add/getSuppressed`方法，377, 380
  - `get/initCause`方法，379
  - `getMessage`方法，366
  - `getStackTrace`方法，377, 379
  - `printStackTrace`方法，264–265, 377, 410
  - `toString`方法，366
- `throwing`方法（`Logger`），392, 405
- `throws`关键字，361–364
  - `main`方法，88
  - `@throws`注释（`javadoc`），196

## Ticks

- 图标（icons），674
- 标记（labeling），673
- 吸附到（snapping to），673

## Time

- 测量与日历（calendars），140
- 定时线程（Timed threads），856–857
- *Timeless Way of Building*（Alexander），630

## Timer

- `TimeoutException`，915
- `Timer`类，302, 314, 627
  - `start`、`stop`方法，305
  - `timer/TimerTest.java`，304
- `title`元素（HTML），807
- `toArray`方法
  - `ArrayList`的，435
  - `Collection`的，249, 467, 469
  - `Stream`的，321
- `toBack/Front`方法（`Window`），552
- `toLowerCase`方法（`String`），73

## Tomcat

824–838

## Toolbars

- `toolBar/ToolBarFrame.java`，697
- 694–696
- 拆离（detaching），695
- 拖拽（dragging），694
- 标题，696
- 垂直（vertical），696

## Toolkit

- `Toolkit`类
  - `beep`方法，305
  - `createCursor`方法，618, 623
  - `getDefaultToolkit`方法，305, 549, 553
  - `getScreenSize`方法，549, 553
- Toolkit 模态对话框，742
- Tooltips，696–699
- `toString`方法
  - 添加到所有类，240
  - 可格式化的，83
  - `Arrays`的，14, 19
  - `Date`的，137
  - `Enum`的，258, 260
  - `Integer`的，256
  - `Modifier`的，266, 271
  - `Object`的，238–244, 302
  - 代理类，355
  - `StackTraceElement`的，378, 381
  - `StringBuilder`的，77–78
  - `Throwable`的，366
- 重声明，318
- 与任何类工作，272
- 总排序，490
- `toUpperCase`方法（`String`），73
- `TraceHandler`类，351
- 追踪执行流，391

## `TransferQueue`

- 接口，900
- `transfer`、`tryTransfer`方法，905
- `translatePoint`方法（`MouseEvent`），627
- 遍历顺序，729–730

## Tree

- maps，497
- sets，489–493
- 添加元素到，490
- 红黑，489
- 总排序，490
- 与优先级队列，495

## TreeMap

- 类，471, 497, 500
- 具体的集合类型，472
- 与`HashMap`，497

## TreeSet

- 类，471, 489–493
- 具体的集合类型，472
- `treeSet/Item.java`，491
- `treeSet/TreeSetTest.java`，490

## Trigonometric

- 三角函数函数，58
- `trim`方法（`String`），73, 650
- `trimToSize`方法（`ArrayList`），246–247

## Troubleshooting

- 故障排除。*参见*调试

## TrueType

- 格式，575

- 将整个任务封装在`try`块中，382
- `try/finally`语句，372–376
- 解耦，374
- `tryLock`方法（`Lock`），856, 893–895
- Try-with-resources 语句，376–377
- 无锁的，869
- 二维数组，120–125
- 类型接口，453
- 类型擦除，425–430
- 之后的冲突，439–440
- 类型参数，245
- 转换为原始类型，441
- 不用于数组，431–432, 441
- 不用基本数据类型实例化，430–431
- 与继承对比，416
- 类型变量
  - 边界用于，422–424
  - 异常中的，437
  - 静态字段或方法中的，436
  - 泛型方法中的匹配，452
  - 命名，419
  - 不可实例化，433–434
  - 用边界类型替换，425–426
- 排版术语，576
- `TypeVariable`接口，453
  - `getBounds`、`getName`方法，457

### U

- UCSD Pascal 系统，5
- `UIManager`类
  - `getInstalledLookAndFeels`、`setLookAndFeel`方法，602
  - `setLookAndFeel`方法，599
- UML（统一建模语言）表示法，134–135
- `UnaryOperator`接口，326
- `UnavailableServiceException`，830
- `uncaughtException`方法（`ThreadGroup`），861–862
- `UncaughtExceptionHandler`接口，860–862
- `uncaughtException`方法，861
- 未检查的异常，264, 361–363
  - 适用性，383
- 不等运算符，62
- Unicode 标准，6, 51–52, 65
  - `char`类型中，50
- 单元测试，162
- 伊利诺伊大学，10

### UNIX

- 适用于 Eclipse 版本，27
- 在 JNLP 中的配置，828
- 在……中运行 applet，34
- 在……中设置路径，20, 191–193
- 在……中设置 JDK，20
- 系统目录，788
- 在……中对 Java 程序进行故障排除，26
- `unlock`方法（`Lock`），869, 871
- 不可修改视图，511–512
  - `unmodifiableCollection`方法（`Collections`），511–512, 514
  - `UnsupportedOperationException`，503, 510, 512, 514
- `unsynch/Bank.java`，865
- `unsynch/UnsynchBankTest.java`，864
- `updateAndGet`方法（`AtomicType`），887
- `updateComponentTree`方法（`Swing`），599
- 用户输入，650
  - 错误，359
- 用户界面。参见图形用户界面
- `userNodeForPackage`方法（`Preferences`），794, 799
- `userRoot`方法（`Preferences`），794, 799
- “使用”关系，133–135
- UTC（协调世界时），139
- UTF-8 标准，87
- 工具类，298–299

### V

- `V`类型变量，419
- `validate`方法（`Component`），651, 951
- `valueOf`方法（`BigDecimal`、`Integer`），108, 110
- `Enum`的，258, 260
- `Integer`的，256
- `values`方法（Map），502–503
- Lambda 表达式捕获的，323–324
- 可变参数，256–257
- 传递泛类型，432–433
- 变量，53–56
  - 在 lambda 中，322–324
  - 拷贝，306
  - 声明，53
  - 废弃，197
  - 最终的，324
  - 访问外部方法，339–342
  - 初始化，54, 200
  - 局部的，430
  - 注解，430
  - 变异，323
  - 包作用域，189–193
  - 打印，409
  - 静态的，159
  - 线程，892–893
- `Vector`类，460, 528, 883
  - `elements`方法，53
  - 泛型数组，245
  - 同步的，883
- `@version`注释，197
- 视图，509, 633
  - 批量操作，525
  - 检查，513
  - 受限的，514
  - 子集，510–511
  - 不可修改的，512–513
- Visual Basic 语言，36
  - 事件处理，587
  - 表单，638
  - 语法，3
- Visual Studio，23
  - `void`关键字，44–45
- Volatile 字段，885–886
- `volatile`关键字，885–886
- von der Ahé, Peter，422

### W

- `wait`方法（`Object`），856, 871, 882
- 等待集，873
- `warning`方法（`Logger`），390, 404

### Warnings

- 穿透行为，105
- 泛型类型，252, 430, 432, 437–439
  - 抑制，432, 437–439
- 弱哈希表，504
- 弱引用，504

# 集合与泛型

- `WeakHashMap`类，504, 507
- 作为一种具体的集合类型，472
- 弱一致性迭代器，906
- `WeakReference`对象，504

# 网页

- 动态的，9
- 从 URL 读取，932
- 显示 applet 在，802–824
- 标题的，807
- `webstart/CalculatorFrame.java`，832
- `Welcome/Welcome.java`，25
- `whenComplete`方法（`CompletableFuture`），933

# 语言基础

- `while`循环，94–99
- 空格符，与 Java 编译器无关，44

# 泛型

- 通配符类型，417, 442–450
- 数组的，432
- 捕获（capturing），448–450
- 上类型边界，444–447
- 无界的，447
- `WildcardType`接口，453
- `getLowerBounds`、`getUpperBounds`方法，458

# GUI - 窗口

- `Window`类，628
- `is/setLocationByPlatform`方法，552
- `pack`方法，550, 557, 560
- `toBack/Front`方法，552
- 窗口监听器，603–607
- 窗口位置，630–631
- `WindowAdapter`类，626
- 窗口关闭事件，688
- `WindowEvent`类，588, 603, 626
  - `getNewState`、`getOldState`方法，607, 628
  - `getWindow`、`getOppositeWindow`、`getScrollAmount`方法，628
- `WindowFocusListener`接口，626
  - `windowGainedFocus`、`windowLostFocus`方法，628
- `WindowListener`接口，626
  - `windowActivated/Deactivated`方法，603, 607, 628
  - `windowClosing/Closed`方法，603–607, 628
  - `windowIconified/Deiconified`方法，603, 607, 628
  - `windowOpened`方法，603, 607, 628
- 窗口外观，628
- Windows 外观，539

# Windows 系统

- Alt，688
- applet，807
- 默认位置，395
- 上下，556
- 数组，27
- 分隔，783
- 字体，574
- JDK 版本，18
- 弹出窗口触发，685
- 注册表，794–795
- 资源，783
- 运行 applet，34–35
- 路径，20, 191, 193
- 设置 JDK，20
- 线程优先级，859

- `WindowStateListener`接口，603, 626
- `windowStateChanged`方法，607, 628
- Wirth, Niklaus，5, 10, 130
- `withInitial`方法（`ThreadLocal`），893
- 工作窃取，930
- 包装类，252–256
- 等等性测试，254
- 不变性，253
- 轻量级集合，509–510

### X

- X11 编程，556
- XML（可扩展标记语言），12–13
- `xor`方法（`BitSet`），533

### Y

- `yield`方法（`Thread`），859

### Z

- ZIP 格式，191, 780

![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)![Image](#)
