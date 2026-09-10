
# Java 编程高级指南

## 第 1 章：Java 概述

### 面向对象编程

Java 的核心是面向对象编程（OOP）。事实上，所有的 Java 程序至少部分是面向对象的。OOP 是 Java 不可缺的一部分。在开始编写简单的 Java 程序之前，熟悉它的原理至关重要。本章将讨论 OOP 的理论方面和应用。

### 两种范式

计算机程序由代码和数据组成。程序在概念上也可以围绕其代码或数据进行组织。这意味着某些程序是根据“发生的事情”编写的，而另一些则是根据“受影响的对象”编写的。这两种范式决定了程序的构建方式。一种是面向模型的，将程序描述为一系列步骤（即代码）。这种模型是作用于数据的代码。这种模型在 `C` 等过程化语言中被广泛使用。

#### 抽象

抽象是面向对象编程的重要组件。抽象是人类管理复杂性的方式。例如，人们不会把汽车看成数千个部件的集合。它是一个定义清晰的对象，具有自己的行为。这种抽象让人们能够自由地开车去超市，而不必担心复杂的部件。他们不需要关注引擎、变速箱或刹车系统的复杂细节。相反，他们可以使用整个对象。

#### 封装

封装是将代码和数据结合在一起并保护它们免受误用和干扰的机制。封装可以被描述为一种保护性封装，阻止外部代码访问内部代码和数据。控制内部代码和数据访问的接口是良好定义的。这类似于汽车的自动变速箱。这些信息包含了关于你引擎的数百位数据，包括加速度的大小、路面的倾斜度和换挡杆的位置。

#### 多态与封装的协同工作

多态、继承和封装可以结合，创建一个比面向过程模型健壮得多的编程环境。你花费时间开发和测试的代码的复用基础是设计良好的层次结构。封装使得你可以在不破坏任何依赖于公共接口代码的情况下移动你的实现代码。多态允许创建出整洁、合理、易读且具有伸缩性的代码。

### 第一个简单程序

在涵盖了 Java 面向对象基础知识之后，让我们来看实际的 Java 程序。让我们从运行和编译以下示例程序开始。这比你想象的要多费一点精力。

```java
/*
这个 Java 程序非常简单。
该文件名为 "Example.java"。
*/
class Example {
    // 从回调 main() 方法开始你的程序
    public static void main(String args[]) {
        System.out.println("This is a simple Java program.");
    }
}
```

### 程序

在大多数计算机语言中，包含程序源代码的文件名无关紧要。Java 不同。Java 的第一课是理解文件名极其重要。这是源代码文件名的示例：`.java`。让我们看看为什么。Java 将源代码称为编译单元。Java 码是程序的中间表示，包含了 Java 虚拟机将执行的指令，这是我们之前讨论过的内容。因此，`javac` 的输出不是可以直接执行的代码。

你必须使用 Java 应用程序启动器（称为 `java`）来实际运行程序。如下所示，需要在命令行上将类名 `Example` 作为参数传递。

```
C:\>java Example
```

执行程序时将显示以下输出：

```
This is a simple Java program.
```

### IF 语句

Java 的 `if` 语句功能与任何其他语言的 `IF` 语句相同。它在语法上与 `C`、`C++` 和 `C#` 的 `if` 语句相同。这是它最简单的形式：

`if(condition) statement;`

这里 `condition` 是条件。这是一个布尔表达式。如果 `condition` 为真（true），则执行该语句。

假（false）条件意味着可以忽略该语句。这里有一个示例：

```java
/*
这个 Java 程序非常简单。
该文件名为 "IfSample.java"。
*/
class IfSample {
    public static void main(String args[]) {
        int x, y;
        if (x < 100) {
            System.out.println("num is less than y");
        }
        if (x == y) {
            System.out.println("x now equal to y");
        }
        if (x > y) {
            System.out.println("x now greater than y");
        }
    }
}
```

## 第 2 章：数据类型与变量

### 基本类型

Java 支持八种基本类型：`byte`、`short`、`int`、`long`、`char`、`float`、`double` 以及 `boolean`。简单类型和基本类型都很经常使用。你可以将它们分为四类：

* 整数：该组包括 `byte`、`short`、`int` 和 `long`，它们是有符号的整数。
* 浮点数：该组包括 `double` 和 `float`，它们是小数数字。

#### 整数

Java 有四种整数类型：`byte`、`short`、`int` 和 `long`。所有整数类型都是带符号的，有正负值。Java 不支持无符号整数。许多其他语言都支持符号和无符号整数。Java 开发者认为无符号整数是不必要的，因为可以使用高位来描述。Java 添加了特殊的无符号右移运算符来明确高位的含义。这消除了对无符号整数类型的需求。

#### 浮点类型

在评估带有精度的表达式时，使用了浮点数（也称为实数）。诸如平方根或正余函数等计算会产生点类型的值。Java 实现了标准的 IEEE-754 浮点运算符和类型。浮点类型有二：`float` 和 `double`。这些表示单精度或双精度的数字。

#### 字符

Java 使用 `char` 作为存储字符的数据类型。`C/C++` 程序员需要注意，Java 中的 `char` 可能与 `C++` 或 `C` 不同。`C/C++` 的 `char` 宽度为 8 位。然而，Java 没有这种限制。Java 使用使用 Unicode 表示字符。Unicode 是一个完整的字符集，可以表示所有人类语言的所有字符。Unicode 是许多字符集的统一，如拉丁希腊字母、阿拉伯西里尔字母、假名和韩语。完成这项任务需要 16 位。因此，Java `char` 是 16 位的类型。`char` 的范围可以在 0 到 65536 之间。不存在负数字符。

#### 布尔值

Java 支持一种名为 `boolean` 的基本类型，用于逻辑值。它只有两个可能的值：真（true）/假（false）。所有关系运算都返回这种类型，例如 `a < b`。条件表达式（如 `for` 和 `if`）所需的类型是 `boolean`。

```java
// Showcase boolean values.

class BoolTest {
    public static void main(String args[]) {
        boolean b;
        b = false;
        System.out.println("b is " + b);
        b = true;
        System.out.println("b is " + b);

        // A boolean value may control the if statem
        if(b) System.out.println("This is executed.");
        b = false;
        if(b) System.out.println("This is not executed.");

        // The result of a relational operation is a boolean number
        System.out.println("10 > 9 is " + (10 > 9));
    }
}
```

### 浮点数字面量

浮点数是包含小数部分的十进制。它们可以以科学计数法或标准记法表示。标准记法由整数部分组成，后面跟着一个小数点和一个小数部分。`2.`、`3.14159`、`0.6667` 和 `0.6667` 都是标准记法下有效的浮点数。标准记法浮点数带有一个指定 10 的幂次的后缀，即该数字在科学计数法中应该乘以倍数。`E` 或 `e` 后面跟着小数点，该数可以是正的也可以负。

### 动态初始化

之前的示例使用了常量作为变量的初始化器，而 Java 允许声明的变量使用声明时有效的任何表达式进行动态初始化。这里有一个示例程序，它根据直角三角形对边的长度来计算斜边的长度。

```java
// Demonstrate dynamic initialization.

class DynInit {
    public static void main(String args[]) {
        Double a = 3.0, double b = 4.0;
        // c 是动态初始化的
        Double c = Math.sqrt(a* a + b* b);
        System.out.println("Hypotenuse is " + c);
    }
}
```

### 类型转换与强制类型

你可能有一些编程经验。将一种类型的值赋值给另一个类型的变量是非常常见的。如果类型兼容，Java 会自动进行类型转换。例如，可以将 `int` 值赋值给 `long` 变量。但并非所有类型都是兼容的，因此并不是所有的类型转换都可以被隐式允许。例如，没有从 `double` 到 `bytes` 的自动转换。可以在不兼容类型之间进行转换。强制转换用于在不兼容类型之间进行转换。让我们来看强制转换和自动类型转换。

## 第 3 章：运算符

### 基础算术运算符

基础算术运算——加、减、乘、除——对于所有数值类型，其行为都符合你的预期。还有一种减运算符的一元形式，用于将其一个操作数取反。当除法运算符应用于整数类型时，其结果将不包含小数部分。

```java
// Demonstrate basic arithmetic operators.

class BasicMath {
    public static void main(String args[]) {
        // 整数算术运算
        System.out.println("Integer Arithmetic");
        int a = 1 + 1;
        int b = 3;
        int c = 4;
        int d = c - a;
        int e = -d;
        System.out.println("a = " + a);
        System.out.println("b = " + b);
        System.out.println("c = " + c);
        System.out.println("d = " + d);
        System.out.println("e = " + e);

        // 浮点数算术运算
        System.out.println("\nFloating Point Arithmetic");
        double da = 1 + 1;
        double db = da * 3;
        double dc = db / 4;
        double dd = dc - a;
        double de = -dd;
        System.out.println("da = " + da);
        System.out.println("db = " + db);
        System.out.println("dc = " + dc);
        System.out.println("dd = " + dd);
        System.out.println("de = " + de);
    }
}
```

### 取模运算符

取模运算符 `%` 返回除法运算的数。该运算符可以用于浮点类型和整数类型。这个示例程序演示了 `%`。

```java
// Demonstrate % operator.

class Modulus {
    public static void main(String args[]) {
        int x = 42;
        double y = 42.25;
        System.out.println("x mod 10 = " + x % 10);
        System.out.println("y mod 10 = " + y % 10);
    }
}
```

该程序在运行时将产生以下输出：

```
x mod 10 = 2
y mod 10 = 2.25
```

### 位运算符

Java 有若干种位运算符，可以用于整数类型 `long`、`int`、`short`、`char` 和 `byte`。这些运算符能够对单个操作数的位进行操作。

#### 位逻辑运算符

`|`、`^` 和 `~`。下面的表显示了每个操作的结果。接下来的表显示了每个操作的输出。

##### 位取反

位补码也称为一元非 运算符。它反转所有位。

##### 无符号右移

位运算符 `>>>` 用于移位。Java 的无符号右移会在高位补零。

### 短路逻辑运算符

Java 有两种在其他语言中不存在的布尔运算符。这些被称为短路。`OR` 运算符当 `A` 为真时返回真。`AND` 运算符当 `A` 为假时返回假。

## 第 4 章：控制语句

### Java 选择语句

Java 支持两种选择语句：`switch` 和 `if`。这些语句可以根据运行时才知道的条件控制程序的执行。这些语句的力量和活性会让你惊讶。

#### If

在第 2 章中引入了 `if` 语句。本章将详细介绍它。Java 的条件分支语句是 `if` 语句。它可以用于引导程序的执行路径。这是 `if` 语句的通用形式：

```java
语句 1; if (条件)
其他语句 2
```

### 迭代语句

Java 的迭代语句有 `for`、`do-while` 和 `while`。这些语句创建循环，我们称之为循环。循环在达到终止条件之前执行相同的指令。Java 提供了一种满足任何编程需求的循环。

#### While

最基本的 Java 循环语句是 `while` 循环。当控制表达式保持为真时，它重复执行块或语句。这是它的通用形式：

```java
while(条件)
{// 循环体}
```

### 循环的一些变体

`for` 循环有许多变体，可以增加它的力和实用性。它是灵活的，因为它的三个部分——初始化和条件测试以及迭代——简单可以用于任何目的。`for` 的三个部分可以用于你想要的任何目的。

```java
boolean done = false;
for(int i=1; !done; i++) {
    if(interrupted()) done = true;
}
```

### for-each 循环变体

JDK 5 引入了 `for` 的第二形式，实现了一种被称为“for-each”的循环样式。for-each 概念正成为现代编程语言中的预期特性。foreach 循环设计用于按顺序遍历对象集合，例如数组中的元素。Java 不像 C# 使用 `foreach` 关键字来实现 foreach 循环。Java 增强了 `for` 语句以添加 for-each 功能。

### 使用 BREAK 退出循环

`break` 可用于强制终止循环。它会跳过条件表达式以及循环体中剩余任何代码。如果在循环内部发现 `break` 语句，它将终止循环，程序控制将恢复到循环后的下一条语句。这里有一个示例：

```java
// Use break to exit a loop.
class BreakLoop {
    public static void main(String args[]) {
        for (int i = 0; i < 100; i++) {
            if (i == 10) break; // 如果 i 等于 10 则终止循环。
            System.out.println("i: " + i);
        }
        System.out.println("Loop complete.");
    }
}
```

#### 作为 GOTO 形式的 BREAK

`break` 语句可以用于创建 `goto` 语句的“文明版本”。它在循环和 `switch` 语句中也很有用。Java 没有 `goto` 子句，因为它允许你以一种无结构化且任意的方式进行分支。这使得理解和维护充满 `goto` 的 Java 代码变得困难。这同时也阻止了某些编译器的优化。然而，在某些情况下，`goto` 对于流程控制是有用且合法的。当你需要退出一组复杂的循环时，`goto` 是很有用的。Java 提供了扩展形式的 `break` 语句来处理这些情况。这种形式的 `break` 允许你跳出一个代码块。这些块不需要必须在循环中，它们可以是任何类型的块。

#### CONTINUE

有时候，强制提前进行循环迭代是很有用的。这意味着你可能希望继续运行循环，但不处理循环体内的其余代码。这本质上是一个直接跳到循环体末尾的 `goto`。这是通过 `continue` 语句实现的。`continue` 语句允许控制转移到 `while` 和 `do-while` 循环中控制循环的条件表达式。`for` 循环控制转移到 `for` 语句的条件表达式和迭代部分。对于这三种循环，任何中间代码都会被忽略。

## 第 5 章：继承

### 继承

#### 基础



# 继承与异常处理

## 继承基础

你可以仅通过使用 `extends` 关键字将一个类的定义包含在另一个类中来继承一个类。让我们来看一个简单的示例来展示如何操作。这个程序创建了一个父类 `A` 和子类 `B`。你可以看到如何使用 `extends` 关键字来为 `A` 创建子类。

```java
// An example of inheritance.
// Create a Superclass.
class A {
    int i, j;
    void showij() {
        System.out.println("i and j: " + i + " " + j);
    }
}

// 通过扩展类 A 创建 A 的子类。
class B extends A {
    int k;
    void showk() {
        System.out.println("k: " + k);
    }
    void sum() {
        System.out.println("i+j+k: " + (i + j + k));
    }
}
```

### 成员访问与继承

子类可以访问其父类的所有成员，尽管它包含了整个父类。然而，被声明为 `private` 的父类成员无法被子类访问。考虑以下类层次结构示例：

私有成员不包含在类层次结构中。它们在各自的类中是私有的。这个程序有一个错误。请编译。

```java
/*
// Create a Superclass.
class A {
    int i; // 默认 public
    private int j; // private A
    void setij(int x, int y) {
        i = x;
        j = y;
    }
}

// A 的 j 在这里不可用。
class B extends A {
    int total;
    void sum() {
        total = i + j; // 错误 j 在这里不可用
    }
}

class Access {
    public static void main(String args[]) {
        B subOb = new B();
        subOb.setij(10, 12);
        subOb.sum();
        System.out.println("Total is " + subOb.total);
    }
}
```

### 父类变量可以引用子类对象

任何派自父类的子类都可以拥有父类中引用变量的引用。继承的这一方面在许多情况下非常有用。考虑以下内容：

```java
class RefDemo {
    public static void main(String args[]) {
        BoxWeight weightbox = new BoxWeight(3, 5, 7, 8.37);
        Box plainbox = new Box();
        double vol;
        vol = weightbox.volume();
        System.out.println("Volume of weightbox is " + vol);
        System.out.println("Weight of weightbox is " + weightbox.weight);
        System.out.println();

        // 将 BoxWeight 引用赋值给 Box 引用
        plainbox = weightbox;
        vol = plainbox.volume(); // OK，volume() 在 Box 中定义
        System.out.println("Volume of plainbox is " + vol);
        /* 此语句由于 plainbox 而无效
           它没有确定 weight 成员。 */
        // System.out.println("Weight of plainbox is " + plainbox.weight);
    }
}
```

### SUPER

任何派自父类的子类都可以拥有父类中引用变量的引用。继承的这一方面在许多情况下非常有用。考虑以下内容（见上面的代码）。

上述示例中的 `super` 构造函数实现没有达到理想。`super` 显式地设置了 `BoxWeight` 的宽度、高度、深度字段。当子类需要初始化这些变量时，这是必要的。

### 创建多级层次结构

我们已经使用了简单的层次结构，它们只由一个父类和一个子类组成。你可以创建任意层数的层次结构。使用另一个类的子类作为父类是可以接受的。如果你有三个类 `A`、`B` 和 `C`，那么 `C` 可以是子类的子类。这种情况意味着每个子类都继承父类的所有特征。`C` 继承了来自 `A` 和 `B` 的所有方面。以下程序说明了多级层次结构的用处。

### 构造函数的调用

当类层次结构被创建时，构造函数按什么顺序被调用？如果 `A` 是 `B` 的子类，且 `B` 是父类，那么 `A` 的构造函数是如何调用的？反之如何？在类层次结构中，构造函数是从父类到子类的顺序调用的。`super()` 必须在子类构造函数首先执行。如果没有使用 `super()`，每个父类的默认或无参数构造函数将被执行。

## 异常处理

Java 异常是描述代码段中异常（或错误）情况的对象。当发生异常情况时，会创建一个异常对象，并在导致该异常的代码中将其抛出。创建异常的方法可以处理它，也可以将其传递。在任何情况下，异常都会被捕获并处理。你可以通过 Java 运行时系统生成异常，也可以通过你的代码手动生成。Java 在发生根本错误时会抛出异常。这些异常可能是由于违反 Java 语言规则或 Java 执行环境的限制而引起的。最常见的是，手动生成的异常用于通知方法调用者错误情况。

### 异常类型

所有异常类型都是内置类 `Throwable` 的子类。`Throwable` 是异常类层次结构中的最高级。紧接 `Throwable` 下的两个子类将异常分为不同的分支。`Exception` 引导一个分支。该类用于用户程序必须捕获的特殊情况。你也可以通过派生该类来创建自定义异常类型。`RuntimeException` 是 `Exception` 的子类。这些异常为你的程序自动创建，包括无效的数组索引和除以零。

### 异常

在学习如何在程序中处理异常之前，了解在不处理异常时会发生什么是很重要的。此程序包含一个导致除以零错误的表达式。

```java
class Exc0 {
    public static void main(String args[]) {
        int d = 0;
        int a = 42/d;
    }
}
```

### TRY 和 CATCH

Java 运行时系统的默认异常处理器对于调试非常有用，但你可能想手动处理任何异常。这样做有两个好处：它允许你纠正错误；它防止了程序自动终止。如果程序每当发生错误就停止运行并打印堆栈跟踪信息，将让大多数用户感到困惑。这很容易避免。你只需通过将你想要监控的代码包含在 `try` 块中，就可以防止并管理运行时错误。在 `try` 块之后紧跟一个 `catch` 子句，并指定你想要捕获的异常类型。

### 显示异常描述

`Throwable` 重写了 `toString()` 方法（定义在 `Object` 中）。它返回一个包含异常描述的字符串。可以通过将异常作为参数传递给 `println()` 语句来显示此描述。这是一个关于如何重写之前程序中 catch 块的示例。

```java
catch (ArithmeticException e) {
    System.out.println("Exception: " + e);
    // 设置 a = 0 以继续
}
```

当程序中使用此版本时，每个发生的除以零错误都会显示此消息。

`Exception: java.lang.ArithmeticException: / by zero`

### 多个 catch 子句

有时，一个代码块可能会引发多个异常。这种情况可以通过指定多个 `catch` 子句来处理，每个子句捕获不同类型。在异常抛出后执行的每个 `catch` 语句都会按顺序检查。一旦执行了某个 `catch` 语句，其他都会被忽略，并在 `try/catch` 块之后继续执行。

### 嵌套 try 语句

你可以嵌套 `try` 语句。一个 `try` 语句可以放在另一个 `try` 块内部。每当进入一个 `try` 时，异常的上下文就会添加到栈中。如果内部 `try` 语句的异常没有对应的 `catch` 处理器，栈将回溯。将检查下一个 `try` 语句的 `catch` 处理器是否匹配。该过程一直持续，直到其中一个 `catch` 短句成功或所有的嵌套尝试语句都已耗尽。如果没有匹配的 `catch` 语句，Java 运行时系统将处理该异常。

### Java 内置异常

Java 在标准包 `java.lang` 中定义了许多异常类。这些异常类中的几个已经在示例中介绍。这些异常可以是 `RuntimeException` 的子类或变体，它是最常见的。如之前所述，这些异常不需要添加到任何方法的 `throws` 中。这些异常在 Java 中被称为未检查异常。这是因为编译器不会检查方法是否处理了这些异常。表 10-1 列出了 `java.lang` 中的未检查异常。表 10-2 列出了 `java.lang` 定义的必须包含在方法 `throws` 列表中的异常。这些被称为已检查异常。Java 还定义了与其类库相关的其他类型的异常。

# 第 7 章：字符串处理

## 字符串构造函数

`String` 类有几个构造函数。你可以调用默认构造函数来创建一个空的 `String`。

```java
String s = new String();
```

创建的 `String` 将不包含任何字符。

你经常需要创建带有初始值的字符串。这可以通过 `String` 类提供的帮助来实现，该类提供了许多构造函数。下面所示的构造函数可以创建一个用字符数组初始化的 `String`。

`String(char chars[])`

示例：

```java
char chars[] = {'a', 'b', 'c'};
String s = new String(chars);
```

## J2SE5 采用的字符串构造函数

J2SE 5 为 `String` 有两个构造函数。这是第一个支持扩展 Unicode 字符的构造函数，所示：

`String(int codePoints[], int startIndex, int numChars)`。

`codePoints` 是一个包含 Unicode 代码点的数组。使用从 `startIndex` 开始并运行 `numChars` 个的范围来创建字符串。

第二个构造函数与 `StringBuilder` 类兼容。所示：

`String(StringBuilder strBuildObj)`。

这会根据 `strBuildObj` 创建一个字符串。

## 字符串长度

字符串的长度是指它包含的字符数。可以使用 `length()` 获取此值，所示：

`int length()`

由于字符串 `s` 中有三个字符，下面的片段将打印 "3"。

```java
char chars[] = {'a', 'b', 'c'};
String s = new String(chars);
System.out.println(s.length());
```

## 特殊字符串操作

字符串是编程的重要部分，因此 Java 在语法中为字符串操作提供了特殊支持。这些操作包括从字符串字面量自动创建 `String` 实例，以及使用 `+` 运算符拼接多个 `String` 对象。它们还允许将数据类型转换为 `String` 表示。Java 通过显式方法执行所有这些功能，但 Java 使程序员变得更加方便并增加了清晰度。

## 字符提取

可以使用 `String` 类通过多种方式从 `String` 对象中提取字符。我们将检查每一种。`String` 对象中的字符不能像字符数组那样索引。然而，许多 `String` 方法使用字符串的偏移量（或索引）来执行操作。String 索引从零开始，数组数组。

你可以使用 `charAt()` 方法从 `String` 中提取一个字符。其通用形式为：

`char charAt(int where)`

`where` 是你所需的字符的索引吗？`where` 值不能为负，应指定字符串内的某个位置。`charAt()` 返回指定位置的字符。例如：

```java
char ch;
ch = "abc".charAt(1);
```

值 "b" 被赋值给 `ch`。

## 字符串搜索

`String` 类可以使用两个方法在字符串中搜索特定字符或子字符串。

* `indexOf()` 搜索首次遇到的子字符串或字符。
* `lastIndexOf()` 搜索过去出现过的字符或子字符串。

这两种方法都可以以多种方式进行重载。这些方法返回字符或子字符串出现的索引。如果方法执行失败，则返回 -1。

### 搜索方法

使用此搜索工具查找特定字符的首次出现的位置。

```java
int indexOf (int ch)
```

使用此工具查找字符最后一次出现的位置。

```java
int lastIndexOf (int ch)
```

在这里，`ch` 代表要查找的字符。

使用此方法搜索首次或最后一次位置的子字符串。

```java
int indexOf (String str)
int lastIndexOf (String str)
```

### 使用 VALUEOF () 进行数据转换

`valueOf()` 是一个方法，它可以将数据从内部格式转换为人类可读的格式。它是一个静态方法，加载在 `String` 类中，适用于 Java 的所有内置类型。这使得每个 Java 类型都能被正确地转换为字符串。`valueOf()` 也加载了 `Object` 类型，因此你创建的任何对象都可以作为参数。（请记住 `Object` 是所有类的超类。以下是它的几种形式的示例：）

```java
static String valueOf(double num)
static String valueOf(long num)
static String valueOf(Object ob)
static String valueOf(char chars[ ])
```

### STRINGBUILDER

J2SE 5 为 Java 令人叹的字符串处理能力引入了一个新的字符串类。`StringBuilder` 就是这个新类。它与 `StringBuffer` 相同，但不是同步的。这意味着它不是线程安全的。`StringBuilder` 的性能更快。在多线程场景下建议使用 `StringBuffer`。
