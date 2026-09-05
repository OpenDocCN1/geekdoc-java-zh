
# Core Java 卷 I：基础，第 12 版

## 4.11 类设计提示

## 第 7 章：异常、断言和日志

### 7.1 处理错误

#### 7.1.1 异常的分类

#### 7.1.2 声明受检异常

#### 7.1.3 如何抛出异常

#### 7.1.4 创建异常类

### 7.2 捕获异常

#### 7.2.1 捕获异常

#### 7.2.2 捕获多个异常

#### 7.2.3 重新抛出和异常链

#### 7.2.4 `finally` 子句

#### 7.2.5 `try`-with-Resources 语句

#### 7.2.6 分析堆栈轨迹元素

### 7.3 使用异常的技巧

### 7.4 使用断言

#### 7.4.1 断言概念

#### 7.4.2 断言的启用与禁用

#### 7.4.3 使用断言进行参数检查

#### 7.4.4 使用断言记录假设

### 7.5 日志

#### 7.5.1 基础日志

#### 7.5.2 高级日志

#### 7.5.3 更改日志管理器配置

#### 7.5.4 本地化

#### 7.5.5 处理器（`Handlers`）

#### 7.5.6 过滤器（`Filters`）

#### 7.5.7 格式化器（`Formatters`）

##### 7.5.8 配方（`Recipe`）

### 7.6 调试技巧

## 第 8 章：泛型编程

### 8.1 为什么用泛型编程？

#### 8.1.1 类型参数的优势

#### 8.1.2 谁想做泛型程序员？

### 8.2 定义一个简单的泛型类

### 8.3 泛型方法

### 8.4 类型变量的边界

### 8.5 泛型代码与虚拟机

#### 8.5.1 类型擦除（`Type Erasure`）

#### 8.5.2 翻译泛型表达式

#### 8.5.3 翻译泛型方法

#### 8.5.4 调用遗留代码

### 8.6 限制与局限性

#### 8.6.1 类型参数不能用基本类型实例化

#### 8.6.2 运行时查询仅对原始类型有效

#### 8.6.3 你不能创建参数化类型的数组

#### 8.6.4 可变参数警告

#### 8.6.5 你不能实例化类型变量

#### 8.6.6 你不能构造泛型数组

#### 8.6.7 类型变量在泛型类的静态文中无效

#### 8.6.8 你不能抛出或捕获泛型类的实例

#### 8.6.9 你可以绕过受检异常检查

#### 8.6.10 警惕擦除后的冲突

### 8.7 泛型类型的继承规则

### 8.8 通配符类型

#### 8.8.1 通配符概念

#### 8.8.2 通配符的上类型边界

#### 8.8.3 无界通配符

#### 8.8.4 通配符捕获

### 8.9 反射与泛型

#### 8.9.1 泛型 `Class` 类

#### 8.9.2 使用 `Class<T>` 参数进行类型匹配

#### 8.9.3 虚拟机中的泛型类型信息

#### 8.9.4 类型字面量

### 9.5 拷贝与视图

#### 9.5.1 小型集合

#### 9.5.2 不可修改拷贝与视图

#### 11.2.2 边界布局

### 12.4.7 为什么 `stop()` 和 `suspend()` 方法已弃用

### 12.4.8 按需初始化

- 图形用户界面设计
- 并发处理

正如许多计算机书籍中一样，我使用`等宽字体`来表示计算机代码。

---

### 1.2.1 简单

我们希望构建一个易于编程、无需大量晦涩训练且能利用当今标准实践的系统。因此，尽管我们发现 `C++` 并不合适，但我们将 `Java` 设计得尽可能接近 `C++`，以使系统更易于理解。`Java` 略了 `C++` 中许多使用频率低、难以理解且令人困惑的特性，根据我们的经验，这些特性带来的麻烦多于收益。

`Java` 的语法确实是 `C++` 语法的精简版。它不需要头文件、指针算术（甚至不需要指针语法）、结构体、联合体、运算符重载、虚基类等。（参穿于全文的 `C++` 注释以了解更多关于 `Java` 与 `C++` 之间的差异。）然而，设计者并没有试图修复 `C++` 的所有笨拙特性。例如，`switch` 语句的语法在 `Java` 中保持不变。如果你熟悉 `C++`，你会会发现过渡到 `Java` 语法非常容易。

`Java` 旨在编写在各种方面必须可靠的程序。`Java` 非常强调对可能问题的早期检查、后期的动态（运行时）检查，以及消除易出错的情况。……`Java` 与 `C/C++` 之间最大的区别是 `Java` 拥有一种指针模型，它消除了覆盖内存和损坏数据的可能性。

`Java` 编译器可以检测许多在其他语言中只会在运行时出现的问题。至于第二点，任何花费数小时追踪由指针 bug 引起的内存损坏的人都会对 `Java` 的这一方面感到非常高兴。

### 1.4 Java 简介

表 1.1](#ch01.xhtml_ch01tab01) 展示了 Java 语言和库的演变。

没有任何像 Java 这样强大的编程语言是容易的。你总是需要区分编写练习程序的易易程度与完成正式工作的困难程度。此外，请注意，书中只有七个章节讨论了 Java 语言。两卷书中的其余章节都展示了如何使用 Java 库来工作。Java 库包含了成千上万的类、接口以及数万个函数。幸运的是，你不需要了解其中的每一个一个，但为了用 Java 完成任何实际任务，你确实需要了解非常多它们。

*Java 将成为适用于所有平台的通用编程语言。*

*通过 Java，可以用廉价的“网络设备”代替我的台式电脑。*

当 Java 最初发布时，有些人曾大注这将会发生。公司生产了 Java 驱动的网络计算机原型，但用户尚未准备好放弃强大且方便的台式电脑，转向一台没有本地存储的限制机器。如今，世界已经变了，对于绝大多数终端用户来说，重要的平台是手机或平板电脑。这些设备大部分由 `Android` 平台控制。学习 Java 编程也将对你的 Android 编程有所帮助。

并按 Enter 键。你应该会看到如下显示：

```
javac 17.0.4
```

```
cd javasrc
jar xvf jdk/lib/src.zip
cd ..
```

```
63          var exitItem = new JMenuItem("Exit");
```

**图 2.8** Eclipse 中的错误消息

当然，让质量保证工程师（他们通常工作过度，且并不总是 Java 细微之处的专家）对 bug 报告做出可疑决定是令人沮丧的。但令人的是，在 Java 开源之前，这些 bug 报告及其解决方案就已经供任何人审查了。

浮点类型表示带有小数部分的数字。两种浮点类型如表 3.2 所示。

更隐险的是，你必须警惕注释中的 `\u`。注释

---

```
Box box; // "Box" 是类型，"box" 是变量名
```

---

```
Math.log10
```

**图 3.1** 数值类型之间的合法转换

![Image](img/note.jpg) **注意：**

```
String rating = "PG" + age;
```

---

```
if (greeting.compareTo("Hello") == 0) . . .
```

获取真实长度——即代码点的数量——调用

- `String stripLeading()` 11
- `insert(int offset, char c)` 在 `offset` 处插入代码单元并返回 `this`。
- 如果文本块以引号结尾

打印

---

在这里，我们指定了 UTF-8 字符编码，这是互联网文件的常用（但并非通用）编码。当你读取文本文件时，需要知道字符编码（更多信息请参见第二卷第 2 章）。如果你省略了字符编码，则将使用运行 Java 程序的计算机的“默认编码”。这不是好主意——程序的行为可能会根据运行位置的不同而有所不同。

```
performance = "Satisfactory";
bonus = 100;
```

在这段代码中，当 `yourSales` 大于或等于 `target` 时，大括号内的所有语句都将被执行（参见图 3.7）。

![Image](img/note.jpg) **注意：**

块（有时被称为 `compound statement`，复合语句）允许你在任何其他允许单个（简单）语句的 Java 编程结构中使用多个（简单）语句。

Java 中更通用的条件语句形式如下所示（参见图 3.8）：

```
if (condition) statement1 else statement2
```

例如：

```
if (yourSales >= target)
{
    performance = "Satisfactory";
    bonus = 100 + 0.01 * (yourSales - target);
}
```

![Images](img/03fig07.jpg)

**图 3.7** `if` 语句的流程图

```
else
{
    performance = "Unsatisfactory";
    bonus = 0;
}
```

`else` 部分总是可选的。`else` 与距离最近的 `if` 组合。因此，在语句：

```
if (x <= 0) if (x == 0) sign = 0; else sign = -1;
```

`else` 属于第二个 `if`。当然，使用大括号来澄清这段代码是一个好主意：

```
if (x <= 0) { if (x == 0) sign = 0; else sign = -1; }
```

重复的 `if . . . else if . . .` 替代方案很常见（参见图 3.9）。例如：

![Images](img/03fig08.jpg)

**图 3.8** `if/else` 语句的流程图

```
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
}
```

![Images](img/03fig09.jpg)

**图 3.9** `if/else if`（多分支）的流程图

### 3.8.3 循环

`while` 循环在条件为 `true` 时执行执行语句（可以是块语句）。其通用形式为：

```
while (condition) statement
```

如果条件开始时为 `false`，则 `while` 循环将永远不会执行（参见图 3.10）。

![Images](img/03fig10.jpg)

**图 3.10** `while` 语句的流程图

列表 3.3 中的程序确定了为你辛苦换来的退休储蓄特定金额需要多久，假设你每年存款相同的金额，并且资金按指定的利率产生。在示例中，我们在循环体中增加计数器并更新当前累积的金额，直到总额超过目标金额。

```
while (balance < goal)
{
    balance += payment;
    double interest = balance * interestRate / 100;
    balance += interest;
    years++;
}
System.out.println(years + " years.");
```

（不要依赖这个程序来规划你的退休生活。它缺少一些细节，如通货膨胀和你的预期寿命。）

`while` 循环在顶部进行测试。因此，块中的代码可能永远不会执行。如果你想确保一个块至少执行一次，你需要使用 `do/while` 循环将测试移到底部。它的语法如下：

`do` `statement` `while (`condition`);

此循环执行 `statement`（通常是一个块）并仅测试 `condition`。如果条件为 `true`，它会重复执行 `statement` 并重新测试 `condition`，依此类推。列表 3.4 中的代码计算你退休账户中的新余额，并询问你是否已准备好退休：

```
do
{
    balance += payment;
    double interest = balance * interestRate / 100;
    years++;
    // print current balance
    // . . .
    // ask if retire and get input
    // . . .
} (input.equals("N"));
```

只要回答 `"N"`，循环就会重复（参见图 3.1）。这个程序是一个至少进入一次的循环示例，因为用户在决定是否足够退休之前需要看到余额。

![Images](img/03fig11.jpg)

**图 3.11** `do/while` 语句的流程图

**列表 3.3** `Retirement/Retirement.java`

```
1 import java.util.*;
2 
3 /**
4 * 这个程序演示了一个 `while` 循环。
5 * @version 1.20 2004-02-10
6 * @author Cay Horstmann
7 */
8 public class Retirement
9 {
10  public static void main(String[] args)
11  {
12    // read inputs
13    Scanner in = new Scanner(System.in);
14  
15    System.out.print("How much money do you need to retire? ");
16    double goal = in.nextDouble();
17  
18    System.out.print("How much money will you contribute every?");
19    double payment = in.nextDouble();
20  
21    System.out.print("Interest rate in %: ");
22    double interestRate = in.nextDouble();
23  
24    double balance = 0;
25    int years = 0;
26  
27    // update account balance while goal isn't reached
28    while (balance < goal)
29    {
30       // add this year's payment and interest
31       balance += payment;
32       double interest = balance * interestRate / 100;
33       balance += interest;
34       years++;
35    }
36  
37    System.out.println("You can retire in " + years + " years.");
38  }
39 }
```

**列表 3.4** `Retirement2/Retirement2.java`

```
1 import java.util.*;
2  
3 /**
4 * 这个程序演示了一个 `do/while` 循环。
5 * @version 1.20 2004-02-10
6 * @author Cay Horstmann
7 */
8 public class Retirement2
9 {
10  public static void main(String[] args)
11  {
12    // read inputs
13    Scanner in = new Scanner(System.in);
14  
15    System.out.print("How much money do you need retire? ");
16    double goal = in.nextDouble();
17    
18    System.out.print("How much money will money contribute every?");
19    double payment = in.nextDouble();
20  
21    System.out.print("Interest rate in %: ");
22    double interestRate = in.nextDouble();
23  
24    double balance = 0;
25    int years = 0;
26  
27    // update account balance while goal isn't reached
28    while (balance < goal)
29    {
30       // add this year's payment and interest
31       balance += payment;
32       double interest = balance * interestRate / 100;
33       balance += interest;
34       years++;
35    }
36  
37    System.out.println("You can retire in " + years + " years.");
38  }
39 }
```

### 3.8.4 确定循环



# `for` 循环

`for` 循环是一种通用的结构，用于支持由计数器或在每次迭代后更新的变量控制的迭代。如图 3.12 所示。

```
System.out.println(i);
```

`for` 语句的第一个槽位通常存放计数器的初始化。第二个槽位是在每次循环新循环之前测试的条件，第三个槽位指定了如何更新计数器。

尽管 Java 像 C++ 一样，允许在 `for` 循环的各个槽位中使用几乎任何表达式，但良好的编程习惯有一条不成文的规定：这三个槽位应该只初始化、测试和更新同一个计数器变量。忽视这一规则可能会写出非常晦涩的循环。

![Images](img/03fig12.jpg)

**图 3.12** `for` 语句的流程图

即使在良好习惯的范围内，仍有许多可能。例如，你可以编写递减计数循环：

```
for (int i = 10; i > 0; i--)

    System.out.println("Counting down . . . " + i);

System.out.println("Blastoff!");
```

* * *

![Image](img/caution.jpg) **注意：**

在循环中测试浮点数的相等性时要小心。像下面这样的 `for` 循环

```
for (double x = 0; x != 10; x += 0.1) . . .
```

可能永远不会结束。由于舍入误差，最终值可能无法精确到达。在这个例中，`x` 会从 `9.99999999999998` 跳到 `10.09999999999998`，因为 0.1 没有精确的二进制表示。

* * *

当你在 `for` 语句的第一个槽位声明变量时，该变量的作用域一直持续到 `for` 循环体的结束。

```
for (int i = 1; i <= 10; i++)

{

    . . .

}

// i 在此处不再定义
```

特别是，如果你在 `for` 语句内部定义变量，则不能在循环外部使用它的值。因此，如果你想在 `for` 循环外部使用循环计数器的最终值，请确保在循环头之外声明它。

```
int i;

for (i = 1; i <= 10; i++)

{

    . . .

}

// i 在此处仍然定义
```

另一方面，你可以在不同的 `for` 循环中定义同名的变量：

```
for (int i = 1; i <= 10; i++)

{

    . . .

} . . .

for (int i = 11; i <= 20; i++) // 定义另一个名为 i 的变量是允许的

{

    . . .

}
```

`for` 循环只是 `while` 循环的一种便利快捷方式。例如，

```
for (int i = 10; i > 0; i--)

    System.out.println("Counting down . . . " + i);

int i = 10;

while (i > 0)

{

    System.out.println("Counting down . . . " + i);

    i--;

}
```

列表 3.5 显示了一个典型的 `for` 循环示例。

程序计算中奖票的概率。例如，如果你必须从 1 到 50 的数字中选出 6 个数字来中奖，那么有 (50 × 49 × 48 × 47 × 46 × 45)/(1 × 2 × 3 × 4 × 5 × 6) 种可能的结果，因此你的机会是 15,890,700 分之一。祝你好运！

通常情况下，如果你从 `n` 个数字中选出 `k` 个，会有

![Images](img/097equ01.jpg)

种可能的结果。下面的 `for` 循环计算该值：

```
int lotteryOdds = 1;

for (int i = 1; i <= k; i++)

    lotteryOdds = lotteryOdds * (n - i + 1) / i;
```

* * *

![Image](img/note.jpg) **注：**

第 3.10.3 节，“‘for each’ 循环”位于第 112 页描述了“广义 `for` 循环”（也称为“for each”循环），它使得访问数组或集合中的所有元素变得方便。

* * *

**列表 3.5** `LotteryOdds/LotteryOdds.java`

```
 1  import java.util.*;

 2

 3  /**

 4    * 此程序演示了一个 <code>for</code> 循环。

 5    * @version 1.20 2004-02-10

 6    * @author Cay Horstmann

 7    */

 8  public class LotteryOdds

 9  {

10     public static void main(String[] args)

11     {

12         Scanner in = new Scanner(System.in);

13         System.out.print("How many numbers do you need to draw? ");

14         int k = in.nextInt();

15

16         System.out.print("What is the highest number you can draw? ");

17         int n = in.nextInt();

18

19         /*

20           计算中奖概率

21         */

22         int lotteryOdds = 1;

23

         for (int i = 1; i <= k; i++)

24             lotteryOdds = lotteryOdds * (n - i + 1) / i;

25

26         System.out.println("Your odds are 1 in " + lotteryOdds + ". Good luck!");

27     }

28 }
```

## 使用 `switch` 进行多选择

`if/else` 结构在处理多个分支时可能非常繁琐。`switch` 语句使得情况变得更容易，特别是当有多个分支时。像图 3.13 所示，`switch` 在 Java 14 中引入了如下形式：

```
String input = ...;

switch (input.toLowerCase())

{

    case "yes" ->

        ...

    case "no" ->

        ...

    default ->

        ...

}
```

`switch` 语句可以跟

- `char`、`byte`、`short` 或 `int` 类型的常量表达式
- 枚举类型
- 字符串字面量
- 多个用逗号分隔的这些

例如，

```
int choice = ...;

switch (choice)

{

    case 1:

        ...;

    case 2:

        ...;

    case 3:

        ...;

    case 4:

        ...;

    default:

        ...;

}
```

`switch` 的“经典”形式追溯到 Java 1.0。它的形式如下：

```
int choice = ...;

switch (choice)

{

    case 1:

        ...;

        break;

    case 2:

        ...;

        break;

    case 3:

        ...;

        break;

    case 4:

        ...;

        break;

    default:

        ...;

        break;

}
```

![Images](img/03fig13.jpg)

**图 3.13** `switch` 语句的流程图

`case` 标签可以跟

- 匹配 `switch` 表达式的值
- `default` 句（如果存在）

执行从匹配的 `case` 标签开始，直到遇到 `break` 或 `switch` 的结束。如果没有任何 `case` 标签匹配，则执行 `default` 句。



`for` 语句的第一个槽位通常存放计数器的初始化。第二个槽位是在每次循环新循环之前测试的条件，第三个槽位指定了如何更新计数器。

尽管 Java 像 C++ 一样，允许在 `for` 循环的各个槽位中使用几乎任何表达式，但良好的编程习惯有一条不成文的规定：这三个槽位应该只初始化、测试和更新同一个计数器变量。忽视这一规则可能会写出非常晦涩的循环。

![Images](img/03fig12.jpg)

**图 3.12** `for` 语句的流程图

即使在良好习惯的范围内，仍有许多可能。例如，你可以编写递减计数循环：

```
for (int i = 10; i > 0; i--)
    System.out.println("Counting down . . . " + i);
System.out.println("Blastoff!");
```

* * *

![Image](img/caution.jpg) **注意：**

在循环中测试浮点数的相等性时要小心。像下面这样的 `for` 循环

```
for (double x = 0; x != 10; x += 0.1) . . .
```

可能永远不会结束。由于舍入误差，最终值可能无法精确到达。在这个例中，`x` 会从 `9.99999999999998` 跳到 `10.09999999999998`，因为 0.1 没有精确的二进制表示。

* * *

当你在 `for` 语句的第一个槽位声明变量时，该变量的作用域一直持续到 `for` 循环体的结束。

```
for (int i = 1; i <= 10; i++)
{
    . . .
}
// i 在此处不再定义
```

特别是，如果你在 `for` 语句内部定义变量，则不能在循环外部使用它的值。因此，如果你想在 `for` 循环外部使用循环计数器的最终值，请确保在循环头之外声明它。

```
int i;
for (i = 1; i <= 10; i++)
{
    . . .
}
// i 在此处仍然定义
```

另一方面，你可以在不同的 `for` 循环中定义同名的变量：

```
for (int i = 1; i <= 10; i++)
{
    . . .
}
. . .
for (int i = 11; i <= 20; i++) // 定义另一个名为 i 的变量是允许的
{
    . . .
}
```

`for` 循环只是 `while` 循环的一种便利快捷方式。例如，

```
for (int i = 10; i > 0; i--)
    System.out.println("Counting down . . . " + i);
```

等价于

```
int i = 10;
while (i > 0)
{
    System.out.println("Counting down . . . " + i);
    i--;
}
```

列表 3.5 显示了一个典型的 `for` 循环示例。

程序计算中奖票的概率。例如，如果你必须从 1 到 50 的数字中选出 6 个数字来中奖，那么有 (50 × 49 × 48 × 47 × 46 × 45)/(1 × 2 × 3 × 4 × 5 × 6) 种可能的结果，因此你的机会是 15,890,700 分之一。祝你好运！

通常情况下，如果你从 `n` 个数字中选出 `k` 个，会有

![Images](img/097equ01.jpg)

种可能的结果。下面的 `for` 循环计算该值：

```
int lotteryOdds = 1;
for (int i = 1; i <= k; i++)
    lotteryOdds = lotteryOdds * (n - i + 1) / i;
```

* * *

![Image](img/note.jpg) **注：**

第 3.10.3 节，“‘for each’循环](#ch03.xhtml_ch3-10-3)”位于第 112 页描述了“广义 `for` 循环”（也称为“for each”循环），它使得访问数组或集合中的所有元素变得方便。

* * *

**列表 3.5** `LotteryOdds/LotteryOdds.java`

```
 1  import java.util.*;
 2
 3  /**
 4    * 此程序演示了一个 <code>for</code> 循环。
 5    * @version 1.20 2004-02-10
 6    * @author Cay Horstmann
 7    */
 8  public class LotteryOdds
 9  {
10     public static void main(String[] args)
11     {
12         Scanner in = new Scanner(System.in);
13         System.out.print("How many numbers do you need to draw? ");
14         int k = in.nextInt();
15
16         System.out.print("What is the highest number you can draw? ");
17         int n = in.nextInt();
18
19         /*
20           计算中奖概率
21         */
22         int lotteryOdds = 1;
23
         for (int i = 1; i <= k; i++)
24             lotteryOdds = lotteryOdds * (n - i + 1) / i;
25
26         System.out.println("Your odds are 1 in " + lotteryOdds + ". Good luck!");
27     }
28 }
```

#### 3.8.5 使用 `switch` 进行多选择

`if/else` 结构在处理多个分支时可能非常繁琐。`switch` 语句使得情况变得更容易，特别是当有多个分支时。像图 3.13 所示，`switch` 在 Java 14 中引入了如下形式：

```
String input = ...;
switch (input.toLowerCase())
{
    case "yes" ->
        ...
    case "no" ->
        ...
    default ->
        ...
}
```

`switch` 语句可以跟

- `char`、`byte`、`short` 或 `int` 类型的常量表达式
- 枚举类型
- 字符串字面量
- 多个用逗号分隔的这些

例如，

```
int choice = ...;
switch (choice)
{
    case 1:
        ...;
        break;
    case 2:
        ...;
        break;
    case 3:
        ...;
        break;
    case 4:
        ...;
        break;
    default:
        ...;
        break;
}
```

`switch` 的“经典”形式追溯到 Java 1.0。它的形式如下：

```
int choice = ...;
switch (choice)
{
    case 1:
        ...;
        break;
    case 2:
        ...;
        break;
    case 3:
        ...;
        break;
    case 4:
        ...;
        break;
    default:
        ...;
        break;
}
```

`case` 标签可以跟

- 匹配 `switch` 表达式的值
- `default` 句（如果存在）

执行从匹配的 `case` 标签开始，直到遇到 `break` 或 `switch` 的结束。如果没有任何 `case` 标签匹配，则执行 `default` 句。




`for` 语句的第一个槽位通常存放计数器的初始化。第二个槽位是在每次循环新循环之前测试的条件，第三个槽位指定了如何更新计数器。

尽管 Java 像 C++ 一样，允许在 `for` 循环的各个槽位中使用几乎任何表达式，但良好的编程习惯有一条不成文的规定：这三个槽位应该只初始化、测试和更新同一个计数器变量。忽视这一规则可能会写出非常晦涩的循环。

![Images](img/03fig12.jpg)

**图 3.12** `for` 语句的流程图

即使在良好习惯的范围内，仍有许多可能。例如，你可以编写递减计数循环：

```
for (int i = 10; i > 0; i--)

    System.out.println("Counting down . . . " + i);

System.out.println("Blastoff!");
```

* * *

![Image](img/caution.jpg) **注意：**

在循环中测试浮点数的相等性时要小心。像下面这样的 `for` 循环

```
for (double x = 0; x != 10; x += 0.1) . . .
```

可能永远不会结束。由于舍入误差，最终值可能无法精确到达。在这个例中，`x` 会从 `9.99999999999998` 跳到 `10.09999999999998`，因为 0.1 没有精确的二进制表示。

* * *

当你在 `for` 语句的第一个槽位声明变量时，该变量的作用域一直持续到 `for` 循环体的结束。

```
for (int i = 1; i <= 10; i++)

{

    . . .

}

// i 在此处不再定义
```

特别是，如果你在 `for` 语句内部定义变量，则不能在循环外部使用它的值。因此，如果你想在 `for` 循环外部使用循环计数器的最终值，请确保在循环头之外声明它。

```
int i;

for (i = 1; i <= 10; i++)

{

    . . .

}

// i 在此处仍然定义
```

另一方面，你可以在不同的 `for` 循环中定义同名的变量：

```
for (int i = 1; i <= 10; i++)

{

    . . .

} . . .

for (int i = 11; i <= 20; i++) // 定义另一个名为 i 的变量是允许的

{

    . . .

}
```

`for` 循环只是 `while` 循环的一种便利快捷方式。例如，

```
for (int i = 10; i > 0; i--)

    System.out.println("Counting down . . . " + i);

int i = 10;

while (i > 0)

{

    System.out.println("Counting down . . . " + i);

    i--;

}
```

列表 3.5 显示了一个典型的 `for` 循环示例。

程序计算中奖票的概率。例如，如果你必须从 1 到 50 的数字中选出 6 个数字来中奖，那么有 (50 × 49 × 48 × 47 × 46 × 45)/(1 × 2 × 3 × 4 × 5 × 6) 种可能的结果，因此你的机会是 15,890,700 分之一。祝你好运！

通常情况下，如果你从 `n` 个数字中选出 `k` 个，会有

![Images](img/097equ01.jpg)

种可能的结果。下面的 `for` 循环计算该值：

```
int lotteryOdds = 1;

for (int i = 1; i <= k; i++)

    lotteryOdds = lotteryOdds * (n - i + 1) / i;
```

* * *

![Image](img/note.jpg) **注：**

第 3.10.3 节，“‘for each’循环](#ch03.xhtml_ch3-10-3)”位于第 112 页描述了“广义 `for` 循环”（也称为“for each”循环），它使得访问数组或集合中的所有元素变得方便。

* * *

**列表 3.5** `LotteryOdds/LotteryOdds.java`

```
 1  import java.util.*;

 2

 3  /**

 4    * 此程序演示了一个 <code>for</code> 循环。

 5    * @version 1.20 2004-02-10

 6    * @author Cay Horstmann

 7    */

 8  public class LotteryOdds

9  {

10     public static void main(String[] args)

11     {

12         Scanner in = new Scanner(System.in);

13         System.out.print("How many numbers do you need to draw? ");

14         int k = in.nextInt();

15

16         System.out.print("What is the highest number you can draw? ");

17         int n = in.nextInt();

18

19         /*

20           计算中奖概率

21         */

22         int lotteryOdds = 1;

23

         for (int i = 1; i <= k; i++)

24             lotteryOdds = lotteryOdds * (n - i + 1) / i;

25

26         System.out.println("Your odds are 1 in " + lotteryOdds + ". Good luck!");

27     }

28 }
```

#### 3.8.5 使用 `switch` 进行多选择

`if/else` 结构在处理多个分支时可能非常繁琐。`switch` 语句使得情况变得更容易，特别是当有多个分支时。像图 3.13 所示，`switch` 在 Java 14 中引入了如下形式：

```
String input = ...;

switch (input.toLowerCase())

{

    case "yes" ->

        ...

    case "no" ->

        ...

    default ->

        ...

}
```

`switch` 语句可以跟

- `char`、`byte`、`short` 或 `int` 类型的常量表达式
- 枚举类型
- 字符串字面量
- 多个用逗号分隔的这些

例如，

```
int choice = ...;

switch (choice)

{

    case 1:

        ...;

        break;

    case 2:

        ...;

        break;

    case 3:

        ...;

        break;

    case 4:

        ...;

        break;

    default:

        ...;

        break;

}
```

`switch` 的“经典”形式追溯到 Java 1.0。它的形式如下：

```
int choice = ...;

switch (choice)

{

    case 1:

        ...;

        break;

    case 2:

        ...;

        break;

    case 3:

        ...;

        break;

    case 4:

        ...;

        break;

    default:

        ...;

        break;

}
```

`case` 标签可以跟

- 匹配 `switch` 表达式的值
- `default` 句（如果存在）

执行从匹配的 `case` 标签开始，直到遇到 `break` 或 `switch` 的结束。如果没有任何 `case` 标签匹配，则执行 `default` 句。




```
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
           计算中奖概率
        */
        int lotteryOdds = 1;

        for (int i = 1; i <= k; i++)
            lotteryOdds = lotteryOdds * (n - i + 1) / i;

        System.out.println("Your odds are 1 in " + lotteryOdds + ". Good luck!");
    }
}
```



`for`语句的第一个槽位通常存放计数器的初始化。第二个槽位是在每次循环新循环之前测试的条件，第三个槽位指定了如何更新计数器。

尽管 Java 像 C++ 一样，允许在`for`循环的各个槽位中使用几乎任何表达式，但良好的编程习惯有一条不成文的规定：这三个槽位应该只初始化、测试和更新同一个计数器变量。忽视这一规则可能会写出非常晦涩的循环。

![Images](img/03fig12.jpg)

**图 3.12** `for`语句的流程图

即使在良好习惯的范围内，仍有许多可能。例如，你可以编写递减计数循环：

```
for (int i = 10; i > 0; i--)

    System.out.println("Counting down . . . " + i);

System.out.println("Blastoff!");
```

* * *

![Image](img/caution.jpg) **注意：**

在循环中测试浮点数的相等性时要小心。像下面这样的`for`循环

```
for (double x = 0; x != 10; x += 0.1) . . .
```

可能永远不会结束。由于舍入误差，最终值可能无法精确到达。在这个例中，`x`会从`9.99999999999998`跳到`10.09999999999998`，因为 0.1 没有精确的二进制表示。

* * *

当你在`for`语句的第一个槽位声明变量时，该变量的作用域一直持续到`for`循环体的结束。

```
for (int i = 1; i <= 10; i++)

{

    . . .

}

// i 在此处不再定义
```

特别是，如果你在`for`语句内部定义变量，则不能在循环外部使用它的值。因此，如果你想在`for`循环外部使用循环计数器的最终值，请确保在循环头之外声明它。

```
int i;

for (i = 1; i <= 10; i++)

{

    . . .

}

// i 在此处仍然定义
```

另一方面，你可以在不同的`for`循环中定义同名的变量：

```
for (int i = 1; i <= 10; i++)

{

    . . .

} . . .

for (int i = 11; i <= 20; i++) // 定义另一个名为 i 的变量是允许的

{

    . . .

}
```

`for`循环只是`while`循环的一种便利快捷方式。例如，

```
for (int i = 10; i > 0; i--)

    System.out.println("Counting down . . . " + i);

int i = 10;

while (i > 0)

{

    System.out.println("Counting down . . . " + i);

    i--;
}
```

列表 3.5 显示了一个典型的`for`循环示例。

程序计算中奖票的概率。例如，如果你必须从 1 到 50 的数字中选出 6 个数字来中奖，那么有 (50 × 49 × 48 × 47 × 46 × 45)/(1 × 2 × 3 × 4 × 5 × 6) 种可能的结果，因此你的机会是 15,890,700 分之一。祝你好运！

通常情况下，如果你从`n`个数字中选出`k`个，会有

![Images](img/097equ01.jpg)

种可能的结果。下面的`for`循环计算该值：

```
int lotteryOdds = 1;

for (int i = 1; i <= k; i++)

    lotteryOdds = lotteryOdds * (n - i + 1) / i;
```

* * *

![Image](img/note.jpg) **注：**

第 3.10.3 节，"'for each'循环"位于第 112 页描述了"广义`for`循环"（也称为"for each"循环），它使得访问数组或集合中的所有元素变得方便。

* * *

**列表 3.5** `LotteryOdds/LotteryOdds.java`

```
 1  import java.util.*;
 2
 3  /**
 4    * 此程序演示了一个 <code>for</code> 循环。
 5    * @version 1.20 2004-02-10
 6    * @author Cay Horstmann
 7    */
 8  public class LotteryOdds
9  {
10     public static void main(String[] args)
11     {
12         Scanner in = new Scanner(System.in);
13         System.out.print("How many numbers do you need to draw? ");
14         int k = in.nextInt();
15
16         System.out.print("What is the highest number you can draw? ");
17         int n = in.nextInt();
18
19         /*
20           计算中奖概率
21         */
22         int lotteryOdds = 1;
23
         for (int i = 1; i <= k; i++)
24             lotteryOdds = lotteryOdds * (n - i + 1) / i;
25
26         System.out.println("Your odds are 1 in " + lotteryOdds + ". Good luck!");
27     }
28 }
```

#### 3.8.5 使用`switch`进行多选择

`if/else`结构在处理多个分支时可能非常繁琐。`switch`语句使得情况变得更容易，特别是当有多个分支时。像图 3.13 所示，`switch`在 Java 14 中引入了如下形式：

```
String input = ...;
switch (input.toLowerCase())
{
    case "yes" ->
        ...
    case "no" ->
        ...
    default ->
        ...
}
```

`switch`语句可以跟

- `char`、`byte`、`short`或`int`类型的常量表达式

- 枚举类型

- 字符串字面量

- 多个用逗号分隔的这些

例如，

```
int choice = ...;
switch (choice)
{
    case 1:
        ...;
        break;
    case 2:
        ...;
        break;
    case 3:
        ...;
        break;
    case 4:
        ...;
        break;
    default:
        ...;
        break;
}
```

`switch`的"经典"形式追溯到 Java 1.0。它的形式如下：

```
int choice = ...;
switch (choice)
{
    case 1:
        ...;
        break;
    case 2:
        ...;
        break;
    case 3:
        ...;
        break;
    case 4:
        ...;
        break;
    default:
        ...;
        break;
}
```

`case`标签可以跟

- 匹配`switch`表达式的值

- `default`句（如果存在）

执行从匹配的`case`标签开始，直到遇到`break`或`switch`的结束。如果没有任何`case`标签匹配，则执行`default`句。

每个`switch`表达式的分支必须产生一个值。最常见的情况是每个值后面跟着一个`->`箭头：

```
case "Summer", "Winter" -> 6;
```

如果无法做到，请使用`yield`语句。

#### 表 3.7 `switch`的四种形式

![Images](img/03tab07.jpg)

* *

![Image](img/note.jpg) **注意：**

在`switch`表达式的分支中抛出异常是合法的。例如：

```
default -> throw new IllegalArgumentException("Not a valid season");
```

异常将在第 7 章中详细介绍。

* *

* *

![Image](img/caution.jpg) **警告：**

`switch`表达式的目的是产生一个值（或因异常失败）。你不允许"跳出"：

```
default -> { return -1; } // 错误
```

具体来说，你不能在`switch`表达式中使用`return`、`break`或`continue`语句。（关于后两者，请参阅第 103 页的第 3.8.6 节"中断控制流的语句"。）

* *

有这么多`switch`的变体，你应该选择哪一个？

优先使用`switch`表达式而不是语句。如果每个分支都是为变量赋值或方法调用计算值，请用表达式产生值，然后使用它。例如：

```
numLetters = switch (seasonName)
   {
      case "Spring", "Summer", "Winter" -> 6
      case "Fall" -> 4
      default -> -1
   };
```

优于

```
switch (seasonName)
{
   case "Spring", "Summer", "Winter" ->
      numLetters = 6;
   case "Fall" ->
      numLetters = 4;
   default ->
      numLetters = -1;
}
```

只有当你确实需要贯穿（fallthrough）或者你必须在`switch`表达式中添加语句时，才使用`break`或`yield`。这些情况极其罕见。

#### 3.8.6 中断控制流的语句

尽管 Java 的设计者保留了`goto`这一保留字，但他们决定不包含在语言中。通常情况下，`goto`语句被认为是一种糟糕的风格。有些程序员觉得反`goto`的力量过头了（例如，参考 Donald Knuth 的著名文章《带有 goto 语句的结构化编程》）。他们认为，虽然无限制地使用`goto`容易出错，但偶尔跳出循环是有益的。Java 的设计者同意了这一点，甚至添加了一种新的语句——带标签的 break（labeled break），来支持这种编程风格。

让我们先看看不带标签的`break`语句。你用于退出`switch`语句的同一个`break`语句也可以跳出循环。例如：

```
while (years <= 100)
{
   balance += payment;
   double interest = balance * interestRate / 100;
   balance += interest;
   if (balance >= goal) break;
   years++;
}
```

现在，如果在循环顶部出现`years > 100`，或者在循环中间出现`balance >= goal`，循环就会退出。当然，你可以在不使用`break`的情况下计算`years`的相同值，如下：

```
while (years <= 100 && balance < goal)
{
   balance += payment;
   double interest = balance * interestRate / 100;
   balance += interest;
   if (balance < goal)
      years++;
}
```

但注意，在这个版本中`balance < goal`测试重复了两次。为了避免这种重复测试，一些程序员更倾向于使用`break`语句。

与 C++ 不同，Java 还提供了带标签的 break 语句（labeled break），允许你跳出多个嵌套循环。深层嵌套循环内部偶尔会发生奇怪的事情。在这种情况下，你可能想要完全跳出所有嵌套循环。通过给各种循环测试添加额外的条件来实现这一操作是不方便的。

这是一个展示`break`语句作用的示例。注意，标签必须在你想要跳出的最外层循环之前。标签后面必须跟冒号。

```
Scanner in = new Scanner(System.in);
int n;
read_data:
while (. . .) // 此循环语句带有该标签
{
   . . .
   for (. . .) // 此内部循环没有标签
   {
      System.out.print("Enter a number >= 0: ");
      n = in.nextInt();
      if (n < 0) // 不应该发生——无法继续
          break read_data;
          // 跳出 read_data 循环
      . . .
   }
}
// 此语句在带标签的 break 后立即执行
if (n < 0) // 检查异常情况
{
   // 处理异常情况
}
else
{
   // 执行正常处理
}
```

如果有错误的输入，带标签的 break 会跳过带标签块的结束。与任何使用`break`语句一样，你随后需要测试循环是正常退出还是由于 break 导致出的。

* *

![Image](img/note.jpg) **注意：**

有趣的是，你可以将带标签的 break 应用到任何`if`语句，如下所示：

```
label:
{
   . . .
```

最后，还有一种带标签的`continue`形式，可以跳转到头部。这是一个示例：

```
for (count = 1; count <= 100; count++)
{
   System.out.print("Enter a number, -1 to quit: ");
   n = in.nextInt();
   if (n < 0) continue label;
   sum += n;
}
```

* *

![Image](img/tip.jpg) **提示：**

许多程序员发现`break`和`continue`令人困惑。这些语句是完全可选的——你始终可以在不需要它们的情况下表达逻辑。

### 3.9 大数字

如果基本整数和浮点类型的精度不足，你可以转向`java.math`包中的两个类：`BigInteger`和`BigDecimal`。这些是用于处理任意长度数字序列的类。

使用静态方法`valueOf`将普通数字转换为大数字：

```
BigInteger a = BigInteger.valueOf(100);
```

对于更长的数字，使用带字符串参数的构造函数：

```
BigInteger reallyBig = new BigInteger("22223224462942044552973989346190996720666693909649976499097600");
```

还有常量`BigInteger.ZERO`、`BigInteger.ONE`、`BigInteger.TEN`以及自 Java 9 起的`BigInteger.TWO`。

* *

![Image](img/caution.jpg) **警告：**

对于`BigDecimal`类，你应该始终使用带字符串参数的构造函数。有一个`BigDecimal(double)`构造函数，会导致舍入误差：`new BigDecimal(0.1)`的数字为`0.1000000000000000055511151231257827021181583404541015625`。

* *

遗憾的是，你不能使用熟悉的数学运算符（如`+`和`*`）组合大数字。相反，你必须使用大数字类中的`add`和`multiply`等方法。

```
BigInteger c = a.add(b); // c = a + b

BigInteger d = c.multiply(b.add(BigInteger.valueOf(2))); // d = c * (b + 2)
```

![Image](img/c.jpg) **C++ 笔记：**

与 C++ 不同，Java 没有可编程的运算符重载。`BigInteger`类的程序员无法重新定义`+`和`*`运算符来为`BigInteger`类提供`add`和`multiply`操作。该语言的语言设计者确实重载了`+`运算符，用于表示字符串的拼接。他们选择不重载其他运算符，也没有为 Java 程序员提供在自己的类中重载运算符的机会。

列表 3.6 显示了对列表 3.5 彩票概率程序的修改，已更新为支持大数。例如，如果你被邀请参加一种彩票，需要从 490 个可能的数字中选出 60 个，你可以使用这个程序来告知你的中奖概率。概率是 1 比`716395843461995557415116222540092933411717612789263493493351013459481104668848`。祝你好运！



列表 3.5 中的程序计算了以下陈述语句：

```
lotteryOdds = lotteryOdds * (n - i + 1) / i;
```

当大整数用于`lotteryOdds`和`n`时，等效语句变为：

```
lotteryOdds = lotteryOdds
    .multiply(n.subtract(BigInteger.valueOf(i - 1)))
    .divide(BigInteger.valueOf(i));
```

**列表 3.6** `BigIntegerTest/BigIntegerTest.java`

```java
 1  import java.math.*;
 2  import java.util.*;
 3
 4  /**
 5    * 此程序使用大数来计算彩票中头奖的概率。
 6    * @version 1.20 2004-02-10
 7    * @author Cay Horstmann
 8    */
 9  public class BigIntegerTest
10  {
11      public static void main(String[] args)
12      {
13          Scanner in = new Scanner(System.in);
14
15          System.out.print("你需要抽取多少个数字? ");
16          int k = in.nextInt();
17
18          System.out.print("你能抽到的最大数字是多少? ");
19          BigInteger n = in.nextBigInteger();
20
21          /*
22           * 计算二项式系数 n*(n-1)*(n-2)*...*(n-k+1)/(1*2*3*...*k)
23          */
24
25          BigInteger lotteryOdds = BigInteger.ONE;
26
27          for (int i = 1; i <= k; i++)
28              lotteryOdds = lotteryOdds
29                  .multiply(n.subtract(BigInteger.valueOf(i - 1)))
30                  .divide(BigInteger.valueOf(i));
31
32          System.out.printf("你的中奖概率是 1 分之一 %s。祝你好运!%n", lotteryOdds);
33      }
34  }
```

**`java.math.BigInteger`** **1.1**

- `add(BigInteger other)`
- `subtract(BigInteger other)`
- `multiply(BigInteger other)`
- `divide(BigInteger other)`
- `mod(BigInteger other)` 返回此整数与`other`的和、差、商和余数。
- `sqrt()` 得`BigInteger`的平方根。
- `compareTo(BigInteger other)` 如果此整数等于`other`则返回`0`，如果此整数小于`other`则返回负结果，否则返回正结果。
- `static BigInteger valueOf(long x)` 返回一个值等于`x`的大整数。

**`java.math.BigDecimal`** **1.1**

- `BigDecimal(String digits)` 使用指定的数字构造一个大小数。
- `add(BigDecimal other)`
- `subtract(BigDecimal other)`
- `multiply(BigDecimal other)`
- `divide(BigDecimal other)` 返回此小数与`other`的和、差或商。如果第一个`divide`方法的商没有有限展开，则抛出异常。要获得舍入后的结果，请使用第二个方法。`RoundingMode.HALF_UP` 模式你在学校学的舍入模式：0 到 4 舍舍入，5 到 9 向上舍入。
- `compareTo(BigDecimal other)` 如果此小数等于`other`则返回`0`，如果此小数小于`other`则返回负结果，否则返回正结果。

### 3.10 数组

数组存储相同类型的值序列。在接下来的章节中，你将看到如何操作数组。

#### 3.10.1 声明数组

数组是存储相同类型值集合的数据结构。在接下来的章节中，你将看到如何操作数组。数组是一个存储相同类型值集合的数据结构。在接下来的章节中，你将看到如何操作数组。数组是一个存储相同类型值集合的数据结构。在接下来的章节中，你将看到如何操作数组。

```
```

计算二项式系数`n*(n-1)*(n-2)*...*(n-k+1)/(1*2*3*...*k)`。

创建一个包含十个字符串的数组，全部为`null`。如果你希望数组持有空字符串，则必须提供它们：

```
for (int i = 0; i < 10; i++) names[i] = "";
```

***

![Image](img/caution.jpg) **注意：**

如果你构建了一个包含 100 个元素的数组，然后尝试访问元素`a[100]`（或 0 到 99 范围外的任何其他索引），将发生“数组越界”（array index out of bounds）异常。

***

要找到数组的元素个数，使用`array.length`。例如：

```
for (int i = 0; i < a.length; i++)
    System.out.println(a[i]);
```

#### 3.10.3 “for each” 循环

Java 拥一种强大的循环结构，允许你遍历数组（或任何其他元素集合）中的每个元素，而无需处理索引值。

#### 增强型`for`循环

```
for (variable : collection) statement
```

将给定的变量设置为集合中的每个元素，然后执行该语句（该语句当然可以是一个块）。`collection`表达式必须是一个数组或实现了`Iterable`接口的类的对象，例如`ArrayList`。数组列表在第 5 章中介绍，`Iterable`接口在第 9 章中介绍。

例如，

```
for (int element : a)
    System.out.println(element);
```

将分行打印数组`a`的每个元素。

你应当将此循环读作“对于`a`中的每个`element`”。Java 语言的设计者曾考虑过使用如`foreach`和`in`等关键字。但这种循环是 Java 语言晚期添加的，最终没有人想要破坏那些已经包含这些名称的方法或变量的旧代码（例如`System.in`）。

当然，你可以使用传统的`for`循环实现相同效果：

```
for (int i = 0; i < a.length; i++)
    System.out.println(a[i]);
```

然而，“for each”循环更加简洁且更不容易出错，因为你不必再担心那些讨厌的起始和结束索引值。

***

![Image](img/note.jpg) **注意：**

“for each”循环的循环变量遍历的是数组元素，而不是索引值。

***

如果你需要处理集合中的所有元素，“for each”循环相比传统循环是一个令人愉的改进。然而，仍然有许多机会可以使用传统的`for`循环。例如，你可能不想遍历整个集合，或者你可能在循环内部需要索引值。

***

![Image](img/tip.jpg) **提示：**

有一种更简单的方法可以打印数组的所有值，即使用`Arrays`类的`toString`方法。调用`Arrays.toString(a)`返回一个包含数组元素的字符串，这些元素包含在括号内并用逗号分隔，例如`"[2, 3, 5, 7, 11, 13]"`。要打印数组，只需调用：

```
System.out.println(Arrays.toString(a));
```

***

### 3.10.4 数组复制

你可以将一个数组变量复制到另一个变量中，但此时两个变量都指向同一个数组：

```
int[] luckyNumbers = smallPrimes;
luckyNumbers[5] = 12; // 现在 smallPrimes[5] 也是 12
```

图 3.14 显示了结果。如果你实际上将一个数组的所有值复制到一个新数组，请使用`Arrays`类中的`copyOf`方法：

```
int[] copiedLuckyNumbers = Arrays.copyOf(luckyNumbers, luckyNumbers.length);
```

![Images](img/03fig14.jpg)

**图 3.14** 复制数组变量

第二个参数是新数组的长度。该方法的一个常见用途增加数组的长度：

```
luckyNumbers = Arrays.copyOf(luckyNumbers, 2 * luckyNumbers.length);
```

如果数组包含数字，额外的元素将填充为`0`；如果数组包含`boolean`值，则填充为`false`。相反，如果长度小于原数组的长度，则只复制初始值。

***

![Image](img/c.jpg) **C++ 注意：**

Java 数组与栈上的 C++ 数组非常不同。然而，它本质上与堆上分配的数组指针相同。也就是说，

```
int[] a = new int[100]; // Java
```

并不等于

```
int a[100]; // C++
```

而是

```
int* a = new int[100]; // C++
```

在 Java 中，`[]`运算符被预定义用于执行边界检查。此外，没有指针算术——你无法通过增加`a`来指向数组中的下一个元素。

***

### 3.10.5 命令行参数

你已经见过一个数组重复几次的示例。每个`main`方法都有一个`String[] args`参数。该参数接收在命令行中指定的字符串数组。例如，考虑这个程序：

```java
public class Message {
    public static void main(String[] args) {
        if (args.length == 0 || args[0].equals("-h")) {
            System.out.println("Hello,");
        } else if (args[0].equals("-g")) {
            System.out.print("Goodbye, ");
            for (int i = 0; i < args.length; i++) {
                System.out.print(args[i] + " ");
            }
            System.out.println("!");
        }
    }
}
```

如果你调用`java Message -h`，`args`数组具有如下：

```
args[0]: -h
```

如果你调用`java Message -g 1 2 3`，`args`数组具有如下：

```
args[0]: -g
args[1]: 1
args[2]: 2
args[3]: 3
```

***

### 3.10.6 数组排序

要对数组进行排序，使用`Arrays`类包含的`sort`方法之一。该方法使用一种经过调优的算法，据称在数据集上非常高效。例如，如果你玩“从 49 中选 6 个数字”的彩票，程序可能会打印：

```
4
7
19
30
44
```

为了选择这样的随机数字，首先用`1`, `2`, ..., `n`填充数组`numbers`：

```java
int[] numbers = new int[n];
for (int i = 0; i < numbers.length; i++)
    numbers[i] = i + 1;
```

第二个数组持有要抽取的数字：

```java
int[] result = new int[k];
```

现在抽取`k`个数字。`Math.random`方法返回一个`0`（包含）到`1`（不包含）之间的随机浮点数。将结果乘以`n`产生一个`0`到`n-1`之间的随机整数。

```java
int r = (int) (Math.random() * n);
```

将第`i`个结果设置为该索引处的数字。最初只是`r` + 1，但正如我们随后看到的，`numbers`数组的内容在每次抽取后都会改变。

```java
result[i] = numbers[r];
```

现在，必须确保不再抽取那个数字——所有彩票数字必须是唯一的。因此，用数组中的最后一个元素覆盖`numbers[r]`，并将`n`减 1。

```java
numbers[r] = numbers[n - 1];
n--;
```

要点是，每次抽取我们选择的是索引，而不是实际值。该索引指向包含尚未抽取的数值的数组。

在抽取`k`个彩票数字后，排序`result`数组以获得更理想的输出：

```java
Arrays.sort(result);
for (int r : result)
    System.out.println(r);
```

**列表 3.7** `LotteryDrawing/LotteryDrawing.java`

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
        System.out.print("你能抽取的最大数字是多少？ ");
        int n = in.nextInt();

        // 用数字 1 2 3 . . . n 填充数组
        int[] numbers = new int[n];
        for (int i = 0; i < numbers.length; i++)
            numbers[i] = i + 1;

        // 抽取 k 个数字并将它们放入第二个数组中
        int[] result = new int[k];
        for (int i = 0; i < result.length; i++)
        {
            // 在 0 到 n - 1 之间生成一个随机索引
            int r = (int) (Math.random() * n);
            // 选取随机位置的元素
            result[i] = numbers[r];
            // 将最后一个元素移动到随机位置
            numbers[r] = numbers[n - 1];
            n--;
        }

        // 打印排序后的数组
        Arrays.sort(result);
        System.out.println("下注以下组合。它会让你富的！");
        for (int r : result)
            System.out.println(r);
    }
}
```



### `java.util.Arrays` 1.2

- `static String toString(xxx[] a)` **5**  
  返回一个包含`a`中元素的字符串，元素用括号括起并用逗号分隔。在本方法及后续方法中，数组的组件类型`xxx`可以是`int`、`long`、`short`、`char`、`byte`、`boolean`、`float`或`double`。
- `static xxx[] copyOf(xxx[] a, int end)` **6**  
- `static xxx[] copyOfRange(xxx[] a, int start, int end)` **6**  
  返回一个与`a`类型相同、长度为`end`或`end – start`的数组，并用`a`的值填充。如果`end`大于`a.length`，结果将用`0`或`false`值填充。
- `static void sort(xxx[] a)`  
  使用经过优化的快速排序（QuickSort）算法对数组进行排序。
- `static int binarySearch(xxx[] a, xxx v)`  
- `static int binarySearch(xxx[] a, int start, int end, xxx v)` **6**  
  使用二分查找算法在排序后的数组`a`中查找值`v`。如果找到`v`，返回其索引。否则，返回一个负值`r`；`r – 1`是`v`应该插入的位置。
- `static void fill(xxx[] a, xxx v)`  
  将数组的所有元素都设置为`v`。
- `static boolean equals(xxx[] a, xxx[] b)`  
  如果数组长度相同且对应位置的元素匹配，则返回`true`。

#### 3.10.7 多维数组

多维数组使用多个索引来访问元素。它们被用于表格和其他布局。在你有存储需求之前，可以安全地跳过这一节。

假设你想创建一个数字表格，显示 10,000 美元的投资在按年付息并再投资的利率场景下将如何增长（参见表 3.8）。

**表 3.8 不同利率下投资的增长情况**

![Images/03tab08.jpg]

你可以将这些信息存储在一个名为`balances`的二维数组（矩阵）中。在 Java 中声明一个二维数组非常简单。例如：

```java
double[][] balances;
```

在初始化它之前，你无法使用该数组。在这种情况下，你可以按照以下方式进行初始化：

```java
balances = new double[YEARS][RATES];
```

在其他情况下，如果你知道数组的元素，可以使用简写符号来初始化多维数组，而无需调用`new`。例如：

```java
int[][] magicSquare = {
    {16, 3, 2, 13},
    {5, 10, 11, 8},
    {9, 6, 7, 12},
    {4, 15, 14, 1}
};
```

一旦数组初始化完成，你就可以提供两对括号来访问单个元素——例如，`balances[i][j]`。

示例程序存储了一个存储利率的一维数组`interest`和一个存储账户余额的二维数组`balances`，每个年份和每个利率对应一个。用初始余额初始化数组的第一行：

```java
for (int j = 0; j < balances[0].length; j++)
    balances[0][j] = 10000;
```

然后按照下面的方式计算其他行：

```java
for (int i = 1; i < balances.length; i++) {
    for (int j = 0; j < balances[i].length; j++) {
        double oldBalance = ...;
        double interest = ...;
        balances[i][j] = oldBalance + interest;
    }
}
```

![Images/note.jpg] **注意:**  
“for each”循环并没有遍历二维数组中的所有元素。相反，它遍历行，而行本身是一维数组。要访问二维数组的所有元素，需要嵌套循环，如下：

```java
for (double[] row : balances)
    for (double value : row)
        do something with value
```

![Images/tip.jpg] **提示:**  
要打印二维数组的快速列表，调用：

```java
System.out.println(Arrays.deepToString(a));
```

输出如下：

```
[[16, 3, 2, 13], [5, 10, 11, 8], [9, 6, 7, 12], [4, 15, 14, 1]]
```

**列表 3.8** `CompoundInterest/CompoundInterest.java`

```java
import java.util.*;

/**
 * 此程序展示了如何在二维数组中存储数据。
 * @version 1.40 2004-02-10
 * @author Cay Horstmann
 */
public class CompoundInterest
{
    public static void main(String[] args)
    {
        double STARTRATE = 10;
        int RATES = 6;
        int NYEARS = 10;

        // 设置利率为 10%-15%
        double[] interestRate = new double[RATES];
        for (int j = 0; j < interestRate.length; j++)
            interestRate[j] = (STARTRATE + j) / 100.0;

        double[][] balances = new double[NYEARS][RATES];

        // 设置初始余额为 10000
        for (int j = 0; j < balances[0].length; j++)
            balances[0][j] = 10000;

        // 计算未来的利息
        for (int i = 1; i < balances.length; i++) {
            for (int j = 0; j < balances[i].length; j++) {
                double oldBalance = balances[i - 1][j];
                double interest = oldBalance * interestRate[j];
                balances[i][j] = oldBalance + interest;
            }
        }

        // 打印一行利率
        for (int j = 0; j < interestRate.length; j++)
            System.out.printf("%9.0f%%", 100 * interestRate[j]);
        System.out.println();

        // 打印余额表
        for (double[] row : balances) {
            // 打印表格行
            for (double b : row)
                System.out.printf("%10.2f", b);
            System.out.println();
        }
    }
}
```

#### 3.10.8 锯齿数组

到目前为止，你所看到的与其它编程语言没有太大区别。但在背后实际上有一些微妙的机制，你有时可以利用这一点：Java 根本**没有**多维数组，只有一维数组。多维数组被伪装成“数组的数组”。

例如，上述示例中的`balances`数组实际上是一个包含十个元素的数组，其中每个元素都是一个包含六个浮点数的数组（参见图 3.15）。

表达式`balances[i]`指第`i`个子数组——即表格的第`i`行。它本身是一个数组，而`balances[i][j]`指该数组的第`j`个元素。

由于数组的行是可以单独访问的，你实际上可以交换它们！

![Images](img/03fig15.jpg)

**图 3.15** 二维数组

```java
double[] temp = balances[i];
balances[i] = balances[i + 1];
balances[i + 1] = temp;
```

创建“锯齿”数组（ragged arrays）也很容易——即不同行长度不同的数组。这里有一个标准示例。让我们创建一个数组，其中第`i`行第`j`列的元素等于“从`i`个数中选择`j`个数”彩票的所有可能的结果。

```
1
1  1
1  2  1
1  3  3  1
1  4  6  4  1
1  5 10 10  5 1
1  6 15 20 15 6 1
```

由于`j`永远不会大于`i`，该矩阵是三角形的。第`i`行有`i` + 1 个元素。（选择 0 个元素是允许的；有一种方法可以进行这种选择）。要构建这个锯齿数组，首先分配存储行的数组：

```java
final int NMAX = 10;
int[][] odds = new int[NMAX + 1][];
```

接下来，分配行：

```java
for (int n = 0; n <= NMAX; n++)
   odds[n] = new int[n + 1];
```

现在数组已经分配完毕，你就可以像平常一样访问元素了，只要不越界：

```java
for (int n = 0; n < odds.length; n++)
  for (int k = 0; k < odds[n].length; k++)
   {
      // compute lotteryOdds
      . . .
      odds[n][k] = lotteryOdds;
    }
```

Listing 3.9 提供了完整的程序。

***

![Image](img/c.jpg) **C++ 注意：**

在 C++ 中，Java 的声明

```java
double[][] balances = new double[10][6]; // Java
```

不等同于

```cpp
double balances[10][6]; // C++
```

甚至于

```cpp
double (*balances)[6] = new double[10][6]; // C++
```

相反，它分配了一个包含十个指针的数组：

```cpp
double** balances = new double*[10]; // C++
```

然后，指针数组中的每个元素都被填充为一个包含六个数字的数组：

```cpp
for (i = 0; i < 10; i++)
   balances[i] = new double[6];
```

幸运的是，当你请求`new double[10][6]`时，这个循环是自动的。当你需要锯齿数组时，你需要单独分配行数组。

***

**Listing 3.9** `LotteryArray/LotteryArray.java`

```java
 1  /**
 2    * 此程序演示了一个三角形数组。
 3    * @version 1.20 2004-02-10
 4    * @author Cay Horstmann
 5    */
 6  public class LotteryArray
 7  {
 8      public static void main(String[] args)
 9      {
10          final int NMAX = 10;
11
12          // 分配三角形数组
13          int[][] odds = new int[NMAX + 1][];
14          for (int n = 0; n <= NMAX; n++)
15              odds[n] = new int[n + 1];
16
17          // 填充三角形数组
18          for (int n = 0; n < odds.length; n++)
19            for (int k = 0; k < odds[n].length; k++)
20            {
21              /*
22               * 计算系数 n*(n-1)*(n-2)*...*(n-k+1)/(1*2*3**k)
23               */
24              int lotteryOdds = 1;
25              for (int i = 1; i <= k; i++)
26                lotteryOdds = lotteryOdds * (n - i + 1) / i;
27
28              odds[n][k] = lotteryOdds;
29            }
30
31          // 打印三角形数组
32          for (int[] row : odds)
33            {
              for (int odd : row)
34                System.out.printf("%d", odd);
35                System.out.println();
36            }
37      }
```



38  }```

你现在已经看到了 Java 语言的基础结构。下一章介绍面向对象编程。

# 第 4 章 对象与类

## 本章内容

- 4.1 面向对象编程简介
- 4.2 使用预定义类
- 4.3 定义你自己的类
- 4.4 静态字段和方法
- 4.5 方法参数
- 4.6 对象构造
- 4.7 记录
- 4.8 程序包
- 4.9 JAR 文件
- 4.10 文档注释
- 4.11 类设计提示

在本章中，我将：

- 向你介绍面向对象编程；
- 向你展示如何创建标准 Java 中的类；以及
- 展示如何编写自己的类。

如果你没有面向对象编程的背景，你将仔细阅读这一章。面向对象编程需要与过程化语言不同的思维方式。转换并不总是容易的，你需要熟悉一些对象概念才能继续学习 Java。

对于丰富的 C++ 程序员来说，本章和上一章一样，介绍了熟悉的信息；然而，两种语言之间存在足够的差异，你应该仔细阅读本章的后续部分。你会发现 C++ 的笔记会有帮助。

## 4.1 面向对象编程简介

面向对象编程（简称 OOP）是如今的主流编程范式，它取代了 20 世纪 70 年代开发的结构化或过程化编程技术。由于 Java 是面向对象的，你必须熟悉 OOP 才能高效使用 Java。

面向对象的程序由对象组成。每个对象都有特定的功能暴露给用户，并隐藏了实现细节。你程序中的许多对象是从库中“现买”的；另一些是自定义设计的。构建对象还是购买对象取决于你的预算或时间。但基本上，只要对象符合你的规范，你就不在乎功能是如何实现的。

传统的结构化编程包括设计一组过程（或`算法`）来解决问题。一旦确定了过程，传统的下一步是找到存储数据的合适方法。这就是为什么 Pascal 语言的设计者 Niklaus Wirth 将他的名著命名为《Algorithms + Data Structures = Programs》（Prentice Hall, 1976）。注意在 Wirth 的标题中，算法在前，数据在后。这反映了那个时代程序员的工作方式。OOP 反转了这个顺序：先放数据，然后看操作数据的算法。

对于小问题，拆分为过程的方法效果非常好。但对于较大的问题，对象更为合适。考虑一个简单的网页浏览器。它的实现可能需要 2000 个过程，所有过程都操作一组全局数据。在面向对象的风格中，可能有 100 个类，每个类平均 20 个方法（参见图 4.1）。这种结构对程序员更容易理解，也更容易发现 bug。假设某个特定对象的数据处于错误状态。在访问该数据项的 20 个方法中寻找罪祸首比在 2000 个过程中要容易得多。

![Images](img/04fig01.jpg)

**图 4.1** 过程化对比 OO 编程

### 4.1.1 类

`类`规定了如何制造对象。将类类比为饼干模；对象是饼干本身。当你从一个类`构造`一个对象时，被认为创建了该类的`实例`。

如你所见，你在 Java 中编写的所有代码都在类内部。标准 Java 库提供了数千个类，用于用户界面设计、日期和日历以及网络编程等各种用途。尽管如此，在 Java 中你仍然需要创建自己的类来描述应用程序问题领域的对象。

`Encapsulation`（封装，有时称为信息隐藏）是处理对象时的一个核心概念。从形式上说，封装仅仅是将数据和行为组合在一个包中，并对对象的用户隐藏实现细节。对象中的数据单元称为其`instance fields`（实例字段），对数据进行操作的过程称为其`methods`（方法）。作为类实例的特定对象具有其实例字段的具体值。这些值的集合就是该对象的当前`state`（状态）。每当你对对象调用方法时，它的状态都可能发生变化。

使封装生效的关键是让方法`never`（从不）直接访问其他类的实例字段。程序应该`only`（仅）通过对象的方法与对象数据交互。封装是赋予对象“黑盒”行为的方式，这是实现重用和可靠性的关键。这意味着一个类可以完全改变其存储数据的方式，但只要它继续使用相同的方法来操作数据，其他对象就不会知道或在乎。

当你开始在 Java 中编写自己的类时，OOP 的另一个原则会让这一切变得更简单：类可以通过`extending`（扩展）其他类来构建。事实上，Java 自带了一个名为`Object`的“宇宙超级类”。所有其他类都扩展了这个类。你将在下一章学习更多关于`Object`的知识。

当你扩展一个现有类时，新类拥有你所扩展的类的所有属性和方法。然后你提供了仅适用于你新类的方法和实例字段。通过扩展类来获取另一个类的概念被称为`inheritance`（继承）。关于继承的更多信息，请参见下一章。

### 4.1.2 对象

为了使用 OOP，你应该能够识别对象的三个关键特征：

- 对象的`behavior`（行为）——你可以用这个对象做什么，或者可以对它应用哪些方法？
- 对象的`state`（状态）——当你调用这些方法时，对象是如何反应的？
- 对象的`identity`（身份）——如何与其他可能具有相同行为和状态的对象区分开来？

同一类的实例的所有对象都通过支持相同的`behavior`具有家族相似性。对象的行为是由你可以调用的方法定义的。

接下来，每个对象都存储关于其当前状态的信息。这就是对象的`state`。对象的状态可能会随时间改变，但不会自发改变。对象状态的变化必须是方法调用的结果。（如果对象的状态在没有对该对象调用方法的情况下发生了改变，那么有人破坏了封装。）

然而，对象的状态并不能完全描述它，因为每个对象都有独特的`identity`。例如，在订单处理系统中，两个订单即使请求相同的物品，它们也是不同的。请注意，作为类实例的单个对象在身份上`always`（总是）不同，在状态上`usually`（通常）也不同。

这些关键特征可以相互影响。例如，对象的状态可以影响它的行为。（如果一个订单是“已发货”或“已支付”，它可能会拒绝要求添加或删除物品的方法调用。相反，如果订单是“空的”——即尚未订单任何物品——它不应该允许自己被发货。）

### 4.1.3 识别类

在传统的过程化程序中，你从顶部的`main`函数开始处理过程。在设计面向对象的系统时，没有“顶部”，OOP 的初学者往往不知道从哪里开始。答案是：识别你的类，然后为每个类添加方法。

识别类的一个简单经验法是在问题分析中寻找名词。另一方面，方法对应于动词。

例如，在订单处理系统中，一些名词是：

- Item（物品）
- Order（订单）
- Shipping address（配送地址）
- Payment（付款）
- Account（账户）

这些名词可能会引出`Item`、`Order`等类。

接下来，寻找动词。物品被`added`（添加）到订单中。订单被`shipped`（发货）或`canceled`（取消）。付款被`applied`（应用）到订单中。对于每个动词，如“add”、“ship”、“cancel”或“apply”，你都要识别执行该操作负主要责任的对象。例如，当一个新物品被添加到订单时，订单对象应该是负责的那个，因为它知道如何存储和排序物品。也就是说，`add`应该是`Order`类的一个方法，并接收一个`Item`对象作为参数。

当然，“名词和动词”只是一个经验法则；只有经验才能帮助你自己在构建类时决定哪些名词和动词是重要的。

### 4.1.4 类之间的关系

类与类之间常见的关系有：

- `Dependence`（依赖，“使用一个……”）
- `Aggregation`（聚合，“有一个……”）
- `Inheritance`（继承，“是一个……”）

`dependence`（依赖关系）或“uses–a”关系是最明显的也是最通用的。例如，`Order`类使用`Account`类，因为`Order`对象需要访问`Account`对象来检查信用状态。但`Item`类不依赖于`Account`类，因为`Item`对象永远不需要担心客户账户。因此，如果一个类的方法使用了或操作了另一个类的对象，那么该类就依赖于另一个类。

尝试尽量减少相互依赖的类数量。要点在于，如果类`A`不感知类`B`的存在，它也不会担心`B`的任何变化。（这意味着对`B`的更改不会给`A`引入错误。）在软件工程中，你希望减少类与类之间的`coupling`（耦合）。

`aggregation`（聚合）或“has–a”关系很容易理解，因为它是具体的；例如，一个`Order`对象包含`Item`对象。包含意味着类`A`的对象包含类`B`的对象。

**注意：** 有些方法论者对聚合概念表示不喜欢，并倾向于使用更通用的关联（association）关系。从建模的角度来看，这是可以理解的。但对于程序员来说，“has–a”关系非常有意义。我喜欢使用聚合还有另一个原因：关联的标准表示不够清晰。

`inheritance`（继承）或“is–a”关系表达了特殊类与更通用类之间的关系。例如，`RushOrder`类继承自`Order`类。特化的`RushOrder`类具有处理优先级的特殊方法和计算运费的方法，但它的其他方法（如添加物品和账单）继承自`Order`类。通常，如果类`D`扩展类`C`，类`D`继承类`C`的方法但具有更多功能。（参见下一章，该章将详细讨论这一重要概念。）

许多程序员使用 UML（统一建模语言）符号来绘制`类图`，以描述类之间的关系。你可以在图 4.2 中看到此类图的示例。你将类画为矩形，将关系画为带有各种装饰的箭头。表 4.1 显示了最常见的 UML 箭头样式。

在 Java 中，没有类你什么也做不了，而且你已经见过好几个类是如何运行的了。然而，并不是所有这些类都展示了面向对象的典型特征。例如，`Math`类。你已经看到过你可以使用`Math`类的方法，例如`Math.random`，而不需要知道它们是如何实现的——你只需要知道名称和参数（如果有的话）。这就是封装的意义，而且这对于所有类来说都是如此。但`Math`类**仅**封装了功能；它既不需要也不隐藏数据。由于没有数据，你就不需要担心创建对象和初始化它们的实例字段——因为根本没有这些字段！

在下一节中，我们将查看一个更具代表性的类，`Date`类。你将看到如何构造对象以及调用该类的方法。

## 4.2 使用预定义类

### 4.2.1 对象和对象变量

要操作对象，你首先要构造它们并指定它们的初始状态。然后，你对对象应用方法。

在 Java 编程语言中，你使用`constructors`（构造函数）来构造新实例。构造函数是一个特殊方法，其目的是构造和初始化对象。让我们来看一个例子。标准 Java 库包含一个`Date`类。它的对象描述了时间点，例如 1999 年 12 月 31 日 23:59:59 GMT。

---

![Image](img/note.jpg)

**注意：**

你可能在想：为什么要用类来表示日期，而不是（像某些语言那样）使用内置类型？例如，Visual Basic 有一个内置的日期类型，程序员可以以`#12/31/1999#`的格式指定日期。从表面上看，这听起来很方便——程序员可以使用内置日期类型，而无需担心类。但实际上，Visual Basic 的设计有多合适呢？在某些地区，日期的格式是月/日/年，而在另一些则是日/月/年。语言设计者真的能够预见到这些问题吗？如果他们做得不好，语言就会变成一个令人不悦的混乱，而程序员对此无能为力。通过类，设计任务被交给了库。如果由于某个类不完美，其他程序员可以轻松地编写自己的类来增强或替换它（为了证明这一点：Java 日期库刚开始有点混乱，已经重新设计了两次）。

---

构造函数的名称始终与类名相同。因此，`Date`类的构造函数名为`Date`。要构造一个`Date`对象，将构造函数与`new`运算符结合，如下：

```java
new Date()
```

这个表达式构造了一个新对象。该对象被初始化为当前日期。如果你愿意，可以将对象传递给一个方法：

```java
System.out.println(new Date());
```

或者，你可以对刚刚构造的对象应用一个方法。`Date`类的方法之一是`toString`。该方法产生日期的字符串表示。以下是你如何将`toString`方法应用于一个新构造的`Date`对象的：

```java
String s = new Date().toString();
```

在这两个示例中，构造的对象只被使用了一次。通常，你会希望保留这些对象以便继续使用它们。只需将对象存储在变量中：

```java
Date rightNow = new Date();
```

图 4.3 显示了引用新构造对象的对象变量`rightNow`。

![Images](img/04fig3.jpg)

**图 4.3** 创建新对象

对象和对象变量之间存在重要的区别。例如，语句：

```java
Date startTime; // startTime 没有引用任何对象
```

这定义了一个对象变量`startTime`，它可以引用`Date`类型的对象。重要的是，要意识到变量`startTime`*本身不是一个对象*，事实上，它甚至还没有引用任何对象。此时，你不能在该变量上使用任何`Date`方法。语句：

```java
startTime.toString(); // 尚还不行
```

将导致编译时错误。

你必须先初始化`startTime`变量。你有两个选择。当然，你可以初始化该变量，使其指向一个新构造的对象：

```java
startTime = new Date();
```

或者，你可以将变量指向一个已存在的对象：

```java
startTime = rightNow;
```

现在，两个变量都指向*同一个*对象（参见图 4.4）。

![Images](img/04fig04.jpg)

**图 4.4** 指向同一个对象的对象变量

重要的是要意识到，对象变量实际上并不包含对象。它只是*引用*一个对象。在 Java 中，任何对象变量的值都是指向存储在其他地方对象的引用。`new`运算符的返回值也是引用。这样的语句：

```java
Date startTime = new Date();
```

包含两个部分。表达式`new Date()`创建了一个`Date`类型的对象，它的值是对该新创建对象的引用。该引用随后存储在`startTime`变量中。

你可以显式地将对象变量设置为`null`，表示它目前没有引用任何对象。

```java
startTime = null; . . .

if (startTime != null)
    System.out.println(startTime);
```

我将在第 4.3.6 节中详细讨论`null`。

---

![Image](img/c.jpg)

**C++：**

有些人误认为 Java 对象变量就像 C++ 的引用。但在 C++ 中没有空引用，且引用是可以赋值的。你应该将 Java 对象变量类比为 C++*指针*。例如：

```java
Date rightNow; // Java
```

等同于：

```cpp
Date* rightNow; // C++
```

一旦你建立了这种联系，一切都迎刃而解。当然，一个`Date*`指针在调用`new`初始化它之前是没有初始化的。C++ 和 Java 的语法几乎相同。

```cpp
Date* rightNow = new Date(); // C++
```

如果你将一个变量赋值给另一个，那么两个变量都指向同一个对象。Java 的`null`等于 C++ 的`NULL`。

所有的 Java 对象都位于堆上。当一个对象包含另一个对象变量时，它只是指向另一个堆对象的指针。

在 C++ 中，指针让你感到紧张，因为它们很容易出错。在 Java 中，如果你使用未初始化的指针，运行时系统会可靠地产生错误，而不是产生随机结果。你不需要担心内存管理，因为垃圾回收器会处理。

C++ 通过对拷贝构造函数和赋值运算符的支持，付出了很大努力允许实现自动拷贝的对象。例如，链表的拷贝是一个具有相同内容但具有独立链接的新链表。这使得设计与内置类型相同的拷贝行为的类成为可能。在 Java 中，你必须使用`clone`方法获取对象的完整拷贝。

### 4.2.2 Java 库中的 `LocalDate` 类

在之前的示例中，我们使用了标准 Java 库中的`Date`类。`Date`类的实例有一个状态——即*特定的时间点*。

尽管在你使用`Date`类时不需要知道这一点，但时间是用从一个固定点（所谓的*纪元*）开始的毫秒（正或负）来表示的，该点是 UTC 1970 年 1 月 1 日 00:00:00。UTC 是协调世界时，是一种科学时间标准，在实践中与更熟悉的 GMT（即格林威治标准时间）是相同的。

但事实证明，`Date`类对于处理人类用于日期的日历信息（例如“1999 年 12 月 31 日”）并不好用。这种对日期的特定描述遵循格林哥亚历，这是世界上大多数国家使用的历法。同一个时间点在中文农历或希伯来阴太历中的描述会完全不同，更不用说来自火星的客户所使用的历法了。

---

![Image](img/note.jpg)

**注意：**

在人类历史上，各个文明都在努力设计日历，以为日期命名，并为太阳和月亮周期带来秩序。关于世界各地日历的精彩解释（从法国革命历到玛雅长纪历），请参阅 Nachum Dershowitz 和 Edward M. Reingold 出的 *Calendrical Calculations*（Cambridge University Press, 4th ed., 2018）。

---

库的设计者决定将“记录时间”与“为时间点命名”这两个职责分开。因此，标准 Java 库包含两个独立的类：`Date`类表示一个时间点，而`LocalDate`类以熟悉的日历表示法表示日期。Java 8 引入了许多其他用于处理日期时间各个方面的类——请参阅第二卷第 6 章。

将时间测量与日历分离是良好的面向对象设计。通常情况下，使用不同的类来表示不同的概念是一个好主意。

你不需要使用构造函数来构造`LocalDate`类对象。相反，使用静态工厂方法，它们会为你调用构造函数。以下表达式：

```java
LocalDate.now()
```

构造一个表示对象构造时日的新对象。

你可以通过提供年、月、日来构造特定日期的对象：

```java
LocalDate.of(1999, 12, 31)
```



当然，你通常希望将构造的对象存储在对象变量中：

```java
LocalDate newYearsEve = LocalDate.of(1999, 12, 31);
```

一旦你有了一个 `LocalDate` 对象，就可以通过 `getYear`、`getMonthValue` 和 `getDayOfMonth` 方法找到年、月、日：

```java
int year = newYearsEve.getYear(); // 1999
int month = newYearsEve.getMonthValue(); // 12
int day = newYearsEve.getDayOfMonth(); // 31
```

这看起来可能毫无意义，因为它们与你刚刚构造对象时使用的值相同。但有时，你拥有一个已经计算出的日期，然后你会想要调用这些方法来获取它的更多信息。例如，`plusDays` 方法会产生一个新的 `LocalDate`，该对象距离你应用它的对象若干的天数：

```java
LocalDate aThousandDaysLater = newYearsEve.plusDays(1000);

year = aThousandDaysLater.getYear(); // 2002
month = aThousandDaysLater.getMonthValue(); // 09
day = aThousandDaysLater.getDayOfMonth(); // 26
```

`LocalDate` 类封装了实例字段来维护所设置的日期。在不查看源代码的情况下，是不可能知道该类内部使用的表示方法的。但当然，封装的意义在于这并不重要。重要的是类暴露的方法。

---

![Image](img/note.jpg) **注意：**

实际上，`Date` 类也有获取日、月、年的方法，称为 `getDay`、`getMonth` 和 `getYear`，但这些方法是已弃用的（deprecated）。当库的设计者意识到该方法从根本就不应该被引入时，该方法就会被弃。

在库的设计者意识到提供单独类来处理日历更有意义之前，这些方法是 `Date` 类的一部分。当 Java 1.1 引入早期日历类集时，`Date` 方法被标记为已弃。你仍然可以在程序中使用它们，但如果你这样做，将会收到难看的编译器警告。避免使用已弃方法是一个好主意，因为它们可能会库的未来版本中被移除。

---

![Image](img/tip.jpg) **提示：**

JDK 提供了 `jdeprscan` 工具来检查你的代码是否使用了 Java API 的已弃功能。请访问 `https://docs.oracle.com/en/java/javase/17/docs/specs/man/jdeprscan.html` 查看说明。

### 4.2.3 修改器和访问器方法

再次查看你在上一节中看到的 `plusDays` 方法调用：

```java
LocalDate aThousandDaysLater = newYearsEve.plusDays(1000);
```

调用后 `newYearsEve` 发生了什么？它被变成一千年后的状态了吗？事实证明，它没有。`plusDays` 方法产生一个新的 `LocalDate` 对象，然后将该对象赋值给变量 `aThousandDaysLater`。原始对象保持不变。我们说 `plusDays` 方法没有修改（mutate）它所调用的对象。（这类似于你在[第三章]中看到的 `String` 类的 `toUpperCase` 方法）。

### 4.2.4 日历实现

`LocalDate` 类封装了实例字段来维护所设置的日期。在不查看源代码的情况下，是不可能知道该类内部使用的表示方法的。但当然，封装的意义在于这并不重要。重要的是类暴露的方法。

---

![Image](img/note.jpg) **注意：**

实际上，`Date` 类也有获取日、月、年的方法，称为 `getDay`、`getMonth` 和 `getYear`，但这些方法是已弃用的。当库的设计者意识到该方法从根本就不应该被引入时，该方法就会被已弃。

在库的设计者意识到提供单独类来处理日历更有意义之前，这些方法是 `Date` 类的一部分。当 Java 1.1 引入早期日历类集时，`Date` 方法被标记为已弃。你仍然可以在程序中使用它们，但如果你这样做，将会收到难看的编译器警告。避免使用已弃方法是一个好主意，因为它们可能会库的未来版本中被移除。

---

![Image](img/tip.jpg) **提示：**

JDK 提供了 `jdeprscan` 工具来检查你的代码是否使用了 Java API 的已弃功能。请访问 `https://docs.oracle.com/en/java/javase/17/docs/specs/man/jdeprscan.html` 查看说明。

### 4.2.3 修改器和访问器方法

再次查看你在上一节中看到的 `plusDays` 方法调用：

```java
LocalDate aThousandDaysLater = newYearsEve.plusDays(1000);
```

调用后 `newYearsEve` 发生了什么？它被变成一千年后的状态了吗？事实证明，它没有。`plusDays` 方法产生一个新的 `LocalDate` 对象，然后将该对象赋值给变量 `aThousandDaysLater`。原始对象保持不变。我们说 `plusDays` 方法没有修改（mutate）它所调用的对象。（这类似于你在[第三章]中看到的 `String` 类的 `toUpperCase` 方法）。

注意，日历的第一行进行了缩进，这样每月的第一天就会落在相应的星期几。这里是打印表头和第一行缩进的代码：

```java
System.out.println("Mon Tue Wed Thu Fri Sat Sun");

for (int i = 1; i < value; i++)
   System.out.print("  ");
```

现在，我们准备好打印日历的主体了。我们进入一个循环，其中 `date` 遍历月份的每一天。

在每次迭代中，我们打印日期值。如果 `date` 是今天，则用 `*` 标记该日期。然后，我们将 `date` 推进后一天。当我们到达每个新周的开始时，打印一个新行：

```java
while (date.getMonthValue() == month)
{
   System.out.printf("%3d", date.getDayOfMonth());

   if (date.getDayOfMonth() == today)
      System.out.print("*");
   else
      System.out.print(" ");

   date = date.plusDays(1);

   if (date.getDayOfWeek().getValue() == 1)
      System.out.println();
}
```

我们何时停止？我们不知道该月份有 31、30、29 还是 28 天。相反，只要 `date` 仍在当前月份内，我们就继续迭代。

Listing 4.1 显示了完整的程序。

如你所见，`LocalDate` 类使得编写日历程序成为可能，它能够处理星期几和月份长度不等等复杂性。你不需要知道 `LocalDate` 类是如何计算月份和星期的。你只需要使用该类的接口——诸如 `plusDays` 和 `getDayOfWeek` 等方法。

这个示例程序的意义在于向你展示如何使用类的接口来执行相当复杂的任务，而无需了解实现细节。

**Listing 4.1** `CalendarTest/CalendarTest.java`

```java
import java.time.*;

/**
 * @version 1.5 2015005-08
 * @author Cay Horstmann
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
        int value = weekday.getValue(); // 1 = 周一, . . . , 7 = 周日

        System.out.println("Mon Tue Wed Thu Fri Sat Sun");

        for (int i = 1; i < value; i++)
            System.out.print("  ");

        while (date.getMonthValue() == month)
        {
            System.out.printf("%3d", date.getDayOfMonth());

            if (date.getDayOfMonth() == today)
                System.out.print("*");
            else
                System.out.print(" ");

            date = date.plusDays(1);

            if (date.getDayOfWeek().getValue() == 1)
                System.out.println();
        }

        if (date.getDayOfWeek().getValue() != 1)
            System.out.println();
    }
}
```

**`java.time.LocalDate`** **8**

- `static LocalDate now()` 构建一个表示当前日期的对象。
- `static LocalDate of(int year, int month, int day)` 构建一个表示给定日期的对象。
- `int getYear()`
- `int getMonthValue()`
- `int getDayOfMonth()` 获取此日期的年、月、日。
- `DayOfWeek getDayOfWeek()` 以 `DayOfWeek` 类的实例形式获取此日期的星期。在 `DayOfWeek` 实例上调用 `getValue` 可以获取从 `1`（周一）到 `7`（周日）之间的星期。
- `LocalDate plusDays(int n)`
- `LocalDate minusDays(int n)` 返回此日期之前 `n` 天的日期。

### 4.3 定义你的类

在第 3 章中，你开始了简单的类。现在是时候向你展示如何编写更多应用程序所需的类了。

#### 4.3.1 一个 `Employee` 类

Java 中最简单的类形式是：

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

   // 方法
   public String getName()
   {
      return name;
   }

   public double getSalary()
   {
      return salary;
   }

   public void raiseSalary(int percentage)
   {
      salary += salary * percentage / 100;
   }

   public LocalDate getHireDay()
   {
      return hireDay;
   }
}
```

考虑以下 `Employee` 类的简化版本，它可能被工资资单系统使用：

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

   // 方法
   public String getName()
   {
      return name;
   }

   public double getSalary()
   {
      return salary;
   }

   public void raiseSalary(int percentage)
   {
      salary += salary * percentage / 100;
   }

   public LocalDate getHireDay()
   {
      return hireDay;
   }
}
```

我们将在接后的章节中详细拆解该类的实现。首先，Listing 4.2 显示了 `Employee` 类的实际用法。

在程序中，我们构建了一个 `Employee` 数组并填充了三个 `Employee` 对象：

```java
Employee[] staff = new Employee[3];

staff[0] = new Employee("Carl Cracker", 50000, 2005, 6, 15);
staff[1] = new Employee("Harry Hacker", 60000, 2008, 3, 20);
staff[2] = new Employee("Tony Tester", 70000, 2010, 11, 1);
```

接下来，我们使用 `Employee` 类的 `raiseSalary` 方法将每个员工的工资增加 5%：

```java
for (Employee e : staff)
   e.raiseSalary(5);
```

最后，通过 `getName`、`getSalary` 和 `getHireDay` 方法打印每个员工的信息：

```java
for (Employee e : staff)
   System.out.println("name=" + e.getName() + ",salary=" + e.getSalary() + ",hireDay=" + e.getHireDay());
```

注意，示例程序由两个类组成：`Employee` 类和一个带有 `public` 修饰符的 `EmployeeTest` 类。我们刚刚描述的 `main` 方法包含在 `EmployeeTest` 类中。

源文件名为 `EmployeeTest.java`，因为文件名必须与 `public` 类的名称匹配。源文件中只能有一个 `public` 类，但可以有任意数量的非公共类。

接下来，当你编译这段源代码时，编译器会在目录中创建两个类文件：`EmployeeTest.class` 和 `Employee.class`。

然后你通过向字节码解释器提供包含程序 `main` 方法的类名来启动程序：

```bash
java EmployeeTest
```

```java
import java.time.*;

/**
 * This program tests the Employee class.
 * @version 1.13 2018-04-10
 * @author Cay Horstmann
 */
public class EmployeeTest
{
    public static void main(String[] args)
    {
        // fill the staff array with three Employee objects
        Employee[] staff = new Employee[3];

        staff[0] = new Employee("Carl Cracker", 75000, 1987, 12, 15);
        staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
        staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);



```java
// raise everyone's salary by 5%

for (Employee e : staff)
    e.raiseSalary(5);

// print out information about all Employee objects

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
        double raise = salary * byPercent / 100;
        salary += raise;
    }
}
```

#### 4.3.2 使用多个源文件

`Listing 4.2` 中的程序在单个源文件中包含两个类。许多程序员更倾向于将每个类放在它自己的源文件中。例如，你可以将 `Employee` 类放入 `Employee.java` 文件中，将 `EmployeeTest` 类放入 `EmployeeTest.java` 中。

如果你喜欢这种安排，你有两种编译方法可选。你可以使用通配符调用 Java 编译器：

```bash
javac *.java
```

然后，所有匹配通配符的源文件将被编译成类文件。或者，你只需要输入：

```bash
javac EmployeeTest.java
```

你可能会发现很惊讶，第二种选择是有效的，尽管 `Employee.java` 文件从未被显式地编译过。然而，当 Java 编译器看到 `EmployeeTest.java` 内部使用了 `Employee` 类时，它会寻找一个名为 `Employee.class` 的文件。如果找不到该文件，它会搜索 `Employee.java` 并对其进行编译。此外，如果它找到的 `Employee.java` 时间戳比现有的 `Employee.class` 新，Java 编译器将重新编译该文件。

**注意：** 如果你熟悉 UNIX 的 `make` 工具（或其 Windows 对应版本 `make`），你可以认为 Java 编译器已经内置了 `make` 功能。

#### 4.3.3 剖析 `Employee` 类

在接下来的章节中，我们将剖析 `Employee` 类。让我们从该类中的方法开始。通过检查源码可以看出，该类有一个构造函数和四个方法：

```java
public Employee(String n, double s, int year, int month, int day)

public String getName()

public double getSalary()

public LocalDate getHireDay()

public void raiseSalary(double byPercent)
```

该类的所有方法都被标记为 `public`。`public` 关键字意味着任何类中的任何方法都可以调用该方法（四个访问级别将在本章和下一章中介绍）。

接下来，注意用于存储 `Employee` 类实例内部三个实例字段：

```java
private String name;

private double salary;

private LocalDate hireDay;
```

`private` 关键字确保了只有 `Employee` 类本身的方法可以访问这些字段。任何外部方法都无法读取或写入这些字段。

**注意：** 你可以在实例字段上使用 `public` 关键字，但那是一个坏主意。拥有 `public` 实例字段将允许程序的任何部分读取和修改这些实例字段。任何类的任何方法都可以修改公共字段——根据我们的经验，某些代码会在你意想不到的时候利用这种特权。我强烈建议将所有实例字段设为 `private`。

最后，注意其中两个实例字段本身就是对象：`name` 和 `hireDay` 字段是对 `String` 和 `LocalDate` 对象的引用。这是非常常见的：类通常包含类类型的实例字段。

#### 4.3.4 构造函数的第一步

让我们看看 `Employee` 类中的构造函数。

```java
public Employee(String n, double s, int year, int month, int day)
{
    name = n;
    salary = s;
    hireDay = LocalDate.of(year, month, day);
}
```

如你所见，构造函数的名称与类名相同。当你构建 `Employee` 类对象时，会运行此构造函数——为实例字段赋予你想要的初始状态。

例如，当你通过如下代码创建一个 `Employee` 实例时：

```java
new Employee("Carl Cracker", 75000, 1987, 12, 15)
```

你为实例字段设置为：

```java
name = "Carl Cracker";

salary = 75000;

hireDay = LocalDate.of(1987, 12, 15);
```

当你通过如下代码创建一个 `Employee` 实例时：

```java
new Employee("Harry Hacker", 50000, 1989, 10, 1)
```

你为实例字段设置为：

```java
name = "Harry Hacker";

salary = 50000;

hireDay = LocalDate.of(1989, 10, 1);
```

当你通过如下代码创建一个 `Employee` 实例时：

```java
new Employee("Tony Tester", 40000, 1990, 3, 15)
```

你为实例字段设置为：

```java
name = "Tony Tester";

salary = 40000;

hireDay = LocalDate.of(1990, 3, 15);
```

构造函数与其他方法之间有重要的区别。构造函数只能结合 `new` 运算符调用。你不能将构造函数应用于现有对象来重置实例字段。例如：

```java
james.Employee("James Bond", 250000, 1950, 1, 1)
```

这是一个编译错误。

我们将在本章后面的部分讨论更多关于构造器的内容。现在，请记住：

- 构造函数的名称与类名相同。
- 类可以有多个构造函数。
- 构造函数可以接受零、一个或多个参数。
- 构造函数没有返回值。
- 构造函数总是通过 `new` 运算符调用。

**C++ 注意：** 构造函数在 Java 中的工作方式与 C++ 相同。然而，请记住所有的 Java 对象都在堆上构造，且构造函数必须结合 `new` 使用。C++ 程序员的一个常见错误是忘记使用 `new` 运算符：

```cpp
（注：此处在 C++ 中是合法的，但在 Java 中需要 new）
```

#### 4.3.5 使用 `var` 声明局部变量

从 Java 10 开始，你可以使用 `var` 关键字而不是指定类型来声明局部变量，只要其类型可以从初始值推断出来。例如，与其声明：

```java
Employee harry = new Employee("Harry Hacker", 50000, 1989, 10, 1);
```

你只需要写：

```java
var harry = new Employee("Harry Hacker", 50000, 1989, 10, 1);
```

这样做很好，因为它避免了类型名 `Employee` 的重复出现。

从现在起，在那些从右侧显而易见、无需了解 Java API 就能确定类型的情况下，我将使用 `var` 写法。但我不会在 `int`、`long` 或 `double` 等数值类型上使用 `var`，这样你就不需要留意 `0`、`0L` 和 `0.0` 之间的区别。一旦你对 Java API 更加熟悉，你可能想要更频繁地使用 `var` 关键字。

请注意，`var` 关键字只能用于方法内部的*局部*变量。你必须始终声明参数和字段的类型。

#### 4.3.6 处理 `null` 引用

在第 4.2.1 节第 132 页的“对象和对象变量”中，你已经看到对象变量持有指向对象的引用，或者持有一个特殊值 `null` 来表示对象的缺失。

这听起来是一个处理特殊情况（如未知的名称或入职日期）的方便机制。但你必须非常小心处理 `null` 值。

如果你对 `null` 值应用方法，就会发生 `NullPointerException`（空指针异常）。

```java
LocalDate rightNow = null;

String s = rightNow.toString(); // NullPointerException
```

这是一个严重的错误，类似于“索引越界”异常。如果你的程序没有“捕获”异常，程序就会崩溃。

（注：此处原文中 "catch" 翻译为“捕获”，此处语境为处理异常）

由于提供的待翻译文本存在大量重复和乱码的片段，已根据您的要求提取并翻译了核心的逻辑部分。

当然，访问器方法（accessor）和变器方法（mutator）可能需要完成大量工作来在旧新数据表示之间进行转换。这引出了我们的第二个优势：变器方法可以执行错误检查，而简单为字段赋值的代码可能不会进行这些操作。例如，`setSalary` 方法可能会检查薪水是否永远小于 0。

![Image](img/caution.jpg) **注意：**

小心不要编写返回可变对象引用的访问器方法。在本书的之前的一个版本中，我在 `Employee` 类中违反了这一规则，其中 `getHireDay` 方法返回了一个 `Date` 类的对象：

```java
class Employee
{
    private Date hireDay;
    . . .

    public Date getHireDay()
    {
        return hireDay; // BAD
    }
    . . .
}
```

与没有变器方法的 `LocalDate` 类不同，`Date` 类有一个变器方法 `setTime`，你可以在其中设置毫秒数。

`Date` 对象是可变的，这一事实破坏了封装！考虑以下异常代码：

```java
Employee harry = . . .;
Date d = harry.getHireDay();
double tenYearsInMilliseconds = 10 * 365.25 * 24 * 60 * 60 * 1000;
d.setTime(d.getTime() - (long) tenYearsInMilliseconds);
// 给 Harry 增加十年的资历
```

其原因是微妙的。`d` 和 `harry.hireDay` 指向同一个对象（参见图 4.5）。对 `d` 应用变器方法会自动更改 `Employee` 对象的私有状态！

如果你需要返回一个可变对象的引用，你应该先对其 `clone`。克隆是存储在新位置的对象的精确拷贝。克隆将在第 6 章中详细讨论。以下是修正后的代码：

![Images](img/04fig05.jpg)

**图 4.5** 返回可变实例字段的引用

```java
class Employee
{
    . . .

    public Date getHireDay()
    {
        return (Date) hireDay.clone(); // OK
    }
    . . .
}
```

作为一个经验，每当你需要返回一个可变字段的副本时，请始终使用 `clone`。

### 4.3.9 基于类的访问权限

你已经知道方法可以访问其调用的对象的私有数据。人们经常感到惊讶的是，一个方法可以访问*该类中所有对象*的私有数据。例如，考虑一个比较两个员工的 `equals` 方法。

```java
class Employee
{
    . . .

    public boolean equals(Employee other)
    {
        return name.equals(other.name);
    }
}
```

一个典型的调用是：

```java
if (harry.equals(boss)) . . .
```

该方法访问了 `harry` 的私有字段，这并不奇怪。它还访问了 `boss` 的私有字段。这是合法的，因为 `boss` 是类型为 `Employee` 的对象，而 `Employee` 类的方法被允许访问*任何*类型为 `Employee` 的对象的私有字段。

![Image](img/c.jpg) **C++ 注意：**

C++ 遵循相同的规则。方法可以访问其类中任何对象的私有特性，而不仅仅是隐式参数。

#### 4.3.10 私有方法

在实现类时，我们将所有实例字段设为私有，因为公共数据是危险的。但方法呢？虽然大多数方法是公共的，但私有方法在某些情况下很有用。有时，你可能希望将计算代码拆分为单独辅助方法。通常，这些辅助方法不应该是公共接口的一部分——它们可能与当前实现过于，或者需要特殊的协议或调用顺序。此类方法最好实现为私有。

在 Java 中实现私有方法，只需将 `public` 关键字更改为 `private` 即可。

通过将方法设为私有，当你更改实现时，你没有义务保持它的可用性。如果数据表示发生变化，该方法的实现可能会变得*更困难*或*不再必要*；这并不重要。要点在于，只要方法是私有的，类的设计者就可以确保它没有在其他地方使用，因此他们可以简单地丢弃它。如果方法是公共的，你就不能简单地丢弃它，因为其他代码可能依赖于它。

#### 4.3.11 `final` 实例字段

你可以将实例字段定义为 `final`。此类字段在对象构造时必须初始化。也就是说，你必须保证在每个构造函数结束后字段值已设置。此后，该字段可能再被修改。例如，`Employee` 类的 `name` 字段可以声明为 `final`，因为在对象构造后它永远不会改变——没有 `setName` 方法。

```java
class Employee
{
    private final String name;
    . . .
}
```

`final` 修饰符对于类型为原始类型或*不可变类*的字段特别有用。（如果一个类没有任何方法会改变其对象，则该类是不可变的。例如，`String` 类就是不可变的。）

对于可变类，`final` 修饰符可能会引起混淆。例如，考虑一个字段：

```java
private final StringBuilder evaluations;
```

它在 `Employee` 构造函数中初始化为：

```java
evaluations = new StringBuilder();
```

`final` 关键字仅意味着存储在 `evaluations` 变量中的对象引用将不再指向不同的 `StringBuilder` 对象。但对象本身是可以变的：

```java
public void giveGoldStar()
{
    evaluations.append(LocalDate.now() + ": Gold star!\n");
}
```

### 4.4 静态字段和方法

在你学过的所有示例程序中，`main` 方法都标记有 `static` 修饰符。我们现在准备讨论此修饰符的含义了。

#### 4.4.1 静态字段

如果你将字段定义为 `static`，那么该字段不存在于类的对象中。每个静态字段都只有一个副本。你可以将静态字段看作属于类，而不是属于单个对象。例如，假设我们想为每个员工分配一个唯一的数字。我们在 `Employee` 类中添加一个实例字段 `id` 和一个静态字段 `nextId`：

```java
class Employee
{
    private static int nextId = 1;
    private int id;
    . . .
}
```

每个 `Employee` 对象现在都有自己的 `id` 字段，但只有一个 `nextId` 字段。另一种说法，如果有 1000 个 `Employee` 对象，那么就有 1000 个实例字段 `id`。但只有一个静态字段 `nextId`。即使没有 `Employee` 对象，该静态字段 `nextId` 也存在。它属于类，而不是属于任何特定的对象。



![Image](img/note.jpg) **注意：** 在某些面向对象的编程语言中，静态字段被称为*类字段*。“static”一词是从 C++ 遗留下来的。

---

在构造函数中，我们将下一个可用 ID 分配给新的 `Employee` 对象并对其递增：

```java
id = nextId;
nextId++;
```

假设我们构造对象 `harry`。那么 `harry` 的 `id` 字段设置为静态字段 `nextId` 的当前值，然后静态字段的值递增：

```java
harry.id = Employee.nextId;
Employee.nextId++;
```

#### 4.4.2 静态常量

静态变量很少见。然而，静态常量更为常见。例如，`Math` 类定义了一个静态常量：

```java
public class Math
{
  . . .
  static final double PI = 3.14159265358979323846;
  . . .
}
```

你可以在程序中使用 `Math.PI` 访问此常量。

如果省略了 `static` 关键字，那么 `PI` 将是 `Math` 类的实例字段。也就是说，你需要该类的一个对象来访问 `PI`，并且每个 `Math` 对象都有自己的 `PI` 副本。

你多次运行的另一个静态常量是 `System.out`。它在 `System` 类中声明如下：

```java
public class System
{
   . . .   public static final PrintStream out = . . .;
   . . .
}
```

正如多次提到的那样，拥有公共字段永远不是一个好主意，因为每个人都可以修改它们。然而，公共常量（即 `final` 字段）是可以的。由于 `out` 已被声明为 `final`，你无法将另一个打印流赋值给它：

```java
System.out = new PrintStream(. . .); // 错误--out 是 final
```

---

![Image](img/note.jpg) **注意：**

如果你查看 `System` 类，你会发现一个名为 `setOut` 的方法，它可以将 `System.out` 设置为不同的流。你可能会奇怪该方法是如何改变一个 `final` 变量的值的。然而，`setOut` 方法是一个 `native`（原生）方法，不是用 Java 语言实现的。原生方法可以绕过 Java 语言的访问控制机制。这是一种非常不寻常的变通，你不应该在程序中模拟它。

---

#### 4.4.3 静态方法

静态方法是不操作对象的方法。例如，`Math` 类的 `pow` 方法就是一个静态方法。该表达式

```java
Math.pow(x, a)
```

计算 `x`^(`a`) 次方。它没有使用任何 `Math` 对象来执行其任务。换句话说，它没有隐式参数。

你可以将静态方法理解为没有 `this` 参数的方法。（在非静态方法中，`this` 参数引用方法的隐式参数——参见第 4.3.7 节 中的“隐式参数和显式参数”，第 150 页。）

`Employee` 类的静态方法无法访问 `id` 实例字段，因为它不操作对象。然而，静态方法可以访问静态字段。这里是此类静态方法的示例：

```java
public static int advanceId()
{
   int r = nextId; // 获取下一个可用 id
   nextId++;
   return r;
}
```

要调用此方法，你需要提供类名：

```java
int n = Employee.advanceId();
```

你可以省略该方法的 `static` 关键字吗？可以，但你你需要一个类型为 `Employee` 的对象引用来调用该方法。

---

![Image](img/note.jpg) **注意：**

使用对象调用静态方法是合法的。例如，如果 `harry` 是一个 `Employee` 对象，那么你可以调用 `harry.advanceId()` 而不是 `Employee.advanceId()`。然而，我发现这种记法令人困惑。`advanceId` 方法完全没有看 `harry` 来计算结果。我建议你使用类名而不是对象来调用静态方法。

在两种情况下请使用静态方法：

- 当方法不需要访问对象状态，因为所有需要的参数都是作为显式参数提供的（例如：`Math.pow`）。
- 当方法只需要访问类的静态字段时（例如：`Employee.advanceId`）。

---

![Image](img/c.jpg) **C++ 注意事项：**

静态字段和方法在 Java 和 C++ 中具有相同的功能。然而，语法略有不同。在 C++ 中，你使用 `::` 运算符在作用域之外访问静态字段或方法，例如 `Math::PI`。

“static”一词有着奇特的历史。起初，C 语言引入了 `static` 关键字来表示退出块后不会消失的局部变量。在这种语境下，“static”一词是有意义的：变量保留了下来，当再次进入块时它仍然在那里。然后 `static` 在 C 中有了第二种含义，表示无法从其他文件访问的全局变量和函数。`static` 关键字简单地被重用以避免引入新关键字。最后，C++ 重复使用了该关键字进行第三种无关的解释——表示属于某个类但不属于该类任何特定对象的变量和函数。这与该关键字在 Java 中的含义相同。

#### 4.4.4 工厂方法

这是静态方法的另一种常见用途。如 `LocalDate` 和 `NumberFormat` 等类使用静态的**工厂方法**来构造对象。你已经见过工厂方法 `LocalDate.now` 和 `LocalDate.of`。以下是获取各种样式的格式化器对象的方法：

```java
NumberFormat currencyFormatter = NumberFormat.getCurrencyInstance();
NumberFormat percentFormatter = NumberFormat.getPercentInstance();
double x = 0.1;
System.out.println(currencyFormatter.format(x)); // 打印 $0.10
System.out.println(percentFormatter.format(x)); // 打印 10%
```

为什么 `NumberFormat` 类不使用构造函数？有两个原因：

- 你不能给构造函数命名。构造函数的名称总是与类名相同。但我们需要两个不同的名称来获取货币实例和百分比实例。
- 当你使用构造函数时，无法改变构造对象的类型。但工厂方法实际上返回 `DecimalFormat` 类的对象，它是 `NumberFormat` 类的子类。（更多信息请参见第 5 章。）

#### 4.4.5 `main` 方法

注意，你可以在没有对象的情况下调用静态方法。例如，你从未构造 `Math` 类的任何对象来调用 `Math.pow`。

出于同样的原因，`main` 方法是一个静态方法。

```java
public class Application
{
   public static void main(String[] args)
   {
      . . .
   }
}
```

`main` 方法不操作任何对象。事实上，当程序启动时，没有任何对象。

---

![Image](img/tip.jpg) **提示：**

每个类都可以有一个 `main` 方法。这是一个为类添加演示代码的巧妙小技巧。例如，你可以为 `Employee` 类添加一个 `main` 方法：

```java
class Employee
{
   public Employee(String n, double s, int year, int month, int day)
   {
      name = n;
      salary = s;
      hireDay = LocalDate.of(year, month, day);
   }
   . . .
   public static void main(String[] args) // 单元测试
   {
      var e = new Employee("Romeo", 50000, 2003, 3, 31);
      e.raiseSalary(10);
      System.out.println(e.getName() + " " + e.getSalary());
   }
   . . .
}
```

要查看 `Employee` 类的演示，只需执行：

```bash
java Employee
```

如果 `Employee` 类是较大应用程序的一部分，你通过以下方式启动应用程序：

```bash
java Application
```

`Employee` 类的 `main` 方法永远不会被执行。

列表 4.3 中的程序包含 `Employee` 类的简单版本，其中包含一个静态字段 `nextId` 和一个静态方法 `advanceId`。我们用三个 `Employee` 对象填充数组，然后打印员工信息。最后，打印下一个可用的标识号，以演示静态方法。

```java
/**
 * This program demonstrates static methods.
 * @version 1.02 2008-04-10
 * @author Cay Horstmann
 */
public class StaticTest
{
    public static void main(String[] args)
    {
        // fill the staff array with three Employee objects
        var staff = new Employee[3];

        staff[0] = new Employee("Tom", 40000);
        staff[1] = new Employee("Dick", 60000);
        staff[2] = new Employee("Harry", 65000);

        // print out information about all Employee objects
        for (Employee e : staff)
        {
            System.out.println("name=" + e.getName() + ",id=" + e.getId() + ",salary="
                + e.getSalary());
        }

        int n = Employee.getNextId(); // calls static method
        System.out.println("Next available id=" + n);
    }
}

class Employee
{
    private static int nextId = 1;

    private String name;
    private double salary;
    private int id;

    public Employee(String n, double s)
    {
        name = n;
        salary = s;
        id = advanceId();
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

    public static int advanceId()
    {
        int r = nextId;
        nextId++;
        return r;
    }

    public static void main(String[] args) // unit test
    {
        var e = new Employee("Harry", 50000);
        System.out.println(e.getName() + " " + e.getSalary());
    }
}
```

### 4.5 方法参数

让我们复习描述在各种编程语言中如何将参数传递给方法（或函数）的计算机科学术语。*值传递*（call by value）意味着方法获取的是调用者提供的值。相比之下，*引用传递*（call by reference）意味着方法获取的是调用者提供的变量的*位置*。因此，方法可以修改通过引用传递的变量中存储的值，但不能修改通过值传递的变量。还有*名传递*（call by name），它主要具有历史意义，被应用于 Algol 中，这是最古老的高级语言之一。

Java 编程语言始终使用值传递。这意味着方法获取的是所有参数值的一个拷贝。特别地，方法无法修改传递给它的任何参数的内容。例如，考虑以下调用：

```java
double percent = 10;
harry.raiseSalary(percent);
```

无论方法如何实现，我们都知道在方法调用之后，`percent` 的值仍然是 `10`。让我们更仔细地观察一下这种情况。假设一个方法尝试将方法参数的值增加三倍：

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

然而，这不起作用。在方法调用后，`percent` 的值仍然是 `10`。发生的情况如下：

1. `x` 被初始化为 `percent` 值的拷贝（即 `10`）。
2. `x` 被乘以 3——它现在是 `30`。但 `percent` 仍然是 `10`（见图 4.6）。
3. 方法结束，参数变量 `x` 不再被使用。

然而，方法参数有两种类型：

- 基本数据类型（数字、`boolean` 值）
- 对象引用

你已经看到方法是不可能改变基本类型参数的。对于对象参数，情况有所不同。你可以轻松地实现一个让员工薪水增加三倍的方法：

```java
public static void tripleSalary(Employee x) // 起作用
{
    x.raiseSalary(200);
}
```

当您调用：

```java
harry = new Employee(...);
tripleSalary(harry);
```

时，会发生以下情况：

![Images/04fig06.jpg]

**图 4.6** 修改参数变量没有持久影响。

1. `x` 被初始化为 `harry` 值的拷贝——即一个对象引用。
2. `raiseSalary` 方法应用于该对象引用。`x` 和 `harry` 共同指向的那个 `Employee` 对象的薪水增加了 200%。
3. 方法结束，参数变量 `x` 不再被使用。当然，对象变量 `harry` 继续指向那个薪水已增加三倍的对象（见图 4.7）。

正如你所见，实现改变对象参数状态的方法是轻而易见的，而且事实上非常常见。原因很简单：方法获取的是对象引用的拷贝，原始引用和拷贝都指向同一个对象。许多编程语言（特别是 C++ 和 Pascal）有两种参数传递机制：值传递和引用传递。一些程序员（不幸的是，甚至还有一些书的作者）声称 Java 对对象使用引用传递。这是错误的。由于这是一个非常常见的误解，我们值得详细检查一个反例。

让我们尝试写一个交换两个 `Employee` 对象的方法：

![Images/04fig07.jpg]

**图 4.7** 修改参数指向的对象具有持久影响。

```java
public static void swap(Employee x, Employee y) // 不起作用
{
    Employee temp = x;
    x = y;
    y = temp;
}
```

如果 Java 对对象使用引用传递，这个方法将生效：

```java
var a = new Employee("Alice", ...);
var b = new Employee("Bob", ...);
swap(a, b);

// 现在 a 是否指向 Bob，b 是否指向 Alice？
```

然而，该方法并没有更改存储在 `a` 和 `b` 中的引用。`swap` 方法的 `x` 和 `y` 初始化为这些引用的*拷贝*。方法随后交换这些拷贝。

```java
// x 指向 Alice，y 指向 Bob
Employee temp = x;
x = y;
y = temp;

// 现在 x 指向 Bob，y 指向 Alice
```

但最终，这是徒劳。当方法结束时，参数变量 `x` 和 `y` 被弃用。原始变量 `a` 和 `b` 仍然指向调用之前的相同对象（见图 4.8）。

![Images/04fig08.jpg]

**图 4.8** 交换参数变量没有持久影响。

这证明了 Java 编程语言对对象并不使用引用传递。相反，*对象引用是通过值传递的。*

以下是关于对 Java 方法参数可以做和不能做的总结：

- 方法不能修改基本数据类型的参数（即数字或 `boolean` 值）。
- 方法可以改变对象参数的*状态*。
- 方法不能让对象参数指向一个新的对象。

列表 4.4 中的程序演示了这些事实。该程序首先尝试将数字参数的值增加三倍，但没有成功：

```text
Testing tripleValue:

Before: percent=10.0

End of method: x=30.0

After: percent=10.0
```

随后，它成功地将员工的薪水增加了三倍：



```text
Testing tripleSalary:

Before: salary=50000.0

End of method: salary=150000.0

After: salary=150000.0
```

方法完成后，`harry` 所引的对象的状态发生了变化。这是可能的，因为方法通过对象引用的副本修改了状态。

最后，程序演示了 `swap` 方法的失败：

```text
Testing swap:

Before: a=Alice

Before: b=Bob

End of method: x=Bob

End of method: y=Alice

After: a=Alice

After: b=Bob
```

如所示，参数变量 `x` 和 `y` 被交换了，但变量 `a` 和 `b` 没有受到影响。

---

![Image](img/c.jpg) **C++ 注意：**

C++ 同时拥有有值传递和引用传递。你用 `&` 标记引用参数。例如，你可以轻松地实现 `void tripleValue(double& x)` 或 `void swap(Employee& x, Employee& y)` 方法，来修改它们的引用参数。

---

**Listing 4.4** `ParamTest/ParamTest.java`

```java
/**/**
 * 此程序演示了 Java 中的参数传递。
 * @version 1.01 2018-04-10
 * @author Cay Horstmann
 */
public class ParamTest
{
    public static void main(String[] args)
    {
        /*
         * 测试 1: 方法不能修改数值型参数
         */
        System.out.println("Testing tripleValue:");
        double percent = 10;
        System.out.println("Before: percent=" + percent);
        tripleValue(percent);
        System.out.println("After: percent=" + percent);

        /*
         * 测试 2: 方法可以改变对象参数的状态
         */
        System.out.println("\nTesting tripleSalary:");
        var harry = new Employee("Harry", 50000);
        System.out.println("Before: salary=" + harry.getSalary());
        tripleSalary(harry);
        System.out.println("After: salary=" + harry.getSalary());

        /*
         * 测试 3: 方法不能为对象参数挂载新对象
         */
        System.out.println("\nTesting swap:");
        var a = new Employee("Alice", 70000);
        var b = new Employee("Bob", 60000);
        System.out.println("Before: a=" + a.getName());
        System.out.println("Before: b=" + b.getName());
        swap(a, b);

        System.out.println("After: a=" + a.getName());
        System.out.println("After: b=" + b.getName());
    }

    public static void tripleValue(double x) // 无效
    {
        x = 3 * x;
        System.out.println("End of method: x=" + x);
    }

    public static void tripleSalary(Employee x) // 有效
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
}

class Employee // 简化类
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

你已经见过如何编写简单的构造器来定义对象的初始状态。然而，由于对象构造非常重要，Java 提供了多种编写构造器的方法。我们将在后面的章节中介绍这些方法。

### 4.6.1 重载

某些类有多个构造器。例如，你可以构造一个空的 `StringBuilder` 对象：

```java
var messages = new StringBuilder();
```

或者，你可以指定一个初始字符串：

```java
var todoList = new StringBuilder("To do:\n");
```

这种能力被称为*重载*。如果多个方法具有相同的名称（在本例中为 `StringBuilder` 构造器）但参数不同，编译器必须确定调用哪个方法。它通过匹配方法头中的参数类型与方法调用中使用的类型来选择正确的方法。如果编译器无法匹配参数，要么是因为完全没有匹配，要么是因为没有一个方法是优于其他方法的。（寻找匹配的过程被称为*重载解析*。）

---

![Image](img/note.jpg) **注意：**

Java 允许你重载任何方法——而不只是构造器方法。因此，要完全描述一个方法，你需要指定它的名称及其参数类型。这被称为方法的*签名*。例如，`String` 类有四个名为 `indexOf` 的公共方法。它们的签名如下：

```text
indexOf(int)
indexOf(int, int)
indexOf(String)
indexOf(String, int)
```

返回值不是方法签名的一部分。也就是说，你不能拥有两个名称和参数类型相同但返回值不同的方法。

---

### 4.6.2 默认字段初始化

如果你不在构造器中显式设置字段，它会被设置为默认值：数字为 `0`，`boolean` 值为 `false`，对象引用为 `null`。有些人认为依赖默认值是不良编程习惯。无疑，如果字段是不可见地初始化的，会让别人难以理解你的代码。

---

![Image](img/note.jpg) **注意：**

这是字段和局部变量之间的重要区别。你必须在方法中显式初始化局部变量。但在类中，如果你不初始化字段，它会自动初始化为默认值。

---

例如，考虑 `Employee` 类。假设你没有在构造器中指定如何初始化某些字段。默认情况下，`salary` 字段将初始化为 `0`，而 `name` 和 `hireDay` 字段将初始化为 `null`。

然而，这不是一个好主意。如果任何人调用 `getName` 或 `getHireDay` 方法，他们将得到一个可能并未料到的 `null` 引用：

```java
LocalDate h = harry.getHireDay();

int year = h.getYear(); // 如果 h 为 null 则抛出异常
```

### 4.6.3 无参数构造器

许多类包含一个无参数的构造器，创建一个状态被设置为适当默认值的对象。例如，这里是 `Employee` 类的无参数构造器：

```java
public Employee()
{
    name = "";
    salary = 0;
    hireDay = LocalDate.now();
}
```

如果你写了一个没有任何构造器的类，那么将为你提供一个无参数构造器。这个构造器将*所有*实例字段设置为它们的默认值。因此，实例字段中的所有数值数据都为 `0`，所有 `boolean` 值都为 `false`，所有对象变量都为 `null`。

如果一个类提供了至少一个构造器但未提供无参数构造器，那么在不提供参数的情况下构造对象是非法的。例如，我们在 Listing 4.2 中原始的 `Employee` 类提供了一个构造器：

```java
public Employee(String n, double s, int year, int month, int day)
```

对于该类，构造默认员工是不合法的。也就是说，调用

```java
e = new Employee();
```

将会是一个错误。

请记住，当你的类没有其他构造方法时，你会获得一个免费的无参数构造方法 `only`。如果你为类编写了即使是一个自己的构造方法，并且希望类的用户能够通过调用来创建实例：

```java
new ClassName()
```

那么你必须提供一个无参数构造方法。当然，如果你对所有字段的默认值感到满意，可以直接提供：

```java
public ClassName()
{
}
```

---

## 4.6 对象构造

---

![Image](img/c.jpg) **C++ 注意：**

C++ 有一种特殊的构造字段的初始化列表语法，例如：

```cpp
Employee::Employee(String n, double s, int y, int m, int d) // C++

: name(n),
  salary(s),
  hireDay(y, m, d)
{
}
```

C++ 使用这种特殊语法来避免不无参数构造方法的调用。在 Java 中，没有这种，因为对象没有子对象，只有指向其他对象的引用。

---

### 4.6.4 显式字段初始化

通过重载类中的构造方法，你可以构建许多方法来设置类实例字段的初始状态。确保无论调用哪个构造方法，每个实例字段都被设置为某个有意义的值始终是一个好主意。

你可以简单地为类定义中的任何字段赋值。例如：

```java
class Employee
{
    private String name = "";
    . . .
}
```

此赋值在构造方法执行之前完成。如果一个类的所有构造方法都需要将特定的实例字段设为相同的值，这种语法就特别有用。

初始化值不必是常量。这里有一个使用方法调用初始化字段的示例。考虑 `Employee` 类，每个员工都有一个 `id` 字段。你可以这样初始化它：

```java
class Employee
{
    private static int nextId;

    private int id = advanceId();

    . . .

    private static int advanceId()
    {
        int r = nextId;
        nextId++;
        return r;
    }

    . . .
}
```

### 4.6.5 参数命名

当你编写非常简单的构造方法（而且你会写很多这种）时，想出参数名称可能会有点沮丧。

我们通常倾向于单字母参数名：

```java
public Employee(String n, double s)
{
    name = n;
    salary = s;
}
```

然而，缺点是你需要通过阅读代码才能知道 `n` 和 `s` 参数的含义。

有些程序员会在每个参数前加上前缀“`a`”：

```java
public Employee(String aName, double aSalary)
{
    name = aName;
    salary = aSalary;
}
```

这样好一些。任何读者都能立即明白参数的含义。

另一个常用的技巧依赖于参数变量会“遮蔽（shadow）”同名的实例字段。例如，如果你将参数命名为 `salary`，那么 `salary` 指的是参数，而不是实例字段。但你仍然可以通过 `this.salary` 访问实例字段。记住 `this` 表示的是隐式参数——即正在被构造的对象。这里有一个示例：

```java
public Employee(String name, double salary)
{
    this.name = name;
    this.salary = salary;
}
```

---

![Image](img/c.jpg) **C++ 注意：**

在 C++ 中，在实例字段前加上下划线或固定字母是常见的（字母 `m` 和 `x` 是常用的选择）。例如，工资字段可能会被命名为 `_salary`、`mSalary` 或 `xSalary`。Java 程序员通常这样做。

---

### 4.6.6 调用另一个构造方法

关键字 `this` 指方法的隐式参数。然而，这个关键字有第二个含义。

如果构造方法的第一语句的形式为 `this(. . .)`，那么该构造方法会调用同一类的另一个构造方法。这是一个典型的示例：

```java
public Employee(double s)
{
    // 调用 Employee(String, double)
    this("Employee #" + nextId, s);
    nextId++;
}
```

当你调用 `new Employee(60000)` 时，`Employee(double)` 构造方法调用 `Employee(String, double)` 构造方法。

这样使用 `this` 关键字是有用的——你只需要写一次公共的构造代码。

---

![Image](img/c.jpg) **C++ 注意：**

Java 中的 `this` 引用与 C++ 中的 `this` 指针相同。但在 C++ 中，一个构造方法无法调用另一个。如果你想提取公共的构造代码，必须编写一个单独的方法。

---

### 4.6.7 初始化块

你已经见过两种初始化实例字段的方法：

- 在构造方法中设置值
- 在声明中赋值

Java 中还有第三种机制，称为*初始化块（initialization block）*。类声明可以包含任意的代码块。当该类的对象被构造时，这些代码块会被执行。例如：

```java
class Employee
{
    private static nextId;

    private int id;

    private String name;

    private double salary;

    // 初始化块
    {
        id = nextId;
    }

    nextId++;

    public Employee(String n, double s)
    {
        name = n;
        salary = s;
    }

    public Employee()
    {
    }
}
```

在这个示例中，`id` 字段在初始化块中被初始化。初始化块首先运行，然后执行构造方法的体。

这种机制永远不是必要的，也不常见。将初始化代码放在构造方法内部通常更直接。

---

![Image](img/note.jpg) **注意：**

即使字段只在之后定义，在初始化块中设置字段也是合法的。然而，为了避免循环定义，读取尚未初始化的字段是非合法的。具体的规则在《Java 语言规范》第 8.3.3 节中说明（http://docs.oracle.com/javase/specs）。这些规则复杂到让编译器实现者都感到困惑——早期的 Java 在实现它们时存在细微的错误。因此，你应该始终将初始化块放在字段定义之后。

---

有如此多的初始化实例字段的方法，为构造过程提供所有可能的路径可能会非常困惑。以下是调用构造方法时详细的发生情况：

1. 如果构造方法的第一行调用了第二个构造方法，则第二个构造方法将使用提供的参数执行。
2. 否则：
   - 所有实例字段都被初始化为默认值（`0`、`false` 或 `null`）。
   - 所有字段初始化器和初始化块将按照它们在类声明中出现的顺序被执行。
3. 执行构造方法的体。

静态初始化发生在类首次加载时。与实例字段一样，静态字段的默认值是 `0`、`false` 或 `null`，除非你显式地将它们设置为其他值。所有的静态字段初始化器和静态初始化块按照它们在类声明中出现的顺序进行执行。

---

![Image](img/note.jpg) **注意：**



令人惊讶的是，在 JDK 6 之前，在 Java 中可以在完全不编写 `main` 方法的情况下编写一个“Hello, World”程序。

```java
public class Hello
{
   static
   {
      System.out.println("Hello, World");
   }
}
```

当你使用 `java Hello` 调用该类时，类被加载，静态初始化块打印出“Hello, World”，只有之后才会显示 `main` 未定义的错误信息。从 Java 7 开始，`java` 程序会先检查是否存在 `main` 方法。

---

此示例使用了 `Random` 类来生成随机数。从 JDK 17 开始，`java.util.random` 包提供了具有不同权衡的强算法实现。阅读 `java.util.random` 包的 API 文档以获取选择何种算法的建议。然后通过提供如下算法名称来获取实例：

```java
RandomGenerator generator = RandomGenerator.of("L64X128MixRandom");
```

通过调用 `generator.nextInt(n)` 或其他 `RandomGenerator` 方法生成随机数。`RandomGenerator` 是一个接口，这是在第 6 章中引入的概念。你可以对 `Random` 类的对象使用所有的 `RandomGenerator` 方法。

列表 4.5 中的程序展示了本节讨论的许多特性：

- 重载构造函数
- 使用 `this(. . .)` 调用另一个构造函数
- 无参数构造函数
- 对象初始化块
- 静态初始化块
- 实例字段初始化

**列表 4.5** `ConstructorTest/ConstructorTest.java`

```java
 1  import java.util.*;
 2
 3  /**
 4    * 此程序演示了对象的构造。
 5    * @version 1.02 2018-04-10
 6    * @author Cay Horstmann
 7    */
 8  public class ConstructorTest
 9  {
10      public static void main(String[] args)
11      {
12          // 用三个 Employee 对象填充 staff 数组
13          var staff = new Employee[3];
14
15          staff[0] = new Employee("Harry", 40000);
16          staff[1] = new Employee(60000);
17          staff[2] = new Employee();
18
19          // 打印所有 Employee 对象的信息
20          for (Employee e : staff)
21              System.out.println("name=" + e.getName() + ",id=" + e.getId() + ",salary="
22                  + e.getSalary());
23      }
24  }
25
26  class Employee
27  {
28    private static int nextId;
29
30    private int id;
31    private String name = ""; // 实例字段初始化
32    private double salary;
33
34    private static Random generator = new Random();
35
36    // 静态初始化块
37    static
38    {
39      // 将 nextId 设置为 0 到 9999 之间的随机数
40      nextId = generator.nextInt(10000);
41    }
42
43    // 对象初始化块
44    {
45      id = nextId;
46      nextId++;
47    }
48
49    // 三个重载构造函数
50    public Employee(String n, double s)
51    {
52      name = n;
53      salary = s;
54    }
55
56    public Employee(double s)
57    {
58      // 调用 Employee(String, double) 构造函数
59      this("Employee #" + nextId, s);
60    }
61
62    // 默认构造函数
63    public Employee()
64    {
65      // name 初始化为 ""--见上文
66      // salary 未设置--初始化为 0
67      // id 在初始化块中初始化
68    }
69
70    public String getName()
71    {
72      return name;
73    }
74
75    public double getSalary()
76    {
77      return salary;
78    }
79
80    public int getId()
81    {
82      return id;
83    }
84  }
```

`java.util.Random` 1.0

---

- `Random()` 构造一个新的随机数生成器。

`java.util.random.RandomGenerator` 17

---

- `int nextInt(int n)` 返回一个 0 到 `n` - 1 之间的随机整数。
- `static RandomGenerator of(String name)` 根据给定的名称产生一个对应算法的随机数生成器。名称为 `"L64X128MixRandom"` 的算法适用于大多数应用程序。

## 4.6 对象的析构与 `finalize` 方法

有些面向对象的语言（如 C++）具有显式的析构方法。Java 不支持析构，垃圾回收器会在对象不再被使用时进行回收。然而，你无法预知对象何时会被回收，因此 `finalize` 方法是不可靠的。

![Image](img/caution.jpg) **注意：**

不要使用 `finalize` 方法。该方法旨在在垃圾回收器清理对象时调用。

---

## 4.7 记录（Records）

有时候，数据就是数据，而面向对象的隐藏反而成了阻碍。考虑一个描述平面的、具有 `x` 和 `y` 坐标的 `Point` 类。当然，你可以创建一个类：

```java
class Point
{
   private final double x;
   private final double y;
   public Point(double x, double y) { this.x = x; this.y = y; }
   public double getX() { return x; }
   public double getY() { return y; }
   public String toString() { return "Point[x=%d, y=%d]".formatted(x, y); }
   // 更多方法 ...
}
```

但是，隐藏 `x` 和 `y` 并通过 getter 方法提供值真的能带给我们什么吗？

我们真的想要更改 `Point` 的实现吗？当然，有极坐标，但你不会在图形 API 使用它们。在实践中，平面点完全由 `x` 和 `y` 坐标描述。

为了更简洁地定义此类类，JDK 14 引入了“record”作为预览功能。最终版本在 JDK 16 中发布。

### 4.7.1 Record 概念

record 是一种特殊的类形式，其状态是不可变的且公开可读的。以下是定义 `Point` 的方式：

```java
record Point(double x, double y) { }
```

结果是一个具有实例字段的类：

```java
double x;

final double y;
```

在 Java 语言规范中，record 的实例字段被称为其组件（components）。

该类有一个构造函数：

```java
Point(double x, double y)
```

以及访问器方法：

```java
public double x()

public double y()
```

注意，访问器的方法是 `x` 和 `y`，而不是 `getX` 和 `getY`。在 Java 中，实例字段和方法同名是合法的。

```java
var p = new Point(3, 4);

System.out.println(p.x() + " " + p.y());
```

Java 并没有遵循 `get` 命名规范，因为它有点混乱。对于 `Boolean` 字段，通常使用 `is` 而不是 `get`。此外，首字母的大小写也可能会产生问题。如果一个类拥有字段 `x` 和 `X`，该会发生什么呢？有些程序员感到很困扰，因为他们的遗留类无法简单地转换为记录（record）。但在实践中，许多此类遗留类是可变的，因此它们不是转换为记录的候选对象。

除了字段访问器方法，每个记录都自动定义了三个方法：`toString`、`equals` 和 `hashCode`。你将在下一章学习更多关于这些方法的知识。

![Image](img/caution.jpg) **注意：**

你可以定义自动方法的自定义版本，只要它们的参数和返回类型相同即可。例如，这种定义是合法的：

```java
record Point(double x, double y)
{
   public double x() { return y; } // 糟糕的做法
}
```

但这无疑不是一个好主意。

你可以为记录添加你自己的方法：

```java
record Point(double x, double y)
{
   public double distanceFromOrigin() { return Math.hypot(x, y); }
}
```

记录像任何类一样，可以拥有静态字段和方法：

```java
record Point(double x, double y)
{
   public static Point ORIGIN = new Point(0, 0);
   public static double distance(Point p, Point q)
   {
      return Math.hypot(p.x - q.x, p.y - q.y);
   }
   ...
}
```

然而，你不能为记录添加实例字段：

```java
record Point(double x, double y)
{
   private double r; // 错误
   ...
}
```

![Image](img/caution.jpg) **注意：**

记录的实例字段自动是 `final` 的。然而，它们可能是指向可变对象的引用：

```java
record PointInTime(double x, double y, Date when) { }
```

那么记录的实例就是可变的：

```java
var pt = new PointInTime(0, 0, new Date());
pt.when().setTime(0);
```

如果你希望记录实例是不可变的，请不要在字段中使用可变类型。

![Image](img/tip.jpg) **提示：**

对于完全由一组变量表示的不可变数据，请使用记录而不是类。如果数据是可变的，或者表示可能随时间演变，请使用类。记录更易读、效率更高且在并发程序中更安全。

### 4.7.2 构造函数：规范、自定义和紧凑

自动定义的设置所有实例字段的构造函数被称为规范构造函数（canonical constructor）。

你可以定义额外的自定义构造函数。此类构造函数的第一语句必须调用另一个构造函数，以便最终调用规范构造函数。这是一个示例：

```java
record Point(double x, double y)
{
   public Point() { this(0, 0); }
}
```

这个记录有两个构造函数：规范构造函数和产生原点的无参数构造函数。

如果规范构造函数需要执行额外工作，你可以提供自己的实现：

```java
record Range(int from, int to)
{
   public Range(int from, int to)
   {
      if (from <= to)
      {
         this.from = from;
         this.to = to;
      }
      else
      {
         this.from = to;
         this.to = from;
      }
   }
}
```

然而，我们鼓励在实现规范构造函数时使用紧凑形式。你不需要指定参数列表：

```java
record Range(int from, int to)
{
   public Range // 紧凑形式
   {
      if (from > to) // 交换边界
      {
         int temp = from;
         from = to;
         to = temp;
      }
   }
}
```

紧凑形式的主体是规范构造函数的“序言”。它在参数变量 `from` 和 `to` 赋值给实例字段 `this.from` 和 `this.to` 之前修改了它们。你不能在紧凑构造函数体中读取或修改实例字段。

**列表 4.6** `RecordTest/RecordTest.java`

```java
import java.util.*;

/**
 * 此程序演示了记录。
 * @version 1.0 2021-05-13
 * @author Horstmann
 */
public class RecordTest
{
   public static void main(String[] args)
   {
      var p = new Point(3, 4);
      System.out.println("Coordinates of p: " + p.x() + " " + p.y());
      System.out.println("Distance from origin: " + p.distanceOrigin());
      // 与字段和方法相同的计算
      System.out.println("Distance from origin: " + Point.distance(Point.ORIGIN, p));

      // 一个可变的记录
      var pt = new PointInTime(3, 4, new Date());
      System.out.println("Before: " + pt);
      pt.when().setTime(0);
      System.out.println("After: " + pt);

      // 调用紧凑构造函数
      var r = new Range(4, 3);
      System.out.println("r: " + r);
   }
}

record Point(double x, double y)
{
   // 自定义构造函数
   public Point() { this(0, 0); }
   // 方法
   public double distanceFromOrigin()
   {
      return Math.hypot(x, y);
   }
   // 静态字段
   public static Point ORIGIN = new Point(0, 0);
   // 静态方法
   public static double distance(Point p, Point q)
   {
      return Math.hypot(p.x - q.x, p.y - q.y);
   }
}

record PointInTime(double x, double y, Date when) { }

record Range(int from, int to)
{
   // 紧凑形式
   public Range
   {
      if (from > to) // 交换边界
      {
         int temp = from;
         from = to;
         to = temp;
      }
   }
}
```

## 4.8 包

Java 将类分组在一个名为包（package）的集合中。包有助于组织工作并区分他人提供的代码。在接下来的章节中，你将学习如何使用包。

### 4.8.1 包名

使用包的主要目的是保证类名的唯一性。假设两个程序员都想出了提供 `Employee` 类的主意。只要他们将类放在不同的包中，就不会产生冲突。事实上，为了绝对保证包名的唯一性，可以使用反写的互联网域名（它是已知唯一的）。你可以在不同的项目使用子包。例如，考虑域名 `horstmann.com`。反过来写变为包名 `com.horstmann`。你可以接着添加项目名称，如 `com.horstmann.corejava`。如果你将 `Employee` 类放入该包中。

### 4.8.2 类导入



类可以使用自身包中的所有类以及其他包中的所有`public`类。

## 访问其他包中的公共类

你有两种方法访问另一个包中的公共类。第一种是直接使用完全限定名，即包名后跟类名。例如：

```java
java.time.LocalDate today = java.time.LocalDate.now();
```

这显然很繁琐。一种更简单且常见的方法是使用`import`语句。`import`语句的作用是提供引用包内类的简写方式。一旦添加了`import`，就不再需要提供类的完整名称了。

```java
import java.time.*;
```

然后你就可以使用：

```java
LocalDate today = LocalDate.now();
```

而不需要包前缀。你也可以在包内导入特定的类：

```java
import java.time.LocalDate;
```

`java.time.*`语法不那么繁琐。它对代码大小没有产生负面影响。然而，如果你显式地导入类，代码的阅读者就能确切知道你使用了哪些类。

---

![Image](img/tip.jpg) **提示：**

在 Eclipse 中，你可以选择菜单选项`Source`（源）→`Organize Imports`（组织导入）。如`import java.util.*;`这样的包语句会自动展开为特定导入的列表，例如：

```java
import java.util.ArrayList;
import java.util.Date;
```

这是一个非常方便的功能。

---

然而，请注意，你只能使用`*`符号导入单个包。你不能使用`import java.*`或`import java.*.*`来导入所有以`java`为前缀的包。

大多数情况下，你只需要导入需要的包而不需要太担心它们。唯一需要注意包的时候是发生命名冲突时。例如，`java.util`和`java.sql`包都有一个`Date`类。假设你写了一个同时导入了这两个包的程序。

```java
import java.util.*;
import java.sql.*;
```

如果你现在使用`Date`类，将得到编译错误：

```java
Date today; // 错误--java.util.Date 还是 java.sql.Date?
```

编译器无法确定你想要哪一个`Date`类。你可以通过添加特定的`import`语句来解决这个问题：

```java
import java.util.*;
import java.sql.*;
import java.util.Date;
```

如果你真的需要两个`Date`类怎么办？那么在每个类名上都使用全包名：

```java
var startTime = new java.util.Date();
var today = new java.sql.Date(. . .);
```

在包中定位类是`compiler`的活动。类文件中的字节码始终使用全包名来引用其他类。

---

![Image](img/c.jpg) **C++ 注意：**

C++ 程序员有时会将`import`与`#include`混淆。两者之间没有任何共同点。在 C++ 中，你必须使用`#include`来包含外部特性的声明，因为 C++ 编译器不会查看除正在编译的文件及其显式包含的头文件之外的任何文件。只要你告诉 Java 编译器去哪里查找，它就会乐意查看其他文件。

在 Java 中，你可以通过显式地命名所有类（例如`java.util.Date`）来完全避免`import`机制。在 C++ 中，你无法避免`#include`指令。

`import`语句的唯一用处是方便。你可以用比全包名短的名字来引用类。例如，在执行`import java.util.*`（或`import java.util.Date`）语句后，你可以简单地用`Date`来引用`java.util.Date`类。

在 C++ 中，与包机制等同的构造是命名空间（namespace）功能。将 Java 中的`package`和`import`语句视为 C++ 中`namespace`和`using`指令的类比即可。

## 4.8.3 静态导入

一种`import`语句允许导入静态方法和字段，而不仅仅是类。

例如，如果你在源文件的顶部添加指令：

```java
import static java.lang.System.*;
```

那么你就可以在没有类名前缀的情况下使用`System`类的静态方法和字段：

```java
out.println("Goodbye, World!"); // 即 System.out

exit(0); // 即 System.exit
```

你也可以导入特定的方法或字段：

```java
import static java.lang.System.out;
```

在实践中，许多程序员似乎并不想要缩写`System.out`或`System.exit`。生成的代码看起来不那么清晰。另一方面，

```java
sqrt(pow(x, 2) + pow(y, 2))
```

看起来比：

```java
Math.sqrt(Math.pow(x, 2) + Math.pow(y, 2))
```

要清晰得多。

## 4.8.4 将类添加到包中

要将类放在包内，请将包名放在源文件的顶部，位于定义包内类的代码**之前**。例如，列表 4.8 中的`Employee.java`文件开头如下：

```java
package com.horstmann.corejava;

public class Employee
{
   . . .
}
```

如果你不在源文件中放置`package`语句，那么该源文件中的类属于匿名包（unnamed package）。匿名包没有包名。到目前，我们所有的示例类都位于匿名包中。

将源文件放在与全包名匹配的子目录下。例如，`com.horstmann.corejava`包中的所有源文件都应该位于`com/horstmann/corejava`（在 Windows 上为`com\horstmann\corejava`）子目录下。编译器会将类文件存放在相同的目录结构中。

列表 4.7 和 4.8 中的程序在两个包中：`PackageTest`类属于匿名包，而`Employee`类属于`com.horstmann.corejava`包。因此，`Employee.java`文件必须位于子目录`com/horstmann/corejava`中。换句话说，目录结构如下：

![Images](img/190fig01.jpg)

要编译此程序，只需切换到基础目录并运行命令：

```bash
javac PackageTest.java
```

编译器会自动找到文件`com/horstmann/corejava/Employee.java`并编译它。

让我们看一个更真实的例子，在其中我们不使用匿名包，而是将类分布在包中（`com.horstmann.corejava`和`com.mycompany`）。

![Images](img/191fig)

在这种情况下，你仍然从基础目录编译和运行——即`com`目录：

```bash
javac com/mycompany/PayrollApp.java
java com.mycompany.PayrollApp
```

再次注意，编译器操作的是文件（使用文件分隔符），而 Java 解释器加载的是类（使用点分隔符）。

---

![Image](img/tip.jpg) **提示：**

从下一章开始，我们将使用包。这样你就可以每个节创建一个 IDE 项目。

---

![Image](img/caution.jpg) **注意：**

编译器在编译源文件时并不检查目录结构。例如，假设你有一个开头为指令的文件：

```java
package com.mycompany;
```

即使它没有位于`com/mycompany`子目录下，你也可以编译它。但是，如果不将类文件移动到正确的位置，生成的程序将无法运行。

## 列表 4.7 `PackageTest.java`

```java
1 import com.horstmann.corejava.*;
2 // Employee 类定义在该包中
3
4 import static java.lang.*;
5
6 /**
7  * 此程序演示了包的使用。
8  * @version 1 2004-02-19
9  * @author Cay Horstmann
10 */
11 public class PackageTest
12 {
13   public static void main(String[] args)
14   {
15     // 因为由于导入语句，我们不需要在这里使用
16     // com.horstmann.corejava.Employee
17     var harry = new Employee("Harry Hacker", 50000, 1989, 10, 1);
18
19     harry.raiseSalary(5);
20
21     // 因为静态导入语句，我们不需要在这里使用 System.out
22     out.println("name=" + harry.getName() + ",salary=" + harry.getSalary());
23   }
24 }
```

## 列表 4.8 `PackageTest/com/horstmann/corejava/Employee.java`

```java
package com.horstmann.corejava;

// the classes in this file are part of this package

import java.time.*;

// import statements come after the package statement

/**
 * @version 1.11 2015-05-08
 * @author Cay Horstmann
 */
public class Employee
{
    private String name;
    private double salary;
    private LocalDate hireDay;

    public Employee(String name, double salary, int year, int month, int day)
    {
        this.name = name;
        this.salary = salary;
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
        double raise = salary * byPercent / 100;
        salary += raise;
    }
}
```

## 4.8.5 包访问

你已经遇到过访问修饰符`public`和`private`。标记为`public`的特征可以被任何类使用。`private`特征只能由定义它的类使用。如果你既没有指定`public`或`private`，该特征（即类、方法或变量）就可以被同一个`package`中的所有方法访问。

考虑列表 4.2 中的程序。`Employee`类没有被定义为`public`类。因此，只有同一个包（在这种情况下是未命名包）中的其他类（如`EmployeeTest`）可以访问它。对于类来说，这是一个合理的默认值。但对于变量来说，这是一个不幸的选择。变量必须显式地标记为`private`，否则它们将默认具有包访问权限。这无疑破坏了封装性。问题在于，忘记输入`private`关键字非常容易。这里是来自`java.awt`包中`Window`类的一个示例，它是 JDK 随附源代码的一部分：

```java
public class Window extends Container
{
   String warningString;
   . . .
}
```

注意`warningString`变量并不是`private`的！这意味着`java.awt`包中所有类的方法都可以访问此变量，并将其设置为它们喜欢的任何值（例如`"Trust me!"`）。实际上，访问此变量的方法只有`Window`类中的，因此将该变量设为`private`是完全合适的。也许程序员在急着写代码时只是忘记了`private`修饰符？也许根本不在意？二十多年后，该变量仍然不是`private`。不仅如此，随着时间的推移，该类添加了新字段，其中大约一半也不是`private`的。

![Figure 4.9](img/09.jpg)

**图 4.9 修改类路径**

## 4.8.6 类路径

正如你所看到的，`.`表示当前目录。从 1.2 版本开始，如果`.`目录在类路径上，`java`类加载器允许未定义的类。

类路径列出了所有作为查找类**起点**的目录和归档文件。让我们考虑我们的示例类路径：

```text
/home/user/classdir:.:/home/user/archives/archive.jar
```

假设虚拟机正在搜索`com.horstmann.corejava.Employee`类的文件。它首先在 Java API 类中查找。它在那里找不到该类文件，于是转向类路径。它接着查找以下文件：

- `/home/user/classdir/com/horstmann/corejava/Employee.class`
- `com/horstmann/corejava/Employee.class`，从当前目录开始
- `com/horstmann/corejava/Employee.class`，在`/home/user/archives/archive.jar`内部

编译器定位文件比虚拟机要困难。如果你在不指定包的情况下引用一个类，编译器首先需要找到包含该类的包。它查询所有的`import`指令作为类的可能来源。例如，假设源文件包含指令：

```java
import java.util.*;
import com.horstmann.corejava.*;
```

源代码中引用了一个名为`Employee`的类。编译器随后会尝试寻找`java.lang.Employee`（因为`java.lang`包始终是默认导入的）、`java.util.Employee`、`com.horstmann.corejava.Employee`以及当前包中的`Employee`。它会在类路径（class path）的所有位置搜索这些类中的**each**。如果发现了多个类，则会产生编译错误。（完全限定类名必须是唯一的，因此`import`语句的顺序并不重要。）

编译器更进了一步。它会查看`source files`以确定源代码是否比类文件新。如果是，则会自动重新编译源码。请记住，你只能从其他包导入公共类（public classes）。一个源文件只能包含一个公共类，且文件名与公共类名必须匹配。因此，编译器可以轻松地定位公共类的源文件。然而，你可以从当前包导入非公共类（nonpublic classes）。这些类可能定义在不同名的文件中。如果你从当前包导入一个类，编译器会搜索当前包的`all`源文件，以查看哪一个定义了该类。

## 4.8.7 设置类路径

最好使用`-classpath`选项（或`-cp`，从 Java 9 开始可以使用`--class-path`）来指定类路径：

```bash
java -classpath /home/user/classdir:.:/home/user/archives/archive.jar MyProg
```

或者：

```bash
java -classpath c:\classdir;.;c:\archives\archive.jar MyProg
```

整个命令必须在一行输入。将这样很长的命令行放在壳脚本或批处理文件中是一个好主意。

使用`-classpath`选项是设置类路径的首选方法。另一种方法是使用`CLASSPATH`环境变量。具体取决于你使用的 shell。对于 Bourne Again shell (bash)，使用命令：

```bash
export CLASSPATH=/home/user/classdir:.:/home/user/archives/archive.jar
```

对于 Windows shell，使用：

```bash
set CLASSPATH=c:\classdir;.;c:\archives\archive.jar
```

类路径的设置一直有效到 shell 退出。

![Image](img/caution.jpg) **CAUTION:**

有些人建议建议永久设置`CLASSPATH`环境变量。这通常是一个坏主意。人们会忘记这个全局设置，并在发现类没有被正确加载时感到惊讶。一个特别值得指责的例子是 Apple 在 Windows QuickTime 安装程序。多年来，它全局地将`CLASSPATH`指向它需要的 JAR 文件，但没有将当前目录包含在类路径中。结果导致无数 Java 程序员在程序编译成功但无法运行时感到抓狂。

![Image](img/caution.jpg) **CAUTION:**



在过去，有些人建议通过将所有 JAR 文件丢进`jre/lib/ext`目录来完全绕过类路径。这种机制在 Java 9 中已经过时，但它一直是一个糟糕的建议。当从扩展目录加载被遗忘已类时，很容易产生混淆。

![Image](img/note.jpg) **NOTE:**

从 Java 9 开始，类也可以从`module path`加载。模块（Modules）和模块路径在第二卷的第 9 章](#ch09.xhtml_ch9) 中进行了讨论。

## 4.9 JAR 文件

当你打包应用程序时，你希望给用户提供单个文件，而不是一个充满类文件的目录结构。Java 存档（JAR）文件正是为此目的设计的。JAR 文件可以包含类文件和其他文件类型，如图像和声音文件。此外，JAR 文件是压缩的，使用了熟悉的 ZIP 压缩格式。

### 4.9.1 创建 JAR 文件

使用`jar`工具制作 JAR 文件。（在默认 JDK 安装中，它位于`jdk/bin`目录下。）创建一个新 JAR 文件的常用命令使用以下语法：

```bash
jar cvf jarFileName file1 file2 . . .
```

例如：

```bash
jar cvf CalculatorClasses.jar *.class icon.gif
```

通常，`jar`命令具有以下格式：

```bash
jar options file1 file2 . . .
```

表 4.2 列出了`jar`程序的所有选项。它们类似于 UNIX`tar`命令的选项。

你可以将应用程序程序和代码库打包成 JAR 文件。例如，如果你想在 Java 程序中发送电子邮件，你会使用一个封装在`javax.mail.jar`文件中的库。

**表 4.2** `jar`程序选项

![Images](img/04tab02.jpg)

### 4.9.2 清单（Manifest）

除了类文件、图像和其他资源外，每个 JAR 文件还包含一个`manifest`文件，描述存档的特殊功能。

清单文件名为`MANIFEST.MF`，位于 JAR 文件中特殊的`META-INF`子目录下。最合法的清单非常无聊——只有：

```text
Manifest-Version: 1.0
```

复杂的清单可以有多许多条目。清单条目分为若干部分。清单中的第一部分称为`main section`（主部分），适用于整个 JAR 文件。随后的条目可以指定属性等。

### 4.9.3 可执行 JAR 文件

你可以使用`jar`命令的`e`选项来指定程序的`entry point`（入口点），即你在调用`java`程序启动器时通常指定的类：

```bash
jar cvfe MyProgram.jar com.mycompany.mypkg.MainClass files to add
```

或者，你可以在清单中指定程序的`main class`（主类），包含如下形式的语句：

```text
Main-Class: com.mycompany.mypkg.MainClass
```

不要在主类名后添加`.class`扩展。

![Image](img/caution.jpg) **CAUTION:**

清单的最后一行必须以换行符结束。否则，清单将无法正确读取。一个常见的错误是产生了一个包含`Main-Class`行但没有终止符的文本文件。

使用任一种方法，用户都可以简单启动程序：

```bash
java -jar MyProgram.jar
```

根据操作系统的配置，用户甚至可以通过双击 JAR 文件图标启动应用程序。以下是各种操作系统的行为：

- 在 Windows 上，Java 运行时安装程序为`.jar`扩展创建文件关联，使用`javaw -jar`命令启动该文件。（与`java`命令不同，`javaw`命令不会打开命令行窗口。）
- 在 Mac OS X 上，操作系统识别`.jar`文件扩展名，并在双击 JAR 文件时执行 Java 程序。

然而，位于 JAR 文件中的 Java 程序并没有像原生应用程序那样的体验。在 Windows 上，你可以使用第三方封装器工具（wrapper utilities）将 JAR 文件转换为 Windows 可执行文件。封装器是一个具有熟悉的`.exe`扩展名的 Windows 程序，它负责定位并启动 Java 虚拟机（JVM），或者在未找到 JVM 时提示用户该如何操作。目前有很多商用和开源产品，例如`Launch4J`（[`http://launch4j.sourceforge.net`](http://launch4j.sourceforge.net)）和`IzPack`（[`http://izpack.org`](http://izpack.org)）。

## 4.9.4 多版本发布 JAR 文件

随着模块的引入和对包的强封装，某些以前可以访问的内部 API 不再可用。这可能要求库提供者为不同的 Java 版本分发不同的代码。Java 9 引入了多版本发布 JAR（multi-release JARs）来实现这一目的。

为了后兼容，特定版本的类文件被放置在

![Images](img/201fig01.jpg)

假设`Application`类使用了`CssParser`类。那么旧版的`Application.class`文件可以编译为使用`com.sun.javafx.css.CssParser`，而 Java 9 版本则使用`javafx.css.CssParser`。

Java 8 完全不知道`META-INF/versions`目录，它只会加载旧版类。当 JAR 文件被 Java 9 读取时，将使用新版本。

要添加带版本的类文件，使用`--release`标志：

```bash
jar uf MyProgram.jar --release 9 Application.class
```

要从头构建多版本发布 JAR 文件，使用`-C`选项并为每个版本切换不同的类文件目录：

```bash
jar cf MyProgram.jar -C bin/8 . --release 9 -C bin/9 Application.class
```

在为不同的发布编译时，使用`--release`标志和`-d`标志来指定输出目录：

```bash
javac -d bin/8 --release 8 . . .
```

从 Java 9 开始，`-d`选项会在目录不存在时创建它。

`--release`标志也是 Java 9 引入的新特性。在旧版本中，你需要使用`-source`、`-target`和`-bootclasspath`标志。JDK 现在附带了两个之前版本 API 的符号文件。在 Java 9 中，你可以将`--release`设置为`9`、`8`或`7`进行编译。

多版本发布 JAR 并不是用于程序或库的不同版本。所有类的公共 API 在两个版本中应该是相同的。多版本发布 JAR 的唯一目的是让你的程序或库的特定版本能够兼容多个 JDK 版本。如果你添加了功能或更改了 API，你应该提供 JAR 的新版本而不是。

![Image](img/note.jpg) **注意：**

诸如`javap`等工具并没有经过重构来处理多版本发布 JAR 文件。如果你调用：

```bash
javap -classpath MyProgram.jar Application.class
```

你将得到该类的基础版本（毕竟，它本应该与新版本具有相同的公共 API）。如果你必须查看新版本，请调用：

```bash
javap -classpath MyProgram.jar!/META-INF/versions/9/Application.class
```

## 4.9.5 关于命令行选项的说明

Java 开发工具包（JDK）中命令的选项传统上使用单个横杠后跟多个字母的名称，例如：

```bash
java -jar . . .

javac -Xlint:unchecked -classpath . . .
```

例外是`jar`命令，它遵循`tar`命令的经典选项格式，不带横杠：

```bash
jar cvf . . .
```

从 Java 9 开始，Java 工具正在向更常见的选项格式转变，即多个字母的选项以双横杠开头，常用选项有单字母快捷方式。例如，Linux 的`ls`命令可以使用“人类可读”选项调用：

```bash
ls --human-readable
```

或：

```bash
ls -h
```

从 Java 9 开始，你可以用`--version`代替`-version`，用`--class-path`代替`-classpath`。正如你在第二卷第 9 章中看到的，`--module-path`选项有一个快捷方式`-p`。

你可以在 JEP 293 增强请求中找到细节，[`http://openjdk.java.net/jeps/293`](http://openjdk.java.net/jeps/293)。作为此次清理工作的一部分，作者还提议标准化选项参数。带有`--`和多个字母的选项的参数通过空格或`=`隔开：

```bash
javac --class-path /home/user/classdir . . .
```

或：

```bash
javac --class-path=/home/user/classdir . . .
```

单字母选项的参数可以使用空格分隔，也可以直接紧跟在选项后面：

```bash
javac -p moduledir . . .
```

或：

```bash
javac -pmoduledir . . .
```

![Image](img/caution.jpg) **注意：**

后者目前不起，而且通常来说这似乎是个坏主意。如果模块目录恰好是`arameters`或`rocessor`，为什么要引入与旧版选项的冲突呢？

不带参数的单字母选项可以组合在一起：

```bash
jar -cvf MyProgram.jar -e mypackage.MyProgram */*.class
```

![Image](img/caution.jpg) **注意：**

这目前不起，而且注定会导致混惑。假设`javac`获得了一个`-c`选项。那么`javac -cp`是指`javac -c -p`，还是旧的`-cp`优先级更高？

这造成了一个混乱局面，希望随着时间的推移得到清理。尽管我很想摆弃过时的`jar`选项，但看起来最好的办法是等尘埃落定。但如果你想彻底现代化，可以安全地使用`jar`命令的长选项：

```bash
jar --create --verbose --file jarFileName file1 file2 . . .
```

如果你不对单字母选项进行分组，它们也同样有效：

```bash
jar -c -v -f jarFileName file1 file2 . . .
```

## 4.10 文档注释

JDK 包含一个非常有用的工具，称为`javadoc`，它可以从你的源文件生成 HTML 文档。事实上，第 3 章中描述的在线 API 仅仅是在标准库上运行`javadoc`的结果。

如果你在源代码中添加以特殊分隔符`/**`开头的注释，你也可以轻松制作专业的文档。这是一个非常好的方法，因为它让你将代码和文档放在一起。如果你将文档放在单独的文件中，正如你所知，代码和注释往往随着时间产生偏差。当文档注释与源码在一起时，更新两者并再次运行`javadoc`很容易。

### 4.10.1 注释插入

`javadoc`工具提取以下项目的信息：

- 模块
- 包
- 公有类和接口
- 公有和保护字段
- 公有和保护构造函数和方法

保护功能出现在第 5 章](#ch05.xhtml_ch5)，接口出现在第 6 章](#ch06.xhtml_ch6)，模块出现在第二卷的第 9 章](#ch09.xhtml_ch9)。

你可以为这些功能提供注释。每个注释都放在描述的功能的正上方。注释以`/**`开始并以`*/`结束。

如果你的注释中包含指向其他文件的链接（例如图表或用户界面组件图像），请将这些文件放在源文件所在目录的名为`doc-files`的子目录中。`javadoc`工具会将从源目录的`doc-files`目录及其内容复制到文档目录。你需要在链接中使用`doc-files`目录，例如`<img src="doc-files/uml.png" alt="UML 图"/>`。

### 4.10.2 类注释

类注释必须放置在任何`import`语句**之后**，直接置于`class`定义之前。

以下是一个类注释的示例：

```java
/**
 * 一个 {@code Card} 对象表示一张扑牌，例如
 * "红心 Q"。一张扑牌有一个花色（方块、红心、
 * 黑桃牌或梅花）和一个值（1 = A, 2 . . . 10, 11 = J,
 * 12 = Q, 13 = K）
 */

public class Card
{
   . . .
}
```

![Image](img/note.jpg) **注意：**

没有必要在每行前面添加`*`。例如，以下注释也是同样有效的：

```java
/**
   一个 <code>Card</code> 对象表示一张扑牌，例如
   如 "红心 Q"。一张扑牌有一个花色（方块、红心、
   黑桃牌或梅花）和一个值（1 = A, 2 . . . 10, 11 = J,
   12 = Q, 13 = K）。
*/
```

然而，大多数 IDE 会自动提供星号，并在换行发生变化时重新排列它们。

### 4.10.3 方法注释

每个方法注释必须紧接在其所描述的方法之前。除了通用标签外，你还可以使用以下标签：

- `@param` *变量描述*

  此标签为当前方法的“参数”部分添加一个条目。描述可以跨多行，并可以使用 HTML 标签。一个方法的所有`@param`标签必须保持在一起。

- `@return` *描述*

  此标签为当前方法添加一个“返回值”部分。描述可以跨多行，并可以使用 HTML 标签。

- `@throws` *类描述*

  此标签添加一个该方法可能会抛出异常的说明。异常是第 7 章的主题。

这是一个方法注释的示例：

```java
/**
 * 增加员工的工资。
 * @param byPercent 增加工资的百分比（例如，10 意味着 10%）
 * @return 增加的金额
 */

public double raiseSalary(double byPercent)
{
   double raise = salary * byPercent / 100;
   salary += raise;
   return raise;
}
```

### 4.10.4 字段注释

你只需要记录公共字段——通常意味着静态常量。例如：

```java
/**
 * “红心”花色
 */
public static final int HEARTS = 1;
```

### 4.10.5 通用注释

标签`@since` *文本*会创建一个“自某版本起”条目。*文本*可以是引入此特性的任何描述。例如，`@since 1.7.1`。

以下标签可以在类文档注释中使用：

- `@author` *姓名*

  此标签创建一个“作者”条目。你可以有多个`@author`标签，每个作者一个。不必强迫自己使用此标签——你的版本控制系统在跟踪作者身份方面做得更彻底。

- `@version` *文本*

  此标签创建一个“版本”条目。`text`可以是对当前版本的任何描述。

你可以使用`@see`和`@link`标签使用指向`javadoc`文档其他相关部分或外部文档的超链接。

标签`@see` *引用*在“另参见”部分添加一个超链接。它可以同时用于类和方法。在这里，*引用*可以是以下内容之一：

```text
package.class#feature label

<a href=". . .">label</a>

"text"
```

第一种情况是最实用的。你提供类、方法或变量名，`javadoc`会插入一个指向文档的超链接。例如：

```text
@see com.horstmann.corejava.Employee#raiseSalary(double)
```

这会创建一个指向`com.horstmann.corejava.Employee`类中`raiseSalary(double)`方法的链接。你可以省略包名，或者同时省略包名和类名。这时，特性将在当前包或类中查找。注意，你必须使用`#`而不是点号来分隔类与方法或变量名。Java 编译器本身非常擅长确定点号作为包、子包、类、内部类以及方法和变量之间分隔符的含义。但`javadoc`工具并不那么聪明，所以你必须帮助它。

如果`@see`标签后面跟着`<`字符，那么你需要指定一个超链接。你可以链接到任何喜欢的 URL。例如：

```html
@see <a href="www.horstmann.com/corejava.html">Core Java 首页</a>
```

在这些的每种情况下，你都可以指定一个可选的*标签*作为链接锚点显示。如果你省略了标签，用户将看到目标代码名或 URL 作为锚点。

如果`@see`标签后面跟着`"`字符，则文本将显示在“另参见”部分。例如：

```text
@see "Core Java 2 volume 2"
```

你可以为一个特性添加多个`@see`标签，但你必须将它们保持在一起。

如果你愿意，可以在任何文档注释的任何位置放置指向其他类或方法的超链接。在注释中的任何位置插入如下形式的特殊标签：

```text
{@link package.class#feature label}
```

特性描述遵循与`@see`标签相同的规则。

最后，从 Java 9 开始，你可以使用`{@index` *条目*`}`标签向搜索框添加条目。

### 4.10.6 包注释



将类、方法和变量注释直接放入源文件中，并用`/** . . */`文档注释分隔。然而，要生成包注释，你需要在每个包目录中添加一个单独的文件。你有两个选择：

1. 提供一个名为`package-info.java`的 Java 文件。该文件必须包含一个初始 Javadoc 注释（用`/**`和`*/`分隔），随后跟一个`package`语句。它不应包含进一步的代码。
2. 提供一个名为`package.html`的 HTML 文件。标签`<body> . .</body>`之间的所有文本将被提取。

#### 4.10.7 注释提取

在这里，`docDirectory`是你希望存放 HTML 文件的目录名称。按照以下步骤操作：

1. 切换到要记录的源文件的目录。如果你有嵌套的包需要记录，例如`com.horstmann.corejava`，你必须在包含`com`的目录中运行。（如果你提供了`overview.html`文件，则就是包含该文件的目录。）

2. 针对单个包，运行命令：

```bash
javadoc -d docDirectory nameOfPackage
```

或者，运行以下命令记录多个包：

```bash
javadoc -d docDirectory nameOfPackage1 nameOfPackage2 . .
```

如果你的文件在无名包中，请改运行：

```bash
javadoc -d docDirectory *.java
```

如果你省略了`-d docDirectory`选项，HTML 文件将提取到当前目录。这可能会变得很杂乱，我不建议这样做。

`javadoc`程序可以通过许多命令行选项进行精细调整。例如，你可以使用`-author`和`-version`选项在文档中包含`@author`和`@version`标签。（默认情况下，它们会被省略。）另一个实用的选项是`-link`，用于指向标准类的超链接。例如，如果你使用命令：

```bash
javadoc -link http://docs.oracle.com/javase/9/docs/api *.java
```

所有标准库类都会自动链接到 Oracle 网站上的文档。

如果你使用`-linksource`选项，每个源文件将转换为 HTML（没有颜色标记，但有行号），并且每个类和方法名将变为指向源代码的超链接。

你还可以为所有源文件提供一个概述注释。将其放置在如`overview.html`等文件中，并使用命令行选项`-overview filename`运行`javadoc`工具。`<<body>>. . .</</body>>`标签之间的所有文本都会被提取。当用户从导航栏选择“Overview”（概述）时，将显示这些内容。

有关更多选项，请参阅`javadoc`实用程序的在线文档：[`https://docs.oracle.com/javase/9/javadoc/javadoc.htm`](https://docs.oracle.com/javase/9/javadoc/javadoc.htm)。

### 4.11 类设计提示

在不力求全面或详尽的前提下，我想用一些提示结束本章，这些提示将使你的类在良好的面向对象（OOP）圈中更受认可。

1. **始终保持数据私有。**

这是首要任务；否则执行任何其他操作都会违反封装。你可能偶尔需要编写访问器方法（accessor）或修改器方法（mutator），但将实例字段保持为私有仍然更好。惨痛的经验表明，数据的表示可能会发生变化，但这些数据的使用方式变化频率要低得多。当数据保持私有时，其表示的变化不会影响类的使用者，且更容易检测到错误。

2. **始终初始化数据。**

Java 不会为你初始化局部变量，但它会初始化对象的实例字段。不要依赖默认值，而是显式地初始化所有变量，通过提供默认值或在所有构造函数中设置默认值来实现。

3. **不要在类中使用过多的基本类型。**

其思想是将基本类型的多次相关使用替换为其他类。这使得你的类更容易被理解和修改。例如，将`Customer`类中的以下实例字段：

```java
private String street;
private String city;
private String state;
private int zip;
```

替换为一个名为`Address`的新类。这样，你就可以轻松处理地址的变化，例如处理国际地址的需求。

4. **并非所有字段都需要单独的字段访问器和修改器。**

你可能需要获取和设置员工的薪水。但一旦对象构造完成，你显然不需要更改入职日期。而且，对象经常拥有你不希望他人获取或设置的实例字段，例如`Address`类中存储州缩写的数组。

5. **拆分职责过多的类。**

这个提示当然是模糊的：“过多”显然取决于观察者的主观判断。然而，如果有一种明显的方法可以将一个复杂的类拆分为两个概念上更简单的类，请抓住这个机会。（另一方面，不要做得过头；十个类、每个类只有一个方法，通常是大材小用了。）

这里有一个糟糕设计的示例：

```java
public class CardDeck // 糟糕的设计
{
   private int[] value;
   private int[] suit;
   public CardDeck() { . . . }
   public void shuffle() { . . . }
   public int getTopValue() { . . . }
   public int getTopSuit() { . . . }
   public void draw() { . . . }
}
```

这个类实际上实现了两个独立的概念：带有`shuffle`和`draw`方法的牌牌，以及具有检查其值和花色方法的单牌。引入一个代表单个牌的`Card`类是有意义的。现在你有两个类，每个类都有自己的职责：

```java
public class CardDeck
{
   private Card[] cards;
   public CardDeck() { . . . }
   public void shuffle() { . . . }
   public Card getTop() { . . . }
   public void draw() { . . . }
}

public class Card
{
   private int value;
   private int suit;
   public Card(int aValue, int aSuit) { . . . }
   public int getValue() { . . . }
   public int getSuit() { . . . }
}
```

6. **让类和方法的名称反映它们的职责。**

正如变量应该具有反映其含义的有意义名称一样，类也应该如此。（标准库确实包含一些可疑的例子，例如描述时间的`Date`类。）

一个良好的约定是类名应该是名词（`Order`），或者由形容词修饰的名词（`RushOrder`）或动名词（以“-ing”结尾的词，如`BillingAddress`）。对于方法，遵循标准约定：访问器方法以小写的`get`开头（`getSalary`），修改器方法使用小写的`set`（`setSalary`）。

7. **偏好使用不可变类。**

`LocalDate`类以及`java.time`包中的其他类都是不可变的——没有方法可以修改对象的状态。与其修改对象，像`plusDays`这样的方法会返回一个带有修改状态的新对象。

修改的问题在于，当多个线程尝试同时更新对象时可能会并发发生。结果是不可预测的。当类是不可变的，在多个线程之间共享它们的对象是安全的。

因此，尽可能将类设为不可变是一个好主意。对于表示值的类（例如字符串或时间点），这尤其容易实现。

当然，并不是所有类都应该是不可变的。如果当员工加薪时让`raiseSalary`方法返回一个新的`Employee`对象，那将很奇怪。

在本章中，我们涵盖了使 Java 成为“基于对象”语言的类和基础。为了真正面向对象，语言必须支持继承和多态。Java 对这些特性的支持是下一章的主题。

## 第 5 章：继承

### 在本章中

- 5.1 类、超类和子类
- 5.2 `Object`：宇宙超类
- 5.3 泛型数组
- 5.4 包装类和自动装箱
- 5.5 变长参数方法
- 5.6 抽象类
- 5.7 枚举类
- 5.8 密封类
- 5.9 反射
- 5.10 继承的设计提示

第 4 章向你介绍了类和对象。在本章中，你将学习继承，面向对象编程的另一个核心概念。继承的核心思想是你可以基于现有类创建新类。当你从现有类继承时，你重用了（或继承了）它的方法，并可以添加新方法和字段以使新类适应新情况。这种技术在 Java 编程中至关重要。

本章还涵盖了反射，即在运行程序中发现有关类及其属性的能力。反射是一个强大的特性，但不可否认地复杂。由于反射对工具开发者比应用程序开发者更感兴趣，你第一次阅读本章时可以快速略过这部分，以后来看。

让我们回到上一章中讨论的`Employee`类。假设（不幸的是）你供职的一家公司里，经理受到的待遇与其他员工不同。当然，经理在许多方面与员工是一致的。员工和经理都领取薪水。然而，员工被要求完成分配的任务以换取薪水，而经理如果真的实现了他们应该做的工作，就能获得奖金。这种情况正需要通过继承来大显身手。为什么呢？嗯，你需要定义一个新类`Manager`并添加一些功能。但你可以保留一些已经在`Employee`类中编写好的代码，并且原类的所有字段都可以被保留。从更抽象的角度来看，`Manager`和`Employee`之间存在着显而易见的“是（is–a）”关系。每个经理都是一个员工：这种“是（is–a）”关系是继承的典型特征。

***

![Image](img/note.jpg) **注意：**

在本章中，我使用了员工和经理的经典例子，但我必须要求你对这个例子保持保留。在现实世界中，员工可以变成经理，因此你可能希望将经理建模为员工的一种角色，而不是一个子类。但在我的例子中，我假设企业世界中只有两种人：一类人是永远的员工，另一类人一直是经理。

***

### 5.1.1 定义子类

以下是如何定义继承自`Employee`类的`Manager`类。使用 Java 关键字`extends`来表示继承。

```java
public class Manager extends Employee
{
   added methods and fields
}
```

***

![Image](img/c.jpg) **C++ 注意：**

继承在 Java 和 C++ 中是相似的。Java 使用`extends`关键字而不是`:`符号。Java 中的所有继承都是公共继承；没有对应于 C++ 中私有（private）和受保护（protected）继承的功能。

***

关键字`extends`表示你正在创建一个派生自现有类的新类。现有类被称为超类（superclass）、基类（base class）或父类（parent class）。新类被称为子类（subclass）、派生类（derived class）或子类（child class）。超类和子类这两个术语是 Java 程序员最常用的，尽管有些程序员更倾向于父/子类的类比，这与“继承”主题也结合得非常完美。

`Employee`类是一个超类，但并不是因为它优于它的子类或包含了更多功能。事实上，事实恰恰相反：子类的功能比其超类更多。例如，当我们查看`Manager`类的其余代码时，你会发现`Manager`类封装了更多数据，功能也比它的超类`Employee`多。

***

![Image](img/note.jpg) **注意：**

前缀*super*（超）和*sub*（子）来源于理论计算机科学和数学中的集合语言。所有员工的集合包含了所有经理的集合，因此被认为是经理集合的超集（superset）。或者换句话说，所有经理的集合是所有员工集合的子集（subset）。

***

我们的`Manager`类有一个新字段来存储奖金，还有一个新方法来设置它：

```java
public class Manager extends Employee
{
   private double bonus;
   . . .
   public void setBonus(double bonus)
   {
      this.bonus = bonus;
   }
}
```

这些方法和字段并没有特殊之处。如果你有一个`Manager`对象，你可以简单地调用`setBonus`方法。

```java
Manager boss = . . .;
boss.setBonus(5000);
```

当然，如果你有一个`Employee`对象，你就无法调用`setBonus`方法——它不在`Employee`类定义的方法列表中。

然而，你可以在`Manager`对象上使用如`getName`和`getHireDay`等方法。尽管这些方法没有在`Manager`类中显式定义，但它们自动继承自`Employee`超类。

每个`Manager`对象都有四个字段：`name`、`salary`、`hireDay`和`bonus`。字段`name`、`salary`和`hireDay`是取自超类的。

***

![Image](img/note.jpg) **注意：**

Java 语言规范规定：“声明为私有（private）的类成员不会被该类的子类继承。”多年来，这一直困扰着我的读者。规范对“继承”一词的使用非常狭隘。它将私有字段视为非继承，因为`Manager`类无法直接访问它们。因此，每个`Manager`对象拥有三个来自超类的字段，但`Manager`类并没有“继承”它们。

***

当通过扩展超类来定义子类时，你只需要指出子类和超类之间的差异。在设计类时，你将通用的方法放在超类中，将更专门的方法放在子类中。通过将共同功能移动到超类来提取出来是面向对象编程的常规操作。

***

![Image](img/note.jpg) **注意：**

在第 4 章中，你学习了继承：你需要指示你想要调用超类。

***

### 5.1.2 方法重写

超类中的某些方法并不适用于`Manager`子类。特别是，`getSalary`方法应该返回`salary`和`bonus`的和。

```java
public class Manager extends Employee
{
   . . .
   public double getSalary()
   {
      . . .
   }
}
```

如何实现这个方法？乍看之下，这似乎很简单——直接返回`salary`和`bonus`之和：

```java
public double getSalary()
{
   return salary + bonus; // 不工作
}
```

然而，这并不通。回想起来，只有`Employee`方法可以直接访问私有字段。这意味着`Manager`类无法直接访问`salary`字段。所以，再次尝试。使用公共接口：

```java
public double getSalary()
{
   return getSalary() + bonus; // 不工作
}
```

现在的问题是`getSalary`的调用只是调用了自己，因为`Manager`类有一个`getSalary`方法（即我们正在尝试实现的这个方法）。结果是对同一个方法的无限调用，导致程序崩溃。

我们需要指示要调用`Employee`超类的`getSalary`方法，而不是当前类。使用特殊关键字`super`来实现此目的。调用：

```java
super.getSalary()
```

调用的是`Employee`类的`getSalary`方法。这是`Manager`类`getSalary`方法的正确版本：

```java
public double getSalary()
{
   double baseSalary = super.getSalary();
   return baseSalary + bonus;
}
```

***

![Image](img/note.jpg) **注意：**

有些人认为`super`类比于`this`引用。然而，这种类比并不准确：`super`并不是指向对象的引用。例如，你不能将`super`值赋值给另一个对象变量。相反，`super`是一个引导编译器调用类方法的特殊关键字。

***

正如你所见，子类可以添加字段，它也可以添加方法或重写超类的方法。然而，继承永远无法剥夺任何字段或方法。

Java 使用关键字`super`来调用父类方法。在 C++ 中，你将使用父类的名称配合`::`运算符来代替。例如，`Manager`类的`getSalary`方法将调用`Employee::getSalary`而不是`super.getSalary`。

### 5.1.3 子类构造函数

为了完成我们的示例，让我们提供一个构造函数。

```java
public Manager(String name, double salary, int year, int month, int day)
{
   super(name, salary, year, month, day);
   bonus = 0;
}
```

在这里，关键字`super`具有不同的含义。这条指令：

```java
super(name, salary, year, month, day);
```

是“调用`Employee`父类的构造函数，并将`name`、`salary`、`year`、`month`和`day`作为参数”的简写。



由于`Manager`构造函数无法访问`Employee`类的私有字段，它必须通过构造函数初始化它们。构造函数通过特殊的`super`语法被调用。使用`super`的调用必须是子类构造函数中的第一条语句。

当在构造子类对象时不显式调用父类构造函数时，父类必须有一个无参数构造函数。该构造函数会在子类构造之前被调用。

![Image](img/note.jpg) **注意：**

回想`this`关键字有两个含义：表示对隐式参数的引用，以及调用同一类的另一个构造函数。同样，`super`关键字也有两个含义：调用父类方法和调用父类构造函数。当用于调用构造函数时，`this`和`super`关键字密切相关。构造函数调用只能作为另一个构造函数的第一条语句。构造函数参数要么传递给同一类的另一个构造函数（`this`），要么传递给父类的构造函数（`super`）。

![Image](img/c.jpg) **C++ 注意：**

在 C++ 构造函数并不调用`super`，而是使用初始化列表语法来构造父类。`Manager`构造函数在 C++ 中看起来如下：

```cpp
// C++
Manager::Manager(String name, double salary, int year, int month, int day)
: Employee(name, salary, year, month, day)
{
   bonus = 0;
}
```

在你重新定义`Manager`对象的`getSalary`方法后，经理的工资将自动加上奖金。

这里有一个此工作原理的示例。我们创建一个新经理并设置经理的奖金：

```java
Manager boss = new Manager("Carl Cracker", 80000, 1987, 12, 15);
boss.setBonus(5000);
```

我们创建一个包含三个员工的数组：

```java
var staff = new Employee[3];
```

我们用混合的经理和员工填充数组：

```java
staff[0] = boss;
staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);
```

我们打印每个人的工资：

```java
for (Employee e : staff)
   System.out.println(e.getName() + " " + e.getSalary());
```

此循环打印出以下数据：

```
Carl Cracker 85000.0
Harry Hacker 50000.0
Tommy Tester 40000.0
```

现在`staff[1]`和`staff[2]`分别打印它们的基本工资，因为它们是`Employee`对象。然而，`staff[0]`是一个`Manager`对象，其`getSalary`方法将奖金加上基本工资。

令人惊讶的是，调用

```java
e.getSalary()
```

选出了正确的`getSalary`方法。注意`e`的声明类型是`Employee`，但`e`所引用对象的实际类型可以是`Employee`也可以是`Manager`。

当`e`指向一个`Employee`对象时，调用`e.getSalary()`调用`Employee`类的`getSalary`方法。然而，当`e`指向一个`Manager`对象时，则调用`Manager`类的`getSalary`方法。虚拟机知道`e`所引用对象的实际类型，因此可以调用正确的方法。

对象变量（如变量`e`）可以引用多个实际类型这一被称为多态。在运行时自动选择合适的方法被称为动态绑定。我将在本章中详细详细讨论这两个主题。

![Image](img/c.jpg) **C++ 注意：**

在 C++ 中，如果你想实现动态绑定，需要将成员函数声明为`virtual`。在 Java 中，动态绑定是默认行为；如果你不想让一个方法是虚的，可以将其标记为`final`。（我将在本章稍后讨论`final`关键字。）

[Listing 5.1]包含一个显示`Employee`和`Manager`工资差异的程序。

**Listing 5.1** `inheritance/ManagerTest.java`

```java
package inheritance;

/**
 * 此程序演示了继承。
 * @version 1.2 2004-02-1
 * @author Caymann
 */
public class ManagerTest
{
   public static void main(String[] args)
   {
      // construct a object
      Manager boss = new Manager("Carl Cracker", 80000, 1987, 12, 15);
      boss.setBonus(5000);

      // make an array of three employees
      var staff = new Employee[3];

      // fill array with managers and employees
      staff[0] = boss;
      staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
      staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);

      // print out everyone's salary
      for (Employee e : staff)
         System.out.println(e.getName() + " " + e.getSalary());
   }
}
```

**Listing 5.2** `inheritance/Employee.java`

```java
package inheritance;

import java.time.*;

public class Employee
{
   private String name;
   private double salary;
   private LocalDate hireDay;

   public Employee(String name, double salary, int year, int month, int day)
   {
      this.name = name;
      this.salary = salary;
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
      double raise = salary * byPercent / 100;
      salary += raise;
   }
}
```

**Listing 5.3** `inheritance/Manager.java`

```java
package inheritance;

public class Manager extends Employee
{
   private double bonus;

   /**
    * @param name the employee's
    * @param salary the salary
    * @param year the hire year
    * @param month the hire month
    * @param day the hire day
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
}
```

### 5.1.4 继承层次结构

继承并不止于派生一层类。例如，我们可以有一个继承自`Manager`的`Executive`类。扩展共同父类的所有类的集合被称为*继承层次结构*，如图 5.1 所示。从某个特定类到其在继承层次结构中祖先类的路径是其*继承链*。

通常，从一个远远的祖类会有多条下降链。你可以创建扩展`Employee`的子类`Programmer`（程序员）或`Secretary`（秘书），它们与`Manager`类（或它们彼此）无关。这个过程可以根据需要一直持续。

![Images](img/05fig01.jpg)

**图 5.1** 员工继承层次结构

***

![Image](img/c.jpg) **C++ 注意：**

在 C++ 中，一个类可以有多个父类。Java 不支持多继承。关于恢复多继承的大部分功能的方法，请参见第 6.1 节，第 312 页的“接口”。

***

### 5.1.5 多态

一个简单的规则可以帮助你判断继承是否是你数据的正确设计。“是一个...”规则（is–a rule）规定，子类的每个对象都是父类的对象。例如，每个经理都是员工。因此，让`Manager`类成为`Employee`类的子类是合理的。自然，反过来则不成立——并不是每个员工都是经理。

制定“是一个...”规则的另一种方式是`替换原则`（substitution principle）。该原则规定，当程序期望父类对象时，你可以使用子类对象。

例如，你可以将子类对象赋值给父类变量。

```java
Employee e;

e = new Employee(. . .);  // 期望 Employee 对象

e = new Manager(. . .); // 确，也可以使用 Manager
```

在 Java 编程语言中，对象变量是`多态的`（polymorphic）。类型为`Employee`的变量可以指向`Employee`类型的对象，也可以指向`Employee`类的任何子类的对象（例如`Manager`、`Executive`、`Secretary`等）。

我们在列表 5.1 中利用了这一原则：

```java
Manager boss = new Manager(. . .);

Employee[] staff = new Employee[3];

staff[0] = boss;
```

在这种情况下，变量`staff[0]`和`boss`指向同一个对象。然而，编译器认为`staff[0]`仅仅是一个`Employee`对象。

这意味着你可以调用：

```java
boss.setBonus(5000); // 确
```

但你不能调用：

```java
staff[0].setBonus(5000); // 错误
```

`staff[0]`的声明类型是`Employee`，而`setBonus`方法并不是`Employee`类的方法。

然而，你不能将父类引用赋值给子类变量。例如，进行以下赋值是非法的：

```java
Manager m = staff[i]; // 错误
```

原因明显：并不是所有员工都是经理。如果此赋值成功且`m`指向一个不是经理的`Employee`对象，那么将来就可以调用`m.setBonus(. . .)`并导致运行时错误。

***

![Image](img/caution.jpg) **注意：**

在 Java 中，子类引用数组可以在不进行强制转换的情况下转换为父类引用数组。例如，考虑这个经理数组：

```java
Manager[] managers = new Manager[10];
```

将此数组转换为`Employee[]`数组是合法的：

```java
Employee[] staff = managers; // 确
```

当然，你可能会想，为什么不呢。毕竟，如果`managers[i]`是一个`Manager`，它也是一个`Employee`。但实际上，一些惊讶的事情正在发生。请记住`managers`和`staff`指向同一个数组。现在考虑以下语句：

```java
staff[0] = new Employee("Harry Hacker", . . .);
```

编译器会愉快地允许这次赋值。但`staff[0]`和`managers[0]`是同一个引用，所以看起来我们成功地将一个普通的员工“偷带”进了管理层。这将非常糟糕——调用`managers[0].setBonus(1000)`将尝试访问一个不存在的实例字段并损坏相邻内存。

为了确保不会发生此类损坏，所有数组都会记住它们创建时的元素类型，并监控只将兼容的引用存储到其中。例如，创建为`new Manager[10]`的数组会记得它是一个经理数组。尝试存储`Employee`引用将导致`ArrayStoreException`。

***

### 5.1.6 理解方法调用

确切理解方法调用是如何应用于对象的是非常重要的。假设我们调用`x.f(args)`，且隐式参数`x`被声明为类`C`的对象。发生了以下情况：

1. 编译器查看对象的声明类型和方法名。注意，可能多个方法都具有相同的名字`f`，但参数类型不同。例如，可能有一个方法`f(int)`和一个方法`f(String)`。编译器列出类`C`中所有名为`f`的方法，以及`C`的父类中所有可访问的名为`f`方法。（父类的私有方法是不可见的。）

   现在编译器知道了要调用方法的所有可能候选者。

2. 接下来，编译器确定方法调用中提供的参数的类型。如果在所有名为`f`的方法中，有一个方法的参数类型与提供的参数最匹配，则选择该方法。这一过程被称为重载解析。例如，在`x.f("Hello")`中，编译器选择了`f(String)`而不是`f(int)`。由于类型转换，情况可能会变得复杂（`int`到`double`、`Manager`到`Employee`等）。如果编译器在应用转换后找不到匹配的方法，或者多个方法都匹配，编译器将报告错误。

   现在编译器知道了要调用的方法名称和参数类型。

***

![Image](img/note.jpg) **注意：**

记住，方法的名称和类型列表被称为方法的`签名`（signature）。例如，`f(int)`和`f(String)`是同名但签名不同的方法。如果你在子类中定义了一个与父类方法相同的方法，你就覆盖了父类方法。

返回类型不是签名的一部分。然而，当你覆盖方法时，你需要保持返回类型兼容。子类可以更改返回类型。例如，假设`Employee`类有一个方法：

```java
public getBuddy() { . . . }
```

经理永远不会希望有一个普通的员工作为伙伴。为了反映这一事实，`Manager`子类可以覆盖此方法：

```java
public Manager getBuddy() { . . . } // 更改返回类型允许的
```

我们说这两个`getBuddy`方法具有协变返回类型。

3. 如果方法是`private`、`static`、`final`或构造函数，那么编译器确切知道调用哪个方法。（`final`修饰将在将在节解释）。这被称为静态绑定。否则，要调用的方法取决于隐式参数的实际类型，必须在运行时使用动态绑定。在我们的示例中，编译器将生成一条动态绑定调用`f(String)`的指令。

4. 当程序运行并使用动态绑定调用方法时，虚拟机必须调用适用于`x`所指对象的实际类型的方法。假设实际类型是`D`，它是`C`的子类。如果类`D`定义了方法`f(String)`，则调用该方法。如果没有，则搜索`D`的父类寻找`f(String)`。

每次调用方法都执行这种搜索将是非常耗时的。相反，虚拟机为每个类预计算一个`方法表`（method table）。方法表列出了所有方法签名和实际调用的方法。

虚拟机可以在加载类后，通过将从类文件中找到的方法与父类的方法表相结合来构建方法表。

当一个方法被实际调用时，虚拟机简单地执行一次表查找。在我们的示例中，虚拟机查询类`D`的方法表，并查找要调用的`f(String)`方法。该方法可能是`D.f(String)`或`X.f(String)`，其中`X`是`D`的某个父类。

在这种情况场景中有一个特殊之处。如果调用是`super.f(param)`，那么虚拟机会查询父类的方法表。

让我们详细查看 Listing 5.1 中调用`e.getSalary()`这一过程。`e`的声明类型是`Employee`。`Employee`类有一个方法，名为`getSalary`，且没有方法参数。因此，在这种情况下，我们不需要担心重载解析问题。



`getSalary()` 方法既不是 `private`、`static` 也不是 `final`，所以它是动态绑定的。虚拟机为 `Employee` 类和 `Manager` 类生成方法表。`Employee` 表显示所有方法都定义在 `Employee` 类本身中：

```
Employee:

    getName() -> Employee.getName()

    getSalary() -> Employee.getSalary()

    getHireDay() -> Employee.getHireDay()

    raiseSalary(double) -> Employee.raiseSalary(double)
```

实际上，这并不是全部故事——正如你在本章后面将看到的，`Employee` 类有一个父类 `Object`，它从中继承了许多方法。我们现在暂忽略 `Object` 的方法。

`Manager` 方法表略有不同。它继承了三个方法，重定义了一个方法，并增加了一个方法。

```
Manager:

    getName() -> Employee.getName()

    getSalary() -> Manager.getSalary()

    getHireDay() -> Employee.getHireDay()

    raiseSalary(double) -> Employee.raiseSalary(double)

    setBonus(double) -> Manager.setBonus(double)
```

在运行时，调用`e.getSalary()`的解析如下：

1. 首先，虚拟机获取`e`的实际类型的方法表。这可能是`Employee`、`Manager`或`Employee`的另一个子类的表。
2. 然后，虚拟机查找`getSalary()`签名的定义类。现在它知道要调用哪个方法了。
3. 最后，虚拟机调用该方法。

动态绑定有一个非常重要的属性：它使程序在不需要修改现有代码的情况下具有可扩展性。假设添加了一个新类`Executive`，并且变量`e`可能指向该类的对象。包含调用`e.getSalary()`的代码不需要重新编译。如果`e`恰好指向类型为`Executive`的对象，则会自动调用`Executive.getSalary()`方法。

---

![Image](img/caution.jpg) **注意：**

当你重写一个方法时，子类方法的可见性至少要与父类方法相同。特别是，如果父类方法是`public`，则子类方法也必须声明为`public`。无意中漏掉子类方法的`public`修饰符是一个常见的错误。编译器会报错，说你试图提供一个限制性更严格的访问权限。

### 5.1.7 防止继承：`final` 类和方法

有时，你想要防止某人创建你某个类的子类。无法被扩展的类被称为`final`类，你可以在类的定义中使用`final`修饰符来表示指示这一点。例如，假设我们想防止他人对`Executive`类进行子类。只需使用`final`修饰符声明该类，如下：

```java
public final class Executive extends Manager
{
    . . .
}
```

你也可以使类中的某个特定方法变为`final`。如果你这样做，任何子类都不能重写该方法。（`final`类中的所有方法都自动是`final`的。）例如：

```java
public class Employee
{
    . . .

    public final String getName()
    {
        return name;
    }

    . . .
}
```

---

![Image](img/note.jpg) **注意：**

记住，字段也可以声明为`final`。在对象构造完成后，`final`字段字段不能被更改。然而，如果一个类被声明为`final`，只有方法会自动变为`final`的，而不是字段。

将方法或类设为`final`的唯一理由是为了确保其语义在子类中不会被改变。例如，`Calendar`类的`getTime`和`setTime`方法是`final`的。这表明`Calendar`类的设计者已经承担了`Date`类与日历状态之间转换的责任。不应允许任何子类破坏这种安排。同样，`String`类是一个`final`类。这意味着没有人可以定义`String`的子类。换句话说，如果你有一个`String`引用，你就知道它指的是`String`。某些程序员认为，除非你有想要多态的理由，否则应该将所有方法都声明为`final`。在 Java 早期，一些程序员使用`final`关键字来避免动态绑定的开销。如果一个方法没有被重写且很短，那么编译器就可以优化掉该调用——这个过程称为内联（inlining）。例如，内联调用`e.getName()`会将其替换为字段访问`e.name`。这是一个值得的改进——CPU 讨厌分支，因为这会干扰它们的预取策略。如果`getName`在另一个类中可以被重写，编译器就无法进行内联。

幸运的是，即时编译器（JIT）比传统编译器做得更好。它确切知道哪些类扩展了类，并可以检查某个方法是否被重写。如果一个方法很短、被频繁调用且实际上没有被重写，即时编译器就可以将其内联。如果虚拟机加载了另一个覆盖内联方法的子类怎么办？优化器必须撤销内联。这需要时间，但确实会发生。

---

![Image](img/note.jpg) **注意：**

枚举和记录总是`final`的——你无法扩展它们。

### 5.1.8 转换

回想第 3 章中的内容，强制从一种类型转换为另一种类型的过程被称为转换（casting）。Java 编程语言对转换有特殊的表示法。例如：

```java
double x = 3.405;
int nx = (int) x;
```

将表达式`x`的值转换为整数，丢弃部分。

正如你需要将浮点数转换为整数，你可能需要将对象引用从一个类转换为另一个类。让我们再次使用包含`Employee`和`Manager`对象的数组示例：

```java
var staff = new Employee[3];
staff[0] = new Manager("Carl Cracker", 80000, 1987, 12, 15);
staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);
```

要实际对对象引用进行转换，使用与转换数值表达式相似的语法。将目标类名括在括号中，并将其放在要转换的对象引用之前。例如：

```java
Manager boss = (Manager) staff[0];
```

你想要进行类型转换（cast）的原因只有一个——在对象的实际类型被临时遗忘后，为了能够充分利用它的功能。例如，在`ManagerTest`类中，`staff`数组必须是`Employee`对象的数组，因为它的某些元素是普通员工。我们需要将数组中的管理类元素转换回`Manager`，以便访问它的任何新变量。（注意，在第一部分的示例代码中，我特意避免了类型转换。在将`boss`变量存入数组之前，我先用一个`Manager`对象对它进行了初始化。因为我需要正确的类型来设置经理的奖金。）

如你所知，在 Java 中，每个变量都有一个类型。类型描述了变量所引的对象种类以及它能做什么。例如，`staff[i]`指向一个`Employee`对象（因此它也可以指向一个`Manager`对象）。

编译器会检查你在向变量存储值时是否承诺了过多的内容。如果你将一个子类引用赋值给父类变量，你承诺的较少，编译器会直接允许你这样做。如果你将一个父类引用赋值给子类变量，你承诺的更多。这时，你必须使用类型转换，以便你的承诺可以在运行时得到检查。

### 如果你尝试对继承链进行向下转换并对对象包含的内容“撒谎”会发生什么？

```java
Manager boss = (Manager) staff[1]; // 错误
```

当程序运行时，Java 运行时系统会注意到违背的承诺并生成`ClassCastException`。如果你不捕获该异常，程序就会终止。因此，在尝试转换之前确定转换是否会成功是一种良好的编程习惯。只需使用`instanceof`运算符即可。例如：

```java
if (staff[i] instanceof Manager)
{
    boss = (Manager) staff[i];
}
```

最后，如果转换没有可能，编译器将不允许你进行转换。例如，以下转换：

```java
String c = (String) staff[i];
```

是一个编译时错误，因为`String`不是`Employee`的子类。

### 总结

- 你只能在继承层次结构内进行类型转换。
- 在从父类向子类转换之前，使用`instanceof`进行检查。

**注意：** 测试

```java
x instanceof C
```

如果`x`为`null`，则不会产生异常。它只是返回`false`。这是很有道理的：`null`指向任何对象，所以它显然没有指向类型为`C`的对象。

实际上，通过类型转换转换对象的类型通常不是一个好主意。在我们的示例中，对于大多数用途，你不需要将`Employee`对象转换为`Manager`对象。`getSalary`方法在两个类中都能正常工作。动态绑定使得多态得以实现。

进行转换的唯一理由是为了使用经理特有的方法，例如`setBonus`。如果由于某种原因，你发现想在`Employee`对象上调用`setBonus`，请问自己这是否表明父类的设计存在缺陷。重新设计父类并添加`setBonus`方法可能是合理的。记住，一个未捕获的`ClassCastException`就会终止你的程序。通常情况下，最好尽量减少类型转换和`instanceof`运算符的使用。

**C++ 注意：** Java 使用了 C 语言“旧时代”的类型转换语法，但它的作用类似于 C++ 中安全的`dynamic_cast`操作。例如：

```java
Manager boss = (Manager) staff[i]; // Java
```

等同于：

```cpp
Manager* boss = dynamic_cast<Manager*>(staff[i]); // C++
```

但有一个重要的区别。如果转换失败，它不会产生空对象，而是抛出一个异常。从这个意义上说，它类似于 C++ 引用的转换。这非常麻烦。在 C++ 中，你可以在一个操作中完成类型测试和类型转换。

```cpp
Manager* boss = dynamic_cast<Manager*>(staff[i]); // C++
if (boss != NULL)
```

在 Java 中，你需要结合使用`instanceof`运算符和类型转换。

```java
if (staff[i] instanceof Manager)
{
    boss = (Manager) staff[i];
}
```

### 5.1.9 `instanceof` 的模式匹配

代码：

```java
if (staff[i] instanceof Manager)
{
    boss = (Manager) staff[i];
    boss.setBonus(5000);
}
```

相当冗长。我们真的需要提到子类`Manager` 3 次吗？

从 Java 16 开始，有一种更简单的方法。你可以直接在`instanceof`测试中声明子类变量：

```java
if (staff[i] instanceof Manager boss)
{
    boss.setBonus(5000);
}
```

如果`staff[i]`是`Manager`类的实例，那么变量`boss`被赋值为`staff[i]`，你可以将其作为`Manager`使用。你跳过了类型转换。

如果`staff[i]`不指向`Manager`，`boss`不会被赋值，且`instanceof`运算符产生值`false`。`if`语句体被跳过。

**提示：** 在大多数使用`instanceof`的情况下，你需要应用子类方法。这时请使用这种“模式匹配”形式的`instanceof`来代替类型转换。

一个无用的`instanceof`模式是一个错误：

```java
Manager boss = ...;
if (boss instanceof Employee) // 错误：当然是 Employee
```

**注意：** 同样无用的

```java
if (boss instanceof Employee)
```

是允许的，为了兼容 Java 1.0。

当`instanceof`模式引入一个变量时，你可以立即在表达式中使用它：

```java
Employee e;
if (e instanceof Manager m && m.getBonus() > 10000)
```

这是可行的，因为`&&`表达式的右侧在左侧为`true`时才会执行。如果执行了右侧，`m`已经绑定到一个`Manager`实例。

然而，以下代码是编译错误：

```java
if (e instanceof Manager || m.getBonus() > 10000)
```

`||`的右侧在左侧为`false`时执行，此时没有绑定`m`。

这是另一个使用条件运算符的例子：

```java
double bonus = e instanceof Manager ? m.getBonus() : 0;
```

变量`m`定义在`?`之后的表达式中，而不是`:`之后。

**注意：** 变量`instanceof`被称为“模式匹配”，因为它类似于`switch`中的类型模式，这是 Java 17 的一个“预览”功能。我不会详细讨论预览功能，但这里有一个语法示例：

```java
String description = switch (e) {
    case exec -> "一个拥有华丽头衔的执行官：" + exec.getTitle();
    case Manager m -> "一个拥有奖金的经理：" + m.getBonus();
    default -> "一个工资较低的员工：" + e.getSalary();
};
```

与`instanceof`模式一样，每个类型模式都声明了一个变量。

**警告：** 与局部变量一样，由`instanceof`模式定义的局部变量可以遮蔽字段。例如：

```java
class Value {
    private double v;
    public boolean equals(Value other) {
        if (other instanceof LabeledValue v)
            // v 等于 other
        else
            // v 指代字段
    }
    ...
}
```

### 5.1.10 `protected` 访问

如你所知，类中的字段最好被标记为`private`，而方法通常标记为`public`。任何声明为`private`的特性在其他类中都是不可访问的。正如章节开头解释的那样，对于子类也是如此：子类无法访问其父类的私有字段。

然而，某些时候你可能希望将一个方法限制为仅子类可以使用，或者较少地允许子类方法访问父类的字段。在这种情况下，你将类特征声明为`protected`。例如，如果父类`Employee`将`hireDay`字段声明为`protected`而不是`private`，那么`Manager`方法就可以直接访问它。

在 Java 中，`protected`字段可以被同一个包中的任何类访问。现在考虑位于不同包中的`Administrator`子类。`Administrator`类的方法只能查看`Administrator`对象的`hireDay`字段，而不能查看其他`Employee`对象的该字段。这种限制是为了防止你通过特意创建子类来获取`protected`字段的访问权限，从而滥用`protected`机制。

实践中，请谨慎使用`protected`字段。假设你的类被其他程序员使用，并且你在设计时使用了`protected`字段。在你不知情的情况下，其他程序员可能会继承你的类并开始访问你的`protected`字段。在这种情况下，你无法在不扰乱那些程序员的情况下更改你类的实现。这违背了鼓励数据封装的面向对象编程（OOP）的精神。

`protected`方法则更有意义。如果一个方法使用起来很复杂，类可以将其声明为`protected`。这表示子类（假设它们很了解自己的祖先）可以被信任正确地使用该方法，而其他类则不能。

这种方法的很好例子是`Object`类的`clone`方法——更多细节请参阅第 6 章。

---

![Image](img/c.jpg) **C++ 注意：**

正如前面提到的，Java 中的`protected`特性对所有子类以及同一个包中的所有其他类都是可见。这与 C++ 中`protected`的含义略有不同，它使得 Java 中`protected`的概念比 C++ 更不安全。

以下是 Java 中四种访问控制修饰符的总结：

1. 仅类内可见（`private`）。
2. 全局可见（`public`）。
3. 包内及所有子类均可见（`protected`）。
4. 包内可见——（不幸的）默认值。不需要修饰符。

### 5.2 `Object`：宇宙父类

`Object`类是终极祖先——Java 中的每一个类都继承`Object`。然而，你永远不需要写：



```java
public class Employee extends Object
```

## 5.2 `Object` 类

如果没有显式提到父类，则终极父类 `Object` 是理所当然的。由于 Java 中的每个类都继承 `Object`，因此熟悉 `Object` 类提供的服务非常重要。我在这章中概述了基础方法；对于未涵盖的内容，请咨询后面的章节或查看在线文档。（`Object` 的某些方法仅在处理并发时才会出现——参见第 12 章。）

### 5.2.1 `Object` 类型的变量

你可以使用 `Object` 类型的变量来引用任何类型的对象：

```java
Object obj = new Employee("Harry Hacker", 35000);
```

当然，`Object` 类型的变量仅作为任意值的通用容器时是有意义的。要对该值进行任何特定操作，你需要对原始类型有一定了解并应用强制转换：

```java
Employee e = (Employee) obj;
```

### 在 Java 中，只有基本类型的值（数字、字符和 `boolean` 值）不是对象。

所有的数组类型，无论是对象数组还是基本类型数组，都是继承 `Object` 类的类型。

```java
Employee[] staff = new Employee[10];

obj = staff; // OK

obj = new int[10]; // OK
```

---

![Image](img/c.jpg) **C++ 注意：**

在 C++ 中，没有宇宙根基类。然而，每个指针都可以转换为 `void*` 指针。

---

### 5.2.2 `equals` 方法

`Object` 类中的 `equals` 方法测试一个对象是否被认为与另一个对象相等。`Object` 类中实现的 `equals` 方法决定了两个对象引用是否完全相同。这是一个非常合理的默认值——如果两个对象是相同的，那么它们当然是相等的。对于许多类来说，不需要其他操作。例如，比较两个 `PrintStream` 对象的相等性几乎没有意义。但是，你通常想要实现基于状态的相等性测试，即当两个对象具有相同状态时，它们被认为是相等。

例如，让我们认为两个员工具有相同的姓名、薪水和入职日期，那么他们就是相等的。（在实际的员工数据库中，比较 ID 反而更合理。我使用这个例子来演示实现 `equals` 方法的机制。）

```java
public class Employee
{
  // ...

  public boolean equals(Object otherObject)
  {
      // 快速测试对象是否相同
      if (this == otherObject) return true;

      // 如果显式参数为 null，必须返回 false
      if (otherObject == null) return false;

      // 如果类不同，它们就不可能相等
      if (getClass() != otherObject.getClass())
        return false;

      // 现在我们知道 otherObject 是一个 Employee
      Employee other = (Employee) otherObject;

      // 测试字段是否相同
      return name.equals(other.name)
        && salary == other.salary
        && hireDay.equals(other.hireDay);
  }
}
```

`getClass()` 方法返回对象的类——我们稍后会详细讨论这个方法。在我们的测试中，对象只有在类相同时才是相等的。

---

![Image](img/tip.jpg) **提示：**

为了防止 `name` 或 `hireDay` 为 `null`，使用 `Objects.equals` 方法。`Objects.equals(a, b)` 在两个参数均为 `null` 时返回 `true`，如果仅一个为 `null` 则返回 `false`，否则调用 `a.equals(b)`。有了该方法，`Employee.equals` 方法的最后一条语句变为：

```java
return Objects.equals(name, other.name)
  && salary == other.salary
  && Objects.equals(hireDay, other.hireDay);
```

---

为子类定义 `equals` 方法时首先调用父类的 `equals`。如果该测试没有通过，则对象就不相等。如果父类字段相等，你就可以比较子类的实例字段了。

```java
public class Manager extends Employee
{
  public boolean equals(Object otherObject)
  {
      if (!super.equals(otherObject))
        return false;

      // 现在我们知道 otherObject 是一个 Manager
      Manager other = (Manager) otherObject;

      return bonus == other.bonus;
  }
}
```

---

![Image](img/note.jpg) **注意：**

回想第 4 章，`record` 是一种特殊的不可变类，其状态完全由“规范”构造函数设置的字段定义。`record` 自动定义 `equals` 方法来比较字段。当相应的字段值相等时，两个 `record` 实例相等。

### 5.2.3 等等测试与继承

当隐性和显式参数不属于同一个类时，`equals` 方法应该如何表现？这一直是一个争议区域。在之前的示例中，如果类不完全匹配，`equals` 方法返回 `false`。但许多程序员使用 `instanceof` 测试来代替它：

```java
if (!(otherObject instanceof Employee)) return false;
```

这留下了 `otherObject` 可能属于子类的可能性。然而，这种方法可能会让你陷入麻烦。原因如下：Java 语言规范要求 `equals` 方法具有以下属性：

1. 自反性：对于任何非空引用 `x`，`x.equals(x)` 应该返回 `true`。
2. 对称性：对于任何引用 `x` 和 `y`，当且仅当 `y.equals(x)` 返回 `true` 时，`x.equals(y)` 返回 `true`。
3. 具有传递性：对于任何引用 `x`、`y` 和 `z`，如果 `x.equals(y)` 返回 `true` 且 `y.equals(z)` 返回 `true`，那么 `x.equals(z)` 应该返回 `true`。
4. 具有一致性：如果 `x` 和 `y` 所引的对象没有发生变化，那么重复调用 `x.equals(y)` 将返回相同的值。
5. 对于任何非空引用 `x`，`x.equals(null)` 应该返回 `false`。

这些规则显然是合理的。你不希望一个库的实现者在数据结构中定位元素时，还要纠结是调用 `x.equals(y)` 还是 `y.equals(x)`。

然而，当参数属于不同的类时，对称规则会产生微妙的后果。考虑以下调用：

```java
e.equals(m)
```

其中 `e` 是一个 `Employee` 对象，而 `m` 是一个 `Manager` 对象，它们恰好具有相同的姓名、工资和入职日期。如果 `Employee.equals` 使用了 `instanceof` 测试，则调用返回 `true`。但这意味着反向调用：

```java
m.equals(e)
```

也需要返回 `true`——对称规则不允许它返回 `false` 或抛出异常。

这让 `Manager` 类陷入了困境。它的 `equals` 方法必须愿意与任何 `Employee` 进行比较，而又不考虑经理特有的信息！突然之间，`instanceof` 测试看起来就没以前那么有吸引力了。

一些作者公开记录过，`getClass` 测试是错误的，因为它违反了替换原则。一个被经常引用的例子是 `AbstractSet` 类中的 `equals` 方法，它用于测试两个集合是否具有相同的元素。`AbstractSet` 类有两个具体的子类 `TreeSet` 和 `HashSet`，它们使用不同的算法来定位集合元素。你确实希望能够比较任何两个集合，无论它们是如何实现的。

然而，集合的例子是相当特殊的。将 `AbstractSet.equals` 声明为 `final` 是有意义的，因为不应该允许任何人重新定义集合等等的语义。（该方法实际上并不是 `final`。这允许子类实现一种更高效的等性测试算法。）

在我看来，存在两种不同的场景：

- 如果子类可以有自己的等价概念，那么对称性要求迫使你使用 `getClass` 测试。
- 如果等价概念在父类中是固定的，你可以使用 `instanceof` 测试，并允许不同子类的对象相互相等。

在员工和经理的示例中，当两个对象具有匹配字段时，我们认为它们是相等的。有两个姓名、工资和入职日期相同的 `Manager` 对象，但奖金不同，我们希望它们是不同的。因此，我们使用 `getClass` 测试。

但假设我们使用员工 ID 进行等性测试。这种等价概念对所有子类都是合理的。那么我们就可以使用 `instanceof` 测试，并且应该将 `Employee.equals` 声明为 `final`。

---

![Image](img/note.jpg) **注意：**

标准 Java 库包含了 150 多个 `equals` 方法的实现，其中混杂了使用 `instanceof`、调用 `getClass`、捕获 `ClassCastException` 或什么都不做。查看 `java.sql.Timestamp` 类的 API 文档，实现者在有些尴尬地指出他们自己陷入了困境。`Timestamp` 类继承自 `java.util.Date`，后者的 `equals` 方法使用了 `instanceof` 测试，而无法重写 `equals` 使得它既对称又准确。

这里是编写完美的 `equals` 方法的配方：

1. 将显式参数命名为 `otherObject`——稍后，你需要将它转换为另一个变量，并将其称为 `other`。
2. 测试 `this` 是否与 `otherObject` 相同：

   ```java
   if (this == otherObject) return true;
   ```

   该语句仅仅是一种优化。在实践中，这是一种常见做法。检查标识性比比较字段要便宜得多。

3. 测试 `otherObject` 是否为 `null`，如果是则返回 `false`。这个测试是必要的。

   ```java
   if (otherObject == null) return false;
   ```

4. 比较 `this` 和 `otherObject` 的类。如果 `equals` 的语义可以在子类中改变，请使用 `getClass` 测试：

   ```java
   if (getClass() != otherObject.getClass()) return false;

   ClassName other = (ClassName) otherObject;
   ```

   如果所有子类的语义保持一致，你可以使用 `instanceof` 测试：

   ```java
   if (!(otherObject instanceof ClassName other)) return false;
   ```

   注意，如果 `instanceof` 测试成功，会将 `other` 设置为 `otherObject`。不需要进行强制转换。

5. 现在根据你的等价概念比较字段。对于原始类型字段使用 `==`，对于对象字段使用 `Objects.equals`。如果所有字段都匹配则返回 `true`，否则返回 `false`。

   ```java
   return field1 == other.field1
      && Objects.equals(field2, other.field2)
      && . . .;
   ```

如果你在子类中重写 `equals`，请包含对 `super.equals(other)` 的调用。

---

![Image](img/tip.jpg) **提示：**

如果你有数组类型的字段，可以使用静态的 `Arrays.equals` 方法来检查对应的数组元素是否相等。对于多维数组使用 `Arrays.deepEquals` 方法。

---

![Image](img/caution.jpg) **注意：**

这是一个实现 `equals` 方法时的常见错误。你能发现问题所在？

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
  . . .
}
```

该方法将参数类型声明为 `Employee`。结果是它没有覆盖 `Object` 类的任何方法。你可以通过对意图覆盖父类方法的方法标记 `@Override` 来防止此类错误：

```java
@Override public boolean equals(Object other)
```

### 5.2.4 `hashCode` 方法

哈希码是从对象派生的整数。哈希码应该是散乱的——如果 `x` 和 `y` 是两个不同的对象，那么 `x.hashCode()` 和 `y.hashCode()` 相等的概率很小。表 5.1 列出了 `String` 类的 `hashCode` 方法产生的一些哈希码示例。

`String` 类使用以下算法计算哈希码：

```java
int hash = 0;

for (int i = 0; i < length(); i++)

  hash = 31 * hash + charAt(i);
```

**表 5.1** 来自 `hashCode` 方法的哈希码

![Image](img/05tab1.jpg)

表 5.2 显示了结果。

### 表 5.2 字符串和 `StringBuilder` 的哈希码

![Images](img/05tab02.jpg)

注意，字符串 `s` 和 `t` 具有相同的哈希码，因为对于字符串来说，哈希码是从它们的 `contents` 派生出来的。`StringBuilder` `sb` 和 `tb` 具有不同的哈希码，因为 `StringBuilder` 类没有定义 `hashCode` 方法，而 `Object` 类中的默认 `hashCode` 方法是根据对象的内存地址派生哈希值的。

如果你重新定义了 `equals` 方法，那么你还需要为用户可能插入到哈希表中的对象重新定义 `hashCode` 方法。（我在第 9 章中讨论了哈希表。）

`hashCode` 方法应该返回一个整数（可以是负数）。只需将实例字段的哈希值组合在一起，使得不同对象的哈希值可能广泛地分布。

例如，这里是 `Employee` 类的 `hashCode` 方法：

```java
public class Employee
{
  public int hashCode()
  {
    return 7 * name.hashCode()
          + 11 * Double.valueOf(salary).hashCode()
          + 13 * hireDay.hashCode();
  }
  . . .
}
```

然而，你可以做得更好。首先，使用空安全的方法 `Objects.hashCode`。如果参数为 `null`，它返回 `0`；否则返回对参数调用 `hashCode` 的结果。此外，使用静态方法 `Double.hashCode` 来避免创建 `Double` 对象：

```java
public int hashCode()
{
  return 7 * Objects.hashCode(name)
      + 11 * Double.hashCode(salary)
      + 13 * Objects.hashCode(hireDay);
}
```

更好的是，当你需要组合多个哈希值时，调用 `Objects.hash` 并传入所有值。它会为每个参数调用 `Objects.hashCode` 并组合这些值。那么 `Employee.hashCode` 方法简单地就是：

```java
public int hashCode()
{
  return Objects.hash(name, salary, hireDay);
}
```

你对 `equals` 和 `hashCode` 的定义必须保持兼容：如果 `x.equals(y)` 为 `true`，那么 `x.hashCode()` 返回的值必须与 `y.hashCode()` 相同。例如，如果你定义 `Employee.equals` 来比较员工 ID，那么 `hashCode` 方法就需要对 ID 进行哈希，而不是姓名或内存地址。

---

![Image](img/tip.jpg) **提示：**

如果你有数组类型的字段，可以使用静态方法 `Arrays.hashCode` 来计算一个由数组元素哈希码组成的哈希码。

---

![Image](img/note.jpg) **注意：**

`record` 类型自动提供了一个 `hashCode` 方法，该方法从字段值的哈希码派生出哈希码。

---

![Image](img/caution.jpg) **警告：**



如果实例变量的取值范围很小，你需要尽可能获得许多不同的哈希码。考虑对日期进行哈希。计算`7 * year + 11 * month + 13 * day`会产生很多冲突。相比之下，`31 * 12 * year + 31 * month + day`是一个“完美哈希函数”。假设在一个合理的年份范围内，没有两个日期具有相同的哈希码。（`LocalDate`类的实际`hashCode`方法支持 ±999,999,999 年的范围，要复杂得多。）

### `java.lang.Object` 1.0

- `int hashCode()`

返回此对象的哈希码。哈希码可以是任何整数，正数或负数。相同的对象需要返回相同的哈希码。

### `java.util.Objects` 7

- `static int hash(Object... objects)`

返回由所有提供的对象的哈希码组合成的哈希码。

- `static int hashCode(Object a)`

如果`a`为`null`则返回`0`，否则返回`a.hashCode()`。

### `java.lang.(Integer`|`Long`|`Short`|`Byte`|`Double`|`Float`|`Character`|`Boolean`)` 1.0

- `static int hashCode(xxx value)` 8

返回给定值的哈希码。这里`xxx`是对应于给定包装类型的原始类型。

### `java.util.Arrays` 1.2

- `static int hashCode(xxx[] a)` 5

计算数组`a`的哈希码。数组的组件类型`xxx`可以是`Object`、`int`、`long`、`short`、`char`、`byte`、`boolean`、`float`或`double`。

#### 5.2.5 `toString`方法

`Object`中的另一个重要方法是`toString`，它返回表示对象值的字符串。这是一个典型的示例。`Point`类的`toString`方法返回如下：

```
java.awt.Point[x=10,y=20]
```

大多数（并非所有）`toString`方法都遵循这种格式：类名，然后是方括号内的字段值。这里是`Employee`类的`toString`方法的实现：

```java
public String toString()
{
  return "Employee[name=" + name + ",salary=" + salary + ",hireDay=" + hireDay + "]";
}
```

实际上，你可以做得更好。对于`toString`方法，很多类都硬编码了类名。集成开发环境（IDE）可以生成如下`toString`方法：

```java
public String toString()
{
  return "Employee[name=" + name + ",salary=" + salary + ",hireDay=" + hireDay + "]";
}
```

如第 7 章所示，一种更好的解决方案是使用`Logger`类的对象并调用

```java
Logger.global.info("Current position = " + position);
```

**提示：**

我强烈建议你为你编写的每个类都添加一个`toString`方法。你以及其他使用你类的程序员都会对这种日志支持表示感激的。

然而，对于`record`类型，已经提供了`toString`方法。它简单地列出了类名以及字段的名称和字符串化后的值。

代码列表 5.4 中的程序测试了`Employee`类（代码列表 5.5）和`Manager`类（代码列表 5.6）的`equals`、`hashCode`和`toString`方法。

#### 代码列表 5.4 `equals/EqualsTest.java`

```java
package equals;

/**
 * This program demonstrates the equals method.
 * @version 1.2 2012-01-26
 * @author Caymann
 */
public class EqualsTest {
    public static void main(String[] args) {
        var alice1 = new Employee("Alice Adams", 75000, 1987, 12, 15);
        var alice2 = alice1;
        var alice3 = new Employee("Alice Adams", 75000, 1987, 12, 15);
        var bob = new Employee("Bob Brandson", 50000, 1989, 10, 1);

        System.out.println("alice1 == alice2: " + (alice1 == alice2));
        System.out.println("alice1 == alice3: " + (alice1 == alice3));
        System.out.println("alice1.equals(alice3): " + alice1.equals(alice3));
        System.out.println("alice1.equals(bob): " + alice1.equals(bob));
        System.out.println("bob.toString(): " + bob);

        var carl = new Manager("Carl Cracker", 80000, 1987, 12, 15);
        var boss = new Manager("Carl Cracker", 80000, 1987, 12, 15);
        boss.setBonus(5000);
        System.out.println("boss.toString(): " + boss);
        System.out.println("carl.equals(boss): " + carl.equals(boss));
        System.out.println("alice1.hashCode(): " + alice1.hashCode());
        System.out.println("alice3.hashCode(): " + alice3.hashCode());
        System.out.println("bob.hashCode(): " + bob.hashCode());
        System.out.println("carl.hashCode(): " + carl.hashCode());
    }
}
```

#### 代码列表 5.5 `equals/Employee.java`

```java
package equals;

import java.time.*;
import java.util.Objects;

public class Employee {
    private String name;
    private double salary;
    private LocalDate hireDay;

    public Employee(String name, double salary, int year, int month, int day) {
        this.name = name;
        this.salary = salary;
        hireDay = LocalDate.of(year, month, day);
    }

    public String getName() {
        return name;
    }

    public double getSalary() {
        return salary;
    }

    public LocalDate getHireDay() {
        return hireDay;
    }

    public void raiseSalary(double byPercent) {
        double raise = salary * byPercent / 100;
        salary += raise;
    }

    public boolean equals(Object otherObject) {
        // 快速测试对象是否相同
        if (this == otherObject) return true;
        // 如果显式参数为 null，则返回 false
        if (otherObject == null) return false;
        // 如果类不匹配，则它们相等
        if (getClass() != otherObject.getClass()) return false;
        // 现在我们知道 otherObject 是一个非空的 Employee
        var other = (Employee) otherObject;
        // 测试字段是否具有相同的值
        return Objects.equals(name, other.name) && salary == other.salary && Objects.equals(hireDay, other.hireDay);
    }

    public int hashCode() {
        return Objects.hash(name, salary, hireDay);
    }

    public String toString() {
        return getClass().getName() + "[name=" + name + ",salary=" + salary + ",hireDay=" + hireDay + "]";
    }
}
```

#### 代码列表 5.6 `equals/Manager.java`

```java
package equals;

public class Manager extends Employee {
    private double bonus;

    public Manager(String name, double salary, int year, int month, int day) {
        super(name, salary, month, day);
        bonus = 0;
    }

    public double getSalary() {
        double baseSalary = super.getSalary();
        return baseSalary + bonus;
    }

    public void setBonus(double bonus) {
        this.bonus = bonus;
    }

    public boolean equals(Object otherObject) {
        if (!super.equals(otherObject)) return false;
        var other = (Manager) otherObject;
        // super.equals 检查了 this 和 other 是否属于同一个类
        return bonus == other.bonus;
    }

    public int hashCode() {
        return java.util.Objects.hash(super.hashCode(), bonus);
    }

    public String toString() {
        return super.toString() + "[bonus=" + bonus + "]";
    }
}
```

这种语法被称为“钻石”语法，因为空括号`<>`看起来像菱形。将钻石语法与`new`运算符一起使用。编译器会检查新值发生了了什么。如果它被赋值给一个变量、传递给方法或从方法返回，那么编译器就会检查该变量、参数或方法的泛型类型。然后，它会将该类型放入`<>`中。在我们的示例中，`new ArrayList<>()`被赋值给类型为`ArrayList<Employee>`的变量。因此，泛型类型是`Employee`。

**警告：**

如果你使用`var`声明`ArrayList`，请*不要*使用钻石语法。以下声明：

```
var elements = new ArrayList<>();
```

会产生一个`ArrayList<Object>`。

**注意：**

在 Java 5 之前，没有泛型类。相反，只有一个`ArrayList`类，它是一个通用的集合，用于存储`Object`类型的元素。你仍然可以在不带`<. . .>`后缀的情况下使用`ArrayList`。它被视为“原始”（raw）类型，类型参数被擦除了。

**注意：**

在更早的 Java 版本中，程序员使用`Vector`类来实现动态数组。然而，`ArrayList`类更高效，已经没有充分的理由使用`Vector`类了。

使用`add`方法向数组列表添加新元素。例如，这里是如何向数组列表填充`Employee`对象的：

```
staff.add(new Employee("Harry Hacker", . . .));

staff.add(new Employee("Tony Tester", . . .));
```

数组列表管理一个内部的对象引用数组。最终，该数组将耗尽所有空间。这就是数组列表发挥魔法的地方：如果你调用`add`且内部数组已满，数组列表会自动创建一个更大的数组，并将所有对象从较小的数组复制到较大的数组中。

如果你已经知道（或大致估计）想要存储多少个元素，可以在填充数组列表之前调用`ensureCapacity`方法：

```
staff.ensureCapacity(100);
```

该调用分配了一个可以包含 100 个对象的内部数组。然后，前 100 次`add`调用将不会涉及任何昂贵的重新分配。

你也可以向`ArrayList`构造函数传递一个初始容量：

```
ArrayList<Employee> staff = new ArrayList<>(100);
```

**警告：**

按如下分配数组列表：

```
new ArrayList<>(100) // 容量为 100
```

*并不同于*分配一个新数组：

```
new Employee[100] // 大小为 100
```

数组列表的容量与数组的大小之间存在重要的区别。如果你分配了一个具有 100 个条目的数组，那么数组就有 100 个空位可以直接使用。容量为 100 个元素的数组列表*潜力*持有 100 个元素（实际上可以超过 100 个，但是以额外重新分配为代价的），但在开始时，即使在初始构造之后，数组列表也一个元素都没有。

`size`方法返回数组列表中元素的实际数量。例如，

```
staff.size()
```

返回`staff`数组列表中当前的元素数量。这等同于数组`a`的

```
a.length
```

一旦你相当确定数组列表已经达到了其固定大小，就可以调用`trimToSize`方法。该方法调整内存块的大小，使其恰好使用存储当前元素数量所需的存储空间。垃圾回收器将回收任何多余内存。

一旦你修剪数组列表的大小，添加新元素将再次移动该块，这需要时间。只有当你确定不会再向数组列表添加更多元素时，才应该使用`trimToSize`。

**C++ 注意：**



`ArrayList` 类类似于 C++ 的 `vector` 模板。`ArrayList` 和 `vector` 都是泛型类型。但 C++ 的 `vector` 模板重载了 `[]` 运算符以便于访问元素。Java 没有运算符重载，因此必须使用显式方法调用。

此外，C++ `vector` 是按值拷贝的。如果 `a` 和 `b` 是两个 `vector`，那么赋值 `a = b` 会使 `a` 变成一个与 `b` 长度相同的新 `vector`，并将所有元素从 `b` 复制到 `a`。Java 中相同的赋值会使 `a` 和 `b` 都指向同一个数组列表。

---

## `java.util.ArrayList<E>` 1.2

- `ArrayList<E>()` 构建一个空的数组列表。
- `ArrayList<E>(int initialCapacity)` 构建一个具有指定容量的空数组列表。
- `boolean add(E obj)` 将 `obj` 追加到数组列表的末尾。始终返回 `true`。
- `int size()` 返回数组列表中当前存储的元素数量。（当然，这永远不会超过列表的容量。）
- `void ensureCapacity(int initialCapacity)` 确保数组列表具有给定的容量。
- `void trimToSize()` 将数组列表的大小减小到当前大小。

### 5.3.2 访问数组列表

不幸的是，没有什么是免费的。使用 `get` 和 `set` 方法。

获取数组元素，使用：

```java
Employee e = staff.get(i);
```

这等同于数组 `a` 的：

```java
Employee e = a[i];
```

（对于数组一样）

![Image](img/caution.jpg) **警告：**

不要在数组列表大于 `i` 时调用 `list.set(i)`。例如，以下代码是错误的：

```java
var list = new ArrayList<Employee>(100); // 容量 100，大小 0

list.set(0); // 元素 0
```

![Image](img/note.jpg) **注意：**

在没有泛型类时，原始 `ArrayList` 的 `get` 方法只能返回 `Object`。因此，`get` 的调用者必须将返回值转换为所需的类型：

```java
Employee e = (Employee) staff.get(i);
```

原始 `ArrayList` 也有点危险。它的 `add` 和 `set` 方法接受任何类型的对象。调用：

```java
staff.set(i, "Harry Hacker");
```

编译没有任何警告，只有当你检索对象并尝试对其强制转换时才会遇到麻烦。如果你使用 `ArrayList<Employee>`，编译器将检测到此错误。

有时你可以通过以下技巧兼顾两者——灵活的增长和方便的元素访问。首先，创建一个数组列表并添加所有元素：

```java
var list = new ArrayList<X>();

while (. . .)
{
  x = . . ++;
  list.add(x);
}
```

当你完成后，使用 `toArray` 方法将元素复制到数组中：

```java
var a = new X[list.size()];

list.toArray(a);
```

有时你需要在数组列表的中间添加元素。使用带有索引参数的 `add` 方法：

```java
int n = staff.size() / 2;

staff.add(n, e);
```

位置 `n` 及以上的元素将向上移动，为新条目留出空间。如果插入后数组列表的新大小超过容量，数组列表将重新分配其存储数组。

同样，你可以从数组列表的中间删除元素：

```java
Employee e = staff.remove(n);
```

位于上面的元素将向下复制，数组的大小将减一。

## ArrayList 操作

插入和删除元素的效率并不高。对于小型数组列表，这可能不值得担心。但如果你存储了许多元素并频繁在集合中间插入和删除，请考虑改用链表。我在第 9 章中解释了如何使用链表进行编程。

你可以使用“for each”循环来遍历数组列表的内容：

```java
for (Employee e : staff)
    do something with e
```

该循环的效果等于：

```java
for (int i = 0; i < staff.size(); i++)
{
    Employee e = staff.get(i);
    do something with e
}
```

Listing 5.7 是对第 4 章中 `EmployeeTest` 程序的修改。`Employee[]` 数组被替换为 `ArrayList<Employee>`。请注意以下变化：

- 你不需要指定数组的大小。
- 你使用 `add` 添加任意数量的元素。
- 你使用 `size()` 代替 `length` 来计算元素个数。
- 你使用 `a.get(i)` 代替 `a[i]` 来访问元素。

**Listing 5.7** `arrayList/ArrayListTest.java`

```java
 1  package arrayList;
 2
 3  import java.util.*;
 4
 5  /**
 6   * 此程序演示了 ArrayList 类。
 7   * @version 1.11 2012-01-26
 8   * @author Cay Horstmann
 9   */
10  public class ArrayListTest
11  {
12      public static void main(String[] args)
13      {
14          // 用三个 Employee 对象填充 staff 数组列表
15          var staff = new ArrayList<Employee>();
16
17          staff.add(new Employee("Carl Cracker", 75000, 1987, 12, 15));
18          staff.add(new Employee("Harry Hacker", 50000, 1989, 10, 1));
19          staff.add(new Employee("Tony Tester", 40000, 1990, 3, 15));
20
21          // 将每个人的薪水增加 5%
22          for (Employee e : staff)
23              e.raiseSalary(5);
24
25          // 打印所有 Employee 对象的信息
26          for (Employee e : staff)
27              System.out.println("name=" + e.getName() + ",salary=" + e.getSalary() + ",hireDay="
28                  + e.getHireDay());
29      }
30  }
```

## `java.util.ArrayList<E>` 1.2

- `E set(int index, E obj)` 将值 `obj` 放在列表中指定的索引处，并返回之前的内容。
- `E get(int index)` 获取存储在指定索引的值。
- `void add(int index, E obj)` 向上移动元素，以便在指定的索引处插入 `obj`。
- `E remove(int index)` 删除指定索引处的元素，并向下移动其上方的所有元素。返回被删除的元素。

### 5.3.3 类型数组列表与原始数组列表之间的兼容性

在你自己的代码中，你总是希望使用类型参数来增加安全性。在本节中，你将看到如何与未使用类型参数的旧代码进行交互。

假设你有以下旧类：

```java
public class EmployeeDB
{
  public void update(ArrayList list) { . . . }
  public ArrayList find(String query) { . . . }
}
```

你可以直接将类型数组列表传递给 `update` 方法而无需任何强制转换：

```java
ArrayList<Employee> staff = . . .;

employeeDB.update(staff);
```

尽管 `ArrayList<Employee>` 是 `ArrayList` 的子类型，但编译器会发出警告，因为 `ArrayList` 是原始类型。当你将类型列表传递给原始方法时，类型安全性被破坏，因为编译器无法保证添加到列表中的元素是正确的类型。

要抑制此警告，可以使用 `@SuppressWarnings("unchecked")` 注解：

```java
@SuppressWarnings("unchecked")
ArrayList<Employee> staff = . . .;

employeeDB.update(staff);
```

### 5.4 包装类与自动装箱

有时，你需要将基本类型转换为对象。所有基本类型都有对应的类型：`Integer`、`Long`、`Float`、`Double`、`Short`、`Byte`、`Character` 和 `Boolean`（前六个继承自共同父类 `Number`）。包装类是不可变的——不能对其类。

假设我们需要一个整数数组列表。遗憾的是，括号不能是基本类型。声明一个 `Integer` 数组列表是可以的：

```java
var list = new ArrayList<Integer>();
```

`ArrayList<Integer>` 的效率远低于 `int[]` 数组，因为每个值都单独封装在一个对象内部。当程序员的便利性比效率更重要时，你才会对小型集合使用这种结构。

幸运的是，有一个非常有用的功能可以方便地向 `ArrayList<Integer>` 添加 `int` 类型的元素。调用：

```java
list.add(3);
```

会被自动转换为：

```java
list.add(Integer.valueOf(3));
```

这种转换被称为*自动装箱*。

相反，当你将 `Integer` 对象赋值给 `int` 值时，它会自动拆箱。也就是说，编译器将：

```java
int n = list.get(i);
```

翻译为：

```java
int n = list.get(i).intValue();
```

装箱和拆箱甚至适用于算术表达式。例如，你可以对包装引用应用递增运算符：

```java
Integer n = 3;

n++;
```

编译器会自动插入指令来拆箱对象、增加值并重新装箱。

在大多数情况下，你会产生基本类型和其包装是相同的错觉。它们仅在一个点上有显著的差异：标识性。正如你所知，`==` 运算符应用于包装对象时，仅测试是否具有相同的内存位置。因此，以下比较可能会失败：

```java
Integer a = 1000;

Integer b = 1000;

if (a == b) . . .
```

然而，Java 的实现 `may` 在其选择的情况下，将经常出现的值包装成相同的对象，因此比较可能会成功。这种歧义并不是你所想要的。解决办法是在比较包装对象时调用 `equals` 方法。

![Image](img/note.jpg) **注意：**

自动装箱规范要求 `boolean`、`byte`、`char` <= `127`、`short` 以及在 `-128` 到 `127` 之间的 `int` 被包装成固定的对象。例如，如果上一个示例中的 `a` 和 `b` 被初始化为 `100`，那么比较将会成功。

![Image](img/tip.jpg) **提示：**

永远不要依赖包装对象的身份标识性。不要用 `==` 比较它们，也不要将它们用作锁（参见第 14 章）。

不要使用包装类的构造函数。它们已经废弃并计划删除。例如，请使用 `Integer.valueOf(1000)`，而永远不要使用 `new Integer(1000)`。或者，简单地依赖自动装箱：`Integer a = 1000`。

关于自动装箱还有其他几个微妙之处。首先，由于包装类引用可以为 `null`，自动拆箱可能会抛出 `NullPointerException`：

```java
Integer n = null;

System.out.println(2 * n); // 产生 NullPointerException
```

此外，如果你在条件表达式中混合了 `Integer` 和 `Double` 类型，那么 `Integer` 值将被拆箱、提升为 `double`，并包装成 `Double`：

```java
Integer n = 1;

Double x = 2.0;

System.out.println(true ? n : x); // 输出 1.0
```

最后，让我们强调一下，装箱和拆箱是 `compiler` 提供的便利，而不是虚拟机的功能。编译器在生成类的字节码时会插入必要的调用。虚拟机仅仅执行这些字节码。

![Image](img/note.jpg) **注意：**

Java 的未来版本将允许类似于原始类型的用户定义类型——其值不存储在对象内部。例如，原始类型具有 `double` 字段 `x` 和 `y` 的 `Point` 值仅仅是内存中的一个 16 字节块，包含两个相邻的 `double` 值。你可以复制它，但你无法拥有它的引用。

如果你需要引用，请使用自动生成的伴侣类（在目前的提案中名为 `Point.ref`）。装箱和拆箱是自动的，就像今天的原始类型一样。

在未来的某个时刻，原始包装类将与这些类统一。例如，`Double` 将成为 `double.ref` 的别名。

你经常因为另一个原因看到数字包装类。Java 的设计者发现包装类是放置某些基本方法的方便地方，例如将数字字符串转换为数字的方法。

要将字符串转换为整数，使用以下语句：

```java
int x = Integer.parseInt(s);
```

这与 `Integer` 对象无关——`parseInt` 是一个静态方法。但 `Integer` 类是一个放置它的好地方。

API 注释显示了 `Integer` 类的一些更重要的方法。其他数字类实现了对应的方法。

![Image](img/caution.jpg) **警告：**

有些人认为可以使用包装类来实现可以修改数值参数的方法。

然而，这是不对的。回想第 4 章，编写一个可以增加整数参数的 Java 方法是不可能的，因为 Java 方法的参数总是按值传递的。

```java
public static void triple(int x) // 无效
{
  x = 3 * x; // 修改了局部变量
}
```

我们可以通过使用 `Integer` 代替 `int` 来克服这一点吗？

```java
public static void triple(Integer x) // 无效
{
  . . .
}
```

问题在于 `Integer` 对象是**不可变**的：包装器内部包含的信息不能改变。你不能使用这些包装类来创建一个修改数值参数的方法。

## `java.lang.Integer` 1.0

- `int intValue()` 返回此 `Integer` 对象的值，作为 `int`（重写了 `Number` 类中的 `intValue` 方法）。
- `static String toString(int i)` 返回一个新的 `String` 对象，表示 10 进制的数字 `i`。
- `static String toString(int i, int radix)` 允许你返回由 `radix` 参数指定的基数表示的数字 `i` 表示。
- `static int parseInt(String s)`
- `static int parseInt(String s, int radix)` 返回字符串 `s` 中包含数字的整数。该字符串必须表示 10 进制整数（对于第一个方法）或 `radix` 参数指定的基数的整数（对于第二个方法）。
- `static Integer valueOf(String s)`
- `static Integer valueOf(String s, int radix)` 返回一个新的 `Integer` 对象，初始化为字符串 `s` 中包含数字的整数。该字符串必须表示 10 进制整数（对于第一个方法）或 `radix` 参数指定的基数的整数（对于第二个方法）。

## `java.text.NumberFormat` 1.1

### 5.5 变长参数方法

你经常看到提供任意数量参数的方法。这些方法有时被称为“变长参数”（varargs）。你已经见过这样的方法：`printf`。例如，以下调用：

```java
System.out.printf("%d", n);
```

和：

```java
System.out.printf("%d %s", n, "widgets");
```

都调用同一个方法，尽管一个调用有两个参数，另一个有三个。`printf` 方法定义如下：

```java
public class PrintStream
{
  public printf(String fmt, Object... args)
  {
    format(fmt, args);
  }
}
```



在这里，省略号 `...` 是 Java 代码的一部分。它表示方法可以接收任意数量的对象（除了 `fmt` 参数外）。对于 `printf` 的实现者来说，它实际上接收两个参数：格式字符串和一个包含所有参数的 `Object[]` 数组。（如果调用者提供整数或其他原始值，自动装箱将其转换为对象。）它面临的艰巨任务是扫描 `fmt` 字符串并将 `i` 个格式说明与 `args[i]` 匹配。

换句话说，对于 `printf` 的实现者，`Object...` 类型与 `Object[]` 完全相同。编译器需要在处理每个 `printf` 调用时将参数封装成数组并在必要时自动装箱：

```java
System.out.printf("%d %s", new Object[] { Integer.valueOf(1), "widgets" } );
```

你可以定义自己的变长参数方法，并且可以为参数指定任何类型，甚至是原始类型。这里有一个简单的示例：一个计算任意数量值最大值的函数。

```java
public static double max(double... values)
{
  double largest = Double.NEGATIVE_INFINITY;
  for (double v : values) if (v > largest) largest = v;
  return largest;
}
```

只需这样调用该函数：

```java
double m = max(3.1, 40.4, -5);
```

编译器向 `max` 函数传递了 `new double[] { 3.1, 40.4, -5 }`。

---

![Image](img/note.jpg) **注意：**

将数组作为变长参数方法的最后一个参数是合法的。例如：

```java
System.out.printf("%d %s", new Object[] { Integer.valueOf(1), "widgets" } );
```

因此，你可以将最后一个参数为数组的现有函数重新定义为变长参数方法，而不会破坏现有代码。例如，`MessageFormat.format` 在 Java 5 中通过这种方式得到了增强。如果你喜欢，甚至可以将 `main` 方法声明为：

```java
public static void main(String... args)
```

随着你在继承层次结构向上移动，类会变得越来越通用，可能也越来越抽象。在某个点，祖先类变得如此通用，以至于你倾向于将其视为其他类的基础，而不是你想要使用的具有特定实例的类。例如，考虑扩展我们的 `Employee` 类层次结构。员工是人，学生也是人。让我们扩展类层次结构以包含 `Person` 和 `Student` 类。图 5.2 展现了这些类之间的继承关系。

![Images](img/05fig02.jpg)

**图 5.2** `Person` 及其子类的继承关系图

### 为什么要费力实现如此层次的抽象？

有些属性对每个人来说都是合理的，例如名字。学生和员工都有名字，引入一个共同的超类允许我们将 `getName` 方法提取到继承层次结构中的更高层。

现在让我们添加另一个方法 `getDescription`，其目的是返回该人的简短描述，例如：

```text
an employee with a salary of $50,000.00

a student majoring in computer science
```

为 `Employee` 和 `Student` 类实现此方法很容易。但在 `Person` 类中你可以提供什么信息呢？`Person` 类对除了名字以外的人一无所知。当然，你可以实现 `Person.getDescription()` 返回一个空字符串。但有更好的更好的方法。如果你使用 `abstract` 关键字，你根本不需要实现该方法。

```java
public abstract String getDescription();

// no implementation required
```

为了更加清晰起见，包含一个或多个抽象方法的类本身必须声明为抽象类。

```java
public abstract class Person
{
  . . .

  public abstract String getDescription();
}
```

除了抽象方法，抽象类还可以拥有字段和具体方法。例如，`Person` 类存储了人的名字，并有一个返回它的具体方法。

```java
public abstract class Person
{
  private String name;

  public Person(String name)
  {
      this.name = name;
  }

  public abstract String getDescription();

  public String getName()
  {
      return name;
  }
}
```

![Image](img/tip.jpg) **提示：** 一些程序员没有意识到抽象类可以拥有具体方法。你应该始终将公共字段和方法（无论是否抽象）移动到父类中（无论是否抽象）。

抽象方法充当子类中实现方法的占位符。当你扩展一个抽象类时，你有两个选择。你可以部分或全部保留抽象方法的未；那么，你也必须将子类标记为抽象。或者，你可以定义所有方法，此时子类就不再是抽象的。

例如，我们将定义一个扩展抽象类 `Person` 的 `Student` 类并实现 `getDescription` 方法。`Student` 类的方法都不是抽象的，因此它不需要被声明为抽象类。

一个类即使没有抽象方法，也可以被声明为 `abstract`。

抽象类不能被实例化。也就是说，如果一个类被声明为 `abstract`，则无法创建该类的任何对象。例如，表达式

```java
new Person("Vince Vu")
```

是一个错误。然而，你可以创建具体子类的对象。

注意，你仍然可以创建抽象类的对象变量，但此类变量必须引用非抽象子类的对象。例如：

```java
Person p = new Student("Vince Vu", "Economics");
```

在这里，`p` 是抽象类型 `Person` 的变量，它引用非抽象子类 `Student` 的实例。

![Image](img/c.jpg) **C++ 注意：** 在 C++ 中，抽象方法被称为纯虚函数，并带有结尾的 `= 0`，如下：

```cpp
class Person // C++
{
public:
   virtual string getDescription() = 0;
   . . .
};
```

如果一个 C++ 类至少有一个纯虚函数，那么它就是抽象类。在 C++ 中，没有特殊的关键字来表示抽象类。

让我们定义一个扩展抽象类 `Person` 的具体子类 `Student`：

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

`Student` 类定义了 `getDescription` 方法。因此，`Student` 类中的所有方法都是具体方法，该类不再是抽象类。

Listing 5.8 所示程序定义了抽象超类 `Person` (Listing 5.8)。

```java
package abstractClasses;

import java.time.*;

public class Employee extends Person
{
    private double salary;
    private LocalDate hireDay;

    public Employee(String name, double salary, int year, int month, int day)
    {
        super(name);
        this.salary = salary;
        hireDay = LocalDate.of(year, month, day);
    }

    public double getSalary()
    {
        return salary;
    }

    public LocalDate getHireDay()
    {
        return hireDay;
    }

    public String getDescription()
    {
        return "an employee with a salary of $%.2f".formatted(salary);
    }

    public void raiseSalary(double byPercent)
    {
        double raise = salary * byPercent / 100;
        salary += raise;
    }
}
```

Listing 5.11 `abstractClasses/Student.java`

```java
package abstractClasses;

public class Student extends Person
{
    private String major;

    /**
     * @param name the student's name
     * @param major the student's major
     */
    public Student(String name, String major)
    {
        // pass name to superclass constructor
        super(name);
        this.major = major;
    }

    public String getDescription()
    {
        return "a student majoring in " + major;
    }
}
```

### 5.7 枚举类（Enumeration Classes）

你在第 3 章中看到了如何定义枚举类型。这里有一个典型的例子：

```java
public enum Size { SMALL, MEDIUM, LARGE, EXTRA_LARGE }
```

此声明定义的类型实际上是一个类。该类恰好有四个实例——无法构造新的对象。

因此，你永远不需要对枚举类型的值使用 `equals`。直接使用 `==` 来比较它们即可。

如果你愿意，，可以为枚举类型添加构造函数、方法和字段。当然，构造函数只有在枚举常量被构造时才会被调用。这是一个示例：

```java
public enum Size
{
    SMALL("S"), MEDIUM("M"), LARGE("L"), EXTRA_LARGE("XL");

    private String abbreviation;

    Size(String abbreviation) { this.abbreviation = abbreviation; }

    // 自动为 private

    public String getAbbreviation() { return abbreviation; }
}
```

枚举的构造函数总是私有的。你可以省略 `private` 修饰符，如前面的示例所示。将枚举构造函数声明为 `public` 或 `protected` 是语法错误。

所有枚举类型都是抽象类 `Enum` 的子类。它们继承了该类的许多方法。最实用的方法是 `toString`，它返回枚举常量的名称。例如，`Size.SMALL.toString()` 返回字符串 `"SMALL"`。

`toString` 的反向操作是静态方法 `valueOf`。例如，语句：

```java
Size s = Enum.valueOf(Size.class, "SMALL");
```

将 `s` 设置为 `Size.SMALL`。

每个枚举类型都有一个静态方法 `values`，它返回枚举所有值的数组。例如，调用：

```java
Size[] values = Size.values();
```

返回包含 `Size.SMALL`、`Size.MEDIUM` 和 `Size.EXTRA_LARGE` 的数组。`ordinal` 方法产生枚举常量在 `enum` 声明中的位置，从零开始。例如，`Size.MEDIUM.ordinal()` 返回 `1`。

Listing 5.12 中的短程序演示了如何使用枚举类型。

**注意：** `Enum` 类有一个类型参数，为了简单起见忽略了它。例如，枚举类型 `Size` 扩展了 `Enum<Size>`。该类型参数用于 `compareTo` 方法。（我在第 6 章中讨论了 `compareTo` 方法，在第 8 章中讨论了类型参数。）

Listing 5.12 `enums/EnumTest.java`

```java
package enums;

import java.util.*;

/**
 * 此程序演示了枚举类型。
 * @version 1.0 2004-05-24
 * @author Horstmann
 */
public class EnumTest
{
    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);

        System.out.print("Enter a size: (SMALL, MEDIUM, LARGE, EXTRA_LARGE) ");

        String input = in.next().toUpperCase();
        Size size = Enum.valueOf(Size.class, input);

        System.out.println("size=" + size);
        System.out.println("abbreviation=" + size.getAbbreviation());

        if (size == Size.EXTRA_LARGE)
            System.out.println("Good job--you paid attention to the.");
    }
}

enum Size
{
    SMALL("S"), MEDIUM("M"), LARGE("L"), EXTRA_LARGE("XL");

    private Size(String abbreviation) { this.abbreviation = abbreviation; }

    public String getAbbreviation() { return abbreviation; }

    private String abbreviation;
}
```

**`java.lang.Enum<E>`** 5

* `static Enum valueOf(Class enumClass, String name)` 返回给定类中给定名称的枚举常量。
* `String toString()` 返回此枚举常量的名称。
* `int ordinal()` 返回此枚举常量在 `enum` 声明中的零起始位置。
* `int compareTo(E other)` 如果此枚举常量在 `other` 之前则返回负整数，如果 `this == other` 则返回零，否则返回正整数。枚举的顺序由 `enum` 声明给出。

### 5.8 密封类（Sealed Classes）

除非一个类被声明为 `final`，否则任何人都可以创建它的子类。如果你想要更多控制怎么办？例如，假设你需要编写自己的 JSON 库，因为现有的库无法满足你的需求。

JSON 标准规定 JSON 值是数组、数字、字符串、布尔值、对象或空。一种明显的方法是用 `JSONArray`、`JSONNumber` 等类扩展抽象类 `JSONValue`：

```java
public abstract class JSONValue
{
    // 适用于 JSON 值的方法
}

public final class JSONArray extends JSONValue
{
    ...
}

public final class JSONNumber extends JSONValue
{
    ...
}
```

通过将 `JSONArray`、`JSONNumber` 等类声明为 `final`，我们可以确保没有人创建子类。但我们无法阻止任何人形成 `JSONValue` 的另一个子类。

为什么我们可能需要这种控制？考虑这段代码：

```java
JSONValue v = ...;

if (v instanceof JSONArray a) ...
else if (v instanceof JSONNumber n) ...
else if (v instanceof JSONString s) ...
else if (v instanceof JSOBoolean b) ...
```



```java
else if (v instanceof JSONObject o) ...

else ... // 必须是 JSONNull
```

在这里，控制流意味着我们知道 `JSONValue` 的直接子类。这不是一个开放的层次结构。JSON 标准不会改变；如果改变了，我们作为库实现者将添加第七个子类。

在 Java 中，*密封*（sealed）控制哪些类可以继承它。密封类在 Java 15 中作为预览功能引入，并在 Java 17 中定型。

以下是将 `JSONValue` 类声明为密封的方法：

```java
public abstract sealed class JSONValue
    permits JSONArray, JSONNumber, JSONString, JSONBoolean, JSONObject, JSONNull
{
    ...
}
```

定义一个非许可的子类是错误的：

```java
public class JSONComment extends JSONValue { ... } // 错误
```

这正如此，因为 JSON 不允许注释。因此，密封类允许准确地建模领域约束。

密封类的许可子类必须是可访问的。它们不能是嵌套在类中的私有类，也不能是另一个包中的包可见类。

对于允许的公共子类，规则更加严格。它们必须与密封类（sealed class）处于同一个包中。然而，如果你使用了模块（参见第二卷的第 9 章），那么它们只需要处于同一个模块中。

![Image](img/note.jpg) **注意：**

密封类可以在不带 `permits` 子句的情况下声明。这样，所有的直接子类都必须在同一个文件中声明。没有访问该文件的程序员无法创建子类。

一个文件最多可以有一个 `public` 类，因此这种安排似乎只有在子类不供公众使用时才有用。

然而，正如你将在下一章中看到的，你可以使用内部类作为公共子类。

密封类的一个重要动力源是编译时检查。考虑 `JSONValue` 类中的这个方法，它使用了带有模式匹配的 `switch` 表达式（这是 Java 17 中的一项预览功能）：

```java
public String type()
{
    return switch (this)
    {
        case JSONArray j -> "array";
        case JSONNumber j -> "number";
        case JSONString j -> "string";
        case JSONBoolean j -> "boolean";
        case JSONObject j -> "object";
        case JSONNull j -> "null";
        // No default needed here
    };
}
```

编译器可以检查出不需要 `default` 子句，因为 `JSONValue` 的所有直接子类都作为 case 出现过。

![Image](img/note.jpg) **注意：**

前面的 `type` 方法看起来并不非常面向对象。符合 OOP 精神的做法是让这六个类中的每一个都提供自己的 `type` 方法，依赖多态而不是 `switch`。对于开放的层次结构，这是一个很好的方法。但当存在一组固定的类时，将所有备选项放在一个方法中通常方便。

一眼看上去，密封类的子类似乎必须是 `final` 的。但为了穷尽性测试，我们只需要知道所有的直接子类。如果这些类还有进一步的子类，并没有问题。例如，我们可以重新组织 JSON 层次结构，如图 5.3 所示。

![Images](img/05fig03.jpg)

**图 5.3** 表示 JSON 值的类完整层次结构

在这个层次结构中，`JSONValue` 允许三个子类：

```java
public abstract sealed class JSONValue
    permits JSONObject, JSONArray, JSONPrimitive
{
    . . .
}
```

`JSONPrimitive` 类也是被密封的：

```java
public abstract sealed class JSONPrimitive extends JSONValue
    permits JSONString, JSONNumber, JSONBoolean, JSONNull
{
    . . .
}
```

密封类的子类必须指定它是 `sealed`、`final` 还是允许子类化的（open）。在后者的情况下，它必须被声明为 `non-sealed`。

![Image](img/note.jpg) **注意：**

`non-sealed` 关键字是第一个带有连字符的 Java 关键字。这很可能是未来的一个趋势。向语言中添加关键字总是伴随着风险。现有代码可能不再编译。出于这个原因，`sealed` 是一个“上下文相关”关键字。你仍然可以声明名为 `sealed` 的变量或方法：

```java
int sealed = 1; // 可以将上下文关键字作为标识符
```

对于带连字符的关键字，人们不必担心这个问题。唯一的歧义在于减法：

```java
int non = 0;

non = non-sealed; // 是减法，不是关键字
```

你为什么想要一个 `non-sealed` 子类呢？考虑一个具有六个直接子类的 XML 类：

```java
public abstract sealed class Node
    permits Element, Text, Comment, CDATASection, EntityReference,
            ProcessingInstruction
{
    . . .
}
```

我们允许 `Element` 有任意子类：

```java
public non-sealed class Element extends Node
{
    . . .
}

public class HTMLDivElement extends Element
{
    . . .
}
```

在这一节中，你学习了密封*类*。在下一章中，你将学习*接口*，它是抽象类的泛化。Java 接口也可以有子类型。密封接口的工作方式与密封类完全相同，用于控制直接子类型。

下面的示例程序充实了 JSON 层次结构。`JSONObject` 的实现使用了 `HashMap`，这将在第 9 章中介绍。在示例中，我们使用接口而不是抽象类，这样 `JSONNumber` 和 `JSONString` 就可以是 record，而 `JSONBoolean` 和 `JSONNull` 类可以是枚举。record 和枚举可以实现接口，但它们不能扩展类。

**列表 5.13** `sealed/SealedTest.java`

```java
package sealed;

import java.util.*;

sealed interface JSONValue permits JSONArray, JSONPrimitive
{
    public default type()
    {
        if (this instanceof JSONArray) return "array";
        else (this instanceof JSONObject) return "object";
        else (this instanceof JSONNumber) return "number";
        else (this instanceof JSONString) return "string";
        else (this instanceof JSONBoolean) return "boolean";
        else return "null";
    }
}

final class JSONArray extends ArrayList<JSONValue> implements JSONValue

final class JSONObject extends HashMap<String, JSONValue> implements JSONValue
{
    public String toString()
    {
        StringBuilder result = new StringBuilder();
        result.append("{");
        for (Map.Entry<String, JSONValue> entry : entrySet())
        {
            if (result.length() > 1) result.append(",");
            result.append(" ");
            result.append(entry.getKey());
            result.append("\": ");
            result.append(entry.getValue());
        }
        result.append(" }");
        return result.toString();
    }
}

sealed interface JSONPrimitive extends JSONValue
    permits JSONString, JSONNumber, JSONBoolean, JSONNull
{
}

final record JSONNumber(double value) implements JSONPrimitive
{
    public String toString() { return "" + value; }
}

final record JSONString(String value) implements JSONPrimitive
{
    public String toString() { return "\"" + value.translateEscapes() + "\""; }
}

enum JSONBoolean implements JSONPrimitive
{
    FALSE, TRUE;

    public String toString() { return super.toString().toLowerCase(); }
}

enum JSONNull implements JSONPrimitive
{
    INSTANCE;

    public String toString() { return "null"; }
}

public class SealedTest
{
    public static void main(String[] args)
    {
        JSONObject obj = new JSONObject();
        obj.put("name", new JSONString("Harry"));
        obj.put("salary", new JSONNumber(90000));
        obj.put("married", JSONBoolean.FALSE);

        JSONArray arr = new JSONArray();
        arr.add(new JSONNumber(13));
        arr.add(JSONNull.INSTANCE);

        obj.put("luckyNumbers", arr);
        System.out.println(obj);
        System.out.println(obj.type());
    }
}
```

## 5.9 反射

*反射库*为你提供了一套丰富且精密的工具集，用于编写动态操作 Java 代码的程序。通过反射，Java 可以支持用户界面生成器、对象关系映射器以及许多动态查询类能力的开发工具。

能够分析类能力的程序被称为反射式的。反射机制非常强大。正如接下来的章节所示，你可以使用它：

- 在运行时分析类的能力
- 在运行时检查对象——例如，编写一个适用于*所有*类的单个 `toString` 方法
- 实现通用的数组处理代码
- 利用类似于 C++ 等语言中函数指针的 `Method` 对象

反思是一种强大且复杂的机制；然而，它主要对工具构建者有意义，而不是对应用程序程序员。如果你感兴趣的是编写应用程序，而不是为其他 Java 程序员编写工具，那么你可以安全地跳过本章的剩余内容，稍后再回来。

### 5.9.1 `Class` 类

当你的程序运行时，Java 运行时系统始终会对所有对象维护一种所谓的*运行时类型识别*（runtime type identification）。这些信息跟踪了每个对象所属的类。运行时类型信息由虚拟机用于用于选择要执行的正确方法。

然而，你也可以通过操作一个特殊的 Java 类来访问这些信息。存储这些信息的类听起来有点令人困惑，被称为 `Class`。`Object` 类中的 `getClass()` 方法返回一个 `Class` 类型的实例。

```java
Employee e; . . .

Class cl = e.getClass();
```

就像 `Employee` 对象描述特定员工的属性一样，`Class` 对象描述了特定类的属性。`Class` 类最常用的方法可能是 `getName`。它返回类的名称。例如，语句

```java
System.out.println(e.getClass().getName() + " " + e.getName());
```

如果 `e` 是一个员工，则打印：

```text
Employee Harry Hacker
```

或者，如果 `e` 是一个经理，则打印：

```text
Manager Harry Hacker
```

如果该类在一个包中，则包名是类名的一部分：

```java
var generator = new Random();

Class cl = generator.getClass();

String name = cl.getName(); // name 被设置为 "java.util.Random"
```

你可以通过使用静态方法 `forName` 获取与类名对应的 `Class` 对象。

```java
String className = "java.util.Random";

Class cl = Class.forName(className);
```

如果类名存储在运行时会变化的字符串中，请使用此方法。如果 `className` 是类或接口的名称，该方法即可有效。否则，`forName` 方法会抛出一个*检查异常*。请参见第 5.9.2 节，“异常声明概述](#ch05.xhtml_ch5-9-2)”，第 283 页，了解每当你使用此方法时如何提供*异常处理器*。

获取 `Class` 类型对象的第三种方法是一种方便的快捷方式。如果 `T` 是任何 Java 类型（或 `void` 关键字），那么 `T.class` 就是匹配的类对象。例如：

```java
Class cl1 = Random.class; // 如果你导入了 java.util.*;

Class cl2 = int.class;

Class cl3 = Double[].class;
```

注意，`Class` 对象实际上描述的是一个*类型*，该类型可能是类，也可能不是。例如，`int` 不是一个类，但 `int.class` 仍然是一个 `Class` 类型的对象。

![Image](img/note.jpg) **注意：**

`Class` 类实际上是一个泛型类。例如，`Employee.class` 的类型是 `Class<Employee>`。我不在此纠结这个问题，因为它会使一个已经抽象的概念变得更加复杂。对于大多数实际用途，你可以忽略类型参数并使用原始 `Class` 类型进行工作。关于此问题的更多信息，请参见第 8 章。

![Image](img/caution.jpg) **警告：**

出于历史原因，`getName` 方法对数组类型返回了一些奇怪的名称：

- `Double[].class.getName()` 返回 `"[Ljava.lang.Double;"`。
- `int[].class.getName()` 返回 `"I"`。

虚拟机为每个类型管理一个唯一的 `Class` 对象。因此，你可以使用 `==` 运算符来比较类对象。例如：

```java
if (e.getClass() == Employee.class) . . .
```

如果 `e` 是 `Employee` 的实例，则测试通过。与条件 `e instanceof Employee` 不同，如果 `e` 是 `Manager` 等子类的实例，则此测试将失败。

如果你有一个 `Class` 类型的对象，可以使用它来构造类的实例。调用 `getConstructor` 方法获取一个 `Constructor` 类型的对象，然后使用 `newInstance` 方法构造实例。例如：

```java
var className = "java.util.Random"; // 或者任何其他类名

Class cl = Class.forName(className);

Object obj = cl.getConstructor().newInstance();
```



如果该类没有无参数的构造函数，`getConstructor` 方法将抛出异常。你将在[第 5.9.7 节，“调用任意方法和构造函数”](#ch05.xhtml_ch5-9-2)，第 304 页看到如何调用其他构造函数。

![Image](img/note.jpg) **注意：**

有一个已弃用的 `Class.toInstance` 方法也可以使用无参数构造函数构造实例。然而，如果构造函数抛出检查异常，该异常将在不经检查的情况下重新抛出。这违反了异常的编译时检查。相比之下，`Constructor.newInstance` 将任何构造函数异常封装在 `InvocationTargetException` 中。

![Image](img/c.jpg) **C++ 注意：**

`newInstance` 方法对应于 C++ 中的*虚构造函数*（virtual constructor）惯用法。然而，C++ 中的虚构造函数并不是语言特性，而是一种需要由专门库支持的惯用法。`Class` 类类似于 C++ 中的 `type_info`，而 `getClass` 方法等同于 `typeid` 运算符。不过，Java 的 `Class` 要灵活得多。C++ 的 `type_info` 只能揭示类型的名称，无法创建该类型的对象。

#### `java.lang.Class` 1.0

- `static Class forName(String className)` 返回表示 `className` 的 `Class` 对象。
- `Constructor getConstructor(Class... parameterTypes)` 1.1 生成描述给定参数类型的构造对象。请参见[第 5.9.7 节，“调用任意方法和构造函数”](#ch05.xhtml_ch5-9-2)，第 304 页，了解如何提供参数类型。

### `java.lang.reflect.Constructor` 1.1

- `Object newInstance(Object... params)` 构造构造函数的类的实例，并将 `params` 传递给构造函数。请参见[第 5.9.7 节，“调用任意方法和构造函数”](#ch05.xhtml_ch5-9-2)，第 304 页，了解如何提供参数。

### `java.lang.Throwable` 1.0

- `void printStackTrace()` 将 `Throwable` 对象和堆栈轨迹打印到标准错误流。

#### 5.9.2 异常声明概述

我将在第 7 章中详细介绍异常处理，在此之前你经常遇到可能会抛出异常的方法。

当运行时发生错误时，程序可以“抛出异常”。抛出异常比终止程序更灵活，因为你可以提供一个*处理器*来“捕获”并处理异常。

如果你不提供处理器，程序将终止并在控制台上打印消息，给出异常的类型。你可能在不小心使用 `null` 引用或越界数组边界时已经见过异常报告。

异常有两种：*未检查异常*和*检查异常*。对于检查异常，编译器会检查你（程序员）是否已经意识到该异常并准备好处理后果。然而，许多常见的异常（如边界错误或访问空引用）是未检查的。编译器并不期望你提供处理器——毕竟，你应该把精力花在避免这些错误上，而不是为这些错误编写处理器。

并非所有的错误都是可以避免的。即使你尽了全力仍然可能发生异常，那么大多数 Java API 都会抛出一个受检异常（checked exception）。一个例子是 `Class.forName` 方法。你无法确保具有给定名称的类存在。在第 7 章中，你将看到几种异常处理策略。现在，我只向你展示最简单的策略。

每当方法包含可能抛出受检异常的语句时，在方法名后添加 `throws` 子句。

```java
public static void doSomethingWithClass(String name)
      throws ReflectiveOperationException
{
   Class cl = Class.forName(name); // might throw exception
   do something with cl
}
```

任何调用此方法的方法也需要 `throws` 声明。这包括 `main` 方法。如果真的发生了异常，`main` 方法将带有堆栈跟踪信息终止。（你将在第 7 章中学习如何捕获异常，而不是让它们终止你的程序。）

你只需要为受检异常提供 `throws` 子句。很容易找出哪些方法抛出受检异常——每当你调用一个可能抛出受检异常的方法且你没有提供处理器时，编译器就会报错。

#### 5.9.3 资源

类通常具有关联的数据文件，例如：

- 图像和音效文件
- 带有消息字符串和按钮标签的文本文件

在 Java 中，这种关联文件被称为 `resource`（资源）。

例如，考虑一个显示消息的对话框，如图 5.4 所示。

![Images](img/05fig04.jpg)

**图 5.4** 显示图像和文本资源

当然，面板中的书名和版权年份会在书的下一个版本中更改。为了方便跟踪这些变化，我们将文本放在一个文件中，而不是将其硬编码为字符串。

但是，你应该将像 `about.txt` 这样的文件放在哪里呢？当然，简单地将其放在 JAR 文件中的其他程序文件一起是比较方便的。

`Class` 类提供了一个用于定位资源文件的有用服务。以下是必要的步骤：

1. 获取拥有资源的类的 `Class` 对象——例如，`ResourceTest.class`。
2. 某些方法，如 `ImageIcon` 类的 `getImage` 方法接受描述资源位置的 URL。然后你调用：

   ```java
   URL url = cl.getResource("about.gif");
   ```

3. 否则，使用 `getResourceAsStream` 方法获取一个用于读取文件中数据的输入流。

点在于，Java 虚拟机知道如何定位类，因此它随后可以在相同位置搜索关联的资源。例如，假设 `ResourceTest` 类位于 `resources` 包中。那么 `ResourceTest.class` 文件位于 `resources` 目录中，你将一个图标文件放在同一个目录中。

与其将资源文件存放在与类文件相同的目录中，你也可以提供一个相对路径或绝对路径，例如：

```text
data/about.txt
/corejava/title.txt
```

自动加载文件就是资源加载功能所做的一切。没有标准的方法来解释资源文件的内容。每个程序必须有自己的方式来解释其资源文件。

资源的另一个常见应用是程序的国际化。依赖语言的字符串（如消息和用户界面标签）存储在资源文件中，每个语言一个文件。在卷第二的第 7 章中讨论的`internationalization API`支持一种组织和访问这些本地化文件的标准方法。

列表 5.13 是一个演示资源加载的程序。（不用担心读取文本和显示对话框的代码——我们稍后会介绍这些细节。）编译、构建 JAR 文件并执行它：

```bash
javac resource/ResourceTest.java

jar cvfe ResourceTest.jar resources.ResourceTest \
    resources/*.class resources/*.gif resources/data/*.txt corejava/*.txt

java -jar ResourceTest.jar
```

将 JAR 文件移动到不同的目录并再次运行，以检查程序是否是从 JAR 文件而不是从当前目录读取资源文件的。

**代码列表 5.14** `resources/ResourceTest.java`

```java
 1  package resources;

 2

 3  import java.io.*;

 4  import java.net.*;

 5  import java.nio.charset.*;

 6  import javax.swing.*;

 7

 8  /**
 9    * @version 1.5 2018-03-15
10    * @author Cay Horstmann
11    */

12  public class ResourceTest
13  {
14      public static void main(String[] args) throws IOException
15      {
16        Class cl = ResourceTest.class;
17        URL url = cl.getResource("about.gif");

19        InputStream is = cl.getResourceAsStream("about.txt");

      }
}
```

#### `java.Class` 1.0

- `URL getResource(String name)` 1.1
- `InputStream getAsStream(String name)` 1.1

在与类相同的地方查找资源，然后返回你可以使用的 URL 或输入流。如果未找到资源则返回 `null`，不对 I/O 错误抛出异常。

### 5.9.4 使用反射分析类的能力

以下是反射机制检查类结构的重要部分的简要概述。

`java.lang.reflect` 中的 `Field`、`Method` 和 `Constructor` 三类分别描述字段、方法和构造方法。这三个类都有一个 `getName` 方法来返回项目的名称。`Field` 类有一个 `getType` 方法，返回一个对象（同样是 `Class` 类型），描述字段类型。`Method` 和 `Constructor` 类有报告参数的方法，`Method` 类还报告返回类型。这三个类都有一个 `getModifiers` 方法，返回一个整数，其中某些位被开启或关闭，描述使用的修饰符（如 `public` 和 `static`）。你可以使用 `Modifier` 类的静态方法来分析 `getModifiers` 返回的整数。使用 `Modifier` 类中的 `isPublic`、`isPrivate` 或 `isFinal` 方法可以判断方法或构造方法是否为 `public`、`private` 或 `final`。你只需要让 `Modifier` 类中的相应方法处理 `getModifiers` 返回的整数即可。你还可以使用 `Modifier.toString` 方法打印修饰符。

`Class` 类的 `getFields`、`getMethods` 和 `getConstructors` 方法返回该类支持的*公共*字段、方法和构造方法的数组。这包括父类的公共成员。`getDeclared` 系列方法返回包含类声明的所有私有、包级和受保护成员，以及具有包访问权限的成员（但不包括父类的成员）的数组。

列表 5.15 展示了如何打印关于类的所有信息。程序提示你输入类名，并写出类所有方法和构造方法的签名，以及所有实例字段的名称。例如，如果你输入：

```text
java.lang.Double
```

程序打印：

```java
public final class java.lang.Double extends java.lang.Number
{
    public java.lang.Double(double);
    public java.lang.Double(java.lang.String);
    public boolean equals(java.lang.Object);
    public static java.lang.String toString(double);
    public static java.lang.String toString();
    public static int hashCode(double);
    public int hashCode();
    public static double min(double, double);
    public static double max(double, double);
    public static native long doubleToRawLongBits(double);
    public static long doubleToLongBits(double);
    public static native double longBitsToDouble(long);
    public int compareTo(java.lang.Double);
    public volatile int compareTo(java.lang.Object);
    public static int compare(double, double);
    public byte byteValue();
    public short shortValue();
    public int intValue();
    public long longValue();
    public float floatValue();
    public double doubleValue();
    public static java.lang.Double valueOf(java.lang.String);
    public static java.lang.Double valueOf(double);
    public static java.lang.String toHexString(double);
    public volatile java.lang.Object resolveConstantDesc(java.lang.invoke.MethodHandles$Lookup);
    public java.lang.Double resolveConstantDesc(java.lang.invoke.MethodHandles$Lookup);
    public java.util.Optional describeConstable();
    public boolean isNaN();
    public static boolean isNaN(double);
    public static double sum(double, double);
    public boolean isInfinite();
    public static boolean isInfinite(double);
    public static boolean isFinite(double);
    public static double parseDouble(java.lang.String);
    public static final double POSITIVE_INFINITY;
    public static final double NEGATIVE_INFINITY;
    public static final double NaN;
    public static final double MAX_VALUE;
    public static final double MIN_NORMAL;
    public static final double MIN_VALUE;
    public static final int MAX_EXPONENT;
    public static final int MIN_EXPONENT;
    public static final int SIZE;
    public static final int BYTES;
    public static final java.lang.Class TYPE;
    private final double value;
    private static final long serialVersionUID;
}
```

这个程序的非凡之处在于，它能够分析 Java 解释器可以加载的任何类，而不仅仅是程序编译时可类。我们将在下一章中使用这个程序来窥探 Java 编译器自动生成的内部类。

**列表 5.15** `reflection/ReflectionTest.java`

```java
package reflection;

import java.util.*;

import java.lang.reflect.*;

/**
 * 此程序使用反射机制来打印类的所有特征。
 * @version 1.12 2021-06-15
 * @author Cay Horstmann
 */

public class ReflectionTest
{
    public static void main(String[] args)
            throws ReflectiveOperationException
    {
        // 从命令行参数或用户输入读取类名
        String name;
        if (args.length > 0) name = args[0];
        else
        {
            var in = new Scanner(System.in);
            System.out.println("输入类名 (例如 java.util.Date): ");
            name = in.next();
        }

        // 打印类的修饰符、名称和父类名（如果不是 Object）
        Class cl = Class.forName(name);



```java
String modifiers = Modifier.toString(cl.getModifiers());

if (modifiers.length() > 0) System.out.print(modifiers + " ");

if (cl.isSealed())
    System.out.print("sealed ");

if (cl.isEnum())
    System.out.print("enum " + name);
else if (cl.isRecord())
    System.out.print("record " + name);
else if (cl.isInterface())
    System.out.print("interface " + name);
else
    System.out.print("class " + name);

Class supercl = cl.getSuperclass();

if (supercl != null && supercl != Object.class)
    System.out.print(" extends " + supercl.getName());

printInterfaces(cl);
printPermittedSubclasses(cl);

System.out.print("\n{\n");

printConstructors(cl);
System.out.println();

printMethods(cl);
System.out.println();

printFields(cl);
System.out.println("}");
}

/**
 * 打印类的所有构造函数
 * @param cl 一个类
 */
public static void printConstructors(Class cl)
{
    Constructor[] constructors = cl.getDeclaredConstructors();

    for (Constructor c : constructors)
    {
        String name = c.getName();

        System.out.print("  ");

        String modifiers = Modifier.toString(c.getModifiers());

        if (modifiers.length() > 0)
            System.out.print(modifiers + " ");

        System.out.print(name + "(");

        // 打印类型
        Class[] paramTypes = c.getParameterTypes();

        for (int j = 0; j < paramTypes.length; j++)
        {
            if (j > 0)
                System.out.print(", ");

            System.out.print(paramTypes[j].getName());
        }

        System.out.println(")");
    }
}

/**
 * 打印类的所有方法
 * @param cl 一个类
 */
public static void printMethods(Class cl)
{
    Method[] methods = cl.getDeclaredMethods();

    for (Method m : methods)
    {
        Class retType = m.getReturnType();
        String name = m.getName();

        System.out.print("  ");

        // 打印修饰符、返回类型和名称
        String modifiers = Modifier.toString(m.getModifiers());

        if (modifiers.length() > 0)
            System.out.print(modifiers + " ");

        System.out.print(retType.getName() + " " + name + "(");

        // 打印参数类型
        Class[] paramTypes = m.getParameterTypes();

        for (int j = 0; j < paramTypes.length; j++)
        {
            if (j > 0)
                System.out.print(", ");

            System.out.print(paramTypes[j].getName());
        }

        System.out.println(")");
    }
}

/**
 * 打印类的所有字段
 * @param cl 一个类
 */
public static void printFields(Class cl)
{
    Field[] fields = cl.getDeclaredFields();

    for (Field f : fields)
    {
        Class type = f.getType();
        String name = f.getName();

        System.out.print("  ");

        String modifiers = Modifier.toString(f.getModifiers());

        if (modifiers.length() > 0)
            System.out.print(modifiers + " ");

        System.out.println(type.getName() + " " + name + ";");
    }
}

/**
 * 打印密封类所有允许的子类
 * @param cl 一个类
 */
public static void printPermittedSubclasses(Class cl)
{
    if (cl.isSealed())
    {
        Class<?>[] permittedSubclasses = cl.getPermittedSubclasses();

        for (int i = 0; i < permittedSubclasses.length; i++)
        {
            if (i == 0)
                System.out.print(" permits ");
            else
                System.out.print(", ");

            System.out.print(permittedSubclasses[i].getName());
        }
    }
}

/**
 * 打印类直接实现的接口
 * @param cl 一个类
 */
public static void printInterfaces(Class cl)
{
    Class<?>[] interfaces = cl.getInterfaces();

    for (int i = 0; i < interfaces.length; i++)
    {
        if (i == 0)
            System.out.print(cl.isInterface() ? " extends " : " implements ");
        else
            System.out.print(", ");

        System.out.print(interfaces[i].getName());
    }
}
```

返回一个 `Class` 对象的数组，这些对象表示参数的类型。

- `Class getReturnType()`（在 `Method` 类中）

返回表示返回类型的 `Class` 对象。

## `java.lang.reflect.RecordComponent` 16

- `String getName()`
- `Class<?> getType()`

获取此记录组件的名称和类型。

- `Method getAccessor()`

返回用于访问此记录组件的 `Method` 对象。

## `java.lang.reflect.Modifier` 1.1

- `static String toString(int modifiers)`

返回一个包含修饰符的字符串，这些修饰符对应 `modifiers` 中设置的位。

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

测试 `modifiers` 值中对应方法名中修饰符的位。

### 5.9.5 使用反射在运行时分析对象

在前面的节中，我们看到了如何找到任何对象的实例字段的名称（`names`）和类型（`types`）：

- 获取相应的 `Class` 对象。
- 在 `Class` 对象上调用 `getDeclaredFields`。

在本节中，我们将更进一步，实际上查看字段的内容（`contents`）。当然，当你编写程序时，查看名称和类型已知的对象的特定字段的内容是很容易的。但反射让你能够查看在编译时未知的对象的字段。

实现此点的关键方法是 `Field` 类中的 `get` 方法。如果 `f` 是 `Field` 类型的对象（例如，从 `getDeclaredFields` 获取的其中），并且 `obj` 是 `f` 字段所属类的实例对象，那么 `f.get(obj)` 返回一个对象，其值即为 `obj` 字段的当前值。这一切都有点抽象，所以让我们来看一个例子。

```java
var harry = new Employee("Harry Hacker", 50000, 10, 1, 1989);

Class cl = harry.getClass();

// 代表 Employee 的类对象

Field f = cl.getDeclaredField("name");

// Employee 类的 name 字段

Object v = f.get(harry);

// harry 对象的 name 字段的值，即

// String 对象 "Harry Hacker"
```

当然，你也可以设置你所获取到的值。调用 `f.set(obj, value)` 将对象 `obj` 中由 `f` 表示的字段设置为新值。

实际上，这段代码存在一个问题。由于 `name` 字段是私有字段，`get` 和 `set` 方法将抛出 `IllegalAccessException`。你只能对可访问的字段使用 `get` 和 `set`。Java 的安全机制让你发现对象拥有哪些字段，但除非你有权限，否则不会让你读取和写入这些字段的值。

反射机制的默认行为是尊重 Java 访问控制。然而，你可以通过对 `Field`、`Method` 或 `Constructor` 对象调用 `setAccessible` 方法来覆盖访问控制。例如：

```java
f.setAccessible(true); // 现在可以调用 f.get(harry)
```

`setAccessible` 方法是 `AccessibleObject` 类的方法，它是 `Field`、`Method` 和 `Constructor` 类的公共父类。此功能是调试器、持久化存储和类似机制提供的。我们将在本节稍后将其用于一个通用的 `toString` 方法。

如果未授予访问，调用 `setAccessible` 将抛出异常。访问被模块系统（第二卷第 9 节](#ch09.xhtml_ch9)）或安全管理器（第二卷第 10 节](#ch10.xhtml_ch10)）拒绝。使用安全管理器并不常见，它们自 Java 17 起已弃用。但是，从 Java 9 开始，由于 Java API 已模块化，每个程序包含模块。

例如，本节末尾的示例程序查看了 `ArrayList` 和 `Integer` 对象的内部。当你使用 Java 9 到 Java 16 运行它时，会出现以下不利的消息：

```text
WARNING: An illegal reflective access operation has occurred

WARNING: Illegal reflective access by objectAnalyzer.ObjectAnalyzer (file:/home/cay
   /books/cj11/code/v1ch05/bin/) to field java.util.ArrayList.serialVersionUID

WARNING: Please consider reporting this to the maintainers of
   objectAnalyzer.ObjectAnalyzer

WARNING: Use --illegal-access=warn to enable warnings of further illegal
   reflective access operations

WARNING: All illegal access operations will be denied in a future release
```

当你使用 Java 17 运行程序时，会发生 `InaccessibleObjectException` 异常。

为了保持程序运行，向匿名模块“开放” `java.util` 和 `Integer` 包。详情见第二卷第 9 节](#ch09.xhtml_ch9)。语法如下：

```text
java.util.ArrayList.Test
```

> **注意：** 未来的库可能会使用变量句柄（variable handles）而不是反射来进行读写。`VarHandle` 类似于 `Field`。然而，为了获取 `VarHandle`，库需要一个 `Lookup`：
>
> ```java
> public Object getFieldValue(Object obj, String fieldName, Lookup lookup)
>     throws NoSuchFieldException, IllegalAccessException
> {
>     Class<?> cl = obj.getClass();
>     Field field = cl.getDeclaredField(fieldName);
>     VarHandle handle = MethodHandles.lookupIn(cl, lookup).unreflectHandle(field);
>     return handle.get(obj);
> }
> ```



只要 `Lookup` 对象是在具有访问权限的模块中生成的，这种方法就可以。这样，一个模块可以为另一个模块提供访问私有成员的权限。

虽然我们可以这样做，但让我们来看看适用于任何类的通用 `toString` 方法（见列表 5.16）。通用 `toString` 方法使用 `getDeclaredFields` 获取所有实例字段，并使用 `setAccessible` 便利方法使所有字段可访问。对于每个字段，它获取名称和值。每个值通过递归调用 `toString` 转换为字符串。

通用 `toString` 方法需要处理一些复杂性。引用循环会导致无限递归。因此，`ObjectAnalyzer` 会跟踪已访问的对象。此外，要查看数组内部你需要不同的方法。你将在下一节学习细节。

你可以使用此 `toString` 方法查看任何对象的内部。例如，以下调用：

```java
var squares = new ArrayList<Integer>();

for (int i = 1; i <= 5; i++) squares.add(i * i);

System.out.println(new ObjectAnalyzer().toString(squares));
```

产生输出：

```text
java.util.ArrayList[elementData=class java.lang.Object[]{java.lang.Integer[value=1][][],

java.lang.Integer[value=4][][],java.lang.Integer[value=9][][],

   java.lang.Integer[value=16][][],

java.lang.Integer[value=25][][],null,null,null,null,null},size=5][modCount=5][][]
```

你可以使用这个通用 `toString` 方法来实现自己类的 `toString` 方法，如下所示：

```java
public String toString()
{
   return new ObjectAnalyzer().toString(this);
}
```

这是一种方便且无疑非常有用的方法，用于提供通用的 `toString` 方法。然而，在你对以后再也不需要实现 `toString` 感到兴奋之前，请记住，不受控访问内部实现的时代已经不多尽头了。

### 列表 5.16 `objectAnalyzer/ObjectAnalyzerTest.java`

```java
 1  package objectAnalyzer;

 2

 3  import java.util.*;

 4

 5  /**

 6    * 此程序使用反射来监控对象。

 7    * @version 1.13 2018-03-16

 8    * @author Cay Horstmann

 9    */

10  public class ObjectAnalyzerTest

11  {

12      public static void main(String[] args)

13            throws ReflectiveOperationException

14      {

15          var squares = new ArrayList<Integer>();

16          for (int i = 1; i <= 5; i++)

17            squares.add(i * i);

18          System.out.println(new ObjectAnalyzer().toString(squares));

19      }

20  }
```

### 列表 5.17 `objectAnalyzer/ObjectAnalyzer.java`

```java
 1  package objectAnalyzer;

 2

 3  import java.lang.reflect.AccessibleObject;

 4  import java.lang.reflect.Array;

 5  import java.lang.reflect.Field;

 6  import java.lang.reflect.Modifier;

 7  import java.util.ArrayList;

 8

 9  public class ObjectAnalyzer

10  {

11      private ArrayList<Object> visited = new ArrayList<>();

12

13      /**

14       * 将对象转换为列出所有字段的字符串表示形式。

15       * @param obj 一个对象

16       * @return 一个包含对象类名以及所有字段名和值的字符串

17       */

18      public String toString(Object obj)

19            throws ReflectiveOperationException

20      {

21          if (obj == null) return "null";

22          if (visited.contains(obj)) return "...";

23          visited.add(obj);

24          Class cl = obj.getClass();

25          if (cl == String.class) return (String) obj;

26          if (cl.isArray())

27          {

28              String r = cl.getComponentType() + "[]{";

29              for (int i = 0; i < Array.getLength(obj); i++)

30              {

31              if (i > 0) r += ",";

32              Object val = Array.get(obj, i);

33              if (cl.getComponentType().isPrimitive()) r += val;

34              else r += toString(val);

35              }

36              return r + "}";

37          }

38

39          String r = cl.getName();

40          // 检查此类及所有父类的字段

41          do

42          {

43            r += "[";

44            Field[] fields = cl.getDeclaredFields();

45            AccessibleObject.setAccessible(fields, true);

46            // 获取字段的名称和值

47            for (Field f : fields)

48            {

49              if (!Modifier.isStatic(f.getModifiers()))

50              {

51                if (!r.endsWith("[")) r += ",";

52                r += f.getName() + "=";

53              Class t = f.getType();

54              Object val = f.get(obj);

55              if (t.isPrimitive()) r += val;

56              else r += toString(val);

57            }

58          }

59            r += "]";

60            cl = cl.getSuperclass();

61          }

62          while (cl != null);

63

64          return r;

65      }

66  }
```

### `java.lang.reflect.AccessibleObject` 1.2

- `void setAccessible(boolean flag)` 设置或清除此可访问对象的标记，如果访问被拒绝，则抛出 `IllegalAccessException`。
- `boolean trySetAccessible()` 设置此可访问对象的标记，如果访问被拒绝，则返回 `false`。
- `boolean canAccess(Object obj)` 检查调用者是否可以通过此字段、方法或构造函数对象访问 `obj`。对于静态字段、方法或构造函数，传递 `null`。
- `static void setAccessible(AccessibleObject[] array, boolean flag)` 是一个为一组对象设置标记的便利方法。

### `java.lang.Class` 1.1

- `Field getField(String name)` 和 `Field[] getFields()` 获取给定名称的公共字段，或所有字段的数组。
- `Field getDeclaredField(String name)` 和 `Field[] getDeclaredFields()` 获取在该类中声明的给定名称字段，或所有字段的数组。

### `java.lang.reflect.Field` 1.1

- `Object get(Object obj)` 获取对象 `obj` 中由此 `Field` 对象描述的字段的值。
- `void set(Object obj, Object newValue)` 将对象 `obj` 中由此 `Field` 对象描述的字段设置为新值。

## 5.6 使用反射编写数组代码

为了实现这一点，我们需要获取新数组的长度和组件类型。我们通过调用 `Array.getLength(a)` 获取长度。`Array` 类的静态 `getLength` 方法返回数组的长度。要获取新数组的组件类型，我们需要 `Class` 类的 `getComponentType` 方法（该方法仅对代表数组的类对象定义）。相反，对于任何表示类 *C* 的 `Class` 对象，`arrayType` 方法产生表示 `C[]` 的 `Class` 对象。

反射方法的分布有时似乎有点是随意的。以下是代码：

```java
public static Object badCopyOf(Object a, int newLength)
{
    Object newArray = new Object[newLength];
    System.arraycopy(a, 0, newArray, 0, Math.min(a.length, newLength));
    return newArray;
}
```

等等，如果数组不是 `Object[]`，`badCopyOf` 将在运行时产生 `ClassCastException`。关键在于 `Array` 类的 `newInstance` 方法，它用于构造新数组。你必须向该方法提供元素的类型和所需的长度作为参数。

```java
Object newArray = Array.newInstance(componentType, newLength);
```

这听起来很有前景。以下是 `good` 代码：

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

注意，此 `copyOf` 方法可以用于扩展任何类型的数组，而不是对象数组。

```java
int[] a = { 1, 2, 3, 4, 5 };

a = (int[]) goodCopyOf(a, 10);
```

为了实现这一点，`goodCopyOf` 的参数被声明为 `Object` 类型，而不是对象数组（`Object[]`）。整数数组类型 `int[]` 可以转换为 `Object`，但不能转换为对象数组！

列表 5.18 展示了这两种方法的运行情况。请注意，对 `badcopyOf` 返回值的强制转换将抛出异常。

### 列表 5.18 `arrays/CopyOfTest.java`

```java
 1  package arrays;

 2

 3  import java.lang.reflect.*;

 4  import java.util.*;

 5

 6  /**

 7    * 此程序演示了如何使用反射操作数组。

 8    * @version 1.2 2012-05-04

 9    * @author Cay Horstmann

10    */

11  public class CopyOfTest

12  {

13      public static void main(String[] args)

14      {

15        int[] a = { 1, 2, 3 };

16        a = (int[]) goodCopyOf(a, 10);

17        System.out.println(Arrays.toString(a));

18

19        String[] b = { "Tom", "Dick", "Harry" };

20        b = (String[]) goodCopyOf(b, 10);

21        System.out.println(Arrays.toString(b));

22

23        System.out.println("The following call will generate an exception.");

24        b = (String[]) badCopyOf(b, 10);

25  }

26

27    /**

28    * 此方法尝试通过分配一个新数组并复制所有元素

29    * 来扩容数组。

30    * @param a 要扩容的数组

31    * @param newLength 新长度

32    * @return 一个包含 a 的所有元素的较大的数组。然而，返回的

33    * 数组类型为 Object[]，而不是与 a 相同的类型

34    */

35    public static Object[] badCopyOf(Object[] a, int newLength) // 没有用

36    {

37        var newArray = new Object[newLength];

38        System.arraycopy(a, 0, newArray, 0, Math.min(a.length, newLength));

39        return newArray;

40    }

41

42    /**

43    * 此方法通过分配一个相同类型的新数组并复制所有

44    * 元素来扩容数组。

45    * @param a 要扩容的数组。这可以是一个对象数组或基本类型

46    *  数组

47    * @return 一个包含 a 的所有元素的较大的数组。

48    */

49    public static Object goodCopyOf(Object a, int newLength)

50    {

51      Class cl = a.getClass();

52      if (!cl.isArray()) return null;

53      Class componentType = cl.getComponentType();

54      int length = Array.getLength(a);

55      Object newArray = Array.newInstance(componentType, newLength);

56      System.arraycopy(a, 0, newArray, 0, Math.min(length, newLength));

57      return newArray;

58    }

59  }
```




### `java.lang.Class` 1.1

- `boolean isArray()`：如果此对象表示数组类型，则返回 `true`。
- `Class<?> getComponentType()`：如果此对象表示数组类型，则返回描述组件类型的 `Class`，否则返回 `null`。
- `Class<?> arrayType()`：返回描述该对象所表示的组件类型为数组类型的 `Class`。

### `java.lang.reflect.Array` 1.1

- `static Object get(Object array, int index)`：`index` 是基本类型 `boolean`、`byte`、`char`、`double`、`int`、`long` 或 `short` 之一。这些方法返回给定数组在指定索引处存储的值。
- `static void set(Object array, int index, Object newValue)`：`newValue` 是基本类型 `boolean`、`byte`、`char`、`double`、`int`、`long` 或 `short` 之一。这些方法将新值存储在给定数组的指定索引处。
- `static int getLength(Object array)`：返回给定数组的长度。
- `static Object newInstance(Class componentType, int length)`
- `static Object newInstance(Class componentType, int[] lengths)`：返回一个具有给定类型和给定维度的新数组。

#### 5.9 调用任意方法和构造函数

在 Java 中，你可以通过反射调用任何方法。`static Object get(Object array, int index)` 中，`index` 是基本类型 `boolean`、`byte`、`char`、`double`、`int`、`long` 或 `short` 之一。这些方法返回给定数组在指定索引处存储的值。`static void set(Object array, int index, Object newValue)` 中，`newValue` 是基本类型 `boolean`、`byte`、`char`、`double`、`int`、`long` 或 `short` 之一。这些方法将新值存储在给定数组的指定索引处。`static int getLength(Object array)` 返回给定数组的长度。`static Object newInstance(Class componentType, int length)`。`static Object newInstance(Class componentType, int[] lengths)` 返回一个具有给定类型和给定维度的新数组。

在这里，`f` 是一个 `Method` 类型的对象。`invoke` 的第一个参数是 `null`，因为我们正在调用一个静态方法。

为了列出 `Math.sqrt` 函数，我们将 `f` 设置为：

```java
Math.class.getMethod("sqrt", double.class)
```

这就是 `Math` 类中一个名为 `sqrt` 且带有一个 `double` 类型参数的方法。

Listing 5.19 显示了泛型表格器的完整代码以及几次测试运行结果。

**Listing 5.19** `methods/MethodTableTest.java`

```java
package methods;

import java.lang.reflect.*;

/**
 * 此程序展示了如何通过反射调用方法
 * @version 1.2 2012-05-04
 * @author Cay Horstmann
 */
public class MethodTableTest
{
    public static void main(String[] args)
           throws ReflectiveOperationException
    {
        // 获取 square 和 sqrt 方法的指针
        Method square = MethodTableTest.class.getMethod("square", double.class);
        Method sqrt = Math.class.getMethod("sqrt", double.class);

        // 打印 x 和 y 值的表格
        printTable(1, 10, 10, square);
        printTable(1, 10, 10, sqrt);
    }

    /**
     * 返回一个数字的平方
     * @param x 一个数字
     * @return x 的平方
     */
    public static double square(double x)
    {
        return x * x;
    }

    /**
     * 打印包含某个方法的 x 值和 y 值的表格
     * @param from x 值的下界
     * @param to x 值的上限
     * @param n 表格的行数
     * @param f 一个具有 double 类型参数和 double 返回值的方法
     */
    public static void printTable(double from, double to, int n, Method f)
        throws ReflectiveOperationException
    {
        // 将方法作为表头打印
        System.out.println(f);

        double dx = (to - from) / (n - 1);

        for (double x = from; x <= to; x += dx)
        {
            double y = (Double) f.invoke(null, x);
            System.out.printf("%10.4f | %10.4f%n", x, y);
        }
    }
}
```

如此示例清楚所示，你对 `Method` 对象可以做的任何事情，就如同你对 C 语言中的函数指针（或 C# 中的委托）所做的事情一样。在 C 中一样，这种编程风格通常非常不方便，而且总是容易出错。如果用错误的参数调用方法会发生什么？`invoke` 方法会抛出一个异常。

此外，`invoke` 的参数和返回值必然是 `Object` 类型。这意味着你必须进行大量的强制类型转换。结果是，编译器失去了检查你代码的机会，因此错误只在测试期间才会出现，而那时寻找和修复错误更加繁琐。此外，使用反射来获取方法指针的代码比直接调用方法的代码要慢得多。

出于这个原因，我建议仅在绝对必要时才在自己的程序中使用 `Method` 对象。使用接口以及（从 Java 8 开始）lambda 表达式（下一章的主题）几乎总是更好的主意。特别是，我赞同 Java 开发者的观点，建议不要将 `Method` 对象用于回调函数。使用接口进行回调会导致代码运行更快，且更具维护性。

`java.lang.reflect.Method` 1.1

- `public Object invoke(Object implicitParameter, Object[] explicitParameters)`

调用此对象描述的方法，传递给定参数并返回方法产生的值。对于静态方法，将 `null` 作为隐式参数。通过使用包装类传递基本类型值。基本类型返回值必须进行解箱。

### 5.10 继承的设计提示

我想在结束本章时分享一些我在使用继承时发现非常有用的提示。

1. **将公共操作和字段放在父类中。**

   这就是为什么我们将 `name` 字段放入 `Person` 类中，而不是在 `Employee` 和 `Student` 类中重复它。

2. **不要使用保护字段。**

   某些程序员认为将大多数实例字段定义为 `protected` 是一个好主意，“以防万一”，这样子类在需要时就可以访问这些字段。然而，`protected` 机制并没有多少保护，原因有两个：首先，子类的集合是无界的——任何人都可以创建你类的子类，然后编写直接访问 `protected` 实例字段的代码，从而破坏封装。其次，在 Java 中，同一个包中的所有类都可以访问 `protected` 字段，无论它们是否是子类。

3. **使用继承来建模“是”（is-a）关系。**

   继承是一个方便的节省工具，但有时人们会过度使用。例如，假设我们需要一个 `Contractor` 类。承包工有名字和入职日期，但他们没有工资。相反，他们按小时计费。人们倾向于从 `Employee` 派出一个子类 `Contractor` 并添加一个 `hourlyWage` 字段。

   ```java
   public class Contractor extends Employee
   {
       private double hourlyWage;
   }
   ```

   但这不是一个好主意，因为现在每个承包工对象都有工资和薪金字段。你最终编写的代码会比从不继承时编写的要多。

   承包工与员工的关系未能通过“是”测试。承包工不是员工的特例。

4. **除非所有继承的方法都合理，否则不要使用继承。**

   假设我们想写一个 `Holiday` 类。显然，每个节日都是一天，且天可以用 `GregorianCalendar` 的实例来表示，因此可以使用继承。

   ```java
   class Holiday extends GregorianCalendar { . . }
   ```

   遗憾的是，节日的集合在继承的操作下是不封闭的。`GregorianCalendar` 的公共方法之一是 `add`。而 `add` 可以将节日变成平日：

   ```java
   Holiday christmas;

   christmas.add(Calendar.DAY_OF_MONTH, 12);
   ```

   因此，在此例中使用继承是不恰当的。注意，如果你扩展的是不可变类，这个问题就不会出现。假设你有一个不可变的日期类，类似于 `LocalDate`。此时形成一个 `Holiday` 子类，则没有方法可以将节日变成平日。

5. **在重写方法时不要更改预期行为。**

   替换原则不仅适用于语法，更重要的是适用于行为。当你重写方法时，不应该无理地改变它的行为。编译器无法帮助你——它无法检查你的重定义是否合理。例如，你可以通过重定义 `add` 方法来解决 `Holiday` 类中 `add` 方法的问题，可以什么都不做，或者抛出异常，或者移动下一个节日。

   然而，这种修复违反了替换原则。以下语句序列：

   ```java
   int d1 = x.get(Calendar.DAY_OF_MONTH);

   x.add(Calendar.DAY_OF_MONTH, 1);

   int d2 = x.get(Calendar.DAY_OF_MONTH);

   System.out.println(d2 - d1);
   ```

   无论 `x` 的类型是 `GregorianCalendar` 还是 `Holiday`，都应该具有预期行为。

   当然，问题正出于此。理性与不理性的人可能会对预期行为是什么展开长时间的争论。例如，某些作者认为，替换原则要求 `Manager.equals` 忽略 `bonus` 字段，因为 `Employee.equals` 忽略了它。如果这些讨论是在真空状态下进行的，它们就是毫无意义的。归根到底，重要的是你在子类中重写方法时，不要违背原始设计的意图。

### 6. 使用多态，而不是类型信息

每当你发现形如所示的代码时：

```text
if (x is of type 1)
    $$$action1(x);
else if (x is of type 2)
    $$$action2(x);
```

请考虑多态。

`action[1]` 和 `action[2]` 是否代表一个共同的概念？如果是，将该概念设为这两个类型的共同超父类或接口的方法。然后，你就可以简单地调用：

```java
x.action();
```




并让多态固有的动态分发机制来启动正确的动作。

使用使用多态方法或接口实现的代码，比使用多个类型测试的代码更容易于维护和扩展。

### 7. 不要过度使用反射。

反射机制允许你通过运行时检测字段和方法，编写出具有惊人通用性的程序。这种能力对于系统级编程非常有用，但在应用程序中通常是不合适的。反射是脆弱的——使用它时，编译器无法帮助你发现编程错误。任何错误都会运行时发现并导致异常。

你现在已经了解了 Java 如何支持面向对象编程的基础：类、继承和多态。在下一章中，我将处理两个对于有效使用 Java 至关重要的高级主题：接口和 lambda 表达式。

# 第 6 章 接口、Lambda 表达式和内部类

本章内容：

- 6.1 接口
- 6.2 Lambda 表达式
- 6.3 内部类
- 6.4 服务加载器
- 6.5 代理

你现在已经学习了类和继承，这是 Java 面向对象编程的关键概念。本章将向你展示几种常用的高级技术。尽管它们的性质并不直观，但你仍然掌握它们来完善你的 Java 工具箱。

第一种技术称为 `interfaces`（接口），它是描述类应该“做什么”的方法，而不指定它们应该“如何”做。一个类可以 `implement`（实现）一个或多个接口。每当需要符合接口时，你可以使用这些实现类的对象。在讨论完接口之后，我们将转向 `lambda expressions`，这是一种创建可以在以后某个时间执行的代码块的简洁方式。使用 lambda 表达式，你可以用优雅且简洁的方式表达使用回调或变量行为的代码。

然后我们讨论 `inner classes`（内部类）的机制。内部类在技术上有些复杂——它们被定义在其他类内部，其方法可以访问外部类的字段。当你设计协作类的集合时，内部类非常有用。

本章以讨论 `proxies`（代理）结束，代理是实现任意接口的对象。代理是一种非常特殊的构造体，用于构建系统级工具。第一次阅读时，你可以安全地跳过该节。

## 6.1 接口

在接下来的章节中，你将学习 Java 接口是什么以及如何使用它们。你还将发现， Java 的最新版本中接口已变得更加强大。

### 6.1.1 接口概念

在 Java 编程语言中，接口不是一个类，而是对想要符合接口的类的一组 `requirements`（要求）。

通常，某些服务的提供者会声明：“如果你的类符合特定的接口，那么我就执行该服务。”让我们来看一个具体的例子。`Arrays`类的 `sort` 方法承诺对对象数组进行排序，但有一个条件：对象必须属于 `implement`（实现）了 `Comparable` 接口的类。

以下是 `Comparable` 接口的内容：

```java
public interface Comparable
{
  int compareTo(Object other);
}
```

在接口中，`compareTo` 方法是 `abstract`（抽象的）——它没有实现。实现 `Comparable` 接口的类需要有一个 `compareTo` 方法，该方法必须接受一个 `Object` 参数并返回一个整数。否则，该类也是抽象的——也就是说，你无法实例化任何对象。

***

![Image](img/note.jpg) **注意：**

从 Java 5 开始，`Comparable` 接口已被增强为泛型类型。

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

你仍然可以使用不带类型参数的“原始” `Comparable` 类型。这时，`compareTo` 方法有一个类型为 `Object` 的参数，你必须手动将该 `compareTo` 方法的参数强制转换为所需的类型。我会暂时这么做，这样你就不需要同时担心两个新概念了。

***

接口的所有方法自动为 `public`（公共的）。因此，在接口中声明方法时没有必要提供 `public` 关键字。

当然，还有一个接口无法显式说明的额外要求：当调用 `x.compareTo(y)` 时，`compareTo` 方法实际上必须能够 `compare`（比较）这两个对象，并返回 `x` 或 `y` 哪个更大的指示。

在接口声明中，`compareTo` 方法没有被声明为 `public`，因为 `interface` 中的所有方法都自动是 `public`。然而，在实现接口时，你必须将该方法声明为 `public`。否则，编译器会认为该方法具有包访问权限（package access）——这是 `class` 的默认权限。编译器随后会报错，提示你正尝试提供一个限制更严格的访问权限。

我们可以通过为泛型 `Comparable` 接口提供一个类型参数来做得更好一点：

```java
class Employee implements Comparable<Employee>
{
  public int compareTo(Employee other)
  {
    return Double.compare(salary, other.salary);
  }
  . . .
}
```

注意，对 `Object` 参数那难看的强制转换已经消失了。

![Image](img/tip.jpg) **提示：**

`Comparable` 接口的 `compareTo` 方法返回一个整数。如果对象不相等，你返回负值还是正值都无所谓。这种灵活性在比较整数字段时非常有用。例如，假设每位员工都有一个唯一的整数 `id`，你想按员工 ID 排序。那么你可以简单地返回 `id - other.id`。如果第一个 ID 小于另一个，该值将是一个负值；如果它们相同，则为 `0`；否则为某个正值。然而，有一个例外：整数的范围必须足够小，以至于减法不会溢出。如果你知道 ID 不是负数，或者它们的绝对值最多为 `(Integer.MAX_VALUE - 1) / 2`，那么就是安全的。否则，调用静态方法 `Integer.compare`。

当然，减法技巧不适用于浮点数。如果两个薪水接近但不相同，差值 `salary - other.salary` 可能会舍入为 `0`。`Double.compare(x, y)` 调用仅在 `x < y` 时返回 `-1`，在 `x > y` 时返回 `1`。

![Image](img/note.jpg) **注意：**

`Comparable` 接口的文档建议 `compareTo` 方法应该与 `equals` 方法兼容。也就是说，恰当 `x.equals(y)` 时，`x.compareTo(y)` 应该为零。Java API 中大多数实现 `Comparable` 的类都遵循了这一建议。一个显著的例外是 `BigDecimal`。考虑 `x = new BigDecimal("1.0")` 和 `y = new BigDecimal("1.00")`。此时 `x.equals(y)` 为 `false`，因为数字的精度不同。但 `x.compareTo(y)` 等于零。理想情况下，它不应该是这样，但并没有明显的方法来决定哪一个应该在前面。

现在你看到了一个类为了利用排序服务必须做什么——它必须实现一个 `compareTo` 方法。这是完全理的。`sort` 方法需要某种方式来比较对象。但为什么 `Employee` 类不能在不实现 `Comparable` 接口的情况下直接提供一个 `compareTo` 方法呢？

接口之所以存在是因为 Java 编程语言是*强类型*的。在进行方法调用时，编译器需要能够检查该方法是否存在。在 `sort` 方法的某处会有类似这样的语句：

```java
if (a[i].compareTo(a[j]) > 0)
{
  // 重新排列 a[i] 和 a[j]
  . . .
}
```

编译器必须知道 `a[i]` 确实有一个 `compareTo` 方法。如果 `a` 是 `Comparable` 对象的数组，那么该方法的存在是有保证的，因为每一个实现 `Comparable` 接口的类必须提供该方法。

![Image](img/note.jpg) **注意：**

你可能认为 `Arrays` 类中的 `sort` 方法定义为接受 `Comparable[]` 数组，这样如果有人调用 `sort` 且数组元素类型没有实现 `Comparable` 接口，编译器就会报错。遗憾的是，事实并非如此。相反，`sort` 方法接受一个 `Object[]` 数组并使用笨拙的强制转换：

```java
// 标准库中使用的方法--不推荐
if (((Comparable) a[i]).compareTo(a[j]) > 0)
{
  // 重新排列 a[i] 和 a[j]
  . . .
}
```

如果 `a[i]` 不属于实现 `Comparable` 接口的类，虚拟机将抛出异常。

`Listing 6.1` 展示了排序 `Employee` 类实例数组的完整代码（`Listing 6.2`）。

**Listing 6.1** `interfaces/EmployeeSortTest.java`

```java
 1  package interfaces;
 2
 3  import java.util.*;
 4
 5  /**
 6   * 此程序演示了 Comparable 接口的使用。
 7   * @version 1.30 2004-02-27
 8   * @author Cay Horstmann
 9   */
10  public EmployeeSortTest
11  {
12    public static void main(String[] args)
13    {
14      var staff = new Employee[3];
15
16      staff[0] = new Employee("Harry Hacker", 35000);
17      staff[1] = new Employee("Carl Cracker", 75000);
18      staff[2] = new Employee("Tony Tester", 38000);
19
20      Arrays.sort(staff);
21
22      //打印所有对象的信息
23      for (Employee e : staff)
24        System.out.println("name=" + e.getName() + ",salary=" + e.getSalary());
25    }
26 }
```

**Listing 6.2** `interfaces/Employee.java`

```java
 1  package interfaces;
 2
 3  public class Employee implements Comparable<Employee>
 4  {
 5    private String name;
 6    private double salary;
 7
 8    public Employee(String name, double salary)
 9    {
10      this.name = name;
11      this.salary = salary;
12    }
13
14    public String getName()
15    {
16      return name;
17    }
18
19    public double getSalary()
20    {
21      return salary;
22    }
23
24    public void raiseSalary(double byPercent)
25    {
26      double raise = salary * byPercent / 100;
27      salary += raise;
28    }
29
30    /**
31     * 按薪水比较员工
32     * @param other 另一个员工
33     * @return 如果此员工薪水低于另一个则返回负值，如果相同则返回 0，否则返回正值。
34     */
35    public int compareTo(Employee other)
36    {
37      return Double.compare(salary, other.salary);
38    }
39 }
```

由于 `Manager` 继承 `Employee`，它实现了 `Comparable<Employee>` 而不是 `Comparable<Manager>`。如果 `Manager` 选择重写 `compareTo`，它必须准备好比较经理和员工。它不能简单地将员工强制转换为经理：

```java
class Manager extends Employee
{
    public int compareTo(Employee other)
    {
        Manager otherManager = (Manager) other; // NO
        . . .
    }
    . . .
}
```

这违反了“反对对称性”规则。如果 `x` 是 `Employee` 且 `y` 是一个 `Manager`，那么调用 `x.compareTo(y)` 不会抛出异常——它仅仅是将 `x` 和 `y` 作为员工进行比较。但反过来，`y.compareTo(x)` 则会抛出 `ClassCastException`。

这种情况与第 5 章中讨论的 `equals` 方法相同，补救办法也一样。有两种不同的场景。

如果子类对比较有不同的定义，那么你应该禁止属于不同类的对象进行比较。每个 `compareTo` 方法都应该从以下测试开始：

```java
if (getClass() != other.getClass()) throw new ClassCastException();
```

如果比较子类对象有一个通用的算法，只需在父类中提供单一的 `compareTo` 方法并将其声明为 `final` 即可。

例如，假设你想让经理无论薪水如何都比普通员工高级。其他子类如 `Executive` 和 `Secretary` 呢？如果你需要建立排序，请在 `Employee` 类中提供类似 `rank` 的方法。让每个子类重写 `rank`，并实现一个考虑 `rank` 值的单一 `compareTo` 方法。

* * *

### 6.1.2 接口的属性

接口不是类。特别是，你永远无法使用 `new` 运算符来实例化接口：

```java
x = new Comparable(. . .); // ERROR
```

然而，尽管无法构造接口对象，你仍然可以声明接口变量。

```java
Comparable x; // OK
```

接口变量必须引用实现该接口的类的对象：

```java
x = new Employee(. . .); // 只要 Employee 实现了 Comparable
```

接下来，就像你使用 `instanceof` 来检查对象是否属于特定类一样，你可以使用 `instanceof` 来检查对象是否实现了某个接口：

```java
if (anObject instanceof Comparable) { . . . }
```

就像你可以构建类的层级结构一样，你也可以扩展接口。这允许创建从高概括性到高特化性的多个接口链。例如，假设你有一个名为 `Moveable` 的接口。

```java
public interface Moveable
{
  void move(double x, double y);
}
```

然后，你可以想象有一个名为 `Powered` 的接口并扩展了它：

```java
public interface Powered extends Moveable
{
  double milesPerGallon();
}
```

虽然你不能在接口中放置实例字段，但你可以在其中提供常量。例如：

```java
public interface Powered extends Moveable
{
  double milesPerGallon();
  double SPEED_LIMIT = 95; // 一个 public static final 常量
}
```

就像接口中的方法自动是 `public` 一样，字段始终是 `public static final`。

* * *

![Image](img/note.jpg) **注意：**

将接口方法标记为 `public`、字段标记为 `public static final` 是合法的。有些程序员这样做，可能是出于习惯，也为了为了清晰。然而，Java 语言规范建议不要提供冗余的关键字，我遵循了这一建议。

* * *

虽然每个类只能有一个父类，但类可以实现多个接口。这在定义类行为时为你提供了最大的灵活性。例如，Java 语言内置了一个重要的接口，名为 `Cloneable`。（该接口在第 6.1.9 节 的“对象克隆”节中进行了详细讨论。）如果你的类实现了 `Cloneable`，`Object` 类中的 `clone` 方法将为你的类对象创建精确副本。如果你同时需要可克隆性和可比较性，只需实现这两个接口即可。用逗号分隔你想实现的接口：

```java
class Employee implements Cloneable, Comparable
```



![Image](img/note.jpg) **注意：**

`Record` 和枚举类（enumeration）不能扩展其他类（因为它们隐式地扩展了 `Record` 和 `Enum` 类）。然而，它们可以实现接口。

---

![Image](img/note.jpg) **注意：**

接口可以是 `sealed`（密封）。与密封类一样，直接子类型（可以是类或接口）必须在 `permits` 子句中声明，或者位于同一个源文件中。

---

### 6.1.3 接口与抽象类

如果你读过第 5 章中关于抽象类的章节，你可能会疑惑为什么 Java 语言的设计者要费心引入接口的概念。为什么 `Comparable` 不能简单地是一个抽象类：

```java
abstract class Comparable // 为什么不能呢
{
  public abstract int compareTo(Object other);
}
```

`Employee` 类只需要扩展这个抽象类并提供 `compareTo` 方法即可：

```java
class Employee extends Comparable // 为什么不能呢
{
  public int compareTo(Object other) { . . . }
}
```

遗憾的是，使用抽象类来表示通用属性有一个主要问题。一个类只能扩展一个类。假设 `Employee` 类已经扩展了 `Person` 类。那么它无法扩展另一个类：

```java
class Employee extends Person, Comparable // 错误
```

但它可以实现多个接口：

```java
class Employee implements Comparable // OK
```

其他编程语言，特别是 C++，允许类拥有多个父类。这种特征被称为多继承。Java 的设计者选择不支持多继承，因为这会让语言变得非常复杂（如 C++），或者降低效率（如 Eiffel）。

相反，接口在获得多继承的大部分优势的同时避免了这些复杂性。

---

![Image](img/c.jpg) **C++ 注意：**

C++ 有多继承以及随而来的问题，如虚基类、支配规则和交叉转换。很少有 C++ 程序员使用多继承，有些人认为不应该使用。其他程序员建议仅对“混合（mix-in）”风格使用多继承。在混合风格中，主基类描述对象，额外的基类提供辅助特性。这种风格类似于具有单一父类和额外接口的 Java 类。

---

你可以从 URI 或一系列字符串构建指向文件或目录的路径，例如 `Paths.get("jdk-17", "conf", "security")`。在 Java 11 中，`Path` 接口提供了等价的方法：

```java
public interface Path
{
  public static Path of(URI uri) { . . . }
  public static Path of(String first, String... more) { . . . }
  . . .
}
```

那么就不再需要 `Paths` 类了。

同样，当你实现自己的接口时，没有理由再为工具方法提供一个单独的伴类类。

从 Java 9 开始，接口中的方法可以是 `private`（私有的）。`private` 方法可以是 `static`（静态的）也可以是实例方法。由于私有方法只能在接口本身的方法中使用，因此它们的用途仅限于作为接口其他方法的辅助方法。

### 6.1.5 默认方法

你可以为任何接口方法提供 `default` 默认实现。你必须使用 `default` 修饰符来标记此类方法。

```java
public interface Comparable<T>
{
  default int compareTo(T other) { return 0; }
    // 默认情况下，所有元素都是相同的
}
```

当然，这并没有什么用，因为 `Comparable` 的任何实际实现都会重写这个方法。但在其他情况下，默认方法可能是很有用的。例如，在第 9 章中，你会看到一个用于访问数据结构中元素的 `Iterator` 接口。它声明了如下 `remove` 方法：

```java
public interface Iterator<E>
{
  boolean hasNext();
  E next();
  default void remove() { throw new UnsupportedOperationException("remove"); }
  . . .
}
```

如果你实现了一个迭代器，你需要提供 `hasNext` 和 `next` 方法。这些方法没有默认实现——它们取决于你正在遍历的数据结构。但如果你的迭代器是只读的，你就不需要担心 `remove` 方法了。

默认方法可以调用其他方法。例如，`Collection` 接口可以定义一个便利方法：

```java
public interface Collection
{
  int size(); // 一个抽象方法
  default boolean isEmpty() { return size() == 0; }
  . . .
}
```

那么，实现 `Collection` 的程序员就不需要担心实现 `isEmpty` 方法了。

---

![Image](img/note.jpg) **注意：**

Java API 中的 `Collection` 接口实际上并没有这样做。相反，有一个类 `AbstractCollection`，它实现了 `Collection` 并根据 `size` 定义了 `isEmpty`。建议集合的实现者扩展 `AbstractCollection`。那种技术已经过时了。直接实现接口中的方法即可。

---

默认方法的一个重要用途是**接口演进**（interface evolution）。以已经在 Java 中存在了多年的 `Collection` 接口为例。假设在很久以前，你提供了一个类：

```java
public class Bag implements Collection
```

稍后在 Java 8 中，接口中添加了一个 `stream` 方法。

假设 `stream` 方法不是默认方法。那么 `Bag` 类将无法编译，因为它没有实现这个新方法。在接口中添加非默认方法不是**源源兼容**（source-compatible）的。

但假设你没有重新编译该类，而简单地使用包含它的旧 JAR 文件。即使缺少该方法，该类仍然可以加载。程序仍然可以构建 `Bag` 实例，且不会发生任何坏事。（向接口添加方法是**二进制兼容**（binary compatible）的。）然而，如果程序对 `Bag` 实例调用 `stream` 方法，就会发生 `AbstractMethodError`。

将方法设为 `default` 方法解决了这两个问题。`Bag` 类将再次编译。如果在未重新编译的情况下加载类并在 `Bag` 实例上调用 `stream` 方法，则会调用 `Collection.stream` 方法。

### 6.1.6 解决默认方法冲突

如果完全相同的方法在一个接口中定义为默认方法，然后又作为父类或另一个接口的方法定义会发生什么？Scala 和 C++ 等语言对解决此类歧义有复杂的规则。幸运的是，Java 的规则简单得多。规则如下：

1. **父类胜出。** 如果父类提供了一个具体方法，具有相同名称和参数类型的默认方法将被简单忽略。
2. **接口冲突。** 如果一个接口提供了默认方法，而另一个接口包含具有相同名称和参数类型的方法（无论是否是默认方法），那么你必须通过重写该方法来解决这种冲突。

让我们看看第二条规则。考虑两个具有 `getName` 方法的接口：

```java
interface Person
{
  default String getName() { return ""; };
}

interface Named
{
  default String getName() { return getClass().getName() + "_" + hashCode(); }
}
```

如果你形成一个实现了这两个者的类会发生什么？

```java
class Student implements Person, Named { . . . }
```

该类继承了由 `Person` 和 `Named` 接口提供的两个不一致的 `getName` 方法。Java 编译器没有选择其中一个，而是报告了一个错误将其交给程序员。

```java
class Student implements Person, Named
{
  @Override
  public String getName() { return Person.super.getName(); }
  . . .
}
```

现在假设 `Named` 接口没有为 `getName` 提供默认实现：

```java
interface Named
{
  String getName();
}
```

`Student` 类可以继承来自 `Person` 的默认方法吗？这可能是合理的，但 Java 设计者决定为了统一性。只要至少有一个接口提供了实现，程序员就必须解决这种歧义。

---

![Image](img/note.jpg) **注意：**

当然，如果两个接口都没有提供默认实现，那么我们就处于 Java 8 之前的情况，没有冲突。实现类有两个选择：实现该方法，或者留空不实现。在后一种情况下，该类是抽象的。

---

我们刚刚讨论了两个接口之间的名称冲突。现在考虑一个扩展父类并实现接口的类，它从两者继承了相同的方法。例如，假设 `Person` 是一个类，`Student` 定义为：

```java
class Student extends Person implements Named { . . . }
```

在这种情况下，只有父类方法有效，任何来自接口的默认方法都被简单忽略。在我们的示例中，`Student` 继承了来自 `Person` 的 `getName` 方法，无论 `Named` 接口是否为 `getName` 提供默认实现都没有。这就是“类胜出”规则。

“类胜出”规则确保了与 Java 7 的兼容性。如果你向接口添加默认方法，它对默认方法出现之前的代码没有影响。

---

![Image](img/caution.jpg) **警告：**

你永远无法无法重定义 `Object` 类中任何方法的默认方法。例如，你不能为 `toString` 或 `equals` 定义默认方法，尽管这对于 `List` 等接口可能很有吸引力。由于“类胜出”规则的存在，此类方法永远无法胜过 `Object.toString` 或 `Object.equals`。

---

### 6.1.7 接口与回调

编程中一种常见的模式是**回调**（callback）模式。在这种模式中，你指定当特定事件发生时应该执行的操作。例如，你可能希望在点击按钮或选择菜单项时执行特定的操作。然而，由于你还没有学习过如何实现用户界面，我们将考虑一个类似但更简单的情况。

`javax.swing` 包包含一个 `Timer` 类，如果你想在每个时间间隔结束时接收通知，这个类就会非常有用。例如，如果你的程序部分包含一个时钟，你可以要求每秒通知一次，以便更新时钟。

当你构造一个定时器时，你会设置时间间隔，并告诉它每当该时间间隔结束时应该执行什么。

### 你如何告诉定时器它应该做什么？

在许多编程语言中，你提供一个定时器应周期调用的函数名称。然而，Java 标准库中的类采用了面向对象的方法。你传递某个类的对象，然后定时器会调用该对象上的其中一个方法。传递对象比传递函数更灵活，因为对象可以携带额外的信息。

当然，定时器需要知道调用哪个方法。定时器要求你指定一个实现了 `java.awt.event` 包中 `ActionListener` 接口的类对象。以下是该接口：

```java
public interface ActionListener
{
  void actionPerformed(ActionEvent event);
}
```

当时间间隔过期时，定时器会调用 `actionPerformed` 方法。

假设你想每秒打印一次消息“咚，时间是 . . .”，并伴随一声嘟声。你会定义一个实现 `ActionListener` 接口的类。然后你把任何想要执行的语句放置在 `actionPerformed` 方法内部。

```java
class TimePrinter implements ActionListener
{
  public void actionPerformed(ActionEvent event)
  {
    System.out.println("At the tone, the time is "
        + Instant.ofEpochMilli(event.getWhen()));
    Toolkit.getDefaultToolkit().beep();
  }
}
```

注意 `actionPerformed` 方法的 `ActionEvent` 参数。该参数提供了有关事件的信息，例如事件发生的时间。调用 `event.getWhen()` 返回事件时间，即自“纪元”（1970 年 1 月 1 日）以来的毫秒数。通过将其传递给静态方法 `Instant.ofEpochMilli`，我们得到了更可读的描述。

接下来，构造该类的对象并将其传递给 `Timer` 构造函数。

```java
var listener = new TimePrinter();
Timer t = new Timer(1000, listener);
```

`Timer` 构造函数的第一个参数是通知之间必须经过的时间间隔，以毫秒为单位。我们希望每秒被通知一次。第二个参数是监听器对象。

最后，启动定时器。

```java
t.start();
```

每秒都会显示类似下面的消息：

```
At the tone, the time is 2017-12-16T05:01:49.550Z
```

并伴随一声嘟声。

---

![Image](img/caution.jpg) **注意：**

确保导入了 `javax.swing.Timer`。还有一个略有不同的 `java.util.Timer` 类。

---

列表 6.3 展示了定时器及其动作监听器的工作方式。定时器启动后，程序会弹出一个对话框并等待用户点击确定按钮以停止。在程序等待用户期间，每秒都会显示一次当前时间。（如果省略对话框，程序将在 `main` 方法退出后立即终止。）

**列表 6.3** `timer/TimerTest.java`

```java
 1  package timer;
 2
 3  /**
 4     @version 1.02 2017-12-14
 5     @author Cay Horstmann
 6  */
 7
 8  import java.awt.*;
 9  import java.awt.event.*;
10  import java.time.*;
11  import javax.swing.*;
12
13  public class TimerTest
14  {
15      public static void main(String[] args)
16      {
17          var listener = new TimePrinter();
18
19          // 创建一个每秒调用一次监听器的定时器
20          var timer = new Timer(1000, listener);
21          timer.start();
22
23          // 保持程序运行直到用户选择“确定”
24          JOptionPane.showMessageDialog(null, "Quit program?");
25          System.exit(0);
26      }
27  }
28
29  class TimePrinter implements ActionListener
30  {
31    public void actionPerformed(ActionEvent event)
32    {
33      System.out.println("At the tone, the time is "
34          + Instant.ofEpochMilli(event.getWhen()));
35        Toolkit.getDefaultToolkit().beep();
36    }
37  }
```

```java
var original = new Employee("John Public", 50000);
Employee copy = original;
copy.raiseSalary(10); // Oops--也改变了原始对象
```

![Images](img/06fig01.jpg)

图 6.1 复制与克隆

如果你希望 `copy` 是一个新对象，其初始状态与 `original` 相同，但其状态可以随时间推发生变化，请使用 `clone` 方法。

```java
Employee copy = original.clone();
copy.raiseSalary(10); // OK--原始对象未改变
```




但情况并不那么简单。`clone` 方法是 `Object` 类的一个 `protected` 方法，这意味着你的代码不能简单地调用它。只有 `Employee` 类可以克隆 `Employee` 对象。这种限制是有原因的。想一想 `Object` 类是如何实现 `clone` 的。它对该对象一无所知，因此它只能进行逐字段的复制。如果对象中的所有实例字段都是数字或其他基本类型，那么复制字段就没问题。但如果对象包含对子对象的引用，那么复制字段将给你另一个指向相同子对象的引用，因此原始对象和克隆对象仍然共享某些信息。

为了直观说明，请考虑第 4 章中引入的 `Employee` 类。图 6.2 显示了当使用 `Object` 类的 `clone` 方法克隆此类 `Employee` 对象时会发生什么。正如你所看到的，默认的克隆操作是“浅”——它不会克隆被其他对象引用的对象。（图中显示了一个共享的 `Date` 对象。由于一些不明的原因，这个示例使用了 `Employee` 类的一个版本，入职日期表示为 `Date`。）

![Images](img/06fig02.jpg)

图 6.2 浅拷贝

拷贝是浅的有用吗？这取决于情况。如果原始对象和浅克隆之间共享的子对象是不可变的，那么共享就是安全的。如果子对象属于不可变类（如 `String`），这确实会发生。或者，子对象在对象的整个生命周期内可能保持不变，没有变异器触碰它，也没有方法返回它的引用。

然而，子对象通常是可变的，你必须重新定义 `clone` 方法以进行深拷贝，从而对子对象进行克隆。在我们的示例中，`hireDay` 字段是 `Date`，它是可变的，因此也必须被克隆。（出于这个原因，此示例使用 `Date` 类型的字段而不是 `LocalDate` 来演示克隆过程。如果 `hireDay` 是不可变类 `LocalDate` 的实例，则不需要采取进一步的操作。）

对于每个类，你都需要决定：

1. 默认的 `clone` 方法足够；
2. 默认的 `clone` 方法可以通过调用可变子对象的 `clone` 方法来修复；或者
3. 不应尝试使用 `clone`。

第三种选项实际上是默认选项。要选择第一种或第二种选项，类必须：

1. 实现 `Cloneable` 接口；并且
2. 使用 `public` 访问修饰符重新定义 `clone` 方法。

---

![Image](img/note.jpg) **注意：**

`clone` 方法在 `Object` 类中被声明为 `protected`，因此你的代码不能简单地调用 `anObject.clone()`。但 `protected` 方法不是可以从任何子类访问吗？每个类不都是 `Object` 的子类吗？幸运的是，受保护访问的规则更为微妙（参见第 5 章）。子类只能调用受保护的 `clone` 方法来克隆*自己的*对象。你必须重新定义 `clone` 为 `public`，以便允许任何方法克隆对象。

---

在这种情况下，`Cloneable` 接口的出现与接口的正常使用无关。特别是，它*并没有*指定 `clone` 方法——该方法是从 `Object` 类继承的。该接口仅充当标记，指示类设计者理解克隆过程。对象对克隆是非常警觉的，以至于如果一个对象请求克隆但没有实现该接口，它们就会抛出一个检查异常。

---

![Image](img/note.jpg) **注意：**

`Cloneable` 接口是 Java 提供的少数标记接口之一。（有些程序员称它们为标记接口。）回想像 `Comparable` 等接口的通常用途是确保类实现了某个特定方法或一组方法。标记接口没有方法；它的唯一目的是允许在类型查询中使用 `instanceof`：

`if (obj instanceof Cloneable) . . .`

我建议你不要在自己的程序中使用标记接口。

---

即使 `clone` 的默认（浅拷贝）实现已经足够，你仍然需要实现 `Cloneable` 接口，重新定义 `clone` 为 `public` 并调用 `super.clone()`。这里有一个示例：

```java
class Employee implements Cloneable
{
   // public 访问，更改返回类型
   public Employee clone() throws CloneNotSupportedException
   {
     return (Employee) super.clone();
   }
}
```

---

![Image](img/note.jpg) **注意：**

`clone` 方法在 `Object` 类中被声明为 `protected`，因此你的代码不能简单地调用 `anObject.clone()`。但 `protected` 方法不是可以从任何子类访问吗？每个类不都是 `Object` 的子类吗？幸运的是，受保护访问的规则更为微妙（参见第 5 章）。子类只能调用受保护的 `clone` 方法来克隆*自己的*对象。你必须重新定义 `clone` 为 `public`，以便允许任何方法克隆对象。

---

在这种情况下，`Cloneable` 接口的出现与接口的正常使用无关。特别是，它*并没有*指定 `clone` 方法——该方法是从 `Object` 类继承的。该接口仅充当标记，指示类设计者理解克隆过程。对象对克隆是非常警觉的，以至于如果一个对象请求克隆但没有实现该接口，它们就会抛出一个检查异常。

---

![Image](img/note.jpg) **注意：**

`Cloneable` 接口是 Java 提供的标记接口之一。（有些程序员称它们为标记接口。）回想像 `Comparable` 等接口的通常用途是确保类实现了某个特定方法或一组方法。标记接口没有方法；它的唯一目的是允许在类型查询中使用 `instanceof`：

`if (obj instanceof Cloneable) . . .`

我建议你不要在自己的程序中使用标记接口。

---

即使 `clone` 的默认（浅拷贝）实现已经足够，你仍然需要实现 `Cloneable` 接口，重新定义 `clone` 为 `public` 并调用 `super.clone()`。这里有一个示例：

```java
class Employee implements Cloneable
{
   // public 访问，更改返回类型
   public Employee clone() throws CloneNotSupportedException
   {
     return (Employee) super.clone();
   }
}
```

你是否应该在自己的类中实现 `clone`？如果你的客户端需要进行深拷贝，那么你可能应该这样做。有些作者认为，你应该完全避免使用 `clone`，而是实现另一个方法来实现相同的目的。我同意 `clone` 确实相当别扭，但如果你将责任转移到另一个方法，你仍然会遇到相同的问题。无论如何，克隆并没有你想象的那么常见。标准库中只有少于 5% 的类实现了 `clone`。

Listing 6.4 中的程序克隆了 `Employee` 类的实例（Listing 6.5），然后调用了两个变器方法。`raiseSalary` 方法改变 `salary` 字段的值，而 `setHireDay` 方法改变 `hireDay` 字段的状态。这两个变异都不会影响原始对象，因为 `clone` 被定义为创建深拷贝。

---

**注意：**

所有数组类型都有一个 `clone` 方法，它是公共的，而不是保护的。你可以用它创建一个包含所有元素拷贝的新数组。例如：

```java
int[] luckyNumbers = { 2, 3, 5, 7, 11, 13 };

int[] cloned = luckyNumbers.clone();

cloned[5] = 12; // 不改变 luckyNumbers[5]
```

---

**注意：**

第二卷第 2 章展示了克隆对象的另一种机制，使用 Java 的对象序列化功能。该机制易实现且安全，但效率不高。

---

**Listing 6.4** `clone/CloneTest.java`

```java
package clone;

/**
 * 此程序演示了克隆。
 * @version 1.11 2018-03-16
 * @author Cay Horstmann
 */
public class CloneTest
{
    public static void main(String[] args) throws CloneNotSupportedException
    {
        var original = new Employee("John Q. Public", 50000);
        original.setHireDay(2000, 1, 1);
        Employee copy = original.clone();
        copy.raiseSalary(10);
        copy.setHireDay(2002, 12, 31);
        System.out.println("original=" + original);
        System.out.println("copy=" + copy);
    }
}
```

**Listing 6.5** `clone/Employee.java`

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
     * 将入职日期设为给定日期。
     * @param year 入职日期的年份
     * @param month 入职日期的月份
     * @param day 入职日期的日期
     */
    public void setHireDay(int year, int month, int day)
    {
        Date newHireDay = new GregorianCalendar(year, month - 1, day).getTime();

        // 实例字段示例
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

## 6.2 Lambda 表达式

在接下来的章节中，你将学习如何使用 Lambda 表达式来定义简洁的代码块，以及如何编写消耗 Lambda 表达式。

### 6.2.1 为什么用 Lambda？

Lambda 表达式是一个可以传递的代码块，以便在稍后执行一次或多次。在介绍语法（或者说这个奇怪的名字）之前，让我们回顾一下在 Java 中何时使用过此类块。在第 6.1.7 节“接口与回调”第 326 页，你看到了如何按间隔执行工作。将工作放入 `ActionListener` 的 `actionPerformed` 方法中：

```java
class Worker implements ActionListener
{
    public void actionPerformed(ActionEvent event)
    {
        // 执行一些工作
    }
}
```

然后，当你想要重复执行这段代码时，你构造了 `Worker` 类的实例。然后将该实例提交给 `Timer` 对象。或者考虑使用自定义比较器进行排序。如果你想按长度而不是默认字典顺序排序字符串，可以将 `Comparator` 对象传递给 `sort` 方法：

```java
class LengthComparator implements Comparator<String>
{
    public int compare(String first, String second)
    {
        return first.length() - second.length();
    }
}

. .

Arrays.sort(strings, new LengthComparator());
```

`compare` 方法并没有立即调用。相反，`sort` 方法会不断调用 `compare` 方法，重新排列顺序错误的元素，直到数组排序完成。你给 `sort` 方法一段比较元素所需代码，这段代码被集成到排序逻辑中，而你可能不想重新实现它。

这两个例子有一个共同点：代码块被传递给了某人——一个定时器或 `sort` 方法。该代码块在之后的某个时间被调用。

到目前，在 Java 中给别人代码块并不容易。你不能直接传递代码块。Java 是一种面向对象的语言，因此你必须构造一个拥有所需方法的类的对象。

在其他语言中，是可以直接处理代码块的。Java 设计者长期以来一直拒绝添加这一功能。毕竟，Java 的一大优势是简单性和一致性。如果一个语言包含了每一个能让代码稍微简洁点的特性，它可能会变成不可维护的混乱局面。然而，在那些其他语言中，不仅创建线程或注册按钮点击处理器更简单，它们的大部分 API 也更简单、一致且强大。在 Java 中，可以编写接收实现特定接口对象的类似 API，但此类 API 使用起来会很糟糕。

一段时间以来，问题不是是否为函数式编程增强 Java，而是如何做。在经历了多年的实验后，才出现了一个适合 Java 的设计。在下一节中，你将看到如何在 Java 中处理代码块。

### 6.2.2 Lambda 表达式的语法

再次考虑上一节中的排序示例。我们传递了检查一个字符串是否比另一个短的代码。我们计算：

`first.length() - second.length()`

`first` 和 `second` 是什么？它们都是字符串。Java 是一种强类型语言，我们也必须指定这一点：

```java
(String first, String second) -> first.length() - second.length()
```

你刚刚看到了你的第一个 *lambda 表达式*。这样的表达式仅仅是一个代码块，加上对任何必须传递给代码的变量的说明。

为什么叫这个名字？多年前，在计算机出现之前，逻辑学家阿隆佐·丘奇（Alonzo Church）想要形式化数学函数是“可计算的”的含义。（奇怪的是，已知某些函数存在，但没有人知道如何计算它们的值。）他使用希腊字母 lambda（`λ`）来标记参数。如果他早知道 Java API，他会写成：

```text
λfirst.λsecond.first.length() - second.length()
```

---

![Image](img/note.jpg) **：：为什么用字母 `λ`？**

Church 用光字母表里的其他字母了吗？实际上，权威的《数学原理》（Principia Mathematica）使用 `^` 符号来表示自由变量，这启发了 Church 使用大写 lambda `ᴧ` 作为参数。但最后他切换到了小写版本。从那时起，带有参数变量的表达式被称为 lambda 表达式。

---

你看到的是 Java 中 lambda 表达式的一种形式：参数、`->` 箭头和一个表达式。如果代码执行的计算不符合单个表达式的写法，请像编写方法一样编写它：封装在 `{}` 中，并带有显式的 `return` 语句。例如：

```java
(String first, String second) ->
{
    if (first.length() < second.length()) return -1;
    else if (first.length() > second.length()) return 1;
    else return 0;
}
```

如果 lambda 表达式没有参数，你仍然需要提供空括号，就像无参数的方法一样：

```text
()
```




`() -> { for (int i = 100; i >= 0; i--) System.out.println(i); }`

如果 lambda 表达式的参数类型可以被推断，你可以省略它们。例如：

```
Comparator<String> comp
  = (first, second) // 等同于 (String first, String second)
  -> first.length() - second.length();
```

在这里，编译器可以推导出 `first` 和 `second` 必须是字符串，因为该 lambda 表达式被赋值了一个字符串比较器。（我们将在下一节中详细查看这种赋值。）

如果一个方法只有一个类型可推断的参数，你甚至可以省略括号：

```
ActionListener listener = event ->
   System.out.println("The time is "
     + Instant.ofEpochMilli(event.getWhen()));
   // 而不是 (event) -> . . . 或 (ActionEvent event) -> . . .
```

你永远不需要指定 lambda 表达式的返回类型。它总是从上下文中推断出来的。例如，表达式

```
(String first, String second) -> first.length() - second.length()
```

可以用于期望结果类型为 `int` 的环境。

最后，你可以使用 `var` 来表示推断出的类型。这并不常见。这种语法是为了附加注解而发明的（见第二卷第 8 章）：

```
(@NonNull var first, @NonNull var second) -> first.length() - second.length()
```

**注意：**

lambda 表达式在某些分支中返回值而在其他分支中不返回值是非法的。例如，`(int x) -> { if (x >= 0) return 1; }` 是无效的。

列表 6.6 中的程序展示了如何使用 lambda 表达式作为比较器和动作监听器。

**列表 6.6** `lambda/LambdaTest.java`

```
 1  package lambda;
 2
 3  import java.util.*;
 4  import javax.swing.*;
 5  import javax.swing.Timer;
 6
 7  /**
 8   * 此程序演示了 lambda 表达式的使用。
 9   * @version 1.0 2015-05-12
10   * @author Cay Horstmann
11   */
12  public class LambdaTest
13  {
14    public static void main(String[] args)
15    {
16      var planets = new String[] { "Mercury", "Venus", "Earth", "Mars",
17          "Jupiter", "Saturn", "Uranus", "Neptune" };
18      System.out.println(Arrays.toString(planets));
19      System.out.println("Sorted in dictionary order:");
20      Arrays.sort(planets);
21      System.out.println(Arrays.toString(planets));
22      System.out.println("Sorted by length:");
23      Arrays.sort(planets, (first, second) -> first.length() - second.length());
24      System.out.println(Arrays.toString(planets));
25
26      var timer = new Timer(1000, event ->
27          System.out.println("The time is " + new Date()));
28      timer.start();
29
30      // 保持程序运行直到用户选择 "OK"
31      JOptionPane.showMessageDialog(null, "Quit program?");
32      System.exit(0);
33    }
34  }
```

#### 6.2.3 函数式接口

正如我们讨论过的，Java 中有很多现有的接口在 ways lambda 表达式。

这种向接口的转换使得 lambda 表达式如此具有吸引力。语法简洁简单。这里是另一个例子：

```
var timer = new Timer(1000, event ->
   System.out.println("The time is "
     + Instant.ofEpochMilli(event.getWhen()));
   // 而不是 (event) -> . . . 或 (ActionEvent event) -> . . .
```

这比使用实现 `ActionListener` 的类的方案要易读得多。

事实上，转换为函数式接口是你可以在 Java 中对 lambda 表达式能做的**唯一**事情。在其他支持函数字面量的编程语言中，你可以声明如 `(String, String) -> int` 的函数类型，声明这些类型的变量，并使用变量来保存函数表达式。然而，Java 设计者决定坚持使用熟悉的接口概念，而不是向语言添加函数类型。

**注意：**

你甚至不能将 lambda 表达式赋值给 `Object` 类型的变量——`Object` 不是函数式接口。

Java API 在 `java.util.function` 包中定义了一些非常通用的函数式接口。接口之一 `BiFunction<T, U, R>` 描述了参数类型为 `T` 和 `U` 返回类型为 `R` 的函数。你可以将你的字符串比较 lambda 存储在该类型的变量中：

```
BiFunction<String, String, Integer> comp
  = (first, second) -> first.length() - second.length();
```

然而，这对于排序没有帮助。没有接受 `BiFunction` 的 `Arrays.sort` 方法。如果你以前用过函数式编程语言，可能会觉得这很奇怪。但对于 Java 程序员来说，这非常自然。像 `Comparator` 这样的接口有一个特定的目的，而不仅仅是一个具有给定参数和返回类型的方法。当你想要对 lambda 表达式某些操作时，你仍然想要记住表达式的目的，并为它有一个特定的函数式接口。

`java.util.function` 包中一个特别实用的接口是 `Predicate`：

```java
public interface Predicate<T>
{
  boolean test(T t);
  // additional default and static methods
}
```

`ArrayList` 类有一个 `removeIf` 方法，其参数是一个 `Predicate`。它专门设计用于传递一个 lambda 表达式。例如，以下语句可以从数组列表中移除所有 `null` 值：

```
list.removeIf(e -> e == null);
```

另一个有用的函数式接口是 `Supplier<T>`：

```java
public interface Supplier<T>
{
  T get();
}
```

供应商（Supplier）没有参数，并在被调用时产生一个类型为 `T` 的值。供应商被用于`惰性求`。例如，考虑以下调用：

```java
LocalDate hireDay = Objects.requireNonNullElse(day,
    new LocalDate.of(1970, 1, 1));
```

这不是最优的。我们预计 `day` 很少为 `null`，因此我们只在需要时才构造默认的 `LocalDate`。通过使用供应商，我们可以推迟计算：

```java
LocalDate hireDay = Objects.requireNonNullElseGet(day,
    () -> new LocalDate.of(1970, 1, 1));
```

`requireNonNullElseGet` 方法只在需要该值时才调用供应商。

#### 6.2.4 方法引用

有时，lambda 表达式涉及单个方法。例如，假设你只是在每次定时器事件发生时打印事件对象。当然，你可以调用：

```java
var timer = new Timer(1000, event -> System.out.println(event));
```

如果你可以直接将 `println` 方法传递给 `Timer` 构造函数，会更好。以下是实现方法：

```java
var timer = new Timer(1000, System.out::println);
```

表达式 `System.out::println` 是一个`方法引用`。它引导编译器产生函数式接口的实例，通过重写接口的单个抽象方法来调用给的方法。在这个示例中，产生了一个 `ActionListener`，其 `actionPerformed(ActionEvent e)` 方法调用了 `System.out.println(e)`。

**注意：**

和 lambda 表达式一样，方法引用并不是一个对象。当被赋值给类型为函数式接口的变量时，它会产生一个对象。

**注意：**

`PrintStream` 类中有十个重载的 `println` 方法（`System.out` 是该类的一个实例）。编译器需要根据上下文确定使用哪一个。在我们的示例中，方法引用 `System.out::println` 必须转换为一个具有如下方法的 `ActionListener` 实例：

```
void actionPerformed(ActionEvent e)
```

由于 `Object` 是 `ActionEvent` 的最佳匹配，因此从十个重载的 `println` 方法中选择了 `println(Object x)`。当 `actionPerformed` 方法被调用时，事件对象会被打印出来。

现在假设我们将相同的方法引用赋值给不同的函数式接口：

```java
Runnable task = System.out::println;
```

`Runnable` 函数式接口有一个没有参数的单个抽象方法：

```java
void run()
```

在这种情况下，选择了无参数的 `println()` 方法。调用 `task.run()` 会向 `System.out` 打印空行。

另一个例子是，假设你想忽略字母大小地对字符串进行排序。你可以传递此方法表达式：

```
Arrays.sort(strings, String::compareToIgnoreCase)
```

从这些示例中可以看出，`::` 运算符将方法名与对象或类名分开。三种变体：

1. `object::instanceMethod`
2. `Class::instanceMethod`
3. `Class::staticMethod`

在第一种变体中，方法引用等于一个 lambda 表达式，其参数传递给该方法。在 `System.out::println` 的情况下，对象是 `System.out`，该方法表达式等于 `x -> System.out.println(x)`。

在第二种变体中，第一个参数变成方法的隐式参数。例如，`String::compareToIgnoreCase` 等于 `(x, y) -> x.compareToIgnoreCase(y)`。

在第三种变体中，所有参数都传递给静态方法：`Math::pow` 等于 `(x, y) -> Math.pow(x, y)`。

表 6.1 将带你了解更多示例。

请注意，只有当 lambda 表达式的主体调用了单个方法且没有做任何其他操作时，lambda 表达式才能重写为方法引用。考虑 lambda 表达式：

```
s -> s.length() == 0
```

这里有一个方法调用。但还有一个比较操作，所以你在这里不能使用方法引用。

**注意：**

当存在多个同名的重载方法时，编译器将尝试根据上下文寻找你指的是哪一个。例如，`Math.max` 方法有两个版本，一个用于整数，一个用于 `double` 值。选择哪一个取决于上下文。就像 lambda 表达式一样，方法引用并不是孤立存在的。

**注意：**

带对象的方法引用与其等效的 lambda 表达式之间存在细微差异。考虑 `separator::equals` 方法引用。如果 `separator` 为 `null`，`separator::equals` 会立即抛出 `NullPointerException`。lambda 表达式 `x -> separator.equals(x)` 只在被调用时才会抛出 `NullPointerException`。

你可以在方法引用中捕获 `this` 参数。例如，`this::equals` 等于 `x -> this.equals(x)`。方法表达式：

```
super::instanceMethod
```

使用 `this` 作为目标并调用给定方法的父类版本。这是一个显示该机制的示例代码：

```java
class Greeter
{
  public void greet(ActionEvent event)
  {
    System.out.println("Hello, the time is " + Instant.ofEpochMilli(event.getWhen()));
  }
}

class RepeatedGreeter extends Greeter
{
  public void greet(ActionEvent event)
  {
    var timer = new Timer(1000, super::greet);
    timer.start();
  }
}
```

当 `RepeatedGreeter.greet` 方法启动时，会构造一个 `Timer`，它会在每次定时器触发时执行 `super::greet` 方法。

### 6.2.5 构造方法引用

构造方法引用与方法引用一样，只是方法名为 `new`。例如，`Person::new` 是对构造函数的引用。哪一个构造函数？取决于上下文。假设你有一个字符串列表。那么通过对每个字符串调用构造函数，你可以将其转换为 `Person` 对象的数组，调用如下：

```java
ArrayList<String> names = . . .;
Stream<Person> stream = names.stream().map(Person::new);
List<Person> people = stream.toList();
```

我们将在第二卷的第 1 章中讨论 `stream`、`map` 和 `toList` 方法的细节。现在，重要的是 `map` 方法会为列表中的每个元素调用 `Person(String)` 构造函数。如果存在多个 `Person` 构造函数，编译器会选择带有 `String` 参数的那一个，因为它从上下文中推断该构造函数是带字符串调用的。

你可以使用数组类型创建构造函数引用。例如，`int[]::new` 是带有一个参数的构造函数引用：数组的长度。它等同于 lambda 表达式 `n -> new int[n]`。

数组构造函数引用有助于克服 Java 的一个局限性。正如你在第 8 章中所看到的，无法构造一个泛型类型 `T` 的数组。（表达式 `new T[n]` 是一个错误，因为它会被“擦除”为 `new Object[n]`）。这对于库作者来说是一个问题。例如，假设我们想要一个 `Person` 对象的数组。`Stream` 接口有一个 `toArray` 方法，它返回一个 `Object` 数组：

```
Object[] people = stream.toArray();
```

但这并不令人满意。用户想要的是一个 `Person` 引用的数组，而不是 `Object` 引用的数组。stream 库通过构造函数引用解决了这个问题。将 `Person[]::new` 传递给 `toArray` 方法：

```
Person[] people = stream.toArray(Person[]::new);
```

`toArray` 方法调用此构造函数以获取正确类型的数组。然后它填充并返回该数组。

### 6.2.6 变量作用域

通常，你可以在 lambda 表达式中访问闭包方法或类的变量。考虑这个例子：

```java
public static void repeatMessage(String text, int delay)
{
    ActionListener listener = event ->
    {
        System.out.println(text);
```



`Toolkit.getDefaultToolkit().beep();`

```
};

new Timer(delay, listener).start();
```

考虑一个调用：

```
repeatMessage("Hello", 1000); // 每 1000 毫秒打印一次 Hello
```

现在看 lambda 表达式内部的变量`text`。注意，这个变量在 lambda 表达式中*并没有*定义。相反，它是`repeatMessage`方法的参数变量。

如果你仔细考虑，这里发生了一些非显而易见的事情。lambda 表达式的代码可能在`repeatMessage`返回且参数变量消失很久之后仍在运行。`text`变量是如何保持状态的？

为了理解发生了什么，我们需要完善对 lambda 表达式的理解。一个 lambda 表达式包含三个要素：

1. 一个代码块
2. 参数
3. *自由*变量的值——即既不是参数也没有在代码内部定义的变量

在我们的例子中，lambda 表达式有一个自由变量`text`。表示该 lambda 表达式的数据结构必须存储自由变量的值——在我们的例子中，就是字符串`"Hello"`。我们称这些值被 lambda 表达式*捕获*（captured）了。（具体如何实现是其实现细节。例如，可以将 lambda 表达式转换成一个只有一个方法的对象，这样自由变量的值就会被复制到该对象的实例变量中。）

***

![Image](img/note.jpg) **注意：**

代码块连同自由变量值在一起的专业术语是*闭包*（closure）。如果有人炫耀他们的语言拥有闭包，请放心，Java 也有。在 Java 中，lambda 表达式就是闭包。

***

正如你所见，lambda 表达式可以捕获外部作用域中变量的值。在 Java 中，为了确保捕获的值是有定义的，有一个重要的限制。在 lambda 表达式中，你只能引用值不会改变的变量。例如，以下代码是非法的：

```java
public static void countDown(int start, int delay)
{
    ActionListener listener = event ->
    {
        start--; // 错误：不能修改捕获变量
        System.out.println(start);
    };
    new Timer(delay, listener).start();
}
```

这种限制是有的。当多个动作并发执行时，在 lambda 表达式中修改变量是不安全的。对于我们目前看到的动作类型不会发生这种情况，但通常情况下这是一个严重的问题。关于这个重要问题的更多信息，请参见第 12 章。

在 lambda 表达式中引用外部被修改的变量也是非法的。例如，以下代码是非法的：

```java
public static void repeat(String text, int count)
{
    for (int i = 1; i <= count; i++)
    {
        ActionListener listener = event ->
        {
            System.out.println(i + ": " + text);
            // 错误：无法引用变化的 i
        };
        new Timer(1000, listener).start();
    }
}
```

规则是，lambda 表达式中的任何捕获变量必须是*有效最终的*（effectively final）。有效最终变量是指在初始化后从没有被赋值过新值的变量。在我们的例子中，`text`始终指向同一个`String`对象，捕获它是可以的。然而，`i`的值被修改了，因此`i`不能被捕获。

表 6.2 列出了 Java API 提供的最重要的函数式接口。在这种情况下，我们可以使用`Runnable`接口：

```java
public static void repeat(int n, Runnable action)
{
    for (int i = 0; i < n; i++) action.run();
}
```

现在让我们这个例子变得稍微复杂一点。我们想告知操作是在哪一次迭代中执行的。为了实现，我们需要选择一个具有`int`参数和`void`返回值的函数式接口。处理`int`值的标准接口是：

```java
public interface IntConsumer
{
  void accept(int value);
}
```

这是`repeat`方法的改进后的版本：

```java
public static void repeat(int n, IntConsumer action)
{
  for (int i = 0; i < n; i++) action.accept(i);
}
```

下面是调用它的方式：

```java
repeat(10, i -> System.out.println("Countdown: " + (9 - i)));
```

表 6.3 列出了针对原始类型`int`、`long`和`double`的 34 种特化类型。正如你在第 8 章中所看到的，使用这些特化类型比通用接口更高效。因此，在上节的示例中，我使用了`IntConsumer`而不是`Consumer<Integer>`。

**表 6.3** 原始类型的函数式接口 *p*, *q* 是`int`、`long`、`double`；*P*, *Q* 是`Int`、`Long`、`Double`

![Images](img/06tab03.jpg)

***

![Image](img/tip.jpg) **提示：**

尽可能使用来自表 6.2 或表 6.3 的接口。例如，假设你写了一个方法来处理符合特定标准的文件。有一个遗留接口`java.io.FileFilter`，但使用标准的`Predicate<File>`更好。唯一不做的理由除非你已经有很多产生`FileFilter`实例的有用方法。

***

![Image](img/note.jpg) **注意：**

大多数标准函数式接口都拥有非抽象方法，用于生成或组合函数。例如，`Predicate.isEqual(a)`等同于`a::equals`，但当`a`为`null`时它也有效。存在默认方法`and`、`or`、`negate`用于组合谓词。例如，`Predicate.isEqual(a).or(Predicate.isEqual(b))`等同于`x -> a.equals(x) || b.equals(x)`。

***

![Image](img/note.jpg) **注意：**

如果你设计了一个只有一个抽象方法的接口，可以给它标记上`@FunctionalInterface`注解。这有两个优点：如果你不小心添加了另一个抽象方法，编译器会给出错误信息；而且 javadoc 页面会包含一条声明，说明你的接口是一个函数式接口。

并不是强制使用该注解。任何具有单个抽象方法的接口根据定义都是一个函数式接口。但使用`@FunctionalInterface`注解是一个好主意。

***

![Image](img/note.jpg) **注意：**

有些程序员喜欢方法调用链，例如：

```java
String input = " 618970019642690137449562111 ";
boolean isPrime = input.strip().transform(BigInteger::new).isProbablePrime(20);
```

`String`类的`transform`方法（Java 12 中引入）将`Function`应用于字符串并产生结果。你完全可以写：

```java
boolean prime = new BigInteger(input.strip()).isProbablePrime(20);
```

但这样你的眼睛就会从内向外、从左到右跳跃以寻找先发生了什么后发生了什么：调用`strip`，然后构造`BigInteger`，最后测试它是否为可能的素数。

我不确定眼睛从内向外、从左到右跳跃是一个大问题。但如果你喜欢链式方法调用从左到右的有序序列，那么`transform`就是你的朋友。

遗憾的是，它只适用于字符串。为什么`Object`类中没有`transform(java.util.function.Function)`方法呢？

Java API 设计者们不够快。他们只有一次机会把这件事做好——在 Java 8，当`java.util.function.Function`接口被添加到 API 时。在此之前，没有人能为自己的类添加`transform(java.util.function.Function)`方法。但在 Java 12，已经太晚了。某处的某人已经在他们的类中定义了含义完全不同的`transform(java.util.function.Function)`。诚然，这不太可能发生过，但无法得知。

这就是 Java 的工作方式。它严肃对待承诺，不会为了方便而违背承诺。

***

### 6.2.8 关于 Comparator 的更多信息

`Comparator`接口有许多方便的静态方法用于创建比较器。这些方法旨在与 lambda 表达式或方法引用配合使用。

静态`comparing`方法接收一个“键提取”函数，该函数将类型`T`映射到可比较的类型（如`String`）。该函数应用于要比较的对象，然后在返回的键上比较。例如，假设你有一个`Person`对象数组。以下是如何按名称对它们进行排序：

```java
Arrays.sort(people, Comparator.comparing(Person::getName));
```

这显然比手动实现`Comparator`要容易得多。而且代码更清晰，因为很明显我们想按名称比较人。

你可以使用`thenComparing`方法链式调用比较器来打破平局。例如：

```java
Arrays.sort(people,
      Comparator.comparing(Person::getLastName)
      .thenComparing(Person::getFirstName));
```

如果两个人的姓氏相同，则使用第二个比较器。

这些方法有几种变体。你可以指定一个比较器，用于`comparing`和`thenComparing`方法提取的键。例如，在这里我们按名字的长度对人排序：

```java
Arrays.sort(people, Comparator.comparing(Person::getName,
  (s, t) -> Integer.compare(s.length(), t.length())));
```

此外，`comparing`和`thenComparing`方法都有变体，可以避免`int`、`long`或`double`的装箱。产生上述操作更简单的方法是：

```java
Arrays.sort(people, Comparator.comparingInt(p -> p.getName().length()));
```

如果你的键函数可以返回`null`，你会喜欢`nullsFirst`和`nullLast`适配器。这些静态方法接收一个现有的比较器并对其修改，使其在遇到`null`时不会抛出异常，而是将其排名比普通值更小或更大。例如，假设`getMiddleName`在人没有中间名时返回`null`。那么你可以使用`Comparator.comparing(Person::getMiddleName, Comparator.nullsFirst(...))`。

`nullsFirst`方法需要一个比较器——在这种情况下，是一个比较两个字符串的比较器。`naturalOrder`方法为任何实现`Comparable`的类创建一个比较器。`Comparator<String>naturalOrder()`就是我们需要的。这里是按可能的中间名排序的完整调用。我使用了`java.util.Comparator.*`的静态导入，使表达式更具可读性。注意`naturalOrder`的类型是推断的。

```java
Arrays.sort(people, comparing(Person::getMiddleName, nullsFirst(naturalOrder())));
```

静态`reverseOrder`方法给出自然顺序的反序。要反转任何比较器，使用`reversed`实例方法。例如，`naturalOrder().reversed()`等于`reverseOrder()`。

### 6.3 内部类

*内部类*是定义在类内部的类。为什么你想这样做？有两个原因：

- 内部类可以对同包中的其他类隐藏。
- 内部类方法可以访问其定义作用域的数据——包括本应是私有的数据。

内部类以前非常用于简洁地实现回调，但现在 lambda 表达式表现得更好。尽管如此，内部类对于组织代码仍然非常有用。接下来的章节将带你了解所有细节。

C++ 拥有`嵌套类`（nested classes）。嵌套类包含在所属类的作用范围内。这里是一个典型的示例：一个链表类定义了一个类来持有链接，并定义了一个类来定义迭代器位置。

```cpp
class LinkedList
{
public:
   class Iterator // 一个嵌套类
   {
    public:
      void insert(int x);
      int erase();
      . . .
    private:
      Link* current;
      LinkedList* owner;
   };
   . . .
private:
   Link* head;
   Link* tail;
};
```

嵌套类与 Java 的内部类（inner classes）相似。然而，Java 的内部类有一个额外特性，使得它们比 C++ 的嵌套类更丰富、更有用。内部类对象对实例化它的外部类对象有一个隐式引用。通过这个指针，它可以访问外部对象的完整状态。例如，在 Java 中，`Iterator`类不需要指向它所属的`LinkedList`类的显式指针。

在 Java 中，`static`内部类没有这个额外的指针。它们是 C++ 嵌套类的 Java 对应物。

***

### 6.3.1 使用内部类访问对象状态

内部类的语法相当复杂。因此，我提供了一个简单但稍显人为的示例来演示内部类的用法。让我们重构`TimerTest`示例并提取出一个`TalkingClock`类。一个报时钟通过两个参数构造：公告之间的间隔以及一个开启或关闭蜂鸣的标志。

```java
public class TalkingClock
{
   private int interval;
   private boolean beep;

   public TalkingClock(int interval, boolean beep) { . . . }
   public void start() { . . . }

   public class TimePrinter implements ActionListener
      // 一个内部类
   {
   . . .
   }
}
```

注意，`TimePrinter`类现在位于`TalkingClock`类内部。这*并不意味着*每个`TalkingClock`都有一个`TimePrinter`实例字段。正如你所看到的，`TimePrinter`对象是通过`TalkingClock`类的方法构造的。

这里是更详细的`TimePrinter`类。注意`actionPerformed`方法在发出蜂鸣声之前会检查`beep`标志。

```java
public class TimePrinter implements ActionListener
{
   public void actionPerformed(ActionEvent event)
   {
      System.out.println("At the tone, the time is "
          + Instant.ofEpochMilli(event.getWhen()));
      if (beep) Toolkit.getDefaultToolkit().beep();
   }
}
```

发生了一些令人惊奇的事情。`TimePrinter`类没有名为`beep`的实例字段或变量。相反，`beep`指向创建这个`TimePrinter`的`TalkingClock`对象的字段。正如你所看到的，内部类方法可以访问它自己的实例字段*以及*创建它的外部对象的字段。

为了实现这一点，内部类对象总是获得一个创建它的对象的隐式引用（参见图 6.3）。

这个引用在内部类的定义中是不可见的。然而，为了解释这个概念，我们将指向外部对象的引用称为`outer`。那么`actionPerformed`方法等同于以下代码：

```java
public void actionPerformed(ActionEvent event)
{
   System.out.println("At the tone, the time is "
       + Instant.ofEpochMilli(event.getWhen()));
```



```java
if (outer.beep) Toolkit.getDefaultToolkit().beep();
```

外部类引用是在构造函数中设置的。编译器修改所有内部类构造函数，添加一个用于外部类引用的参数。`TimePrinter` 类没有定义构造函数；因此，编译器合成了一个无参数构造函数，生成类似如下的代码：

![Images](img/06fig03.jpg)

**图 6.3** 内部类对象有一个外部类对象的引用。

```java
public TimePrinter(TalkingClock clock) // 自动生成的代码
{
   outer = clock;
}
```

再次，请注意 `outer` 不是 Java 关键字。我们只是用它来说明内部类涉及的机制。

在 `start` 方法中构造 `TimePrinter` 对象时，编译器将当前报时钟的 `this` 引用传递给构造函数：

```java
var listener = new TimePrinter(this); // 自动添加参数
```

Listing 6.7 显示了内部类的完整程序。再次查看访问控制。如果 `TimePrinter` 类是一个普通类，它将需要通过 `TalkingClock` 类的公共方法来访问 `beep` 标志。使用内部类是一种改进。不需要提供仅对其他类感兴趣的访问器。

> **注意：** 我们可以将 `TimePrinter` 类声明为 `private`。这样只有 `TalkingClock` 方法能够构造 `TimePrinter` 对象。只有内部类可以是私有的。普通类只有包级或公共访问权限。

**Listing 6.7** `innerClass/InnerTest.java`

```java
package innerClass;

import java.awt.*;
import java.awt.event.*;
import java.time.*;
import javax.swing.*;

/**
 * 程序演示了内部类的用法。
 * @version 1.1 2017-12-14
 * @author Horstmann
 */
public class InnerTest
{
   public static void main(String[] args)
   {
      var clock = new TalkingClock(1000, true);
      clock.start();

      // 保持程序运行直到用户选择 "OK"
      JOptionPane.showMessageDialog(null, "Quit?");
      System.exit(0);
   }
}

/**
 * 一个按固定间隔打印时间的闹钟。
 */
class TalkingClock
{
   private int interval;
   private boolean beep;

   /**
    * 构造一个报时钟
    * @param interval 消息之间的间隔（毫秒）
    * @param beep 如果闹钟应该蜂鸣则为 true
    */
   public TalkingClock(int interval, boolean beep)
   {
      this.interval = interval;
      this.beep = beep;
   }

   /**
    * 启动闹钟。
    */
   public void start()
   {
      var listener = new TimePrinter();
      var timer = new Timer(interval, listener);
      timer.start();
   }

   public class TimePrinter implements ActionListener
   {
      public void actionPerformed(ActionEvent event)
      {
         System.out.println("At the tone, the time is "
             + Instant.ofEpochMilli(event.getWhen()));

         if (beep) Toolkit.getDefaultToolkit().beep();
      }
   }
}
```

### 6.3.2 内部类的特殊语法规则

在上一节中，我们通过将其称为 `outer` 解释了内部类的外部类引用。实际上，外部引用的正确语法稍微复杂一点。表达式

```java
OuterClass.this
```

表示外部类引用。例如，你可以这样写 `TimePrinter` 内部类的 `actionPerformed` 方法：

```java
public void actionPerformed(ActionEvent event)
{
   . . .
   if (TalkingClock.this.beep) Toolkit.getDefaultToolkit().beep();
}
```

相反，你可以使用语法更显式地编写内部对象构造函数：

```java
outerObject.new InnerClass(construction parameters)
```

例如：

```java
ActionListener listener = this.new TimePrinter();
```

在这里，新构造的 `TimePrinter` 对象的外部类引用被设置为创建内部类对象的方法的 `this` 引用。这是最常见的情况。像一常一样，`this.` 修饰符是多余的。然而，也可以通过显式命名来将外部类引用设置为另一个对象。例如，由于 `TimePrinter` 是公共的内部类，你可以为任何报时钟构造一个 `TimePrinter`。

```java
var jabberer = new TalkingClock(1000, true);
TalkingClock.TimePrinter listener = jabberer.new TimePrinter();
```

注意，当在外部类的作用域之外引用内部类时，应使用如下格式：

```java
OuterClass.InnerClass
```

> **注意：**
>
> 在内部类中声明的任何静态字段必须是 `final` 的，并用编译时常量进行初始化。如果该字段不是常量，它可能不是唯一的。
>
> 内部类不能有 `static` 方法。Java 语言规范并未为这种限制给出任何理由。本可以允许那些只访问外部类中静态字段和方法的静态方法。显然，语言设计者认为这种复杂性超过了其带来的益处。

### 6.3.3 内部类有用吗？真的必要吗？安全吗？

当内部类在 Java 1.1 中引入 Java 语言时，许多程序员认为它们是一项重大的新特性，而且这违背了 Java 旨在比 C++ 更简单”的哲学。内部类的语法无疑是复杂的（在我们章稍后学习匿名内部类时，它会变得更加复杂）。目前还不清楚内部类如何与语言的其他特性（如访问控制和安全）相互作用。

内部类被翻译成普通的类文件，并用 `$`（美元符号）分隔外部类和内部类名。例如，`TalkingClock` 类内部的 `TimePrinter` 类被翻译为类文件 `TalkingClock$TimePrinter.class`。要此效果，请尝试以下实验：运行第 5 章中的 `ReflectionTest` 程序，并给它类 `TalkingClock$TimePrinter` 以进行反射。或者，只需简单地使用 `javap` 工具：

```bash
javap -private ClassName
```

> **注意：**
>
> 如果你使用 UNIX，记住在命令行上提供类名时要转义 `$` 字符。也就是说，运行 `ReflectionTest` 或 `javap` 程序如下：

```bash
java --classpath .:../v1ch05 reflection.ReflectionTest \
   innerClass.TalkingClock\$TimePrinter
```

或者：

```bash
javap -private innerClass.TalkingClock\$TimePrinter
```

你将得到以下输出：

```java
public class innerClass.TalkingClock$TimePrinter
     implements java.awt.event.ActionListener
{
  final innerClass.TalkingClock this$0;

  public innerClass.TalkingClock$TimePrinter(innerClass.TalkingClock);

  public void actionPerformed(java.awt.event.ActionEvent);
}
```

你可以清楚地看到，编译器为指向外部类的引用生成了一个额外的实例字段 `this$0`。（`this$0` 的名称是编译器合成的——你不能在代码中引用它。）你还可以看到构造函数接收的 `TalkingClock` 参数。

如果编译器可以自动完成这种转换，你难道不能直接手动编写相同的机制吗？让我们试一下。我们将 `TimePrinter` 变成一个普通类，放在 `TalkingClock` 类之外。在构造 `TimePrinter` 对象时，我们将创建该对象的对象的 `this` 引用传递给它。

```java
class TalkingClock
{
  . . .

  public void start()
  {
      var listener = new TimePrinter(this);
      var timer = new Timer(interval, listener);
      timer.start();
  }
}

class TimePrinter implements ActionListener
{
  private TalkingClock outer;
  . . .

  public TimePrinter(TalkingClock clock)
  {
      outer = clock;
  }
}
```

现在让我们来看 `actionPerformed` 方法。它需要访问 `outer.beep`。

```java
if (outer.beep) . . . // 错误
```

在这里我们遇到了问题。内部类可以访问外部类的私有数据，但我们的外部 `TimePrinter` 类不能。

因此，内部类确实比普通类更强大，因为它们拥有更多的访问权限。

你可能很好奇内部类是如何获得这些额外访问权限的。在 Java 11 之前，内部类纯粹是`编译器`的一种现象，虚拟机对它们没有任何特殊知识。在那些日子，使用 `ReflectionTest` 程序或 `javap` 配合 `-private` 选项监视 `TalkingClock` 类显示：

```java
class TalkingClock
{
  private int interval;
  private boolean beep;

  public TalkingClock(int, boolean);

  static boolean access$0(TalkingClock); // Java 11 之前

  public void start();
}
```

注意编译器添加到外部类的静态方法 `access$0`。它返回作为参数传递的对象的 `beep` 字段。（方法名可能略有不同，例如 `access$000`，取决于编译器。）

这是一个潜在的安全风险，并让分析类文件的工具变得变得复杂。从 Java 11 开始，虚拟机理解类之间的嵌套关系，不再生成这些访问方法。

#### 6.3.4 局部内部类

如果你仔细查看 `TalkingClock` 示例的代码，你会发现你只需要一次 `TimePrinter` 类型名称：即在 `start` 方法中创建该类型的对象时。

在这种情况下，你可以`在单个方法中本地定义`类。

```java
public void start()
{
  class TimePrinter implements ActionListener
  {
      public void actionPerformed(ActionEvent event)
      {
          System.out.println("At the tone, the time is "
              + Instant.ofMilli(event.getWhen()));

          if (beep) Toolkit.getDefaultToolkit().beep();
      }
  }

  var listener = new TimePrinter();
  var timer = new Timer(interval, listener);
  timer.start();
}
```

局部类永远没有修饰符（即 `public` 或 `private`）。它们的作用域仅限于声明所在的块。

### 6.3.5 访问外部方法的变量

局部类相比于内部类有另一个优势。它们不仅可以访问外部的字段，甚至可以访问局部变量！但是，这些局部变量必须是*有效最终的*（effectively final）。这意味着它们一旦被赋值就不会改变。

这是一个典型的例子。让我们 `interval` 和 `beep` 参数从 `TalkingClock` 构造函数移动到 `start` 方法中。

```java
public void start(int interval, boolean beep)
{
  class TimePrinter implements ActionListener
  {
      public void actionPerformed(ActionEvent event)
      {
          System.out.println("At the tone, the time is "
              + Instant.ofMilli(event.getWhen()));

          if (beep) Toolkit.getDefaultToolkit().beep();
      }
  }

  var listener = new TimePrinter();
  var timer = new Timer(interval, listener);
  timer.start();
}
```

注意，`TalkingClock` 类不再需要存储 `beep` 实例字段。它直接引用 `start` 方法的 `beep` 参数变量。

也许这并不意外。毕竟这行

```java
if (beep) . . .
```

最终仍然位于 `start` 方法内部，所以为什么它不能访问 `beep` 变量的值呢？

为了理解为什么这里有一个微妙的问题，让我们仔细仔细一下控制流。

1. `start` 方法被调用。
2. 对象变量 `listener` 通过调用内部类的构造函数进行初始化。
3. `listener` 引用被传递给 `Timer` 构造函数，定时器启动，`start` 方法退出。此时此时，`start` 方法的 `beep` 参数变量已不再存在。
4. 一秒后，`actionPerformed` 方法执行 `if (beep) . . .`。

为了使 `actionPerformed` 方法中的代码能够工作，`TimePrinter` 类必须在 `beep` 参数值失效之前，将 `beep` 字段作为 `start` 方法的局部变量进行拷贝。事实如此。在我们的示例中，编译器为局部内部类生成了名称 `TalkingClock$1TimePrinter`。如果你再次使用 `ReflectionTest` 程序或 `javap` 工具来查看 `TalkingClock$1TimePrinter` 类，你将得到以下输出：

```java
class TalkingClock$1TimePrinter
{
  TalkingClock$1TimePrinter();

  public void actionPerformed(java.awt.event.ActionEvent);

  final boolean val$beep;
  final TalkingClock this$0;
}
```

当创建一个对象时，`beep` 变量的当前值被存储在 `val$beep` 字段中。从 Java 11 开始，这是通过“嵌套同伴”（nest mate）访问实现的。在此之前，内部类的构造函数有一个额外的参数来设置该字段。无论哪种方式，局部变量离开了作用域，内部类字段依然存在。

#### 6.3.6 匿名内部类

在使用局部内部类时，你通常可以更进一步。如果你只想为该类创建一个单一对象，你甚至不需要给该类命名。这样的类被称为匿名内部类。

```java
public void start(int interval, boolean beep)
{
  var listener = new ActionListener()
    {
      public void actionPerformed(ActionEvent event)
      {
        System.out.println("At the tone, the time is "
```



```java
+ Instant.ofEpochMilli(event.getWhen()));

if (beep) Toolkit.getDefaultToolkit().beep();

}

};

var timer = new Timer(interval, listener);

timer.start();

}
```

这种语法确实非常晦涩。它的意思是：创建一个实现 `ActionListener` 接口的类的新对象，其中所需的方法 `actionPerformed` 是在大括号 `{ }` 内部定义的那个。

通常情况下，语法形式为：

```java
new SuperType(construction parameters)
{
    内部类方法和数据
}
```

在这里，`SuperType` 可以是一个接口，例如 `ActionListener`；那么内部类就实现了该接口。`SuperType` 也可以是一个类；那么内部类就继承该类。

匿名内部类不能有构造函数，因为构造函数的名称必须与类名相同，而该类没有名称。相反，构造参数是传递给父类构造函数的。特别是，每当内部类实现接口时，它不能有任何构造参数。尽管如此，你必须提供一组括号，如下：

```java
new InterfaceType()
{
    方法和数据
}
```

你必须仔细观察构造一个类的新对象与构造一个继承该类的匿名内部类对象之间的区别。

```java
var queen = new Person("Mary");
// 一个 Person 对象

var count = new Person("Dracula") { . . . };
// 一个继承 Person 的内部类对象
```

如果构造参数列表的右括号后面跟着一个左大括号，则正在定义一个匿名内部类。

> **注意：**
>
> 尽管匿名类不能有构造函数，但你可以提供一个对象初始化块：
>
> ```java
> var count = new Person("Dracula")
> {
>     { initialization }
>     . . .
> };
> ```

[Listing 6.8] 包含了带有匿名内部类的会报钟程序的完整源代码。如果你将此程序与 [Listing 6.7] 进行比较，你会发现在这种情况下，使用匿名内部类的解决方案要短得多，而且希望通过练习，它同样容易理解。

多年来，Java 程序员经常使用匿名内部类作为事件监听器和其他回调函数。现在，使用 lambda 表达式会更好。例如，本节开头的 `start` 方法可以使用类似下面的 lambda 表达式写得简洁：

```java
public void start(int interval, boolean beep)
{
    var timer = new Timer(interval, event -> {
        System.out.println(
            "At the tone, the time is " + Instant.ofEpochMilli(event.getWhen()));
        if (beep) Toolkit.getDefaultToolkit().beep();
    });
    timer.start();
}
```

> **注意：**
>
> 如果你将匿名类实例存储在用 `var` 定义的变量中，该变量知道添加的方法或字段：
>
> ```java
> var bob = new Object() { String name = "Bob"; }
> System.out.println(bob.name);
> ```
>
> 如果你将 `bob` 声明为类型 `Object`，那么 `bob.name` 将无法编译。
>
> 用 `new Object() { String name = "Bob"; }` 构建的对象类型为“带有 `String name` 字段的 `Object`”。这是一种不可表示的类型——即你无法用 Java 语法表达的类型。尽管如此，编译器理解该类型，并可以将其设置为变量 `bob` 的类型。

> **注意：**
>
> 下面这种被称为“双大括号初始化”的技巧利用了内部类语法。假设你想构造一个列表并将其传递给一个方法：
>
> ```java
> var friends = new ArrayList<String>();
> friends.add("Harry");
> friends.add("Tony");
> invite(friends);
> ```
>
> 如果你不再需要这个列表，让它变成匿名的会很好。但那时如何添加元素呢？方法如下：
>
> ```java
> invite(new ArrayList<String>() {{ add("Harry"); add("Tony"); }});
> ```
>
> 注意双大括号。外部大括号形成 `ArrayList` 的匿名子类。内部大括号是一个初始化块（见第 4 章）。
>
> 在实践中，这种技巧很少用。更有可能的是，`invite` 方法接受任何 `List<String>`，你可以直接传递 `List.of("Harry", "Tony")`。

> **注意：**
>
> 通常方便创建一个与父类相似但并不完全相同的匿名子类。但你需要小心 `equals` 方法。在第 5 章中，我建议你的 `equals` 方法使用如下测试：
>
> ```java
> if (getClass() != other.getClass()) return false;
> ```
>
> 匿名子类将通过此测试失败。

```java
package anonymousInnerClass;

import java.awt.*;
import java.awt.event.*;
import java.time.*;
import javax.swing.*;

/**
 * 此程序演示了匿名内部类。
 * @version 1.12 2017-12-14
 * @author Cay Horstmann
 */
public class AnonymousInnerClassTest
{
    public static void main(String[] args)
    {
        var clock = new TalkingClock();
        clock.start(1000, true);

        // 保持程序运行直到用户选择“确定”
        JOptionPane.showMessageDialog(null, "Quit program?");
        System.exit(0);
    }
}

/**
 * 一个按间隔打印时间的闹钟。
 */
class TalkingClock
{
    /**
     * 启动闹钟。
     * @param interval 消息之间的间隔（毫秒）
     * @param beep 如果闹钟应该发出蜂鸣声，则为 true
     */
    public void start(int interval, boolean beep)
    {
        var listener = new ActionListener()
        {
            public void actionPerformed(ActionEvent event)
            {
                System.out.println("At the tone, the time is "
                    + Instant.ofEpochMilli(event.getWhen()));

                if (beep) Toolkit.getDefaultToolkit().beep();
            }
        };

        var timer = new Timer(interval, listener);
        timer.start();
    }
}
```

### 6.3.7 静态内部类

有时，你可能只想使用内部类来将一个类隐藏在另一个类内部——但你不需要内部类持有外部类对象的引用。你可以通过将内部类声明为 `static` 来抑制该引用的生成。

这里有一个你想这样做的典型示例。考虑计算数组中最小值和最大值的任务。当然，你会写一个方法来计算最小值，写另一个方法来计算最大值。当你调用这两个方法时，数组会被遍历两次。只遍历数组一次并同时计算最小值和最大值会更高效。

```java
double min = Double.POSITIVE_INFINITY;
double max = Double.NEGATIVE_INFINITY;

for (double v : values)
{
    if (min > v) min = v;
    if (max < v) max = v;
}
```

然而，该方法必须返回两个数字。我们可以通过定义一个持有两个值的 `Pair` 类来实现这一点：

```java
class Pair
{
    private double first;
    private double second;

    public Pair(double f, double s)
    {
        first = f;
        second = s;
    }

    public double getFirst() { return first; }

    public double getSecond() { return second; }
}
```

然后 `minmax` 方法就可以返回一个 `Pair` 对象了。

```java
class ArrayAlg
{
    public static Pair minmax(double[] values)
    {
        // ...
        return new Pair(min, max);
    }
}
```

方法的调用者使用 `getFirst` 和 `getSecond` 方法：

```java
Pair p = ArrayAlg.minmax(d);

System.out.println("min = " + p.getFirst());

System.out.println("max = " + p.getSecond());
```

当然，`Pair` 是一个极其常见的名称，在大型项目中，很有可能其他程序员也想到了这一点——制作了一个包含字符串对的 `Pair` 类。我们可以通过将 `Pair` 变为 `ArrayAlg` 内部的公共内部类来解决这种潜在的冲突。这样该类对外公开称为 `ArrayAlg.Pair`：

```java
ArrayAlg.Pair p = ArrayAlg.minmax(d);
```

然而，与之前示例中使用的内部类不同，我们不希望在 `Pair` 对象内部持有任何其他对象的引用。可以通过将内部类声明为 `static` 来抑制该引用：

```java
class ArrayAlg
{
    public static class Pair
    {
        // ...
    }

    // ...
}
```

当然，内部类可以被声明为静态。静态内部类与任何内部类都完全一样，只是静态内部类的对象不持有生成它的外部类的引用。在我们的示例中，我们必须使用静态内部类，因为内部对象是在静态方法内部构造的：

```java
public static Pair minmax(double[] d)
{
    // ...
    return new Pair(min, max);
}
```

如果 `Pair` 类没有被声明为 `static`，编译器将报错，因为没有类型 `ArrayAlg` 的隐式对象来初始化该内部类。

**注意：**只要内部类不需要访问外部类对象，请使用静态内部类。某些程序员使用*嵌套类*（nested class）一词来描述静态内部类。

**注意：**与普通类不同，静态内部类可以拥有静态字段和方法。

**注意：**在接口内部声明的类自动是 `static` 且 `public`。

**注意：**在类内部声明的接口、记录（records）和枚举（enumerations）自动是 `static`。

列表 6.9 包含了 `ArrayAlg` 类和嵌套类 `Pair` 的完整源代码。

**列表 6.9** `staticInnerClass/StaticInnerClassTest.java`

```java
package staticInnerClass;

/**
 * 此程序演示了静态内部类的使用。
 * @version 1.02 2015-05-12
 * @author Cay Horstmann
 */
public class StaticInnerClassTest
{
    public static void main(String[] args)
    {
        var values = new double[20];

        for (int i = 0; i < values.length; i++)
            values[i] = 100 * Math.random();

        ArrayAlg.Pair p = ArrayAlg.minmax(values);

        System.out.println("min = " + p.getFirst());
        System.out.println("max = " + p.getSecond());
    }
}

class ArrayAlg
{
    /**
     * 一对浮点数。
     */
    public static class Pair
    {
        private double first;
        private double second;

        /**
         * 从两个浮点数构造一个对。
         * @param f 第一个数字
         * @param s 第二个数字
         */
        public Pair(double f, double s)
        {
            first = f;
            second = s;
        }

        /**
         * 返回第一个数字
         */
        public double getFirst()
        {
            return first;
        }

        /**
         * 返回第二个数字
         */
        public double getSecond()
        {
            return second;
        }
    }

    /**
     * 计算数组的最小值和最大值
     * @param values 一个浮点数数组
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

### 6.4 服务加载器（Service Loaders）

有时，你会开发一个具有服务架构的应用程序。有一些平台鼓励这种方法，例如 OSGi（[`http://osgi.org`](http://osgi.org)），它们被用于开发环境、应用服务器和其他复杂的应用程序。此类平台远远超出了本书的范围，但 JDK 也提供了一种简单的加载服务的机制，将在此进行描述。

通常，在提供服务时，程序希望赋予服务设计者在实现服务功能方面的某些自由度。同时，有多个实现方案供选择可能也是理想的。`ServiceLoader` 类可以方便地加载符合通用接口的服务。

定义一个接口（或者，如果你愿意，定义一个超类），包含每个服务实例应该提供的方法。例如，假设你的服务提供加密功能。

```java
package serviceLoader;

public interface Cipher
{
    byte[] encrypt(byte[] source, byte[] key);

    byte[] decrypt(byte[] source, byte[] key);

    int strength();
}
```

服务提供者提供一个或多个实现该服务的类，例如：

```java
package serviceLoader.impl;

public class CaesarCipher implements Cipher
{
```



```java
public byte[] encrypt(byte[] source, byte[] key)
{
    var result = new byte[source.length];

    for (int i = 0; i < source.length; i++)
        result[i] = (byte) (source[i] + key[0]);

    return result;
}

public byte[] decrypt(byte[] source, byte[] key)
{
    return encrypt(source, new byte[] { (byte) -key[0] });
}

public int strength() { return 1; }
}
```

实现类可以位于任何包中，不一定与服务接口处于同一个包。每个类都必须有一个无参数构造函数。

现在，将类名添加到 `META-INF/services` 目录下的 UTF-8 编码文本文件中，该文件名必须与接口的全限定名匹配。在我们的示例中，`META-INF/services/serviceLoader.Cipher` 文件将包含以下行：

```text
serviceLoader.impl.CaesarCipher
```

在这个示例中，我们提供了一个实现类。你也可以提供多个类，并在之后从中选择。

完成这些准备后，程序如下初始化服务加载器：

```java
public static ServiceLoader<Cipher> cipherLoader = ServiceLoader.load(Cipher.class);
```

这应该在程序中只执行一次。

服务加载器的 `iterator` 方法返回一个遍历所有提供的服务实现的迭代器。（有关迭代器的更多信息，请参阅第 9 章。）使用增强型 `for` 循环遍历它们是最简单的。在循环中，选择一个合适的对象来执行服务。

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

或者，你可以使用流（参阅第二卷的第 1 章）来定位所需的服务。`stream` 方法产生一个 `ServiceLoader.Provider` 实例的流。该接口拥有 `type` 和 `get` 方法，用于获取提供者类和提供者实例。如果你通过类型选择提供者，只需调用 `type`，而不会不必要地实例化服务实例。

```java
public static Optional<Cipher> getCipher2(int minStrength)
{
    return cipherLoader.stream()
        .filter(descr -> descr.type() == serviceLoader.impl.CaesarCipher.class)
        .findFirst()
        .map(ServiceLoader.Provider::get);
}
```

最后，如果你愿意接受任何服务实例，只需调用 `findFirst`：

```java
Optional<Cipher> cipher = cipherLoader.findFirst();
```

`Optional` 类在第二卷的第 1 章中进行了解释。

### `java.util.ServiceLoader<S>` 1.6

- `static <S> ServiceLoader<S> load(Class<S> service)` 创建一个服务加载器，用于加载实现给定服务接口的类。
- `Iterator<S> iterator()` 返回一个延迟加载服务类的迭代器。也就是说，每当迭代器推进时，就会加载一个类。
- `Stream<ServiceLoader.Provider<S>> stream()` 9 返回提供者描述符的流，以便延迟地加载所需类的提供者。
- `Optional<S> findFirst()` 9 找到第一个可服务提供者（如果有）。

### `java.util.ServiceLoader.Provider<S>` 9

- `Class<? extends S> type()` 获取此提供者的类型。
- `S get()` 获取此提供者的实例。

## 6.5 代理

在本章的最后一节中，我们将讨论代理。你可以使用代理在运行时创建实现一组给定接口的新类。只有当你编译时尚不知道需要实现哪些接口时，代理才是必要的。对于应用程序程序员来说，这并不是常见的情况，所以如果你对高级魔术不感兴趣，可以随时跳过本节。然而，对于某些系统编程应用程序，代理提供的灵活性可能非常重要。

### 6.5.1 何时使用代理

假设你想构造一个实现一个或多个接口的类对象，而你可能在编译时不知道这些接口的精确性质。这是一个困难的问题。要构造一个实际类，你可以简单地使用 `newInstance` 方法或使用反射查找构造函数。但你不能实例化接口。你需要在运行程序中定义一个新类。

为了解决这个问题，某些程序会生成代码，将其放入文件，调用编译器，然后加载生成的类文件。自然地，这种方法很慢，而且还需要将编译器与程序一起部署。代理机制是一个更好的解决方案。代理类可以在运行时创建全新的类。此类代理类实现了你指定的接口。特别地，代理类具有以下方法：

- 指定的接口要求的所有方法；
- `Object` 类中定义的所有方法。

然而，你不能在运行时为这些方法定义新代码。相反，你必须提供一个调用处理器（invocation handler）。调用处理器是任何实现 `InvocationHandler` 接口的类的对象。该接口有一个方法：

```java
Object invoke(Object proxy, Method method, Object[] args)
```

每当在代理对象上调用方法时，调用处理器的 `invoke` 方法会被调用，并带有原始调用的 `Method` 对象和参数。调用处理器随后必须弄清如何处理该调用。

### 6.5.2 创建代理对象

要创建代理对象，使用 `Proxy` 类的 `newProxyInstance` 方法。该方法有三个参数：

- 一个类加载器。作为 Java 安全模型的一部分，不同的类加载器可以用于平台和应用程序类、从互联网下载的类等。我们将在第二卷的第 9 章中讨论类加载器。在示例中，我们指定了加载平台和应用程序类的“系统类加载器”。
- 一个 `Class` 对象数组，每个对象对应要实现的接口。
- 一个调用处理器。

剩下两个问题。我们如何定义处理器？我们对生成的代理对象可以做什么？答案取决于我们想要用代理机制解决的问题。代理可以用于许多目的，例如：

- 将方法调用路由到远程服务器；
- 将用户界面事件与运行程序中的操作关联；
- 用于调试目的跟踪方法调用。

在我们的示例程序中，我们使用代理和调用处理器来跟踪方法调用。我们定义了一个 `TraceHandler` 包装类，存储一个被包装的对象。它的 `invoke` 方法简单地打印被调用方法的名称和参数，然后使用被包装的对象作为隐式参数调用该方法。

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
        . . .

        // 调用实际方法
        return m.invoke(target, args);
    }
}
```

以下是构造一个代理对象的方法，当它的任何方法被调用时，都会触发追踪行为：

```java
Object value = . . .;

// 构造包装器
var handler = new TraceHandler(value);

// 为一个或多个接口构造代理
var interfaces = new Class[] { Comparable.class };

Object proxy = Proxy.newProxyInstance(
    ClassLoader.getSystemClassLoader(),
    new Class[] { Comparable.class },
    handler);
```

现在，每当在 `proxy` 上调用接口的某个方法时，方法名和参数都会打印出来，然后在 `value` 上调用该方法。

在 Listing 6.10 所示的程序中，我们使用代理对象来追踪二分查找。我们用指向整数 `1 . . . 1000` 的代理对象填充数组。然后，我们调用 `Arrays` 类的 `binarySearch` 方法在数组中搜索随机整数。最后，我们打印匹配的元素。

```java
var elements = new Object[1000];

// 用整数 1 . . . 1000 的代理对象填充 elements
for (int i = 0; i < elements.length; i++)
{
    Integer value = i + 1;
    elements[i] = Proxy.newProxyInstance(. . .); // value 的代理
}

// 构造一个随机整数
Integer key = (int) (Math.random() * elements.length) + 1;

// 查找 key
int result = Arrays.binarySearch(elements, key);

// 如果找到则打印结果
if (result >= 0) System.out.println(elements[result]);
```

`Integer` 类实现了 `Comparable` 接口。代理对象属于一个在运行时定义的类（它的名称类似于 `$Proxy0`）。该类也实现了 `Comparable` 接口。然而，它的 `compareTo` 方法会调用代理对象处理器的 `invoke` 方法。

> **注意：**
>
> 正如你在本章较早看到的，`Integer` 类实际上实现了 `Comparable<Integer>`。但是，在运行时，所有的泛型类型都会擦除，代理是使用原始 `Comparable` 类的类对象构造的。

`binarySearch` 方法发出的调用如下：

```java
if (elements[i].compareTo(key) < 0) . . .
```

由于我们向数组中填充了代理对象，因此 `compareTo` 调用会触发 `TraceHandler` 类的 `invoke` 方法。该方法打印方法名和参数，然后在被包装的 `Integer` 对象上调用 `compareTo`。

最后，在示例程序的末尾，我们调用了：

```java
System.out.println(elements[result]);
```

`println` 方法调用代理对象的 `toString` 方法，该调用也会被重定向到调用处理器。

以下是程序运行的完整追踪：

```text
500.compareTo(288)
250.compareTo(288)
375.compareTo(288)
312.compareTo(288)
281.compareTo(288)
296.compareTo(288)
288.compareTo(288)
288.toString()
```

你可以看到二分查找算法如何通过每一步将搜索范围缩小一半来定位 key。注意，尽管 `toString` 方法不属于 `Comparable` 接口，它也是被代理的——正如你将在下一节中看到的，某些 `Object` 方法总是会被代理的。

**Listing 6.10** `proxy/ProxyTest.java`

```java
package proxy;

import java.lang.reflect.*;
import java.util.*;

/**
 * 此程序演示了代理的使用。
 * @version 1.02 2021-06-16
 * @author Cay Horstmann
 */
public class ProxyTest
{
    public static void main(String[] args)
    {
        var elements = new Object[100];

        // 用整数 1 . . . 1000 的代理对象填充 elements
        for (int i = 0; i < elements.length; i++)
        {
            Integer value = i + 1;
            var handler = new TraceHandler(value);
            Object proxy = Proxy.newProxyInstance(
                ClassLoader.getSystemClassLoader(),
                new Class[] { Comparable.class },
                handler);
            elements[i] = proxy;
        }

        // 构造一个随机整数
        Integer key = (int) (Math.random() * elements.length) + 1;

        // 查找 key
        int result = Arrays.binarySearch(elements, key);

        // 如果找到则打印结果
        if (result >= 0) System.out.println(elements[result]);
    }
}
```

### 6.5.3 代理类的属性

现在你已经看到了代理类的用法，让我们回顾一下它们的一些属性。记住，代理类是在运行时创建的。但是，一旦创建，它们就像任何其他类一样是普通的类。

所有的代理类都扩展 `Proxy` 类。代理类只有一个实例字段——调用处理器，它定义在 `Proxy` 超类中。执行代理任务所需的额外数据必须存储在调用处理器。例如，当我们在 Listing 6.10 所示程序中代理对象时，`TraceHandler` 包装了实际对象。

所有代理类都重写了 `Object` 类的 `toString`、`equals` 和 `hashCode` 方法。与所有代理方法一样，这些方法简单地调用调用处理器。`Object` 类的其他方法（如 `clone` 和 `getClass`）没有重定义。

代理类的名称没有定义。Oracle 虚拟机中的 `Proxy` 类生成的类名以字符串 `$Proxy` 开头。

特定的类加载器和有序接口集只有一个代理类。也就是说，如果你使用相同的类加载器和接口数组调用两次 `newProxyInstance` 方法，你将获得相同类的对象。你也可以通过 `getProxyClass` 方法获取该类：

```java
Class proxyClass = Proxy.getProxyClass(null, interfaces);
```

代理类始终是 `public` 且 `final` 的。如果代理类实现的所有接口都是 `public`，则代理类不属于任何特定的包。否则，所有非 `public` 接口必须属于同一个包，且代理类也将属于该包。

可以通过调用 `Proxy` 类的 `isProxyClass` 方法来测试特定的 `Class` 对象是否代表代理类。

调用代理的默认方法会触发处理程序。要实际调用该方法，请使用 `InvocationHandler` 接口的静态方法 `invokeDefault`。例如，这里有一个处理程序，它可以调用默认方法并将抽象方法传递给另一个目标。

```java
InvocationHandler handler = (proxy, method, args) ->
{
    if (method.isDefault())
        return InvocationHandler.invokeDefault(proxy, method, args);
    else
        return method.invoke(target, args);
};
```



# `java.lang.reflect.InvocationHandler`（1.3）

- `Object invoke(Object proxy, Method method, Object[] args)`

  定义此方法以包含每当在代理对象上调用方法时你想要执行的操作。

- `static Object invokeDefault(Object proxy, Method method, Object... args)`（16）

  使用给定的参数调用代理实例的默认方法，跳过处理程序。

# `java.lang.reflect.Proxy`（1.3）

- `static Class<?> getProxyClass(ClassLoader loader, Class<?>... interfaces)`

  返回实现给定接口的代理类。

- `static Object newProxyInstance(ClassLoader loader, Class<?>[] interfaces, InvocationHandler handler)`

  构造实现给定接口的代理类的新实例。所有方法都会调用给定处理对象的 `invoke` 方法。

- `static boolean isProxyClass(Class<?> cl)`

  如果 `cl` 是代理类，则返回 `true`。

关于 Java 编程语言面向对象特性的章节到此结束。接口、lambda 表达式和内部类是你会频繁遇到的概念，而克隆、服务加载器和代理是主要是库设计者和工具构建者感兴趣的高级技术，而不是应用程序程序员的。你现在已经准备好在[第 7 章](#ch07.xhtml_ch7)中学习如何处理程序中的异常情况了。

## 第 7 章 异常、断言与日志

### 本章内容

- 7.1 处理错误
- 7.2 捕获异常
- 7.3 使用异常的技巧
- 7.4 使用断言
- 7.5 日志
- 7.6 调试技巧

在一个完美的世界里，用户永远不会以错误的格式输入数据，他们选择打开的文件始终存在，代码永远不会有 bug。到目前为止，我展示代码大多就像我们都生活在这样一个完美的世界一样。现在是时候转向 Java 编程语言用于处理糟糕数据和多 bug 代码的真实世界的机制了。

遇到错误是不愉快的。如果用户因为编程错误或某些外部情况丢失了在程序会话期间的所有工作，那么该用户可能会永远离开你的程序。至少，你必须：

- 通知用户发生了错误；
- 保存所有工作；以及
- 允许用户优雅地退出程序。

对于异常情况（例如可能导致程序崩溃的错误输入数据），Java 使用了一种错误捕获机制，顾名思义被称为*异常处理*。Java 中的异常处理与 C++ 或 Delphi 类似。本章的第一部分将介绍 Java 异常。

在测试期间，你需要运行许多检查以确保你的程序运行正常。但这些检查在测试完成后可能是耗时且不必要的。你可以直接删除这些检查，并在需要额外测试时将它们加回来——但这很麻烦。本章的第二部分将向你展示如何使用断言机制选择性地激活检查。

当你的程序执行错误时，你并不总是能与用户通信或终止。相反，你可能想记录问题以便稍后分析。本章的第三部分将讨论标准的 Java 日志框架。

### 7.1 处理错误

假设一个 Java 程序在运行时发生了错误。该错误可能是由包含错误信息的文件、不稳定的网络连接，或者（我不想提到它）使用无效的数组索引或尚未分配给对象的引用引起的。用户期望程序在发生错误时表现得合情合理。如果某个操作因为错误而无法完成，程序应该：

- 回到安全状态并允许用户执行其他命令；或者
- 允许用户保存所有工作并优雅地退出程序。

这可能并不容易做到，因为检测（甚至引起）错误条件的代码通常与可以将数据回滚到安全状态或保存用户工作并愉快退出的代码相隔很远。异常处理的任务是将控制从错误发生的地方转移到处理该情况的错误处理器。为了处理程序中的异常情况，你必须考虑到可能发生的错误和问题。你需要考虑哪些类型的问题？

- *用户输入错误*。除了不可避免的拼写错误外，某些用户喜欢自辟蹊而不是遵循指示。例如，假设用户请求连接到一个语法上错误的 URL。你的代码应该检查语法，但假设它没有检查。那么网络层就会抱怨。
- *设备错误*。硬件并不总是按照你希望的方式工作。打印机可能关闭了。网页可能临时不可用。设备经常会在任务中间失败。例如，打印机在打印过程中可能缺纸。
- *物理限制*。磁盘可能会满；你可能会耗尽可用内存。
- *代码错误*。方法可能执行不正确。例如，它可能提供错误的答案或错误地使用其他方法。计算无效的数组索引、尝试在哈希表中查找不存在的条目或尝试从空栈中弹出都是代码错误的示例。

对方法中错误的传统反应是返回一个特殊的错误代码，由调用方法进行分析。例如，从文件读取信息的方法通常返回一个 `-1` 文件结束值标记，而不是标准字符。这是处理许多异常情况的一种有效方法。另一个表示错误条件的常见返回值是 `null` 引用。

不幸的是，并不总是可以返回错误代码。可能没有明显的方法来区分有效数据无效。返回整数的方法不能简单地返回 `-1` 表示错误；值 `-1` 可能是一个完全有效的结果。

相反，正如我在第 5 章中提到的，如果方法无法以正常方式完成任务，Java 允许每个方法有一个替代路径。在这种情况下，方法不返回值。相反，它*抛出*一个封装了错误信息的对象。注意方法会立即退出；它不返回正常值。此外，执行不会在调用方法的代码处继续；相反，异常处理机制开始寻找处理此特定错误条件的*异常处理器*。

异常有自己的语法，并属于特殊的继承层次结构。我将先介绍语法，然后提供如何有效使用此语言功能的提示。

#### 7.1.1 异常的分类

在 Java 编程语言中，异常对象总是派自 `Throwable` 类的实例。正如你很快就会看到的，如果 Java 内置的异常不能满足需求，你可以创建自己的异常类。

图 7.1 是 Java 异常层次结构的简化图表。

![Images](img/07fig01.jpg)

**图 7.1** Java 异常层次结构

注意所有的异常都继承自 `Throwable`，但该层次结构立即分为两个分支：`Error` 和 `Exception`。

`Error` 层次结构描述了 Java 运行时系统内部的错误和资源耗尽的情况。你不应该抛出此类类型的对象。如果发生此类内部错误，除了通知用户并尝试优雅地退出程序外，你无能为力。这些情况非常罕见。

在进行 Java 编程时，请关注 `Exception` 层次结构。`Exception` 层次也分为两个分支：派自 `RuntimeException` 的异常和不派自它的异常。通用规则是：`RuntimeException` 的发生是因为你犯了编程错误。而任何其他异常的发生是因为某些坏事（例如 I/O 错误）发生在了你原本良好的程序上。

继承自 `RuntimeException` 的异常包括此类问题：

- 错误的类型转换
- 数组越界访问
- 空指针访问

不继承自 `RuntimeException` 的异常包括：

- 尝试读取文件末尾之后的内容
- 尝试打开一个不存在的文件
- 尝试为一个未表示现有类的字符串查找 `Class` 对象

“如果是 `RuntimeException`，那就是你的错”这条规则运行得很好。你可以通过检查数组索引是否在数组边界内避免 `ArrayIndexOutOfBoundsException`。如果你在使用变量之前检查了它是否为 `null`，那么 `NullPointerException` 就不会发生。

那么不存在的文件呢？难道不能先检查文件是否存在，然后再打开它吗？嗯，文件可能在你检查其存在性之后立即被删除了。因此，“存在性”的概念取决于环境，而不仅仅取决于你的代码。

Java 语言规范将任何派自 `Error` 类或 `RuntimeException` 类的异常称为*未检查的*（unchecked）异常。所有其他异常都称为*已检查的*（checked）异常。这是一个用的术语，我在书中也采用了这一术语。编译器会检查你是否为所有已检查异常提供了异常处理器。

> ![Image](img/note.jpg) **注意：**
>
> `RuntimeException` 这个名字有点让人困惑。当然，我们讨论的所有错误都发生在运行时。这个名字源于史前时代，当时 Java 的前身 Oak 的“运行时”会产生越界异常和空指针异常。推测 I/O 异常是由其他组件产生的。

> ![Image](img/c.jpg) **C++ 注意：**
>
> 如果你熟悉标准 C++ 库（受限得多）的异常层次结构，你在这里可能会感到非常困惑。C++ 有两个基础异常类：`runtime_error` 和 `logic_error`。`logic_error` 类等同于 Java 的 `RuntimeException`，也表示程序中的逻辑错误。`runtime_error` 类是由不可预测问题引起的异常的基类。它等同于 Java 中那些*不是* `RuntimeException` 类型的异常。

### 7.1.2 声明已检查异常

如果 Java 方法遇到它无法处理的情况，它就可以抛出异常。这个想法很简单：一个方法不仅会告诉 Java 编译器它可以返回什么值，*还会告诉编译器可能会出现什么问题。*例如，尝试从文件读取的代码知道文件可能不存在，或者可能为空。因此，尝试处理文件中信息的代码将需要通知编译器它可以抛出某种 `IOException`。

你宣称你的方法可以抛出异常的地方是方法的头部；头部会改变以反映该方法可以抛出的已检查异常。例如，这里是标准库中 `FileInputStream` 类的一个构造函数的声明。（有关输入和输出的更多信息，请参见第二卷的第 1 章。）

```java
public FileInputStream(String name) throws FileNotFoundException
```

声明说该构造函数从 `String` 参数产生一个 `FileInputStream` 对象，但它*也*可能以特殊方式出错——通过抛出一个 `FileNotFoundException`。如果发生了这种不幸的情况，构造函数的调用将不会初始化一个新的 `FileInputStream` 对象，而是抛出一个 `FileNotFoundException` 类的对象。如果是这样，运行时系统将开始寻找知道处理 `FileNotFoundException` 对象的异常处理器。

当你编写自己的方法时，你不需要宣称你的方法实际上可能抛出的每一个可能的可抛出对象。要理解何时（以及什么）你需要在编写的方法的 `throws` 子句中声明内容，请记住异常在以下四种情况之一中会被抛出：

- 你调用了一个抛出已检查异常的方法——例如，`FileInputStream` 构造函数。
- 你检测到一个错误并使用 `throw` 语句抛出已检查异常（`throw` 语句将在下一节中介绍）。
- 你犯了编程错误，例如 `a[-1] = 0` 导致了未检查异常（在这种情况下，是 `ArrayIndexOutOfBoundsException`）。
- 虚拟机或运行时库中发生了内部错误。

如果发生了前两种情况的任何一种，你必须告诉将使用你方法的程序员关于异常的可能性。为什么？任何抛出异常的方法都是一个潜在的死亡陷阱。如果没有处理器捕获该异常，当前的执行线程将终止。

与所提供的类中的 Java 方法一样，你通过方法头部的*异常规格说明*来声明你的方法可能抛出异常。

```java
class MyAnimation
{
    . . .

    public Image loadImage(String s) throws IOException
    {
        . . .
    }
}
```

如果一个方法可能抛出多个已检查异常，你必须在头部列出所有异常类。用逗号分隔它们，如下例：

```java
class MyAnimation
{
    . . .

    public Image loadImage(String s) throws FileNotFoundException, EOFException
    {
        . . .
    }
}
```

然而，你不需要宣称 Java 错误——即继承自 `Error` 的异常。任何代码都可能抛出这些异常，而且完全在你的控制之外。

同样，你不应该宣称继承自 `RuntimeException` 的未检查异常。

```java
class MyAnimation
{
    . . .

    void drawImage(int i) throws ArrayIndexOutOfBoundsException // 坏风格
    {
        . . .
    }
}
```

这些运行时错误完全在你的控制之下。如果你如此担心数组索引错误，你应该花时间修复它们，而不是宣称它们发生的可能性。

总结，方法必须声明它可能抛出的所有*已检查*异常。未检查异常要么在你的控制之外（`Error`），要么是由你本不应该允许的情况引起的（`RuntimeException`）。如果方法未能声明所有已检查异常，编译器将发出错误信息。

当然，正如你已经在许多示例中所看到的，除了声明异常之外，你也可以捕获它。这样，异常就不会抛出方法，也不需要 `throws` 规格说明。你将在本章稍后的部分看到如何决定是捕获异常还是让别人捕获它。

如果你重写了父类的方法，那么子类方法声明的受检异常（checked exceptions）不能比父类方法的更具通用性。（在子类方法中抛出更具体的异常，或者不抛出任何异常都是可以的。）特别是，如果父类方法完全没有抛出任何受检异常，子类也不能抛出。例如，如果你重写了 `JComponent.paintComponent`，那么你的 `paintComponent` 方法不能抛出任何受检异常，因为父类方法没有抛出任何异常。

当类中的方法声明它会抛出一个特定类实例的异常时，它可能会抛出该类的异常或该类任何子类的异常。例如，`FileInputStream` 构造函数可能声明它会抛出一个 `IOException`。在这种情况下，你将不知道它是哪种 `IOException`；它可能是一个普通的 `IOException`，也可能是各种子类中的一个对象，例如 `FileNotFoundException`。

> ![Image](img/c.jpg) **C++ 注意：**
>
> `throws` 标识符与 C++ 中的 `throw` 标识符相同，但有一个重要的区别。在 C++ 中，`throw` 标识符是在运行时强制执行的，而不是编译时。也就是说，C++ 编译器不检查异常规范。但如果在不在 `throw` 列表的函数中抛出了异常，将调用 `unexpected` 函数，并且默认情况下，程序将终止。
>
> 此外，在 C++ 中，如果没有给出 `throw` 规范，函数可以抛出任何异常。在 Java 中，没有 `throws` 标识符的方法可能完全不会抛出任何受检异常。

#### 7.1.3 如何抛出异常

现在，假设你的代码发生了某些糟糕的事情。你有一个方法 `readData` 正在读取一个文件，该文件的头部承诺了：

```text
Content-length: 1024
```

但你在 733 个字符之后就遇到了文件末尾。你可能认为这种情况太异常了，以至于你想抛出一个异常。

你需要决定抛出什么类型的异常。某种 `IOException` 会是一个很不错的选择。查阅 Java API 文档，你发现了一个 `EOFException`，描述为“信号在输入过程中意外到达了文件末尾”。完美。以下是抛出它的方法：

```java
throw new EOFException();
```

或者，如果你喜欢的话：

```java
var e = new EOFException();

throw e;
```

以下是它们是如何结合的：

```java
String readData(Scanner in) throws EOFException
{
    . . .

    while (. . .)
    {
        if (!in.hasNext()) // 遇到 EOF
        {
            if (n < len)
                throw new EOFException();
        }

        . . .
    }

    return s;
}
```

`EOFException` 有第二个构造函数，可以接受一个字符串参数。你可以通过更详细地描述异常条件来充分利用它。

```java
String gripe = "Content-length: " + len + ", Received: " + n;

throw new EOFException(gripe);
```

如你所见，如果现有的异常类有一个适用于你，那么抛出异常很容易。在这种情况下：

1. 找到一个合适的异常类。
2. 创建该类的对象。
3. 抛出它。

一旦方法抛出异常，它就不会返回到调用者处。这意味着你不需要担心去构造一个默认的返回值或错误代码。

> ![Image](img/c.jpg) **C++ 注意：**
>
> 在 C++ 和 Java 中抛出异常是相同的，但有一个微小的区别。在 Java 中，你只能抛出 `Throwable` 子类的对象。在 C++ 中，你可以抛出任何类型的值。

#### 7.1.4 创建异常类

你的代码可能会遇到任何标准异常类都无法充分描述的问题。在这种情况下，创建你自己的异常类是非常简单的。只需继承自 `Exception`，或者继承自 `Exception` 的子类（如 `IOException`）。惯例是提供一个默认构造函数和一个包含详细消息的构造函数。（`Throwable` 父类的 `toString` 方法返回一个包含该详细消息的字符串，这对于调试非常有用。）

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




现在你已经准备好抛出你自己的异常类型了。

```java
String readData(Scanner in) throws FileFormatException
{
    . . .
    while (. . .)
    {
        if (ch == -1) // 遇到 EOF
        {
            if (n < len)
                throw new FileFormatException();
        }
        . . .
    }
    return s;
}
```

---

**`java.lang.Throwable`**

- `Throwable()` 构建一个新的没有消息的 `Throwable`。
- `Throwable(String message)` 构建一个新的带有指定消息的 `Throwable`。
- `String getMessage()` 获取 `Throwable` 的消息。

## 7.2 捕获异常

你现在知道如何抛出异常了。如何异常。捕获异常需要更多的规划。接下来的章节将涵盖这些。

### 7.2.1 捕获异常

`try` 块的最简单形式如下：

```java
try
{
    code
    more code
}
catch (ExceptionType e)
{
    handler
}
```

如果 `try` 块中的任何代码抛出了与 `catch` 子句中命名的类相同的异常：

1. 程序跳过 `try` 块中剩余的代码。
2. 程序执行 `catch` 子句中的处理器。

如果 `try` 块中的任何代码抛出了与指定名称不同的类型的异常，程序将立即退出该方法。

为了展示这一工作，这里有一些用于读取的典型代码：

```java
public void read(String filename)
{
    try
    {
        var in = new FileInputStream(filename);
        int b;
        while ((b = in.read()) != -1)
        {
            process input
        }
    }
    catch (IOException exception)
    {
        exception.printStackTrace();
    }
}
```

注意，`try` 子句中的大部分代码都是直观的：它读取并处理字节直到遇到文件末尾。如你通过查看 Java API 所示，`read` 方法有抛出 `IOException` 的可能。在这种情况下，我们跳过整个 `while` 循环，进入 `catch` 子句并生成堆栈跟踪。对于玩具程序，这似乎是处理该异常的合理方法。你还有什么选择？

通常，最好的选择是什么都不做，只需将异常传递给调用者。如果 `read` 方法中发生错误，让调用 `read` 方法的调用者去担心吧！如果我们采取这种方法，我们就必须声明该方法可能会抛出 `IOException`。

```java
public void read(String filename) throws IOException
{
    var in = new FileInputStream(filename);
    int b;
    while ((b = in.read()) != -1)
    {
        process input
    }
}
```

记住，编译器会强制执行 `throws` 限定符。如果你调用了一个抛出受检异常（checked exception）的方法，你必须要么处理它，要么将其传递下去。

这两种方法哪种更好？作为一个一般原则，你应该捕获那些你知道如何处理的异常，并传播那些你不知道如何处理的异常。当你传播一个异常时，必须添加 `throws` 限定符，以提醒调用者可能会抛出异常。

查看 Java API 文档，以了解哪些方法抛出哪些异常。然后决定你是应该处理它们，还是将它们添加到 `throws` 列表中。后一种选择并不可羞耻。将异常引导给胜任的处理器，比将其扼杀（忽略）要好。

请记住，正如前面提到的，这条规则有一个例外。如果你编写的方法重写了一个不抛出任何异常的父类方法（例如 `JComponent` 中的 `paintComponent`），那么你必须在方法代码中处理每个受检异常。你不被允许在子类方法中添加比父类方法更多的 `throws` 限定符。

---

![Image](img/c.jpg) **C++ 注意：**

在 Java 和 C++ 中，捕获异常几乎是相同的。严格来说，

```java
catch (Exception e) // Java
```

等价于：

```cpp
catch (Exception& e) // C++
```

C++ 中的 `catch (. . .)` 没有对应的等价物。这在 Java 中不需要，因为所有异常都派自一个共同的父类。

### 7.2.2 捕获多个异常

你可以在 `try` 块中捕获多种异常类型，并对每个类型进行不同的处理。为每种类型使用单独的 `catch` 子句，如下：

```java
try
{
    code that might throw exceptions
}
catch (FileNotFoundException e)
{
    缺少文件的紧急操作
}
catch (UnknownHostException e)
{
    未知主机的紧急操作
}
catch (IOException e)
{
    所有其他 I/O 问题的紧急操作
}
```

异常对象可能包含有关异常性质的信息。要了解更多关于对象的信息，请尝试：

```java
e.getMessage()
```

获取详细的错误信息（如果有的话），或者：

```java
e.getClass().getName()
```

获取异常对象的实际类型。

从 Java 7 开始，你可以在同一个 `catch` 子句中捕获多种异常类型。例如，假设处理缺失文件和未知主机的操作是相同的。那么你可以合并 `catch` 子句：

```java
try
{
    code that might throw exceptions
}
catch (FileNotFoundException | UnknownHostException e)
{
    缺失文件和未知主机的紧急操作
}
catch (IOException e)
{
    所有其他 I/O 问题的紧急操作
}
```

此特性只有在捕获互不为子类的异常类型时才需要。

---

![Image](img/note.jpg) **注意：**

当你捕获多个异常时，异常变量隐含是 `final` 的。例如，你不能在子句体中为 `e` 赋值不同的值：

```java
catch (FileNotFoundException | UnknownHostException e) { . . . }
```

---

![Image](img/note.jpg) **注意：**

捕获多个异常不仅让你的代码看起来更简单，而且更高效。生成的字节码包含一个用于共享 `catch` 子句的单一块。

## 7.2.3 重新抛出和链异常

你可以在 `catch` 子句中抛出异常。通常，当你想要更改异常类型时这样做。如果你构建了一个其他程序员使用的子系统，那么使用一种指示子系统失败的异常类型是有意义的。这种异常类型的一个示例是 `ServletException`。执行 servlet 的代码可能不想知道发生了什么问题，但它绝对想知道 servlet 出了错。

以下是捕获异常并重新抛出它的方法：

```java
try
{
    access the database
}
catch (SQLException e)
{
    throw new ServletException("database error: " + e.getMessage());
}
```

在这里，`ServletException` 使用异常的消息文本进行构造。

然而，将原始异常设置为新异常的“原因”（cause）是一个更好的主意：

```java
try
{
    access the database
}
catch (SQLException original)
{
    var e = new ServletException("database error");
    e.initCause(original);
    throw e;
}
```

当异常被捕获时，可以检索原始异常：

```java
Throwable original = caughtException.getCause();
```

这种封装技术是被高度推荐的。它允许你在子系统中抛出层级异常，而不会丢失原始失败的细节。

---

![Image](img/tip.jpg) **提示：**

如果在不允许抛出受检异常的方法中发生了受检异常，封装技术也有用。你可以捕获受检异常并将其封装为运行时异常（runtime exception）。

有时，你只想记录异常并在不做任何更改的情况下重新抛出它：

```java
try
{
    access the database
}
catch (Exception e)
{
    logger.log(level, message, e);
    throw e;
}
```

在 Java 7 之前，这种方法存在问题。假设代码位于方法：

```java
public void updateRecord() throws SQLException
```

Java 编译器查看 `catch` 块内部的 `throw` 语句，查看 `e` 的类型，并抱怨该方法可能会抛出任何 `Exception`，而不只是 `SQLException`。这现在已经得到了。编译器现在跟踪 `e` 源自 `try` 块这一事实。只要该块中唯一的受检异常是 `SQLException` 实例，且只要 `e` 在 `catch` 块中没有被更改，将封装的方法声明为 `throws SQLException` 就是有效的。

### 7.2.4 `finally` 子句

当你的代码抛出异常时，它会停止处理方法中的剩余代码并退出方法。如果该方法获取了一些只有该方法知道的本地资源，且该资源必须被清理，就会出现问题。一种解决方案是捕获所有异常，执行清理并重新抛出异常。但这种解决方案是冗长的，因为你需要在两个地方清理资源分配——普通代码和异常代码中。`finally` 子句可以解决这个问题。

---

![Image](img/note.jpg) **注意：**

从 Java 7 开始，有一个更优雅的解决方案，即 `try`-with-resources 语句，你将在下一节看到它。我们详细讨论 `finally` 机制是因为它是概念基础。但在实践中，你可能会比使用 `finally` 子句频繁地使用 `try`-with-resources 语句。

`finally` 子句中的代码无论是否捕获异常都会执行。在示例中，程序将在所有情况下关闭输入流：

```java
var in = new FileInputStream(. . .);

try
{
    // 1
    code that might throw exceptions
    // 2
}
catch (IOException e)
{
    // 3
    show error message
    // 4
}
finally
{
    // 5
    in.close();
}
// 6
```

让我们看看程序执行 `finally` 子句的三种可能情况。

1. 代码没有抛出异常。在这种情况下，程序首先执行 `try` 块中的所有代码。然后，执行 `finally` 子句中的代码。之后，从 `finally` 子句后的第一个语句继续执行。换句话说，执行通过了点 1、2、5 和 6。
2. 代码抛出了一个被 `catch` 子句捕获的异常——在我们的案例中，是一个 `IOException`。对于这种情况，程序执行 `try` 块中的所有代码，直到抛出异常的点为止。`try` 块中的剩余代码被跳过。然后，程序执行匹配的 `catch` 子句中的代码，然后执行 `finally` 子句中的代码。

   如果 `catch` 子句没有抛出异常，程序将执行 `finally` 子句之后的第一行。在这种情况下，执行流将通过点 1、3、4、5 和 6。

   如果 `catch` 子句抛出了异常，则该异常将抛回给此方法的调用者，执行流将仅通过点 1、3 和 5。

3. 代码抛出了一个没有被任何 `catch` 子句捕获的异常。在这里，程序会执行 `try` 块中的所有代码，直到抛出异常为止。`try` 块中剩余的代码被跳过。然后，执行 `finally` 子句中的代码，并将异常抛回给此方法的调用者。执行流将仅通过点 1 和 5。

你可以在没有 `catch` 子句的情况下使用 `finally` 子句。例如，考虑以下 `try` 语句：

```java
InputStream in = . . .;

try
{
    code that might throw exceptions
}
finally
{
    in.close();
}
```

无论 `try` 块中是否遇到异常，`finally` 子句中的 `in.close()` 语句都会执行。当然，如果遇到了异常，它会被重新抛出并在另一个 `catch` 子句中被捕获。

```java
InputStream in = . . .;

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

内部 `try` 块有单一职责：确保输入流被关闭。外部 `try` 块有单一职责：确保错误被报告。这种解决方案不仅更清晰，而且功能更强：`finally` 子句中的错误会被报告。

---

![Image](img/caution.jpg) **注意：**

当 `finally` 子句包含 `return` 语句时，可能会产生意想不到的结果。假设你使用 `return` 语句从 `try` 块中间退出。在方法返回之前，会执行 `finally` 块。如果 `finally` 块也包含 `return` 语句，它将掩盖原始的返回值。考虑这个例子：

```java
public static int parseInt(String s)
{
    try
    {
        return Integer.parseInt(s);
    }
    finally
    {
        return 0;
    }
}
```

看起来在调用 `parseInt("42")` 时，`try` 块的主体返回整数 42。然而，`finally` 子句在方法实际返回之前执行，导致方法返回 0，忽略了原始的返回值。

情况变得更糟。考虑调用 `parseInt("zero")`。`Integer.parseInt` 方法抛出了 `NumberFormatException`。然后执行 `finally` 子句，`return` 语句吞噬了异常！

`finally` 子句的主体用于清理资源。不要在 `finally` 子句中放置改变控制流的语句（`return`、`throw`、`break`、`continue`）。

### 7.2.5 `try`-with-Resources 语句

从 Java 7 开始，这种代码模式有一个实快捷写法：

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

前提是该资源属于实现 `AutoCloseable` 接口的类。该接口有一个单一的方法：

```java
void close() throws Exception
```

---

![Image](img/note.jpg) **备注：**

还有一个 `Closeable` 接口。它是 `AutoCloseable` 的子接口，同样有一个单一的 `close` 方法。然而，该方法声明为抛出 `IOException`。

在最简单的变中，`try`-with-resources 语句的形式如下：

```java
try (Resource res = . . .)
{
    work with res
}
```

当 `try` 块退出时，会自动调用 `res.close()`。这是一个典型的例子——读取文件中的所有单词：

```java
try (var in = new Scanner(Path.of("in.txt"), StandardCharsets.UTF_8))
{
    while (in.hasNext())
        System.out.println(in.next());
}
```

当块正常退出或发生异常时，都会调用 `in.close()` 方法，就 exact 比你使用了 `finally` 块一样。

你可以指定多个资源。例如：

```java
try (var in = new Scanner(Path.of("in.txt"), StandardCharsets.UTF_8);
     var out = new PrintWriter("out.txt", StandardCharsets.UTF_8))
{
    while (in.hasNext())
        System.out.println(in.next());
}
```




`factorial(3)`：

```text
stackTrace.StackTraceTest.factorial(StackTraceTest.java:20)
stackTrace.StackTraceTest.main(StackTraceTest.java:36)
```

`factorial(2)`：

```text
stackTrace.StackTraceTest.factorial(StackTraceTest.java:20)
stackTrace.StackTraceTest.factorial(StackTraceTest.java:26)
stackTrace.StackTraceTest.main(StackTraceTest.java:36)
```

`factorial(1)`：

```text
stackTrace.StackTraceTest.factorial(StackTraceTest.java:20)
stackTrace.StackTraceTest.factorial(StackTraceTest.java:26)
stackTrace.StackTraceTest.factorial(StackTraceTest.java:26)
stackTrace.StackTraceTest.main(StackTraceTest.java:36)
```

```text
return 1
return 2
return 6
```

### 7.1 `stackTrace/StackTraceTest.java`

```java
package stackTrace;

import java.util.*;

/**
 * 一个显示递归方法调用轨迹特征的程序。
 * @version 1.10 2017-12-14
 * @author Cay Horstmann
 */
public class StackTraceTest
{
    /**
     * 计算数字的阶乘
     * @param n 一个非负整数
     * @return n! = 1 * 2 * . . . * n
     */
    public static int factorial(int n)
    {
        System.out.println("factorial(" + n + "):");
        var walker = StackWalker.getInstance();
        walker.forEach(System.out::println);
        int r;
        if (n <= 1) r = 1;
        else r = n * factorial(n - 1);
        System.out.println("return " + r);
        return r;
    }

    public static void main(String[] args)
    {
        try (var in = new Scanner(System.in))
        {
            System.out.print("Enter n: ");
            int n = in.nextInt();
            factorial(n);
        }
    }
}
```

### `java.lang.Throwable` 1.0

- `Throwable(Throwable cause)` 1.4
- `Throwable(String message, Throwable cause)` 1.4  
  创建一个带有给定原因的 `Throwable`。
- `Throwable initCause(Throwable cause)` 1.4  
  设置此对象的异常，如果此对象已经有了原因则抛出异常。返回 `this`。
- `Throwable getCause()` 1.4  
  获取设置为此对象原因的异常对象，如果没有设置原因则返回 `null`。
- `StackTraceElement[] getStackTrace()` 1.4  
  获取此对象构造时的调用堆栈轨迹。
- `void addSuppressed(Throwable t)` 7  
  向此异常添加一个“被抑制”的异常。这发生在 `try`-with-resources 语句中，其中 `t` 是由 `close` 方法抛出的异常。
- `Throwable[] getSuppressed()` 7  
  获取此异常的所有“被抑制”异常。通常，这些是 `try`-with-resources 语句中由 `close` 方法抛出的异常。

### `java.lang.Exception` 1.0

- `Exception(Throwable cause)` 1.4
- `Exception(String message, Throwable cause)`  
  创建一个带有给定原因的 `Exception`。

### `java.lang.RuntimeException` 1.0

- `RuntimeException(Throwable cause)` 1.4
- `RuntimeException(String message, Throwable cause)` 1.4  
  创建一个带有给定原因的 `RuntimeException`。

### `java.lang.StackWalker` 9

- `static StackWalker getInstance()`
- `static StackWalker getInstance(StackWalker.Option)`
- `static StackWalker getInstance(Set<StackWalker.Option>)`
- `forEach(Consumer<? super StackFrame>)`
- `walk(Function<? super StackFrame, ? extends T>)`

### `java.lang.StackTraceElement` 1.4

- `String getFileName()`
- `int getLineNumber()`
- `String getClassName()`
- `String getDeclaring()`
- `String getMethodName()`
- `boolean isNativeMethod()`
- `String toString()`

### 7.3 使用异常的技巧

#### 使用异常的 3 个技巧

关于异常的正确使用存在一定的争议。一些程序员认为所有受检异常（checked exceptions）都是麻烦，而另一些人似乎觉得抛得不够。我认为异常（即使是受检异常）也有其用武，因此我提供了这些正确使用异常的技巧。

#### 1. 异常处理不应该替代简单的测试

作为一个示例，这里的代码尝试 10,000,000 次弹出一个空栈元素。它首先通过检查栈是否为空来实现这一点。

```java
if (!s.empty()) s.pop();
```

接下来，我们无论如何都强制弹出栈，并捕获 `EmptyStackException`，它告诉我们我们没有这样做。

```java
try
{
    s.pop();
}
catch (EmptyStackException e)
{
}
```

在我的测试机器上，调用 `isEmpty` 的版本运行了 646 毫秒。捕获 `EmptyStackException` 的版本运行了 21,739 毫秒。如你所见，捕获异常比执行简单的测试花费得多。教训是：仅在异常情况下使用异常。

#### 2. 不要对异常进行微观管理

一些程序员将每个语句都封装在一个独立的 `try` 块中。

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
        // 写入文件问题
    }
}
```

这种方法会极大地增加你的代码量。考虑一下你想让代码完成的任务。在这里，我们想从栈中弹出 100 个数字并将它们保存到文件中。（不用管为什么——这只是一个玩具级示例。）如果出现问题，我们是无能为力的。如果栈是空的，它不会变得被占用；如果文件包含错误，错误也不会魔迹般地消失。因此，将整个任务封装在一个 `try` 块中是有意义的。如果任何一个操作失败，你就可以放弃该任务。

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
    // problem writing to file
}
catch (EmptyStackException e)
{
    // stack was empty
}
```

这段代码看起来整洁得多。它实现了异常处理的一个承诺：将正常处理与错误处理分离。

#### 3. 善用异常的层次结构

不要只抛出一个 `RuntimeException`。找到一个合适的子类或创建你自己的子类。

不要只捕获 `Throwable`。这会让你的代码变得难以阅读和维护。

尊重检查异常（checked exceptions）和未检查异常（unchecked exceptions）之间的区别。检查异常本质上是有种负担的——不要为逻辑错误抛出它们。（例如，反射库就做错了。调用者通常需要捕获他们知道永远不会发生的异常。）

不要犹豫将一个异常转换为另一个更合适的异常。例如，当解析文件中的整数时，捕获 `NumberFormatException` 并将其转换为 `IOException` 或 `MySubsystemException` 的子类。

#### 4. 不要静息异常

在 Java 中，人们有极大的诱惑去掩盖异常。如果你正在编写一个方法，该方法调用了一个可能每世纪才抛出一次异常的方法，编译器会抱怨，因为你没有在方法的 `throws` 列表中声明该异常。你不想把它放在 `throws` 列表中，因为那样编译器会针对所有调用你方法的类进行抱怨。所以你直接把它静音了：

```java
public Image loadImage(String s)
{
    try
    {
        code that threatens to throw checked exceptions
    }
    catch (Exception e)      {} // so there
}
```

现在你的代码可以无障碍地编译了。它会运行良好，除非发生异常。那时，异常将被无声地忽略。如果你认为异常是有重要的，你就应该花精力正确地处理它们。

### 5. 当你检测到错误时，“严厉的爱”比纵容更有效

有些程序员担心在检测到错误时抛出异常。也许当用无效参数调用方法时，返回一个占位值会比抛出异常更好？例如，`Stack.pop` 在栈空时，是应该返回 `null` 还是抛出异常？我认为，在故障发生点抛出 `EmptyStackException` 比在稍后的某个时间发生 `NullPointerException` 要好。

#### 6. 传播异常并不是可耻的标志

有些程序员感到必须捕获所有抛出的异常。如果他们调用一个会抛出异常的方法（例如 `FileInputStream` 构造函数或 `readLine` 方法），他们会本能地捕获可能生成的异常。在很多情况下，传播异常实际上比捕获它更好：

```java
public void readStuff(String filename) throws IOException // not a sign of shame!
{
    var in = new FileInputStream(filename, StandardCharsets.UTF_8);
    . . .
}
```

高层方法通常更具备向用户报告错误或放弃失败命令的能力。

#### 7. 使用标准方法报告空指针和越界异常

`Objects` 类拥有以下方法：

```java
requireNonNull
checkIndex
checkFromToIndex
checkFromIndexSize
```

用于这些常见的检查。使用它们进行参数校验：

```java
public void putData(int position, Object newValue)
{
    Objects.checkIndex(position, data.length);
    Objects.requireNonNull(newValue);
    . . .
}
```

如果使用无效索引或空参数调用方法，将抛出一个异常，并使用 Java 库中熟悉的信息。

#### 8. 不要向终端用户显示堆栈跟踪

如果你的程序遇到意外之外的异常，显示堆栈跟踪似乎是个好主意，这样用户就可以报告它，让你更容易精位问题。然而，堆栈跟踪可能包含你不不想向潜在攻击者暴露的实现细节，例如你正在使用的库版本。

记录堆栈跟踪以便你检索，但只向你的用户显示摘要消息。

> **注意：**
>
> 规则 5 和 6 可以总结为“尽早抛出，晚捕获”。

### 7.4 使用断言

断言（Assertions）是一种常用的惯用法。在接下来的章节中，你将学习如何使用它们。

#### 7.4.1 断言的概念

假设你确信某个属性已满足，你可以使用。例如：

```java
double y = Math.sqrt(x);
```

你确定 `x` 不是负数。Java 语言有一个关键字 `assert`。它有两种形式：

```java
assert condition;
```

以及：

```java
assert condition : expression;
```

这两条语句都会求值条件，如果条件为 `false` 则抛出 `AssertionError`。在第二条语句中，表达式被传递给 `AssertionError` 对象的构造函数，并转换为消息字符串。

断言机制允许你在测试期间插入检查，并在生产环境中自动移除它们。如果你有大量此类检查，程序的运行速度可能会慢很多。

若要断言 `x` 非负数，你可以直接使用语句：

```java
assert x >= 0;
```

或者你可以将 `x` 的实际值传入 `AssertionError` 对象，以便将其显示出来。

```java
assert x >= 0 : x;
```

> **注意：**
>
> *表达式* 部分的唯一目的是生成一个消息字符串。`AssertionError` 对象并不存储实际值，因此你无法查询它。正如 JDK 文档所说，这样做“会鼓励程序员尝试从断言失败中恢复，这违背了初衷”。

> **C++ 注意：**
>
> C 语言的 `assert` 宏会将断言条件转换为一个字符串，当断言失败时，会打印该字符串。例如，如果 `assert(x >= 0)` 失败，它会打印 `"x >= 0"` 是失败的条件。在 Java 中，条件本身不是错误报告的一部分。如果你想看到它，必须作为字符串传递给 `AssertionError` 对象：`assert x >= 0 : "x >= 0"`。

#### 7.4.2 断言的启用与禁用

默认情况下，断言是禁用的。通过在运行程序时使用 `-enableassertions` 或 `-ea` 来启用它们：

```bash
java -enableassertions MyApp
```

注意，你不需要重新编译程序即可启用或禁用断言。启用或禁用断言是*类加载器*的功能。当禁用断言时，类加载器会剥离断言代码，这样就不会影响执行速度。

你甚至可以在特定的类或整个包中开启断言。例如：

```bash
java -ea:MyClass -ea:com.mycompany.mylib MyApp
```

此命令开启类 `MyClass` 以及 `com.mycompany.mylib` 包及其子包中所有类的断言。`-ea...` 选项开启未命名包中所有类的中的断言。

你也可以使用 `-disableassertions` 或 `-da` 选项禁用某些类和包的断言：

```bash
java -ea:... -da:MyClass MyApp
```

某些类不是通过类加载器加载的，而是由虚拟机直接加载。你可以使用这些开关选择性启用或禁用这些类中的断言。

然而，启用或禁用所有断言的 `-ea` 和 `-da` 开关不适用于没有类加载器的“系统类”。使用 `-enablesystemassertions/-esa` 开关来启用系统类中的断言。

还可以通过程序化控制类加载器的断言状态。请参见本节末尾的 API 注释。

Java 库的源代码中有四百多个被注释掉的断言。有些程序员在测试后会注释掉断言，否则它们会占用类文件的空间。如果你担心这一点，可以如下条件地包含它们：

```java
public static final boolean asserts = true; // 生产环境用 false 重新编译

...

if (asserts) assert x >= 0;
```



#### 7.4.3 使用断言进行参数检查

Java 语言提供了三种机制来处理系统故障：

- 抛出异常
- 日志记录
- 使用断言

何时应该选择断言？请记住以下几点：

- 断言失败旨在致命的、不可恢复的错误。
- 断言检查仅在开发和测试期间开启。（这有时被开玩笑地描述为“靠近岸边时穿着救生衣，一旦到了海洋中心就把它扔掉”）

因此，你不应该使用断言来向程序的其他部分发送可恢复的状态信号，或者向程序用户通信问题。断言应该只在测试期间定位内部程序错误。

让我们来看一个常见的场景——方法参数检查。你应该使用断言来检查非法索引值或 `null` 引用吗？回答这个问题，你必须查看方法的文档。假设你实现了一个排序方法。

```java
/**
   按数字升序对指定数组的指定范围进行排序。
   排序范围从 fromIndex（包含）延伸到 toIndex（不包含）。
   @param a 要排序的数组。
   @param fromIndex 要排序的第一个元素的（包含）索引。
   @param toIndex 要排序的最后一个元素的（不包含）索引。
   @throws IllegalArgumentException if fromIndex > toIndex
   @throws ArrayIndexOutOfBoundsException if fromIndex < 0 or toIndex > a.length
*/
static void sort(int[] a, int fromIndex, int toIndex)
```

文档指出，如果索引值不合法，方法将抛出异常。该行为是方法与其调用者之间契约的一部分。如果你实现了该方法，你必须遵守该契约并抛出指定的异常。使用断言代替是不恰当的。

你应该断言 `a` 不为 `null` 吗？这也不合适。方法文档对于 `a` 为 `null` 时方法的行为未作说明。调用者有权假设在这种情况下方法将成功返回，而不会抛出断言错误。

然而，假设方法的契约略有不同：

```java
@param a 要排序的数组（不能为 null）。
```

现在，方法的调用者已被告知，使用 `null` 数组调用该方法是非法的。那么方法可以从断言开始：

```java
assert a != null;
```

计算机科学家将这种契约称为“先置条件”（precondition）。原始方法对其参数没有先置条件——它承诺在所有情况下都有定义的行为。修改后的方法有一个唯一的先置条件：`a` 不为 `null`。如果调用者未能满足先置条件，则一切失效，方法可以执行任何它想做的事。事实上，由于断言的存在，该方法具有未定义的行为。

#### 7.4.4 使用断言记录假设

通常，程序员使用断言来记录他们的假设。考虑这个例子：

```java
if (i == 0) {
    // ...
} else if (i == 1) {
    // ...
} else {
    assert false; // i 必须是 0 或 1
}
```

`assert false` 语句用于记录 `i` 应该是 0 或 1。如果 `i` 是其他任何值，断言将失败并抛出 `AssertionError`。

### 7.5 日志记录

每个 Java 程序员都熟悉在麻烦代码中插入 `System.out.println` 调用以获取程序行为见解的过程。当然，一旦发现了问题的所在，就会移除打印语句，只在下一个问题出现时把它们放回来。日志 API 旨在解决这个问题。以下是该 API 的主要优势：

- 很容易抑制所有日志记录或仅抑制某些级别以下的记录，并且同样容易重新开启它们。
- 抑制的日志开销非常小，因此在应用程序中保留日志代码的代价极小。
- 日志记录可以定向到不同的处理器——例如在控制台中显示、写入文件等。
- 日志记录器和处理器都可以过滤记录。过滤器可以使用实现者提供的任何标准丢弃无趣的日志条目。
- 日志记录可以用不同的方式格式化——例如纯文本或 XML。
- 应用程序可以使用多个日志记录器，并使用类似包名的 `com.mycompany.myapp` 等分级名称。
- 日志配置由配置文件控制。

许多应用程序使用其他日志框架，例如 Log4J 2 (`https://logging.apache.org/log4j/2.x`) 和 Logback (`https://logback.qos.ch`)，它们提供的性能比标准的 Java 日志框架更高。这些框架的 API 略有不同。日志门面（如 SLF4J (`https://www.slf4j.org`) 和 Commons Logging (`https://commons.apache.org/proper/commons-logging`)）提供了统一的 API，使得你可以在不重写应用程序的情况下替换日志框架。更令人困惑的是，Log4J 2 也可以作为使用 SLF4J 组件的门面。在书中，我介绍了标准的 Java 日志框架。它对于许多用途来说已经足够了，学习它的 API 将为你理解其他替代方案做好准备。

**注意：**

从 Java 9 开始，Java 平台拥有一个独立的轻量级日志系统，它不依赖于 `java.logging` 模块（该模块包含标准的 Java 日志框架）。该系统仅供 Java API 使用。如果存在 `java.logging` 模块，日志消息会自动转发到那里。第三方日志框架可以提供适配器来接收平台日志消息。我不介绍平台日志，因为它们不是给应用程序程序员使用的。

#### 7.5.1 基础日志

对于简单的日志，请使用全局日志器并调用其 `info` 方法：

```java
Logger.getGlobal().info("File->Open menu item selected");
```

默认情况下，记录打印如下：

```
May 10, 2013 10:12:15 PM LoggingImageViewer fileOpen
INFO: File->Open menu item selected
```

但如果你在适当的位置（例如 `main` 方法开始处）调用

```java
Logger.getGlobal().setLevel(Level.OFF);
```

所有的日志都会被抑制。

#### 7.5.2 高级日志

现在你已经了解了“小白级日志”，让我们进入工业级日志。在专业应用程序中，你不会希望将所有记录都记录到单个全局日志器中。相反，你可以定义自己的日志器。

调用 `getLogger` 方法来创建或获取日志器：

```java
private static final Logger myLogger = Logger.getLogger("com.mycompany.myapp");
```

**提示：**

没有被变量引用的日志器可能会被垃圾收集。为了防止这种情况，请像上面的示例一样用静态变量保存日志器的引用。

与包名类似，日志器名称是分级的。事实上，它们的层级比包*更*丰富。包和它的父包之间没有语义关系，但日志器的父级和子级共享某些属性。例如，如果你在名为 `"com.mycompany"` 的日志器上设置了日志级别，那么子日志器将继承该级别。

共有七种日志级别：

- `SEVERE`
- `WARNING`
- `INFO`
- `CONFIG`
- `FINE`
- `FINER`
- `FINEST`

默认情况下，前三个级别实际上会被记录。你可以设置一个不同的级别——例如，

```java
logger.setLevel(Level.FINE);
```

现在 `FINE` 及其以上的所有级别都会被记录。

你也可以使用 `Level.ALL` 开启所有级别的日志记录，或使用 `Level.OFF` 关闭所有日志。

所有级别都有对应的日志方法，例如

```java
logger.warning(message);
logger.fine(message);
```

等等以此类推。或者，你可以使用 `log` 方法并提供级别，例如

```java
logger.log(Level.FINE, message);
```

**提示：**

默认日志配置记录所有级别为 `INFO` 或更高的记录。因此，你应该使用 `CONFIG`、`FINE`、`FINER` 和 `FINEST` 级别来记录对诊断有用但对用户无意义的调试消息。

**警告：**

如果你将日志级别设置为比 `INFO` 更细致的值，你还需要更改日志处理器的配置。默认的日志处理器会抑制 `INFO` 以下的消息。详情请见下一节。

默认日志记录会显示包含日志调用的类和方法名，这是从调用栈推断出来的。然而，如果虚拟机优化了执行，可能无法获得准确的调用信息。你可以使用 `logp` 方法来提供调用类和方法的精确位置。该方法签名如下

```java
void logp(Level l, String className, String methodName, String message)
```

有一些用于跟踪执行流的便利方法：

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
   logger.exiting("com.mycompany.mylib.Reader", "read", result);
}
```

**注意：**

从 Java 9 开始，Java 平台拥有一个独立的轻量级日志系统，它不依赖于 `java.logging` 模块（该模块包含标准的 Java 日志框架）。该系统仅供 Java API 使用。如果存在 `java.logging` 模块，日志消息会自动转发到那里。第三方日志框架可以提供适配器来接收平台日志消息。我不介绍平台日志，因为它们不是给应用程序程序员使用的。

### 7.5.3 修改日志管理器配置

你可以通过编辑配置文件来更改日志系统的各种属性。默认配置文件位于 `jdk`/conf/logging.properties`（在 Java 9 之前为 `jre`/lib/logging.properties`）。

```
conf/logging.properties
```

（在 Java 9 之前为 `jre`/lib/logging.properties`）。

要使用另一个文件，启动应用程序时将 `java.util.logging.config.file` 属性设置为文件路径

```
java -Djava.util.logging.config.file=configFile MainClass
```

要更改默认日志级别，编辑配置文件并修改行

```
.level=INFO
```

你可以通过添加如下行来指定自己的日志器的级别

```
com.mycompany.myapp.level=FINE
```

即在日志器名称后附加 `.level` 后缀。

正如你将在本节后面看到的，日志器实际上并没有将消息发送到控制台——那是处理器的工作。处理器也有级别。为了在控制台上看到 `FINE` 消息，你还需要设置

```
java.util.logging.ConsoleHandler.level=FINE
```

**警告：**

日志管理器配置中的设置*不是*系统属性。启动程序时使用 `-Dcom.mycompany.myapp.level=FINE` 对日志器没有任何影响。

日志管理器在虚拟机启动期间进行初始化，在 `main` 方法执行之前完成。如果你想自定义日志属性，但没有使用 `-Djava.util.logging.config.file` 命令行选项启动应用程序，请在程序中调用 `System.setProperty("java.util.logging.config.file", file)`。但随后你还必须调用 `LogManager.getLogManager().readConfiguration()` 来重新初始化日志管理器。

从 Java 9 开始，你可以通过调用以下方法来更新日志配置：

```java
LogManager.getLogManager().updateConfiguration(mapper);
```

新配置将从 `java.util.logging.config.file` 系统属性指定的位置读取。然后，应用 `mapper` 来解析旧配置或新配置中所有键的值。`mapper` 是一个 `Function<String,BiFunction<String,String,String>>`。它将现有配置中的键映射到替换函数。每个替换函数都会接收与键关联的旧值和新值（如果没有关联的值，则为 `null`），并产生一个替换值；如果该键在更新时应被丢弃，则产生 `null`。

这听起来相当复杂，让我们来看几个例子。一个实用的映射方案是合并旧新配置，当一个键同时存在于旧、新配置中时，优先使用新值。此时，`mapper` 为：

```java
key -> ((oldValue, newValue) -> newValue == null ? oldValue : newValue)
```

或者，你可能只想更新以 `com.mycompany` 开头的键，而保持其他键不变：

```java
key -> key.startsWith("com.mycompany")
    ? ((oldValue, newValue) -> newValue)
    : ((oldValue, newValue) -> oldValue)
```

还可以使用 `jconsole` 程序在运行中的程序中更改日志级别。请参 `www.oracle.com/technetwork/articles/java/jconsole-1564139.html#LoggingControl` 获取信息。

**注意：**

日志属性文件由 `java.util.logging.LogManager` 类处理。可以通过设置 `java.util.logging.manager` 系统属性为子类的名称来指定不同的日志管理器。或者，你可以保留标准的日志管理器并仍然跳过日志属性文件的初始化。将 `java.util.logging.config.class` 系统属性设置为以其他方式设置日志管理器属性的类名。更多信息请参见 `LogManager` 类的 API 文档。

#### 7.5.4 本地化

你可能希望对日志消息进行本地化，以便国际用户能够读懂。应用程序的国际化是第二卷第 7 章的主题。简而言之，在本地化日志消息时需要注意以下几点。

本地化的应用程序在*资源包（resource bundles）*中包含针对特定语言区域的信息。资源包由一组针对不同语言区域（如美国或德国）的映射组成。例如，一个资源包可以将字符串 `"readingFile"` 映射为英语字符串 `"Reading file"` 或德语字符串 `"Achtung! Datei wird eingelesen"`。

程序可能包含多个资源包——例如，一个用于菜单，另一个用于日志消息。每个资源包都有一个名称（例如 `"com.mycompany.logmessages"`）。要向资源包中添加映射，请为每个语言区域提供一个文件。英语消息映射位于文件 `com/mycompany/logmessages_en.properties` 文件中，德语消息映射位于 `com/mycompany/logmessages_de.properties` 文件中（`en` 和 `de` 是语言代码）。你将这些文件与应用程序的类文件放在一起，`ResourceBundle` 类就会自动定位它们。这些文件是纯文本文件，由如下条目组成：

```
readingFile=Achtung! Datei wird eingelesen
renamingFile=Datei wird umbenannt
. . .
```

在请求记录器时，你可以指定一个资源包：

```java
Logger logger = Logger.getLogger(loggerName, "com.mycompany.logmessages");
```

然后为日志消息指定资源包键，而不是实际的消息字符串：

```java
logger.info("readingFile");
```

你通常需要将参数包含在本地化消息中。消息中可能包含占位符：`{0}`、`{1}` 等。例如，要在日志消息中包含文件名，可以如下所示使用占位符：

```
Reading file {0}.
```



Achtung! Datei `{0}` wird eingelesen.

然后，要向占位符传递值，请调用以下方法之一：

```
logger.log(Level.INFO, "readingFile", fileName);

logger.log(Level.INFO, "renamingFile", new Object[] { oldName, newName });
```

或者，从 Java 9 开始，你可以在 `logrb` 方法中指定资源包对象（而不是名称）：

```
logger.logrb(Level.INFO, bundle, "renamingFile", oldName, newName);
```

***

![Image](img/note.jpg) **注意：**

这是唯一使用可变参数作为消息参数的日志方法。

***

#### 7.5.5 处理器（Handlers）

默认情况下，记录器将记录发送到 `ConsoleHandler`，将其打印到 `System.err` 流中。具体而言，记录器将记录发送到父级处理器，而最终祖先（名称为 `""`）拥有一个 `ConsoleHandler`。

与记录器一样，处理器也有日志级别。为了记录一条记录，其日志级别必须高于记录器和处理器的阈值。日志管理器配置文件设置默认控制台处理器的日志级别为：

```
java.util.logging.ConsoleHandler.level=INFO
```

要记录 `FINE` 级别的记录，请同时更改记录器和处理器的级别。或者你可以跳过配置并安装自己的处理器。

```
Logger logger = Logger.getLogger("com.myapp");

logger.setLevel(FINE);

logger.setParentHandlers(false);

var handler = new ConsoleHandler();

handler.setLevel(FINE);

logger.addHandler(handler);
```

默认情况下，记录器会将记录同时发送到它的处理器以及父级处理器。我们的记录器是原始记录器（名称为 `""`）的子类，它将 `INFO` 及以上的记录发送到控制台。我们不想重复看到这些记录，因此设置 `useHandlers=false`。

要将记录发送到其他地方，添加另一个处理器。日志 API 提供了实用的处理器：`FileHandler` 和 `SocketHandler`。`SocketHandler` 将记录发送到指定的主机和端口。更有的是收集文件的 `FileHandler`。

你可以简单地将记录发送到默认处理器，如下：

```
var handler = new FileHandler();

logger.addHandler(handler);
```

记录被发送到用户目录下的 `java*n.log` 文件，其中 *n* 是数字。如果系统没有用户目录的概念（例如在 Windows 中），则文件存储在默认位置，如 `C:\Windows`。默认情况下，记录以 XML 格式化。典型的日志记录形式如下：

```xml
<record>
  <date>2002-02-04T07:45:15</date>
  <millis>101283751710</millis>
  <sequence>1</sequence>
  <logger>com.mycompany.myapp</logger>
  <level>INFO</level>
  <class>com.mycompany.mylib.Reader</class>
  <method>read</method>
  <thread>10</thread>
  <message>Reading file corejava.gif</message>
</record>
```

你可以通过在日志管理器配置中设置各种参数（参见表 7.1）或使用另一个构造函数（参见本节末尾的 API 注意）来修改文件处理器的默认行为。

可能不想使用默认文件名。因此，你应该使用另一种模式，例如 `%h/myapp.log.`。（模式变量的解释请参见表 7.2）。

如果多个应用程序（或同一程序的多个副本）使用同一个日志文件，你应该开启 `append` 标志。或者，在文件名模式中使用 `%u`，以便每个应用程序都创建一个唯一的日志副本。

开启文件轮转也是一个好主意。日志文件以循环顺序保存，例如 `myapp.log.0`、`myapp.log.1`、`myapp.log.2` 等。每当文件超过大小限制时，最旧的日志会被删除，其他文件被重命名，并创建一个编号为 `0` 的新文件。

**表 7.1** 文件处理器配置参数

![Images](img/07tab01.jpg)

**表 7.2** 日志文件模式变量

![Images](img/07tab02.jpg)

***

![Image](img/tip.jpg) **表 7.1 提示：**

一些程序员将日志记录作为技术支持人员的辅助。如果程序在现场出现异常，用户可以发回日志文件进行检查。在这种情况下，你应该开启 `append` 标志、使用轮转日志，或两者兼顾。

***

你还可以通过扩展 `Handler` 或 `StreamHandler` 类来定义自己的处理器。我们在本节末尾的示例程序中定义了这样一个处理器。该处理器在窗口中显示记录（参见图 7.2）。

![Images](img/07fig02.jpg)

**图 7.2** 在窗口中显示记录的日志处理器

该处理器扩展了 `StreamHandler` 类并安装了一个流，其 `write` 方法在文本区域中显示流输出。

```
class WindowHandler extends StreamHandler
{
   public WindowHandler()
   {
      . . .
      var output = new JTextArea();
      setOutputStream(new
          OutputStream()
          {
            public void write(int b) {} // 未被调用
            public void write(byte[] b, int off, int len)
            {
                output.append(new String(b, off, len));
            }
          });
   }   . . .
}
```

这种方法只有一个问题——处理器缓存了记录，仅在缓冲区满时将它们写入流。因此，我们重写了 `publish` 方法以便在每条记录后刷新缓冲区：

```
class WindowHandler extends StreamHandler
{
   . . .
   public void publish(LogRecord record)
   {
      super.publish(record);
      flush();
   }
}
```

如果你想编写更奇异的流处理器，可以扩展 `Handler` 类并定义 `publish`、`flush` 和 `close` 方法。

#### 7.5.6 过滤器 (Filters)

默认情况下，根据日志级别进行过滤。每个日志记录和处理器都可以有一个可选的过滤器来执行额外的过滤。要定义过滤器，请实现 `Filter` 接口并定义方法：

```
boolean isLoggable(LogRecord record)
```

使用你需要的任何标准分析日志记录，并对应该包含在日志中的记录返回 `true`。例如，特定的过滤器可能只对 `entering` 和 `exiting` 方法生成的消息感兴趣。此时过滤器应该调用 `record.getMessage()` 并检查它是否以 `ENTRY` 或 `RETURN` 开始。

要将过滤器安装到日志记录或处理器中，只需调用 `setFilter` 方法。请注意，你最多只能有一个过滤器。

#### 7.5.7 格式化器 (Formatters)

`ConsoleHandler` 和 `FileHandler` 类以文本和 XML 格式输出日志记录。然而，你也可以定义自己的格式。你需要扩展 `Formatter` 类并重写方法：

```
String format(LogRecord record)
```

以你喜欢的任何方式格式化记录中的信息并返回生成的字符串。在 `format` 方法中，你可能想要调用方法：

```
String formatMessage(LogRecord record)
```

该方法格式化记录的消息部分，替换参数并应用本地化。

许多文件格式（如 XML）需要包围格式化后记录的头部和尾部。为了实现这一点，请重写方法：

```
String getHead(Handler h)
String getTail(Handler h)
```

最后，调用 `setFormatter` 方法将格式化器安装到处理器中。

#### 7.5.8 日志配方 (A Logging Recipe)

日志记录有这么多选项，很容易忘记基础知识。下面的配方总结了最常用的操作。

1. 对于简单的应用程序，选择单个日志记录器。给日志记录器命名与主应用程序相同的名称是一个主意，例如 `comcompany.myprog`。你始终可以通过调用以下代码获取日志记录器：

```
Logger logger = Logger.getLogger("comcompany.myprog");
```

为了方便起见，你可能想在活动频繁的类中添加静态字段：

```
private static final Logger logger = Logger.getLogger("comcompany.myprog");
```

2. 默认日志配置将所有 `INFO` 或更高级别的消息输出到控制台。用户可以覆盖默认设置，但正如你所看到的，这个过程有点复杂。因此，在你的应用程序中安装更合理的默认设置是一个好主意。以下代码确保所有消息都记录到应用程序特定的文件中。将代码放在应用程序的 `main` 方法中。

```
if (System.getProperty("java.util.logging.config.class") == null
   && System.getProperty("java.util.logging.config.file") == null)
{
   try
   {
      Logger.getLogger("").setLevel(Level.ALL);
      final int LOG_ROTATION_COUNT = 10;
      var handler = new FileHandler("%h/myapp.log", 0, LOG_ROTATION_COUNT);
      Logger.getLogger("").addHandler(handler);
   }
   catch (IOException e)
   {
      logger.log(Level.SEVERE, "无法创建日志文件处理器", e);
   }
}
```

3. 现在你可以准备尽情记录日志了。请记住，所有级别为 `INFO`、`WARNING` 和 `SEVERE` 的消息都会显示在控制台上。因此，将这些级别留给对用户有意义的消息。`FINE` 级别是记录面向程序员消息的良好选择。

当你忍不住调用 `System.out.println` 时，请改为发射一条日志消息：

```
logger.fine("取消文件对话框");
```

记录意外异常也是一个好主意。例如：

```
try
{
   . . .
}
catch (SomeException e)
{
   logger.log(Level.FINE, "解释", e);
}
```

列表 7.2 将此配方付诸实践，并增加了一个：日志消息也会显示在日志窗口中。

**列表 7.2** `logging/LoggingImageViewer.java`

```java
package logging;

import java.awt.*;
import java.awt.event.*;
import java.io.*;
import java.util.logging.*;
import javax.swing.*;

/**
 * 图像查看器程序的修改版，用于记录各种事件。
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
              var handler = new FileHandler("%h/LoggingImageViewer.log", 0, LOG_ROTATION_COUNT);
              Logger.getLogger("com.horstmann.corejava").addHandler(handler);
          }
        catch (IOException e)
          {
              Logger.getLogger("com.horstmann.corejava").log(Level.SEVERE,
                  "Can't create log file handler", e);
          }
      }
      EventQueue.invokeLater(() ->
          {
              var windowHandler = new WindowHandler();
              windowHandler.setLevel(Level.ALL);
              Logger.getLogger("com.horstmann.corejava").addHandler(windowHandler);
              var frame = new ImageViewerFrame();
              frame.setTitle("LoggingImageViewer");
              frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
              Logger.getLogger("com.horstmann.corejava").fine("Showing frame");
              frame.setVisible(true);
        });
    }
}

/**
 * 显示图像的帧.
 */
class ImageViewerFrame extends JFrame
{
    private static int DEFAULT_WIDTH = 300;
    private static int DEFAULT_HEIGHT = 400;
    private JLabel label;
    private static Logger logger = Logger.getLogger("com.horstmann.corejava");

    public ImageViewerFrame()
    {
      logger.entering("ImageViewerFrame", "<init>");
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
      // 设置菜单栏
      var menuBar = new JMenuBar();
      setMenuBar(menuBar);
      var menu = new JMenu("File");
      menuBar.add(menu);
      var openItem = new JMenuItem("Open");
      menu.add(openItem);
      openItem.addActionListener(new FileOpenListener());
      var exitItem = new JMenuItem("Exit");
      menu.add(exitItem);
      exitItem.addActionListener(new ActionListener()
        {
          public void actionPerformed(ActionEvent event)
          {
              logger.fine("Exiting.");
              System.exit(0);
          }
        });
    }
}
```



### 7.5.2 实现日志记录

在示例中，我们展示了如何实现日志记录。以下是一个完整的示例代码：

```java
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

          var chooser = new JFileChooser();

          chooser.setCurrentDirectory(new File("."));

          // 接受所有以 .gif 结尾的文件

          chooser.setFileFilter(new javax.swing.filechooser.FileFilter()

            {

              public boolean accept(File f)

              {

                return f.getName().toLowerCase().endsWith(".gif") || f.isDirectory();

              }

              public String getDescription()

              {

                return "GIF Images";

              }

            });

          // 显示文件选择对话框

          int r = chooser.showOpenDialog(ImageViewFrame.this);

          // 如果接受图像，则将其设置为标签的图标

          if (r == JFileChooser.APPROVE_OPTION)

          {

              String name = chooser.getSelectedFile().getPath();

              logger.log(Level.FINE, "Reading file {0}", name);

              label.setIcon(new ImageIcon(name));

          }

          else logger.fine("File open canceled.");

          logger.exiting("ImageViewerFrame.FileOpenListener", "actionPerformed");

        }

    }

}

/**
 * 在窗口中显示日志记录的处理器.
 */

class WindowHandler extends StreamHandler

{

    private JFrame frame;

    public WindowHandler()

    {

      frame = new JFrame();

      var output = new JTextArea();

      output.setEditable(false);

      frame.setSize(200, 200);

      frame.add(new JScrollPane(output));

      frame.setFocusableWindowState(false);

      frame.setVisible(true);

      setOutputStream(new OutputStream()

        {

          public void write(int b)

          {

          } // 不被调用

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

### `java.util.logging.Logger` (1.4)

- `Logger getLogger(String loggerName)`
- `Logger getLogger(String loggerName, String bundleName)`

获取指定名称的日志记录器。如果不存在，则会创建它。本地化消息位于名为 `bundleName` 的资源程序包中。

- `void severe(String message)`
- `void warning(String message)`
- `void info(String message)`
- `void config(String message)`
- `void fine(String message)`
- `void finer(String message)`
- `void finest(String message)`

根据方法名指定的级别记录日志记录。

- `void entering(String className, String methodName)`
- `void entering(String className, String methodName, Object param)`
- `void entering(String className, String methodName, Object[] param)`
- `void exiting(String className, String methodName)`
- `void exiting(String className, String methodName, Object result)`

记录进入或退出方法，带有给定的参数或返回值。

- `void throwing(String className, String methodName, Throwable t)`

记录抛出给定异常对象的记录。

- `void log(Level level, String message)`
- `void log(Level level, String message, Object obj)`
- `void log(Level level, String message, Object[] objs)`
- `void log(Level level, String message, Throwable t)`

使用给定的级别和消息记录日志，可选包含对象或异常。要包含对象，消息必须包含格式化位符（`{0}`、`{1}` 等）。

- `void logp(Level level, String className, String methodName, String message)`
- `void logp(Level level, String className, String methodName, String message, Object obj)`
- `void logp(Level level, String className, String methodName, String message, Object[] objs)`
- `void logp(Level level, String className, String methodName, String message, Throwable t)`

使用给定的级别、精确的调用者信息和消息记录日志，可选包含对象或异常。

- `void logrb(Level level, String className, String methodName, ResourceBundle bundle, String message, Object... params)` (9)
- `void logrb(Level level, String className, String methodName, ResourceBundle bundle, String message, Throwable thrown)` (9)

记录带有给定级别、精确的调用者信息、资源包和消息的记录，随后是对象或可抛异常（throwable）。

- `Level getLevel()`
- `void setLevel(Level l)`

获取和设置此日志器的级别。

- `Logger getParent()`
- `void setParent(Logger l)`

获取和设置此日志器的父日志器。

- `Handler[] getHandlers()`

获取此日志器的所有的处理器。

- `void addHandler(Handler h)`
- `void removeHandler(Handler h)`

为此日志器添加或移除处理器。

- `boolean getUseParentHandlers()`
- `void setUseParentHandlers(boolean b)`

获取和设置“使用父处理器”属性。如果该属性为 `true`，日志器将所有日志记录转发到其父日志器的处理器。

- `Filter getFilter()`
- `void setFilter(Filter f)`

获取和设置此日志器的过滤器。

### `java.util.logging.Handler` 1.4

- `abstract void publish(LogRecord record)`

将记录发送到目标位置。

- `abstract void flush()`

刷新任何缓冲区中的数据。

- `abstract void close()`

刷新任何缓冲区中的数据并释放所有相关资源。

- `Filter getFilter()`
- `void setFilter(Filter f)`

获取和设置此处理器的过滤器。

- `Formatter getFormatter()`
- `void setFormatter(Formatter f)`

获取和设置此处理器的格式器。

- `Level getLevel()`
- `void setLevel(Level l)`

获取和设置此处理器的级别。

### `java.util.logging.ConsoleHandler` 1.4

- `ConsoleHandler()`

构造一个新的控制台处理器。

### `java.util.logging.FileHandler` 1.4

- `FileHandler(String pattern)`
- `FileHandler(String pattern, boolean append)`
- `FileHandler(String pattern, int limit, int count)`
- `FileHandler(String pattern, int limit, int count, boolean append)`
- `FileHandler(String pattern, long limit, int count, boolean append)` 9

构造一个文件处理器。模式格式参见表 7.2。`limit` 是打开新日志文件之前的最大字节数。`count` 是轮转序列中的文件数量。如果 `append` 为 `true`，则记录应追加到现有的日志文件中。

### `java.util.logging.LogRecord` 1.4

- `Level getLevel()`

获取此记录的日志级别。

- `String getLoggerName()`

获取记录此记录的日志器的名称。

- `ResourceBundle getResourceBundle()`
- `String getResourceBundleName()`

获取用于消息本地化的资源包（或其名称），如果没有提供，则返回 `null`。

- `String getMessage()`

获取本地化或格式化之前的“原始”消息。

- `Object[] getParameters()`

获取参数对象，如果没有提供，则返回 `null`。

- `Throwable getThrown()`

获取抛出的对象，如果没有提供，则返回 `null`。

- `String getSourceClassName()`
- `String getSourceMethodName()`

获取记录此记录的代码位置。此信息可能由日志代码提供，也可以从运行时堆栈中自动推断。如果日志代码提供了错误的值或运行代码经过了优化导致无法推断出确切位置，则该信息可能不准确。

- `long getMillis()`

获取自 1970 年以来的毫秒创建时间。

- `Instant getInstant()` 9

获取 `java.time.Instant` 类型的创建时间（参见卷二的第 6 章）。

- `long getSequenceNumber()`

获取此记录的唯一序列号。

- `long getLongThreadID()` 16

获取创建此记录的线程唯一 ID。这些 ID 由 `LogRecord` 类分配，与其他线程 ID 无关。（`getThreadID` 方法返回 `int` 类型 ID。它现已过时，因为长时间运行的程序可能会生成超过 `Integer.MAX_VALUE` 个日志记录。）

### `java.util.logging.LogManager` 1.4

- `static LogManager getLogManager()`

获取全局 `LogManager` 实例。

- `void readConfiguration()`
- `void readConfiguration(InputStream in)`

从系统属性 `java.util.logging.config.file` 指定的文件或给定的输入流中读取日志配置。

- `void updateConfiguration(InputStream in, Function<String,BiFunction<String,String,String>> mapper)` 9
- `void updateConfiguration(Function<String,BiFunction<String,String,String>> mapper)` 9

将日志配置与系统属性 `java.util.logging.config.file` 指定的文件或给定的输入流合并。关于 `mapper` 参数的描述，参见第 424 页的第 7.5.3 节“更改日志管理器配置”。

### `java.util.logging.Filter` 1.4

- `boolean isLoggable(LogRecord record)`

如果给定的日志应该记录，则返回 `true`。

### `java.util.logging.Formatter` 1.4

- `abstract String format(LogRecord record)`

返回格式化日志记录后的字符串。

- `String getHead(Handler h)`
- `String getTail(Handler h)`

返回日志记录头部和尾部的字符串。`Formatter` 基类定义这些方法为空字符串；必要时可以重写。

- `String formatMessage(LogRecord record)`

返回日志记录的本地化和格式化部分。

### 7.6 调试技巧

假设你写了一个程序并通过捕获所有异常使其变得健壮。现在你运行它，但没有正常工作。现在怎么办？（如果你没有这个问题，可以跳过本章。）

当然，如果有方便且强大的调试器最好。调试器可以在 Eclipse、IntelliJ 和 NetBeans 等开发环境中。在本节中，我提供了一些值得尝试的技巧。

1. 你可以使用如下代码打印或记录变量的值：

```java
System.out.println("x=" + x);
```

或者

```java
Logger.getGlobal().info("x=" + x);
```

如果 `x` 是数字，会被转换。如果 `x` 是对象，Java 会调用它的 `toString` 方法。为了获取隐式参数的状态，打印 `this` 对象：

```java
Logger.getGlobal().info("this=" + this);
```

Java 库中的大多数类都非常用心重写了 `toString` 方法以提供有用信息。这对于调试非常有帮助。你应该在类中付出同样的努力。

2. 一个不为人知但非常有用的技巧是在每个类中放置一个独立的 `main` 方法。在方法内部，你可以编写一个单元测试存根来隔离测试该类。

```java
public class MyClass

{

    方法和字段

    . . .

    public static void main(String[] args)

    {

      测试代码

    }

}
```



创建几个对象，调用所有方法，并检查每个方法是否运行正确。你可以保留这些 `main` 方法，并单独启动每个文件的虚拟机来运行测试。当你运行 applet 时，这些 `main` 方法都不会被调用。当你运行应用程序时，虚拟机只调用启动类的 `main` 方法。

3. 如果你喜欢上面的技巧，你应该检查 [`http://junit.org`](http://junit.org) 的 JUnit。JUnit 是一个非常流行的单元测试框架，便于组织测试用例。每当你修改类时运行测试，每当发现 bug 时添加另一个测试用例。

4. *日志代理*是一个子类对象，它可以拦截方法调用、记录日志并调用基类。例如，如果你在 `Random` 类的 `nextDouble` 方法上遇到问题，可以创建一个匿名子类的实例作为代理对象：

```java
var generator = new Random()
{
    public double nextDouble()
    {
        double result = super.nextDouble();
        Logger.getGlobal().info("nextDouble: " + result);
        return result;
    }
};
```

每当调用 `nextDouble` 方法时，都会生成一条日志。

要找出是谁调用了该方法，可以生成堆栈跟踪（stack trace）。

### 5. 你可以通过 `Throwable` 类中的 `printStackTrace` 方法从任何异常对象获取堆栈跟踪。以下代码捕获任何异常，打印异常对象和堆栈跟踪，并重新抛出异常，以便其找到预期的处理器。

```java
try
{
   . . .
}
catch (Throwable t)
{
   t.printStackTrace();
   throw t;
}
```

你甚至不需要捕获异常即可生成堆栈跟踪。只需在代码任何位置插入语句

```java
Thread.dumpStack();
```

即可获取堆栈跟踪。

### 6. 通常，堆栈跟踪显示在 `System.err` 上。如果你想记录或显示堆栈跟踪，可以按照以下方法将其捕获到字符串：

```java
var out = new StringWriter();
new Throwable().printStackTrace(new PrintWriter(out));
String description = out.toString();
```

### 7. 将程序错误捕获到文件中通常方便。然而，错误被发送到 `System.err` 而不是 `System.out`。因此，你不能简单地通过运行来捕获它们：

```bash
java MyProgram > errors.txt
```

相反，应将错误流捕获为

```bash
java MyProgram 2> errors.txt
```

要在同一个文件中捕获 `System.err` 和 `System.out`，请使用

```bash
java MyProgram 1> errors.txt 2>&1
```

这在 `bash` 和 Windows shell 中均有效。

### 8. 让未捕获异常的堆栈跟踪显示在 `System.err` 中并不理想。如果终端用户恰好看到这些信息，他们会感到困惑，而且当你需要它们进行诊断时无法获取。更好的方法是将它们记录到文件中。你可以通过静态方法 `Thread.setDefaultUncaughtExceptionHandler` 更改未捕获异常的处理器：

```java
Thread.setDefaultUncaughtExceptionHandler(
    new Thread.UncaughtExceptionHandler()
    {
        public void uncaughtException(Thread t, Throwable e)
        {
            // 将信息保存到日志文件中
        };
    });
```

### 9. 要监控类加载，请使用 `-verbose` 标志启动 Java 虚拟机。你将获得如下的输出：

```
[0.012s][info][class,load] opened: /opt/jdk-11.0.1/lib/modules
[0.034s][info][class,load] java.lang.Object source: jrt:/java.base
[0.035s][info][class,load] java.io.Serializable source: jrt:/java.base
[0.035s][info][class,load] java.lang.Comparable source: jrt:/java.base
[0.035s][info][class,load] java.lang.CharSequence source: jrt:/java.base
[0.035s][info][class,load] java.lang.String source: jrt:/java.base
[0.036s][info][class,load] java.lang.reflect.AnnotatedElement source: jrt:/java.base
[0.036s][info][class,load] java.lang.reflect.GenericDeclaration source: jrt:/java.base
[0.036s][info][class,load] java.lang.reflect.Type source: jrt:/java.base
[0.036s][info][class,load] java.lang.Class source: jrt:/java.base
[0.036s][info][class,load] java.lang.Cloneable source: jrt:/java.base
[0.037s][info][class,load] java.lang.ClassLoader source: jrt:/java.base
[0.037s][info][class,load] java.lang.System source: jrt:/java.base
[0.037s][info][class,load] java.lang.Throwable source: jrt:/java.base
[0.037s][info][class,load] java.lang.Error source: jrt:/java.base
[0.037s][info][class,load] java.lang.ThreadDeath source: jrt:/java.base
[0.037s][info][class,load] java.lang.Exception source: jrt:/java.base
[0.037s][info][class,load] java.lang.RuntimeException source: jrt:/java.base . . .
```

这偶尔对诊断 `class-path` 问题很有帮助。

### 10. `-Xlint` 选项告诉编译器发现常见的代码问题。例如，如果你使用命令编译

```bash
javac -Xlint sourceFiles
```

编译器将报告 `switch` 语句中缺失的 `break` 语句。（“lint”一词最初描述一种用于定位 C 程序中潜在问题的工具，但现在泛指任何标记可疑但非法的构造的工具。）

你将得到类似如下的消息：

```
warning: [fallthrough] possible fall-through into case
```

方括号中的字符串标识了警告类别。你可以启用或禁用每个类别。由于大多数类别都非常有用，最好的方法似乎保留所有类别，并仅禁用你不在乎的，如下所示：

```bash
javac -Xlint:all,-fallthrough,-serial sourceFiles
```

Java 5 中引入的泛型是 Java 编程语言自发布以来最重大的变化。一个主要的设计目标是与早期版本后兼容。因此，Java 泛型具有一些不方便的局限性。在本章中，你将学习泛型编程的优势和挑战。

## 8.1 为什么要用泛型编程？

`Generic programming`（泛型编程）意味着编写可以重用于许多不同类型对象的代码。例如，你不想编写单独的类来分别收集 `String` 和 `File` 对象。而且你也不需要这样做——单一的 `ArrayList` 类就可以收集任何类的对象。这就是泛型编程的一个示例。

实际上，Java 在拥有泛型类之前就已经有一个 `ArrayList` 类了。让我们来调查一下泛型编程机制是如何演变的，以及这对于用户和实现者来说意味着什么。

#### 8.1.1 类型参数的优势

在 Java 引入泛型类之前，泛型编程是通过 `inheritance`（继承）实现的。`ArrayList` 类简单地维护了一个 `Object` 引用数组：

```java
public class ArrayList // 泛型类出现之前
{
   private Object[] elementData;
   . . .
   public Object get(int i) { . . . }
   public void add(Object o) { . . . }
}
```

这种方法有两个问题。每当你检索一个值时，都需要进行强制类型转换：

```java
ArrayList files = new ArrayList(); . . .
String filename = (String) files.get(0);
```

此外，没有错误检查。你可以添加任何类的值：

```java
files.add(new File(". . ."));
```

此调用可以通过编译并运行而不会报错。在其他地方，将 `get` 的结果强制转换为 `String` 将导致错误。

泛型提供了一个更好的解决方案：`type parameters`（类型参数）。`ArrayList` 类现在有一个类型参数，用于指示元素类型：

```java
var files = new ArrayList<String>();
```

这使得你的代码更易读。你可以立即看出这个特定的列表包含 `String` 对象。

* *

![Image](img/note.jpg) **注意：**

如果你使用显式类型而不是 `var` 来声明变量，则可以通过使用“菱形”语法在构造函数中省略类型参数：

```java
ArrayList<String> files = new ArrayList<>();
```

省略的类型是从变量的类型推断出来的。

Java 9 将菱形语法的使用范围扩展到了以前不被接受的场景。例如，你现在可以在匿名子类中使用菱形：

```java
ArrayList<String> passwords = new ArrayList<>() // Java 9 中可以使用菱形
   {
      public String get(int n) { return super.get(n).replaceAll(".", "*"); }
   };
```

* *

编译器也可以很好地利用类型信息。调用 `get` 不需要强制转换。编译器知道返回类型是 `String` 而不是 `Object`：

```java
String filename = files.get(0);
```

编译器还知道 `ArrayList<String>` 的 `add` 方法有一个类型为 `String` 的参数。这比使用 `Object` 参数要安全得多。现在编译器可以检查你没有插入错误类型的对象。例如，语句

```java
files.add(new File(". . .")); // ArrayList<String> 只能添加 String 对象
```

该语句将无法编译。编译错误比运行时的类类型转换异常（class cast exception）要好得多。

这就是类型参数的魅力：它们让你的程序更易读、更安全。

#### 8.1.2 谁想做泛型程序员？

使用像 `ArrayList` 这样的泛型类很容易。大多数 Java 程序员会直接使用 `ArrayList<String>` 等类型，就像它们内置在语言中一样，类似于 `String[]` 数组。（当然，列表比数组更好，因为它们可以自动扩展。）

然而，实现一个泛型类并不容易。使用你代码的程序员想要为你的类型参数接入各种类。他们期望一切在没有繁琐限制和困惑错误信息的情况下正常工作。因此，作为一名泛型程序员，你的工作是预测你的类的所有可能的未来用途。

### 8.2 定义一个简单的泛型类

`generic class`（泛型类）是一个有一个或多个类型变量的类。在本章中，我们使用一个简单的 `Pair` 类作为示例。这允许我们关注泛型，而不会被数据细节分散注意力。以下是 `Pair` 类的代码：

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

`Pair` 类在类名后引入了一个封装在角括号 `< >` 中的类型变量 `T`。泛型类可以有多个类型变量。例如，我们可以为第一个和第二个字段使用不同的类型来定义 `Pair` 类：

```java
public class Pair<T, U> { . . . }
```

类型变量贯穿整个类定义，用于指定方法的返回类型以及字段和局部变量的类型。例如：

```java
private T first; // 使用类型变量
```

* *

![Image](img/note.jpg) **注意：**

使用大写字母作为类型变量是常见做法，并保持简短。Java 库使用 `E` 作为集合的元素类型，使用 `K` 和 `V` 作为表格的键和值类型，使用 `T`（必要时使用相邻字母 `U` 和 `S`）表示“任何类型”。

* *

你通过用类型替换类型变量来 `instantiate`（实例化）泛型类型，例如

```java
Pair<String>
```

你可以将结果认为是一个带有构造函数的普通类：

```java
Pair<String>()
Pair<String>(String, String)
```

```java
String getFirst()
String getSecond()
void setFirst(String)
void setSecond(String)
```

换句话说，泛型类充当了普通类的工厂。

列表 8.1 中的程序让 `Pair` 类发挥作用。静态方法 `minmax` 遍历数组并同时计算最小值和最大值。它使用 `Pair` 对象来返回这两个结果。回想 `compareTo` 方法比较两个字符串：如果字符串相同则返回 `0`；如果第一个字符串在字典顺序上排在第二个之前，则返回负整数；否则返回正整数。

***

![Image](img/c.jpg) **C++ 备注：**

从表面上看，Java 中的泛型类与 C++ 中的模板类相似。唯一的区别是 Java 没有特殊的 `template` 关键字。然而，正如你将在本章中将看到的，这两种机制之间存在显著差异。

***

### 列表 8.1 `pair1/PairTest1.java`

```java
 1  package pair1;
 2
 3  /**
 4    * @version 1.01 2012-01-26
 5    * @author Cay Horstmann
 6    */
 7  public class PairTest1
 8  {
 9      public static void main(String[] args)
10     {
11         String[] words = { "Mary", "had", "a", "little", "lamb" };
12         Pair<String> mm = ArrayAlg.minmax(words);
13         System.out.println("min = " + mm.getFirst());
14         System.out.println("max = " + mm.getSecond());
15     }
16  }
17
18  class ArrayAlg
19  {
20      /**
21       * 获取字符串数组的最小值和最大值。
22       * @param a 字符串数组
23       * @return 一个包含最小和最大值的对，如果 a 为空或为空则返回 null
24       */
25      public static Pair<String> minmax(String[] a)
26      {
```



### 8.3 泛型方法

在前面的节中，你已经学习了如何定义泛型类。你也可以定义带有类型参数的单个方法。

```java
class ArrayAlg
{
  public static <T> getMiddle(T... a)
  {
    return a[a.length / 2];
  }
}
```

该方法定义在普通类内部，而不是泛型类内部。然而，它是泛型方法，正如你从尖括号和类型变量所看到的那样。注意，类型变量插入在修饰符（`public static`）之后、返回类型之前。

你可以在普通类和泛型类中都定义泛型方法。当你调用泛型方法时，可以在方法名之前放置用尖括号括起来实际类型：

```java
String middle = ArrayAlg.<String>getMiddle("John.", "Q.");
```

在这种情况下（实际上在大多数情况下都是），你可以从方法调用中省略 `<String>` 参数。编译器有足够的信息来推断你想要的方法。它将参数类型与泛型类型 `T` 进行匹配，并推断出 `T` 必须是 `String`。也就是说，你可以简单地调用：

```java
String middle = ArrayAlg.getMiddle("John.", "Q.");
```

在几乎所有的情况下，泛型方法的类型推断都能顺利工作。偶尔编译器会出错，这时你需要解读错误报告。考虑这个例子：

```java
double middle = ArrayAlg.getMiddle(3.14, 27, 0);
```

错误信息用一种晦涩的术语（因编译器而异）抱怨道，这段代码有两种解释方式，且都是有效的。简而言之，编译器将参数自动装箱为 `Double` 和 `Integer` 对象，然后尝试寻找这些类的公共父类型。它实际上找到了两个：`Number` 和 `Comparable` 接口，而后者本身是一个泛型类型。在这种情况下，解决办法是将所有参数写为 `double` 值。

***

![Image](img/tip.jpg) **提示：**

Peter von Milch 建议，如果你想查看编译器为泛型方法推断哪种类型，可以使用这个小技巧：故意引入一个错误并研究由此产生的错误信息。例如，考虑调用 `ArrayAlg.getMiddle("Hello", 0, null)`。将结果赋值给 `JButton`，这显然是不可能的。你会得到一个错误报告：

```
found: java.lang.Object, java.io.Serializable, java.lang.Comparable<?>
```

用通俗的话的话说，你可以将结果赋值给 `Object`、`Serializable` 或 `Comparable`。

***

***

![Image](img/c.jpg) **C++ 备注：**

从表面上看，Java 中的泛型类与 C++ 中的模板类相似。唯一而易见的区别是 Java 没有特殊的 `template` 关键字。然而，正如你将在本章中将看到的，这两种机制之间存在显著差异。

***

### 列表 8.1 `pair1/PairTest1.java`

（此处代码块已在上方提供，无需重复）

### 8.4 类型变量的边界

有时类或方法需要对类型变量进行限制。这里有一个典型的例子。我们想要计算数组的最小值和最大值：

```java
class ArrayAlg
{
    /**
     * 获取字符串数组的最小值和最大值。
     * @param a 字符串数组
     * @return 一个包含最小和最大值的对，如果 a 为空或为空则返回 null
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

但是，如何知道 `T` 所属的类具有 `compareTo` 方法呢？解决办法是给 `T` 设定一个边界：

```java
public static <T extends Comparable> T min(T[] a)
```

`Comparable` 接口本身就是一个泛型类型。目前，请忽略这种复杂性以及编译器生成的警告。8.8 节 第 475 页讨论了如何正确地与 `Comparable` 使用类型参数。

现在，泛型 `min` 方法只能与实现了 `Comparable` 接口类的数组调用，例如 `String`、`LocalDate` 等。使用 `Rectangle` 数组调用 `min` 是编译错误，因为 `Rectangle` 类没有实现 `Comparable`。

***

***

![Image](img/c.jpg) **C++ 备注：**

在 C++ 中，你无法限制模板的类型。如果程序员用不恰类型实例化模板，模板代码内部会报告（通常是晦涩的）错误信息。

***

你可能会奇怪，为什么在这种情况下使用 `extends` 关键字而不是 `implements` 关键字——毕竟 `Comparable` 是一个接口。这种符号

```
<T extends BoundingType>
```

表示 `T` 应该是边界类型的**子类型**。`T` 和边界类型都可以是类或接口。选择 `extends` 关键字是因为它是子类型概念的合理近似，而且 Java 设计者不想向语言中添加新的关键字（如 `sub`）。

类型变量或通配符可以有多个边界。例如：

```java
T extends Comparable & Serializable
```

边界类型之间使用和符号（`&`）分隔，因为逗号用于分隔类型变量。

与 Java 继承一样，你可以有任意多个接口父类型，但边界中最多只能有一个类。如果你有一个类作为边界，它必须是边界列表中的第一个。

在下一个示例程序 (Listing 8.2) 中，我们将 `minmax` 方法重写为泛型。该方法计算泛型数组的最小值和最大值，返回一个 `Pair<T>`。

### Listing 8.2 `pair2/PairTest2.java`

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
            LocalDate.of(1903, 12, 3), // J. von Neumann
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
     * @param a 一个类型为 T 的对象数组
     * @return 一个包含最小值和最大值的对，如果 a 为 null 或空，则返回 null
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

虚拟机并不拥有泛型类型的对象——所有对象都属于普通类。泛型实现的早期版本能够将一个使用泛型的程序编译成可以在 1.0 虚拟机上执行的类文件！在接下来的章节中，你将看到编译器是如何“擦除”类型参数的，以及这一过程对 Java 有什么影响。

#### 8.5.1 类型擦除

每当你定义一个泛型类型，系统会自动提供一个对应的原始类型（raw type）。原始类型的名称仅仅是泛型类型的名称，去掉了类型参数。类型变量被擦除，并替换为它们的边界类型（bounding types）（对于没有边界的变量，替换为 `Object`）。

例如，`Pair<T>` 的原始类型如下：

```java
class Pair
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

由于 `T` 是无边界类型，它被简单替换为 `Object`。结果是一个普通类，就像你在 Java 引入泛型之前可能实现的那样。你的程序可能包含不同类型的 `Pair`，例如 `Pair<String>` 或 `Pair<LocalDate>`，但擦除将它们都变成了原始的 `Pair` 类型。

**注意：** 在这方面，Java 泛型与 C++ 模板非常不同。C++ 为每个实例化产生不同的类型——这种现象被称为“模板膨胀（template bloat）”。Java 则不会受到这个问题的影响。

原始类型将类型变量替换为第一个边界，如果没有给出边界，则替换为 `Object`。例如，类 `Pair<T>` 中的类型变量没有边界，因此原始类型将 `T` 替换为 `Object`。假设我们声明一个略有不同的类型：

```java
class Interval<T extends Comparable & Serializable> implements Serializable
{
    private T lower;
    private T upper;
    . . .
    public Interval(T first, T second)
    {
        if (first.compareTo(second) <= 0) { lower = first; }
        else { upper = second; }
    }
}
```

原始类型 `Interval` 如下：

```java
class Interval implements Serializable
{
    private Comparable lower;
    private Comparable upper;
    . . .
    public Interval(Comparable first, Comparable second) { . . }
}
```

**注意：** 你可能会好奇，如果切换边界会发生什么：`Interval<T extends Serializable & Comparable>`。在这种情况下，原始类型将 `T` 替换为 `Serializable`，编译器会在必要时插入到 `Comparable` 的强制转换。为了效率起见，你应该将标记接口（即不含方法的接口）放在边界列表的末尾。

#### 8.5.2 翻译泛型表达式

当你编写对泛型方法的调用时，如果返回类型被擦除，编译器会插入强制转换。例如，考虑以下语句序列：

```java
Pair<Employee> buddies = . . .;
Employee buddy = buddies.getFirst();
```

`getFirst()` 的擦除返回类型为 `Object`。编译器会自动插入到 `Employee` 的强制转换。也就是说，编译器将该方法调用翻译为两条虚拟机指令：

- 调用原始方法 `getFirst`
- 将返回的 `Object` 强制转换为 `Employee`

在访问泛型字段时也会插入强制转换。假设 `Pair` 类的 `first` 和 `second` 字段是公共的（这可能不是好的编程风格，但在 Java 中是合法的）。那么表达式

```java
Employee buddy = buddies.first;
```

生成的字节码中也包含了强制转换。

#### 8.5.3 翻译泛型方法

类型擦除也适用于泛型方法。程序员通常将这样的泛型方法

```java
public static <T extends Comparable> T min(T[] a)
```

视为一组方法，但在擦除后，只留下一个方法：

```java
public static Comparable min(Comparable[] a)
```

注意类型参数 `T` 被擦除了，留下了它的边界类型 `Comparable`。

方法的擦除带来了一些复杂度。考虑这个示例：

```java
class DateInterval extends Pair<LocalDate>
{
    public void setSecond(LocalDate second)
    {
        if (second.compareTo(getFirst())) >= 0) {
            super.setSecond(second);
        }
    }
    . . .
}
```

日期区间是 `LocalDate` 对象的对，我们希望重写方法以确保第二个值永远不会小于第一个。该类被擦除为：

```java
class DateInterval extends Pair // 擦除后
{
    public void setSecond(LocalDate second) { . . . }
    . . .
}
```

令人惊讶的是，从 `Pair` 继承了另一个 `setSecond` 方法，即：

```java
public void setSecond(Object second)
```

这是一个显然不同的方法（参数类型是 `Object` 而不是 `LocalDate`）。但它*不应该*是不同的。为了解决这个问题，编译器在 `DateInterval` 类中生成了一个桥接方法（bridge method）：

```java
public void setSecond(Object second) { setSecond((LocalDate) second); }
```



为了理解为什么这有效，让我们仔细跟踪语句的执行过程：

```java
pair.setSecond(aDate)
```

变量`pair`被声明类型为`Pair<LocalDate>`，而该类型只有一个名为`setSecond`的方法，即`setSecond(Object)`。虚拟机在`pair`所引的对象上调用该方法。该对象的类型为`DateInterval`。因此，调用了`DateInterval.setSecond(Object)`。该方法是生成的桥接方法（bridge method）。它调用了`DateInterval.setSecond(LocalDate)`，这正是我们想要的。

桥接方法更加诡。假设`DateInterval`类也重写了`getSecond`方法：

```java
class DateInterval extends Pair<LocalDate>
{
   public LocalDate getSecond() { return (LocalDate) super.getSecond(); }
   . . .
}
```

在`DateInterval`类中，有两个`getSecond`方法：

```java
LocalDate getSecond() // 定义在 DateInterval 中
Object getSecond() // 重写了 Pair 中定义的方法以调用第一个方法
```

你不能编写这样的 Java 代码；拥有两个相同参数类型（在此处为均为无参数）的方法是非法的。然而，在虚拟机中，参数类型*和返回类型*共同决定了一个方法。因此，编译器可以为两个仅返回类型不同的方法生成字节码，而虚拟机将正确处理这种情况。

* * *

![Image](img/note.jpg) **注意：**

桥接方法不仅限于泛型。你已经在第 5 章中看到，在重写另一个方法时，指定更严格的返回类型是合法的。例如：

```java
public class Employee implements Cloneable
{
   public Employee clone() throws CloneNotSupportedException { . . . }
}
```

`Object.clone`和`Employee.clone`方法被称为具有协变返回类型。

实际上，`Employee`类有*两个* clone 方法：

```java
Employee clone() // 上文定义
Object clone() // 生成的桥接方法，重写了 Object.clone
```

生成的桥接方法调用新定义的方法。

* * *

总结，你需要记住关于 Java 泛型翻译的事实：

- 虚拟机中没有泛型，只有普通的类和方法。
- 所有类型参数都被替换为它们的边界（bounds）。
- 生成桥接方法是为了保持多态性。
- 在需要时插入强制转换以保持类型安全。

## 8.5.4 调用遗留代码

在设计 Java 泛型时，一个主要目标是允许泛型与遗留代码之间的交互。让我们来看这种遗留代码的具体示例。Swing 用户界面工具包提供了`JSlider`类，其“刻度”可以使用包含文本或图像的标签进行自定义。标签通过以下调用设置：

```java
void setLabelTable(Dictionary table)
```

`Dictionary`类将整数映射到标签。在 Java 5 之前，该类实现为`Object`实例的映射。Java 5 将`Dictionary`变成了泛型类，但`JSlider`从未更新过。此时，没有类型参数的`Dictionary`是原始类型（raw type）。这就是兼容性发挥的地方。

当你填充字典时，可以使用泛型类型。

```java
Dictionary<Integer, Component> labelTable = new Hashtable<>();
labelTable.put(0, new JLabel(new ImageIcon("nine.gif")));
labelTable.put(20, new JLabel(new ImageIcon("ten.gif")));
. . .
```

当你将`Dictionary<Integer, Component>`对象传递给`setLabelTable`时，编译器会发出警告。

```java
slider.setLabelTable(labelTable); // 警告
```

毕竟，编译器无法保证`setLabelTable`可能会对`Dictionary`对象做什么。该方法可能会将所有键替换为字符串。这破坏了键类型为`Integer`的保证，未来的操作可能会导致强制类型转换异常（bad cast exceptions）。

你应该思考并询问`JSlider`实际上要对这个`Dictionary`对象做什么。在我们的案例中，很明显`JSlider`只是读取信息，所以你可以忽略该警告。

现在考虑相反的情况，即你从遗留类获取一个原始类型的对象。你可以将其赋值给类型使用泛型的变量，但当然你会收到一个警告。例如：

```java
Dictionary<Integer, Components> labelTable = slider.getLabelTable(); // 警告
```

这没关系——检查警告并确保标签表确实包含`Integer`和`Component`对象。当然，这不存在绝对的保证。恶意的代码编写可能在滑块中安装了不同的`Dictionary`。但同样，这种情况并不比泛型出现之前更糟。在最坏的情况下，你的程序将抛出异常。

当你思考完该警告后，可以使用一个*注解*（annotation）让它消失。你可以对局部变量进行注解：

```java
@SuppressWarnings("unchecked")
Dictionary<Integer, Components> labelTable = slider.getLabelTable(); // 无警告
```

或者你可以注解整个方法，如下：

```java
@SuppressWarnings("unchecked")
public void configureSlider() { . . . }
```

此注解关闭对方法内部所有代码的检查。

## 8.6 限制与局限性

在后续章节中，我将讨论在使用 Java 泛型时需要考虑的若干限制。这些限制大部分是类型擦除（type erasure）的后果。

### 8.6.1 类型参数不能用基本类型实例化

你不能用基本类型替换类型参数。你不能用基本类型替换类型参数。因此，没有`Pair<>`。其原因是类型擦除。这确实是一种困扰，但与 Java 语言中的基本类型是一致的。这不是致命缺陷。

### 8.6.2 运行时类型检查仅适用于原始类型

虚拟机中的对象始终具有特定的非泛型类型。因此，所有的类型检查都产生原始类型。例如，

```java
if (a instanceof Pair<String>) // 错误
```

只能测试`a`是否为任何类型的`Pair`。同样适用于：

```java
if (a instanceof Pair<T>) // 错误
```

或强制转换：

```java
Pair<String> p = (Pair<String>) a; // 警告
```

同样的，`getClass()`方法始终返回原始类型。例如：

```java
Pair<String> stringPair = . . .;
Pair<Employee> employeePair = . . .;
if (stringPair.getClass() == employeePair.getClass()) // 它们相等
```

比较结果为`true`，因为两次调用`getClass`都返回`Pair.class`。

### 8.6.3 不能创建泛化数组

你不能实例化泛化数组，例如：

```java
var table = new Pair<String>[10]; // 错误
```

这有什么问题？擦除后，`table`的类型是`Pair[]`。你可以将其转换为`Object[]`：

```java
Object[] objarray = table;
```

数组记得其组件类型，如果你尝试存储错误类型的元素，它会抛出`ArrayStoreException`：

```java
objarray[0] = "Hello"; // 错误--组件类型是 Pair
```

但擦除使得这种机制对泛型失效。赋值操作

```java
objarray[0] = new Pair<Employee>();
```

会通过数组存储检查，但仍会导致类型错误。由于这个原因，泛化数组是非法的。

注意，只有创建这些数组是非法的。你可以声明一个类型为`Pair<String>[]`的变量。但你不能用`new Pair<String>[10]`来初始化它。

```java
var table = (Pair<String>[]) new Pair<?>[10];
```

结果是不安全的。如果你在`table[0]`中存储一个`Pair<Employee>`，然后对`table[0].getFirst()`调用`String`方法，就会得到一个`ClassCastException`。

* * *

![Image](img/tip.jpg) **提示：**

如果你需要收集泛化类型对象，只需使用`ArrayList`：`ArrayList<Pair<String>>`是安全且有效的。

* * *

### 8.6.4 变长参数警告

在前面的节中，你看到 Java 不支持泛型数组。在本节中，我将讨论一个相关问题：将泛型实例传递给具有变长参数的方法。

考虑下面这个简单的变长参数方法：

```java
public static <T> void addAll(Collection<T> coll, T... ts)
{
   for (T t : ts) coll.add(t);
}
```

记住参数`ts`实际上是一个持有所有提供参数的数组。

现在考虑这个调用：

```java
Collection<Pair<String>> table = . . .;
Pair<String> pair1 = . . .; Pair<String> pair2 = . . .;
addAll(table, pair1, pair2);
```

为了调用此方法，Java 虚拟机必须创建一个`Pair<String>`数组，这是不符合规则的。然而，规则在这种情况下被放宽了，你只会得到一个警告而不是错误。

你可以通过两种方式之一抑制警告。你可以在包含调用`addAll`方法的方法上添加`@SuppressWarnings("unchecked")`注解。或者从 Java 7 开始，你可以在`addAll`方法本身上标记`@SafeVarargs`：

```java
@SafeVarargs
public static <T> void addAll(Collection<T> coll, T... ts)
```

现在现在用泛型类型调用此方法了。你可以将此注解用于任何仅读取参数数组元素的方法，这被认为是最常见的用例。

`@SafeVarargs`只能用于构造函数和为`static`、`final`或（从 Java 9 开始）`private`的方法。任何其他方法都可以被重写，导致该注解失去意义。

* * *

![Image](img/note.jpg) **注意：**

你可以使用`@SafeVarargs`注解来绕过泛型数组创建限制，使用这种方法：

```java
@SafeVarargs static <E> E[] array(E... array) { return array; }
```

现在你可以调用

```java
Pair<String>[] table = array(pair1, pair2);
```

这看起来很方便，但存在一个隐藏的危险。这段代码：

```java
Object[] objarray = table;
objarray[0] = new Pair<Employee>();
```

将能够运行而不会抛出`ArrayStoreException`（因为数组存储只检查擦除后的类型），当你处理`table[0]`时会在其他地方得到异常。

* * *

### 8.6.5 你不能实例化类型变量

你不能在像`new T(. . .)`的表达式中使用类型变量。例如，以下`Pair<T>`构造函数是非法的：

```java
public Pair() { first = new T(); second = new T(); } // 错误
```

类型擦除会将`T`变为`Object`，而你显然不想调用`new Object()`。

自 Java 8 开始，最好的变通方法是让调用者提供构造器表达式。例如：

```java
Pair<String> p = Pair.makePair(String::new);
```

`makePair`方法接收一个`Supplier<T>`，它是无参数且结果类型为`T`的函数的函数式接口：

```java
public static <T> Pair<T> makePair(Supplier<T> constr)
{
   return new Pair<>(constr.get(), constr.get());
}
```

另一种更传统的变通方法是通过反射调用`Constructor.newInstance`方法来构造泛型对象。

遗憾的是，细节上有些复杂。你不能调用：

```java
first = T.class.getConstructor().newInstance(); // 错误
```

`T.class`表达式是不合法的，因为它会被擦除为`Object.class`。相反，你必须设计 API，以便你获得一个`Class`对象，如下：

```java
public static <T> Pair<T> makePair(Class<T> cl)
{
   try
   {
      return new Pair<>(cl.getConstructor().newInstance(),
         cl.getConstructor().newInstance());
   }
   catch (Exception e) { return null; }
}
```

此方法可以如下所示调用：

```java
Pair<String> p = Pair.makePair(String.class);
```

注意`Class`类本身是泛型的。例如，`String.class`是`Class<String>`的一个实例（事实上，是唯一的实例）。因此，`makePair`方法可以推断出它正在创建的配对的类型。

### 8.6.6 你不能构造泛型数组

正如你不能实例化单个泛型实例一样，你不能实例化数组。原因是不同的——毕竟数组是用`null`填充的。假设我们实现：

```java
public static <T> T[] minmax(T... a)
{
   var result = Comparable[2]; // 错误
   . . .
}
```

`ArrayList`类就没有那么幸运了。它需要产生`T[]`数组，但它没有组件类型。因此有两种变体：

```java
Object[] toArray()
T[] toArray(T[] result)
```

第二个方法接收一个数组参数。如果数组足够大，则使用它。否则，将使用`result`的组件类型创建一个足够大小的新数组。

`ArrayList`类可能如下：

```java
public class ArrayList<E>
{
   private Object[] elements;
   . . .
   @SuppressWarnings("unchecked") public E get(int n) { return (E) elements[n]; }
   void set(int n, E e) { elements[n] = e; }
}
```

另一种实现是：

```java
public class ArrayList<E>
{
   private Object[] elements;
   . . .
   public ArrayList() { elements = (E[]) Object[10]; }
}
```

如果可以做到这一点，程序就可以声明一个`Singleton<Random>`来共享随机数生成器，并声明一个`Singleton<JFileChooser>`来共享文件选择对话框。但这是不可行的。在类型擦除之后，只有一个`Singleton`类，且只有一个`singleInstance`字段。因此，带有类型变量的静态字段和方法被直接禁止了。

### 8.6.8 你不能抛出或捕获泛型类的实例

你既不能抛出也不能捕获泛类的对象。实际上，泛型类继承`Throwable`也是不法的。例如，以下定义将无法编译：

```java
public class Problem<T> extends Exception { /* . . . */ }
// ERROR--不能扩展 Throwable
```

你不能在`catch`子句中使用类型变量。例如，以下方法将无法编译：

```java
public static <T extends Throwable> void doWork(Class<T> t)
{
   try
   {
      do work
   }
   catch (T e) // ERROR--不能捕获类型变量
   {
      Logger.global.info(. . .);
   }
}
```

然而，在异常规格中使用中使用类型变量是允许的。以下方法是合法的：

```java



`public static <T extends Throwable> void doWork(T t) throws T` // OK

```
{
   try
   {
      do work
   }
   catch (Throwable realCause)
   {
      t.initCause(realCause);
      throw t;
   }
}
```

#### 8.6.9 你可以绕过受检异常检查

Java 异常处理的一个基本原则是你必须为所有受检异常提供处理器。你可以使用泛型来绕过这一机制。关键在于这个方法：

```java
@SuppressWarnings("unchecked")
static <T extends Throwable> void throwAs(Throwable t) throws T
{
   throw (T) t;
}
```

假设该方法包含在接口 `Task` 中。当你有一个受检异常 `e` 并调用

```java
Task.<RuntimeException>throwAs(e);
```

那么编译器就会认为 `e` 变成了一个未检异常。以下代码将所有异常都转换为编译器认为的未检查异常：

```java
try
{
   do work
}
catch (Throwable t)
{
   Task.<RuntimeException>throwAs(t);
}
```

让我们用此来解决一个棘手的问题。要在线程中运行代码，你必须将其放入实现 `Runnable` 接口的类的 `run` 方法中。但该方法不允许抛出受检异常。我们将提供一个适配器，将一个 `run` 方法允许抛出任意异常的 `Task` 转换为 `Runnable`：

```java
interface Task
{
   void run() throws Exception;

   @SuppressWarnings("unchecked")
   static <T extends Throwable> void throwAs(Throwable t) throws T
   {
      throw (T) t;
   }

   static Runnable asRunnable(Task task)
   {
      return () ->
         {
            try
            {
               task.run();
            }
            catch (Exception e)
            {
               Task.<RuntimeException>throwAs(e);
            }
         };
   }
}
```

例如，此程序运行了一个会抛出受检异常的线程：

```java
public class Test
{
   public static void main(String[] args)
   {
      var thread = new Thread(Task.asRunnable(() ->
```

（注：提供的文本在此处突然中断，或下方有重复片段。我已对所提供的逻辑流进行了处理。）

你可以始终将参数化类型转换为原始类型（raw type）。例如，`Pair<Employee>` 是原始类型 `Pair` 的子类型。这种转换对于与遗留代码交互是必要的。

你能先转换为原始类型，然后引发类型错误吗？遗憾的是，你可以这么做。考虑这个例子：

```
var managerBuddies = new Pair<Manager>(ceo, cfo);
Pair rawBuddies = managerBuddies; // OK
rawBuddies.setFirst(new File(". . .")); // 仅有编译时警告
```

这听起来很可怕。然而，请记住，你的处境并不比使用旧版本的 Java 时更糟糕。虚拟机的安全性不会受到威胁。当使用 `getFirst` 获取外部对象并赋值给 `Manager` 变量时，会抛出 `ClassCastException`，就像在过去的老时代一样。你只是失去了泛型编程通常提供的额外安全性。

最后，泛型类可以扩展或实现其他的泛型类。在这方面，它们与普通类没有区别。例如，`ArrayList<T>` 类实现了 `List<T>` 接口。这意味着一个 `ArrayList<Manager>` 可以转换为 `List<Manager>`。然而，正如你刚刚看到的，一个 `ArrayList<Manager>` *不是* `ArrayList<Employee>` 或 `List<Employee>`。图 8.2 显示了这些关系。

![Images](img/08fig02.jpg)

**图 8.2 泛型列表类型之间的子类型关系**

### 8.8 通配符类型

类型系统研究人员早就知道，僵化的泛型类型系统用起来非常不方便。Java 设计者发明了一种巧妙（尽管依然安全）“逃口”：*通配符类型*（wildcard type）。后续章节将为你介绍如何使用通配符。

#### 8.8.1 通配符概念

在通配符类型中，类型参数允许变化。例如，通配符类型

```
Pair<? extends Employee>
```

表示任何类型参数为 `Employee` 子类的泛型 `Pair` 类型，例如 `Pair<Manager>`，但不是 `Pair<String>`。

假设你想写一个方法来打印员工对，如下所示：

```
public static void printBuddies(Pair<Employee> p)
{
   Employee first = p.getFirst();
   Employee second = p.getSecond();
   System.out.println(first.getName() + " and " + second.getName() + " are buddies.");
}
```

正如你在上一节中所看到的，你不能将 `Pair<Manager>` 传递给该方法，这相当相当局限。但解决方案很简单——使用通配符类型：

```
public static void printBuddies(Pair<? extends Employee> p)
```

类型 `Pair<Manager>` 是 `Pair<? extends Employee>` 的子类型（参见图 8.3）。

我们能通过 `Pair<? extends Employee>` 引用来破坏 `Pair<Manager>` 吗？

```
var managerBuddies = new Pair<Manager>(ceo, cfo);
Pair<? extends Employee> wildcardBuddies = managerBuddies; // OK
wildcardBuddies.setFirst(lowlyEmployee); // 编译时错误
```

这种破坏是不可能的。对 `setFirst` 的调用是一个类型错误。为了了解原因，让我们仔细观察类型 `Pair<? extends Employee>`。它的方法看起来如下：

```
? extends Employee getFirst()
void setFirst(? extends Employee)
```

![Images](img/08fig03.jpg)

**图 8.3 带通配符的子类型关系**

无法调用 `setFirst` 方法！考虑调用 `wildcardBuddies.setFirst(lowlyEmployee)`。编译器知道 `setFirst` 的参数某种特定类型，该类型扩展了 `Employee`。这个特定类型是 `Employee` 吗？是 `Manager` 还是其他子类？编译器无法得知。因此，编译器不能接受 `lowlyEmployee`。出于同样的原因，调用 `wildcardBuddies.setFirst(cio)`（`cio` 是一个 `Manager` 实例）也会失败。编译器必须拒绝除 `null` 之外的所有 `setFirst` 参数。

`getFirst` 方法继续有效。`getFirst` 的返回值是某个 `Employee` 子类型的特定类型实例。它可以保证赋值给 `Employee` 引用是安全的。

这就是边界通配符背后的核心思想。我们现在有一种方法区分安全的访问方法（accessor）和不安全的变器方法（mutator）。

#### 8.8.2 通配符的上类型边界

通配符边界与类型变量边界相似，但它们多了一个功能——你可以指定一个*上类型边界*，如下所示：

```
? super Manager
```

这个通配符限制限于 `Manager` 的所有上类型。（现有的 `super` 关键字能如此准确地描述这种关系，真是一种好运。）

为什么要这样做呢？带有上类型边界的通配符提供的行为与第 475 页 8.8 节 中“通配符类型”通配符相反。你可以向方法提供参数。

直观来说，带有上类型边界的通配符允许你向泛型对象写入，而带有子类型边界的通配符允许你从泛型对象读取。

这是一个典型的例子。我们有一个经理数组，并将奖金最低和最高的经理放入 `Pair` 中。图 8.4。以下方法接受任何合适的 `Pair`：

```
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
```

![Images](img/08fig04.jpg)

**图 8.4 带上类型边界的通配符**

这是上类型边界的另一个用途。`Comparable` 接口本身是一个泛型类型。它的声明如下：

```
public interface Comparable<T>
{
   public int compareTo(T other);
}
```

在这里，类型变量指示了 `other` 参数的类型。例如，`String` 类实现了 `Comparable<String>`，它的 `compareTo` 方法声明为：

```
public int compareTo(String other)
```

这很棒——显式参数具有正确的类型。在接口泛型之前，`other` 是一个 `Object`，在方法的实现中需要进行强制转换。

现在 `Comparable` 是一个泛型类型了，也许我们应该对 `ArrayAlg` 类中的 `minmax` 方法做得更好？我们可以将其声明为：

```
public static <T extends Comparable<T>> Pair<T> minmax(T[] a)
```

这看起来比仅仅使用 `T extends Comparable` 更详尽，并且对于许多类都有效。例如，如果你计算一个 `String` 数组的最小值，那么 `T` 的类型就是 `String`，而 `String` 是 `Comparable<String>` 的子类型。但在处理 `LocalDate` 对象数组时，我们会遇到一个问题。事实上，`LocalDate` 实现了 `ChronoLocalDate`，而 `ChronoLocalDate` 扩展了 `Comparable<ChronoLocalDate>`。因此，`LocalDate` 实现的是 `Comparable<ChronoLocalDate>` 而不是 `Comparable<LocalDate>`。

在这样的情况下，超类型就派上用场了：

```
public static <T extends Comparable<? super T>> Pair<T> minmax(T[] a)
```

现在 `compareTo` 方法的形式为：

```
int compareTo(? super T)
```

它可能声明为接收一个类型为 `T` 的对象，或者（例如当 `T` 为 `LocalDate` 时）`T` 的超类型。无论如何，将类型为 `T` 的对象传递给 `compareTo` 方法都是安全的。

对于初学者来说，像 `<T extends Comparable<? super T>>` 这样的声明看起来可能令人令畏。这很遗憾，因为这个声明的意图是通过消除对调用参数的不必要限制来帮助应用程序程序员的。对泛型不感兴趣的应用程序程序员可能会很快学会忽略这些声明，并理所当然地认为库程序员会做正确的事。如果你是一个库程序员，你就需要习惯通配符（wildcards），否则你的用户会咒骂你，并在代码中进行随机的强制转换，直到编译通过为止。

***

![Image](img/note.jpg) **注意：**

超类型边界的常见用途是函数式接口的参数类型。例如，`Collection` 接口有一个方法：

```
default boolean removeIf(Predicate<? super E> filter)
```

该方法删除所有符合给定谓词的元素。例如，如果你讨厌哈希码为奇数的员工，可以这样删除他们：

```
ArrayList<Employee> staff = . . .;
Predicate<Object> oddHashCode = obj -> obj.hashCode() %2 != 0;
staff.removeIf(oddHashCode);
```

你希望能够传递一个 `Predicate<Object>`，而不仅仅是 `Predicate<Employee>`。`super` 通配符使得这成为可能。

***

#### 8.8.3 无界通配符

你甚至可以使用没有任何边界的通配符——例如 `Pair<?>`。从乍上看，它看起来与原始（raw）`Pair` 类型相同。实际上，这两者的类型是非常不同的。`Pair<?>` 类型具有如下方法：

```
? getFirst()
void setFirst(?)
```

`getFirst` 的返回值只能赋值给 `Object`。`setFirst` 方法永远无法被调用，即使传入 `Object` 也不行。这就是 `Pair<?>` 和 `Pair` 之间的本质区别：你可以用任何 `Object` 调用原始 `Pair` 类的 `setFirst` 方法。

***

![Image](img/note.jpg) **注意：**

你可以调用 `setFirst(null)`。

***

你为什么会想要这样软弱的类型呢？它对于非常简单的操作很有用。例如，下面的方法测试元组是否包含 `null` 引用。它永远不需要实际类型。

```
public static boolean hasNulls(Pair<?> p)
{
   return p.getFirst() == null || p.getSecond() == null;
}
```

你可以通过将 `hasNulls` 转换为泛型方法来避免使用通配符类型：

```
public static <T> boolean hasNulls(Pair<T> p)
```

然而，带有通配符类型的版本似乎更易于读。

#### 8.8.4 通配符捕获

让我们写一个交换对元组中元素的方法：

```
public static void swap(Pair<?> p)
```

通配符不是类型变量，所以我们不能编写使用 `?` 作为类型的代码。换句话说，以下代码是非合法的：

```
? t = p.getFirst(); // 错误
p.setFirst(p.getSecond());
p.setSecond(t);
```

这是一个问题，因为在执行交换时我们需要临时持有第一个元素。幸运的是，这个问题有一个有趣的解决方案。我们可以像下面这样写一个辅助方法 `swapHelper`：

```
public static <T> void swapHelper(Pair<T> p)
{
   T t = p.getFirst();
   p.setFirst(p.getSecond());
   p.setSecond(t);
}
```

注意 `swapHelper` 是泛型方法，而 `swap` 不是——它有一个固定类型为 `Pair<?>` 的参数。

现在我们可以从 `swap` 调用 `swapHelper`：

```
public static void swap(Pair<?> p) { swapHelper(p); }
```

在这种情况下，`swapHelper` 方法的参数 `T` 捕获了通配符。我们不知道通配符表示什么类型，但它是一个确定的类型，而且当 `T` 表示该类型时，`<T>swapHelper` 的定义完全合理。

当然，在这种情况下，我们并没有强制使用通配符。我们可以直接实现 `<T> void swap(Pair<T> p)` 为没有通配符的泛型方法。然而，考虑这个例子，通配符类型自然地出现在计算中间：

```
public static void maxminBonus(Manager[] a, Pair<? super Manager> result)
{
   minmaxBonus(a, result);
   PairAlg.swapHelper(result); // 正确--swapHelper 捕获了通配符类型
}
```



在这里，通配符捕获是无法避免的。

通配符捕获仅在非常有限的情况下合法。编译器必须能够保证通配符表示一个单一、确定的类型。例如，`ArrayList<Pair<T>>` 中的 `T` 永远无法捕获 `ArrayList<Pair<?>>` 中的通配符。该列表可能包含两个 `Pair<?>`，每个 `?` 的类型都是不同的。

Listing 8.3 中的测试程序汇总了前面节讨论的各种方法，以便你可以在上下文中看到它们。

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
        var ceo = new Manager("Gus Greedy", 800000, 2003, 12, 15);
        var cfo = new Manager("Sid Sneaky", 600000, 2003, 12, 15);
        var buddies = new Pair<Manager>(ceo, cfo);
        printBuddies(buddies);

        ceo.setBonus(1000000);
        cfo.setBonus(500000);

        Manager[] managers = { ceo, cfo };
        var result = new Pair<Employee>();

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

    public static void maxminBonus(Manager[] a, Pair<? super Manager> result)
    {
        minmaxBonus(a, result);
        PairAlg.swapHelper(result); // OK--swapHelper captures wildcard type
    }

    // can't write public static <T super manager> . . .
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

## 8.9 反射与泛型

反射允许你分析任意对象。如果对象是泛型类的实例，你无法获得关于泛型类型的太多信息，因为它们已经被擦除了。在接下来的章节中，你将学习通过反射可以找到关于泛型类的哪些信息。

### 8.9.1 泛型 `Class` 类

`Class` 类现在是泛型的。例如，`String.class` 实际上是 `Class<String>` 类的一个对象（事实上是该唯一的对象）。

类型参数非常有用，因为它允许 `Class<T>` 的方法在返回类型上更具具体性。`Class<T>` 的以下方法利用了类型参数：

```java
T newInstance()

T cast(Object obj)

T[] getEnumConstants()

Class<? super T> getSuperclass()

Constructor<T> getConstructor(Class... parameterTypes)

Constructor<T> getDeclaredConstructor(Class... parameterTypes)
```

`newInstance` 方法返回一个从无参构造函数获取的类实例。它的返回类型现在可以声明为 `T`，即与 `Class<T>` 所描述的类相同的类型。这节省了一次强制转换。

`cast` 方法返回给定的对象，如果其类型确实是 `T` 的子类型，则现在声明为类型 `T`。否则，它会抛出 `BadCastException`。

如果该类不是 `enum` 类，或者已知为 `T` 的枚举值数组，则 `getEnumConstants` 方法返回 `null`。

最后，`getConstructor` 和 `getDeclaredConstructor` 方法返回一个 `Constructor<T>` 对象。`Constructor` 类也被变为了泛型，以便其 `newInstance` 方法具有正确的返回类型。

`java.lang.Class<T>`

- `T newInstance()` 返回一个用无参构造函数构建的新实例。
- `T cast(Object obj)` 如果 `obj` 为 `null` 或可以转换为类型 `T`，则返回 `obj`；否则抛出 `BadCastException`。
- `T[] getEnumConstants()` 如果 `T` 是枚举类型，则返回所有值的数组；否则返回 `null`。
- `Class<? super T> getSuperclass()` 返回此类的父类；如果 `T` 不是一个类或 `Object` 类，则返回 `null`。
- `Constructor<T> getConstructor(Class... parameterTypes)`
- `Constructor<T> getDeclaredConstructor(Class... parameterTypes)` 获取公共构造函数，或具有给定参数类型的构造函数。

`java.lang.reflect.Constructor<T>`

- `T newInstance(Object... parameters)` 返回一个用给定参数构建的新实例。

### 8.9.2 使用 `Class<T>` 参数进行类型匹配

在泛型方法中，匹配 `Class<T>` 参数的类型变量有时是有用的。这里有一个经典的示例：

```java
public static <T> Pair<T> makePair(Class<T> c) throws InstantiationException,
    IllegalAccessException
{
    return new Pair<>(c.newInstance(), c.newInstance());
}
```

如果你调用：

```java
makePair(Employee.class)
```

那么 `Employee.class` 是一个 `Class<Employee>` 类型的对象。`makePair` 方法的类型参数 `T` 匹配 `Employee`，编译器可以推导出该方法返回一个 `Pair<Employee>`。

### 8.9.3 虚拟机中的泛型类型信息

Java 泛型的显著特征之一是虚拟机中泛型类型的擦除。也许令人惊讶的是，擦除后的类仍然保留了关于其泛型起源的微弱记忆。例如，擦除后的 `Pair` 类知道它源自泛型类 `Pair<T>`，尽管 `Pair` 对象无法判断它是被构造为 `Pair<String>` 还是 `Pair<Employee>`。

同样，考虑一个方法：

```java
public static Comparable min(Comparable[] a)
```

它是泛型方法的擦除：

```java
public static <T extends Comparable super T>> T min(T[] a)
```

可以使用反射 API 判断：

- 泛型方法有一个名为 `T` 的类型参数；
- 该类型参数有一个本身是泛型的类型；
- 边界类型有一个通配符；
- 通配符有一个父类型边界；
- 泛型方法有一个泛型数组参数。

也就是说，你可以重建实现者声明的所有关于泛型类和方法的信息。然而，你并不知道类型参数是如何具体解析的。

为了表示泛型声明，请使用 `java.lang.reflect` 包中的 `Type` 接口。该接口有以下子类型：

- `Class` 类，描述具体类型；
- `TypeVariable` 接口，描述类型变量（如 `T extends Comparable<? super T>`）；
- `WildcardType` 接口，描述通配符（如 `? super T`）；
- `ParameterizedType` 接口，描述泛型类或接口类型（如 `Comparable<? super T>`）；
- `GenericArrayType` 接口，描述泛型数组（如 `T[]`）。

图 8.5 显示了继承结构。注意最后四个子类型是接口——虚拟机实现了这些接口的合适类。

![Images](img/08fig05.jpg)

**图 8.5** `Type` 接口及其后代

列表 8.4 使用泛型反射 API 打印它关于给定类所发现的信息。如果你对 `Pair` 类运行它，将得到如下报告：

```text
class Pair<T> extends java.lang.Object

public T getFirst()

public T getSecond()

public void setFirst(T)

public void setSecond(T)
```

如果你在 `PairTest2` 目录下使用 `ArrayAlg` 运行它，报告将显示以下方法：

```text
public static <T extends java.lang.Comparable> Pair<T> minmax(T[])
```

**Listing 8.4** `genericReflection/GenericReflectionTest.java`

```java
package genericReflection;

import java.lang.reflect.*;
import java.util.*;

 /**
  * @version 1.12 2021-05-30
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
            try (var in = new Scanner(System.in))
            {
                System.out.println("Enter class name (e.g., java.util.Collections): ");
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
        printTypes(cl.getTypeParameters(), "<", ", ", ">", true);

        Type sc = cl.getGenericSuperclass();
        if (sc != null)
        {
            System.out.print(" extends ");
            printType(sc, false);
        }

        printTypes(cl.getGenericInterfaces(), " implements ", ", ", "", false);
        System.out.println();
    }

    public static void printMethod(Method m)
    {
        String name = m.getName();

        System.out.print(Modifier.toString(m.getModifiers()));
        System.out.print(" ");

        printTypes(m.getTypeParameters(), "<", ", ", "> ", true);
        printType(m.getGenericReturnType(), false);

        System.out.print(" ");
        System.out.print(name);
        System.out.print("(");

        printTypes(m.getGenericParameterTypes(), "", "", "", false);
        System.out.println(")");
    }

    public static void printTypes(Type[] types, String pre, String suf,
        boolean isDefinition)
    {
        if (pre.equals(" extends ") && Arrays.equals(types, new Type[] { Object.class }))
            return;

        if (types.length > 0) System.out.print(pre);

        for (int i = 0; i < types.length; i++)
        {
            if (i > 0) System.out.print(", ");
            printType(types[i], isDefinition);
        }

        if (types.length > 0) System.out.print(suf);
    }
}
```



#### 8.9.4 类型字面量

在有时，你可能希望根据值的类型来驱动程序行为。例如，在持久化机制中，你可能希望用户指定保存特定对象的方法。这通常通过将`Class`对象与操作关联来实现。

然而，对于泛型类，擦除带来了问题。当`ArrayList<Integer>`和`ArrayList<String>`都擦变为相同的`ArrayList`类型时，如何为它们实现不同的操作？

有一种技巧可以缓解某些情况。你可以捕获上一节中遇到的`Type`接口的实例。构造一个匿名子类：

```java
var type = new TypeLiteral<ArrayList<Integer>>(){} // 注意 {}
```

`TypeLiteral`构造函数捕获泛型超类：

```java
class TypeLiteral
{
    public TypeLiteral()
    {
        Type parentType = getClass().getGenericSuperclass();
        if (parentType instanceof ParameterizedType paramType)
            type = paramType.getActualTypeArguments()[0];
        else
            throw new UnsupportedOperationException(
            "Construct as new TypeLiteral<...>(){}");
    }
    ...
}
```

如果在运行时有一个泛型类型可用，就可以将其与`TypeLiteral`进行匹配。我们无法从对象获取泛型类型——它被擦除了。但正如你在上一节中所看到的，字段和方法参数的泛型类型在虚拟机中仍然存在。

CDI 和 Guice 等注入框架使用类型字面量来控制泛型类型的注入。书中示例程序展示了一个更简单的例子。给定一个对象，我们遍历其泛型类型字段，并查找关联的格式化操作。

通过空格分隔值来格式化`ArrayList<Integer>`，通过将字符接到字符串来格式化`ArrayList<Character>`。任何其他列表通过`ArrayList.toString`进行格式化。

**Listing 8.5** `genericReflection/TypeLiterals.java`

```java
package genericReflection;

/**
    * @version 1.02 2021-05-30
    * @author Cay Horstmann
    */

import java.lang.reflect.*;
import java.util.*;
import java.util.function.*;

/**
 * 类型字面量描述了一个可以是泛型的类型，例如
 * ArrayList<String>
 */
class TypeLiteral<T>
{
    private Type type;

    /**
     * 此构造函数必须通过匿名子类调用，
     * 如 new TypeLiteral<. . .>(){}。
     */
    public TypeLiteral()
    {
        Type parentType = getClass().getGenericSuperclass();
        if (parentType instanceof ParameterizedType paramType)
            type = paramType.getActualTypeArguments()[0];
        else
            throw new UnsupportedOperationException(
                "请使用 new TypeLiteral<. . .>(){ 进行构造");
    }

    private TypeLiteral(Type type)
    {
        this.type = type;
    }

    /**
     * 返回一个描述给定类型的类型字面量。
     */
    public static TypeLiteral<?> of(Type type)
    {
        return new TypeLiteral<Object>(type);
    }

    public String toString()
    {
        if (type instanceof Class clazz) return clazz.getName();
        else return type.toString();
    }

    public boolean equals(Object otherObject)
    {
        return otherObject instanceof TypeLiteral otherLiteral
            && type.equals(otherLiteral.type);
    }

    public int hashCode()
    {
        return type.hashCode();
    }
}

/**
 * 使用将类型与格式化函数关联的规则对对象进行格式化。
 */
class Formatter
{
    private Map<TypeLiteral<?>, Function<?, String>> rules = new HashMap<>();

    /**
     * 向此 formatter 添加格式化规则。
     * @param type 规则应用的类型
     * @param formatterForType 用于格式化该类型对象的函数
     */
    public <T> void forType(TypeLiteral<T> type, Function<T, String> formatterForType)
    {
        rules.put(type, formatterForType);
    }

    /**
     * 使用此 formatter 的规则格式化对象的所有字段。
     * @param obj 一个对象
     * @return 包含所有字段名和格式化后值的字符串
     */
    public String formatFields(Object obj)
        throws IllegalArgumentException, IllegalAccessException
    {
        var result = new StringBuilder();
        for (Field f : obj.getClass().getDeclaredFields())
        {
            result.append(f.getName());
            result.append("=");
            f.setAccessible(true);
            Function<?, String> formatterForType = rules.get(Type.of(f.getGenericType()));
            if (formatterForType != null)
            {
                // formatterType 有参数 ?. 无法传递给它的 apply 方法。
                // 强制转换将参数类型转换为 Object 以便可以它。
                @SuppressWarnings("unchecked")
                Function<Object, String> objectFormatter
                    = (Function<Object, String>) formatterForType;
                result.append(objectFormatter.apply(f.get(obj)));
            }
            else
                result.append(f.get(obj).toString());
            result.append("\n");
        }
        return result.toString();
    }
}

public class TypeLiterals
{
    public class Sample
    {
        ArrayList<Integer> nums;
        ArrayList<Character> chars;
        ArrayList<String> strings;

        public Sample()
        {
            nums = new ArrayList<>();
            nums.add(42); nums.add(17);
            chars = new ArrayList<>();
            chars.add('H'); chars.add('i');
            strings = new ArrayList<>();
            strings.add("Hello"); strings.add("World");
        }
    }

    private static <T> String join(String separator, ArrayList<T> elements)
    {
        var result = new StringBuilder();
        for (T e : elements)
        {
            if (result.length() > 0) result.append(separator);
            result.append(e.toString());
        }
        return result.toString();
    }

    public static void main(String[] args) throws Exception
    {
        var formatter = new Formatter();
        formatter.forType(new TypeLiteral<ArrayList<Integer>>(){},
            lst -> join(" ", lst));
        formatter.forType(new TypeLiteral<ArrayList<Character>>(){},
            lst -> "\"" + join("", lst) + "\"");
        System.out.println(formatter.formatFields(new Sample()));
    }
}
```




# Java 反射类型与方法

## `java.lang.Class<T>`（1.0）

- `TypeVariable[] getTypeParameters()`（5）  
  如果此类型被声明为泛型类型，则获取泛型类型变量，否则返回长度为 0 的数组。

- `Type getGenericSuperclass()`（5）  
  获取为此类型声明的父类的泛型类型，如果此类型是 `Object`，则返回 `null`。

- `Type[] getInterfaces()`（5）  
  按顺序获取为此类型声明的接口的泛型类型，如果此类型未实现接口，则返回长度为 0 的数组。

## `java.lang.reflect.Method`（1.1）

- `TypeVariable[] getTypeParameters()`（5）  
  如果此方法被声明为泛型方法，则获取泛型类型变量，否则返回长度为 0 的数组。

- `Type getGenericReturnType()`（5）  
  获取此方法声明的泛型返回类型。

- `Type[] getGenericParameterTypes()`（5）  
  获取此方法声明的泛型参数类型。如果方法没有参数，则返回长度为 0 的数组。

## `java.lang.reflect.TypeVariable`（5）

- `String getName()`  
  获取此类型变量的名字。

- `Type[] getBounds()`（5）  
  获取此类型变量的子类边界，如果变量无边界，则返回长度为 0 的数组。

## `java.lang.reflect.WildcardType`（5）

- `Type[] getUpperBounds()`（5）  
  获取此类型变量的子类（`extends`）边界，如果变量没有子类边界，则返回长度为 0 的数组。

- `Type[] getLowerBounds()`（5）  
  获取此类型变量的父类（`super`）边界，如果变量没有父类边界，则返回长度为 0 的数组。

## `java.lang.reflect.ParameterizedType`（5）

- `Type getRawType()`  
  获取此泛化类型的原始类型。

- `Type[] getActualTypeArguments()`（5）  
  获取声明此泛化类型时使用的类型参数。

- `Type getOwnerType()`  
  如果此类型为内部类型，则获取外部类类型；如果此类型是顶层类型，则返回 `null`。

## `java.lang.reflect.GenericArrayType`（5）

- `Type getGenericComponentType()`  
  获取声明此数组类型时使用的泛型组件类型。

## 9.6 算法

## 9.7 遗留集合

当你尝试以自然风格实现方法或关注性能时，你选择的数据结构会产生巨大影响。你需要快速地在数千个（甚至数百万个）排序后的项目中进行搜索吗？你需要在有序序列的中间快速插入和删除元素吗？你需要在键和值之间建立关联吗？

本章将展示 Java 库如何帮助你完成正式编程所需的传统数据结构。在大学的计算机科学专业中，一门名为 `Data Structures` 的课程通常需要一个学期才能完成，而且有很多书籍致力于这个重要主题。我们的涵盖范围与大学课程不同；我们将跳过理论，直接查看如何使用标准库中的集合类。

# 9.1 Java 集合框架

Java 的最初发布版本仅为最实用的数据结构提供了一小部分类：`Vector`、`Stack`、`Hashtable`、`BitSet` 以及 `Enumeration` 接口，后者提供了一种用于访问任意容器中元素的抽象机制。这无疑是一个明智的选择——开发一个完整的集合类库需要时间和技巧。

随着 Java 1.2 的出现，设计者认为是时候推出一套完整的数据结构了。他们面临着许多相互冲突的设计挑战。他们希望库既小又易于学习。他们不想要 C++ 标准模板库（STL）那样的复杂性，但他们想要获得 STL 开创的“泛型算法”的益处。他们希望遗留类能够适应新框架。正如所有集合库的设计者所做的那样，他们必须做出艰难的选择并在这个过程中提出了一系列许多独特的设计决策。在本节中，我们将探索 Java 集合框架的基本设计，演示如何使用它，并解释一些更具争议的特征背后的原理。

## 9.1.1 分离集合接口与实现

与现代数据结构库的常见做法一样，Java 集合库将 `interfaces`（接口）和 `implementations`（实现）分开。让我们通过一个熟悉的数据结构——队列（queue）来看这种分离。

`queue interface` 指定了你可以在队列的尾部添加元素，从头部删除元素，并找出队列中有多少元素。当你需要收集对象并按“先进先出”的方式检索它们时，就会使用队列（参见图 9.1）。

![Images](img/09fig01.jpg)

**图 9.1** 队列

队列接口的极简形式可能如下：

```java
public interface Queue<E> // 标准库中接口的简化形式
{
   void add(E element);
   E remove();
   int size();
}
```

接口没有告诉你任何关于队列如何实现的信息。在队列的两种常见实现中，一种使用“循环数组”，另一种使用链表（参见图 9.2）。

![Images](img/09fig02.jpg)

**图 9.2** 队列的实现

每个实现都可以由一个实现了 `Queue` 接口的类来表示。

```java
public class CircularArrayQueue<E> implements Queue<E> // true 实际的库类
{
   private int head;
   private int tail;

   CircularArrayQueue(int capacity) { . . . }
   public void add(E element) { . . . }
   public E remove() { . . . }
   public int size() { . . . }

   private E[] elements;
}

public class LinkedListQueue<E> implements Queue<E> // true 实际的库类
{
   private Link head;
   private Link tail;

   LinkedListQueue() { . . . }
   public void add(E element) { . . . }
   public E remove() { . . . }
   public int size() { . . . }
}
```

> ![Image](img/note.jpg) **注意：**
>
> Java 库实际上并没有名为 `CircularArrayQueue` 和 `LinkedListQueue` 的类。我使用这些类作为示例来解释集合接口与实现之间概念上的区别。如果你需要循环数组队列，请使用 `ArrayDeque` 类。对于链表队列，只需使用 `LinkedList` 类即可——它实现了 `Queue` 接口。

当你在程序中使用队列时，一旦集合构建完成，你就不知道实际使用的是哪种实现。因此，在构建集合对象时仅使用具体类（concrete class）是合理的。使用 `interface type`（接口类型）来持有集合引用。

```java
Queue<Customer> expressLane = new CircularArrayQueue<>(100);
expressLane.add(new Customer("Harry"));
```

通过这种方法，如果你改变主意，可以轻松地使用不同的实现。你只需要更改程序中的一处——即构造函数调用处。如果你决定 `LinkedListQueue` 更好，你的代码将变为：

```java
Queue<Customer> expressLane = new LinkedListQueue<>();
expressLane.add(new Customer("Harry"));
```

为什么选择其中一种实现而不是另一种？接口并没有说明效率。循环数组比链表更高效，因此通常是首选的。然而，一如以往，这是有代价的。循环数组是*有界的*（bounded）——它有有限的容量。如果你对收集的对象数量没有上限，那么链表可能更好。当你学习 API 时，你会发现一组以 `Abstract` 开头的类，例如 `AbstractQueue`。这些类是为实现者设计的，用于实现 `Queue` 接口的方法。

## 9.1.2 `Collection` 接口

Java 库中集合类的基础接口是 `Collection` 接口。该接口有两个方法：

```java
public interface Collection<E>
{
   boolean add(E element);
   Iterator<E> iterator();
   . . .
}
```

除了这两个方法外，还有几个方法；我们稍后会讨论。

`add` 方法将元素添加到集合中。如果添加元素确实更改了集合，`add` 方法返回 `true`，否则返回 `false`。例如，如果你尝试向集合（set）添加对象而该对象已存在，则 `add` 请求无效。

`iterator` 方法返回一个实现了 `Iterator` 接口的对象。你可以使用该迭代器逐个访问集合中的元素。我们在下一节讨论迭代器。

## 9.1.3 迭代器（Iterators）

`Iterator` 接口有四个方法：

```java
public interface Iterator<E>
{
   E next();
   boolean hasNext();
   void remove();
   default void forEachRemaining(Consumer<? super E> action);
}
```

通过反复调用 `next` 方法，你可以逐个访问集合中的元素。然而，当你到达集合结束时，`next` 方法会抛出 `NoSuchElementException`。因此，在调用 `next` 之前调用 `hasNext`。如果迭代器对象还有元素需要访问，该方法返回 `true`。如果你想检查集合中的所有元素，请求一个迭代器并在 `hasNext` 返回 `true` 时不断调用 `next` 方法。例如：

```java
Collection<String> c = . . ++;
Iterator<String> iter = c.iterator();

while (iter.hasNext())
{
   String element = iter.next();
   do something with element
}
```

你可以将这种循环更简洁地写为“for each”循环：

```java
for (String element : c)
{
    do something with element
}
```

编译器简单地将“for each”循环（增强型循环）翻译为带有迭代器的循环。

“for each”循环适用于任何实现了 `Iterable` 接口的对象，该接口仅有一个抽象方法：

```java
public interface Iterable<E>
{
    Iterator<E> iterator();
    . . .
}
```

`Collection` 接口继承了 `Iterable` 接口。因此，你可以对标准库中的任何集合使用“for each”循环。

与其编写循环，不如调用 `forEachRemaining` 方法并传入一个消耗元素的 Lambda 表达式。该 Lambda 表达式会在迭代器的每个元素上被调用，直到没有剩余元素。

```java
iterator.forEachRemaining(element -> do something with element);
```

访问元素的顺序取决于集合的类型。如果你遍历 `ArrayList`，迭代器从索引 `0` 开始，并在每一步中增加索引。然而，如果你访问 `HashSet` 中的元素，获取到的元素顺序在本质上是随机的。你可以保证在迭代过程中会遇到集合的所有元素，但无法对它们的顺序做出任何假设。这通常不是问题，因为对于计算总和或计数匹配等计算来说，顺序并不重要。

> ![Image](img/note.jpg) **注意：**
>
> 老手会注意到，`Iterator` 接口的 `next` 和 `hasNext` 方法与 `Enumeration` 接口的 `nextElement` 和 `hasMoreElements` 方法的作用相同。Java 集合库的设计者本可以选择使用 `Enumeration` 接口，但他们不喜欢那些冗长的方法名，而是引入了一个具有更短方法名的新接口。

Java 集合库中的迭代器与其他库中的迭代器之间存在着重要的概念区别。在传统的集合库中（如 C++ 的标准模板库 STL）中，迭代器是根据数组索引建模的。给定这样一个迭代器，你可以查找存储在该位置的元素，就像在有数组索引 `i` 时可以查找数组元素 `a[i]` 一样。与查找无关，你可以将迭代器移动到下一个位置。这与通过调用 `i++` 推进数组索引的操作相同，且不需要执行查找。然而，Java 迭代器并非这样工作的。查找和位置变化是紧密耦合的。查找元素的唯一方法是调用 `next`，而该查找会推进位置。

相反，请将 Java 迭代器想象为处于*元素之间*。当你调用 `next` 时，迭代器会*跳过*下一个元素，并返回它刚刚经过的元素的引用（参见图 9.3）。

> ![Image](img/note.jpg) **注意：**
>
> 这里另一个实用的类比。你可以认为 `Iterator.next` 同于 `InputStream.read`。从流中读取一个字节会自动“消耗”该字节。下一次调用 `read` 会消耗并返回输入流中的下一个字节。同样，重复调用 `next` 允许你读取集合中的所有元素。

`Iterator` 接口的 `remove` 方法移除上一次调用 `next` 返回的元素。在许多情况下，这是合理的——你必须先看到元素才能判断它是否是应该删除的那个。但如果你想移除特定位置的元素，仍然需要跳过该元素。例如，这里是移除字符串集合中第一个元素的方法：

```java
Iterator<String> it = c.iterator();
it.next(); // 跳过第一个元素
it.remove(); // 现在移除它
```

![Images](img/09fig03.jpg)

**图 9.3** 推进迭代器

更重要的是，`next` 方法和 `remove` 方法的调用之间存在依赖关系。如果在没有调用 `next` 的情况下调用 `remove` 是非法的。如果你尝试，将抛出 `IllegalStateException`。

如果你想移除两个相邻元素，不能简单地调用：

```java
it.remove();
it.remove(); // 错误
```

相反，你必须先调用 `next` 来跳过要移除的元素。

```java
it.remove();
it.next();
it.remove(); // OK
```

## 9.1.4 泛型工具方法

`Collection` 和 `Iterator` 接口是泛型的，这意味着你可以编写操作于任何类型集合的工具方法。例如，这里有一个泛型方法，用于测试任意集合是否包含给定元素：

```java
public static <E> boolean contains(Collection<E> c, Object obj)
{
    for (E element : c)
        if (element.equals(obj))
            return true;

    return false;
}
```

Java 库的设计者认为，某些工具方法非常有用，因此库应该提供它们。这样，库用户就不需要不断重复轮子了。`contains` 方法就是其中一种方法。

事实上，`Collection` 接口声明了许多实现类必须提供的有用方法。其中包括：

```java
int size()
boolean isEmpty()
boolean contains(Object obj)
boolean containsAll(Collection<?> c)
boolean add(E element)
boolean addAll(Collection<? extends E> other)
boolean remove(Object obj)
boolean removeAll(Collection<?> c)
void clear()
boolean retainAll(Collection<?> c)
Object[] toArray()
```

这些许多方法都是自明的；你将在本节末尾的 API 注意找到完整的文档。

当然，如果每个实现 `Collection` 的类都必须提供这么多方法，会很麻烦。为了方便实现者的工作，库提供了一个 `AbstractCollection` 类，它将 `size` 和 `iterator` 留为抽象，但实现了常规方法。例如：

```java
public abstract class AbstractCollection<E> implements Collection<E>
{
    . . .

    public abstract Iterator<E> iterator();

    public boolean contains(Object obj)
    {
        for (E element : this) // 调用 iterator()
            if (element.equals(obj))
                return true;

        return false;
    }

    . . .
}
```




## 集合类与 `Collection` 接口

现在具体的集合类可以继承 `AbstractCollection` 类。具体的集合类负责提供 `iterator` 方法取决于其自身，但 `contains` 方法已经由 `AbstractCollection` 父类处理好了。然而，如果子类有更高效的实现 `contains` 的方法，可以自由这样做。

这种方法有点过时了。如果这些方法是 `Collection` 接口的默认方法会更好。这种情况尚未发生。不过，已经添加了一些默认方法。它们大部分与流有关（在第二卷中讨论）。此外，还有一个实用的方法：

```java
default boolean removeIf(Predicate<? super E> filter)
```

用于移除满足条件的元素。

### `java.util.Collection<E>` 1.2

- `Iterator<E> iterator()` 返回用于访问集合中元素的迭代器。
- `int size()` 返回集合中存储的元素数量。
- `boolean isEmpty()` 如果集合不包含元素则返回 `true`。
- `boolean contains(Object obj)` 如果集合包含与 `obj` 相等的对象，则返回 `true`。
- `boolean containsAll(Collection<?> other)` 如果集合包含另一个集合中的所有元素，则返回 `true`。
- `boolean add(E element)` 将元素添加到集合中。如果集合由于此调用而发生了变化，则返回 `true`。
- `boolean addAll(Collection<? extends E> other)` 将另一个集合中的所有元素添加到此集合。如果集合由于此调用而发生了变化，则返回 `true`。
- `boolean remove(Object obj)` 从此集合中移除等于 `obj` 的对象。如果删除了匹配的对象，则返回 `true`。
- `boolean removeAll(Collection<?> other)` 从此集合中移除另一个集合中的所有元素。如果由于此调用导致集合发生了变化，则返回 `true`。
- `default boolean removeIf(Predicate<? super E> filter)` 8：移除所有 `filter` 返回 `true` 的元素。如果由于此调用导致集合发生了变化，则返回 `true`。
- `void clear()` 移除此集合中的所有元素。
- `boolean retainAll(Collection<?> other)` 从此集合中移除不等于另一个集合中任何元素的元素。如果由于此调用导致集合发生了变化，则返回 `true`。
- `Object[] toArray()` 返回集合中对象的数组。
- `<T> T[] toArray(IntFunction<T[]> generator)` 11：返回集合中对象的数组。该数组使用 `generator` 构造，该 `generator` 通常是一个构造器表达式 `T[]::new`。

### `java.util.Iterator<E>` 1.2

- `boolean hasNext()` 如果还有另一个元素可以访问，则返回 `true`。
- `E next()` 返回下一个要访问的对象。如果到达集合末尾，则抛出 `NoSuchElementException`。
- `void remove()` 移除上一次访问的对象。此方法必须紧接在访问元素之后调用。如果自上一次访问元素以来集合已被修改，则此方法将抛出 `IllegalStateException`。
- `default void forEachRemaining(Consumer<? super E> action)` 8：访问元素并将它们传递给给定的 `action`，直到没有剩余元素或该 `action` 抛出异常。

## 9.2 集合框架中的接口

Java 集合框架为不同类型的集合定义了许多接口，如图 9.4 所示。

![Images](img/09fig04.jpg)

**图 9.4** 集合框架的接口

集合有两个基本接口：`Collection` 和 `Map`。正如你已经看到的，你通过一个方法向集合中插入元素：

```java
boolean add(E element)
```

然而，map 存储的是键值对，你使用 `put` 方法来插入它们：

```java
V put(K key, V value)
```

要从集合中读取元素，请使用迭代器访问它们。然而，你可以使用 `get` 方法从 map 中读取值：

```java
V get(K key)
```

`List` 是一个有序集合。元素被添加到容器中的特定位置。元素可以通过两种方式访问：通过迭代器或通过整数索引。后者被称为随机访问，因为元素可以以任何顺序被访问。相比之下，使用迭代器时，必须按顺序访问它们。

`List` 接口定义了几个用于随机访问的方法：

```java
void add(int index, E element)

void remove(int index)

E get(int index)

E set(int index, E element)
```

`ListIterator` 接口是 `Iterator` 的子接口。它定义了一个在迭代器位置之前添加元素的方法：

```java
void add(E element)
```

坦率地说，集合框架的这一个方面设计得并不够好。在实践中，有两种有序集合，它们的性能权衡非常不同。由数组支持的有序集合具有快速的随机访问，使用带有整数索引的 `List` 方法是有意义的。相比之下，链表虽然也是有序的，但随机访问很慢，最好用迭代器进行遍历。提供两个接口本应是一件容易的事。

![Image](img/note.jpg) **注意：**

为了避免对链表执行随机访问操作，Java 1.4 引入了一个标记接口 `RandomAccess`。该接口没有任何方法，但你可以用它来测试特定集合是否支持高效的随机访问：

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

`Set` 接口与 `Collection` 接口相同，但方法的行为定义得更为紧密。set 的 `add` 方法应该拒绝重复项。set 的 `equals` 方法应该定义为：如果两个 set 具有相同的元素（顺序不一定），它们就是相等的。`hashCode` 方法应该定义为：两个具有相同元素的 set 会产生相同的哈希码。

既然方法签名相同，为什么要单独定义一个接口呢？从概念上讲，并不是所有的集合都是 set。定义 `Set` 接口允许程序员编写只接受 set 的方法。

`SortedSet` 和 `SortedMap` 接口暴露了用于排序的比较器对象，并定义了获取集合子集视图的方法。我们在第 9.5 节“副本与视图”548 页讨论了这些内容。

最后，Java 6 引入了 `NavigableSet` 和 `NavigableMap` 接口，包含了用于在排序集合和 map 中搜索和遍历的其他方法。（理想情况下，这些方法应该直接包含在 `SortedSet` 和 `SortedMap` 接口中。）`TreeSet` 和 `TreeMap` 类实现了这些接口。

## 9.3 具体集合

表 9.1 显示了 Java 库中的集合，并简述了每个集合的。（简单起见，我省略了将在第 12 章中讨论的线程安全集合。）

表 9.1](#ch09.xhtml_ch09tab1) 中的类实现了 `Collection` 接口，以 `Map` 结尾的类除外。这些类实现了 `Map` 接口。我们将在 9.4 节“Map](#ch09.xhtml_ch9-4)”535 页讨论 map。

图 9.5](#ch09.xhtml_ch09fig05) 显示了这些类之间的关系。

**表 9.1** 具体集合

![Images](img/09tab1.jpg)

![Images](img/09fig5.jpg)

**图 9.5** 集合框架中的类

我们在许多示例使用了数组及其动态表亲 `ArrayList` 类。然而，数组和数组列表有一个巨大的缺点。从数组中间移除元素是昂贵的，因为被移除元素之后的所有数组元素都必须向开头移动（见图 9.6）。在中间插入元素也是如此。

![Images](img/09fig6.jpg)

**图 9.6** 从数组中移除元素

另一种已知的数据结构——链表解决了这个问题。数组在连续的内存位置存储对象引用，而链表将每个对象存储在单独的链中。每个链还存储指向序列中下一个链的引用。在 Java 编程语言中，所有的链表实际上都是双链的；也就是说，每个链还存储一个指向其前驱的引用（见图 9.7）。

![Images](img/09fig7.jpg)

**图 9.7** 双链表

从链表的中间移除元素是一项廉价的操作——只需要更新要移除元素周围的链（见图 9.8）。

![Images](img/09fig8.jpg)

**图 9.8** 从链表中移除元素

也许你曾经上过一门数据结构课程，在课程学习了如何实现链表。你可能对在链表中删除或添加元素时弄乱链有坏记忆。如果是这样，你会很高兴地发现 Java 集合库提供了一个供你使用的 `LinkedList` 类。

下面的代码示例添加了三个元素，然后删除了第二个：

```java
var staff = new LinkedList<String>();

staff.add("Amy");

staff.add("Bob");

staff.add("Carl");

Iterator<String> iter = staff.iterator();

String first = iter.next(); // visit first element

String second = iter.next(); // visit second element

iter.remove(); // remove last visited element
```

然而，链表与通用集合之间存在一个重要的区别。链表是一个 `ordered collection`（有序集合），其中对象的位置非常重要。`LinkedList.add` 方法将对象添加到列表的末尾。但你通常想在列表的中间某个添加对象。这种依赖于位置的 `add` 方法是由 `iterator`（迭代器）负责的，因为迭代器描述了集合中的位置。使用迭代器来添加元素仅对于具有自然顺序的集合才有意义。例如，我们将在下一节中讨论的 `set` 数据类型并没有对其元素施加任何顺序限制。因此，`Iterator` 接口中没有 `add` 方法。相反，集合库提供了一个包含 `add` 方法的子接口 `ListIterator`：

```java
interface ListIterator<E> extends Iterator<E>
{
   void add(E element);
   . . .
}
```

与 `Collection.add` 不同，此方法不返回 `boolean`——它假设 `add` 操作总是会修改列表。

此外，`ListIterator` 接口有两个方法可以用于反向遍历列表。

```java
E previous()

boolean hasPrevious()
```

与 `next` 方法一样，`previous` 方法返回它跳过的对象。

`LinkedList` 类的 `listIterator` 方法返回一个实现 `ListIterator` 接口的迭代器对象。

```java
ListIterator<String> iter = staff.listIterator();
```

`add` 方法在迭代器位置之前添加新元素。例如，以下代码跳过链表中的第一个元素，并在第二个元素之前添加 `"Juliet"`（参见图 9.9）：

```java
var staff = new LinkedList<String>();

staff.add("Amy");

staff.add("Bob");

staff.add("Carl");

ListIterator<String> iter = staff.listIterator();

iter.next(); // skip past first element

iter.add("Juliet");
```

如果你多次调用 `add` 方法，元素将简单按照你提供的顺序进行添加。它们都会按顺序添加到当前迭代器位置之前。

当你使用一个从 `listIterator` 方法新返回且指向链表开头的迭代器执行 `add` 操作时，新添加的元素将成为列表的新头部。当迭代器通过了列表的最后一个元素时（即当 `hasNext` 返回 `false` 时），添加的元素将成为列表的新尾部。如果链表有 `n` 个元素，则有 `n + 1` 个位置添加新元素。这些位置对应于迭代器的 `n + 1` 种可能的位置。例如，如果一个链表包含三个元素 A、B 和 C，则有四个插入新元素的位置（标记为 `|`）：

![Images](img/09fig09.jpg)

**图 9.9** 向链表添加元素

```text
|ABC

A|BC

AB|C

ABC|
```

![Image](img/note.jpg) **注意：**

请注意“光标”类比的区别。`remove` 操作的工作方式并不完全像退格键（Backspace）。在紧接着调用 `next` 之后，`remove` 方法确实删除迭代器左侧的元素，就像退格键的作用一样。然而，如果你刚刚调用了 `previous`，右侧的元素将被删除。而且你不能连续调用两次 `remove`。

与仅取决于迭代器位置的 `add` 方法不同，`remove` 方法取决于迭代器的状态。

最后，`set` 方法会将调用 `next` 或 `previous` 返回的最后一个元素替换为新元素。例如，以下代码将列表的第一个元素替换为新值：

```java
ListIterator<String> iter = list.listIterator();

String oldValue = iter.next(); // returns first element

iter.set(newValue); // sets first element to newValue
```

正如你想象到的，如果一个迭代器在遍历集合的同时另一个迭代器正在修改它，可能会出现混乱的情况。例如，假设一个迭代器指向另一个迭代器刚刚删除的元素之前。该迭代器现在是无效的，不应再次使用。链表迭代器设计用于检测此类修改。如果迭代器发现其集合被另一个迭代器或集合本身的方法修改了，它将抛出 `ConcurrentModificationException`。例如，考虑以下代码：

```java
List<String> list = . . .;

ListIterator<String> iter1 = list.listIterator();

ListIterator<String> iter2 = list.listIterator();

iter1.next();

iter1.remove();

iter2.next(); // throws ConcurrentModificationException
```

调用 `iter2.next` 会抛出 `ConcurrentModificationException`，因为 `iter2` 检测到列表已从外部被修改。

为了避免并发修改异常，请遵循这一简单规则：你可以为集合挂载任意多个迭代器，只要它们都是只读的。或者，你可以挂载一个既能读又能写的迭代器。并发修改检测是以一种简单的方式实现的：集合会跟踪修改操作的数量。每个迭代器都维护一个单独的修改操作计数。在每个迭代器方法的开始处，迭代器只需检查其计数是否与集合的计数相等。如果不相等，它将抛出 `ConcurrentModificationException`。

![Image](img/note.jpg) **注意：**

然而，并发修改检测中有一个奇特的异常。链表只跟踪结构性修改，例如添加和删除元素。`set` 方法不被视为结构性修改。你可以为列表挂载多个迭代器，它们都可以调用 `set` 来更改现有链接的内容。

现在你已经看到了 `LinkedList` 类的基本方法。使用 `ListIterator` 可以双向遍历链表的元素，并添加和删除元素。

正如你在第 9.2 节第 508 页的“集合框架中的接口”中所示，许多其他用于操作链表的有用方法在 `Collection` 接口中声明。这些方法大部分在 `LinkedList` 类的父类 `AbstractCollection` 中实现。例如，`toString` 方法会对所有元素调用 `toString` 并生成一个格式为 `[A, B, C]` 的长字符串。这对于调试非常有用。使用 `contains` 方法检查元素是否存在于链表中。例如，如果链表已经包含一个与字符串 `"Harry"` 相同的字符串，则调用 `staff.contains("Harry")` 将返回 `true`。

该库还提供了一些从理论角度来看有些可疑的方法。链表不支持快速的随机访问。如果你想查看链表的第 `n` 个元素，必须从开始开始并跳过前 `n – 1` 个元素。没有捷径。出于这个原因，程序员通常不会需要在通过整数索引访问元素的情况下使用链表。

尽管如此，`LinkedList` 类提供了一个 `get` 方法，让你能够访问特定元素：

```java
LinkedList<String> list = . . .;

String obj = list.get(n);
```

当然，这个方法并不高效。如果你发现自己在使用它，那么你可能为你的问题使用了错误的数据结构。

你绝对不要使用这种幻觉般的随机访问方法来遍历链表。以下代码：



```java
for (int i = 0; i < list.size(); i++)
    do something with list.get(i);
```

效率低得令人惊心。每当你查找另一个元素时，搜索都会从列表的开头重新开始。`LinkedList` 对象并没有缓存位置信息。

---

![Image](img/note.jpg) **注意：**

`get` 方法有一个轻微的优化：如果索引至少为 `size() / 2`，则元素的搜索将从列表末尾开始。

---

列表迭代器接口（list iterator）还有一个方法可以告诉你当前位置的索引。事实上，由于 Java 迭代器在概念上指向元素之间，因此它有两个这样的方法：`nextIndex` 方法返回下一次调用 `next` 将返回的元素的整数索引；`previousIndex` 方法返回下一次调用 `previous` 将返回的元素的索引。当然，它仅仅比 `nextIndex` 小 1。这些方法是高效的——迭代器会维护其当前位置的计数。

最后，如果你有一个整数索引 `n`，那么 `list.listIterator(n)` 返回一个指向索引为 `n` 的元素之前的迭代器。也就是说，调用 `next` 产生的元素与 `list.get(n)` 相同；但获取该迭代器是低效的。

如果你有一个链表只有几个元素，你不必过度担心 `get` 和 `set` 方法的代价。但既然如此，起初为什么要用链表呢？使用链表的唯一理由是为了最小化在列表中间插入和删除元素的成本。如果你只有几个元素，可以直接使用 `ArrayList`。

我建议你直接避开所有使用整数索引来表示链表位置的方法。如果你想对集合进行随机访问，请使用数组或 `ArrayList`，而不是链表。

Listing 9.1 中的程序演示了链表的工作。它简单创建了两个列表，合并它们，然后从第二个列表中删除每个第二个元素，最后测试了 `removeAll` 方法。我建议你跟踪程序流，并特别注意迭代器。你可能会发现画迭代器位置的图会有帮助，如下所示：

```
|ACE  |BDFG

A|CE  |BDFG

AB|CE B|DFG

. . .
```

注意，该调用：

```java
System.out.println(a);
```

通过调用 `AbstractCollection` 中的 `toString` 方法打印了链表 `a` 中的所有元素。

**Listing 9.1** `linkedList/LinkedListTest.java`

```java
package linkedList;

import java.util.*;

/**
 * 此程序演示了链表的操作。
 * @version 1.12 2018-04-10
 * @author Caymann
 */
public class LinkedListTest
{
  public static void main(String[] args)
  {
    var a = new LinkedList<String>();
    a.add("Amy");
    a.add("Carl");
    a.add("Erica");

    var b = new LinkedList<String>();
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

    // 从 b 删除每个单词
    bIter = b.iterator();
    while (bIter.hasNext())
    {
      bIter.next(); // 跳过一个元素
      if (bIter.hasNext())
      {
        bIter.next(); // 跳过下一个元素
        bIter.remove(); // 删除该元素
      }
    }

    System.out.println(b);

    // 批量操作：从 a 中删除 b 中的所有单词
    a.removeAll(b);

    System.out.println(a);
  }
}
```

## `java.util.List<E>` 1.2

- `ListIterator<E> listIterator()` 返回一个用于访问列表元素的列表迭代器。
- `ListIterator<E> listIterator(int index)` 返回一个用于访问列表元素的列表迭代器，其下一次调用 `next` 将返回给定索引的元素。
- `void add(int i, E element)` 在指定位置添加元素。
- `void addAll(int i, Collection<? extends E> elements)` 将集合中的所有元素添加到指定位置。
- `E remove(int i)` 删除并返回指定位置的元素。
- `E get(int i)` 获取指定位置的元素。
- `E set(int i, E element)` 用新元素替换指定位置的元素并返回旧元素。
- `int indexOf(Object element)` 返回指定元素首次出现的索引，如果未找到则返回 -1。
- `int lastIndexOf(Object element)` 返回指定元素最后一次索引，如果未找到则返回 -1。

## `java.util.ListIterator<E>` 1.2

- `void add(E newElement)` 在当前位置之前添加元素。
- `void set(E newElement)` 用新元素替换由 `next` 或 `previous` 最近访问的元素。如果上次调用 `next` 或 `previous` 后列表结构被修改，则抛出 `IllegalStateException`。
- `boolean hasPrevious()` 如果反向遍历列表还有其他元素则返回 `true`。
- `E previous()` 返回上一个对象。如果到达列表开头，则抛出 `NoSuchElementException`。
- `int nextIndex()` 返回下一次调用 `next` 将返回的索引。
- `int previousIndex()` 返回下一次调用 `previous` 将返回的索引。

## `java.util.LinkedList<E>` 1.2

- `LinkedList()` 构建一个空链表。
- `LinkedList(Collection<? extends E> elements)` 构建一个链表并添加集合中的所有元素。
- `void addFirst(E element)` 和 `void addLast(E element)` 在列表开头或末尾添加元素。
- `E getFirst()` 和 `E getLast()` 返回列表开头或末尾的元素。
- `E removeFirst()` 和 `E removeLast()` 删除并返回列表开头或末尾的元素。

链表和数组允许你指定元素的排列顺序。然而，如果你在寻找某个特定元素但不记得它的位置，你就需要访问所有元素，直到找到匹配的项为止。如果集合中包含许多元素，这可能会非常耗时。

如果你不在乎元素的顺序，则某些数据结构可以让你更快速地找到元素。缺点是，这些数据结构无法让你控制元素出现的顺序。这些数据结构按照有利于其自身目的的顺序来组织元素。

## 哈希表

一种用于快速查找对象的常用数据结构是 `hash table`（哈希表）。哈希表为每个对象计算一个整数，即 `hash code`（哈希码）。哈希码是以某种方式从对象的实例字段得出的，最好是使得具有不同数据的对象产生不同的代码。表 9.2 列出了几个 `String` 类的 `hashCode()` 方法产生的哈希码示例。

如果你定义了自己的类，则你需要负责实现自己的 `hashCode()` 方法——更多信息请参阅第 5 章。你的实现需要与 `equals()` 方法兼容：如果 `a.equals(b)`，那么 `a` 和 `b` 必须具有相同的哈希码。

**表 9.2** 由 `hashCode()` 方法产生的哈希码

![Images](img/09tab02.jpg)

现在重要的是，哈希码可以被快速计算，且计算仅取决于需要哈希的对象的状态，而不取决于哈希表中的其他对象。

## 在 Java 中实现

在 Java 中，哈希表被实现为链表数组。每个列表被称为一个 `bucket`（桶）（参见图 9.10）。要找到对象在表中的位置，请计算它的哈希码并对桶的总数取模。得到的数字是存放该元素的桶的索引。

例如，如果一个对象的哈希码为 76268 且有 128 个桶，则该对象被放在第 108 号桶中（因为 `76268 % 128` 的余数是 108）。也许你很幸运，该桶中没有其他元素。这时你只需将元素插入该桶中。

当然，有时你会遇到一个已经填充的桶。这被称为 `hash collision`（哈希冲突）。然后，将新对象与桶中的所有对象进行比较，看它是否已经存在。如果哈希码分布足够随机且桶的数量足够大，通常只需要几次比较即可。

![Images](img/09fig10.jpg)

**图 9.10** 哈希表

---

![Image](img/note.jpg) **注意：**

从 Java 8 开始，当桶变满时，它们会从链表变为平衡二叉树。如果哈希函数选择不当导致产生许多冲突，或者恶意代码试图用许多具有相同哈希码的值淹没哈希表，这将提高性能。

---

![Image](img/tip.jpg) **提示：**

如果可能的话，哈希表的键应该属于实现 `Comparable` 接口的类。这样你就能保证不会因为哈希码分布不均而遭受性能低下的影响。

## 性能与调优

如果你想对哈希表的性能有更多控制，可以指定初始桶的数量。桶的数量是指用于收集具有相同哈希值的对象的桶数。如果向哈希表中插入了更多的元素，冲突的数量就会增加，检索性能也会受到影响。

如果你大致知道表中最终会有多少元素，可以设置桶的数量。通常，你应该将其设置为预期元素数量的 75% 到 150% 之间。一些研究人员认为，将桶的数量设置为质数是一个好主意，可以防止键的聚集。然而，这并没有结论。

标准库使用的桶的数量是 2 的幂，默认为 `16`。（你为表大小提供的任何值都会被自动舍入到下一个 2 的幂。）

当然，你并不总是知道需要存储多少个元素，或者你的初始猜测可能太低了。如果哈希表太满，就需要进行 `rehashed`（重哈希）。要重哈希表，会创建一个具有更多桶的新表，将所有元素插入新表，并丢弃原表。

`load factor`（负载因子）决定了哈希表何时进行重哈希。例如，如果负载因子为 `0.75`（默认值）且表填充率超过 75%，则会自动进行重哈希，桶的数量翻倍。对于大多数应用程序，将负载因子保持在 `0.75` 是合理的。

## HashSet

哈希表可以用于实现几种重要的数据结构。其中简单的是 `set`（集合）类型。集合是一个没有重复元素的元素集合。集合的 `add()` 方法首先尝试查找要添加的对象，仅在其尚不存在时才进行添加。

Java 集合库提供了一个基于哈希表实现集合的 `HashSet` 类。你通过 `add()` 方法添加元素。`contains()` 方法被重写，以便进行快速查找以检查元素是否已存在于集合中。它只检查一个桶中的元素，而不是集合中的所有元素。

哈希集合迭代器依次访问所有的桶。

```java
package set;

import java.util.*;

/**
 * 该程序使用集合打印唯一的单词。
 * @version 2015-06-21
 * @author Caymann
 */
public class Set {

    public static void main(String[] args) {

        var words = new HashSet<String>();

        long totalTime = 0;

        try (var in = new Scanner(System.in)) {

            while (in.hasNext()) {

                String word = in.next();

                long callTime = System.currentTimeMillis();

                words.add(word);

                callTime = System.currentTimeMillis() - callTime;

                totalTime += callTime;
            }
        }

        Iterator<String> iter = words.iterator();

        for (int i = 1; i <= 20 && iter.hasNext(); i++) {

            System.out.println(iter.next());
        }

        System.out.println(". . .");

        System.out.println(words.size() + " distinct words. " + totalTime + " milliseconds.");
    }
}
```

- `HashSet(int initialCapacity, float loadFactor)`

  构造一个具有指定容量和负载因子的空哈希集合。如果大小/容量的比例超过负载因子，哈希表将重新哈希到一个更大的哈希表中。

## `java.lang.Object` 1.0

- `int hashCode()`

  返回此对象的哈希码。哈希码可以是任意整数，正数或负数均可。`equals` 和 `hashCode` 的定义必须保持兼容：如果 `x.equals(y)` 为 `true`，则 `x.hashCode()` 的值必须与 `y.hashCode()` 相同。

### 9.3.4 Tree Sets

`TreeSet` 类与哈希集合类似，但增加了一项改进。树集是一个排序集合。你可以以任何顺序将元素插入到集合中。当你遍历集合时，值将自动按排序顺序呈现。

例如，假设你插入了三个字符串，然后访问你添加的所有元素。

```java
var sorter = new TreeSet<String>();

sorter.add("Bob");

sorter.add("Amy");

sorter.add("Carl");

for (String s : sorter) System.out.println(s);
```



然后，值将按排序顺序打印：`Amy Bob Carl`。正如类名所示，排序是通过树数据结构实现的。（当前实现使用了红黑树。关于红黑树的详细描述，请参考 Thomas Cormen、Charles Leiserson、Ronald Rivest 和 Clifford Stein 等的《算法导论》，The MIT Press，2009。）每当向树添加一个元素时，它都会被放在正确的排序位置。因此，迭代器始终按排序顺序访问元素。

向树中添加元素比向哈希表中添加元素要慢——参见表 9.3 的比较。但它仍然比在数组或链列表中检查重复项要快得多。如果树包含 *n* 个元素，则平均需要 log[2] *n* 次比较来找到新元素的正确位置。例如，如果树已经包含了 1,000 个元素，添加一个新元素大约需要 10 次比较。

---

![Image](img/note.jpg) **注意：**

为了使用树集，你必须能够比较元素。元素必须实现 `Comparable` 接口，或者你需要在构建集合时提供一个 `Comparator`。（`Comparable` 和 `Comparator` 接口是在第 6 章中引入的。）

---

**表 9.3** 向哈希集合和树集添加元素

![Images](img/09tab03.jpg)

如果你回看表 9.3，你可能会疑惑是否应该始终使用树集而不是哈希集合。毕竟，添加元素似乎并没有花费多少时间，而且元素是自动排序的。答案取决于你正在收集的数据。如果你不需要数据排序，就没有理由为排序的开销支付额外代价。更重要的是，对于某些数据，想出一个排序顺序比写出一个哈希函数困难得多。哈希函数只需要相当好地打乱对象即可，而比较函数必须以完全精确的度区分对象。

为了使这种区别更具体，考虑收集一组矩形的任务。如果你使用 `TreeSet`，你需要提供一个 `Comparator<Rectangle>`。你如何比较两个矩形？按面积吗？这行不通。你可能有两个坐标不同但面积相同的矩形。树的排序顺序必须是全序。任何两个元素都必须是比较的，且只有当元素相等时，比较结果才能为零。矩形有这样的排序顺序（坐标的字典序），但计算起来既不自然又繁琐。相比之下，`Rectangle` 类已经定义了哈希函数。它简单地对坐标进行哈希。

---

![Image](img/note.jpg) **注意：**

从 Java 6 开始，`TreeSet` 类实现了 `NavigableSet` 接口。该接口增加了几个方便的方法，用于定位元素和反向遍历。详情请参见 API 注释。

---

Listing 9.3 中的程序构建了两个 `Item` 对象的树集。第一个集合按部分号排序，这是 `Item` 对象的默认排序顺序。第二个集合按描述排序，使用了自定义的比较器。

**列表 9.3** `treeSet/TreeSetTest.java`

```java
 1  package treeSet;

 2

 3  import java.util.*;

 4

 5  /**

 6    * 此程序通过比较描述来对 Item 对象集合进行排序。

 7    * @version 1.13 2018-04-10

 8    * @author Cay Horstmann

 9    */

10  public class TreeSetTest

11  {

12      public static void main(String[] args)

13      {

14        var parts = new TreeSet<Item>();

15      parts.add(new Item("Toaster", 123));

16      parts.add(new Item("Widget", 456));

17      parts.add(new Item("Modem", 992));

18      System.out.println(parts);

19

20      var sortByDescription = new TreeSet<Item>(Comparator.comparing(Item::getDescription));

21

22      sortByDescription.addAll(parts);

23      System.out.println(sortByDescription);

24  }
```

**列表 9.4** `treeSet/Item.java`

```java
 1  package treeSet;

 2

 3  import java.util.*;

 4

 5  /**

 6    * 具有描述和部分号的 item。

 7    */

8  public class Item implements Comparable<Item>

9  {

10     private String description;

11     private int partNumber;

12

13     /**

14     * 构造一个 item。

15     * @param description item 的描述

16     * @param partNumber item 的号

17     */

18     public Item(String description, int partNumber)

19     {

20         description = description;

21         partNumber = partNumber;

22     }

23

24     /**

25     * 获取此 item 的描述。

26     * @return 描述

27     */

28     public String getDescription()

29     {

30         return description;

31     }

32

33     public String toString()

34     {

35         return "[description=" + description + ", partNumber=" + partNumber + "]";

36     }

37

38     public boolean equals(Object otherObject)

39     {

40         if (this == otherObject) return true;

41         if (otherObject == null) return false;

42         if (getClass() != otherObject.getClass()) return false;

43         var other = (Item) otherObject;

44         return Objects.equals(description, other.description) && partNumber == other.partNumber;

45     }

46

47     public int hashCode()

48     {

49         return Objects.hash(description, partNumber);

50     }

51

52     public int compareTo(Item other)

53     {

54         int diff = Integer.compare(partNumber, other.partNumber);

55         return diff != 0 ? diff : description.compareTo(other.description);

56     }

57 }
```

- `Iterator<E> descendingIterator()`

  返回一个按降序遍历此集合的迭代器。

#### 9.3.5 队列与双端队列

正如我们已经讨论过的，队列（queue）允许你在尾部高效添加元素并从头部移除元素。双端队列，或 `deque`，允许你在头部和尾部高效添加或移除元素。不支持在中间添加元素。Java 6 引入了 `Deque` 接口。它由 `ArrayDeque` 和 `LinkedList` 类实现，这两个类都提供了根据需要增长大小的双端队列。在第 12 章中，你将看到有界队列和双端队列。

*** `java.util.Queue<E>` **5**

- `boolean add(E element)`
- `boolean offer(E element)`

  将给定元素添加到此队列的尾部，如果队列未满则返回 `true`。如果队列已满，第一个方法将抛出 `IllegalStateException`，而第二个方法返回 `false`。

- `E remove()`
- `E poll()`

  如果队列不为空，则移除并返回此队列头部的元素。如果队列为空，第一个方法将抛出 `NoSuchElementException`，而第二个方法返回 `null`。

- `E element()`
- `E peek()`

  如果队列不为空，则返回此队列头部的元素而不将其移除。如果队列为空，第一个方法将抛出 `NoSuchElementException`，而第二个方法返回 `null`。

*** `java.util.Deque<E>` **6**

- `void addFirst(E element)`
- `void addLast(E element)`
- `boolean offerFirst(E element)`
- `boolean offerLast(E element)`

  将给定元素添加到此双端队列的头部或尾部。如果双端队列已满，前两个方法抛出 `IllegalStateException`，而后两个方法返回 `false`。

- `E removeFirst()`
- `E removeLast()`
- `E pollFirst()`
- `E pollLast()`

  如果双端队列不为空，则移除并返回此双端队列头部的元素。如果双端队列为空，前两个方法抛出 `NoSuchElementException`，而后两个方法返回 `null`。

- `E getFirst()`
- `E getLast()`
- `E peekFirst()`
- `E peekLast()`

  如果双端队列不为空，则返回此双端队列头部的元素而不将其移除。如果双端队列为空，前两个方法抛出 `NoSuchElementException`，而后两个方法返回 `null`。

`java.util.ArrayDeque<E>` **6**

- `ArrayDeque()`
- `ArrayDeque(int initialCapacity)`

  构造一个初始容量为 16 或给定初始容量的无界双端队列。

#### 9.3.6 优先级队列

优先级队列在元素以任意顺序插入后，按排序顺序检索元素。也就是说，每当你调用 `remove` 方法时，都会得到当前优先级队列中最小的元素。然而，优先级队列并没有对其所有元素进行排序。如果你遍历这些元素，它们并不一定是有序的。优先级队列利用了一种名为 `heap`（堆）的优雅且高效的数据结构。堆是一种自组织的二叉树，在其中 `add` 和 `remove` 操作会导致最小元素向根节点聚集，而无需浪费时间对所有元素进行排序。

就像 `TreeSet` 一样，优先级队列可以包含实现了 `Comparable` 接口的类的元素，或者是你在构造函数中提供的 `Comparator` 对象。

优先级队列的一个典型用途是任务调度。每个任务都有一个优先级。任务按随机顺序添加。每当有新任务可以启动时，优先级最高的任务就会从队列中移除。（传统上优先级 1 是“最高”优先级，因此 `remove` 操作产生最小元素。）

代码列表 9.5 展示了优先级队列的实际运行。与 `TreeSet` 中的迭代不同，这里的迭代不会按排序顺序访问元素。然而，移除操作总是产生剩余最小元素。

**代码列表 9.5** `priorityQueue/PriorityQueueTest.java`

```java
 1  package priorityQueue;

 2

 3  import java.util.*;

 4  import java.time.*;

 5

 6  /**

 7   * 此程序演示了优先级队列的使用。

 8    * @version 1.02 2015-06-20

 9    * @author Cay Horstmann

 10  */

 11  public class PriorityQueueTest

 12  {

 13      public static void main(String[] args)

 14      {

 15          var pq = new PriorityQueue<LocalDate>();

 16          pq.add(LocalDate.of(1906, 12, 9)); // G. Hopper

 17          pq.add(LocalDate.of(1806, 12, 9)); // Lovelace

 18          pq.add(LocalDate.of(1815, 6, 10)); // Lovelace

 19          pq.add(LocalDate.of(1910, 12, 3)); // von Neumann

 20          pq.add(LocalDate.of(1903, 6, 22)); // Zuse

 21          pq.add(LocalDate.of(1912, 6, 23)); // Turing

 22          for (LocalDate date : pq) {

 23              System.out.println(date);

 24          }

 25      }

 26  }
```

`java.util.PriorityQueue` **5**

- `PriorityQueue()`
- `PriorityQueue(int initialCapacity)`
- `PriorityQueue(int initialCapacity, Comparator<? super E> c)`

### 9.4 Map（映射）

Map 是允许你将键映射到值的集合。每个键恰好映射到一个值。映射的作用正是如此。在接下来的章节中，你将学习如何。

#### 9.4.1 基础 Map 操作

Java 提供了两个通用实现：`HashMap` 和 `TreeMap`。它们都实现了 `Map` 接口。`HashMap` 对键进行哈希处理，而 `TreeMap` 使用排序来组织键。值不进行哈希或比较。你应该选择哈希映射还是树映射？和集合一样，哈希通常速度更快，如果你不需要按顺序访问键，那么它是首选。

这里是设置员工哈希映射的方法：

```java
var staff = new HashMap<String, Employee>();

var harry = new Employee("Harry Hacker");

staff.put("987-996", harry);
```

每当你向映射添加对象时，必须提供一个键。在我们的例子中，键是一个字符串，对应的值是一个 `Employee` 对象。为了检索对象，必须使用（因此要记住）键。

```java
var id = "987-9996";

Employee e = staff.get(id); // 获取 harry
```

如果映射中没有存储指定键的信息，`get` 返回 `null`。`null` 返回值可能不方便。有时，你有一个良好的默认值，可以用于不存在的键。这时可以使用 `getOrDefault` 方法。

```java
Map<String, Integer> scores = . .;

int score = scores.getOrDefault(id, 0); // 如果 id 不存在则获取 0
```

```java
scores.forEach((k, v) ->
    System.out.println("key=" + k + ", value=" + v));
```

`列表 9.6` 展示了 map 的工作原理。我们首先向 map 添加键/值对。然后，我们从 map 中移除一个键，这也会移除其关联的值。接下来，我们更改与键关联的值，并调用 `get` 方法来查找值。最后，我们遍历条目集（entry set）。

**列表 9.6** `map/MapTest.java`

```java
 1  package map;

 2

3  import java.util.*;

 4

5  /**

6   * 此程序演示了键类型为 String、值类型为 Employee 的 map 的用法。

7   * @version 1.12 2015-06-21

 8   * @author Cay Horstmann

 9   */

10  public class MapTest

11  {

12      public static void main(String[] args)13

14          var staff = new HashMap<String, Employee>();

15          staff.put("144-25-5464", new Employee("Amy Lee"));

16          staff.put("567-24-2546", new Employee("Harry Hacker"));
```



```java
staff.put("157-62-7935", new Employee("Gary Cooper"));
staff.put("456-62-5527", new Employee("Francesca Cruz"));

// 打印所有条目
System.out.println(staff);

// 移除一个条目
staff.remove("567-24-2546");

// 替换一个条目
staff.put("456-62-5527", new Employee("Francesca Miller"));

// 查找一个值
System.out.println(staff.get("157-62-7935"));

// 遍历所有条目
staff.forEach((k, v) ->
    System.out.println("key=" + k + ", value=" + v));
```

## `java.util.Map<K, V>`

- `V get(Object key)` 获取与键关联的值；返回与键关联的对象，如果找到该键则返回 `null`。实现类可能禁止 `null` 键。
- `default V getOrDefault(Object key, V defaultValue)` 获取与键关联的值；返回与键关联的对象，如果未找到该键则返回 `defaultValue`。
- `V put(K key, V value)` 将键和值的关联放入 map 中。如果键已存在，则替换旧值。此方法返回该键的旧值，如果键不存在则返回 `null`。实现类可能禁止 `null` 键或值。
- `void putAll(Map<? extends K, ? extends V> entries)` 将指定 map 中的所有条目添加到此 map 中。
- `boolean containsKey(Object key)` 如果键存在 map 中，返回 `true`。
- `boolean containsValue(Object value)` 如果值存在 map 中，返回 `true`。
- `default void forEach(BiConsumer<? super K, super V> action)` 将操作应用于此 map 的所有键/值对。

## `java.util.HashMap<K, V>`

- `HashMap()`
- `HashMap(int initialCapacity)`
- `HashMap(int initialCapacity, float loadFactor)` 构造一个具有指定容量和负载因子的空哈 map（负载因子是 `0.0` 到 `1.0` 之间的数字，决定了哈希表在达到百分之几填充率时重新哈希为更大的表）。默认负载因子为 `0.75`。

## `java.util.TreeMap<K, V>`

- `TreeMap()` 为实现 `Comparable` 接口的键构造一个空树 map。
- `TreeMap(Comparator<? super K> c)` 构造一个树 map 并使用指定的比较器对其键进行排序。
- `TreeMap(Map<? extends K, ? extends V> entries)` 构造一个树 map 并添加来自 map 的所有条目。
- `TreeMap(SortedMap<? extends K, ? extends V> entries)` 构造一个树 map，添加来自排序 map 的所有条目，并使用与给定 map 相同的元素比较器。

## `java.util.SortedMap<K, V>`

- `Comparator<? super K> comparator()` 返回用于键键的比较器，如果使用 `Comparable` 接口的 `compareTo` 方法比较则返回 `null`。
- `K firstKey()`
- `K lastKey()` 返回 map 中最小或最大的键。

### 9.4.2 更新 map 条目

处理 map 时棘手的部分是更新条目。通常，你获取与键关联的旧值，更新它，然后放回更新后的值。但你必须担心键第一次出现的特殊情况。考虑使用 map 来统计一个单词在文件中出现的次数。当我们看到一个单词时，想要这样增加计数器：

```java
counts.put(word, counts.get(word) + 1);
```

如果键第一次出现，`counts.get(word)` 会返回 `null`，导致 `null + 1` 抛出 `NullPointerException`。使用 `getOrDefault` 方法可以解决这个问题：

```java
counts.put(word, counts.getOrDefault(word, 0) + 1);
```

或者使用 `compute` 方法：

```java
counts.compute(word, (k, v) -> v == null ? 1 : v + 1);
```

或者使用 `merge` 方法，这最简洁：

```java
counts.merge(word, 1, Integer::sum);
```

## `java.util.Map<K, V>`

- `default V merge(K key, V value, BiFunction<? super V, ? super V, ? extends V> remappingFunction)` 如果键不存在，则将其关联 `value`；如果键存在，则使用 `remappingFunction` 旧值和新值，返回新值。
- `default V computeIfAbsent(K key, Function<? super K,? extends V> mappingFunction)` 如果键不存在或关联 `null`，则将其关联 `mappingFunction` 的结果并返回 `null`。否则返回关联的值。
- `default V compute(K key, BiFunction<? super K, super V,? extends V> remappingFunction)` 如果键存在且非 `null`，则使用 `remappingFunction` 计算新值并返回它；如果键不存在则返回 `null`。
- `default V computeIfPresent(K key, BiFunction<? super K, super V,? extends V> remappingFunction)` 如果键存在且关联非 `null`，则使用 `remappingFunction` 计算新值并返回它；否则返回 `null`。
- `default V replace(K key, V value)` 如果键存在且关联非 `null`，则将其替换为 `value` 并返回旧值。
- `default V replace(K key, BiFunction<? super K, super V,? extends V> remappingFunction)` 如果键存在且关联非 `null`，则使用 `remappingFunction` 计算新值并返回旧值。
- `void replaceAll(BiFunction<? super K,? super V,? extends V> function)` 对所有条目调用函数。

### 9.4.3 Map 视图

集合框架并不将 map 本身视为集合。（其他数据结构框架将 map 视为键/值对的集合，或者通过键索引的值的集合。）然而，你可以获取 map 的*视图*——实现了 `Collection` 接口或其一个子接口的对象。

有三个视图：键的集合、值的集合（不是集合）以及键/值对的集合。键和键/值对形成集合，因为 map 中只能有一个键副本。以下方法返回这三个视图：

```java
Set<K> keySet();

Collection<V> values();

Set<Map.Entry<K, V>> entrySet();
```

注意 `keySet` 不是 `HashSet` 或 `TreeSet`，而是实现了 `Set` 接口的其他类的对象。`Set` 接口扩展了 `Collection` 接口。因此，你可以像使用任何集合一样使用 `keySet`。

例如，你可以枚举 map 的所有的键：

```java
Set<String> keys = map.keySet();

for (String key : keys) {
    do something with key;
}
```

如果你想同时查看键和值，可以通过枚举条目（entries）来避免对值的重复查找。请使用以下代码骨架：

```java
for (Map.Entry<String, Employee> entry : staff.entrySet()) {
    String k = entry.getKey();
    Employee v = entry.getValue();
    do something with k, v;
}
```

> **提示：**
>
> 你可以使用 `var` 声明来避免繁琐的 `Map.Entry`。
>
> ```java
> for (var entry : map.entrySet()) {
>     do something with entry.getKey(), entry.getValue();
> }
> ```
>
> 或者简单地使用 `forEach` 方法：
>
> ```java
> map.forEach((k, v) -> {
>     do something with k, v;
> });
> ```

如果你在键集视图上调用迭代器的 `remove` 方法，你实际上会从 map 中删除该键及其关联的值。然而，你不能向键集视图中添加元素。在不添加值的情况下只添加键是毫无意义的。如果你尝试调用 `add` 方法，它会抛出 `UnsupportedOperationException`。条目集视图也有同样的的限制，尽管在概念上添加新的键/值对是有有意义的。

### `java.util.Map<K, V>` 1.2

- `Set<Map.Entry<K, V>> entrySet()` 返回 `Map.Entry` 对象的集合视图，即 map 中的键/值对。你可以从这个集合中移除元素，这些元素也会从 map 中移除，但你不能添加任何元素。
- `Set<K> keySet()` 返回 map 中所有键的集合视图。你可以从这个集合中移除元素，相应的键和关联的值也会从 map 中移除，但你不能添加任何元素。
- `Collection<V> values()` 返回 map 中所有值的集合视图。你可以从这个集合中移除元素，被移除的值及其对应的键也会从 map 中移除，但你不能添加任何元素。

### `java.util.Map.Entry<K, V>` 1.2

- `K getKey()`
- `V getValue()` 返回此条目的键或值。
- `V setValue(V newValue)` 将关联 map 中的值更改为新值并返回旧值。
- `static <K, V> Map.Entry<K,V> copyOf(Map.Entry<? extends K,? extends V> map)` 17 产生给定 map 条目的拷贝。与 map 条目集中的元素不同，该拷贝不是“活”的。调用 `setValue` 不更新任何 map。

### 9.4.4 Weak Hash Maps

集合类库有几个针对特殊需求的 map 类，我们将在本节和接下来的章节中简要讨论。

`WeakHashMap` 类的设计是为了解决一个有趣的问题：如果一个值的键不再被程序中的任何地方使用，会发生什么？假设键的最后一个引用已经消失。那么，就没有办法可以引用该值对象了。但是由于程序的任何部分都不再持有该键，该键/值对无法从 map 中移除。为什么垃圾回收器不能移除它？移除未使用的对象不应该是垃圾回收器的工作吗？

遗憾的是，并没有那么简单。垃圾回收器追踪活对象。只要 map 对象是活的，它所有的桶（buckets）都是活的且不会被回收。因此，你的程序应该注意从长寿命 map 中移除未使用的值。或者，你可以使用 `WeakHashMap`。这种数据结构与垃圾回收器协作，当键的唯一引用来自哈希表条目时，移除键/值对。

这是该机制的内部原理。`WeakHashMap` 使用弱引用（weak references）来持有键。`WeakReference` 对象持有另一个对象的引用——在我们的案例中哈希表键。这种类型的对象会被垃圾回收器特殊对待。通常，如果垃圾回收器发现某个对象没有指向它的引用，它会直接回收该对象。然而，如果对象仅通过 `WeakReference` 可达，垃圾回收器仍然回收该对象，但将导致它的弱引用放入队列中。`WeakHashMap` 的操作会定期检查该队列中新到达的弱引用。队列中弱引用的出现意味着该键不再被任何人使用并已被收集。`WeakHashMap` 随后移除关联的条目。

### 9.4.5 Linked Hash Sets and Maps

`LinkedHashSet` 和 `LinkedHashMap` 类会记住你插入元素的顺序。这样，你就可以避免哈希表中元素看似随机的顺序。当条目被插入到表时，它们被连接到双向链表中。

![Image](img/tip.jpg) **图 9.11** 哈希表。哈希 map 也可以使用访问顺序而非插入顺序来遍历 map。每当你调用 `get` 或 `put`，受影响的条目都会从当前位置移除并置于链表的末尾。（只影响链表中的位置，不影响哈希桶。）

访问顺序对于实现缓存的“最近最未使用”（LRU）策略非常有用。例如，你可能希望将频繁访问的条目保留在内存中，并从数据库读取较少访问的对象。当不在表中找不到条目且表已满时，你可以获取一个表的迭代器并移除它枚举的前几个元素。那些条目就是最近最使用的。

你甚至可以自动化该过程。创建一个 `LinkedHashMap` 的子类并重写方法：

```java
protected boolean removeEldestEntry(Map.Entry<K, V> eldest);
```

添加新条目时，每当你的方法返回 `true`，`eldest` 条目就会被移除。例如，以下缓存的大小保持在最多 100 个元素：

```java
var cache = new LinkedHashMap<K, V>(128, 0.75F, true) {
    protected boolean removeEldestEntry(Map.Entry<K, V> eldest) {
        return size() > 100;
    }
};
```

或者，你可以考虑根据 `eldest` 条目来决定是否移除它。例如，你可能想要检查与条目一起存储戳。

### 9.4.6 Enumeration Sets and Maps

`EnumSet` 是一种高效的集合实现，元素属于枚举类型（enumerated type）。由于枚举类型的实例数量有限的，`EnumSet` 在内部简单地实现为位位序列。如果集合中存在对应的值，则该位被开启。

`EnumSet` 类没有公共构造函数。使用静态工厂方法来构建该集合。

```java
enum Weekday {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}

EnumSet<Weekday> always = EnumSet.allOf(Weekday.class);
EnumSet<Weekday> never = EnumSet.noneOf(Weekday.class);
EnumSet<Weekday> workday = EnumSet.range(Weekday.MONDAY, Weekday.FRIDAY);
EnumSet<Weekday> mwf = EnumSet.of(
    Weekday.MONDAY,
    Weekday.WEDNESDAY,
    Weekday.FRIDAY
);
```

你可以使用 `Set` 接口的常用方法来修改 `EnumSet`。

`EnumMap` 是一种键属于枚举类型的映射。它被实现为一个值的数组，既简单又高效。你需要在构造函数中指定键类型：

```java
var personInCharge = new EnumMap<Weekday, Employee>(Weekday.class);
```



![Image](img/note.jpg) **注意：**

在`EnumSet`的 API 文档中，你会看到类似`E extends Enum<E>`的这种奇怪类型参数。这仅仅意味着“`E` 是一个枚举类型”。所有枚举类型都继承自泛型类`Enum`。例如，`Weekday`继承自`Enum<Weekday>`。

#### 9.4.7 标识哈希映射

`IdentityHashMap`有非常特殊的用途。在这里，键的哈希值不通过`hashCode`方法计算，而是通过`System.identityHashCode`方法计算。这是`Object.hashCode`用于根据对象的内存地址计算哈希值的方法。此外，在比较对象时，`IdentityHashMap`使用`==`而不是`equals`。

换句话说，不同的键对象即使内容相同，也会被认为是不同的。该类用于实现对象遍历算法（例如对象序列化），在这些算法中，你需要跟踪哪些对象已经被遍历过了。

#### `java.util.WeakHashMap<K, V>` **1.2**

- `WeakHashMap()`
- `WeakHashMap(int initialCapacity)`
- `WeakHashMap(int initialCapacity, float loadFactor)`

构造一个指定容量和负载因子的空哈希映射。

#### `java.util.LinkedHashSet<E>` **1.4**

- `LinkedHashSet()`
- `LinkedHashSet(int initialCapacity)`
- `LinkedHashSet(int initialCapacity, float loadFactor)`

构造一个指定容量和负载因子的空链接哈希集。

#### `java.util.LinkedHashMap<K, V>` **1.4**

- `LinkedHashMap()`
- `LinkedHashMap(int initialCapacity)`
- `LinkedHashMap(int initialCapacity, float loadFactor)`
- `LinkedHashMap(int initialCapacity, float loadFactor, boolean accessOrder)`

构造一个指定容量、负载因子和排序的空链接哈希映射。`accessOrder`参数为`true`时按访问顺序，为`false`时按插入顺序。

- `protected boolean removeEldestEntry(Map.Entry<K, V> eldest)`

如果你想移除`eldest`条目，应该重写此方法并返回`true`。`eldest`参数是要考虑移除的条目。该方法在条目添加到映射后调用。默认实现返回`false`——默认不会移除旧元素。但是，你可以重新定义此方法以选择性地返回`true`——例如，如果最老的条目符合某个条件，或者映射超过了某个大小。

#### `java.util.EnumSet<E extends Enum<E>>` **5**

- `static <E extends Enum<E>> EnumSet<E> allOf(Class<E> enumType)`

返回一个包含给定枚举类型所有值的可变集合。

- `static <E extends Enum<E>> EnumSet<E> noneOf(Class<E> enumType)`

返回一个初始为空的可变集合。

- `static <E extends Enum<E>> EnumSet<E> range(E from, E to)`

返回一个包含从`from`到`to`（包含）所有值的可变集合。

- `static <E extends Enum<E>> EnumSet<E> of(E e)`

`. . .`

- `static <E extends Enum<E>> EnumSet<E> of(E e1, E e2, E e3, E e4, E e5)`
- `static <E extends Enum<E>> EnumSet<E> of(E first, E... rest)`

返回一个包含给定元素的可变集合，这些元素不能为`null`。

- `public static <E extends Enum<E>> EnumSet<E> copyOf(EnumSet<E> s)`
- `public static <E extends Enum<E>> EnumSet<E> copyOf(Collection<E> c)`

创建一个初始包含给定元素的可变集合。在第二种方法中，`c`必须是`EnumSet`或者非空（以便确定元素类型）。

#### `java.util.EnumMap<K extends Enum<K>, V>` **5**

- `EnumMap(Class<K> keyType)`

构造一个键具有给定类型的空可变映射。

#### `java.util.IdentityHashMap<K, V>` **1.4**

- `IdentityHashMap()`
- `IdentityHashMap(int expectedMaxSize)`

构造一个容量为`expectedMaxSize`的空标识哈希映射。

#### `java.lang.System` **1**

- `static int identityHashCode(Object obj)`

返回指定对象的哈希值，该值与`System.identityHashCode(Object)`返回的结果相同。

### 9.5 拷贝与视图

Java 9 引入了产生带有给定元素的集合、列表或映射的静态方法。例如：

```java
List<String> names = List.of("Peter", "Paul", "Mary");

Set<Integer> numbers = Set.of(2, 3);
```

对于映射，你可以这样指定键和值：

```java
Map<String, Integer> scores = Map.of("Peter", 2, "Paul", 3);
```

元素、键或值不能为`null`。集合和映射的键不能重复：

```java
numbers = Set.of(1, null); // 错误—null

scores = Map.of("Peter", 4, "Peter", 2); // 错误—重复键
```

![Image](img/caution.jpg) **注意：**

不保证这些集合和映射的迭代顺序。事实上，该顺序是故意打乱的，并使用在虚拟机启动时随机生成的种子。看这两个`jshell`运行结果：

```text
$ jshell -q

jshell> Set.of("Peter", "Paul", "Mary")

$1 ==> [Peter, Mary, Paul]

jshell> /exit

$ jshell -q

jshell> Set.of("Peter", "Paul", "Mary")

$1 ==> [Paul, Mary, Peter]
```

一些 Java 程序员编写的程序依赖于“实现细节永远不会改变”的假设。这会让库的实现者非常难做出有效的实现更改。在这种情况下，信息很明确——不要编写假设元素顺序固定的程序。

`List`和`Set`接口有十一个具有零到十个参数的`of`方法，以及一个具有变长参数的`of`方法。提供这些特化是为了效率。

对于`Map`接口，无法提供变长参数的版本，因为参数类型在键和值类型之间交替。有一个静态方法`ofEntries`接受任意数量的`Map.Entry<K, V>`对象，你可以使用静态`entry`方法创建它们。例如：

```java
import static java.util.Map.*;

. . .

Map<String, Integer> scores = ofEntries(
    entry("Peter", 2),
    entry("Paul", 3),
    entry("Mary", 5));
```

`of`和`ofEntries`方法产生的对象，其类为每个元素拥有一个实例变量，或者由数组支持。

这些集合对象是**不可修改的**（`unmodifiable`）。任何尝试更改其内容的操作都会导致`UnsupportedOperationException`。

如果你需要一个可变的集合，可以将不可修改的集合传递给构造函数：

```java
var names = new ArrayList<>(List.of("Peter", "Paul", "Mary")); // 一个可变的名称列表
```

该方法调用：

```java
Collections.nCopies(n, anObject)
```

返回一个实现了`List`接口的不可变对象，并给出具有`n`个元素的幻象，每个元素看起来都是`anObject`。

例如，以下调用创建了一个包含 100 个字符串的`List`，它们都被设置为`"DEFAULT"`：

```java
List<String> settings = Collections.nCopies(100, "DEFAULT");
```

存储成本非常低——该对象只存储一次。

![Image](img/note.jpg) **注意：**

`of`方法是在 Java 9 中引入的。在此之前，有一个静态的`Arrays.asList`方法，它返回一个可变但不可调整大小的列表。也就是说，你可以在列表上调用`set`但不能调用`add`或`remove`。还有遗留方法`Collections.emptySet`和`Collections.singleton`。

![Image](img/note.jpg) **注意：**

`Collections`类包含许多工具方法，其参数或返回值是集合。不要将其与`Collection`接口混淆。

![Image](img/tip.jpg) **提示：**

Java 没有内置`Pair`类，某些程序员使用`Map.Entry`作为廉价的对（poor man’s pair）。在 Java 9 之前，这非常痛苦——你必须手动构造一个`new AbstractMap.SimpleImmutableEntry<>(first, second)`。现在，你可以调用`Map.entry(first, second)`。

### 9.5.2 不可修改的拷贝和视图

要创建集合的**不可修改拷贝**，请使用该集合类型的`copyOf`方法：

```java
ArrayList<String> names = . . .;

Set<String> nameSet = Set.copyOf(names); // 作为不可修改集合的名称

List<String> nameList = List.copyOf(names); // 作为不可修改列表的名称
```

每个`copyOf`方法都会创建集合的拷贝。如果原始集合被修改，拷贝将不会受影响。

如果原始集合恰好是不可修改的且类型正确，那么`copyOf`只会直接返回它：

```java
Set<String> names = Set.of("Peter", "Paul", "Mary");

Set<String> nameSet = Set.copyOf(names); // 不需要拷贝：names == nameSet
```

`Collections`类具有可以产生集合的**不可修改视图**的方法。这些视图为现有集合添加了运行时检查。如果检测到尝试修改不可修改的集合，则会抛出异常。

然而，如果原始集合发生了变化，视图会反映这些变化。这正是视图不同于拷贝之处。

你可以通过八种方法获取不可修改视图：

```java
Collections.unmodifiableCollection

Collections.unmodifiableList
Collections.unmodifiableSet
Collections.unmodifiableSortedSet

Collections.unmodifiableNavigableSet

Collections.unmodifiableMap
Collections.unmodifiableSortedMap

Collections.unmodifiableNavigableMap
```

每个方法都定义为作用于接口。例如，`Collections.unmodifiableList`适用于`ArrayList`、`LinkedList`或任何实现`List`接口的类。

例如，假设你想让代码的某部分查看但不触碰集合的内容。你可以这样做：

```java
var staff = new LinkedList<String>();

. . .

lookAt(Collections.unmodifiableList(staff));
```

`Collections.unmodifiableList`方法返回一个实现`List`接口的类对象。它的访问器方法从`staff`集合中检索值。当然，`lookAt`方法可以调用`List`接口的所有方法，而不仅仅是访问器。但所有的变异器方法（如`add`）都已重新定义为抛出`UnsupportedOperationException`，而不是将调用转发给底层集合。

不可修改视图并不会让集合本身变为不可变。你仍然可以通过原始引用（在本例中为`staff`）修改集合。你仍然可以在集合的元素上调用变异器方法。

视图包装的是`接口`而不是实际集合对象，因此你只能访问接口中定义的方法。例如，`LinkedList`类有方便方法`addFirst`和`addLast`，它们并不是`List`接口的一部分。这些方法无法通过不可修改视图访问。

![Image](img/caution.jpg) **警告：**

`unmodifiableCollection`方法（以及本节稍后讨论的`synchronizedCollection`和`checkedCollection`方法）返回的集合，其`equals`方法*不会*调用底层集合的`equals`方法。相反，它继承了`Object`类的`equals`方法，该方法仅测试对象是否相同。如果你将集合或列表转换为普通集合，你无法再次测试内容是否相等。视图之所以这样做是因为在层次结构的这一级上，相等性测试没有良好的定义。视图对待`hashCode`方法的方式也是如此。

然而，`unmodifiableSet`和`unmodifiableList`方法使用了底层集合的`equals`方法。

### 9.5.3 范围

你可以为许多集合创建范围视图。例如，假设你有一个列表`staff`并想要提取 10 到 19 的元素。使用`subList`方法获取列表的视图：

```java
List<Employee> group2 = staff.subList(10, 20);
```

第一个索引是包含，第二个是排除的——就像`String`类的`substring`操作一样。

你可以对范围应用任何操作，它们会自动反映整个列表。例如，清除整个范围：

```java
group2.clear(); // staff
```

元素会自动从`staff`列表中清除，`group2`将为空。

对于排序集合和映射，使用排序而不是元素位置来形成范围。`SortedSet`接口声明了三个方法：

```java
SortedSet<E> subSet(E from, E to)

SortedSet<E> headSet(E to)

SortedSet<E> tailSet(E from)
```

这些方法返回大于等于`from`且严格小于`to`的子集。对于排序映射，类似的方法：

```java
SortedMap<K, V> subMap(K from, K to)

SortedMap<K, V> headMap(K to)

SortedMap<K, V> tailMap(K from)
```

返回映射视图。

Java 6 引入的`NavigableSet`接口对这些范围操作提供了更多控制。你可以指定边界是否包含：

```java
NavigableSet<E> subSet(E from, boolean fromInclusive, E to, boolean toInclusive)

NavigableSet<E> headSet(E to, boolean toInclusive)

NavigableSet<E> tailSet(E from, boolean fromInclusive)
```

### 9.5.4 检查视图

检查视图旨在为泛型可能出现的问题提供调试支持。正如第 8 章所述，实际上可以将错误类型的元素带入泛型集合中。例如：

```java
var strings = new ArrayList<String>();

ArrayList rawList = strings; // 仅警告，不是错误，
                             // 为了与遗留代码兼容

rawList.add(new Date()); // 现在 strings 包含了一个 Date 对象！
```

错误的`add`命令在运行时不会被检测到。相反，当代码的另一部分调用`get`并将结果转换为`String`时，会发生类类型转换异常。

检查视图可以检测此问题。按如下方式定义安全列表：

```java
List<String> safeStrings = Collections.checkedList(strings, String.class);
```



视图的 `add` 方法会检查插入的对象是否属于给定的类。如果不属于，它会立即抛出 `ClassCastException`。这种方法的优点是在正确的位置报告错误：

```java
ArrayList rawList = safeStrings;

rawList.add(new Date()); // checked list throws a ClassCastException
```

![Image](img/caution.jpg) **注意：**

检查视图（checked views）受限于虚拟机可以执行的运行时检查。例如，如果你有一个 `ArrayList<Pair<String>>`，你无法防止它插入 `Pair<Date>`，因为虚拟机只有一个“原始” `Pair` 类。

### 9.5.5 同步视图

如果你从多个线程访问集合，你需要确保集合不会无意中损坏。例如，如果一个线程试图向哈希表中添加元素，而另一个线程正在对元素进行重新哈希，结果将是灾难性的。

库的设计者并没有实现线程安全的集合类，而是使用视图机制使普通集合变得线程安全。例如，`Collections` 类中的静态方法 `synchronizedMap` 可以将任何 map 转换为具有同步访问方法的 `Map`：

```java
var map = Collections.synchronizedMap(new HashMap<String, Employee>());
```

你现在可以从多个线程访问 `map` 对象了。`get` 和 `put` 等方法是同步的——每个方法调用在完全完成之前，另一个线程无法调用另一个方法。我们将在第 12 章中详细地讨论数据结构的同步访问问题。

### 9.5.6 关于可选操作的说明

视图通常有一些限制——它可能是只读的，可能无法更改大小，或者可能支持删除但不插入（如 map 的键视图）。如果你尝试执行不适当的操作，受限视图会抛出 `UnsupportedOperationException`。

在集合和迭代器接口的 API 文档中，许多方法被描述为“可选操作（optional operations）”。这似乎与接口的概念相冲突。毕竟，接口的目的不就是为了列出类*必须*实现的方法吗？确实，从理论角度来看，这种安排是不令人满意的。更好的解决方案可能是为只读视图和无法更改集合大小的视图设计单独的接口。然而，这将接口的数量增加三倍，库的设计者认为这是不可接受的。

你是否应该将“可选”方法的技术扩展到你自己的设计中？我认为不应该。尽管集合被频繁使用，但实现它们的编码风格在其他问题领域并不典型。集合类库的设计者必须解决一组特别严酷的冲突需求。用户希望库易于学习、方便使用、完全泛型、防呆（idiot-proof），并且与手编写的算法一样高效。要同时实现所有目标显然是不可能的，甚至无法接近。但在你自己的编程问题中，很少会遇到如此极端的约束。你应该找到不依赖于“可选”接口操作这种极端手段的解决方案。

#### `java.util.List` 1.2

- `static <E> List<E> of()` 9
- `static <E> List<E> of(E e1)` 9
- `. . .`
- `static <E> List<E> of(E e1, E e2, E e3, E e4, E e5, E e6, E e7, E e8, E e9, E e10)` 9
- `static <E> List<E> of(E... elements)` 9 返回一个给定元素的不可修改列表，这些元素不能为 `null`。
- `static <E> List<E> copyOf(Collection<? extends E> coll)` 10 返回给定集合的不可修改副本。

#### `java.util.Set` 1.2

- `static <E> Set<E> of()` 9
- `static <E> Set<E> of(E e1)` 9
- `. . .`
- `static <E> Set<E> of(E e1, E e2, E e3, E e4, E e5, E e6, E e7, E e8, E e9, E e10)` 9
- `static <E> Set<E> of(E... elements)` 9 返回一个给定元素的不可修改集合，这些元素不能为 `null`。
- `static <E> Set<E> copyOf(Collection<? extends E> coll)` 10 返回给定集合的不可修改副本。

#### `java.util.Map` 1.2

- `static <K, V> Map<K, V> of()` 9
- `static <K, V> Map<K, V> of(K k1, V v1)` 9
- `. . .`
- `static <K,V> Map<K,V> of(K k1, V v1, K k2, V v2, K k3, V v3, K k4, V v4, K k5, V v5, K k6, V v6, K k7, V v7, K k8, V v8, K k9, V v9)` 9
- `static <K, V> Map<K, V> copyOf(Collection<? extends E> coll)` 10 返回给定集合的不可修改副本。

- `static <T> ListIterator<T> emptyListIterator()`

返回一个空的集合、映射或迭代器。

`java.util.Arrays` 1.2

- `static <E> List<E> asList(E... array)`

返回数组元素的列表视图，该视图是可修改的但不可调整大小。

`java.util.List<E>` 1.2

- `List<E> subList(int firstIncluded, int firstExcluded)`

返回一个位置范围内元素的列表视图。

`java.util.SortedSet<E>` 1.2

- `SortedSet<E> subSet(E firstIncluded, E firstExcluded)`
- `SortedSet<E> headSet(E firstExcluded)`
- `SortedSet<E> tailSet(E firstIncluded)`

返回一个范围内元素的视图。

`java.util.NavigableSet<E>` 6

- `NavigableSet<E> subSet(E from, boolean fromIncluded, E to, boolean toIncluded)`
- `NavigableSet<E> headSet(E to, boolean toIncluded)`
- `NavigableSet<E> tailSet(E from, boolean fromIncluded)`

返回一个范围内元素的视图。`boolean` 标志决定边界是否包含在视图中。

`java.util.SortedMap<K, V>` 1.2

- `SortedMap<K, V> subMap(K firstIncluded, K firstExcluded)`
- `SortedMap<K, V> headMap(K firstExcluded)`
- `SortedMap<K, V> tailMap(K firstIncluded)`

返回一个键在范围内的条目映射视图。

`java.util.NavigableMap<K, V>` 6

- `NavigableMap<K, V> subMap(K from, boolean fromIncluded, K to, boolean toIncluded)`
- `NavigableMap<K, V> headMap(K from, boolean fromIncluded)`
- `NavigableMap<K, V> tailMap(K to, boolean toIncluded)`

返回一个键在范围内的条目映射视图。`boolean` 标志决定边界是否包含在视图中。

### 9.6 算法

除了实现集合类，Java 集合框架还提供了许多有用的算法。在接下来的章节中，你将看到如何使用这些算法，以及如何编写与集合框架良好协作的自定义算法。

#### 9.6.1 为什么用泛型算法？

泛型集合接口有一个巨大的优势——你只需要实现一次你的算法。例如，考虑一个计算集合中最大元素的简单算法。传统上，程序员会用循环来实现这种算法。这里是你可以找到数组中最大元素的方法：

```java
if (a.length == 0) throw new NoSuchElementException();

T largest = a[0];

for (int i = 1; i < a.length; i++)
    if (largest.compareTo(a[i]) < 0)
        largest = a[i];
```

当然，要找到数组列表（`ArrayList`）中的最大值，写的代码会略有不同。

```java
if (v.size() == 0) throw new NoSuchElementException();

T largest = v.get(0);

for (int i = 1; i < v.size(); i++)
    if (largest.compareTo(v.get(i)) < 0)
        largest = v.get(i);
```

链表（Linked list）呢？在链表中无法进行高效的随机访问，但你可以使用迭代器。

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

这些循环写起来非常繁琐，而且容易出错。是否存在差一错误（off-by-one error）？循环对于空容器是否工作正常？对于只有一个元素的容器又如何？你不想每次都去测试和调试这些代码，但你也不想实现一大堆方法，例如：

```java
static <T extends Comparable> T max(T[] a)

static <T extends Comparable> T max(ArrayList<T> v)

static <T extends Comparable> T max(LinkedList<T> l)
```

这正是集合接口用武之地。考虑高效执行该算法所需的*最小*集合接口。使用 `get` 和 `set` 进行随机访问在食物链上高于简单的迭代。正如你在计算链表中最大元素时看到的，这项任务并不需要随机访问。计算最大值可以通过简单的遍历元素完成。因此，你可以实现 `max` 方法，使其接收*任何*实现了 `Collection` 接口的对象。

```java
public static <T extends Comparable> T max(Collection<T> c)
{
    if (c.isEmpty()) throw new NoSuchElementException();

    Iterator<T> iter = c.iterator();

    T largest = iter.next();

    while (iter.hasNext())
    {
        T next = iter.next();

        if (largest.compareTo(next) < 0)
            largest = next;
    }

    return largest;
}
```

现在，你可以用一个方法计算链表、数组列表或数组的最大值。

这是一个强大的概念。事实上，标准 C++ 库有很多种有用的算法，每种算法都作用在泛型集合上。Java 库并没有那么丰富，但它包含了基础功能：排序、二分查找和一些工具算法。

#### 9.6.2 排序与洗牌

计算机老兵们有时会回忆起他们如何使用打孔卡……如今，排序算法是大多数语言标准库的一部分，Java 编程语言也不例外。

`Collections.sort` 方法对实现了 `List` 的集合进行排序。

```java
var staff = new LinkedList<String>();

Collections.sort(staff);
```

该方法假设列表元素实现了 `Comparable` 接口。如果你想以其他方式排序列表，可以使用 `List` 接口的 `sort` 方法并传递一个 `Comparator` 对象。这里是如何按薪资对员工列表进行排序：

```java
staff.sort(Comparator.comparingDouble(Employee::getSalary));
```

如果你想按*降序*顺序排序列表，使用静态便利方法 `Comparator.reverseOrder()`。它返回一个返回 `b.compareTo(a)` 的比较器。例如：

```java
staff.sort(Comparator.reverseOrder());
```

同样地：

```java
staff.sort(Comparator.comparingDouble(Employee::getSalary).reversed());
```

你可能会好奇 `sort` 方法是如何对列表排序的。通常，当你从算法书中查看排序算法时，它是针对数组演示的并使用随机元素访问。然而，链表中的随机访问是低效的。实际上，你可以使用归并排序的一种形式高效地排序链表。然而，Java 语言中的实现并没有这样做。它只是简单将所有元素转到数组中，对数组排序，然后将排序后的序列复制回列表。

`Collections` 类有一个名为 `shuffle` 的算法，它的作用与排序相反——它会随机打乱列表中元素的顺序。例如：

```java
ArrayList<Card> cards = . . .;

Collections.shuffle(cards);
```

如果你提供一个没有实现 `RandomAccess` 接口的列表，`shuffle` 方法会将元素复制到数组中，对数组进行洗牌，然后将洗牌后的元素复制回列表。

Listing 9.7 中的程序向数组列表填充了 49 个包含数字 1 到 49 的 `Integer` 对象。然后它随机打乱列表，并从打乱后的列表中选取前六值。最后，它对选定的值进行排序并打印出来。

**Listing 9.7** `shuffle/ShuffleTest.java`

```java
1  package shuffle;

2

3  import java.util.*;

4

5  /**
6    * 此程序演示了随机洗牌和排序算法。
7    * @version 1.12 2018-04-10
8    * @author Cay Horstmann
9    */
10 public class ShuffleTest
11 {
12     public static void main(String[] args)
13     {
14         var numbers = new ArrayList<Integer>();
15         for (int i = 1; i <= 49; i++)
16             numbers.add(i);
17         Collections.shuffle(numbers);
18         List<Integer> winningCombination = numbers.subList(0, 6);
19         Collections.sort(winningCombination);
20         System.out.println(winningCombination);
21     }
22 }
```



## `java.util.Collections`（1.2）

- `static <T extends Comparable<? super T>> void sort(List<T> elements)`

  使用稳定的排序算法对列表中的元素排序。该算法保证在 `O(n log n)` 时间内运行，其中 `n` 是列表的长度。

- `static void shuffle(List<?> elements)`
- `static void shuffle(List<?> elements, Random r)`

  随机打乱列表中的元素。该算法在 `O(n a(n))` 时间内运行，其中 `n` 是列表的长度，`a(n)` 是访问元素的平均时间。

## `java.util.List<E>`（1.2）

- `default void sort(Comparator<? super T> comparator)`（8）

  使用给定的比较器对此列表排序。

## `java.util.Comparator<T>`（1.2）

- `static <T extends Comparable<? super T>> Comparator<T> reverseOrder()`（8）

  产生一个反转 `Comparable` 接口提供的排序的比较器。

- `default Comparator<T> reversed()`（8）

  产生一个反转此比较器提供的排序的比较器。

### 9.6.3 二分查找

要在数组中查找对象，通常需要遍历所有元素直到找到匹配项。然而，如果数组是排序过的，你可以查看中间元素并检查它是否大于你要查找的元素。如果是，继续在数组的前半部分查找；否则，在后半部分查找。这会将问题减半，你以这样继续下去。例如，如果数组有 1024 个元素，你将在 10 步后找到匹配项（或确认不存在），而线性搜索在元素存在时平均需要 512 步，不存在时需要 1024 步来确认其不存在。

`Collections` 类的 `binarySearch` 实现了这种算法。注意，集合必须已经是排序的，否则算法将返回错误答案。要查找一个元素，请提供集合（必须实现 `List` 接口——更多信息请见下文注释）和要定位的元素。如果集合不是通过 `Comparable` 接口的 `compareTo` 元素排序的，请也提供一个比较器对象。

```java
i = Collections.binarySearch(c, element);

i = Collections.binarySearch(c, element, comparator);
```

`binarySearch` 方法的非负返回值表示匹配对象的索引。也就是说，在比较顺序下，`c.get(i)` 等于 `element`。如果值为负数，则没有匹配的元素。然而，你可以使用返回值来计算应该将 `element` 插入到集合中的位置以保持其排序。插入位置是：

```java
insertionPoint = -i - 1;
```

它不仅仅是 `-i`，因为值 `0` 将会产生歧义。换句话说，操作

```java
if (i < 0)
    c.add(-i - 1, element);
```

会将元素添加到正确的位置。

为了使二分查找有意义，它需要随机访问。如果你必须逐个遍历链表的一半来找到中间元素，那么你就失去了二分查找的所有优势。因此，如果你给它链表，`binarySearch` 算法将退化为线性搜索。

#### `java.util.Collections`（1.2）

- `static <T extends Comparable<? super T>> int binarySearch(List<T> elements, T key)`
- `static <T> int binarySearch(List<T> elements, T key, Comparator<? super T> c)`

  在排序的列表中查找 `key`，如果元素实现了 `RandomAccess`。这些方法在 `O(n log n)` 时间内运行，其中 `n` 是列表的长度，`a(n)` 是访问元素的平均时间。方法返回 `key` 的索引或负值 `-i - 1` 以保持列表排序。

### 9.6.4 简单算法

`Collections` 类包含几个简单算法。其中包括查找最大值。其他的包括从一个列表复制到另一个、填充常量值以及反转列表。

为什么要在标准库中提供这些简单算法？程序员完全可以用简单的循环实现它们。当你阅读别人实现的循环时，你必须理解其意图。例如，看这个循环：

```java
for (int i = 0; i < words.size(); i++)
    if (words.get(i).equals("C++")) words.set(i, "Java");
```

现在将循环与调用对比：

```java
Collections.replaceAll(words, "C++", "Java");
```

当你看到方法调用时，立刻就知道代码在做什么。

本部分的 API 注释说明了 `Collections` 类的简单算法。默认方法 `Collection.removeIf` 和 `List.replaceAll` 稍微复杂。你提供 lambda 表达式来测试或转换元素。例如，这里我们移除短单词并将剩余单词转换为小写：

```java
words.removeIf(w -> w.length() <= 3);

words.replaceAll(String::toLowerCase);
```

#### `java.util.Collections`（1.2）

- `static <T extends Comparable<? super T>> T min(Collection<T> elements)`
- `static <T extends Comparable<? super T>> T max(Collection<T> elements)`
- `static <T> T min(Collection<T> elements, Comparator<? super T> c)`
- `static <T> T max(Collection<T> elements, Comparator<? super T> c)`

  返回集合中最小或最大的元素。（参数边界为了清晰起见进行了简化。）

- `static <T> void copy(List<? super T> to, List<T> from)`

  将源列表的所有元素复制到目标列表相同的位置。目标列表必须与源列表一样长。

- `static <T> void fill(List<? super T> l, T value)`

  将列表的位置设置为相同的值。

- `static <T> boolean addAll(Collection<? super T> c, T... values)`

  将所有值添加到给定的集合，如果集合因此发生了变化，则返回 `true`。

- `static <T> boolean replaceAll(List<T> l, T oldValue, T newValue)`

  替换所有等于 `oldValue` 的元素为 `newValue`。

- `static int indexOfSubList(List<?> l, List<?> s)`
- `static int lastIndexOfSubList(List<?> l, List<?> s)`

  返回 `l` 中第一个或最后一个等于 `s` 的子列表的索引；如果 `l` 中没有子列表等于 `s`，则返回 `-1`。例如，如果 `l` 为 `[s, t, a, r]` 且 `s` 为 `[t, a, r]`，则两种方法都返回索引 `1`。

- `static void swap(List<?> l, int i, int j)`（1.4）

  交换给定偏移量处的元素。

- `static void reverse(List<?> l)`

  反转列表中元素的排列顺序。例如，反转列表 `[t, a, r]` 会得到列表 `[r, a, t]`。该方法的运行时间复杂度为 `O(n)`（错误，应为时间复杂度为 `O(n)`），其中 `n` 是列表的长度。

- `static void rotate(List<?> l, int d)`（1.4）

  旋转列表中的元素，将索引为 `i` 的项移动到位置 `(i + d) % l.size()`。例如，将列表 `[t, a, r]` 旋转 2 位会得到列表 `[a, r, t]`。该方法的运行时间复杂度为 `O(n)`，其中 `n` 是列表的长度。

- `static int frequency(Collection<?> c, Object o)`（5）

  返回 `c` 中等于对象 `o` 的元素计数。

- `boolean disjoint(Collection<?> c1, Collection<?> c2)`（5）

  如果两个集合没有共同的元素，则返回 `true`。

### `java.util.Collection<T>`（1.2）

- `default boolean removeIf(Predicate<? super E> filter)`（8）

  移除所有匹配的元素。

### `java.util.List<E>`（1.2）

- `default void replaceAll(UnaryOperator<E> op)`（8）

  将该操作应用于此列表中的所有元素。

### 9.6.5 批量操作

有几种操作可以“批量”复制或删除元素。调用

```java
coll1.removeAll(coll2);
```

会从 `coll1` 中移除所有存在于 `coll2` 中的元素。相反，

```java
coll1.retainAll(coll2);
```

会从 `coll1` 中移除所有不在 `coll2` 中的元素。这是一个典型的应用。

假设你想找到两个集合的交集——即两个集合共同元素。首先，创建一个新集合来存放结果。

```java
var result = new HashSet<String>(firstSet);
```

在这里，我们利用了每个集合都有一个构造函数的特性，其参数是另一个持有初始化值的集合。

现在，使用 `retainAll` 方法：

```java
result.retainAll(secondSet);
```

它保留了在两个集合中都出现的所有元素。你可以在没有编写循环的情况下形成交集。

你可以进一步扩展这个想法，并将批量操作应用于视图。例如，假设你有一个将员工 ID 映射到员工对象的映射，并且有一组所有要终止合同的员工的 ID。

```java
Map<String, Employee> staffMap = . . .;

Set<String> terminatedIDs = . . .;
```

只需形成键集并移除所有已终止员工的 ID。

```java
staffMap.keySet().removeAll(terminatedIDs);
```

由于键集是映射的视图，键和关联的员工名称会自动从映射中移除。

通过使用子范围视图，你可以将批量操作限制在子列表和子集中。例如，假设你想将列表的前十个元素添加到另一个容器中。形成一个子列表来选取前十个：

```java
relocated.addAll(staff.subList(0, 10));
```

子范围也可以作为变动操作的目标。

```java
staff.subList(0, 10).clear();
```

### 9.6.6 集合与数组之间的转换

Java 平台 API 的大部分内容是在集合框架创建之前设计的。因此，你偶尔需要在传统的数组和更现代的集合之间进行转换。

如果你有一个需要转换为集合的数组，`List.of` 方法可以恰好实现此目的。例如：

```java
String[] names = . . .;

List<String> staff = List.of(names);
```

从集合获取数组要稍微复杂一些。你可以使用 `toArray` 方法：

```java
Object[] names = staff.toArray();
```

但结果是一个对象的数组。即使你知道你的集合包含特定类型的对象，你不能使用强制转换：

```java
String[] names = (String[]) staff.toArray(); //
```

`toArray` 方法返回的数组是作为 `Object[]` 数组创建的，你不能更改它的类型。相反，将数组构造表达式传递给 `toArray` 方法。返回的数组将作为正确的数组类型创建：

```java
String[] values = staff.toArray(String[]::new);
```

![Image](img/note.jpg) **注意：**

在 JDK 11 之前，你必须使用 `toArray` 方法的另一种形式，传递正确类型的数组：

```java
String[] values = staff.toArray(new String[0]);
```

此 `toArray` 方法构造另一个相同类型的数组。或者，如果数组长度足够，则会重用它：

```java
staff.toArray(new String[staff.size()]);
```

在这种情况下，没有创建新数组。

### 9.6.7 编写你自己的算法

如果你编写自己的算法（或者，实际上是任何以集合作为参数的方法），你应该尽可能与接口工作，而不是具体的实现。例如，假设你想处理项。当然，你可以实现这样一个方法：

```java
public void processItems(ArrayList<Item> items)
{
   for (Item item : items)
      do something with item
}
```

然而，你现在限制了你方法的调用者——调用者必须以 `ArrayList` 提供项。如果这些项恰好在另一个集合中，它们首先需要重新包装。接受更通用的集合要好得多。

你应该问自己这个问题：能够完成工作的最通用的集合接口是什么？你在意顺序吗？那么你应该接受一个 `List`。但如果顺序不重要，你可以接受任何种类的集合：

```java
public void processItems(Collection<Item> items)
{
   for (Item item : items)
      do something with item
}
```

现在，任何人都可以使用 `ArrayList` 或 `LinkedList` 调用此方法，甚至可以使用包装在 `List.of` 方法中的数组。

![Image](img/tip.jpg) **提示：**

在这种情况下，通过接受 `Iterable<Item>` 可以做得更好。`Iterable` 接口有一个抽象方法 `iterator`，增强 `for` 循环在底层使用它。`Collection` 接口扩展 `Iterable`。相反，如果你的方法返回多个元素，你不想限制自己改进。例如，考虑：

```java
public ArrayList<Item> lookupItems(. . .)
{
   var result = new ArrayList<Item>();
   . . .
   return result;
}
```

此方法承诺返回 `ArrayList`，尽管调用者几乎不在乎它是哪种列表。如果改为返回 `List`，你随时可以添加一个返回空列表或单例列表的分支。

## 9.7 遗留集合

许多“遗留”容器类自 Java 第一版以来一直存在，当时还没有集合框架。

它们已经集成到集合框架中——参见图 9.12。我将在下面的章节中简要介绍它们。

![Images](img/09fig12.jpg)

**图 9.12** 集合框架中的遗留

### 9.7.1 `Hashtable` 类

### 9.7.2 枚举

旧集合（legacy collections）使用 `Enumeration` 接口来遍历元素序列。`Enumeration` 接口有两个方法：`hasMoreElements` 和 `nextElement`。这些与 `Iterator` 接口的 `hasNext` 和 `next` 方法完全对应。

如果你在旧版类中发现此接口，可以使用 `Collections.list` 将元素收集到 `ArrayList` 中。例如，`LogManager` 类只愿意以 `Enumeration` 的形式公开记录器名称。以下是获取所有这些名称的方法：

```java
ArrayList<String> loggerNames = Collections.list(LogManager.getLoggerNames());
```

或者，从 Java 9 开始，你可以将枚举转换为迭代器：

```java
LogManager.getLoggerNames().asIterator().forEachRemaining(n -> { . . . });
```

你偶尔会遇到一个期望枚举参数的旧版方法。静态方法 `Collections.enumeration` 会产生一个枚举对象，该对象遍历集合中的元素。例如：

```java
List<InputStream> streams = . . .;

var in = new SequenceInputStream(Collections.enumeration(streams));

// SequenceInputStream 构造函数期望一个枚举
```



![Image](img/note.jpg) **注意：**

在 C++ 中，将迭代器作为参数是非常常见的。幸运的是，在 Java 平台上，很少有程序员使用这种习惯。比起传递迭代器，传递集合要明智得多。集合对象更有用。接收者在需要时始终可以从集合中获取迭代器，而且他们可以使用所有的集合方法。然而，你会在某些旧代码中发现枚举，因为在 Java 1.2 集合框架出现之前，它们是泛型集合唯一的可用机制。

### `java.util.Enumeration<E>` **1.0**

- `boolean hasMoreElements()`
  如果还有更多待检查的元素，则返回 `true`。

- `E nextElement()`
  返回下一个待检查的元素。如果 `hasMoreElements()` 返回为 `false`，则不要调用此方法。

- `default Iterator<E> asIterator()` **9**
  产生一个遍历已枚举元素的迭代器。

### `java.util.Collections` **1.2**

- `static <T> Enumeration<T> enumeration(Collection<T> c)`
  返回一个枚举 `c` 中元素的枚举器。

- `public static <T> ArrayList<T> list(Enumeration<T> e)`
  返回一个包含由 `e` 枚举的元素的列表。

#### 9.7.3 属性映射 (Property Maps)

*属性映射*（property map）是一种特殊类型的映射结构。它有三个特征：

- 键和值都是字符串。
- 映射可以很容易地保存到文件并从文件中加载。
- 有一个用于默认值的辅助表。

实现属性映射的 Java 类称为 `Properties`。属性映射在指定程序的配置选项时有用。例如：

```
var settings = new Properties();
settings.setProperty("width", "600.0");
settings.setProperty("filename", "/home/cay/books/cj12/code/v1ch09/raven.html");
```

使用 `store` 方法将属性列表保存到文件中。在这里，我们仅将属性映射保存到 `program.properties` 文件中。第二个参数是包含在文件中的注释。

```
var out = new FileWriter("program.properties", StandardCharsets.UTF_8);
settings.store(out, "Program Properties");
```

示例集给出以下输出：

```
#Program Properties
#Sun Dec 31 12:54:19 PST 2017
top=227.0
left=1286.0
width=423.0
height=547.0
filename=/home/cay/books/cj12/code/v1ch09/raven.html
```

要从文件加载属性，请使用：

```
var in = new FileReader("program.properties", StandardCharsets.UTF_8);
settings.load(in);
```

![Image](img/caution.jpg) **注意：**

如果你对输入输出流使用 `load` 和 `store` 方法，将使用过时的 ISO 8859–1 字符编码，且大于 U+00FF 的字符将被保存为 Unicode 转义序列。对于 UTF-8，请像上面的代码段一样使用读取/写入器。

`System.getProperties` 方法产生一个描述系统信息的 `Properties` 对象。例如，主目录具有键 `"user.home"`。你可以通过返回键为字符串的 `getProperties` 方法读取它：

```
String userDir = System.getProperty("user.home");
```

![Image](img/caution.jpg) **注意：**

出于历史原因，`Properties` 类实现了 `Map<Object, Object>`。因此，你可以使用 `Map` 接口的 `get` 和 `put` 方法。但 `get` 方法返回类型 `Object`，而 `put` 方法允许你插入任何对象。最好坚持使用处理字符串而非对象的 `getProperty` 和 `setProperty` 方法。

要获取虚拟机的 Java 版本，请查找 `"java.version"` 属性。你将得到一个类似于 `"17.0.1"` 的字符串（对于 Java 8 直到 `"1.8.0"`）。

![Image](img/tip.jpg) **提示：**

如你所见，从 Java 9 开始，枚举可以可以转换为迭代器。这一微小的变化破坏了许多依赖旧格式的工具。

`Properties` 类有两种提供默认值的机制。首先，每当你通过 `getProperty` 查找值时，都可以指定一个默认值。

```java
String filename = settings.getProperty("filename", "");
```

如果属性映射中有 `"filename"` 属性，则 `filename` 设置为该字符串；否则，设置为空字符串。

如果你觉得在每次调用 `getProperty` 时指定默认值太麻烦了，可以将所有默认值封装在一个属性映射中并在构造函数中提供该映射。

```
var defaultSettings = new Properties();
defaultSettings.setProperty("width", "600");
defaultSettings.setProperty("height", "400");
defaultSettings.setProperty("filename", "");
. . .
var settings = new Properties(defaultSettings);
```

是的，你可以通过给 `defaultSettings` 另一个属性映射来指定默认值，但这通常这样做。

配套代码有一个示例程序展示了如何使用属性存储和加载程序状态。该程序使用了第二章中的 `ImageViewer` 程序，并记得框架的位置、大小和最后加载的文件。运行程序，加载文件并调整窗口。然后关闭程序并重新打开，查看它是否记得你的文件和位置。你也可以手动编辑主目录下的 `.corejava/ImageViewer.properties` 文件。

`Properties` 是没有分级结构的简单表。通常使用如 `window.main.color`、`window.main.title` 等键名引入伪分级结构。但 `Properties` 类没有帮助组织此类分级的方法。如果你存储复杂的配置信息，应该使用 `Preferences` 类——参见第十章。

**`java.util.Properties`** **1.0**

- `Properties()`
  创建一个空的属性映射。

- `Properties(Properties defaults)`
  创建一个带有默认映射的空属性映射。

- `String getProperty(String key)`
  获取属性。返回与键关联的字符串；如果表中不存在该键，则返回默认表中与键关联的字符串；如果默认表中也没有该键，则返回 `null`。

- `String getProperty(String key, String defaultValue)`
  在键未找到时带默认值获取属性。返回与键关联的字符串；如果表中不存在该键，则返回默认字符串。

- `Object setProperty(String key, String value)`
  设置一个属性。返回给定键之前先设置的值。

- `Set<String> stringPropertyNames()` 6
  返回所有键的集合，包括默认 map 中的键。

- `void load(Reader in) throws IOException` 6
  从读取器加载属性映射。

- `void store(Writer out, String header)` 6
  将属性映射保存到写入器。头部位于存储文件的第一行。

### `java.lang.System` 1.0

- `Properties getProperties()`
  检索所有系统属性。应用程序必须具有检索所有属性的权限，否则将抛出安全异常。

- `String getProperty(String key)`
  根据指定的键名检索系统属性。应用程序必须具有检索该属性的权限，否则将抛出安全异常。以下属性可以始终被检索：

```
java.version
java.vendor
java.vendor.url
java.home
java.class.path
java.library.path
java.class.version
os.name
os.version
os.arch
file.separator
path.separator
line.separator
java.io.tempdir
user.name
user.home
user.dir
java.compiler
java.specification.version
java.specification.vendor
java.specification.name
java.vm.version
java.vm.vendor
java.vm.name
java.version
java.vendor
java.name)
```

### 9.7.4 Stacks（栈）

从 1.0 版本开始，标准库就有一个带有 `push` 和 `pop` 方法的 `Stack` 类。然而，`Stack` 类继承了 `Vector`，这从理论角度来看并不够理想——你可以应用类似栈的操作 `insert` 和 `remove` 在栈的任何位置进行插入和删除，而不仅仅是栈顶。

### `java.util.Stack<E>` 1.0

- `E push(E item)`
  将 `item` 推入栈并返回 `item`。

- `E pop()`
  弹出并返回栈顶的元素。如果栈为空，不要调用此方法。

- `E peek()`
  返回栈顶元素但不将其弹出。如果栈为空，不要调用此方法。

### 9.7.5 Bit Sets（位集）

Java 平台的 `BitSet` 类存储一个位序列（它在数学意义上不是 *set*，使用位 *vector* 或位 *array* 会更合适）。如果你需要高效地存储位序列（例如标志位），请使用位集。位集将位压缩到字节中，因此使用位集比使用 `Boolean` 对象的 `ArrayList` 高得多。`BitSet` 类提供了读取、设置和重置位的方便接口，避免了在 `int` 或 `long` 变量中存储位时所需的掩码和其他位操作。

例如，对于一个名为 `bucketOfBits` 的 `BitSet`：

```
bucketOfBits.get(i)
```

如果第 i 位开启，则返回 `true`，否则返回 `false`。同样，

```
bucketOfBits.set(i)
```

开启第 i 位。最后，

```
bucketOfBits.clear(i)
```

关闭第 i 位。

**注意：** C++ 的 `bitset` 模板具有与 Java `BitSet` 相同的功能。

### 9.7 Legacy Collections（遗留集合）

### `java.util.BitSet` 1.0

- `BitSet(int initialCapacity)`
  构造一个位集。

- `int cardinality()` 4
  返回开启的位数，或者视为整数集合时，返回元素的数量。

- `int length()` 1.2
  返回“逻辑长度”（1 加位的索引）。这对于遍历元素很有用。

- `int size()`
  返回内部结构中可用的位数，*而不是*元素的数量。

- `boolean get(int bit)`
  获取一个位。

- `void set(int bit)`
  设置一位。

- `void clear(int bit)`
  清除一个位。

- `void and(BitSet set)`
  此位集与另一个位集进行 AND 运算。

- `void or(BitSet set)`
  此位集与另一个位集进行 OR 运算。

- `void xor(BitSet set)`
  此位集与另一个位集进行 XOR 运算。

- `void andNot(BitSet set)`
  清除此位集中在另一个位集中被开启的所有位。

- `IntStream stream()` 8
  产生开启位的索引流，或者视为整数集合时，产生元素的流。

作为位集使用的示例，我想向你展示一个寻找素数的“埃拉托尼筛法”实现（素数是指像 2、3 或 5 这样只能被自身和 1 整除的数字，筛法是枚举这些数字的方法之一）。这不是并不是很好的算法，但由于某种原因，它变成了流行的编译器性能基准（因为它主要测试位操作）。

好吧，我遵循传统并提供一个实现。该程序计算 2 到 2,000,000 之间的所有素数（在这个范围内有 148,933 个素数，所以你可能不想全部打印出来）。

不涉及过多细节，程序的想法是遍历一个具有 200 万位的位集。首先，我们开启所有位。之后，关闭已知素数的倍数。处理后剩余位的位置就是素数。列表 9.8 用 Java 语言列出了该程序，列表 9.9 是 C++ 代码。

**注意：** 尽管筛法不是很好的基准，但我无法抑制对这两种实现进行计时。以下是在使用 Intel i5–8265U 处理器和 16 GB RAM、运行 Ubuntu 20.04 时的计时结果：

- C++ (g++ 9.3.0): 115 毫秒
- Java (Java 17): 31 毫秒

我已经对《Core Java》进行了十一版本的测试，在最后七版本中，Java 轻松击败 C++。公平地说，如果提高 C++ 编译器的优化级别，它以 14 毫秒击败 Java。只有当程序运行足够久以触发 Hotspot JIT 编译器时，Java 才能与之匹配。

**Listing 9.8** `sieve/Sieve.java`

```java
package sieve;

import java.util.*;

/**
 * 此程序运行埃拉托尼筛基准。它计算到 2,000,000 的素数。
 * @version 1.22 2021-06-17
 * @author Cay Horstmann
 */
public class Sieve
{
    public static void main(String[] s)
    {
        int n = 2000000;
        long start = System.currentTimeMillis();
        var bitSet = new BitSet(n + 1);
        int i;
        for (i = 2; i <= n; i++)
            bitSet.set(i);
        i = 2;
        while (i * i <= n)
        {
            if (bitSet.get(i))
            {
                int k = i * i;
                while (k <= n)
                {
                    bitSet.clear(k);
                    k += i;
                }
            }
            i++;
        }
        long end = System.currentTimeMillis();
        System.out.println(bitSet.cardinality() + " primes");
        System.out.println((end - start) + " milliseconds");
    }
}
```

```cpp
 1  /**
 2    * @version 1.22 2021-06-17
 3    * @author Cay Horstmann
 4    */
 5
 6  #include <bitset>
 7  #include <iostream>
 8  #include <ctime>
 9
10  using namespace std;
11
12  int main()
13  {
14      const int N = 2000000;
15      clock_t cstart = clock();
16
17      bitset<N + 1> b;
18      int i;
19      for (i = 2; i <= N; i++)
20          b.set(i);
21      i = 2;
22      while (i * i <= N)
23      {
24          if (b.test(i))
25          {
26              int k = i * i;
27              while (k <= N)
28              {
29                  b.reset(k);
30                  k += i;
31              }
32          }
```



```cpp
33          i++;

34      }

35

36      clock_t cend = clock();

37      double millis = 1000.0 * (cend - cstart) / CLOCKS_PER_SEC;

38

39      cout << b.count() << " primes\n" << millis << " milliseconds\n";

40

41      return 0;

42  }

```

这就是我们对 Java 集合框架的介绍。正如你所看到的，Java 库提供了多种集合类来满足你的编程需求。在下一章中，你将学习如何编写图形用户界面。

# 第 10 章 图形用户界面编程

本章：

- 10.1 Java 用户界面工具包的历史
- 10.2 显示帧
- 10.3 在组件中显示信息
- 10.4 事件处理
- 10.5 Preferences API

Java 诞生的时代，大多数计算机用户都在与具有图形用户界面（GUI）的桌面应用程序进行交互。如今，基于浏览器和移动应用程序已更为常见，但在某些情况下提供桌面应用程序是有用的。此外，许多老师和学生喜欢通过 GUI 学习 Java。在本章及接下来的章节中，我将使用 Swing 工具包讨论用户界面编程的基础。如果你对编写 GUI 程序不感兴趣，可以安全地跳过这两章。

## 10.1 Java 用户界面工具包的历史

当 Java 1.0 引入时，它包含了一个名为抽象窗口工具包（AWT）的类库，用于基础 GUI 编程。基础 AWT 库通过将用户界面元素的创建和行为委托给每个目标平台上的原生 GUI 工具包（Windows、Linux、Macintosh 等）来处理用户界面元素。例如，如果你使用原始的 AWT 在 Java 窗口上放置文本框，实际上是由底层的“对等体”（peer）文本框来处理文本输入的。生成的程序理论上可以运行在这些任何一个平台上，并具有目标平台的“外观和感觉”（look-and-feel）。

这种基于对等体的方法对于简单应用程序很好，但很快发现，要编写一个依赖原生用户界面元素的高质量可移植图形库是非常困难的。菜单、滚动条和文本字段等用户界面元素在不同平台上的行为可能会有细微差异。

## 10.2 显示帧

顶层窗口（即不包含在另一个窗口内的窗口）在 Java 中被称为帧（frame）。AWT 库有一个名为 `Frame` 的类用于这种顶层窗口。该类的 Swing 版本被称为 `JFrame`，并继承自 `Frame` 类。从 Java 7 update 6 开始，JavaFX 已经捆装在 JDK 和 JRE 中。然而，在本书编写期间，Oracle 已经宣布从版本 11 开始，JavaFX 将不再包含在 Java 中。由于这是一本关于 Java 核心语言和 API 的书，我将专注于使用 Swing 进行用户界面编程。

### 10.2.1 创建帧

在本节中，我们将回顾使用 Swing `JFrame` 的最常用方法。列表 10.1 列出了一个在屏幕上显示空帧的简单程序，如图 10.1 所示。

```java
package simpleFrame;

import java.awt.*;
import javax.swing.*;

/**
 * @version 1.34 2018-04-10
 * @author Cay Horstmann
 */
public class SimpleFrameTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            var frame = new SimpleFrame();
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

Swing 类位于 `javax.swing` 包中。包名 `java.x` 表示这是一个 Java 扩展包，而不是核心包。由于历史原因，Swing 被视为一种扩展。然而，自 1.2 版本以来，它存在于每一个 Java 实现中。

默认情况下，窗口的大小是非常无用的 0 × 0 像素。我们定义了一个子类 `SimpleFrame`，它的构造函数将大小设置为 300 × 200 像素。这是 `SimpleFrame` 和 `JFrame` 之间的唯一区别。

在 `SimpleFrameTest` 类的 `main` 方法中，我们构造了一个 `SimpleFrame` 对象并使其可见。

在每个 Swing 程序中我们需要处理两个技术问题。

首先，所有的 Swing 组件都必须从*事件分发线程*（event dispatch thread）进行配置，该线程是将鼠标点击和按键等事件传递给用户界面组件的控制线程。以下代码片段用于在事件分发线程中执行语句：

```java
EventQueue.invokeLater(() ->

{
    statements
});
```

![Image](img/note.jpg) **注意：**

你会看到许多 Swing 程序并没有在事件分发线程中初始化用户界面。过去在主线程中进行初始化是完全可以接受的。遗憾的是，随着 Swing 组件变得越来越复杂，JDK 开发者已经无法保证这种方法的安全性了。错误发生的概率极低，但你不想成为那少数遇到间歇性问题的幸运儿之一。最好做正确的事，即使代码看起来相当神秘。

接下来，我们定义了当用户关闭应用程序窗口时应该发生什么。对于这个程序，我们希望程序退出。为了选择这种行为，我们使用语句：

```java
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
```

在具有多个窗口的其他程序中，你不希望程序仅仅因为用户关闭了一个窗口就退出。默认情况下，当用户关闭窗口时，窗口会被隐藏，但程序不会终止。（如果程序在*最后一个*窗口变得不可见时就终止，可能会很不错，但并不是 Swing 的工作方式。）

仅仅构造窗口并自动显示它。窗口在生命周期初期是不可见的。这为程序员提供了在第一次显示窗口之前向窗口中添加组件的机会。要显示窗口，`main` 方法调用了窗口的 `setVisible` 方法。

在调度了初始化语句后，`main` 方法退出。请注意，退出 `main` 并不会终止程序——只是终止主线程。事件分发线程会保持程序运行，直到它通过关闭窗口或调用 `System.exit` 方法被终止。

运行中的程序如图 10.1 所示——这是一个真正无聊的顶层窗口。如图所示，标题栏和周围的装饰（如缩放角）是由操作系统绘制的，而不是由 Swing 库绘制。Swing 库绘制窗口内部的所有内容。在这个程序中，它只是用默认背景色填充了窗口。

### 10.2.2 窗口属性

`JFrame` 类本身只有几个方法可以更改窗口的外观。

将组件移动到新位置。如果组件不是顶级组件，则 `x` 和 `y` 坐标使用容器的坐标；如果组件是顶级的（例如 `JFrame`），则使用屏幕坐标。

- `void setBounds(int x, int y, int width, int height)` **1.1**
- 移动并调整此组件的大小。
- `Dimension getSize()` **1.1**
- `void setSize(Dimension d)` **1.1**

获取或设置此组件的 `size` 属性。

### `java.awt.Window` 1.0

- `void setLocationByPlatform(boolean b)` **5**

获取或设置 `locationByPlatform` 属性。如果在窗口显示之前设置该属性，平台将选择一个合适的位置。

### `java.awt.Frame` 1.0

- `boolean isResizable()`
- `void setResizable(boolean b)`

获取或设置 `resizable` 属性。当设置该属性时，用户可以调整框架的大小。

- `String getTitle()`
- `void setTitle(String s)`

获取或设置 `title` 属性，该属性决定框架标题栏中的文本。

- `Image getIconImage()`
- `void setIconImage(Image image)`

获取或设置 `iconImage` 属性，该属性决定框架的图标。窗口系统可能会将图标作为框架装饰的一部分或其他位置进行显示。

### `java.awt.Toolkit` 1.0

- `static Toolkit getDefaultToolkit()`

返回默认工具包。

- `Dimension getScreenSize()`

获取用户屏幕的大小。

### `javax.swing.ImageIcon` 1.2

- `ImageIcon(String filename)`

构造一个图像存储在文件中的图标。

- `Image getImage()`

获取此图标的图像。

## 10.3 在组件中显示信息

在本节中，我将向你展示如何在框架内部显示信息（参见图 10.3）。

你可以直接在框架上绘制消息字符串，但这并不认为是一种良好的编程习惯。在 Java 中，框架的设计初衷实际上是作为组件的容器，例如菜单栏和其他用户界面元素。你通常会在添加到框架的另一个组件上进行绘制。

![Images](img/10fig03.jpg)

**图 10.3** 显示信息的框架

`JFrame` 的结构出奇地复杂。请看图 10.4，它展示了 `JFrame` 的组成。如你所见，`JFrame` 中叠加了四个面板。根面板（root pane）、分面板（layered pane）和玻璃面板（glass pane）对我们没有意义；它们是组织菜单栏和内容面板以及实现外观和效果所必需的。Swing 程序员最关心的部分是内容面板（content pane）。你添加到框架的任何组件都会自动放入内容面板中：

```java
Component c = . . .;

frame.add(c); // 添加到内容面板
```

在我们的情况下，我们想要向框架添加一个单个组件，并在上面绘制消息。要在组件上绘制，你需要定义一个扩展 `JComponent` 的类，并在类中重写 `paintComponent` 方法。

`paintComponent` 方法接受一个 `Graphics` 类型的参数。`Graphics` 对象记录了绘制图像和文本的设置集合，例如你设置的字体或当前颜色。Java 中的所有绘制都必须通过 `Graphics` 对象。它具有绘制图案、图像和文本的方法。

以下是创建一个可以在其上绘制的组件的方法：

```java
class MyComponent extends JComponent

{
    public void paintComponent(Graphics g)
    {
      用于绘制的代码
    }
}
```

每当窗口需要重绘时，无论原因何在，事件处理器都会通知组件。这会导致所有组件的 `paintComponent` 方法被执行。

![Images](img/10fig04.jpg)

**图 10.4** `JFrame` 的内部结构

永远不要亲自调用 `paintComponent` 方法。每当应用程序的某个需要重绘时，它都会被自动调用，你不应该干预这个自动过程。

什么样的动作会触发这种自动响应？例如，当用户增大窗口大小，或最小化窗口后恢复窗口时，就会发生绘制。如果用户弹出一个覆盖了现有窗口的窗口，然后让被覆盖的窗口消失，那么被覆盖的窗口现在就损坏了，需要重新重绘。（图形系统不会保存下方的像素）。当然，当窗口第一次显示时，它需要处理指定如何以及在何处绘制初始元素的代码。

***

![Image](img/tip.jpg) **提示：**

如果你需要强制重绘屏幕，请调用 `repaint` 方法而不是 `paintComponent`。`repaint` 方法将导致所有组件调用 `paintComponent`，并传入一个配置良好的 `Graphics` 对象。

***

正如你在上面的代码片段中看到的，`paintComponent` 方法接受一个 `Graphics` 类型的参数。在 `Graphics` 对象上进行屏幕显示测量是以像素为单位的。(0, 0) 坐标表示你正在绘制的组件表面的左上角。`Graphics` 类有各种方法，显示文本被视为一种特殊类型。我们的 `paintComponent` 方法看起来如下：

```java
class MyComponent extends JComponent

{
    public void paintComponent(Graphics g)
    {
      g.drawString("Not a Hello, World program", MESSAGE_X, MESSAGE_Y);
    }
}
```

最后，组件应该告诉用户它有多大。重写 `PreferredSize` 方法并返回一个包含宽度和高度的 `Dimension` 对象：

```java
class MyComponent extends JComponent

{
    private final int DEFAULT_WIDTH = 300;
    private final int DEFAULT_HEIGHT = 200;

    public Dimension getPreferredSize()
    {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

当你向框架填充一个或多个组件，并简单地使用它们的大小时，调用 `pack` 方法而不是 `setSize`：

```java
class MyFrame extends JFrame

{
    public MyFrame()
    {
        add(new MyComponent());
        pack();
    }
}
```

列表 10.2 显示了完整的代码。

**列表 10.2** `HelloWorld.java`

```java
package HelloWorld;

import javax.swing.*;
import java.awt.*;

/**
 * @version 2018-04-10
 * @author Caymann
 */
public class HelloWorld {
    public static void main(String[] args) {
        EventQueue.invokeLater(() -> {
            var frame = new JFrame();
            frame.setTitle("HelloWorld");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 包含面板的框架。
 */
class HelloWorldFrame extends JFrame {
    public HelloWorldFrame() {
        add(new HelloWorldComponent());
        pack();
    }
}

/**
 * 显示消息的组件。
 */
class HelloWorldComponent extends JComponent {
    public static final int MESSAGE_X = 75;
    public static final int MESSAGE_Y = 100;

    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public void paintComponent(Graphics g) {
        g.drawString("Not a Hello, World program", MESSAGE_X, MESSAGE_Y);
    }

    public Dimension getPreferredSize() {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

将给定的组件添加到此框架的内容面板中并返回它。

### `java.awt.Component` 1.0

- `void repaint()`：导致组件“尽快”进行重绘。
- `Dimension getPreferredSize()`：用于重写的方法，用以返回此组件的首选尺寸。

### `javax.swing.JComponent` 1.2

- `void paintComponent(Graphics g)`：用于重写的方法，以描述你的组件需要如何绘制。

### `java.awt.Window` 1.0

- `void pack()`：调整此窗口的大小，并考虑其内部组件的首选尺寸。

#### 10.3.1 使用 2D 形状



从 Java 1.0 开始，`Graphics` 类已经拥有了绘制线、矩形、椭圆等的方法。但那些绘制操作非常有限。相反，我们将使用来自 `Java 2D` 库的形状类。

要使用此库，你需要获取 `Graphics2D` 类的对象。该类是 `Graphics` 类的子类。从 Java 1.2 开始，诸如 `paintComponent` 等方法会自动接收一个 `Graphics2D` 类对象。只需进行如下强制转换即可：

```java
public void paintComponent(Graphics g)
{
    Graphics2D g2 = (Graphics2D) g;
    . . .
}
```

Java 2D 库以面向对象的方式组织几何形状。特别是，有专门的类来表示线、矩形和椭圆：

```java
Line2D
Rectangle2D
Ellipse2D
```

这些类都实现了 `Shape` 接口。Java 2D 库支持更复杂的形状——弧、二次和三次贝塞尔曲线以及通用路径——这些我们在本章中不会讨论。

要绘制一个形状，你首先创建一个实现 `Shape` 接口类的对象，然后调用 `Graphics2D` 类的 `draw` 方法。例如：

```java
Rectangle2D rect = . . .
g2.draw(rect);
```

Java 2D 库使用浮点坐标而非整数来表示像素。内部计算使用单精度 `float` 数量进行。单精度已经足够了——毕竟，几何计算的最终目的是在屏幕或打印机上设置像素。只要任何舍入误差保持在一个像素以内，视觉结果就不会受到影响。

然而，对 `float` 值的操作对程序员来说有时是不方便的，因为 Java 固执地要求将 `double` 值转换为 `float` 值时进行强制转换。例如，考虑以下语句：

```java
float f = 1.2; // 错误--可能丢失精度
```

该语句无法编译，因为常量 `1.2` 的类型为 `double`，编译器担心精度的丢失。解决办法是在浮点常量后加上 `F` 后缀：

```java
float f = 1.2F; // OK
```

现在考虑这条语句：

```java
float f = r.getWidth(); // 错误
```

该语句同样无法编译，原因相同。`getWidth` 方法返回一个 `double`。这一次，解决办法是提供一个强制转换：

```java
float f = (float) r.getWidth(); // OK
```

这些后缀和强制转换有点麻烦人，因此 2D 库的设计者决定为每个形状类提供两个版本：一个带有 `float` 坐标供节约经费的程序员使用，另一个带有 `double` 坐标供懒惰的人使用。（在书中，我们属于后一个阵营，并尽可能使用 `double` 坐标。）

库的设计者采用了一种奇特的机制来封装这些选择。考虑 `Rectangle2D` 类。这是一个抽象类，有两个具体的子类，这两个子类也是静态内部类：

```java
Rectangle2D.Float
Rectangle2D.Double
```

图 10.5 显示了继承图。

![图像](img/10fig05.jpg)

**图 10.5** 2D 矩形类

忽略这两个具体类是静态内部类的事实是最好的——这只是为了避免使用像 `FloatRectangle2D` 和 `DoubleRectangle2D` 这样的名称。

当你构造一个 `Rectangle2D.Float` 时，你提供 `float` 坐标。对于 `Rectangle2D.Double`，你提供 `double` 坐标。

```java
Rectangle2D.Float rect = new Rectangle2D.Float(10, 10, 100, 50);
Rectangle2D.Double rect = new Rectangle2D.Double(10, 10, 100, 50);
```

Java 2D 库使用浮点坐标而非整数来表示像素。内部计算使用单精度 `float` 数量进行。单精度已经足够了——毕竟，几何计算的最终目的是在屏幕或打印机上设置像素。只要任何舍入误差保持在一个像素以内，视觉结果就不会受到影响。

然而，对 `float` 值的操作对程序员来说有时是不方便的，因为 Java 固执地要求将 `double` 值转换为 `float` 值时进行强制转换。例如，考虑以下语句：

```java
float f = 1.2; // 错误--可能丢失精度
```

该语句无法编译，因为常量 `1.2` 的类型为 `double`，编译器担心精度的丢失。解决办法是在浮点常量后加上 `F` 后缀：

```java
float f = 1.2F; // OK
```

现在考虑这条语句：

```java
float f = r.getWidth(); // 错误
```

该语句同样无法编译，原因相同。`getWidth` 方法返回一个 `double`。这一次，解决办法是提供一个强制转换：

```java
float f = (float) r.getWidth(); // OK
```

```java
package draw;

import java.awt.*;
import java.awt.geom.*;
import javax.swing.*;

/**
 * @version 1.34 2018-04-10
 * @author Cay Horstmann
 */
public class DrawTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
            var frame = new DrawFrame();
            frame.setTitle("DrawTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * A frame that contains a panel with drawings.
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
 * A component that displays rectangles and ellipses.
 */
class DrawComponent extends JComponent
{
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 400;

    public void paintComponent(Graphics g)
    {
        var g2 = (Graphics2D) g;

        // draw a rectangle
        double leftX = 100;
        double topY = 100;
        double width = 200;
        double height = 150;

        var rect = new Rectangle2D.Double(leftX, topY, width, height);
        g2.draw(rect);

        // draw the enclosed ellipse
        var ellipse = new Ellipse2D.Double();
        ellipse.setFrame(rect);
        g2.draw(ellipse);

        // draw a diagonal line
        g2.draw(new Line2D.Double(leftX, topY, leftX + width, topY + height));

        // draw a circle with the same center
        double centerX = rect.getCenterX();
        double centerY = rect.getCenterY();
        double radius = 150;
        var circle = new Ellipse2D.Double();
        circle.setFrame(centerX - radius, centerY - radius, radius * 2, radius * 2);
        g2.draw(circle);
    }

    public Dimension getPreferredSize()
    {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

### `java.awt.geom.RectangularShape` 1.2

- `CenterX()`
- `getCenterY()`
- `getMinX()`
- `getMinY()`
- `getMaxX()`
- `getMaxY()`

返回包围矩形的中心、最小或最大 `x` 或 `y` 值。

- `getWidth()`
- `getHeight()`
- `getX()`
- `getY()`

返回包围矩形左上角的 `x` 或 `y` 坐标。

### `java.awt.geom.Rectangle2D.Double` 1.2

- `Rectangle2D.Double(double x, double y, double w, double h)`

根据给定的左上角、宽度高度构造一个矩形。

### `java.awt.geom.Ellipse2D.Double` 1.2

- `Ellipse2D.Double(double x, double y, double w, double h)`

构造一个椭圆，其边界矩形具有给定的左上角、宽度和高度。

### `java.awt.geom.Point2D.Double` 1.2

- `Point2D.Double(double x, double y)`

根据给定的坐标构造一个点。

### `java.awt.geom.Line2D.Double` 1.2

- `Line2D.Double(Point2D start, Point2D end)`
- `Line2D.Double(double startX, double startY, double endX, double endY)`

根据给定的起点和终点构造一条线。

## 10.3.2 使用颜色

`Graphics2D` 类的 `setPaint` 方法允许你选择一种颜色，用于图形上下文上的所有绘制操作。例如：

```java
g2.setPaint(Color.RED);
g2.drawString("Warning!", 100, 100);
```

你可以用颜色填充闭合形状（如矩形或椭圆）的内部。只需调用 `fill` 而不是 `draw`：

```java
Rectangle2D rect = ...;
g2.setPaint(Color.RED);
g2.fill(rect); // 用红色填充 rect
```

要用多种颜色进行绘制，可以选择一种颜色，进行绘制或填充，然后选择另一种颜色，再次进行绘制或填充。

`fill` 方法在右侧和底部会少画一个像素。例如，如果你绘制一个 `new Rectangle2D.Double(0, 0, 10, 20)`，那么绘制结果包含 `x = 10` 和 `y = 20` 的像素。如果你填充同一个矩形，这些像素将不会被绘制。

使用 `Color` 类定义颜色。`java.awt.Color` 类提供了以下 13 种标准色的预定义常量：

```text
BLACK, BLUE, CYAN, DARK_GRAY, GRAY, GREEN, LIGHT_GRAY, MAGENTA, ORANGE, PINK, RED, WHITE, YELLOW
```

你可以通过其红、绿、蓝分创建 `Color` 对象来指定自定义颜色，每个值的值在 `0` 到 `255` 之间：

```java
g2.setPaint(new Color(0, 128, 128)); // 蓝绿色
g2.drawString("Warning!", 100, 100);
```

除了纯色，你还可以通过 `setPaint` 方法传递 `Paint` 接口的实例。这允许使用渐变和纹理。

要设置背景色，使用 `Component` 类的 `setBackground` 方法。

```java
var component = new MyComponent();
component.setBackground(Color.PINK);
```

`setForeground` 方法指定用于绘制的默认颜色。

### `java.awt.Color` 1.0

- `Color(int r, int g, int b)`

根据红、绿、蓝组件创建一个颜色对象，值在 `0` 到 `255` 之间。

### `java.awt.Graphics2D` 1.2

- `Paint getPaint()`
- `void setPaint(Paint p)`

获取或设置绘制属性。`Color` 类实现了 `Paint` 接口。

- `void fill(Shape s)`

用当前颜色填充形状。

### `java.awt.Component` 1.0

- `Color getForeground()`
- `Color getBackground()`
- `void setForeground(Color c)`
- `void setBackground(Color c)`

获取或设置前景或背景颜色。

## 10.3.3 使用字体

本书开头的“Hello World”程序使用默认字体显示字符串。有时，你可能想用不同的字体显示文本。你可以通过`字体名称`指定字体。字体名称由`字体族`（例如“Helvetica”）和一个可选的后缀（如“Bold”）组成。例如，“Helvetica”和“Helvetica Bold”都被认为是“Helvetica”族的一部分。

要找出特定计算机上的字体，调用 `GraphicsEnvironment` 类的 `getAvailableFamilyNames` 方法。该方法返回可用字体名称的数组。要获取描述用户系统图形环境的 `GraphicsEnvironment` 类实例，使用静态方法 `getLocalGraphicsEnvironment`。以下程序打印系统上所有的字体：

```java
import java.awt.*;

public class ListFonts
{
    public static void main(String[] args)
    {
        String[] fontNames = GraphicsEnvironment
            .getLocalGraphicsEnvironment()
            .getAvailableFamilyNames();
        for (String fontName : fontNames)
        {
            System.out.println(fontName);
        }
    }
}
```

AWT 定义了五个`逻辑`字体名称：

```text
SansSerif
Serif
Monospaced
Dialog
DialogInput
```

这些名称始终映射到客户端机器上实际存在的字体。例如，在 Windows 系统上，`SansSerif` 映射到 Arial。

此外，Oracle JDK 始终包含三个名为“Lucida Sans”、“Lucida Bright”和“Lucida Sans Typewriter”的字体族。

要在字体中绘制字符，必须先创建一个 `Font` 类对象。指定字体名称、字体样式和字号。以下是如何构造 `Font` 对象的示例：

```java
var sansbold14 = new Font("SansSerif", Font.BOLD, 14);
```

第三个参数是字号（point size）。点在排版中通常用于表示字体的大小。每英寸有 72 点。

你可以在 `Font` 构造函数中使用逻辑字体名称来代替字体脸名称。通过将 `Font` 构造函数的第二个参数设置为以下值之一来指定样式（`plain`、`bold`、`italic` 或 `bold italic`）：

```java
Font.PLAIN

Font.BOLD

Font.ITALIC

Font.BOLD + Font.ITALIC
```

该字体是普通字体，字号为 1 点。使用 `deriveFont` 方法获取所需大小的字体：

```java
Font f = f1.deriveFont(14.0F);
```

***

![Image](img/caution.jpg) **注意：**

`deriveFont` 方法有两个重载版本。其中一个（带有 `float` 参数的）设置字体大小，另一个（带有 `int` 参数的）设置字体样式。因此，`f1.deriveFont(14)` 设置的是样式而不是大小！（其结果是斜体字体，因为 `14` 的二进制表示中设置了 `ITALIC` 位，但没有设置 `BOLD` 位。）

***

以下是使用系统中的标准无衬线字体、14 点加粗字型，显示字符串“Hello, World!”的代码：



```java
var sansbold14 = new Font("SansSerif", Font.BOLD, 14);

g2.setFont(sansbold14);

var message = "Hello, World!";

g2.drawString(message, 75, 100);
```

接下来，让我们让字符串在它的组件中居中显示，而不是在任意位置绘制它。我们需要知道字符串在像素中的宽度和高度。这些维度取决于三个因素：

- 使用的字体（在我们的例子中，是无衬线字体、加粗、14 点）；
- 字符串（在我们的例子中，“Hello, World!”）；以及
- 绘制字体的设备（在我们的例子中，用户的屏幕）。

要获取一个表示屏幕设备字体特征的对象，调用`Graphics2D`类的`getFontRenderContext`方法。它返回一个`FontRenderContext`类的对象。只需将该对象传递给`Font`类的`getStringBounds`方法即可：

```java
FontRenderContext context = g2.getFontContext();

Rectangle2D bounds = sansbold14.getStringBounds(message, context);
```

`getStringBounds`方法返回一个包围字符串的矩形。为了解释该矩形的尺寸，你应该了解一些排版术语（见图 10.9）：

- `baseline`（基线）是一条虚线，例如，字母“e”的底部就停在上面。
- `ascent`（升部高度）是从`baseline`到`ascender`（升部字母）的距离，升部字母是如“b”或大写字母的上半部分。
- `descent`（下降高度）是从`baseline`到`descender`（下降字母）的距离，下降字母是如“p”或“g”等字母的下半部分。

![Image](img/10fig9.jpg) **图 10.9 排版术语**

- `Leading`（行间距）是上一行的`descent`与下一行的`ascent`之间的空间（该术语源于用于分隔行的条带）。
- 字体的`height`（高度）是相邻`baseline`之间的距离，等于`descent` + `ascent`。

`getStringBounds`方法返回的矩形的宽度是字符串的水平跨度。矩形的高度是`ascent`、`descent`和`leading`之和。矩形的原点位于字符串的`baseline`上。矩形的`y`坐标为负值。因此，你可以如下获取字符串宽度、高度和`ascent`：

```java
double stringWidth = bounds.getWidth();

double stringHeight = bounds.getHeight();

double ascent = -bounds.getY();
```

如果你需要知道`descent`或`leading`，请使用`Font`类的`getLineMetrics`方法。该方法返回一个`LineMetrics`类的对象，该对象拥有获取`descent`和`leading`的方法：

```java
LineMetrics metrics = f.getLineMetrics(message, context);

float descent = metrics.getDescent();

float leading = metrics.getLeading();
```

---

![Image](img/note.jpg) **注意：**

当需要在`paintComponent`方法之外计算布局时，无法从`Graphics2D`对象获取字体渲染信息。相反，调用`JComponent`类的`getFontMetrics`方法，然后调用`getFontContext`：

```java
FontRenderContext context = getFontMetrics(f).getFontContext();
```

---

为了证明定位是准确的，Listing 10.4 中的示例程序将字符串在框架中居中，并绘制了基线和边界矩形。图 10.10 显示了屏幕显示。

![Images](img/10fig10.jpg) **图 10.10 绘制基线和字符串边界**

**Listing 10.4 `font/FontTest.java`**

```java
package font;

import java.awt.*;
import java.awt.font.*;
import java.awt.geom.*;
import javax.swing.*;

/**
 * @version 1.35 2018-04-10
 * @author Cay Horstmann
 */
public class FontTest {
    public static void main(String[] args) {
        EventQueue.invokeLater(() -> {
            var frame = new FontFrame();
            frame.setTitle("FontTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 一个带有文本消息组件的框架。
 */
class FontFrame extends JFrame {
    public FontFrame() {
        add(new FontComponent());
        pack();
    }
}

/**
 * 一个在框中显示居中消息的组件。
 */
class FontComponent extends JComponent {
    static final int DEFAULT_WIDTH = 300;
    static final int DEFAULT_HEIGHT = 200;

    public void paintComponent(Graphics g) {
        Graphics2D g2 = (Graphics2D) g;
        String message = "Hello, World!";
        var f = new Font("Serif", Font.BOLD, 36);
        g2.setFont(f);

        // 测量消息的大小
        FontRenderContext context = g2.getFontContext();
        Rectangle2D bounds = f.getStringBounds(message, context);

        // 设置 (x,y) = 文本上角
        double x = (getWidth() - bounds.getWidth()) / 2;
        double y = (getHeight() - bounds.getHeight()) / 2;

        // 将 ascent 加到 y 以到达基线
        double ascent = -bounds.getY();
        double baseY = y + ascent;

        // 绘制消息
        g2.drawString(message, (int) x, (int) baseY);
        g2.setPaint(Color.LIGHT_GRAY);

        // 绘制基线
        g2.draw(new Line2D.Double(x, baseY, x + bounds.getWidth(), baseY));

        // 绘制边界矩形
        var rect = new Rectangle2D.Double(x, y, bounds.getWidth(), bounds.getHeight());
        g2.draw(rect);
    }

    public Dimension getPreferredSize() {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

## `java.awt.Font` 1.0

- `Font(String name, int style, int size)`

  创建一个新的字体对象。字体名称可以是字体脸名称（如`"Helvetica Bold"`）或逻辑字体名称（如`"Serif"`、`"SansSerif"`）。样式是`Font.PLAIN`、`Font.BOLD`、`Font.ITALIC`或`Font.BOLD + Font.ITALIC`之一。

- `String getFontName()` 获取字体脸名称（如`"Helvetica Bold"`）。
- `String getFamily()` 获取字体族名称（如`"Helvetica"`）。
- `String getName()` 如果字体是用逻辑字体名称创建的，则获取逻辑名称（如`"SansSerif"`）；否则，获取字体脸名称。
- `Rectangle2D getStringBounds(String s, FontRenderContext context)` 1.2

  返回一个包含字符串的矩形。矩形的原点位于基准线上。矩形的顶端`y`坐标等于上升高度的负值。矩形的高度等于上升高度、下降高度和行间距之和。宽度等于字符串宽度。

- `LineMetrics getLineMetrics(String s, FontRenderContext context)` 1.2

  返回一个行度量对象，以确定字符串的范围。

- `Font deriveFont(int style)` 1.2
- `Font deriveFont(float size)` 1.2
- `Font deriveFont(int style, float size)` 1.2

  返回一个新字体，它与当前字体相同，但具有指定的尺寸和样式。

### `java.awt.font.LineMetrics` 1.2

- `float getAscent()`

  获取字体上升高度——从基准线到大写字母顶部的距离。

- `float getDescent()`

  获取字体下降高度——从基准线到字母下部部分的距离。

- `float getLeading()`

  获取字体行间距——一行文本底部与下一行文本顶部之间的空间。

- `float getHeight()`

  获取字体总高度——文本两行基准线之间的距离（下降高度 + 行间距 + 上升高度）。

### `java.awt.Graphics2D` 1.2

- `FontRenderContext getFontRenderContext()`

  获取字体渲染上下文，该上下文指定此图形上下文中的字体特征。

- `void drawString(String str, float x, float y)`

  使用当前字体和颜色绘制字符串。

### `javax.swing.JComponent` 1.2

- `FontMetrics getFontMetrics(Font f)` 5

  获取给定字体的字体度量信息。`FontMetrics`类是`LineMetrics`类的前身。

### `java.awt.FontMetrics` 1.0

- `FontRenderContext getFontRenderContext()` 1.2

  获取该字体的字体渲染上下文。

## 10.3.4 显示图像

你可以使用`ImageIcon`类从文件中读取图像：

```java
Image image = new ImageIcon(filename).getImage();
```

现在变量`image`包含一个封装了图像数据的对象的引用。使用`Graphics`类的`drawImage`方法显示图像。

```java
public void paintComponent(Graphics g)
{
  . . .
  g.drawImage(image, x, y, null);
}
```

我们可以更进一步，用图形图像对窗口进行平铺（tile）。结果如图 10.11 所示。我们在`paintComponent`方法中进行平铺处理。我们首先在左上角绘制图像的一个副本，然后使用`copyArea`调用将其复制到整个窗口：

```java
for (int i = 0; i * imageWidth <= getWidth(); i++)
    for (int j = 0; j * imageHeight <= getHeight(); j++)
      if (i + j > 0)
        g.copyArea(0, 0, imageWidth, imageHeight, i * imageWidth, j * imageHeight);
```

![Images](img/10fig11.jpg)

**图 10.11** 带有平铺图形图像的窗口

### `java.awt.Graphics` 1.0

- `boolean drawImage(Image img, int x, int y, ImageObserver observer)`
- `boolean drawImage(Image img, int x, int y, int width, int height, ImageObserver observer)`

  绘制未缩放或缩放后的图像。注意：此调用可能在图像绘制完成之前返回。`imageObserver`对象会被通知渲染进度。这在过去是一个非常有用的特性。现在，只需传递一个`null`观察者即可。

- `void copyArea(int x, int y, int width, int height, int dx, int dy)`

  复制屏幕的一个区域。`dx`和`dy`参数是从源区域到目标区域的距离。

## 10.4 事件处理

任何支持 GUI 的操作系统环境都会持续监控如按键或鼠标点击等事件。这些事件会被报告给运行中的程序。然后，每个程序都会决定对这些事件做出什么反应（如果要做的话）。

### 10.4.1 基础事件处理概念

在 Java AWT 中，*事件源*（如按钮或滚动条）拥有允许你注册*事件监听器*的方法——即执行对事件的预期响应的对象。

当事件监听器被通知某个事件时，关于事件的信息被封装在*事件对象*中。在 Java 中，所有事件对象最终都派自`java.util.EventObject`类。当然，每种事件类型都有相应的子类，例如`ActionEvent`和`WindowEvent`。

不同的事件源可以产生不同类型的事件。例如，按钮可以发送`ActionEvent`对象，而窗口可以发送`WindowEvent`对象。

总结来说，以下是 AWT 事件处理工作原理的概述：

- 事件监听器是实现*监听器接口*的类的实例。
- 事件源是一个可以注册监听器对象并向它们发送事件对象的对象。
- 当事件发生时，事件源向所有已注册的监听器发送事件对象。
- 监听器对象利用事件对象中的信息来确定对事件的反应。

图 10.12 显示了事件源与监听器之间的关系。

### 10.4.2 示例：处理按钮点击

作为熟悉事件委托模型的一种方式，让我们通过处理按钮点击的细节。在这个示例中，我们将展示一个带有三个按钮的面板。三个监听器对象被作为动作监听器添加到按钮上。

在这种情况下，每当用户点击面板上的任何按钮时，关联的监听器都会接收到一个指示按钮点击的`ActionEvent`。在示例程序中，监听器将更改面板的背景颜色。

使用`ActionListener`接口的方法在所有情况下都是相同的：`actionPerformed`方法（它是`ActionListener`中唯一的方法）接受一个类型为`ActionEvent`的对象作为参数。这个事件对象提供了有关所发生事件的信息。

当按钮被点击时，我们希望面板的背景颜色变为特定的颜色。我们在监听器类中存储所需的颜色。

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
      // set 面板背景颜色
      . . .

   }
}
```

然后我们为每种颜色构造一个对象，并将这些对象设置为按钮的监听器。

```java
var yellowAction = new ColorAction(Color.YELLOW);

var blueAction = new ColorAction(Color.BLUE);

var redAction = new ColorAction(Color.RED);
```

```java
yellowButton.addActionListener(yellowAction);

blueButton.addActionListener(blueAction);

redButton.addActionListener(redAction);
```



例如，如果用户点击标记为“Yellow”的按钮，`yellowAction` 对象的 `actionPerformed` 方法会被调用。它的 `backgroundColor` 实例字段被设置为 `Color.YELLOW`，现在它可以继续设置面板的背景颜色。

仍然遗留一个问题。`ColorAction` 对象无法访问 `buttonPanel` 变量。你可以通过两种方法解决这个问题。你可以将面板存储在 `ColorAction` 对象中并在 `ColorAction` 构造函数中设置它。或者更方便的是，可以将 `ColorAction` 成为 `ButtonFrame` 类的内部类。这样它的方法就可以自动访问外部面板。

Listing 10.5 包含了完整的框架类。每当你点击其中一个按钮时，相应的监听器就会改变面板的背景颜色。

Listing 10.5 `button/ButtonFrame.java`

```java
 1  package button;

 2
 3  import java.awt.*;
 4  import java.awt.event.*;
 5  import javax.swing.*;
 6
 7  /**
 8    * 一个带有按钮面板的框架。
 9    */
10  public class ButtonFrame extends JFrame
11  {
12    private JPanel buttonPanel;
13    private static final int DEFAULT_WIDTH = 300;
14    private static final int DEFAULT_HEIGHT = 200;
15
16    public ButtonFrame()
17    {
18      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
19
20      // 创建按钮
21      var yellowButton = new JButton("Yellow");
22      var blueButton = new JButton("Blue");
23      var redButton = new JButton("Red");
24
25      buttonPanel = new JPanel();
26
27      // 将按钮添加到面板
28      buttonPanel.add(yellowButton);
29      buttonPanel.add(blueButton);
30      buttonPanel.add(redButton);
31
32      // 将面板添加到框架
33      add(buttonPanel);
34
35      // 创建按钮动作
36      var yellowAction = new ColorAction(Color.YELLOW);
37      var blueAction = new ColorAction(Color.BLUE);
38      var redAction = new ColorAction(Color.RED);
39
40      // 将动作与按钮关联
41      yellowButton.addActionListener(yellowAction);
42      blueButton.addActionListener(blueAction);
43      redButton.addActionListener(redAction);
44    }
45
46    /**
47      * 一个设置面板背景颜色的监听器。
48      */
49    private class ColorAction implements ActionListener
50    {
51      private Color backgroundColor;
52
53      public ColorAction(Color c)
54      {
55          backgroundColor = c;
56      }
57
58      public void actionPerformed(ActionEvent event)
59      {
60          buttonPanel.setBackground(backgroundColor);
61      }
62    }
63  }
```

`javax.swing.JButton` 1.2

- `JButton(String label)`
- `JButton(Icon icon)`
- `JButton(String label, Icon icon)`

构造一个按钮。标签字符串可以是纯文本或 HTML；例如，`"<html><b>Ok</b></html>"`。

`java.awt.Container` 1.0

- `Component add(Component c)`

将组件 `c` 添加到此容器。

#### 10.4.3 简洁地指定监听器

在前节中，我们为事件监听器定义了一个类并构造了该类的三个对象。监听器类拥有多个实例并不常见。通常情况下，每个监听器执行一个独立的动作。

#### 10.4.4 适配类

并不是所有事件都像点击按钮那样容易处理。假设你想监控用户尝试关闭主框架的情况，以便弹出对话框，并在用户同意后退出程序。

当用户尝试关闭窗口时，`JFrame` 对象是 `WindowEvent` 的源。如果你想捕获该事件，必须有一个相应的监听器并将其添加到框架的窗口监听器列表中。

```java
WindowListener listener = . . .;

frame.addWindowListener(listener);
```

窗口监听器必须是实现 `WindowListener` 接口的对象。`WindowListener` 实际上有七个方法。框架调用这些方法作为对窗口发生的七种不同事件的响应。这些名称是自俗易明的，只是在 Windows 下，“iconified”（最小化）通常被称为“minimized”。以下是完整的 `WindowListener` 接口：

```java
public interface WindowListener
{
  void windowOpened(WindowEvent e);
  void windowClosing(WindowEvent e);
  void windowClosed(WindowEvent e);
  void windowIconified(WindowEvent e);
  void windowDeiconified(WindowEvent e);
  void windowActivated(WindowEvent e);
  void windowDeactivated(WindowEvent e);
}
```

当然，我们可以定义一个实现接口的类，在 `windowClosing` 方法中添加对 `System.exit(0)` 的调用，并为其他六个方法编写空函数。然而，为六个无所作用的方法编写代码是那种没人喜欢的无聊重复劳动。为了简化这项任务，每个具有多个方法的 AWT 监听接口都带有一个配套的适配器（adapter）类，该类实现了接口中的所有方法，但对它们不执行任何操作。例如，`WindowAdapter` 类有七个什么都不做的方法。你通过扩展适配器类来为接口中的某些（但不是全部）事件类型指定所需的响应。（像 `ActionListener` 这样只有一个方法的接口就不需要适配器类。）

以下是我们如何定义一个重写了 `windowClosing` 方法的窗口监听器：

```java
class Terminator extends WindowAdapter
{
   public void windowClosing(WindowEvent e)
   {
      if (user agrees)
          System.exit(0);
   }
}
```

现在，你可以将一个 `Terminator` 类型的对象注册为事件监听器：

```java
var listener = new Terminator();
frame.addWindowListener(listener);
```

***

![Image](img/note.jpg) **注意：**

如今，人们会使用默认方法来实现 `WindowListener` 接口的空方法。然而，Swing 是在默认方法出现之前的很多年就已经发明的。

***

### `java.awt.event.WindowListener` 1.1

- `void windowOpened(WindowEvent e)` 在窗口打开后调用。
- `void windowClosing(WindowEvent e)` 在用户向窗口管理器发出关闭窗口命令时调用。请注意，只有当调用了 `hide` 或 `dispose` 方法时，窗口才会关闭。
- `void windowClosed(WindowEvent e)` 在窗口关闭后调用。
- `void windowIconified(WindowEvent e)` 在窗口被最小化后调用。
- `void windowDeiconified(WindowEvent e)` 在窗口恢复还原化后调用。
- `void windowActivated(WindowEvent e)` 在窗口变为激活状态后调用。只有框架或对话框可以是激活状态。通常情况下，窗口管理器会对激活的窗口进行装饰——例如，通过高亮标题栏。
- `void windowDeactivated(WindowEvent e)` 在窗口变为非激活状态后调用。

### `java.awt.event.WindowStateListener` 1.4

- `void windowStateChanged(WindowEvent event)` 在窗口最大化、最小化或恢复到正常大小后调用。

#### 10.4.5 操作（Actions）

通过多种方式激活同一个命令是常见现象。用户可以通过菜单、按键或工具栏上的按钮来选择某个功能。这在 AWT 事件模型中很容易实现：将所有事件链接到同一个监听器上。例如，假设 `blueAction` 是一个动作监听器，其 `actionPerformed` 方法将背景颜色更改为蓝色。你可以将同一个对象作为监听器附加到多个事件源上：

- 一个标记为“Blue”的工具栏按钮
- 一个标记为“Blue”的菜单项
- 一个按键组合 Ctrl+B

颜色更改命令现在将以统一的方式被处理，无论它是由按钮点击、菜单选择还是按键引起的。

Swing 包提供了一个非常实用的机制来封装命令并将其附加到多个事件源上：`Action` 接口。一个动作（action）是一个封装了以下内容的对象：

- 命令的描述（作为文本字符串和可选图标）；以及
- 执行命令所需的参数（例如我们示例中请求的颜色）。

`Action` 接口具有以下方法：

```java
void actionPerformed(ActionEvent event)
void setEnabled(boolean b)
boolean isEnabled()
void putValue(String key, Object value)
Object getValue(String key)
void addPropertyChangeListener(PropertyChangeListener listener)
void removePropertyChangeListener(PropertyChangeListener listener)
```

第一个方法是 `ActionListener` 接口中熟悉的方法；事实上，`Action` 接口扩展了 `ActionListener` 接口。因此，在需要 `ActionListener` 对象的地方，你可以使用 `Action` 对象。

接下来两个方法允许你启用或禁用动作，并检查动作当前是否处于启用状态。当动作附加到菜单或工具栏上且该动作被禁用时，该选项将变为灰色。

`putValue` 和 `getValue` 方法允许你在动作对象中存储和检索任意的键/值对。两个重要的预定义字符串，即 `Action.NAME` 和 `Action.SMALL_ICON`，将动作名称和图标存储到动作对象中：

```java
action.putValue(Action.NAME, "Blue");
action.putValue(Action.SMALL_ICON, new ImageIcon("blue-ball.gif"));
```

表 10.1 显示了所有预定义的动作表名称。

如果动作对象被添加到菜单或工具栏，名称和图标将被自动检索并显示在菜单项或工具栏按钮中。`SHORT_DESCRIPTION` 值将变成工具提示。

`Action` 接口的最后两个方法允许其他对象（特别是触发动作的菜单或工具栏）在动作对象的属性发生变化时收到通知。例如，如果一个菜单作为动作对象的属性更改监听器被添加，并且动作对象随后被禁用，则该菜单会被调用并可以将动作名称变灰。

注意 `Action` 是一个接口（interface），而不是类。任何实现此接口的类必须实现我们刚刚讨论的七个方法。幸运的是，一位热心的人提供了一个类，实现了除了 `actionPerformed` 之外的所有方法。该类处理键/值对并管理属性更改监听器。你只需扩展 `AbstractAction` 并提供 `actionPerformed` 方法。



表 10.1 显示了所有预定义的动作表名称。

如果动作对象被添加到菜单或工具栏，名称和图标将被自动检索并显示在菜单项或工具栏按钮中。`SHORT_DESCRIPTION` 值将变成工具提示。

`Action` 接口的最后两个方法允许其他对象（特别是触发动作的菜单或工具栏）在动作对象的属性发生变化时收到通知。例如，如果一个菜单作为动作对象的属性更改监听器被添加，并且动作对象随后被禁用，则该菜单会被调用并可以将动作名称变灰。

注意 `Action` 是一个*接口*（*interface*），而不是类。任何实现此接口的类必须实现我们刚刚讨论的七个方法。幸运的是，一位热心的人提供了一个类 `AbstractAction`，实现了除了 `actionPerformed` 之外的所有方法。该类处理键/值对并管理属性更改监听器。

```
action.putValue(Action.NAME, "Blue");
action.putValue(Action.SMALL_ICON, new ImageIcon("blue-ball.gif"));
```

```
KeyStroke ctrlBKey = KeyStroke.getKeyStroke("ctrl B");
```

要理解下一步，你需要理解 `keyboard focus`（键盘焦点）的概念。一个用户界面可以包含许多按钮、菜单、滚动条和其他组件。当你按下按键时，该按键会被发送到拥有焦点的组件。该组件通常（但并非总是）会在视觉上有所区分。例如，在 Java 外观（look-and-feel）中，具有焦点的按钮会在按钮文字周围有一个细的矩形框。你可以使用 `Tab` 键在组件之间移动焦点。当你按下空格键时，具有焦点的按钮会被点击。其他按键执行不同的操作；例如，方向键可以移动滚动条。

然而，在我们的情况下，我们并不希望将按键发送到拥有焦点的组件。否则，每个按钮都得知道如何处理 `Ctrl+Y`、`Ctrl+B` 和 `Ctrl+R` 键。

这是一个常见问题，Swing 的设计者提供了一个方便的解决方案。每个 `JComponent` 都有三个 `input maps`（输入映射），每个映射将 `KeyStroke` 对象映射到相关的动作（actions）。这三个输入映射对应三个不同的条件（参见 表 10.2）。

**表 10.2** 输入映射条件

![Images](img/10tab02.jpg)

按键处理按以下顺序检查这些映射：

1. 检查具有输入焦点的组件的 `WHEN_FOCUSED` 映射。如果该按键存在且对应的动作已启用，则执行该动作并停止处理。

2. 从具有焦点的组件开始，检查其父级组件的 `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT` 映射。一旦发现带有按键和对应已启用动作的映射，立即执行该动作并停止处理。

3. 在具有输入焦点的窗口中，查看所有 `visible`（可见）且 `enabled`（启用）的组件，它们在 `WHEN_IN_FOCUSED_WINDOW` 映射中注册了该按键。给这些组件（按按键注册的顺序）一个执行对应动作的机会。一旦执行了第一个启用的动作，停止处理。

要从组件获取输入映射，请使用 `getInputMap` 方法。这是一个示例：

```
InputMap imap = panel.getInputMap(JComponent.WHEN_FOCUSED);
```

`WHEN_FOCUSED` 条件意味着当当前组件拥有键盘焦点时会查询此映射。在我们的情况下，这并不是我们想要的映射。是按钮中的一个而不是面板拥有输入焦点。另外两个映射选择中的任意一个对于插入颜色更改按键都是有效的。我们在示例程序中使用 `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT`。

`InputMap` 并不直接将 `KeyStroke` 对象映射到 `Action` 对象。相反，它映射到任意对象，而由 `ActionMap` 类实现的第二个映射则将这些对象映射到动作。这使得在来自不同输入映射的按键之间共享相同的动作变得更容易。

因此，每个组件都有三个输入映射和一个动作映射。为了将它们连接起来，你需要为动作命名。以下是你可以如何将按键绑定到动作的方法：

```
imap.put(KeyStroke.getKeyStroke("ctrl Y"), "panel.yellow");
ActionMap amap = panel.getActionMap();
amap.put("panel.yellow", yellowAction);
```

习惯上使用字符串 `"none"` 作为无操作动作的动作。这使得禁用某个按键变得简单：

```
imap.put(KeyStroke.getKeyStroke("ctrl C"), "none");
```

***

![Image](img/caution.jpg) **注意：**

JDK 文档建议使用动作名称作为动作的键。我不认为这是一个好主意。动作名称会显示在按钮和菜单项上；因此，它可以根据 UI 设计师的意愿而改变，并被翻译成多种语言。这种不稳定的字符串是查找键的糟糕选择，因此我建议你想出与显示名称无关的动作名称。

***

总结一下，以下是响应按钮、菜单项或按键以执行相同动作的步骤：

1. 实现一个继承自 `AbstractAction` 类的类。你可能可以使用同一个类处理多个相关的动作。

2. 构造一个动作类的对象。

3. 从动作对象构造一个按钮或菜单项。构造函数将从动作对象中读取标签文本和图标。

4. 对于可以由按键触发的动作，你必须执行额外的步骤。首先，找到窗口的顶层组件，例如包含所有其他组件的面板。

5. 然后，获取顶层组件的 `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT` 输入映射。为所需的按键创建一个 `KeyStroke` 对象。创建一个动作键对象，例如描述你动作的字符串。将键对（按键, 动作键）添加到输入映射中。

6. 最后，获取顶层组件的动作映射。将键对（动作键, 动作对象）添加到映射中。

***

**`javax.swing.Action`** 1.2

- `boolean isEnabled()`
- `void setEnabled(boolean b)`
获取或设置此动作的 `enabled` 属性。

- `void putValue(String key, Object value)`
在动作内部放置一个键/值对。键可以是任何字符串。

- `Object getValue(String key)`
返回 key 的值。

**`javax.swing.KeyStroke`** 1.2

- `static KeyStroke getKeyStroke(String description)`
从可读的描述（空格分隔的字符串）构造按键。描述以零或多个修饰符（`shift`、`control`、`meta`、`alt`、`altGraph`）开始，并以字符串 `typed` 结束，后跟一个字符字符串（例如 `"typed a"`），或者可选的事件指定符（`pressed` 或 `released`，默认为 `pressed`），后跟一个键码。键码在加上 `VK_` 前缀后应对应 `KeyEvent` 常量；例如，`"INSERT"` 对应 `KeyEvent.VK_INSERT`。

**`javax.swing.JComponent`** 1.2

- `ActionMap getActionMap()`
返回动作键（可以是任意对象）与动作对象的映射。

- `InputMap getInputMap(int flag)`
获取映射按键到动作键的输入映射。flag 是 表 10.2 中的值之一。

#### 10.4.6 鼠标事件

如果你只想让用户点击按钮或菜单，就不需要处理鼠标事件。这些鼠标操作由用户界面中的各种组件内部处理。然而，如果你想允许用户用鼠标，你需要捕捉移动、点击和拖拽事件。

在本节中，我将向你展示简单的图形编辑器应用程序，允许用户在画布上放置、移动和删除正形（参见 图 10.16）。

![Images](img/10fig16.jpg)

**图 10.16** 鼠标测试程序

当用户点击鼠标按钮时，会调用三个监听方法：`mousePressed` 在鼠标按下时调用，`mouseReleased` 在鼠标释放时调用，最后是 `mouseClicked`。如果你对完整的点击感兴趣，可以忽略前两个方法。通过使用 `MouseEvent` 参数的 `getX` 和 `getY` 方法，你可以获取鼠标指针点击时的 *x* 和 *y* 坐标。要区分单击、双击和三击，请使用 `getClickCount` 方法。

在我们的示例程序中，我们同时提供了 `mousePressed` 和 `mouseClicked` 方法。当你点击一个不在任何已绘制正方形内部的像素时，就会添加一个新的正方形。我们在 `mousePressed` 方法中实现了这一功能，这样用户就能获得即时反馈，而不需要等待释放鼠标按钮。当用户在现有正方形内部双击时，该正方形会被擦除。我们在 `mouseClicked` 方法中实现了这一功能，因为我们需要获取点击次数。

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

当鼠标在窗口移动时，窗口会接收到连续的鼠标移动事件。请注意，存在独立的 `MouseListener` 和 `MouseMotionListener` 接口。这样做是为了效率考虑——当用户移动鼠标时，会产生大量的鼠标事件，而一个只关心鼠标*点击*的监听器就不会被不需要的鼠标*移动*打扰。

我们的测试应用程序捕获鼠标移动事件，以便在鼠标悬停在正方形上并将光标更改为不同的形状（十字准）。这是通过 `Cursor` 类的 `getPredefinedCursor` 方法实现的。表 10.3 列出了配合此方法使用的常量，以及这些光标在 Windows 下的样式。

**表 10.3** 示例光标形状

![Images](img/10tab03.jpg)

以下是示例程序中 `MouseMotionListener` 的 `mouseMoved` 方法：

```java



```java
public void mouseMoved(MouseEvent event)
{
   if (find(event.getPoint()) == null)
       setCursor(Cursor.getDefaultCursor());
   else
       setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));
}
```

如果用户在鼠标移动时按下鼠标按钮，则会生成 `mouseDragged` 调用而不是 `mouseMoved` 调用。我们的测试应用程序允许用户拖动鼠标下的正方形。我们简单地更新当前正在拖动的矩形，使其位于鼠标位置的正下方。然后，我们重绘画布以显示新的鼠标位置。

```java
public void mouseDragged(MouseEvent event)
{
   if (current != null)
   {
      int x = event.getX();
      int y = event.getY();
      current.setFrame(x - SIDELENGTH / 2, y - SIDELENGTH / 2, SIDELENGTH, SIDELENGTH);
      repaint();
   }
}
```

> **注意：**
>
> `mouseMoved` 方法只有在鼠标留在组件内部时才会被调用。然而，当鼠标被拖动到组件外部时，`mouseDragged` 方法会持续被调用。

还有另外两个鼠标事件方法：`mouseEntered` 和 `mouseExited`。这些方法在鼠标进入或离开组件时被调用。

最后，让我们看看如何监听鼠标事件。鼠标点击通过 `mouseClicked` 方法报告，该方法是 `MouseListener` 接口的一部分。许多应用程序只感兴趣鼠标点击而非鼠标移动；由于鼠标移动事件发生频繁，鼠标移动和拖拽事件定义在一个名为 `MouseMotionListener` 的独立接口中。

在我们的程序中，对这两种鼠标事件都感兴趣。我们定义了两个内部类：`MouseHandler` 和 `MouseMotionHandler`。`MouseHandler` 类继承了 `MouseAdapter` 类，因为它只定义了五个 `MouseListener` 方法中的两个。（`MouseAdapter` 类将所有方法都定义为空方法。）`MouseMotionHandler` 实现了 `MouseMotionListener` 并定义了该接口的两个方法。代码列表 10.6 是程序列表。

**列表 10.6** `mouse/MouseComponent.java`

```java
package mouse;

import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;
import java.util.*;
import javax.swing.*;

/**
 * 一个具有添加和删除正方形鼠标操作次数的组件。
 */
public class MouseComponent extends JComponent
{
   private static final int DEFAULT_WIDTH = 300;
   private static final int DEFAULT_HEIGHT = 200;

   private static final int SIDELENGTH = 10;
   private ArrayList<Rectangle2D> squares;
   private Rectangle2D current; // 包含光标的正方形

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

      // 绘制所有正方形
      for (Rectangle2D r : squares)
          g2.draw(r);
   }

   /**
    * 包含点的正方形。
    * @param p 点
    * @return 包含 p 的正方形
    */
   public Rectangle2D find(Point2D p)
   {
      for (Rectangle2D r : squares)
          if (r.contains(p)) return r;
      return null;
   }

   /**
    * 将正方形添加到集合。
    * @param p 正方形的中心
    */
   public void add(Point2D p)
   {
      double x = p.getX();
      double y = p.getY();

      current = new Rectangle2D.Double(x - SIDELENGTH / 2, y - SIDELENGTH / 2,
          SIDELENGTH, SIDELENGTH);
      squares.add(current);
      repaint();
   }

   /**
    * 从集合中删除正方形。
    * @param s 要删除的正方形
    */
   public void remove(Rectangle2D s)
   {
      if (s == null) return;
      if (s == current) current = null;
      squares.remove(s);
      repaint();
   }

   private class MouseHandler extends MouseAdapter
   {
      public void mousePressed(MouseEvent event)
      {
         // 如果光标不在正方形内，则添加新正方形
         current = find(event.getPoint());
         if (current == null) add(event.getPoint());
      }

      public void mouseClicked(MouseEvent event)
      {
         current = find(event.getPoint());
         if (current != null && event.getClickCount() >= 2)
             remove(current);
      }
   }

   private class MouseMotionHandler implements MouseMotionListener
   {
      public void mouseMoved(MouseEvent event)
      {
         // 如果鼠标光标在矩形内，则将鼠标光标设置为十字准星
         if (find(event.getPoint()) == null)
             setCursor(Cursor.getDefaultCursor());
         else
             setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));
      }

      public void mouseDragged(MouseEvent event)
      {
         if (current != null)
         {
            int x = event.getX();
            int y = event.getY();

            // 拖动当前矩形，使其以 (x, y) 为中心
            current = new Rectangle2D.Double(x - SIDELENGTH / 2, y - SIDELENGTH / 2,
                SIDELENGTH, SIDELENGTH);
            repaint();
         }
      }
   }
}
```

• `public void setCursor(Cursor cursor)` 1.1

将光标图像设置为指定的光标。

## 10.4.7 AWT 事件层次级结构

`EventObject` 类有一个子类 `AWTEvent`，它是所有 AWT 事件类的父类。图 10.17 显示了 AWT 事件的继承图。

![Images](img/10fig17.jpg)

**图 10.17** AWT 事件类的继承图

某些 Swing 组件会生成更多事件类型的事件对象；这些对象直接扩展自 `EventObject`，而不是 `AWTEvent`。

事件对象封装了事件源向其监听器通信的事件信息。在需要时，你可以分析传递给监听器对象的事件对象，就像我们在按钮示例中使用 `getSource` 和 `getActionCommand` 方法做的那样。

某些 AWT 事件类对 Java 程序员来说没有实际用途。例如，AWT 会将 `PaintEvent` 对象插入事件队列，但这些对象并不会被派送给监听器。Java 程序员不会监听绘图事件；相反，他们通过重写 `paintComponent` 方法来控制重绘。AWT 还会产生许多仅系统程序员需要的事件，用于为意文字语言提供输入系统、自动化测试机器人等。

AWT 在 `low-level`（低级）事件和 `semantic`（语义）事件之间做了非常有用的区分。语义事件表达了用户正在进行的操作，例如“点击那个按钮”；`ActionEvent` 就是一个语义事件。低级事件是实现这些操作的事件。在点击按钮的情况下，这包括鼠标按下、一系列鼠标移动和鼠标释放（但仅当鼠标释放在按钮区域内时有效）。或者也可能是按键，如果用户使用 Tab 键选中按钮然后用空格键激活它，就会发生。同样，调整滚动条是一个语义事件，但拖动鼠标是一个低级事件。

以下是 `java.awt.event` 包中通常用的语义事件类：

• `ActionEvent`（用于按钮点击、菜单选择、选择列表项或在文本字段中输入回车键）

• `AdjustmentEvent`（用户调整了滚动条）

• `ItemEvent`（用户从一组复选框或列表项中选择）

常用的有五个低级事件类：

• `KeyEvent`（键被按下或释放）

• `MouseEvent`（鼠标按钮被按下、释放、移动或拖动）

• `MouseWheelEvent`（鼠标轮被旋转）

• `FocusEvent`（组件获得焦点或失去焦点）

• `WindowEvent`（窗口状态发生变化）

表 10.4 显示了最重要的 AWT 监听接口、事件和事件源。

**表 10.4** 事件处理总结

![Images](img/10tab04.jpg)

### 10.5 Preferences API

我通过对 `java.util.prefs` API 的讨论来结束本章。在桌面程序中，你通常想要存储用户偏好，例如用户最后处理的文件、最后一个窗口位置等。

正如你在第 9 章中所示，`Properties` 类使得加载和保存程序的配置信息变得简单。然而，使用属性文件有以下缺点：

• 某些操作系统没有“主目录”的概念，这使得很难为配置文件找到一个统一的位置。

• 配置文件的命名没有标准约定，增加了用户在安装多个 Java 时发生名称冲突的概率。

某些操作系统拥有配置信息的中央仓库。最广为人知的例子是 Microsoft Windows 中的注册表。`Preferences` 类以平台无关的方式提供了这样一个中央仓库。在 Windows 中，`Preferences` 类使用注册表进行存储；而在 Linux 上，信息存储在本地文件系统中。当然，对于使用 `Preferences` 的程序员来说，仓库的实现是透明的。

`Preferences` 仓库具有树形结构，具有如 `/com/mycompany/myapp` 的节点路径名。与包名一样，只要程序员以反向域名开头路径，就可以避免名称冲突。事实上，API 设计者建议配置节点路径与你程序中的包名匹配。

仓库中的每个节点都有一个独立的键值对表，你可以用它存储数字、字符串或字节数组。该 API 未提供存储序列化对象的规定。API 设计者认为序列化格式对于长期存储来说太脆弱。当然，如果你不同意，可以将序列化对象保存在字节数组中。

为了增加额外的灵活性，存在多个并行的树。每个程序用户拥有一个树；另一个名为“系统树”的树适用于所有用户的公共设置。`Preferences` 类使用操作系统的“当前用户”概念来访问相应的用户树。

要访问树中的节点，从用户根或系统根开始：

```java
Preferences root = Preferences.userRoot();
```

或者：

```java
Preferences root = Preferences.systemRoot();
```

然后访问节点。你可以直接提供节点路径名：

```java
Preferences node = root.node("/com/mycompany/myapp");
```

有一个方便的快捷方式可以获取路径名等于类包名的节点。只需获取该类的一个对象并调用：

```java
Preferences node = Preferences.userNodeForPackage(obj.getClass());
```

或者：

```java
Preferences node = Preferences.systemNodeForPackage(obj.getClass());
```

通常，`obj` 将是 `this` 引用。

一旦有了节点，你可以使用以下方法访问键值表：

```java
String get(String key, String defval)

int getInt(String key, int defval)

long getLong(String key, long defval)

float getFloat(String key, float defval)

double getDouble(String key, double defval)

boolean getBoolean(String key, boolean defval)

byte[] getByteArray(String key, byte[] defval)
```

注意，在读取信息时必须指定默认值，以防仓库数据不可用。需要默认值有几个原因：数据可能因为用户从未指定偏好而缺失；某些资源受限的平台可能没有仓库；移动设备可能会临时断开连接。

相反，你可以使用 `put` 方法将数据写入仓库，例如：

```java
put(String key, String value)

putInt(String key, int value)
```

等等。

你可以使用 `keys()` 方法列出节点中的所有键：

```java
String[] keys()
```

目前没有方法可以确定特定键的值类型。

> **注意：**节点名和键限制为 80 个字符，字符串值限制为 8192 个字符。

中央仓库（如 Windows 注册表）存在两个问题：

• 它们变成了充满了过期信息的“垃圾场”。

• 配置数据与仓库耦合，使得将偏好迁移到新平台变得困难。

`Preferences` 类为第二个问题提供了解决方案。你可以通过调用方法导出子树（或较少见的单个节点）的偏好：

```java
void exportSubtree(OutputStream out)

void exportNode(OutputStream out)
```

数据以 XML 格式保存。你可以通过调用以下方法将它们导入到另一个仓库：

```java
void importPreferences(InputStream in)
```

这是一个示例文件：

```xml



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

        <node name="corejava">

          <map>

            <entry key="height" value="200.0"/>

            <entry key="left" value="1027.0"/>

            <entry key="filename" value="/home/cay/books/cj11/code/v1ch11/raven.html"/>

            <entry key="top" value="380.0"/>

            <entry key="width" value="300.0"/>

          </map>

        </node>

      </node>

    </node>

  </root>

</preferences>
```

如果你的程序使用了首选项（preferences），你应该为用户提供导出和导入首选项的机会，这样他们就可以轻松地将设置从一台计算机迁移到另一台。列表 10.7 中的程序演示了这种技术。程序仅保存了窗口位置和最后加载的文件。尝试调整窗口大小，然后导出首选项，移动窗口，退出并重启应用程序。窗口将与你退出时完全一样。导入首选项后，窗口将恢复到之前的位置。

### 列表 10.7 `preferences/ImageViewer.java`

```java
package preferences;

import java.awt.EventQueue;
import java.awt.event.*;
import java.io.*;
import java.util.prefs.*;
import javax.swing.*;

/**
 * 一个测试首选项设置的程序。程序记得
 * 框架的位置、大小和最后选择的文件。
 * @version 1.10 2018-04-10
 * @author Cay Horstmann
 */
public class ImageViewer
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                var frame = new ImageViewerFrame();
                frame.setTitle("ImageViewer");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 一个图像查看器，可以从用户
 * 首选项中恢复位置、大小和图像，并在退出时
 * 更新首选项。
 */
class ImageViewerFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;
    private String image;

    public ImageViewerFrame()
    {
        Preferences root = Preferences.userRoot();
        Preferences node = root.node("/com/horstmann/corejava/ImageViewer");
        // 从属性中获取位置、大小、标题
        int left = node.getInt("left", 0);
        int top = node.getInt("top", 0);
        int width = node.getInt("width", DEFAULT_WIDTH);
        int height = node.getInt("height", DEFAULT_HEIGHT);
        setBounds(left, top, width, height);
        image = node.get("image", null);
        var label = new JLabel();
        if (image != null) label.setIcon(new ImageIcon(image));

        addWindowListener(new WindowAdapter()
        {
            public void windowClosing(WindowEvent event)
            {
                node.putInt("left", getX());
                node.putInt("top", getY());
                node.putInt("width", getWidth());
                node.putInt("height", getHeight());
                if (image != null) node.put("image", image);
            }
        });

        // 使用 label 显示图像
        add(label);

        // 设置文件选择器
        var chooser = new JFileChooser();
        chooser.setCurrentDirectory(".");

        // 设置菜单栏
        var menuBar = new JMenuBar();
        setMenuBar(menuBar);

        var menu = new JMenu("File");
        menuBar.add(menu);

        var openItem = new JMenuItem("Open");
        menu.add(openItem);
        openItem.addActionListener(event ->
            {
                // 显示文件选择器
                int result = chooser.showOpenDialog(null);

                // 如果选择了文件，则将其设为 label 的图标
                if (result == JFileChooser.APPROVE_OPTION)
                {
                    image = chooser.getSelectedFile().getPath();
                    label.setIcon(new ImageIcon(image));
                }
            });

        var exitItem = new JMenuItem("Exit");
        menu.add(exitItem);
        exitItem.addActionListener(event -> System.exit(0));
    }
}
```

### `java.util.prefs.Preferences` 14

- `userRoot()` 返回用户的首选项根节点。
- `systemRoot()` 返回系统首选项根节点。
- `node(String path)` 返回从当前节点通过路径到达的节点。如果 `path` 是绝对的（即以 `/` 开头），则从根开始查找。
- `userNodeForPackage(Class cl)` 返回与类 `cl` 包名对应的用户首选项树节点。
- `String[] keys()` 返回属于此节点的所有键。
- `String get(String key, String defval)` 返回与键关联的字符串。
- `int getInt(String key, int defval)` 返回与键关联的整数。
- `long getLong(String key, long defval)` 返回与键关联的长整型。
- `float getFloat(String key, float defval)` 返回与键关联的浮点型。
- `double getDouble(String key, double defval)` 返回与键关联的双精度浮点型。
- `boolean getBoolean(String key, boolean defval)` 返回与键关联的布尔值。
- `byte[] getByteArray(String key, byte[] defval)` 返回与键关联的字节数组。如果没有关联值、关联类型不正确或首选项存储不可用，则返回提供的默认值。
- `void put(String key, String value)` 在此节点中存储一个键值对。
- `void putInt(String key, int value)` 在此节点中存储一个整数。
- `void putLong(String key, long value)` 在此节点中存储一个长整型。
- `void putFloat(String key, float value)` 在此节点中存储一个浮点型。
- `void putDouble(String key, double value)` 在此节点中存储一个双精度浮点型。
- `void putBoolean(String key, boolean value)` 在此节点中存储一个布尔值。
- `void putByteArray(String key, byte[] value)` 在此节点中存储一个字节数组。
- `void exportSubtree(OutputStream out)` 将此节点及其子节点导出到指定的输出流。
- `void exportNode(OutputStream out)` 将此节点（但不包括其子节点）导出到指定的输出流。
- `void importPreferences(InputStream in)` 导入包含在指定流中的首选项。

## 第 11 章 使用 Swing 用户界面组件

### 在本章中

- 11.1 Swing 和模型-视图-控制器模式
- 11.2 布局管理简介
- 11.3 输入
- 11.4 选择组件
- 11.5 菜单
- 11.6 复杂的布局管理
- 11.7 对话框

上一章主要是为了向你展示 Java 的事件模型。在此过程中，你迈了构建图形用户界面的第一步。本章将向你展示构建更功能完整的 GUI 所需的最重要工具。

我们将首先介绍 Swing 的架构基础。了解“内部”运行了什么内容，对于理解如何有效地使用某些高级组件至关重要。随后，我将向你展示 Swing 中常用的用户界面组件，例如文本字段、单选按钮和菜单。接下来，你将学习如何使用布局管理器来安排这些组件。最后，你将看到如何在 Swing 中实现对话框。

本章涵盖了基础的 Swing 组件，如文本组件、按钮和滑块。这些是你最频繁需要使用的本质用户界面组件。我们将在第二卷中介绍高级 Swing 组件。

## 11.1 Swing 和模型-视图-控制器（MVC）设计模式

让我们停下来，思考一下构成用户界面组件（如按钮、复选框、文本字段或复杂的树控件）的各个。每个组件都有三个特征：

- 它的 `content`，例如按钮的状态（按下或未按下）或文本字段中的文本
- 它的 `visual appearance`（颜色、大小等）
- 它的 `behavior`（对事件的反应）

即使是像按钮这样看似简单的组件，这些特征之间也表现出中等复杂的交互。显然，按钮的视觉外观取决于外观（look-and-feel）。Metal 按钮看起来与 Windows 按钮或 Motif 按钮不同。此外，外观取决于按钮状态；当按钮被按下时，它需要被重绘以显示不同的外观。状态取决于按钮接收到的事件。当用户在按钮内部按下鼠标时，按钮就会被按下。

当然，当你在程序中使用按钮时，你只是简单地将其视为一个 `button`；你不会过多地考虑其内部机制和特征。毕竟，那是实现按钮的程序员的工作。然而，实现按钮及所有其他用户界面组件的程序员，有动力对它们进行更深层次的思考，以确保无论生效的是哪种外观，它们都能良好工作。

为了做到这一点，Swing 的设计者们转向了一种著名的设计模式：`model-view-controller`（MVC）模式。这种设计模式告诉我们提供三个独立的对象：

- `model`（模型），存储内容
- `view`（视图），显示内容
- `controller`（控制器），处理用户输入

该模式精确规定了这三个对象如何交互。模型存储内容且没有用户界面。对于按钮来说，内容非常简单——只是一小组标志位，用于告诉我们按钮当前是按下还是弹起、是激活还是空闲等。对于文本字段，内容就稍微有趣一点。它是一个持有当前文本的字符串对象。这不等同于内容的视图——如果内容大于文本字段，用户只能看到显示的部分文本（请参见图 11.1）。

![Images](img/11fig01.jpg)

**图 11.1** 文本字段的模型和视图

模型必须实现更改内容和发现内容是什么的方法。例如，文本模型有方法可以在当前文本中添加或删除字符，并把当前文本作为字符串返回。再次，请记住，模型是完全非视觉的。绘制存储在模型中的数据是视图的任务。

> ![Image](img/note.jpg) **注意：**
>
> “模型（model）”这个词可能不太理想，因为我们经常认为模型是某个抽象概念的表示。汽车和飞机设计师建立模型来模拟真实的汽车和飞机。但在思考模型-视图-控制器模式时，这种类比真的会误导你。在这一设计模式中，模型存储完整的内容，而视图提供了内容的（完整或不完整的）视觉表示。一个更好的类比可能是为艺术家摆姿的模型。观察模型并创建视图是艺术的任务。取决于艺术家，那个视图可能是一个正式肖像、一幅印象派绘画，或是一幅肢体奇异扭曲的立体主义画。

模型-视图-控制器模式的优势之一是模型可以拥有多个视图，每个视图显示完整内容的不同部分或方面。例如，HTML 编辑器可以提供同一内容的两个`同时`视图：一个所见即所得（WYSIWYG）视图和一个“原始标签”视图（请参见图 11.2）。当模型通过其中一个视图的控制器更新时，它会通知所有关联的视图更改。当视图被通知时，它们会自动刷新自己。当然，对于像按钮这样简单的用户界面组件，你不会拥有同一个模型的多个视图。

![Images](img/11fig02.jpg)

**图 11.2** 同一模型的两个独立视图

控制器处理用户输入事件，例如鼠标点击和按键触发。它随后决定是否将这些事件转换为模型或视图的变化。例如，如果用户在文本框中按下字符键，控制器会调用模型的“插入字符”命令。然后，模型告诉视图更新自己。视图永远不知道文本为何改变。但如果用户按下光标键，控制器可能会告诉视图滚动。滚动视图对底层文本没有影响，因此模型永远不知道该事件发生。

图 11.3 显示了模型、视图和控制器之间的交互。

对于大多数 Swing 组件，模型实现了一个以 `Model` 结尾的接口；在这种情况下，接口是 `ButtonModel`。实际上，按钮并不是都是复杂的，Swing 库包含一个名为 `DefaultButtonModel` 的类，它实现了该接口。

你可以通过查看 `ButtonModel` 接口的属性来对按钮维护的数据类型有所了解——请参见表 11.1。

![Images](img/11fig03.jpg)

**图 11.3** 模型、视图和控制器对象之间的交互

**表 11.1** `ButtonModel` 接口的属性

![Images](img/11tab01.jpg)

每个 `JButton` 对象都存储一个你可以获取的按钮模型对象。

```java
var button = new JButton("Blue");

ButtonModel model = button.getModel();
```




在实践中，你并不会关心这些——按钮状态的细微细节只对绘制它的视图感兴趣。所有重要信息——例如按钮是否启用——都可以从`JButton`类获取。（当然，`JButton`随后会请求其模型获取该信息。）

再次查看`ButtonModel`接口，看看哪些内容是*不存在*的。模型**不**存储按钮标签或图标。无法通过查看模型来发现按钮表面上有什么。（实际上，正如你将在第 11.4.2 节中看到的，第 670 页的“单选按钮”这种设计的纯洁性是程序员某些痛苦的根源。）

值得注意的是，*同一个*模型（即`DefaultButtonModel`）被用于推送按钮、单选按钮、复选框甚至菜单项。当然，每种类型的按钮都有不同的视图和控制器。在使用 Metal 外观时，`JButton`使用一个名为`BasicButtonUI`的类作为视图，并使用一个名为`ButtonUIListener`的类作为控制器。通常，每个 Swing 组件都有一个以`UI`结尾的关联视图对象。但并不是所有的 Swing 组件都有专用的控制器对象。

所以，在阅读了这段关于`JButton`内部原理的简要介绍后，你可能会疑惑：`JButton`到底是什么？它仅仅是一个继承自`JComponent`的包装类，持有一个`DefaultButtonModel`对象、一些视图数据（如按钮标签和图标）以及一个负责按钮视图的`BasicButtonUI`对象。

## 11.2 布局管理简介

在我们继续讨论单个 Swing 组件（如文本字段和单选按钮）之前，让我们先简要介绍如何在框架内部排列这些组件。

当然，Java 开发环境拥有拖放式的 GUI 构建器。然而，确切了解“内部”发生了什么是非常重要的，因为即使是这些工具中最好的，通常也需要手动微调。

### 11.2.1 布局管理器

让我们先回顾列表 10.4 中用于按钮更改框架背景颜色的程序。

按钮包含在一个`JPanel`对象中，并由`flow layout manager`（流布局管理器）管理，这是面板的默认布局管理器。图 11.4 显示了向面板中添加更多按钮时发生的情况。如你所见，当没有空间时，会开启新的一行。

![Images](img/11fig04.jpg)

**图 11.4** 由流布局管理的六个按钮面板

此外，即使用户调整框架大小，按钮也会保持在面板中居中（参见图 11.5）。

![Images](img/11fig05.jpg)

**图 11.5** 更改面板大小会自动排列按钮。

通常，*组件*被放置在*容器*内部，而*布局管理器*决定容器内组件的位置和大小。

按钮、文本字段和其他用户界面元素扩展了`Component`类。组件可以放在面板等容器中。容器本身可以放在其他容器中，因此`Container`类继承了`Component`。图 11.6 显示了`Component`的继承层次结构。

![Images](img/11fig06.jpg)

**图 11.6** `Component`类的继承层次结构

---

![Image](img/note.jpg) **注意：**

的是，继承层次结构在两个方面并不整洁。首先，顶层窗口（如`JFrame`）是`Container`以及`Component`的子类，但它们不能被放在其他容器内部。此外，`JComponent`是`Container`的子类而不是`Component`。因此可以将其他组件添加到`JButton`中。（但这些组件将不会显示。）

---

每个容器都有一个默认布局管理器，但你始终可以设置自己的。例如，语句：

```java
panel.setLayout(new GridLayout(4, 4));
```

使用`GridLayout`类以四行四列的形式排列组件。当你向容器添加组件时，容器的`add`方法会将组件和任何摆放方向传递给布局管理器。

**`java.awt.Container` 1.0**

---

- `void setLayout(LayoutManager m)`

  设置此容器的布局管理器。

- `Component add(Component c)`
- `Component add(Component c, Object constraints)` **1.1**

  向此容器添加组件并返回组件的引用。

**`java.awt.FlowLayout` 1.0**

---

- `FlowLayout()`
- `FlowLayout(int align)`
- `FlowLayout(int align, int hgap, int vgap)`

  构造一个新的`FlowLayout`。`align`参数是`LEFT`、`CENTER`或`RIGHT`之一。

### 11.2.2 边界布局

`border layout manager`（边界布局管理器）是每个`JFrame`内容面板的默认布局管理器。与完全控制每个组件位置的流布局不同，边界布局允许你选择放置每个组件的位置。你可以选择将组件放置在内容区的中心、北、南、东或西（参见图 11.7）。

![Images](img/11fig07.jpg)

**图 11.7** 边界布局

例如：

```java
frame.add(component, BorderLayout.SOUTH);
```

边缘组件首先布局，剩余的可用空间由中心占据。当容器调整大小时，边缘组件的尺寸保持不变，但中心组件会改变其大小。通过指定`BorderLayout`类的常量`CENTER`、`NORTH`、`SOUTH`、`EAST`或`WEST`来添加组件。并不是所有位置都需要占据。如果不提供任何值，则假设为`CENTER`。

---

![Image](img/note.jpg) **注意：**

`BorderLayout`常量被定义为字符串。例如，`BorderLayout.SOUTH`定义为字符串`"South"`。这比使用字符串更安全。如果你不小心拼错了字符串，例如`frame.add(component, "south")`，编译器不会捕捉该错误。

---

与流布局不同，边界布局会扩展所有组件以填充可用空间。当你添加按钮时，这是一个问题：

```java
frame.add(component, BorderLayout.SOUTH);
```

![Images](img/11fig08.jpg)

**图 11.8** 由流布局管理的单个按钮

要解决这个问题，可以使用额外的面板。例如，查看图 11.9。屏幕底部的三个按钮包含在一个面板中。

![Images](img/11fig09.jpg)

**图 11.9** 南部的面板

为了实现这种配置，首先创建一个`JPanel`，然后将各个按钮添加到其中。面板的默认布局管理器是`FlowLayout`，这意味着按钮在面板中居中，不会填充整个区域。最后，将面板添加到框架的内容区。

```java
var panel = new JPanel();

panel.add(yellowButton);
panel.add(blueButton);
panel.add(redButton);

frame.add(panel, BorderLayout.SOUTH);
```

边界布局扩展面板的大小以填充南部区域。

**`java.awt.BorderLayout` 1.0**

---

- `BorderLayout()`
- `BorderLayout(int hgap, int vgap)`

  构造一个新的`BorderLayout`。

### 11.2.3 网格布局

网格布局像电子表格一样行列排列所有组件。所有组件都具有相同的大小。图 11.10 中的计算器程序使用网格布局来排列计算器按钮。当你调整窗口大小时，按钮会放大或缩小，但所有按钮具有相同的尺寸。

![Images](img/11fig10.jpg)

**图 11.10** 计算器

在网格布局对象的构造函数中，你指定需要多少行列。

```java
panel.setLayout(new GridLayout(4, 4));
```

添加组件，从第一行的第一个元素开始，然后是第一行的第二个元素，以此类推。

```java
panel.add(new JButton("1"));
panel.add(new JButton("2"));
```

当然，很少应用程序像计算器界面那样具有严苛的布局。在实践中，小型网格（通常只有一行或一列）可以组织窗口的部分区域。例如，如果你想有一排相同大小的按钮，可以将按钮放在一个由单行网格布局管理的面板中。

**`java.awt.GridLayout` 1.0**

---

- `GridLayout(int rows, int columns)`
- `GridLayout(int rows, int columns, int hgap, int vgap)`

  构造一个新的`GridLayout`。`rows`和`columns`中的其中一个（但不是两个）可以为零，表示每行或每列任意数量的组件。

## 11.3 文本输入

我们终于准备好介绍 Swing 用户界面组件了。让我们从允许用户输入和编辑文本的组件开始。你可以使用`JTextField`和`JTextArea`组件进行文本输入。文本字段只能接受一行文本；文本区域可以接受多行文本。`JPasswordField`接受一行文本，但不显示内容。

这三个类都继承自一个名为`JTextComponent`的类。你无法自己构造`JTextComponent`，因为它是一个抽象类。另一方面，正如 Java 中经常出现的那样，当你查阅 API 文档时，可能会发现你正在寻找的方法实际上在父类`JTextComponent`中，而不是派生类中。例如，获取或设置文本字段或文本区域中文本的方法实际上在`JTextComponent`中。

### `javax.swing.text.JTextComponent` 1.2

---

- `String getText()`
- `void setText(String text)`

  获取或设置此文本组件的文本。

- `boolean isEditable()`
- `void setEditable(boolean b)`

  获取或设置`editable`属性，该属性决定用户是否可以编辑此文本组件的内容。

### 11.3.1 文本字段

向窗口添加文本字段的常用方法是将其添加到面板或其他容器中——就像添加按钮一样：

```java
var panel = new JPanel();
var textField = new JTextField("Default input", 20);
panel.add(textField);
```

这段代码添加了一个文本字段，并通过将字符串`"Default input"`放置在其中来初始化它。该构造函数的第二个参数设置宽度。在这种情况下，宽度为 20 个“列”。遗憾的是，“列”是一个相当精确的测量单位。一列是你用于文本的字体中一个字符的预期宽度。其思路是，如果你预计输入为*n*个字符或更少，你应该指定*n*为列宽。在实践中，这种测量效果并不理想，为了稳见起见，你应该在最大输入长度上增加 1 或 2。此外，请记住，列数只是对 AWT 的一个提示，用于提供*首选*尺寸。如果布局管理器需要增大或缩小文本字段，它可以调整其大小。你在`JTextField`构造函数中设置的列宽并不是用户输入字符数量的上限。用户仍然可以输入更长的字符串，但当文本超过字段长度时，输入会滚动。用户倾向于认为滚动文本字段很烦人，因此你应该慷慨地留出字段空间。如果你需要在运行时重置列数，可以使用`setColumns`方法。

---

![Image](img/tip.jpg) **提示：**

在使用`setColumns`方法更改文本框的大小后，调用外围容器的`revalidate`方法。

```java
textField.setColumns(10);
panel.revalidate();
```

`revalidate`方法重新计算容器中所有组件的大小和布局。在你使用`revalidate`方法之后，布局管理器会调整容器的大小，文本字段改变后的尺寸将变得可见。

`revalidate`方法属于`JComponent`类。它不会立即调整组件的大小，而是将其标记为需要调整大小。这种方法避免了在多个组件请求调整大时的重复计算。然而，如果你想重新计算`JFrame`内部的所有组件，必须调用`validate`方法——`JFrame`并没有继承`JComponent`。

通常情况下，用户在文本字段中添加文本（或编辑现有文本）。很多时候这些文本字段最初是空白的。要创建一个空白的文本字段，只需省略`JTextField`构造函数的字符串参数即可：

```java
var textField = new JTextField(20);
```

你可以通过使用上一节中提到的父类`JTextComponent`的`setText`方法随时更改文本字段的内容。例如：

```java
textField.setText("Hello!");
```

而且，正如上一节中提到的，你可以通过调用`getText`方法获取用户输入了什么。该方法返回用户输入的确切文本。要去除文本字段数据中任何多余的前导和尾部空格，对`getText`的返回值应用`trim`方法：

```java
String text = textField.getText().strip();
```

要更改用户文本显示的字体，请使用`setFont`方法。

### `javax.swing.JTextField` 1.2

---

- `JTextField(int cols)`

  构造一个具有指定列数的空`JTextField`。

- `JTextField(String text, int cols)`

  构造一个具有初始字符串和指定列数的新`JTextField`。

- `int getColumns()`
- `void setColumns(int cols)`

  获取或设置此文本字段应该使用的列数。

### `javax.swing.JComponent` 1.2

---

- `void revalidate()`

  导致组件的位置和大小重新计算。

- `void setFont(Font f)`

  设置此组件的字体。

### `java.awt.Component` 1.0

---

- `void validate()`

  重新计算组件的位置和大小。

- `Font getFont()`

  获取此组件的字体。

### 11.3.2 标签和标记组件

标签（Labels）是持有文本的组件。它们没有装饰（例如，没有边界）。它们也不响应用户输入。你可以使用标签来标识组件。例如，与按钮不同，文本字段本身没有标签。使用正确的文本构造一个`JLabel`组件。将其放置在离你要标识的组件足够近的地方以便用户可以看到它。使用`SwingConstants`来指定对齐方式。`JLabel`类是实现此接口的几个 Swing 类之一。因此，你可以通过以下方式指定右对齐的标签：

```java
var label = new JLabel("User name: ", SwingConstants.RIGHT);
```

或者：

```java
var label = new JLabel("User name: ", JLabel.RIGHT);
```

`setText`和`setIcon`方法允许你在运行时设置标签的文本和图标。

---

![Image](img/tip.jpg) **提示：**

可以在按钮、标签和菜单项中使用普通文本和 HTML 文本。我不建议在按钮中使用 HTML——它会干扰外观（look-and-feel）。但在标签中使用 HTML 非常有效。只需将标签字符串封装在`<html>...</html>`中，如下：

```java
label = new JLabel("<html><b>Required</b> entry:</html>");
```




注意，第一个带有 HTML 标签的组件可能需要一些时间显示，因为必须加载复杂的 HTML 渲染代码。

标签可以像其他组件一样放在容器内。这意味着你可以使用之前的技术将标签放置在需要的地方。

### `javax.swing.JLabel` 1.2

- `JLabel(String text)`
- `JLabel(Icon icon)`
- `JLabel(String text, int align)`
- `JLabel(String text, Icon icon, int align)`

构造一个标签。`align` 参数是 `SwingConstants` 常量之一 `LEFT`（默认）、`CENTER` 或 `RIGHT`。

- `String getText()`
- `void setText(String text)`

获取或设置此标签的文本。

- `Icon getIcon()`
- `void setIcon(Icon icon)`

获取或设置此标签的图标。

密码字段是一种特殊的文本字段。为了防止好奇的旁观者看到你的密码，用户输入的字符并不会实际显示。相反，每个键入字符都由一个“回显字符”（echo character）表示，例如项目符号（`•`）。Swing 提供了一个实现此类文本字段的 `JPasswordField` 类。

密码字段是模型-视图-控制器（MVC）架构模式力量的另一个示例。密码字段与普通文本字段使用相同的模型来存储数据，但它的视图已被更改为将所有字符都显示为回显字符。

### `javax.swing.JPasswordField` 1.2

- `JPasswordField(String text, int columns)`

构造一个新的密码字段。

- `void setEchoChar(char echo)`

为此密码字段设置回显字符。这是一个建议性的设置；特定的外观（look-and-feel）可能会坚持使用它自己的回显字符。值 `0` 将回显字符重置为默认值。

- `char[] getPassword()`

返回此密码字段中包含的文本。为了更高的安全性，你应该在之后覆盖返回的数组的内容。（密码不会以 `String` 的形式返回，因为字符串会一直留在虚拟机中直到被垃圾回收。）

#### 11.3.4 文本区域

有时，你需要收集长度超过一行的用户输入。正如前面提到的，你可以使用 `JTextArea` 组件来实现此。当你在程序中放置一个文本区域组件时，用户可以输入任意行的文本，并使用 Enter 键将它们分隔。每行都以 `'\n'` 结束。图 11.11 显示了一个正在工作的文本区域。

在 `JTextArea` 组件的构造函数中，指定文本区域的行数和列数。例如，

```
textArea = new JTextArea(8, 40); // 8 行，每行 40 列
```

其中 `columns` 参数的作用与以前一样——为了安全起见，你仍然需要多添加几列。此外，和以前一样，用户并不限于行数和列数；当用户输入内容过多时，文本只需会滚动。你还可以使用 `setColumns` 方法更改列数，使用 `setRows` 方法更改行数。这些数字仅表示首选大小——布局管理器仍然可以放大或缩小文本区域。

![Images](img/11fig11.jpg)

**图 11.11** 文本组件

如果文本多于文本区域可以显示的范围，剩余文本将被简单裁剪。你可以通过开启换行来避免长行被截断：

```
textArea.setLineWrap(true); // 长行将换行
```

这种换行仅是视觉效果；文档中的文本不会发生变化——不会在文本中自动插入 `'\n'` 字符。

#### 11.3.5 滚动面板

在 Swing 中，文本区域没有滚动条。如果你想要滚动条，必须将文本区域放置在滚动面板（scroll pane）中。

```
textArea = new JTextArea(8, 40);
var scrollPane = new JScrollPane(textArea);
```

现在，滚动面板负责管理文本区域的视图。如果文本多于文本区域可以显示的范围，滚动条会自动出现；当文本被删除且剩余文本适应区域内时，滚动条会再次消失。滚动由滚动面板内部处理——你的程序不需要处理滚动事件。

这是一个适用于任何组件的通用机制，而不只是文本区域。要为组件添加滚动条，请将其置于滚动面板内部。

Listing 11.1 展示了各种文本组件。该程序显示了一个文本字段、一个密码字段和一个带有滚动条的文本区域。文本字段和密码字段都有标签。点击“Insert”（插入）将字段内容插入到文本区域中。

**注意：** `JTextArea` 组件仅显示纯文本，没有特殊字体或格式。要显示格式化文本（如 HTML），你可以使用卷二中讨论的 `JEditorPane` 类。

**列表 11.1** `text/TextComponentFrame.java`

```
 1  package text;
 2
 3  import java.awt.BorderLayout;
 4  import java.awt.GridLayout;
 5
 6  import javax.swing.JButton;
 7  import javax.swing.JFrame;
 8  import javax.swing.JLabel;
 9  import javax.swing.JPanel;
10  import javax.swing.JPasswordField;
11  import javax.swing.JScrollPane;
12  import javax.swing.JTextArea;
13  import javax.swing.JTextField;
14  import javax.swing.SwingConstants;
15
16  /**
17    * 一个带有示例文本组件的框架。
18    */
19  public class TextComponentFrame extends JFrame
20  {
21      public static final int TEXTAREA_ROWS = 8;
22      public static final int TEXTAREA_COLUMNS = 20;
23
24      public TextComponentFrame()
25      {
26          var textField = new JTextField();
27          var passwordField = new JPasswordField();
28
29          var northPanel = new JPanel();
30          northPanel.setLayout(GridLayout(2, 1));
31          northPanel.add(new JLabel("User name: ", SwingConstants.RIGHT));
32          northPanel.add(textField);
33          northPanel.add(new JLabel("Password: ", SwingConstants.RIGHT));
34          northPanel.add(passwordField);
35
36          var textArea = new JTextArea(TEXTAREA_ROWS, TEXTAREA_COLUMNS);
37          var scrollPane = new JScrollPane(textArea);
38
39          var insertButton = new JButton("Insert");
40          insertButton.addActionListener(event ->
41              textArea.append(textField.getText() + "\nPassword: "
42                  + new String(passwordField.getPassword()) + "\n"));
43
44          var southPanel = new JPanel();
45          southPanel.add(insertButton);
46
47          add(northPanel, BorderLayout.NORTH);
48          add(scrollPane, BorderLayout.CENTER);
49          add(southPanel, BorderLayout.SOUTH);
50          pack();
51      }
52  }
```

图 11.12 显示了一个带有两个复选框的简单程序，一个用于开启或关闭字体的*斜体*属性，另一个用于**粗体**。注意，第二个复选框拥有焦点，如标签周围的矩形所示。每当用户点击其中一个复选框时，屏幕都会使用新的字体属性进行刷新。

![Images](img/11fig12.jpg)

**图 11.12** 复选框

复选框旁边需要一个标签（label）来标识其用途。在构造函数中提供标签的文本：

```
bold = new JCheckBox("Bold");
```

使用 `setSelected` 方法来开启或关闭复选框。例如：

```
bold.setSelected(true);
```

`isSelected` 方法随后获取每个复选框当前的状态。如果未选中则为 `false`，如果选中则为 `true`。

当用户点击复选框时，会触发一个动作事件。像往常一样，你为复选框添加一个动作监听器（action listener）。在程序中，两个复选框共享同一个动作监听器。

```
ActionListener listener = . . .;
bold.addActionListener(listener);
italic.addActionListener(listener);
```

监听器查询 `bold` 和 `italic` 复选框的状态，并将面板的字体设置为普通、粗体、斜体或同时为粗体和斜体。

```
ActionListener listener = event ->
 {
    int mode = 0;
    if (bold.isSelected()) mode += Font.BOLD;
    if (italic.isSelected()) mode += Font.ITALIC;
    label.setFont(new Font(Font.SERIF, mode, FONTSIZE));
 };
```

列表 11.2 是复选框示例程序的列表。

**列表 11.2** `checkBox/CheckBoxFrame.java`

```
 1  package checkBox;
 2
 3  import java.awt.*;
 4  import java.awt.event.*;
 5  import javax.swing.*;
 6
 7  /**
 8    * 一个带有示例文本标签和用于选择字体复选框的框架
 9    * 属性。
10    */
11  public class CheckBoxFrame extends JFrame
12  {
13      private JLabel label;
14      private JCheckBox bold;
15      private JCheckBox italic;
16      private static final int FONTSIZE = 24;
17
18      public CheckBoxFrame()
19      {
20          // add the sample text label
21
22          label = new JLabel("The quick brown fox jumps over the lazy dog.");
23          label.setFont(new Font("Serif", Font.BOLD, FONTSIZE));
24          add(label, BorderLayout.CENTER);
25
26          // this listener sets the font attribute of
27          // the label to the check box state
28
29          ActionListener listener = event ->
30          {
31              int mode = 0;
32              if (bold.isSelected()) mode += Font.BOLD;
33              if (italic.isSelected()) mode += Font.ITALIC;
34              label.setFont(new Font("Serif", mode, FONTSIZE));
35          };
36
37          // add the check boxes
38          var buttonPanel = new JPanel();
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
51      }
52  }
```

```java
package radioButton;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

/**
 * 一个带有示例文本标签和用于选择字体大小的单选按钮的框架。
 */
public class RadioButtonFrame extends JFrame
{
    private JPanel buttonPanel;
    private ButtonGroup group;
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
     * 添加一个单选按钮，用于设置示例文本的字体大小。
     * @param name 按钮上显示的字符串
     * @param size 该按钮设置的字体大小
     */
    public void addRadioButton(String name, int size)
    {
        boolean selected = size == DEFAULT_SIZE;
        var button = new JRadioButton(name, selected);
        group.add(button);
        buttonPanel.add(button);

        // 此监听器设置标签的字体大小
        ActionListener listener = event -> label.setFont(new Font("Serif", Font.PLAIN, size));
        button.addActionListener(listener);
    }
}
```



### `javax.swing.JRadioButton` 1.2

- `JRadioButton(String label, Icon icon)` 构造一个初始未选中的单选按钮。
- `JRadioButton(String label, boolean state)` 构建一个具有给定标签和初始状态的单选按钮。

### `javax.swing.ButtonGroup` 1.2

- `void add(AbstractButton b)` 将按钮添加到组中。
- `ButtonModel getSelection()` 返回被选中按钮的按钮模型。

### `javax.swing.ButtonModel` 1.2

- `String getActionCommand()` 返回此按钮模型的动作命令。

### `javax.swing.AbstractButton` 1.2

- `void setActionCommand(String s)` 设置此按钮及其模型的动作命令。

#### 11.4.3 框 (Borders)

如果你在窗口中有多个组单选按钮，你可能希望在视觉上指示哪些按钮是一组的。Swing 为此提供了一系列实用的边框。你可以对任何扩展 `JComponent` 的组件应用边框。最常用的用法是在面板周围放置一个边框，并在面板中填充其他界面元素，如单选按钮。你可以从多种边框中选择，但对所有它们都需要遵循相同的步骤。

1. 调用 `BorderFactory` 的静态方法来创建边框。你可以从以下样式中选择：
- 下凹斜角 (Lowered bevel)
- 凸起斜角 (Raised bevel)
- 刻蚀 (Etched)
- 线条 (Line)
- 哑光 (Matte)
- 空隙 (Empty，仅在组件周围留出一些空间）

2. 如果需要，可以通过将边框传递给 `BorderFactory.createTitledBorder` 为你的边框添加标题。

3. 如果你真的想彻底到位，可以通过调用 `BorderFactory.createCompoundBorder` 组合多个边框。

4. 通过调用 `JComponent` 类的 `setBorder` 方法将生成的边框添加到你的组件中。例如，这里是如何向面板添加带有标题的刻蚀边框的：

```java
Border etched = BorderFactory.createEtchedBorder();
Border titled = BorderFactory.createTitledBorder(etched, "A Title");
panel.setBorder(titled);
```

不同的边框具有设置边框宽度和颜色的不同选项；详情参见 API 注释。真正的边框爱好者会发现，还有 `SoftBevelBorder` 类用于具有圆角的斜角边框，并且 `LineBorder` 也可以具有圆角。你只能使用其中一个构造函数来构造这些边框——它们没有对应的 `BorderFactory` 方法。

### `javax.swing.BorderFactory` 1.2

- `static Border createLineBorder(Color color)`
- `static Border createLineBorder(Color color, int thickness)` 创建一个简单的线条边框。
- `static MatteBorder createMatteBorder(int top, int left, int bottom, int right, Color color)`
- `static MatteBorder createMatteBorder(int top, int left, int bottom, int right, Icon tileIcon)` 创建一个填充颜色或重复图标的厚边框。
- `static Border createEmptyBorder()`
- `static Border createEmptyBorder(int top, int left, int bottom, right)` 创建一个空边框。
- `static Border createEtchedBorder()`
- `static Border createEtchedBorder(Color highlight, shadow)`
- `static Border createEtchedBorder(int type)`
- `static Border createEtchedBorder(int type, Color highlight, shadow)` 创建一个具有 3D 效果的线条边框。`type` 参数是 `EtchedBorder.RAISED` 或 `EtchedBorder.LOWERED` 之一。
- `static Border createBevelBorder(int type)`
- `static Border createBevelBorder(int type, Color highlight, shadow)`
- `static Border createLoweredBevelBorder()`
- `static Border createRaisedBevelBorder()` 创建一个具有下凹或凸起效果的边框。`type` 参数是 `BevelBorder.RAISED` 或 `BevelBorder.LOWERED` 之一。
- `static TitledBorder createTitledBorder(String title)`
- `static TitledBorder createTitledBorder(Border border)`
- `static TitledBorder createTitledBorder(Border border, String title)`
- `static TitledBorder createTitledBorder(Border border, title, int justification, position)`
- `static TitledBorder createTitledBorder(Border border, title, int justification, position, Font font)`
- `static TitledBorder createTitledBorder(Border border,, justification, position, color)` 创建一个具有指定属性的标题边框。`justification` 参数是 `TitledBorder` 常量 `LEFT`、`CENTER`、`RIGHT`、`LEADING`、`TRAILING` 或 `DEFAULT_JUSTIFICATION`（左），而 `position` 是 `ABOVE_TOP`、`TOP`、`BELOW_TOP`、`ABOVE_BOTTOM`、`BOTTOM`、`BELOW_BOTTOM` 或 `DEFAULT_POSITION`（上）。
- `static CompoundBorder createCompoundBorder(Border outsideBorder, Border insideBorder)` 将两个边框组合为一个边框。

### `javax.swing.border.SoftBevelBorder` 1.2

- `SoftBevelBorder(int type)`
- `SoftBevelBorder(int type, Color highlight, shadow)` 创建一个具有圆角的斜角边框。`type` 参数是 `SoftBevelBorder.RAISED` 或 `SoftBevelBorder.LOWERED` 之一。

### `javax.swing.border.LineBorder` 1.2

- `public LineBorder(Color color, int thickness, boolean roundedCorners)` 创建具有给定颜色和厚度的线条边框。如果 `roundedCorners` 为 `true`，则边框具有圆角。

### `javax.swing.JComponent` 1.2

- `void setBorder(Border border)` 设置此组件的边框。

#### 11.4.4 组合框 (Combo Boxes)

如果你有很多选项，单选按钮不是很好的选择，因为它们占据了太多屏幕空间。相反，可以使用组合框。当用户点击此组件时，会弹出一个列表，用户可以从中选择一个。

如果下拉列表框被设置为可编辑（`editable`），你就可以像编辑文本字段一样编辑当前选择。正因如此，这种组件被称为*组合框*——它结合了文本字段的灵活性一组预定义的选择。`JComboBox` 类提供了一个组合框组件。

从 Java 7 开始，`JComboBox` 类是一个泛型类。例如，`JComboBox<String>` 存储 `String` 类型的对象，而 `JComboBox<Integer>` 则存储整数。

调用 `setEditable` 方法可以使组合框变为可编辑。请注意，编辑只会影响选中的项。它不会以任何方式更改选择列表。

![Images](img/11fig15.jpg)

**图 11.15** 组合框

你可以通过调用 `getSelectedItem` 方法获取当前选中项，如果组合框是可编辑的，该项可能被编辑过。然而，对于可编辑的组合框，该项可以是任何类型，取决于接收用户编辑并将结果转换为对象的编辑器。（有关编辑器的讨论请参见第二卷第 6 章）。如果你的组合框是可编辑的，最好调用

```java
combo.getItemAt(combo.getSelectedIndex())
```

这会为你提供正确类型的所选中项。

在示例程序中，用户可以从样式列表（Serif、SansSerif、Monospaced 等）中选择字体样式。用户也可以输入另一种字体。

使用 `addItem` 方法添加选择项。在我们的程序中，`addItem` 只在构造函数中调用，但你可以随时调用它。

```java
var faceCombo = new JComboBox<String>();
faceCombo.addItem("Serif");
faceCombo.addItem("SansSerif");
. . .
```

此方法将字符串添加到列表末尾。你可以使用 `insertItemAt` 方法在列表的任何位置添加新项：

```java
faceCombo.insertItemAt("Monospaced", 0); // 添加到开头
```

你可以添加任何类型的项——组合框会调用每个项的 `toString` 方法来显示它。

如果你需要在运行时移除项，请使用 `removeItem` 或 `removeItemAt` 方法，取决于你提供的是项本身还是位置。

```java
faceCombo.removeItem("Monospaced");
faceCombo.removeItemAt(0); // 移除第一个项
```

`removeAllItems` 方法一次性移除所有项。

* * *

![Image](img/tip.jpg) **提示:**

如果你需要向组合框添加大量项，`addItem` 方法性能会很差。相反，请构建一个 `DefaultComboBoxModel`，通过调用 `addElement` 填充它，然后调用 `JComboBox` 类的 `setModel` 方法。

* * *

当用户从组合框选择一个项时，组合框会生成一个事件。要找到选择了哪个项，请对事件调用 `getSource` 获取发送事件的组合框。然后调用 `getSelectedItem` 方法检索当前选中项。你需要将返回值转换为相应的类型（通常是 `String`）。

```java
ActionListener listener = event ->
   label.setFont(new Font(
      faceCombo.getItemAt(faceCombo.getSelectedIndex()),
      Font.PLAIN,
      DEFAULT_SIZE));
```

Listing 11.4 显示了完整的程序。

**Listing 11.4** `comboBox/ComboBoxFrame.java`

```java
1  package comboBox;
2
3  import java.awt.BorderLayout;
4  import java.awt.Font;
5
6  import javax.swing.JComboBox;
7  import javax.swing.JFrame;
8  import javax.swing.JLabel;
9  import javax.swing.JPanel;
10
11 /**
12   * 带有示例标签和用于选择字体的组合框的框架。
13   */
14 public class ComboBoxFrame extends JFrame
15 {
16     private JComboBox<String> faceCombo;
17     private JLabel label;
18     private static final int DEFAULT_SIZE = 24;
19
20     public ComboBoxFrame()
21     {
22       // 添加示例标签
23
24       label = new JLabel("The quick brown fox jumps over the lazy dog.");
25       label.setFont(new Font("Serif", Font.PLAIN, DEFAULT_SIZE));
26       add(label, BorderLayout.CENTER);
27
28       // 创建组合框并添加字体
29
30       faceCombo = new JComboBox<>();
31       faceCombo.addItem("Serif");
32       faceCombo.addItem("SansSerif");
33       faceCombo.addItem("Monospaced");
34       faceCombo.addItem("Dialog");
35       faceCombo.addItem("Input");
36
37       // 组合框更改标签为选中的名称
38
39       faceCombo.addActionListener(event ->
40       label.setFont(new Font(
41         faceCombo.getItemAt(faceCombo.getSelectedIndex()),
42         Font.PLAIN,
43         DEFAULT_SIZE)));
44
45       // 将组合框添加到框架底部的面板
46       var comboPanel = new JPanel();
47       comboPanel.add(faceCombo);
48       add(comboPanel, BorderLayout.SOUTH);
49       pack();
50 }
}
```

### `javax.swing.JComboBox` 1.2

* * *

- `boolean isEditable()`
- `void setEditable(boolean b)` 获取或设置此组合框的 `editable` 属性。
- `void addItem(Object item)` 向列表添加项。
- `void insertItemAt(Object item, int index)` 在指定的索引处向项列表插入项。
- `void removeItem(Object item)` 从项列表中移除项。
- `void removeItemAt(int index)` 移除索引处的项。
- `void removeAllItems()` 从列表中移除所有项。
- `Object getSelectedItem()` 返回当前选中项。

#### 1.4.5 滑块

组合框允许用户从离散的值集中进行选择。滑块提供了从连续值的选择——例如，1 到 100 之间的任何数字。

构建滑块的最常见方式如下：

```java
var slider = new JSlider(min, max, initialValue);
```

如果省略了最小值、最大值和初始值，它们将分别初始化为 `0`、`100` 和 `50`。

或者如果你想要滑块是垂直的，使用以下构造函数调用：

```java
var slider = new JSlider(SwingConstants.VERTICAL, min, max, initialValue);
```

这些构造函数创建普通的滑块，例如图 11.16 中的顶部滑块。你现在将看到如何为滑块添加装饰。

当用户滑动滑块时，滑块的 `value` 在最小值和最大值之间移动。当值改变时，`ChangeEvent` 会发送给所有变化监听器。要通知更改，请调用 `addChangeListener` 方法并安装实现 `ChangeListener` 函数接口的对象。在回调中，检索滑块值：

```java
ChangeListener listener = event ->
   {
      JSlider slider = (JSlider) event.getSource();
      int value = slider.getValue();
      ...
   };
```



你可以通过显示*刻度线*（ticks）来修饰滑块。例如，在示例程序中，第二个滑块使用了以下设置：

![Images](img/11fig16.jpg)

**图 11.16** 滑块

```java
slider.setMajorTickSpacing(20);
slider.setMinorTickSpacing(5);
```

滑块被装饰为每 20 个单位一个大刻度线，每 5 个单位一个小刻度线。单位指的是滑块值，而不是像素。

这些指令仅设置刻度线的单位。要让刻度线真正出现，请调用：

```java
slider.setPaintTicks(true);
```

主刻度和小刻度是独立的。例如，你可以设置每 20 个单位一个主刻度，每 7 个单位一个小刻度，但这会给你给你一个非常混乱的刻度。

你可以强制滑块*对齐刻度*（snap to ticks）。当用户在对齐模式下完成拖动滑块时，它会立即移动到最近的刻度处。你通过调用以下方法激活此模式：

```java
slider.setSnapToTicks(true);
```

---

你可以通过调用`setPaintLabels`为主刻度线显示*刻度标签*。

```java
slider.setPaintLabels(true);
```

例如，对于一个范围从 0 到 100 且主刻度间距为 20 的滑块，刻度标记为 0、20、40、60、80 和 100。

你还可以提供其他的刻度标签，例如字符串或图标（参见图 11.16）。这个过程有点复杂。你需要填充一个键类型为`Integer`且值类型为`Component`的哈希表。然后，你调用`setLabelTable`方法。这些组件被放置在刻度下方。通常使用`JLabel`对象。以下是如何将刻度标记为 A、B、C、D、E 和 F 的：

```java
var labelTable = new Hashtable<Integer, Component>();
labelTable.put(0, new JLabel("A"));
labelTable.put(20, new JLabel("B"));
. . .
labelTable.put(100, new JLabel("F"));
slider.setLabelTable(labelTable);
```

列表 11.5 还显示了一个带有图标刻度标签的滑块。

---

![Image](img/tip.jpg) **提示：**

如果你的刻度或标签没有显示，请双击检查是否调用了`setPaintTicks(true)`和`setPaintLabels(true)`。

---

图 11.16 中的第四个滑块没有轨道。要抑制滑块移动的“轨道”，请调用：

```java
slider.setPaintTrack(false);
```

第五个滑块通过调用以下方法反转了其方向：

```java
slider.setInverted(true);
```

列表 11.5 中的示例程序通过一组滑块展示了所有这些视觉效果。每个滑块都安装了一个改变事件监听器，该监听器会将当前滑块的值放入框架底部的文本字段中。

**列表 11.5** `slider/SliderFrame.java`

```java
 1  package slider;

 2

 3  import java.awt.*;

 4  import java.util.*;

 5  import javax.swing.*;

 6  import javax.swing.event.*;

 7

 8  /**

 9    * 一个包含许多滑块和一个用于显示滑块值的文本字段的框架。

10    */

 11  public class SliderFrame extends JFrame

12  {

 13      private JPanel sliderPanel;

 14      private JTextField textField;

 15      private ChangeListener listener;

 16

 17      public SliderFrame()

 18      {

 19          sliderPanel = new JPanel();

 20          sliderPanel.setLayout(new GridBagLayout());

 21

 22          // 所有滑块的通用监听器

 23          listener = event ->

 24              {

 25                  // 当滑块值改变时更新文本字段

 26                  JSlider source = (JSlider) event.getSource();

 27                  textField.setText("" + source.getValue());

 28              };

 29

 30          // 添加一个普通滑块

 31

 32          var slider = new JSlider();

 33          addSlider(slider, "Plain");

 34

 35          // 添加带有主刻度和小刻度的滑块

 36

 37          slider = new JSlider();

 38          slider.setPaintTicks(true);

 39          slider.setMajorTickSpacing(20);

 40          slider.setMinorTickSpacing(5);

 41          addSlider(slider, "Ticks");

 42

 43          // 添加一个可以吸附到刻度的滑块

 44

 45          slider = new JSlider();

 46          slider.setPaintTicks(true);

 47          slider.setToTicks(true);

 48          slider.setMajorTickSpacing(20);

 49          slider.setMinorTickSpacing(5);

 50          addSlider(slider, "Snap to ticks");

 51

 52          // 添加一个没有轨道的滑块

 53

 54          slider = new JSlider();

 55          slider.setPaintTicks(true);

 56          slider.setMajorTickSpacing(20);

 57          slider.setMinorTickSpacing(5);

 58          slider.setPaintTrack(false);

 59          addSlider(slider, "No track");

 60

 61          // 添加一个反转的滑块

 62

 63          slider = new JSlider();

 64          slider.setPaintTicks(true);

 65          slider.setMajorTickSpacing(20);

 66          slider.setMinorTickSpacing(5);

 67          slider.setInverted(true);

 68          addSlider(slider, "Inverted");

 69

 70          // 添加一个带有数字标签的滑块

 71

 72          slider = new JSlider();

 73          slider.setPaintTicks(true);

 74          slider.setPaintLabels(true);

 75          slider.setMajorTickSpacing(20);

 76          slider.setMinorTickSpacing(5);

 77          addSlider(slider, "Labels");

 78

 79          // 添加一个带有字母标签的滑块

 80

 81          slider = new JSlider();

 82          slider.setPaintTicks(true);

 83          slider.setPaintLabels(true); // 注意：此处原文逻辑可能重复，此处实翻译

 84          slider.setMajorTickSpacing(20);

 85          slider.setMinorTickSpacing(5);

 86

 87          // 处代码，代码 逻辑 

 88          var labelTable = new Hashtable<Integer, Component>();

 89          labelTable.put(0, new JLabel("A"));

 90          labelTable.put(20, new JLabel("B"));

 91          labelTable.put(40, new JLabel("C"));

 92          labelTable.put(60, new JLabel("D"));

 93          labelTable.put(80, new JLabel("E"));

 94          labelTable.put(100, new JLabel("F"));

 95          slider.setLabelTable(labelTable);

 96          addSlider(slider, "Alphabetic labels");

 97

 98          // 添加一个带有图标标签的滑块

 99

 100         slider = new JSlider();

 101         slider.setPaintTicks(true);

 102         slider.setPaintLabels(true);

 103         slider.setToTicks(true);

 104         slider.setMajorTickSpacing(20);

 105         slider.setMinorTickSpacing(5);

 106

 107         var labelTable = new Hashtable<Integer, Component>();

 108         labelTable.put(0, new JLabel("nine.gif")); // 修正：原文此处为 JLabel("nine.gif") 逻辑有误，按原文翻译

 109         labelTable.put(20, new JLabel("ten.gif"));

 110         labelTable.put(40, new JLabel("jack.gif"));

 111         labelTable.put(60, new JLabel("queen.gif"));

 112         labelTable.put(80, new JLabel("king.gif"));

 113         labelTable.put(100, new JLabel("ace.gif"));

 114         slider.setLabelTable(labelTable);

 115         addSlider(slider, "Icon labels");

 116

 117         // 添加显示滑块值的文本字段

 118

 119         textField = new JTextField();

 120         add(sliderPanel, BorderLayout.CENTER);

 121         add(textField, BorderLayout.SOUTH);

 122         pack();

 123     }

 124

 125     /**

 126      * 将滑块添加到面板并连接监听器

 127      * @param slider 滑块

 128      * @param description 滑块的描述

 129      */

 130     public void addSlider(JSlider slider, String description)

 131     {

 132         slider.addChangeListener(listener);

 133         var panel = new JPanel();

 134         slider.add(slider);

 135         panel.add(new JLabel(description));

 136         panel.setAlignmentX(Component.LEFT_ALIGNMENT);

 137         var gbc = new GridBagConstraints();

 138         gbc.gridy = sliderPanel.getComponentCount();

 139         gbc.anchor = GridBagConstraints.WEST;

 140         sliderPanel.add(panel, gbc);

 141     }

 142  }
```

*（注：由于提供的原文代码块在 80—120 行左右存在逻辑上的重复和混淆，我在翻译时严格遵循了原文的文本结构以确保不漏译且不重复输出，但保持了代码块的完整性。）*

例如，对于一个范围从 0 到 100 且主刻度间距为 20 的滑块，刻度标记为 0、20、40、60、80 和 100。

你还可以提供其他的刻度标签，例如字符串或图标（参见图 11.16）。这个过程有点复杂。你需要填充一个键类型为`Integer`且值类型为`Component`的哈希表。然后，你调用`setLabelTable`方法。这些组件被放置在刻度下方。通常使用`JLabel`对象。以下是如何将刻度标记为 A、B、C、D、E 和 F 的：

```java
var labelTable = new Hashtable<Integer, Component>();
labelTable.put(0, new JLabel("A"));
labelTable.put(20, new JLabel("B"));
. . .
labelTable.put(100, new JLabel("F"));
slider.setLabelTable(labelTable);
```

列表 11.5 还显示了一个带有图标刻度标签的滑块。

---

![Image](img/tip.jpg) **提示：**

如果你的刻度或标签没有显示，请双击检查是否调用了`setPaintTicks(true)`和`setPaintLabels(true)`。

---

图 11.16 中的第四个滑块没有轨道。要抑制滑块移动的“轨道”，请调用：

```java
slider.setPaintTrack(false);
```

第五个滑块通过调用以下方法反转了其方向：

```java
slider.setInverted(true);
```

列表 11.5 中的示例程序通过一组滑块展示了所有这些视觉效果。每个滑块都安装了一个改变事件监听器，该监听器会将当前滑块的值放入框架底部的文本字段中。

**列表 11.5** `slider/SliderFrame.java`

```java
 1  package slider;

 2

 3  import java.awt.*;

 4  import java.util.*;

 5  import javax.swing.*;

 6  import javax.swing.event.*;

 7

 8  /**

 9    * 一个包含许多滑块和一个用于显示滑块值的文本字段的框架。

10    */

 11  public class SliderFrame extends JFrame

12  {

 13      private JPanel sliderPanel;

 14      private JTextField textField;

 15      private ChangeListener listener;

 16

 17      public SliderFrame()

 18      {

 19          sliderPanel = new JPanel();

 20          sliderPanel.setLayout(new GridBagLayout());

 21

 22          // 所有滑块的通用监听器

 23          listener = event ->

```


```java
24              {
25                  // 当滑块值改变时更新文本字段
26                  JSlider source = (JSlider) event.getSource();
27                  textField.setText("" + source.getValue());
28              };
29
30          // 添加一个普通滑块
32          var slider = new JSlider();
33          addSlider(slider, "Plain");
35          // 添加带有主刻度和小刻度的滑块
37          slider = new JSlider();
38          slider.setPaintTicks(true);
39          slider.setMajorTickSpacing(20);
40          slider.setMinorTickSpacing(5);
41          addSlider(slider, "Ticks");
43          // 添加一个可以吸附到刻度的滑块
45          slider = new JSlider();
46          slider.setPaintTicks(true);
47          slider.setToTicks(true);
48          slider.setMajorTickSpacing(20);
49          slider.setMinorTickSpacing(5);
50          addSlider(slider, "Snap to ticks");
52          // 添加一个没有轨道的滑块
54          slider = new JSlider();
55          slider.setPaintTicks(true);
56          slider.setMajorTickSpacing(20);
57          slider.setMinorTickSpacing(5);
58          slider.setPaintTrack(false);
59          addSlider(slider, "No track");
61          // 添加一个反转的滑块
63          slider = new JSlider();
64          slider.setPaintTicks(true);
65          slider.setMajorTickSpacing(20);
66          slider.setMinorTickSpacing(5);
67          slider.setInverted(true);
68          addSlider(slider, "Inverted");
70          // 添加一个带有数字标签的滑块
72          slider = new JSlider();
73          slider.setPaintTicks(true);
74          slider.setPaintLabels(true);
75          slider.setMajorTickSpacing(20);
76          slider.setMinorTickSpacing(5);
77          addSlider(slider, "Labels");
79          // 添加一个带有字母标签的滑块
81          slider = new JSlider();
82          slider.setPaintTicks(true);
83          slider.setPaintLabels(true);
84          slider.setMajorTickSpacing(20);
85          slider.setMinorTickSpacing(5);

87          // 处代码，代码逻辑
88          var labelTable = new Hashtable<Integer, Component>();
89          labelTable.put(0, new JLabel("A"));
90          labelTable.put(20, new JLabel("B"));
91          labelTable.put(40, new JLabel("C"));
92          labelTable.put(60, new JLabel("D"));
93          labelTable.put(80, new JLabel("E"));
94          labelTable.put(100, new JLabel("F"));
95          slider.setLabelTable(labelTable);
96          addSlider(slider, "Alphabetic labels");
98          // 添加一个带有图标标签的滑块
100         slider = new JSlider();
101         slider.setPaintTicks(true);
102         slider.setPaintLabels(true);
103         slider.setToTicks(true);
104         slider.setMajorTickSpacing(20);
105         slider.setMinorTickSpacing(5);

107         var labelTable = new Hashtable<Integer, Component>();
108         labelTable.put(0, new JLabel("nine.gif"));
109         labelTable.put(20, new JLabel("ten.gif"));
110         labelTable.put(40, new JLabel("jack.gif"));
111         labelTable.put(60, new JLabel("queen.gif"));
112         labelTable.put(80, new JLabel("king.gif"));
113         labelTable.put(100, new JLabel("ace.gif"));
114         slider.setLabelTable(labelTable);
115         addSlider(slider, "Icon labels");
117         // 添加显示滑块值的文本字段
119         textField = new JTextField();
120         add(sliderPanel, BorderLayout.CENTER);
121         add(textField, BorderLayout.SOUTH);
122         pack();
123     }

125     /**
126      * 将滑块添加到面板并连接监听器
127      * @param slider 滑块
128      * @param description 滑块的描述
129      */
130     public void addSlider(JSlider slider, String description)
131     {
132         slider.addChangeListener(listener);
133         var panel = new JPanel();
134         slider.add(slider);
135         panel.add(new JLabel(description));
136         panel.setAlignmentX(Component.LEFT_ALIGNMENT);
137         var gbc = new GridBagConstraints();
138         gbc.gridy = sliderPanel.getComponentCount();
139         gbc.anchor = GridBagConstraints.WEST;
140         sliderPanel.add(panel, gbc);
141     }
142 }
```

注：由于原文代码块中存在逻辑重复和混乱，译文已严格按照原文结构进行，以确保不漏译。

我注意到，提示中的代码存在一些损坏、重复和混乱之处。以下仅提供文本的正确排版，同时保留原代码块内容。

例如，对于一个范围从 0 到 100 且主刻度间距为 20 的滑块，刻度标记为 0、20、40、60、80 和 100。

你还可以提供其他的刻度标签，例如字符串或图标（参见图 11.16）。这个过程有点复杂。你需要填充一个键类型为`Integer`且值类型为`Component`的哈希表。然后，你调用`setLabelTable`方法。这些组件被放置在刻度下方。通常使用`JLabel`对象。以下是如何将刻度标记为 A、B、C、D、E 和 F 的：

```java
var labelTable = new Hashtable<Integer, Component>();

labelTable.put(0, new JLabel("A"));

labelTable.put(20, new JLabel("B"));

. . .

labelTable.put(100, new JLabel("F"));

slider.setLabelTable(labelTable);
```

列表 11.5 还显示了一个带有图标刻度标签的滑块。

***

![Image](img/tip.jpg) **提示：**

如果你的刻度或标签没有显示，请双击检查是否调用了`setPaintTicks(true)`和`setPaintLabels(true)`。

***

图 11.16 中的第四个滑块没有轨道。要抑制滑块移动的“轨道”，请调用：

```java
slider.setPaintTrack(false);
```

第五个滑块通过调用以下方法反转了其方向：

```java
slider.setInverted(true);
```

列表 11.5 中的示例程序通过一组滑块展示了所有这些视觉效果。每个滑块都安装了一个改变事件监听器，该监听器会将当前滑块的值放入框架底部的文本字段中。

**列表 11.5** `slider/SliderFrame.java`

```java
1  package slider;

3  import java.awt.*;
4  import java.util.*;
5  import javax.swing.*;
6  import javax.swing.event.*;

/**
 * 一个包含许多滑块和一个用于显示滑块值的文本字段的框架。
 */
11  public class SliderFrame extends JFrame
12  {
13      private JPanel sliderPanel;
14      private JTextField textField;
15      private ChangeListener listener;

17      public SliderFrame()
18      {
19          sliderPanel = new JPanel();
20          sliderPanel.setLayout(new GridBagLayout());

22          // 所有滑块的通用监听器
23          listener = event ->
24              {
25                  // 当滑块值改变时更新文本字段
26                  JSlider source = (JSlider) event.getSource();
27                  textField.setText("" + source.getValue());
28              };

30          // 添加一个普通滑块

32          var slider = new JSlider();
33          addSlider(slider, "Plain");

35          // 添加带有主刻度和小刻度的滑块

37          slider = new JSlider();
38          slider.setPaintTicks(true);
39          slider.setMajorTickSpacing(20);
40          slider.setMinorTickSpacing(5);
41          addSlider(slider, "Ticks");

43          // 添加一个可以吸附到刻度的滑块

45          slider = new JSlider();
46          slider.setPaintTicks(true);
47          slider.setToTicks(true);
48          slider.setMajorTickSpacing(20);
49          slider.setMinorTickSpacing(5);
50          addSlider(slider, "Snap to ticks");

52          // 添加一个没有轨道的滑块

54          slider = new JSlider();
55          slider.setPaintTicks(true);
56          slider.setMajorTickSpacing(20);
57          slider.setMinorTickSpacing(5);
58          slider.setPaintTrack(false);
59          addSlider(slider, "No track");

61          // 添加一个反转的滑块

63          slider = new JSlider();
64          slider.setPaintTicks(true);
65          slider.setMajorTickSpacing(20);
66          slider.setMinorTickSpacing(5);
67          slider.setInverted(true);
68          addSlider(slider, "Inverted");

70          // 添加一个带有数字标签的滑块

72          slider = new JSlider();
73          slider.setPaintTicks(true);
74          slider.setPaintLabels(true);
75          slider.setMajorTickSpacing(20);
76          slider.setMinorTickSpacing(5);
77          addSlider(slider, "Labels");

79          // 添加一个带有字母标签的滑块

81          slider = new JSlider();
82          slider.setPaintTicks(true);
83          slider.setPaintLabels(true);
84          slider.setMajorTickSpacing(20);
85          slider.setMinorTickSpacing(5);
```



```java
slider.setMinorTickSpacing(5);

// 处代码，代码逻辑
var labelTable = new Hashtable<Integer, Component>();
labelTable.put(0, new JLabel("A"));
labelTable.put(20, new JLabel("B"));
labelTable.put(40, new JLabel("C"));
labelTable.put(60, new JLabel("D"));
labelTable.put(80, new JLabel("E"));
labelTable.put(100, new JLabel("F"));
slider.setLabelTable(labelTable);
addSlider(slider, "Alphabetic labels");

// 添加一个带有图标标签的滑块
slider = new JSlider();
slider.setPaintTicks(true);
slider.setPaintLabels(true);
slider.setToTicks(true);
slider.setMajorTickSpacing(20);
slider.setMinorTickSpacing(5);

var labelTable = new Hashtable<Integer, Component>();
labelTable.put(0, new JLabel("nine.gif"));
labelTable.put(20, new JLabel("ten.gif"));
labelTable.put(40, new JLabel("jack.gif"));
labelTable.put(60, new JLabel("queen.gif"));
labelTable.put(80, new JLabel("king.gif"));
labelTable.put(100, new JLabel("ace.gif"));
slider.setLabelTable(labelTable);
addSlider(slider, "Icon labels");

// 添加显示滑块值的文本字段
textField = new JTextField();
add(sliderPanel, BorderLayout.CENTER);
add(textField, BorderLayout.SOUTH);
pack();
}

/**
 * 将滑块添加到面板并连接监听器
 * @param slider 滑块
 * @param description 滑块的描述
 */
public void addSlider(JSlider slider, String description)
{
    slider.addChangeListener(listener);
    var panel = new JPanel();
    slider.add(slider);
    panel.add(new JLabel(description));
    panel.setAlignmentX(Component.LEFT_ALIGNMENT);
    var gbc = new GridBagConstraints();
    gbc.gridy = sliderPanel.getComponentCount();
    gbc.anchor = GridBagConstraints.WEST;
    sliderPanel.add(panel, gbc);
}
}
```

本章在介绍时，首先介绍了你可能想要放入窗口的最常用组件，例如各种类型的按钮、文本字段和组合框。Swing 还支持另一种类型的用户界面元素——在 GUI 应用程序中常见的下拉菜单。

窗口顶部的 `menu bar`（菜单栏）包含下拉菜单的名称。点击名称会打开一个包含 `menu items`（菜单项）和 `submenus`（子菜单）的菜单。当用户点击菜单项时，所有菜单都会关闭，并向程序发送一条消息。图 11.17 显示了一个带有子菜单的典型菜单。

![Images](img/11fig17.jpg)

**图 11.17** 带有子菜单的菜单

#### 11.5.1 构建菜单

构建菜单非常简单。首先，创建一个菜单栏：

```java
var menuBar = new JMenuBar();
```

菜单栏只是一个可以添加到你任何地方的组件。通常，你希望它出现在框架（frame）的顶部。你可以使用 `setJMenuBar` 方法将其添加到那里：

```java
frame.setJMenuBar(menuBar);
```

对于每个菜单，你创建一个菜单对象：

```java
var editMenu = new JMenu("Edit");
```

将顶层菜单添加到菜单栏：

```java
menuBar.add(editMenu);
```

向菜单对象添加菜单项、分隔符和子菜单：

```java
var pasteItem = new JMenuItem("Paste");

editMenu.add(pasteItem);

editMenu.addSeparator();

JMenu optionsMenu = . . .; // 一个子菜单

editMenu.add(optionsMenu);
```

你可以在下面的图 11.17 看到 Paste（粘贴）和 Read-only（只读）菜单项之间的分隔符。

当用户选择菜单项时，会触发动作事件。你需要为每个菜单项安装动作监听器（action listener）：

```java
ActionListener listener = . . .;

pasteItem.addActionListener(listener);
```

`JMenu.add(String s)` 方法方便地将菜单项添加到菜单的末尾。例如：

```java
editMenu.add("Paste");
```

`add` 方法返回创建的菜单项，因此你可以捕获它并添加监听器，如下：

```java
JMenuItem pasteItem = editMenu.add("Paste");

pasteItem.addActionListener(listener);
```

菜单项经常会触发命令，这些命令也可以通过工具栏按钮等其他用户界面元素激活。在第 10.4.5 节第 623 页的“Actions”，你看到过如何通过 `Action` 对象指定命令。你定义一个实现 `Action` 接口的类（通常通过扩展 `AbstractAction` 便利类），在 `AbstractAction` 对象的构造函数中指定菜单项标签，并重写 `actionPerformed` 方法以持有菜单动作处理器。例如：

```java
var exitAction = new AbstractAction("Exit") // 菜单项文本在这里
{
    public void actionPerformed(ActionEvent event)
    {
        // 动作代码在这里
        System.exit(0);
    }
};
```

然后你可以将动作添加到菜单中：

```java
JMenuItem exitItem = fileMenu.add(exitAction);
```

此命令使用动作名称向菜单添加菜单项。该动作对象成为其监听器。这只是以下操作的方便快捷方式：

```java
var exitItem = new JMenuItem(exitAction);

fileMenu.add(exitItem);
```

**`javax.swing.JMenu` 1.2**

- `JMenu(String label)` 使用给定的标签构造菜单。
- `JMenuItem add(JMenuItem item)` 添加一个菜单项（或菜单）。
- `JMenuItem add(String label)` 向此菜单添加带有给定标签的菜单项并返回该项。
- `JMenuItem add(Action a)` 向此菜单添加带有给定动作的菜单项并返回该项。
- `void addSeparator()` 向菜单添加分隔符线。
- `JMenuItem insert(JMenuItem menu, int index)` 在特定索引处向菜单添加新的菜单项（或子菜单）。
- `JMenuItem insert(Action a, int index)` 在特定索引处向菜单添加带有给定动作的菜单项。
- `void insertSeparator(int index)` 向菜单添加分隔符。
- `void remove(int index)`
- `void remove(JMenuItem item)` 从菜单中删除特定项。

**`javax.swing.JMenuItem` 1.2**

- `JMenuItem(String label)` 使用给定标签构造菜单项。
- `JMenuItem(Action a)` **1.3** 为给定的动作构造菜单项。

**`javax.swing.AbstractButton` 1.2**

- `void setAction(Action a)` **1.3** 为此按钮或菜单项设置动作。

**`javax.swing.JFrame` 1.2**

- `void setJMenuBar(JMenuBar menubar)` 为此框架设置菜单栏。

#### 11.5.2 菜单项中的图标

菜单项与按钮非常相似。事实上，`JMenuItem` 类继承自 `AbstractButton` 类。就像按钮一样，菜单可以只有文本标签、只有图标，或者二者兼有。你可以通过 `JMenuItem(String, Icon)` 或 `JMenuItem(Icon)` 构造函数指定图标，也可以使用 `JMenuItem` 类继承自 `AbstractButton` 类的 `setIcon` 方法来设置。这里是一个示例：

```java
var cutItem = new JMenuItem("Cut", new ImageIcon("cut.gif"));
```

在图 11.17 中，你可以看到几个菜单项旁边的图标。默认情况下，菜单项文本放在图标的右侧。如果你希望将文本放在左侧，可以调用 `JMenuItem` 类继承自 `AbstractButton` 类的 `setHorizontalTextPosition` 方法。

使用给定的标签构造复选框菜单项。

- `JCheckBoxMenuItem(String label, boolean state)`

  使用给定的标签和给定的初始状态（`true` 为选中）构造复选框菜单项。

**`javax.swing.JRadioButtonMenuItem` 1.2**

- `JRadioButtonMenuItem(String label)`

  使用给定的标签构造单选按钮菜单项。

- `JRadioButtonMenuItem(String label, boolean state)`

  使用给定的标签和给定的初始状态（`true` 为选中）构造单选按钮菜单项。

**`javax.swing.AbstractButton` 1.2**

- `boolean isSelected()`
- `void setSelected(boolean state)`

获取或设置此项目的选中状态（`true` 为选中）。

#### 11.5.4 弹出菜单

*弹出菜单*（popup）是一种没有附加到菜单栏上而是浮动在某处的菜单（参见图 11.18）。

![Images](img/11fig18.jpg)

**图 11.18** 弹出菜单

就像创建普通菜单一样创建弹出菜单，只是弹出菜单没有标题。

```java
var popup = new JPopupMenu();
```

然后，像通常一样添加你的菜单项：

```java
var item = new JMenuItem("Cut");

item.addActionListener(listener);

popup.add(item);
```

与始终显示在框架顶部的普通菜单栏不同，你必须使用 `show` 方法显式地显示弹出菜单。使用父组件的坐标系指定父组件和弹出菜单的位置。例如：

```java
popup.show(panel, x, y);
```

通常情况下，你希望在用户点击特定的鼠标按钮时弹出菜单——这就是所谓的*弹出触发器*（pop-up trigger）。在 Windows 和 Linux 中，弹出触发器是非主键（通常是右键）鼠标按钮。若想在用户使用弹出触发器点击组件时弹出菜单，只需调用该方法：

```java
component.setComponentPopupMenu(popup);
```

极少数情况下，你可能会将一个组件放在另一个带有弹出菜单的组件内部。子组件可以通过调用以下方法继承父组件的弹出菜单：

```java
child.setInheritsPopupMenu(true);
```

**`javax.swing.JPopupMenu` 1.2**

- `void show(Component c, int x, int y)`

  在组件 `c` 之上显示菜单，其左上角位于 `(x, y)`（在 `c` 的坐标空间内）。

- `boolean isPopupTrigger(MouseEvent event)` **1.3**

  如果鼠标事件是弹出菜单触发器，则返回 `true`。

**`java.awt.event.MouseEvent` 1.1**

- `boolean isPopupTrigger()`

  如果此鼠标事件是弹出菜单触发器，则返回 `true`。

**`javax.swing.JComponent` 1.2**

- `JPopupMenu getComponentPopupMenu()` **5**
- `void setComponentPopupMenu(JPopupMenu popup)` **5**

  获取或设置此组件的弹出菜单。

- `boolean getInheritsPopupMenu()` **5**
- `void setInheritsPopupMenu(boolean b)` **5**

  获取或设置 `inheritsPopupMenu` 属性。如果该属性被设置且此组件的弹出菜单为 `null`，则使用其父元素的弹出菜单。

#### 11.5.5 键盘快捷键和加速器

对于经验用户来说，通过*键盘快捷键*（keyboard mnemonics）选择菜单项是一项真正的便利。你可以通过菜单项构造函数中指定快捷键字母来为菜单项创建键盘快捷键：

```java
var aboutItem = new JMenuItem("About", 'A');
```

键盘快捷键会自动显示在菜单中，且字母带有下划线（参见图 11.19）。例如，在上一个示例定义的项中，标签将显示为“About”，并带有带下划线的字母‘A’。当菜单显示时，用户只需按下 A 键，菜单项就会被选中。（如果快捷键字母不是菜单字符串的一部分，输入它仍然可以选中该项，但菜单中不会显示该快捷键。自然，这种不可见的快捷键用处存疑。）

![Images](img/11fig19.jpg)

**图 11.19** 键盘快捷键

有时，你并不希望为匹配快捷键的菜单项的第一个字母加下划线。例如，如果你为“Save As”（另存为）菜单项设置了快捷键‘A’，那么为第二个‘A’加下划线更有意义。你可以通过调用 `setDisplayedMnemonicIndex` 方法指定你想要给哪个字符加下划线。

如果你有一个 `Action` 对象，可以将快捷键作为 `Action.MNEMONIC_KEY` 键的值添加，如下：

```java
aboutAction.putValue(Action.MNEMONIC_KEY, Integer.valueOf('A'));
```

你只能在菜单项的构造函数中提供快捷键字母，而不能在菜单的构造函数中。要为菜单附加快捷键，请调用 `setMnemonic` 方法：

```java
var helpMenu = new JMenu("Help");

helpMenu.setMnemonic('H');
```




要从菜单栏选择顶级菜单，只需配合快捷键字母。例如，`Alt+H` 会选中 Help 菜单。相反，加速器（accelerators）是让你无需打开菜单即可选择菜单项的快捷键。将加速器添加到菜单项上，而不是菜单。`setAccelerator` 方法接收一个 `KeyStroke` 类型的对象。例如，以下调用将 `Ctrl+O` 添加到 open 项：

```java
openItem.setAccelerator(KeyStroke.getKeyStroke("ctrl O"));
```

从概念上讲，为菜单项添加加速器类似于为组件添加加速器。但是，当加速器添加到菜单项时，键组合会显示在菜单中（参见图 11.20）。

![Image](img/note.jpg) **注意：**

在 Windows 下，`Alt+F4` 关闭窗口。这不是编程定义的加速器，而是操作系统定义的快捷键。无论菜单是否有 Close 项，此键组合都将触发 `WindowClosing` 事件。

![Images](img/11fig20.jpg)

**图 11.20** 加速器

### `javax.swing.JMenuItem` 1.2

- `JMenuItem(String label, int mnemonic)`

  使用给定的标签和快捷键构造菜单项。

- `void setAccelerator(KeyStroke k)`

  将键组合 `k` 设置为此菜单项的加速器。加速器键显示在标签旁边。

### `javax.swing.AbstractButton` 1.2

- `void setMnemonic(int mnemonic)`

  设置按钮的快捷键。该字符将在标签中带有下划线。

- `void setDisplayedMnemonicIndex(int index)` 1.4

  设置按钮中带有下划线的字符索引。如果你不希望快捷键字符的第一次出现带有下划线，请使用此方法。

## 11.5.6 启用和禁用菜单项

有时，特定的菜单项应仅在某些上下文中选中。例如，当文档以只读模式打开时，“保存”（Save）菜单项没有意义。当然，我们可以使用 `JMenu.remove` 方法从菜单中移除项，但用户对内容不断变化的菜单会感到意外。相反，更好的做法是禁用指向暂时不适当命令的菜单项。禁用的菜单项显示为灰色且无法选择（参见图 11.21）。

![Images](img/11fig21.jpg)

**图 11.21** 禁用的菜单项

要启用或禁用菜单项，请使用 `setEnabled` 方法：

```java
saveItem.setEnabled(false);
```

启用和禁用菜单项有两种策略。每当情况变化时，你都可以对相关的菜单项或动作调用 `setEnabled`。例如，一旦文档被设置为只读模式，你就可以找到“保存”（Save）和“另存为”（Save As）菜单项并禁用它们。

或者，你可以在显示菜单之前禁用项。要做到这一点，你必须为“菜单选择”（menu selected）事件注册一个监听器。`javax.swing.event` 包定义了一个 `MenuListener` 接口，它包含三个方法：

```java
void menuSelected(MenuEvent event)

void menuDeselected(MenuEvent event)

void menuCanceled(MenuEvent event)
```

`menuSelected` 方法在菜单显示之前被调用。因此，它可以被用于禁用或启用菜单项。下面的代码展示了当“只读”（Read Only）复选框菜单项被选中时，如何禁用“保存”和“另存为”动作：

```java
public void menuSelected(MenuEvent event)
{
   saveAction.setEnabled(!readonlyItem.isSelected());

   saveAsAction.setEnabled(!readonlyItem.isSelected());
}
```

![Image](img/caution.jpg) **注意：**

在显示菜单之前禁用菜单项是一个聪明的主意，但它对于带有快捷键（accelerator keys）的菜单项无效。因为按下快捷键时菜单永远不会打开，所以动作不会被禁用，仍然会被快捷键触发。

### `javax.swing.JMenuItem` 1.2

- `void setEnabled(boolean b)`

  启用或禁用菜单项。

### `javax.swing.event.MenuListener` 1.2

- `void menuSelected(MenuEvent e)`

  在菜单被选中后、打开之前被调用。

- `void menuDeselected(MenuEvent e)`

  在菜单被取消选中后、关闭后被调用。

- `void menuCanceled(MenuEvent e)`

  在菜单被取消时被调用，例如用户点击了菜单外部。

Listing 11.6 是一个生成一组菜单的示例程序。它展示了在本节中看到的所有功能：嵌套菜单、禁用的菜单项、复选框和单选框菜单项、弹出菜单以及键盘记忆键（mnemonics）和快捷键。

**Listing 11.6** `menu/MenuFrame.java`

```java
 1   package menu;

 2

 3   import java.awt.event.*;

 4   import javax.swing.*;

 5

 6   /**

 7    * 一个带有示例菜单栏的 own。

 8    */

 9   public class MenuFrame extends JFrame

10   {

11      private static final int DEFAULT_WIDTH = 300;

12      private static final int DEFAULT_HEIGHT = 200;

13      private Action saveAction;

14      private Action saveAsAction;

15      private JCheckBoxMenuItem readonlyItem;

16      private JPopupMenu popup;

17

18      /**

19        * 一个将动作名称打印到 System.out 的示例动作。

20        */

21      class TestAction extends AbstractAction

22      {

23          public TestAction(String name)

24          {

25              super(name);

26          }

27

28          public void actionPerformed(ActionEvent event)

29          {

30              System.out.println(getValue(Action.NAME) + " selected.");

31          }

32      }

33

34      public MenuFrame()

35      {

36          setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

37

38          var fileMenu = new JMenu("File");

39          fileMenu.add(new TestAction("New"));

40

41          // 演示快捷键

42

43          var openItem = fileMenu.add(new TestAction("Open"));

44          openItem.setAccelerator(KeyStroke.getKeyStroke("ctrl O"));

45

46          fileMenu.addSeparator();

47

48          saveAction = new TestAction("Save");

49          JMenuItem saveItem = fileMenu.add(saveAction);

50          saveItem.setAccelerator(KeyStroke.getKeyStroke("ctrl S"));

51

52          saveAsAction = new TestAction("Save As");

53          fileMenu.add(saveAsAction);

54          fileMenu.addSeparator();

55

56          fileMenu.add(new AbstractAction("Exit")

57          {

58              public void actionPerformed(ActionEvent event)

59              {

60                  System.exit(0);

61              }

62          });

63

64          // 演示复选框和单选框菜单

65

66          readonlyItem = new JCheckBox("Read-only");

67          readonlyItem.addActionListener(new ActionListener()

68          {

69              public void actionPerformed(ActionEvent event)

70              {

71                  boolean saveOk = readonlyItem.isSelected();

72                  saveAction.setEnabled(saveOk);

73                  saveAsAction.setEnabled(saveOk);

74              }

75          });

76

77          var group = new ButtonGroup();

78

79          var insertItem = new JRadioButton("Insert");

80          insertItem.setSelected(true);

81          var typeItem = new JRadioButton("Type");

82          group.add(insertItem);

83          group.add(typeItem);

... (省略部分代码以保持逻辑一致)
```

## 11.5.7 工具栏

工具栏是一个按钮栏，为程序中最常用的命令提供快速访问（参见图 11.22）。

![Image](img/11fig22.jpg)

**图 11.22** 工具栏

工具栏特殊之处在于你可以移动它们。你可以将工具栏拖动到框架的四个边界之一（参见图 11.23）。当你释放鼠标按钮时，工具栏将放置在新的位置（参见图 11.24）。

![Images](img/11fig23.jpg)

**图 11.23** 拖动工具栏

![Images](img/11fig24.jpg)

**图 11.24** 工具栏已拖到另一个边界

![Image](img/note.jpg) **注意：**

如果工具栏位于具有边界布局（border layout）的容器中，或者任何支持 `North`、`East`、`South` 和 `West` 约束的布局管理器中，则工具栏拖动功能有效。

工具栏甚至可以从框架中完全分离。分离后的工具栏包含在它自己的框架中（参见图 11.25）。当你关闭包含分离工具栏的框架时，该工具栏会跳回原始框架。

![Images](img/11fig25.jpg)

**图 11.25** 分离工具栏

工具栏的编程非常简单。向工具栏中添加组件：

```java
var toolbar = new JToolBar();

toolbar.add(blueButton);
```

`JToolBar` 类还有一个用于添加 `Action` 对象的方法。只需像这样用 `Action` 对象填充工具栏即可：

```java
toolbar.add(blueAction);
```

`Action`（动作）的小型图标会显示在工具栏中。

你可以使用分隔符将按钮组隔开：

```java
toolbar.addSeparator();
```

例如，图 11.22 中的工具栏在第三个和第四个按钮之间有一个分隔符。

然后，将工具栏添加到框架中：

```java
add(toolbar, BorderLayout.NORTH);
```

你也可以为工具栏指定标题，该标题在工具栏未停靠时会显示：

```java
toolbar = new JToolBar(titleString);
```

默认情况下，工具栏初始是水平的。要让工具栏从垂直方向开始，请使用：

```java
toolbar = new JToolBar(SwingConstants.VERTICAL);
```

或者：

```java
toolbar = new JToolBar(titleString, SwingConstants.VERTICAL);
```

按钮是工具栏内部最常见的组件。但对你可以添加到工具栏的组件没有限制。例如，你可以将一个组合框添加到工具栏中。

## 11.5.8 提示（Tooltips）

工具栏的一个缺点是，用户往往对工具栏中微小图标的含义感到困惑。为了解决这个问题，用户界面设计师发明了提示。当光标停留在按钮上片刻时，就会激活提示。提示文本显示在颜色的矩形中。当用户移开鼠标时，提示就会消失。（参见图 11.26。）

![Images](img/11fig26.jpg)

**图 11.26** 提示

在 Swing 中，你只需调用 `setToolTipText` 方法即可为任何 `JComponent` 添加提示：

```java
exitButton.setToolTipText("Exit");
```

或者，如果你使用 `Action` 对象，则将提示与 `SHORT_DESCRIPTION` 键关联：

```java
exitAction.putValue(Action.SHORT_DESCRIPTION, "Exit");
```




#### `javax.swing.JToolBar` 1.2

- `JToolBar()`
- `JToolBar(String titleString)`
- `JToolBar(int orientation)`
- `JToolBar(String titleString, int orientation)`

根据给定的标题字符串和方向构造工具栏。`orientation` 是 `SwingConstants.HORIZONTAL`（默认值）或 `SwingConstants.VERTICAL` 之一。

- `JButton add(Action a)`

根据给定的 `action` 在工具栏内部构造一个具有名称、图标、短描述和动作回调的新按钮，并将该按钮添加到工具栏的末尾。

- `void addSeparator()`

在工具栏的末尾添加一个分隔符。

#### `javax.swing.JComponent` 1.2

- `void setToolTipText(String text)`

设置当鼠标悬停在组件上时应显示为提示的文本。

### 11.6 复杂的布局管理

到目前为止，我们在示例应用程序的用户界面中仅使用了边界布局（border layout）、流式布局（flow layout）和网格布局（grid layout）。对于更复杂的任务，这是不够的。

自 Java 1.0 以来，AWT 就包含了网格布局（grid bag layout），它以行和列的形式布局组件。行和列的大小是灵活的，组件可以跨越多行多列。这种布局管理器非常灵活，但也非常复杂。仅仅是提到“grid bag layout”这几个词就足以让 Java 程序员感到恐惧。

在一次尝试设计一种能让程序员摆脱网格布局专政的布局管理器的尝试中，Swing 设计者提出了框布局（box layout）。根据 `BoxLayout` 类的 JDK 文档：“嵌套多个具有不同水平和垂直 [sic]组合的面板可以产生类似于 `GridBagLayout` 的效果，而没有其复杂性。”然而，由于每个框都是独立布局的，你无法使用框布局来在水平和垂直方向上排列相邻组件。

Java 1.4 出现了另一个设计网格布局替代品的尝试——弹簧布局（spring layout），你使用虚拟的弹簧来连接容器中的组件。随着容器的大小调整，弹簧会拉伸或收缩，从而调整组件的位置。这听起来既乏味又混乱，事实也如此。弹簧布局很快就被遗忘了。

NetBeans IDE 结合了布局工具（称为“Matisse”）和布局管理器。用户界面设计师使用该工具将组件拖入容器中，并指示哪些组件应该对齐。该工具将设计师的意图翻译成分组布局管理器的指令。这比手动编写布局管理代码要方便得多。

在接下来的章节中，我将介绍网格布局，因为它常用，并且仍然程序化生成布局代码的最简单机制。我将为你展示一种让 grid bag 布局在常见情况下变得不再痛苦的策略。

最后，你将看到如何编写自己的布局管理器。

#### 11.6.1 网格布局（The Grid Bag）

网格布局是所有布局管理器的母体。你可以将网格布局看作是不带限制的网格布局。在网格布局中，行和列的大小是可以变化的。你可以合并相邻单元以为更大的组件留空间。（许多文字处理器，如 HTML，提供了类似的功能：你可以从这里合并单元格。）组件不需要填充整个单元格，你可以指定它们在单元格内的对齐方式。

考虑图 11.27 中的字体选择器。它由以下组件组成：

- 指定字体和大小的组合框
- 这些组合框的标签
- 选择加粗和斜体的复选框
- 用于字符串的文本区域

![Images](img/11fig27.jpg)

**图 11.27** 字体选择器

现在，如图 11.28 所示将容器划分为单元格。（行列不需要相等。）每个复选框跨越两列，文本区域跨越四行。

![Images](img/11fig28.jpg)

**图 11.28** 设计中使用的对话框

要向网格管理器描述布局，请使用以下步骤：

1. 创建一个 `GridBagLayout` 对象。你不需要告诉它底层网格有多少行多少列。相反，布局管理器将根据你之后提供的信息进行判断。
2. 将此 `GridBagLayout` 对象设置为组件的布局管理器。
3. 对于每个组件，创建一个 `GridBagConstraints` 对象。设置 `GridBagConstraints` 对象的字段值以指定组件在网格袋中的布局方式。
4. 最后，通过调用添加每个组件及其约束：

```java
add(component, constraints);
```

技巧在于知道如何设置 `GridBagConstraints` 对象的状态。我们将在接下来的章节中讨论该对象。

##### 11.6.1.1 `gridx`、`gridy`、`gridwidth` 和 `gridheight` 参数

`gridx`、`gridy`、`gridwidth` 和 `gridheight` 定义了组件在网格中的位置。`gridx` 和 `gridy` 值指定了要添加的组件左上角的列位置和行位置。`gridwidth` 和 `gridheight` 值决定了组件占据的列数和行数。

网格坐标从 `0` 开始。特别是，`gridx = 0` 和 `gridy = 0` 表示左上角。我们示例中的文本区域具有 `gridx = 2`、`gridy = 0`，因为它从第 0 行的第 2 列（即第三列）开始。它的 `gridwidth = 1`、`gridheight = 4`，因为它跨越了一列和四行。

##### 11.6.1.2 权重字段（Weight Fields）

在 grid bag 布局中，你始终需要为每个区域设置 `weight` 字段（`weightx` 和 `weighty`）。如果你将权重设置为 `0`，则该区域在该方向上永远不会超出其初始大小进行增长或缩小。在图 11.27 的 grid bag 布局中，我们将标签的 `weightx` 字段设置为 `0`。这允许标签在调整窗口大时保持固定宽度。相反，如果你将所有区域的权重都设置为 `0`，容器将收缩在其分配区域的中心，而不是拉伸以填充它。

从概念上说，权重参数的问题在于权重是行和列的属性，而不是单个单元格的属性。但你需要为单元格指定它们，因为 grid bag 布局并没有暴露行和列。行和列权重是通过每行或每列中单元格权重的最大值计算出的。因此，如果你想让某行或某列保持固定大小，你需要将其中所有组件的权重设置为零。

请注意，权重实际上并没有给出列的相对大小。它们告诉你如果容器超过了其首选尺寸，应该将多少比例的“空隙”（slack）空间分配给每个区域。这并不直观。我建议你将所有权重设置为 `100`。然后运行程序查看布局情况。调整对话框查看行和列是如何调整的。如果你发现某一行或某列不应该增长，则将其其中所有组件的权重设置为零。你可以尝试其他权重值，但通常不值得花费精力。

##### 11.6.1.3 `fill` 和 `anchor` 参数

如果你不希望组件拉伸并填充整个区域，请设置 `fill` 约束。该参数有四种可能性：有效值分别为 `GridBagConstraints.NONE`、`GridBagConstraints.HORIZONTAL`、`GridBagConstraints.VERTICAL` 和 `GridBagConstraints.BOTH`。

如果组件没有填充整个区域，你可以通过设置 `anchor` 字段来指定你希望它位于区域的哪个位置。有效值为 `GridBagConstraints.CENTER`（默认值）、`GridBagConstraints.NORTH`、`GridBagConstraints.NORTHEAST`、`GridBagConstraints.EAST` 等。

##### 11.6.1.4 内置内边距（Padding）

你可以通过设置 `GridBagConstraints` 的 `insets` 字段在组件周围留出额外的空白空间。将 `Insets` 对象的 `left`、`top`、`right` 和 `bottom` 值设置为你希望在组件周围保留的空间量。这被称为*外边距*（external padding）。

`ipadx` 和 `ipady` 值设置了*内边距*（internal padding）。这些值会被加到组件的最小宽度和高度。这确保了组件不会缩小到它的最小尺寸。

##### 11.6.1.5 指定 `gridx`、`gridy`、`gridwidth` 和 `gridheight` 参数的替代方法

AWT 文档建议，不要将 `gridx` 和 `gridy` 值设置为绝对位置，而是将它们设置为常量 `GridBagConstraints.RELATIVE`。然后，按照标准顺序将组件添加到 grid bag 布局中，从第一行从左到右，然后移动到下一行，依此类推。

你仍然通过提供相应的 `gridheight` 和 `gridwidth` 字段来指定跨越的行和列数。然而，如果组件延伸到*最后*一行或一列，不需要指定实际数字，而是常量 `GridBagConstraints.REMAINDER`。这告诉布局管理器该组件是该行中的最后一个。

这种方案似乎确实有效。但向布局管理器隐藏实际的放置信息并希望它能重新发现这些信息，听起来真的非常笨拙。

##### 11.6.1.6 Grid Bag 布局配方

在实践中，以下配方可以使 grid bag 布局变得相对没什么问题：

1. 在纸上勾画出组件布局。
2. 找到一个网格，使得每个小组件都包含在一个单元格中，而较大的组件跨越多个单元格。
3. 用 0, 1, 2, 3, . . . 为网格的行和列标记。你可以读取 `gridx`、`gridy`、`gridwidth` 和 `gridheight` 值。
4. 对于每个组件，问自己它是否需要水平或垂直填充其所在的单元格。如果不需要，你希望如何对齐？这决定了 `fill` 和 `anchor` 参数。
5. 将所有权重都设置为 `100`。然而，如果你想让某行或某列保持固定大小，则将其其中所有组件的权重设置为零。
6. 编写代码。仔细检查你的设置。一个错误的约束就会破坏布局。
7. 编译、运行并享受。

##### 11.6.1.7 用于简化 Grid Bag 约束的辅助类

grid bag 布局中最枯燥的部分是编写设置代码。我为字体示例提供了这样一个类。该类具有以下特性：

- 它的名字很短：`GBC` 而不是 `GridBagConstraints`。
- 它继承自 `GridBagConstraints`，因此可以使用更短的常量，例如 `GBC.EAST`。
- 有两个构造函数可以设置常用的参数：`gridx` 和 `gridy`，或者 `gridwidth` 和 `gridheight`。
- 对于成对出现的字段有方便的 setter。
- setter 方法返回 `this`，因此你可以进行链式调用。
- `setInsets` 方法为你构造 `Insets` 对象。要获取 1 像素的内边距，只需调用。

列表 11.7 显示了字体对话框的类。`GBC` 辅助类在列表 11.8 中。以下是将组件添加到 grid bag 的代码：

```java
add(faceLabel, new GBC(0, 0).setAnchor(GBC.EAST));

add(face, new GBC(1, 0).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));

add(sizeLabel, new GBC(0, 1).setAnchor(GBC.EAST));

add(size, new GBC(1, 1).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));

add(bold, new GBC(0, 2, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));

add(italic, new GBC(0, 3, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));

add(sample, new GBC(2, 0, 1, 4).setFill(GBC.BOTH).setWeight(100, 100));
```

一旦你理解了 grid bag 约束，这种代码就非常容易阅读和调试。

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
 * 一个使用 grid bag 布局来排列字体选择组件的框架。
 */
public class FontFrame extends JFrame {
    public static final int TEXT_ROWS = 10;
    public static final int TEXT_COLUMNS = 20;

    private JComboBox<String> face;
    private JComboBox<Integer> size;
    private JCheckBox bold;
    private JCheckBox italic;
    private JTextArea sample;

    public FontFrame() {
        var layout = new GridBagLayout();
        setLayout(layout);

        ActionListener listener = event -> updateSample();

        // 构建组件
        var faceLabel = new JLabel("Face: ");
        face = new JComboBox<>(new String[] {
            "Serif", "SansSerif", "Monospaced", "Dialog", "DialogInput"
        });
        face.addActionListener(listener);

        var sizeLabel = new JLabel("Size: ");
        size = new JComboBox<>(new Integer[] { 8, 10, 12, 15, 18, 24, 36, 48 });
        size.addActionListener(listener);

        bold = new JCheckBox("Bold");
        bold.addActionListener(listener);

        italic = new JCheckBox("Italic");
        italic.addActionListener(listener);

        sample = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
        sample.setText("The quick brown fox jumps over the lazy dog");
        sample.setEditable(false);
        sample.setLineWrap(true);
        sample.setBorder(BorderFactory.createEtchedBorder());

        // 使用 GBC 便利类将组件添加到网格
        add(faceLabel, new GBC(0, 0).setAnchor(GBC.EAST));
        add(face, new GBC(1, 0).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));
        add(sizeLabel, new GBC(0, 1).setAnchor(GBC.EAST));
        add(size, new GBC(1, 1).setFill(GBC.HORIZONTAL).setWeight(100, 0).setInsets(1));
        add(bold, new GBC(0, 2, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));
        add(italic, new GBC(0, 3, 2, 1).setAnchor(GBC.CENTER).setWeight(100, 100));
        add(sample, new GBC(2, 0, 1, 4).setFill(GBC.BOTH).setWeight(100, 100));

        pack();
        updateSample();
    }

    public void updateSample() {
        var fontFace = (String) face.getSelectedItem();
        int fontStyle = (bold.isSelected() ? Font.BOLD : 0)
                + (italic.isSelected() ? Font.ITALIC : 0);
        int fontSize = size.getSelectedIndex();
        var font = new Font(fontFace, fontStyle, fontSize);



```java
sample.setFont(font);

sample.repaint();

}
}
```

### Listing 11.8 `gridbag/GBC.java`

```java
package gridbag;

import java.awt.*;

/**
 * 此类简化了 `GridBagConstraints` 类的使用。
 *
 * @version 1.0 2004-05-06
 * @author Cay Horstmann
 */
public class GBC extends GridBagConstraints {

    /**
     * 构建一个具有给定 `gridx` 和 `gridy` 位置的 `GBC`，并将所有其他约束值设置为默认值。
     *
     * @param gridx the `gridx` 位置
     * @param gridy the `gridy` 位置
     */
    public GBC(int gridx, int gridy) {
        this.gridx = gridx;
        this.gridy = gridy;
    }

    /**
     * 构建一个具有给定 `gridx`、`gridy`、`gridwidth`、`gridheight` 的 `GBC`，并将所有其他约束值设置为默认值。
     *
     * @param gridx the `gridx` 位置
     * @param gridy the `gridy` 位置
     * @param gridwidth x 方向的单元格跨度
     * @param gridheight y 方向的单元格跨度
     */
    public GBC(int gridx, int gridy, int gridwidth, int gridheight) {
        this.gridx = gridx;
        this.gridy = gridy;
        this.gridwidth = gridwidth;
        this.gridheight = gridheight;
    }

    /**
     * 设置锚点。
     *
     * @param anchor 锚点值
     * @return 此对象以便进行进一步修改
     */
    public GBC setAnchor(int anchor) {
        this.anchor = anchor;
        return this;
    }

    /**
     * 设置填充方向。
     *
     * @param fill 填充方向
     * @return 此对象以便进行进一步修改
     */
    public GBC setFill(int fill) {
        this.fill = fill;
        return this;
    }

    /**
     * 设置权重。
     *
     * @param weightx x 方向的单元格权重
     * @param weighty y 方向的单元格权重
     * @return 此对象以便进行进一步修改
     */
    public GBC setWeight(double weightx, double weighty) {
        this.weightx = weightx;
        this.weighty = weighty;
        return this;
    }

    /**
     * 设置此单元格的内边距。
     *
     * @param distance 统一使用的间距
     * @return 此对象以便进行进一步修改
     */
    public GBC setInsets(int distance) {
        this.insets = new Insets(distance, distance, distance);
        return this;
    }

    /**
     * 设置此单元格的内边距。
     *
     * @param top 顶部的间距
     * @param left 左侧的间距
     * @param bottom 底部的间距
     * @param right 右侧的间距
     * @return 此对象以便进行进一步修改
     */
    public GBC setInsets(int top, int left, int bottom, int right) {
        this.insets = new Insets(top, left, bottom, right);
        return this;
    }

    /**
     * 设置内部填充空间。
     *
     * @param ipadx x 方向的内部填充宽度
     * @param ipady y 方向的内部填充高度
     * @return 此对象以便进行进一步修改
     */
    public GBC setIpad(int ipadx, int ipady) {
        this.ipadx = ipadx;
        this.ipady = ipady;
        return this;
    }
}
```

### `java.awt.GridBagConstraints` 1.0

- `int gridx, gridy` 指定单元格的起始列和行。默认值为 `0`。
- `int gridwidth, gridheight` 指定单元格的列和行跨度。默认值为 `1`。
- `double weightx, weighty` 指定单元格的增长能力。默认值为 `0`。
- `int anchor` 表示组件在单元格内的对齐方式。你可以选择绝对位置：

```text
NORTHEAST          NORTH                NORTHWEST

WEST                CENTER               EAST

SOUTHWEST           SOUTH                SOUTHEAST
```

或者方向无关的对应项：

```text
FIRST_LINE_END      LINE_START           LAST_LINE_END

PAGE_START          CENTER               PAGE_END

FIRST_LINE_START    LAST_LINE_START      LINE_END
```

如果你的应用程序可能用于从右到左或从上下的文本，请使用后者。默认值为 `CENTER`。

- `int fill` 指定组件在单元格内的填充行为：`NONE`、`BOTH`、`HORIZONTAL` 或 `VERTICAL` 之一。默认值为 `NONE`。
- `int ipadx, ipady` 指定组件周围的“内部”填充。默认值为 `0`。
- `Insets insets` 指定沿单元格边界的“外部”填充。默认无间距。
- `GridBagConstraints(int gridx, int gridy, int gridwidth, int gridheight, double weightx, double weighty, int anchor, int fill, Insets insets, int ipadx, int ipady)` 1.2

通过参数中指定的所有字段来构造一个 `GridBagConstraints`。此构造函数应该只由自动代码生成器使用，因为它会让你的源代码变得非常难以读。

### 11.6.2 自定义布局管理器

你可以设计自己的 `LayoutManager` 类，以特殊的方式管理组件。作为一个趣味的例子，让我们把容器中的所有组件排列成一个圆（参见图 11.29）。

你自定义的布局管理器必须实现 `LayoutManager` 接口。你需要重写以下五个方法：

```java
void addLayoutComponent(String s, Component c)

void removeLayoutComponent(Component c)

Dimension preferredLayoutSize(Container parent)

Dimension minimumLayoutSize(Container parent)

void layoutContainer(Container parent)
```

![Images](img/11fig29.jpg)

**图 11.29** 圆形布局

前两个方法在组件添加或移除时被调用。如果你没有保留关于组件的任何额外信息，可以让它们什么都不做。接下来两个方法计算组件的最小布局和首选布局所需的空间。这些通常是相同的值。第五个方法执行实际工作，并在所有组件上调用 `setBounds`。

---

![Image](img/note.jpg) **注意：**

AWT 有第二个接口，称为 `LayoutManager2`，有十个方法需要实现而不是五个。`LayoutManager2` 接口的主要点是允许你使用带约束的 `add` 方法。例如，`BorderLayout` 和 `GridBagLayout` 实现了 `LayoutManager2` 接口。

---

Listing 11.9 显示了 `CircleLayout` 管理器的代码，遗憾的是，它将组件沿父容器内部的圆周布局。示例程序的框架类在 Listing 11.10 中。

### Listing 11.9 `circleLayout/CircleLayout.java`

```java
1  package circleLayout;

2

3  import java.awt.*;

4

5  /**
6    * 一个沿圆周排列组件的布局管理器。
7    */
8  public class CircleLayout implements LayoutManager
9  {
10      private int minWidth = 0;
11      private int minHeight = 0;
12      private int preferredWidth = 0;
13      private int preferredHeight = 0;
14      private boolean sizesSet = false;
15      private int maxComponentWidth = 0;
16      private int maxComponentHeight = 0;

18      public void addLayoutComponent(String name, Component comp)
19      {
20      }

22      public void removeLayoutComponent(Component comp)
23      {
24      }

26      public void setSizes(Container parent)
27      {
28          if (sizesSet) return;
29          int n = parent.getComponentCount();

31          preferredWidth = 0;
32          preferredHeight = 0;
33          minWidth = 0;
34          minHeight = 0;
35          maxComponentWidth = 0;
36          maxComponentHeight = 0;

38          // 计算组件的最大宽度和高度
39          //并将首选尺寸设为组件尺寸之和
40          for (int i = 0; i < n; i++)
41          {
42              Component c = parent.getComponent(i);
43              if (c.isVisible())
44              {
45                  Dimension d = c.getPreferredSize();
46                  maxComponentWidth = Math.max(maxComponentWidth, d.width);
47                  maxComponentHeight = Math.max(maxComponentHeight, d.height);
48                  preferredWidth += d.width;
49                  preferredHeight += d.height;
50              }
51          }
52          minWidth = preferredWidth / 2;
53          minHeight = preferredHeight / 2;
54          sizesSet = true;
55      }

56      public Dimension preferredLayoutSize(Container parent)
57      {
58          setSizes(parent);
59          Insets insets = parent.getInsets();
60          int width = preferredWidth + insets.left + insets.right;
61          int height = preferredHeight + insets.top + insets.bottom;
62          return new Dimension(width, height);
63      }

64      public Dimension minimumLayoutSize(Container parent)
65      {
66          setSizes(parent);
67          Insets insets = parent.getInsets();
68          int width = minWidth + insets.left + insets.right;
69          int height = minHeight + insets.top + insets.bottom;
70          return new Dimension(width, height);
71      }

72      public void layoutContainer(Container parent)
73      {
74          setSizes(parent);
75          // 计算圆的中心
76          Insets insets = parent.getInsets();
77          int containerWidth = parent.getSize().width - insets.left - insets.right;
78          int containerHeight = parent.getSize().height - insets.top - insets.bottom;
79          int xcenter = insets.left + containerWidth / 2;
80          int ycenter = insets.top + containerHeight / 2;
81          // 计算圆的半径
82          int xradius = (containerWidth - maxComponentWidth) / 2;
83          int yradius = (containerHeight - maxComponentHeight) / 2;
84          int radius = Math.min(xradius, yradius);
85          // 沿圆周布局
86          int n = parent.getComponentCount();
87          for (int i = 0; i < n; i++)
88          {
89              Component c = parent.getComponent(i);
90              if (c.isVisible())
91              {
92                  double angle = 2 * Math.PI * i / n;
93                  // 组件中心点
94                  int x = xcenter + (int) (Math.cos(angle) * radius);
```



```java
int y = ycenter + (int) (Math.sin(angle) * radius);

// 移动组件使其中心位于 (x, y)

// 尺寸为其首选尺寸

Dimension d = c.getPreferredSize();
c.setBounds(x - d.width / 2, y - d.height / 2, d.width, d.height);
}
}
}
}
```

**Listing 11.10** `circleLayout/CircleLayoutFrame.java`

```java
package circleLayout;

import javax.swing.*;

/**
 * 一个沿圆周排列按钮的框架。
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

无模对话框（modeless dialog box）允许用户在对话框和应用程序的其他部分输入信息。无模对话框的一个示例是工具栏。工具栏可以根据需要保持原位，用户可以根据需要与应用程序窗口和工具栏进行交互。

让我们从简单的对话框开始本节——即带有单个消息的模态对话框。Swing 有一个方便的 `JOptionPane` 类，可以让你无需编写任何特殊的对话框代码就能弹出一个简单的对话框。接下来，你将看到如何通过实现自己的对话窗口来编写更复杂的对话框。最后，你将看到如何将数据从应用程序传输到对话框并返回。

我们将通过查看 Swing 的 `JFileChooser` 来结束对对话框的讨论。

## 11.7.1 选项对话框

Swing 有一组现成的简单对话框，足以向用户询问单项信息。`JOptionPane` 有四个静态方法来显示这些简单对话框：

![Images](img/722tab01.jpg)

图 11.30 显示了一个典型的对话框。如你所见，该对话框包含以下组件：

- 一个图标
- 一条消息
- 一个或多个选项按钮

![Images](img/11fig30.jpg)

**图 11.30** 选项对话框

输入对话框还有一个额外的用于用户输入的组件。这可以是一个用户可以在其中输入任意字符串的文本字段，也可以是一个用户可以从中选择一个项目的组合框。

这些对话框的精确布局以及标准消息类型的图标选择取决于可插的外观节点（pluggable look-and-feel）。

左侧的图标取决于五种消息类型之一：

```text
ERROR_MESSAGE

INFORMATION_MESSAGE

WARNING_MESSAGE

QUESTION_MESSAGE

PLAIN_MESSAGE
```

`PLAIN_MESSAGE` 类型没有图标。每种对话框类型都有一个方法允许你提供自己的图标。

对于每种对话框类型，你可以指定一条消息。此消息可以是字符串、图标、用户界面组件或任何其他对象。消息对象的显示方式如下：

![Images](img/723tab01.jpg)

当然，提供消息字符串是最常见的情况。提供一个 `Component` 会给你极大的灵活性，因为你可以让 `paintComponent` 方法绘制你想要的任何内容。

底部的按钮取决于对话框类型和选项类型。调用 `showMessageDialog` 和 `showInputDialog` 时，你只会得到一组标准的按钮（分别是 OK 和 OK/Cancel）。调用 `showConfirmDialog` 时，你可以从四种选项类型中选择：

```text
DEFAULT_OPTION

YES_NO_OPTION

YES_NO_CANCEL_OPTION

OK_CANCEL_OPTION
```

使用 `showOptionDialog` 可以指定任意一组选项。你为选项提供一个对象数组。每个数组元素的渲染方式如下：

![Images](img/723tab02.jpg)

这些函数的返回值如下：

![Images](img/723tab03.jpg)

`showConfirmDialog` 和 `showOptionDialog` 返回整数以表示用户选择了哪个按钮。对于选项对话框，这仅仅是所选选项的索引，如果用户关闭了对话框而不是选择选项，则返回 `CLOSED_OPTION`。对于确认对话框，返回值可以是以下值之一：

```text
OK_OPTION

CANCEL_OPTION

YES_OPTION

NO_OPTION

CLOSED_OPTION
```

这听起来像是一组令人困惑的选择，但在实践中非常简单。遵循以下步骤：

1. 选择对话框类型（消息、确认、选项或输入）。
2. 选择图标（错误、信息、警告、问题、无或自定义）。
3. 选择消息（字符串、图标、自定义组件或它们的组合）。
4. 对于确认对话框，选择选项类型（默认、是/否、是/否/取消或确定/取消）。
5. 对于选项对话框，选择选项（字符串、图标或自定义组件）和默认选项。
6. 对于输入对话框，在文本字段和组合框之间进行选择。
7. 在 `JOptionPane` API 中找到要调用的相应方法。

例如，假设你想显示图 11.30 中的对话框。该对话框显示了一条消息并要求用户确认或取消。因此，这是一个确认对话框。图标是一个问号图标。消息是一个字符串。选项类型是 `OK_CANCEL_OPTION`。以下是你将进行的调用：

```java
int selection = JOptionPane.showConfirmDialog(parent,
    "Message", "Title",
    JOptionPane.OK_CANCEL_OPTION,
    JOptionPane.QUESTION_MESSAGE);

if (selection == JOptionPane.OK_OPTION) . . .
```

***

![Image](img/tip.jpg)

**提示：**

消息字符串可以包含换行符（`'\n'`）。这样的字符串将以多行形式显示。

***

**`javax.swing.JOptionPane`** **1.2**

***

- `static void showMessageDialog(Component parent, Object message, String title, int messageType, Icon icon)`
- `static void showMessageDialog(Component parent, Object message, String title, int messageType)`
- `static void showMessageDialog(Component parent, Object message)`
- `static void showInternalMessageDialog(Component parent, Object message, String title, int messageType, Icon icon)`
- `static void showInternalMessageDialog(Component parent, Object message, String title, int messageType)`
- `static void showInternalMessageDialog(Component parent, Object message)`

显示消息对话框或内部消息对话框。（内部对话框完全渲染在所有所有者的框架内。）父组件可以为 `null`。在对话框上显示的消息可以是字符串、图标、组件或它们的数组。`messageType` 参数是 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE`、`PLAIN_MESSAGE` 之一。

- `static int showConfirmDialog(Component parent, Object message, String title, int optionType, int messageType, Icon icon)`
- `static int showConfirmDialog(Component parent, Object message, String title, int optionType, int messageType)`
- `static int showConfirmDialog(Component parent, Object message, String title, int optionType)`
- `static int showConfirmDialog(Component parent, Object message)`
- `static int showInternalConfirmDialog(Component parent, Object message, String title, int optionType, int messageType, Icon icon)`
- `static int showInternalConfirmDialog(Component parent, Object message, String title, int optionType, int messageType)`
- `static int showInternalConfirmDialog(Component parent, Object message, String title, int optionType)`
- `static int showInternalConfirmDialog(Component parent, Object message)`

显示确认对话框或内部确认对话框。（内部对话框完全渲染在所有者的框架内。）返回用户选择的选项（`OK_OPTION`、`CANCEL_OPTION`、`YES_OPTION`、`NO_OPTION` 之一），如果用户关闭了对话框则返回 `CLOSED_OPTION`。父组件可以为 `null`。在对话框上显示的消息可以是字符串、图标、组件或它们的数组。`messageType` 参数是 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE`、`PLAIN_MESSAGE` 之一，`optionType` 是 `DEFAULT_OPTION`、`YES_NO_OPTION`、`YES_NO_CANCEL_OPTION`、`OK_CANCEL_OPTION` 之一。

- `static int showOptionDialog(Component parent, Object message, String title, int optionType, int messageType, Icon icon, Object[] options, Object default)`
- `static int showInternalOptionDialog(Component parent, Object message, String title, int optionType, int messageType, Icon icon, Object[] options, Object default)`

显示一个选项对话框或内部选项对话框。（内部对话框完全在所有所有者框架内渲染。）返回用户选择的选项的索引，如果用户取消了对话框，则返回 `CLOSED_OPTION`。父组件可以是 `null`。显示在对话框上的消息可以是字符串、图标、组件或它们的数组。`messageType` 参数是 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE`、`PLAIN_MESSAGE` 之一，`optionType` 是 `DEFAULT_OPTION`、`YES_NO_OPTION`、`YES_NO_CANCEL_OPTION`、`OK_CANCEL_OPTION` 之一。`options` 参数是字符串、图标或组件的数组。

- `static Object showInputDialog(Component parent, Object message, String title, int messageType, Icon icon, Object[] values, Object default)`
- `static String showInputDialog(Component parent, Object message, String title, int messageType)`
- `static String showInputDialog(Component parent, Object message)`
- `static String showInputDialog(Object message)`
- `static String showInputDialog(Component parent, Object message, Object default)` **1.4**
- `static String showInputDialog(Object message, Object default)` **1.4**
- `static Object showInternalInputDialog(Component parent, Object message, String title, int messageType, Icon icon, Object[] values, Object default)`
- `static String showInternalInputDialog(Component parent, Object message, String title, int messageType)`
- `static String showInternalInputDialog(Component parent, Object message)`

显示一个输入对话框或内部输入对话框。（内部对话框完全在所有所有者框架内渲染。）返回用户输入的字符串，如果用户取消了对话框，则返回 `null`。父组件可以是 `null`。显示在对话框上的消息可以是字符串、图标、组件或它们的数组。`messageType` 参数是 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE`、`PLAIN_MESSAGE` 之一。

## 11.7.2 创建对话框

在上一节中，你已经了解了如何使用 `JOptionPane` 类来显示简单的对话框。在本节中，你将看到如何手动创建一个这样的对话框。

图 11.31 显示了一个典型的模态对话框——当用户点击“关于”（About）按钮时显示的程序信息框。

![Images](img/11fig31.jpg)

**图 11.31** “关于”对话框

要实现一个对话框，你需要扩展 `JDialog` 类。这与为应用程序的主窗口扩展 `JFrame` 的过程本质上是相同的。更具体地说：

1. 在你的对话框的构造函数中，调用父类 `JDialog` 的构造函数。
2. 添加对话框的用户界面组件。
3. 添加事件处理器。
4. 设置对话框的大小。

当你调用父类构造函数时，你需要提供*所有者框架*（owner frame）、对话框的标题以及*模态性*（modality）。

所有者框架控制对话框显示的位置。你可以提供 `null` 作为所有者；这样对话框将由隐藏的框架所有。模态指定了在对话框显示期间，应用程序的哪些其他窗口会被阻塞。非模态对话框不会阻塞其他窗口。模态对话框会阻塞应用程序的所有其他窗口（对话框的子窗口除外）。你会为一个用户可以随时访问的工具箱使用非模态对话框。另一方面，如果你想强制用户在继续之前提供必需信息，就会使用模态对话框。

这里是对话框的代码：

```java
public AboutDialog extends JDialog
{
    public AboutDialog(JFrame owner)
    {
        super(owner, "About DialogTest", true);
        add(new JLabel(
            "<html><h1><i>Core Java</i></h1><hr>By Cay Horstmann</html>"),
            BorderLayout.CENTER);

        var panel = new JPanel();
        var ok = new JButton("OK");
```



```java
ok.addActionListener(event -> setVisible(false));

panel.add(ok);

add(panel, BorderLayout.SOUTH);

setSize(250, 150);

}
}
```

你可以看到，构造函数添加了用户界面元素——在这种情况下，是标签和按钮。它为按钮添加了处理器并设置了对话框的大小。

要显示对话框，创建一个新的对话框对象并使其可见：

```java
var dialog = new AboutDialog(this);
dialog.setVisible(true);
```

实际上，在下方的示例代码中，我们只创建一次对话框，并在用户每次点击“关于”按钮时重复使用它。

```java
if (dialog == null) // 第一次
   dialog = new AboutDialog(this);
dialog.setVisible(true);
```

当用户点击 OK 按钮时，对话框应该关闭。这在 OK 按钮的事件处理器中处理：

```java
ok.addActionListener(event -> setVisible(false));
```

当用户通过点击关闭关闭对话框时，对话框也会隐藏。与 `JFrame` 一样，你可以通过 `setDefaultCloseOperation` 方法来覆盖此行为。列表 1.1 是测试框架类的代码。列表 1.2 显示了对话框类。

**列表 1.1** `dialog/DialogFrame.java`

```java
package dialog;

import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;

/**
 * 一个其菜单->About 显示对话框的框架。
 */
public class DialogFrame extends JFrame
{
   private static int DEFAULT_WIDTH = 300;
   private static int DEFAULT_HEIGHT = 200;
   private AboutDialog dialog;

   public DialogFrame()
   {
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

      // 构建一个文件菜单
      var menuBar = new JMenuBar();
      setJMenuBar(menuBar);
      var fileMenu = new JMenu("File");
      menuBar.add(fileMenu);

      // 添加 About 和 Exit 菜单项
      // About 项显示 About 对话框
      var aboutItem = new JMenuItem("About");
      aboutItem.addActionListener(event ->
      {
         if (dialog == null) // 第一次
            dialog = new AboutDialog(DialogFrame.this);
         dialog.setVisible(true); // 弹出对话框
      });
      fileMenu.add(aboutItem);

      // Exit 项退出程序
      var exitItem = new JMenuItem("Exit");
      exitItem.addActionListener(event -> System.exit(0));
      fileMenu.add(exitItem);
   }
}
```

**列表 11.12** `dialog/AboutDialog.java`

```java
package dialog;

import java.awt.BorderLayout;

import javax.swing.JButton;
import javax.swing.JDialog;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;

/**
 * 一个显示消息并等待用户点击
 * OK 按钮的示例模态对话框。
 */
public class AboutDialog extends JDialog
{
   public AboutDialog(JFrame owner)
   {
      super(owner, "About DialogTest", true);

      // 添加 HTML 标签到中心
      add(
        new JLabel(
          "<html><h1><i>Core Java</i></h1><hr>By Cay Horstmann</html>"),
          BorderLayout.CENTER);

      // OK 按钮关闭对话框
      var ok = new JButton("OK");
      ok.addActionListener(event -> setVisible(false));

      // 将 OK 按钮添加到南部边界
      var panel = new JPanel();
      panel.add(ok);
      add(panel, BorderLayout.SOUTH);
      pack();
   }
}
```

**`javax.swing.JDialog` 1.2**

- `public JDialog(Frame parent, String title, boolean modal)`

  构造对话框。对话框在显式显示之前是不可的。

### 11.7.3 数据交换

弹出对话框最常见的目的是获取用户获取信息。你已经看到创建一个对话框对象是多么简单了：给它提供初始数据并调用 `setVisible(true)` 即可在屏幕上显示该对话框。现在，让我们来看看如何在对话框中进行数据的输入输出。

考虑图 11.32 中的对话框，它可以用于获取用户名和密码，以连接某些在线服务。

![Images](img/11fig32.jpg)

**图 11.32** 密码对话框

你的对话框应该提供设置默认数据的方法。例如，示例程序中的 `PasswordChooser` 类有一个方法 `setUser`，用于将默认值填充到后续字段中：

```java
public void setUser(User u)
{
   username.setText(u.getName());
}
```

一旦设置了默认值（如果需要），就可以调用 `setVisible(true)` 来显示对话框。此时对话框就会显示。

用户随后填写信息并点击确定或取消按钮。这两个按钮的事件处理器都会调用 `setVisible(false)`，这会终止对 `setVisible(true)` 的调用。或者，用户也可以直接关闭对话框。如果你没有为对话框安装窗口监听器，则应用默认的窗口关闭操作：对话框变为不可见，这也会终止对 `setVisible(true)` 的调用。

重要的问题是，`setVisible(true)` 的调用会阻塞，直到用户关闭对话框。这使得实现模态对话框（modal dialogs）变得简单。

你想知道用户是接受还是取消了对话框。我们的示例代码在显示对话框之前将 `ok` 标记置为 `false`。只有确定按钮的事件处理器会将 `ok` 标记置为 `true`；这就是你从对话框中检索用户输入的方法。

![Image](img/note.jpg) **注意：**

从非模态对话框传输数据并不简单。当显示非模态对话框时，`setVisible(true)` 的调用不会阻塞，程序会在对话框显示期间继续运行。如果用户在非模态对话框上选择了项目并点击确定，对话框需要向程序中的某些监听器发送事件。

示例程序包含了另一个实用的改进。当你构造 `JDialog` 对象时，需要指定所有者帧（owner frame）。然而，通常你希望用不同的所有者帧显示同一个对话框。更好的做法是在准备显示对话框时选择所有者帧，而不是在构造 `PasswordChooser` 对象时。

技巧是让 `PasswordChooser` 继承 `JPanel` 而不是 `JDialog`。在 `showDialog` 方法中动态构建 `JDialog` 对象：

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

注意，`owner` 等于 `null` 是安全的。

你可以做得更好。有时所有者帧并不容易获取。从任何 `parent` 组件计算它都是容易的，如下：

```java
Frame owner;

if (parent instanceof Frame)
   owner = (Frame) parent;
else
   owner = (Frame) SwingUtilities.getAncestorOfClass(Frame.class, parent);
```

我们在示例程序使用了这种增强功能。`JOptionPane` 类也使用了这种机制。

许多对话框有一个默认按钮，如果用户按下触发键（在大多数外观和感觉实现中为 Enter 键），该默认按钮会被自动选中。默认按钮会被特别标记，通常有一个加粗的轮廓。

在对话框的根面板（root pane）中设置默认按钮：

```java
dialog.getRootPane().setDefaultButton(okButton);
```

如果你遵循在面板中布局对话框的建议，那么你必须在将面板封装进对话框之后设置默认按钮。面板对话框本身没有根面板。

列表 11.13 是程序的帧类，说明了进入和对话框的数据流。列表 11.14 显示了对话框类。

**列表 11.13** `dataExchange/DataExchangeFrame.java`

```java
1   package dataExchange;

2
3   import java.awt.*;
4   import java.awt.event.*;
5   import javax.swing.*;

6
7   /**
8    * 一个带有菜单的帧，其 File->Connect 操作会显示密码对话框。
9    */

10  public class DataExchangeFrame extends JFrame
11    public static final TEXT_ROWS = 20;
12    public static final TEXT_COLUMNS = 40;
13    private PasswordChooser dialog = null;
14    private JTextArea textArea;

15
16    public DataExchangeFrame()
17    {
18      // 构造菜单
19      MenuBar mbar = new JMenuBar();
20      setMenuBar(mbar);
21      JMenu fileMenu = new JMenu("File");
22      mbar.add(fileMenu);

23      // 添加 Connect 和 Exit 项
24      JMenuItem connectItem = new JMenuItem("Connect");
25      connectItem.addActionListener(new ConnectAction());
26      fileMenu.add(connectItem);

27      // Exit 项退出程序
28      JMenuItem exitItem = new JMenuItem("Exit");
29      exitItem.addActionListener(event -> System.exit(0));
30      fileMenu.add(exitItem);

31      textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
32      add(new JScrollPane(textArea), BorderLayout.CENTER);
33      pack();
34    }

35    /**
36     * Connect 操作弹出密码对话框。
37     */
38    private class ConnectAction implements ActionListener
39    {
40      public void actionPerformed(ActionEvent event)
41      {
42          // 如果是第一次运行，构造对话框
43          if (dialog == null) dialog = new PasswordChooser();

44          // 设置默认值
45          dialog.setUser(new User("yourname", null));

46          // 弹出对话框
47          if (dialog.showDialog(DataExchangeFrame.this, "Connect"))
48          {
49              // 如果接受，检索用户输入
50              User u = dialog.getUser();
51              textArea.append("user name = " + u.getName() + ", password = "
52              + (new String(u.getPassword())) + "\n");
53          }
54      }
55    }
56  }
57  }
```

**列表 11.14** `dataExchange/PasswordChooser.java`

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
 * 一个显示在对话框中的密码选择器。
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
      var panel = new JPanel();
      panel.setLayout(new GridLayout(2, 2));
      panel.add(new JLabel("User name:"));
      panel.add(username = new JTextField(""));
      panel.add(new JLabel("Password:"));
      panel.add(password = new JPasswordField(""));
      add(panel, BorderLayout.CENTER);

      // 创建用于关闭对话框的确定和取消按钮
      okButton = new JButton("Ok");
      okButton.addActionListener(event ->
      {



`ok = true;`

`dialog.setVisible(false);`

`});`

`var cancelButton = new JButton("Cancel");`

`cancelButton.addActionListener(event -> dialog.setVisible(false));`

// 将按钮添加到南部边界

`var buttonPanel = new JPanel();`

`buttonPanel.add(okButton);`

`buttonPanel.add(cancelButton);`

`add(buttonPanel, BorderLayout.SOUTH);`

`}`

`/**`

`* 设置对话框默认值。`

`* @param u 默认用户信息`

`*/`

`public void setUser(User u)`

`{`

`username.setText(u.getName());`

`}`

`/**`

`* 获取对话框条目。`

`* @return 代表对话框条目的 User 对象状态`

`*/`

`public User()`

`{`

`return new User(username.getText(), password.getPassword());`

`}`

`/**`

`* 在对话框中显示选择器面板。`

`* @param parent 所有者框架中的组件或 null`

`* @param title 对话框标题`

`*/`

`public boolean showDialog(Component parent, String title)`

`{`

`ok = false;`

// 定位所有者框架

`Frame owner = null;`

`if (parent instanceof Frame)`

`owner = (Frame) parent;`

`else`

`owner = (Frame) SwingUtilities.getAncestorOfClass(Frame.class, parent);`

// 如果是第一次，或者所有者发生了变化，则新建对话框

`if (dialog == null || dialog.getOwner() != owner)`

`{`

`dialog = new JDialog(owner, true);`

`dialog.add(this);`

`dialog.getRootPane().setDefaultButton(okButton);`

`dialog.pack();`

`}`

// 设置标题并显示对话框

`dialog.setTitle(title);`

`dialog.setVisible(true);`

`return ok;`

`}`

`}`

`javax.swing.SwingUtilities`

- `Container getAncestorOfClass(Class c, Component comp)` 返回给定组件的最内层父容器，该容器属于指定的类或其任子类。

`javax.swing.JComponent`

- `JRootPane getRootPane()` 获取包含此组件的根面板，如果此组件没有具有根面板的祖先则返回 `null`。

`javax.swing.JRootPane`

- `void setDefaultButton(JButton button)` 设置此根面板的默认按钮。要停用默认按钮，请带 `null` 参数调用此方法。

`javax.swing.JButton`

- `boolean isDefaultButton()` 如果此按钮是其根面板的默认按钮，则返回 `true`。

## 11.7.4 文件对话框 (File Dialogs)

在应用程序中，你通常想要打开和保存文件。编写一个可以显示文件和目录并允许用户浏览文件系统的良好的文件对话框很难，而且你绝对不想重复轮子。幸运的是，Swing 提供了一个 `JFileChooser` 类，允许你显示一个与大多数原生应用程序类似的文件对话框。`JFileChooser` 对话框始终是模态的。请注意 `JFileChooser` 类并不是 `JDialog` 的子类。不要调用 `setVisible(true)`，而应调用 `showOpenDialog` 来显示打开文件的对话框，或调用 `showSaveDialog` 来显示保存文件的对话框。接受文件的按钮将自动标记为“打开”或“保存”。你也可以通过 `showDialog` 提供自己的按钮标签。

以下是建立文件对话框的步骤：

1. 创建 `JFileChooser` 对象。与 `JFileChooser` 构造函数不同，你不需要提供父组件。例如：

```
var chooser = new JFileChooser();
```

2. 通过调用 `setCurrentDirectory` 设置目录。例如，使用当前目录：

```
chooser.setCurrentDirectory(new File("."));
```

3. 如果你有一个期望用户选择默认默认，使用 `setSelectedFile` 方法提供它：

```
chooser.setSelectedFile(new File(filename));
```

4. 要允许用户在对话框中选择多个文件，调用 `setSelectionEnabled` 方法。这当然是完全可选的，而且并不常见。

```
chooser.setMultiSelectionEnabled(true);
```

5. 如果你想限制对话框中显示的文件为特定类型（例如，所有 `.gif` 扩展名的文件），你需要设置文件过滤器。我们将在本节稍后的部分讨论文件过滤器。

6. 默认情况下，用户可以使用文件选择器选择文件。如果你想让用户选择目录，使用 `setFileSelectionMode` 方法。调用 `JFileChooser.FILES_ONLY`（默认）、`JFileChooser.DIRECTORIES_ONLY` 或 `JFileChooser.FILES_AND_DIRECTORIES`。

7. 通过 `showOpenDialog` 或 `showSaveDialog` 方法显示对话框。在这些调用中你必须提供父组件：

```
int result = chooser.showOpenDialog(parent);
```

或

```
int result = chooser.showSaveDialog(parent);
```

这些调用之间的区别在于“确认按钮”的标签——用户点击以完成文件选择的按钮。你也可以调用 `showDialog` 方法并为确认按钮传递式文本：

```
int result = chooser.showDialog(parent, "Select");
```

## 8. 使用 `getSelectedFile()` 或 `getSelectedFiles()` 方法获取选定的文件或多个文件

这些方法返回单个 `File` 对象或一个 `File` 对象数组。如果你只需要文件对象的名称，可以调用它的 `getPath` 方法。例如：

```
String filename = chooser.getSelectedFile().getPath();
```

在大多数情况下，这些步骤都是简单的。使用文件对话框的主要困难在于指定用户应从中选择的文件子集。例如，假设用户应该选择 GIF 图像文件。那么，文件选择器应该只显示扩展名为 `.gif` 的文件。它还应该向用户提供某种反馈，说明显示的文件属于某个特定类别，例如“GIF 图片”。但情况可能会更加复杂。如果用户需要选择 JPEG 图像文件，扩展名可以是 `.jpg` 也可以是 `.jpeg`。为了避免通过编码来处理这些复杂性，文件选择器设计者提供了一种更优雅的机制：通过提供扩展 `javax.swing.filechooser.FileFilter` 抽象类的对象来限制显示的文件。文件选择器会将每个文件传递给文件过滤器，并只显示过滤器接受的文件。

在编写本文时，提供了两个此类子类：一个接受所有文件的默认过滤器，另一个接受具有特定扩展名文件的过滤器。然而，编写临时的文件过滤器非常简单。只需实现 `FileFilter` 超类的两个抽象方法即可：

```
public boolean accept(File f);
public String getDescription();
```

第一个方法测试文件是否应该被接受。第二个方法返回文件类型的描述，可以在文件选择器对话框中显示。

***

![Image](img/note.jpg) **注意：**

`java.io` 包中一个不相关的 `FileFilter` 接口只有一个方法 `boolean accept(File f)`。它被用于 `File` 类的 `listFiles` 方法，以列出目录中的文件。我不知道为什么 Swing 的设计者没有扩展这个接口——也许 Java 类库现在已经变得如此复杂，以至于 Sun 的程序员也不再了解所有的标准类和接口。

如果你同时导入 `java.io` 和 `javax.swing.filechooser` 包，你需要解决这两个同名类型之间的命名冲突。最简单的解决方法是导入 `javax.swing.filechooser.FileFilter`，而不是 `javax.swing.filechooser.*`。

***

一旦你有了文件过滤器对象，请使用 `JFileChooser` 类的 `setFileFilter` 方法将其安装到文件选择器对象中：

```
chooser.setFileFilter(new FileNameExtensionFilter("Image files", "gif", "jpg"));
```

你可以通过调用以下方法为文件选择器安装多个过滤器：

```
chooser.addChoosableFileFilter(filter1);
chooser.addChoosableFileFilter(filter2);
. . .
```

用户从文件对话框底部的组合框中选择过滤器。默认情况下，“所有文件”过滤器始终出现在组合框中。这是一个好主意——以防你的程序用户需要选择具有非标准扩展名的文件。然而，如果你想抑制“所有文件”过滤器，请调用：

```
chooser.setAcceptAllFileFilterUsed(false)
```

***

![Image](img/caution.jpg) **警告：**

如果你重用同一个文件选择器来加载和保存不同类型的文件，请调用：

```
chooser.resetChoosableFilters()
```

在添加新过滤器之前，清除任何旧的过滤器。

***

最后，你可以通过为文件选择器显示的每个文件提供特殊的图标和文件描述来自定义文件选择器。通过提供一个扩展 `javax.swing.filechooser` 包中 `FileView` 类的对象来实现。这绝对是一项高级技术。通常，你不需要提供文件视图——可插的外观（look-and-feel）会为你提供一个。但如果你想为特殊文件类型显示不同的图标，你可以安装自己的文件视图。你需要扩展 `FileView` 类并实现五个方法：

```
Icon getIcon(File f)
String getName(File f)
String getDescription(File f)
String getTypeDescription(File f)
Boolean isTraversable(File f)
```

然后，使用 `setFileView` 方法将你的文件视图安装到文件选择器。

文件选择器会对想要显示的每个文件或目录调用你的方法。如果你的方法对图标、名称或描述返回 `null`，则文件选择器将查询外观的默认文件视图。这是好事，因为你只需要处理你想要进行特殊处理的文件类型。

文件选择器调用 `isTraversable` 方法来决定当用户点击目录时是否打开它。注意，该方法返回一个 `Boolean` 对象，而不是 `boolean` 值！这看起来很奇怪，但实际上非常方便——如果你不感兴趣偏离默认文件视图，只需返回 `null`。文件选择器将查询默认文件视图。换句话说，该方法返回一个 `Boolean` 让你在三个选项之间选择：真 (`Boolean.TRUE`)、假 (`Boolean.FALSE`) 或不关乎 (`null`)。

示例程序包含一个简单的文件视图类。该类每当文件匹配文件过滤器时都会显示一个特定的图标。我们使用它为所有图像文件显示调色板图标。

```
class FileIconView extends FileView
{
  private FileFilter filter;
  private Icon icon;

  public FileIconView(FileFilter filter, Icon icon)
  {
      filter = filter;
      icon = icon;
  }

  public Icon getIcon(File f)
  {
      if (!f.isDirectory() && filter.accept(f))
      return icon;
      else return null;
  }
 }
```

使用 `setFileView` 方法将此文件视图安装到你的文件选择器中：

```
chooser.setFileView(new FileIconView(filter, new ImageIcon("palette.gif")));
```



此后，文件选择器将在所有通过`filter`的文件旁边显示调色板图标。

- `void setSelectedFile(File file)`
- `void setSelectedFiles(File[] file)`

设置文件对话框的默认文件选择。

- `void setMultiSelectionEnabled(boolean b)`

设置或清除多选模式。

- `void setFileSelectionMode(int mode)`

允许用户仅选择文件（默认）、仅选择目录，或同时选择文件和目录。`mode`参数是`JFileChooser.FILES_ONLY`、`JFileChooser.DIRECTORIES_ONLY`和`JFileChooser.FILES_AND_DIRECTORIES`之一。

- `int showOpenDialog(Component parent)`
- `int showSaveDialog(Component parent)`
- `int showDialog(Component parent, String approveButtonText)`

显示一个对话框，其中确认按钮标记为“打开”、“保存”或`approveButtonText`字符串。返回`APPROVE_OPTION`、`CANCEL_OPTION`（如果用户选择了取消或关闭了对话框）或`ERROR_OPTION`（如果发生错误）。

- `File getSelectedFile()`
- `File[] getSelectedFiles()`

获取用户选择的文件或文件（如果用户没有选择任何文件，则返回`null`）。

- `void setFileFilter(FileFilter filter)`

设置文件对话框的文件掩码。所有`filter.accept`返回`true`的文件都将显示。同时，将该过滤器添加到可选过滤器列表中。

- `void addChoosableFileFilter(FileFilter filter)`

将文件过滤器添加到可选过滤器列表中。

- `void setAcceptAllFileFilterUsed(boolean b)`

在过滤器组合框中包含或抑制“所有文件”的过滤器。

- `void resetChoosableFileFilters()`

清除可选过滤器列表。除非被显式抑制，否则只保留“所有文件”过滤器。

- `void setFileView(FileView view)`

设置文件视图，以提供有关文件选择器所显示的文件的信息。

- `void setAccessory(JComponent component)`

设置一个配件组件。

### `javax.swing.filechooser.FileFilter` 1.2

- `boolean accept(File f)`

如果文件选择器应该显示此文件，则返回`true`。

- `String getDescription()`

返回此文件过滤器的描述——例如`"Image files (*.gif,*.jpeg)"`。

### `javax.swing.filechooser.FileNameExtensionFilter` 6

- `FileNameExtensionFilter(String description, String... extensions)`

根据给定的描述构造文件过滤器，该过滤器接受所有目录以及所有文件名以点后接给定的扩展名字符串之一结尾的文件。

### `javax.swing.filechooser.FileView` 1.2

- `String getName(File f)`

返回文件`f`的名称，或返回`null`。通常情况下，此方法直接返回`f.getName()`。

- `String getDescription(File f)`

返回文件`f`的可读描述，或返回`null`。例如，如果`f`是一个 HTML 文档，此方法可能会返回它的标题。

- `String getTypeDescription(File f)`

返回文件`f`类型的可读描述，或返回`null`。例如，如果`f`是一个 HTML 文档，此方法可能会返回字符串`"Hypertext document"`。

- `Icon getIcon(File f)`

返回文件`f`的图标，或返回`null`。例如，如果`f`是一个 JPEG 文件，此方法可能会返回缩略图图标。

- `Boolean isTraversable(File f)`

如果`f`是用户可以打开的目录，则返回`Boolean.TRUE`。如果目录在概念上是一个复合文档，此方法可能会返回`Boolean.FALSE`。与所有的`FileView`方法一样，此方法可以返回`null`，表示文件选择器应该咨询默认视图。

关于 Swing 编程的讨论此此。请参阅第二卷获取高级 Swing 组件和复杂的图形技术。

## 第 12 章 并发

本章内容

- 12.1 什么是线程？
- 12.2 线程状态
- 12.3 线程属性
- 12.4 同步
- 12.5 线程安全集合
- 12.6 任务与线程池
- 12.7 异步计算
- 12.8 进程

你可能对多任务处理很熟悉——你的操作系统能够让多个程序在看似的同时运行。例如，你可以在编辑或下载电子邮件时进行打印。如今，你可能有一台带有多个 CPU 的计算机，但并发执行的进程数量并不限于 CPU 的数量。操作系统为每个进程分配 CPU 时间片，从而产生并行活动的印象。

多线程程序通过将此想法进一步降低来扩展多任务处理：单个程序似乎同时执行多个任务。每个任务都在一个`thread`（控制线程的缩写）中执行。能够同时运行多个线程的程序被称为多线程程序。

### 12.1 什么是线程？

让我们先来看一个使用两个线程的简单程序。该程序在不同账户之间转移资金。第一个线程将资金从账户 0 转移到 1。第二个线程将资金从账户 2 转移到 3。

以下是在独立线程中运行任务的简单步骤：

1. 将任务代码放入实现`Runnable`接口的类的`run`方法中。该接口非常简单，只有一个方法：

```
public interface Runnable
{
  void run();
}
```

由于`Runnable`是一个函数式接口，你可以使用 lambda 表达式创建一个实例：

```
Runnable r = () -> {
  // task
};
```

2. 从`Runnable`构造一个`Thread`对象：

```
var t = new Thread(r);
```

3. 启动线程：

```
t.start();
```

为了转移资金创建一个独立线程，我们只需要将转移代码放在`Runnable`的`run`方法中，然后启动线程：

```java
Runnable r = () -> {
  try {
    for (int i = 0; i < STEPS; i++) {
      double amount = MAX_AMOUNT * Math.random();
      bank.transfer(0, 1, amount);
      Thread.sleep((int) (DELAY * Math.random()));
    }
  } catch (InterruptedException e) {
  }
};

var t = new Thread(r);
t.start();
```

对于给定的步数，此线程会转移一个随机金额，然后随机休眠一段时间。

我们需要捕获`sleep`方法可能抛出的`InterruptedException`。我们将在第 757 页的第 12.3.1 “中断线程”中讨论此异常。通常，中断用于请求线程终止。因此，当发生`InterruptedException`时，我们的`run`方法就会退出。

我们的程序还启动了第二个线程，将资金从账户 2 转移到账户 3。当你运行该程序时，你会得到如下所示输出：

```
Thread[Thread-1,5,main]  606.77 from 2 to 3 Total Balance:  400000.00
Thread[Thread-0,5,main]    98.99 from 0 to 1 Total Balance:  400000.00
Thread[Thread-1,5,main]  476.78 from 2 to 3 Total Balance:  400000.00
Thread[Thread-0,5,main]  653.64 from 0 to 1 Total Balance:  400000.00
Thread[Thread-1,5,main]  807.14 from 2 to 3 Total Balance:  400000.00
Thread[Thread-0,5,main]  481.49 from 0 to 1 Total Balance:  400000.00Thread[Thread-0,5,main]  203.73 from 0 to 1 Total Balance:  400000.00
Thread[Thread-1,5,main]  111.76 from 2 to 3 Total Balance:  400000.00
Thread[Thread-1,5,main]  794.88 from 2 to 3 Total Balance:  400000.00
. . .
```

如你所见，两个线程的输出是交错的，这表明它们正在并发运行。事实上，当两行输出交错在一起时，输出有时会显得有点杂乱。

就这些了！你现在知道如何并发运行任务。本章的剩余部分将告诉你如何控制线程之间的交互。

完整的代码如代码列表 12.1 所示。

***

![Image](img/note.jpg) **注意：**

你也可以通过创建`Thread`类的子类来定义线程，如下：

```
class MyThread extends Thread
{
  public void run()
  {
    task code
  }
}
```

然后，你构造该子类的对象并调用它的`start`方法。然而，不再推荐这种方法。你应该将要运行的*任务*与运行任务的*机制*解耦。如果你有许多任务，为每个任务创建一个单独的线程开销太大。相反，你可以使用线程池——参见第 818 页的第 12.6.2 “执行器”。

***

![Image](img/caution.jpg) **警告：**

*不要*调用`Thread`类的`run`方法或`Runnable`对象的`run`方法。直接调用`run`方法仅仅是在*相同*线程中执行任务——而不会启动新线程。请调用`Thread.start`方法。它会创建一个执行`run`方法的新线程。

***

**代码列表 12.1** `threads/ThreadTest.java`

```
 1  package threads;
 2
 3  /**
 4   * @version 1.30 2004-08-01
 5   * @author Cay Horstmann
 6   */
 7  public class ThreadTest
 8  {
 9    public static final int DELAY = 10;
10    public static final int STEPS = 100;
11    public static final double MAX_AMOUNT = 1000;
12
13    public static void main(String[] args)
14    {
15      var bank = new Bank(4, 100000);
16      Runnable task1 = () ->
17      {
18        try
19        {
20          for (int i = 0; i < STEPS; i++)
21          {
22            double amount = MAX_AMOUNT * Math.random();
23            bank.transfer(0, 1);
24            Thread.sleep((int) (DELAY * Math.random()));
25          }
26        }
27        catch (InterruptedException e)
28        {
29        }
30      };
31
32      Runnable task2 = () ->
33      {
34        try
35        {
36          for (int i = 0; i < STEPS; i++)
37          {
38            double amount = MAX_AMOUNT * Math.random();
39            bank.transfer(2, 3, amount);
40            Thread.sleep((int) (DELAY * Math.random()));
41          }
42        }
43        catch (InterruptedException e)
44        {
45        }
46      };
47
48      new Thread(task1).start();
49      new Thread(task2).start();
50    }
```

**代码列表 12.2** `threads/Bank.java`

```
 1  package threads;
 2
 3  import java.util.*;
 4
 5  /**
 6   * 具有数量账户的银行。
 7   */
 8  public class Bank
 9  {
10    private final double[] accounts;
11
12    /**
13      * 银行。
14      * @param n 账户数量
15      * @param initialBalance 每个账户的初始余额
16      */
17    public Bank(int n, double initialBalance)
18    {
19      accounts = new double[n];
20      Arrays.fill(accounts, initialBalance);
21    }
22
23    /**
24      * 将资金从一个账户转移到另一个账户。
25      * @param from 转出账户
26      * @param to 转入账户
27      * @param amount 转移金额
28      */
29    public void transfer(int from, int to, double amount)
30    {
31      if (accounts[from] < amount) return;
32      System.out.printf(" %.2f from %d to %d", amount, from, to);
33      accounts[from] -= amount;
34      accounts[to] += amount;
35      System.out.printf(" Total Balance: %.2f%n", getTotalBalance());
36    }
37
38    /**
39      * 获取所有余额的总和。
40      * @return 总余额
41      */
42    public double getTotalBalance()
43    {
44      double sum = 0;
45
46      for (double a : accounts)
47        sum += a;
48      return sum;
49    }
50
51    /**
52      * 获取账户数量。
53      * @return 账户数量
54      */
55    public int size()
56    {
57      return accounts.length;
58    }
59  }
```



一旦线程开始运行，它并不一定持续运行。事实上，让运行中的线程偶尔暂停是理想的，这样其他线程才有机会运行。线程调度的具体细节取决于操作系统提供的服务。抢占式调度系统为每个可运行的线程分配一个时间片来执行其任务。当该时间片用尽时，操作系统会抢占该线程，并给予另一个线程工作的机会（参见图 12.2）。在选择下一个线程时，操作系统会考虑线程优先级——更多信息请参见第 763 页的第 12.3.5 节“线程优先级”。

所有现代桌面操作系统和服务器操作系统都使用抢占式调度。然而，手机等小型设备可能会使用协作式调度。在这样的设备中，线程只有在调用 `yield` 方法、或者被阻塞或等待时，才会失去控制权。

在具有多个处理器的机器上，每个处理器都可以运行一个线程，你可以让多个线程并行运行。当然，如果线程数量多于处理器，调度器仍然必须进行时间分片。

始终记住，一个可运行的线程在任何时刻可能运行，也可能不运行。（这就是为什么该状态被称为“可运行”（runnable）而不是“运行中”（running）。）

### `java.lang.Thread` 1.0

- `static void yield()` 使当前执行的线程让给另一个线程。注意这是一个静态方法。

#### 12.2.3 阻塞和等待线程

当线程被阻塞或等待时，它处于临时不活跃状态。它不执行任何代码且消耗极少的资源。重新激活它取决于线程调度器，具体取决于是如何进入不活跃状态的。

- 当线程尝试获取当前由另一个线程持有的内部对象锁（但不是 `java.util.concurrent` 库中的 `Lock`）时，它变为阻塞状态。（我们在第 769 页的第 12.4.3 节中讨论 `java.util.concurrent` 锁、锁对象，以及在第 778 页的第 12.4.5 节中讨论内部对象锁、`synchronized` 关键字。）当所有其他线程都释放锁且线程调度器允许该线程持有锁时，该线程变为未阻塞。
- 当线程等待另一个线程通知调度器某个条件时，它进入等待状态。我们在第 772 页的第 12.4.4 节中讨论条件、条件对象。这通过调用 `Object.wait` 或 `Thread.join` 方法，或者等待 `java.util.concurrent` 库中的 `Lock` 或 `Condition` 来实现。在实践中，阻塞状态和等待状态之间的区别并不显著。
- 几个方法带有超时参数。调用它们会导致线程进入超时等待状态。该状态一直持续，直到超时过期或收到适当的通知。带有超时的方法包括 `Thread.sleep` 以及 `Object.wait`、`Thread.join`、`Lock.tryLock` 和 `Condition.await` 的超时版本。

图 12.1 显示了线程可以处于的状态以及从一个状态到另一个状态的可能转换。当线程被阻塞或等待时（当然，当它终止运行时），将调度另一个线程。当线程被重新激活时（例如，因为超时过期或成功获取了锁），调度器会检查它的优先级是否比当前运行的线程高。如果是，它将抢占当前线程之一并选择一个新线程运行。

![Images](img/12fig01.jpg)

**图 12.1** 线程状态

#### 12.2.4 已终止的线程

线程的终止有两个原因：

- 它因为 `run` 方法正常退出而自然死亡。
- 它因为未捕获的异常终止了 `run` 方法而突然死亡。

特别地，你可以通过调用它的 `stop` 方法来杀死线程。该方法会抛出一个 `ThreadDeath` 错误对象并杀死线程。然而，`stop` 方法已过时，你不应该在自己的代码中调用它。

### `java.lang.Thread` 1.0

- `void join()` 等待指定的线程终止。
- `void join(long millis)` 等待指定的线程死亡或等待指定的毫秒数。
- `Thread.State getState()` 获取此线程的状态：`NEW`、`RUNNABLE`、`BLOCKED`、`WAITING`、`TIMED_WAITING` 或 `TERMINATED`。
- `void stop()` 停止线程。该方法已过时。
- `void suspend()` 挂起此线程的执行。该方法已标记为删除。
- `void resume()` 恢复此线程。

### 12.3 属性

在接下来的章节中，我们将讨论属性：中断状态、守护线程以及未捕获的异常。

#### 12.3.1 中断线程

当线程被中断时，它的中断状态会被设置。然而，这并不意味着会停止线程。

`isInterrupted` 检查在你在每次工作迭代后都调用 `sleep` 方法（或另一个可中断的方法）时，既没有必要也没有用。如果你在中断状态被设置时调用 `sleep` 方法，它不会睡眠。相反，它会清除该状态（！！）并抛出一个 `InterruptedException`。因此，如果你的循环调用了 `sleep`，请不要检查中断状态。相反，请这样捕获 `InterruptedException`：

```java
Runnable r = () ->
{
    try
    {
        . . .

        while (more work to do)
        {
            do more work
            Thread.sleep(delay);
        }
    }
    catch (InterruptedException e)
    {
        // thread was interrupted during sleep
    }
    finally
    {
        cleanup, if required
    }

    // exiting the run method terminates the thread
};
```

![Image](img/note.jpg)

**注意：**

有两个非常相似的方法：`interrupted` 和 `isInterrupted`。`interrupted` 方法是一个静态方法，用于检查*当前*线程是否被中断。此外，调用 `interrupted` 方法会*清除*线程的中断状态。另一方面，`isInterrupted` 方法是一个实例方法，你可以用它来检查任何线程是否被中断。调用它不会改变中断状态。

你会在很多已发表的代码中看到 `InterruptedException` 在底层被静默忽略了，如下所示：

```java
void mySubTask()
{
    . . .

    try
    {
        sleep(delay);
    }
    catch (InterruptedException e)
    {
    }

    // don't ignore!
    . . .
}
```

不要这样做！如果你无法在 `catch` 子句中想出任何好的做法，你仍然有两个合理的选择：

- 在 `catch` 子句中，调用 `Thread.currentThread().interrupt()` 来设置中断状态。然后调用者可以对其进行测试。

```java
void mySubTask()
{
    . . .

    try
    {
        sleep(delay);
    }
    catch (InterruptedException e)
    {
        Thread.currentThread().interrupt();
    }

    . . .
}
```

- 或者，更好的是，用你的方法标记 `throws InterruptedException` 并丢弃 `try` 块。然后调用者（或者最终的 `run` 方法）可以捕获它。

```java
void mySubTask() throws InterruptedException
{
    . . .

    sleep(delay);

    . . .
}
```

### `java.lang.Thread` 1.0

- `void interrupt()` 向线程发送中断请求。线程的中断状态被设置为 `true`。如果线程当前正被 `sleep` 调用所阻塞，则会抛出一个 `InterruptedException`。
- `static boolean interrupted()` 测试*当前*线程（即正在执行此指令的线程）是否被中断。注意，这是一个静态方法。该调用具有副作用——它会将当前线程的中断状态重置为 `false`。
- `boolean isInterrupted()` 测试线程是否被中断。与静态 `interrupted` 方法不同，此调用不会改变线程的中断状态。
- `static Thread currentThread()` 返回代表正在执行线程的 `Thread` 对象。

#### 12.3.2 守护线程

你可以通过调用以下代码将线程转换为*守护线程*：

```java
t.setDaemon(true);
```

这种线程并没有什么“魔性”。守护线程仅仅是在生命中除了服务他人之外没有其他角色的线程。例如向其他线程发送定期“定时器滴答”的定时器线程，或者清理过期缓存条目的线程。当只剩下守护线程时，虚拟机就会退出。如果剩余线程都是守护线程，那么保持程序运行就没有意义了。

### `java.lang.Thread` 1.0

- `void setDaemon(boolean isDaemon)` 将此线程标记为守护线程或用户线程。此方法必须在线程启动之前调用。

#### 12.3.3 线程名称

默认，线程具有如 `Thread-2` 这样易于记忆的名字。你可以使用 `setName` 方法设置任何名称：

```java
var t = new Thread(runnable);

t.setName("Web crawler");
```

这在线程转储中可能很有用。

#### 12.3.4 用于未捕获异常的处理器

线程的 `run` 方法不能抛出任何检查异常，但它可能会被未检查异常终止。在这种情况下，线程会死亡。

然而，没有 `catch` 子句可以传播该异常。相反，在线程死亡之前，异常会被传递给处理器。

当线程调度器有机会选择新线程时，它会倾向于选择优先级更高的线程。然而，线程优先级是*高度依赖系统的*。当虚拟机依赖于宿主平台的线程实现时，Java 线程优先级会被映射到宿主平台的优先级级别，而宿主平台可能有更多或更少的线程优先级级别。

例如，Windows 有七个优先级级别。某些 Java 优先级将映射到相同的操作系统级别。在用于 Linux 的 Oracle JVM 中，线程优先级完全被忽略了——所有线程具有相同的优先级。

线程优先级在没有使用操作系统线程的 Java 早期版本中可能有用。但现在你不应该再使用它们。

### `java.lang.Thread` 1.0

- `void setPriority(int newPriority)` 设置此线程的优先级。优先级必须在 `Thread.MIN_PRIORITY` 和 `Thread.MAX_PRIORITY` 之间。使用 `Thread.NORM_PRIORITY` 设置普通优先级。
- `static int MIN_PRIORITY` 是 `Thread` 可以拥有的最低优先级。最小优先级值为 `1`。
- `static int NORM_PRIORITY` 是 `Thread` 的默认优先级。默认优先级为 `5`。
- `static int MAX_PRIORITY` 是 `Thread` 可以拥有的最高优先级。最大优先级值为 `10`。

### 12.4 同步

在大多数实际的多线程应用中，两个或多个线程需要共享访问同一数据。如果两个线程访问同一个对象，并且每个调用修改该对象状态的方法会发生什么？正如你想象的，线程可能会相互干扰。取决于访问数据的顺序，可能会导致对象损坏。这种情况通常被称为*竞态条件*（race condition）。

#### 12.4.1 竞态条件示例

为了避免多个线程对共享数据造成损坏，你必须学会如何*同步访问*。在本节中，你将看到如果不使用同步会发生什么。在下一节中，你将看到如何同步数据访问。

在接下来的测试程序中，我们继续操作我们的模拟银行。与第 12.1 节第 748 页的“什么是线程？”中的示例不同，我们随机选择转账的源账户和目的账户。由于这会导致问题，让我们仔细查看一下 `Bank` 类中 `transfer` 方法的代码。

```java
public void transfer(int from, int to, double amount)

// CAUTION: 当从多个线程调用时是不安全的

{
    System.out.print(Thread.currentThread());

    accounts[from] -= amount;

    System.out.printf(" %10.2f %d to %d", amount, from, to);

    accounts[to] += amount;

    System.out.printf(" Total Balance:%10.2f%n", getTotalBalance());
}
```

这里是 `Runnable` 实例的代码。`run` 方法不断地离开给定的银行。在每次迭代中，`run` 方法会随机选择一个账户和一个随机金额，调用银行的 `transfer` 方法然后睡眠。

```java
Runnable r = () -> {
    try {
        while (true) {
            int toAccount = (int) (bank.size() * Math.random());
            double amount = MAX_AMOUNT * Math.random();

            bank.transfer(fromAccount, toAccount, amount);

            Thread.sleep((int) (DELAY * Math.random()));
        }
    }
    catch (InterruptedException e) {
    }
};
```

当此模拟运行时，我们不知道在任何时候任何一个账户中有多少钱。但我们知道所有账户的总金额应该保持不变，因为我们做的只是从一个账户移动到另一个账户。在每笔交易结束时，`transfer` 方法会重新计算总和并打印。这个程序永远不会结束。只需按 Ctrl+C 杀死程序即可。这是一个典型的输出：

```
...

[Thread-11,5,main]  588.48 from 11 to 44 Total Balance: 100000.00

[Thread-12,5,main]  976.11 from 12 to 22 Total Balance: 100000.00

[Thread-14,5,main]  521.51 from 14 to 22 Total Balance: 100000.00

[Thread-13,5,main]  359.89 from 13 to 81 Total Balance: 100000.00

...

[Thread-36,5,main]  401.71 from 36 to 73 Total Balance: 99291.06

[Thread-35,5,main]  691.46 from 35 to 77 Total Balance: 99291.06

[Thread-37,5,main]  78.64 from 37 to 3 Total Balance: 99291.06

[Thread-34,5,main]  197.11 from 34 to 69 Total Balance: 99291.06

[Thread-36,5,main]  85.96 from 36 to 4 Total Balance: 99291.06

...

[Thread-4,5,main][Thread-33,5,main]   7.31 from 31 to 32 Total Balance: 99979.24

      627.50 from 4 to 5 Total Balance: 99979.24

...
```

如你所见，有些非常不对。对于几次交易，银行余额保持在 $100,000，这是 100 个每个 $1,000 账户的正确总额。但一段时间后，余额发生了微变化。当你运行此程序时，错误可能会很快发生，或者余额可能需要很长时间才会损坏。这种情况并不令人产生信心，你可能不想在这样的银行存入辛苦赚的钱。看看你是否能发现列表 12.3 中的代码和列表 12.2 中 `Bank` 类中的问题。我们将在下一节解开这个谜团。

#### 12.3 `unsynch/UnsynTest.java`

```java
package unsynch;

/**
 * 当多个线程访问数据结构时显示损坏情况。
 * @version 1.3 2018-04-10
 * @author Caymann
 */

public class UnsynTest {
    static final int ACCOUNTS = 100;
    static final double INITIAL_BALANCE = 1000;
    static final double MAX_AMOUNT = 100;
    static final int DELAY = 10;

    public static void main(String[] args) {
        var bank = new Bank(ACCOUNTS, INITIAL_BALANCE);

        for (int i = 0; i < ACCOUNTS; i++) {
```



```java
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

var t = new Thread(r);
t.start();
```

#### 12.4.2 竞态条件的解释

在上一节中，我们运行了一个多个线程更新账户余额的程序。一段时间后，错误悄悄出现，某些金额丢失或凭空产生。这个问题发生在两个线程同时尝试更新账户时。假设两个线程同时执行指令：

```java
accounts[to] += amount;
```

问题在于这些不是*原子性*操作。该指令可能会如下处理：

1. 将 `accounts[to]` 加载到寄存器。
2. 加上 `amount`。
3. 将结果移回 `accounts[to]`。

现在，假设第一个线程执行了步骤 1 和 2 步，然后它被抢占了。假设第二个线程醒来并更新账户数组中的同一项。然后，第一个线程醒来并完成它的步骤 3。

该操作消除了另一个线程的修改。结果是总额不再正确（见图 12.2）。

我们的测试程序检测到了这种损坏。（当然，如果线程在执行测试时被中断，会有极小的概率出现误报！）

---

![Image](img/note.jpg) **注意：**

实际上，你可以查看执行我们类中每条语句的虚拟机字节码。运行以下命令：

```bash
javap -c -v Bank
```

来反编译 `Bank.class` 文件。例如，这一行：

```java
accounts[to] += amount;
```

被翻译为以下字节码：

```text
aload_0
getfield       #2; //Field accounts:D
iload_2
dup2
daload
dload_3
dadd
dastore
```

这些代码的含义并不重要。点在于，自增命令是由几条指令组成的，而执行这些指令的线程可以在任何指令处被中断。

---

这种损坏发生的概率有多大？在具有多核现代处理器上，损坏的风险很高。我通过将打印语句与更新余额的语句交替执行，增加了在单核处理器上观察到该问题的概率。

如果你省略了打印语句，损坏的风险就会降低，因为每个线程在再次进入睡眠之前的工作极少，调度器不太可能在计算过程中抢占它。然而，损坏的风险并没有完全消失。如果你在负载严重的机器上运行大量线程，即使你删除了打印语句，程序仍然会失败。这种失败可能在几分钟、几小时或几天后发生。坦率地说，对于程序员来说，没有比只有不规律才出现的错误更糟糕的事情了。

真正的问题是，`transfer` 方法的工作可能会中间被中断。如果我们能确保方法在线程失去控制权之前运行完毕，银行账户对象的状态就永远不会损坏。

#### 12.4.3 锁对象

有两种机制可以保护代码块免受并发访问。Java 语言为此目的提供了一个 `synchronized` 关键字，而 Java 5 引入了 `ReentrantLock` 类。`synchronized` 关键字会自动提供锁以及相关的“条件（condition）”，这使得它对于大多数需要显式锁的情况来说既强大又方便。然而，我相信，在单独查看了锁和条件之后，对 `synchronized` 关键字会更容易理解。`java.util.concurrent` 框架为这些基础机制提供了单独的类，在这里以及第 772 页的[第 12.4.4 节 “条件对象”中进行了解释。一旦你理解了这些构建组件，我将在第 778 页的第 12.4.5 节 “`synchronized` 关键字”中介绍 `synchronized` 关键字。

使用 `ReentrantLock` 保护代码块的基本轮廓如下：

```java
myLock.lock(); // 一个 ReentrantLock 对象

try {
    临界区
} finally {
    myLock.unlock(); // 即使抛出异常也能确保解锁
}
```

这种结构保证了一次只有一个线程可以进入临界区。一旦一个线程锁定了锁对象，其他线程就无法通过 `lock` 语句。当其他线程调用 `lock` 时，它们会被去激活状态，直到第一个线程释放锁对象。

---

![Image](img/caution.jpg) **警告：**

将 `unlock` 操作封装在 `finally` 句中至关重要。如果临界区中的代码抛出异常，必须解锁。否则，其他线程将被永久阻塞。

---

![Image](img/note.jpg) **注意：**

当你使用锁时，无法使用 `try`-with-resources 语句。首先，`unlock` 方法并不叫 `close`。但即使它被重命名，`try`-with-resources 语句也不有效。它的头部期望声明一个新的变量。但当你使用锁时，你希望继续使用线程间共享的同一个变量。

让我们使用锁来保护 `Bank` 类的 `transfer` 方法。

```java
public class Bank {
    private Lock bankLock = new ReentrantLock();

    . . .

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

假设一个线程调用 `transfer` 并在完成之前被抢占。假设第二个线程调用 `transfer`。第二个线程无法获取锁并被阻塞。等待第一个线程完成。当第一个线程释放锁时，第二个线程就可以继续执行。

公平性听起来很美好，但公平锁（fair locks）比普通锁慢得多。只有当你真正清楚自己在做什么，并且有理由认为公平性对你的程序至关重要时，才应该启用公平锁。即使你使用了公平锁，也不能保证线程调度器是公平的。如果线程调度器选择忽略一个等待锁已久的线程，那么该线程就没有机会被锁公平对待的机会。

#### 12.4.4 条件对象

线程经常会进入临界区域，结果发现自己在某个条件满足之前无法继续执行。使用条件对象（condition object）来管理已获取锁但无法进行有用工作的线程。在本节中，我将介绍 Java 库中条件对象的实现。（出于历史原因，条件对象通常被称为条件变量。）

让我们完善对银行的模拟。我们不想从一个没有资金支付转账的账户转账。注意，我们不能使用如下代码：

```java
if (bank.getBalance(from) >= amount)
    bank.transfer(from, to, amount);
```

当前线程在测试结果成功和调用 `transfer` 之间完全有可能被停用。

```java
if (bank.getBalance(from) >= amount)
    // 线程在此处可能被停用
    bank.transfer(from, to, amount);
```

当线程再次运行时，账户余额可能已经低于取款金额。你必须确保在测试和转账操作之间，没有其他线程可以修改余额。你通过用锁保护测试和转账操作来实现这一点：

```java
public void transfer(int from, int to, int amount) {
    bankLock.lock();
    try {
        while (accounts[from] < amount) {
            // 等
            . . .
        }

        // 转账资金
        . . .
    } finally {
        bankLock.unlock();
    }
}
```

现在，当账户中钱不足时，该怎么办？我们等待其他线程增加资金。但这个线程刚刚获得了 `bankLock` 的独占访问权限，因此没有其他线程有机会存款。这就是条件对象大显身场的地方。

锁对象可以有一个或多个关联条件对象。你通过 `newCondition` 方法获取条件对象。习惯上是为每个条件对象命名，使其能唤起它所代表的条件。例如，在这里我们设置了一个条件对象来代表“资金充足”条件。

```java
class Bank {
    private Condition sufficientFunds;

    . . .

    public Bank() {
        . . .
        sufficientFunds = bankLock.newCondition();
    }
}
```

如果 `transfer` 方法发现资金不足，它会调用：

```java
sufficientFunds.await();
```

当前线程现在被停用并放弃锁。这让另一个线程进入，我们希望它能增加账户余额。

等待获取锁的线程与调用 `await` 的线程之间存在本质的区别。一旦线程调用了 `await` 方法，它就会进入该条件的等待集（wait set）。当锁可用时，线程并不会变为可运行状态。相反，它会保持停用，直到另一个线程在同一个条件上调用了 `signalAll` 方法。

当另一个线程完成转账后，它应该调用：

```java
sufficientFunds.signalAll();
```

此调用会激活所有等待该条件的线程。当线程从等待集中中移除时，它们再次变为可运行状态，调度器最终会再次激活它们。那时，它们将尝试重新进入对象。一旦锁可用，其中一个线程将获取锁并从上次停止的地方继续执行，从 `await` 调用处返回。

此时，线程应该再次测试该条件。无法保证该条件现在已经满足——`signalAll` 方法仅仅向等待的线程发出信号，表明现在可能已经满足，值得再次检查该条件。

![Image](img/note.jpg) **注意：**

通常，对 `await` 的调用应该放在如下形式的循环内部：

```java
while (!(OK to proceed))
    condition.await();
```

其他线程最终必须调用 `signalAll` 方法是至关重要的。当线程调用 `await` 时，它没有办法重新激活自己。它寄希望于其他线程。如果它们中没有一个线程去激活等待的线程，那么它将永远不会运行。

![Image](img/caution.jpg) **警告：**

线程只有在拥有条件的锁的情况下，才能对该条件调用 `await`、`signalAll` 或 `signal`。

在实践中，正确使用条件可能非常有挑战性。在你开始实现自己的条件对象之前，应该考虑使用第 12.5 节 第 797 页的“线程安全集合”中描述的构造。

如果你运行列表 12.4 中的示例程序，你会发现没有任何问题发生。总余额永远保持在 $100,000。任何账户都不会出现负余额。（再次，按 Ctrl+C 终止程序。）你可能还会注意到程序运行得慢一点——这就是你为同步机制涉及的额外账目工作所付出的代价。

**列表 12.4** `synch/Bank.java`

```java
package synch;

import java.util.*;
import java.util.concurrent.locks.*;

/**
 * 一个拥有多个银行账户并使用锁来实现序列化访问的银行。
 */
public class Bank10 {
    private final double[] accounts;
    private Lock bankLock;
    private Condition sufficientFunds;

    /**
     * 构造银行。
     * @param n 账户的数量
     * @param initialBalance 每个账户的初始余额
     */
    public Bank(int n, double initialBalance) {
        accounts = new double[n];
        Arrays.fill(accounts, initialBalance);
        bankLock = new ReentrantLock();
        sufficientFunds = bankLock.newCondition();
    }

    /**
     * 将资金从一个账户转移到另一个账户。
     * @param from 从转出的账户
     * @param to 转入的账户
     * @param amount 要转移的金额
     */
    public void transfer(int from, int to, double amount) throws InterruptedException {
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
        } finally {
            bankLock.unlock();
        }
    }

    /**
     * 获取所有账户余额的总和。
     * @return 总余额
     */
    public double getTotalBalance() {
        bankLock.lock();
        try {
            double sum = 0;
            for (double a : accounts)
                sum += a;
            return sum;
        } finally {
            bankLock.unlock();
        }
    }

    /**
     * 获取银行中账户的数量。
     * @return 账户的数量
     */
    public int size() {
        return accounts.length;
    }
}
```

`java.util.concurrent.locks.Lock`

- `newCondition()` 返回与此锁关联的条件。

`java.util.concurrent.locks.Condition`

- `await()` 将此线程置于该条件的等待集上。
- `signalAll()` 解阻塞该条件等待集中的所有线程。
- `signal()` 解阻塞该条件等待集中的随机选择的一个线程。

#### 12.4.5 `synchronized` 关键字

在前面的节节中你你已经学习了如何使用 `Lock` 和 `Condition` 对象。在继续深入之前，让我们总结一下关于锁和条件的要点：

- 锁保护代码段，允许一次只有一个线程执行该代码。
- 锁管理尝试进入受保护段落的线程。
- 一个锁可以带有一个或多个关联的条件对象。
- 每个条件对象管理已进入受保护代码段但无法继续执行的线程。

`Lock` 和 `Condition` 接口为程序员提供了对锁的高度细粒控制。然而，在大多数情况下，你不需要那种控制——你可以使用 Java 语言内置的机制。从 1.0 版本开始，Java 中的每个对象都有一个内置锁（intrinsic lock）。如果一个方法声明了 `synchronized` 关键字，那么该对象的锁就会保护整个方法。也就是说，要调用该方法，线程必须获取该内建锁。

换句话说：

```java
public synchronized void method() {
    method body
}
```

等同于：



```java
public void method() {
    this.intrinsicLock.lock();

    try {
        method body
    } finally {
        this.intrinsicLock.unlock();
    }
}
```

例如，与其使用显式锁，我们可以简单地将 `Bank` 类的 `transfer` 方法声明为 `synchronized`。

内建锁有一个关联的条件。`wait` 方法将线程添加到等待集中，而 `notifyAll`/`notify` 方法会解阻塞等待的线程。换句话说，调用 `wait` 或 `notifyAll` 等同于：

```java
intrinsicCondition.await();
intrinsicCondition.signalAll();
```

![Image](img/note.jpg) **注意：**

`wait`、`notifyAll` 和 `notify` 方法是 `Object` 类的 `final` 方法。`Condition` 方法必须命名为 `await`、`signalAll` 和 `signal`，以免与这些方法冲突。

例如，你可以像这样在 Java 中实现 `Bank` 类：

```java
class Bank {
    private double[] accounts;

    public synchronized void transfer(int from, int to, int amount)
        throws InterruptedException {
        while (accounts[from] < amount)
            wait(); // 在内置对象锁的单一条件上等待

        accounts[from] -= amount;
        accounts[to] += amount;

        notifyAll(); // 通知所有在该条件上的等待
    }

    public synchronized double getTotalBalance() {
        double sum = 0;

        for (double a : accounts)
            sum += a;

        return sum;
    }
}
```

你可以看到，使用 `synchronized` 产生的代码更加简洁。当然，为了理解这段代码，你必须知道每个对象都有一个内建锁，并且锁有一个内建条件。锁管理尝试进入 `synchronized` 方法的线程。

```java
package synch2;

import java.util.*;

/**
 * 一个拥有多个银行账户并使用同步原的银行。
 */
public class Bank {
    private final double[] accounts;

    /**
     * 构造银行。
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
     * @param from 要转出的账户
     * @param to 要转入的账户
     * @param amount 要转账的金额
     */
    public synchronized void transfer(int from, int to, double amount)
        throws InterruptedException {
        while (accounts[from] < amount)
            wait();

        System.out.print(Thread.currentThread());
        accounts[from] -= amount;
        System.out.printf(" %10.2f from %d to %d", amount, from, to);
        accounts[to] += amount;
        System.out.printf(" Total Balance: %10.2f%n", getTotalBalance());

        notifyAll();
    }

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
}
```

`java.lang.Object` 1.0

- `void notifyAll()`

  唤醒在该对象上调用 `wait` 的所有线程。此方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，则该方法将抛出 `IllegalMonitorStateException`。

- `void notify()`

  在在该对象上调用 `wait` 的线程中随机选择一个唤醒。此方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，则该方法将抛出 `IllegalMonitorStateException`。

- `void wait()`

  导致线程等待，直到它被唤醒。此方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，则该方法将抛出 `IllegalMonitorStateException`。

- `void wait(long millis)`
- `void wait(long millis, int nanos)`

  导致线程等待直到它被唤醒或过了指定的时间。这些方法只能在同步方法或同步块内部调用。如果当前线程不是对象锁的所有者，则它们将抛出 `IllegalMonitorStateException`。纳秒数不应超过 1,000,000。

#### 12.4.6 同步块（Synchronized Blocks）

正如我们讨论过的，每个 Java 对象都有一把锁。线程可以通过调用同步方法来获取锁。获取锁的第二种机制是：进入形式如下的同步块：

```java
synchronized (obj) {
    // 临界区
}
```

然后它获取了 `obj` 的锁。你有时会发现“临时（ad hoc）”锁，例如：

```java
public class Bank {
    private double[] accounts;
    private Object lock = new Object();

    public void transfer(int from, int to, double amount) {
        synchronized (lock) { // 临时锁
            accounts[from] -= amount;
            accounts[to] += amount;
        }

        System.out.println();
    }
}
```

在这里，`lock` 对象的创建仅仅是为了使用每个 Java 对象都拥有的锁。

**注意：** 使用同步块时，要小心锁对象。例如，下面的代码不起作用：

```java
private final String lock = "LOCK";

synchronized (lock) { ... }
```

如果这在同一个程序中发生两次，锁将是同一个对象，因为字符串字面量是共享的。这可能导致死锁。

此外，避免使用基本类型的包装类作为锁：

```java
private final Integer lock = new Integer(42); // 不要对包装类上加锁
```

构造函数调用 `new Integer(0)` 已被弃用，你不希望维护程序员将调用更改为 `Integer.valueOf(42)`。如果使用同一个魔术数字执行两次，锁将被意外共享。

如果你需要修改静态字段，请在特定的类上锁，而不是在 `getClass()` 返回的值上锁：

```java
synchronized (MyClass.class) { staticCounter++; } // OK

synchronized (getClass()) { staticCounter++; } // 不要这样做
```

如果包含此代码的方法是从子类调用的，那么 `getClass()` 将返回不同的 `Class` 对象！你将不再保证互斥性！

通常情况下，如果你必须使用 `synchronized` 块，请明确你的锁对象！你必须对所有受保护的路径使用相同的锁，并且不能有其他人使用你的锁。

有时，程序员使用对象的锁来实现额外的原子操作——这种做法被称为客户端锁定（client-side locking）。例如，考虑 `Vector` 类，它是一个方法都是同步的列表。现在假设我们把银行余额存储在 `Vector<Double>` 中。这是一个 `transfer` 方法的朴素实现：

```java
public void transfer(
    Vector<Double> accounts,
    int from,
    int to,
    int amount
) // 错误
{
    accounts.set(from, accounts.get(from) - amount);
    accounts.set(to, accounts.get(to) + amount);
    System.out.println();
}
```

`Vector` 类的 `get` 和 `set` 方法都是同步的，但这对我们没有帮助。在 `transfer` 方法中完成第一次 `get` 调用后，线程可能会被抢占。另一个线程可能会在同一位置存储不同的值。然而，我们可以劫持锁：

```java
public void transfer(
    Vector<Double> accounts,
    int from,
    int to,
    int amount
) {
    synchronized (accounts) {
        accounts.set(from, accounts.get(from) - amount);
        accounts.set(to, accounts.get(to) + amount);
    }

    System.out.println();
}
```

这种方法有效，但它完全取决于 `Vector` 类对其所有修改方法都使用内部锁。然而，这真的是事实吗？`Vector` 类的文档并没有这样的承诺。你必须仔细研究源码，并希望未来的版本不要引入同步的修改方法。可见，客户端锁定是非常脆弱的，通常不推荐。

**注意：** Java 虚拟机对同步方法有内置支持。然而，同步块被编译为一组长字节码序列来管理内部锁。

#### 12.4.7 监器概念（Monitor Concept）

锁和条件是线程同步的强大工具，但它们并不十分面向对象。多年来，研究人员一直在寻找让多线程安全的方法，而不强制程序员思考显式的锁。最成功的解决方案之一是由 Per Brinch Hansen 和 Tony Hoare 在 20 世纪 70 年代提出的*监器*概念。在 Java 的术语中，监器具有以下属性：

- 监器是一个只有一个私有字段的类。
- 该类的每个对象都关联一把锁。
- 所有方法都由该锁锁定。换句话说，如果客户端调用 `obj.method()`，`obj` 的锁会在方法调用开始时自动获取，并在方法返回时释放。由于所有字段都是私有的，这种安排确保了当一个线程在操作字段时，另一个线程无法访问这些字段。
- 锁可以具有任意数量的关联条件。

早版本的监视器（monitors）只有一个条件，语法非常优雅。你可以直接调用 `await accounts[from] >= amount`，而无需使用显式的条件变量。然而，研究表明，对条件进行无区别的重新测试可能是低效的。这个问题通过显式条件变量得到了解决，每个条件变量管理一组独立的线程。

Java 的设计者松散地借鉴了监视器的概念。Java 中的**每个对象**都有一个内置锁和一个内置条件。如果一个方法被用 `synchronized` 关键字声明，它的行为就像一个监视器方法。通过调用 `wait`/`notifyAll`/`notify` 来访问条件变量。

然而，Java 对象与监视器在三个重要方面有所不同，这损害了线程安全：

- 字段不要求为 `private`。
- 方法不要求为 `synchronized`。
- 内置锁对客户端可见。

这种对安全的无视让 Per Brinch Hansen（布林·汉森）非常愤怒。在对 Java 多线程原的严厉批评中，他写道：“令我惊讶的是，在监视器和并发帕斯卡（Concurrent Pascal）发明四分之一后，Java 不安全的并行性竟然被编程社区严肃对待。它毫无价值” [Java’s Insecure Parallelism, *ACM SIGPLAN Notices* 34:38–45, April 1999]。

#### 12.4.8 Volatile 字段

有时，仅仅为了读取或写入一两个实例字段就付出同步的代价似乎是过分的。毕竟，在现代处理器和编译器上，存在很大的容错空间。

- 拥有多个处理器的计算机可以将内存值临时存储在寄存器或本地内存缓存中。因此，运行在不同处理器上的线程可能会看到同一个内存位置的不同的值！
- 编译器为了最大化吞吐量可能会重排指令顺序。编译器不会选择改变代码含义的排序，但它们假设只有当代码中存在显式指令时，内存值才会被改变。然而，内存值可以被另一个线程更改！

如果你使用锁来保护可以被多个线程访问的代码，就不会有这些问题。编译器被要求在需要时刷新本地缓存并且不恰当地重排指令来尊重锁。细节在 JSR 133 开发的 Java 内存模型和线程规范中进行了解释（参见 [`www.jcp.org/en/jsr/detail?id=133`](http://www.jcp.org/en/jsr/detail?id=133)）。该规范大部分非常复杂且具有技术性，但文档也包含许多解释清晰的示例。Brian Goetz 编写的一篇更易理解的概述文章可以在 `www.ibm.com/developerworks/library/j-jtp02244` 找到。

![Image](img/note.jpg) **注意：**

Brian Goetz 创造了以下“同步格言”：“如果你写了一个可能被另一个线程读取的变量，或者你读取了一个可能最近被另一个线程写入的变量，你必须使用同步。”

`volatile` 关键字为同步实例字段的访问提供了一种无锁机制。如果你将一个字段声明为 `volatile`，那么编译器和虚拟机就会考虑到该字段可能会被另一个线程并发更新。

例如，假设一个对象有一个 `boolean` 标记 `done`，由一个线程设置并在另一个线程查询。正如我们已经讨论过的，你可以使用锁：

```java
private boolean done;

public synchronized boolean isDone() {
    return done;
}

public synchronized void setDone() {
    done = true;
}
```

也许使用对象的内置锁并不是一个好主意。如果另一个线程锁定了对象，`isDone` 和 `setDone` 方法可能会被阻塞。如果担心这个问题，可以使用专门为这个变量设置的单独锁。但这会变得非常麻烦。

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

编译器将插入适当的代码，以确保一个线程中对 `done` 变量的更改对读取该变量的任何线程都是可见的。

![Image](img/caution.jpg) **警告：**

Volatile 变量不提供任何原子性。例如，方法：

```java
public void flipDone() {
    done = !done;
} // 不是原子的
```

并不能保证能翻转字段的值。无法保证读取、翻转和写入的过程是不中断的。

#### 12.4.9 Final 变量

正如你在上一节看到的，除非使用锁或 `volatile` 修饰符，否则你无法从多个线程安全地读取字段。

还有一种访问共享字段安全的情况——当它被声明为 `final` 时。考虑：

```java
final var accounts = new HashMap<String, Double>();
```



其他线程在构造函数完成后可以看到`accounts`变量。

如果不使用`final`，无法保证其他线程能看到`accounts`的更新值——它们可能都看到`null`，而不是构造好的`HashMap`。

当然，对 map 的操作不是线程安全的。如果多个线程变动并读取 map，你仍然需要同步。

#### 12.4.10 原子类 (Atomics)

只要你不执行赋值以外的操作，就可以将共享变量声明为`volatile`。

在`java.util.concurrent.atomic`包中许多类，它们使用高效的机器级指令在不使用锁的情况下保证其他操作的原子性。例如，`AtomicInteger`类具有`incrementAndGet`和`decrementAndGet`方法，可以原子性地增加或减少一个整数。例如，你可以安全地生成如下数字序列：

```
public static AtomicLong nextNumber = new AtomicLong();

// 在某些线程中 . .

long id = nextNumber.incrementAndGet();
```

`incrementAndGet`方法原子性地增加`AtomicLong`并返回自增后的值。也就是说，获取值、加 1、设置值和产生新值的操作是被中断的。即使多个线程并发访问同一个实例，也能保证计算并返回正确的值。

虽然有方法可以原子性地设置、相加和减去值，但如果你想进行更复杂的更新，就必须使用`compareAndSet`方法。例如，假设你想跟踪不同线程观察到的最大值。以下代码不起作用：

```
public static AtomicLong largest = new AtomicLong();

// 在某些线程中 . .

largest.set(Math.max(largest.get(), observed)); // --竞态条件！
```

这种更新不是原子的。相反，提供一个更新变量的 lambda 表达式，更新将由你完成。在我们的示例中，我们可以调用

```
largest.updateAndGet(x -> Math.max(x, observed));
```

或者

```
largest.accumulateAndGet(observed, Math::max);
```

`accumulateAndGet`方法接收一个二进制运算符，用于合并原子值和提供的参数。还有`getAndUpdate`和`getAndAccumulate`方法返回旧值。

---

这些方法也提供给`AtomicInteger`、`AtomicIntegerArray`、`AtomicIntegerFieldUpdater`、`AtomicLongArray`、`AtomicLongFieldUpdater`、`AtomicReference`、`AtomicReferenceArray`以及`AtomicReferenceFieldUpdater`类。

当有大量线程访问同一个原子值时，性能会受到影响，因为乐观更新需要过多的重试。`LongAdder`和`LongAccumulator`类解决了这个问题。`LongAdder`由多个变量组成，这些变量的累加和就是当前值。多个线程可以更新不同的加数项，并且当线程数量增加时，会自动提供新的加数项。在通常情况下，即在所有工作完成之前不需要总和值时，这种方法是非常高效的。性能的提升可能是巨大的。

如果你预见到会有高并发竞争，应该直接使用`LongAdder`而不是`AtomicLong`。方法名称略有不同。调用`increment`增加计数器，调用`add`增加指定数值，并调用`sum`获取总和。

```
var adder = new LongAdder();

for (. . .)
    pool.submit(() ->
        {
            while (. . .)
            {
                . . .
                if (. . .) adder.increment();
            }
        });

. . .

long total = adder.sum();
```

---

![Image](img/note.jpg) **注意：**

当然，`increment`方法*并没有*返回旧值。这样做会抵消将总和拆分为多个加数项所带来的效率收益。

---

`LongAccumulator`将此思想推广到任意的累加操作。在构造函数中，你提供该操作以及它的中性元素（neutral element）。要合并新值，请调用`accumulate`。调用`get`获取当前值。以下代码在逻辑上实现的效果与`LongAdder`相同：

```
var adder = new LongAccumulator(Long::sum, 0);

// 在某些线程中. . .

adder.accumulate(value);
```

内部，累加器拥有变量`a[1]`、`a[2]`、. . . `a[n]`。每个变量都用中性元素初始化（在我们的示例中为`0`）。

当使用值`v`调用`accumulate`时，其中一个变量会被原子地更新为`a[i] = a[i] * op v`，其中`op`是中缀形式的累加操作。在我们的示例中，调用`accumulate`会为某个`i`计算`a[i] = a[i] + v`。

`get`的结果是`a[1] op a[2] op . . op a[n]`。在我们的示例中，它是所有累加器的和，`a[1] + a[2] + . . . + a[n]`。

如果你选择不同的操作，可以计算最大值或最小值。通常，该操作必须满足结合律和交换律。这意味着最终结果必须与中间值组合的顺序无关。

还有`DoubleAdder`和`DoubleAccumulator`，它们的工作方式相同，只是处理的是`double`类型的值。

#### 12.4.11 死锁

锁和条件变量无法解决多线程环境中可能出现的所有问题。考虑以下情况：

1. 账户 1：$200
2. 账户 2：$300
3. 线程 1：从账户 1 转账 $300 到账户 2
4. 线程 2：从账户 2 转账 $400 到账户 1

如图 12.4 所示，线程 1 和 2 显然被阻塞了。它们都无法继续执行，因为账户 1 和账户 2 的余额不足。

![Images](img/12fig04.jpg)

**图 12.4** 死锁状况

可能所有线程都被阻塞，因为每个线程都在等待更多的钱。这种情况被称为*死锁*。

在我们的程序中，由于一个简单的原因不会发生死锁。每个转账金额最多为 $1,000。由于有 100 个账户且总金额为 $100,000，因此在任何时候至少有一个账户里至少有 $1,000。因此，从该账户中取出资金的线程可以继续执行。

但如果你修改线程的`run`方法以移除 $1,000 的转账限制，死锁会迅速发生。尝试一下：将`NACCOUNTS`设置为`10`。构造一个`max`值为`2 * INITIAL_BALANCE`的每个转账`Runnable`，并运行程序。程序将运行一段时间后就会挂起。

---

![Image](img/tip.jpg) **提示：**

当程序挂起时，按 Ctrl+\。你将得到一个列出所有线程的线程储（thread dump）。每个线程都有堆栈跟踪，告诉你它当前阻塞在哪里。或者，如第 7 章所示运行`jconsole`并查看 Threads 面板（参见图 12.5）。

---

![Images](img/12fig05.jpg)

**图 12.5** jconsole 中的 Threads 面板

创建死锁的另一种方法是让第`i`个线程负责将钱放入第`i`个账户，而不是从第`i`个账户取出钱。在这种情况下，所有线程都有可能围攻一个账户，每个线程都试图从中取出超过其余额的钱。尝试一下：在`SynchBankTest`程序中，找到`TransferRunnable`类的`run`方法。在调用`transfer`时，反转`fromAccount`和`toAccount`。运行程序。

当一个线程想要停止另一个线程时，它无法知道`stop`方法何时调用是安全的，以及何时调用会导致对象损坏。因此，该方法已被弃用。当你想要停止一个线程时，应该中断（interrupt）它。被中断的线程随后可以在安全的时候再停止。

---

![Image](img/note.jpg) **注意：**

某些作者声称，`stop`方法被弃用是因为它可以导致对象被停止的线程永久锁定。然而，这种说法是不成立的。停止的线程会退出它调过的所有同步方法——从技术上讲，是通过抛出一个`ThreadDeath`异常来实现。结果是，线程会释放它持有的内置对象锁。

---

接下来，让我们看看`suspend`方法有什么问题。与`stop`不同，`suspend`不损坏对象。但是，如果你挂起了一个拥有锁的线程，那么在线程被恢复之前，该锁将是不可用的。如果调用`suspend`方法的线程尝试获取同一个锁，程序就会发生死锁：挂起的线程在等待被恢复，而挂起线程的线程在等待锁。

这种情况在图形用户界面中经常发生。假设我们有一个银行的图形模拟。一个标记为“暂停”（Pause）的按钮挂起传输线程，一个标记为“恢复”（Resume）的按钮恢复它们。

```
pauseButton.addActionListener(event ->
   {
      for (int i = 0; i < threads.length; i++)
          threads[i].suspend(); // 不要这么做
   });

resumeButton.addActionListener(event ->
   {
      for (int i = 0; i < threads.length; i++)
          threads[i].resume();
   });
```

假设一个`paintComponent`方法绘制每个账户的图表，并调用`getBalances`方法来获取余额数组。

正如你将在第 12.7.3 节中，第 839 页的“用户界面回调中的长时间运行任务”中看到的，按钮操作和重绘都发生在同一个线程中，即*事件派发线程*（event dispatch thread）。考虑以下场景：

1. 传输线程之一获取了`bank`对象的锁。
2. 用户点击了暂停按钮。
3. 所有传输线程都被挂起；其中一个线程仍然持有`bank`对象的锁。
4. 出于某种原因，账户图表需要重绘。
5. `paintComponent`方法调用了`getBalances`方法。
6. 该方法尝试获取`bank`对象的锁。

现在程序冻结了。

事件派发线程无法继续，因为锁被其中一个挂起的线程持有了。因此，用户无法点击恢复按钮，线程将永远不会恢复。

如果你想安全地挂起一个线程，可以引入一个变量`suspendRequested`并在你的`run`方法的安全位置对其进行测试——即在你的线程不会锁定其他线程所需的对象的地方。当你的线程发现`suspendRequested`变量被设置过时，它应该继续等待，直到它再次可用。

#### 12.4.13 需需初始化

有时，你有一个数据结构，你只想在第一次需要它时对其进行初始化。并且你想确保初始化恰好发生一次。与其设计自己的机制，不如利用这样一个事实：虚拟机在类第一次被使用时会恰好执行一次静态初始化器。虚拟机通过锁来确保这一点，所以你不需要编写自己的锁。

```java
public class OnDemandData
{
   // 私有构造函数以确保只构造一个对象
   private OnDemandData()
   {
      . . .
   }

   public static OnDemandData getInstance()
   {
```



```java
return Holder.INSTANCE;

}

// 仅在第一次使用时初始化，即在第一次调用`getInstance`时

private static Holder

{

   // VM 保证这最多发生一次

   static final OnDemandData INSTANCE = new OnDemandData();

}

}
```

***

![Image](img/caution.jpg) **警告：**

要使用这种惯用法，你必须确保构造函数不会抛出任何异常。虚拟机不会第二次尝试初始化持有者类。

***

#### 12.4.14 线程本地变量

在前面的章节中，我们讨论了线程之间共享变量的风险。有时，你可以通过为每个线程提供自己的实例来避免共享，使用`ThreadLocal`辅助类。例如，`SimpleDateFormat`类不是线程安全的。假设我们有一个静态变量：

```java
public static final SimpleDateFormat dateFormat = new SimpleDateFormat("yyyy-MM-dd");
```

第一次调用`get`时，值是通过调用`initialize`获取的。如果两个线程执行诸如`dateFormat`的操作，它可能会由于并发访问而损坏。你可以使用同步，但这也是昂贵的。要为每个线程构造一个实例，请使用以下代码：

```java
public static final ThreadLocal<SimpleDateFormat> dateFormat = ...
```

从那时起，`get`返回属于当前线程的实例。

类似的问题是多线程中随机数的生成。`java.util.Random`类是线程安全的。但如果多个线程需要一个共享的生成器，它仍然是低的。Java 7 为你提供了一个便利类。只需调用如下：

```java
int random = ThreadLocalRandom.current().nextInt(upperBound);
```

调用`ThreadLocalRandom.current()`返回一个当前线程唯一的随机数实例。

线程本地变量有时也用于让协作任务的所有方法都能使用对象，而无需在调用者之间传递对象。例如，假设你想共享数据库连接。声明一个变量：

```java
public static final ThreadLocal<Connection> connection = ThreadLocal.withInitial(() -> null);
```

当任务开始时，为该线程初始化连接：

```java
connection.set(connect(url, username, password));
```

任务在同一线程内调用某些方法，最终其中一个方法需要连接：

```java
var result = connection.get().executeQuery(query);
```

注意，相同的调用发生在多个线程中。它们各自获取连接对象。

***

![Image](img/caution.jpg) **警告：**

在前面的示例中，只有一个任务使用该线程至关重要。当线程池执行任务时，你不希望将数据库连接暴露给共享同一线程的其他任务。

***

**`java.lang.ThreadLocal<T>`** **1.2**

***

- `T get()` 获取此线程的值。如果是第一次调用`get`，则通过调用`initialize`获取。
- `void set(T t)`为此线程设置新值。
- `void remove()` 此线程的值。
- `static <S> ThreadLocal<S> withInitial(Supplier<? extends S> supplier)` **8**

创建一个线程本地变量，其初始值通过调用给定的提供者产生。

**`java.util.concurrent.ThreadLocalRandom`** **7**

***

- `static ThreadLocalRandom current()` 返回一个当前线程唯一的`Random`类实例。

### 12.5 线程安全集合

如果多个线程并发修改数据结构（例如哈希表），很容易损坏该数据结构。（有关哈希表的更多信息，请参阅第 9 章）。例如，很容易损坏该数据结构。

如果多个线程并发修改数据结构（例如哈希表），很容易损坏该数据结构。（有关哈希表的更多信息，请参阅第 9 章）。例如，很容易损坏该数据结构。`put`和`take`方法。

### 12.5.1 阻塞队列

`java.util.concurrent`包提供了几种变体阻塞队列。默认情况下，`LinkedBlockingQueue`具有无界容量，但也可以指定最大容量。`LinkedBlockingDeque`是双端队列版本。`ArrayBlockingQueue`使用指定的容量构建，并带有一个可选的参数来要求公平性。如果指定了公平性，则等待时间最长的线程将获得优先处理。一如既往，公平性会带来巨大的性能代价，只有当你的问题特别需要时才应该使用它。

`PriorityBlockingQueue`是优先级队列，而不是先进先出队列。元素按照它们的优先级顺序被移除。它具有无界容量，但如果队列为空，检索将阻塞。（有关优先级队列的更多信息，请参阅第 9 章）。

`DelayQueue`包含实现了`Delayed`接口的元素：

```java
interface Delayed extends Comparable<Delayed> {

    long getDelay(TimeUnit unit);

}
```

`getDelay`方法返回对象的剩余延迟。负值表示延迟已过去。只有当元素的延迟过期后，才能从`DelayQueue`中移除。你还需要实现`compareTo`方法。`DelayQueue`使用该方法对条目进行排序。

Java 7 添加了一个`TransferQueue`接口，允许生产者线程等待直到消费者准备好获取一个项目。当生产者调用：

```java
q.transfer(item);
```

该调用将一直阻塞，直到另一个线程将其移除。`LinkedTransferQueue`类实现了该接口。

清单 12.6 中的程序显示了如何使用阻塞队列来控制一组线程。该程序搜索目录及其子目录中的所有文件，并打印包含关键字的行。

生产者线程枚举所有子目录中的所有文件，并将它们放入阻塞队列中。此操作非常快，如果队列不是无界的，它会被文件系统中的所有文件填满。

我们还启动了大量的搜索线程。每个搜索线程从队列获取一个文件，打开它，打印所有包含关键字的行，然后获取下一个文件。我们使用了一种技巧在不再需要进一步工作时终止应用程序。为了信号完成，枚举线程向队列中放入一个虚拟对象。当搜索线程获取到虚拟对象时，它将其放回去并终止。

注意，这不需要显式的线程同步。在这个应用程序中，我们使用队列数据结构作为同步机制。

## 12.5.2 高效的 Map、Set 和 Queue

`java.util.concurrent`包提供了映射、排序集合和队列的高效实现：`ConcurrentHashMap`、`ConcurrentSkipListMap`、`ConcurrentSkipListSet`以及`ConcurrentLinkedQueue`。

这些集合使用了复杂的算法，通过允许对数据结构的不同部分进行并发访问，最大限度地减少了竞争。

与大多数集合不同，这些类的`size`方法并不一定在常数时间内运行。确定这些集合之一的当前大小通常需要进行遍历。

***

![Image](img/note.jpg) **注意：**

某些应用程序使用了巨大的并发哈希映射，其规模大至于`size`方法由于返回的是`int`类型而不够用。对于一个包含超过 20 亿条目的映射，该怎么办？`mappingCount`方法以`long`类型返回大小。

集合返回`弱一致性`的迭代器。这意味着迭代器可能反映也可能不反映在构造之后所进行的所有修改，但它们不会返回两次值，且不会抛出`ConcurrentModificationException`。

![Image](img/note.jpg) **注意：**

相比之下，`java.util`包中集合的迭代器在迭代器构造后集合被修改时，会抛出`ConcurrentModificationException`。

并发哈希映射可以高效地支持大量的读取者和有限数量的写入者。

![Image](img/note.jpg) **注意：**

哈希映射将具有相同哈希码的所有条目放在同一个“桶”中。某些应用程序使用了糟糕的哈希函数，导致所有条目最终落入少数桶中，严重降低性能。即使是通常合理的哈希函数（例如`String`类）也可能出现问题。例如，攻击者可以通过构造大量哈希到相同值的字符串来减慢程序。在最近的 Java 版本中，当键类型实现了`Comparable`时，并发哈希映射将桶组织为树而不是列表，从而保证了`O`(log `n`)的性能。

### `java.util.concurrent.ConcurrentLinkedQueue<E>` **5**

- `ConcurrentLinkedQueue<E>()`

构造一个无界的、非阻塞的队列，可以被多个线程安全地访问。

### `java.util.concurrent.ConcurrentSkipListSet<E>` **6**

- `ConcurrentSkipListSet<E>()`
- `ConcurrentSkipListSet<E>(Comparator<? super E> comp)`

构造一个可以被多个线程安全地访问的排序集合。第一个构造函数要求元素实现`Comparable`接口。

### `java.util.concurrent.ConcurrentHashMap<K, V>` **5**

### `java.util.concurrent.ConcurrentSkipListMap<K, V>` **6**

- `ConcurrentHashMap<K, V>()`
- `ConcurrentHashMap<K, V>(int initialCapacity)`
- `ConcurrentHashMap<K, V>(int initialCapacity, float loadFactor, int concurrencyLevel)`

构造一个可以被多个线程安全地访问的哈希映射。初始容量的默认值为`16`。如果每个桶的平均负载超过负载因子，则对表进行大小。默认值为`0.75`。并发级别是估计的并发写入线程数。

- `ConcurrentSkipListMap<K, V>()`
- `ConcurrentSkipListSet<K, V>(Comparator<? super K> comp)`

构造一个可以被多个线程安全地访问的排序映射。第一个构造函数要求键实现`Comparable`接口。

#### 12.5.3 Map 条目的原子化更新

`ConcurrentHashMap`的原始版本只有几个方法用于原子更新，这使得编程变得有些有些笨拙。假设我们想要统计某些特征出现的频率。作为一个简单的例子，假设多个线程遇到单词，我们想要统计它们的频率。

我们可以使用`ConcurrentHashMap<String, Long>`吗？考虑增加计数器的代码。显然，以下代码不是线程安全的：

```java
Long oldValue = map.get(word);

Long newValue = oldValue == null ? 1 : oldValue + 1;

map.put(word, newValue); // --可能没有替换 oldValue
```

另一个线程可能同时在更新同一个计数。

![Image](img/note.jpg) **注意：**

一些程序员对一个据说是线程安全的数据结构允许非线程安全的操作感到惊讶。但这里有两种完全不同的考量。如果多个线程修改一个普通的`HashMap`，它们可能会破坏内部结构（链表数组）。某些链接可能会丢失，甚至形成循环，导致数据结构不可用。这在`ConcurrentHashMap`中永远不会发生。在上面的示例中，`get`和`put`的代码永远不会损坏数据结构。但是，由于操作序列不是原子的，结果是不可预测的。

在 Java 的旧版本中，有必要使用`replace`方法，该方法原子性地将旧值替换为新值，前提是没有其他线程在此之前将旧值替换为其他内容。你必须不断这样做，直到尝试成功为止：

```java
do
{
   oldValue = map.get(word);
   newValue = oldValue == null ? 1 : oldValue + 1;
}
while (!map.replace(word, oldValue, newValue));
```

另一种方法是使用`ConcurrentHashMap<String, AtomicLong>`以及以下更新代码：

```java
map.putIfAbsent(word, new AtomicLong());

map.get(word).incrementAndGet();
```

遗憾的是，每增加一次都会构造一个新的`AtomicLong`，无论是否需要。

如今，Java API 提供了使原子更新更方便的方法。`compute`方法在调用时传入一个键和一个用于计算新值的函数。该函数接收键和关联的值（如果没有则则为`null`），并计算出新值。例如，这里是我们如何更新一个整数计数器映射：

```java
map.compute(word, (k, v) -> v == null ? 1 : v + 1);
```

![Image](img/note.jpg) **注意：**

你不能在`ConcurrentHashMap`中拥有`null`值。有许多方法使用`null`值作为指示，表示给定的键不在映射中。

还有`computeIfPresent`和`computeIfAbsent`变体，它们只在已经存在旧值或还没有旧值时才计算新值。一个包含`LongAdder`计数器的映射可以这样更新：

```java
map.computeIfAbsent(word, k -> new LongAdder()).increment();
```

这与之前看到的`putIfAbsent`调用非常相似，但只有在真正需要时才会调用`LongAdder`构造函数。

你经常需要在键首次添加时执行某些特殊操作。`merge`方法使得这变得特别方便。它有一个参数用于键不存在时使用的初始值。否则，将调用你提供的函数，将现有值和初始值合并。（与`compute`不同，该函数*不*处理键。）

```java
map.merge(word, 1L, (existingValue, newValue) -> existingValue + newValue);
```

或者简单地：

```java
map.merge(word, 1L, Long::sum);
```

没有比这更简洁的。

![Image](img/note.jpg) **注意：**

如果传递给`compute`或`merge`的函数返回`null`，则映射中移除现有条目。

![Image](img/caution.jpg) **注意：**

在使用`compute`或`merge`时，记住你提供的函数不应执行大量工作。当该函数运行时，映射的某些其他更新可能会阻塞。当然，该函数也不应更新映射的其他部分。

列表 12.7 中的程序使用并发哈希映射来统计目录树中 Java 文件中的所有单词。

**列表 12.7** `concurrentHashMap/CHMDemo.java`

```java
package concurrentHashMap;

import java.io.*;

import java.nio.file.*;

import java.util.*;

import java.util.concurrent.*;

import java.util.stream.*;

/**
 * 此程序演示了并发哈希映射。
 * @version 1.0 2018-01-04
 * @author Cay Horstmann
 */

public class CHMDemo
{
    public static ConcurrentHashMap<String, Long> map = new ConcurrentHashMap<>();

    /**
     * 将文件中所有的单词添加到并发哈希映射。
     * @param file 一个文件
     */

    public static void process(Path file)
    {
        try (var in = new Scanner(file))
        {
            while (in.hasNext())
            {
                String word = in.next();

                map.merge(word, 1L, Long::sum);
            }
        }
        catch (IOException e)
        {
            e.printStackTrace();
        }
    }

    /**
     * 返回给定目录的所有后代——参见第二卷的第 1 章和第 2 章
     * @param rootDir 根目录
     * @return 根目录所有后代的集合
     */

    public static Set<Path> descendants(Path rootDir) throws IOException
    {



```java
try (Stream<Path> entries = Files.walk(rootDir)) {
    return entries.collect(Collectors.toSet());
}
```

```java
public static void main(String[] args) throws InterruptedException, ExecutionException, IOException {
    int processors = Runtime.getRuntime().availableProcessors();
    ExecutorService executor = Executors.newFixedThreadPool(processors);
    Path pathToRoot = Path.of(".");
    for (Path p : descendants(pathToRoot)) {
        if (p.getFileName().toString().endsWith(".java"))
            executor.execute(() -> process(p));
    }
    executor.shutdown();
    executor.awaitTermination(10, TimeUnit.MINUTES);
    map.forEach((k, v) -> {
        if (v >= 10)
            System.out.println(k + " occurs " + v + " times");
    });
}
```

#### 12.5.4 并发映射的批量操作

Java API 提供了针对并发哈希映射的批量操作，这些操作可以在其他线程对映射进行操作时安全地执行。批量操作会遍历映射，并在遍历过程中对找到的元素进行操作。程序并没有尝试冻结映射在某一时间点的快照。除非你恰好知道映射没有被修改，否则你应当将其操作结果视为映射状态的近似值。

操作共有三类：

- `search` 对每个键/或值应用一个函数，直到该函数产生一个非空结果为止。然后，`search` 停止并返回函数的结果。
- `reduce` 使用提供的累加函数合并所有的键/或值。
- `forEach` 对所有键/或值应用一个函数。

每个操作都有四个版本：

- `Keys`：对键进行操作。
- `Values`：对值进行操作。
- （未提供名称）：对键和值进行操作。
- `Entries`：对 `Map.Entry` 对象进行操作。

对于每种操作，你都需要指定并行阈值。如果映射中包含的元素多于阈值，则批量操作将是并行的。如果你希望批量操作在单线程中运行，请使用 `Long.MAX_VALUE`。如果你希望为批量操作提供最大数量的线程，请使用阈值 `1`。

让我们先看看 `search` 方法。以下是各个版本：

```java
U searchKeys(long threshold, BiFunction<? super K, extends U> f)
U searchValues(long threshold, BiFunction<? super V, extends U> f)
U search(long threshold, BiFunction<? super K, super V, extends U> f)
U searchEntries(long threshold, BiFunction<Map.Entry<K, V>, extends U> f)
```

例如，假设我们想要找到出现次数超过 1000 次的单词。我们需要搜索键和值：

```java
String result = map.search(threshold, (k, v) -> v > 1000 ? k : null);
```

然后 `result` 被设置为第一个匹配项，如果搜索函数对所有输入都返回 `null`，则将其设置为 `null`。`forEach` 方法有两个变体。第一种简单地为每个映射条目应用一个消费者函数，例如：

```java
map.forEach(threshold, (k, v) -> System.out.println(k + " -> " + v));
```

第二种变体接受一个额外的转换函数，该函数会被先应用，其结果将传递给消费者：

```java
map.forEach(threshold, (k, v) -> k + " -> " + v, System.out::println);
```

转换器可以用作过滤器。每当转换器返回 `null` 时，该值会被跳过。例如，在这里我们只打印值较大的条目：

```java
map.forEach(threshold, (k, v) -> v > 1000 ? k + " -> " + v : null, System.out::println);
```

`reduce` 操作使用累加函数合并其输入。例如，这里是计算所有值的和：

```java
Long sum = map.reduceValues(threshold, Long::sum);
```

与 `forEach` 一样，你也可以提供一个转换函数。在这里我们计算所有键的最大长度：

```java
Integer maxlength = map.reduceKeys(threshold, String::length, Integer::max);
```

转换器可以通过返回 `null` 来充当过滤器。在这里我们统计值大于 1000 的条目数量：

```java
Long count = map.reduceValues(threshold, (k, v) -> v > 1000 ? 1L : null, Long::sum);
```

**注意**：如果映射为空或所有条目都被过滤掉，`reduce` 操作返回 `null`。只有一个元素，则返回其转换结果，而不应用累加。

针对 `int`、`long` 和 `double` 输出有对应的 `ToInt`、`ToLong` 和 `ToDouble` 特化版本。你需要将输入转换为原始值，并指定默认值和累加函数。当映射为空时，返回默认值。

```java
long sum = map.reduceValuesToLong(threshold, Long::longValue, 0, Long::sum);
```

**警告**：这些特化版本的行为与对象版本不同。它们不是返回转换后的元素，而是与默认值进行累加。因此，默认值必须是累加器的单位元。

#### 12.5.5 并发集合视图

假设你需要一个大型、线程安全的集合而不是映射。目前没有 `ConcurrentHashSet` 类，你最好不要尝试自己创建一个。当然，你可以使用带有虚假值的 `ConcurrentHashMap`，但你得到的是映射而不是集合，而且无法应用 `Set` 接口的操作。

静态方法 `newKeySet` 返回一个 `Set<K>`，它实际上是 `ConcurrentHashMap<K, Boolean>` 的包装器。（所有的映射值都是 `Boolean.TRUE`，但你并不关心，因为你只是作为集合使用。）

```java
Set<String> words = ConcurrentHashMap.<String>newKeySet();
```

当然，如果你已经有一个映射，`keySet` 方法返回键的集合。该集合是可变的。如果你删除了集合中的元素，键（及其值）将从映射中移除。但向键集合添加元素是没有意义的，因为没有对应的值可以添加。`ConcurrentHashMap` 有第二个 `keySet` 方法，它带有一个默认值，用于向集合中添加元素：

```java
Set<String> words = map.keySet(1L);
words.add("Java");
```

如果 `words` 中尚不存在 `"Java"`，现在它的值变为 1。

#### 12.5.6 写时复制数组 (Copy on Write Arrays)

`CopyOnWriteArrayList` 和 `CopyOnWriteArraySet` 是线程安全的集合，所有的修改器都会对底层数组进行拷贝。如果遍历集合的线程远多于修改集合的线程，这种安排就会非常有用。当你创建一个迭代器时，它包含指向当前数组的引用。如果数组随后被修改，迭代器仍然持有旧数组，但集合的数组被替换了。因此，旧的迭代器拥有一个一致（但可能已过时）视图，且无需任何同步开销即可访问该视图。

### 12.5.7 并行数组算法

`Arrays` 类提供了许多并行操作。静态方法 `Arrays.parallelSort` 可以对原始类型或对象的数组进行排序。例如：

```java
var contents = new String(Files.readAllBytes(
    Path.of("alice.txt")), StandardCharsets.UTF_8); // 将文件读入字符串
String[] words = contents.split("[\\P{L}]+"); // 按非字母字符分割
Arrays.parallelSort(words);
```

在排序对象时，你可以提供一个 `Comparator`。

```java
Arrays.parallelSort(words, Comparator.comparing(String::length));
```

对于所有这些方法，你都可以提供范围的边界，例如：

```java
Arrays.parallelSort(words.length / 2, words.length); // 排序后半部分
```

![Image](img/note.jpg) **注意：**

乍一看，这些方法的名称中带有 `parallel`（并行）似乎有点奇怪，因为用户不应该关心排序是如何发生的。然而，API 设计者希望明确表示排序是并行的。这样一来，用户就会注意避免使用带有副作用的比较器。

`parallelSetAll` 方法通过一个函数计算出的值来填充数组。该函数接收元素索引并计算该位置的值。

```java
Arrays.parallelSetAll(values, i -> i % 10);
// 用 0 1 2 3 4 5 6 7 8 9 0 1 2 . . . 填充 values
```

显然，这一操作受益于并行化。它提供了适用于所有原始类型数组和对象数组的版本。

最后，还有一个 `parallelPrefix` 方法，它根据给定的结合律操作，将每个数组元素替换为前缀和。哈？这里有一个示例。考虑数组 `[1, 2, 3, 4, . . .]` 和 `×` 操作。执行 `Arrays.parallelPrefix(values, (x, y) -> x * y)` 后，数组包含：

```java
[1, 1 × 2, 1 × 2 × 3, 1 × 2 × 3 × 4, . . .]
```

可能令人惊讶的是，这种计算是可以并行的。首先，如处所示，合并相邻元素：

```java
[1, 1 × 2, 3, 3 × 4, 5, 5 × 6, 7, 7 × 8]
```

灰色的值保持不变。显然，可以在数组的不同独立区域并行进行此计算。在下一步中，通过将指示元素与其下方一个或两个位置的元素相乘来更新这些元素：

```java
[1, 1 × 2, 1 × 2 × 3, 1 × 2 × 3 × 4, 5, 5 × 6, 5 × 6 × 7, 5 × 6 × 7 × 8]
```

这同样可以并行完成。在经过 `log n` 步后，过程完成。如果有足够的处理器，这比直接的线性计算更有优势。在特殊用途硬件上，这种算法被广泛使用，且此类硬件的用户在将其适应各种问题方面非常有天赋。

#### 12.5.8 旧的线程安全集合

自 Java 最初发布以来，`Vector` 和 `Hashtable` 类就提供了动态数组和哈希表的线程安全实现。这些类现在被认为是过时的，已被 `ArrayList` 和 `HashMap` 类取代。这些类不是线程安全的。相反，集合库提供了一种不同的机制。通过“同步包装器”（synchronization wrapper），任何集合类都可以变变为线程安全的：

```java
List<E> synchArrayList = Collections.synchronizedList(new ArrayList<E>());
Map<K, V> synchHashMap = Collections.synchronizedMap(new HashMap<K, V>());
```

结果集合的方法受锁保护，提供了线程安全的访问。

你应该确保没有线程通过原始的未同步方法访问数据结构。确保此点的最简单方法是不保存原始对象的任何引用。只需构造一个集合并立即将其传递给包装器，正如我们在示例中所做的那样。

如果你想在另一个线程有机会修改集合时对集合进行 `iterate`，你仍然需要使用“客户端”锁定：

```java
synchronized (synchHashMap) {
    Iterator<K> iter = synchHashMap.keySet().iterator();
    while (iter.hasNext()) . ./;
}
```

如果你使用“for each”循环，必须使用相同的代码，因为循环使用了迭代器。注意这……

### 12.6 任务与线程池

创建一个新线程是有开销的，因为涉及到与操作系统的交互。如果你的程序创建了大量短寿命线程，你不应该将每个任务映射到单独线程，而应该使用线程池。线程池包含若干就绪运行的线程。你将 `Runnable` 交给池，其中一个线程会调用 `run` 方法。当 `run` 方法退出时，线程不会消失而是留下来处理下一个请求。

在接下来的章节中，你将看到 Java 并发框架提供的用于协调并发任务的工具。

#### 12.6.1 Callable 和 Future

`Runnable` 封装了一个异步运行的任务；你可以将其看作是一个没有参数也没有返回值的异步方法。`Callable` 与 `Runnable` 类似，但它有。`Callable` 接口是一个泛型接口，只有一个方法 `call`。

```java
public interface Callable<V>
{
    V call() throws Exception;
}
```

类型参数是返回值的类型。例如，`Callable<Integer>` 代表最终返回 `Integer` 对象的异步计算。

`Future` 持有异步计算的 `result`。你启动一个计算，将 `Future` 对象交给某人并忘记它。对象的所有者可以在结果就绪时获取它。

`Future<V>` 接口有以下方法：

```java
V get()
V get(long timeout, TimeUnit unit)
void cancel(boolean mayInterrupt)
boolean isCancelled()
boolean isDone()
```

调用第一个 `get` 方法会阻塞直到计算完成。第二个 `get` 方法也会阻塞，如果在计算完成前超时，它将抛出 `TimeoutException`。如果运行计算的线程被中断，这两个方法都会抛出 `InterruptedException`。如果计算已经完成，`get` 将立即返回。

`isDone` 方法在计算仍在进行时返回 `false`，在计算已完成时返回 `true`。

你可以使用 `cancel` 方法取消计算。如果计算尚未开始，它会被取消且永远不会开始。如果计算当前正在进行中，当当 `mayInterrupt` 参数为 `true` 时，它会被中断。

***

![Image](img/caution.jpg) **注意：**

取消任务涉及两个步骤：首先必须找到并对底层线程进行中断；其次，任务的实现（在 `call` 方法中）必须感知到中断并放弃工作。如果 `Future` 对象不知道任务是在哪个线程上执行的，或者任务没有监控其执行所在线程的被中断状态，那么取消将不起任何作用。

***

执行 `Callable` 的一种方法是使用 `FutureTask`，它同时实现了 `Future` 和 `Runnable` 接口，因此你可以构造一个线程来运行它：

```java
Callable<Integer> task = . . .;
var futureTask = new FutureTask<Integer>(task);
var t = new Thread(futureTask); // it's a Runnable t.start();
. . .
Integer result = futureTask.get(); // it's a Future
```



更常见的做法是将`Callable`传递给执行器。那是下一节的主题。

### `java.util.concurrent.Callable<V>` **5**

***

• `V call()`

运行一个产生结果的任务。

### `java.util.concurrent.Future<V>` **5**

***

• `V get()`

• `V get(long time, TimeUnit unit)`

获取结果，阻塞直到结果可用或给定时间过去。如果第二个方法未成功，则会抛出`TimeoutException`。

• `boolean cancel(boolean mayInterrupt)`

尝试取消此任务的执行。如果任务已经开始且`mayInterrupt`参数为`true`，则它会被中断。如果取消成功，返回`true`。

• `boolean isCancelled()`

如果任务在完成之前被取消，则返回`true`。

• `boolean isDone()`

如果任务通过正常完成、取消或异常而完成，则返回`true`。

### `java.util.concurrent.FutureTask<V>` **5**

***

• `FutureTask(Callable<V> task)`

• `FutureTask(Runnable task, V result)`

构造一个既是`Future<V>`又是`Runnable`的对象。

#### 12.6.2 Executors

`Executors`类有许多静态工厂方法用于构造线程池；摘要请参见表 12.2。

**表 12.2 Executors 工厂方法**

![Images](img/12tab02.jpg)

`newCachedThreadPool`方法构造一个立即执行每个任务的线程池，在有空闲线程可用时使用它，否则创建一个新线程。`newFixedThreadPool`方法构造一个固定大小的线程池。如果提交的任务多于空闲线程，未处理的任务将放置在队列中。它们将在其他任务完成后运行。`newSingleThreadExecutor`是一个大小为 1 的退化线程池，由单个线程按顺序执行提交的任务。这三个方法返回一个实现`ExecutorService`接口的`ThreadPoolExecutor`类对象。

当你有生命周期较短或花费大量时间阻塞的线程时，请使用缓存线程池。然而，如果你有线程正在努力工作且没有阻塞，你就不希望同时运行大量线程。为了获得最佳速度，并发线程的数量应该是处理器核心数。在这种情况下，你应该使用固定线程池来限制并发线程的总数。

单线程执行器对于性能分析很有用。如果你临时将缓存线程池或固定线程池替换为单线程池，可以衡量在没有并发优势的情况下你的应用程序运行速度慢了多少。

***

![Image](img/note.jpg) **备注：**

Java EE 提供了一个`ManagedExecutorService`子类，适用于 Java EE 环境中的并发任务。同样，Play 等 Web 框架提供了用于框架内部任务的执行器服务。

***

你可以使用以下方法之一向`ExecutorService`提交`Runnable`或`Callable`：

```
Future<T> submit(Callable<T> task)
Future<?> submit(Runnable task)
Future<T> submit(Runnable task, T result)
```

池将在其最方便的时候运行提交的任务。当你调用`submit`时，你会得到一个`Future`对象，你可以用它来获取结果或取消任务。

第二个`submit`方法返回一个看起来很奇怪的`Future<?>`。你可以使用此类对象调用`isDone`、`cancel`或`isCancelled`，但`get`方法在完成后简单地返回`null`。

第三种版本的`submit`返回一个`Future`，其`get`方法在完成后返回给定的`result`对象。

当你完成线程池的使用后，调用`shutdown`。该方法启动池的关闭序列。关闭的执行器不再接受新任务。当所有任务完成后，池中的线程会死亡。或者，你可以调用`shutdownNow`。池随后会取消所有尚未开始的任务。

这里总结了你使用线程池的操作：

1. 调用`Executors`的静态`newCachedThreadPool`或`newFixedThreadPool`方法。
2. 使用`submit`提交`Callable`或`Runnable`对象。
3. 获取返回的`Future`对象以便获取结果或取消任务。
4. 在不再需要提交任务时调用`shutdown`。

`ScheduledExecutorService`接口具有调度或重复执行任务的方法。`Executors`的`newScheduledThreadPool`和`newSingleThreadScheduledExecutor`方法返回实现`ScheduledExecutorService`的对象。你可以调度`Runnable`或`Callable`在初始延迟后运行一次。你也可以调度`Runnable`定期运行。详情请参见 API 说明。

### `java.util.concurrent.Executors` **5**

***

• `ExecutorService newCachedThreadPool()`

返回一个需要时创建线程并在空闲 60 秒后终止线程的缓存线程池。

• `ExecutorService newFixedThreadPool(int threads)`

返回一个使用给定数量线程执行任务的线程池。

• `ExecutorService newSingleThreadExecutor()`

返回一个在单线程中顺序执行任务的执行器。

• `ScheduledExecutorService newScheduledThreadPool(int threads)`

返回一个使用给定数量线程调度任务的线程池。

• `ScheduledExecutorService newSingleThreadScheduledExecutor()`

返回一个在单线程中调度任务的执行器。

### `java.util.concurrent.ExecutorService` **5**

***

• `Future<T> submit(Callable<T> task)`

• `Future<T> submit(Runnable task, T result)`

• `Future<?> submit(Runnable task)`

提交给定任务执行。

• `void shutdown()`

关闭服务，完成已提交的任务但不接受新提交。

### `java.util.concurrent.ThreadPoolExecutor` **5**

***

• `int getLargestPoolSize()`

返回此执行器生命周期内线程池的最大大小。

### `java.util.concurrent.ScheduledExecutorService` **5**

***

• `ScheduledFuture<V> schedule(Callable<V> task, long time, TimeUnit unit)`

• `ScheduledFuture<?> schedule(Runnable task, long time, TimeUnit unit)`

在给定时间后调度给定任务。

• `ScheduledFuture<?> scheduleAtFixedRate(Runnable task, long initialDelay, long period, TimeUnit unit)`

在初始延迟后，每隔`period`单位周期性调度给定任务。

• `ScheduledFuture<?> scheduleWithFixedDelay(Runnable task, long initialDelay, long delay, TimeUnit unit)`

在初始延迟后，以固定的延迟`delay`调度给定任务。

调度给定任务以定期运行，在初始延迟结束后，在每次调用完成与下一次调用开始之间有`delay`单位的间隔。

#### 12.6.3 控制任务组

你已经看到过如何使用执行器服务（executor service）作为线程池来提高任务执行的效率。有时，使用执行器是为了更具战术性的考虑——仅仅是为了控制一组相关的任务。例如，你可以使用`shutdownNow`方法取消执行器中的所有任务。

`invokeAny`方法提交`Callable`集合中的所有对象，并返回已完成任务的结果。你并不知道是哪一个任务——推测，它是完成最快的那一个。对于你乐意接受任何解决方案的搜索问题，请使用此方法。例如，假设你需要对一个大整数进行因数分解——这是破解 RSA 密所需的计算。你可以提交多个任务，每个任务尝试对不同范围内的数字进行因数分解。一旦其中一个任务有了答案，你的计算就可以停止。

`invokeAll`方法提交`Callable`集合中的所有对象，阻塞直到所有任务都完成，并返回一个代表所有任务解决方案的`Future`对象列表。当计算结果可用时，你可以像这样处理它们：

```
List<Callable<T>> tasks = . . .;
List<Future<T>> results = executor.invokeAll(tasks);
for (Future<T> result : results)
    processFurther(result.get());
```

在`for`循环中，第一次调用`result.get()`会阻塞直到第一个结果可用。如果所有任务都在大约相同的时间完成，这就不是问题。然而，可能值得按照结果产生的顺序来获取它们。这可以通过`ExecutorCompletionService`来安排。

从通常方式获取执行器开始。然后构造一个`ExecutorCompletionService`。将任务提交到完成服务中。该服务管理一个`Future`对象的阻塞队列，在提交任务的结果可用时将其包含其中。因此，对于上述计算，更高效的组织方式如下：

```
var service = new ExecutorCompletionService<T>(executor);
for (Callable<T> task : tasks) service.submit(task);
for (int i = 0; i < tasks.size(); i++)
    processFurther(service.take().get());
```

程序 Listing 12.8 展示了如何使用 callables 和 executors。在第一次计算中，我们统计目录树中包含给定单词的文件数。我们为每个文件创建了一个独立的任务：

```
Set<Path> files = descendants(Path.of(start));
var tasks = new ArrayList<Callable<Long>>();
for (Path file : files)
{
    Callable<Long> task = () -> occurrences(word, file);
    tasks.add(task);
}
```

然后我们将任务提交给执行器服务：

```
ExecutorService executor = Executors.newCachedThreadPool();
List<Future<Long>> results = executor.invokeAll(tasks);
```

为了获得合并后的计数，我们相加所有结果，阻塞直到它们可用：

```
long total = 0;
for (Future<Long> result : results)
    total += result.get();
```

程序还显示了搜索期间花费的时间。在某处解压 JDK 源码并运行搜索。然后将执行器服务替换为单线程执行器并再次尝试，看看并发计算是否更快。

在程序的第二部分，我们搜索包含给定单词的第一个文件。我们使用`invokeAny`来并行化搜索。在这里，我们在构建任务时必须更加小心。`invokeAny`方法在任何任务*返回*后就会终止。因此，我们不能让搜索任务返回`boolean`来指示成功或失败。我们不希望在任务失败时停止搜索。相反，失败的任务会抛出`NoSuchElementException`。此外，当一个任务成功时，其他任务会被取消。因此，我们监控中断状态。如果底层线程被中断，搜索任务会在终止前打印一条消息，这样你就可以看到取消是有效的。

```
public static Callable<Path> searchForTask(String word, Path path)
{
    return () ->
        {
            try (var in = new Scanner(path))
            {
                while (in.hasNext())
                {
                    if (in.next().equals(word)) return path;
                    if (Thread.currentThread().isInterrupted())
                    {
                        System.out.println("Search in " + path + " canceled.");
                        return null;
                    }
                }
            }
            throw new NoSuchElementException();
        }
    };
}
```

出于信息提示之目的，此程序打印了执行期间最大的池大小。此信息无法通过`ExecutorService`接口获取。因此，我们必须将池对象强制转换为`ThreadPoolExecutor`类。

* * *

![Image](img/tip.jpg) **提示：**

在你阅读这个程序时，你可以体会到执行器服务有多么有用。在你自己的程序中，你应该使用执行器服务来管理线程，而不是单独地启动线程。

* * *

**Listing 12.8** `executors/ExecutorDemo.java`

```java
package executors;

import java.io.*;
import java.nio.file.*;
import java.time.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.stream.*;

/**
 * 此程序演示了 Callable 接口和执行器。
 * @version 1.01 2021-05-30
 * @author Cay Horstmann
 */
public class ExecutorDemo
{
    /**
     * 统计文件中给定单词的出现次数。
     * @return 单词在给定文件中出现的次数
     */
    public static long occurrences(String word, Path path)
    {
        try (var in = new Scanner(path))
        {
            int count = 0;
            while (in.hasNext())
                if (in.next().equals(word)) count++;
            return count;
        }
        catch (IOException ex)
        {
            return 0;
        }
    }

    /**
     * 返回给定目录的所有后代节点——参见卷第二的第 1 章和第 2 章。
     * @param rootDir 根目录
     * @return 根目录所有后代的集合
     */
    public static Set<Path> descendants(Path rootDir) throws IOException
    {
        try (Stream<Path> entries = Files.walk(rootDir))
        {
            return entries.filter(Files::isRegularFile)
                .collect(Collectors.toSet());
        }
    }

    /**
     * 产生一个在文件中搜索单词的任务。
     * @param word 要搜索的单词
     * @param path 要搜索的文件
     * @return 成功后返回路径的搜索任务
     */
    public static Callable<Path> searchForTask(String word, Path path)
    {
        return () -> {
            try (var in = new Scanner(path))
            {



```java
while (in.hasNext())
{
    if (in.next().equals(word)) return path;

    if (Thread.currentThread().isInterrupted())
    {
        System.out.println("Search in " + path + " canceled.");
        return null;
    }
}

throw new NoSuchElementException();

};

}

public static void main(String[] args)
    throws InterruptedException, ExecutionException, IOException
{
    try (var in = new Scanner(System.in))
    {
        System.out.print("Enter base directory (e.g. /opt/jdk-src): ");
        String start = in.nextLine();

        System.out.print("Enter keyword (e.g. volatile): ");
        String word = in.nextLine();

        Set<Path> files = descendants(Path.of(start));
        var tasks = new ArrayList<Callable<Long>>();

        for (Path file : files)
        {
            Callable<Long> task = () -> occurrences(word, file);
            tasks.add(task);
        }

        ExecutorService executor = Executors.newCachedThreadPool();

        // 改用单线程来查看多线程是否
        // 加快搜索
        // ExecutorService executor = Executors.newSingleThreadExecutor();

        Instant startTime = Instant.now();
        List<Future<Long>> results = executor.invokeAll(tasks);

        long total = 0;
        for (Future<Long> result : results)
            total += result.get();

        Instant endTime = Instant.now();

        System.out.println("Occurrences of " + word + ": " + total);
        System.out.println("Time elapsed: "
            + Duration.between(startTime, endTime).toMillis() + " ms");

        var searchTasks = new ArrayList<Callable<Path>>();

        for (Path file : files)
        {
            searchTasks.add(searchForTask(word, file));
        }

        Path found = executor.invokeAny(searchTasks);
        System.out.println(word + " occurs in: " + found);

        if (executor instanceof ThreadPoolExecutor tpExecutor)
        {
            // 线程执行器并不是
            System.out.println("Largest pool size: "
                + tpExecutor.getPoolSize());

            executor.shutdown();
        }
    }
}
}
```

### `java.util.concurrent.ExecutorService`

- `T invokeAny(Collection<?Callable<T>> tasks)`
- `T invokeAny(Collection<?Callable<T>> tasks, long timeout, TimeUnit unit)`

执行给定的任务并返回其中一个任务的结果。如果发生超时，第二个方法抛出 `TimeoutException`。

- `List<Future<T>> invokeAll(Collection<?Callable<T>> tasks)`
- `List<Future<T>> invokeAll(Collection<?Callable<T>> tasks, long timeout, TimeUnit unit)`

执行给定的任务并返回所有任务的结果。如果发生超时，第二个方法抛出 `TimeoutException`。

### `java.util.concurrent.ExecutorCompletionService<V>`

- `ExecutorCompletionService(Executor e)`

构造一个执行器完成服务，用于收集给定执行器的结果。

- `Future<V> submit(Callable<V> task)`
- `Future<V> submit(Runnable task, V result)`

将任务提交给底层执行器。

- `Future<V> take()`

移除并下一个完成的结果，如果没有可用结果则阻塞。

- `Future<V> poll()`
- `Future<V> poll(long time, TimeUnit unit)`

移除并返回下一个完成的结果，如果没有可用结果则返回 `null`。第二个方法会等待指定的时间。

#### 12.6.4 Fork-Join 框架

某些应用程序使用大量空闲的线程。例如，每个连接使用一个线程的 Web 服务器。其他应用程序每个处理器核心使用一个线程，以执行计算密集型任务，如图像或视频处理。在 Java 7 中出现的 Fork-Join 框架旨在支持后者。

假设你有一个自然分解为子任务的处理任务，如下：

```text
if (problemSize < threshold)
    直接解决问题
else
{
    将问题分解为子问题
    递归地解决每个子问题
    合并结果
}
```

其中一个例子是图像处理。为了增强图像，你可以转换上半部分和下半部分。如果你有足够的空闲处理器，这些操作就可以并行运行。（你可能需要在分割两部分的条带沿处做一些额外工作，但这是一个技术细节。）

在这里，我们讨论一个更简单的例子。假设我们想要统计数组中有多少元素符合特定属性。我们将数组一分为两半，计算每个部分的计数，并把它们相加。

为了将递归计算写成框架可以使用的格式，请提供一个扩展 `RecursiveTask<T>`（如果计算产生类型为 `T` 的结果）或 `RecursiveAction`（如果不产生结果）的类。重写 `compute` 方法来生成并调用子任务，并合并它们的结果。

```java
class Counter extends RecursiveTask<Integer>
{
    ...
    protected Integer compute()
    {
        if (to - from < THRESHOLD)
        {
            直接解决问题
        }
        else
        {
            int mid = from + (to - from) / 2;

            var first = new Counter(values, from, mid, filter);
            var second = new Counter(values, mid, to, filter);

            invokeAll(first, second);
            return first.join() + second.join();
        }
    }
}
```

![Image](img/note.jpg) **注意：**

还有一个用于获取当前结果的 `get` 方法，但它不太吸引人，因为它抛出检查异常，而我们不允许在 `compute` 方法中抛出这些异常。

Listing 12.9 显示了完整示例。

在底层，fork-join 框架使用了一种名为“工作窃取”（work stealing）的有效启发式算法来在可用线程之间平衡工作负载。每个工作线程都有一个 `deque`（双端队列）用于存放任务。工作线程将子任务推到其自己的 `deque` 的头部。（只有一个线程访问头部，因此不需要锁定。）当一个工作线程处于空闲时，它会从另一个 `deque` 的尾部“窃取”一个任务。由于较大的子任务位于尾部，这种窃取非常罕见。

---

![Image](img/caution.jpg) **注意：**

Fork-join 池针对非阻塞工作负载进行了优化。如果你向 fork-join 池中添加了许多阻塞任务，可能会导致其饥饿。可以通过让任务实现 `ForkJoinPool.ManagedBlocker` 接口来克服这一点，但这是一项我们不会讨论的高级技术。

---

**Listing 12.9** `forkJoin/ForkJoinTest.java`

```java
package forkJoin;

import java.util.concurrent.*;
import java.util.function.*;

/**
 * 此程序演示了 fork-join 框架。
 * @version 1.02 2021-06-17
 * @author Cay Horstmann
 */
public class ForkJoinTest
{
    public static void main(String[] args)
    {
        final int SIZE = 10000000;
        var numbers = new double[SIZE];

        for (int i = 0; i < SIZE; i++)
            numbers[i] = Math.random();

        var counter = new Counter(
            numbers, 0, numbers.length, x -> x > 0.5);

        var pool = new ForkJoinPool();
        pool.invoke(counter);

        System.out.println(counter.join());
    }
}

class Counter extends RecursiveTask<Integer>
{
    public static final int THRESHOLD = 1000;

    private double[] values;
    private int from;
    private int to;
    private DoublePredicate filter;

    public Counter(
        double[] values,
        int from,
        int to,
        DoublePredicate filter)
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
                if (filter.test(values[i]))
                    count++;
            }

            return count;
        }
        else
        {
            int mid = from + (to - from) / 2;

            var first = new Counter(values, from, mid);
            var second = new Counter(values, mid, to, filter);

            invokeAll(first, second);
            return first.join() + second.join();
        }
    }
}
```

### 12.7 异步计算

到为止，我们处理并发计算的方法是拆分任务，然后等待所有部分完成。但等待并不总是一个好主意。在接下来的章节中，你将看到如何实现无等待（或 `asynchronous`）计算。

#### 12.7.1 Completable Futures

当你有一个 `Future` 对象时，你需要调用 `get` 来获取值，这会阻塞直到值可用。`CompletableFuture` 类实现了 `Future` 接口，并提供了获取结果的第二种机制。你可以注册一个回调（callback），一旦结果可用，该回调就会（在某个线程中）被调用。

```java
CompletableFuture<String> f = ...

f.thenAccept(s -> Process the result s);
```

通过这种方式，你可以在结果可用时无需阻塞就对其进行处理。有一些 API 方法返回 `CompletableFuture` 对象。例如，你可以使用在 II 卷第 4 章中会遇到的 `HttpClient` 类来获取网页：

```java
HttpClient client = HttpClient.newHttpClient();

HttpRequest request = HttpRequest
    .newBuilder(URI.create(urlString))
    .GET()
    .build();

CompletableFuture<HttpResponse<String>> f = client.sendAsync(
    request,
    BodyHandlers.ofString());
```

如果有一个方法可以直接产生一个现成的 `CompletableFuture` 那就很好了，但大多数时候，你需要自己创建一个。要异步运行任务并获取 `CompletableFuture`，你不需要直接将其提交给执行器。相反，你应该调用静态方法 `CompletableFuture.supplyAsync`。以下是在不借助 `HttpClient` 类优势的情况下读取网页的方法：

```java
public CompletableFuture<String> readPage(URL url)
{
    return CompletableFuture.supplyAsync(() ->
        try
        {
            return new String(
                url.openStream().readAllBytes(),
                "UTF-8");
        }
        catch (IOException e)
        {
            throw new UncheckedIOException(e);
        }
    );
}
```




# `CompletableFuture`

非阻塞调用是通过回调实现的。程序员为任务完成后应该执行的动作注册一个回调。当然，如果下一个动作也是异步的，那么该动作之后的后续动作将位于另一个回调中。尽管程序员在思考时是“先执行第 1 步，然后是第 2 步，最后是第 3 步”，程序逻辑可能会分散在“回调地狱”中。当必须添加错误处理时，情况会更加糟糕。假设第 2 步是“用户登录”。由于用户可能输入错误的凭据，你可能需要重复该步骤。在一组回调中实现这种控制流，或者在实现后去理解它，都是是非常具有挑战性的。

`CompletableFuture` 类通过提供一种将异步任务组合成处理流水线的机制来解决这个问题。

例如，假设我们想从一个网页中提取所有图像。假设我们有一个方法：

```java
public CompletableFuture<String> readPage(URL url)
```

它在网页内容可用时产生该网页的文本。如果方法

```java
public List<URL> getImageURLs(String page)
```

产生 HTML 页面中图像的 URL，你可以安排在页面可用时调用它：

```java
CompletableFuture<String> contents = readPage(url);

CompletableFuture<List<URL>> imageURLs = contents.thenApply(this::getLinks);
```

`thenApply` 方法也不会阻塞。它返回另一个 future。当第一个 future 完成时，它的结果会被传送给 `getImageURLs` 方法，而该方法的返回值将成为最终结果。

通过 completable futures，你只需要指定你想执行的操作以及执行顺序。当然，这些操作并不会立即发生，但重要的是所有的代码都在同一个地方。

从概念上说，`CompletableFuture` 是一个简单的 API，但有许多变体方法可以用于组合 completable futures。让我们先看看那些处理单个 future 的方法（参见表 12.3）。在表格中，我为冗长的函数式接口使用了简记法，用 `T -> U` 代替 `Function<? super T, U>`。当然，这些并不是实际的 Java 类型。

对于显示的每个方法，还有两个我没有显示的 `Async` 变体。其中一个使用通用的 `ForkJoinPool`，另一个带有一个 `Executor` 参数。

你已经见过 `thenApply` 方法。假设 `f` 是一个接收 `T` 类型值并返回 `U` 类型值的函数。以下调用：

```java
CompletableFuture<U> future.thenApply(f);

CompletableFuture<U> future.thenApplyAsync(f, executor);
```

返回一个 future，当 `future` 的结果可用时将函数 `f` 应用于它。第二次调用使用另一个 executor 运行 `f`。

`thenCompose` 方法接收的不是将类型 `T` 映射到类型 `U` 的函数，而是将 `T` 映射到 `CompletableFuture<U>` 的函数。这听起来相当抽象，但可以非常自然。考虑从给定 URL 读取网页的动作。与其提供一个方法：

```java
public String blockingReadPage(URL url)
```

不如让该方法返回一个 future 更优雅：

```java
public CompletableFuture<String> readPage(URL url)
```

现在，假设我们有另一个方法从用户输入获取 URL，可能来自一个在用户点击 OK 按钮之前不会显示答案的对话框。那也是未来发生的一个事件：

```java
public CompletableFuture<URL> getURLInput(String prompt)
```

这里我们有两个函数 `T -> CompletableFuture<U>` 和 `U -> CompletableFuture<V>`。显然，如果当第一个函数完成后调用第二个函数，那么它们就组合成一个函数 `T -> CompletableFuture<V>`。这正是 `thenCompose` 所做的。

在前面的节中，你看到了了用于处理异常的 `whenComplete` 方法。还有一个 `handle` 方法，它需要一个函数来处理结果或异常并计算新结果。在许多情况下，调用 `exceptionally` 方法反而更简单。该方法在发生异常时计算一个占位值：

```java
CompletableFuture<List<URL>> imageURLs = readPage(url)
    .exceptionally(ex -> "<html></html>")
    .thenApply(this::getImageURLs);
```

你可以用的方式处理超时：

```java
CompletableFuture<List<URL>> imageURLs = readPage(url)
    .completeOnTimeout("<html></html>", 30, TimeUnit.SECONDS)
    .thenApply(this::getImageURLs);
```

或者，你可以在超时时抛出异常：

```java
CompletableFuture<String> = readPage(url).orTimeout(30, TimeUnit.SECONDS);
```

表 12.3 中结果为 `void` 的方法通常用于处理流水线的末尾。

现在让我们转向组合多个 future 的方法（参见表 12.4）。

前三个方法并发运行 `CompletableFuture<T>` 和 `CompletableFuture<U>` 动作并合并结果。

接下来的三个方法并发运行两个 `CompletableFuture<T>` 动作。只要其中一个完成，它的结果就会被传递，另一个结果被忽略。

最后，静态的 `allOf` 和 `anyOf` 方法接受任意数量的 completable futures，并产生一个 `CompletableFuture<Void>`，该 future 在所有任务或任意一个任务完成后完成。`allOf` 方法不产生结果。`anyOf` 方法不会终止剩余的任务。

## 表 12.3：向 `CompletableFuture<T>` 对象添加动作

![Images](img/12tab03.jpg)

---

> **注意：** 从技术上来说，本节的方法接受 `CompletionStage` 类型参数，而不是 `CompletableFuture`。`CompletionStage` 接口描述了如何组合异步计算，而 `Future` 接口关注计算的结果。`CompletableFuture` 既是 `CompletionStage` 也是 `Future`。

---

列表 12.10 显示了一个完整的程序，读取网页、扫描图像、加载图像并保存到本地。注意所有耗时方法都返回 `CompletableFuture`。为了启动异步计算，我们使用了一个小技巧。与其直接调用 `readPage` 方法，不如用 URL 参数创建一个完成的 future，然后将该 future 与 `this::readPage` 组合。这样，流水线就有非常统一的外观：

```java
CompletableFuture.completedFuture(url)
    .thenComposeAsync(this::readPage, executor)
    .thenApply(this::getImageURLs)
    .thenCompose(this::getImages)
    .thenAccept(this::saveImages);
```

## 表 12.4：组合多个组合对象

![Images](img/12tab04.jpg)

## 列表 12.10：`completableFutures/CompletableFutureDemo.java`

```java
package completableFutures;

import java.awt.image.*;

import java.io.*;

import java.net.*;

import java.nio.charset.*;

import java.util.*;

import java.util.concurrent.*;

import java.util.regex.*;

import javax.imageio.*;

public class CompletableFutureDemo
{
    private static final Pattern IMG_PATTERN = Pattern.compile(
        "[<]\\s*[iI][mM][gG]\\s*[^>]*[sS][rR][cC]\\s*[=]\\s*'\"['\"][^>]*[>]");

    private ExecutorService executor = Executors.newCachedThreadPool();

    private URL urlToProcess;

    public CompletableFuture<String> readPage(URL url)
    {
        return CompletableFuture.supplyAsync(() ->
        {
            try
            {
                var contents = new String(url.openStream().readAllBytes(),
                    StandardCharsets.UTF_8);

                System.out.println("Read page from " + url);

                return contents;
            }
            catch (IOException e)
            {
                throw new UncheckedIOException(e);
            }
        }, executor);
    }

    public List<URL> getImageURLs(String webpage) // 不耗时操作
    {
        try
        {
            var result = new ArrayList<URL>();

            Matcher matcher = IMG_PATTERN.matcher(webpage);

            while (matcher.find())
            {
                var url = new URL(urlToProcess, matcher.group(1));
                result.add(url);
            }

            System.out.println("Found URLs: " + result);

            return result;
        }
        catch (IOException e)
        {
            throw new UncheckedIOException(e);
        }
    }

    public CompletableFuture<List<BufferedImage>> getImages(List<URL> urls)
    {
        return CompletableFuture.supplyAsync(() ->
        {
            try
            {
                var result = new ArrayList<BufferedImage>();

                for (URL url : urls)
                {
                    result.add(ImageIO.read(url));
                    System.out.println("Loaded " + url);
                }

                return result;
            }
            catch (IOException e)
            {
                throw new UncheckedIOException(e);
            }
        }, executor);
    }

    public void saveImages(List<BufferedImage> images)
    {
        System.out.println("Saving " + images.size() + " images");

        try
        {
            for (int i = 0; i < images.size(); i++)
            {
                String filename = "/tmp/image" + (i + 1) + ".png";
                ImageIO.write(images.get(i), "PNG", new File(filename));
            }
        }
        catch (IOException e)
        {
            throw new UncheckedIOException(e);
        }

        executor.shutdown();
    }

    public void run(URL url)
        throws IOException, InterruptedException
    {
        urlToProcess = url;

        CompletableFuture.completedFuture(url)
            .thenComposeAsync(this::readPage, executor)
            .thenApply(this::getImageURLs)
            .thenCompose(this::getImages)
            .thenAccept(this::saveImages);

        /*
        // 或者使用 HTTP 客户端：

        HttpClient client = HttpClient.newBuilder().build();

        HttpRequest request = HttpRequest.newBuilder(urlToProcess.toURI()).GET()
            .build();

        client.sendAsync(request, BodyHandlers.ofString())
            .thenApply(HttpResponse::body)
            .thenApply(this::getImageURLs)
            .thenCompose(this::getImages)
            .thenAccept(this::saveImages);
        */
    }

    public static void main(String[] args)
        throws IOException, InterruptedException
    {
        new CompletableFutureDemo().run(new URL("http://horstmann.com/index.html"));
    }
}
```

## 2.7.3 用户界面回调中的耗时任务

使用线程的原因之一是让你的程序更具响应性。这在具有用户界面的应用程序中尤为重要。当你的程序需要执行耗时操作时，你不能在用户界面线程中执行工作，否则用户界面将被冻结。相反，应该启动另一个工作线程。

例如，如果你想在用户点击按钮时读取文件，请不要这样做：

```java
var open = new JButton("Open");

open.addActionListener(event ->
{ // 错误--耗时操作在 UI 线程上执行
    var in = new Scanner(file);

    while (in.hasNextLine())
    {
        String line = in.nextLine();
        ...
    }
});
```

相反，请在独立的线程中执行工作。

```java
open.addActionListener(event ->
{ // 正确--耗时操作在独立线程中执行
    Runnable task = () ->
    {
        var in = new Scanner(file);

        while (in.hasNextLine())
        {
            String line = in.nextLine();
            ...
        }
    };

    executor.execute(task);
});
```




然而，你不能直接从执行耗时任务的工作线程更新用户界面。诸如 `Swing`、`JavaFX` 或 `Android` 等用户界面不是线程安全的。你不能从多个线程中操作用户界面元素，否则它们有损坏的风险。事实上，`JavaFX` 和 `Android` 会检查这一点，如果你尝试从 UI 其他线程访问用户界面，它们会抛出异常。

因此，你需要将任何 UI 更新调度在 UI 线程上执行。每个用户界面库都提供某种在 UI 线程上调度 `Runnable` 的机制。例如，在 `Swing` 中，你调用：

```java
EventQueue.invokeLater(() -> label.setText(percentage + "% complete"));
```

在工作线程中实现用户反馈是乏味的，因此每个用户界面库都提供了某种辅助类来管理细节，例如 `Swing` 中的 `SwingWorker`、`JavaFX` 中的 `Task` 以及 `Android` 中的 `AsyncTask`。你指定了耗时任务的操作（在独立线程上运行），以及进度更新和最终处理（在 UI 线程上运行）。

`Listing 12.11` 中的程序具有加载文本文件和取消文件加载过程的命令。你应该尝试使用长文件运行该程序，例如书籍配套代码中 `gutenberg` 目录提供的《基督山伯爵》全文。文件是在独立线程中加载的。当文件正在读取时，Open 菜单项被禁用，Cancel 项被启用（见图 12.6）。每读取一行，状态栏中的行计数器就会更新。

![Images](img/12fig06.jpg)

**图 12.6** 在独立线程中加载文件

假设一个工作线程会产生某种结果；因此，`SwingWorker<T, V>` 实现了 `Future<T>`。该结果可以通过 `Future` 接口的 `get` 方法获取。由于 `get` 方法会阻塞直到结果可用，因此你不希望在调用 `execute` 之后立即调用它。最好的做法是在确定工作已经完成时再调用它。通常，你会在 `done` 方法中调用 `get`。（并没有强制调用 `get`。有时，你只需要处理进度数据就足够了。）

中间进度数据和最终结果可以是任意类型。`SwingWorker` 类将这些类型作为类型参数。一个 `SwingWorker<T, V>` 会产生一个类型为 `T` 的结果和一个类型为 `V` 的进度数据。

要取消正在进行的工作，请使用 `Future` 接口的 `cancel` 方法。当工作被取消时，`get` 方法会抛出 `CancellationException`。

如前所述，工作线程调用 `publish` 会导致在事件分发线程上调用 `process`。为了提高效率，多次调用 `publish` 的结果可能会合并在单次 `process` 调用中。`process` 方法接收一个包含所有中间结果的 `List<V>`。

让我们利用这一机制来读取文本文件。事实证明，`JTextArea` 的速度非常慢。从长文本文件中追加行（例如《基督山德贡亚伯爵》中的所有行）需要花费大量时间。

为了向用户显示正在处理进度，我们希望在状态栏中显示已读取的行数。因此，进度数据由当前行号和当前行的文本组成。我们将这些封装进一个简单的内部类中：

```java
private class ProgressData
{
   public int number;
   public String line;
}
```

最终结果是已读取到 `StringBuilder` 中的文本。因此，我们需要一个 `SwingWorker<StringBuilder, ProgressData>`。

在 `doInBackground` 方法中，我们逐行读取文件。在处理完每一行后，我们都调用 `publish` 来发布当前行号和当前行的文本。

```java
@Override public StringBuilder doInBackground() throws IOException, InterruptedException
{
   int lineNumber = 0;
   var in = new Scanner(new FileInputStream(file), StandardCharsets.UTF_8);
   while (in.hasNextLine())
   {
      String line = in.nextLine();
      lineNumber++;
      text.append(line).append("\n");
      var data = new ProgressData();
      data.number = lineNumber;
      data.line = line;
      publish(data);
      Thread.sleep(1); // 为了测试取消；在你的程序中没必要这样做
   }
   return text;
}
```

我们在每行之后都让线程睡眠一毫秒，以便你可以在不感到压力的情况下测试取消，但你不会希望通过睡眠来减慢自己的程序。如果你注释掉这一行，你会发现《基督山德贡亚伯爵》加载得非常快，只有几次批处理的用户界面更新。

在 `process` 方法中，我们忽略除最后一个号之外的所有行号，并合并所有行以对文本区域进行单更新。

```java
@Override public void process(List<ProgressData> data)
{
   if (isCancelled()) return;
   var b = new StringBuilder();
   statusLine.setText("" + data.get(data.size() - 1).number);
   for (ProgressData d : data) b.append(d.line).append("\n");
   textArea.append(b.toString());
}
```

在 `done` 方法中，文本区域将更新为完整文本，并禁用“取消”菜单项。

注意“打开”菜单项的事件监听器是如何启动工作线程的。

这种简单的技术允许你在执行耗时任务的同时，保持用户界面的响应。

**列表 12.11** `swingWorker/SwingWorkerTest.java`

```java
package swingWorker;

import java.awt.*;

import java.io.*;

import java.nio.charset.*;

import java.util.*;

import java.util.List;

import java.util.concurrent.*;

import javax.swing.*;

/**
 * 此程序演示了一个运行可能耗时任务的工作线程。
 *
 * @version 1.12 2018-03-17
 * @author Cay Horstmann
 */
public class SwingWorkerTest
{
    public static void main(String[] args) throws Exception
    {
        EventQueue.invokeLater(() ->
        {
            var frame = new SwingWorkerFrame();
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 此框架包含一个文本区域用于显示文本文件的内容，一个用于打开文件并
 * 取消打开的菜单，以及一个显示文件加载进度的状态栏。
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

        var menuBar = new JMenuBar();
        setJMenuBar(menuBar);

        var menu = new JMenu("File");
        menuBar.add(menu);

        openItem = new JMenuItem("Open");
        menu.add(openItem);

        openItem.addActionListener(event ->
        {
            // 显示文件选择器对话框
            int result = chooser.showOpenDialog(null);

            // 如果选择了文件，则将其设置为标签的图标
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

        // 以下方法在工作线程中执行；它们不要触碰 Swing 组件
        public StringBuilder doInBackground() throws IOException, InterruptedException
        {
            int lineNumber = 0;

            try (var in = new Scanner(new FileInputStream(file), StandardCharsets.UTF_8))
            {
                while (in.hasNextLine())
                {
                    String line = in.nextLine();
                    lineNumber++;
                    text.append(line).append("\n");

                    var data = new ProgressData();
                    data.number = lineNumber;
                    data.line = line;
                    publish(data);

                    Thread.sleep(1); // 用于测试取消；在你的程序中不需要这样做
                }
            }

            return text;
        }

        // 以下方法在事件分发线程中执行
        public void process(List<ProgressData> data)
        {
            if (isCancelled()) return;

            var builder = new StringBuilder();
            statusLine.setText("" + data.get(data.size() - 1).number);

            for (ProgressData d : data)
                builder.append(d.line).append("\n");

            textArea.append(builder.toString());
        }

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
                statusLine.setText("Cancelled");
            }
            catch (ExecutionException ex)
            {
                statusLine.setText("" + ex.getCause());
            }

            cancelItem.setEnabled(false);
            openItem.setEnabled(true);
        }
    };
}
```

### `javax.swing.SwingWorker<T, V>`

- `abstract T doInBackground()` 被重写以执行后台任务并返回结果。
- `void process(List<V> data)` 被重写以便事件分发线程中处理中间数据。
- `void publish(V... data)` 将中间数据转发到事件分发线程。在 `doInBackground` 中调用此方法。
- `void execute()` 调度工作在工作线程上执行。
- `State getState()` 获取工作的状态：`PENDING`、`STARTED` 或 `DONE`。

### Processes

到目前为止，你已经了解如何在程序内部线程中执行 Java 代码。有时你需要执行另一个程序。对于这种情况，使用 `ProcessBuilder` 和 `Process` 类。`Process` 类在独立的操作系统进程中执行命令，并允许你与其标准输入、输出和错误流进行交互。`ProcessBuilder` 类允许你配置 `Process` 对象。

#### 12.8.1 构建进程

首先指定你想要执行的命令。你可以提供一个 `List<String>` 或直接提供组成命令的字符串。



```java
var builder = new ProcessBuilder("gcc", "myapp.c");
```

> **注意：**
>
> 构建列表的第一个字符串必须是可执行的命令，而不是 shell 内置命令。例如，在 Windows 上运行 `dir` 命令，你需要构建一个包含 `"cmd.exe"`、`"/C"` 和 `"dir"` 字符串的进程。

每个进程都有*工作目录*，用于解析相对目录名称。默认情况下，进程具有虚拟机相同的工作目录，这通常是你启动 `java` 程序时的目录。你可以通过 `directory` 方法来更改它：

```java
builder = builder.directory(path.toFile());
```

请注意，进程的输入流是 JVM 中的一个输出流！你向该流写入内容，你写入的任何内容将成为进程的输入。相反，你读取进程写入输出和错误流的内容。对你来说，它们是输入流。

你可以指定新进程的输入、输出和错误流与 JVM 相同。如果用户在控制台中运行 JVM，任何用户输入都将被转发到进程，而进程的输出将显示在控制台中。调用

```java
builder.inheritIO()
```

可以对所有三个流进行此设置。如果你只想继承某些流，请将值

```java
ProcessBuilder.Redirect.INHERIT
```

传递给 `redirectInput`、`redirectOutput` 或 `redirectError` 方法。例如：

```java
builder.redirectOutput(ProcessBuilder.Redirect.INHERIT);
```

你可以通过提供 `File` 对象将进程流重定向到文件：

```java
builder.redirectInput(inputFile)
    .redirectOutput(outputFile)
    .redirectError(errorFile);
```

当进程启动时，输出和错误文件将被创建或截断。若要向现有文件追加内容，请使用

```java
builder.redirectOutput(ProcessBuilder.Redirect.appendTo(outputFile));
```

合并输出和错误流通常很有用，这样你就能按照进程生成输出的顺序看到输出和错误消息。调用

```java
builder.redirectErrorStream(true)
```

激活合并。如果你这样做，就不能再在 `ProcessBuilder` 上调用 `redirectError` 或在 `Process` 上调用 `getErrorStream` 了。

你可能还想修改进程的环境变量。在这里，构建器链的语法中断了。你需要获取构建器的环境（它由运行 JVM 的进程的环境变量初始化），然后放入或移除条目。

```java
Map<String, String> env = builder.environment();

env.put("LANG", "fr_FR");

env.remove("JAVA_HOME");

Process p = builder.start();
```

如果你想将一个进程的输出管道到另一个进程的输入（类似于 shell 中的 `|` 运算符），Java 9 提供了 `startPipeline` 方法。传递一个 process builder 列表并从最后一个进程读取结果。这里有一个示例，用于列出目录树中唯一的扩展名：

```java
List<Process> processes = ProcessBuilder.startPipeline(List.of(
    new ProcessBuilder("find", "/opt/jdk-17"),
    new ProcessBuilder("grep", "-o", "\\.[^./]*$"),
    new ProcessBuilder("sort"),
    new ProcessBuilder("uniq")
));

Process last = processes.get(processes.size() - 1);

var result = new String(last.getInputStream().readAllBytes());
```

当然，这个特定任务通过在 Java 中进行目录遍历会比运行四个进程更高效。第二卷的第 2 章 将向你展示如何这样做。

## 12.8.2 运行进程

配置好构建器后，调用其 `start` 方法来启动进程。如果你将输入、输出和错误流配置为管道，现在你可以向输入流写入并读取输出和错误流了。例如：

```java
Process process = new ProcessBuilder("/bin/ls", "-l")
    .directory(Path.of("/tmp").toFile())
    .start();

try (var in = new Scanner(process.getInputStream())) {
    while (in.hasNextLine())
        System.out.println(in.nextLine());
}
```

> ![Image](img/caution.jpg) **注意：**
>
> 进程流的缓冲区空间有限。你不应该淹没输入，并且应该及时读取输出。如果有大量的输入和输出，你可能需要在单独的线程中对其进行生产和消费。

要等待进程完成，调用

```java
int result = process.waitFor();
```

或者，如果你不想无限期地等待，可以这样做：

```java
long delay = . . .;

if (process.waitFor(delay, TimeUnit.SECONDS)) {
    int result = process.exitValue(); . . .
} else {
    process.destroyForcibly();
}
```

第一次调用 `waitFor` 返回进程的退出值（按照约定，`0` 表示成功，非零表示错误代码）。第二次调用如果进程没有超时，则返回 `true`。然后你需要通过调用 `exitValue` 方法来获取退出值。

与其等待进程完成，你也可以让它保持运行，并偶尔调用 `isAlive` 来查看它是否仍然存活。要杀死进程，调用 `destroy` 或 `destroyForcibly`。这些调用之间的区别取决于平台。在 UNIX 上，前者使用 `SIGTERM` 终止进程，后者使用 `SIGKILL`。（如果 `destroy` 方法可以正常终止进程，则 `supportsNormalTermination` 方法返回 `true`。）

最后，你可以在进程完成时接收一个异步通知。调用 `process.onExit()` 会产生一个 `CompletableFuture<Process>`，你可以用它来调度任何操作。

```java
process.onExit().thenAccept(
    p -> System.out.println("Exit value: " + p.exitValue()));
```

## 12.8.3 进程句柄（Process Handles）

要获取关于程序启动的进程或机器上运行的任何其他进程的更多信息，请使用 `ProcessHandle` 接口。可以通过以下四种方式获取 `ProcessHandle`：

1. 给 `Process` 对象 `p`，`p.toHandle()` 返回其句柄。
2. 给 `long` 类型的操作系统进程 ID，`ProcessHandle.of(id)` 返回该进程的句柄。
3. `ProcessHandle.current()` 是当前进程的句柄。
4. `ProcessHandle.allProcesses()` 返回所有可见操作系统进程的 `Stream<ProcessHandle>`。

给定一个进程句柄，你可以获取其 PID、父进程、子进程和后代：

```java
long pid = handle.pid();

Optional<ProcessHandle> parent = handle.parent();

Stream<ProcessHandle> children = handle.children();

Stream<ProcessHandle> descendants = handle.descendants();
```

> ![Image](img/note.jpg) **注意：**
>
> `allProcesses`、`children` 和 `descendants` 返回的 `Stream<ProcessHandle>` 只是快照。在你处理它们时，某些进程可能已经终止，并且新新进程。

`info` 方法产生一个 `ProcessHandle.Info` 对象，其中包含获取进程信息的方法：

```java
Optional<String[]> arguments()

Optional<String> command()

Optional<String> commandLine()

Optional<Instant> startInstant()

Optional<Duration> totalCpuDuration()

Optional<String> user()
```

这些方法都返回 `Optional` 值，因为特定的操作系统可能无法报告这些信息。

对于监控或强制终止进程，`ProcessHandle` 具有与 `Process` 类相同的 `isAlive`、`supportsNormalTermination`、`destroy`、`destroyForcibly` 和 `onExit` 方法。不过，没有 `waitFor` 方法的等效方法。

### `ProcessBuilder.redirectError(ProcessBuilder.Redirect destination)` **7**

重定向进程的标准输入、输出或错误流，其中 `destination` 是以下之一：

- `Redirect.PIPE`—默认行为，通过 `Process` 对象访问
- `Redirect.INHERIT`—来自虚拟虚拟的流
- `Redirect.DISCARD`
- `Redirect.from(file)`
- `Redirect.to(file)`
- `Redirect.appendTo(file)`
- `Map<String,String> environment()`

产生一个用于设置进程环境变量的可变映射（map）。

- `Process start()`

启动进程并返回其 `Process` 对象。

- `static List<Process> startPipeline(List<ProcessBuilder> builders)` **9**

启动一个进程流水线，将每个进程的标准输出连接到上一个进程的标准输入。

### `java.lang.Process` **1.0**

- `abstract OutputStream getOutputStream()`

  获取一个用于向进程输入流写入数据的输出流。

- `abstract InputStream getInputStream()`
- `abstract InputStream getErrorStream()`

  获取一个用于读取进程输出流或错误流的输入流。

- `abstract int waitFor()`

  等待进程结束并返回退出值。

- `boolean waitFor(long timeout, TimeUnit unit)` **8**

  等待进程结束，但不超过给定的超时时间。如果进程已退出，则返回 `true`。

- `abstract int exitValue()`

  返回进程的退出值。按照惯，非零退出值表示错误。

- `boolean isAlive()` **8`

  检查此进程是否仍在运行。

- `abstract void destroy()`
- `Process destroyForcibly()` **8`

  终止此进程，可以是正常终止也可以是强制终止。

- `boolean supportsNormalTermination()` **9`

  检查此进程是否可以正常终止或必须强制销毁。

- `ProcessHandle toHandle()` **9`

  返回一个描述此进程的 `ProcessHandle`。

- `CompletableFuture<Process> onExit()` **9`

  返回一个在进程退出时执行的 `CompletableFuture`。

### `java.lang.ProcessHandle` **9**

- `static Optional<ProcessHandle> of(long pid)`
- `static Stream<ProcessHandle> allProcesses()`
- `static ProcessHandle current()`

  返回具有给定 PID 的进程句柄、所有进程的句柄或虚拟机的进程句柄。

- `Stream<ProcessHandle> children()`
- `Stream<ProcessHandle> descendants()`

  返回此进程子进程或后代进程的句柄。

- `long pid()`

  返回此进程的 PID。

- `ProcessHandle.Info info()`

  返回关于此进程的详细信息。

### `java.ProcessHandle.Info` **9**

- `Optional<String[]> arguments()`
- `Optional<String> command()`
- `Optional<String> commandLine()`
- `Optional<Instant> startInstant()`
- `Optional<Instant> totalCpuDuration()`
- `Optional<String> user()`

如果可用则返回提供的详细信息。

你现在已经到达了*Core Java*第一卷。本卷介绍了 Java 编程语言的基础以及大多数编程项目所需的标准库部分。希望你喜欢这段 Java 基础之旅，并在此过程中发现了有用信息。对于高级主题，例如 Java 平台模块系统、网络、高级用户界面和图形编程、安全以及国际化，请参阅第二卷。

## 附录 A

本附录列出了 Java 语言所有的关键字和类关键字的词。“受限关键字”是仅在模块声明中的关键字，在其他情况下是标识符。“受限标识符”是标识符，除非用于特定位置。例如，`var` 始终是一个标识符，除非它在预期类型的地方使用。`null`、`false` 和 `true` 不是关键字，而是字面量。

**表 A.1** Java 关键字

![Images](img/app01tab01.jpg)![Images](img/app01tab01a.jpg)![Images](img/app01tab01b.jpg)![Images](img/app01tab01c.jpg)![Images](img/app01tab01d.jpg)
