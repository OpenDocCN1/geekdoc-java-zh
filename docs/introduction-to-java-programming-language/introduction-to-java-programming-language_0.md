
# Java 编程语言入门指南

## 引言

本教材面向雅罗斯拉夫尔国立大学（YarGU）信息与计算机技术学院“信息系统支持与管理”专业的四年级学生。它描述了 `Java` 编程语言以及一些相关技术。书中还包含了一些关于面向对象软件编程和设计的通用信息。

前两章介绍了语言的基础——类型、运算和运算符。这些章节中的大部分材料通过 Java 语言工具与类似的 `C++` 语言工具进行了对比。

第 3–5 章阐述了面向对象编程的原理，并描述了实现这些原理的语言工具。特别关注了可能异常情况的处理，以及一些类设计问题。

第 6-8 章描述了 Java 标准库的特性。包括字符串数据处理、流式输入/输出，以及 Java 容器类的使用——这些应用程序中存储和处理数据的极其强大且方便的手段。

第 9–11 章对了一些 Java 技术进行了介绍。所提供的材料使我们能够学习相关技术背后的思想，并掌握这些技术的基础知识。

手册末尾列出了所讨论主题的主要和额外参考文献。在这些列表中，我想重点推荐书籍 [1]，它对语言机制的理解有非常详细且深入的阐述；还有一本可以作为语言主要工具（尤其是库）指南的书籍。我还推荐一本描述 Java 应用设计的书籍，学习它可能会显著提高程序员的专业水平。

## 1. 数据类型、字面量、变量

基本数据类型。Java 定义了 8 种基本数据类型。包括四种整数类型 `byte`、`short`、`int`、`long`，两种实浮型 `float` 和 `double`，字符类型 `char` 和逻辑类型 `boolean` 类型。其主要特征见表 1.1。与 `C++` 不同，Java 中没有“指针”数据类型。

Java 中基本数据类型的主要特征是，这些类型的变量不是对象。所有其他类型的变量（包括数组和字符串类型变量 `String`）都是对象引用（object references）。更多细节将在节 3.3 中讨论。

字面量。整数字面量可以用十进制、八进制和十六进制指定。十进制字面量直接写入，其余使用类似的前缀：八进制使用 `"0"`，十六进制使用 `"0x"`。例如，整数 47 可以表示为 `0x2F`。

`Long` 型常量必须带有 `L` 或 `l`（例如 `47L`）。浮点字面量必须带有 `F` 或 `f`（例如 `3.5F`）。`Double` 字面量必须带有 `D` 或 `d`（例如 `3.5D`）。

符号字面量仅限于引号。也可以使用 Unicode 表示。对于后者，字面量写为 `\u`。

布尔字面量 `true` 和 `false` 分别定义。

变量。在 Java 中声明变量与 `C++` 类似。任何变量可以在描述时初始化。与 `C++` 不同，不允许在内部块中使用相同名称进行声明。用 `final` 修饰符声明的变量是不可变的。例如：`final double PI = 3.14159265358973116`。

类型转换。Java 中的类型转换分为隐式和显式。隐式转换自动执行。强制转换（Casting）的规则要严格得多。

赋值时满足以下条件会进行自动类型转换：

- 整数类型或 `char` 转换为某种数值类型或实型
- 所需转换的类型范围更大

表达式中的自动类型转换在参数运算、字符串拼接时执行（更多细节见节 6.3）：

- 如果二元运算的操作数之一类型为 `double`，则第二个转换为 `double` 类型；
- 否则：如果操作数之一类型为 `float`，则第二个转换为 `float` 类型；
- 否则：如果操作数之一类型为 `long`，则第二个转换为 `long` 类型；
- 否则，两个操作数都转换为 `int` 类型。

这里需要注意最后一点。在某些情况下，它的应用可能会导致不自然的结果。例如，以下代码段在语言层是错误的：

```java
int x = 2.5;
```

错误是因为在给变量 `a` 的值加 1 时，结果已转换为 `int` 类型。由于从 `int` 类型到 `short` 的类型转换可能会溢出，因此必须显式地产生：

```java
short a = 5;
short b = (short)(a + 1); // 错误：需要 short，而不是 int
```

通过截断高位产生的收缩整数类型。将实数类型赋值给整数类型产品时，其截断是通过舍弃小数部分并应用之前的位完成的。

显式类型转换的语法与 `C` 中的强制类型转换相同（参见上文示例）。

最后，某些类型转换是无效的——此类转换包括：任何到 `boolean` 类型的转换、类到基本类型的转换，以及基本类型到类的转换（某些除外）等。尝试执行此类转换将在编译阶段导致错误。

数组。Java 中的数组是对象，因此它们都适用于处理对象的所有规则（参见第 3.3 节）。然而，由于数组独立于大多数广泛应用的数据结构，我们在这里对其进行讨论。

声明一维数组的语法与变量的描述类似，但在变量名或数据类型名后添加空方括号。例如：

```java
int a[]; // 第一种选择
int [] b; // 第二种选择
```

在这种情况下，数组本身并没有创建。要创建数组，请使用 `new` 操作：

```java
a = new int [50];
```

也可以同时添加和选择内存：

```java
int a[] = new int [50];
```

在创建时也可能初始化数组：

```java
int a[] = { 20, 50, 166, 72, 0, –53 };
```

`[]` 运算符用于访问数组的元素。数组元素从零开始编号。引用不存在的数组元素会导致运行时错误。数组支持通过示例长度变量获取其大小的信息。

多维数组是数组的数组。它们可以像一维数组一样创建：

```java
int a[][] = new int [5][2];
```

也可以创建非矩形数组。处理非规则数组的方法见下一个示例。

```java
// 示例：构建二项式系数表
public class Binomial {
    public static void main(String args[]) {
        final int N = ten;
        int c[][] = new int [N][];
        // 构建二项式系数表
        for ( int i = 0; i < N; ++i) {
            c[i] = new int[i + 1];
            c[i][0] = c[i][i] = 1;
            for(int j = 1; j < i; ++j)
                c[i][j] = c[i - 1][j - one] + c[i - 1][j];
        }
        // 输出表
        for(int i = 0; i < c.length; ++i) {
            for(int j = 0; j < c[i].length; ++j) 
                System.out.print("\t" + c[i][j]);
            System.out.println();
        }
    }
}
```

## 2. 操作与运算符

操作的一般特征。大多数 Java 操作与 C++ 操作相似，尽管它们中的某些功能略有不同。由于 Java 中没有指针，这是很自然的。没有用于获取地址 (`&`）、解引用 (`*`）和间接寻址 (`->`）的操作。Java 中的 `.`（点）运算符用于通过对象引用访问对象的字段和方法（详细信息参见第 3.3 节）。

接下来的段落描述了基本的 Java 操作。优先级操作在表 2.1 中。

算术操作。算术操作包括以下这些操作：保持和改变符号的一元操作 (`+` 和 `-`)；一元递、减运算符 (`++` 和 `--`)；加、减、乘、除和取余的二元运算操作 (`+`, `-`, `*`, `/`, `%`)，以及带赋值的操作 (`+=`, `-=`, `*=`, `/=`, `%=`)。

算术操作适用于数值类型，结果也是数值类型。整数类型的除法操作给出整数类型的结果（整数商），对于实数则如此。

如果在执行整数算术操作时发生溢出，则一个或多个高位结果可能会被截断（同时，由于最高位负责数字符号，可能会改变符号），且不会生成错误消息。整数算术中唯一导致错误的操作是除以 0。

比较操作。比较操作包括 `==`, `!=`, `<`, `>`, `<=`, `>=`。它们与相应的 C++ 操作的唯一区别是它们的结果始终是 `boolean`。

逻辑操作。逻辑操作适用于布尔参数并产生布尔结果。包括：一元操作“非” (`!`)，二元“与” (`&&`, `&`)，“或” (`||`, `|`) 和“异或” (`^`)，以及类似于赋值的操作 (`&=`, `|=`, `^=`)。

`&&` 和 `||` 只在情况下计算第二个参数的值。相反，`&` 和 `|` 总是计算两个参数。例如：

```java
int x = 10, y = 10;
if(x == 10 || ++y) System.out.println(y);
```

打印 `"ten"`，如果我们使用 `|`，结果将是 `"eleven"`。

条件操作。Java 有类似于 C++ 的条件运算符 `?:`：

```
condition ? expression1 : expression2
```

如果条件为真，则该操作的结果为 `expression1`，否则为 `expression2`。在这种情况下，未评估的表达式不会被计算。

赋值运算符与表达式运算符。所有的 Java 语句（与所有语言一样）都有返回值。除此之外，它们（在 C、C++ 中，但在其他语言中不是）也可以更改其操作数。此类操作包括 `++`, `--`, `=`, 以及所有带赋值的操作。

赋值操作是一种二元操作，将第二个参数的值赋值给第一个。第一个参数的赋值必须是 `lvalue`，即“允许赋值的”。赋值操作的结果等于第二个参数的值。例如，下一个操作：

```
x = y = ten;
```

将 10 赋值给变量 `y`，之后将操作的结果（即 10）赋值给 `x`。

表达式运算符。它的语法为：

```
expression ;
```

因此，在任何表达式后添加分号将其转换为运算符，这种组合操作的可能性允许一个运算符同时更改多个变量，这在使用赋值运算符时是不可能的。

与 C++ 不同，Java 有一个额外要求：包含在运算符表达式中的最后一个操作必须更改其操作数。例如，运算符：

```java
x + 1;
```

在 C++ 中是有效的，在 Java 中是无效的，因为它不改变变量的值。

控制流语句。当前的控制运算符包括：条件语句 `if`、选择语句 `case`、循环运算符 `while`、`do-while` 和 `for`、提前退出循环的运算符 `break` 以及跳转到下一次迭代的 `continue`，以及用于从函数返回 `return` 运算符。这些运算符的语法与 C++ 相似，但有细小的修改。

特别是，所有执行验证条件的运算符都要求条件具有布尔类型。这意味着，与 C++ 不同，`if (n)` 和 `if (n != 0)` 结构是不等价的，而且如果变量 `n` 的类型不是布尔类型，第一种写法在语法上是错误的。

`for` 语句就像在 C++ 中一样，可以在循环中声明任何类型的变量。例如：

```cpp
for (int i = 0; i < N; ++i)
```

以这种方式声明的变量在循环内部有效。你可以在 `for` 运算符的头部中使用多个表达式，并用逗号分隔它们：

```cpp
for (i = 0, j = 0; i + j < twenty; ++i, ++j)
```

`case` 语句中的控制表达式必须是整数类型之一。

Java 不包含 `goto` 语句。相反，它扩展了 `break` 语句和 `continue` 语句来退出多个嵌套循环。它们并不常见，因此在这里不被考虑。它们的描述可以在例如 [2] 这样的书书中找到。

需要注意的是，Java 不允许程序中存在不可访问的代码（例如，跟在 `return` 语句后面的代码），这会导致编译错误。

## 3. 类和对象

核心概念——面向对象编程。Java 编程语言支持面向对象编程（OOP）范式。OOP 的核心概念是类。类是由用户定义的共享数据类型。类可以包含字段（变量）和方法（函数）。类型为“类”的变量被称为对象（或类实例）。每个对象都有自己的类中某些字段的副本。字段的内容决定了该对象在任何给定时间的状态。每个类的一个实例存在一个方法，但是调用任何（非静态）方法只能通过指定的类对象执行。通常，该方法处理的是恰好属于被调用实例类的字段（改变它的状态）。因此，类方法决定了该类所有对象的行为。非常重要的一点是，类的字段或方法本身并不存在于该类的对象之外。

类的概念可以看作是结构体概念的演进，在结构体中处理数据的函数被放置在这些结构内部。同时，面向对象编程语言的中介属性允许禁止从外部访问对象数据，并仅通过方法处理数据。在这种情况下，我们说类方法为其数据提供了接口。

之前的介绍从技术角度（即从编程语言手段的角度）描述了类和对象的概念。然而，也可以给出另一种解释。面向对象编程相对于早期范式（结构化编程）的一个特点是，程序员有机会不仅仅为表示领域的数据处理机制选择语言环境，而是在程序内部对领域进行建模。在这种情况下，程序中的对象（大多数情况下）对应于领域的对象，而类则是预定义领域的通用概念，刻画了相同类型对象的属性和行为。这种编程方法通常是高效的（特别是在开发大型软件系统时，以及在集体开发中），因为程序员能够用领域的语言描述对象之间的交互，而不是用反映计算机内部工作细节的语言。

请注意，与开发面向对象应用原则相关的问题极其广泛，但对于任何专业程序员来说，认真处理这些问题都是必要的。为了进一步学习这些问题，建议首选书籍 [6]，以及书籍 [1, 3, 5, 7, 8]。

### 类声明

使用以下内容来声明一个类：语法如下：

```java
[access_spec] class class_name
{
    [access_spec] datatype field_name [ = initial_value ];
    [access_spec] datatype method_name ( argument_list )
    {
        // method_body
    }
}
```

类中字段和方法的声明顺序可以是任意的。可能的访问修饰符在 3.10 中描述。

构造函数的名称与类名相同，且没有返回值。如果没有显式声明类构造函数，则创建一个不带参数的空构造函数。

如果一个类有两个同名的方法，则这些方法被称为重载。所需的重载方法的选择由编译器根据传递给方法的参数数量和类型执行。不允许定义两个签名相同的方法（签名是指方法名和参数类型），否则编译器在这种情况下无法确定你应该调用哪种方法。

不支持默认参数。如果需要这种可能性，则你应该显式地实现所有必要参数的方法。

Java 不允许类之外存在代码，即没有不是字段的局部变量，也没有 C++ 意义上的函数。

### 对象的创建

在 Java 中，所有对象都是动态创建的。在虚拟内存中。在 C++ 中存在的变量对象在 Java 中不存在，类型为某个类的变量实际上不是对象，而是对象的引用。例如：

```java
MyClass myObject;
```

这声明了一个名为 `myObject` 的 `MyClass` 类型对象引用，但没有创建对象本身（在 C++ 中对应的将是指针声明：`MyClass* myObject`）。对象的实际创建通过 `new` 运算符完成：

```java
myObject = new MyClass();
```

这里创建了一个 `MyClass` 的对象（在创建时，调用了无参数构造函数），并将其引用写入变量 `myObject`。也可以同时完成对象的创建和它的初始化：

```java
MyClass myObject = new MyClass();
```

### 访问字段和方法

一旦对象创建，就可以通过 `.`（点）运算符访问它的字段和方法：

```java
myObject.someMethod();
```

当从同一个对象上调用的方法访问该对象的字段或方法时，可以省略对象的名称或用 `this` 关键字替换。`this` 关键字还用于从另一个 `constructor` 中调用 `constructor` `class`（参见下文示例）。在后者的情况下，此类调用必须是 `constructor` 中的第一条语句。

#### 示例

作为一个示例，考虑 `Box` 类（"box"），它存储某些箱子的尺寸（三个整数）。`Box` 类拥有具有不同参数的重载构造函数，以及一个计算箱子体积的 `volume()` 方法。`SimpleBoxDemo` 类演示了 `box` 类的创建和使用。

为了简化示例，没有使用访问控制（参见 3.10）。在实践中，任何程序员都不应该使用这种方法！



```java
/** Class "Box" */
class Box
{
    /** 尺寸绘制器 */
    int width, height, depth;
    /** 默认构造函数 */
    Box() { width = height = depth = 0; }

    /** 基本构造函数 */
    Box(int width, int height, int depth)
    {
        this.width = width; this.height = height; this.depth = depth;
    }

    /** 用于立方体的构造函数 */
    Box(int size)
    {
        this (size, size, size); // width = height = depth = size;
    }

    /** 计算体积的方法 */
    int volume() { return width * height * depth; }
}

public class SimpleBoxDemo
{
    static void main(String args[])
    {
        Box b1 = new Box(5), b2 = new Box(5, 10, 20); b1.width = 10;
        System.out.println(b1.volume() + "\n" + b2.volume());
    }
}
```

## 对象的移除

在 Java 中，对象的移除操作不是手动的。在这里，自动垃圾回收机制取代了手动组装。为了确保该机制的工作，`JVM`（Java 虚拟机）会跟踪每个被创建对象的引用数量，一旦某个对象不再剩余引用，它就会成为移除候选对象。对象的移除是定期进行的，并且只有在需要释放的内存变得本质时才会进行。

自动垃圾回收允许规避大部分与内存泄漏相关的问题。遗憾的是，在某些情况下，Java 中仍然会出现此类问题。可以在书中找到示例。

Java 不提供析构函数。由于内存管理由 `JVM` 实现，因此对它们的需求并不常见。如果仍然需要，你应该定义自己的方法并显式地调用它们。这里的例子是内联类中的 `close()` 方法，用于执行 I/O 的关闭流程（参见第 7.1 页）。

## 静态字段和方法

静态字段和现有方法存在于每个类的实例，也就是说它们被该类的所有拷贝共享。声明静态字段和方法使用特殊的标识符 `static`：

```java
static int static_field = ten;
```

静态字段在类加载时初始化，可以是声明中指定的值（参见章节 3.5 的示例），也可以在特殊的 `static` 块中初始化。静态方法无法（在不显式指定对象的情况下）访问类的非静态字段和非静态方法。

调用静态字段和方法可以在没有类实例的情况下进行。在这种情况下，通常使用类名而不是实例名。例如：

```java
double x = Math.sqrt(2.0);
```

作为所有 Java 程序入口的 `main()` 方法必须声明为 `static`（参见第 3.5 页的示例）。

带有参数和特殊特性的方法使用对象链接。对象引用的行为类似于 C 中的指针，因此将一个对象引用赋值给另一个不会导致对象的拷贝。要执行对象的拷贝，类通常会实现一个拷贝构造函数以及可能可能的 `clone()` 方法。

基本类型通过值传递给方法。这同样适用于对象引用，因此对象本身是通过引用传递的（类似于在 C 中拷贝指针）。

让我们考虑使用对象引用时的一个典型错误。假设类 `point` 的实现如下：

```java
class point
{
    public double x, y;
    public point(double x, double y) {
        this.x = x;
        this.y = y;
    }
}
```

假设我们想要交换两个 `point` 对象：

```java
void swap(point p1, point p2) {
    point temp = p1;
    p1 = p2;
    p2 = temp;
}
```

如果使用以下代码：

```java
void swap(point p1, point p2)
{
    p1.x = p2.x;
    p1.y = p2.y;
}
```

这是错误的，因为它只交换了内容，而不是对象本身。要交换对象，我们应该使用：

```java
void swap(point p1, point p2)
{
    double tempX = p1.x;
    double tempY = p1.y;
    p1.x = p2.x;
    p1.y = p2.y;
    p2.x = tempX;
    p2.y = tempY;
}
```

等待，如果我们想在调用方法中交换引用：

```java
void swap(point p1, point p2)
{
    point temp = p1;
    p1 = p2;
    p2 = temp;
}
```

这不起作用，因为变量 `p1` 和 `p2` 是方法的局部变量。为了解决这个问题，我们可以将 `point` 封装在一个类中：

```java
class Wrapper {
    point p;
    Wrapper(point p) { this.p = p; }
}

void swap(Wrapper w1, Wrapper w2) {
    point temp = w1.p;
    w1.p = w2.p;
    w2.p = temp;
}
```

最后，如果我们想交换 `point` 对象的内容：

```java
void swap(point p1, point p2)
{
    double tempX = p1.x;
    double tempY = p1.y;
    p1.x = p2.x;
    p1.y = p2.y;
    p2.x = tempX;
    p2.y = tempY;
}
```

## 包与翻译类模块的结构

包是 Java 程序中类型（类和接口）的分组手段。每个包可以包含一个或多个类以及其他包。通过包划分类可以解决命名冲突问题，并实现更高效的访问控制。引用包元素时使用完整路径，该路径由由点分隔的子包组成（例如 `java.util`）。

```java
package mypackage.mysubpackage;
```

如果缺少 `package` 语句，类将属于一个没有的默认包，该包没有子包且对其他包可见。

翻译模块可以包含一个或多个 `import` 语句，允许在引用类时省略包名。例如，如果模块中存在行：

```java
import java.util.*;
```

那么 `java.util` 包中的所有类（但不是其子包中的类！）都可以通过短名称访问。当导入单个类时，例如：

```java
import java.util.HashSet;
```

翻译模块必须包含 `main` 类（或接口）模块的源码。该类的名称应与翻译模块的文件匹配。该类是唯一可以声明为 `public` 的翻译模块类。该模块还可以包含一个或多个辅助类。

在环境变量 `CLASSPATH` 列出的目录中，搜索包含字节码类的文件，这些类位于与包分级结构中类的位置对应的子目录中。

例如，对于 JVM 找到的字节码类 `java.util.HashSet`，它必须位于任何目录环境变量 `CLASSPATH` 下的 `java/util` 子目录中名为 `HashSet.class` 的文件中。通常情况下，它包括当前目录以及包含标准 Java 库的目录。源文件也根据包的分级结构位于文件系统中。

## 访问控制与封装

访问控制主要用于：一方面，防止由于误用或恶意使用导致对象中包含的数据发生未经授权的更改；另一方面是将类的接口与其实现分离来（隐藏实现细节）。使用该类的程序员只能看到它的接口（具有公共访问权限的字段和方法），而可能对类的内部结构一无所知。这允许你更改类的实际实现，而对程序员是透明的。例如，你可以替换为一种更高效的实现，完全重构类的内部结构，而使用该类的程序代码无需更改即可与新版本共同工作。

将字段和方法放在类内部并隐藏实现细节被称为封装。封装是面向对象编程的一个特征。

访问控制通过在类、字段和方法的描述中设置特定的访问修饰符来实现。在 Java 中，类有两种访问修饰符，字段和方法有四种。所有这些连同作用域，都对应于表 3.1、3.2 中列出的程序现有元素。访问级别由其修饰符指定。此外还有“默认”（default）访问级别，它没有任何特殊的修饰符。

以下是在 Java 程序中使用访问控制的某些指南。

访问管理的核心规则：在设计程序的所有元素时，应该将访问级别设置为允许这些元素正常运行的最限制级别。类与类之间彼此的信息越少，它们就越可能被重复使用。

类字段使用 `private` 访问权限。为了从外部读取和更改它们的值，使用了特殊方法（setter 和 getter），这些方法具有 `public` 访问修饰符。例如：

```java
class MyClass
{
    private int value;
    public void setValue(int value) { this.value = value; }
    public int getValue() { return value; }
}
```

这种方法非常灵活。例如，你可以通过删除或简单地不重写相应的 setter，或者通过插入相关的检查来限制字段的可能值，从而将某个字段设为只读字段。

具有 `public` 访问修饰符的类方法构成了该类数据的接口。只有通过这些方法，外部类才能访问该类封装的数据，并且只有这些方法决定了处理这些数据的可能方式。

在存在继承的情况下（参见条目 4.1），元素的 `private` 和“默认”访问修饰符通常会被 `protected` 修饰符替换，以允许类的后类访问相应的类元素。如果整个后类层级都在同一个文件夹中（即与被继承类相同），也可以使用默认访问。

默认访问可以用于创建“友元”私有类，这些类可以访问彼此的私有字段和本地成员。此类友元类放在同一个包中。在这种情况下，访问控制的能力比 C++ 中的友元类更灵活。然而，不建议滥用这种可能性，因为友元类之间的关系比普通类更紧密，因此一个类中的更改可能需要其他类进行重大更改。

示例。以具有以下实现的“整数栈”类作为示例：

```java
/** “整数整数栈”类 */
public class IntStack
{
    private final int MAXLEN = 64;  // 栈的最大尺寸
    private int s[], size;

    /** 默认构造函数 */
    public IntStack()
    {
        size = 0;
        s = new int [MAXLEN];
    };

    /** 拷贝构造函数 */
    public IntStack (IntStack stack)
    {
        size = stack.size;
        s = new int [MAXLEN]; 
        for ( int i = 0; i < size; ++i)
            s[i] = stack.s[i];
    }

    /** 获取栈的大小 */
    public int getSize() { return size; }
    /** 在栈中记录元素 */
    public void push( int e) { s[size++] = e; }
    /** 从栈中弹出元素 */
    public int pop() { return s[--size]; }
    /** 检查栈是否为空 */
    public boolean isEmpty() { return size == 0; }
}
```

栈的状态由其当前的实际大小 `size` 和存储在 `s` 数组中的内容决定。对于字段 `size`，定义了 `getSize()` 方法来获取当前栈的大小。没有访问数组 `s` 的手段。通过 `push()`、`pop()`、`isEmpty()` 方法结合 `getSize()` 方法和两个类构造函数来定义栈数据的接口。注意，为了使用一个类，只需要这些方法的签名以及它们执行的操作的描述。在这种方法中，内部实现细节被隐藏了，并且很容易更改。例如，你可以将数组 `s` 替换为双链表，这不会影响使用 `IntStack` 的类。

对象比较。标准操作 `==` 比较的是对象的引用。但通常要求对对象的内容进行比较而不是引用。为此，`boolean equals(Object obj)` 方法定义在 `Object` 类中（参见节 4.1）并包含在所有类中。程序员必须重写此方法以便按要求的方式进行比较。例如，对于包含两个整数坐标 `x` 和 `y` 的 `Coords` 类（“平面点”），对应的方法可以实现如下：

```java
public boolean equals(Object obj)
{
    if(!(obj instanceof Point))
        return false;  Point c = (Point)obj;
    return x == c.x && y == c.y;
}
```

如果程序中使用了标准容器类（参见节 8.1），通常不仅需要重写 `equals()` 方法，还需要重写 `int hashCode()` 方法。哈希值——这是一个根据对象的状态（包含的字段）计算出的数字。相等对象（即 `equals()` 方法返回 true 的对象）必须具有相同的哈希值。对于不相等的对象，哈希值不一定不同。然而，应该尽力做到。此外，还应该考虑到哈希值的分布越均匀，所使用的内置集合（集合和关联数组）的性能就越好。

上述上述类可以定义 `hashCode()` 方法如下：

```java
int hashCode()
{
    return x + y;
}
```

基本类型的包装类。如前所述，Java 中的基本类型不是对象。但在某些情况下，需要将它们表示为对象（例如，为了存储在容器中，请参见第 8.1 节）。为此，它们被用作基本类型的包装类——封装基本类型的类。

对于八种基本类型中的每一种，都有一个对应的包装类。在创建这些类型的实例时，包装类会通过对应类的构造函数传递一个对象：

```
Byte(byte value) Short(short value) Integer(int value) Long(long value) Float(float value) Double(double value) Character(char value) Boolean(boolean value)
```

此外，除 `Character` 外，所有包装类都具有参数类型为 `String` 的构造函数。它们执行到对应基本类型的转换并封装生成的结果。

所有包装类都重新定义了方法 `equals()`、`toString()`（见第 3.12 页），并实现了 `Comparable<T>` 接口（见第 8.4 页）。

要执行从包装对象到基本类型的反转换，使用了以下方法：

```
byteValue() shortValue() intValue()
```

在相应的对象上调用 `...`。从 Java 1.5 版本开始，大多数转换都是自动完成的。所有包装类都是不可变的（immutable）。

包装类还包含静态方法：

```
static byte parseByte(String s) static short parseShort(String s) static int parseInt(String s)
```

这些方法可以用于转换为基本类型的转换。如果转换失败，将抛出 `NumberFormatException` 异常。

# 继承与多态

## 继承

继承是一种基于现有类构建新类的机制。同时，类 `ca` 的继承者（子类）获得了父类（超类）的属性和功能，并具有更改和扩展它们的能力。继承机制用于创建与超类相比更私有的、更专门的类。

为了声明一个类继承另一个类，使用 `extends` 关键字，后跟被继承的类名，并添加到类定义中：

```
[ 访问修符 ] class subclass_name extends superclass_name
```

Java 只允许从一个类进行继承。子类继承超类的所有字段和方法，然而，那些使用访问修饰符 `private` 和默认修饰符（后者仅当子类位于包含该类的类的包之外时）的对于子类是不可访问的。

子类可以重写超类的字段和方法。在这种情况下，对父类字段和方法的访问被关闭，并且只能通过子类方法通过 `super` 关键字执行，`super` 的语法与通过 `this` 显式访问当前实例元素的语法相同。例如，以下代码段显示了从同名类的子类方法调用 `overridenMethod` 方法：

```java
public void overridenMethod() {
    super.overridenMethod();
    // ...
}
```

在重新定义字段和方法时，可能会更改访问范围为更宽（从 `private` 改为其他；从默认改为其他，除 `private` 外）。

构造函数是不继承的，但子类需要构造函数。必然会调用其父类的构造函数。最后一点可以显式发生（为此，构造函数的第一条语句必须通过 `super` 调用父类的构造函数）或隐式发生（在这种情况下，默认调用构造函数）。父类构造函数的调用按照继承树从上到下的方式进行。

在下一个示例中，基于 "box" 类创建了一个更专门的 "weight box" 类，它添加了额外的实体字段 "weight" 以及获取它的方法，并且使用了对超类的构造调用。



```java
/** "Box" 类 */
class Box {
    /** 尺寸字段 */
    protected int width, height, depth;

    /** Getter */
    public int getWidth() { return width; }
    public int getHeight() { return height; }
    public int getDepth() { return depth; }

    /** 主要构造函数 */
    public Box(int w, int h, int d) {
        width = w;
        height = h;
        depth = d;
    }

    /** 立方体构造函数 */
    public Box(int size) {
        this(size, size, size);
    }

    /** 主要构造函数 */
    public int volume() {
        return width * height * depth;
    }
}

/** "带重量的 Box" 类 */
class BoxWeight extends Box {
    /** 重量 */
    protected int weight;

    /** 重的 Getter */
    public int getWeight() {
        return weight;
    }

    /** 基本构造函数 */
    public BoxWeight(int w, int h, int d, int weight) {
        super(w, h, d);
        this.weight = weight;
    }

    /** 立方体构造函数 */
    public BoxWeight(int size, int weight) {
        super(size);
        this.weight = weight;
    }

    /** 重写 */
    @Override
    public int volume() {
        return super.volume() * weight;
    }
}
```

如果类描述没有定义超类，则它继承自库类并包含正确运行所需的方法。

## 多态

多态是一种机制，允许你将从同一个类继承的对象视为该类的对象。通过这种方式访问子类对象，它们将按照相应子类定义的方式做出反应，而不是按照父类。在这种情况下，超类中定义的方法为所有子类形成了一个单一的数据访问接口。

Java 中多态的实现基于以下规则：

1. 类对象的引用可以强制转换为继承层次结构中给定类之上任何类的对象的引用。这种转换是扩展的，并且可以自动完成。反向转换也可以产生，但总是显式执行。在尝试将对象引用转换为无效类型时不会发生错误。为了检查转换的可用性，需要使用 `instanceof` 操作：

![](img/image00400.jpeg)

```java
if (myObject instanceof MyClass) ((MyClass) myObject).doSomethingSpecificForMyClass();
```

2. 如果父类的某些方法在子类中被重写，那么在访问这些方法时，即使通过父类对象的引用，也会调用对应的被重写方法。这与 C++ 中的多态实现不同，在上述情况下，只有当相关方法被声明为虚函数（`virtual`）时才会调用被重写的方法。

考虑一个例子。假设有一个“几何形状”的基类。它包含一个方法 `area()`，设计用于计算图形的面积。“shape”类的每个子类都重写了该方法，以计算相应几何图形的面积。

指向特定形状类实例的引用存储在一个类型为“shape”的引用数组中，然后进行统一的不同的处理：对于每个图形，显示其面积。这不需要任何形状类型检查，因为每个形状都会自动调用所需的方法。

```java
/**  抽象类 "Geometric figure" */
abstract class figure
{
    /**  计算图形面积的方法 */
    abstract public double area();
}

/**  类 "Rectangle" */
class Rectangle extends figure
{
    private double a, b;
    public Rectangle(double a, double b) { this.a = a; this.b = b; }
    public double area() { return a * b; }
}

/**  类 "Circle" */
class Circle extends Figure
{
    private double r;
    public Circle(double r) { this.r = r; }
    public double area() { return Math.PI * r * r; }
}

/**  类 "triangle" */
class triangle extends figure
{
    private double a, b, c;
    public Triangle(double a, double b, double c)
    {
        this.a = a; this.b = b; this.c = c;
    }
    public double area()
    {
        double p = (a + b + c) / 2;
        return Math.sqrt(p * (p – a) * (p – b) * (p – c));
    }
}

public class FiguresPolymorphism
{
    public static void main(String args[])
    {
        figure f[] = new Figure[3]; //  引用对象数组
        f[0] = new Rectangle(2, 3); f[1] = new Triangle(3, 4, 5); f[2] = new Circle(1);
        for(int i = 0; i < f.length; ++i) System.out.println(f[i].area());
    }
}
```

## 接口

Java 不允许一个类继承多个类。然而，存在多重继承的局限模拟形式，即“一个类实现多个接口”。函数式接口接近抽象类，但带有某些限制（只允许抽象方法和静态字段），但任何类都可以实现（作为继承的模拟）多个接口。

对于接口的定义，使用以下语法：

`interface interface_name [extends list_of_interface_ancestors_names]`

接口的所有方法隐式接收修饰符 `abstract public`，所有接口变量都是 `final static public` 修饰符，并且必须在声明时初始化。不允许在接口中使用特定的访问访问符。

任何类都可以实现任意数量的接口。对于一个类，实现一个或多个接口，遵循以下语法：

`[access_spec] class class_name [extends superclass_name] implements list_of_interface_names`

接口名称列表的元素用逗号分隔。如果类被声明实现某些接口，则它必须实现这些接口中声明的所有方法，或者该类必须是抽象类。

### 接口引用

就像将类对象的引用转换为其父类对象的引用一样，可以将此类引用转换为该类所实现的任何接口的引用。这种引用的行为与抽象类对象的引用行为完全一致。例如：

```java
interface Ifc1
{
    void f();
}

interface Ifc2
{
    void g();
}

class MyClass implements Ifc1
{
    public void f() { };
    public void g() { };
}

public class InterfRef
{
    public static void main(String args[])
    {
        MyClass m = new MyClass();
        Ifc1 ir = m;
        ir.f();
        ((Ifc2)m).g();
        Ifc2 ir2 = m;
        ir2.g();
    }
}
```

## 使用继承和多态的指南

开发类时应构建层次结构：子类更私有，……抽象类是一个抽象实体，其细节未完全描述。不遵循这一原则会导致严重的设计错误，体现在类中，增加后续阶段设计的难度。

…… 尽管抽象类和接口之间存在明显的相似性，但通常它们的用途是有些不同的。……一种匹配抛出的异常对象的类型，或者其后继（不一定是直接后继）的类型。按照以下规则进行搜索：

## 5. 异常处理

### 异常概念

异常提供了一种面向对象的机制用于处理程序运行期间的异常情况。与传统的错误处理方法（如返回特殊值或在 C 中使用 `setjmp()` 函数和 `longjmp()`）相比，这种机制允许以更简单、更符合概念的方式处理此类情况。

### 抛出和处理异常

为了抛出异常，使用以下语法：

`throw exception object;`

……必须通过接口来实现。一个例子是 `Comparable<T>` 接口（见第 8.4 节）。任何允许实例排序的类都可以实现此接口。抛出异常的语句必须放在特殊的 `try` 块中，并紧跟其异常处理器：

```java
try
{
    exception-throwing-operators
}
catch (exception_class_name variable_name)
{
    exception_handler_body
}
...
[finally
{
    operators
}]
```

如果抛出异常的语句不在 `try` 块中，则该方法将退出并继续搜索。这一过程会在调用者方法中进行（可能会重复多次），直到调用该方法的其中一个语句位于 `try` 块中。

处理器将在紧随该 `try` 块的 `catch` 块中进行搜索。

如果未找到合适的处理器，搜索将继续在与外层 `try` 块相关的 `catch` 块中进行（在此也可能发生从一个或多个方法中退出）。

如果完全没有找到合适的处理器，异常将由默认处理器捕获，它会打印异常的描述、堆栈跟踪并结束程序运行。

如果找到了合适的处理器，则将执行它，异常对象将作为参数传递给处理器。在处理器执行结束时，控制将转移到紧邻处理完异常块的所有 `catch` 块之后的运算符。

子类异常处理器必须在父类异常处理器之前存在。否则，所有此类异常将由父类异常处理器处理，导致代码中不可用。

在 `finally` 运算符块处，该块的执行不取决于是否抛出了异常：

- 如果发生异常并被处理，`finally` 块会在异常处理器后执行；
- 如果未找到处理器，则 `finally` 块会在包含块内搜索处理器之前执行；
- 如果通过 `return` 运算符完成 `try` 块的退出，则 `finally` 块将在退出方法之前执行。

### 示例

考虑一个对段落 3.11 中 `ra` 的改进示例。这个“整数栈”类的实现实现了对栈操作正确性的检查，并在发生错误时抛出 `vaet` 异常。

```java
/**  “整数整数栈”类 */
class IntStack
{
    private final int MAXLEN = 64; // 栈的最大尺寸
    private int s[] = new int[MAXLEN], size = 0;

    /** 获取栈的大小 */
    public int getSize() { return size; }

    /** 在栈中压入元素 */
    public void push(int e)
    {
        if (size < MAXLEN) s[size++] = e;
        else
            throw new RuntimeException("Overflow stack");
    }

    /** 从栈中弹出元素 */
    public int pop()
    {
        if (size != 0) return s[--size];
        throw new RuntimeException("In stack No elements");
    }

    /** 检查栈是否为空 */
    public boolean isEmpty() { return size == 0; }
}

public class IntStackExample
{
    /** 从栈顶移除 n 个元素并打印到屏幕上 */
    static void popAndPrint(IntStack st, int n)
    {
        for (int i = 0; i < n; ++i) System.out.println(st.pop());
    }

    /** 程序入口 */
    public static void main(String args[])
    {
        IntStack st = new IntStack();

        try
        {
            st.push(3);
            st.push(5);
            st.push(7);
            popAndPrint(st, four);
        }
        catch (RuntimeException e)
        {
            System.out.println("Thrown out exception: " + e);
        }
    }
}
```

`IntStackDemo` 类的 `main()` 方法创建 `IntStack` 类副本并顺序向其放入三个元素，然后调用 `popAndPrint()` 方法，该方法尝试从栈中取出四个元素。当 `IntStack` 类的 `pop()` 方法尝试移除第四个元素时，会抛出一个异常。由于此方法不包含 `try` 块，因此它返回到 `popAndPrint()` 方法。该方法也不包含 `try` 块，因此继续并退出该方法，随后导致 `main()` 方法的 `catch()` 语句处理该异常。

程序的结论如下：

```text
7
5
3
thrown out exception: java.lang.RuntimeException: AT stack No elements
```

注意，通过多个方法“抛出”异常在它们处理过程中是典型的做法——异常在变得可能处理的上下文中被处理，而调用栈在不参与程序员参与的情况下进行“展开”。这一特性在许多方面决定了异常 `ny` 的巨大实用价值。

### 异常的层次类和从方法中抛出异常

Java 中所有的异常对象都必须属于类本身，继承自 `Throwable` 类，该类有两个子类：`Exception` 和 `Error`。当发生严重错误时，JVM 会抛出 `Error` 类型的异常。按照规定，程序员不应处理此类异常：

```java
catch (Exception e)
{
    // ...
}
```

关于异常有一个重要的特性，即 `Exception` 类及其子类的实例，但 `RuntimeException` 类及其子类除外。如果从方法中抛出此类异常，则其类型必须在头部中指定：

`[access_spec] datatype method_name(argument_list) [throws list_of_class_exceptions_thrown_by_method]`

否则，编译器将给出错误信息。这样做是为了引起程序员注意需要强制处理的异常情况。标准库中的异常相关的有：I/O 错误（`IOException`）、数据库访问错误（`SQLException`）以及其他。在抛出 `RuntimeException` 类及其子类实例的异常时，不需要特殊的声明。在库中，这些异常包括：

- `ArithmeticException`：不可接受的算术运算
- `IndexOutOfBoundsException`：访问数组不存在的元素
- `NullPointerException`：访问不存在对象的字段或方法

此类错误在正确的程序中不应该发生，但强制处理会导致源代码文本臃肿（例如，为了避免除以零而需要将每个操作放在 `try` 块中）。

# 字符串

## `String` 类

`String` 类是存储和处理字符串的主要类。

创建 `String` 类的副本可以使用以下构造函数之一：

- `String()`
- `String(String str)`
- `String(StringBuffer strbuf)`
- `String(char[] arr)`
- `String(char[] arr, int first, int count)`

第一个创建一个空字符串，第二个和第三个将 `String` 和 `StringBuffer` 对象的内容复制到创建的对象中。最后两个构造函数允许基于字符数组或其部分创建字符串。此外，任何类型为 `String` 的对象引用都可以通过分配字符串字面量来初始化：

```java
String filename = "data.txt";
```



`String` 类的一个可能出乎意料的特性是，该类的实例在创建后不能被更改（不可变性）。然而，这并没有给它们的使用带来限制，因为所有修改字符串的方法只是创建一个新的修改后的字符串，而保持运行中的字符串不变。让我们通过示例来解释这一机制是如何工作的：

```java
String s = "abcd";
s = s.toUpperCase();
```

在这里，`toUpperCase()` 方法创建一个包含字符序列 `"ABCD"` 的新字符串，并返回该字符串的引用，将其赋值给变量 `s`，变量的旧值被丢弃。原始字符串保持不变，由于没有更多对象引用，它将被汇编器垃圾回收器移除。

### 表中给出的 `String` 类主要方法。6.1

- `int length()`: 获取字符串长度
- `char charAt(int index)`: 提取字符
- `char [] toCharArray()`: 将字符串转换为字符数组
- `boolean equals(String str)`: 比较字符串相等性
- `boolean equalsIgnoreCase(String str)`: 忽略区分大小写的字符串比较
- `int compareTo(String str)`: 字典序字符串比较
- `int compareToIgnoreCase(String str)`: 忽略区分大小写的字典序比较
- `boolean startsWith(String prefix)`: 检查字符串是否以指定的子字符串开头
- `boolean endsWith(String suffix)`: 检查字符串是否以指定的子字符串结尾
- `int indexOf(String subStr)`: 从行开始或从指定位置搜索子字符串的第一次出现的位置
- `int indexOf(String subStr, int fromIndex)`: 从指定位置搜索子字符串的第一次出现的位置
- `int lastIndexOf(String subStr)`: 从指定位置搜索子字符串的最后出现的位置
- `int lastIndexOf(String subStr, int fromIndex)`: 从指定位置搜索子字符串的最后出现的位置
- `String substring(int beginIndex, int endIndex)`: 接收子字符串（不包含索引 `endIndex`!）
- `String substring(int beginIndex)`: 获取尾部字符串
- `String concat(String str)`: 字符串拼接
- `String toUpperCase()`: 字符串转换为大写
- `String toLowerCase()`: 字符串转换为小写
- `String trim()`: 移除字符串首尾的空格
- `String replace(String target, String replacement)`: 替换另一个字符串中的子字符串
- `boolean matches(String regex)`: 检查字符串是否符合正则表达式
- `String replaceFirst(String regex, String replacement)`: 替换第一个匹配正则表达式的子字符串
- `String replaceAll(String regex, String replacement)`: 替换所有匹配正则表达式的子字符串
- `String[] split(String regex)`: 根据正则表达式分割字符串（当分隔符为正则表达式）

### 正则表达式

正则表达式使用约定符号和元字符来描述文本行的结构，确定行的整体或其各个部分的属性。Java 标准库工具允许你检查字符串是否符合指定的正则表达式，并替换符合正则表达式的子字符串或其他子字符串。

Java 正则表达式中使用的元字符见表 6.2。正则表达式示例见表 6.3。

要检查字符串是否匹配指定的正则表达式，使用 `String` 类中的方法 `boolean matches(String regex)`。注意，由于它检查整个字符串是否符合正则表达式，在这种情况下使用符号 `^` 和 `$` 是没有必要的。

以下方法分别替换第一个和所有相关的正则表达式匹配：
- `String replaceFirst(String regex, String replacement)`
- `String replaceAll(String regex, String replacement)`

例如，以下语句替换了位于行尾的省略号为问号：

```java
someString.replaceFirst("\\.\\.\\.$", "?");
```

由于 `.` 是元字符，因此为了将其作为字面量使用，必须将其转义为 `\.`。在替换字符串中，你可以使用字符 `$` 后跟数字来表示分组：

```java
someString.replaceFirst("(.*)", "$1");
```

应该注意的是，如果行包含多个括号，它们必须被转义：`\\(`。

方法 `String[] split(String regex)` 允许使用正则表达式将字符串拆分为子字符串。结果以数组形式写入。例如：

```java
String[] m = "abc:de:f".split(":"); // 数组 m 填充 "abc", "de", "f"
```

结论，我们注意到正则表达式似乎是处理字符串数据最强大的工具，它们的能力比给定示例所展示的要广泛得多。关于正则表达式的更多信息可以在书籍 10 中找到。

### 字符串转换与拼接

`String` 类在意义上是 Java 中的一个特殊类，因为任何数据类型都可以转换为它。对于原始类型，这种转换赋予了它们自然的表示形式，对于对象，则调用 `toString()` 方法。

拼接操作由符号 `+` 表示。这是一个二元操作，其中一个参数必须是 `String` 类型。它执行参数到 `String` 的自动转换（如果需要）并合并结果行。注意，这是唯一一种隐式进行字符串转换的情况。还有一种带有 `+=` 的拼接赋值，其第一个参数必须是 `String` 类型（并且必须是左值），第二个参数可以是任意类型。

让我们给出一个使用字符串转换的示例。对于“平面上的点”类，可以如下方式定义到字符串的转换：

```java
class point {
    private double x, y;

    public String toString() {
        return "(" + x + ", " + y + ")";
    }

    public point(double _x, double _y) {
        x = _x;
        y = _y;
    }
}
```

在这里，双精度值到字符串的自动转换在返回语句的表达式中完成。定义的 `toString()` 可以按以下方式使用：

```java
point p = new point(2.0, 5.0);
System.out.println(p); // 屏幕输出结论：(2.0, 5.0)
```

为了获取并在屏幕上显示对象的字符串表示，`println()` 方法会导致 `point` 类的 `toString()` 方法。

有时需要查看字符串表示。可以使用 `String` 类的静态方法 `format()`：

```java
static String format(String format, Object... args)
```

它接受一个格式字符串和任意数量的表达式，并将它们按照特定的格式字符串转换为格式化字符串。编写格式字符串的规则通常对应于 `C` 语言中 `printf()` 函数的编写规则。例如：

```java
System.out.println(String.format("%04d%4.1f", 25, 3.58));
```

将输出 "0025 3.6"。

### StringBuffer 类

`StringBuffer` 类设计用于处理可变字符串。该类的每个对象都包含一个缓冲区，用于存储字符串。当字符串发生变化时，缓冲区的大小可能会自动改变。

在程序中并不总是需要使用 `StringBuffer` 类的对象，因为所有这些相同的操作都可以使用 `String` 类的对象来完成。然而，在某些情况下，使用 `StringBuffer` 类可以提高程序的效率，因为它允许我们避免重复复制修改过的字符串。

创建 `StringBuffer` 类的实例使用以下相应的构造函数：

- `StringBuffer()`
- `int length()` 获取字符串长度
- `char charAt(int index)` 提取字符
- `char setCharAt(int index)` 修改字符
- `StringBuffer append(String str)`
- `StringBuffer append(int i)`
- `StringBuffer append(Object obj)`
- `. . .`
- `StringBuffer insert(int index, String str)`
- `StringBuffer delete(int beginIndex, int endIndex)`
- `StringBuffer replace(int beginIndex, int endIndex, String page)`

在末尾添加字符串（对于所有基本类型和对象类型都有重载版本）
在给定位置插入字符串
删除子串
将一个子串替换另一个
`StringBuffer reverse()` 反转字符串

#### 表 6.4 `StringBuffer` 类方法

- `StringBuffer(int capacity)`
- `StringBuffer(String str)`

前两个创建一个从开始存储空字符串的对象。第一情况下缓冲区长度为 16，第二情况下为给定长度。第三个构造函数使用给定字符串初始化缓冲区。在这种情况下，缓冲区的大小设置为字符串的长度，并增加 16。

表 6.4 给出了 `StringBuffer` 类的主要方法。

与 `String` 类修改方法不同，`StringBuffer` 类的相似方法直接修改它们被调用的副本对象。在此过程中，它们返回该对象的引用（`this`）。这样做是为了能够将对字符串的一系列顺序操作组合成一个表达式，就像在标准库语言 `C` 中实现一样：

```java
StringBuffer sb = new StringBuffer("abc"); sb.append("ef").reverse();
System.out.println(sb); // 在屏幕上显示：fedcba
```

# 7. 输入输出

I/O 流。Java 中的输入/输出意味着流类。所有的流都分为字节流和字符流。字节流设计用于传输二进制数据，而字符流用于传输文本。为了在字符流中表示信息，使用了 Unicode。Java 流库的设计使得无论传输数据的源头和接收端如何，数据输入/输出几乎是相同的。这一特性是由于所有当前类都继承自同一个抽象类，这些抽象类决定了用户应用程序与流交互的方法。输出流超类是 `InputStream` 和 `OutputStream`，字符流是 `Reader` 和 `Writer`。这些类的主要方法列在表 7.1, 7.2 中。

在发生 I/O 错误时，流类的方法会选择抛出 `IOException` 类或其子类（例如 `FileNotFoundException`）的异常。这些异常类本身不是 `RuntimeException` 类的子类，因此必须进行处理。

用于 I/O 的类放在 `java.io` 包中。

```java
void write(int a) throws IOException 向流中写入一个字节/字符
void write(} a) throws IOException 从当前流写入数组内容
void write(} [] a, int offset, int len) throws IOException 将数组的部分内容写入流
void flush() throws IOException 重置缓冲区，刷新到流
void close() throws IOException 关闭流
```

与文件相关的字节流。与文件相关的字节流用于处理二进制文件。

```java
int read() throws IOException 从当前位置读取一个字节/字符（如果到达文件末尾则返回 -1）
int read(} [] a) throws IOException 从流读取并填充数组内容（返回实际计数的字节/字符数）
int read(} [] a, int offset, int len) throws IOException 从流读取并填充数组部分内容
boolean ready() throws IOException 检查流中数据的可用性（如果方法返回 false，则后续对 `read()` 方法的调用将等待数据，并在接收到数据时才完成）。该方法仅由接口 `Reader` 定义！
long skip(long n) throws IOException 跳过流中给定数量的字节/字符
void close() throws IOException 关闭流
```

字符流是字节流的包装。由于 Java 中所有的字符信息都以 Unicode 表示，而外部数据通常以其他编码表示，因此为了让 Java 与外部世界有效通信，需要编码转换。此操作由符号包装流执行。它们可以结合任何字节流（“包装”它）并允许接收到的流被视为符号，从而执行所有必要的转换。

这些流对应于 `InputStreamReader`（将字节流读取的数据转换为 Unicode）和 `OutputStreamWriter`（将 Unicode 字符数据转换为字节流）。创建类数据对象使用以下构造函数：

```java
InputStreamReader(InputStream in)
InputStreamReader(InputStream in, String charSet)
OutputStreamWriter(OutputStream out)
OutputStreamWriter(OutputStream out, String charSet)
```

所需的编码由参数 `charSet` 决定。如果没有指定，则使用系统默认编码。

与文件相关的字符流。与文件相关的字符流用于处理文本文件。实际上，它们是字节流和执行转换的字符包装流的结合体。在这种情况下始终使用默认编码。

这些流对应于 `FileReader` 和 `FileWriter` 类，具有以下构造函数：

```java
FileReader(String filename) throws FileNotFoundException
FileWriter(String filename) throws FileNotFoundException
FileWriter(String filename, boolean append) throws FileNotFoundException
```

它们的使用方式与字节流构造函数相同。`当前文件，相关文件`（参参见第 7.2 页）。

## 字符打印流

字符打印流（对应的类是 `PrintWriter`）是另一个字符流的包装流，它为流输出添加了格式化功能——方法 `print()` 和 `println()`。它们针对所有基本类型的参数和 `Object` 类型进行了定义。在后者的情况下，在流输出性能字符串对象时存在性能问题（参参见第 6.3 页）。

### PrintWriter 构造函数

为了创建 `PrintWriter` 类的对象，使用了以下构造函数：

```java
PrintWriter(Writer out)
PrintWriter(Writer out, boolean autoFlush)
```

注意，`PrintWriter` 类在流中出现符号转换操作时，不会自动将缓冲区中的内容刷新到文件。只有在使用 `println()` 方法时，且在创建对象时参数 `autoFlush` 的值设置为 `true`，才可能自动刷新。

在 Java 较新版本中，`PrintWriter` 类包含了允许你连接字节流甚至文件字节流的构造函数：

```java
PrintWriter(OutputStream out)
PrintWriter(OutputStream out, boolean autoFlush)
PrintWriter(String filename) throws FileNotFoundException
PrintWriter(String filename, String charset)
```

这些构造函数只是创建了中间类型 `InputStreamWriter` 和 `FileInputStream` 的对象，并对它们进行了连接。

注意，与 `PrintWriter` 类同时还存在一个具有相似功能的 `PrintStream` 类。在新的 Java 程序中，不建议创建此类类的对象，但这种类型的对象拥有 `System.out`（标准输出流）和 `System.err`（标准错误流）。这是由于历史原因。

## 缓冲流

缓冲流是其他流的包装器。它们通过缓冲来提高 I/O 操作的效率。缓冲流的功能由 `BufferedInputStream`、`BufferedOutputStream`（带缓冲的输入输出字节流）以及 `BufferedReader` 和 `BufferedWriter`（类似的字符流）提供。为了创建这些类的对象，使用了构造函数，并将被包装的流作为参数传递：

```java
BufferedInputStream(InputStream in)
BufferedOutputStream(OutputStream out)
BufferedReader(Reader in)
BufferedWriter(Writer out)
```

此外，缓冲输入字符流增加了方法



`String readLine() throws IOException`

用于从输入符号流中读取一行。当到达文件末尾时，该方法返回 `null`。

## 控制台 I/O

Java 中的标准输出流和错误流由 `System.out` 和 `System.err` 对象表示，它们的类型为 `PrintStream`（参见第 7.5 节）。功能上，它们与字符打印流相似，因此对于输出，通常使用 `print()` 和 `println()`，例如：

```java
System.err.println("这一行输出到标准错误流");
```

标准输入流的情况稍微复杂。在 Java 中，它对应于 `System.in` 对象，但由于历史原因，它不是字符流，而是字节流，且从其读取输入数据需要转换为 Unicode。后者可以使用包装线程 `InputStreamReader` 完成：

```java
Reader in = new InputStreamReader(System.in);
```

因为通常从标准输入流是逐行读取而非逐字符读取，所以经常使用另一种包装类型 `BufferedReader`：

```java
BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
```

之后可以使用创建的流的 `read()` 和 `readLine()` 方法：

```java
String s = in.readLine();
```

**示例**

接下来的程序将输入文件中仅包含数字（由空格分隔）的行显示在输出文件中。输入和输出文件名通过命令行参数传递给程序。为了定义应该输出到输出文件的字符串，使用了正则表达式（参见第 6.2 页）。

```java
import java.io.*;

class NumbersCopier {

    /** 程序入口 */
    public static void main(String args[]) {
        if (args.length != 2) {
            //
        }

        try {
            //
            System.out.println("程序调用方式错误");
            return;

            BufferedReader in = new BufferedReader(new FileReader(args[0]));
            PrintWriter out = new PrintWriter(args[1]);
            String s;

            while ((s = in.readLine()) != null) {
                if (s.matches("[0-9]+")) {
                    out.println(s);
                }
            }

            out.close();
            in.close();
        } catch (IOException e) {
            System.out.println("I/O 错误");
        }
    }
}
```

# 容器

容器概述。容器是存储其他对象。它们在组织方式、执行基本操作（添加、提取和删除）的时间上有所不同，Java 中支持的容器可以分为三组：数组、集合和关联数组。数组在第 1.5 节中讨论过。它们的特征是创建后无法调整大小。Java 中的所有其他容器在添加和删除时都会动态改变大小。

集合组最大的组。Java 中所有的集合类都是泛化类型（泛型）。泛化类型是一个类或接口，其泛参数是在创建对象时必须指定的类型名称。泛化类型类似于 C++ 模板，其设计初衷是为了确保在编译时对正确类型的控制。它们代表了一种非常灵活且复杂的机制，详细的考虑超出了本手册的范围。关于泛化类型的详细信息可以在文章找到。Java 集合类的参数是它们可以存储的对象类型（在此处及后续，该类型用字母 `E` 表示）。

`Collection<E>` 接口。该接口的基本方法见表 8.1。它们都对应于这些实际上独立于集合类型的操作。常用的集合数量包括动态数组、双向链表、集合和有序集合。实现这些集合功能的类描述在第 8.3 页、第 8.5 页。

关联数组（也使用“字典”和“显示映射”术语）比集合更复杂的数据类型。实际上它们表现为数组，使用如下：

- 在集合中添加元素（成功时返回 `true`）。
- `boolean remove(Object o)`：从集合中删除元素。
- `boolean contains(Object o)`：验证集合是否包含元素。
- `int size()`：获取集合中的元素数量。
- `boolean isEmpty()`：检查集合是否为空。
- `boolean equals(Object o)`：比较集合的相等性。
- `Iterator<E> iterator()`：获取集合的迭代器。
- `Object[] toArray()`：将集合内容按照迭代器的顺序复制到数组中。

## 表 8.1. `Collection<E>` 主要接口方法

包含任意对象而非索引。它们在第 8.6 页中详细描述。

## 迭代器（Iterators）

迭代器用于按某种顺序遍历集合。使用迭代器是遍历集合所有元素的最快方法。迭代器类实现了 `Iterator<E>` 接口，该接口定义了三个方法：`hasNext()`、`next()` 和 `remove()`。

通过调用相应集合对象的 `iterator()` 方法可以获取迭代器。初始时，迭代器设置在第一个元素之前。每次调用方法：

![迭代器示意图](img/image00401.jpeg)

```java
E next()
```

返回迭代器在调用之前的元素，并移动迭代器，将其置于返回元素之后。如果迭代器位于集合的最后一个元素之后，则 `next()` 方法将抛出 `NoSuchElementException` 类型的异常。在使用迭代器之前检查元素可用性的方法：

```java
boolean hasNext()
```

对于删除上一次返回的 `next()` 元素，可以使用方法：

```java
void remove()
```

仅允许在调用 `next()` 方法后调用一次 `remove()` 方法。在其他情况下，或者在完全没有调用 `next()` 的情况下，抛出类似 `IllegalStateException` 的异常。

以下示例考虑了使用迭代器输出包含 `MyClass` 类型元素集合的用法：

```java
for (Iterator<MyClass> it = collection.iterator(); it.hasNext(); )
    System.out.println(it.next());
```

对于集合（以及数组），还有另一种可选方案，用于循环：

```java
for ([ type of data ] variable : collection)
```

它按照 `iterator` 指定的顺序遍历集合内容（对于数组，是从第一个元素到最后一个元素的顺序），而循环头中指定的变量将紧跟指向集合上元素的赋值链接。例如：

```java
for (MyClass e : collection)
    System.out.println(e);
```

## 列表与动态数组（Lists and dynamic arrays）

列表和动态数组——这些是按给定顺序包含任意元素的集合。此类集合中元素的顺序由它们的索引决定，如下与普通数组相同。所有提供此类集合性质功能的类都实现了 `List<E>` 接口（`Collection<E>` 的子接口），其方法见表 8.2。

对于所考虑的集合，定义在接口 `Collection<E>` 中的 `add()` 方法在集合末尾执行插入，而 `remove()` 方法删除指定元素的首次出现项。

标准库包含以下按给定顺序包含任意元素的集合：`LinkedList<E>`、`ArrayList<E>` 和 `Vector<E>`。

### `LinkedList<E>`

`LinkedList<E>` 类是以双向链表形式组织的集合。它提供了按 `O(N)` 时间复杂度根据索引获取元素，还提供了按 `O(1)` 时间复杂度在迭代器位置插入和删除元素。

为了创建 `LinkedList<E>` 类的副本，可以使用构造函数：

```java
void add(int index, E element) // 在指定位置添加元素

E get(int index) // 根据索引获取元素

E set(int index, E element) // 根据索引更改元素（返回旧元素）

E remove(int index) // 根据索引删除元素（返回被删除的副本）

int indexOf(Object o)

int lastIndexOf(Object o)

ListIterator<E> listIterator()

ListIterator<E> listIterator(int index) // 搜索第一个/最后一个元素（如果失败，则返回 -1）

// 接收在给定元素列表开始建立的列表迭代器

LinkedList()

LinkedList(Collection<? extends E> c)
```

除了 `List<E>` 接口中声明的方法外，`LinkedList<E>` 类还提供了插入、获取和删除列表第一个和最后一个元素的方法：

```java
void addFirst(E o)

void addLast(E o)

E getFirst()

E getLast()

E removeFirst()

E removeLast()
```

它们工作的时间复杂度均为 `O(1)`。

### `ArrayList<E>`

`ArrayList<E>` 类表示自己组织为变大小数组的集合。此类数组具有某些初始大小（默认 10），在必要时可以增长。它们以 `O(1)` 的复杂度通过索引获取元素。插入和删除元素需要 `O(N)`。为了创建 `ArrayList<E>` 类的副本，使用了：

```java
ArrayList()

ArrayList(Collection<? extends E> c)

ArrayList(int capacity)
```

`ArrayList<E>` 类表示自己组织为变大小数组的集合。此类数组具有某些初始大小（默认 10），在必要时可以增长。它们以 `O(1)` 的复杂度通过索引获取元素。插入和删除元素需要 `O(N)`。为了创建 `ArrayList<E>` 类的副本，使用了：

```java
ArrayList()

ArrayList(Collection<? extends E> c)

ArrayList(int capacity)
```

`ArrayList<E>` 类表示自己组织为变大小数组的集合。此类数组具有某些初始大小（默认 10），在必要时可以增长。它们以 `O(1)` 的复杂度通过索引获取元素。插入和删除元素需要 `O(N)`。为了创建 `ArrayList<E>` 类的副本，使用了：

```java
ArrayList()

ArrayList(Collection<? extends E> c)

ArrayList(int capacity)
```

## 对象的排序（Ordering of objects）

根据特定的比较操作对对象进行排序的方法在 Java 中称为自然排序（natural-ordering）。每个类最多定义一种自然排序方式。另一种排序方法是定义一个外部类（比较器），其对象将实现所需类对象的比较。`Comparator` 类必须实现 `Comparator<T>` 接口，其中参数 `T` 定义了由此比较器比较的对象类型。`Comparator<T>` 接口定义了方法：

```java
int compare(T obj)
```

Java 有两种标准方法来定义此类操作。在第一种，需要排序的对象类实现 `Comparable<T>` 接口。类型参数 `T` 必须替换为实现类的类名称。例如，如果有一个具有两个实部 `re` 和 `im` 字段的“复数”类，并且按照对应复数的模的升序或降序对该类对象进行排序，则 `compareTo` 操作可以定义如下：

```java
class MyClass implements Comparable<MyClass>

int compareTo(T obj)
```

它应该比较调用此方法的对象（`this`）与传递给此方法的对象；如果此对象大于 `obj`，则返回一个小于零的值；如果 `this.equals(obj)` 为 `true`，则返回零；如果 `obj` 对象大于此对象，则返回大于零的值。“大于”关系本身可以是任意的，并对应于排序的标准。

```java
int compare(T o1, T o2)
```

该方法比较作为参数传递的两个对象，并返回正数、负数或零的整数作为比较结果。

`compare()` 接口属于 `Comparable<T>`。

因此，在上面的示例中，与其使用 `compareTo()` 方法，你可以通过以下方式实现 `comparator`：

```java
class ComplexNumberLenComp implements Comparator<ComplexNumber> {

    public int compare(ComplexNumber c1, ComplexNumber c2) {
        double diff = (c1.re * c1.re + c1.im * c1.im)
                    - (c2.re * c2.re + c2.im * c2.im);

        return (int) (Math.sign(diff));
    }
}
```

很明显，对于一个类，可以定义任意数量的比较器，因此该方法通常用于程序对对象使用不同排序标准的情况。

许多标准容器处理算法以及自容器都要求你定义对象如何排序。在第 8.8 页介绍了在存储研究机构和处理导入数据时使用多种排序方法的示例。

### 集合与有序集合

集合（Sets）和有序集合提供了快速添加和删除元素的集合，但不允许对它们进行排序并保留重复。

`Set<E>` 接口以及实现的 `HashSet<E>` 类。它们与 `Collection<E>` 接口相比都没有增加新方法。存储类 `HashSet<E>` 使用哈希表，因此存储在集合中的对象必须实现 `equals()` 和 `hashCode()` 方法（见第 3.12 节）。由于哈希的存在，执行基本操作（添加、删除和检查元素在集合中的出现）的时间实际上与集合的大小无关。迭代器遍历集合元素的顺序被认为是任意的，因为是由元素的哈希值决定的。创建副本类 `HashSet<E>` 使用以下构造函数：

```java
HashSet()

HashSet(Collection<? extends E> c)
```

集合由 `SortedSet` 接口表示，并使用 `TreeSet<E>` 类实现它。后者使用平衡二叉树进行存储，这可以保证迭代器按升序遍历集合的顺序。添加、删除和检查元素出现的操作的时间复杂度为 `O(log N)`。

创建副本类 `TreeSet<E>` 使用以下构造函数：

```java
TreeSet()

TreeSet(Collection<? extends E> c)

TreeSet(SortedSet<E> s)

TreeSet(Comparator<? super E> c)
```

其中最后一个允许你根据构造函数中比较器确定的任意顺序创建集合（见第 8.4 节）。在所有其他情况下，集合的排序按照自然顺序进行。在这种情况下，元素类必须实现 `Comparable<T>` 接口。

### 关联数组

正如前面提到的，关联数组可以被认为是使用任意对象代替索引的数组。我们可以假设它们将一个键对象集合归约化为一个值对象集合。它们并不是传统意义上的集合，因为它们没有实现 `Collection<E>` 接口。它被 `Map<K, V>` 接口取代，该接口有两个选项。第一个定义了关联数组的键的数据类型，第二个是其值的类型。基本接口方法 `Map<K, V>` 见表 8.3。

关联数组用于存储集合容器的对。因此，两者的层次结构和属性都是匹配的：类 `HashSet` 和 `TreeSet` 分别对应类 `HashMap` 和 `TreeMap`，接口 `SortedSet` 对应接口 `SortedMap`。关联列表主要操作的执行时间与其相关的集合相同。

关联列表没有自己的迭代器。它们的遍历使用通过 `keySet()` 方法返回的键的集合迭代器。以下代码段演示了关联数组的使用：

```java
V put(K key, V value) // 添加键值对（返回与键关联的旧值，如果该键不存在则返回 null）

V get(Object key) // 获取值（如果键不在关联数组中则返回 null）

V remove(Object key) // 删除键值对（返回被删除的键值）

boolean containsKey(Object key) // 检查关联数组是否包含该键

int size() // 获取关联数组的大小

void clear() // 清空关联数组

boolean isEmpty() // 检查关联数组是否为空

Set<K> keySet() // 获取键集合
```

## 表 8.3. `Map<K, V>` 的主要方法

```java
TreeMap<String, String> capitals = new TreeMap<String, String>();

capitals.put("Russia", "Moscow");

capitals.put("France", "Paris");

capitals.put("Italy", "London"); // 不正确

capitals.put("Italy", "Rome"); // 修正
```



```java
System.out.println("Capital Italy: " + capitals.get("Italy"));

for (String s : capitals.keySet()) {
    System.out.println(s + ": " + capitals.get(s));
}
```

### 继承（遗留）类

除了 `ArrayList<E>`、`HashSet<E>` 和 `HashMap<E>` 之外，还有功能类似的类 `Vector<E>`、`Hashtable<E>` 和 `Dictionary<E>`。这些是所谓的遗留类（legacy classes）。它们的主要目的是提供向后兼容。尽管它们不被视为已过用，但在新程序中最好避免使用它们。

```java
E max(Collection<? extends E> coll)

E max(Collection<? extends E> coll, Comparator<? super T> comp)

E min(Collection<? extends E> coll)

E min(Collection<? extends E> coll, Comparator<? super T> comp)

void sort(List<T> list)

void sort(List<T> list, Comparator super super T> c)

int binarySearch(List<? extends T> list, T key)

int binarySearch(List<? extends T> list, T key, Comparator<? super T> c)

Collection<T> unmodifiableCollection(Collection<? extends T> c)

List<T> unmodifiableList(List<? extends T> c)
```

特别注意工厂方法，它们会返回不可变的容器包装器（`unmodifiableCollection()`、`unmodifiableList()` 等）。这些方法返回一个实现相应类型容器接口的对象。在使用返回对象进行估计和获取值的方法时，后者的表现方式与原始对象完全相同。当尝试调用任何容器修改方法时，会抛出 `UnsupportedOperationException` 类型的异常。

下面的示例演示了本章所描述工具的功能。

```java
void sort(int[] a) // Sorting array

void sort(T[] a, Comparator<? super T> c)

int binarySearch(int[] a, int key)

int binarySearch(T[] a, T key, Comparator<? super T> c) // 对对象数组进行排序，使用指定的比较器

// 在引用行数组中查找元素索引的二分查找。如果未找到元素，则返回一个等于（元素应该插入的位置减去 1）的值。

boolean equals(int[] a, int[] a2) // 数组的相等性比较

void fill(int[] a, int val) // 给给定数组的所有元素赋值

List<T> asList(T[] a)

List<T> asList(t...a) // 数组/集合转换为列表

import java.util.*;

/** 类 "问卷数据人类" */

class person implements Comparable<Person> {

    /** 用于接收的数据字段和方法 */

    private String name;

    public String getName() { return name; }

    private int age;

    public int getAge() { return age; }

    /** 构造函数 */

    public Person(String name, int age) {

        this.name = name;

        this.age = age;

    }

    /** 将对象转换为字符串 */

    public String toString() {

        return name + " (" + age + ")";

    }

    /** 等等性比较对象 */

    public boolean equals(Object obj) {

        if (!(obj instanceof Person))

            return false;

        return ((Person)obj).name.equals(name) && ((Person)obj).age == age;

    }

    /** 获取哈希码对象 */

    public int hashCode() {

        return name.hashCode() + age;

    }

    /** 姓名的比较对象 */

    public int compareTo(Person p) {

        return name.compareTo(p.name);

    }

}

/** 类 "用于年龄比较的比较器" */

class PersonAgeComparator implements Comparator<Person> {

    public int compare(Person p1, Person p2) {

        return p1.getAge() - p2.getAge();

    }

}

public class PersonsSortExample {

    public static void main(String[] args) {

        TreeSet<Person> data = new TreeSet<Person>();

        data.add(new Person("Petrov", 31));

        data.add(new Person("Ivanov", 45));

        data.add(new Person("Smirnov", 20));

        data.add(new Person("Smirnov", twenty)); // 此元素已存在

        System.out.println(data); // 结论：按姓排序

        // 将集合的内容复制到列表

        ArrayList<Person> data2 = new ArrayList<Person>(data);

        Collections.sort(data2, new PersonAgeComparator());

        System.out.println(data2); // 输出：按年龄排序

    }

}
```

这些程序的结论如下：

```text
[Ivanov (45) Petrov (31), Smirnov (twenty)]
[Smirnov (twenty), Petrov (31), Ivanov (45)]
```

# 9. 多线程编程

线程的创建与管理。多线程是一种组织程序执行的方法，其中程序的各个部分同时或伪同时地执行。

`Thread` 类封装了一个执行线程。该类的基本方法列于表 9.1。程序中的每个执行线程都对应该类或其子类的一个实例。通常情况下，程序会创建 `Thread` 类的子类，并重写作为流入口的方法。

```java
void run()
```

在创建当前类的实例时，相应的执行线程不会接收管理。要运行流，应该调用与其对应的：

```java
void start()
```

一旦调用了 `start()` 方法，相应的执行线程就会开始执行 `run()` 方法。这创造了同时执行的错觉。要验证某个流是否已经结束，可以使用对应对象的 `isAlive()` 方法。还可以暂停当前线程直到另一个线程完成。要实现此点，请使用 `join()` 方法。

```java
static void sleep(long millis) throws InterruptedException

void join() throws InterruptedException
```

运行中的线程可以通过调用 `sleep()` 方法自行进入睡眠模式。在这种情况下，处理器时间也会通过 `yield()` 重新分配给其他线程。

```java
void run() // 流的入口

void start() // 启动流

void isAlive() // 检查流是否结束

void interrupt() // 设置中断标记

boolean isInterrupted() // 获取中断标记状态

void setPriority(int newPriority) // 修改流优先级

int getPriority() // 流优先级

void setDaemon(boolean on) // 设置守护线程流
```

```java
if (!somethingHappened) yield();
```

有时有必要提前终止线程，并可能在未来恢复其执行。为了此，在 `Thread` 类中引入了 `stop()`、`suspend()` 和 `resume()` 方法，但后来它们被认为是不安全的，因为它们允许在停止线程之前执行诸如（例如）释放指定资源等操作，因此可能导致程序挂起或运行异常。在新程序中不应使用这些方法。

控制流的另一种方法是使用 `Thread` 类的特殊标志位 `interrupted`。为了中断当前执行流，使用了 `setInterrupted()` 方法。如果此时流处于挂起状态（调用了 `sleep()`、`join()` 等方法），则它将恢复工作，相应的方法抛出处会抛出一个异常。否则，将设置特殊标志位 `interrupted`。

线程必须通过调用 `isInterrupted()` 方法自行检查该标志位状态，并在已安装了 `interrupted` 标志位（即它被设置为 `true`）的情况下终止工作，例如：

```java
void run()
{
    boolean done = false;

    while (!done)  // 主循环流
    {
        if (isInterrupted())
        {
            // 执行最后的动作
            return;
        }
    }
}
```

每次调用方法 `isInterrupted()` 都会重置标志位 `interrupted`。注意，如果流不检查标志位 `interrupted`，可能会出现其在通常被禁止的情况下被停止的状况。

下面的示例演示了 `Thread` 类各种方法的使用。在这个示例中，主线程实例化了 `helloThread` 类，在独立的执行线程上于屏幕上输出“Hello, world!”短语，并在完成前制造了延迟。主线程反而在等待子线程完成，完成后显示一条消息，表示子线程已完成。

```java
class helloThread extends Thread {

    /** 流的入口点 */

    public void run() {

        System.out.println("Hello, world!");

        try {

            sleep(1000);

        } catch(InterruptedException e) {

            System.err.println("线程 MyHelloThread 被中断了");

        }

    }

}

public class SimpleThreadsExample {

    public static void main(String args[]) {

        Thread t = new HelloThread(); t.start();  // 启动流

        try {

            t.join();  // 等待流完成

        } catch (InterruptedException e) {

            System.err.println("主流被中断");

        }

        System.out.println("线程 MyHelloThread 结束");

    }

}
```

### `Runnable` 接口

有时需要向已有的类添加 `Thread` 类的功能。为了实现对 `Thread` 类的继承是不允许的，因为该类已经是其他类的子类。在这种情况下，可以使用 `Runnable` 接口。该接口只定义了一个方法 `void run()`，与线程类中的同名方法相似。

实现 `Runnable` 接口的类如下方式使用：创建该类的实例，并将其传递给线程类的构造函数：

`MyRunnableClass r = new MyRunnableClass(); Thread t = new Thread(r); t.start();`

有时将 `Thread` 类对象直接放置在实现 `Runnable` 接口的类内部，并在类的构造函数中初始化：

```java
class MyRunnableClass implements runnable {

    private Thread thread;

    /** 构造函数：创建一个 Thread 类对象并启动它 */

    public MyThread() {

        thread = new Thread(this);
        thread.start();

    }

    /** 流的入口点 */

    public void run() {

        // . . .

    }

}
```

### 同步

在多线程应用程序中，通常不需要让同一个对象或方法只被一个线程使用。为了提供这种可能性，使用了 `sync` 机制。

考虑一个可能需要同步的原始示例。

```java
class MyThread extends Thread {

    /** 构造函数（保存流名并启动流） */

    public MyThread(String name) {
        super(name);
        start();
    }

    /** 流的入口点 */

    public void run() {

        try {

        }

        System.out.print("[");
        Thread.sleep(1);
        System.out.print(getName());
        Thread.sleep(1);
        System.out.print("]");

        } catch(InterruptedException e) {

            System.err.println("线程 " + getName() + " 被中断");

        }

    }

}

public class SyncExample {

    public static void main(String[] args) {

        for (int i = 0; i < ten; ++i)

            new MyThread(String.valueOf(i));

    }

}
```

这个示例创建了 10 个线程，每个线程向控制台输出其方括号内的数字并终止。该程序的输出示例：

`[[[[[[[[[1[4320586]79]]]]]]]]]`

因为所有流都同时使用同一个对象（`System.out`），所以不同流的输出结果会混合在一起。并不难让你理解这种状况，即类似对象的联合使用可能会导致错误。

还应该考虑到，由于流之间的时间分布具有非确定性特征，因此错误可能不会在每个程序启动时出现，这增加了发现它们的复杂性。在示例中，如果在上面的示例中去掉（`sleep`），这种效果几乎永远不会发生。

同步的核心概念是监视器（monitor）。监视器是一个（隐式的）对象，用于互斥阻塞。在 Java 中，每个对象最初都有自己的监视器。当一个线程进入监视器时，会检查相应的块。如果此时另一个线程尝试进入同一个监视器，它将暂停直到第一个线程出来。

Java 中有两种同步类型：同步方法和同步块。

要使一个方法同步，只需在它的头部添加 `synchronized` 关键字即可。同步块（有时称为临界区）具有如下语法：

```java
synchronized (object_name) {

    // . . .

}
```

特别是在给出的示例中，将 `try` 内容放在同步块中：

```java
synchronized (System.in) {

    System.out.print("[");
    Thread.sleep(1);
    System.out.print(getName());
    Thread.sleep(1);
    System.out.print("]");

}
```




在这种情况下，首先进入`System.in`对象监视器的线程会挂起所有尝试进入同一个监视器的线程，只有在它完全完成结论后才释放监视器。然后监视器包含下一个流并继续。

# 10. 数据库数据访问技术：JDBC 架构

`JDBC` 是 Java 应用程序的平台无关数据库访问技术。它提供了一组数据访问接口，Java 应用程序通过它们与外部数据库驱动程序交互，并提供了集成这些外部驱动程序到 Java 中的工具。

这种方法足够灵活，因为 Java 应用程序不需要与数据库（DB）的交互细节分离。数据库只需要提供某些`JDBC`接口的实现即可，以便与 Java 应用程序兼容。

`JDBC` 类和接口托管在`java.sql`包中。关于`JDBC`技术的更多信息可以在书籍中找到[4, 5]。

## 数据库驱动程序

要连接到数据库，我们必须首先加载与所用数据库对应的驱动程序。Java 的标准发行仅包含这样一个驱动程序——`JDBC-ODBC`桥接。该驱动程序桥接了`JDBC`接口与连接 Microsoft 数据库的标准接口`ODBC`（开放数据库连接）。

这种方法虽然足够但通用，因为对于大多数数据库都有相应的`ODBC`驱动。然而，首选的连接方式仍然被认为是使用特定数据库的`JDBC`驱动，因为此类驱动通常比`JDBC-ODBC Bridge`功能更强、速度更快。此外，它们还可以提供跨平台的应用程序变性（使用`ODBC`通常只能在 MS Windows 上使用）。

`JDBC`驱动可以在大多数现有 DBMS 的交付中找到，或者通过互联网地址找到。

`JDBC`驱动通常以`jar`归档的形式提供，必须放在`CLASSPATH`列出的任何目录中（参见第 3.9 节），以便`JVM`找到所需的驱动程序。

加载驱动程序通过调用类静态方法完成：

```java
static class forName(String classname) throws ClassNotFoundException
```

在方法参数中传递驱动类名，例如：

```java
Class.forName("sun.jdbc.odbc.JdbcOdbcDriver");  // ODBC-JDBC 桥接驱动

Class.forName("com.mysql.jdbc.Driver");  // MySQL Connector/J 驱动
```

在无法下载驱动的情况下，将抛出`classNotFoundException`。

## 连接基础数据

连接基础数据对应于实现`connection`接口的对象类。

创建这些对象使用了静态方法：

```java
static connection getConnection(String url, String user, String password) throws SQLException
```

`DriverManager`类。该方法的第一个参数定义了连接到数据库的字符串，另外两个是用户名和密码。

### 连接字符串

其格式如下：

`jdbc:subprotocol_name:data_source_name`

这里，“name subprotocol”定义了数据库的驱动或协议插件，而“data source name”通常是数据库名称。连接字符串还可以包含额外参数，例如它们的格式，即数据源名称的格式，取决于特定的驱动。

例如，以下行可用于`JDBC-ODBC Bridge`驱动连接到本地计算机上名为“Clients”的数据库：

`jdbc:odbc:Clients`

相关的数据库必须先在`ODBC`管理器中注册。另一个示例是：

`jdbc:mysql://http://mydbserv.ru:3105/Students?useUnicode=true`

此类连接用于连接到位于地址[](http://mydbserv.ru/)的服务器 MySQL 上的远程数据库 students。连接将通过端口 3105 建立，传输的行将使用 Unicode 编码。

## 基础数据的创建和性能请求

对基础数据的请求封装在实现`Statement`接口的类中。每个此类对象对应不多于一个对象，表示产生的数据集。如果需要多个结果集，每个结果集都必须由单独的`Statement`对象生成。新的 SQL 查询会关闭由同一`Statement`对象创建的现有数据集。

创建请求使用了方法：

```java
Statement createStatement() throws SQLException

Statement createStatement(int resultSetType, int resultSetConcurrency, int resultSetHoldability) throws SQLException
```

在连接对象上调用。该方法的第二个版本允许设置结果集数据的安装选项。这些参数的可能值见表 10.1。为了执行数据库请求，使用了`Statement`接口中的以下方法：

```java
boolean execute(String sql) throws SQLException

ResultSet executeQuery(String sql) throws SQLException

int executeUpdate(String sql) throws SQLException
```

第一个方法通常用于不返回结果值的查询（例如，`DROP`），第二个方法用于返回数据集的查询（例如，`SELECT`）。第三个方法用于`INSERT`、`UPDATE`和`DELETE`。它返回添加、删除或更改的记录数。

处理结果后必须通过调用关闭请求：

```java
void close() throws SQLException
```

如果创建了结果，它将自动关闭。

下面的示例演示了如何通过 SQL 查询创建、填充和修改“people”表。

```java
// 加载驱动并连接数据库

String dbUrl = "jdbc:mysql://localhost/test?useUnicode=true";

Class.forName("com.mysql.jdbc.Driver");

Connection conn = DriverManager.getConnection(dbUrl, "");

Statement s = conn.createStatement();

// 创建表并填充

s.execute("CREATE TABLE people (Id INTEGER AUTO_INCREMENT PRIMARY KEY, Name VARCHAR(40), Telephone VARCHAR(10), Age INTEGER)");

s.execute("INSERT INTO people(Name, Telephone, Age) VALUES (' Ivanov', '12-02-00', 37)");

s.execute("INSERT INTO people(Name, Telephone, Age) VALUES (' Petrov', '43-55-47', 26)");

s.execute("INSERT INTO people(Name, Telephone, Age) VALUES (' Sidorov', '43-88-90', 59)");

// 修改和删除记录

System.out.println("Updated records: " + s.executeUpdate("UPDATE people SET Telephone= '63-16-00' WHERE Name= ' Petrov ' "));

System.out.println("Removed entries: " + s.executeUpdate("DELETE FROM people WHERE Name='Иванов'"));

s.close();
```

## 遍历数据集

数据集是实现`ResultSet`接口的对象类，封装了执行数据库查询的结果。数据集的能力由其参数定义。这些参数在对象创建时设置——请求`createStatement()`或`prepareStatement()`对象方法（见段落[10.4]、[10.7]）。

`rsType`参数指定数据集类型，`rsConcurrency`指定更新模式，`rsholdability`指定事务提交后游标保留模式。

数据集包含一个游标，允许你在该集的行之间移动。处理游标的技术与处理集合迭代器的技术非常相似（见第 8.2 节）。首先，初始游标放在第一行数据之前。

```java
boolean next() throws SQLException
boolean previous() throws SQLException
```

`allow`允许在字符串集中分别向前向后移动（光标保留在行之间！）。

### 方法

```java
boolean relative(int rows) throws SQLException
boolean absolute(int row) throws SQLException
```

`allow`允许在数据集中进行`relative`和`absolute`的光标定位。如果移动成功，指定的方法返回值`true`；如果请求的元素不存在，则返回`false`。

注意记录集的实现是基于单位的！为了将光标定位在第一个元素之前和最后一个元素之后，使用了以下方法：

```java
void beforeFirst() throws SQLException
void afterLast() throws SQLException
```

上述列出的方法除`next()`方法外，都仅在数据集不是单向的情况下（即读取参数`rsType`不等于`TYPE_FORWARD_ONLY`）有效。

为了获取数据集最后几行字段的值，当移动了任何定位方法（`next()`、`previous()`和`t.`等）后，可以使用以下方法：

```java
get***(int columnIndex) throws SQLException
get***(String columnName) throws SQLException
```

在这里，替代 Java 数据类型名称的是与参数对应的 SQL 数据类型（参见表 10.2）。所需的字段可以通过数据库中的名称或在请求中的编号来指定（字段编号从一开始！）。

除了`get***`方法，你还可以使用通用方法`vat`：

```java
Object getObject(int columnIndex) throws SQLException
Object getObject(String columnName) throws SQLException
```

它将请求字段的值作为对应已存在类型的对象返回（参见表 10.2）。如果该类型是基本类型，则返回其包装类（例如`Integer`代替`int`等，参见第 3.13 节）。

以下方法可以在屏幕上显示作为方法参数传递的任意表的内容。示例中使用了`ResultSetMetadata`类对象，它允许你获取数据集字段的数量和名称。关于此类的更多信息可以在 JDBC 的文档中查找到。

```java
/** 输出数据库表内容 */
public static void printDB(Connection conn, String tableName)
throws SQLException
{
    Statement s = conn.createStatement();
    ResultSet r = s.executeQuery("SELECT * FROM " + tableName);
    // 结果集元数据列 ResultSetMetaData md = r.getMetaData();
    for (int i = 1; i <= md.getColumnCount(); ++i) {
        System.out.print(md.getColumnName(i) + "\t");
        System.out.println();
    }
    // 输出表数据
    while(r.next()) {
        for(int i = 1; i <= md.getColumnCount(); ++i)
            System.out.print(r.getObject(i) + "\t");
        System.out.println();
    }
    s.close();
}
```

## 可修改的数据集

如果数据集仅包含一个数据库表的字段，且集合中包含该表的主键，同时`rsConcurrency`选项设置为`CONCUR_UPDATABLE`，则可以使用此类数据调用来修改相应的数据库表，而跳过显式的 SQL 语句。

为此使用了以下方法：

```java
void update***(int columnIndex, x) throws SQLException
void update***(String columnName, x) throws SQLException
```

更改通过调用方法记录在数据库中：

```java
void updateRow() throws SQLException
```

要从数据库中删除数据集的当前记录，使用方法：

```java
void deleteRow() throws SQLException
```

一种稍微复杂的方法是添加记录。首先，你需要将光标移动到数据集中要插入的特殊行。为此，使用了方法：

```java
void moveToInsertRow() throws SQLException
```

然后借助方法`update***()`完成对新增记录字段的填充。在表中产生新增记录的方法是：

```java
void insertRow() throws SQLException
```

为了让光标返回到插入之前的位置，使用了方法：

```java
void moveToCurrentRow() throws SQLException
```

下一个示例修改了第 10.4 节示例中从数据库中间修改的集合数据：

```java
Statement s = conn.createStatement(ResultSet.TYPE_SCROLL_INSENSITIVE, ResultSet.CONCUR_UPDATABLE);
ResultSet r = s.executeQuery("SELECT Id, Name, Telephone, Age " + "FROM people");

// 为所有人的年龄加 1
while (r.next()) {
    r.updateInt(4, r.getInt(4) + 1);
    r.updateRow();
}

// 添加新记录
r.moveToInsertRow();
r.updateString("Name", "Smirnov");
r.updateObject("Telephone", "26-08-58");
r.updateInt("Age", 43);
r.insertRow();
r.moveToCurrentRow();
s.close();
```

## 使用预编译查询

在这些场景中，当向数据库执行大量相似但仅参数不同的请求时，为了提高性能，你可以使用预编译查询。预编译请求对应实现`PreparedStatement`类的对象。

创建此类对象的方法是：

```java
PreparedStatement prepareStatement(String sql) throws SQLException

PreparedStatement prepareStatement(String sql, int resultSetType, int resultSetConcurrency, int resultSetHoldability) throws SQLException
```

在连接对象上。这些方法接受一个包含问号作为参数占位符的请求模式字符串，例如，

