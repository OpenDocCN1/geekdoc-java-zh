
# Java 实践指南：Level 1；1000+ 习题解析

## 引言

欢迎阅读《练习你的 Java 第1级》！此书旨在通过练习，提高读者在 Java 编程方面的知识、技能和信心。书中提供了超过 1000 道经过精心设计的练习及其答案，以帮助实现这一目标。

在本书纸质版的封底上，我们展示了旨在帮助你实现的四个重要目标。我们希望帮助你快速实现以下目标：

- (1) 对该语言的基础获得坚实的理解
- (2) 对书中介绍的知识保持高记忆力，从而提高你的技能
- (4) 在此水平上 Java 编程以及追求该语言更高水平的信心

本书通过两种方式帮助实现这些目标；首先通过合理安排其中的章节和内容，其次通过我们独特的题目结构。我们通过以下方式进行说明：

### 通过合理的章节与题目顺序实现理解、记忆、技能和信心

关于飞机，我有这样一种说法：“尽管驾驶舱内有大量的按钮，但只要你按照正确的顺序操作，飞机是非常容易驾驶的”。按照正确的顺序进行学习和理解，你就能很容易记住哪个按钮是什么以及它的作用是什么。同样的概念对于真正的 Java 也是如此。因此，在书中，语言子主题的呈现是按照学习这一特定语言的适当安排的，有助于记忆。随着读者一章读到另一章，他们的 Java 知识和技能将以一种方法的方式构建起来。

### 通过的题目结构实现理解、记忆、技能和信心

曾提到，本卷的目标之一是帮助理解并帮助记忆所学材料。在互联网普及之前，开发者必须在脑中保留高水平的知识（而不仅仅是事实），仅在需要时参考文本。然而，现在，由于对现有语言的学习和练习不当，开发者可能会花费大量时间在网上寻找问题的“点点解决方案”，而不是花时间正确地学习语言的基础。

本书如何帮助理解？它如何帮助记忆？它如何帮助学习？它通过以下练习结构来促进理解、记忆和学习：

> 读者在每个练习中通常只被呈现一个概念/方法

就像我们学习字母表时，我们是按字母学习的。因此，在本卷中，相应数量的编程练习要求使用单个 Java 方法作为练习答案的关键。这让读者能够专注于这一个方法，有助于理解和记忆。

当然，书中也提供了包含多个概念的题目。

### 读者在编程题中通常会获得直接的提示

这是书中练习的一项非常重要的特征。我们解释一下原因。

你看，如果一个练习是关于一个读者不熟悉或仅边缘熟悉的话题，读者将搜索（可能是在互联网上）可能的解决方案。这浪费了时间。

事实上，对于更复杂的话题，读者可能会花费大量时间阅读潜在的解决方案，以至于当他们找到解决方案时，已经忘记了是如何到达那里的，并且太疲劳而无法真正记住它！最好像本卷中那样，提供“提示”，指定问题解决方案中出现的精确 Java 方法，以便读者可以将时间研究与解决当前问题相关的方法/特征并实现解决方案。这种关注也有助于记忆。

### 反向题目结构

有些话题是相当深奥的。我们不是要求读者提供问题的答案，而是将完成的代码作为题目，并要求读者分析给出的解决方案。这些练习的意图显然是为了教读者涉及的相关话题。这再次节省了时间并让用户专注于此。

读者会发现这种题目结构最有帮助。敏锐的读者会观察到这实际上是在教授这些话题。

## 本书的使用场景

预计这本书将满足初级到中级 Java 开发者的需求。本书适用于以下场景：

- 对于没有 Java 经验的个人，本书旨在作为一份参考文本。
- 对于只需刷新 Java 知识的程序员，完成练习可能足够。
- 对于课堂教师，他们会发现这本书是确保学生精通 Java 的有力工具。

## 目标读者群

本书的主要受众是初级 Java 程序员。

## 工具集

书中的代码解决方案是用 `Java 8` 和 `Eclipse IDE 4.4` 版本实现的。书中没有针对特定 IDE 的练习。鼓励读者使用任何选择的 IDE。

## 目录结构

本书按章节结构，每个章节涵盖一个主要主题（其部分）。话题之间的重叠将在相应的章节中涵盖。

## 图例/结构

练习按顺序编号。题目统一位于书籍的左侧。每个练习的答案出现在练习旁边或正下方。

题目列中出现的 `$M$` 表示必须手动执行的操作；例如将 USB 盘/驱动器插入计算机。

题目列中跟随数字的 `$E$` 表示给读者解决的额外练习。它们出现的地方在章节的末尾。

## 如何使用本书

对 Java 比较陌生的个人建议按顺序阅读书中的章节。课堂教师或个人可以按照最适合其需求的顺序阅读各个章节。

## 使用本书需要什么

为了实现书中的所有练习，你需要下载并安装 `Java 8 JDK` 以及你选择的任何 Java IDE。用户还需要访问 Oracle 提供的免费官方 Java 文档。书的代码可以从出版商网站下载。

## 关于作者

Ayodle "Ayo" Agboola 拥有加拿大滑铁卢大学的电气工程学位。在过去的 30 年里，他有幸一直从事编程，首先是个人兴趣，然后是职业发展。作为专业人士，他曾在全球范围内担任过多种角色，包括软件开发、项目管理和培训，实施各种规模的软件，主要是为电信服务提供商。

### 致谢

Oluwa lẹ́ ẹyí; ó si jé ohun iyanu lọjú wa!

感谢所有通过分享知识对此做出贡献的人。

## 目录

- 第 1 章 入门
- 第 2 章 控制台处理 I：基础输出
- 第 3 章 数字处理 I – 数值基本类型
- 第 4 章 布尔运算 - 布尔基本类型
- 第 5 章 字符串：基础处理
- 第 6 章 条件处理
- 第 7 章 数组
- 第 8 章 迭代/循环
- 第 9 章 数字处理 II – 数字包装类
- 第 10 章 布尔包装类
- 第 11 章 枚举 I
- 第 12 章 数字处理 III – BigInteger & BigDecimal
- 第 13 章 数字处理 IV – strictfp & StrictMath
- 第 14 章 数字处理 V – 无符号整数
- 第 15 章 日期/时间处理 – 基础
- 第 16 章 异常
- 第 17 章 控制台处理 II：控制台输入
- 第 18 章 控制台处理 III：命令行输入
- 第 19 章 char 基本类型与 Character 包装类
- 第 20 章 随机数
- 第 21 章 StringBuffer & StringBuilder
- 第 22 章 类 I
- 第 23 章 对象引用与基本类型变量：更深入的理解
- 第 24 章 类 II：嵌套类、本地类、匿名类
- 第 25 章 集合 I：带泛型的集合
- 第 26 章 接口
- 第 27 章 集合 II：使用接口的集合以及迭代器
- 第 28 章 属性、计算机环境与计算机信息
- 第 29 章 文件系统 I：使用 NIO/NIO.2 的路径、目录和文件处理
- 第 30 章 文件系统 II：文件输入与输出
- 第 31 章 枚举 II
- 第 32 章 使用 Swing 的图形用户界面
- 第 33 章 Applets – 简要回顾

# 练习你的 Java 水平 1

## 附录 A. 类、对象与方法：简介

## 附录 B. 项目

## 索引

## 第 1 章 入门

本章的意图主要是对读者可能已经完全熟悉的入门主题进行快速概述；这些主题涉及 Java 应用程序的基本结构，以及大量的基础 Java 编程主题和概念。如前所述，本章中的练习将以快速概述的形式呈现。

> **注意：** 如果读者需要对类的概念进行介绍，请先阅读附录 A。

首先，我们在下方展示了一个示例程序；我们将在本章的一个练习中引用该程序。

```java
package practiceYourJava;
import java.util.*;
import java.time.*;
import java.nio.file.*;
import java.nio.file.attribute.*;
```

```java
public class PracticeYourJava {

    public static void main(String[] args) {
    }
}
```

1. 针对以上代码块，`package practiceYourJava;` 语句是什么意思？这意味着我们正在编写代码放在一个命名为 `practiceYourJava` 的“包”（package）中（包的概念将在下一个练习中解释）。

2. 针对上述代码块，简要解释 `import java.util.*; import java.time.*; import java.nio.*; import java.nio.file.attribute.*;` 语句的含义。这些语句中的每一个都表示我们的意图导入一个包；通过“import”，我们是在告诉编译器，我们打算在程序中使用所指定包的部分内容。我们的最终程序将由我们编写的内容加上我们在程序中所使用的指定包的特定节点组成。

3. Java 中的“包”（package）是指什么？

“包”是 Java 类型的分组（这里指的是某种意义上的类，包括枚举类、异常类和接口）；我们将在后面的章节中查看这些每一个类型。包的开发者决定将他们想要放入的任何类型分组到给定的包中。一个例子是 `java.nio` 包，它包含了与文件 I/O 某些方面的 Java 类。

那么，为什么我们必须导入包呢？编译器需要知道 (1) 哪些包是可用的 (2) 使用了哪些哪些类。这允许编译器在编译过程中解析引用。

`*` 是什么意思？

`*` 符号是一个通配符，代表特定包中的所有类。例如，`import java.util.*;` 告诉编译器从 `java.util` 包中导入所有类。

# 练习你的 Java 水平 1

在 Java 中，类是创建对象的蓝图。它定义了该类的对象将具有的数据（字段）和行为（方法）。类的实例被称为对象。

## 第 1 章：入门

> **注意事项：** 没有定义方法的类不能直接运行；它们只能作为组件被其他类使用。

9. 如果你的 `.java` 文件不包含 `main` 方法，会有什么影响？

> *提示：参见前面的练习题*

在相关的 `.java` 文件中放入一个 `main` 方法，意味着我们不希望我们的类是“双重可运行”的。这非常常见，大多数 `.java` 文件仅包含其他程序作为组件使用的类型定义。

10. 针对一个我们希望被 JVM 调用/调用的给定方法，列出 JVM 可以拥有的所有可能的修饰符声明。

符合 `main` 方法方法标准的唯一可能的修饰符声明如下：

1. `public static void main(String[] args)`

访问修饰符提供了它的可见性，因此它可以被 JVM 调用。`main` 方法不能直接向操作系统返回值（还有其他方法，如 `System.exit`）。`main` 方法必须始终准备好接收一个 `String` 类型的数组，如输入所示。此外，`main` 总是带有 `static` 修饰符（我们将在第 22 章“类 I”中讨论此修饰符）。

11. 除了 `static` 修饰符外，`main` 方法还可以使用其他什么类型的修饰符？

不能。`main` 方法始终是一个静态（static）方法。

修饰符（如 `static`）将在第 22 章“类 I”中介绍。

12. 在下面的代码段中，我们使用了 `return` 关键字。这个关键字的作用是什么？

```java
public static void main(String[] args) {
    return;
}
```

`return` 关键字在执行时，会导致其被调用的方法立即终止，并将控制权返回给调用方法。在 `main` 方法的情况下，它会退出程序并将控制权返回给操作系统。总而言之，我们可以说 `return` 意味着“退出你正在运行的方法，并将控制权返回给调用该方法的人”。

13. 对比此程序中 `return` 关键字的使用与上一个练习中的用法。

```java
public int doSomething() {
    return(5);
}
```

本练习和上一个练习中的语句具有相同的基本效果，它们都将控制权返回给调用了该 `return` 语句的方法。然而，在这种情况下，`return` 还向它的调用方法“返回”了一个所需的值（在本示例中，它返回了值 5）。需要注意的一个非常重要的点是：`return` 语句返回任何内容的能力与 `return` 语句出现的方法定义中指定的返回类型相关。这个特定的示例说明我们正在返回一个 `int` 类型的值，而该声明允许我们返回 `int` 值 `5`。

14. 解释为什么以下代码是无效的：

```java
public void main(String[] args) {
    return("finished");
}
```



它是无效的，因为 `main` 方法不能直接返回任何内容；它的返回类型应该是 `void`。

当 `//` 序列出现在程序的一某行时表示什么？

双正斜杠表示同一行中之后的任何文本都是注释，因此编译器应该忽略它。

16. 下面代码片段的输出是什么？

```java
/*
System.out.println("Hello");
System.out.println();
*/
```

什么都不会输出。

原因是因为整个类片段块被注释了，正如起始注释符 `/*` 和结束注释符 `*/` 所示。

问题中的界定代码是多行注释的示例。

# Java 练习 Level 1

## 实例成员与静态成员简览

后续问题的目的是让读者复习类的实例成员和静态成员之间的区别。这是必要的，因为在进入详细讨论类的章节之前，我们会遇到许多这类内容。

- 17. 我们有以下类定义：

```java
class Man {
    public static String gender="male";
    public String firstName;
    public String lastName;
}
```

指出哪些是类的静态成员，哪些是实例成员。

该类唯一的静态成员是 `String gender`。这通过定义中的 `static` 修饰符可以辨别。

字段 `firstName` 和 `lastName` 是类的实例成员。

- 18. 在 `Man` 类的方法中实例化（创建）一个名为 `man01` 的对象。之后，将对象 `man01` 的第一个字段设置为 "Adam"，然后打印 `man01.firstName`。

```java
class Man {
    public static String gender="male";
    public String firstName;
    public String lastName;
    public static void main(String[] args) {
        Man man01 = new Man(); // 我们现在创建了该类的对象 man01
        man01.firstName = "Adam"; // firstName 是一个"public"字段，所以我们可以在任何方法中设置它
        System.out.println(man01.firstName);
    }
}
```

- 19. 类成员和实例成员之间的区别是什么？

静态成员是“属于”类的，而实例成员“属于”类的具体实例。

静态成员是相对于类调用的，而实例成员是相对于实例化对象调用的。我们可以通过以下使用之前定义的类 `Man` 的 4 行代码看到这一点：

| 代码 | 注释 |
|---|---|
| man01 = new Man(); | 实例化一个名为 man01 的 Man 类对象 |
| man01.firstName = "John"; | 观察到实例字段相对于实例 |
| man01.lastName = "Doe"; | 观察到实例字段相对于实例 |
| System.out.println(Man.gender); | 观察类访问静态成员 |

## 关于方法的一些要点

后续练习涉及方法的概念。

- 20. 在 Java 中，“签名（signature）”术语是什么意思？

Java 中的方法签名意味着方法名和参数类型。例如，对于一个名为 `addIntegers` 添加两个整数的公共方法，其签名是 `addIntegers(int, int)`。

- 21. “方法声明（method declaration）”术语是什么意思？

方法声明意味着：方法名、访问范围（public、private 等）、输入类型。例如，对于一个名为 `addIntegers` 添加两个整数并返回 `long` 类型的公共方法，其声明是 `long addIntegers(int, int)`。

- 22. 使用返回语句的方法可以返回什么类型？

可以返回任何类型，自定义类型或内置类型（`main` 方法是一个特殊情况，无法返回任何内容）。

- 23. “方法重载（method overloading）”术语是什么意思？

这意味着对于给定的方法，可以存在不同输入类型的多个版本，并由 Java 编译器调用正确的一个（编译器通过查看传递给它的参数类型来确定）。例如，如果我有具有相同名称但不同输入参数的方法：

`addIntegers(int, int);`

`addIntegers(int, int, int);`

那么如果另一个方法传递三个整数值给 `addIntegers`；编译器将调用第二个版本；如果我只传递两个整数给 `addIntegers`;编译器知道上面的第一个版本。

然而，方法不能仅通过返回类型进行重载，例如以下组合不能在同一个类中：

`long addIntegers(int, int);`

`addIntegers(int, int);`

- 24. 在名为 `PracticeJava` 的类创建一个静态方法 `greet`，它不返回任何内容也不接受任何参数。它只需打印语句 "Hello, how are you?" 并返回调用者。在 `main` 方法中调用此方法。

```java
public class Practicejava {
    static void greet() {
        System.out.println("Hello, how are you?");
    }
    public static void main(String[] args) {
        greet(); //调用方法 hello
    }
}
```

- 25. 写一个返回类型为 `int` 的静态方法 `addIntegers`，用于加两个整数并返回得到的整数值。

为了测试该方法，向 `addIntegers` 传递两个任意整数值并让 `main` 打印结果。

```java
public class PracticeJava {
    static int addIntegers(int a, int b) {
        return(a + b);
    }
    public static void main(String[] args) {
        int result = addIntegers(5, 2);
        System.out.println(result);
    }
}
```

# 练习你的 Java 1 级

## 可变长度参数

注意：此主题比第一章更高级，将其放在此处是为了保持一致性。读者可以自由地简单读过此主题，并在后续章节中需要该功能时再回来查看。

26. 什么是可变长度参数（varargs）的概念？

这是一种机制，我们可以向设计为接收可变长度参数的方法传递给定类型的任意数量参数。例如，我们可以编写一个方法，用于计算并返回其参数列表中发送给它的任意数量整数之和；即，任何调用该方法的地方都可以向其传递任意数量的整数，并使用循环将它们相加。

接收可变长度参数的变量必须是方法声明中的最后一个参数。此外，在一个方法声明中只能有一个接收可变长度参数的变量，且它必须是方法声明中的最后一个。

需要注意的是，出于通用目的，接收可变长度参数的变量的行为类似于数组。

27. 编写一个方法，可以加传递给它的任意数量整数，并将结果作为 `long` 返回。

在 `main` 方法中调用此方法，并使用以下数据进行测试：

- 1. 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
- 2. 55, 76, 88, 13
- 3. 3, 7
- 4. 一个包含值 1, 5, 15, 19 的整数数组

```java
public class PracticeYourJava {
    public long addIntegers(int... intArray) {
        if (intArray.length == 0) return 0;
        long total = 0;
        for (int i = 0; i < intArray.length; i++) {
            total += intArray[i];
        }
        return total;
    }

    public static void main(String[] args) {
        long result1 = addIntegers(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
        long result2 = addIntegers(55, 76, 88, 13);
        long result3 = addIntegers(3, 7);

        int[] intArray1 = { 1, 5, 15, 19 };
        long result4 = addIntegers(intArray1);
    }
}
```

注意：在进入“类”章节之前，我们创建任何方法都将像 `main` 方法一样是静态方法，即不绑定到特定对象，而是绑定到类上的方法（非静态方法将在稍后直接处理类时处理）。

由于方法和类之间存在相互关系，方法的概念在第 22 章“类”中将得到进一步的增强和完善。

# 第 2 章：控制台处理 I：基础输出

程序的一个重要部分是向用户展示输出的能力，这是用户与程序交互的界面。这可以是到控制台的文本输出。在本章中，将提供一些练习，让读者练习并磨练基础和格式化控制台输出的技能，特别是 `System.out.printf`、`System.out.println` 和 `System.out.print` 方法，以及在所示有关数据类型输出的练习中使用字符串、整数和浮点数变量。

## 使用 `System.out.printf` 输出

| # | 任务 |
|---|---|
| 1 | 预测程序的输出。并解释代码。 |
| | ```java |
| | public class FormattingExercises{ |
| |     public static void main(String[] args) { |
| |         System.out.println("Hello!"); |
| |     } |
| | } |
| | ``` |
| | 输出: Hello! |
| | **解释：** 我们使用了 `System.out.println` 方法向控制台输出 "Hello"。我们只需要将双引号括起来的字符串传递给打印方法即可。 |
| 2 | 预测程序的输出。并解释代码。 |
| | ```java |
| | public class FormattingExercises{ |
| |     public static void main(String[] args) { |
| |         String var01 = "Hello"; |
| |         System.out.printf("%s", var01); |
| |     } |
| | } |
| | ``` |
| | 输出: Hello! |
| | **解释：** 我们使用了 `System.out.printf` 方法输出类型为 `String` 的 `var01` 内容。查看传递给 `printf` 方法的参数，第一个参数是双引号的字符串 "%s"，第二个参数是变量名，在此情况下是 `var01`。第一个参数和后续参数之间的关系如下：调用 `printf` 时的第一个参数可以包含我们想要输出的任何文本，带有“格式字符串”，例如 %s，它代表我们作为参数传递给 `printf` 的 `String` 变量名的值。在这个练习中，我们在第一个参数中有一个格式字符串，并将它所代表的变量名传递给 `printf`。第一个参数中格式字符串的数量必须与作为参数传递的等数量变量匹配... |
| 3 | 预测程序的输出。并解释代码。 |
| | ```java |
| | public static void main(String[] args) { |
| |     String var01 = "Hello"; |
| |     String var02 = "How are you"; |
| |     System.out.printf("My friend! %s %s", var01, var02); |
| | } |
| | ``` |
| | 输出: My friend! Hello! How are you? |
| | **解释：** 我们使用了 `System.out.printf` 方法输出 `var01` 内容（注：这里输出了两个变量）。查看传递给 `printf` 方法的参数，第一个参数是双引号的字符串 "%s"，第二个参数是变量名，在此情况下是 `var01`。第一个参数和后续参数之间的关系如下：调用 `printf` 时的第一个参数可以包含我们想要输出的任何文本，带有“格式字符串”，例如 %s，它代表我们作为参数传递给 `printf` 的 `String` 变量名的值。在这个练习中，我们在第一个参数中有一个格式字符串，并将它所代表的变量名传递给 `printf`。第一个参数中格式字符串的数量必须与作为参数传递的等数量变量匹配... |



# 练习题

## 2. 预测程序的输出。并解释代码。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String var01 = "Hello";
        System.out.printf("%s", var01);
    }
}
```

输出: Hello!

**解释：** 我们使用了 `System.out.printf` 方法输出类型为 `String` 的 `var01` 内容。查看传递给 `printf` 方法的参数，第一个参数是双引号的字符串 `"%s"`，第二个参数是变量名，在此情况下是 `var01`。第一个参数和后续参数之间的关系如下：调用 `printf` 时的第一个参数可以包含我们想要输出的任何文本，带有“格式字符串”，例如 `%s`，它代表我们作为参数传递给 `printf` 的 `String` 变量名的值。在这个练习中，我们在第一个参数中有一个格式字符串，并将它所代表的变量名传递给 `printf`。第一个参数中格式字符串的数量必须与作为参数传递的等数量变量匹配...

## 3. 预测程序的输出。并解释代码。

```java
public static void main(String[] args) {
    String var01 = "Hello";
    String var02 = "How are you";
    System.out.printf("My friend! %s %s", var01, var02);
}
```

输出: My friend! Hello! How are you?

**解释：** 我们使用了 `System.out.printf` 方法输出 `var01` 内容（注：这里输出了两个变量）。

## 4. 预测程序的输出。并解释代码。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String var01 = "Hello";
        System.out.printf("%s %s", var01);
    }
}
```

输出: Hello! Hello!

**解释：** 这和上一个练习相同，仅在此情况下我们选择了使用同一个变量。

## 5. 预测程序的输出。并解释代码。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String var01 = "Hello";
        String var02 = "How are you";
        System.out.printf("%s\n%s", var01, var02);
    }
}
```

输出:
```
Hello!
How are you?
```

**解释：** 我们看到输出分两行。这是由于我们在两个占位符之间放置了格式参数 `\n`。`\n` 相当于“在这里换行”。这是我们在输出中看到的效果。

## 6. 预测程序的输出。并解释代码。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String var01 = "Hello";
        String var02 = "How are you";
        System.out.printf("%s\t%s", var01, var02);
    }
}
```

输出:
```
Hello!    How are you?
```

**解释：** 我们看到在两个使用的字符串之间有一个制表符。这是由于我们在两个占位符之间放置了格式参数 `\t`。`\t` 意味着“在这里放置制表符”。

## 7. 编写一个程序，使用两个字符串变量将它们在同一行打印到控制台，中间留一个空格。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String firstName = "John";
        String lastName = "Doe";
        System.out.printf("%s %s", firstName, lastName);
    }
}
```

## 8. 预测程序的输出。并解释代码。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        int var01 = 22;
        System.out.printf("%d", var01);
    }
}
```

输出: 22

**解释：** 我们在这里被引入了一个新的格式参数 `%d`。参数 `%d` 用于整数。

---

# 第2章：控制台处理 I

```java
public static void main(String[] args) {
    int var01 = 2;
    System.out.printf("%d", var01);
}
```

整数值。在所有其他方面，该功能方法的描述与之前的练习相同。

输出：2.550000

解释：我们在这里看到了格式化参数，`%f` 用于格式化浮点数值。在所有其他方面，该功能方法的描述与之前的练习相同。注意输出被写写保留了 6 位小数。这是 `%f` 格式化参数的默认输出格式。我们将在稍后的章节中学习如何修改输出的精度。

## 预测输出并解释代码。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        double var01 = 2.55;
        System.out.printf("%f", var01);
    }
}
```

### 9. 预测并解释此程序的输出。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        double var02 = 1.23456789;
        System.out.printf("%f", var02);
    }
}
```

### 10.

输出：1.234568

解释：我们确实输入了一个带有 9 位小数的数字，如之前所述，`printf` 方法默认只打印到 6 位小数，必要时会对最后一位进行四舍五入。在后面的章节，我们将学习如何修改输出的精度。

---

## 使用 System.out.println & System.out.printf 输出

### 11. 编写程序分别使用 `System.out.print` 和 `System.out.println` 向控制台输出 "Hello World" 并紧跟一个换行符。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.print("Hello World\n");
    }
}
```

> **注意：** 你发现 `System.out.println` 会自动向输出添加一个行终止符。如果你选择使用 `print`，则必须向输出的数据中添加换行符 `'\n'` 才能获得与 `println` 相同的输出。

### 12. 编写一个程序，使用 `System.out.println` 向控制台输出包含双引号的文本 "Hello World"；使用 `\` 转义序列。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("\\Hello World\\n");
    }
}
```

> **注意：** 参见每个实例中使用 `\` 对双引号的转义。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("\\Hello World\\n");
    }
}
```

### 13. 包含 "n" 的精确短语 "Hello World,\n"。

#### 使用 `System.out.println` 从变量输出输出

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String firstName = "John";
        String lastName = "Doe";
        System.out.println(firstName + " " + lastName);
    }
}
```

编写一个程序，使用 `println` 语句将这些 String 变量在同一行输出到控制台，中间加一个空格。

---

# 练习你的 Java 1 级

| 题目 | 代码 |
| :--- | :--- |
| 15. 我定义了两个 String 变量：`String firstName = "John"; lastName = "Doe";` 将这些字符串拼接，中间加一个空格，合并到一个名为 `fullName` 的单个 String 变量中，并将拼接后的字符串输出到控制台。 | ```java<br>public class FormattingExercises {<br>    public static void main(String[] args) {<br>        String firstName = "John";<br>        String lastName = "Doe";<br>        String fullName = firstName + " " + lastName;<br>        System.out.println(fullName);<br>    }<br>}<br>``` |

| 练习 | 说明 |
| :--- | :--- |
| E1 | 读者应该学习 `DecimalFormat` 类，以查看数值格式化规则如何应用于 `System.out.println` 和 `System.out.println`。 |

---

# 第3章：数字处理 I – 原始数值类型

本章对 Java 中的数字处理主题进行了广泛涵盖。你对 Java 中数值类型及其操作的知识将通过本章提供的广泛系列练习得到练习和增强。

本章提供练习的关键主题包括：原始类型的知识、数值类型的恰当选择、使用内置数值运算符以及 `Math` 类方法的计算练习。

除了上述主题外，还包括关于包装类中数值常量的使用、溢出条件、`Exact` 方法、无限大处理、十六进制数、数制转换、逻辑和位运算、递增、递减以及简写数值运算符。一组关于原始数值类型格式化的健壮练习。

Java 中数字处理的主题非常广泛，因此不仅限于本章的主题；这是书中关于 Java 数字处理主题的五个个练习中的第一个。

| 题号 | 内容 |
| :--- | :--- |
| | 解释 Java 中原始数值类型（numerical primitives）的概念。 |
| 1. | 描述 Java 中原始数值的一种方法是：原始数值是在运行 Java 的 CPU 中原生表示和处理的数字类型。今天世界上大多数 CPU 都能原生表示并处理 `byte`、`short`、`int`、`float` 和 `double` 类型。此外 |
| 2. | 列出原始类型的名称：`byte`、`short`、`int`、`float` 和 `double`。 |
| 3. | 解释 Java 中原始数值类型的概念。 |
| 4. | 列出原始类型的名称：`byte`、`short`、`int`、`float` 和 `double`。 |
| 5. | `int` 支持的最小值是多少？ |
| 6. | `int` 支持的最大值是多少？ |
| 7. | `int` 使用了多少位？ |
| 8. | 预测并解释此程序的输出。 |

输出：1.234568

解释：我们确实输入了一个带有 9 位小数的数字，如之前所述，`printf` 方法默认只打印到 6 位小数，必要时会对最后一位进行四舍五入。在后面的章节，我们将学习如何修改输出的精度。

---

## 使用 System.out.println & System.out.printf 输出

### 11. 编写程序分别使用 `System.out.print` 和 `System.out.println` 向控制台输出 "Hello World" 并紧跟一个换行符。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.print("Hello World\n");
    }
}
```

> **注意：** 你发现 `System.out.println` 会自动向输出添加一个行终止符。如果你选择使用 `print`，则必须向输出的数据中添加换行符 `'\n'` 才能获得与 `println` 相同的输出。

### 12. 编写一个程序，使用 `System.out.println` 向控制台输出包含双引号的文本 "Hello World"；使用 `\` 转义序列。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("\\Hello World\\n");
    }
}
```

> **注意：** 参见每个实例中使用 `\` 对双引号的转义。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("\\Hello World\\n");
    }
}
```

### 13. 包含 "n" 的精确短语 "Hello World,\n"。

#### 使用 `System.out.println` 从变量输出输出

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String firstName = "John";
        String lastName = "Doe";
        System.out.println(firstName + " " + lastName);
    }
}
```

编写一个程序，使用 `println` 语句将这些 String 变量在同一行输出到控制台，中间加一个空格。

---

# 练习你的 Java 1 级

| 题目 | 代码 |
| :--- | :--- |
| 15. 我定义了两个 String 变量：`String firstName = "John"; lastName = "Doe";` 将这些字符串拼接，中间加一个空格，合并到一个名为 `fullName` 的单个 String 变量中，并将拼接后的字符串输出到控制台。 | ```java<br>public class FormattingExercises {<br>    public static void main(String[] args) {<br>        String firstName = "John";<br>        String lastName = "Doe";<br>        String fullName = firstName + " " + lastName;<br>        System.out.println(fullName);<br>    }<br>}<br>``` |

| 练习 | 说明 |
| :--- | :--- |
| E1 | 读者应该学习 `DecimalFormat` 类，以查看数值格式化规则如何应用于 `System.out.println` 和 `System.out.println`。 |

---

# 第3章：数字处理 I – 原始数值类型

本章对 Java 中的数字处理主题进行了广泛涵盖。你对 Java 中数值类型及其操作的知识将通过本章提供的广泛系列练习得到练习和增强。

本章提供练习的关键主题包括：原始类型的知识、数值类型的恰当选择、使用内置数值运算符以及 `Math` 类方法的计算练习。

除了上述主题外，还包括关于包装类中数值常量的使用、溢出条件、`Exact` 方法、无限大处理、十六进制数、数制转换、逻辑和位运算、递增、递减以及简写数值运算符。一组关于原始数值类型格式化的健壮练习。

Java 中数字处理的主题非常广泛，因此不仅限于本章的主题；这是书中关于 Java 数字处理主题的五个个练习中的第一个。

| 题号 | 内容 |
| :--- | :--- |
| | 解释 Java 中原始数值类型（numerical primitives）的概念。 |
| 1. | 描述 Java 中原始数值的一种方法是：原始数值是在运行 Java 的 CPU 中原生表示和处理的数字类型。今天世界上大多数 CPU 都能原生表示并处理 `byte`、`short`、`int`、`float` 和 `double` 类型。此外 |
| 2. | 列出原始类型的名称：`byte`、`short`、`int`、`float` 和 `double`。 |
| 3. | 解释 Java 中原始数值类型的概念。 |
| 4. | 列出原始类型的名称：`byte`、`short`、`int`、`float` 和 `double`。 |
| 5. | `int` 支持的最小值是多少？ |
| 6. | `int` 支持的最大值是多少？ |
| 7. | `int` 使用了多少位？ |
| 8. | 预测并解释此程序的输出。 |



# Java 原始数值类型练习

## 1. 描述 Java 中原始数值的一种方法
原始数值是在运行 Java 的 CPU 中原生表示和处理的数字类型。今天世界上大多数 CPU 都能原生表示并处理 `byte`、`short`、`int`、`float` 和 `double` 类型。此外，数值操作...

## 2. 列出原始类型的名称
`byte`、`short`、`int`、`float` 和 `double`。

## 3. 解释 Java 中原始数值类型的概念
（此处原文缺失具体解释内容）

## 4. 列出原始类型的名称
`byte`、`short`、`int`、`float` 和 `double`。

## 5. `int` 支持的最小值是多少？
`-2,147,483,648` (即 `-2^31`)

## 6. `int` 支持的最大值是多少？
`2,147,483,647` (即 `2^31 - 1`)

## 7. `int` 使用了多少位？
32 位 (4 字节)

## 8. 预测并解释此程序的输出
**输出**：`1.234568`

**解释**：我们确实输入了一个带有 9 位小数的数字，如之前所述，`printf` 方法默认只打印到 6 位小数，必要时会对最后一位进行四舍五入。在后面的章节，我们将学习如何修改输出的精度。

---

# 使用 System.out.println & System.out.printf 输出

## 11. 编写程序分别使用 `System.out.print` 和 `System.out.println` 向控制台输出 "Hello World" 并紧跟一个换行符

**使用 `System.out.println`**：
```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

**使用 `System.out.print`**：
```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.print("Hello World\n");
    }
}
```

> **注意**：`System.out.println` 会自动向输出添加一个行终止符。如果你选择使用 `print`，则必须向输出的数据中添加换行符 `'\n'` 才能获得与 `println` 相同的输出。

## 12. 编写一个程序，使用 `System.out.println` 向控制台输出包含双引号的文本 "Hello World"；使用 `\` 转义序列

```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println("\"Hello World\"");
    }
}
```

> **注意**：参见每个实例中使用 `\` 对双引号的转义。

## 13. 包含 "n" 的精确短语 "Hello World,\n"
（原文此处内容不完整，推测为输出字面量 `Hello World,\n`）

### 使用 `System.out.println` 从变量输出输出
```java
public class FormattingExercises {
    public static void main(String[] args) {
        String firstName = "John";
        String lastName = "Doe";
        System.out.println(firstName + " " + lastName);
    }
}
```

**编写一个程序，使用 `println` 语句将这些 String 变量在同一行输出到控制台，中间加一个空格**
（同上代码示例）

---

# 练习你的 Java 1 级

## 15. 字符串拼接
我定义了两个 String 变量：`String firstName = "John"; String lastName = "Doe";` 将这些字符串拼接，中间加一个空格，合并到一个名为 `fullName` 的单个 String 变量中，并将拼接后的字符串输出到控制台。

```java
public class FormattingExercises {
    public static void main(String[] args) {
        String firstName = "John";
        String lastName = "Doe";
        String fullName = firstName + " " + lastName;
        System.out.println(fullName);
    }
}
```

## E1. 学习 `DecimalFormat` 类
读者应该学习 `DecimalFormat` 类，以查看数值格式化规则如何应用于 `System.out.println` 和 `System.out.printf`。

---

# byte

Java 中的 `byte` 是一种整数类型，占据单个字节（8 位），并可以表示 2^8 = 256 个值；范围是 -128 到 127。

## 12. 编写一个程序，声明并初始化一个字节变量 `firstByte` 为 -115，然后将其变量输出到控制台，说明 "The value of firstByte is <value>"
```java
public class FormattingExercises {
    public static void main(String[] args) {
        byte firstByte = -115;
        System.out.println("The value of firstByte is " + firstByte);
    }
}
```

## 13. `byte` 类型支持的最小值是多少？
-128

## 14. `byte` 类型支持的最大值是多少？
127

## 15. 编写一个程序，使用 `Byte` 类中的内置常量，输出 `byte` 类型支持的最小最大值；同时也打印 `byte` 占据的位数
```java
public class FormattingExercises {
    public static void main(String[] args) {
        System.out.println(Byte.MIN_VALUE);
        System.out.println(Byte.MAX_VALUE);
        System.out.println(Byte.SIZE);
    }
}
```

---

# short

## 16. `short` 整数类型支持的最小值是多少？
-32,768

## 17. `short` 类型支持的最大值是多少？
32,767

## 18. 表示 `short` 使用了多少位/字节？
16 位 / 2 字节

## 19. 编写一个程序，声明并初始化一个 `short` 变量 `firstShort` 为 10,000，然后将其变量输出到控制台，说明 "The value of firstShort is <value>"
```java
public class PracticeJava {
    public static void main(String[] args) {
        short firstShort = 10000;
        System.out.println("The value of firstShort is " + firstShort);
    }
}
```

## 20. 写一个程序，使用 `Short` 类中的内置常量，输出 `short` 类型支持的最小值和最大值；同时打印 `short` 占据的位数
```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.println(Short.MIN_VALUE);
        System.out.println(Short.MAX_VALUE);
        System.out.println(Short.SIZE);
    }
}
```

---

# long

## 21. Java `long` 整数支持的最小值是多少？
-9,223,372,036,854,775,808 (即 `-2^63`)

## 22. Java `long` 类型支持的最大值是多少？
9,223,372,036,854,775,807 (即 `2^63 - 1`)

## 23. 表示一个 `long` 使用了多少位/字节？
64 位 / 8 字节

## 24. 写一个程序，初始化变量 `firstLong` 值为 7,000,000,000，并将变量打印到控制台，显示 "The value of firstLong is <value>"
```java
public class PracticeJava {
    public static void main(String[] args) {
        long firstLong = 7000000000L;
        System.out.println("The value of firstLong is " + firstLong);
    }
}
```

## 25. 解释上一个练习中数值值末尾后缀 `L` 的原因
如果字面量大于 `Integer.MAX_VALUE`，Java 会将其视为无效值，因为在某种意义上它将其视为一个越范围的整数。然而，当它看到后缀时，Java 会将该值评估为后缀所暗示的类型。

## 26. 以下变量 `firstLong` 的声明之间有什么区别？
```java
long firstLong = 7000000000L;
long firstLong = 700_000_0000L;
long firstLong = 7_000_000_000L;
```
这些声明样式之间实际上没有区别。Java 允许在字面量中使用下划线字符，以便人类读者更清晰地查看数值。下划线也没有影响。但是，下划线不能位于数字的开头或结尾。

## 27. 写一个程序，使用 `Long` 类中的内置常量，输出 `long` 类型支持的最小值和最大值；同时打印 `long` 占据的位数
```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.println(Long.MIN_VALUE);
        System.out.println(Long.MAX_VALUE);
        System.out.println(Long.SIZE);
    }
}
```

---

# 练习你的 Level 1：浮点数类型 (float, double)

## 28. `float` 类型支持的最小值是多少？
-3.402825 x 10^38 (即 `-Float.MAX_VALUE`)

## 29. `float` 类型支持的最大值是多少？
3.402825 x 10^38 (即 `Float.MAX_VALUE`)

## 30. 表示一个 `float` 使用了多少位/字节？
32 位 / 4 字节

## `float` 的精度是多少？
6-7 位有效数字（包括小数点前后的数字）。

> **说明**：整数是离散的值，在整数刻度上的每个点之间有确定的 1 个整数范围。但浮点数并非如此，即使在两个整数之间（例如 0 和 1），也可能存在无限数量的浮点数。计算机无法在浮点数刻度上的小范围内表示无限数量的点。目前已决定 `float` 类型将具有其可以表示的给定精度。任何尝试使用 `float` 类型表示超过 6-7 位数字的尝试将是失败的。
>
> 即使在指定的 6-7 位数字范围内，由于计算机存储浮点数的方式，某些数字是无法精确表示的。任何需要维护精度的十进制数字（如货币计算）都应该只使用 `BigDecimal`。建议读者研究浮点数在计算机中如何表示的原理。

## 32. `float` 可以表示的最小正值是多少？
~1.4 x 10^-45 (即 `Float.MIN_VALUE`)
将该数字想成 Java 类型可以做出的最小步长。

## 33. 为什么 `float` 也被称为单精度？
`float` 实际指的是所谓的“单精度浮点数”，这是一种设计为仅占据 4 字节的浮点数格式。这种标准是 IEEE 754 标准。

## 34. 写一个程序，使用 `Float` 类的内置常量，输出 `float` 类型支持的最大值最小值。同时打印 `float` 占据的位数
```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.println("Minimum value = " + (-1 * Float.MAX_VALUE));
        // 没有最小值的常量 (指负最大值)
        System.out.println("Maximum value = " + Float.MAX_VALUE);
        System.out.println("Bits occupied = " + Float.SIZE);
    }
}
```

## 35. 写一个程序，打印 Java 支持的最小正 `float`
```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.printf("Smallest positive float = %e%n", Float.MIN_VALUE);
    }
}
```

## 36. 为什么 Java 在 `float` 类型的变量后应用后缀 `F`？
这是因为 Java 假设任何浮点字面量都是 `double` 类型（`double` 意味着“双精度浮点数”），除非通过后缀 `F` 显式指定为单精度数字，否则它是双精度的。

## 37. 写一个程序，初始化一个单精度浮点数变量值为 7.919876542，并使用 `System.out.println` 将其值打印到控制台。注意并解释整数值与打印值之间的差异
```java
public class PracticeJava {
    public static void main(String[] args) {
        float firstFloat = 7.919876542F; // 注意末尾的 F
        System.out.println(firstFloat);
    }
}
```
**观察/解释**：输出是 `7.9198766` 而不是输入的 10 位数字 `7.919876542`！这是因为 `float` 类型的官方精度是 6-7 位有效数字，因此不应尝试给它分配更高精度的值。是的，输出中有 8 位有效数字，但最后一位是舍入的结果。有时舍入后的值是可以接受的。

## 38. 写一个程序，将小数值 1.768001117 赋值给 `float`。使用 `printf` 方法的 `%f` 格式符打印它。输出结果和你的观察
```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1 = 1.768001117f; // 注意末尾的 f
        System.out.printf("%f%n", f1);
    }
}
```
**输出**：`1.768001`

**观察**：输出与输入非常不同！事实上，即使输入手动舍入到最近的小数点，得到的值也比之前的练习更接近原始数字。Java 没有保留其值的完整性。结论：不要尝试赋值超出其精度（6-7 位）的浮点值。

## 39. `double` 支持的最小值是多少？
-1.7976931348623157 x 10^308 (即 `-Double.MAX_VALUE`)

## 40. `double` 支持的最大值是多少？
1.7976931348623157 x 10^308 (即 `Double.MAX_VALUE`)

## 41. 表示一个 `double` 使用了多少位/字节？
64 位 / 8 字节

## 42. `double` 可以表示的最小正值是多少？
~4.9 x 10^-324 (即 `Double.MIN_VALUE`)

## 43. `double` 的精度是多少？
15-16 位有效数字。

## 44. 写一行代码显示声明并初始化双精度变量 `firstDouble` 为 5.4875990943E-4
```java
double firstDouble = 5.4875990943E-4;
```

## 45. 写一个程序，使用 `Double` 类输出 `double` 类型支持的最小值和最大值。同时打印 `double` 占据的位数
```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.println("Minimum value = " + (-1 * Double.MAX_VALUE));
        // 没有直接对应的常量 (指负最大值)
        System.out.println("Maximum value = " + Double.MAX_VALUE);
        System.out.println("Bits occupied = " + Double.SIZE);
    }
}
```

---

# 评估精度类型 double
（此处原文结束，后续内容缺失）



# 练习你的 Java 1 级

## 46. 写一个程序，将 12 位数字 1768000111.7 赋值给 `double` 值，并使用 `printf` 方法的 `%f` 格式符以及 `println` 方法将其打印。输出结果和你的观察。

（此输入值在第 38 题中已对 `float` 尝试过）。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double d1 = 1768000111.77;
        System.out.printf("d1 = %f\n", d1);
        System.out.println(d1);
    }
}
```

输出：`d1 = 1768000111.770000`

观察：输出与输入匹配，因为输入值的精度为 12 位有效数字，这在 `double` 的范围范围内。

## 编写一个程序，将 double 类型的值 17680001119837.7 赋值给一个 double 类型的变量，并使用 `printf` 方法的 `%f` 格式符将其打印出来。注意输出并说明你的观察。

解决方案：修改上练习中的代码以使用本次练习中的数字。

输出：`d1 = 17680001119837.700000`

观察：输出与输入完全匹配，因为输入值的精度为 15-17 位有效数字，这在 `double` 的范围范围内。

## 编写一个程序，将 double 类型的值 17680001119837.35 赋值给一个 double 类型的变量，并使用 `printf` 方法的 `%f` 格式符将其打印出来。注意输出并说明你的观察。

解决方案：修改上练习中的代码以使用本次练习中的数字。

输出：`d1 = 17680001119837.340000`

观察：如你所见，输入数字的最后一位被四舍五入了。这是预期的，因为 `double` 最多支持 15-17 位数字。

总结：你应该仔细考虑是否对精度大于 15 位的数值使用 `double`。

## 编写一个程序，将 double 类型的值 123456789012345678.0 赋值给一个 double 类型的变量，并使用 `printf` 方法的 `%f` 格式符将其打印出来。注意输出并说明你的观察。

解决方案：修改上练习中的代码以使用本次练习中的数字。

输出：`d1 = 123456789012345678.000000`

观察：如你所见，第 18 位被向上四舍五入，这影响了 `d1` 的值。这是预期的，因为 `double` 最多支持 15-17 位的数字。

# 重要提示

使用 `printf` 和 `println` 打印 `float.MIN_VALUE`。对你的观察进行注释。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double d1 = Double.MIN_VALUE;
        System.out.printf("d1 = %f\n", d1);
        System.out.println("d1 = " + d1);
    }
}
```

输出：
`d1 = 0.000000`
`d1 = 4.9E-324`

显然，使用 `printf` 的第一个输出是错误的！这种现象是因为 `printf` 格式化浮点数的默认方式；它最多在小数点后保留 6 位，并且默认不会尝试像 `println` 那样以指数格式打印值。

在本章后面的部分中，将介绍关于数字格式化的练习。

为了进一步进行此类实验，请使用 `printf` 和 `println` 打印 double 值 -1.0011596521859。

# 重要提示

打印 1/10 结果至少 15 位小数。对输出进行注释。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double x = 1.0f/10.0f;
        System.out.printf("%.15f\n", x);
    }
}
```

输出：
`z = 0.10000000149012`

该值并不等于 0.1！1/10 的计算应该产生一个非常特定的有理结果。这种错误在某些浮点计算中会出现，这是计算机处理/存储浮点数的方式导致的。当我们需要精确精度时，这不是好事；想象一下金融应用计算数十亿货币单位的场景，这种错误将会出现。另一个在科学计算中需要精度的例子，这种处理上的不精确也会出现。我们将在下一节和“处理 III”中介绍如何使用 `BigDecimal` 实现浮点数所需的精度。

# 第 3 章：数值类型 BigInteger 和 BigDecimal：简记

**`BigInteger`**：你用什么来表示比 `long` 或 `unsigned long` 更大的整数值？使用 `BigInteger` 类型。它可以接受并操作任意大小的值。

**`BigDecimal`**：在浮点练习中，我们观察到浮点数的精确值并不总是正确的，因为 Java 提供了一种不同的类型 `BigDecimal` 来高精度地表示浮点数。使用 `BigDecimal` 类型的数字不是用 `float` 和 `double` 相同的内部格式表示的。由于其精度，对于任何金融计算，Java 中唯一接受的选择是 `BigDecimal`。

我们介绍了这两种类型，之后将引述它们。

# 第 3 章：数值处理 I

转换也适用于对象；你可以将给定类的对象转换为其任何祖先类的变量。这种能力是通过多态的概念来实现的。我们在关于类的章节中看到过这方面的示例。

装箱（boxing）和拆箱（unboxing）的概念可以被视为一种特殊的转换。我们将在稍后的章节中讨论装箱和拆箱的话题。

## 67. 为什么想要转换变量？

当你想要将被转换变量的内容放入不同的类型时，你就会想要转换变量。

例如，如果你有一个 `int a=10`，并且由于其值较小，我想将其放入 `byte` 类型的变量中（该类型支持 0 到 255 之间的值），我会这样转换它：

```java
byte c = (byte)a;
```

这行代码获取了 `int a` 内容的副本，并尽可能将其转为 `byte` 格式。

如果我必须转换一个 `int` 和一个 `long` 并希望将结果放入 `int` 中，由于目标变量的宽度小于至少一个输入变量，因此大于输出变量的输入变量可以转换为目标变量的宽度。我们看到下面的示例：

```java
long a = 10;
int result = (int)a + b;
```

有些转换更具戏剧性。`char` 类型（代表字符）可以转换为整数表示。例如：

```java
char letter = 'A';
int integerEquivalent = (int)letter;
```

通过这种方式，你现在能够方便字符的排序，因为它们具有显式的数值表示，这便于于按大小进行排序。

你也可以转换对象。例如，如果你有一个名为 `Road` 的类的如下对象：

```java
Road x = new Road();
```

如果我需要，可以将该对象转换为终极祖先类 `Object` 的对象如下：

```java
Object y = (Object)x;
```

（根据多态的概念，将任何对象转换为其任何祖先类都是可行的）

我可以将 `y` 转换回 `Road` 类的对象：

```java
Road z = (Road)y;
```

如前提到的，对于数值，如果你尝试转换一个包含的值高于目标变量支持范围的变量，将会丢失数据。例如，如果我们有如下场景：

```java
int var01 = 75000;
short var02 = (short)var01;
```

由于 `var01` 的值超过了 `short` 的最大值，`var02` 绝对不会包含 75,000，而是是一个扭曲的值。

## 68. 什么是隐式转换？

隐式转换是指一种场景：给定当前的操作，编译器会认为将变量的内容适配到更合适的类型，且该类型转换为给定类型是安全的。

例如，如果我想将一个 `int` 与一个 `long` 相加并将结果放入 `long` 中，代码看起来如下：

```java
long a = 10; int b = 50;
long result = a + b;
```

为了执行此编译，编译器必须使 `a` 和 `b` 的内容类型相同；在这种情况下，编译器将直接将 `b` 转换为更宽的类型（注意它没有改变 `b` 本身，只是获取了 `b` 的一个*转换值*）并将其相加得到结果。不会产生任何副作用，因为 `int` 的范围小于目标输出变量（在这种情况下为 `long`）。

现在，如果你有如下场景，结果为 `int`：

```java
long a = 10; int b = 50;
int result = a + b;
```

编译器不会将变量转换为 `int`。为什么呢？因为将给定类型（在此情况下为 `long` 转换为较小的类型）会导致数据丢失。因此，在这种情况下，如果你真的想这样做，编译器将坚持你对变量进行转换，要求显式地写出：

```java
int result = (int)a + b;
```

## 69. 解释编译并运行下面程序的 own。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        short a = 5;
        short b = 2;
        short result;

        result = a + b;
        System.out.println("result = " + result);
    }
}
```

它无法通过编译。无法编译的原因是在 Java 中，针对 `short` 或 `int` 值的计算是在 `int` 类型中进行的。尽管两个输入值都是 `short` 类型，Java 也会将 `a + b` 的值保持为 `int`。除非显式转换值，否则尝试将结果值放入 `short` 中是非法的。要实现这一点，你必须执行以下操作之一：

- (1) `result` 应该声明为 `int`
- (2) `result = (short)(a+b);` 也就是说，你必须计算结果转换为所需的类型（在此例下为 `short`）。

## 70. 写一个程序相加以下两个 short 值（i=250; j=3）。将结果放入 short 中并打印到控制台。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        short i = 250;
        short j = 3;
        short result;

        result = (short)(i + j);
        System.out.println("result = " + result);
    }
}
```

## 71. 写一个程序相乘以下 short 变量（i=250; j=300）。将结果放入 int 中并将结果打印到控制台。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        short i = 250;
        short j = 300;
        int result;

        result = i * j;
        System.out.println("result = " + result);
    }
}
```

注意：这将打印出 75000 而不是 short（short 为 32767）。

# 练习你的 Java 级水平

### 访问常量

| 类型 | 访问方式 |
| :--- | :--- |
| 类常量 | 使用类名作为常量名的前缀来访问。例如，在代码中，你通过 `Math.PI` 访问 `Math` 常量 `PI`。 |
| 实例常量 | 使用对象的名称作为常量名的前缀来访问。 |
| 方法常量 | 仅通过其名称进行访问（因为方法常量仅在其声明的方法内部被访问）。 |

### 74. 什么是未在编译时赋值的空白 final 变量？

空白 final 是一个在编译时未被赋值的 `final` 变量。

### 75. 写一个程序打印出内置常量 PI 的值。提示：Math.PI

```java
class PracticeJava {
    public static void main(String[] args) {
        System.out.println(Math.PI);
    }
}
```

### 76. 写一个程序打印出内置常量 E 的值。

```java
class PracticeJava {
    public static void main(String[] args) {
        System.out.println(Math.E);
    }
}
```

### 77. 写一行代码，将里德堡数（Rydberg）作为公类常量实现。

`public static final double rydberg = 1.0973315683592e0;`

### 78. 写一行代码，将里德堡数（Rydberg）作为公实例常量实现。

`public final double rydberg = 1.0973315683592e0;`

## 内置数学运算符和方法

在本练习中，将介绍 Java 中标准的数学运算符、常量和 `Math` 类的方法。

### 79. 写一个程序，将两个变量 `i=5` 和 `j=9` 相加并将结果打印到控制台。

```java
class PracticeJava {
    public static void main(String[] args) {
        int i = 5;
        int j = 9;
        int result = i + j;
        System.out.println("The sum is: " + result);
    }
}
```

### 80. 写一个程序，从两个变量 `i=5` 中减去 `j=9` 并将结果打印到控制台。

```java
class PracticeJava {
    public static void main(String[] args) {
        int i = 5;
        int j = 9;
        int result = i - j;
        System.out.println("The result is: " + result);
    }
}
```

### 81. 写一个程序，使用 `%` 运算符计算并打印 55 除以 22 的余数。

```java
class PracticeJava {
    public static void main(String[] args) {
        int i = 55;
        int j = 22;
        int rem = i % j;
        System.out.println("The remainder is: " + rem);
    }
}
```

### 82. 写一个程序，使用 `Math.sqrt` 方法计算并打印 81.39 的平方根。

```java
class PracticeJava {
    public static void main(String[] args) {
        double x = 81.39;
        double result = Math.sqrt(x);
        System.out.println("The square root is: " + result);
    }
}
```

### 83. 写一个程序，使用 `Math.pow` 方法打印 79.34 的 12 次方幂的值。

```java
class PracticeJava {
    public static void main(String[] args) {
        double x = 79.34;
        double result = Math.pow(x, 12);
        System.out.println("to the power of: " + result);
    }
}
```

# 第 3 章：数字处理 I

### 84. 写一个程序，使用 `Math.cbrt` 方法计算并打印 89 的立方根。

```java
class PracticeJava {
    public static void main(String[] args) {
        double x = 89;
        double result = Math.cbrt(x);
        System.out.println("the cube root is: " + result);
    }
}
```

### 85. 写一个程序，使用 `Math.pow` 方法打印 89 的五次方。

```java
class PracticeJava {
    public static void main(String[] args) {
        double x = 89;
        double result = Math.pow(x, 1.0/5.0);
        System.out.println("the fifth root is: " + result);
    }
}
```



# Java 练习题集

## 数学函数练习

### 86. 七次方根计算
写一个程序，使用 `Math.pow` 方法打印 121 的七次方根。

```java
class PracticeJava {
    public static void main(String[] args) {
        double x = 121;
        double result = Math.pow(x, 1.0/7.0);
        System.out.println("the 7th root is: " + result);
    }
}
```

### 87. 余弦值计算
写一个程序，使用 `Math.cos` 和 `Math.toRadians` 计算并打印 180 度的余弦值。

```java
class PracticeJava {
    public static void main(String[] args) {
        double degrees = 180;
        double radians = Math.toRadians(degrees);
        double cosine = Math.cos(radians);
        System.out.printf("the cosine of %f degrees = %f\n", degrees, cosine);
    }
}
```

### 88. 30度正切值
写一个程序，使用 `Math.tan` 和 `Math.toRadians` 计算并打印 30 度的正切值。

```java
class PracticeJava {
    public static void main(String[] args) {
        double degrees = 30;
        double radians = Math.toRadians(degrees);
        double tangent = Math.tan(radians);
        System.out.printf("the tangent of %f degrees = %f\n", degrees, tangent);
    }
}
```

### 89. 60度正切值
写一个程序，使用 `Math.tan` 和 `Math.toRadians` 计算并打印 60 度的正切值。

```java
class PracticeJava {
    public static void main(String[] args) {
        double degrees = 60;
        double radians = Math.toRadians(degrees);
        double tangent = Math.tan(radians);
        System.out.printf("the tangent of %f degrees = %f\n", degrees, tangent);
    }
}
```

### 90. 75度正弦值
写一个程序，使用 `Math.sin` 和 `Math.toRadians` 计算并打印 75 度的正弦值。

```java
class PracticeJava {
    public static void main(String[] args) {
        double degrees = 75;
        double radians = Math.toRadians(degrees);
        double sine = Math.sin(radians);
        System.out.printf("the sine of %f degrees = %f\n", degrees, sine);
    }
}
```

### 91. 反正弦计算
某个角度的正弦值为 .86602537。写一个程序，使用 `Math.asin` 和 `Math.toRadians` 计算并打印该值对应的弧度。

```java
class PracticeJava {
    public static void main(String[] args) {
        double sine = .86602537;
        double radians = Math.asin(sine);
        System.out.printf("the sine of %f degrees = %f radians\n", sine, radians);
    }
}
```

### 92. 反余弦计算
某个角度的余弦值为 .86602537。写一个程序，使用 `Math.acos` 和 `Math.toRadians` 计算并打印该值对应的弧度。

```java
class PracticeJava {
    public static void main(String[] args) {
        double cosine = .86602537;
        double radians = Math.acos(cosine);
        System.out.printf("the cosine of %f degrees = %f radians\n", cosine, radians);
    }
}
```

### 93. 重复题目
注：原文此处内容与第 91 题重复。

---

## 你的 Java 1 级练习

### 比较两个整数
给定两个数字 55 和 70，编写一个程序确定并打印其中哪一个较大。

```java
public class PracticeJava {
    public static void main(String[] args) {
        int bigger = Math.max(55, 70);
        System.out.printf("The bigger number is %f\n", bigger);
    }
}
```

**提示**：`Math.max`

### 比较两个双精度数
给定两个类型为 double 的 320 和 -2.95，编写一个程序确定并打印其中哪一个较小。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double smaller = Math.min(320, -2.95);
        System.out.printf("The smaller number is %f\n", smaller);
    }
}
```

**提示**：`Math.min`

> 注意：使用 `Math.min` 或 `Math.max` 进行比较时，被比较的数字必须是相同的类型。

### 舍入到最近的整数
将值 12777.899 舍入到最近的整数 double 并打印结果。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double x = 12777.899;
        double rounded = Math.round(x);
        System.out.printf("The rounded value is %f\n", rounded);
    }
}
```

**提示**：`Math.rint`

### 舍入到最近的 long
将值 12777.899 舍入到最近的 long 并打印结果。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double x = 12777.899;
        long rounded = Math.round(x);
        System.out.printf("The rounded value is %d\n", rounded);
    }
}
```

**提示**：`Math.round`

### 向上取整
编写一个程序分别打印 5.799 和 583.6 的向上取整（ceiling）。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double d01 = 5.799;
        double d02 = 583.6;
        double ceil01 = Math.ceil(d01);
        double ceil02 = Math.ceil(d02);
        System.out.printf("The ceiling of %f is %f\n", d01, ceil01);
        System.out.printf("The ceiling of %f is %f\n", d02, ceil02);
    }
}
```

**提示**：`Math.ceil`

### 向下取整
编写一个程序分别打印 5.799 和 583.6 的向下取整（floor）。

```java
public class PracticeJava {
    public static void main(String[] args) {
        double d01 = 5.799;
        double d02 = 583.6;
        double floor01 = Math.floor(d01);
        double floor02 = Math.floor(d02);
        System.out.printf("The floor of %f is %f\n", d01, floor01);
        System.out.printf("The floor of %f is %f\n", d02, floor02);
    }
}
```

### 符号函数
给出以下每个值的符号：

```java
public class PracticeJava {
    public static void main(String[] args) {
        double num1 = -55.6, num2 = 0.0004, num3 = 0.0, num4 = 79;
        double signum1 = Math.signum(num1);
        double signum2 = Math.signum(num2);
        double signum3 = Math.signum(num3);
        double signum4 = Math.signum(num4);
        System.out.printf("sign of %f is %f\n", num1, signum1);
        System.out.printf("sign of %f is %f\n", num2, signum2);
        System.out.printf("sign of %f is %f\n", num3, signum3);
        System.out.printf("sign of %d is %f\n", num4, signum4);
    }
}
```

---

## 第 3 章：数字处理

### 106. 复制符号
我有两个 double 变量 x 和 y。编写一个程序，返回一个具有 x 的幅度但 y 的符号的数字。使用以下值对 (x, y) 对程序进行测试：
- -89.5, 200
- 400, -300

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        double set1 = -89.5, set2 = 200;
        double set3 = 400, set4 = -300;
        double result = Math.copySign(set1, set2);
        double result2 = Math.copySign(set3, set4);
        System.out.printf("first pair result = %f\n", result);
        System.out.printf("second pair result = %f\n", result2);
    }
}
```

**提示**：`Math.copySign`

### 107. 整数除法陷阱
重要：打印以下除法的结果：a/b，其中 a 和 b 是为 1 和 4 的整数。将结果放入 float 中。解释该结果。

初始代码尝试可能会得到：

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int a = 1, b = 4;
        float result = a/b; // 错误
        System.out.println(result);
    }
}
```

**解释**：此代码的结果是 0！问题在于 1 和 4 是整数除法。如果你想要正确的结果，请确保进行类型转换：
```java
float result = (float)a/b;
```

此片段的预期输出是什么？

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int a = 5;
        int b = 0;
        System.out.printf("%d/%d", a, b);
    }
}
```

除零会导致程序停止并抛出 `java.lang.ArithmeticException`。

### 108. 特殊浮点数值
编写一个使用命名变量确定并打印以下计算结果：

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        float a = 0, b = 0, c = -1;
        System.out.printf("%f = %f\n", a, b);
        System.out.printf("%f = %f\n", a, c);
        float d = 1;
        System.out.printf("%f = %f\n", a, d);
    }
}
```

结果：
- 0/0 = NaN（意味着不是数字）
- -1/0 = -Infinity
- 1/0 = Infinity

---

## Java 1 级

### 109. 无穷大运算
编写一个程序确定并打印以下每个计算的结果：
- -Infinity + Infinity
- Infinity / -Infinity
- -Infinity / -Infinity
- Infinity / 0
- -Infinity / 0

**提示**：`Float.POSITIVE_INFINITY`, `Float.NEGATIVE_INFINITY`

```java
public class PracticeJava {
    public static void main(String[] args) {
        float a = Float.POSITIVE_INFINITY;
        float b = Float.NEGATIVE_INFINITY;
        System.out.printf("%f + %f = %f\n", a, b, a+b);
        System.out.printf("%f - %f = %f\n", a, b, a-b);
        System.out.printf("%f * %f = %f\n", a, b, a*b);
        System.out.printf("%f / %f = %f\n", a, b, a/b);
        System.out.printf("%f / %f = %f\n", b, a, b/a);
    }
}
```

结果：
1. -Infinity + Infinity = NaN
2. Infinity / -Infinity = NaN
3. -Infinity / -Infinity = NaN
4. Infinity / 0 = Infinity
5. -Infinity / 0 = -Infinity

---

## 复数

### 110. 极坐标表示
我们有一个复数 10 + 5i，其值在一个 double 变量中。用极坐标表示，即 (r, theta)。

**提示**：`Math.hypot`, `Math.atan2`

```java
public class PracticeJava {
    public static void main(String[] args) {
        double x_var = 5;
        double y_var = 10;
        double r = Math.hypot(x_var, y_var);
        double theta = Math.atan2(y_var, x_var); // 注意：此处示例代码中为2*x_var，按原文保留
        System.out.printf("The complex number in polar form is %f, %f\n", r, theta);
    }
}
```

---

## 自增自减运算符

### 111. 整数自增
给定初始化变量：`int i = 2;`
说明该语句执行后的值：`i++` → **3**

> 自增运算符 (`++`) 意味着目标变量的值应该加 1。

### 112. 浮点数自增
给变量：`double i = 8.46;`
说明该语句执行后的值：`i++` → **9.46**

> 自增运算符也适用于浮点数，将目标变量的值加 1。

### 113. 独立语句中的自增
给定初始化变量：`int i = 2;`
说明该语句执行后的值：`i++` → **3**

> 对于这种独立语句中的变量，操作符出现在变量之前还是之后并不重要。同样的逻辑也适用于自减运算符。

### 114. 整数自减
给以下变量：`int i = 26;`
说明该语句执行后的值：`i--` → **25**

> 自减运算符 (`--`) 意味着目标变量的值应该减 1。



## 115. 给以下变量：

```java
int i = 23;
```

说明该语句执行后 `j` 和 `i` 的值：

```java
int j = i++;
```

该语句表示 `j = i` 增加后的值。

因此在将 `i` 的值赋值给 `j` 之前，先增加了 `i`。因此结果是：

```
j = 23
i = 24
```

## 116. 说明语句执行后 `j` 和 `i` 的值：

```java
int j = i++;
```

给以下变量：

```java
int i = 23;
```

说明该语句执行后 `j` 和 `i` 的值：

语句 `j = i++` 意味着：

将 `i` 给 `j` 然后增加 `i`。

因此先赋值给 `j`，然后增加 `i`。

## 第 3 章：数字处理 I

### 118. 给定以下代码片段：

```java
int i = 5; j = 27;
int result = i++ + --j;
```

1. `i` 的预期值是多少？
2. `j` 的预期值是多少？
3. `result` 的预期值是多少？

| 问题 | 答案 |
| :--- | :--- |
| 1. `i` 的预期值 | `i = 6` |
| 2. `j` 的预期值 | `j = 26` |
| 3. `result` 的预期值 | `result = 5 + 26 = 31` |

用语言描述，我们可以说这行代码的意思是：
`result = (i, (i 的增量), PLUS, j 减后的值)`

### 119. 给定以下代码片段：

```java
int i = 5; j = 27;
result = --i - j;
```

1. `i` 的预期值是多少？
2. `j` 的预期值是多少？
3. `result` 的预期值是多少？

| 问题 | 答案 |
| :--- | :--- |
| 1. `i` 的预期值 | `i = 4` |
| 2. `j` 的预期值 | `j = 26` |
| 3. `result` 的预期值 | `result = 5 - 26 = -22` |

用语言描述，我们可以说：
`result = (减少 i 减少 j)`

### 120. 给定两个数值型变量 `g` 和 `y`，以下语句是什么意思？

```java
g += y;
```

这意味着将 `g` 增加 `y`，简之，`g = g + y;`。

### 121. 给定两个数值型变量 `g` 和 `y`，以下语句是什么意思？

```java
g *= y;
```

这意味着将 `g` 乘以 `y`，简之它完全匹配：
`g = g * y;`。

### 122. 给定两个数值型变量 `g` 和 `y`，以下语句是什么意思？

```java
g /= y;
```

这意味着将 `g` 除以 `y`，简之，`g = g / y;`。

### 123. 给定两个数值型变量 `g` 和 `y`，以下语句是什么意思？

```java
g -= y;
```

这意味着将 `g` 减去 `y`，简之，`g = g - y;`。

### 124. 给定以下语句 `int i += 12`，说明语句执行后 `i` 的值：

```java
i += 29;
```

`i = 41`。
该语句是以下简写形式：`i = i + 29;`（即给 `i` 加上 29）。

### 125. 给定以下语句 `int i /= 39`，说明语句执行后 `i` 的值：

```java
i /= 3;
```

`i = 13`。
该语句是以下简写形式：`i = i / 3;`（即将 `i` 除以 3）。

### 126. 给定以下语句 `int j *= 9`，说明语句执行后 `j` 的值：

```java
j *= 6;
```

`j = 54`。
该语句是以下简写形式：`j = j * 6;`（即将 `j` 乘以 6）。

### 127. `x = 5.2f`，说明执行以下语句后 `x` 的值：

```java
x -= 2;
float x;
```

`3.2`。
该语句是以下简写形式：`x = x - 2;`（即将 `x` 减去 2）。

### 128. 两个语句之间有什么区别？

```java
i += 1;
i++;
```

没有区别；它们的意思相同，都是将 `i` 增加 1。

## 描述整数溢出的概念

整数溢出的概念可以描述如下。

以类型 `int` 为例，它的所有值都表示在一个圆轮上，从最小整数开始到最大整数。

现在，我们有 `int x = Integer.MAX_VALUE`（大整数），如果给 `x` 加上 1，即 `x = x + 1`，有趣的是，结果仅仅是 `x` 变成了 `Integer.MIN_VALUE`！

> 如果我给 `x` 加上 2，那么 `x` 将会移动到 `Integer.MIN_VALUE - 1` 的位置。
> 这就是 Java 中发生整数溢出的方式。
> 任何整数计算都应该假设存在溢出的风险。
> 注意：即使你使用 `int` 类型作为示例，这个概念也适用于任何整数类型。

### 描述整数溢出的概念（续）

当整数计算的结果小于 `int` 类型能包含的最小值（即更接近 `--`）时，就会发生整数溢出。继续使用圆轮上的整数溢出进行类比，如果从 `x` 中减去 1，即 `x = x - 1`，我们正在圆轮上向移动，结果是 `x = Integer.MAX_VALUE`，这显然是错误的。

## 如何防止整数溢出/下溢？

使用 `Math` 类中的 "Exact" 系列方法（Java 8 引入）配合普通运算符。

## 如果我们在使用 "Exact" 方法时计算发生了溢出或下溢，会怎样？

程序将生成一个异常。如果程序没有捕获该异常，程序将停止运行。我们将在后面的章节讨论异常。

有两个 `int` 变量 `a` 和 `b`，它们的相加有溢出的风险，我想捕获这个溢出。编写一个示例程序显示如何实现。

说明当变量 `a` 和 `b` 都使用 `Integer.MAX_VALUE` 值时，该程序的输出。

提示：`Math.addExact`

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = Integer.MAX_VALUE; // 仅为了此程序的目的
        int b = Integer.MAX_VALUE; // 同上
        int total;

        total = Math.addExact(a, b);
        System.out.println(total);
    }
}
```

# Java 1 级练习

| ID | 描述 |
| :--- | :--- |
| 139. | 生成了以下异常：`java.lang.ArithmeticException`。我们有如下变量 `a = Integer.MIN_VALUE`。编写两个程序来显示尝试取反该值的结果。第一个程序应该使用取反运算符 `-()`，第二个程序应该使用 `Math.negate()` 方法。说明程序的结果并解释为什么如此。 |

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = Integer.MIN_VALUE;
        int total = -a;
        System.out.println(total);
    }
}
```

结果：生成了异常 `java.lang.ArithmeticException`。当输出此取反操作的结果时，`n = Integer.MAX_VALUE + 1`。这显然是一个 `int` 无法包含的数字（这是一个溢出场景），因此 `negate` 方法抛出了异常。

| 140. | 我们有如下长整变量 `a = 3074836868`。编写两个程序将其转换为 `int`，第一个使用强制类型转换，第二个使用 `Math.toInt()`。观察并注释每个程序的输出。 |

```java
public class PracticeJava {
    public static void main(String[] args) {
        long a = 3074836868;
        int result = (int) a;
        System.out.println(result);
    }
}
```

结果：第一个解决方案的强制转换给出了明显错误的结果：`-1247436868`。第二个解决方案理所当然地抛出了 `java.lang.ArithmeticException` 异常。

## 二进制（2 进制）

| ID | 描述 |
| :--- | :--- |
| 142. | 编写一个程序，将二进制值 `00001110` 赋值给 `int` 变量 `var01`。打印出对应的 10 进制数字。 |

```java
public class PracticeJava {
    public static void main(String[] args) {
        int var01 = 0b00001110;
        System.out.println(var01);
    }
}
```

| 143. | 编写一个程序，加二进制值 `10000101` 和 `1111101`。打印出结果的 10 进制数字。 |

```java
public class PracticeJava {
    public static void main(String[] args) {
        int var01 = 0b10000101;
        int var02 = 0b1111101;
        int var03 = var01 + var02;
        System.out.println(var03);
    }
}
```

## 十六进制数

| ID | 描述 |
| :--- | :--- |
| 144. | 编写一个程序，将十六进制值 `FFF0` 赋值给名为 `var01` 的 `int` 变量。打印出对应的 10 进制数字。 |

```java
int var01 = 0xFFF0;
System.out.println(var01);
```

| 145. | 编写一个程序，加十六进制值 `1EC05` 和 `F238C`。打印出结果的 10 进制数字。 |

```java
public class PracticeJava {
    public static void main(String[] args) {
        int var01 = 0x1EC05;
        int var02 = 0xF238C;
        int var03 = var01 + var02;
        System.out.println(var03);
    }
}
```

> 注：稍后我们将看到如何以十六进制打印结果。

# 随机数生成

### 146. 编写一个程序生成一个随机浮点数值 `x`，情况如下：

```java
public class PracticeJava {
    public static void main(String[] args) {
        double random01 = Math.random();
        System.out.println(random01);
    }
}
```

`0 ≤ x ≤ 1`

提示：`Math.random()`

### 147. `Math.random()` 方法生成的值的上限限制是多少？

上限值定义为 `< 1`。这意味着它不会完全达到 1。

### 148. 针对上一个示例（上限未达到 1 的情况），编写一个程序生成随机值 `x`，情况如下：

```java
public class PracticeJava {
    public static void main(String[] args) {
        double random01 = Math.random() * 10;
        System.out.println(random01);
    }
}
```

`0 ≤ x < 10`

```java
public class PracticeJava {
    public static void main(String[] args) {
        int random01 = (int) (Math.random() * 10);
        System.out.println(random01);
    }
}
```

### 149. 编写一个程序生成一个 1 到 10 之间的随机整数。

> 注：在第 20 章“随机数”中有更多关于随机数的练习题。

# 格式化

在本节中，我们将回顾练习以磨练你的格式化输出的技能。

特别关注 `printf` 方法可用的格式化选项。除非本文另有说明，否则请按要求执行。

### 150. 考虑到变量 `m = 304638`，以十进制、十六进制和八进制格式化输出它。观察并对每个程序的输出进行注释。

```java
public class PracticeJava {
    public static void main(String[] args) {
        int m = 304638;
        System.out.printf("%d\n", m);
        System.out.printf("%x\n", m);
        System.out.printf("%o\n", m);
    }
}
```

### 157. `%e` 和 `%f` 格式说明符之间的区别是什么？

`%e` 以指数计数法打印数据，而 `%f` 则打印完整的数字。指数本身被写为“`<符号><值>`”，例如 10^7 被写为 `-0.07`。数字 10^-7 被写为 `e-07`。

使用 `%e` 说明符打印出 `Float.MIN_VALUE` 的值。

```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.printf("%e\n", Float.MIN_VALUE);
    }
}
```

### 160. 使用为 9 的字段宽度和 2 位小数重复之前的练习。使用字段说明符代替 `%f`。

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1 = 8.91, f2 = 8.9, f3 = 327.338, f4 = 1768000111.77f;
        System.out.printf("%9.2e\n", f1);
        System.out.printf("%9.2e\n", f2);
        System.out.printf("%9.2e\n", f3);
        System.out.printf("%9.2e\n", f4);
    }
}
```

### 161. 使用 `%e` 格式说明符和为 9 的最小字段宽度、2 位小数重复之前的练习。观察并注释上一个练习中两种输出之间的差异。

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1 = 8.91, f2 = 8.9, f3 = 327.338, f4 = 1768000111.77f;
        System.out.printf("%9.2e\n", f1);
        System.out.printf("%9.2e\n", f2);
        System.out.printf("%9.2e\n", f3);
        System.out.printf("%9.2e\n", f4);
    }
}
```

观察：此输出与使用 `%E` 输出之间的区别在于，使用 `%E` 格式说明符时指数被写为大写字母。

### 162. 描述 `%g` 格式的功能。

当使用 `%g` 格式打印浮点数时，浮点数如下所示打印：如果数字的精度少于 6 个有效数字，则打印完整数字。如果数字的精度大于 6 位，则以指数计数法打印数字。

当存在精度说明符时，整数部分小于精度说明符宽度的数字将完整打印（带四舍五入），否则数字将以指数计数法打印。

## 第 3 章：数字处理 I（代码段示例）

### 代码段 1

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1 = 8.91, f2 = -8.9, f3 = 327.338, f4 = 17468000111.77f;
        System.out.printf("%e\n", f1);
        System.out.printf("%e\n", f2);
        System.out.printf("%e\n", f3);
        System.out.printf("%e\n", f4);
    }
}
```

### 代码段 2

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1 = 8.91, f2 = -8.9, f3 = 327.338, f4 = 17468000111.77f;
        System.out.printf("%.2f\n", f1);
        System.out.printf("%.2f\n", f2);
        System.out.printf("%.2f\n", f3);
        System.out.printf("%.2f\n", f4);
    }
}
```



# Java 练习代码示例

## 格式化输出练习

### 练习 161-168：printf 格式化说明符

以下代码演示了不同的 `printf` 格式标志：

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1=8.91f, f2=-8.9f, f3=327.338f, f4=17468000111.77f;
        System.out.printf("%+9.2f\n", f1);
        System.out.printf("%+9.2f\n", f2);
        System.out.printf("%+9.2f\n", f3);
        System.out.printf("%+9.2f\n", f4);
    }
}
```

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1=8.91f, f2=-8.9f, f3=327.338f, f4=17468000111.77f;
        System.out.printf("%-9.2f\n", f1);
        System.out.printf("%-9.2f\n", f2);
        System.out.printf("%-9.2f\n", f3);
        System.out.printf("%-9.2f\n", f4);
    }
}
```

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1=8.91f, f2=-8.9f, f3=327.338f, f4=17468000111.77f;
        System.out.printf("%#9.2f\n", f1);
        System.out.printf("%#9.2f\n", f2);
        System.out.printf("%#9.2f\n", f3);
        System.out.printf("%#9.2f\n", f4);
    }
}
```

**练习题：**

- 163. 使用不带任何字段宽度或精度说明符的 `%g` 格式重复练习161。
- 164. 重复之前的练习，这次使用最小字段宽度 9 和精度 2。
- 165. 重做之前的练习，确保正数的符号显示在输出中。
- 166. 重做之前的练习，确保输出右对齐。
- 167. 重做之前的练习，确保负值用括号而不是负号表示。
- 168. 重做之前的练习，确保值左对齐。

> **观察**：注意数字是右对齐的。

## 练习你的 Java 级1

### 打印浮点值并显示分组分隔符

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1=1000f, f2=12000, f3=-115000, f4=145000.743f;
        System.out.printf("%f\n", f1);
        System.out.printf("%f\n", f2);
        System.out.printf("%f\n", f3);
        System.out.printf("%f\n", f4);
    }
}
```

> **注意**：分组分隔符根据区域打印；例如，在欧洲某些国家，而不是逗号 `,`。

### 使用格式说明符将值 87.5 打印为 87.5%

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1=87.5f;
        System.out.printf("%%f\n", f1);
    }
}
```

### 修改练习将数字只打印 2 位小数

```java
public class PracticeJava {
    public static void main(String[] args) {
        float f1=87.5f;
        System.out.printf("%.2f%%\n", f1);
    }
}
```

## 逻辑运算符与位运算符

### 逻辑与（AND）

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = 5, b = 2;
        System.out.println(a & b);
    }
}
```

### 逻辑或（OR）

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = 5, b = 3;
        System.out.println(a | b);
    }
}
```

### 逻辑异或（XOR）

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = 5, b = 3;
        System.out.println(a ^ b);
    }
}
```

### 按位取反

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = 26;
        System.out.println(~a);
    }
}
```

### 176. 左移 4 位

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = 38, b = 4;
        int result = a << b;
        System.out.println(result);
    }
}
```

### 177. 左移运算的区别解释

**问题**：以下两者之间的区别是什么？

- 对于结果没有等价性，因为计算机以 2 进制存储数据，因此左移等同于乘以 2；
- 通常情况下一下：我们以 10 进制操作。在 10 进制中左移意味着乘以 10。在 10 进制中左移 4 次意味着将数字乘以 10^4。

```java
int a = 38;
result = a << 4;
```

**为什么结果是那样？**

### 178. 右移 2 位

```java
public class PracticeJava {
    public static void main(String[] args) {
        int a = 38, b = 2;
        int result = a >> b;
        System.out.println(result);
    }
}
```

**解释**

右移等同于对 2 进行整数除并返回商。因此，右移 2 次意味着除以 2（整数除，忽略余数），然后将之前计算的商再次除以 2，得到以下计算和结果：

```
38 >> 1 = 19
19 >> 1 = 9
```

### E1 复数除法

给定两个复数 `10 + 5i` 和 `2 + 9i`，编写一个程序将第一个数除以第二个数。

> **提示**：转换为极坐标形式，进行计算后再转换回笛卡坐标格式。

### E2 自定义 `Math.copySign` 实现

编写你自己的 `Math.copySign` 方法等价实现。

> **提示**：`Math.signum`

---

# 第 4 章 布尔运算 - 布尔原始类型

本章介绍了练习题，让你练习对布尔原始类型及其相关运算符的知识。还介绍了关于复合布尔表达式的练习。

| 序号 | 问题 | 答案 |
|------|------|------|
| 1 | 描述什么是 `boolean` 类型。 | `boolean` 是一种表示逻辑值（`true` 或 `false`）的类型。 |
| 2 | Java `boolean` 支持的取值范围是什么？ | 两个不同值之一：`true` 或 `false`（区分大小写）。 |
| 3 | 写一行代码声明一个名为 `b01` 的 `boolean` 变量并给其赋值为 `true`。 | `boolean b01 = true;` |

## 布尔测试

### 4. 测试相等性

设定一个值为 5 的 `int x` 和一个值为 7 的 `int y`。编写一个程序测试 x 是否等于 y，并将测试结果存入名为 `result` 的布尔变量中。将结果打印到控制台，并说明如下内容：“5 是否等于 7 的结果是 \<result\>”

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x = 5;
        int y = 7;
        result = x == y;
        System.out.printf("The result of whether %d is equal to %d is %b\n", x, y, result);
    }
}
```

> **笔记**
> 以以下方式思考语句 `result = x == y;`：
> `result = (x 是否等于 y，为真还是为假？)`
> 另外注意，`result` 也可以写为 `(x == y)`；如果加上括号使语句更容易理解的话。

### 5. 测试大于

设定一个值为 5 的 `int x` 和一个值为 7 的 `int y`。编写一个程序测试 x 是否大于 y，并将测试结果存入名为 `result` 的布尔变量中。将结果打印到控制台。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x = 5;
        int y = 7;
        result = x > y;
        System.out.printf("The result of whether %d is greater than %d is %b\n", x, y, result);
    }
}
```

### 6. 测试小于等于

设定一个值为 5 的 `int x` 和一个值为 7 的 `int y`。编写一个程序测试 x 是否小于等于 y，并将测试结果存入名为 `result` 的布尔变量中。将结果打印到控制台。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x = 5;
        int y = 7;
        result = x <= y;
        System.out.printf("The result of whether %d is less than or equal to %d is %b\n", x, y, result);
    }
}
```

### 7. 测试大于等于

我有一个值为 5 的 `int` 和一个值为 7 的 `int y`。编写一个程序测试 x 是否大于等于 y，并将测试结果存入名为 `result` 的布尔变量中。将结果打印到控制台。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x = 5;
        int y = 7;
        result = x >= y;
        System.out.printf("The result of whether %d is >= %d = %b\n", x, y, result);
    }
}
```

### 8. 测试小于

我有一个值为 5 的 `int` 和一个值为 7 的 `int y`。编写一个程序测试 x 是否小于 y，并将测试结果存入名为 `result` 的布尔变量中。将结果打印到控制台。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x = 5;
        int y = 7;
        result = x < y;
        System.out.printf("The result of whether %d is less than %d = %b\n", x, y, result);
    }
}
```

### 9. 测试不等于

我有一个值为 5 的 `int` 和一个值为 7 的 `int y`。编写一个程序测试 x 是否不等于 y。将测试结果存入名为 `result` 的布尔变量中并将结果打印到控制台。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x = 5;
        int y = 7;
        result = x != y;
        System.out.printf("The result of whether %d is not equal to %d = %b\n", x, y, result);
    }
}
```

### 10. 测试不大于

我有一个值为 5 的 `int` 和一个值为 7 的 `int y`。编写一个程序测试 x 是否不大于 y。将测试结果存入名为 `result` 的布尔变量并将结果打印到控制台。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x = 5;
        int y = 7;
        result = !(x > y);
        System.out.printf("The result of whether %d is less than or equal to %d = %b\n", x, y, result);
    }
}
```

> **注意**：没有“不大于”运算符。因此，将非符号 (`!`) 放在括号外可以实现“不大于”的效果。

### 11. 布尔值相等测试

我有一个值为 `false` 的 `boolean x` 和一个值为 `true` 的 `boolean y`。编写一个程序测试 x 是否等于 y。将测试结果存入名为 `result` 的布尔变量并将结果打印到控制台。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean x = false, y = true;
        boolean result = x == y;
        System.out.printf("Test of whether %b == %b\n", x, y);
    }
}
```

### 12. 复合布尔表达式

编写一个程序测试 x 是否大于 5 且 y 是否大于 7。分别用以下 x 和 y 的组合测试程序并打印每次测试的结果：(1,1), (6,7) 和 (15,15)。

#### 方案 #1

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x, y;
        x = 1; y = 1; result = (x > 5 && y > 7); System.out.println(result);
        x = 6; y = 7; result = (x > 5 && y > 7); System.out.println(result);
        x = 15; y = 15; result = (x > 5 && y > 7); System.out.println(result);
    }
}
```

#### 方案 #2



# 练习题

## 练习 12

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y;
        x = 1; y = 1; result = (x > 5 & y > 7); System.out.println(result);
        x = 6; y = 7; result = (x > 5 & y > 7); System.out.println(result);
        x = 15; y = 15; result = (x > 5 & y > 7); System.out.println(result);
    }
}
```

### 13. 前述两个方案有什么区别？

第一个方案使用了“短路”运算符，而第二个不是。

### 14. 短路布尔运算符和普通布尔运算符有什么区别？

一旦确定某个子测试失败，短路布尔运算符就会停止。在练习 12 的第一个测试中，当我们知道 `x` 小于 5 且测试的两部分都为真时，没有必要继续评估。然而，非短路布尔运算符会评估整个语句而不是在子测试失败停止。这种区别在于短路布尔运算符可能性能更好。

### 15. 编写一个程序测试 x 是否大于 5 且小于 7。（注意：本章中的 x、y 以及后续练习都是 `int` 类型；但你可以使用你喜欢的原始类型混合）。分别用以下 x 和 y 的组合测试程序并打印每次测试的结果：(1,1), (6,5) 和 (4,5)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x;
        int y;
        x = 1; y = 1; result = (x > 5 && y < 7); System.out.println(result);
        x = 6; y = 5; result = (x > 5 && y < 7); System.out.println(result);
        x = 4; y = 5; result = (x > 5 && y < 7); System.out.println(result);
    }
}
```

### 16. 解释逻辑或（OR）和异或（XOR）的区别。

逻辑或意味着“所考虑的对象中至少有一个为真”。

逻辑异或意味着“所考虑的对象中绝对只有一个为真”。

### 17. 编写一个程序测试 x 是否大于 5 或 y 是否小于 7。分别用以下 x 和 y 的组合测试程序并打印每次测试的结果：(1,1), (6,5) 和 (4,15)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y;
        x = 1; y = 1; result = (x > 5 || (y < 7)); System.out.println(result);
        x = 6; y = 5; result = (x > 5 || (y < 7)); System.out.println(result);
        x = 4; y = 15; result = (x > 5 || (y < 7)); System.out.println(result);
    }
}
```

### 18. 编写一个程序测试 x 是否大于等于 5 且 y 是否等于 0。分别用以下 x 和 y 的组合测试程序并打印每次测试的结果：(6,0), (5,0) 和 (4,1)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y;
        x = 6; y = 0; result = (x >= 5 && (y == 0)); System.out.println(result);
        x = 5; y = 0; result = (x >= 5 && (y == 0)); System.out.println(result);
        x = 4; y = 1; result = (x >= 5 && (y == 0)); System.out.println(result);
    }
}
```

### 19. 编写一个程序测试 x 是否大于等于 5 且 y 不等于 0。分别用以下 x 和 y 的组合测试程序并打印每次测试的结果：(6,0), (5,0), (4,1) 和 (7,2)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y;
        x = 6; y = 0; result = (x >= 5 && (y != 0)); System.out.println(result);
        x = 5; y = 0; result = (x >= 5 && (y != 0)); System.out.println(result);
        x = 4; y = 1; result = (x >= 5 && (y != 0)); System.out.println(result);
        x = 7; y = 2; result = (x >= 5 && (y != 0)); System.out.println(result);
    }
}
```

### 20. 编写一个程序测试 x 或 y 中是否有一个大于 5。分别用以下 x 和 y 的组合测试程序并打印每次测试的结果：(5,5), (6,6), (3,3), (1,10) 和 (10,1)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y;

        x = 5; y = 5; result = ((x > 5) ^ (y > 5)); System.out.println(result);
        x = 6; y = 6; result = ((x > 5) ^ (y > 5)); System.out.println(result);
        x = 3; y = 10; result = ((x > 5) ^ (y > 5)); System.out.println(result);
        x = 1; y = 10; result = ((x > 5) ^ (y > 5)); System.out.println(result);
        x = 10; y = 1; result = ((x > 5) ^ (y > 5)); System.out.println(result);
    }
}
```

# 第 4 章：布尔运算

### 21. 编写一个程序，测试 x 是否大于 5 或者小于 15 或者小于等于 25。

使用以下 x, y 的组合对程序测试，并在每次测试后打印结果：(5,16,25), (5,16,24), (5,15,24) 和 (4,30)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y,z;

        x=5; y=16; z=25; result = ((x > 5) || (y > 15)) && (z <= 25); System.out.println(result);
        x=5; y=16; z=24; result = ((x > 5) || (y > 15)) && (z <= 25); System.out.println(result);
        x=5; y=15; z=24; result = ((x > 5) || (y > 15)) && (z <= 25); System.out.println(result);
        x=4; y=25; z=30; result = ((x > 5) || (y > 15)) && (z <= 25); System.out.println(result);
    }
}
```

### 22. 编写一个程序，测试 x 是否大于或等于 5，且 y 或 z 中至少一个小于 15。

使用以下 x, y, z 的组合对程序测试，并在每次测试后打印结果：(5,14,20), (5,15,13), (5,10,10) 和 (4,30)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y,z;

        x=5; y=14; z=20; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
        x=5; y=15; z=13; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
        x=5; y=10; z=10; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
        x=4; y=25; z=30; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
    }
}
```

如果需要，可以将各个条件拆分为如下形式：

```java
boolean result1 = (y < 15) || (z < 15);
boolean result2 = (result1 && result2);
```

### 23. 编写一个程序，测试 x 是否大于或等于 5 或者小于 15 或者 y 小于等于 25。

使用以下 x, y 的组合对程序测试，并在每次测试后打印结果：(5,14,20), (5,15,13), (5,10,10), (4,5,30), 和 (1,20,20)。

```java
public class PracticeJava {
    public static void main(String[] args) {
        boolean result;
        int x,y,z;

        x=5; y=14; z=20; result = ((x >= 5) || (y < 15)) || (z <= 25); System.out.println(result);
        x=5; y=15; z=13; result = ((x >= 5) || (y < 15)) || (z <= 25); System.out.println(result);
        x=5; y=10; z=10; result = ((x >= 5) || (y < 15)) || (z <= 25); System.out.println(result);
        x=4; y=5; z=30; result = ((x >= 5) || (y < 15)) || (z <= 25); System.out.println(result);
        x=1; y=20; z=20; result = ((x >= 5) || (y < 15)) || (z <= 25); System.out.println(result);
    }
}
```

# 练习你的 Java 1级

### 24. 编写一个程序测试 x 是否大于或等于 5 或者 y 或 z 中其中一个小于 15。

分别使用以下 x, y, z 的组合对程序测试，并在每次测试后打印结果：(5,14,14), (5,20,13), (6,5,30) 和 (6,20,20)。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        boolean result;
        int x,y,z;
        x=5;y=14;z=14; result = ((x >= 5) || (y < 15)) || (z < 15); System.out.println(result);
        x=5;y=20;z=13; result = ((x >= 5) || (y < 15)) || (z < 15); System.out.println(result);
        x=6;y=5;z=30; result = ((x >= 5) || (y < 15)) || (z < 15); System.out.println(result);
        x=6;y=20;z=20; result = ((x >= 5) || (y < 15)) || (z < 15); System.out.println(result);
    }
}
```

### 25. 编写一个程序测试 x 是否大于或等于 5 且 y 或 z 中至少一个小于 15。

使用以下 x, y, z 的组合对程序测试，并在每次测试后打印结果：(5,14,20), (5,15,13), (5,10,10) 和 (4,30)。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        boolean result;
        int x,y,z;

        x=5; y=14; z=20; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
        x=5; y=15; z=13; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
        x=5; y=10; z=10; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
        x=4; y=25; z=30; result = ((x >= 5) && (y < 15)) || (z < 15); System.out.println(result);
    }
}
```

### 26. 编写一个程序测试 x 是否大于或等于 5 或者小于 15 或者 y 小于等于 25。

使用以下 x, y 的组合对程序测试，并在每次测试后打印结果：(5,14,20), (5,15,13), (5,10,10), (4,5,30), 和 (1,20,20)。

# 第 5 章：字符串：基础处理

本章的目的是确保你熟悉字符串处理以及格式化。同时也练习对字符串对象不可变性的理解。

| 序号 | 练习内容 | 代码示例 |
| :--- | :--- | :--- |
| 1 | 编写一个程序，声明一个名为 `firstName` 的字符串变量并使用 `new` 运算符将其初始化为 "John"。 | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>        String firstName = new String("John");<br>    }<br>}<br>``` |
| 2 | 重复上述练习，使用赋值运算符将 "John" 赋值字符串变量。 | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>        String firstName = "John";<br>    }<br>}<br>``` |
| 3 | 我有如下字符串 s1 和 s2：<br>`s1 = "John"`;<br>`s2 = "Leavings"`;<br>使用加法 (`+`) 运算符将这两个字符串拼接放入第三个字符串变量 s3 中，确保它们之间有一个空格。将 s3 打印到控制台。 | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>        String s1 = "John";<br>        String s2 = "Leavings";<br>        String s3 = s1 + " " + s2;<br>        System.out.println(s3);<br>    }<br>}<br>``` |
| 4 | 重复之前的练习，使用 String 类的 `concat` 方法。 | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>        String s1 = "John";<br>        String s2 = "Leavings";<br>        String space = " ";<br>        String s3 = s1;<br>        s3 = s3.concat(s2);<br>        System.out.println(s3);<br>    }<br>}<br>``` |



| 5 | 确定并打印练习 2 中字符串变量 `firstName` 所包含的字符串长度。提示：使用 String 类的 `length` 方法。 | 
```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String firstName = "John";
        int length = firstName.length(); // 我们将使用这个变量表示长度。
    }
}
``` |

# Java 1级练习

```java
int stringLength = firstName.length();
System.out.printf("The length of the first name is %s\n", stringLength);
}
```

注意：我们可以在声明变量 `stringLength` 的情况下，直接在 `System.out.printf` 语句中打印字符串的长度，如下：

`System.out.printf("The length of the first name is %s\n", firstName.length());`

- 6. 我有字符串 "Basketball"。打印它的长度，不声明任何变量。

```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.printf("The length is %d\n", "Basketball".length());
    }
}
```

- 7. 以小写打印练习2中变量 `firstName` 的值。

提示：使用 String 方法 `toLowerCase()`。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String firstName = "John";
        String firstNameLowerCase = firstName.toLowerCase();
        System.out.printf("firstName as all uppercase is %s\n", firstNameLowerCase);
    }
}
```

```java
或者
public class PracticeJava {
    public static void main(String[] args) {
        String firstName = "John";
        System.out.printf("firstName as all lowercase is %s\n", firstName.toLowerCase());
        // 我们方法的参数字段内执行了所需的方法
        //System.out.printf();
    }
}
```

- 8. 以大写打印上一个练习中变量 `firstName` 的值。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String firstName = "John";
        System.out.printf("firstName as all uppercase is %s\n", firstName.toUpperCase());
    }
}
```

- 9. 语句“String 是不可变的（immutable）”是什么意思？

在回答之前，必须首先理解对于指向对象的变量，变量中包含的直接不是对象本身，而是存储在它所引用对象位置的值。当你访问一个对象变量时，为了获取所引用的对象，Java 运行时会执行两个步骤：首先查找变量指向的内存地址，其次去该内存位置获取内容。关于不可变性的解释：

“String 是不可变的”这一语句意味着，一旦将值赋值给 String 对象，Java 实际上不允许更改 String 对象中包含的值。然而，这需要解释，在某种情况下，我们可以如下所示修改 String 的内容：

```java
String s1 = "Hello";
s1 += " How are you?";
```

我们将字符串 "How are you?" 添加到对象引用 `s1` 中的字符串时，实际上发生的情况是 Java 在后台内存的其它某处创建了一个新字符串 "Hello. How are you?"

# 第5章：字符串：基础处理

将此新字符串的位置引用赋值给变量 `s1`

为什么了解 String 类对象的不可变性这些知识很重要？了解这一点有许多原因，包括一个事实：修改 String（这现在会导致创建一个新字符串，并使持有其引用的变量更新为新字符串的位置）是相对耗费时间的。因此，对于我们在程序中需要频繁修改字符串的情况，使用可变的 `StringBuilder` 比使用 `String` 类更好；如果是特定的内存引用，那么当您修改 String 变量的内容时，知道这一点将是有益的。

实际上，字符串可以被称为不可变类型。它们有独特的行为，特别是以下这些：

1. （之前说过的）它们一旦创建就无法被更改。如果你修改一个 String（修订、修剪等），会创建一个新字符串，并以修改后的状态呈现给程序，使用相同的变量名，这让你产生 String 变量内容已经改变的错觉（如前所述，通过创建一个新字符串并让变量 `s1` 包含指向该新字符串内存位置的引用来实现）。对于许多程序来说，这对程序的构建没有负面影响，因为这种丢弃并重建对于请求修改的程序员是隐藏的。

2. 虽然它们是引用类型，但由于其不可变性，与其他类型不同，如果你将一个 String 传递给另一个尝试修改其内容的方法，调用方法中的原始 String 内容不会被修改。

注意：尽管有上述解释，从通常目的来说，你可以认为可以修改方法中的 String 内容，但你必须意识到后台正在发生什么。

- 10. 我有一个字符串引用 `s1`，初始化如下：`String s1 = null;`

这种初始化值为 `null` 代表什么？

初始化值为 `null` 实际上是在说“这个对象引用 `s1` 不包含对任何对象的引用”。

`null` 值不适用于 String 变量；它可以用于任何对象引用变量。当任何对象引用的值为 `null` 时，意味着该对象变量不包含对任何对象的引用。

- 11. 以下两个对象有什么区别？

`String s1 = null;`

`String s2 = "";`

变量 `s1` 不指向任何对象，而 `s2` 指向空字符串，空字符串仍被视为 String 对象，而 `null` 真的意味着什么都没有，甚至

```java
System.out.println(s1.length());
```

对于未赋值的变量，它将导致异常，空指针异常（NullPointerException）。

然而

```java
System.out.println(s2.length());
```

结果将为 0。

## 字符串相等性

给定两个字符串 `s1` 和 `s2`，使用 String 方法写一行代码来测试 `s1` 和 `s2` 是否相等，并将结果放入布尔变量中。

```java
boolean x = s1.equals(s2);
```

## 子字符串

- 13. 字符串中第一个字符的索引是多少？

这是因为 Java 中的字符枚举从 0 开始。因此，此字符串中的位置如下：

M

0

a

1

r

2

y

3

4

h

5

- 14. 给定字符串 "Mary had a little"，手动确定字符 'h' 在字符串中的位置。该字符的位置是。

# Java 1级练习

- 15. 给定字符串 "Mary had a little lamb"，将此位置打印到控制台：字母 'i' 的位置是：<position>。

提示：`<String>.indexOf` 方法。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String rhymeLine = "Mary had a little lamb";
        int letterPosition = rhymeLine.indexOf('i'); // 单个字母使用单引号
        System.out.printf("The position of the letter \i is %d\n", letterPosition);
    }
}
```

解 #1

注意：对于单个字符使用单引号而不是双引号，如在本例所示，当我们使用 `indexOf` 方法查找 'i' 时。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String rhymeLine = "Mary had a little lamb";
        System.out.printf("The position of the letter \i is %d\n", rhymeLine.indexOf('i'));
    }
}
```

解 #2

注意：在这种变体中，我们直接在 `System.out.method` 的参数字段内调用 `indexOf` 方法。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int letterPosition = "Mary had a little lamb".indexOf('i');
        System.out.printf("The position of the letter \i is %d\n", letterPosition);
    }
}
```

解 #3

注意：观察这种情况下我们展示了如何将 String 方法直接应用于字面量，而无需声明持有该字符串的变量。

```java
public class PracticeJava {
    public static void main(String[] args) {
        System.out.printf("The position of the letter \i is %d\n",
        "Mary had a little lamb".indexOf('i'));
    }
}
```

解 #4

注意（s）：在这种答案变体中，完全没有声明任何变量；我们直接在 `System.out` 的参数字段中使用 `indexOf` 方法。

- 16. 给定字符串 "Mary had a little lamb"，此字符串中第二个字母 'a' 的位置是多少？

提示：重载的 String， `indexOf` 方法。

# 第 5 章：字符串：基础处理

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String rhymeLine = "Mary had a little lamb";
        int positionFirstOccurrence = rhymeLine.indexOf('a');
        // 现在，我们找到了我们要查找的第 1 个字母 'a' 的位置
        // 以及之后的下一个字母 'a'
        int positionOfSecondOccurrence = rhymeLine.indexOf('a', positionFirstOccurrence + 1);
        System.out.printf("the position of the 2nd letter 'a' is %d\n", positionOfSecondOccurrence);
    }
}
```

- 17. 给字符串 "Mary had a little lamb, little, little lamb, Mary had a little lamb that was white as snow"，编写一个程序，确定并在控制台中输出字符串中单词 "little" 的第 2 次出现的位置。

提示：确定第一次出现位置的结尾，然后从之后开始搜索。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String rhymeLine = "Mary had a little lamb, little, little lamb, Mary had a little lamb that was white as snow";
        // 所以我们对单词 "little" 的第一次出现要做，
        // 然后从该次出现之后搜索。
        int firstAppearancePosition = rhymeLine.indexOf("little");
        int secondStartPosition = firstAppearancePosition + "little".length();
        int secondOccurrencePosition = rhymeLine.indexOf("little", secondStartPosition);
        System.out.printf("the 2nd occurrence of \"little\" is at position: %d\n", secondOccurrencePosition);
    }
}
```

- 18. 给字符串 "Mary had a little lamb,\n little lamb, little lamb, Mary had a little lamb that was white as snow"，编写一个程序来确定并在控制台中打印字符串中单词 "little" 的最后一次出现。

提示：lastIndexOf

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String rhymeLine = "Mary had a little lamb,\n little lamb,\n little lamb,\n Mary had a little lamb that was white as snow";
        int wordPosition = rhymeLine.lastIndexOf("little");
        System.out.printf("the position of the last \"little\" is %d.\n", wordPosition);
    }
}
```

- 20. 给出一个包含韵律句 "Mary had a little lamb,\n little lamb,\n little lamb,\nMary had a lamb that was white as snow" 的 String，编写代码在单词 "little" 出现的地方将其替换为短语 "big big"（以保持韵律 j）。打印修改后的字符串。

提示：String replace

51

# Java 练习 第 1 

```java
public class PracticeJava {
    public static void main(String[] args) {
        String rhyline = "Mary had a little lamb,\nlittle lamb,\nlittle lamb,\nMary had a little lamb that was as white as snow";
        String newRhyline = rhyline.replace("little", "big big");
        System.out.printf("The new rhyme is:\%s\n", newRhyline);
    }
}
```

- 21. 给韵律句 "Mary had a little lamb,\nlittle lamb,\nlittle lamb,\nMary had a little lamb that was as white as snow"，编写一个程序，替换韵律句中任何地方出现的单词 "little"。打印结果字符串。提示：将该单词替换为空字符串。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String rhyline = "Mary had a little lamb,\nlittle lamb,\nlittle lamb,\nMary had a little lamb that was as white as snow";
        String newRhyline = rhyline.replace("little", "");
        // "little" 被替换为空字符串。双引号之间什么都没有
        // 就等于一个空字符串。
        System.out.printf("The new rhyme is:\%s\n", newRhyline);
    }
}
```



- 22. 我们给出的一个数字为 `111-222-3333`，其中前 3 位数字是区号。提取并打印区号。提示：`substring`

```java
public class PracticeJava {
    public static void main(String[] args) {
        String phoneNumber = "111-222-3333";
        int startPosition = 0; // 我们从字符串开头开始
        int numberOfCharacters = 3;
        String areaCode = phoneNumber.substring(startPosition, (startPosition + numberOfCharacters);
        System.out.printf("The area code is:\%s\n", areaCode);
    }
}
```

- 23. 我们给出的一个数字为 `111-222-3333`，其中最后 7 位是用户号码。提取并打印用户号码，即 `222-3333`。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String phoneNumber = "111-222-3333";
        int startPosition = 4; // 我们从第一个连字符之后开始。记得从 0 开始。
        String subscriberNum = phoneNumber.substring(startPosition);
        // 提取到字符串的结尾
        System.out.printf("The subscriber number is:\%s\n", subscriberNum);
    }
}
```

- 24. 给出一个数字 `111-222-3333`，其中前 3 位数字是区号。提取并打印区号。后面的 3 位是"提取"并打印它。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String phoneNumber = "111-222-3333";
        int startPosition = 0; // 我们从字符串开头开始
        int numberOfCharacters = 3;
        String areaCode = phoneNumber.substring(startPosition, startPosition + numberOfCharacters);
        System.out.printf("The area code is:\%s\n", areaCode);
    }
}
```

# 第 5 章：字符串：基础处理

注意：你可以设计得更通用一些；确定两个连字符的位置并提取它们之间的内容。

- 25. 我们给出的数字为 `111-222-3333`，其中前 3 位是区号。找到并打印区号中 `'1'` 的最后一次出现的位置。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String phoneNumber = "111-222-3333";
        int startPosition = 2;
        int foundPosition = phoneNumber.lastIndexOf('1', startPosition);
        System.out.printf("Last position of 1 in the area code is %d\n", foundPosition);
    }
}
```

- 26. 如下：

`"how are you?"`

编写一个程序去除前后的空格并打印结果。通过在字符串后面打印字母 `'X'` 来确认你删除了空格。

提示：`String trim`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String s1 = "how are you?";
        String ending = "X";
        String s2 = s1.trim();
        System.out.printf("%s\n%s", s2, ending);
    }
}
```

- 27. 如下：

`">>>>>>How are you<<<<"`

使用 `String` 类的 `replace` 方法删除边界 `"How are you?"` 的字符。打印结果。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String s1 = ">>>>>>How are you<<<<";
        String s2 = s1.replace(">", "");
        System.out.println(s2);
    }
}
```

- 28. 字符串 `"Mary had a little lamb,\nlittle lamb,\nlittle lamb,\nMary had a little lamb that was white as snow"` 输出：

```text
Mary had a little lamb,
little lamb,
little lamb,
Mary had a little lamb that was white as snow
```

编写一个程序，确定韵律句中第二行相对于开头的单词 `"lamb"` 的位置。

代码逻辑（这是一种可能的方法）：提取第二行（`\n` 是分界点），然后在提取的行中查找单词 `"lamb"`。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String rhymeLine = "Mary had a little lamb,\n little lamb,\n little lamb,\n Mary had a little lamb that was white as snow";
        int startPos = rhymeLine.indexOf("\n") + 1;
        String rhymeFrom2Line = rhymeLine.substring(startPos);
        int endPos = rhymeFrom2Line.indexOf("\n");
        String rhymeFrom2Line = rhymeFrom2Line.substring(0, endPos+1);
    }
}
// 我们已经将第二行提取到变量 `rhymeFrom2Line` 中
```

# 练习你的 Level 1

```java
int wordPos = rhyme2nd.indexOf("lamb");
System.out.printf("The 1st position of the word \"lamb\" in line 2 = %d\n", wordPos);
```

### 格式化字符串输出

我有以下 `String` 变量；`s1="Mary"`, `s2="had"`, `s3="a"`, `s4="little"` 和 `s5="lamb"`。

将它们每一个都右对齐打印在一个宽度为 10 个字符的字段中。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String s1 = "Mary", s2 = "had", s3 = "a", s4 = "little", s5 = "lamb";
        System.out.printf("%-10s\n", s1);
        System.out.printf("%-10s\n", s2);
        System.out.printf("%-10s\n", s3);
        System.out.printf("%-10s\n", s4);
        System.out.printf("%-10s\n", s5);
    }
}
```

- 29. 重复上一个练习，但输出左对齐。同时，每个对齐的字符串左右都用字符 `'#'` 进行包围。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String s1 = "Mary", s2 = "had", s3 = "a", s4 = "little", s5 = "lamb";
        System.out.printf("#%-10s#\n", s1);
        System.out.printf("#%-10s#\n", s2);
        System.out.printf("#%-10s#\n", s3);
        System.out.printf("#%-10s#\n", s4);
        System.out.printf("#%-10s#\n", s5);
    }
}
```

- 31. `String.format` 方法的作用是什么？

`String.format` 方法的行为本质上与 `System.out.println/print` 方法相似，但它是被放入一个字符串中，而不是写入到控制台。

该方法在以下场景中非常有用：在代码的某些点产生了中间输出，并倾向于将这些中间输出附加字符串中，以便在处理的后期将最终字符串输出到控制台或文件。

- 32. 重复练习 30，这次将所有中间输出放入 `String` 变量 `s` 中。在所有处理结束后打印出来。

提示：

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String s1 = "Mary", s2 = "had", s3 = "a", s4 = "little", s5 = "lamb";
        String s = "";
        s = s + String.format("%-10s\n", s1);
        s = s + String.format("%-10s\n", s2);
        s = s + String.format("%-10s\n", s3);
        s = s + String.format("%-10s\n", s4);
        s = s + String.format("%-10s\n", s5);
        System.out.println(s);
    }
}
```

# 第 6 章. 条件处理

计算机语言的一个关键部分是根据布尔条件的结果来引导执行（或不执行）特定的代码段/块。本章将练习你使用条件处理的技能，通过 `if`、`if/else`、`else` 以及 `switch`、`case`、`break` 和 `default` 语句来引导特定代码块的执行。

| 条件运算符：if 至少 | if/else |
| :--- | :--- |
| 1. 我有两个整数变量 `x` 和 `y`，值分别为 5 和 7。比较这两个值并打印一个语句说明哪一个更大。仅使用 `if/else` 进行比较。 | ```java
public class PracticeYourJava {
    public static void main(String[] args) {
        boolean b01;
        boolean b02;
        int x = 5;
        int y = 7;

        b01 = x > y;
        b02 = x < y;

        if (b01 == true) {
            System.out.printf("%d is greater than %d", x, y);
        }
        if (b02 == true) {
            System.out.printf("%d is greater than %d", x, y);
        }
        if (x > y) {
            System.out.printf("%d is greater than %d", x, y);
        }
    }
}
``` |
| 注：在比较两个解决方案时，观察到布尔变量 `b01` 和 `b02` 是不需要的，`(x > y)` 或 `(y > x)` 是一个返回真或假结果的自包含语句。 | |
| 2. 我有两个浮点型变量 `x` 和 `y`，值分别为 5.77 和 7.83。比较这两个值，如果它们相等，否则说明它们不相等。使用 `if/else` 结构。 | ```java
public class PracticeYourJava {
    public static void main(String[] args) {
        float x = 5.77f;
        float y = 7.83f;

        if (x == y) {
            System.out.println("The numbers are equal");
        } else {
            System.out.println("The numbers are not equal");
        }
    }
}
``` |
| 解释：`else` 条件可以描述为：当条件为假时，由 `else` 条件处理。当括号内内容为真的问题。 | |

# 练习你的 Java Level 1

3. 我有两个整数变量 `x` 和 `y`。编写一个程序比较它们并打印哪一个更大，如果它们相等，程序说明它们相等。硬编码 `x` 和 `y` 的值为 5 和 7 来测试你的程序。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int x = 5;
        int y = 7;

        if (x > y) {
            System.out.printf("%d is > %d", x, y);
        } else if (y > x) {
            System.out.printf("%d is < %d", y, x);
        } else if (x == y) {
            System.out.printf("%d = %d", x, y);
        }
    }
}
```

4. 上一个练习中显示的两个解决方案有什么区别？

第一个解决方案会遍历并评估 `<condition>` 中的每个条件。但在这种情况下，由于每个条件互斥，如果前面的条件被评估为真，则没有需要测试后续条件（在这种情况下我们已经知道 `x > y`，没必要检查 `y > x` 或 `x == y`）。因此，第二个解决方案使用了 `else` 条件，如果前面的条件为真，则不再进行评估。

- 5. 根据给定的温度值编写程序，输出以下内容：

  1. 如果 `temperature < 60`，输出 `"Cold enough to wear a coat"`

  2. 如果 `temperature >= 60` 但 `< 68`，输出 `"Cold enough to wear a jacket"`

  3. 否则输出 `"No jacket required"`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        float temperature = 60;
        if (temperature < 60) {
            System.out.println("Cold enough to wear a coat");
        } else if (temperature >= 60 && temperature < 68) {
            System.out.println("Cold enough to wear a jacket");
        } else {
            System.out.println("No jacket required");
        }
    }
}
```

## 组合多个条件

| 条件运算符：if 至少 | if/else |
| :--- | :--- |
| 给两个数值变量 `x` 和 `y`，解释以下含义：`if ((x > 5) && (y > 20)) { // action... }` | 代码表示如果 `x` 大于 5 且 `y` 大于 20，则执行括号内的操作。 |
| 给两个数值变量 `x` 和 `y`，解释以下含义：`if ((x > 5) \| (y < 20)) { // action... }` | 代码表示如果 `x` 大于 5 或者 `y` 小于 20，则执行括号内的操作。注：你知道逻辑“或”意味着“至少有一个条件有效”。 |



| 给三个数值变量 `x`、`y` 和 `z`，解释以下含义：`if ((x > 5) | (y > 20) | (z == 0)) { // action... }` | 代码表示如果 `x` 的任何一个值大于 5 或者大于 20 或者 `z`，则执行括号内的操作。注：见上一个解决方案。 |

| 给三个整数 `x`、`y` 和 `z`，解释以下含义（注意括号的位置）：`if ((x > 5) && ((y > 20) ^ (z == 0))) { // action... }` | 代码分别评估两个不同的条件集，即：`(x > 5)` 和 `((y > 20) ^ (z == 0))`。`&&` 条件是“如果两个条件都为真”，则执行括号内的操作。注：记住异或（XOR）意味着只有一个条件可以为真。将其与“或”的功能对比（见上一个练习）。 |

使用三元运算符重写这段代码片段：

```java
int x = 50, y = 0;
if (x > 10)
    y = 5;
else
    y = 27;
System.out.println(y);
```

```java
int x = 50, y = 0;
y = x > 10 ? 5 : 27;
System.out.println(y);
```

## switch 和 case 语句

解释你对 `switch` 语句工作原理理解。`switch` 语句是一种条件处理结构，根据受评估变量的值，根据变量的值调用特定的代码块。`switch` 结构使用 `switch`、`case`、`break` 和 `default` 关键字来确定、绑定并退出 switch 结构中的特定代码块。每个 `case` 都由 `case` 和 `break` 关键字封装。对于任何我们没有 case/break 的情况，都可以由 switch 块末尾的 `default` 块处理。

例如，参见以下代码块：

### Java 1级练习

```java
int zz=10;
switch(zz)
{
    case 5:
        System.out.println("zz is equal to 5");
        // 意味着此特定块的结束。你退出了 case（因此退出了 switch 块）
        break;
        // 
    case 6:
    case 7:
        System.out.println("zz is equal to 6 or 7");
        // 注意我们可以将多个 case 组合在一个块中。
        break;
    case 8:case 10:
        System.out.println("zz is equal to 8, 9 or 10!");
        break;
    default:
        System.out.println("Default 涵盖任何未被 case 涵盖的情况!");
}
```

- 12. 假设 zz=5，解释以下 switch 的输出并说明其原因。

```java
int zz=5;
switch(zz)
{
    case 5:
        System.out.println("zz is equal to 5");
    case 6:
    case 7:
        System.out.println("zz is equal to 6 or 7");
        // 我们可以将多个 case 组合在块中。
        break;
    default:
        System.out.println("Default 涵盖任何未被 case 涵盖的情况!");
}
```

输出：

zz is equal to 5

zz is equal to 6 or 7

原因：case 5 结尾没有 break 语句；当没有此类语句时，switch 会继续在 switch 块内运行，直到遇到 break、default 语句或块的结束！

这种效应有时是有意的，但在这种情况下我们必须小心地放置 break 语句。

- 13. 写一个程序，使用 switch 打印任何月份（指定为字符串）有多少天。硬编码值以匹配你的类型。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String month = "jan";
        month = month.toLowerCase(); // 为了统一处理
        month = month.substring(0, 3); // 3字母字符
        switch(month) {
            case "jan": case "mar": case "may": case "jul": case "aug": case "oct": case "dec":
                System.out.println("This month has 31 days");
                break;
            case "apr": case "jun": case "sep": case "nov":
                System.out.println("This month has 30 days");
                break;
            case "feb":
                System.out.println("This month has 28 days");
                break;
            default:
                System.out.println("无效月份。请至少输入月份的前三个字母");
        }
    }
}
```

- 14. 在我们的酒店，我们为常客提供奖励卡。有三个卡等级，即金级、银级和铜级，其中铜级最低最低。

- 每个级别的福利如下：

* 铜级免费停车 + 报纸

* 银级特性 + 早餐

* 金级、银级特性 + 单人晚餐

如果你没有奖励卡，那么默认情况下你只能得到房间。

写一个使用包含卡等级的 String 变量的程序，使用 switch 块打印每个级别的所有福利。确保你没有重复代码。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String customerLevel = "bronze"; //硬编码测试值
        customerLevel = customerLevel.toLowerCase(); // 为了处理的统一性
        System.out.println("your benefits are:");
        switch (customerLevel) {
            case "gold":
                System.out.println("t included dinner for 1");
            case "silver":
                System.out.println("t included breakfast");
            case "bronze":
                System.out.println("t included newspaper");
            default:
                System.out.println("t room");
        }
    }
}
```

注意：观察到为了打印每个级别的汇总福利，我们将 case 按照特定的顺序排列，以利用在不向每个 switch 块中显式放置 break 时提供的穿透（fall-through）功能。

# 第 7 章 数组

数组是任何编程语言中方便且必要的部分，因为它们有助于将数据项组合成单一的索引单元。在本章中，你将有机会练习并增强你的 Java 数组技能。本章介绍的练习包括数组声明、创建、初始化、赋值、复制、反转、子集操作、排序和元素搜索。还介绍了多维数组的练习。

除了处理数组的内置语法外，大量使用了 `Arrays` 类的方法。

| # | 在 Java 中，数组是什么？ | 数组是一种数据元素，它具有一个索引列表（原始类型或对象），这些元素的类型是*相同的*。数组索引是一个整数索引。 |
|---|---|---|
| 1 | | 如果你想将不同类型的对象放入数组，你必须将对象强制转换为数组的类型（如果在给定情况下可行）。从元素的意义上说，它们是相同类型。 |
| 2 | 它们是 Object 类的类吗？ | 是，因为数组是对象，且 Java 中对象的终极祖先类是 Object |
| 3 | 我定义了一个整数数组：`int[] array = new int[3];` 解释此代码语句中每个部分的含义：1. `int` 是我们要定义的变量类型名称，在本例中，它是指向整数数组的引用变量。在声明中，类型名后的 `[]` 表示它是该类型的数组变量。2. `array` 是我们选择的变量名，用于定义该数组对象引用，它包含该类型的元素。3. `new int[3]` 表示我们请求系统为一个包含 3 个整数的数组分配空间。4 出现在等号左侧的 `array`。 |
| 4 | 数组的*第一个*索引是多少？ | 0。Java 中的数组始终从索引 0 开始 |
| 5 | 写一行代码声明一个 int 数组变量 `intArray`。 | `int[] intArray;` |
| 6 | 写一行代码实例化一个名为 `intArray` 且容量为 20 个整数的数组。 | `int[] intArray = new int[20];` |
| 7 | 给数组的第一个索引赋值 2。 | `intArray[0] = 2;` |
| 8 | 给数组的第一个索引赋值 800。 | `intArray[0] = 800;` |
| 9 | 给数组的第三个索引赋值 17。 | `intArray[2] = 17;` |
| 10 | 写一个程序，为以下类型各创建一个大小为 5 的数组：Float, float, int, double, boolean。 | `import java.util.*; class PracticeJava { public static void main(String[] args) { Float[] fArray1 = new Float[5]; float[] fArray2 = new float[5]; Integer[] iArray1 = new Integer[5]; int[] intArray2 = new int[5]; double[] dArray1 = new double[5];` |

### Java 练习 1

```java
boolean[] bArray1 = new boolean[5];
```

- 写一个程序实例化一个容量为 String 数组。将前五个元素初始化为："Mary", "had", "a", "little", "lamb"。

- 使用数组字段打印数组长度。

注意：正如你将观察到的，数组长度是分配的空间，而不是占据的空间。

- 写一个程序实例化一个名为 `intArray` 的整数数组。使用数组字段打印长度。

- 是或否：Java 会初始化数组中的值？

是。读者应与 Java 不初始化单独变量的事实进行对比。

17. 默认初始化的数组元素是什么？

null

18. 解释以下代码中的错误：

```java
public class PracticeYour {
    public static void main(String[] args) {
        int[] array01 = new int[] { 10, 11, 12, 13, 14 };
        System.out.printf("%d\n", array02[5]);
    }
}
```

该代码尝试打印一个具有 5 个元素的数组的第 5 个元素。运行该代码时，将发生以下异常：`java.lang.ArrayIndexOutOfBoundsException`。结论：永远不要访问不存在的索引。

19. 编写一个程序实例化一个具有 0 个元素的 `int[]`。打印数组的长度。

```java
public class PracticeYour {
    public static void main(String[] args) {
        int[] array01 = new int[0];
        System.out.println("length of " + array01.length);
    }
}
```

20. 解释以下两个数组之间的区别：

```java
int[] array01;
int[] array02 = new int[0];
```

第一个声明创建了一个将持有数组的变量；完全没有定义任何数组。第二个声明实际上定义了一个空数组。

21. 复制数组

将数组复制到名为 `array02` 的新 `int[]`。打印内容。

```java
int[] array01 = new int[] { 10, 11, 12, 13, 14 };
```

提示：`Arrays.copyOf`

```java
import java.util.*;
public class PracticeYour {
    public static void main(String[] args) {
        int[] array01 = new int[] { 10, 11, 12, 13, 14 };
        int[] array02 = Arrays.copyOf(array01, array01.length);
        System.out.printf("%d, %d, %d, %d, %d\n", array02[0], array02[1], array02[2], array02[3], array02[4]);
    }
}
```

22. 修改上一个练习的解决方案以检查 `array01` 和 `array02` 是否相同。打印你的发现。

提示：`Arrays.equals`

```java
import java.util.*;
public class PracticeYour {
    public static void main(String[] args) {
        int[] array01 = new int[] { 10, 11, 12, 13, 14 };
        int[] array02 = Arrays.copyOf(array01, array01.length);
        boolean isEqual = Arrays.equals(array01, array02);
        if(isEqual == true)
            System.out.println("The arrays have the same content!");
        else
            System.out.println("The arrays do NOT have the same content!");
    }
}
```

### 练习 Java 级 1

23. 将数组的一部分复制到另一个数组

我们有一个整数数组 `intArray01`，包含如下 5 个元素：

- [0] 55
- [1] 747
- [2] 15000
- [3] 89
- [4] 2333

将 `intArray01` 的前 3 个元素复制到 `intArray02` 中。打印 `intArray02` 的长度及其内容，使用以下代码：

```java
import java.util.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        int[] intArray01 = new int[]{500,17500,89,2333};
        int[] intArray02 = new int[]

        // 现在将 intArray01 的前 3 个元素复制到 intArray02
        // 我们从索引 0 到索引 2
        intArray02 = Arrays.copyRange(intArray01, 0, 3);
        // 观察赋值。返回的数组长度与
        // 长度完全一致。
        System.out.printf("intArray02's length is %d\n", intArray02.length);
        System.out.printf("intArray02's contents are %d, %d, %d\n", intArray02[0],intArray02[1],intArray02[2]);
    }
}
```

提示：`Arrays.copyRange`

24. 我们有一个整数数组 `intArray01`，包含如下 5 个元素的内容：

- [0] 55
- [1] 747
- [2] 15000
- [3] 89
- [4] 2333

将 `intArray01` 的第 2 到第 4 个元素复制到 `intArray02` 的第 3 到第 5 个位置（`intArray02` 也是一个元素数组）。在复制操作前后分别打印 `intArray02` 的内容。



```java
import java.util.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        int[] intArray01 = new int[]{55,747,15000,89,2333};
        int[] intArray02 = new int[intArray01.length];
        //目标数组长度必须 >= 源长度
        System.arraycopy(intArray01,1,intArray02,2,3);
        // intArray01 的第 2 个元素在索引1
        // intArray02 的第 3 个元素在索引2
        // 复制了 3 个元素。
        System.out.printf("intArray02's contents are %d,%d,%d\n", intArray02[0],intArray02[1],intArray02[2]);
    }
}
```

提示：`System.arraycopy`

### 25. 使用 `Arrays.toString` 方法重写程序输出数组的内容。

```java
import java.util.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        int[] intArray01 = new int[]{55,747,15000,89,2333};
        int[] intArray02 = new int[intArray01.length];
        //目标数组长度必须 >= 源长度
        System.arraycopy(intArray01,0,intArray02,0,3); // 示例代码逻辑调整
        // intArray01 的第 2 个元素在索引1
        // intArray02 的第 3 个元素在索引2
        // 复制了 3 个元素。
        System.out.printf("intArray02's contents are %s\n", Arrays.toString(intArray02));
    }
}
```

### 26. 运行以下程序并说明你的观察。

```java
import java.util.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        int[] intArray01 = new int[]{55,747,15000,89,2333};
        int[] intArray02 = new int[intArray01.length];
        //目标数组长度必须 >= 源长度
        System.arraycopy(intArray01,0,intArray02,0,3);
        // intArray01 的第 2 个元素在索引1
        // intArray02 的第 3 个元素在索引2
        // 复制了 3 个元素。
        System.out.printf("intArray02's contents are %s\n", Arrays.toString(intArray02));
    }
}
```

### 27. 将数组缩短为 3 个元素：

```java
int[] intArray1 = new int[]{55,747,15000,89,2333};
```

打印 `intArray1` 的长度以证明其长度已修改。

```java
import java.util.*;
public class PracticeYour {
    public static void main(String[] args) {
        int[] intArray1 = new int[] {55,747,15000,89,2333};
        intArray1 = Arrays.copyOf(intArray1, 3);
        System.out.println("New length of intArray1 = " + intArray1.length);
    }
}
```

### 28. 增加长度将数组长度扩展到十个元素：

```java
int[] intArray1 = new int[] {55,747,15000,89,2333};
```

打印 `intArray1` 的长度以及内容。

提示：参考第 26 题的解决方案。

```java
import java.util.*;
public class PracticeYour {
    public static void main(String[] args) {
        int[] intArray1 = new int[] {55,747,15000,89,2333};
        System.out.printf("Current length of intArray1 = " + intArray1.length);
        intArray1 = Arrays.copyOf(intArray1, 10);
        // 注意源数组和目标数组是同一个
        System.out.println("New length of intArray1 = " + intArray1.length);
        System.out.printf("intArray1's contents are now %s\n", Arrays.toString(intArray1));
        // 注意额外的元素会被自动设置为该类型的默认值。
    }
}
```

# Java 级级练习

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[] intArray0 = new int[] {17,42,43,8,23};

        // We use an indirect method to extend the length of the array;
        intArray0 = Arrays.copyOf(intArray0, intArray0.length + 2);
        // So we give it the contents of intArray0 and told it to return the same data
        // in an array of length intArray0 + 2.

        // Now we put our data into the two new elements.
        intArray0[5] = 57;
        intArray0[6] = 84;
        System.out.printf("intArray0's length is %d\n", intArray0.length);
        System.out.printf("intArray0's contents are %s\n", Arrays.toString(intArray0));
    }
}
```

### 30. 缩短数组长度/减少数组容量

我们有如下数组：`int[] intArray1 = new int[] {55, 74, 15000, 89, 2333};` 通过程序手段修改该数组为：`int[] intArray1 = new int[] {15000, 89, 2333};` 打印数组的新长度及其内容。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[] intArray0 = new int[] {55, 74, 15000, 89, 2333};
        int startIndex = 0;
        int finalIndex = intArray0.length / 2;
        intArray0 = Arrays.copyOfRange(intArray0, startIndex, finalIndex);
        System.out.printf("New length of intArray0 = %d\n", intArray0.length);
        System.out.printf("intArray0's contents are %s\n", Arrays.toString(intArray0));
    }
}
```

### 31. 我们已经看到，当数组被创建但未初始化时，它会被填充为该类型的默认值。例如，int 类型会被填充为值 0。然而，某些情况下 0 对我们来说是一个有效数据点，我们无法判断是我们将特定条目设置为了 0，还是它作为任何数组元素的默认值。在这种情况下，解决此问题最简单的方法是将数组中的元素设置为一个对我们来说不是有效数据点、或者我们无法区分的值。例如，我们可能希望将条目的默认值设置为 -1。

提示：`Arrays.fill`

解决方案是使用 `Arrays.fill` 方法用所需的标记位填充整个数组。

### 32. 创建一个长度为 5 的数组，并将它的每个元素初始化为 -1。之后打印该数组。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[] intArray0 = new int[5];
        Arrays.fill(intArray0, -1);
        System.out.printf("intArray0's contents are %s\n", Arrays.toString(intArray0));
    }
}
```

### 33. 排序以下数组并打印其内容：`int[] intArray0 = new int[] {55, 74, 15000, 89, 2333};`

提示：`java.util.*`

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[] intArray0 = new int[] {55, 74, 15000, 89, 2333};
        Arrays.sort(intArray0);
        System.out.printf("intArray0's contents are %s\n", Arrays.toString(intArray0));
    }
}
```

### 34. 重复上面的例子，这次使用 `parallelSort` 方法。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[] intArray1 = new int[] {55, 74, 15000, 89, 2333};
        Arrays.parallelSort(intArray1);
        System.out.printf("intArray1's contents are now %s\n", Arrays.toString(intArray1));
    }
}
```

### 35. 简要解释 `parallelSort` 和 `sort` 之间的区别。

这两个方法的区别在于 `parallelSort` 设计用于使用多线程进行排序。在多核或多线程处理器上，`parallelSort` 的结果应该比 `sort` 快。

### 36. 使用 `binarySearch` 方法确定在前述例子的排序数组中，哪个元素包含值 74。（`binarySearch` 仅适用于已排序的数组）。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[] intArray2 = new int[] {55, 74, 15000, 89, 2333};
        Arrays.sort(intArray2);
        int valueToSearch = 74;
        int position = Arrays.binarySearch(intArray2, valueToSearch);
        if (position >= 0) {
            System.out.printf("The value %d was found at position %d\n", valueToSearch, position);
        }
    }
}
```

### 37. 我有如下对象：`String s01 = "Hello you?";` 将其转换为字节数组。说明数组中有多少个元素。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        String s01 = "Hello you?";
        byte[] strByteArray = s01.getBytes();
        System.out.printf("The length of the byte array is %d\n", strByteArray.length);
    }
}
```

**重要：** 转换是在你运行程序的系统默认字符集中进行的，但你应该注意这一点，因为指定的字符集会影响字符串转换后的字节数。

## 38. 矩阵/多维数组

### 38. 写一行代码声明一个名为 `matrixA` 的 2x3 维二维整数矩阵（即 2 行 3 列）。

```java
int[][] matrixA = new int[2][3];
```

### 40. 编写适当的代码声明一个名为 `matrixB` 的五维整数数组。

```java
int[][][][] matrixB;
```

### 41. 写一行代码实例化一个维度为 10x4x5x12 的五维整数矩阵 `matrixB`。

```java
int[][][][] matrixB = new int[10][4][3][5][12];
```

### 42. 分别实例化 2x3 的矩阵，名为 `matrix1` 和 `matrix2` 并初始化它们：

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[][] matrix1 = new int[2][3];
        matrix1[0][0] = 1; matrix1[0][1] = 2; matrix1[0][2] = 3;
        matrix1[1][0] = 4; matrix1[1][1] = 5; matrix1[1][2] = 6;

        int[][] matrix2 = new int[2][3];
        matrix2[0][0] = 5; matrix2[0][1] = 5; matrix2[0][2] = 8;
    }
}
```

紧凑形式：

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int[][] matrix1 = new int[][]{ {1, 2, 3}, {4, 5, 6} };
        int[][] matrix2 = new int[][]{ {5, 5, 8}, {3, 1, 3} };
        // 注意数据是按行输入的，
        // 每行用逗号分隔。
    }
}
```

### 43. 将上一个练习中数组的内容相加，并将结果放入一个新的矩阵 `matrix3` 中。



```java
public class PracticeJava {
    public static void main(String[] args) {
        int[][] matrix1 = new int[][]{ {1, 2, 3 }, {4, 5, 6} };
        int[][] matrix2 = new int[][]{ {5, 5, 8 }, {3, 1, 3} };

        int[][] matrix3 = new int[2][3];
        matrix3[0][0] = matrix1[0][0] + matrix2[0][0];
        matrix3[0][1] = matrix1[0][1] + matrix2[0][1];
        matrix3[0][2] = matrix1[0][2] + matrix2[0][2];
        matrix3[1][0] = matrix1[1][0] + matrix2[1][0];
        matrix3[1][1] = matrix1[1][1] + matrix2[1][1];
        matrix3[1][2] = matrix1[1][2] + matrix2[1][2];
    }
}
```

# 练习你的 Java 级1

```java
{
}
}
```

## for 循环

5. 使用下面的示例代码解释 `for` 循环的组成部分及其工作原理：

```java
int loopCounter;
for(loopCounter=3; loopCounter < 10; loopCounter++)
{
    // 执行操作
}
```

一个 `for` 循环的控制部分由以下元素组成：

1. 关键字 `for`，括号内的其他控制元素在括号内用分号分隔。
2. 其他控制元素在括号内用分号分隔。

在括号内中，我们按照以下顺序拥有：

1. 一个语句，指示 `for` 循环的控制变量并指定其初始值。在上面的示例中，我们看到名为 `loopCounter` 的循环计数器初始值为 3。注意，控制变量的初始化并不总是在 `for` 的控制部分完成，在某些情况下，`for` 循环的初始化部分将留空。
2. 一个条件语句，规定条件为真时允许 `for` 循环继续运行。在我们的示例中，我们说“只要变量 `loopCounter` 小于 10，就保持执行循环”。
3. 最后是一个递增语句，它指示在 `for` 循环语句中本应执行的操作后，加到循环计数器上的增量值。在我们的示例中，我们指定循环计数器 `loopCounter` 应该加 1。

`for` 循环的主体在此示例所示：

```java
{
    // 执行操作
}
```

这些大括号紧随 `for` 循环之后，包裹了每次 `for` 循环迭代要运行的代码。

从某种意义上说，Java 中的 `for` 循环是一个封装过的 `while`。因为它的条件语句说是“当此条件为真时，继续循环”。

### 注意事项

1. 如果你只想在 `for` 循环的每次迭代中执行一行代码，则不需要对这单行代码加上大括号。例如我们会写：

```java
int loopCounter;
for(loopCounter=3; loopCounter < 10; loopCounter++)
单行操作语句。
```

2. 循环计数器可以直接声明在 `for` 循环的控制部分。例如我们写道：

```java
for(int loopCounter = 0; loopCounter < 20; loopCounter++)
{
    // 执行操作
}
```

在控制部分声明的变量的作用域限于 `for` 循环本身的作用域。

3. 另一个需要注意的点是，循环控制组件的任何（或全部）缺失是可以接受的！只有控制语句中的两个分号是强制性的。

6. 预测以下 `for` 循环的输出。

```java
public class PracticeJava {
    public static void main(String[] args) {
    for (int loopCounter = 0; loopCounter < 5; loopCounter = loopCounter + 1) {
        System.out.println("Hello!");
    }
}
}
```

输出：

Hello!

Hello!

Hello!

Hello!

Hello!

7. 编写一个程序，使用 `for` 循环输出值 2 到 10。

```java
public class PracticeJava {
    public static void main(String[] args) {
    for (int i = 2; i < 11; i++) {
        System.out.println(i);
    }
}
```

8. 以下两个循环代码示例之间有什么区别？

```java
int i;
for (i=0; i<10; i++) {
    System.out.println(i);
}
vs.
for (int i=0; i<10; i++) {
    System.out.println(i);
}
```

循环之间的区别在于第二个代码片段，循环控制变量被定义在循环的控制结构内部。这两个循环在功能上是等价的。注意在第二个代码示例中，循环控制变量的生命周期在 `for` 循环结束时结束，因为它定义在循环的控制结构内部。

9. 以下两个循环代码示例之间有什么区别？

```java
int i;
for (i=0; i<10; i++) {
    System.out.println(i);
}
vs.
for (int i=0; i<10; i++) {
    System.out.println(i);
}
```

循环之间的区别在于第二个代码片段，循环控制变量在循环控制结构之外/之前进行了初始化。否则，循环在功能上是完全等价的。

10. 以下两个循环代码示例之间有什么区别？

```java
for (int i=0; i<10; i++) {
    System.out.println(i);
}
vs.
for (int i=0; i<10; ) {
    System.out.println(i);
    i++;
}
```

循环之间的区别在于第二个代码片段，循环变量在代码块内部递增，而不是在控制部分。否则，循环在功能上是完全等价的。

11. 预测以下代码段的输出：

```java
for (int i=0; i<3; i++) {
    System.out.println(i);
    System.out.println("hello");
}
```

输出是：

0

1

2

hello

# 练习你的 Java 级1

| 问题 | 答案 |
| :--- | :--- |
| 12. 预测并解释以下代码段的输出：`for(int i=0;i<10;i++);` | 如果 `for` 循环后面的代码行没有大括号，则只有紧随 `for` 循环的第一行代码被视为循环的主体。尽管没有任何输出，但代码是有效的。注意语句末尾的分号。 |
| 13. 预测此代码的输出：`public class PracticeYourJava { public static void main(String[] args) { for(int j=0; j < 10; j++) { System.out.println("Hello"); } }` | 它会打印 "Hello" 单词 10 次。通常我们是这样写 `for` 循环的：`for(int j=0; j < 10; j++) System.out.println("Hello");`。然而，练习中显示的紧凑形式表明我们可以在循环控制部分的递增部分执行操作，这也是有效的（尽管这可能被认为可读性较低）。 |
| 14. 我们有以下数组定义：`int[] intArray01 = new int[18, 42, 26, 44, 55];`。使用 `for` 循环打印此数组包含的值，格式如下：`intArray01[index] = <value>` | ```java
public class PracticeYourJava {
    public static void main(String[] args) {
int[] intArray01 = new int[] {18, 42, 26, 44, 55};
int counter;
for (int counter = 0; counter < intArray01.length; counter++) {
System.out.printf("intArray01[%d] = %d\n", counter, intArray01[counter]);
}
}
``` |
| 14. | Java 中 `for` 循环的说明/解释：实际上，`for` 循环可以被认为是是结构的 `while` 循环（使用上面的答案作为示例）：`counter=0; while(counter < intArray01.length) { System.out.printf("intArray01[%d] = %d\n", counter, intArray01[counter]); counter++; }` |
| 14. | 如果 `for` 循环后面的代码行没有大括号，只有紧随 `for` 循环的第一行代码被视为循环的主体。 |
| 15. | 使用 `for` 循环以相同的格式反向打印数组。提示：递减计数器 |
| 16. | 使用循环为 15 个元素的数组填充 0 到 50000 之间的随机整数。 |

# 第 8 章：迭代/循环

```java
public class PracticeJava {
    public static void main(String[] args) {
        int numElements = 15;
        int[] array01 = new int[numElements];
        for(int i=0;i<array01.length;i++)
            array01[i] = (int)(Math.random() * 50000);

        int counter=0;
        while(counter < numElements) {
            System.out.printf("intArray01[%d] = %d\n", counter, array01[counter]);
            counter++;
        }
    }
}
```

## 增强型循环

```java
public class PracticeJava {
    public static void main(String[] args) {
        int[] array01 = new int[] {18, 42, 26, 44, 55 };
        for(int item : array01) {
            System.out.println(item);
        }
    }
}
```

# 练习你的第 1

```java
for(int item : intArray) {
  if (index % 2 == 0) {
    System.out.printf("intArray[%d] = %d\n", index, item);
  }
  index += 1;
}
```

解释：再次，从增强 `for` 循环语句的本质来看，在这种场景下，它并不像使用其他任何循环结构那样顺手。

20. 重复之前的练习，这次使用循环结构。

```java
public class PracticeJava {
  public static void main(String[] args) {
    int[] intArray01 = new int[] { 18, 42, 26, 44, 55 };
    for (int j = 0; j < intArray01.length; j++) {
      System.out.printf("intArray01[%d] = %d\n", j, intArray01[j]);
    }
  }
}
```

注意：重复循环是如何递增 2 的，以实现每隔 2 个条目的指定输出效果。

21. 使用 `while` 循环重复之前的练习。

```java
public class PracticeJava {
  public static void main(String[] args) {
    int[] intArray01 = new int[] { 18, 42, 26, 44, 55 };
    int counter = 0; // 我们将从第 0 个索引开始。
    int length = intArray01.length;
    while (counter < intArray01.length) {
      System.out.printf("intArray01[%d] = %d\n", counter, intArray01[counter]);
      counter += 2;
    }
  }
}
```

## do/while 循环

22. 当你有某些在检查循环条件之前必须运行一次的内容时。将此循环想为：你必须先执行它，然后为潜在的后续操作检查条件。

23. 编写一个使用 `do/while` 循环打印 1 到 10 的程序。

```java
public class PracticeJava {
  public static void main(String[] args) {
    int index = 1;
    do {
      System.out.println(index);
      index++;
    } while (index <= 10);
  }
}
```

24. 使用 `do/while` 循环计算并打印 10 的阶乘。

```java
public class PracticeJava {
  public static void main(String[] args) {
    int nToCalculateFactorial = 10;
    long result = 1;
    int index = 1;
    do {
      result = result * index;
      index++;
    } while (index <= nToCalculateFactorial);
    System.out.printf("%d = %d\n", index, result);
  }
}
```

25. 使用无限 `while` 循环打印字符串：“Hello!”

注意：记住，`while` 循环在控制语句求值为布尔值 `true` 时会运行。因此，我们需要直接将布尔值放入循环中。

```java
public class PracticeJava {
    public static void main(String[] args) {
        while (true) {
            System.out.println("Hello!");
        }
    }
}
```

26. 使用无限 `for` 循环重复之前的练习。

```java
public class PracticeJava {
    public static void main(String[] args) {
        for ( ; ) {
            System.out.println("Hello!");
        }
    }
}
```

## 嵌套循环

27. 预测以下代码的输出：

```java
public class PracticeJava {
    public static void main(String[] args) {
        int j, k;
        for (j = 1; j < 5; j++) {
            for (k = 1; k < 5; k++) {
                System.out.printf("%d,%d ", j, k);
            }
            System.out.println();
        }
    }
}
```

输出：

1,1 1,2 1,3 1,4 

2,1 2,2 2,3 2,4 

3,1 3,2 3,3 3,4 

4,1 4,2 4,3 4,4 

注意：此练习的目标是使用嵌套循环输出矩阵。

28. 编写一个程序，输出如下的模式：

A,1 A,2 A,3 A,4 

B,1 B,2 B,3 B,4 

C,1 C,2 C,3 C,4 

D,1 D,2 D,3 D,4 

E,1 E,2 E,3 E,4 

```java
public class PracticeJava {
    public static void main(String[] args) {
        int j, k;
        String[] letters = {"A", "B", "C", "D", "E"};
        for (j = 0; j < letters.length; j++) {
            for (k = 1; k < 5; k++) {
                System.out.printf("%s,%d ", letters[j], k);
            }
            System.out.println();
        }
    }
}
```

或者使用字符数组：



```java
public class PracticeJava {
  public static void main(String[] args) {
    int j, k;
    int start = 'A';
    char[] letters = {'A', 'B', 'C', 'D', 'E'};
    for (j = start; j < (start + 5); j++) {
        for (k = 1; k < 5; k++) {
            System.out.printf("%c,%d ", (char)j, k);
        }
        System.out.println();
    }
}
```

# 练习 Java 第 1

## 关键字 continue 和 break 以及标签的使用

- 29. 编写一个 for 循环，顺序打印 0 到 1000 的值，当循环计数器值为 10 时使用 break 语句停止循环。

```java
public class PracticeJava {
  public static void main(String[] args) {
    for (int i = 0; i < 1000; i++) {
        if (i == 10) break;
        System.out.println(i);
    }
  }
}
```

- 30. continue 运算符是做什么的？

`continue` 运算符出现在循环中时，会让代码立即回到循环开头。

```java
public class PracticeJava {
  public static void main(String[] args) {
    for (int i = 0; i < 50; i++) {
        if (i % 5 == 0) continue;
        System.out.println(i);
    }
  }
}
```

- 31. 编写一个从 1 到 50 的 for 循环，使用 continue 语句跳过每个被 5 整除的数值。

- 32. Java 中的标签是什么？如何使用？

标签放在代码块的开头并以冒号结束。标签的命名规范可以是任何有效的标识符（即任何有效的变量名）。你可以在代码的任何位置使用标签。

- 33. 描述标签 break（labeled break）语句的功能。

标签 break 语句允许你从给定的代码块跳转到带有标签的块的结尾。标签 break 的用法如下：

```java
break label;
```

标签 break 语句的好处是允许根据需要按非顺序移动代码。此外请注意 break 语句不仅用于循环，也可以用于任何其他代码。可以运行下面的短示例来观察标签 break 语句的功能。

```java
import java.util.*;
public class PracticeJava {
  public static void main(String[] args) {
    label:
    System.out.println("1");
  }
}
```

# 第 8 章：迭代

当运行此代码时，输出如下：

1

注意 for 循环（例如）被视为块。

- 34. 我想输出如下模式：

```text
A1 A2 A3 A4 A5 A6 A7 A8 A9 A10
B1 B2 B3 B4 B5 B6 B7 B8 B9 B10
C1 C2 C3 C4
D1 D2 D3 D4 D5 D6 D7 D8 D9
E1 E2 E3 E4 E5 E6 E7 E8 E9 E10
```

编写一个循环来实现此。

提示：在看到 C5 时在循环中使用 break 语句。此解决方案不需要循环。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String[] sArray01 = {"A", "B", "C", "D", "E"};
        for (int i = 0; i < sArray01.length; i++) {
            for (int j = 1; j < 10; j++) {
                String sf01 = String.format("%s%d", sArray01[i], j);
                if (sf01.equals("C5") == true) break;
                System.out.print(sf01);System.out.print(" ");
            }
        }
    }
}
```

- 35. 描述循环上下文中 break（非标签 break）的用途。

循环中的 break 语句会导致循环立即停止处理，并将控制转移到循环后的语句。

- 36. 我想输出如下模式：

```text
A1 A2 A3 A4 A5 A6 A7 A8 A9 A10
B1 B2 B3 B4 B5 B6 B7 B8 B9 B10
C1 C2 C3 C4
D1 D2 D3 D4 D5 D6 D7 D8 D9
E1 E2 E3 E4 E5 E6 E7 E8 E9 E10
```

编写一个循环来实现此。

提示：在看到 C5 时在循环中使用 break 语句。此解决方案不需要循环。

```java
public class PracticeJava {
    public static void main(String[] args) {
        String[] sArray01 = {"A", "B", "C", "D", "E"};
        for (int i = 0; i < sArray01.length; i++) {
            for (int j = 1; j < 10; j++) {
                String sf01 = String.format("%s%d", sArray01[i], j);
                if (sf01.equals("C5") == true) break;
                System.out.print(sf01);System.out.print(" ");
            }
        }
    }
}
```

# 练习 Java 级

```java
System.out.println(); // break 语句跳转到此行
}
```

37. 编写一个程序，使用循环将两个 2x3 矩阵相加，并以相同的 2x3 格式输出结果。

```text
1 2 3
4 5 6
5 8 8
```

38. 使用包含以下元素的数组：

```text
0 0
oo oo
000 000
0000 0000
000000 000000
00000000 000000000
000000000 000000000
0000000000 0000000000
0000000000 00000000000
```

提示：使用 `String.format` 来构建字符串以及输出。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        String[] patternArray = new String[] {"o", "oo", "000", "oooo", "oooooo", "ooooooo", "00000000", "00000000"};

        int maxLength = 0;
        for (String s : patternArray) {
            if (s.length() > maxLength) maxLength = s.length();
        }

        int fieldWidth = maxLength;
        for (int i = 0; i < patternArray.length; i++) {
            String formatStr = "-%" + fieldWidth + "s" + " " + "%%" + fieldWidth + "s";
            String outputStr = String.format(formatStr, patternArray[i], patternArray[i]);
            System.out.println(outputStr);
        }

        // 模式的下部分
        for (int i = (patternArray.length - 2); i >= 0; i--) {
            String formatStr = "-%" + fieldWidth + "s" + " " + "%%" + fieldWidth + "s";
            String outputStr = String.format(formatStr, patternArray[i], patternArray[i]);
            System.out.println(outputStr);
        }
    }
}
```

E1 使用与上一个练习相同的源模式，编写代码输出以下模式：

```text
o
oo  oo
ooo  ooo
ooooo  oooo
00000 00000
000000 000000
0000000 0000000
00000000 00000000
```

E2 使用与上方相同的源模式，编写代码输出以下模式：

```text
o  000000
ooo  000000
ooo  000000
ooooo  00000
oooooo  000
000000  oo
0000000
00000000
```

E3 我有一个字符串数组，其中每个字符串的长度不确定。

写该字符串数组，每个字符串的宽度相同，并用字符 '|' 包围字符串的左右。

提示：确定最长字符串的长度。这将是你的字段宽度。然后使用 `String.format` 适当输出每行。

# 第 9 章 数字处理 II – 数值包装类

正如“数字处理 I”章节中所述，数值基本类型有对应的包装类（`Integer`, `Float`, `Byte`, `Short`, `Long` 和 `Double`）；我们在该章节中使用了一些来自包装类的常量。本章介绍了侧重于数值包装类的练习。

数值包装类的功能大部分分为以下几类：

- 尊重各自基本类型的常量（在章节 I 中见过）
- 在基本类型与其包装类之间转换的方法和手段（装箱）
- 模拟基本类型功能的方法
- 为各自基本类型提供额外功能的方法

应该理解的是，包装类并没有提供基本类型的完整功能，但可能会提供新的功能。尽管如此，为了精通 Java，必须熟悉基本类型及其包装类。

考虑到基本类型与其包装类之间的自然关系，我们在本章中还将看到更多关于基本类型自动装箱/拆装箱的练习。

这是书中关于 Java 数字处理的第二个章节。

| 以下基本类型的对应包装类：`byte`, `short`, `int`, `float`, `double`. | 包装类分别是：`Byte`, `Short`, `Integer`, `Long` 和 `Double`. |
|---|---|

| 1. | 编写一个程序，实例化一个值为 5 的 `Integer` 类对象。使用 **new** 操作。 | ```java
public class PracticeJava {
    public static void main(String[] args) {
        Integer i = new Integer(5);
    }
}
``` |

| 2. | 我有一个值为5 的 `int k`。使用 **k** 作为参数实例化 `Integer` 类对象。 | ```java
public class PracticeJava {
    public static void main(String[] args) {
        int k = 5;
        Integer int0 = new Integer(k);
    }
}
``` |

| 3. | 什么是装箱（boxing）？装箱的概念是在 Java 中使用基本类型作为参数来创建等效包装类。例如，如果我们将值为 100 的 `int` **j** 赋值给 `Integer` 类对象，代码如下：```java
int j = 100;
Integer boxedEquivalent = new Integer(j);
```我们在上一个练习中见过这个；它的正式名称是 *boxing*。 | |

| 4. | 什么是自动装箱（auto-boxing）？自动装箱是装箱的自动化版本。自动装箱是 Java 的一种无需使用标准对象创建语法（即使用 **new** 关键字）通过赋值基本值来创建包装类对象的功能。例如，如果我们把 `int j` 表示为 `Integer` 对象，代码如下：```java
Integer boxedEquivalent = j;
``` | |

# 练习 Java 级

编译器处理后台细节。

将此情况与使用装箱的情况进行对比。

该功能从 Java 1.5 版本开始提供。

什么是拆箱（unboxing）？

拆箱是你显式地通过类型转换将装箱类型转换回其基本类型的方法。如果我们想将值为 100 的 `Integer` 对象 `obj1` 转换为 `int k`，代码如下：

```java
Integer obj1 = new Integer(100);
int k = (int)obj1;
```

什么是自动拆箱（auto-unboxing）？

（这是拆箱的自动化版本）。自动拆箱是 Java 的一种通过使用赋值运算符将包装类对象转换为其基本值的功能。例如，如果我们有一个 `Integer obj1` 并且想将其内容放入类型为 `int` 的类型 `k` 中，我们需要这样做：

```java
int k = obj1;
```

编译器处理任何细节。

为什么（见下方）是实例化 `Integer` 类对象的有效方式而不是 new 运算符？

```java
Integer obj1 = 500;
```

使用自动装箱代替 new 运算符重写练习 3 的解。

使用 `Integer` 对象代替 `int` 重写以下程序。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int i = 753;
        byte b = (byte)i;
    }
}
```

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int i = 5;
        Integer obj1 = 1; //自动装箱
    }
}
```

```java
import java.util.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        int i = 753;
        byte b = (byte)i;
    }
}
```

提示：`Integer.valueOf`

对于上一个练习的解，解释为什么以下代码行保持了 i 是 `Integer` 对象：`b = i.valueOf();` 和 `b = (byte)((int));`

这些代码行是等价的（引用第二行），通过拆箱，我们可以将 `Integer` 对象转换为其对应的基本类型（`int`）。在获得 `int` 后，通过普通转换我们可以将其转换为任何选择的字节类型。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        Integer i = 753;
        b = (byte)((int));
    }
}
```

使用自动装箱重写练习 10 的解。

对于上一个练习中的 `Integer` 对象 i，解释为什么这种尝试的转换是非法的：`b = (byte)i;`

该转换是非法的，因为自动装箱和自动拆箱只在给定的基本类型变量与其自身的包装类之间直接转换。

使用 `Integer` 对象重写以下程序。

代替 `int`。不要使用强制类型转换或任何类型的装箱（boxing）来实现所需的结果。

```java
import java.util.*;
public class PracticeJava {
  public static void main(String[] args) {
    int i = 753;
    short k = (short)i;
  }
}
```

```java
public static void main(String[] args) {
  Integer i = 753;
  short k = i.shortValue();
}
```

提示：`Integer.shortValue`

使用 `Integer` 对象代替 `int` 重写以下代码片段。

```java
int i = 49;
long k = (long)i;
```

```java
Integer i = 49;
long k = i.longValue();
```

提示：`Integer.longValue`

使用 `Integer` 对象代替 `int` 重写以下代码片段。

```java
int i = 49;
float f = (float)i;
```

```java
Integer i = 49;
float f = i.floatValue();
```

提示：`Integer.floatValue`

使用 `Integer` 对象代替 `int` 重写以下代码片段。

```java
int i = 275;
double k = (double)i;
```



# Java 练习

## 基础代码示例

```java
Integer i = 275;
double k = i.doubleValue();
```

提示：`Integer.doubleValue`

使用 `Integer` 对象代替变量 `int` 重写以下代码。

```java
int i = 500;
double k = i;
```

```java
Integer i = new Integer(500);
int k = i.intValue(); // 编译器自动装箱。
```

重写练习 17 的答案，利用拆箱（unboxing）和强制类型转换来实现相同的结果，使用方法 `Integer.doubleValue` 代替 `int`。

```java
import java.util.*;
public class PracticeJava {
  public static void main(String[] args) {
    int i = 752;
    System.out.printf("%d\n", i);
  }
}
```

```java
public class PracticeJava {
  public static void main(String[] args) {
    Integer i = 753;
    System.out.printf("%d\n", i);
    // 对象将自动装箱
  }
}
```

使用 `Integer` 对象代替基本类型重写以下代码。

```java
import java.util.*;
public class PracticeJava {
  public static void main(String[] args) {
    int j = 753;
    int k = j; // 将 k 设置为 j 的值。
    k++;
    System.out.printf("%d\n", j);
    System.out.printf("%d\n", k); // 现在是 754
  }
}
```

```java
public class PracticeJava {
  public static void main(String[] args) {
    Integer j = 753;
    Integer k = j;
    k++;
    System.out.printf("%d\n", j);
    System.out.printf("%d\n", k);
  }
}
```

## Java 练习 1

### 22. 使用 `Integer` 作为控制变量代替 `int` 重写循环。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int j;
        for (j = 0; j < 5; j++) {
            System.out.println("Hello!");
        }
    }
}
```

```java
public class PracticeJava {
    public static void main(String[] args) {
        Integer j = new Integer(0);
        for (j < 5; j++) {
            System.out.println("Hello!");
        }
    }
}
```

注意：在本次练习中它将是一个对象，因为处理基本类型需要更长时间。

### 23. 使用 `Integer` 对象和方法 `Integer.compareTo` 代替基本类型重写以下代码。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        int h = 5, j = 7;
        if (h > j) {
            System.out.println("h > j");
        }
        if (h < j) {
            System.out.println("h < j");
        }
        if (h == j) {
            System.out.println("h = j");
        }
    }
}
```

```java
public class PracticeJava {
    public static void main(String[] args) {
        Integer h = 5, j = 7;
        if (h.compareTo(j) == 1) {
            System.out.println("h > j");
        }
        if (h.compareTo(j) == -1) {
            System.out.println("h < j");
        }
        if (h.compareTo(j) == 0) {
            System.out.println("h = j");
        }
    }
}
```

### 24. 使用自动装箱（auto-boxing）重写上一个练习的答案。

```java
public class PracticeJava {
    public static void main(String[] args) {
        Integer h = 5, j = 7;
        if (h > j) {
            System.out.println("h > j");
        }
        if (h < j) {
            System.out.println("h < j");
        }
        if (h == j) {
            System.out.println("h = j");
        }
    }
}
```

注意：从这个练习中可以明显看出通过自动装箱/拆箱机制，基本类型及其对应的类在许多情况下是可以互换的。自动装箱确实使得在 Java 自动装箱功能出现之前的许多包装类方法变得过时，例如 `Integer.compareTo` 方法。

### 25. 给定一个值为 86 的 `Integer` 对象 m，编写一个程序将该 `Integer` 对象持有的值加5。打印该 `Integer` 对象的值。

```java
public class PracticeJava {
    public static void main(String[] args) {
        Integer m = new Integer(86);
        m += 5;
        System.out.println(m);
    }
}
```

提示：`Integer.intValue()`

### 26. 在不自动装箱的情况下重做上一个练习。

```java
public class PracticeJava {
    public static void main(String[] args) {
        int m = 86;
        int result = m + 5;
        System.out.println(result);
    }
}
```

# 第9章：数字处理

确定以下两个值中的较小者：

```java
int x1 = 86;
Integer x2 = 92;
```

解释为什么基本类型及其包装类传递给需要对它们进行数学运算的 `min` 方法。

```java
public class PracticeJava {
    public static void main(String[] args) {
        int smaller = Integer.min(x1, x2);
        System.out.println(smaller);
    }
}
```

确定以下值中的较大者：

```java
Integer x1 = 86;
int x2 = 92;
```

```java
public class PracticeJava {
    public static void main(String[] args) {
        int larger = Integer.max(x1, x2);
        System.out.println(larger);
    }
}
```

# 练习你的 Java 水平

| 任务描述 | 提示 | 代码示例 |
| :--- | :--- | :--- |
| 32 我们有一个 7 进制的值 "100"，并以字符串的形式传给我们。将此字符串转换为其对应的 10 进制值并打印该 int。 | | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>    String s = "100";<br>    int numberBase = 7;<br>    int m = Integer.parseInt(s, numberBase);<br>    System.out.println(m);<br>}<br>}``` |
| 33. 给定一个值为 5 的 int m，将其转换为二进制等价值，并将结果存入 String。 | 提示：方法 `Integer.toBinaryString` | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>    int m = 5;<br>    String result = Integer.toBinaryString(m);<br>    System.out.println(result);<br>}<br>}``` |
| 35. 编写一个程序，使用方法 `Integer.toInt()`，将 int 转换为十六进制值 m = 74；确保输出中的字母大大写。 | | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>    int m = 74;<br>    String result = Integer.toHexString(m);<br>    result = result.toUpperCase();<br>    System.out.println(result);<br>}<br>}``` |
| 36. 编写一个程序，使用方法 `Integer.toString()`，将 int 转换为等价的 8 进制值 m = 74； | | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>    int m = 74;<br>    String result = Integer.toOctalString(m);<br>    System.out.println(result);<br>}<br>}``` |
| 37. 编写一个程序，计算并打印数字 227 的二进制表示中 "1" 位的数量。 | 提示：`Integer.bitCount`（此功能对于计算校验和有用） | ```java<br>public class PracticeYourJava {<br>    public static void main(String[] args) {<br>    int m = 227;<br>    int numBits = Integer.bitCount(m);<br>    System.out.println(numBits);<br>}<br>}``` |
| 38. 解释下面代码段输出的原因：`int y; Integer x = null; y=x;` | | 结果导致了以下异常：`java.lang.NullPointerException`。<br><br>异常的原因是 `Integer` 的值为 `null`，这意味着没有东西可以装箱为 `int`！在基本类型的语境下，值 `x` 是无意义的。<br><br>```java<br>int y;<br>Integer x = null;<br>if(x != null)<br>y=x;<br>``` |
| 39. 重写上一个练习中的代码段，以确保它不再触发异常。 | | |

# 第 2 章：数值处理 II

| 任务描述 | 描述 | 代码示例 |
| :--- | :--- | :--- |
| 40. 编写一个程序，实例化 `Float` 类对象，初始值为 27.53。使用 `new` 运算符和自动装箱（autoboxing）显示初始化。 | | ```java<br>public class PracticeJava {<br>    public static void main(String[] args) {<br>    Float f = new Float(27.53);<br>    // OR<br>    // Float f = 27.53;<br>}<br>}``` |
| 41. 给定一个值为 27.53 的 `Float`。编写一个程序显示将其赋值给以下每一个：`byte`, `short`, `int`, `long`, `double`。 | | ```java<br>public class PracticeJava {<br>    public static void main(String[] args) {<br>byte b = Float.byteValue(f);<br>short s = Float.valueOf(f);<br>int i = Float.intValue(f);<br>long l = Float.longValue(f);<br>double d = Float.doubleValue(f);<br>}<br>}``` |
| 42. 编写代码测试给定的 `float` 值是否为 `Float.NaN`。如果确实为 `Float.NaN`，则打印 "Yes is NaN"，否则打印 "it is not NaN"。 | 提示：`Float.isNaN(f)` | ```java<br>public class PracticeJava {<br>    public static void main(String[] args) {<br>    float f = Float.NaN; // 为了测试目的设置值<br>if(Float.isNaN(f))<br>    System.out.println("Yes is NaN!");<br>else<br>    System.out.println("it is not NaN");<br>}<br>}``` |
| 43. 编写代码测试给定的 `Float` 是否具有有限值。如果为有限的，则打印 "Yes it is"，否则打印 "it is not finite"。 | 提示：`Float.isFinite()` | ```java<br>public class PracticeJava {<br>    public static void main(String[] args) {<br>    float f = Float.NaN; // 根据测试目的设置所需值<br>if(Float.isFinite(f))<br>    System.out.println("Yes it is!");<br>else<br>    System.out.println("It is not finite");<br>}<br>}``` |
| 44. 编写代码测试给定的 `Float` 是否具有有限值。如果为有限的，则打印 "Yes it is"，否则打印 "it is not finite"。 | | ```java<br>public class PracticeJava {<br>    public static void main(String[] args) {<br>    float f = Float.POSITIVE_INFINITY; // 根据测试目的设置所需值<br>if(Float.isFinite(f))<br>    System.out.println("Yes it is!");<br>else<br>    System.out.println("It is not finite");<br>}<br>}``` |
| 45. 使用方法 `Float.parseDouble(String)` 并根据给定的对象 `s = "98.73"`，编写代码将此字符串转换为 `float`。 | | ```java<br>public class PracticeJava {<br>    public static void main(String[] args) {<br>    String s = "98.73";<br>float m = Float.parseDouble(s);<br>}<br>}``` |

数值包装类 `Short`、`Long` 和 `Double` 的差异与此处所示的 `Integer` 和 `Float` 相似。敦促读者阅读这些类。

# 第 10 章：Boolean 类

`Boolean` 类是基本类型 `boolean` 的包装类。由于 Java 中的某些功能不接受基本类型（例如集合，我们将在稍后的章节中看到），在这些情况下，`Boolean` 类清楚地代表了基本类型。`Boolean` 类提供了可以对基本类型执行相同的操作。

| 任务 | 描述 | 代码示例 |
| :--- | :--- | :--- |
| 40. 编写一个程序，实例化 `Float` 类对象，初始值为 27.53。使用 `new` 运算符和自动装箱显示初始化。 | | |
| (此处省略重复翻译，遵循上方逻辑) | | |

（接下文部分）

| 任务 | 描述 | 代码示例 |
| :--- | :--- | :--- |
| ... | | |

数值包装类 `Short`、`Long` 和 `Double` 的差异与此处所示的 `Integer` 和 `Float` 相似。敦促读者阅读这些类。



# 第 10 章：Boolean 类

`Boolean` 类是基本类型 `boolean` 的包装类。由于 Java 中的某些功能不接受基本类型（例如集合，我们将在稍后的章节中看到），在这些情况下，`Boolean` 类清楚地代表了基本类型。

计算并打印数字 227 的二进制表示中 "1" 位的数量。

- 提示：`Integer.bitCount()`（此功能对于计算校验和有用）

解释下面代码段输出的原因。结果导致了以下异常：`java.lang.NullPointerException`。异常的原因是 `Integer` 的值为 `null`，这意味着没有东西可以装箱为 `int`！在基本类型的语境下，值 `x` 是有意义的。

# 第 11 章：枚举 I

本章介绍了 Java 中枚举概念的练习。本章是书中介绍该主题的两个章节之一。

1. 什么是枚举 (`enum`) 以及它为什么有用？并展示一个名为 `Gender` 的简单枚举示例，包含 `MALE` 和 `FEMALE`。

在基本的形式中，Java 枚举（`enumeration` 的缩写）可以被描述为一种由程序员分配的有序字符串类型，在枚举语境下，每个“值”仅仅是它们的名称，但它们有一个顺序；这个顺序取决于它们被放入枚举的方式，第一个值具有最小的“顺序”，最后一个具有最大的顺序。（注意，尽管枚举的高级功能允许我们将任何类型的任意数量的值与代表枚举的字符串关联，我们将在第二章中看到）。

| 任务 | 描述 | 代码示例 |
| :--- | :--- | :--- |
| 重写上一个练习中的代码段，以确保它不再触发异常。 | | |
| 40. | 编写一个程序，实例化 `Float` 类对象，初始值为 27.53。使用 `new` 运算符和自动装箱显示初始化。 | ```java
public class PracticeJava {
    public static void main(String[] args) {
        Float f = new Float(27.53);
        // OR
        // Float f = 27.53;
    }
}
``` |
| 41. | 给定一个值为 27.53 的 `Float`。编写一个程序显示将其赋值给以下每一个：`byte`, `short`, `int`, `long`, `double`。 | ```java
public class PracticeJava {
    public static void main(String[] args) {
        Float f = 27.53f;
        byte b = f.byteValue();
        short s = f.shortValue();
        int i = f.intValue();
        long l = f.longValue();
        double d = f.doubleValue();
    }
}
``` |

## 练习你的 Java 11

2. 定义一个名为 `Gender` 的枚举，其取值顺序依次为 `MALE`、`FEMALE` 和 `OTHER`。

```java
enum Gender {
    MALE, FEMALE, OTHER;
}
```

3. 下列代码的输出是什么（在与上方定义的枚举 `Gender` 相同的包中编译）？

```java
class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println(Gender.MALE);
        System.out.println(Gender.FEMALE);
    }
}
```
输出：
```
MALE
FEMALE
```

4. 当你编译任何枚举时，该枚举创建了多少个对象？

系统为每个枚举条目创建一个对象；请记住，枚举是一种特殊的类，每个条目实际上都代表一个对象。

5. 当你编译先前的 `Gender` 枚举时，会自动创建多少个 `Gender` 类的对象（实际上枚举本质上是一个类定义）？

创建了两个对象：一个是 `Gender.MALE`，另一个是 `Gender.FEMALE`。

6. 这些对象是在何时创建的？

在初始化时。

7. 枚举的声明与赋值

在 `main` 方法中，将 `Gender.MALE` 的值赋给一个 `Gender` 类型变量。打印该变量。

```java
class PracticeYourJava {
    public static void main(String[] args) {
        Gender gender1 = Gender.MALE; // 注意我们不需要 "new" 关键字
        System.out.println(gender1);
    }
}
```
输出：`MALE`

8. 解释为什么在上述执行过程中，在将 `Gender.MALE` 赋值给变量 `gender1` 时不需要 `new` 关键字。

不需要 `new` 关键字的原因是系统已经创建了对象 `Gender.MALE`，而我们正在通过变量 `gender1` 引用它。

9. 使用方法 `<枚举名>.ordinal()`，编写一个程序，打印出先定义的 `Gender` 枚举中每个条目的位置。

```java
class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println(Gender.MALE.ordinal());
        System.out.println(Gender.FEMALE.ordinal());
    }
}
```
输出：`0` 和 `1`。

10. 使用方法 `<枚举名>.valueOf(String)`，打印赋值给 `Gender` 枚举中每个条目的值的值。

```java
class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println("the value of MALE = " + Gender.valueOf("MALE"));
        System.out.println("the value of FEMALE = " + Gender.valueOf("FEMALE"));
        // 有趣的是，使用的是 Gender 类的赋值变量。
    }
}
```
输出：分别为 `MALE` 和 `FEMALE`。
注释：Java 使用相关枚举的名称作为其值，除非另有选择。

11. 在 `Gender` 枚举中，交换条目 `MALE` 和 `FEMALE` 的位置，并重新运行练习 9 的解决方案代码。注释输出内容的差异。

该枚举现在如下：

```java
enum Gender {
    FEMALE,
    MALE;
}
```

输出：重新运行代码后，输出如下：分别为 `1` 和 `0`。注释：正如预期的，位置值与之前反转了。如果你的代码对相关枚举中元素的常量序数有特殊需求，请确保枚举中的元素顺序不会发生任何改变。

12. 定义一个枚举 `Day`；按顺序从星期日到星期六输入星期的几天。

```java
public enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}
```

13. 使用 `enum` 类的 `values()` 方法，使用增强型 for 循环遍历 `Day` 枚举，并打印它的每个元素及其对应的值。提示：`Day.values()`

```java
class PracticeYourJava {
    public static void main(String[] args) {
        for (Day day : Day.values()) {
            System.out.println(day + " : " + day.ordinal());
        }
    }
}
```

14. 编写一个程序，检查两个类型为 `Day` 的枚举值（练习 12 中定义的枚举）的顺序，并判断它们哪一个更早。如果它们相同，则显示 0。使用不同的日期组合测试你的代码。提示：使用枚举实例的 `compareTo` 方法来实现。

```java
public class PracticeJava {
    public static void main(String[] args) {
        Day day1 = Day.SUNDAY;
        Day day2 = Day.SATURDAY;
        if (day1.compareTo(day2) < 0) {
            System.out.println(day1 + " is before " + day2);
        } else if (day1.compareTo(day2) > 0) {
            System.out.println(day2 + " is before " + day1);
        } else {
            System.out.println("The same day was specified!");
        }
    }
}
```

显然，如果你编写的枚举中的元素顺序对你很重要，你必须确保枚举中元素的顺序永远不会改变，否则你的代码将受到影响。

15. 直接使用枚举值的 `ordinal` 来进行比较，重写前面的程序。

```java
public class PracticeJava {
    public static void main(String[] args) {
        Day day1 = Day.SUNDAY;
        Day day2 = Day.SATURDAY;
        if (day1.ordinal() < day2.ordinal()) {
            System.out.println(day1 + " is before " + day2);
        } else if (day1.ordinal() > day2.ordinal()) {
            System.out.println(day2 + " is before " + day1);
        } else {
            System.out.println("The same day was specified!");
        }
    }
}
```
注意：与 `compareTo` 方法一样，你必须确保枚举中条目的顺序永远不会改变，否则你的代码将受到影响。

16. 枚举与直接在类中定义常量有何区别？

枚举在以下方面与众不同：

1. 枚举对其所代表的元素有一个顺序，便于元素之间进行比较。
2. 枚举提供了一组定义清晰的有序项。
3. 枚举实际上是类对象。作为一个类，可以向枚举中添加方法、字段、接口和其他有效的类元素，以确保枚举类清晰地封装了与相关枚举的所有内容。

17. 我在公司里有不同的职位。创建一个名为 `Position` 的枚举：`Staff`, `Staff2`, `Staff3`, `Staff4`, `Manager`, `SeniorManager`, `Director`, `VicePresident` 和 `CEO`。

```java
enum Position {Staff, Staff2, Staff3, Staff4, Manager, SeniorManager, Director, VicePresident, CEO;}
```

18. 公司有 10 个薪资带。按顺序创建一个名为 `SalaryBand` 的枚举。薪资带被列为 `BAND1`...`BAND10`。

```java
enum SalaryBand {BAND1, BAND2, BAND3, BAND4, BAND5, BAND6, BAND7, BAND8, BAND9, BAND10}
```

19. 我有正式员工和合同工。创建一个名为 `EmploymentType` 的枚举来代表正式和合同。

```java
enum EmploymentType {PERMANENT, CONTRACTOR;}
```

20. 创建一个 `VehicleTypes` 枚举，支持以下车辆类型：自行车、摩托车、汽车、卡车、船、火车、飞机。

```java
enum VehicleTypes {BICYCLE, MOTORBIKE, CAR, TRUCK, BOAT, TRAIN, AIRPLANE;}
```

学习以下 Java 枚举：

1. `RoundingMode`
2. `Month`
3. `DayOfWeek`
4. `TextStyle`

# 第 12 章：数字处理 III – BigInteger & BigDecimal

本章是关于 Java 数字处理的第三部分。

## BigInteger

1. 解释 `BigInteger` 类的存在原因。

`BigInteger` 类是为了在 Java 中表示超出最大原始类型 `long` 范围的整数值。`long` 类型可以在运行 Java 的 CPU 上原生表示；任何超出范围的整数都通过软件实现的 `BigInteger`。

2. 创建一个程序来处理 `Long.MAX_VALUE` 的 `BigInteger` 对象。`BigInteger` 不能直接通过值初始化，而是通过值的字符串表示来初始化。因此，我们必须将 `Long.MAX_VALUE`（它是一个 `long`）转换为字符串。我们首先将其转换为 `Long` 对象，因为该对象允许将其转换为字符串。

```java
import java.math.*;

public class PracticeJava {
    public static void main(String[] args) {
        long long_max = Long.MAX_VALUE;
        BigInteger bigInt1 = new BigInteger(Long.toString(long_max));
        System.out.println(bigInt1);
    }
}
```

3. 增强上练习的解决方案，将变量 `bigInt1` 持有的值增加 5，然后打印结果。提示：`BigInteger`。`Integer` 只能与 `BigInteger` 对象直接相加（此 Java 版本不支持更小的类型），因此我们需要：(1) 将要加的原始数字转换为其包装类对象，(2) 使用其 `toString` 方法将该对象转换为字符串表示，然后 (3) 使用该字符串创建一个 `BigInteger` 对象，现在你将其与原始的 `BigInteger` 相加。这似乎有很多步骤，但其实并不多。开始吧！

```java
import java.math.*;

public class PracticeJava {
    public static void main(String[] args) {
        long long_max = Long.MAX_VALUE;
        int numberToAdd = 5;
        BigInteger bigInt1 = new BigInteger(Long.toString(long_max));
        BigInteger numberToAddBI = BigInteger.valueOf(numberToAdd);
        bigInt1 = bigInt1.add(numberToAddBI);
        System.out.println(bigInt1);
    }
}
```

简而言之，我们可以按照以下方式编写：

```java
import java.math.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        long longMax = Long.MAX_VALUE;
        int numberToAdd = 5;
        BigInteger bigint1 = new BigInteger(Long.toString(longMax));
        BigInteger bigint2 = bigint1.add(BigInteger.valueOf(numberToAdd));
        System.out.println(bigint1);
    }
}
```

4. 编写一个程序，打印整数 -79922337203685477680 的绝对值。提示：`BigInteger.abs()`

```java
import java.math.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        BigInteger bigint1 = new BigInteger("-79922337203685477680");
        System.out.println(bigint1.abs());
    }
}
```

5. 打印 9876543210987654321 的 `Integer.MAX_VALUE` 次方。打印结果。提示：`BigInteger.pow()`

```java
import java.math.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        BigInteger bigint1 = new BigInteger("9876543210987654321");
        BigInteger result = bigint1.pow(Integer.MAX_VALUE);
        System.out.println(result);
    }
}
```



# Java BigInteger 和 BigDecimal 练习

## 练习 6

将值 `855223372036854776234` 乘以 `9876543210987654321`，并将其放入不同的 `BigInteger` 类中。
按照以下格式打印结果：`Result of <value1> * <value2> = <result>`

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        BigInteger bigint1 = new BigInteger("855223372036854776234");
        BigInteger bigint2 = new BigInteger("9876543210987654321");
        BigInteger bigint3 = bigint1.multiply(bigint2);

        System.out.println(bigint1 + " * " + bigint2 + " = " + bigint3);
    }
}
```

## 练习 7

使用前一个练习中的数字，将第一个值除以第二个值，确定商和余数。
按照以下格式输出结果：`Result of <value1> / <value2> = <result> REM <remainder>`
提示：`BigInteger.divideAndRemainder()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        BigInteger bigInt01 = new BigInteger("855223372036854776234");
        BigInteger bigInt02 = new BigInteger("98765432109876543210");

        BigInteger[] result = bigInt01.divideAndRemainder(bigInt02);

        System.out.println(bigInt01 + " / " + bigInt02 + " = " + result[0] + " REM " + result[1]);
    }
}
```

## 练习 8

将练习中的第一个值除以第二个值，仅确定计算结果。
提示：`BigInteger.divide()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        BigInteger bigInt01 = new BigInteger("855223372036854776234");
        BigInteger bigInt02 = new BigInteger("98765432109876543210");

        BigInteger result = bigInt01.divide(bigInt02);

        System.out.println(bigInt01 + " / " + bigInt02 + " = " + result);
    }
}
```

## 练习 9

将练习中的第一个值除以第二个值，并仅打印计算的余数。
提示：`BigInteger.mod()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        BigInteger bigInt01 = new BigInteger("855223372036854776234");
        BigInteger bigInt02 = new BigInteger("98765432109876543210");

        BigInteger result = bigInt01.mod(bigInt02);

        System.out.println(bigInt01 + " mod " + bigInt02 + " = " + result);
    }
}
```

## 练习 10

找出并打印练习中两个数字的最大公约数。
提示：`BigInteger.gcd()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        BigInteger bigInt01 = new BigInteger("855223372036854776234");
        BigInteger bigInt02 = new BigInteger("98765432109876543210");

        BigInteger result = bigInt01.gcd(bigInt02);

        System.out.println(bigInt01 + " gcd " + bigInt02 + " = " + result);
    }
}
```

## 练习 11

我有一个十六进制字符串 `"FF1916A8AACBA70DEA148"`。打印它的十进制。
提示：`BigInteger(String, radix)`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        String hexString = "FF1916A8AACBA70DEA148";
        BigInteger bigInt01 = new BigInteger(hexString, 16);

        System.out.println("The equivalent decimal = " + bigInt01);
    }
}
```

## 练习 12

我有一个七进制数字。打印它的十进制。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        String numberString = "67";
        BigInteger bigInt01 = new BigInteger(numberString, 7);

        System.out.println("The equivalent decimal = " + bigInt01);
    }
}
```

## 练习 13

我有一个值为 57 的 `BigInteger`。将此值放入字节（基本类型）。
提示：`BigInteger.byteValue()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        String numberString = "77";
        BigInteger bigInt01 = new BigInteger(numberString);

        byte newByte = bigInt01.byteValue();
    }
}
```

## 练习 14

将前一个练习中的 `BigInteger` 值放入长整型（基本类型）。
提示：`BigInteger.longValue()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        String numberString = "77";
        BigInteger bigInt01 = new BigInteger(numberString);

        long newLong = bigInt01.longValue();
    }
}
```

## 练习 15

将前一个练习中的 `BigInteger` 值放入浮点数（基本类型）。
提示：`BigInteger.floatValue()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        BigInteger bigInt01 = new BigInteger("77");
        float newFloat = bigInt01.floatValue();
    }
}
```

## 练习 16

打印并注释尝试将值为 `"7755559999123143143"` 的 `BigInteger` 放入 `long` 变量时获得的值。打印收到的值。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        String numberString = "7755559999123143143";
        BigInteger bigInt01 = new BigInteger(numberString);

        long newLong = bigInt01.longValue();

        System.out.println(newLong);
    }
}
```

> **注**：`long` 的值与 `BigInteger` 值不匹配。放入 `long` 中的值是溢出的结果。
> **结论**：如果不需要发生下溢或溢出，请使用相应的 `BigInteger` 方法将值放入目标变量。

## 练习 17

尝试将值为 `"7755559999123143143"` 的 `BigInteger` 放入 `long` 变量。确保如果该值超过 `long` 的范围，则不将其放入。
提示：`BigInteger.longValueExact()`

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        String numberString = "7755559999123143143";
        BigInteger bigInt01 = new BigInteger(numberString);

        long newLong = bigInt01.longValueExact();

        System.out.println("long = " + newLong);
    }
}
```

**结果**：抛出异常 `java.lang.ArithmeticException`，因为该值超出了 `long` 的范围。

## 练习 18

我有两个十六进制数：`FFFF82312DFADE1234ED` 和 `ABCD3243256789909F`。对这些数字执行逻辑与运算，并以十进制、十六进制和二进制打印结果。确保十六进制数字大写。
提示：`BigInteger.toString(radix)`, `BigInteger`

```java
import java.math.*;

public class PracticeYour {

    public static void main(String[] args) {

        BigInteger bigInt01 = new BigInteger("FFFF82312DFADE1234ED", 16);
        BigInteger bigInt02 = new BigInteger("ABCD3243256789909F", 16);

        BigInteger bigInt03 = bigInt01.and(bigInt02);

        System.out.println("result (decimal): " + bigInt03.toString());
        System.out.println("result (hex): " + bigInt03.toString(16).toUpperCase());
        System.out.println("result (binary): " + bigInt03.toString(2));
    }
}
```

## 练习 19

为什么存在 `BigDecimal` 类？该类的存在是为了支持任意精度。对象的精度和舍入是确定的。

## 练习 20

请运行程序并注意每个 `BigDecimal` 的输出。代码将在练习中引用。

```java
import java.math.*;

public class PracticeYour {

    public static void main(String[] args) {

        BigInteger bigInt01 = new BigInteger((long)1570335L).toString();

        BigDecimal bd01 = new BigDecimal(bigInt01, 0);
        System.out.println(bd01);

        BigDecimal bd02 = new BigDecimal(bigInt01, 5);
        System.out.println(bd02);

        BigDecimal bd03 = new BigDecimal(bigInt01, 2);
        System.out.println(bd03);

        BigDecimal bd04 = new BigDecimal(bigInt01, -2);
        System.out.println(bd04);

        BigDecimal bd05 = new BigDecimal(bigInt01, -10);
        System.out.println(bd05);
    }
}
```



- 输出（分别）：
1. 1570335
2. 15703.35
3. 1570333
4. 1.570335E+6
5. 1.570335E+16

- 21. 解释初始化 `BigDecimal` 时“规模”（scale）的概念。使用前一个练习中的代码和输出作为解决方案中的参考示例。

理解 `BigDecimal` 用户可能希望以显著位/指数的形式表示数字。这本质上就是 `BigDecimal` 规模的概念的内容。因此，在 `BigDecimal` 的某些构造函数中提供了便利，以便以显著位和指数呈现所需的数字。

结果数字 = 显著位 x 10^指数
因此，如果输入的指数是正数，我们实际上是表示一个负指数，如果指数是一个负数，我们实际上是在表示一个正指数，因为在数学上 -- -- = +。这可以在上一个练习的输出中观察到，该输出根据以下逻辑产生了 `BigDecimal` 值：

- 没有指数 7 的条目，`BigDecimal` 值与输入的数字相同
- 正指数，5 -> 负指数；结果为 x = 10^5
- 正指数，2 -> 负指数；结果为 x = 10^-2
- 负指数，-2 -> 正指数，结果为 x = 10^(-2) = 10^-2
- 另一个负数输入，-10 -> 正指数，结果为 x = 10^-10

# 练习你的 Java 一级水平

## 22. 结合 `BigDecimal` 解释“精度”（precision）的概念。

`BigDecimal` 精度的概念，简单来说就是定义当前 `BigDecimal` 对象应该包含多少位数字。精度指的是整个数字整数部分和小数部分中有效数字的总数。例如，8.3 有两个有效数字，0.83 有两个数字，1.35 有三个数字，0.135 有三个有效数字。

## 23. 解释适用于 `BigDecimal` 类对象的“舍入模式”（rounding mode）的概念。

“舍入模式”的概念涉及到：当数字的有效数字多于我们期望的精度时，如何确定我们指定的该数字的最后一位数字。
读者可能已经熟悉一种特定的舍入模式；即“四舍五入”（rounding up），也就是说，如果任何大于或等于 5 的数字，都会导致其相邻的高位数字加 1。在 Java 中，`BigDecimal` 有八种舍入模式。

## 24. 列出并描述 `RoundingMode` 枚举中的所有八种舍入模式。你的示例应该描述精度（precision）为 2 时的正数和负数的舍入。

| 模式 (Mode) | 描述 | 示例 |
| :--- | :--- | :--- |
| CEILING | 将值舍入到最接近的正数。 | 8.73 -> 8.8。注意，尽管第二位小数的数字小于 5，但 CEILING 仍然会将数字向上移动。 |
| DOWN | 舍入到 0。这实际上意味着正数的值减小，负数的值增加！对于这一点，请将“零”看作是向下。 | 8.78 -> 8.7。注意，尽管第二位小数的数字大于 5，DOWN 仍然会将数字向 0 移动。-8.78 -> -8.7 如所述向 0 移动！ |
| FLOOR | 根据指定的精度将值舍入到最近的较低值。 | 8.78 -> 8.7。注意，尽管第二位小数的数字大于 5，对于正值，FLOOR 会截断数字。-8.73 -> -8.8。注意，尽管第二位小数的数字小于 5，FLOOR 也会将其向下移动。 |
| HALF_DOWN | 根据指定的精度舍入到最近的邻居。值 5 被视为要舍入数字的低半部分。值被分为两个舍入组：1-5 和 6-9。与 HALF_UP 相对比。将“down”理解为“向更小的数字”。 | 8.75 -> 8.8<br>8.75 -> 8.7<br>-8.77 -> -8.7<br>-8.75 -> -8.7<br>注意正数和负数处理 5 时的差异。有趣的是，负数时它不是向更小的数字移动。 |
| HALF_EVEN | 根据指定的精度舍入到最近的邻居，但正中间的数字（即以 5 结尾的）将舍入到最近的偶数。 | 8.75 -> 8.8 \| 8.74 -> 8.7 \| 8.77 -> 8.8 \| 8.75 -> 8.8 |
| HALF_UP | 根据指定的精度向最近的邻居舍入。值 5 向上舍入（考虑“更高的数字”）。注意：这对应于普通的舍入机制。 | 8.74 -> 8.8 \| 8.75 -> 8.8 \| 8.78 -> 8.8 \| 8.74 -> 8.7 \| 8.77 -> 8.8 \| 8.75 -> 8.8 |
| UP | 意味着始终舍入到下一个更高的数字。这对于正数和负数同样成立。 | 8.71 -> 8.8 \| 8.74 -> 8.8 \| 8.75 -> 8.8 \| 8.78 -> 8.8 \| 8.73 -> 8.8 \| 8.74 -> 8.8 \| 8.77 -> 8.8 |
| UNNECESSARY | 意味着“不要尝试舍入该数字，程序员将始终确保它具有正确的精度”。其含义是，如果你有一个精度不符的数字，将会生成异常。 | |

## 25. 解释 `MathContext` 对象的概念。

`MathContext` 对象是 `BigDecimal` 的配置对象。它在单个对象中方便了指定有效数字（精度）和应用于 `BigDecimal` 的舍入机制。`MathContext` 被作为变量传递给 `BigDecimal` 的构造函数。

## 26. 解释以下语句：`MathContext mc = new MathContext(4, RoundingMode.HALF_UP);`

该语句创建了一个 `MathContext` 对象，指定了精度为 4 以及应用于 `BigDecimal` 的舍入机制。

## 27. 编写一个程序，使用字符串 "145574" 初始化一个 `BigDecimal`，并使用上一个练习中的 `MathContext` 变量。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        MathContext mc = new MathContext(4, RoundingMode.HALF_UP);

        BigDecimal bd01 = new BigDecimal("145574", mc);

        System.out.println(bd01);

    }

}
```

## 28. 从字符串 "145574" 开始，实例化 `BigDecimal` 对象 `bd01`，使用标度 6 以及上一个练习中相同的 `MathContext`。打印该值。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        MathContext mc = new MathContext(4, RoundingMode.HALF_UP);

        BigDecimal bd01 = new BigDecimal("145574", 6, mc);

        System.out.println(bd01);

    }

}
```

## 29. 修改练习 27 中的代码，以非科学计数法打印值。提示：方法 `toString()`。

将代码行 `System.out.println(bd01);` 修改为：
`System.out.println(bd01.toString());`

## 30. 实例化 `BigDecimal bd03`，值为 1.455734，精度为 15，舍入模式为 `UNNECESSARY`。打印该数字。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        MathContext mc = new MathContext(15, RoundingMode.UNNECESSARY);

        BigDecimal bd01 = new BigDecimal("1.455734", 6, mc);

        System.out.println(bd01);

    }

}
```

## 31. 重复上述练习，将精度改为 4 而不是 15。说明并解释程序的输出。

输出：`Exception in thread "main" java.lang.ArithmeticException: Rounding necessary`
解释：正如舍入模式文档所述，如果配合精度使用 `UNNECESSARY` 模式，`BigDecimal` 要求任何分配给 `BigDecimal` 实例的数字必须符合指定的精度；也就是说程序员保证确保精度是正确的。

## 32. 解释 `MathContext` 中精度为 0 意味着什么。

`MathContext` 中的精度为 0 意味着应用于该 `BigDecimal` 值的精度

# 第 12 章：数字处理 III

## 33. 重复练习 26，将精度设为 0，舍入模式设置为 UNNECESSARY。说明并解释程序的输出。

输出: 1.455734
解释：输入的数字就是输出的数字，因为我们已经说明了它应该保留其原始精度。

## 34. 重复上一个练习，使用其他模式。找出你的发现。

所有情况下的输出均为 1.455734
解释：当给定精度为 0 时，实际上是在说：按照给定的精度保持数字不变。这意味着在问题中不应尝试进行舍入。

## 35. （更仔细地观察舍入）

编写一个程序，将值 3445 应用于该值，其中标度（scale）为 3，精度（precision）为 2，且 RoundMode 为 HALF_UP。在运行程序之前，打印出你预期的结果。选择这个数字是刻意的，为了便于观察开启的模式。此练习的目的是让你观察并记录数字的长度以及根据指定模式进行的舍入在何时会起作用。

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        MathContext mc0 = new MathContext(2, RoundingMode.HALF_UP);

        BigInteger bi01 = new BigInteger("3445");

        int scale = 3;

        BigDecimal bd01 = new BigDecimal(bi01, scale, mc0);

        System.out.println(bd01.toString());

    }

}
```

# 舍入与标度 (Scale)

## 36. 我通过代码段定义了 BigDecimal：

```java
MathContext mc0 = new MathContext(10, RoundingMode.HALF_UP);
int scale = 6;
BigDecimal bd01 = new BigDecimal(new BigInteger("1455734"), scale, mc0);
```

`BigDecimal bd01=1.4557340000` 的标度值将直接使用已有的 `BigDecimal` 中的值通过 `setScale(12)` 创建一个新的 `BigDecimal` 对象 `bd02`，其值为=1.4557340000（现在小数点后有 12 位）。

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        MathContext mc0 = new MathContext(10, RoundingMode.HALF_UP);

        int scale = 6;

        BigDecimal bd01 = new BigDecimal(new BigInteger("1455734"), scale, mc0);

        BigDecimal bd02 = bd01.setScale(12);

        System.out.println(bd02);

    }

}
```

## 37. 给定上一个练习中的值 bd01，返回一个值为 bd01 * 10^4 的新 BigDecimal。使用不同的方法实现此。

提示：`bd01.movePointRight(4)`, `bd01.multiply(BigDecimal.TEN.pow(4))`, `bd01.scaleByPowerOfTen(4)`

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        MathContext mc0 = new MathContext(10, RoundingMode.HALF_UP);

        int scale = 6;

        BigDecimal bd01 = new BigDecimal(new BigInteger("1455734"), scale, mc0);

        BigDecimal bd02 = bd01.movePointRight(4);

        System.out.println(bd02);

    }

}
```

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        MathContext mc01 = new MathContext(10, RoundingMode.HALF_UP);

        int scale = 6;

        BigDecimal bd01 = new BigDecimal(new BigInteger("1455734"), scale, mc01);

        BigDecimal bd02 = bd01.multiply(new BigDecimal(new BigInteger("100000000")));

        // 这里我们乘以 10^8

        System.out.println(bd02);

    }

}
```

OR

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        MathContext mc01 = new MathContext(10, RoundingMode.HALF_UP);

        int scale = 6;

        BigDecimal bd01 = new BigDecimal(new BigInteger("1455734"), scale, mc01);

        BigDecimal bd02 = bd01.scaleByPowerOfTen(4);

        // 这里我们乘以 10^4

        System.out.println(bd02);

    }

}
```

## 38. 使用上一个练习中 BigDecimal 中的值，返回一个值为 bd01 * 10^-8 的新 BigDecimal。

使用三种方法展示此计算。
提示：`BigDecimal.movePointLeft`, `BigDecimal.divide`, `scaleByPowerOfTen`

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        MathContext mc01 = new MathContext(10, RoundingMode.HALF_UP);

        int scale = 6;

        BigDecimal bd01 = new BigDecimal(new BigInteger("1455734"), scale, mc01);

        BigDecimal bd02 = bd01.movePointLeft(8);

        System.out.println(bd02);

    }

}
```

OR

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {
```



# 第 12 章：数字处理 III

## 练习 39

编写一个程序，将以下浮点值 `(40/3)`、`(4/3)` 和 `(1/3)` 分别赋值 `BigDecimal` 类对象，精度为 2，舍入模式为 `HALF_UP`。打印结果。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        MathContext mc01 = new MathContext(2, RoundingMode.HALF_UP);

        BigDecimal bd01 = new BigDecimal((40f/3f), 2, mc01);

        BigDecimal bd02 = new BigDecimal((4f/3f), 2, mc01);

        BigDecimal bd03 = new BigDecimal((1f/3f), 2, mc01);

        System.out.println(bd01);
        System.out.println(bd02);
        System.out.println(bd03);

    }

}
```

输出：`13.1` 和 `0.33`

## 练习 40

结合上一个练习的输出，我们如何确保输出符合期望的小数位数？我们具体如何指定精度？

指定标度（scale）的方法是应用 `setScale` 方法。为了使此起作用，对数字指定的精度必须足够。事实上，取决于情况，可能不需要对数字指定精度，而是对计算输出指定。

将此应用于上一个练习，代码可以表示如下：

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        MathContext mc01 = new MathContext(5, RoundingMode.HALF_UP);

        // 我们增加了精度；现在 5 可以覆盖这些数字

        BigDecimal bd01 = new BigDecimal((40f/3f), mc01).setScale(2, RoundingMode.HALF_UP);

        BigDecimal bd02 = new BigDecimal((4f/3f), mc01).setScale(2, RoundingMode.HALF_UP);

        BigDecimal bd03 = new BigDecimal((1f/3f), mc01).setScale(2, RoundingMode.HALF_UP);

        System.out.println(bd01);
        System.out.println(bd02);
        System.out.println(bd03);

    }

}
```

在上述练习的代码中，我们实际上对数字进行了两次舍入。这可能是多余的（至少在这种情况下），并且只有在应用 `setScale` 方法时才需要。

> **注意**：注意这里的“scale”一词与构造函数中的“scale”含义不同。

## 练习 41

重写代码以确保舍入只对数字应用一次。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        BigDecimal bd01 = new BigDecimal((40f/3f)).setScale(2, RoundingMode.HALF_UP);

        BigDecimal bd02 = new BigDecimal((4f/3f)).setScale(2, RoundingMode.HALF_UP);

        BigDecimal bd03 = new BigDecimal((1f/3f)).setScale(2, RoundingMode.HALF_UP);

        System.out.println(bd01);
        System.out.println(bd02);
        System.out.println(bd03);

    }

}
```

观察以下内容：我们不需要担心值没有正确的精度，因为通过移除 `MathContext` 对象消除了该限制。我们也对数字进行了一次向上舍入。

## 练习 42

预测运行此程序的输出。解释输出并针对观察到的现象提出解决方案。

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        BigDecimal bd01 = new BigDecimal("5/2").setScale(2);

        System.out.println(bd01);

        BigDecimal bd02 = new BigDecimal("40/3").setScale(2);

        System.out.println(bd02);

    }

}
```

**结果**

- `2.5`
- `Exception in thread "main", java.lang.ArithmeticException: Rounding number（数字舍入）`

第一次计算得到的值 `2.5`，这是正确的。
第二次计算实际上导致了异常。

**解释**

第一次计算产生了一个有理数（即非循环小数）。此类计算的结果根据需要实际上可以写成 `2.5000000000`；由于其具有有理性，我们将标度（scale）设置为 2 是可能的，而不会影响数字的实际值。然而，第二次计算产生了循环小数。如果 JVM 决定进行标度调整，它将截断它认为数字的有效部分，而它倾向于不要这样做；它倾向于在我们请求它进行缩放之前，首先由我们来指定精度。

**结论/解决方案**：为非有理计算设置精度，因为我们需要添加一个标度。

## BigDecimal：初始化中的问题

### 练习 43

重要：观察并解释左侧计算的结果。将其与右侧计算的结果进行对比，并说明获得的值是如何得出的。

```java
import java.math.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        BigDecimal integerOne = new BigDecimal("1");

        BigDecimal integerThree = new BigDecimal("3");

        BigDecimal bd01 = new BigDecimal("one");

        BigDecimal bd02 = new BigDecimal("three");

        BigDecimal bd03 = bd01.divide(bd02);

        System.out.println(bd03);

    }

}
```

> 对于左侧的计算，输出以下语句的结果：`Exception in thread "main", java.lang.ArithmeticException: Non-terminating decimal, no exact represent decimal result（无限小数，没有精确的进制表示结果）`。

对于右侧的计算，结果是：`0.3333333334409627440795898475`
左侧结果的原因是因为计算 `1/3` 产生了**无限**小数（原文“有限小数”应为笔误）。
`BigDecimal` 并不接受这一点，并通过异常向你表示“尊重”。
右侧计算没有失败的原因（尽管它是错误的）是因为输入值首先被计算为浮点类型，浮点类型对无限小数和循环小数的精度有限，这从结果的第 7 位小数可以看出，答案是零。如果我们使用 `double` 而不是 `float`，结果将是 `0.333333333333333314829612562473909923942719848632815`，这个结果本身在第 16 位小数后也是错误的。

**结论**：初始化方法使得左侧的结果是正确的。然而，理解这一点并因此...

## 练习 44

重要：出于任何其他目的将数据输入到 `BigDecimal` 时，为什么使用 `BigInteger` 或 `String` 值比表示 `float` 或 `double` 值更好？

由于精度问题，许多 `float`/`double` 数字在计算机中无法精确表示。上练习中的计算就是一个很好的例子。然而，由于整数是离散的，是可以精确表示的。如果你需要精度，你需要输入：可以表示为 `BigInteger` 类对象的整数值。

虽然在例子中我们使用浮点值初始化了 `BigDecimal` 对象，但除非它们在浮点类型的精度范围内产生有理数，否则使用它们初始化 `BigDecimal` 对象是不正确的。

### 练习 45

编写一个程序，用 `double` 类型值 `0.1` 初始化一个 `BigDecimal` 并打印该 `BigDecimal`。在同一个程序中，用字符串值 `"0.1"` 初始化另一个 `BigDecimal` 并打印它。对你对输出的观察进行评论。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        double d = 0.1;

        BigDecimal bd01 = new BigDecimal(d);

        System.out.println(bd01);

        BigDecimal bd02 = new BigDecimal("0.1");

        System.out.println(bd02);

    }

}
```

**观察**：
`bd01` 的值为 `0.10000000000000000555111515123578270211853840545101625`
`bd02` 的值精确的 `0.1`。

**结论**：这个练习证实了上一个练习中的陈述：具有整数值或字符串值的 `BigDecimal` 对象。

### 练习 46

将以下数字 `1/3` 和 `4/9` 放入 `BigDecimal` 对象中，精度为 10，标度为 10。进行乘法、除法 `(a/b)`、加法、减法 `(a - b)`。

```java
import java.math.*;

public class PracticeJava {

    public static void main(String[] args) {

        MathContext mc = new MathContext(10, RoundingMode.HALF_UP);

        // 准备第一个数字

        BigDecimal bd01 = new BigDecimal("1");

        BigDecimal bd02 = bd01.divide(new BigDecimal("3"), mc).setScale(10);

        // 准备第二个数字

        BigDecimal bd03 = new BigDecimal("4");

        BigDecimal bd04 = bd03.divide(new BigDecimal("9"), mc).setScale(10);

        // 现在进行计算...

        BigDecimal result = bd02.multiply(bd04, mc).setScale(10);

        System.out.println(result);

        result = bd02.divide(bd04, mc).setScale(10);

        System.out.println(result);

        result = bd02.add(bd04, mc).setScale(10);

        System.out.println(result);

        result = bd02.subtract(bd04, mc).setScale(10);

        System.out.println(result);

    }

}
```

### 练习 47

给出一个值为 7 的 `BigDecimal`，打印该数字的 20 次方的结果。

```java
import java.math.*;

public class PracticeYour {

    public static void main(String[] args) {

        // 准备一个数字

        BigDecimal bd = new BigDecimal("7");

        System.out.println(bd.pow(20));

    }

}
```

### 练习 48

为什么之前的计算中不需要精度？

### 练习 49

如果我有一个值为 7.5 的 `BigDecimal`，将其转换为 `float`。

```java
import java.math.*;

public class PracticeYour {

    public static void main(String[] args) {

        BigDecimal bd = new BigDecimal("7.5");
        float f = bd.floatValue();
        System.out.println(f);

    }

}
```

### 练习 50

如果我有一个值为 7.5 的 `BigDecimal`，将其转换为 `BigInteger`。

### 练习 51

如果不是该方法，结果会是什么？

# 第 13 章：数字处理 IV – strictfp & StrictMath

在本章中，我们介绍了使用 `StrictMath` 的练习。

这个主题并不困难，但它被单独作为一个章节。

### 1. strictfp 存在后的概念是什么？

构成计算结果的若干因素：执行计算的 CPU 设计以及执行计算的算法。

**硬件**：在执行浮点计算时，某些平台的寄存器比 `float` 支持的要宽；寄存器的宽度。我们通过例子来解释：首先，假设一个处理器支持最多 4 位的数字。在这个例子中，我们拥有只使用 4 位的 CPU-1。如果我有计算 $1000 \times 10 - 5000$，处处只使用 4 位，结果将是：

```
1000
x 10
0000  <- CPU 溢出！我们丢失了“1”，因为我们的寄存器只有 4 位宽
-5000
-5000
```

如果另一个制造商决定创建一个最多支持 4 位的小数 CPU-2，它在内部使用扩展的 5 位进行中间计算，我们将得到：

```
1000
x 10
10000  <- 我们仍然保留了“1”，因为中间寄存器是 5 位宽
-5000
5000  <- 这个结果符合 4 位限制
```

| 关键字 | 说明 |
| :--- | :--- |
| `strictfp` | 该类中的计算必须符合 strict-FP 要求。 |

`strictfp` 关键字仅适用于浮点类型 `double` 和 `float`。

### 2. StrictMath 类存在背后的概念是什么？

`StrictMath` 类的存在是为了确保 Java 中数学运算的输出，无论在运行这些运算的平台上如何，都能实现位级（bit level）的严格可复现性。某些应用程序要求程序可能运行的不同平台之间具有位级的可复现性。`Math` 类的实现仅要求在“高容差”内准确；由于运行程序的硬件不同，或由于实现相关浮点方法时选择的算法不同，输出可能会有细微差异。严格的可复现性通过指定 `StrictMath` 中每个方法在不同平台（软件而非硬件算法）上计算结果时使用的算法来实现。你可以认为任何使用 `StrictMath` 的计算实际上都是 `strictfp` 的。

### 3. Math 方法与与之对应的 StrictMath 方法之间有什么区别？

通常可以预期 `StrictMath` 方法的速度会较慢，因为它们更多地使用了软件算法。在某些实现中，`Math` 方法被设计为调用其对应的 `StrictMath` 等效方法。然而，即使在虚拟机可以自由使用此类方法的特定功能的情况下，简而言之，在这些情况下它可以忽略对 `StrictMath` 的使用。



# 练习题

| 序号 | 题目 | 代码/说明 |
| :--- | :--- | :--- |
| 4 | 使用 `StrictMath` 类中适当的方法计算 75 度的余弦、正切和正弦。打印结果。 | ```java
public class Java {
    public static void main(String[] args) {
        double degrees = 75;
        double radians = StrictMath.toRadians(degrees);
        double cosine = StrictMath.cos(radians);
        double sine = StrictMath.sin(radians);
        double tangent = StrictMath.tan(radians);

        System.out.printf("The cosine of %f degrees, %f\n", degrees, cosine);
        System.out.printf("The sine of %f degrees, %f\n", degrees, sine);
        System.out.printf("The tangent of %f degrees, %f\n", degrees, tangent);
    }
}
``` |
| 5 | 正或错：Java 将编译时定义的每个（由 `final` 关键字定义）浮点常量都设为 strict-FP 的。 | |
| 6 | 解释下面程序之间功能上的区别： | ```java
public class PracticeJava {
    public static void main(String[] args) {
        double degrees = 75;
        double radians = Math.toRadians(degrees);
        Math.cos(radians); Math.sin(radians); Math.tan(radians);
    }
}
``` |
| | 区别在于左侧的程序使用了 `StrictMath`，它要求严格的算法，因此每个 JVM 上的结果将位位地完全相同。右侧的程序要求标准的中间结果处理，但所使用的算法并未在 JVM 之间强制执行。 | |

| 7 | 为什么没有 `BigDecimal` 类的 `StrictMath` 等类？ | 没有，因为 `BigDecimal` 实际上并没有使用 IEEE 浮点数格式来表示数字。 |

# 第 14 章 数字处理 V – 无符号整数

在本章中，我们将介绍 Java 中的无符号整数主题。这一特性在许多其他语言中都存在，从 Java 8 版本开始，Java 也增加了对它的支持。

本章是书中关于 Java 数字处理的五个章节中的第五章。

| 序号 | 题目 | 答案/说明 |
| :--- | :--- | :--- |
| 1 | 解释什么是无符号数。 | 无符号数是指始终是非负的（即 0 或更高）。“无符号”一词意味着数字前面不需要符号位，即非负数。 |
| 2 | 简述有符号数和无符号数在内部存储上的区别。 | 对于有符号数，位集中的最高位（`most significant bit`）用于标识数字的符号。这意味着在这种情况下，用于表示实际值的位少了一位。对于无符号数，由于整数已知是正的，因此任何位都可以表示数字的符号，从而分配的所有位都可用于表示数值。例如，`int` 使用 32 位表示整数。然而，最高位表示符号，留给我们 31 位来表示正和负的 `int` 值。但对于无符号数，所有 32 位都用于表示数值。 |
| 3 | 列出 Java 中支持无符号类型的类型。 | Java 中支持无符号类型的类型是 `int` 和 `long` 类型。请注意，这种支持很大程度上是通过 `Integer` 和 `Long` 类中的特定方法实现的；没有创建新的原始类型或类来支持这些类型。 |
| 4 | Java 中的无符号 "int" 是什么？ | Java 中的无符号 `int` 是一个与整数类型 `int`（有符号类型）占据相同空间的数字。由于 `int` 占据 32 位，其中 31 位用于数值，最高位用于数字符号，因此无符号 `int` 无需符号位，可以自由地使用 32 位来表示一个数字。 |
| 5 | 什么是无符号 long？ | 无符号 `long` 是一个与 `long` 类型（有符号类型）占据相同空间的数字，但与无符号 `int` 一样，无符号 `long` 不使用最高位作为符号，因此可以使用分配给 `long` 的完整空间来表示数字。 |
| 6 | 无符号 int 是如何工作的？ | 有趣的是，Java 使用 `int` 原始类型来存储无符号 `int` 值，因为 `int` 原始类型确实有 32 位。Java 提供了特定的方法来使用无符号操作。 |
| 7 | Java 中无符号 int 支持的数值范围是什么？ | 0 到 `2^32 - 1` (4,294,967,295)。 |
| 8 | Java 中无符号 long 支持的数值范围是什么？ | 0 到 `2^64 - 1` (18,446,744,073,709,551,615)。 |
| 9 | 解释以下代码的结果： | ```java
class PracticeJava {
    public static void main(String[] args) {
        int uint1 = 50;
    }
}
``` |
| | 代码编译并运行。Java 将其视为有符号 `int`。 | |
| 10 | 解释以下代码的结果： | ```java
class PracticeJava {
    public static void main(String[] args) {
        int uint1 = 2147483648;
    }
}
``` |
| | 代码无法编译，因为 Java 看到一个大于 `Integer.MAX_VALUE` 的值。 | |
| 11 | 解释以下代码的结果： | ```java
class PracticeJava {
    public static void main(String[] args) {
        int uint1 = 2147483647;
    }
}
``` |
| | 代码编译并运行。 | |
| 12 | 解释以下代码的结果： | ```java
class PracticeJava {
    public static void main(String[] args) {
        int uint1 = 4294967295;
    }
}
``` |
| | 代码使用 `Integer.parseUnsignedInt` 来表示它。 | |
| 13 | 将两个无符号整数相加：3,294,967,294 和 45。打印结果。 | |
| 14 | 用第一个无符号整数减去第二个：4,294,967,294 和 3,333,967,295。打印结果。 | |
| 15 | 将两个无符号整数相乘：2,094,967,294 和 2。 | |
| 16 | 除以两个无符号整数 4,294,967,295 和 2,147,483,648。用第一个无符号整数除以第二个。打印结果的商，忽略余数。<br>**提示**：`Integer.divideUnsigned` | |

# 第 14 章：数字处理 V（代码示例）

## 示例 16 实现

```java
public static void main(String[] args) {
    int uint01 = Integer.parseUnsignedInt("429467295");
    int uint02 = Integer.parseUnsignedInt("314748367");
    int uint03 = Integer.divideUnsigned(uint01, uint02);
    System.out.println(Integer.toUnsignedString(uint03));
}
```

## 17. 对无符号整数进行除法。打印出商和余数

**提示**：`Integer.divideUnsigned`, `Integer.remainderUnsigned`

```java
public class PracticeYour {
    public static void main(String[] args) {
        int uint01 = Integer.parseUnsignedInt("429467295");
        int uint02 = Integer.parseUnsignedInt("314748367");
        int quotient = Integer.divideUnsigned(uint01, uint02);
        int remainder = Integer.remainderUnsigned(uint01, uint02);
        System.out.println(Integer.toUnsignedString(quotient));
        System.out.println("the remainder is " + Integer.toUnsignedString(remainder));
    }
}
```

## 18. 使用无符号算术，乘以以下无符号整数 2,394,967,294 和 5,000 并打印结果

**提示**：`Long.parseUnsignedLong`, `Long.toUnsignedString`<br>
这些数字的乘法将导致无符号整数溢出，因此我们使用无符号 `long`。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        long uint01 = Long.parseUnsignedLong("2394967294");
        long uint02 = Long.parseUnsignedLong("5000");
        long uint03 = uint01 * uint02;
        System.out.println(Long.toUnsignedString(uint03));
    }
}
```

## 19. 编写代码比较两个无符号整数，打印出哪一个更大。使用值 3,394,967,294 和 3,400,001,003 测试你的代码

**提示**：`compareUnsigned`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int uint01 = Integer.parseUnsignedInt("3394967294");
        int uint02 = Integer.parseUnsignedInt("3400001003");

        int result = Integer.compareUnsigned(uint01, uint02);
        if (result < 0) {
            System.out.println(Integer.toUnsignedString(uint02) + " is larger");
        } else if (result > 0) {
            System.out.println(Integer.toUnsignedString(uint01) + " is larger");
        } else {
            System.out.println("the numbers are equal!");
        }
    }
}
```

## 20. 将无符号整数 2,094,634,885 左移 1 位并打印结果

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int uint01 = Integer.parseUnsignedInt("2094634885");
        int uint02 = uint01 << 1;
        System.out.println("the result is " + Integer.toUnsignedString(uint02));
    }
}
```

## 21. 将无符号整数值 4,194,634,885 右移 3 位并打印结果

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        int uint01 = Integer.parseUnsignedInt("4194634885");
        int uint02 = uint01 >>> 3; // 用于右移的无符号右移运算符 >>>
        System.out.println("The result = " + Integer.toUnsignedString(uint02));
    }
}
```

## 22. 将无符号整数值 4,194,634,885 以二进制数的形式打印

**提示**：`Integer.toUnsignedString(number, base)`

```java
public class PracticeJava {
    public static void main(String[] args) {
        int uint01 = Integer.parseUnsignedInt("4194634885");
        String str01 = Integer.toUnsignedString(uint01, 2);
        System.out.println(str01);
    }
}
```

## 23. 将上一个练习中的数字以以下基数：16 和 7 重新打印。确保十六进制数中的字母为大写

```java
public class PracticeJava {
    public static void main(String[] args) {
        int uint01 = Integer.parseUnsignedInt("4194634885");
        String str01 = Integer.toUnsignedString(uint01, 16).toUpperCase();
        String str02 = Integer.toUnsignedString(uint01, 8);
        String str03 = Integer.toUnsignedString(uint01, 7);
        System.out.println("The result (Base 16) = " + str01);
        System.out.println("The result (Base 8) = " + str02);
        System.out.println("The result (Base 7) = " + str03);
    }
}
```

## 24. 将 50 作为 short uint01。将其加到无符号整数 4,194,634,885 并打印结果

**提示**：`Short.toUnsignedInt`

```java
public class PracticeJava {
    public static void main(String[] args) {
        short uint01 = 50;
        int uint02 = Integer.parseUnsignedInt("4194634885");
        int uint03 = Short.toUnsignedInt(uint01); // 将 short 转换为无符号 int
        int sum = uint02 + uint03;
        String str01 = Integer.toUnsignedString(sum);
        System.out.println("The result = " + str01);
    }
}
```

## 25. 如果无符号整数 4,194,634,885 表示为无符号 uint01。将其加到无符号 long 400,194,634,224 并打印结果

**提示**：`Long.parseUnsignedLong`

```java
public class PracticeJava {
    public static void main(String[] args) {
        int uint01 = Integer.parseUnsignedInt("4194634885");
        long long01 = Long.parseUnsignedLong("400194634224");
        // 将无符号整数转换为无符号 long
        // 我们通过将其转换为字符串再转换为 long
        String str01 = Integer.toUnsignedString(uint01);
        long long02 = Long.parseUnsignedLong(str01); // 现在我们把它放在 long 中
        long result = long01 + long02;
        String strResult = Long.toUnsignedString(result);
        System.out.println("the result = " + strResult);
    }
}
```

## 26. 使用无符号算术，乘以以下无符号整数 2,394,967,294 和 5,000 并打印结果

(同题目 18)

## 27. 编写代码比较两个无符号整数，打印出哪一个更大。使用值 3,394,967,294 和 3,400,001,003 测试你的代码

(同题目 19)

## 28. 将无符号整数 2,094,634,885 左移 1 位并打印结果

(同题目 20)

## 29. 将无符号整数值 4,194,634,885 右移 3 位并打印结果

(同题目 21)



### 30. 将无符号整数值 4,194,634,885 以二进制数的形式打印。

### 31. 将上一个练习中的数字以以下基数：16 和 7 重新打印。

### 32. 将 50 作为 `short` `uint01`。将其加到无符号整数值 4,194,634,885 并打印结果。

### 33. 如果无符号整数值 4,194,634,885 表示为无符号 `uint01`。将其加到无符号 `long` 400,194,634,224 并打印结果。

# 练习你的 Java Level 1

| 任务 | 提示 / 代码 |
| :--- | :--- |
| 4 | 将 `LocalDateTime` 对象设置为当年的第一天。 | 提示: `LocalDateTime.of` |
```java
import java.time.*;

class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime currentTime = LocalDateTime.of(LocalDateTime.now().getYear(), 1, 1, 0, 0);
    }
}
```
| 5 | 打印 2 年前的日期和时间。 | 提示: `LocalDateTime.minusYears` |
```java
import java.time.*;

class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime currentTime = LocalDateTime.now();
        LocalDateTime twoYearAgo = currentTime.minusYears(2);
        System.out.println("The date and 2 years ago was: " + twoYearAgo);
    }
}
```
| 6 | 打印 7 个月前的日期和时间。 | 提示: `LocalDateTime.minusMonths` |
```java
import java.time.*;

class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime currentTime = LocalDateTime.now();
        LocalDateTime monthsAgo = currentTime.minusMonths(7);
        System.out.println("The date and 7 months ago was: " + monthsAgo);
    }
}
```
| 7 | 打印 6 周前的日期和时间。 | 
```java
import java.time.*;

class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime currentTime = LocalDateTime.now();
        LocalDateTime weeksAgo = currentTime.minusWeeks(6);
        System.out.println("The date and 6 months ago was: " + weeksAgo);
    }
}
```
| 8 | 打印 15 天前的日期和时间。 | 
```java
import java.time.*;

class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime currentTime = LocalDateTime.now();
        LocalDateTime daysAgo = currentTime.minusDays(15);
        System.out.println("The date and 15 days ago was: " + daysAgo);
    }
}
```
| 9 | 打印 9 小时前的日期和时间。 | 
```java
import java.time.*;

class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime currentTime = LocalDateTime.now();
        LocalDateTime hoursAgo = currentTime.minusHours(9);
        System.out.println("The date and 9 hours ago was: " + hoursAgo);
    }
}
```

# 第 15 章：日期与时间处理

### 10. 打印 54 分前的日期和时间。

```java
import java.time.*;

public class PracticeJava {
    public static void main(String[] args) {
        LocalTime currentDate = LocalDateTime.now();
        LocalTime minsAgo = currentDate.minusMinutes(54);
        System.out.println("The date and time 54 minutes ago was: " + minsAgo);
    }
}
```

### 11. 打印 1000 秒前的日期和时间。

```java
import java.time.*;

public class PracticeJava {
    public static void main(String[] args) {
        LocalTime currentDate = LocalDateTime.now();
        LocalTime secondsAgo = currentDate.minusSeconds(1000);
        System.out.println("The date and time 1000 seconds ago was: " + secondsAgo);
    }
}
```

### 12. 打印以下日期：

- 5 年后的日期
- 9 个月后的日期
- 3 周后的日期
- 14 天后的日期
- 2 小时后的日期
- 15 分钟后的日期
- 1000 秒后的日期

> 提示: `LocalDateTime.plusYear`、`plusMonths` 等。

```java
import java.time.*;

public class PracticeJava {
    public static void main(String[] args) {
        System.out.printf("/date time in 5 years will be %s\n", LocalDateTime.now().plusYears(5));
        System.out.printf("/date time in 9 months will be %s\n", LocalDateTime.now().plusMonths(9));
        System.out.printf("/date time in 3 weeks will be %s\n", LocalDateTime.now().plusWeeks(3));
        System.out.printf("/date time in 14 days will be %s\n", LocalDateTime.now().plusDays(14));
        System.out.printf("/date time in 2 hours will be %s\n", LocalDateTime.now().plusHours(2));
        System.out.printf("/date time in 15 minutes will be %s\n", LocalDateTime.now().plusMinutes(15));
        System.out.printf("/date/time in 1000 seconds will be %s\n", LocalDateTime.now().plusSeconds(1000));
    }
}
```

### 13. 确定当年的第 200 天是星期几。

> 提示: 确定第一天和对应的天数。也使用 `LocalDateTime.plusDays`。

```java
import java.time.*;

public class PracticeJava {
    public static void main(String[] args) {
        LocalTime currentDate = LocalDateTime.of(LocalDateTime.now().getYear(), 1, 1, 0, 0);
        LocalTime day200 = currentDate.plusDays(199);
        System.out.printf("The 200th day of the year is %s %s\n", day200.getMonth(), day200.getDayOfYear());
    }
}
```

# 练习你的 Java Level 1

### 14. 确定本地日期（不包含时间）并以默认格式打印。

提示: `import java.time.*;`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDate currentDate = LocalDate.now();
        System.out.println("The date is " + LocalDate.now());
    }
}
```

### 15. 分别打印上一个练习中 `LocalDate` 的子元素：

年、月（均为单词格式和数字格式）、日中的几和星期几。

提示: `import java.time.*;`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDate currentDate = LocalDate.now();
        System.out.println("Year: " + currentDate.getYear());
        System.out.println("Month: " + currentDate.getMonth());
        System.out.println("Month: " + currentDate.getMonthValue());
        System.out.println("DayOfMonth: " + currentDate.getDayOfMonth());
        System.out.println("DayOfWeek: " + currentDate.getDayOfWeek());
    }
}
```

### 16. 打印 Java 中可以表示的最晚和最早的日期。

提示: `LocalDate` 中的常量。

```java
import java.time.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDate maxDate = LocalDate.MAX;
        System.out.println("The maximum date is: " + maxDate);
        LocalDate minDate = LocalDate.MIN;
        System.out.println("The minimum date is: " + minDate);
    }
}
```

### 17. 打印当前月份有多少天。

```java
import java.time.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDate currentDate = LocalDate.now();
        int daysInMonth = currentDate.lengthOfMonth();
        System.out.println("Number of days in this month is " + daysInMonth);
    }
}
```

### 18. 相对于当前日期打印以下日期：

- 14 年前
- 9 个月前
- 4 周前
- 7 天前

```java
import java.time.*;

public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime currentDate = LocalDateTime.now();
        System.out.printf("14 years ago was: %s\n", currentDate.minusYears(14));
        System.out.printf("9 months ago was: %s\n", currentDate.minusMonths(9));
        System.out.printf("4 weeks ago was: %s\n", currentDate.minusWeeks(4));
        System.out.printf("7 days ago was: %s\n", currentDate.minusDays(7));
    }
}
```

### 19. 相对于当前日期打印以下日期：

- 5 年后的日期
- 9 个月后的日期
- 3 周后的日期
- 14 天后的日期

```java
import java.time.*;

public class PracticeJava {
    public static void main(String[] args) {
        System.out.printf("/date time in 5 years will be %s\n", LocalDateTime.now().plusYears(5));
        System.out.printf("/date time in 9 months will be %s\n", LocalDateTime.now().plusMonths(9));
        System.out.printf("/date time in 3 weeks will be %s\n", LocalDateTime.now().plusWeeks(3));
        System.out.printf("/date time in 14 days will be %s\n", LocalDateTime.now().plusDays(14));
    }
}
```

### 20. 打印从 2010 年到 2030 年每年每年有多少天。

同时，打印这些年份是否为闰年。

```java
import java.time.*;

public class PracticeJava {
    public static void main(String[] args) {
        for (int i = 2010; i <= 2030; i++) {
            LocalDate dt1 = LocalDate.of(i, 1, 1);
            int days = dt1.lengthInYear();
            System.out.printf("There are %d days in year %d\n", days, i);
            if (dt1.isLeapYear()) {
                System.out.printf("Year %d is a leap year\n", i);
            } else {
                System.out.printf("Year %d is NOT a leap year\n", i);
            }
        }
    }
}
```

### 21. 今年的第 300 天是哪一天？

从当前的 `LocalDate` (now) 获取当前年份并使用 `LocalDate.ofYearOfYear`



```java
import java.time.*;
public class PracticeJava {
    public static void main(String[] args) {
        int dayInQuestion = 300;
        int iYear = LocalDate.now().getYear();
        LocalDate dateInQuestion = LocalDate.ofYearOfYear(iYear, dayInQuestion);
        System.out.printf("The 300th day of the year is %s\n", dateInQuestion);
    }
}
```

## 22. 在计算机术中，什么是“纪时间（epoch time）？”

纪时间是一种描述时间实例的系统，它是指自称为“纪（epoch）”的时间点以来所逝的时间，该时间点是 UTC 1970 年 1 月 1 日星期四 00:00:00。

# 练习你的 Java 1

| 问题 | 代码 / 提示 |
| :--- | :--- |
| 23. 距离纪元（epoch）今天有多少天？<br>提示: `LocalDate.toEpochDay()` | ```java\nimport java.time.*;\npublic class PracticeYourJava {\n    public static void main(String[] args) {\n        LocalDate currentDate = LocalDate.now();\n        long daysSinceEpoch = currentDate.toEpochDay();\n        System.out.printf("Today is %d days since the epoch.\\n", daysSinceEpoch);\n    }\n}``` |
| 24. 纪元后的第 5000 天是哪一天？<br>提示: `LocalDate.ofEpochDay()` | ```java\nimport java.time.*;\npublic class PracticeYourJava {\n    public static void main(String[] args) {\n        int daysInQuestion = 5000;\n        LocalDate dateInQuestion = LocalDate.ofEpochDay(daysInQuestion);\n        System.out.printf("The %d day after the epoch = %s,\n", daysInQuestion, dateInQuestion);\n    }\n}``` |
| 25. 我有以下一个 `LocalDate` 对象：`LocalDate date01 = LocalDate.now();`<br>将该对象的年、月、日字段分别修改为 2020、10 和 15。打印结果 `LocalDate` 对象。<br>提示: `LocalDate.withYear`, `withMonth`, `withOfMonth` | ```java\nimport java.time.*;\npublic class PracticeYourJava {\n    public static void main(String[] args) {\n        LocalDate date01 = LocalDate.now();\n        date01 = date01.withYear(2020);\n        date01 = date01.withMonth(10);\n        date01 = date01.withOfMonth(15);\n        System.out.printf("The new DateTime = %s\n", date01);\n    }\n}``` |
| 26. 我有以下一个 `LocalDate` 对象：`LocalDate date01 = LocalDate.now();`<br>将该对象修改为年的第 121 天。打印结果 `LocalDate` 输出。<br>提示: `LocalDate.dayOfYear` | ```java\nimport java.time.*;\npublic class PracticeYourJava {\n    public static void main(String[] args) {\n        LocalDate date01 = LocalDate.now();\n        date01 = date01.withDayOfYear(121);\n        System.out.printf("The new DateTime = %s\n", date01);\n    }\n}``` |
| 27. 我有以下一个 `LocalDate` 对象：`LocalDate date01 = LocalDate.now();`<br>将其拷贝到 `String` 变量并打印该 `String` 变量。 | ```java\nimport java.time.*;\npublic class PracticeYourJava {\n    public static void main(String[] args) {\n        LocalDate date01 = LocalDate.now();\n        String s01 = date01.toString();\n        System.out.printf("The DateTime = %s\n", s01);\n    }\n}``` |

# 第 15 章：日期与时间处理

| 问题 | 代码 / 提示 |
| :--- | :--- |
| 28. 初始化 `LocalDate` 为你的生日。打印结果对象。<br>提示: `LocalDate.of` | ```java\nimport java.time.*;\npublic class PracticeYourJava {\n    public static void main(String[] args) {\n        LocalDate birthdate = LocalDate.of(1970, 03, 01); //例如 1970 年 3 月 1 日\n        System.out.println("My birthday is " + birthdate);\n    }\n}``` |
| 29. 判断你的生日是否在 2004 年 3 月 15 日之前或在当天。<br>提示: `LocalDate.isEqual`, `isBefore` | ```java\nimport java.time.*;\npublic class PracticeYourJava {\n    public static void main(String[] args) {\n        LocalDate birthdate = LocalDate.of(1970,03,01); // 1970 年 3 月 1 日的生日\n        LocalDate targetDate = LocalDate.of(2004, 03, 15);\n        if(birthdate.equals(targetDate)) {\n            System.out.println("My birth is actually " + targetDate.toString());\n        } else {\n            if(birthdate.isBefore(targetDate)) {\n                System.out.println("My birthday is before " + targetDate.toString());\n            } else {\n                System.out.println("My birthday is after " + targetDate.toString());\n            }\n        }\n    }\n}``` |

## LocalTime 类

### 30. 获取当前日期（不是时间）并以默认格式打印出来。<br>提示: `LocalTime.now`

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime currentTime = LocalTime.now();

        System.out.println("The time is " + currentTime);

    }

}
```

### 31. 分别打印 `LocalTime` 的以下子元素：小时、分钟、秒和纳秒。

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime currentTime = LocalTime.now();

        System.out.println("Hour = " + currentTime.getHour());

        System.out.println("Minute = " + currentTime.getMinute());

        System.out.println("Seconds = " + currentTime.getSeconds());

        System.out.println("Nano-seconds = " + currentTime.getNano());

    }

}
```

### 32. 计算并打印以下时间：
- 27 小时前
- 24 分钟前
- 51 秒前

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime currentTime = LocalTime.now();

        System.out.printf("time 27 hours ago was %s\n", currentTime.minusHours(27));

        System.out.printf("time 24 minutes ago was %s\n", currentTime.minusMinutes(24));

        System.out.printf("time 51 seconds ago was %s\n", currentTime.minusSeconds(51));

    }

}
```

### 33. 计算并打印出后的时间：
- 3 小时后
- 45 分钟后
- 100 秒后

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime currentTime = LocalTime.now();

        System.out.printf("time in 3 hours is %s\n", currentTime.plusHours(3));

        System.out.printf("time in 45 minutes is %s\n", currentTime.plusMinutes(45));

        System.out.printf("time in 100 seconds is %s\n", currentTime.plusSeconds(100));

    }

}
```

### 34. 2.5 小时前的时间是几点？

```java
import java.time.*;

public class PracticeJava {

    public static void main(String[] args) {

        LocalTime time = LocalTime.now();

        System.out.printf("The time 2.5 hours ago was %s\n", time.minusMinutes(150)); 

    }

}
```

### 35. 当天的第 49000 秒是几点？<br>提示: `java.time.LocalTime`

```java
import java.time.*;

public class PracticeJava {

    public static void main(String[] args) {

        long secondsToConvert = 49000;

        LocalTime currentTime = LocalTime.ofSecondOfDay(secondsToConvert);

        System.out.printf("The %d second is %s\n", secondsToConvert, currentTime);

    }

}
```

### 36. 当天的第 558975589000 纳秒是几点？

```java
import java.time.*;

public class PracticeJava {

    public static void main(String[] args) {

        long nosecondsToConvert = 558975589000L;

        LocalTime currentTime = LocalTime.ofNanoOfDay(nosecondsToConvert);

        System.out.printf("The %d second is %s\n", nosecondsToConvert, currentTime);

    }

}
```

### 37. 初始化 `LocalTime` 对象为下午 3:30:35。

```java
import java.time.*;

public class PracticeJava {

    public static void main(String[] args) {

        LocalTime time = LocalTime.of(15, 30, 35);

        System.out.printf("The time is %s", time);

    }

}
```

### 38. 初始化 `LocalTime` 对象为 16:30。

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime time = LocalTime.of(16, 30);

        System.out.printf("The time is %s", time);

    }

}
```

### 39. 将上一个练习中 `LocalTime` 对象的小时字段修改为 17。<br>提示: `LocalTime.of`, `LocalTime.withHour`

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime time = LocalTime.of(16, 30);

        time = time.withHour(17);

        System.out.printf("The time is %s", time);

    }

}
```

### 40. 将上一个练习中 `LocalTime` 对象的分钟和秒字段分别修改为 37 和 24。同时将纳秒字段设置为 0。

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime time = LocalTime.of(16, 30);

        time = time.withMinute(37);

        time = time.withSecond(24);

        time = time.withNano(0);

        System.out.printf("The time is %s\n", time);

    }

}
```

### 41. 将时间转换为秒和纳秒。打印这些值。<br>提示: `LocalTime.toSecondOfDay`, `toNanoOfDay`

```java
import java.time.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        LocalTime currentTime = LocalTime.now();

        long seconds = currentTime.toSecondOfDay();
```



# 练习你的 Java 1级

```java
long nanoseconds = currentTime.toNanoOfDay();

System.out.printf("Current time in seconds = %d\n", seconds);

System.out.printf("Current time in nano-seconds = %d\n", nanoseconds);

}
}
```

## 42. 将时间存储在 String s01 中

提示：`LocalTime.toString`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalTime currentTime = LocalTime.now();
        String s01 = currentTime.toString();
    }
}
```

```java
String s01 = currentTime.toString();
}
```

## 43. 合并 LocalDate 和 LocalTime

我有以下对象：

```java
LocalDate date01 = LocalDate.of(2025, 12, 15);
LocalTime time01 = LocalTime.of(15, 25, 17);
```

将这两个对象合并成单个的 `LocalDateTime` 对象并打印出结果对象。

提示：`LocalTime.atDate` 或 `LocalDate.atTime`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDate date01 = LocalDate.of(2025, 12, 15);
        LocalTime time01 = LocalTime.of(15, 25, 17);
        LocalDateTime dt01 = time01.atDate(date01);
        // OR LocalDateTime dt01 = date01.atTime(time01);
        System.out.printf("The combined object is %s\n", dt01);
    }
}
```

## 44. 比较两个 LocalTime 对象

给定以下两个 `LocalTime` 对象，判断它们是否相等。如果相等则指出；否则打印出哪一个较早。

```java
LocalTime time01 = LocalTime.of(8, 30, 35);
LocalTime time02 = LocalTime.of(14, 42, 9);
```

提示：`LocalTime.isBefore`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalTime time01 = LocalTime.of(19, 30, 35);
        LocalTime time02 = LocalTime.of(14, 42, 9);
        if (time01.equals(time02)) {
            System.out.println("They are the same time value!");
            return;
        } else {
            System.out.println("They are NOT the same time value!");
            if (time01.isBefore(time02)) {
                System.out.println("The first time is before the 2nd.");
            } else {
                System.out.println("The 2nd time is before the 1st!");
            }
        }
    }
}
```

备注：也看下 `isAfter` 方法。

## 45. 计算两个 LocalTime 对象之间的秒差

使用 `ChronoUnit` 枚举和以下方法计算时间差。

确定以下两个 `LocalTime` 对象之间的秒差：

```java
LocalTime time01 = LocalTime.of(8, 30, 35);
LocalTime time02 = LocalTime.of(14, 42, 9);
```

提示：`LocalTime.until`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalTime time01 = LocalTime.of(8, 30, 35);
        LocalTime time02 = LocalTime.of(14, 42, 9);
        long diff = time01.until(time02, ChronoUnit.SECONDS);
        System.out.printf("The difference is %d seconds\n", diff);
    }
}
```

## 46. 打印你的年龄（天数）

提示：`LocalDate.until`。你的生日与现在之间的差。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDate birthdate = LocalDate.of(1970, 03, 01); // 例如 1970年3月1日
        LocalDate currentDate = LocalDate.now();
        long numberOfDays = birthdate.until(currentDate, ChronoUnit.DAYS);
        System.out.println("I am " + numberOfDays + " days old.");
    }
}
```

## 47. 打印你的小时数

提示：你不能对 `LocalDate` 对象应用 `ChronoUnit.HOURS`，但你可以使用 `LocalDateTime`。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime birthTime = LocalDateTime.of(1970, 03, 01, 0, 0, 0);
        // 例如3月1日，我们假设是午夜
        LocalDateTime currentDate = LocalDateTime.now();
        long numberOfHours = birthTime.until(currentDate, ChronoUnit.HOURS);
        System.out.println("I am " + numberOfHours + " hours old.");
    }
}
```

## 48. 计算距离下次生日还有多少天

提示：判断你的生日在今年是否已经过去。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDate birthdate = LocalDate.of(1970, 03, 01);
        LocalDate nextBirthday = LocalDate.of(LocalDate.now().getYear(), birthdate.getMonth(), birthdate.getDayOfMonth());
        // birthdate.getDayOfMonth(); // 我今年的生日
        // 让我们看看我们是否已经过了它
        long numberOfDays = nextBirthday.until(LocalDate.now(), ChronoUnit.DAYS);
        if (numberOfDays < 0)
            nextBirthday = nextBirthday.plusYears(1);
        numberOfDays = LocalDate.now().until(nextBirthday, ChronoUnit.DAYS);
        System.out.println("It is " + numberOfDays + " days till my next birthday day");
    }
}
```

# 类与枚举 Year, Month, MonthDay 和 DayOfWeek

## 49. 实例化 Year 对象

实例化一个值为 2025 的 `Year` 对象。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Year year01 = Year.of(2025);
        System.out.printf("The year is %s\n", year01);
    }
}
```

## 50. 判断闰年

判断上一个练习中的 `Year` 对象是否为闰年。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Year year01 = Year.of(2025);
        if (year01.isLeap())
            System.out.printf("The year is a leap year\n", year01);
        else
            System.out.printf("The year is NOT a leap year\n", year01);
    }
}
```

# Java 练习 1

## 51. 打印 Year 对象值

给定以下两个 `Year` 对象，其中一个打印它的值。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Year year01 = Year.of(2025);
        System.out.printf("The year is %s\n", year01);
    }
}
```

## 52. 比较两个 Year 对象

我有两个 `Year` 对象。编写一个程序判断它们是否相等。如果相等则指出；否则打印哪一个较早。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Year year01 = Year.of(2025);
        Year year02 = Year.of(2020);
        if (year01.equals(year02)) {
            System.out.println("They are the same year value!");
        } else {
            System.out.println("They are NOT the same year value!");
            if (year01.isBefore(year02)) {
                System.out.println("The first year is before the 2nd.");
            } else {
                System.out.println("The 2nd year is before the 1st!");
            }
        }
    }
}
```

## 53. 创建 YearMonth 对象

给定一个值为 2025 的 `Year` 和一个整数 8（代表月份），形成一个 `YearMonth` 对象。打印它。

提示：`Year.atMonth`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Year year01 = Year.of(2025);
        int month = 8;
        YearMonth ymonth = year01.atMonth(month);
        System.out.printf("%s\n", ymonth);
    }
}
```

## 54. Month 枚举操作

实例化值为 `FEBRUARY` 的 `Month`。之后打印：

1. 枚举的值
2. 月份的最大长度（天数）
3. 月份的最小长度（天数）

提示：`Month.getValue()`, `minLength`, `maxLength`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Month month01 = Month.FEBRUARY;
        System.out.printf("Value = %d\n", month01.getValue());
        System.out.printf("Max days = %d\n", month01.maxLength());
        System.out.printf("Min days = %d\n", month01.minLength());
    }
}
```

# 第15章：日期与时间处理

## 55. Month 加减操作

实例化值为 7（代表七月）的 `Month`。同时，打印出 2 个月前的月份和 3 个月后的月份。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Month month01 = Month.of(7);
        System.out.printf("2 months before = %s\n", month01.minus(2));
        System.out.printf("3 months after = %s\n", month01.plus(3));
    }
}
```

## 56. Month.valueOf 输出

以下代码的输出是什么？

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Month month01 = Month.valueOf("AUGUST");
        System.out.printf("The month is %s\n", month01);
    }
}
```

输出是：`The month is AUGUST`

这说明你可以使用月份枚举名称对应的字符串来初始化月份。

## 57. 闰年二月长度

闰年二月份的长度是多少？提示：首先使用 `Year.isLeap` 判断是否为闰年。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        int specifiedYear = 2024; // 为了测试设置一个值
        Month month01 = Month.FEBRUARY;
        int length = month01.length(Year.isLeap(specifiedYear));
        System.out.printf("The length is %d days\n", length);
    }
}
```

# 你的 Java 1 级练习

## 考虑时区：类 ZonedDateTime, ZoneId, ZoneOffset

### 59. 简要描述 ZonedDateTime、ZoneId 和 ZoneOffset 类以及它们之间的关系

`ZonedDateTime` 类用于表示日期-时间，在日期和时间信息的基础上指定时区。

在每个类中，时区都被分配了一个名称。`ZoneId` 类代表每个时区；如其名所示，它是日期的“标识(id)”。现在，由于每个 `ZonedDateTime` 对象都拥有一个时区，该时区可以从 `ZonedDateTime` 对象中提取出来并赋值给 `ZoneId` 对象。

`ZoneOffset` 类表示 `ZonedDateTime` 对象相对于 UTC/GMT 的偏移量（以秒为单位）。

总结：一旦你有了一个 `ZonedDateTime` 对象，就可以确定它处于哪个时区（这被放入 `ZoneId` 对象中）以及该时区与 UTC/GMT 之间的差距（这被放入 `ZoneOffset` 对象中）。



# 练习你的 Java 1 级

## 日期与时间处理

### 60. 打印你运行程序的系统所在默认时区

提示：使用 `ZoneId.systemDefault()`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        System.out.printf("the default time zone is %s\n", ZoneId.systemDefault());
    }
}
```

### 61. 打印日期和时间，包括当前时区

提示：使用 `ZonedDateTime` 对象而不是 `LocalDateTime` 来确定包含时区的当前日期/时间。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZonedDateTime dateTime = ZonedDateTime.now();
        System.out.println("the current date & time is " + dateTime);
    }
}
```

### 62. 从当前的 `ZonedDateTime` 中提取你所在地的时区名称

提示：`ZonedDateTime.getZone`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZonedDateTime dateTime = ZonedDateTime.now();
        ZoneId myZone = dateTime.getZone();
        System.out.println("Zone name = " + myZone);
    }
}
```

### 63. 从当前的 `ZonedDateTime` 中提取你所在地的时区偏移量

提示：`java.time.*`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZonedDateTime dateTime = ZonedDateTime.now();
        ZoneOffset myOffset = dateTime.getOffset();
        System.out.println("Zone offset = " + myOffset);
    }
}
```

> **注意**：观察 `ZonedDateTime` 类具有与 `LocalDateTime` 相同的日期/时间字段的 get 方法。在本次练习中，我们显式地只提取了时区和时间偏移量。

### 64. 编写一个程序判断你所在的时区是在 UTC 之前、之后还是相同

提示：`ZonedDateTime.getOffset`, `ZoneOffset.getTotalSeconds`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZonedDateTime zonedDateTime = ZonedDateTime.now();
        ZoneOffset myOffset = zonedDateTime.getOffset();
        int behindBefore = myOffset.getTotalSeconds();
        if (behindBefore < 0) {
            System.out.println("We are behind GMT.");
        } else if (behindBefore > 0) {
            System.out.println("We are ahead of GMT.");
        } else {
            System.out.println("We are in GMT.");
        }
    }
}
```

### 65. 运行程序以观察可用时区名称列表。对输出格式进行注释

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        String[] zoneArray = ZoneId.getAvailableZoneIds().toArray(new String[0]);
        for (int i = 0; i < zoneArray.length; i++) {
            System.out.println(zoneArray[i]);
        }
    }
}
```

输出的一些时区名称如下：

- Africa/Nairobi
- Africa/Cairo
- America/Belize
- America/New_York
- America/Indiana/Petersburg
- America/Argentina/San_Juan
- Asia/Aden
- Asia/Pontianak
- Asia/Kuching
- CET
- Etc/GMT+9
- Etc/GMT-1
- Europe/London
- Europe/Brussels
- GMT
- Libya

可以观察到时区名称以以下格式呈现：

- 当格式为 `<X>/<Y>` 时，X 是大陆的名称，Y 是该大陆中某个城市的名称。
- 当格式为 `<X>` 时，这些通常是广为人知的时区，例如 GMT、CET（欧洲中部时间），甚至是一个只有一个时区的国家名称（例如利比亚）。
- 当格式为 `<X>/<Y>/<Z>` 时，X 可能代表一个大陆，Y 代表其中的一个特定区域，Z 可能代表国家，或者是其中的某个州/省份，然后是城市/城镇。

通常，世界上的每个时区都表示在这个列表中。

**解释时区名称与 `ZoneId` 对象之间的关系。**

时区名称是存在的不同时区的文本表示/描述。`ZoneId` 对象是一个用于表示给定时区名称的对象；`ZoneId` 知道它所代表的时间偏移量。

### 66. 为以下时区名称获取 `ZoneId`

- 1. Africa/Nairobi
- 2. GMT
- 3. Europe/London

提示：`ZoneId.of`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZoneId zId1 = ZoneId.of("Africa/Nairobi");
        ZoneId zId2 = ZoneId.of("GMT");
        ZoneId zId3 = ZoneId.of("Europe/London");
    }
}
```

### 67. 创建代表美国纽约 2019 年 6 月 15 日凌晨 1:15 的 `ZonedDateTime` 对象

提示：`ZonedDateTime.of`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZonedDateTime zdt01 = ZonedDateTime.of(2019, 6, 15, 1, 15, 0, 0, ZoneId.of("America/New_York"));
    }
}
```

### 68. 如果伦敦是下午 5 点，莫斯科是什么时间？

提示：获取伦敦的 `ZonedDateTime`，然后使用 `withZoneInstant` 方法配合莫斯科的 `ZoneId` 确定莫斯科的时间。

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZonedDateTime zdt01 = ZonedDateTime.now(ZoneId.of("Europe/London"));
        zdt01 = zdt01.withHour(17).withMinute(0);
        ZonedDateTime zdt02 = zdt01.withZoneInstant(ZoneId.of("Europe/Moscow"));
        System.out.println("The corresponding time in Moscow = " + zdt02);
    }
}
```

## 日期/时间格式化

### 69. 我有以下 `ZonedDateTime`

`ZonedDateTime zdt01 = ZonedDateTime.of(2017, 2, 9, 8, 6, 4, 0, ZoneId.of("America/New_York"));`

以以下方式打印它：

1. 使用每种内置格式。
2. 仅打印内置格式的日期部分。
3. 仅打印内置格式的时间部分。

提示：`DateTimeFormatter` 常量

```java
import java.time.*;
import java.time.format.DateTimeFormatter;
public class PracticeYourJava {
    public static void main(String[] args) {
        ZonedDateTime zdt01 = ZonedDateTime.of(2017, 2, 9, 8, 6, 4, 0, ZoneId.of("America/New_York"));
        System.out.println(zdt01.format(DateTimeFormatter.ISO_DATE_TIME));
        System.out.println(zdt01.format(DateTimeFormatter.ISO_LOCAL_TIME));
        System.out.println(zdt01.format(DateTimeFormatter.ISO_ZONED_DATE_TIME));
        System.out.println(zdt01.format(DateTimeFormatter.ISO_DATE));
        System.out.println(zdt01.format(DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss")));
        System.out.println(zdt01.format(DateTimeFormatter.ofPattern("MMMM dd, yyyy")));
        System.out.println(zdt01.format(DateTimeFormatter.ofPattern("E, MMM d, yyyy")));
    }
}
```

### 70. 我有以下对象

`ZonedDateTime zdt0 = ZonedDateTime.of(2017, 2, 9, 8, 6, 4, 0, ZoneId.of("UTC"));`

编写一个程序，使用自定义格式符输出该对象的所有组件：年、月、日（月份）、小时（12-24小时制）、AM/PM、分、秒、毫秒和时区。

```java
import java.time.*;
import java.time.format.DateTimeFormatter;
public class PracticeJava {
    public static void main(String[] args) {
        ZonedDateTime zdt0 = ZonedDateTime.of(2017, 2, 9, 8, 6, 4, 0, ZoneId.of("UTC"));
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy MMMM dd EEEE, HH:mm:ss.SSS a zzz");
        System.out.println(zdt0.format(formatter));
    }
}
```

### 71. 对于上一个练习中的 `ZonedDateTime` 对象，打印以下信息

是年份中的哪一天，是星期几，是月份中的哪一天（例如，确定它是该月的第三个周三）。

```java
import java.time.*;
import java.time.format.DateTimeFormatter;
import java.time.temporal.TemporalFields;
public class PracticeJava {
    public static void main(String[] args) {
        ZonedDateTime zdt0 = ZonedDateTime.of(2017, 2, 9, 8, 6, 4, 0, ZoneId.of("America/New_York"));
        System.out.println("Day in year " + zdt0.getDayOfYear());
        System.out.println("Day of week " + zdt0.getDayOfWeek());
        System.out.println("The week of the month is " + zdt0.get(TemporalFields.WEEK_OF_MONTH()));
        System.out.println("The nth day of this week is " + zdt0.get(TemporalFields.DAY_OF_WEEK()));
        System.out.println("It is the nth day of the month " + zdt0.get(TemporalFields.DAY_OF_MONTH()));
    }
}
```

### 72. 编写一个程序，以以下格式打印 2017 年 3 月 1 日 21:05:00

1. 2019/3 02:15:07
2. 20190301 02:15:07
3. 20190301-02:15:07

```java
import java.time.*;
import java.time.format.DateTimeFormatter;
public class PracticeYourJava {
    public static void main(String[] args) {
        LocalDateTime dt02 = LocalDateTime.of(2019, 3, 1, 22, 15, 7);
        System.out.println(dt02.format(DateTimeFormatter.ofPattern("yyyy/MM/dd HH:mm:ss")));
        System.out.println(dt02.format(DateTimeFormatter.ofPattern("yyyyMMdd HH:mm:ss")));
        System.out.println(dt02.format(DateTimeFormatter.ofPattern("yyyyMMdd-'T'HH:mm:ss")));
    }
}
```

## 时长 (Duration) 与 瞬间 (Instant)

### 73. 我们想要测量将 1 到 1,000,000 的数字相加所需的时间

并将这些数字加到一个 `Long` 类对象。使用循环进行累加，并使用 `Instant` 和 `Duration` 类对象测量相加时长。打印出时长。

使用 `Long` 类中的 `long` 原始类型重复该练习。

提示：`Instant.now()`, `Duration.between()`

```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        // 使用 Long 对象
        Instant start = Instant.now();
        Long sumObj = 0L;
        for (long i = 1; i <= 1_000_000; i++) {
            sumObj += i;
        }
        Instant end = Instant.now();
        Duration durationObj = Duration.between(start, end);
        System.out.println("Duration using Long object: " + durationObj);

        // 使用 long 原始类型
        start = Instant.now();
        long sumPrim = 0L;
        for (long i = 1; i <= 1_000_000; i++) {
            sumPrim += i;
        }
        end = Instant.now();
        Duration durationPrim = Duration.between(start, end);
        System.out.println("Duration using long primitive: " + durationPrim);
    }
}
```



```java
import java.time.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        int maxNum = 1_000_000_000;
        long sum01 = 0;
        Instant startInstant = Instant.now();
        for(int i=0; i < maxNum; i++)
            sum01+=i;
        Instant finishInstant = Instant.now();
        Duration duration01 = Duration.between(startInstant,finishInstant);
        System.out.println("The duration is: " + duration01);

        // 使用 long 原始类型进行
        long sum02 = 0;
        startInstant = Instant.now();
        for(int i=0; i < maxNum; i++)
            sum02+=i;
        finishInstant = Instant.now();
        Duration duration02 = Duration.between(startInstant,finishInstant);
        System.out.println("The duration is: " + duration02);
    }
}
```

### 75. 我们想要确定哪种更高效：`Arrays.sort` 方法还是 `Arrays.parallelSort` 方法。编写一个程序，在数组中填充 20,000,000 个 1 到 10,000 之间的随机数。使用上述提到的方法对每个数组进行排序，测量并打印执行每次排序所需的时间。

在创建数组后，在 `[]` 数组中创建它的副本，供第二个算法使用，以便它们排序的是相同的数据。

```java
import java.time.*;
import java.util.Arrays;

public class PracticeYourJava {
    public static void main(String[] args) {
        // 使用 Instant & Duration 测量数组排序的时长
        int numElements = 20_000_000;
        int[] array1 = new int[numElements];
        int[] array2; // 我们在为 array1 填充随机数后将 array1 复制到此

        for(int i=0;i<array1.length;i++)
            array1[i] = (int)Math.ceil(Math.random() * 10000);
        array2 = Arrays.copyOf(array1, array1.length); // 创建一个副本供另一个算法使用
        // 第一次排序，使用 Arrays.sort
        Instant startInstant = Instant.now();
        Arrays.sort(array1);
        Instant finishInstant = Instant.now();
        Duration duration01 = Duration.between(startInstant,finishInstant);
        System.out.println("Using Arrays.sort: time to sort: " + numElements + " = " + duration01);

        // 第二次排序，使用 Arrays.parallelSort
        startInstant = Instant.now();
        Arrays.parallelSort(array2);
        finishInstant = Instant.now();
        Duration duration02 = Duration.between(startInstant,finishInstant);
        System.out.println("Using Arrays.parallelSort: time to sort: " + numElements + " = " + duration02);
    }
}
```

- **E1** 编写一个程序计算并打印你的年龄（以年、月、日为单位，例如“35岁，11个月，3天”）。
  提示：研究 `Period` 类。

- **E2** 使用 `System.nanoTime` 方法重复练习 74 以测量时间差。

## 第 16 章 异常

异常在 Java 中是一个非常重要的概念，因为它提供了一种优雅地处理程序执行过程中可能出现的异常情况的方法。本章介绍了有助于理解异常概念的练习，并有助于明确 Java 程序中适当、必要且有时是强制的异常处理做法。

```java
public class ExceptionTest {
    public static void main(String[] args) {
        int a = 5;
        int b = 0;
        System.out.println(a / b);
        System.out.println("After the calculation\n");
    }
}
```

这将产生 `java.lang.ArithmeticException`。

这会产生 `java.lang.ArithmeticException`。程序将不会执行“计算之后”这一行。

### 4. 修改前面的练习，捕获异常。异常块应该输出“计算之后”。

```java
public class ExceptionTest {
    public static void main(String[] args) {
        int a = 5;
        int b = 0;
        try {
            System.out.println(a / b);
        } catch (ArithmeticException e) {
            // Handle exception
        }
        System.out.println("After the calculation\n");
    }
}
```

## 练习你的 Java 1 级

| # | 问题 |
| :--- | :--- |
| 5 | 下列代码访问空引用会抛出什么异常？<br>```java<br>public class ExceptionTest {<br>    public static void main(String[] args) {<br>        String s = null;<br>        s.length();<br>    }<br>}<br>```<br>抛出 `java.lang.NullPointerException` 异常。 |
| 6 | 修改前面的练习，捕获该异常并打印异常的名称。<br>```java<br>public class ExceptionTest {<br>    public static void main(String[] args) {<br>        String s = null;<br>        try {<br>            s.length();<br>        } catch (NullPointerException e) {<br>            System.out.println(e.getClass().getName());<br>        }<br>    }<br>}<br>```<br>异常会抛出 `java.lang.NullPointerException` 异常。 |
| 7 | 下列代码会产生什么异常？<br>```java<br>public class ExceptionTest {<br>    public static void main(String[] args) {<br>        int x1 = Integer.MAX_VALUE;<br>        int x2 = 1000;<br>        int x3 = Math.addExact(x1, x2);<br>    }<br>}<br>```<br>抛出 `java.lang.ArithmeticException`，虚拟机说明是“整数溢出”。 |
| 8 | 修改前面的练习，捕获异常并在异常处理程序中打印“整数溢出”文本。<br>```java<br>public class ExceptionTest {<br>    public static void main(String[] args) {<br>        int x1 = Integer.MAX_VALUE;<br>        int x2 = 1000;<br>        try {<br>            int x3 = Math.addExact(x1, x2);<br>        } catch (ArithmeticException e) {<br>            System.out.println("整数溢出");<br>        }<br>    }<br>}<br>```<br>异常处理程序会输出“整数溢出”。 |
| 9 | 下列代码尝试访问越界索引会抛出什么异常？<br>```java<br>public class ExceptionTest {<br>    public static void main(String[] args) {<br>        int arrayIndex = 14;<br>        int[] iArray = new int[5];<br>        iArray[arrayIndex] = 1500;<br>    }<br>}<br>```<br>抛出 `java.lang.ArrayIndexOutOfBoundsException` 异常。 |

## 第 16 章 异常

这将抛出 `java.lang.ArrayIndexOutOfBoundsException` 异常。

### 10. 修改前面的练习，捕获异常并在异常处理程序中打印“我捕获了异常”。

```java
public class ExceptionTest {
    public static void main(String[] args) {
        int arrayIndex = 14;
        int[] iArray = new int[5];
        try {
            iArray[arrayIndex] = 1500;
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("I caught the exception!");
        }
        System.out.println("After the array index attempt");
    }
}
```

### 11. 修改前面练习的异常处理程序，打印关于异常对象的以下信息：

1. 异常消息
2. 异常原因
3. 异常点的栈跟踪

```java
public class ExceptionTest {
    public static void main(String[] args) {
        int arrayIndex = 14;
        int[] iArray = new int[5];
        try {
            iArray[arrayIndex] = 1500;
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println(e.getMessage());
            System.out.println(e.getCause());
            e.printStackTrace();
        }
    }
}
```

### 故意抛出异常

修改练习 10 中的程序，当用户尝试访问数组位置 2 时，抛出 `ArrayIndexOutOfBoundsException` 异常。异常消息应该是“尝试访问索引 2”。

```java
public class ExceptionTest {
    public static void main(String[] args) {
        int arrayIndex = 2; // 为了测试将其设置为 2
        int[] iArray = new int[5];
        if (arrayIndex == 2) {
            throw new ArrayIndexOutOfBoundsException("Attempt to access array index 2");
        }
        try {
            iArray[arrayIndex] = 1500;
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("I caught the exception!");
        }
        System.out.println("After the array index attempt");
    }
}
```

## 练习你的 Java 1 级

### 13. 用户定义异常：创建你自己的异常类

Java 提供了让你定义自己的自定义异常类的功能。这些类看起来与其他任何异常类一样，必须继承自 `Exception` 或其任何子类。基于此，我们有以下示例：

创建一个名为 `DivideBy2Exception` 的自定义异常，父类为 `Exception`。（不要在其中的方法中添加任何实质性代码）。

*注意：如果你正在使用 Eclipse IDE，最简单的方法是使用类创建模板，只需在窗口中指定父类为 `Exception` 即可；IDE 将向你展示所继承方法的存根方法（stubs）。*

```java
public class DivideBy2Exception extends Exception {
    public DivideBy2Exception() {
    }
    public DivideBy2Exception(String message) {
        super(message);
    }
    public DivideBy2Exception(Throwable cause) {
        super(cause);
    }
    public DivideBy2Exception(String message, Throwable cause) {
        super(message, cause);
    }
    public DivideBy2Exception(String message, Throwable cause,
        boolean enableSuppression, boolean writableStackTrace) {
        super(message, cause, enableSuppression, writableStackTrace);
    }
}
```

### 14. 抛出用户定义异常

编写一个程序，将一个给定的浮点数除以另一个浮点数（硬编码数值进行测试）。当除数能被 2 整除时，抛出你创建的 `DivideBy2Exception`。

让异常的 `catch` 块打印出：
1. 异常的 `message` 字段
2. 短语 "Divisor divisible by 2 exception"

```java
public class ExceptionTest {
    public static void main(String[] args) {
        float a = 10f;
        float b = 2f;
        try {
            if ((b % 2) == 0) {
                throw new DivideBy2Exception("Divisor divisible by 2 exception");
            }
            float c = a / b;
            System.out.println(c);
        } catch (DivideBy2Exception e) {
            System.out.println(e);
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

## 第 16 章：异常

### 检查点异常（强制捕获异常）

**15. 解释“受检异常”（checked exceptions）的概念。** 在某些场景下，Java 强制要求你为捕获可能抛出的异常提供准备，否则编译器将**拒绝编译**你的代码。文件处理是 Java 编程中你被强制捕获异常的一个关键领域。

**16. 解释为什么下面的代码尝试为一个不存在的文件创建符号链接将无法编译，以及它编译需要什么状态。**

```java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class ExceptionTest {
    public static void A() throws IOException {
        String fileName = "ThisFileNotExist";
        String symlinkName = "link01";
        Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        Path symlinkPath = Paths.get(System.getProperty("user.home"), "Desktop", symlinkName);
        Files.createSymbolicLink(symlinkPath, targetPath);
    }
}
```



# 第 16 章：异常

## 代码示例：编译错误演示

```java
public static void main(String[] args) {
    A();
}
```

该代码无法编译，是因为它包含了 Java 要求我们处理的潜在异常的方法。I/O 操作属于这类“你必须捕获”的异常类别；Java 将这些称为“受检异常”（checked exceptions）。处理这些异常有两种方法：

1. 标准的 `try/catch` 处理
2. 抛出这些“受检异常”的方法必须在方法声明中显式出现，并在其方法声明中带有 `throws` 语句。例如，上述方法 `A()` 的头部（其中方法 `Files.createLink` 可能会抛出此类异常）可以被修改为：

```java
public static void A() throws IOException {
```

如果选择这种方式，意味着在方法 `A()` 的堆栈调用中将处理这些异常。在这种情况下，异常必须在调用方法 `main` 中处理。请注意，直接在方法内部应用 `try/catch` 块来捕获相同的异常仍然是有效的。这种机制的优点是它便于在中心位置处理异常，而不会让块散落在代码各个地方。

### 说明

1. 重申：即使使用这种第二种机制，在使用该机制的方法内部应用 `try/catch` 块仍然有效。
2. 如果 `main()` 是头部带有 `throws <exception>` 子句的方法，那么显然，如果异常在 `main()` 内部没有被处理，程序将在异常发生时停止运行。

## 类错误解释

```java
public class ExceptionTest {
    public static void main(String[] args) {
        int arrayIndex = 10;
        int[] iArray = new int[5];
        try {
            iArray[arrayIndex] = 1500;
        } catch (Exception e) {
            System.out.println("I caught the exception!");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("I caught the exception!");
        }
        System.out.println("After the array index access attempt");
    }
}
```

由于 `ArrayIndexOutOfBoundsException` 是 `Exception` 的子类，第一个 `catch(Exception e)` 会捕获该异常，导致第二个 `catch(ArrayIndexOutOfBoundsException e)` 块变得不可达。

## 练习你的 Java 1 级

### 练习 23

```java
public class ExceptionTest {
    public static void B() {
        int a = 10, b = 0;
        int result;
        result = a / b;
    }

    public static void A() {
        B();
    }

    public static void main(String[] args) {
        try {
            A();
        } catch (ArithmeticException e) {
            System.out.println("In main...exception caught.");
        }
    }
}
```

**输出**
```
In main...exception caught.
```

**观察/解释**
异常在 `B()` 方法中触发，但在另一个方法 `main()` 中被捕获，该方法从 `try` 块调用了 `A()`，而 `A()` 又调用了 `B()`。另一个练习显示 `try` 块可以放置在生成异常方法的调用栈的任何位置，`try` 块将捕获该异常。

### 练习 24：重新抛出异常

```java
public class ExceptionTest {
    public static void main(String[] args) {
        try {
            int a = 10, b = 0;
            int result;
            try {
                result = a / b;
            } catch (ArithmeticException e) {
                System.out.print("Divide by zero situation has occurred.");
                System.out.println("Rethrowing this exception.");
                throw e;
            }
        } catch (ArithmeticException e) {
            System.out.println("Outer block...exception caught.");
        }
    }
}
```

**输出**
```
Divide by zero situation has occurred.Rethrowing this exception.
Outer block...exception caught.
```

**解释**
这段代码展示了“重新抛出”异常的概念以及它如何与嵌套 `try` 块协同工作。代码中注意以下几点：

1. 内部块有一个对应的 `catch` 块，通过简单使用 `throw` 关键字重新抛出异常。
2. 外部块捕获了重新抛出的异常。

### 练习 25

修改上述练习中外部 `try` 块的 `catch`，以捕获 `Exception` 类的异常。运行修改后的代码并解释结果。

**输出**
与之前的解决方案相同。

**解释**
这是因为 `Exception` 是父类，因此它的处理程序可以作为任何未被捕获内容的通用捕获器。

### 练习 26

给出一个你可能想要实现重新抛出异常的场景。

发生这种情况的一种场景是：你在异常发生的方法中对异常进行了本地处理（如记录日志），但在更高层次上，你对该异常有更通用的处理。

### 练习 27

给出一个使用嵌套 `try` 块有价值的场景。

例如，我们可能拥有内部 `try` 块来捕获所有预见到的异常，但并非所有异常都被预见到。捕获父异常的外部 `try` 块将帮助你的应用程序优雅地处理此类故障。

### 练习 28

编写一个执行以下操作程序：

```java
import java.time.*;
import java.time.temporal.ChronoUnit;

public class PracticeYourJava {
    public static void main(String[] args) {
        // 1. 获取当前时间
        LocalDateTime dt1 = LocalDateTime.now();

        // 2. 睡眠 10 秒
        try {
            Thread.sleep(10000);
        } catch (InterruptedException e) {
            System.out.println("Sleep interrupted.");
        }

        // 3. 再次读取时间
        LocalDateTime dt2 = LocalDateTime.now();

        // 4. 打印第一次读取和第二次读取之间毫秒的差异
        System.out.println("Elapsed milliseconds = " + dt1.until(dt2, ChronoUnit.MILLIS));
    }
}
```

**提示**：`LocalDateTime`, `Thread.sleep`, `ChronoUnit.MILLIS`, exception handling

### 练习 29：try with resources

注意：不熟悉 I/O 的读者应该阅读这个示例，因为使用 `try with resources` 在使用实现了 `java.lang.AutoCloseable` 接口的类时将变得更加清晰（我们将在后面的章节中讨论 I/O 和接口）。

重写以下代码以使用 `try with resources` 语句：

**原始代码：**

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class ExceptionTest {
    public static void main(String[] args) {
        String fileTo = "rhyme.txt";
        Path sourcePath = Paths.get(System.getProperty("user.home"), "Desktop", fileTo);
        String nextLine;
        BufferedReader nbr;
        try {
            nbr = Files.newBufferedReader(sourcePath);
            while ((nextLine = nbr.readLine()) != null) {
                System.out.println(nextLine);
            }
            nbr.close();
        } catch (IOException e) {
            System.out.println("IOException: " + e);
        }
    }
}
```

**使用 `try with resources` 重写后的代码：**

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class ExceptionTest {
    public static void main(String[] args) {
        String fileTo = "rhyme.txt";
        Path sourcePath = Paths.get(System.getProperty("user.home"), "Desktop", fileTo);
        String nextLine;

        try (BufferedReader nbr = Files.newBufferedReader(sourcePath)) {
            while ((nextLine = nbr.readLine()) != null) {
                System.out.println(nextLine);
            }
        } catch (IOException e) {
            System.out.println("I/O Exception noted");
        }
    }
}
```

**注意事项**

问题中的代码与解决方案代码之间的差异是：

1. `BufferedReader` 对象的实例化直接在 `try` 块的资源声明部分完成。
2. 不再需要使用 `close()` 方法显式关闭 `BufferedReader` 资源，`try-with-resources` 会自动处理。

---

# 第 17 章：控制台处理 II：控制输入

有些时候控制台应用程序需要用户交互，通过键盘输入。这要求我们理解如何请求和解释数据。键盘读取的数据总是以字符串形式接收（无论它是数字），因此需要进行转换。

本章的练习利用了 `Console` 或 `Scanner` 类来接收用户输入。

**注意**：本章的练习必须直接从命令行运行，而不是从 IDE 中。

### 练习 1

使用 `Console` 对象从用户处请求名和姓。随后打印：“Your name is \<firstName> \<lastName>”。

**提示**：`System.console()`, `java.io.Console`

```java
import java.io.Console;

public class ConsoleHandling {
    public static void main(String[] args) {
        Console consoleObject = System.console();

        if (consoleObject != null) {
            System.out.print("Please enter your first name: ");
            String firstName = consoleObject.readLine();

            System.out.print("Please enter your last name: ");
            String lastName = consoleObject.readLine();

            System.out.printf("Your name is %s %s", firstName, lastName);
        } else {
            System.out.println("无法获取控制台对象。");
            System.out.println("请确保此程序直接在命令行运行。");
        }
    }
}
```

### 练习 2

使用 `Console` 对象接收数据，并向用户请求第一个和第二个字符串。如果字符串相同，输出“The strings are the same!”，否则输出“The strings are different!”。

**提示**：`String.equals()`

```java
import java.io.Console;

public class ConsoleHandling {
    public static void main(String[] args) {
        Console consoleObject = System.console();

        if (consoleObject == null) {
            System.out.println("无法获取控制台对象");
            System.exit(0);
        }

        System.out.print("Please enter your 1st String: ");
        String str01 = consoleObject.readLine();

        System.out.print("Please enter the 2nd String: ");
        String str02 = consoleObject.readLine();

        boolean comparisonValue = str01.equals(str02);

        if (!comparisonValue) {
            System.out.println("The Strings are different!");
        } else {
            System.out.println("The Strings are the same!");
        }
    }
}
```

### 练习 3

重做上一个练习，这次忽略输入字符串的大小写。

**提示**：`String.equalsIgnoreCase()`

只需将上一个练习方案中的以下代码行：

```java
comparisonValue = str01.equals(str02);
```

替换为以下行：

```java
comparisonValue = str01.equalsIgnoreCase(str02);
```

### 练习 4

重复上一个练习，按以下方式进行修改：如果字符串相同但大小写不同，输出“They are equal and the case is different!”；否则它们相同且大小写一致，输出“They are equal and the case is the same!”。

```java
import java.io.Console;

public class ConsoleHandling {
    public static void main(String[] args) {
        Console consoleObject = System.console();

        if (consoleObject == null) {
            System.out.println("无法获取控制台对象");
            System.exit(0);
        }

        System.out.print("Please enter your 1st String: ");
        String str01 = consoleObject.readLine();

        System.out.print("Please enter the 2nd String: ");
        String str02 = consoleObject.readLine();

        boolean equalsIgnoreCase = str01.equalsIgnoreCase(str02);
        boolean equals = str01.equals(str02);

        if (equalsIgnoreCase) {
            if (equals) {
                System.out.println("They are equal and the case is the same!");
            } else {
                System.out.println("They are equal and the case is different!");
            }
        } else {
            System.out.println("The Strings are different!");
        }
    }
}
```



## 练习你的 Java 级 1

### 5. 字符串比较与字母顺序

让用户输入第一个和第二个字符串。打印出字母顺序上靠前的字符串。如果它们相同，则视为事实。忽略字符串的大小写。
*提示：`String.equalsIgnoreCase`*

```java
import java.io.Console;

public class ConsoleHandling {

    public static void main(String[] args) {

        Console consoleObject = System.console();

        if (consoleObject == null) {

            System.out.println("A console object was not obtained successfully");

            System.exit(0);

        }

        System.out.print("Please enter your 1st String: ");

        String str0 = consoleObject.readLine();

        System.out.print("Please enter your 2nd String: ");

        String str2 = consoleObject.readLine();

        int comparisonValue;

        comparisonValue = str0.compareToIgnoreCase(str2);

        if (comparisonValue < 0) {

            System.out.printf("%s is before %s alphabetically", str0, str2);

        } else if (comparisonValue > 0) {

            System.out.printf("%s is after %s alphabetically ", str2, str0);

        } else {

            System.out.println("The Strings are the same!");

        }

    }

}
```

### 6. 控制台输入数据类型说明

控制台输入的数据是什么类型，并被解释为字符串？即使你输入的是一个数字（例如输入数字“22”），它被接收并视为由两个连续字符组成的字符串，没有任何语义含义；控制台接收并将数值数据解释为字符串的影响是，数据必须显式地转换为数字。Java 中提供了提供这种转换的方法，例如 `Integer.valueOf()` 可将整数值从字符串转换为 `int` 值，`Float.valueOf()` 对 `float` 执行相同的操作，以及适用于相应原始类型的 `Long.valueOf()` 和 `Double.valueOf()` 方法。

### 7. 整数求和与异常处理

使用控制台对象接收数据，要求用户输入两个整数，将其相加并打印和。如果数据不是整数，则无法计算，因此使用 `case` 语句指出哪个或哪些数字出现错误，然后退出程序。提示：使用 `Integer.valueOf` 方法将控制台输入的数字转换为整数。

```java
import java.io.Console;

public class ConsoleHandling {

    public static void main(String[] args) {

        Console consoleObject = System.console();

        if (consoleObject == null) {

            System.out.println("A console object was not obtained successfully...exiting");

            System.exit(0);

        }

        System.out.println("Please enter the first integer:");

        String svalue01 = consoleObject.readLine();

        System.out.println("Please enter the 2nd integer:");

        String svalue02 = consoleObject.readLine();

        int value01 = 0, value02 = 0;

        boolean isValidNum1 = true;

        boolean isValidNum2 = true;

        try {

            value01 = Integer.valueOf(svalue01);

        } catch (NumberFormatException e) {

            isValidNum1 = false;

        }

        try {

            value02 = Integer.valueOf(svalue02);

        } catch (NumberFormatException e) {

            isValidNum2 = false;

        }

        if (isValidNum1 != true) {

            System.out.println("The 1st value entered is not an integer");

        }

        if (isValidNum2 != true) {

            System.out.println("The 2nd value entered is not an integer");

        }

        if (isValidNum1 && isValidNum2) {

            System.out.println("The sum is: " + (value01 + value02));

        }

    }

}
```

### 12. 使用 Scanner 求和整数集合

要求用户输入一组整数（用空格分隔）并对其进行求和。确保跳过数据区域中的非整数。使用 `Scanner` 对象接收用户输入的数据。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        System.out.println("Enter a set of integers to be added up:");

        Scanner scanner01 = new Scanner(System.in);

        String s = scanner01.nextLine();

        Scanner scanner02 = new Scanner(s);

        int scannedInt = 0;

        int sum = 0;

        while (scanner02.hasNext()) {

            try {

                scannedInt = scanner02.nextInt();

                sum += scannedInt;

            } catch (InputMismatchException e) {

                // skip the unwanted token

                scanner02.next();

            } catch (IllegalStateException e) {

                break;

            }

        }

        scanner01.close();

        scanner02.close();

        System.out.println("Total = " + sum);

    }

}
```

### 13. 增强版：无限循环直到输入 "quit"

增强上一个练习的解决方案，这次执行无限循环请求数字，直到在输入中看到任何大小写的 "quit" 单词为止。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        Scanner scanner01 = new Scanner(System.in);

        while (true) {

            System.out.println("Enter a set of integers to be added up:");

            String s = scanner01.nextLine();

            String s_lower = s.toLowerCase();

            if (s_lower.contains("quit")) {

                System.out.println("Quit! detected in input...bye bye!");

                break;

            }

            Scanner scanner02 = new Scanner(s);

            int scannedInt = 0;

            long sum = 0;

            while (scanner02.hasNext()) {

                try {

                    scannedInt = scanner02.nextInt();

                    sum += scannedInt;

                } catch (InputMismatchException e) {

                    // skip the unwanted token

                    scanner02.next();

                } catch (IllegalStateException e) {

                    break;

                }

            }

            System.out.println("Total = " + sum);

            scanner02.close();

        }

        scanner01.close();

    }

}
```

### 14. 姓名格式化输出

要求用户输入他们的名和姓，并返回一条声明：“Your full name is <姓（仅首字母大写）>, <名（仅首字母大写）>”。
例如，如果用户输入的名字为 "jay"，姓为 "doe"，则打印 "Your full name is Doe, Jay"。

*提示：识别每个条目中你希望分别转换为大写和小写的子字符串 (`String.substring`)。*

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        String firstName = ""; // 声明一个接收值的 String

        String lastName = ""; // 声明一个接收值的 String

        String modifiedFirstName, modifiedLastName;

        System.out.print("What is your first name please?");

        Scanner in = new Scanner(System.in);

        firstName = in.next();

        modifiedFirstName = firstName.substring(0, 1).toUpperCase() +

            firstName.substring(1, firstName.length()).toLowerCase();

        System.out.print("What is your last name please?");

        lastName = in.next();

        modifiedLastName = lastName.substring(0, 1).toUpperCase() +

            lastName.substring(1, lastName.length()).toLowerCase();

        System.out.printf("Your full name is %s, %s\n", modifiedLastName, modifiedFirstName);

        in.close();

    }

}
```

### 15. 标记类型识别

要求用户输入一个数据字符串，其中包含以下类型的标记：boolean、integer、long、float、double、bigdecimal、big decimal 或 string。
确定这些标记的类型并打印出该类型。
注意：注意处理浮点数时的顺序，例如，在检测到一个本该应该是 BigDecimal 的值时，`hasNextFloat` 会假设它是一个 float。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        Scanner scanner0 = new Scanner(System.in);

        System.out.println("Please enter a set of tokens:");

        String s = scanner0.nextLine();

        System.out.println("Input string is " + s);

        Scanner scanner2 = new Scanner(s); // 将 scanner 应用于 String

        while (scanner2.hasNext()) {

            if (scanner2.hasNextBoolean()) {

                System.out.println("boolean");

            } else if (scanner2.hasNextByte()) {

                System.out.println("byte");

            } else if (scanner2.hasNextShort()) {

                System.out.println("short");
            }
        }
    }
}
```



# 练习你的 Java 级 1

## 12. 要求用户输入一组整数（用空格分隔）并对其进行求和。确保跳过数据区域中的非整数。使用 `Scanner` 对象接收用户输入的数据。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        System.out.println("Enter a set of integers to be added up:");

        Scanner scanner01 = new Scanner(System.in);

        String s = scanner01.nextLine();

        Scanner scanner02 = new Scanner(s);

        int scannedInt = 0;

        int sum = 0;

        while (scanner02.hasNext()) {

            try {

                scannedInt = scanner02.nextInt();

                sum += scannedInt;

            } catch (InputMismatchException e) {

                // skip the unwanted token

                scanner02.next();

            } catch (IllegalStateException e) {

                break;

            }

        }

        scanner01.close();

        scanner02.close();

        System.out.println("Total = " + sum);

    }

}
```

## 13. 增强上一个练习的解决方案，这次执行无限循环请求数字，直到在输入中看到任何大小写的 "quit" 单词为止。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        Scanner scanner01 = new Scanner(System.in);

        while (true) {

            System.out.println("Enter a set of integers to be added up:");

            String s = scanner01.nextLine();

            String s_lower = s.toLowerCase();

            if (s_lower.contains("quit")) {

                System.out.println("Quit! detected in input...bye bye!");

                break;

            }

            Scanner scanner02 = new Scanner(s);

            int scannedInt = 0;

            long sum = 0;

            while (scanner02.hasNext()) {

                try {

                    scannedInt = scanner02.nextInt();

                    sum += scannedInt;

                } catch (InputMismatchException e) {

                    // skip the unwanted token

                    scanner02.next();

                } catch (IllegalStateException e) {

                    break;

                }

            }

            System.out.println("Total = " + sum);

            scanner02.close();

        }

        scanner01.close();

    }

}
```

## 要求用户输入他们的名和姓，并返回一条声明：“Your full name is <姓（仅首字母大写）>, <名（仅首字母大写）>”。例如，如果用户输入的名字为 "jay"，姓为 "doe"，则打印 "Your full name is Doe, Jay"。

**提示**：识别每个条目中你希望分别转换为大写和小写的子字符串 (`String.substring`)。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        String firstName = ""; // 声明一个接收值的 String

        String lastName = ""; // 声明一个接收值的 String

        String modifiedFirstName, modifiedLastName;

        System.out.print("What is your first name please?");

        Scanner in = new Scanner(System.in);

        firstName = in.next();

        modifiedFirstName = firstName.substring(0, 1).toUpperCase() + firstName.substring(1, firstName.length()).toLowerCase();

        System.out.print("What is your last name please?");

        lastName = in.next();

        modifiedLastName = lastName.substring(0, 1).toUpperCase() + lastName.substring(1, lastName.length()).toLowerCase();

        System.out.printf("Your full name is %s, %s\n", modifiedFirstName, modifiedLastName);

        in.close();

    }

}
```

## 要求用户输入一个数据字符串，其中包含以下类型的标记：boolean、integer、long、float、double、bigdecimal、big decimal 或 string。确定这些标记的类型并打印出该类型。注意：注意处理浮点数时的顺序，例如，在检测到一个本该应该是 BigDecimal 的值时，`hasNextFloat()` 会假设它是一个 float。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        Scanner scanner0 = new Scanner(System.in);

        System.out.println("Please enter a set of tokens:");

        String s = scanner0.nextLine();

        System.out.println("Input string is " + s);

        Scanner scanner2 = new Scanner(s); // apply a scanner to the String

        while (scanner2.hasNext()) {

            if (scanner2.hasNextBoolean()) {

                System.out.println("boolean");

            } else if (scanner2.hasNextByte()) {

                System.out.println("byte");

            } else if (scanner2.hasNextShort()) {

                System.out.println("short");

            } else if (scanner2.hasNextInt()) {

                System.out.println("integer");

            } else if (scanner2.hasNextLong()) {

                System.out.println("long");

            } else if (scanner2.hasNextBigInteger()) {

                System.out.println("BigInteger");

            } else if (scanner2.hasNextFloat()) {

                // ...

            }

        }

    }

}
```



```java
public static void main(String[] args) {

    System.out.println("Enter a set of integers to be added up:");

    Scanner scanner01 = new Scanner(System.in);

    String s = scanner01.nextLine();

    Scanner scanner02 = new Scanner(s);

    int scannedInt = 0;

    int sum = 0;

    while (scanner02.hasNext()) {

        try {

            scannedInt = scanner02.nextInt();

            sum += scannedInt;

        } catch (InputMismatchException e) {

            // skip the unwanted token

            scanner02.next();

        } catch (IllegalStateException e) {

            break;

        }

    }

    scanner01.close();

    scanner02.close();

    System.out.println("Total = " + sum);

}
```

### 13. 增强上一个练习的解决方案，这次执行无限循环请求数字，直到在输入中看到任何大小写的 "quit" 单词为止。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        Scanner scanner01 = new Scanner(System.in);

        while (true) {

            System.out.println("Enter a set of integers to be added up:");

            String s = scanner01.nextLine();

            String s_lower = s.toLowerCase();

            if (s_lower.contains("quit")) {

                System.out.println("Quit! detected in input...bye bye!");

                break;

            }

            Scanner scanner02 = new Scanner(s);

            int scannedInt = 0;

            long sum = 0;

            while (scanner02.hasNext()) {

                try {

                    scannedInt = scanner02.nextInt();

                    sum += scannedInt;

                } catch (InputMismatchException e) {

                    // skip the unwanted token

                    scanner02.next();

                } catch (IllegalStateException e) {

                    break;

                }

            }

            System.out.println("Total = " + sum);

            scanner02.close();

        }

        scanner01.close();

    }

}
```

- 要求用户输入他们的名和姓，并返回一条声明：“Your full name is <姓（仅首字母大写）>, <名（仅首字母大写）>”。
  例如，如果用户输入的名字为 "jay"，姓为 "doe"，则打印 "Your full name is Doe, Jay"。

- 提示：识别每个条目中你希望分别转换为大写和小写的子字符串 (`String.substring`)。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        String firstName = ""; // 声明一个接收值的 String

        String lastName = ""; // 声明一个接收值的 String

        String modifiedFirstName, modifiedLastName;

        System.out.print("What is your first name please?");

        Scanner in = new Scanner(System.in);

        firstName = in.next();

        modifiedFirstName = firstName.substring(0, 1).toUpperCase() +
            firstName.substring(1, firstName.length()).toLowerCase();

        System.out.print("What is your last name please?");

        lastName = in.next();

        modifiedLastName = lastName.substring(0, 1).toUpperCase() +
            lastName.substring(1, lastName.length()).toLowerCase();

        System.out.printf("Your full name is %s, %s\n", modifiedFirstName, modifiedLastName);

        in.close();

    }

}
```

- 要求用户输入一个数据字符串，其中包含以下类型的标记：boolean、integer、long、float、double、bigdecimal、big decimal 或 string。
  确定这些标记的类型并打印出该类型。
  注意：注意处理浮点数时的顺序，例如，在检测到一个本该应该是 BigDecimal 的值时，`hasNextFloat` 会假设它是一个 float。

```java
import java.util.*;

public class ConsoleHandling {

    public static void main(String[] args) {

        Scanner scanner0 = new Scanner(System.in);

        System.out.println("Please enter a set of tokens:");

        String s = scanner0.nextLine();

        System.out.println("Input string is " + s);

        Scanner scanner2 = new Scanner(s); // apply a scanner to the String

        while (scanner2.hasNext()) {

            if (scanner2.hasNextBoolean()) {

                System.out.println("boolean");

            } else if (scanner2.hasNextByte()) {

                System.out.println("byte");

            } else if (scanner2.hasNextShort()) {

                System.out.println("short");

            } else if (scanner2.hasNextInt()) {

                System.out.println("integer");

            } else if (scanner2.hasNextLong()) {

                System.out.println("long");

            } else if (scanner2.hasNextBigInteger()) {

                System.out.println("BigInteger");

            } else if (scanner2.hasNextFloat()) {

                // ...

            }

        }

    }

}
```

# 练习你的 Java 1 级

```java
public class ConsoleHandling {

    public static void main(String[] args) {

        long sum = 0;

        int numOfIntegers = 0;

        if (args.length == 0) {

            System.out.println("No arguments passed. Exiting");

            System.exit(0);

        }

        for (int i = 0; i < args.length; i++) {

            try {

                long potentialInteger = Long.parseLong(args[i]);

                sum += potentialInteger;

                numOfIntegers++;

            } catch (NumberFormatException e) {

                // 忽略非数字内容

            }

        }

        System.out.printf("Total = %d\n", sum);

        System.out.printf("Number of integers = %d\n", numOfIntegers);

        System.out.printf("Number of args = %d\n", args.length);

    }

}
```

# 第 19 章：char 基本类型与 Character 包装类

Java 提供了处理单个字符的能力，无论是 `char` 类型还是字符串中的单个字符。本章介绍了关于 `char` 类型及其相关包装类 `Character` 的各个方面的练习。此外还介绍了关于 `char` 类型与整数以及 `String` 对象各个元素之间关系的练习。

操作 `char` 基本类型的方法可以在其对应的包装类 `Character` 中找到；它们的相互关系贯穿于本章的练习中。

## 1. 什么是 Unicode？

Unicode 是一种编码方式，为各种语言的字符分配一个特定的正数值。然而，Unicode 的范围超过了一百万，但大多数正在使用的字符都在 0000（十六进制）到 FFFF（十六进制，即十进制的 65535）的范围内，这个范围可以用 2 字节表示，这正好是 `char` 基本类型的大小。

## 2. 什么是 char 类型？

`char` 是一种用于表示 Unicode 字符的 Java 类型。

## 3. 解释 Unicode 编码方案的基本概念。

早在 Unicode 中，字符被分配了一个数值，范围从 0 到一个大于 1,000,000 的值。Unicode 编码方案的概念是指 Unicode 值表示的不同方式；在 Unicode 中有不同的编码方案，每种方案都有不同的重点。存在 UTF-8、UTF-16 和 UTF-32 方案；每种方案以不同的方式编码字符。例如，UTF-32 每个字符使用 4 字节进行编码（对于那些实际上不需要 4 字节表示的字符来说，这占据了大量空间），UTF-8 每个字符使用 1、2 或 4 字节进行编码（这节省了 Unicode 空间低端字符的空间，但增加了编程的复杂性）。UTF-16 使用 2 或 4 字节编码字符。

## 4. Java 中用于字符的 Unicode 编码是什么？

这种特定的 Unicode 编码使用 2 或 4 字节来表示字符。

## 5. Java 中表示一个 char 使用多少字节？

2 字节，代表 65536 个数字的范围。`char` 类型由正整数值表示，这 2 字节的范围是 0 到 65535。
然而，有足够的 Unicode 字符需要 4 字节来表示；这些在 Java 中通过 2 个 `char` 来表示。

## 6. 哪种数值类型最直接对应 char 能够容下的数值范围？

无符号短整型，范围为 0...65535（`char` 没有无符号短整型）。

## 7. 写一行代码，将 char 变量首次初始化为值 'x'。

```java
char firstChar = 'x';
```

## 8. 运行程序并解释它。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        char char01 = (char) 100;

        System.out.println(char01);

    }

}
```

输出：程序将输出：d
我们之所以能将整数强制转换为 `char`，是因为每个字符在 Unicode 及其各种编码方案中都映射了一个数值等。在这个例子中，我们看到 100 映射到字符 d。
建议读者查看前 127 个字符的 Unicode UTF-16 编码，并将这些值与 ASCII 表的前 127 个值进行比较。

- 运行以下类 PracticeYourJava {

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        char char01 = 'A';

        int num = char01; // 从 char 到整数的隐式转换

        System.out.println(num);

    }

}
```

输出：控制台将输出值：65
这是因为 Unicode UTF-16 对字符 'A' 的映射数值为 65。
此练习和上一个练习的目的是为了展示 `char` 类型与整数值之间的关系，在此期间使用了必需的强制转换。

- 使用 for 循环，打印数字 65 到 150 的等效字符。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        for (int j = 65; j < 150; j++) {

            System.out.println(j + " is equivalent to " + (char) j);

        }

    }

}
```

注意：你会发现当超过某个整数值时，控制台会为每个字符显示问号。这并不意味着这些值每一个都代表问号，而是由于控制台显示项目的方式，它无法显示这些字符（它们可以在 GUI 中显示）。

- 给定以下数组（见下方），打印数组中每个 `char` 的数值。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        char[] charArray1 = {'?', '1', '2', '3', '4', '5', '6', '7', '8', '9', '0', 'A', 'a', ';'};

        for (int j = 0; j < charArray1.length; j++) {

            System.out.println(charArray1[j] + " is equivalent to " + (int) charArray1[j]);

        }

    }

}
```

## Char 与 十六进制

编写一个程序，将十六进制值 20 赋值给变量。打印该变量。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        char char01 = 0x20;
```



# 练习你的 Java 1 级

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        char char01;

        Scanner in = new Scanner(System.in);

        System.out.print("Enter a character: ");

        char01 = in.next().charAt(0);

        System.out.printf("The character you typed: %c\n", char01);

    }

}
```

---

## 16. 编写一个程序向用户请求一个字符。分析它并告诉用户它是否为数字字符。
提示：`Character.isDigit`

```java
import java.util.Scanner;

public class PracticeYourJava {

    public static void main(String[] args) {

        char c01;

        System.out.print("Enter a character followed by the return key please: ");

        Scanner in = new Scanner(System.in);

        c01 = in.next().charAt(0); // 获取第1个字符。

        boolean isNumeric = Character.isDigit(c01);

        if (isNumeric) {

            System.out.println("The character you entered is a numeric character.\n");

        } else {

            System.out.println("The character you entered is not a numeric character.\n");

        }

    }

}
```

## 17. 编写一个程序向用户请求一个字符。分析该字符并告诉用户它是否为字母数字字符。
提示：`Character.isAlphabetic`, `Character.isDigit`

```java
import java.util.Scanner;

public class PracticeYourJava {

    public static void main(String[] args) {

        char c01;

        System.out.print("Enter a character followed by the return key please: ");

        Scanner in = new Scanner(System.in);

        c01 = in.next().charAt(0); // 获取第1个字符。

        boolean isAlphanumeric = (Character.isAlphabetic(c01)) || Character.isDigit(c01);

        if (isAlphanumeric) {

            System.out.println("The character you entered is an alphanumeric character.\n");

        } else {

            System.out.println("The character you entered is not an alphanumeric character.\n");

        }

    }

}
```

## 18. 编写一个程序向用户请求单个字符。分析并告诉用户它是否为空白字符。
提示：`Character.isWhitespace`

```java
import java.util.Scanner;

public class PracticeYourJava {

    public static void main(String[] args) {

        char c01;

        System.out.print("please enter a character: ");

        Scanner in = new Scanner(System.in);

        c01 = in.next().charAt(0); // 获取第1个字符。

        boolean isWhitespace = Character.isWhitespace(c01);

        if (isWhitespace == true)

            System.out.println("The character you entered is a whitespace\n");

        else

            System.out.println("The character you entered is not a whitespace\n");

    }

}
```

# 第 19 章：char 原生类型与 Character 类

## 19. 你有两个变量 c01 和 c02（用于测试它们的特定代码）。编写一个程序判断它们是否包含相同的值，并打印它们是否相等的输出。

```java
public class PracticeJava {

    public static void main(String[] args) {

        char c01 = 'x';

        char c02 = 'x';

        if (c01 == c02) {

            System.out.println("The characters are the same!");

        } else

            System.out.println("The characters are different!");

    }

}
```

OR

```java
public class PracticeJava {

    public static void main(String[] args) {

        char c01 = 'x';

        char c02 = 'x';

        if (Character.compare(c01, c02) == 0) {

            System.out.println("The characters are the same!");

        } else

            System.out.println("The characters are different!");

    }

}
```

# String/Char 关系

## 20. char 和 String 类型之间什么关系？
String 是一种看起来像是 char 序列/数组的数据类型，但事实并非如此。我们的答案如下：在上下文中描述其相似性，`char[]` 等同于 String。然而，存在方法可以在两种类型之间进行转换，并且有一种方法可以从 String 中提取单个字符作为 char 类型。

## 21. 说明 "x" 和 'x' 的区别。
"x" 指一个 String 对象。
'x' 指一个 char。

## 22. 编写一个程序将 char 'x' 转换为 String 并将其打印。
提示：`Char.toString` 或 `String.valueOf`

```java
public class PracticeJava {

    public static void main(String[] args) {

        char c01 = 'x';

        String s01 = Character.toString(c01);

        System.out.printf("%s\n", s01);

    }

}
```

```java
public class PracticeJava {

    public static void main(String[] args) {

        char c01 = 'x';

        String s01 = String.valueOf(c01);

        System.out.printf("%s\n", s01);

    }

}
```

## 编写一个程序将 "X" 转换为 char 类型的数组

```java
public class PracticeJava {

    public static void main(String[] args) {

        String s1 = "avier";

        char[] cArray1 = s1.toCharArray();

        for (int j = 0; j < cArray1.length; j++)

            System.out.print(cArray1[j]);

    }

}
```

## 23. 遍历 char 数组并逐个输出每个字符。
提示：`String.toCharArray` 练习你的 Java 1 级

```java
public class PracticeJava {

    public static void main(String[] args) {

        String s1 = "Xavier";

        char c01 = s1.charAt(1); // 第二个字符。

        System.out.println(c01);

    }

}
```

我有以下 String：`s1="Xavier"` 将 s1 中的第二个字符复制到 char c01 并打印 c01。提示：char

## 24. 将以下数组转换为 String：charArray1 = {'A', 'B', 'C', 'D', 'E', 'F', 'G'};

```java
public class PracticeJava {

    public static void main(String[] args) {

        char[] cArray1 = {'A', 'B', 'C', 'D', 'E', 'F', 'G'};

        String s1 = new String(cArray1);

        System.out.println(s1);

    }

}
```

OR

```java
import java.util.*;

public class PracticeJava {

    public static void main(String[] args) {

        char[] cArray1 = {'A', 'B', 'C', 'D', 'E', 'F', 'G'};

        String s1 = String.valueOf(cArray1);

        System.out.println(s1);

    }

}
```

## 26. 将以下数组转换为 String：charArray1 = {'A', 'B', 'C', 'D', 'E', 'F', 'G'};

```java
public class PracticeJava {

    public static void main(String[] args) {

        char[] cArray1 = {'A', 'B', 'C', 'D', 'E', 'F', 'G'};

        String s1 = String.valueOf(cArray1);

        System.out.println(s1);

    }

}
```

## 27. 有一个包含 "Hello are you?" 的 String 变量。编写一个程序反转这个字符串并打印结果。
提示：char 一方法是将 String 转换为数组。然后反向遍历数组并将字符添加到 String 中。

```java
public class PracticeJava {

    public static void main(String[] args) {

        String s1 = "Hello are you?";

        char[] cArray1 = s1.toCharArray();

        String reversed = "";

        for (int i = cArray1.length - 1; i >= 0; i--) {

            reversed += cArray1[i];

        }

        System.out.println(reversed);

    }

}
```

# 第 20 章：随机数

产生随机数的能力在许多场景中很重要，例如计算机游戏和加密应用。本章介绍了确保随机性的练习。

## 1. 随机生成器的初始化
以下随机生成器的初始化方法有什么区别？
1. 使用用户种子值
2. 使用内置的时间
在第一种情况下，你提供种子值。但如果你使用相同的值，随机生成器将简单生成相同的随机值。
在第二种情况下，你是在确保内置生成器的随机性，它确实使用了系统时作为输入之一。

## 2. JVM 确定种子，实例化随机生成器对象并打印它返回的前 10 个值。使用方法 `nextInt()`。

```java
import java.util.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        Random randomGenerator = new Random();

        int nextRandomValue;

        for(int count=0; count < 10; count++){

            nextRandomValue = randomGenerator.nextInt();

            System.out.println(nextRandomValue);

        }

    }

}
```

> 注意：观察到返回值可以是正或负，并跨越 int 的范围。

## 3. JVM 确定种子，实例化随机生成器对象并打印它返回的前 10 个 long 类型值。使用方法 `nextLong()`。

```java
import java.util.*;

public class PracticeYourJava {

    public static void main(String[] args) {

        Random randomGenerator = new Random();

        long nextRandomValue;

        for(int count=0; count < 10; count++){

            nextRandomValue = randomGenerator.nextLong();

            System.out.println(nextRandomValue);

        }

    }

}
```

> 注意：观察到返回值可以是正或负，并跨越 long 的范围。

## 4. 方法 `Random.nextDouble()` 跨越的值范围是多少？
值的范围是 0 到 1.0。

## 5. JVM 确定种子，实例化随机生成器随机生成器生成器并打印它返回的前 10 个值。使用方法 `Random.nextDouble()`。

```java
public static void main(String[] args) {

    Random randomGenerator = new Random();

    double nextValue;

    for(int count=0; count < 10; count++) {

        nextValue = randomGenerator.nextDouble();

        System.out.println(nextValue);

    }

}
```

## 6. 使用你任选的 int 值作为种子初始化随机数生成器，并打印由随机数生成器返回的前 10 个 `int` 类型的随机数。记录生成的数字。然后，运行该练习并记录生成的数字。对结果进行注释。

```java
import java.util.*;

public class PracticeJava {

    public static void main(String[] args) {

        Random randomGenerator = new Random(1234312);
    }

}
```



# 第 21 章 StringBuffer & StringBuilder

本章介绍了与 `StringBuffer` 和 `StringBuilder` 类相关的练习，它们是 `String` 类的可变对应。本章的编程练习将关注 `StringBuilder` 类，它虽然在外部功能上完全旧的 `StringBuffer` 类，但是一个更安全的类。

## 练习题

### 1. 描述 `StringBuffer` 类以及它与 `String` 类的关系和区别

`StringBuffer` 类支持与 `String` 类相同的内容，但 `StringBuffer` 类对象是可变的，而 `String` 类的对象是不可变的（String 对象的不可变性在第 5 章“String：基础处理”中讨论过）。由于可变性，当一个 `StringBuffer` 对象从一个方法传递到另一个方法时，接收方法可以更改其内容。`String` 对象是不可变的，因此它们不能被更改。

### 2. 当实例化一个 `StringBuilder` 对象时，它的默认容量是多少？

### 3. 如果向一个大于当前容量的 `StringBuilder` 中追加内容会发生什么？

### 4. 写一个程序，实例化一个名为 `sb01` 的 `StringBuilder`。打印它的容量。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder();

        System.out.println("the capacity is " + sb01.capacity());

    }

}
```

### 5. 写一个程序，实例化一个具有特定初始容量的 `StringBuilder`。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        StringBuilder sb02 = new StringBuilder(1000);

        System.out.println("the capacity is " + sb02.capacity());

    }

}
```

### 6. 给上面的 `StringBuilder` 对象确保其容量为 5000。打印它的容量。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        StringBuilder sb02 = new StringBuilder(1000);

        sb02.ensureCapacity(5000);

        System.out.println("the capacity is " + sb02.capacity());

    }

}
```

### 7. 解释 `trim()` 方法的使用。

### 8. `String` 的 `length()` 代表什么？

### 9. 给定 `s01 = "Mary had a lamb"`，实例化一个 `StringBuilder sb01`。打印 `sb01` 的长度。

```java
public class PracticeJava {

    public static void main(String[] args) {

        String s01 = "Mary had a lamb";

        StringBuilder sb01 = new StringBuilder(s01);

        System.out.println("the length is " + sb01.length());

    }

}
```

### 10. 给定 `s01 = "Mary had a lamb"`，实例化一个 `StringBuilder sb01`。打印 `s01` 的长度，并打印 `sb01` 的容量。

```java
public class PracticeJava {

    public static void main(String[] args) {

        String s01 = "Mary had a lamb";

        StringBuilder sb01 = new StringBuilder(s01);

        System.out.println("the length is " + s01.length());

        System.out.println("the length is " + sb01.length());

        System.out.println("the capacity is " + sb01.capacity());

    }

}
```

### 11. 给定 `s01 = "Mary had a lamb"`，实例化一个 `StringBuilder sb01`。`String` 和 `StringBuilder` 对象的长度匹配。

```java
public class PracticeJava {

    public static void main(String[] args) {

        String s01 = "Mary had a lamb";

        StringBuilder sb01 = new StringBuilder(s01);

        System.out.println("the length is " + s01.length());

        System.out.println("the length is " + sb01.length());

    }

}
```

### 12. 一个内容为 "Mary had a little lamb" 的 `StringBuilder` 对象。将该对象的内容复制到字符串 `s01`。

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb");

        String s01 = sb01.toString();

    }

}
```

### 13. 一个内容为 "Mary had a little lamb" 的 `StringBuilder` 对象。将一个包含 "nlittle lamb\nam"（故意漏了 "b"）的字符串 `s01` 追加到该 `StringBuilder` 对象中。打印生成的 `StringBuilder` 对象。

提示：方法 `append`

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb");

        String s01 = "\nlittle lamb\nlittle lamb";

        sb01.append(s01);

        System.out.println(sb01);

    }

}
```

### 14. 扩展上一个练习的解决方案，在上一个问题中的 `StringBuilder` 对象末尾添加字符 'b'。打印生成的 `StringBuilder`。

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb");

        String s01 = "\nlittle lamb\nlittle lamb";

        sb01.append(s01);

        char missingCharacter = 'b';

        sb01.append(missingCharacter);

        System.out.println(sb01);

    }

}
```

### 15. 将以下值以逗号分隔的形式放入 `StringBuilder` 对象 `sb01` 中：`double d01=7.594e12, float f01=1.61e14, int i01=823`。打印 `sb01` 并将其内容与输入进行比较。

```java
public class PracticeJava {

    public static void main(String[] args) {

        double d01 = 7.594e12;
        float f01 = 1.61e14;
        int i01 = 823;

        StringBuilder sb01 = new StringBuilder();

        sb01.append(d01);
        sb01.append(",");

        sb01.append(f01);
        sb01.append(",");

        sb01.append(i01);

        System.out.println(sb01);

    }

}
```

> **注释**：此练习的目的是让你看到数值类型的字符串表示可以放入 `StringBuilder` 对象中。

### 16. 我有以下 `StringBuilder` 对象：`StringBuilder sb01 = new StringBuilder("Mary had a little lamb");` 和 `StringBuilder sb02 = new StringBuilder("\nlittle lamb\nlittle lamb");` 将 `sb02` 的内容拼接到 `sb01` 上。打印 `sb01`。

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb");

        StringBuilder sb02 = new StringBuilder("\nlittle lamb\nlittle lamb");

        sb01.append(sb02);

        System.out.println(sb01);

    }

}
```

### 17. 将上一个解决方案中生成的 `StringBuilder sb01` 的前四个字符拷贝到 `String s01` 中。打印 `sb01`。

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb\nlittle lamb\nlittle lamb");

        String s01 = sb01.substring(0, 4);

        System.out.println(s01);

    }

}
```

### 18. 单词 "little" 在上一个练习的 `StringBuffer sb1` 中第一次出现的位置是在哪里？

提示：`StringBuffer.indexOf`

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        String searchword = "little";

        StringBuffer sb1 = new StringBuffer("Mary had a little\nlittle\nlittle lamb");

        int position = sb1.indexOf(searchword);

        System.out.printf("The position of %s is %d\n", searchword, position);

    }

}
```



## 19. 单词 "little" 在上一个练习的 StringBuffer sb1 中第二次出现的位置是在哪里？

提示：`StringBuffer.indexOf(String str, int fromIndex)`
确定先出现的位置，然后从那里开始开始。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        String searchword = "little";

        StringBuffer sb1 = new StringBuffer("Mary had a little\nlittle\nlittle lamb");

        int position = sb1.indexOf(searchword); // 第一次出现

        position = sb1.indexOf(searchword, position + searchword.length());

        // 我们在第一次出现之后搜索

        System.out.printf("The position of %s is %d\n", searchword, position);

    }

}
```

## 20. 单词 "little" 在上一个练习的 StringBuffer sb1 中最后一次出现的位置是在哪里？

提示：`StringBuffer.lastIndexOf`

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        String searchword = "little";

        StringBuffer sb1 = new StringBuffer("Mary had a little\nlittle\nlittle lamb");

        int position = sb1.lastIndexOf(searchword);

        System.out.printf("The last index of %s is %d\n", searchword, position);

    }

}
```

## 21. 单词 "little" 在上一个练习的 StringBuffer sb1 中第 n 次出现的位置是在哪里？

提示：与上一个练习类似，使用循环

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        String searchword = "little";

        StringBuffer sb1 = new StringBuffer("Mary had a little\nlittle\nlittle lamb");

        int occurrenceCounter = 0; // 我们在这里选择第 3 次。你可以更改它。

        int found = 0;

        int position = 0;

        int occurrence = 3;

        do {

            occurrenceCounter++;

            found = sb1.indexOf(searchword, position);

            if ((found != -1) && (occurrenceCounter < occurrence))

                position = found + searchword.length();

        } while ((occurrenceCounter < occurrence) && (found >= 0));

        if (found > 0)

            System.out.printf("The position is %d\n", position);

        else

            System.out.printf("There are not up to %d occurrences of %s here\n", occurrence, searchword);

    }

}
```

## 22. 给上一个例子中的相同的 StringBuffer 对象，将 StringBuilder 开头的单词 "Mary" 修改为 "John"。打印生成的 StringBuilder。
提示：`insert`

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb\nlittle lamb\nlittle lamb");

        sb01.insert(0, "John ");

        System.out.println(sb01);

    }

}
```

## 23. 将上一个练习中 StringBuilder sb01 开头的 "John & Mary" 替换为 "David"。
提示：`replace`

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("John had a little lamb\nlittle lamb\nlittle lamb");

        String oldStr = "John & Mary";

        String newStr = "David";

        sb01.replace(0, oldStr.length(), newStr);

        System.out.println(sb01);

    }

}
```

## 24. 如何反转字符串 original = "Hello you?"？ 使用 StringBuilder 的 reverse 方法打印它。

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        String original = "Hello you?";

        StringBuilder sb01 = new StringBuilder(original);

        sb01.reverse();

        System.out.println(sb01);

    }

}
```

## 25. 给值为 "Mary had a little lamb" 的 StringBuilder sb01 拷贝前 4 个字符到字符数组。
提示：`getChars`

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb");

        char[] array01 = new char[4];

        sb01.getChars(0, 4, array01, 0);

        System.out.println(array01);

    }

}
```

## 26. 从上一个练习的 StringBuffer 对象中删除 "had a little"。
提示：`delete`

```java
public class PracticeYourJava {

    public static void main(String[] args) {

        StringBuffer sb01 = new StringBuffer("Mary had a little lamb\nlittle lamb\nlittle lamb");

        String strToRemove = "had a little";

        int position = sb01.indexOf(strToRemove);

        if (position != -1) {

            sb01.delete(position, position + strToRemove.length());

        }

        System.out.println(sb01);

    }

}
```

## 27. 给值为 "Mary had a little lamb" 的 StringBuilder sb01 打印第 7 个字符。
提示：`charAt`

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb");

        char char01 = sb01.charAt(7);

        System.out.println("character is " + char01);

    }

}
```

## 28. 给值为 "Mary had a little lamb" 的 StringBuilder sb01 清空其内容。
提示：`length`

```java
public class PracticeJava {

    public static void main(String[] args) {

        StringBuilder sb01 = new StringBuilder("Mary had a little lamb");

        sb01.setLength(0);

        System.out.println(sb01);

    }

}
```

## 29. StringBuilder vs String 性能

我们要评估 `StringBuilder` 与 `String` 的性能。为此，编写一个执行以下操作的程序：

1. 创建一个 `StringBuilder` 测试对象。使用循环向其拼接 100,000 次 "A"。
2. 使用 `Duration` 对象测量代码运行所需的时间并打印到控制台。
3. 创建一个 `String` 测试并使用循环向其拼接 100,000 次 "A"。
4. 测量其运行时间并打印到控制台。注意时间差异。

接下来，运行循环计数器到 250,000 并注意时间差异。

```java
public class PracticeJava {

    public static void main(String[] args) {

        // 测量时长，Instant & Duration

        System.out.println("Testing StringBuilder concatenation time");

        StringBuilder sbTest = new StringBuilder("A");

        Instant startInstant = Instant.now();

        long numElements = 100000;

        for (long counter = 0; counter < numElements; counter++) {

            sbTest.append("A");

        }

        Instant finishInstant = Instant.now();

        Duration duration0 = Duration.between(startInstant, finishInstant);

        System.out.println("Time (StringBuilder) " + numElements + " characters = " + duration0);

        String aTest = "A";

        startInstant = Instant.now();

        for (long counter = 0; counter < numElements; counter++) {

            aTest += "A";

        }

        finishInstant = Instant.now();

        Duration duration1 = Duration.between(startInstant, finishInstant);

        System.out.println("Time (String) " + numElements + " characters = " + duration1);

    }

}
```



备注：可以清楚看到，`StringBuilder` 的拼接速度远比 `String` 快。在字符串操作次数有限的场景下，`String` 是一个可以接受的选择。但有一点是：如果你存储字符串数据的对象的引用引用对你很重要，并且你希望它在整个程序中保持不变，请使用 `StringBuilder` 对象。

## 30. 总的来说，`StringBuilder` 类和 `StringBuffer` 类之间有什么相似点和区别？更倾向于使用哪一个？为什么？

`StringBuffer` 类和 `StringBuilder` 类在功能上本质是相同的，但 `StringBuilder` 类在内部实现上是 `StringBuilder` 更现代的版本。特别是 `StringBuilder` 为线程提供了更好的支持。因此，在两者之间，`StringBuilder` 是首选的类。正如本章的练习所示，我们在练习中使用更现代的 `StringBuilder`。

# 第 22 章 类

Java 是一种面向对象的语言，类和对象的概念是它的核心。这是一个非常重要的概念，因为它提出的练习涵盖了类的概念（本章中的顶层类）及其类型、类（对象）、类/对象的成员访问权限、构造函数、初始化器、继承、多态以及其他关键相关主题。

请注意，本章中的练习应按顺序完成，因为本章的后续练习通常建立在之前的练习基础之上。

鉴于本章涵盖的主题和子主题很多，在每个节之后都提供了涵盖主题的简要总结。

读者应该注意，这是书中两个讨论类主题的章节之一。

## 1. 在 Java 中，什么是类？

类是一种数据结构，可以将 Java 成员（即：字段、方法、构造函数、初始化器，以及实现的接口）组合在单个单元中。类是动态创建的类实例的“模板”；这些实例被称为对象。类支持继承概念，这是一种机制，派生类可以获得其所继承的类（称为“父类”）的功能，并根据需要增强所继承的功能。

## 2. 在 Java 中，什么是包？

包是类型的分组（通常是所有的类、枚举和接口）。程序员决定你想在包中分组的类型（参见第 1 章的练习 2）。

## 3. 描述类的潜在成员。

1. 常量 — 与类关联的常量值（例如 `Math.PI`），或与实例关联的常量值
2. 字段 — 类或其实例的变量
3. 方法 — 属于类（静态方法）或其实例的独立方法块
4. 构造函数 — 在类实例实例化时调用的特殊方法
5. 静态初始化块 — 初始化类变量的代码块
6. 初始化块 — 用于初始化实例变量的代码块（它们与构造函数配合工作）
7. 类型 — 其他类，以及实现的接口

注意：并不是所有这些成员都要求在某处同时存在于给定的类中。

## 4. 在 Java 中，可以在另一个类内部定义类吗？

是的。（在上面练习 3 的解答中已提到一个类可以在其内部定义其他类）。

## 5. 解释“顶层”类的概念

顶层类简单指的是不是定义在另一个类内部的类。（在上面练习 3 的解答中已提到一个类可以在其内部定义其他类。这里定义的所有类都是顶层类。）

## 6. 什么是嵌套类？

嵌套类的简要描述是“定义在另一个类内部的类”。我们将在第 24 章“类 II”详细查看不同类型的嵌套类。

## 7. 顶层类访问修饰符

解释以下每个顶层类访问修饰符的含义：

### 1. public

### 2. package-private

该类只能被其所在相同包中的其他项访问。注意：“package-private”在我们的代码中并没有显式写出来，相反，如果没有指定 `public`，则该类的默认类访问级别就是 `package-private`。结论：如果你想让类是 `package-private`，则在它的定义中不要添加任何访问修饰符。

## 8. 类成员访问修饰符

描述以下每个类访问修饰符：

### 1. public

所涉及的类成员可以被任何地方的任何其他类直接访问，无论是子类（稍后看子类的概念）、包含该类的包中的其他类型，还是任何包中的类型。总结来说，任何地方的任何事物都可以访问访问级别为 `public` 的成员。

### 2. protected

可以被其类成员、子类或其所属包的成员访问（与 `public` 形成对比）。

### 3. 未指定修饰符

所涉及的类成员只能被其类及其所在包的成员访问；具有此未指定权限的类的子类无法访问，除非子类在相同的包中！这种访问级别被称为“package-private”。

### 4. private

成员只能由其所属的类本身的元素直接访问。

为了回顾，请注意访问级别是按限制程度从小到大的顺序列出的。应当理解为成员的访问级别低于其所属类的访问级别。例如，如果一个类的访问级别是 `public`，但其包含的类访问级别是 `package-private`，那么类成员的访问级别仍然限制为 `package-private`。

> **刚练习的概念总结**：类的定义。包的定义。潜在类成员。类访问修饰符。

## 9. 创建一个名为 `Vehicle` 的公类的大纲。

```java
public class Vehicle {
    // 名为 Vehicle 的公类的基本大纲
}
```

## 10. 在之前创建的公类 `Vehicle` 中添加以下字段：

1. 一个名为 `license` 的私有 String
2. 一个名为 `chassisNumber` 的私有 String
3. 一个类型为 `VehicleTypes` 的私有枚举 `vehicleType`。定义如下：

```java
public enum VehicleTypes {
    BICYCLE, MOTORBIKE,
    CAR, TRUCK, BOAT,
    TRAIN, TRAILER,
    AIRPLANE;
}
```

4. 一个名为 `color` 的私有 String
5. 一个名为 `numberOfWheels` 的私有 short 字段

```java
public class Vehicle {
    private String license;
    private String chassisNumber; // 车辆识别码
    private VehicleTypes vehicleType;
    private String color;
    private short numberOfWheels;
}
```

## 11. 说明为什么没有类可以访问我们刚刚定义的 `Vehicle` 类对象的字段。

这种无法访问的原因是因为我们为该类定义的每个字段的访问级别都是 `private`，因此 `Vehicle` 类任何对象的字段只能由该对象的其他成员访问。

## 12. Java 中赋值给对象中字段的默认值是什么？

基本数据类型的默认值是 `0`。对象引用字段的默认值是 `null`。

## 13. 在任何类中都存在的、在创建类实例时自动调用的特殊方法的标题（名称）是什么？

它被称为构造函数。

## 14. 构造函数的作用是什么？

构造函数用于对新实例化的对象执行初始化操作。在实例化对象时，可以将初始化参数传递给构造函数。例如，如果你有一个代表人的类，因此有人的姓和名的字段，你的构造函数可以在对象初始化时接收这些字段的值以初始化对象。除了初始化新实例化的对象外，构造函数可以在实例化时根据需要对程序的任何其他部分执行任何操作；它不仅限于对象的初始化。

## 15. 构造函数在对象生命周期的哪一点被调用？

它在对象实例化时自动被调用。

## 16. Java 中一个类可以有多少个构造函数？

类可以拥有的最少构造函数数量是 1，每个类必须至少有一个构造函数。如果程序员没有为类定义任何构造函数，编译器会自动创建一个；编译器创建的被称为默认构造函数，因为它是默认创建的。它不接受任何参数。

## 17. 构造函数可以重载吗？

是的，构造函数可以像任何方法一样被重载。

## 18. 解释重载构造函数的必要性。

这就像方法重载；你需要重载构造函数以适应你在实例化对象时想要初始化的不同输入值和类型。例如，如果我有一个名为 `lastName`、`firstName` 和 `age` 的字段类，我可以拥有以下构造函数：

```java
public Person(String lastName, String firstName);
public Person(String lastName, int age);
public Person(String lastName, String firstName, int age);
```

## 19. 对于 `Vehicle` 类，其任何构造方法的名称会是什么？

构造方法的名称始终与类本身相同。构造函数是唯一与其所属类名称相同的方法。

## 20. 构造函数的返回类型是什么？

构造函数没有任何返回类型（甚至没有 `void`）。

## 21. 什么是无参数构造函数？

无参数构造函数是不传递任何参数的构造函数。它是当不带参数实例化对象时调用的构造函数。例如我们有：

```java
Vehicle v0 = new Vehicle(); // 使用无参数构造函数实例化的示例
// 括号内没有参数。
```

程序员可以创建无参数构造函数，也可以留给编译器隐式创建（如果程序员没有定义任何构造函数，Java 会这样做）。例如，由于我们没有为 `Vehicle` 类显式定义任何构造函数，Java 实际上创建了一个无参数构造函数，它只有在程序员没有为该类定义任何构造函数时才会这样做。

# 练习你的 Java 级别 1

## 22.（重要）描述构造函数被调用时所执行的操作。

在 Java 中，对象的创建会调用其构造函数，其首要任务是在运行自身方法体之前，先调用其父类中指定的构造函数（默认是无参数构造函数）。父类的构造函数反过来又调用其父类中指定的构造函数（默认是无参数构造函数）；在运行自身方法体之前，以及在其直接父类中的构造函数，在运行自身方法体之前，一直到继承层次结构的顶端，即 `Object` 类是所有类的终极祖先类。简而言之，每个祖类的构造函数从类继承层次顶端（始终是 `Object` 类）的构造方法体开始，到实例化对象的构造方法体结束。如果直接父类没有无参数构造函数，且你也没有在自己的构造函数中指定调用父类中的另一个构造函数，你的代码将无法编译。

## 23. 描述什么是默认构造函数、它的性质（参数数量、访问级别）以及被调用时的操作。此外，一旦你为类创建/定义了构造函数，默认构造函数会发生什么？

如前所述，这是一个由编译器自动创建的构造函数，仅当类没有任何程序员定义的构造函数时才会创建。使用我们创建的 `Vehicle` 类示例，我们是否为它定义了构造函数？由于我们没有定义，编译器将隐式创建该类，因此我们可以实例化 `Vehicle` 类的对象。默认构造函数的特征如下：

1. 它不接受任何参数
2. 它的访问级别为 `public`
3. 在运行自身方法体之前，它将调用其直接父类的无参数构造函数，这是所有构造函数的默认操作，正如练习解答所示。

一旦你为给定的类定义了构造函数，Java 期望该类创建的任何对象都将调用程序员定义的构造函数之一。例如，如果你为 `Vehicle` 类定义了以下构造函数：

```java
public Vehicle(String vehicleColor) {
    color = vehicleColor;
}
```

那么你无法进行以下实例化：

`Vehicle v01 = new Vehicle();`

你之所以不能这样做，是因为你已经为该类定义了至少一个构造函数，Java 将永远不会为它创建默认构造函数。但是，你可以自由创建自己的无参数构造函数。

## 24. 对于之前创建的类，如果你没有为该类定义构造函数，那么新实例化的 Vehicle 的 numberOfWheels 和 color 字段将具有什么值？

`numberOfWheels` 的取值为 `0`，`color` 初始化为 `null`。这些值的原因是字段值被设置为它们对应类型的默认值。

## 25. 为 Vehicle 类编写一个公有无参数构造函数大纲。此构造函数不需要执行任何操作。

```java
public Vehicle() {
}
```

如你所示，构造函数没有指定返回类型。

## 26. 关键字：`this` 关键字是什么意思？如何使用？

`this` 关键字意味着“我们正在处理的这个对象”。它被用于实例方法内部，以引用与方法相关的实例。以下是使用它的几种场景：

### 场景 1：字段与参数的歧义

例如，我有一个 `Car` 类，其中定义了一个字段：

```java
class Car {
    private String color;
}
```

如果该类有一个方法 `setColor(String color){...}`，其功能是设置 `Car` 的 `color` 字段，那么问题出现了，因为方法声明中的参数名与类本身的字段名匹配。你看到我们不能说：

```java
setColor(String color) {
    color = color;
    // 我们的意图是第一个 color 是对象字段，第二个 color
    // 是传递给方法的参数。但编译器无法判断哪个是哪一个。
}
```

这样的陈述具有混淆性，因为它不确定等式两边引用的是哪个字段或变量 `color`，因为它必须问：“我正在处理的是哪一个，字段还是方法声明中的参数？”因此，我们使用 `this` 如下所示影响方法：

```java
setColor(String color) {
    this.color = color; // 表示对象的 color（左侧）= 传递的参数 color 的值
}
```

### 场景 2：传递所属类的对象

有时，实例需要将它所属的那个对象本身传递给另一个方法。记住，当前的对象指的是这个 `this`。对象受影响的方式可以在代码片段所示：

```java
class Car {
    void sendMeElsewhere() {
        sendOff(this); // 方法 sendOff 接收
        // Car 类的对象作为参数
    }
}
```

### 场景 3：调用重载构造函数

在某些场景下，需要从同一个类的另一个构造函数内部调用该类的构造函数。在这种情况下 `this` 就会派上用场。调用兄弟构造函数是显式构造函数调用。我们将在本章后面看到这个概念的应用。

## 27. 解释显式构造函数调用的概念。

显式调用是一个短语，用于描述从同类的另一个构造函数调用该类的构造函数，即你正在直接调用你的其中一个重载构造函数方法。

## 28. 创建一个类，接收并设置之前定义的类的字段。

## 29. （原文缺失，或由流程暗示）

## 30. 为 Vehicle 类添加一个名为 `setChassisNumber` 的公有方法。该方法应该设置 `chassisNumber`。方法的返回类型应为 void。

```java
public void setChassisNumber(String chassisNumber) {
    this.chassisNumber = chassisNumber;
}
```

## 31. 在 Vehicle 的无参数构造函数中创建一个打印“I am a Vehicle!”的行。

```java
public Vehicle() {
    System.out.println("I am a Vehicle!");
}
```

## 32. 在 Vehicle 类的方法中创建一个该类的实例，命名为 v01。使用无参数构造函数实例化。控制台输出是什么？

```java
// Vehicle 类的 main 方法
public static void main(String[] args) {
    Vehicle v01 = new Vehicle();
}
```

输出为：“I am a Vehicle”，这是无参数构造函数执行的内容。

> **练习的概念**：定义、构造函数行为、默认构造函数、无参数构造函数、显式构造函数调用、方法、`this` 关键字、对象实例化。

## 33. 在 Java 中，继承的概念是什么？

继承是 Java 的一种功能，允许一个类指定为现有类（称为其父类）的后类。通过继承，子类继承了父类的组件。子类可以自由创建任何所需的功能，并在某些限制范围内覆盖所继承的内容。例如，如果你想将 `Car` 类声明为 `Vehicle` 类的后类，你可以定义如下：

```java
public class Car extends Vehicle {
}
```

观察 `extends` 关键字的使用，它用于扩展继承。

注意：在 Java 中，官方规定子类不继承父类的私有成员，但从实际角度来看，它继承了。问题在于对父类私有成员的直接访问；除非父类提供了访问这些私有成员的方法，否则无法直接访问。

## 34. 多重继承的概念是什么？

多重继承是计算机语言中的一种功能，允许给定类拥有多个父类并继承其所有父类的成员。

## 35. Java 是如何实现继承的？

Java 不支持多重继承。它支持单继承，即一个类只能有一个直接父类。请注意，接口的概念似乎具有与多重继承相似的效果。我们将在后面的章节中查看接口的概念。

## 36. （子类创建）创建一个名为 Car 的公有类，它是之前创建的 Vehicle 类的子类。

提示：关键字 `extends`

```java
public class Car extends Vehicle {
}
```

## 37. 创建类 `Motorcycle` 作为 `Vehicle` 类的子类。给它一个无参数的构造函数，将字段 `vehicleType` 设置为值 `MOTORBIKE`。该构造函数还应该将字段 `numberOfWheels` 设置为 `2`。



```java
public class Motorcycle extends Vehicle {
    public Motorcycle() { // Constructor函数
        vehicleType = VehicleTypes.MOTORBIKE;
        numberOfWheels = 2;
    }
}
```

### 38. 创建类 `Train` 作为 `Vehicle` 类的子类。创建一个构造函数，将字段 `vehicleType` 设置为值 `TRAIN`。

```java
public class Train extends Vehicle {
    public Train() { // Constructor函数
        vehicleType = VehicleTypes.TRAIN;
    }
}
```

### 39. 类继承中的问题：使用父类的方法作为自己的方法。给定以下类，预测代码的输出并解释为什么会有该输出。

```java
public class A {
    public void print() {
        System.out.println("I am class A!");
    }
}
```

```java
public class B extends A {
    public static void main(String args[]) {
        B obj01 = new B();
        obj01.print();
    }
}
```

**输出：**
I am class A

**解释：**
如示例所示，类 `B` 继承自类 `A`。发生这种情况时，子类对象继承父类的方法并将其作为自己的方法，这就是为什么我们在编写 `obj01.print();` 这一行代码时，可以像它是类 `B` 的直接成员一样使用该继承的方法。

### 40. 重写父类方法。给定以下类，预测此代码的输出并解释为什么会有该输出。

```java
public class A {
    public void print() {
        System.out.println("I am class A!");
    }
}
```

```java
public class B extends A {
    public void print() {
        System.out.println("I am class B!");
    }
}
```

```java
public static void main(String args[]) {
    B obj01 = new B();
    obj01.print();
}
```

**输出：**
I am class B

**解释：**
如示例所示，类 `B` 继承自类 `A`。也可以看到类 `B` 声明了一个方法 `print()`，它与其父类中的方法同名。

在 Java 中，当子类重用父类中非静态方法的名称时，这被称为重写（overriding）。Java 将类 `B` 中的重写方法识别为属于类 `B` 对象的方法，因此它打印出 "I am class B"。

### 41. `final` 组件的行为

给定以下类，预测此代码的输出并解释你的观察结果。

```java
public class A {
    public final void println() {
        System.out.println("I am class A!");
    }
}

public class B extends A {
    public void println() {
        System.out.println("I am class B!");
    }
}

public static void main(String[]){
    B obj1 = new B();
    obj1.println();
}
```

**观察：**
代码将无法编译。

**解释：**
我们在类 `A` 中将方法 `println` 声明为 `final` 方法。声明为 `final` 的方法不能在后代类中被重写。

**你练习的概念总结：** 继承、方法重写、关键字 `extends` 和 `final`（即 `final` 方法）。

### 42. 修改 `Vehicle` 类的 `main` 方法以实例化之前声明的 `Car` 类对象 `car01`。观察并解释代码的输出。

```java
public static void main(String[]) {
    Car car01 = new Car();
}
```

**输出：**
I am a Vehicle!

**解释：**
正如练习 21 的解决方案中所述，每当实例化任何类的对象时，该类的构造函数会在运行自身体之前，首先调用其父类中所有的构造函数（是的，你可以选择调用父类中的哪个构造函数，我们将在后面的练习中看到）。如果没有显式指定要调用的父构造函数，将调用父类的无参数构造函数，正如本练习的输出所示。此外，无论调用哪个父类构造函数，它都会在运行自身体之前调用其父类中指定的构造函数（无参数的是默认的），并以此类推递归地调用指定的构造函数直到到达对象层次结构的顶端。

在接下来的练习中进一步研究此主题。

### 43. 预测以下代码的输出：

```java
public class X {
    public X() {
        System.out.println("Class X: Parameterless constructor!");
    }
    public X(int x) {
        System.out.println("Class X: The constructor that takes an integer!");
    }
}

public class Y extends X {

    public Y() {
        System.out.println("Class Y: Parameterless constructor!");
    }

    public static void main(String args[]){
        Y obj = new Y();
    }
}
```

**输出：**
Class X: Parameterless constructor!
Class Y: Parameterless constructor!

此练习与之前的练习类似，因为它展示了当实例化一个对象时，对象的构造函数默认是其父类的无参数构造函数，正如输出中所观察到的它运行本身。

**注意：** 如之前所述，我们可以指定想要调用的父类构造函数；我们将在练习 46 中看到。

### 44. 预测以下代码的输出：

```java
public class W {
    public W() {
        System.out.println("Class W: Parameterless constructor!");
    }
    public W(String str) {
        System.out.println("Class W: The constructor that takes a String!");
    }
}

public class X extends W {
    public X() {
        System.out.println("Class X: Parameterless constructor!");
    }
    X(int x) {
        System.out.println("Class X: The constructor that takes an integer!");
    }
}

public class Y extends X {
    public Y() {
        System.out.println("Class Y: Parameterless constructor!");
    }

    public static void main(String args[]){
        Y obj = new Y();
    }
}
```

**输出：**
Class W: Parameterless constructor!
Class X: Parameterless constructor!
Class Y: Parameterless constructor!

此练习展示了之前提到的：实例化对象时，会递归调用每个祖先类的构造函数，最后以我们实例化的类的构造函数结束。

## 第22 章：类 I

### 45. (使用 `super` 关键字调用父类构造函数)

之前的练习中提到可以通过子类构造函数调用父类构造函数。简要描述这种调用是如何实现的。

### 练习 Java 1

### 46. 预测以下代码的输出：

```java
public class X {
  public X() {
    System.out.println("Class X: Parameterless constructor!");
  }
  public X(int x) {
    System.out.println("Class X: The constructor that takes an integer!");
  }
  public X(float x) {
    System.out.println("Class X: The constructor that takes a float!");
  }
}
public class Y extends X {
  public Y() {
    super(5); // 注意构造函数中的这一行。super 调用必须是第一行。
    System.out.println("Class Y: Parameterless constructor!");
  }
  public static void main(String args[]){
    Y obj = new Y();
  }
}
```

**输出：**
Class X: The constructor that takes an integer!
Class Y: Parameterless constructor!

`super` 在此处用于指定要使用父类的哪些构造函数。在这种情况下，通过 `super`，我们调用了我们想要的父类构造函数；在本例中接收 `int` 输入的 `super` 构造函数。应该注意，如果我们显式地调用父类中的构造函数，父类的无参数构造函数将不再运行。

### 47. 使用 **super 访问直接父类中被重写的方法**。给定以下类定义，说明程序的预期输出。

```java
public class Parent {
  int x=25;
  public void printValue() {
    System.out.println("x in the parent is " + x);
  }
}
public class Child extends Parent {
  int x=120;
  public void printValue() {
    System.out.println("x in the child is " + x);
    super.printValue();
  }
  public static void main(String[] args[]){
    Child child1 = new Child();
    child1.printValue();
  }
}
```

**输出：**
x in the child is 120
x in the parent is 25

从此练习的输出可以看出，`super` 关键字可以访问直接父类中重写的方法，该方法名与被访问的父类方法所属的子类中的方法名相同。

#### 在什么情况下使用 `super` 关键字？

提示：*参考前几个练习。*

`super` 关键字在以下情况下使用：

1. 子类中的构造函数可以调用其父类中选定的构造函数。
2. 子类中的方法可以使用它来调用父类中的方法，而子类通过重用同名方法隐藏了该方法。

#### Java 中所有类的终极祖先类是什么？

Java 中所有类的终极祖先类是 `Object` 类。该类提供了许多方法，每个后代都继承了这些方法。建议读者查看 Java 官方文档以了解该类提供的方法，特别是 `toString` 和 `getClass` 方法。我们在此处隐式地使用了 `toString`：我们将在本章稍后部分使用 `getClass` 方法。

```java
// 以下代码无法编译。解释为什么它无法编译。
public class A {
    public A(int x) {
        return;
    }
    // 这里我们为该类定义了一个非无参数构造函数。
    // 因此，现在该类只有一个构造函数了，因为一旦我们自己
    // 定义了构造函数，Java 不再负责为我们创建
    // 无参数构造函数。
}

public class B extends A {
    static void main(String[] args) {
        B obj = new B();
    }
}
```

（注意类 A 只定义了一个构造函数，且该构造函数带有参数，而类 B 只有默认构造函数）
请准确地说明，父类 A 中没有供子类 B 的构造函数调用的构造函数（B 自己有一个编译后的默认构造函数）。问题的详细解释见下方。
之前提到，一旦程序员为某个类定义了构造函数，编译器就不再承担为该类提供无参数构造函数的责任。因此，示例中的类 A 没有无参数构造函数。这并不是错误，但在本示例中，它是问题的一部分。我们知道，当创建给定类的对象时，该对象默认会尝试调用其父类的无参数构造函数。在上面的代码中，问题在于当实例化 B 的对象时，类 A 中没有可供调用的无参数构造函数。

#### 上一个练习代码无法编译的解决方案是什么？

有两种解决方案。它们是：
1. 在父类中创建一个无参数构造函数。
2. 在类 B 的构造函数中使用 `super` 关键字调用子类中存在的唯一构造函数（参见练习 45）。

# 练习你的 Java 水平 1

**刚刚练习的概念总结：** 对象实例化、与父类构造函数交互的更多详细信息、方法、关键字。

### 为 `Vehicle` 类编写单独的 public 方法，以返回以下每一项：1. license 2. chassisNumber 3. vehicleType 4. color 5. numberOfWheels 为 `Vehicle` 类添加方法。分别命名为 `getChassisNumber`、`getVehicleType`、`getColor` 和 `getNumberOfWheels`。

方法如下：

```java
public String getLicense() {return(license);}

public String getChassisNumber() {return(chassisNumber);}

public VehicleType getVehicleType() {return (vehicleType);}

public String getColor() {return (color);}

public short getNumberOfWheels() {return(numberOfWheels);}
```

### 除了练习 29 和 30 中编写的分别为字段 `license` 和 `chassisNumber` 设置值的方法外，还为 `Vehicle` 类编写单独的 public 方法来设置以下每一项：

- 1. VehicleType
- 2. color
- 3. numberOfWheels

方法命名为 `setVehicleType`、`setColor` 和 `setNumberOfWheels`。它们的返回类型应为 `void`。

```java
public void setVehicleType(VehicleTypes vt) {
    vehicleType = vt;
}

public void setColor(String color) {
    this.color = color;
}

public void setNumberOfWheels(short numberOfWheels){
    this.numberOfWheels = numberOfWheels;
}
```

### 对于之前创建的 `car01`（参见练习 42），增强 `Vehicle` 类 `main` 方法中的代码，处理其字段 `vehicleType`、`numberOfWheels` 并使用练习 52 中定义的方法。解释程序的输出结果。

在 `Vehicle` 类中添加以下代码行：

```java
System.out.println("Vehicle type=" + car01.getVehicleType());
System.out.println("Number Of Wheels=" + car01.getNumberOfWheels());
System.out.println("color=" + car01.getColor());
```



## 第 22 章：类 I

### 55. 为 `Car` 类创建一个无参数构造函数

让它将枚举字段 `vehicleType` 设置为值 `CAR`，并将字段 `numberOfWheels` 设置为 4。重新运行上一个练习的代码。解释程序的输出。

```java
public class Car extends Vehicle {

    // 此处是类的其他部分

    public Car() { // 构造函数
        vehicleType = VehicleTypes.CAR;
        numberOfWheels = 4;
    }
}
```

**输出**
```
I a Vehicle!
Vehicle type=CAR
numberOfWheels=4
color=null
```

**解释**
- 第 1 行：现在调用了我们为 `Car` 定义的无参数构造函数。但在它运行之前，会调用父类的无参数构造函数。父类构造函数打印字符串 "I a Vehicle"。
- 第 2 行：字段 `vehicleType` 被初始化为 `VehicleTypes.CAR`。
- 第 3 行：`numberOfWheels` 初始化为 4。
- 第 4 行：由于我们没有显式初始化它，`color` 字段保持 `null`。

---

### 56. 重载构造函数

为 `Car` 创建一个接受 `chassisNumber`、`license` 和 `color` 参数的构造函数。在类的 `main` 方法中创建一个实例 `car02`：

```java
public class Car extends Vehicle {

    // 此处是类的其他部分

    public Car() { // 构造函数
        vehicleType = VehicleTypes.CAR;
        numberOfWheels = 4;
    }

    public Car(String chassisNumber, String license, String color) {
        this.chassisNumber = chassisNumber;
        this.license = license;
        this.color = color;
    }
}

Car car02 = new Car("VIN11232", "DRV0123A432", "blue");

System.out.println("vehicle type=" + car02.getVehicleType());
System.out.println("Number Of Wheels=" + car02.getNumberOfWheels());
System.out.println("color=" + car02.getColor());
System.out.println("license=" + car02.getLicense());
System.out.println("chassisNumber=" + car02.getChassisNumber());
```

**输出**
```
I a Vehicle!
VehicleType=null
numberOfWheels=0
color=blue
license=DRV0123A432
chassisNumber=VIN11232
```

**解释**
问题是父类 A 中没有供子类 B 的构造函数调用的无参数构造函数（B 自己有一个编译后的默认构造函数）。问题的详细解释见下方。

之前提到，一旦程序员为某个类定义了构造函数，编译器就不再承担为该类提供无参数构造函数的责任。因此，示例中的类 A 没有无参数构造函数。这并不是错误，但在本示例中，它是问题的一部分。我们知道，当创建给定类的对象时，该对象默认会尝试调用其父类的无参数构造函数。在上面的代码中，问题在于当实例化 B 的对象时，类 A 中没有可供调用的无参数构造函数。

**上一个练习代码无法编译的解决方案是什么？**
有两种解决方案：
1. 在父类中创建一个无参数构造函数。
2. 在类 B 的构造函数中使用 `super` 关键字调用子类中存在的唯一构造函数（参见练习 45）。

---

# 练习你的 Java 水平 1

刚刚练习的概念总结：对象实例化、与父类构造函数交互的更多详细信息、方法、关键字。

### 练习题 1

为 `Vehicle` 类编写单独的 public 方法，以返回以下每一项：
1. license
2. chassisNumber
3. vehicleType
4. color
5. numberOfWheels

为 `Vehicle` 类添加方法。分别命名为 `getChassisNumber`、`getVehicleType`、`getColor` 和 `getNumberOfWheels`。

**方法如下：**

```java
public String getLicense() {
    return license;
}

public String getChassisNumber() {
    return chassisNumber;
}

public VehicleType getVehicleType() {
    return vehicleType;
}

public String getColor() {
    return color;
}

public short getNumberOfWheels() {
    return numberOfWheels;
}
```

### 练习题 2

除了练习 29 和 30 中编写的分别为字段 `license` 和 `chassisNumber` 设置值的方法外，还为 `Vehicle` 类编写单独的 public 方法来设置以下每一项：
- 1. VehicleType
- 2. color
- 3. numberOfWheels

方法命名为 `setVehicleType`、`setColor` 和 `setNumberOfWheels`。它们的返回类型应为 `void`。

```java
public void setVehicleType(VehicleTypes vt) {
    vehicleType = vt;
}

public void setColor(String color) {
    this.color = color;
}

public void setNumberOfWheels(short numberOfWheels) {
    this.numberOfWheels = numberOfWheels;
}
```

### 练习题 3

对于之前创建的 `car01`（参见练习 42），增强 `Vehicle` 类 `main` 方法中的代码，处理其字段 `vehicleType`、`numberOfWheels` 并使用练习 52 中定义的方法。解释程序的输出结果。

在 `Vehicle` 类中添加以下代码行：

```java
System.out.println("Vehicle type=" + car01.getVehicleType());
System.out.println("Number Of Wheels=" + car01.getNumberOfWheels());
System.out.println("color=" + car01.getColor());
```

**输出**
```
I am a Vehicle!
VehicleType=null
numberOfWheels=0
color=null
```

**解释**
输出的原因如下：
- 第 1 行：这是因为调用了父类的参数构造函数（这在练习 42 的解答中解释过）。
- 第 2 行：我们没有修改这个字段，因此它保持默认值 `null`（枚举是对象）。
- 第 3 行：我们没有修改这个原始类型字段，因此它仍然保持默认值 0。
- 第 4 行：同样，如果没有显式初始化，`String` 字段作为对象引用会被初始化为 `null`。

**注意**：再次观察到，由于继承，`Car` 类对象继承了其父类的方法并将其作为自己的方法使用。



# 练习你的 Java 1级

## 第 22 章：类 I

### 57. 从另一个构造函数调用重载构造函数

#### 55. 为 `Car` 创建无参数构造函数
让它将枚举字段 `vehicleType` 设置为值 `CAR`，并将字段 `numberOfWheels` 设置为 4。重新运行上一个练习的代码。解释程序的输出。

**提示**：`this();`

```java
public class Car extends Vehicle {
    // 此处是类的其他部分
    public Car() { // 构造函数
        vehicleType = VehicleTypes.CAR;
        numberOfWheels = 4;
    }
    public Car(String chassisNumber, String license, String color) {
        this(); // 这是调用一个重载构造函数，在此情况下恰好是
        this.chassisNumber = chassisNumber;
        this.license = license;
        this.color = color;
    }
}
```

在 `main` 中有：

```java
Car car02 = new Car("VIN112322","DRV0123A432","blue");

System.out.println("vehicle type=" + car02.getVehicleType());
System.out.println("Number Of Wheels=" + car02.getNumberOfWheels());
System.out.println("color=" + car02.getColor());
System.out.println("license=" + car02.getLicense());
System.out.println("chassisNumber=" + car02.getChassisNumber());
```

**输出**

```text
I am a Vehicle!
VehicleType=CAR
numberOfWheels=4
color=blue
license=DRV0123A432
chassisNumber=VIN11232
```

输出是预期的。

**解释**

我们没有拷贝这些代码行：

```java
vehicleType = VehicleTypes.CAR;
numberOfWheels = 4;
```

这些已经存在于无参数构造函数中的代码，我们通过在构造器中添加以下代码来调用该无参数构造函数的：

```java
this(<constructor parameters>);
```

---

### 58. 类修饰符

解释每个类修饰符的含义：

1.  `abstract`（抽象）
2.  `final`（最终）

**注意**：还有一个类修饰符 `static`，我们将在嵌套类中查看它，因为它不适用于顶层类。

1.  **abstract** - 一个我们希望不被实例化的类。它的成员可以被实例化，也可能不会；但是，使用此修饰符，其中定义的成员无法被调用。只有抽象类的非抽象子类可以被实例化。
2.  **final** - 其他类不能从该类中派生（即它不能有子类）。

**注意**：任何可以实例化的类（即任何非抽象类）都称为“具体类”。

---

### 59. 类成员修饰符

这些类成员修饰符分别什么意思？

1.  `abstract`
2.  `final`
3.  `static`

1.  **abstract**（此适用于方法） - 抽象方法是一种已定义但未实现的方法。抽象方法在后代类中**必须**被重写。
2.  **final** - 表示该成员不能被修改（对于变量）或不能被重写（对于方法）。
3.  **static** - 表示该成员属于类本身，而不是实例。例如，来自 `String` 类的 `join(CharSequence, CharSequence...)` 方法存在于 `String` 类，因此通过类名开头访问；而不是通过对象的名称访问。另一个 `static` 的例子是 `Math` 中的 `double PI`；在之前的章节练习中已经看到，`Math` 的方法都是作为静态方法调用的。

**注意**：并不是所有的修饰符对于所有潜在的成员类型都有效。但它们都适用于方法。

---

### 60. 类的实例方法和类的静态成员之间有什么区别？

类的实例方法只能相对于类的实例（实例化的对象）被调用；静态成员属于类本身，不需要引用任何对象即可运行。让我们从 `Float` 类中举例，它既有实例方法也有静态方法。

**静态方法示例**：`Float.isInfinite(float)`
```java
boolean result = Float.isInfinite(700.5f);
```
如你所见，该方法是相对于类名 `Float` 调用的。

**实例方法示例**：`Float.shortValue()`
另一方面，同一类的 `shortValue()` 必须为给定的实例调用；也就是说，这个特定方法必须相对于类 `Float` 的实例被调用。例如，要为 `Float` 的实例 `float8` 调用它，我们必须像 `float8.shortValue()` 那样调用。

现在，不仅方法可以是静态的，字段也可以是静态的。例如，在 `Math` 类中，表示数学常数 $\pi$ 的字段被定义为静态字段，通过 `Math.PI` 访问。一些著名的静态成员是 `System` 类中的 `in` 和 `out`；你广泛用于控制台输出的对象是 `System.out`。`System.out` 是 `PrintStream` 类的实例，`System.in` 是 `InputStream` 类的实例。

---

### 61. 在下方的类中，识别哪些是类变量，哪些是实例变量。

```java
public class Store {
    public String storeName;
    public static LocalDateTime openingTime;
    public static LocalDateTime closingTime;
    public static LocalDateTime startTime;
    public LocalDateTime finishTime;
}
```

**类变量（静态变量）**：通过其声明中的关键字 `static` 来标识。这些是字段 `openingTime`、`closingTime` 和 `startTime`。

**实例变量**：通过声明中缺少关键字 `static` 来标识。这些是字段 `storeName` 和 `finishTime`。

---

### 62. （阻止类实例化）

将 `Car` 类的两个构造函数的访问级别修改为 `private`，并尝试运行 `Vehicle` 类的 `main` 方法。展示并解释输出结果。

*运行程序后，将构造函数的访问级别恢复为 public。*

**结果**：代码无法编译。它产生了以下错误："The constructor Car(String, String) is not visible"。

**解释**：`private` 访问级别意味着只有 `Car` 类的直接成员可以访问它的任何成员；这将包括我们刚刚设为私有的构造函数。`Vehicle` 无法访问 `Car` 类新的私有构造函数，因此在 `Car` 类本身之外的任何类中都不实例化 `Car` 类对象，因为 `Car` 现在是唯一可以访问其私有构造函数的类。

**总结**：我们从中学到的一点是，如果你给类的构造函数赋予 `private` 访问级别，你就无法创建该类的对象（除非类内部的方法创建了该类的对象；例如，你可以在 `Car` 类的 `main` 方法中实例化一个 `Car` 对象；尝试这样做）。

**必须说明的是**：如果类中有任何非私有的静态成员，这些静态成员属于类而不是其实例，是可以被访问的。

---

### 63. 尝试编译并运行以下程序。说明并解释结果。

```java
import java.util.*;
public class Experiment {
    public static void main(String[] args) {
        Math abc = new Math();
    }
}
```

**结果**：代码无法编译。呈现的错误信息："The constructor Math() is not visible"。

**解释**：显然，这是因为 `Math` 类的无参构造函数具有 `private` 访问修饰符，阻止了 `Math` 类任何其他对象通过此构造函数实例化任何 `Math` 类对象；它也没有任何公共构造函数；简而言之，除了类内部本身，无法创建 `Math` 类的实例。

但是，我们可以像在之前的章节中那样访问 `Math` 类的静态成员。

**结论/观察**：
1.  如果类有非私有的静态成员，这些静态成员属于类而不是其实例，是可以被访问的。
2.  私有构造函数阻止外部实例化，常用于工具类或单例模式。

---

### 64. 为什么你想让它是静态的？

当你希望该成员（字段或方法）属于类本身，而不属于某个特定实例时，将其设为 `static`。这适用于：
-   工具方法（如 `Math.sqrt()`）
-   常量（如 `Math.PI`）
-   共享状态（如计数器、单例实例引用）
-   无需访问实例字段的逻辑

---

### 65. 创建一个名为 `Volume` 的类，带有以下静态方法：

-   `Sphere` 接收半径。
-   `Cube` 接受长度。
-   `Cone` 接收半径和高度。
-   `Cylinder` 接收半径和高度。

这些每一个都应该返回一个 `double` 类型的值。此外，确保该类不能被实例化。

```java
public class Volume {
    // 唯一的构造函数是私有的，以防止在类之外被实例化。
    private Volume() {
    }

    public static double Sphere(double radius) {
        return ((4.0 / 3.0) * Math.PI * radius * radius * radius);
    }

    public static double Cube(double length) {
        return Math.pow(length, 3);
    }

    public static double Cone(double radius, double height) {
        return ((1.0 / 3.0) * Math.PI * radius * radius * height);
    }

    public static double Cylinder(double radius, double height) {
        return Math.PI * radius * radius * height;
    }
}
```

---

### 66. 测试上述静态类以以下对象：

1.  半径为 40,000 的球
2.  长度为 2.5 的立方体
3.  半径为 50、高度为 50 的圆锥
4.  半径为 50、高度为 25 的圆柱

将代码放入你的 `main` 方法或类本身。打印结果。

我们只显示 `main` 部分：

```java
public class PracticeJava {
    public static void main(String args[]) {
        double sphereVolume = Volume.Sphere(40000);
        double cubeVolume = Volume.Cube(2.5);
        double coneVolume = Volume.Cone(50, 50);
        double cylinderVolume = Volume.Cylinder(50, 25);
        System.out.printf("%f\n%f\n%f\n%f\n", sphereVolume, cubeVolume, coneVolume, cylinderVolume);
    }
}
```

---

### 67. 创建一个 `Circle` 类，定义名为 `Area`、`Diameter` 和 `Circumference` 的方法，为给定的半径计算它们的值（即面积、直径、周长）。每一个都应该返回一个 `double` 类型的值。此外，确保该类在类外不能被实例化。

```java
public class Circle {
    public static double Area(double radius) {
        return (Math.PI * radius * radius);
    }
    public static double Diameter(double radius) {
        return (2 * radius);
    }
    public static double Circumference(double radius) {
        return (2 * Math.PI * radius);
    }
    private Circle() {
        // 这个构造函数确保了该类在类本身之外不能被实例化。
    }
}
```

---

### 68. 使用上面创建的 `Circle` 类，打印半径为 2 的圆的面积、周长和直径，保留两位小数。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        double r = 2;
        // 半径
        System.out.printf("the area, circumference, diameter of a circle radius of %.2f is %.2f, %.2f, %.2f respectively\n", r, Circle.Area(r), Circle.Diameter(r), Circle.Circumference(r));
        r = 12;
        // 第二个半径
        System.out.printf("the area, circumference, diameter of a circle radius of %.2f is %.2f, %.2f, %.2f respectively\n", r, Circle.Area(r), Circle.Diameter(r), Circle.Circumference(r));
    }
}
```

---

### 69. 单例模式

分析并解释以下代码的特征：

```java
public class PrinterSpooler {
    public static PrinterSpooler spool = new PrinterSpooler();
    private PrinterSpooler() {
    }
    public void printFile(String[] filePath) {
        // This stub represents a method that handles print spooling using the
    }
}
```

有趣的是，在这种情况下，给定类（`PrinterSpooler`）的对象直接在类定义内部就被实例化了！这在 Java 中是合法的。

我们还注意到，该类有一个私有构造函数。这意味着没有人可以创建 `PrinterSpooler` 类的另一个对象；它唯一的实例就是我们在类内部直接创建的那个。

现在，为什么你想这样做呢？原因是在某些情况下，我们希望一个类只有一个实例，用来控制代码中某些操作的访问。这种情况的一个例子是资源控制；当我们在代码中使用单个 `PrinterSpooler` 对象来管理程序中所有线程向打印机发送的打印数据时。

这种将对象的实例化限制为给定类中单个实例的程序有一个名称：被称为**“单例模式”**。

**刚刚练习的概念总结**：静态类成员、阻止类实例化、单例模式。

---

### 70. 修改之前创建的 `Circle` 类，使其不再是工具类（即可实例化），并且它的方法不再是静态的。

它还应该包含以下修改：

1.  一个构造函数，将传递的值保存到类型为 `double radius` 的私有字段中。
2.  它应该有一个 `getRadius` 方法，返回字段的值。
3.  它应该有一个 `setRadius` 方法，设置 `radius` 字段的值。
4.  修改类中的现有方法，使其从私有 `radius` 字段获取半径，而不是从方法参数中传递的值。

```java
public class Circle {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    public double getRadius() {
        return radius;
    }

    public void setRadius(double radius) {
        this.radius = radius;
    }

    public double Area() {
        return Math.PI * radius * radius;
    }

    public double Diameter() {
        return 2 * radius;
    }

    public double Circumference() {
        return 2 * Math.PI * radius;
    }
}
```



## Circle 类示例

```java
public class Circle {
    private double radius;

    public double Area() { return (Math.PI * radius * radius); }
    public double Diameter() { return (2 * radius); }
    public double Circumference() { return (2 * Math.PI * radius); }
    public void setRadius(double r) { radius = r; }
    public double getRadius() { return radius; }
    public Circle(double r) { radius = r; } // Constructor
}
```

- **71.** 实例化修改后的 `Circle` 类，其中一个半径为 2 的对象，另一个半径为 4 的对象。打印这些对象的面积、周长和直径，保留两位小数。

## 第 22 章：类 I

```java
public static void main(String[] args) {
    Circle circle1 = new Circle(2);
    Circle circle2 = new Circle(4);
    System.out.printf("The area,diameter,circumference of a circle of radius %f is %f, %f, %f\n", circle1.getRadius(), circle1.Area(), circle1.Diameter(), circle1.Circumference());
    System.out.printf("The area,diameter,circumference of a circle of radius %f is %f, %f, %f\n", circle2.getRadius(), circle2.Area(), circle2.Diameter(), circle2.Circumference());
}
```

# 抽象类

- **72.** 什么是抽象类？

> 提示：查看 58 和 59。

抽象类是：该类被标记为抽象的。

- **73.** 实例化抽象类对象的步骤是什么？

抽象类不能被实例化。只有抽象类的非抽象（具体的）子类可以被实例化。

- **74.** 为什么抽象类很有用？

抽象类是一个要求一组强制实现（即，所有标记为抽象的类中的组件）在它的子类中被实现的类。通过这样做，抽象类强制其具体的子类提供必要的实现。

例如，如果我们有一个 `Shape` 类并想要派生类……

- **75.** 抽象方法的目的是什么？

抽象方法的目的是定义一个必须由子类实现的方法的签名。这确保了所有子类都提供了该方法的实现，从而允许多态行为。

- **76.** 定义一个带有抽象方法 `area()` 和 `perimeter()` 的抽象类 `Shape`。

```java
public abstract class Shape {
    protected double radius;

    public Shape(double radius) {
        this.radius = radius;
    }

    public abstract double area();
    public abstract double perimeter();
}
```

- **77.** 实现 `Shape` 的 `Circle`、`Triangle` 和 `Square` 子类。

```java
public class Circle extends Shape {
    public Circle(double radius) {
        super(radius);
    }

    @Override
    public double area() {
        return Math.PI * radius * radius;
    }

    @Override
    public double perimeter() {
        return 2 * Math.PI * radius;
    }
}

public class Triangle extends Shape {
    public Triangle(double radius) {
        super(radius);
    }

    @Override
    public double area() {
        return (Math.sqrt(3) / 4) * radius * radius;
    }

    @Override
    public double perimeter() {
        return 3 * radius;
    }
}

public class Square extends Shape {
    public Square(double radius) {
        super(radius);
    }

    @Override
    public double area() {
        return radius * radius;
    }

    @Override
    public double perimeter() {
        return 4 * radius;
    }
}
```

## 第 22 章：类

### 多态

| 题号 | 内容 |
| :--- | :--- |
| **78.** | 显而易见，`Car` 类是 `Vehicle` 类的子类。如果我们有一个 `Car` 类的对象 `car01`，解释为什么写以下代码 `Vehicle v01 = car01;` 是有效的。<br><br>这段代码有效是因为它是“多态”特性，这是面向对象编程的核心概念。多态的特性之一是：子类的对象可以赋值给与其任何祖先类类型相同的变量。 |
| **79.** | 给定一个 `Car` 类的对象 `car01`，解释为什么以下代码是有效的：`Object obj01 = car01;`。<br><br>代码有效的原因与前面的解决方案相同，因为 `Object` 类是 `Car` 类的父类（`Object` 类是 Java 中所有类的终极父类）。 |

### 多态以及实例方法的重写与静态方法的方法隐藏

| 题号 | 内容 |
| :--- | :--- |
| **80.** | 确定此程序的输出并解释为什么是这样。<br><br>```java<br>public class A {<br>    public void MyName() { System.out.println("My Name is class A."); }<br>}<br>public class B extends A {<br>    public void MyName() { System.out.println("My Name is class B."); } // overriding<br>    public static void main(String[] args) {<br>        Object object01 = new B(); // 注意：我们使用类型为 A 的变量<br>        // 来访问一个类型为 B 的对象<br>        object01.MyName();<br>    }<br>}<br>```<br><br>**输出：** `My Name is class B.`<br><br>**解释：** 非常重要的一点是，我们创建了一个 `B` 类的对象，但将其赋值给了一个祖先类变量（即 `A` 类，这种赋值是通过多态实现的）。尽管如此，由于 `MyName` 是一个实例方法，调用的是属于变量所访问的对象的实际类的方法版本（在本例中，变量 `object01` 访问的是 `B` 类对象）。<br><br>这与在相同条件下当被调用的方法是静态方法时调用的方法版本形成对比（见下一个练习题）。 |
| **81.** | 确定此程序的输出并解释为什么是这样。（代码与上一个练习题的区别在于，本次练习中 `MyName` 方法是静态的）。<br><br>```java<br>public class A {<br>    public static void MyName() { System.out.println("My Name is class A."); }<br>}<br>public class B extends A {<br>    public static void MyName() { System.out.println("My Name is class B."); } // hiding<br>    public static void main(String[] args) {<br>        Object object01 = new B(); // 注意：我们使用类型为 A 的变量<br>        // 来访问一个类型为 B 的对象<br>        object01.MyName();<br>    }<br>}<br>```<br><br>**输出：** `My Name is class A.`<br><br>**解释：** 在 Java 中，当调用静态方法时，被调用的方法版本属于调用该方法的变量的声明类型。这与当所涉及的方法是实例方法时调用的方法版本形成对比（见上一个练习题）。读者应该重复此练习，将 `object01` 实例化为 `B` 类，以确认这一解释。<br><br>你只能“隐藏（hide）”静态方法，而不能“重写（override）”它们。 |

# 练习你的 Java 1 级

这组练习展示了多态的优势；即能够使用对应于共同祖先类类型的分组，并且在使用父类类型的变量引用对象时，能够访问属于所引用对象实际类的方法。

- **82.** 实例化以下每个对象并将它们放入 `Shape` 类型的数组中：一个半径为 2.73 的 `Circle` 对象、一个长度为 15 的 `Square` 对象、一个大小为 3.0 的 `Pentagon` 对象和一个大小为 3.7 的 `Hexagon` 对象。

> 这里只显示 `main` 方法：

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        Circle obj1 = new Circle(2.73);
        Square obj2 = new Square(15);
        Pentagon obj3 = new Pentagon(5); // 注意：原文参数为 5，题目描述为 3.0
        Hexagon obj4 = new Hexagon(3.7);
        // 接下来定义 Shape 类型的数组并将子类对象放入其中。
        Shape[] shape = new Shape[4];
        shape[0] = obj1;
        shape[1] = obj2;
        shape[2] = obj3;
        shape[3] = obj4;
    }
}
```

> 注意：`Shape` 是一个抽象类，但我们仍然能够创建它的引用。

- **83.** 对上一个练习应用循环，通过多态打印每个对象的面积和周长。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        Circle obj1 = new Circle(2.73);
        Square obj2 = new Square(15);
        Pentagon obj3 = new Pentagon(5);
        Hexagon obj4 = new Hexagon(3.7);
        // 接下来定义 Shape 类型的数组并将子类对象放入其中。
        Shape[] shape = new Shape[4];
        shape[0] = obj1;
        shape[1] = obj2;
        shape[2] = obj3;
        shape[3] = obj4;
        for (int j = 0; j < shape.length; j++) {
            System.out.println("Area: " + shape[j].area());
            System.out.println("Perimeter: " + shape[j].perimeter());
        }
    }
}
```

- **84.** 遍历上一个练习中的数组并使用 `getClass()` 打印出数组元素是种种对象。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        Circle obj1 = new Circle(2.73);
        Square obj2 = new Square(15);
        Pentagon obj3 = new Pentagon(5);
        Hexagon obj4 = new Hexagon(3.7);
        Shape[] shape = new Shape[4];
        shape[0] = obj1;
        shape[1] = obj2;
        shape[2] = obj3;
        shape[3] = obj4;
        for (int i = 0; i < shape.length; i++) {
            System.out.printf("%d: %s\n", i, shape[i].getClass());
        }
    }
}
```

## 第 22 章：类 I

- **85.** 遍历上一个练习中的数组并使用 `getClass()` 打印出数组元素是种种对象。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        Circle obj1 = new Circle(2.73);
        Square obj2 = new Square(15);
        Pentagon obj3 = new Pentagon(5);
        Hexagon obj4 = new Hexagon(3.7);
        Shape[] shape = new Shape[4];
        shape[0] = obj1;
        shape[1] = obj2;
        shape[2] = obj3;
        shape[3] = obj4;
        for (int j = 0; j < shape.length; j++) {
            System.out.printf("%d: %s\n", j, shape[j].getClass());
        }
    }
}
```

> 注意：将此解决方案与上一个练习的解决方案进行对比。此解决方案以更简洁的方式实现了相同的问题。

已练习的概念：多态、重写、方法隐藏。

## final 类和方法

- **86.** 如果我在之前定义的 `Hexagon` 类（见第 77 题）的定义第一行添加 `final` 关键字如下，这对该类产生什么影响？

```java
public class Hexagon extends Shape
```
变为
```java
public final class Hexagon extends Shape
```

影响是无法从 `Hexagon` 类派生子类。将 `final` 理解为“这是该层次结构中的最后一个类”。

为了练习，你可以尝试从这个 final 类派生类以观察编译器的反应。

- **87.** 尝试编译以下代码的结果是什么，为什么？

```java
public class A {
    public final void hello() {
        System.out.println("Hello I'm from class A!");
    }
}
public class B extends A {
    public void hello() {
        System.out.println("Hello I'm from class B!");
    }
}
```

无法编译，因为无法重写祖先类中声明为 `final` 的方法。

# 初始化

- **88.** 预测以下代码的输出并解释为什么是这样。

```java
public class Experiment {
    static int x;
    final int y;
    final static LocalDateTime startTime;
    static {
        x = 2;
        // y = 500; // 编译错误：无法在静态上下文中给实例变量 y 赋值
        startTime = LocalDateTime.now();
    }
}
```

```java
public static void main(String args[]) {
    System.out.println("y=" + y); // 编译错误：无法从静态上下文中引用非静态变量 y
    System.out.println("x=" + x);
}
```

> **注意：** 原文提供的代码片段存在编译错误（静态初始化块中无法初始化实例变量 `y`，静态 `main` 方法中无法直接访问实例变量 `y`）。原文给出的输出 `y=500, x=512` 与代码逻辑不符（且 `x` 初始化为 2，输出应为 2）。此处保留原代码结构并标注错误。

- **89.** **类初始化器的作用是什么？**

类初始化器（静态初始化块）用于在类加载时初始化类变量（静态字段）。它提供了编写必要代码块的能力，以实现编译时未知的静态类变量的运行时初始化顺序，并在类启动时执行任何所需的操作。你可以将静态初始化器理解为类变量的“构造函数”。

- **90.** **预测以下代码的输出并解释其原因。**

（原文此处缺少代码，待补充）



```java
class Experiment {
    static int x;
    final int y;
    final static LocalDateTime startTime;

    static {
        x = 12;
    }
    static {
        y = 500;
        startTime = LocalDateTime.now();
    }
    static int z = y;
    public static void main(String args[]) {
        System.out.println("y=" + y);
        System.out.println("x=" + x);
    }
}
```

**输出：** 输出与练习 88 相同。在同一个类定义中存在多个静态初始化器块是有效的。静态初始化器按照它们出现的顺序执行。

- 91. **实例初始化器**

- 预测以下代码的输出并解释其原因。

```java
class Experiment {
    final LocalDateTime startTime;
    {
        startTime = LocalDateTime.now();
        // 实例初始化器块
    }
    public static void main(String args[]) {
        Experiment exp01 = new Experiment();
        System.out.println("startTime=" + exp01.startTime);
    }
}
```

在这里我们看到了“实例初始化器”块的示例。它看起来像类初始化器，只是缺少了 `static` 关键字。Java 实际上会将实例初始化器块复制到它们出现的每个构造函数的开头（即在构造函数体之前结束）。

**注意：** `super` 关键字可以在实例初始化器中使用。

- 92. 为什么存在实例初始化器？

实例初始化器存在的一个原因是 `final` 变量无法在构造函数中初始化，但可以在实例初始化块中初始化。实例初始化器存在的另一个原因是匿名类。匿名类无法定义自己的构造函数（它们受限于继承），因此初始化块可以为它们提供功能。我们在第 24 章查看匿名类。

刚刚练习的概念：类和方法、类（静态）初始化器、实例初始化器。

# 包访问

- 93. 我们在不同的包中定义了两个类：

```java
package package_A;
class X {
}
```

和

```java
package package_B;
import package_A.*;
public class Y extends X {
    public static void main(String[] args) {
    }
}
```

解释为什么继承 X 的类 Y 的编译尝试失败。

**提示：** 类 X 需要什么访问级别？

位于 `package_A` 的类 X 具有包私有的（package-private）可见性。位于不同包的类 Y 尝试访问它“看不到”的内容。这就是编译失败的原因。

- 94. 我们有以下类：

```java
package package_A;
public class X {
    int var01;
}
```

和

```java
package package_B;
import package_A.*;
public class Y extends X {
    public static void main(String[] args) {
        Y obj01 = new Y();
        obj01.var01 = 5;
    }
}
```

解释为什么继承 X 的类 Y 的编译尝试失败。编译失败的精确原因是 `obj01` 尝试访问另一个包中的包私有变量 `var01`。

- 95. 我们修改了类 Y，删除了对包私有变量 `var01` 的访问。它能编译吗？

```java
package package_B;
import package_A.*;
class Y extends X {
    public static void main(String[] args) {
        Y obj01 = new Y();
    }
}
```

# 练习你的 Java 级1

编译成功是因为 obj1 没有尝试访问字段 `var1`（正如之前的练习中尝试过的那样）。观察发现，尽管对于类 Y 来说其父类的成员 var1 是私有的，由于你没有尝试访问它，它是可以编译的。

刚刚练习的概念：跨包和类成员。

- 96. 访问器和修改器（getter 方法）：关于数据的进一步说明

访问器和修改器的概念是一个简单的命名概念。

访问器和修改器（getter 和 setter 方法）的概念是实现数据封装的约定。你实际上已经在练习 29、30、52 和 53 中实现了此类示例；现在请快速查看这些解决方案。

访问器是一个“私有”的（很可能是公有的）方法，用于访问对象中的字段；此方法具有以下要求：

1. 它的命名规范是 `getVariableName`（首字母大写）。

2. 它返回其引用的字段值。

如练习 52 所示，你实际上实现了访问器。

修改器方法是一个“私有”的（很可能是公有的）方法，用于设置对象中的字段；此方法具有以下要求：

1. 它的命名规范是 `setVariableName`（首字母大写）。

2. 它传递了我们想要设置的值。

3. 它直接设置字段的值。

如练习 53 所示，你实际上实现了修改器。

现在，为什么存在访问器和修改器？由于数据封装。

如果我们想从另一个对象访问对象中的特定字段，将字段设为公共不是最优的，因为它违反了面向对象编程的基本原则——封装。如果发生此类损坏，必须搜索源代码以查看问题字段的哪个部分。访问器和修改器作为字段的单一入口点（用于读写）。任何读取或写入数据的尝试都会被单个断点捕获，从而更容易识别来源。

刚刚练习的概念：访问器和修改器方法。

# 第 23 章。对象引用与原始类型：深入理解

这个重要的章节讨论了正确理解 Java 中对象引用和原始类型如何在方法之间传递的必要性。虽然主题在之前的章节中已经在某种程度上介绍过，但仍需针对该主题进行针对性练习。本章提供了用于练好这些概念技能的练习。在阅读本章的练习和解决方案时，你可能会观察到某种程度的重述。鉴于本章主题的重要性，这被认为是必要的。

| 什么是类型 | 类型是适用于任何数据的特定“模板”。在 Java 中，类型分为大类：原始类型（primitives）和引用类型。任何不是原始类型（我们之前已经处理了所有的）都是引用类型。类型的示例包括 `double`，它是适用于浮点数的原始类型；`Double` 是对象的引用类型。在 Java 中，程序员可以创建引用类型，但不是原始类型。这些“模板”对于编译器确定许多事情是必要的，例如使用多少内存来存储数据、在哪里存储数据以及哪些数据操作是有效的。 |
| 定义 Java 中所谓的原始类型 | 原始类型是指其值直接包含数据的类型。 |
| 可用的原始类型 | 可用的原始类型包括 `byte`、`short`、`int`、`long`、`float`、`double` 以及 `boolean` 和 `char` 类型。 |
| 什么是原始变量？ | 原始变量简单来说内存中一个数据项的命名空间。变量对应于我们赋予数据项的名称。所以当我们说 `x5` 时，我们是在给一个值以及它在内存中的位置命名（以便我们找到它）。分配给它的内存空间对应于它声明的该原始类型的适用空间。 |
| 解释什么是引用类型变量 | “引用类型”变量是一个“包含”指向对象的引用的。我们在书中已经很大程度上使用了这些，但在这里我们更正式地解释它们的细节。重述上面的内容，我们会说引用类型的变量并不是所引用数据/对象的实际容器，而是它所代表的数据存储位置的引用。简单来说，我们可以说“引用类型的变量包含它所引用的对象的地址”。如果我是一个原始类型变量，我的口袋里会有 10 美元。如果是一个引用类型，我的口袋里就不会有这 10 美元，而是有一张纸，上面写着这 10 美元所在的地址；从物理意义上来说，你必须根据口袋里纸条上的地址去取钱。 |

注意，当你使用变量（无论是基本类型还是引用类型）时，Java 运行时会为我获取这 10 美元，因此在引用类型的情况下，我不需要做额外的工作；Java 会替我完成工作。在 Java 中，获取引用类型的实际值涉及两个步骤：首先获取引用类型变量的值（即地址），然后根据该地址获取实际对象；而对于基本类型，只有一步。

在处理相等性问题时，我们所处理的类型（引用类型或基本类型）至关重要。例如，对于任何基本类型的变量 `a=2` 和 `b=4`，对于 `a==b`（a 的值是否等于 b 的值）这个问题，`==` 运算符会对值 2 和 4 进行直接比较，并给出适当的结果（此处为 false）。

在引用类型的情况下，如果我们有引用类型变量 `x` 和 `y`，并且如下所示：`x=object` 和 `y=object`，那么 `x==y` 的结果将是 `false`！这种情况发生的原因是，引用类型变量是一张写有地址的纸，它们显然不是同一张纸（尽管它们上写的是同一地址）。虽然有时你想“检查你谈论的是否同一张纸”，但更多情况下，你想比较纸上写的内容，即比较 `x` 和 `y` 所引用的内容。要做到这一点，你必须使用引用类型特定的比较器来比较由引用类型所引用的值。

- 6. 列出不同类型的引用类型。

Java 中的每种**非**基本类型都是引用类型。这包括类、接口和所有数组（即使数组是基本类型数组）。

- 7. 描述从方法传递到其他方法（包括方法尝试更改传递给它的变量值时产生的影响）给以下每个类型区别：

    - 基本类型

    - 引用类型

当你从一个方法“传递”一个基本类型变量时，你仅仅是将基本类型变量中数据的一个拷贝传递给其他方法。拷贝与原始数据没有任何关系！

然而，当你向方法传递一个引用类型变量时，你实际上传递的是地址的拷贝（与基本类型不同，基本类型传递的是数据的拷贝；这里你传递的是数据所在地址的拷贝）。这是我的理解；然而，地址是写在纸上的，而我把这个地址写在另一张纸上给你。

方法尝试更改传递给它的值的结果：

1. 对于基本类型，如果方法更改了传递的参数的值，它对调用者中变量的值没有影响，因为你从未向方法传递过引用，方法对包含该值的原始变量一无所知。

2. 对于引用类型，如果方法更改了传递给它的参数所引用对象的内容（即查看地址并去修改地址处存储的内容），它实际上对调用者中变量所引用的对象产生了影响。使用地址类比，方法已被告知数据所在的位置（因为传递了地址），因此方法可以修改该地址的内容。

**注意：** 这种情况的例外是传递包装类对象和 `String` 类。我们将在本章中看到。

- 8. “字符串是不可变的”这一说法是什么意思？

请再次查看第 5 章第 9 题练习的答案。

- 9. 在下面的程序中，我们将一个 `String` 变量从 `main` 方法传递到一个命名方法 `Modify`，该方法旨在修改 `String` 的内容。预测并解释尝试修改 `String` 的结果。

# 第 23 章：对象引用与基本类型处理

```java
public class PracticeYourJava {
    public static void Modify(String s) {
        s = "Modified!!"; // 尝试修改 String
        System.out.println(s);
    }

    public static void main(String[] args) {
        String str0 = "Hello, ";
        Modify(str0); // 调用方法 Modify
        System.out.println(str0);
    }
}
```

**输出：**

```text
Modified!! -- 这是来自方法 Modify 的输出
Hello, -- 来自此方法，在 Modify 方法尝试修改后的输出
```

**解释：** 正如我们之前注意到的，`String` 对象是不可修改的。`String` 类型是一种引用类型，当我们把 `String` 传递给方法 `Modify` 时，Java 在 `Modify` 方法中复制/传递了 `str0` 的地址。然而，记住当我们尝试修改字符串时会发生什么；正如前面的示例，因为 `String` 是不可变的，当方法 `Modify` “修改” `String` 的内容时，后台创建了一个新的 `String` 对象并将其赋值给 `Modify` 方法中的变量 `s`；`str0` 仍然指向原始字符串的地址。

- 10. 非常重要：在下面的程序中，我们尝试在调用的方法 `Modify` 中修改不同的变量，这将会失败。结果意味着尝试修改 `int`、`String[]`、`String` 和 `StringBuilder` 的内容无效。

```java
public class PracticeYourJava {
    public static void Modify(int z1, int[] a, String str0, StringBuilder sa01, StringBuilder sb01) {
        z1++;
        str0 = str0 + "Modified!!"; // 尝试修改 String
        sa01[0] += "Modified!!"; // 尝试修改数组列表
        sb01.append("Modified!!"); // 尝试修改 StringBuilder
        if (a.length < 1) // 尝试修改数组中的 int
            for (int count = 0; count < a.length; count++)
                a[count]++; // 尝试增加数组中的每个元素
    }

    public static void main(String[] args) {
        int z1 = 50;
        int[] a = new int[] {1, 2, 3, 4, 5};
        String str0 = "Hello. ";
        StringBuilder sa01 = new StringBuilder("I am String array 0: ");
        StringBuilder sb01 = new StringBuilder("Hello. ");
        Modify(z1, a, str0, sa01); // 调用方法 Modify
        System.out.println("z1: " + z1);
        System.out.println("a[0]: " + a[0]);
        System.out.println("str0: " + str0);
        System.out.println("sa01[0]: " + sa01[0]);
        System.out.println("sb01: " + sb01);
    }
}
```

# 第 23 章：对象引用与基本类型处理

在后台进行了更新，指向了一个新的 `Integer` 对象，该对象的值是根据 `ref01` 原本引用的 `Integer` 对象的值所执行的操作的结果。简而言之，`ref01` 不再指向它最初指向的对象。

这种行为与 `String` 类的行为是相同的。

- 16. 记住前一个练习的解释，预测以下代码的输出并解释原因。

```java
class PracticeYourJava {
    public static void modify(Integer refin) {
        refin++; // 尝试修改 Integer
        System.out.println("refin = " + refin);
    }
    public static void main(String[] args) {
        Integer ref01 = 20;
        modify(ref01);
        System.out.println("value = " + ref01);
    }
}
```

**输出：**

```text
refin = 21
value = 20
```

`ref01` 所引用的 `Integer` 值没有被修改！

**解释：** 我们确实将对象引用 `ref01` 的内容传递给了方法 `modify`。因此，方法 `modify` 中的参数 `refin` 和变量 `ref01` 具有相同的内容；即值为 20 的对象的地址。

请记住，基本类型包装类的对象是不可变的，因此，当 `modify` 方法尝试通过引用修改对象时，`refin` 中的地址现在更新为指向一个具有修改后值的 `Integer` 对象（在本例中为 21），但 `ref01` 没有被更新。

`ref01` 没有被更新的原因可以用以下类比来解释：想象 `ref01` 是一张包含值为 20 的 `Integer` 对象地址的纸。该地址被复制到了 `modify` 的变量 `refin` 中。我们现在有两张写有相同内容的纸（`refin` 和 `ref01`）。现在记住，基本类型包装类的对象是不可变的，对它们的任何更改都会导致一个新对象的创建，并对该对象的引用更新为指向该新对象。在对 `refin` 和 `ref01` 指向的 `Integer` 对象进行更新后，创建了一个新对象，并将引用更新为新对象的地址。简而言之，`refin` 这张纸上的地址被擦掉了，并在上面写了一个新地址。现在，`ref01` 这张纸的内容不会被更新，除非有人传递了一个对象的地址并将其写在一张名为 `refin` 的纸上。再次，请注意以下几点：

> 基本类型包装类对象是不可变的。`String` 类是不可变的。

- 17. 预测以下代码的输出并解释原因。



```java
class PracticeYourJava {
    public static void main(String[] args) {
        Integer ref01 = 20;
        Integer ref02 = 21;
        System.out.println("ref01 = " + ref01);
        System.out.println("ref02 = " + ref02);
    }
}
```

输出：

```
ref01 = 20
ref02 = 21
```

# Java 练习 Level 1

解释：将 `ref01` 和 `ref02` 想象成两张纸。变量 `ref01` 设置为指向值为 20 的 `Integer` 对象的引用；在我们的类比中，值为 20 的 `Integer` 的地址现在写在名为 `ref01` 的纸上。写在 `ref01` 上的地址被复制到 `ref02`，即现在两张纸（`ref01` 和 `ref02`）上写着相同的地址。然后我们决定修改 `ref02` 引用的对象；然而被引用的对象是不可变的（意味着对象本身不能被更改），修改导致了新对象的创建，并且 `ref02` 更新为包含指向新对象地址的引用。这就是 `ref01` 和 `ref02` 报告的值不同的原因。

记住：基本类型包装类是不可变的。`String` 类是不可变的。任何修改基本类型包装类对象或 `String` 对象的尝试都会导致新对象的创建，并且尝试修改的对象（`ref02`）将更新为包含指向新位置的引用。

## 18. 预测此代码的输出并解释原因。

```java
public class PracticeYourJava {
    public static void Modify(StringBuilder sb1) {
        sb1.append("How are you?"); // 尝试修改 StringBuilder
    }

    public static void main(String[] args) {
        StringBuilder sb1 = new StringBuilder("Hello. ");
        Modify(sb1); // 调用 Modify 方法
        System.out.println(sb1);
    }
}
```

输出：`Hello. How are you?`

解释：`StringBuilder` 类的对象是可变的，因此任何修改此类对象的尝试都会成功。

## 19. 预测此 PracticeYourJava 的输出并解释原因。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        StringBuilder sb1 = new StringBuilder("Hello. ");
        StringBuilder sb2 = sb1;
        sb2.append("How are you?");
        System.out.println(sb1);
        System.out.println(sb2);
    }
}
```

输出：

```
Hello. How are you?
Hello. How are you?
```

解释：想象 `sb1` 和 `sb2` 是两张不同的纸。名为 `sb1` 的纸是 `StringBuilder` 对象的地址。然后我们将 `sb1` 的地址复制到 `sb2`。

## 20. 此代码的预期输出是什么？

```java
public class Person {
    public String firstName;
    public String lastName;
}

public class PracticeJava {
    public static void Modify(Person y) {
        y.firstName = "Me";
        y.lastName = "Myself";
    }

    public static void main(String[] args) {
        Person p = new Person();
        Modify(p);
        System.out.printf("The person is: %s %s\n", p.firstName, p.lastName);
    }
}
```

输出：

```
The person is: Me Myself
```

# 第 24 章 类 II：嵌套类、局部类、匿名类

“类 I”章节是 Java 中类概念的基础。本章在它的基础上进行了扩展，介绍了关于非顶层类这一有趣话题的练习题，即不同类型的嵌套类。

## 什么是嵌套类？

嵌套类是在另一个类内部声明的类。

嵌套类有四种显式类型，它们分别是成员类（分为两种类型，即 (1) 静态类和非静态嵌套类，也称为 (2) 内部类）、(3) 局部类和 (4) 匿名类。成员类直接声明在外部类内部，而局部类和匿名类则直接声明在方法内部。

## 成员类

### 2. 识别下方代码中的静态类 Shape 和内部类。

```java
public class Shape {
    public double area(double length) {
        return (length * length);
    }
}

static class Rectangle {
    public double area(double length, double breadth) {
        return (length * breadth);
    }
}
```

静态类是 `Rectangle` 类。通过以下两个事实可以识别：(1) 它定义在另一个类内部（在本例中为 `Shape` 类），且 (2) 它在类定义前面带有 `static` 关键字。

内部类是 `Square` 类。通过以下两个事实可以识别：(1) 它定义在另一个类内部，且 (2) 它的定义中没有 `static` 关键字。

### 3. 描述什么是内部类、什么情况下使用内部类合适，以及如何实例化这些对象。

内部类是定义在另一个类体内的非静态类，不同之处在于它是另一个类。内部类只能作为其所属类的对象来被实例化。内部对象可以访问其所属类对象的成员。

现在，你会在哪里使用内部类呢？当一个类所包含的信息可能仅作为其所属类的一个组件时才有意义时，内部类是一个合适的选择。

以下示例展示了这一点：

1. 内部类的声明
2. 内部类对象的实例化

```java
public class Shape {
    public class Circle {
    }

    public static void main(String args[]) {
        Shape shape01 = new Shape();
        Shape.Circle circle01 = shape01.new Circle();
    }
}
```

## 测试你的 Java 水平

内部类 `Circle` 显示在外部类 `Shape` 内部。应注意代码第 6 行的声明，它展示了如何实例化内部类对象。该行的元素描述如下：

1. 行的第一个项是完全限定的类名，在本例中为 `Shape.Circle`。
2. 第二项是我们想要创建的内部类对象的名称。
3. 第三个项是等号，我们在此将其用于任何对象实例化。
4. 第四项 `shape1.new` 显示我们正在创建一个外部类的子对象。回想之前提到过，内部类对象是其闭包类的子对象。这就是为什么外部类名会出现在这里，以便编译器知道将这个新对象绑定到哪个外部类；该关键字以 `.new` 的形式附加其后。
5. 行的第五（五）项是正在被实例化的类名。

我们展示了如何访问内部对象作为子对象的那个外部类中的变量。

```java
public class Shape {
    private int shapeInt;

    public class Circle {
        public void printOuterInfo() {
            System.out.println(Shape.shapeInt);
        }
    }

    public static void main(String[] args) {
        Shape shape1 = new Shape();
        shape1.shapeInt = 50;
        shape1.circle1 = shape1.new Circle();
    }
}
```

我们在第五行看到内部类对象如何访问其所属对象的数据。我们使用的语法是 `外部类.类名`。当所属对象的成员的访问级别为 `private` 时，这是可能的。

我们想要创建一个 `Alphabet` 类，其中包含一个名为 `letter` 的内部类。`Letter` 类的每个对象代表字母表中的一个字母。每个 `Letter` 类的对象都有两个字段 `letterName` 和 `pronunciation`，它们的类型为 `String`。

`Alphabet` 具有以下特征：一个私有的数字 `numberLetters`，`Alphabet` 的实例在实例化时会被初始化；一个私有的字符串 `alphabetName`，包含包含所讨论的 `Alphabet` 的名称；该类还会为该变量初始化一个值。

类的另一个成员是 `Letter` 类型的数组；它在创建对象时被实例化，大小等于 `numberLetters`。我们写一个方法来打印存储在其中的 `Letter` 类对象。

在类中，包含一个方法，使 `Letter` 类对象可以将自己放入其外部类（`Alphabet`）拥有的 `Letter` 数组中。

使用类 `AlphabetTest` 测试你的代码。执行以下操作：

1. 创建一个 `Alphabet` 类对象，参数为 "Roman" 和 26，代表罗马字母。
2. 创建代表字符 "A" 和 "B" 的 `Letter` 类对象。
3. 将字母插入到其外部对象 `Alphabet` 对象中。
4. 打印之前创建的 `Alphabet` 对象中 `Letter` 数组的内容。

注意：代码行仅供参考：

```java
public class Alphabet {
    private String alphabetName;
    private int numberLetters;
    private Letter letters[];
    private int lettersIndex = 0;

    protected Alphabet(String alphabetname, int numberLetters) {
        this.alphabetName = alphabetName;
        this.numberOfLetters = numberLetters;
        letters = new Letter[numberOfLetters];
    }

    public void printAlphabet() {
        if (numberOfLetters == 0) return;
        System.out.println("Expected # of characters in alphabet = " + numberOfLetters);
        System.out.println("Currently # of characters = " + lettersIndex + "\n");
        for (int j = 0; j < lettersIndex; j++) {
            System.out.printf("%s:%s\n", letters[j].letterName, letters[j].pronunciation);
        }
    } // outer class

    public class Letter {
        String letterName;
        String pronunciationDescription;

        Letter(String name, String description) {
            letterName = name;
            pronunciationDescription = description;
        }

        void addToOuterObject() {
            letters[lettersIndex] = this;
            lettersIndex++;
        }
    } // inner class
}

public class testAlphabet {
    public static void main(String[] args) {
        Alphabet roman = new Alphabet("Roman", 26);
        Alphabet.Letter letter_A = roman.new Letter("A", "Ayyyy");
        Alphabet.Letter letter_B = roman.new Letter("B", "Beeee");
        letter_A.addToOuterObject();
        letter_B.addToOuterObject();
        roman.printAlphabet();
    }
}
```

# 第 24 章：类

在我们的数据库中，我们存储了关于员工的以下信息：

* 名
* 姓

我们还存储了员工的薪资历史，其格式如下：`(int monthsSalary, BigDecimal amount)`

创建一个 `Employee` 类，它分别具有字符串字段 `FirstName` 和 `LastName` 表示员工的名字和姓。同时在 `Employee` 类中创建一个内部类 `SalaryHistory`，用于存储上述数据元组。在 `Employee` 类中创建一个方法来计算员工随时间变化的平均薪资。

针对给定的员工测试你的代码：

```java
import java.math.BigDecimal;
import java.math.RoundingMode;

public class Employee {
    private String firstName;
    private String lastName;
    private SalaryHistory[] history = new SalaryHistory[100];
    // 我们使用 100 设置为一个合理的数字
    private int insertionCounter = 0; // 数组计数器

    public Employee(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    public void addSalary(int numberOfMonths, String amount) {
        SalaryHistory sh = new SalaryHistory();
        sh.numberOfMonths = numberOfMonths;
        sh.amount = new BigDecimal(amount);
        history[insertionCounter] = sh;
        insertionCounter++;
    }

    public BigDecimal averageSalary() {
        if (insertionCounter == 0) return (new BigDecimal("0"));
        int totalMonths = 0;
        BigDecimal decimalTotal = new BigDecimal("0");
        for (int count = 0; count < insertionCounter; count++) {
            BigDecimal aggregateForPeriod = history[count].amount.multiply(new BigDecimal(history[count].numberOfMonths));
            decimalTotal = decimalTotal.add(aggregateForPeriod);
            totalMonths += history[count].numberOfMonths;
        }
        BigDecimal averageSalary = decimalTotal.divide(new BigDecimal(totalMonths), RoundingMode.HALF_UP);
        return (averageSalary);
    }

    class SalaryHistory {
        int numberOfMonths;
        BigDecimal amount;
    }

    public static void main(String[] args) {
        Employee emp01 = new Employee("Tabitha", "Gump");
        emp01.addSalary(3, "3000");
        emp01.addSalary(9, "3500");
        emp01.addSalary(12, "4000");
        emp01.addSalary(5, "4500");
        System.out.println("The average monthly salary of " + emp01.firstName + " " + emp01.lastName + " is " + emp01.averageSalary());
    }
}
```

## 成员类 — 静态嵌套



# 第 24 章：类 II

## 6. 静态类

描述什么是静态类、在何时使用静态嵌套类合适，以及如何实例化此类对象。

静态类是：

1. 定义在类内部的类
2. 它具有 `static` 类修饰符

> **重要：** 静态嵌套类的静态定义与之前讨论类和成员时所使用的 `static` 定义不同，因为静态类是可以被实例化的。静态嵌套类的定义意味着，嵌套框中的类在实例化内部类对象之前，**不需要**先实例化外部类的对象。当我们想要将类分组在一个伞形类下时，静态嵌套类是有意义的。如果需要，静态嵌套类可以使用其外部类的数据，否则没有强制要求静态内部类与其外部类之间存在任何特定关系；外部类仅仅是一个命名空间容器。

### 静态类示例

```java
public class Shape {
    static class Square { // 在此处定义了静态嵌套类
        protected double area(double length) {
            return (length * length);
        }
    }
    public static void main(String[] args) {
        Shape.Square square01 = new Shape.Square(); // 对象实例化
        // 正如所示，必须使用完全限定的类名
        //（在此情况下为 Shape.Square）
        // 静态嵌套类的用法很正常，见下文
        double area = square01.area(40F);
        System.out.println("Area of the square = " + area);
    }
}
```

从代码中可以看到：

1. 在创建静态类对象之前，不需要创建外部类的对象（与内部类对象的创建对比）。
2. 在创建静态嵌套类对象时，使用了静态类的完全限定名。

在上一版本代码的基础上，增加 `Circle`、`Pentagon` 和 `Hexagon` 静态类的定义。创建对象以分别展示半径为 25 的圆形、边长为 15 的五边形和六边形的面积。

```java
public class Shape {
    static class Square { // 在此处定义了静态嵌套类
        protected double area(double length) {
            return (length * length);
        }
    }
    static class Circle {
        protected double area(double radius) {
            return (Math.PI * radius * radius);
        }
    }
    static class Pentagon {
        protected double area(double length) {
            return (1.720477401 * Math.pow(length, 2));
        }
    }
    static class Hexagon {
        protected double area(double length) {
            return (2.598076211 * Math.pow(length, 2));
        }
    }
    public static void main(String[] args) {
        Shape.Circle circle01 = new Shape.Circle();
        Shape.Square square01 = new Shape.Square();
        Shape.Pentagon pentagon01 = new Shape.Pentagon();
        Shape.Hexagon hexagon01 = new Shape.Hexagon();
        System.out.println("Area of the circle = " + circle01.area(25F));
        System.out.println("Area of the square = " + square01.area(40F));
        System.out.println("Area of the pentagon = " + pentagon01.area(15F));
        System.out.println("Area of the hexagon = " + hexagon01.area(15F));
    }
}
```

## Java 练习 Level 1

### 8. 防止静态类实例化

如果我不希望我的静态类实例化，只想使用它的方法，该怎么办？

解决方案是给该类一个 `private` 构造函数。

### 9. 修改练习 6，将 Circle 设置为静态类，输出结果保留两位小数

```java
public class Shape {
    static class Circle {
        public static double area(double radius) { return (Math.PI * radius * radius); }
        public static double diameter(double radius) { return (2 * radius); }
        public static double circumference(double radius) { return (2 * Math.PI * radius); }
        private Circle() { }
    }

    public static void main(String[] args) { // 使用
        System.out.printf("Area: %.2f\n", Circle.area(15));
        System.out.printf("Diameter: %.2f\n", Circle.diameter(15));
        System.out.printf("Circumference: %.2f\n", Circle.circumference(15));
    }
}
```

## 匿名类

### 10. 匿名类概念

描述什么是匿名类、何时可以使用以及如何实例化对象。

匿名类是一个：
1. 没有名称
2. 在对象实例化点定义的类

当现有类的某个实例需要某种程度上修改类的行为时，通常会创建匿名类；正因如此，在代码中创建对象的地方就可以修改类定义。匿名类由编译器定义为一个表达式，并以分号结束。以下示例显示了匿名类的实现（在本例中，匿名类是 `Hello` 类的子类）：

```java
class Hello {
    public void sayHello() {
        System.out.println("Hello are you?");
    }
}

public static void main(String[] args) { // 构造参数后面的左侧表示
    Hello obj1 = new Hello() {
         // 匿名类的开始
        public void sayHello() { // 重写继承的方法
            System.out.println("HI !!!");
        }
    }; // 类结束。右大括号 = 在这里使用匿名类的对象。运行
    obj1.sayHello(); // 代码查看它输出了 "HI !!!"。
}
```

正如之前提到的，匿名类是在预期匿名类对象实例化时定义的。为什么被称为匿名类？之所以这样命名，是因为通常类会被赋予一个显式名称，而匿名类没有显式名称。虽然我们确实使用了从继承而来的类名 `Hello` 为了实例化，这并不是属于对象的真实类。

匿名类的存在通过包含构造函数参数的括号之前的左大括号 `{` 来标识。匿名类以右括号 `}` 结束；分号 `;` 是用于结束代码行的字符；这正是为什么匿名类被视为一个表达式的原因。我们在派自 `Hello` 类的匿名类定义中看到了这一点。

当你的代码中某些类实际上只需要使用一次时，匿名类非常有用。这种“一次性”场景在 Java GUI 编程中非常常见。例如，你 GUI 中的每个按钮可能都有独特的任务；你不必为每个按钮将执行的操作创建一个显式命名的类，而是创建与每个按钮实例相关的匿名类来处理此类功能。

匿名类还可以实现接口！这将在第 26 章“继承的接口”中介绍。

### 11. 匿名类构造函数问题

既然匿名类没有类名，你如何在匿名类中定义新的构造函数？

你不能为匿名类定义构造函数！它只能使用继承的构造函数。如果它想定义自己的类似于构造函数的功能，可以使用实例初始化块。

```java
class Hello {
    String name;
    Hello(String name) {
        this.name = name;
    }
    public void sayHello() {
        System.out.println("Hello " + name + " how are you?");
    }
}
```

我们修改上一个问题中匿名类的 `main` 方法，使用字段 `name`，在 `sayHello` 方法中打印以下内容：“Hi <name> !!!”

这里只显示 `main` 方法。

```java
public static void main(String[] args) {
    String nameToPass = "Jack";
    Hello obj1 = new Hello(nameToPass) {
        public void sayHello() {
            System.out.println("Hi " + name + " !!!");
        }
    };
    obj1.sayHello();
}
```

这段代码显示匿名类继承了其父类的构造函数，并且在此练习中清楚地看到，传递给匿名类构造函数的参数值已赋值给实例变量 `name`（我们在 `sayHello` 方法使用了该变量）。

### 13. 实例初始化块练习

修改上面的匿名类，使其具有一个实例初始化块，以便以大写形式存储在字段 `name` 中的值。通过修改 `sayHello` 方法打印第一行 `name` 来确认你的代码值（下方仅显示 `main`）

```java
public static void main(String[] args) {
    String x = "Jack";
    Hello obj1 = new Hello(x) {
        { // 这是一个实例初始化块
            name = name.toUpperCase();
        }
        public void sayHello() {
            System.out.println(name);
        }
    };
    obj1.sayHello();
}
```

## 练习你的 Java 一级水平

### 14. 黑天鹅匿名类练习

我有下面这个代表天鹅的类：

```java
class Swan {
    public void sayType() {
        System.out.println("I am a white swan!");
    }
}
```

我有一个 `Swan` 类数组，其中包含了代表我的 100 只天鹅中每一只的对象。我有 99 只白天鹅和一只黑天鹅。创建一个匿名类来处理黑天鹅；当为黑天鹅调用 `sayType` 方法时，它会说“我是一只黑天鹅”。

将所有天鹅放入数组中，从白天鹅开始，最后将黑天鹅放入数组。遍历天鹅列表并调用它们的 `sayType` 方法。

```java
class Swan {
    public void sayType() {
        System.out.println("I am a white swan!");
    }
}

public static void main(String[] args) {
    Swan[] swanArray = new Swan[100];
    for (int j = 0; j < 99; j++) {
        swanArray[j] = new Swan();
    }
    // 现在是黑天鹅的匿名类
    Swan blackSwan = new Swan() {
        public void sayType() {
            System.out.println("I am a black swan!");
        }
    };
    swanArray[99] = blackSwan;
    for (int j = 0; j < 100; j++) {
        swanArray[j].sayType();
    }
}
```

## 15. 局部类

### 什么是局部类？

局部类是直接定义在代码块中的类。该代码块可以是一个方法、循环结构或条件语句。局部类的实例可以在它们出现的块内进行实例化。

当代码块需要执行的操作最好分组为类和方法本身，以便将相关数据类在类内部在一起时，局部类会很有用。将这些内容分组为类的用处是代码的可读性。

### 16. 标准差计算练习

编写一个程序，确定并打印整数变量数组中的哪些点距离平均值超过 2 个标准差。使用局部类来存储传递的每个值以及它与平均值的偏差，并存储每个点到平均值的距离。

```java
public class Computation {
    public void printValues2sdAway(int[] values) {
        class DataPoint {
            // 此方法内部的局部类
            int value;
            float squareDeviation;
            float distanceFromMean;

            DataPoint(int value) {
                this.value = value;
            }
        }

        int numberOfPoints = values.length;
        int sum = 0;
        float mean = 0;
        float variance = 0;
        float standardDeviation;
        DataPoint[] myDataPoints = new DataPoint[numberOfPoints];

        for (int j = 0; j < numberOfPoints; j++) {
            sum += values[j];
        }
        mean = sum / numberOfPoints;
        for (int j = 0; j < numberOfPoints; j++) {
            variance += Math.pow(values[j] - mean, 2);
        }
        standardDeviation = (float) Math.sqrt(variance);
        System.out.println("The mean = " + mean);
        for (int j = 0; j < numberOfPoints; j++) {
            if (Math.abs(values[j] - mean) > 2 * standardDeviation) {
                System.out.println("point " + values[j] + " is more than 2 deviations");
            }
        }
    }
}
```

# 第 25 章：集合 I：泛型

集合是属于对象的内置类，例如 `List`。

## 什么是“集合”？

“集合”专门为元素设计并提供单独访问。许多集合包括栈、队列、树、映射和变体。

### 练习题

| 问题 | 选项/答案 |
|---|---|
| 1. 以下哪些是集合？ | `Stack`、`Queue`、`Set`、`List`、`Deque` 和 `Map` |
| 2. 哪种最适合表示：<br>a) 你将 5 本书叠放在放在一个盒子里<br>b) 商店收银台前排队的人<br>c) 书架上的书 | - **Stack (栈)**：后进先出结构；你放入的栈是先取出的。<br>- **Queue (队列)**：通常是先进先出；队列中的人是下一个服务的。<br>- **List (列表)**：取出或放入它们没有特定顺序。 |
| 3. Java 中“泛型”的概念是什么？ | Java 中泛型的概念是创建可以支持任何类的类或接口的手段。 |

### 4. 解释声明含义

解释以下声明的含义：`ArrayList<Integer> arrayList1 = new ArrayList<Integer>();`

我们正在告诉编译器我们要实例化一个包含 `Integer` 对象的 `ArrayList`。

这是书中首次出现“菱形运算符”。菱形运算符用于指定泛型参数；例如，对于 `ArrayList`，我们也可以使用菱形运算符指定 `<String, Boolean>`、`<any class>` 等。

> **注意：** 在 Java 7 中，不需要在菱形运算符的右侧再次声明左侧已经声明的类型（在本例中为 `String`）。在本章中我们将使用这两种方式。

### 6. 实例化 ArrayList<Character>

实例化名为 `characterList01` 的 `ArrayList<Character>` 变量。

```java
ArrayList<Character> characterList01 = new ArrayList<Character>();
```

### 7. 实例化 ArrayList<Object>

实例化名为 `objList01` 的 `ArrayList<Object>` 变量。

```java
ArrayList<Object> objList01 = new ArrayList<Object>();
```



# 第 25 章：集合 I

## 练习 8
解释为什么以下代码无效：`ArrayList<int> arrayList01 = new ArrayList<int>();`

代码无效，是因为 Java 集合只支持对象，不支持基本数据类型（`int`、`char`、`float` 等）。

## 练习 9
解释为什么以下代码无效：`ArrayList<boolean> arrayList01 = new ArrayList<boolean>();`

与上一个练习的原因相同，代码无效，因为 Java 集合仅作用于对象，而非基本数据类型；而 `boolean` 是基本数据类型。

## 练习 10
Java 中 `ArrayList` 数据结构内容的第一个索引是多少？

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> intList01 = new ArrayList<Integer>();
        intList01.add(1);
        intList01.add(60);
        intList01.add(70);
        intList01.add(80);
        intList01.add(90);
    }
}
```

重写上一个练习的解，这次使用 `Arrays.asList` 方法在实例化同时初始化 `ArrayList<Integer>`。

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<Integer>(Arrays.asList(1, 60, 70, 80, 90));
    }
}
```

> **重要：** 在带有数值的集合练习中，请理解这些数值并不是直接放入集合的，而是被自动装箱为对应的包装类对象。

将上一个练习中 `ArrayList` 对象第一个位置的值替换为 10。

*提示：* `ArrayList.set`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<Integer>(Arrays.asList(1, 60, 70, 80, 90));
        arrList01.set(0, 10); // 记住 0 是第 1 个位置，以此类推
    }
}
```

## 练习 11
在上一个练习解法生成的 `ArrayList` 对象 `arrList01` 的第二个位置插入值 20。

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(10, 60, 70, 80, 90));
        arrList01.add(1, 20); // 记住 0 是第 1 个位置，1 是第 2 个
        for (Integer j : arrList01) {
            System.out.println(j);
        }
    }
}
```

通过将上一个练习的内容连接到以下 `ArrayList` 的内容来增强后续练习：

`ArrayList<Integer> arrList02 = new ArrayList<>(Arrays.asList(100, 108, 110, 112, 120, 130, 130, 140, 150))`

打印增强后的 `arrList01` 内容。

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(10, 60, 70, 80, 90));
        arrList01.add(1, 20);
        ArrayList<Integer> arrList02 = new ArrayList<>(Arrays.asList(100, 108, 110, 112, 120, 130, 130, 140, 150));
        arrList01.addAll(arrList02);
        for (Integer j : arrList01) {
            System.out.println(j);
        }
    }
}
```

## 练习 12
参考上一个练习生成的 `arrList01`，通过在 `arrList01` 的第 3 个位置插入以下 `ArrayList` 来增强它：

`ArrayList<Integer> arrList02 = new ArrayList<>(Arrays.asList(30, 40, 50))`

打印修改后的 `arrList01` 内容。

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(10, 20, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 150));
        ArrayList<Integer> arrList02 = new ArrayList<>(Arrays.asList(30, 40, 50));
        arrList01.addAll(2, arrList02);
        for (Integer j : arrList01) {
            System.out.println(j);
        }
    }
}
```

## 练习 13
对于上一个练习生成的 `arrList01`，打印出：

1. 值 100 出现在 `arrList01` 中的位置。
2. 值 100 出现在 `arrList01` 中的最后一个位置。

*提示：* `ArrayList.indexOf`、`ArrayList.lastIndexOf`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 140));
        System.out.println("First position of 100: " + arrList01.indexOf(100));
        System.out.println("Last position of 100: " + arrList01.lastIndexOf(100));
    }
}
```

## 练习 14
打印 `arrList1` 的第 2 到第 5 个元素。

*提示：* `ArrayList.get`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList1 = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 140));
        for (int j = 1; j < 5; j++) {
            System.out.printf("%d = %s\n", j, arrList1.get(j));
        }
    }
}
```

## 练习 15
将 `arrList1` 的内容拷贝到另一个 `ArrayList`。打印新的 `ArrayList`。

*提示：* `ArrayList.addAll`（或构造函数拷贝）

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList1 = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 140));
        ArrayList<Integer> arrList2 = new ArrayList<>(arrList1);
        System.out.println(arrList2);
    }
}
```

## 练习 16
将 `arrList1` 中的所有元素拷贝到 `int` 数组。打印结果。

*提示：* `ArrayList.toArray`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList1 = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 140));
        Integer[] result = arrList1.toArray(new Integer[0]);
        System.out.println(Arrays.toString(result));
    }
}
```

## 练习 17
从 `arrList1` 中移除第 1 个和第 3 个元素。打印结果。

*提示：* `ArrayList.remove`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList1 = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 140));
        arrList1.remove(0);
        arrList1.remove(1); // 删除第一个元素后，原第 3 个元素变成了索引 1
        System.out.println(arrList1);
    }
}
```

## 练习 18
从上一个练习的 `arrList1` 中移除所有 130 的值。

*提示：* `ArrayList.remove(Object)` 或循环移除

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList1 = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 140));
        arrList1.removeIf(n -> n == 130); // 使用 removeIf 高效移除所有匹配项
        System.out.println(arrList1);
    }
}
```

## 练习 19
丢弃上练习生成的 `arrList1` 中除 100 和 110 以外的所有元素。打印生成的 `ArrayList`。

*提示：* `ArrayList.retainAll`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList1 = new ArrayList<>(Arrays.asList(10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 110, 120, 130, 130, 140, 140));
        ArrayList<Integer> arrListToKeep = new ArrayList<>(Arrays.asList(100, 110));
        arrList1.retainAll(arrListToKeep);
        System.out.println(arrList1);
    }
}
```

## 练习 20
重复“Clatters”章节的第 85 题，这次使用 `ArrayList<Shape>` 代替 `Shape[]`。

（此处仅显示 `main` 方法）

```java
public static void main(String[] args) {
    Circle obj1 = new Circle(2.7f);
    Square obj2 = new Square(15);
    Pentagon obj3 = new Pentagon(5);
    Hexagon obj4 = new Hexagon(3.7);

    ArrayList<Shape> shape = new ArrayList<>();
    shape.add(obj1);
    shape.add(obj2);
    shape.add(obj3);
    shape.add(obj4);
    for (Shape item : shape) {
        System.out.println("Object class = " + item.getClass());
        System.out.println("Area = " + item.area());
        System.out.println("Perimeter = " + item.perimeter());
        System.out.println();
    }
}
```

## 练习 21
将 `Collections` 的方法应用于 `ArrayList` 类型对象。

给定以下 `ArrayList` 定义：

`ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 0, 0));`

编写一个程序，将列表中的元素向右旋转 2 个位置。打印旋转后的 `ArrayList` 元素。

*提示：* `Collections.rotate`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 0, 0));
        Collections.rotate(arrList01, 2);
        System.out.println(arrList01);
    }
}
```

## 练习 22
使用与前一个练习相同的原始 `ArrayList`，将列表中的元素向左旋转 2 个位置。打印旋转后的 `ArrayList` 元素。

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 0, 0));
        Collections.rotate(arrList01, -2);
        System.out.println(arrList01);
    }
}
```

## 练习 23
打印前一个练习中 `ArrayList` 中数字 0 的出现频率。

*提示：* `Collections.frequency`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arrList01 = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 0, 0));
        int frequency = Collections.frequency(arrList01, 0);
        System.out.println("The frequency is " + frequency);
    }
}
```



将前一个练习中 `ArrayList` 中所有的值 `0` 替换为值 `5`。打印后的 `ArrayList` 元素。

提示：`Collections.replaceAll`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arr01 = new ArrayList<>(Arrays.asList(1,2,3,4,0,0));
        Collections.replaceAll(arr01, 0, 5);
        System.out.println(arr01);
    }
}
```

- 30. 记住在 `Collections.replaceAll` 方法调用中，值 `0` 和 `5` 会自动装箱为它们对应的 `Integer` 对象。

使用 `Collections.indexOfSubList` 和 `ArrayList.set` 方法，将前一个练习中旋转后的 `ArrayList` 中最后一次出现的值 `5` 替换为值 `6`。

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arr01 = new ArrayList<>(Arrays.asList(1,2,3,4,5,5));
        ArrayList<Integer> arr02 = new ArrayList<>(Arrays.asList(5));
        int positionOfLast5 = Collections.indexOfSubList(arr01, arr02);
        if(positionOfLast5 != -1) {
            arr01.set(positionOfLast5, 6);
        }
        System.out.println(arr01);
    }
}
```

- 31. 反转上述解决方案中生成的 `ArrayList` 元素的顺序。打印生成的 `ArrayList`。

提示：`Collections.reverse`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arr01 = new ArrayList<>(Arrays.asList(1,2,3,4,5,6));
        Collections.reverse(arr01);
        System.out.println(arr01);
    }
}
```

- 32. 随机打乱前一个练习中生成的 `ArrayList`。打印生成的 `ArrayList`。

提示：`Collections.shuffle`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arr01 = new ArrayList<>(Arrays.asList(1,2,3,4,5,6));
        Collections.shuffle(arr01);
        System.out.println(arr01);
    }
}
```

- 33. 打印前一个练习中 `ArrayList` 中的最大和最小元素。

提示：`Collections.min`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arr01 = new ArrayList<>(Arrays.asList(1,2,3,4,5,6));
        System.out.println("min=" + Collections.min(arr01));
        System.out.println("max=" + Collections.max(arr01));
    }
}
```

- 34. 交换前一个练习中 `ArrayList` 中的第一个和最后一个元素。打印生成的 `ArrayList`。

提示：`Collections.swap`

```java
import java.util.*;
public class ListPractice {
    public static void main(String[] args) {
        ArrayList<Integer> arr01 = new ArrayList<>(Arrays.asList(1,2,3,4,5,6));
        Collections.swap(arr01, 0, arr01.size() - 1);
        System.out.println(arr01);
    }
}
```

# Java 练习 Level 1

按照它们的“自然顺序”或放入 `TreeSet` 集合的对象实现的接口的 `compareTo` 方法确定的顺序进行排序。

## 44. 预测以下代码段的输出：

```java
TreeSet<Character> ss2 = new TreeSet<>();
ss2.add('C'); ss2.add('a'); ss2.add('X');
ss2.add('z'); ss2.add('Z'); ss2.add('A');
System.out.println(ss2);
```

输出：`[A, C, X, Z, z]`

解释：与前一个练习相同；`TreeSet` 以其自然顺序维护输入其中的数据。

## HashSet

## 45. 预测此程序的输出并解释其原因：

```java
import java.util.*;
public class Hash {
    public static void main(String[] args) {
        HashSet<Integer> hashSet = new HashSet<>(Arrays.asList(51, 54, 55, 55, 17, 18, 54));
        System.out.println(hashSet.size());
        System.out.println(hashSet);
    }
}
```

输出：`4`

`[17, 18, 54, 55]`

解释：`HashSet` 实际上是一种集合类型，它存储唯一的条目，会拒绝包含相同对象引用的尝试。

## 46. 使用 `HashSet` 统计并打印以下由 `String` 对象表示的儿歌中唯一单词的数量：

`String rhyme = "Mary had a little lamb\nlittle lamb\nMary had a little lamb that was as as snow";`

提示：将字符串拆分为标记，或许可以使用 `String.split`

```java
import java.util.*;
public class Hash {
    public static void main(String[] args) {
        String rhyme = "Mary had a little lamb\nlittle lamb\nMary had a little lamb\nthat was as snow";
        rhyme = rhyme.replace("\n", " ");
        String[] rhymeArray = rhyme.split(" ");
        HashSet<String> hashSet = new HashSet<>(Arrays.asList(rhymeArray));
        System.out.println("number of unique words in the verse = " + hashSet.size());
        for(String str:hashSet){
            System.out.println("  " + str + "");
        }
    }
}
```

## HashMap

## 47. 国家及其大小（平方公里）的列表如下：(欧洲, 1.018x10⁷),(北美, 2.449x10⁷),(非洲, 3.037x10⁷),(亚洲, 4.382x10⁷),(澳洲, 9.008x10⁵),(南美, 1.784x10⁷ 和 Antarctica, 1.372x10⁷）。编写一个程序，首先创建一个名为 `continents` 的 `HashMap` 类对象，然后将每对数据放入，以大洲名称为键，对象为值。插入后，使用增强循环打印输入到 `HashMap` 中的每个大洲的名称及其大小。

```java
import java.util.*;
public class Hash {
    public static void main(String[] args) {
        HashMap<String, Double> continents = new HashMap<>();
        continents.put("Europe",1.018E8);
        continents.put("North America",2.449E8);
        continents.put("Africa",3.037E8);
        continents.put("Asia",4.382E8);
        continents.put("Australia",2.0085E7);
        continents.put("South America",1.7840E8);
        continents.put("Antarctica",1.3728E8);

        // 现在从 HashMap 中获取键；将它们放入一个数组并遍历数组
        String[] keys = continents.keySet().toArray(new String[continents.size()]);
        if(keys.length < 0) return;
        for(String str:keys) {
            System.out.println("continent=" + str + "\tsize=" + continents.get(str));
        }
    }
}
```

> 注意：观察到键返回的顺序是不可预测的。

### 4. 修改前一个练习中的代码，按字母顺序打印大洲及其大小。

提示：在将键放入数组 `keys` 后对其进行排序。

只需在前一个解决方案的变量 `keys` 赋值后代码中添加以下内容：

提示：`Arrays.sort(keys);`

### 4. 编写一个程序，使用 `HashMap` 按大小的升序顺序打印大洲。

提示：使用大洲的大小作为键。

```java
import java.util.*;
public class Hash {
    public static void main(String[] args) {
        HashMap<String, Double> continents = new HashMap<>();
        continents.put("Europe",1.018E8);
        continents.put("North America",2.449E8);
        continents.put("Africa",3.037E8);
        continents.put("Asia",4.382E8);
        continents.put("Australia",2.0085E7);
        continents.put("South America",1.7840E8);
        continents.put("Antarctica",1.3728E8);

        String[] keys = continents.keySet().toArray(new String[continents.size()]);
        Arrays.sort(keys);
        for(String str:keys) {
            System.out.println("continent=" + str + "\tsize=" + continents.get(str));
        }
    }
}
```

# 练习你的 Java 级1

## 用法（接口作为类型）

如果你是一个古怪的人，你可以带上你那奇怪的方向盘去你的多车库库，并将其连接到你当天选择的车辆上。这听起来很奇怪，但它实际上是有效的。同样，在 Java 中，你可以声明一个类型为“相关接口”的引用，并将其赋值给实现该接口的任意类型的对象。它看起来如下：

```java
interface type <reference name> = 实现接口的类对象;
```

现在，请理解接口是不能实例化的，而像方向盘是可以实例化的。但我们可以使用 `Interface` 类型的引用来指向实现该接口的对象。

例如，我有一个用于方向盘的接口（我将其命名为 `ITurn`），它支持左转（`turnleft`）和右转（`turnright`）。我们定义接口 `ITurn` 如下：

```java
interface ITurn {
    public void turnleft();
    public void turnRight();
}
```

假设我们有一个类 `Mercedes300`，它“实现”了 `ITurn`：

```java
public class Mercedes300 implements ITurn {
    public void turnleft() {
        // 在 Mercedes300 的变速箱中执行必要的操作以向左转向
    }
    public void turnRight() {
        // 在 Mercedes300 的变速箱中执行必要的操作以向右转向
    }
}
```

通过该接口和 `Mercedes300` 类，我们可以执行以下操作：

```java
ITurn mySteering = new Mercedes300();
// 请仔细注意这里使用了接口引用来指向
// 实现相关接口的类的实际对象
mySteering.turnleft(); // Mercedes300 向左转向
mySteering.turnRight(); // Mercedes300 向右转向
```

### 单个类实现实现的多个接口

我们还提到了汽车的齿轮。因此，我们有一个命名为 `IGear` 的接口。它的方法将是升挡（`shiftUp`）和降挡（`shiftDown`）。因此，接口如下：

```java
interface IGear {
    public void shiftUp();
    public void shiftDown();
}
```

我们希望 `Mercedes300` 类也支持 `IGear` 接口。因此，`Mercedes300` 类的扩展如下：

```java
public class Mercedes300 implements ITurn, IGear { // 我们看到类同时实现了
// 多个接口。
    public void shiftUp() {
        // 在 Mercedes300 的变速箱中执行操作以升高位
    }
    public void shiftDown() {
        // 在 Mercedes300 的变速箱中执行操作以降低挡位
    }
    public void turnleft() {
        // 在 Mercedes300 的变速箱中执行必要的操作以向左转向
    }
    public void turnRight() {
    }
}
```

# 第 26 章：接口

在 `Mercedes300` 的变速箱中执行必要的操作以向右转向。

我们现在可以执行以下操作：

```java
IGear myGear = new Mercedes300(); // 因为 Mercedes300 类实现了 IGear，所以我们
// 使用了这样的声明。记住 Mercedes300 类也实现了 ITurn
// 并且使用 ITurn 类型的引用来引用 Mercedes300 实例仍然有效。
myGear.shiftUp();
myGear.shiftDown();
```

我们已经看到汽车可以实现多个接口。我们还看到可以使用不同类型的引用来访问实现接口的类的对象。我们在下面展示了如何让接口指向同一个对象：

```java
Mercedes300 mercedes01 = new Mercedes300();
ITurn steeringwheel01 = (ITurn)mercedes01; // 这种获取接口引用是有效的
// 指向实现该接口的对象
```

要让汽车右转，我可以使用以下两行之一：

`mercedes01.turnRight();`

或者

`mysteeringwheel01.turnRight();`

随之产生了一个问题：“既然相关对象已经拥有接口的方法，为什么要使用接口引用呢？”

使用接口引用的一个原因是在无关的对象上执行接口操作。我们看下面的示例。

假设我们有一个类（`Human`）也实现了 `ITurn`。显然，人类与汽车的转向方式是不同的。

观察通过使用接口引用，我们如何对实现接口的无关类的条目执行任何定义的方法：



# 第 26 章：接口

## 用法（接口作为类型）

如果你是一个古怪的人，你可以带上你那奇怪的方向盘去你的多车库库，并将其连接到你当天选择的车辆上。这听起来很奇怪，但它实际上是有效的。同样，在 Java 中，你可以声明一个类型为“相关接口”的引用，并将其赋值给实现该接口的任意类型的对象。它看起来如下：

```java
interface type <reference name> = 实现接口的类对象;
```

现在，请理解接口是不能实例化的，而像方向盘是可以实例化的。但我们可以使用 `Interface` 类型的引用来指向实现该接口的对象。

例如，我有一个用于方向盘的接口（我将其命名为 `ITurn`），它支持左转（`turnleft`）和右转（`turnRight`）。我们定义接口 `ITurn` 如下：

```java
interface ITurn {
    public void turnleft();
    public void turnRight();
}
```

假设我们有一个类 `Mercedes300`，它“实现”了 `ITurn`：

```java
public class Mercedes300 implements ITurn {
    public void turnleft() {
        // 在 Mercedes300 的变速箱中执行必要的操作以向左转向
    }
    public void turnRight() {
        // 在 Mercedes300 的变速箱中执行必要的操作以向右转向
    }
}
```

通过该接口和 `Mercedes300` 类，我们可以执行以下操作：

```java
ITurn mySteering = new Mercedes300();
// 请仔细注意这里使用了接口引用来指向
// 实现相关接口的类的实际对象
mySteering.turnleft(); // Mercedes300 向左转向
mySteering.turnRight(); // Mercedes300 向右转向
```

### 单个类实现多个接口

我们还提到了汽车的齿轮。因此，我们有一个命名为 `IGear` 的接口。它的方法将是升挡（`shiftUp`）和降挡（`shiftDown`）。因此，接口如下：

```java
interface IGear {
    public void shiftUp();
    public void shiftDown();
}
```

我们希望 `Mercedes300` 类也支持 `IGear` 接口。因此，`Mercedes300` 类的扩展如下：

```java
public class Mercedes300 implements ITurn, IGear { // 我们看到类同时实现了
// 多个接口。
    public void shiftUp() {
        // 在 Mercedes300 的变速箱中执行操作以升高位
    }
    public void shiftDown() {
        // 在 Mercedes300 的变速箱中执行操作以降低挡位
    }
    public void turnleft() {
        // 在 Mercedes300 的变速箱中执行必要的操作以向左转向
    }
    public void turnRight() {
        // 在 Mercedes300 的变速箱中执行必要的操作以向右转向
    }
}
```

我们现在可以执行以下操作：

```java
IGear myGear = new Mercedes300(); // 因为 Mercedes300 类实现了 IGear，所以我们
// 使用了这样的声明。记住 Mercedes300 类也实现了 ITurn
// 并且使用 ITurn 类型的引用来引用 Mercedes300 实例仍然有效。
myGear.shiftUp();
myGear.shiftDown();
```

我们已经看到汽车可以实现多个接口。我们还看到可以使用不同类型的引用来访问实现接口的类的对象。我们在下面展示了如何让接口指向同一个对象：

```java
Mercedes300 mercedes01 = new Mercedes300();
ITurn steeringwheel01 = (ITurn) mercedes01; // 这种获取接口引用是有效的
// 指向实现该接口的对象
```

要让汽车右转，我可以使用以下两行之一：

`mercedes01.turnRight();`

或者

`steeringwheel01.turnRight();`

随之产生了一个问题：“既然相关对象已经拥有接口的方法，为什么要使用接口引用呢？”

使用接口引用的一个原因是在无关的对象上执行接口操作。我们看下面的示例。

假设我们有一个类（`Human`）也实现了 `ITurn`。显然，人类与汽车的转向方式是不同的。

观察通过使用接口引用，我们如何对实现接口的无关类的条目执行任何定义的方法：

```java
Human human01 = new Human();
Human human02 = new Human();
Mercedes300 mercedes01 = new Mercedes300();
ITurn[] list = new ITurn[3]; // 我们创建了一个接口引用数组
list[0] = mercedes01; // 我们可以放入任何实现接口的对象
list[1] = human01; // 放入其中
list[2] = human02;
for (int count = 0; count < 3; count++)
    list[count].turnRight();
```

如果没有接口，只要这些对象具有共同的父类，我们就能将它们组合在一起并调用命名相似的方法。

## 接口的优点（总结）

总结来说，我们可以说接口的优点如下：

1. 接口允许我们通过一种共同机制来访问执行接口指定方法的不同类，从而避免了学习每个非接口类实现相同功能时可能呈现的不同方法签名。这还允许实现功能的类在无需任何担心的情况下更改实现，因为它们必须离开接口来……
2. 接口允许我们将并非相同祖先关系的对象分组，并执行接口中所指定的、与接口共有的操作。
3. 由于你只能继承自一个类，接口允许一个类实现它需要的多个接口。

## 练习你的 Java 级1

### 练习

2. 给定以下接口和类定义，判断以下哪行是无效的：

```java
interface ITakeoff();
interface ILanding();
public class Helicopter implements ITurn, IGear();
public class Airplane implements ITurn, IGear();
public Helicopter h01 = new Helicopter();
public Helicopter h02 = new Helicopter();
public Airplane a01 = new Airplane();
public Airplane a02 = new Airplane();
ILanding landings[] = new ILanding[];
landings[0] = h01;
landings[1] = h02;
landings[2] = h03;
landings[3] = h04;
ArrayList<ITakeoff> takeoffs = new ArrayList<ITakeoff>();
takeoffs.add(h01);
takeoffs.add(null);
takeoffs.add(h03);
```

**答案**：所有代码行都是有效的！正如练习1的解答所示，接口类型的引用变量可以引用实现接口的类。`Helicopter` 和 `Airplane` 类都实现了 `ITurn` 和 `ILanding`，因此它们都是有效的。对于 `ArrayList<ITakeoff>` 的声明，就像 `ArrayList<Integer>` 有效一样，`ArrayList<interface>` 也是有效的。

3. 写出一个继承另一个类并实现多个接口的类声明语法：

**答案**：`<访问权限> <类名> extends <父类> implements <接口>,...,<接口>`

类必须位于接口名称之前。参见练习1的解答。

4. 接口成员的访问级别是什么？

**答案**：接口成员的级别是 `public`（公有）。

5. 接口最像哪种类？

**答案**：接口不是抽象类，因为与抽象类不同，接口中的方法不需要实现（但至少应该指定），而且，当在具体类中实现接口时，接口的所有方法都必须实现，这与抽象类一样。

6. 一个类可以实现多少接口？

**答案**：没有限制。

7. 接口相对于抽象类提供了什么？

**答案**：主要优点是一个具体类可以实现多个接口，然而它一次只能继承自一个类，当这种继承不是给定类之间正确的关系时；例如，汽车拥有组件方向盘和变速箱；即使 Java 允许继承，汽车大多数时候并不是方向盘或变速箱的后代，它们仅仅是具有各自接口特定参数的汽车成员。

此时，邀请读者审阅任意数量内置类的官方类定义（例如 `String`、`List`、`StringBuffer`、`ArrayList` 等，查看与之相关的接口并在网上搜索相关接口的定义。

读者受邀查看许多内置接口的官方定义（例如 `Collection`、`Iterator`），并观察实现相关接口的内置类列表。

```java
public interface Greeting {
    public void morningGreeting();
    public void afternoonGreeting();
    public void eveningGreeting();
}
```

```java
public class Person {
    private String firstName;
    private String lastName;
    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }
}
```

创建一个名为 `EnglishGreeter` 的类，它继承 `Person` 类并实现 `Greeting` 接口。



```java
public class EnglishGreeter extends Person implements Greeting {
    public EnglishGreeter(String firstName, String lastName) {
        super(firstName, lastName);
    }
    public void morningGreeting() {
        System.out.println("Good morning!");
    }
    public void afternoonGreeting() {
        System.out.println("Good afternoon!");
    }
    public void eveningGreeting() {
        System.out.println("Good evening!");
    }
}
```

注意：在这种情况下，我们同时看到了接口的实现和类的扩展。

- 创建以下继承自 `Person` 类并实现 `Greeting` 接口的类：

1. 一个名为 `FrenchGreeter` 的类。该类应该用法语打印问候语。

2. 一个名为 `SpanishGreeter` 的类。该类应该用西班牙语打印问候语。

注意：可以在网上找到翻译软件/链接，例如 <https://translate.google.com>

```java
public class FrenchGreeter extends Person implements Greeting {
    public FrenchGreeter(String firstName, String lastName) {
        super(firstName, lastName);
    }
    public void morningGreeting() {
        System.out.println("Bonjour!");
    }
    public void afternoonGreeting() {
        System.out.println("Bon après-midi!");
    }
    public void eveningGreeting() {
        System.out.println("Bonne soirée!");
    }
}
```

```java
public class SpanishGreeter extends Person implements Greeting {
    public SpanishGreeter(String firstName, String lastName) {
        super(firstName, lastName);
    }
    public void morningGreeting() {
        System.out.println("Buenos dias!");
    }
    public void afternoonGreeting() {
        System.out.println("Buenas tardes!");
    }
    public void eveningGreeting() {
        System.out.println("Buenas noches!");
    }
}
```

# 练习你的 Java 1

## 10. 在命名的问候中，为之前创建的每个问候创建一个对象

问候者的名字是 Matthew Charlis、Jacques Gorm 和 Hernandez Po；分别使用英语、法语和西班牙语问候语。将代表它们的对象放入类型为 `Greeting` 的 `ArrayList` 中，然后使用循环打印每种语言的原始问候语。

```java
import java.util.ArrayList;
public class greeting {
    public static void main(String[] args) {
        Greeting englishGreeter = new EnglishGreeter("Matthew", "Charlis");
        Greeting frenchGreeter = new FrenchGreeter("Jacques", "Gormand");
        Greeting spanishGreeter = new SpanishGreeter("Hernandez", "Po");

        ArrayList<Greeting> greeters = new ArrayList<>();
        greeters.add(englishGreeter); greeters.add(frenchGreeter); greeters.add(spanishGreeter);
        for(Greeting greeting : greeters) {
            greeting.morningGreeting();
        }
    }
}
```

注：这里展示了我们如何将对象放入接口类型的变量/引用中的方法；这个概念在第一个练习的解答中讨论过。这只是一个设计选择，用于展示使用接口来引用实现相关接口的对象；这与你下面编写代码的效果相同：

```java
Greeting englishGreeter = new EnglishGreeter("Matthew", "Charlis");
Greeting frenchGreeter = new FrenchGreeter("Jacques", "Gormand");
Greeting spanishGreeter = new SpanishGreeter("Hernandez", "Po");
```

然后我们执行以下操作：

```java
ArrayList<Greeting> greeters = new ArrayList<>();
greeters.add(englishGreeter); greeters.add(frenchGreeter);
greeters.add(spanishGreeter);
```

注意对接口的强制转换。

从解答中也可以看到我们如何将无关的对象放入集合中，该集合的类型是所有对象都实现的接口，这使得我们能够使用循环对没有继承关系的对象执行共同的操作。

## 11. 默认接口方法

如果我们想在我们的 `Greeting` 语言中实现一个默认（default）问候，我们应该如何做？

我们可以使用英语语言将每一个实现为“默认方法（default method）”。在接口方法中引入默认功能的能力是在 Java 8 中引入的。注意：Java 接口中的默认方法也称为“防御方法（defender methods）”。

## 12. 使用指定的语言用默认方法实现 `Greeting` 接口

之后，重新实现实现 `Greeting` 的类以考虑到接口中的默认方法。

```java
public interface Greeting {
    default void morningGreeting() { // 这些方法中都有 default 关键字
        //methods
        System.out.println("Good morning!");
    }
    public void afternoonGreeting() {
        System.out.println("Good afternoon!");
    }
    default void eveningGreeting() {
        System.out.println("Good evening!");
    }
}
```

```java
public class EnglishGreeter extends Person implements Greeting {
  public EnglishGreeter(String firstName, String lastName) {
    super(firstName, lastName);
  }
}
```

`FrenchGreeter` 和 `SpanishGreeter` 类保持不变。实际上它们实现了接口的默认方法。可以看到 `EnglishGreeter` 不需要重新实现这些方法，因为接口中的默认方法已经足够了。

## 13. 查看此接口的定义

### 1. 接口的用途

### 2. 接口定义中 `<T>` 的含义

## 2. 接口定义中 `<T>` 的含义

1. `Comparable` 接口包含一个名为 `compareTo` 的方法，该方法的任务是将实现接口的类的实例与另一个同类类的对象进行比较，并返回一个整数，表示大、小或相等。就 `T` 而言，当一个类实现了 `Comparable` 时，通过 `compareTo` 方法实现的该类对象的“自然排序（natural ordering）”。

2. `<T>` 是一个占位符，指定该类型设计为支持泛型（即任何类型）。因此，我们可以为任何想要的引用类型使用该接口；我们只需要在实际类型的位置替换占位符 `T`；例如，如果我们想为之前定义的 `Person` 类实现 `Comparable` 接口，我们会这样声明 `Person` 类：

```java
class Person implements Comparable<Person>
```

可以看到在我们实现 `Comparable` 的钻石运算符中，`Person` 类占据了占位符 `T` 的位置。

## 14. `Comparable` 接口中 `compareTo` 方法的方法签名如下：

`int compareTo(T o)`

解释该方法参数列表组成部分的含义。

参数列表仅指示一个对象类型，由字母 `T` 表示；这是与接口定义中相同的 `T`（见前文）。因此，我们在类定义语句中替换 `T` 的任何类型，就是我们在具有类型占位符的方法中替换的类型。继续 `Person` 类实现 `Comparable` 的示例，当我们在 `Person` 类中实现接口方法 `compareTo` 时，我们编写如下的方法签名：

```java
int compareTo(Person o)
```

显然 `Person` 取了占位符 `T` 的位置。字母 `o` 是 `T` 所代表的类型实例的变量名。

## 15. 以下代码不起作用。解释为什么。

```java
import java.util.ArrayList;
import java.util.Collections;
public class Person {
  private String firstName;
  private String lastName;
}
```

# 练习你的 Java 1

```java
public Person(String firstName, String lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}
public static void main(String[] args) {
    Person p1 = new Person("Marie", "Tabith");
    Person p2 = new Person("Ruddy", "Gump");
    Person p3 = new Person("George", "Hudderstein");
    Person p4 = new Person("Peter", "Hudderstein");
    ArrayList<Person> personList = new ArrayList<>();
    personList.add(p1);personList.add(p2);personList.add(p3);personList.add(p4);
Collections.sort(personList);
for(Person p:personList) {
    System.out.println(p.lastName + ", " + p.firstName);
}
```

`Collections.sort` 方法要求其调用的所有类对象都实现 `Comparable` 接口，以便它使用实现的 `compareTo` 方法。我们没有为该类实现该接口，这就是代码无法运行的原因。

## 16. 为 `Person` 类实现 `Comparable` 接口

对象的顺序应根据字段 `firstName` 和 `lastName` 的字母顺序确定，顺序为 `lastName` 后是 `firstName`。

为了测试你的实现，请将下面列出的名称放入 `ArrayList<Person>` 中，然后应用 `Collections.sort` 方法，打印出排序后数组的内容。结果应为：

Gump, Ruddy

Hudderstein, George

Hudderstein, Peter

Tabith, Marie

```java
public class Person implements Comparable<Person> {
    private String firstName;
    private String lastName;
    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }
    public int compareTo(Person p) {
        if (this.lastName.compareTo(p.lastName) < 0) {
            return(-1);
        } if (this.lastName.compareTo(p.lastName) > 0) {
            return (1);
        }//否则它们相等，则比较第一个名字
        if (this.firstName.compareTo(p.firstName) < 0) {
            return(-1);
        } if (this.firstName.compareTo(p.firstName) > 0) {
            return(1);
        } else
            return(0);
    }
    public static void main(String[] args){
        // main 方法与之前的练习相同
    }
}
```

## 17. 解释超接口（super-interface）和子接口（sub-interface）的概念

在 Java 中，接口可以“扩展”另一个接口。被扩展的接口称为超接口，执行扩展的接口称为子接口。

扩展的语法如下：

`子接口 extends 超接口, 超接口, ...超接口`

# 第 26 章：交织/嵌套 (Interlaces)

## 18. 列出以下每个接口的子接口：(1) `Queue`, (2) `ConcurrentLinkedQueue<E>` (3) `BlockingQueue`, (4) `Collection`

| 接口 | 子接口 |
| :--- | :--- |
| `Queue<E>` | `Collection<E>`, `Iterable<E>` |
| `ConcurrentLinkedQueue<E>` | `Serializable`, `Iterable<E>`, `Collection<E>`, `Queue<E>` |
| `BlockingQueue<E>` | `Collection<E>`, `Iterable<E>`, `Queue<E>` |
| `Collection<E>` | `Iterable<E>` |

## 19. 列出以下每个接口的子接口：(1) `Queue`, (2) `ConcurrentLinkedQueue<E>` (3) `BlockingQueue`

| 接口 | 子接口 |
| :--- | :--- |
| `Queue<E>` | `BlockingQueue<E>`, `BlockingQueue<E>`, `Deque<E>`, `TransferQueue<E>` |
| `ConcurrentLinkedQueue<E>` | 无 |
| `BlockingQueue<E>` | `BlockingDeque<E>` |

## 20. 接口扩展另一个接口意味着什么？对于被扩展接口的方法实现会有什么影响？

接口扩展另一个接口的实际含义是，子接口现在被视为其超接口以及自身方法的集合体。子接口并不实现其超接口的方法。我们通过示例来说明这一点：

```java
public interface A{
    public void methodA1();
    public void methodA2();
}
```

```java
public interface B extends A{
    public void methodB1();
    public void methodB2();
}
```

现在如果我们有一个实现接口 `B` 的类 `X`，该类如下：

```java
class X {
    // 类 X 现在必须实现接口 A 和接口 B 的所有方法
    public void methodA1(){}
    public void methodA2(){}
    public void methodB1(){}
    public void methodB2(){}
}
```

## 21. 接口与匿名类的结合

`MouseListener` 是一个接口。解释下面代码中尝试实例化 `MouseListener` 时发生了什么。



```java
MouseListener ml = new MouseListener(){
    public void mouseClicked(MouseEvent event) {
        button0.setText("你点击了我!");
    }
    public void mouseEntered(MouseEvent event) {
        button0.setText("你正在悬停在这里!");
    }
    public void mouseExited(MouseEvent event) {
        button0.setText("你移离开了这里!");
    }
    public void mousePressed(MouseEvent event) {
        button0.setText("你正在按下我!");
    }
    public void mouseReleased(MouseEvent event) {
        button0.setText("你松开了我!");
    }
};
```

记住，接口不能实例化，但我们可以使用匿名类来实现它。由于 `MouseListener` 是一个接口，因此当我们写 `new MouseListener()` 时，并不是在创建一个接口，而是创建一个实现该接口的匿名类。当我们写 `<interface>` 时，我们是在指向实现接口的对象。

# 练习你的 Java 1

# 第 27 章：集合 II：带有接口的集合

在之前的章节中，我们查看了集合和接口。在本章中，我们将查看它们之间的关系，Java 为每个组提供了内置接口。我们还会查看 `Iterator` 和 `List` 的定义。

- 1. 列出 Java 提供的不同集合接口。

Java 提供的集合接口有：`Set`、`List`、`Queue` 和 `Deque`。

应该注意，`Set`、`List`、`Queue` 和 `Deque` 接口都有超接口。

- 2. 给定如下定义的 `ArrayList<Integer>`：

`ArrayList<Integer> list01 = new ArrayList<>();`

解释为什么以下赋值是有效的：

`Serializable ser01 = list01;`

`Cloneable cloneable01 = list01;`

`Iterable<Integer> iter01 = list01;`

`Collection<Integer> collection01 = list01;`

`RandomAccess rand01 = list01;`

提示：查看 `ArrayList` 定义及其实现的所有接口。

这些赋值都是有效的，因为 `ArrayList<T>` 实现了每一个接口。正如我们在接口章节中看到的，接口引用变量可以引用任何实现该接口的类对象，上面的赋值有效。

- 3. 解释为什么以下赋值是有效的：

`Serializable ser01 = new ArrayList<Integer>();`

`Serializable ser02 = new TreeMap<String, Integer>();`

`Serializable ser03 = new LinkedList<Float>();`

所有对 `Serializable` 接口引用的赋值都是有效的，因为问题中每个对象类型实现了 `Serializable` 接口。

- 4. 给定以下声明：

`Serializable ser01 = new ArrayList<Integer>();`

编写一个程序，显示向接口引用 `ser01` 指向的 `ArrayList<Integer>` 实例插入值 27。打印出问题中 `ArrayList<Integer>` 的内容。

```java
import java.io.Serializable;
import java.util.ArrayList;

public class InterfacesAndCollections {
    public static void main(String[] args) {
        Serializable ser01 = new ArrayList<Integer>();
        ((ArrayList<Integer>) ser01).add(27);
        // 注意我们如何对 ser01 强制转换为 ArrayList<> 以“看到”
        // ser01 所被引用的实际对象，因为它确实是一个 ArrayList<Integer>。
        // 当我们应用强制转换时，就可以调用适用于“转换后”
        // 类型的方法的方法，正如我们在这里应用的 ArrayList<T>.add 方法一样。
        for (Integer j : (ArrayList<Integer>) ser01) {
            System.out.println(j); // 我们打印出变量
        }
    }
}
```

# 练习你的 Java 级 1

```java
// 再次，我们像之前的那样对 ser01 进行强制转换，以便
// “看到”它引用的对象作为一个 ArrayList<Integer>。
ArrayList<Integer> arrayList01 = (ArrayList<Integer>) ser01;
```

然后我们就可以在后续应用了对 `ser01` 类型进行强制转换的地方使用变量 `arrayList01`，如下所示：

```java
ArrayList<String> string01 = new ArrayList<String>();
```

解释像下面的示例所示，使用其主接口 `List` 的引用来引用 `arrayList` 的用处：

`List<String> list01 = new ArrayList<String>();`

通过观察发现，`ArrayList` 的许多关键方法实际上都是该接口方法的实现，使用接口 `List` 的对象引用不会丢失通用性。此外，使用 `List<String>` 变量的一个用处是，如果我们决定将它引用的特定集合更改另一个实现该接口的集合，我们只需要在对象的初始实例化点进行更改，而不需要在整个代码中进行修改。现在我们为什么可能将对象更改为不同的类型（例如从 `ArrayList` 变为同样实现了 `List` 接口的 `LinkedList`）。我们可能出于性能考虑想进行这种更改。Java 通过许多接口对集合类型分组有助于这种修改。还需要注意的是，接口的一个关键优势是尽可能将访问数据的概念与存储数据的实现分开。

# 迭代器 (Iterators)

- 6. 什么是迭代器？

迭代器是一个对象，它有助于以顺序方式（顺序方式意味着涉及的类型实现了 `Iterator` 认为的任何顺序方式）访问集合中的元素。

- 7. 预测以下代码的输出，并解释用于输出的利用机制：

```java
import java.util.Iterator;
import java.util.LinkedList;
import java.util.List;

public class InterfacesAndCollections {
    public static void main(String[] args) {
        List<Integer> list01 = new LinkedList<Integer>();
        list01.add(1);
        list01.add(3);
        list01.add(5);
        list01.add(9);
        Iterator<Integer> it01 = list01.iterator();
        while (it01.hasNext()) {
            Integer j = it01.next();
            System.out.print(j + " ");
        }
    }
}
```

输出: `1 3 5 9`

所利用的机制被称为 `Iterator`（迭代器）。在上方标记为 1 的代码行中，我们看到一个 `Iterator<Integer>` 引用被分配了一个来自相关 `List<T>` 实例的对象作为“迭代器对象”。

迭代器对象有助于以顺序方式（顺序方式意味着涉及的类型它在内部实现了 `Iterator` 的某种方式）访问集合的元素。

我们在标记为 2 到 5 的行中看到了迭代器对象的使用。我们看到了它的两个方法的使用，特别是 `hasNext()`，它用于判断我们正在迭代的元素列表集合中是否有任何元素，然后使用 `next()` 方法，该方法用于获取下一个元素，并将迭代器对象的内部“指针”移动到下一个元素（如果有的话）。

所有集合都实现了 `Iterator` 接口。

如果读者尚未阅读，邀请他们学习 `Iterator` 接口的官方文档。

- 8. 增强上述练习中的程序，使用 `Iterator` 从给出的 `List<Integer>` 中移除数字 5。删除后，使用 `Iterator` 打印 `List<Integer>` 的内容。

```java
public class InterfacesAndCollections {
    public static void main(String[] args) {
        List<Integer> list01 = new LinkedList<>();
        list01.add(1);
        list01.add(3);
        list01.add(5);
        list01.add(7);
        list01.add(9);
        Iterator<Integer> it01 = list01.iterator();
        while (it01.hasNext()) {
            Integer j = it01.next();
            if (j == 5) it01.remove();
        }

        // 现在使用迭代器打印
        Iterator<Integer> it02 = list01.iterator();
        while (it02.hasNext()) {
            System.out.print(it02.next() + " ");
        }
    }
}
```

- 9. 给出一个包含 1, 3, 5, 7, 9 的 `List<Integer>`，使用 `Iterator` 为每个元素添加 11，然后使用 `Iterator` 打印内容。

```java
public class InterfacesAndCollections {
    public static void main(String[] args) {
        List<Integer> list01 = new LinkedList<>();
        list01.add(1);
        list01.add(3);
        list01.add(5);
        list01.add(7);
        list01.add(9);
        Iterator<Integer> it01 = list01.iterator();
        while (it01.hasNext()) {
            Integer j = it01.next();
            list01.add(11);
        }

        // 现在使用迭代器打印
        Iterator<Integer> it02 = list01.iterator();
        while (it02.hasNext()) {
            System.out.print(it02.next() + " ");
        }
    }
}
```

# 第 27 章：集合 II (Collections II)

# 练习你的 Java 级 1

11. 有一个包含 1, 3, 5, 7, 9, 10, 11 值的 `LinkedList<Integer>`，使用 `Iterator` 遍历列表并打印其内容。

```java
public class InterfacesAndCollections {
    public static void main(String[] args) {
        List<Integer> list01 = new LinkedList<Integer>();
        list01.add(1);
        list01.add(3);
        list01.add(5);
        list01.add(7);
        list01.add(9);
        list01.add(10);
        list01.add(11);

        // 现在使用迭代器打印
        Iterator<Integer> it01 = list01.iterator();
        while (it01.hasNext()) {
            Integer j = it01.next();
            System.out.print(j + " ");
        }
    }
}
```

12. 有一个包含 1, 3, 5, 7, 9, 10, 11 值的 `LinkedList<Integer>` `list01`，使用 `Iterator` 反向遍历并打印其内容。提示：查看方法 `List(int index)`

```java
public class InterfacesAndCollections {
    public static void main(String[] args) {
        List<Integer> list01 = new LinkedList<>();
        list01.add(1);
        list01.add(3);
        list01.add(5);
        list01.add(7);
        list01.add(9);
        list01.add(10);
        list01.add(11);
        ListIterator<Integer> it01 = list01.listIterator(list01.size());
        while (it01.hasPrevious()) {
            Integer j = it01.previous();
            System.out.print(j + " ");
        }
    }
}
```

13. 重复练习 9，这次使用 `Iterator`。遍历一次 `List<Integer>` 以同时完成其内容的添加和打印。

```java
public class InterfacesAndCollections {
    public static void main(String[] args) {
        List<Integer> list01 = new LinkedList<>();
        list01.add(1);
        list01.add(3);
        list01.add(5);
        list01.add(7);
        list01.add(9);
        ListIterator<Integer> it01 = list01.listIterator();
        while (it01.hasNext()) {
            Integer j = it01.next();
            it01.set(j + 11);
            // 好的，后退一次再打印出来
            if (it01.hasPrevious()) {
                System.out.print(it01.previous() + " ");
                it01.next(); // 因为我们后退了1，所以我们需要向前移动1
            }
        }
    }
}
```

# 列表迭代器 (ListIterator)

`ListIterator` 是 `Iterator` 的子接口，因此继承了它的所有方法。然而，`ListIterator` 超出了 `Iterator` 接口的能力，增加了反向遍历 List 元素的能力。此外，由于 `Iterator` 只能删除，而 `ListIterator` 还可以添加或替换元素。

14. 对于实现 `List` 接口的类，比较 `Iterator` 和 `ListIterator` 的功能与增强型 for 循环的区别。

实际上，增强型循环使用了 `Iterator` 的功能！在那种意义上，增强型循环只是 `Iterator` 的一个外壳。`Iterator` 相比于增强型 for 循环的一个优势是它支持通过其 `remove()` 方法移除元素。然而，对于 `ListIterator`，除了具有 `Iterator` 的功能外，`ListIterator` 还可以对实现该接口的对象执行以下操作：(1) 添加元素 (2) 返回元素索引 (3) 替换元素以及 (4) 反向遍历元素。

### 15 使用 ListIterator 向集合中插入

我有一个 `LinkedList<Integer>`，初始只填充了奇数。使用 `ListIterator` 遍历该 `LinkedList<Integer>`，并在每个奇数之后插入紧随其后的偶数。生成的 `LinkedList<Integer>` = 如果 `LinkedList<Integer>` 的内容为 {1, 3, 5, 7} 那么插入后的结果将变为 (1, 2, 3, 4, 5, 6, 7, 8)。



```java
import java.util.LinkedList;
import java.util.List;
import java.util.ListIterator;

public class AndCollections {
    public static void main(String[] args) {
        List<Integer> list01 = new LinkedList<Integer>();
        list01.add(1);list01.add(3);list01.add(15);list01.add(7);
        ListIterator<Integer> it01 = list01.listIterator();
        while(it01.hasNext()){
            Integer j = it01.next();
            if(j % 2 == 1) {
                it01.add(j+1);
            }
        }
        ListIterator<Integer> it02 = list01.listIterator();
        while(it02.hasNext()){
            Integer j = it02.next();
            System.out.print(j + " ");
        }
    }
}
```

我有一个 `List<Integer>`，其中至少两个不同的数字且按升序排列。编写一个程序，使用 `List<Integer>` 在 `List<Integer>` 中出现的数字之间插入所有缺失的数字。例如，如果 `List<Integer>` 的原始内容为 {1, 5, 8}，运行你的程序后，其内容应变为 {1, 2, 3, 4, 5, 6, 7, 8}。

# 第 28 章：属性、计算机环境与计算机信息

本章介绍了一些练习，用于练习和增强如何使用 Java 内置方法来确定有关计算机信息的知识。本章包含了关于属性概念、确定可用 JVM 运行时状态、处理器计数、驱动器和文件系统信息、操作系统版本、计算机名称、系统运行时间等相关主题的练习。

本章利用的关键类是 `Runtime` 和 `System`。某些练习还要求使用 Java Beans 来获取系统信息。

## Java 中属性的概念是什么？

Java 中的属性概念非常简单。它特指管理已赋值的值的环境常量。只要 JVM 正在运行，就可以访问属性。属性存在以供你的程序根据需要随时使用。请注意，属性的值也可以被修改。

JVM 至少通过以下方式获取这些属性：

* 从操作系统获取
* 在启动 JVM 时从命令行获取（即用户可以在命令行上指定属性的值）
* 可以直接从你的程序内部创建新属性

系统属性在很大程度上涉及 JVM 运行的硬件规范、操作系统、JVM 运行的用户配置以及 JVM 本身。

运行该程序以获取你的 JVM 当前设置的属性列表及其值。

```java
import java.util.Properties;
public class PracticeYourJava {
    public static void main(String[] args) {
        Properties p = System.getProperties();
        p.list(System.out);
    }
}
```

## 2. Java 安装和配置信息

使用 `System.getProperty` 方法，打印出以下信息：(1) 你当前运行的 Java 版本 (2) JVM 安装的目录以及 3) JAR 文件的类路径。

提示：`java.version`、`java.home` 和 `java.class.path`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println("Java version: " + System.getProperty("java.version"));
        System.out.println("JRE installation directory: " + System.getProperty("java.home"));
        System.out.println("JAVA CLSPATH: " + System.getProperty("java.class.path"));
    }
}
```

## 3. Java 运行时

`Runtime.maxMemory()` 的值定义了 JVM 允许请求的最大 RAM 数量。

解释如何解释从此方法返回的值。

所涉及的值应解释如下：如果返回的值 = `Long.MAX_VALUE`，则对 JVM 请求多少内存没有实际限制。如果它是任何其他值，则该值是 JVM 可以请求的最大内存量。

## 4. 使用 `Runtime.getRuntime()` 方法返回的类的实例，打印出以下信息

(1) JVM 当前可用的 RAM 数量 (2) JVM 使用的 RAM 数量 (3) JVM 允许请求的最大 RAM 数量。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        Runtime rt = Runtime.getRuntime();
        System.out.println("Currently available to the JVM: " + rt.freeMemory());
        System.out.println("Currently used by the JVM: " + (rt.totalMemory() - rt.freeMemory()));
        System.out.println("Maximum RAM allowed: " + rt.maxMemory());
    }
}
```

## 5. 打印 JVM 正在使用的工作目录。

## 6. 打印信息：(1) 版本 (2) 供应商。

## 7. 打印信息：(1) 操作系统名称，(2) 架构以及 (3) 版本。

## 8. 使用 `Runtime` 打印有多少个处理器可供使用。

# 第 28 章：属性与计算机环境

注意：如果路径是正斜杠 `/`，在 UNIX 上则是反斜杠 `\\`。

## 9. 用户信息

编写一个程序来确定 JVM 运行的用户名。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println("User name: " + System.getProperty("user.name"));
    }
}
```

## 10. 打印用户的主目录。

提示：`user.home`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println("User home: " + System.getProperty("user.home"));
    }
}
```

## 11. 使用通过 `FileSystem.getFileSystem()` 方法获取的 `FileSystem` 的 `getFileSystem()` 方法，编写一个程序确定并打印 JVM 运行的目录。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        FileSystem fileSys = FileSystem.getFileSystem();
        System.out.println("The home directory is " + fileSys.getHomeDirectory());
    }
}
```

## 12. 路径分隔符

路径分隔符是正斜杠 `/`，在 UNIX 上则是反斜杠 `\\`。由于你的 Java 程序应该能够在任何操作系统运行，编写一个程序获取并打印你正在运行系统的文件分隔符。

提示：`file.separator`

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println("File separator : " + System.getProperty("file.separator"));
    }
}
```

## 13. 编写一个程序打印你系统使用的路径分隔符。

（路径分隔符是连接一组路径的字符，例如用于你的 Java CLSPATH 变量）。

```java
public class PracticeYourJava {
    public static void main(String[] args) {
        System.out.println("Path separator : " + System.getProperty("path.separator"));
    }
}
```

## 14. 使用 bean 查找系统信息

使用 `OperatingSystemMXBean` 引用来获取由 `ManagementFactory` 静态方法 `ManagementFactory.getOperatingSystemMXBean()` 返回的对象，确定并打印出以下信息：

* 处理器架构
* 可用处理器数量
* 操作系统名称
* 操作系统版本

```java
import java.lang.management.OperatingSystemMXBean;
import java.lang.management.ManagementFactory;

public class PracticeJava {
    public static void main(String[] args) {
        OperatingSystemMXBean osmxbean = ManagementFactory.getOperatingSystemMXBean();
        System.out.println("The system architecture = " + osmxbean.getArch());
        System.out.println("Available processors = " + osmxbean.getAvailableProcessors());
        System.out.println("Operating System OS Name = " + osmxbean.getName());
        System.out.println("OS Version = " + osmxbean.getVersion());
    }
}
```

注意：记住，我们也可以像练习 8 中之前的那样，使用 `Runtime.availableProcessors()` 方法来确定系统的处理器数量。

## 15. 使用上一个练习中的相同对象，确定过去一分钟的平均负载（如果你运行的系统支持该值）。

```java
import java.lang.management.OperatingSystemMXBean;
import java.lang.management.ManagementFactory;

public class PracticeJava {
    public static void main(String[] args) {
        OperatingSystemMXBean osmxbean = ManagementFactory.getOperatingSystemMXBean();
        float loadavg = (float)osmxbean.getLoadAverage();
        if (loadavg < 0) {
            System.out.println("Load avg is not supported");
        } else {
            System.out.println("System load in last minute = " + osmxbean.getLoadAverage());
        }
    }
}
```

## 16. 使用类型为 `RuntimeMXBean` 的接口引用指向由静态方法 `ManagementFactory.getRuntimeMXBean()` 返回的对象，确定并打印以下内容：

* JVM 供应商
* 规范版本
* JVM 实现

```java
import java.lang.management.ManagementFactory;
import java.lang.management.RuntimeMXBean;

public class PracticeJava {
    public static void main(String[] args) {
        RuntimeMXBean rmxbean = ManagementFactory.getRuntimeMXBean();
        System.out.println("JVM vendor = " + rmxbean.getVendor());
        System.out.println("spec version = " + rmxbean.getSpecVersion());
        System.out.println("implementation version = " + rmxbean.getVersion());
    }
}
```

注意：打印出的信息对应属性 `vm.vendor`、`specification.version` 和 `vm.version`。

## 17. 使用上一个练习中的相同对象，确定以下内容：

* CLASSPATH
* JVM 启动类
* 库路径

```java
import java.lang.management.ManagementFactory;
import java.lang.management.RuntimeMXBean;
import java.util.*;

public class PracticeJava {
    public static void main(String[] args) {
        RuntimeMXBean rmxbean = ManagementFactory.getRuntimeMXBean();
        System.out.println("ClassPath = " + rmxbean.getClassPath());
        System.out.println("Boot ClassPath = " + rmxbean.getBootClassPath());
        System.out.println("Java Library Path = " + rmxbean.getClassLibraryPath());
    }
}
```

## 18. 使用与上一个练习相同的对象，确定以下内容：程序运行的 JVM 实例名称（你可能在计算机上运行了多个 JVM）。

```java
import java.lang.management.ManagementFactory;
import java.lang.management.RuntimeMXBean;

public class PracticeJava {
    public static void main(String[] args) {
        RuntimeMXBean rmxbean = ManagementFactory.getRuntimeMXBean();
        System.out.println("instance name = " + rmxbean.getName());
    }
}
```

## 19. 使用与上一个练习相同的对象，以毫秒为单位打印 JVM 自身的运行时间。

```java
import java.lang.management.ManagementFactory;
import java.lang.management.RuntimeMXBean;

public class PracticeJava {
    public static void main(String[] args) {
        RuntimeMXBean rmxbean = ManagementFactory.getRuntimeMXBean();
        System.out.println("The JVM has been up for: " + rmxbean.getUptime() + " milliseconds.");
    }
}
```

## 20. 使用与上一个练习相同的对象，打印解析到 JVM 自身的命令行参数。



```java
import java.lang.management.ManagementFactory;
import java.lang.management.RuntimeMXBean;

public class PracticeJava {
    public static void main(String[] args) {
        RuntimeMXBean rmxbean = ManagementFactory.getRuntimeMXBean();
        System.out.println("The JVM arguments are: " + rmxbean.getInputArguments());
    }
}
```

### 21. 编写一个程序，使用静态方法 `ManagementFactory.getSystemMXBean()` 返回的操作系统 Bean 获取计算机内存的大小并打印出来。

```java
import java.lang.management.ManagementFactory;
import com.sun.management.OperatingSystemMXBean;

public class PracticeJava {
    public static void main(String[] args) {
        OperatingSystemMXBean osbean = ManagementFactory.getOperatingSystemMXBean();
        long memSize = osbean.getTotalPhysicalMemorySize();
        System.out.println("Computer memory = " + memSize + " bytes");
    }
}
```

### 22. 修改属性：使用 `System.setProperty` 方法更新 `country` 属性。为了确保已修改，请打印该属性。

```java
import java.util.*;
public class PracticeJava {
    public static void main(String[] args) {
        System.setProperty("country", "UK"); // 我们在此处使用英国
        System.out.println(System.getProperty("country"));
    }
}
```

# 练习你的 Java Level 1

| 任务 | 描述 |
| :--- | :--- |
| 23 | 创建一个新的系统属性：创建一个名为 `greeting` 的属性并为其赋值一个值。为了确保已创建，请打印该属性。<br>提示: `System.setProperty`<br><pre>public class PracticeJava {n  public static void main(String[] args) {n    System.setProperty("greeting", "Hello!!");\n    System.out.println(System.getProperty("greeting"));\n  }\n}</pre> |
| E1 | 编写一个程序，以天、小时、分钟为单位确定系统运行时间。 |
| E2 | 编写一个程序获取你运行的计算机的主机名。 |

# 练习你的 Java 级1

（出现在本章中）。

总结来说，我们可以说 `Paths` 类实际上只是 `Path` 类提供的一个辅助类，用于形成“路径”。

`Paths` 类仅包含用于执行任务的静态方法。

### 4. 使用 Paths 类和系统属性获取 Path 对象

编写一个程序，获取代表用户主目录的 `Path` 对象。将该 `Path` 对象打印到控制台。

提示：使用应用于属性 `user.home` 的 `Paths.get` 来获取所需的 `Path` 对象。

```java
import java.nio.file;
public class PracticeYourJava {
    public static void main(String[] args) {
        Path homeDir = Paths.get(System.getProperty("user.home"));
        System.out.println("the home directory is " + homeDir);
    }
}
```

### 5. 编写一个程序，获取代表用户桌面目录 `Path` 对象。将该 `Path` 对象打印到控制台。

提示：使用应用于属性 `user.home` 和字符串 "Desktop" 的 `Paths.get` 来获取所需的 `Path` 对象。此外，注意 `Paths` 接受可变参数。

```java
import java.nio.file;
public class PracticeYourJava {
    public static void main(String[] args) {
        Path desktop = Paths.get(System.getProperty("user.home"), "Desktop");
        System.out.println("the path of the Desktop is " + desktop);
    }
}
```

### 6. 将代表当前工作目录的属性设置为桌面。之后，打印当前工作目录的路径以确认其已修改。

提示：`System.setProperty user.dir`

```java
import java.nio.file;
public class PracticeYourJava {
    public static void main(String[] args) {
        Path desktop = Paths.get(System.getProperty("user.home"), "Desktop");
        System.setProperty("user.dir", desktop);
        System.out.println("JVM working directory is " + System.getProperty("user.dir"));
    }
}
```

### 7. 编写一个程序，判断桌面上是否存在名为 `Dir_A` 的目录，并告知用户你的发现。

提示：获取目标目录的 `Path` 对象。使用 `Files.exists` 方法检查其存在性。

```java
import java.nio.file;
public class PracticeYourJava {
    public static void main(String[] args) {
        String targetDir = "Dir_A";
        Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", targetDir);
        if (Files.exists(targetPath)) {
            System.out.printf("The directory %s exists on the desktop", targetDir);
        } else {
            System.out.printf("The directory %s does not exist on the desktop", targetDir);
        }
    }
}
```

### 8. 在确认以下目录不存在后，在桌面上创建每个目录：Dir_A, Dir_B, Dir_C, Dir_D 和 Dir_E。

提示：使用循环为每个目录创建一个 `Path` 对象（将目录名称放入 `String[]` 中），然后使用 `Files.createDirectories` 进行实际的创建。

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeJava {
    public static void main(String[] args) {
        String[] dirNames = new String[]("Dir_A", "Dir_B", "Dir_C", "Dir_D", "Dir_E");
        for (int i = 0; i < dirNames.length; i++) {
            Path targetDir = Paths.get(System.getProperty("user.home"), "Desktop", dirNames[i]);
            if (Files.exists(targetDir)) {
                System.out.printf("The directory %s already exists on the desktop\n", dirNames[i]);
            } else {
                try {
                    Files.createDirectory(targetDir);
                    System.out.printf("The directory %s has been created on the desktop\n", dirNames[i]);
                } catch (IOException e) {
                    System.out.println("Couldn't create directory " + dirNames[i]);
                }
            }
        }
    }
}
```

### 9. 编写一个程序，在创建的 `Dir_A` 内部创建子目录 `Dir_A_1`, `Dir_A_2`, `Dir_A_3`, `Dir_A_4` 和 `Dir_A_5`。

提示：此练习与上一个练习相似。

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeJava {
    public static void main(String[] args) {
        String base = "Dir_A";
        String[] dirNames = new String[]("Dir_A_1", "Dir_A_2", "Dir_A_3", "Dir_A_4", "Dir_A_5");
        for (int i = 0; i < dirNames.length; i++) {
            Path targetPath = Paths.get(System.getProperty("user.home"), base, dirNames[i]);
            if (Files.exists(targetPath)) {
                System.out.printf("The directory %s already exists\n", targetPath);
            } else {
                try {
                    Files.createDirectory(targetPath);
                    System.out.printf("The directory %s has been created\n", targetPath);
                } catch (IOException e) {
                    System.out.println("Couldn't create directory " + targetPath);
                }
            }
        }
    }
}
```

### 10. 一次性创建嵌套目录

在桌面上创建以下目录树：A/B/C/D/E/F/G/H/I/J/K/L/M/N/O/P/Q/R/S/T/U/V/W/Y/Z

提示：使用 `createDirectories`。同时确保将 "/" 替换为对应系统的路径分隔符（`File.separator`）。

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeJava {
    public static void main(String[] args) {
        String targetDir = "A/B/C/D/E/F/G/H/I/J/K/L/M/N/O/P/Q/R/S/T/U/V/W/Y/Z";
        // 路径分隔符在 file.separator 中
        targetDir = targetDir.replace("/", File.separator);
        // 现在创建 Path
        Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", targetDir);
        if (Files.exists(targetPath)) {
            System.out.println("The directory %s already exists on the desktop", targetDir);
        } else {
            try {
                Files.createDirectories(targetPath);
            } catch (IOException e) {
                System.out.println("Couldn't create directory " + targetPath);
            }
            System.out.println("The directory %s has been created on the desktop", targetDir);
        }
    }
}
```

### 11. 删除创建的空目录 `Dir_A_5`。

在异常处理器中，打印可能产生的 `IOException` 的堆栈跟踪。

提示：`Files.deleteIfExists`

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeJava {
    public static void main(String[] args) {
        String targetDir = "Dir_A_5";
        Path targetPath = Paths.get(System.getProperty("user.home"), "Dir_A", targetDir);

        try {
            boolean result = Files.deleteIfExists(targetPath);
            if (result == true) // 也可以写为 if(result)
                System.out.printf("The directory %s has been deleted.\n", targetPath);
            } else
                System.out.println("The directory %s was non-existent.\n", targetPath);
        } catch (IOException e) {
            System.out.println("Exception: could not delete the directory " + e.toString());
            e.printStackTrace();
        }
    }
}
```

### 12. 在之前创建的 `Dir_A_4` 中创建一个文本。修改之前的练习以删除 `Dir_A_4`。对程序的输出进行注释。

发生了 `DirectoryEmptyException` 异常并被其父异常 `IOException` 捕获。

如果我们需要，可以在每个 `catch` 块中关闭 `DirectoryStream`。

### 13. 什么是 `DirectoryStream` 接口？

`DirectoryStream` 接口用于读取目录所有内容的名称和信息的接口。使用 `Files.newDirectoryStream` 方法针对 `Path` 开启 `DirectoryStream`。生成的 `DirectoryStream` 可以通过迭代来分析返回的每个元素。

如果只需要目录内容的子集，也可以创建 `DirectoryFilter`（`DirectoryStreamFilter`）；例如，你可能只想列出扩展名为 `.txt` 的文件（指定为 `*.txt`），或者另一个例子是所有扩展名为 `.jpg` 且在文件扩展名前仅有三个字母的文件（指定为 `???.jpg`）。

注意：这里的 "Stream" 一词不要与 Java 8 的 Streams 概念混淆；将这里的 stream 理解为“像水流流出一样倾出目录中的项”。



## 第 29 章：文件系统

### 14. DirectoryStream 示例
下面的代码是一个 `DirectoryStream` 对象，用于获取并打印所有文件和目录的列表。

说明：代码从获取桌面目录的 `Path` 对象开始。然后，我们实例化一个 `DirectoryStream` 引用指向一个 `DirectoryStream` 对象。该对象通过 `Files.newDirectoryStream` 方法初始化并填充，该方法传递了目标目录的 `Path` 对象；在本例中，我们想要列出该目录的内容，因此只需循环并打印其内容即可。稍后我们将看到对 `newDirectoryStream` 方法产生的数据进行过滤的练习。

### 15. 练习：列出桌面内容并标识类型
编写一个程序，使用 `DirectoryStream` 完成以下操作：

- 获取桌面目录的内容
- 输出内容列表，并执行以下操作：
  - 在条目开头使用以下字符串 "F-" 或 "D-" 或 "S-" 指明该条目是文件、目录还是符号链接。
  - 如果条目是目录，程序应在条目末尾加上路径分隔符。

提示：应用以下方法获取上一个练习的输出：`Files.isRegularFile`、`Files.isSymbolicLink`。

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeYourJava {
    public static void main(String[] args) {
        Path indexPath = Paths.get(System.getProperty("user.home"), "Desktop");
        String pathSeparator = System.getProperty("path.separator");
        try {
            DirectoryStream<Path> stream = Files.newDirectoryStream(indexPath);
            for (Path item : stream) {
                if (Files.isRegularFile(item)) {
                    System.out.println("F-" + item);
                } else if (Files.isDirectory(item)) {
                    System.out.println("D-" + item + pathSeparator);
                } else if (Files.isSymbolicLink(item)) {
                    System.out.println("S-" + item + pathSeparator);
                } else {
                    System.out.println(item);
                }
            }
            stream.close(); // 确保你关闭了流
        } catch (IOException e) {
        }
    }
}
```

### 16. 练习：分类打印文件和目录
编写一个程序，使用 `DirectoryStream` 获取桌面目录的内容。程序应先打印文件，空一个空行，然后打印内容，并在每个目录列表的末尾加上路径分隔符。忽略符号链接。

提示：此练习的解是对上一个练习解答的修改。

```java
import java.nio.file.*;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;

public class PracticeJava {
    public static void main(String[] args) {
        Path pathDesktop = Paths.get(System.getProperty("user.home"), "Desktop");
        String pathSeparator = System.getProperty("path.separator");
        List<Path> dirList = new ArrayList<>();
        // 我们在第一个循环中遍历 DirectoryStream 对象
        // 并打印文件，但将 Path 对象放入 ArrayList 对象中
        // dirList; 我们在随后的循环中打印 dirList 的内容。
        try {
            DirectoryStream<Path> dirStream = Files.newDirectoryStream(pathDesktop);
            for (Path item : dirStream) {
                if (Files.isRegularFile(item)) {
                    System.out.println(item);
                } else if (Files.isDirectory(item)) {
                    dirList.add(item);
                }
            }
            System.out.println();
            for (Path item : dirList) {
                System.out.println(item + pathSeparator);
            }
            dirStream.close(); // 确保你关闭了流
        } catch (IOException e) {
        }
    }
}
```

### 17. 过滤 DirectoryStream 数据
“通配符”（Globbing）/模式匹配

给定过滤器，右侧的项目中哪些会被下面指定的每个过滤器捕获？

- 1. `a*.txt`
- 2. `a?.txt`
- 3. `a*`
- 4. `*.doc`
- 5. `A1*.doc`
- 6. `*(txt,doc)`

| | | | | |
| :--- | :--- | :--- | :--- | :--- |
| a) abc.txt | b) abc.doc | c) def.txt | d) abc | |
| e) abd.txt | f) abcd.txt | g) A12342e3.doc | h) A2c.doc | |
| i) abc.txt | j) country_list.doc | k) breed_list.doc | | |

提示：问号 (`?`) 匹配任何单个字符。`*` 匹配任何范围的字符。

**答案：**
- 1. a
- 2. c, f
- 3. a, b, d, e, f, i
- 4. g, h
- 5. h
- 6. a, b, c, e, f, g, h, i, j, k

### 18. 练习：列出 .txt 文件
编写一个程序，列出桌面上所有扩展名为“.txt”的文件。

提示：使用重载方法 `Files.newDirectoryStream` 来过滤数据。

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeJava {
    public static void main(String[] args) {
        Path pathDesktop = Paths.get(System.getProperty("user.home"), "Desktop");
        try {
            DirectoryStream<Path> dirStream = Files.newDirectoryStream(pathDesktop, "*.txt");
            for (Path item : dirStream) {
                System.out.println(item);
            }
            dirStream.close();
        } catch (IOException e) {
        }
    }
}
```

### 19. 练习：列出 .doc 文件
编写一个程序，列出桌面上所有扩展名为“doc”的文件。

提示：修改上一个练习中的 `Files.newDirectoryStream` 实例化。

### 20. 练习：列出系统中的所有目录
列出系统中的所有目录。

提示：使用 `Files.getDefault()` 配合 `Path`。

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeJava {
    public static void main(String[] args) {
        Path pathDesktop = Paths.get(System.getProperty("user.home"), "Desktop");
        try {
            DirectoryStream<Path> dirStream = Files.newDirectoryStream(pathDesktop, "*.txt");
            for (Path item : dirStream) {
                System.out.println(item);
            }
            dirStream.close();
        } catch (IOException e) {
        }
    }
}
```

### 21. 练习：打印分区空间信息
对于系统的每个分区，打印类型、总空间和可用空间。

提示：使用 `Files.getDefault()` 和 `getFileStores()`。

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeJava {
    public static void main(String[] args) {
        try {
            Path desktopPath = Paths.get(System.getProperty("user.home"));
            FileStore fs = Files.getFileStore(desktopPath);
            double totalSpaceMgs = (double) fs.getTotalSpace() / (1024 * 1024);
            System.out.printf("Total space = %.4f mgs\n", totalSpaceMgs);
            double availableSpaceMgs = (double) (fs.getTotalSpace() - fs.getUnallocatedSpace()) / (1024 * 1024);
            System.out.printf("Available space = %.4f mgs\n", availableSpaceMgs);
        } catch (IOException e) {
        }
    }
}
```

### 22. 练习：打印桌面所在驱动器空间
扩展练习 20 以打印桌面所在的驱动器空间。

提示：`directory path`。

---

## 文件信息

本部分的问题关于确定单个文件的信息。

在桌面上创建一个名为 `abc.txt` 的文件。为其输入任意数据。该文件将在接下来的练习中引用。

### 24. 文件大小
编写一个程序打印新创建的文件的大小。以字节和兆字节为单位。

在检查其大小之前确保文件存在。

提示：`Files.size`

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeYourJava {
    public static void main(String[] args) {
        long fileSize;
        float fileSizeMgs;
        String fileName = "abc.txt";
        Path targetfile = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        try {
            if (!Files.exists(targetfile)) {
                System.out.printf("文件 %s 不存在。正在退出...\n", targetfile);
                System.exit(0);
            }
            fileSize = Files.size(targetfile);
            fileSizeMgs = (float) fileSize / (1024 * 1024);
            System.out.printf("大小（字节）: %d\n", fileSize);
            System.out.printf("大小（兆字节）: %.2f mgs\n", fileSizeMgs);
        } catch (IOException e) {
        }
    }
}
```

### 25. 隐藏文件
编写一个程序来确定创建的文件是否为隐藏。

运行程序后，手动将创建文件的权限/属性修改为“隐藏”，然后重新运行程序以验证其结果。

提示：`isHidden`

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeJava {
    public static void main(String[] args) {
        String fileName = "abc.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        try {
            if (Files.notExists(targetFile)) {
                System.out.printf("The file %s does not exist. Exiting...\n", targetFile);
                System.exit(0);
            }
            if (Files.isHidden(targetFile)) {
                System.out.printf("The file %s is hidden\n", targetFile);
            } else {
                System.out.printf("The file %s is NOT hidden\n", targetFile);
            }
        } catch (IOException e) {
        }
    }
}
```

### 26. 只读文件
编写一个程序来确定创建的文件是否可写。

运行程序后，手动将创建文件的权限/属性修改为“只读”，然后重新运行程序以验证其结果。完成后不要让该文件保持在可写状态。

提示：`isWritable`



```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeJava {
    public static void main(String[] args) {
        String fileName = "abc.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        try {
            if(Files.notExists(targetFile)) {
                System.out.printf("The file %s does not exist. Exiting...\n", targetFile);
                System.exit(0);
            }
            if(Files.isWritable(targetFile)) {
                System.out.printf("The file %s is writable\n", targetFile);
            } else {
                System.out.printf("The file %s is NOT writable\n", targetFile);
            }
        } catch(IOException e) {
        }
    }
}
```

# Java 练习 Level 1

## 27. 文件可执行性

编写一个程序来确定文件 `abc.txt` 是否可执行。

> **注意**：要理解文件可执行性并不意味着该文件本身是一个程序。

> **进阶**：如果需要，在 UNIX 类系统上测试这一点时，使用 `chmod` 设置文件的执行位。

> 在运行 Windows 系统的计算机上，进入该文件的属性，然后前往提示：为了你的特定用户修改该文件的读取和执行权限。

提示：`Files.isExecutable`

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeYourJava {
    public static void main(String[] args) {
        String filename = "abc.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", filename);
        if(!Files.exists(targetFile)) {
            System.out.printf("The file %s does not exist. Exiting...\n", targetFile);
            System.exit(0);
        }
        if(Files.isExecutable(targetFile)) {
            System.out.printf("The file %s is executable\n", targetFile);
        } else {
            System.out.printf("The file %s is NOT executable\n", targetFile);
        }
    }
}
```

## 28. 文件可读性

在你的桌面上创建一个名为 `Test.txt` 的文件。在系统上，使用 `chmod` 将其设置为不可读。在 Windows 上，进入文件属性并将其权限设置为“拒绝”。

编写并测试一个程序来确定指定的文件是否可读。

将文件重新恢复为可读，然后重新运行程序。它应该产生相反的结果。

提示：`Files.isReadable`

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeYourJava {
    public static void main(String[] args) {
        String filename = "Test.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", filename);
        if(!Files.exists(targetFile)) {
            System.out.printf("The file %s does not exist.\n", targetFile);
            System.exit(0);
        }
        if(Files.isReadable(targetFile)) {
            System.out.printf("The file %s is readable.\n", targetFile);
        } else {
            System.out.printf("The file %s is NOT readable\n", targetFile);
        }
    }
}
```

## 29. 文件访问时间

打印较先创建的文件 `abc.txt` 被修改的时间。

提示：`Files.getLastModifiedTime`

```java
import java.nio.file.*;
import java.io.IOException;
import java.nio.file.attribute.FileTime;
public class PracticeYourJava {
    public static void main(String[] args) {
        String fileName = "abc.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        if(!Files.exists(targetFile)) {
            System.out.printf("The file %s does not exist. Exiting...\n", targetFile);
            System.exit(0);
        }
        try {
            FileTime ft = Files.getLastModifiedTime(targetFile);
            System.out.println("The time the file was modified: " + ft);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 30. 使用接口 `BasicFileAttributes`，确定并打印文件 `abc.txt` 的以下信息：

- 创建时间
- 最后访问时间
- 修改时间

提示：`Files.readAttributes`

```java
import java.nio.file.*;
import java.io.IOException;
import java.nio.file.attribute.BasicFileAttributes;

public class PracticeYourJava {
    public static void main(String[] args) {
        String fileName = "abc.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        if(!Files.exists(targetFile)) {
            System.out.printf("The file %s does not exist. Exiting...\n", targetFile);
            System.exit(0);
        }

        try {
            BasicFileAttributes bfa = Files.readAttributes(targetFile, BasicFileAttributes.class);
            System.out.println(bfa.creationTime());
            System.out.println(bfa.lastAccessTime());
            System.out.println(bfa.lastModifiedTime());
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 31. 打印文件 `abc.txt` 的所有者。

如果需要，修改所有者并返回程序。

提示：`Files.getOwner`

```java
import java.nio.file.*;
import java.io.IOException;
import java.nio.file.attribute.UserPrincipal;

public class PracticeYourJava {
    public static void main(String[] args) {
        String fileName = "abc.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        if(!Files.exists(targetFile)) {
            System.out.printf("The file %s does not exist. Exiting...\n", targetFile);
            System.exit(0);
        }

        try {
            UserPrincipal owner = Files.getOwner(targetFile);
            System.out.printf("The owner of the file is: " + owner);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 32. 打印文件 `.txt` 所在的卷名称。

提示：`Files.getFileStore`

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeYourJava {
    public static void main(String[] args) {
        String filename = "abc.txt";
        Path targetFile = Paths.get(System.getProperty("user.home"), "Desktop", filename);
        if(!Files.exists(targetFile)) {
            System.out.printf("The file %s does not exist. Exiting...\n", targetFile);
            System.exit(0);
        }
        try {
            FileStore fs = Files.getFileStore(targetFile);
            System.out.printf("The filestore of the file is: " + fs);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

# 文件操作

在本节中，展示了复制、删除、移动等文件操作。

提示：`Files.copy`

```java
// 现在进行复制
Files.copy(sourcePath, targetPath);
System.out.println("复制已完成。");
}
```

## 34. 重命名/移动文件

编写一个程序，将桌面上的文件 `abc.txt` 重命名为 `def.txt`。

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeYourJava {
    public static void main(String[] args) {
        String oldFileName = "abc.txt";
        String newFileName = "def.txt";

        Path sourcePath = Paths.get(System.getProperty("user.home"), "Desktop", oldFileName);
        Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", newFileName);

        if(Files.notExists(sourcePath)) {
            System.out.println("源文件不存在。正在退出...");
            System.exit(0);
        }

        if(Files.exists(targetPath)) {
            System.out.println("目标位置已存在同名文件。正在退出...");
            System.exit(0);
        }

        if(!Files.isWritable(targetPath)) {
            System.out.println("目标目录不可写。正在退出...");
        }

        // 现在执行移动
        try {
            Files.move(sourcePath, targetPath);
        } catch (IOException e) {
            System.out.println("错误：无法移动文件");
            e.printStackTrace();
        }
        System.out.println("移动/重命名已完成。");
    }
}
```

> **注意**：相同的代码也适用于移动或重命名文件。

## 35. 删除文件

编写一个程序，删除桌面上的 `def.txt` 文件。

提示：`Files.deleteIfExists`

```java
import java.nio.file.*;
import java.io.IOException;
public class PracticeYourJava {
    public static void main(String[] args) {
        String fileName = "def.txt";
        Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", fileName);
        boolean deletionResult=false;
        try {
            deletionResult = Files.deleteIfExists(targetPath);
        } catch (IOException e) {
            System.out.println("无法删除文件！");
            e.printStackTrace();
            System.exit(0);
        }

        if(deletionResult == false) {
            System.out.println("无法完成删除。");
        } else {
            System.out.println("文件已删除。");
        }
    }
}
```

> **注意**：如果文件不存在，使用 `Files.deleteIfExists` 方法的程序会提示你“无法完成删除”。

# 递归目录操作

## 36. 子文件夹遍历操作（遍历、删除）

描述你将如何遍历目录树并打印出其中每个文件和目录的。

执行所需任务的一种方法是使用具体类或作为匿名类的 `SimpleFileVisitor`，并将该类的实例传递给内置的目录路径遍历方法 `Files.walkFileTree`。



# `Files.walkFileTree` 设计用于递归遍历传入的路径

`Files.walkFileTree` 顾如上述接收一个 `SimpleFileVisitor` 实例并执行该类中的操作。`SimpleFileVisitor` 拥有以下你可以修改的方法：

- `postDirectory` - 此方法在 `Files.walkFileTree` 递归访问完当前目录的后代目录和文件后调用，然后执行该方法中指定的操作。
- `preDirectory` - 此方法在 `Files.walkFileTree` 递归访问当前目录的后代目录和文件之前调用，然后执行该方法中指定的操作。
- `visitFile` - 此方法由 `Files.walkFileTree` 为其访问的每个文件调用。
- `visitFileFailed` - 此方法在 `Files.walkFileTree` 无法“访问”某个文件时调用。

如果你想打印出想要的目录和文件的名称，可以将代码放入列出的相应方法中。如果你想删除想要的目录和文件，可以将代码放在这些方法中的其中一个的路径中。

## 37. 下面的程序尝试递归地统计给定目录中的文件总数和子目录总数。解释该程序如何实现这一目标。

```java
import java.nio.file.*;
import java.io.IOException;
import java.nio.file.attribute.BasicFileAttributes;

public class SimpleFileVisitor extends SimpleFileVisitor<Path> {
    public int fileCount = 0;
    public int directoryCount = 0;

    public FileVisitResult visitFile(Path pathItem
```

# 第 29 章：文件系统 I

```java
Files.walkFileTree(pathDir, (FileVisitor<Path>) sfv2);
System.out.println("文件计数 = " + sfv2.fileCount);
System.out.println("目录计数 = " + sfv2.directoryCount);
```

代码显示我们正在递归地遍历文件树，向方法 `Files.walkFileTree` 传递了 `Path` 对象和 `FileVisitor<Path>`。

`Path` 对象指向我们之前在桌面上创建的目录 "A"。

`FileVisitor<Path>` 指向我们创建的实例 `sv2`，它是我们创建的 `SimpleFileVisitor` 类的实例。

`SimpleFileVisitor` 类执行以下操作：

- 它拥有两个变量来存储文件和目录计数。
- 它修改了 `preDirectory` 方法来增加目录计数。
- 它修改了 `visitFile` 方法来增加文件计数。
- 在 `main` 方法中，它递归地遍历目录。
- 它通过 `Files.walkFileTree` 递归地遍历路径。

## 第 29 章：文件系统

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeYourJava {
    public static void main(String[] args) {
        String fileName = "rhyme.txt";
        String symLinkName = "lnk01";
        Path targetPath = Paths.get(System.getProperty("user.home"), fileName);
        Path symLinkPath = Paths.get(System.getProperty("user.home"), symLinkName);
        try {
            Files.createSymbolicLink(symLinkPath, targetPath);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

注意：对于新创建的符号链接，你可以使用任何应用程序来读取 `rhyme.txt`；你会发现 `rhyme.txt` 的内容会出现在你的应用程序中。

### 编写一个程序，检查上一个练习中创建的链接是否为符号链接。打印你的结果。

Windows：如果你无法通过程序创建链接，可以在具有管理员权限的命令行窗口中使用 `mklink` 命令来创建一个。提示：`Files.isSymbolicLink`

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeYourJava {
    public static void main(String[] args) {
        String symLinkName = "lnk01";
        Path targetPath = Paths.get(System.getProperty("user.home"), symLinkName);
        if (Files.isSymbolicLink(symLinkPath)) {
            System.out.printf("%s is a symbolic link\n", symLinkPath);
        } else {
            System.out.printf("%s is NOT a symbolic link\n", symLinkPath);
        }
    }
}
```

### 编写一个程序，打印上一个练习中符号链接的实际目标的名称。提示：`Files.readSymbolicLink`

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeYourJava {
    public static void main(String[] args) {
        String symLinkName = "lnk01";
        Path targetPath = Paths.get(System.getProperty("user.home"), symLinkName);
        if (!Files.isSymbolicLink(symLinkPath)) {
            System.out.printf("%s is not a symbolic link, so nothing to detect...Exiting\n", symLinkPath);
            System.exit(0);
        }
        Path actualTarget;
        try {
            actualTarget = Files.readSymbolicLink(symLinkPath);
            System.out.printf("%s is pointing to %s\n", symLinkPath, actualTarget);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 练习 Java Level 1

输出：程序将简单地输出目标相对于链接的路径。例如，如果链接和目标在同一个目录下，程序将仅输出目标的名称。

### 44. 硬符号链接（hard symbolic link）和软符号链接（soft symbolic link）之间的区别是什么？

另外，解释对引用文件的以下操作对软链接和硬链接的影响：1) 更新，2) 重命名和 3) 删除

此解决方案需要一些关于文件系统工作原理的背景知识。我们首先展示文件系统如何跟踪条目的简化视图，以回答该问题。

文件系统有一个“文件目录”（可以想象成电话目录），它以类似于下面的方式存储关于文件的以下信息元组：

(条目编号#, 条目名称, 条目类型, 磁盘上的实际文件位置, 目标)

在我们的示例中，文件条目类型将具有以下值：F(文件), D(目录), S(软符号链接), nH(硬符号链接)。

为了说明，该条目名称为问题目录的解析后名称。

我们文件目录中的一个文件 `abc.txt` 如下：

(#1, "C:/Users/PJ/Desktop/abc.txt", F, 1500001, "")

指向此文件的软符号链接 `hardLink01` 记录如下：

(#2, "softLink01", S, , "C:/Users/PJ/Desktop/abc.txt")

注意，软链接没有指示文件实际位置的条目。

指向此文件的硬符号链接记录如下：

(#3, hardLink01, H, 1500001, "")

注意，软链接没有指向被指向的文件（即软符号链接）的条目，但有一个指向磁盘实际位置的条目。此外，操作系统仍然意识到它指向磁盘上某个文件的物理位置。

#### 软链接和硬链接的文件访问机制

当通过软符号链接访问文件时，操作系统会查看软链接指向的名称、该项的实际条目，并从原始条目确定文件的实际磁盘位置并访问文件。

当通过硬符号链接访问文件时，操作系统会查看该链接本身直接指向的解析后名称，并以这种方式访问文件。

#### 更新文件对链接的影响

如果我们更新了文件，无论是通过硬链接还是软链接访问文件，访问机制都如上述所示保持不变。可以直接访问文件内容或通过[内容缺失]访问。

#### 重命名文件对链接的影响

现在，如果文件 `abc.txt` 被重命名为 `def.txt`，发生以下情况：

(#1, "C:/Users/PJ/Desktop/def.txt", F, 1500001, "")

注意重命名文件时的实际位置。此外，操作系统仍然意识到它指向磁盘上的物理位置。（注意：此处页面似乎有损坏）。

#### 删除文件对链接的影响

根据我们之前的解释，这意味着条目 #2 被删除，但并没有删除它指向的目标。这是符号链接和硬链接的原理说明。

# 第 29 章：文件系统 I

这导致条目 #2（软链接）变成“死链接”，文件无法通过软链接访问。

#### 硬链接的影响

有趣的是，文件内容可以通过硬链接访问，因为文件系统知道硬链接指向哪里。请记住，当 `abc.txt` 被删除时，只有条目被删除，并没有删除它指向的目标。

### 45. 创建一个指向 `rhyme.txt` 的硬符号链接2。提示：`java.nio.file.*;`

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeYourJava {
    public static void main(String[] args) {
        String filename = "rhyme.txt";
        String symlinkName = "link2";
        Path targetPath = Paths.get(System.getProperty("user.home"),
    }
}
```

### 46. 对链接所在的目录进行列表；观察并注释我们创建的软链接之间的差异。

可以清楚地看到代表链接的软链接条目。硬链接的条目看起来不像链接，而是目标文件的“副本”！

### 47. 带选项的文件操作

如果你在使用 `Files.copy` 时没有使用任何额外选项尝试覆盖已存在的文件，结果如何？

将产生 `java.nio.file.FileAlreadyExistsException` 异常。

无：如果你尝试复制覆盖已存在的文件，请求将被忽略。

### 48. 如何使用 `Files.copy` 方法覆盖已存在的文件？

提示：枚举 `StandardCopyOption.CopyOption`

你会将 `StandardCopyOption.REPLACE_EXISTING` 应用于 `Files.copy` 命令。而不是简单的，你会这样做：

```java
Files.copy(sourcePath, targetPath, StandardCopyOption.REPLACE_EXISTING);
```

### 49. `StandardCopyOption.COPY_ATTRIBUTES` 枚举的作用是什么？

该选项确保在底层操作系统允许的情况下，将原始属性复制到新文件中。这些属性包括但不限于时间戳（创建、修改、最后访问时间）和 POSIX 属性。

# Java 练习 Level 1

| 50. | 作为统一资源标识符 (URI) 的 Path 对象 |

| 什么是统一资源标识符 (URI) 的概念？ | URI 的概念是一个用于标识资源的字符字符串。URI 的示例是您允许解析的类似 `URI-like` 的字符串，该字符串可以直接将文件或目录引用到您计算机上的网络浏览器中，并且必须导入它所引用的文件或目录。URI 实际上是一种类型。<br>URI 的结构是一个名称后跟一个冒号；其余部分是资源的网络/计算机位置。例如形式为 `http://location` 的 URI。在这种情况下，URI 是 "http" |

# 临时目录和文件

有时练习需要临时目录和文件来对其处理。某些操作系统具有指定的区域用于存储这些条目。Java 提供了某些方法，可以在默认的临时目录中创建临时目录和文件。

# 第 29 章：文件系统 I

### 53. 在默认临时目录中创建一个名称前缀为 PYJ 的临时目录。打印生成的 Path。

此外，在此目录中创建一个名称前缀为 ABC、后缀为 FFF 的临时文件。

```java
import java.nio.file.*;
import java.io.IOException;

public class PracticeJava {
    public static void main(String[] args) {
        String dirPrefix = "PYJ";
        String filePrefix = "ABC";
        String fileSuffix = "FFF";
        try {
            Path dirPath = Files.createTemporaryDirectory(dirPrefix); // + dirPath;
            System.out.println("The path of the new dir = " + dirPath);
            // 现在在此内部创建临时文件。在上一个问题中
            // 我们直接在默认临时目录中创建文件
            Path filePath = Files.createTempFile(dirPath, filePrefix, fileSuffix);
            System.out.println("The name of the new temp file = " + filePath);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

# Zip 文件

### 54. 描述在 Java 中创建 zip 文件的程序结构。

广义来说，步骤是：(1) 创建一个归档 FileSystem 对象 (2) 使用 Map 对象指定您想要应用于此的操作，或者创建 zip 文件、解压或 (3) 创建或插入文件/从 zip 归档。我们在下面解释这些步骤。

第一步是创建一个新的 FileSystem 对象，使用 `FileSystems.newFileSystem()` 方法的重载版本之一。我们查看的两个潜在版本具有以下方法定义：

```java
newFileSystem(Path, Map, null);
and
newFileSystem(URI, Map);
```

方法中变量类型的描述如下：

**Path**: Path 的最后一个元素必须是目标 zip 文件的文件名，并且必须以 .zip 结尾。此要求方法能够确定它正在创建什么种的 FileSystem 对象；它将通过文件扩展名成功判断出目的是创建一个 zip 文件。

**Map**: 这是一个 `Map<String, String>`，包含特定的值，供文件系统用于确定我们想要执行的操作；要创建一个 zip 文件，必须在 Map 对象中插入 String, String 元组 ("create", "true")。当我们从 zip 文件中提取时，为了确保我们是“create”，则设为 "false"。

使用提供的值，我们可以使用上面所示的第一方法创建我们的 FileSystem 变量。

为了使用第二种方法，必须先将目标 zip 文件的位置转换为 URI 对象，对于 zip 文件如下所示：

使用 `<Path>.toUri()` 将目标 zip 文件的目标 Path 转换为 URI。



之后，程序必须使用 `<URI>.toPath()` 将此 URI 转回路径。

zip 文件的完整 URI 确定为前缀 `"jar:file:"`，创建的 URI 追加在其后。

以上所有内容都可以写成：

```java
URI uri_instance = URI.create("jar:file:" + targetPath.toUri().getPath());
```

其中 `targetPath` 是包含目标 zip 文件路径的 `Path` 对象。

上述描述的 `Map<String, String>` 应该用于接受 URI 的方法变体。

通过此，我们可以使用第二个重载方法创建一个 `FileSystem` 对象。

# 练习你的 Java Level 1

## 插入 zip 文件

在获取 `FileSystem` 对象后，可以使用下面的 `Files.copy` 方法轻松地完成向 zip 文件的插入：

- 第一个参数是我们要放入归档的文件的 `Path` 对象
- 第二个参数是代表我们要插入的对象在 zip 文件中位置的 `Path` 对象
- 第三个参数是我们想要使用的 `StandardCopyOption`；例如，我们可能接受或不接受覆盖归档中可能存在的同名文件。

### 55. 创建 zip 文件并向其插入

手动识别一个您想要放入 zip 文件的任意文件（我们在这里选择桌面上的 `abc.txt` 文件）。在桌面上创建一个名为 `zip1.zip` 的 zip 文件。将之前识别的文件插入其中。如果归档中相同位置已存在任何文件，则替换它。

```java
import java.nio.File;
import java.io.IOException;
import java.net.URI;
import java.nio.file.*;
import java.util.Map;

public class PracticeYour {
    public static void main(String[] args) {
        String dirPrefix = "PYJ";
        String filePrefix = "ABC";
        String fileSuffix = "FFF";
        try {
            Path dirPath = Files.createTemporaryDirectory(dirPrefix);
            System.out.println("The path of the new dir = " + dirPath);
            Path filePath = Files.createTempFile(dirPath, filePrefix, fileSuffix);
            System.out.println("The name of the new temp file = " + filePath);
        } catch (IOException e) {
            e.printStackTrace();
        }
        
        // 任务 55 的逻辑
        Path desktop = Paths.get(System.getProperty("user.home"), "Desktop");
        Path sourceFile = desktop.resolve("abc.txt");
        Path zipFile = desktop.resolve("zip1.zip");
        // 实现将涉及 FileSystems.newFileSystem 和 Files.copy
        try {
            // Files.copy(sourceFile, ..., StandardCopyOption.REPLACE_EXISTING);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 从 zip 文件中提取

之前插入到 zip 文件中的文件。

```java
import java.nio.File;
import java.io.IOException;
import java.net.URI;
import java.nio.file.*;
import java.util.Map;

public class PracticeYour {
    public static void main(String[] args) {
        // 任务 56 的逻辑
    }
}
```

### 57. 给定以下路径：

Windows: `C:\Users\PYJ\PracticeDir\file1.txt`

Unix: `/home/pyj/PracticeDir/file1.txt`

提取结束元素并打印它。

```java
import java.nio.file.*;
public class PracticeYour {
    public static void main(String[] args) {
        Path pathTarget = Paths.get("C:\\Users\\PYJ\\PracticeDir\\file1.txt");
        Path endElement = pathTarget.getFileName();
        System.out.println("the end element is " + endElement);
    }
}
```

> 注意：无论结束元素是文件还是目录，`getFileName` 都能提取它。

### 58. 针对上一个练习中的路径，获取路径的根元素。

提示：`Path.getRoot()`

```java
import java.nio.file.*;
public class PracticeYour {
    public static void main(String[] args) {
        Path pathTarget = Paths.get("C:\\Users\\PYJ\\PracticeDir\\file1.txt");
        Path rootElement = pathTarget.getRoot();
        System.out.println("the root element is " + rootElement);
    }
}
```

### 59. 针对上一个练习中的路径，编写一个程序打印路径中有多少元素。

提示：`Path.getNameCount()`

```java
import java.nio.file.*;
public class PracticeYour {
    public static void main(String[] args) {
        Path pathTarget = Paths.get("C:\\Users\\PYJ\\PracticeDir\\file1.txt");
        int numberOfElements = pathTarget.getNameCount();
        System.out.println("the number of elements in the path is " + numberOfElements);
    }
}
```

### 60. 针对上一个练习中的相同路径，编写一个程序确定结束元素的父目录。

提示：`Path.getParent`

```java
import java.nio.file.*;
public class PracticeYour {
    public static void main(String[] args) {
        Path pathTarget = Paths.get("C:\\Users\\PYJ\\PracticeDir\\file1.txt");
        Path parentDir = pathTarget.getParent();
        System.out.println("the parent directory is " + parentDir);
    }
}
```

# 练习 Java 1 级

```java
public static void main(String[] args) {
    Path targetPath = Paths.get("C:\\Users\\PYJ\\PracticeDir\\testfile01.txt");
    Path parentPath = targetPath.getParent();
    System.out.println("The parent's path is : " + parentPath);
}
```

### 61. 编写一个程序，移除以下路径中的冗余元素。打印结果路径。

Windows: `C:\Users\PYJ\\PracticeDir\..\PracticeDir\testfile01.txt`

NIX: `/home/PYJ/PracticeDir/../PracticeDir/testfile01.txt`

提示：`Path.normalize();`

```java
import java.nio.file.*;
public class PracticeYourJava {
    public static void main(String[] args) {
        Path targetPath = Paths.get("C:\\Users\\PYJ\\PracticeDir\\..\PracticeDir\\testfile01.txt");
        Path normalizedPath = targetPath.normalize();
        System.out.println("The normalized path is : " + normalizedPath);
    }
}
```

| E1 | 编写一个程序，将整个文件夹/目录放入 zip 文件 |
|----|----------------------------------------------|
| E2 | 编写一个程序，将 zip 文件的所有组件提取到指定的目录中 |
| E3 | 编写一个程序，递归遍历目录并列出所有扩展名为 `*.txt` 或 `*.doc` 的文件 |
| E4 | 重写练习 39 题的解决方案（递归删除目录），这次要确保了对文件和目录的访问性和可删除性进行检查 |
| E5 | 调查 `Files.probeContentType` 方法的作用和功能 |
| E6 | 如果你使用的是基于 UNIX 的系统，编写一个程序来设置文件的组权限和其他权限（提示：参见 `PosixFilePermissions` 类） |

# 第 30 章. 文件系统 II：文件输入与输出

在上一个章节中，我们查看了文件处理，但没有处理文件的内容。本章介绍了处理文件读取和写入的练习题。本章展示了使用 NIO/NIO2 读取/写文件的两种不同方法。本章中用的主要类包括 `Files`、`Path`、`Paths`、`BufferedReader` 和 `BufferedWriter`。

## 使用 File.readAllLines 读取文本文件的内容

在桌面上手动创建一个文件 `abc.txt`。使用你选择的文本编辑器，将其放入任何你喜欢的文本中。

现在，使用 `Files.readAllLines` 方法读取文件内容并将内容输出到控制台。

```java
import java.io.IOException;
import java.nio.file.*;
import java.util.List;

public class FileHandling {
    public static void main(String[] args) {
        String filename = "abc.txt";
        Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", filename);
        List<String> fileContents = null;
        if(Files.isReadable(targetPath)) {
            try {
                fileContents = Files.readAllLines(targetPath);
            } catch (IOException e) {
                e.printStackTrace();
            }
            for (String s:fileContents) {
                System.out.println(s);
            }
        } else {
            System.out.println("The file is not readable \n");
        }
    }
}
```

## 使用 Files.write 写入文本文件

将韵律“Mary had a little lamb"的前几行写入命名为 `rhyme.txt` 的文件（将此文件放在桌面上）。运行程序后查看文件内容，以确认文件已写入。

```java
import java.io.IOException;
import java.nio.file.*;
import java.util.ArrayList;
import java.util.List;

public class FileHandling {
    public static void main(String[] args) {
        List<String> rhyme = new ArrayList<>();
        rhyme.add("Mary had a little lamb");
        rhyme.add("little lamb, little lamb");
        rhyme.add("Mary had a little lamb that was as white as snow");
        String filename = "rhyme.txt";
        Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", filename);
        try{
            Files.write(targetPath, rhyme);
            System.out.println("The data has been written to the file");
        } catch(IOException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

# 练习 Java 1 级

### 3. 如果你删除了上一个练习中将韵律前两行写入 listString 的代码，只留下单行 `rhyme.add("Mary had a little lamb that was as white as snow")`，然后运行修改后的程序，文件 rhyme.txt 的内容将会是什么？

**发现：** 现在文件的内容只有第三行，“Mary had a little lamb that was as white as snow”，内容被覆盖了，而不是追加的！这是因为 `Files.write(Path, List<T>)` 方法的默认操作是覆盖文件中的数据。我们稍后会看到如何需要将数据追加到文件中。

# 缓冲文件 (Buffered Files)

## 4. 解释文件缓冲读取和写入的概念。

### 缓冲读取的概念

我们通过示例来解释。假设我们有一个想要读取的文件，其内容是字符串“Sun rises in the east”，我们打算按字符读取并处理数据。伪代码中的处理过程类似于以下：

```
while(there is character to read)
    read_character_from_file(); // 我们正在按字符读取
    process_character();
```

查看上面的伪代码，我们发现这个序列相对较慢！这种低速访问的解决方案是：当请求从文件中读取数据时，应该将相当数量的文件读取到内存空间中，而不是按字符读取。当每次请求一个字符时，`read_character_from_file()` 方法将从内存空间中获取下一个字符。读取文件的区域称为缓冲区（buffer）。现在我们的 `read_character_from_file()` 方法看起来像这样：

```
read_character_from_file()
    are desired file contents already in buffer?
    no 则 则从 the desired character 开始将文件的合理部分读取到缓冲区中
    return character from buffer
```

这就是缓冲读取的概念。作为一般规则，操作系统会将磁盘一次性读取到内存中。

### 缓冲写入的概念

缓冲写入的概念与读取类似。在程序说应该写入的精确时刻写入每个数据项并不是最优的；相反，当收集了足够数量的数据进行写入时，我们才将数据写入磁盘。一种适当的策略是等待足够数量的乘客后再前往目的地；一个一个地将每个乘客移动到目的地是不高效的。在坐满之前公交不会移动。当我们无法使用之前显示的方法一次性地从/向读取/写入整个文件时，缓冲读取和写入是合适的。

## 5. 读取缓冲文件

详细解释下面代码片段中带编号的代码部分的目标、功能和原理。



```java
#1 String filename = "rhyme.txt";
Path indexPath = Paths.get(System.getProperty("user.home"), "Desktop", filename);
#2 String nextLine;
BufferedReader nbr = Files.newBufferedReader(source);
while((nextLine = nbr.readLine()) != null){
    System.out.println(nextLine);
}
#4 nbr.close();
```

#1. 标记为 #1 的代码仅仅是在 `String` 变量中添加了一个名为 `source` 的 `Path` 对象，用于指向桌面上的一个文件。

#2. 静态方法 `Files.newBufferedReader(Path)` 返回一个与传递的 `Path` 关联的 `BufferedReader` 对象。

#3. 在此代码中读取 `BufferedReader` 对象的内容。在代码的这部分，我们使用 `while` 循环通过 `readLine` 方法成功地从 `BufferedReader` 读取另一行。我们将读取的每行都打印到控制台。当没有其他内容可读时，`readLine` 的返回值为 `null`。需要注意的是 `BufferedReader` 类属于 `java.io` 包，该包属于旧的 Java 文件机制，但它对于 NIO 操作仍然有效。

#4 这一行调用了释放与 `BufferedReader` 对象相关的所有资源。完成使用后必须关闭缓冲对象。

总结来说，使用 `BufferedWriter` 写入文件只需要做几件事。这些：(1) 获取源文件位置的 `Path` 对象，(2) 获取对应 `Path` 的 `BufferedReader` 对象，(3) 从 `BufferedReader` 对象读取数据以及 (4) 关闭 `BufferedReader` 对象。

（注释：关于 #2）`Files.newBufferedReader(Path)` 方法实际上是 Java 旧文件机制 `java.io.BufferedReader` 方法的 NIO 包装器。`newBufferedReader` 接收一个 `Path` 对象。由于这是一个简单的包装器，该行可以如下所示风格编写：

```java
BufferedReader nbr = new BufferedReader(FileReader(sourcePath.toString()));
```

使用与 #2 行相同的代码在在使用 NIO 包时更为合适。

## 6. 增强上一个练习的代码使其具有完整功能。将其放入 `FileHandling` 类中。

通过在桌面上手动创建一个名为 `rhyme.txt` 的文件（并在放入你喜欢的韵律），然后使用你的程序读取文件并将其内容打印到控制台来测试代码。

```java
import java.io.*;
import java.io.IOException;
import java.nio.file.*;

public class FileHandling {
    public static void main(String[] args) {
        String FileToFile = "rhyme.txt";
        Path sourcePath = Paths.get(System.getProperty("user.home"), "Desktop", FileToFile);
        String nextLine;
        try {
            BufferedReader nbr = Files.newBufferedReader(sourcePath);
            while ((nextLine = nbr.readLine()) != null) {
                System.out.println(nextLine);
            }
            nbr.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## Java 级级练习

```java
}
nbr.close();
}
catch (IOException e) {
  System.out.println("IOException = " + e);
}
}
```

## 7. 写入缓冲文件 (Buffered Files)

详细解释下方代码片段中编号代码部分的get、功能和原理。

```java
#1 String targetFile = "out.txt";
Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", targetFile);
#2 BufferedWriter bw = Files.newBufferedWriter(targetPath);
#3 nbw.write("the sun rises in the East");
#4 nbw.write(System.getProperty("line.separator"));
#5 nbw.write("the sun settles in the West");
#6 bw.close();
```

- #1. 这只是简单地为 `String` 变量 `targetFile` 指定的桌面上的文件获取一个 `Path` 对象 `targetPath`。

- #2. 静态方法 `Files.newBufferedWriter(Path)` 返回一个 `BufferedWriter` 对象，该对象与传递的 `Path` 对象关联。

- #3 我们正在使用 `BufferedWriter` 类的 `write` 方法向文件写入一行。行分隔符不是必须的 `"\n"`，但使用 `line.separator` 属性是安全的。

- #4 我们正在使用 `BufferedWriter` 类的 `write` 方法向目标写入另一个 `String`。

- #5 这关闭并释放与 `BufferedWriter` 关联的所有资源。在完成对 `BufferedWriter` 对象的操作后应使用它。

总结来说，我们有一份使用 `BufferedWriter` 向文件写入数据的简短操作列表。这些操作是：(1) 获取目标文件的 `Path` 对象，(2) 针对该 `Path` 获取 `BufferedWriter`，(3) 将数据写入 `BufferedWriter` 对象以及 (4) 关闭 `BufferedWriter` 对象。

注意：(Rc #2 方法 `Files.newBufferedWriter(Path)` 实际上是针对预-NIO 文件处理机制中 `BufferedWriter` 类对应方法的 NIO 包装方法。`NewBufferedWriter` 接收一个 `Path`。由于它是一个更简单的包装方法，可以用旧样式写为：

```java
BufferedWriter bw = new BufferedWriter(new FileWriter(target.toString()));
```

然而，当使用 NIO 包时，编写如 #2 所示的代码含义更为合适。

## 8. 增强练习以使其功能完备。将其放入名为 `FileHandling` 的类中。

```java
import java.io.BufferedWriter;
import java.io.IOException;
import java.nio.file.*;
```

```java
public class FileHandling {
  public static void main(String[] args) {
    String fileToFile = "out.txt";
    Path targetPath = Paths.get(System.getProperty("user.home"), "Desktop", fileToFile);
    try{
      BufferedWriter bw = Files.newBufferedWriter(targetPath);
      bw.write("the sun rises in the East");
      bw.write(System.getProperty("line.separator"));
      bw.write("the sun settles in the West");
      bw.close();
    } catch (IOException e) {
      e.printStackTrace();
    }
  }
}
```

## 9. 如果在运行上一个练习的程序后立即运行下面的程序，文件 `out.txt` 的结果是什么？

（仅显示了 `main` 方法中新的 `try` 块；程序的其他部分与上一个练习相同）；

```java
try{
  BufferedWriter nbw = Files.newBufferedWriter(targetPath);
  nbw.write("what happens from the North?");
  nbw.close();
}
```

文件的内容现在是：

What happens from the North then?

发生了什么，导致文件的内容实际上被新程序覆盖了。

## 10. 追加到文件 (Appending)

重新运行练习 8 以重置文件内容。现在如下所示修改练习 9 中的程序，并注释文件 `out.txt` 内容。

（仅显示了 `main` 方法中新的 `try` 块；程序的其他部分与上一个练习相同）；

```java
try{
  BufferedWriter nbw = Files.newBufferedWriter(targetPath);
  nbw.write(System.getProperty("line.separator"));
  nbw.append("what happens from the North then?"); //我们现在正在使用 append 方法
  nbw.close();
}
```

文件的内容是：

The rises in the East

The sun sets in the West

What happens from the North then?

如所示，与练习 9 相比，最后一行 "What happens from the north then?” 被追加到了文件的现有内容。本练习的目的是使用 `append` 方法写入文件。

## 11. 当为文件实例化缓冲区时同时使用 `StandardOpenOption` 的不同值决定了如何写入或从文件中读取。请解释以下每个 `StandardOpenOption` 的含义：(1) APPEND, (2) CREATE, (3) CREATE_NEW, (4) READ, (5) DYNC, (6) SYNC, (7) TRUNCATE_EXISTING 和 (8) WRITE。

- **APPEND** – 这意味着任何要写入文件的数据应该添加到文件的末尾。回想练习 9，如果我们没有用此选项打开文件缓冲区，那么文件中的数据将不会被覆盖，而是被追加。
- **CREATE** – 此选项说明如果预期的文件不存在，则创建它。如果文件已存在，则是没问题的。
- **CREATE_NEW** – 此选项说明如果预期的文件不存在，则创建它。如果文件已存在，则会报错。
- **READ** – 这表示我们需要从文件中读取。
- **DSYNC** – 此模式在写入文件时要求更改立即写入磁盘，而不是缓冲。
- **SYNC** – 此模式除了缓冲之外，这会导致性能较慢。
- **TRUNCATE_EXISTING** – 用于我们打算写入的文件，这会清除现有内容。
- **WRITE** – 这表示我们打开文件进行写入访问。

## 12. 写入时的文件权限

重做练习 9，这次使用 `APPEND` 选项打开文件。在运行你的代码之前，先运行 8 重置文件内容。

注意：此练习的目的是证明当打开 `BufferedWriter` 并使用 `write` 方法时，数据将追加到文件末尾，而不是

```java
import java.io.BufferedWriter;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;
public class FileHandling {
    public static void main(String[] args) {
        String fileWrite = "out.txt";
        Path targetPath = Paths.get(System.getProperty("user.home")
```

## 13. 解释以下两行代码之间的功能差异：

`BufferedWriter nbw = Files.newBufferedWriter(targetPath, StandardOpenOption.APPEND);`

和

`BufferedWriter nbw = Files.newBufferedWriter(targetPath, StandardOpenOption.WRITE, StandardOpenOption.APPEND);`

没有差异。原因是 `BufferedWriter` 是为了写入而打开的，因此明确说明使用 `WRITE` 选项对代码没有影响。

## 14. 如果使用 `StandardOpenOption.APPEND` 初始化 `BufferedWriter` 对于一个不存在的文件，结果如何？

将抛出 `java.nio.file.NoSuchFileException`异常。

## 15. 如果使用 `StandardOpenOption.CREATE` 初始化 `BufferedWriter` 对于一个已存在的文件，结果如何？

文件将被覆盖。

## 16. 如果使用 `StandardOpenOption.CREATE_NEW` 初始化 `BufferedWriter` 对于一个已存在的文件，结果如何？

将抛出 `java.nio.file.FileAlreadyExistsException`异常。

## 17. 以字节写入/读取数据

`Files.write(Path, String[])/Files.readLines` 与 `Files.write(Path, byte[])/Files.readAllBytes` 这对方法之间有什么区别？

## 第 30 章：文件系统

`Files.write(Path,String[])/Files.readAllBytes` 这对方法用于逐行从写入/读取文本/人类可读的字符串，而 `Files.write(Path,byte[])/Files.readAllBytes` 方法用于作为简单的字节流写入/读取数据。练习 1 是 `readAllBytes Files.write(Path,byte[])/readAllBytes` 方法用于非文本数据的示例，例如 jpeg 文件、mpeg 文件、png 文件、mp3 文件等（这些显然不是文本数据），它们是由理解如何解释的相应程序解释的字节数据。如果你编写一个播放 mp3 文件的程序，你将使用 `Files.readAllBytes` 方法将 mp3 文件读取到 `byte[]` 中。

注意：所有数据都以字节形式存储，但 `Files.readAllLines` 已经对读取的数据应用了解释层，将其转换为人类可读的格式；其派生方法 `Files.write(Path,String[])` 应用了该解释层的反向操作，将文本/人类可读的数据转换为字节。将文本数据转换为字节的常用方案/格式包括 ASCII 和 UTF-16。

另一种方法

如前所述，所有数据都以字节形式存储，因此你实际上可以使用 `Files.readAllBytes` 读取一个通过 `Files.write(Path,String[])` 方法写入的文本文件；你只需要自己解释这些字节即可。

- 18. 我们知道 NIO 方法对 `Files.newBufferedWriter/Files.newBufferedReader` 用于在缓冲区中写入/读取文本数据。以缓冲方式写入/读取 `byte[]` 数据的对应方法是什么？

在 Java 中有两种向文件写入/读取字节的方法的方法。这些：

- 1. 使用 NIO 中的 `ByteBuffer` 和 `newByteChannel` 功能。
- 2. 使用 `java.io` 包中的 `BufferedInputStream/BufferedOutputStream`。

注意：在本书中，不再对 NIO 的 `ByteBuffer` 功能进行进一步研究。

- E1 使用 `BufferedReader` 和 `BufferedWriter` 将一个选的文件复制到另一个文件。
- E2 编写一个程序，在你选择的目录中创建 50 个空文件，命名方案为 JPG0058。
- E3 我从相机下载了一些照片到桌面上的指定目录。相机将文件命名为 JPG0001...JPG0058。我删除了其中一个文件，导致我的编号方案出现了一个空隙。编写一个程序，将我删除文件之后的文件名移动一位，以便我的编号方案中不再有空隙（这样我们现在将拥有名为 JPG0001 到 JPG0049 的文件）。

## 第 31 章：枚举 II

本章名为“枚举 II”，是上一章“枚举 I”的延续。在“枚举 I”中，介绍了确保理解 Java 枚举基本功能的的练习。本章通过介绍与 Java 枚举扩展功能相关的练习扩展了上一章的内容。



# Java 枚举与 Swing GUI 练习

## 枚举进阶练习

### 1. 解释下面所示代码的含义及其影响

```java
public enum Gender {
    MALE(10), FEMALE(20);
    private final int value;
    public int getValue(){
        return value;
    }
    private Gender(int value){
        this.value = value;
    }
}
```

在第一章中已经提到，枚举类是一种特殊的类，它拥有所有可以从类定义内部进行实例化的对象。还提到对象被认为有一个序数（`ordinal`），该序数直接源于它们在相关枚举类中的声明顺序。

由于我们提到过枚举是特定类的对象，就像任何类一样，枚举可以有构造函数。再次，因为枚举是对象，它们可以向其构造函数传递初始化参数。在这个示例中，我们看到两个枚举 `MALE` 和 `FEMALE`，呈现了我们想要传递给它们构造函数的值；对于枚举 `Gender.MALE`，我们希望它将值 10 传递给其构造函数，对于枚举 `Gender.FEMALE`，我们希望它将值 20 传递给其构造函数。

现在，就像每个类一样，初始化参数可以根据我们的意愿选择；在这种情况下，我们恰好将它们存储在类中的变量中。创建了一个名为 `getValue` 的方法用以访问该变量。

再次，将枚举看作一种特殊的类，其对象和构造函数参数是在类定义时内部指定的。你实际上可以将枚举学习为单例模式的一种变体吗？

如果我们想使用任何枚举初始化参数来表示枚举对象的相对顺序，我们就必须重写 `compareTo` 方法，或者使用我们自己创建的方法进行顺序比较。在这个示例中，我们使用创建的 `getValue` 方法来执行顺序比较，枚举的自然序数对我们无关，我们可以按照任意的顺序在类定义中插入对象。

再次，枚举是一个包含所有对象的类，它们的构造函数初始化参数被硬编码在其中。

> **注意**：如果这有点困惑，在创建枚举类时，可以先像定义任何其他类一样创建类体，然后向类添加枚举对象。

### 2. 修改 `Gender` 枚举，使用字符串 "man" 用于 `MALE` 条目，使用 "woman" 用于 `FEMALE` 条目

```java
enum Gender {
    MALE("man"), FEMALE("woman");
    private final String value;
    public String getValue() {
        return value;
    }
    private Gender(String value) {
        this.value = value;
    }
}
```

> **注意**：此练习的目标是让枚举与普通类非常相似。

### 3. 创建枚举 `Continents` 存储大陆面积和名称

大陆及其面积如下（以指数形式表示）：欧洲（1.018e10）、北美（2.449e10）、Antarctica（3.037e10）、非洲（4.382e10）、澳洲（9.0085e10）、南美（1.784e10）。创建一个枚举 `Continents`，分别在字段 `area` 和 `name` 中存储大陆的面积和名称，并提供 `getArea` 和 `getName` 方法调用时返回面积和名称。

> **提示**：像任何对象一样，枚举可以有多个构造初始化值，并拥有多个字段；再次，枚举是一个其构造参数在其边界内的类。

```java
public enum Continents {
    EUROPE(2.449e8, "North America"),
    AFRICA(3.037e8, "Africa"),
    AUSTRALIA(9.0085e7, "Australia"),
    SOUTH_AMERICA(1.784e8, "South America"),
    ANTARCTICA(1.372e8, "Antarctica");

    private final double area;
    private final String name;

    public double getArea() {
        return area;
    }
    
    private Continents(double area, String name) {
        this.area = area;
        this.name = name;
    }
    
    public String getName() {
        return name;
    }
}
```

### 4. 重写 `Continents` 枚举类的 `toString` 方法

让 `toString` 方法输出内容：`<name>, size = <size>`。

在枚举中添加：

```java
public String toString() {
    return this.name + ", size = " + this.area;
}
```

### 5. 判断正误

- **错误**：枚举不能有子类。
- **正确**：枚举可以实现接口。

### 6. `SalaryBand` 枚举实现

薪资带区间定义：
`BAND1 = 30000 - 37000, BAND2 = 33000 - 45000, BAND3 = 43000 - 55000, BAND4 = 50000 - 60000,`
`BAND5 = 57000 - 70000, BAND6 = 67000 - 80000, BAND7 = 77000 - 90000, BAND8 = 88000 - 100000,`
`BAND9 = 98000 - 120000, BAND10 = 120000 - 150000`。

需要创建以下方法：
1. `getBand`：返回工资金额所属的带宽区间；如果工资金额出现在两个区间内，则该方法应返回较低的区间。
2. `getUpperLimit`：返回传入的带区间的上限。
3. `getLowerLimit`：返回传入的带区间的下限。

```java
import java.math.BigDecimal;

enum SalaryBand {
    BAND1(30000, 37000), BAND2(33000, 45000), BAND3(43000, 55000), BAND4(50000, 60000),
    BAND5(57000, 70000), BAND6(67000, 80000), BAND7(77000, 90000), BAND8(88000, 100000),
    BAND9(98000, 120000), BAND10(120000, 150000);

    private BigDecimal lowerLimit;
    private BigDecimal upperLimit;

    public BigDecimal getLowerLimit() { return lowerLimit; }
    public BigDecimal getUpperLimit() { return upperLimit; }

    static SalaryBand getBand(BigDecimal valueToCheck) {
        // 获取对象列表并检查金额是否在它们的带范围内
        for (SalaryBand x : SalaryBand.values()) {
            BigDecimal lower = x.getLowerLimit();
            BigDecimal upper = x.getUpperLimit();
            if (valueToCheck.compareTo(lower) >= 0 && valueToCheck.compareTo(upper) <= 0) {
                return x; // 隐式退出方法
            }
        }
        // 否则我们没有该数字。返回 null。
        return null;
    }

    private SalaryBand(int lower, int upper) {
        lowerLimit = new BigDecimal(lower);
        upperLimit = new BigDecimal(upper);
    }
}
```

---

## 第 32 章：使用 Swing 构建图形用户界面

本章介绍了使用 Swing 库实现图形用户界面的练习。

Java 图形是一个非常广泛的主题，相关的练习可以很容易填满多卷书。你很可能会使用 GUI 构建器作为图形应用前端，从而避开 GUI 布局中的某些问题（例如布局管理器的细节）。尽管如此，了解 GUI 构建器是什么是有益的。本章提供了一组精心挑选的练习，以巩固你对 Java Swing GUI 应用结构、GUI 组件和事件监听器的理解。

### 1. 用通俗术语描述以下每个 Java 包及其它们的关系：AWT、Swing 和 JavaFX

- **抽象窗口工具包（Abstract Windowing Toolkit，缩写 AWT）**：Java 原始的图形包。它将许多图形绘制工作委托给底层操作系统，因此 AWT 应用程序具有其运行系统的视觉外观和感受。
- **Swing**：构建在 AWT 之上，开发在 Java 的后续版本（1.2 版本）中。它呈现了比 AWT 更先进的组件图形绘制。Swing 本身用 Java 编写。Swing 还对组件的实际绘制、绘画及其外观和感受拥有更多控制权，允许你在所有平台上为应用程序指定通用的视觉外观和感受。
- **JavaFX**：目前的下一代图形工具包。它基于场景图模型。提供了用于布局和 JavaFX 组件的 `FXML`。它还提供了比 Swing 更强大的内置组件（例如 MediaFX 库）。JavaFX 应用的外观和感受可以使用调用样式表（CSS）进行自定义。JavaFX 的设计使得在应用程序中提供环境变得更容易。如果需要，用户还可以通过 `Swing JPanelFX` 在 Swing 应用中嵌入 JavaFX 特性。

### 2. 通俗来说，Swing 中的“组件”是指什么？

Swing 中的组件意味着你用户界面中的“图形”组件。内置图形组件的知名示例包括按钮（推入）、文本区域（有许多不同类型）、单选框、复选框、列表框、滚动条、菜单、文件选择器和工具提示等。这些组件每个都可以“监听”用户交互并将其报告给应用程序进行适当处理。

你也可以构建自己的自定义组件。

### 3. 粗略地描述 Java 的组件以及如何在 Java Swing 中构建图形应用

Java 应用存在于帧中（你可以将其想象成一张图片）；这是通过 `JFrame` 对象实现的。`JFrame` 对象有许多不同的子组件，其中直接相关的有：
1. 应用程序帧（使用）
2. 菜单栏（可选）
3. 内容面板（通常为 `JPanel`），应用程序组件（如按钮、文本区域、复选框等）就位于此处。

> **注**：原文此处存在大量重复段落，已根据逻辑合并并去重。

### 4. 运行解释并解释其作用。同时，解释为什么应用程序需要在线程中运行

在这个方法中，我们创建了一个 `JFrame` 对象。回想练习 3 你应该记得，每个图形应用程序都是从一个 `JFrame` 对象开始的。接下来，我们指定当用户选择窗口上的关闭按钮时应用程序执行的操作；我们的选择由常量 `JFrame.EXIT_ON_CLOSE` 指定。随后，我们引导应用程序使框架可见。

GUI 应用程序运行在 Swing 的“事件分发线程”（Event Dispatch Thread，EDT）上。GUI 应用在事件分发线程上运行的方式是在实现 `Runnable` 接口的类的 `run` 方法中调用 GUI 类的实例。在示例中，我们看到了实现 `Runnable` 的匿名类。我们实现了接口方法 `run`，并在该方法中创建 GUI 类的实例，并启动创建我们 GUI 方法。

“事件分发线程”负责图形应用程序中事件通知的适当调度和处理。

> **观察**：运行程序时，你会发现应用程序启动时的长度和宽度均为 0 像素！这是因为我们没有使用 `JFrame.setSize(width, height)` 方法为它指定大小。
> **注意**：我们在 Java GUI 中使用了多线程；使用了 `Runnable` 接口。这种关于线程的初级知识对于你的测试来说足够了。

### 5. 用术语描述 Swing 中的布局管理器

之前已经提到过（参见练习 3 的答案），Swing 提供了布局管理器的概念来处理顺序放置组件的任务。Swing 提供了以下 8 种布局管理器：

- **BorderLayout**：该管理器定义了 5 个区域：顶部、底部、左侧、右侧和中心。这些区域的常量分别为 `BorderLayout.PAGE_START`、`BorderLayout.PAGE_END`、`BorderLayout.LINE_START`、`BorderLayout.LINE_END` 和 `BorderLayout.CENTER`。
- **BoxLayout**：该管理器按从上到下或从左到右顺序排列组件（这些常量分别为 `BoxLayout.PAGE_AXIS` 和 `BoxLayout.LINE_AXIS`）。
- **CardLayout**：该管理器允许你将许多面板作为给定框架的候选；正如名称所示，此管理器实际上像堆叠的纸牌一样，在任何给定时间只有当前卡牌（如果是顶部的面板）可见。
- **FlowLayout**：流动布局从左到右在面板中放置组件，必要时扩展到更多行。它确保每行都居中显示。
- **GridLayout**：该容器将面板划分为等大小的网格。每个组件被放置在一个网格中。这种布局使每个组件填充其网格位置，每个组件都可以缩放到指定大小。
- **GridBagLayout**：该管理器拥有网格，但并不是每行的高度都相同，且给定组件可以跨越多个网格。
- **GroupLayout**：该管理器允许用户同时指定一组项目，要求用户指定该项目的水平分组和垂直分组。
- **SpringLayout**：在此管理器中，组件的位置是由其与其他组件的垂直和水平距离定义的。
- **绝对定位**：除了布局管理器，你还可以通过 (x, y) 位置直接将组件放置在面板上。这被称为绝对定位。

除了上述之外，Java 还允许你创建自定义的布局管理器。

### 6. 你可以将 `JPanel` 对象放在另一个 `JPanel` 对象内部吗？

是的，可以的！

### 7. 你为什么可能想将 `JPanel` 对象放在另一个 `JPanel` 内部？

对于你的应用程序来说，屏幕上可能有不同的组件分组，不同类型的布局管理器将是最佳选择。这就是当你希望在一个类中使用不同面板时的情况。

**实现**：鉴于框架有一个单一的内容面板，必须为内容面板选择一个布局管理器，并将“子面板”像其他任何组件一样插入到此布局管理器中。

---

## 练习你的 Java 1 级水平

### 8. 设置应用程序窗口的初始大小

给定以下确定屏幕大小的代码：

```java
Dimension screenSize = Toolkit.getDefaultToolkit().getScreenSize();
// 高在 screenSize.height 中，宽在 screenSize.width 中
```

修改练习以将应用程序的大小设置为屏幕宽的 1/2 和高度的 1/2。

> **提示**：`JFrame.setSize`

```java
public class GraphicsPractice {
    public void createUI() {
        Dimension screenSize = Toolkit.getDefaultToolkit().getScreenSize();
        JFrame frame01 = new JFrame("My Application Title");
        frame01.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame01.setSize(screenSize.width / 2, screenSize.height / 2);
        frame01.setVisible(true);
    }
    
    public static void main(String[] args) throws Exception {
        SwingUtilities.invokeAndWait(new Runnable() {
            public void run() {
                new GraphicsPractice().createUI();
            }
        });
    }
}
```

### 9. 使应用程序在启动时在屏幕上居中

修改应用程序来实现这一点。

> **提示**：`JFrame.setLocationRelativeTo`

只需在使其可见之前在代码中添加以下行：

```java
frame01.setLocationRelativeTo(null);
```

### 10. 修改应用程序，使其在启动时出现在位置 (25, 25)

> **提示**：`JFrame.setLocation`

只需在使其可见之前在代码中添加以下行：

```java
frame01.setLocation(25, 25);
```



```java
JFrame01 = new JFrame("My Application Title");
frame01.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
panel01 = new JPanel(new GridLayout());
frame01.setContentPane(pane01);
frame01.setSize(screen.width/2, screen.height/2);
label101 = new JLabel("Title");
label102 = new JLabel("Hello!");
label103 = new JLabel("Bye!");
Font font01 = new Font("Arial", Font.BOLD, Font.ITALIC);
label103.setFont(font01);
label104 = new JLabel(null);
label105 = null;
try {
    Image img = Image.read(new File("C:\\Users\\Admin\\Desktop\\a.png"));
    label104.setIcon(new ImageIcon(img));
    label105 = new JLabel("Hello", new ImageIcon(img), SwingConstants.TRAILING);
} catch (Exception e) {
    System.out.println("Couldn't set the image");
}
pane01.add(label101);pane01.add(label102);
pane01.add(label103);
pane01.add(label104);
frame01.setVisible(true);
}
public static void main(String[] args) throws Exception {
    SwingUtilities.invokeLater(new Runnable() {
        public void run() {
            new graphicsPractice().createGUI();
        }
    });
}
```

## 15. JTextField

在带有布局的程序中创建以下 `JTextField` 对象：

1. 一个 30 列宽的空 `JTextField`
2. 一个文本为 "Hello" 的 `JTextField`
3. 一个在 30 列字段中文本为 "Hello" 的 `JTextField`
4. 一个文本为 "How are you" 的 `JTextField`，格式为：Arial、粗体、斜体、大小 25

此外，将此 `JTextField` 设置为不可编辑状态。

提示：检查 `JTextField`、`Font`、`JTextField.setEditable()` 的类和方法。

```java
public class graphicsPractice {
    public void createGUI() {
        Dimension screen = Toolkit.getDefaultToolkit().getSize();
        System.out.println("height = " + screen.height);
        System.out.println("width = " + screen.width);
        frame01 = new JFrame("My Application Title");
        frame01.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        panel01 = new JPanel(new GridLayout());
        frame01.setContentPane(pane01);
        frame01.setSize(screen.width/2, screen.height);
        textField01 = new JTextField("JTextField", 30);
        textField02 = new JTextField("Hello!", 30);
        textField03 = new JTextField("Hello", 30);
        textField04 = new JTextField("How are you?", 30);
        Font font01 = new Font("Arial", Font.BOLD | Font.ITALIC, 25);
        textField04.setFont(font01);
        pane01.add(textField01); pane01.add(textField02); 
    }
```

## 第 32 章：使用 Swing 图用户界面

```java
frame01.add(textField03); frame01.add(textField04);
frame01.setVisible(true);
textField01.setCut(\)
public static void main(String[] args) throws Exception{
    SwingUtilities.invokeAndWait(new Runnable(){
        public void run() {
            new graphicsPractice().createGUI();
        }
    });
}
```

## 观察

1. 注意在此布局中，`JTextField` 的高度是如何设置为与它包含的字体高度匹配的。
2. 注意，在没有显式为 `JTextField` 分配宽度的情况下，分配给字段的宽度与其文本长度匹配。从这可以得出的结论是，如果你想为 `JTextField` 指定特定的宽度，应该显式地分配。
3. 为什么建议使用 `JPasswordField` 组件来接收用户输入的密码？

建议这样做的原因是 `JPasswordField` 组件会掩盖输入其中的数据。

4. 解释 `JScrollPane` 组件的作用。

某些对象可以包含多行文本，但它们没有提供滚动行的功能，因此部分数据对用户是隐藏的。这有两种解决方案：(1) 确保显示组件的大小足够显示所有数据（这仅可行）或 (2) 将组件放入 `JScrollPane` 组件中。`JScrollPane` 具有滚动内容的能力。

5. JList 和 JScrollPane

解释什么是 `JList` 以及它与 `JScrollPane` 的关系。

`JList` 是一个以垂直方式包含并显示项目的组件，但无论放入其中的项目列表大小如何均可处理。后者允许用户选择单个项目、一组连续项目或一组不连续项目中的某一个。

如果条目数量超过了显示的 `JList` 控件的大小，则 `JList` 需要 `JScrollPane` 来帮助查看其条目。

6. 以下代码段显示了如何将系统字体列表获取字符串数组：

`String[] strings = GraphicsEnvironment.getLocalGraphicsEnvironment().getAvailableFontNames();`

在 `JList` 组件中显示所有字体，每次显示 10 个项目。

```java
public class Practice {
    public void createGUI() {
        Dimension size = Toolkit.getDefaultToolkit().getSize();
        System.out.println("height = " + size.height);
        System.out.println("width = " + size.width);
        frame01 = new JFrame("My Application Title");
        frame01.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        panel01 = new JPanel(new GridBagLayout());
        frame01.setContentPane(pane01);
        frame01.setSize(size.width/2, size.height);
        String[] array = GraphicsEnvironment.getLocalGraphicsEnvironment().getAvailableFontNames();
        JList<String> list = new JList<>(array);
        list.setVisibleCount(10);
        JScrollPane scrollPane = new JScrollPane(list);
        panel01.add(scrollPane); // 为列表获取滚动条并放入 JScrollPane
        scrollPane.setViewport(list);
        frame01.add(textField03);
        frame01.setLocationRelativeTo(null);
        frame01.setVisible(true);
    }
}
```

## 练习你的 Level 1

```java
public class graphicsPractice {
    public void createGUI() {
        Dimension screenSize = Toolkit.getToolkit().getSize();
        JFrame frame01 = new JFrame("My Application Title");
        frame01.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        JPanel pane01 = new JPanel(new BorderLayout());
        frame01.setContentPane(pane01);
        frame01.setSize(screenSize.width/2, screenSize.height);
        Object[] tableHeading = {"Continent", "Size", "Population"};
        Object[][] data = {
            {"Asia", 382000, 4162500},
            {"Africa", 3037000, 1022340},
            {"North America", 2499000, 5425600},
            {"South America", 1784000, 3925550},
            {"Antarctica", 1372000, 45000},
            {"Europe", 1018000, 738190},
            {"Australia", 900850, 291270}
        };
        DefaultTableModel model = new DefaultTableModel(data, tableHeading);
        JTable table01 = new JTable(model);
        JScrollPane scrollPane = new JScrollPane(table01);
        table01.setEnabled(false);
        pane01.add(scrollPane);
        frame01.setLocationRelativeTo(null);
        frame01.setVisible(true);
    }
    public static void main(String[] args) throws Exception {
        SwingUtilities.invokeAndWait(new Runnable() {
            public void run() {
                new graphicsPractice().createGUI();
            }
        });
    }
}
```

## 第 32 章：使用 Swing 图用户界面

7. 解释组件 `JMenuBar`、`JMenu` 和 `JMenuItem` 之间的关系。这三个类代表了创建（1）菜单栏（使用 `JMenuBar`，通常位于应用程序顶部）、下拉菜单（`JMenu`）以及创建单独项（`JMenuItem`）所需的元素。

8. 创建具有三个选项：早餐、午餐和晚餐的下拉菜单。早餐菜单应该有一个包含选项：炒蛋加吐司、牛奶和咖啡的子菜单。

```java
class graphicsPractice {
    public void createGUI() {
        JFrame frame0 = new JFrame("Menu example");
        frame0.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        JPanel pane01 = new JPanel(new GridLayout());
        frame0.setContentPane(pane01);
        frame0.setSize(300, 300);

        // 我们创建菜单栏
        JMenuBar menuBar = new JMenuBar();
        // 然后我们创建单独菜单
        JMenu menu01 = new JMenu("Meals");
        menu01.add(menu1);
        // 注意：早餐本身不仅仅是一个项，它是一个“菜单”，因为它有子项
        JMenu breakfastMenu = new JMenu("Breakfast");
        breakfastMenu.add("Scrambled Eggs & Toast");
        breakfastMenu.add("Cereal & Milk");
        breakfastMenu.add("Muffin & Coffee");
        menu01.add(breakfastMenu);
        // 午餐和晚餐是菜单项...
        JMenuItem menuItem02 = new JMenuItem("lunch");
        menu01.add(menuItem2);
        JMenuItem menuItem03 = new JMenuItem("Dinner");
        menu01.add(menuItem3);
        frame.setMenuBar(menuBar); // 将整个部分放在框架上
        frame.setLocationRelativeTo(null);
        frame.setVisible(true);
    }

    public static void main(String[] args) throws Exception {
        SwingUtilities.invokeLater(() -> {
            new graphicsPractice().createGUI();
        });
    }
}
```

9. Check选框 创建并显示一组四个 Checkbox 项，分别标记为 Shirt、Shorts、Socks 和 Shoes。使用以下字体：Arial、粗体和斜体，大小为 20。

（实现此点的代码片段所示）

```java
Font font01 = new Font("Arial", Font.BOLD | Font.ITALIC, 20);
JCheckBox cb01 = new JCheckBox("Shirt");
JCheckBox cb02 = new JCheckBox("Shorts");
JCheckBox cb03 = new JCheckBox("Socks");
JCheckBox cb04 = new JCheckBox("Shoes");
cb01.setFont(font01);cb02.setFont(font01);
cb03.setFont(font01);cb04.setFont(font01);
pane01.add(cb01); pane01.add(cb02);
pane01.add(cb03); pane01.add(cb04);
```

// 将组件添加到你的面板中

## 练习你的 Java 1 级

10. 为以下每个组件提供简要描述：`JTextField`、`JTextArea` 和 `JPane`。

`JTextField` 是一个只能显示单行文本的组件。它的背景颜色、字体颜色和大小可以修改，甚至可以设置为**粗体**和*斜体*。

`JTextArea` 可以显示多行文本，并具备上述所有功能。



Pane 具有类似于文字处理器的实际功能。它拥有上述描述组件的所有功能，并且支持在同一个 `JTextArea` 对象内应用不同的功能。它允许对单个字符（或字符组）应用不同的样式，包括应用下划线（其他两个组件不支持）、不同的字体以及上标/下标等功能。它还可以作为 HTML 编辑器使用。

这些组件都是可编辑的。

### 25. 分别创建两个具有以下特征的 JTextField 对象

第一个应包含字符串 "I am a TextField"。第二个应包含字符串 "I am the 2nd JTextField"。它的宽度应该与字符串的宽度匹配。

第二个 textField 的其他特征为：颜色：红色，字体：Lucida Console，**粗体**，大小：25。

```java
String string1 = "I am a JTextField"
String string2 = "I am the 2nd JTextField"

Font font1 = new Font("Lucida Console", Font.BOLD | Font.ITALIC, 25);
jTextField01 = new JTextField(string1, string1.length());
jTextField02 = new JTextField(string2, string2.length());
jTextField02.setForeground(Color.RED);
jTextField02.setFont(font1);
```

### 26. 创建一个维度为 2 行 30 列的 JTextArea，并将其放入 JScrollPane 中

在 TextArea 中放入儿歌 "Had had a little" 的行内容。确保文本使用 Lucida Console 字体、**粗体**、*斜体*且大小为 25。

```java
String string1 = "Had had a little\n lamb"
String string2 = "Had had a little lamb\nthat was as white as snow\n"
JTextArea textArea01 = new JTextArea(string1, 2, 30);
Font font1 = new Font("Lucida Console", Font.BOLD | Font.ITALIC, 25);
textArea01.setFont(font1);//add the text to the JTextArea
JScrollPane scrollPane = new JScrollPane(textArea01);//add the object to your panel
```

### 27. 创建一个内容为儿歌 "Had had a little lamb" 内容的 JTextField，需满足以下要求

1. 第一行应为上标。字体应为 Lucida Console，大小 20。
2. 第二行应为红色并带有下划线。字体应为 Arial，大小 20。
3. 第三行应为*斜体*并带有删除线。字体应为 Courier New，大小 15。
4. 所有后续行应使用 Gambit 字体，大小为 25，并带有青色背景。

```java
String[] rhyme = new String[5];
rhyme[0] = "Had had a little lamb\n"
rhyme[1] = "little lamb\n"
rhyme[2] = "little lamb\n"
rhyme[3] = "Had had a little lamb\n"
rhyme[4] = "that was as white as snow\n"
TextPane textPane01 = new JTextPane();
Document doc = textPane01.getDocument();
textPane01.setSize(200,200);
SimpleAttributeSet attr = new SimpleAttributeSet();

attr.addAttribute(Style.Constants.FontFamily, "Lucida Console");
attr.addAttribute(Style.Constants.FontSize, 20);
```

```java
attr0.addAttribute(StyleConstants.Constants.Superscript, Boolean.TRUE)
SimpleAttributeSet attr1 = new SimpleAttributeSet();
attr1.addAttribute(StyleConstants.Constants.FontFamily, "Arial");
attr1.addAttribute(StyleConstants.Constants.FontSize, 20);
attr1.addAttribute(StyleConstants.Constants.Foreground, Color.RED);
attr1.addAttribute(StyleConstants.Constants.Underline, Boolean.TRUE)
SimpleAttributeSet attr2 = new SimpleAttributeSet();
attr2.addAttribute(StyleConstants.Constants.Foreground, Color.BLUE);
attr2.addAttribute(StyleConstants.Constants.Italic, Boolean.TRUE)
attr2.addAttribute(StyleConstants.Constants.Strikethrough, Boolean.TRUE)
attr2.addAttribute(StyleConstants.Constants.FontFamily, "Courier New")
attr2.addAttribute(StyleConstants.Constants.FontSize, 15);
SimpleAttributeSet attr3 = new SimpleAttributeSet();
attr3.addAttribute(StyleConstants.Constants.FontFamily, "Garamond")
attr3.addAttribute(StyleConstants.Constants.FontSize, 25);
attr3.addAttribute(StyleConstants.Constants.Background, Color.CYAN);
```

```java
try {
    doc.insertString(0, rhyme[0], attr0)
    doc.insertString(doc.getEndPosition().offset(rhyme[1]), attr1)
    doc.insertString(doc.getEndPosition().offset(rhyme[2]), attr2)
    doc.insertString(doc.getEndPosition().offset(rhyme[3]), attr3)
    doc.insertString(doc.getEndPosition().offset(rhyme[4]), attr3)
} catch (Exception e) {
```

### 28. Pane 中的 Pane（嵌套）

编写一个程序，使用 `JScrollPane` 显示 `JTextArea`。`JTextArea` 应该有一个标题为 "Font List" 的边界。`JScrollPane` 应该被添加到 `JPanel` 中，然后添加到 `JFrame` 中。`JFrame` 的大小应为 300x200，默认关闭操作设置为 `EXIT_ON_CLOSE`。

### 29. 事件监听器

1. 通过应用于单个组件的匿名类来监听事件
2. 让 GUI 类实现监听器

展示实现 `MouseListener` 的 `JButton` 代码示例。

（查看 3 和 4 的解答以总结事件）

编写事件监听器的两种方式之间的区别在于：在一种情况下，为每个组件实现了特定事件接口的实现；在另一种情况下，使用匿名类的单一列出。这种方法使得你的代码位于同一个面板中，你可能更喜欢；它使得 GUI 中许多对象的响应代码更加紧凑，你不需要为每个对象的行为编写的匿名类。

应该理解 Swing 组件已经准备好了实现相关接口的对象。这些方法通常命名为 `addListenerType`，例如 `JButton` 的 `addEventListener` 方法。感兴趣的读者可以查看 `JButton` 等类的定义，以查看组件支持的监听器方法列表。

下面显示了一个 `JButton` 对象的示例，其中对每种情况都实现了代码

#### 实现监听器的匿名类方法

我们下面展示了一个 `JButton` 对象的示例，该对象实例化了一个实现 `MouseListener` 的匿名类：

```java
JButton button01 = new JButton("Starting out");
button01.addListener(new MouseListener(){
    public void mouseClicked(MouseEvent arg) {
        button01.setText("You clicked!");
    }
    public void mouseEntered(MouseEvent arg) {
        button01.setText("You are hovering over me!");
    }
    public void mouseExited(MouseEvent arg) {
        button01.setText("Phew! what was left!");
    }
    public void mousePressed(MouseEvent arg) {
    }
    public void mouseReleased(MouseEvent arg) {
    }
});
```

```java
button01.setText("why are you pressing the mouse?");
  public void mouseReleased(MouseEvent arg) {
    button01.setText("Now you've released it!");
}
```

#### 让 GUI 类实现监听器

使用此方法有三个步骤：

**步骤 1**

在演示器（presenter）中声明该类实现了监听器，例如：

```java
public class graphicsPractice implements MouseListener(
```

**步骤 2**

然后你必须按照以下简单方式在事件中注册 `MouseListener`：

```java
<frame>addMouseListener(this);
或者，如果你想对每个应该监听事件的对象进行单独注册，可以为 button01 编写以下代码；
button01.addMouseListener(this);
```

（每个实现的监听器类型都有自己的注册方法。如此示例所示，我们只监听鼠标事件）

**步骤 3**

现在，在代码中我们必须实现与之前代码相同的接口。

除非你指定，否则你不能直接写：

```java
public void mouseClicked(MouseEvent arg) {
  button01.setText("You clicked me!");
}
```

之所以不能这样做，是因为当类实现接口时，接口会对该页面上的每一个对象做出响应。我们必须在实现风格中确定是哪个对象被点击了。为此，我们必须通过 `MouseEvent` 的 `getSource` 方法从参数 `arg` 中获取对象名称，如下

```java
public void mouseClicked(MouseEvent arg) {
  Object affectedObject = arg.getSource();
  if (affectedObject.equals(button01)) {
    button01.setText("You clicked me!");
  }
  以及在你的应用程序中编写用于对此特定事件做出反应的后续 (if 条件)。
}
```

你不需要创建对象引用 `affectedObject`，可以简单地使用：

```java
if(arg.getSource().equals(button01)){
  执行操作...
}
if(arg.getSource().equals(button02)){
  执行当 button2 被按下时的操作...
}
```

> **注意**：不要忘记直接在类中声明对象的引用，而不是在 GUI 实例化的方法调用中，因为这些对象引用必须具有适当的可见性。

建议读者将这些代码段放置在之前开发的解决方案中观察其运行情况。

# 第 32 章：使用 Swing 构建图形用户界面

## 练习你的 Java 水平 I

创建一个符合以下规范的程序：

1. 程序应该有一个 `JTextField` 对象，其初始内容为 "Just starting out"。
2. 当鼠标移动到 `JTextField` 上时，它的文本应该变为 "Hey mouse, I saw you enter..."。
3. 当鼠标在内部被点击时，它的文本应该变为 "Don't click please!"。
4. 当鼠标在内部被按住时，它的文本应该变为 "Why are you holding the mouse down?"。
5. 当鼠标释放时，它的文本应该变为 "Stopped holding it down. That's good, please leave!"。
6. 当鼠标离开时，它的文本应该变为 "Phew...the mouse left!"。

使用提供的两种方法为此事件提供两种解决方案：

### 解决方案 #1：使用匿名类

```java
public class graphicsPractice {
    JTextField tf01;
    public void createGUI() {
        Dimension size = Toolkit.getDefaultToolkit().getSize();
        JFrame frame01 = new JFrame("My Application");
        frame01.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        JPanel panel01 = new JPanel(new GridLayout());
        frame01.setContent(panel01);
        frame01.setSize(size.width/2,size.height/2);
        tf01 = new JTextField("Just starting out");
        Font font0 = new Font("Lucida Console", Font.BOLD, Font.ITALIC);
        tf01.setFont(font0);
        tf01.addMouseListener(new MouseListener() {
            public void mouseExited(MouseEvent arg) {
                tf01.setText("Hey mouse, I saw you enter...");
            }
            public void mouseClicked(MouseEvent arg) {
                tf01.setText("Don't click please!");
            }
            public void mousePressed(MouseEvent arg) {
                tf01.setText("Why are you holding the mouse down?");
            }
            public void mouseReleased(MouseEvent arg) {
                tf01.setText("You are holding it down. That's good, but please leave!");
            }
            public void mouseEntered(MouseEvent arg) {
                tf01.setText("Phew...the mouse left!");
            }
        });
        panel01.add(tf01);
        frame01.setVisible(true);
    }
    public static void main(String[] args) throws Exception {
        SwingUtilities.invokeLaterAndWait(new Runnable() {
            public void run() {
                new graphicsPractice().createGUI();
            }
        });
    }
}
```

### 解决方案 #2：使用匿名类

```java
public class graphicsPractice implements MouseListener
```

# 第 32 章：图形用户界面 Swing



```java
JTextField tf01;
public void createGUI() {
    Dimension screenSize = Toolkit.getDefaultToolkit().getSize();
    JFrame frame01 = new JFrame("My Application");
    frame01.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    JPanel panel01 = new JPanel(new GridBagLayout());
    frame01.setContent(panel01);
    frame01.setSize(width/2, screenSize.height);
    tf01 = new JTextField("Just starting out", 50);
    Font font01 = new Font("Lucida Console", Font.BOLD, Font.ITALIC, 20);
    tf01.setFont(font01);
    tf01.addMouseListener(this); // 注册对象以监听鼠标事件
    // 我们可以注册 frame，但这是
    frame01.add(tf01);
    frame01.setVisible(true);
}

public void mouseClicked(MouseEvent event) {
    tf01.setText("Don't click please!!!");
}
public void mouseEntered(MouseEvent event) {
    tf01.setText("Hey mouse, I saw you enter...");
}
public void mouseExited(MouseEvent event) {
    tf01.setText("phew...the mouse left!");
}
public void mousePressed(MouseEvent event) {
    tf01.setText("why are you holding the mouse down?");
}
public void mouseReleased(MouseEvent event) {
    tf01.setText("You stopped holding it down. That's good, but please leave!");
}

public static void main(String[] args) throws Exception {
    SwingUtilities.invokeAndWait(new Runnable(){
        public void run() {
            new GraphicsPractice().createGUI();
        }
    });
}
```

学习以下组件：`JComboBox`、`Tooltip`、`JSpinner`。

# 字体选择器应用程序

编写一个看起来像 [字体选择器应用程序](img/25945951eab275f18dbcf76e314_0.png) 的程序。

主要的图形元素类型有 `JList`、`JComboBox` 和 `JTextPanel`。修改 `JPanel` 中的 "Sample" 以匹配所选择的内容。注意互斥项（例如上标和下标）。

| | |
| :--- | :--- |
| `JSpinner` 对象应该包含你支持的字体范围。 | 有兴趣的读者应该学习 `Dialog` 的概念。 |
| 学习如何将复选框等其他组件放入 `JTable` 对象。 | |

# 第 33 章：Applets – 简述

本章介绍了关于 Java Applet 的一组非常短的练习。由于我们已经涵盖了 GUI 并考虑到 Applet 是在浏览器中运行的修改版 GUI 应用，我们提供了以下简短练习。

| | |
| :--- | :--- |
| 1（用一行解释）什么是 Java Applet？ | Applet 是一种编写在网页上运行的 Java 程序。 |
| 2 为什么最初会有 Applet？ | Applet 存在的初衷之一是为用户提供更丰富的图形体验；Applet 早于层级样式表 (CSS) 和 HTML5，后者为网页设计提供了更高级的图形选项。 |
| 3 解释浏览器支持运行（而非加载）java applet 的机制。 | 网页浏览器支持 Java 应用运行有两种方式：1. 在浏览器内部嵌入 JVM；2. 安装 Java 浏览器插件（通过许多浏览器提供的浏览器扩展接口工作）。该插件随后在网页上运行 applet。 |
| 4 什么是 WebStart 应用？ | WebStart 应用是一种通过 Java 网络启动协议 (JNLP) 加载的 Java 应用。浏览器嵌入不仅有助于在浏览器中加载 Java 应用，还有助于通过网络加载桌面应用并在计算机上作为普通程序运行。 |
| 5 解释通过 HTML 将 applet 加载到浏览器的机制。 | 使用了两组不同的标签：基础 applet 标签和 jnlp 标签。 |

## 使用 applet 标签

相关对象及其启动参数（例如启动大小）被嵌入 HTML 页面的 HTML `<applet>` 标签中。浏览器会识别并运行指定的 applet。例如，如果我们有一个本地 applet（我们的示例是一个编译为名为 `Hello` 的类），我们将其嵌入 HTML 页面如下：

远程 applet 需要指定 `codebase`，例如从 zyco 的 Web 服务器加载的 applet 可能如下：

```html
<applet code="Hello" width="300" height="200"></applet>
<applet codebase="http://www.zyco.com/appletdir/" code="Hello.class" width="300" height="200"></applet>
```

## 使用 JNLP

JNLP 使用不同的 HTML 标签，主要是 `<jnlp>` 标签。此外，JNLP 规定了打包 applet 的特定方法。这不涉及 JNLP 的细节，但希望你了解此功能。

### 注意

1. 为了便于测试，可以使用 Java 自带的 `applet viewer`。此外，某些 IDE 在你尝试运行并在 applet viewer 中启动你的 applet 时会自动识别代码。
2. 目前，所有 applet（无论本地还是远程）在允许运行之前都必须由证书机构签名。如果你在计算机上配置 Java 控制面板（执行 `javcp`）中的条目，指定本地类的位置，并设置浏览器权限，你就可以在支持 Java 应用的浏览器中运行本地 applet。你必须将类文件的 URI 使用到 Java 控制面板中异常列表中 an。（参阅第 29 章练习 51，获取如何确定目录或文件夹 URI 的示例）。

## 练习你的 Java 11

3. 官方已尝试废弃 `<applet>` 标签。取而代之，可以使用 `<object>` 标签或 `<embed>` 标签。

6. 解释 applet 的“安全沙箱”概念。

安全沙箱指的是施加在 Java applet 上的限制。例如，运行在沙箱中的 Java applet 无法访问所在计算机的系统文件，也无法访问下载来源以外的任何网络节点（通过名称，而不是 IP 地址）。它甚至无法访问系统剪贴板。此外，沙箱化的 applet 只能读取一份可用系统属性的列表。

7. 什么是“特权”（privileged）applet？

特权 applet 是运行在沙箱之外且不受沙箱 applet 限制的 applet。任何签名的 applet 都可以请求以特权 applet 的身份运行。当然，用户在使用此类 applet 时必须小心，因为此类 applet 有访问用户计算机组件的权限。

8. 解释 applet 和普通 Java GUI 之间的区别。

Java applet 是一个扩展了 `Applet` 类的公共类（对于 Swing applet，AWT applet 会扩展 `Applet`），而桌面 GUI 应用是扩展了 `JFrame` 的。

Java applet 没有 `main` 方法；它有一个名为 `init` 的方法，执行相同的功能。

`JFrame` 的 `getSize` 和 `setVisible` 方法对于 applet 并不相关，因为它根据 HTML 标签中的指定来设置大小，并由浏览器自动显示。

查看下方的示例 applet 代码：

```java
import java.awt.EventQueue;
import javax.swing.Applet;
import javax.swing.JLabel;

public class AppHello extends Applet{
    public void init(){
        EventQueue.invokeLater(new Runnable(){
            public void run() {
                JLabel label01 = new JLabel("Hello. How are you?");
                add(label01);
            }
        });
    }
}
```

关于安全：我们在之前的练习中已经讨论了此类 applet 的安全限制。考虑到这些，我们理解任何沙箱化的 applet 都不应该尝试任何文件操作（尽管代码在编写和编译时可能包含此类操作，但尝试访问受限区域将导致异常）。

## 附录 A 类、对象与方法：导论

本附录介绍了类和对象的概念，然后介绍了这些概念在 Java 中的实现。对类和对象概念陌生的读者可以放心，类和对象的基本概念其实很简单。

之后，将对 Java 中的方法概念进行介绍。

### 类与对象

我们从一个问题开始：*什么是类？* 我们通过类比来解释，第一个类比是人类。

人类的概念是一个*类*（class）。

你读者是人类类的一个*实例*（instance）。

你的父亲是人类类的一个实例。

你的母亲是人类类的一个实例。

我们用狗作为另一个类比。假设你有一只狗，你的邻居有两个狗。

这个*类*是 *Dog*。

你自己的狗是 `Dog` 类的实例。

你邻居的两个狗各各是 `Dog` 类的实例。

在 Java 代码中，表示人类的类可以写如下：

```java
class HumanBeing{
}
```

我们刚刚写了表示人类的 `HumanBeing` 类的基本代码。

要创建类的实例（你、父亲、母亲），每个类的代码简单如下：

```java
Human be = new HumanBeing();
Human father = new HumanBeing();
Human mother = new HumanBeing();
```

将类简单地视为一个模板。类的每个实例都拥有我们在模板中列出的所有属性（到目前为止，`HumanBeing` 类还没有放入任何属性）。

对于 *Dog* 的类比，我们可以有如下类定义：

```java
class Dog{
}
Dog myDog = new Dog();
Dog neighborDog1 = new Dog();
Dog neighborDog2 = new Dog();
```

这确实是类和对象的基本概念。

## 练习你的 Java 11

### 更多细节

现在，人类具有哪些特征/属性？例如他们有名、姓和体重。我们需要在每个实例内部设置字段。因此，我们将按照以下方式增强我们的 Java 类 `HumanBeing`：

```java
class HumanBeing{
    String firstName;
    String lastName;
    int age;
    float weight;
}
```

观察 `HumanBeing` 类的增强定义，可以发现每个字段都指定了类型。例如，我们的名和姓是“字符字符串”类型的数据；字符字符串数据可以用 Java 类型 `String` 表示。我们的年龄是整数（integers），Java 有许多许多可以处理的整数类型；我们选择了 `int` 类型。我们的体重中带有小数，因此我们需要一种可以处理小数的类型；`float` 是一种可以处理的类型。

现在，我们需要为每个人的独立对象设置数据字段吗？很简单。让我们为自己设置数据（我们的名字是 John Smith，40 岁，体重 178 磅）。

我们回到了每一个我们称为“我”的对象/实例，它们代表了我们自己。现在我们想做的是：

```java
me.firstName = "John";
me.lastName = "Smith";
me.age = 40;
```

（注：原文中存在大量 OCR 识别噪声和重复描述，翻译时已根据核心逻辑进行清理和整合。）

# 练习你的 Java 级水平

返回我们想要捕获的值；其返回类型为 `float`，且我们想知道具体是什么，因此我们创建一个名为 `myResult` 的 `float` 变量来接收加法方法的结果。

就像编写公式 `y = sin(x)` 一样，我们写了 `myResult = JohnsCalculator(value, value)` 并返回了结果。

注意：在 `addition` 方法定义中我们所谓的参数（我们把它们称为 `a` 和 `b`）并不重要，我们可以给它们起任何名字。`addition` 方法的意思仅仅是：“我接收两个数字，我会把第一个称为某个名字，第二个称为另一个名字，以便我跟踪它们”。

我们使用了内置方法 `System.out.println` 将结果打印到屏幕上。

简而言之，这就是类、类实例（对象）和方法的概念。你学过的主题包括：

类、类实例（对象）创建、类字段定义、实例字段赋值、实例方法创建、实例方法调用、向方法传递参数、从方法返回参数、使用 `main` 方法、将变量打印到控制台！

**注意：** 为了练习，鼓励读者在 `Calculator` 类中添加更多方法（例如除法、减法和乘法方法）并进行测试。

## 附录 B. 项目

这是一个将锻炼你在本书中介绍的多个领域技能的项目。在练习过程中，你应该能够识别出特定的 Java 特性如何应用于练习的不同部分。

在这个项目中，我们将模拟银行的运作。你将构建一个模拟程序，运行你指定的模拟周期，模拟周期反映从第1天到第30年的运营情况。

银行将有一组客户，他们不时来到银行。客户的潜在活动包括：

### 客户活动

1. 工资存款：客户每周向银行存款一次
2. 杂项存款
3. 申请贷款
4. 偿还（由银行自动扣款，且始终安排在工资存款的第二天）
5. 现金提取（如果他们提取过任何贷款，则账户中的余额必须足够支付下一次还款）
6. 当日交易账单（这应该包含服务客户的员工 ID#）
7. 获取上个月的每月银行账单，列出以下内容：
   - a. 他们的总存款
   - b. 给定月份内提取的现金金额
   - c. 每笔提取的贷款及利率
   - d. 截至目前的贷款总额
   - e. 截至目前的已还贷款金额
   - f. 每笔贷款的预计还款完成日期
   - g. 下一次还款日期

此账单应根据要求提供。此外，无论是否被请求，银行都应在每月初生成账单并存储在客户的目录中。

文件目录结构为 `customer_id_number/monthly_statements/`

对于客户进入银行的每一天，他们的每日活动记录应存储在以下目录中：`customer_id_number/year/daily_reports/`

### 日终职责

银行本身在一天结束时承担以下职责

1. 生成一份说明当日总存款的报告
2. 生成一份说明当天发放贷款总额的报告

这些报告应存储在命名适当的目录中。

### 银行贷款

1. 所有贷款的最大金额 = 薪资的 300%
2. 利率：在 3.00% 到 8.00% 之间随机选择值
3. 还款期限：可变，从一个月到30年不等
4. 客户的累计还款额不能超过其薪资的 50%

# 练习你的 Java 级水平

### 更多细节

模拟应创建以下内容：

一个银行客户列表。一种方法是准备一个名字列表和一个姓氏列表，然后从每个列表中随机配对数据，以便在模拟中生成任意数量的客户。同时，分配客户 ID 号；顺序数字可能是最优的。为每个客户随机分配以下内容：存款工资的日期和工资金额。如果该日期是银行未开放的日子，则客户应在下一个工作日存款。

你的客户类将具有表示以下内容的字段：`id`、`firstname`、`lastname`、`salary`、`deposit rate`。

一个银行柜员列表。指定使用的程序数量，并以与创建相同的方式从列表中创建它们。也为他们分配员工 ID。此员工 ID# 应出现在每天打印的客户账单上。

银行营业时间：在你的模拟中定义银行营业时间和日期。这将有助于确定“日终”。在银行未开放的日子，仍需提前生成当天的银行报告，以反映这些日的活动。

客户到达：随机选择在营业时间内在任何一天出现在银行的客户。他们应该进入队列，并由下一个可用柜员提供服务。在当天存款工资的客户不会被选中，但必须在当天的客户列表中。

客户在某一天可以有多个想要执行的活动。选择并运行这组活动。你可能希望对某些活动应用权重，例如，贷款请求不能太频繁。此外，如果客户发现贷款不合适，可以自由拒绝。

# 练习你的 Java 1 级

- `FileSystem`, 259
- `FileTime`, 262
- `Path`, 254
- `Paths`, 254
- `SimpleFileVisitor`, 266

## 输入/输出

- `Console`, 147
- `Scanner`, 150
- `System` (见方法中的), 154
- 成员
- `if`, 55
- `if/else`, 55
- `switch`, 57

### Console

- 输出方法, 7
- `System.out.print`, 7
- `System.out.printf`, 21
- `Frames`, 289
- `JavaFX`, 289
- 布局管理器, 291
- 绝对定位, 291
- `BorderLayer`, 291
- `BoxLayer`, 291



# 索引

## 杂项

- `Enum`, 91
- `FileSystem`, 249
- `Random`, 163
- `Runtime`, 248
- `System`, 247

## 数值

- `BigDecimal`, 99
- `BigInteger`, 95
- `Math`, 22
- `MathContext`, 101
- `Random`, 163
- `StrictMethod`, 110

## 数值包装类

- `Double`, 87
- `Float`, 187
- `Long`, 82
- `Short`, 87
- `StrictMethod`, 110

## 字符串处理

- `String`, 47
- `StringBuffer`, 167

## 终祖类

- `Object`, 185

## 常量

- 21

## D

- 日期/时间处理, 117
- 日期/时间格式化, 132
- `Decoder`/默认方法 (接口), 236
- `defender`/默认方法 (接口), 236

## E

- 枚举, 91
  - (高级), 285
- 日期/时间处理
  - `ChrononUtil`, 126
  - `DayOfWeek`, 127
  - `Month`, 127
- 声明，使用 92
- I/O
  - `StandardOpenOption`, 281
- 事件监听器, 300
- 异常, 137
  - 捕获, 137
  - 检查异常, 141
  - `finally` 块, 142
  - 抛出, 143
  - `throw`, 139
  - 有意地抛出, 139
  - `try/catch` 块, 137
  - 用户定义, 140

## I

- 压缩/Zip文件, 273
  - 创建, 274
  - 挖掘, 274
- 创建牙医, 255
- 创建子类, 255
- 访问 `DesktopLookup`, 254
- 访问文件访问时间, 262
- 访问灵活性, 262
- 访问隐藏状态, 261
- 访问无价值, 263
- 访问大小, 260
- 访问卷, 264
- 访问主目录, 254
- 访问工作目录, 253
- 访问目录操作, 269
- 访问目录遍历, 266
- 文件信息, 260
- 文件操作
  - 追加到文件(缓冲), 281
  - 缓冲文件, 277
  - 读取文件(缓冲), 279
  - 写入文件, 275
  - 写入文件(缓冲), 280
- 分类, 2
- 集合
  - (定义), 219
  - 泛型, 219
- 类
  - `ArrayList`, 219
  - `HashMap`, 228
  - `HashSet`, 228
  - `Stack`, 226
  - `TreeSet`, 227
- 命令行输入, 155
- 注释, 3
  - `//`, 3
  - 行`/*...*/`, 4
- 条件配置
  - `case`, 57

## G

- 泛型
  - (定义), 219
- getter/setter 方法, 200
- glob 通配（在过滤流数据上）, 258
- 图形用户界面
  - 嵌套路径, 299
- 图形用户界面
  - 抽象窗口工具包 (AWT), 289
  - 组件(定义), 289
  - 事件监听器, 289
- 文件
  - 复制, 264
  - 删除, 265
  - 移动, 265
  - 重命名, 265
- 符号链接
  - 创建 (硬), 271
  - 创建 (软), 269
  - 确定, 269
  - 确定实际的, 269
  - 硬链接 vs 软链接, 270

## K

- 二进制数, 32

## 索引

- 过滤数据流, 258
- 模式匹配, 258
- 列表提升器, 259
- 列表根, 259

## 关键字

- `byte`, 12
- 复数, 28
- `Paths`, 275
- 根确定, 275
- 元素检测, 275
- 设置工作目录, 254
- 符号链接, 268
- `break`, 57
- `case`, 57
- `catch`, 137
- `continue`, 76
- `default`, 57
- `do`, 74
- `extends`, 180
- `extends` (接口), 238
- `final`, 182
- `final` (应用到常量), 21
- `finally`, 142
- `Double.MIN_VALUE`
- `Double.MAX_VALUE`
- `Double.SIZE`
- `Float.MIN_VALUE`
- `Float.MAX_VALUE`
- `Float.NEGATIVE_INFINITY`, 288
- `Float.POSITIVE_INFINITY`, 288
- `Integer.MIN_VALUE`
- `Integer.MAX_VALUE`
- `Integer.SIZE`
- `Long.MIN_VALUE`
- `Long.MAX_VALUE`
- `Long.SIZE`
- `Initializer`, 198
- 实例初始化器, 198
- 静态初始化器, 197
- 输入/输出, 147
  - (定义), 231
  - (用法), 231
- 默认方法, 236
- `Short.MIN_VALUE`
- `Short.MAX_VALUE`
- `Short.SIZE`, 13
- 接口, 236
- 集合
  - `Deque`, 241
  - `Iterator`, 242
  - `List`, 241
  - `Map`, 241
  - `Queue`, 241
  - `Set`, 241
- `double`
  - 浮点数精度, 16
- `float`, 14
- 格式化输出, 33
- 规范, 33
- `DirectoryStream`, 256
- `int`, 11
- 迭代
  - `do/while` 循环, 74
  - `for` 循环, 70
- 关键字
  - `break`, 76
  - `continue`, 76
  - 标记 `break`, 76
- `long`, 13
- `while` 循环, 69
- 精度, 15
- 基本
  - `byte`, `short`, `int`, `long`, `float`, `double`, 12
- 标签, 76
- 无符号数, 11
- 包装类, 11
- `main`, 2
- 方法
  - `main`, 2
  - 方法声明, 5
  - 方法签名, 4
  - 重载, 5
  - 静态方法, 5
  - 参数个数 (变长), 6
- 修改器/访问方法, 200

## Object

- (定义), 175
- 对象
  - `new`, 81
- 运算符
  - (递减), 28
  - (减法), 22
  - (取模), 22
  - (除法), 27
- 迭代器, 242
  - `Iterator`, 242
  - `ListIterator`, 243

## J

- Java 虚拟机 (JVM), 2
- JVM (见虚拟机), 2

## N

- NIO/2.0, 253
- 数字类型
  - `BigDecimal`, 17
  - `BigInteger`, 17

## 练习你的 Java 1 级

- `+` (加法), 22
- `++` (自增), 28
- 菱运算符, 29
- `>>>` (无符号整数右移), 113
- 位运算运算符, 38
- `<<` (左移), 39
- `>>` (右移), 39
- 布尔运算符
  - `!=` (不等于), 42
  - `&` (与), 41
  - `<` (小于), 42
  - `<=` (小于等于), 41
  - `>=` (大于等于), 42
- 复合运算符
  - `&` (与), 43
  - `^` (异或), 45
  - `||` (或), 44
- 逻辑运算符, 38
  - `&` (与), 38
  - `!` (非), 38
  - `|` (或), 38
  - `~` (按位反), 38
- `short`, 29
- 三元运算符 `?`, 57
- 输出/输入, 14
- 溢出 (整数), 29
- 溢出/下溢避免
  - Exact 方法, 30
  - Exact 方法 (`BigInteger`), 98

## P

- 包
  - (定义), 1, 175
  - 从另一个包中访问, 199
- 多态, 195
- 数字类型精度, 15
- 基本类型
  - `boolean`, 41
  - `byte`, `short`, `int`, `long`, `float`, `double`, 11
- 基本变量
  - (定义), 201
- 基本字符, 157
- 属性, 247
  - 创建, 252
  - 读取, 247
  - 设置修改, 251

## R

- 随机数生成, 33, 163
- 格式化, 54
- 不变性, 48
- 子字符串, 49
- 符号链接 (见 I/O, 符号链接), 268
- 系统属性 (见属性), 247
- `System.out.println`, 7

## T

- 临时文件/目录, 272
- 类型
  - 定义, 201
  - 基本类型
    - (定义), 201
  - 引用类型
    - 定义, 201

## U

- 解箱, 82
- 解箱/装箱(见箱/装箱), 82
- 下溢 (整数), 30
- Unicode, 157
- Unicode/UTF-16, 157
- 无符号数处理, 111
- URI
  - I/O, URI, 272

## S

- setter/getter 方法, 200
- 单例模式, 192
- `StrictMath`, 109
- 字符串/字符关系, 161
- 字符串, 47
- 质量, 49

## V

- `varargs` (变长参数), 89
