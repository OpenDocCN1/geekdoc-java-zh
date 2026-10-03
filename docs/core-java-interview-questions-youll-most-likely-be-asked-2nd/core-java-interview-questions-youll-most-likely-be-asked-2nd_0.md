

# 最常遇到的 Core Java 面试题（第 2 版）

![](img/Cover.jpg)

![img](img/Cover.jpg)

在继续阅读面试问题和答案之前，请下载您的免费在线资源。

您的**免费在线资源**包括：

- 电子书，《编写一份令人印象深刻的符合 ATS 标准简历的终极指南》
- 能力测试

从下方的 URL 下载：

[`www.vibrantpublishers.com/product/core-java-interview-questions-youll-most-likely-be-asked/`](https://www.vibrantpublishers.com/product/core-java-interview-questions-youll-most-likely-be-asked/)

或者扫描下方的二维码：

![](img/1-1.jpg)

![](img/3-1.jpg)

本出版物旨在就涵盖的主题提供准确且权威的信息。作者在编写本书时已尽一切努力确保信息的准确性。然而，书中的信息按销售时不提供任何明示或暗示的保证。作者或出版者对本书直接或间接引起或造成的任何损害不承担责任。

Vibrant Publishers 的书籍适用于促销或企业培训计划提供特殊批量折扣。欲了解更多信息，请邮件至 `bulkorders@vibrantpublishers.com`。

请将反馈/更正（技术、语法或拼写）邮件发送至 `spellerrors@vibrantpublishers.com`。

欲访问 Vibrant Publishers 的完整目录，请访问 [`www.vibrantpublishers.com`](http://www.vibrantpublishers.com)。

# 专家对这本书的评价！

随着技术的快速变化，IT 专业人员需要根据最新的技术趋势不断更新自己的资质。新版《你最可能被问到的核心 Java 面试题》是 Java 程序员和开发者提升面试技能、建立 IT 职业完美伴侣。除了标准的 Java 问答外，此版本还包含了关于 Java 8 函数式接口和 lambda 表达式以及 Java 9 模块和流的问题。人力资源问答将帮助 IT 专业人员胜任面试并给雇主留下深刻印象。通过基于真实生活场景的问题，本书为职场人士在当今竞争激烈的就业市场中制定策略和脱颖而出提供了简洁信息。

– **David Han**

德克萨斯大学圣安东奥分校管理科学与统计学博士副教授

我与学生密切接触，特别是在他们的就业方面。这本书将真正帮助学生准备和练习面试题。毫无疑问，这将是求职者的真实指南。索引设计良好且易于理解。书中包含了几乎所有可能的变化。难度程度从易到难，适用于各种 Java 相关的工作。

– **Yogesh Jadhav**

Sinhgad Institutes 教授兼培训与就业官

优秀的问卷列表。Vibrant Publishers 出版的《核心 Java 面试题》对于 Java 技术人员的求职者来说将非常有用。它还包含了 HR 问题。许多求职者对 HR 面试并不清楚，所以书中包含 HR 问题非常不错。这本书将对寻找 Java 工作的应届生和初级求职者有很大帮助。我的最终评价是，它对于寻找跨国公司职位的新人和经验丰富的者非常有帮助。

– **Shashikanth K**

CSE 系就业协调员兼副教授

我非常喜欢书中触及了 Java 的每一个部分。此外，详细的解释配合代码片段示例使它更加清晰、更易于理解。

– **Barkat Amirali Jiwani**

Vaagdevi 工程学院助理教授/就业负责人

# 本书贡献者

![](img/7-1.jpg)

**Reshma Bidikar** 是一位充满激情的 Java 工程师和教育者。在 IT 行业拥有超过 16 年高级 Java 开发人员/架构师经验，从事过 Core Java、Spring、Spring Boot、Hibernate、REST、JDBC 等技术。她是一位专家 Java 培训师/Java 作者，她的 Java 文章/教程/课程已帮助了全球数千名学生/读者。她擅长将其丰富的 Java 知识与其用易懂的语言解释复杂概念的能力相结合。她拥有计算机科学工程学位。工作之余，她还是一个热心的读者和博客爱好者。

- 02. Java 基础
- 03. 数据类型
- 04. 运算符
- 05. 控制语句
- 06. 类
- 07. 内部类
- 08. 继承
- 09. 抽象类与接口
- 10. 包控制
- 11. 异常处理
- 12. 字符串处理
- 13. 泛型
- 14. 集合
- 15. 枚举类与装箱类
- 16. 多线程
- 17. Java IO
- 18. 其他
- 01. 函数式接口
- 02. Lambda 表达式
- 03. 流
- 04. 方法引用
- 05. 日期时间 API
- 06. 静态和默认接口方法
- 07. `Optional`
- 08. 集合增强
- 09. 其他
- 01. 模块
- 02. 流/集合增强
- 03. 其他
- 04. 场景题
- 01. 创意
- 02. 领导力
- 03. 截止日期与时间管理
- 04. 客户服务
- 05. 沟通
- 06. 找工作与安排
- 索引

## Java 9

## 人力资源

### 001. 解释方法重载和方法重写。

**答案：**

方法重载（Method overloading）发生在一个类中存在两个或多个名称相同但参数数量或类型不同的方法时。以下代码演示了这一点：

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
}
```

```java
public class Animal {
    public void saySomething() {
        System.out.println("I am an animal");
    }
}

public class Dog extends Animal {
    public void saySomething() {
        System.out.println("I am a dog");
    }
}
```

**答案：**

以下是 OOP 的优点：

- **可扩展性：** 使用`继承（Inheritance）`等 OOP 原则编写的代码具有扩展性。
- **安全性：** 像`封装（encapsulation）`等 OOP 原则有助于将数据和操作数据的代码结合在一起，并使代码安全。
- **简单性：** `Java` 类代表现实世界的对象。这使得代码非常易于理解。
- **可维护性：** 使用 OOP 原则编写的代码更容易维护。

**答案：**

封装（Encapsulation）是指将数据和操作数据的代码组合在一个单元中。只需创建一个带有 `private` 字段和 `public` getter/setter 方法的类就是封装的一个示例。以下代码片段演示了这一点：

```java
public class Laptop {
    private String memory;

    public String getMemory() {
        return memory;
    }

    public String setMemory(String newMemory) {
        memory = newMemory;
    }
}
```

在这里，有一个名为 `Laptop` 的类。它有一个名为 `memory` 的 `private` 字段以及用于访问/修改 `memory` 字段的 `public` getter 和 setter 方法。因此，类外部无法直接访问 `memory` 字段，只能通过它的 getter/setter 方法访问。

**答案：**

继承关系规定了代码如何被重用。继承关系有两种类型。

它们如下：

- **IS–A（继承关系）**

  `IS–A` 关系通过继承实现，即通过创建子类来实现。假设 `Camera` 是子类，而 `Electronics` 是父类。在这种情况下，我们可以说 `Camera` 是一个 `Electronic`（电子）产品。

- **HAS–A（包含关系）**

  `HAS–A` 关系可以通过`组合（composition）`创建，即通过创建一个对应另一个类的字段。假设在 `Camera` 类内部，有一个名为 `Battery` 的对象。在这种情况下，我们可以说 `Camera` 包含一个名为 `Battery` 的对象。

**答案：**

实例变量应该始终声明为 `private`。它们应该拥有 `public` getter/setter 方法。这有助于保护实例变量，因为它们只能在程序员的控制下被修改。这符合`封装（Encapsulation）`原则。

将实例变量声明为 `public` 违反了封装原则并会带来安全问题。`public` 实例变量可以在你的类外部被恶意修改。如果确实需要从子类访问实例变量，可以将其设置为 `protected`。

### 006. 什么是单例类？

**答案：**

在任何给定时间只允许你创建一个实例的类被称为`单例（Singleton）`类。单例类可以通过 `private` 构造函数和 `public` getter 方法来实现。以下代码演示了这一点。

```java
public class MySingleton {
    private static MySingleton mySingletonInstance;

    private MySingleton() {
    }

    public static MySingleton getInstance() {
        if (mySingletonInstance == null) {
            mySingletonInstance = new MySingleton(); // 只有在为空时才创建对象
        }
        return mySingletonInstance;
    }

    public void doSomething() {
        System.out.println("I am here....");
    }

    public static void main(String[] a) {
        MySingleton mySingleton = MySingleton.getInstance();
    }
}
```

在这里定义了一个 `private` 构造函数和一个 `public` 的 `getInstance()` 方法。`getInstance` 检查实例是否存在。如果实例不存在，则使用 `private` 构造函数创建一个。如果实例存在，则直接返回它。任何需要单例类实例的外部类都需要通过 `getInstance` 方法获取它。`getInstance` 方法确保了单例类只有一个实例。

### 007. 解释编译以下代码时会发生什么，并说明它使用了方法重载还是方法重写。

```java
class Electronics {
    public void displayPrice(Float price) {} // Line 1
}

class Camera extends Electronics {
    public void displayPrice(String price) {} // Line 2
}
```

上述代码可以编译。它使用了方法重载。`Camera` 类拥有相同的 `displayPrice` 方法，但两个类中的参数类型不同。

**答案：**

方法重载发生在类中存在多个名称相同但参数数量或类型不同的方法时。以下代码演示了这一点：

```java
class Laptop {
    public void displayPrice(int width, int height) {} // Line 1

    public void displayPrice(float width, float height) {} // Line 2
}
```

`Laptop` 类有两个名为 `displayPrice` 的方法。Line 1 的参数类型为 `int`，Line 2 的参数类型为 `float`。因此，这里的 `displayPrice` 方法被称为重载。

以下是声明 Java 类的可能方式：

```java
class Class1 {}
class Class2 {}
private class Class3 {}
protected class Class4 {}
static class Class5 {}
```

`Approach a` 将类声明为公共（public）。`Approach b` 没有使用任何访问修饰符，因此具有默认访问权限。它仅可以在包内访问。`Approaches c and d` 使用 `private` 和 `protected` 访问修饰符。注意，顶层类不能具有这些修饰符。这只能用于内部类。`Approach e` 使用 `static` 关键字。同样，只有内部类可以具有这种访问修饰符。

**答案：**

标识符是赋给类、方法、变量或接口的名字。Java 标识符有几条规则，如下：

- 标识符可以包含字母、数字、`$` 和 `_`。
- 标识符不能包含特殊字符。
- 标识符是区分大小写的。

下面显示了一些合法的标识符示例：

- `b`
- `$a`
- `book`
- `author1`
- `myName`
- `___1_c`

### 014. 哪些修饰符不能指定在实例变量上？

**答案：**

以下修饰符不能指定在实例变量上：

- `synchronized`
- `native`

`synchronized` 和 `native` 关键字仅对方法有效，不能指定在实例变量上。

- `void`：只能作为返回类型，当方法不返回任何值时。

### 015. 哪些修饰符可以指定用于方法声明？

**答案：**

以下关键字可以指定用于方法声明：

- `public`
- `private`
- `protected`

关键字 `public`、`private` 和 `protected` 是访问修饰符。它们指定了从哪里可以访问该方法。

- `final`：用于指示该方法不能被重写（override）。
- `abstract`：用于指定子类应该重写该方法。
- `native`：用于指定该方法是用另一种语言（如 `C++`）实现的。
- `synchronized`：用于指示该方法只能被一个线程访问。

**答案：**

当引用变量没有被显式初始化时，它的默认值为 `null`。如果不对这些变量进行妥善处理，可能会导致 `NullPointerException`。因此，为了避免 `NullPointerException`，你可以采取以下操作之一：

- 确保变量被正确初始化。
- 使用 Java 8 的 `Optionals`。

### 017. 解释关键字 `transient` 和 `native`。

**答案：**

`native` 关键字可以作为方法的修饰符。它指定该方法是用另一种语言（如 `C`、`C++`）实现的。

### 018. 什么是 Java 注释？解释 Java 支持的注释类型。

**答案：**

注释是添加到代码中的文本，提供了关于代码的额外信息。它向代码阅读者描述了代码的功能。编译器会忽略注释。Java 支持以下三种类型的注释：

- **单行注释（Single Line Comment）**：此类注释以两个斜杠（`//`）开头，并在行尾结束。下面的代码段演示了：

```java
// 这是单行注释
```

- **多行注释（Multi Line Comment）**：以 `/*` 开始，以 `*/` 结束。这两个之间的任何内容都被视为注释并被编译器忽略。下面的代码段演示了：

```java
/*
这是多行注释
*/
```

```java
for (int i = 0; i < 10; i++) {
}
```

- **文档注释（Documentation Comment）**：

```java
/**
 * 执行某些操作的方法
 * @param a
 */
```

### 019. 解释什么是 JVM、JRE 和 JDK。

**答案：**

`JDK` 代表 Java Development Kit（Java 开发包）。它包含编写和运行 Java 程序所需的工具和库。因此，它包含了 Java 编译器、`JRE` 以及其他工具。

`JRE` 代表 Java Runtime Environment（Java 运行时）。它包含运行 Java 程序所需的工具。它包含在 `JDK` 中，但也可以单独安装。如果只安装 `JRE` 而不安装 `JDK`，你能够运行 Java 程序，但无法编写和编译 Java 代码。`JRE` 包含了 `JVM` 和其他库。

`JVM` 代表 Java Virtual Machine（Java 虚拟机）。Java 代码被编译成字节码（byte code）。这些字节码在 `JVM` 内部执行。因此，`JVM` 只提供一个执行代码的环境。

**答案：**

Java 提供了一个名为 `java.util.Scanner` 的类。它可以用于从用户处读取输入。下面的代码演示了这一点：

```java
System.out.println("Enter a Number:");
Scanner scanner = new Scanner(System.in);
int num = scanner.nextInt();
System.out.println("The entered number is " + num);
scanner.close();
```




这段代码对应`System.in`创建了一个`Scanner`。它要求用户输入一个数字，并通过`nextInt()`将该数字读入变量`num`。正如`nextInt()`一样，`Scanner`类还有其他方法可以读取`String`、`float`、`long`等不同类型。

### 声明 short 数组有哪些可能的方式？

答案：

a. `short a1[];`

b. `short [] a2;`

c. `short b1[] [];`

d. `short [] [] b2;`

f. `short c2[] = {2,3,4};`

方法`a`和`b`声明单维`short`数组。方法`c`和`d`声明二维`short`数组。方法`e`和`f`声明单维`short`数组并对其初始化。在所有方法中，方括号都可以放在变量名之后，也可以放在`short`关键字之后。

### 22. 如何显式地将 int 变量转换为 byte？有必要将 int 字面量转换为 byte 吗？

`int`变量可以如下转换为`byte`：

```java
int i = 30;
```

因此，你需要在`int`变量之前指定`(byte)`关键字。是的，有必要显式地将`int`变量转换为`byte`，否则会发生如下编译错误：

```java
```

这是因为与`byte`相比，`int`是更宽的类型。因此，Java无法自动将`int`类型转换为`byte`，你需要指定显式转换。

### 举一个隐式转换的例子。

隐式转换发生在将值赋值给范围更宽的数据类型的变量时。在这种情况下，转换默认发生，不需要显式转换。例如，如果你将`int`值赋值给`long`值，就会发生隐式转换。下面的代码段演示了这一点：

```java
int iValue = 250;
long lValue = iValue;
```

上面的代码证明了`int`值始终可以赋值给`long`变量而无需转换，转换默认发生。

### 024. 编写一段代码片段，演示如何将 float 值赋值给 short 变量。

答案：

以下代码演示了如何将`float`值转换为`short`变量：

```java
float fValue = 37000.02F;
short sValue = (short) fValue;
```

在这里，在`float`变量`fValue`之前指定了关键字`short`，这被称为显式强制。由于`float`数据类型比`short`大，因此需要显式强制。

答案：

上述类型的默认值如下：

- `int = 0`
- `float = 0.0f`
- `boolean = false`
- `long = 0L`
- `char = 'u0000'`

### 026. 在以下代码片段中，解释哪些行可以正常编译，哪些行会导致编译错误。

```java
int [] [] add = new int [2] []; //Line 1
int [] subtract = new int [2]; //Line 2
int iValue = 2; //Line 3
add[1] = subtract; //Line 4
add[1] = iValue; //Line 5
```

答案：

`Line 1`正常编译，因为它创建了一个二维数组。`Line 2`正常编译，因为它创建了一个一维数组。`Line 3`正常编译，因为它声明并初始化了一个`int`变量。

由于二维数组是数组的数组，`Line 4`也正常编译。它将一个一维数组赋值给二维数组的其中一个维度。`Line 5`编译错误，因为我们不能将`int`变量赋值给`int`数组变量。

### 027. 解释编译以下代码时会发生什么。

```java
public class Car {

    public Car (String carName) {}

}

Car myCar = new Car("Benz");

Car [] myCars = { myCar, new Car("Ford"), new Car("BMW")};
```

答案：

### 028. 你被分配了一个任务，使用多维数组创建一个井字游戏。以下初始化数组的方法是？

a. `int ttt = new int[3][3];`
b. `int[]ttt = new int[3][3];`
c. `int[][]ttt = new int[3][3];`

答案：

(c) 答案`c`是正确的。声明多维数组的正确语法是`int[][]ttt =new int[3][3];`

答案：

Java中八种基本数据类型。它们如下：

| 名称 | 宽度（位） | 范围 |
| :--- | :--- | :--- |
| byte | 8 | –128 to 127 |
| short | 16 | –32,768 to 32,767 |
| int | 32 | –2,147,483,648 to 2,147,483,647 |
| long | 64 | –9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| float | 32 | 1.4e–045 to 3.4e+038 |
| double | 64 | 4.9e–324 to 1.8e+308 |
| boolean | 1 | true/false |

### 030. 将小数赋值给 float 变量的可能有哪些？

答案：

```java
float fValue1 = 100.5f;

float fValue2 = 100.5F;

float fValue3 = (float) 100.5;
```

小数默认被视为`double`。因此，为了将其赋值给`float`变量，需要在后面加上`'f'`或`'F'`，或者将其显式强制转换为`float`类型。

### 031. 识别以下代码片段中的错误并解释如何修复它。

```java
byte bValue = 10; //line 1
```

答案：

上述代码在`line 2`会导致编译错误。`Line 2`将一个`int`值赋值给`byte`变量并产生`int`结果。因此，当将`int`值赋值给`byte`变量`bValue`时，会导致编译错误。该代码可以通过如下指定显式转换来修复：

```java
bValue = (byte) (bValue + 10);
```

### 032. 如何将八进制和十六进制字面量赋值给“int”变量？

答案：

八进制和十六进制字面量可以如下赋值给`int`变量：

```java
int iValue1 = 000;
int iValue2 = 0xf;
```

八进制字面量需要前缀`0`。十六进制字面量需要前缀`0x`。

### 033. 识别以下代码中的错误并解释如何修复。

```java
byte bValue = 10; //line 1
```

上述代码在`line 2`会导致编译错误。`Line 2`将`int`值赋值给`byte`变量并产生`int`结果。因此，当将`int`值赋值给`byte`变量`bValue`时，会导致编译错误。该代码可以通过指定显式转换来修复：

```java
bValue = (byte) (bValue + 10);
```

### 034. 编译以下代码时会发生什么。

```java
public class Car {

    public Car (String carName) {}

}

Car myCar = new Car("Benz");

Car [] myCars = { myCar, new Car("Ford"), new Car("BMW")};
```

答案：

代码正常编译，没有任何问题。代码首先创建一个`Car`类。它创建一个名为`myCar`的汽车对象。最后，它创建一个初始化了三个值的`myCars`数组。`Car`构造函数在数组初始化期间被直接调用。

### 035. 被分配任务使用多维数组创建一个井字游戏。以下初始化数组的正确方法是？

a. `int ttt = new int[3][3];`
b. `int[]ttt = new int[3][3];`
d. `int ttt [3][3] = new int[][];`

答案：

(c) 答案`c`是正确的。声明多维数组的正确语法是`int[][]ttt =new int[3][3];`

答案：

Java有八种基本数据类型。它们如下：

| 名称 | 宽度（位） | 范围 |
| :--- | :--- | :--- |
| byte | 8 | –128 to 127 |
| short | 16 | –32,768 to 32,767 |
| int | 32 | –2,147,483,648 to 2,147,483,647 |
| long | 64 | –9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| float | 32 | 1.4e–045 to 3.4e+038 |
| double | 64 | 4.9e–324 to 1.8e+308 |
| boolean | 1 | true/false |

### 037. 将小数赋值给 float 变量的可能有哪些？

答案：

```java
float fValue1 = 100.5f;

float fValue2 = 100.5F;

float fValue3 = (float) 100.5;
```

小数默认被视为`double`。因此，为了将其赋值给`float`变量，需要在后面加上`'f'`或`'F'`，或者将其显式强制转换为`float`类型。

### 038. 识别以下代码片段中的错误并解释如何修复。

```java
byte bValue = 10; //line 1
```

答案：

上述代码在`line 2`会导致编译错误。`Line 2`将一个`int`值赋值给`byte`变量并产生`int`结果。因此，当将`int`值赋值给`byte`变量`bValue`时，会导致编译错误。该代码可以通过指定显式转换来修复：

```java
bValue = (byte) (bValue + 10);
```

### 039. 如何将八进制和十六进制字面量赋值给“int”变量？

答案：

八进制和十六进制字面量可以如下赋值给`int`变量：

```java
int iValue1 = 0100;
int iValue2 = 0xf1dead;
```

八进制字面量需要前缀`0`。十六进制字面量需要前缀`0x`。

### 040. 识别以下代码片段中的错误并解释如何修复它。

### 041. 以下代码的输出是什么？

```java
final int iIntFinal = 100;

int iValue = iIntFinal ++;

System.out.println("The output is– "+iValue);
```

答案：

这将导致编译错误，因为`iIntFinal`是`final`的，不能递增。

这段代码会导致编译错误。这是因为代码尝试使用自增运算符增加最终变量`iIntFinal`。`final`变量不能被修改。如果仅将`final`变量赋值给`intValue`变量，代码将正常运行。

### 042. 解释当以下代码被编译和执行时会发生什么？

```java
int iValue = 100;

if(iValue = 100) { //line 1

    System.out.println("iValue is: "+iValue);

}
```

答案：

### 043. 下面代码可以编译吗？如果是，输出是什么？

```java
int [] iArray = new int[10];

if(iArray instanceof Object) { //line 1

    System.out.println("Object");

}

else

    System.out.println("int");
```

答案：

上述代码可以正常编译，并显示以下输出：

```text
Object
```

数组是一个对象实例。因此，当执行第 1 行时，`if`条件返回`true`。

### 044. 下述代码的输出是什么？

```java
int iValue = 10;

int jValue =20;

if(iValue && jValue) { //line 1

}
else {
    System.out.println("False will be printed...");
}
```

答案：

上述代码会在第 1 行导致编译错误。`&&`是逻辑与运算符，只能拥有`boolean`类型的操作数。它不能与`int`类型的值配合使用。

### 045. 下述代码的输出是什么？为什么？

```java
System.out.println((10 < 100) ^ (100 > 10));
```

答案：

此代码产生以下输出：

```text
false
```

原因为——

- `10 < 100`返回`true`，可以表示为`1`
- `100 > 10`返回`true`，可以表示为`1`

对这些值应用`XOR`（异或）操作。当两个值相同时，`XOR`运算符返回`0`，否则返回`1`。由于两个值都是`true`，`XOR`运算符返回`0`，对应于`false`。

### 046. 下述代码段的输出是什么？解释原因。

```java
if(!(100 == 1000)) { //line 1

    System.out.println("TRUE gets printed");
}

else {
    System.out.println("FALSE gets printed");
}
```

答案：

此代码产生以下输出：

```text
TRUE gets printed
```

第 1 行检查条件`100 == 1000`，结果为`false`。`if`语句检查该条件的逻辑“非”（`!`）。逻辑“非”运算符返回其操作数的反面值。因此，它返回`true`。所以，`if`条件求值为`true`，并打印出上述输出。

### 047. 解释自增和自减运算符。

答案：

自增运算符用两个加号表示。它增加其操作数的值。以下代码演示了这一点：

```java
int i = 10;

i++; //将 i 设置为 11
```

自减运算符用两个减号表示。它将其操作数的值减 1。以下代码演示了这一点：

```java
int i = 10;

i--; //将 i 设置为 9
```

### 048. 解释 `instanceOf` 运算符。

答案：

`instanceOf`运算符可以用于检查一个对象是否是另一个类的实例。它返回一个`boolean`值。如果所比较的两个对象类型相同，则返回`true`，否则返回`false`。以下代码演示了这一点：

```java
String str = "Hello";

String str = null;

str instanceof String //返回 false
```

### 049. 解释三元运算符。

答案：

三元运算符也被称为条件运算符。它是`if–else`语句的简写运算符。其语法如下：

```text
条件?真路径:假路径
```

以下代码演示了这一点：

```java
int iValue1 = 100;

int iValue2 = (iValue1 == 100) ? 200: 100; //第 1 行
```

在这里，评估了`iValue==100`条件。由于它是真的，值`200`将赋值给变量`intValue2`。

# 第 05 章

## 控制语句

### 050. Java 中有哪些决策语句？

答案：

决策语句评估一个表达式并根据结果执行操作。Java中有两种决策语句。它们是：

a. `if`: `if else`是一种条件分支语句。它测试一个条件，如果条件为真，则按照某路径执行，如果不是，则遵循另一路径。它具有如下语法：

```java
if(condition){
    //在此处编写某些代码
}
else { //这部分是可选的
    //在此处编写某些代码
}
```

b. `switch`: `switch`语句是一种多路分支语句。它可以用于替代多个`if`语句。一旦找到匹配项，就会执行`case`内部的代码。它具有如下语法：

```java
switch(expression) {

case value1:

    break;

case value2:

    //某些代码

    break;

default:

    //某些代码
}
```

### 051. Java 中的循环结构包含哪些？

答案：

循环结构也称为迭代语句。它们可以用于重复执行一段代码。Java拥有以下结构：

a. `while`: `while`语句检查条件，只要条件为真就重复执行代码块。其语法为：

```java
while(condition){

    //代码体

}
```

b. `do while`: `do while`循环至少执行一次代码块，因为它在循环末尾检查条件。其语法为：

```java
do{
    //代码体
} while(condition);
```

c. `for`: `for`循环用于迭代范围的值。在条件为假后退出循环。其语法为：

```java
for(initialization;condition;iteration){

    //代码体

}
```

d. `for each`: `for each`循环用于遍历数组或集合。在迭代中，它从集合中获取元素并执行循环体。其语法为：

```java
for(type element : collection) {

    //代码体

}
```

### 052. 用示例解释 `if–else` 语句的语法。

以下是`if–else`的示例：

```java
int iValue = 10;

if(iValue > 1000) {

    System.out.println("iValue is > 1000");

}
else {
    System.out.println("iValue is < 1000");
}
```



`System.out.println(“iValue is < 1000”);`

### 053. 以下代码行可以编译，哪些会导致错误？

```java
while (iValue) {} //第 1 行

while (false) {} //第 2 行

while (iValue = 5) {} //第 3 行
while (iValue == 5) {} //第 4 行
```

**答案：**

第 1 行会导致错误，因为整数值不能传递给 `while` 循环。它需要一个 `boolean` 值。

第 3 行会导致编译错误，因为表达式 `iValue=5` 的求值不是 `boolean` 类型，它是一个赋值语句。

第 4 行可以正常编译，因为表达式 `iValue==5` 求值为 `boolean` 类型。

```java
public void foo(boolean boolA, boolean boolB) /* 第 1 行 */
{
    if (boolA) { /* 第 3 行 */
        System.out.println(“X”); /* 第 5 行 */
    else if (boolA && boolB) { /* 第 7 行 */
```

```java
System.out.println(“X && Y”); /* Line 9 */
}

else { /* Line 11 */

System.out.println(“notY”); /* Line 15 */
}

else { /* Line 17 */

}

}
}
```

**输出：** `In here`

由于 `boolA` 为 false，第 5 行将不会执行，且 `X` 不会被打印。由于 `boolA` 为 false，第 7 行也不会执行，因此 `X && Y` 也不会被打印。将进入第 11 行的 `else` 块。由于 `boolB` 为 true，第 13 行的 `if` 语句不会执行。因此，第 13 行的 `else` 语句被执行，打印出 `In here`。

### 055. 下列程序的输出是什么？

```java
public class SwitchDemo
{
    final static short caseVal = 2;

    public static void main(String[] abc)
        for (int iterNo = 0; iterNo < 3; iterNo++) {
            switch (iterNo) {
                case caseVal: System.out.print(“a ”);
                case caseVal - 1: System.out.print(“b ”);
                case caseVal - 2: System.out.print(“c ”);
            }
        }
}
```

**答案：**

由于 `caseVal` 被声明为 `final` 变量，它在编译时就会求值。当 `iterNo = 0` 时，第 3 个 `case` 语句为真，因此打印 `c`。在第二次迭代中，`iterVal` 变为 `1`，因此第二个 `case` 语句为真，打印 `b`。由于在第二个 `case` 之后没有 `break` 语句，第三个 `case` 语句也会执行，打印出 `c`。在第三次迭代中，第一个 `case` 为真，因此打印 `a`。由于 `case` 之后没有 `break`，随后紧接着打印 `b` 和 `c`。

### 056. 执行下面的代码时会发生什么？如果编译通过，输出是什么？

```java
int iValue2 = 200;

boolean isTrue() {
    return true;
}

if (((iValue1 > iValue2) && (iValue2 < 50))
    || isTrue()) { //Line 1
    System.out.println(“This is True”);
}
else {
    System.out.println(“This is False”);
}
```

**答案：**

代码可以正常编译并显示以下输出：

第 1 行的 `if` 语句使用了 `OR` 操作。当其操作数中任意一个为真时，`OR` 操作返回 true。由于 `isTrue()` 方法返回 `true`，`if` 语句将返回 `true`。因此，无论 `AND` 操作的结果如何，`if` 语句中的表达式都返回 `true`。

### 057. “break”和“continue”语句的作用是什么？

**答案：**

`break` 关键字可以在循环中使用。当遇到 `break` 语句时，循环会立即终止，控制权转移到循环外部。

`continue` 关键字也可以在循环中使用。它用于停止执行当前迭代中循环的后续语句，并将控制权转移到循环的开头。

### 058. 编译并执行下面的代码时会发生什么？输出是什么？

```java
for (int iValue = 0; iValue < 5; iValue++) {
    System.out.println(iValue); //line 1

    continue; //line 2

    System.out.println(iValue + 1);
}
```

**答案：**

代码可以编译，并在执行时显示如下输出：

`0`  
`1`  
`3`  
`4`

在第 1 行的 `Sysout` (`System.out`) 语句之后，执行了第 2 行的 `continue` 语句。这会跳过循环体的剩余部分，并将控制权转移到循环的开头。

### 059. 编译并执行下面的代码时会发生什么？输出是什么？

```java
for (int iValue = 0; iValue < 5; iValue++) {
    System.out.println(iValue);

    break;

    System.out.println(iValue + 1);
}
```

**答案：**

代码可以编译，并在执行时显示以下输出：

`0`

它只打印了 `0`。这是因为 `break` 语句停止执行循环中的后续语句，并将控制权转移到循环之外。

### 060. 编译并执行下面的代码时会发生什么？输出是什么？

```java
for (;;) {
}
```

**答案：**

上述代码可以正常编译。然而，它会执行无限循环，因为没有循环控制变量，也没有检查的条件。因此，这段代码将不断打印输出 `“Will this get printed?”`

### 061. 编译并执行下面的代码时会发生什么？输出是什么？

```java
int iValue = 50;

for (; iValue < 100;) {
}
```

**答案：**

在上述代码中，没有初始化语句和迭代语句，只指定了条件。因此，变量 `iValue` 永远不会递增。这变成了一个无限循环；无限地打印值 `“50”`。

**输出：**

`50`

`50`

`50`

`...`

### 062. 为“for–each”循环举一些例子。

**答案：**

以下是 `for–Each` 循环的一些示例：

```java
Integer[] integerArray = {1, 2, 3};

for (Integer i : integerArray) { }
```

**示例 2：**

```java
int[] numbers = {10, 20};

for (int n : numbers) { }
```

**示例 3：**

```java
Electronics[] electronics = {new Camera(), new Laptop()};

for (Electronics e : electronics) { }
```

**示例 4：**

```java
List<Integer> numbers = Arrays.asList(1, 2, 3);
```

### 063. 下列程序的输出是什么？

```java
int iValue = 0;

System.out.println(iValue);
}
```

**答案：**

### 064. 执行下面的代码时会发生什么？如果编译通过，输出是什么？

```java
int iValue = 10;

switch (iValue) {
    case 8:
        System.out.println(“8”);
    default:
        System.out.println(“This is Default”);
    case 9: {
        System.out.println(“9”);
        break;
    }
    case 11:
        System.out.println(“11”);
}
```

**答案：**

代码可以正常编译并显示输出：

`This is Default`

`9`

尽管 `iValue` 是 10，但 `default` 分支被执行了。由于 `default` 之后没有 `break` 语句，case `9` 也会执行。由于 `case 9` 之后有 `break`，因此不会打印 `11`。

### 065. 考虑下面的代码片段：

```java
static void main(String argument[]) {
}
```

**编译执行这段代码会输出？**

**答案：**

上述代码可以正常编译。但在执行时会发生如下错误：

`Error: Main method not found in class`

这是因为 `main` 方法没有 `public` 访问限定，所以它在类外部不可访问。因此，JVM 无法访问 `main` 方法。

### 066. 实例变量可以声明为 `static` 吗？

**答案：**

实例变量不能声明为 `static`。如果将实例变量声明为 `static`，那么该变量将成为类变量。

### 067. 解释编译并执行下面的代码时会发生什么。

```java
class Laptop {
    Laptop(String laptopName) {
        System.out.println(“Laptop Name is ....”);
    }

    Laptop l = new Laptop();
}
}
```

**答案：**

代码无法编译，并会导致以下编译错误：

`The constructor Laptop() is undefined.`

这是因为代码中没有定义默认构造函数。由于存在带参数的构造函数，Java 无法自动创建默认无参数构造函数。为了让这段代码工作，需要显式添加一个构造函数：

```java
Laptop() {
}
```

### 068. 如果没有显式指定构造函数，底层会发生什么？

如果没有显式指定构造函数，编译器会自动生成一个默认无参数构造函数。每当创建新对象时，都会使用这个默认构造函数。

### 069. 解释编译下面的代码会发生什么。

```java
Electronics() {
}

public void displayPrice() {
    Electronics();
}
}
```

编译上述代码时，会导致编译错误：类型 `Electronics` 中未定义方法 `Electronics()`。这是因为像这样调用构造函数是不合法的。

### 070. 构造函数可能的访问修饰符有哪些？

**答案：**

以下是构造函数可能的访问修饰符：

a. `private`：表示构造函数仅可以从所属类内部访问。

b. `public`：表示构造函数可以从位于任何包中的任何类访问。

### 071. 下述代码段的输出将是什么？

```java
public class MyClass {

    public void callMe(int a) {
        System.out.println(“Call me with int argument”);
    }

    public void callMe(long a) {
        System.out.println(“Call me with long argument”);
    }

    public static void main(String args[]) {
        MyClass myClassObj = new MyClass();

        int i = 6;

        myClassObj.callMe(i);
    }
}
```

**答案：**

上述代码将打印以下输出：

由于方法 `callMe()` 是用整数值调用的，因此接受整数参数的方法会被调用。如果我们将 `i` 的数据类型改为 `long`，则接受 `long` 类型参数的方法会被调用。

### 072. 你如何定义构造函数？请给出一个示例。

**答案：**

构造函数是一种特殊的方法，它的名称与类名相同，但没有返回类型。每当创建新对象时，构造函数就会自动调用。它最常用于执行在类对象被创建时就需要运行的代码，例如为实例变量设置初始值。下面的代码演示这一点：

```java
public class Electronics {
    int price;

    Electronics(int price) {
        this.price = price;
    } //constructor

    Electronics e = new Electronics(); //Line 1
}
```

在上述代码中，一旦执行 Line 1，`JVM` 就会调用构造函数。这会使用传入的值初始化 `price` 字段。

### 073. 请用代码示例解释 `void` 关键字。

**答案：**

当方法不返回值时，`void` 关键字非常有用。它被指定为此类方法的返回类型。下面的代码演示了这一点：

```java
public void doSomething() {
}
```

在这里，`void` 关键字被指定在 `doSomething()` 方法中，表示该方法不返回任何值。

### 074. 解释构造函数和普通方法之间的区别。

**答案：**

构造函数和普通方法之间有几点区别，如下：

- 构造函数的名称与类名相同，而普通方法可以有任何名称。
- 构造函数没有返回类型，即使是 `void` 也没有。方法有返回类型。如果方法不返回任何值，则需要指定 `void` 关键字。
- 如果一个类没有构造函数，Java 会自动创建一个默认构造函数。如果一个类没有方法，Java 不会自动添加方法。

### 075. 请用代码示例解释 `this` 关键字。

**答案：**

`this` 关键字用于引用当前对象。它可以用于引用当前对象对应的字段或方法。下面的代码演示了这一点：

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

这段代码创建了一个名为 `Book` 的类。它有一个初始化 `name` 和 `author` 字段的构造函数。`this` 关键字用于引用当前对象 `name` 和 `author` 字段的副本。这有助于区分实例字段和传入的变量。`this` 关键字也可以用于方法。因此，`doSomethingElse` 方法通过 `this` 关键字调用了 `doSomething` 方法。

### 076. 解释类和对象之间的区别。

类和对象之间有几点区别，如下：

- 类像一个模板，定义了一种新的数据类型。而对象是该数据类型的一个值。
- 类没有被分配任何内存。对象则被分配了内存。
- 类是一个逻辑实体，对象具有物理存在。
- 类使用 `class` 关键字声明，对象使用 `new` 关键字创建。
- 类没有状态，对象有状态。

### 077. 解释 `new` 关键字。

**答案：**

`new` 关键字用于为对象分配内存。它后面需要跟随对构造方法的调用。下面的代码段演示了 `new` 关键字：

```java
Person person1 = new Person();
```

在这里，`Person` 是类名，`person1` 是 `Person` 类型的对象。`new` 关键字后面是 `Person` 类的构造函数。这为 `person1` 对象分配了内存。`new` 关键字只需要指定对象，而不需要用于 `int`、`double` 等基本类型。

### 078. 下述代码段的输出将是什么？

```java
public class MyClass2 {
    private int field1 = 0;
    private static int field2 = 0;

    MyClass2 object1 = new MyClass2();

    object1.field1++; //Line 1
    object1.field2++; //Line 2

    MyClass2 object2 = new MyClass2();

    object2.field1++; //Line 3
    object2.field2++; //Line 4

    System.out.println(object2.field2); //Line 6
}
```

**答案：**

此代码将打印以下输出：

`1`  
`2`

在这里，类 `MyClass2` 有两个字段，`field1` 和 `field2`。`field1` 是实例字段，而 `field2` 是静态字段。对于实例字段，类的每个对象都有自己的副本。因此，`object1` 和 `object2` 将拥有它们各自的 `field1` 副本。Line 1 和 Line 3 会导致该字段副本的增。然而，对于静态字段，类的所有对象共享一个副本。因此，对应于 `object1` 和 `object2` 的 `field2` 只有一个副本。所以，Line 2 和 Line 4 会增加同一个副本，并导致 Line 6 打印值 2。

### 079. 请用代码示例解释 `return` 关键字。

`return` 关键字用于方法的末尾，以返回某些计算的结果。返回的值必须与方法的返回类型匹配。下面的代码演示了这一点：

```java
public int add(int num1, int num2) {
    return sum;
}
```

即使方法不返回任何值，也可以可选地指定不带任何值的 `return` 关键字。下面的代码演示了这一点：

```java
public void printSum(int a, int b) {
}
```



```java
System.out.println(sum);

return;
}
```

在这种情况下，方法具有`void`返回类型，表示方法不返回任何值。然而，仍然指定了`return`关键字。

### 080. 什么是内部类？内部类有哪些不同的类型？

**答案：**

内部类是指定义在另一个类体内的任何类。内部类有以下 4 类：

a. **嵌套类（Nested class）**：定义在另一个类体内的类。它可以访问外部类的所有成员。

b. **静态嵌套类（Static nested class）**：静态的嵌套类被称为静态嵌套类。它无法访问外部类的非静态成员。

c. **方法局部内部类**：在另一个类的方法内部定义的类被称为方法局部内部类。此类内部类只能访问外部类的 final（最终的）成员。

d. **匿名内部类**：一种没有名称且在定义时只能实例化一次的类被称为匿名内部类。因为它没有名称，所以它没有构造方法。它不能是静态的（`static`）。该类的定义以一个分号结束。

**答案：**

假设你有一个名为`TestOuter`的外部类，其中包含一个名为`TestInner`的内部类。以下代码段演示了如何实例化`TestInner`类：

```java
TestOuter.TestInner inner = outer.new TestInner();
```

因此，首先，你需要创建一个外部类的实例。由于内部类是外部类的成员，你随后可以使用点运算符（`.`）创建内部类的实例。此外，在使用`new`运算符调用内部类构造函数时，你需要使用点运算符指定外部类对象实例。

### 082. 编写一个代码示例，演示内部类

**答案：**

以下代码演示了一个内部类：

```java
class Outer {

    public void callInner() {
        Inner inner = new Inner();
        inner.readValue();
    }

    public void readValue() {
        System.out.println("Value is: " + iValue);
    }
}
```

在上面的代码中，`Outer`类有一个内部类`Inner`。`callInner()`方法实例化了`Inner`类并调用了它的`readValue()`方法。

### 083. 什么是“方法局部”内部类？

**答案：**

```java
public class Outer {
    public void doSomething() {
        final int i = 10;

        class Inner {
            System.out.println(i);
        }

        Inner inner = new Inner();
        inner.doSomethingInInner();
    }
}
```

这段代码指定了一个带有`doSomething()`方法的类`Outer`。在该方法内部定义了一个名为`Inner`的类。`Inner`是一个方法局部类。它在方法内部本身被实例化。

### 084. 使用代码示例解释静态嵌套类

静态嵌套类简单来说就是带有`static`关键字的内部类。以下代码演示了这一点：

```java
public class MyClass {
    int ivalue = 1000; // 第 1 行

    static class Nested {
        void doSomething() {
            staticValue = 6; // 第 2 行
            // ivalue = 20; // 第 3 行
        }
    }
}
```

静态嵌套类只能访问外部类的静态变量，不能访问非静态外部类变量。因此，第 2 行可以正常工作，但取消第 3 行的注释将导致编译错误。

### 085. 使用代码示例解释如何实例化静态嵌套类

考虑以下代码段：

```java
class MyClass {
    int ivalue = 1000; // 第 1 行
}
```

静态嵌套类可以如下方式进行实例化：

要实例化静态嵌套类，需要指定外部类名和嵌套类类名。在上面的代码中，类名是`MyClass`，静态嵌套类名是`Nested`。

## 继承

### 086. 给出一个非法方法重写的示例

**答案：**

以下代码是非法方法重写的示例：

```java
class Electronics {
}

class Camera extends Electronics {
    public void displayPrice() throws Exception {}
}
```

在代码段中，`Camera`类是`Electronics`类的子类。`displayPrice()`方法在`Camera`类中被重写。然而，这段代码将导致编译错误。这是因为`Camera`类中的`displayPrice()`方法指定了它抛出一个`Exception`。方法重写的规则之一是，重写的方法不能抛出新的或范围更广的检查异常（checked exception）。

### 087. 解释`super`关键字

**答案：**

```java
class Electronics {
    protected double price;

    public void displayPrice() {
        // 此处为某些代码
    }
}

class Camera extends Electronics {
    String cameraName;

    public void setPrice(double price) {
        super.price = price; // 第 1 行
    }
}
```

`super`关键字可以在子类中访问基类的实例字段或方法。它也可以用于子类构造函数以调用基类构造函数。考虑以下代码段：

`Camera`类是`Electronics`类的子类。`displayPrice()`方法在`Camera`类中被重写。然而，这段代码将导致编译错误。这是因为`Camera`类中的`displayPrice()`方法指定了它抛出一个`Exception`。方法重写的规则之一是，重写的方法不能抛出新的或范围更广的检查异常。

### 087. 解释`super`关键字

**答案：**

`super`关键字可以在子类中访问基类的实例字段或方法。它也可以用于子类构造函数以调用基类构造函数。考虑以下代码段：

```java
class Electronics {
    protected double price;

    public void displayPrice() {
    }
}

class Camera extends Electronics {
    String cameraName;

    public void setPrice(double price) {
        super.displayPrice(); // 第 2 行
    }
}
```

（注：原文中 087 之后出现了多处重复且混乱的文本，翻译时已根据语境进行了对齐）

`Camera`类是`Electronics`类的子类。`displayPrice()`方法在`Camera`类中被重写。然而，这段代码将导致编译错误。这是因为`Camera`类中的`displayPrice()`方法指定了它抛出一个`Exception`。方法重写的规则之一是，重写的方法不能抛出新的或范围更广的检查异常。

### 088. 下面的代码有一个错误。请指出并说明原因

```java
class Electronics {
}

class Camera extends Electronics {
    public void name() {}
}

public static void main(String argument[]) {
    Electronics e = new Camera(); // 第 1 行
    Camera c = new Electronics(); // 第 2 行
}
```

在上述代码段中，第 1 行是正常的，因为子类对象可以赋值给基类类型。然而，第 2 行会导致错误。这是因为基类实例不能赋值给子类类型。

### 089. 编写一个代码示例，演示继承如何帮助代码复用

**答案：**

```java
class Electronics {
    public void displayPrice() { // 第 1 行
        System.out.println("价格为...");
    }
}

class Camera extends Electronics {
    public void displayBatteryDuration() {
        System.out.println("电池可以持续 ... 小时");
    }
}

public class TestElectronics {
    public static void main(String argument[]) {
        Camera c = new Camera();
        c.displayPrice(); // 第 2 行
        c.displayBatteryDuration();
    }
}
```

在上面的代码中，定义了一个`Electronics`类。它有一个子类`Camera`。`Electronics`类中有一个`displayPrice()`方法。由于`Camera`是子类，可以通过`Camera`实例调用该方法，如第 2 行所示。

### 090. 编写一个 Java 代码示例，演示方法重写

方法重写发生在子类方法的名称和类型签名与基类中的方法相同时。考虑以下代码：

```java
public class Electronics {
    public void charge() {
    }
}

public class Camera extends Electronics {
    public void charge() {
        System.out.println("相机需要定期充电");
    }
}
```

在上面的代码中，`Camera`是`Electronics`的子类。两个类都具有相同类型签名的`charge()`方法。因此，`Camera`类中的`charge()`方法重写了`Electronics`类中的`charge()`方法。

### 091. 使用代码示例解释`extends`关键字

**答案：**

`extends`关键字用于指定一个类是另一个类的子类。它在子类的声明中指定。后面应该跟着基类的名称。以下代码演示了这一点：

```java
public class Animal {
}

public class Dog extends Animal {
}
```

在这里，`Animal`是基类，`Dog`是子类。`Dog`类使用`extends`关键字来指定`Dog`是`Animal`的子类。

### 092. 下面代码段的输出是什么？

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

    public static void main(String args[]) {
        Circle circle = new Circle();
    }
}
```

**答案：**

上述代码输出了以下内容：

```text
Circle constructor
```

这是因为子类构造函数会自动调用基类构造函数。不仅如此，基类构造函数的调用也发生在子类构造函数中的代码执行之前。因此，在本例中，当`Circle`构造函数被调用时，它会首先调用`Shape`构造函数，然后执行`Circle`构造函数中的代码。

### 093. 解释以下代码段的输出是什么？

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

    public static void main(String args[]) {
        Animal a = new Animal(); // Line 1
        Animal b = new Dog(); // Line 3

        b.saySomething(); // Line 4

        Dog d = new Dog(); // Line 5
        d.saySomething(); // Line 6
    }
}
```

**答案：**

这段代码将输出以下内容：

```text
I am an animal
I am a dog
```

第`1`和`2`行创建了一个`Animal`对象并调用`saySomething()`方法，该方法打印“I am an Animal”。第`3`行声明了一个`Animal`类型变量`b`，但将其赋值了一个`Dog`类型的对象。第`4`行使用变量`b`调用`saySomething()`方法。通常情况下，当给父类变量赋值子类对象并调用被重写的方法时，将执行子类的版本。然而，在本例中，尽管`Animal`和`Dog`类都拥有`saySomething()`方法，但它是一个静态方法。静态方法不能被重写。因此，第`4`行调用了`Animal`类的`saySomething()`方法并打印 I am an Animal。第`5`和`6`行创建了一个`Dog`对象并调用`saySomething()`方法，该方法打印 I am a Dog。

```java
public class Shape {
    public Shape() {
        System.out.println("Shape Constructor");
        System.out.println("I’m a shape!");
    }

    public void printShape() {
    }
}

public class Circle extends Shape {
    public void printShape() {
    }
}

public class Triangle extends Shape {
    public void printShape() {
        System.out.println("I’m a Triangle!");
    }
}

public class ShapeDemo {
    public static void main(String[] args) {
        Shape shape = new Shape(); // Line 1
        shape.printShape();

        Circle circle = new Circle(); // Line 2
        circle.printShape();

        Shape triangle = new Triangle(); // Line 3
        triangle.printShape();
    }
}
```

**答案：**

这段代码输出了以下内容：

```text
I’m a shape!
I’m a Triangle!
```

在这里，`Shape`是基类，`Circle`和`Triangle`是其子类。基类中有一个`printShape()`方法，该方法在两个子类中都被重写了。当方法被重写时，由赋值的对象类型而不是引用变量类型来决定调用哪个版本的重写方法。在第`1`行，一个`Shape`类型的变量被赋值一个`Shape`对象，因此调用了`Shape`类中的`printShape()`方法。在第`2`行，一个`Shape`类型的变量被赋值一个`Circle`对象，因此调用了`Circle`类中的`printShape()`方法。在第`3`行，一个`Shape`类型的变量被赋值一个`Triangle`对象，因此调用了`Triangle`类中的`printShape()`方法。Java 的这一特性被称为运行时多态。

### 095. 解释以下代码段存在什么问题

```java
public class Base {
    public void doSomething() {
    }

    public void doSomethingElse() {
    }
}

public class Demo {
    public static void main(String[] args) {
        base.doSomethingElse(); // Line 2
    }
}
```

**答案：**



这段代码在第`2`行导致编译错误。它定义了一个名为`Base`的类和一个名为`Sub`的子类。第`1`行创建了一个`Base`类对象。第`2`行调用`base.doSomethingElse()`方法。由于`doSomethingElse()`方法定义在`Sub`中，`Base`无法访问它，因此在第`2`行发生编译错误。

### 096. 什么是动态方法分派？

答案：

### 097. 下列代码是否有效？

```java
public class Shape {
}
public class Circle extends Shape {
}

public class ShapeDrawer {
    public void drawShape(Shape shape) {
        System.out.println("Drawing a shape");
}

public class ShapeDemo {
    public static void main(String args[]) {
        ShapeDrawer drawer = new ShapeDrawer();
        drawer.drawShape(new Circle()); //Line1
}
```

答案：

是的，上述代码是有效的。它定义了一个`Shape`类，`Circle`是`Shape`的子类。`ShapeDrawer`类有一个`drawShape`方法，接受一个`Shape`类型参数。`ShapeDemo`类创建了一个`ShapeDrawer`对象。第`1`行调用`drawer.drawShape(new Circle())`。由于`Circle`是`Shape`的子类，它可以被传递给接受`Shape`类型参数的方法。

```java
public class Sub extends Base{
    private void doSomething() { //Line 2
    }
}
```

Answer:

在这里，基类`Base`有一个被标记为`public`的`doSomething`方法。子类`Sub`重写了`doSomething`方法。然而，在子类的第`2`行中它被标记为`private`。因此，第`2`行导致了编译错误。这是因为你不能缩小被重写方法的可见性。为了修复此错误，你需要将第`2`行的`doSomething`方法标记为`public`。

# 第 09 章

## 抽象类与接口

### 101. 声明接口的可能方式有哪些？

以下是声明接口的可能方式：

a. `interface Interface1 {}`

b. `public interface Interface2 {}`

c. `public abstract interface Interface3 {}`

e. `abstract public interface Interface5 {}`

因此，接口可以有`public`访问修饰符，也可以没有修饰符（这意味着它将具有默认访问权限）。它也可以包含`abstract`关键字。关键字的顺序并不重要，可以以任何顺序指定。

### 102. 请用代码示例解释抽象类。

抽象类是一个具有零个或多个抽象方法的类。抽象方法是一个没有方法体的方法。抽象方法和类本身都需要指定`abstract`关键字。以下代码演示了一个抽象类：

```java
public abstract class Animal {
    private String name;
    public void printName(){
        System.out.println(name);
    }
}
```

### 103. 请用代码示例解释如何实现接口。

Answer:

为了实现一个接口，你需要在类名后使用`implements`关键字。`implements`关键字后面需要跟着接口名称。你还需要为接口中的方法提供实现。以下代码演示了这一点：

```java
public interface ShapeDrawer {
    public void draw();
}
```

```java
public class Triangle implements ShapeDrawer{
    public void draw() {
        // 绘制形状的代码
    }
```

类名即`Triangle`后面跟着`implements`关键字，随后是接口的名称`ShapeDrawer`。此外，`Triangle`类包含了`draw`方法的代码。

### 104. 下面的代码片段有效吗？请分别解释原因。

```java
public abstract class MyAbstractClass {

    public void doSomething() {

        // 正在做某些事情

    }

    public static void main(String args[]) {

        MyAbstractClass obj = new MyAbstractClass();//Line 1

    }

}
```

Answer:

### 105. 类可以实现两个接口吗？如果两个接口都有同名方法会发生什么？

Answer:

是的，一个类可以实现两个接口。即使两个接口都有同名的方法，也不会导致歧义，因为将使用类中提供的实现。
以下代码演示了这一点：

```java
public interface MyInterface1 {

    public void doSomething();

}

public interface MyInterface2 {

    public void doSomething();

}

public class MyClass implements MyInterface1, MyInterface2{

    @Override

        // 代码在这里

    }

}

MyClass obj = new MyClass();

obj.doSomething(); //Line 1
```

上面的代码指定了两个接口`MyInterface1`和`MyInterface2`。这两个接口都有一个名为`doSomething`的方法。代码还指定了一个实现这两个接口的类`MyClass`。它需要为`doSomething`方法提供实现。当执行第`1`行时，将执行`MyClass`中的`doSomething()`方法。

### 106. 抽象类的作用是什么？

Answer:

在某些编程场景下，你可能想要创建一个被许多子类共享的父类。你可能想在父类中放置一些通用代码，但将具体细节留给各个类来实现。抽象类在这种场景下非常有用。因此，你可以创建一个抽象父类。你可以拥有实现通用功能的具体方法，以及针对子类特有功能的抽象方法。子类可以扩展该抽象类并为抽象方法提供实现。

### 107. 请解释以下代码片段存在什么问题：

```java
public abstract final class MyAbstractClass {
    }
}
```

Answer:

### 108. 下面的代码片段有效吗？请分别解释原因。

```java
public interface ShapeDrawer {
    public void draw();

public class Triangle implements ShapeDrawer
{
    public void draw() {
        // 绘制形状的代码
    }
        ShapeDrawer shapeDrawer = new Triangle(); //Line 1
        shapeDrawer.draw(); //Line 2
    }
}
```

上面的代码是有效的。这段代码声明了接口`ShapeDrawer`和实现该接口的类`Triangle`。第`1`行声明了一个`ShapeDrawer`类型的变量并赋值一个`Triangle`对象。第`2`行调用`draw`方法。这执行了`Triangle`类中的。

### 109. 下面代码中的哪些行会导致编译错误？

```java
    private static int FIELD1 = 7; //Line 1
    int FIELD2 = 8;//Line 2
    public final FIELD3; //Line 3
    public static int FIELD4 = 8; //Line 4
}
```

Answer:

在上面的代码中，第`1`行和第`3`行会导致编译错误。接口中声明的所有字段应该是`public`、`static`且`final`的。如果没有指定`public` `static`和`final`关键字，字段会被隐式地变为`public` `static` `final`。第`1`行显式指定了`private`关键字，因此导致编译错误。第`2`行没有指定`public` `static` `final`关键字。然而，这不会导致编译错误，Java隐式将字段变为`public static final`。第`3`行指定了`public`和`final`关键字，但没有初始化字段。`final`字段需要初始化。因此，第`3`行也会导致编译错误。第`4`行指定了`public`和`static`关键字并初始化了字段。它没有指定`final`关键字。然而，这再次没有导致编译错误，字段被隐式视为`final`。

### 110. 下面的代码片段有效吗？请解释。

```java
public abstract class MyAbstractClass {

    private abstract void doSomething();

}
```

Answer:
上面的代码无效，并导致`doSomething`方法出现编译错误。这是因为`doSomething()`方法既是`abstract`的又是`private`的。`abstract`方法不能被标记为`private`。`private`方法在子类中是不可见的。`abstract`方法需要在子类中是可见的，以便子类能够提供实现。

# 第 10 章

## 包与访问控制

### 111. 什么是包（package）？包的优点是什么？
答案：

包是相关Java类型的集合。因此，一个包可以包含相关的类、接口和枚举。使用包有以下几个优点：

• 包有助于将相关的代码组织在一起。
• 包有助于避免命名命名冲突。因此，你可以在不同的包中拥有相同名称的类或其他Java类型。

### 112. 解释Java访问修饰符（access specifiers）。

答案：

访问修饰符控制特定成员在何处可以被访问。它们是指定在类成员上的关键字。它们既可以指定给实例字段，也可以指定给方法。Java有4种访问修饰符：
a. `Private`（私有）：具有`private`修饰符的成员只能在声明它的类内部被访问。
b. `Protected`（受保护）：具有`protected`修饰符的成员可以被包内的所有类以及包外部的子类访问。
c. `Public`（公共）：具有`public`修饰符的成员可以被包外部的所有类访问。
d. `Default`（默认）：当没有指定上述任何访问修饰符时，会发生默认访问。在这种情况下，该成员在包内可以访问，但在包外无法被访问。

### 113. 用代码示例解释如何创建一个包。
答案：

你可以使用`package`关键字创建一个包。其后应该跟随你想要给包命名的名称。包名应该是有效的Java标识符。包语句应该是Java文件中的第一条语句。以下代码演示了这一点：

```java
package demo;

public class MyClass {

    //instance fields and methods

}
```

这段代码声明了一个名为`MyClass`的类。它位于名为`demo`的包中。注意包语句是代码的第一条语句。

### 114. 列出JDK中的一些默认包并简要解释它们的作用。

答案：

以下是Java中的一些默认包：

b. `java.io`：此包包含帮助执行输入输出操作的类，如`InputStream`、`FileInputStream`、`FileOutputStream`、`BufferedReader`、`BufferedWriter`等。
c. `java.awt`:此包包含所有创建用户界面的类，如`Component`、`Container`、`Frame`等。
d. `java.util.concurrent`：此包包含所有用于并发编程的类，如`Future`、`Executor`、`ExecutorService`等。

### 115. 以下代码有效吗？解释原因。

```java
package demo1;

public class Base {
    protected int a;
}
```

```java
package demo2;

public class Sub extends Base {
    public void doSomething() {
        System.out.println("Value of a is "+a);
    }
}
```

答案：

上述代码是有效的，不会引起任何编译或运行时错误。这段代码创建了一个名为`Base`的父类和一个名为`Sub`的子类。这两个类位于不同的包中。`Base`类有一个`protected`字段`a`，该字段在子类的`doSomething()`方法被访问。这是完全有效的。只有基类的私有字段在子类中不可访问。具有`protected`修饰符的字段即使子类在不同的包中，也可以在子类中被访问。

### 116. 解释import关键字。
答案：

`import`关键字用于在代码中引入其他包。你可以导入标准的Java包（如`java.util`等），也可以导入用户定义的包。

`import`关键字后需要跟随包名。若要从包中导入特定类，你还需要指定类名。若要导入整个包，你需要在包名后使用通配符（`*`）。以下是import的示例：
`import java.util.List;`

### 117. 解释protected和default修饰符之间的区别。

答案：

`protected`和`default`修饰符之间有几点区别：
• `protected`访问修饰符允许访问包所有类以及包外部的子类。
• `default`访问发生在未指定上述任何访问修饰符时。它只在包内可访问，如果子类在不同的包中，则无法被访问。

### 118. 以下代码有效吗？解释。

```java
package demo1;

public class MyClass1 {

    int a; //Line 1

}
```

```java
package demo2;

public class MyClass2 {

    public void doSomething() {

        MyClass1 obj = new MyClass1(); //Line 2

        obj.a = 5; //Line 3

    }

}
```

答案：

上述代码无效，并会在第`3`行引起编译错误。`MyClass1`类位于`demo1`包中，并有一个具有默认访问权限的字段`a`。由于默认访问权限在包外不可，`MyClass2`无法访问它。

### 119. 解释当编译并执行以下代码时会发生什么：

```java
package com.questions;

public class CoreJava {
    private String getQuestion() {
        return "Question1";
}
```

```java
package com.questions;

class JSP extends CoreJava {
    public void getSPQuestion() {
    }
}
```

答案：

### 120. 解释java.lang包。

答案：

`java.lang`包包含了对Java编程语言重要的类。它包含了包装类，如`Byte`、`Boolean`、`Integer`、`Double`等。它包含用于字符串操作的`String`、`StringBuffer`和`StringBuilder`。它包含用于创建多线程程序的`Thread`和`Runnable`。它包含`Throwable`和其他`Exception`类，用于Java的异常处理功能。

# 第 11 章

## 异常处理

### 121. 解释Java中的'throw'、'throws'和'Throwable'。

`throws`关键字用于指定特定方法抛出一个未处理的异常或需要单独处理的多个异常。它基本上指定你不想在方法内部处理错误条件，而是希望将异常处理交给代码的其他部分。

`throw`关键字用于在方法内部显式地抛出异常。

`Throwable`是异常层次结构基类。可以通过扩展`Throwable`类来创建自定义异常。

### 122. 当编译并执行以下代码时，输出是什么？

```java
class Test {
    try {
        System.out.println("This is try block");
    System.out.println("Try block is executed"); //Line 1
    catch(Exception exp) {
        System.out.println("This is catch block");
    }
}
```

答案：

该代码会导致编译错误，因为不能在`try`块和它的`catch`块之间放置代码。



上述代码将无法编译并抛出编译错误。这是因为第 1 行的代码写在`try`块结束之后、`catch`块之前。所有代码都需要写在`try`块或`catch`块内部。Java 不允许在`try`块和`catch`块之间存在代码。

### 123. 编写一个演示 try/catch/finally 块的代码示例。

**答案：**

```java
try {
    System.out.println(“This is try block”);
} catch {
    System.out.println(“This is catch block”);
    System.out.println(“This is finally block”);
}
```

所有需要监控异常的代码都应该放在`try`块中。紧接`try`块之后，你需要指定一个`catch`子句。在`catch`块中，你需要指定想要捕获的异常类型以及当异常发生时你想要执行的代码。`finally`子句是可选的，它需要放在`try`块或`catch`块之后。无论是否发生异常，任何始终需要执行的代码都应该放在`finally`子句中。

```java
class ExceptionTest {
    public static void main(String argument[]) {
        callMethod();
    }
        int intValue = 100 / 0;
        System.out.println(“intValue is: ”+intValue);
    }
}
```

上述代码编译时没有任何错误。然而，在执行时它会抛出一个`ArithmeticException`，并带有堆栈跟踪（错误信息或报告），如下：

```
Exception in thread “main” java.lang.Arithmetic Exception– / by zero
at ExceptionTest.callMethod(ExceptionTest.java:12)
```

这是因为不允许将数字除以 0。

### 125. 解释 Java 中的 try–catch–finally 语句。

`Try–Catch–Finally`语句允许在 Java 中进行异常处理。你可以将想要监控错误的语句放在`try`块中。在发生异常时需要执行的代码应该存放在`catch`块中。你还需要指定你想要捕获的异常类型。你可以为不同类型的异常指定多个`catch`块。在`catch`块之后，你可以指定`finally`块。在这里，你只需要放入无论是否抛出异常都需要执行的代码。`catch`块和`finally`块是可选的，但你至少需要拥有其中一个。

以下代码演示了`try–catch–finally`语句：

```java
    // 需要监控异常的代码
} catch (ExceptionType 1) {
    // 发生异常时遵循的指令
} catch (ExceptionType 2) {
    // 发生异常时遵循的指令
} catch (ExceptionType n) {
} finally {
    // 无论是否抛出异常，此块都一定会被执行
}
```

### 126. 下面代码段的输出是什么？

```java
public class MyClass1 {
    public static void main(String abc[]) {
        try {
            int no;
            no = 52 / 0; //Line 1
            System.out.println(“ArithmeticException”);
        } catch (ArrayIndexOutOfBoundsException e) { //Line 3
            System.out.println(“Array Out Of Bound”);
        } catch (Exception e) { // any 其他异常 //Lin2 4
            System.out.println(“Sorry Unhandled Exception”);
        } finally { // 这将被执行 //Line 5
        }
        System.out.println(“Thank You!!”); //Line 6
    }
}
```

此代码打印以下输出：

```
ArithmeticException
I am done!
```

第 1 行导致了`ArithmeticException`。它被第 2 行的`ArithmeticException`catch 块捕获，该块打印文本`ArithmeticException`。由于`finally`块无论是否发生错误总是执行的，控制随后转移到第 5 行的`finally`块并打印`I am done`。接下来，控制转移到`finally`块之外的第 6 行，代码打印`Thank You!!`。

### 127. 假设你有一个名为`myMethod`的方法，包含可能会抛出检查异常（checked Exception）的代码。你如何在代码中处理它？

如果方法抛出检查异常，有两种处理方式：

a. 在方法体中使用`try/catch`，如下：

```java
    try {
        // 此处代码
    } catch (CheckedException e) {
    }
}
```

在这里，当代码抛出`CheckedException`时，它会被方法内部的`catch`块捕获。

b. 在方法声明中使用`throws`子句：

```java
public void myMethod () throws CheckedException{
}
```

在这里，当代码抛出`CheckedException`时，通过`throws`子句抛到方法外部。因此，调用方法的代码需要处理该异常。

### 128. “finally”子句的作用是什么？请举例。

**答案：**

无论是否发生异常，任何始终需要执行的代码都应该放在`finally`子句中。例如，关闭数据库连接、文件系统或其他资源的清理代码可以放在`finally`子句中。如果将此类代码放在`try`块中，一旦发生异常，它可能无法执行。为了确保此类代码执行，它需要放在`finally`块中。

### 129. 解释 Error（错误）和 Exception（异常）之间的区别。

`java.Throwable`是所有异常类的父类。它有两个子类：`Exception`和`Error`。它们之间存在若干区别：

- `Exception`代表程序本身引起的程序错误，如访问空值、除以 0、写入文件时出错等。`Error`代表发生在代码之外环境中的错误，如内存不足等。

- `Exception`是应用程序可以处理并恢复的状况。`Error`是应用程序无法恢复的异常状态。

- `Exception`既有检查的（checked）也有未检查的（unchecked）。检查异常需要在方法声明中通过`throws`子句指定。错误始终是未检查的，不需要声明。

### 130. 什么是 RuntimeException？

**答案：**

`java.lang.RuntimeException`是`java.lang.Exception`类的子类。`RuntimeException`及其子类也称为未检查异常（unchecked exceptions）。这是因为编译器不会强制你处理此类异常。因此，即使编写可能会抛出未检查异常的代码，编译器也不会报错。`RuntimeException`的示例包括`ArithmeticException`、`NullPointerException`和`ArrayIndexOutOfBoundsException`。

`strVar = strVar.concat(“ to Java”);`

### 133. 执行以下代码时，输出是什么？

```java
StringBuffer stringBuffer = new StringBuffer();
stringBuffer.append(“Core ”);
stringBuffer.append(“Java”);
System.out.println(“The resultant StringBuffer Value is– “+stringBuffer);
```

执行上述代码后，它将打印以下输出：

`The resultant StringBuffer Value is: Core Java`

`StringBuffer.append()`方法将指定的值附加到`StringBuffer`的值之后。

### 134. 下述代码段的输出是什么？

```java
String xValue = “xyz”;
String yValue = xValue.concat(“qrs”).toUpperCase().replace(‘Z’, ‘c’);
System.out.println(yValue);
```

**答案：**

上述代码打印以下输出：

`XYcQRS`

首先，`xValue`与值`qrs`拼接，因此值变为`xyzqrs`。然后，将值转换为大写，因此值变为`XYZQRS`。随后，字符`Z`被替换为`c`，因此值变为`ZYcQRS`。

### 135. 将字符串字面量赋值给 String 变量的方法有哪些？

**答案：**

a. `String strValue1 = “String Literal 1”;`

b. `String strValue2 = new String(“String Literal 2”);`

c. `String strValue3 = new String(); strValue3 = “String Literal 3”;`

d. `String strValue4 = strValue3;`

### 136. 列出 String 类中一些常用的方法。

**答案：**

以下是`String`类的一些常用方法：

a. `concat()`：用于将值附加到当前`String`之后。

b. `length()`：用于查找字符串的长度，即字符串中字符的总数。

c. `replace()`：用于将字符串中的特定字符或多个字符替换为其他值。

d. `substring()`：用于获取从指定位置开始的当前字符串的子字符串。

e. `trim()`：用于移除字符串中的空格。

f. `toUpperCase()`：用于将字符串中的所有字符转换为大写。

h. `equals()`：用于比较当前`String`与指定的`String`。它返回一个布尔值作为比较的结果。

i. `equalsIgnoreCase()`：用于在不区分大小的情况下比较当前`String`与指定的`String`。它返回一个布尔值，作为比较的结果。

### 137. StringBuffer 和 StringBuilder 之间的区别是什么？

**答案：**

`StringBuffer`和`StringBuilder`类都可用于执行字符串操作。与不可变的`java.lang.String`不同，它们都是可变的。然而，`StringBuilder`类不是线程安全的，即`StringBuilder`方法没有同步。这意味着当你在应用程序中执行两个或多个线程时，不应使用`StringBuilder`。此外，由于`StringBuilder`未同步，它的性能优于`StringBuffer`。

### 138. 编写一个不使用循环反转字符串的代码示例。

**答案：**

```java
StringBuilder sBuilder = new StringBuilder(“Core Java”);
sBuilder.reverse();
System.out.println(sBuilder);
```

这段代码创建一个带有字符串`Core Java`的`StringBuilder`实例，然后对其调用`reverse()`方法。

这段代码打印以下输出：

`avaJ eroC`

### 139. 编写一个演示如何将字符串转换为大写的代码示例。

**答案：**

`String`类有一个名为`toUpperCase()`的方法。它可以将字符串转换为大写。以下代码演示了这一点：

```java
String myStr = “Hello World”;
myStr = myStr.toUpperCase();
System.out.println(myStr);
```

`HELLO WORLD`

### 140. 解释如何将 Integer 转换为 String。

**答案：**

有多种方法可以将 Integer 转换为 String。如下：

a. 直接将整数包含在引号中：你可以将数字包含在引号内并赋值给字符串变量：`String str = “10”;`

b. 使用`String.valueOf`：`String`类有一个`valueOf`方法。可以使用它将整数转换为字符串：`String str = String.valueOf(10);`

### 141. 编译以下代码会发生什么？

```java
class Mammal {}
class Cat extends Mammal {}
```

**答案：**

此代码将无法编译。这是因为`List`指定的是`Mammal`，而`ArrayList`指定的是`Cat`。变量声明的类型必须匹配。

```java
class Mammal {}
class Cat extends Mammal {}
List<? super Mammal> mList = new ArrayList<Cat>(); // 第 1 行
```

**答案：**

第 1 行会导致编译错误。这是因为`Cat`位于层级结构中较低的位置。`Mammal`是父类。因此，只有将`<Cat>`替换为`<Mammal>`，上述代码才能编译。

### 143. 解释以下代码的问题。

**答案：**

上述代码创建一个名为`mylist`的`List`。它在声明中使用了通配符`?`。这是错误的，因为通配符不能用于声明部分。泛型的通配符符号只允许用于方法参数或返回值。

### 144. 解释使以下代码片段有效需要哪些额外的代码：

`public void getList(T t)`

**答案：**

这段代码声明了一个带有泛型参数的方法`getList`。为了使这段代码有效，该方法必须位于接受泛型类型的类内部：

```java
public class MyClass<T> {
    public void getList(T t) {
    }
}
```

**答案：**

边界泛型类型有助于限制可以作为泛型参数的类型。以下代码演示了这一点：

```java
public class Circle extends Shape {
}
public class ShapeDrawer<T extends Shape> {
    System.out.println(“Drawing Shape..”);
}
```

### 146. Java Collection API 中的四个主要接口是什么？

**答案：**

`java.util.Collection`是 Java Collection API 中的顶层接口。它简单地表示一组作为一个单元进行操作的值。它有两个主要的子接口：`Set`和`List`。这两者都用于存储一组值；但它们在存储数据的方式上略有不同。

`Set`不允许重复且是无序的，因此元素插入`Set`的顺序不会被保持。

另一个顶层接口是`Map`。`Map`用于存储键值对（key–value pairs）。

### 147. 如何在数组中搜索特定元素？

**答案：**

Java 提供了`java.util.Arrays`类作为 Collection 框架的一部分。它包含几个实用方法。其中一种方法是`Arrays.binarySearch`，它可以用于在数组中搜索特定元素。它返回一个整数，如果被搜索的元素存在，则指定其位置；否则返回 -1。以下代码演示了`binarySearch()`方法：

```java
String [] strArr = {“one”, “two”, “four”};
```

这段代码输出以下内容：
`Search index of one is:0`

由于`String` `one`位于位置`0`，所以`binarySearch()`方法返回`0`。

### 148. 如果不需要重复元素且不在乎顺序，你会选择哪种集合？

**答案：**

如果你想避免重复且不在乎顺序，应该使用`HashSet`。`HashSet`是`Set`接口的实现。它是无排序且无序的。此外，`TreeSet`和`LinkedHashSet`也是`Set`的实现。这两者都不允许重复。然而，`TreeSet`维护排序顺序，而`LinkedHashSet`维护插入顺序。

**答案：**

`Queue`接口有一个名为`poll()`的方法，用于移除队列的头部。以下代码演示了这一点：

```java
lList.add(100);
lList.add(200);
System.out.println(“Removed– “:lList.poll()); // Line 1
```



这段代码创建了一个 `Queue` 并向其添加两个整数值。然后调用 `poll()` 方法。因此，这段代码输出以下内容：

所以，`poll()` 方法始终移除队列的头部，即队列中添加的第一个元素。

### 150. 哪种集合实现允许增长或缩小大小，并对其元素提供索引访问？

答案：

`ArrayList` 是 `List` 接口的实现。它允许增长或缩小大小。它有 `add/remove` 方法来增加或减少 `List` 的大小。它还对其元素提供索引访问。它有一个 `get` 方法来实现这一点。以下代码演示了一个 `ArrayList`：

```java
List<Integer> myList = new ArrayList<Integer>();

myList.add(2);

myList.add(4);

myList.remove(1);

Integer num = myList.get(0);
```

### 151. 解释 `Queue` 接口

`Queue` 接口是 Collection API 的一部分，并扩展了 `java.util.Collection` 接口。除了 Collection 操作外，`Queue` 还提供了队列数据结构的功能，如 FIFO（先进先出）。`Queue` 接口有几个方法允许队列操作：

- `peek()`：允许检查队列顶部的元素。
- `poll()`：移除队列顶部的元素。
- `offer()`：向队列中插入一个元素。

### 152. 解释 `Comparator` 接口

答案：

`Comparator` 是一个可以用于排序的接口。从 Java 8 开始，它被指定为函数式接口（functional interface）。它有一个名为 `compare` 的单抽象方法。`compare` 方法接收两个对象，并返回一个作为比较结果的布尔值。`Comparator` 也可以用于排序自定义对象。为了这一点，相应的类需要实现 `Comparator` 接口并为 `compare` 方法提供实现。如果你使用 Java 8 或更高版本，还可以使用 lambda 表达式实现 `Comparator`。

以下是 Queue 接口的一些方法：

a. `offer(E e)`：将对象添加到队列中。如果无法将对象添加到队列中，它不会抛出异常。  
c. `poll()`：返回队列中最后添加的对象并将其从队列中移除。  
d. `remove(Object O)`：从队列中移除该对象。  
e. `add(E e)`：将对象添加到队列中。如果无法将对象添加到队列中，该方法会抛出异常。

### 154. 可以混合泛型（generic）和非泛型集合吗？如果是，请给出一个示例

是的，可以混合泛型和非泛型集合。以下代码片段演示了这一点：

```java
public void insertDouble() {
    List<Double> myDoubleList = new ArrayList<Double>();
    myDoubleList.add(4.0); // Line 2
    insertSomethingElse(myDoubleList);
}

public void insertSomethingElse(List myDoubleList) { // Line 3
    myDoubleList.add("Hello World"); // Line 4
}
```

在上面的代码中，Line 1 和 Line 2 将双精度字面量添加到列表中，该列表指定了泛型 `Double` 的 `List`。代码随后用这个双精度列表调用了 `insertSomethingElse()` 方法。在 Line 3 的方法声明中，`myDoubleList` 变量没有指定泛型类型。因此，任何类型的值都可以添加到此 `List` 中。Line 4 将一个字符串字面量添加到 `List` 中。

### 155. `Collection` 接口上有哪些重要方法？

以下是 Collection 接口的一些重要方法：

a. `add`：将对象添加到集合。  
b. `remove`：从集合中移除对象。  
c. `contains`：检查对象是否存在于集合。  
e. `iterate`：遍历集合。

# 第 15 章

## 枚举（Enumerations）、自动装箱（Autoboxing）和包装类（Wrapper Classes）

包装类是与 Java 基本类型对应的类。它们有助于将基本类型转换为对象，反之亦然。这在用 Collection 时特别有用。由于 Collection 不接受基本类型，你可以使用相应的包装类型。大多数包装类接受其基本类型或字符串作为参数。Java 支持以下包装类：

| 基本类型 | 包装类型 |
| --- | --- |
| byte | Byte |
| short | Short |
| int | Integer |
| long | Long |
| float | Float |
| double | Double |
| boolean | Boolean |

### 157. 下面代码的输出是什么？

```java
public class BooleanDemo {
    // 使用 boolean 基本类型创建 Boolean
    boolean boo1 = true;

    Boolean booObj1 = new Boolean(boo1); // line 1

    System.out.println("Wrapper class Boolean output: " + booObj1);

    Boolean booObj2 = new Boolean("false"); // line 2

    System.out.println(booObj1.booleanValue());
}
```

Line 1 创建了与变量 `boo` 对应的包装类型 `booObj1`。Line 2 使用字符串值创建了包装 `booObj2`。Java 会自动将包装类型转换为基本类型。此外，`Boolean` 包装类上有一个名为 `booleanValue()` 的方法可以返回基本布尔值。因此，这段代码将打印以下内容：

```text
包装类 Boolean 输出: false
true
```

### 158. 解释你如何将字符串 “100.55” 转换为 `Double` 以及将 `Double` 100.55 转换为字符串

答案：

可以使用 `Double.parseDouble()` 方法将 `String` 转换为 `Double`，如下所示：

```java
Double doubleValue = Double.parseDouble("100.55");
```

可以使用 `Double.toString()` 方法将 `Double` 转换为 `String`，如下所示：

```java
String stringValue = Double.toString(100.55);
```

### 159. 以下代码的输出是什么？

```java
Double doubleValue = Double.parseDouble("Java");
System.out.println(doubleValue);
```

答案：

上述代码编译编译。但在执行时会抛出 `NumberFormatException`。这是因为 JVM 无法将字符串 `Java` 转换为 `Double` 值。

### 160. 什么是 Java 中的包装类（Wrapper class）？包装类对象有哪些特殊属性？

Java 是一种面向对象的语言。Java 中的基本数据类型不是对象。有时，你需要基本类型的等效对象。一个很好的例子是当你想使用 `Collections` 时。`Collections` 只能包含对象而不能包含基本类型。为了解决这个问题，Java 引入了包装类，将基本类型封装成对象。每个基本类型都有一个对应的包装类，你可以创建该类型的对象。同样，你也可以将包装对象转换为基本类型。例如，对应于基本类型 “int”，Java 有 `java.lang.Integer` 包装类。Java 会自动在基本类型和对应的包装类之间进行转换。

### 161. 结合一个示例解释一下什么是自动装箱（Autoboxing）

答案：

自动装箱（Autoboxing），也称为 Boxing 或自动拆箱（Unboxing）是 Java 5 中引入的一项功能，有助于程序员减少一些代码行。

例如，为了将基本值赋值给包装类，你需要编写如下的装箱代码：

```java
Integer integerValue = new Integer(1000); // 装箱
```

通过自动装箱，上述代码可以重写为：

```java
Integer integerValue = 1000;
```

同样，为了将包装类赋值给基本类型，你需要编写如下的拆箱代码：

```java
Integer integerValue = 1000;
int iValue = integerValue.intValue(); // 拆箱
```

通过自动装箱，上述代码可以重写为：

```java
Integer integerValue = 1000;
int iValue = integerValue;
```

# 第 16 章

## 线程（Threads）

### 162. 在 Java 中你如何创建线程？

在 Java 中创建 `Thread` 有两种方法：

a. 通过继承 Thread 类：在这种方法中，你需要创建一个继承内置 `Thread` 类的类，并重写 `run()` 方法。以下代码演示了这一点：

```java
public void run() {
    System.out.println("In Thread Body..");
}
```

b. 通过实现名为 `Runnable` 的接口：在这种方法中，你需要创建一个实现内置 `Runnable` 接口的类。`Runnable` 接口有一个名为 `run()` 的单一方法，你需要实现它。以下代码演示了这一点：

```java
public class MyThread implements Runnable {
    public void run() {
        System.out.println("In Thread Body..");
    }
}
```

### 163. 解释 Java 中不同类型的线程

答案：

线程有 2 类型——用户定义线程（User defined Threads）和守护线程（Daemon threads）。

用户定义线程是由用户通过程序创建的线程。这些是高优先级线程。JVM 会等待这些线程完成。

守护线程大部分由 JVM 创建，用户用户线程也可以显式地设置为守护线程。守护线程通常用于后台进程，如垃圾回收（Garbage Collection）。一旦所有非守护线程停止运行，JVM 就会停止运行而不会等待守护线程停止。

### 164. 能否在不调用 `start()` 方法的情况下直接调用 `run()` 方法？

答案：

可以直接调用 `run()` 方法而不是调用 `start()` 方法。然而，这不会产生一个新线程，`run()` 方法中的代码将在调用它的同一个线程中执行。`start()` 方法负责产生新线程，并且需要被调用。

### 165. 当执行以下代码时，后台发生了什么？

```java
class Test {
    public static void main(String argument[]) {
        System.out.println("Thread Example...");
    }
}
```

答案：

当执行上述代码时，JVM 会创建一个线程来运行这段代码。该线程执行 `main` 方法中的代码，之后程序即终止。

### 166. 解释 `Thread` 类中的一些主要方法

答案：

a. `start()`：启动线程并调用 `run()` 方法。  
b. `run()`：需要在单独线程中执行的代码需要放在 `run` 方法中。  
c. `sleep()`：使运行的线程暂停指定的时间。  
d. `setName()`：将线程名称设置为指定的值。  
e. `join()`：等待线程死亡，最多等待指定的时间。  
f. `isAlive()`：返回一个布尔值，指示当前线程是否存活。  
g. `setPriority()`：将线程优先级更改为指定的值。

### 167. 解释线程状态

答案：

线程存在五种状态。它们如下：

a. **New（新建状态）**：当创建了一个新的 `Thread` 但没有调用 `start` 方法时，线程处于新状态。  
b. **Runnable（可运行状态）**：在调用 `start()` 方法后，但线程调度器尚未开始执行该线程，线程处于 Runnable 状态。  
c. **Running（运行状态）**：当线程调度器开始执行该线程时，它处于 Running 状态。`run()` 方法中的代码开始执行。  
d. **Waiting / Blocking（等待/阻塞状态）**：如果一个线程存活但不符合运行条件，则称其处于阻塞状态。  
e. **Dead（死亡状态）**：当线程完成执行时，它进入死亡状态。

### 168. 写一个使用 `Thread` 类创建线程的代码示例

答案：

以下代码使用 `Thread` 类创建一个线程：

```java
class MyThread extends Thread {
    public static void main(String argument[]) {
        MyThread thread = new MyThread();
        thread.start(); // 第 1 行
    }

    public void run() {
        System.out.println("In Thread Body..");
    }
}
```

上述代码定义了一个继承 `Thread` 类的 `MyThread`。当执行第 1 行时，产生了一个新线程。这执行了 `run()` 方法中的代码。

### 169. 写一个使用 `Runnable` 接口创建线程的代码示例

答案：

以下代码通过实现接口接口创建一个线程：

```java
class MyThread implements Runnable {
    public static void main(String argument[]) {
        MyThread myThread = new MyThread();
        Thread thread = new Thread(myThread); // 第 1 行
        thread.start(); // 第 2 行
    }

    public void run() {
        System.out.println("In Thread Body..");
    }
}
```

上述代码定义了一个实现 `Runnable` 接口的 `MyThread` 类。在第 1 行创建一个 `Thread` 对象，并将 `Runnable` 实现实例 `myThread` 传递给它。当执行第 2 行时，产生了一个新线程。这执行了 `run()` 方法中的代码。

### 170. 在 Java 应用中可以创建多个线程吗？如果是，线程之间如何通信？

答案：

是的，在 Java 应用中可以创建多个线程。为了让两个线程相互通信，需要使用来自 `object` 类的 `wait()`、`notify()` 和 `notifyAll()` 方法。

`wait()` 方法导致当前线程暂停，直到其他线程在同一个对象上调用 `notify()`。

如果有许多对象在等待某个特定对象，`notify()` 方法会导致其中一个线程恢复执行。

`notifyAll()` 方法会导致所有等待该特定对象的线程恢复执行。

### 171. 什么是同步（Synchronization）？

当多个线程尝试同时访问同一个共享资源时，它们需要某种方式确保同一时间只有一个线程可以访问该资源。实现这一目标的过程被称为同步。Java 提供了一个名为 `synchronized` 的关键字来帮助实现这一目标。

### 172. 解释执行以下代码时会发生什么

```java
class TestMyRunnable implements Runnable {
    public void run() {
        System.out.println("Inside Run Method..");
        System.out.println("Name of thread is– " + Thread.currentThread().getName());
    }
}

class TestMyThread {
    public static void main(String argument[]) {
        TestMyRunnable runnable = new TestMyRunnable();
        Thread thread = new Thread(runnable);
        Thread.setName("My Thread"); // Line 1
        thread.start(); // Line 2
    }
}
```

答案：

代码正常编译并显示以下输出：

```text
Inside Run Method.
Name of thread is: My Thread
```

当执行 `Line 1` 时，它将线程设置为 `My Thread`。因此，当执行 `Line 2` 时，它会产生新线程并执行 `run()` 方法中的代码，打印出的线程名称为 `My Thread`。

### 173. 考虑以下代码

```java
class TestMyRunnable implements Runnable {
    public void run() {
        for (int iValue = 0; iValue < 1000; iValue++)
```



`System.out.println("Name of thread is: " + Thread.currentThread().getName());`

```
public static void main(String argument[]) {
    TestMyRunnable runnable = new TestMyRunnable();
    Thread threadC = new Thread(runnable);
    Thread threadD = new Thread(runnable);
    threadC.setName("Thread 1");
    threadD.setName("Thread 2");
    threadC.start();
    threadD.start();
}
```

执行这段代码会先打印 1000 次“Thread 1”，然后打印 1000 次“Thread 2”。如果这是是错误的，请解释原因。

**答案：**

执行上述代码时，它不会先打印 1000 次 `Thread 1` 然后打印 1000 次 `Thread 2`。线程执行的顺序取决于 `Thread` 调度器。因此，虽然两个线程都打印了 1000 次名称，但它们打印的顺序是不可知的。

### 174. 编写一个代码示例让线程暂停十分分钟。

**答案：**

为了让线程暂停十分分钟，你需要在 `run()` 方法中调用 `sleep()` 方法。`sleep()` 方法接受一个 `long` 类型的参数，表示线程应该睡眠的毫秒数。以下代码演示了这一点：

```java
try {
    Thread.sleep(10 * 60 * 1000)
}
catch(InterruptedException exp) {
}
```

### 175. 调用同步方法（synchronized method）时会发生什么？

**答案：**

每当执行 `synchronized` 方法时，调用该方法的线程都会获取锁并在方法结束时持有锁。只有在当前线程完成方法执行后，它才会释放锁。这样，其他线程就可以获取锁并执行该方法。因此，`synchronized` 关键字防止了多个线程同时执行 `synchronized` 方法中的代码。

## 第 17 章

## Java IO API

### 176. 执行以下代码时会发生什么？

```java
File myFile = new File("CoreJava.txt");
```

**答案：**

当执行上述代码时，JVM 在内存中创建了一个名为 `myFile` 的 Java 对象，但文件系统上不会创建实际的文件。要实际创建文件，需要调用 `myFile.createNewFile()` 方法。

### 177. 编写一个代码示例在 `/usr/test.txt` 路径下创建一个文件。

**答案：**

以下代码将在 `/usr/` 目录下创建一个名为 `test.txt` 文件：

```java
try {
    File txtFile = new File("/usr/test.txt"); // Line 1
    txtFile.createNewFile(); // Line 2
} catch (IOException exp) {
}
```

在上述代码中，当执行 `Line 1` 时，内存中创建了一个对象 `txtFile`；当执行 `Line 2` 时，`/usr/` 文件夹内创建了文件 `test.txt`。

### 178. 使用代码示例解释 `FileWriter` 类。

**答案：**

`FileWriter` 类用于向文件写入字符或字符串，而无需将其转换为字节数组。

它们通常被包装在 `PrintWriter` 或 `BufferedWriter` 中，这可以提供性能改进和更多写入数据的方法。以下代码演示了 `FileWriter`：

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

在上述代码中，当执行 `Line 1` 时，`write()` 方法将内容写入 `CoreJava.txt` 文件。

### 179. 编写一个代码片段，使用 `FileReader` 读取 `CoreJava.txt` 的内容。

**答案：**

为了使用 `FileReader` 读取 `CoreJava.txt` 的内容，通常使用如下代码：

```java
try {
    File txtFile = new File("CoreJava.txt");
    FileReader myFileReader = new FileReader(txtFile);
    // 读取逻辑
}
catch (IOException exp) {
}
```

### 180. 使用代码示例解释 `FileWriter` 类。

**答案：**

`FileWriter` 类用于向文件写入字符或字符串，而无需将其转换为字节数组。

它们通常被包装在 `PrintWriter` 或 `BufferedWriter` 中，这可以提供性能改进和更多写入数据的方法。以下代码演示了 `FileWriter`：

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

在上述代码中，当执行 `Line 1` 时，`write()` 方法将内容写入 `CoreJava.txt` 文件。

这段代码将文件 `file1.txt` 重命名为 `file2.txt`。以下代码演示了重命名目录：

```java
File dir1 = new File("/usr/dir1");
dir1.createNewFile();
File dir2 = new File("/usr/dir2");
dir1.renameTo(dir2); //Line 1
```

这段代码将目录 `dir1` 重命名为 `dir2`。

### 185. 哪些类被用于对象的序列化和反序列化？

**答案：**

序列化（Serialization）是将对象写入到文件系统的过程。可以使用 `java.io.ObjectOutputStream` 来对对象序列化。它有一个 `writeObject()` 方法可以实现这一功能。反序列化（De–serialization）是恢复序列化对象的过程。可以使用 `java.io.ObjectInputStream` 来恢复对象。它有一个 `readObject()` 方法可以实现这一功能。

### 186. 解释 `File` 类的一些重要方法。

**答案：**

`File` 类封装了文件系统上的文件或目录。`File` 类的一些方法如下：

a. `createNewFile()`：创建一个新的空文件
b. `list()`：返回当前目录内文件/目录的数组
c. `delete`：从文件系统中删除文件
d. `mkdir`：创建一个目录
e. `getAbsolutePath`：返回文件的绝对路径

## 第 18 章

## 杂记

### 187. 解释编译以下代码段时会发生什么。

```java
public class Test {
    public static void main(String argument[]) {
        int iValue;
        System.out.println(iValue);
    }
}
```

**答案：**

这段代码会导致编译错误。这是因为变量 `iValue` 没有初始化但在 `Sysout` 语句中被使用了。可以通过在在使用之前初始化变量 `iValue` 来修复错误，如下：

```java
int iValue = 0;
System.out.println(iValue);
```

### 188. 解释编译并执行以下代码会发生什么。

```java
class Calculate {
    float fValue = 10.2f;
    public static void main(String argument[]) {
        System.out.println("Float value is: "+fValue);
    }
}
```

**答案：**

上述代码会导致编译错误，因为 `main` 方法尝试访问非静态实例变量 `fvalue`。Java 不允许从非静态方法访问静态变量。

### 189. 解释对称的 `equals()` 合约。

**答案：**

假设有两个对象 `v1` 和 `v2`。如果 `v1.equals(v2)` 返回 true，那么 `v2.equals(v1)` 必须返回 true。这种 `equals()` 约被称为对称契约（symmetric contract）。考虑以下代码：

```java
Object v1; Object v2;
v1.equals(v2); //Line 1
v2.equals(v1); //Line 2
```

因此，在对称契约的情况下，Line 1 返回 true 当且仅当 Line 2 返回 true 时。

### 190. 以下哪些是无效的语句？为什么？

```java
System.out.println(2+2); //line 1
int i= 2+'2'; //line 2
String s= "one"+'two'; //line 3
byte b=256; //line 4
```

**答案：**

Line 1 和 line 2 是有效语句。

Line 3 是无效的。值 `two` 是无效的，因为单引号不能用于字符串，它们只能用于字符常量。字符串需要包含在双引号中。

Line 4 是无效的。`byte` 类型的变量 `b` 不能被赋值为 256，因为超出了 `byte` 的范围范围。

### 191. `transient` 关键字的作用是什么？

**答案：**

`transient` 关键字可以指定在实例变量上。为实例变量指定 `transient` 表示在对象被序列化时，其状态不应被保存。考虑以下代码段：

```java
class Electronics implements Serializable {
    transient private int price; //Line 1
    private int quantity; //Line 2
}
```

当 `Electronics` 类的实例被序列化时，`price` 字段将不会被序列化，只有 `quantity` 字段会被序列化。

### 192. 什么是 Java 中的垃圾回收？

**答案：**

垃圾回收（Garbage collection）是释放分配给不再使用的对象的内存的过程。在运行时，当对象被创建时，`JVM` 会分配一些内存来存放该对象。`JVM` 定期检查正在使用的对象，并为那些不再使用的对象释放内存。垃圾回收就是移除这些不再使用的对象的过程。因此，程序员不需要担心手动释放内存的问题。

### 193. 垃圾回收使用了内存的哪个部分？JVM 使用什么算法进行垃圾回收？

**答案：**

垃圾回收是在堆内存（heap memory）中进行的。`JVM` 内部使用“标记-清除”（mark and sweep）算法进行垃圾回收。

### 194. 垃圾回收何时发生？

**答案：**

`JVM`（Java 虚拟机）控制垃圾回收过程。因此，由 `JVM` 决定何时运行垃圾回收过程。

也可以通过 Java 代码显式地请求垃圾回收。

### 195. 什么样的代码可以触发垃圾回收？

**答案：**

可以通过以下方式触发垃圾回收：

方法 1– 使用 `Runtime.gc()`：
```java
Runtime.getRuntime();
```

方法 2– 使用 `System.gc()`：
```java
System.gc();
```

这两种方法都不保证触发垃圾回收，取决于 `JVM`。

### 196. 请通过代码示例解释对象何时变为垃圾对象。

**答案：**

当对象不再被引用时，就会变为垃圾对象。以下场景演示了这一点：

场景 1– 将对象设置为 null
```java
String stringValue = "This is a String); //Line 1
stringValue = null; //使该字符串变为垃圾
```

场景 2– 重新赋值变量
```java
String str1 = "Hello";
str1 = str1; //使 str1 变为垃圾
```

场景 3– 方法内部创建的对象
```java
public void doSomething(){
    String str1 = "Hello";
}
public void callMethod(){
    doSomething();
}
//doSomething 中的 str1 变为垃圾
```

## 第二节

## 核心 Java

## JAVA 8

## 第一章

## 函数式接口

### 197. 什么是函数式接口？如何创建一个函数式接口？

**答案：**

函数式接口只有一个抽象方法的接口。要创建一个函数式接口，你只需要创建一个只有一个抽象方法的接口，如下：

```java
@FunctionalInterface
public interface Multiplier {
    public int multiply(int a, int b);
}
```

这段代码定义了一个名为 `Multiplier` 的接口。它只有一个 `multiply` 方法。它指定了 `@FunctionalInterface` 注解。该注解是可选的，它标记接口为函数式接口。因此，如果你尝试向接口添加另一个抽象方法，会导致编译错误。

### 198. 解释 `java.util.function` 包。

**答案：**

`java.util.function` 是 Java 8 添加的新包。它有很多内置的函数式接口。该包的一些接口如下：

a. `Predicate`：用于测试条件。它返回一个布尔值，表示条件的真假。它接受任意类型的参数。
b. `Consumer`：用于对值进行操作。它接受任意类型的参数并对其进行操作。它返回 void。
c. `Function`：用于转换输入值。它接受任意类型的参数，对其进行转换并返回一个结果。
d. `Supplier`：用于产生一个值。它不接受任何参数，但产生一个任意类型的结果。

### 199. 请用代码示例解释 `java.util.function.Consumer` 接口。

**答案：**

`java.util.function.Consumer` 是一个内置函数式接口。它是 Java 8 添加的 `java.util.function` 包的一部分。它有一个名为 `accept()` 的方法，该方法接受任何数据类型的参数并对其进行操作。它不返回任何结果。该方法需要通过 lambda 表达式来实现。以下代码演示了：

```java
Consumer<String> printStr = val-> System.out.println(val); //Line 1
printStr.accept("Hello World"); //Line 2
```

Line 1 创建了一个类型为 `String` 的名为 `printStr` 的 `Consumer`。它通过 lambda 表达式实现了 `accept()` 方法，该方法简单打印输入的 `String`。Line 2 使用值“Hello World”调用了 `accept` 方法。因此，这段代码输以下输出：

Hello World

### 200. 解释 `Supplier` 和 `Consumer` 接口之间的区别。

**答案：**

`Supplier` 和 `Consumer` 接口都是 `java.util.function` 包中的内置函数式接口。它们之间有以下几点区别：

- `Supplier` 接口不接受参数，而 `Consumer` 接口接受任何数据类型的参数。
- `Supplier` 接口产生任何数据类型的返回值，而 `Consumer` 接口不返回任何值。
- `Supplier` 接口基本上产生特定数据类型的值，而 `Consumer` 接口则对输入值进行操作。

### 201. 下述代码段的输出是什么？

```java
Predicate<Integer> numberChecker = (num)-> num > 20;
int input = 10;
System.out.println(input+" greater than 20–"+numberChecker.test(input)); //Line 1
input = 40;
System.out.println(input+" greater than 20–"+numberChecker.test(input)); //Line 2
```



答案：

上述代码段使用了名为`Predicate`的内置函数式接口。该接口接受任何数据类型的参数并返回一个布尔值。因此，它基本上被用于测试条件。在这里，代码创建了一个名为`numberChecker`的`Predicate`，它接受一个整数值。它通过 lambda 表达式实现，用于检查输入数字是否大于 20。Line 1 对值 10 应用了`Predicate`，而 Line 2 对值 40 应用了`Predicate`。因此，代码输出了以下输出：

```
10 greater than 20:false
40 greater than 20:true
```

### 202. 你使用哪种内置函数式接口将 String 转换为大写？

答案：

有一个名为`UnaryOperator`的内置函数式接口。它接受任何数据类型的参数并返回相同数据类型的结果。它有一个名为`apply`的方法可以对输入值进行操作。因此，你可以用它将`String`转换为大写。以下代码演示了：

```java
UnaryOperator<String> converter = str-> str.toUpperCase();
System.out.println(converter.apply("hello world"));
```

在这里，代码创建了一个名为`converter`的`UnaryOperator`实现，它对`String`值进行操作。使用 lambda 表达式将`String`转换为大写。因此，这段代码输出了以下输出：

```
HELLO WORLD
```

### 203. 下面代码有效吗？请解释。

```java
@FunctionalInterface
public interface Interface1 {
    public void doSomething();
}

public interface Interface2 extends Interface1{
    public void doSomethingElse();
}
```

答案：

上面的代码声明了一个名为`Interface1`的函数式接口，包含一个名为`doSomething`的抽象方法。然后它定义了另一个名为`Interface2`的函数式接口，它扩展了`Interface1`并有一个名为`doSomethingElse`的抽象方法。这段代码完全有效。`Interface2`现在有两个抽象方法：`doSomething()`和`doSomethingElse()`。因为它没有标记`@FunctionalInterface`注解，所以拥有多个抽象方法是可以允许的。如果在`Interface2`上使用了`@FunctionalInterface`注解，代码将会导致编译错误。

### 204. 列举一些 Java 8 之前被 Java 8 变为函数式接口的接口。

答案：

在 Java 8 之前，某些接口已经有单个抽象方法。Java 8 通过在这些接口上指定`@FunctionalInterface`注解将这些接口指定为函数式接口。因此，这些接口中的抽象方法可以通过 lambda 表达式来实现。这些接口如下：

a. `java.lang.Runnable`：用于创建`Thread`。
b. `java.util.concurrent.Callable`：用于创建返回值的`Thread`。
c. `java.util.Comparator`：用于比较值。
d. `java.io.FileFilter`：用于过滤`Files`。

### 205. 为什么 Java 8 添加了内置函数式接口的原始类型特化（如`IntSupplier`、`BooleanSupplier`等）？

答案：

Java 添加`IntSupplier`、`BooleanSupplier`等内置函数式接口的原始类型特化是为了提高性能。原始类型特化消除了自动装箱的需求，从而提高了性能。以下代码演示了这一点：

```java
Supplier<Integer> integerSupplier = ()-> new Integer(new Random().nextInt());
```

这段代码创建一个返回小于 100 随机整数的`Supplier`。由于没有使用原始类型特化，`Random`类返回的值需要被封装为`Integer`。现在考虑以下代码：

```java
IntSupplier integerSupplier2 = ()-> Random().nextInt();
```

在这种情况下，使用了`IntSupplier`，它是`Supplier`的原始类型特化，返回整数。因此，不需要将返回值封装为`Integer`。由于避免了自动装箱，这段代码带来了更好的性能。

### 206. 内置函数式接口通常用在哪里？

答案：

Java 8 添加了`Stream API`，它帮助对集合进行批量操作。内置函数式接口通常用作流中方法的参数。流方法将函数式接口指定的操作应用到`Stream`中的每个元素。例如，`Stream`接口有一个`filter`方法，可以根据某些条件过滤`Collection`。条件通过`Predicate`接口指定，它是一个内置函数式接口。它检查输入`Stream`中的每个值是否符合`Predicate`指定的条件。同样，`Stream`接口有一个方法`map`，可以转换`Stream`中的元素。它接受一个`Function`实例作为参数，它是一个内置函数式接口。它将`Function`接口指定的操作应用到`Stream`中的每个元素。

Java 8 增加了函数式接口以支持 lambda 表达式并为 Java 函数式编程支持。由于 Java 是一种面向对象的语言，lambda 表达式不能独立存在。它们需要与对象关联。因此，Java 8 引入了函数式接口，并强制 lambda 表达式只能配合函数式接口使用。通过让 lambda 表达式实现函数式接口的方法，lambda 表达式变成了函数式接口的实现。函数式接口和 lambda 表达式有助于编写简洁的 Java 代码。

### 209. 解释 lambda 表达式的语法。

**答案：**

以下是 lambda 表达式的语法：

`(parameters)–> {lambda body}`

因此，一个 lambda 表达式由表达式的`parameters`、lambda 运算符`(–>)`和`expression body`组成。lambda 表达式接收零或多个参数。如果不接受任何参数，则需要使用空括号。如果接受单个参数，则不需要在括号中指定参数。如果接受多个参数，则需要在括号中指定并用逗号隔开。lambda 体是普通的 Java 代码，可以包含任意数量的语句。如果 lambda 体中只有一条语句，可以省略主体周围的大括号，否则需要指定它们。

### 210. 提供一些 lambda 表达式的示例。

**答案：**

以下是一些 lambda 表达式的示例：

**示例 1– 单参数，无返回值**

`str–> System.out.println(str);`

此 lambda 表达式接受一个参数并使用`Sysout`语句打印它。它不返回任何值。

**示例 2– 多个参数和返回值**

`(num1, num2)–> num1+num2;`

此 lambda 表达式接受两个参数并返回它们相加的结果。这里没有显式指定`return`关键字。

**示例 3– 无参数，lambda 体和返回值**

```java
()>(){
    //在此执行某些操作
    return 0;
}
```

此 lambda 表达式不接受任何参数。它有一个执行某些代码体。它返回值`0`。

## 211. 编写一个代码示例，创建一个函数式接口并使用 Lambda 表达式实现它。

**答案：**

函数式接口是一个只有一个抽象方法的接口。考虑以下函数式接口：

```java
@FunctionalInterface
public interface StringConverter {
    public String convert(String s);
}
```

此代码定义了一个名为`StringConverter`的函数式接口，包含一个名为`convert`方法。`convert`方法接受一个`String`值并返回一个`String`。

lambda 表达式为函数式接口中的方法提供了实现。

因此，你可以如下使用 lambda 表达式实现`StringConverter`接口：

```java
StringConverter converter = (str)–> str.toUpperCase();
```

在这里，`StringConverter`通过一个 lambda 表达式实现，该表达式将输入的`String`转换为大写并返回。

## 212. 用代码示例说明如何使用不同的 lambda 表达式以不同的方式实现同一个函数式接口。

**答案：**

考虑以下`StringConverter`函数式接口：

```java
@FunctionalInterface
public interface StringConverter {
    public String convert(String s);
}
```

现在可以通过不同的 lambda 表达式为`convert`方法提供不同的实现，如下：

```java
StringConverter upperCaseconverter = str–> str.toUpperCase();
String result = upperCaseconverter.convert(“Hello”);
```

在这里，`StringConverter`接口通过一个 lambda 表达式实现，该表达式将输入的`String`转换为大写并返回。

现在考虑以下代码：

```java
StringConverter lowerCaseconverter = str–> str.toLowerCase();
String result = lowerCaseconverter.convert(“Hello”);
```

在这里，`StringConverter`接口通过一个 lambda 表达式实现，该表达式将输入的`String`转换为小写并返回。

因此，不同的 lambda 表达式为`StringConverter`接口提供了不同的实现。

### 213. 识别以下 lambda 表达式中的错误以及如何修复它。

`(str)–> return str.toUpperCase();`

**答案：**

上面的 lambda 表达式在 lambda 体中使用了`return`关键字。如果使用了`return`关键字，则 lambda 体需要包含在大括号中。或者，也可以移除`return`关键字以消除错误。

因此，上面的 lambda 表达式可以通过以下两种方式修复：

```java
(str)–> {return str.toUpperCase();};
```

或者

```java
(str)–> str.toUpperCase();
```

## 214. 下列代码有效吗？请解释。

```java
public void generateSquareRoot(int num) {
    Function<Integer, Double> squareRoot = (num)–> Math.sqrt(num);
}
```

**答案：**

上面的代码指定了一个名为`generateSquareRoot`方法。它接受一个整数值作为参数。然后使用内置的函数式接口`Function`并通过 lambda 表达式实现它。该代码无效并会导致编译错误。这是因为你不能在 lambda 表达式内部声明与外部方法变量同名的参数或局部变量。`generateSquareRoot`方法接受一个名为`num`的参数，并在 lambda 表达式使用了相同的名称，这导致了编译错误。可以通过重命名方法参数或 lambda 表达式参数来修复它。

### 215. 编写一个函数式接口，使得以下 lambda 表达式可以工作。

`(input)–> input.toUpperCase();`

**答案：**

上面的代码段指定了一个接受`String`值、将其转换为大写并返回的 lambda 表达式。因此，它可以用于实现函数式接口：

```java
@FunctionalInterface
public interface Interface1 {
    public String doSomething(String input);
}
```

此代码定义了一个名为`Interface1`的函数式接口。它有一个接受`String`作为输入并返回`String`方法。

### 216. 说明如何使用 lambda 表达式创建一个新线程。

**答案：**

`java.lang.Runnable`接口用于创建新线程。Java 8 将此接口指定为函数式接口，因此你可以使用 lambda 表达式实现它。以下代码演示了这一点：

```java
Runnable r = ()–> {
    System.out.println(“Starting Thread..”);
    //其他代码
};
Thread myThread = new Thread(r);
myThread.start();
```

在这里，`Runnable`接口通过一个包含简单`Sysout`语句的 lambda 表达式实现。使用该`Runnable`实例创建新的`myThread`对象。调用`myThread.start()`方法将产生新线程。

# 第三章

## Streams

### 217. 解释创建 Stream 的不同方法。

**答案：**

有多种方法可以创建 Stream。如下：

a. 你可以直接从值流创建一个列表：

```java
Stream<String> values = String.of(“Red, “Blue”);
```

b. 你可以从集合创建一个 Stream：

```java
List<Integer> numbers = Arrays.asList(1,2,3,4);
Stream<Integer> stream = numbers.stream();
```

c. 你可以从数组创建一个 Stream：

```java
int[] numbers = new int[] {1,2,3,4};
IntStream arrayStream= Arrays.stream(numbers);
```

### 218. 用代码示例解释 Stream filter 操作。

**答案：**

`Stream.filter()`操作可以根据某些条件过滤`Stream`。因此，它会创建一个仅包含符合指定元素的新的`Stream`。它接受一个`Predicate`实例作为参数并根据指定的谓词过滤流中的元素。以下代码演示了这一点：

```java
Stream<Integer> numbers = Stream.of(7,3,9,6,1);
Stream<Integer> output = numbers.filter(num–> num > 5);
```

这段代码创建了一个包含某些 Integer 值的`Stream`。然后，它调用了`filter()`方法，并使用一个 lambda 表达式检查输入数字是否大于 5。因此，输出的`Stream`将仅包含那些大于 5 的数字。

### 219. 解释 Stream 操作的类型。

答案：

Stream 操作可以分为以下几类：

a. **中间操作 (Intermediate)**：中间操作在`Streams`上操作并产生`Stream`输出。由于中间操作产生的是`Stream`，因此它们可以链式调用以执行一系列操作。中间操作示例包括`filter`、`map`、`sorted`。

b. **终端操作 (Terminal)**：终端操作在`Streams`上操作但产生非流的结果。因此，它们可以产生任何数据类型的结果。终端操作不能被链式调用。当多个`Stream`操作链式调用时，终端操作通常是最后一个操作。终端操作示例包括`count`、`anyMatch`、`allMatch`、`collect`。

### 220. 什么是并行流 (parallel stream)？请用代码示例说明如何创建并行流。

答案：

除了顺序流外，`Stream API`还支持并行流。并行流对`Stream`中的元素进行并发操作，从而提供性能提升。`Collection`接口新增了一个名为`parallelStream()`的新方法。可以使用它来获取与底层集合对应的并行流。以下代码演示了这一点：

```java
List<String> colours = Arrays.asList(“Red”，“Green”，“Blue”);
Stream<String> parallelStream = colours.parallelStream();
```

这段代码首先创建了一个名为`colours`的 String 值`List`。然后它在`colours` List 上调用了`parallelStream()`方法。这会返回一个与该 List 对应的并行流。在此流上执行的任何后续`Stream`操作都将在该`Stream`的元素上并发执行。

### 221. 如何将 Stream 转换回 Collection？

答案：

`Stream`接口有一个名为`collect()`的方法。它可以用于将`Stream`转换回`Collection`。以下代码演示了这一点：

```java
Stream<Integer> numbers = Stream.of(7,3,9,6,1);
```



`List<Integer> filteredList = numbers.filter(num -> num > 5).collect(Collectors.toList());`

这段代码首先创建了一个 `Integer` 的 `List`。然后它调用 `filter()` 方法来获取大于 5 的数字。之后，它调用了 `collect()` 方法。`collect()` 方法接受一个 `Collector` 作为参数。调用 `Collectors.toList()` 方法会返回一个能将输入 `Stream` 转换为 `List` 的 `Collector`。因此，`filteredList` 是一个只包含输入 `List` 中大于 5 的数字的 `List`。`Collectors` 类还有其他方法，如 `Collectors.toSet`、`Collectors.toMap`、`Collectors.toCollection`，它们可将 `Stream` 转换为其他类型的 `Collections`。

### 222. 下述代码段的输出是什么？

```java
Stream<Integer> numbers = Stream.of(10,15,20,25);
boolean anyMatch = numbers.anyMatch(num -> num%2==0);
System.out.println(anyMatch);
```

答案：

上面的代码段使用了 `Stream` 接口上的 `anyMatch()` 方法。如果输入 `Stream` 中的任何元素符合指定条件，该方法将返回 `true`。在这种情况下，它检查输入 `Stream` 中是否存在偶数。由于 `Stream` 中存在偶数，`anyMatch()` 方法返回 `true`。因此，这段代码打印以下输出：

```
true
```

### 223. `Stream` 和 `Collection` 之间有什么区别？

答案：

`Stream` 和 `Collection` 之间有几点区别，如下：

- `Collections` 实际上存储了数据。而流不存储任何数据，它只是在底层数据上执行某些操作。
- 当你对 `Collection` 执行操作时，`Collection` 会被修改。当你在从 `Collection` 获取的 `Stream` 上执行操作时，底层的 `Collection` 不会被修改。
- `Collection` 在创建后可以被修改。而 `Stream` 在构造后不能被修改。
- 你可以多次遍历 `Collection`。然而，你只能遍历一次 `Stream`。如果你希望再次遍历 `Stream`，是不可能的，你需要从底层源创建一个新的 `Stream` 并再次遍历。

### 224. 假设你有一个包含 `String` 值的 `List`。你想创建一个新的 `List`，消除原始 `List` 中的重复项并将 `String` 值转换为大写。你如何通过 `Stream` 操作实现这一点？

答案：

```java
List<String> fruits = Arrays.asList("Apple", "Mango", "Banana", "Apple", "Orange", "Mango", "Strawberry"); //Line 1
List<String> uniqueFruits = fruits.stream().distinct().map(str -> str.toUpperCase()).collect(Collectors.toList()); //Line 2
uniqueFruits.forEach(str -> System.out.println(str)); //Line 3
```

这段代码在第 1 行首先创建一个名为 `fruits` 的 `String` 值 `List`。第 2 行首先调用 `fruits.stream()` 获取 `fruits` `List` 上的 `Stream`。然后调用 `distinct()` 操作。`distinct()` 方法返回一个新的 `Stream`，其中仅包含输入 `Stream` 中的去重元素。接下来，调用 `map()` 操作。`map()` 操作可用于转换 `Stream`。它接受一个 `Function` 实例作为参数，并将该 `Function` 应用于 `Stream` 中的每个元素。这里使用了一个 lambda 表达式将 `Stream` 中的每个 `String` 转换为大写。最后，调用 `collect()` 方法并传入一个将 `Stream` 转换为 `List` 的 `Collector`。第 3 行打印 `uniqueFruits` `List` 中的所有元素。因此，这段代码打印以下输出：

```
APPLE
MANGO
BANANA
ORANGE
STRAWBERRY
```

### 225. 是否可以将数组转换为 `Stream`？请解释。

答案：

是的，可以将数组转换为 `Stream`。Java 8 在 `java.util.Arrays` 类中添加了一个 `stream()` 方法。该方法有许多重载版本，可以接受不同数据类型的数组并将数组转换为 `Stream`。以下代码演示了将一个 `Integer` 数组转换为 `Stream`：

```java
int[] numbers = {10,20,30};
IntStream numberStream = Arrays.stream(numbers);
```

这段代码首先创建一个名为 `numbers` 的 `int` 数组。然后它使用 `Arrays.stream` 方法传递输入数组。`Arrays.stream` 返回一个 `IntStream`，它是 `Stream` 接口的原始类型特化。就像 `IntStream` 一样，Java 8 还添加了 `DoubleStream` 和 `LongStream`，它们分别在用 `Arrays.stream` 方法处理 `double` 或 `long` 数组时返回。

### 226. 假设你有如下的 `Employee` 类：

```java
public class Employee {
    private String name;
    private int salary;
}
```

并且假设有一个如下的 `Employee` 对象 `List`：

```java
List<Employee> employees = new ArrayList<Employee>();
employees.add(new Employee("John",10000));
employees.add(new Employee("Ana",15000));
employees.add(new Employee("Tia",8000));
```

**如何使用 `Streams` 创建一个根据 `Employee` 工资排序的新 `List`？**

答案：

```java
List<Employee> sortedList = employees.stream().sorted((emp1, emp2) -> emp1.getSalary() - emp2.getSalary()).collect(Collectors.toList());
sortedList.forEach(emp -> System.out.println(emp.getSalary()));
```

这段代码首先获取 `employees` `List` 上的 `Stream`。然后它调用 `sorted()` 操作。`sorted()` 方法接受一个 `Comparator` 作为输入。这里，`Comparator` 通过 lambda 表达式实现，用于比较 `Employee` 对象的工资字段。最后，调用 `collect()` 方法将 `Stream` 转换回 `List`。因此，这段代码打印以下输出：

```
8000
10000
15000
20000
```

方法引用（Method reference）是 `Java 8` 引入的一种新运算符。它是 lambda 表达式的快捷运算符，用 `::` 符号表示。

方法引用有以下几个优点：

a. **它们避免了代码重复**：有时，你的代码中可能已经有一个方法，其代码与你想在 lambda 表达式中指定的代码相同。在这种情况下，方法引用是非常有用的。因此，你不需要在 lambda 表达式中重新编写代码，而是可以通过方法引用引用现有的方法。

b. **它们让代码更简洁**：方法引用在 lambda 表达式的基础上更进了一层。通过将代码从 lambda 表达式移动到单独的方法中，帮助代码变得更加简洁。

### 228. 方法引用的不同类型有哪些？

答案：

方法引用有 4 种类型。如下：

a. **静态方法引用**：当通过方法引用运算符引用类的静态方法时，就会发生这种情况。其语法如下：

`class::staticmethod`

b. **实例方法引用**：当通过方法引用运算符引用类的实例方法时，就会发生这种情况。其语法如下：

`object::instancemethod`

c. **构造器引用**：当通过方法引用运算符引用类的构造器时，就会发生这种情况。其语法如下：

`class::new`

d. **任意方法引用**：当访问类的某个实例方法但不是在任何特定对象上时，就会发生这种情况。其语法如下：

`class::instancemethod`

### 229. 请出一个静态方法引用的例子。

答案：

当通过方法引用运算符访问类的静态方法时，就会静态方法引用。以下代码演示了这一点：

```java
public class MethodReferenceDemo {
    public static boolean checkIfNumberGreaterThan8(int num) {
        return num > 8;
    }
    public static void main(String[] args) {
        Predicate<Integer> numberChecker = MethodReferenceDemo::checkIfNumberGreaterThan8;
        boolean flag = numberChecker.test(10);
    }
}
```

在这里，`MethodReferenceDemo` 类有一个名为 `checkIfNumberGreaterThan8()` 的静态方法。该方法检查输入数字是否大于 8，并返回相应的布尔值。在 `main` 方法中，定义了一个 `Predicate`。然而，并没有使用 lambda 表达式来实现该 `Predicate`，而是通过方法引用运算符引用了现有的 `checkIfNumberGreaterThan8()`。由于 `checkIfNumberGreaterThan8()` 是静态方法，因此使用了类名后跟方法名。

### 230. 考虑以下 `Shape` 类：

```java
public class Shape {
    private String name;
}
```

**为了让下面的代码有效，此类需要哪些更改？**

```java
List<String> shapeNames = Arrays.asList("Circle", "Triangle");
List<Shape> shapes = shapeNames.stream().map(Shape::new).collect(Collectors.toList());
```

答案：

上面的代码创建了一个名为 `shapeNames` 的 `String` 值 `List`。然后它使用 `Stream.map()` 操作创建了一个名为 `shapes` 的 `Shape` 对象 `List`。代码使用构造器引用通过 `String` 形状名称创建一个新的 `Shape` 对象。因此，`Shape` 类需要一个接受 `String` 值作为输入的构造器，如下：

```java
public Shape(String name) {
    this.name = name;
}
```

### 231. 解释 `String::toUpperCase` 是什么类型的方法引用。

答案：

`String::toUpperCase` 是任意方法引用的例子。它引用 `String` 类的 `toUpperCase` 方法，但不是在任何特定对象上。这通常在遍历 `Collection` 或 `Stream` 时使用。例如，假设你想将 `List` 的所有元素转换为大写字母。你可以如下使用此 `String::toUpperCase`：

```java
List<String> colours = Arrays.asList("Red", "Blue", "Green");
List<String> upperCaseColours = colours.stream().map(String::toUpperCase).collect(Collectors.toList());
```

# 第 05 章
## DateTime API

### 232. 解释以下代码片段中的错误以及你如何修复它。

```java
LocalDate date1 = LocalDate.of(2018, 7, 24);
LocalTime time1 = date1.atTime(5, 30);
```

答案：

上面的代码片段首先创建了一个名为 `date1` 的 `LocalDate`。然后它在 `date1` 上使用 `atTime()` 方法并将结果赋值给名为 `time1` 的 `LocalTime` 对象。这会导致编译错误。`atTime()` 方法将当前时间对象中的日期与指定的时间结合并返回一个 `LocalDateTime` 对象。因此，你可以通过以下更改来修复上面的代码：

```java
LocalDateTime time1 = date1.atTime(5, 30);
```

这会将 `date1` 中指定的日期与时间 `5:30` 结合并返回一个 `LocalDateTime` 对象。

### 233. 请用适当的代码示例说明创建 `LocalDate` 的不同方法。

答案：

`LocalDate` 类有一些用于创建 `LocalDate` 的静态方法。这些如下：

a. 创建对应当前日期的 `LocalDate` – 可以使用 `LocalDate.now()` 方法，如下所示：

```java
LocalDate date1 = LocalDate.now();
```

b. 创建对应指定年、月、日的 `LocalDate` – 可以使用 `LocalDate.of` 方法，如下所示：

```java
LocalDate date2 = LocalDate.of(2018, 7, 24);
```

c. 创建对应字符串的 `LocalDate` – 可以使用 `LocalDate.parse` 方法，如下所示：

```java
LocalDate date3 = LocalDate.parse("2014-08-11");
```

### 234. 用代码示例说明如何检查一个日期是否在另一个日期之前。

答案：

`LocalDate` 类有一个方法 `isBefore()`。可以使用它来检查一个日期是否在另一个之前，如下：

```java
LocalDate date1 = LocalDate.of(2018, 7, 24);
LocalDate date2 = LocalDate.parse("2014-08-11");
boolean isBefore = date1.isBefore(date2);
System.out.println("isBefore-" + isBefore);
```

这段代码创建了日期对象 `date1` 和 `date2`。它在 `date1` 上调用 `isBefore()` 并传递 `date2` 作为参数。由于 `date1` 在 `date2` 之后，`isBefore()` 返回 `false`。

### 235. 解释 `ZonedDateTime` 类。

答案：

`ZonedDateTime` 类表示有时区信息的日期和时间。因此，除了年、月、日、时、分、秒和纳秒，它还有一个 `ZoneId` 组件。`ZoneId` 是 `java.time.ZoneId` 的实例并表示时区。大约有 40 个时区可以通过 `ZoneId` 表示。下面的代码显示了如何创建 `ZonedDateTime`：

```java
ZoneId zoneId = ZoneId.of("Asia/Kolkata");
ZonedDateTime zonedDateTime = ZonedDateTime.now(zoneId);
```

所以，上面的代码片段首先创建一个对应 `Asia/Kolkata` 的 `ZoneId`，这是 IST 时区。然后它根据系统时创建一个对应当前时间的 `ZonedDateTime`。

### 236. 下面代码片段的输出是什么？

```java
LocalTime localTime = LocalTime.of(7, 15);
System.out.println(localTime.minusMinutes(30));
```

答案：

上面的代码创建一个 `LocalTime` 实例。`LocalTime` 表示具有小时、分、秒和纳秒组件的时间。在这里创建了一个对应 `7:15` 的 `LocalTime` 对象。代码接着调用带有 `30` 的 `minusMinutes()` 方法并打印输出。`minusMinutes()` 方法从它调用的 `LocalTime` 上减去指定的分钟数。从 `7:15` 减去 `30` 分钟，时间将是 `6:45`。所以这段代码打印输出：

```
06:45
```

### 237. 如何使用 Java 8 DateTime API 获取对应日期的星期？

答案：

`LocalDate` 类有一个方法 `getDayOfWeek()`。你可以使用它来获取对应日期的星期，如下代码所示：

```java
LocalDate date = LocalDate.of(2018, 7, 24);
DayOfWeek dayOfWeek = date.getDayOfWeek();
System.out.println(dayOfWeek);
```



`LocalDate date = LocalDate.parse("2017–04–25");`

`System.out.println(date.getDayOfWeek());`

```
上述代码创建了一个对应于 `2017 年 4 月 25 日` 的 `LocalDate`。然后它在该日期对象上调用了 `getDayOfWeek()` 方法。该方法返回一个名为 `DayOfWeek` 的枚举。`DayOfWeek` 枚举拥有对应于每周每一天的值。由于日期 `2017 年 4 月 25 日` 对应于`星期二`，因此 `getDayOfWeek` 方法返回一个对应`星期二`的枚举值。因此，这段代码打印了下面的输出：

TUESDAY
```

### 238. 解释 `Period` 和 `Duration` 类的区别。

答案：

`Period` 和 `Duration` 都是由 `DateTime API` 引入的类，用于表示时间持续时间。然而，它们之间存在一些区别。如下：

- `Period` 表示以年、月、日为单位的时间间隔。而 `Duration` 表示以秒和纳秒为单位的时间间隔。
- `Period` 用于测量两个 `LocalDate` 对象之间的时间间隔。而 `Duration` 用于测量两个 `LocalTime` 对象之间的时间间隔。
- `Period` 通常用于测量较长的时间间隔，而 `Duration` 用于测量较短的时间间隔。

### 239. 假设你有一个 `yyyy/mm/dd` 格式的 `String` 日期。如何获取与该日期对应的 `LocalDate` 对象？

答案：

下面的代码演示了将 `yyyy/mm/dd` 格式的 `String` 日期转换为 `LocalDate`：

```java
String strDate = "2012/10/11";
LocalDate date = LocalDate.parse(strDate, DateTimeFormatter.ofPattern("yyyy/MM/dd"));
System.out.println(date);
```

`LocalDate` 有一个 `parse()` 方法，可以将 `String` 日期转换为 `LocalDate` 对象。`parse()` 方法接受 `yyyy–MM–dd` 格式的 `LocalDate`。在上述场景中，日期是 `yyyy/MM/dd` 格式，因此 `parse()` 方法无法直接工作。但是，`parse()` 方法有一个重载版本，它除了接受 `String` 日期外还接受一个 `DateTimeFormatter` 实例。可以通过静态方法 `DateTimeFormatter.ofPattern()` 创建 `DateTimeFormatter`。该方法接受一个对应于所需数据格式的 `String` 作为参数。在这里，代码创建了一个可以解析 `yyyy/mm/dd` 格式日期的 `DateTimeFormatter`。因此，这段代码打印了下面的输出：

`2012–10–11`

### 240. 下面代码段的输出是什么？

```java
LocalDateTime dateTime = LocalDateTime.parse("2014–12–28T08–45–00");
dateTime = dateTime.withYear(1998);
System.out.println(dateTime);
```

答案：

上述代码首先创建了一个 `LocalDateTime` 实例。然后它调用了 `dateTime.withYear()` 方法。该方法将被调用的 `LocalDateTime` 的年份组件更新为指定的年份。因此，在这种情况下，它将 `dateTime` 中的年份更新为 `1998`并将结果赋值给 `dateTime` 对象。因此，这段代码打印了下面的输出：

`1998–12–28T08–45–00`

### 241. 解释 `LocalDateTime` 和 `ZonedDateTime` 之间的区别。

答案：

`LocalDateTime` 和 `ZonedDateTime` 都是表示日期时间的类，但它们之间有以下区别：

- `LocalDateTime` 不包含时区信息，而 `ZonedDateTime` 包含完整的时区信息。
- `LocalDateTime` 用于表示不确定特定时区的时间，而 `ZonedDateTime` 用于表示特定时区的时间点。
- `ZonedDateTime` 提供了处理时区转换的方法，而 `LocalDateTime` 则没有。

### 242. 如何在 Java 8 中计算两个 `LocalDateTime` 之间的差？

答案：

你可以使用 `Duration` 类来计算两个 `LocalDateTime` 之间的差值：

```java
LocalDateTime dateTime1 = LocalDateTime.of(2023, 1, 1, 10, 0);
LocalDateTime dateTime2 = LocalDateTime.of(2023, 1, 1, 12, 30);
Duration duration = Duration.between(dateTime1, dateTime2);
System.out.println(duration.toMinutes());
```

在上面的例子中，`Duration.between()` 计算了两个 `LocalDateTime` 之间的差值。你可以使用 `toMinutes()`、`toHours()` 或 `toSeconds()` 等方法来获取特定单位的差值。

### 243. 如何在 Java 8 中修改 `LocalDateTime` 的年份？

答案：

你可以使用 `withYear()` 方法来修改年份。注意，由于 `LocalDateTime` 是不可变的，该方法会返回一个新实例：

```java
LocalDateTime dateTime = LocalDateTime.of(2023, 1, 1, 10, 0);
LocalDateTime updatedDateTime = dateTime.withYear(2024);
System.out.println(updatedDateTime);
```

### 244. 如何在 Java 8 中获取 `LocalDateTime` 的小时？

答案：

你可以使用 `getHour()` 方法来获取小时：

```java
LocalDateTime dateTime = LocalDateTime.now();
int hour = dateTime.getHour();
System.out.println(hour);
```

### 245. 解释 `LocalDateTime` 的格式化。

答案：

你可以使用 `DateTimeFormatter` 类对 `LocalDateTime` 进行格式化：

```java
LocalDateTime dateTime = LocalDateTime.of(2023, 10, 27, 14, 30);
DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm");
String formattedDate = dateTime.format(formatter);
System.out.println(formattedDate);
```

### 246. 如何将 `String` 转换为 `LocalDateTime`？

答案：

你可以使用 `LocalDateTime.parse()` 方法来转换字符串：

```java
String dateString = "2023-10-27T14:30";
LocalDateTime dateTime = LocalDateTime.parse(dateString);
System.out.println(dateTime);
```

如果字符串格式不是默认的 ISO-8601 格式，你需要提供一个 `DateTimeFormatter`。

`Optional<Integer> number;`

在这里，`number` 是一个 `Integer` 类型的 `Optional`。它可能包含也可能不包含值。

Java 8 引入 `Optional` 是为了避免与空检查相关的样板代码。有时，一个方法可能会返回 `null`。这可能导致 `NullPointerException`。为了避免该异常，调用方法的代码需要进行显式的空检查。这会使代码难以阅读。Java 8 的 `Optionals` 有助于避免这种样板代码。因此，不再需要显式的空检查，可以使用 `optional`。如果值存在，则可以获取它。

### 248. 如何创建 Optional？

**答案：**

`Optional` 类上有一些静态方法可以用于创建 `Optional`。它们如下：

a. `Optional.isEmpty`– 这会创建一个空的 `Optional`，即一个不含值的 `Optional`，如下所示：

```java
Optional<Integer> number = Optional.empty();
```

b. `Optional.of`– 这创建一个具有特定值的 `Optional`，如下所示：

```java
Optional<Integer> number = Optional.of(10); // 创建具有值 10 的 Optional
```

c. `Optional.ofNullable`– 这创建一个具有 null 或非 null 值的 `Optional`，如下所示：

```java
Optional<Integer> number = Optional.ofNullable(10); // 创建具有值 10 的 Optional
```

也可以用于创建一个具有 null 值的 `Optional`，如下：

```java
Optional<Integer> number = Optional.ofNullable(null);
```

### 249. 用代码示例解释 Optional.ifPresent 方法。

**答案：**

`Optional.ifPresent` 方法会在 `Optional` 中的值存在时对该值执行某种操作。要执行的操作被指定为一个 `Consumer` 实例。如果 `Optional` 是空的，则它什么都不做。下面的代码演示了这一点：

```java
Optional<String> strOptional = Optional.of("Test");
strOptional.ifPresent(str-> System.out.println(str.toUpperCase()));
```

这段代码创建了一个与值 `Test` 对应的 `Optional` `strOptional`。然后使用 lambda 表达式调用 `ifPresent` 方法，该表达式将 `Optional` 中的值转换为大写并打印它。因此，这段代码输出以下输出：

`TEST`

如果传入的 `Optional` 是空的，`ifPresent()` 方法什么都不做。

### 250. orElse 和 orElseThrow 方法之间有什么区别？

**答案：**

`orElse()` 和 `orElseThrow()` 都是 `Optional` 类上的方法。如果 `Optional` 中存在值，它们会返回该值。它们的区别在于当 `Optional` 中不存在值时会发生什么。

`orElse()` 方法接受一个值作为参数，如果在空 `Optional` 上调用，它将返回该值。下面的代码演示了这一点：

```java
Optional<String> strOptional1 = Optional.empty();
String strValue1 = strOptional1.orElse("Default");
```

在这里，由于 `strOptional1` 是一个空的 `Optional`，`orElse()` 方法返回值 `Default`。

`orElseThrow()` 方法如果在空 `Optional` 上调用，则会抛出一个 `Exception`。它接受一个 `Supplier` 实例作为参数，该实例返回一个 `Exception`。下面的代码演示了这一点：

```java
Optional<String> strOptional2 = Optional.empty();
String strValue2 = strOptional1.orElseThrow(()-> new IllegalArgumentException());
```

在这里，由于 `strOptional2` 是一个空的 `Optional`，`orElseThrow()` 方法抛出了 `IllegalArgumentException`。

### 251. 下面代码段的输出是什么？

```java
Optional<Integer> opInt1 = Optional.of(200); // Line 1
Optional<Integer> opInt2 = opInt.filter(num-> num > 100); // Line 2
System.out.println(opInt2.get()); // Line 3
```

**答案：**

`Optional` 类有一个名为 `filter()` 的方法，在上面的代码段中使用它。`filter()` 方法接受 `Predicate` 作为参数，如果 `Optional` 中的值存在，则将该 `Predicate` 应用于该值。如果满足 `Predicate` 中的条件，它返回 `Optional` 中的值值，否则返回一个空的 `Optional`。在这种情况下，第 1 行创建了一个值为 `200` 的 `Integer` 类型 `Optional`。第 2 行调用了 `filter()` 方法，并传入一个 `Predicate` 来检查 `Optional` 中的值是否大于 `100`。由于这是真的，`filter()` 方法返回一个值为 `100` 的 `Optional` 并将其赋值给 `opInt2`。因此，`get()` 方法返回了这个值。

因此，这段代码打印以下输出：

`100`

# 第 08 章

# 的改进

### 252. 用代码示例解释 forEach 方法如何工作。

**答案：**

Java 8 在 `Iterable` 接口中添加了一个名为 `forEach` 的新默认方法。`java.util.Collection` 接口扩展了 `Iterable` 接口，因此所有 `Collection` 类都可以 `forEach` 方法。`forEach` 方法有助于在不需要显式 `for` 循环的情况下遍历 `Collection`。下面的代码演示了这一点：

```java
List<String> colours = Arrays.asList("Red","Blue","Black","White");
colours.forEach(str-> System.out.println(str));
```

这段代码声明了一个名为 `colours` 的 `String` 列表。`forEach()` 方法被调用于这个 `List` 上。它接受一个 lambda 表达式并打印它。因此，这段代码打印以下输出：

`Red`
`Blue`
`Black`
`White`

### 253. Java 8 对 List 接口做了哪些改进？

**答案：**

Java 8 为 `List` 接口添加了如下方法：

a. `List.sort`: Java 8 添加了 `sort` 方法。它可以接受 `Comparator` 作为参数并对 `List` 进行排序。

b. `List.replaceAll`: Java 8 添加了 `replaceAll` 方法。它可以替换 `List` 中的所有值。它接受 `UnaryOperator` 作为参数，`UnaryOperator` 是 `Function` 接口的特化，接受一个输入并返回相同类型的结果。

### 254. Map.getOrDefault 方法是如何工作的？

**答案：**

Java 8 在 `Map` 接口中添加了 `getOrDefault` 方法。它接受一个需要检索值的键作为参数，以及一个默认值。因此，如果键存在，它返回对应的值；否则，它返回传入的默认值。下面的代码演示了这一点：

```java
Map<Integer, String> fruits = new HashMap<Integer, String>();
fruits.put(1,"Apple");
fruits.put(2,"Orange");
String fruit1 = fruits.getOrDefault(1,"Mango"); // 返回 apple
String fruit2 = fruits.getOrDefault(3,"Mango"); // 返回 mango
```



这段代码创建了一个名为`fruits`的 map，具有`Integer`键和`String`值。它向 map 添加了一些值。它首先使用`getOrDefault`方法检索键`1`的对应值，默认值为`Mango`。由于`Map`中存在键`1`的值，`fruit1`被赋值为键对应的值`Apple`。它接着使用`getOrDefault`方法检索键`3`的对应值，默认值为`Mango`。由于 map 中没有键`3`的值，`fruit2`被赋值为默认值`Mango`。

`Map.replace(key, value)`方法仅当键映射到某个值时才替换该值。在上面的示例中，键`1`映射到值`Apple`，因此`replace()`方法将值`Apple`替换为值`Mango`。`Map.replace(key, oldValue, newValue)`仅当键映射到指定的旧值时才替换该值。在上面的示例中，键`2`映射到值`Orange`。因此，第 2 行的`replace`方法将值`Orange`替换为值`Banana`。此外，键`3`映射到值`Strawberry`。因此，第 3 行的`replace`方法没有替换值，因为键`3`没有映射到`Blackberry`。

## 256. 解释`Iterator`和`SplitIterator`之间的区别。

**答案：**

`Iterator`和`SplitIterator`用于遍历`Collection`中的元素。然而，这些接口之间存在一些区别。具体如下：

- `Iterator`接口从 Java 的早期版本就开始存在。`SplitIterator`是 Java 8 引入的新接口。
- `Iterator`接口仅支持顺序处理。`SplitIterator`同时支持顺序处理和并行处理。
- `Iterator`可以用于遍历`Collection`。`SplitIterator`既可以遍历`Collection`也可以遍历`Stream`。
- `Iterator`只允许单独遍历`Collection`中的元素。而`SplitIterator`既允许单独遍历`Collection`中的元素，也可以批量遍历。

# 第 09 章

## 杂杂

### 257. `CompletableFuture`类相比于`Future`接口有哪些优势？

**答案：**

在 Java 8 之前，Java 拥有`Callable`类和`Future`接口。它们可以用于返回异步计算的结果。然而，`Future`接口存在几个问题。`CompletableFuture`通过以下方式解决了所有这些问题：

- `Future`无法手动完成。因此，如果任务挂起，就没有办法手动完成该任务。而`CompletableFuture`有一个名为`complete()`的方法，允许手动完成任务。
- `Future`有一个名为`get()`的方法可以返回计算结果。然而，该方法会阻塞直到结果可用。因此，如果你想对`Future`的结果执行任何计算，你必须等待结果可用。而`CompletableFuture`允许在计算结果上附加回调函数。这些回调会在结果可用时执行，因此不需要等待。
- `Future`接口没有任何异常处理机制。而`CompletableFuture`有一个名为`exceptionally()`的方法，允许在发生异常时运行替代代码。

### 258. 什么是`StringJoiner`？请用代码示例进行解释。

**答案：**

`StringJoiner`是 Java 8 引入的新类。它帮助连接由分隔符隔开、并具有前缀和后缀的字符串。下面的代码演示了这一点：

```java
StringJoiner strJoiner = new StringJoiner(“–”,”[“,]”); //Line 1
strJoiner.add(“cat”); //Line 2
strJoiner.add(“dog”); //Line 3
strJoiner.add(“mouse”); //Line 4
System.out.println(strJoiner); //Line 5
```

这段代码创建了一个`StringJoiner`。它使用冒号（`:`）作为分隔符，使用方括号（`[]`）作为前缀和后缀。然后它调用`add()`方法并传入一些字符串值。因此，这段代码输出以下内容：

`[cat:dog:mouse]`

### 259. 解释`Comparator.reverse`和`Comparator.reverseOrder`方法之间的区别。

**答案：**

`Comparator.reversed`和`Comparator.reverseOrder`都是 Java 8 添加到`Comparator`接口的方法。它们都有助于按反序排序`Collection`。然而，两者之间的区别如下：

- `Comparator.reversed`是一个默认方法，而`Comparator.reverseOrder`是一个静态方法。
- `Comparator.reversed`需要一个比较器存在。它简单地反转了该比较器。`Comparator.reverseOrder`不需要`Comparator`存在。它直接返回一个按反序排序的比较器。
- `Comparator.reversed`返回一个`Comparator`，该比较器在其调用的比较器上施加反序排序。而`Comparator.reverseOrder`返回一个`Comparator`，该比较器对`Collection`中元素的自然顺序进行反向排序。

### 260. 识别下方代码中的错误，并解释需要如何修复。

```java
public class Employee {
    private String name;
    private double salary;
    //构造函数, getters 和 setters
}

List<Employee> employees = new ArrayList<Employee>();
employees.add(new Employee(“A”,10000));
employees.add(new Employee(“B”,5000.50));
employees.add(new Employee(“C”,15000));
employees.sort(Comparator.comparingInt(employee–> employee.getSalary())); //Line 1
```

**答案：**

上述代码在第 1 行存在编译错误。`employees.sort()`方法配合`Comparator.comparingInt`使用。该方法接受一个`ToIntFunction`函数式接口作为参数，并根据`int`字段排序。然而，这里使用的表达式表达式返回的是`double` salary。因此这会导致编译错误。为了修复此错误，需要将第 1 行修改为：

```java
employees.sort(Comparator.comparingDouble(employee–> employee.getSalary()));
```

现在，使用了`Comparator.comparingDouble()`方法。该方法接受一个`ToDoubleFunction`接口作为参数，根据`Double`进行比较。

### 261. 解释`CompletableFuture.runAsync`和`CompletableFuture.supplyAsync`的区别。

**答案：**

`runAsync`和`supplyAsync`方法都可以用于异步执行代码。然而，两者之间的区别如下：

- `runAsync`方法不返回结果，因此返回`CompletableFuture<Void>`。`supplyAsync`方法从线程返回一个值。因此它返回`CompletableFuture<T>`。
- `runAsync`方法接受一个`Runnable`实例作为参数。而`supplyAsync`方法接受一个`Supplier`实例作为参数。
- `runAsync`方法在单独线程中执行`Runnable`实现。`supplyAsync`方法在单独线程中执行`Supplier`并返回`Supplier`产生的值。

### 262. 模块描述符是什么？解释模块描述符中可以包含的指令。

**答案：**

模块描述符是一个名为`module-info.java`的 Java 文件。它包含了关于模块的信息。它必须存在于模块的根目录下。下面的代码演示了模块描述符的结构：

```java
module demomodule {
    //optional directives
}
```

模块描述符可以一些可选指令。在模块描述符中可以某些指令如下：

a. `Name`：指定模块的名称。
b. `exports`：指定该模块中可供其他模块使用的包名。
c. `requires`：指定当前模块依赖的模块名称。因此，如果没有指定这些模块，当前模块可能无法工作。
d. `provides`：指定当前模块提供的服务。当模块作为服务提供者时，应使用此指令。
e. `uses`：指定当前模块消耗的服务。当模块是服务消费者时，应使用此指令。
f. `open`：指定当前模块中的类可以通过 Java 反射进行访问。

### 263. 包（package）和模块（module）之间有什么区别？

**答案：**

包和模块都是逻辑单元，并封装了一些 Java 文件。然而，它们之间有以下几点区别：

- 包从 Java 的早期版本开始就存在。而模块是在 Java 9 中引入的。
- Java 引入包是为了避免命名冲突，因为它允许在不同的包中具有相同名的类。Java 引入模块是为了将 JDK 模块化并提高安全性。
- 一个包包含一组相关的文件。而另一方面，一个模块包含一组相关的包。
- 包不需要包描述符，而模块需要一个名为`module-info.java`的模块描述符。
- 包不能独立部署；而模块可以独立部署。
- 包中的类可以通过反射可见的。而模块中的类除非在模块描述符中指定了`open`指令，否则通过反射是不可见的。

### 264. 解释 Java 9 对 JDK 做了哪些更改。

**答案：**

Java 9 做出了一些根本性的变化，这些变化利用了模块化。在 Java 9 之前，安装 JDK 后会创建一个名为`jre\lib`的文件夹。它包含了所有的核心 jar 文件。当你安装 Java 9 时，不再创建`jre\lib`文件夹。相反，在 JDK 安装根目录下会创建一个名为`jmods`的文件夹。`jmods`文件夹包含与所有核心 Java 文件对应的模块。因此，不再有一个巨大的`rt.jar`，JDK 9 拥有独立的模块。

### 265. 考虑以下代码片段：

```java
package mypackage;

public class MyClass {
    public void doSomething() {
    }
}
```

**为了让这段代码作为模块的一部分进行部署，需要做什么？**

**答案：**

上面的代码指定了一个名为`MyClass`的类作为名为`mypackage`包的一部分。为了让这段代码作为模块的一部分进行部署，需要按照如下方式创建一个模块描述符：

```java
module mymodule {
    exports mypackage;
}
```

因此，这指定了一个名为`mymodule`的模块。它使用了`exports`指令并配合包`mypackage`，表示`mypackage`将供其他模块使用。

### 266. 解释`requires static`模块指令。什么应该使用它？

**答案：**

`requires static`指令用于指定可选依赖，即编译时需要但在运行时不需要的依赖。假设你开发了一个模块并需要某些第三方库，而你模块的终端用户永远不需要这些库。在这种情况下，你可以在定义模块时通过`requires static`指令指定该第三方库。因此，你模块的用户在编译时需要该第三方库，但在运行时不需要它。

# [第 02 章]

# [Stream/集合 改进]

### 267. Java 9 在 Stream 接口上做了哪些改进？

**答案：**

以下是 Java 9 对 Stream 接口做的一些改进：

a. `Stream.ofNullable`：Java 9 在`Stream`接口上添加了`Stream.ofNullable()`方法。这有助于创建一个值可能为 null 的 Stream。因此，如果向此方法传递一个非空值，它将创建一个包含该方法的值的 Stream，否则它将创建一个空流。
b. `takeWhile`, `dropWhile`：`takeWhile()`和`dropWhile()`方法都作用于`Stream`。它们可以被用于获取输入 Stream 的子集。
c. `Stream.iterate`：Java 9 添加了`Stream.iterate()`方法的重载版本，该版本接受一个`Predicate`并在`Predicate`指定条件为真时终止 Stream。

### 268. 下面的代码有效吗？如果无效，可以做什么来修复？

```java
Stream<String> strStream = Stream.of(null);
strStream.forEach(str-> System.out.println(str));
```

**答案：**

上面的代码是有效的，不会导致任何编译错误。然而，当它执行时，它会导致`NullPointerException`。这是因为你不能使用`Stream.of()`方法创建一个带有空值的 Stream。为了修复上面的代码，你需要进行以下更改：

```java
Stream<String> strStream = Stream.ofNullable(null);
str.forEach(str-> System.out.println(str));
```

Java 9 在`Stream`接口上添加了`ofNullable()`方法，帮助你创建一个空值的 Stream。因此，上面的代码不会产生 NullPointerException。

### 269. 识别下面代码中的问题并解释如何修复它。

```java
List<Integer> numbers = List.of(5,10,15); //Line 1
numbers.add(20); //Line 2
System.out.println(numbers); //Line 3
```

**答案：**

Java 9 为所有集合接口添加了静态方法`of()`。上面的代码在第 1 行使用该方法创建一个 Integer List。`of`方法创建的是不可变的 List。然而，第 2 行尝试向 List 添加值，这在代码执行时会导致异常。因此，为了修复上面的代码，你需要删除第 2 行。所以，你需要重写代码为：

```java
List<Integer> numbers = List.of(5,10,15,20); //Line 1
System.out.println(numbers); //Line 3
```

### 270. 你可以使用哪个 Java 9 方法创建一个字符串值的 Set？

**答案：**

Java 9 在`Set`接口上添加了一个静态工厂方法。你可以使用它创建一个包含字符串值的 Set。下面的代码演示了这一点：

```java
Set<String> months = Set.of("January","February","March");
```

这段代码创建了一个名为`months`的字符串 Set。它使用了`Set.of()`方法并指定的值。`Set.of()`有多个重载版本，可以接受 0 到 10 个参数，以及一个接受可变参数的版本。

### 271. 下面代码片段的输出是什么？

```java
Stream<Integer> oddNumbers = Stream.iterate(1, num-> num <= 20, num-> num+2);
oddNumbers.forEach(num-> System.out.print(num+" "));
```

**答案：**

在 Java 9 之前，有一个`Stream.iterate()`方法创建一个无限值的 Stream。Java 9 添加了`Stream.iterate()`方法的重载版本，创建一个有限的 Stream。因此，此方法接受一个额外的参数作为`Predicate`，并在`Predicate`为真时停止流。因此，这段代码将打印以下输出：

1 3 5 7 9 11 13 15 17 19

# [第 03 章]

# [杂项]

### 272. Java 9 对接口做了哪些更改？为什么？

**答案：**

Java 9 允许在接口中使用私有方法。在 Java 8 之前，接口只能包含抽象方法。Java 8 增加了对静态和默认接口方法的支持。默认和静态方法只是带有方法体的接口。Java 9 更进了一步，允许在接口中使用私有方法。私有接口方法允许代码重用。因此，如果一个接口有多个默认和静态方法，并且这些方法之间存在共同代码，可以将这些代码移动到私有方法中。下面的代码演示了这一点：

```java
public interface Sample {
    default method1(){
        //some code
        doSomething();
    }

    default method2(){
        //some code
        doSomething();
    }

    private void doSomething(){
        System.out.println(“Doing something..”);
    }
}
```




在这里，`doSomething()` 是私有接口方法，在默认方法 `method1()` 和 `method2()` 中。

### 274. 什么是 JShell？

答案：

`JShell` 基本是一个命令行工具。它允许你在无需创建类的情况下编写并运行 Java 代码。可以通过在命令提示符上输入 `jshell` 来启动它。一旦 `JShell` 打开，你可以输入任何 Java 代码，`JShell` 将显示代码的输出。例如，如果你输入以下内容：

```java
System.out.println(“Hello World”);
```

`JShell` 将打印文本“Hello World”。

`JShell` 为 Java 增加了 REPL 支持。REPL 代表读取-求值-循环（Read Evaluate Print Loop）。许多语言（如 Python）也提供 REPL 功能。

### 275. 下面代码段的输出是什么？

```java
Optional<Double> myDoubleOptional = Optional.of(10.0);

Optional<Double> defaultOptional = Optional.of(50.0);

double value = myDoubleOptional.or(()–> defaultOptional).get();

System.out.println(value);
```

答案：

Java 9 在 `Optional` 类上增加了一个名为 `or()` 的新方法。它接受一个 `Supplier` 实例作为参数，产生一个 `Optional`。它返回一个 `Optional`。因此，如果调用的 `Optional` 是非空 `Optional`，则返回该 `Optional`，否则返回由传递的 `Supplier` 生成的 `Optional`。在上面的代码段中，`or` 方法在 `myDoubleOptional` 上被调用，这是一个值为 10 的 `Optional`。由于这是一个非空 `Optional`，`or` 方法返回此值而不是 `defaultOptional`。因此，此代码打印以下输出：

```text
10.0
```

### 276. Java 9 对 try–with 语句做了哪些更改？

答案：

`try–with` 语句是 Java 7 引入的。它允许自动关闭资源而无需显式的 `close` 语句。例如，如果你正在编写写文件的代码，如果使用 `try–with` 语句，一旦 `try` 语句完成，`FileWriter` 就会自动关闭。它的缺点是，需要自动关闭的资源必须是 `try` 语句的一部分。因此，如果资源在 `try–with` 语句之外声明，则需要再次作为 `try–with` 的部分进行声明。Java 9 取消了这一限制。因此，通过 Java 9，你可以在 `try–with` 语句中使用在语句外部声明的资源。

### 277. Java 9 在 Optional 类上添加的 stream 方法有什么用处？

答案：

Java 9 在 `Optional` 类上添加的 `stream()` 方法可以将 `Optional` 转换为 `Stream`。这允许在 `Optional` 上应用所有的 `Stream` 操作。下面的代码演示了这一点：

```java
Optional<String> str = Optional.of(“Hello”);

Stream<String> strStream = str.stream();
```

这段代码定义了一个名为 `str` 的 `Optional`，其值为字符串 "Hello"。然后它使用了 `stream()` 方法。这将 `Optional` 转换为包含一个值的 `Stream`。因此，现在所有的 `Stream` 操作（如 `map`、`filter` 等）都可以应用到此流上。

### 278. 解释 ProcessHandle 类及其一些重要方法。

答案：

Java 9 增加了一个新类 `java.lang.ProcessHandle`。这有助于管理与操作系统相关的进程，并有助于与操作系统进行交互。该类的一些方法如下：

a. `current()`：这是一个静态方法，返回一个与当前进程对应的 `ProcessHandle` 对象。  
b. `isAlive()`：它返回一个布尔值，表示进程是否存活。  
c. `pid()`：返回进程的 ID。  
d. `children()`：返回一个 `ProcessHandle` 对象的 `Stream`，对应于当前进程的子进程。

### 279. 在下面的代码段中，解释第一行应该使用什么代码在下方的“预期输出”部分打印输出：

```java
Optional<Double> price = <code here>; //Line 1

price.ifPresentOrElse(val–> System.out.println(“Price is not null”), ()–> System.out.println(“Price not specified”));
```

**预期输出：**

```text
Price not specified
```

答案：

上述代码使用了 Java 9 在 `Optional` 类上添加的 `ifPresentOrElse()` 方法。该方法接受一个 `Consumer` 实例和一个 `Runnable` 实例作为参数。如果 `Optional` 中存在值，则执行 `Consumer`。如果 `Optional` 中不存在值，则执行 `Runnable`。在这种情况下，我们希望打印“Price Specified”输出。因此，`price` 必须是一个空的 `Optional`。第 1 行需要写为：

```java
Optional<Double> price = Optional.empty();
```




###我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。280. Java 9 引入的 `HttpClient` 有什么优势？

答案：

Java 9 引入了一个新的 `HttpClient` 类，可用于发送 HTTP 请求。在 Java 9 之前，可以使用 `UrlConnection` 和 `HttpUrlConnection` 类发送 HTTP 请求。新的 `HttpClient` 比这些类具有以下优势：

- `HttpUrlConnection` 只支持 HTTP 1.1，这是一个非常旧的版本。`HttpClient` 支持 HTTP 2.0，这是最新版本。
- 通过 `HttpClient` 编写的代码比 `UrlConnection` 清洁得多。
- `HttpClient` 通过 `CompletableFuture` 支持异步处理。因此，它有一个名为 `sendAsync` 的方法可以发送 HTTP 请求。它返回一个 `CompletableFuture`，可以在请求完成后用于获取响应。

### 281. 假设你扩展 `Thread` 类创建一个新线程并多次调用 `start` 方法，认为会发生什么？

答案：

当你第一次调用 `start()` 方法时，将产生一个新的 `Thread` 并执行 `run()` 方法中指定的代码。然而，在后续调用 `start` 方法时，会发生 `IllegalThreadStateException`。这是因为你不能启动同一个线程多次。线程遵循生命周期并在生命周期期间具有某些状态。当线程第一次创建时，它处于 NEW 状态。调用 `start()` 方法后，它进入 RUNNABLE 状态，一旦 `run` 方法完成，它进入 TERMINATED 状态。因此，当你对运行中的线程调用 `start` 方法时，它已经处于 RUNNABLE 状态。这会导致 `IllegalThreadStateException`。如果你想再次执行线程中的代码，你需要创建一个新的 `Thread`。

### 282. 假设有一个返回整数值的方法。代码位于 `try/catch/finally` 块中。`try`、`catch` 和 `finally` 块都有 `return` 语句。`try` 块返回 1，`catch` 块返回 -1，`finally` 块返回 0。如果发生异常，将返回哪个值？

答案：

在上述场景中，`finally` 块中的返回语句将被执行，因此将返回值 `0`。由于 `try` 块中发生了异常，`try` 块体的剩余部分将被跳过。因此，`try` 块中的返回语句不会执行。由于发生了异常，`catch` 块中的代码将执行。然而，由于存在 `finally` 块，`catch` 块中的返回语句也不会执行。`finally` 块中的代码将执行，`finally` 块中的返回语句也会执行。如果不存在 `finally` 块，`catch` 块中的返回语句将被执行。

### 283. 假设你在 `Base` 类中有一个静态方法。假设你在子类中有一个同名的方法。假设你创建了一个 `Base` 类对象，并给它赋值一个子类对象的引用，然后调用该静态方法。这样做是有效的吗？如果是，调用的是哪个版本的静态方法？

答案：

上述场景是完全有效的，不会引起任何错误。当执行此代码时，将调用基类中的静态方法。通常情况下，当你定义一个父类类型的变量并给它赋值一个子类对象，然后调用一个重写的方法时，将调用子类中定义的方法。这是因为 Java 使用赋值的对象而不是引用变量来确定要调用的重写方法版本。然而在上述场景中，父类和子类中的方法都是静态的。静态方法不能被重写。因此，如果你在基类中有一个静态方法，在子类中有一个同名方法，这并不是重写的例子。相反，这被称为“方法隐藏”（method hiding）。在这样的情况下，调用的方法版本不是由赋值给引用变量的对象类型决定，而是由引用变量的类型决定。在这种情况下使用了基类引用变量。因此，将调用基类中的静态方法。

### 284. 假设你在基类中有一个方法，它会抛出 `ArrayIndexOutOfBoundsException`。假设该方法在子类中被重写，并声明它会抛出 `RuntimeException`。你认为会发生什么？

答案：

上述场景说明基类方法抛出了 `ArrayIndexOutOfBoundsException`，这是一种未检出的异常（unchecked exception）。子类方法重写了该方法，并声明它会抛出 `RuntimeException`。这种情况是有效的，且不会引起任何错误。在方法重写中，子类方法不允许抛出比父类方法中声明的异常新或范围更大的已检查异常。然而，这条规则不适用于未检查异常。因此，子类方法可以自由声明任何未检查异常，且不会引起任何错误。如果子类方法在 `throws` 子句中声明了 `java.lang.Exception` 或其任何子类，将发生编译错误。这是因为 `java.lang.Exception` 是一种已检查异常（checked exception）。

### 285. 假设你有一个对象 `List`。你想将其作为参数发送给客户端应用程序，但想确保客户端应用程序不对其进行修改。你如何实现这一点？

答案：

为了确保客户端应用程序不对 `List` 进行修改，你需要获取该 `List` 的只读拷贝并将该拷贝返回给客户端应用程序。`Collections` 类有几个实用方法可以返回 `Collection` 的只读拷贝。例如，它有一个名为 `Collections.unmodifiableList` 的方法。该方法接受一个 `List` 作为参数，并返回一个输入 `List` 的只读拷贝。一旦通过此方法获得了 `Collection` 的只读拷贝，任何修改 `List` 的尝试（如添加或删除数据）都将导致 `UnsupportedOperationException`。因此，如果客户端应用程序尝试修改此 `List`，就会发生异常。

### 286. 假设你正在从数据库读取 10000 个 `String` 值。你需要使用这些值创建一个拼接的 `String`。实现此点的最高效方法是什么？

答案：

有多种方法可以拼接 `String` 值。最常用的方法是使用连接运算符（`+`）。然而，在性能方面这完全不高效，当你有大量 `Strings` 时应该避免使用它。这是因为 `String` 类是不可变的。因此，使用 `+` 运算符会导致创建大量的 `Strings`。Java 提供了 `StringBuffer` 类。它有一个名为 `append` 的方法，可以用于创建拼接的 `Strings`。由于它是可变类，它的性能更好。还有一个名为 `StringBuilder` 的类，它与 `StringBuffer` 非常相似。唯一的区别是 `StringBuffer` 是同步的，而 `StringBuilder` 不是。因此，与 `StringBuffer` 相比，`StringBuilder` 的性能略好。所以，如果同步不是问题，你可以使用 `StringBuilder`，否则可以使用 `StringBuffer`。

### 287. 假设你正在开发一个涉及非常大小数的数学计算的应用程序。考虑到精度很重要，你会为变量使用哪种数据类型？

答案：

通常情况下，程序员在处理小数时会使用 `float` 或 `double` 数据类型。然而，这些数据类型有一个缺点。在处理非常大或非常小的数字时，这些数据类型可能会丢失精度，导致结果不准确。因此，在精度重要的情况下使用这些数据类型不是好主意。Java 提供了一个名为 `java.lang.BigDecimal` 的类。该类克服了 `float` 和 `double` 数据类型的局限性。它在处理大小数字时不会丢失精度，因此提供了精确的结果。它具有对应于加、减、乘、除等算运算的方法。此外，它还支持许多其他操作。因此，它可以执行所有的数学运算并提供精确的结果。`BigDecimal` 的唯一缺点是性能。然而，如果精度优先于性能，则应该使用 `BigDecimal`。

### 288. 假设你正在开发一个多线程应用程序。出现了一个新需求，你需要存储键值对（key–value pairs）。在这样的情况下，最合适的 `Collection` 是哪一个？

答案：

`java.util.Map` 接口支持以键值对的形式存储数据。`Map` 接口最常用的实现是 `HashMap`。然而，`HashMap` 的问题在于它不是线程安全的，因此不适用于多线程应用程序。`Collections` 类有一个名为 `synchronisedMap()` 的实用方法。它接受一个 `Map` 作为输入，并返回与传入的 `Map` 对象对应的线程安全映射。因此，这种同步映射可以在多线程环境中使用。还有一个名为 `ConcurrentHashMap` 的 `Map` 实现。它是 `Map` 接口的线程安全实现，因此适用于多线程环境。`ConcurrentHashMap` 的性能略优于同步映射。同步映射会同步整个 `Map` 对象，因此当另一个线程正在使用 `Map` 时，不允许读取操作。而 `ConcurrentHashMap` 则没有同步整个映射，因此当另一个线程正在写入 `Map` 时，它允许读取操作。因此，虽然同步映射和 `ConcurrentHashMap` 都适用于多线程环境，但如果考虑性能，则应该使用 `ConcurrentHashMap`。

### 289. 假设你需要在应用程序中创建一些工具方法。创建此类方法的最佳实践是什么？你会把它们放在哪里？

答案：

大多数情况下，开发者会将工具方法放在一个单独的工具类（util class）中。然而，你应该尝试将工具代码放在与它相关的类中。例如，如果你有一个名为 `Car` 的类，并且你需要创建一个名为 `createCar` 的工具方法，它可以是 `Car` 类本身的一个静态方法，而不是拥有一个单独的 `CarUtil` 类。然而，在许多编程场景下，你可能需要将一些互无关的工具方法组合在一起。在这种情况下，你可以创建一个单独的类并在该类中创建静态工具方法。从 Java 8 开始，你也可以在接口（interface）中拥有静态方法。静态接口方法有助于将工具方法组合在一起，而无需创建类的实例对象。

### 290. 假设你作为 API 的一部分开发了一个名为 `FileWriter` 的接口。它有一个 `writeToCsv` 文件方法，可以将传入的内容写入 CSV 文件中。该 API 由不同的应用程序实现，这些应用程序提供了 `FileWriter` 接口的实现。现在，假设你被向接口中添加一个名为 `writeToExcel` 的新方法，将传入的内容写入 Excel 文件。你如何能在对 API 用户影响最小的情况下完成这一变更？

答案：

在上述场景中，需要向 `FileWriter` 接口添加一个新方法。简单地向接口中添加该方法会导致所有实现该接口的现有类出现编译错误，并要求所有类为 `writeToExcel()` 方法提供实现。最好的方法是将 `writeToExcel()` 方法作为默认方法（default method）添加到 `FileWriter` 接口中。默认方法是 Java 8 添加的一项新功能。它们允许你在接口中创建带有方法体的方法。实现接口的类不需要为默认方法提供实现。因此，在 `FileWriter` 接口中将 `writeToExcel()` 方法作为默认方法不会影响实现 `FileWriter` 的类。默认方法是由 Java 8 引入的。因此，如果你使用的是较早的 Java 版本，那么该解决方案将不起作用。在这种情况下，你可以创建一个 `FileWriter` 接口的新版本（例如 `FileWriterEnhanced`），该接口扩展了当前的 `FileWriter` 并在 `FileWriterEnhanced` 接口中添加 `writeToExcel()` 方法。在这种情况下，实现 `FileWriter` 接口的现有代码将按原样运行。任何需要 `writeToExcel()` 方法的代码将需要实现 `FileWriterEnhanced` 接口。

# 第 04 节

核心 Java

JAVA 8

JAVA 9

人力资源

## 第 01 章节

# 创造力

### 291. 你在哪里寻找灵感？

答案：

灵感可以来自任何地方，面试官希望看到你的灵感同样是多样化的。提到你获取灵感的多个地方，或者你发现自己进行头脑风暴的环境。此外，详细说明你是如何记录灵感或在稍后对其进行扩展的。

*作为示例：*

在整天的时间里，我不断在笔记本或手机上记录我以后想重新回顾的事项。我在工作会议期间获得灵感，通过听取同事面临的困难和进展来记录，并在稍后研究我们如何改进工作流程。当我的人脉发布他们在工作中正在追求的新创新事物时，我也会通过他们的网络获得灵感，看看我可能如何将这些创新应用到我自己的公司中。

### 292. 你在工作中如何实现创造力？

答案：

向面试官展示你能够在工作中善于利用资源并进行创新，同时又不超出公司价值观的范围，这是非常重要的。解释你的灵感通常源自哪里（例如可以包括列清单或思维图谱等练习），并将其与工作中某个需要创造力会有帮助的特定任务联系起来。

*作为示例：*

我曾被分配到一个安全与健康工作小组。大多数人在休息时本来就在散步，只是没有聚在一起。我报名参加了一个为期三个月的托管步行挑战，在活动中，人们在休息时仍然可以自己步行，但被鼓励与同事互动，并在跟踪进度方面进行一些健康的竞争。这最终促使更多的人站起来锻炼，同时也提振了士气和团队合作精神。

### 293. 你如何促使他人创造创意？

答案：

如果你处于管理职位，这可能要求员工提交特定数量的创意，或者完成定期的灵感产生练习，以锻炼他们的创造力肌肉。然而，你也可以通过创造更多自己的灵感来推动周围的人创造灵感。此外，与面试官讨论向他人提问作为激发灵感和改变的一种方式的重要性。

*作为示例：*

在每次员工会议上，我都鼓励员工带上他们自我们上次会议以来面临或面临过的问题或挑战，以及一个解决方案。我还鼓励员工参加定期的职业发展机会，无论是免费的网络研讨会、培训，还是阅读他们领域新发表的文章，并与团队分享他们学到的东西或热门话题。

### 294. 描述你的创造力。

答案：

尽量将此答案控制在专业领域，但如果你在职业经历之外的某些创造性领域拥有令人深刻目的背景，不要害怕将其也包含在答案中。关于创造力的最佳答案将与解决问题的能力、目标设定，以及在工作中寻找创新方法来处理项目或完成销售相关联。然而，办公室之外的热情也是很棒的（只要它们不会占用你的工作时间或精神空间）。

*作为示例：*

我参加参加一个工作之外的志愿者小组，该小组为无归者提供餐点。我工作的公司正在寻求与社区的联系，以及员工参与比他们特定职责更大事的方法，因此在获得公司许可的情况下，我举办了一场公司募活动，员工通过经营意大利面晚餐为无归者慈善机构筹款。这增强了员工的团队合作、凝聚力以及使命感。

## 第 02 章节

## 领导力

### 295. 在工作中，你倾向于获得更多的权威还是更多的责任？

答案：

这两个选择都有优缺点，面试官更有兴趣看到你能对该问题提供批判性的回答。获得更多的权威可能意味着更大的决策权，对于具有卓越领导能力的人来说非常有益；而更多的责任对于那些希望在职业生涯不断进步的人来说是一个增长机会。

*作为示例：*

我认为我在团队工作方面是“仆人式领导者”的良好范例。我有天生的领导力，人们自然地追随我。我是一个天生的项目经理，既能看到大局，也能看到细节。尽管如此，我会听取团队的意见，并鼓励和重视他们的每一个投入。这关键在于具有领导和做出简洁正确决策的能力，同时在需要时考虑并改进你的决策。

### 296. 当小组中的某人没有贡献应有的份额时，你会怎么办？

答案：

如果你正在应聘管理类职位，那么这个问题尤为重要——解释你将如何识别问题，以及你将如何找该个人单独谈来讨论他们的贡献。理解建立对话的过程非常重要，这样你就可以清晰地向个人传达你的期望，给他们回应的机会，并明确哪些地方需要改变。之后，与团队成员一起制定一份行动计划，确保他们的贡献与小组内其他人的水平相当。

*示例示例：*

我会说我在团队中的工作方式是“仆人式领导”的良好典范。我天生具有领导力，人们也自然而然地追随我。我是一个天生的项目经理，既能看到大局，也能关注细微的细节。尽管如此，我会听取团队的意见，并鼓励和重视他们的所有的投入。关键在于具备领导能力并做出简洁恰当的决策，同时考虑到整个团队的意见和想法，并在需要时改进你的决策。

### 297. 请告诉我一次你做过超出你权限范围的决定的经历。

回答：

虽然回答这个问题可能表现出你非常果断且自信，但也可能让雇主认为你是一个潜在的问题员工。相反，最好是将问题稍微重新聚焦，举一个你承担了额外责任的例子，因此不得不做出超出你正常权限的决定（但在特定情况下，这些权限是被授予你的）。讨论该决定的分量如何影响了你的决策过程，以及情况的结果。

*示例示例：*

我有一个客户打来电话，要求免除已经到期的月付款，因为他们觉得服务不尽如意。只有经理有权做出此项决定，而他那天恰不在公司。客户非常生气，并准备要取消服务。我推迟了当天到期的款项，并覆盖了由于客户欠款而设置的自动取消程序，并向经理保证他会在第二天会联系该客户。当他们能够交谈时，客户的问题得到了解决，他们决定继续使用我们的服务。

### 298. 你是否乐意就分歧问题向上级反映？

回答：

如果出现问题，雇主希望知道你会以及时且恰当的方式处理它。强调你过去很少与上级发生分歧，但如果发生这种情况，你完全乐意与相关人员进行讨论，以找到双方都满意的解决方案。

*示例示例：*

我曾向我的主管反映了报告中需要调整的地方，那份报告需要我进行格式化并提交给公司老板。当我向主管提到他们的错误时，他们立刻变得具有防御性，直到我向他们保证，我恰好发现了数字上的差异，并想引起他们的注意，以便他们可以在提交之前进行调整，这样他和我们部门看起来会更体面。我向他保证，我是在维护我们产出工作的完整性，并想尽力支持他。他感谢我，报告在没有错误的情况下被提交了。

### 299. 如果你在你上一份工作中担任负责人，你会做什么不同的改变？

回答：

无论你对如何让事情运行得更好有多种想法，或者对你上一份工作的管理层有什么意见，在回答这个问题时都请保持积极态度。对如何处理某事以提高效率或提高销售额进行深思熟虑的反是可以的，但务必确保你的所有建议都集中在如何让事情变得更好，而不是讨论消除浪费或负面情绪的方法。

*示例示例：*

我会本更侧重于对部门员工进行跨岗培训，这样我们在空闲时间，或者在团队成员的职责或职位出现工作量激增或紧急情况下，能够更好地互相帮助。这将有助于减少混乱和积压，让整个部门能够跟上进度并更加高效。

### 300. 你认为雇主是否应该对表现良好的员工进行表扬或奖励？

回答：

在完成艰巨工作后获得认可总是很棒，但有很多雇主可能会通过这个问题来推断你是否会是一个高维护需求的员工。虽然你可能喜欢奖励或赞扬，但向面试官传达以下这一点非常重要：你不需要赞誉来确认自己工作得良好。如果你正在应聘一个由你来赞扬其他员工的管理职位，请强调赞扬对提高团队士气的重要性。

*示例示例：*

我认为每个员工对赞扬和奖励的回应是不同的，甚至他们是否渴望这些也不同。有些人可能非常渴望并为了赞扬而努力，而有些人则不喜欢处于风灯下。确保员工意识到他们被雇佣是为了工作，并被要求完成任务是很重要的。尽管如此，员工也是人，会有压力大的日子，有私人的生活，有时仅仅是上班并努力工作本身就值得赞扬。让员工知道他们作为支持组织的人是受到重视的，而不仅仅是一个员工编号，这非常重要。每季度为全体员工提供免费午餐，提供音乐和食物，并对那些在特殊情况下表现优异的人给予认可，是保持士气和同谊的极佳方法。

### 301. 你认为领导者具备的最重要的特质是什么？

回答：

领导者在任何业务中都需要具备许多重要的技能，而这个问题最重要的部分在于，你要解释为什么你选择强调的这种特质是重要的。尝试选择一种特质，例如沟通能力或激励人的能力，并将其与你在团队中展示该能力的特定实例联系起来。

*示例示例：*

沟通是领导力的关键。在做出决定之前，考虑到所有方面和每种方案，但最终由你做出决定（无论这是否受欢迎），是领导者需要做到的。重要的部分是能够真正倾听并并他们的顾虑，让他们知道你重视他们的意见，然后向他们解释你为什么做出那个决定。大多数时候员工只是希望被听到。随时保持开放的沟通渠道对于维护员工之间的信任至关重要。我决定调整休假申请政策，要求员工在休假前至少两周申请，这引起了很大的抵触。一旦我解释了决定是基于休假冲突、人员配置不足、同事间的不公平以及利润损失，并且这对公司和员工都是好处，他们理解了。

### 302. 请告诉我一次你遇到意外问题的经历。你是如何处理的？

回答：

在压力下保持资源匮乏时的机变能力和冷静是非常重要的。面试官希望看到你能够系统化地处理问题，并且能够以有序的过程处理变化。清晰地概述情况，包括你所实施的流程的所有解决方案和结果。

*示例示例：*

作为我上一任雇主的安全官，我曾与部门主管参加一次非常重要的两点会议，这次会议已经在日程表上排了一个月，由于高管们的日程繁忙，无法推迟。与此同时，现场出现了一个紧急安全问题需要我赶过去处理。我在两个问题之间左右左右为难，于是让我的实习生带着我准备的演示文稿参加会议，解释了情况，并向他们展示了演示文稿。他解释了他自己能说明的问题，并对他们提出的问题以及他无法回答的事项进行了记录；我们安排在第二天进行跟进电话会议，以讨论我当时未在场无法回答的待办问题。我们在跟进电话中解决了所有遗留问题，并在第二天顺利推进了项目。高管们理解我所面临的困境，并对项目没有中断表示感谢。

### 303. 你能否举一个例子，说明你在上一份工作中是如何改进某个 X 目标的？

回答：

这里的重点应该是你所为公司创造了实实在结果的改进。提高效率无疑是业务中一个非常重要的因素，但雇主也在寻找具体的成果，例如销售额增长或开支减少。请详尽说明你的过程，尽可能提供具体的数字和证据，特别是在概述结果时。

*例如：*

我成功地将每个客户电话的等待时间缩短了 4 分钟，并通过建议使用一种软件简化了候名单流程，该软件让所有客服代表都能访问一个显示所有客户电话的显示器。显示器显示了有多少个电话处于激活、待处理或挂起状态（以及由哪个客服负责），以及他们使用的是哪条线路。客服可以轻松地挂断电话，查看看板并看到下一个哪条线路需要被接听。这改进了客服部门的工作流，使每天能多解决约 20 个客户问题，由于现在可以接收更多新订单，利润增加了 30%，并提高了客户的满意度和公司评分。

### 304. 请谈谈一次主管对项目提供的指导意见不够具体的经历。

回答：

虽然许多雇主希望员工遵循非常具体的指导方针而没有太大的决策权，但能够在指令模糊的情况下接手项目并独立完成工作同样重要。请举出你提出的必要问题的例子，并说明你是如何判断一个问题是需要向主管提的，还是你可以自己决定的。

*例如：*

在我主管准备去休假时，我有一个大型项目正在待处理。在她休假之前，她给了我另一个项目，但没有留下截止日期。我分析了该项目，确定这是一个新客户，我不想让他们感到困惑。我继续处理我的待办项目，并与新客户联系介绍自己，并安排了电话讨论他们的需求。这为我争取了时间，同时也让我获取了更多信息。由于截止日期还不清楚，而且并不紧急，所以我继续处理现有的工作，并在每天下午都留出时间开始处理新客户的项目。

### 305. 请谈谈一次你负责领导一个项目的经历。

回答：

带领面试官了解项目的过程，就像你对团队中的任何成员成员做的那样。解释项目的目标、必要的步骤，以及你是如何向团队分配任务的。包括结果，以及你通过这次领导机会中学到了什么。

*例如：*

作为在人力资源福利代表休假期间提供帮助的 HR 助理，我负责了一个大型机构的年度员工福利开放注册。我提前与经理进行了沟通，尽可能收集有关过去在时间表和工作流程方面哪些有效的信息，我自己增加了一些有用的改进，例如为即将的各种福利变化建立档案系统。在开放注册开始的前一周，我与 HR 部门开了会议，检查了每份表格，并向团队解释了我将如何分发每份表格，并为他们制作了实用的信息小抄，让他们放在办公桌上，以防员工来提问而我可能不在场。

整个过程非常顺利且有条理，员工们评价说非常简单。

### 306. 请谈谈你曾向前任雇主提出的某项后来被实施的建议。

回答：

雇主希望看到你对改进公司感兴趣并尽了自己的份力量——请提供一个具体的例子，说明你在上一份工作中做了什么来创造积极的改变。解释你是如何想到这个主意的，你的主管是如何接收的，以及在当主意实施时，其他员工是怎么想的。

*例如：*

我建议成立一个创新委员会，让员工聚集在一起讨论他们对工作场所产生的新想法。这些想法涵盖了广泛的内容，例如员工认可机制、零食卖机选项、客户大厅的变更，以及其间的任何细节。虽然并不是所有的想法都得到了管理层的采纳，但大多数想法的变体都得到了实施。这让员工对公司产生了主人翁和归属感，同时也提高了士气和团队协作。

### 307. 请谈谈一次你想到工作场所中某事可以更高效地完成的方法。

回答：

专注于你想法中积极的方面。重要的是不要负面地描绘你的旧公司或老板，因此不要详述某个特定系统是多么低效。相反，请解释一个你看到机会提高生产力或简化流程的情况，并用通用的分步骤方法说明你是如何实施一个更好的系统的。

*例如：*

我们部门曾将周五定为“归档日”，用于处理整整周收集的文件。虽然这绝对是很好的好主意，但如果某个同事请假了，或者我们某周有大量的归档工作，有时会出现我们在周五无法完成所有工作的情况，或者由于整周收到的大量文件而感到压力巨大。我建议我们在项目之间的空隙时间在整周内开始归档，这样就不会会堆积在某一天。我还注意到每天的最后半小时，有些同事会开始“收拾东西”，由于我们的工作性质，在最后一点时间里我们无法真正开始一个新项目，所以我们会开始收拾，然后在最后三十分钟归档，直到下班。这大大减少了堆积在周五的工作量，同时也保持了整周更高的生产力。

### 308. 领导和管理人员之间是否存在区别——哪一个是你更大的优势？

回答：

这两者之间是有区别的——领导者通常是很有主意的人，充满热情、富有魅力，并具备组织和激励他能力；而经理是那些确保系统运行、促进其运营、做出权威决策，并对从整体成功到细微决策的所有方面都承担巨大责任的人。考虑哪一种最适用于该职位，并解释你如何适应这一角色，提供你过去经验的具体例子。

*例如：*

我是一个优秀的领导者，因为我会花时间思考项目的所有可能方面，以及它将如何影响每一位负责该项目的员工。我尽力从每个角度来看待问题，预判并计划可能出现的问题，并关注可能顺利进行的事物。我以一种能够的方式推销想法，能够获得员工的支持，并让他们觉得自己是某项伟大事业的一部分。

### 309. 你在领导角色中表现更好，还是作为团队中的成员表现更好？

回答：

考虑面试官在你的职位中寻找什么样的素质，并表达你如何体现这一角色的是非常重要的。如果你是一个领导者，请突出你出色的见解、动力和激情，以及激励他人采取行动的能力。如果你在团队合作中表现出色，请关注你对当前任务的投入、合作与沟通能力，以及保持事情顺畅运行的能力。

*示例：*

虽然我可以在这两个角色中都表现得很好，但我发现自己更适合领导角色，因为这对我来说是非常自然的事情。即使在那些不是老板的职位上，也会有人向我寻求建议、讨论点子或寻求支持。我擅长项目管理，并将合适的人放在合适的位置，使他们的技能、性格以及工作道德得到最好的契合。如果我发现团队中的某人在跟进方面遇到困难，我能够找到创新的方法将他们包含，并将任务更改为可能超出他们舒适区的事情，在那里他们更适合为团队做出贡献。我发现了每位员工最好的品质，并激励他们采取行动。

### 310. 请讲述一次你在工作场所发现某些事情正在破坏你（或他人）效率的经历——你是如何处理的。

回答：

尽量不要过分关注你上一份工作的负面方面，而是选择一个你发现了积极且快速解决方案来提高效率的案例。关注你是如何注意到这个机会的，你是如何向主管提出解决方案的，然后改变是如何实施的（最重要的是，要谈谈你是如何领导这项变革倡议的）。这是你展示自己解决问题能力、资源利用能力和领导技能的绝佳机会。

*示例：*

我们仅有的一台打卡机经常面临着所有员工在同一时间下班时排出的长队。这会导致下班排队处出现混乱、员工感到不满、赶时间的员工完全跳过流程，以及员工为了“排队”而提前收拾东西下班。我建议在房间另一侧、靠近第二个入口处的地方增加第二台打卡机以缓解排队情况。这提高了效率，因为员工不再需要提前收拾东西浪费时间站在打卡机前，并缓解了一天结束时人们感到的烦闷情绪。

### 311. 你在目标和任务定义明确的工作中表现如何？

回答：

在回答这个问题时，考虑该职位本身是非常重要的——显然，如果你能够在目标和任务明确的工作中脱颖而出，那是最好的（特别是如果你处于初级职位或销售职位）。然而，如果你申请的是具有领导角色或创意性质的职位，请务必关注你额外喜欢的开发和实施自己想法所面临的挑战。

*示例：*

我喜欢拥有一套需要遵守的既定准则。这有助于简化流程，特别是在处理以客户为中心的公司的业务时。尽管如此，如果我看到某个可以改进的政策，我不介意将我的想法推向前沿，对其进行测试，如果有效，就实施它们。随着流程的改进，政策需要更新，并通知所有员工新的程序，以确保所有员工都达成一致。

### 312. 你在拥有巨大决策权的工作中表现如何？

回答：

面试官想知道，如果被录用，你不会是那种需要不断监督，或者在每一步都寻求建议、权威或反馈的员工类型。解释你在果断、高效的环境中工作得很好，并且你期待在你的职位上采取主动。

*示例：*

在在之前的职位中，我曾多次获得担任决策者的机会。虽然某些时候存在关于如何妥善执行工作的准则以及职位范围内的局限性，但在某些情况下，你必须在现场做出果断的决定。在这些时刻，我不介意在解决问题上发挥创意，并在事后告知我的上级发生的情况，以让他们处于知情状态。

### 313. 如果你看到另一名员工做不诚实或不符合道德的事，你会怎么办？

回答：

在目击另一名员工做不诚实事情的情况下，根据公司政策处理此类情况总是是最好的——如果你不知道这家公司的具体政策，可以简单说明你将根据政策进行处理，并向相关的负责人进行汇报。如果你了解公司的政策（例如，如果你正在自己的公司内部寻求晋升），最好根据政策具体列出你的行动。

*示例：*

这实际上取决于他们正在做什么。某些事情，如偷取大量资金、设备或任何将自己或他人陷入危险的事情，需要立即报告。然而，在某些时候，同事可能违反了政策或绕过规程以节省时间或降低成本，这可能对他们或公司是有害的。在这些情况下，我乐意亲自与同事讨论这个问题，看看我是否可以以任何方式帮助他们，并告诉他们他们所做的是错误的。他们可能甚至没有那是错误的，或者可能正处于艰难时期。如果在交谈之后他们继续这样做，我会乐意将问题提交给管理层。

### 314. 请讲述一次你自学并在以后帮助了你职业生活的经历。

回答：

这个问题很重要，因为它让面试官能够了解你对学习和进步的投入。选择一个纯个人生活的例子，并提供一个以教训结束的短故事。然后，清晰详细地解释这一教训如何转化为你在工作中可用的技能或实践。

*示例：*

我周末在一家志愿者组织工作。当该组织的主席无法领导一场募捐活动时，我必须介入并确保活动顺利进行、布置场地并向观众主持。我当时非常紧张，但这最终极大地帮助了我的公开演讲能力，在我们的下一次团队会议上，我能够向同事发言并展示我的项目，而不再感到紧张。我也被要求协调下一次员工活动，并使用了我在志愿者活动中学到的一些内容，例如座位安排和签到流程。我成为了工作团队中一个更具价值的成员。

### 315. 请讲述一次你在工作中开发项目项目想法的经历。

回答：

选择一个你开发的项目想法，该想法应与你在新职位中可能完成的项目具有典型性。概述你的想法来源，你为确保其成功和相关性所做的研究类型，项目中包含的步骤，以及最终结果。提供具体的对比统计数据，以展示其成功。

*示例：*

我们在招聘新销售人员时遇到了困难。我开发了更新我们销售职位描述的构想。我们之前的职位描述已经过时了，而且多年没有更新，在此期间，出现了许多新的软件工具，该职位的职责也发生了变化。销售团队聚在一起审查了当前的职位描述，并就他们认为应该在描述中增加或删除的内容意见，然后管理层进行了审查并做了相应的更新。一旦我们开始使用新的职位描述发布招聘广告，发现申请的合格销售专业人士人数增加了，他们更了解自己所申请的职位，而且契合度也更高。

### 316. 请告诉我一次你在项目中承担风险风险的经历。

回答：

无论这种风险涉及的是像在资源或时间有限的情况下承担重大项目这样复杂的事情，还是仅仅自愿承担一项超出你经验领域的任务，都要表现出你愿意走出舒适区并尝试新事物。提供具体的例子来说说明你所做的某件事为什么具有风险，并解释你在过程中学到了什么——或者这如何帮助你应对后来在职业生涯中遇到的某个工作目标。

*例如：*

我曾在一家公用事业公司的工程部门工作。我们遇到了一次紧急情况，社区的一根水管破裂了，社区关于水电费单的客户电话让我们应于交。在此期间，有两个客服代表请假，由于我当时正处于两个大项目之间，于是我提供了帮助。然而，我完全超出了舒适区，但我协助接听客户电话、回答基础问题，并记录了无法帮助的客户的姓名和电话，以便主管之后回访他们。我成功收了大约 100 名客户的款项，成功回答了大约 50 个问题，并为另外 25 个人记录了回电信息。我更多地了解了我在部门的工作是如何与客服联系的，以及客户向他们提出的问题类型以及他们面临的挑战。在这种情况发生后，我们两个部门开始更多地合作，甚至还举行了季度会议，就可能直接影响另一个部门工作的事目提供更新。

### 317. 对于一个想进入这个领域的人，你会告诉他们什么？

回答：

这个问题让你能够扮演专家的角色——并将向面试官展示你拥有知识和经验，可以配得上你简历上的任何培训和教育。将你的知识作为对进入该领域的人可能遇到的意外情况的建议，并确保以积极的建议结束，例如真正取得成功所需的工作的热情或奉献精神。

*例如：*

如果有人想进入销售领域，我建议他们首先查看有哪些相关的证书课程或学位选择可以帮助到该领域。我还会建议，如果你不习惯与他人交谈（无论是一对一还是在小组环境中），就去上一门公共演讲课程来增强你的信心。我建议学习销售的各种门道，并找到一个你真正热衷于销售的产品。如果你对自己的业务（尤其是销售）没有热情，你的表现不会很好。一旦你找到了热衷于销售的产品，就尽一切能学习关于它的一切。如果是产品，就去使用并测试它；如果是服务，就去尝试。记住在开始时给自己时间失败几次，这并不是世界末日，因为这有助于你学习。在工作中保持坚持，并学习哪些方法对你的目标受众有效，哪些无效。对客户和顾客保持积极的态度，在显得过于咄咄逼人或急切与过于胆小和冷淡不关心之间找到平衡，并且不要忘记在初次联系后进行跟进！

# 第 03 章

## 截止日期与时间管理

### 318. 请告诉我一次你没能遵守截止日的经历。

回答：

理想情况下，这种情况没有发生过——但如果发生了，请确保你使用一个较小的例子来说明情况，强调它发生已经多久了，并确保你已经尽了可能去确保遵守截止日期。此外，务必包括你在更好地管理时间或优先考虑任务方面学到的知识，以满足未来所有的截止日期。

*例如：*

我很少、如果说的话会错过截止日期。话虽如此，我记得大约两年前，我错过了一个向财务部门提交报告的截止日期。问题在于我一次性承担了太多的项目，而且同一周又冒出了几个“紧急”的意外问题。我没有寻求帮助，认为自己可以独立完成所有，并且不想给主管留下一份无法处理这项工作的印象。但结果结果是，我确实让主管失望了，当我坐下来和他讨论这个问题时，他们向我保证，只要我对自己的工作量保持开放沟通，他们就会帮助分担。从那时起，我确保向主管更开放地说明目前的工作量，并表达我对截止日期的任何担忧。从那以后我没有错过过截止日期，而且由于更开放的沟通，我和同事的关系以及部门内的生产力都得到了提高。

### 319. 你在工作时如何消除干扰？

回答：

随着技术的进步和沟通的便利，每天都会产生新的干扰。你的面试官会希望看到你仍然能够专注于，并且你的生产力没有受到影响，可以通过展示一个你为了保持专注而采用的日常流程来实现。

*例如：*

每天早上，我查看当天的任务并为我需要做的事情准备。我检查电子邮件、消息和其他个人物品，然后收起我的个人设备。我确保我的家人和朋友知道我只在休息期间查看消息，如果有紧急情况，他们有一个可以联系我的电话号码。在工作周的休息期间，我不参与很多社交媒体，因为那会拖累工作日。在休息时，我倾向于散步、阅读、和同事聊天几分钟，或者给家人或朋友发信息问问候，然后回到工作中。

### 320. 请告诉我一次你在一个有每周或每月定额要求的职位工作的经历。你成功的频率有多高？

回答：

你的数据将说明一切，你必须诚实地回答这个问题。如果你经常达到定额，请确保以自信的方式强调这一点，并不要羞于指出你在这一方面的优势。如果你的统计数据并不理想，尝试指出它们在你任职结束前呈增长的趋势，并展示对未来改进方式的反思。

*例如：*

我每个季度都能准时完成任务。我接受公司给我的定额，然后在这个基础上增加我自己的个人目标。这样，我就有一个更高的目标可以追求，并且当我只能达到公司目标而没有达到个人目标时，留有回旋地。我尝试不过分关注每日销售额，而是进行每月检查。这使我不会浪费太多时间在担心进度上，同时确保我处于目标范围内。

### 321. 请告诉我一次你完成了艰难截止日的经历，以及你是如何完成它的。

回答：

解释你如何优先安排任务，或者将任务的部分内容分配给其他团队成员，以应对紧迫的截止日期。具体说明截止日期之所以紧迫可能会有益处——确保清楚这并不是由于你个人的拖延导致的。最后，解释你是如何成功满足截止日期的，以及最终实现这一目标付出了什么努力。

*例如：*

由于同事突然缺席，我被分配了提交一份我从未做过的州报告的大任务。我利用空闲时间自己研究了该主题，联系了其他公司以了解他们是如何完成项目的，并找到了一个可以在工作时间内参加的在线培训。在获得老板的许可后，我将我的行政事务交给了部门秘书处理，直到我完成了州报告。我最终提前提交了报告，这为我的工作以及我作为员工的个人发展创造了价值，因为在那之后我被邀请协助其他项目，并在随后的评估期间获得了非常出色的绩效评定和加薪。

### 322. 当你手上有多个项目时，你如何保持条井有序？

答案：

面试官将希望看到你是否能够良好地管理时间和工作——而且能够同时处理多个项目，并给予每个项目应有的关注，是员工能力和效率的极佳体现。描述一个典型的设定目标和优先级排序流程，并向面试官解释这些步骤，以便他或她看到你管理时间的水平如何。

*例如：*

我会在笔记本和 `Outlook` 日历上维护一份持续更新的任务列表。每天早上上班时，我会查看我的 `Outlook` 日历，并回顾前一天在笔记本上添加的任务列表，在一天中优先考虑哪些是今天必须完成的，哪些可以等。对于本周晚些时候可以完成的任务，我利用 `Outlook` 中的日历功能将任务安排在特定日期，这样就会弹出提醒促我完成任务。在列表中不能等待的项目中，我选择最快的先完成。然后，我转而处理更复杂的任务。在白天如果出现打乱我计划的紧急事项，我会重新查看我的 `Outlook` 日历和手写列表，并进行相应的调整。我还会与同事保持沟通，如果他们有空闲，我会告诉他们哪些项目需要他们的协助。

### 323. 在工作日期间，有多少时间处于“自动驾驶”状态？

答案：

虽然你可能好奇雇主通过这个问题是否是在考察你的工作效率（例如，看你是否足够精通工作以至于不需要思考），但在几乎每情况下，雇主都希望看到你正在不断地思考、分析和处理职场中发生的事情。即使一切进展顺利，通常在某个地方也存在提高效率、增加销售额或生产力的机会。强调你对持续发展的投入，并传达出处于“自动驾驶”状态不利于实现那样的成功。

*例如：*

我的工作非常精练，也确实发现自己经常进入“自动驾驶”状态。尽管如此，当我完成一个项目或任务时，我会花时间审查已完成的项目以确保准确性。如果我在完成项目后还有空闲时间，我可能会尝试不同的完成方法，看看是否有改进流程的方法。有时确实有，有时则没有，但我不断寻找以最有效、最熟练的方式利用我的时间。

### 324. 你如何处理截止日期？

答案：

处理紧迫截止日期最重要的部分是优先安排任务并设定完成目标，以及分配或消除不必要的工作。引导面试官进入一个通用场景，并通过你组织和设定优先级的能力展示你的胜任能力，最重要的是保持冷静。

*例如：*

我利用 `Outlook` 日历处理那些我知道必须定期完成的持续任务。例如，每个周一我必须提交销售报告，每个周三我必须归档。如果有任何我需要准备的特殊项目，我会在日历上留出时间并提醒来准备即将到来的项目。我每天早上上班后花时间查看当天的任务，并在每天结束时也做同样的事，以确保我完成了所有需要的内容并为第二天做准备。如果我觉得由于某些原因无法满足截止日期，我会与我合作的部门沟通，看看是否需要进行任何调整。沟通是关键。此外，我也会时刻意识到，如果出现紧急项目，需要据此调整我的日程。

### 325. 请介绍一下你个人的问题解决流程。

答案：

你的个人问题解决流程应该包括概述问题、提出可能的解决办法，以及制定一个通向解决方案的清晰行动计划。保持你的回答简洁且有条理，用简洁、冷静的方式解释步骤，显示你即使在压力下也能保持头脑。

*例如：*

当我担任设备机械师工作时，我发现很难管理来自公司多个项目经理的涌入工作。他们中的每个人都开始安排我担任他们客户设备的技师。我试图对其中一些人说不，但被告诉我没有团队合作精神。最后，我与车间主任讨论了问题所在，并解释说我有团队合作精神，只是一天之内没有足够的时间完成他们交给我的所有工作。我在工作区域建立了一个调度板，在上面写下我有哪些工作、项目经理是谁、我在每个项目中处于什么阶段，以及预计完成时间。这让所有项目经理都能清楚地看到我的工作量，并更好地理解和欣赏我正在做的工作，同时也让他们能够决定是想找别人来维修客户的设备，还是等我有时间空档。

### 326. 工作中的哪些事情会让你感到压力？

答案：

由于最好远离负面因素，请保持这个回答简短明了。虽然回答“工作中没有任何事让你感到压力”在面试官看来可能不太可信，但请将回答控制在一个通用的原则上，例如团队成员没有履行承诺时，然后专注于你通常用来应对那种压力的解决方案，例如召开每周状态会议或在项目过程中设置阶段性截止日期。

*例如：*

## 处理团队合作中的挑战

当我的同事没有尽责时，如果这最终对我的工作产生了负面影响，我会感到压力很大。在这种情况下，我会保持冷静并与团队进行沟通。在能力范围内我会提供帮助，并寻找改善现状的方法。我会尽力保持积极愉快的态度，因为表现出负面情绪只会变得更加糟糕。

我曾与三位同事一起完成一个项目。我们每个人都有特定的任务，而且这些任务都是环环相扣的。如果其中一个人落后，所有人都会落后。其中一位同事一直落后于我们，导致整个项目进度滞后。我把那位同事拉到一边，询问他们是否需要帮助，并向他们解释他们的不及时导致了我们其他人的落后。我用非常非指责的方式进行了谈话，并保持氛围轻松。我针对他们如何提高及时性提出了有帮助的建议，然后建议我们团队每天召开晨会，查看每个人的进度。这增加了团队内部的透明度，并为那位同事提供了改进的机会打开了大门，最终帮助我们按时完成了了项目。

### 327. 你在工作中如何从外应对压力？当你感到压力时如何让自己冷静下来？

答案：

这是一个陷阱题——面试官想听到的是你在压力大时看起来没有任何变化，而且你不会让负面情绪干扰你的工作效率。至于你如何解决压力，最好是精通一种简单的解决方案，例如简单的深呼吸并数到 10，以此将自己重新回到眼下的任务中。

*例如：*

当我开始对工作中的某种情况感到压力时，我有时倾向于变得非常安静，花费太长时间来思考我想给出的回复或想传达给团队的信息。在这些情况下，我知道让团队知道“虽然我现在感到有点压力，但我没事的，我正在思考处理这种情况的恰当方法”很重要。我会确保自己深呼吸，保持冷静，微笑并说我要快速休息一下。我离开现场，到室外去，甚至在休息室里坐一会儿读读书。如果同事问我我在做什么，我只是很开玩笑地告诉他们，我需要一点时间来思考如何出色地回应这种情况；或者如果是一个更严肃的话题或情况，我可能会说我需要一点时间来充电。然后我会重新调整精神，回到我的团队。

### 328. 你擅长多任务处理吗？请举一些你成功处理多任务的例子。

答案：

有些人可以，有些人则不行。多任务处理最重要的部分是始终保持头脑清醒，明确需要做什么以及每个任务的优先级是什么。解释你是如何评估任务以确定优先级的，以及你如何管理时间以确保所有任务都能高效完成。

*例如：*

我很擅长多任务处理，因为我能够快速应对变化。我会一直运行着我正在处理的任务清单，所以如果我有中断或有紧急项目需要我离开现有的任务，我能够快速回到之前正在工作的内容。

### 329. 你每周工作多少小时？

答案：

很多人会被这个问题误导，认为回答更长的小时更好——然而，这可能会让雇主怀疑，为什么你必须工作这么多小时才能完成别人可以在更短时间内完成的工作。给出一个你完成一项工作所需的合理预估时间，并解释你在任何需要的时候都愿意加班。

*例如：*

如果我做的是一份每周 40 小的全职工作，那么那就是我的工作时间。老实说，我们是人……所以有时我身体不舒服导致动作慢了，或者在某些周里可能只工作了 38 小时左右，但我没有错过任何截止日期，一旦我感觉好些了，我就恢复了正常的工作速度和生产力时长。另一方面，如果我觉得需要加班，我只有在先获得主管许可的情况下才会这样做。有一次我遇到了紧急情况需要离开，但如果我当时直接离开，会让公司和客户的状况变得更糟，所以我多留了 30 分钟完成了任务，不过我立即通知了主管这个问题以及我多留下的原因，以便他们知情。

### 330. 你每天检查几次邮件？

答案：

虽然雇主希望看到你紧跟现代技术，但你每天检查邮件的次数相对较低也是同样重要的——也许每天二到三次（取决于你所在的具体领域）。在工作中，检查邮件通常是工作的极佳干扰因素，虽然保持联系很重要，但很多通信内容完全可以在早上和下午集中处理。

*例如：*

我每天大约检查三到四次邮件。通常情况下是在我到达办公室时、午饭前后以及我每天下班离开之前。有时办公室里事情很慢，我检查得较少；或者有时我正在等待包含启动某项任务所需信息的邮件，或者我正在与客户就某个重要话题反复沟通，所以我可能会更频繁地检查或回复。但在平均工作日，每天不超过四次。

# 第 04 章

## 客户服务

### 331. 什么是客户服务？

答案：

客户服务可以有很多意义——这个问题中最重要的考虑因素是你得出一个创造性的答案。通过提供一个超出基础定义的自信回答，展示你跳跃性思考的能力，这表明你真正考虑过自己对“照顾客户”的看法。你对客户付出的深思熟虑将说明一切。

*例如：*

客户服务基本上是你在工作日期间与他人的任何互动。如果你在客户服务部门工作，很简单——你接电话、收付款、解决问题。如果你在人力资源部门工作，你的客户可能是你服务的员工。如果你在销售部门工作，你的客户可能是你卖产品的人。客户服务展示了你如何与他人合作、你的态度以及你解决问题的能力。它是希望在工作期间遇到任何人时，以你所能的任何方式提供尽可能最好的服务。

### 332. 请讲述一次你为客户付出额外努力的经历。

答案：

重要的是你提供一个你真正付出了额外努力的例子——要小心把一件对你来说努力很大的事情，与雇主本该就要求你做的事情搞混淆。提供一个关于客户问题的例子，你做了什么来解决它，以及在你处理好情况后客户的反应。

*例如：*

我曾与一个新客户合作一项大型建筑工程。该客户本已准备好启动，但随后陷入了财务困境。我想要确保能帮到客户，于是制定了一项付款计划，让他们无需预先支付全部费用。我让他们签署了一份合同，注明我调整了付款计划，并且这是一次性的情况，以便确保他们意识到，如果未来再次使用我们的服务，可能需要再次预付。这位新客户对此感激尽尽，项目也顺利完成了。我们与该客户保持了长期的关系，并在随后的时间里从他们那里获得了更多工作，而且由于口碑相传，我们在社区内的知名度也得到了提升。

### 333. 你如何获得客户的信任？

回答：

这是一个非常开放式的问题，可以让你向面试官展示你的客户服务技巧。答案有很多种，最好是选择一个你有过良好经历的方面，例如“通过透明化的方式处理情况”、“提供奖励”或“关注出色的沟通”。提供你获得过的具体成功案例。

*例如：*

在赢得客户信任方面，开放的沟通总是有益的。我不会为了回答而随便给出任何答案，如果我无法立即回答客户的问题，我一定会让客户知道，并向他们保证我会找到正确答案并回复他们。然后，我会确保跟进。如果没有沟通和跟进，你将会失去他们的信任，他们会把业务转给其他地方。客户会感激你的诚实，以及你为他们提供正确答案和最佳服务所花费的时间。

### 334. 请描述一次客户感到不悦或焦虑的经历 - 你是如何处理该情况的？

回答：

与处理另一位同事的纠纷类似，回答这个问题最重要的部分是：首先设定场景，针对你特定的冲突解决风格提供分步指南，并以描述冲突解决的方式作为结束。在回答关于你自己的冲突解决风格的问题时，务必强调双方开放沟通和理解的重要性，以及达成妥协或其他解决方案的意愿。

*例如：*

不悦的客户只是想被倾听。倾听至关重要。我在计费呼叫中心工作时，曾有一位客户打来电话，抱怨她觉得每月账单的收费太高了。她在打电话时已经很焦虑了，我很快意识到，我越试图和她说话，她就越不开心。我花时间倾听，让她充分解释情况。我明显发现，她没有一直关注那些说明费率上涨的通知。我告知了她费率上涨的情况，并免除了第一个月的涨价部分，然后通过电子邮件将通知发给她审阅。第二天我给她打了电进行跟进，看她是否还有任何问题。

### 335. 什么时候可以为客户破例？

回答：

通常，在符合公司政策或根据主管的指示时，可以为客户破例。表现出对应当考虑例外情况的理解，例如当客户遭受了特定的困境、订单出现复杂问题或根据其要求时。

*例如：*

通常，公司有相关的协议和政策，以确保运营顺畅，所有客户都得到公平对待，同时确保公司盈利且不被他人利用。有时，客户可能会遇到异常或意料之外的困境，导致他们难以按时付款，在这些情况下，应该作为一次性的优惠服务给予延期。如果问题持续到下个月，我会查阅政策手册，看看是否还有其他可以提供的方案；如果没有，我会去找主管寻求帮助和指导。那时，通常由主管来做最终决定。

### 336. 当客户和老板同时需要你时，你会怎么办？

回答：

虽然你的客户和老板对你的需求不同，且对你作为员工的成功都至关重要，但最好的办法总是尝试先照顾客户——不过，关键在于向老板解释为什么客户迫切需要你，然后向老板保证你会尽快满足他或她的需求（除非是绝对紧急的事情）。

*例如：*

客户永远第一，老板在大多数时候也知道这一点。在老板可能与客户同时请求你帮助的情况下，你可以很容易接触老板看看他们需要什么，获取信息，并向他们解释，一旦你帮助完客户，就会立即着手那项任务。客户是你的业务来源，你需要确保他们得到及时的照料。

### 337. 客户服务最重要的方面是什么？

回答：

虽然许多人会简单地认为客户满意度是客户服务最重要的方面，但能够在客户服务情境下详述其他重要技巧也是重要的。解释为什么客户服务是业务中如此关键的一部分，并确保就你认为最重要的方面以合逻辑且深思熟虑的方式进行扩展。

*例如：*

客户服务最重要的方面是真诚。如果你没有真正能帮到客户的产品，或者你在提供客户服务时不真诚，公司将会失败。具备享受提供最佳客户服务的能力，并对帮助客户感到兴奋，会让客户也对与你做生意感到兴奋，并且他们感到自己得到了妥善对待。

### 338. 为客户建立低预期还是高预期更好？

回答：

你可以从两者中任其一回答这个问题（当然，前提是在确定公司对此事没有明确意见的情况下）。然而，无论你以哪种方式回答，都必须展示出全的思考过程以及你所选择方案的清晰理由。提供每个选项的优缺点，并包含使结果向你所选答案倾斜的最终观点。

*例如：*

在与新客户建立关系的初期，建立高预期是好的。这显示了你的自信，并让客户对与你共同的旅程感到兴奋。但在建立如此高预期的同时，你应该确保沟通现实的流程和时间表，让客户知道虽然你是他们的最佳选择，他们也会为选择了你的公司，但事情并非一夜之间就能完成，客户在等待产品交付时需要具备一定的耐心和理解。务必让他们知道等待是值得的，因为你是最好的！高预期、创造兴奋感以及让他们预知将发生什么的开放式沟通都是重要的。

### 339. 请描述一次你向同事传达困难或复杂想法的经历。

回答：

首先向面试官简要解释你的想法，然后概述为什么有必要向同事进一步拆解这个想法。最后，用简练的步骤解释该想法，这样面试官可以看到你的沟通能力和化繁为简单的技巧。

*作为示例：*

我当时有一个关于新工作调度系统的想法，并需要向团队展示。由于我的资源有限，而且我们还没有获得必要的软件，所以我做的是写了一份关于该想法的简要概述，并添加了带有互联网软件图片和屏幕截图的要点，然后将其汇成了一份 PowerPoint 演示文稿。我尝试思考会议期间可能出现的所有潜在问题和不同的视角，以便我准备好回答问题，并以一种吸引所有人的方式进行展示。我列出了一份优缺点列表，并针对每个可能出现的缺点给出了解决方案，让团队理解我已经经过了周全考虑并且准备充分。

### 340. 你在什么情况下觉得沟通起来比较困难？

回答：

即使是优秀的沟通者通常也会发现某些特定情况下很难进行有效沟通，因此不要害怕诚实地回答这个问题。务必解释为什么你提到的特定情况对你来说是困难的，并尝试选择一个不常见的答案，例如语言障碍或在困难时期，而不是像与上级交谈这类的情况。

*作为示例：*

在传达坏消息时，有时很难进行有效沟通。人们很容易感到压力，或者担心对方会有什么反应。重要的是，在感到自己准备好之前不要尝试沟通。要准备好倾听而不仅仅是说，回答你有的答案的问题，并对对方的想法或感受提供同理心。最重要的是要开诚且自信地沟通，让对方感到舒服，并对你或对当前局势有信心。

### 341. 良好沟通的关键要素包含什么？

回答：

良好沟通的某些要素包括：不受干扰的环境、听者的反馈，以及说话者在需要时进行的修改或澄清。在需要时可以参考基本的沟通模型，并提议与面试官进行角色扮演演练，以展示你的技能。

*作为示例：*

我发现，在进行严肃谈话时，确保保持眼神交流并避免手机或电脑等干扰是最好的。知道要求澄清是没问题的很重要，这样就可以避免出现任何误解。反思性倾听在任何沟通中都是极佳的工具，你通过在适当的时候重复对方所说的某些内容向对方展示你正在倾听（例如，“我听到你说对这个项目需要更多支持。让我们一起研究如何解决它，并为你提供你所需的支持”）。

### 342. 请讲述一次你通过沟通解决问题的经历。

回答：

在商业世界中，通过沟通解决问题是关键，因此从你之前的工作中选择一个具体的情况，说明你如何通过冲突中的有效沟通来处理一个复杂的局面。解释情况背景，以及你所采取的沟通步骤，最后讨论为什么通过沟通来解决问题对达成最终结果如此重要。

*作为示例：*

我的部门由于缺乏面对面的沟通，且仅通过电子邮件交流，产生了太多的误解。我们从不在同一时间查看邮件，从未在同一个频道上。我们继续在工作上重叠，任务分配不均，许多任务被遗漏。此外，还出现过通过电子邮件发布的指令不清晰的情况。我要求部门至少每两周举行一次会议，以确保我们都在同一个频道上，并留出不受干扰的时间来彼此交流并提供部门项目的更新。这段共处的时间增强了团队内部的凝聚力，并为开启更多沟通渠道提供了有效的方法。

### 343. 请讲述一次你与另一员工发生争议的经历。你是如何解决该情况的？

回答：

确保使用一个具体的案例，并逐步解释该场景、你采取了什么处理措施，以及最终是如何解决的。中间步骤，即你如何处理争议的，显然是最具决定性的——描述你使用的沟通类型，以及你如何通过妥协来达成决定。冲突解决是任何员工都应该具备的重要技能，也是面试官会寻找的技能，以判断你卷入争议的概率有多大，以及如果发生争议，他们被迫介入争议的概率有多大。

*作为示例：*

当我与一位同事发生争议时，我问他们是否可以谈谈这个问题。他们起初显然不感兴趣。我留给他们空间，并在几天后再次跟进，同时温和地传达我尊重他们，并想把这个问题抛在脑后以便我们都能向前迈进并更好地合作。我提议了几个不同的见面时间来讨论问题，并让他们选择最适合他们的时间。这让他们觉得自己处于某种主导地位并有了认同感。一旦我们见面，我再次解释了我想向前发展，并关注他们以及我们团队协作能力的积极特质，询问他们认为我们应该如何解决这个问题。我认真地倾听，并在他们结束后提供了我的建议。此后我们向前发展并将其抛诸脑后，能够比以往任何时候都更有效地沟通。从那以后，如果发生任何其他问题，我们也更愿意彼此寻求交流。

### 344. 你是能很快与人建立关系，还是需要更多时间来了解他们？

回答：

这两种选择都可以表现出良好的品质，因此确定哪种风格更适用于你。强调你在建立关系时所采取的步骤，而不是特定的风格，并简要总结为什么这种方式最适合你。

*作为示例：*

我觉得自己可以很快、很容易地与人相处并建立有效的工作关系。我总是注意不要过快地熟悉，因为任何关系的某些方面都需要时间来发展。虽然在职业生涯中我可能会遇到一些不太合拍的人，但我能够与他们保持专业的工作关系和相互尊重。

### 345. 描述一次你不得不通过处理办公室政治来解决问题的经历。

回答：

尝试在这个问题上关注积极面，这样你就可以将这种情况转化为你的优势。不要负面描绘你之前的雇主，而是使用一个极小的案例（例如文书工作或个人），来突出你是如何机智地处理特定实例的。举出为了达成解决方案而使用的沟通技能或问题解决能力的例子。

*作为示例：*

我曾多次需要处理在申请新工作许可时办公程序中涉及的“官僚主义”繁琐手续。尽管有时这让人非常沮丧且耗费时间，但我理解这是必要的，因为审查计划并确保工作符合安全和法律协议需要时间。我有一项需要加急的任务，所以我准备了一封解释情况的信，获取了该项目业主的声明，并让我的主管联系签署授权来陈述我的情况。我确保包含了这些理由：即如果项目停工或工期过长，会对社区产生负面影响；以及加紧工作对社区有益，而且这家店的开将产生连锁效应，在同一片空置地上带动其他商店开设。虽然工作最终没有在第二天完成，但它比原定计划提前了两周执行。

### 346. 请讲述一次你说服他人承担艰巨任务的经历。

答案：

这个问题是一个展示你领导力和沟通能力的绝佳机会。虽然提供具体的情况作为背景介绍很重要，但重点应放在你是如何说服他人的，以及哪些策略最有效。

*例如：*

我的一位同事不愿意帮我实施新的归档系统。这个项目将非常耗时且困难。我向她阐述了该项目如何使她个人以及整个部门受益，并让她的工作变得更简单，并告诉她这最终将是老板会赞赏的，也是她展现才华的机会。我通过告诉她她有很多非常棒的想法，并告诉如果她参与项目，由于她的知识和想法，将有助于项目更快、更高效地完成来激励她。让她感到很有价值并感到被需要，这激励了她提供帮助。

### 347. 请讲述一次你成功说服一个群体接受你的提案的经历。

答案：

这个问题旨在衡量你的资源利用能力和沟通技巧。请解释你是如何考虑小组内的不同视角的，并制作出一个对所有成员都有吸引力且有说服力的演示的。此外，你还可以通过提供有关提案的细节来增强提案本身的说服力，展示其执行良好。

*例如：*

我曾试图尝试购买一套新的发票软件，但只有我一个人感兴趣。他们不感兴趣是因为习惯了目前的软件，并且觉得太忙，没时间学习新系统。我研究了感兴趣的软件，整理了一份要点清单，并在计划会议之前发给每个部门成员，这样他们就有时间查看并带着问题来；然后我使用截图和关于软件如何让他们的工作更简单的深度信息向团队展示了该软件。我专门针对了两个同事的工作，指出了它将如何直接影响他们的工作并改进他们的流程。我给他们留了时间进行思考，并在做决定之前自己进行更多研究。

### 348. 请讲述一次你与他人发生矛盾的经历，事后看来，你希望自己能换一种方式处理。

答案：

这个问题的关键在于展示你的反思能力和学习过程。解释当时的情况、你当时是如何处理的、结果如何，以及最后你现在会如何处理。最重要的是，告诉面试官你为什么现在会以不同的方式处理——是因为你之前的方案给与对方之间的关系造成了压力，还是你希望自己当时能更坚定地维护自己的诉求？虽然你不应该详细阐述你以前处理得有多糟糕，但最重要的是展示出你已经成长，并通过这次冲突达到了更深层次的理解。

*例如：*

很多年前，我有一位同事完全不想听我说的任何话或采纳我的任何想法。他们非常固执，不愿学习新事。。我认为最好的办法就是避开他们，让他们做自己的事，避免冲突。事后看来，我本可以做得更好，去理解他们的观点以及他们可能对变化的恐惧，并更好地尝试去沟通新流程的必要性，向他们保证新流程可能会让他们的工作更轻松，并且我们都是一个团队，会在任何变化中互相支持。多年来，我的沟通能力以及意识到沟通对团队合作及最终对公司至关重要的认识已经有了巨大的提高。

### 349. 请讲述一次你调解其他员工之间冲突的经历。

答案：

对于应聘主管职位的人来说，这是一个特别重要的问题——从一个具体的情况开始，并解释你是如何与每个人进行有效沟通的。例如，你引入了折中方案吗？你做了行政决定吗？或者你扮演了调解人的角色，鼓励员工自行达成结论？

*例如：*

担任车间主管期间，我有多次担任两名员工之间纠纷的调解员。没有一种适用于所有情况的通用解决方案，因为每个员工都不同，每种情况或纠纷也各不同。我会仔细反思纠纷，并根据我所知的事实以及相关方的性格来决定需要做什么。大多数情况下，让两名员工坐在一起讨论，由我担任见证和调解员是非常有效的。我确保让每个人都有机会陈述发生了什么、他们的观点，以及这给他们带来了什么感受，或者他们认为最好的结果是什么。我确保始终指出双方都可以以不同的方式处理这种情况以避免纠纷升级，并指出了我认为他们身上的积极特质，我认为这些特质将让他们向前发展并更好地合作。我总是会进行跟进，以确保一切仍然进展顺利，并且如果他们再次遇到问题，我一直实行开放政策。

# 第 06 章

## 找工作与日程安排

### 350. 你在职位中最看重的前三点是什么？

答案：

你对职位最看重的前三点应该与雇主对员工要求的前三点相似，这样就能清楚地表明你与工作非常匹配。例如，雇主想要一个资历且具有实践经验的候选人——而你想要一个能够让你将教育和技能发挥到最大的职位。雇主想要一个愿意接受新挑战并开发新系统以增加销售或生产力的候选人——而你想要一个能推你并提供发展、创造和领导新倡议机会的职位。雇主想要一个能够成长并留在公司很长时间的候选人——而你想要一个提供稳定性并相信建立强大团队的职位。在在此之前研究雇主在寻找什么，并将你的目标与他们的目标匹配。

*例如：*

我寻找的三个点将是：应用我的技能产生积极影响的机会、成长和学习新事的机会，以及在一家具有积极使命的公司中获得稳定性。

### 351. 你是如何评估你想要加入的公司的？

答案：

虽然你可能觉得在面试中提出自己的要求有些不舒服，但雇主希望看到你对所申请的公司进行批判性思考，正就像他们也在批判性地审视你一样。不要害怕明确你对公司的需求（但要尽量确保这些需求与公司相匹配——最好在申请之前就确认），并在回答中表现出自信和果断。面试官想知道你是否是一个清楚自己想要什么、以及如何获得它的人。

**示例如下：**

我关注的是员工满意度、公司稳定性以及公司提供的服务类型。我希望确保自己是在一家员工反馈良好的公司工作，这样我就知道公司很好地照顾了那些公司成功的一线员工。我同时也希望公司能够持续存在很长时间，让我能与公司并肩成长。最后，我想在一家能为社区提供良好服务的公司工作，并且让我每天去上班时都充满热情。

### 352. 你能接受 __________ 的薪资工作吗？

回答：

如果这个问题的回答是“否”，那么在初次面试中这可能会是一个决定性因素，因为你不太可能有太大的议价空间。你可以尝试通过强调你的特定经验以及这些经验如何让你更有能力获得高薪来增加筹码，但要注意，在流程的这一阶段这样做非常困难。为了避免这种情况，请在申请之前了解行业标准，如果可能的话还有公司标准。

**示例如下：**

我完全接受从那个薪资水平起步。我很珍惜这个机会，并且知道我将在公司内不断成长。

### 353. 你为什么选择上一份工作？

回答：

通过了解导致你选择上一份工作的原因，面试官能够感受到激励你的动力类型。请将这些内容保持在专业范围内，并对职业生涯早期的阶段保持热情，以及你对进入该领域感到多么兴奋。

**示例如下：**

我选择上一份工作是因为那是一家非营利机构。虽然薪水低于私营公司，但我知道那是一次很好的经历，而且他们确实需要帮助。我的技能和知识对他们的公司是一个很好的补充，当时我靠这份收入就可以维持生活。这是一段很棒的经历，现在已经过去，我准备好在职业生涯上向前进一步并进入下一个水平，无论是否是非营利机构，我希望能提升我的职业生涯。

### 354. 距离你上一份工作结束已经多久了？为什么？

回答：

请确保对职业生涯中的所有空白期都做好解释，并确保这些理由是专业的。不要提到你在找工作可能遇到的困难，而要关注积极的事情，例如追求业外兴趣，或者可能回到学校接受额外的教育。

**示例如下：**

我大约在一年前辞去了上一份工作。我那份工作要求非常高，时间很长，而且财务状况也很好，但我花了一些时间休息，并专注于我感到自己错过的家庭时光。在那段时间里，我参加了一些职业发展课程，并重新明确了目标，现在准备好回到职场了。我感到精神焕然一发、接受了重新培训，并对我最感兴趣的领域领域重新集中了精力。

### 355. 你还在寻找其他哪些类型的工作？

回答：

这个问题的回答可以向面试官展示你既处于人才市场又很受欢迎。提到你申请过或看过的与你领域密切相关、或与你面试的职位相似的工作。不要提到那些走投无路的举动，比如你申请了一份与你领域完全无关的兼职。

**示例如下：**

因为我正在追求营销职业，所以我专注于公立部门的营销工作。我主要申请的是营销助理职位，如果我仍然能够参与营销工作，我也可能对行政角色感兴趣。作为一名成功的营销助理，我对自己的能力非常有信心，所以我正尽力想在那个领域拥有一席足之地，在那里我可以帮助公司通过新的创意营销策略开宽眼界。

### 356. 你在工作中曾受过纪律处分吗？

回答：

希望这里的答案是“否”——但如果你在工作中确实因为某些事情受过处分，那么请务必确保你能彻底解释清楚。详细说明你从该情况中学学到了什么，并反思在过程之后你是如何成长的。

**示例如下：**

我在工作中没有受过处分，但在重大项目期间，在向主管及时汇报进度方面，我收到过一些批评。我以前倾向于进入状态并按照自己的节奏推进以完成工作，当时并没有认为在没有出现任何问题的情况下，让主管了解最新进展是重要的。我想如果出了什么问题，那才是让老板介入的时候。经过讨论，我了解到主管实际上每周需要向高层提交报告，其中必须包含我的项目以及我在流程中的进度。得知这一点后，我意识到即使在一切顺利的情况下，让老板了解我的项目进展始终是重要的。

### 357. 你的时间安排如何？

回答：

你的时间安排显然应该尽可能开放，任何时间安排上的空缺都应该得到解释和合理解说明。避免询问假期或请假（以及其他福利），并向面试官传达你对工作的严谨态度。

**示例如下：**

我查看了工作时间，相信我的时间安排可以符合职位的要求。虽然我显然需要时间处理家庭和个人事务，但我愿意根据需要加班以支持机构。

### 358. 我可以联系你的现任雇主吗？

回答：

如果可能，最好让面试官联系你的现任雇主作为证明。然而，如果不联系雇主非常重要，请委婉地解释原因，例如你刚开始找工作，还没有机会告知他们你正在寻找其他工作。不过要小心这种理由，因为雇主可能会怀疑你是否会在为他们工作期间也寻找其他机会。

**示例如下：**

我完全介意你联系我的现任雇主。但我希望在获得条件录取（contingent offer）之后，给我时间先与老板沟通，以示尊重，这样他们才不会措不及。虽然他们意识到我最终可能会离开去发展职业，但由于我在组织中扮演着如此重要的角色，他们会对填补我的职位感到担心。

### 359. 你有任何可以为我们的业务介绍的宝贵人脉吗？

回答：

如果你能带来知识、推荐人或其他你的新雇主可以建立联系的人脉，那太棒了。但是，请确保你没有提供任何你任雇主的客户，或以任何方式违反合同协议。

**示例如下：**

我确实有一些来自其他机构的好人脉，他们使用与我在会计领域相同的软件。多年来，我们能够一起排除故障并解决问题，他们分享了许多很棒的新想法，帮助我处理出现的问题。我在这里会有很多支持。我还有几位企业主朋友，他们可以与你们的管理层分享他们在处理员工问题和新业务趋势方面的见解。

### 360. 你最快什么时候上班？

回答：

虽然你希望确保在公司对你有招聘意向时能尽可能尽快上班，但如果你还有另一份工作，请务必给他们至少两周的通知。尽管你的新雇主可能急于让你入职，但他们会希望雇佣一个因给予充分通知而受的员工，这样他们就不必担心你最终是否会将他们置于困境。

*示例：*

虽然我很渴望并期待与你们一起工作，但出于尊重，我更倾向于向现任雇主提前两周通知。这将留出时间处理收尾工作，并让我能够在我离开期间及之后帮助他们完成过渡。

### 361. 你的前任雇主会说你是为什么离开的？

回答：

这个问题的关键在于，雇主的回答必须与你对离职原因的回答一致。例如，如果你告诉雇主你离开是为了寻找一个职业发展空间更大的职位，那么你的雇主最好不要说你是因为缺勤太多而被解雇的。在求职过程中，诚实是关键。

*示例：*

我相信我的前任雇主会说我是为了成长机会而离开的。虽然他们对我离开感到遗憾，但我知道他们对我在那里的工作时间很满意，我很感激在那里工作期间学到的知识。

### 362. 你积极寻找工作多久了？

回答：

最好是你没有积极找工作太久，因为时间太长可能会让面试官怀疑为什么没有其他人雇佣过你。如果已经过了一段时间，请务必解释原因，并保持积极的态度。也许你还没有遇到过太多能为你提供足够挑战，或与你的教育背景和经验相充分匹配的机会。

*示例：*

我实际上并没有在特定时间内一直在找工作。通常，只有有人给我发他们认为我擅长或感兴趣的内容时，我才会看招聘广告，因为我之前并不急于离开我的前任雇主。我看到了这个招聘广告并感到非常兴奋，所以申请了。它看起来像是一个绝佳的机会，我觉得我非常合适。我无法错过这次面试的机会，以及在贵公司进一步发展职业的机会。

### 363. 你在什么情况下不来上班？

回答：

显然，唯一可以缺勤的情况是发生紧急情况或你真的生病了——所以现在不要开始提到你计划因假期或家庭生日而缺勤的时间。或者，你可以告诉面试官你对工作有多么投入，以及你总是努力做到全程投入，并在每次上班时都投入相同的工作，即使在你感到身体轻微不适时也是。

*示例：*

通常情况下，除非发生很多我才会缺勤。如果我只是流鼻涕我也会上班，我不是那种因为打了个喷嚏或轻微头痛就打电话请假的人。同时，我不想传染给别人，所以如果我觉得身体真的非常不适，我一定会留在家家里。此外，当然，如果发生了需要请假的家庭紧急情况，我一旦发现有需要，就会立即给我的主管足够的通知。我很擅长让老板了解情况。如果我预计会缺勤整天，我会告知老板任何可能需要处理的紧急任务，以确保没有任何事情落后太远，并保持完全透明。

### 364. 你是否曾被主管要求离开工作岗位回家一天？如果是，原因是什么？

回答：

这个问题的回答很可能是“否”，但是，如果你确实有过一天被送回家的经历，无论是因为生病太重无法工作、心情不好还是不听从，请尝试用这种方式表述：表现你理解了原因并在之后努力了改进。

*示例：*

我只被送回家过一次，那是我生病持续了将快一周时间的时候。我缺了两天工作，工作进度落后了。第三天我觉得身体好到可以上班，不想进一步落后。我没有发烧，感觉状态不错可以上班，于是我就去了，但几小时后我立刻感到精疲力竭、疲惫，显然我的状况并没有我想象中那么好。老板在我到达时问我是否确定自己可以上班，我说可以。几个小时后，她最终告诉我直接回家吧，因为由于我感到充血和虚弱，集中注意力变得越来越困难。我回家了，并庆幸这样做了。我睡了一觉，第二天回来。现在我更擅长先照顾好自己，确保自己状态良好后再上班，因为健康第一。

### 365. 你的出勤记录如何？

回答：

务必诚实地回答这个问题，但理想情况下，你已经付出了努力来证明你很少缺勤或迟到的事实。然而，如果你的出勤记录中有空隙，请用适当的原因简要解释，并确保强调你对工作的投入和可靠性。

*示例：*

我的出勤记录相当不错。我不能说我有完美的出勤记录，因为我是人，生过几次需要请假的病，或者有某些只有在工作期间才能完成的预约。除此之外，我坚持每天都准时出勤。在极少数迟到几分钟的情况下，我会让老板知道。

### 366. 你从哪里听到这个职位的？

回答：

这个问题看起来简单，但答案实际上能反映出你的很多信息。如果你是由朋友或在该公司工作的员工推荐的，这是一个提及你与他们之间关系的绝佳机会。然而，如果你是在招聘会或职业中介处听说的，你可能希望关注你发现这样一个机会时有多么高兴。

*示例：*

我是从一个朋友发给我时听到这个职位的。她觉得这很有趣，并且对这家公司评价很高。我通常不太在意招聘广告，但当我看到这一个时，我感到兴奋并感兴趣，不想错过这个机会。

### 367. 告诉我们在做招聘决策时，你还有什么想了解的。

回答：

这是你向面试官进行最后推销自己的绝佳机会——利用这段时间提醒面试官你为什么胜任该职位，以及你能为公司带来什么其他其他人无法提供的价值。表达你对能为一家拥有使命感的的公司工作感到兴奋。

*示例：*

如果你雇佣了我，你不会失望的。我对比这个机会感到兴奋，并渴望能够帮助贵公司成长。我的技能和经验似乎与职位完美匹配。我非常期待加入团队，并看到我能如何像贵公司使命所说的那样“为社区带来解决方案”。

### 007. 解释编译以下代码时会发生什么，并说明它使用的是方法重载还是方法重写。

### 008. 编写一个演示方法重载的 Java 代码示例。

### 009. 什么是多态？Java 如何支持多态？

### 010. 解释 Java 如何实现抽象。

## Java 基础

### 011. 声明 Java `main` 方法的可能方式有哪些？

```java



```
public static void main(String[] args) {}
```



# 第 1 部分 – Java 基础

## 声明与访问控制

- 012. 声明 Java `class` 的可能方式有哪些？
- 013. 你将如何定义一个 `Identifier`？
- 014. 无法为实例变量指定的修饰符有哪些？
- 015. 方法声明中可以指定的修饰符有哪些？
- 016. 引用变量在未被显式初始化时的默认值是什么？你将在代码中如何处理这个问题？
- 017. 解释关键字 `transient` 和 `native`。
- 018. Java 中的注释是什么？解释 Java 支持的注释类型。
- 019. 解释什么是 `JVM`、`JRE` 和 `JDK`。
- 020. 通过代码示例解释你如何读取用户输入的值。

## 数据类型、变量与数组

- 021. 声明 `short` 数据类型数组的可能方式有哪些？
- 022. 如何显式地将 `int` 变量强制转换为 `byte`？真的必要将 `int` 字面量转换为 `byte` 吗？
- 023. 给出一个隐式转换的示例。
- 024. 编写一段代码片段，演示如何将 `float` 值赋值给 `short` 变量。
- 025. `int`、`double`、`float`、`boolean`、`long` 和 `char` 数据类型的默认值是什么？
- 026. 在以下代码片段中，解释哪些行可以正常编译，哪些行会导致编译错误。
- 027. 解释编译以下代码时会发生什么。
- 028. 你被分配了一个任务，使用多维数组创建一个井棋游戏。以下哪种是初始化数组的正确方式？
- 029. 解释 Java 中的原始数据类型。
- 030. 给 `float` 变量赋值小数的可能方式有哪些？
- 031. 识别以下代码片段中的错误并解释如何修复它。
- 032. 你将如何将 `Octal`（八进制）和 `Hexadecimal`（十六进制）字面量赋值给 `int` 变量？
- 033. 在下面的代码片段中，哪些行会编译，哪些行会导致错误？
- 034. 编译并执行以下代码时会发生什么？
- 035. 考虑以下代码片段并解释其输出。

## 运算符

- 036. 在以下代码片段中，哪些行会导致编译错误？为什么？
- 037. 下列代码的输出将是什么？为什么？
- 038. 通过代码示例解释用于字符串拼接的运算符。
- 039. 以下代码的输出是什么？
- 040. 解释 `%` 运算符。
- 041. 以下代码的输出是什么？
- 042. 编译并执行以下时会发生什么？
- 043. 下列代码可以编译吗？如果是，输出是什么？
- 044. 以下代码的输出是什么？
- 045. 以下代码的输出是什么？为什么？
- 046. 以下代码片段的输出是什么？解释原因。
- 047. 解释自增和自减运算符。
- 048. 解释 `instanceOf` 运算符。

## 控制语句

- 049. 通过代码示例解释三元运算符。
- 050. 命名判断语句。
- 051. 循环结构有哪些？
- 052. 通过示例解释 `if-else` 语句。
- 053. 下列哪些可以编译，哪些会导致错误？
- 054. 如果 `boolA` 为 false 且 `boolB` 为 true，输出将是什么？
- 055. 以下代码的输出是什么？
- 056. 如果可以编译，输出是什么？
- 057. `break` 和 `continue` 语句的作用是什么？
- 058. 执行代码时会发生什么？
- 059. 输出将是什么？
- 060. 给出 `for-each` 循环的示例。
- 061. 以下代码的输出是什么？
- 062. 执行代码时会发生什么？
- 063. 下列的输出是什么？
- 064. 以下代码会发生什么？

## 类与方法

- 065. 考虑以下片段：编译此代码时输出是什么？
- 066. 实例变量可以被声明为 `static` 吗？
- 067. 解释代码编译时会发生什么。
- 068. 如果没有显式指定构造函数，背后会发生什么？
- 069. 解释编译以下代码时会发生什么。
- 070. 构造函数的可能的访问修符有哪些？
- 071. 下列片段的输出将是什么？
- 072. 你将如何定义方法？给出一个示例。
- 073. 通过代码示例解释 `void` 关键字。
- 074. 解释构造函数与普通方法的区别。
- 075. 通过代码示例解释 `this` 关键字。
- 076. 解释类与对象的区别。
- 077. 通过代码示例解释 `new` 关键字。
- 078. 下列代码的输出将是什么？
- 079. 通过代码示例解释 `return` 关键字。

## 内部类

- 080. 什么是内部类？内部类有哪些类型？
- 081. 编写一个代码示例演示如何从外部类实例化内部类。
- 082. 编写一个演示内部类的代码示例。
- 083. 什么是“方法局部”内部类。
- 084. 通过代码示例解释静态嵌套类。
- 085. 通过代码示例解释如何实例化静态嵌套类。

## 继承

- 086. 给出一个非法方法重写的示例。
- 087. 解释 `super` 关键字。
- 088. 下面的代码段有一个错误。识别它并说明原因。
- 089. 编写一个代码示例演示继承如何帮助代码复用。
- 090. 编写一个 Java 代码示例演示方法重写（method overriding）。
- 091. 使用代码示例解释 `extends` 关键字。
- 092. 下面代码片段的输出是什么？
- 093. 解释下面代码片段的输出是什么：
- 094. 下面代码片段的输出是什么？
- 095. 解释下面代码片段存在什么问题：
- 096. 为什么是动态方法分发（dynamic method dispatch）？
- 097. 下面代码有效吗？解释原因。
- 098. 为什么 Java 不支持多继承？
- 099. 使用代码示例解释如何防止方法不被重写。
- 100. 下面的代码有一个错误。识别它并说明如何修复。

## 抽象类与接口

- 101. 声明接口的可能方式有哪些？
- 102. 使用代码示例解释抽象类（abstract class）。
- 103. 使用代码示例解释如何实现接口。
- 104. 下面代码有效吗？解释原因。
- 105. 一个类可以实现两个接口吗？如果两个接口都有同名方法，会发生什么？
- 106. 抽象类的作用是什么？
- 107. 解释下面代码片段存在什么问题：
- 108. 下面代码有效吗？解释原因。
- 109. 下面代码中的哪几行会导致编译错误？
- 110. 下面的代码片段有效吗？

## 包与访问控制

- 111. 什么是包（package）？包有什么优势？
- 112. 解释访问修饰符（access specifiers）。
- 113. 使用代码示例解释如何创建一个包。
- 114. 列出 `JDK` 中的一些默认包，并简要说明它们的作用。
- 115. 下面代码有效吗？解释原因。
- 116. 解释 `import` 关键字。
- 117. 解释 `protected` 和默认（default）访问修饰符之间的区别。
- 118. 下面代码片段有效吗？
- 119. 解释编译并执行以下代码时会发生什么：
- 120. 解释 `java.lang` 包。

## 异常处理

- 121. 解释 Java 中的 `throw`、`throws` 和 `Throwable`。
- 122. 编译并执行以下代码时的输出是什么？
- 123. 编写一个代码示例演示 `try/catch/finally` 块：
- 124. 执行下面代码的输出是什么？
- 125. 解释 Java 中的 `try–catch–finally` 语句。
- 126. 下面代码片段的输出是什么？
- 127. 假设你有一个方法 `myMethod`，其中包含可能抛出受检异常（checked Exception）的代码。你会在代码中如何处理？
- 128. `finally` 子句的作用是什么？举一个例子。
- 129. 解释 `Error` 和 `Exception` 之间的区别。
- 130. 什么是 `RuntimeException`？

## 字符串处理

- 131. 什么是字符串字面量（string literal）？举一个例子。
- 132. 下面代码的输出是什么？解释原因。
- 133. 执行以下代码时的输出是什么？
- 134. 下面代码片段的输出是什么？
- 135. 将字符串字面量赋值给 `String` 变量的各种方式有哪些？
- 136. 列出 `String` 类中的一些常用方法。
- 137. `StringBuffer` 和 `StringBuilder` 之间的区别是什么？
- 138. 编写一个不使用循环的反转 `String` 代码示例。
- 139. 编写一个代码示例演示如何将 `String` 转换为大写。
- 140. 解释如何将 `Integer` 转换为 `String`。

## 泛型

- 141. 编译并运行以下代码会发生什么？
- 142. 下面代码的第 1 行可以编译吗？如果不能，说明原因。
- 143. 解释下面代码存在的问题。
- 144. 解释使下面的代码片段有效还需要哪些额外代码——
- 145. 使用代码示例解释边界泛型类型（Bounded Generic Types）。

## 集合

- 146. Java 集合 API 中的四个主要的接口是什么？
- 147. 你将如何在集合中搜索特定元素？
- 148. 如果你不希望有重复且不在乎顺序，你会选择哪种集合？
- 149. 使用代码示例解释如何移除头部（head）。
- 150. 哪种集合允许动态调整大小并为元素提供索引访问？
- 151. 解释 `Queue` 接口。
- 152. 解释 `Comparator` 接口。
- 153. 解释 Queue 上的一些方法。
- 154. 可以混合泛型集合和非泛型集合吗？如果是，请举例。

## 枚举、自动装箱与包装类

- 155. Java 中提供了哪些包装类（wrapper classes）？
- 156. 下面代码的输出是什么？
- 157. 解释你如何将字符串“100.55”转换为 `Double`，以及将 `Double` 100.55 转换为 `String`。
- 158. 下面代码的输出是什么？
- 159. Java 中的什么是包装类？包装类对象有哪些特殊属性？
- 160. 用例子解释自动装箱（Autoboxing）。

## 线程

- 161. 你如何在 Java 中创建线程（Threads）？
- 162. 解释 Java 中不同的线程类型。
- 163. 可以在不调用 `start()` 方法的情况下直接调用 `run()` 方法吗？
- 164. 执行以下代码时在后台发生了什么？
- 165. 解释 `Thread` 类中的一些主要方法。
- 166. 解释线程状态（thread states）。
- 167. 使用“Thread”类创建线程的代码示例。
- 168. 使用 `Runnable` 接口创建线程的代码示例。
- 169. 在 Java 中可以创建多个线程吗？如果是，线程之间如何通信？
- 170. 什么是同步（Synchronization）？
- 171. 解释执行以下代码时会发生什么。
- 172. 考虑以下代码：
- 173. 执行此代码会首先打印“Thread 1” 1000 次，然后打印“Thread 2” 1000 次。如果这种结果是不正确的，请解释原因。
- 174. 编写一个代码示例，让线程暂停十分钟。
- 175. 当调用 `synchronized` 方法时会发生什么？

## Java IO API

- 176. 执行以下代码时会发生什么？
- 177. 编写一个代码示例，在 `/usr/test.txt` 路径下创建一个文件。
- 178. 用代码示例解释 `FileWriter` 类。
- 179. 编写一个代码片段，使用 `FileReader` 读取文件 `/usr/CoreJava.txt` 的内容并在控制台显示输出。
- 180. 用代码示例解释如何在文件系统上创建目录。
- 181. 解释当以下代码被编译和执行时会发生什么。
- 182. 编写一个代码示例来演示 `PrintWriter` 类。
- 183. 编写一个代码示例来演示如何删除文件。
- 184. 编写一个代码示例来演示如何重命名文件或目录。
- 185. 使用哪些类来序列化和反序列化对象？
- 186. 解释 `File` 类中的一些重要方法。

# Miscellaneous

- 187. 解释当以下代码片段被编译时会发生什么。
- 188. 解释当以下代码被编译和执行时会发生什么。
- 189. 解释对称的 `equals()` 约。
- 190. 以下哪些是无效语句？为什么？
- 191. `transient` 关键字的作用是什么？
- 192. 什么是 Java 垃圾收集（Garbage Collection）？
- 193. 内存的哪部分用于垃圾收集？`JVM` 使用什么算法进行垃圾收集？
- 194. 垃圾收集何时发生？
- 195. 需要编写什么代码来触发垃圾收集？
- 196. 用代码示例解释对象如何成为垃圾收集的候选。

# 第 2 部分– Java 8

## 函数式接口 (Functional Interfaces)

- 197. 什么是函数式接口？你如何创建一个函数式接口？
- 198. 解释 `java.util.Function` 包。
- 199. 用代码示例解释 `java.util.function.Consumer` 接口。
- 200. 解释 `Supplier` 和 `Consumer` 接口之间的区别。
- 201. 以下代码片段的输出是什么？
- 202. 你会使用哪个内置函数式接口来将 `String` 转换为大写？
- 203. 下面代码有效吗？请解释。
- 204. 列举一些 Java 8 之前被 Java 8 转换为函数式接口的接口。
- 205. 为什么 Java 8 增加了内置函数式接口的原始类型特化，如 `IntSupplier`、`BooleanSupplier` 等？
- 206. 内置函数式接口通常用在哪里？

## Lambda 表达式 (Lambda Expressions)

- 207. 什么是 Lambda 表达式？使用 Lambda 表达式有什么用处？
- 208. Lambda 表达式和函数式接口之间有什么关系？
- 209. 解释 Lambda 表达式的语法。
- 210. 给出一些 Lambda 表达式的示例。
- 211. 编写一个代码示例，创建一个函数式接口并使用 Lambda 表达式来实现它。
- 212. 用代码示例解释如何使用 Lambda 表达式以不同的方式实现同一个函数式接口。
- 213. 识别以下 Lambda 表达式中的错误以及如何修复它。
- 214. 以下代码有效吗？请解释。
- 215. 编写一个函数式接口，使得以下 Lambda 表达式可以正常工作。
- 216. 解释如何使用 Lambda 表达式创建一个新的 `Thread`。

## 流处理 (Streams)

- 217. 解释创建 `Stream` 的不同方式。
- 218. 用代码示例解释 `filter` 操作。
- 219. 解释 `Stream` 操作的类型。
- 220. 什么是并行流（parallel stream）？用代码示例解释你如何创建一个并行流。
- 221. 如何将 `Stream` 转换回 `Collection`？
- 222. 以下代码片段的输出是什么？
- 223. `Stream` 和 `Collection` 之间的区别是什么？
- 224. 假设你有一个 `String` 值的 `List`。你想创建一个新的 `List`，消除原始 `List` 中的重复项并将 `String` 值转换为大写。你如何通过 `Stream` 操作实现这一点？
- 225. 可以将数组转换为 `Stream` 吗？请解释。
- 226. 假设你有如下所示的 `Employee` 类，并且假设你有如下所示的 `Employee` 对象列表：你如何使用 `Streams` 创建根据 `Employee` 薪资排序的新 `List`？

## 方法引用 (Method References)

- 227. 什么是方法引用？方法引用的用处是什么？
- 228. 方法引用有哪些不同的类型？
- 229. 给出一个静态方法引用的示例。
- 230. 考虑以下 `Shape` 类：为了让下面的代码有效，该类需要哪些更改？
- 231. 解释 `String::toUpperCase` 是什么种类型的方法引用。

## 日期时间 API (DateTime API)

- 232. 解释以下代码片段中哪里错误以及你如何修复它。
- 233. 用适当的代码示例解释创建 `LocalDate` 的不同方式。
- 234. 用代码示例解释如何检查一个日期是否在另一个日期之前。
- 235. 解释 `ZonedDateTime` 类。
- 236. 以下代码片段的输出将是什么？
- 237. 如何使用 Java 8 `DateTime API` 获取日期对应的星期几？
- 238. 解释 `Period` 和 `Duration` 类之间的区别。
- 239. 假设你有一个格式为 `yyyy/mm/dd` 的 `String` 日期。你如何获取该日期对应的 `LocalDate` 对象？
- 240. 以下代码片段的输出是什么？
- 241. 解释如何使用新的 `DateTime API` 判断某年是否为闰年。

## Optional

- 242. 什么是 `Optional`？为什么 Java 8 引入了它？
- 243. 如何创建 `Optional`？
- 244. 请用代码示例解释 `Optional.ifPresent` 方法。
- 245. `orElse` 和 `orElseThrow` 方法之间有什么区别？
- 246. 下面代码段的输出是什么？

## 集合改进 (Collection Improvements)

- 247. 请用代码示例解释 `forEach` 方法是如何工作的。
- 248. Java 8 对 `List` 接口做了哪些改进？
- 249. `Map.getOrDefault` 方法是如何工作的？
- 250. 下面代码段的输出是什么？
- 251. 解释 `Iterator` 和 `SplitIterator` 之间的区别。

## 其他 (Miscellaneous)

- 252. `CompletableFuture` 类相比 `Future` 接口有哪些优势？
- 253. 什么是 `StringJoiner`？请用代码示例解释。
- 254. 解释 `Comparator.reverse` 和 `Comparator.reverseOrder` 方法之间的区别。
- 255. Identify 下方代码中的错误，并说明需要如何修复。
- 256. 解释 `CompletableFuture.runAsync` 和面 `CompletableFuture.supplyAsync` 方法之间的区别。

# 第 3 部分 – Java 9

## 模块 (Modules)

- 257. 什么是模块？它们提供了什么好处？
- 258. 什么是模块描述符（module descriptor）？
- 259. 包（package）和模块（module）之间的区别是什么？
- 260. 解释 Java 9 对 JDK 所做的更改。
- 261. 考虑以下代码段：为了让这段代码作为模块的一部分部署，需要完成什么？
- 262. 解释 `requires static` 模块指令。什么情况下应该它？

## 流/集合改进 (Stream/Collection Improvements)

- 263. Java 9 对 `Stream` 接口做了哪些改进？
- 264. 下面代码有效吗？如果没有，可以如何修复？
- 265. 识别下方代码段中的问题，并说明如何修复。
- 266. 你可以使用哪个 Java 9 方法创建一个包含 `String` 值的 `Set`？
- 267. 下面代码段的输出是什么？

## 其他 (Miscellaneous)

- 268. Java 9 对接口做了哪些更改？为什么？
- 269. 什么是 `JShell`？
- 270. 下面代码段的输出是什么？
- 271. Java 9 对 `try–with` 语句做了哪些更改？
- 272. Java 9 在 `Optional` 类中添加的 `stream` 方法用途是什么？
- 273. 解释 `ProcessHandle` 类及其一些重要方法。
- 274. 在下方代码段中，说明第 1 行应该使用什么代码来打印下方“预期输出”部分中的内容：
- 275. Java 9 引入的新型 `HttpClient` 有哪些优势？

# 场景题 (Scenario Based Questions)

- 276. 假设你通过扩展 `Thread` 类创建了一个新线程并多次调用 `start` 方法。你认为会发生什么？
- 277. 假设你有一个返回整数值的方法。代码位于 `try/catch/finally` 块中。`try`、`catch` 和 `finally` 块中都有 `return` 语句。`try` 块中的 `return` 返回 `1`，`catch` 块返回 `-1`，`finally` 块返回 `0`。如果发生异常，将返回哪个值？
- 278. 假设 `Base` 类中有一个 `static` 方法。假设在 `sub–class` 中有一个同名方法。假设你创建了一个 `Base` 类对象并将其赋值为 `sub–class` 对象的引用，然后调用该 `static` 方法。这有效吗？如果是，调用的是哪个版本的 `static` 方法？
- 279. 假设基类中有一个方法抛出 `ArrayIndexOutOfBoundsException`。假设该方法在 `sub–class` 中被重写并声明抛出 `RuntimeException`。你认为会发生什么？
- 280. 假设你有一个对象 `List`。你想将其作为参数发送给客户端应用程序，但想确保客户端不要对其进行修改。你如何实现这一点？
- 281. 假设你正在从数据库读取 10000 个 `String` 值。你需要创建一个包含这些值的拼接后的 `String`。实现这一目标最高效的方法是什么？
- 282. 假设你正在开发一个涉及大量极大数值计算的应用。考虑到精度很重要，你会使用什么数据类型作为变量？
- 283. 假设你正在开发一个多线程应用程序。现在有一个新需求，你需要存储键值对。在这种情况下最合适的 `Collection` 是哪一个？
- 284. 假设需要在应用程序中创建一些工具方法。创建此类方法的最佳实践是什么？你应该把它们放在哪里？
- 285. 假设你作为 API 的一部分开发了一个 `FileWriter` 接口。它有一个 `writeToCsv` 方法，可将传入的内容写入 CSV 文件。该 API 由不同的应用程序实现，这些程序为 `FileWriter` 接口提供了实现。现在，假设需要在接口中添加一个名为 `writeToExcel` 的新方法，将传入的内容写入 Excel 文件。你如何进行这一更改以对对 API 用户产生最小的影响？

# 第 4 部分 – 人力资源 (Human Resource)

## 创意 (Creativity)

- 286. 你在哪里寻找灵感？
- 287. 你如何在工作中发挥创意？
- 288. 你如何促使他人创造创意？
- 289. 描述你的创造力。

## 领导力 (Leadership)

- 290. 在工作中你倾向于获得权力还是更多的责任？
- 291. 当小组中有人没有尽到职责时你会怎么办？
- 292. 请 true 你做过超出权限范围的决策。
- 293. 你乐意向主管汇报纠纷吗？
- 294. 如果你在上一份工作中担任负责人，你会做哪些不同的改变？
- 295. 你认为雇主是否应对表现优秀的员工进行表扬或奖励？
- 296. 你认为领导者具备最重要的特质是什么？
- 297. 请讲述一次出现意外问题。你是如何处理的？
- 298. 能否举一个例子，说明你在之前的工作中改进了某个目标？
- 299. 请讲述一次主管对项目没有提供足够具体的指导的情况。
- 300. 请讲述你领导一个项目的经历。
- 301. 请讲述你向前雇主提出的一个建议，该建议后来被实施了。
- 302. 请讲述一次你想到工作中的某事可以更高效完成的方法的情况。
- 303. 领导他人与管理他人之间是否有区别？哪一个是你更大的强项？
- 304. 你在领导角色中表现得更好，还是作为团队中的成员表现得更好？
- 305. 请讲述一次你在工作中发现某些影响你（或他人）工作效率的经历——你是如何处理的？
- 306. 在有明确目标和任务的工作中，你的表现如何？
- 307. 在你拥有巨大决策权的工作中，你的表现如何？
- 308. 如果你看到其他员工有不诚实或不符合道德的行为，你会怎么办？
- 309. 请讲述一次你通过自学获得了知识，并在后来帮助了你职业生涯的经历。
- 310. 请讲述一次你在工作中构思项目想法的经历。
- 311. 请讲述一次你在项目中承担风险的经历。
- 312. 对于 对于那些想要进入这个领域的人，你会建议他们什么？

## 截止日期与时间管理

- 313. 请讲述一次你没有赶上截止日的经历。
- 314. 你在工作时如何消除干扰？
- 315. 请讲述一次你在有每周或每月配额任务的职位上工作的经历。你成功的频率有多高？
- 316. 请讲述一次你完成艰巨截止日的经历，以及你是如何完成它的。
- 317. 当你手上有多个项目时，你如何保持有条理？
- 318. 你工作日期间有多少时间处于“自动驾驶”状态？
- 319. 你如何处理截止日期？
- 320. 请介绍你个人的解决问题的流程。
- 321. 工作中哪些事情会让你感到压力？
- 322. 你如何对工作中的压力做出反应？当你感到压力时，如何让自己冷静下来？
- 323. 你擅长多任务处理吗？请举一些你成功处理多项任务的例子。
- 324. 你每周工作多少小时？
- 325. 你每天检查几次邮件？

## 客户服务

- 326. 什么是客户服务？
- 327. 请讲述一次你为客户额外付出的经历。
- 328. 你如何获得客户的信任？
- 329. 请讲述一次客户感到不悦或焦虑的经历——你是如何处理该情况的？
- 330. 什么时候你可以为客户破例？
- 331. 当客户和老板都需要你时，你会怎么办？
- 332. 客户服务最重要的方面是什么？
- 333. 为客户建立低预期还是高预期更好？

## 沟通

- 334. 描述一次你向同事传达困难或复杂想法的经历。
- 335. 在哪些情况下你觉得难以沟通？
- 336. 良好沟通的关键要素是什么？
- 337. 请讲述一次你通过沟通解决问题的经历。
- 338. 请讲述一次你与另一员工发生冲突的经历。你是如何解决该情况的？
- 339. 你是倾向与他人建立关系，还是花更多时间去了解他们？
- 340. 描述一次你必须通过人际关系来解决问题的经历。
- 341. 请讲述一次你说服他人承担艰巨任务的经历。
- 342. 请讲述一次你说服一个群体接受你提案的经历。
- 343. 请讲述一次你与他人发生问题的经历，事后看来，你希望当时能以不同的方式处理。
- 344. 请讲述一次你协调员工之间冲突的经历。

## 求职与日程

- 345. 你在职位中寻找的三个最重要的东西是什么？
- 346. 你是如何评估你想要加入的公司的？
- 347. 你接受月薪制吗？
- 348. 你为什么选择上一份工作？
- 349. 离开上一份工作已经多久了？原因是什么？
- 350. 你还在寻找其他类型的工作？
- 351. 你在工作中受过纪分吗？
- 352. 你的时间安排是怎样的？
- 353. 我可以联系你的现主吗？
- 354. 你是否有任何可以为我们的业务带来价值的人脉联系？
- 355. 你多快可以开始工作？
- 356. 你的前任雇主说你离开的原因是什么？
- 357. 你积极寻找工作多久了？
- 358. 在什么情况下你会不上班？
- 359. 你是否被主管告诉过今天提前下班？如果是，为什么？
- 360. 你的考勤记录如何？
- 361. 你在哪里听到这个职位的？
- 362. 在做聘用决策时，还有什么你想让我知道的吗？

# 以下标题可能也很有用

1. 你可能会遇到的 `NET` 面试题
2. 你可能会遇到的 `Access VBA` 编程面试题
3. 你可能会遇到的 `Administrator & Helpdesk` 面试题
4. 你可能会遇到的 `Adobe ColdFusion` 面试题
5. 你可能会遇到的 `Advanced C++` 面试题
6. 你可能会遇到的 `Advanced Excel` 面试题
7. 你可能会遇到的 `Advanced JAVA` 面试题
8. 你可能会遇到的 `Advanced SAS` 面试题
9. 你可能会遇到的 `AJAX` 面试题
10. 你可能会遇到的 `Algorithms` 面试题
11. 你可能会遇到的 `Android Development` 面试题
12. 你可能会遇到的 `Ant & Maven` 面试题
13. 你可能会遇到的 `Apache Web Server` 面试题
14. 你可能会遇到的 `Artificial Intelligence` 面试题
15. 你可能会遇到的 `ASP.NET` 面试题
16. 你可能会遇到的 `Automated Software Testing` 面试题
17. 你可能会遇到的 `Base SAS` 面试题
18. 你可能会遇到的 `BEA WebLogic Server` 面试题
19. 你可能会遇到的 `C & C++` 面试题
20. 你可能会遇到的 `C#` 面试题
21. 你可能会遇到的 `CCNA` 面试题
22. 你可能会遇到的 `Cloud Computing` 面试题
23. 你可能会遇到的 `Computer Architecture` 面试题
24. 你可能会遇到的 `Computer Networks` 面试题
25. 你可能会遇到的 `Core JAVA` 面试题
26. 你可能会遇到的 `Data Structures & Algorithms` 面试题
27. 你可能会遇到的 `EJB 3.0` 面试题
28. 你可能会遇到的 `Entity Framework` 面试题
29. 你可能被要求的 `Fedora & RHEL` 面试题
30. 你可能被要求的 `Hadoop` 大数据面试试题
31. 你可能被要求的 `Hibernate`, `Spring` & `Struts` 面试题
32. 你可能被要求的 `HR` 面试题
33. 你可能被要求的 `HTML`, `XHTML` 和 `CSS` 面试题
34. 你可能被要求的 `HTML5` 面试题
35. 你可能被要求的 `IBM WebSphere` 应用服务器面试试题
36. 你可能被要求的创新型面试题
37. 你可能被要求的 `iOS SDK` 面试题
38. 你可能被要求的 `Java / J2EE` 设计模式面试试题
39. 你可能被要求的 `Java / J2EE` 面试题
40. 你可能被要求的 `JavaScript` 面试题
41. 你可能被要求的 `JavaServer Faces` 面试题
42. 你可能被要求的 `JDBC` 面试题
43. 你可能被要求的 `jQuery` 面试题
44. 你可能被要求的 `JSP-Servlet` 面试题
45. 你可能被要求的 `JUnit` 面试题
46. 你可能被要求的领导力面试题
47. 你可能被要求的 `Linux` 面试题
48. 你可能被要求的 `Linux` 系统管理员面试试题
49. 你可能被要求的 `Mac OS X Lion` 面试题
50. 你可能被要求的 `Mac OS X Snow Leopard` 面试题
51. 你可能被要求的 `Microsoft Access` 面试题
52. 你可能被要求的 `Microsoft Powerpoint` 面试题
53. 你可能被要求的 `Microsoft Word` 面试题
54. 你可能被要求的 `MySQL` 面试题
55. 你可能被要求的网络网络面试题
56. 你可能被要求的 `OOPS` 面试题
57. 你可能被要求的操作系统面试试题
58. 你可能被要求的 `Oracle` 数据库管理面试试题
59. 你可能被要求的 `Oracle E-Business Suite` 面试题
60. 你可能被要求的 `ORACLE PL/SQL` 面试题
61. 你可能被要求的 `Perl` 编程面试试题
62. 你可能被要求的 `PHP` 面试题
63. 你可能被要求的 `Python` 面试题
64. 你可能被要求的 `RESTful Java Web` 服务面试试题
65. 你可能被要求的 `SAP HANA` 面试题
66. 你可能被要求的 `SAS` 编程指南面试试题
67. 你可能被要求的 `Selenium` 测试工具面试试题
68. 你可能被要求的 `Silverlight` 面试题
69. 你可能被要求的软件仓库面试试题
70. 你可能被要求的软件测试面试题
71. 你可能被要求的 `SQL Server` 面试题
72. 你可能被要求的 `Tomcat` 面试题
73. 你可能被要求的 `UML` 面试题
74. 你可能被要求的 `Unix` 面试题
75. 你可能被要求的 `UNIX Shell` 编程面试试题
76. 你可能被要求的 `Windows Server 2008 R2` 面试题
77. 你可能被要求的 `XLXP`, `XSLT`, `XPATH`, `XFORMS` & `XQuery` 面试题
78. 你可能被要求的 `XML` 面试题

访问完整列表请
[www.vibrantpublishers.com](http://www.vibrantpublishers.com)

# 注意事项

![img](img/Bcover.jpg)

