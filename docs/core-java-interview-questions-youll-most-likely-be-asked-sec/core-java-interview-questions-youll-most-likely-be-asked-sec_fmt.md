

# Core Java 面试高频题（第二版）（求面试问题系列）

在继续阅读面试题与答案之前，请下载您的免费在线资源。

您的免费在线资源包括：

- 电子书：编写令人深刻的符合 ATS 标准简历的终极指南
- 技能测试

请从下方 URL 下载：

`https://www.vibrantpublishers.com/product/core-java-interview-questions-youll-most-likely-be-asked/`

或者扫描下方的二维码：

![](img/c9df4df242594cca676f19a60877f783_1_0.png)

![](img/c9df4df242594cca676f19a60877f783_3_0.png)

# 专家如何评价这本书！

随着技术的飞速发展，IT 专业人士需要不断更新技能以跟上最新的技术趋势。新版《你最可能被问的核心 Java 面试题》是 Java 程序员和开发者提升面试技巧、建立 IT 职业的完美伴侣。除了标准的核心 Java 问答，本版还包含了关于 Java 8 函数式接口和 Lambda 表达式的问题，以及 Java 9 的模块和流。人力资源问答将帮助 IT 专业人士胜任面试并给雇主留下深刻印象。通过真实的场景题，这本书为职业人士提供了在当今竞争激烈的就业市场中制定策略和脱颖出的所需的简洁信息。

> - David Han  
> 德克萨斯大学圣安东奥分校管理科学与统计学副教授

我与学生密切合作，特别是他们的就业。这本书将极大地帮助学生准备和练习面试题。毫无疑问，这将是求职者的真实指南。索引做得良好且易于理解。书中包含了几乎所有可能的变体。难度程度从易到难，适用于各种 Java 相关工作。

> – Yogesh Jhadav  
> Sinhgad 学院教授 & 培训与就业官

非常优秀的问卷列表。Vibrant Publishers 出版的《核心 Java 面试题》对 Java 技术领域的求职者将非常有用。它还包含了 HR（人力资源）问题。很多求职者对 HR 面试并不清楚，因此书中包含 HR 问题非常好。这本书将对初级生和初级 Java 工作求职者有很大帮助。我的最终评价是，它对于寻找跨国公司机会的新手和经验候选人非常有帮助。

> – Shashikikanth K  
> CSE 部门就业协调员兼副教授

我非常喜欢书中触及 Java 每一个部分的方式。此外，详细的解释配合代码段示例使其更加清晰易于理解。

> – Barkat Amirali Jiwani  
> Vaagdevi 工程学院助理教授/就业负责人

# 本书贡献者

![](img/c9df4df242594cca676f19a60877f783_8_0.png)

Reshma Bidikar 是一位热情的 Java 工程师和教育者。她在 IT 行业拥有超过 16 年的经验，担任高级 Java 开发人员/架构，工作过 Core Java、Spring、Spring Boot、Hibernate、REST、JDBC 等技术。她是一位专家 Java 培训师/Java 作者，她的文章/课程帮助了数千名学生。她擅长用简单的语言解释复杂的概念。

亲爱的读者：

感谢购买《你最可能被问的核心 Java 面试题》。我们希望这本书在您准备面试时提供丰富的体验。如果您有任何问题或建议，请随时邮件至 `vibrantpublishers.com`。

再次感谢您的购买。祝您面试顺利！

> – Vibrant Team

![](img/c9df4df242594cca676f19a60877f783_11_0.png)

# 01

# 核心 Java

## Java 8

## Java 9

## 人力资源

# 第 01 章：OOP 概念

## 001. 解释方法重载和方法重写

解答：

方法重载是指类中存在多个同相同但参数数量或类型不同的方法。以下代码演示了这一点：

```java
public class Calculator {
    public int add (int a, int b) {
        return a+b;
    }
    public double add (double a, double b) {
        return a+b;
    }
    public int add (int a) {
        return a+a;
    }
}
```

方法重写是指子类中存在与父类方法名称和参数数量相同的方法。以下代码演示了这一点：

```java
public class Animal {
    public void saySomething () {
        System.out.println("I am an animal");
    }
}

public class Dog extends Animal {
    public void saySomething() {
        System.out.println("I am a dog");
    }
}
```

## 002. 解释 OOP 的优点

解答：

OOP 的优点如下：

- 可用性：继承、组合和多态等 OOP 原则有助于重复代码。
- 扩展性：使用继承等 OOP 原则编写的代码具有扩展性。
- 安全性：封装等 OOP 原则有助于将数据和操作数据的代码结合，使代码更安全。
- 简单性：Java 类代表真实世界的对象。这使得代码非常易于理解。
- 可维护性：使用 OOP 原则编写的代码更容易维护。

## 003. 编写一个演示封装的代码段

解答：

封装是指将数据和操作数据的代码结合在单一单元中。简单地创建一个带有私有字段和公共 getter/setter 方法的类就是封装示例。下面的代码段演示了这一点：

```java
public class Laptop {
    private String memory;
    public String getMemory() {
        return memory;
    }
    public String setMemory (String newMemory){
        memory = newMemory;
    }
}
```

在这里有一个名为 `Laptop` 的类。它有一个名为 `memory` 的私有字段，以及用于访问/修改 `memory` 字段的公共 getter 和 setter 方法。因此，类外部无法访问 `memory` 字段，只能通过它的 getter/setter 方法访问。

## 004. 继承关系有哪些类型？

回答：

继承关系规定了代码如何被重用。继承关系有两种类型。

它们如下：

- a. IS-A（包含关系）

  IS-A 关系通过继承实现，即通过创建子类。假设 `Camera` 是 `Electronics` 类的子类。在这种情况下，我们可以说 `Camera` 是一个电子产品（Electronic product）。

- b. HAS-A（组合关系）

  HAS–A 关系可以通过组合创建，即通过创建一个对应另一个类的字段。假设在 `Camera` 类内部，有一个名为 `Battery` 的对象。在这种情况下，我们可以说 `Camera` 拥有一个名为 `Battery` 的对象。

## 005. 声明实例变量的最佳实践是什么？

回答：

实例变量应该始终声明为 `private`。它们应该具有公共的 getter/setter 方法。这有助于保护实例变量，因为它们只能在程序员的控制下被修改。这符合封装原则。

将实例变量声明为 `public` 违反了封装原则并会带来安全问题。公共实例变量可以在类外部被恶意修改。如果确实需要从子类访问实例变量，可以将其设为 `protected`。

## 006. 什么是单例类？

回答：

在任何给定时间内允许创建一个实例的类被称为单例类（Singleton class）。单例类可以通过私有构造函数和公共 getter 方法来实现。下面的代码演示了这一点。

```java
public class MySingleton {
    private static MySingleton mySingletonInstance;
    private MySingleton () {
    }
    public static MySingleton getInstance() {
        if (mySingletonInstance == null) {
            mySingletonInstance = new MySingleton(); // 仅在为空时创建对象
        }
        return mySingletonInstance;
    }
    public void doSomething() {
        System.out.println("I am here...");
    }
    public static void main(String a[]) {
        MySingleton mySingleton = MySingleton.getInstance();
        mySingleton.doSomething();
    }
}
```

在这里，定义了一个私有的 `getInstance` 方法。它检查实例是否存在。如果实例不存在，则使用私有构造函数创建一个实例。如果实例存在，则直接返回它。任何需要单例类实例的外部类，都需要通过 `getInstance` 方法来获取它。`getInstance` 方法确保了单例类只有一个实例。

## 007. 解释当编译以下代码时发生了什么，并说明它使用的是方法重载还是方法重写

```java
class Electronics {
    public void displayPrice (Float price) {} // 第 1 行
}
class Camera extends Electronics {
    public void displayPrice (String price) {} // 第 2 行
}
```

回答：

上述代码可以正常编译。它使用了方法重载。`Camera` 是 `Electronics` 的子类，且两个类都有名为 `displayPrice` 的方法。然而，这两个类中的 `displayPrice` 方法在参数类型上不同。

## 008. 编写一个演示方法重载的 Java 代码示例

回答：

当类中存在两个或多个同名但参数数量/类型不同的方法时，发生了方法重载。下面的代码演示了这一点：

```java
class Laptop {
    public void displayPixel (int width, int height) { } // 第 1 行
    public void displayPixel (float width, float height) { }; // 第 2 行
}
```

`Laptop` 类有两个同名为 `displayPixel` 的方法。第 1 行的 `displayPixel` 方法有两个参数，类型均为 `int`。第 2 行的 `displayPixel` 方法有两个 `float` 类型的参数。因此，这里说 `displayPixel` 方法被重载了。

## 009. 什么是多态？Java 如何支持多态？

回答：

多态的字面意思是“许多种形式”。它是使用相同接口执行不同代码的能力。Java 通过方法重载和方法重写来实现多态。方法重载发生在类中存在多个同名但参数数量/类型不同的方法时。被调用的重载方法版本在编译时根据传入参数的数量/类型确定。方法重写发生在子类拥有与父类方法相同名称和类型签名的方法时。被调用的重写方法版本在运行时根据调用方法的类型确定。

## 010. 解释 Java 如何实现抽象

回答：

抽象是一个面向对象编程（OOPs）概念，它只向最终用户暴露必要的信息，并隐藏内部的实现细节。Java 通过抽象类和接口来实现抽象。因此，你可以在抽象类或接口中声明你想要向外部公开的方法。实际实现将位于扩展抽象类或实现接口的具体类中。外部代码感知不到实现类，它们只与抽象类进行交互。

## 011. 声明 `main` 方法可能方式有哪些？

回答：

以下是声明 `main` 方法的可能方式：

- a. `public void main (String[])`
- b. `static void main (String[])`

## 012. 声明类的可能方式有哪些？

回答：

以下是声明类的可能方式：

- a. `public Class1 {}`
- b. `Class2 {}`
- c. `private Class3 {}`
- d. `protected Class4 {}`
- e. `static Class5 {}`

## 013. 如何定义标识符（Identifier）？

回答：

标识符是赋予类、方法、变量或接口的名称。Java 标识符有很多规则，如下：

- 标识符必须以字母、美元符号（`$`）或下划线（`_`）开头
- 标识符可以包含字母、数字、`$` 和 `_`
- 标识符不能包含特殊字符
- 标识符区分大小写

合法标识符的一些示例：

- `b`
- `$a`
- `book`
- `author1`
- `myName`
- `__1_c`

## 014. 实例变量不能指定哪些修饰符？

回答：

以下修饰符不能指定在实例变量上：

- `abstract`：仅对类、接口和方法有效，不能指定在实例变量上。
- `synchronized`
- `native`
- `void`：只能作为返回类型指定，当方法不返回任何值时使用。

## 015. 方法声明中可以指定哪些修饰符？

回答：

方法声明中可以指定以下关键字：

- `public`
- `private`
- `protected`

`public`、`private` 和 `protected` 是访问修饰符。它们规定了从哪里可以访问方法。

- `static`：表示该方法是类级方法。
- `final`：表示该方法不能被重写。
- `abstract`：指定子类应该重写该方法。
- `native`：指定该方法是在另一种语言（如 C++）中实现的。
- `synchronized`：表示该方法一次允许一个线程访问。

## 016. 如果引用变量没有显式初始化，其默认值是什么？你如何在...中处理这种情况

回答：

当引用变量没有显式初始化时，它的默认值为 `null`。如果对这些变量进行不当处理，可能会导致 `NullPointerException`。因此，为了避免 `NullPointerException`，你可以采取以下措施之一：

- 确保变量已正确初始化
- 在代码中显式添加空值检查
- 使用 Java 8 的 Optional

## 017. 解释关键字 `transient` 和 `native`

回答：

`transient` 关键字可以用作实例变量的修饰符。它指定 JVM 在序列化包含该变量的对象时忽略该变量。

`native` 关键字可以作为方法的修饰符。它指定该方法是用 C、C++ 等其他语言实现的。

## 018. 什么是 Java 中的注释？解释 Java 支持的注释类型

回答：

注释是添加到代码中的某些文本，用于提供有关代码的额外信息。它向代码读者描述了代码的功能。编译器会忽略注释。Java 支持以下 3 种注释：

- 单行注释：此类注释以正斜杠（`//`）开始，并在行尾结束。以下代码段演示了这一点：

  ```
  int count; // 这存储对象的数量
  ```

- b. 多行注释：它以 `/*` 开始，以 `*/` 结束。这两个之间的任何内容都被视为注释并被编译器忽略。以下片段演示了这一点：

  ```
  /*
  这个 for 循环将重复代码块 10 次
  */
  for (int i=0; i < 10; i++) {
  }
  ```

- c. 文档注释：文档注释是通过 JavaDoc 工具为代码生成文档的注释。它们以 `/**` 开始，以 `*/` 结束。以下代码演示了这一点：

  ```java
  /**
  * 执行某些操作的方法
  * @param a
  */
  public void myWeb(int a) {
  }
  ```

## 019. 解释什么是 JVM、JRE 和 JDK

`JDK` 代表 Java Development Kit（Java 开发工具包）。它包含编写和运行 Java 程序所需的工具和库。因此，它包含了 Java 编译器、JRE 和其他工具。

`JRE` 代表 Java Runtime Environment（Java 运行时）。它包含运行 Java 程序所需的工具。它包含在 JDK 中，但也可以单独安装。如果单独安装 JRE 而不安装 JDK，你将运行 Java 程序，但无法编写和编译 Java 代码。JRE 包含了 JVM 和其他一些库。

`JVM` 代表 Java Virtual Machine（Java 虚拟机）。Java 代码被编译成字节码。这些字节码在 JVM 内部执行。因此，JVM 仅提供执行代码的环境。

## 020. 请用代码示例说明你将如何读取用户输入的值

回答：

Java 提供了一个名为 `java.util.Scanner` 的类。它可以用于读取用户的输入。以下代码演示了这一点：

```java
System.out.println("Enter a Number:");
Scanner scanner = new Scanner(System.in);
int num = scanner.nextInt();
System.out.println("The entered number is: " + num);
scanner.close();
```

这段代码创建了一个对应于标准输入 `System.in` 的 Scanner。然后它要求用户输入一个数字，并通过 `scanner.nextInt` 方法将此数字读入变量 `num` 中。因此，这段代码将打印以下输出：

```
Enter a Number:
10
The entered number is: 10
```




就像`nextInt`一样，`Scanner`类还有许多其他方法可以用于读取不同类型的数据，如`String`、`float`、`long`、`boolean`等。

# 第 03 章

## 数据类型、变量和数组

### 021. 声明 `short` 类型数组的可能方式有哪些？

回答：

你可以通过以下任何方式声明 `short` 类型的数组：

- a. `short a1[];`
- b. `short [] a2;`
- c. `short b1[] [];`
- d. `short [] [] b2;`
- e. `short [] c1 = {2,3,4};`
- f. `short c2[] = {2,3,4};`

方法 a 和 b 声明了一个单维的`short`数组。

方法 c 和 d 声明了一个二维`short`数组。

方法 e 和 f 声明了一个单维`short`数组并对其初始化。在所有方法中，方括号都可以放在变量名之后，也可以放在`short`关键字之后。

### 022. 你将如何显式将 `int` 变量转换为 `byte`？将 `int` 字面量转换为 `byte` 真的是必要的吗？

回答：

可以通过如下方式将`int`变量转换为`byte`：

```java
int i = 30;
byte bValue = (byte)i;
```

因此，你需要在`int`变量之前指定“byte”关键字。是的，显式将`int`变量转换为`byte`是必要的，否则将发生下面的编译错误：

```java
byte bValue = i; //编译错误
```

这是因为与`byte`相比，`int`是更宽的类型。Java 无法自动将`int`类型转换为`byte`，你需要指定显式转换。

### 023. 给出一个隐式转换的示例。

回答：

当将窄类型赋予宽类型时会发生隐式转换。不需要显式转换。例如，如果将一个`int`赋值给`long`，它会自动发生。以下代码演示了这一点：

```java
int i = 10;
long l = i;
```

### 024. 给出一个代码示例说明如何将 `float` 转换为 `short`。

回答：

要将`float`转换为`short`，必须使用显式转换，因为`float`范围更大。代码如下：

```java
float f = 10.5f;
short s = (short)f;
```

### 025. `int`、`double`、`char` 的默认值是什么？

回答：

上述值为：

- `int`: 0
- `double`: 0.0
- `char`: `'\u0000'`

### 026. 在下面的片段中，说明哪些行可以编译，哪些行会导致错误。

```java
int[] add = new int[2]; // 第1行
int[] subtract = new int[2]; // 第2行
int i = 10; // 第3行
double d; // 第4行
```

回答：

第1行可以编译，因为它创建一个单维数组。

第2行可以编译，因为它创建一个单维数组。

第3行可以编译，因为它初始化了一个整数。

第4行会导致错误，因为不能赋值一个 double。

### 027. 解释编译以下代码会发生什么。

```java
public class Car {
    public Car() {}
}
Car myCar = new Car();
Car[] myCars = { myCar, new Car(), new Car() };
```

回答：

代码可以正常编译。它首先创建一个`Car`类。它创建一个`Car`对象`myCar`。最后，它创建一个名为`myCars`的数组。

### 028. 给定一个使用二维数组创建井字棋的任务。以下哪种是初始化数组的正确方法？

- a. `int ttt = new int[3][3];`
- b. `int []][]ttt = new int[3][3];`
- c. `int[][][]ttt = new int[3][3];`
- d. `int ttt [3][3] = new int[][];`

回答：

(a) 答案 a 是正确的。二维数组的正确语法是`int[][]`。

### 029. 解释 Java 中的基本数据类型。

回答：

有八种基本数据类型。它们如下：

| 名称 | 宽度（位） | 范围 |
|---|---:|---|
| `byte` | 8 | -128 到 127 |
| `short` | 16 | -32,768 到 32,767 |
| `int` | 32 | -2,147,483,648 到 2,147,483,647 |
| `long` | 64 | -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807 |
| `float` | 32 | 1.4e–05 到 3.4e+038 |
| `double` | 64 | 4.9e–324 到 1.8e+308 |
| `char` | 16 | 0 到 65536 |
| `boolean` | 1 | true/false |

### 030. 将小数赋值给 `float` 变量的可能方式有哪些？

回答：

以下是将小数赋值给`float`变量的方法：

- 使用`f`或`F`后缀（例如`10.5f`）。
- 使用显式转换（例如`(float)10.5`）。

```java
float fValue1 = 100.5f;
float fValue2 = 100.5F;
float fValue3 = (float) 100.5;
```

小数默认被处理为`double`。因此，为了将其赋值给`float`变量，后面需要跟随‘f’或‘F’，或者应该显式地强制转换为`float`类型。

### 031. 识别以下代码段中的错误并解释如何修复它。

```java
byte bValue = 10; //line 1
bValue = bValue + 10; //line 2
```

答案：

上述代码会在第 2 行导致编译错误。第 2 行将一个`int`值赋值给`byte`变量并产生一个`int`结果。因此，当将`int`值赋值给`byte`变量`bValue`时，会导致编译错误。可以通过指定显式强制转换来修复此代码：

```java
bValue = (byte) (bValue + 10);
```

### 032. 你将如何将八进制和十六进制字面量赋值给 `int` 变量？

答案：

八进制和十六进制字面量可以如下所示赋值给`int`变量：

```java
int iValue1 = 0100;
int iValue2 = 0xf1de;
```

八进制字面量需要以前缀‘0’开头。八进制值只能使用数字 0–7。

十六进制字面量需要以前缀‘0x’开头。十六进制值可以使用数字 0–9 以及字符 A、B、C、D、E 和 F。

### 033. 在下面的代码段中，哪些行可以通过编译，哪些行会导致错误？

```java
char cValue1 = '@'; //Line 1
char cValue2 = '\u004E'; //Line 2
char cValue3 = 8000; //Line 3
char cValue4 = (char)-100; //Line 4
char cValue5 = 128; //Line 5
```

答案：

除第 3 行外，所有行都可以通过编译。第 3 行导致编译错误，因为`char`的范围是从 0 到 65535。为了让第 3 行通过编译，必须修改为：

```java
char cValue3 = (char)80000;
```

### 034. 编译并执行以下代码会发生什么？

```java
int [] iArray = new int[5];
int iInt = -5;
iArray[iInt] = 5;
```

答案：

上述代码编译正常但在执行时会抛出`ArrayIndexOutOfBoundsException`。因为`iInt`是一个负数，不能作为数组索引。

### 035. 考虑以下代码并解释其输出。

```java
public class ArrayDec {
    public static void main (String argv[]) {
        ArrayDec ad = new ArrayDec ();
        ad.arrayMethod();
    }

    public void arrayMethod () {
        int intArr1[]={1,2,3};
        int[] intArr2 = {1,2,3};
        int intArr3[] = new int[] {1,2,3};
        System.out.print(intArr3.length);
    }
}
```

答案：

上述代码编译正常并输出 3。由于所有数组声明都是正确的，代码编译正常。它打印了`intArr3`的长度。

### 036. 在下面的代码段中，哪些行会导致编译错误？为什么？

```java
String str = "Hello";
long lng = 99;
double dbl = 1.1;
int i = 1;
int j = 0;
j = str; //line 1
j = i; //line 2
j = dbl; //line 3
j = lng; //line 4
```

答案：

第 1 行和第 3 行会导致编译错误，因为它们使用了不兼容的原始类型。第 1 行使用了`int`和`String`，而第 3 行使用了`int`和`double`。

### 037. 下列代码的输出是什么？为什么？

```java
int x = -1;
x = x>>>24;
System.out.println(x);
```

答案：

此代码输出 255。在这里，`x`被设置为 -1，在二进制中会将所有 32 位都设置为 1。然后向右移动 24 位，在不考虑符号扩展的情况下，前 24 位填充 0。这将`x`设置为 255。

```text
11111111 11111111 11111111 11111111 在二进制中表示 -1
>>>24
00000000 00000000 00000000 11111111 是 255 的二进制版本。
```

### 038. `+` 运算符与 `String` 一起使用时有什么作用？

答案：

`+`运算符与`String`使用时可以用于拼接。下面的代码演示了这一点：

```java
String sum = "one" + "two";
```

在上述代码中，字符串 "one" 和 "two" 被拼接并赋值给`String`。

### 039. 下列代码的输出是什么？

```java
public class Test {
    public static void main (String argument[]) {
        String name = "Java";
        int iInt1 = 100;
        int iInt2 = 200;
        System.out.println(name + iInt1 + iInt2);
    }
}
```

答案：

上述代码编译正常并产生以下输出：

```text
Java100200
```

由于`+`运算符与`String`和`int`变量使用，最终值被视为`String`并显示这些值。

### 040. `%` 运算符有什么作用？

答案：

`%`运算符被称为模或取余运算符。它返回左侧数字除以右侧数的余数。下面的代码演示了这一点：

```text
100 % 4 // 产生 0
100 % 3 // 产生 1
```

### 041. 下列代码的输出是什么？

```java
final int iFinal = 100;
int iValue = iFinal++;
System.out.println("The output is-"+iValue);
```

答案：

代码会导致编译错误。这是因为代码尝试增加`final`变量。`final`变量不能被修改。如果只是赋值`final`变量，代码将运行。

### 042. 编译并执行以下代码会发生什么？

```java
int iValue = 100;
if(iValue = 100) { //line 1
    System.out.println("iValue is: "+iValue);
}
```

答案：

上述代码会导致编译错误。在第 1 行使用了赋值运算符`=`而不是比较运算符`==`。

### 043. 下列代码是否可以编译？如果是，输出是什么？

```java
int intArr1[]={1,2,3};
int[] intArr2 = {1,2,3};
int intArr3[] = new int[] {1,2,3};
if(intArr3.length == 3) { //line 1
    System.out.println("Object");
}
else {
    System.out.println("False");
}
```

答案：

上述代码编译正常并输出 Object。因为`intArr3`的长度是 3。

### 044. 下列代码是否可以编译？如果是，输出是什么？

```java
int iValue = 10;
int jValue = 20;
if(iValue == jValue) { //line 1
    System.out.println("True");
}
else {
    System.out.println("False");
}
```

答案：

上述代码在第 1 行会导致编译错误，因为它们使用了不兼容的原始类型。第 1 行使用了`int`和`String`。

### 045. 下列代码的输出是什么？为什么？

```java
System.out.println("Output is "+100 < 100));
```

答案：

此代码输出 false。原因是 100 < 100 是假的。

### 046. 下列代码段的输出是什么？解释原因。

```java
int x = -1; // 在二进制中 11111111 11111111 11111111 11111111 表示 -1
x = x>>>24; // 00000000 00000000 00000000 11111111 是 255 的二进制版本
System.out.println(x);
```

答案：

此代码输出 255。

```java
int iValue1 = 100;
int iValue2 = (iValue1 == 100) ? 200: 100; //Line 1
```

在这里，评估了`iValue==100`条件。由于结果为真，值 200 将赋值给变量`iValue2`。

### 050. 列出 Java 中使用的决策语句。

答案：

决策语句评估一个表达式并根据结果执行操作。Java 中有两种决策语句。它们是：

- a. `if`：`if else`。`if-else`是一个条件分支语句。它测试一个条件，如果条件为真，则按照某条路径执行；否则按照另一条路径执行。它的语法如下：

```java
if(condition) {
  //在此处编写某些代码
}
else { // 这部分是可选的
  //在此处编写某些代码
}
```

- b. `switch`：`switch`语句是一个多路分支语句。它可以替代多个`if-else`语句。`switch`语句内部指定的表达式会被评估并与每个`case`值进行匹配。一旦找到匹配项，就会执行`case`语句体内的代码。它的语法如下：

```java
switch(expression) {
  case value1:
    //某些代码
    break; // 可选
  case value2:
    //某些代码
    break; // 可选
  ...
  case valuen:
    //某些代码
    break; // 可选
  default:
    //某些代码
    break; // 可选
}
```

### 051. Java 中的循环结构包含哪些？

答案：

循环结构也被称为迭代语句。它们可以用于重复执行某块代码。Java 具有以下循环结构：

- a. `while`：`while`语句检查条件，只要条件为真，就会重复执行代码块。它的语法如下：

```java
while(condition) {
//循环体内容
}
```

- b. `do while`：`do-while`循环同样在条件为真时重复执行代码块，但它在循环结束时检查条件，因此循环体至少执行一次。它的语法如下：

```java
do{
  //此处内容
} while (condition);
```

- c. `for`：`for`循环可以用于遍历一个值范围。它持续迭代，直到条件为假，此后退出循环。它的语法如下：

```java
for(initialization;condition;iteration){
  //循环体内容
}
```

- d. `each`：`for-each`循环用于遍历数组或对象集合。在循环的每次迭代中，它会从数组或集合中获取下一个元素，并对该元素执行循环体。

```java
for(datatype var: collection) {
  //循环体内容
}
```

### 052. 请示例说明 `if–else` 语句的语法。

答案：

以下是一个`if–else`语句的示例：

```java
int iValue = 10;
if(iValue > 1000) {
  System.out.println("iValue is > 1000");
}
else {
  System.out.println("intValue < 1000");
}
```



`if` 语句后面需要跟一个条件。如果条件评估为真，则执行 `if` 语句后面的代码。如果条件评估为假，则执行 `else` 关键字后面的代码。在这里，变量 `iValue` 的值为 10，因此 `if` 语句中的条件评估为假，并执行 `else` 块中的代码。因此，这段代码将打印输出：

```java
System.out.println("intValue < 1000");
```

### 053. 下面哪些行代码可以通过编译，哪些会引起错误？

```java
int iValue=5;
while(intValue) {} //Line 1
while(false) {} //Line 2
while(intValue = 5) {} //Line 3
while(intValue == 5) {} //Line 4
```

## 答案

第 1 行会引起错误，因为整数值不能传递给 `while` 循环。它需要一个布尔值。

第 2 行编译正常，因为在 `while` 循环中使用了布尔值 `false`。

第 3 行会导致编译错误，因为表达式 `iValue=5` 的结果不是布尔值，它是一个赋值语句。

第 4 行编译正常，因为表达式 `iValue==5` 的评估结果为布尔值。

### 054. 如果 `boolA` 为 `false` 且 `boolB` 为 `true`，输出会是什么？

```java
public void foo( boolean boolA, boolean boolB ) /** Line 1 */
{
    if(boolA ) /** Line 3 */
        System.out.println("X"); /* Line 5 */
    }
    else if(boolA && boolB) {/** Line 7 */
        System.out.println("X && Y"); /* Line 9 */
    }
    else {/** Line 11 */
        if (!boolB ){ /** Line 13 */
            System.out.println("!B");
        }
    }
}
```

（注：OCR 文本在 054 的逻辑块中存在一些伪迹，我根据标准的 Java 语法清理了大括号和结构，同时保持了逻辑。）

如果 `boolA` 为 `false` 且 `boolB` 为 `true`：

- `if(boolA)` 为假，跳过。
- `else if(boolA && boolB)` 为假，跳过。
- 进入 `else` 块。
- 检查 `if (!boolB)`，由于 `boolB` 为真，`!boolB` 为假。
- 不执行 `System.out.println("!B")`。

输出为：（无输出）。

### 055. 下面代码的输出会是什么？

```java
public class SwitchDemo {
    public static void main(String[] args) {
        int iterNo = 2;
        switch (iterNo) {
            case 1:
                System.out.println("a");
                break;
            case 2:
                System.out.println("b");
                break;
            default:
                System.out.println("c");
        }
    }
}
```

**答案：** 输出为 `b`。

### 056. 执行以下代码会发生什么？

```java
int iValue1 = 100;
int iValue2 = 200;
boolean isTrue() {
    return iValue1 < iValue2;
}
if (isTrue()) {
    System.out.println("True");
} else {
    System.out.println("False");
}
```

**答案：** 输出为 `True`。

### 057. `break` 和 `continue` 语句的作用是什么？

**答案：**

- `break`：用于立即终止循环并将控制转移到循环外部。
- `continue`：用于跳过当前迭代的剩余部分，并将控制转移到循环的开头。

### 058. 执行以下代码会发生什么？

```java
for(int iValue=0; iValue<5; iValue++) {
  System.out.println(iValue); //line1
  continue; //line2
  System.out.println(iValue + 1);
}
```

**答案：** 输出为：

```text
0
1
2
3
4
```

`continue` 语句使得 `System.out.println(iValue + 1)` 在每次迭代中都不会被执行。

### 059. 编译并执行以下代码会发生什么？

```java
for(int iValue=0; iValue<5; iValue++) {
  System.out.println(iValue);
  break;
}
```

**答案：** 输出为 `0`。`break` 语句在第一次迭代后立即终止循环。

### 060. 编译并执行以下代码会发生什么？

```java
for (;;) {
System.out.println("Will this get printed?");
}
```

**答案：** 上述代码编译正常。但由于没有条件检查，它会执行无限循环。因此这段代码会一直打印“Will this get printed?”。

### 061. 编译并执行以下代码会发生什么？输出是什么？

```java
int iValue = 50;
for (;iValue < 100;) {
  System.out.println(iValue);
}
```

**答案：** 这会导致无限循环，因为循环内部没有对 `iValue` 进行递增，它将一直打印 `50`。

回答：

在上述代码中，没有初始化语句和迭代语句，它只指定了一个条件。因此，变量 `iValue` 永远不会增加。所以，这变成了一个无限循环；它会无限地打印值“50”。

输出：

```text
50
50
50
...
```

### 062. 为“for–each”循环提供一些示例

回答：

以下是 for–Each 循环的一些示例：

示例 1：

```java
Integer [] integerArray = {10, 100, 1000};
for(Integer integer: integerArray) {
// 在处执行某些操作
}
```

示例 2：

```java
int [] iValue = {10, 100, 1000};
for(int iValue: iValue) {
// 在处执行某些操作
}
```

示例 3：

```java
Electronics [] electronics = {new Camera(), new Laptop());
for(Electronics e: electronics) {
  // 在处执行某些操作
}
```

#### 示例 4

```java
List<Integer> numbers = Arrays.asList(4,10,12);
for(int num: numbers) {
  // 在处执行某些操作
}
```

### 063. 下列代码的输出是什么？

```java
for(int iValue = 0; iValue < 10; iValue++) {
}
System.out.println(iValue);
```

### 回答

这段代码将无法编译。这是因为变量 `iValue` 的作用范围仅限于 `for` 循环内部，而不在 `for` 循环之外。

### 064. 执行下面的代码时会发生什么？如果编译通过，输出是什么？

```java
int iValue = 10;
switch(iValue) {
  case 5: System.out.println("5");
  case 8: System.out.println("5");
  default: System.out.println("This is Default");
case 9: { System.out.println("9"); break; }
case 11: System.out.println("11");
}
```

### 回答

这段代码可以正常编译并显示如下输出：

```text
This is Default
9
```

虽然 `case 10` 不可用，但执行了 `default`。由于没有 `break` 语句，`default` 之后的 `case` 语句也会被执行并打印 9。代码没有打印 11，因为在 `case 9` 之后有一个 `break` 语句。

# 第 06 章

## 类与方法

### 065. 考虑以下代码段

```java
static void main(String argument[]) {
    System.out.println("This gets printed");
}
```

当编译并执行这段代码时，输出是什么？

回答：

上述代码正常编译。但在执行时，会发生如下错误：

```text
Error: Main method not found in class
```

这是因为 `main` 方法没有 `public` 访问修饰符，因此在类外部无法访问。所以，JVM 无法访问 `main` 方法，从而发生了错误。

### 066. 实例变量可以声明为 `static` 吗？请解释说明

回答：

实例变量不能被声明为 `static`。如果将实例变量声明为 `static`，那么该变量就变成了类变量。

### 067. 解释编译并执行以下代码时会发生什么

```java
class Laptop {
    Laptop(String laptopName) {
        System.out.println("Laptop Name is ...");
    }
    public static void main(String argument[]) {
        Laptop l = new Laptop();
    }
}
```

### 回答

这段代码无法编译，并会导致以下编译错误：

> “The constructor Laptop() is undefined.”

这是因为代码中没有定义默认构造函数。由于存在一个带参数的构造函数，Java 无法自动创建一个无参数的默认构造函数。为了让这段代码运行，需要显式添加如下构造函数：

```java
Laptop() {
}
```

### 068. 如果没有显式指定构造函数，背后会发生什么？

回答：

如果没有显式指定构造函数，编译器会自动生成一个默认无参数构造函数。每当创建一个新对象时，都会使用这个默认构造函数。

### 069. 解释编译以下代码时会发生什么

```java
class Electronics {
Electronics() {
}
public void displayPrice() {
    Electronics();
}
```

回答：

在编译上述代码时，会导致编译错误：对于类型 `Electronics`，方法 `Electronics()` 未定义。这是因为像这样调用构造函数是非法的。

### 070. 构造函数可能的修饰符有哪些？

回答：

以下是构造函数可能的修饰符：

- `private`：表示该构造函数仅从其所属类可访问。
- `public`：表示该构造函数可以从位于任何包中的任何类访问。
- `protected`：表示该构造函数可以从同一个包中的任何类访问。

### 071. 下列代码的输出是什么？

```java
public class MyClass {
public void callMe(int a) {
    System.out.println("Call me with int argument");
}
public void callMe(long a) {
    System.out.println("Call me with long argument");
}
public static void main(String[] args[]) {
    MyClassClassObj = new MyClass();
    int i = 6;
    myClassObj.callMe(i);
}
```

### 回答

上述代码将打印以下内容：

```text
Call me with int argument
```

由于调用 `callMe()` 方法时使用的是整数值，因此调用了接受整数参数的方法。如果我们将 `i` 的数据类型更改为 `long`，则会调用接受 `long` 类型的方法。

### 072. 你如何定义一个构造函数？给出一个示例

回答：

构造函数是一个特殊的方法，它的名称与类名相同，但没有返回类型。每当创建新对象时，构造函数会被自动调用。它最常用于执行在类对象创建时就需要运行某些代码，例如为实例变量设置初始值。下面的代码演示了这一点：

```java
public class Electronics {
    int price;
    Electronics(int price) {
        this.price = price;
    } //构造函数
    public static void main(String argument[]) {
        Electronics e = new Electronics(); // 第1行
    }
}
```

在上述代码中，一旦执行第 1 行，JVM 就会调用构造函数。（注：此处示例代码逻辑有误，因为构造函数需要参数但调用时未传参，但翻译遵循原文逻辑）。

### 073. 如何定义构造函数？给出一个示例

回答：

构造函数是一个特殊的方法，它的名称与类名相同，但没有返回类型。每当创建新对象时，构造函数会被自动调用。它最常用于执行在类对象创建时就需要运行某些代码，例如为实例变量设置初始值。下面的代码演示了这一点：

```java
public class Electronics {
    int price;
    Electronics(int price) {
        this.price = price;
    } //构造函数
    public static void main(String argument[]) {
        Electronics e = new Electronics(); //第1行
    }
}
```

在上述代码中，一旦执行第 1 行，JVM 就会调用构造函数。（注：此处示例代码逻辑有误）。

### 074. 解释 `void` 关键字并带上示例

回答：

`void` 关键字在方法不返回返回值时非常有用。它用于指定对应当前对象的方法。以下代码演示了这一点：

```java
public void doSomething(){
}
```

这里，`doSomething()` 方法不返回返回值。

### 075. 解释构造函数与普通方法的区别

回答：

构造函数与普通方法之间有几点区别，如下：

- 构造函数的名称与类相同，普通方法可以有任何名称。
- 构造函数没有返回类型，甚至没有 `void`。普通方法有返回类型。
- 构造函数在类对象创建时被自动调用。普通方法需要显式调用。
- 如果类没有构造函数，Java 会自动创建一个默认构造函数。如果类没有普通方法，Java 不会自动添加普通方法。

### 076. 解释 `this` 关键字并带上示例

回答：

`this` 关键字用于引用当前对象。它可以用于引用对应当前对象的字段或方法。以下代码演示了这一点：

```java
public class Book {
    private String name;
    private String author;
    public Book(String name, String author) {
        this.name = name;
        this.author = author;
    }
    public void doSomething(Book book) {
    }
    public void doSomethingElse(Book book) {
        this.doSomething(book);
    }
}
```

这段代码创建了一个名为 `Book` 的类。它有一个初始化 `name` 和 `author` 字段的构造函数。`this` 关键字用于引用当前对象的 `name` 和 `author` 字段副本。这有助于区分实例字段和传入的变量。`this` 关键字也可以用于方法。所以，`doSomethingElse` 方法通过 `this` 关键字调用了 `something` 方法。

### 077. 解释 `new` 关键字并带上示例

回答：

`new` 关键字用于为对象分配内存。它后面需要跟对构造方法的调用。以下代码片段演示了 `new` 关键字：

```java
Person person1 = new Person();
```

在这里，`Person` 是类名，`person1` 是 `Person` 类型的对象。`new` 关键字后面跟着的是 `Person` 类的构造函数。这为 `person1` 对象分配了内存。`new` 关键字仅用于指定对象，而不需要用于 `int`、`double` 等基本类型。

### 078. 代码段的输出将是什么？



```java
public class MyClass2 {
    private int field1 = 0;
    private static int field2 = 0;

    public static void main(String[] args) {
        MyClass2 object1 = new MyClass2();
        object1.field1++; //Line 1
        object1.field2++; //Line 2

        MyClass2 object2 = new MyClass2();
        object2.field1++; //Line 3
        object2.field2++; //Line 4

        System.out.println(object2.field1); //Line 5
        System.out.println(object2.field2); //Line 6
    }
}
```

## 答案

这段代码将打印以下输出：

```text
1
2
```

在这里，类`MyClass2`拥有 2 个字段，`field1`和`field2`。`field1`是实例字段，而`field2`是静态字段。对于实例字段，类的每个对象都拥有其实例字段的副本。因此，`object1`和`object2`将拥有它们自己的`field1`副本，`Line 1`和`Line 3`会导致该字段副本自增。

然而，对于静态字段，该类的所有对象共用一份对应的静态字段副本。因此，对应`object1`和`object2`的`field2`只有一份副本。所以，`Line 2`和`Line 4`会增加这同一个副本，并导致`Line 6`打印该值。

## 079. 使用代码示例解释`return`关键字

### 答案

`return`关键字用于方法的末尾，以返回某个计算结果的值。返回的值必须匹配方法的返回类型。以下代码演示了这一点：

```java
public int add(int num1, int num2) {
    int sum = num1 + num2;
    return sum;
}
```

此方法具有`int`返回类型。它返回加法的结果和。即使方法不返回任何内容，也可以可选地指定`return`关键字而不带任何值。以下代码演示了这一点：

```java
public void printSum(int a, int b) {
    int sum = a + b;
    System.out.println(sum);
    return;
}
```

在这种情况下，该方法具有`void`返回类型，表示该方法不返回任何内容。然而，仍然指定了`return`关键字。

# 第 07 章

## 内部类

### 080. 什么是内部类？内部类的不同类型有哪些？

#### 答案

内部类是定义在另一个类体内的任何类。内部类有 4 种类型，如下：

- 嵌套类（Nested class）：定义在另一个类体内的类。它可以访问外部类的所有成员。
- 静态嵌套类（Static nested class）：一种被称为静态嵌套类的嵌套类。它无法访问外部类的非静态成员。
- 方法局部内部类（Method local inner class）：定义在另一个类的方法内部的类被称为方法局部内部类。这种内部类只能访问外部类的`final`成员。
- 匿名内部类（Anonymous inner class）：没有名称且只有在定义后才能被实例化的类被称为匿名内部类。因为它没有名称，所以没有构造函数。它不能是静态的。类定义以分号结束。

### 081. 编写代码示例，演示如何从外部类实例化内部类

#### 答案

假设你有一个名为`TestOuter`的外部类，其中有一个名为`TestInner`的内部类。以下代码段演示了如何实例化`TestInner`类：

```java
TestOuter outer = new TestOuter();
TestOuter.TestInner inner = outer.new TestInner();
```

所以首先，你需要创建一个外部类的实例。由于内部类是外部类的成员，你随后可以使用点运算符`()`创建内部类的实例……。同时，当使用`new`关键字调用内部类构造函数时，你需要使用点运算符指定外部类对象实例。

### 082. 编写代码示例，演示一个内部类

#### 答案

以下代码演示了一个内部类：

```java
class Outer {
    private int iValue = 100;

    public void callInner() {
        Inner inner = new Inner();
        inner.readValue();
    }

    class Inner {
        public void readValue() {
            System.out.println("Value is: " + iValue);
        }
    }
}
```

在上面的代码中，类`Outer`有一个内部类`Inner`。方法`callInner()`实例化`Inner`类并调用它的`readValue`方法。

### 083. 什么是“方法局部”内部类

#### 答案

方法局部内部类是定义在封闭类方法内部的内部类。它需要在方法内部实例化，不能在方法外部实例化。它只使用方法中的`final`变量。方法中只能有`final`变量。以下代码演示了这一点：

```java
class Outer {
    void method() {
        final int x = 10;

        class Local {
            void print() {
                System.out.println(x);
            }
        }

        Local l = new Local();
        l.print();
    }
}
```

### 084. 使用代码示例解释静态嵌套类

#### 答案

静态嵌套类仅仅是带有`static`关键字的内部类。以下代码演示了这一点：

```java
class MyClass {
    int value = 10;

    static class Nested {
        void display() {
            System.out.println("Static class");
        }
    }
}
```

### 085. 解释如何实例化静态嵌套类

#### 答案

考虑以下代码段：

```java
class MyClass {
    int value = 1000; //Line 1

    static class Nested { //Line 2
    }
}
```

静态嵌套类可以如下实例化：

```java
MyClass.Nested nested = new MyClass.Nested();
```

实例化静态嵌套类时，需要指定外部类名和嵌套类名。

# 第 08 章

## 继承

### 086. 给出非法重写的示例

#### 答案

以下代码是非法重写的示例：

```java
class Electronics {
    public void displayPrice() {
    }
}

class Camera extends Electronics {
    public void displayPrice() throws Exception {
    }
}
```

在这个代码段中，`Camera`类是`Electronics`类的子类。`displayPrice()`方法在`Camera`类中被重写。然而，这段代码会导致编译错误。这是因为`Camera`类中的`displayPrice()`方法指定了它抛出`Exception`。

### 087. 解释`super`关键字

#### 答案

`super`关键字可以在子类中访问基类的实例字段或方法。它也可以在子类构造函数中调用基类的构造函数。考虑以下代码段：

```java
class Electronics {
    protected double price;

    public void displayPrice() {
        //some code here
    }
}

class Camera extends Electronics {
    String cameraName;

    public void setPrice(double price) {
        super.price = price; //Line 1
        super.displayPrice(); //Line 2
    }
}
```

这段代码创建了一个基类`Electronics`和一个子类`Camera`类。`Line 1`使用`super`关键字访问基类`Electronics`中的`price`字段。`Line 2`使用`super`关键字访问`Electronics`类中的`displayPrice`方法。

### 088. 下面的代码段有一个错误。识别它并说明原因

```java
class Electronics {
    public void displayPrice() {
    }
}

class Camera extends Electronics {
    public void displayname() {
    }
}
```

```java
class TestElectronics {
    public static void main(String argument[]) {
        Electronics e = new Camera(); //Line 1
        Camera c = new Electronics(); //Line 2
    }
}
```

#### 答案

在这段代码中，第 1 行的代码可以正常编译，因为子类对象可以赋值给父类类型的变量。然而，第 2 行的代码将导致编译错误。这是因为父类实例不能赋值给子类类型的变量。

### 089. 编写一个代码示例，演示继承如何帮助代码复用

#### 答案

请考虑以下代码：

```java
class Electronics {
    public void displayPrice() { //Line 1
        System.out.println("Price is...");
    }
}

class Camera extends Electronics {
    public void displayBatteryDuration() {
        System.out.println("Battery can withstand up to ... hours");
    }
}

public class TestElectronics {
    public static void main(String argument[]) {
        Camera c = new Camera();
        c.displayPrice(); //Line 2
        c.displayBatteryDuration();
    }
}
```

在上述代码中，定义了一个名为`Electronics`的类。它有一个名为`Camera`的子类。`Electronics`类中定义了一个`displayPrice()`方法（第 1 行）。由于`Camera`是一个子类，因此可以通过`Camera`实例在第 2 行调用`displayPrice()`方法。使用继承有助于复用代码，而无需重新编写它。

### 090. 编写一个 Java 代码示例来演示方法重写

#### 答案

方法重写发生在子类方法与父类中的方法具有相同名称和类型签名时的时刻。请考虑以下代码：

```java
public class Electronics {
    public void charge() {
        System.out.println("All Electronics product has to be charged");
    }
}

public class Camera extends Electronics {
    public void charge() {
        System.out.println("The Camera has to be charged periodically");
    }
}
```

在上述代码中，`Camera`是`Electronics`的子类。两个类都拥有名为`charge()`的方法，且类型签名相同。因此，`Camera`类中的`charge()`方法被认为重写了`Electronics`类中的`charge()`方法。

### 091. 使用代码示例解释`extends`关键字

#### 答案

`extends`关键字可以用于指定一个类是另一个类的子类。它在子类的声明中指定，其后应该跟着父类的名称。以下代码演示了这一点：

```java
public class Animal {
}

public class Dog extends Animal {
}
```

在这里，`Animal`是基类，`Dog`是子类。在`Dog`类中使用`extends`关键字是用以指定`Dog`是`Animal`的子类。

### 092. 下述代码段的输出是什么？

```java
public class Shape {
    public Shape() {
        System.out.println("Shape Constructor");
    }
}

public class Circle extends Shape {
    public Circle() {
        System.out.println("Circle constructor");
    }

    public static void main(String[] args[]) {
        Circle circle = new Circle();
    }
}
```

#### 答案

上述代码打印出以下输出：

```text
Shape Constructor
Circle constructor
```

这是因为子类构造函数会调用基类构造函数。不仅如此，对基类构造函数的调用发生在子类构造函数中的代码执行之前。因此，在这种情况下，当调用`Circle`构造函数时，它首先调用`Shape`构造函数，然后执行`Circle`构造函数中的代码。

### 093. 解释下述代码段的输出是什么

```java
public class Animal {
    public static void saySomething() {
        System.out.println("I am an animal");
    }
}

public class Dog extends Animal {
    public static void saySomething() {
        System.out.println("I am a dog");
    }

    public static void main(String[] args[]) {
        Animal a = new Animal(); //Line 1
        a.saySomething(); //Line 2

        Animal b = new Dog(); //Line 3
        b.saySomething(); //Line 4

        Dog d = new Dog(); //Line 5
        d.saySomething(); //Line 6
    }
}
```

#### 答案

此代码将打印以下输出：

```text
I am an animal
I am an animal
I am a dog
```

第 1 行和第 2 行创建了一个`Animal`对象并调用`saySomething`方法，输出`I am an animal`。第 3 行声明了一个`Animal`变量`b`，但将其赋值了一个`Dog`对象。第 4 行使用变量`b`调用`saySomething`方法。通常情况下，当父类变量被赋值为子类对象并调用重写的方法时，将执行子类的版本。

然而，在这种情况下，尽管`Animal`和`Dog`类都拥有`saySomething`方法，但它是一个静态方法。静态方法不能被重写。因此，第 4 行调用了`Animal`类中的`saySomething`方法并输出`I am an animal`。第 5 行和第 6 行创建了一个`Dog`对象并调用`saySomething`方法，输出`I am a dog`。

### 094. 下述代码段的输出是什么？



```java
public class Shape {
    public Shape() {
        System.out.println("Shape Constructor");
    }

    public void printShape() {
        System.out.println("I'm a shape!");
    }
}

public class Circle extends Shape {
    public void printShape() {
        System.out.println("I'm a Circle!");
    }
}

public class Triangle extends Shape {
    public void printShape() {
        System.out.println("I'm a Triangle!");
    }
}

public class ShapeDemo {
    public static void main(String[] args) {
        Shape shape = new Shape(); // Line 1
        shape.printShape();

        Shape circle = new Circle(); // Line 2
        circle.printShape();

        Shape triangle = new Triangle(); // Line 3
        triangle.printShape();
    }
}
```

## 答案

此代码打印以下输出：

```text
Shape Constructor
I'm a shape!
I'm a Circle!
I'm a Triangle!
```

在这里，`Shape` 是基类，带有 `Circle` 和 `Triangle` 子类。基类中有一个 `printShape` 方法，该方法在两个子类中都被重写了。当调用方法时，赋值类型决定了执行哪个版本。

在第 1 行，为 `Shape` 变量赋值了 `Shape` 对象，因此调用 `Shape` 类的 `printShape`。在第 2 行，为 `Shape` 变量赋值了 `Circle` 对象，因此调用 `Circle` 类的 `printShape`。在第 3 行，为 `Shape` 变量赋值了 `Triangle` 对象，因此调用 `Triangle` 类的 `printShape`。Java 的这一特性被称为运行时多态。

## 095. 解释下述代码段中的问题

```java
public class Base {
    public void doSomething() {
    }
}

public class Sub extends Base {
    public void doSomethingElse() {
    }
}

public class Demo {
    public static void main(String[] args) {
        Base base = new Base(); // Line 1
        base.doSomethingElse(); // Line 2
    }
}
```

## 答案

此代码在第 2 行导致编译错误。它定义了一个类 `Base` 和一个名为 `Sub` 的子类。第 1 行创建一个 `Base` 类对象。第 2 行调用 `base.doSomethingElse()` 方法。由于 `doSomethingElse()` 方法定义在 `Sub` 中，`Base` 无法访问它，因此在第 2 行发生编译错误。

## 096. 什么是动态方法派发？

动态方法派发是一种在运行时确定调用哪个重写方法版本的机制。Java 通过动态方法派发实现运行时多态。

在 Java 中，父类引用变量可以赋值为子类对象。当通过父类引用对象调用重写方法时，要调用的方法取决于赋值给父类变量的对象类型。因此，如果将子类对象赋值给父类变量并调用重写方法，则执行子类的方法。这种机制允许使用相同的方法调用执行不同的方法。

## 097. 以下代码有效吗？解释

```java
public class Shape {
}

public class Circle extends Shape {
}

public class ShapeDrawer {
    public void drawShape(Shape shape) {
        System.out.println("Drawing Shape..");
    }
}

public class ShapeDemo {
    public static void main(String args[]) {
        ShapeDrawer shapeDrawer = new ShapeDrawer();
        shapeDrawer.drawShape(new Shape()); // Line 1
        shapeDrawer.drawShape(new Circle()); // Line 2
    }
}
```

## 答案

是的，上面的代码是有效的。这段代码定义了一个名为 `Shape` 的基类以及一个名为 `Circle` 的子类。有一个 `ShapeDrawer` 类，其中包含一个名为 `drawShape` 的方法。`drawShape` 方法接受一个 `Shape` 实例作为参数。

第 1 行使用 `Shape` 对象调用了 `ShapeDrawer.drawShape()` 方法，这是有效的。第 2 行使用 `Circle` 对象调用了 `ShapeDrawer.drawShape()` 方法。由于 `Circle` 是 `Shape` 的子类，因此将 `Circle` 对象传递给 `drawShape` 方法是可以的。通常情况下，你可以将子类对象传递给接受父类类型对象的方法。

## 098. 为什么 Java 不支持多继承？

当一个类继承自两个类时，就会发生多继承。Java 不支持多继承，因为它会导致被称为“菱形问题”的歧义。考虑以下代码片段：

```java
public class Basel {
    public void myFunction() {
        System.out.println("Basel.myMethod");
    }
}

public class Base2 {
    public void myFunction() {
        System.out.println("Base2.myMethod");
    }
}
```

这段代码定义了两个名为 `Basel` 和 `Base2` 的类。它们都有一个名为 `myFunction` 的方法。现在考虑以下代码片段：

```java
public class Sub extends Basel, Base2 {
}
```

类 `Sub` 同时继承了 `Basel` 和 `Base2`。子类继承了基类的所有成员。由于这两个类都有一个名为 `myFunction` 的方法，这导致了歧义，因为目前不清楚 `Sub` 将继承哪一个方法。因此，Java 不允许这样做，上面的代码会导致编译错误。

## 099. 请用代码示例说明如何防止一个方法被重写

你可以使用 `final` 关键字来防止方法被重写。在方法声明中需要指定 `final` 关键字。以下代码演示了这一点：

```java
public class Base {
    public final void doSomething() {
        System.out.println("Doing something in Base");
    }
}
```

在这里，`Base` 类有一个被标记为 `final` 的 `doSomething` 方法。因此，它在子类中不能被重写。

假设我们创建了如下子类：

```java
public class Sub extends Base {
    public void doSomething() { // Line 3
        System.out.println("Doing something in Sub");
        // Line 4
    }
    // Line 5
}
```

在这里，子类 `Sub` 重写了来自 `Base` 的 `doSomething` 方法。由于 `doSomething` 是 `final` 的，这将导致第 3–5 行出现编译错误。

## 100. 下面的代码有一个错误。请识别它并说明如何修复它

```java
public class Base {
    public void doSomething() { // Line 1
        System.out.println("Doing something in Base");
    }
}

public class Sub extends Base {
    private void doSomething() { // Line 2
        System.out.println("Doing something in Sub");
    }
}
```

## 答案

在这里，基类 `Base` 有一个被标记为 `public` 的 `doSomething` 方法。子类 `Sub` 重写了 `doSomething` 方法。然而，在子类的第 2 行中，它被标记为 `private`。因此，第 2 行导致了编译错误。这是因为你不能缩小被重写方法的可见性。为了修复该错误，你需要将第 2 行的 `doSomething` 方法标记为 `public`。

## 抽象类与接口

### 101. 声明接口的可能方式有哪些？

以下是声明接口的可能方式：

```java
interface Interface1 {
}

public interface Interface2 {
}

public abstract interface Interface3 {
}

abstract interface Interface4 {
}

abstract public interface Interface5 {
}
```

因此，接口可以有 `public` 访问修饰符也可以没有修饰符（这意味着它将具有默认访问权限）。它也可以包含 `abstract` 关键字。关键字的顺序不重要，可以以任何顺序指定。

### 102. 请用代码示例解释抽象类

抽象类是一个具有零或多个抽象方法的类。抽象方法是一个没有方法体的方法。抽象方法和类本身都需要指定 `abstract` 关键字。以下代码演示了一个抽象类：

```java
public abstract class Animal {
    private String name;

    public abstract void speak();

    public void printName() {
        System.out.println(name);
    }
}
```

在这里，`Animal` 是一个抽象类。它有一个名为 `speak` 的抽象方法。它还有一个名为 `printName` 的具体方法。

## 103. 请用代码示例说明如何实现接口

为了实现一个接口，你需要在类后面使用 `implements` 关键字。以下代码演示了这一点：

```java
public interface ShapeDrawer {
    void draw();
}

public class Triangle implements ShapeDrawer {
    @Override
    public void draw() {
        // 在此处实现
    }
}
```

## 104. 下面的代码有一个错误。请识别它并说明如何修复它

```java
public abstract class MyAbstractClass {
    public void doSomething() {
        System.out.println("Doing something");
    }

    public static void main(String args[]) {
        MyAbstractClass obj = new MyAbstractClass(); // Line 1
        obj.doSomething(); // Line 2
    }
}
```

## 答案

上面的代码无效，并在第 1 行导致编译错误。这段代码实例化抽象类。你不能创建抽象类的对象。

### 105. 类可以实现两个接口吗？如果两个接口同名会发生什么？

是的，类可以实现两个接口。即使两个接口同名，也不会导致歧义，因为实现是在类中提供的。以下代码演示了这一点：

```java
public interface Interface1 {
    void doSomething();
}

public interface Interface2 {
    void doSomething();
}

public class MyClass implements Interface1, Interface2 {
    @Override
    public void doSomething() {
        // 在此处实现
    }
}

MyClass obj = new MyClass();
obj.doSomething(); // Line 1
```

上面的代码指定了两个接口 `Interface1` 和 `Interface2`。这两个接口都有一个名为 `doSomething` 的方法。代码还指定了一个实现这两个接口的类 `MyClass`。它需要为 `doSomething` 提供实现。当执行第 1 行时，执行的是 `MyClass` 的 `doSomething()` 方法。

### 106. 抽象类的作用是什么？

在某些编程情况下，你可能想要创建一个被多个子类共享的父类。你可能想在父类中放置一些通用代码，但让具体的类提供特定的细节。抽象类在这类情况下非常有用。

因此，你可以创建一个抽象父类。你可以拥有实现通用功能的具体方法，以及针对子类特定功能的抽象方法。子类随后可以扩展抽象类并为抽象方法提供实现。

## 107. 请解释以下代码片段的问题所在

```java
public abstract final class MyAbstractClass {
    public void doSomething() {
    }
}
```

### 答案

上面的代码片段无效。这段代码声明了一个同时具有 `abstract` 和 `final` 关键字的类 `MyAbstractClass`。抽象类不能是 `final` 的，反之亦然。这是因为抽象类需要有一个子类来实现类中的抽象方法。

## 108. 下面的代码片段有效吗？请解释其原因

```java
public interface ShapeDrawer {
    public void draw();
}
```

```java
public class Triangle implements ShapeDrawer {
    public void draw() {
        // code to draw shape
    }

    public static void main(String args[]) {
        ShapeDrawer shapeDrawer = new Triangle(); // Line 1
        shapeDrawer.draw(); // Line 2
    }
}
```

### 答案

上述代码是有效的。这段代码声明了一个名为 `ShapeDrawer` 的接口和一个实现该接口的类 `Triangle`。

第 1 行声明了一个 `ShapeDrawer` 类型的变量，并为其赋值了一个 `Triangle` 类型的对象。这是有效的，因为可以将实现接口的类对象赋值给接口类型的变量。第 2 行调用了 `draw` 方法。这会执行 `Triangle` 类中 `draw` 方法的代码。

### 109. 下列代码中的哪些行会导致编译错误？

```java
public interface MyInterface {
    private static int FIELD1 = 7; // Line 1
    int FIELD2 = 8; // Line 2
    public final int FIELD3; // Line 3
    public static int FIELD4 = 8; // Line 4
}
```

### 答案

在上述代码中，第 1 行和第 3 行会导致编译错误。接口中声明的所有字段必须是 `public static final` 的。如果没有指定 `public`、`static` 和 `final` 关键字，该字段将被隐式地变为 `public static final`。

第 1 行显式指定了 `private` 关键字，因此导致编译错误。第 2 行没有指定 `public static final` 关键字。但这不会导致编译错误，Java 会隐式将该字段设置为 `public`、`static` 和 `final`。

第 3 行指定了 `public` 和 `final` 关键字，但没有初始化字段。`final` 字段需要初始化。因此，第 3 行也会导致编译错误。

第 4 行指定了 `public` 和 `static` 关键字并初始化了字段。它没有指定 `final` 关键字。但这同样不会导致编译错误，该字段被隐式地视为 `final`。

### 110. 下面代码段有效吗？解释原因

```java
public abstract class MyAbstractClass {
    private abstract void doSomething();
}
```

### 答案



上述代码是无效的，会导致`doSomething`方法编译错误。这是因为`doSomething()`方法既是`abstract`的又是`private`的。抽象方法不能被设置为`private`。`private`方法在子类中是不可访问的。抽象方法需要在子类中是可访问的，以便子类为该方法提供实现。子类无法为抽象私有方法提供实现。

# 第 10 章

## 包与访问控制

### 111. 什么是包（package）？包的优点是什么？

**Answer：**

包是相关 Java 类型的集合。因此，一个包可以包含相关的类、接口和枚举。使用包有以下几个优点：

- 包有助于将相关代码组织在一起。
- 包有助于避免命名冲突。因此，你可以在不同的包中拥有具有相同名的类或其他 Java 类型。
- 包还帮助控制访问。除非通过`public`关键字显式允许，否则包外部的代码无法访问包内部的代码。

### 112. 解释 Java 访问修饰符（access spec）。

**Answer：**

访问修饰符控制特定成员在何处是可访问的。它们只是指定在类成员上的某些关键字。它们可以指定实例字段，也可以指定方法。Java 有 4 种访问修饰符如下：

- a. Private（私有）：具有`private`访问修饰符的成员仅在声明它的类内部可访问。
- b. Protected（受保护）：具有`protected`访问修饰符的成员对包内所有类以及包外的子类可访问。
- c. Public（公共）：具有`public`访问修饰符的成员对所有类都可访问。
- d. Default（默认）：当未指定访问修饰符时发生默认访问。它仅对同一包内的类可访问。

### 113. 解释默认访问（default access）。

**Answer：**

默认访问在未指定访问修饰符时发生。它只对同一包内的类可访问。它通常被称为“包级私有”（package-private）。

### 114. 举出一些默认包。

**Answer：**

以下是一些默认包：

- `java.util`：包含`Collection`、`List`、`Set`、`Map`、`HashMap`、`Date`、`Calendar`。
- `java.io`：包含`InputStream`、`OutputStream`、`BufferedReader`、`BufferedWriter`。
- `java.awt`：包含`Component`、`Container`、`Frame`。
- `java.util.concurrent`：包含`Future`、`ExecutorService`。

### 115. 下列代码有效吗？解释原因。

```java
package demo;
public class Base {
    protected int a;
}

package demo2;
public class Sub extends Base {
    public void doSomething() {
        System.out.println("Value of a is "+a);
    }
}
```

**Answer：**

上述代码是有效的且不会导致任何错误。这段代码了父类`Base`和子类`Sub`。由于字段`a`是`protected`的，因此在子类中是可以访问的。

### 116. 解释`import`关键字。

**Answer：**

`import`关键字用于在代码中引入其他包。你可以导入标准 Java 包（如`util`）或用户定义的包。`import`关键字后面需要跟包名。为了从某个包中导入特定类，你需要指定类名。为了导入整个包，需要在包名后使用通配符（`*`）。示例下：

```java
import java.util.List; //导入 List 接口
import java.io.*; // 导入 java.io 包中的所有类
```

### 117. 解释`protected`访问修饰符和默认访问之间的区别。

**Answer：**

`protected`和默认访问之间存在若干差异，如下：

- `protected`访问修饰符通过`protected`关键字指定，而默认访问在未使用访问修饰符时发生。因此，默认访问没有独立的关键字。
- 当成员具有`protected`访问修饰符时，该成员对包内所有类以及包外的子类可访问。当成员具有默认修饰符时，该成员仅对包内的类可访问，包外不可访问。

### 118. 下面代码段有效吗？解释原因。

```java
package demo;
public class MyClass1 {
    int a; //Line 1
}

package demo2;
public class MyClass2 {
    public void doSomething() {
        MyClass1 obj = new MyClass1(); //Line 2
        obj.a = 5; //Line 3
    }
}
```

**Answer：**

上述代码是无效的，会在第 3 行导致编译错误。类`MyClass1`位于`demo`包中。它有一个字段`a`。由于没有显式包含访问修饰符，该字段具有默认访问权限。类`MyClass2`位于`demo2`包中。`doSomething()`方法在第 3 行访问了`MyClass1`的字段。默认访问字段在包外不可访问，因此第 3 行会导致编译错误。

### 119. 解释编译和执行以下代码时会发生什么：

```java
package com.questions;
```

```java
public class CoreJava {
    private String getQuestion() {
        return "Question1";
    }
}
package com.questions;
class JSP extends CoreJava {
    public void getJSPQuestion() {
        System.out.println(getQuestion());
    }
}
```

## 回答：

上述代码无法编译。`CoreJava`类定义了一个私有方法`getQuestion()`。子类中的`getJSPQuestion()`调用了父类的方法。由于私有方法无法被子类访问，会发生编译错误。

### 120. 解释`java.lang`包。

## 回答：

`java.lang`包包含了对 Java 编程语言非常重要的类。它包括`Byte`、`Boolean`、`Integer`、`Double`等包装类。它包含了`String`、`StringBuffer`和`StringBuilder`等类，用于字符串操作。它包含了`Thread`、`Runnable`等类，用于创建多线程应用程序。它包含了`Throwable`和其他`Exception`类，用于 Java 的异常处理功能。

# 第 11 章

## 异常处理

### 121. 解释 Java 中的`throw`、`throws`和`Throwable`。

## 回答：

`throws`关键字用于指定特定方法会抛出一个未处理的异常或多个需要单独处理的异常。基本上，它指定了你不想在方法内部处理该错误情况，而是想将异常处理委托给代码的其他部分。

`throw`关键字用在方法内部，用于显式地抛出一个异常。

`Throwable`是异常层次结构中的基类。可以通过扩展`Throwable`类来创建自定义异常。

### 122. 编译并执行以下代码时，输出是什么？

```java
class Test {
    try {
        System.out.println("This is try block");
    }
    System.out.println("Try block is executed"); //Line 1
    catch(Exception exp) {
        System.out.println("This is catch block");
    }
}
```

## 回答：

上述代码无法编译，并会抛出编译错误。这是因为第 1 行的代码写在`try`块结束之后、`catch`块之前。所有的代码都需要写在`try`块或`catch`块内部。Java 不允许`try`和`catch`块之间存在代码。

### 123. 编写一个演示`try/catch/finally`块的代码示例。

## 回答：

下面是一个演示`try/catch/finally`块的代码示例。

```java
try {
    System.out.println("This is try block");
} catch {
    System.out.println("This is catch block");
}
finally {
    System.out.println("This is finally block");
}
```

所有需要监控异常的代码都应该放在`try`块中。在紧随`try`块之后，你需要指定一个`catch`子句。在`catch`块中，你需要指定你想要捕获的异常类型以及当异常发生时你想要执行的代码。`finally`子句是可选的，它需要放在`try`块或`catch`块之后。无论是否发生异常，任何需要执行的代码都应该放在`finally`子句中。

### 124. 执行以下代码时，输出是什么？

```java
class ExceptionTest {
    public static void main(String argument[]) {
        callMethod();
    }
    static void callMethod() {
        int intValue = 100 / 0;
        System.out.println("intValue is: "+intValue);
    }
}
```

## 回答：

上述代码可以编译通过，没有任何错误。但在执行时，它会抛出一个`ArithmeticException`，并带有堆栈跟踪（错误信息或报告），如下所示：

> Exception in thread “main” java.lang.ArithmeticException: / by zero
>
> at ExceptionTest.callMethod(ExceptionTest.java:12)
>
> at ExceptionTest.main(ExceptionTest.java:9)

这是因为不允许将数字除以 0。

### 125. 解释 Java 中的`try–catch–finally`语句。

## 回答：

`Try–Catch–Finally`语句允许在 Java 中进行异常处理。你可以将想要监控错误的语句放在`try`块中。发生异常时需要执行的代码应该放在`catch`块中。你还需要指定你想要捕获的异常类型。你可以为不同类型的异常指定多个`catch`块。在`catch`块之后，你可以指定放入无论是否抛出异常都需要执行的代码。`catch`和`finally`块是可选的，但你至少需要其中一个。

下面的代码演示了`try–catch–finally`语句：

```java
try {
    // 监控异常的代码
}
catch (ExceptionType 1) {
    // 如果发生异常时遵循的指令
}
catch (ExceptionType 2) {
    // 如果发生异常时遵循的指令
}
catch (ExceptionType n) {
    // 如果发生异常时遵循的指令
}
finally {
    // 无论是否抛出异常，
    // 这一块都一定会被执行
}
```

### 126. 下述代码段的输出是什么？

```java
public class MyClass1 {
    public static void main(String args[]) {
        try {
            int no;
            no = 5 / 0; //Line 1
        } catch (ArithmeticException e) { //Line 2
            System.out.println("ArithmeticException");
        } catch (ArrayIndexOutOfBoundsException e) { //Line 3
            System.out.println("Array Out Bound");
        } catch (Exception e) { //Line 4
            System.out.println("Unhandled Exception");
        } finally { //Line 5
            System.out.println("I am done!");
        }
        System.out.println("Thank You!"); //Line 6
    }
}
```

## 回答：

此代码打印以下输出：

```text
ArithmeticException
I am done!
Thank You!
```

第 1 行导致了`ArithmeticException`。它被第 2 行的`ArithmeticException` catch 块捕获，该块打印了文本 ArithmeticException。由于`finally`块无论是否发生错误都会执行，控制权随后转移到第 5 行的`finally`块并打印`I am done`。接下来，控制转移到`finally`块外的第 6 行并打印`Thank You!!`

### 127. 假设你有一个名为`webWeb`的方法，其中包含可能会抛出检查异常（checked exception）的代码。你会在代码中处理这种情况？

## 回答：

如果方法抛出检查异常，有两种处理方式：

a. 在方法体中使用`try/catch`：

```java
public void myWeb() {
  try {
    // 代码在此
  } catch (CheckedException e) {
  }
}
```

在这里，当代码抛出检查异常时，它会被方法内部的`catch`块捕获。

b. 在方法声明中使用`throws`子句：

```java
public void myWeb() throws CheckedException {
  // 代码在此
}
```

在这里，当代码抛出检查异常时，它会通过`throws`子句抛到方法外部。因此，调用该方法的代码需要处理该异常。

### 128. “finally”子句的作用是什么？请举例。

## 回答：

无论是否发生异常，任何始终需要的代码都应该放在`finally`子句中。例如，关闭数据库连接、文件系统文件或其他资源的清理代码可以放在`finally`子句中。如果将此类代码放在`try`块中，一旦发生异常它可能就不会执行。因此，为了确保此类代码始终执行，需要将它们放在`finally`块中。

### 129. 解释 Error 和 Exception 区别。

## 回答：

`java.lang.Throwable`是所有异常类的父类。它有两个子类：`Exception`和`Error`。它们之间有若干区别：

- `Exception`代表由应用程序引起的程序错误，例如访问空值、除以 0、写入文件时的错误；`Error`代表发生在代码之外的运行时环境中的错误，例如内存不足等。
- `Exception`是应用程序可以处理并恢复的条件。而`Error`是应用程序无法恢复的严重问题的异常状态。
- `Exception`既包括检查异常（checked）也包括未检查异常（unchecked）。检查异常需要处理或在方法声明的`throws`子句中指定。而`Error`总是未检查的，且不需要在`throws`子句中声明。

### 130. 什么是`RuntimeException`？

## 回答：

`java.lang.RuntimeException`是`java.lang.Exception`类的子类。`RuntimeException`及其子类也被称为未检查异常。这是因为编译器不会强制你处理此类异常。因此，即使编写了可能抛出未检查异常的代码，编译器也不会产生错误。`RuntimeException`的一些示例包括`ArithmeticException`、`NullPointerException`和`ArrayIndexOutOfBoundsException`。

# 第 12 章

## 字符串处理

### 131. 什么是字符串字面量？请举例说明。

**回答：**

字符串字面量是一组封装在双引号中的字符。它可以通过赋值运算符（`=`）赋值给一个`String`变量。下行代码显示了将字符串字面量“I’m a literal”赋值给名为'name'的字符串变量。

```java
String name = “I’m a literal";
```

### 132. 下述代码的输出是什么？解释原因。

```java
class StringDemo {
    public static void main (String strArgs[]) {
        String strVar = "Welcome";
        strVar.concat(" to Java");
        System.out.println(strVar);
    }
}
```

**回答：**

此代码打印以下输出：

```text
Welcome
```

Java 字符串是不可变对象，除非显式赋值，否则字符串的值不会发生改变。`concat()`方法仅将"to Java"追加到`strVar`上，但没有将追加后的字符串赋值回变量`strVar`。



为了打印出 `"Welcome to Java"`，代码需要修改如下：

```java
strVar = strVar.concat(" Java");
```

## 133. 执行以下代码时的输出是什么？

```java
StringBuilder StringBuffer = new StringBuilder();
StringBuffer.append("Core ");
StringBuffer.append("Java");
System.out.println("The resultant StringBuilder Value is-" + StringBuffer);
```

### 回答

执行上述代码后，它将打印以下输出：

> The resultant StringBuilder Value is: Core Java

`StringBuilder.append()` 方法将指定的值追加到 `StringBuilder` 中的值末尾。

## 134. 下述代码片段的输出是什么？

```java
String xValue = "xyz";
String yValue = xValue.concat("qrs").toUpperCase().replace('Z', 'c');
System.out.println(yValue);
```

### 回答

上述代码打印以下输出：

```text
XYcQRS
```

首先，`xValue` 与值 `qrs` 拼接，因此值变为 `xyzqr`。然后，将该值转换为大写，因此值变为 `XYZQRS`。接着，将字符 `Z` 替换为 `c`，因此值变为 `YcQRS`（此处此处逻辑如此）。

## 135. 将字符串字面量赋值给 `String` 变量的各种方法有哪些？

### 回答

以下是将字符串字面量赋值给字符串变量的各种方法：

- a. `String strValue1 = "String Literal 1";`
- b. `String strValue2 = new String("String Literal 2");`
- c. `String strValue3 = new String(); strValue3 = "String Literal 3";`
- d. `String strValue4 = strValue3;`

方法 a 通过给变量赋值一个字符串字面量来创建了 `String` 变量 `strValue1`。方法 b 使用接受字符串值的 `String` 构造函数创建了变量 `strValue2`。方法 c 使用默认的 `String` 构造函数创建变量 `strValue3`，稍后对其赋值。方法 d 通过将另一个 `String` 变量赋值给它来创建了变量 `strValue4`。

## 136. 列举 `String` 类中的一些常用方法。

### 回答

以下是 `String` 类中的一些常用方法：

- a. `concat()`：用于向当前字符串追加一个值。
- b. `length()`：用于查找字符串的长度，即字符串中字符的总数。
- c. `replace()`：用于将字符串中的某个特定字符或多个字符替换为其他值。
- d. `substring()`：用于获取从指定位置开始的当前字符串的子字符串。
- f. `trim()`：用于移除字符串中的空白字符。
- f. `toUpperCase()`：用于将字符串中的所有字符转换为大写。
- g. `toLowerCase()`：用于将字符串中的所有字符转换为小写。
- h. `equals()`：用于将当前字符串与指定的字符串比较。它返回一个表示比较结果的布尔值。
- i. `equalsIgnoreCase()`：用于在忽略大小写的情况下比较当前字符串与指定的字符串。它返回一个表示比较结果的布尔值。

## 137. `StringBuffer` 和 `StringBuilder` 之间有什么区别？

### 回答

`StringBuffer` 和 `StringBuilder` 类都可以用于执行字符串操作。它们都是可变的，不像不可变的 `java.lang.String`。然而，`StringBuilder` 类不是线程安全的，即 `StringBuilder` 方法没有同步。这意味着，当你在应用程序中执行两个或多个线程时，不应使用 `StringBuilder`。此外，由于 `StringBuilder` 是异步的，它的性能比 `StringBuffer` 好。

## 138. 编写一个不使用循环的反转字符串的代码示例。

### 回答

有多种方法可以在不使用循环的情况下反转字符串。一种方法是使用 `StringBuilder` 类上的 `reverse` 方法。

```java
StringBuilder sb = new StringBuilder("Hello");
String reversed = sb.reverse().toString();
System.out.println(reversed);
```

## 139. 编写一个将字符串转换为大写的代码示例。

### 回答

```java
String str = "hello";
String upperStr = str.toUpperCase();
System.out.println(upperStr);
```

## 140. Java 中合并两个字符串的各种方法有哪些？

### 回答

Java 中有多种方法合并字符串：

- 使用 `+` 运算符。
- 使用 `concat()` 方法。
- 使用 `StringBuilder` 或 `StringBuffer`。

```java
// 使用 + 运算符
String s1 = "Hello " + "World";

// 使用 concat()
String s2 = "Hello".concat(" World");

// 使用 StringBuilder
StringBuilder sb = new StringBuilder();
sb.append("Hello ");
sb.append("World");
String s3 = sb.toString();
```

有边界泛型（Bounded Generic Types）有助于限制可以作为泛型参数的类型。以下代码演示了这一点：

```java
public class Shape {
}

public class Circle extends Shape {
}

public class ShapeDrawer<T extends Shape> {
    public void drawShape(T shape) {
        System.out.println("Drawing Shape.");
    }
}
```

这段代码声明了一个名为 `Shape` 的父类，它有一个名为 `Circle` 的子类。它还指定了一个名为 `ShapeDrawer` 的类，这是一个泛型类型。代码没有直接指定 `T`，而是指定了 `T extends Shape`。这意味着泛型类型 `T` 应该是 `Shape` 的子类。因此，如果调用 `drawShape` 方法时传入的参数不是 `Shape` 的子类，将会发生编译错误。

# 第 14 章

## 集合（Collections）

### 146. Java Collection API 中的四个主要接口是什么？

#### 答案

`java.util.Collection` 是 Java Collection API 中的顶层接口。它简单地表示一组作为一个单元操作的值集合。它有两个子接口 `Set` 和 `List`。两者都用于存储一组值；但它们在存储数据的方式上略有不同。

`List` 允许重复元素，即同一个元素可以出现多次。此外，`List` 是有序的，即列表中的元素按照它们被插入的顺序存储，并且这种顺序会被维护。

`Set` 不允许重复且是无序的，因此元素插入 `Set` 的顺序不会被维护。

还有另一个顶层接口称为 `Map`。`Map` 用于存储键值对（key-value pairs）。

### 147. 你如何在数组中搜索特定元素？

#### 答案

Java 提供了 `java.util.Arrays` 类作为集合框架的一部分。它包含几个实用方法。其中一个方法是 `Arrays.binarySearch` 方法，它可以用于在数组中搜索特定元素。它返回一个整数，如果被搜索的元素存在，则该整数指定该元素的位置（索引）；否则，如果不存在，它将返回 `-1`。以下代码演示了 `binarySearch()` 方法：

```java
String[] strArr = {"one", "two", "four"};
System.out.println("Search index of one is: " + Arrays.binarySearch(strArr, "one"));
```

这段代码输出以下内容：

```text
Search index of one is:0
```

由于字符串 `"one"` 位于位置 0，所以 `binarySearch()` 返回 0。

### 148. 如果你不想要重复且不在乎顺序，你会选择哪种集合？

#### 答案

如果你想避免重复且不在乎顺序，应该使用 `HashSet`。`HashSet` 是 `Set` 接口的一种实现。它是无排序且无序的。此外，`TreeSet` 和 `LinkedHashSet` 也是 `Set` 的实现。这两个实现都不允许重复。然而，`TreeSet` 维护排序，而 `LinkedHashSet` 维护插入顺序。

### 149. 请用代码示例说明如何移除队列头部。

#### 答案

`Queue` 接口有一个名为 `poll()` 的方法，用于移除队列头部。以下代码演示了这一点：

```java
Queue<Integer> lList = new LinkedList<Integer>();
lList.add(100);
lList.add(200);
System.out.println("Removed- " + lList.poll()); // Line 1
```

这段代码创建了一个队列并向其添加两个整数值。然后调用了 `poll()` 方法。因此，这段代码输出以下内容：

```text
The Element removed is: 100
```

因此，`poll()` 方法始终移除队列头部，即队列中添加的第一个元素。

### 150. 哪种集合实现允许增长或缩小大小，并对其元素提供索引访问？

#### 答案

`ArrayList` 是 `List` 接口的一种实现。它允许增长或缩小大小。它有 `add`/`remove` 方法来增加或减少 `List` 的大小。它还对其元素提供索引访问。它有一个 `get` 方法来实现这一点。以下代码演示了 `ArrayList`：

```java
List<Integer> myList = new ArrayList<Integer>();
myList.add(2);
myList.add(4);
myList.add(6);
myList.remove(1);
Integer num = myList.get(0);
```

### 151. 解释 `Queue` 接口。

#### 答案

`Queue` 接口是 Collection API 的一部分，扩展 `java.util.Collection`。`Queue` 接口是一种用于以先进先出（FIFO）方式持有元素的集合。元素在末尾添加并从头部移除。`Queue` 接口中的一些关键方法包括：

- `add(E e)`：将元素插入到队列末尾。
- `offer(E e)`：插入元素，如果队列已满则返回 `false`。
- `poll()`：移除并返回队列头部，如果队列为空则返回 `null`。
- `peek()`：获取但不移除队列头部，如果队列为空则返回 `null`。
- `isEmpty()`：如果队列不包含任何元素，则返回 `true`。
- `size()`：返回队列中元素的数量。

### 152. 解释 `Queue` 上的一些方法。

#### 答案

以下是 `Queue` 接口上的一些方法：

- `add(E e)`：将元素插入到队列末尾。
- `offer(E e)`：插入元素，如果队列已满则返回 `false`。
- `poll()`：移除并返回队列头部，如果队列为空则返回 `null`。
- `peek()`：获取但不移除队列头部，如果队列为空则返回 `null`。

### 153. 解释 `Comparator` 接口。

#### 答案

`Comparator` 是一个用于定义对象自定义排序的函数式接口。它允许在不修改类的情况下定义排序策略。主要方法是：

- `compare(T o1, T o2)`：比较对象的顺序。如果 `o1` 小于 `o2`，返回一个负整数；如果相等，返回 0；如果 `o1` 大于 `o2`，返回一个正整数。

### 154. 是否可以混合泛型和非泛集合？如果是，请给出示例。

#### 答案

是的，可以混合泛型和非泛集合。以下代码演示了这一点：

```java
public void insertDouble() {
    List<Double> myList = new ArrayList<Double>();
    myList.add(2.0); // Line 1
    myList.add(4.0); // Line 2

    insertSomethingElse(myList);
}

public void insertSomethingElse(List myList) {
    // Line 3
    myList.add("Hello World"); // Line 4
}
```

在上述代码中，Line 1 和 Line 2 将双精度数字字面量添加到列表中。代码随后调用 `insertSomethingElse` 方法传递该列表。在 Line 3 的方法声明中，`myList` 变量没有指定泛型类型。因此，可以向其添加任何类型的值。Line 4 向列表中添加了字符串字面量。

### 155. `Collection` 接口上有哪些重要方法？

#### 答案

以下是 `Collection` 接口的一些重要方法：

- `add(E e)`：允许将对象添加到集合中。
- `remove(Object o)`：允许从集合中移除对象。
- `contains(Object o)`：允许检查集合中是否存在对象。
- `size()`：返回集合的大小。
- `iterator()`：允许遍历集合。

# 第 15 章

## 枚举（Enumerations）、自动装箱（Autoboxing）和包装类（Wrapper Classes）

### 156. Java 中提供了哪些包装类？

#### 答案

包装类是与 Java 基本类型对应的类。它们有助于将基本类型转换为对象，反之亦然。这在你使用 Collections 时特别有用。由于 Collection 不接受基本类型值，你可以使用对应的包装类型。大多数包装类接受其基本类型或 String 作为参数。Java 支持以下包装类：

| 基本类型（Primitive Type） | 包装类型（Wrapper Type） |
|---|---|
| `byte` | `Byte` |
| `short` | `Short` |
| `int` | `Integer` |
| `long` | `Long` |
| `float` | `Float` |
| `double` | `Double` |
| `char` | `Character` |
| `boolean` | `Boolean` |

### 157. 以下代码的输出是什么？

```java
public class BooleanDemo {
    public static void main(String a[]) {
        // 使用 boolean 原始类型创建 Boolean
        boolean bool = true;

        Boolean booleanObj1 = new Boolean(bool); // line 1
        System.out.println("Wrapper class Boolean output:\n" + booleanObj1);

        Boolean booleanObj2 = new Boolean("false"); // line 2
        System.out.println("Wrapper class Boolean output:\n" + booleanObj2);

        System.out.println(booleanObj1.booleanValue());
    }
}
```

#### 答案

第 1 行创建了一个与 `bool` 变量对应的 boolean 类型 `booleanObj1`。第 2 行使用字符串值创建了 boolean 包装类 `booleanObj2`。Java 会自动将包装类型转换为原始类型。此外，在 `Boolean` 包装类上有一个名为 `booleanValue()` 的方法，它可以返回原始类型的布尔值。因此，这段代码将打印以下输出：

> Wrapper class Boolean output: true

```text
Wrapper class Boolean output: false

true
```

### 158. 解释如何将字符串 “100.55” 转换为 `Double`，以及将 `Double` 100.55 转换为字符串。

#### 答案

可以使用 `Double.parseDouble()` 方法将字符串转换为 `Double`，如下所示：

```java
Double doubleValue = Double.parseDouble("100.55");
```

可以使用 `Double.toString()` 方法将 `Double` 转换为字符串，如下：

```java
String stringValue = Double.toString(100.55);
```

### 159. 下面代码的输出是什么？

```java
Double doubleValue = Double.parseDouble("Java");
System.out.println(doubleValue);
```

#### 答案

上述代码可以正常编译。但在执行时，它会抛出 `NumberFormatException`。这是因为 JVM 无法将字符串 `Java` 转换为 `Double` 值。

### 160. 什么是 Java 中的包装类（Wrapper class）？包装类对象具有哪些特殊属性？



答案：

Java 是一门面向对象的语言。Java 中的原始数据类型不是对象。有时，你可能需要原始类型的等效对象。一个很好的例子是你想使用 Collections（集合）时。Collections 只能包含对象而不能包含原始类型。为了解决这个问题，Java 引入了包装类，将原始类型封装在对象中。每个原始类型都有一个对应的包装类，你可以创建该类型的对象。同样，你也可以将包装对象转换为原始类型。例如，对应原始类型 `int`，Java 有一个对应的 `java.lang.Integer` 包装类。

# 161. 举例说明什么是自动装箱（Autoboxing）

## 答案

自动装箱（也称为装箱 Boxing 或自动拆箱 Unboxing）是 Java 5 中引入的一项功能，它可以帮助程序员减少一些代码行。

例如，为了将原始值赋给包装类，你需要编写如下的包装代码：

```java
Integer integerValue = new Integer(1000); //封装
```

通过自动装箱，上述代码可以重写为：

```java
Integer integerValue = 1000;
```

同样，为了将包装类赋给原始类型，你需要编写如下的拆箱代码：

```java
Integer integerValue = 1000;
int iValue = integerValue.intValue(); //拆箱
```

通过自动装箱，上述代码可以重写为：

```java
Integer integerValue = 1000;
int iValue = integerValue;
```

# 第 16 章：线程

## 162. 如何在 Java 中创建线程？

### 答案

在 Java 中创建线程有两种方法：

1. 通过扩展 `Thread` 类：在这种方法中，你需要创建一个扩展内置 `Thread` 类的类，并重写 `run()` 方法。下面的代码演示了这一点：

```java
public class MyThread extends Thread {
    void run() {
        System.out.println("In Thread Body.");
    }
}
```

2. 实现名为 `Runnable` 的接口：在这种方法中，你需要创建一个实现内置 `Runnable` 接口的类。`Runnable` 接口有一个名为 `run()` 的单方法，你需要实现它。下面的代码演示了这一点：

```java
public class MyThread implements Runnable {
    void run() {
        System.out.println("In Thread Body.");
    }
}
```

## 163. 解释 Java 中不同线程类型

### 答案

线程有两种类型——用户定义线程（User defined Threads）和守护线程（Daemon threads）。

用户定义线程是由用户通过程序创建的线程。这些是高优先级线程。JVM 会等待这些线程执行完毕。

守护线程大多由 JVM 创建，尽管用户定义线程也可以被显式地设置为守护线程。守护线程通常用于后台进程，如垃圾回收（Garbage Collection）。一旦非守护线程停止运行，JVM 就会停止运行而不会等待守护线程停止。

## 164. 可以在不调用 `start()` 方法的情况下直接调用 `run()` 方法吗？

### 答案

可以直接调用 `run()` 方法而不是调用 `start()` 方法。然而，这不会产生一个新线程，`run()` 方法中的代码将在调用它的同一个线程中执行。`start()` 方法负责派生一个新线程。

## 165. 当执行以下代码时，后台发生了什么？

```java
class Test {
    public static void main(String argument[]) {
        System.out.println("Thread..");
    }
}
```

### 答案

当执行上述代码时，JVM 会创建一个线程来运行。

## 166. 解释 `Thread` 类中的一些方法

### 答案

- a. `start()`：启动线程。
- b. `run()`：需要在单独线程中执行的代码。
- c. `sleep()`：让运行的线程暂停一段时间。
- d. `setName()`：设置线程名称。
- e. `join()`：等待线程死亡。
- f. `isAlive()`：返回布尔值表示线程是否存活。
- g. `setPriority()`：更改线程优先级。

## 167. 解释线程状态

### 答案

线程存在五种状态：

- a. 新（New）：当创建一个新线程但没有调用 `start()` 方法时，线程处于新状态。
- b. 可运行（Runnable）：调用 `start()` 方法后但线程调度尚未开始执行它时，处于可运行状态。
- c. 运行（Running）：当线程调度开始执行线程时，它处于运行状态。`run()` 方法中的代码开始执行。
- d. 等待/阻塞（Waiting / Blocking）：如果线程存活但不具备运行，则处于阻塞状态。
- e. 死亡（Dead）：当线程完成执行时，进入死亡状态。

## 168. 写一个使用 `Thread` 类创建线程的代码示例

### 答案

下面的代码使用 `Thread` 类创建了线程：

```java
class MyThread extends Thread {
    public static void main(String argument[]) {
        MyThread thread = new MyThread();
        thread.start(); // line 1
    }

    public void run() {
        System.out.println("Inside Run Method."); // line 2
    }
}
```

## 169. 写一个使用 `Runnable` 接口创建线程的代码示例

### 答案

下面的代码通过实现 `Runnable` 接口创建了线程：

```java
class MyThread implements Runnable {
    public static void main(String argument[]) {
        MyThread myThread = new MyThread();
        Thread thread = new Thread(myThread); // line 1
        thread.start(); // line 2
    }

    public void run() {
        System.out.println("Inside Run Method.");
    }
}
```

## 170. Java 应用程序中可以创建多个线程吗？如果是，线程之间如何通信？

### 答案

是的，Java 应用程序中可以创建多个线程。为了两个线程之间的通信，需要使用对象类中的 `wait()`、`notify()` 和 `notifyAll()` 方法。

`wait()` 方法会导致当前线程暂停，直到其他某个线程在同一个对象上调用 `notify()`。

如果有多个对象正在等待某个特定对象，`notify()` 方法会导致其中任意一个线程恢复。

`notifyAll()` 方法会导致所有等待特定对象的线程都恢复。

## 171. 什么是同步（Synchronization）？

### 答案

当多个线程尝试同时访问共享资源时，需要某种方式确保资源在同一时间只有一个线程被访问。实现这一点的过程被称为同步。Java 提供了 `synchronized` 关键字来实现这一点。

## 172. 解释执行以下代码时发生了什么

```java
class TestMyRunnable implements Runnable {
  public void run() {
    System.out.println("Inside Run Method.");
    System.out.println("Name of thread is-":Thread.currentThread().getName());
  }
}

class TestMyThread {
  public static void main(String argument[]) {
    TestMyRunnable runnable = new TestMyRunnable();
    Thread thread = new Thread(runnable);
    Thread.setName("My Thread"); //Line 1
    thread.start(); //Line 2
  }
}
```

### 答案

该代码可以正常编译并显示以下输出：

```text
Inside Run Method.
Name of thread is: My Thread
```

当执行 Line 1 时，它将线程名称设置为 `My Thread`。因此，当执行 Line 2 时，它会创建一个新线程并执行 `run()` 方法中的代码，该代码会将线程名称打印为 `My Thread`。

## 173. 考虑以下代码

```java
class TestMyRunnable implements Runnable {
  public void run() {
    for (int iValue = 0; iValue < 1000; iValue++) {
      System.out.println("Name of thread is: "+Thread.currentThread().getName());
    }
  }

  public static void main(String argument[]) {
    TestMyRunnable runnable = new TestMyRunnable();
    Thread threadC = new Thread(runnable);
    Thread threadD = new Thread(runnable);
    threadC.setName("Thread 1");
    threadD.setName("Thread 2");
    threadC.start();
    threadD.start();
  }
}
```

执行此代码首先会打印 "Thread 1" 1000 次，然后打印 "Thread 2" 1000 次。如果这是错误的，请解释原因。

### 答案

执行上述代码时，它不会先打印 Thread 1 1000 次再打印 Thread 2 1000 次。线程执行的顺序取决于线程调度器。因此，尽管两个线程都打印了 1000 次它们的名称，但它们打印的顺序是不可知的。

## 174. 编写一个让线程暂停十分分钟的代码示例

### 答案

为了让线程暂停十分分钟，你需要在 `run()` 方法内部调用 `sleep()` 方法。`sleep()` 方法接受一个 `long` 类型的值作为参数，表示线程应该暂停的毫秒数。以下代码演示了这一点：

```java
try {
  Thread.sleep(10 * 60 * 1000);
} catch (InterruptedException exp) {
}
```

## 175. 调用同步方法时会发生什么？

### 答案

每当执行同步方法时，调用该方法的线程都会获取锁并在方法结束时持有该锁。只有当当前线程完成方法执行后，它才会释放锁。这样其他线程就可以获取锁并执行该方法。因此，`synchronized` 关键字防止了多个线程同时执行同步方法中的代码。

# 第 17 章：Java IO API

## 176. 执行以下代码会发生什么？

```java
File myFile = new File("CoreJava.txt");
```

### 答案

执行上述代码后，JVM 在内存中创建一个名为 `myFile` 的 Java 对象，但文件系统中不会创建实际的文件。要实际创建文件，需要调用 `myFile.createNewFile()` 方法。

## 177. 编写一个在 `/usr/test.txt` 路径创建文件的代码示例

### 答案

以下代码将在 `/usr/` 目录下创建一个名为 `test.txt` 的文件：

```java
try {
  File txtFile = new File("/usr/test.txt"); // Line 1
  txtFile.createNewFile(); // Line 2
} catch (IOException exp) {
}
```

在上述代码中，当执行 Line 1 时，内存中会创建一个对象 `txtFile`，当执行 Line 2 时，在 `/usr` 文件夹内会创建 `test.txt` 文件。

## 178. 用代码示例解释 `FileWriter` 类

### 答案

`FileWriter` 类用于将字符或字符串写入文件，而无需手动将它们转换为字节数组。

它们通常被封装在 `PrintWriter` 或 `BufferedWriter` 中，这些类提供了性能改进和更多的数据写入方法。以下代码演示了 `FileWriter`：

```java
try {
    File txtFile = new File("/usr/CoreJava.txt");
    FileWriter myFileWriter = new FileWriter(txtFile);
    myFileWriter.write("Line 1 \n Line 2 \n"); // Line 1
    myFileWriter.flush();
    myFileWriter.close();
} catch (IOException exp) {
}
```

## 179. 编写一个创建文件的代码段

### 答案

`FileWriter` 类用于将字符或字符串写入文件，而无需手动将它们转换为字节数组。

它们通常被封装在 `PrintWriter` 或 `BufferedWriter` 中，这些类提供了性能改进和更多的数据写入方法。以下代码演示了 `FileWriter`：

```java
try {
    File txtFile = new File("/usr/CoreJava.txt");
    FileWriter myFileWriter = new FileWriter(txtFile);
    myFileWriter.write("Line 1 \n Line 2 \n"); // Line 1
    myFileWriter.flush();
    myFileWriter.close();
} catch (IOException exp) {
}
```

在上述代码中，当执行 Line 1 时，内存中会创建一个对象 `txtFile`，当执行 Line 2 时，在 `/usr` 文件夹内会创建 `test.txt` 文件（注：此处原文描述为 `test.txt` 但代码中为 `CoreJava.txt`）。

## 180. 用代码示例解释 `FileWriter` 类

### 答案

`FileWriter` 类用于将字符或字符串写入文件，而无需手动将它们转换为字节数组。

它们通常被封装在 `PrintWriter` 或 `BufferedWriter` 中，这些类提供了性能改进和更多的数据写入方法。以下代码演示了 `FileWriter`：

```java
try {
    File txtFile = new File("/usr/CoreJava.txt");
    FileWriter myFileWriter = new FileWriter(txtFile);
    myFileWriter.write("Line 1 \n Line 2 \n"); // Line 1
    myFileWriter.flush();
    myFileWriter.close();
} catch (IOException exp) {
}
```

在上述代码中，当执行 Line 1 时，内存中会创建一个对象 `txtFile`，当执行 Line 2 时，在 `/usr` 文件夹内会创建 `test.txt` 文件。

## 181. 用代码示例解释 `FileWriter`

### 答案

`FileWriter` 类用于将字符或字符串写入文件，而无需手动将它们转换为字节数组。

它们通常被封装在 `PrintWriter` 或 `BufferedWriter` 中，这些类提供了性能改进和更多的数据写入方法。以下代码演示了 `FileWriter`：

```java
try {
    File txtFile = new File("/usr/CoreJava.txt");
    FileWriter myFileWriter = new FileWriter(txtFile);
    myFileWriter.write("Line 1 \n Line 2 \n"); // Line 1
    myFileWriter.flush();
    myFileWriter.close();
} catch (IOException exp) {
}
```

## 182. 编写一个演示 `PrintWriter` 的代码示例

### 答案

`FileWriter` 类用于将字符或字符串写入文件，而无需手动将它们转换为字节数组。

它们通常被封装在 `PrintWriter` 或 `BufferedWriter` 中，这些类提供了性能改进和更多的数据写入方法。以下代码演示了 `FileWriter`：



```java
try {
    File txtFile = new File("/usr/CoreJava.txt");
    FileWriter myFileWriter = new FileWriter(txtFile);
    myFileWriter.write("Line 1 \n Line 2 \n"); // Line 1
    myFileWriter.flush();
    myFileWriter.close();
} catch (IOException exp) {
}
```

`dir1.createNewFile();`

```java
File dir2 = new File("/usr/dir2");
```

`dir1.renameTo(dir2); //第 1 行`

这段代码将目录`dir1`重命名为`dir2`。

## 185. 哪些类被用于对象的序列化和反序列化？

### 答案

序列化是将对象写入文件系统的过程。`java.io.ObjectOutputStream`可用于序列化对象。它有一个`writeObject()`方法可以实现这一功能。反序列化是恢复已序列化对象的过程。`java.io.ObjectInputStream`可用于序列化对象（反序列化）。它有一个`readObject()`方法可以实现这一功能。

## 186. 解释`File`类中的一些重要方法

### 答案

`File`类封装了文件系统上的文件或目录。`File`类的一些方法如下：

- a. `createNewFile()`：创建一个新的空文件。
- b. `list()`：返回当前目录下的文件/目录数组。
- c. `delete()`：从文件系统删除该文件。
- d. `mkdir()`：创建目录。
- e. `getAbsolutePath()`：返回文件的绝对路径。

# 第 18 章：杂项

## 187. 解释当编译以下代码段时会发生什么

```java
public class Test {
    public static void main(String argument[]) {
        int iValue;
        System.out.println(iValue);
    }
}
```

### 答案

这段代码会导致编译错误。这是因为变量`iValue`未初始化但在`Sysout`语句中被使用了。可以通过在使用之前初始化变量`iValue`来修复错误，如下所示：

```java
int iValue = 0;
System.out.println(iValue);
```

## 188. 解释当编译并执行以下代码时会发生什么

```java
class Calculate {
    float fValue = 10.2f;
    public static void main(String argument[]) {
        System.out.println("Float value is: "+fValue);
    }
}
}
```

### 答案

上述代码会导致编译错误，因为`main`方法尝试访问非静态实例变量`fvalue`。Java 不允许从非静态方法访问静态变量。

## 189. 解释对称的`equals()`合约

### 答案

假设有两个对象`v1`和`v2`。如果`v1.equals(v2)`返回`true`，那么`v2.equals(v1)`必须返回`true`。这种`equals()`合约被称为对称合约。考虑以下代码：

```java
Object v1; Object v2;
v1.equals(v2); //第 1 行
v2.equals(v1); //第 2 行
```

因此，在对称合约的情况下，第 1 行返回`true`且仅当第 2 行返回`true`时才返回`true`。

## 190. 下列哪些语句是无效的？为什么？

```java
System.out.println(2+2); //第 1 行
int i= 2+'2'; //第 2 行
String s= "one'+two'; //第 3 行
byte b=256; //第 4 行
```

### 答案

第 1 行和第 2 行是有效语句。

第 3 行是无效的。值`two`是无效的，因为单引号不能用于`String`，它们只能用于字符常量。`String`需要用双引号包围。

第 4 行是无效的。`byte`变量`b`不能赋值为 256，因为超出了`byte`的范围。

## 191. `transient`关键字的作用是什么？

### 答案

`transient`关键字可以指定在实例变量上。为实例变量指定`transient`表示在对象被序列化时，不应保存其状态。考虑以下代码段：

```java
class Electronics implements Serializable {
  transient int price; //第 1 行
  private int quantity; //第 2 行
}
```

当`Electronics`类的实例被序列化时，`price`字段将不会被序列化，只有`quantity`字段会被序列化。

## 192. 什么是 Java 中的垃圾回收？

### 答案

垃圾回收是释放分配给不再使用的对象的内存的过程。在运行期间，当创建一个对象时，JVM 会为该对象分配一些内存。JVM 定期检查正在使用的对象，并为那些不再使用的对象释放内存。垃圾回收就是这种移除不再使用的对象的过程。因此，程序员不需要担心手动释放内存。

## 193. 垃圾回收使用了内存的哪个部分？JVM 使用什么算法进行垃圾回收？

### 答案

垃圾回收是在堆内存（heap memory）中进行的。JVM 内部使用标记-清除（mark and sweep）算法进行垃圾回收。

## 194. 垃圾回收何时发生？

### 答案

JVM（Java 虚拟机）控制垃圾回收过程。因此，JVM 决定何时运行垃圾回收过程。

也可以通过 Java 代码，通过`System.gc()`或`Runtime.getRuntime().gc()`方法显式请求垃圾回收。然而，不能保证调用这些方法一定会运行垃圾回收器。

## 195. 需要编写什么代码来触发垃圾回收？

### 答案

可以通过以下方式触发垃圾回收。

**方法 1**：如下所示使用`Runtime.gc()`：

```java
Runtime runTime = Runtime.getRuntime();
runTime.gc();
```

**方法 2**：如下所示使用`System.gc()`：

```java
System.gc();
```

这两种方法都不保证运行垃圾回收器，由 JVM 决定。

## 196. 如何通过代码示例解释对象何时变为垃圾回收？

### 答案

当对象不再被引用时，就会变为垃圾回收。以下场景演示了这一点。

### 场景 1：将对象设置为`null`

```java
String stringValue = "This is a String"; //第 1 行
stringValue = null; //使 stringValue 可被回收
```

### 场景 2：重新赋值变量

```java
String str1 = "Hello";
str1 = "World"; //原来的对象 Hello 可被回收
```

### 场景 3：方法内部创建的对象

```java
public void doSomething(){
    String str1 = "Hello";
}
```

# 第二部分：核心 Java 8

## 第一章：函数式接口

## 197. 什么是函数式接口？如何创建函数式接口？

### 答案

函数式接口只有一个抽象方法的接口。要创建函数式接口，你只需要创建一个只有一个抽象方法的接口，如下：

```java
@FunctionalInterface
public interface Multiplier {
    public int multiply(int a, int b);
}
```

这段代码定义了一个名为`Multiplier`的接口。它只有一个`multiply`方法。它指定了`@FunctionalInterface`注解。该注解是可选的，它标记该接口为函数式接口。因此，如果你尝试向接口添加另一个抽象方法，代码会导致编译错误。

## 198. 解释`java.util.function`包

### 答案

`java.util.function`是 Java 8 添加的新包。它包含许多内置的函数式接口。包中的一些接口如下：

- a. `Predicate`：用于测试条件。它返回一个布尔值，表示条件是否为真。它接受任意类型的参数。
- b. `Consumer`：用于操作一个值。它接受任意类型的参数并对其进行操作。它返回`void`。
- c. `Function`：用于转换输入值。它接受任意类型的参数，对其进行转换并返回结果。
- d. `Supplier`：用于产生一个值。它不接受任何参数，但产生一个任意类型的结果。

## 199. 用代码示例解释`java.util.function.Consumer`接口

### 答案

`java.util.function`是 Java 8 添加的包。它有一个名为`accept()`的方法，该方法接受任意类型的参数并对其进行操作。它不返回任何结果。该方法需要通过 lambda 表达式来实现。以下代码演示了这一点：

```java
Consumer<String> printStr = val -> System.out.println(val); //第 1 行
printStr.accept("Hello World"); //第 2 行
```

第 1 行创建了一个`String`类型的`printStr`。它通过 lambda 表达式实现了`accept`方法，只需打印传入的字符串。第 2 行使用值 "Hello World" 调用了`accept`方法。因此，这段代码会打印以下输出：

## 200. 解释`Supplier`和`Consumer`接口之间的差异

### 答案

`Supplier`和`Consumer`接口都是`java.util.function`包中的内置函数式接口。它们之间有以下几区别：

- `Supplier`接口不接受参数，而`Consumer`接口接受任何数据类型的任何参数。
- `Supplier`接口产生任何数据类型的返回值，而`Consumer`接口不返回任何值。
- `Supplier`接口基本上产生一个特定数据类型的值，而`Consumer`接口则对输入值进行操作。

## 201. 下述代码段的输出是什么？

```java
Predicate<Integer> numberChecker = (num) -> num > 20;
int input = 10;
System.out.println(input+" greater than 20-"+numberChecker.test(input)); //Line 1
input = 40;
System.out.println(input+" greater than 20-"+numberChecker.test(input)); //Line 2
```

### 答案

上述代码段使用了一个名为`Predicate`的内置函数式接口。该接口接受任何数据类型的参数并返回一个布尔值。因此，它基本上被用于测试某个条件。在这里，代码创建了一个名为`numberChecker`的`Predicate`，它接受一个整数值。它通过 lambda 表达式实现，检查输入数字是否大于 20。第 1 行将`Predicate`应用于值 10，而第 2 行将`Predicate`应用于值 40。因此，代码打印出以下输出：

```text
10 greater than 20:false
40 greater than 20:true
```

## 202. 你会使用哪种内置函数式接口将字符串转换为大写字母？

### 答案

有一个名为`UnaryOperator`的内置函数式接口。它接受任何数据类型的参数并返回相同数据类型的结果。它有一个名为`apply`的方法，该方法可以对输入值进行操作。因此，你可以使用它将字符串转换为大写字母。以下代码演示了这一点：

```java
UnaryOperator<String> converter = str -> str.toUpperCase();
System.out.println(converter.apply("hello world"));
```

在这里，代码创建了一个名为`converter`的`UnaryOperator`实现，它对字符串值进行操作。使用了 lambda 表达式将字符串转换为大写。因此，此代码打印出以下输出：

```text
HELLO WORLD
```

## 203. 下述代码有效吗？请解释。

```java
@FunctionalInterface
public interface Interface1 {
    public void doSomething();
}
public interface Interface2 extends Interface1 {
    public void doSomethingElse();
}
```

### 答案

上述代码声明了一个名为`Interface1`的函数式接口，包含一个名为`doSomething`的抽象方法。然后定义了另一个名为`Interface2`的函数式接口，它扩展了`Interface1`并有一个名为`doSomethingElse`的抽象方法。这段代码完全有效。`Interface2`现在有两个抽象方法：`doSomething()`和`doSomethingElse()`。由于它没有标记`@FunctionalInterface`注解，因此拥有多个抽象方法是可以的。如果在`Interface2`上使用了`@FunctionalInterface`注解，代码将会导致编译错误。

## 204. 请列出一些 Java 8 之前但被 Java 8 变为函数式接口的接口

### 答案

在 Java 8 之前，有一些接口已经拥有单个抽象方法。Java 8 通过在这些接口上指定`@FunctionalInterface`注解，将它们指定为函数式接口。因此，这些接口中的抽象方法可以通过 lambda 表达式来实现。这些接口如下：

- a. `java.lang.Runnable`：用于创建线程。
- b. `java.util.concurrent.Callable`：用于创建返回值的线程。
- c. `java.util.Comparator`：用于比较值。
- d. `java.io.FileFilter`：用于过滤文件。

## 205. 为什么 Java 8 增加了像`IntSupplier`、`BooleanSupplier`等内置函数式接口的原始类型特化版本？

### 答案

Java 增加像`IntSupplier`、`BooleanSupplier`等内置函数式接口的原始类型特化版本是为了提高性能。原始类型特化版本消除了自动装箱（autoboxing）的需求，从而提高了性能。

以下代码演示了这一点：

```java
Supplier<Integer> integerSupplier = () -> new Random().nextInt();
```

这段代码创建了一个返回小于 100 的随机整数的`Supplier`。由于没有使用原始类型特化，`Random`类返回的值需要被包装成`Integer`。

现在考虑以下代码：

```java
IntSupplier integerSupplier2 = () -> new Random().nextInt();
```

在这种情况下，使用了返回整数的`Supplier`的原始类型特化版本`IntSupplier`。因此，没有需要将返回值包装成`Integer`。由于避免了自动装箱，这段代码产生了更好的性能。

## 206. 内置函数式接口通常在哪里使用？

### 答案

Java 8 增加了 Stream API，帮助对集合（Collections）进行批量操作。内置函数式接口通常用作 Stream API 方法的参数。Stream 方法将函数式接口指定的操作应用到 Stream 中的每个元素。例如，`Stream`接口有一个`filter`方法，可以根据某些条件过滤集合。该条件是通过`Predicate`接口（一种内置函数式接口）指定的。它检查输入 Stream 中的每个值是否匹配条件；而`map`方法则对 Stream 中的元素进行转换。

# 第 02 章：Lambda 表达式

## 207. 什么是 lambda 表达式？使用 lambda 表达式有什么好处？

### 答案

Lambda 表达式用于指定一个没有名字的函数。它用于实现函数式接口。Lambda 表达式有以下优点：

- 它们使代码更简洁。在 Java 8 之前，开发者需要编写大量代码来实现接口。Lambda 表达式消除了与实现接口相关的模板代码。
- 它们允许将代码作为方法参数传递。
- 它们允许为同一个方法提供不同的实现。
- Java 8 添加的其他新特性（如 Streams）也使用了 lambda 表达式。

## 208. Lambda 表达式和函数式接口之间是什么关系？

### 答案

函数式接口是一个只有一个抽象方法的接口。Lambda 表达式用于实现函数式接口中的抽象方法。

Java 8 添加函数式接口是为了支持 lambda 表达式并为 Java 提供函数式编程支持。由于 Java 是一种面向对象的语言，lambda 表达式无法独立存在。它们需要与对象关联。因此，Java 8 引入了函数式接口，并强制 lambda 表达式只能与函数式接口配合。通过让 lambda 表达式实现函数式接口，lambda 表达式就成了函数式接口的实现。函数式接口和 lambda 表达式有助于编写清晰简洁的代码。

## 209. 请解释 lambda 表达式的语法

### 答案

以下是 lambda 表达式的语法：

```text
(parameters) -> {lambda body}
```



因此，lambda 表达式由参数、lambda 运算符（`->`）和表达式体组成。lambda 表达式可以接收零或多个参数。如果不接受任何参数，则需要使用空括号。如果接受单个参数，参数不需要放在括号中。如果接受多个参数，它们需要放在括号内并用逗号隔开。lambda 体是普通的 Java 代码，可以包含任意数量的语句。如果 lambda 体中只有一个语句，可以省略主体的大括号；否则必须指定大括号。

## 210. 请给出一些 lambda 表达式的示例

答案：

以下是 lambda 表达式的一些示例：

### 示例 1：单参数，无返回值

```java
str -> System.out.println(str);
```

此 lambda 表达式接受一个参数，并使用 `System.out.println()` 语句打印它。它不返回任何值。

### 示例 2：多参数和返回值

```java
(num1, num2) -> num1 + num2;
```

此 lambda 表达式接受两个参数并返回它们相加的结果。这里没有显式地指定 `return` 关键字。

### 示例 3：无参数，lambda 体和返回值

```java
() -> {
    // 在这里执行某些操作
    return 0;
}
```

此 lambda 表达式不接受任何参数。它有一个执行某些代码的体，并返回值 `0`。

## 211. 编写代码示例创建一个函数式接口（Functional interface）并使用 Lambda 表达式实现它

答案：

函数式接口是只有一个抽象方法的接口。考虑以下函数式接口：

```java
@FunctionalInterface
public interface StringConverter {
    public String convert(String s);
}
```

此代码定义了一个名为 `StringConverter` 的函数式接口，包含一个名为 `convert` 的方法。`convert` 方法接受一个 `String` 值并返回一个 `String`。

Lambda 表达式为函数式接口中的方法提供了实现。

因此，你可以像下面这样使用 lambda 表达式实现 `StringConverter` 接口：

```java
StringConverter converter = (str) -> str.toUpperCase();
```

在这里，`StringConverter` 是通过 lambda 表达式实现的，该表达式将输入的 `String` 转换为大写并返回。

## 212. 用代码示例说明如何使用不同的 lambda 表达式实现同一个函数式接口

答案：

考虑以下 `StringConverter` 函数式接口：

```java
@FunctionalInterface
public interface StringConverter {
    public String convert(String s);
}
```

现在可以通过不同的 lambda 表达式为 `convert` 方法提供不同的实现：

```java
StringConverter uppercaseConverter = str -> str.toUpperCase();
String result = uppercaseConverter.convert("Hello");
```

在这里，`StringConverter` 接口通过 lambda 表达式实现，该表达式将输入的 `String` 转换为大写并返回。

现在考虑以下代码：

```java
StringConverter lowercaseConverter = str -> str.toLowerCase();
String result = lowercaseConverter.convert("Hello");
```

在这里，`StringConverter` 接口通过 lambda 表达式实现，该表达式将输入的 `String` 转换为小写并返回。

因此，不同的 lambda 表达式为 `StringConverter` 接口提供了不同的实现。

## 213. 识别以下 lambda 表达式中的错误以及如何修复它

```java
(str) -> return str.toUpperCase();
```

答案：

上面的 lambda 表达式在 lambda 体中使用了 `return` 关键字。如果使用了 `return` 关键字，lambda 体需要包含在大括号 `{}` 中。或者，也可以移除 `return` 关键字以消除错误。

因此，上面的 lambda 表达式可以通过以下两种方式之一修复：

```java
(str) -> { return str.toUpperCase(); }
```

或者：

```java
(str) -> str.toUpperCase();
```

## 214. 以下代码有效吗？解释

```java
public void generateSquareRoot(int num) {
    Function<Integer, Double> squareRoot = (num) -> sqrt(num);
}
```

答案：

上面的代码定义了一个名为 `squareRoot` 的 `Function` 变量。它接受 `num` 参数并返回 `sqrt(num)`。此代码是有效的。

## 215. 使用 lambda 表达式编写一个函数式接口并实现它

```java
@FunctionalInterface
public interface InterfaceL {
    void doSomething(String input);
}
```

答案：

你可以使用 lambda 表达式实现 `InterfaceL` 接口：

```java
InterfaceL interfaceL = (input) -> {
    System.out.println(input);
};
```

### 216. 用代码示例说明如何使用 lambda 表达式创建一个新的 Stream

答案：

除了顺序式流外，Stream API 还支持并行流。并行流对 `Stream` 中的元素进行并发操作，从而提供性能提升。`parallelStream()` 方法已添加到 `Collection` 接口中。它可以获取与底层集合对应的并行流。

以下代码演示了这一点：

```java
List<String> colours = Arrays.asList("Red", "Green", "Blue");
Stream<String> parallelStream = colours.parallelStream();
```

此代码首先创建一个名为 `colours` 的 `String` 值列表。然后它调用 `colours` 列表的 `parallelStream()` 方法。这返回一个与该列表对应的并行流。

### 217. 解释创建 Stream 的不同方式

答案：

有多种方式可以创建 Stream，如下：

- a. 从列表创建 Stream：

```java
Stream<String> values = Stream.of("Red", "Blue");
```

- b. 从集合创建 Stream：

```java
List<Integer> numbers = Arrays.asList(1, 2, 3);
Stream<Integer> stream = numbers.stream();
```

- c. 从数组创建 Stream：

```java
int[] numbers = new int[]{1, 2, 3, 4};
IntStream stream = Arrays.stream(numbers);
```

### 218. 解释 Stream filter 操作

答案：

`Stream.filter()` 操作可以根据条件过滤 Stream。它接受一个 `Predicate` 实例并过滤流中的元素。以下代码演示了这一点：

```java
Stream<Integer> numbers = Stream.of(7, 3, 9, 6, 1);
Stream<Integer> output = numbers.filter(num -> num > 5);
```

此代码创建一个 `Stream`。它通过 lambda 表达式调用 `filter()` 方法，检查输入是否大于 `5`。因此，`output` Stream 将包含大于 `5` 的数字。

### 219. 解释 Stream 操作类型

答案：

Stream 操作分为：

- a. 中间操作：中间操作处理 Stream 并产生 Stream。由于中间操作产生 Stream，因此可以链式调用执行一系列操作。中间操作的示例有 `filter`、`map`、`sorted`。

- b. 终端操作：终端操作处理 Stream 但产生非 Stream 结果。因此，不能链式调用。当链接多个 Stream 操作时，终端操作通常是最后一个。终端操作的示例有 `count`、`anyMatch`、`allMatch`、`collect`。

## 220. 什么是并行流（parallel stream）？用代码示例说明如何创建一个并行流

答案：

除了顺序式流外，Stream API 还支持并行流。并行流对 Stream 中的元素进行并发操作，从而提供性能提升。`parallelStream()` 方法已添加到 `Collection` 接口中。它可以获取与底层集合对应的并行流。以下代码演示了这一点：

```java
List<String> colours = Arrays.asList("Red", "Green", "Blue");
Stream<String> parallelStream = colours.parallelStream();
```

此代码首先创建一个名为 `colours` 的 `String` 值列表。然后它调用 `colours` 列表的 `parallelStream()` 方法。这返回一个与该列表对应的并行流。

## 221. 如何将 Stream 转换为集合？

答案：

Stream 接口有一个名为 `collect()` 的方法。它可以用于将 Stream 转换为集合。以下代码演示了这一点：

```java
Stream<Integer> numbers = Stream.of(7, 3, 9, 6, 1);
List<Integer> filteredList =
    numbers.filter(num -> num > 5).collect(Collectors.toList());
```

该方法接受一个 `Collector` 作为参数。调用了 `Collectors.toList()` 方法，它返回一个将输入 Stream 转换为 List 的 `Collector`。因此，`filteredList` 是一个只包含输入 List 中大于 `5` 的数字的 List。`Collectors` 类中还有其他方法，如 `Collectors.toSet`、`Collectors.toMap`、`Collectors.toCollection`，它们可以将 Stream 转换为其他类型的 Collection。

### 222. 下面代码段的输出是什么？

```java
Stream<Integer> numbers = Stream.of(10, 15, 20, 25);
boolean anyMatch = numbers.anyMatch(num -> num % 2 == 0);
System.out.println(anyMatch);
```

### 答案

上面的代码段在 Stream 接口上使用了 `anyMatch()` 方法。如果输入 Stream 中的任何元素符合指定条件，该方法将返回 `true`。在这种情况下，它检查输入 Stream 中是否存在偶数。由于 Stream 中存在偶数，`anyMatch()` 方法返回 `true`。因此，此代码打印出以下输出：

```text
true
```

### 223. Stream 和 Collection 之间有什么区别？

### 答案

Stream 和 Collection 之间有几点区别如下：

- Collection 实际上存储数据，而 Stream 不存储任何数据，它只是在底层数据上执行某些操作。
- 当你对 Collection 执行操作时，Collection 会被修改。当你对从 Collection 获取的 Stream 执行操作时，底层 Collection 不会被修改。
- Collection 在创建后可以被修改，而 Stream 在构造后无法被修改。
- 你可以多次遍历 Collection。然而，你只能遍历一次 Stream。如果你想再次遍历 Stream，是不可能的；你需要从底层源创建一个新的 Stream 并再次遍历它。

## 224. 假设你有一个包含 String 值的 List。你想创建一个新 List，其中消除原始 List 中的重复项，并将 String 值转换为大写。你将如何通过 Stream 操作实现这一点？

### 答案

下面的代码段演示了上述需求：

```java
List<String> fruits =
    Arrays.asList("Apple", "Mango", "Banana", "Apple",
                  "Orange", "Mango", "Strawberry"); // 第 1 行

List<String> uniqueFruits =
    fruits.stream()
          .distinct()
          .map(str -> str.toUpperCase())
          .collect(Collectors.toList()); // 第 2 行

uniqueFruits.forEach(str -> System.out.println(str)); // 第 3 行
```

此代码首先在第 1 行创建一个名为 `fruits` 的 String 值 List。第 2 行调用 `fruits.stream()` 获取一个关于 `fruits` List 的 Stream。然后它调用 `distinct()` 操作。`distinct()` 方法返回一个仅包含输入 Stream 中唯一元素的新 Stream。

接下来，它调用 `map()` 操作。`map()` 操作可用于转换 Stream。它接受一个 `Function` 实例作为参数，并将该 `Function` 应用于 Stream 中的每个元素。这里，使用 lambda 表达式将 Stream 中的每个 String 转换为大写。

最后，它调用 `collect()` 方法，并传入一个将 Stream 转换为 List 的 `Collector`。第 3 行打印 `uniqueFruits` List 中的所有元素。因此，此代码打印出以下输出：

```text
APPLE
MANGO
BANANA
ORANGE
STRAWBERRY
```

## 225. 是否可以将数组转换为 Stream？请解释

### 答案

是的，可以将数组转换为 Stream。Java 8 在 `java.util.Arrays` 类中增加了 `stream()` 方法。它有许多重载版本，接受不同数据类型的数组并将其转换为 Stream。下面的代码演示了将 Integer 数组转换为 Stream：

```java
int[] numbers = {10, 20, 30};
IntStream numberStream = Arrays.stream(numbers);
```

此代码首先创建一个名为 `numbers` 的 int 数组。然后使用 `Arrays.stream()` 方法并传入输入数组。`Arrays.stream()` 方法返回一个 `IntStream`，它是 `Stream` 接口的一个原始类型特化版本。就像 `IntStream` 一样，Java 8 还添加了 `DoubleStream` 和 `LongStream`，当分别使用 `Arrays.stream()` 方法处理 double 或 long 数组时会返回这些流。

### 226. 假设你有如下所示 Employee 类

```java
public class Employee {
    private String name;
    private int salary;
}
```

并假设你有一个如下的 Employee 对象 List：

```java
List<Employee> employees = new ArrayList<Employee>();
employees.add(new Employee("John", 10000));
employees.add(new Employee("Ana", 15000));
employees.add(new Employee("Tia", 8000));
```

你如何使用 Stream 创建一个根据 Employee 薪资排序的新 List？

### 答案

可以使用以下代码创建一个根据 Employee 薪资排序的新 List：

```java
List<Employee> sortedList =
    employees.stream()
             .sorted((emp1, emp2) -> emp1.getSalary() - emp2.getSalary())
             .collect(Collectors.toList());

sortedList.forEach(emp -> System.out.println(emp.getSalary()));
```

此代码首先获取 `employees` List 的 Stream。它调用了 `sorted()` 操作。`sorted()` 方法接受一个 `Comparator` 作为输入。这里，使用 lambda 表达式来比较薪资。最后，此代码打印出以下输出：

```text
8000
10000
15000
```

### 227. 什么是方法引用？方法引用的用处是什么？

### 答案

方法引用是调用现有方法的 lambda 表达式快捷方式。它是在 Java 8 中引入的。

方法引用的用处如下：



- a. **避免代码重复**：有时，你的代码已经有了你想在 lambda 表达式中指定的方法。与其再次编写代码，你可以引用它。
- b. **代码简洁**：方法引用可以使代码更具可读性。

### 228. 方法引用的不同类型有哪些？

#### 答案

方法引用有四种：

- a. **静态方法引用**：通过方法引用访问静态方法。语法为：

```
class::staticmethod
```

- b. **实例方法引用**：通过方法引用引用类的实例方法。语法为：

```
object::instancethod
```

- c. **构造器引用**：通过方法引用引用类的构造函数。语法为：

```
class::new
```

- d. **任意方法引用**：访问没有对象的类实例方法。语法为：

```
class::instancethod
```

### 229. 给出一个静态方法引用的示例。

#### 答案

静态方法引用是指通过方法引用访问类的静态方法。下面的代码演示了这一点：

```java
public class MethodReferenceDemo {
    public static boolean checkIfGreaterThan8(int num) {
        return num > 8;
    }

    public static void main(String[] args) {
        Predicate<Integer> numberChecker = MethodReferenceDemo::checkIfGreaterThan8;
        boolean flag = numberChecker.test(10);
    }
}
```

在这里，`MethodReferenceDemo` 类有一个静态方法 `checkIfGreaterThan8()`。它检查数字是否大于 8 并返回一个布尔值。在 `main` 方法中，定义了一个 `Predicate`。然而，并没有使用 lambda 表达式来实现 `Predicate`，而是通过方法引用引用了现有的 `checkIfGreaterThan8()`。由于 `checkIfGreaterThan8()` 是静态方法，使用了类名加方法名。

### 230. 考虑下面的 `Shape` 类

```java
public class Shape {
    private String name;
}
```

为了下面的代码有效，该类需要哪些更改？

```java
List<String> shapeNames =
Arrays.asList("Circle", "Triangle");
List<Shape> shapes =
shapeNames.stream().map(Shape::new).collect(Collectors.toList());
```

#### 答案

上面的代码创建了一个名为 `shapeNames` 的 String 值 List。然后它使用 Stream 的 `map()` 操作创建 `Shape` 对象。为了使之有效，我们必须在 `Shape` 类中添加一个接受 String 作为参数的构造函数。

```java
public class Shape {
    private String name;

    public Shape(String name) {
        this.name = name;
    }
}
```

一个名为 `shapes` 的 Shape 对象列表。该代码使用构造器引用来使用 String 名称创建一个新的 Shape 对象。因此，Shape 类需要一个接受 String 值作为输入的构造函数，如下所示：

```java
public Shape(String name) {
    this.name = name;
}
```

### 231. 解释 `String::toUpperCase` 是什么类型的类型的方法引用。

#### 答案

`String::toUpperCase` 是**任意方法引用**的示例。它引用 String 类的 `toUpperCase` 方法，但不是针对任何特定对象。这通常在遍历 Collection 或 Stream 时使用。例如，假设你想将 List 中的所有元素转换为大写。你可以如下所示使用此 `String::toUpperCase`：

```java
List<String> colours =
Arrays.asList("Red", "Blue", "Green");
List<String> upperCaseColours =
colours.stream().map(String::toUpperCase).collect(Collectors.toList());
```

# 第 05 章：DateTime API（日期时间 API）

### 232. 解释以下代码片段中的错误以及你如何修复它。

```java
LocalDate datel = LocalDate.of(2018, 7, 24);
LocalTime timel = datel.atTime(5, 30);
```

答案：

上面的代码片段创建了一个名为 `datel` 的 `LocalDate`。它随后在 `datel` 上使用 `atTime()` 方法并将结果赋值给名为 `timel` 的 `LocalTime` 对象。这导致了编译错误。`atTime()` 方法将当前时间对象的日期与指定的时间结合并返回一个 `LocalDateTime` 对象。因此，你可以通过以下更改来修复上面的代码：

```java
LocalDateTime timel = datel.atTime(5, 30);
```

这会将 `datel` 中指定的日期与时间 5:30 结合并返回一个 `LocalDateTime` 对象。

### 233. 用适当的代码示例说明创建 `LocalDate` 的不同方法。

#### 答案

`LocalDate` 类有一些用于创建 `LocalDate` 的静态方法。这些如下：

- a. 创建与当前日期对应的 LocalDate – 可以使用 `LocalDate.now()` 方法，如下所示：

```java
LocalDate date1 = LocalDate.now();
```

- b. 创建与指定的年、月、日对应的 LocalDate – 可以使用 `LocalDate.of` 方法，如下所示：

```java
LocalDate date2 = LocalDate.of(2018, 7, 24);
```

- c. 创建与 String 日期对应的 LocalDate – 可以使用 `LocalDate.parse` 方法，如下所示：

```java
LocalDate date3 = LocalDate.parse("2014-08-11");
```

### 234. 用代码示例解释如何检查一个日期是否在另一个日期之前。

#### 答案

`LocalDate` 类有一个名为 `isBefore()` 的方法。你可以使用它来检查一个日期是否在另一个日期之前，如下所示：

```java
LocalDate date1 = LocalDate.of(2018, 7, 24);
LocalDate date2 = LocalDate.parse("2014-08-11");
boolean isBefore = date1.isBefore(date2);
System.out.println("isBefore-" + isBefore);
```

此代码创建了两个日期对象 `date1` 和 `date2`。它在 `date1` 上调用 `isBefore()` 并将 `date2` 作为参数传递。由于 `date1` 在 `date2` 之后，`isBefore()` 方法返回 `false`。因此，此代码打印如下所示的输出：

### 235. 解释 `ZonedDateTime` 类。

#### 答案

`ZonedDateTime` 类表示一个带有时区信息的日期和时间。因此，除了年、月、日、时、分、秒组件外，它还有一个 `ZoneId` 组件。`ZoneId` 是 `java.time.ZoneId` 的实例，代表时区。大约有 40 个时区可以通过 `ZoneId` 表示。下面的代码展示了你如何创建一个 `ZonedDateTime`：

```java
ZoneId zoneId = ZoneId.of("Asia/Kolkata");
zonedDateTime zonedDateTime = ZonedDateTime.now(zoneId);
```

因此，上面的代码片段创建了对应于 Asia/Calcutta 的 `ZoneId`，它是 IST 时区。它创建了一个与系统时钟当前时间对应的 `ZonedDateTime`，但使用了此 ID。

### 236. 下面代码片段的输出是什么？

```java
LocalTime localTime = LocalTime.of(7, 15);
System.out.println(localTime.minusMinutes(30));
```

#### 答案

上面的代码创建了一个 `LocalTime` 实例。`LocalTime` 表示具有时、分、秒和纳秒组件的时间。这里创建了一个对应于 7:15 的 `LocalTime` 对象。代码随后调用了值为 30 的 `minusMinutes()` 方法并打印输出。`minusMinutes()` 方法从被调用的 `LocalTime` 上减去指定的分钟数。

从 7:15 减去 30 分钟后，时间将是 6:45。

因此，此代码打印如下所示的输出：

```
06-45
```

### 237. 如何使用 Java 8 DateTime API 获取与日期对应的星期几？

#### 答案

`LocalDate` 类有一个名为 `getDayOfWeek()` 的方法。你可以使用它来获取与日期对应的星期几，如下所示：

```java
LocalDate date = LocalDate.parse("2017-04-25");
System.out.println(date.getDayOfWeek());
```

上面的代码创建了一个 `LocalDate` 对象。它在 `date` 上调用 `getDayOfWeek()`。该方法返回星期几。由于日期是 2017 年 4 月 25 日，该方法返回 `TUESDAY`（星期二）。因此，此代码打印输出：

`TUESDAY`

### 238. 解释 `Period` 和 `Duration` 的区别。

#### 答案

`Period` 和 `Duration` 都是为了表示时间间隔而引入的类。

- `Period` 用于年、月、日衡量时间。
- `Duration` 用于时、分、秒和纳秒衡量时间。

### 239. 假设你有一个 yyyy/mm/dd 格式的字符串。如何获取一个 `LocalDate`？

#### 答案

```java
String strDate = "2012/10/11";
LocalDate date = LocalDate.parse(
    strDate,
    DateTimeFormatter.ofPattern("yyyy/MM/dd")
);
System.out.println(date);
```

上面的代码使用 `LocalDate` 类的 `parse` 方法将字符串转换为 `LocalDate` 对象。`DateTimeFormatter` 用于指定日期的格式。

### 240. 以下代码片段的输出是什么？

```java
LocalDateTime dateTime = LocalDateTime.parse("2014-12-28T08:45:00");
dateTime = dateTime.withYear(1998);
System.out.println(dateTime);
```

#### 答案

上面的代码首先创建了一个 `LocalDateTime` 实例。随后调用了 `dateTime.withYear()` 方法。该方法将被调用 `LocalDateTime` 的年份组件更新为指定的年份。因此，在这种情况下，它将 `dateTime` 中的年份更新为 1998 并将结果赋值给 `dateTime` 对象。因此，此代码打印输出：

`1998-12-28T08:45`

### 241. 解释如何使用新的 DateTime API 找出一年是否为闰年。

#### 答案

`LocalDate` 类有一个名为 `isLeapYear()` 的方法。它可以检查某一年是否为闰年，代码所示：

```java
LocalDate date1 = LocalDate.of(2020, 7, 24);
boolean isLeapYear = date1.isLeapYear();
```

此代码创建了一个名为 `date1` 的 `LocalDate`，然后在 `date1` 上调用 `isLeapYear()` 方法。`isLeapYear()` 方法返回一个布尔值。在这种情况下，由于 `date1` 对应 2020 年（闰年），`isLeapYear()` 方法将返回 `true`。

# 第 06 章：静态和默认接口方法

### 242. 什么是静态方法和默认方法？Java 8 为什么要引入它们？

#### 答案

在 Java 8 之前，接口只能包含抽象方法。因此，它们不能包含带有方法体的方法。Java 8 允许拥有带有方法体的方法，即静态方法和默认方法。引入这些方法的原因如下：

- 默认接口方法有助于保持代码的向后兼容性。在 Java 8 之前，如果向接口中添加了新方法，所有实现该接口的类都需要进行修改。默认方法克服了这一限制。因此，它们允许你在接口中添加带有方法体的方法，而所有的实现类就不需要修改了。
- 静态接口方法有助于将工具方法分组。静态接口方法不能在实现方法的类中被重写。因此这避免了由于实现错误导致的意外结果，并提供了额外的安全保障。

### 243. 在 Java 8 之后，抽象类和接口之间的区别是什么？

#### 答案

Java 8 默认接口方法的引入缩小了抽象类和接口之间的区别。在 Java 8 之前，接口不能包含具体方法。然而，Java 8 在接口中增加了默认和静态方法。这些是带有方法体的方法。这进一步缩小了抽象类和接口之间的区别。不过，两者之间仍然存在一些差异，具体如下：

- 抽象类可以拥有实例字段。另一方面，接口不能拥有实例字段。所以基本上，抽象类可以通过实例字段拥有状态，而接口不能拥有状态。
- 抽象类可以有构造函数并可以被实例化。另一方面，接口不能有构造函数。

### 244. 编写一个演示默认方法的代码示例。

#### 答案

默认方法简单来说就是接口内部带有方法体的方法。它带有 `default` 关键字。以下代码演示了这一点：

```java
public interface MyInterface {
    public void doSomething();

    public default void doSomethingElse() {
        System.out.println("Doing something else...");
    }
}
```

这段代码声明了一个名为 `MyInterface` 的接口。它包含一个名为 `doSomething()` 的抽象方法和一个名为 `doSomethingElse()` 的默认方法。默认方法指定了 `default` 关键字，并包含一个方法体。

### 245. 静态接口方法和默认接口方法之间的区别是什么？

#### 答案

静态和默认接口方法都带有方法体。然而，两者之间存在一些差异：

- 静态方法指定了 `static` 关键字，而默认方法指定了 `default` 关键字。
- 默认接口方法可以被重写。另一方面，静态方法不能被重写。
- 默认方法可以通过实现接口的类对象来调用。另一方面，静态接口方法不能通过实现接口的类或对象来调用。它们需要通过接口名称来调用。

### 246. 识别以下代码段中的错误并解释如何修复它。

```java
public interface MyInterface {
    public static void doSomething() {
        System.out.println("Doing something...");
    }
}

public class MyClass implements MyInterface {
    public static void main(String args[]) {
        MyClass obj = new MyClass();
        obj.doSomething(); // Line 1
    }
}
```

#### 答案

上述代码定义了一个名为 `MyInterface` 的接口，其中包含一个名为 `doSomething()` 的静态方法。然后创建了一个名为 `MyClass` 的类来实现该接口。`MyClass` 的 `main` 方法创建了一个 `MyClass` 对象 `obj` 并在第 1 行调用了 `doSomething()` 方法。这导致第 1 行出现编译错误。这是因为代码尝试通过类对象访问静态接口方法。静态接口方法只能通过接口名称访问。要修复此错误，需要将第 1 行替换：

```java
MyInterface.doSomething();
```

# 第 07 章：Optional（可选）

### 247. 什么是 `Optional`？为什么 Java 8 要添加它？

#### 答案

`Optional` 用于表示一个可能存在也可能不存在的值。它包含了一些方法，可以在值存在时用于获取底层值。以下代码演示了 `Optional`：

```java
Optional<Integer> number;
```

在这里，`number` 是一个 `Integer` 类型的 `Optional`。它可能也可能不包含值。



Java 8 引入 `Optional` 是为了避免与空检查相关的样板代码。有时，方法可能会返回 `null`，这可能导致 `NullPointerException`。为了避免该异常，调用方法的代码需要进行显式的空检查。这会使代码难以阅读。Java 8 的 `Optional` 有助于避免这些样板代码。因此，与其进行显式的空检查，可以使用 `optional`。如果值存在，就可以将其提取。

### 248. 如何创建 Optional？

答案：

`Optional` 类中有一些静态方法可以用于创建 `Optional`。它们如下：

- a. `Optional.isEmpty` – 创建一个空的 `Optional`，即如下所示的没有值的 `Optional`：

```java
Optional<Integer> number = Optional.empty();
```

- b. `Optional.of` – 创建一个带有特定值的 `Optional`，如下所示：

```java
Optional<Integer> number = Optional.of(10); // 创建一个值为10的Optional
```

- c. `Optional.ofNullable` – 创建一个带有 `null` 或非空值的 `Optional`，如下所示：

```java
Optional<Integer> number = Optional.ofNullable(10);
```

它也可以用于创建一个带有空值的 `Optional`：

```java
Optional<Integer> number = Optional.ofNullable(null);
```

### 249. 带有代码示例解释 Optional.ifPresent 方法。

答案：

`Optional.ifPresent` 方法在 `Optional` 存在时对其执行操作。如果 `Optional` 是空的，它什么都不做。以下代码演示了这一点：

```java
Optional<String> strOptional = Optional.of("Test");
```

```java
strOptional.ifPresent(str ->
    System.out.println(str.toUpperCase()));
```

这段代码创建了值为 `Test` 的 `strOptional`。所以这段代码输出：

```text
TEST
```

### 250. `orElse` 方法和 `orElseThrow` 方法的区别是什么？

答案：

- `orElse` 和 `orElseThrow` 都是 `Optional` 类的方法。如果 `Optional` 中存在值，它们都会返回该值。它们的区别在于当 `Optional` 中不存在值时的处理。

- `orElse` 方法接受一个值，并在空 `Optional` 上调用时返回该值。以下代码演示了这一点：

```java
Optional<String> strOptional1 = Optional.empty();
String strValue1 = strOptional1.orElse("Default");
```

在这里，由于 `strOptional1` 是空的 `Optional`，`orElse` 方法返回值 `Default`。

- `orElseThrow` 方法在空 `Optional` 上调用时抛出异常。它接受一个返回异常的 `Supplier` 实例。以下代码演示了这一点：

```java
Optional<String> strOptional2 = Optional.empty();
String strValue2 = strOptional2.orElseThrow(() -> new IllegalArgumentException());
```

在这里，由于 `strOptional2` 是空的 `Optional`，`orElseThrow` 抛出了 `IllegalArgumentException`。

### 251. 以下代码段的输出是什么？

```java
Optional<Integer> opInt1 = Optional.of(200); // Line 1
Optional<Integer> opInt2 = opInt1.filter(num -> num > 100); // Line 2
System.out.println(opInt2.get()); // Line 3
```

答案：

`Optional` 类有一个名为 `filter()` 的方法，在代码段中使用了它。`filter()` 方法接受一个 `Predicate`，并在 `Optional` 存在时将其应用到该值上。如果 `Predicate` 中的条件满足，它会返回 `Optional` 中的值，否则返回一个空的 `Optional`。在这种情况下，第 1 行创建了一个值为 200 的 `Integer Optional`。第 2 行调用了 `filter()` 方法，并传入了一个检查 `Optional` 值是否大于 100 的 `Predicate`。由于这是真的，`filter()` 方法返回了一个值为 200 的 `Optional` 并赋值给 `opInt2`。因此 `get()` 方法返回了这个值。

所以，这段代码输出：

```text
200
```

## 第 8 章：集合的改进

### 252. 请用代码示例解释 `forEach` 方法的工作原理。

答案：

Java 8 在 `Iterable` 接口中添加了一个名为 `forEach` 的新默认方法。`java.util.Collection` 接口继承了 `Iterable` 接口，因此所有 `Collection` 类都可以使用 `forEach` 方法。`forEach` 方法有助于内部遍历集合，而不需要显式的 `for` 循环。以下代码演示了这一点：

```java
List<String> colours =
Arrays.asList("Red", "Blue", "Black", "White");
colours.forEach(str -> System.out.println(str));
```

这段代码声明了一个名为 `colours` 的 `String` 类型值 `List`。然后在该 `List` 上调用了 `forEach()` 方法。`forEach` 方法接受一个 `Consumer` 实例作为参数并对其进行操作。在这种情况下，`Consumer` 通过 lambda 表达式实现，它只是打印传递给它的值。因此，这段代码输出了以下内容：

```text
Red
Blue
Black
White
```

### 253. Java 8 对 `List` 接口做了哪些改进？

答案：

Java 8 在 `List` 接口中添加了以下方法：

- a. `List.sort`：Java 8 添加了 `List.sort` 方法。它可以用于对 `List` 进行排序。它接受一个 `Comparator` 参数，并根据指定的 `Comparator` 对输入的 `List` 进行排序。

- b. `List.replaceAll`：Java 8 添加了 `List.replaceAll` 方法。它可以替换 `List` 中的所有值。它接受一个 `UnaryOperator` 接口作为参数。`UnaryOperator` 是 `Function` 接口的特化版本，它接受特定数据类型的输入并返回相同数据类型的结果。`replaceAll()` 方法将 `UnaryOperator` 应用于 `List` 中的每个元素。

### 254. `Map.getOrDefault` 方法是如何工作的？

答案：

Java 8 在 `Map` 接口中添加了 `getOrDefault` 方法。它接受一个需要检索其值的键（key）以及一个默认值作为参数。因此，如果指定的键存在，它将返回对应的值；否则，它将返回传入的默认值。以下代码片段演示了这一点：

```java
Map<Integer, String> fruits = new HashMap<Integer, String>();
fruits.put(1, "Apple");
fruits.put(2, "Orange");
```

```java
String fruit1 = fruits.getOrDefault(1, "Mango");
// 返回 apple
String fruit2 = fruits.getOrDefault(3, "Mango");
// 返回 mango
```

这段代码创建了一个名为 `fruits` 的 `Map`，其键类型为 `Integer`，值类型为 `String`。向 `Map` 中添加了一些值。它首先使用 `getOrDefault` 方法检索键 1 对应的值，并传递 `Mango` 作为默认值。由于 `Map` 中存在键为 1 的值，因此 `fruit1` 被赋值为对应的值，即 `Apple`。然后它使用 `getOrDefault` 方法检索键 3 对应的值，并传递 `Mango` 作为默认值。由于 `Map` 中没有键为 3 的值，因此 `fruit2` 被赋值为默认值 `Mango`。

### 255. 下面代码段的输出是什么？

```java
Map<Integer, String> fruits = new HashMap<Integer, String>();
fruits.put(1, "Apple");
fruits.put(2, "Orange");
fruits.put(3, "Strawberry");
fruits.replace(1, "Mango"); // 行 1
fruits.replace(2, "Orange", "Banana"); // 行 2
fruits.replace(3, "Blackberry", "Pineapple"); // 行 3
System.out.println(fruits.get(1));
System.out.println(fruits.get(2));
System.out.println(fruits.get(3));
```

答案：

这段代码输出了以下内容：

```text
Mango
Banana
Strawberry
```

`Map.replace(key, value)` 方法仅在键映射到某个值时才替换该值。在上面的示例中，键 1 映射到值 `Apple`，因此 `replace()` 方法将值 `Apple` 替换为 `Mango`。`Map.replace(key, oldValue, newValue)` 仅在键映射到指定值时才替换。在上面的示例中，键 2 映射到值 `Orange`。因此，第 2 行的 `replace` 方法将值 `Orange` 替换为 `Banana`。此外，键 3 映射到值 `Strawberry`。因此，第 3 行的 `replace` 方法没有替换该值，因为键 3 并没有映射到 `Blackberry`。

### 256. 解释 `Iterator` 和 `SplitIterator` 之间的区别。

答案：

`Iterator` 和 `SplitIterator` 都可以遍历集合中的元素。然而，这些接口之间存在一些差异，如下：

- `Iterator` 接口从 Java 早期就开始存在。`SplitIterator` 是 Java 8 添加的新接口。

- `Iterator` 接口仅支持顺序处理。`SplitIterator` 同时支持顺序处理和并行处理。

- `Iterator` 可以遍历集合。`SplitIterator` 可以遍历集合，也可以遍历 `Stream`。

- `Iterator` 只允许逐个遍历集合中的元素。而 `SplitIterator` 既允许逐个遍历集合元素，也可以批量遍历。

## 第 9 章：杂杂

### 257. `CompletableFuture` 类相对于 `Future` 接口有哪些优势？

答案：

在 Java 8 之前，Java 拥有 `Callable` 类和 `Future` 接口。它们可以用于返回异步计算的结果。然而，`Future` 接口存在几个问题。`CompletableFuture` 通过如下方式克服这些问题：

- `Future` 无法手动完成。因此，无法手动完成任务。`CompletableFuture` 提供了 `complete()` 方法可以手动完成。

- `Future` 有一个 `get()` 方法可以返回结果。然而，该方法会阻塞直到结果可用。`CompletableFuture` 允许附加回调，在结果可用时执行。

- `Future` 接口没有异常处理机制。`CompletableFuture` 提供了 `exceptionally()` 方法允许在发生异常时运行备用代码。

### 258. 什么是 `StringJoiner`？请用代码示例解释。

答案：

`StringJoiner` 是 Java 8 添加的一个新类。它有助于通过分隔符连接字符串，并带有前缀和后缀。以下代码演示了这一点：

```java
StringJoiner strJoiner = new StringJoiner("-", "[", "]");
// 行 1
strJoiner.add("cat"); // 行 2
strJoiner.add("dog"); // 行 3
strJoiner.add("mouse"); // 行 4
System.out.println(strJoiner); // 行 5
```

这段代码创建了一个 `StringJoiner`。它使用符号 `-` 作为分隔符，使用方括号 `[]` 作为前缀和后缀。然后它调用 `add()` 方法添加了一些字符串值。因此这段代码输出了：

```text
[cat-dog-mouse]
```

### 259. 解释 `Comparator.reversed` 和 `Comparator.reverseOrder` 方法之间的区别。

答案：

`Comparator.reversed` 和 `Comparator.reverseOrder` 都是 Java 8 添加到 `Comparator` 接口的方法。它们都有助于对集合进行反序排序。然而，两者之间的差异如下：

- `reversed` 是默认方法，而 `reverseOrder` 是静态方法。

- `reversed` 需要一个比较器存在。`reverseOrder` 不需要比较器存在，它直接返回一个按反序排序的比较器。

- `reversed` 返回一个施加于被调用的比较器的反序排序的比较器。`reverseOrder` 返回一个施加集合中元素自然排序反序的比较器。

### 260. 识别下方代码中的错误，并说明需要做什么来修复。

```java
public class Employee {
    private String name;
    private double salary;
    // 构造函数，getter 和 setter
}

List<Employee> employees = new ArrayList<Employee>();
ememployees.add(new Employee("A", 10000));
ememployees.add(new Employee("B", 5000));
ememployees.add(new Employee("C", 15000));
ememployees.sort(Comparator.comparingInt(employee ->
    employee.getSalary())); // 行 1
```

上述代码在第 1 行处有编译错误。`employees.sort()` 方法配合 `Comparator.comparingInt` 使用。该方法接受一个 `ToIntFunction` 函数式接口作为参数，并根据 `int` 字段进行排序。然而，这里使用的是一个返回 `double` 的 lambda 表达式。

返回一个 `double` 类型的薪资值。这会导致编译错误。为了修复此错误，需要将第 1 行修改如下：

```java
employees.sort(Comparator.comparingDouble(employee ->
    employee.getSalary()));
```

现在使用了 `Comparator.comparingDouble()` 方法。该方法接受一个 `ToDoubleFunction` 接口作为参数，根据 `Double` 字段进行比较。

### 261. 解释 `CompletableFuture.runAsync` 和 `CompletableFuture.supplyAsync` 方法之间的差异。

答案：

`runAsync` 和 `supplyAsync` 方法都可以用于异步运行代码。然而，它们之间存在以下差异：

- `runAsync` 方法不返回结果，因此它返回一个 `CompletableFuture<Void>`。相反，`supplyAsync` 方法从线程返回一个值。因此，它返回一个 `CompletableFuture<T>`。

- `runAsync` 方法接受一个 `Runnable` 实例作为参数。而 `supplyAsync` 方法接受一个 `Supplier` 实例作为参数。

- `runAsync` 方法在单独线程中执行 `Runnable` 实现中的代码。而 `supplyAsync` 方法在单独线程中执行 `Supplier` 中的代码，并返回 `Supplier` 产生的值。

# 第 3 部分：核心 JAVA

## JAVA 8

## JAVA 9

## 人力资源

## 第 1 章：模块（Modules）

### 262. 什么是模块？它们提供哪些好处？

答案：

模块由一组相关的包组成。就像你将一组相关的类放入一个包中一样，你也可以将一组相关的包放入一个模块中。模块提供了以下优势：

- 如果一个应用程序拥有大量的包，将很难追踪。模块的出现解决了这个问题，它们帮助组织包，也就是说，相关的包可以被分组到一个模块中。

- 模块可以独立部署。这有助于减小应用程序的。

- 模块提供了更好的安全性。在模块出现之前，使类在其他包中可重用的唯一方法是将其设为 `public`。然而，这引发了安全问题，因为公共类对所有人可见。将包分组到模块中可以确保该类在模块外部无法被访问。



在 Java 9 之前没有模块，像`rt.jar`这样的 Java API jar 文件非常大。相反，Java 9 将其拆分为更小的模块，这些模块更容易测试和维护。

在 Java 9 之前，安全性是一个问题，因为开发者可以访问 JDK 内部文件。模块也帮助克服这个问题。因此，通过模块，你可以控制模块内部哪些包在模块外部可见且可访问。

## 263. 什么是模块描述符 (module descriptor)？

答案：

模块描述符是一个名为`module-info.java`的 Java 文件。它包含了有关模块的信息。它需要存在模块的根目录下。以下行演示了模块描述符的结构：

```
module demomodule {
//可选指令
}
```

模块描述符可以包含一些可选指令。在模块描述符中指定的某些指令如下：

- a. **Name（名称）：** 指定模块的名称。

- b. **exports（导出）：** 指定模块内对其他模块可见的包名。

- c. **requires（需要）：** 指定当前模块所依赖的模块名称。因此，如果没有指定这些模块，当前模块可能无法工作。

- d. **provides（提供）：** 指定当前模块提供的服务。当模块作为服务提供者时，应使用此指令。

- e. **uses（使用）：** 指定当前模块消耗的服务。当模块作为服务消费者时，应使用此指令。

- f. **open（开放）：** 指定当前模块中的类可以通过 Java 反射访问。

## 264. 包 (package) 和模块 (module) 之间的区别是什么？

答案：

包和模块都是逻辑单元，并封装了一些 Java 文件。然而，它们之间存在以下差异：

- 包从 Java 的早期版本就开始存在了。而模块是 Java 9 引入的。

- Java 引入包是为了避免命名冲突，它们允许在不同的包中具有同名的类。Java 引入模块是为了将 JDK 模块化并提高安全性。

- `runAsync` 方法不返回结果，因此它返回一个`CompletableFuture<Void>`。相反，`supplyAsync` 方法从线程返回一个值。因此，它返回一个`CompletableFuture<T>`。

- `runAsync` 方法接受一个`Runnable`实例作为参数。而`supplyAsync`方法接受一个`Supplier`实例作为参数。

- `runAsync` 方法在单独线程中执行`Runnable`实现中的代码。而`supplyAsync`方法在单独线程中执行`Supplier`中的代码，并返回`Supplier`产生的值。

### 265. 解释 Java 9 所做的更改。

答案：

在 Java 9 之前没有模块，像`rt.jar`这样的 Java API jar 文件非常大。相反，Java 9 将其拆分为更小的模块，这些模块更容易测试和维护。

- 在 Java 9 之前，安全性是一个问题，因为开发者可以访问 JDK 内部文件。模块也帮助克服这个问题。因此，通过模块，你可以控制模块内部哪些包在模块外部可见且可访问。

### 266. 考虑以下代码：

```
package myyp;
public class MyClass {
    public void doSomething() {
}
```

答案：

模块描述符是一个名为`module-info.java`的 Java 文件。它包含了有关模块的信息。它需要存在模块的根目录下。以下行演示了模块描述符的结构：

```
module demomodule {
//可选指令
}
```

模块描述符可以包含一些可选指令。在模块描述符中指定的某些指令如下：

- a. **Name（名称）：** 指定模块的名称。

- b. **exports（导出）：** 指定模块内对其他模块可见的包名。

- c. **requires（需要）：** 指定当前模块所依赖的模块名称。因此，如果没有指定这些模块，当前模块可能无法工作。

- d. **provides（提供）：** 指定当前模块提供的服务。当模块作为服务提供者时，应使用此指令。

- e. **uses（使用）：** 指定当前模块消耗的服务。当模块作为服务消费者时，应使用此指令。

- f. **open（开放）：** 指定当前模块中的类可以通过 Java 反射访问。

### 267. 解释`of()`方法。

答案：

Java 9 增加了一个静态方法`of()`到所有集合接口中。上述代码使用该方法创建了一个 Integer List。该方法创建了一个不可修改的 List。然而，第 2 行尝试向 List 添加值，这在代码执行时会抛出异常。因此，为了修复上述代码，你需要删除第 2 行。因此，你需要重写代码如下：

```java
List<Integer> numbers = List.of(5,10,15,20); // 第 1 行
System.out.println(numbers); // 第 3 行
```

### 268. Java 9 对 Stream 有哪些改进？

**答案：**

- a. `Stream.ofNullable`：Java 9 为 Stream 增加了`nullable()`方法。这有助于创建一个 Stream。因此，如果向此方法传递非空值，就会创建一个 Stream。

- b. `takeWhile`, `dropWhile`：这两个方法作用于 Stream 上。它们被用于获取输入的一个子集。

- c. `Stream.iterate`：Java 9 增加了一个接受`Predicate`的重载版本，该方法在`Predicate`为真时停止 Stream。

### 269. 下代码有效吗？如果不有效，如何修复？

```java
Stream<String> strStream = Stream.of(null);
strStream.forEach(str-> System.out.println(str));
```

答案：

上述代码是有效的，不会导致编译错误。然而，当执行它时，会抛出`NullPointerException`。这是因为你不能使用`Stream.of()`方法创建一个包含空值的 Stream。为了修复上述代码，你需要进行以下更改：

```java
Stream<String> strStream = Stream.ofNullable(null);
strStream.forEach(str-> System.out.println(str));
```

## 270. 识别下方代码段中的问题并解释如何修复它。

```java
List<Integer> numbers = List.of(5,10,15); // 第 1 行
numbers.add(20); // 第 2 行
System.out.println(numbers); // 第 3 行
```

答案：

Java 9 为所有集合接口增加了静态方法`of()`。上述代码使用该方法创建了一个 Integer List。该方法创建了一个不可修改的 List。然而，第 2 行尝试向 List 添加值，这在代码执行时会抛出异常。因此，为了修复上述代码，你需要删除第 2 行。因此，你需要重写代码如下：

## 271. 你可以使用哪个 Java 9 方法来创建一个包含 String 值的 Set？

答案：

Java 9 在 Set 接口中添加了一个静态工厂方法。你可以使用该方法来创建一个包含 String 值的 Set。下面的代码演示了这一点：

```java
Set<String> months = Set.of("January","February","March");
```

这段代码创建了一个名为 months 的包含 String 值的 Set。它使用了带有指定值的`String.of()`方法。`String.of()`有多个重载/重载版本，可以接受 0 到 10 个参数，以及一个接受可变参数（varargs）的版本。

### 272. 下述代码段的输出是什么？

```java
Stream<Integer> oddNumbers = Stream.iterate(1, num-> num <= 20, num-> num+2);
oddNumbers.forEach(num-> System.out.print(num+" "));
```

答案：

在 Java 9 之前，有一个`Stream.iterate()`方法，它可以创建一个无限的数值流。Java 9 添加了`Stream.iterate()`方法的重载版本，可以创建一个有限的流。因此，该方法接受一个额外的参数作为`Predicate`（谓词），一旦谓词为真，流就会停止。所以，这段代码将打印以下输出：

```
1 3 5 7 9 11 13 15 17 19
```

# 第 03 章

##杂杂

### 273. Java 9 对接口做了哪些更改？为什么？

答案：

Java 9 允许在接口中使用私有方法。在 Java 8 之前，接口只能有抽象方法。Java 8 添加了对静态和默认接口方法的支持。默认和静态方法无非是带有方法体的接口。Java 9 更进了一步，允许在接口中使用私有方法。私有接口方法允许代码复用。因此，如果一个接口有多个默认和静态方法，并且这些方法之间存在一些共同代码，可以将这些代码移动到私有方法中。下面的代码演示了这一点：

```java
public interface Sample {
    default void method1(){
        //一些代码
        doSomething();
    }
    default void method2(){
        //一些代码
        doSomething();
    }
    private void doSomething(){
        System.out.println("Doing something.");
    }
}
```

在这里，`doSomething()`是一个私有接口方法，在默认方法`method1()`和`method2()`中使用。

### 274. 什么是 JShell？

答案：

JShell 基本上是一个命令行工具。它允许你在不创建类文件的情况下编写并运行 Java 代码。可以通过在命令提示符中输入`jshell`来启动。一旦 JShell 打开，你可以输入任何 Java 代码，JShell 将显示代码的输出。例如，如果你输入以下内容：

```java
System.out.println("Hello World");
```

JShell 将打印文本 "Hello World.\nJShell 为 Java 添加了 REPL 支持。REPL 代表读取-求值-打印循环（Read Evaluate Print Loop）。Python 等语言也提供了 REPL 功能。

### 275. 下述代码段的输出是什么？

```java
Optional<Double> myDoubleOptional = Optional.of(10.0);
Optional<Double> defaultOptional = Optional.of(50.0);
double value = myDoubleOptional.or(() -> defaultOptional).get();
System.out.println(value);
```

答案：



Java 9 在`Optional`类上添加了一个名为`or()`的新方法。它接受一个产生`Optional`的`Supplier`实例作为参数。它返回一个`Optional`。因此，如果调用的`Optional`非空，则返回该`Optional`；否则，返回由传递的`Supplier`生成的`Optional`。在上面的代码段中，`or`方法在`myDoubleOptional`上被调用，它是一个值为 10 的非空`Optional`。由于这是一个非空`Optional`，`or`方法返回此值，而不是`defaultOptional`。因此，这段代码将打印以下输出：

```
10.0
```

## 276. Java 9 对 try–with 语句做了哪些更改？

答案：

`try–with`语句是由 Java 7 添加的。它允许在没有显式语句的情况下自动关闭资源。例如，如果你正在编写写文件的代码，如果你使用`try–with`语句，`FileWriter`会在`try`语句完成后自动关闭。这种方式的缺点是需要自动关闭的资源。

Java 9 允许在`try-with`语句中使用有效最终（effectively final）变量。……（注：原文此段存在大量重复文本，已根据原意精简）Java 9 允许在`try-with`语句中使用有效最终变量。Java 9 允许向块中添加资源。……（注：原文此段存在大量重复文本，已根据原意精简）Java 9 允许在`try-with`语句中使用有效最终变量。……（注：OCR 在此处有重复，已清理为核心内容）。

## Answer:

在上述场景中，`finally`块中的返回语句将被执行；返回值为**0**。由于`try`块发生了异常，`try`块的剩余部分将被跳过。因此，`try`块中的返回语句不会执行。由于发生了异常，`catch`块中的代码将被执行。但由于存在`finally`块，`catch`块中的返回语句也不会执行。`finally`块的代码会被执行，`finally`块的返回语句也会执行。如果没有`finally`块，`catch`块的返回语句将被执行。

## 283. 假设你在`Base`类中有一个静态方法。假设你在子类中有一个同名的方法。假设你创建了一个`Base`类对象，并给它赋值子类对象的引用，然后调用该静态方法。这有效吗？如果有效，调用的是哪个版本的静态方法？

## Answer:

上述场景是完全有效的，不会引起任何错误。当执行此代码时，将调用基类中的静态方法。通常，当你定义一个父类类型的变量并给它赋值一个子类对象且调用被重写的方法时，调用的是子类中定义的方法。这是因为 Java 使用赋值的对象而不是引用变量来确定要调用的重写方法版本。然而，在上述场景中，父类和子类的方法都是静态的。静态方法不能被重写。因此，如果你在基类中有一个静态方法而在子类中有一个同名方法，这并不属于重写的例子。相反，这被称为方法隐藏（method hiding）。在这样的情况下，调用的方法版本不是由赋值给引用变量的对象类型决定，而是由引用变量的类型决定。在这种情况下，使用的是基类引用变量。因此，调用的是基类中的静态方法。

## 284. 假设你在基类中有一个方法，它会抛出`ArrayIndexOutOfBoundsException`。假设该方法在子类中被重写，并声明它抛出`RuntimeException`。你认为会发生什么？

## Answer:

上述场景说明基类方法抛出了`ArrayIndexOutOfBoundsException`，这是一个未检查异常（unchecked exception）。子类方法重写了该方法并声明它抛出`RuntimeException`。这种情况是有效的，且不会引起任何错误。在方法重写中，子类方法不允许抛出比父类方法中声明的异常更新或更宽的检查异常（checked exception）。但此规则不适用于未检查异常。因此，子类方法可以声明任何未检查异常而不会引起任何错误。如果子类方法在`throws`子句中声明了`java.lang.Exception`或其任何子类，将会发生编译错误。这是因为`java.lang.Exception`是一个检查异常。

## 285. 假设你有一个对象列表。你想将其发送给客户端应用程序，但想确保客户端应用程序不对其进行更改。你如何实现这一点？

## Answer:

为了确保客户端应用程序不对`List`进行更改，你需要获取`List`的只读副本并将该副本返回给客户端应用程序。`Collections`类有几个工具方法可以返回集合的只读副本。例如，它有一个名为`Collections.unmodifiableList`的方法。该方法接受一个`List`作为参数，并返回一个输入`List`的只读副本。一旦通过此方法获取了集合的只读副本，任何修改`List`的尝试（如添加或删除数据）都会抛出`UnsupportedOperationException`。因此，如果客户端应用程序尝试修改此`List`，就会发生异常。

## 286. 假设你正在从数据库读取 10000 个`String`值。你需要用这些值创建一个拼接后的`String`。实现此点的最有效方法是哪？

## Answer:

有多种方法可以拼接`String`值。最常用的方法是使用拼接运算符（`+`）。然而，从性能角度来看这并不是高效的，当你有大量`String`时，应该避免使用它。这是因为`String`类是不可变的。因此，使用`+`运算符会导致创建大量的`String`对象。Java 提供了`StringBuilder`类。它有一个`append`方法可以用于创建拼接后的`String`。由于它是一个可变类，因此性能更好。还有一个名为`StringBuffer`的类，它与`StringBuilder`非常相似。唯一的区别是`StringBuffer`是同步的，而`StringBuilder`不是。与`StringBuffer`相比，`StringBuilder`的性能略优。因此，如果同步不是问题，你可以使用`StringBuilder`，否则可以使用`StringBuffer`。

## 287. 假设你正在开发一个涉及非常大小数数学计算的应用程序。考虑到精度非常重要，你会使用哪种数据类型来定义你的变量？

## Answer:

通常，程序员在处理小数时使用`float`或`double`数据类型。然而，这些数据类型有一个缺点。在处理很大或很小的数字时，这些数据类型可能会丢失精度，导致结果不准确。因此，在精度重要的情况下使用这些数据类型并不是一个好主意。Java 提供了一个名为`java.lang.BigDecimal`的类。该类克服了`float`和`double`数据类型的局限性。它在处理很大或很小的数字时不会丢失精度，因此提供了精确的结果。它具有与所有算术操作（如加、减、乘、除）对应的方法。此外，它支持许多其他操作。因此，它可以执行所有的数学运算并提供精确的结果。`BigDecimal`的缺点是性能。然而，如果精度优先于性能，则应该使用`BigDecimal`。

## 288. 假设你正在开发一个多线程应用程序。出现了一个新需求，你需要存储键值对。在这种情况下，最合适的集合是什么？

## Answer:

`java.util.Map`接口支持以键值对存储数据。`Map`最常用的实现是`HashMap`。然而，`HashMap`的问题在于它不是线程安全的，因此不适用于多线程应用程序。`Collections`类有一个名为`synchronizedMap()`的工具方法。它接受一个`Map`作为输入，并返回一个与传入`Map`对象对应的线程安全`Map`。因此，这种同步`Map`可以在多线程环境中使用。还有另一个实现类`ConcurrentHashMap`。它是`Map`接口的一个线程安全实现，适用于多线程环境。`ConcurrentHashMap`的性能略优于同步`Map`。同步`Map`同步整个`Map`对象，因此当其他线程正在使用`Map`时，甚至不允许进行读取操作。而`ConcurrentHashMap`则没有同步整个`Map`，因此在其他线程正在写入`Map`时允许读取操作。因此，同步`Map`和`ConcurrentHashMap`都适用于多线程环境；如果考虑性能，应使用`ConcurrentHashMap`。

## 289. 假设你在应用程序中创建工具方法。创建此类方法的最佳实践是什么？你会把它们放在哪里？

## Answer:

大多数开发者会将工具方法放在单独的类中。然而，你应该将工具代码放在与其相关的类中。例如，如果你有一个名为`Car`的类，并且需要一个`createCar`的工具方法，它可以是`Car`类本身的一个静态方法。

与其创建一个独立的`CarUtil`类。然而，在许多编程场景中，你可能需要将一些无关的工具方法组合在一起。在这种情况下，你可以创建一个单独的类并在该类中创建静态工具方法。从 Java 8 开始，你也可以在接口中拥有静态方法。静态接口方法有助于将工具方法分组在一起，而无需创建类的对象。

## 290. 假设你作为 API 的一部分开发了一个名为`FileWriter`的接口。它有一个`writeToCsv`方法，可以将传入的内容写入 CSV 文件中。该 API 由不同的应用程序实现，这些应用程序为`FileWriter`接口提供了具体实现。现在，假设你被要求向接口中添加一个名为`writeToExcel`的新方法，将传入的内容写入 Excel 文件中。你如何在对 API 用户影响最小的情况下进行这一更改？

## Answer:

在上述描述的场景中，需要在`FileWriter`接口中添加一个新方法。简单地向接口中添加该方法会导致实现该接口的所有现有类出现编译错误，并要求所有类为`writeToExcel()`方法提供实现。最好的办法是将`writeToExcel()`方法作为默认方法（default method）添加到`FileWriter`接口中。默认方法是 Java 8 引入的新功能。它们允许你在接口中创建带有方法体的方法。实现接口的类不需要为默认方法提供实现。因此，将`writeToExcel()`方法作为默认方法添加到`FileWriter`接口中不会影响实现`FileWriter`的类。默认方法是由 Java 8 添加的，所以如果你使用的是早期 Java 版本，此解决方案将无效。在这种情况下，你可以创建一个`FileWriter`接口的新版本（例如`FileWriterEnhanced`），它扩展当前的`FileWriter`并在`FileWriterEnhanced`接口中添加`writeToExcel()`方法。在这种情况下，实现`FileWriter`接口的现有代码将正常运行。任何需要`writeToExcel()`方法的代码都需要实现`FileWriterEnhanced`接口。

# 第 04 节

核心 JAVA

JAVA 8

JAVA 9

人力资源

# 第 01 章

# 创意

## 291. 你从哪里寻找灵感？

## 答案：

灵感可以来自任何地方，面试官希望看到你的灵感同样是多样化的。提到你获取灵感的多个地方，或者你进行头脑风暴的环境。此外，详细说明你是如何记录灵感或稍后对其进行扩展的。

## 例如：

我整天都会不断在笔记本上或手机里记录我以后想回顾的内容。我在工作会议期间、通过听同事面临的困难和进展时获得灵感，做记录并在稍后研究我们如何改进工作流。当我的人脉发布他们在职场追求的新创新成果时，我也会通过他们获得灵感，并思考我如何能在自己的公司里应用这些创新。

## 292. 你在工作中如何实现创造力？

## 答案：

向面试官展示你在工作中能够善用资源并具有创新精神是重要的，同时不要超出公司价值观的范畴。解释你的灵感通常源于何处（例子可以包括列清单或思维导图等练习），并将其与工作中某项你发挥创造力的特定任务联系起来。

## 例如：

> 我被分配到了一个安全与健康工作小组。大多数人在休息时其实都在走路，只是没有聚在一起。我参加了一个为期三个月的托管步行挑战，在休息期间，人们仍然可以自己散步，但被鼓励与同事互动，并在跟踪进度方面进行一些健康的竞争。这最终让更多的人站起来运动，同时也增强了士气和团队合作精神。

## 293. 你如何推动他人创造灵感？

## 答案：

如果你处于管理职位，这可能要求员工提交特定数量的创意，或者完成定期的灵感产生练习，以锻炼他们的创意肌肉。然而，你也可以通过创造更多自己的灵感来简单地推动周围的人创造创意。此外，与面试官讨论提问的重要性，这是激发灵感和改变的一种方式。

## 例如：

在每次员工会议上，我都会鼓励员工带上他们自我们上次会议以来一直面临或遇到的问题或挑战，并附带解决方案。我鼓励员工参加定期的职业发展机会，无论是免费的网络研讨会、培训，甚至是阅读他们所在领域新发表的文章，并与团队分享他们学到的东西或热门话题。

## 294. 描述你的创造力。

## 答案：

尽量将这个答案控制在专业领域内，但如果你在职业经历之外的某些创意领域拥有令人印象深刻的背景，不要害怕将其纳入答案中。关于创意的最佳答案将与解决问题的能力、目标设定以及在工作中应对项目或完成销售的创新方法有关。办公室之外的热情也很棒（只要它们不会占用你的工作时间或心理空间）。

## 例如：

我参加了一个工作之外的志愿者小组，为无家可归者提供食物。我工作过的公司正在寻求与社区的联系，以及员工参与比其特定工作角色更大事务的方法，因此在公司的许可下，我举办了一场公司内部的募款活动，员工举办意大利面晚餐以为无家可归者筹集资金。这提升了团队合作和目标感。

# 第 02 章

# 领导力

## 295. 你更倾向于获得更多的权力还是责任？

## 答案：

这两者各有优缺点，面试官会更有兴趣看到你能提供一个批判性的回答。获得更多的权力可能意味着更大的决策权，对于那些具有卓越领导能力的人来说是非常棒的；而更大的责任对于那些希望在职业生涯中稳步发展的人来说是一个增长机会。

## 例如：

我会说我在团队中的工作方式是“仆人式领导”的良好范例。我具有天生的领导能力，人们自然地追随我。我是一个天生的项目经理，既能看到大局也能看到细微的细节。尽管如此，我会听取团队的意见，鼓励并重视他们所有的投入。关键在于具有领导力并做出简洁、妥当决策的能力，同时考虑到整个团队的意见和想法，并在需要时改进你的决策。

## 296. 当小组中的有人没有贡献应有的份额时，你会怎么办？

## 答案：

如果你正在应聘管理职位，这是一个特别重要的问题——解释你识别问题的方法，以及你将如何找该个人单独来讨论他们的贡献。理解建立对话的过程是非常重要的，这样你就可以清楚地向该个人传达你的期望，给他们回应的机会，并明确需要改变的地方。之后，与该小组成员制定行动计划，以确保他们的贡献与小组中的其他人相当。

## 例如：

我会说我在团队中的工作方式是“仆人式领导”的良好范例。我具有天生的领导能力，人们自然地追随我。我是一个天生的项目经理，既能看到大局也能看到细微的细节。尽管如此，我会听取团队的意见，鼓励并重视他们所有的投入。关键在于具有领导力并做出简洁、妥当决策的能力，同时考虑到整个团队的意见和想法，并在需要时改进你的决策。

## 297. 请告诉我们一次你做出了超出权限范围的决策的经历。

## 答案：

虽然对这个问题的回答可能表现出你果断且自信，但它也让雇主将你识别为潜在的问题员工。相反，最好的办法是将问题稍微重新聚焦，转向一个你承担了额外责任的案例，因此不得不做出超出正常权限范围的决策（但这些决策是在特定情况下被授予你的）。讨论决策的权重如何影响了你的决策过程以及情况的结果。

## 示例：

我曾有一位客户要求免除月度费用，因为他们觉得服务质量不高。当时只有经理有权做此决定，而他那天恰不在公司。客户非常不满，并准备要取消服务。我推迟了当天的缴费，并覆盖了由于客户欠费而设置的自动取消程序，同时向经理保证他第二天会联系该客户。当他们能够交谈时，客户的问题得到了解决，他们决定继续使用我们的服务。

## 298. 你是否乐意就分歧问题与主管进行沟通？

## 答案：

当问题出现时，雇主希望你能够以及时且恰当的方式处理。强调你过去很少与主管发生分歧，但如果真的发生了这种情况，你觉得完全乐意与相关人员进行讨论，以找到一个令双方都满意的解决方案。

## 示例：

我曾向主管提交了一份需要调整的报告，那份报告由他们格式化后提交给公司老板。当我向主管指出他们的错误时，他立刻表现出防御心理，直到我向他保证，我只是偶然发现了数字上的差异，并想提醒他们注意，以便在提交之前进行调整，这样他以及我们部门看起来会更好一些。我向他保证，我是在维护我们产出工作的完整性，并想尽力支持他。他感谢我，报告在没有错误的情况下提交了。

## 299. 如果你曾在上一份工作中担任负责人，你会有什么不同的做法？

## 答案：

无论你对如何让事情运行得更好有多少想法，或者对上一份工作管理层有什么意见，在回答这个问题时都要保持积极态度。对如何处理某事以提高效率或增加销售额进行深思熟虑是可以的，但要确保你所有的建议都集中在如何让事情变得更好，而不是讨论消除浪费或负面情绪的方法。

## 示例：

> 我本会更关注部门员工的跨岗培训，这样我们在自己的空闲时间，或者当团队成员的角色或职位出现工作量激增或紧急情况时，能够更好地互相帮助。这将有助于减少混乱和积压，让整个部门都能跟上进度并保持高效。

## 300. 你认为是否应该对工作表现良好的员工给予表扬或奖励？

## 答案：

在完成一项艰巨任务后获得认可总是很棒，但许多雇主问这个问题可能是为了推断你是否是一个“高维护”的员工。虽然你可能喜欢奖励或表扬，但向面试官传达出这一点非常重要：你不需要赞誉来确认自己工作得很好。如果你正在应聘一个由你来表扬其他员工的主管职位，请强调表扬对提高团队士气的重要性。

## 示例：



我相信每个员工我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。表扬的回应（以及他们是否渴望表扬）是不同的。有些人可能非常渴望并为了表扬而努力，而另一些则不喜欢处于风口。确保员工意识到他们被聘用是为了工作，并被要求完成任务很重要。话虽如此，员工也是人，会有压力巨大的日子、私私生活，有时仅仅是上班并努力工作本身就值得表扬。让员工知道他们作为支持组织的人是受到重视的，而不仅仅是一个员工编号。每季度为全体员工提供免费的午餐，配有音乐和食物，并对在特殊情况下表现卓越的人给予认可，是维持士气和团队友谊的极佳方法。

### 301. 你认为领导者具备最重要的特质是什么？

#### 回答：

在任何业务中，领导者都需要许多重要的技能，而这个问题的关键点在于你要解释为什么你选择强调的那个特质是重要的。尝试选择一种特质，如沟通能力或激励人的能力，并将其与你在团队中展示该特质的特定实例联系起来。

#### 示例：

沟通是领导力的关键。在做出决定之前能够考虑到所有方面和每种情况，并且成为最终做出决定的人（无论这个决定是否受欢迎），这些都是领导者需要的能力。重要的部分是能够真正倾听员工并听取他们的顾虑，让他们知道你重视他们的意见，然后向他们解释你为什么做出那个决定。大多数时候，员工只是想感到被听见了。始终保持畅通的沟通渠道对于维护员工之间的信任至关重要。我曾决定调整休假申请政策，要求员工在休假前至少两周申请，这引起了许多人的不满。一旦我解释了这一决定是基于休假日期重叠、人手不足、同事之间不公平以及利润损失的考虑，并且这对公司和员工都是更好的选择，他们就理解了。

### 302. 告诉我一次遇到不可预测问题的经历。你是如何处理的？

#### 回答：

在压力下保持机智多变和冷静至关重要。面试官希望看到你以系统化的方式处理问题，并能够按照有序流程处理变化。清晰地描述情况，包括你所实施流程的所有解决方案和结果。

#### 示例：

作为我上一任雇主的安全官，我曾与部门主管有一个非常重要的下午两点会议，该会议已经在日程表上列了一个月，由于高管层行程繁忙，无法推迟。与此同时，我在现场有一个紧急的安全问题需要赶过去处理。我在两个问题之间左右为难，于是我让我的实习生带着我准备好的演示文稿去会议，解释了情况并向他们展示了演示文稿。他解释了他能解释的内容，并对他们的问题以及他无法回答的事项进行了记录，我们安排在第二天进行跟进电话，以讨论我不在场时无法回答的待办问题。我们在跟进电话中解决了所有遗留问题，并在第二天推进了项目。高管们理解了我所面临的困境，并很感激不需要暂停项目。

### 303. 你能给我举一个例子，说明你在上一份工作中是如何改进 X 目标的吗？

#### 回答：

在这里，重点应该是你所为公司带来实质性结果的改进。提高效率无疑是业务中非常重要的因素，但雇主也在寻找具体的成果，例如销售额的增长或费用的减少。详尽地解释你的过程，尽可能提供具体的数字和证据，特别是在概述结果时。

#### 示例：

我成功减少了每次客户通话的 4 分钟等待时间，并优化了等待列表流程，我建议使用一种软件，让所有客服代表都能访问一个显示所有客户电话的显示器。显示器显示了有多少电话正在通话、等待中或挂机（以及由哪个代表负责），以及他们使用的是哪条线路。代表可以轻松地挂断电话，查看看板并决定下一个接听哪条线路。这改进了客服的工作流。

该部门每天大约可以多处理 20 个多个客户问题，在现在可以接收的新订单方面使利润增加了 30%，并提升了客户满意度和公司评分。

### 304. 请描述一次主管对项目提供的指导不够具体的经历。

#### 回答：

虽然许多雇主希望员工能够遵循非常具体的指南，而不具备太大的决策权，但能够接手指导模糊的项目并独立完成工作同样重要。请列举你提过的哪些必要问题，并说明你是如何判断哪些问题是需要请示主管的，而哪些是你自己可以决定的。

#### 例如：

当我的主管准备休假时，我手里已经有一个大型项目在等待处理了。在她休假之前，她又给了我另一个项目，但没有留下截止日期。我分析了该项目，确定这是一个新客户，我不想让他们苦苦等待。我继续处理手头上的项目，并联系了新客户进行自我介绍，并安排了电话讨论他们的需求。这为我赢得了时间，同时也让我获取了更多信息。当时截止日期仍然不清楚，而且看起来并不紧急，所以我继续处理现有的工作，并每天下午安排固定时间开始处理新客户的项目。

### 305. 请描述一次你负责领导某个项目的经历。

#### 回答：

引导面试官了解项目的执行过程，就像你对团队任何成员做的那样。解释项目的目标、必要的步骤，以及你是如何向团队分配任务的。包括结果，以及你通过这次领导机会学到了什么。

#### 例如：

作为一名人力资源助理，在人力资源福利代表休假期间提供协助，我负责了一个大型机构的年度员工福利注册工作。我提前与经理进行了沟通，尽可能收集了关于过去时间安排和流程方面哪些做法有效的信息，并我自己又添加了几个很有有用的改进，例如为即将到来的各种福利变动建立了一个归档系统。在开放注册开始前的一周，我与人力资源部门开了一个会议，检查了每份表格，并向我的团队解释了我将如何分发每份表格，还为他们制作了实用的信息小抄，放在他们的办公桌上，以防员工来提问而我恰好不在身边。

整个过程非常顺利且井井有序，员工们评价这非常简单。

### 306. 请描述你曾向前雇主提出的一个后来被实施的建议。

#### 回答：

雇主希望看到你对改进公司感兴趣并愿意尽一份力——请提供一个具体的例子，说明你在之前的工作中做了什么来创造积极的改变。解释你是如何想到这个主意的，你的主管是如何接受的，以及在主意实施时，其他员工是如何看这个想法的。

#### 例如：

我建议成立一个创新委员会，让员工聚集在一起讨论他们对工作场所的新想法。这些想法涵盖了广泛的内容，例如实施员工认可机制、零食自动机选项、客户大厅的变动，以及其中的任何任何细节。虽然管理层没有采纳所有的想法，但大多数大多数想法的变体都得到了实施。这让员工对公司产生了主人翁意识和归属感，同时也提高了团队士气和团队合作。

### 307. 请描述一次你认为工作场所的某事可以更高效完成的经历。

#### 回答：

关注你想法的积极方面。重要的是，不要对你的旧公司或老板进行负面描绘，因此不要详细阐述某个系统有多低效。相反，解释一个你看到机会提高生产率或简化流程的情况，并用通用的步骤说明你是如何实施一个更好的系统的。

#### 例如：

我们的部门将周五设定为“归档日”，处理一整周收集到的文件。虽然这绝对是一个很棒的主意，但如果有同事请假，或者我们某某周有大量需要归档的文件，有时我们在周五就无法全部完成，或者因为一整周收到的大量文件而感到压力巨大。我建议我们在项目之间的空隙时间在整周内进行归档，这样我们就不会在某一天堆积所有工作。我还注意到，每天的最后半小时，一些同事会开始“收拾东西”，由于我们的工作量，在最后一点时间里我们无法真正开始新项目，所以我们会开始收拾东西，然后在每天的最后三十分钟里归档，直到下班。这极大地减少了周五堆积的工作量，同时也保持了整个周内更高的的生产率。

### 308. 领导和管理人员之间有区别吗——哪一个是你的更大优势？

#### 回答：

是有区别的——领导者往往是出主意的人，充满激情、富有魅力，并且组织和激励他人的能力；而经理是那些确保系统运行、促进其运营、做出权威决策，并对从整体成功到最细微决策的所有方面承担巨大责任的人。考虑哪一种最适用于该职位，并解释你如何胜任这一角色，提供你过去经验的具体例子。

#### 例如：

我是一个很好的领导者，因为我会花时间考虑项目的所有可能方面，以及它将如何影响每个负责该项目的员工。我尽力从每个角度来看问题，预测并计划可能出错的事情，并专注于可能顺利进行的事情。我推销想法的方式能够获得员工的支持，并让他们觉得他们是其中的一部分。

### 309. 你在领导角色中工作更好，还是作为执行者工作更好？

#### 回答：

考虑面试官在寻找什么很重要，并表达你如何体现这一角色，以及保持事情顺畅运行的能力。

#### 例如：

虽然我可以在任何一个角色中工作，但我发现我更适合领导工作，因为这对我来说非常自然。即使在那些我不是老板的职位上，也有人来向我寻求建议、碰撞想法。

### 310. 请描述一次你在工作场所发现某些扰了你（或他人）生产率的经历——你是如何处理的。

#### 回答：

尽量不要过多关注你之前工作的负面方面，而是选择一个你发现了积极且快速解决方案来提高生产率的实例。关注你发现机会的方式，你如何向你的主管提出解决方案的，然后该改变是如何实施的（最重要的是，谈谈你如何领导这项变革倡议）。这是你展示解决问题能力、以及资源利用能力和领导能力的绝佳机会。

#### 例如：

我们唯一的考打卡机经常在所有员工同一时间下班时面临长长的排队。这会导致下班排队时的混乱、员工情绪不满、赶时间的员工完全跳过流程，以及员工提早收拾当天的东西以便“去排队”。我建议在房间另一侧靠近第二个入口处增加第二个打卡机以缓解排队。这有助于提高生产率，因为员工不再需要提早收拾并浪费时间站在打卡机前，同时也缓解了一天结束时的某些烦躁。

### 311. 你在目标明确的目标和工作中表现如何？

#### 回答：

在回答此问题时，考虑该职位很重要——显然，如果你能在目标明确的目标和工作中表现出色，那是最好的（特别是如果你处于初级或销售职位）。然而，如果你申请的是一个具有领导角色或创意方面的职位，请务必关注你额外喜欢开发和实施自己想法的挑战。

我喜欢拥有一套可以遵守的准则规则。这有助于简化流程，特别是在处理以客户为中心的公司时。话虽如此，如果我发现某项可以改进的政策，我不介意将自己的想法推到前沿，对其进行测试，如果有效，就将其实施。随着流程的改进，需要更新政策，并通知所有员工新的程序，以确保所有员工的步调一致。

### 312. 在一个拥有巨大决策权的职位上，你的表现如何？

#### 回答：

面试官想想知道的是，如果被录用，你不会是那种需要不断监督，或者在每一步都寻求建议、授权或反馈的员工。请解释你能够在果断、高效的环境中工作得很好，并且你期待在自己的职位上采取主动行动。

#### 例如：

在之前的职位中，我曾多次获得过担任决策者的机会。虽然有些时候存在关于如何妥善履行职责以及职位局限性的准则，但在某些情况下，你必须现场做出果断的决定。在这些时刻，我不介意发挥创意来解决问题，并在事后告知我的上级发生的情况，以便让他们了解进展。

### 313. 如果你看到其他员工有不诚实或不符合道德的行为，你会怎么办？

#### 回答：

在目睹其他员工做出不诚实行为的情况下，最好的方式总是根据公司政策来处理此类情况——如果你不知道这家公司的具体政策，可以简单说你将根据政策处理，并向相关的负责人汇报。如果你了解公司的政策（例如，如果你正在自己的公司内部寻求晋升），那么最好是根据政策具体列出你的行动。

#### 例如：

这很大程度上取决于他们在做什么。某些事情，如盗窃巨额资金、设备或任何让自己陷入危险的行为，需要立即报告。然而，可能在某些时候，同事可能为了节省时间或降低成本而违反了政策或绕过规程，而这可能对他们自己或公司产生不利影响。在这些情况下，我乐意亲自与同事讨论这个问题，看看我是否能以任何方式帮助他们，并让他们知道他们所做的事情是错误的。他们可能没有意识到那是错误的，或者可能正经历艰难的时期。如果我们在谈话之后他们继续这样做，我将乐意向管理层反映这个问题。

### 314. 请讲述一次你自学某项技能并在日后对职业生活有所帮助的经历。

#### 回答：

这个问题很重要，因为它能让面试官洞察你对学习和进步的投入程度。仅从你的个人生活中选择一个例子，并提供一个简短的轶事，以你学到的教训结束。然后，用清晰详尽的方式解释这一教训如何转化为你职位上可行的技能或实践。

#### 例如：

我周末时会在一家志愿者组织工作。当该组织的负责人无法抽空领导一场募捐活动时，我必须介入并确保活动顺利进行、负责布置并向观众进行主持。我当时非常紧张，但这最终极大地提高了我的公共演讲能力，在下一次工作单位的团队会议上，我能够向同事发言并陈述我的项目，而不再感到紧张。我还被要求协调工作的下一次员工活动，并将我在志愿者活动中学到的一些内容应用到公司的员工活动中，例如座位安排和签到流程。我成为了公司团队中一个更具价值的成员。

### 315. 请讲述一次你在工作中构思项目想法的经历。

#### 回答：

选择一个由你构思的、与你在新职位上可能完成的项目典型的想法。概述你的想法源何处、为了确保其成功和相关性你做了哪些类型的研究、项目包含的步骤以及最终结果。提供具体的改进前后统计数据，以证明其成功。

#### 例如：

我们在招聘新销售人员方面遇到了困难。我构思了更新我们销售职位职位描述的想法。我们之前的职位描述已经过时了，已经多年没有更新，在此期间，许多新的软件工具已经问世，该职位也发生了变化。销售团队聚集在一起审查了当前的职位描述，并就他们认为应该在描述中增加或删除的内容提供了意见，然后管理层进行了审查并相应地进行了更新。一旦我们开始使用新的职位描述发布招聘广告，申请的合格销售专业人士增加了，他们更了解自己所申请的职位，且匹配度更高。

### 316. 请讲述一次你在项目中项目中承担过风险的经历。

#### 回答：

无论这种风险涉及的是诸如在资源或时间有限的情况下承担重大项目这样复杂的事情，还是仅仅自愿承担一项你经验范围之外的任务，都要表现出你愿意走出舒适区并尝试新事物。提供具体的例子说明为什么某事是有风险的，并解释你在这个过程中学到了什么——这如何帮助你应对日后在职业生涯中面临的工作目标。

#### 例如：

我在一家公用事业公司的工程部门工作。我们遇到一个紧急情况，社区内的一根水管破裂，社区关于公用账单的客户电话让我们应接不暇。期间，两名客服请假，由于我正处于两个大项目的空隙，于是我提供了协助。尽管我完全超出了舒适区，但我协助接听客户电话、回答基础问题，并记录下我无法帮助的客户姓名和电话，以便主管以后拨回电话。我成功收到了大约100名客户的款项，成功回答了大约50个问题，并另外记录了25个回电信息。我更多地了解了我所在部门的工作是如何与客服联系的，以及他们面临的问题类型和面临的挑战。在这种情况之后，两个部门开始更多地合作，甚至举行了季度会议，提供可能直接影响另一个部门工作的更新信息。

### 317. 对于一个想要进入这个领域的人，你会告诉他们什么？

#### 回答：

这个问题让你能够成为专家——并向面试官展示你拥有与简历上的任何培训和教育相匹配的知识和经验。提供你的知识作为对进入该领域的人可能会遇到的意外情况的建议，并确保以积极的建议结尾，例如对获得真正成功所需的激情或投入。

#### 例如：

如果有人想进入销售领域，我会建议他们首先查看有哪些可以帮助该领域的证书课程或学位选择。我还会建议，如果你对与他人交流（无论是一对一还是小组）感到不自在，就去上一个公共演讲课程来增强信心。我会建议学习销售的门道，并找到一个你真正热于销售的产品。如果你对自己的业务没有热情，特别是在销售领域，你不会做得很好。一旦你找到了自己热于销售的产品，就尽可能地了解关于它的一切。如果是产品，就去使用、测试它；如果是服务，就去尝试它。记住在初期允许自己失败几次，这并不是世界末日，因为它能帮助你学习。在工作中保持坚持，了解哪些方法对你的目标群体是有效的，哪些是无效的。对客户客户保持积极的态度，在显得过于咄逼或急切与显得太胆怯和不感兴趣之间找到平衡，并在第一次联系后不要忘记跟进！

# 第 03 章

## 截止日期与时间管理

### 318. 请告诉我一次你没有按时完成任务的经历。

#### 回答：

理想情况下，这种情况没有发生过——但如果发生过，请确保你使用一个较小的例子来说明情况，强调这种情况持续了多久，并确保你已经尽了最大努力以确保满足截止日期。此外，务必包括你在为了更好地管理时间或安排任务优先级以满足所有未来截止日期方面学到了什么。

#### 例如：

我极少（如果可以说从不）错过截止日期。尽管如此，我记得大约两年前，我错过了一个向财务部门提交报告的截止日期。问题在于我一次性承担了太多的项目，而且那周又突然插进来几个“紧急”的突发问题。我没有寻求帮助，心想自己可以搞定一切，而且不想给主管留下我无法胜任这项工作的印象。但结果是，我让主管失望了，当我坐下来他们讨论这个问题时，他们向我保证，只要我一直就工作量与他们沟通，他们会帮助分担压力。从那时起，我确保向主管更透明地说明我的当前工作量，并表达我对截止日期的任何担忧。从以后我没有错过过截止日期，而且通过更开放的沟通，我和同事的关系以及在部门内的效率都得到了提高。

### 319. 你在工作时如何消除分心？

#### 回答：

随着技术的进步和沟通的便利，新的干扰源每天都会出现。面试官希望看到你仍然能够专注于工作，并且你的生产力没有受到影响，可以通过一个例子说明你为了保持任务状态而采用的常规做法。

#### 例如：

每天早上，我都会查看当天的任务并为我需要做的事情做准备。我会检查电子邮件、消息和其他个人物品，然后收起个人设备。我确保我的家人和朋友知道我只在休息期间查看消息，如果有紧急情况，他们有一个很好的电话号码可以联系到我。工作日休息期间，我不会参与过社交媒体，因为那会拖累工作时间。休息时，我更倾向于散步、阅读、和同事聊几分钟，或者给家人或朋友发信息问候，然后回到工作。

### 320. 请告诉我一次你在一个有每周或每月配额需要完成的职位。你成功的频率如何？

#### 回答：

你的数据会说明一切，你必须诚实地回答这个问题。如果你经常能达到配额，请务必以自信的方式强调这一点，不要羞于指出你在这一方面的优势。如果你的统计数据不那么理想，尝试指出它们在在你职结束前有所增加的趋势，并对你未来可以改进的方法进行反思。

#### 例如：

我每个季度都能如时完成截止日期。我将公司给我的配额作为基准，然后基础上加上我自己的个人目标。这样，我有了更高的目标可以努力，而且如果我只能达到公司目标而不能达到自己的目标，也留有回旋地。我尝试不过分关注每日销售额，而是进行每月检查。这使我不会在担心进度上浪费太多时间，同时确保我正处于目标之上。

### 321. 请告诉我一次你完成了艰难截止日期的经历，以及你是如何完成它的。

#### 回答：

解释你是如何对任务进行排序，或者将任务部分分配给其他团队成员，以应对艰难的截止日期。具体说明为什么截止日期很困难可能会有益——确保清楚这不是由于你个人的拖延导致的。最后，解释你是如何成功满足截止日期的，以及最终达成目标付出了什么努力。

#### 例如：

由于同事突然缺席，我被分配了提交一份我从未做过的州报告的大型任务。我在空闲时间自己研究了该主题，联系了其他公司查看他们是如何完成该项目的，并发现了一个可以在办公时间内参加的在线培训。在老板的许可下，我将文书工作分配给了部门秘书，直到我能够完成该州报告。我提前提交了报告，这为我的工作以及我作为员工的身份增了值，因为之后我被要求协助其他项目，并在随后的评估期间获得了极佳的绩效评估和加薪。

### 322. 当你手上有多个项目时，你如何保持组织有理？

#### 回答：



面试官将希望看到你是否能良好地管理时间和工作——能够同时处理多个项目，并给每个项目提供应有的关注，是员工能力和效率的极佳标志。回顾一个典型的目标设定和优先级排序流程，并向面试官解释这些步骤，这样他或她就能看到你管理时间如何。

例如：

我在笔记本和 Outlook 日历上维护着一份持续的任务列表。每天早上我上班后，都会查看我的 Outlook 日历，并回顾前一天在笔记本上添加的任务列表，在整天过程中优先考虑哪些是需要做的，哪些可以等一下。对于那些在本周晚些时候可以完成的任务，我利用 Outlook 日历将任务安排在特定日期，并优先考虑当天需要做什么，哪些可以等。

### 323. 在工作日期间你有多少时间处于“自动驾驶”状态？

回答：

虽然你可能会好奇，雇主希望看到你有多高效（例如，增加销售额或生产力），但在大多数情况下，雇主希望看到你不断地思考、分析和处理。即使事情进展顺畅，通常也有地方可以变得更高效。强调你对持续发展的奉献。

例如：

我的工作做得很好，经常发现自己处于自动驾驶状态。尽管如此，当我完成一个项目时，我会花时间检查准确性。如果我有富余的时间完成项目，我会尝试不同的方法，看看是否有改进的办法。有时有，有时没有；然而，我不断寻找以最有效、最专业的方式利用时间。

### 324. 你如何处理截止日期？

回答：

处理艰难截止日期最重要的部分是对任务进行排序并设定完成目标，以及授权或消除不必要的工作。引导面试官进入一个通用场景，并展示你组织和设定优先级的能力，最重要的是保持冷静。

例如：

我利用 Outlook 日历来处理需要定期完成的持续任务。例如，我每周一必须提交销售报告，每周三必须进行归档。如果有任何我需要准备的特别项目即将，我会在日历上留出时间并设置提醒来准备该项目。我每天早上上班时也会花时间查看当天的任务，并在每天结束时也这样做，以完成为第二天需要准备的所有工作。如果我觉得由于某些原因我无法满足截止日期，我会与合作的部门沟通，并查看是否需要进行调整。沟通是关键。此外，当紧急项目出现时，我时刻意识到需要相应调整我的计划。

### 325. 请告诉我你的个人解决问题的流程。

回答：

你的个人解决问题的流程应该包括概述问题、提出解决问题的可能方法，并制定一个通向解决方案的清晰行动计划。保持你的回答简练且有组织，并以简洁冷静的方式解释这些步骤，显示即使在压力下也能保持头脑。

当我担任设备机械师时，我发现自己很难应对公司里多个项目经理派来的工作量。他们中的每个人都开始将我指派为技术员来负责他们客户的设备。我曾尝试对其中一些人说不，但被被指责没有团队合作精神。最后，我与车间领班讨论了问题所在，并解释说我很有团队合作精神，只是一天之内没有足够的时间来完成他们给我的所有任务。于是我在工作区域建立了一个工作进度安排板，上面写着我手头有哪些任务、项目经理是谁、每个项目处于什么阶段，以及预计的完成时间。这让所有项目经理都能清楚地看到我的工作量，并能更好地地理解和欣赏我正在做的工作，从而使他们能够决定是想找别人来维修客户的设备，还是等我这里空出来。

### 326. 工作中哪种事情会让你感到压力？

回答：

由于最好是远离负面情绪，请保持这个回答简明扼要。虽然回答“工作中没有任何事让你感到压力”对面试官来说可能不太可信，但请将答案保持在一个通用的原则上，例如团队成员没有履行承诺，然后专注于你通常采用的应对这种压力的解决方案，例如召开每周状态会议或在项目过程中设定间歇性的截止日期。

举例说明：

当与其共事的同事没有尽力时，如果这最终对我的工作产生了负面影响，会让我感到压力。在这些期间，我会保持冷静并与团队沟通。我会在能力范围内提供帮助，并努力寻找改善状况的方法。我尽力保持积极愉悦的态度，因为表现出负面情绪只会让情况变得糟糕。我曾与三位同事一起负责一个项目。我们都有特定的任务，而且这些任务都与彼此的任务相互关联。如果我们其中一个人落后了，我们所有人都会落后。一位同事一直落后于我们其他人，整个项目也都在滞后。我把那位同事拉到一边询问他们是否需要帮助，并向他们解释他们的不及时导致了我们其他人的落后。我以一种非常非指责的方式进行了谈话，并保持氛围轻松。我就他们如何提高准时性提供了建设性的建议，然后建议我们团队召开每日会议，查看每个人的进度。这增加了团队内部的透明度，并为该同事如何改进的对话打开了门，最终帮助我们按时完成了项目。

### 327. 你在职场中如何对外应对压力？当你感到压力大时，如何让自己冷静下来？

回答：

这是一个陷阱题——面试官想听到的是你在压力大时看起来没有任何变化，而且你不会让负面情绪干扰你的工作效率。至于你如何解决压力，最好是你精通一个简单的解决方案，例如只需深呼吸并数到10，以此将自己重新回到手头的任务中。

举例说明：

当我开始对工作中的某种情况感到压力时，我有时倾向于变得非常安静，花太长时间去思考我想要给出的回答或想要传达给团队的信息。在这些情况下，我知道让团队知道我很重要的：虽然我现在感到有点压力，但我会没事的，我只是在处理这种情况的正确方法。我确保深呼吸，保持镇定，微笑并说我要快速休息一下。让自己离开现场并走出去，或者甚至在休息室坐一会儿看会儿书。如果员工问我我在做什么，只需轻松地告诉他们我需要一点时间来思考如何绝妙地回应这种情况，或者如果是更严肃的话题，我可以说我只是需要一点时间充电。然后重新整队并回到我的团队。

### 328. 你擅长多任务处理吗？请举一些你成功处理多项任务的例子。

回答：

有些人可以，有些人则不行。多任务处理中最重要的部分是时刻保持头脑清晰，明确需要做什么，以及每个任务的优先级是什么。解释你如何评估任务以确定优先级，以及你如何管理时间以确保所有任务都能高效地完成。

举例说明：

我很擅长多任务处理，因为我能够快速应对变化。我一直记录着我正在处理的任务清单，所以如果我有中断或有紧急项目需要我离开现有的任务，我能够迅速回到之前正在工作的任务上。

### 329. 你每周工作多少小时？

回答：

很多人会被这个问题误导，认为回答更长的小时更好——然而，这可能会让雇主怀疑，为什么你需要花费这么多时间才能完成别人在更短时间内就能完成的工作。给出一个完成一项工作所需小时的合理估算，并解释你也愿意在需要时进行额外工作。

举例说明：

如果我做的是一份每周40小时的全职工作，那么我就是那样工作的。诚实地说，我们是人……所以曾有过我身体不舒服导致速度很慢，或者有几周我可能只工作了30小时左右，但我没有错过任何截止日期，而且一旦我感觉好些了，我就恢复了通常的工作速度和生产力时长。另一方面，如果我觉得需要加班，我只有在获得主管许可后才会这样做。有一次我遇到了紧急情况，本该离开但离开就会让公司变得更糟，所以我多留了30分钟完成任务，这样他们就意识到了。

重要的是，你需要提供一个你真正额外付出的努力的例子——注意不要把你觉得付出了很大努力与雇主本该要求你做的事情搞混了。请提供一个关于客户问题的例子，你是如何解决它的，以及在你处理完情况后客户的反应。

### 示例：

我曾与一个新客户合作一项大型建筑工程。客户本已准备好开展项目，但陷入了财务困境。我想确保能帮到客户，于是制定了一项付款计划，让他们不需要预先支付所有费用。他们签署了一份合同，注明我调整了付款计划，并且这是一次性的情况，这样他们就能意识到如果将来再次使用，可能需要再次预付。新客户对此非常感激，项目顺利完成。我们与该客户保持了长期的关系，并在随后从他们那里获得了更多工作，还获得了良好的评价，由于口碑相传，在社区内的知名度也提高了。

### 333. 你如何获得客户的信任？

回答：

这是一个非常开放的问题，可以让你向面试官展示你的客户服务技巧。这里有很多可能的答案，最好选择一个你拥有过良好经历的，例如“通过透明的方式处理情况”、“提供奖励”或“专注于良好的沟通”。提供你获得过的具体成功案例。

### 示例：

开放的沟通对于获得客户信任一直都是有益的。我不会为了提供答案而随便给出一个答案，如果我无法立即回答客户的问题，我一定会让客户知道，并向他们保证我会获得正确答案并回复他们。然后，我会确保跟进。如果没有沟通和跟进，你就会失去信任，他们会把业务转给其他地方。客户感激诚实，以及感激你为提供正确答案和最佳服务所花费的时间。

### 334. 请告诉我一次客户感到不悦或激动的经历——你是如何处理这种情况的？

回答：

与处理与另一同事的纠纷类似，回答这个问题最重要的部分是首先设定场景，针对你特定的冲突解决风格提供分步骤的指南，并以描述冲突解决的方式作为结束。在回答关于你自己的冲突解决风格的问题时，务必强调双方开放沟通和理解的重要性，以及达成妥协或其他解决方案的意愿。

### 示例：

情绪不佳的客户只是想被倾听。倾听是非常重要的。我在账单客服中心工作时，有一个客户打来电话，抱怨她觉得每月账单收费太高了。她打电话时已经很激动了，我很快意识到，我越试图和她说话，她就越不开心。我花时间倾听，让她充分解释情况。对我来说，很明显，她没有关注发出的关于费率上涨的通知。我告知了她费率上涨的情况，并免除了第一个月的涨价部分，然后通过电子邮件将通知发给她审阅。第二天我给她打了了电话进行跟进，看她是否还有任何问题。

### 335. 你什么时候可以为客户破例？

回答：

通常情况下，只有在符合公司政策或根据主管指示时，才可以为客户破例。表现出对应该考虑破例的情况类型的理解，例如当客户遭受了特定的困境、订单出现复杂问题或根据客户要求时。

### 示例：

通常，公司有相关的流程和政策以确保运营顺畅，并在确保所有客户得到公平对待的同时，确保公司盈利且不被占便宜。有时客户可能会遇到异常或意料之外的困境，导致他们难以按时付款，在这种情况下，应该作为一次性的优惠给予延期。如果问题持续到下个月，我会查阅政策手册看看是否还有其他可以提供的，如果没有，我会寻求主管的协助和指导。在那个时候，通常由主管来做决定。

### 336. 当客户和你的老板同时需要你时，你会怎么办？

回答：

虽然你的客户和老板对你的需求不同，并且对你作为工作者的成功都非常重要，但最好的方法总是尝试先照顾客户——然而，关键在于向老板解释为什么客户急切需要你，然后向老板保证你会尽快处理他或她的需求（除非是绝对紧急的事情）。

### 示例：

客户永远第一，老板在大多数时候都明白这一点。在老板可能与客户同时向请求你帮助的情况下，很容易去找老板看看他们需要什么，获取信息，并向他们解释，你将在帮助完客户后立即着手处理那项任务。客户是你的业务来源，你需要确保他们得到及时的照顾。

### 337. 客户服务中最重要的方面是什么？

回答：

虽然许多人会简单地认为客户满意度是客户服务最重要的方面，但能够在客户服务场景中详述其他重要技巧也是重要的。解释为什么客户服务是业务如此关键的，并确保对你认为最重要的方面以合逻辑且深思熟虑的方式进行扩展。

### 示例：

客户服务最重要的方面是真诚。如果你没有真正能帮助客户的产品，或者如果你在提供客户服务时不真诚，公司将会失败。能够享受提供最佳的服务并对帮助客户感到兴奋，会让客户也对与你做生意感到兴奋，并感到自己得到了照顾。良好的态度设定了与客户对话的基调，确保跟进并尽职会让客户对你的服务感到放心。

### 338. 为客户建立低预期还是高预期最好？

回答：

你可以从任何一种方式回答这个问题（当然，是在确定公司对该问题没有明确意见之后）。然而，无论你从哪种方式回答，都必须展示详尽的思考过程，并为你的选择提供非常清晰的理由。提供每个选项优缺点，并包含倾向于你所选答案的最终观点。

# 第 05 章

沟通

### 339. 请描述一次你向同事解释一个困难或复杂的想法的经历。

回答：

首先向面试官简要地解释该想法，然后概述为什么有必要向同事进一步拆解。最后，用简洁明了的步骤解释该想法，以便面试官能够看到你的沟通能力和化繁为简的技巧。

举个例子：

> 我当时有一个关于新工作调度系统的想法，并需要向团队展示。由于我的资源有限，且我们还没有获得必要的软件，所以我做的是写了一份关于该想法的简要概述，并结合互联网上的软件图片和截图添加了主要的要要点，然后汇编成一份 PowerPoint 演示文稿。我尝试思考会议期间可能出现的所有问题和不同的视角，以便我准备好回答问题，并以一种能吸引所有方式进行展示。我还列了一份优缺点列表，并针对可能出现的每个问题提供了解决方案，这让团队明白我经过深思熟虑并且准备充分。

### 340. 你觉得在什么情况下沟通起来比较困难？

回答：

即使是出色的沟通者通常也会发现某些特定情况更难进行有效沟通，所以不要害怕诚实地回答这个问题。务必解释你提到的特定情况为什么对你来说很困难，并尝试选择一个不常见的答案，例如语言障碍或在困难时期，而不是像与上级权威说话这样的情况。

举个例子：

在传达坏消息时，有时很难进行有效沟通。这种时候很容易产生压力，或者担心对方会有什么反应。重要的是在你感到准备好之前，不要尝试进行沟通。要准备好倾听而不仅仅是说说，回答你有答案的问题，并对对方的想法或感受表现出同理心。最重要的是要开诚且自信地进行沟通，让对方感到很自在，并对你或对局势有信心。

### 341. 良好沟通的要素组成部分是什么？

回答：

良好沟通的一些组成部分包括：不受干扰的环境、听者的反馈，以及说话者在必要时进行的修订或澄清。必要时可以参考基本的沟通模型，并提议与面试官进行角色扮演演示，以展示你的技能。

举个例子：

我发现，进行严肃谈话时，保持眼神交流并避免手机或电脑等干扰是最好的。知道要求澄清是没问题的这一点非常重要，这样就不会出现任何误解的情况。反思倾听是任何沟通中极佳的工具，你可以通过在适当重复对方说的某些话向对方展示你正在倾听（例如：“我听到你说你需要对这个项目更多的支持。让我们看看如何解决它，并获得你所需的支持。”）。

### 342. 请讲述一次你通过沟通解决问题的经历。

回答：

在商业世界中，通过沟通解决问题是关键，因此请从你之前的工作中选择一个具体的情况，当时你是如何通过冲突中的有效沟通来应对混乱局面的。解释情况的基础，以及你采取的沟通步骤，最后讨论为什么通过沟通解决问题对最终解决至关重要。

举个例子：

我的部门因为缺乏面对面的沟通且仅通过电子邮件交流，导致了太多的误解。我们不在同一时间查看邮件，彼此不在同一个频道上。我们继续在工作上出现重叠，任务分配不均，导致许多任务被遗漏。此外，还出现过通过邮件下指令不明的情况。我要求我的部门至少每两周开一次部门会议，以确保我们都在同一个步调上，并留出不受干扰的时间互相交流并提供部门项目的进展更新。这种共同相处的时间建立了团队的友谊，并为开启更多沟通渠道提供了有效的方法。

### 343. 请讲述一次你与另一员工发生争议的经历。你是如何解决该情况的？

回答：

确保使用一个具体的实例，并分步骤解释场景、你是如何处理的，以及最终是如何解决的。中间的步骤，即你如何处理争议，显然是最具决定性的——描述你使用的沟通类型，以及你如何通过妥协达成共识。冲突解决是任何员工都应该具备的一项技能，也是面试官会寻找的技能，用以判断你卷入争议的概率，以及一旦发生争议时，他们被迫介入争议的概率有多大。

举个例子：

当我与一位同事发生争议时，我问他们是否可以谈谈这个问题。起初他们显然并不感兴趣。我留给他们空间，并在几天后再次跟进，同时温和地强调我尊重他们，并希望把这个问题抛在过去，这样我们才能更好地向前迈进并合作。我提议了一个折中方案，我们达成了一个对我们都有效的协议。

### 344. 你是快速建立关系，还是需要时间来培养？

回答：

这两个选项都可以，因此请确定哪种风格最适合你。强调你所采取的步骤并总结为什么这种方式对有效。

举个例子：

我发现我可以快速建立关系，因为我平易近人且乐于结识新人。然而，也会花时间维护专业边界以确保相互信任。

### 345. 描述一次你不得不克服办公室政治来解决问题的经历。

回答：

尝试在回答这个问题时关注积极的一面，这样你就可以将这一情况转化为优势。不要负面地描述你之前的雇主，而是使用一个较小的实例（例如文书工作或个人），来突出你是如何克服的。给出你为了达成结果而使用的沟通技巧或解决问题的示例。

举个例子：

我有很多时候需要克服获取新许可审批时办公程序中的“官僚主义”。尽管有时这令人感到非常沮丧且耗时，但我理解这是必要的，因为需要时间审查计划并确保工作符合安全和法律协议。我有一项需要加快的任务，所以我准备了一封解释情况的信、一份来自业务主的声明，并让我的主管联系签署授权来陈述我的理由。我确保包含了以下原因：如果建造时间太长，该项目将影响社区；以及加快进度对社区是有益的，而且这家店的开会对同一片空地的开设其他商店产生连锁效应。虽然这项工作最终没有在第二天完成，但比原计划提前了两周完成。

### 346. 请讲述一次你说服他人承担一项艰巨任务的经历。

回答：

这个问题是一个展示你领导力和沟通能力的机会。虽然具体的场景本身作为背景介绍很重要，但重点应放在你是如何说服他人的，以及哪些策略最有效。

举个例子：

我有一位同事不愿意帮助我实施新的归档系统。这个项目将非常耗时且困难。我向她展示了关键要点，说明该项目将使她自己和整个部门受益并让她的工作变得轻松，并告诉她这最终是一件让她感激的事，也是一个展示才华的机会。我通过告诉她她有很多非常棒的主意，以及如果她参与项目将有助于完成来激励了她。

因为她的知识和想法，工作变得更快更高效。这让她觉得自己很有价值并感到被需要，从而激励了她去帮助。

### 347. 请告诉我一次你成功说服一个群体接受你提案的经历。

回答：

这个问题旨在衡量你的应变能力和沟通技巧。解释你是如何考虑小组内的不同视角的，并制作出一个对所有成员都具有吸引力且有说服力的演示的。此外，你也可以通过提供关于提案本身的细节来推销该提案，展示其执行得有多好。

例如：

我曾尝试购买一种新的发票软件，但没有人对它感兴趣。他们不感兴趣是因为他们习惯了目前的软件，并且觉得太忙了，没有时间学习新系统。我研究了我感兴趣的软件，整理了一份要点清单，并在计划中的会议之前发给每个部门的成员，这样他们就有时间查看并带着问题来。然后，我通过截图以及关于该软件如何减轻他们工作的深度信息，向团队展示了该软件。我特意地找了几位同事，指出它将如何直接影响他们的工作并改进他们的流程。在做出决定之前，我留给他们时间去思考并进行更多的研究。

### 348. 请告诉我一次你与他人发生冲突的经历，事后看来，你希望当时能采取不同的处理方式。

回答：



这个问题的关键在于展示你的反思能力和学习过程。解释当时的情况、你是如何处理的、结果是什么，最后，你现在会如何处理。最重要的是，告诉面试官你现在为什么会以不同的方式处理——是因为你之前的解决方案给与那个人的关系造成了压力，还是你希望自己当时能更坚定地维护自己的诉求？虽然你不应该详细阐述你之前处理情况的方式有多糟糕，但最重要的是展示出你通过这次冲突已经获得了成长，并达到了更深层次的理解。

例如：

多年前，我有一位同事从不愿意听我说的任何话，也不听取我的任何想法。他们非常固守成规，不愿意学习新事物。当时我想最好的办法就是直接避开他们，让他们各行其是，避免冲突。事后看来，我本可以做得更好，去理解他们的观点以及他们可能对变化的恐惧，并更好地尝试沟通对新流程的需要，同时向他们保证新流程可能会让他们的工作变得更轻松，我们是一个团队，会在整个变化过程中互相支持。多年来，我的沟通能力以及意识到沟通对团队合作乃至最终对公司重要性的能力得到了极大提高。

## 349. 请告诉我一次你调解其他员工之间冲突的经历

### 回答

对于那些应聘主管职位的人来说，这是一个特别重要的问题——从一个具体的情况开始，解释你是如何与每个人进行有效沟通的。例如，你是否引入了折中方案？你是否做出了行政决定？或者，你是否当了调解员并鼓励员工自行得出结论？

例如：

在担任店主管期间，我有许多次担任两名员工之间纠纷的调解员。没有一种一成不变的方案适用于所有情况，因为每个员工都不同，每种情况或纠纷也不同。我会仔细反思纠纷，并根据我所了解的事实以及相关方的性格，对需要做什么做出决定。大多数情况下，让两名员工坐下来讨论，由我担任见证和调解员是非常有效的。我确保让每个人都有机会陈述发生的情况、他们的观点，以及这给他们带来了什么感受或他们认为最好的结果是什么。我确保始终指出双方都可以以不同的方式处理这种情况以避免纠纷升级，并指出我感到他们身上拥有的能够进步并更好地合作的积极特质。我总是确保事情进展顺利，并且如果他们再次遇到问题，我一直实行开放政策。

# 第 06 章：求职与日程安排

## 350. 你在职位上最看重的三个点是什么？

### 回答

你对一个职位最想要的前三点应该与雇主对员工要求的前三点相似，这样就能清楚地表明你与工作非常匹配。例如，雇主想要一个资优秀且具有实践经验的候选人——而你想要一个可以让你将教育和技能发挥最大作用的职位。雇主想要一个愿意接受新挑战并开发新系统以增加销售或生产力的候选人——而你想要一个能推你并提供发展、创造和领导新倡议机会的职位。雇主想要一个成长并在公司长期留的候选人——你想要一个提供稳定性并相信建立强大团队的职位。在之前研究一下雇主在寻找什么，并将你的目标与他们的匹配。

例如：

我寻找的三个点将是：应用我的技能产生积极影响的机会、成长和学习新事物的机会，以及在拥有良好使命的公司中的稳定性。

## 351. 你是如何评估你想要加入公司的？

### 回答

虽然你可能觉得在面试期间提出自己的要求会感到不自在，但雇主希望看到你对你所申请的公司进行批判性思考。不要害怕说明你的需求（最好在申请之前），并在你的回答中表现出自信和果断。面试官想知道你是那种清楚自己想要什么的人。

例如：

我关注的是员工满意度、公司稳定性以及公司提供的服务类型。我想确保公司能很好对待员工，并且每天对工作充满热情。最后，我想知道公司存在一段时间，让我成长。

## 352. 你对这个薪资满意吗？

### 回答

如果这个问题的答案是否，那么在面试中可能是一个致命伤，因为你不太会有很大的还价空间。你可以通过强调你的特定经验来尝试增加筹码，并了解行业标准。

例如：

我对这个起薪水平完全满意。我很珍惜这个机会，并知道会在公司继续成长。

## 353. 你为什么选择上一份工作？

### 回答

通过了解是什么引导你选择了上一份工作，面试官能够感受到激励你的事物类型。将这些内容保持在专业范围内，并对职业生涯的早期保持热情，以及你对进入该领域感到多么兴奋。

例如：

我选择上一份工作是因为那是一家非营利机构。工资比私人公司低，但我知道这将是一个很好的经历，而且他们需要帮助。我的技能和知识对他们的公司是一个很好的补充，当时我可以靠薪水生活。那是一段很棒的经历，现在时间过去了，我准备好让职业向前迈进并达到新的高度。

## 354. 你离开上一份工作多久了？为什么？

### 回答

确保为所有的职业空窗期准备好解释，并确保这是一个专业的理由。不要提到你在找工作时可能遇到的困难，以及不如关注积极的事物，例如追求业外的兴趣，或者回到学校接受进修教育。

### 示例

我的上一份工作大约在一年前。我的那份工作要求很高，时间很长，财务状况也很好，但我还是花了一些时间休息，并专注于我一直觉得被错过的家庭时光。在那段时间里，我参加了一些职业发展课程，并重新明确了目标，现在准备好重返职场。我感到自己焕然一新，经过了重新培训，并重新专注于我最感兴趣从事的专业领域。

## 355. 你还在寻找其他类型的工作？

### 回答

这个问题的回答可以向面试官展示你不仅正处于人才市场，而且非常受欢迎。提到你申请过或看过的与你的领域密切相关，或与你面试的职位相似的工作。不要提到那些走投无路的尝试，比如发现申请一份与你领域完全无关的兼职。

### 示例

因为我正在追求营销职业，所以我专注于公立部门的营销工作。我目前申请的大多是营销助理职位，如果我还能参与营销，我也可能对行政职位感兴趣。我对作为一名成功的营销助理的能力非常有信心，所以我正尽力在那个领域占有一席之地，在那里我可以帮助公司用新的创造性营销策略拓展眼界。

## 356. 你在工作中受过纪律处分吗？

### 回答

希望这里的答案是否定的——但如果你确实在工作中因为某事受过处分，一定要确保你能详尽地解释。详细说明你从这种情况中中学到了什么，并反思在这个过程之后你是如何成长的。

作为一个示例：

我在工作中没有受过处分，但在重大项目期间没能及时向我的主管汇报进度方面，我收到过一些批评。我倾向于进入状态并按照自己的节奏推进，完成工作，当时我并没有认为在没有出现任何问题的情况下，让主管了解最新进展是重要的。我想，如果发生了什么问题，才是让我的老板介入的时候。经过讨论，我了解到主管实际上每周需要向高层管理层提交报告，其中必须包含我的项目以及我在流程中的进度。一旦得知这一点，我意识到，即使在一切顺利的情况下，向老板通报项目进展也一直很重要。

## 357. 你的时间安排是怎样的？

### 回答

你的时间安排显然应该是尽可能开放的，任何时间上的空缺都应该得到解释和说明。避免询问假期或请假（以及其他福利），并向面试官传达你对工作的有多么认真。

作为一个示例：

我查看了营业时间，认为我的时间安排将与工作的要求相匹配。虽然我显然需要时间照顾家庭和个人事务，但我愿意根据需要加班工作，以支持该机构。

## 358. 我可以联系你现在的雇主吗？

### 回答

如果可能的话，最好让面试官联系你现在的雇主作为推荐人。但是，如果不联系你的雇主非常重要，请委婉地解释你的原因，例如你刚刚开始找工作，还没有机会他们你正在寻找其他工作机会。不过，要小心这种理由，因为雇主可能会怀疑你会在为他们工作期间同时也在寻找更好的机会。

### 示例

我不完全介意你联系我的现任主。我希望你能在提供条件录用通知（contingent offer）后再等待，并给我时间先与我的老板沟通，出于对他们的尊重，我不让他们措手不及。虽然他们知道我最终可能会离开去发展职业生涯，但由于我在组织中扮演着如此重要的角色，他们完全会立即担心填补我的职位。我希望在他们接到电话之前能和他们谈谈。

## 359. 你是否有任何可以带入我们业务的有价值的人脉？

### 回答

如果你能带来知识、推荐人或其他新雇主可以建立人脉的联系，那就太棒了。

但是，请确保你没有提供你上一任雇主的任何客户，或以任何方式违反合同协议。

### 示例

我在其他机构有一些很棒的人脉，他们使用的软件和我会计领域的软件相同。多年来，我们一直能够共同排除故障并解决问题，他们与我分享许多很棒的新想法，帮助我处理出现的问题。我一定会得到很多支持。我还有几位企业主，他们可以与你们的管理团队分享关于处理员工问题和新业务趋势的任何见解。

## 360. 你多快可以开始工作？

### 回答

虽然你希望在公司对雇用你感兴趣时确保自己尽可能尽快开始，但如果你还有另一份工作，请务必给他们至少两周的通知。虽然你的新雇主可能急于让你开始，但他们会希望雇用一个因给出充分通知而受尊敬的员工，这样他们就不必担心你最终会将他们陷入困境。

### 示例

虽然我很渴望并兴奋与你们一起工作，但出于尊重，我更倾向于给我的现主两周的通知。这将留出时间处理收尾工作，并让我能够帮助他们。

## 361. 你的雇主会说你是为什么离开的？

### 回答

虽然你希望在公司对雇用你感兴趣时确保自己尽可能尽快开始，但如果你还有另一份工作，请务必给他们至少两周的通知。虽然你的新雇主可能急于让你开始，但他们会希望雇用一个因给出充分通知而受尊敬的员工，这样他们就不必担心你最终会将他们陷入困境。

作为一个示例：

我很渴望并兴奋与你们一起工作，但我更倾向于给我的现主两周的通知，出于尊重。这将留出时间处理收尾工作，并让我能够帮助他们。

## 362. 你积极寻找多久了？

### 回答

如果你能带来知识、推荐人或其他新雇主可以建立人脉的联系，那就太棒了。

但是，请确保你没有提供你上一任雇主的任何客户，或以任何方式违反合同协议。

### 示例

我在其他机构有一些很棒的人脉，他们使用的软件和我会计领域的软件相同。多年来，我们一直能够共同排除故障并解决问题，他们与我分享许多很棒的新想法，帮助我处理出现的问题。我一定会得到很多支持。我还有几位企业主，他们可以与你们的管理团队分享关于处理员工问题和新业务趋势的任何见解。

## 363. 你什么时候不上班？

### 回答

显然，可以不上班唯一时间是紧急情况或当你真的生病时——所以不要现在就计划因为假期或家庭生日而缺勤。或者，你可以向面试官传达你对工作的有多么投入，以及你如何努力在每次上班时都投入等量的工作，即使在你感到身体不适时。

作为一个示例：

通常情况下，我缺勤需要很大。如果我打喷嚏也会去上班，我不会因为打喷嚏或轻微头痛而请假。同时，我不想传染给其他人，所以当我感到身体非常不适时，我确定会留家里。此外，当然，如果有家庭紧急情况需要请假，我会在发现需要后立即给我的主管足够的通知。我很擅长让老板了解最新情况。我还会预计预计缺席整天告知老板需要处理的任何紧急任务，这样就不会落后太远，并保持完全透明。

## 364. 你是否曾被主管要求离开工作一天？如果是，原因是什么？

### 回答

这个问题的回答极有可能是否定的，但是，如果你曾经有一次被要求回家的经历，无论是因为你病得太无法工作、心情不好还是不听从，请尝试用一种方式来组织语言，你理解了其中的原因，并在此后一直致力于改进。

### 示例

我曾只被叫回家过一次，那是因为我生病很严重，持续了几乎整整一周。我请了两假，工作进度也落后了。第三天我觉得身体状况已经可以上班了，不想再继续落后了。我没有发烧，感觉状态可以应付工作，于是就去了。但过了几个小时后，我立刻感到精疲力竭、疲惫，显然我的状况并没有我想象中那么好。老板问我到达那里时是否确定自己没问题、可以上班，我回答了定的。几个小时后，老板告诉我直接回家吧，因为我感到头脑充血且虚弱，注意力变得越来越难以集中。我回家了并很庆幸。我睡了一觉，第二天回了公司。现在我更擅长先照顾好自己，确保身体状态良好后再上班，因为健康第一。

## 365. 你的考勤记录如何？

### 回答

请务必诚实地回答这个问题，但理想情况下，你已经付出了努力，证明你很少缺勤或迟到。然而，如果你的考勤记录存在空缺，请简要说明原因，并务必强调你对工作的投入和可靠性。

### 示例

我的考勤记录非常不错。我不能说自己是完美出勤，因为我毕竟人，曾生过几次病导致需要请病假，或者有一些特定的预约只能在我工作的时间段内进行。除此之外，我每天都会准时打卡上班，表现非常如一。在极少数迟到几分钟的情况下，我会确保通知所有人并告知老板，随后会在老板的许可下，在午休时间或下班前把时间补回来。

## 366. 你是在哪里获知这个职位的？

### 回答

这看起来像是一个简单的问题，但答案实际上能反映很多关于你的信息。如果你是由朋友或公司的其他员工推荐的，这是一个提及你人脉关系的绝佳机会（如果那人的表现良好的话！）。然而，如果你是从招聘会或工作中介机构等地方听说的，你可能希望关注自己对发现这样一个绝佳机会感到多么高兴。

### 示例

我是通过朋友发给我的信息得知这个职位的。她觉得它看起来很有趣，并且对这家公司评价很高。通常我不太在意职位招聘广告，但当我读到这则广告时，我感到非常兴奋和感兴趣，不想错过这次申请机会。

## 367. 在做用人决策时，还有什么你想让我知道的吗？

### 回答

这是一个向面试官对自己进行最后“自我推销”的绝佳机会——利用这段时间提醒面试官你为什么胜任该职位，以及你能够能为公司带来什么其他人无法提供的价值。表达你对有机会加入一家追求 X 使命公司的兴奋之情。

### 示例

如果你聘用我，你不会失望的。我对这个机会感到非常兴奋，并渴望帮助贵公司成长。我的技能和经验似乎与职位完美匹配。我对加入团队的前景感到兴奋，并期待看到我如何像贵公司的使命所说的那样，“为社区带来解决方案”！

# 索引

## 核心 Java 面试题

## 第 1 部分：核心 Java

### OOP 概念

- 001. 解释方法重载（method overloading）和方法重写（method overriding）。
- 002. 解释 OOP 的益处。
- 003. 编写一个演示封装（encapsulation）的代码片段。
- 004. 继承关系的类型有哪些？
- 005. 声明实例变量的最佳实践是什么？
- 006. 什么是单例类（singleton class）？
- 007. 解释编译以下代码时会发生什么，并说明它使用的是方法重载还是重写。
- 008. 编写一个演示方法重载的 Java 代码示例。
- 009. 什么是多态（polymorphism）？Java 如何支持多态？
- 010. 解释 Java 如何实现抽象（abstraction）。

### Java 基础

- 011. 声明 Java 主方法的可能方式有哪些？
- 012. 声明 Java 类的可能方式有哪些？
- 013. 你如何定义标识符（Identifier）？
- 014. 哪些修饰符不能指定给实例变量？
- 015. 方法声明可以指定哪些修饰符？
- 016. 引用变量在未显式初始化时的默认值是什么？你在代码中如何处理这种情况？
- 017. 解释关键字“transient”和“native”。
- 018. Java 中的注释是什么？解释 Java 支持的注释类型。
- 019. 解释什么是 JVM、JRE 和 JDK。
- 020. 通过代码示例解释你将如何读取用户输入的值。

### 数据类型、变量和数组

- 021. 声明 short 类型数组的可能方式有哪些？
- 022. 你如何显式地将 int 变量转换为 byte？真的有必要将 int 字面量（int literal）转换为 byte 吗？
- 023. 给出一个隐式类型转换（implicit casting）的例子。
- 024. 编写一个代码片段，演示如何将 float 变量赋值给 short 变量。
- 025. float 的默认值是什么？
- 026. 代码片段中哪些行可以编译的？
- 027. 编译以下代码时会发生什么？
- 028. 初始化数组的正确方式是什么？
- 029. 解释基本数据类型（primitive types）。
- 030. 将十进制赋值给 float 的方式有哪些？
- 031. 识别代码片段中的错误并解释如何修复。
- 032. 如何将八进制（Octal）和十六进制（Hexadecimal）字面量赋值给 int？
- 033. 下列代码中哪些行可以编译，哪些会导致错误？
- 034. 编译以下代码时会发生什么？
- 035. 考虑以下片段的输出。

### 运算符

- 036. 代码片段中哪些行会导致错误？
- 037. 以下代码的输出是什么？
- 038. 通过代码示例解释字符串拼接的运算符。
- 039. 以下代码的输出是什么？
- 040. 解释`%`运算符。
- 041. 以下代码的输出是什么？
- 042. 编译执行以下代码时会发生什么？
- 043. 下面代码可以编译吗？如果是，输出是什么？
- 044. 以下代码的输出是什么？

### 控制语句

- 050. 列出 Java 中使用的决策语句。
- 051. Java 中的循环结构有哪些？
- 052. 用示例解释 if–else 语句的语法。
- 053. 以下代码中哪些行可以编译，哪些会导致错误？
- 054. 如果`boolA`为假且`boolB`为真，输出将会是什么？
- 055. 以下程序的输出是什么？
- 056. 执行以下代码时会发生什么？如果可以编译，输出是什么？
- 057. `break`和`continue`语句的作用是什么？
- 058. 编译执行以下代码时会发生什么？输出是什么？
- 059. 编译执行以下代码时会发生什么？输出是什么？
- 060. 编译执行以下代码时会发生什么？输出是什么？
- 061. 编译并执行以下代码时会发生什么？输出是什么？
- 062. 给出一些“for-each”循环的示例。
- 063. 下面代码的输出是什么？
- 064. 执行以下代码时会发生什么？如果编译通过，输出是什么？

### 类与方法

- 065. 考虑以下代码片段：

  当这段代码被编译并执行时，输出会是什么？

- 066. 实例变量可以声明为`static`吗？请解释。
- 067. 解释以下代码在编译并执行时会发生什么。
- 068. 如果没有显式指定构造函数，后台会发生什么？
- 069. 解释编译以下代码时会发生什么。
- 070. 构造函数可能的访问修饰符有哪些？
- 071. 下面代码片段的输出是什么？
- 072. 你将如何定义构造函数？给出一个示例。
- 073. 用代码示例解释`void`关键字。
- 074. 解释构造函数和普通方法之间的区别。
- 075. 用代码示例解释`this`关键字。
- 076. 解释类和对象之间的区别。
- 077. 用代码示例解释`new`关键字。
- 078. 下面代码片段的输出是什么？
- 079. 用代码示例解释`return`关键字。

### 内部类



# 080. 什么是内部类？内部类的不同类型有哪些？

# 081. 编写一个代码示例，演示如何从外部类实例化内部类。

# 082. 编写一个代码示例，演示一个内部类。

# 083. 什么是“方法局部”内部类。

# 084. 用代码示例解释静态嵌套类。

# 085. 用代码示例解释如何实例化静态嵌套类。

## 继承

# 086. 给出一个非法的方法重写示例。

# 087. 解释 `super` 关键字。

# 088. 下面代码片段有一个错误。找出它并说明原因。

# 089. 编写一个代码示例，演示继承如何帮助代码重用。

# 090. 编写一个 Java 代码示例，演示方法重写。

# 091. 用代码示例解释 `extends` 关键字。

# 092. 下面代码片段的输出是什么？

# 093. 解释下面代码片段的输出是什么：

# 094. 下面代码片段的输出是什么？

# 095. 解释下面代码片段存在什么问题：

# 096. 什么是是动态方法派发？

# 097. 以下代码有效吗？请解释。

# 098. 为什么 Java 不支持多继承？

# 099. 用代码示例解释如何防止方法不被重写。

# 100. 下面代码有一个错误。找出它并说明如何修复它。

## 抽象类与接口

# 101. 声明接口的可能方式有哪些？

# 102. 用代码示例解释抽象类。

# 103. 用代码示例解释如何实现接口。

# 104. 下面代码片段有效吗？请从两种方式解释原因。

# 105. 类可以实现两个接口吗？如果两个接口都有同名方法，会发生什么？

# 106. 抽象类的作用是什么？

# 107. 解释下面代码片段存在什么问题：

# 108. 下面代码片段有效吗？请从两种方式解释原因。

# 109. 下面代码中的哪些行会导致编译错误？

# 110. 下面代码片段有效吗？请解释。

## 包与访问控制

# 111. 什么是包？包的优点是什么？

# 112. 解释 Java 访问修饰符。

# 113. 用代码示例解释如何创建包。

# 114. 列出 JDK 中的一些默认包，并简要说明它们的作用。

# 115. 以下代码有效吗？请解释原因。

# 116. 解释 `import` 关键字。

# 117. 解释 `protected` 和 `default` 访问修饰符之间的区别。

# 118. 下面代码片段有效吗？请解释。

# 119. 解释编译并执行以下代码时会发生什么。

# 120. 解释 `java.lang` 包。

## 异常处理

# 121. 解释 Java 中的 `throw`、`throws` 和 `Throwable`。

# 122. 编译并执行以下代码时，输出是什么？

# 123. 编写一个演示 `try/catch/finally` 块的代码示例：

# 124. 执行以下代码的输出是什么？

# 125. 解释 Java 中的 `try–catch–finally` 语句。

# 126. 下面代码片段的输出是什么？

# 127. 假设你有一个名为 `myMethod` 的方法，它可以抛出受检异常（checked Exception）。你如何在代码中处理它？

# 128. `finally` 子句的作用是什么？给出一个示例。

# 129. 解释 Error 和 Exception 的区别。

# 130. 什么是 RuntimeException。

## 字符串处理

# 131. 什么是字符串字面量（string literal）？给出一个示例。

# 132. 以下代码的输出是什么？请解释。

# 133. 执行以下代码的输出是什么？

# 134. 下面代码片段的输出是什么？

# 135. 如何将字符串字面量赋值给变量？

# 136. String 类的一些常用方法有哪些。

# 137. `StringBuffer` 和 `StringBuilder` 的区别是什么？

# 138. 使用循环演示如何反转字符串。

# 139. 写一个代码示例演示如何将字符串转换为大写。

# 140. 如何将 Integer 字符串。

## 泛型

# 141. 编译并执行以下代码时会发生什么？

# 142. 以下代码有效吗？如果不是，说明原因。

# 143. 解释以下代码中的问题。

# 144. 需要什么额外的代码才能使其有效？

# 145. 用代码示例解释边界泛型。

## 集合

# 146. 集合框架中的四个主要接口是什么？

# 147. 如何在数组中搜索特定元素？

# 148. 如果你不想要重复且不在顺序，你会选择哪种集合？

# 149. 用代码示例演示可以伸缩大小并提供索引的集合。

# 150. 解释 `Queue` 接口。

# 151. 解释 `Comparator` 接口。

# 152. 集合接口的一些方法有哪些？

# 153. 是否可以混合泛型和非泛型集合？如果是，请给出示例。

# 154. 集合接口的一些重要方法有哪些？

## 枚举、自动装箱与包装类

# 155. Java 中有哪些包装类？

# 156. 编译并执行以下代码时，输出是什么？

# 157. 解释如何将字符串“100.55”转换为 Double 以及将 Double 100.55 转换为 String。

# 158. 以下代码的输出是什么？

# 159. 什么是包装类？包装类对象有哪些特殊属性？

# 160. 用示例解释自动装箱。

## 线程

# 161. 如何在 Java 中创建线程？

# 162. 解释线程的不同类型。

# 163. 可以直接调用 `run` 方法而不是调用 `start` 方法吗？

# 164. 执行以下代码时后台发生了什么？

# 165. Thread 类的一些主要方法。

# 166. 解释线程状态。

# 167. 编写一个使用 `Thread` 类创建线程的代码示例。

# 168. 编写一个使用 `Runnable` 接口创建线程的代码示例。

# 169. Java 中可以创建多个线程吗？如果是，线程之间如何通信？

# 170. 什么是同步（Synchronization）？

# 171. 执行以下代码时会发生什么？

# 172. 考虑以下代码：

首先打印“Thread 1”1000 次，然后打印“Thread 2”1000 次。如果这是错误的，请解释原因。

# 176. 执行以下代码会发生什么？

# 177. 编写一个代码示例，在 `/usr/test.txt` 路径下创建一个文件。

# 178. 用代码示例解释 `FileWriter` 类。

# 179. 编写一个代码片段，使用 `FileReader` 读取 `/usr/Java.txt` 文件中的内容并在控制台中显示输出。

# 180. 用代码示例解释如何在文件系统上创建目录。

# 181. 解释编译并执行以下代码时会发生什么。

# 182. 编写一个代码示例来演示 `PrintWriter` 类。

# 183. 编写一个代码示例来演示如何删除文件。

# 184. 编写一个代码示例来演示如何重命名文件或目录。

# 185. 哪些类被用于对象的序列化和反序列化？

# 186. 解释 `File` 类中的一些重要方法。

## 杂项

# 187. 解释编译以下代码片段时会发生什么。

# 188. 解释编译并执行以下代码时会发生什么。

# 189. 解释对称的 `equals()` 约。

# 190. 以下哪些语句是无效的？为什么？

# 191. `transient` 关键字的作用是什么？

# 192. Java 中的垃圾回收（Garbage Collection）是什么？

# 193. 内存的哪部分用于垃圾回收？JVM 使用什么种算法进行垃圾回收？

# 194. 垃圾回收何时发生？

# 195. 需要编写什么代码来触发垃圾回收？

# 196. 用代码示例解释对象如何成为垃圾回收的对象。

# 第 2 节 – Java 8

## 函数式接口

# 197. 什么是函数式接口？如何创建一个函数式接口？

# 198. 解释 `java.util.Function` 包。

# 199. 用代码示例解释 `java.util.function.Consumer` 接口。

# 200. 解释 `Supplier` 和 `Consumer` 接口之间的区别。

# 201. 以下代码片段的输出是什么？

# 202. 使用哪种内置函数式接口可以将 `String` 转换为大写？

# 203. 下代码有效吗？解释。

# 204. 列举一些在 Java 8 中变为函数式接口的 Java 8 之前的接口。

# 205. 为什么 Java 8 增加了内置函数式接口的如 `IntSupplier`、`BooleanSupplier` 等原始基类型特化？

# 206. 内置函数式接口通常在哪里使用？

## Lambda 表达式

# 207. 什么是 Lambda 表达式？使用 Lambda 表达式有什么好处？

# 208. Lambda 表达式和函数式接口之间有什么关系？

# 209. 解释 Lambda 表达式的语法。

# 210. 给一些 Lambda 表达式的示例。

# 211. 编写一个代码示例，创建一个函数式接口并使用 Lambda 表达式实现它。

# 212. 用代码示例解释如何使用不同的 Lambda 表达式对同一个函数式接口进行不同的实现。

# 213. 识别以下 Lambda 表达式中的错误以及如何修复它。

# 214. 以下代码有效吗？解释。

# 215. 为以下 Lambda 表达式编写一个可以工作的函数式接口。

# 216. 解释如何使用 Lambda 表达式创建一个新线程。

## 流处理（Streams）

# 217. 解释创建 Stream 的不同方式。

# 218. 用代码示例解释 Stream 的 `filter` 操作。

# 219. 解释 Stream 操作类型。

# 220. 什么是并行流（parallel stream）？用代码示例解释如何创建一个并行流。

# 221. 如何将 Stream 转换回 Collection？

# 222. 以下代码片段的输出是什么？

# 223. Stream 和 Collection 之间的区别是什么？

# 224. 假设你有一个包含 `String` 值的 `List`。你想创建一个新的 `List`，消除原始列表中重复项并将 `String` 值转换为大写。你将如何通过 Stream 操作实现这一点？

# 225. 是否可以将数组转换为 Stream？解释。

# 226. 假设你有一个如下 `Employee` 类：并且假设你有一个如下 `Employee` 对象的 `List`：如何使用 Streams 创建一个根据 `Employee` 薪水排序的新 `List`？

## 方法引用（Method References）

# 227. 什么是方法引用？方法引用的好处是什么？

# 228. 方法引用的不同类型有哪些？

# 229. 给出一个静态方法引用的示例。

# 230. 考虑以下 `Shape` 类：为了使以下代码有效，该类需要进行哪些更改？

# 231. 解释 `String::toUpperCase` 是什么类型的方法引用。

## 日期与时间 API（DateTime API）

# 232. 解释以下代码片段中的错误以及你如何修复它。

# 233. 用适当的代码示例解释创建 `LocalDate` 的不同方式。

# 234. 用代码示例解释如何检查一个日期是否在另一个日期之前。

# 235. 解释以下代码中的错误。

# 236. （注：此处原文编号重复或逻辑对应后续 DateTime API 翻译）

# 237. 解释如何检查日期是否在另一个日期之前。

# 238. 解释以下代码中的错误以及如何修复它。

# 239. 解释创建 `LocalDate` 的不同方式。

# 240. 解释日期检查方法。

# 241. 解释以下代码中的错误以及如何修复它。

# 242. 解释创建 `LocalDate` 的不同方式。

# 243. 解释日期检查方法。

# 244. 解释以下代码中的错误以及如何修复它。

# 245. 解释创建 `LocalDate` 的不同方式。

# 246. 解释日期检查方法。

# 247. 解释以下代码中的错误以及如何修复它。

# 248. 解释创建 `LocalDate` 的不同方式。

# 249. 解释日期检查方法。

# 250. 解释以下代码中的错误以及如何修复它。

# 251. 解释创建 `LocalDate` 的不同方式。

# 252. 解释日期检查方法。

# 253. 解释以下代码中的错误以及如何修复它。

# 254. 解释创建 `LocalDate` 的不同方式。

# 255. 解释日期检查方法。

# 256. 解释以下代码中的错误以及如何修复它。

# 257. 解释创建 `LocalDate` 的不同方式。

# 258. 解释日期检查方法。

# 259. 解释以下代码中的错误以及如何修复它。

# 260. 解释方法之间的关系。

## 静态与默认方法（Static and Default Methods）

# 261. 静态方法是什么？

# 262. 用代码示例解释。

# 263. 默认方法是什么？

# 264. 用代码示例解释。

# 265. 识别以下 Lambda 表达式中的错误以及如何修复它。

## 可容器（Optionals）

# 266. 什么是 Optional？

# 267. 如何使用？

# 268. 什么是？

# 269. 用代码示例解释。

## 集合改进（Collection Improvements）

# 270. 什么是？

# 271. 用代码示例解释。

## 杂项（Miscellaneous）

# 272. 什么是？

# 273. 用代码示例解释。

# 274. 什么是？

# 275. 解释之间的关系。

# 第 3 节 – Java 9

## 模块（Modules）

# 276. 什么是模块？

# 277. 模块有什么用？

# 278. 模块之间的区别是什么？

# 279. JDK 做了哪些更改？

# 280. 为了将此代码作为模块部署，需要做什么？

## 流/集合改进（Stream/Collection Improvements）

# 281. 什么是？

# 282. 以下代码有效吗？如果不是，可以如何修复？

# 283. 识别代码片段中的问题并解释如何修复。

# 284. 使用哪种 Java 9 方法可以创建一个包含 `String` 值的 `Set`？

## 杂项（Miscellaneous）

# 285. 以下代码片段的输出是什么？

# 286. Java 9 对接口 做了哪些更改？为什么？

# 287. 什么是？

# 288. 以下代码片段的输出是什么？

# 289. 什么是？

# 场景题（Scenario Based Questions）

# 290. 假设你通过扩展 `Thread` 类创建一个新线程并多次调用 `start` 方法。你认为会发生什么？

# 291. 假设你有一个返回整数值的方法。代码位于 `try/catch/finally` 块中。try、catch 和 finally 块中都有返回语句。try 块中的返回语句返回 1，catch 块中的返回语句返回 -1，而 finally 块中的返回语句返回

# 283. 假设你在基类（Base）中有一个静态方法。假设你在子类中有一个同名方法。假设你创建一个基类对象，并给它赋值一个子类对象的引用，然后调用该静态方法。这样做有效吗？如果，调用的是哪个版本的静态方法？

# 284. 假设你在基类中有一个会抛出 `ArrayOutOfBoundsException` 的方法。假设该方法在子类中被重写，并声明它抛出 `RuntimeException`。你认为会发生什么？

# 285. 假设你有一个对象列表 `List`。你想将其作为参数发送给客户端应用程序，但想确保客户端应用程序不对其进行修改。你如何实现这一点？

# 286. 假设你正在从数据库读取 10000 个 `String` 值。你需要创建一个包含这些值的拼接 `String`。实现这一目标最有效的方法是什么？

# 287. 假设你正在开发一个涉及大量大数字数学计算的应用。在精度非常重要的情况下，你会使用哪种数据类型来定义变量？

# 288. 假设你正在处理一个多线程应用程序。现在有一个新需求，你需要存储键值对。在这种情况下，最合适的 `Collection`（集合）是哪个？

# 289. 假设你需要在应用程序中创建一些工具方法。创建此类方法的最佳实践是什么？你会把它们放在哪里？

# 290. 假设你作为 API 的一部分开发了一个名为 `FileWriter` 的接口。它有一个 `writeToCsv` 文件方法，可以将传入的内容写入 CSV 文件。该 API 由不同的应用程序实现，这些程序为 `FileWriter` 接口提供了实现。现在，假设你需要在接口中添加一个新方法 `writeToExcel`，将传入的内容写入 Excel 文件。你如何进行这一更改，以对对 API 用户产生的影响降至最低？

# 第 4 节 – 人力资源

## 创造力

# 291. 你在哪里寻找灵感？

# 292. 你在工作中如何实现创造力？

# 293. 你如何激励他人创造点子？

# 294. 请描述一下你的创造力。

## 领导力

# 295. 在工作中，你更倾向于获得更多的权力还是更多的责任？

# 296. 当小组中的有人没有做出应有的贡献时，你会怎么办？

# 297. 请讲述一次你做过超出权限范围决定的经历。

# 298. 你在向主管反映纠纷时感到自在吗？

# 299. 如果你在上一份工作中担任负责人，你会做哪些不不同的改变？

# 300. 你认为雇主应该对工作表现良好的员工给予表扬或奖励吗？

# 301. 你认为领导者具备最重要的特质是什么？

# 302. 请讲述一次出现不可预见问题的经历。你是如何处理的？

# 303. 你能给我举一个例子，说明你在上一份工作中是如何改进某个 X 目标的吗？

# 304. 请讲述一次主管对某个项目没有提供足够具体的指导的经历。

# 305. 请讲述一次你负责领导某一个项目的经历。



# 面试问题列表

## 行为面试问题

- 306. 请讲述一次你向前雇主提出的建议且该建议后来被实施的经历。
- 307. 请讲述一次你发现工作中的某件事可以更高效完成的经历。
- 308. 领导和管理人员之间有区别吗——哪一个是你的更大强项？
- 309. 你在领导角色中表现得更好，还是作为团队成员表现得更好？
- 310. 请讲述一次你在工作中发现某些影响你（或他人）生产力的经历——你是如何处理的？
- 311. 在一个有明确目标和目标的工作中，你表现如何？
- 312. 在一个拥有很大决策权的工作中，你表现如何？
- 313. 如果你看到其他员工做出不诚实或违反伦理的事情，你会怎么办？
- 314. 请讲述一次你自学并对工作有帮助的知识经历。
- 315. 请讲述一次你开发某个项目的经历。
- 316. 请讲述一次你接手某个项目的经历。
- 317. 请讲述一次你准时完成期限的经历。
- 318. 请讲述一次你准时完成期限的经历。
- 319. 请讲述一次你解决问题的经历。
- 320. 请讲述一次你解决问题的经历。
- 321. 请讲述一次你同时处理多个项目的经历。
- 322. 请讲述一次你同时处理多个项目的经历。
- 323. 请讲述一次你同时处理多个项目的经历。
- 324. 请讲述一次你解决问题的经历。
- 325. 请讲述一次你感到压力巨大的经历。
- 326. 请讲述一次你感到压力巨大的经历。
- 327. 请讲述一次你感到压力巨大的经历。
- 328. 请讲述一次你兼顾多任务的经历。
- 329. 请讲述一次你兼顾多任务的经历。
- 330. 请讲述一次你兼顾多任务的经历。
- 331. 请讲述一次你帮助客户的经历。
- 332. 请讲述一次你为客户额外付出的经历。
- 333. 请讲述你如何处理客户问题。
- 334. 请讲述一次客户不不满的经历。
- 335. 请讲述一次你帮助客户的经历。
- 336. 请讲述一次你帮助客户的经历。
- 337. 请讲述一次你帮助客户的经历。
- 338. 请讲述一次你帮助客户的经历。
- 339. 请讲述一次你传达困难想法的经历。
- 340. 请讲述一次你发现沟通困难的经历。
- 341. 请讲述一次你传达问题的经历。
- 342. 请讲述一次你通过沟通解决问题的经历。
- 343. 请讲述一次你与同事发生纠纷的经历。
- 344. 请讲述一次你与同事发生纠纷的经历。
- 345. 请讲述一次你与建立人际关系的经历。
- 346. 请讲述一次你说服他人承担困难任务的经历。
- 347. 请讲述一次你成功说服群体接受你的建议的经历。
- 348. 请讲述一次你调解员工冲突的经历。
- 349. 请讲述一次你处理办公室政治的经历。

## 求职与日程安排

- 350. 你寻找的最重要的三件事是什么？
- 351. 你是如何评估你想要加入公司的？
- 352. 你对 [amount] 的薪资感到满意吗？
- 353. 你为什么选择上一份工作？
- 354. 你离开上一份工作有多久了？原因是什么？
- 355. 你在寻找哪些类型的职位？
- 356. 你在工作中受过纪律处分？
- 357. 你的时间安排如何？
- 358. 我们可以联系你目前的雇主吗？
- 359. 你是否有可以为公司提供的宝贵人脉？
- 360. 你多久可以开始工作？
- 361. 你的前雇主会说你离开的原因是什么？
- 362. 你积极寻找工作多久了？
- 363. 你什么时候不会来上班？
- 364. 你是否曾被主管要求当天下班？如果是，为什么？
- 365. 你的考勤记录如何？
- 366. 你是从哪里听说这个职位的？
- 367. 在做录用决策时，还有什么我应该知道的？

# 以下标题可能对你有所帮助

- 1. 你可能被问到的 NET 面试题
- 2. 你可能被问到的 Access VBA 编程面试题
- 3. 你可能被问到的管理员与帮助桌面面试题
- 4. 你可能被问到的 Adobe ColdFusion 面试题
- 5. 你可能被问到的高级 C++面试题
- 6. 你可能被问到的高级 Excel 面试题
- 7. 你可能被问到的高级 JAVA 面试题
- 8. 你可能被问到的高级 SAS 面试题
- 9. 你可能被问到的 AJAX面试题
- 10. 你可能被问到的算法面试题
- 11. 你可能被问到的 Android 开发面试题
- 12. 你可能被问到的 Ant & Maven 面试题
- 13. 你可能被问到的 Apache Web 服务器面试题
- 14. 你可能被问到的人工智能面试题
- 15. 你可能被问到的 ASP.NET 面试题
- 16. 你可能被问到的自动化软件测试面试题
- 17. 你可能被问到的 Base SAS 面试题
- 18. 你可能被问到的 BEA WebLogic 服务器面试题
- 19. 你可能被问到的 C & C++ 面试题
- 20. 你可能被问到的 C# 面试题
- 21. 你可能被问到的 CCNA 面试题
- 22. 你可能被问到的云计算面试题
- 23. 你可能被问到的计算机架构面试题
- 24. 你可能被问到的计算机网络面试题
- 25. 你可能被问到的 Core Java 面试题
- 26. 你可能被问到的数据结构与算法面试题
- 27. 你可能被问到的 EJB 3.0 面试题
- 28. 你可能被问到的 Entity Framework 面试题
- 29. 你可能被问到的 Fedora & RHEL 面试题
- 30. 你可能被问到的 Hadoop 大数据面试题
- 31. 你可能被问到的 Hibernate, Spring & Struts 面试题
- 32. 你可能被问到的 HR 面试题
- 33. 你可能被问到的 HTML, XHTML 和 CSS 面试题
- 34. 你可能被问到的 HTML5 面试题
- 35. 你可能被问到的 IBM WebSphere 应用服务器面试题
- 36. 你可能被问到的创新面试题
- 37. 你可能被问到的 iOS SDK 面试题
- 38. 你可能被问到的 Java / J2EE 设计模式面试题
- 39. 你可能被问到的 Java / J2EE 脚本面试题
- 40. 你可能被问到的 JavaScript面试题
- 41. 你可能被问到的 JavaServer Faces 面试题
- 42. 你可能被问到的 JDBC 面试题
- 43. 你可能被问到的 jQuery面试题
- 44. 你可能被问到的 JSP-Servlet 面试题
- 45. 你可能被问到的 JUnit 面试题
- 46. 你可能被问到的领导力面试题
- 47. 你可能被问到的 Linux 面试题
- 48. 你可能被问到的 Linux 系统管理员面试题
- 49. 你可能被问到的 Mac OS X Lion 面试题
- 50. 你可能被问到的 Mac OS X Snow Leopard 面试题
- 51. 你可能被问到的 Microsoft Access 面试题
- 52. 你可能被问到的 Microsoft Powerpoint面试题
- 53. 你可能被问到的 Microsoft Word面试题
- 54. 你可能被问到的 MySQL面试题
- 55. 你可能被问到的网络面试题
- 56. 你可能被问到的 OOPS面试题
- 57. 你可能被问到的操作系统面试题
- 58. 你可能被问到的 Oracle 数据库管理面试题
- 59. 你可能被问到的 Oracle E-Business Suite 面试题
- 60. 你可能被问到的 ORACLE PL/SQL 面试题
- 61. 你可能被问到的 Perl 编程面试题
- 62. 你可能被问到的 PHP面试题
- 63. 你可能被问到的 Python面试题
- 64. 你可能被问到的 RESTful JAVA Web 服务面试题
- 65. 你可能被问到的 SAP HANA 面试题
- 66. 你可能被问到的 SAS 编程指南面试题
- 67. 你可能被问到的 Selenium 测试工具面试题
- 68. 你可能被问到的 Silverlight面试题
- 69. 你可能被问到的软件仓库面试题
- 70. 你可能被问到的软件测试面试题
- 71. 你可能被问到的 SQL Server面试题
- 72. 你可能被问到的 Tomcat面试题
- 73. 你可能被问到的 UML面试题
- 74. 你可能被问到的 Unix面试题
- 75. 你可能被问到的 Unix Shell 编程面试题
- 76. 你可能被问到的 Windows Server 2008 R2面试题
- 77. 你可能被问到的 XLXP, XSLT, XPath, XFORMS 及 XQuery面试题
- 78. 你可能被问到的 XML面试题

# 欲查看完整列表请访问

# www.vibrantpublishers.com

# 注意事项

# 你可能被问到的核心 Java 面试题

《Core Java Interview Questions You'll Most Likely Asked》第二版是当今竞争激烈的职场市场中脱颖而出的完美伴侣。

通过本指南，你将学习或复习面试所需的 Java 基础和原理，并熟悉真实的面试题以及获取解决方案的策略。简历编写教程和能力测试将帮助你在面试开始前就更好地展示自己。

这本书本身就是一门完整的课程，帮助你为理想的 Java 工作岗位做好准备。

# 书中包含内容？

- 详细解释 Java 基础知识的所有概念
- 290 道技术类（核心 Java）面试题
- 包含 Java 8 和 Java 9 问题
- 包含场景题
- 77 道 HR（行为面试）面试题
- 所有题目的策略与答案
- 符合 ATS 标准的简历编写教程（电子版格式）
- 2 份能力测试（可下载）

# 关于系列丛书

本书是“工作面试题”系列的一部分，该系列包含超过 75 本书籍，涵盖不同技术主题和 HR 面试相关话题的面试题。

www.vibrantpublishers.com
