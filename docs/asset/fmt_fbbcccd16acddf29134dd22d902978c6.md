
# 图 5.9 计算用户输入的一组数字成绩的平均值，并使用 switch 语句确定每个成绩是否等同于 A、B、C、D 或 F，以增加相应的等级计数器。程序还显示获得每个成绩的学生数摘要。

与之前的版本类平均分程序一样，`LetterGrades`（图 5.9）的 `main` 方法声明了局部变量 `total`（第 9 行）和 `gradeCounter`（第 10 行），用于跟踪用户输入的成绩总和和输入的成绩数量。第 11–15 行为每个成绩类别声明了计数器变量。注意第 9–15 行中的变量已初始化为 0。

`main` 方法包含两个关键部分。第 26–56 行从用户控制的输入中读取任意数量的整数成绩，更新实例变量 `total` 和 `gradeCounter`，并为每个成绩增加相应的字母等级计数器。第 59–80 行输出一份包含所有输入成绩、成绩平均值以及获得每个字母等级的学生数的报告。让我们详细检查这些部分。

```java
// Fig.5.9: LetterGrades.Java
// LetterGrades 使用 switch 语句对字母等级计数。
import java.util.Scanner;

public class LetterGrades {
    public static void main(String[] args) {
    }
}
```

**图 5.9** LetterGrades 类使用 switch 语句对字母等级计数。（3 部分中的第一部分。）

## 第 5 章 控制语句：部分 2：逻辑运算符

图 5.9 | LetterGrades 类使用 switch 语句对字母等级计数。（3 部分中的第 2 部分。）

## 5.6 switch 多重选择语句

```java
// 如果至少了一个成绩

if (gradeCounter != 0)
{
    // 计算所有成绩的平均值
    double average = (double) total / gradeCounter;

    // 输出结果
    System.out.printf("Total of the %d grades entered is %d\n",
        gradeCounter, total);
    System.out.printf("Class average is %.2f\n", average);
    System.out.printf("Number of students who received each grade:\n%d\n%d\n%d\n%d\n%d\n",
        "A: " + account, // 显示 A 级
        "B: " + bcount, // 显示 B 级
        "C: " + ccount, // 显示 C 级
        "D: " + dcount, // 显示 D 级
        "F: " + fcount); // 显示 F 级
} // end if
else 如果没有输入成绩，则输出适当的消息
{
    // end classGrades
}
```

```java
// 循环直到用户输入结束标志
while (input.hasNext()) {
    int grade = input.nextInt(); // 读取成绩
    total += grade; // 将成绩加到 total
    gradeCounter++; // 增加成绩数量

    // 增加相应的字母等级计数器
    switch (grade / 10) {
        case 9: // 90 到 99 之间
            ++account;
            break; // 退出 switch
        case 8: // 80 到 89 之间
            ++bcount;
            break; // 退出 switch
        case 7: // 70 到 79 之间
            ++ccount;
            break; // 退出 switch
        case 6: // 60 到 69 之间
            ++dcount;
            break; // 退出 switch
        default: // 小于 60
            ++fcount;
            break; // 可选；退出 switch
    }
}

// 输出成绩报告
System.out.printf("%nGrade Report:\n");
```

## 第 5 章 控制语句：部分 2：逻辑运算符

用户输入的某个字符用于表示没有更多数据待输入。在第 15 章“文件、流与对象序列化”中，你将看到程序从文件中读取输入时如何使用文件结束符。

在 UNIX/Linux/Mac OS 系统上，通过在单独的一行上输入序列来输入文件结束：

```
<Ctrl>d
```

这意味着同时按下 Ctrl 键和 d 键。在 Windows 系统上，可以通过输入以下内容输入文件结束：

```
<Ctrl>z
```

[注意：在某些系统中，在输入文件结束键键序列后必须按 Enter 键。此外，当输入文件结束符时，Windows 通常会在屏幕上显示字符 ^Z，如图 5.9 所示。]

> **可移植性提示 5.1**
>
> 输入文件结束的按键组合取决于系统。

`while` 语句（第 26–56 行）获取输入。第 26 行的条件调用了 Scanner 的 `next` 方法来确定是否还有更多数据待输入。如果有更多数据，该方法返回布尔值；否则返回 `false`。返回的值随后被用 `while` 语句中条件的值。如果用户输入文件结束符，`next` 方法返回 `false`。

第 28 行获取用户输入的成绩值。第 29 行将成绩累加到 `total`。第 30 行将 `gradeCounter` 加1。这些变量用于计算成绩的平均分。第 33–55 行使用 `switch` 语句根据输入的数字成绩来增加相应的字母等级计数器值。

## 处理成绩

`while` 语句（第 33–55 行）决定递增哪个计数器。我们假设用户输入的是 0–100 范围内的有效成绩。90–100 范围内的成绩代表 A，80–89 代表 B，70–79 代表 C，60–69 代表 D，0–59 代表 F。`switch` 语句由一个包含一系列 `case` 标签的块以及一个可选的 `default` 分用例组成。在本例中，这些标签用于根据成绩确定递增哪个计数器。

当控制流到达 `switch` 时，程序评估关键字 `switch` 后面括号中的表达式 `(grade / 10)`。这是 `switch` 的控制表达式。程序在每个 `case` 标签处计算该表达式的值（必须评估为 `byte`、`char` 或 `int` 类型整数，或 `String`）。第 33 行的表达式执行整数除法，会截断结果的小数部分。然后，当我们除一个 0 到 100 之间的值时，结果始终是0 到 10 之间的值。我们在每个 `case` 标签中使用了这些值。例如，如果用户输入成绩 85，控制表达式的值为 8。`switch` 将 8 与每个 `case` 标签进行比较。如果匹配（第 40 行的 `case 8:`），程序执行该 case 的语句。对于整数 8，第 41 行增加了 `bCount`，这意味着 80 分段的成绩是 B。`break` 语句（第 42 行）导致程序继续执行 `switch` 之后的第一个语句——在本程序中，我们到达 `while` 循环的末尾，因此控制返回到第 26 行的循环继续条件，以确定循环是否继续执行。

## 5.6 switch 多重选择语句

我们 `switch` 中的 `case` 显式测试了值 10、9、8、7 和 6。注意第 35–36 行测试值 9 和 10 的 `case`（两者都代表成绩 A）。以这种方式连续列出 `case` 且之间没有语句，允许这些 `case` 执行同一组语句——当控制表达式评估为 9 或 10 时，将执行第 37–38 行的语句。`switch` 语句提供测试值范围的机制，因此需要测试的每个值必须位于单独的 `case` 中。每个 `case` 可以有多个语句。`switch` 语句与其他结构的区别在于它不需要为 `case` 中的多个语句使用大括号。

## 没有 break 的 case

如果没有 `break` 语句，`switch` 中发生匹配，`case` 的后续语句将执行，直到遇到 `break` 语句或 `switch` 结束。这通常被称为“穿透”（falling through）（这种功能非常适合编写简洁的程序，如练习 5.2 中的“圣诞之歌”）。

> **常见编程错误 5.7**
>
> 在 `switch` 中需要时忘记 `break` 语句是一个逻辑错误。

## default Case

如果控制表达式的值与任何 `case` 之间没有发生匹配，则执行 `default` 情况（第 52–54 行）。如果没有匹配且 `switch` 不包含 `default` 情况，程序将继续执行 `switch` 之后的第一个语句。

> **预防提示 5.7**
>
> 在 `switch` 语句中，确保测试控制表达式的所有可能值。

## 设计成绩报告

第 59–80 行根据成绩输出报告（如图 5.9 的输入窗口所示）。第 62 行判断用户是否输入了成绩——有助于我们避免除以零。如果是，第 65 行计算成绩的平均分。第 68–77 行输出所有成绩的总和、平均分以及获得每个成绩的人数。如果没有输入成绩，第 80 行输出适当的消息。图 10 的输出显示了一个成绩报告。

## switch 语句 UML 活动图

图 5.10 显示了通用 `switch` 语句的 UML 活动图。大多数 `switch` 语句在 `case` 中使用 `break` 在处理完 `case` 后终止 `switch` 语句。图 5.10 通过在活动图中包含 `break` 语句强调了这一点。该图明确了在 `case` 末尾的 `break` 语句控制立即退出 `switch`，因为执行将 continue到 `switch` 之后的语句。

图 5.10 | 带有 break 语句的多重选择活动图。

> **预防提示 5.8**
>
> 在 `switch` 语句中提供 `default` 情况。这让你关注异常情况。

> **良好编程实践 5.3**
>
> 虽然 `switch` 中的每个 `case` 和 `default` 情况可以按任意顺序出现，但请将 `default` 情况放在最后。

*关于 switch 中每个 case 的表达式*

使用 `switch` 语句时，记住每个 `case` 必须包含一个常量表达式——评估为常量整数的任何整数组合（例如 -7、0 或 7）或一个 `String`。整数常量就是一个整数值。此外，你可以使用字符常量——单引号内的特定字符，如 'A'、'7' 或 '$'——代表字符值和枚举常量（在 6.10 节引入；附录 B 显示了值）。`case` 中的表达式也可以是一个常量变量——其值在整个程序中不变。此类变量用 `final` 关键字声明（第 6 章讨论）。Java 有一种称为枚举类型，我们在第 6 章中介绍——枚举常量也可以用于 `case` 标签。

## 5.7 AutoPolicy 案例研究：switch 中的字符串

在第 10 章“面向对象编程：多态与接口”中，我们介绍了一种更优雅的实现 switch 逻辑的方法——我们使用多态技术创建比使用 switch 逻辑更清晰、更容易维护和扩展的程序。

## 5.7 AutoPolicy 案例研究：switch 中的字符串

字符串可以作为 `switch` 语句中的控制表达式，字符串字面量可以用于 `case` 标签。为了证明字符串可以作为 `switch` 语句中的控制表达式且字符串字面量可以用于 `case` 标签，我们实现了一个满足以下要求的程序：

> 你被一家服务于这些东北州的汽车公司聘佣——康涅狄格州、缅因州、马萨诸塞州、新罕布什州、新泽西州、纽约州、宾夕法尼亚州和佛蒙特州。公司希望你创建一个程序，识别其每份保单是否位于具有“无过错”汽车保险的州——马萨诸塞州、新泽西州、纽约州和宾夕法尼亚州。

带有要求的 Java 应用包含两个类——`AutoPolicy`（图 5.11）和 `AutoPolicyTest`（图 5.12）。

## AutoPolicy 类

`AutoPolicy` 类（图 5.11）代表汽车保险单。该类包含：

- `int` 实例变量 `accountNumber`（第 5 行）用于存储账号
- `String` 实例变量 `makeAndModel`（第 6 行）用于存储汽车品牌和型号（如“丰田凯瑞”）
- `String` 实例变量 `state`（第 7 行）用于存储代表保单所在州的两个字符缩写（例如，马萨诸塞州的 "MA"）
- 一个构造函数（第 10–15 行），用于初始化类变量
- 方法 `setAccountNumber` 和 `getAccountNumber`（第 18–27 行），用于设置获取 `AutoPolicy` 的 `accountNumber` 变量
- 方法 `setMakeModel` 和 `getMakeAndModel`（第 30–39 行），用于设置获取 `AutoPolicy` 的 `makeAndModel` 实例变量
- 方法 `setState` 和 `getState`（第 42–51 行），用于设置获取 `AutoPolicy` 的 `state` 变量
- 方法 `isNoFaultState`（第 54–70 行），返回一个布尔值，指示保单是否位于无过错汽车保险的州；注意返回布尔值的方法的命名习惯，以 "is" 开头而不是 "get"（这种方法通常被称为谓词方法）。

在 `isNoFaultState` 方法中，`switch` 语句的控制表达式（第 59 行）由 `AutoPolicy` 的 `getState` 方法返回。`switch` 语句将控制表达式与 `case` 标签（第 61 行）进行比较，以确定保单是否位于马萨诸塞州、新泽西州、纽约州或宾夕法尼亚州（无过错州）。

# 172 第 5 章 控制语句：部分 2：逻辑运算符

如果匹配，则第 62 行将局部变量 `noFaultState` 设置为 switch 语句终止；否则，默认情况将 `noFaultState` 设置为 `false`（第 65 行）。然后方法 `isNoFault` 返回局部变量 `noFaultState.value`。

为了简单起见，我们没有在构造函数或设置方法中验证 `AutoPolicy` 的数据，并假设缩写始终为大写字母。此外，真实的 `AutoPolicy` 类可能会包含许多其他实例变量和方法，用于处理数据，如账户持有人的姓名、地址等。在练习 5.30 中，你将被要求使用 5.9 节中将学的技术通过验证其州缩写来增强 `AutoPolicy` 类。

```java
// 图 5.11: AutoPolicy.java
// 表示汽车保险单的类。
public class AutoPolicy {
    private int accountNumber; // 险单账号
    private String makeModel; // 保险适用的汽车车型
    private String state; // 两个字母的州缩写

    // 构造函数
    public AutoPolicy(int accountNumber, String makeModel, String state) {
        this.accountNumber = accountNumber;
        this.makeModel = makeModel;
        this.state = state;
    }

    // 设置账号
    public void setAccountNumber(int accountNumber) {
        this.accountNumber = accountNumber;
    }

    // 返回账号
    public int getAccountNumber() {
        return accountNumber;
    }

    // 设置车型
    public void setMakeModel(String makeModel) {
        this.makeModel = makeModel;
    }

    // 返回车型
    public String getMakeModel() {
        return makeModel;
    }
}
```

**图 5.11** | 表示汽车保险单的类。（2 部分中的第 I 部分。）

## 5.7 AutoPolicy 类案例研究：switch 语句中的字符串

```java
// 设置州
public void setState(String state)
{
    this.state = state;
}

// 返回州
public String getState()
{
    return state;
}

// 谓词方法返回该州是否有无责任险
public boolean isNoFaultState(){
    boolean noFaultState;
    // 确定该州是否有无责任汽车险
    switch (getState()) { // 获取 AutoPolicy 对象的州缩写
        case "MA": case "NJ": case "NY": case "PA":
            noFaultState = true;
            break;
        default:
            noFaultState = false;
            break;
    }
    return noFaultState;
}// 结束类 AutoPolicy
```

图 5.11 | 表示汽车保险单的类。（2 部分中的第 2 部分。）
