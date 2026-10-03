
# 编程：Java、JavaScript、编码：编程指南：一天学会！（JAVA、HTML、Python、SQL、App、iPhone、网站设计、Word Press）

![](img/19cb7751e839eebf53a5a37b4de40341_0_0.png)

Os Swift 著

# Java 简介

Java —— 互联网时代最流行的编程语言之一，于1991年在太阳微型系统公司（Sun Microsystems）构思并开发。任何编程语言的演进都是由计算生态系统发展的需求驱动的——Java也不例外。

虽然用 C 或 C++ 编写的代码（Java 的强大前身）也可以在所有设备上运行，但为了让它们在特定设备上运行而每次都需要编译，成本是非常昂贵的。

Java 解决了这个问题，只需获取文本源代码 (`.java`) 并将其编译为中间字节码 (`.class`) 文件，然后该文件可以由任何运行解释器的设备——Java 虚拟机 (JVM) 解释。字节码的想法意味着代码变得与架构中性，只需要编译一次，就可以在任何运行 JVM 的设备上进行解释。

今天，Java 已经成为一种重要的编程语言，对于任何对编程感兴趣的人来说，了解 Java 基础是必不可少的。这本书正是为此目的而编写的。我想帮助任何几乎或没有之前编程经验的人轻松、有效地接触 Java 编程。

# 第1章：入门

## 安装

首先，我们需要准备好开发环境。初学者可以使用在线开发环境（`https://ideone.com/`）来执行小型代码段，但如果要执行的代码是一个完整的程序，则必须安装。Java 分为三种：

- 微型版 (J2ME)
- 标准版 (JSE)
- 企业版 (JEE)

对于个人使用，可以通过安装 `java` 来显示终端的版本。运行程序意味着指令 JVM 加载从源码编译的 `.class` 文件并从 `main` 方法开始执行。

## 代码结构

![](19cb7751e839eebf53a5a37b4de4031)

每个 Java 代码以 `.java` 结尾保存。每个 Java 程序包含一个或多个类。每个类包含一些方法定义。

## 语法与关键字的含义

```java
import java.io.*;
public class FirstProgram {
    public static void main(String[] args) {
        // 这是我的第一个 Java 程序
        System.out.println(" Hello World!");
    }
}
```

- `import java.io.*;` - 关键字 `import` 用于包含“包”，这些包包含了可以使用的预定义函数。
- `public class FirstProgram` - 这是类定义，关键字 `public` 表示该类对所有人可见，“class” 表示一个类定义。
- `FirstProgram` – 这是类的名称。具有 `main()` 函数的类名应与文件名相同。
- 类定义封装在 `{}` 中。
- `public static void main(String[] args) :` 这是程序的主部分。由于 `main()` 是驱动函数，它应该始终是 `public`。
- `static:` 你需要记住 `main()` 方法始终应该是 `static` 的，因为这提高了内存效率。
- `void:` 这是方法的返回类型。这意味着 `main()` 方法不会返回任何内容。
- `main:` 方法名称。解释器从 `main` 方法开始执行。

`main` 方法的参数总结如下：

- `String[] args` : 是传递给 `main` 方法的参数。该方法始终接收字符串数组作为输入参数，数组名称应始终为 `args`。注意数据类型大小写 `S`，因为 `String` 是 Java 中的一个类，所有类名都以大写开头。

要在标准输出控制台打印语句，使用 `System.out.println("");`。注意所有语句必须以分号 (`;`) 结尾。

你也可以使用 `System.out.print()` 显示输出，区别在于 `println` 在它打印的每个语句结束引入一个新行。

我们程序中 `main()` 方法内的另一个语句被称为“注释”语句。这些语句不会被编译，以 `//` 开头的语句仅用于向程序员提供有关代码的更多信息。

## 使用 Java 库

在处理 Java 工作时，你可以看到许多预定义的类。所有这些类都可以在 Java 程序中使用，从而避免了用户重复发明轮子的任务。但要使用这些类的任何一个，你应该对需要使用什么以及在哪里使用有一些最少知识。

为了找到它。这些被称为 Java API。该库无非是一堆巨大的预定义类，这些类可以在程序中的任何地方使用。它们包含了预定义的代码，用户需要知道的就是如何使用它们。这些库通过让用户输入长长的代码来减轻负担。这也称为 Java 标准代码库。在 Java 平台中，Java 标准库主要有三个用途。它们是：

- 就像其他库一样，Java 库为程序员提供了一系列实用的工具。这些工具包括正则表达式处理、容器类等。
- 标准代码库为用户提供了抽象接口，用户可以通过这些接口独立地执行任务。这样，用户就不需要为文件访问和网络访问等复杂过程编写完整的代码。
- 有少数底层平台不支持所有的 Java 应用程序。在这种情况下，你可以使用 Java 库来模拟这些功能，或者使用它提供一种检查特定功能是否存在的方法。

### Java 标准代码库的实现与配置

标准库中的大部分代码是用 Java 编写的。需要直接访问操作系统或硬件的代码除外。在这些情况下，使用 Java 原生接口（JNI）包装器来访问操作系统的 API。几乎所有的 Java 代码都存储在一个名为 `rt.jar` 的单一存档文件中。该文件由 JDK 和 JRE 分发。Java 类库可以在引导类路径（bootstrap class path）中找到。

### Java 类库的主要特征

我们使用类来访问 Java 类库的功能。这些属于包（packages）。下面是 Java 类库的一些主要特征：

- `java.lang` 包含所有的基础接口和类。它们与运行时系统和语言密切相关。
- 有一个专门用于数学运算的包，包含了数学表达式、求值和任意精度小数。它们都存在于 `java.math` 库中。
- 工具与集合：Java 为用户提供了内置的工具类和数据结构。这些工具类和数据结构可以用于数据压缩、日志记录、并发和正则表达式。
- 2D 图形和图形用户界面：用户可以使用 `AWT` 包，它提供了图形用户界面操作。该包绑定到原生系统。你可以用它来设计平台相关的工具包以及可插的外观和感觉。该包还可以用于可编辑和不可编辑的文本组件。
- 声音：此包为用户提供了可以用于写入、读取、合成和序列化声音数据的类和接口。
- 文本：`java.text` 接口用于处理文本、数字、消息和日期。
- 数据库：用户可以使用 `java.sql` 库访问数据库 (SQL)。
- `Java.Security` 提供了加密服务的安全功能。`javax.crypto` 库中存在加密服务。
- Java 还允许你访问脚本引擎。你可以使用 `javax.script` 包使用任何符合规范的脚本语言。
- 小程序（Applets）：`Java.applet` 包允许通过网络下载应用程序，并允许你在受保护的沙箱中运行它们。

# 第 2 章：面向对象编程

Java 的语法与 C 相似，但编程哲学源自 C++ —— 也就是说，Java 是一种面向对象的语言。

在我们看到的第一个示例中，我们有一个类声明，并说 `main()` 函数负责程序中执行的任务。嗯，这并没有让 Java 变成了一门 OOP 语言，让我们看一个例子来更好地理解 OOP —— 对象和类。

## 过程化方法

这并不那么简单，因为之前的形状是确定的，动画代码可以假设一个中心点并旋转形状；而对于变形虫这样的不规则形状，它无法使用其他形状的代码进行旋转，相反，API 需要更多的参数来定义形状应该旋转的坐标。

## 面向对象方法

所以你可以为每个形状写一个类文件，这样在添加变形虫或修改旋转方法时无需更改其他部分。

示例 1：

```java
class Movie {
}
```

示例 2：

```java
class Movie {
    public static void main(String[] args) {
    }
}
```

示例 3：

```java
class Test {
    public static void main(String[] args) {
    }
}
```

# 第 3 章：变量声明与数据类型

接下来的重要概念是关于变量和数据类型。变量基本上是存储值的内存位置。Java 是一种强类型语言，类型检查有助于安全性。

类型为 `x` 的变量可以存储值。

例如：

```java
int n;
```

Java 中的变量可以是：

- 局部变量（`int`、`float`、`double` 等基本数据类型）
- 引用变量（对象的实例）

假设你声明了一个类型为 `float` 的变量，需要在数字末尾附加 `f` 使其成为 `float` 字面量。

```java
float f = 1.5f;
```

变量命名的规则：

- 不要使用保留字作为变量名。
- 变量名不能以数字开头。

应该知道的一些流行关键字：

| abstract | assert | boolean | break | byte | case |
| --- | --- | --- | --- | --- | --- |
| catch | char | class | const | continue | default |
| do | double | else | enum | extends | final |
| finally | float | for | goto | if | implements |
| import | instanceof | int | interface | long | native |
| new | package | private | protected | public | return |
| short | static | strictfp | super | switch | synchronized |
| this | throw | throws | transient | try | void |
| volatile | while | | | | |

表 1-1 关键字

## 字符串

`String` 被声明为一个类。字符串常用的操作有：

```java
String str = "Hello World"; // 声明
int len = str.length(); // 获取字符串长度
int len = "hello World".length(); // 同样获取字符串长度
String concatStr = "hello" + "world"; // + 运算符可以重载以执行两个字符串的拼接
String str1 = "Hello";
String str2 = "World";
if (str1 == str2) // 比较两个字符串
    System.out.println("strings are equal");
```

## 引用变量

```java
Movie m1 = new Movie();
```

左侧是声明，它指示 JVM 为引用变量留出空间，该变量持有到达实际对象的引用。

```java
int[] n; // 声明整数数组
n = new int[5]; // 创建一个包含 5 个整数的数组
```

注意，即使是基本数据类型值的数组，数组也是一个对象。

```java
Movie[] mArray; // 声明对象数组
```

大小：基本类型有固定大小，引用变量没有预定义的大小。

## 等于操作

我们知道 `==` 和 `!=` 等比较运算符可以用于基本类型，但为了对对象进行比较操作，不能使用默认运算符，相反 Java 提供了 `equals` 方法。

## 数组列表

这可用于 `java.util.ArrayList` 包中。

```java
ArrayList<String> myList = new ArrayList<String>();
```

它允许声明不同数据类型的数组。它提供了多种方法来执行常见的数组操作，如 `add(elem)` 和 `remove(index)` 用于从 `ArrayList` 中添加/删除元素。还有诸如 `size()` 用于查找数组长度，查找是否 `isEmpty()` 或者 `ArrayList` 是否 `contains()` 给定的元素等 API。

让我们来看一个使用目前所学概念的示例：

```java
class MyProgram {
    public static void main(String[] args) {
        // 声明并赋值变量
        int num = 10;
        float fNum = 10.5f;
        // 打印语句输出到控制台
        System.out.println("The value of integer num is : " + num);
        System.out.println("The Value of float fNum is : " + fNum);
        num = num / 2;
        fNum = fNum + num;
        System.out.println("The value of integer num after operation is : " + num);
        System.out.println("The Value of float fNum after operation is : " + fNum);
    }
}
```

输出：

```text
The value of integer num is : 10
The value of float fNum is : 10.5
The value of integer num after operation is : 5
The value of float fNum after operation is : 20.5
```

你只需要在 `System.out.println` 语句中使用 `+` 运算符即可。

## 包装类

正如我们所知，Java 是一种面向对象的编程语言，Java 中的所有内容都可以被视为一个对象，等等。从简单的文件、图像到系统地址，任何内容都可以被视为 Java 中的对象。我们通过使用包装类来更改对象的数据类型。在本教程中，我们将介绍包装类及其细节。使用包装类，你可以将任何给定的数据类型转换为对象。

Java 中的原始数据类型不是对象。这些原始数据类型不属于任何类。它们定义在 Java 语言本身中。我们可能会遇到需要将这些原始数据类型转换为对象的情况。例如，通过将数据类型转换为对象来将其添加到向量（Vector）或栈（Stack）中。Java 设计引入了包装类来完成这些转换。

### 关于包装类

顾名思义，包装类封装（包围）任何数据类型，赋予其对象的外观，并在需要该数据类型时可以使用它。这是一个可逆的过程。包装类不仅可以将数据类型转换为类，还可以拆开对象并返回数据类型。这就像巧克力上的包装纸。制造商用包装纸包住巧克力并出货。用户去除包装纸以获得巧克力。

查看下面的转换示例，其中 `int` 数据类型被转换为对象。

```java
int k = 100;
Integer it1 = new Integer(k);
```

在上面的示例中，`int` 数据类型 `k` 使用包装类转换为对象 `it1`。这是通过使用 `Integer` 类实现的。每当需要 `k` 时，可以使用对象 `it1`。

以下代码展示了如何拆封对象并从整数对象 `it1` 获取 `int` 数据类型。

```java
int m = it1.intValue();
System.out.println(m * m); // prints 10000
```

### 包装类列表

在 Java 语言中存在 8 种原始数据类型，每种类型都有它们自己的包装类。

| 原始数据类型 | 包装类 |
| --- | --- |
| byte | Byte |
| short | Short |
| int | Integer |
| long | Long |
| float | Float |
| double | Double |
| char | Character |
| boolean | Boolean |

所有的包装类都可以在 `java.lang` 包中找到。它们的放置方式使得只要被导入，就可以隐式地对程序员可用。为了避免继承，Java 设计师将这些包装类设为 `final`。

### 包装类的重要性

我们使用包装类有两个目的：

- 将简单的数据类型转换为对象。这是通过给给定的数据类型对象的形式来实现。
- 将字符串转换为数据类型。对于此类转换，我们使用如 `parseXXX()` 等方法。

这里有一个示例程序，展示了数据类型到对象的转换，并同时获取数据类型。



```java
public class WrappingUnwrapping
{
    public static void main(String args[])
    {
        byte grade = 2;
        int marks = 50;
        float price = 8.6f;
        string f="strong"; // for float
        double rate = 50.5;

        Byte g1 = new Byte(grade);
        Integer m1 = new Integer(marks);
        Float f1 = new Float(price);
        Double r1 = new Double(rate);

        System.out.println("Values of Wrapper objects (printing as objects)");
        System.out.println("Byte object g1: " + g1);
        System.out.println("Integer object m1: " + m1);
        System.out.println("Float object f1: " + f1);
        System.out.println("Double object r1: " + r1);

        // 对象到数据类型
        System.out.println("Byte object g1: " + g1);
        System.out.println("Integer object m1: " + m1);
        System.out.println("Float object f1: " + f1);
        System.out.println("Double object r1: " + r1);

        // 对象到数据类型
        byte b = g1.byteValue();
        int i = m1.intValue();
        float f = f1.floatValue();
        double d = r1.doubleValue();

        System.out.println("byte value: " + b);
        System.out.println("int value: " + i);
        System.out.println("float value: " + f);
        System.out.println("double value: " + d);
    }
}
```

## 控制语句

控制语句控制程序的执行流。

### if-else

`if` 语句用于根据条件执行代码块。

### switch

`switch` 语句用于从多个代码块中选择一个执行。

### while 循环

`while` 循环在条件为真时重复代码块。

### do-while 循环

`do-while` 循环在检查条件之前至少执行一次代码块。

### for 循环

`for` 循环用于按特定次数重复代码块。

x 的值 : 10

x 的值 : 11

x 的值 : 12

x 的值 : 13

x 的值 : 14

x 的值 : 15

x 的值 : 16

x 的值 : 17

x 的值 : 19

## 更多关于 for 循环

在这里我们将研究循环的细节。现在我们来看看 `for` 循环。每个 `for` 循环由三部分组成。它们是：

- **初始化 (Initialisation)**：在初始化部分，我们将使用一个合适的变量来声明并初始化循环。我们在循环体中使用它。我们在循环中使用的这个变量通常用作计数器。循环内部可以放置的变量数量不仅限于 1。你可以在循环体中放置任意数量可以作为计数器的变量。

- **布尔值设置 (Boolean set)**：条件测试将放置在循环的这一部分。给定的条件无论其是什么，都必须解析为一个布尔值。你可以给出一个表达式，也可以使用返回布尔值的方法。

- **迭代表达式 (Iteration expression)**：在循环的这部分中，你可以放置一个或多个希望在每次循环运行时发生的预期动作。始终记住，执行只会在循环结束时发生。

### 嵌套 for 循环

你可以将一个 `for` 循环放在另一个 `for` 循环内部。这种结构被称为嵌套循环（`nested loop`）。你可以在循环内部放置任意数量的循环。但建议不要超过五或六层嵌套循环，因为这会让程序看起来很臃肿。汽车里程表的工作原理与嵌套 `for` 循环相同。另一个例子是日期或日历。正如我们所见的，一天由小时、分钟和秒组成。在数字钟中，嵌套 `for` 循环的最后一个分支是秒计数器。在其上方是分钟计数器，再上方是小时计数器。它是嵌套在嵌套循环中的嵌套循环。首先给出了嵌套 `for` 循环的语法。循环有三种形式。它们是：

#### 形式 1 语法

```java
for(initialization; test; increment)
{
    statements;
    while(expression)
    {
        statements;
        |
        |
        do
        {
            statements;
        }while(expression);
    }
}
```

#### 形式 2 语法

```java
for(initialization; test; increment)
{
    statements;
    for(initialization; test; increment)
    {
        statements;
        |
        for(initialization; test; increment)
        {
            statements;
        }
    }
}
```

#### 形式 3 语法

```java
While(expression)
{
    statements;
}
While(expression)
{
    statements;
}
```

这里有几个示例将帮助你理解嵌套 `for` 循环的工作原理。

#### 示例 1：使用嵌套 for 循环显示 * 三角形形的程序

```java
class NestedForLoopDemo
{
    public static void main(String args[])
    {
        for(int i = 1; i<=5; i++)
        {
            for(int j = 1; j <= i; j++)
            {
                System.out.println("* ");
            }
        }
        System.out.println("");
    }
}
```

##### 输出

*

**

***

****

*****

#### 示例 2：打印乘法表的程序

```java
class NestedWhileLoop
{
    public static void main(String args[])
    {
        int i=1, j=1;
        System.out.println("Tables");

        while(i <= 2) // 根据用户需要的将 2 改为 10 或 20 以生成更多表
        {
            while(j <= 10)
            {
                System.out.println(i + " * " + j + " = " + (i * j));
                j++;
            }
            i++;
            j=1;
        }
    }
}
```

##### 输出

Tables

1 * 1 = 1

1 * 2 = 2

1 * 3 = 3

1 * 4 = 4

1 * 5 = 5

1 * 6 = 6

1 * 7 = 7

1 * 8 = 8

1 * 9 = 9

1 * 10 = 10

2 * 1 = 2

2 * 2 = 4

2 * 3 = 6

2 * 4 = 8

2 * 5 = 10

2 * 6 = 12

2 * 7 = 14

2 * 8 = 16

2 * 9 = 18

2 * 10 = 20

#### 示例 3：打印数字三角形的程序

```java
class NestedWhileLoop
{
    public static void main(String args[])
    {
        int i=1;
        do
        {
            int j=1;
            do
            {
                System.out.print(j + " ");
                j++;
            }while(j <= i);
            System.out.println("");
            i++;
        }while(i <= 5);
    }
}
```

##### 输出

1 

1 2 

1 2 3 

1 2 3 4 

1 2 3 4 5 

## 第5 章：封装 (Encapsulation)

封装正如其名所示，隐藏了数据。在 Java 中，设计类时可以使用封装。这为数据提供了安全性。考虑以下示例：

```java
class GetterSetter
{
    private String name;
    private int age;

    // getters
    public String getName()
    {
        return name;
    }
    public int getAge()
    {
        return age;
    }

    // setters
    public void setName(String name)
    {
        name = name;
    }
    public void setAge(int age)
    {
        age = age;
    }

    public static void main(String args[])
    {
        GetterSetter gs = new GetterSetter();
        gs.setName("John");
        gs.setAge(30);
        System.out.println("Name: " + gs.getName());
        System.out.println("Age: " + gs.getAge());
    }
}
```

### 输出

Name: John

Age: 30

## 第6 章：多态与继承 (Polymorphism and Inheritance)

在 Java 中，多态发生在一个对象具有多种形式时。在方法重写中，子类有重写父类方法的。被重写的方法在子类使用 `super` 关键字之前实际上上是隐藏的。

```java
class Employee
{
    private String name;
    private String address;
    private int number;

    public Employee(String name, String address, int number)
    {
        System.out.println("Constructing an Employee");
        this.name = name;
        this.address = address;
        this.number = number;
    }
    public void mailCheck()
    {
        System.out.println("Mailing a check to " + this.name + ""+ this.address);
    }
    public String toString()
    {
        return name + ""+ address + ""+ number;
    }
    public String getName()
    {
        return name;
    }
    public String getAddress()
    {
        return address;
    }
    public void setAddress(String newAddress)
    {
        address = newAddress;
    }
    public int getNumber()
    {
        return number;
    }
}

class Salary extends Employee
{
    public Salary(String name, String address, int number)
    {
        super(name, address, number);
    }
    @Override
    public void mailCheck()
    {
        System.out.println("Mailing a salary check to " + getName() + ""+ getAddress());
    }
}
```

```java
private double salary; //Annual salary
public Salary(String name, String address, int number, double salary)
{
    super(name, address, number);
    setSalary(salary);
}
public void mailCheck()
{
    System.out.println("Within mailCheck of Salary class ");
    System.out.println("Mailing check to " + getName() + " with salary " + salary);
}
public double getSalary()
{
    return salary;
}
public void setSalary(double newSalary)
{
    if(newSalary>= 0.0)
    {
        salary = newSalary;
    }
}
public double computePay()
{
    System.out.println("Computing salary pay for " + getName());
    return salary/52;
}
}
```

现在请看以下程序并尝试判断输出结果

/* 文件名：VirtualDemo.java */

```java
public class VirtualDemo
{
    public static void main(String [] args)
    {
        Salary s = new Salary("George Martin", "Ambehta, "UP", 3, 3600.00);
        Employee e = new Salary("John Adams", "Boston, MA", 2, 2400.00);

        System.out.println("Call mailCheck using Salary reference --");
        s.mailCheck();

        System.out.println("\n Call mailCheck using Employee reference--");
        e.mailCheck();
    }
}
```



# Java 核心概念：多态、抽象类、接口与继承

## 虚方法调用示例

### 代码示例

**Salary 类**

```java
private double salary; // Annual salary

public Salary(String name, String address, int number, double salary) {
    super(name, address, number);
    setSalary(salary);
}

public void mailCheck() {
    System.out.println("Within mailCheck of Salary class ");
    System.out.println("Mailing check to " + getName() + " with salary " + salary);
}

public double getSalary() {
    return salary;
}

public void setSalary(double newSalary) {
    if (newSalary >= 0.0) {
        salary = newSalary;
    }
}

public double computePay() {
    System.out.println("Computing salary pay for " + getName());
    return salary / 52;
}
```

**VirtualDemo 类**

```java
/* 文件名：VirtualDemo.java */
public class VirtualDemo {
    public static void main(String[] args) {
        Salary s = new Salary("George Martin", "Ambehta, UP", 3, 3600.00);
        Employee e = new Salary("John Adams", "Boston, MA", 2, 2400.00);
        System.out.println("Call mailCheck using Salary reference --");
        s.mailCheck();
        System.out.println("\nCall mailCheck using Employee reference--");
        e.mailCheck();
    }
}
```

### 运行输出

```
Constructing an Employee
Constructing an Employee
Call mailCheck using Salary reference --
Within mailCheck of Salary class
Mailing check to George Martin with salary 3600.0
Call mailCheck using Employee reference--
Within mailCheck of Salary class
Mailing check to John Adams with salary 2400.0
```

### 解析

在这个示例中，实例化了两个 `Salary` 对象。其中一个使用 `Salary` 引用 `s`，另一个使用 `Employee` 引用 `e`。

- 对于 `s.mailCheck()`，编译器在编译期间查看 `Salary` 类中的 `mailCheck()`，JVM 在运行时调用 `Salary` 类中的 `mailCheck()`。
- 对于 `e.mailCheck()`，由于 `e` 是 `Employee` 引用，编译器在编译期间查看 `Employee` 类中的 `mailCheck()` 进行验证。但在运行时，JVM 调用的是实际对象类型 `Salary` 中的 `mailCheck()`。

这种行为被称为**虚方法调用**。在 Java 中，所有非静态方法默认都是虚方法，重写方法在运行时总是被调用，而不依赖于编译时的引用类型。

---

## 抽象方法与类

**抽象类** 是被 `abstract` 关键字声明的类。它可能包含抽象方法，也可能不包含。抽象类可以有子类，但不能被实例化。

**抽象方法** 是被声明为 `abstract` 且没有实现体的方法。

### 示例

```java
abstract void moveTo(double deltaX, double deltaY);
```

如果一个类包含抽象方法，则该类必须声明为抽象类：

```java
public abstract class GraphicObject {
    // 声明字段
    // 声明非抽象方法
    abstract void draw();
}
```

**规则**：
- 子类继承抽象类时，通常必须为父类中的每个抽象方法提供具体实现。
- 如果子类未实现所有抽象方法，则该子类也必须声明为抽象类。
- 接口中未声明为 `static` 或 `default` 的方法隐式为抽象方法，不使用 `abstract` 修饰符。

---

## 抽象类与接口的比较

| 特性 | 抽象类 | 接口 |
| :--- | :--- | :--- |
| **构造方法** | 可以包含构造方法 | 不能包含构造方法 |
| **成员变量** | 可以包含实例变量（字段） | 只能包含 `static final` 常量 |
| **方法实现** | 可以包含具体方法和抽象方法 | Java 8 前只能有抽象方法；Java 8+ 可有 `default`/`static` 方法 |
| **继承关键字** | `extends` (单继承) | `implements` (可多实现) |
| **访问修饰符** | 方法可为 `protected`、`private` 等 | 方法隐式为 `public` |

---

## 继承

继承是指一个对象获取另一个对象属性的过程，主要用于代码复用。Java 使用 `extends` 关键字实现继承。

### IS-A 关系

`IS-A` 表示“是一个”的关系，即子类是父类的一种。

```java
class Animal {}
class Mammal extends Animal {}
class Reptile extends Animal {}
class Dog extends Mammal {}
```

**推导关系**：
- `Mammal` IS-A `Animal`
- `Reptile` IS-A `Animal`
- `Dog` IS-A `Mammal`
- `Dog` IS-A `Animal`

**特性**：
- 子类继承父类所有非私有（`private`）成员。
- 可使用 `instanceof` 运算符验证对象是否为特定类型的实例。

### `instanceof` 运算符示例

```java
public class Dog extends Mammal {
    public static void main(String[] args) {
        Animal a = new Animal();
        Mammal m = new Mammal();
        Dog d = new Dog();

        System.out.println(m instanceof Animal); // true
        System.out.println(d instanceof Mammal); // true
        System.out.println(d instanceof Animal); // true
    }
}
```

---

## `instanceof` 运算符详解

`instanceof` 是类型比较运算符，用于判断对象是否为某个类的实例，或是否实现了某个接口。返回 `boolean` 值。

### 综合示例

```java
class Vehicle {
    String name;
    Vehicle() { name = "Vehicle"; }
}

class DirtBike extends Vehicle {
    DirtBike() { name = "DirtBike"; }
}

class ATV extends DirtBike {
    ATV() { name = "ATV"; }
}

class LightVehicle extends Vehicle {
    LightVehicle() { name = "LightVehicle"; }
}

public class InstanceOfExample {
    static boolean result;
    static DirtBike hv = new DirtBike();
    static ATV t = new ATV();
    static DirtBike hv2 = null;

    public static void main(String[] args) {
        result = hv instanceof DirtBike;
        System.out.println("hv is a DirtBike: " + result); // true

        result = t instanceof DirtBike;
        System.out.println("t is a DirtBike: " + result); // true (ATV 继承自 DirtBike)

        result = hv instanceof ATV;
        System.out.println("hv is an ATV: " + result); // false (父类实例不是子类)

        result = hv2 instanceof DirtBike;
        System.out.println("hv2 is a DirtBike: " + result); // false (null 引用)

        // 类型转换演示
        hv = t;          // 向上转型 (子类 -> 父类)，隐式
        t = (ATV) hv;    // 向下转型 (父类 -> 子类)，显式强转
    }
}
```

**输出**：
```
hv is a DirtBike: true
t is a DirtBike: true
hv is an ATV: false
hv2 is a DirtBike: false
```

**注意**：
- `null` 引用 `instanceof` 任何类型均返回 `false`。
- 不能在兄弟类（如 `DirtBike` 和 `LightVehicle`）之间使用 `instanceof`，编译报错。

---

## `implements` 关键字

`implements` 关键字用于类实现接口。接口不能被 `extends`，只能被 `implements`。一个类可以实现多个接口。

```java
public interface Animal {}

public class Mammal implements Animal {}

public class Dog extends Mammal {}
```

此处 `Mammal` 实现了 `Animal` 接口，`Dog` 继承 `Mammal`，因此 `Dog` 也是 `Animal` 类型。

---

## HAS-A 关系 (组合)

`HAS-A` 关系表示“有一个”，即组合。通过将一个类的对象作为另一个类的成员变量来实现，有助于减少代码重复和 Bug。

```java
public class Vehicle {}
public class Speed {}

public class Van extends Vehicle {
    private Speed sp; // Van HAS-A Speed
}
```

此处 `Van` 继承 `Vehicle` (IS-A)，同时包含 `Speed` 实例 (HAS-A)。



上面的示例告诉我们，van（面包车）“有一个”speed（速度）。如果我们专门为为速度创建一个类，我们就可以在不同的应用程序中反复使用它。

在 Java 中，类只能有单继承。Java 不支持多重继承。每个类都限制为使用 `extends` 关键字进行单继承。然而，允许类实现多个接口。通过这种方式，可以在 Java 中获得多重继承。以下语句包含两个带有 `extends` 关键字的类，无法像那样使用该关键字：

```java
public class extends Animal, Mammal { }
```

# 第 7 章：对象的生命与死亡

## 构造函数

在 Java 中，构造函数可以定义为一种特殊的方法，通过它你可以初始化对象。构造函数在对象创建期间被调用。它被称为构造函数是因为它为对象构造了值。

### 在 Java 中创建构造函数的规则

Java 为构造函数定义了两个基本规则：

- 构造函数的名称必须与它的类名完全相同。
- 构造函数不应该有显式的返回值。

### 构造函数的类型

在 Java 中，我们有两种类型的构造函数：

- 默认构造函数或无参构造函数
- 参数化构造函数

在这里我们将详细查看它们。

#### Java 默认构造函数

Java 默认构造函数是不带参数的构造函数。

##### 默认构造函数的语法

```java
class Bike1 {
    Bike1() {
        System.out.println("Bike is created");
    }
    public static void main(String args[]) {
        Bike1 b = new Bike1();
    }
}
```

输出：

```
Bike is created
```

这是一个默认构造函数的示例，它提供了默认值。在单独的示例中，你没有创建任何构造函数。

#### Java 中的参数化构造函数

在 Java 中，如果一个构造函数带有参数，则被称为参数化构造函数。

##### 为什么我们需要使用参数化构造函数？

当我们给对象赋予不同的值时，我们使用参数化构造函数。这里有一个参数化构造函数的示例，它可以定义任意数量的参数。

```java
class Student4 {
    int id;
    String name;
    Student4(int i, String n) {
        id = i;
        name = n;
    }
    void display() {
        System.out.println(id + " " + name);
    }
    public static void main(String args[]) {
        Student4 s1 = new Student4(111, "David");
        Student4 s2 = new Student4(222, "Aryan");
        s1.display();
        s2.display();
    }
}
```

输出：

```
111 David
222 Aryan
```

#### Java 中的构造函数重载

在 Java 中，如果构造函数具有不同的参数，则被称为构造函数重载。构造函数重载是 Java 中使用的一种技术，通过它可以可以使用不同数量的参数。

```java
class Student5 {
    int id;
    String name;
    int age;
    Student5(int i, String n) {
        id = i;
        name = n;
    }
    Student5(int i, String n, int a) {
        id = i;
        name = n;
        age = a;
    }
    void display() {
        System.out.println(id + " " + name + " " + age);
    }
    public static void main(String args[]) {
        Student5 s1 = new Student5(111, "David");
        Student5 s2 = new Student5(222, "Aryan", 25);
        s1.display();
        s2.display();
    }
}
```

输出：

```
111 David 0
222 Aryan 25
```

#### Java 中的拷贝构造函数

虽然我们称之为拷贝构造函数，但 Java 中并没有这种东西。如果你想将一个对象的值拷贝到另一个对象，可以使用以下方法：

```java
class Student6 {
    int id;
    String name;
    Student6(int i, String n) {
        id = i;
        name = n;
    }
    void display() {
        System.out.println(id + " " + name);
    }
    public static void main(String args[]) {
        Student6 s1 = new Student6(111, "David");
        Student6 s2 = s1; // 
        s1.display();
        s2.display();
    }
}
```

输出：

```
111 David
111 David
```

#### 不使用构造函数的值拷贝

正如我们之前讨论过的，我们可以在不使用构造函数的情况下将对象的值拷贝到不同的对象。在这种情况下你不需要创建构造函数。你只需通过赋值该对象的值来拷贝。在下面的示例中，我们没有使用构造函数，而是通过赋值来进行拷贝。

```java
class Student7 {
    int id;
    String name;
    Student7(int i, String n) {
        id = i;
        name = n;
    }
    Student7() {
    }
    void display() {
        System.out.println(id + " " + name);
    }
    public static void main(String args[]) {
        Student7 s1 = new Student7(111, "David");
        Student7 s2 = new Student7();
        s2.id = s1.id;
        s2.name = s1.name;
        s1.display();
        s2.display();
    }
}
```

输出：

```
111 David
111 David
```

## Java 中的垃圾回收

Java 中的垃圾可以定义为 Java 中未引用的对象。而清理垃圾以回收未使用运行时内存的过程被称为垃圾回收。简单来说，垃圾回收意味着销毁未使用的对象。与 C 和 C++ 不同，垃圾回收在 Java 中是一个自动化的过程。这就是为什么 Java 为用户提供更好、更高的内存管理的原因之一。

### 垃圾回收的优点

- 垃圾回收通过移除所有未引用的对象使内存变得高效。这些对象使用堆内存，垃圾回收会清理这些内存。
- 用户不需要手动执行垃圾回收，因为垃圾回收过程在 Java 中是自动的。所以我们不需要为管理内存付出额外努力。Java 虚拟机负责清理这些内存。

例如，对象 `e1` 的引用被赋值给 `e2`。这使得 `e1` 达到了垃圾回收的条件。

```java
Employee e1 = new Employee();
Employee e2 = new Employee();
e1 = e2;
```

利用匿名对象：这是释放对象的第三种方法。在这里，我们将创建一个新对象。示例：`new Employee();`

# 第 8 章：类型转换

## 通过对象引用的类型转换

在 Java 中，你可以将一个对象的引用类型转换为另一种对象的引用类型。这被称为类型转换。类型转换不仅限于类本身。你可以享受如何测试你的一个父类或子类类型或接口。对于类型转换，既有编译时规则，也有运行时规则。当对给定类型的对象进行类型转换时，可以分配任何对象的引用。这是因为我们所使用的对象类是 Java 中所有类的父类。类型转换有两种，它们是：

- 向上转换 (Upcasting)
- 向下转换 (Down casting)

类型转换可以隐式地或显式地进行。如果从低级数据结构到高级数据结构，则是隐式类型转换。Java 不会自动执行向下转换。向下转换应由用户显式地进行。从高级数据结构到低级数据结构的类型转换应该小心进行，因为如果强制执行将涉及大量数据。Java 虚拟机会在需要时执行向上转换。例如，如果有几个数据类型，其中只有一个是高级类型，JVM 将所有其他七个低级数据类型转换为高级类型。在上述情况下执行向下转换将导致高级类型对象中数据的丢失。在运行时，可能会出现名为 `ClassCastException` 的情况，即正在转换的对象与其要转换的类型不兼容。这里有一个解释 `ClassCastException` 的示例。

```java
// X 是 Y 和 Z 的父类，Y 和 Z 是兄弟关系。
public class RuntimeCastDemo {

    public static void main(String[] args[]) {
        X x = new X();
        Y y = new Y();
        Z z = new Z();

        X y = new Y(); // 编译通过（向上层级）
        X z = new Z(); // 编译通过（向上层级）

        // Y z = new Z(); 类型不兼容（兄弟关系）
        // Y1 = new X(); X 不是 Y
        // Z1 = new X(); X 不是 Z

        X1 = y; // 编译通过（y 是 X 的子类）
        X2 = z; // 编译通过（z 是 X 的子类）

        Y y1 = (Y) x; // 编译通过但产生运行时错误
        z1 = (Z) x; // 编译通过但产生运行时错误

        Y y2 = (Y) x1; // 编译并运行正常（x1 是 Y 类型）
        z2 = (Z) x2; // 编译并运行正常（x2 是 Z 类型）

        // Y3 = (Y) z; 类型不兼容（兄弟关系）
        // Z3 = (Z) y; 类型不兼容（兄弟关系）

        Object o = z;
        Object o1 = (Y) o; // 编译通过但产生运行时错误
    }
}
```

### 转换对象引用：使用编译器的隐式转换

每当对对象引用进行赋值时，就会执行一次隐式转换。在这里，对象的引用将被赋值给：

- 与类类型相同的引用变量。这是实例化给定对象的类。每个类的父类都是作为 object 存在的。
- 与数据类型对齐的引用变量，它是实例化该对象的类所实现的接口。

这里有一个显示接口 `Automobile`、父类和子类 `Ducati` 的示例。在这里你可以看到编译器处理的给定对象引用的自动转换。

```java
interface Automobile {
}
class Bike implements Automobile {
}
class Ducati extends Bike {
}
```

示例：假设 `c` 是 `Bike` 类变量，`f` 是 `Ducati` 类，`v` 是 `Vehicle` 接口引用。我们可以将 `Ducati` 引用赋值给 `Bike` 变量：

我们可以执行以下操作：

#### 示例 1

```java
c = f; // 编译正常
// 其中 c = new Bike();
// 并且 f = new Ducati();
```

编译器会自动处理转换（赋值），因为类型是兼容的（子类 – 父类关系），即 `Bike` 类型可以容纳 `Ducati` 类型，因为 `Ducati` 是一个 `Bike`。

#### 示例 2

```java
c = v; // 从接口类型到类类型的非法转换导致编译错误
// 其中 c = new Bike();
// 并且 v 是 `Vehicle` 接口引用 (Vehicle v)
```

编译器会自动处理转换（赋值），因为类型是兼容的（类 – 接口关系），即 `Bike` 类型可以转换为 `Vehicle` 接口类型，因为 `Bike` 实现了 `Vehicle` 接口。（`Bike` 是 `Vehicle`）。

### 转换对象引用：显式转换

在 Java 中，当隐式类型转换无效或效率低下时，有时我们需要显式地进行转换。这种转换非常简单，只需在匹配的括号内加上新“类型”的名字。在这里我们将查看 `Bike` 和 `Ducati` 类的相同示例。

```java
class Bike {
    void bikeMethod() {
    }
}

class Ducati extends Bike {
    void DucatiMethod() {
    }
}
```

在这里你可以看到我们还有一个 `brakingSystem()` 函数。此函数接受 `Bike` 作为输入。无论对象类型如何，如果你想确定可以使用的类型，可以使用它。

```java
public void system(Bike obj) {
    obj.bikeMethod();
    if (obj instanceof Ducati) {
        ((Ducati) obj).DucatiMethod();
    }
}
```

以下示例将显示转换运算符的使用。在这种情况下 `Ducati` 是兄弟关系。它们都是 `Bike` 类。以下代码实例化了给定对象。

#### 示例程序

```java
class Bike extends Object {
    void bikeMethod() {
    }
}

class DirtBike extends Object {
}

class Ducati extends Bike {
    void DucatiMethod() {
        System.out.println("I am DucatiMethod defined in Ducati");
    }
}

class Honda extends Bike {
    void DucatiMethod() {
        System.out.println("I am DucatiMethod defined in Ducati");
    }
}

public class ObjectCasting {
    public static void main(String[] args) {
        Bike obj = new Ducati();

        // 以下操作会导致编译错误
        // obj.DucatiMethod(); // 因为 Bike 类型未定义 DucatiMethod

        // 以下操作会导致编译错误
        // ((DirtBike) obj).DucatiMethod();
        // DucatiMethod 在 DirtBike 类型中未定义

        // 以下操作将编译并运行
        ((Ducati) obj).DucatiMethod();

        // 以下操作将编译错误
        // Honda hondaObj = (Ducati) obj; // 无法转换，因为它们是兄弟关系
    }
}
```

用户被允许在 Java 中将对象引用转换为字符串。这是处理集合时的一种常用转换之一。

#### 示例

```java
import java.util.Vector;

public class StringCastDemo {
    public static void main(String[] args[]) {
        String username = "asdf";
        String password = "qwer";
        Vector v = new Vector();
        v.add(username);
        v.add(password);
        // String u = v.elementAt(0); 无法从 Object 转换为 String
        Object u = v.elementAt(0); // 未进行转换
        System.out.println("Username : " + u);
        String uname = (String) v.elementAt(0); // 允许转换
        String pass = (String) v.elementAt(1); // 允许转换
        System.out.println();
        System.out.println("Username : " + uname);
        System.out.println("Password : " + pass);
    }
}
```

输出：

```
Username : asdf
Username : asdf
Password : qwer
```

# 第 9 章：异常处理

## 异常

异常可以定义为任何中断给定程序流的事件。异常希望让程序继续执行，但它们会终止程序而不允许其继续运行。在这种情况下，系统将生成错误消息来通知用户发生的问题。但不必担心异常，因为它们是可以被处理的。

### 异常何时会发生？

异常可能发生在运行时也可以发生在编译时。并不是所有异常都发生在运行时。当程序编译过程中出现问题时，Java 虚拟机会给出关于该异常的错误消息。大多数异常发生在运行时。在编译期间发生的异常称为编译时异常，而在运行期间发生的异常称为运行时异常（run-exceptions）。

### 异常产生是什么？



异常发生的原因有很多。例如，当系统无法打开文件时，它会抛出异常。网络连接问题、类文件缺失、处理超出范围的操作数都是抛出异常的常见原因。

在 Java 语言中可以找到两种类型的异常。它们是受检异常（checked exceptions）和未检异常（unchecked exceptions）。

我们将详细学习受检异常和未检异常。

## 受检异常

在编译期间检查的异常称为受检异常。在这种情况下，如果一个方法抛出受检异常，它应该使用 `try-catch` 块进行处理，或者使用 `throws` 关键字进行声明。如果都不遵循上述两种方法之一，编译器将给出编译错误。由于这些异常是在编译期间检查的，因此被称为受检异常。下面的示例将帮助你理解受检异常。

在这个示例中，有一个文件 `myfile.txt`。将从该文件中读取数据并显示在屏幕上。此程序中有三个受检异常，如下所示。

示例：

```java
import java.io.*;
class Example {
    public static void main(String args[]) {
        FileInputStream fis = null;
        /*构造函数 FileInputStream(File filename)
         * 会抛出 FileNotFoundException，这是一个受检
         *异常*/
        fis = new FileInputStream("B:/myfile.txt");
        int k;

        /*FileInputStream 类的 read() 方法也抛出
         * 一个受检异常: IOException*/
        while(( k = fis.read()) != -1) {
            System.out.print((char)k);
        }
        /*close() 方法关闭文件输入流
         * 它抛出 IOException*/
        fis.close();
    }
}
```

Output:

```
Exception in thread "main" java.lang.Error: Unresolved compilation problems:

Unhandled exception type FileNotFoundException

Unhandled exception type IOException

Unhandled exception type IOException
```

在上面的示例中，受检异常在编译期间被编译器检查过，由于我们没有声明这些异常，程序显示了编译错误消息。

下面是另外几个受检异常。

- `SQLException`
- `IOException`
- `DataAccessException`
- `ClassNotFoundException`
- `InvocationTargetException`

## 未检异常

未检异常只不过是在编译期间不被检查的异常。这些异常不会产生编译错误，因为它们在编译期间无法被检查。你是否声明了异常并不重要。未检异常通常由于用户在与程序交互时提供的数据。处理这些异常的唯一方法是预判它们并为该异常编写适当的处理器。`RuntimeException` 类是所有未检异常的父类。下面的示例将帮助你更好地理解未检异常。

```java
class Example {
    public static void main(String args[])
    {
        int num1=10;
        int num2=0;
        /*由于我正在用整数除以 0
         * 它应该抛出 ArithmeticException*/
        int res=num1/num2;
        System.out.println(res);
    }
}
```

如果你编译上面的代码，你可以看到编译将成功完成，但是如果你运行它，程序将抛出一个名为 `ArithmeticException` 的异常。通过这一点，你知道受检异常不在编译期间抛出错误，而是在运行时。这里是另一个示例：

```java
class Example {
    public static void main(String arr[])
    {
        int arr[]={1,2,3,4,5};
        /*我的数组只有 5 个元素但
        * 我正试图显示第
        * 8 个元素的值。它应该抛出
        * ArrayIndexOutOfBoundsException*/
        System.out.println(arr[7]);
    }
}
```

在这个示例中，和上一个一样，将没有编译时错误。然而，这段代码在运行时，会抛出一个名为 `ArrayIndexOutOfBoundsException` 的未检异常。这些异常在编译期间无法发现，但这意味着它们没有被用户忽略。在上面的示例中，添加一条消息建议用户给出范围内的值是明智的。

添加消息后的代码如下。

```java
class Example {
    public static void main(String args[])
    {
        try{
            int arr[]={1,2,3,4,5};
            System.out.println(arr[7]);
        }catch(ArrayIndexOutOfBoundsException e) {
            System.out.println("指定的索引不存在。请修正数组。");
        }
    }
}
```

这里是运行时常见的某些未检异常。

- `NullPointerException`
- `ArrayIndexOutOfBoundsException`
- `ArithmeticException`
- `IllegalArgumentException`

## 异常与错误的区别

### 异常

异常发生在代码内部并可以由开发者处理。当异常发生时，开发者可以采取必要的行动。异常示例如下：

- `DivideByException`
- `NullPointerException`
- `ArithmeticException`

### 错误

错误与异常不同。它们是系统尝试处理的异常状况。当错误发生时，它表示在通常情况下无法解决的严重问题。错误示例如下：

- `Hardware error`
- `Memory error`
- `JVM error`

## 异常处理

异常处理是一种处理运行时错误的强大机制。异常处理确保了程序的正常流得以维持。

- 如果程序具有异常处理，允许用户控制程序的执行流。
- 每当出现错误时，它都会抛出一个异常。通过使用不同的代码块来区分和组织不同的错误。可以使用 `try-catch` 块来实现。

我们将查看几个异常处理示例。

示例：

```java
class Division {
    public static void main(String[] args) {

        int a, b, result;

        Scanner input = new Scanner(System.in);
        System.out.println("输入两个整数");

        a = input.nextInt();
        b = input.nextInt();

        // try 块
        try {
            result = a / b;
            System.out.println("结果 = " + result);
        }

        // catch 块
        catch (ArithmeticException e) {
            System.out.println("捕获异常：除以零。");
        }
    }
}
```

当异常被捕获时，相应的 `catch` 块将执行。从上面的示例问题中，代码将抛出一个 `ArithmeticException`。捕获异常的一种简单方法是使用异常类的对象作为另一个类的子类。这里有一个显示该点的示例。

```java
class Exceptions {
    public static void main(String[] args) {
        String languages[] = {"C", "C++", "Java", "Perl", "Python" };

        try {
            for (int c = 1; c <= 5; c++) {
                System.out.println(languages[c]);
            }
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

```
C++
Java
Perl
Python
java.lang.ArrayIndexOutOfBoundsException: 5
```

异常处理是 Java 中一个非常重要的机制，良好的 Java 开发者会预判异常，并为可能出现的异常编写处理程序。

# 第 10 章：JavaScript 导论

JavaScript 是一种基于对象的动态脚本语言。Netscape 是该语言的开发者。该语言用于开发服务器应用程序和网页。它是世界上使用最广泛的脚本语言。

Java 和 JavaScript 唯一相似的地方是它们的名称相近。除此之外，这些语言在功能和概念上是完全不同的。让 JavaScript 在 Java 和 C++ 等面向对象的编程语言中脱颖而出的是，它的对象可以在运行时创建或修改。为了实现这一点，可以在空对象上添加方法和属性。一旦创建了对象，可以在创建其他相似对象的过程中作为原型使用。变量参数列表、源码恢复、动态脚本创建、动态对象创建、函数变量等都是 JavaScript 拥有的动态能力。

## JavaScript 基础

### 在 JavaScript 中存储数据

- **本地存储 (Local Storage)**：本地存储用于永久存储数据。通过它，可以随时访问该页面上的数据。本地存储没有过期时间。如果用户希望数据在一段时间内被反复重用，可以使用本地存储。
- **会话存储 (Session Storage)**：会话存储与本地存储不同，因为它只保留单个会话的数据，并在用户关闭页面时将其丢弃。这种存储用于订票等网页。

### 使用变量数据和常量数据存储数据

变量（Variables）和常量（Constants）存储了 JavaScript 中使用的数据和值。它们在 JavaScript 中都有自己的重要性。并不是所有存储的数据都不能设为常量。时间倒计时等过程使用变量，而常量则用于不可更改的数据。

**变量数据**：如其名，这种随时间改变其值的数据被称为变量数据。这种数据在 JavaScript 中被广泛使用。变量在本质上是动态的。

**常量数据**：常量数据是指永远不会改变其值的数据。这种数据随时间推移而保持不变。这种数据是静态的。我们使用这类数据处理不可修改的数据。

### 创建变量和常量

#### 声明变量

通过在名称前加上 `var` 关键字来声明变量。例如，如果你想声明 'group' 为变量，只需在 'group' 之前添加 `var` 关键字。每个变量都应该以 `;`（分号）结束。这使得语句是自包含的。在使用单词时需要小心，因为 JavaScript 是区分大小写的。因此，所使用的字母必须与原始声明完全相同。

例：`var Dell;`

上面的对象 `Dell` 被声明为一个变量。

#### 声明常量

在名称前使用 `const` 关键字使其变为常量。这种声明与声明常量的方式一样。

例：`const Book;`

在上面的示例中，`Book` 被设为了常量。

## JavaScript 中的决策

总是会出现我们必须在面前的两个路径中选择其一的情况。这时我们就可以实现 `if` 和 `else` 条件语句了。

`if` 和 `else` 语句可以用于决策。这将允许程序选择正确的路径。

JavaScript 支持以下条件语句：

1. `if` 语句
2. `if...else` 语句
3. `if...else if...` 语句

### `if` 语句

`if` 是用于决策的基础性语句。在 `if` 语句中添加一个条件，如果给定的条件成立，则可以给出一组语句。

**语法：**

```javascript
if(condition){
    // 要执行的语句
}
```

**示例：**

```javascript
<script type='text/javascript'>
//
var age = 20;
if( age > 18 ) {
    document.write("<b>Allowed inside the pub.</b>");
}
//
</script>
```

输出：Allowed inside the pub. (如果输入的数字大于 18)

### `if else` 语句

这类似于 `if` 语句的扩展。如果 “if”语句为假，系统将运行代码并执行 `else` 块中的语句。

**语法：**

```javascript
if(condition) {
    // statements
} else {
    // statements
}
```

**示例：**

```javascript
<script type='text/javascript'>
//
var age = 16;
if( age > 18 ) {
    document.write("<b>Allowed inside the pub.</b>");
} else {
    document.write("<b>Not allowed</b>");
}
//
</script>
```

**输出：**

- Allowed inside the pub (如果输入的数字大于 18)
- Not allowed (如果输入的数字小于 18)

### `if else if` 语句

这类似于在 `if else` 语句中又添加了另一个步骤。它用于使用一系列条件的情况。

**语法：**

```javascript
if(condition) {
    // statements
} else if(condition) {
    // statements
} else if(condition) {
    // statements
} else {
    // statements
}
```

**示例：**

```javascript
<script type="text/javascript">
//
var book = "JAVASCRIPT";
if( book == "JAVA") {
    document.write("<b>JAVA Book</b>");
} else if( book == "JAVASCRIPT") {
    document.write("<b>JAVASCRIPT Book</b>");
} else if( book == "DBMS") {
    document.write("<b>DBMS Book</b>");
} else {
    document.write("<b>UNKNOWN Book</b>");
}
//
</script>
```

输出：JAVASCRIPT Book

### 嵌套 `if`

“嵌套 if” 是在另一个 `if` 语句内部的 `if` 语句。

**语法：**

```javascript
if(condition) {
    if(condition) {
        // statements
    }
}
```

### `switch` 和 `break` 语句

在 `switch` 语句中，将有一个表达式，后面跟着几个语句。语句将根据表达式的值执行。

**语法：**

```javascript
switch (expression) {
    case 1:
        // statements
        break;
    case 2:
        // statements
        break;
    case n:
        // statements
        break;
    default:
        // statements
}
```

`break` 语句用于指示 `switch` 的结束。

## JavaScript 中的循环

### `for` 循环

循环用于人们希望重复执行某些代码的情况。`for` 循环是三种循环之一。`for` 循环简单且紧凑。它包含以下点：

- 初始化语句在循环开始前执行。
- 只有当给定的条件为真时循环才会执行。测试代码运行一次。
- 计数器可以增加或减少。

**语法：**

```javascript
for (初始化; 测试条件; 迭代语句) {
    // 如果条件为真要执行的语句
}
```

**示例：**

```javascript
<script type="text/javascript">
//
var count;
document.write("This will repeat 10 times" + "<br />");
for(count = 0; count < 10; count++) {
    document.write("Currently repeated : " + count);
    document.write("<br />");
}
document.write("Done!!");
//
</script>
```

**输出：**

```
This will repeat 10 times
Currently repeated : 0
Currently repeated : 1
Currently repeated : 2
Currently repeated : 3
Currently repeated : 4
Currently repeated : 5
Currently repeated : 6
Currently repeated : 7
Currently repeated : 8
Currently repeated : 9
Done!!
```

# 第 11 章：JavaScript 中的函数和事件

## 什么是函数？

一组在需要时可以在程序任何地方调用的代码被称为函数。它减少了人们反复编写相同代码的时间和精力。这减少了代码冗余。可以通过函数编写模块化代码。大型程序可以通过函数划分为许多部分。JavaScript 像任何其他编程语言一样，支持编写模块化代码所需的特性。这是通过使用“函数”实现的。

`write()` 和 `alert()` 是默认函数。JavaScript 为用户提供了许多可以直接使用的函数。

JavaScript 还允许创建自己的自定义函数。

## 函数定义



# JavaScript 函数与对象教程

## 函数定义

在使用函数之前应该先定义函数。`function` 关键字是定义 JavaScript 的常用方法。它后面跟着唯一的函数名称和参数列表。它还应该包含一个大括号的语句块。

语法：

```javascript
function functionname(parameter-list) {
    statements
}
```

**示例**：在下方的示例中，有一个简单的函数程序。

```javascript
function simplefunction() {
    alert("This is a simple function");
}
```

## 调用函数

在 JavaScript 中调用函数，应该按照如下方式编写函数的名称。

```javascript
simplefunction();
```

## 函数参数

在 JavaScript 中，函数也可以带有参数传递。在调用函数时，JavaScript 可以传递不同的参数。可以通过传递的参数在函数内部进行操作。函数中使用逗号来分隔函数中的多个参数。

### 示例

在接下来的示例中，我们将修改 `simplefunction` 函数。现在我们将使用两个参数。

```javascript
function simplefunction(name, age) {
    alert(name + " " + age + " years old.");
}
```

该函数可以被调用，如下所示：

```javascript
simplefunction('Zara', 7);
```

## return 语句

如果用户希望该函数返回一个值，可以向 JavaScript 函数中添加一个可选的 `return` 语句。`return` 语句始终应该是函数的最后一个语句。

例如，用户可以在特定函数中传递两个不同的数字，并期望该函数在程序中返回这两个数字的乘积。

### 示例

```javascript
function concatenate(first, last) {
    var full;
    full = first + last;
    return full;
}
```

现在可以如下所示调用该函数：

```javascript
var result;
result = concatenate('Zara', 'Ali');
alert(result);
```

# JavaScript 中的事件

## 事件概述

事件处理 JavaScript 和 HTML 之间的交互。当用户或浏览器操作页面时，就会发生这种交互。

一切都是事件。页面加载是一个事件。当用户通过点击选择内容时，该点击也被视为一个事件。事实上，用户执行的任何操作如关闭窗口、选择链接、按键、关闭标签页、调整窗口大小等，都是事件的示例。

在 JavaScript 中编写的响应通过这些事件执行，例如关闭窗口、要显示的文本、显示的警报、确认消息或任何可能发生的响应。

事件是文档对象模型（DOM）Level 3 的一部分。每个 HTML 元素都提供一组事件。这些事件会触发 JavaScript 中的代码。

## onclick 事件类型

这是一个事件，在点击时会显示所需的验证或警告等。这被广泛使用。

**示例**：下面的代码在点击 `onclick` 上的 hello 按钮时，它会触发 `events` 函数。

```html
<html>
<head>
<script type="text/javascript">
function events() {
    alert("Hello World")
}
</script>
</head>
<body>
<input type="button" onclick="sayHello()" value="Say Hello"/>
</body>
</html>
```

## onsubmit 事件类型

`onsubmit` 事件是另一个重要的事件类型。在此处提交表单时会发生验证。只有当函数返回 `true` 时，文本才会被发送。

**示例**：

```html
<html>
<head>
<script type="text/javascript">
function validation() {
    // 所有验证逻辑都在这里
    return either true or false;
}
</script>
</head>
<body>
<form method="POST" action="t.cgi" onsubmit="return validate()">
    ......
    <input type="submit" value="Submit" />
</form>
</body>
</html>
```

# 第12 章：JavaScript 调试

在编写程序时有很多机会犯错。脚本中的此类错误被称为 bug（缺陷）。调试是修复 bug 的过程。开发过程中，调试是正常工作的一部分。

我们编写的代码可能存在逻辑错误或语法错误，这些是很难识别的。很多时候，当 JavaScript 代码包含错误时，什么都不会发生。没有消息指示程序中存在错误。

## 使用 JavaScript 验证器

如果有人想检查代码中的 bug，必须确保它是有效代码，并通过运行一个名为验证解析器（Validating parsers，简称验证器 Validators）的程序来检查它是否遵循语言的官方语法规则。这些验证器通常带有 JavaScript 编辑器和商业 HTML 编辑器。

访问网页后，将代码粘贴到文本区域中，点击 jslint 按钮。该程序将解析我们的 JavaScript 代码，以确保所有变量和函数定义符合正确的语法。

## 在程序中添加调试代码

`alert()` 或 `document.write()` 方法有助于调试你的代码。例如：

```javascript
var debugging = true;
var whichImage = "widget";
if (debugging) {
    alert("Calls swapImage() with argument: " + whichImage);
}
var swapStatus = swapImage(whichImage);
if (debugging) {
    alert("Exits swapImage() with swapStatus=" + swapStatus);
}
```

## 使用 JavaScript 调试器

调试器（debugger）是一个允许程序员控制脚本执行的应用程序。调试器可以帮助用户检查脚本的执行流。调试器逐行运行脚本，并可以在特定的断点（breakpoints）处停止。在执行完成后，程序员可以检查变量的状态。

# 表单验证

当用户输入所需信息并点击提交按钮时，会发生表单验证。如果用户未能输入所有信息或输入了无效数据，JavaScript 允许在向服务器发送表单之前在客户端对表单数据进行验证。

表单验证通常由两个函数执行：

- **基础验证** - 为了确保每个字段都提供了数据，首先需要检查表单。
- **数据格式验证** —— 这是为了检查是否输入了正确或有效的数据。

## 基础表单验证

让我们看看基础表单验证。当提交事件发生时，我们调用 `validate()` 函数来验证数据。`validate()` 函数实现如下：

```javascript
function validate() {
    if (document.myForm.Name.value == "") {
        alert("请输入姓名！");
        document.myForm.Name.focus();
        return false;
    }
    if (document.myForm.EMail.value == "") {
        alert("请输入邮箱 ID！");
        document.myForm.EMail.focus();
        return false;
    }
    if (document.myForm.Zip.value == "" ||
        isNaN(document.myForm.Zip.value) ||
        document.myForm.Zip.value.length != 5) {
        alert("请以 ##### 格式输入邮编。");
        document.myForm.Zip.focus();
        return false;
    }
    if (document.myForm.Country.value == "-1") {
        alert("请输入国家名称！");
        return false;
    }
    return true;
}
```

## 数据格式验证

在将数据提交到 Web 服务器之前可以对数据进行验证。验证邮箱 ID：邮箱 ID 应该包含 `@` 符号和点 (.)，如下方的示例所示。此外，最后一个点在 `@` 符号之后至少要有一个字符，且邮箱地址不能以 `@` 符号开头。

```javascript
function validateEmail() {
    var emailID = document.myForm.EMail.value;
    var atpos = emailID.indexOf("@");
    var dotpos = emailID.lastIndexOf(".");
    if (atpos < 1 || (dotpos - atpos < 2)) {
        alert("请输入有效的邮箱 ID");
        document.myForm.EMail.focus();
        return false;
    }
    return true;
}
```

# 第 13 章：JavaScript 中的对象

## 对象概述

JavaScript 对象由属性组成。如果一个属性包含函数，则它被视为方法，否则该属性被视为属性值。

## 对象属性

对象的属性可以是任何数据类型。当需要向对象添加属性时，使用以下语法：

```javascript
objectName.objectProperty = propertyValue;
```

### 示例

下一个示例展示了如何使用文档对象的 `title` 属性：

```javascript
var strg = document.title;
```

## 对象方法

允许对象执行特定任务的函数。

### 示例

以下示例展示了如何使用 `write()` 方法：

```javascript
document.write("This is text");
```

## 用户定义对象

### new 运算符

`new` 运算符有助于创建对象的实例。创建对象时，构造方法跟在 `new` 运算符之后。

在下面的示例中，`Object()`、`Array()` 和 `Date()` 是构造方法，它们是 JavaScript 的内置函数。

```javascript
var emp = new Object();
var textbooks = new Array("C", "Python", "Java");
var day = new Date("August 21, 1987");
```

## Object() 构造函数

对象可以通过构造函数进行创建和初始化。`Object()` 是一个帮助构建对象的特殊构造函数。

以下示例展示了如何创建一个对象：

```html
<html>
<head>
<title>用户定义的对象</title>
<script type="text/javascript">
    var book = new Object(); // 创建对象
    book.subject = "Perl"; // 为对象分配属性
    book.author = "Yashwanth";
</script>
</head>
<body>
<script type="text/javascript">
    document.write("Book name is : " + book.subject + "<br>");
    document.write("Book author is : " + book.author + "<br>");
</script>
</body>
</html>
```

## JavaScript 原生对象

JavaScript 包含许多内置的原生对象。它们的行为不受运行其对象的浏览器或平台的影响。

以下是 JavaScript 中最常用的原生对象列表：

1. 数字对象 (Number Object)
2. 布尔对象 (Boolean Object)
3. 字符串对象 (String Object)
4. 数学对象 (Math Object)

## 数字对象

JavaScript 中的数字对象用于表示数值。它可以包含整数和浮点值。每当遇到数值时，网络浏览器会自动将这些值转换为数字类的实例。

### 语法

创建数字对象的语法如下：

```javascript
var value = new Number(number);
```

### 数字方法

以下是数字对象中包含的方法。

| 方法 | 描述 |
| --- | --- |
| `constructor()` | 此方法用于返回创建对象实例的函数。 |
| `toExponential()` | 此方法的结果是以指数形式显示标准范围的数字。 |
| `toLocaleString()` | 此方法接收一个数字并返回数字的字符串版本。其格式随浏览器的本地设置变化。 |
| `toPrecision()` | 此方法定义在给定数字中显示的位数。这包括小数点两侧的数字。 |
| `toString()` | 此方法帮助将数字转换为字符串值。 |
| `valueOf()` | 此方法表示数字的值。 |

## 布尔对象

布尔对象用于表示可以是“真”（True）或“假”（False）值的值。

### 语法

可以使用以下语法创建布尔对象：

```javascript
var bval = new Boolean(value);
```

如果 `value` 参数包含以下任何一个值：空字符串、null、0、NaN、-0、null 或 undefined，则布尔对象的初始值为 `false`。

### 布尔方法

以下是布尔对象中包含的方法。

| 方法 | 描述 |
| --- | --- |
| `toSource()` | 此方法用于返回一个由布尔对象源码组成的字符串。可以使用该字符串创建一个等效对象。 |
| `toString()` | 此方法根据对象的值返回 'true' 字符串或 'false' 字符串。 |
| `valueOf()` | 此方法用于返回布尔对象的原始值。 |

## 字符串对象

字符串对象允许用户处理一组字符，并用辅助方法封装 JavaScript 的字符串原始类型。

### 语法

可以使用以下语法创建字符串对象：

```javascript
var value = new String(string);
```

`string` 参数表示一组编码适当的字符。

### 字符串方法

以下是字符串对象中包含的方法。

| 方法 | 描述 |
| --- | --- |
| `charAt()` | 此方法返回一个数字，表示指定索引处字符的 Unicode 值。 |
| `charCodeAt()` | 此方法返回指定索引处字符的 Unicode 值。 |
| `concat()` | 此方法用于合并两个字符串的字符并返回新创建的字符串。 |
| `match()` | 此方法用于用正则表达式匹配字符串。 |
| `toLowerCase()` | 用于在保持本地设置的同时将字符串转换为小写。 |
| `toUpperCase()` | 用于在保持本地设置的同时将字符串转换为大写。 |

## Math 对象

它允许用户执行许多数学计算。通过编写对象名称后跟一个点，然后是方法名称来调用方法。参数写在方法的括号中。

**示例**：`document.writeln(Math.sqrt(81));`

以下是 Math 对象的常用函数：

| 方法 | 说明 |
| --- | --- |
| `abs(x)` | x 的绝对值 |
| `ceil(x)` | 将 x 向上舍入为不小于 x 的最小整数。 |
| `round(x)` | 将 x 四舍五入到最近整数。 |
| `pow(x, y)` | x 的 y 次方 |
| `floor(x)` | 将 x 向下舍入为不大于 x 的最大整数。 |

# 结语

我们学习 Java 和 JavaScript 编程基础的书已经到了最后。

我要感谢你购买这本书。我希望这本书对你有所帮助，并帮助你理解使用 Java 和 JavaScript 的编程概念。作为一种高级编程语言，它让学习基础并开始自己编写程序变得简单。

只要学习得当，没有任何语言是火箭科学。本书涵盖的两种语言也是如此。深入学习并掌握这些语言的基础知识。

谢谢！



## 你可能喜欢我的其他书籍！

- [Python：初学者编程指南：一天内掌握!]
- [C++ 编程：初学者语言：一天内掌握!]
- [SQL：编程指南：JavaScript 与编码：一天内掌握!]
- [编程：HTML：编程指南：计算机编程：一天内掌握!]
