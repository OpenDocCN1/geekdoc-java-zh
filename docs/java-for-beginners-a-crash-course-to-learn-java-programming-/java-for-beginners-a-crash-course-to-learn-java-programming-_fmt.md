
# Java 初学者指南：一周掌握 Java 编程的快速成课程

## 远程运行和执行代码

## 面向对象编程

面向对象编程语言（OO）有许多解释方式，取决于语言本身。对于 Java 而言，支持这一说点的主要组件是将代码和数据结合成实体对象的能力。

通过这种方式，Java 将代码与数据分离，或将发生变化的事与不发生变化的事分离。这有助于稳定大型项目，否则如果没有实现这一点，这些项目的质量可能会降低。基本上，这是一种简化大型且复杂项目的方法。

面向对象语言的另一个伟大用处是，对象可以变得更通用，因此即使不重新编写，也可以在不同的项目中使用它们。这有助于通过重用原本需要更长时间编写的对象来更快地构建大型项目。Java 面向对象的其他特性还包括：

- 结构清晰，易于程序员理解
- 通过使用 DRY（不要重复自己）原则有助于维护代码的可访问性
- 重用应用程序，缩短了创建时间

## 在多个操作系统上执行

这是 Java 编程的一项非常出色的特性，因为它允许任何用 Java 编写的代码都能轻松地运行在另一个操作系统上。这是通过编译特定的 Java 字节码实现的，这些字节码可以被视为“半成品”代码，并允许在其他操作系统上运行时进行平滑过渡。存在某些编译器实现可以将代码编译为原生机器代码，从而去除了中间的字节码阶段。

## 自动内存管理

这一特性允许程序员避免进行手动内存管理，而这在某些编程语言中是非常常见的。这种做法的问题在于，如果程序员忘记了或没有及时执行，就会发生内存泄漏。当这种情况发生时，程序将消耗不必要的内存。还可能出现内存被分配两次的情况，这会导致程序崩溃。

## 社区支持

由于其开源特性，Java 提供了极大的社区支持，在问题出现时能够迅速做出响应。通常，社区是非常开放的，并根据你的技能接受任何人，而且他们倾向于结成小组来尝试解决问题或教教他人如何编写 Java 编程。

## 卓越的应用程序编程接口

这些应用程序接口（也称为 API）帮助开发者和程序员使用许多不同的工具创建应用和其他软件。然而，它最棒的一点是，开发者在实现内部代码结构时，并不一定需要感知这些 API。这意味着 API 具有正确的兼容性，可以在各种不同的代码中良好运行。

拥有超过 4000 个 API，开发者可以从许多不同的需求中进行，这使得该语言具有极大的灵活性。

## 文档支持

与其他编程语言相比，使用 Javadoc 扩展你的 Java 编程知识极其简单。这部分文档让开发者和程序员使用 Java 进行编码变得容易得多。

Java 无疑是世界上最广泛使用的编程语言之一，上述理由证明了这一点。它拥有强大的社区支持和良好的编程文档，让你能够扩展对可能面对的任何问题的知识和理解。

它还有许多 API 允许你为应用程序和程序添加许多功能，以便你按照自己的意图进行操作并发挥创意。

## 安全性

Java 是一种非常安全的编程语言，主要因为它不使用显式指针。这些在其他编程语言中常见的显式指针，意味着程序员在执行某些语句时必须显式地定义游标。通过不使用指针，内存区域无法被直接访问。

另一个大点是，Java 运行在虚拟机沙箱上。JRE（Java运行环境）提供了将类（也称为类加载器）加载到 JVM（Java虚拟机）的能力。这意味着类包与网络分离，降低了被他人访问的风险。

## 多线程

多线程环境允许 Java 程序将大任务分解为小任务，并允许程序不为每个运行的线程提供内存。

## 核心概念

在我们深入 Java 编程世界之前，有几个概念你应该了解，以便你理解 Java 更基础的概念。

### Java 是一种非常安全的编程语言，主要因为它不使用显式指针。这些在其他编程语言中常见的显式指针，意味着程序员在执行某些语句时必须显式地定义游标。通过不使用指针，内存区域无法被直接访问。

另一个大点是，Java 运行在虚拟机沙箱上。

```java
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

## 类与对象的区别

在 Java 中，类是对象的模板或蓝图，对象是类的实例。你可以想象类是建筑的设计图，而对象是根据设计图建造的房子。

```java
class Dog {
    String name;
    void bark() {
        System.out.println(name + " says woof!");
    }
}

// 使用类
Dog myDog = new Dog(); // 创建对象
myDog.name = "Buddy";
myDog.bark();
```

## 继承

继承允许一个类（子类）获得另一个类（父类）的属性和方法。这促进了代码复用。

```java
class Animal {
    void eat() {
        System.out.println("This animal is eating.");
    }
}

class Dog extends Animal { // Dog继承 Animal
    void bark() {
        System.out.println("The dog is barking.");
    }
}
```

### 多态

多态允许不同类对同一个方法调用有不同的反应。

```java
Animal myDog = new Dog(); 
myDog.eat(); // 调用父类的方法
```

### 异常处理

Java 使用 `try-catch` 块来处理异常，防止程序崩溃。

```java
try {
    int data = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("不能以零除");
}
```

注释（comments）和打印（print）的区别在于，注释不会显示在你的编辑器或终端上。

要复习这一节，你只需要记住使用 `//` 添加单行注释，通过使用 `/* */`，你可以按顺序编写多行注释。

## 类 (Class)

尽管我们将在接下来的章节中详细介绍类，但我们将粗略解释一下它是什么，以便你理解这里的操作过程。类是一个概念，在这种情况下，是一个单一的概念（目前让我们把它想成一个单一的概念即可）。Java 中的每个程序都必须有一个类，且该类的名称必须与程序名称相同。

在我们的示例中，类是 `HelloWorld`。这意味着该类必须在一个名为 `HelloWorld.java` 的文件中声明。

## 编译器 (Compiler)

编译器的基本功能是将人类友的代码翻译成计算机可以处理的语言。

编译意味着运行程序。当你编译程序时，类会被转换为一个以 `.class` 结尾的文件，也称为字节码。然后，你可以使用 Java 虚拟机（或 JVM）来运行代码。

安装好 JVM 后，你可以打开终端或命令行窗口，进入你保存 Java 程序的目录。输入以 `.java` 结尾的程序名称并按回车编译代码。

之后，你应该能看到 `.class` 文件的出现，假设你的代码中没有错误。

通常，或者至少在你学习期间，编译器可能会为你运行程序；然而，当你离开平台开发环境工作时，编译器可能会运行也可能不会，你需要知道自己犯了哪些错误。Java 编译器通常在计算机开始运行代码之前就能理解代码中可能出错的地方。

例如，如果你有一个名为 `Compiling.java` 的文件，我们可以在终端上使用命令来编译它：

```
javac Compiling.java
```

如果没有错误，编译器将创建一个 `.class` 文件。因此，可以使用使用终端命令执行此 `Compiling.class`：

```
java Compiling
```

如果你的代码中存在错误，则不会创建 `.class` 文件，你必须修复错误并运行命令来创建 `.class` 文件。

如果编译器运行且没有错误，它将创建一个可执行的 `.class` 文件。这意味着你可以从终端运行程序。

这是一个 `.java` 文件和 `.class` 文件的示例。假设我们有以下代码：

```
public class Compileandecutable.java {
    public static void main(String[] args) {
        System.out.println("These are the differences");
    }
}
```

我们可以通过添加命令来编译此程序：

`javac Compileandecutable.java`

如果一切顺利且你没有犯任何错误，这意味着你的程序编译成功了。这也意味着你应该有两个不同的文件：

Compileandecutable.class。这是这是我们未编译的代码文件，可以由 JVM 执行。只需使用命令 `java Compileandecutable` 即可执行此程序。

## 空格与分号 (Whitespace and Semicolons)

这些是程序忽略的代码之间的行和空格。这样做是为了让朋友或同事等其他人能够轻松解释代码。通过添加空格，你让代码易于理解。这样的示例如下：

```
System.out.println("You can write whatever you want here");
System.out.println("As you can see, there’s a space between line codes");
```

在运行程序后，看到的应该如下所示：

You can write whatever you want here.

如你所见，代码行之间有一个空格。

但在输出中，你不会看到所写内容之间有任何行或空格，因为它们被程序忽略了。

分号由程序读取，它宣告一个句子或语句的结束。然而，当你添加大括号时，不需要添加分号。

## 语句 (Statements)

语句是执行一项任务的代码行。为了确保没有错误，如上述所示，所有语句都应该以分号结尾。

```
System.out.println("Hello World");
```

如我们的示例所示，你需要使用分号让程序知道语句已结束。

## 第 2 章：变量

尽管 Java 是面向对象的语言，但并不是所有类型都是对象。基本数据类型（Primitives）是语言构建的基础性变量。这些基本数据类型包括：

- byte（整数，1 字节）
- short（整数，2 字节）



## Java 基本数据类型

- `int`（整数，4 字节）
- `long`（整数，8 字节）
- `float`（浮点数，4 字节）
- `double`（浮点数，8 字节）
- `char`（字符，2 字节）
- `boolean`（真或假）

在本章中，我们将详细介绍变量在 Java 编程中的重要性，变量如何帮助我们在 Java 中实现目标，以及不同的变量类型，还有我们如何操作变量并在代码中使用它们来执行不同的任务。

Java 变量是数据的容器，允许你在运行代码时保存值。每种数据类型都有一个对应的变量，说明了该变量可以存储的数据值的数量和类型。

换句话说，变量是程序运行时任何内存位置的名称，它也是 Java 编程中存储测量的最基本单位。

变量是程序中的信息。一旦我们为这些信息命名，以后就可以用该名称来访问它们。

在使用任何变量作为内存位置之前，你首先需要声明它们，而且在程序执行期间，你可以更改变量。

## 声明变量

但声明变量是什么意思呢？声明编程术语意味着创建某些东西，在这种情况下就是创建变量。

在 Java 编程中声明变量时，你需要注意两个不同的点：

- 赋予变量的名称，称为 **Dataname**（数据名）。
- 可以存储在该特定变量的数据类型，称为 **Datatype**（数据类型）。

在这个示例中，我们有一个程序试图通过约会应用连接人们。

```java
// 数据类型和数据名
int age;
double placelocation;
boolean employed;
```

正如我们所见，我们将变量命名为 "age"、"placelocation" 和 "employed"。然而，我们还没有为它们关联任何值。为了做到这一点，我们需要像这样使用 `=` 运算符：

```java
int age = 30;
```

现在我们已经将 `age` 变量关联到值 `30`。这些也被称为字面量（literals），因为它们有固定的值。

```java
public class datingApp {
    public static void main(String[] args) {
        int age = 30;
        System.out.println(age);
    }
}
```

因为我们把变量 `int` 与 `30` 标识起来，如果我们想打印这一行，只需要写 `age`，程序就会获取该信息。

正如我们所看到的，变量的类型可以是我们上面写的任何基本数据类型之一，例如 `String`、`int` 或 `double`。虽然你可以给变量起任何喜欢的名称，但记住它是区分大小写的，要给这些变量赋值，你需要使用等号运算符 `=`。再给你提供几个例子：

### 示例 1

```java
String name = "Anthony";
// 记得加上带有 "" 的语法
System.out.println(name);
// 这将打印 Anthony
```

### 示例 2

```java
int myNumber = 34;
System.out.println(myNumber);
```

### 示例 3

```java
double myHeight = 1.70;
System.out.println(myHeight);
```

### 示例 4

```java
int houseNumber = 4;
houseNumber = 7;
System.out.println(houseNumber);
```

## long 类型

这些整数数据类型仅在你需要使用超出 `int` 范围的变量时使用，范围在 `-2,147,483,648` 到 `2,147,483,647` 之间。`long` 可以存储从 `-922337203685477808` 到 `922337203685477807` 之间的值。这比 `int` 消耗多得多的内存。在使用这些数据类型时，另一个需要了解的重要点是，你需要在数值后面加上一个 `L`。例如：

```java
long aNumber = 200000000000L;
System.out.println(aNumber);
```

## 浮点类型

当你想要使用像 `5.99` 甚至 `78.9987` 这样的小数时，你需要使用浮点数据类型。

### Float 类型

这些浮点数据类型能够存储从 `3.4e-038` 到 `3.4e+038` 之间的分数。然而，你需要在数值后面加上一个 `f`。记住这些都是区分大小写的。例如：

#### 示例 1

```java
float myHeight = 170.56f;
System.out.println(myHeight);
```

#### 示例 2

```java
float highNumber = 3.4e+038f;
System.out.println(highNumber);
```

### Double 类型

和 `int` 一样，`double` 是 Java 编程中最常用的其他变量，而且在分配小数时也是最常用的。

`double` 可以同时存储极大的数字、极小的数字，也可以存储小数。`double` 能够存储的最大值是 `1.707,693,134,862,315,7E+308`，最小值为 `4.9E-324`，这包含了 324 位小数。以下是声明 `double` 变量的方法：

#### 示例 1

```java
// 带有小数的 double，例如价格
double price = 7.99;
```

```java
// 也可以存储非常大的数字
double worldPopulation = 7900000000;
```

#### 示例 2

```java
public class WorldsPopulation {
    public static void main(String[] args)
    {
        double worldpopulation = 7.9;
        System.out.println(worldpopulation);
    }
}
```

结果将是 `7.9`。

`float` 和 `double` 原始类型最大的区别是 `float` 可以存储 7 位小数，而 `double` 可以存储大约 15 位小数。因此，在进行计算时，使用 `double` 比 `float` 更“安全”，因为如果结果超出了 `float` 变量的范围，就会产生错误。

## 科学计数法

如果我们使用 `e` 来表示 10 的幂次，就可以在代码中使用科学计数法。例如：

```java
float x = 25e5f;
double y = 13E4;
System.out.println(x);
System.out.println(y);
```

## Boolean 类型

并不是所有东西都是数字，有时程序必须回答其他内容，如“是”或“否”。

我去杂货商店了吗？你给植物浇水了吗？你洗车了吗？这些问题都无法用数字回答，而可以使用 `boolean` 数据类型，它可以存储两个值之一：`true`（真）或 `false`（假）。

为了声明这些变量，我们需要在变量之前写入 `boolean` 关键字：

### 示例 1

```java
boolean didyoucleanthecar = false;
boolean didyouwatertheplants = true;
```

### 示例 2

```java
boolean youHavingFun = true;
boolean goodWeatherOut = false;
System.out.println(youHavingFun);
System.out.println(goodWeatherOut);
// 这些内容的输出分别为 "true" 和 "false"。
```

```java
如果我们用整个代码举个例子：
public class Booleans {
    public static void main(String[] args)
    {
        boolean didyoucleanthecar = false;
        System.out.println(didyoucleanthecar);
    }
}
```

这里的结果将打印 `false`。

这类原始类型通常用于条件测试。我们将在书的后面部分介绍它们。

## Char 类型

再次，变量并不都是数字。你如何回答一个既不是数字也不是真也不是假的问题？有些问题需要用字符、标点符号甚至空格来回答。这正是 `char`（`character` 字符的缩写）数据类型所包含的。然而，与我们目前为止看到的任何变量不同，你需要加上“引号”。像这样：

### 示例 1

```java
char grade = 'B';
char firstlettername = 'R';
char punctuation = '?';
```

这里有一个带有打印输出的完整示例：

```java
public class Char {
    public static void main(String[] args) {
        char gradeYouHad = 'A';
        System.out.println(gradeYouHad);
    }
}
```

预期的打印结果将是 `A`。
这另一种方法，即使用 ASCII 值。

## 非原始数据类型

这些不是原始类型。它们是对象。与原始类型不同，它们拥有可以调用的方法。最常见的非原始类型是 `String`。`String` 是字符序列。你可以通过多种方式创建 `String`：

```java
String greeting = "Hello World";
String greeting2 = new String("Hello World");
```

这两个字符串表示相同的值，但第一种方式更常见。

- 回车符 `\r` 的作用与 `\n` 类似，但它被放置在单词之间，例如：`System.out.println("Hello\rWorld");` // 输出结果为
  ```
  Hello
  World
  ```
- 如果你想在单词之间创建一个更大的间距，可以使用 `\t`，例如：`System.out.println("Hello \tWorld");` // 将输出 `Hello   World`
- 我们还可以使用被称为“退格键（backspace）”的 `\b` 来删除字符：`System.out.println("Hello Wor\bd");` // 输出结果为 `Hello Word`

## 静态检查

如果变量的值不匹配，编译器将不会编译程序，这被称为类型声明错误（declaration bug），因为你声明了一个错误的值。如果发生这种情况，你的程序将会崩溃或给出错误的结果。

静态类型有助于程序员在代码执行之前识别这些错误。如果变量与所赋值值的类型不匹配，程序将无法编译。例如，如果我们用一个 `int` 变量来存储如 `"Hello World"` 这样的字符串，将会出现一个提示类型不兼容的错误，正如我们所见，`int` 类型变量的设计是为了存储某些数字而不是单词。

有时这些错误不会被编译器捕获，因此当运行代码时，它会导致称为运行时错误（runtime errors）的错误。静态类型有助于程序员避免运行时错误。我们将在本书后面学习更多关于不同类型的错误以及如何调试你的代码。

## 命名规范

命名，也称为标识符（identifiers），在编写 Java 程序时是非常重要的一件事。如果你想让你的程序正常运行，就需要正确地命名变量。例如，正如我们提到的，变量名是区分大小写的，因此为了确保你使用正确的变量，你需要注意这一点。变量名的长度虽然没有限制，但为了清晰起见，你应该保持它们的简洁并使用描述性名称，这样你就能快速地理解该变量代表什么。

在创建变量时，只能用字母、`$` 或 `_` 开头。如果你的变量以任何其他符号开头，你的命名将是无效的。另一个需要记住的重要点是，如果你只有一个单词，你应该输入小写字母，但如果你有多个单词，应该以小写字母开头，然后使用大写字母开始句子中的新单词，如下所示：

```java
// 这是正确的
boolean isHeHuman;

// 这是错误的
boolean ishehuman;

// 这也是错误的
boolean IsHeHuman;
```

让我们回顾一下关于如何命名的一些通用规则：

- 命名应以小写字母开头，且中间不能有空格
- 名称只能包含字母、数字、美元符号和下划线
- 名称应该以字母开头，你也可以使用美元符号或下划线，虽然我们暂时不会讨论这些
- 名称是区分大小写的，例如，`MyName` 和 `myName` 是不同的
- Java 关键字不能用于命名变量，例如 `char`、`boolean` 或 `int`

## 类型转换

你可以将某些原始数据类型赋值给其他类型。实现此操作有两种不同的方法：

- **宽类型转换（Widening Casting）** —— 如果你在代码中编写它们，它会自动完成，并将较小的原始类型转换为较大的原始类型。让我们再看一次它们的排序：`byte` > `short` > `char` > `int` > `long` > `float` > `double`
- **窄类型转换（Narrowing Casting）** 是手动完成的，是宽转换的相反：`double` > `float` > `long` > `int` > `char` > `short` > `byte`。

但我们会在代码中表示它吗？宽类型转换可以这样完成：

```java
public class Main {
  public static void main(String[] args) {
    int myInteger = 5;
    double transMyDouble = myInteger;
    // 这会自动进行转换
    System.out.println(myInteger);
    // 输出 5
    System.out.println(transMyDouble);
    // 输出 5.0
  }
}
```

如果我们想在代码中表示窄类型转换，它看起来会是这样：

```java
public class Main {
  public static void main(String[] args) {
    double transMyDouble = 8.65;
    int myInteger = (int) transMyDouble;
    // 我们需要手动进行转换以便将其翻倍
    System.out.println(transMyDouble);
    // 输出为 8.65
    System.out.println(myInteger);
    // 输出为 8
  }
}
```

## 变量操作：运算符

### 变量操作：加法和减法

我们可以操作变量来控制代码中的决策。例如，如果我们有一个银行账户的示例，我们可以轻松地通过 `double` 原始类型来增加余额。但如果我们想从银行账户取款或存款呢？

我们必须操作变量上的值以与我们编写的代码相对应。因为 Java 有对数字进行计算的能力，我们可以更改这些变量。以银行账户的为例，它看起来如下：

```java
// 首先你必须声明初始余额
double balance = 300.50;
// 加上存款
double depositAmount = 20.00;
// 加上计算结果
balance = balance + depositAmount;
```

正如你所看到的，我们可以使用如 `+` 这样的运算符来计算变量。现在，我们将只关注加法。

### 变量操作：乘法和除法

你可以在 Java 中进行乘法和除法。假设你工作了 35 小时，时薪为 $20。

```java
double checkAmount = 35 * 20;
// 你的薪水应该是 700
```

如果你想进行除法，假设工作时长为 100，时薪为 20：

```java
double hoursWorked = 100 / 20;
// 结果应该是 5
```

### 变量操作：取模

取模用 `%` 表示，它的意图是给我们除法的余数。例如，如果你制作了 13 个马芬，并每 3 个一组分，你会剩下多少马芬？你可以分 4 组，剩下一个。

```java
int muffinsMade = 13;
int muffinsLeft = muffinsMade % 3;
// muffinsLeft 为 1
```

如果你想知道一个数字是否被 2 整除（换句话说是偶数），可以使用取模。例如，如果你用取模除一个偶数，你会得到 0；相反如果是奇数，你会得到余数 1。

### 变量操作：复合赋值运算符

复合赋值运算符用于我们在调整变量或在此情况下其值时无需重复编写语法。通过使用 `+=`，我们可以进行算术运算并再次赋值。例如，你在饼干店工作，并想知道任何时候有多少饼干。

```java
int numCookies = 10;
// 现在我们又做了 5 个
numCookies = numCookies + 5;
// 我们会有 15 个
```

正如你所看到的，如果我们想调整饼干的数量，每次都需要写变量 `numCookies`。但是，如果我们使用 `+=`，我们可以这样写代码：

```java
numCookies += 5;
// 我们会有 20 个
```

这种方式，我们只需要写一次 `numCookies`，从而使代码更简单。我们可以在任何运算符中使用复合运算符，如下：

- 减法 (`-=`)
- 乘法 (`*=`)
- 除法 (`/=`)
- 取模 (`%=`)

### 变量操作：运算顺序

Java 编程遵循与任何其他数学运算相同的规则。你可能还记得在学校学习运算时，这些运算有必须遵循的特定顺序，才能得到正确的结果。让我们以这个运算为例：

```java
int num = 6 * (12 - 2) + 6 / 2;
```

如果我们自己在不使用计算器或终端的情况下手动计算，那么运算顺序将是：

括号；幂；取模/乘法/除法；加法/减法。

当运算符处于相同的优先级时，我们首先会执行左侧的运算。这就是我们计算 `int num` 的方式：

首先计算括号：

```java
6 * 10 + 6 / 2;
```

接下来，你要执行的是乘法，方程将看起来像这样：

```java
60 + 6 / 2;
```

根据运算符的顺序，下一个操作是除法。所以我们得到：

```java
60 + 3;
```



`int num` 的值将是 63。

## 变量操作：大于和小于号

通过使用大于 `>` 和小于 `<`（称为关系运算符），我们可以进行布尔比较。让我们再次以银行账户为例，我们想知道在提取现金时，取出的金额是否少于账户中的余额。

```java
double balanceBankAccount = 1000.02;
double amountWithdraw = 500.02;
System.out.println(amountWithdraw < balanceBankAccount);
// 输出将为 true，因为我们取出的金额少于账户余额
```

我们可以利用此来判断是否可以购买某物品，或者银行账户中是否有足够的钱购买。以下是你如何结合大于和小于号使用布尔变量：

```java
double balanceAccount = 1000.02;
double costOfNewBike = 1500;
boolean canBuyBike = balanceAccount > costOfNewBike;
// 结果将为 false，因为自行车的价格高于你账户里的余额
```

## 变量操作：等于和不等于

我们也可以通过 `==` 来判断两个变量是否相同。例如，这可以用来判断你的工资金额是否正确。以下是实现方法：

```java
double wageAmount = 700;
double calculatedWage = 17.50 * 40;
System.out.print(wageAmount == calculatedWage);
// 这将为 true，因为两个变量相等
```

现在，我们可以通过同样的方法来判断两个不同的变量是否相等：

```java
double balance = 150.00;
double amountDeposited = 50;
double balanceAfterDeposit = balance + amountDeposited;
boolean changeBalance = balance != balanceAfterDeposit;
// 这将为 true
```

检查两个变量是否不等的符号是 `!=`。

## 变量操作：大于/小于等于

再次回到工资的例子。我们如何确定收到的工资是否至少达到了预期的金额？在这种情况下，我们使用小于或等于 `<=` 或大于等于 `>=`。代码实现会是这样的：

```java
double wageAmount = 700;
double calculatedWage = 17.50 * 40;
System.out.println(wageAmount >= calculatedWage);
// 在这种情况下，输出将为 true，因为两个变量相等
```

## 变量操作：.equals()（与字符串方法中的 equals() 内容非常相似）

只对基本类型使用运算是合理的。你可能会认为对字符串使用运算是不起的，因为没有数字可以进行任何运算。但我们仍然可以使用算术运算，在这种情况下使用 `.equals()` 方法来判断两个字符串是否相同。这是一个比较两个对象的方法，因此我们不使用目前为止使用的运算符符号。这是一个示例：

```java
String person1 = "Jack";
String person2 = "Rodri";
String person3 = "Rodri";
System.out.println(person1.equals(person3));
// 这将为 false，因为 "Jack" 不是 "Rodri"
System.out.println(person2.equals(person3));
// 这将为 true，因为 "Rodri" 与 "Rodri"
```

## 变量操作：字符串拼接

到目前为止，我们讨论的运算符只适用于基本类型。但情况并非总是如此，某些运算符也适用于字符串。例如，如果我们想在账户中添加你的名字，可以使用 `+` 将两个字符串相连：

```java
String yourName = "Rodri Sanchez";
System.out.println("Your name is:" + yourName);
```

输出结果为：Your name is: Rodri Sanchez。这被称为字符串拼接。但你可以更进一步，将一个基本类型作为变量，Java 编程将理解它。让我们来看一个简单的银行账户报告示例：

```java
double bankAccountBalance = 250.50;
String message = "Your balance is:" + bankAccountBalance;
System.out.println(message);
```

输出结果为：Your balance is: 250.5。

## 变量操作：final 关键字

我们讨论了变量以及如何操作它们。但事实是，某些变量应该保持不变，例如使用 `final` 关键字来定义常量。如下：

```java
final int weddingDay = 20;
```

如果我们尝试修改，编译器将会报错。

## 变量类型

Java 中有三种类型的变量，它们具有不同的功能：

- 类变量
- 局部变量
- 实例变量

### 类变量

这些类型的变量也被称为静态变量。它们与其他类型的变量相似，但区别在于声明方式。类变量在类内部使用 `static` 关键字，但在块之外。无论你创建多少个对象，静态变量都只有一个副本。

它们在程序开始运行时被创建，并在程序结束时自动删除。因为它们的默认值为零，所以初始化不是强制的。然而，如果我们通过对象访问静态变量，会弹出警告但程序不会停止。相反，编译器会自动将对象名更改为类名。

### 局部变量

如果你可以在构造函数、方法或块中定义变量，那么它就是局部变量。这些局部变量只存在于声明它的块中，这意味着局部变量不会出现在其他块中。

与类变量不同，局部变量在使用前的初始化是强制的，并且在进入块或调用返回函数时创建。

### 实例变量

这些变量在任何块、方法或构造函数之外声明；但它们仍然声明在类中。这些是非静态变量，但与静态变量一样，它们的默认值为零，因此初始化不是强制的。只有通过创建对象，你才能访问实例变量。

## 第 3 章：字符串方法

我们在上一章中提到过字符串，但它们不仅仅是 Java 中的一个对象那么简单。字符串对于 Java 编程非常重要，这就是为什么 Java 有一个专门的 `String` 类，它包含许多可以在编写代码时对我们帮助的方法。此外，你不需要导入任何类，因为它们属于 `java.lang` 包，对于这种编程语言来说是非常基础的。在本节中，我们将介绍 Java 编程中常用的许多 `String` 方法，这些方法将出现在本书的后续章节中。

### toString() 方法

你尝试过打印对象吗？你通常会得到一个随机数字，对吧？例如，如果我们打印上面示例中的一个对象，我们会得到类似 `myCoolMotorcycle@5bc6do78` 的内容，其中 `myCoolMotorcycle` 是对象，而 `5bc6do78` 将是内存中的位置。嗯，这并没有告诉我们关于这辆摩托车的很多信息。但我们可以改变它，让它打印出更多内容和信息。这时 `toString()` 方法就派上用场了。当我们使用这个方法时，我们打印对象，因为我们返回了一个字符串。就像这段代码片段：

```java
class Motorcycle {
    String color;

    public Motorcycle(String motorcyclecolor) {
        color = motorcycleColor;
    }

    public static void main(String[] args) {
        Motorcycle myCoolMotorcycle = new Motorcycle("black");
        System.out.println(myCoolMotorcycle);
    }

    public String toString() {
        return "This is a " + color + " motorcycle.";
    }
}
```

这将带给我们输出：This is a black motorcycle. 因为我们写了 `System.out.println(myCoolMotorcycle)`，这反过来给了我们关于对象 `myCoolMotorcycle` 的信息。

### length()

在 Java 编程中，`length()` 用于返回字符的数量，在这种情况下，即字符串的长度。例如，如果我们有一个名为 `line` 的字符串并想要返回这个字符串的长度，我们会编写 `line.length()`。为了给你举例，请看这段代码：

```java
String line = "Hi there!";
System.out.println(line.length());
```

你认为会打印出什么？如果你猜是 9，那么你是正确的。如果你猜是 8，请记住空格也被算作一个字符。

### concat()

这个字符串方法将一个字符串连接到另一个。这被称为拼接，即将一个字符串的结尾与另一个字符串连接。假设我们有两个名为 `line1` 和 `line2` 的字符串。例如，我们编写了代码：

```java
String word = new String("Alpha");
word = word.concat("Century");
System.out.println(word);
```

系统将打印 "AlphaCentury"。我们在这个示例中所做的是取存储在 `word` 中的字符串对象 "Alpha"，并连接（或者在这种情况下是与新对象拼接），并将这两个单词链接起来。例如，如果我们没有给 `word` 赋值，而是写了以下代码：

```java
String word = "Alpha";
word.concat("Century");
System.out.println(word);
```

我们将只打印 "Alpha"，因为字符串是不可变的，所以我们不能改变它的值。

如果你还记得的话，我们使用 `toString()` 方法来打印对象的名称而不是它的内存位置。我们使用 `concat()`，然后把该 `toString()` 方法的对象连接到我们的第一个字符串上。换句话说，我们不是连接或拼接我们的初始字符串和另一个字符串，我们不是连接它的内存位置，而是 `toString()` 的结果。

### equals() & compareTo()

在变量章节中，我们已经稍微讨论过 `equals()` 方法，但现在我们将进一步完善这个概念。正如你可能记得的，我们不能在字符串中使用任何运算符，因此我们需要 `equals()` 方法。由于我们不能使用运算符，我们需要比较字符串。现在，如果我们想按字母顺序比较两个字符串，我们会使用 `compareTo()`。正如你可能记得，我们需要 `equals()` 来比较两个字符串。例如：

```java
String dog1 = "Rufus";
String dog2 = "Fido";
System.out.println(dog1.compareTo(dog2));
```

如果结果为 0，说明字符串相等。如果结果为负，意味着第一个字符串在第二个字符串之前。如果结果为正，意味着第一个字符串在第二个字符串之后。

### indexOf()

`indexOf()` 方法返回子字符串首次出现的索引。如果找不到子字符串，它返回 -1。例如：

```java
String text = "Hello World";
System.out.println(text.indexOf("World"));
```

输出将是 6，因为 "World" 始于索引 6。

### charAt()

当我们使用 `charAt()` 方法时，我们可以获取指定索引处的字符。例如：

```java
String line = "dog";
System.out.println(line.charAt(1));
```

输出将是 "o"，因为 "o" 在索引 1。

### substring()

记得上面我们使用 `indexOf()` 来打印吗？嗯，如果我们使用 `substring()`，我们可以打印字符串的一部分。例如：

```java
String sentence = "To be, or not be? That is the question.";
System.out.println(sentence.substring(21));
```

输出将是 “That is the question.”因为它从索引 21 开始。如果我们不想输出运行到结尾，我们需要定义结尾。如下：

```java
String sentence = "To be, or not be? That is the question.";
System.out.println(sentence.substring(21, 28));
```

这将类似于：“That is.”正如你可能注意到的，当我们添加两个参数时，第一个包含，最后一个排除。但注意索引 28 不在输出中，所以如果你想切分句子，你需要增加一个数字。例如：

```java
String sentence = "To be, or not be? That is the question.";
System.out.println(sentence.substring(21, 22));
```

我们的结果将是 “T”。

### toUpperCase() & toLowerCase()

有时我们需要返回与代码中大小写不同的字符串值，为此，我们可以使用 `toUpperCase()` 和 `toLowerCase()`。正如你可能已经猜到的，前者返回大写形式的字符串，后者返回小写形式。

```java
String word = "Oh my!";
String uppercase = word.toUpperCase();
// 这将存储字符串 "OH MY!"
String lowercase = word.toLowerCase();
// 这将存储字符串 "oh my!"
```

如果你需要搜索数据库，这非常棒。但一个小小的错误，例如将数据存储为小写而不是大写，会让搜索变得非常困难。请确保正确地使用此功能。

字符串方法是 Java 编程中的一项基本功能，在本章中我们学习了：

- 与不同的字符串方法有关
- 每个字符串方法具体的功能是什么
- 学习了字符串方法的实际应用

## 第 4 章：数组

正如我们之前所过的，我们可以在变量中存储单个数据点，也可以存储一组数据。例如，如果我们需要列出一支足球球队的球员。如果我们为每一位球员都创建一个变量，将会会有很多重复且不必要的代码。当存在长列表时，我们可以使用数组以更简单的方式存储数据。

通过数组，我们可以存储特定数量的值，只要它们的类型是相同的。例如，数组可以存储双精度浮点数、布尔值或字符，以及字符串和对象引用。

数组还被分为索引，其中第一个索引从 0 开始。知道这一点很重要，因为在本章的稍后部分，我们需要通过数组访问索引。因此，第一个索引是 0，第二个是 1，以此类推。

### 创建数组

例如，我们想要跟踪使用程序创建的不同画作的值。为此，我们需要一个画作列表，以及一个与每幅画作关联的不同价格列表。我们需要做的第一件事是声明数组将存储的数据类型，如下：

```java
double[] prices;
```

然后，我们需要添加数组想要包含的数据，在这种情况下是价格。如下：

```java
prices = {220.99, 360.00, 210.00, 500.00};
```

就像其他变量一样，我们可以使用同一行：

```java
double[] prices = {220.99, 360.00, 210.00, 500.99};
```

正如我们所说的，你也可以存储字符串：

```java
String[] paintings = {"blue Sky", "Scarlet Red", "Pinks", "Abandoned"};
```

起初处理字符串时，我们无法正确打印它。为此，我们需要使用与之前相同的方法，但要稍作修改，使用 `Arrays.toString()`。由于这个方法是通过 arrays 包提供的，因此我们需要导入该包。在 Java 中，当我们导入一个包时，我们使该包中的每个方法在我们的代码中都可用。

`Arrays.toString()` 是 arrays 包的一部分，但该包还有许多其他有用方法。以下是当我们使用 `Arrays.toString()` 时发生的情况：

```java
import java.util.Arrays;
// 这是我们用于导入的内容，它必须放在顶部

public class Paintings {
    public static void main(String[] args) {
        double[] paintingPrices = {220.99, 360.00, 210.00, 509.99};
        String betterPrintout = Arrays.toString(paintingPrices);
        System.out.println(betterPrintout);
    }
}
```

打印出来的结果应该是：
[220.99, 360.00, 210.00, 509.99]

现在，我们想要从数组中获取值，因此我们需要从某个索引访问数据。看下这个例子：

```java
double[] prices = {220.99, 360.00, 210.00, 509.99};
```



System.out.println(prices[2]);

它会打印什么数字？如果你认为数字是 210.00，那么你是正确的。记住数组的索引从 0 开始，以元素个数减 1 结束。

相反，如果我们写了 `System.out.println(prices[6])`，我们将得到这样的输出：`java.lang.ArrayIndexOutOfBoundsException`，因为即使我们有五个元素，最后一个索引也是四个。

## 空数组

为了能够创建空数组，我们需要给它们一个固定大小，之后我们可以按照需要填充变量。如下：

```java
String[] paintingItems = new String[6];
```

我们之后无法更改它，因此此数组的大小将始终为 6。之后，我们可以逐个设置不同的索引。或者我们可以一次性分配所有。如下：

```java
String[] paintingItems = {"Blue Sky", "Scarlet Red", "Pinks", "Abandoned", "Ship", "Garden"};
```

或者可以单独完成：

```java
paintingItems[0] = "Blue Sky";
paintingItems[1] = "Scarlet Red";
paintingItems[2] = "Pinks";
paintingItems[3] = "Abandoned";
paintingItems[4] = "Ship";
paintingItems[5] = "Garden";
```

在赋值后，我们允许更改项目的名称，只需修改名称即可。数组的长度可以通过访问数组的长度来查看，如下：

```java
String[] paintingItems = new String[6];
System.out.println(paintingItems.length);
```

在这种情况下，它将打印 0，即使它们像这种情况一样是空的。

## String[] args

你对 `String[] args` 熟悉，因为我们在使用 `main()` 方法时使用了它。由于我们正在学习数组……

```java
public class Hi {
    public static void main(String[] args) {
        System.out.println("Hi " + args[0]);
    }
}
```

## ArrayList

与固定大小的数组不同，`ArrayList` 是动态的。它们根据需要增长或缩小。使用 `ArrayList` 需要你导入 `java.util.ArrayList` 包。

```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
System.out.println(list);
```

//it's the reference to Motorcycle
//now the assortment stores [hi", 3, harley

尽管你可以像这样使用 `ArrayList`，但通常指定类型会更简单、也更常见。

让我们来看看如何使用一个可扩展的 `ArrayList`。这在某些情况下非常有用，例如在线购物。假设你正在在线购物，并在购物车中添加商品。这个购物车会变大，因此为了追踪它，我们必须使用像 `size()` 这样不同的方法。

```java
ArrayList<String> shoppingBasket = new ArrayList<String>();
shoppingBasket.add("Milk Box");
System.out.println(shoppingBasket.size());
//this would print 1
shoppingBasket.add("Ice Cream Tub");
System.out.println(shoppingBasket.size());
//this would print 2
shoppingBasket.add("Tomatoes");
System.out.println(shoppingBasket.size());
//this would print 3
```

那么我们如何访问 `ArrayList` 的索引呢？我们已经看到在数组可以使用中括号访问索引。例如：
`int[] numbers = {2, 4, 6};`
`System.out.println(numbers[2]);`
这会打印数字 6，因为那是索引 2 上的数字。当我们使用 `ArrayList` 时，不能使用括号，而是需要使用方法。`get()` 是我们用于通过 `ArrayList` 访问索引的方法。所以，它看起来像这样：

```java
ArrayList<String> shoppingBasket = new ArrayList<String>();
shoppingBasket.add("Milk Box");
shoppingBasket.add("Ice Cream Tub");
shoppingBasket.add("Tomatoes");
System.out.println(shoppingBasket.get(2));
//this should print out tomatoes
```

正如我们在使用数组时看到的，如果我们使用括号可以更改值：
`String[] shoppingBasket = {"Milk Box", "Ice Cream Tub", "Tomatoes"};`
`shoppingBasket[1] = "Spinach";`
//this means that shoppingBasket now holds ["Milk Box", "Spinach", "Tomatoes"]

然而，当我们使用 `ArrayList` 时，如果想更改一个值，我们需要通过 `set()` 使用不同的方式来实现：
`ArrayList<String> shoppingBasket = new ArrayList<String>();`
`shoppingBasket.add("Milk Box");`
`shoppingBasket.add("Ice Cream Tub");`
`shoppingBasket.add("Tomatoes");`
`shoppingBasket.set(1, "Spinach");`
//this means that shoppingBasket now holds ["Milk Box", "Spinach", "Tomatoes"]

记得我们如何从数组中删除元素吗？我们必须创建一个不包含想要删除的值的新数组。使用 `ArrayList`，如果我们指定要删除的精确索引，就可以删除一个值：
`ArrayList<String> shoppingBasket = new ArrayList<String>();`
`shoppingBasket.add("Milk Box");`
`shoppingBasket.add("Ice Cream Tub");`
`shoppingBasket.add("Tomatoes");`
`shoppingBasket.remove(0);`
//shoppingBasket now has ["Ice Cream Tub", "Tomatoes"]

我们也可以通过指定值本身来删除元素。如下：

```java
ArrayList<String> shoppingBasket = new ArrayList<String>();
shoppingBasket.add("Milk Box");
shoppingBasket.add("Ice Cream Tub");
shoppingBasket.add("Tomatoes");
shoppingBasket.remove("Milk Box");
```

//shoppingBasket now has ["Ice Cream Tub", "Tomatoes"]
我们还可以查找某个元素的索引，或者某个元素可能的位置，例如：
//shoppingBasket stores ["Milk Box", "Ice Cream Tub", "Tomatoes"]

```java
System.out.println(shoppingBasket.indexOf("Milk Box"));
// it would print out 0 because that is the index value of "Milk Box"
```

现在你已经了 `ArrayList` 的基本函数，它允许你创建、添加新项、通过 `size()` 访问其大小、使用 `set()` 更改值，或使用 `remove()` 删除元素。你也可以使用 `indexOf()` 查找 `ArrayList` 中索引的数字。

数组是创建 Java 程序的重要部分。在本章中，我们学习了：

- 数组的作用
- 我们如何创建它们
- 什么是 `ArrayList`
- 我们如何将数组和 `ArrayList` 应用到代码中
- 代码中的 `String[] args` 是做什么的

## 第 5 章：运算符

在关于变量的章节中，我们讨论了基本运算符以及你如何使用它们来操作变量。在本章中，我们将回顾在该章中学到的内容，并加深对 Java 运算符的理解，并发现除了基本操作之外我们还可以用它们做的许多其他事情。

## 方法回顾

正如我们之前看到的，运算符允许我们在变量之间执行操作，例如，将两个变量相加：

```java
int oprt = 50 + 200;
```

尽管我们也可以将变量和值相加，甚至是两个变量，只要它们的类型相同即可：

```java
int oprt = 50 + 200;
//printout would be 250
int oprt2 = oprt + 100;
//printout would be 350
int oprt3 = oprt2 + 200;
//printout would be 700
```

在 Java 编程中，我们可以将不同的运算符分为五组。我们查看了算术运算符，如加法 `+`、减法 `-`、乘法 `*`

我们有赋值运算符，它们通常用于将我们可能有的任何值分配给变量。基本的赋值运算符是 `=`，但你也可以使用 `+=`，在这种情况下，我们将为变量增加一个值。

然后我们有比较运算符，我们在变量章节中已经讨论了几乎所有的运算符，剩下的将在本章中讨论。这些运算符的示例包括等于 `==`、大于 `>`、小于 `<` 或大于等于 `>=`

## 条件运算符

在 Java 编程中有些运算符只使用布尔变量和值。这使得我们更容易理解和编写复杂的布尔关系。这些条件运算符（也称为逻辑运算符）的目标是将多个布尔变量的选择简化为 true 或 false 等简单值。

在某些情况下，你可能只想在所有条件都为假或所有条件都为真时才运行特定的代码和程序。或者，如果你有一个程序除了一个条件之外都是假，而这是程序执行的唯一方式。

另一种情况是，我们需要条件运算符来交换值反之亦然。这看起来可能有点人生畏，但一旦解释了它就会变得容易。让我们遍历所有类型的条件运算符，以便你更好地理解它们在 Java 编程中的作用。

## 条件—与：&&

让我们看看初中足球队招募新球员的情况。为了被球队录取，球员需要平均 GPA 达到 2.7，并且在上个赛季至少进了 5 个球。如果你在代码中写，看起来是这样的：

```java
if(enoughGpa && hasEnoughGoals) {
  //player gets in the team
}
```

被称为与运算符，你需要在两个布尔变量之间使用它。在这个例子中，你需要这两个布尔值都为真才能进入球队。如果两个布尔值都为真，如果其中一个或两个为假，结果将为假。

## 条件—或：||

现在想象，另一所学校如果学生满足两个条件之一就招收他们。你会这样写代码：

```java
if(enoughGpa) {
  //player gets in the team
}
```

```java
if(hasEnoughGoals) {
  //player gets in the team
}
```

如果你不知道 `||` 运算符，你会写这样的代码。看起来是这样的：
`if(enoughGpa || hasEnoughGoals) {`
`  //player gets in the team`
`}`

我们可以在两个布尔值之间使用 `||` 运算符，这意味着只要两个值中至少有一个为真，条件就为真。

有一种被称为短路求值的机制，它只在你使用这两种条件运算符之一时发生。这意味着有时编译器只需要运行第一个布尔值就可以知道结果。例如，如果最终结果需要为真且它有一个 `||` 条件运算符，编译器理解如果第一个条件为真，那么最终结果将为真。相反，如果你运行一个 `&&` 条件运算符并且你需要最终结果为真，而第一个条件为假，编译器就不需要运行另一个条件就可以知道无法执行该代码。

## 逻辑非：!

当你想要相反的结果，或者想在代码中表达清晰的意图时，可以使用此运算符。例如，如果你只需要在某个条件为假时运行代码。你可以这样写：

```java
boolean hasEnoughGoals = false;
if(!hasEnoughGoals) {}
```

## 我们如何组合条件运算符

我们可以使用多个条件运算符来帮助我们扩展表达式。来看这个例子：
```java
boolean rap = true && (false || true)
```

这是我们按照顺序对其拆解的方式：

表达式将首先解决括号内的条件，然后处理非 `!`，接着是 AND `&&`，最后评估 OR `||`。
如果编译器首先求值 `(false || !true)`，结果为 false，我们得到：

- `true && !(false || false)`

然后，它将编译括号内的剩余部分 `(false || false)`，结果为 false。所以现在我们有了：
`true && !false`

编译器将评估的下一个运算符是 `!false && true`，我们将得到：
`true && true`
因此 rap 的值为 true。

当你需要在编码中简化布尔值时，条件运算符是非常用的。所以让我们回顾一下目前为止在本主题中所学到的：

- 条件 - AND（与）用 `&&` 表示，当两个条件都为真时它会运行代码。
- 条件 - OR（或）用 `||` 表示，如果两个布尔值中有一个为真，则为真。
- 逻辑 - NOT（非）用 `!` 表示，当布尔值相反时它运行代码。

运算符是一项主要特性，一旦学会了它们，就能帮助我们创建更复杂的代码。在本章中，我们：

- 回顾了基本运算符以及如何在代码中使用它们
- 描述了什么是条件运算符，例如“AND”、“OR”和逻辑非：!
- 学习了如何组合运算符并让它们在代码中工作

## 第 6 章：语句

为了确保没有错误，所有的语句都应该以分号结束，正如我上面提到的那样。我们从第二章学习了什么是语句，以及它们如何允许我们在编写的代码中执行任务。

在本章中，我们将稍微深入理解语句是什么，以及我们还可以用它们做其他事情。

## 条件语句

- `if` 用于在特定条件为真时指定特定的代码块
- `else` 用于代码块中的条件为假时，或者当相同的条件为假时
- `else if` 用于第一个条件为假，并指定一个新的条件
- `switch` 用于指示要执行的几种替代方案

## if 语句

在本节中，我们将学习控制流以及语句如何管理控制流。以 `if` 语句为例，它挑战表达式并根据答案运行代码。如下：

```java
if(flip == 1) {
    System.out.println("Tails");
}
```

`if()` 存储布尔类型的数据。这意味着如果满足了条件，程序将运行代码。我们在括号之间使用的表达式是一个代码块，如果布尔值为真，代码将运行。例如：

示例 1
```java
boolean isValidCode = true;
if (isValidCode) {
    System.out.println("Code Accepted");
}
```
// 如果布尔值为真，则打印 "Code Accepted"

示例 2
```java
int numberOfCars = 10;
if (numberOfCars > 11) {
    System.out.println("Car Park Full");
}
```
// 什么都不打印，因为汽车数量少于 11

## else 语句

我们现在已经看到如何根据条件执行一个代码块，但如果有两个块呢？例如，*如果*牛奶在打折，*那么*玛利亚就买得起，*否则*她将买另一个品牌的牛奶。看这段代码：

示例 1
```java
if (hasPrerequisite) {
    //玛利亚买了她喜欢的牛奶
} else {
    //玛利亚将买另一个品牌的牛奶
}
```

示例 2
```java
int hour = 12;
if (hour < 13) {
    System.out.println("Good morning");
} else {
    System.out.println("Good afternoon");
}
```
// 输出将是“Good morning”，因为时间小于13
// 如果时间大于 13，输出将是“Good afternoon”

## else if 语句

如果需要，我们可以继续使用这种条件结构并使用 if-then-else。让我们使用同样的例子，但现在玛利亚希望她两种最喜欢的牛奶中至少有一种在打折。这让我们的代码有了多个条件。看这段代码：

```java
if (milkOne > 3) {
} else if (milkTwo > 3) {
} else if (milkThree > 3) {
} else {
  System.out.println("Can't afford milk");
}
```



在这种情况下，我们有两个可能为真的条件，代码将继续运行，直到其中一个为真，或者到达 `else`。

## switch 语句

`switch` 语句允许你根据值执行不同的代码块。它通常比多个 `if-else` 语句更整洁。

```java
String course = "Math";

switch (course) {
    case "Science":
        // 代码
        break;
    case "History":
        // 代码
        break;
    default:
        // 代码
        break;
}
```

在本节中，我们将学习 `switch` 语句以及它是如何工作的。

```java
int fruit = 1;

switch (fruit) {
    case 1:
        System.out.println("Apple");
        break;
    case 2:
        System.out.println("Banana");
        break;
    default:
        System.out.println("Unknown fruit");
}
```

## 创建类

请看这个类的创建片段：

```java
public class Main {
    int a = 10;
}
```

## 创建对象

一旦我们创建了类，就可以继续创建我们的对象：

```java
public class Main {
    int a = 10;

    public static void main(String[] args) {
        Main anObject = new Main();
        System.out.println(anObject.a);
    }
}
```

显然，你可以在一个类中创建多个对象：

```java
public class Main {
    int a = 10;

    public static void main(String[] args) {
        Main anObject1 = new Main();
        Main anObject2 = new Main();
        System.out.println(anObject1.a);
        System.out.println(anObject2.a);
    }
}
```

## 多个类

对象在类之间也是可以交换的。这意味着你可以使用在其他类中创建的对象。这样做是为了更好地组织你的代码。例如，在一个类中包含方法和属性，而在另一个类中包含 `main()` 方法。在这种情况下，你需要两个不同的 Java 文件。一个是 `Main`，另一个是其他的。如下：

```java
// Example 1 (Main.java)
public class Main {
    int a = 10;
}
```

```java
// Example 2 (Other.java)
class Other {
    public static void main(String[] args) {
        Main anObject1 = new Main();
        System.out.println(anObject1.a);
    }
}
```

我们可以在命令行提示符中编译这两个文件：

```
C:\Users\Name of Your Computer>javac Main.java
C:\Users\Name of Your Computer>javac Other.java
```

然后运行 `Other.java`：

```
C:\Users\Name of Your Computer>java Other
```

输出将是 10。

这个示例将包含名称、GPA、年份以及学生是否有奖学金。

现在我们已经给出了关于类的指令，但在这种情况下，我们创建了一个对象，一个学生。

所以我们首先需要声明类内部的内容，以便我们能创建对象。在我们的示例中，一个对象将是这样的学生：

- Student name: Rex
- GPA: 3.6
- Year: 2005
- Scholarship: Yes

这就是我们刚刚创建的类中的对象。一旦我们定义了类，我们就可以创建任意数量的对象。这就是为什么面向对象的编程语言如此流行且易于管理的原因之一。

我们可以为我们世界中建模的任何事物创建类，从汽车到学生、动物，甚至是星期几的每一天。如果我们创建一个程序来跟踪学生和他们的考试分数，我们将创建诸如 `Student`、`Grade` 或 `Course` 之类的类。现在 `Student` 类中的每个学生都将是一个对象，也被称为实例（`instance`），与任何不同的课程一样，它将是 `Course` 类中的一个对象或实例。

正如我们所看到的，我们可以将对象进一步分类为同时具有状态和行为。在学生的情况下，状态将是不同的字段，例如名称、GPA 等，而行为则是方法。

## 语法

例如，正如我们所看到的，Java 具有预定义的类，例如 `System`，我们经常使用它向屏幕上添加文本。当我们使用 `public` 来启动代码时，我们正在使用一种访问层级修饰符，这就是为什么我们允许其他类与此类交互。这就是为什么我们可以向代码中添加其他类。为了方便理解，我们现在要处理的所有类将是 `public` 的。

正如我们所看到的，当我们写 `public static void main(String[] args)` 时，它包含一个 `main()` 方法，该方法反过来能够列出程序执行的任务。这个 `main()` 在每次编译 `.class` 文件时都会运行。

## 构造方法

为了能够创建类的对象或实例，我们需要一个构造方法。当你定义构造方法时，你必须在类内部定义它。让我们来看这个示例：

```java
public class Chocolates {
    // 这是一个构造方法
    public Chocolate() {
        // 这些是创建巧克力对象的指令
    }

    public static void main(String[] args) {
        // main 方法的主体
    }
}
```

为了让我们创建对象或实例，我们需要在 `main()` 中调用构造方法。所以，如果我们想将一个新的巧克力对象赋值给变量 `ferrero`，它看起来像这样：

```java
public class Chocolate {
    public Chocolate() {
        // 如何创建一个 Chocolate 对象
    }

    public static void main(String[] args) {
        // 调用构造方法
        Chocolate ferrero = new Chocolate();
    }
}
```

与我们目前看到的不同（之前声明的是 `boolean` 或 `int` 等原始数据类型），我们将变量 `Chocolate` 声明为一种引用数据类型。这决定了 `ferrero` 变量的值是对对象内存引用。当我们声明它时，我们使用类的名称作为变量的类型，在这个示例中是 `Chocolate`。

所以我们需要分配一个运算符（在此情况下是 `=`），调用构造方法 `Chocolate()`，并使用 `new` 告诉程序我们正在创建。

## 实例字段

对象应该具有特征，因此我们需要添加实例字段。例如，如果我们有一个学生对象，字段可以是名称、GPA 和年份。这些是定义在类内部的。

```java
public class Student {
    String name;
    double gpa;
    int year;
}
```

当我们创建类的实例时，我们为这些字段赋值：

```java
Student s = new Student();
s.name = "Rex";
s.gpa = 3.6;
s.year = 2005;
```

这些字段代表了对象的状态。

## 构造方法参数

虽然我们没有详细解释，但我们已经见过参数了，例如 `String[]` 是 `main` 方法中的参数。现在我们将在构造方法体中使用参数。

```java
public class Chocolate {
    String flavor;

    // 这是一个构造方法
    public Chocolate(String chocolateFlavor) {
        flavor = chocolateFlavor;
    }

    public static void main(String[] args) {}
}
```

为了向方法传递值，我们将参数分为两种不同的类型：形式参数（formal）和实际参数（actual）。第一个声明了传入方法的数据类型和名称，在上面的示例中是 `String chocolateFlavor`。这告诉我们 `chocolateFlavor` 代表传递到构造方法的任何字符串。我们将在本章稍后的部分介绍实际参数。

由于所谓的“构造方法重载”（constructor overloading），一个类可以拥有多个构造方法，只要它们的参数值不同。编译器将能够根据签名区分这两个方法。这里是两个构造方法的示例：

```java
public class Chocolate {
    String flavor;
    boolean containNuts;

    // 构造方法1
    public Chocolate(String chocolateFlavor) {
        flavor = chocolateFlavor;
    }

    // 构造方法2
    public Chocolate(boolean containNuts) {
        this.containNuts = containNuts;
    }
}
```

## 为实例字段赋值

我们之前提到过参数，这些参数本质上是我们可以传递给方法的值。一旦我们这样做了，就可以使用它们来给实例字段赋初值。看这个示例：

```java
public class Chocolate {
    String flavor;

    public Chocolate(String chocolateFlavor) {
        // 在这里我们能够将参数值赋值给实例字段
        flavor = chocolateFlavor;
    }

    public static void main(String[] args) {
        // 在这里我们调用构造函数来提供参数值
        Chocolate ferrero = new Chocolate("fruity");
    }
}
```

为了实现这一操作，给定的类型值必须与声明的参数类型相等。当我们查看构造函数时，看到 `chocolateFlavor` 指向我们传递的值，在此例中为 "fruity"。"Fruity" 被赋值给 `flavor`，而 `flavor` 就是实例字段。

在这个示例中，当我们执行 `flavor = chocolateFlavor` 时已经声明了 `flavor`，因此我们不再需要对其进行赋值。实例 `ferrero` 持有 `flavor`，这是一个指向值 "fruity" 的实例字段。为了访问该字段的值（在此例中为 `flavor`），我们将使用点符号 `.`。例如：

```java
// 如何访问字段：对象名.字段名
System.out.println(ferrero.flavor); // 结果是 "fruity"
```

现在，当在方法调用期间传递值时，这被称为**实际参数**。当我们通过调用方法的过程调用参数时，被称为**按值传递**。举例来说，在上面的练习中当我们声明对象 `ferrero` 时，`String` 类型值 "fruity" 被作为参数传递。作为形式参数的 `chocolateFlavor` 随后被赋值该值的副本。

## 多个字段

对象可以无限制地添加实例字段，只要程序需要它们。在我们的示例中，我们将添加更多实例，以便程序拥有多个字段。我们将放置一个布尔值 `hasAllergens`，用于表示巧克力是否含有坚果等过敏原，以及一个整数 `gramsPerChocolate`，表示每块巧克力的克数。它看起来应该是这样的：

```java
public class Chocolate {
    String flavor;
    // 我们将在这里添加新字段
    boolean hasAllergens;
    int gramsPerChocolate;

    // 现在我们将添加与新字段关联的新参数
    public Chocolate(String flavor, boolean allergens, int grams) {
        this.flavor = flavor;
        // 新参数
        hasAllergens = allergens;
        gramsPerChocolate = grams;
    }

    public static void main(String[] args) {
        // 在方法调用中传递新值
        Chocolate ferrero = new Chocolate("nutty", true, 72);
        Chocolate tony = new Chocolate("fruity", false, 64);
        System.out.println(tony.hasAllergens);
        // 结果将是 false
        System.out.println(ferrero.gramsPerChocolate);
        // 这里将是 72 克
    }
}
```

我们可以看到，构造函数有多个参数，因此能够接收为新创建字段的值。需要考虑的一点是，在传递值时，参数的顺序必须保持一致。

这些是我们谈论类以及它们在代码中所能做什么时，需要了解的基本概念。程序通常由许多类和对象创建，并且程序至少需要一个类才能运行。

因为类定义了其对象所代表的行为和状态。例如，当你声明实例字段时，你正在定义一种状态。在类中定义方法时，行为也是类似的。

正如我们所看到的，我们可以将类看作是从现实世界中抽象而出的，它们代表了我们世界中的那些事物，例如学校程序中的学生信息。

## 方法

正如我们在本章中学到的，对象（或实例）既有行为也有状态。我们还研究了如何添加实例字段来给对象提供状态。在本节中，我们将研究如何使用方法来添加行为。

我们可以再次查看之前的银行账户示例。在这个示例中，状态定义了账户余额。行为表示我们可以对该银行账户做什么，例如取款、存款甚至验证余额。

方法用于重复我们可以执行的操作。这也是为什么可以完成大型程序的原因，因为方法允许我们将这些大任务分解。因为我们可以反复使用方法，这简化了我们的生活。想象一下，你有一个用于组装自行车的程序，在代码中可能类似于 `assembleBike()`。如果我们必须为每辆组装的自行车编写代码，我们将浪费大量时间，并且代码更容易出错。但因为我们创建了 `assembleBike()`，我们只需要在需要时调用该方法即可。

在本节中，我们将看到如何创建并将方法引入到我们的代码中。由于 Java 编程方式的原因，任何人可以在自己的代码中调用 `assembleBike()` 并对其工作，即使他们并不理解它是如何写的。由于有许多程序员使用这种技术，他们给它起了一个名字**过程抽象**（procedural abstraction）。就是当你使用一个方法，知道它能完成什么，但不知道它是如何实现的。

看这段代码片段：

```java
// balance
System.out.println("Hi");
System.out.println("The balance in account: " + balance);

// 存款
int afterDeposit = 50;
System.out.println("You deposited " + afterDeposit);

// 取款
int afterWithdraw = 50;
System.out.println("You withdrew " + afterWithdraw);
```

我们将看到如何创建并将方法引入到我们的代码中。

将某些方法并传递到另一个方法。还记得我们如何为构造函数添加参数的吗？我们可以更改方法，使其允许某些参数。查看代码片段了解如何实现：

```java
public void startingSpeed(int speedNum, String cheerUp) {
    System.out.println("As we reach the speed of " + speedNum + ", " + cheerUp + "!");
    System.out.println("Hell yeah!");
}

public static void main(String[] args) {
    Motorcycle myCoolMotorcycle = new Motorcycle("black");
    myCoolMotorcycle.startingSpeed(70, "Wow!");
}
```

就像构造函数一样，签名（signature）由方法名以及参数类型组成。此方法的签名是 `startingSpeed(int, String)`。

再次，顺序是相关的。因此，参数类型需要与参数类型的顺序一致。

我们还可以重新赋值实例字段。回到我们的银行账户示例，我们需要两个不同的方法来存款和取款。根据你取出的金额、存款的金额以及初始余额，`balance` 值会发生变化。正如我们所看到的，通过使用 `=` 运算符，我们可以再次为 `balance` 赋一个新值：

```java
public void depositing(double valueToDeposit) {
```



## 方法与实例字段

```java
double updatedBalance = balance + valueToDeposit;
balance = updatedBalance;
}
```

如果我们调用 `depositing()` 方法，实例字段的值应该改变：

```java
public static void main(String[] args) {
    bankAccount myAccount = new bankAccount(100);
    System.out.println(myAccount.balance);
    myAccount.depositing(50);
    System.out.println(myAccount.balance);
}
```

如果我们运行这段代码，它会首先打印 100（这是账户中的初始值），然后会打印 150（因为这是存款后留在账户中的）。通过更改实例字段，我们能够改变对象的状态并使其更加多样化和灵活。

### 返回值

为了能够在创建方法之外使用变量，我们需要从方法中返回它们。这个关键字是 `return`。如下：

```java
public int numberOfMugs() {
    int mugs = 6;
    // 在这里返回该语句
    return mugs;
}
```

在这个示例中，我们有一个方法 `numberOfMugs()`，它返回 6。在你返回该语句后，编译器将忽略其后的任何内容。

正如你可能注意到的，我们没有使用 `void` 关键字，而是使用了 `int`，这是为了让我们理解返回类型是 `int`。在之前使用 `void` 的示例中，我们是在告诉程序没有返回任何值。在我们使用的非 `void` 方法 `numberOfMugs()` 中，我们可以在调用它时返回一个值。

如果我们想返回一个对象呢？这是可能的，但与我们返回基本数据类型的方式并不相同。举个例子，我们可以创建另一个名为 `MotoLot` 的类，这个类将拥有 `Motorcycle` 参数并返回 `Motorcycle` 对象。

```java
class MotoLot {
    Motorcycle motln;

    public MotoLot(Motorcycle givenMotorcycle) {
        motln = givenMotorcycle;
    }

    public Motorcycle returnAMotorcycle() {
        // 我们现在正在返回 Motorcycle 对象
        return motln;
    }

    public static void main(String[] args) {
        Motorcycle myCoolMotorcycle = new Motorcycle("black", 70);
        System.out.println(myCoolMotorcycle);
        MotoLot myMotoLot = new MotoLot(myCoolMotorcycle);
        System.out.println(myMotoLot.returnAMotorcycle());
    }
}
```

输出应该给你相同的内存地址，因为 `myCoolMotorcycle` 和 `motln` 具有相同的值。

### 方法小结

复习一下目前为止关于方法的知识。我们可以通过使用 `.` 符号来调用方法。通过使用方法更改实例字段的值。作用域仅限于创建它们的方法内部，返回允许我们在方法之外使用变量。

## 参数和参数 (Parameters and Arguments)

你现在可能已经知道什么是参数和参数了。我们展示了许多示例，特别是关于参数的内容。在本节中，我们将深入理解它们，以及它们如何帮助我们使用代码。

我们知道为了向方法传递信息，可以使用参数。你可以说参数类似于变量，但它们是在方法内部使用的。在声明方法名后，你在括号内指定参数，这些参数没有限制，只要用逗号隔开，你可以在方法中添加任意数量的参数。看这个示例：

```java
public class Main {
    static void aMethod(String firstName) {
        System.out.println(firstName + " Martins");
    }

    public static void main(String[] args) {
        aMethod("George");
        aMethod("Sebastian");
        aMethod("Gui");
    }
}

// 输出将是：
// George Martins
// Sebastian Martins
// Gui Martins
```

### 多个参数

你可以向方法传递多个参数，只需用逗号分隔：

```java
public class Main {
    static void aMethod(String firstName, int age) {
        System.out.println(firstName + " is " + age + " years old");
    }

    public static void main(String[] args) {
        aMethod("George", 25);
        aMethod("Sebastian", 30);
    }
}
```

### 方法重载

方法重载允许在同一个类中定义多个同名方法，只要它们的参数列表不同（参数类型、数量或顺序不同）。

```java
public class Main {
    static void display(int a) {
        System.out.println("Integer: " + a);
    }

    static void display(String a) {
        System.out.println("String: " + a);
    }

    static void display(int a, String b) {
        System.out.println("Integer: " + a + ", String: " + b);
    }

    public static void main(String[] args) {
        display(10);
        display("Hello");
        display(10, "World");
    }
}
```

### 重载总结

- 方法名必须相同
- 参数列表必须不同（类型、数量、顺序）
- 返回类型可以相同也可以不同
- 仅返回类型不同无法构成重载

## Java Math 类

Java `Math` 类提供了许多用于数学运算的静态方法。

### Math.max()

返回两个值中的较大值。

```java
public class Main {
    public static void main(String[] args) {
        System.out.println(Math.max(10, 20)); // 输出 20
    }
}
```

### Math.min()

返回两个值中的较小值。

```java
public class Main {
    public static void main(String[] args) {
        System.out.println(Math.min(10, 20)); // 输出 10
    }
}
```

### Math.sqrt()

我们使用这个方法来寻找给定变量的平方根，例如：

```java
public class Main {
    public static void main(String[] args) {
        System.out.println(Math.sqrt(25)); // 输出 5.0
    }
}
```

### Math.abs()

通过这个方法，我们可以找到给定变量的绝对正值：

```java
public class Main {
    public static void main(String[] args) {
        System.out.println(Math.abs(-5.1)); // 输出 5.1
    }
}
```

### Math.random()

如其名所示，此方法返回一个 0.0 到 1.0 之间的随机数，例如：

```java
public class Main {
    public static void main(String[] args) {
        System.out.println(Math.random());
    }
}
// 结果将是 0.0 到 1.0 之间的随机数
```

然而，你可以更改随机数的范围。如果你想将随机数的范围扩大到 50，你可以这样写：

```java
public class Main {
    public static void main(String[] args) {
        int randomNumber = (int)(Math.random() * 51);
        // 注意这里是 51，因为它不包含在内
        System.out.println(randomNumber);
    }
}
// 输出为 0 到 50 之间的数字
```

## Java 包与 API

当我们谈论 Java 中的包（packages）时，我们指的是类的组。就像计算机文件夹一样。为了创建清晰且更易维护的代码，我们使用具有唯一名称的包，这样就不会混淆哪个是哪个。我们可以将这些包分为两类：

- 内置包（来自 Java API）
- 自定义包（由用户创建）

### 内置包

这些是 Java API，可以被视为一个内部 Java 库，其中包含了写好并可以直接使用的类。所有这些包都是免费使用的。你可以在那里找到许多允许许多操作的类。

这个内部 Java 库进一步分为类和包。如果你导入一个类，你将获得一个带有属性和方法的单个类；但如果你导入一个包，你将获得几个相互相关的类。那么我们如何从 Java 内部库导入包或类呢？让我们来看：

```java
import package.nameOfClass;   // 你将导入单个类
import package.nameOfPackage.*; // 你将导入一个包
import java.time.LocalDateTime;
```

给你一个具体的例子：
上面示例中的包是 `java.time`，这个包允许你引入日期、时间、持续时间和瞬间。然后我们将范围缩小到 `LocalDateTime` 类，它允许访问当前的日期和时间。例如：

```java
import java.time.LocalDateTime;

public class TimeNow {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.of(2022, 3, 4, 12, 30, 0);
        System.out.println("Hours = " + now.getHour());
        System.out.println("Minutes = " + now.getMinute());
        System.out.println("Seconds = " + now.getSecond());
        System.out.println("Nanos = " + now.getNano());
        System.out.println("Year = " + now.getYear());
        System.out.println("Month = " + now.getMonth());
        System.out.println("Day = " + now.getDayOfMonth());
    }
}
```

输出结果看起来像这样：
```text
Hours = 12
Minutes = 30
Seconds = 0
Nanos = 0
Year = 2022
Month = MARCH
Day = 4
```

如果你访问 Oracle 官方网站，会有很多包供选择以及许多其他类。只需记住，如果你想导入整个包，你需要这样写：
`import java.time.*;`

你需要使用 `*` 来导入整个包。

### 自定义/第三方包

如果你想创建自己的包，你需要将它存储在特定的 Java 目录下。你需要使用的关键字是 `package`，它的应用方式如下：

```java
package myownpack;

class MyPackageClass {
    public static void main(String[] args) {
        System.out.println("I created this package");
    }
}
```

你需要将此保存为 `MyPackageClass.java` 以便进行编译：

```bash
C:\Users\Name of Your Computer>javac MyPackageClass.java
C:\Users\Name of Your Computer>javac -d . MyPackageClass.java
```

这里有两个关键字：`-d` 允许你指定保存文件的特定目标，而 `.` 允许将包保留在相同目录下。

然后，在我们编译包之后，会创建一个名为“myownpack”的文件夹。要运行它你需要输入：

```bash
C:\Users\Name of Your Computer>java myownpack.MyPackageClass
```

你将得到：
```text
I created this package
```

## 抽象类与方法

当我们提到抽象时，我们隐藏了某些细节并只显示必要的数据。我们可以使用抽象类和方法。例如：

```java
abstract class Insect {
    abstract void insectNoise();
    public void sleep() {
        System.out.println("Sleeping...");
    }
}

class Bee extends Insect {
    @Override
    void insectNoise() {
        System.out.println("Bzz!");
    }
}

public class Main {
    public static void main(String[] args) {
        Bee bee = new Bee();
        bee.insectNoise();
        bee.sleep();
    }
}
```

## 接口

接口用于定义类必须实现的合约。一个类可以实现多个接口。

```java
interface oneInterface {
    void aMethod();
}

interface twoInterface {
    void bMethod();
}

class DemonstrationClass implements oneInterface, twoInterface {
    @Override
    public void aMethod() {
        System.out.println("Method A executed");
    }

    @Override
    public void bMethod() {
        System.out.println("Method B executed");
    }
}

public class Main {
    public static void main(String[] args) {
        DemonstrationClass obj = new DemonstrationClass();
        obj.aMethod();
        obj.bMethod();
    }
}
```

## Java 枚举 (Enum)

枚举是一种特殊的类，用于表示一组常量。

```java
enum LightTrafficSignal {
    RED("halt"), GREEN("go"), ORANGE("slower");

    private String move;

    LightTrafficSignal(String move) {
        this.move = move;
    }

    public String getMove() {
        return this.move;
    }
}

public class Main {
    public static void main(String[] args) {
        LightTrafficSignal signal = LightTrafficSignal.valueOf("RED");
        System.out.println(signal.getMove());
    }
}
```

## Java 用户输入

这是 Java 中一个非常有用的类。通过 `Scanner` 类，你可以获取用户输入。为了导入 `Scanner` 类，你需要使用 `java.util` 包。`Scanner` 类内部有许多方法。在这个示例中，我们将使用一个允许我们读取字符串的方法，它被称为 `nextLine()` 方法：

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        Scanner aObject = new Scanner(System.in);
        // this是为了我们能够创建一个扫描对象
        System.out.println("Enter nickname");
        String userNickname = aObject.nextLine();
        System.out.println("Nickname is " + userNickname);
    }
}
```

输出结果应该是这样的：
```text
Enter nickname
（在此输入你选择的昵称）
Nickname is: （你选择的昵称）
```

我们使用 `nextLine()` 是为了读取字符串，但 `Scanner` 内部还有许多其他方法可以让你读取其他值。例如：

- `nextDouble()` 允许你读取 double 类型。
- `nextBoolean()` 允许你读取布尔值。
- `nextInt()` 允许你读取 int 值，依此类推。

## Java 日期

我们上面提供了一个与 `java.time` 包相关的示例，使用了同时代表日期和时间的 `LocalDateTime` 类。但该包中还有其他有用的类，例如 `LocalDate` 只代表日期，而 `LocalTime` 只代表时间。

再给你一个当前日期的示例：

```java
import java.time.LocalDate;

public class Main {
    public static void main(String[] args) {
        LocalDate aObject = LocalDate.now();
        System.out.println(aObject);
    }
}
```

要实现当前时间，我们将采取类似的方法：

```java
import java.time.LocalTime;

public class Main {
    public static void main(String[] args) {
        LocalTime aObject = LocalTime.now();
        System.out.println(aObject);
    }
}
```



System.out.println(aObject);

}

}

```

输出将是你计算机上的当前日期。
`java.time` 包中还有另一个类叫做 `DateTimeFormatter`，它使用了 `ofPattern()` 方法。这允许你按照意愿格式化日期和时间。这里有一个示例：

```java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class Main {
    public static void main(String[] args) {
        LocalDateTime aObject = LocalDateTime.now();
        System.out.println("No formatting " + aObject + " = " + aObject);
        DateTimeFormatter aFormatObject = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");
        String formattedDate = aObject.format(aFormatObject);
        System.out.println("With formatting:" + formattedDate);
    }
}
```

输出如下：
No formatting—yyyy-MM-dd : HH:mm:ss
With formatting—dd-MM-yyyy : HH:mm:ss

你不一定得使用这种配置；相反，你可以使用 `dd/MM/yyyy` 或 `dd-MMM-yyyy`，程序将进行相应的调整。

## Java HashMap

在关于数组和 `ArrayList` 的章节中，我们学习了可以有序地保存不同的值，并且能够通过调用这些值所在的索引号来访问它们。当使用 `ArrayList` 时，这些值是 `int` 类型。使用 `HashMap` 时，你可以成对地持有其他键和值，并可以使用如 `String` 等其他类型通过索引来访问它们。

在这种情况下，你使用一个对象键（或索引）对应一个不同的对象（或值）。这样你就可以持有不同的类型，甚至是相同的类型。例如，看这段代码片段：

```java
import java.util.HashMap;
HashMap<String, String> countriesContinents = new HashMap<String, String>();
```

上面你导入了 `HashMap` 并创建了一个名为 `countriesContinents` 的对象。来看整个代码块：

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, String> countriesContinents = new HashMap<String, String>();
        countriesContinents.put("Europe", "England");
        countriesContinents.put("North America", "USA");
        countriesContinents.put("Asia", "Japan");
        System.out.println(countriesContinents);
    }
}
```

如果你想访问 `HashMap` 中的某项，需要使用 `get()`，如下所示：

```java
countriesContinents.get("Asia");
```

如果你想删除一个值，则可以使用 `remove()`，或者如果你想删除所有项，则可以使用 `clear()`。如果你想确定你的 `HashMap` 的大小，可以使用 `size()` 方法。

## Java HashSet

和 `HashMap` 一样，你通过导入 `java.util` 包来访问 `HashSet`。这允许你使用哈希表数据类型创建一个数学集合。它是一种项目的集合。以下是它的创建方法：

```java
import java.util.HashSet;
HashSet<String> dogs = new HashSet<String>();
```

如果你想添加项目，可以这样操作：

```java
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        HashSet<String> dogs = new HashSet<String>();
        dogs.add("Poodle");
    }
}
```

如果你想删除一个值，则可以使用 `remove()`，或者如果你想删除所有项，则可以使用 `clear()`。如果你想确定你的 `HashSet` 的大小，可以使用 `size()` 方法。

## 包装类

尽管我们之前说的是基本类型，但现在可以使用对象。每个种类型都有对应的：
- Byte
- Short
- Integer
- Long
- Float
- Double
- Character
- Boolean

这里是我们如何使用它们：

```java
public class Main {
    public static void main(String[] args) {
        Integer aInt = 8;
        Double aDouble = 4.9;
        Character aChar = 'R';
        System.out.println(aInt);
        System.out.println(aDouble);
        System.out.println(aChar);
    }
}
```

## 正则表达式

Java 使用此功能搜索文本。这种正则表达式可以使用 `java.util.regex` 包。它包含了用于搜索的 `Matcher` 类、定义模式的 `Pattern` 类以及识别语法错误的 `PatternSyntaxException`。看起来如下：

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Main {
    public static void main(String[] args) {
        Pattern pattern = Pattern.compile("programming");
        Matcher matcher = pattern.matcher("I love programming in Java");
        while (matcher.find()) {
            System.out.println(matcher.group());
        }
    }
}
```

我们使用 `Pattern.compile()` 来创建模式。我们使用第一个参数来声明要搜索的模式，使用第二个参数来声明搜索不区分大小写，所以使用大写或小写字母都没有关系。

`Pattern.CASE_INSENSITIVE` 被称为标志，当与 `compile()` 方法一起使用时我们可以更改搜索方式。还有其他标志，例如：
- `Pattern.LITERAL`：允许模式中的任何特殊字符被视为普通字符。
- `Pattern.UNICODE_CASE`：如果与 `CASE_INSENSITIVE` 同时使用，你可以忽略不属于英语字母表的字符。

## 多线程

你可以通过创建类的实例并调用 `start()` 方法来运行线程。如下：

```java
public class Main extends Thread {
    public static void main(String[] args) {
        Main thread = new Main();
        thread.start();
        System.out.println("This is not in the thread");
    }
    public void run() {
        System.out.println("This is in the thread");
    }
}
```

如果类实现了 `Runnable` 接口，操作方法如下：

```java
public class Main implements Runnable {
    public static void main(String[] args) {
        Main aObject = new Main();
        Thread thread = new Thread(aObject);
        thread.start();
        System.out.println("This is not in the thread");
    }
    public void run() {
        System.out.println("This is in the thread");
    }
}
```

实现接口和继承线程的区别在于，类只能继承一次，而如果实现接口，你可以先继承再实现一个类。

## Lambda 表达式

Lambda 表达式在 Java 8 中首次引入，它们的工作方式与方法相似，但不同的是 Lambda 表达式不需要名称。这些表达式必须立即返回一个值，并且不包含任何像 `if` 或 `for` 的赋值语句。它们还不能包含变量，因此被认为比方法要局限得多。如果你打算执行任何复杂的操作，将必须使用代码块。在这种情况下，如果表达式必须返回一个值，代码块将返回一个语句。通常这些表达式也作为参数传递。例如，如果你在 `ArrayList` 中使用 `forEach()` 打印列表中的所有项，它看起来像这样：

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> items = new ArrayList<Integer>();
        items.add(8);
        items.add(2);
        items.add(22);
        items.add(9);
        items.forEach((n) -> {System.out.println(n); });
    }
}
// 打印结果将为 8, 2, 22, 9
```

使用 Lambda 表达式时，如果变量类型是一个接口，它允许将其存储在变量中。然而，表达式必须具有与使用的方法相同的参数和相同的类型。让我们来看 `java.util.function` 包中的 `Consumer`。

```java
import java.util.ArrayList;
import java.util.function.Consumer;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> items = new ArrayList<Integer>();
        items.add(8);
        items.add(2);
        items.add(22);
        items.add(9);
        Consumer<Integer> method = (n) -> {System.out.println(n); };
        items.forEach(method);
    }
}
```

为了在方法中使用 Lambda 表达式，该类型必须有一个带有单个方法接口的参数。以下是在调用接口方法时运行表达式的方法：

```java
interface StringFunction {
    String run(String a);
}

public class Main {
    public static void main(String[] args) {
        StringFunction exclamation = (s) -> s + "!";
        StringFunction question = (s) -> s + "?";
        printFormatted("Hi", exclamation);
        printFormatted("Hi", question);
    }
    public static void printFormatted(String aString, StringFunction format) {
        String outcome = format.run(aString);
        System.out.println(outcome);
    }
}
```

类包含了大量的课题，这使得它们成为理解的最关键知识之一。我们在本章中学习了许多对你未来有用的知识，但为了理解后续章节，你需要记住的主要内容是：
- 如何创建类
- 如何创建对象
- 如何使用在其他类创建的对象
- 什么是语法
- 以及什么是构造函数

## 第 8 章：静态方法和静态变量

### 方法回顾

我们在本书前面已经学习了方法和变量，但现在我们将深入探讨 Java 编程背景下静态方法和静态变量的含义。我们之前也简要提到过静态方法，这里是对它们作用的提醒。

这些方法不属于它们所在类的任何特定对象，而是属于整个类。如果你还记得，我们通过 `.` 运算符和类名来调用这些静态方法。

```java
double aNumber = Math.random();
```

我们没有创建一个像 `Math` 这样的对象（例如 `Math myNObject = new Math()`），而是直接使用了类名。你可能记得这一个：

```java
double aNumber = Double.valueOf("3.6");
```

我们不需要再次创建对象，而是将字符串转换成了 double。

### 静态变量

在我们深入研究静态方法并开始创建自己的之前，让我们来看静态变量。

```java
class Cat {
    public static String genus = "Felis";
    public int years;
    public String nickname;
    public Cat(int inputYears, String inputNickname) {
        years = inputYears;
        nickname = inputNickname;
    }
}
```

在我们深入研究静态方法并开始创建自己的之前，让我们来看静态变量。

### 编写你的静态方法

我们使用 `static` 关键字来创建静态方法，就像创建变量一样。如下：

```java
public static void learnAboutStaticMethods() {
```

## 第 9 章：继承与多态

继承和多态是 Java 编程中两个极其重要的特性，这也是 Java 成为一种面向对象语言的原因之一。让我们先关注继承。

正如你可能好奇过的，Java 中的继承应该与我们世界中的继承某些联系。如果你是这么想的，你是正确的。就像你从父母那里继承了特征，如棕发、蓝眼睛或身高一样，在 Java 中，你也可以继承类的特征。你将像现实生活中一样，有一个父类和一个子类。

假设你有一个 `Mammals` 类，并赋予了它一些特征，如热血、四条腿或有皮毛。但现在你想创建一个 `Cat` 类，你不需要重新定义和创建所有的方法，你可以使用类的继承将 `Mammals` 类中的某些特征传递给 `Cat` 类。因为猫是哺乳动物，所以它可以继承一些方法和字段。这非常重要，因为我们不需要不断地重新定义同一个类的成员。

尽管 `Cat` 类将继承 `Mammals` 类拥有的所有特征，但 `Cat` 也可以拥有自己独特的方法。

父类也可以称为超类或基类，它是你获取方法和特征的类；而子类，有时也称为派生类，是从父类继承的类，在我们的示例中就是 `Cat` 类。

那么我们如何应用继承呢？我们需要知道如何定义一个可以从父类继承的子类，为此，我们需要使用关键字 `extends`。它在代码中的写法如下所示：

```java
class Mammals {
    // mammals class members
}

class Cat extends Mammals {
}
```



在这个示例中，`Cat` 类从 `Mammals` 类继承了方法和字段。为了进行更深层次的理解，你扩展了 `Mammals` 类以涵盖 `Cat` 类，但 `Mammals` 并不是 `Cat` 的对象。

### 继承构造函数

既然我们可以从类中继承字段和方法，那么我们也可以对构造函数这样做吗？可以，通过使用 `super()` 构造函数。假设 `Mammals` 类有一个名为 `numLegs` 的字段。当我们用 `Cat` 创建对象时，我们希望 `numLegs` 始终为 4，因此我们希望构造函数始终将 `numLegs` 赋值为 4。

如果我们使用 `super()` 方法，我们可以让构造函数像父子构造函数一样工作。如下所示：

```java
class Cat extends Mammals {
    Cat() {
        super(4);
    }
}
```

如果我们将 4 传递给 `super()`，我们就可以创建一个 `numLegs` 为 4 的新 `Cat` 对象。我们也有编写不带 `super()` 的构造函数的可能性。如下：

```java
class Cat extends Mammals {
    Cat() {
        this.numLegs = 4;
    }
}
```

### 多态

Java 凭借其面向对象的编程允许父类与子类共享行为和信息，同时也允许它们结合自身的特征。这是为了简化编码时的语法，并让程序员更容易与其他程序员共享包。例如：

```java
class Mammal {
    public void salutation() {
        System.out.println("Animals salute you.");
    }
}

class Dog extends Mammal {
    public void salutation() {
        System.out.println("The dog barks");
    }
}

class MainClass {
    public static void main(String[] args) {
        Mammal mammal1 = new Mammal();
        Dog dog1 = new Dog();
        mammal1.salutation();
    }
}
```

### 方法重写

我们能够在子类中重写父类，并在当我们希望在子类中使用相同名称但希望其行为不同时使用它。然而，在我们这样做之前，我们需要确保子类与父类具有共同的属性，如下：

- 相同的参数数量和类型
- 相同的返回值
- 相同的方法名

为了重写该类，我们需要在子类方法上方写上 `@Override`。例如：

```java
class Mammal {
    public void salutation() {
        System.out.println("Animals salute you.");
    }
}

class Dog extends Mammal {
    @Override
    public void salutation() {
        System.out.println("The dog barks");
    }
}
```

正如我们之前看到的，我们可以使用关键字 `super` 来调用构造函数，但我们也可以用它来调用父类的方法。这样做需要写下 `super` 后面跟一个点（`.`）。但为了让它生效，我们需要编写正确的方法参数。

我们也可以在预期父类对象的地方使用子类作为其父类或子类对象。

实现这一点的一种方法如下：
`savingsAccount RodAccount = new checkAccount(400.50);`

在这里我们将 `RodAccount` 作为 `savingsAccount` 的一个对象。

### 子类中的 ArrayList 和数组

还记得我们之前说创建数组或 `ArrayList` 时需要所有内容都具有相同类型吗？这仍然成立，但通过多态，情况变得有点不同。我们允许将具有不同类但共享相同父类的对象放在 `ArrayList` 或数组中。

```java
Mammals poodle, siamese, chimpanzee;

poodle = new Dog();
siamese = new Cat();
chimpanzee = new Primate();
```

### 子类与参数

正如我们之前所见，我们需要确保可能会发生变化，否则你可能会陷入死循环，导致程序崩溃。例如，如果你写一个骰子程序，当骰子只到 6 时，骰子点为 7 的条件为假。这将是一个死循环。

- Java 中的多态是什么
- 如何继承构造函数

## 第 10 章：循环

因为在编码时，程序员经常使用循环作为工具来帮助编写需要执行多次的代码。这不仅节省了时间，而且在我们寻找 bug 时也有帮助。通常，当我们运行循环时，Java 中有三种主要的循环：`for` 循环、`while` 循环和 `for-each` 循环。我们将介绍它们以及如何使用它们。

### While 循环

还记得 `if` 语句吗？`while` 循环的工作方式类似。如果写成代码，它如下：

```java
while(funkiness > 5) {
    // code
}
```

在这个示例中，代码只有在为真时才会运行，并且将一直运行直到它为假，在这种情况下，直到 `funkiness` 小于或等于 5。

让我们来看一个密码系统，你有三次机会输入正确的密码。

```java
int tries = 0;
while (password != 3398 && tries < 3) {
    System.out.println("Wrong, try again");
    password = getNewPassword();
    tries += 1;
}
```

然而，你需要确保可能会发生变化，否则你可能会陷入死循环导致程序崩溃。

### Do/While 循环

这些是我们刚刚看到的 `while` 循环的稍微变体。在这里，代码将在运行之前先不知道条件是否可能为真。如果是，那么它将继续运行直到条件保持为真。示例如所示：

```java
public class Main {
    public static void main(String[] args) {
        int x = 1;
        do {
            System.out.println(x);
            x++;
        } while (x < 6);
    }
}
// 输出结果将是 1, 2, 3, 4, 5
```

## 计数器变量

计数器变量（有时称为迭代器）是我们在循环时使用的变量。这样做是为了程序在达到该变量的值时退出循环。例如，让我们再次查看密码示例，但稍微稍有不同：

```java
int tries = 0;
while(tries < 3) {
    System.out.println("Try again.");
    tries++;
}
```

正如我们所见，我们在开始循环之前将 `tries` 初始化为零。程序会对 `tries` 加 1，直到它的值达到 3 为止。一旦达到该值，它就会离开循环。

## For 循环

`for` 循环是用于递增/递减或对变量进行加减的极佳语法工具，它们分为三个不同的部分。首先，你有一个启动循环的控制变量、一个布尔表达式以及递减或递增部分。例如：

```java
for (int e = 0; e < 3; e++) {
}
```

翻译后的内容类似于：我们有循环的起始点或初始化值 `int e = 0`。然后我们给循环提供了一个布尔值，表示循环将一直执行直到该布尔表达式为假，即 `e < 3`。我们公式的最后部分表示，每次运行循环时 `e` 都会增加，因此在这种情况下，循环将在退出前运行三次。这里是另一个例子：

```java
public class Main {
    public static void main(String[] args) {
        for (int x = 5; x < 10; x = x + 2) {
            System.out.println(x);
        }
    }
}
// 输出将是 5, 7, 9。因为它只会输出 5 到 10 之间的奇数
```

## 遍历 ArrayList 和数组

当我们遍历一个数组或 `ArrayList`（例如数据列表）时，我们正在进行遍历。为了遍历数组或 `ArrayList`，我们需要使用索引来访问每个元素，为此，我们可以使用计数器来跟踪数组的长度。

正如你可能记得，数组和 `ArrayList` 中的索引从 0 开始，所以你会使用 0 作为计数器的值。这就是我们如何在数组中为 `int` 加 1 的方法：

```java
for (int e = 0; e < aList.length; e++) {
    aList[e] += 1;
}
```

我们使用 `a.length` 是因为正如我们所看到的，数组以及 `ArrayList` 的索引都从 0 开始。循环应该在计数器等于数组长度之前退出代码。例如，如果数组长度为 7，那么循环将运行到索引 6。如果代码尝试访问 7，将会出现一个提示为 `ArrayOutOfBoundsException` 的错误。如果你想遍历 `ArrayList`，可以像这样做：

```java
for (int e = 0; e < aList.size(); e++) {
    int num = aList.get(e);
    aList.set(e, num + 1);
}
```

当我们使用 `while` 循环遍历 `ArrayList` 和数组时，我们需要添加自己的计数器，以及一个直到计数器匹配数组长度的条件。例如：

```java
int e = 0;
while (e < aList.length) {
    aList[e] += 1;
    e++;
}
```

如果我们想用 `while` 循环来做：

```java
int e = 0;
while (e < aList.size()) {
    int num = aList.get(e);
    aList.set(e, num + 1);
    e++;
}
```

我们还可以使用 `break` 和 `continue` 等关键字来跳过或退出循环。如果你想离开或打破循环，就会使用 `break`。例如：

```java
for (int e = 0; e < 6; e++) {
    System.out.println(e);
    if (e == 5) {
        break;
    }
}
```

虽然我们设置了循环运行到 6，但我们使用了 `break` 让它在 5 处停止。如果我们只想跳过某次迭代，我们在循环内部使用 `continue` 关键字，程序会自动跳过并开始下一次迭代，例如：

```java
int[] numbers = {1,2,3,4,5,6,7};
for (int e = 0; e < numbers.length; e++) {
    if (numbers[e] % 2 == 0) {
        continue;
    }
    System.out.println(numbers[e]);
}
```

打印结果将跳过所有偶数，并输出 "1,3,5,7"。

## For-Each 循环

`For-Each` 循环也称为增强循环，允许我们遍历数组或 `ArrayList` 中的每个项目，并对每个元素执行操作。

```java
for (String aList : allLists) {
    System.out.println(aList);
}
```

正如我们所见，当我们遍历 `ArrayList` 时，我们也可以移除其中的任何元素。当我们这样做时，索引中的每个变量都会减一（或变为负一），因此我们在操作时需要注意，否则可能会遇到一些错误。

如果我们使用 `while` 循环并想移除所有奇数，可以这样做：

```java
int e = 0;
while (e < aList.size()) {
    if (aList.get(e) % 2 != 0) {
        aList.remove(e);
    } else {
        e++;
    }
}
```

如果我们想使用 `for` 移除元素，与 `while` 循环不同，我们需要添加循环控制变量，因此每当我们移除一个元素时，都需要手动减少循环控制变量。像这样：

```java
for (int e = 0; e < aList.size(); e++) {
    if (aList.get(e).equals("removed value")) {
        aList.remove(e);
        e--;
    }
}
```

- 带有数组和 `ArrayList` 的循环
- 以及计数器变量的作用

## 第 11 章：访问与作用域

你将遇到一个点，你的程序将变得越来越大，并开始拥有各种类以及不可避免地相互组合的对象。这时这两个概念将帮到你。简单来说，访问和作用域都与代码中可以与程序其他部分的特定方法和变量结合的部分有关。

### 访问

#### public 关键字

你可能已经知道 `public` 和 `private` 关键字在 Java 编程中的含义。让我们先看看访问是如何运作的。

```java
public class Cat {
    public String nickname;
    public int years;
    public Cat(String input_nickname, int input_years){
        nickname = input_nickname;
        years = input_years;
    }
    public void says() {
        System.out.println("Meow! Everyone calls me " + nickname + " and that's who I am!");
    }
}
```

你看到我们在不同的情况下使用了 `public` 吗？正如我们在代码中所看到的，所有内容都是 `public`，这意味着其他类都可以访问它们。当我们定义访问权限时，涉及到类、方法和构造函数。你可能已经知道如何声明某些 `public` 或 `private`，但在某些情况下，我们需要刷新一下记忆。

如果你理解了 `public` 的概念，你一定理解 `private` 可能意味着什么。当你有一个 `private` 方法或实例变量时，意味着只有在类内部才能访问它。结合上面的例子并查看下面的代码片段：

```java
public class Cat {
    private String nickname;
    private int years;
    public Cat(String input_nickname, int input_years){
        nickname = input_nickname;
        years = input_years;
    }
    public void says() {
        System.out.println("Meow! Everyone calls me " + nickname + " and that's who I am!");
    }
}

public class CatApprentice {
    public void createACat(){
        Cat bernard = new Cat("Bernard", 12);
        System.out.println(bernard.years);
        bernard.says();
    }
}
```

如果我们在最初创建 `Cat` 类时将变量 `.years` 和方法 `.says()` 都设为 `private`，那么 `CatApprentice` 将无法访问其中的任何内容。当我们决定让某些内容可以时时设置为 `public`，而只有在少数情况下我们才会将其设为 `private`。

虽然你的第一想法可能是总是将所有内容设为 `public`，但在某些情况下，将它们设为 `private` 更有意义。我们可以通过将变量和有时的方法设为 `private` 来将代码组织成逻辑单元，这被称为封装。有时我们需要保持分离，例如，一个对象可能不需要知道代码中其他对象的工作方式，不需要知道其他方法如何工作就能执行其功能。如果它有这些访问权限，很有可能会在不不知的情况下更改某些变量。

通过使用 `private` 关键字，我们限制了这种访问，并防止更改我们的代码，即使是无意为。在这里，你需要理解哪些应该设为 `private`，哪些不应该。

即使我们在编码时可能会将变量设为 `private`，我们仍然需要某些类来访问这些变量。有时我们需要类来访问 `private` 变量，所以我们会使用一个访问器方法，也称为 getter。

```java
public class Cat {
    private String name;
    public String getName() {
        return name;
    }
}
```



如你所见，变量名被设置为私有（`private`），但如果你使用 `getName()` 公共方法，仍然可以返回变量的值。这是因为访问器方法始终是公开的（`public`），并且总是返回相同类型的变量。

还有变器方法（mutator methods），它们的工作方式与私有类似，这些也称为 setter。它们的作用是重置给定变量的值，通常是空类型（`void`）方法。这意味着它们不返回任何值。

## 作用域

当我们使用访问修饰符时，我们需要设置作用域。这样我们就知道代码的哪些部分可以访问该变量。变量所在的位置对于理解我们拥有什么权限非常重要。例如，我们在类内部声明变量，但这些是在构造函数和方法之外，尽管每个构造函数和方法都在实例变量的作用范围内。让我们给你举一个例子来帮助你理解这个概念：

```java
class Cat {
    public String nickname;
    public int years;
    public int kg;
    public Cat() {
        nickname = "Voodoo";
        years = 4;
        kg = 15;
    }
    public void speak(){
        System.out.println("The name of the cat is " + nickname);
    }
}
```

我们可以看到，`Cat` 的构造方法使用 `nickname` 和 `years` 作为变量。另一方面，如果我们在给定方法内部声明变量，该变量无法在该方法之外的任何地方使用。

作用域内的循环和条件判断也是如此。你只有在条件判断或循环内部声明了某个变量，你才能在循环或条件判断中使用它。

## this 关键字

有时在添加类时，我们创建了与实例变量同名的局部变量。例如：

```java
public class Cat{
    public String nickname;
    public Cat(String inputNickname){
        nickname = inputNickname;
    }
    public void tellName(String nickname) {
        System.out.println("Hi, the new name is " + nickname);
    }
    public static void main(String[] args){
        Cat myCat = new Cat("Voodoo");
        myCat.tellName("Simon");
    }
}
```

这将使输出为 'Simon' 而不是 'Voodoo'。如你所见，有一个名为 `nickname` 的实例，同时也带有一个参数 `nickname` 的方法 `tellName`。如果我们要求输出打印 `nickname`，它将自动使用局部变量。

然而，如果我们使用 `this` 关键字，就可以访问实例变量。例如：

```java
public class Cat{
    public String nickname;
    public Cat(String inputNickname){
        nickname = inputNickname;
    }
    public void tellName(String nickname) {
        System.out.println("Hi, the new name is " + this.nickname);
    }

    public static void main(String[] args) {
        Cat a = new Cat("Guille");
        Cat b = new Cat("Filip");
        a.tellName("Voodoo");
        a.tellName("Simon");
    }
}
```

当我们使用 `this` 关键字时，我们是在指明正在操作的对象。因为我们在 `tellName()` 方法中使用了 `this.nickname`，所以打印的是实例变量中的变量或值。

当使用变器方法时，我们通常这样做：

```java
public void whatName(String nickname) {
    this.nickname = nickname;
}
```

这里是重置传递给参数的变量的值。

那么我们如何在方法中使用 `this` 呢？到目前为止，我们使用方法的方式是：

```java
public static void main(String[] args) {
    Cat myCat = new Cat("Jackson");
    myCat.speak();
}
```

如你所示，我们使用 `Cat` 来调用 `speak()` 方法。现在让我们看看使用 `this` 的：

```java
public class Cat{
    public int age;
    public int weight;
    public void setAge(int inputAge) {
        this.age = inputAge;
    }
    public void setWeight(int inputWeight) {
        this.weight = inputWeight;
    }
    public void resetSettings(){
        this.setAge(3);
        this.setWeight(14);
    }
}
```

当我们使用方法 `resetSettings()` 时，我们正在调用类中的方法。但正如你可能注意到的，调用方法需要一个对象，但我们没有像在之前的示例那样命名该对象，而是使用 `this` 代替对象。所以，当我们通过 `resetSettings()` 调用对象时，它也将用于调用 `setAge(3)` 和 `setWeight(14)`。

我们还可以将 `this` 用于参数。假设紧接上面的例子，`Cat` 是现有方法的一个参数。在编写 `Cat` 的另一个方法时，虽然签名可能类似于 `public void combineWithOtherCat(Cat another)`，而我们想要调用 `combineWithOtherCat(Cat)`，相反，我们可以使用 `this` 来作为参数。因此，在这种情况下，它看起来像这样：`this.combineWithOtherCat(this)`。如你所见，我们使用对象来调用方法，同时将其作为方法的参数传递。

这是你需要了解的关于访问和作用域的最主要知识。`private` 和 `public` 关键字的使用定义了代码的某些部分对方法、构造函数、变量和其他类的访问或无访问。

有一种方法可以让我们通过结合使用两个关键字——`try` 和 `catch` 来快速且轻松地发现异常。当你对一段代码块使用 `try` 时，你是在要求程序在运行该代码时对其进行错误测试。当你在 `try` 之后使用 `catch` 时，如果在使用 `try` 期间发生了错误，你将允许该代码块继续运行。

例如：

```java
try {
    int dimension = length / width;
} catch (ArithmeticException e) {
    System.err.println("ArithmeticException: " + e.getMessage());
}
```

我们没有使用常规的打印顺序，而是使用了 `System.err.println()`，因为这允许我们打印错误并更容易发现问题。

## 逻辑错误

即使我们消除了所有的运行时错误和语法错误，但似乎仍然无法得到正确的输出，尽管并没有报错。这被称为逻辑错误，是程序员（尤其是初学者）经常犯错误。

这通常是因为程序员编写代码的方式存在缺陷。编译器或程序不会给你提供任何错误，因为这是一个逻辑问题。你设计代码的方式无法产生你所预期的输出。这些可能是非常难以修复的 Bug。然而，有一些技术和工具可以帮助你在寻找这些错误时节省大量时间，被称为测试驱动开发（TDD）。这个过程旨在当代码存在逻辑错误时为代码抛出错误。

## 调试技巧

如果你反复检查你的代码，但仍然找不到问题的根源，你可以选择执行一些技巧来尝试解决问题。

### 打印语句法

你可以使用 `System.out.println()` 在代码的不同点验证你的代码。你可以在每个代码块中使用打印语句来查找返回值或变量值，直到发现异常所在。

### 分解你的程序

这可能是一个激进的，但如果你临时删除代码或部分代码并编译查看程序是否成功，你就可以缩小问题范围。例如，如果你删除了一半代码并运行程序没有问题，你可以加回被删除的一半或四分之一，然后重新运行，直到知道问题出在哪里。

与其临时删除代码，你可以将其作为注释。在大多数编辑器中，你可以通过选中代码并按下 `command + /` 来将其注释。

# 第 13 章：Java 文件

处理 Java 文件的方法对于理解 Java 编程的基础也同样重要。事实上，有一个专门的类可以让你管理文件，从创建、修改甚至删除文件。在本章中，我们将介绍通过 `File` 类可以执行的主要功能。

## 文件管理

为了导入 `File` 类，你需要导入 `java.io` 包。以下是如何为该类创建一个新对象并指定文件名：

```java
import java.io.File;
// 这里你正在导入一个 File 类
File aObject = new File("anyfilename.txt");
// 你需要添加文件名
```

以下是你可以配合 `File` 类使用的方法列表：

- `canWrite()` - 布尔类型，用于检查文件是否可以被写入
- `createNewFile()` - 布尔类型，用于允许创建一个新的空文件
- `canRead()` - 布尔类型，用于检查文件是否可以被读取
- `exists()` - 布尔类型的方法，用于检查文件是否存在于某处
- `getName()` - 字符串类型的方法，返回给定文件的名称
- `delete()` - 布尔类型的方法，用于删除文件
- `length()` - 长整型类型的方法，获取当前文件的大小
- `getAbsolutePath()` - 返回文件的路径
- `mkdir()` - 布尔类型的方法，能够创建目录
- `list()` - 字符串类型，能够返回文件数组

## 创建文件

如我们上面所示，通过使用 `createNewFile()` 方法。如果你创建成功，将返回一个 `true` 布尔值。如果目录中已存在同名文件，布尔值将返回 `false`。它的样子如下：

```java
import java.io.File;
import java.io.IOException;
// 这用于在发生错误时管理错误
public class CreatingAFile {
    public static void main(String[] args) {
        try {
            File aObject = new File("insertfilename.txt");
            if (aObject.createNewFile()) {
                System.out.println("The file was successfully created:" + aObject.getName());
            } else {
                System.out.println("The file exists");
            }
        } catch (IOException i) {
            System.out.println("There was an error");
            i.printStackTrace();
        }
    }
}
```

在这里如果文件创建成功，你会看到 "The file was successfully created:insertfilename.txt"。如果文件已存在，你会看到 "The file exists"。

## 写入文件

为了写入文件，我们将使用 `FileWriter` 类以及 `write()` 方法。这是一个示例：

```java
import java.io.FileWriter;
import java.io.IOException;
public class WritingAFile {
    public static void main(String[] args) {
        try {
            FileWriter aFile = new FileWriter("insertfilename.txt");
            aFile.write("Hello world!");
            aFile.close();
            System.out.println("The file was successfully written!");
        } catch (IOException e) {
            System.out.println("There was an error");
            e.printStackTrace();
        }
    }
}
```

## 读取文件

我们之前使用的类现在将被用于读取文件。通过使用 `Scanner` 类，你可以读取文本文件内部的内容。以下是这样做的示例：

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;
public class ReadingAFile {
    public static void main(String[] args) {
        try {
            File aObject = new File("insertfilename.txt");
            Scanner aTextReader = new Scanner(aObject);
            while (aTextReader.hasNextLine()) {
                String data = aTextReader.nextLine();
                System.out.println(data);
            }
            aTextReader.close();
        } catch (FileNotFoundException e) {
            System.out.println("There was an error");
            e.printStackTrace();
        }
    }
}
```

我们也可以通过使用 `File` 方法返回关于文件的信息。例如：

```java
import java.io.File;
public class GettingInfo {
    public static void main(String[] args) {
        File aObject = new File("insertfilename.txt");
        if (aObject.exists()) {
            System.out.println("Name of the file:" + aObject.getName());
            System.out.println("Get the Path:" + aObject.getAbsolutePath());
            System.out.println("Is it readable?" + aObject.canRead());
            System.out.println("Is it writable?" + aObject.canWrite());
            System.out.println("Size of the file:" + aObject.length());
        } else {
            System.out.println("It doesn't exist.");
        }
    }
}
```

## 删除文件

通过使用 `delete()` 方法，你可以在 Java 中删除文件，也可以删除整个文件夹。以下是实现方法：

```java
import java.io.File;
public class DeletingFile {
    public static void main(String[] args) {
        File aObject = new File("insertfilename.txt");
        if (aObject.delete()) {
            System.out.println("Deleting the file: " + aObject.getName());
        } else {
            System.out.println("Couldn't delete the file!");
        }
    }
}
```

输出结果将是“Deleting the file: insertfilename.txt”。

你也可以删除文件夹。如下所示：



```java
import java.io.File;
public class DeletingAFolder {
    public static void main(String[] args) {
        File aObject = new File("C:\\Users\\Your Computer Name\\Folder");
        if (aObject.delete()) {
            System.out.println("Deleted folder: " + aObject.getName());
        } else {
            System.out.println("Couldn't delete the folder.");
        }
    }
}
```

输出结果应该是：“Deleted folder Folder”。因为这是我们在代码中提供的路径。

了解如何处理 Java 文件（从创建到写入、读取和删除）至关重要的。这将使你精练地理解 Java 编程的各个方面。

# 第 14 章：常见问题解答 (FAQ)

在本章中，我们将回答一些书中没有涵盖的、或者涵盖了但没有完全回答的关于 Java 的常见问题。

## 什么是 JDK？

JDK 代表 Java Development Kit（Java 开发工具包），是 Java 程序使用的核心包的一部分。JDK 允许程序员和开发者用 Java 创建程序，这些程序可以由 JVM（Java 虚拟机）或 JRE（Java 运行环境）运行，我们将在下一个问题中解释它们。从本质上说，JDK 由 JVM 和 JRE 组成。JDK 包含了我们编译代码所需的编译器以及内置的 Java 类库。如果你想基于 Java 编程创建应用程序，则需要下载 JDK 软件。

不同类型的 JDK 针对不同类型的应用程序。你选择哪一个取决于你想开发的内容。目前有三个包可供选择：Java 标准版 (Java SE)、Java 企业版 (Java EE) 和 Java 微型版 (J2ME)。以下关于下载和安装 JDK 的简要说明（我们将使用 SE 版本）。

首先，你需要访问 `oracle.com`，系统会弹出一个 JDK 列表。你需要在三个不同的工具之间进行选择：公共 JRE、源码（Source Code）或开发工具（Development Tools）。你可以安装所有工具，也可以只安装其中一两个。如果你是初学者，只需要开发工具即可。

安装完成后，你可以打开命令提示符并输入 `java` 命令，返回的结果将应该是你刚刚安装的 Java 版本。你还需要 `javac` 来编译你的程序。你可以安装刚刚下载的 `jdk` 目录下的 `javac`。

现在你需要做的就是测试一下了！

## 什么是 JVM 和 JRE？

JVM（Java 虚拟机）用于执行 Java 编程。它的作用是将字节码转换为 JRE 和 JDK 能理解的代码。此外，它在安全和程序内存管理方面也起着重要作用。

JVM 有一个执行引擎，可以对代码进行编译和理解；一个类加载器，可以导入并初始化 Java 类文件；以及一个包含线程、栈区域和方法区域的运行时数据区域。

JRE（Java 运行环境）是我们用来执行 Java 编程的工具。它的主要功能是执行 Java 程序，如果你需要编译或开发代码，则不需要 JRE。

JRE 部署解决方案允许部署 Java Plugin 和 Java Web Start 等功能。它拥有开发工具包，允许开发者处理用户界面；集成库，允许你同时使用集成库和类库，以及工具库和语言库。

## 什么是 Java 编译器？

编译器用于将文本文件编译为 Java 文件。标准的 Java 编译器是 Java 语言编译器 (`javac`)，但还有其他的，例如 GNU 编译器或 ECP（Eclipse Java 编译器）。

正如我们所见，Java 程序是用语句编写的，我们需要编译器将这些语句转换成计算机可以执行的形式，例如 Java 文件。

## 什么是 Java API？

Java API 代表应用程序编程接口（application programming interface），它是预编写的类、接口和包。这有助于开发者和程序员更快速地开发 Java 程序。API 有三种类型：

- 官方 Java API
- 可选 Java API（它们是官方的，但没有第一组那么必不可）
- 第三方 API（通常由用户创建并可以在线下载）

### 什么是 Java Web Start？它是如何启动的？

Java Web Start 的主要功能是允许你在 Web 上运行 Java 程序和应用程序。它易于使用，不需要复杂的安装过程。一旦自动安装了 JRE，你就可以使用 Java Web Start，所以一旦安装了 Java，你的电脑上就有它了。启动 Web Start 很简单，有几种方法可以实现。

### 什么是 Java 插件 (Plugin)？

Java 插件允许你在浏览器中使用小程序（applets）。与 Java Web Start 类似，插件在安装 JRE 时同时安装。

### 如何获得 Java 认证？

Java 认证可以证明你精通 Java 编程。像许多其他认证一样，你需要参加课程。你首先需要的是选择你想参加的认证。不同级别和类型的认证取决于你想如何使用 Java 技能。无论如何，如果你是初学者，应该从基础认证开始。

你需要参加课程，根据你参加的认证，课程的数量可能会有所不同。现在你可以选择线下或在线授课，任何适合你的方式都行。当你完成课程并觉得自己准备好考试时，你需要做的就是预约。你参加课程的机构应该为你提供认证考试。你可能需要获取一个有效期为六月的优惠券，并安排考试。考试的数量也取决于认证的级别。官方的 Java 认证包括：

- Oracle Certified Associate Java Programmer (OCAJP) —— 基础认证，学习 Java 的基础知识。如果你想继续学习 Java，需要先参加 OCAJP。
- Oracle Certified Professional Java Programmer (OCPJP) —— 这证明你拥有高级 Java 技能。
- Oracle Certified Professional Java Application Developer (OCJPAD) —— 这证明你可以使用 Java 进行编程和应用开发。
- Oracle Certified Master Java Enterprise Architect (OCMKEA) —— 它证明你精通 Java。这是你可以获得的最高 Java 认证之一。

## Java 需要许可证吗？

Java 在浏览器上用于教育用途是免费的。从 2019 年 1 月起，Java SE 的商业用户如果获取未来的更新，必须购买年度订阅。作为参考，桌面价格为每月 2.50 美元，如果需要在云或服务器上使用，处理器价格为每月 25 美元。

## 什么是关键字？

Java 中有 67 个关键字。这些是预定义的保留字，允许程序执行特定的操作。因为这些是保留字，你不能用它们来命名类、方法或变量。此类单词的示例：`boolean`、`byte`、`catch`、`double` 或 `else`。

# 结论

至此，你应该已经对 Java 编程及其用途有了基本的了解。你应该能够编写基础代码并构建自己的程序。

在本书中，你从学习 Java 最基础的功能开始，随着阅读的持续，内容会逐渐变得复杂。这样做是为了让你能够开始积累知识，以便在书中学习更困难的概念。

读完整本书后，你应该具备了获得基础 Java 认证所需的必要知识，但你仍然需要报名并参加课程才能考试。然而，如果你想获得认证，这本书将是一个极好的资源：由于本书的结构安排，你可以轻松找到内容并进行复习。

Java 就像真正的语言一样，需要通过练习才能变得精通。它的内容远比本书丰富的得多，从这里开始，你应该能够扩展知识，继续通往 Java 编程专家的道路。精通这种语言可以为你的职业发展打开许多大门，如果你只是想创建程序和应用程序，对个人也大有益处。

# 参考文献

Agarwal, H. (2019, July 8). Variables in java. GeeksforGeeks. https://www.geeksforgeeks.org/variables-in-java/

IBM Cloud Education. (2021, June 30). JVM vs. JRE vs. JDK: What’s the difference? Www.ibm.com. https://www.ibm.com/cloud/blog/jvm-vre-vs-jdk

Java keywords. (n.d.). Www.w3schools.com. https://www.w3schools.com/java/java_ref_keywords.asp

Krishna, A., Baid, A., & Gandhi, N. (2017, March 29). Operators in java. GeeksforGeeks. https://www.geeksforgeeks.org/operators-in-java/

Learn Java: Access, encapsulation, and static methods cheatsheet. (n.d.). Codecademy. Retrieved February 10, 2022, from https://www.codecademy.com/learn-java/modules/access-encapsulation-and-static-methods/cheatsheet

Romano, C. (2018, July 24). Thinking About errors in your code differently. Codecademy News. https://www.codecademy.com/resources/blog/errors-in-code-think-differently/

Tyson, M. (2020, January 17). What is the JDK? Introduction to the Java Development Kit. InfoWorld. https://www.infoworld.com/article/3296360/what-is-the-jdk-introduction-to-the-java-development-kit.html

Variables and types. (n.d.). Www.learnjavaonline.org. https://www.learnjavaonline.org/en/Variables_and_Types
