

# Java 入门指南：Prem Kumar Java 编程

## 作者简介

当印度 IT 行业发生重大演变时，Destiny 引导 Prem Kumar 接触了计算机。他在 Silli 理工学院完成了计算机科学工程教育，随后在布巴内斯瓦尔甘迪科技学院继续深造。Prem 对探索 IT 知识充满热情，是快速发展的初创公司“F5 Developers”的创始人。他是各种技术领域备受青的演讲者，也是 Open Source 和 OSE Hub 的定期专栏作家。目前的身份包括 F5 Developers 的创始人（这是一家多服务提供公司，包括 F5 的子公司即 THOR、F5 Initiative 和 OSE Hub）。为了感谢他的贡献，微软在 2019 年授予他 Java 编程领域享誉的“微软技术协士”奖。可以通过以下方式与他联系。

## 铭言

“简单并不在复杂之前，而是紧随之后。” —— Prem Kumar

## 致谢

从《深入浅 Java - 入门指南》这本书想法的构思到第一版的发布，这是一段几乎是全新的开始的旅程。在这段旅途中，我遇到了许多学生、开发者、教授、出版商和作者，他们对 Java 表达了自己的看法。他们是我完成这本书的主要动力。特别是，我非常感谢 Priya 女士，她对这个书的想法充满信心，相信我的写作能力，不断给予鼓励，并时提供有用的建议。我感谢上帝让我拥有这样的父母，没有他们，我无法获得一点知识。在此，我想感谢我的父亲 Rajan Mahto 博士和我的母亲 Manju Devi 女士，让我能够做到。在这个过程中，R.K. Raja、Mohit Kumar 和 Priya 等人な编写程序、发现 Bug、绘制图表和准备索引方面提供了帮助。我相信凭借他们的集体智慧，所有程序在任何情况下都能正确运行。我要感谢我的初创公司 F5 Developers 的所有成员。我希望他们的梦想已经实现。感谢我的朋友 Priya，感谢她的友谊以及她对我所做的每件事的贡献。

## 引言

本教材有两个主要目标。第一个是介绍 Java 语言。Java 是一种实用且目前流行的软件工具；它是世界上最流行的语言之一，特别是在嵌入式系统等领域。Java 有助于编写非常高效且强大的代码，鉴于 Java 编译器的无处不在，它可以轻松移植到许多平台。第二个关键目标是介绍 OOP 的基本概念。在某种程度上，这是 Java 特有的：学习设计、编码和调试 Java 程序。

## Java – 概述

### 什么是 Java？

Java 既是一种编程语言也是一个平台。Java 是一种高级、健壮、面向对象且安全的编程语言。Java 由孙景系统公司（现为 Oracle 的子公司）于 1995 年开发。James Gosling 被称为 Java 之父。在 Java 之前，它的名字是 Oak。由于 Oak 已经是一家注册的公司，James Gosling 和他的团队将名字更改为 Java。

### 平台

运行程序的任何硬件或软件环境被称为平台。由于 Java 拥有运行环境（`JRE`）和 API，因此被称为平台。

### 示例

让我们快速看一下 Java 编程示例。

```java
class Example{
    public static void main(String args[]){
        System.out.println("Hello Java");
    }
}
```

### Java 的应用

根据孙景系统的数据，有 30 亿台设备运行 Java。目前有很多设备在使用 Java。其中一些如下：

1. 桌面应用程序，如 Acrobat Reader、媒体播放器等。
2. Web 应用程序，如 irctc.co.in、javatpoint.com 等。
3. 企业级应用，如银行应用程序。
4. 移动端
5. 嵌入式系统
6. 智能卡
7. 机器人
8. 游戏等。

### Java 应用的类型

使用 Java 创建的应用主要有 4 类：

1. **独立应用程序**：也称为桌面应用程序或基于窗口的应用程序。这些需要在每台机器上安装的传统软件。`AWT` 和 `Swing` 用于创建独立应用程序。
2. **Web**：运行在服务器端并创建动态页面的应用程序。目前 Java 用于创建 Web。
3. **企业级应用**：具有分布式性质的应用程序，如银行应用程序。它具有高级安全性、负载均衡等优势。`EJB` 用于创建企业级应用。
4. **移动应用**：为移动设备创建的应用程序。目前 Android 和 Java ME 用于移动应用。

### Java 平台 / 版本

1. **Java SE (标准版)**：一个 Java 编程平台。它包含了如 `java.lang`、`java.io`、`java.net`、`java.util`、`java.sql`、`java.math` 等 Java API，以及 OOP、异常、内部类、多线程、I/O 流、网络、反射、集合。
2. **Java EE (企业版)**：一个主要用于开发 Web 和企业级应用的平台。构建在 Java SE 平台之上，包含了 Servlet、JSP、Web Services 等。
3. **Java ME (微版)**：一个主要用于开发移动应用的微平台。
4. **JavaFX**：用于开发富应用程序。它使用轻量级用户界面。

### Java 历史

Java 的历史非常有趣。Java 最初是为交互式电视设计的，但当时的数字电缆行业技术太先进。Java 的历史始于 Green Team。Green Team 的成员发起了这个项目，为机顶盒、电视等数字设备开发语言。后来，Java 技术被 Netscape 采用。James Gosling、Mike Sheridan 和 Patrick Naughton 在 90 年代初启动了这个项目。Arthur Gosling 经常被称为“Java 博士”。以下点描述了 Java 的历史：

1. 1991 年 6 月发起了 Java 语言。
2. 最初是为机顶盒等嵌入式系统设计的。
3. 之后它被称为 Oak，并作为 Green 项目的一部分被开发。

### 为什么叫 Oak？

Oak 是美国、德国、罗马尼亚等国家的国树。1995 年，Oak 被更名为 Java，因为 Oak 已经是 Oak Technologies 的商标。

### 为什么命名为 Java？

团队聚集在一起选择新名字。建议的词有“动态”、“革命性”、“Silk”、“jolt”、“DNA”等。他们想要一个反映技术本质的名字：革命性的、动态的、活力、独特且易读。

### Java 版本历史

到目前已发布了许多 Java 版本。Java 目前的稳定版本是 Java SE 10。

1. `JDK Alpha` 和 `Beta` (1995)
2. `JDK 1.0` (1996 年 1 月 23 日)
3. `JDK 1.1` (1997 年 2 月 19 日)
4. `J2SE 1.2` (1998 年 12 月 8 日)
5. `J2SE 1.3` (2000 年 5 月 8 日)
6. `J2SE 1.4` (2002 年 2 月 6 日)
7. `J2SE 5.0` (2004 年 9 月 30 日)
8. `Java SE 6` (2006 年 12 月 11 日)
9. `Java SE 7` (2011 年 7 月 28 日)
10. `Java SE 8` (2014 年 3 月 18 日)
11. `Java SE 9` (2017 年 9 月 21 日)
12. `Java SE 10` (2018 年 3 月 20 日)

## Java 的特性

创建 Java 编程语言的主要目标是使其成为可移植、简单且安全的编程语言。除此之外，还有一些在该语言流行中起重要作用的优秀特性。Java 的特性也被称为 `java`。

以下是 Java 语言最重要的特性列表：

1. 简单
2. 面向对象
3. 可移植
4. 平台无关
5. 安全
6. 健壮
7. 架构中立
8. 解释型
9. 高性能
10. 多线程
11. 分布式
12. 动态
13. 简单

### 简单

Java 非常容易学习，其语法简单、清晰且易于理解。根据官方，Java 语言是一种简单的编程语言，因为：

- Java 语法基于 `C++`（因此程序员在学习 `C++` 后更容易学习它）。
- Java 删除了许多且不常用的特性，例如显式指针、运算符重载等。
- 不需要删除未引用的对象，因为 Java 中有自动垃圾回收机制。

### 面向对象

Java 是一种面向对象的编程语言。Java 中的一切都是对象。面向对象意味着我们通过不同对象的组合来组织软件。

- **面向对象编程 (OOP)** 是一种通过提供一些概念来简化软件开发和维护的方法。
- **OOP 的基本概念**：
  - 对象
  - 类
  - 继承
  - 多态
  - 抽象
  - 封装

### 对象

任何具有状态和行为的实体被称为对象。例如：椅子、笔、键盘等。它可以被定义为类的实例。对象占据某些空间。对象可以在不了解其他数据的情况下进行通信。对象接收消息。例如：狗，它有颜色、品种等状态，以及摇尾巴、汪叫等行为。

### 类

对象的集合被称为类。它是一个逻辑实体。它是创建对象的模板或蓝图。类不消耗任何空间。

### 继承

当一个对象获取父类的属性和行为时，被称为继承。它提供了代码重用性，用于运行时。当你从现有类继承时，可以用方法和字段。

### 多态

如果以不同的方式执行任务，被称为多态。例如：形状、三角形等。在 Java 中，我们使用方法重载和方法重写来实现多态。另一个例子是说话：猫喵喵、狗汪。

### 抽象

隐藏内部细节并显示功能被称为抽象。例如：电话、调用。在 Java 中，我们使用 `abstract class` 和 `interface` 来实现抽象。

### 封装

将代码和数据绑定到单个单元被称为封装。例如：胶囊，它带有不同的药物。Java 类是完全封装的，因为所有数据成员都是私有的。

### 类与对象

在本章中，我们将学习 Java 对象和类。在面向对象编程中，使用对象和类设计程序。Java 中的对象是物理实体，而类是逻辑实体。

### Java 中的对象是什么？

具有状态和行为的实体被称为对象。例如：椅子、自行车、笔、表。它可以是物理的或逻辑的（有无形的）。对象有三个特征：

- **状态**：代表对象的数据（值）。
- **行为**：代表对象（的功能）。
- **身份**：对象通常通过唯一 ID 实现。该 ID 对外部用户不可见，由 JVM 用于识别每个对象。

### 什么是类？

类是具有共同属性对象的集合。它是一个创建对象的模板或蓝图。它不是物理的。类可以包含：

- 字段
- 方法
- 构造函数
- 块
- 嵌套类和接口

### 类的声明语法

```java
class {
    field;
    method;
}
```

### 对象定义

对象是真实实体。对象是运行时实体。

### Java 中的实例变量

在类内部方法外部创建的变量被称为实例变量。实例变量在编译时不获得内存。它们在运行时获得内存。

### Java 中的方法

在 Java 中，方法类似于函数，用于暴露对象的行为。

## 初始化对象的方法

Java 有 3 种初始化对象的方法：

1. 通过引用变量
2. 通过方法
3. 通过构造函数

### 对象类示例：通过引用初始化

初始化对象意味着将数据存储到对象中。让我们来看一个简单的示例，通过引用变量初始化对象。

（为了简单起见省略了代码）

### Java 默认构造函数

当构造函数没有参数时，被称为“默认构造函数”。

### 默认构造函数的语法

```java
{}
```

### 默认构造函数示例

在本示例中，我们在 `Bike` 类中创建无构造函数。

```java
class Bike1{
    Bike1(){
        System.out.println("Bike is created")
    }
}
```

## Java 参数构造函数

具有特定数量参数的构造函数被称为参数构造函数。

### 为什么要使用参数构造函数？

参数构造函数用于为不同的对象提供不同的值。然而，你也可以提供相同的值。

### 参数构造函数示例

在本示例中，我们创建了具有两个参数的 `Student` 类构造函数。我们可以在构造函数中有任意数量的参数。

```java
class Student4{
    int id;
    String name;
    Student4( int i, String n){
        id = i;
        name = n;
    }
}
```

## Java 中的构造函数重载

在 Java 中，构造函数类似于方法但不返回值。它可以像方法一样被重载。Java 中的构造函数重载是拥有多个具有不同参数列表的构造函数的技术。编译器通过参数的数量和类型来区分它们。

### 构造函数重载示例

```java
class Student5{
    int id;
    String name;
    int age;
    Student5( int i, String n){
        id = i;
    }
    Student5( int i, String n, int a){
        id = i;
        name = n;
        age = a;
    }
}
```

### 拷贝构造函数

Java 中没有拷贝构造函数。然而，我们可以像 C++ 那样通过值从一个对象拷贝到另一个。Java 中有许多方法可以拷贝：

- 通过构造函数
- 通过 `Object` 类的 `clone()` 方法

### 无构造函数的拷贝

我们可以通过赋值对象将一个对象的值拷贝到另一个对象。

```java
s2.id = s1.id;
// ...
```

## 变量、数据类型、运算符

### Java 变量

变量是执行 Java 程序执行时存储值的容器。变量被分配了数据类型。Java 有三类型的变量：局部、实例和静态。

### 变量

变量是分配在内存中的位置。在这种情况下，是“可变的”，意味着它的值可以改变。

```java
int data=50; //这里 data 是变量
```

### 运算符

运算符是用于执行操作的符号。例如：`+`、`-`、`*`、`/` 等。Java 有许多类型的运算符：

- 一元运算符
- 算术运算符
- 移位运算符
- 关系运算符
- 位运算符
- 逻辑运算符
- 三元运算符
- 赋值运算符

### 运算符优先级

（参考图像）

### 一元运算符

Java 一元运算符需要一个操作数。一元运算符用于执行各种操作，例如：

- 增加减少值
- 反转布尔值

### 算术运算符

Java 算术运算符用于执行加、减、乘、除法。它们作为基本的数学操作操作。

### 左移位运算符

Java 左移位运算符 `<<` 用于将值的所有位向左移动指定的次数。

### 右移位运算符

Java 右移位运算符 `>>` 用于按操作数指定的位数将操作数右移。

### 无符号移位运算符

对于负数，`>>>` 将最高位 (MSB) 变为 0。

### 逻辑运算符

逻辑运算符 `&&` 在第一个条件为真时不检查第二个条件。它只在第一个条件为假时才检查第二个。

### 位运算符

位运算符 `|` 总是检查两个条件是否真或假。

### 三元运算符

Java 三元运算符被用作 `if-then-else` 语句的单行替代，在 Java 编程中使用大量。它接受三个操作数。

### 赋值运算符

Java 赋值运算符是将右侧的值分配给左侧的操作。

## 多线程

### 多线程概述

Java 多线程是同时执行多个线程的过程。线程是轻量级的子进程，处理的最小单元。多处理和多线程都用于实现多任务。然而，我们使用多线程而不是多处理，因为线程使用共享内存区域。它们不分配内存区域，因此节省了内存，线程之间的上下文切换比进程快。

### 多任务

多任务是同时执行多个任务的过程。我们使用多任务来利用 CPU。多任务可以通过两种方式实现：

1. **基于进程的多任务（多处理）**：每个进程在内存中有地址。分配独立的内存区域。进程是重量级的。进程之间的通信成本很高。
2. **基于线程的多任务（多线程）**：线程共享地址空间。线程是轻量级的。线程之间的通信成本较低。注意：一次执行一个线程。

### 线程

Java 提供了 `Thread` 类来实现多线程编程。`Thread` 类提供了构造函数和方法来创建线程并对线程执行操作。`Thread` 继承 `Object`。

### 线程的周期和状态

Java 中的线程在任何时候都处于以下状态之一。线程在任何时刻只处于显示状态之一：

1. 新生 (New)
2. 可运行 (Runnable)
3. 阻塞 (Blocked)
4. 等待 (Waiting)
5. 定时等待 (Timed Waiting)
6. 终止 (Terminated)

### 在 Java 中实现状态

在 Java 中，使用 `getState()` 方法获取线程的当前状态。Java 提供了 `java.lang.Thread.State` 类，为线程的状态定义枚举常量。

- `NEW`：尚未启动的线程状态。
- `RUNNABLE`：可运行线程的状态。
- `BLOCKED`：等待监视器锁的线程状态。
- `WAITING`：等待线程的状态。
- `TIMED_WAITING`：带有指定等待等待的等待线程的状态。
- `TERMINATED`：已终止线程的状态。

## 线程优先级

在多线程环境中，线程调度器根据线程的优先级为线程分配处理器。当我们在 Java 中创建一个线程时，它总是被分配某些优先级。优先级可以由 JVM 在创建线程时给出，也可以由程序员显式给出。线程优先级的接受值范围是 1 到 10。`Thread` 类中定义了三个静态变量用于优先级：

- `MIN_PRIORITY`：线程可以拥有的最小优先级。值为 1。
- `NORM_PRIORITY`：线程的默认优先级，如果没有显式定义它。值为 5。
- `MAX_PRIORITY`：线程的最大优先级。值为 10。

### 获取和设置线程优先级




- `public final int getPriority()`：返回线程的优先级。
- `public final void setPriority(int newPriority)`：更改线程的优先级。如果参数 `newPriority` 超出了（1 到 10）的范围，该方法抛出 `IllegalArgumentException`。

## Java 杂杂

### Java Applets

Applet 是一种嵌入网页的特殊程序类型。

### Applet 的生命周期

Applet 类提供了 4 个周期方法：

- `init()`：初始化。仅调用一次。
- `start()`：在浏览器最大化时调用。
- `stop()`：在浏览器最小化时调用。停止 applet。
- `destroy()`：销毁 applet。在浏览器关闭时调用一次。

### 在 Applet 中显示图形

`java.awt.Graphics` 类提供了许多图形编程方法。常用的方法有：

- `public abstract void drawString(String str, int x, int y)`：绘制指定的字符串。
- `public void drawRect(int x, int y, int width, int height)`：绘制指定宽宽的矩形。
- `public abstract void fillRect(int x, int y, int width, int height)`：用默认颜色填充矩形。
- `public abstract void drawOval(int x, int y, int width, int height)`：绘制指定宽高的的椭圆。
- `public abstract void fillOval(int x, int y, int width, int height)`：用默认颜色填充椭圆。
- `public abstract void drawArc(int x, int y, int width, int height, int startAngle, int arcAngle)`：绘制圆弧或椭弧。
- `public abstract void fillArc(int x, int y, int width, int height, int startAngle, int arcAngle)`：用默认颜色填充圆弧或椭弧。
- `public abstract void drawLine(int x1, int y1, int x2, int y2)`：在两个点 `(x1, y1)` 和 `(x2, y2)` 之间画线。
- `public abstract void drawPoly(int x1, int y1, int x2, int y2, int width)`：绘制指定宽度的线。
- `public abstract boolean drawImage(Image img, int x, int y, Observer observer)`：绘制指定的图像。

### 在 Applet 中显示图像

Applet 主要用于游戏和动画。`java.awt.Graphics` 类提供 `drawImage()` 来显示图像。

语法：`public abstract boolean drawImage(Image img, int x, int y, Observer observer)` 用于绘制指定的图像。

### 如何获取 Image 对象

`java.applet.Applet` 类提供了 `getImage()` 方法返回 `Image` 对象。

语法：`public Image getImage(URL u, String image)`。

Applet 的其他需要方法：

- `getDocumentBase()`：返回文档。
- `getCodeBase()`：返回基础 URL。

### Applet 中的事件处理

由于我们在 `AWT` 或 `Swing` 中执行事件处理，我们也可以在 applet 中执行它。

```java
import java.applet.*;
import java.awt.*;
import java.awt.event.*;
public class EventApplet extends Applet implements ActionListener{
    Button b;
    TextField tf;
    public void init() {
        tf = new TextField();
        tf.setBounds(30, 40, 150, 20);
        b = new Button("Click");
        b.setBounds(80, 150, 60, 50);
        add(b);add(tf);
        b.addActionListener(this);
        setLayout(null);
    }
    public void actionPerformed(ActionEvent e) {
        tf.setText("Welcome");
    }
}
```

## 异常处理

Java 中的异常处理是处理运行时错误的强大机制之一，以便维持应用程序的正常流。

### Java 中的异常是什么？

字典：异常是一种异常状态。在 Java 中，异常是中断程序正常流的事件。它是运行时抛出的一个对象。

### 什么是异常处理？

异常处理是处理运行时错误（如 `ClassNotFoundException`、`IOException`、`RemoteException` 等）的机制。

### 异常处理的优势

异常处理的核心优势是维持应用程序的正常流。异常通常会中断程序的流。这就是我们使用异常处理的原因。

### Java 异常的常见场景

1. `ArithmeticException`：如果你将任何数字除以零，就会发生 `ArithmeticException`。
2. `NullPointerException`：如果你在任何变量中有 `null` 值，对该变量执行任何操作都会抛出 `NullPointerException`。
3. `NumberFormatException`：可能会发生任何值的格式错误。假设我有一个包含字符的字符串变量，将此变量转换为数字将发生 `NumberFormatException`。
4. `ArrayIndexOutOfBoundsException`：如果你在错误的索引处插入值，会导致 `ArrayIndexOutOfBoundsException`。

### Java try-catch 块

`try` 块用于封装可能抛异常的代码。它必须在方法内部。如果 `try` 块中的某个语句发生异常，后续代码将不会执行。因此建议将代码放在 `try` 块中。`try` 块必须跟在 `catch` 或 `finally` 块之后。当发生异常时，`catch` 块会被触发。

### Java try-catch 语法

```java
try {
    // 可能抛异常的代码
} catch (Exception_class_Name ref){}
```

### Java try-finally 语法

`try` 块后面跟着 `finally` 块。

```java
try {
    // 可能抛异常的代码
} finally {}
```

### Java catch 块

Java `catch` 块用于处理异常，通过声明异常的类型。声明的异常必须是父类（例如 `Exception`）或生成的异常类型。`catch` 块必须跟在 `try` 块之后。

### 没有异常处理的问题

如果不使用 `try-catch` 块，理解该问题。示例 1：

```java
public class TryCatch1 {
    public static void main(String[] args) {
        int a[]= new int [ 5 ];
        a[ 5 ]= 30 / 0; //抛出异常
        System.out.println("rest of the code");
    }
}
```

输出：`Exception in "main" java.lang.ArithmeticException:/ zero`。如上示例所示，代码的其余部分没有执行。

### 通过异常处理解决

通过 `try-catch` 块来解决上述问题。示例 2：

```java
public class TryCatch2 {
    public static void main(String[] args) {
        try {
            int a[]= new int [ 5 ];
            System.out.println(a[ 10 ]);
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
        System.out.println("rest of the code");
    }
}
```

输出：`java.lang.ArithmeticException: zero`。如上示例所示，代码的其余部分被打印。

示例 3：

```java
public class TryCatch3 {
    public static void main(String[] args) {
        try {
            int data= 50 / 0; //抛出异常
            System.out.println("rest of the code");
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

输出：`java.lang.ArithmeticException:/ zero`。这里我们可以看到，如果 `try` 块中发生了异常，代码的其余部分不会执行。

示例 4：

```java
public class TryCatch4 {
    public static void main(String[] args) {
        try {
            int data= 50 / 0; //抛出异常
        } catch (Exception e) {
            System.out.println(e);
        }
        System.out.println("rest of the code");
    }
}
```

输出：`java.lang.ArithmeticException:/ zero`

`rest of the code`。

### Java try-catch 块的内部工作

`JVM` 首先检查异常是否被处理。如果异常未被处理，`JVM` 提供默认异常处理器执行以下操作：

- 打印异常描述。
- 打印堆栈跟踪（发生异常的方法）。
- 导致程序终止。

如果异常被应用程序处理，正常流得以维持。

### Java 多异常异常

`try` 块可以跟随一个或多个 `catch` 块。每个 `catch` 块必须包含不同的异常处理器。

要记忆的点：

- 一时间只发生一个异常，一时间只执行一个 `catch` 块。
- 所有 `catch` 块必须从具体的到通用的排序，例如 `ArithmeticException` 的 `catch` 必须在 `Exception` 的 `catch` 之前。

示例 1：

```java
public class MultipleCatchBlock1 {
    public static void main(String[] args) {
        try {
            int a[]= new int [ 5 ];
            a[ 5 ]= 30 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception occurs");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayIndexOutOfBounds Exception occurs");
        } catch (Exception e) {
            System.out.println("Parent Exception occurs");
        }
        System.out.println("rest of the code");
    }
}
```

输出：`Arithmetic Exception occurs`，`rest of the code`。

示例 2：

```java
public class MultipleCatchBlock2 {
    public static void main(String[] args) {
        try {
            int a[]= new int [ 5 ];
            System.out.println(a[ 10 ]);
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception occurs");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayIndexOutOfBounds Exception occurs");
        } catch (Exception e) {
            System.out.println("Parent Exception occurs");
        }
        System.out.println("rest of the code");
    }
}
```

输出：`java.lang.ArrayIndexOutOfBoundsException: Index 10 out of bounds for length 5`。

示例 3：

```java
public class MultipleCatchBlock3 {
    public static void main(String[] args) {
        try {
            int data= 50 / 0; //抛出异常
            System.out.println("rest of the code");
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

输出：`java.lang.ArithmeticException: / zero`。

这里我们可以看到，如果 `try` 块中发生了异常，代码的其余部分不会执行。

### 嵌套 try 块

在 `try` 块中的 `try` 块被称为嵌套 `try`。

#### 为什么要使用嵌套 try？

有时会出现一种情况，部分块导致一个错误，整个块本身导致另一个错误。在这种情况下，异常处理器必须是嵌套的。

#### 语法

```java
try {
    statement 1;
    statement 2;
    try {
        statement 1;
        statement 2;
    } catch (Exception e) {}
} catch (Exception e) {}
```

### 嵌套 try 示例

```java
class Excep6{
    public static void main(String[] args[]){
        try {
            System.out.println("going to divide");
            int b = 39 / 0;
        } catch (ArithmeticException e){
            System.out.println(e);
            }
            try {
                int a[]= new int [ 5 ];
                a[ 5 ]= 4 ;
            } catch (ArrayIndexOutOfBoundsException e){
                System.out.println(e);}
            }
        } catch (Exception e){
            System.out.println("handeled" );
        }
        System.out.println("normal flow.." );
    }
}
```

## Java finally 块

`finally` 块是一个用于执行重要代码（如关闭连接、流等）的块。无论异常是否被处理，`finally` 块都会执行。`finally` 块位于 `try` 或 `catch` 块之后。

注意：如果在终止程序之前没有处理异常，`JVM` 会执行 `finally` 块（如果有的话）。



## 为什么要使用 `finally`

Java 中的 `finally` 块可以用于放置“清理”代码，如关闭文件、关闭连接等。

## Java `finally` 的用法

### 情况 1：没有发生异常

```java
class TestFinallyBlock{
    public static void main(String[] args[]){
        try {
            int data= 25 / 5 ;
            System.out.println(data);
        } catch (NullPointerException e){System.out.println(e);}
        finally {System.out.println( "finally block is always executed" );}
        System.out.println( "rest of the code..." );
    }
}
```

输出：`5`，`finally block is always executed rest of the code...`

### 情况 2：发生了异常且未被处理

```java
class TestFinallyBlock1{
    public static void main(String[] args[]){
        try {
            int data= 25 / 0 ;
            System.out.println(data);
        } catch (NullPointerException e){System.out.println(e);}
        finally {System.out.println( "finally block is always executed" );}
        System.out.println( "rest of the code..." );
    }
}
```

输出：`finally block is always executed rest of the code...`

### 情况 3：发生了异常并被处理

```java
class TestFinallyBlock{
    public static void main(String[] args[]){
        try {
            int data= 25 / 0 ;
            System.out.println(data);
        } catch (ArithmeticException e){System.out.println(e);}
        finally {System.out.println( "finally block is always executed" );}
    }
}
```

输出：`java.lang.ArithmeticException: / zero`。

### 示例 5

```java
class MultipleCatchBlock5 {
    public static void main(String[] args) {
        try {
            int a[]= new int [ 5 ];
            a[ 5 ]= 30 / 0;
        } catch (Exception e){
            System.out.println("common task");
        } catch (ArithmeticException e){
            System.out.println("task1 is completed");
        } catch (ArrayIndexOutOfBoundsException e){
            System.out.println("task 2 completed");
        }
    }
}
```

输出：`Compile-time error`
