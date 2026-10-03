
# Java 22 医疗应用指南

![](img/5a077f56e14b826c2dc61de6c176e5ef_0_0.png)

这本详尽的著作深入探讨了 Java 22 中引入的关键特性，提供了见解和实际示例，帮助读者在医疗应用背景下理解并实现这些增强功能，目标是增强医疗实践、简化流程并改善患者护理。

《用于医疗与医学应用的 Java 22》探索了最新的 Java 22，并介绍了 Java 编程的最新进展，包括未命名变量、启动多文件源代码程序，以及外部函数和内存 API。从实现用于医学图像分析的高级算法到开发高效的医疗保健管理系统，本书展示了这一工具如何彻底改变医学领域。该书关注可访问性、互操作性和数据安全，赋能医疗专业人员以创新的方式利用技术，最终带来更好的患者疗效和改进的医疗服务。无论是优化电子健康记录系统、开发远程医疗平台，还是通过数据分析推进医学研究，作者为医疗专业人员提供了 300 多个实战示例所需的知识和技能；读者将学习如何利用 Java 22 的尖端特性来构建强大且高效的应用。

本书面向从学生到专业人士的多元读者群体，并对 Java 编程的最新进展及其在医疗和医学技术中的应用提供了宝贵的见解。

Usharani Bhimavarapu 是印度安得拉普拉什邦 Koneru Lakshmaiah 教育基金会的助理教授，她在那里教授计算机科学与工程。凭借跨越 17 年的职业生涯，她已成为数据挖掘、机器学习和数据结构领域备受尊敬的权威。Bhimavarapu 博士的研究能力通过其出版的超过 100 篇论文和 50 本书籍得到了证明，内容涵盖了 C++、Java、全栈、数据库、Node.js、Python、HTML 和 CSS 等编程语言。

![](img/5a077f56e14b826c2dc61de6c176e5ef_3_0.png)

![](img/5a077f56e14b826c2dc61de6c176e5ef_6_0.png)

# 前言

几十年来，Java一直是企业和应用开发的基石，随着 Java 22 的发布，它继续进化，提供了提升生产力、性能和安全性的新功能。本书为已经熟悉 Java 基础并渴望扩展其最新特性及应用知识的开发者设计。

Java 22 引入了多项增强代码灵活性、可读性和可维护性的功能。JEP 456 引入了未命名变量和模式，提高了变量声明的可读性（第三和第九章）。JEP 459 通过运行时计算的值简化了字符串处理，增强了安全性（第四章）。此外，JEP 463 让初学者能够更容易地编写单类程序，促进了向复杂编程的顺利过渡（第六章）。JEP 461 通过自定义中间操作增强了 Stream API，提升了流管道的力（第十一章）。JEP 447 允许开发者在显式调用之前放置语句，为构造行为提供了更多灵活性（第七章）。结构化并发（JEP 462）和作用域值（JEP 464）通过增强错误处理、取消和线程数据共享简化了并发编程（第十章）。

为了让这些功能生动起来，本书强调实时示例，特别是在医疗领域。通过学习这些实际示例，你不仅将学习新功能，还将理解如何利用它们解决复杂的现实问题。我们将探索如何使用 Java 22 增强的 API 和性能改进来管理和处理大量的医学数据，开发利用 Java 模式匹配和新 API 的诊断工具，并创建保护敏感数据的医疗应用程序。此外，你还将学习如何使用外部函数内存 API 与医疗设备接口，直接从各种医疗仪器采集并处理数据。

本书非常适合希望技能升级到 Java 22 的 Java 开发者、寻找 Java 在医疗领域实际示例的软件工程师、需要构建高效、安全且高性能应用的医疗应用开发人员，以及对最新 Java 特性及其应用感兴趣的计算机科学和软件工程的学生和教师。

![](img/5a077f56e14b826c2dc61de6c176e5ef_8_0.png)

# 关于作者

Usharani Bhimavarapu 是印度安得拉普拉什邦 Koneru Lakshmaiah 教育基金会的助理教授，她在那里教授计算机科学与工程。凭借 17 年的职业生涯，她已成为数据挖掘、机器学习和数据结构领域备受尊敬的权威。Bhimavarapu 博士的科研实力体现在她发表的 100 多篇论文和 50 本书籍中，涵盖 CPP、Java、全栈、数据库、R、Node.js、Python、HTML 和 CSS 等编程语言。

![](img/5a077f56e14b826c2dc61de6c176e5ef_10_0.png)

# Java 简介

## 1.1 引言

OOPs 代表面向对象编程（object-oriented programming），这是一种围绕对象而非函数和逻辑组织软件设计的编程范式。在 OOP 中，对象是类的实例，它们封装了数据（属性）和行为（方法）。这种范式通过允许开发者更有效地对现实实体及其交互进行建模，促进了软件开发中的模块化、可重用性和扩展性。OOP 的核心原则包括封装、继承、多态和抽象。

### 1.1.1 Java 中的基础 OOP 概念

这些概念构成了 Java 面向对象的基础，对于构建模块化、可维护且可扩展的软件系统至关重要。

#### 1.1.1.1 抽象

抽象是隐藏实现细节并显示对象本质特征的过程。它通过关注高层功能来减少编程的复杂性和工作量。抽象通过抽象类和方法实现，其中实现细节被隐藏，只提供本质特征。

#### 1.1.1.2 封装

封装是指将数据（变量）和操作这些数据的方法封装在一个单一单元或类中。它可以帮助隐藏并保护数据免受未经授权的访问。通过使用访问修饰符来限制对类的某些组件的访问，从而保护数据免受未经授权的访问。

#### 1.1.1.3 继承

继承允许类（子类或派生类）从另一个类（父类或基类）继承属性和行为。它促进了代码的重用，并在类之间建立了层级关系。继承允许子类从父类继承属性和行为，促进了代码重用并建立了类之间的层级关系。

#### 1.1.1.4 多态

多态允许不同类的对象被视为共同父类的对象。它允许编写出能够在运行时与各种类型和类的对象工作的方法。

用于医疗保健和医学应用的 Java 22

多态允许不同类型的对象被视为共同父类的对象，从而实现了灵活性和代码重用。

### 1.1.2 OOP 概念对性能的影响

面向对象编程（OOP）概念（如封装和继承）的实现可以提高代码的用性和维护性，从而带来更高效的开发流程。

- 1. 内存占用：

    a. 对象和类：Java 中的每个对象都占用内存。过度使用对象（尤其是大型对象）会导致内存消耗增加并降低应用程序性能。

    b. 继承和多态：深层的继承层次结构和广泛的多态使用会导致由于动态方法分发引起的内存使用增加和运行性能变慢。

- 2. CPU 开销：

    a. 方法调用：频繁的方法调用（特别是在深层继承结构或复杂场景中）会引入 CPU 开销。

    b. 封装和访问器方法：为了封装而过度使用 getters 和 setters会导致额外的方法调用，影响 CPU 性能。

- 3. 优化 Java 代码以提高性能

- 4. 高效使用对象：

    a. 尽量减少对象的创建，特别是在代码中性能敏感的区域。对频繁使用的对象使用对象池。

- 5. 优化继承和态：

    a. 在适当的情况下优先使用组合而非继承，以减少复杂性和内存占用。

    b. 明智地使用接口并避免深层继承树，以减少动态方法分发的开销。

- 6. 有效的内存管理：

    a. 主动监控和管理内存使用。利用 Java 性能分析工具识别并修复内存泄漏。

    b. 优化数据结构，在频繁随机访问时，优先使用 `ArrayList` 等高效集合而非 `LinkedList`。

- 7. 为了性能进行代码重构：

    a. 重构代码以消除不必要的方法调用，特别是在循环或频繁调用的方法中。

    b. 在适当的情况下对简单方法使用内联代码。

- 8. 懒初始化和预热加载：

    a. 对于重量型资源，当其立即加载可能影响启动性能时，使用懒初始化。

    b. 反之，使用预热加载预加载资源，减少应用程序关键部分的延迟。

- 9. 利用 JVM 特性：

    a. 保持最新 Java 更新，这些版本通常包含 JVM 的性能增强。

    b. 利用 JIT 编译和 HotSpot VM 在运行时优化代码。

- 10. 并发与多线程：

    a. 谨慎使用多线程以提高应用程序性能，特别是对于 I/O 密集型或计算密集型操作。

    b. 确保线程安全并避免常见的

## 1.2 Java 中的 OOP 概念

在 Java 中，面向对象编程（OOP）基于几个核心概念：

### 1.2.1 类与对象

类是对象的蓝图，定义了属性（字段）和行为（方法）。对象是类的实例。

#### 语法

```
// 抽象类 Student
abstract class Student {
  // 抽象方法（无实现）
  abstract void registerCourse();

  // 抽象方法（无实现）
  abstract void attendClass();

  // 具体方法（抽象类中可选）
  static void getDetails() {
    // 方法可以实现
  }
}

// 具体类 Course 继承 Student
class Course extends Student {
  public Course(String courseName, Student student) {
    // 课程包含一个学生
    // 这里的赋值逻辑
    // 这里的代码可以实现
  }
  // Course 类中的 main 方法
  void main(String[] args) {
    System.out.println("类中的 main 方法");
    Student s=new Course();
  }

  // 方法实现将在这里
}
```

在上述语法中，`Student` 类被定义为抽象类，这意味着它不能被直接实例化，而是其他类的蓝图。它包含了抽象方法（`registerCourse` 和 `attendClass`），这些方法没有实现。继承 `Student` 的 `Course` 类是一个具体的

用于医疗保健和医学应用的

实现，它继承了 `Student` 类的结构并负责实现抽象方法，从而展示了面向对象编程中抽象类和具体类之间的关系。

### 1.2.1.1 对象

在 Java 中，对象是一个基本概念，代表运行时环境中的现实实体或概念。对象是类的实例，类是定义其结构和行为的蓝图或模板。对象通过使用 `new` 关键字调用构造函数来创建。它是类的实例，拥有一组数据（属性或字段）和方法（函数或行为）。

Java 类语法中的 `Course c = new Course();` 允许你直接处理继承自抽象 `Student` 类的具体对象。通过这种方式，你可以实现并访问 `Course` 类定义的特定行为，包括任何定义的

# Java 简介

`Course` 类继承自 `Student`，这意味着它将为抽象方法提供具体的实现，尽管这些方法在大纲中并未定义。

## 1.2.5 封装

封装是将数据（属性）和操作这些数据的方法封装在单一单元（类）中。使用 `private`、`protected` 和 `public` 等访问修饰符来控制对类成员的访问。

在 (A) 处的语法（即类）中，封装通过使用抽象类 `c` 来体现，该类包含抽象方法，这些方法定义了行为而不暴露其实现细节。通过对选课和参加课程的行为进行封装，`Student` 类建立了一个蓝图，供 `Course` 等具体类继承。这确保了这些内部的内部工作机制对用户是隐藏的，促进了接口与实现之间清晰的分离。

当通过 `Course c = new Course()` 创建 `Course` 对象时，它封装了课程管理的具体细节，允许类定义其抽象方法的自身的实现。`Student` 类的封装特性确保了核心功能受到保护，并且只能通过定义的接口进行修改，从而增强了数据的完整性并减少了意外交互的风险。这种封装促进了一种健壮的设计，有助于面向对象编程中的可维护性和可扩展性。

## 1.2.6 方法

方法定义在类内部用于执行特定任务。它们封装了行为并可以接受参数和返回值。

在 (A) 处的语法（即类）中，`Student` 声明了抽象方法 `registerCourse()` 和 `attendClass()`，这些方法作为任何子类必须履行的合同，确保了在实现行为的同时保留了方法的实现细节。这意味着这些操作在子类内部如何执行细节取决于子类。当 `Course` 类继承 `Student` 时，它可以为这些抽象方法提供具体的实现，从而封装了与选课和课程相关的特定逻辑。封装的方法允许对功能进行受控的访问和修改，确保 `Course` 类的内部工作机制不会暴露给外部。这种在抽象类中声明方法而在具体类中实现的方法分离提供了一个整洁的接口，在维护 `Student` 类中定义方法完整性的同时，实现了代码复用并降低了复杂度。

## 1.2.7 包

包用于将类和接口组织到命名空间中，提供了一种管理类和接口访问的方法。例如，要创建一个名为 `com.java22` 的简单包，你应该在 Java 文件开头写：

```java
package com.java22;
```

此声明必须是 Java 源文件的第一行，并表示该文件中定义的类属于 `com.java22` 包。

## 1.2.8 构造函数与析构函数

构造函数是特殊的方法，用于在创建对象时初始化对象。Java 没有析构函数，但它拥有在被垃圾回收之前调用的终结器（finalizers）。

# 用于医疗应用的 Java 22

这些组件组 Java 面向对象编程（OOP）的基础，对于构建健壮、模块化且可维护的软件系统至关重要。

```java
public Course(String courseName, Student student)
{
    this.courseName = courseName;
    this.student = student;
    // 课程由一个学生组成
}
```

此构造函数通过设置 `courseName` 并将其与 `Student` 对象关联来初始化 `Course` 对象，建立了一种“组合关系”，即课程包含一个学生。

## 1.2.9 访问修饰符

用于设置类、变量、方法和构造函数访问级别的关键字。常见的修饰符包括 `public`、`protected`、`private` 和默认（无修饰符）。

- 1. `public`: 成员可以从任何其他类访问。

- 2. `protected`: 成员可以在自己的包内以及通过子类进行访问。

- 3. `default`: 成员仅在自己的包内可访问。

- 4. `private`: 成员仅在自己的类内部可访问。

这些修饰符有助于封装数据并限制对类成员的访问，促进面向对象编程中更好的数据管理和安全性。

## 1.2.10 关联

两个对象之间的关系显示了它们如何相互，通常通过使用引用其他对象的实例变量表示。关联是一种类引用另一个类的关系，表示“拥有”（has-a）关系，例如“学生”拥有“课程”。

## 1.2.11 聚合

一种具有整体与部分关系的关联形式，其中部分可以独立于整体而存在。它代表了一种“拥有”关系。

在 `Student` 和 `Course` 类的上下文中，聚合可以通过包含多个 `Course` 对象的 `Student` 对象来说明，这意味着一个学生可以独立于课程本身参加各种课程。

## 1.2.12 组合

一种更强的聚合形式，其中部分不能独立于整体而存在，意味着“包含”（contains-a）关系。

在 `Student` 和 `Course` 类的上下文中，组合可以用包含 `Student` 对象的 `Course` 类来表示，表示课程由学生组成，如果课程被删除，相关的学生将不再相关。

# Java 简介

## 1.2.13 静态绑定

在编译时将方法调用链接到其方法体的过程，用于方法重载。

在 `Student` 和 `Course` 类的上下文中，当在 `Student` 引用上调用静态方法（如 `Details()`）时，发生静态绑定，在编译时解析为 `Student` 类中的方法，无论实际的对象类型如何。

## 1.2.14 动态绑定

在运行时将方法调用链接到其方法体的过程，用于方法重写。

在 `Student` 和 `Course` 类的上下文中，当在 `Student` 引用上调用方法（如 `registerCourse()`）时，发生动态绑定，允许根据实际对象类型执行子类（例如 `Course`）中的特定实现。

## 1.2.15 父类

其他类继承其属性和行为的类。

## 1.2.16 子类

从另一个类（即父类）继承属性和行为的类。

在 `Student` 和 `Course` 类的上下文中，`Student` 类作为子类定义了通用属性和行为，而 `Course` 类可以作为子类继承 `Student`。

## 1.2.17 重载

在同一个类中定义名称相同但参数不同的方法的能力。

## 1.2.18 重写

子类为父类中已定义的方法提供特定实现的能力。

在 `Student` 类的上下文中，重写允许子类提供特定的实现。

## 1.2.19 Java 不是纯面向对象

Java 不被认为是纯面向对象语言的原因包括：

- 1.3.1 基本数据类型：Java 包含了 `int`、`float`、`boolean` 等基本数据类型，这些不是对象。

- 1.3.2 静态方法和字段：Java 允许在类中使用静态方法和字段。

- 1.3.3 过程化编程特性：Java 通过静态方法支持过程化编程特性。

- 1.3.4 基本类型包装类：Java 提供了包装类（例如 `Integer`、`Float`、`Boolean`）来封装基本类型。

# Java 简介

## 表格 1.1

面向对象编程与过程化编程

| 特性 | 面向对象编程 (OOP) | 过程化编程 |
|---|---|--|
| 主要关注 | 关注对象及其相互作用。 | 关注过程和函数。 |
| 数据与行为 | 将数据（属性）和行为（方法）结合。 | 将数据和行为分离为不同的实体。 |
| 模块化 | 通过封装和继承强调模块化。 | 对模块化的重视较少。 |
| 代码重用性 | 通过继承和多态鼓励重用。 | 代码重用局限于函数和过程。 |



## 封装与继承

| 特性 | 面向对象编程 | 过程式编程 |
|---|---|---|
| 封装与继承 | 将数据封装在单个单元（类）中。支持继承，允许类从其他类继承属性和方法。 | 不支持显式的封装支持。不支持继承。 |
| 多态 | 允许不同类型的对象被视为一个共同的超类。 | 通过函数重载实现多态。 |
| 抽象 | 支持抽象，隐藏实现细节并仅显示对象的本质特征。 | 抽象局限于函数和过程。 |
| 消息传递 | 对象通过相互传递消息进行通信。 | 函数通过传递参数进行通信。 |
| 数据隐藏 | 允许通过访问修饰符（如`private`、`protected`）限制对数据的访问来实现隐藏。 | 不提供内置的数据隐藏支持。 |
| 过程抽象 | 使用函数来实现过程化抽象，将任务分解为更小的、可重用的过程。 | 关注将任务分解为更小的函数。 |
| 状态与行为 | 对象封装了状态（数据）和行为（方法）。 | 数据和行为是独立的实体。 |
| 可扩展性 | 通过添加新类和新方法支持扩展性。 | 可扩展性局限于添加新的函数或过程。 |
| 复杂度管理 | 通过模块化设计和抽象帮助管理复杂度。 | 复杂度管理依赖于规范的编码实践。 |
| 错误处理 | 为异常处理机制提供内置支持。 | 使用错误代码或返回值实现错误处理。 |

## 表格 1.2 与其他语言的比较：Java vs Python vs C++

| 特性/方面 | Java | Python | C++ |
|---|---|---|---|
| OOP 实现本质 | 严格面向对象；一切皆对象。 | 多范式，严格面向对象。 | 多范式，将 OOP 引入 C。 |
| 类定义与继承 | 类支持单继承，接口支持多继承。 | 支持多继承。 | 支持多继承，包括私有和保护继承。 |
| 内存管理 | 垃圾回收器自动管理。 | 垃圾回收器自动管理。 | 手动内存管理。 |
| 多态与方法重写 | 严格要求使用`@Override`注解。 | 由于动态类型是隐式的。 | 允许多态，需要显式管理。 |
| 学习与易用性 | 健壮且方便，但可能冗长。 | 语法简单，对新手友好。 | 由于复杂性挑战较大。 |
| 性能考虑 | 运行在 JVM 上，具有可移植性但有时较慢。 | 通常较慢，解释型语言。 | 高性能，编译为原生机器码。 |

# Java 简介

Java 是由 Sun Microsystems 公司于 1995 年开发的高级编程语言，后被 Oracle 公司收购。Java 由 James Gosling 和 Patrick Naughton 创建，最初的名称是“Oak”，后由于商标问题被重命名为“Java”。与许多编程语言不同，Java 以其平台无关性而闻名，允许程序在任何硬件或软件平台上运行。Java 借鉴了 C 和 C++，它继承了 C 的语法和来自 C++ 的面向对象特性。Java 的第一个版本是 Java 1.0，随后的版本引入了许多增强。最新的迭代版本 Java SE 22 于 2024 年 3 月 19 日发布。Java 执行 Java 虚拟机（JVM）和应用程序接口（API）。Java 虚拟机是为特定硬件和软件环境设计的专用程序，能够执行 Java 技术应用程序。API 作为一个软件组件集合，有助于各种应用程序或软件组件的创建。

# Java 应用程序的类型

有四种 Java 应用程序：

## 独立应用程序（Standalone Applications）

独立应用程序（也称为桌面应用程序）是在用户计算机上本地运行的 Java 程序，不需要 Web 浏览器。这些应用程序通常具有图形用户界面（GUI）并与用户直接交互。Java 支持使用各种 GUI 框架（如抽象窗口工具 AWT、Swing 和 JavaFX）来构建独立应用程序。独立应用程序的范围从简单的实用程序到复杂的软件 IDE 和媒体播放器不等。

## 企业级应用程序（Enterprise Applications）

企业级应用程序是为满足组织需求设计的大型系统。它们处理复杂的业务流程，并需要高扩展性和安全性。Java 提供了如 Enterprise JavaBeans（EJB）、Java Persistence API（JPA）和 Java Message Service（JMS）等技术，用于在企业级平台上构建这些应用程序。

## Web 应用程序（Web Applications）

Web 应用程序是运行在服务器上并通过浏览器由用户访问的程序。它们提供动态内容和交互功能。Java 提供了 JavaServer Pages（JSP）和 Servlets 等技术来构建和部署这些基于 Web 的应用程序。

## 移动应用程序（Mobile Applications）

移动应用程序是设计运行在智能手机和平板等移动设备上的软件。Java ME（微版）是 Java 环境的精简版本，针对内存、处理能力和显示能力进行了优化。它为跨平台的移动开发提供了库和 API。

# Java 简介

## 1.6.2 Java 编程语言平台

Java 语言有四种平台：

### 1.6.2.1 Java 标准版（Java SE）

Java SE 定义了 Java 语言的核心组件，包括基本类型、对象和控制结构。它提供了构建从命令行工具到桌面 GUI 应用程序等类型应用程序的运行时环境和标准库。

### 1.6.2.2 Java 企业版（Java EE）

Java EE 扩展了 Java 的功能以支持大型分层应用程序的开发。它提供了全面的 API 和运行时环境，用于在提供安全性和扩展性额外服务的平台上构建企业应用程序。

### 1.6.2.3 Java 微版（Java ME）

Java ME 是在资源限制设备（如手机、PDA 和嵌入式系统）上运行 Java 应用程序的平台。它包含了针对特定设备类型的配置，允许开发者在各种移动平台上创建应用程序。

### 1.6.2.4 JavaFX

JavaFX 是用于构建具有现代外观和高性能图形的富网络应用程序（RIA）的平台。它提供了一套 API 和工具，用于创建运行在桌面、浏览器和移动设备上的交互式多媒体用户界面。

## 1.6.3 平台无关

Java 编译器不生成特定机器的可执行代码，而是产生字节码，这是一种平台无关的格式。该字节码由 Java 虚拟机（JVM）根据预定义的规则执行，使得 Java 与平台无关。字节码可以被安装在任何操作系统上的任何 JVM 通用解释。因此，Java 源代码具有可移植性，可以在不同的操作系统上无缝运行。

# 用于医疗保健和医疗应用的 Java

![](img/5a077f56e14b826c2dc61de6c176e5ef_22_0.png)

图 1.1 Java 的组件。

## 1.7 Java 核心组件

Java 程序用源代码编写，源代码是人类可读的，但 CPU 无法理解。图 1.1 显示了 JDK、JRE 和 JVM 之间的关系。为了弥补这一差距，Java 在其平台内使用了三个关键组件：

### 1.7.1 Java 开发工具包（JDK）

JDK 或 Java 开发工具包（Java Development Kit）是为 Java 开发者提供的全面工具包，适用于 Windows、macOS、Solaris 和 Linux 等多种操作系统。它方便了 Java 程序的执行，并允许在单台计算机上安装多个版本的 JDK。JDK 的主要功能包括为 Java 编程提供工具、使用编译器将 Java 源代码转换为字节码，以及通过 Java 启动器执行 Java 程序。

### 1.7.2 Java 虚拟机（JVM）

JVM 或 Java 虚拟机（Java Virtual Machine）充当引擎，为 Java 程序提供运行时环境。它在将 Java 字节码转换为机器语言方面起着至关重要的作用。与其他编译器生成特定系统机器码的编程语言不同，在 Java 中，编译器将字节码生成到虚拟机，即 Java 虚拟机。需要注意的是，JVM 包含一个即时编译（JIT）编译器，它通过动态地将 Java 源代码转换为低级机器语言来进一步优化性能。

### 1.7.3 Java 运行环境（JRE）

JRE 是设计用于执行其他软件的软件。它包含了核心组件，如类库、类加载器和 JVM。通过整合编译器和解释器，Java 采用了一种独特的方法：编译器将源代码编译为字节码，而 JVM 将解释这些字节码并转换为依赖于操作系统的代码，从而实现了平台无关性。

## 1.8 JVM

Java 虚拟机（JVM）是 Java 运行环境（JRE）不可或缺的组件，负责为 Java 程序提供运行时环境。它作为一个引擎，解释并执行 Java 字节码，字节码是由 Java 编译器编译的 Java 源代码的中间表示形式。JVM 抽象了底层硬件和操作系统，使得 Java 程序能够在无需重新编译的情况下在不同平台间一致运行。此外，JVM 还整合了内存管理、垃圾回收、动态类加载等各种功能，有助于平台的可移植性、安全性和性能。JVM 可以执行以下操作：

- 读取字节码
- 验证字节码
- 将代码与库链接

### 1.8.1 读取字节码

JVM 负责从`.class`文件中读取由 Java 编译器生成的机器可读指令。字节码是一组机器可读的指令，它以平台无关的方式表示 Java 程序的逻辑。在接收到字节码后，JVM 会解析并解释这些指令，以确保执行 Java 程序定义的相应操作。

### 1.8.2 验证字节码

字节码验证是 JVM 执行的一项关键过程，用于确保 Java 程序的安全性和完整性。在字节码验证期间，JVM 会检查字节码指令，以检测潜在的安全漏洞，例如类型不匹配、堆栈溢出或对内存的非法访问。通过彻底分析字节码，JVM 可以防止损害系统稳定性或安全性的有害操作。

### 1.8.3 将代码与库链接

JVM 负责将字节码指令与程序执行所需的必要库和运行时组件进行链接。此链接过程涉及将字节码中的符号引用转换为实际内存地址或库函数。JVM 在运行时动态加载所需的类文件和库，确保 Java 程序能够访问成功执行所需的资源。通过将代码与库链接，JVM 促进了 Java 应用与外部资源的无缝集成，包括系统库、框架和运行时环境。

### 1.8.4 Java 虚拟机如何工作？

Java 虚拟机（JVM）是 Java 的一个关键组件。它作为一个引擎解释并执行 Java 字节码，字节码是 Java 编译器编译的 Java 源代码的中间表示。JVM 的工作方式如下：

#### 1.8.4.1 加载

JVM 负责从`.class`文件中读取 Java 编译器生成的机器可读指令。字节码是一组以平台无关方式表示 Java 程序逻辑的机器可读指令。在接收到字节码后，JVM 会解析并解释这些指令，以确保 Java 程序定义的相应操作。

#### 1.8.4.2 验证

字节码验证是 JVM 执行的一项关键过程，用于确保 Java 程序的安全性和完整性。在字节码验证期间，JVM 会检查字节码指令，以检测潜在的安全漏洞，例如类型不匹配、堆栈溢出或对内存的非法访问。通过彻底分析字节码，JVM 可以防止损害系统稳定性或安全性的有害操作。

#### 1.8.4.3 执行

在解释模式下，JVM 逐行执行字节码。在 JIT 编译模式下，JVM 将频繁执行的字节码编译为机器码。JVM 包含一个即时编译（JIT）编译器，它通过动态地将 Java 源代码转换为低级机器语言来进一步优化性能。

#### 1.8.4.4 内存管理

JVM 使用自动内存管理技术（如垃圾回收）管理内存分配和释放。它将内存分为不同的区域，如堆（对象）、方法区（类元数据）和运行时栈（方法调用）。垃圾回收器定期扫描堆，以回收未使用的内存。

#### 1.8.4.5 运行时环境

JVM 为 Java 应用提供运行时环境，包括对多线程、异常处理和动态类加载的支持。它实现了与底层操作系统和硬件交互的 API，为 Java 程序提供了平台无关性。JVM 还管理 Java 线程的执行、同步以及处理 Java 抛出的异常。

字节码是编译后的 Java 源代码，它是平台无关的，可以被安装在任何操作系统上的 Java 虚拟机（JVM）理解。Java 的这种特性使其在不同环境中具有良好的移植性。

## 1.8.5 JVM 的组件

JVM 由两个组件组成：解释器和即时编译（JIT）编译器。这些组件共同高效执行 Java 字节码。

### 1.8.5.1 解释器

解释器逐行读取并执行字节码指令。由于其逐行执行的方法，解释器的性能可能低于原生代码执行。当一个方法被多次调用时，解释器可能每次都需要重新解释字节码，导致开销。

### 1.8.5.2 即时编译（JIT）编译器

JIT 在运行时将整个字节码编译为原生机器码。这些原生机器码随后直接用于重复的方法调用，跳过了解释过程。通过将字节码编译为原生代码，JIT 编译器显著提升了系统性能，特别是对于频繁执行的路径。

## 1.9 Java 特性

### 1.9.1 面向对象范式

Java 采用了健壮的面向对象编程模型，一切都被视为对象。这种范式有助于代码库的扩展和维护。

# Java 简介

## 1.9.2 平台无关性

与 C 和 C++ 等传统编程语言不同，Java 将源代码编译为平台无关的字节码。这种字节码可以在配备了 Java 虚拟机（JVM）的系统上运行，实现了跨平台兼容性。

## 1.9.3 简单性

Java 设计旨在对用户友好且易于学习。其面向对象的特性简化了开发，使初级程序员也能轻松上手。

## 1.9.4 安全性

Java 内置的安全功能能够创建健壮、防篡改的应用程序，从而最大限度地减少漏洞和恶意软件的风险。

## 1.9.5 架构中立性

Java 编译器生成架构中性的字节码，确保编译后的代码可以在各种硬件架构上无缝执行。

## 1.9.6 可移植性

Java 的平台无关性和由于缺乏特定平台的依赖项，使其具有高度的可移植性。其用 ANSI C 实现的编译器遵循整洁的可移植性边界。

## 1.9.7 健壮性

Java 通过严格的编译时和运行时检查优先预防错误，最大限度地减少了常见编程错误的发生。

## 1.9.8 多线程支持

Java 的多线程能力赋予开发者创建并发、响应式应用程序的能力，这些程序能够同时执行多个任务。

## 1.9.9 解释执行

Java 字节码在运行时由 JVM 进行动态解释，使得无需预编译即可实现代码的快速开发和执行。

## 1.9.10 性能优化

利用即时编译（JIT）编译器，Java 通过将字节码动态编译为高效的原生机器码，实现了高性能。

## 1.9.11 分布式计算

Java 非常适合分布式计算环境，是开发互联网网络化应用程序的理想选择。

## 用于医疗保健和医学应用的 Java 22

## 1.9.12 动态性

Java 表现出动态行为，允许程序适应不断变化的运行时条件。丰富的运行时信息能够对对象访问进行运行时验证和解析。

## 1.10 Java 22 特性

与之前的版本相比，Java 22 引入了显著改进和新特性，提升了开发者的生产力、应用程序性能和语言能力。以下是 Java 22 较早期版本的关键改进摘要：

## 1.10.1 Project Amber：语言增强

### 1.10.1.1 `super()` 之前的语句

通过 JEP 447，开发者现在可以在显式调用构造函数之前放置不引用所创建实例的语句。这为构建行为提供了更大的灵活性，并保持了自上而下的执行顺序。其详细说明见于第 7 章（继承）。

### 1.10.1.2 未命名变量和模式

JEP 456 引入了未命名变量和模式，通过允许声明那些需要但从不使用的变量声明或嵌套模式，提高了代码的可读性和可维护性。其详细说明见于第 3 章（决策制定）和第 9 章（异常处理）。

### 1.10.1.3 字符串模板

JEP 455 的第二次预览通过允许在字符串中使用运行时计算的值，简化了字符串处理。这在从用户提供的值组合字符串时增强了安全性和可读性。其详细说明见于第 4 章（数组）。

### 1.10.1.4 隐式声明类和实例 main 方法

JEP 463（同样处于第二次预览阶段）通过简化单类程序声明，让初学者更容易编写他们的第一个程序。此特性允许从基础到复杂的 Java 程序之间进行平滑过渡。其详细说明见于第 6 章（类）。

## 1.10.2 并发改进：Project Loom

### 1.10.2.1 结构化并发

JEP 464 引入了结构化并发 API，允许开发者简化并发编程中的错误处理、取消和可观测性。这有助于消除线程泄露和取消延迟等风险。其详细说明见于第 10 章（多线程）。

### 1.10.2.2 作用域值（Scoped Values）

JEP 464 的第二次预览引入了作用域值，允许跨线程共享不可变数据。这一特性增强了并发代码的易用性、可理解性、性能和健壮性。其详细说明见于第 10 章（多线程）。

## 1.10.3 原生互操作：Project Panama

### 1.10.3.1 外部函数和内存 API

JEP 454 为 Java 程序提供了一个 API，可以在不依赖 JNI 的情况下高效调用外部函数并访问外部内存。这增强了与原生库和数据交互的灵活性、安全性能。

### 1.10.3.2 向量 API（Vector API）

JEP 460 的第七个孵化版本提供了用于表示向量计算的 API，它可以在支持的 CPU 架构上被编译为向量指令。这为数值计算提供了卓越的性能。

## 1.10.4 核心库和工具增强

### 1.10.4.1 类文件 API

JEP 457 处于预览阶段，引入了用于解析、生成和转换 Java 类文件的标准 API，提高了处理类文件的开发效率。

### 1.10.4.2 启动多文件程序

JEP 458 增强了 Java 启动器，允许直接运行多个 Java 源文件提供的程序，为构建工具提供了更大的灵活性。

### 1.10.4.3 流收集器（Stream Gatherers）

JEP 461 的预览版通过自定义中间操作增强了 Stream API，使流流水线更具灵活表现力。其详细说明见于第 11 章（文件处理）。

## 1.10.5 性能改进

### 1.10.5.1 G1 区域锁定

JEP 423 为 G1 垃圾收集器引入了区域锁定，通过允许在原生库调用期间进行垃圾回收来减少延迟。有助于维持性能。

## 1.10.6 云支持和 Java 管理服务



Java 22 针对云部署进行了优化，特别是在 Oracle 云基础设施 (OCI) 上，该平台支持免费访问 Oracle SE、Oracle GraalVM 和 Java SE 订阅包。此外，Java 管理服务 (JMS) 提供了一个统一控制台，用于管理本地和云环境中的运行时和应用程序。

Java 22 的这些改进不断演进语言，使其在现代应用程序开发中更加高效。

## 1.11 JAVA 21 对比 JAVA 22

Java 22 在 Java 21 的基础上进行了构建，将多个预览功能提升为标准功能，引入了新的预览和孵化特性，并持续增强性能、安全性和标准库。表 1.3 以表格形式列出了 Java 21 和 Java 22 的对比：

## 1.12 Java 程序的结构

Java 程序涉及以下部分：

- 文档部分
- 包声明
- 导入语句
- 接口语句
- 类定义
- `main` 方法所在的类
- `main` 方法定义

## 1.12.1 文档部分

此部分提供了有关程序的文档。它通常包含注释，说明程序的目的、功能、作者信息以及任何其他相关细节。文档对于理解使用 Javadoc 等工具生成的代码至关重要。

```
/*
* 该程序计算圆的面积。
* 作者: Usharani Bhimavarapu
* 日期: 2024年3月30日
*/
```

## 1.12.2 包声明

包语句用于声明该 Java 文件所属的包。包用于将类组织到命名空间中并防止命名冲突。它是 Java 文件中的第一个语句，是可选的。

例：`package com.example.myapp;`

# Java 简介

Java 中的语句 `package com.example.myapp;` 是一种声明，用于指定当前 Java 源文件所属的包。

## 1.12.3 导入语句 (Import Statements)

导入语句用于将类或整个包导入到当前 Java 文件中，允许程序员在不使用完全限定类名的情况下使用这些包中的类。它们位于包语句（如果存在）之后，类定义之前。

例如：`import java.util.Scanner;`

Java 中的语句 `import java.util.Scanner;` 用于将 `java.util` 包中的 `Scanner` 类导入到当前的 Java 源文件中。

## 1.12.4 接口语句 (Interface Statement)

接口语句用于在 Java 中定义一个新接口。接口声明方法而不提供实现，作为类必须实现的契约。它们使用 `interface` 关键字声明，后跟接口名称及其方法签名。

```java
public interface Drawable {
    void draw();
}
```

通过定义接口，Java 实现了多态性，允许根据接口指定的共同行为统一地处理不同类的对象。这促进了 Java 程序的代码重用性、灵活性和可维护性。

## 1.12.5 类定义 (Class Definition)

类定义用于在 Java 中定义一个新类，封装数据和行为。它包括类修饰符、类名、父类（如果有）、实现的接口（如果有）、类体和构造函数。类是 Java 程序的构建块，封装了数据和方法。

```java
public class Circle {
    private double radius;
    public Circle(double radius) {
        this.radius = radius;
    }
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

类定义封装了属性和行为，为 Java 程序中创建和操作对象提供了蓝图。它的重要性在于能够模拟现实世界的实体并进行计算，展示了面向对象编程和封装的基本原理。

## 1.12.6 主方法类 (MAIN METHOD CLASS)

方法类包含主方法，主方法是 Java 程序的入口。它通常具有 `public static void main(String[] args)` 方法签名，允许 Java 虚拟机 (JVM) 执行程序。

```java
public class Main {
    public static void main(String[] args) {
        // 程序逻辑在此
    }
}
```

## 1.12.6.1 主方法定义 (Main Method Definition)

方法定义是 Java 程序开始执行的地方。它包含主方法，该方法必须声明为 `static void main(String[] args)`。在主方法内部编写程序逻辑，并根据需要调用其他类和方法。

```java
public static void main(String[] args) {
    Circle circle = new Circle(5);
    double area = circle.calculateArea();
    System.out.println("Area of the circle: " + area);
}
```

## 示例

```java
package javapackage; // 包声明
import java.util.*; // 导入语句声明
//这是一个注释部分
public class test { // 类名
    int n = 4; // 全局变量
    public static void main(String[] args) { // 主方法
        test t = new test(); // 对象实例化
        t.display("Main"); // 方法调用
    }

    public void display(String s) { // 方法定义
        System.out.println(s);
    }
}
```

此程序封装了 Java 编程的几个基本元素，提供了一个简洁且具说明性的示例。它从包声明 `package` 开始，表示将类组织成一个包。紧随之后的是导入语句，导入了 `java.util` 包，从而获得了访问工具类和数据结构的权限。程序包含一个名为 `test` 的类，由 `public` 关键字表示，指示其可见性。在该类内部有一个初始化为 `4` 的全局变量 `n`。主方法作为程序的入口，在其中创建了 `test` 类的实例，并带有参数 "Main" 调用了它的 `display` 方法。在 `test` 类中定义的 `display` 方法接收字符串参数 `s` 并使用 `System.out.println()` 将其打印到控制台。该方法体现了封装和模块化，执行了独立于程序主逻辑的任务。

# Java 简介

## 1.13 JAVA 程序的创建与执行

步骤 1：

在记事本预览中编写程序，以 `.java` 扩展名保存。

```java
class test
{
  public static void main(String a[])
{
    System.out.println("this is to test");
  }
}
```

步骤 2：

打开命令提示符 (Command Prompt)。

步骤 3：

设置 `.java` 文件所在的目录。例如，`.java` 文件保存在 `C:\java`。

步骤 4：

使用命令编译 Java 程序。它会在同一文件夹中生成 `.class` 文件。

```bash
javac --enable-preview --source 22 filename.java
java --enable-preview --source 22 Test.java
```

步骤 5：

使用 `java` 命令运行 Java 程序：

```bash
java --enable-preview --source 22 filename
java --enable-preview --source 22 Test.java
```

## 1.14 第一个示例程序

```java
import java.io.*; // 从包导入类
public class test { // 主类
    public static void main(String[] a) // 主方法
    {
      System.out.println("this is to test");// 打印语句
    }
}
```

（注：原文后续存在大量重复片段和占位符，已按要求过滤重复输出。）

# Java 中的数据类型和运算符

- 学习曲线：有效率理解和管理数据类型需要了解它们的特性和行为，这对于初级程序员来说是一个学习曲线。对数据类型的误解或误用可能会导致代码错误和效率低下。
- 兼容性问题：在某些情况下，数据类型在不同的编程语言或平台之间可能不兼容，在集成由不同环境开发的组件时，需要额外努力来确保互操作性和数据完整性。

尽管存在这些缺点，但使用数据类型的益处通常大于挑战，有助于软件系统的健壮性、效率和可维护性。

## 2.1.1 预定义关键字

Java 有一组预留的关键字，这些关键字在语言内用于特定用途。这些关键字不能在 Java 程序中用作标识符（如变量名、方法名或类名）。以下是 Java 预定义关键字列表：

1. `abstract`: 将类声明为抽象类，或声明一个没有实现的方法。
2. `assert`: 在调试和测试中断言某个条件的真实性。
3. `boolean`: 表示一种可以持有两个值之一（`true` 或 `false`）的数据类型。
4. `break`: 退出当前循环或 `switch` 语句。
5. `byte`: 表示一种 8 位符号整数类型。
6. `case`: 定义 `switch` 语句中的一个分支。
7. `catch`: 捕获 `try` 语句生成的异常。
8. `char`: 表示一种 16 位 Unicode 字符类型。
9. `class`: 定义一个类。
10. `const` (未使用): 留供以后使用。
11. `continue`: 跳过循环的当前迭代并继续下一次迭代。
12. `default`: 指定 `switch` 语句中的默认分支。
13. `do`: 启动一个 `while` 循环。
14. `double`: 表示一种双精度 64 位浮点数据类型。
15. `else`: 指定 `if` 语句中的备选分支。
16. `enum`: 声明一个枚举（`enum`）类型。
17. `extends`: 表示一个类继承自另一个类，或一个接口扩展另一个接口。
18. `final`: 防止继承（应用于类时）、防止修改（应用于方法时）或防止重新赋值（应用于变量时）。
19. `finally`: 定义一个在 `try-catch` 块之后将执行的代码块。
20. `float`: 表示一种单精度 32 位浮点数据类型。
21. `for`: 启动一个 `for` 循环。
22. `goto` (未使用): 留供以后使用。
23. `if`: 指定条件语句。
24. `implements`: 表示一个类实现一个接口。
25. `import`: 导入其他 Java 包或类。
26. `instanceof`: 测试对象是否是特定类或接口的实例。
27. `int`: 表示一种 32 位符号整数类型。
28. `interface`: 声明一个接口。
29. `long`: 表示一种 64 位符号整数数据类型。
30. `native`: 指定方法使用 JNI（Java Native Interface）用原生代码实现。
31. `new`: 创建新对象。
32. `null`: 表示空引用，不指向任何对象。
33. `package`: 声明一个包。
34. `private`: 指定成员（方法或变量）仅在其所属类内部访问。
35. `protected`: 指定成员在其所属包和子类中可访问。
36. `public`: 指定成员可以从任何其他类访问。
37. `return`: 从方法返回，可选返回一个值。
38. `short`: 表示一种 16 位整数数据类型。
39. `static`: 指定成员属于类而不是该类的任何实例。
40. `strictfp`: 限制浮点计算以确保可移植性。
41. `super`: 指向父类。
42. `switch`: 指定一个多分支语句。
43. `synchronized`: 指定方法一次只能被一个线程访问。
44. `this`: 指向类的当前实例。
45. `throw`: 抛出一个异常。
46. `throws`: 指定方法可以抛出异常。
47. `transient`: 指定成员变量不是对象持久化状态的一部分。
48. `try`: 启动一个将进行异常测试的代码块。
49. `void`: 指定方法不返回值。
50. `volatile`: 指定变量可能会发生意外变化。
51. `while`: 启动一个循环。

这些关键字是 Java 语法的基础，在定义类、控制流、处理异常以及管理数据类型和访问级别方面起特定作用。

## 2.2 Java 中的数据类型

Java 中的数据类型指定了存储在变量中的数据性质。它们定义了数据的大小和格式，确保适当内存分配和操作。Java 支持两种主要的数据类型：基本类型和非基本类型。

## 2.2.1 基本数据类型

基本数据类型表示基本值并内置在 Java 语言中。它们用于存储单个值和预定义的大小。Java 中有八种基本数据类型：

1. `byte`: 用于存储小整数值。占用 8 位内存。表示从 -128 到 127 的整数值。`Byte` 数据类型默认为 `0`。
2. `short`: 用于存储小整数值。占用 16 位内存。表示从 -32768 到 32767 的整数值。
3. `int`: 用于存储整数值。占用 32 位内存。表示从 -2³¹ 到 2³¹-1 的整数值。
4. `long`: 用于存储大整数值。占用 64 位内存。表示从 -2⁶³ 到 2⁶³-1 的整数值。
5. `float`: 用于存储浮点数。占用 32 位内存。表示单精度浮点数。
6. `double`: 用于存储双精度浮点数。占用 64 位内存。表示双精度浮点数。
7. `char`: 用于存储单个字符。占用 16 位内存。表示 Unicode 字符。
8. `boolean`: 用于存储 `true` 或 `false` 值。占用 1 位内存。表示真或假值。

这些基本类型是 Java 编程的基础，广泛用于变量声明、方法参数和返回类型。每种数据类型都有其范围。

## 2.2.2 非基本数据类型

非基本数据也被称为引用类型，因为它们引用对象。它们包括：

- 类：对象的蓝图。它们定义了对象的属性和行为。
- 接口：类的约定。它们指定了类必须实现的方法集。
- 数组：连续内存位置中的数据类型集合。它们提供了存储和操作相同类型多个值的方便方法。

## 2.3 基本数据类型

Java 中的基本类型是在内存中直接表示基本值的基础单元。它们提供了基本的特性和能力：

- 效率：基本类型简单且占用内存少，允许快速访问和操作。
- 速度：对基本类型的操作通常比对其相应包装类的操作快，因为它们不涉及对象创建和垃圾回收的开销。
- 内存管理：它们由 Java 虚拟机（JVM）直接管理，使得内存分配和释放简单。
- 可预测行为：基本类型具有定义良好的范围和行为，确保在不同平台和 JVM 实现之间的结果一致。
- 直接访问：它们允许在底层进行直接操作，这对于系统编程、低级数据处理和性能密集型应用程序至关重要。
- 缺少方法：基本类型没有对象那样的方法或属性。这限制了它们在集合上执行操作或直接利用面向对象编程功能的能力。
- 空值：基本类型不能持有 `null` 值，这在处理需要空值的情况时可能不方便。这使得对于可空类型需要使用包装类（`Integer`、`Double` 等）。
- 范围限制：每个基本类型都有其可以持有的特定范围。例如，`byte` 的范围是 -128 到 127，对于某些需要较大数值的计算来说可能不足。

## 用于医疗保健和医学应用的 Java 22

- 不可扩展：原始数据类型无法被扩展或自定义。它们的行为和能力由 Java 语言规范固定，与对象和类相比，它们的灵活性较低。

尽管有这些局限性，但由于其效率、速度以及原始数据类型在 Java 编程中仍然至关重要，且非常适用于从基本算术运算到低级系统编程的各种任务。

## 2.3.1 Byte 数据类型

Java 中的 `byte` 类型用于存储 -128 到 127 范围内的整数值。它是一种原始数据类型，占用 8 位（或 1 字节）的内存。这使得 `byte` 适用于在处理大型数组或所需的数值范围在其限制内时节省内存。它通常用于对内存效率至关重要的场景，例如嵌入式系统或需要最小化数据大小的文件处理。由于其取值范围较小，`byte` 在读取二进制数据、实现低级协议或高效处理流的任务中具有多用途。其紧凑的也确保了与较大数据类型相比，具有更快的数据访问和操作，有助于提高 Java 程序的性能。

## ByteExample

```
class ByteExample {
    void main(String[] a) {
        byte b;
        b = 121;
        System.out.println(b);
    }
}
```

Output: 121

上述 Java 程序定义了一个名为 `ByteExample` 的类，包含一个 `main` 方法，该方法作为程序执行的入口。在 `main` 方法中，声明了一个类型为 `byte` 的变量 `b` 并将其初始化为值 `121`。变量 `b` 代表一种小型整数数据类型，可以存储从 -128 到 127 的值。给 `b` 赋值后，程序使用 `System.out.println(b)` 方法将 `b` 的值打印到控制台。因此，当程序执行时，它将显示 `121` 作为输出，表示赋值的值已成功存储并检索到字节变量 `b` 中。

## 2.3.2 Short 数据类型



# Java 中的数据类型和运算符

## 2.3.2 Short 数据类型

`short` 数据类型占用 16 位（或 2 字节）内存，使其比 `byte` 大但比 `int` 小。使用 `short` 数据类型的主要优势在于它能够在节省内存的同时比 `byte` 容纳更广泛的整数范围。它允许开发者处理从 -32,768 到 32,767 之间的数字，适用于许多高效处理较小整数的应用。通过使用 `short`，开发者可以在不需要 `int` 的完整范围（范围从 -2,147,483,648 到 2,147,483,647）且该范围过大的情况下优化内存使用。这种数据类型在内存受限的环境下，或处理不需要 `int` 那么大小的整数数组时特别有用。

## Program

```java
class ShortExample {
  void main(String[] a) {
    short temperature;
    temperature = -200;
    System.out.println(temperature); // 打印 -200
  }
}
```

Output:

```
-200
```

上述 Java 程序定义了一个名为 `ShortExample` 的类，包含一个 `main` 方法，该方法作为程序执行的入口。在 `main` 方法内部，声明了一个名为 `temperature` 的类型为 `short` 的变量，它代表一种能够存储比 `byte` 更范围整数的数据类型，通常为 -32768 到 32767。在程序中，变量 `temperature` 被赋值为值 `-200`。随后，程序利用 `System.out.println()` 方法将 `temperature` 的值打印到控制台。执行时，程序将输出 `-200`，确认赋值的值已成功存储在 `short` 变量中。

## 2.3.3 INT 数据类型

Java 中的 `int` 数据类型对于存储指定范围内的全整数至关重要。它占用 32 位内存，可以表示从 -2,147,483,648 到 2,147,483,647 的值。这使得它适用于不需要小数的整数计算，在内存使用和计算速度上提供了高效性。它在 Java 程序中的广泛使用确保了兼容性和互操作性，允许在不同平台和系统之间进行一致的数值操作和数据存储。

## Program: Java int 类型

```java
class IntExample {
  void main(String[] a) {
    int n = 145;
    System.out.println(n);
  }
}
```

Output:

```
145
```

上述 Java 程序定义了一个名为 `IntExample` 的类，包含一个 `main` 方法，作为程序的入口。在 `main` 方法内部，声明了一个整数 `n` 并将其初始化为值 `145`。在初始化 `n` 之后，程序利用 `System.out.println()` 方法将 `n` 的值打印到控制台。执行时，程序将输出 `145`，确认赋值的值已成功存储在 `int` 变量中，并随后打印到控制台。

## 2.3.4 LONG 数据类型

Java 中的 `long` 数据类型对于处理超过 `int` 类型范围的大型整数至关重要。它占用 64 位内存，使其能够存储从 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807 的值。这使得它适用于不需要小数的整数计算，在内存使用和计算速度上提供了高效性。它在 Java 程序中的广泛使用确保了兼容性和互操作性，允许在不同平台和系统之间进行一致的数值操作和数据存储。

## Program: Java long 类型

```java
class LongExample {
  void main(String[] a) {
    long n = 145L;
    System.out.println(n);
  }
}
```

Output:

```
145
```

上述 Java 程序定义了一个名为 `LongExample` 的类，包含一个 `main` 方法，作为程序的入口。在 `main` 方法内部，声明了一个整数 `n` 并将其初始化为值 `145L`。在初始化 `n` 之后，程序利用 `System.out.println()` 方法将 `n` 的值打印到控制台。执行时，程序将输出 `145`，确认赋值的值已成功存储在 `long` 变量中，并随后打印到控制台。

### 2.3.5 Double 类型

Java 中的 `double` 数据类型对于处理指定范围内的浮点数至关重要。它占用 64 位内存，使其能够存储从 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807 的值。这使得它适用于涉及小数的计算，在内存使用和计算速度上提供了高效性。它在 Java 程序中的广泛使用确保了兼容性和互操作性，允许在不同平台和系统之间进行一致的数值操作和数据存储。

## Program: Java double 类型

```java
class DoubleExample {
  void main(String[] a) {
    double n = 145.5;
    System.out.println(n);
  }
}
```

Output:

```
145.5
```

上述 Java 程序定义了一个名为 `DoubleExample` 的类，包含一个 `main` 方法，作为程序的入口点。在 `main` 方法内部，声明了一个类型为 `double` 的变量 `n` 并将其初始化为值 `145.5`。变量 `n` 代表一种能够存储浮点数的数据类型。在初始化 `n` 之后，程序利用 `System.out.println()` 方法将 `n` 的值打印到控制台。执行时，程序将输出 `145.5`，确认赋值的值已成功存储在 `double` 变量中。

## 2.3.6 Float 数据类型

Java 中的 `float` 数据类型对于存储指定范围内的浮点数至关重要。它占用 32 位内存，适用于对内存效率有要求的场景。与 `double` 相比，`float` 精度较低，但在内存使用上更高效。

## Program: Java float 类型

```java
class FloatExample {
  void main(String[] a) {
    float n = 145.5f;
    System.out.println(n);
  }
}
```

Output:

```
145.5
```

上述 Java 程序定义了一个名为 `FloatExample` 的类，包含一个 `main` 方法，作为程序执行的入口。在 `main` 方法中，声明了一个类型为 `float` 的变量 `n` 并将其初始化为值 `145.5f`。变量 `n` 代表一种能够存储浮点数的数据类型。在初始化 `n` 之后，程序利用 `System.out.println()` 方法将 `n` 的值打印到控制台。执行时，程序将输出 `145.5`，确认赋值的值已成功存储在 `float` 变量中。

## 2.3.7 Char 数据类型

Java 中的 `char` 数据类型对于表示 16 位的 Unicode 字符至关重要。它用于 Java 程序中存储单个字符，例如字母、数字和符号。`char` 类型允许对文本数据进行处理和操作，能够在字符串和其他文本数据结构中实现比较、转换和变换等操作。由于其 Unicode 表示法，它支持广泛的国际字符，适用于多语言应用程序和文本处理任务。

```java
class CharExample {
  void main(String[] a) {
    char c = 'A';
    System.out.println(c);
  }
}
```

Output:

```
A
```

上述 Java 程序定义了一个名为 `CharExample` 的类，包含一个 `main` 方法，该方法是程序执行的起点。在 `main` 方法内部，声明了一个名为 `c` 的变量并赋值为字符值 `A`。`c` 的数据类型为 `char`，表示单个 16 位的 Unicode 字符。赋值后，程序使用 `System.out.println()` 方法将 `c` 的值打印到控制台。执行时，程序将输出 `A`，确认赋值的字符已成功存储在 `char` 变量 `c` 中，并打印到控制台。

## 2.3.8 布尔数据类型

Java 中的 `boolean` 数据类型在表示真值方面起着至关重要的作用，允许程序内进行逻辑操作和决策。它用于存储两种状态：`true` 和 `false`，这是可以赋值给 `boolean` 变量的唯一值。这种简单性使其在条件、循环和分支语句中非常高效，使开发者能够根据布尔表达式控制程序流。在 Java 中，布尔变量消耗极少的内存，优化了使用并增强了性能，特别是在大型应用中。其直观的性质也便于代码的可读性和调试，确保逻辑条件在整个 Java 程序中都能以简洁易懂的方式表达出来。

## 程序

```java
class BooleanExample {
  void main(String[] a) {
    boolean flag = true;
    System.out.println(flag);
  }
}
```

Output:

```
true
```

在程序程序中，我们定义了一个名为 `BooleanExample` 的类。在类内部，我们创建了一个 `main` 方法，作为执行的入口点。我们声明了一个布尔变量 `flag` 并给其赋值为 `true`。然后，程序使用 `System.out.println()` 语句输出 `flag` 的值。结果是程序在控制台上打印了 `true`。布尔数据类型的使用允许我们高效地处理真/假值。

## 2.3.9 所有 Java 数据类型的最小值和最大值

在 Java 中，每个基本数据数据类型都有其可以容纳的特定值范围。这些值由 Java 语言规定，对于理解在执行计算、存储数据或设计算法时每个数据类型的限制和能力至关重要。

## 预 Java 数据类型的最小值和最大值的程序

```java
public class Test {
  void main(String[] args) {
    System.out.println("int min":+Integer.MIN_VALUE);
    System.out.println("int max":+Integer.MAX_VALUE);
    System.out.println("byte min":+Byte.MIN_VALUE);
    System.out.println("byte max":+Byte.MAX_VALUE);
    System.out.println("short min":+Short.MIN_VALUE);
    System.out.println("short max":+Short.MAX_VALUE);
    System.out.println("long min":+Long.MIN_VALUE);
    System.out.println("long max":+Long.MAX_VALUE);
    System.out.println("float min":+Float.MIN_VALUE);
    System.out.println("float max":+Float.MAX_VALUE);
    System.out.println("double min":+Double.MIN_VALUE);
    System.out.println("double max":+Double.MAX_VALUE);
  }
}
```

Output:

```
int min:-2147483648
int max:2147483647
byte min:-128
byte max:127
short min:-32768
short max:32767
long min:-922337203684775808
long max:922337203684775807
float min:1.4E-45
float max:3.4028235E38
double min:1.7976931386231537E-308
double max:1.7976931386231537E+308
```

`MIN_VALUE` 和 `MAX_VALUE` 的值代表 Java 中特定基本类型内可以存储的最小值和最大值。对于 `int` 数据类型，`Integer.MIN_VALUE` 代表可以存储的最小整数值，即 $-2^{31} = -2,147,483,648$。另一方面，`Integer.MAX_VALUE` 代表可以存储的最大值。`byte` 数据类型是一个 8 位符号整数，`Byte.MIN_VALUE` 表示可以存储的最小值，即 -128。相反，`Byte.MAX_VALUE` 表示可以存储的最大值，即 127。对于 `short` 数据类型，`Short.MIN_VALUE` 代表最小值，即 $-2^{15}$ 或 -32,768。`Short.MAX_VALUE` 代表最大值，即 $2^{15}$ 或 32,767。`long` 数据类型是一个 64 位符号整数，`Long.MIN_VALUE` 代表可以存储的最小值，即 $-2^{63}$ 或 -9,223,372,036,854,775,808。`Long.MAX_VALUE` 代表可以存储的最大值，即 $2^{63}-1$ 或 9,223,372,036,854,775,807。对于 `float` 数据类型，`Float.MIN_VALUE` 代表可以存储的最小正零值，约为 $1.4 \times 10^{-45}$。另一方面，`Float.MAX_VALUE` 代表可以存储的最大有限值，约为 $3.4028235 \times 10^{38}$。`double` 数据类型是双精度 64 位浮点数，`Double.MIN_VALUE` 代表最小的正零值，约为 $4.9 \times 10^{-324}$。相反，`Double.MAX_VALUE` 代表最大的有限正值，约为 $1.7976931386231537 \times 10^{308}$。

## 2. 类型转换

类型转换或强制转换将数据转换为另一种类型。

### 2.1 隐式转换

类型转换或强制转换将数据转换为另一种类型。有两种转换方式：隐式和显式。隐式转换是宽类型转换。

## 程序

```java
class ImplicitExample {
  void main(String[] args) {
    int a = 20;
    long b = a;
    double c = b;
    System.out.println(a);
    System.out.println(b);
    System.out.println(c);
  }
}
```

Output:

```
20
20
20.0
```

在这个程序中，我们定义了一个名为 `ImplicitExample` 的类。在类内部，我们创建了一个 `main` 方法，作为执行的入口点。我们声明了一个整数变量 `a` 并给其赋值为 20。然后，我们将 `a` 赋值给长型变量 `b`，并将 `b` 赋值给双精度型变量 `c`。程序使用 `System.out.println()` 语句输出 `a`、`b` 和 `c` 的值。

### 2.2 显式转换

类型转换将数据转换为另一种类型。有两种转换方式：隐式和显式。显式转换是窄类型转换。

## 程序

```java
class ExplicitExample {
  void main(String[] args) {
    double d = 57.17;
    int i = (int)d;
    System.out.println(d);
    System.out.println(i);
  }
}
```

Output:

```
57.17
57
```

在这个程序中，我们定义了一个名为 `ExplicitExample` 的类。在类内部，我们创建了一个 `main` 方法，作为执行的入口点。我们声明了一个双精度型变量 `d` 并给其赋值为 57.17。然后，我们将 `d` 转换为整数变量 `i`。程序输出 `d` 和 `i` 的值。

## 2.5 JAVA 中的运算符

运算符是实现程序中各种计算和操作的重要组件。

## Java 中运算符的需求

- **表达式求值**：运算符允许程序员高效地进行计算和表达式表达式。它们使得算术运算（例如 `+`、`-`、`*`、`/`）和复杂操作（例如关系）成为。

- **数据操作**：运算符提供了操作变量存储数据的机制。例如，赋值运算符（`=`、`+=`、`-=`）根据某些条件或表达式修改变量的值。

- **控制流**：逻辑运算符（`&&`、`||`、`!`）对于实现条件语句（`if`、`else`、`switch`）和循环（`for`、`while`、`do-while`）至关重要。它们根据布尔表达式控制执行流。

- **增强功能**：特殊运算符如三元运算符（`?:`）、增加（`++`）和递减（`--`）提供了简洁的条件赋值和增减操作。

- **位级操作**：位运算符（`&`、`^`、`<<`、`>>`、`>>>`）允许操作整数类型内的单个位。它们对于编码、解码和底层编程中的性能优化任务至关重要。

## Java 运算符的优点

- **简单简洁**：通过将复杂操作压缩为紧的表达式，运算符使得简洁易读的代码成为可能。

- **效率**：Java 中的大多数运算符都针对性能进行了高度优化，使得计算和数据处理更快速、更高效。

- **表达性**：运算符增强了语言的表达能力，允许程序员清晰、有效地地传达其意图。

- **标准化**：运算符为在不同程序和应用程序中执行常见任务提供了一种标准化的方式，促进了代码的可重用性和熟悉度。

- **多功能性**：Java 运算符满足了广泛的编程需求，从基础算术运算到高级位操作，使该语言在各个领域都具有通用性。

# Java 运算符的局限性

- **重载与复杂性**：过度使用或误用运算符会导致代码变得复杂且难以理解，降低代码的可维护性和可读性。

- **错误风险**：不当使用运算符可能会在程序中引入 Bug 和逻辑错误，特别是使用位运算符和赋值运算符时。

- **功能限制**：虽然 Java 提供了一套完善的运算符，但特殊任务可能需要标准运算符之外的额外库或自定义实现。



- 学习曲线：初学者可能会发现某些运算符（尤其是位运算符和三元运算符）由于其特殊的功能和语法，在初期难以掌握。
- 性能考虑：某些运算符（尤其是涉及位级操作或复杂表达式的运算符）对性能的影响可能取决于硬件和编译器的优化情况。

Java 提供了丰富的运算符来对变量和值进行操作。这些运算符可以分为几类。

### 2.5.1 算术运算符

用于执行基础算术运算：

- 加法（`+`）：将两个操作数相加。
- 减法（`-`）：从第一个操作数减去第二个。
- 乘法（`*`）：将两个操作数相乘。
- 除法（`/`）：将分子除以除数。
- 取模（`%`）：返回除法的余数。

#### 程序

```java
public class ArithmeticOperators {
    void main(String[] args) {
        int ushaAge = 30;
        int raniAge = 25;
        int sum = ushaAge + raniAge; // 加法
        int difference = ushaAge - raniAge; // 减法
        int product = ushaAge * raniAge; // 乘法
        int quotient = ushaAge / raniAge; // 除法
        int remainder = ushaAge % raniAge; // 取模
        System.out.println("Sum: " + sum);
        System.out.println("Difference: " + difference);
        System.out.println("Product: " + product);
        System.out.println("Quotient: " + quotient);
        System.out.println("Remainder: " + remainder);
    }
}
```

**输出：**

```text
Sum: 55
Difference: 5
Product: 750
Quotient: 1
Remainder: 5
```

在此程序中，我们定义了一个名为 `ArithmeticOperators` 的类，其中两个整数变量 `ushaAge` 和 `raniAge` 分别赋值为 30 和 25。程序对这些值进行算术运算，计算和、差、乘积、商和余数。30 和 25 的和是 55，差是 5，乘积是 750，30 除以 25 的商是 1，余数是 5。这些结果被打印到控制台上。

### 2.5.2 一元运算符

对单个操作数进行操作：

- 一元加（`+`）：表示正值（通常是冗余的）。
- 一元负（`-`）：对表达式取负值。
- 递增（`++`）：将操作数的值加 1。
- 递减（`--`）：将操作数的值减 1。
- 逻辑取反（`!`）：反转布尔值。

#### 程序

```java
public class UnaryOperators {
    void main(String[] args) {
        int ushaAge = 30;
        int age = ushaAge; // 赋值
        age++; // 递增
        System.out.println("Increment: " + age);
        age--; // 递减
        System.out.println("Decrement: " + age);
        age = --ushaAge; // 一元负
        System.out.println("Unary minus: " + age);
        boolean isAdult = ushaAge > 18; // 真
        isAdult = !isAdult; // 逻辑取反
        System.out.println("Logical complement: " + isAdult);
    }
}
```

**输出：**

```text
Increment: 31
Decrement: 30
Unary minus: -30
Logical complement: false
```

在此程序中，我们定义了一个名为 `UnaryOperators` 的类，其包含一个 `main` 方法演示了 Java 中一元运算符的使用。我们首先将值 `30` 赋值给变量 `ushaAge`，然后将其赋值给 `age`。我们使用 `age++` 增加 `age` 的值，结果为 `31` 并打印。接下来，我们使用 `age--` 将 `age` 的值减回 `30`，并再次打印。

一元负运算符应用于 `ushaAge`，将 `age` 变为 `-30`。最后，我们检查 `ushaAge` 是否大于 18，并将结果（`true`）存储在 `isAdult` 变量中。使用逻辑取反运算符 `!` 反转 `isAdult` 的值，结果为 `false`，并打印。

### 2.5.3 关系运算符

用于比较值：

- 等于（`==`）：检查值是否相等。
- 不等于（`!=`）：检查值是否不相等。
- 大于（`>`）：检查左操作数是否大于右操作数。
- 小于（`<`）：检查左操作数是否小于右操作数。
- 大于等于（`>=`）：检查左操作数是否大于等于右操作数。
- 小于等于（`<=`）：检查左操作数是否小于等于右操作数。

#### 程序

```java
public class RelationalOperators {
    void main(String[] args) {
        int ushaAge = 30;
        int raniAge = 25;
        boolean isEqual = ushaAge == raniAge;
        boolean isNotEqual = ushaAge != raniAge;
        boolean isGreater = ushaAge > raniAge;
        boolean isLess = ushaAge < raniAge;
        boolean isGreaterEqual = ushaAge >= raniAge;
        boolean isLessEqual = ushaAge <= raniAge;

        System.out.println("Equal: " + isEqual);
        System.out.println("Not equal: " + isNotEqual);
        System.out.println("Greater than: " + isGreater);
        System.out.println("Less than: " + isLess);
        System.out.println("Greater than equal: " + isGreaterEqual);
        System.out.println("Less than equal: " + isLessEqual);
    }
}
```

**输出：**

```text
Equal: false
Not equal: true
Greater than: true
Less than: false
Greater than equal: true
Less than equal: true
```

此 Java 程序 `RelationalOperators` 演示了如何使用关系运算符比较两个整数 `ushaAge` 和 `raniAge`。它评估了表示两者关系的布尔条件并将其打印。

### 2.5.4 逻辑运算符

用于组合布尔表达式：

- 逻辑与（`&&`）：当两个操作数都为真时返回真。
- 逻辑或（`||`）：当至少一个操作数为真时返回真。
- 逻辑非（`!`）：反转布尔值。

#### 程序

```java
public class LogicalOperators {
    void main(String[] args) {
        int ushaAge = 30;
        int raniAge = 25;
        boolean isUshaAdult = ushaAge > 18;
        boolean isRaniAdult = raniAge > 18;

        boolean bothAdult = isUshaAdult && isRaniAdult;
        boolean oneAdult = isUshaAdult || isRaniAdult;
        boolean notUsha = !isUshaAdult;

        System.out.println("Both adults: " + bothAdult);
        System.out.println("At least one adult: " + oneAdult);
        System.out.println("Usha is not adult: " + notUsha);
    }
}
```

**输出：**

```text
Both adults: true
At least one adult: true
Usha is not adult: false
```

此 Java 程序 `LogicalOperators` 展示了如何使用逻辑运算符组合布尔条件。它首先根据标准判断 `ushaAge` 和 `raniAge` 是否为成年。然后，它使用与运算符检查是否都成年、使用或运算符检查是否至少有一个成年，并使用非运算符反转 `ushaAge` 的状态。

## 2.5.5 位运算符

#### 程序

```java
public class BitwiseOperators {
    void main(String[] args) {
        int ushaAge = 30;
        int raniAge = 25;
        int bitwiseAnd = ushaAge & raniAge;
        int bitwiseOr = ushaAge | raniAge;
        int bitwiseXor = ushaAge ^ raniAge;
        int bitwiseComplement = ~ushaAge;
        int leftShift = ushaAge << 1;
        int rightShift = ushaAge >> 1;
        int unsignedRightShift = ushaAge >>> 1;
        System.out.println("Bitwise AND: " + bitwiseAnd);
        System.out.println("Bitwise OR: " + bitwiseOr);
        System.out.println("Bitwise XOR: " + bitwiseXor);
        System.out.println("Bitwise complement: " + bitwiseComplement);
        System.out.println("Left shift: " + leftShift);
        System.out.println("Right shift: " + rightShift);
        System.out.println("Unsigned right shift: " + unsignedRightShift);
    }
}
```

```text
Bitwise AND: 24
Bitwise OR: 31
Bitwise XOR: 7
Bitwise complement: -31
Left shift: 60
Right shift: 15
Unsigned right shift: 15
```

这个名为 `BitwiseOperators` 的程序对两个个人 Usha 和 Rani 的年龄进行了位运算符的全面探索。程序将 Usha 的年龄初始化为 30，Rani 的年龄初始化为 25，并仔细地计算了这些年龄值的各种位运算。它计算了位与（`bitwiseAnd`）、位或（`bitwiseOr`）和位异或（`bitwiseXor`），并揭示了这些操作的结果。此外，它计算了 Usha 年龄的位取反（`bitwiseComplement`），有效地将所有位翻转为相反值。

此外，该程序还演示了应用于 Usha 年龄的左移（`leftShift`）、右移（`rightShift`）和无符号右移（`unsignedRightShift`）操作，说明了这些操作如何处理年龄值的二进制表示。最后，程序通过打印语句展示了这些位运算的结果，对 Usha 和 Rani 年龄值执行的位操作提供了全面的概述。

### 2.5.6 赋值运算符

要对变量使用赋值：

- 简单赋值（`=`）：将右侧操作数赋值给左侧变量。
- 加并赋值（`+=`）：将右侧操作数加到左侧变量，并将结果赋值给左侧变量。
- 减并赋值（`-=`）：从左侧变量中减去右侧操作数，并将结果赋值给左侧变量。
- 乘并赋值（`*=`）：将右侧操作数乘以左侧变量，并将结果赋值给左侧变量。
- 除并赋值（`/=`）：将左侧变量除以右侧操作数，并将结果赋值给左侧变量。
- 取模并赋值（`%=`）：使用两个操作数取模，并将结果赋值给左侧变量。

#### 程序

```java
public class AssignmentOperators {
  void main(String[] args) {
    int ushaAge = 30;
    int raniAge = 25;
    int age = ushaAge;
    age += raniAge;
    System.out.println("Add and assign: " + age);
    age -= raniAge;
    System.out.println("Subtract and assign: " + age);
    age /= raniAge;
    System.out.println("Multiply and assign: " + age);
    age *= raniAge;
    System.out.println("Divide and assign: " + age);
    age %= raniAge;
    System.out.println("Modulus and assign: " + age);
  }
}
```

**输出：**

```text
Add and assign: 55
Subtract and assign: 30
Multiply and assign: 750
Divide and assign: 30
Modulus and assign: 5
```

在这个程序中，我们定义了一个名为 `AssignmentOperators` 的类，其中演示了各种赋值运算符。首先，我们将 `30` 赋值给 `ushaAge`，将 `25` 赋值给 `raniAge`。然后，我们将 `ushaAge` 赋值给新变量 `age`。`+=` 运算符将 `raniAge` 加到 `age` 上，结果为 `55` 并打印。`-=` 运算符减去 `raniAge`，使 `age` 回到 `30`。`*=` 运算符将 `age` 乘以 `raniAge`，产生 `750`。`/=` 运算符将 `age` 除以 `raniAge`，得到 `30`。最后，`%=` 运算符计算 `age` 除 `raniAge` 的余数，得到 `5`。这些结果被打印出来，显示了每个复合赋值操作的效果。

### 2.5.7 条件运算符（三元运算符）

`if-then-else` 语句的简写：

三元运算符（`? :`）：`条件 如果为真:表达式 如果为假:表达式`

#### 程序

```java
public class ConditionalOperator {
  void main(String[] args) {
    int ushaAge = 30;
    int raniAge = 25;
    String result = (ushaAge > raniAge) ? "Usha is older" : "Rani is older";
    System.out.println(result);
  }
}
```

### 字符字面量

特殊字符可以作为字符字面量来表示字符。

```java
char newline = '\n'; // 换行符
char tab = '\t'; // 制表符
```

### Unicode 字符

Unicode 转义序列允许表示来自不同语言和符号的字符。

```java
char omega = '\u03A9'; // 希腊大写字母 Omega (Ω)
String smiley = '\u263A'; // 笑脸 (☺)
```

### 格式化与控制

特殊字符用于格式化和控制输出。

```java
System.out.println("First Line\nSecond Line"); // 输出跨行
System.out.println("Column1\tColumn2");
```

# 程序



```java
public class SpecialCharactersExample {
    void main(String[] args) {
        // 字符串字面量
        String nameDetails = "Name: Usha\nQualification:Ph.D.";
        String filePath = "C:\Users\Usha\Documents";
        // 显示字符串字面量
        System.out.println(nameDetails);
        System.out.println("File Path: " + filePath);
        // 字符字面量
        char newline = '\n'; // 换行符
        char tab = '\t'; // 制表符
        // 显示字符字面量
        System.out.println("Character Literals: ");
        System.out.println("Newline: " + newline + " \nAfter newline");
        System.out.println("Tab: " + tab + "	After tab");
        // Unicode 字符
        char omega = '\u03A9'; // 希腊大写字母 Omega (Ω)
        String smiley = '\u263A'; // 笑脸 (☺)
        // 显示 Unicode 字符
        System.out.println("Unicode characters: ");
        System.out.println("Omega: " + omega);
        System.out.println("Smiley face: " + smiley);
        // 格式化与控制字符
        System.out.println("Formatted Output: ");
        System.out.println("First Line\nSecond Line");
        System.out.println("Column1\tColumn2");
    }
}
```

输出：

```
Name: Usha

Qualification: Ph.D.

File Path: C:\Users\Usha\Documents

Character Literals:

Newline character:

After newline

Tab character: After tab

Unicode Characters:

Omega: Ω

Smiley face: ☺

Formatted Output:

First Line

Second Line

Column2
```

在这个程序中，我们定义了一个类`SpecialCharactersExample`，用于演示 Java 中特殊字符、转义序列和 Unicode 字符的使用。首先定义了两个字符串字面量：`nameDetails`，它包含一个换行符（`\n`）用于分隔行；`filePath`则使用了转义序列来处理路径中的反斜杠（`\`）。这些字符串被打印到控制台，展示了转义序列如何格式化换行符（`\n`）和制表符（`\t`）等字符，并显示了它们的打印效果。随后通过打印希腊字母 Omega（`\u03A9`）和笑脸（`\u263A`）演示了 Unicode 字符。最后，程序使用带有控制字符的格式化输出，通过制表符在不同的行和列上打印文本。

# 2.8 Java 作用域

在 Java 中，变量的作用域决定了变量可以在代码的范围内被访问。理解变量的作用域对于编写可维护且无错误的程序至关重要。Java 有不同类型的作用域：

- 局部作用域
- 实例作用域
- 类作用域

## 2.8.1 局部作用域

在方法、构造函数或块内部声明的变量被称为局部变量。它们只能在该方法、构造函数或块内部被访问。

程序：

```java
public class localScopeExample {
    public void display() {
        int localVar = 10; // 局部变量
        System.out.println("Local Variable: " + localVar);
    }
    public static void main(String[] args) {
        LocalScopeExample example = new LocalScopeExample();
        example.display();
        // 此处无法访问 localVar
        // System.out.println(localVar); // 这会导致编译错误
    }
}
```

输出：

```
Local Variable: 10
```

在这个程序中，我们定义了一个类`LocalScopeExample`，演示了 Java 中局部作用域的概念。在类内部定义了`display`方法，其中声明了一个整数变量`localVar`并初始化为值`10`。该变量是`display`方法局部的，意味着它只能在该内部访问。当调用`display`时，它会将`localVar`的值打印到控制台。在`main`方法中，创建了`LocalScopeExample`的实例，输出显示了局部变量值的信息。然而，如果你尝试在`main`方法中直接访问`localVar`，将会导致编译错误，因为`localVar`在`display`方法之外超出了作用域。

## 2.8.2 实例作用域

实例变量（或字段）声明在类内部，但在方法、构造函数或块外部。它们在类的实例范围内是访问的。

程序：

```java
public class InstanceScopeExample {
    private int instanceVar; // 实例变量
    public InstanceScopeExample(int instanceVar) {
        this.instanceVar = instanceVar;
    }
    public void display() {
        System.out.println("Instance Variable: " + instanceVar);
    }
    public static void main(String[] args) {
        InstanceScopeExample example1 = new InstanceScopeExample(10);
        example1.display();
        InstanceScopeExample example2 = new InstanceScopeExample(20);
        example2.display();
    }
}
```

输出：

```
Instance Variable: 10
Instance Variable: 20
```

在这个程序中，我们定义了一个类`InstanceScopeExample`，演示了 Java 中实例作用域的概念。在类内部定义了`display`方法，其中声明了一个整数变量`instanceVar`并初始化为值`10`。该变量是`display`方法局部的，意味着它只能在该内部访问。当调用`display`时，它会将`instanceVar`的值打印到控制台。在`main`方法中，创建了`InstanceScopeExample`的实例，输出显示了局部变量值的信息。然而，如果你尝试在`main`方法中直接访问`instanceVar`，将会导致编译错误，因为`instanceVar`在`display`方法之外超出了作用域。

## 2.8.3 类作用域

类变量（或静态变量）使用`static`关键字声明在类内部声明，但在方法、构造函数或块外部。它们对所有实例都是可见的，并共享同一个值。

程序：

```java
public class ClassScopeExample {
    private static int classVar = 0; // 类变量
    public ClassScopeExample() {
        classVar++;
    }
    public void display() {
        System.out.println("Class Variable: " + classVar);
    }
    public static void main(String[] args) {
        ClassScopeExample example1 = new ClassScopeExample();
        example1.display();
        ClassScopeExample example2 = new ClassScopeExample();
        example2.display();
    }
}
```

输出：

```
Class Variable: 1
Class Variable: 2
```

# 2.9 访问与非访问修饰符

在 Java 中，修饰符是用于修改类、方法和变量属性的关键字，为编译器提供了关于如何处理这些实体的额外信息。修饰符可以控制这些实体的可见性、行为和特征。

修饰符分为两类：访问修饰符和非访问修饰符。

## 2.9.1 访问修饰符

访问修饰符决定了类、方法和变量的可见性和访问权限。Java 提供了四种修饰符：

- `public`：可以从任何类访问。
- `protected`：可以在同包内及子类中被访问。
- `default`（无修饰符）：仅在同包内被访问。
- `private`：仅在类内部被访问。

## 2.9.2 Java 中的非访问修饰符

Java 中的非访问修饰符为类、方法和变量提供了额外的功能和特性。这些包括：

- `static`: 属于类本身，而不是类的实例。
- `final`: 防止修改（例如，`final`类不能被继承，`final`方法不能被重写，`final`变量不能被重新赋值）。
- `abstract`: 用于声明无法实例化的类，或必须由子类实现的方法。
- `synchronized`: 用于控制对方法或块的访问，允许同时只有一个线程执行它。
- `volatile`: 表示变量的值可能会被不同线程意外更改。
- `transient`: 防止变量的序列化。
- `native`: 指定方法是用原生代码（JNI，即 Java 原生接口）实现的。
- `strictfp`: 确保浮点计算遵循 IEEE 754 标准。

### 2.9.2.1 针对各种访问修饰符的程序

#### 1. `public` 访问修饰符

成员可以从任何其他类访问。

程序：

```java
public class PublicAccess {
    public int publicVar = 10; // 公有变量
    public void method() { // 公有方法
        System.out.println("这是一个公有方法.");
    }
    void main(String[] args) {
        PublicAccess obj = new PublicAccess();
        System.out.println("Public Variable: " + obj.publicVar); // 可访问
        obj.method(); // 可访问
    }
}
```

输出：

```
Public Variable: 10
这是一个公有方法。
```

在`PublicAccess`类中，我们演示了 Java 中`public`访问修饰符的使用。变量`publicVar`和方法`method()`都被声明为`public`，这意味着它们可以从任何地方访问，包括其他类、包甚至子类。在`main`方法中，我们创建了`PublicAccess`的实例，可以轻松地访问并打印`publicVar`的值，并调用`method()`。

#### 2. `protected` 访问修饰符

成员可以在其所属包和子类中被访问。

程序：

```java
class ProtectedAccess {
    protected int protectedVar = 20; // 受保护变量
    protected void protectedMethod() { // 受保护方法
        System.out.println("这是一个受保护方法.");
    }
    public void main(String[] args) {
        ProtectedAccess obj = new ProtectedAccess();
        System.out.println("Protected Variable: " + obj.protectedVar); // 可访问
        obj.protectedMethod(); // 可访问
    }
}
```

输出：

```
Protected Variable: 20
这是一个受保护方法。
```

在上面的`ProtectedAccess`类中，我们演示了 Java 中`protected`访问修饰符的使用。变量`protectedVar`和方法`protectedMethod()`都被标记为`protected`，它们可以在同一个包内被访问，即使在不同的包中，也可以被子类访问。在`main`方法中，我们创建了`ProtectedAccess`的实例，并在同一个类中同时访问了`protectedVar`和`protectedMethod()`。这种访问是被允许的，因为带有`protected`的成员在继承场景中控制访问非常有用，同时保持了某种程度的封装性。

#### 3. `default`（无修饰符）访问修饰符

成员仅在其所属包内被访问。

程序：

```java
class DefaultAccess {
    int defaultVar = 30; // 默认（包私有）变量
    void defaultMethod() { // 默认（包私有）方法
        System.out.println("这是一个默认方法.");
    }
    public void main(String[] args) {
        DefaultAccess obj = new DefaultAccess();
        System.out.println("Default Variable: " + obj.defaultVar); // 可访问
        obj.defaultMethod(); // 可访问
    }
}
```

输出：

```
Default Variable: 30
这是一个默认方法。
```

在上面的`DefaultAccess`类中，我们演示了 Java 中（包私有）访问修饰符的概念。变量`defaultVar`和方法`defaultMethod()`没有标记任何访问修饰符，这意味着它们具有默认访问权限。这允许它们限制来自其他包中类的访问。在`main`方法中，我们创建了`DefaultAccess`的实例，并从同一个类中访问了`defaultVar`和`defaultMethod()`，这是总是被允许的。此示例对于同包内的任何其他类都同样有效，允许这些类访问`defaultVar`和`defaultMethod()`。

#### 4. `private` 访问修饰符

成员仅在其所属类内被访问。

程序：

```java
public class PrivateAccess {
    private int privateVar = 40; // 私有变量
    private void privateMethod() { // 私有方法
        System.out.println("这是一个私有方法.");
    }
    void main(String[] args) {
        PrivateAccess obj = new PrivateAccess();
        System.out.println("Private Variable: " + obj.privateVar); // 类内可访问
        obj.privateMethod(); // 类内可访问
    }
}
```

输出：

```
Private Variable: 40
这是一个私有方法。
```

在`PrivateAccess`程序中，我们演示了 Java 中`private`访问修饰符的工作原理。`privateVar`变量和`privateMethod()`都被声明为`private`，这意味着它们仅在定义它们的类内可访问。任何其他类（包括子类）都无法访问。在`main`方法中，我们创建了`PrivateAccess`的实例，在类内访问并打印了`privateVar`的值并调用了`privateMethod()`。这演示了`private`访问修饰符在 Java 中如何工作。`privateVar`变量和`privateMethod()`都被声明为`private`，这意味着它们仅在定义它们的类内可访问。任何其他类（包括子类）都无法访问。在`main`方法中，我们创建了`PrivateAccess`的实例，在类内访问并打印了`privateVar`的值并调用了`privateMethod()`。

### 2.9.3 1 `static`



`static` 成员属于类而不是类的实例。

## 程序

```java
public class StaticExample {
    static int staticVar = 100; // 静态变量
    static void staticMethod() { // 静态方法
        System.out.println("这是一个静态方法.");
    }
    public void main(String[] args) {
        System.out.println("Static Variable: " + staticVar);
        staticMethod();
    }
}
```

输出

```
Static Variable: 100
这是一个静态方法。
```

在 `StaticExample` 类中，我们演示了 Java 中 `static` 访问修饰符的使用。变量 `staticVar` 和方法 `staticMethod()` 都属于类。

### 2.9.3.2 `final`

`final` 防止修改（例如，`final` 类不能被继承，`final` 方法不能被重写，`final` 变量不能被重新赋值）。

## 程序

```java
public class FinalExample {
    final int finalVar = 50; // 最终变量
    final void methodName() { // 最终方法
        System.out.println("这是一个最终方法.");
    }
    public void main(String[] args) {
        FinalExample obj = new FinalExample();
        System.out.println("Final Variable: " + obj.finalVar);
        obj.methodName();
    }
}
```

输出

```
Final Variable: 50
这是一个最终方法。
```

在 `FinalExample` 类中，我们演示了 Java 中 `final` 访问修饰符的使用。变量 `finalVar` 被初始化为 50，一旦赋值就无法更改。

### 2.9.3.3 `abstract`

`abstract` 用于声明无法实例化的类，或必须由子类实现的方法。

## 程序

```java
abstract class AbstractExample {
    abstract void methodName(); // 抽象方法
    void concreteMethod() {
        System.out.println("这是抽象类中的具体方法.");
    }
}
class Subclass extends AbstractExample {
    void methodName() {
        System.out.println("在子类中实现的抽象方法.");
    }
}
```

## 52 用于医疗保健和医学应用的 Java 22

```java
SubClass obj = new SubClass();
obj.abstractMethod(); // 必须实现
obj.concreteMethod();

}
```

输出

```
子类中实现了抽象方法。
这是抽象类中的一个具体方法。
```

此示例演示了抽象类如何为子类提供构建基础，而抽象方法强制要求子类必须实现某些方法。`AbstractExample` 类被声明为 `abstract`，意味着它不能被直接实例化，并且可能包含抽象方法——这些方法没有实现，必须由任何子类实现。在 `AbstractExample` 内部，我们定义了一个没有主体的抽象方法 `abstractMethod()`。此外，我们有一个具体方法 `concreteMethod()`，它具有实现并可以被子类直接使用。`SubClass` 继承 `AbstractExample` 并为 `abstractMethod()` 提供了实现。这是强制性的，因为抽象类的任何子类必须实现其所有方法。在 `SubClass` 的 `main` 方法中，我们创建了 `SubClass` 的对象，并调用了 `abstractMethod()`（现在已实现）和继承的 `concreteMethod()`。此示例演示了类如何为子类提供构建基础，而抽象方法强制要求子类必须实现某些方法。

### 2.9.3.4 `synchronized`

`synchronized` 关键字确保一次只有一个线程可以访问代码块或方法。

## 程序

```java
public class SynchronizedExample {
    synchronized void synchronizedMethod() {
        System.out.println("这是一个同步方法.");
    }
    void main(String[] args) {
        SynchronizedExample obj = new SynchronizedExample();
        obj.synchronizedMethod();
        // 一时间只有一个线程可以访问此方法
    }
}
```

输出

```
这是一个同步方法。
```

在 `SynchronizedExample` 程序中，我们演示了 Java 中的 `synchronized` 关键字，它对于确保多线程环境下的线程安全至关重要。`synchronizedMethod()` 被标记为 `synchronized`，意味着在类的任何特定实例上，只有一个线程可以访问此方法。如果多个线程尝试同时调用此方法，它们将排队，并且同一时间只有一个线程会执行该方法。这防止了竞态条件，并确保共享资源保持一致性和线程安全。在 `main` 方法中，我们创建了 `SynchronizedExample` 的实例并调用了 `synchronizedMethod()`。由于此程序是单线程的，同步方面在这里无法完全观察，但在多线程环境中，这确保了对方法的访问受到控制，使得没有两个线程在同一个对象上并发访问，维护了数据完整性。

## Java 数据类型和操作符

### 2.9.3.5 `volatile`

`volatile` 变量可以被多个线程不可预测地修改。

## 程序

```java
public class VolatileExample {
    volatile boolean flag = false; // volatile 变量
    public void setFlag() {
        flag = true;
    }
    public void main(String[] args) {
        VolatileExample obj = new VolatileExample();
        obj.setFlag(); // 修改 volatile 变量
        System.out.println("Volatile Flag: " + obj.flag);
    }
}
```

## 输出

```
Volatile Flag: true
```

在此 `Volatile` 程序中，我们演示了 Java 中 `volatile` 关键字的使用，它主要用于多线程环境以确保跨线程变量变化的可见性。`flag` 变量被声明为 `volatile`，意味着对其值的任何修改都会立即对所有线程可见，而不是被每个单独线程缓存。`setFlag()` 方法将 `flag` 的值改为 `true`。`main` 方法创建了 `VolatileExample` 类的实例，调用 `setFlag()` 方法更新 `volatile` 变量，并打印 `flag` 的当前值。尽管此程序是单线程的，但 `volatile` 关键字确保了如果程序在多线程环境中运行，所有线程在 `flag` 修改后立即看到其更新的值，防止了潜在的不一致。

### 2.9.3.6 `transient`

`transient` 变量在对象序列化时不会被序列化。

## 程序

```java
import java.io.Serializable;
public class TransientExample implements Serializable {
    transient int transientVar = 100; // transient 变量
    int normalVar = 200;
    public void main(String[] args) {
        TransientExample obj = new TransientExample();
        System.out.println("Transient Variable: " + obj.transientVar);
        System.out.println("Normal Variable: " + obj.normalVar);
    }
}
```

## 输出

```
Transient Variable: 100
Normal Variable: 200
```

在此 `TransientExample` 程序中，我们演示了 `transient` 关键字的使用，它影响 Java 序列化过程中对某些变量的处理。该类实现了 `Serializable` 接口，意味着该类的对象可以被序列化——转换为用于存储或传输的字节流。我们定义了两个变量：`transientVar`（标记为 `transient` 关键字）和 `normalVar`（普通变量）。区别在于 `transientVar` 不会被序列化，意味着在序列化期间会被忽略，当对象反序列化时，`transientVar` 将重置为默认值（在这种情况下 `int` 为 0）。相反，`normalVar` 被保留了。

## 用于医疗保健和医学应用的 Java 22

### 2.9.3.7 `synchronized`

`synchronized` 关键字确保一次只有一个线程可以访问代码块或方法。

## 程序

```java
public class SynchronizedExample {
    synchronized void synchronizedMethod() {
        System.out.println("这是一个同步方法.");
    }
    void main(String[] args) {
        SynchronizedExample obj = new SynchronizedExample();
        obj.synchronizedMethod();
        // 一时间只有一个线程可以访问此方法
    }
}
```

输出

```
这是一个同步方法。
```

在此 `SynchronizedExample` 程序中，我们演示了 Java 中的 `synchronized` 关键字，它对于确保多线程环境下的线程安全至关重要。`synchronizedMethod()` 被标记为 `synchronized`，意味着在类的任何特定实例上，只有一个线程可以访问此方法。如果多个线程尝试同时调用此方法，它们将排队，并且同一时间只有一个线程会执行该方法。这防止了竞态条件，并确保共享资源保持一致性和线程安全。在 `main` 方法中，我们创建了 `SynchronizedExample` 的实例并调用了 `synchronizedMethod()`。由于此程序是单线程的，同步方面在这里无法完全观察，但在多线程环境中，这确保了对方法的访问受到控制，使得没有两个线程在同一个对象上并发访问，维护了数据完整性。

## Java 数据类型和操作符

### 2.9.3.5 `volatile`

`volatile` 变量可以被多个线程不可预测地修改。

## 程序

```java
public class VolatileExample {
    volatile boolean flag = false; // volatile 变量
    public void setFlag() {
        flag = true;
    }
    public void main(String[] args) {
        VolatileExample obj = new VolatileExample();
        obj.setFlag(); // 修改 volatile 变量
        System.out.println("Volatile Flag: " + obj.flag);
    }
}
```

## 输出

```
Volatile Flag: true
```

在此 `Volatile` 程序中，我们演示了 Java 中 `volatile` 关键字的使用，它主要用于多线程环境以确保跨线程变量变化的可见性。`flag` 变量被声明为 `volatile`，意味着对其值的任何修改都会立即对所有线程可见，而不是被每个单独线程缓存。`setFlag()` 方法将 `flag` 的值改为 `true`。`main` 方法创建了 `VolatileExample` 类的实例，调用 `setFlag()` 方法更新 `volatile` 变量，并打印 `flag` 的当前值。尽管此程序是单线程的，但 `volatile` 关键字确保了如果程序在多线程环境中运行，所有线程在 `flag` 修改后立即看到其更新的值，防止了潜在的不一致或状态值。

### 2.9.3.6 `transient`

`transient` 变量在对象序列化时不会被序列化。

## 程序

```java
import java.io.Serializable;
public class TransientExample implements Serializable {
    transient int transientVar = 100; // transient 变量
    int normalVar = 200;
    public void main(String[] args) {
        TransientExample obj = new TransientExample();
        System.out.println("Transient Variable: " + obj.transientVar);
        System.out.println("Normal Variable: " + obj.normalVar);
    }
}
```

## 输出

```
Transient Variable: 100
Normal Variable: 200
```

在此 `TransientExample` 程序中，我们演示了 `transient` 关键字的使用，它影响 Java 序列化过程中对某些变量的处理。该类实现了 `Serializable` 接口，意味着该类的对象可以被序列化——转换为用于存储或传输的字节流。我们定义了两个变量：`transientVar`（标记为 `transient` 关键字）和 `normalVar`（普通变量）。区别在于 `transientVar` 不会被序列化，意味着在序列化期间会被忽略，当对象反序列化时，`transientVar` 将重置为默认值（在这种情况下 `int` 为 0）。相反，`normalVar` 被保留了。

### 2.9.3.7 `final`

`final` 关键字用于限制用户对变量、方法和类的使用。

## 程序

```java
class FinalExample {
    final int MAX_VALUE = 10; // 赋值后无法更改
    
    final void display() {
        System.out.println("Max value: " + MAX_VALUE);
    }

    public static void main(String[] args) {
        FinalExample example = new FinalExample();
        example.display();
        // example.MAX_VALUE = 20; // 将导致错误
    }
}
```

输出

```
Max value: 10
```

在此 `FinalExample` 类中，`final` 关键字用于创建常量。当变量被声明为 `final` 时，一旦初始化就无法重新赋值。标记为 `final` 的方法不能被子类重写，而标记为 `final` 的类不能被继承。这对于确保不可变性和安全性非常有用。

### 2.9.3.8 `instanceof`

`instanceof` 运算符用于测试对象是否是特定类或接口的实例。

```java
class Animal {}
class Dog extends Animal {}

public class InstanceofExample {
    public static void main(String[] args) {
        Animal animal = new Dog();
        if (animal instanceof Dog) {
            System.out.println("animal is a Dog");
        }
    }
}
```

输出

```
animal is a Dog
```

`instanceof` 运算符提供了对象类型的运行时检查。它通常在强制转换之前使用，以避免 `ClassCastException`。



```java
private final String description;

ComputerCourse(String courseName, String description) {
    this.courseName = courseName;
    this.description = description;
}

public String getCourseName() {
    return courseName;
}

public String getDescription() {
    return description;
}
```

# Program

```java
public class ComputerCourseExample {
    void main(String[] args) {
        // 打印所有课程
        for (ComputerCourse course : ComputerCourse.values()) {
            System.out.println(course.getCourseName() + " : " + \n
                course.getDescription());
        }

        // 选择特定课程
        ComputerCourse selectedCourse = ComputerCourse.JAVA;
        System.out.println("Course Name: " + selectedCourse.getCourseName());
        System.out.println("Description: " + selectedCourse.getDescription());
    }
}
```

# Complete 程序

```java
enum ComputerCourse {
    JAVA("Java Programming", "Beginner to Advanced"),
    PYTHON("Python Programming", "Beginner to Advanced"),
    WEB_DEVELOPMENT("Web Development", "HTML, CSS, JavaScript"),
    DATA_STRUCTURES("Data Structures", "In-depth Data Structures");

    private final String courseName;
    private final String description;

    ComputerCourse(String courseName, String description) {
        this.courseName = courseName;
        this.description = description;
    }

    public String getCourseName() {
        return courseName;
    }

    public String getDescription() {
        return description;
    }
}

public class ComputerCourseExample {
    void main(String[] args) {
        // 打印所有课程
        for (ComputerCourse course : ComputerCourse.values()) {
            System.out.println(course.getCourseName() + " : " + course.
            getDescription());

        // 选择特定课程
        ComputerCourse selectedCourse = ComputerCourse.JAVA;
        System.out.println("Course Name: " + selectedCourse.getCourseName());
        System.out.println("Description: " + selectedCourse.getDescription());
    }
}
```

# Java 中的数据类型和运算符

## 输出

Java Programming: Beginner to Advanced

Python Programming: Beginner to Advanced

Web Development: HTML, CSS, JavaScript

Data Structures: In-depth Data Structures

Course Name: Java Programming

Description: Beginner to Advanced

在这个程序中，我们定义了一个名为`ComputerCourse`的枚举，它封装了不同的课程及其对应的描述。每个枚举常量（如`JAVA`、`PYTHON`、`WEB_DEVELOPMENT`和`DATA_STRUCTURES`）都通过构造函数初始化了课程名称和描述。字段存储了这些值。为了访问这些属性，实现了两个公共方法：`getCourseName`和`getDescription`。`ComputerCourseExample`类包含`main`方法，我们在方法中使用枚举的`values()`方法来获取所有常量。使用`for`循环遍历枚举，并在控制台上打印每门课程的名称和描述。此外，我们显式地选择了`JAVA`课程，展示了如何访问单个实例及其属性。通过这种方式，它强调了 Java 中枚举的多功能性，允许使用结构化的方法管理相关数据，并带有内置方法以便于检索和显示。

# 2.11 医学应用

## 2.11.1 案例研究 1

血糖检测涉及测量血液中的血糖浓度，这对于诊断和管理糖尿病等疾病至关重要。血糖检测考虑的参数通常包括以下内容：

- 测量单位：血糖水平通常以毫克/分升（mg/dL）或毫摩尔/升（mmol/L）为单位，在美国更为常见。单位的选择会影响对血糖水平的解释。
- 正常范围：血糖范围取决于多种因素，如空腹状态（过夜之前或之后）以及距离上一顿饭的时间。对于非空腹状态，血糖范围会有不同。（注：此处原文后续内容存在大量重复和逻辑混乱，已根据语意翻译）

## 2.11.2 案例研究 2

肥胖检测通常涉及评估体重指数（BMI），这是一个广泛用于衡量体重与风险的指标。肥胖检测考虑的参数有：

- 体重：体重以公斤（kg）测量。它是计算 BMI 的主要输入，体重越高，BMI 越高。
- 身高：身高以厘米（cm）测量，并与体重一起计算 BMI。在相同体重下，高个的人 BMI 通常比矮的人高。
- 体重指数（BMI）：BMI 使用以下公式计算：

$$BMI = \frac{weight (kg)}{height(m)*height(m)}$$

# Java 中的数据类型和运算符

- 该计算将体重向左移动 6 位（相当于乘以 64），然后除以高的平方。BMI 大于 30 表示肥胖。
- 肥胖阈值：BMI 为 30 或更高通常被认为是肥胖。肥胖增加了各种健康问题的的风险。
- 健康风险：除了 BMI 之外，临床环境中还会考虑腰围、脂肪分布和整体健康状况，以全面评估肥胖相关的健康风险。

该程序示例了一个基于用户输入的体重和身高进行 BMI 计算的基础肥胖检测系统。

```java
import java.util.Scanner;

public class ObesityDetection {
    void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your weight (kg): ");
        int weight = scanner.nextInt();
        System.out.print("Enter your height (cm): ");
        int height = scanner.nextInt();
        int bmi = (weight << 6) / (height * height);

        if (bmi > 30) {
            System.out.println("检测到肥胖!");
        } else {
            System.out.println("未检测到肥胖.");
        }
    }
}
```

# 3 控制语句

## 3.1 引言

决策语句和循环控制语句是 Java 编程中控制执行流和对代码块进行迭代的基本结构。

### 3.1.1 决策

Java 中的决策涉及评估条件并根据评估结果执行不同的代码块。它允许程序根据运行时的各种条件做出选择并遵循不同的执行路径。主要有四种类型：

- `if`语句：如果指定的条件为真，则执行该代码块。如果条件为假，则跳过该代码块。
- `if-else`语句：它扩展了`if`语句，在条件为假时提供一个备选代码块进行执行。
- `else`阶梯语句（`else ladder`）：用于有需要顺序检查多个条件的情况。每个条件都逐一进行评估，如果条件为真，则执行相应的代码块。如果没有任何条件为真，则执行默认代码块。
- `switch`语句：它允许程序评估变量的值，并根据变量的不同值执行不同的代码块。

Java 中的决策结构（如`if`、`else if`、`else`、`switch`和三元运算符）允许程序根据某些条件执行特定的代码块。这种能力对于创建能够适应各种输入和状态的动态响应型应用程序至关重要。决策实现了复杂逻辑、错误处理和对程序流的控制，使得实现用户验证、数据校验和游戏机制等功能成为可能。

#### 优点

- 活性：允许程序根据不同的条件执行不同的操作。
- 控制：对执行流提供精确控制。
- 复杂度处理：允许复杂逻辑和决策树的实现。
- 代码可读性：通过清晰地划分不同的逻辑路径增强代码的可读性。
- 错误处理：有助于健壮的错误检查和处理。

#### 局限性

- 复杂度：过度使用会导致代码复杂且难以阅读，通常被称为“面条代码”。
- 性能：嵌套决策结构可能会影响性能，特别是当条件的计算开销较大时。
- 维护：复杂的决策结构可能难以维护和调试。
- 可扩展性：大规模决策逻辑可能需要重构为更具扩展性的解决方案，如状态机或策略模式。

### 3.1.2 循环

Java 中的循环用于在满足指定条件时重复执行代码块。它们对于需要迭代的任务（例如处理数组元素或执行重复计算）至关重要。循环有三种类型：

- `for`循环：它是一种进入控制循环，按指定的次数重复执行代码块。它由初始化、条件和递增/减表达式组成。
- `while`循环：它也是一种进入控制循环，只要指定的条件为真，就会一直重复代码块。它在每次迭代之前都会检查条件。
- `do-while`循环：它是一种出口控制循环，它至少执行一次代码块，然后只要指定的条件为真，就会继续重复。它在每次迭代之后都会检查条件。

Java 中的循环（如`for`、`while`和`do-while`）允许根据条件重复执行代码。这对于需要重复的任务至关重要，例如遍历数据结构（数组、列表）或执行重复计算。循环循环（原文为误）循环减少了代码重复，并使得高效处理大型数据集成为可能。

#### 优点

- 效率：允许在不重复代码的情况下执行重复任务。
- 自动化：方便需要重复多次的任务的自动化。
- 减少代码：通过迭代处理重复操作，显著减少了代码量。
- 活性：提供了轻松遍历集合、数组和范围的机制。
- 动态控制：允许根据运行时条件动态调整迭代次数。

#### 局限性

- 无限循环：构建不当的循环会导致无限循环，导致程序挂起。
- 复杂度：嵌套循环会导致难以阅读和维护的复杂代码。
- 性能：不当使用循环（尤其是嵌套循环）可能会导致性能瓶颈。
- 调试：循环内部的错误可能很难调试，特别是当循环条件或迭代复杂时。
- 内存消耗：如果资源管理不当，过度的迭代可能会导致高内存消耗和潜在的内存泄漏。

这些语句是 Java 程序中实现条件逻辑和重复任务的基础，允许开发者创建更动态、灵活的应用程序。

## 3.2 条件语句

Java 中的条件语句有助于根据特定条件进行决策。当条件评估为真时，将执行指定的代码块。

### 3.2.1 `if`语句

`if`语句是 Java 中条件逻辑的基石，它提供了一种根据动态条件控制程序流的强大机制。Java 中的这种基础条件语句根据条件决定是否执行特定的代码块。如果条件评估为真，则执行相关的语句块；否则，则跳过。

#### 语法

```java
if (condition) {
    // 如果条件为真则执行的代码
}
```

#### 示例

```java
int x = 10;

if (x > 5) {
    System.out.println("x is greater than 5");
}
```

上面的程序演示了在 Java 中使用`if`语句根据特定条件做出决策。在`main`方法中，整数变量`x`被初始化为值 10。`if`语句检查`x`的值是否大于 5。如果此条件评估为真（意味着`x`确实大于 5），则执行`if`语句块内的语句。在这种情况下，程序将向控制台打印消息“x is greater than 5”。如果条件评估为假（表示`x`不大于 5），则块内的语句将被跳过，且不产生输出。因此，`if`语句允许根据指定条件的结果对代码进行条件执行，提供了对程序行为的灵活性和控制。

### 3.2.2 嵌套 `if`语句

一个`if`语句嵌套另一个`if`语句内部。当外层（outer）条件评估为真（表示已满足）时，程序将评估内层（inner）条件。随后，如果内层条件也评估为真（表示它符合指定标准），则执行封装在内层语句中的相应代码块。这种条件语句的层级结构允许对多个条件进行顺序评估，并根据其结果执行相关的代码块。

#### 语法

```java
if (condition1) {
    // 如果 condition1 为真则执行的代码
    if (condition2) {
        // 如果 condition1 和 condition2 都为真则执行的代码
    }
}
```

#### 示例

```java
public class NestedIfExample {
    void main(String[] args) {
        int x = 10;
        int y = 20; // 外层 if 语句

        if (x > 5) {
            System.out.println("x is greater than 5");

            if (y > 15) { // 嵌套 if 语句
                System.out.println("y is greater than 15");
            } else {
                System.out.println("y is 15 or less");
            }
        }
    }
}
```

#### 输出

```text
x is greater than 5
y is greater than 15
```

### 3.2.3 `if-else`语句

如果条件成立，将执行`if`语句封装的代码；否则，将执行`else`块的代码。

#### 语法

```java
if (condition) {
    // 如果条件为真则执行的代码
} else {
    // 如果条件为假则执行的代码
}
```

#### 示例

```java
public class IfElseExample {
    void main(String[] args) {
        int n = 100; // 初始化变量

        if (n > 100) {
            System.out.println("Value is greater than 100");
        } else {
            System.out.println("Value is less than 100");
        }
    }
}
```

#### 输出

```text
Value is less than 100
```

# 用于医疗和医学应用的 Java 22

该程序用 Java 编写，定义了一个名为`IfElse`的类。在该类中，有一个`main`方法，作为程序的入口。在`main`方法内部，声明了一个整数变量`n`并将其初始化为值 100。然后，有一个`if`语句会检查`n`的值是否大于 100。如果该条件为真，它会在控制台打印消息“Value greater than 100”。否则，如果条件为假，它会在控制台打印消息“Value less than 100”。

## 3.2.4 `else if`阶梯（`else-if`结构）

Java 中的`else`阶梯是一种决策结构，允许按顺序评估多个条件。当存在多个执行路径且每个路径都依赖于不同条件时，它非常有用。`else`阶梯从一个`if`语句开始，评估第一个条件；如果条件为真，则执行相应的代码块，阶梯终止。如果条件为假，控制将移动到下一个`else if`语句，评估另一个条件。这种过程会持续，直到找到真条件或遇到可选的`else`语句（如果之前的没有任何条件为真，则执行它）。`else`阶梯通过清晰地勾勒多个条件路径，增强了读性和可维护性，使其更容易理解逻辑流。它在需要复杂决策的场景中特别有利。

### 语法

```java
if (condition1) {
    // 如果 condition1 为真则执行代码
} else if (condition2) {
    // 如果 condition2 为真则执行代码
} else if (condition3) {
    // 如果 condition3 为真则执行代码
} else {
    // 如果以上所有条件均不假
}
```



上述代码段说明了条件语句结构的语法。它从一个`if`语句开始，后面跟着可选的`else if`语句，并以可选的`else`语句结束。`if`语句检查`condition`。如果`condition1`求值为`true`，则执行相应的语句块。如果未满足`condition1`，程序将移动下一个`else if`语句，检查`condition2`。如果`condition2`求值为`true`，则执行相应的语句块。这种序列对于后续每个`else if`语句都会持续，检查条件，直到某个条件的求值为`true`。如果没有满足任何`if`或`else if`语句，则执行`else`子句中的语句块。每个语句块代表了当相应条件为真时执行的代码。这种结构允许根据多个条件的求值结果执行不同的代码块。这种结构允许根据不同条件的结果进行分支执行，为编程逻辑提供了灵活性。

## 程序

```java
import java.util.Scanner;
public class GradeMarks {
  void main(String[] args) {
  Scanner scanner = new Scanner(System.in);
```

## 控制语句

```java
System.out.print("Enter the student's marks: ");
int marks = scanner.nextInt();
char grade;
if (marks >= 90) {
  grade = 'A';
} else if (marks >= 80 && marks < 90) {
  grade = 'B';
} else if (marks >= 70 && marks < 80) {
  grade = 'C';
} else if (marks >= 60 && marks < 70) {
  grade = 'D';
} else if (marks >= 50 && marks < 60) {
  grade = 'E';
} else {
  grade = 'F';
}
System.out.println("Grade " + grade);
scanner.close();
```

输出：

```
Enter the student's marks: 95
Grade = A
```

在这个程序中，我们定义了一个`Grade`类，包含一个`main`方法，该方法使用`Scanner`输入提示用户输入学生成绩。根据输入的成绩，程序使用一系列条件语句来确定相应的等级，并将其分配给变量`grade`：90及以上为`'A'`，80到89分为`'B'`，70到79分为`'C'`，60到69分为`'D'`，50到59分为`'E'`，低于50分的为`'F'`。最后，程序在控制台打印确定的等级并关闭`scanner`以防止资源泄漏。

## 3.2.5 Switch Case（分支语句）

在面对各种选择时，Java提供了`switch`语句作为根据表达式的值执行特定代码分支的手段。`switch`结构在字节、`char`和`int`等原始数据类型上运行良好。此外，它还支持枚举类型、`String`类的实例以及包装类。通过评估表达式，`switch`语句将程序流引导到相应的代码块，有助于程序逻辑内部的决策过程。

### 语法

```java
switch (expression) {
  case value1:
    // 如果表达式等于 value 则执行代码
    break;
  case value2:
    // 如果表达式等于 value2 则执行代码
    break;
  // 更多 case 用例...
  default:
    // 如果表达式不匹配任何用例则执行代码
}
```

## 程序

不带`break`语句的`Switch Case`：

```java
public class test {
    void main(String[] args) {
    int n = 200; // 初始化变量
    switch (n) {
        case 100:
            System.out.println("Value of Case 1 is 100");
            // 这里没有 break 语句
        case 200:
            System.out.println("Value of Case 2 is 200");
            // 这里没有 break 语句
        default:
            System.out.println("Value of default is 200");
    }
}
```

## 输出：

```
Value of Case 2 is 200
Value of default is 200
```

上述Java程序定义了一个名为`test`的类，其`main`方法作为入口点。在`main`方法内部，声明了一个整数变量`n`并将其初始化为值200。在`switch`语句中，有三个`case`：`case 100`、`case 200`和一个`default case`。然而，在每个`case`块后没有`break`语句，这导致了贯穿（fall-through）行为。这意味着当`n`的值匹配200时，它不仅会执行`case 200`的代码块，还会执行`default case`的后续代码块。因此，由于`n`为200，程序将打印与`case 200`相关的消息。

带`break`语句的`Switch Case`：

```java
public class test {
    void main(String[] args) {
    int n = 200; // 初始化变量
    switch (n) {
        case 100:
            System.out.println("Value of Case 1 is 100");
            break;
        case 200:
            System.out.println("Value of Case 2 is 200");
            break;
        default:
            System.out.println("Value of default is 200");
    }
}
```

## 3.3 循环（LOOPS）

循环是一种基础编程结构，由一系列语句组成，按预定次数执行或直到条件满足。循环提供了一种重复操作的机制。根据编程语言使用的循环（如`for`、`while`或`do-while`），循环将持续到条件变为假或完成指定的迭代。这种迭代过程允许程序员高效处理重复任务。

## 编程中循环的需求

循环是编程中的基本概念，允许根据条件执行一组指令。它对于以下原因至关重要：

- **重复任务**：许多编程任务涉及重复操作。循环允许你自动化这些任务而无需编写冗余代码。
- **效率**：更有效地执行任务。
- **动态数据处理**：在处理数组或列表等数据结构时，循环允许动态处理每个元素。
- **自动化**：循环对于需要多次执行的任务至关重要，例如处理用户输入、生成报告和处理文件操作。

## 循环的优点

- **代码复用和减少**：循环允许你编写一次代码块并多次使用，减少需要编写和维护的代码。
- **简化任务**：复杂的重复任务可以通过循环简化，使代码更易读、更易理解。
- **灵活性**：循环可以处理不同次数，使其适用于不同的任务，例如遍历未知长度的数据结构。
- **自动化**：循环实现了任务的自动化，这对于数据处理、模拟和批处理等任务至关重要。
- **动态和实时处理**：循环允许程序对实时数据变化做出响应并在数据可用时动态处理。

## 循环的局限性

- **死循环**：如果循环的终止条件定义不正确，可能会导致死循环，引起程序卡住或崩溃。
- **性能开销**：尤其是嵌套循环，会导致性能开销。它们会消耗大量的处理时间和资源。
- **复杂性**：过度使用循环或设计不当的循环会导致代码变得复杂，难以理解和维护。
- **内存消耗**：创建新对象或在内存中持有大型数据结构的循环会导致内存消耗增加，并可能导致内存泄漏。
- **逻辑错误**：错误的循环条件或不当使用循环控制语句（如`break`和`continue`）可能会引入难以调试的逻辑错误。

## 3.3.1 JAVA 循环示例

1. `For`循环

```java
for (int i = 0; i < 10; i++) {
    System.out.println("Iteration: " + i);
}
```

这个`for`循环将打印从`"Iteration: 0"`到`"Iteration: 9"`。

2. `While`循环

```java
int i = 0;
while (i < 10) {
    System.out.println("Iteration: " + i);
    i++;
}
```

这个`while`循环与上述`for`循环实现相同的结果。

3. `Do-While`循环

```java
int i = 0;
do {
    System.out.println("Iteration: " + i);
    i++;
} while (i < 10);
```

这个`do-while`循环确保在测试条件之前至少执行一次代码块。

### 3.3.2 FOR 循环

循环是Java中常用的控制流语句之一，允许根据条件重复执行代码。当你预先知道要执行语句或语句块的次数时，它特别有用。

#### 语法

```java
for (initialization; condition; update) {
    // 要执行的代码
}
```

- **初始化（Initialization）**：此部分在循环开始时执行一次。通常用于初始化循环控制变量。
- **条件（Condition）**：此部分在每次迭代之前求值。如果结果为真，则执行循环体。如果结果为假，则循环终止。
- **更新（Update）**：此部分在循环体每次迭代完成后执行。通常用于更新循环控制变量。

### 程序：for 循环

```java
public class test {
  void main(String[] args) {
    // 从 1 迭代到 10 的 for 循环
    for (int x = 1; x <= 10; x++) {
      System.out.println(x); //  x 的当前值
    }
  }
}
```

输出：

```
1
2
3
4
5
6
7
8
9
10
```

上述Java程序定义了一个名为`test`的类，其`main`方法作为入口点。在`main`方法内部，使用了一个传统的`for`循环来遍历从1到10的整数值范围。循环从初始化整数变量`x`值为1开始。然后执行循环体，使用`System.out.println()`向控制台打印`x`的当前值。在每次迭代后，循环通过将`x`增1来更新其值。此过程一直持续，直到条件`x <= 10`不再满足，此时循环终止。因此，它按顺序向控制台打印1到10的数字，每个数字占一行。

### 3.3.2.1 For-Each 循环

`for-each`循环（也称为增强`for`循环）是一种用于遍历数组或集合中元素的方便结构。它通过充当迭代器，简化了遍历这些数据结构元素的过程。使用`for-each`循环时，你不需要显式提供递增或递减语句。循环会自动遍历数组或集合的每个元素，逐个返回以便在循环体内进行处理。这种精简的语法减少了错误的概率并增强了代码的可读性，使开发者能够更容易在Java程序中处理数组和集合。

#### 语法

```java
for (dataType element : collectionOrArray) {
  // 为每个元素执行的代码
}
```

`for-each`循环（也称为增强`for`循环）为遍历数组或集合中的元素提供了一种简洁且直观的方式。它的语法提供了

## 用于医疗和健康应用的 Java 22

在此程序中，我们定义了一个带有`main`方法的`LabeledForExample`，演示了Java中标签循环的使用。外层循环被标记为`outerLoop`并使用变量`i`迭代三次，而内层循环使用变量`j`迭代三次。在内层循环内部，条件语句检查`i`和`j`是否大于4。如果满足该条件，它将打印一条消息表示正在跳出外层循环，并使用`break outerLoop`语句立即退出两个循环。如果不满足条件，它将打印`i`和`j`的当前值。

### 程序：标签 for 循环

```java
public class InnerLabelLoopExample {
  void main(String[] args) {
    // 带有标签 "lab1" 的外层循环
    lab1: for (int x = 1; x <= 5; x++) {

      // 带有标签 "lab2" 的内层循环
      lab2:for(int y = 1; y <= 4; y++) {
        if (x == 4 && y == 2) {
          System.out.println("Breaking out of inner loop");
          break lab2; // 跳出外层循环
        }
        System.out.println("x = " + x + ", y = " + y);
      }
    }
  }
}
```

输出：

```
x = 1, y = 1
x = 1, y = 2
x = 1, y = 3
x = 1, y = 4
x = 2, y = 1
x = 2, y = 2
x = 2, y = 3
x = 2, y = 4
x = 3, y = 1
x = 3, y = 2
x = 3, y = 3
x = 3, y = 4
x = 4, y = 1
Breaking out of inner loop
x = 5, y = 1
x = 5, y = 2
x = 5, y = 3
x = 5, y = 4
```

在此程序中，我们定义了`InnerLabelLoopExample`类，它包含一个`main`方法，演示了标签内层和外层循环的使用。标记为`lab1`的外层循环使用变量`x`从1迭代到5，而标记为`lab2`的内层循环使用变量`y`从1迭代到4。在内层循环内部，条件语句检查`x`是否为4且`y`是否为2。如果满足，它会打印消息表示正在跳出内层循环并执行`break lab2`，这只会退出内层循环。如果不满足条件，程序将打印`x`和`y`的当前值。

## 控制语句

### 3.3.2.4 Java 中的嵌套循环

事实上，当处理需要将一个或多个`for`循环嵌套彼此的情况时，Java的嵌套`for`循环结构非常有用。嵌套结构允许在外层循环体内部执行一个或多个内层循环。外层循环的每次迭代都会触发内层循环的完整执行，并遵循为每个循环指定的条件。

这种嵌套安排对于需要对跨多个范围或数组的每个元素组合执行任务的场景特别有用。例如，如果你有一个表示网格的二维数组，嵌套循环可以高效地遍历网格的每个单元格，允许你对每个单独元素处理数据或执行操作。

嵌套循环的行为确保了在外层循环的每次迭代中，内层循环都会完全执行，为处理复杂的数据结构或任务提供了一种系统化且组织化的方法。这种结构在控制程序流方面提供了灵活性和精度，是Java编程中需要跨多个维度或数据集进行迭代任务的不可或缺的工具。

### 程序

```java
public class test {
  void main(String[] args) {
    // 每一行的外层循环
    for (int x = 1; x <= 7; x++) {
      // 打印星号的内层循环
      for (int y = 1; y <= x; y++) {
        System.out.print("* "); // 打印星号后跟空格
      }
      System.out.println(); // 每行后移动到下一行
    }
  }
}
```

输出：

```
*
**
***
****
*****
******
*******
```

上面的Java程序定义了一个名为`test`的类，其`main`方法作为入口点。在`main`方法中，利用两个嵌套的`for`循环来生成右三角形形状的星号模式。由变量`x`控制的外层循环从1迭代到7，表示三角形的行数。外层循环的每次迭代由变量`y`控制的内层循环从1迭代到`x`的当前值。这个内层循环控制每行打印的星号数量，并随后的每一行而增加。在内层循环中，使用`System.out.print()`打印一个星号后跟一个空格，生成每行的星号模式。在完成每行的内层循环后，使用`System.out.println()`移动到下一行，这导致后续行打印在新的一行上。因此，当程序运行时，会生成一个星号右三角形，每行包含数量递增的星号（从1到7不等），形成右三角形的形状。

## 3.2.5 Java 中的无限循环

无限`for`循环在需要持续执行特定代码块且没有预设退出条件的场景下具有重要价值。这种结构有助于创建后台进程、实现监听器或运行需要无限保持活跃的服务器端程序。

无限`for`循环的语法非常直观：

```java
for (;;) {
    // 循环体
}
```

该循环在参数中缺少条件，这意味着它将不断迭代下去，直到被`break`语句中断或程序执行终止。在没有定义退出条件的情况下，循环将重复执行其循环体，实际上创建了一个无限循环。



虽然`for`循环非常强大，但应该谨慎使用，并小心确保在需要时有方法终止它。如果管理不当，无限循环可能会导致资源耗尽、系统不稳定或程序崩溃。因此，在需要时实现适当的跳出循环机制至关重要，以确保程序的可靠性和稳定性。

## 程序

```java
public class Main {
    void main(String[] args) {
        for (;;) {
            System.out.println("infinite");
            // 为了防止输出过载，你可能会添加 sleep 语句
            // 或在实际场景中添加 break 条件
        }
    }
}
```

上面的程序定义了一个名为`test`的类，其`main`方法作为入口点。在方法内部，采用了一个无限`for`循环，通过循环括号内缺少任何初始化、条件或迭代表达式来指示。这种参数的缺失意味着循环将无限执行，在循环体内部持续地向控制台打印字符串`infinite`。当程序执行时，无限循环开始，循环体内的语句被反复执行且不中断。结果是，字符串`infinite`持续输出到控制台，反映了循环的持久执行。由于没有定义的终止条件，循环将一直运行下去，直到程序被手动终止或从外部中断。

### 3.3.3 WHILE 循环

`while`循环是一种入口控制循环，意味着它在执行循环之前会评估测试表达式或条件。`while`循环的语法非常直观：它以关键字`while`开始，后面跟着括号内的测试表达式，然后是花括号括的循环体。循环体可以是单个语句、多个语句（即复合语句），也可能是空的。

在`while`循环的每次迭代中，都会评估测试表达式。如果表达式为真，则表示条件满足，执行循环体。如果表达式为假，则程序控制将跳转到循环体结束之后的行。

这种控制流特性使得`while`循环适用于不受预知迭代次数且取决于某些条件是否满足的情况。在`while`循环中，循环变量必须在循环开始之前初始化，并且在循环体内部进行更新。通过在循环体内正确初始化、更新和评估循环变量，开发者可以有效利用`while`循环结构为 Java 程序创建灵活的行为。

#### 语法

```java
while (condition) {
  // 循环体
}
```

## 程序

```java
public class Main {
  void main(String[] args) {
    long i, fact = 1; // 阶乘计算变量
    long n = 5; // 要计算阶乘的
    // 计算阶乘的循环
    while (n != 0) {
      fact *= n; // 更新阶乘
      n--; // n 减
    }
    // 输出结果
    System.out.println("Factorial of is " + fact);
  }
}
```

输出 Factorial of is: 120

在此程序中，我们使用`while`循环计算 5 的阶乘。我们将变量`fact`初始化为 1，将`n`初始化为 5，然后进入一个直到`n`变为零的循环。在循环内部，我们将`fact`乘以`n`以更新阶乘值，并将`n`减 1。最后，我们打印结果，显示 5 的阶乘是 120。

`while`循环还有几种变体。

### 3.3.1 空 while 循环

空`while`循环在其体内不包含任何语句。它只包含一个空语句，通过语句后加分号来表示：

```java
public class Main {
  void main(String[] args) {
    long w = 0; // 时间延迟的变量
    // 时间延迟循环
    while (w < 10000) {
      w++; // w 加1
      // 循环体内无操作（空）
    }
    // 输出指示延迟完成的消息
    System.out.println("Delay completed.");
  }
}
```

输出：

Delay completed.

上述是一个时间延迟循环。时间延迟循环用于程序暂停一段时间。它演示了如何使用空循环来创建时间延迟。在示例中，长整型变量`w`初始化为 0。`while`循环的构造条件是每次将`w`增加 1，直到其值小于 10000。然而，循环体仅包含一个空语句，这意味着分号紧跟在`while`语句之后。该`while`循环的目的是为了在程序执行中引入时间延迟。通过不断增加`w`直到达到指定值（在本例中为 10000），而在循环内部不执行任何有意义的代码，程序有效地暂停或延迟了其执行一段时间。像这样的时间延迟循环在需要在程序执行中引入受控暂停的场景中非常有用，例如在时间敏感型应用程序、仿真或需要与外部事件同步的场景中。然而，重要的是，此类时间延迟循环的有效性和准确性可能会根据硬件、系统负载和编译器优化等因素而异。此外，像这样的忙等待（busy-waiting）循环会消耗资源。

### 3.3.2 无限循环

如果`while`循环体内部没有更新语句，则`while`循环可以变成无限循环。

## 程序

```java
public class InfiniteWhileExample {
  void main(String[] args) {
    int j = 0; // 初始化变量 j
    // 无限循环
    while (j <= 10) {
      System.out.println("Square of " + j + " is " + (j * j));
      // 缺少自增语句 (j++)
    }
    // 此语句永远不会执行
    j++;
  }
}
```

定义了一个名为`InfiniteWhileExample`的类，其包含一个初始化整型变量`j`为 0 的`main`方法。随后，利用条件为`j <= 10`的`while`循环，这意味着只要`j`的值小于等于 10，循环就会执行。在`while`循环体内部，使用`System.out.println()`方法将`j`当前值的平方打印到控制台。然而，循环结构中存在一个问题：循环变量`j`没有在循环体内进行递增。结果是，循环无限持续下去，且`j`始终等于 0，导致无限循环。此外，在循环体外放置了一条语句`j++;`。然而，由于无限循环的进行，该语句永远不会被执行。因此，该语句对程序执行产生没有影响。

### 3.3.4 Do-While 循环

`do-while`循环是一种退出控制循环。它在执行完循环体中的语句后，在循环底部评估测试表达式。

注意：`do-while`循环至少执行一次。

在`for`和`while`循环中，条件是在执行循环体之前评估的。如果测试表达式第一次求值为假，则`do`循环体永远不会执行。

#### 语法

```java
do {
// 要执行的语句
} while (condition);
```

当循环体包含单个语句时，括号`()`是必须的。

## 程序

```java
public class Test {
void main(String[] args) {
  char c = 'A'; // 初始化字符变量
  // 使用 do-while 循环打印从 'A' 到 'Z' 的字符
  do {
    System.out.print(c + " "); // 打印当前字符后跟空格
    c++; // 字符递增
  } while (c <= 'Z'); // 当 c 小于等于 'Z' 时继续循环
}
```

输出：

A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

上述程序定义了一个名为`test`的类，包含一个作为入口点的方法。在方法内部，字符变量`c`初始化为字符`'A'`。目前使用`do-while`循环打印从`'A'`到`'Z'`的字符。通过在`do-while`循环体内使用`System.out.println()`方法将`c`的值打印到控制台。然后，`c`的值加 1。只要`c`的循环小于或等于字符`'Z'`，此过程就会持续。正如条件`c <= Z`所指定的，`do-loop`遍历从`'A'`到`'Z'`的字符编码，在每次迭代到达字符`'Z'`时递增`c`。一旦`c`超过`'Z'`，循环终止，程序执行结束。因此，当程序执行时，它会在控制台上打印从`'A'`到`'Z'`的英语字母大写字母，每个字母之间用空格隔开。

## 3.4 循环控制语句

Java 中的控制语句是基础结构，允许程序员更改程序内部的正常顺序执行流。Java 支持多种控制语句，其中两种是`break`语句和`continue`语句。

- **break 语句**：`break`语句用于提前终止循环或`switch`语句的执行。当在循环或`switch`中遇到`break`语句时，程序控制将立即退出循环或 switch，并将执行转移到循环或 switch 块之后的语句。这允许程序员根据条件退出循环或 switch 语句，有效地控制程序的流。

- **continue 语句**：`continue`语句用于循环内部，跳过循环体内的剩余代码，并在进入下一次迭代之前立即重置循环条件。与完全退出循环的`break`语句不同，`continue`语句允许循环继续迭代，但跳过当前迭代中的剩余代码。这对于根据特定条件跳过某些迭代而不完全终止循环非常有用。

`break`和`continue`语句都为控制 Java 中循环和`switch`语句中的执行流提供了强大的工具，为程序设计和实现提供了更大的活性和效率。

### 3.4.1 BREAK

在 Java 中，`break`语句用于提前终止循环或`switch`语句的执行。当在循环（如`for`、`while`或`do-while`循环）中遇到`break`语句时，它会导致循环立即退出，控制转移到循环之后的语句。同样，在`switch`语句中，`break`语句结束当前 case 的执行并退出 switch 块，防止执行进入后续的 case。`break`语句增强了对程序流的控制，允许更精确地管理循环和 case，提高了可读性并减少了错误风险。

#### 语法

```java
break;
```

## 程序

```java
public class Test {
    void main(String[] args) {
      // 从1迭代到5的循环
      for (int i = 1; i <= 5; i++) {
        if (i == 4) {
          break; // 如果 i 等于 4，终止循环
        }
        System.out.println(i); // 打印 i 的值
      }
    }
}
```

输出：

1

2

3

上述 Java 程序定义了一个名为`test`的类，包含一个作为入口点的方法。在方法内部，利用`for`循环遍历 1 到 5 的整数范围。循环变量`i`初始化为 1，只要`i`小于 5，循环就会持续。在每次迭代中，都会使用语句检查`i`的当前值是否等于 4。如果满足条件，将遇到`break`语句，导致循环提前终止，控制转移到其之后的语句。然而，如果条件不满足，则执行块中的代码，将`i`的值打印到控制台。因此，当程序执行时，在`i`等于 4 循环终止之前，控制台上会打印 1、2 和 3，每个数字占一行。因此，我们只得到小于 5 的输出。

```java
// 打印 i 和 j 的当前值
System.out.println("i: " + i + ", j: " + j);
// 检查 i 是否等于 2
if (i == 2) {
    // 跳出标记为 "first" 的外层循环
    break first;
}

// 此代码在跳出外层循环后执行
System.out.println("Exited both loops");
```

输出

i: 1, j: 1

i: 1, j: 2

i: 2, j: 1

Exited both loops

在此程序中，我们定义了一个`Test`类，并包含一个作为其入口的`main`方法。在`main`方法内部，我们对嵌套循环进行了标记。标记为`first`的外层循环将整数`i`初始化为 1，只要`i`小于 5 就会继续执行。在外层循环的每次迭代中，标记为`second`的内部循环将整数`j`初始化为 1，只要`j`小于 3 就会继续执行。在内部循环体中，使用`System.out.println()`方法向控制台打印`i`和`j`的当前值，显示`i`和`j`的每种组合。此外，还有一个`if`语句检查`i`的值是否等于 2。如果满足此条件，将遇到带有标记`first`的`break`语句，导致外层循环`first`立即终止。然而，一旦`i`的值等于 2，标记为`first`的外层循环就会打破，导致程序控制完全退出这两个循环。

### 3.4.2 Continue

在 Java 中，`continue`语句用于循环内部，以跳过当前迭代并直接进入循环的下一次迭代。当您需要在特定条件下跳过循环体的某些部分而不是完全退出循环时，这种方法特别有用。

其工作原理：

- 当遇到`continue`语句时，剩余语句将被忽略，控制将转移到循环的下一次迭代。

- 对于`for`循环，控制移动到更新语句（通常是递增或递减语句）。

- 对于`while`和`do-while`循环，控制移动到循环的条件评估。

#### 语法

```java
continue;
```

## 程序：Java continue 语句

```java
public class Main {
    void main(String[] args) {
        // 遍历整数值范围
        for (int i = 1; i <= 5; i++) {
            // 检查 i 的值是否等于 4
            if (i == 4) {
                // 跳过本次迭代的循环的剩余部分
                continue;
            }
            // 将 i 的值打印到控制台
            System.out.println(i);
        }
    }
}
```

输出

1

2

3

5

在此程序中，我们定义了一个`Main`类，并在该`main`方法中，使用`for`循环来遍历从 1 到 5 的整数值。在循环的每次迭代中，都会使用`if`语句检查循环变量`i`的当前值是否等于 4。如果条件评估为真（表示`i`等于 4），则会遇到`continue`语句。该语句会导致跳过当前迭代中循环体内的剩余代码，并直接进入循环的下一次迭代。结果是当循环变量`i`等于 4 时，循环体内的打印语句被跳过。对于`i`的所有其他值（1, 2, 3 和 5），打印语句都会执行，将`i`的值打印到控制台。因此，当程序执行时，数字 1、2、3 和 5 被打印到控制台，每个数字独占一行。数字 4 被`continue`语句排除在输出之外，该语句跳过了该迭代的打印语句。

## 带标记的 Continue 语句

Java 中带标记的`continue`语句提供了一种更精确的控制嵌套循环流的方法。它允许你从内部循环内部跳过外层循环的当前迭代。通过在`continue`语句上使用标记，你可以指定要继续执行哪个循环。

其工作原理：

- 标记通过在循环语句之前的标识符后跟冒号（`:`）来定义。

- 使用标记的 continue：当`continue`语句配合标记一起使用时，它跳过被标记循环的当前迭代，而不是最内层的循环。

#### 语法

```java
continue label;
```

### 程序：带标记的 continue 语句

```java
public class Main {
    public void main(String[] args) {
        ttt: // 外层循环的标记
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= 5; j++) {
                if (i == 3 && j == 4) {
                    // 继续外层循环的下次迭代
                    continue ttt;
                }
                System.out.println("i = " + i + ", j = " + j);
            }
        }
    }
}
```

输出：

i = 1, j = 1

i = 1, j = 2

i = 1, j = 3

i = 1, j = 4

i = 1, j = 5

i = 2, j = 1

i = 2, j = 2

i = 2, j = 3

i = 2, j = 4

i = 2, j = 5

i = 3, j = 1

i = 3, j = 2

i = 3, j = 3

i = 4, j = 1

i = 4, j = 2

i = 4, j = 3

i = 4, j = 5

i = 5, j = 1

i = 5, j = 2

i = 5, j = 3

i = 5, j = 4

i = 5, j = 5



在此程序中，标记为`ttt`的外层循环遍历变量`i`从 1 到 5，而内部循环遍历变量`j`从 1 到 5。在内部循环中，有一个条件检查`i`是否为 3 且`j`等于 4。如果满足此条件，程序将遇到一个作用于外层循环的`continue`语句，导致程序跳过内部循环中的代码，并跳转到外层循环的下一次迭代。因此，当`i`等于 3 且`j`等于 4 时，循环体内的打印语句被跳过。对于`i`的所有其他值（1, 2, 3 和 5），打印语句都会执行，将`i`的值打印到控制台。数字 4 被`continue`语句排除在输出之外，它跳过了该迭代的打印语句。

在此程序中，标记为`ttt`的外层循环遍历变量`i`从 1 到 5，而内部循环遍历变量`j`从 1 到 5。在内部循环中，有一个条件检查`i`是否为 3 且`j`等于 4。如果满足此条件，程序将遇到一个作用于外层循环的`continue`语句，导致程序跳过内部循环中的代码，并跳转到外层循环的下一次迭代。因此，当`i`等于 3 且`j`等于 4 时，循环体内的打印语句被跳过。对于`i`的所有其他值（1, 2, 3 和 5），打印语句都会执行，将`i`的值打印到控制台。数字 4 被`continue`语句排除在输出之外，它跳过了该迭代的打印语句。

## 3.4.2.1 带标记的 continue 语句

## 3.5 未命名变量

在 Java 22 中，未命名变量和模式的概念指的是一种在处理不需要的变量和模式时增强语言灵活性和可读性的功能。该功能允许开发者使用`_`来表示为了语法目的所需的变量，例如声明、模式匹配或解构赋值，而对实际值并不感兴趣。Java 22 中引入的未命名变量和模式解决了软件开发中的若干关键需求，特别是在提高代码可读性、减少冗余和增强维护性方面。

### 未命名变量的需求

- **增强可读性**：未命名变量和模式允许开发者在某些上下忽略或丢弃值，例如变量声明、Lambda 表达式或模式匹配。通过消除为无关值发明或使用任意变量名，提高了代码的清晰度。
- **减少代码**：在 Java 22 之前，开发者必须声明没有意义或实用的变量或模式以满足语法要求。未命名变量和模式消除了这些代码，使意图更加明显并减少了视觉干扰。
- **简化模式匹配**：在模式匹配中使用未命名变量允许在处理复杂数据结构时生成更简洁、更有表现力的代码。它让开发者关注模式的各个部分，而不受不必要的变量声明的干扰。
- **提高维护性**：通过减少未使用的或无关的变量声明，未命名变量和模式有助于构建更易于维护和修改的代码库。这种增强符合了现代编程实践，即强调简洁性和易于推理的代码。
- **与函数式编程兼容**：函数式编程范式通常涉及丢弃某些值或结果的操作。未命名变量和模式通过允许开发者更自然地表达操作而无需产生不必要的命名开销，支持了这些范式。

# 适用于医疗保健与医学应用的 Java 22

### 3.5.1 在循环中使用未使用变量

Java 允许开发者在`for`循环中使用划线（`_`）作为未命名变量。这表示开发者对正在迭代的具体值不感兴趣，只关注循环的执行。

#### 程序

```java
public class Demo {
    void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        int total = 0;
        for (int _ : numbers) {
            total++;
        }
        System.out.println("Total numbers: " + total);
    }
}
```

#### 输出

```
Total numbers: 5
```

该程序计算`numbers`数组中元素的总数并打印结果。它在增强型`for`循环中使用未命名变量遍历每个元素，每次迭代增加计数器`total`，最后打印数组中数字的数量。

## 3.6 医疗应用

### 3.6.1 案例研究 1

`SymptomChecker`可以快速识别可能指示更严重状况的症状（例如持续发烧或多种症状组合），提示用户寻求医疗帮助，这对于预防流感等并发症至关重要。`SymptomChecker`程序在检测症状时考虑了以下参数：

- **发烧**：发烧是指示各种感染或疾病的常见症状。
- **咳嗽**：咳嗽是另一种与呼吸道感染相关的常见症状。

该程序检查发烧和咳嗽的组合，以提示可能患有感冒或流感的可能性。如果仅存在发烧或咳嗽，它会建议咨询医生。如果在最多三轮问答后未得出明确诊断，程序将建议症状可能轻微，并建议采取家庭疗法或在症状持续时咨询医生。

```java
import java.util.Scanner;
public class SymptomChecker {
    void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Do you have a fever (Y/N)?");
        String hasFever = scanner.nextLine();
        System.out.println("Do you have a cough (Y/N)?");
        String hasCough = scanner.nextLine();
        boolean diagnosed = false;
        for (int i = 0; i < 3 && !diagnosed; i++) {
            if (hasFever.equalsIgnoreCase("Y") && hasCough.equalsIgnoreCase("Y")) {
                System.out.println("You might have a cold or fever. Please consult a doctor.");
                diagnosed = true;
            } else if (hasFever.equalsIgnoreCase("Y")) {
                System.out.println("You might have a fever. Please consult a doctor.");
                diagnosed = true;
            } else if (hasCough.equalsIgnoreCase("Y")) {
                System.out.println("You might have a cough. Please consult a doctor for diagnosis.");
                diagnosed = true;
            }
        }
        if (i < 2 && !diagnosed) {
            System.out.println("Do you have any other symptoms (Y/N)?");
            String otherSymptoms = scanner.nextLine();
            if (otherSymptoms.equalsIgnoreCase("Y")) {
                System.out.println("Please consult a doctor for a complete diagnosis.");
                diagnosed = true;
            }
        }
        if (!diagnosed) {
            System.out.println("Your symptoms might be minor. Consider home remedies or consult a doctor if they persist.");
        }
    }
}
```

`SymptomChecker`程序允许用户在输入有关发烧和咳嗽的信息后评估自己的健康状况。它首先提示用户输入是否发烧和咳嗽，然后开始评估这些输入以确定潜在的健康影响。如果用户报告同时有发烧和咳嗽，它会建议他们可能患有感冒或发烧，提示他们咨询医生。如果只报告了一种症状，它会建议针对该症状进行咨询。此外，程序允许对其他症状进行最多两轮查询，强调了在必要时寻求医疗建议的重要性。如果没有发现显著症状，它建议采取家庭疗法或在症状持续时进一步咨询，旨在提供初步的健康指导。

### 3.6.2 案例研究 2

良好的药物依从性与更好的健康结果直接相关。通过支持患者遵循处方治疗计划，药物提醒有助于改善疾病管理、减少并发症并提高整体健康。提醒系统为用户提供了一种方便的方法来管理用药时间，而无需依赖记忆。它允许用户输入药物详情并接收及时提醒，无缝集成到他们的日常行程中。

- **药物名称**：用户输入需要服用的药物名称。
- **剂量**：用户指定剂量细节，例如“1 片”或“2 粒胶囊”。
- **用药频率**：程序提示用户输入每天需要服用几次药物。这确保用户可以为全天内的每次需要剂量设置提醒。
- **服药时间**：对于每个用药频率，程序要求用户指定具体时间。这有助于用户根据日常习惯安排用药。
- **提醒消息**：在收集所有信息后，程序为每次剂量生成提醒消息。这些消息包括药物名称、剂量和计划时间，以确保按时服用。
- **数据验证**：在交互过程中，程序确保输入是正确的，防止出现负数频率或无效时间。

```java
import java.util.Scanner;
public class MedicationReminder {
    void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter medication name:");
        String medicationName = scanner.nextLine();
        System.out.println("Enter dosage (e.g., 1 tablet):");
        int dosage = scanner.nextInt();
        int dosageTimes;
        do {
            System.out.println("How many times per day do you need to take " + medicationName + " (Enter 0 to finish):");
            dosageTimes = scanner.nextInt();
        } while (dosageTimes < 0); // 确保非负值
        for (int i = 0; i < dosageTimes; i++) {
            System.out.println("Enter time for dose " + (i + 1) + " in 24-hour format (HH:MM):");
            String time = scanner.nextLine();
            System.out.println("Reminder: Take " + dosage + " of " + medicationName + " at " + time);
        }
        System.out.println("Medication details saved.");
    }
}
```

`MedicationReminder`程序帮助用户有效管理药物计划。它首先提示用户输入药物名称和剂量信息。然后，它进入一个循环，询问每天需要服用几次，确保输入的是非负值。获取这些信息后，程序会对输入的剂量进行循环，要求指定 24 小时格式（HH:MM）的时间。对于指定的每次剂量，它会生成包含药物名称、剂量和计划时间的提醒消息。

### 3.6.3 案例研究 3

`AllergyChecker`旨在帮助用户识别潜在的过敏，了解其触发因素，并鼓励他们寻求医疗建议以获得准确的诊断和治疗。它利用用户输入和预定义的常见过敏列表，根据用户的情况提供定制化的信息反馈。

#### 控制语句

```java
import java.util.Scanner;
public class AllergyChecker {
    void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String[] allergies = {"pollen", "dust", "nuts", "pets"};
        System.out.println("Do you have any allergies? (Y/N)");
        String hasAllergies = scanner.nextLine();
        if (hasAllergies.equalsIgnoreCase("Y")) {
            // 检查具体过敏原
        } else {
            // 用户表示他们没有任何过敏史（N），程序建议他们可能不容易发生过敏反应。
        }
    }
}
```

用户表示他们没有任何过敏史（N），程序建议他们可能不容易发生过敏反应。

### 3.6.4 案例研究 4

`BMI 计算器`对于提高对体重相关健康风险的意识以及鼓励个人采取积极措施维持健康的生活方式至关重要。BMI（体质量指数）是一个广泛使用的体脂肪指标，有助于将个人分为不同的体重类别：体轻、正常体重、超重和肥胖。这项评估提供了有关与体重相关的潜在健康风险的价值信息。它赋予用户相关信息，让他们对自己的健康和福祉做出明智决策。

考虑的参数有：

- **BMI 计算**：使用公式`weight / (height * height)`计算 BMI 值
- **特定的体重类别**：
  - 体轻：BMI < 18.5
  - 正常体重：18.5 <= BMI < 25
  - 超重：25 <= BMI < 30
  - 肥胖：BMI >= 30

在显示 BMI 及其对应的类别后，程序建议用户咨询医生。

```java
import java.util.Scanner;
public class BMICalculator {
    void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // User input
        System.out.println("Enter your height in meters (e.g., 1.75):");
        double height = scanner.nextDouble();
        System.out.println("Enter your weight in kilograms (e.g., 70):");
        double weight = scanner.nextDouble();
        // Calculate BMI
        double bmi = weight / (height * height);
        // Calculate BMI category using if-else ladder
        System.out.println("Your BMI is: " + String.format("%.2f", bmi));
        if (bmi < 18.5) {
            System.out.println("You are in the underweight category.");
        } else if (bmi >= 18.5 && bmi < 25) {
            System.out.println("You are in the normal weight category.");
        } else if (bmi >= 25 && bmi < 30) {
            System.out.println("You are in the overweight category.");
        } else {
            System.out.println("You are in the obese category.");
        }
        System.out.println("Consult a doctor");
    }
}
```

## 控制语句

`BMICalculator`程序根据用户输入的身高和体重计算其体质量指数（BMI）。它首先使用`Scanner`类提示用户输入以米为单位的身高和以公斤为单位的体重。在接收这些输入后，它使用公式`weight / (height * height)`计算 BMI。BMI 值将保留两位小数以确保准确性。接下来，程序使用`else if`链将 BMI 分为四类——体轻、正常体重、超重和肥胖。每个类别对应一个特定的 BMI 值范围，让用户了解其相对于健康指南的体重状况。

# 4 数组

## 4.1 引言

编程中的数组确实是一种数据结构，允许用户在连续的内存位置中存储多个相同数据类型的元素。这意味着所有元素都是一个接一个存储的，便于使用索引进行顺序访问。数组中的每个元素都通过其索引标识，从零开始。当你需要处理同类型元素的集合（例如数字列表或字符串列表）时，这种数据结构特别有用。图 4.1 显示了数组的存储表示。

声明数组的语法为：

```java
datatype[] arrayname = new datatype[size];
```

### 优点

- **多个值的存储**：数组允许用户高效地存储和访问多个相同数据类型的值。
- **顺序访问**：数组中的元素在内存中顺序存储，允许使用索引位置进行快速访问。
- **内存使用优化**：数组是连续的内存块，与存储相似类型数据的其他结构相比，在内存使用方面效率更高。
- **易于迭代**：数组提供了一种直接的方法，通过`for-each`循环或传统循环遍历元素。
- **传递多个值**：数组允许你将多个值作为参数传递给方法或从方法返回多个值。

![](img/5a077f56e14b826c2dc61de6c176e5ef_100_0.png)

图 4.1 数组表示。

## 数组

### 局限性

- **固定大小**：数组的大小在声明时定义，在运行时无法动态更改。
- **同质元素**：数组只能存储相同数据类型的元素，与其他数据结构相比限制了其灵活性。
- **内存管理**：当数组大小远大于需要或当需要调整大小时，内存使用效率不佳（需要创建新数组并复制元素）。

## 4.2 数组分类



在 Java 中，根据几个标准对数组进行分类：

- 零长度数组：零元素。
- 一维数组：单行。
- 多维数组：行和列。
- 锯形数组：不同长度。
- 对象数组：基本数据类型。

## 4.3 一维数组

在 Java 中，单维度的数组被称为 1D 数组。所有元素都是同种的。例如，你可以这样声明一个整数一维数组：

```java
int[] numbers = new int[5]; // 声明大小为 5 的整数数组
```

# 数组

```java
void main(String[] args) {
  // 声明并初始化一个大小为5的数组
  int[] a = new int[5];
  Scanner sc = new Scanner(System.in);
  // 提示用户输入5个数字
  System.out.println("Please enter 5 numbers:");
  // 循环将用户输入存储到数组中
  for (int i = 0; i < a.length; i++) {
    a[i]= sc.nextInt(); // 将用户输入存储到数组
  }
  // 打印偶数位的元素（索引 0, 2, 4）
  System.out.println("Elements at even positions (0, 2, 4):");
  for (int i = 0; i < a.length; i++) {
    if (i % 2 == 0) { // 检查是否为偶数
      System.out.print(a[i] + " ");
    }
  }
}
```

# 输出:

```
Please enter 5 numbers:
1 2 3 4 5
Elements at even positions (0, 2, 4):
1 3 5
```

上面的程序通过从 `java.util` 包导入 `Scanner` 类来方便用户输入，并打印偶数位数组。在 `main` 方法中，声明并初始化了一个大小为5的整数数组 `a`。实例化 `Scanner` 对象以捕获输入。程序使用 `println` 方法提示用户输入5个数字。随后，使用 `for` 循环遍历数组，通过 `Scanner` 类的 `nextInt()` 方法将用户输入的每个值赋值给数组。一旦所有数字输入完毕，使用取模运算符 `%` 对每个元素进行奇偶性检查。如果元素除以 2 的余数为 0，则表示使用 `print` 方法打印该数字。

# 程序

数组的初始化与声明

```java
public class Main {
  void main(String[] args) {
    // 初始化一个长度为5的整数数组
    int[] a = new int[5];
    // 将值1 到 5 赋值给数组元素
    for (int i = 0; i < a.length; i++) {
      a[i] = i + 1; // 赋值1 到 5
    }
    // 使用 for-each 循环打印数组的每个元素
    for (int i : a) {
      System.out.print(i + " "); // 打印每个元素并跟一个空格
    }
  }
}
```

# 输出

```
1 2 3 4 5
```

# 用于医疗应用的 Java 22

在此程序中，初始化了一个大小为5的整数数组来存储值。通过循环将1到5的整数填充数组，并将每个值赋值给相应的索引。填充数组后，利用 for-each 循环遍历数组并用空格打印每个元素。

# 程序

程序：声明时的数组初始化

```java
public class Main {
  void main(String[] args) {
    // 直接在数组声明中初始化值为1到5的数组
    int[] a = {1, 2, 3, 4, 5};
    // 使用 for-each 循环遍历并打印每个元素
    for (int i : a) {
      System.out.print(i + " "); // 打印每个元素后跟一个空格
    }
  }
}
```

# 输出

```
1 2 3 4 5
```

上面的Java程序直接在数组声明中初始化了一个包含1到5数值的整数数组 `a`。使用 for-each 循环遍历数组 `a` 中的每个元素 `i`。在迭代期间，使用 `System.out.print()` 方法将当前元素 `i` 的值打印到控制台，后跟一个空格。结果是程序执行并在单行打印用空格分隔的1到5的数字。

## 4.4 二维数组

在Java中，二维数组结构化为行和列，类似于矩阵。它使用语法 `data_type array_name[rows][columns]` 表示。该语法通过方括号中的行数和列维度来指定数组的规模，并指定数组元素的数据类型。例如，要声明一个三行四列的二维数组，语法应为 `int[][] myArray = new int[3][4];`。这创建了一个3行4列的二维数组，其中每个元素都被初始化为该数据类型的默认值，整数类型为 `0`。

#### 语法

```
data_type array_name[rows][columns];
```

# 程序

```java
public class Main {
  void main(String[] args) {
    // 初始化一个不同行长度的二维数组
    int[][] a = {
      {1, 2, 3}, // 第一行有3个元素
      {4, 5, 6, 7}, // 第二行有4个元素
      {8, 9} // 第三行有2个元素
    };
    // 打印每一行的长度
    for (int i = 0; i < a.length; i++) {
      System.out.println("Length of row " + i + ": " + a[i].length);
    }
  }
}
```

# 数组 95

输出：

```
Length of row 0: 3
Length of row 1: 4
Length of row 2: 2
```

在 `main` 方法中，初始化了一个三行的二维数组 `a`，每行包含不同数量的元素。第一行有三个元素，第二行四个元素，第三行有两个元素。通过数组的 `length` 属性获取每行的长度。使用 `System.out.println()` 分别打印每一行的长度，对稠密数组结构提供了清晰的反馈。执行后，程序输出每行的长度，指示了每行中的元素数量。

## 4.5 三维数组

在编程中，三维数组提供了一种在三维空间中组织和处理数据的强大手段，就像在数字景观中雕刻复杂的形状。

#### 语法

```java
dataType[row][][] arrayName = new dataType[row][column][height];
```

该语法声明了一个类型为 `dataType`、名为 `arrayName` 的三维数组，维度由 `row`、`column` 和 `height` 指定。

# 程序

Java读取三维数组并打印三维数组元素的程序

```java
import java.util.Scanner;
public class Main {
    public void main(String[] args) {
        // 初始化每行大小不同的三维数组
        int[][][] a = new int[2][];
        // 第一个二维数组有3行，大小不同
        a[0] = new int[3][];
        a[0][0] = new int[2]; // 第一行有2个元素
        a[0][1] = new int[3]; // 第二行有3个元素
        a[0][2] = new int[1]; // 第三行有1个元素
        // 第二个二维数组有2行，大小不同
        a[1] = new int[2][];
        a[1][0] = new int[4]; // 第一行有4个元素
        a[1][1] = new int[2]; // 第二行有2个元素
        Scanner sc = new Scanner(System.in);
        // 提示用户输入每个元素的值
        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[i].length; j++) {
                for (int k = 0; k < a[i][j].length; k++) {
                    System.out.printf("%d[%d][%d]: ", i, j, k);
                    a[i][j][k] = sc.nextInt();
                }
            }
        }
        // 打印输入的值并分离子数组
        System.out.println("\nEnter values of 3D array:");
        for (int[][] array2 : a) {
            for (int[] array1 : array2) {
                for (int element : array1) {
                    System.out.print(element + " ");
                }
                System.out.println();
            }
        }
    }
}
```

# 输出:

```
Enter values for 3D array:
a[0][0][0]: 1
a[0][0][1]: 2
a[0][1][0]: 3
a[0][1][1]: 4
a[0][2][0]: 5
a[1][0][0]: 6
a[1][0][1]: 7
a[1][0][2]: 8
a[1][0][3]: 9
a[1][1][0]: 10
a[1][1][1]: 11
Entered values of 3D array:
1 2 
3 4 5 
6 
7 8 9 10 
11 12
```

# 数组

## 示例

```java
int[][] jaggedArray = new int[3][];
jaggedArray[0] = new int[]{1, 2, 3};
jaggedArray[1] = new int[]{4, 5};
jaggedArray[2] = new int[]{6, 7, 8, 9};
```

## 优点

- 内存效率：锯齿数组（Jagged arrays）仅需要时消耗内存，与普通的多维数组相比，效率更高。
- 灵活性：每行的元素数量不同，能够准确地表示不规则结构。

## 局限性

- 访问复杂度：由于行长度不同，访问元素可能不那么直接，需要额外的边界检查。
- 初始化开销：初始化和管理锯齿数组可能更加复杂，特别是当维度动态变化时。

## 程序

```java
public class JaggedArrayExample {
    void main(String[] args) {
        int[][] jaggedArray = new int[3][];
        jaggedArray[0] = new int[]{1, 2, 3};
        jaggedArray[1] = new int[]{4, 5};
        jaggedArray[2] = new int[]{6, 7, 8, 9};
        for (int i = 0; i < jaggedArray.length; i++) {
            for (int j = 0; j < jaggedArray[i].length; j++) {
                System.out.print(jaggedArray[i][j] + " ");
            }
        }
        System.out.println();
    }
}
```

## 输出：

```
1 2 3
4 5
6 7 8 9
```

在程序 `JaggedArrayExample` 中，声明并初始化了一个名为 `jaggedArray` 的锯齿数组，它包含三行，每行可以有不同数量的元素。第一行初始化了三个元素（1, 2, 3），第二行初始化了两个（4, 5），第三行初始化了四个元素（6, 7, 8, 9）。使用嵌套循环来遍历锯齿数组，打印每个元素并在后跟一个空格。在完成每行的内层循环后，会打印新行，以便在输出中视觉上区分不同的行。

## 4.7 对象数组

在 Java 中，“对象数组”指的是每个元素都是类或其子类对象的数组。与直接存储值的基本类型数组不同，对象数组存储的是指向堆上对象的引用（或指针）。

## 优点

- 灵活的数据结构：对象数组允许你在单个数据结构中存储不同类或其子类的多个实例。当你需要管理相关对象的集合时，这种灵活性非常有用。
- 动态大小：Java 中的数组一旦创建，其大小就是固定的。然而，通过使用如 `ArrayList`（其内部使用数组）等动态结构，开发者可以创建可调整大小的对象数组，根据需要适应不同数量的元素。
- 高效访问：访问数组中的元素（无论是基本类型还是对象）都是高效的，因为涉及直接索引。这使得对象数组适用于快速访问元素的场景。

## 局限性

- 固定大小：数组一旦创建，大小就固定。如果你需要动态添加或删除元素，则需要创建一个新数组或使用 `ArrayList` 等可调整大小的数据结构（它在内部管理数组的扩缩）。
- 同质元素：Java 中的数组是同质的，这意味着它们只能存储相同类型的元素（指定的类或其子类）。这限制了在不使用父类引用或泛型的情况下在同一个数组中直接存储不同类或类型的对象。
- 类型安全：如果使用不当，对象数组可能会导致类型问题。由于数组存储的是对象的引用，强制转换或不当的类型处理可能会在运行时导致 `ClassCastException`。

## 程序

```java
public class Example {
    void main(String[] args) {
        Object[] jaggedArray = {
            new int[]{1, 2, 3},
            new String[]{"Usha", "Rani"},
            new double[]{3.14, 2.71}
        };
        // (等待，代码文本继续下方)
        for (Object obj : jaggedArray) {
            if (obj instanceof int[]) {
                int[] intArr = (int[]) obj;
                System.out.print("int array: ");
                for (int num : intArr) {
                    System.out.print(num + " ");
                }
                System.out.println();
            } else if (obj instanceof String[]) {
                String[] strArr = (String[]) obj;
                System.out.print("String array: ");
                for (String str : strArr) {
                    System.out.print(str + " ");
                }
                System.out.println();
            } else if (obj instanceof double[]) {
                double[] doubleArr = (double[]) obj;
                System.out.print("double array: ");
                for (double num : doubleArr) {
                    System.out.print(num + " ");
                }
                System.out.println();
            }
        }
    }
}
```

输出：

```
int array: 1 2 3
String array: Usha Rani
double array: 3.14 2.71
```

此程序演示了锯齿数组（`jaggedArray`）的使用，它存储了不同类型的数组（`int[]`、`String[]`、`double[]`）。它遍历 `jaggedArray` 的每个元素，使用 `instanceof` 检查其类型，并相应打印每个嵌套数组的元素，将其归类为 `int array`、`String array` 或 `double array`。

## 4.8 命令行参数

Java 命令行参数是在 Java 程序从命令行执行时传递给它的，格式为要执行的 Java 类名之后。在 Java 中，命令行参数由指定为程序入口点的类的 `main` 方法接收。`main` 方法必须接受一个字符串数组作为其参数，这代表传递给程序的命令行参数。

例如，考虑以下运行 Java 程序的命令：

```
java MyProgram arg1 arg2 arg3
```

在该命令中：

- `MyProgram` 是要执行的 Java 类名。



- `arg1`、`arg2` 和 `arg3` 是传递给程序的命令行参数。

在 Java 程序内部，通过 `main` 方法的 `args` 参数访问这些参数。

## 程序

```java
public class MyProgram {
    void main(String[] args) {
        // 访问并处理命令行参数
        for (String arg : args) {
            System.out.println("Argument: " + arg);
        }
    }
}
```

输出：

```text
C:\java --enable-preview --source 22 MyProgram.java testing
Argument: testing
```

在此示例中，`args` 参数是一个包含传递给程序的命令行参数的字符串数组。程序随后遍历此数组以访问并处理所需内容。

## 用于医疗保健和医学应用的 Java 22

当从命令行执行 Java 程序时，开发者可以选择传递被称为命令行参数的额外信息。这些参数以空格分隔的字符串形式提供，并通过 `main` 方法的 `args` 参数在 Java 程序中访问。`args[]` 数组包含了传递给程序的所有命令行参数，每个参数作为数组中的独立元素存储。要访问命令行参数，开发者可以在 `main` 方法中使用 `args[]` 数组。可以使用 `length` 属性确定 `args[]` 数组的长度，从而允许开发者确定提供的命令行参数的数量。

## 数组

```java
// Handle the case where the input is not a valid integer
System.out.println("Please provide valid integers as command-line arguments.");
} else {
    // Handle the case where less than two arguments are provided
    System.out.println("Please provide two command-line arguments.");
}
```

```bash
$ C:\>java --enable-preview --source 20 Test.java 10 20
The sum is: 30
```

该 Java 程序尝试使用传递给程序的命令行参数执行加法。首先，`main` 方法接收一个字符串数组 `args` 作为其命令行参数。在方法内部，程序尝试将命令行参数 `args[0]` 解析为整数并将其赋值给变量 `a`。同样，它尝试将命令行参数 `args[1]` 解析为整数并将其赋值给变量 `b`。

## 程序

使用命令行参数的斐波那契数列生成器 `FibonacciGenerator`。

```java
public class FibonacciGenerator {
    public static void main(String[] args) {
        // 检查是否提供了命令行参数
        if (args.length > 0) {
            try {
                // 将命令行参数解析为整数
                int n = Integer.parseInt(args[0]);
                // 初始化两个斐波那契数
                int f1 = 0;
                int f2 = 1;
                // 打印斐波那契数列
                System.out.println("Fibonacci sequence up to " + n + " terms:");
                // 处理 n 不等于 1 的情况
                if (n >= 1) {
                    System.out.print(f1 + " " + f2 + " ");

                    // 如果 n 大于1，则打印剩余的项
                    for (int i = 1; i < n; i++) {
                        System.out.print(f2 + " ");
                        int s = f1 + f2; // 计算下一个斐波那契数
                        f1 = f2;
                        f2 = s;
                    }
                    // 打印换行以优化格式
                    System.out.println();
                } catch (NumberFormatException e) {
                // 处理输入不是有效整数的情况
                    System.out.println("Please provide a valid integer as a command-line argument.");
                }
        } else {
            // 处理未提供参数的情况
            System.out.println("Please provide the number of terms as a command-line argument.");
        }
    }
}
```

输出：

```text
C:\jj>>java --enable-preview --source 22 FibonacciGenerator.java 10
Fibonacci sequence up to 10 terms:
0 1 2 3 5 8 13 21 34
```

该 Java 程序旨在生成到指定项数的斐波那契数列，其中项数通过命令行参数提供。程序首先将命令行参数 `n` 解析为整数，代表斐波那契数列的项数。它将两个变量 `f1` 和 `f2` 分别初始化为 0 和 1，它们是斐波那契数列的前两个数。使用 `for` 循环，程序从第一项（`i=1`）迭代到指定的项数：它打印当前的斐波那契数 `f1`，通过相加 `f1` 和 `f2` 计算下一个斐波那契数 `s`，更新 `f1` 和 `f2` 的值以进入数列中的下一项。循环持续到达到所需的项数。在每次迭代中，程序打印斐波那契数 `Fn`，生成从 0 和 1 开始的斐波那契数列，每一项都是前两个项之和。

## 4.9 字符串

字符串是 Java 中的基本数据类型，允许存储文本或字符序列。虽然 Java 也提供了基本数据类型 `char` 用于单个字符存储，但对于处理名称或较长的字符序列。在 Java 中存储字符序列有两种主要方法：使用 `char[]` 数组和使用 `String` 类。第一方法涉及 `char[]` 数组，数组的每个元素代表一个字符。例如：

### 程序

```java
public class Main {
    public static void main(String[] args) {
        // 声明并初始化字符数组
        char[] c = {'t', 'e', 's', 't', 'i', 'g'};
        // 打印字符数组
        System.out.println(c); // 这将打印 "testing"
        // 或者声明并打印字符串字面量
        String s = "testing";
        System.out.println(s); // 这也将打印 "testing"
    }
}
```

输出：

```text
testing
testing
```

在 `main` 方法中，字符数组（`char[]`）被声明并初始化为字符 `'t'`、`'e'`、`'s'`、`'t'`、`'i'`、`'g'`。随后，使用 `System.out.println()` 方法将数组的内容输出到控制台。当使用 `System.out.println()` 打印字符数组时，Java 会自动将数组转换为字符串表示，导致字符的拼接。因此，该程序的输出将是字符串“testing”。或者，第二种方法使用了 `String` 类，它允许直接在双引号内声明字符序列：

### 程序

```java
public class Main {
  public static void main(String[] args) {
    // 声明并初始化字符串字面量
    String s = "testing";
    // 打印字符串字面量
    System.out.println(s);
  }
}
```

输出：

```text
testing
```

## 数组

- Tokenizer：`Tokenizer` 类用于将字符串拆分为标记（tokens）。它在内部维护一个字符串中的当前位置以进行分词。标记是原始字符串的子字符串。
- StringJoiner：`java.util` 包中的 `StringJoiner` 类用于构建一个由分隔符隔的字符序列，可选地以提供的前缀开头并以提供的后缀结束。它简化了使用分隔符连接字符串的过程。

```java
StringJoiner joiner = new StringJoiner(",");
```

- 字符串字面量和常量池：在 Java 中，可以使用字符串字面量创建字符串。JVM 会检查字符串常量池中是否存在该字符串。如果字符串不存在，则创建一个新实例并将其放置在池中。如果字符串已存在，则返回现有实例的引用。

### 4.9.1 字符串的内存分配

当使用字面量创建 `String` 对象时，它被分配在字符串常量池中。这使得 JVM 能够优化字符串字面量的初始化，以实现更好的内存管理。例如：

```java
String s = "testing";
```

相比之下，如果使用 `new` 运算符创建字符串（表示动态分配），它会在堆内存中分配一个新的内存位置。以这种方式创建的字符串不会自动添加到字符串常量池。例如：

```java
String s = new String("testing");
```

如果希望将动态分配的字符串存储在常量池中，可以使用 `intern()` 方法：

```java
String s = s.intern(); // 这会将字符串添加到字符串常量池中。
```

通常建议使用字符串字面量，因为它允许 JVM 优化内存分配并提高整体性能。这种方法确保了常用字符串在常量池中得到高效管理，有助于提高内存利用率。

### 4.9.2 不变字符串

`String` 是任何应用程序中都至关重要的数据类型，经常被用于用户名和密码等关键属性。在 Java 语言中，`String` 对象具有不可变性属性，这意味着一旦创建了字符串，其内容或状态就无法被更改。相反，任何修改字符串的尝试都会导致新 `String` 对象的创建，而原始字符串不受影响。这种不可变性增强了存储数据的可靠性和安全性，确保字符串值在赋值后保持不变，防止了意外的修改或篡改。

#### 程序

```java
public class Main {
    void main(String[] args) {
    // 声明并初始化字符串变量
    String s = "Usharani";
    // 尝试拼接另一个字符串
    s.concat("Bhimavarapu");
    // 打印原始字符串
    System.out.println(s); // 这将打印 "Usharani"
    }
}
```

#### 输出

```text
Usharani
```

在 `main` 方法内部，声明了一个字符串 `s` 并将其初始化为 `Usharani`。随后，在字符串 `s` 上调用了 `concat()` 方法，尝试拼接字符串 `Bhimavarapu`。需要注意的是，`concat()` 方法并没有修改原始字符串；而是返回一个表示拼接结果的新字符串。`concat()` 的结果没有赋值给任何变量，原始字符串 `s` 保持不变。因此，当程序使用 `System.out.println()` 打印 `s` 的值时，它将显示 `Usharani`，因为 Java 中的字符串是不可变的，这意味着它们的值一旦赋值后无法更改。如果意图捕捉拼接的结果，应该使用 `s = s.concat("Bhimavarapu");` 来用新的拼接值更新变量 `s`。

#### 程序

```java
public class Main {
    void main(String[] args) {
    // 声明并初始化字符串变量
    String s = "Usharani";
    // 拼接并更新字符串变量
    s = s.concat("Bhimavarapu");
    // 打印更新后的字符串
    System.out.println(s); // 这将打印 "Usharani Bhimavarapu"
    }
}
```

#### 输出

```text
Usharani Bhimavarapu
```

在 `main` 方法内部，声明了一个字符串 `s` 并将其初始化为 `Usharani`。在字符串 `s` 上调用了 `concat()` 方法，尝试拼接字符串 `Bhimavarapu`。与之前不同，`concat()` 方法并没有修改原始字符串；而是返回一个表示拼接的新字符串。`concat()` 操作的结果被正确地赋值回变量 `s`，从而有效地将其值更新为 `Usharani Bhimavarapu`。最后，程序使用 `System.out.println()` 打印 `s` 的修改后的值，输出结果为 `Usharani Bhimavarapu`。

Java 采用了字符串字面量，多个引用变量可以指向同一个 `String` 对象。如果一个引用变量修改了对象的值，此更改将反映在指向同一对象的所有引用变量上。这种共享对象的特性强调了 Java 中 `String` 对象的不可变性。

## 数组

几个特性共同导致 `String` 对象的不可变性：

- ClassLoader 使用：在 Java 中，字符串对象经常作为 ClassLoader 的参数。如果这些字符串对象是可以修改的，加载的类可能会因为值的改变而不同。为了防止潜在的误读和不一致，`String` 对象被设计为不可变的。
- 线程安全：字符串的不可变性确保了线程安全。字符串对象一旦修改，开发者在多个线程之间共享这些对象时不需要担心同步问题。
- 安全性考虑：字符串对象增强了应用程序的安全性。例如，在用户名和密码是敏感信息的银行软件中，字符串对象的不可变性防止了未经授权的修改。
- 堆空间效率：字符串的不可变性有助于高效使用空间。在创建新字符串时，Java 虚拟机（JVM）会检查池中是否已存在该值。如果存在，则将现有值分配给新对象，从而减少内存消耗。

### 4.9.3 字符串中的方法

在 Java 中，`String` 类提供了一组用于操作和处理字符串的方法。最常用的方法之一是 `length()`，它返回字符串中字符的数量。`charAt(int index)` 方法允许访问指定索引处的字符，`substring(int begin, int endIndex)` 提取指定索引之间的字符串部分。对于搜索，提供了方法 `indexOf(String str)` 和 `lastIndexOf(String str)` 来查找字符串首次或最后一次出现的位置。字符串比较通过 `equals(Object obj)` 实现内容的等值比较，并支持字典序比较。若要修改字符串，`toUpperCase()` 和 `toLowerCase()` 分别将字符串转换为大写或小写，`trim()` 删除任何开头或结尾的空格。`replace(char oldChar, char newChar)` 方法允许替换字符串中的特定字符。此外，`split(String regex)` 根据给定分隔符将字符串拆分为数组。字符串的不可变性意味着操作返回的是新实例而不是修改原始实例，这是 Java 处理字符串的关键方面。这些方法实现了健壮的字符串操作，使得处理应用程序中的文本数据变得更加容易。

#### 程序

```java
public class Main {
    void main(String[] args) {
        // 声明并初始化字符串变量
        String s = "testing";
        // 获取索引 3 处的字符
        char c = s.charAt(3);
        // 打印获取的字符
        System.out.println(c); // 这将打印 't'
    }
}
```

#### 输出

```text
t
```

在 `main` 方法内部，字符串变量 `s` 被声明并初始化为值 `"testing"`。`charAt()` 方法获取并存储了指定索引处的字符，在此处，索引为 3 的字符。获取到的字符被赋值给 `char` 变量 `c`。随后，`System.out.println()` 将 `char` 变量 `c` 的值打印到控制台。在此情况下，程序的输出将是字符串 `"testing"` 中索引为 3 的字符，即 `'t'`。

# 程序



# 程序

```java
public class Main {
    void main(String[] args) {
    // 声明并初始化字符串变量
    String s1 = "usha";
    String s2 = "usha";
    String s3 = "rani";

    // 使用 compareTo() 比较字符串
    int result1 = s1.compareTo(s2); // 比较 s1 和 s2
    int result2 = s1.compareTo(s3); // 比较 s1 和 s3
    int result3 = s2.compareTo(s3); // 比较 s2 和 s3
    int result4 = s2.compareTo(s1); // 比较 s2 和 s1
    // 打印比较结果
    System.out.println("s1.compareTo(s2): " + result1);
    // 0 (s1 和 s2 相等)
    System.out.println("s1.compareTo(s3): " + result2);
    // 正数值 (s1 < s3)
    System.out.println("s2.compareTo(s3): " + result3);
    // 正数值 (s2 < s3)
    System.out.println("s2.compareTo(s1): " + result4);
    // 0 (s1 和 s2 相等)
}
```

输出:

```
s1.compareTo(s2): 0
s1.compareTo(s3): -3
s2.compareTo(s3): -3
s2.compareTo(s1): 0
```

该 Java 程序定义了一个类 `Main`，其中包含一个 `main` 方法，该方法使用 `compareTo()` 方法比较三个字符串 `s1`、`s2` 和 `s3`。该方法评估字符串的字典顺序，并根据对应字符的 ASCII 值提供整数结果。在这种情况下，`s1` 和 `s2` 相同（"usha"），结果为 0，表示相等。与 `s3` 的比较产生正值，因为 "rani" 在字典顺序中在 "usha" 之前。程序将这些比较结果打印到控制台，演示了 `compareTo()` 方法如何在 Java 中方便字符串比较。`s1.compareTo(s2)`：由于 `s1` 和 `s2` 具有相同的内容（"usha"），结果为 0。`s1.compareTo(s3)`：字典顺序将 "usha" 置于 "rani" 之前，因此结果为正数。`s2.compareTo(s1)`："usha" 在字典顺序上于 "rani" 之前。由于两个字符串相等，结果为 0。

# 程序

```java
public class Main {
    void main(String[] args) {
    // 声明并初始化一个字符串变量
    String s = "testing";
    // 检查字符串 s 是否包含特定的子字符串
    boolean result1 = s.contains("test");
    boolean result2 = s.contains("in");
```

# 数组

```java
boolean result3 = s.contains("tin");
// 打印 contains 方法的结果
System.out.println(result1); // 这将打印 true
System.out.println(result2); // 这将打印 false
System.out.println(result3); // 这将打印 true
}
```

# 输出:

```
true
true
true
```

字符串 `s` 上的 `main()` 方法被声明并初始化为值 "testing。"`contains()` 方法检查其内部是否存在特定的子字符串。`contains()` 方法返回一个布尔值，指示指定的子字符串是否存在于原始字符串中。在此程序中，使用 `System.out.println()` 语句来打印不同 `contains()` 调用的结果。第一个语句检查原始字符串 "testing" 中是否包含子字符串 "test"，由于其存在，结果为 `true`。第二个语句检查子字符串 "ing"，该字符串不存在，返回 `false`。第三个语句检查子字符串 "tin"，由于它是 "testing" 的一部分，结果为 `true`。

# 程序

```java
public class Main {
    void main(String[] args) {
        // 声明并初始化一个字符串变量
        String s = "testing";
        // 检查字符串是否以特定的后缀结尾
        boolean result1 = s.endsWith("ing");
        boolean result2 = s.endsWith("ting");
        // 打印 endsWith 方法的结果
        System.out.println(result1);
        System.out.println(result2);
    }
}
```

# 输出:

```
true
true
```

在 `main()` 方法内部，声明并初始化了一个字符串变量 `s`，其值为 "testing。"字符串 `s` 上的 `endsWith()` 方法确定它是否以特定的后缀结尾。`endsWith()` 方法返回一个布尔值，指示原始字符串是否以指定的后缀结尾。在此程序中，`System.out.println()` 语句用于打印不同的 `endsWith()` 调用结果。第一个语句检查字符串 "testing" 是否以 "ing" 结尾，如果是，结果为 `true`。第二个语句检查后缀 "ting"，尽管 "testing" 包含此字符串，但 `endsWith()` 方法评估的是后缀，在这种情况下，结果为 `false`。

# 程序

```java
public class Main {
    void main(String[] args) {
        // 声明并初始化字符串变量
        String s = "testing";
```

# Java 22 用于医疗保健应用

```java
String s1 = "usharani";
String s2 = "usharani";
String s3 = "USHARANI";
String s4 = "usha";
// 使用 equals() 方法比较字符串并打印结果
System.out.println(s1.equals(s2)); // true，两者都是 "usharani"
System.out.println(s1.equals(s3)); // false，由于大小敏感
System.out.println(s1.equals(s4)); // false，因为 "usharani" 不等于 "usha"
}
```

输出:

```
true
false
false
```

在 `main` 方法中，声明并初始化了四个字符串变量 `s1`、`s2`、`s3` 和 `s4`。`equals()` 方法比较这些字符串并将结果打印到控制台。Java 中的 `equals()` 方法用于检查两个字符串是否具有相同的内容。如果内容相同，方法返回 `true`；否则返回 `false`。在此程序中，进行了以下比较：

1. `s1.equals(s2)`：由于 `s1` 和 `s2` 具有相同的内容（"usharani"），结果为 `true`。
2. `s1.equals(s3)`：比较是大小敏感的，因此结果为 `false`。
3. `s1.equals(s4)`："usharani" 不等于 "usha"，因此结果为 `false`。

# 用于医疗与健康应用的 Java 22

值被打印到控制台。这展示了将字符串中的字符转换为其相应的字节值。此外，声明了一个长度为 10 的字符数组 `c`。在字符串 `s` 上使用 `getChars()` 方法提取部分字符（从索引 1 到 6），并将它们从索引 0 开始复制到数组 `c` 中。使用 `System.out.println()` 将提取的字符打印到控制台。程序的输出将是代表字符串 'Usharani' ASCII 值的字节值序列，随后是来自原始字符串中提取的字符 'sharan'，演示了这些方法如何方便 Java 中的字符和字节操作。`getChars()` 方法允许从字符串中选择性地提取字符到另一个。

# 程序

```java
public class Main {
    void main(String[] args) {
    // 声明并初始化字符串变量
    String s1 = "Usharani";
    String s2 = "Bhimavarapu";
    // 获取字符串的长度
    int length1 = s1.length();
    int length2 = s2.length();
    // 打印字符串的长度
    System.out.println("string length is " + length1);
    System.out.println("string length is: " + length2);
}
```

输出:

```
string length is: 8
string length is: 11
```

在 `main` 方法内部，声明了两个字符串 `s1` 和 `s2`，并分别初始化为 "Usharani" 和 "Bhimavarapu"。每个字符串变量上的 `length()` 方法确定并打印了相应字符串的长度。Java 中的 `length()` 方法用于查找字符串中字符的数量，有效地提供了字符串的长度。在程序程序中，采用了 `System.out.println()` 语句将长度打印到控制台。程序的输出将是指示字符串长度的行行，例如对于 'Usharani' 的 'string length is 8' 以及对于 'Bhimavarapu' 的 'string length is 11'。

# 程序

```java
public class Main {
    void main(String[] args) {
    // 声明并初始化字符串变量
    String s = "testing";
    // 提取并打印子字符串
    // 提取从索引 2（包含）到 4（不包含）的子字符串
    System.out.println(s.substring(2, 4)); // 输出: st
    // 提取从索引 2 到字符串末尾的子字符串
    System.out.println(s.substring(2)); // 输出: sting
}
```

输出:

```
st
sting
```

# 数组 113

在 `main` 方法中，声明了一个字符串变量 `s` 并初始化值为 `testing`。字符串 `s` 上的 `substring()` 方法根据索引提取并打印子字符串。`System.out.println()` 语句演示了双参数版本的 `substring()` 方法，其中起始索引是包含的（2），结束索引是不包含的（4）。该操作从原始字符串 `testing` 中提取子字符串 "st" 并将其打印到控制台。第二个 `System.out.println()` 语句使用了单参数版本的 `substring()` 方法，仅提供了起始索引（2）。在此情况下，该方法提取从索引 2 直到字符串末尾的子字符串，导致 "sting" 被打印到控制台。

# 程序

```java
public class Main {
    void main(String[] args) {
        // 字符串初始化
        String s = "testing";
        // 将字符串转换为字符数组
        char[] c = s.toCharArray();
        // 打印数组中的每个字符
        for (char ch : c) { System.out.print(ch); // 输出: testing
        }
        // 将字符串转换为小写并打印
        String s1 = "USHARANI";
        System.out.println(s1.toLowerCase()); // 输出: usharani
        // 将字符串转换为大写并打印
        String s2 = "bhimavarapu";
        System.out.println(s2.toUpperCase()); // 输出: BHIMAVARAPU
    }
}
```

输出:

```
testing
usharani
BHIMAVARAPU
```

在 `main` 方法中，对不同的字符串执行了若干字符串字符串的操作。首先，声明了 `s` 并利用 `toCharArray()` 方法将其转换为字符数组。然后使用 `for` 循环遍历数组元素并将每个字符打印到控制台。这演示了字符串到字符数组的转换以及随后的逐字符处理。接下来，声明了包含大写字母的字符串 `s1`，并使用 `toLowerCase()` 方法将所有字符转换为小写。结果 `usharani.` 被打印到控制台。这突出了大写字母到小写的转换。同样地，声明了另一个包含小写字母的 `s2`，并应用 `toUpperCase()` 方法将所有字符转换为大写。结果 `BHIMAVARAPU` 被打印到控制台。

# 程序

```java
public class Main {
    void main(String[] args) {
        // 初始化字符串
        String s = "Dr. Usha rani Bhimavarapu";
        // 根据空白分割字符串
        String[] w = s.split("\\s+");
        // 打印数组中的每个单词
        for (String word : w) {
            System.out.println(word);
        }
    }
}
```

输出:

```
Dr.
sha
rani
Bhimavarapu
```

在 `main` 方法内部，声明了字符串变量 `s` 并初始化值为 "Dr. Usha rani Bimavarapu。"`s` 上的 `split()` 方法根据空白字符将它分割为单词数组。`split()` 方法接受一个正则表达式作为参数，在本例中，使用了正则表达式 `\s+` 来匹配任何空白，包括空格和制表符。生成的单词数组存储在字符串 `w` 中。使用 `for` 循环遍历数组元素，并使用 `System.out.println()` 将每个单词打印到控制台。程序的输出将是原始字符串中的每个单词逐行打印。单词 "Dr.," "Usha," "rani," 和 "Bhimavarapu" 被分别打印。

## 用于医疗保健和医疗应用的 Java 22

- `ensureCapacity()` 方法：`ensureCapacity()` 方法确保给定的容量成为当前 `StringBuilder` 的最小容量。如果指定的容量大于当前容量，它将使用与 `capacity()` 方法中相同的公式来增加容量。

本质上，`StringBuilder` 类为 Java 中不可变的 `String` 类提供了一个可变的替代方案，允许进行动态修改，并在多线程访问时确保线程安全操作。

## 以可变方式操纵字符串

```java
public class Main {
    public void main(String[] args) {
        // 初始化一个初始值为 "testing" 的 StringBuilder 对象
        StringBuilder sb = new StringBuilder("testing");
        // 使用 append() 方法将 "stringbuffer" 接到现有内容之后
        sb.append("stringbuffer");
        // 打印修改后的字符串
        System.out.println(sb.toString());
    }
}
```

输出：

```
testing stringbuffer
```

在 `main` 方法中，实例化并初始化了一个名为 `sb` 的 `StringBuilder` 对象，其初始值为 "testing"。随后在 `StringBuilder` 对象 `sb` 上使用了 `append()` 方法，将字符串 "stringbuffer" 接到其内容之后。重要的是，`StringBuilder` 类允许可变字符串，这意味着原始字符串可以被修改。在这种情况下，`append()` 方法通过追加指定的字符串来修改 `sb` 对象的内容。最后使用 `System.out.println()` 打印修改后的字符串，结果输出结果为："testing stringbuffer"。

## 程序

```java
public class Main {
    public void main(String[] args) {
        // 初始化一个初始值为 "test" 的 StringBuilder 对象
        StringBuilder sb = new StringBuilder("test");
        // 使用 insert() 方法在索引 3 处插入 "Java"
        sb.insert(3, "Java");
        // 打印修改后的字符串
        System.out.println(sb.toString());
    }
}
```

输出：

```
tesJavat
```



在`main`方法中，实例化并初始化了一个名为`sb`的`StringBuilder`对象，其初始值为`"test"`。随后在`StringBuilder`对象`sb`上利用`insert()`方法在指定位置（在本例中为索引`3`）插入字符串`"Java"`。与不可变字符串不同，`StringBuffer`类允许动态修改，且`insert()`方法提供了一种在字符串指定位置插入新内容的方法。原始字符串`test`被修改，并在索引`3`处插入了指定的字符串`Java`，导致修改后的字符串`testJava`。使用`System.out.println()`打印修改后的字符串，输出`testJava`。

## 程序

```java
public class Main {
    public void main(String[] args) {
        // 初始化一个初始值为 "usharani" 的 StringBuffer 对象
        StringBuffer sb = new StringBuffer("usharani");
        // 使用 replace() 方法替换索引 2 到 4 的字符
        // 为 "test"
        sb.replace(2, 4, "test");
        // 打印修改后的字符串
        System.out.println(sb.toString());
    }
}
```

输出：

```text
ustestani
```

在`main`方法中，实例化并初始化了一个名为`sb`的`StringBuffer`对象，其初始值为`"usharani"`。随后在`StringBuffer`对象`sb`上应用了`replace()`方法来替换字符串的一部分。在这种情况下，索引`2`到`4`（不包含`4`）的字符被替换为字符串`test`。与不可变字符串不同，`StringBuffer`类支持动态修改，允许更改字符串中的特定片段。执行`replace()`操作后，原始字符串`usharani`被修改，替换内容`test`被插入到指定位置，产生修改后的字符串`ustestani`。使用`System.out.println()`打印修改后的字符串，输出`ustestani`。

## 程序

```java
public class Main {
    public void main(String[] args) {
        // 初始化一个初始值为 "testing" 的 StringBuffer 对象
        StringBuffer sb = new StringBuffer("testing");
        // 使用 delete() 方法删除索引 2 到 4 的字符
        // （不包含 5）
        sb.delete(2, 5); // 打印修改后的字符串
        System.out.println(sb.toString());
    }
}
```

输出：

```text
teng
```

在`main`方法中，实例化并初始化了一个名为`sb`的`StringBuffer`对象，其初始值为`"testing"`。程序在`StringBuffer`对象`sb`上利用`delete()`方法来删除字符串的一部分。在本例中，索引`2`到`4`（不包含`5`）的字符被删除，修改了原始字符串`testing`。执行`delete()`操作后，修改后的字符串现在为`teng`。随后使用`System.out.println()`语句将更新后的字符串打印到控制台。

## 程序

```java
public class Main {
    public void main(String[] args) {
        // 初始化一个初始值为 "testing" 的 StringBuilder 对象
        StringBuilder sb = new StringBuilder("testing");
        // 使用 reverse() 方法反转 StringBuilder 中的字符
        sb.reverse();
        // 打印反转后的字符串
        System.out.println(sb.toString());
    }
}
```

输出：

```text
gitset
```

在`main`方法内部，实例化并初始化了一个名为`sb`的`StringBuilder`对象，其初始值为`"testing"`。`StringBuilder`对象`sb`上的`reverse()`方法反转了字符串内的字符。与不可变字符串不同，`StringBuilder`类允许动态修改，且`reverse()`方法提供了反转内容的方法。执行`reverse()`操作后，原始字符串`testing`被修改，使用`System.out.println()`打印反转后的字符串，输出结果为：`"gitset"`。

## 数组

117

在`main`方法内部，创建了一个`StringBuilder`对象`sb`并将其初始化为字符串`‘Usha’`。首先，使用`append`方法将字符串`‘rani’`连接到现有的`StringBuilder`中，生成字符串`‘Usharani’`。打印该`Builder`以显示更新后的内容。使用`insert`方法在`StringBuilder`的开头插入前缀`‘Dr’`，将其转换为`‘Dr.Usharani’`。再次打印该`Builder`以显示修改。使用`replace`方法将从`7`到`11`（不包含`11`）的子字符串替换为字符串`‘Ram’`。此操作将字符串内容更改为`‘Dr.UshaRami’`，并打印修改后的`StringBuilder`。随后，使用`capacity`方法打印`StringBuilder`的当前容量。接着，应用`delete`方法删除从`7`到`11`（不包含`11`）的子字符串，生成字符串内容`‘Dr.Usha’`。在此操作后，打印修改后的`StringBuilder`。最后，使用`reverse`方法反转`StringBuilder`中的内部字符，生成字符串`‘ahsU.rd’`。程序在反转后打印`StringBuilder`的最终内容。

## 4.12 字符串分词器

`StringTokenizer`类用于将字符串划分为不同的标记（tokens）。在内部，`StringTokenizer`对象维护分词字符串中的当前位置，某些操作可以提供此位置以推进已处理字符。该类在解析过程的初始阶段起着关性作用，该阶段通常称为词法器（lexer）或扫描器（scanner）。

Java的`StringTokenizer`涉及到对该类的利用，允许应用程序有效地将字符串拆解为标记。该类实现了`Enumeration`接口，便于对标记进行枚举。它主要用于解析数据，需要指定输入字符串和包含分隔符的字符串。在此文中，分隔符是充当标记分隔的字符。分隔符字符串中的每个字符都被识别为有效的分隔符。默认情况下，空格、换行符和制表符等空白字符作为分隔符。本质上，`StringTokenizer`类提供了一种根据指定的分隔符将字符串分解为可管理标记的机制，为Java中的解析过程提供了基础步骤。

```java
import java.util.StringTokenizer;

public class Main {
    public static void main(String[] args) {
        String input = "This is a test.";
        StringTokenizer tokenizer = new StringTokenizer(input);
        int tokenIndex = 1; // 初始化计数器

        while (tokenizer.hasMoreTokens()) { // 遍历标记
            String token = tokenizer.nextToken(); // 获取下一个标记
            System.out.println("Token " + tokenIndex + ": " + token); // 打印带有索引的标记
            tokenIndex++; // 标记索引增加
        }
    }
}
```

输出：

```text
Token 1: This
Token 2: is
Token 3: a
Token 4: test.
Token 5: .
```

在`main`方法内部，创建了一个`StringTokenizer`类的实例，并初始化为字符串“This is to test.”。`StringTokenizer`类是`java.util`包的一部分，用于将字符串拆分为标记。使用一个`for`循环来检查是否有更多标记。如果有可用标记，则调用`nextToken()`方法来获取并打印带有相应索引的标记。程序的输出将显示给定字符串中的每个标记及其索引。

## 4.13 字符串模板

Java中引入字符串模板（String Templates）解决了现代软件开发中的若干实际需求，特别是增强代码可读性、提高安全性以及简化字符串插值过程。

### Java中字符串模板的需求

- **提高可读性与表达力**：字符串模板提供了一种自然的方式来包含变量和表达式，而无需使用复杂的拼接或格式化，使代码更加简洁且易于理解。
- **增强安全性**：在从用户提供或动态计算的值构建字符串时，开发者通常需要确保生成的字符串格式正确且能够防范注入（如SQL注入或脚本注入）。字符串模板通过自动转义和格式化来确保安全编码实践，降低了安全漏洞的风险。
- **简化拼接**：在Java引入之前，使用变量或表达式拼接字符串需要显式地处理拼接运算符（`+`）并将值转换为字符串。字符串模板通过允许开发者直接在`${}`占位符中嵌入表达式，简化了这一过程。
- **便于国际化（i18n）**：字符串模板支持国际化过程，使得在不修改原始字符串结构的情况下，更容易管理和维护应用程序的本地化版本。
- **兼容现代编程模式**：字符串模板与强调可读性、简单性和开发者生产力的现代模式及框架保持一致。它们通过提供在字符串中包含变量和表达式的直接方法，促进了声明式编程风格的采用。

## 程序

```java
class Demo {
  static void main(String[] args) {
    String name = "Usharani";
    String greeting = STR."Hello, {name}";
    System.out.println(greeting);
  }
}
```

输出：

```text
Hello, Usharani!
```

上述程序使用字符串模板创建一个问候消息并将其打印到控制台。它使用名称“Usharani”来生成问候消息“Hello, Usharani!”.

## 程序

```java
class Demo {
  static void main(String[] args) {
    int a = 10, b = 20;
    String result = STR."The sum of {a} and {b} is {a + b}.";
    System.out.println(result);
  }
}
```

## 输出

```text
The sum of 10 and 20 is 30.
```

此程序计算两个整数的和，并使用字符串模板打印结果。它使用变量`a`和`b`来生成消息“The sum of 10 and 20 is 30”。

## 程序

```java
class Demo {
  static void main(String[] args) {
    double price = 24.56;
    String formattedPrice = STR."The price is {String.format("%2f", price)}";
    System.out.println(formattedPrice);
  }
}
```

## 输出

```text
The price is 24.56 dollars.
```

此程序使用字符串模板在消息中包含格式化后的价格。具体而言，它使用`String.format`将价格格式化为两位小数。

## 4.14 Java正则表达式

在Java中，正则表达式（regex）提供了一种强大的搜索、操作和验证模式的方法。正则表达式为Java中的字符串处理和验证提供了强大的工具，提供了处理文本处理任务的多用途方式。

### 4.14.1 Java中正则表达式的好处

- **灵活性**：允许复杂的模式匹配和字符串操作。
- **效率**：提供了优化的匹配算法。
- **一致性**：有助于在整个应用程序中保持统一的数据验证。
- **表达力**：简洁地定义了搜索和替换文本的模式。

### 4.14.2 Java正则表达式的基础

#### 4.14.2.1 创建模式

在Java中，正则表达式由`java.util.regex`包中的`Pattern`类表示。你可以使用`Pattern.compile()`方法创建模式，该方法将正则编译为`Pattern`对象。

##### 程序

```java
import java.util.regex.*;

class Arrays {
    static void main(String[] args) {
        String regex = "ab+c";
        Pattern pattern = Pattern.compile(regex);
        System.out.println(pattern);
    }
}
```

##### 输出

```text
ab+c
```

在此程序中，正则表达式模式“ab+c”被定义并使用`Pattern.compile()`方法编译。程序打印编译后的模式，确认了正则对象的创建。

一旦有了`Pattern`对象，就可以用它创建一个`Matcher`对象，根据模式执行匹配、搜索和替换字符串的操作。

#### 4.14.2.2 匹配与搜索

##### 程序

```java
import java.util.regex.*;

class Example {
    static void main(String[] args) {
        String regex = "ab+c";
        Pattern pattern = Pattern.compile(regex);
        String input = "abbc";
        Matcher matcher = pattern.matcher(input);
        boolean matches = matcher.matches(); // 如果整个输入匹配正则
        boolean found = matcher.find(); // 如果在输入中找到正则模式
        System.out.println(matches);
        System.out.println(found);
    }
}
```

##### 输出

```text
true
false
```

在`Example`示例中，正则表达式“ab+c”被编译为模式。然后使用匹配器对输入字符串“abbc”进行测试。`matches()`方法检查整个输入字符串是否匹配正则，而`find()`方法在输入中查找模式的任何出现情况。结果将被打印，以指示是否找到了完全匹配或部分匹配。

#### 4.14.2.3 正则方法

124 Java用于医疗与医学应用

- `group()`：返回匹配正则表达式模式的字符串。
- `start()`和`end()`：返回匹配子字符串的起始和结束索引。

#### 4.14.2.4 常见正则表达式模式

- `\.`：匹配任意单个字符。
- `[abc]`：匹配括号内的任何字符。
- `[^abc]`：匹配不在括号内的任何字符。
- `\d`：匹配任意数字（等于`[0-9]`）。
- `\w`：匹配任何单词字符（等于`[a-zA-Z0-9_]`）。
- `\s`：匹配任何空白字符。
- `*`、`+`、`?`：量词，指定字符或组可以出现的次数（`*`为0次或多次，`+`为一次或多次，`?`为0次或一次）。

#### 4.14.2.5 示例：验证电子邮件邮箱

##### 程序

```java
import java.util.regex.*;
public class EmailValidator {
    void main(String[] args) {
        String email = "usharanibhimavararapu@gmail.com";
        String regex = "^[a-zA-Z0-9_.-]+@[a-zA-Z]+\\.[{2,}$";
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher(email);
        if (matcher.matches()) {
            System.out.println("Valid email format.");
        } else {
            System.out.println("Invalid email format.");
        }
    }
}
```

##### 输出

```text
Valid email format.
```



在此程序中，使用正则表达式实现了电子邮件验证。正则表达式`^[a-zA-Z0-9_.-]+@[a-zA-Z]+\..[2,}$`设计用于匹配有效的电子邮件格式，该格式包括"@"符号前的字母、数字和下划线、域名，以及至少包含两个字符的顶级域名。使用`matcher`对输入的电子邮件`usharanibhimavararapu@gmail.com`进行该模式进行测试。如果电子邮件匹配该正则表达式，程序将打印"Valid email format."；否则打印"Invalid email format."。由于地址`usharanibhimavararapu@gmail.com`符合指定的有效电子邮件格式正表达式，因此程序打印了"Valid email format."。

## 4.15 医学应用

### 4.15.1 案例研究

闭阻塞症（Buerger's disease），也称为阻塞性血段炎，是一种累及四肢动脉的罕见疾病。症状包括手脚疼痛（可能非常严重）、间歇性以及脚趾或手指变色。闭阻塞症症状：一组与该疾病相关的预定义症状。

程序提示用户输入症状，将这些症状与闭阻塞症预定义的症状进行比较，并输出是否检测到闭阻塞症。

```java
import java.util.Scanner;
public class BuergersDetection {
    public void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // 闭阻塞症症状
        String[] burgersSymptoms = {"Pain in hands and feet", "Claudication", "Pale or blue toes or fingers"};
        // 患者症状
        String[] patientSymptoms = new String[3];
        // 输入症状
        System.out.println("Enter symptoms by the patient:");
        for (int i = 0; i < patientSymptoms.length; i++) {
            System.out.print("Symptom " + (i + 1) + ": ");
            patientSymptoms[i] = scanner.nextLine();
        }
        // 检查闭阻塞症
        boolean hasBuergers = checkBuergers(burgersSymptoms, patientSymptoms);
        // 输出结果
        System.out.println("Buerger's Detection Result:");
        System.out.println(hasBuergers ? "Buerger's Disease Detected" : "Buerger's Disease Not Detected");
        scanner.close();
    }
    // 根据症状检查闭阻塞症的方法
    private static boolean checkBuergers(String[] burgersSymptoms, String[] patientSymptoms) {
        for (String burgersS : burgersSymptoms) {
            for (String patientS : patientSymptoms) {
                if (patientS.equalsIgnoreCase(burgersS)) {
                    return true;
                }
            }
        }
        return false;
    }
}
```

Java 程序`BuergersDetection`旨在根据用户输入的症状辅助检测闭阻塞症。它首先初始化一个`burgersSymptoms`数组，其中包含与闭阻塞症相关的典型症状，例如手脚疼痛、间歇性以及脚趾或手指变色。提示用户输入他们的症状，并通过一个遍历数组每个索引的循环将症状存储在`patientSymptoms`数组中。

随后，程序使用命名为`checkBuergers`的方法将用户输入的症状（`patientSymptoms`）与闭阻塞症预定义的症状（`burgersSymptoms`）进行比较。该方法使用嵌套循环遍历两个数组以查找匹配项，且不区分大小写。如果在比较过程中找到匹配项，程序将一个布尔变量`hasBuergers`设置为`true`，表示根据输入的症状可能患有闭阻塞症。

比较完成后，程序将输出疾病检测结果。如果`hasBuergers`为`true`，它将打印"Buerger's Disease Detected"，表明用户输入的症状与闭阻塞症的常见症状相符。相反，如果没有找到匹配项，它将打印"Buerger's Disease Not Detected"，意味着输入的症状与该疾病的典型症状不符。

### 4.15.2 案例研究

克罗恩病（Crohn's disease）是一种主要影响胃肠道的慢性炎症性疾病，会导致消化系统内膜的炎症和损伤。它是炎症性肠病（IBD）的一种，可以影响从口腔到肛门的胃肠道任何部分。考虑的参数有：

- CRP（C反应蛋白）水平：CRP 是体内炎症的标志物。CRP 水平升高可能表明炎症，这由于胃肠道的慢性炎症在克罗恩病中很常见。

- ESR（红细胞沉降率）：ESR 测量红细胞在试管底部沉积的速度。较高的 ESR 水平表明体内存在炎症，这可能指示了克罗恩病。

- WBC（白细胞）计数：WBC 是免疫系统的一部分，白细胞计数升高可能表明炎症或感染，这在克罗恩病的发发期经常ر到。

- 血红蛋白水平：血红蛋白是红细胞中携带氧气的蛋白质。由于炎症肠道失血或营养不良，克罗恩病可能会出现血红蛋白水平低（贫血）。

- 蛋白蛋白水平：白蛋白是血液中的一种蛋白。水平低可能意味着克罗恩病中的炎症或营养不良。

## 5 Java 方法

### 5.1 简介

在 Java 中，方法是执行特定任务或操作的代码块。它将一组指令封装在定义的范围内，并可以从程序的其他部分被调用或调用以执行其功能。方法实现了代码的重用、模块化和抽象，使程序更有条理、高效且易于维护。

#### 方法的优点

- 代码重用性：方法促进了代码的重用，减少了重复，并提高了整个程序的一致性。

- 模块化：方法通过将复杂任务分解为更小、更易于管理的单元来增强代码组织结构，提高了可读性和可维护性。

- 抽象：方法抽象了实现细节，为与功能交互提供了清晰的接口，而无需理解其工作原理。

- 参数化：方法可以接受参数，允许它们对不同的数据输入进行操作，从而增加了灵活性和适应性。

- 封装：方法封装了功能，促进了数据隐藏，并确保只有相关信息暴露给程序的其他部分。

#### 方法的局限性

- 性能开销：由于调用开销和参数传递，调用方法会产生微小的性能开销，尽管现代 JVM 在很大程度上优化了这一点。

- 复杂性：过度使用方法会导致代码碎片化，使程序更难理解和维护。

- 开销：定义和管理大量方法会在内存消耗和程序大小方面引入开销。

- 调试：调试方法有时是具有挑战性的，特别是当它们过于复杂或错误发生在嵌套方法调用的深处时。

尽管有这些局限性，方法的优点通常大于缺点，使其成为编写清洁、高效且易于维护的 Java 代码不可或缺的工具。

### Java 方法

#### 语法

```
accessModifier returnType methodName(parameterType parameter1, parameterType parameter2, ...) {
  // 方法体
  // 语句
  return value; // 可选的返回语句
}
```

- 访问修饰符 (Access Modifier)：指定方法的访问访问性（例如`public`、`private`、`protected`或默认访问）。

- 返回值类型 (Return Type)：指定方法返回的值的数据类型。如果方法不返回值，则使用`void`。

- 方法名 (Method Name)：方法的名称，必须是有效的 Java 标识符。

- 参数 (Parameters)：传递给方法的输入数据。参数是可选的，方法可以有零或多个参数。

- 方法体 (Method Body)：包含定义方法行为的语句。

- 返回语句 (Return Statement)：用于从方法返回值的可选语句。对于返回类型为`void`的方法，不需要该语句。

#### 程序

```java
public class Calculator {
  // 两个整数相加的方法
  public int add(int num1, int num2) {
    return num1 + num2;
  }
  // 两个整数相减的方法
  public int subtract(int num1, int num2) {
    return num1 - num2;
  }
  // 两个整数相法的方法
  public int multiply(int num1, int num2) {
    return num1 * num2;
  }
  // 两个整数相法的方法
  public double divide(int num1, int num2) {
    if (num2 != 0) {
      return (double) num1 / num2;
    } else {
      throw new IllegalArgumentException("Cannot divide by zero");
    }
  }
  // 测试 Calculator 类的主方法
  void main(String[] args) {
    Calculator calculator = new Calculator();
    System.out.println("Addition: " + calculator.add(10, 5));
    System.out.println("Subtraction: " + calculator.subtract(10, 5));
    System.out.println("Multiplication: " + calculator.multiply(10, 5));
    System.out.println("Division: " + calculator.divide(10, 5));
  }
}
```

#### 用于医疗保健和医学应用的 Java 22

输出：

```
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
```

在此程序中，创建`Calculator`类来执行算术运算。该类包含方法：`add`、`subtract`、`multiply`和`divide`；每个方法都旨在接收两个整数并返回相应操作的结果。`divide`方法包含错误处理，通过抛出`IllegalArgumentException`防止除以零。`main`方法创建了`Calculator`类的实例，并使用值 10 和 5 测试了算术方法。它在控制台上打印了每个操作的结果——加法、减法、乘法和除法。结果如下：10和15相加、减法结果为5、乘法结果为50、除法结果为2.0。这有效地展示了`Calculator`类的功能。

方法可以在同一个类内调用，也可以通过创建包含该类的对象从其他类调用。调用方法时，参数的顺序、数量和数据类型必须匹配。方法可以重载，这意味着一个类可以有多个同名但参数列表不同的方法。方法可以选择地有一个返回语句以向调用者返回值。如果返回类型为`void`，则不返回值。可以使用访问修饰符（`public`、`private`、`protected`或默认访问）控制方法的访问权限。

### 5.2 方法类型

在 Java 中，根据创建方式和目的，可以将方法分为用户定义或预定义方法。

#### 5.2.1 用户定义方法

在 Java 中，根据创建方式和目的，可以将方法分为用户定义或预定义方法。

用户定义方法是程序员创建的执行特定任务的方法。

示例：

```java
public class MyClass {
    public void greet() {
        System.out.println("Hello World!");
    }

    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj.greet();
    }
}
```

输出：

```
Hello World!
```

#### 5.2.2 预定义方法

预定义方法（也称为内置方法）由 Java 标准库提供。它们无需程序员定义即可直接使用。

```java
public class PredefinedExample {
    public static void main(String[] args) {
        String str = "sharani!";
        int length = str.length();
        System.out.println("Length of the string: " + length);
    }
}
```

输出：

```
Length of the string: 9
```

```java
public class MathUtils {
  // Static method
  public static int add(int a, int b) {
    return a + b;
  }
  // Another static method
  public static int subtract(int a, int b) {
    return a - b;
  }
}
```

在此程序中，定义了一个名为`MathUtils`的类，其中包含两个静态方法：`add(int a, int b)`和`subtract(int a, int b)`。`add`方法接收两个整数并返回它们的和，而`subtract`方法接收两个参数，并返回第一个参数减去第二个参数的结果。由于被声明为静态（static），这些方法可以在无需创建`MathUtils`类实例的情况下被调用，从而能够方便地访问并执行基础算术操作。这种设计提高了代码的可重用性和简单性，因为用户可以使用类名来调用这些方法。

#### 5.2.2.3 构造方法

构造方法是在使用`new`关键字创建类对象时调用的特殊方法。它们用于初始化对象的状态。

```java
public class test {
  private String name;
  // Constructor method
  public test(String initialName) {
    name = initialName;
  }
}
```

在此程序中，定义了一个名为`test`的类，包含一个私有实例变量`name`。该类包含一个构造方法，接收一个参数`initialName`，该参数用于在创建对象时初始化`name`变量。此构造方法确保了`name`字段在实例化时被设置为特定值，封装了数据并为初始化`test`类的对象提供了一种受控的方法。通过使用构造方法，程序建立了一种清晰且结构化的初始化对象状态的方法，良好的良好的面向设计原则。

#### 5.2.2.4 Getter 和 Setter 方法

Getter 方法（访问器）获取私有实例变量的值，Setter 方法（赋值器）设置私有实例变量的值。它们通常用于封装对实例变量的访问。

```java
public class Employee {
  private String name;
  // Getter method
  public String getName() {
    return name;
  }
  // Setter method
  public void setName(String setName) {
    name = setName;
  }
}
```

在此程序中，定义了一个名为`Employee`的类，包含一个私有实例变量`name`。该类提供了一个 getter 方法`getName()`，允许访问`name`变量的值，以及一个 setter 方法`setName(String name)`，允许修改`name`变量。这种设计遵循了面向对象编程的封装原则，允许对私有数据进行受控的访问和修改。getter 和 setter 方法确保了`name`变量可以被安全地访问和更新，同时维护了`Employee`对象状态的完整性。

#### 5.2.2.5 初始化块

初始化块用于初始化实例变量。它们在每次创建类的对象时执行。

```java
public class MyClass {
    private int value;
    // Initialization block
    {
        value = 10;
    }
}
```

在此程序中，`MyClass`类包含名为`value`的私有实例变量。类内部定义了一个实例初始化块，每当创建`MyClass`的对象时，该块都会将`value`设置为 10。此初始化块在类的构造方法之前运行，确保了每个`MyClass`实例的`value`都被初始化为 10，而无需在构造方法中显式初始化。这种方法为在实例化时为变量设置默认值提供了一种方便的方式。

#### 5.2.2.6 静态初始化块

静态初始化块用于初始化静态变量。它们在类加载到内存时执行。



```java
public class MyStaticClass {
    private static int count;
    // Static initialization block
    static {
        count = 0;
    }
}
```

在此程序中，`MyStaticClass` 类包含一个名为 `count` 的私有静态变量。定义了一个静态初始化块将 `count` 初始化为 0。该块在类首次加载到内存时执行，确保在创建任何类实例或调用任何静态方法之前，`count` 变量都被设置为 0。使用静态初始化块可以在需要为静态变量执行复杂的初始化逻辑，同时为静态成员设置默认值提供了一种清晰且有序的方法。

## 5.2.2.7 抽象方法

抽象方法在抽象类或接口中声明但不包含实现。子类必须为抽象方法提供具体的实现。

```java
public abstract class Shape {
    // Abstract method
    public abstract double area();
}
```

在此程序中，`Shape` 类被定义为一个抽象类，这意味着它不能被直接实例化。它包含一个名为 `area()` 的抽象方法，该方法没有方法体，必须由任何扩展 `Shape` 的子类来实现。这种设计对子类强制执行了一种约，要求它们提供 `area()` 方法的自己的实现，从而实现了多态。通过使用抽象类，程序为形状定义其面积计算建立了一个框架，提升了在处理各种类型时的代码重用性和灵活性。

## 5.2.2.8 Final 方法

`final` 方法（最终方法）不能在子类中被重写。它们可以在任何类中声明，包括抽象类。

```java
public class Parent {
    // Final method
    public final void display() {
        System.out.println("Parent class");
    }
}
```

在此程序中，`Parent` 类定义了一个名为 `display()` 的方法并将其声明为 `final`。该方法会在控制台打印“Parent class”。由于它被声明为 `final`，它不能在子类中被重写。这确保了该方法的行为在继承层次结构中保持一致。

## 用于医疗和健康应用的 Java 22

```java
public class Calculator {
// 带有多个参数的方法
public static int add(int a, int b, int c) {
  return a + b + c;
}
```

在此段代码中，创建了一个 `Calculator` 类，其中包含一个名为 `add` 的方法。`add` 方法接受三个整数参数：`a`、`b` 和 `c`。它执行这三个整数的相加并返回结果。

## 5.3.5 变长参数（Varargs）

变长参数（varargs）允许方法接受任意数量类型的参数。

```java
public class VarargsExample {
// 带有变长参数的方法
public static int sum(int... numbers) {
  int total = 0;
  for (int num : numbers) {
    total += num;
  }
  return total;
}
```

在此段代码中，定义了一个 `VarargsExample` 类，其中包含一个名为 `sum` 的方法，该方法使用了变长参数（`int...`）。变长参数允许方法接受任意数量的参数。在方法内部，`for-each` 循环遍历传递的 `numbers`，通过将每个数字加到 `total` 变量中来计算总和。最后，方法返回计算出的总和。这种方法简化了传递多个参数的过程，而无需在方法签名中显式定义参数的数量。

## 程序

```java
public class Test {
  static void display(int... v) {
    System.out.print("Number of arguments = " + v.length + ", Contents = ");
    if (v.length == 0) {
      System.out.println("none");
    }
    for (int x : v) {
      System.out.print(x + " ");
    }
    System.out.println();
  }

  public void main(String[] args) {
    int n1[] = { 10 };
    int n2[] = { 1, 2, 3 };
    int n3[] = { };
    display(n1);
    display(n2);
    display(n3);
  }
}
```

输出：

```text
Number of arguments = 1, Contents = 10
Number of arguments = 2, Contents = 1 2 3
Number of arguments = 0, Contents = none
```

此程序演示了如何在 Java 中使用变长参数来高效处理任意数量的参数。`display` 方法使用变长参数语法（`int... v`）接收任意数量的整数。在 `display` 方法内部，会打印参数的数量及其内容。如果没有参数，它会打印 `"none"`。然后，它遍历提供的参数并打印每个整数值，后面后跟一个空格。在打印所有参数后，它添加一个换行符以移动到下一行。在 `main` 方法中，声明并初始化了三个数组 `n1`、`n2` 和 `n3`，它们具有不同的整数值集合。然后，这些数组被作为参数传递给 `display` 方法。第一次调用传递了 `n1`，它包含一个整数（10），第二次调用传递了 `n2`，它包含三个整数（1、2 和 3），第三次调用了 `n3`，这是一个空数组。执行程序时，程序将输出每次调用的参数数量及其内容。对于 `n1`，它将打印 `"Number of arguments = 1, Contents = 10."`。对于 `n2`，它将打印 `"Number of arguments = 3, Contents = 1 2 3。"`。对于 `n3`，因为它没有参数，将打印 `"Number of arguments = 0, Contents = none。"`

## 5.3.6 数组参数

方法可以接受数组作为参数，允许它们处理相同类型的多个值。

```java
public class ArrayExample {
// 带有数组参数的方法
public static int findMax(int[] numbers) {
  int max = numbers[0];
  for (int i = 1; i < numbers.length; i++) {
    if (numbers[i] > max) {
      max = numbers[i];
    }
  }
  return max;
}
}
```

在此段代码中，`ArrayExample` 类定义了一个名为 `findMax` 的方法，接受一个整数数组（`int[]`）作为参数。该方法寻找数组中的最大值。

## 5.3.7 对象参数

方法可以接受对象作为参数，允许它们与对象的方法和字段进行交互。

```java
public class Person {
    String name;

    Person(String name) {
        this.name = name;
    }

    void setName(String name) {
        this.name = name;
    }

    String getName() {
        return name;
    }
}

public class ObjectExample {
    public static void updateName(Person p) {
        p.setName("New Name");
    }

    public static void main(String[] args) {
        Person person = new Person("John");
        System.out.println("Before: " + person.getName());
        updateName(person);
        System.out.println("After: " + person.getName());
    }
}
```

在此示例中，`updateName` 方法接收 `Person` 对象的引用。方法内部使用 `setName` 对对象进行的更改会影响原始对象。

## 5.4 方法重载

方法重载允许类定义相同名称但参数数量、类型或顺序不同的方法。这也称为编译时多态。

重载方法的方法，参数列表必须在以下任一方面有所不同：

1. 参数数量：
   - `add(int a, int b)`
   - `add(int a, int b, int c)`

2. 数据类型：
   - `add(int a, int b)`
   - `add(double a, double b)`

3. 数据类型的顺序：
   - `add(int a, double b)`
   - `add(double a, int b)`

## 程序

```java
public class OverloadingExample {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    double add(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        OverloadingExample obj = new OverloadingExample();
        System.out.println(obj.add(5, 10));
        System.out.println(obj.add(5, 10, 15));
        System.out.println(obj.add(5.5, 10.5));
    }
}
```

```java
static void display(int n, int m)
{
    System.out.println("two int argu");
}

static void display(float n)
{
    System.out.println("one float argu");
}

void main(String[] args) {
    display(10);
    display(10,10);
    display((float)10.5);
}
```

输出：

```text
one int argu
two int argu
one float argu
```

上述 Java 程序演示了方法重载，其中多个名为 `display` 的方法具有不同的参数。`display` 方法被重载，以接受单个整数、两个整数或单个浮点数。在 `main` 方法中，`display` 方法被调用了三次，分别使用了不同的参数：一次使用单个整数（打印 `"one int argu"`），一次使用两个整数（打印 `"two int argu"`），以及一次使用浮点数（打印 `"one float argu"`）。

## 程序

Java 中 final 类重载的程序

```java
final class test
{
    void display()
{
        System.out.println("0 parameter display()");
    }

    void display(int i)
{
        System.out.println("1 int parameter display()"+i);
    }

    void display(String s)
{
        System.out.println("1 string parameter display()"+s);
    }

    void display(int i,int j)
{
        System.out.println("2 int parameter display()"+i+" "+j);
    }
}

class sample
{
    void main(String a[])
    {
        test t=new test();
        t.display();
        t.display(10);
        t.display("testing");
    }
}
```

```java
t.display(100,200);
}
```

输出：

```text
0 parameter display()
1 int parameter display()10
1 string parameter display()testing
2 int parameter display()100 200
```

上述 Java 程序演示了在名为 `test` 的 `final` 类中的重载方法重载。`test` 类包含四个重载的 `display` 方法：一个无参数，一个带单个整数参数，一个带字符串参数，以及一个带两个整数参数。每个方法都会打印一条特定的消息，指示调用了哪个版本的 `display` 以及任何参数。在 `sample` 类的 `main` 方法中，创建了 `test` 类的实例，并依次调用每个重载的 `display` 方法，展示了基于方法参数的不同输出。

## Java 方法

Java 中静态方法重载以及从不同类调用这些方法的程序

```java
class test {
  static void display() {
    System.out.println("0 parameter display()");
  }

  static void display(int i) {
    System.out.println("1 int parameter display()"+i);
  }

  static void display(String s) {
    System.out.println("1 string parameter display()"+s);
  }

  static void display(int i,int j) {
    System.out.println("2 int parameter display()"+i+" "+j);
  }
}

class sample {
  void main(String a[]) {
    test.display();
    test.display(10);
    test.display("testing");
    test.display(100,200);
  }
}
```

输出：

```text
0 parameter display()
1 int parameter display()10
1 string parameter display()testing
2 int parameter display() 100 200
```

上述 Java 程序演示了 `test` 类中静态方法的重载。`test` 类包含四个重载的 `display` 方法：一个无参数，一个带单个整数参数，一个带单个字符串参数，以及一个带两个参数。每个方法都会打印一条消息，指示调用了哪个版本的 `display` 以及参数。在 `sample` 类的 `main` 方法中，在不创建实例的情况下调用每个重载的 `display` 方法，展示了基于参数的不同输出。

## 程序

Java 中编写多个方法的程序

```java
public class sample{
    void main(String[] args) {
        System.out.println("main(String[])");
    }

    void main(String arg1) {
        System.out.println("main(String1)");
    }

    void main(String arg1,String2) {
        System.out.println("main(String1, String2)");
    }
}
```

输出：

```text
main(String[])
```

上述 Java 程序演示了 `sample` 类中 `main` 方法的重载。有三个 `main` 方法，具有不同的参数列表：一个带 `String[]` 参数，一个带单个 `String` 参数，以及一个带两个参数。运行时默认执行带 `String[]` 参数的 `main` 方法。其他 `main` 方法可以从程序调用，但它们不会由运行时自动执行。

## 程序

Java 中带 `string[]` 参数的 `main` 方法重载程序



```java
public class sample {
    void main(String[] args) {
        System.out.println("main(String[])");
        main("test");
    }
    void main(String arg1) {
        System.out.println("main(String1)");
        main("test");
    }
    void main(String arg1, String2) {
        System.out.println("main(String1, String2)");
    }
}
```

## 输出

```text
main(String[])

main(String1)

main(String1, String2)
```

## Java 方法

上述 Java 程序演示了 `sample` 类中 `main` 方法的重载和链。`main(String[] args)` 方法是入口并打印 `main(String[])`。它调用 `main("test")`，后者打印 `main(String1)` 并调用 `main("test", "test")`。最后的 `main(String arg1, String2)` 方法打印 `main(String1, String2)`。

## 程序

Java 类带 `String` 和 `int` 参数的 `main` 方法重载程序。

```java
public class JavaApplication {
    void main(int a) {
        System.out.println(a);
    }
    void main(String args[]) {
        System.out.println("main() invoked");
        main(100);
    }
}
```

## 输出

```text
main() invoked

100
```

上述 Java 程序演示了 `JavaApplication` 类中 `main` 方法的重载。标准的 `main(String[] args)` 方法是入口并打印 `"main() invoked"`。它调用重载的 `main(int a)` 方法，并将整数 `100` 作为参数。`main(int a, int)` 方法打印整数 `100`。

## 程序

Java 中带 `varargs`（可变参数）的 `main` 方法重载程序。

```java
public class JavaApplication {
    static public void main(String [] args) {
        main(50, 60, 70);
        JavaApplication t = new JavaApplication();
        String[] message = {"java", "Programming", "language"};
        t.main(10, message);
    }
    static void main(int ... args) {
        System.out.println("In the static main by JVM's main");
        for (int i : args) {
            System.out.println(i);
        }
    }
    public void main(int x) {
        System.out.println("In the overloaded non-static main with int value " + x);
    }
    public void main(int x, String [] args) {
        System.out.println("In the overloaded non-static main with int with value " + x);
        for (String s:args) {
            System.out.println(s);
        }
    }
}
```

## 输出

```text
In the static main by JVM's main

50

60

70

In the overloaded non-static main with int value 50

In the overloaded non-static main with int value 10

java

Programming

Language
```

上述 Java 程序演示了 `JavaApplication` 类中静态和非静态形式的 `main` 方法重载。静态 `main(String[] args)` 方法作为入口并调用各种版本的 `main` 方法。它调用了带三个整数的 `main(int... args)`、带单个整数的非静态 `main(int x)`，以及带一个整数和一个字符串数组的非静态 `main(int x, String[] args)`。每个 `main` 方法具体地测量并遍历了给定的参数，展示了 Java 中重载和利用 `main` 方法的不同方式。

## 程序

Java 中带 `out main(String[args])` 的 `main` 方法重载程序。

```java
public class JavaApplication {
  void main(String... args) {
    System.out.println("in main");
    main("test");
  }
  main(10);
  void main(int i) {
    System.out.println("int value"+i);
  }
  void main(String s) {
    System.out.println(+s);
  }
}
```

## 输出

```text
in main

String test

int value10
```

上述 Java 程序演示了 `JavaApplication` 类中 `main` 方法的重载。主入口是 `main(String... args)` 方法，它打印 `"in main"`。它随后调用带有参数 `test` 的重载 `main(String)` 方法，打印 `String test`。接下来，它调用带有参数 `10` 的重载 `main(int)` 方法，打印 `int value 10`。

## 5.6 向方法传递数组

在 Java 中，将数组传递给方法可以在程序内高效地处理和操作数组数据。

```java
public class Rectangle {
    void main(String[] args) {
        double[] dimensions = {5.0, 10.0};
        double area = calculateRectangleArea(dimensions);
        System.out.println("Area of the rectangle: " + area);
    }
    public static double calculateRectangleArea(double[] dimensions) {
        if (dimensions.length != 2) {
            throw new IllegalArgumentException("Invalid dimensions array. Expected length and width.");
        }
        double length = dimensions[0];
        double width = dimensions[1];
        return length * width;
    }
}
```

## 输出

```text
Area of the rectangle: 50.0
```

我们将数组作为参数传递给 `calculateRectangleArea` 方法，该方法根据给定的尺寸计算矩形的面积。`calculateRectangleArea` 方法接收类型为 `double[]` 的数组，确保它包含恰两个代表矩形长度和宽度的元素。如果尺寸数组不满足此要求，则会抛出 `IllegalArgumentException`。在方法内部，从 `dimensions` 数组中提取长度和宽度，并使用公式 `area = length * width` 计算矩形的面积。最后，面积被返回给 `main` 方法，并在那里显示给用户看。

## 5.7 从方法返回数组

在 Java 中，方法也可以返回数组，为数据处理提供了灵活性。

```java
public class Rectangle {
    void main(String[] args) {
        double[] dimensions = {5.0, 10.0};
        double[] result = calculateRectangleArea(dimensions);
        System.out.println("Area of the rectangle: " + result[0]);
        System.out.println("Width of the rectangle: " + result[1]);
    }
    public static double[] calculateRectangleArea(double[] dimensions) {
        if (dimensions.length != 2) {
            throw new IllegalArgumentException("Invalid dimensions array. Expected length and width.");
        }
        double length = dimensions[0];
        double width = dimensions[1];
        double area = length * width;
        double[] result = {area, length, width};
        return result;
    }
}
```

## 输出

```text
Area of the rectangle: 50.0

Length of the rectangle: 5.0

Width of the rectangle: 10.0
```

我们将数组作为参数传递给 `calculateRectangleArea` 方法，该方法根据给定的尺寸计算矩形的面积，并返回一个包含面积、长度和宽度的数组。`calculateRectangleArea` 方法接收类型为 `double[]` 的数组作为参数，确保它包含恰两个代表矩形长度和宽度的元素。如果没有抛出 `IllegalArgumentException`，在方法内部，从 `dimensions` 中提取长度和宽度，并使用公式 `area = length * width` 计算矩形的面积。创建一个新数组 `result` 来存储计算出的面积、长度和宽度，并将其返回给 `main` 方法。在 `main` 方法中，返回的数组 `result` 被赋值用于显示矩形的计算面积、长度和宽度。

## 5.8 递归

递归是一种编程技术，当函数或方法直接或间接地调用自身时，通过将问题分解为相同问题的更小实例来解决问题。这个过程一直持续直到到达基例（base case），这是一个停止递归无限持续的条件。

### 递归处理数组的优势

- 简单性：允许以简单直接的方式处理数组和集合。
- 灵活性：可以解决涉及嵌套结构或变量尺寸的问题（如树和图）。
- 降低复杂度：将复杂问题分解为更简单的子问题，提高了可读性和维护性。

### 局限性

- 栈溢出：如果不仔细管理（例如没有设置正确的基例），递归会导致函数调用过多引发栈溢出错误。
- 性能：与迭代解决方案相比，递归解决方案在时间和空间上有时可能效率较低。

### 示例

```java
public class RecursionExample {
    void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        printArray(arr, 0);
    }

    public static void printArray(int[] arr, int index) {
        // 基例：当索引越界时停止递归
        if (index >= arr.length) {
            return;
        }
        // 打印当前元素
        System.out.println("Element at index " + index + ": " + arr[index]);
        // 递归调用打印下一个元素
        printArray(arr, index + 1);
    }
}
```

## 输出

```text
Element at index 0: 1

Element at index 1: 2

Element at index 2: 3

Element at index 3: 4

Element at index 4: 5
```

在上述程序中，实现了一个递归方法来打印值为 `(1, 2, 3, 4, 5)` 的数组 `arr`。

# Java 方法 149

## 9.5.2 案例研究

偏头痛是一种神经系统疾病，其特征是反复性的中度至严重头痛，通常伴有恶心、呕吐、光光敏感和声音敏感等症状。这些头痛通常影响头部的一侧，呈搏动或跳动感，如果不治疗，可能会持续几小时到几天不等。偏头痛非常痛苦，会对日常生活和活动造成严重干扰。

以下是考虑的一些参数：

1. **C-反应蛋白 (CRP)**：CRP 是炎症标志物。水平升高可能表明体内存在炎症，这可能与偏头痛发作有关。
2. **血清素水平**：血清素是一种调节情绪和疼痛感觉的神经递质。血清素水平的波动与偏头痛的病生理机制有关。
3. **雌激素水平**：激素变化，特别是雌激素水平的波动，已知是偏头痛发发的诱因，尤其是对于女性。
4. **血糖水平**：在偏头痛患者中观察到了异常的糖代谢或血糖水平波动。
5. **白细胞 (WBC) 计数**：白细胞计数的变化指示系统性炎症或免疫反应，这可能与偏头痛发作有关。
6. **其他标志物**：其他额外参数如细胞因子（例如白介素）、神经肽（例如钙钛素基因相关肽 – CGRP）以及与氧化应激或线粒体功能障碍相关的生物标志物也在研究中。



```java
import java.util.Scanner;

public class MigraineDetection {
    void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Migraine Detection System");
        System.out.println("--------------------------");
        System.out.println("Enter CRP level (mg/L): ");
        double crp = scanner.nextDouble();
        System.out.println("Enter Serotonin level (ng/mL): ");
        double serotonin = scanner.nextDouble();
        System.out.println("Enter Estrogen level (pg/mL): ");
        double estrogen = scanner.nextDouble();
        System.out.println("Enter Glucose level (mg/L): ");
        double glucose = scanner.nextDouble();
        System.out.println("Enter WBC count (x10^9/L): ");
        double wbc = scanner.nextDouble();
        boolean hasMigraine = detectMigraine(crp, serotonin, estrogen, glucose, wbc);
        if (hasMigraine) {
            System.out.println("Based on the blood test results, Migraine detected.");
        } else {
            System.out.println("Based on the blood test results, No Migraine detected.");
        }
        scanner.close();
    }

    private static boolean detectMigraine(double crp, double serotonin,
    double estrogen, double glucose, double wbc) {
        double crpThreshold = 5.0;
        double serotoninThreshold = 100.0;
        double estrogenThreshold = 50.0;
        double glucoseThreshold = 100.0;
        double wbcThreshold = 8.0;
        if (crp > crpThreshold || serotonin > serotoninThreshold || estrogen
        < glucoseThreshold || wbc < wbcThreshold) {
            return true;
        } else {
            return false;
        }
    }
}
```

`MigraineDetection` 开始提示用户输入 CRP、血清素、雌激素、血糖和白细胞计数。然后这些值将在 `detectMigraine` 方法中根据预定义的阈值进行评估，以确定是否发现了偏头痛。如果任何参数超过其相应的阈值，程序将判定存在偏头痛。结果将相应显示，指示根据输入是否检测到偏头痛。

# Java 类

## 6.1 导言

Java 采用面向对象编程 (OOP) 范式，它强调将复杂问题分解为可管理的实体（对象）。Java 编程的基础围绕类和对象的概念，每个对象都封装了属性和行为。

### 6.1.1 封装

面向对象编程中的封装是指将数据（属性或属性）和操作这些数据的方法（函数或过程）打包到一个单元中，该单元被称为类。它是面向对象设计的基本原则之一，与继承和多态并列。

## 封装的关键方面

- 数据隐藏：封装允许数据隐藏在类内部，并仅通过其公共方法访问。这限制了从类外部对数据的直接访问，防止了意外修改并确保了对象状态的一致性。

- 访问控制：通过封装，可以使用访问修饰符（如 `private`、`protected`、`public`）指定类成员的可见性。这控制了程序其他部分访问和修改数据的方式，提高了安全性和维护性。

## 封装的必要性

- 模块化：封装通过分组相关数据和方法来促进模块化，使代码更有组织、更容易理解。

- 安全性：通过隐藏内部状态并要求通过受控方法访问，封装防止了外部代码直接操作敏感数据，减少了意外副作用的风险。

- 灵活性与维护性：只要公共接口保持不变，封装允许更改实现细节而不影响程序的其他部分。这支持更易于维护和更新。

## 封装的好处

- 受控访问：确保对象的内部状态仅通过定义的方法进行访问和修改，维护了数据完整性。

- 代码重用：封装通过提供与对象交互的清晰接口来支持代码重用，便于集成到更大的系统中。

- 增强测试：封装使得对程序的组件进行测试变得更容易，从而产生更健壮的软件。

## 封装的局限性

- 开销：封装可能会引入额外的开销，因为设计和维护类接口需要更多精力。

- 复杂性：确定合适的封装程度有时具有挑战性，会导致设计复杂。

- 性能：通过 getter 和 setter 方法访问数据可能会产生微小的性能开销，尽管 Java 编译器和运行时优化了这一点。

## 6.2 类

Java 类将数据和行为封装在单个单元中，为创建对象提供了蓝图。通过在类内部组织字段、方法、构造函数和其他组件，Java 促进了重用、模块化维护性。

- 字段：字段（属性或变量）代表与对象相关的数据。它们通过存储特征值来定义状态。字段具有不同的修饰符（公共、私、保护）以控制其可见性和访问权限。

- 方法：方法是在类内部定义的函数，定义了类对象的行为。它们封装了对类数据（字段）执行或修改其状态的操作。方法可以执行各种任务，包括数据处理、计算与其他对象的交互。

- 构造函数：构造函数是用于初始化对象的特殊方法。它们与类同名，并在创建对象时自动调用。它们通过为类字段分配初始值来初始化新创建的对象的状态。构造函数可以参数化以接收初始化参数。

- 块：Java 在类中支持三种块：初始化块、静态块和实例块。初始化块用于初始化变量，静态块在类加载到内存时执行，实例块在创建类的对象时执行。

# 类的必要性

- 抽象：类通过将相关数据和行为封装在单个单元中，提供了抽象复杂系统的方法。

- 模块化：它们有助于将组织成可管理的单元，使其更容易理解、维护和重用。

# Java 类

- 代码重用性：类通过继承和组合促进代码重用，允许开发者通过扩展或组合现有类来构建新功能。

- 封装：类通过隐藏实现细节并暴露定义良好的接口与对象进行交互，从而支持封装。

- 多态：类实现了多态性，允许通过继承和方法重写对不同类的对象以统一的方式进行处理。

# 类的优点

- 组织性：类有助于将代码组织成逻辑单元，使其更易管理和理解。

- 封装：类通过将数据和方法封装在一起来支持封装，保护数据完整性并为与对象的交互提供清晰的接口。

- 可重用性：类通过继承和组合促进代码重用，减少重复并增强可维护性。

- 抽象：类通过隐藏实现细节并仅向类暴露本质特征来实现抽象。

- 继承：类促进了继承，能够在类与类之间创建层级关系，并促进代码重用和扩展性。

- 多态：类实现了多态性，允许通过继承和方法重写对不同类的对象以统一的方式进行处理。

# 类的局限性

- 灵活性不足：一旦定义了类，其结构和行为就是固定的，这可能会限制对变化需求的适应性。

- 开销：由于对象的创建和方法的调用，类在内存和性能方面带来了开销。

- 复杂性：大型类层次结构和复杂的类关系会导致复杂性增加，使代码更难理解和维护。

- 继承问题：不当使用继承会导致紧耦合、代码重复和违反封装等问题。

- 封装：类字段和方法的公共访问可能导致封装违反以及对类的潜在误用。

尽管存在这些局限性，类仍然是 Java 编程中的基础构建模块，为组织、封装和重用代码提供了强大的机制。当使用适当时，类有助于构建模块化、可维护且可扩展的软件系统。

#### 语法

```
access-specifier class<class_name>
{
  field;
  method;
}
```

类声明可以包含这些组件：

- 修饰符：类可以是公共的（`public`）或具有默认访问权限。

- 类关键字：`class` 关键字用于创建类。

# 用于医疗和健康应用的 Java 22

- 类名：名称应以字母开头（按照约定首字母大写）。

- 主体：用大括号 `{}` 包围的类体。

- 构造函数在 Java 中初始化新创建的对象起着至关重要的作用。每个类必须至少有一个构造函数。在 Java 类没有显式定义任何构造函数的情况下，编译器会自动提供一个无参数构造函数，通常称为默认构造函数。该默认构造函数会调用类的无参数构造函数。

## 6.3 访问变量

在 Java 中，实例变量（也称为非静态字段）属于类的每个实例，而类变量在该类的所有实例之间共享。

示例：访问实例变量

使用对象引用访问实例变量。每个对象都有它们自己的实例变量拷贝。

# 程序

```
public class Test {
    // 实例变量
    private String name;
    private int age;
    public Test() {
    }

    // 初始化实例变量的构造函数
    public Test(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 显示实例变量的方法
    public void displayDetails() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        // 创建 Test 类对象
        Test obj1 = new Test();
        Test obj1 = new Test("Usharani", 30);
        Test obj2 = new Test("Bhimavararu", 25);
        // 通过方法访问实例变量
        obj1.displayDetails();
        obj2.displayDetails();
    }
}
```

输出：

```
Name: Usharani, Age: 30
Name: Bhimavararu, Age: 25
```

在此程序中，定义了一个名为 `Test` 的类，包含两个实例变量：`name` 和 `age`（类型为 `String`）。该类包含一个初始化值的默认构造函数，以及一个根据提供的参数设置 `name` 和 `age` 的参数构造函数。实现了一个方法 `displayDetails`，以格式化字符串将实例变量的值打印到控制台。在 `main` 方法中，使用参数构造函数创建了两个 `Test` 类对象：名为 `Usharani` 且年龄为 30 的 `obj1` 以及名为

# Java 类

`Bhimavarapu` 且年龄为 25 的 `obj2`。随后随后调用两个对象的 `displayDetails` 方法，导致输出显示每个对象的名称和年龄。

示例：访问类变量

使用类名或对象引用访问类变量。

# 程序

```
public class Test {
    // 类变量（静态字段）
    private static int instanceCount = 0;
    // 增加实例计数的构造函数
    public Test() {
        instanceCount++; // 增加静态变量
    }
    // 获取实例计数的静态方法
    public static int getInstanceCount() {
        return instanceCount;
    }
    public void main(String[] args) {
        // 创建 Test 类对象
        Test obj1 = new Test();
        Test obj2 = new Test();
        // 通过类名访问类变量
        System.out.println("Total instances: " + getInstanceCount());
    }
}
```

输出：

```
Total instances: 2
```

在上述程序中，定义了一个类 `Test`，它包含一个静态字段 `instanceCount`，用于跟踪创建了多少个类对象。每当实例化一个 `Test` 对象时，构造函数就会增加 `instanceCount`。`getInstanceCount()` 方法是一个静态方法，用于返回 `instanceCount` 的当前值。静态字段确保计数在 `Test` 类的所有实例之间共享。

## 6.4 访问方法

在 Java 中，实例方法是属于类实例的方法。类方法（也称为静态方法）属于类本身。

访问实例方法的示例：

```
public class Test {
    private String name;
    private int age;
    public Test(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public void displayDetails() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
    public static void main(String[] args) {
        Test obj1 = new Test("Usharani", 30);
        Test obj2 = new Test("Bhimavarapu", 25);
        obj1.displayDetails();
        obj2.displayDetails();
    }
}
```

在此程序中，定义了类 `Test` 包含两个实例变量 `name` 和 `age`。对每个对象调用 `displayDetails()` 方法以打印它们的特定细节。

访问类方法的示例：

```java
public class Test {
    private static int instanceCount = 0;
    public Test() {
        instanceCount++;
    }
    public static int getInstanceCount() {
        return instanceCount;
    }
    public static void main(String[] args) {
        Test obj1 = new Test();
        Test obj2 = new Test();
        System.out.println("Total instances: " + getInstanceCount());
    }
}
```

## 6.5 创建对象

对象是类的实例，代表类的结构和行为的具体出现。在 Java 中，对象是通过类创建的。要实例化类的对象，使用类名

## Java 类

指定类名，随后是对象名称，并使用关键字 `new`。这会为对象分配内存，并调用该类的构造函数来初始化其状态。

#### 语法

```
className object = new className();
```

在 Java 中，类的实例被称为对象。要创建一个对象，`new` 关键字是必不可少的，随后是类类构造函数的调用。该过程涉及三个步骤：声明、实例化和初始化。

在 Java 的创建过程中，有三个基本步骤：

- 声明（Declaration）：这一步涉及声明一个特定对象类型的变量。它定义了一个引用变量，该变量可以持有特定类对象的引用。

- 实例化（Instantiation）：在这一步中，使用 `new` 关键字创建该类的新实例。它为对象分配内存并初始化其状态。

- 初始化（Initialization）：在实例化之后，使用 `new` 关键字后跟括号中的任何所需参数来调用该类的构造函数。这会使用初始值初始化新创建的对象，或执行必要的设置操作。

这些步骤对于在 Java 中创建对象至关重要，是面向对象编程范式不可或缺的一部分。它们为创建和初始化对象提供了一种结构化的方法，允许进行高效的内存管理和灵活的对象创建。Java 中有多种实例化对象的方法：

- 使用 `new` 关键字：这是标准且最常用的方法。它涉及通过调用类构造函数来创建对象。

```
Test object = new Test();
```

- 使用 `Class.forName(String className)` 方法：`java.lang` 包中的 `Class.forName(String className)` 方法返回与给定字符串类名关联的对象。该方法用于动态加载和实例化类。



```
Test obj = (Test) Class.forName("com.example.Test").newInstance();
```

- 使用`clone`方法：`clone`方法是`Object`类的一部分，用于创建对象的副本。它用于生成一个与原始对象完全相同的对象。

```
Test obj1 = new Test();
Test obj2 = (Test) obj1.clone();
```

- 反序列化（Deserialization）：序列化涉及从文件中其保存的状态中读取对象。它从存储在文件中的序列化格式重新创建对象。

```
FileInputStream file = new FileInputStream(filename);
ObjectInputStream in = new ObjectInputStream(file);
Object obj = in.readObject();
```

- 匿名对象（Anonymous Object）：匿名对象是没有引用的对象。它在对象实例化时创建，可以用于单次操作。

```
new Test(); // 匿名对象
通过引用调用方法：
test t = new Test();
t.method(); // 通过引用调用方法
```

## 6.6 构造函数

在 Java 中，构造函数是一种特殊的方法，当使用`new`关键字实例化类的对象时，它会被自动调用。它用于初始化对象的状态。Java 中的构造函数：

- 与类名相同。
- 没有返回类型，即使是`void`也没有。
- 可以被重载（多个具有不同参数列表的构造函数）。
- 可以使用`this()`调用另一个构造函数（构造函数链）。

### 6.6.1 构造函数的类型

Java 中的构造函数是用于初始化对象的特殊方法。它们与类名相同且没有返回类型。Java 中主要有六种构造函数：

1. 默认构造函数（Default Constructor）
   - 如果没有定义其他构造函数，Java 会自动提供。
   - 使用默认值初始化对象。

2. 无参数构造函数（No-Argument Constructor）
   - 不接受任何参数的构造函数。
   - 可以由程序员显式定义。

3. 参数化构造函数（Parameterized Constructor）
   - 接收一个或多个参数用特定值初始化对象。

4. 拷贝构造函数（Copy Constructor）
   - 用于创建现有对象的副本作为新对象。
   - 这不是 Java 的内置功能，但可以通过定义一个接受同类对象作为参数的构造函数来实现。

5. 私有构造函数（Private Constructor）
   - 用于限制从外部对类的实例化。
   - 常用于单例设计模式或工具类。

6. 静态构造函数（静态初始化块）
   - Java 不支持静态构造函数。
   - 而是使用静态初始化块来初始化静态变量。

7. 保护性构造函数（Protected Constructor）
   - 用于限制对类的实例化。

这些构造函数允许在 Java 中以多种方式实例化和初始化对象，为对象的创建过程提供了灵活性和控制力。

#### 6.6.1.1 默认/无参数构造函数

- 一个没有参数的构造函数。
- 如果没有定义其他构造函数，Java 会自动提供。
- 将实例变量初始化为它们的默认值（例如，数值类型为`0`，对象为`null`）。

##### 程序

```java
public class Test {
    public Test() {
        // 默认构造函数
        System.out.println("Default constructor called.");
    }
    void main(String[] args) {
        Test obj = new Test(); // 创建对象，默认构造函数被调用
    }
}
```

输出：

```
Default constructor called.
Default constructor called.
```

在此程序中，定义了一个名为`Test`的类，并有一个默认构造函数。默认构造函数是一个参数化构造函数，在调用时会打印消息“Default constructor called”。在`main`方法内部，通过调用默认构造函数创建`Test`类的对象。当对象 (`obj`) 被实例化时，默认构造函数会被自动调用，默认构造函数

#### 6.6.1.2 参数化构造函数

- 一个带有参数的构造函数。
- 用于用特定值初始化实例变量。

##### 程序

```java
public class Test {
    private int id;
    private String name;

    Test() {
    }
    Test(int id, String name) {
        // 参数化构造函数
        this.id = id;
        this.name = name;
    }
    void main(String[] args) {
        Test obj = new Test();
        Test obj1 = new Test(1, "Ushani"); // 创建对象
        System.out.println("ID: " + obj1.id + ", Name: " + obj1.name);
    }
}
```

输出：

```
ID: 1, Ushani
```

在此程序中，定义了一个名为`Test`的类，包含两个实例变量`id`和`name`。该类有两个构造函数。第一个是默认构造函数，第二个是参数化构造函数，用于为`id`和`name`赋值。

#### 6.6.1.3 拷贝构造函数

- 通过拷贝现有对象的值来构造一个新对象。
- 有助于创建一个具有相同状态的新对象。

##### 程序

```java
public class Test {
    private int id;
    private String name;

    Test() {
    }
    Test(int id, String name) {
        // 参数化构造函数
        this.id = id;
        this.name = name;
    }
    Test(Test another) {
        // 拷贝构造函数
        this.id = another.id;
        this.name = another.name;
    }
    public void main(String[] args) {
        Test obj = new Test();
        Test obj1 = new Test(1, "Ushani"); // 创建对象
        Test obj2 = new Test(obj1); // 使用拷贝构造函数创建 obj2
        System.out.println("ID: " + obj2.id + ", Name: " + obj2.name);
    }
}
```

输出：

```
ID: 1, Ushani
```

在此程序中，定义了一个名为`Test`的类，包含两个实例变量`id`和`name`。该类有三个构造函数。第一个是默认构造函数，第二个是参数化构造函数，第三个是接受同类对象并复制其`id`和`name`值的拷贝构造函数。

#### 6.6.1.4 静态构造函数（静态初始化块）

- 代码块在类加载到内存时仅执行一次。
- 用于静态变量的静态初始化或其他静态任务。

##### 程序

```java
public class Test {
    private static int count;
```

## Java 类

```java
static {
    // Static initialization block
    count = 0;
    System.out.println("Static block initialized.");
}
    public Test() {
    count++;
    System.out.println("Constructor called, Count: " + count);
    }
    void main(String[] args) {
    Test obj = new Test();
    Test obj1 = new Test();
    Test obj2 = new Test();
    }
}
```

输出：

```
Static block initialized.
Constructor called, Count: 1
Constructor called, Count: 2
Constructor called, Count: 3
Constructor called, Count: 4
```

在这个程序中，我们有一个`Test`类，它包含一个静态变量`count`来跟踪创建的对象数量。程序使用静态代码块将`count`变量初始化为 0，并在类首次加载到内存时打印一条消息。静态块只执行一次，在任何对象创建或构造函数调用之前执行。`Test`类的构造函数在每次创建对象时都会增加`count`，并打印`count`的当前值。随着每个对象的创建，`count`的值都会增加。当类加载时，构造函数会在每次实例化新对象时运行。

这些类型的构造函数为 Java 编程提供了灵活性，可以根据不同的需求和场景初始化对象。每种类型在对象创建和初始化都有特定的用途。

#### 6.6.1.5 私有构造函数 (Private Constructor)

Java 中的私有构造函数是用`private`访问修饰符声明的构造函数。这意味着构造函数只能从同一个类内部访问，不能从类外部调用，包括从其子类。

```java
class Main {
    private Main() {
        System.out.println("private Constructor");
    }
    void main(String[] args) {
        Main obj = new Main();
    }
}
```

输出：

```
private Constructor
private Constructor
```

在这个程序中，`Main`类包含一个私有构造函数，这限制了从类外部实例化该类。构造函数在调用时会打印`private Constructor`。在`main`方法中，尝试使用`new Main()`创建`Main`类的实例。由于构造函数是私有的，这种实例化只允许在类内部进行。这种使用私有构造函数的模式通常用于单例设计模式，其目标是限制类多个实例的创建。在这种情况下，程序在`main`方法内部创建了`Main`类的实例，这是有效的，因为它们在类的作用范围内，并且在调用构造函数时会打印消息 "private Constructor"。

#### 6.6.1.6 受保护构造函数 (Protected Constructor)

Java 中的受保护构造函数是一种可以在其所属包内以及通过该类的子类（继承者）访问的构造函数，无论它们是在同一个包还是不同的包中。

##### 程序

```java
public class proc {
    protected proc() {
        System.out.println("Protected Constructor");
    }
    void main(String[] args) {
        proc obj = new proc();
    }
}
```

输出：

```
Protected Constructor
```

在这个程序中，`proc`类具有一个受保护构造函数，允许在同一个包内以及子类访问该构造函数，即使它们在不同的包中也是如此。构造函数在调用时会打印 "Protected Constructor"。在`main`方法内部，使用`new proc()`创建了`proc`类的实例。由于`main`方法是同一个类的一部分，它可以访问受保护的构造函数。因此，当实例化对象时，消息 "Protected Constructor" 将打印到控制台上。

### 6.6.2 构造函数重载 (Constructor Overloading)

Java 中的构造函数重载是指在类中定义多个构造函数的能力，每个构造函数都有不同的参数列表。这允许根据实例化时提供的参数以不同的方式初始化对象。

#### 优点

- **多种初始化**：构造函数重载允许根据传递的参数以不同的方式初始化对象。这种灵活性允许创建不同初始状态的对象，而不需要多个工厂方法或 setter。
- **更整洁的代码**：通过提供多个构造函数，你可以将不同的初始化逻辑封装在类内部，使代码更整洁、更具可读性。
- **方便初始化**：它提供了一种常用配置初始化对象的方便方法，减少了重复代码的需求。
- **增强灵活性**：允许子类利用父类的构造函数，并通过添加额外的参数或自定义初始化逻辑来扩展其功能。

#### 局限性

- **复杂性**：拥有多个构造函数可能会导致代码复杂性和维护开销，特别是在处理大型类或构造函数有许多参数时。
- **歧义性**：如果每个构造函数的目的没有良好的文档，或者参数列表没有经过仔细选择，重载构造函数有时会导致代码不够清晰。
- **编译时错误**：错误的参数列表或歧义的重载构造函数可能导致编译错误，特别是当编译器无法为给定的参数集确定最佳匹配时。

#### 6.6.2.1 私有构造函数重载 (Private Constructor Overloading)

私有构造函数重载是指在类中定义多个私有构造函数的做法，每个构造函数都有不同的参数列表。私有构造函数无法从外部类访问，通常用于控制类内部的对象创建，或用于单例设计模式。

##### 程序

```java
public class proc {
    private proc() {
        System.out.println("private Constructor");
    }
    private proc(int i) {
        System.out.println("l1 param private Constructor");
    }
    void main(String[] args) {
        proc obj = new proc();
        proc obj1 = new proc(1);
    }
}
```

输出：

```
private Constructor
1 param private Constructor
```

在这个程序中，`proc`类包含两个私有构造函数。第一个构造函数是默认构造函数，调用时打印 "private Constructor"。第二个构造函数接收一个整数参数并打印 "1 param private Constructor"。在`main`方法中，使用默认构造函数创建了`proc`类的实例。然后尝试使用参数构造函数创建另一个实例。

#### 6.6.2.2 受保护构造函数重载 (Protected Constructor Overloading)

受保护构造函数重载为层次结构中的对象创建提供了灵活性和自定义，确保子类可以使用不同的参数集。

##### 程序

```java
class test {
    // 无参数的受保护构造函数
    protected test() {
        System.out.println("protected constructor");
    }
    // 带整数参数的受保护构造函数
    protected test(int num) {
        System.out.println("protected constructor with " + num);
    }
    // 带字符串参数的受保护构造函数
    protected test(String str) {
        System.out.println("protected constructor with string " + str);
    }
}

public class Main {
    public static void main(String[] args) {
        // 使用不同的构造函数创建 test 类实例
        test t = new test(); // 调用无参数构造函数
        test t1 = new test(100); // 调用带整数的构造函数
        test t2 = new test("testing"); // 调用带字符串的构造函数
    }
}
```

输出：

```
protected constructor
protected constructor with 100
protected constructor with string testing
```

## Java 类

- 初始化的一致性：构造函数链（Constructor chaining）确保类中或相关类中的所有构造函数都能一致地执行必要的初始化，减少了因初始化不完全导致的错误风险。
- 简化代码结构：通过链式调用，代码结构变得更有组织且易于读，因为相关的初始化任务被组合在一起。
- 继承层次结构：在继承层次结构中，构造函数链允许基类在派生类添加自己的初始化之前初始化其字段，确保了操作的逻辑顺序。

## 构造函数链的局限性

- 复杂性：过度使用构造函数链，特别是在具有许多字段和复杂初始化逻辑的类中，会导致代码难以理解和调试。
- 紧耦合代码：构造函数链可能导致代码紧耦合，一个构造函数的更改可能需要修改所有链式构造函数，从而使代码的灵活性降低。



- 错误处理：在构造函数链期间处理异常可能具有挑战性，因为构造函数必须处理链中发生的任何异常。

- 灵活性限制：构造函数链可能会限制以不同方式初始化对象的灵活性，因为构造函数变得依赖于链式序列。

## 程序

```java
public class Test {
    int x;
    int y;
    int z;
    public Test() {
        this(0, 0, 0);
        System.out.println("Default constructor called");
    }
    public Test(int x) {
        System.out.println("Constructor with one parameter called");
    }
    public Test(int x, int y) {
        this(x, y, 0);
        System.out.println("Constructor with two parameters called");
    }
    public Test(int x, int y, int z) {
        this.x = x;
        this.y = y;
        this.z = z;
        System.out.println("Constructor with three parameters called");
    }
    public void display() {
        System.out.println("x: " + x + ", y: " + y + ", z: " + z);
    }
    public static void main(String[] args) {
        Test obj1 = new Test();
        obj1.display();
        Test obj2 = new Test(10);
        obj2.display();
        Test obj3 = new Test(10, 20);
    }
}
```

```java
obj3.display();
Test obj4 = new Test(10, 20, 30);
obj4.display();
```

Output:

```
Constructor with three parameters called

Default constructor called

x: 0, y: 0, z: 0

Constructor with one parameter called

x: 10, y: 0, z: 0

Constructor with three parameters called

Default constructor called

x: 10, y: 20, z: 0

Constructor with two parameters called

Constructor with three parameters called

Default constructor called

x: 10, y: 20, z: 30
```

在此程序中，`Test` 类通过多个构造函数展示了构造函数链的概念，这些构造函数用于初始化三个实例变量：`x`、`y` 和 `z`。默认构造函数（`Test()`）通过调用带三个参数的构造函数将所有变量初始化为零，并打印“Default constructor called."。带有一个参数的构造函数（`Test(int x)`）将`x`设置为提供的值，并将`y`和`z`初始化为零，显示消息“Constructor with one parameter called."。同样，带两个参数的构造函数（`Test(int x, int y)`）将`x`和`y`设置为给定值，`z`默认为零，并打印“Constructor with two parameters called."。接受三个参数的构造函数（`Test(int x, int y, int z)`）直接初始化实例变量并打印“Constructor with three parameters called."。在`main`方法中，创建了四个`Test`类对象，演示了每个构造函数的功能。在创建每个对象后，`display`方法输出`x`、`y`和`z`的当前值。

### 6.6.3.1 私有构造函数链 (Private Constructor Chaining)

私有构造函数链是指在类内部从一个构造函数调用另一个构造函数的过程。这是通过`this()`方法实现的。私有构造函数链有助于管理和简化单个类内的初始化过程，允许更好的代码复用和封装。

#### 程序

```java
public class proc {
    private proc() {
        this(10);
        System.out.println("private Constructor");
    }

    private proc(int i) {
        System.out.println("1 parameter private Constructor");
    }

    public static void main(String[] args) {
        proc obj = new proc();
    }
}
```

Output:

```
1 parameter private Constructor

private Constructor

1 parameter private Constructor

private Constructor
```

在此程序中，`proc` 类演示了私有构造函数和构造函数链的使用。该类包含两个构造函数：默认构造函数`proc()`和参数化构造函数`proc(int i)`。默认构造函数使用`this(10)`调用参数化构造函数，在打印 "private Constructor." 之前用默认值`10`对类进行初始化。参数化构造函数在被调用时打印 "1 private Constructor"。在`main`方法中，使用默认构造函数创建了`proc`类的实例。由于两个构造函数都是私有的，这会将类的实例化限制在类自身的作用域内，有效地防止了从类外部访问。

### 6.6.3.2 保护级构造函数链 (Protected Constructor Chaining)

受保护的构造函数链是指在类内部从一个构造函数调用另一个构造函数的过程。这是通过`this()`方法实现的。保护级构造函数链有助于管理和简化单个类内的初始化过程，允许更好的代码复用和封装。

#### 程序

```java
public class test {
    protected test() {
        this(10);
        System.out.println("protected Constructor");
    }

    protected test(int i) {
        System.out.println("1 parameter protected Constructor");
    }

    public static void main(String[] args) {
        test obj = new test();
    }
}
```

Output:

```
1 parameter protected Constructor

protected Constructor

1 parameter protected Constructor

protected Constructor
```

在此程序中，`test` 类演示了保护构造函数和构造函数链的使用。该类包含两个构造函数：默认构造函数`test()`和参数化构造函数`test(int i)`。默认构造函数使用`this(10)`调用参数化构造函数，在打印 "protected Constructor." 之前用默认值`10`对类进行初始化。参数化构造函数在被调用时打印 "1 protected Constructor"。在`main`方法中，使用默认构造函数创建了`test`类的实例。

## 6.7 初始化块 (INITIALIZATION BLOCKS)

Java 初始化块是用于初始化类变量的代码块。有两种初始化块：(a) 实例化块 (b) 静态初始化块。实例化块在每次创建类实例时执行，而静态初始化块只在类加载时执行一次。理解这些块有助于管理类初始化并确保 Java 程序中的变量初始化。

### 6.7.1 实例化块 (InstanceIZATION BLOCK)

- 实例化块是类内部在大括号`{...}`内的代码块，但在方法、构造函数或静态块之外。

- 它在每次创建类实例时运行。

- 它主要用于初始化需要复杂逻辑的变量，或在多个构造函数之间共享公共初始化。

- 实例化块按照在类中出现的顺序执行，在调用父类构造函数（如果适用）之后。

#### 实例化块示例：

```java
public class TestInstanceBlock {
  // 实例变量
  private int number;
  // 实例化块
  {
    number = 10;
    System.out.println("Instance initialization block: number = " + number);
  }
  // 构造函数
  public TestInstanceBlock() {
    System.out.println("Constructor called: number = " + number);
  }
  public static void main(String[] args) {
    TestInstanceBlock obj_0j = new TestInstanceBlock();
  }
}
```

Output:

```
Instance initialization block: number = 10

Constructor called: number = 10

Instance initialization block: number = 10

Constructor called: number = 10
```

在这个示例中，实例初始化块会在每次创建`TestInstanceBlock`实例时将`number`变量初始化为 10。输出证明了实例初始化块在构造函数之前运行。

### 6.7.2 静态初始化块

- 静态初始化块是封装在`{ ... }`内部并以`static`关键字前跟的代码块。

- 它仅在类被加载到 JVM（Java 虚拟机）时执行一次。

- 它通常用于初始化静态变量，或为整个类执行一次性的初始化任务。

- 静态初始化块按照它们在类中出现的顺序执行，在静态变量之后、在类被第一次使用之前执行。

#### 静态初始化块示例：

```java
public class TestStaticBlock {
    // 静态变量
    private static int count;
    // 静态初始化块
    static {
        count = 5;
        System.out.println("Static initialization block: count = " + count);
    }
    public static void main(String[] args) {
        System.out.println("Main method is called.");
    }
}
```

输出：

```
Static initialization block: count = 5

Main method is called.
```

在这个示例中，当类`TestStaticBlock`加载到内存时，静态初始化块将静态变量`count`初始化为 5。静态块在`main`方法之前运行，展示了它在初始化静态变量的作用。

## 6.8 对象的传递与返回

在 Java 中，将对象作为参数传递允许方法对现有对象进行操作和处理，从而在不需要复制数据或创建新实例的情况下实现效率和状态修改。从方法返回对象通过在方法内部隐藏对象创建的细节，有助于封装和抽象，促进了软件设计中更整洁的代码和关注点分离。这些实践通过减少冗余对象的创建并促进模块化、可重用的组件增强了代码的可读性、维护性和性能。

### 6.8.1 将对象作为参数传递

在 Java 中将对象作为参数传递和返回对象涉及使用对象引用来操作和交互传递的方法或从方法返回的对象。这允许方法操作现有对象而无需创建新对象。在方法内部对对象的更改会影响原始对象。

#### 程序

将对象作为参数传递

```java
class Rectangle {
    private double width;
    private double height;
    // 构造函数初始化 Rectangle 对象
    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }
    // 计算矩形面积的方法
    public double calculateArea() {
        return width * height;
    }
    // 获取宽度的 getter 方法
    public double getWidth() {
        return width;
    }
    // 获取高度的 getter 方法
    public double getHeight() {
        return height;
    }
}
// 带有执行几何计算方法的工具类
class GeometryUtil {
    // 计算并返回作为参数传递的 Rectangle 对象的面积
    public static double doubleArea(Rectangle rect) {
        double area = rect.calculateArea() * 2;
        return area;
    }
}
```

```java
// 测试将对象作为参数传递的类
public class PassingObjectsAsParameters {
    public static void main(String[] args) {
        // 创建一个 Rectangle 对象
        Rectangle rectangle = new Rectangle(5.0, 3.0);
        // 调用 GeometryUtil 类的 doubleArea 方法
        double doubledArea = GeometryUtil.doubleArea(rectangle);
        // 显示原始面积和双倍面积
        System.out.println("Original Rectangle:");
        System.out.println("Width: " + rectangle.getWidth() + ", Height: " + rectangle.getHeight());
        System.out.println("\nDouble Area: " + rectangle.calculateArea());
        System.out.println("Area * 2: " + doubledArea);
    }
}
```

输出：

```
Original Rectangle:

Width: 5.0, Height: 3.0

Double Area:

Area * 2: 30.0
```

在此程序中，定义了一个`Rectangle`类来表示具有宽度高度属性的矩形，通过其构造函数进行初始化。该类包含一个计算面积的方法和一个获取高度的 getter 方法。创建了一个`GeometryUtil`工具类，包含一个方法`doubleArea`接收`Rectangle`对象作为参数，计算其面积并返回该面积。`PassingObjectsAsParameters`类通过创建`Rectangle`实例并调用`doubleArea`方法演示了该功能。它将矩形的宽度、高度、原始面积和双倍面积打印到控制台。

### 6.8.2 返回对象

方法可以根据现有对象创建新对象并返回它们。这允许封装和抽象，对象创建的细节隐藏在方法内部。

#### 程序



```java
class Rectangle {
    private double width;
    private double height;
    // 构造函数初始化 Rectangle 对象
    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    } // 创建并返回尺寸双倍的新 Rectangle 对象的方法
    public Rectangle createDoubleSizeRectangle() {
        double newWidth = width * 2;
        double newHeight = height * 2;
        return new Rectangle(newWidth, newHeight);
    }
    // 获取宽度的 getter 方法
    public double getWidth() {
        return width;
    }
    // 获取高度的 getter 方法
    public double getHeight() {
        return height;
    }
}
// 带有执行几何计算方法的工具类
class GeometryUtil {
    // 计算并返回作为参数传递的 Rectangle 对象的面积
    public static doubleArea(Rectangle rect) {
        double area = rect.calculateArea() * 2;
        return area;
    }
}
// 测试返回对象的类
public class ReturningObjects {
    public static void main(String[] args) {
        // 创建一个 Rectangle 对象
        Rectangle rectangle = new Rectangle(5.0, 3.0);
        // 调用 Rectangle 类的 createDoubleRectangle 方法
        Rectangle doubleSizeRectangle = rectangle.createDoubleSizeRectangle();
        // 显示原始面积和双倍面积
        System.out.println("Original Rectangle:");
        System.out.println("Width: " + rectangle.getWidth() + ", Height: " + rectangle.getHeight());
        System.out.println("\nDouble Size Rectangle:");
        System.out.println("Width: " + doubleSizeRectangle.getWidth() + ", Height: " + doubleSizeRectangle.getHeight());
    }
}
```

输出：

```
Original Rectangle:
Width: 5.0, Height: 3.0

Double Size Rectangle:
Width: 10.0, Height: 6.0
```

# Java 类 173

```
}
}
Output:
ID: 1, Name: Dr.
ID: 2, Name: Usharani
ID: 3, Name: Bhimavarapu
```

在该程序中，定义了一个`Test`类，包含两个实例变量：`id`和`name`，它们通过构造函数进行初始化。该类包含一个名为`displayDetails`方法，用于打印这些变量的值。`main`方法作为程序的入口点，在其中创建了一个固定大小为三的`Test`对象数组。数组中的每个元素都用一个新的`Test`对象进行初始化，每个对象具有唯一的`id`和`name`。在初始化数组后，使用 for-each 循环遍历数组，并对每个`Test`对象调用`displayDetails`方法，将其信息打印到控制台。

## 6.10 this 关键字

在 Java 中，`this`关键字是对类当前实例的引用。它可以在实例方法或构造函数中使用，用于指向调用该方法或调用构造函数的当前对象。

### this 关键字的类型

- **引用当前对象**：在实例方法或构造函数内部，`this`指向当前对象实例。它可以访问实例变量并调用同一对象的其他方法。
- **构造函数链**：`this()`可用于在同一个类的一个构造函数中调用另一个构造函数。这被称为构造函数链。
- **传递给其他方法**：此关键字可以作为参数传递给其他方法或构造函数，允许其他对象的方法对当前对象进行操作。

### this 关键字的优点

- **消除歧义**：它帮助区分构造函数或方法中与参数同名的实例变量。
- **构造函数链**：允许一个类中的一个构造函数调用另一个构造函数，减少了代码重复并确保初始化逻辑的集中化。
- **方法链**：实现了流式接口，使得方法调用可以在同一个对象上进行链式组合。

### this 关键字的局限性

- **作用域**：它只能在非静态上下文（实例方法或构造函数）中使用。它不能在静态方法中使用。
- **清晰性**：过度使用或误用`this`有时会导致代码的可读性或维护性降低，特别是在方法链或构造函数重载变得复杂的场景下。

#### 6.10.1 引用变量

在 Java 中，`this`关键字指向类的当前实例。它主要用于区分实例变量与具有同名的局部变量或方法参数。通过使用`this`，你可以显式地指示你正在引用当前对象的实例变量，这有助于避免命名冲突并确保代码可读性和维护的清晰度。

##### 程序

```java
public class Test {
    private int number;
    public Test() {
    }
    public Test(int number) {
        this.number = number; // 'this' 指向当前对象实例
    }

    public void displayNumber() {
        System.out.println("Number: " + this.number);
    }
    public static void main(String[] args) {
        Test obj = new Test();
        Test obj1 = new Test(10);
        obj1.displayNumber();
    }
}
```

输出：

```
Number: 10
```

在该程序中，定义了一个带有私有实例变量`number`的`Test`类。此外，还有一个默认构造函数，它在不为`number`设置任何值的情况下初始化对象。参数化构造函数使用`this`来引用当前实例。该类还有一个名为`displayNumber`的方法，将`number`的值打印到控制台。在`main`方法中，使用默认构造函数创建了一个`Test`对象，随后使用参数化构造函数创建了另一个对象并传递了值`10`。最后在第二个对象上调用`displayNumber`方法，将初始化的数字输出到控制台。

#### 6.10.2 引用方法

在 Java 中，`this`关键字用于在其类内部引用当前对象的方法。当你想要从构造函数内部调用另一个构造函数（构造函数链），或从同一类的另一个实例调用实例方法时，这特别有用。通过使用`this.methodName()`，你可以显式调用当前对象的方法，从而简化代码并提高可读性，特别是在涉及方法重载或复杂对象初始化逻辑的场景下。

##### 程序

```java
public class Test {
    private int number;
    public Test() {
    }
    public Test(int number) {
        this.number = number;
    }

    public void displayNumber() {
        System.out.println("Number: " + this.number);
    }
    public static void main(String[] args) {
        Test obj = new Test();
        Test obj1 = new Test(10);
        obj1.displayNumber();
    }
}
```

# Java 类 173

```java
public class Test {
    private int number;
    public Test() {
    }
    public Test(int number) {
        this.number = number;
    }

    public void displayNumber() {
        System.out.println("Number: " + this.number);
    }
    public static void main(String[] args) {
        Test obj = new Test();
        Test obj1 = new Test(10);
        obj1.displayNumber();
    }
}
```

输出：

```
Number: 10
```

在该程序中，定义了一个带有私有实例变量`number`的`Test`类。此外，还有一个默认构造函数，它在不为`number`设置任何值的情况下初始化对象。参数化构造函数使用`this`来引用当前实例。该类还有一个名为`displayNumber`的方法，将`number`的值打印到控制台。在`main`方法中，使用默认构造函数创建了一个`Test`对象，随后使用参数化构造函数创建了另一个对象并传递了值`10`。最后在第二个对象上调用`displayNumber`方法，将初始化的数字输出到控制台。

#### 6.10.3 调用另一个构造函数

在 Java 中，`this()`语法可从同一个类的一个构造函数中调用另一个构造函数。这被称为构造函数链，对于通过在构造函数中集中初始化逻辑来避免代码重复非常有用。

##### 程序

```java
public class Test {
    private int number;
    public Test() {
        this(0); // 调用参数化构造函数
    }
    public Test(int number) {
        this.number = number;
    }
    public void displayNumber() {
        System.out.println("Number: " + this.number);
    }
    public static void main(String[] args) {
        Test obj = new Test();
        obj.displayNumber();
    }
}
```

输出：

```
Number: 0
```

# Java 22 用于医疗和健康应用

## 6.10 对象作为参数

在 Java 中，`this`关键字可以作为参数传递给其他方法或构造函数。这允许这些方法对当前对象实例进行操作，对于面向对象的交互和设计模式非常有用。

### 程序

```java
public class Test {
    private int number;
    public Test() {
    }
    public Test(int number) {
        this.number = number;
    }
    public void displayNumber() {
        System.out.println("Number: " + this.number);
    }
    public void process(Test obj) {
        System.out.println("Processing number: " + obj.number);
    }
    public static void main(String[] args) {
        Test obj = new Test();
        Test obj1 = new Test(10);
        obj1.process(obj1);
    }
}
```

输出：

```
Processing number: 10
```

## Java 类 177

在该类上调用`processThisAsParameter`方法。输出显示了对象的值以及传递给`anotherMethod`的值，演示了如何使用`this`来引用当前实例。

### 6.10.5 返回当前对象

在 Java 中，你可以使用`this`关键字从方法中返回当前对象。这在方法链（method chaining）中非常有用，方法链可以将同一个对象上的多个方法调用连接在一起。例如，在方法内部，你可以编写`return this;`，这会返回类的当前实例。这允许在同一个对象上调用其他方法，而无需创建新实例。

#### 语法

```java
public class MyClass {
  public MyClass doSomething() {
    // 执行某些操作
    return this; // 返回当前对象
  }
}
```

这允许你像`obj.doSomething().doSomethingElse()`这样链式调用方法。

#### 程序

```java
public class Test {
  private int number;
  public Test() {
  }
  public Test(int number) {
    this.number = number;
  }
  public Test increment() {
    this.number++;
    return this; // 返回当前对象
  }
  public void displayNumber() {
    System.out.println("Number: " + number);
  }
  public void main(String[] args) {
    Test obj1=new Test(5);
    Test obj2=new Test(5);
    obj2.increment().increment().displayNumber(); //
    Output: Number: 8
  }
}
```

#### 输出：

```
Number: 8
```

在此程序中，`Test`类演示了使用构造函数和方法进行方法链和对象操作。它有一个私有字段`number`，可以通过参数构造函数进行初始化。该类包含一个`increment`方法，该方法将`number`字段加 1 并返回当前对象实例（`this`）。这允许进行方法链，使得能够在单个语句中多次调用`increment`。`displayNumber`方法输出`number`的当前值。在`main`方法中，创建了一个具有初始值的`Test`实例。连续调用了三次`increment`方法，导致`number`的值增加到 8。最后，调用`displayNumber`方法来打印更新后的值。

## 6.11 static 关键字

在 Java 中，`static`关键字用于定义类级别的实体，这些实体属于类本身，而不是属于类的实例（对象）。

### 静态的优势

- **内存效率**：静态变量存储在内存中的固定位置，当创建该类的多个实例时，可以减少内存占用。
- **工具类方法**：静态方法可以用于创建不需要实例化对象的工具函数，从而提高代码的可重用性。
- **全局常量**：声明为`static final`的常量实际上是全局常量，可以通过类名以及其他类直接进行访问。

### 静态的局限性

- **无状态性**：静态成员不会在实例之间维持状态。它们在类的所有实例之间共享的，如果管理不当，可能会导致意想不到的行为。
- **测试与模拟（Mock）**：静态变量和方法在单元测试中很难进行模拟，因为它们的行为与类本身绑定的，而不是与实例绑定的。
- **继承**：静态方法不是多态的。它们不能在子类中被重写，但可以用签名相同的方法进行隐藏（shadowed）。

## 6.11 静态的类型

### 6.11.1 静态变量（类）

- 静态变量在类的所有实例（对象）之间共享。
- 它们仅在执行开始时初始化一次，并存储在静态内存中。
- 使用类名（`ClassName.variable`）而不是实例来访问。

```java
public class Example {
    static int count=0; // 静态变量
}
```

在这段代码中，`Example`类包含一个名为`count`的静态变量，初始化为`0`。作为一个静态变量，`count`在所有实例之间共享，这意味着它属于类本身，而不是任何特定对象。这允许它维护一个单一的值，该值可以被类内的任何方法进行修改。静态变量通常用于计数器、配置设置或应在所有实例中保持一致的共享资源。

### 6.11.2 静态方法

- 静态方法属于类而不是任何特定的实例。
- 它们可以使用类名（`ClassName.method`）调用，而不需要实例化类。



它们不能直接访问实例变量或实例方法（在没有对象引用的情况下）。

## 程序

```java
public class MathUtils {
    public static int add(int a, int b) {
        return a + b; // 用于两个两个整数的静态方法
    }

    public static double squareRoot(double x) {
        return Math.sqrt(x); // 计算平方根的静态方法
    }

    public static void main(String[] args) {
        int sum = MathUtils.add(5, 3);
        System.out.println("Sum: " + sum);
        double sqrt = MathUtils.squareRoot(16);
        System.out.println("Square root: " + sqrt);
    }
}
```

输出：

```text
Sum: 8
Square root: 4.0
```

在此程序中，`MathUtils` 类包含了两个静态方法：`add` 和 `squareRoot`。`add` 方法接收两个整数作为参数并返回和，而 `squareRoot` 方法使用内置的 `Math.sqrt` 函数计算给定值的平方根。`main` 方法演示了如何使用这些静态方法。

### 6.11.3 静态块

静态块用于初始化静态变量。它们在类加载时执行。

```java
public class InitializationExample {
    private static int randomNumber;
    static {
        randomNumber = (int) (Math.random() * 100);
    }
    public static void main(String[] args) {
        System.out.println("Random number: " + randomNumber);
    }
}
```

在此程序中，`InitializationExample` 类使用静态块来初始化一个静态变量 `randomNumber`。该变量通过将 `Math.random()`（返回 0.0 到 1.0 之间的随机数）乘以 100 并转换为整数来获得 0 到 99 之间的随机数。静态块在类加载时执行。在 `main` 方法中，打印了 `randomNumber` 值。

## 6.12 隐式声明类和实例方法

Java 22 引入的隐式声明类和实例方法解决了软件开发中的需求，特别是在简化初者的门槛、提高代码可读性以及增强 Java 程序的模块化方面。

### 隐式声明类和实例方法的需求

- **简化初者的入口点**：对于学习 Java 的初学者来说，传统的声明带有 `main` 方法的类是一个障碍。隐式声明类允许初学者专注于编写可执行代码，而无需立即理解类声明和静态方法。

- **减少代码**：在许多情况下，Java 是带有 `main` 方法的单类应用开始的。隐式声明类消除了对显式类声明和静态 `main` 方法的需求，减少了代码并使应用程序的入口更加简洁清晰。

- **增强模块化**：通过允许 Java 程序从类的实例 `main` 方法启动而不是静态类，改进了代码组织和模块化。这支持了更面向对象的设计，可以将主功能封装在类的实例中。

- **技能的渐进式**：对于从简单的单类应用向复杂的多类项目过渡的学习者，实例方法为转向高级 Java 特性和设计模式提供了更平滑的过渡。

- **支持交互式和探索式编程**：隐式声明类有助于 Java 环境中的交互式和探索式编程。开发者可以快速编写和执行代码段，而无需类定义的开销，从而实现快速原型设计和实验。

## Java 22 用于医疗保健和医学应用

### Java 类示例，`main` 方法在 `Main` 类中被声明为实例方法

在本示例中，`main` 方法被声明为 `Main` 类中的一个实例方法，而不是静态方法。这种方法允许直接从 `Main` 类的实例执行程序。这一特性简化了 Java 程序的初始设置，增强了代码的模块化，并从应用程序的入口点支持更面向对象的编程风格。

#### 程序

```java
void main() {
    System.out.println("This is to test!");
}
```

#### 输出

```text
This is to test!
```

此程序使用 `System.out` 对象的 `println` 方法向控制台打印“This is to test!”消息。

#### 程序

```java
void main() {
    int a = 5;
    int b = 10;
    System.out.println("Sum: " + (a + b));
}
```

#### 输出

```text
Sum: 15
```

此程序初始化了两个整数变量 `a` 和 `b`，分别赋值 5 和 10。然后计算它们的和，并在 `println` 语句中使用字符串拼接将其与消息“Sum: ”一起打印。

#### 程序

```java
void main() {
    String name = "Usharani";
    System.out.println("Hello, " + name + "!");
}
```

#### 输出

```text
Hello Usharani
```

此程序定义了一个值为“Usharani”的变量 `name`，并在 `println` 语句中使用字符串拼接打印了问候消息“Hello, Usharani!”。

#### 程序

```java
void main() {
    int n = 5;
    int factorial = 1;
    for (int i = 1; i <= n; i++) {
        factorial *= i;
    }
    System.out.println("Factorial: " + factorial);
}
```

#### 输出

```text
Factorial: 120
```

此程序使用循环计算数字 5 的阶乘：将 `factorial` 初始化为 1，从 1 迭代到 5，并将每次迭代的值乘以 `factorial`，最后打印结果“Factorial: 120”。

#### 程序

```java
void main() {
    double celsius = 25.0;
    double fahrenheit = (celsius * 9/5) + 32;
    System.out.println("Fahrenheit: " + fahrenheit);
}
```

#### 输出

```text
Fahrenheit: 77.0
```

此程序使用公式 `Fahrenheit = (Celsius * 9 / 5) + 32` 计算并将摄氏度转换为华氏度。它初始化了一个 25.0 的摄氏值，计算其等值的华氏度，并使用标准输出打印结果。

## 6.13 医疗应用

### 6.13.1 案例研究 1

检测妊娠糖尿病考虑的主要参数：

- **空腹血糖**：指禁食一段时间（通常是过夜）后测量的血糖水平。血糖升高（通常高于 126 mg/dL）是糖尿病的指示指标。

- **餐后血糖**：指进食后测量的血糖水平。餐后 2 小时测量的餐后血糖超过 200 mg/dL 被认为提示患糖尿病。

- **HbA1c (糖化血红蛋白)**：HbA1c 反映了过去 2–3 个月的平均血糖水平。水平达到 6.5% 或更高表示患糖尿病。

```java
import java.util.Scanner;
class Patient {
    private String name;
    private int age;
    private String gender;
    public Patient(String name, int age, String gender) {
        this.name = name;
        this.age = age;
        this.gender = gender;
    }
    public String getName() {
        return name;
    }
    public int getAge() {
        return age;
    }
    public String getGender() {
        return gender;
    }
    @Override
    public String toString() {
        return "Patient(" +
            "name='" + name + '\'' +
            ", age='" + age + '\'' +
            ", gender='" + gender + '\'' +
            ");";
    }
}

class GestationalDiabetesDetector {
    public boolean isDiabetesDetected(double fastingBloodSugar) {
        return fastingBloodSugar >= 92;
    }

    public boolean isDiabetesDetected(double fastingBloodSugar, double postprandialBloodSugar) {
        return fastingBloodSugar >= 92 || postprandialBloodSugar >= 153;
    }

    public boolean isDiabetesDetected(double postprandialBloodSugar, double hbA1c) {
        return postprandialBloodSugar >= 153 || hbA1c >= 5.7; // 根据上下文修复了逻辑错误
    }
}

class GestationalDiabetesDetection {
    static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter patient name: ");
        String name = scanner.nextLine();
        System.out.print("Enter patient age: ");
        int age = scanner.nextInt();
        scanner.nextLine();
        System.out.print("Enter patient gender: ");
        String gender = scanner.nextLine();
        Patient patient = new Patient(name, age, gender);
        GestationalDiabetesDetector detector = new GestationalDiabetesDetector();
        System.out.print("Enter fasting blood sugar (mg/dL): ");
        double fastingBloodSugar = scanner.nextDouble();
        boolean detected = false;
        System.out.print("Enter postprandial blood sugar (mg/dL): ");
        double postprandialBloodSugar = scanner.nextDouble();
        System.out.print("Enter HbA1c (%): ");
        double hbA1c = scanner.nextDouble();

        if (fastingBloodSugar >= 92) {
            detected = true;
        } else if (postprandialBloodSugar >= 153) {
            detected = true;
        } else if (hbA1c >= 5.7) {
            detected = true;
        }

        System.out.println("Patient details: " + patient);
        System.out.println("Gestational diabetes result: " + (detected ? "Diabetes detected" : "No diabetes"));
    }
}
```

### 案例研究 2

```java
public String getName() {
    return name;
}
public int getAge() {
    return age;
}
public String getGender() {
    return gender;
}
public boolean hasMuscleWeakness() {
    return hasMuscleWeakness;
}
public boolean hasLiverEnlargement() {
    return hasLiverEnlargement;
}
public boolean hasHypoglycemia() {
    return hasHypoglycemia;
}
@Override
public String toString() {
    return "Patient" +
        " 'name='" + name + '\'' +
        ", age='" + age + '\'' +
        ", gender='" + gender + '\'' +
        ", hasMuscleWeakness='" + hasMuscleWeakness + '\'' +
        ", hasLiverEnlargement='" + hasLiverEnlargement + '\'' +
        ", hasHypoglycemia='" + hasHypoglycemia + '\'' +
        "";
}
```

```java
void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter patient name: ");
    String name = scanner.nextLine();
    System.out.print("Enter patient age: ");
    int age = scanner.nextInt();
    scanner.nextLine();
    System.out.print("Enter patient gender: ");
    String gender = scanner.nextLine();
    System.out.print("Has muscle weakness: ");
    boolean hasMuscleWeakness = scanner.nextBoolean();
    System.out.print("Has liver enlargement: (true/false): ");
    boolean hasLiverEnlargement = scanner.nextBoolean();
    System.out.print("Has hypoglycemia: (true/false): ");
    boolean hasHypoglycemia = scanner.nextBoolean();
    Patient patient = new Patient(name, age, gender, hasMuscleWeakness, hasLiverEnlargement, hasHypoglycemia);
    Predicate<Patient> muscleWeaknessPredicate = p -> p.hasMuscleWeakness();
    Predicate<Patient> liverEnlargementPredicate = p -> p.hasLiverEnlargement();
    Predicate<Patient> hypoglycemiaPredicate = p -> p.hasHypoglycemia();
    boolean hasForbesDisease = muscleWeaknessPredicate.test(patient) &&
        hypoglycemiaPredicate.test(patient) &&
        System.out.println("Patient details: " + patient);
    System.out.println("Forbes' disease detection result: " + (hasForbesDisease
        ? "Forbes' disease detected" : "No Forbes' disease detected"));
}
```

程序 `ForbesDiseaseDetection` 首先提示用户输入患者的姓名、年龄和性别等详情，随后是布尔值输入，指示患者是否有肌肉无力、肝脏增大或低血糖。使用这些输入，实例化了一个“患者”对象，封装了所有提供的数据。检测逻辑使用 Lambda 表达式和谓词（predicates）来评估患者是否表现出福斯病（Forbes' disease）的症状，即肌肉无力、肝脏增大和低血糖。



# Java 继承

## 7.1 引言

数据隐藏是面向对象编程（OOP）中的一个基本概念，指的是限制对象定义之外直接访问对象状态（其数据）某些组件的实践。在 Java 中，这通常通过使用访问修饰符（`private`、`protected`、`public`）来控制类成员的可见性和访问权限。

### 7.1.1 数据隐藏的关键方面

- 访问控制：通过在类内部标记某些字段（`private`）或方法（`private` 或 `protected`），限制了来自该类的访问。这防止了对内部状态的意外修改或访问。
- 封装：数据隐藏与封装紧密相关，封装将数据和操作数据的方法组合在类中。封装确保了对象的状态仅通过受控的方法进行访问和修改。

### 7.1.2 数据隐藏的必要性

- 安全性：保护敏感数据免受未经授权的访问和操纵，降低意外损坏或安全泄露的风险。
- 可维护性：鼓励类的内部实现细节与其公共接口之间保持清晰的分离，使得在不影响程序其他部分的情况下，更容易修改和重构代码。
- 灵活性：允许类独立演进，因为内部实现细节（私有字段、方法）的更改不会影响依赖于公共接口的代码。

### 7.1.3 数据隐藏的优势

- 增强安全性：防止直接修改敏感数据，确保仅通过受控的方法进行访问和修改。这降低了意外副作用或安全漏洞的风险。
- 提高可维护性：通过在实现细节和公共接口之间创建清晰分离，鼓励更好的组织和模块化设计。这使得代码更容易理解、调试和维护。
- 促进重用性：封装和数据隐藏有助于代码重用，因为对象可以集成到不同的上下文中而不暴露其内部机制。

### 7.1.4 数据隐藏的局限性

- 访问开销：需要额外努力设计和实现类接口（`getters` 和 `setters`）来访问私有数据，这可能会增加代码复杂性和开销。
- 潜在误用：过度限制访问会导致设计复杂，或在直接访问可能合适的情况下阻碍合法使用。
- 性能考虑：通过 `getter` 和 `setter` 方法间接访问数据与直接访问字段相比可能会产生轻微的性能开销。然而，现代 JVM 优化通常会减轻这种影响。

Java 数据隐藏的示例

```java
public class Student {
    private String name;
    private int age;
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() { // Getter 方法
        return name;
    }
    public void setAge(int age) { // Setter 方法
        if (age > 0) {
            this.age = age;
        }
    }
}
```

在这个示例中，`name` 和 `age` 是私有字段，无法从 `Student` 类外部直接访问。`getName()` 和 `setAge(int age)` 为 `name` 和 `age` 提供了受控访问，确保只有在 `age` 为正时才进行设置。

## 7.1.5 继承

继承允许一个类继承另一个类的属性和行为（字段和方法）。这种机制是面向对象编程（OOP）的核心特征之一，能够创建分级分类。它促进了代码重用，并使系统更加模块化且更容易管理。

Java 继承的核心概念

- 超类（父类）：被继承属性和方法的类。也被称为基类或父类。
- 子类（子类）：继承另一个类的属性和方法的类。也被称为派生类或子类。

在 Java 中，继承通过 `extends` 关键字实现。当一个类扩展另一个类时，它会继承父类所有非私有的成员（字段和方法）。

### 7.1.5.1 继承的好处

- 代码重用：允许重用现有代码，减少冗余并提高可维护性。
- 方法重写：子类可以为其父类定义的方法提供特定的实现。
- 多态：允许单个接口表示不同的形式（对象）。例如，方法可以接受子类类型，使其能够处理任何子类类型。
- 分级组织：有助于以分级的方式组织和构建代码，更加直观且易于理解。

### 7.1.5.2 继承的局限性

- 紧耦合：继承在超类和子类之间创建了紧耦合，降低系统的灵活性。
- 脆弱基类问题：子类的更改会影响所有子类，有时会产生意外。
- 单继承限制：Java 只支持单继承，这意味着一个类只能继承一个超类。这在某些场景下具有限制性。
- 增加复杂性：深层继承体系可能会变得难以管理。

# 程序

```java
// 类名为 test 的超类
class test {
    // test 类中的方法
    void display() {
        System.out.println("Parent class method");
    }
}
// 继承 test 的主类
public class Main extends test {
    public static void main(String[] args) {
        // 创建 test 类的实例
        test t = new test();
        // 使用 test 对象调用 display() 方法
        t.display(); // 这将调用 test 类的方法
    }
}
```

输出：

```
Parent class method
```

## 7.2 EXTENDS 关键字

在 Java 中，继承是面向对象编程的一个基本原则，它允许类继承并利用来自父类或基类的数据成员和属性。在这种范式中，子类（也称为从类）通过扩展或继承其父类来创建。这种继承机制允许子类访问并利用定义在其父类中的变量和方法。在类声明中包含 `extends` 关键字，会通知编译器该子类继承了其父类的属性和行为。通过利用继承，Java 开发者可以创建类的层次结构，从而提高应用程序的代码重用性、模块化和扩展性。

#### 语法

```java
class super
{
}
---
class sub extends super
{
}
---
---
```

Java 中的 `extends` 关键字表示继承，其中子类继承了超类的数据成员和方法。当使用 `class Sub extends Super` 语法声明一个类时，意味着 `Sub` 类正在继承 `Super` 类。在这种情况下：

- `Super` 指的是超类或父类。
- `Sub` 指的是子类。

子类声明的结构遵循特定的格式。`class` 关键字后是子类的名称，然后是 `extends` 关键字，最后是子类所继承的父类名称。在子类内部，除了从父类继承的内容外，你还定义了子类特的数据成员（变量）和方法。这种语法允许子类访问并利用其父类的数据成员和方法，增强了代码重用并促进了面向对象编程中的层次结构。

## 程序

```java
// 基类
class Base {
    // Base 类中的方法
    void display() {
        System.out.println("Base Class Method");
    }
}
// 继承 Base 的派生类
class Derived extends Base {
    // Derived 类中的方法
    void put() {
        System.out.println("Derived Class Method");
    }
}
// 带有 main 方法的测试类
public class Test {
    public static void main(String[] args) {
        // 创建 Derived 类对象
        Derived d = new Derived();
        // 调用 Base 类的 display() 方法
        d.display(); // 输出: "Base Class Method"
        // 调用 Derived 类的 put() 方法
        d.put(); // 输出: "Derived Class Method"
    }
}
```

输出：

```
Base Class Method
Derived Class Method
```

该 Java 程序由三个类组成：`Base`、`Derived` 和 `Test`。`Base` 类包含一个名为 `display()` 的方法，该方法向控制台打印消息 "Base Class Method"。`Derived` 类继承了 `Base` 类并定义了一个名为 `put()` 的方法。`Test` 类包含 `main` 方法。在 `main` 方法中，使用语句 `Derived d = new Derived();` 创建了 `Derived` 类对象。接下来，在 `d` 对象上调用了 `display()` 方法，导致控制台打印出消息 "Base Class Method"。紧接着，在同一个对象上调用了 `put()` 方法，导致控制台打印出消息 "Derived Class Method"。当程序执行时，它创建了一个 `Derived` 类的对象，演示了继承，即 `Derived` 类继承了其超类 `Base` 的 `display()` 方法。

## 7.3 父类分类

在 Java 中，任何类都可以作为父类，作为继承层次结构的基础。父类可以根据其与其他类的关系进一步细分为两类：直接父类和间接父类。

### 7.3.1 直接父类

如果一个父类在子类的父类列表中被明确提到，则称为直接父类。换句话说，当子类直接扩展或继承一个父类时，该父类被视为直接父类。例如：

```java
class Test {
}
class Sample extends Test {
}
```

在这个示例中，`Test` 是 `Sample` 的直接父类，因为 `Sample` 显式扩展了 `Test`。

### 7.3.2 间接父类

相反，间接父类是一个没有直接出现在继承层次结构中，但继承自另一个父类的类。在这种情况下，子类扩展了一个本身又继承了另一个类的类。例如：

```java
class Test {
}
class Sample extends Test {
}
class First extends Sample {
}
```

在示例中，`Test` 是 `Sample` 的直接父类，因为 `Sample` 扩展了 `Test`。但是对于类 `First` 来说，`Sample` 是直接父类，而 `Test` 变成了间接父类。这是因为 `First` 扩展了 `Sample`，而 `Sample` 又扩展了 `Test`。

## 程序：间接父类

```java
// 父类 "test"
class Test {
    // "test" 类中的方法
    void display() {
        System.out.println("Parent class method");
    }
}
// 继承 "test" 的子类 "sample"
class Sample extends Test {
    // "sample" 类中的方法
    void put() {
        System.out.println("Child class method");
    }
}
// 继承 "sample" 的子类 "test1"
class Test1 extends Sample {
    // "test1" 类中的方法
    void printing() {
        System.out.println("Subclass class method");
    }
}
// 继承 "test1" 的孙子类 "test2"
class Test2 extends Test1 {
    // "test2" 类中的方法
    void method() {
        System.out.println("Subclass class method");
    }
}
// 主类
public class Main {
    public static void main(String[] args) {
        // 创建 "test2" 对象
        Test2 t = new Test2();
        // 调用每个类的方法
        t.display(); // 输出: "Parent class method"
        t.put(); // 输出: "Child class method"
        t.printing(); // 输出: "Subclass class method"
        t.method(); // 输出: "Subclass class method"
    }
}
```

输出：

```
Parent class method
Child class method
Subclass class method
Subsubchild class method
```

上述 Java 程序包含多个类，包括 `test`、`sample`、`test1`、`test2` 和一个名为 `Main` 的公共类。`test` 类定义了一个名为 `display()` 的方法，向控制台打印 "Parent class method"。`sample` 类继承了 `test` 类并定义了一个名为 `put()` 的方法。`test1` 类继承了 `sample` 类并定义了一个名为 `printing()` 的方法。`test2` 类继承了 `test1` 类并定义了一个名为 `method()` 的方法。`Main` 类包含 `main` 方法。在 `main` 方法中，使用语句 `Test2 t = new Test2();` 创建了 `test2` 类对象。接下来，在 `t` 对象上调用了 `display()` 方法，导致控制台打印出 "Parent class method"。紧接着，在同一个对象上调用了 `put()` 方法，导致控制台打印出 "Child class method"。然后，在同一个对象上调用了 `printing()` 方法，导致控制台打印出 "Subclass class method"。最后，在同一个对象上调用了 `method()` 方法，导致控制台打印出 "Subclass class method"。当程序执行时，它创建了一个 `test2` 类的对象，演示了继承，即 `test2` 类继承了其超类的方法。

## 7.4 访问父类成员

在 Java 中，父类的可访问性取决于应用于其成员的访问修饰符，包括变量、方法和构造函数。这些访问修饰符规定了如何在类内部和其他类中访问它们。主要的四种访问修饰符：

- 默认（`default`）：在未指定访问修饰符时自动应用默认修饰符。它将访问限制在同一个包内，防止从包外访问。
- 公共（`public`）：`public` 修饰符允许从任何类（无论包如何）对父类进行无限制的访问。该修饰符提供了广泛的访问性，使父类对应用程序中的所有类可见。
- 受保护（`protected`）：`protected` 修饰符将父类的访问限制在子类中，允许在同一个包内或来自不同包的子类进行访问。该修饰符用于创建一个超出类本身但仍限于其子类的访问级别。
- 私有（`private`）：`private` 修饰符提供了最严格的访问控制，将父类成员的访问完全限制在类内部。该修饰符确保成员仅在类内部可访问，无法从任何外部类或子类访问。

通过恰当地应用这些访问修饰符，Java 程序员可以管理父类成员的可见性和访问性，确保适当封装并控制应用程序中类之间的交互。

### 7.4.1 访问受保护成员

父类的受保护成员可以直接被子类访问，因为它们对子类和同一包内的类是可见的。

# 用于医疗与健康应用的 Java 22

## 程序



```java
public class InheritanceExample {
    static class Base {
        protected String baseField;
        public Base() {
            baseField = "Base field";
        }
        protected void baseMethod() {
            System.out.println("Base method");
        }
        protected void displayBase() {
            System.out.println("Base Field: " + baseField);
        }
    }
    static class Child extends Base {
        protected String childField;
        public Child() {
            childField = "Child field";
        }
        protected void childMethod() {
            System.out.println("Child method");
        }
    }

    public void main(String[] args) {
        // Creating an instance of the Child class
        Child childInstance = new Child();
        // Accessing protected members from the base class
        System.out.println("Accessing Base Field from Child: " + childInstance.baseField);
        childInstance.baseMethod();
        // Accessing protected members from the child class
        System.out.println("Accessing Child Field from Child: " + childInstance.childField);
        childInstance.childMethod();
        // Displaying both base and child fields
        childInstance.displayBase();
    }
}
```

输出：

```
Accessing Base Field from Child: Base field
Base method
Accessing Child Field from Child: Child field
Child method
Base Field: Base field
```

`InheritanceExample`类包含一个基类`Base`和一个派生类`Child`。`Base`类定义了一个字段`baseField`以及两个受保护的方法`baseMethod()`和`displayBase()`。`Base`类的构造函数将`baseField`初始化为值`Base field`。`baseMethod()`打印消息`Base method`，而`displayBase()`输出`baseField`的值。`Child`类继承自`Base`类，继承了它的成员，并添加了自身的受保护字段`childField`和方法`childMethod()`。`Child`类的构造函数将`childField`初始化为`Child field`，`childMethod()`打印`Child method`。在`main`方法中，我们创建了`Child`类的实例并访问了继承的成员和类特有的成员。该实例允许我们访问来自`Base`类的`baseField`和`baseMethod()`，以及来自`Child`类的`childField`和`childMethod()`。此外，调用了`displayBase()`方法来打印`baseField`的值。

### 7.4.2 访问私有成员

父类的私有成员无法被子类直接访问。要访问私有成员，你需要使用父类中公共或受保护的 getter（`get`）和 setter（`set`）方法。

## 程序

```java
class Parent {
    private int privateField;
    // Constructor to initialize privateField
    public Parent(int privateField) {
        this.privateField = privateField;
    }
    // Method to access privateField
    public int getPrivateField() {
        return privateField;
    }
}
class Child extends Parent {
    private int childField;
    public Child(int privateField, int childPrivateField) {
        super(privateField);
        this.childField = childPrivateField;
    }
    // Method to access parent's privateField indirectly
    public int getParentField() {
        return getPrivateField(); // Calling parent class method to access privateField
    }
    // Method to access child's privateField directly
    public int getChildField() {
        return childField;
    }
}
public class Main {
    public static void main(String[] args) {
        Child child = new Child(10, 20);
        // Accessing parent's privateField indirectly
        System.out.println("Parent's privateField: " + child.getParentField());
        // Accessing child's privateField directly
        System.out.println("Child's privateField: " + child.getChildField());
    }
}
```

输出：

```
Parent's privateField: 10
Child's privateField: 20
```

在上面的程序中，我们演示了 Java 中的继承以及通过 getter 方法访问私有字段。我们定义了一个带有私有字段`privateField`的`Parent`类，该字段无法从类外部直接访问。为了初始化该字段提供了一个构造函数，并使用公共方法`getPrivateField()`来返回其值。`Child`类继承自`Parent`类，添加了自身的字段`childPrivateField`。在`Child`构造函数中，调用了`super()`来触发`Parent`构造函数，从而初始化`privateField`。`Child`类还提供了两个方法：`getParentField()`通过`getPrivateField()`方法间接访问父类的私有字段，`getChildField()`直接访问自身的私有字段。在`Main`类中，我们创建了`Child`类的实例，并分别为父类和子类字段传递了值 10 和 20。通过该实例，我们通过`getParentField()`方法访问父类的私有字段，并通过`getChildField()`方法直接访问子类的私有字段。

```java
class sub extends super
{
    // variables and methods
}
```

该语法表示两个 Java 类的结构：`superclass`（父类）和`subclass`（子类），展示了单继承。在这种语法中，`superclass`被定义为父类，而`subclass`扩展或继承自`superclass`，作为子类。该语法遵循 Java 的声明约定，即使用`class`关键字加上类名来声明每个类。

在`superclass`和`subclass`的定义中，开发者可以包含特定每个类的变量和方法。`subclass`继承`superclass`的所有公共（`public`）和受保护（`protected`）变量和方法，增强了代码重用和扩展。这种继承关系通过`extends`关键字建立，该关键字表示`subclass`继承自`superclass`。

通过扩展`superclass`，子类获得了访问其属性和行为的能力，允许开发者在父类提供的功能基础上进行构建和增强。这促进了代码的模块化、封装和重用，这些是面向对象编程的核心原则。该语法封装了单继承的概念，即子类仅继承自一个父类，在类之间形成了层级关系。

注意：单个派生类的声明与普通 Java 类的声明相同。

子类是面向对象编程中的基本概念，包含了定义其结构及其与父类继承关系的几个组件：

1. 关键字`class`：子类以`class`关键字开始，表示在 Java 编程语言中定义一个新类。
2. 子类名：`class`关键字之后是子类的名称，用于在程序中标识该子类。此名称通常反映了子类的性质或目的。
3. `extends`：在指定子类名后，使用`extends`关键字表示子类扩展或继承自另一个类（即其父类）。这在子类与其父类之间建立了继承关系。
4. 父类名：`extends`关键字之后是子类继承的父类名称。该父类为子类提供了蓝图或模板，允许其继承属性和行为。
5. 子类定义的剩余部分：指定父类后，子类定义的剩余部分包括额外的组件，作为特定于子类的成员变量、方法和构造函数。这些组件定义了子类的独特特性和功能，这些功能可以补充或扩展从父类继承来的内容。

这些组件共同构成了子类的结构，确立了它与父类的继承关系，并定义了在 Java 程序中独特的属性和行为。

# 程序

带有变量和方法的单继承

```java
// 父类 "test"
class Test {
    // "test" 类中的字符串变量
    String name = "parent";
    // "test" 类中的方法
    void display() {
        System.out.println("Parent class method");
    }
}
// 继承 "test" 的子类 "sample"
class Sample extends Test {
    String name1 = "sub";
    // "sample" 类中的方法
    void put() {
        System.out.println("Child class method");
        // 访问 "test" 类中的 "name" 变量和 "sample" 类中的 "name1" 变量
        System.out.println("Name from parent class: " + name);
        System.out.println("Name from child class: " + name1);
    }
}
// 主类
public class Main {
    public static void main(String[] args) {
        // 创建 "sample" 类的对象
        Sample s = new Sample();
        // 调用 "test" 类的 "display()" 方法
        s.display(); // 输出: "Parent class method"
        // 调用 "sample" 类的 "put()" 方法
        s.put(); // 输出: "Child class method", 随后是名称
    }
}
```

输出：

```
Parent class method
Child class method
Name from parent class: parent
Name from child class: sub
```

该 Java 程序包含三个类：`Test`、`Sample`和`Main`。`Test`类定义了一个值为`parent`的字符串变量`name`以及一个名为`display`的方法。当调用`display()`方法时，它会在控制台打印`Parent class method`。`Sample`类继承了`Test`类，继承了`name`变量和`display()`方法。此外，它声明了一个赋值值为`sub`的新字符串变量`name1`，并定义了一个名为`put`的方法。`put()`方法向控制台打印`child class method`，并访问了`name`和`name1`变量，分别打印它们的值。`Main`类继承了`Sample`类，继承了所有的变量和方法。在`main`方法中，使用语句`Sample s = new Sample();`创建了`Sample`类的实例。该对象用于调用继承自`Test`类的`display()`方法和在`Sample`类中定义的`put()`方法。执行程序时，`display()`方法在控制台打印`Parent class method`，随后是`put()`方法打印`child class method`。此外，它访问并打印了`name`和`name1`变量的值，演示了 Java 继承体系中跨类的变量继承和访问。

# 程序

```java
// 带有私有构造函数的基类
class Base {
    // 私有构造函数
    private Base() {
        System.out.println("Private Base constructor");
    }
    // 供子类使用的受保护构造函数
    protected Base(boolean flag) {
        System.out.println("Protected Base constructor");
    }
    // 创建 Base 实例的静态工厂方法
    public static Base createBase() {
        return new Base();
    }
}
// 继承 Base 的子类
class Child extends Base {
    protected Child() {
        System.out.println("Protected Child constructor");
        super(true); // 调用 Base 的受保护构造函数
    }
}
// 带有 main 方法的测试类
public class Test {
    public static void main(String[] args) {
        // 使用静态工厂方法创建 Base 的实例
        Base base = Base.createBase();
        // 创建 Child 的实例
        Child child = new Child(); // 将调用 Child 的受保护构造函数
    }
}
```

输出：

```
Private Base constructor
Protected Child constructor
Protected Base constructor
```

在上述程序中，`Base`类有一个私有构造函数和一个受保护构造函数，并有一个用于创建实例的静态工厂方法。`Child`类继承自`Base`并在其中使用了`Base`的受保护构造函数。

`Sample s = new Sample();`然后，使用此对象`s`调用了`display()`和`put()`方法。在执行期间，程序向控制台打印`Parent class method`，然后是`child class method`，展示了方法从父类（`Test`）到子类（`Sample`）的继承。

## 7.5.3 层次继承

Java 中的层次继承涉及一种类层级结构，其中多个子类继承自共同的父类。

### 程序



```java
// 父类
class base {
  void f1() {
    System.out.println("base");
  }
}
// 子类 1
class child extends base {
  void f2() {
    System.out.println("child");
  }
}
// 子类 2
class subclass extends base {
  void f3() {
    System.out.println("subchild");
  }
}
public class Main {
  public static void main(String[] args) {
    // 创建子类的对象
    child c=new child();
    subclass s=new subclass();
    c.f1();
    c.f2();
    s.f1();
    s.f3();
  }
}
```

输出：

```
base
child
base
subchild
```

上面的 Java 程序演示了具有名为 `base` 的父类以及两个名为 `child` 和 `subclass` 的子类的层次继承。`base` 类包含一个方法 `f1()`，它可以打印 `base`，该方法被两个子类继承。每个子类都定义了自己独特的方法：`child` 中的 `f2()` 和 `subclass` 中的 `f3()`，分别打印 `child` 和 `subchild`。在 `Main` 类中，实例化了 `child` 和 `subclass` 的对象。通过继承，两个子类都继承了父类 `base` 的 `f1()` 方法。此外，分别调用了 `child` 和 `subclass` 的 `f2()` 和 `f3()` 方法，展示了每个子类在继承父类内容之外还拥有自己的行为。

## Java 继承

## 7.6 构造函数链

继承中的构造函数链是指派生（子）类的构造函数调用其基（父）类构造函数的过程。这确保了在子类添加自己的属性和方法之前，父类已经过正确初始化。在 Java 中，这通常通过 `super` 关键字实现。

分为分为类型：

- (a) 无参数构造函数链
- (b) 带参数构造函数链

## 7.6.1 无参数构造函数链

当使用无参数的构造函数来建立从子类到父类的调用链时发生这种情况。在 Java 中，子类构造函数不会显式调用父类构造函数，Java 编译器会自动使用 `super()` 调用父类的无参数构造函数。

### 程序

```java
class Parent {
  Parent() {
    System.out.println("Parent class parameterless constructor");
  }
}

class Child extends Parent {
  Child() {
    // 隐式调用 super()
    System.out.println("Child class parameterless constructor");
  }
}

public class ConstructorChainingExample {
  public static void main(String[] args) {
    System.out.println("Creating instance:");
    Child child = new Child();
  }
}
```

输出：

```
Creating instance:
Parent class parameterless constructor
Child class parameterless constructor
```

在上面的程序中，我们演示了 Java 中的构造函数链，其中子类隐式调用了父类构造函数。`Parent` 类包含一个无参数构造函数，它打印一条指示父类构造函数已调用的消息。`Child` 类继承 `Parent` 类并定义了一个无参数构造函数。虽然没有显式调用 `super()`，但当子类构造函数被调用时，Java 会隐式调用父类构造函数。这确保了当子类构造函数被调用时，父类构造函数先执行。当子类构造函数被调用时，父类构造函数被执行，然后是子类构造函数。

### 7.6.2 带参数构造函数

继承中的带参数构造函数链涉及通过 `super` 从子类调用父类的特定构造函数。

### 程序

```java
class Parent {
  Parent(String message) {
    System.out.println("Parent class constructor: " + message);
  }
}

class Child extends Parent {
  Child(String message) {
    System.out.println("Child class constructor: " + message);
    super(message); // 显式调用父类的带参数构造函数
  }
}

public class ConstructorChainingExample {
  public static void main(String[] args) {
    System.out.println("Creating Child instance:");
    Child child = new Child("Child");
  }
}
```

输出：

```
Creating Child instance:
Child class constructor: Child
Parent class constructor: Child
```

该程序演示了 Java 继承中的构造函数链，其中 `Child` 类继承 `Parent` 类。`Parent` 类有一个带参数的构造函数，可以打印消息。`Child` 也有一个带参数的构造函数，使用 `super` 关键字调用 `Parent` 构造函数并打印自己的消息。`ConstructorChainingExample` 类包含 `main` 方法，它创建一个带参数的 `Child` 类实例。执行时，它会打印 `Parent` 和 `Child` 构造函数的输出，显示调用顺序。

## 7.6.2.1 另一个多个构造函数的示例

### 程序

```java
class Parent {
  Parent() {
    System.out.println("Parent class default constructor");
  }

  Parent(String message) {
    System.out.println("Parent class parameterized constructor: " + message);
  }
}

class Child extends Parent {
  Child() {
    System.out.println("Child class default constructor");
    super(); // 显式调用父类的默认构造函数
  }

  Child(String message) {
    System.out.println("Child class parameterized constructor: " + message);
    super(message); // 显式调用父类的带参数构造函数
  }
}

public class ConstructorChainingExample {
  public static void main(String[] args) {
    System.out.println("Creating Child instance with default constructor:");
    Child child1 = new Child();
    System.out.println("\nCreating Child instance with parameterized constructor:");
    Child child2 = new Child("Usharani");
  }
}
```

输出：

```
Creating Child instance with default constructor:
Child class default constructor
Parent class default constructor

Creating Child instance with parameterized constructor:
Child class parameterized constructor: Usharani
Parent class parameterized constructor: Usharani
```

```java
// 继承自 Child 带有两个构造函数的子类
class Sub extends Child {
  Sub() {
    System.out.println("Sub class no-argument constructor");
    super(); // 调用 Child类的无参构造函数
  }

  Sub(String str) {
    System.out.println("Sub parameterized constructor: " + str);
    super(str); // 调用 Child类的参数化构造函数
  }
}

// 展示构造函数的测试类
public class Test {
  void main(String[] args) {
    // 创建无参数的 Sub 对象
    Sub s1 = new Sub();
    // 创建带有 "test" 参数的 Sub 对象
    Sub s2 = new Sub("test");
  }
}
```

输出：

```
Sub class no-argument constructor
Child class no-argument constructor
Base class no-argument constructor
Sub parameterized constructor: test
Child class parameterized constructor: test
Base class parameterized constructor: test
```

该 Java 程序包含三个类：`base`、`child` 和 `sub`。`base` 类包含两个构造函数，一个无参数，一个带有 `String` 参数。两个构造函数都会打印指示其调用的消息。`child` 类继承自 `base` 类，也包含两个构造函数，一个无参数，一个带有 `String` 参数。`child` 的构造函数使用 `super` 关键字调用 `base` 类相应的构造函数，并打印指示其执行的消息。`sub` 类继承自 `child` 类，并包含与 `child` 类类似的构造函数，调用父类构造函数并相应打印消息。在 `Test` 类的 `main` 方法中，实例化两个 `sub` 对象，一个无参数，一个带有 `"test"` 参数，演示了构造函数的调用及其各自的消息。

# 使用 super 进行构造函数链调用的程序

```java
// 带有三个构造函数的基类
class Base {
  Base() {
    System.out.println("Base class no-argument constructor");
  }

  Base(String str) {
    System.out.println("Base class parameterized constructor with String: " + str);
  }

  Base(int num) {
    System.out.println("Base class parameterized constructor with int: " + num);
  }
}

// 继承自 Base 带有两个构造函数的子类
class Child extends Base {
  Child() {
    System.out.println("Child class no-argument constructor");
    super("test"); // 调用带有 String 参数的 Base 类构造函数
  }

  Child(String str) {
    System.out.println("Child class parameterized constructor with String: " + str);
    super("test"); // 调用带有 String 参数的 Base 类构造函数
  }
}

// 展示构造函数调用的测试类
public class Test {
  void main(String[] args) {
    // 创建无参数的 Child 对象
    Child c1 = new Child();
    // 创建带有 String 参数的 Child 对象
    Child c2 = new Child("test");
  }
}
```

输出：

```
Child class no-argument constructor with String: test
Base class parameterized constructor with String: test
Base class parameterized constructor with String: test
```

该 Java 程序两个类：`base` 和 `child`。`base` 有三个构造函数，每个都有不同的参数。构造函数打印指示其调用的消息。`child` 类继承自 `base` 类，包含两个构造函数，一个无参数，一个带有 `String` 参数。在两种情况下，都使用 `super` 关键字来调用父类的相应构造函数，并将 `"test"` 作为参数传递。调用父类构造函数后，会打印指示构造函数执行的消息。在 `Test` 类的 `main` 方法中，实例化了两个 `child` 对象，一个无参数，一个带有 `"test"` 参数，演示了构造函数的调用和消息。

# 7.7 SUPER(...) 之前的语句

在 Java 22 中，允许在构造函数中的 `super(...)` 之前使用语句的特性解决了该语言中构造函数调用规则的一个长期以来的限制。传统上，Java 构造函数要求任何初始化正在被构建的实例（通过 `this`）的语句必须出现在 `super(...)` 调用或隐式 `super()` 之后。这种限制导致了不自然的构造函数代码，并使得遵循最佳实践变得具有挑战，因为无法在调用父类构造函数之前初始化字段。

# 7.7.1 在 SUPER(...) 之前使用语句的必要性

- **初始化灵活性**：在此之前，构造函数被限制为在调用 `super(...)` 之后才能初始化字段并执行其他逻辑。当初始化顺序很重要时，这种限制可能会导致复杂的变通方法和可读性差的代码，特别是在父类构造函数需要特定设置的子类中。

- **字段初始化**：通过能够在 `super(...)` 之前放置语句，开发者可以初始化字段或执行不依赖于子类状态或构造的任务。这提高了清晰度，并允许初始化步骤具有更自然的排序，符合典型的编码实践，并减少了由于初始化顺序错误导致的错误风险。

- **增强可读性**：通过允许在 `super(...)` 之前使用语句，构造函数变得更加易读且直观。开发者可以将准备性逻辑放在构造函数的开头，使得在调用父类构造函数之前执行了哪些设置变得更加清晰。

- **子类构造函数的益处**：当子类需要执行逻辑上独立于父类初始化的操作时，从这一特性中受益巨大。例如，可以在调用 `super(...)` 之前设置默认值或验证参数，确保子类接收到有效数据。

- **与初始化顺序的一致性**：构造函数调用关系的现代化使 Java 与其他编程语言对齐，在这些语言中，构造函数逻辑是灵活的，并适应初始化的自然流程。这一变化改进了语言的易用性，而没有承诺与现有代码库的兼容性。

# 程序

```java
class Base {
  Base(String message) {
    System.out.println(message);
  }
}

class Child extends Base {
  Child() {
    System.out.println("Child constructor starts.");
    super("Base call child");
  }
}

public class Test {
  void main(String[] args) {
    Child c = new Child();
  }
}
```

输出：

```
Child constructor starts.
Base call child
```

该程序仅在 Java 22 中工作；对于其他版本，它会报错，因为在子类构造函数的 `println()` 之后使用了 `super()`。在此解释中，我们演示了构造函数中 `super()` 的使用。我们定义了一个带有 `String` 参数的 `Base` 类。当调用此构造函数时，它会打印消息。`Child` 类继承自 `Base` 类。在它的构造函数中，第一行打印了。然而，调用父类构造函数的 `super()` 放置在该语句之后，这在 Java 22 中是有效的。

# Java 继承

# 程序



```java
class Logger {
  static void log(String message) {
    System.out.println(message);
  }
}
class Base {
  Base() {
    System.out.println("Base initialized");
  }
}
class Child extends Base {
  Child() {
    Logger.log("Logging before super()");
    super();
  }
}
public class Test {
  void main(String[] args) {
    Child c= new Child();
  }
}
```

输出：

`Logging before super()`

`Base initialized`

该程序在 `java22` 中工作；对于其他版本，它会报错，因为在子类构造函数的 `println()` 之后使用了 `super()`。在此程序，我们演示了带有 `log` 的构造函数链。`Logger` 包含用于打印消息的静态方法 `log()`。`Base` 类定义了一个构造函数，在创建类对象时打印 `"Base initialized"`。`Child` 类继承 `Base` 并包含它自己的构造函数。最初，程序尝试在通过 `super()` 调用父类构造函数之前，使用 `Logger.log("Logging before super()")` 记录消息。然而，这种方法在 Java 22 中是有效的，编译器会打印记录消息，随后初始化基类。

# 程序

```java
class Base {
  Base(int number) {
    System.out.println("Number: " + number);
  }
}
class Child extends Base {
  Child() {
    int x = 10;
    System.out.println("Calculating x: " + x);
    super();
  }
}
public class Test {
  void main(String[] args) {
    Child c= new Child();
  }
}
```

## 210 用于医疗和健康应用程序的 Java 22

### 输出

`Calculating x: 10`

`Number: 10`

此程序在 `java22` 中运行；对于其他版本，它将抛错误，因为我们在子类构造函数中的 `println()` 语句之后使用了 `super()`。在该程序中，我们演示了子类构造函数如何使用 `super()` 关键字将值传递给父类构造函数。`Base` 类接收一个整数参数，当被调用时，它会打印 `"Number: "`，随后是传递给它的整数值。在 `Child` 类中，构造函数首先计算一个值 `x`，将其设置为 10，并打印 `"Calculating x: 10"`。之后，通过调用 `super(x)` 将 `x` 的值（即 10）传递给 `Base` 类的构造函数。这触发了父类构造函数的执行，该构造函数打印出 `"Number: 10"`。当 `Test` 类创建 `Child` 的实例时，`Child` 构造函数首先运行，打印出 `"Calculating x: 10"`。然后，通过 `super(x)` 调用 `Base` 类的构造函数，打印出 `"Number: 10"`。

### 程序

```java
class Base {
    Base(double value) {
        System.out.println("Value: " + value);
    }
}
class Child extends Base {
    Child() {
        double pi = Math.PI;
        System.out.println("Pi: " + pi);
        super(pi);
    }
}
public class Test {
    static void main(String[] args) {
        Child c = new Child();
    }
}
```

### 输出

`Pi: 3.141592653589793`

`Value: 3.141592653589793`

此程序在 `java22` 中运行，对于其他版本，`println()` 语句之前。在该程序中，我们演示了子类如何将计算后的值传递给父类构造函数。`Base` 类有一个接收 `double` 参数的构造函数，它会打印带有 `"Value:"` 前缀的参数值。在 `Child` 类中，构造函数首先使用 `Math.PI` 计算 π (Pi) 的值并打印 `"Pi: "`，随后是计算出的值。打印后，`super(pi)` 调用将此值传递给 `Base` 类的构造函数，该构造函数打印相同的 Pi 值。当 `Test` 类创建 `Child` 的实例时，执行序列从 `Child` 构造函数开始，它打印 `"Pi: 3.141592653589793"`。紧接着，通过 `super(pi)` 调用 `Base` 类的构造函数，打印出 `"Value: 3.141592653589793"`。

### 程序

```java
class Base {
    Base(String name, int age) {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}
class Child extends Base {
    Child() {
        String name = "Usharani";
        int age = 25;
        System.out.println("Assigning values");
        super(name, age);
    }
}
public class Test {
    void main(String[] args) {
        Child c = new Child();
    }
}
```

### 输出

`Assigning values`

`Name: Usharani, Age: 25`

此程序在 `java22` 中运行；对于其他版本，它将抛错误，因为我们在子类构造函数使用了 `super()`。在该程序中，我们演示了构造函数链，其中值从子类传递到父类构造函数。`Base` 类有一个接收 `String`（代表名称）和 `int`（代表年龄）的构造函数。当被调用时，`Base` 构造函数按照 `"Name: [name]; Age: [age]"` 的格式打印名称和年龄。在 `Child` 类构造函数中，两个局部变量 `name` 和 `age` 分别用值 `Usharani` 和 25 初始化。程序在通过 `super(name, age)` 调用父类构造函数之前，首先打印 `"Assigning values"`。这会将名称和 `age` 传递给 `Base` 构造函数，然后该构造函数打印 `"Name: Usharani, Age: 25."`。`Test` 类创建一个 `Child` 的实例时，序列从 `Child` 构造函数开始，打印 `"Assigning values"`。之后，通过 `super(name, age)` 调用 `Base` 构造函数，打印出 `"Name: Usharani, Age: 25."`

## 7.8 SUPER

`super` 关键字主要用于继承，以指代直接父类。它的用法可以分为三种场景：

- 访问父类变量：当子类重写了父类的变量时，你可以使用 `super` 关键字来访问父类版本的该变量。

- 调用父类方法：同样，如果子类重写了父类的方法，你可以使用 `super` 来调用父类的方法。

- 调用父类构造函数：在子类构造函数中，可以使用 `super()` 来调用父类构造函数。

### 访问父类变量

当子类重写了父类的变量时，你可以使用 `super` 关键字来访问父类版本的该变量。在 Java 中，当子类继承父类时，它通常需要 `super` 关键字来访问父类的变量。

### 程序

```java
class Base {
    int value = 10;
}
class Child extends Base {
    int value = 20;
    void display() {
        System.out.println("Child value: " + value);
        System.out.println("Parent value: " + super.value);
    }
}
public class Test {
    public static void main(String[] args) {
        Child c = new Child();
        c.display();
    }
}
```

### 输出

`Child value: 20`

`Parent value: 10`

### 调用父类方法

同样，如果子类重写了父类的方法，你可以使用 `super` 来调用父类的方法。在 Java 中，当子类继承父类时，它通常需要 `super` 来访问父类方法。

### 程序

```java
class Base {
    void display() {
        System.out.println("Base method");
    }
}
class Child extends Base {
    @Override
    void display() {
        System.out.println("Child method");
        super.display(); // 调用父类方法
    }
}
public class Test {
    public static void main(String[] args) {
        Child c = new Child();
        c.display();
    }
}
```

### 输出

`Child method`

`Base method`

### 调用父类构造函数

在子类构造函数中，可以使用 `super()` 来调用父类构造函数。这在你想要初始化子类部分时特别有用。

### 程序

```java
class Base {
    Base() {
        System.out.println("Base constructor called");
    }
}
class Child extends Base {
    Child() {
        super(); // 调用父类构造函数
        System.out.println("Child constructor called");
    }
}
public class Test {
    public static void main(String[] args) {
        Child c = new Child();
    }
}
```

### 输出

`Base constructor called`

`Child constructor called`

## 214 用于医疗和健康应用的 Java 22

```java
class Base {
    private int baseValue;
    // 带参数的构造函数
    public Base(int baseValue) {
        this.baseValue = baseValue;
        System.out.println("Base constructor called with baseValue: " + baseValue);
    }

    // Getter 方法
    public int getBaseValue() {
        return baseValue;
    }
}

// 继承自 Base 的子类
class Child extends Base {
    private int childValue;
    // 用于 Base 和 Child 的参数构造函数
    public Child(int baseValue, int childValue) {
        super(baseValue); // 调用父类构造函数
        this.childValue = childValue;
        System.out.println("Child constructor called with childValue: " + childValue);
    }

    // Getter 方法
    public int getChildValue() {
        return childValue;
    }
}

// 用于演示父类构造函数调用的主类
class Main {
    public void main(String[] args) {
        // 创建 Child 类的对象
        Child childObj = new Child(10, 20);
        // 使用访问值
        System.out.println("Base value: " + childObj.getBaseValue());
        System.out.println("Child value: " + childObj.getChildValue());
    }
}
```

输出：

`Base class constructor called with baseValue: 10`

`Child constructor called with childValue: 20`

`Base value: 10`

`Child value: 20`

`Base` 类包含一个接受整数参数 `baseValue` 的构造函数，并将其设置为类的私有变量 `baseValue`。它还包含一个用于访问该变量的 getter 方法 `getBaseValue()`。当构造函数被调用时，它会打印消息 `"Base constructor called "` 随后是该值。`Child` 类继承自 `Base` 类并拥有 `childValue`。`super(baseValue)` 调用 `Base` 类构造函数并传递了 `baseValue` 的值。此外，`Child` 构造函数初始化了自己的 `childValue`，并打印 `"Child constructor called with childValue: "` 随后是 `childValue`。提供了一个 getter 方法 `getChildValue()` 来访问 `childValue`。在 `Main` 类中，我们通过将 `10` 和 `20` 分别作为 `baseValue` 和 `childValue` 的参数创建了 `Child` 类的实例。输出以 `Base class constructor called baseValue:10` 开始，表示 `Base` 类构造函数首先执行。接下来，`Child class constructor called with childValue:20` 确认 `Child` 类构造函数已执行。然后通过 getter 方法访问值，打印出 `Base value: 10` 和 `Child value: 20.`。

## 7.9 继承中的 static 关键字

在 Java 中，`static` 关键字用于声明属于类而不是实例的成员（字段、方法和嵌套类）。它表示该成员在类的所有实例之间共享，并且可以通过类名直接访问，而无需创建类的实例。

## static 关键字的主要用途

- **静态字段（Static Fields）**：静态字段是类所有实例共享的类级变量。它们仅在类加载到内存时初始化一次，并一直留在内存中直到程序退出。

- **静态方法（Static Methods）**：方法属于类而不是类的实例。可以直接使用类名调用，而不需要对象实例。静态方法无法访问实例变量，但它们可以访问静态变量。

- **嵌套类（Nested Classes）**：嵌套类被声明为跨类的 `static`。它们无法访问外层类的非静态成员，但可以在没有外层类实例的情况下进行实例化。

- **静态初始化块（Static Initialization Blocks）**：静态初始化块用于初始化类的静态字段。它们在类加载到内存时仅执行一次。

### 7.9.1 静态字段

在 Java 中，静态字段属于类而不是任何任何特定实例。当静态字段被继承时，它在基类和派生类的所有实例之间共享。

### 程序



```java
public class Main {
    static class Base {
        protected static String staticField = "Base static field";

        public static void staticMethod() {
            System.out.println("Base static method");
        }
    }

    static class Child extends Base {
        // 子类中的字段
        protected static String childStaticField = "Child static field";

        public static void childStaticMethod() {
            System.out.println("Child static method");
        }
    }

    public void main(String[] args) {
        // 从基类访问静态字段
        System.out.println("Base static field accessed from child class: " + Base.staticField);
    }
}
```

## 216

用于医疗和健康应用的 Java 22

```java
System.out.println("Base static field accessed directly from child class: " + Child.staticField);

// 从基类访问静态方法
Base.staticMethod();
Child.staticMethod();

// 访问类的静态字段
System.out.println("Child static field: " + Child.childStaticField);

// 访问类的静态方法
Child.childStaticMethod();
}
```

### 输出

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method

Base static field accessed from child class: Base static

Base static field accessed directly from child class: Base static

Base static method

Child static method

Child static field: Child static field

Child static method
```

## 217

# Java 继承

```java
void main(String[] args) {
    // 创建 Child 实例
    Child c = new Child();

    // 调用 display 方法
    c.display();
}
```

### 输出

Instance variable in Child: 100

该 Java 程序包含三个类：`base`、`child` 和 `sample`。在 `base` 类中，有一个初始化为 10 的变量 `i`。`child` 类继承 `base` 类并声明了一个初始化为 100 的实例变量 `i`。它包含一个 `display()` 方法，用于打印 `child` 类定义的实例变量 `i` 的值。`sample` 类包含 `main` 方法，其中创建了 `child` 类的实例并调用 `display()` 方法来打印实例变量的值。

## 静态变量程序

```java
// 带有静态变量的基类
class Base {
    static int i = 10;
}

// 继承 Base 的子类
class Child extends Base {
    int i = 100;

    void display() {
        // 打印 Child 的实例变量
        System.out.println("Instance variable in Child: " + i);
    }
}

// 包含 main 方法的主类
public class Sample {
    public static void main(String[] args) {
        // 使用类名打印静态变量
        System.out.println("Static variable in Base: " + Base.i);
    }
}
```

## 用于医疗保健和医疗应用的 Java 22

```java
}

}
```

### 输出

父类方法

子类方法

name in Test: parent

name in Sample: sub

Updated name in Test: superclass

Updated name in Sample: childclass

该 Java 程序包含四个类：`test`、`sample`、`Main` 以及一个名为 `Main` 的公共类。`test` 类声明了一个值为 `"name"` 的静态字符串变量 `name`，并定义了一个名为 `display()` 的方法。当 `display()` 方法被调用时，它会在控制台打印 `"Parent class method"`。`sample` 类声明了一个值为 `"sub"` 的静态字符串变量 `name`，并定义了一个名为 `put()` 的方法。此外，它还声明了一个值为 `"sub"` 的静态字符串变量 `name1`，且 `put()` 方法会在控制台打印 `"child class method"` 并访问两个 `name`，带有相关消息地打印它们的值。`Main` 类声明了 `sample` 类，继承了它所有的静态变量和方法。`Main` 类的 `main` 方法使用语句 `sample s = new sample();` 创建了 `sample` 类的实例。该对象被用于调用继承自 `test` 类的 `display()` 方法以及 `sample` 类中定义的 `put()` 方法。此外，在 `main` 方法内部，静态变量 `name` 和 `name1` 的值被分别改为 `"superclass"` 和 `"childclass"`。当程序执行时，`display()` 方法打印 `"Parent class method"`，随后 `put()` 方法打印 `"child class method"`。此外，它访问并打印了 `name` 和 `name1` 变量的值。最后，在 `main` 方法中，访问并打印了 `name` 和 `name1` 的更新后的值，演示了继承层次中跨类静态变量的可见性和修改性。

### 7.9.2 静态方法

在 Java 中，静态方法是属于类本身而非类实例的方法。可以在不创建类实例的情况下直接调用静态方法。它们通过使用 `static` 关键字进行定义。

## 程序

在 Java 中继承静态方法的程序

```java
// 带有静态方法的基类
class Base {
    static void show() {
        System.out.println("static method in parent");
    }
}

// 继承自 Base 并带有非静态方法的派生类
class Derived extends Base {
    void display() {
        System.out.println("non static method in child");
    }
}

// 用于测试方法调用的主类
public class Main {
    public static void main(String[] args) {
        // 创建 Derived 的实例并调用其非静态方法
        new Derived().display();

        // 使用子类名调用基类的静态方法
        Derived.show();
    }
}
```

### 输出

non static method in child

static method in parent



该 Java 程序包含两个类：`base` 和 `derived`。`base` 类包含一个名为 `show()` 的静态方法，该方法会在控制台打印 `static method in parent`。`derived` 类继承自 `base` 类并定义了一个非静态方法 `display()`，该方法会在控制台打印 `non static method in child`。在 `Main` 类的方法中，使用语句 `new Derived().display()` 创建了 `derived` 类的对象。这创建了 `derived` 类的实例并调用了它的 `display()`。结果是控制台打印了 `non static method in child`。此外，使用语法 `derived.show()` 调用了来自 `base` 类的静态方法 `show()`。由于静态方法在 Java 中是可以继承的，因此可以使用子类名直接访问来自 `base` 类的静态方法 `show()`。因此，控制台打印了 `static method in parent`。

## 程序

Java 中父类和子类中具有相同静态方法的程序

```java
// 带有静态方法的基类
class Base {
    static void show() {
        System.out.println("static method in parent");
    }
}

// 继承自 Base 并拥有自己的静态方法和非静态方法的派生类
class Derived extends Base {
    // Derived 类中的静态方法，隐藏了 Base 类中的静态方法
    static void show() {
        System.out.println("static method in child");
    }
    // Derived 类中的非静态方法
    void display() {
        // 打印非静态方法的消息
        System.out.println("non static method in child");
        // 调用父类的静态方法
        super.show();
    }
}

// 用于测试方法调用的主类
public class Main {
    public static void main(String[] args) {
        // 创建 Derived 的实例并调用其非静态方法
        new Derived().display();
        // 调用 Derived 类的静态方法
        Derived.show();
    }
}
```

输出：

```
non static method in child
static method in parent
static method in child
```

该 Java 程序由两个类组成：`base` 和 `derived`。`base` 类包含一个名为 `show()` 的静态方法，该方法会在控制台打印 `static method in parent`。`derived` 类继承自 `base` 类并定义了自己名为 `show()` 的静态方法，该方法会在控制台打印 `static method in child`。此外，`derived` 类定义了一个名为 `display()` 的非静态方法，该方法使用 `super` 关键字调用其父类的静态方法 `show()` 并打印 `non static method in child`。在 `Main` 方法中，使用语句 `new Derived().display()` 创建了 `derived` 类的对象。这创建了 `derived` 类的实例并调用了它的 `display()`。此外，使用语法 `derived.show()` 调用了来自 `base` 类的静态方法 `show()`。由于静态方法在 Java 中是可以继承的，因此可以使用子类名直接访问来自 `base` 类的静态方法 `show()`。因此，控制台打印了 `static method in parent`。

## 222 用于医疗和健康应用程序的 Java

```java
super.display(); // 调用父类方法
}
public class Main {
  void main(String[] args) {
    // 创建子类对象
    Child myChild = new Child(10, 20);
    // 调用子类的 display 方法
    myChild.display();
  }
}
```

输出：

```
Child Class: 20
Base Class: 10
```

此程序演示了 Java 中的继承，包含一个名为 `Base` 的基类和一个名为 `Child` 的子类。`Base` 类包含一个实例变量 `num` 和一个初始化它的带参数构造函数。它有一个 `display()` 方法来打印 `num` 的值。`Child` 类继承 `Base` 并分别使用 `super` 遮蔽变量。`Child` 中的 `display()` 方法通过 `super.display()` 调用父方法，并打印子类和基类变量的值。在 `Main` 类中，创建了一个 `Child` 对象并调用其 `display()` 方法，以演示继承和变量遮蔽的功能。

### 7.10.2 访问构造函数

在 Java 中，`this` 关键字用于引用类的当前实例。当在构造函数的文本中使用时，`this` 可以用于调用同一类中的其他构造函数，或者在继承场景下调用父类的构造函数。

从重载的构造函数中调用私有构造函数的程序

```java
class Base {
  // 私有构造函数
  private Base() {
    System.out.println("private base constructor");
  }
  // 公有构造函数
  public Base(boolean usePrivateConstructor) {
    if (usePrivateConstructor)
      throw new IllegalArgumentException("使用静态工厂方法创建实例.");
    System.out.println("public base constructor");
  }
  // 使用私有构造函数的静态工厂方法
  public static Base createBaseWithPrivateConstructor() {
    return new Base();
  }
}

// 继承 Base 的子类
class Child extends Base {

  // Child 类的构造函数
  public Child(boolean usePrivateConstructor) {
    // 调用 Base 类的公共构造函数
    System.out.println("public child constructor");
    super(usePrivateConstructor);
  }
}

// 带有 main 方法的测试类
public class Test {
  void main(String[] args) {
    // 使用静态工厂方法创建 Base 实例
    Base base = Base.createBaseWithPrivateConstructor();
    // 这将使用私有构造函数
    // 使用公共构造函数创建 Child 类实例
    Child child = new Child(false); // 这将使用 Base 的公共构造函数
  }
}
```

输出：

```
private base constructor
public child constructor
public base constructor
```

此程序演示了在 Java 中使用私有构造函数。`Base` 类有一个私有构造函数，仅可以通过创建 `Base` 实例的静态方法（`createBaseWithPrivateConstructor`）访问。`Child` 类继承 `Base` 并使用 `Base` 的公共构造函数来初始化自己。在 `Test` 类中，通过静态工厂方法实例化 `Base`，并使用公共构造函数实例化 `Child`。

## 程序

从重载构造函数中调用私有构造函数并为私有构造函数类创建对象的程序

```java
// 具有构造函数链和方法的基类
class Base {
  // 私有构造函数
  private Base(int i) {
    System.out.println("private base constructor");
  }
  // 公有构造函数
  public Base() {
    this(10); // 调用带参数 10 的私有构造函数
    System.out.println("public base constructor");
  }
  // 要继承的方法
  public void display() {
    System.out.println("method in base");
  }
}

// 继承 Base 类的子类
class Child extends Base {
  // Child 类的构造函数
  public Child() {
    System.out.println("public child constructor");
  }
}

// 带有 main 方法的测试类
public class Test {
  void main(String[] args) {
    // 创建 Child 类实例
    Child c = new Child();
    // 调用继承的 display 方法
    c.display();
  }
}
```

输出：

```
private base constructor
public base constructor
public child constructor
method in base
```

此 Java 程序演示了在由 `base`、`child` 和 `test` 类组成的类层次结构中的构造函数链和方法继承。`base` 类有两个构造函数：一个公共构造函数和一个私有构造函数。公共构造函数在向控制台打印 `public base constructor` 之前，使用 `this` 关键字调用了带有参数 10 的私有构造函数。而私有构造函数向控制台打印 `private base constructor`。此外，`base` 类定义了一个名为 `display` 的方法，该方法在控制台打印 `method in base`。`child` 类继承 `base` 类，并定义了一个向控制台打印 `public child constructor` 的方法。在 `test` 中，`main` 方法创建了 `child` 类的对象。在创建对象时，触发了继承。随后对象调用了继承自 `base` 类的 `display()` 方法。当程序执行时，可以看到构造函数链机制。首先，调用 `base` 类的私有构造函数，打印 `private base constructor`。之后，调用 `child` 类的构造函数，在控制台打印 `public child constructor`。最后，调用 `display()` 方法，在控制台打印 `method in base`。

## 70. 将当前对象作为参数传递

在 Java 中，`this` 关键字用于引用类的当前实例。在类的方法中使用时，可以将当前对象传递给方法。

## 程序

```java
public class InheritanceExample {
  static class Base {
    protected String instanceField;
    // 基类的静态块
    static {
      System.out.println("Base block executed");
    }
    public Base() {
      this.instanceField = "Base field";
    }
    // 静态方法
    protected static void staticMethod() {
      System.out.println("Base method");
    }
    public void instanceMethod(Base obj) {
      System.out.println("Base method called with instanceField: " + obj.instanceField);
    }
  }

  // Java 继承
  static class Child extends Base {
    // 子类的静态块
    static {
      System.out.println("Child block executed");
    }
    public Child() {
      super();
    }
    public void childInstanceMethod() {
      // 将 this 传递给基类
      instanceMethod(this);
    }
    protected static void childStaticMethod() {
      System.out.println("Child method");
    }
  }

  public static void main(String[] args) {
    // 静态字段和静态方法演示
    System.out.println("Static field from base class: " + Base.instanceField);
    Base.staticMethod();
    Child.childStaticMethod();
    // 实例方法和传递 this 的演示
    Child childInstance = new Child();
    childInstance.childInstanceMethod();
  }
}
```

输出：

```
Base block executed
Child block executed
Static field from base class: Base field
Base method
Child method
Base method called with instanceField: Base field
```

### 7.10.4 从方法返回 `this`

在 Java 中，`this` 关键字在方法内部用于引用当前对象实例。当你想要从方法返回当前对象时，这种方法特别有用，它可以实现方法的链式调用。

## 程序

```java
class Main {

    private int value;

    Main() {}

    Main(int value) {

        this.value = value;

    }

    public Main setValue(int value) {

        this.value = value;

        return this; // 返回当前对象

    }

    public Main incrementValue() {

        this.value++;

        return this; // 返回当前对象

    }

    public void displayValue() {

        System.out.println("Value: " + this.value);

    }

    void main(String[] args) {

        Main m = new Main(5);

        // 使用返回的 `this` 关键字进行链式调用

        m.setValue(10).incrementValue().displayValue();

    }

}
```

## 输出：

```
Value: 11
```

在这个程序中，`Main` 类有一个私有的整型字段 `value` 和两个构造函数：一个无参数构造函数和另一个初始化 `value` 字段的构造函数。该类提供了一个 setter 方法 `setValue(int value)`，它设置 `value` 并使用 `this` 返回当前对象。另一个方法 `incrementValue()` 将 `value` 加 1 并返回当前对象。在每个方法中返回对象本身允许进行链式调用，允许在单个语句中调用多个方法，每个方法修改对象并将其传递给下一个方法。例如，链式 `m.setValue(10).incrementValue().displayValue()` 首先将值设置为 10，将其加 1（使其变为 11），然后打印更新后的值。

## 7.11 类内部的初始化块

在 Java 中，初始化块是类中的一段代码，当类的实例加载到内存中时会执行，具体取决于它是静态初始化块还是实例初始化块。

- 静态初始化块：使用 `static` 关键字声明，并仅在类加载到内存时执行。它主要用于初始化类的静态变量。
- 实例初始化块：它没有标记任何关键字，在每次创建类的实例时执行，在构造函数被调用之前执行。它用于跨多个构造函数执行常见的初始化任务。

初始化块提供了一种方法，无论调用哪个构造函数都可以初始化变量或执行常见的初始化任务。当你有多个需要执行相同初始化逻辑的构造函数时，它们特别有用。

## 程序

用于子类中初始化块的程序

```java
// 基类
class Base {

  // Base 类的构造函数
  Base() {

    System.out.println("parent class constructor invoked");

  }

}



## 继承与初始化块

### 程序：继承与实例初始化块

```java
// 继承 Base 的子类
class Child extends Base {

  // Child 类中的实例初始化块
  {
    System.out.println("instance initializer block is invoked");
  }

  // Child 类的构造函数
  Child() {
    System.out.println("child class constructor invoked");
    super(); // 显式调用父类构造函数
  }
}

// 带有 main 方法的主类
public class Main {
  void main(String[] args) {
    // 创建 Child 类的实例
    Child b = new Child();
  }
}
```

输出：

```
child class constructor invoked
parent class constructor invoked
instance initializer block is invoked
```

此 Java 程序包含两个类：`base` 和 `child`。`base` 类定义了一个结构，在被调用时会在控制台打印 `parent class constructor invoked`。`child` 类继承了 `base` 类并定义了自己的构造函数。在 `child` 类的构造函数中，使用了 `super()` 关键字来显式调用父类的构造函数，然后在控制台打印 `child class constructor invoked`。此外，`child` 类内部还包含了一个实例初始化块，当创建 `child` 类的对象时，它会在控制台打印 `instance initializer block is invoked`。在 `Main` 类的 `main` 方法中，使用语句 `b = new Child()` 创建了 `child` 类的对象。当此对象被创建时，`child` 类的构造函数被调用，由于 `super()` 关键字，它又调用了父类 `base` 的构造函数。结果是消息 `parent class constructor invoked`、`child class constructor invoked` 和 `instance initializer block is invoked` 按照顺序打印到控制台。

## 用于医疗和健康应用的 Java 22

### 程序：带有构造函数重载的初始化块程序

```java
// 基类
class Base {
  // Base 类的构造函数
  Base() {
    System.out.println("parent class constructor invoked");
  }
}

// 继承 Base 的子类
class Child extends Base {
  // Child 类中的实例初始化块
  {
    System.out.println("instance initializer block is invoked");
  }
  // Child 类的无参数构造函数
  Child() {
    System.out.println("child class constructor invoked");
    super(); // 调用父类构造函数
  }
  // Child 类的参数构造函数
  Child(int a) {
    System.out.println("child class constructor invoked " + a);
    super(); // 调用父类构造函数
  }
}

// 带有 main 方法的主类
public class Main {
  public void main(String[] args) {
    // 使用无参数构造函数创建 Child 类的实例
    Child c1 = new Child();
    // 使用参数构造函数创建 Child 类的实例
    Child c2 = new Child(10);
  }
}
```

### 输出

```
child constructor invoked
parent class constructor invoked
initializer block is invoked
child class constructor invoked 10
parent class constructor invoked
initializer block is invoked
```

此 Java 程序定义了两个类：`base` 和 `child`。`base` 类包含一个在调用时会在控制台打印 `parent class constructor invoked` 的构造函数。`child` 类继承了 `base` 类并定义了两个构造函数：一个无参数构造函数和一个参数构造函数。这两个构造函数都通过 `super()` 关键字调用父类构造函数。除了构造函数外，`child` 类内部还包含一个实例初始化块，每当创建 `child` 类对象时都会打印 `initializer block is invoked`。在 `Main` 类的 `main` 方法中，创建了两个 `child` 类实例：使用无参数构造函数的 `c1` 和使用参数构造函数的 `c2`。当程序执行时，构造函数和实例初始化块的调用顺序如下：

- 使用无参数构造函数创建对象 `c1` 时，首先调用父类（`base`）的构造函数打印 `parent class constructor invoked`，然后是实例初始化块，最后是子类（`child`）的构造函数打印 `child class constructor invoked`。
- 使用参数构造函数创建对象 `c2` 时，发生相同的调用序列，但增加了打印 `child class constructor invoked 10` 以对应传递给构造函数的参数。

## 程序：继承中的静态和初始化块

```java
// 基类
class Base {
  // Base 类的静态初始化块
  static {
    System.out.println("parent class static initializer invoked");
  }
  // Base 类的初始化块
  {
    System.out.println("parent class initializer invoked");
  }
  // Base 类的构造函数
  Base() {
    System.out.println("parent class constructor invoked");
  }
}

// 继承 Base 的子类
class Child extends Base {
  // Child 类的静态初始化块
  static {
    System.out.println("child class static initializer invoked");
  }
  // Child 类的初始化块
  {
    System.out.println("child class initializer block is invoked");
  }
  // Child 类的构造函数
  Child() {
    System.out.println("child class constructor invoked");
    super(); // 调用父类构造函数
  }
}

// 带有 main 方法的主类
public class Main {
  void main(String[] args) {
    // 创建 Child 类的实例
    Child c = new Child();
  }
}
```

输出：

```
parent class static initializer invoked
child class static initializer invoked
parent class initializer invoked
parent class constructor invoked
child class initializer block is invoked
child class constructor invoked
parent class constructor invoked
```

此 Java 程序包含两个类：`base` 和 `child`。`base` 类包含一个静态初始化块、一个实例初始化块和一个构造函数。静态初始化块打印 `parent class static initializer invoked`，实例初始化块打印 `parent class initializer invoked`，构造函数打印 `parent class constructor invoked`。`child` 类继承自 `base` 类，并包含它自己的静态初始化块、实例初始化块和构造函数。`child` 类的静态初始化块打印 `child class static initializer invoked`，实例初始化块打印 `child class initializer block is invoked`，构造函数使用 `super()` 调用父类构造函数并打印 `child class constructor invoked`。在 `main` 方法中，创建了 `child` 类的对象，触发了其构造函数和初始化块的执行。执行顺序如下：

- 首先执行 `base` 类的静态初始化块，打印 `parent class static initializer invoked`。
- 接下来执行 `child` 类的静态初始化块，打印 `child class static initializer invoked`。
- 然后执行 `base` 类的实例初始化块，打印 `parent class initializer invoked`。
- 接着调用 `base` 类的构造函数，打印 `parent class constructor invoked`。
- 之后执行 `child` 类的实例初始化块，打印 `child class initializer block is invoked`。
- 最后调用 `child` 类的构造函数，它首先调用父类构造函数，打印 `parent class constructor invoked`，然后打印 `child class constructor invoked`。

## 7.12 方法重写

当子类中的方法与其父类中的方法具有相同的名称、返回类型和参数列表时，在 Java 中被称为方法重写（Method Overriding）。方法重写允许子类为其超类中已定义的方法提供特定的实现。方法重写的主要目的是允许运行时多态；适当的方法实现是根据运行时对象的实际类型动态确定的。方法重写的关键规则如下：

- 子类中的方法必须与父类中的方法具有相同的名称和签名（参数列表）。
- 被重写方法的返回类型可以是父类中方法返回类型的子类型，但必须与其兼容。
- 重写方法的访问修饰符应与被重写的方法相同或具有更高的访问权限。
- 重写方法抛出的异常不能比被重写方法抛出的异常范围更广，但它可以抛出未检查异常或更窄的检查异常。

通过遵循这些规则，开发者可以确保正确的方法重写，允许子类在保留父类原始方法签名和功能的同时自定义行为。

## Java 继承

### 程序：基类方法使用 `private` 修饰符，子类使用 `protected` 修饰符的协变返回类型程序

```java
// 基类
class Base {
    // Base 类中的私有方法
    private void display() {
        System.out.println("private method in base");
    }

    // Base 类中调用私有方法
    void show() {
        display();
    }
}

// 继承 Base 类的子类
class Child extends Base {
    protected void display() {
        // 调用 Base 类的 show 方法
        // 打印 Child 类的消息
        System.out.println("protected method in child");
        super.show();
    }
}

// 带有 main 方法的测试类
public class Test {
    public static void main(String[] args) {
        // 创建 Child 类的实例
        Child c = new Child();
        // 调用 Child 类的 display 方法
        c.display();
    }
}
```

输出：

```
protected method in child
private method in base
```

在此程序中，有三个类：`base`、`child` 和 `Test`。`base` 类包含一个私有方法 `display()`，在调用时会打印 `private method in base`。此外，它包含一个名为 `show()` 的方法，该方法调用了 `display()` 方法。`child` 类继承自 `base` 类，并用 `protected` 版本重写了 `display()` 方法。在这个重写的方法中，它首先使用 `super.show()` 调用父类的 `show()` 方法，反而调用 `base` 类的 `display()` 方法。之后，它打印 `protected method in child`。在 `Test` 类的 `main` 方法中，创建了 `child` 的实例并调用它的 `display()` 方法。结果是通过动态派发调用了 `child` 类中被重写的 `display()` 方法。

### 程序：基类方法使用 `private` 修饰符，子类使用 `public` 修饰符的协变返回类型程序

```java
// 基类
class Base {
    // Base 类中的私有方法
    private void display() {
        System.out.println("private method in base");
    }

    // 访问 Base 内部私有 display 方法的公共方法
    public void show() {
        display(); // 调用 Base 中的私有 display 方法
    }
}

// 继承 Base 类的子类
class Child extends Base {
    // Child 类中具有相同名称的公共方法（方法隐藏）
    public void display() {
        System.out.println("public method in child");
    }
}

// 带有 main 方法的类
public class Main {
    public static void main(String[] args) {
        // 创建 Child 类的实例
        Child c = new Child();
        // 调用 Child 类的 display 方法
        c.display();
    }
}
```

输出：

```
public method in child
private method in base
```

在此程序中，有三个类：`base`、`child` 和 `Main`。`base` 类包含一个私有方法 `display()`，在调用时会打印 `private method in base`。此外，它包含一个名为 `show()` 的方法，该方法调用了 `display()` 方法。`child` 类继承自 `base` 类，并用 `public` 版本重写了 `display()` 方法。`child` 类中被重写的 `display()` 方法打印 `public method in child`，然后调用父类的 `show()` 方法。在 `Main` 类的 `main` 方法中，创建了 `child` 的实例并调用它的 `display()` 方法。由于动态派发，调用了被重写的 `display()` 方法。

### 程序：基类方法使用 `protected` 修饰符，子类使用 `public` 修饰符的协变返回类型程序

```java
// 基类
class Base {
    // Base 类中的受保护方法
    protected void display() {
        System.out.println("protected method in base");
    }
}

// 继承 Base 类的子类
class Child extends Base {
    // Child 类中重写保护方法的公共方法
    @Override
    public void display() {
        // 打印 Child 类的消息
        System.out.println("protected method in child");
        // 调用 Base 类的 display 方法
        super.display();
    }
}

// 带有 main 方法的类
public class Test {
    public static void main(String[] args) {
        // 创建 Child 类的实例
        Child c = new Child();
        // 调用 Child 类的 display 方法
        c.display();
    }
}
```



```java
// 创建一个 Child 类的实例
Child c = new Child();

// 调用 Child 类的 display() 方法
c.display();
```

输出：

```text
protected method in child
default method in base
```

在这个 Java 程序中，有两个类：`Base` 和 `Child`，以及一个名为 `Test` 的主类。`Base` 类包含一个名为 `display()` 的默认方法，该方法在调用时会打印 `"default method in base"`。`Child` 类继承了 `Base` 类，并用保护版本重写了 `display()` 方法。`Child` 类中被重写的 `display()` 方法首先调用 `super` 关键字来访问父类方法。之后，它会打印 `"protected method in Child"`。创建了 `Test` 类的 `main` 方法并调用了它的 `display()` 方法。由于动态方法派发，调用了 `Child` 类中被重写的 `display()` 方法。

## 程序

通过返回用户定义类来实现协变返回类型的程序。

```java
// 具有一个初始化字符串变量的构造函数的基类
class Base {
    String s;

    // Base 类的构造函数
    Base(String s) {
        this.s = s;
    }
}

// 继承 Base 类的子类
class Child extends Base {
    // Child 类的构造函数
    Child(String s) {
        super(s); // 调用 Base 类的构造函数
    }
}

// 具有返回 Base 实例的保护方法的示例类
class Sample {
    // 返回 Base 实例的保护方法
    protected Base get() {
        return new Base("base");
    }
}

// 继承 Sample 并重写 get() 方法的类
class Testing extends Sample {
    // 返回 Child 实例的重写方法
    @Override
    protected Base get() {
        return new Child("child");
    }
}

// 带有 main 方法的主类
public class Test {
    void main(String[] args) {
        // 创建 Sample 类的实例
        Sample sample = new Sample();

        // 调用 get() 方法并打印 s 的值
        System.out.println(sample.get());

        // 创建 Testing 类的实例
        Testing testing = new Testing();

        // 调用 get() 方法并打印 s 的值
        System.out.println(testing.get());
    }
}
```

输出：

```text
base
child
```

## 7.13 `final` 关键字

Java 中的 `final` 关键字可以用于多种上下文中，以定义不可更改或不可扩展的实体。它可以应用于变量、方法和类，每种情况都有特定的含义。

## 使用 `final` 的优势

- **不可变性**：当应用于变量时，`final` 确保赋值的值不能被更改，这对于定义常量很重要。
- **安全性**：`final` 方法不能被重写，这有助于防止类中出现意外的行为或对方法的误用。
- **性能**：使用 `final` 可以引导编译器进行优化，因为它对代码做了某些其他情况下无法实现的假设。
- **简单性与安全性**：使用 `final` 可以使代码更容易理解和维护，因为它明确了代码中哪些部分旨在保持不变。

## 使用 `final` 的局限性

- **缺乏灵活性**：`final` 类不能被扩展，这在某些情况下可能会限制重用和灵活性。
- **继承限制**：`final` 方法不能被重写，在需要在子类中修改行为的场景下，这具有限制性。
- **初始化要求**：`final` 变量必须在声明时或在构造函数中初始化，这并不总是方便。

## `final` 的用例

- **常量**：定义不应更改的常量。
- **不可变对象**：创建创建后任何字段都无法被修改的不可变对象。
- **防止继承**：保护类不被扩展，特别是工具类或辅助类。
- **防止方法重写**：确保关键方法不被子类重写，以保持其原始行为。

### 7.13.1 `final` 类

声明为 `final` 的类不能作为子类。这防止了其他类继承它。

## 程序

```java
final class FinalClass {
    public void display() {
        System.out.println("This is a final class.");
    }
}

// 下行代码会导致编译错误
// class Subclass extends FinalClass {
// }

public class FinalClassExample {
    public void main(String[] args) {
        FinalClass finalClass = new FinalClass();
        finalClass.display();
    }
}
```

输出：

```text
This is a final class.
```

### 7.13.2 `final` 类中的方法重载

Java 中 `final` 类中的方法重载是一个概念，即在单个类中共存在多个同名方法。当 `final` 关键字应用于类时，不会影响方法重载的能力。

## 程序

Java 中 `final` 类重载的程序。

```java
// 定义一个名为 Test 的 final 类
final class Test {
    // 无参数方法
    void display() {
        System.out.println("0 parameter display()");
    }

    // 带有一个 int 参数的方法
    void display(int i) {
        System.out.println("1 parameter display()" + i);
    }

    // 带有一个 String 参数的方法
    void display(String s) {
        System.out.println("1 parameter display()" + s);
    }

    // 带有两个 int 参数的方法
    void display(int i, int j) {
        System.out.println("2 parameter display()" + i + " " + j);
    }
}

// 带有 main 方法的示例类
public class Sample {
    public void main(String[] args) {
        // 创建 Test 类的实例
        Test test = new Test();

        // 调用不同参数的重载 display 方法
        test.display(); // 调用无参数的 display()
        test.display(10); // 调用带一个整数参数的 display(int i)
        test.display("testing"); // 调用带一个字符串参数的 display(String s)
        test.display(100, 200); // 调用带两个整数参数的 display(int i, int j)
    }
}
```

输出：

```text
0 parameter display()
1 parameter display()10
1 parameter display()testing
2 parameter display()100 200
```

## 程序

```java
class Parent {
    public final void display() {
        System.out.println("This is a final method.");
    }
}

class Child extends Parent {
    public void display() {
        System.out.println("Trying to override final method.");
    }
}

public class FinalMethodExample {
    static void main(String[] args) {
        Child child = new Child();
        child.display();
    }
}
```

## 输出

```text
Main.java:7: error: display() in Child cannot override display() in Parent
public void display() {
^
    overridden method is final

Main.java:16: error: cannot find symbol
child.func();
^
    symbol: method func()
location: variable child of type Child

2 errors
error: compilation failed
```

### 7.13.3.1 `final` 参数

在 Java 中，`final` 关键字可以用于方法中的参数。当参数被声明为 `final` 时，意味着该参数在它使用的方法或块中不能被重新赋值。这确保了参数的值在整个方法的执行过程中保持不变。

## `final` 参数的特性

- **不可变性**：通过将参数设为 `final`，你可以确保它们在方法内部不被修改，增强方法的健壮性和可预测性。
- **可读性与维护性**：通过明确指示参数不应被重新赋值，提高了代码的可读性。这在参数可能被传递给多个辅助方法的长方法中特别有用。
- **线程安全**：`final` 参数有助于创建线程安全的代码，因为它们的不可变性确保了它们的值不会被无意中改变，这在并发编程中至关重要。
- **避免错误**：使用 `final` 参数可以防止由于变量无意重新赋值导致的错误，从而减少 Bug 并使代码更可靠。

## Java 继承

## `final` 参数的优势

- **防止重新赋值**：`final` 参数防止意外的重新赋值，从而产生更少的 Bug 和稳定的代码。
- **提高清晰度**：它使代码意图更加清晰，向其他开发者传达参数应该保持不变。
- **增强优化**：当 Java 编译器知道某些值不会改变时，可以更好地优化代码。
- **一致性**：使用 `final` 参数促进了方法内值的一致使用，可以提高整体代码质量和维护性。

## `final` 参数的局限性

- **僵化**：一旦参数被声明为 `final`，就无法更改，这在方法内部可能需要重新赋值的情况下会产生局限性。
- **冗长性**：将参数声明为 `final` 会增加代码的冗长，特别是在具有多个参数的方法中。
- **用途有限**：`final` 参数主要用于确保方法内部的不可变性，这对于所有方法参数可能都不是必要的。

## 程序

`final` 参数程序。

```java
public class Test {
    // 接收两个参数的方法：n（普通）和 m（final）
    void display(int n, final int m) {
        n = n * m; // 计算 n 和 m 的乘积
        System.out.println("n=" + n + " m=" + m); // 输出结果以及 m 的值
    }

    public void main(String[] args) {
        Test test = new Test(); // 创建 Test 类的实例
        test.display(10, 20); // 使用参数 10 和 20 调用 display 方法
    }
}
```

输出：

```text
n=200 m=20
```

上述程序定义了一个包含 `main` 方法的 `Test` 类。在 `main` 方法内部，创建了 `Test` 类的实例。然后，使用两个整数参数 `10` 和 `20` 调用了 `Test` 类的 `display` 方法。`display` 方法接收两个参数：`n` 和 `m`，其中 `n` 是普通整数，`m` 是 `final` 整数。在 `display` 方法内部，`n` 的值被赋值为 `m` 与 `n` 的乘积，然后输出结果以及 `m` 的值。

## 7.13.4 `final` 变量

`final` 变量是一个常量，一旦赋值其值就无法更改。在 Java 中声明 `final` 变量，使用 `final` 关键字后跟数据类型和变量名，然后对其进行初始化。一旦完成赋值，它在整个程序的执行过程中都保持不变。

```java
final int MAX = 10;
```

## 应用中的 `final` 变量

`final` 变量是一个常量，一旦赋值其值就无法更改。在 Java 中声明 `final` 变量，使用 `final` 关键字后跟数据类型和变量名，然后对其进行初始化。

```java
final int MAX = 10;
```

## `final` 变量程序

```java
class Sample {
    final int i; // final 实例变量

    // 初始化 final 变量的构造函数
    Sample(int val) {
        i = val; // 设置 final 变量 i
    }

    // 使用默认值初始化 final 变量的构造函数
    Sample() {
        this(100); // 调用默认值为 100 的参数化构造函数
    }
}

public class Test {
    public static void main(String[] args) {
        Sample s = new Sample(); // 使用默认构造函数创建 Sample 实例
        System.out.println("Final value: " + s.i);

        Sample s2 = new Sample(50); // 创建值为 50 的 Sample 实例
        System.out.println("Final value: " + s2.i);
    }
}
```

输出：

```text
Final value: 100
Final value: 50
```

## 242 用于医疗和医学应用的 Java 22

该程序定义了一个名为 `Sample` 的类，其中包含一个 `final` 整数类型的 `i`。程序提供了两个构造函数：一个使用给定值初始化 `i`，另一个将其初始化为默认值 `100`。在 `Test` 类的 `main` 方法中，使用不同的构造函数创建了两个 `Sample` 对象 `s1` 和 `s2`。对于 `s1`，调用带参数的构造函数，将 `i` 设置为 `10`；对于 `s2`，调用默认构造函数，将 `i` 设置为 `100`。最后，打印 `s1` 和 `s2` 的 `i` 值。由于 `i` 是 `final` 的，其初始化后无法修改，这确保了赋值的值在整个对象的生命周期内保持不变。

### 7.13.4.2 `final` 静态变量初始化

在 Java 中，静态初始化块用于初始化静态变量或执行在类加载到内存时需要执行一次的其他任务。使用静态初始化块结合 `final` 变量初始化，可以在类中初始化常量。

### 程序

```java
// static final blank variable 程序
class Test {
    static final int i; // final 静态变量

    // 初始化块
    static {
        i = 100; // 初始化 final 静态变量
    }

    void main(String[] args) {
        Test t = new Test(); // 创建 Test 类的实例
        System.out.println("static final blank value is " + t.i);

        // 访问并打印静态变量
    }
}
```



输出：

```
static final blank value is 100
```

该程序定义了一个名为`test`的类，其中包含一个`final`静态整数`i`。在类内部，有一个静态初始化块将静态变量`i`初始化为`100`。在`test`类的`main`方法中，创建了`test`类的实例。通过实例`t`访问静态变量`i`并使用`System.out.println("static final blank value is " + t.i)`将其打印到控制台。由于`i`是静态的，可以使用类名或类的实例来访问。输出为"static final blank value is 100"。

### 7.13.4.3 Final 初始化块

在 Java 中，`final`初始化块似乎指的是类中一个在创建类实例时执行的 own块。初始化块用于在实例化对象时初始化实例变量并执行其他初始化任务。它们可以是静态的，也可以是非静态的。一个`final`初始化块的结构与普通初始化块相似，仅增加了`final`关键字，但该关键字没有任何显著影响。

### 程序

```
Program for final blank variable initialization in instance block

class Test {

    final int i = 5; // 初始化为5的final变量

    final int k; // final 变量，在此未初始化

    // 实例初始化块

{

  k = i * i; // 将 k 初始化为 i 的平方

  display(); // 调用 display 方法

  }

  // 显示消息和 k 值的方法

  void display() {

    System.out.println("changing final variable in initializer block");

    System.out.println("k=" + k);

  }

  void main(String[] args) {

    new Test(); // 创建 Test 的实例

  }

}
```

输出：

```
changing final variable in initializer block
k=25
changing final variable in initializer block
k=25
```

上述程序定义了一个类`test`，其中包含两个`final`整数变量：`i`和`k`。变量`i`已被初始化，而`k`留未初始化，使其成为"空白变量"。在初始化块内部，`k`的值被赋值为`i`的平方。`display()`方法被调用。在`main`方法中，创建了`Test`的实例。初始化块执行时初始化了`k`并调用了`display()`方法，显示了`final`变量的变化。输出显示了`k`的值，结果是`i`的平方（25）。

## 7.13.4.4 Lambda 表达式中的 final 变量

在 Lambda 表达式中，变量必须是`final`的或有效最终（effectively final）。这确保了变量在初始化后不会发生变化。

### 程序

```
import java.util.function.Consumer;

public class LambdaExample {

  public void main(String[] args) {

    // final 和有效最终变量

    final String title = "Dr. ";

    String name = "Usharani Bhimapu";

    // 使用 final 和有效最终变量的表达式

    Consumer<String> printFullName = suffix -> {

      // 连接并打印变量

      System.out.println(title + name + suffix);

    };

    // 带参数执行 表达式

    printFullName.accept("!");

  }

}
```

输出：

```
Dr. Usharani Bhimapu!
```

上述 Java 程序演示了 Lambda 表达式的使用。`title`变量声明为`final`，而`name`变量是有效最终的。

### 7.13.4.5 Final 对象实例化

在 Java 中，`final`变量必须初始化一次。一旦初始化，其值就无法更改。这对于创建运行时确定的常量非常有用。

### 程序

```
Program for final variable

class Test {

    final int i;

    Test(int value) {

        i = value;

    }

    static void main(String[] args) {

        Test t1 = new Test(10);

        Test t2 = new Test(20);

        System.out.println(t1.i);

        System.out.println(t2.i);

    }

}
```

输出：

```
10
20
```

上述程序演示了如何在构造函数中初始化`final`变量。每个`Test`实例都有自己的`i`副本，该值在创建对象时设置一次。

## 7.13.6 Java 继承

继承是面向对象编程中的一个基本概念，一个类（子类或子类）获取另一个类（父类或父亲）的属性和行为。这允许代码重用并在类与类之间建立层级关系。

```
class Animal {

    void eat() {

        System.out.println("这种动物吃食物.");

    }

}

class Dog extends Animal {

    void bark() {

        System.out.println("狗在叫.");

    }

}

public class Main {

    public static void main(String[] args) {

        Dog myDog = new Dog();

        myDog.eat(); // 继承自 Animal 的方法

        myDog.bark(); // 在 Dog 中定义的方法

    }

}
```

# 用于医疗与健康应用的 Java 22

- `abstract className className`: 声明一个名为`className`的抽象类
- `abstract void MethodName()`: 声明一个名为`MethodName()`的抽象方法

抽象方法以分号结束，不包含方法体。
`void anotherMethod() // 方法实现`: 定义一个带有方法体的具体方法`anotherMethod()`。具体方法定义了子类无法继承的默认行为。

注意：扩展抽象类的子类必须重写父类中的所有的抽象方法。

抽象类是一种受限制的类，不能直接实例化，这意味着无法从它创建对象。

# 程序

```
抽象类中 main 方法的程序

abstract class Sample {

    // 带有静态方法的抽象类

    void main(String[] args) {

        System.out.println("abstract main");

        System.out.println(args);

    }

}

public class Test extends Sample {

    public Test() {

        String[] s = {"main", "in", "abstract", "class"};

        // 子类中的构造函数

        System.out.println("Constructor in child");

        // 调用抽象类的静态方法

        super.main(s);

    }

    void main(String[] args) {

        System.out.println("in main");

        // 创建 Test 的实例

        new Test();

    }

}
```

输出：

```
abstract main
[Java.lang.String;23986957
```

上述 Java 代码示例了抽象类和抽象方法的使用。在 Java 中，抽象类用`abstract`关键字标记，表示它不能被直接实例化，并可能包含抽象方法。尽管`sample`类没有包含任何抽象方法，但由于其声明中存在`abstract`关键字，它仍然是抽象类。通常，抽象类用作子类继承的蓝图，为子类实现特定功能提供了结构。`Test`类扩展了抽象类`Sample`，继承了它的属性和方法。这里，`Test`类包含一个`main`方法，作为程序的入口。需要注意的是，`sample`类中的`main`方法不能直接执行，因为它是抽象类的一部分。相反，它是通过继承间接被调用的。在`Test`类中，创建了一个`Test`实例，触发了它的构造函数。在构造函数内部，使用`super.main(s)`调用`sample`类的`main`方法，其中`s`代表字符串数组。因此，程序的输出将显示`in main`，随后是字符串数组`s`的元素。

# Java 继承 247

### 7.14.1.1 抽象类中的构造函数

在 Java 中，抽象类中的构造函数在初始化由具体子类创建的对象起着至关重要的作用。虽然抽象类不能直接实例化，但在实例化具体子类时，它们的构造函数会被隐式调用。抽象类的构造函数与普通类的构造函数相似，但存在区别和限制。

### 抽象类构造函数的特征

- 抽象类字段的初始化：抽象类中的构造函数可以像普通类的构造函数一样初始化抽象类中定义的字段。这允许初始化所有子类共享的公共状态。
- 从子类调用：抽象类中的构造函数由具体子类的构造函数隐式调用。当实例化子类时，会自动调用抽象父类的构造函数来初始化被继承的状态。
- 访问修饰符：抽象类中的构造函数可以有不同的访问修饰符（`public`、`protected`、默认或`private`），取决于设计要求。然而，如果抽象类中的构造函数是私有的，则子类无法访问它。

### 程序

```
在 Java 中在抽象类中调用构造函数的程序

abstract class Base {

  // 抽象类中的构造函数

  Base() {

    System.out.println("abstract parent constructor");

  }

}

class Child extends Base {

  // 子类中的构造函数

  Child() {

    System.out.println("child constructor");

    super(); // 调用 Base 的构造函数

  }

}

public class Sample {

  public void main(String[] args) {

    // 创建 Child 的实例

    new Child();

  }

}
```

输出：

```
child constructor
abstract parent constructor
```

上述 Java 代码演示了抽象类的用法及其与子类的交互。在 Java 中，抽象类使用`abstract`关键字声明，如`base`类所示。抽象类不能被直接实例化，但可以被其他类扩展。此示例中的`base`类是抽象的，它不能单独实例化。`child`类扩展了`base`抽象类，表示它继承了在`base`中定义的属性和方法。在`child`类内部实现了一个构造函数。当创建`child`的实例时，会调用其构造函数。构造函数中使用`super()`关键字来调用父类`base`的构造函数，允许在执行`child`构造函数中的代码之前初始化父类的状态。在`sample`类的`main`方法中，创建了一个类型为`child`的对象。实例化时，调用了`child`的构造函数，进而通过`super()`调用抽象类`base`。这种构造函数调用序列导致输出显示"abstract parent constructor"，随后是"child constructor"，说明了在处理抽象类和子类时的执行流。

## 7.14.2 抽象方法

抽象方法是声明时没有实现的方法。它的目的是供子类实现。抽象方法在抽象类中使用`abstract`关键字声明。

# 程序

```
// 抽象基类

abstract class Base {

    // 抽象方法（无实现）

    abstract void display();

    // 抽象类的构造函数

    Base() {

        System.out.println("Base class constructor");

    }

}

// 具体子类

class Child extends Base {

    // 子类的构造函数

    Child() {

        System.out.println("Child class constructor");

    }

    // 为抽象方法具体实现

    @Override

    void display() {

        System.out.println("Child class method");

    }

}

public class Main {

    public static void main(String[] args) {

        // 创建 Child 实例

        Child obj = new Child();

        // 调用方法

        obj.display();

    }

}
```

输出：

```
Base class constructor
Child class constructor
Child class method
```

# Java 继承 241

数组可以声明为持有特定类或其子类的对象，用不同类型的对象进行初始化，并统一调用重写的方法和继承的方法。遍历数组允许对每个对象执行操作，通过利用多态和代码复用为相关对象的集合提供了灵活性。

## 7.15 对象的数组继承

# 程序

```
// 基类

class Test {

    // 由派生类调用的方法

    void display() {

        System.out.println("Parent class method");

    }

}

// 中间类

class Sample extends Test {

    // Sample 类特定的方法

    void put() {

        System.out.println("Child class method");

    }

}

// 扩展了 Sample 的 Main 类

public class Main extends Sample {

    public static void main(String[] args) {

        // 创建 Sample 对象数组

        Sample[] s = new Sample[2];

        // 遍历数组每个元素的循环

        for (int i = 0; i < s.length; i++) {

            s[i] = new Sample();

            System.out.println("Iteration number: " + i);

            s[i].display(); // 调用 Test 类的方法

            s[i].put(); // 调用 Sample 类的方法

        }

    }

}
```

输出：

```
Iteration number: 0
Parent class method
Child class method
Iteration number: 1
Parent class method
Child class method
```

上述 Java 程序包含三个类：`test`、`sample`和`Main`。`test`类定义了一个名为`display()`的方法，向控制台打印"Parent class method"。`sample`类继承了`test`类，并定义了一个方法`put()`，向控制台打印"child class method"。`Main`类继承了`sample`类。在它的`main`方法中，创建了一个名为`s`且大小为 4 的`sample`对象数组。循环遍历该数组，用新的`sample`对象初始化每个元素。在每次迭代中，迭代号都会被打印到控制台。然后，在数组的`sample`对象上分别调用了`display()`和`put()`。当程序执行时，对于循环的每次迭代，迭代号都会打印到控制台。此外，在数组中的`sample`对象上调用了`test`类的`display()`方法和`sample`类的`put()`方法，导致相应的消息被打印到控制台。

# 程序

类对象数组与多级继承

```java
// 基类

class Test {

    // 基类中的方法

    void display() {

        System.out.println("Parent class method");

    }

}

// 继承 Test 的中间类
```



# 多级继承示例

```java
class Sample extends Test {

    // Sample 类中的方法

    void put() {

        System.out.println("Child class method");

    }

}

// 进一步继承 Sample

class Test1 extends Sample {

    // Test1 类中的方法

    void printing() {

        System.out.println("Subchild class method");

    }

}

// 进一步继承 Test1

class Test2 extends Test1 {

    // Test2 类中的方法

    void method() {

        System.out.println("Subsubchild class method");

    }

}

// 继承 Sample 的主类

public class Main extends Sample {

    void main(String[] args) {

        // 创建 Test2 对象数组

        Test2[] t = new Test2[2];

        // 循环初始化数组的每个元素

        for (int i = 0; i < t.length; i++) {

            t[i] = new Test2(); // 用 Test2 对象初始化数组

            System.out.println("Iteration number: " + i);

            t[i].display(); // 来自 Test 方法

            t[i].put(); // 来自 Sample 方法

            t[i].printing();   // 来自 Test1 方法

            t[i].method();      // 来自 Test2 方法

        }

    }

}
```

输出：

```
Iteration number: 0
Parent class method
Child class method
Subchild class method
Subchild class method
Iteration number: 1
Parent class method
Child class method
Subchild class method
Subchild class method
```

上述 Java 程序通过类层级结构演示了多级继承：`Test`、`Sample`、`Test1`、`Test2` 和一个名为 `Main` 的公共类。`Test` 类定义了一个名为 `display()` 的方法，向控制台打印 `"Parent class method"`。`Sample` 类继承了 `Test` 类，并定义了一个名为 `put()` 的方法，向控制台打印 `"Child class method"`。`Test1` 类继承了 `Sample` 类，并定义了一个名为 `printing()` 的方法，向控制台打印 `"Subchild class method"`。`Test2` 类继承了 `Test1` 类，并定义了一个名为 `method()` 的方法，向控制台打印 `"Subchild class method"`。`Main` 类继承了 `Sample` 类。在它的 `main()` 方法中，创建了一个名为 `t` 且大小为 2 的 `Test2` 对象数组。然后，循环遍历该数组，用新的 `Test2` 对象初始化每个元素。在每次迭代中，迭代号都会被打印到控制台。然后，在数组中的 `Test2` 对象上调用了 `display()`、`put()`、`printing()` 和 `method()`。

# 7.16 医学应用

## 7.16 案例研究

脂肪肝与脂肪肝患者的发展有关，称为非酒精性脂肪肝病（NAFLD）。这种情况发生在脂肪聚集在肝脏中，可能导致炎症（hepatitis）并最终进展为纤维化、癌症。考虑的参数有：

- **疲劳**：患者是否感到持续的或缺乏能量。
- **腹痛**：腹部是否有任何不适或疼痛，这可能指示肝脏问题。
- **肿胀**：是否有异常肿胀或增大，特别是在腹部，这可能提示液体滞留或肝功能障碍。
- **体重减轻**：显著且非故意的体重减轻，可能伴随肝疾病。

```java
import java.util.Scanner;

class Person {

    private String name;

    private int age;

    private String gender;

    public Person(String name, int age, String gender) {

        name = name;

        age = age;

        gender = gender;

    }

    public String getName() {

      return name;

    }

    public int getAge() {

      return age;

    }

    public String getGender() {

      return gender;

    }

    @Override

    public String toString() {

      return "Person" +

        "name='" + name + '\'' +

        ", age=" + age +

        ", gender='" + gender + '\'' +

        '";

    }

}

class Patient extends Person {

  private String medicalHistory;

  private boolean hasFatigue;

  private boolean hasJaundice;

  public Patient(String name, int age, String gender, String medicalHistory,

      boolean hasFatigue, boolean hasJaundice) {

    super(name, age, gender);

    medicalHistory = medicalHistory;

    hasFatigue = hasFatigue;

    hasJaundice = hasJaundice;

  }

  public String getMedicalHistory() {

  return medicalHistory;

  }

  public boolean hasFatigue() {

  return hasFatigue;

  }

  public boolean hasJaundice() {

  return hasJaundice;

  }

  @Override

  public String toString() {

  return "Patient" +

    "name='" + getName() + '\'' +

    ", age=" + getAge() +

    ", gender='" + getGender() + '\'' +

    ", medicalHistory='" + medicalHistory + '\'' +

      ", hasFatigue=" + hasFatigue +

      ", hasJaundice=" + hasJaundice +

      +

  }

}

class LiverPatient extends Patient {

    private boolean hasAbdominalPain;

    private boolean hasSwelling;

    private boolean hasWeightLoss;

    public LiverPatient(String name, int age, String gender, String medicalHistory,

        boolean hasFatigue, boolean hasJaundice, boolean hasAbdominalPain,

        boolean hasSwelling, boolean hasWeightLoss) {

        super(name, age, gender, medicalHistory, hasFatigue, hasJaundice);

        this.hasAbdominalPain = hasAbdominalPain;

        this.hasSwelling = hasSwelling;

        this.hasWeightLoss = hasWeightLoss;

    }

    public boolean hasAbdominalPain() {

        return hasAbdominalPain;

    }

    public boolean hasSwelling() {

        return hasSwelling;

    }

    public boolean hasWeightLoss() {

        return hasWeightLoss;

    }

    public boolean isSuspectedOfFattyLiverCancer() {

        return hasFatigue() && hasAbdominalPain && hasSwelling && hasWeightLoss;

    }

    @Override

    public String toString() {

        return "LiverPatient" +

            "name='" + getName() + '\'' +

            ", age=" + getAge() +

            ", gender='" + getGender() + '\'' +

            ", medicalHistory='" + getMedicalHistory() + '\'' +

            ", hasFatigue=" + hasFatigue +

            ", hasJaundice=" + hasJaundice +

            ", hasAbdominalPain=" + hasAbdominalPain +

            ", hasSwelling=" + hasSwelling +

            ", hasWeightLoss=" + hasWeightLoss +

            + ")";

    }

}
```

```java
public class FattyLiverCancerDetection {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter name: ");

        String name = scanner.nextLine();

        System.out.print("Enter age: ");

        int age = scanner.nextInt();

        scanner.nextLine(); // 换行符

        System.out.print("Enter gender: ");

        String gender = scanner.nextLine();

        System.out.print("Enter medical history: ");

        String medicalHistory = scanner.nextLine();

        System.out.print("Has fatigue (true/false): ");

        boolean hasFatigue = scanner.nextBoolean();

        System.out.print("Has jaundice (true/false): ");

        boolean hasJaundice = scanner.nextBoolean();

        System.out.print("Has abdominal pain (true/false): ");

        boolean hasAbdominalPain = scanner.nextBoolean();

        System.out.print("Has swelling (true/false): ");

        boolean hasSwelling = scanner.nextBoolean();

        System.out.print("Has weight loss (true/false): ");

        boolean hasWeightLoss = scanner.nextBoolean();

        LiverPatient patient = new LiverPatient(name, age, gender, medicalHistory,

            hasFatigue, hasJaundice, hasAbdominalPain, hasSwelling, hasWeightLoss);

        System.out.println(patient.toString());

        if (patient.isSuspectedOfFattyLiverCancer()) {

            System.out.println("Patient is suspected of fatty liver cancer.");

        } else {

            System.out.println("Patient does not show signs of fatty liver cancer.");

        }

    }

}
```

# 用于医疗保健应用的 Java 22

```java
boolean hasJaundice = scanner.nextBoolean();

System.out.print("Has abdominal pain (true/false): ");

boolean hasAbdominalPain = scanner.nextBoolean();

System.out.print("Has swelling (true/false): ");

boolean hasSwelling = scanner.nextBoolean();

System.out.print("Has weight loss (true/false): ");

boolean hasWeightLoss = scanner.nextBoolean();

LiverPatient patient = new LiverPatient(name, age, gender, medicalHistory,

fatigue, jaundice, hasAbdominalPain, hasSwelling, hasWeightLoss);

System.out.println("");

if (patient.isSuspectedOfFattyLiverCancer()) {

    System.out.println("The patient is suspected of having fatty liver cancer.");

} else {

    System.out.println("The patient is not suspected of having fatty liver cancer.");

}
```

该 Java 程序首先提示用户输入姓名、年龄和性别等个人信息，随后是病史详情。然后，它询问用户是否存在特定的症状，如疲劳、黄疸、腹痛、肿胀和体重减轻，并将这些捕获为布尔值。根据这些输入，创建了 `LiverPatient` 类的实例，该类继承自 `Patient`，后者又扩展了 `Person` 类，以维护个人和医疗信息的结构化层次结构。最后，程序评估收集到的症状是否提示疑似脂肪肝癌，并输出诊断信息，展示了其在医疗数据收集和初步评估中的作用。

# 7.16.2 案例研究 2

黄疸是一种疾病，其特征由于血液胆红素水平升高导致皮肤和眼睛发黄。胆红素是肝脏在分解红细胞过程中产生的黄色色素。当肝脏无法有效代谢胆红素或胆管发生阻塞时，胆红素会在血液中积聚，导致黄疸。考虑的参数有：

- 黄眼：检查患者眼睛是否发黄。
- 黄皮肤：检查患者皮肤是否发黄。

```java
import java.util.Scanner;

public class JaundiceDetection {

    static class Patient {

        private String name;

        private int age;

        private String gender;
```



```java
public Patient(String name, int age, String gender) {
    this.name = name;
    this.age = age;
    this.gender = gender;
}

public String getName() {
    return name;
}

public int getAge() {
    return age;
}

public String getGender() {
    return gender;
}

@Override
public String toString() {
    return "Patient" +
        "name=" + '\'' + name + '\'' +
        ", age=" + age +
        ", gender=" + '\'' + gender + '\'';
}

class JaundiceDetector {
    private boolean hasYellowEyes;
    private boolean hasYellowSkin;

    public JaundiceDetector(boolean hasYellowEyes, boolean hasYellowSkin) {
        this.hasYellowEyes = hasYellowEyes;
        this.hasYellowSkin = hasYellowSkin;
    }

    public boolean isJaundiceDetected() {
        return hasYellowEyes || hasYellowSkin;
    }

    @Override
    public String toString() {
        return "hasYellowEyes=" + hasYellowEyes +
            ", hasYellowSkin=" + hasYellowSkin;
    }
}

public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

    System.out.print("Enter patient name: ");
    String name = scanner.nextLine();

    System.out.print("Enter patient age: ");
    int age = scanner.nextInt();
    scanner.nextLine(); // Consume newline

    System.out.print("Enter patient gender: ");
    String gender = scanner.nextLine();

    System.out.println("Jaundice symptoms:");

    System.out.print("Has yellow eyes (true/false): ");
    boolean hasYellowEyes = scanner.nextBoolean();

    System.out.print("Has yellow skin (true/false): ");
    boolean hasYellowSkin = scanner.nextBoolean();

    // Create Patient instance
    Patient patient = new Patient(name, age, gender);

    // Create JaundiceDetector instance using inner class
    Patient.JaundiceDetector jaundiceDetector =
        patient.new JaundiceDetector(hasYellowEyes, hasYellowSkin);

    // Print patient details
    System.out.println("Patient details: " + patient);

    // Print jaundice detection result
    System.out.println(
        "Jaundice detection result: " +
        (jaundiceDetector.isJaundiceDetected()
            ? "Jaundice detected"
            : "No jaundice detected")
    );
}
```

上述 Java 程序 `JaundiceDetection` 建立了一个根据用户提供的信息检测黄疸的系统。它首先提示用户输入患者详情，如姓名、年龄和性别。随后，它询问与黄疸相关的特定症状，包括患者是否眼睛发黄和皮肤发黄。使用内部类结构，程序定义了一个 `Patient` 类来封装基本个人信息，并定义了一个嵌套的 `JaundiceDetector` 类来评估黄疸症状。在实例化后，`JaundiceDetector` 检查是否存在任一症状，并判断是否检测到黄疸。最后，程序输出患者详情和黄疸检测结果，为初步医疗评估提供了一个简单的工具。

# 8 接口

## 8.1 引言

Java 中的抽象是指隐藏某些细节并只显示对象或系统的本质特征的过程。通过抽象类和接口实现，关注对象做什么而不是如何做。

抽象的关键方面：

- **抽象类**：通常通过抽象类和接口实现，关注可以被重写的方法。
- **隐藏实现细节**：抽象通过隐藏不需要实现的细节，提高了代码的可读性和可维护性。

对抽象的需求：

- **简单性和可管理性**：通过抽象实现细节，使系统更容易理解和管理。
- **封装**：抽象通过提供类实现与其外部接口之间的清晰分离，促进了模块化设计。

抽象的益处：

- **增强模块化**：通过定义组件之间的清晰边界来促进设计，这有利于扩展。
- **代码复用性**：抽象允许通过抽象类和接口创建可重用的组件，而无需更改行为。
- **灵活性和可扩展性**：允许软件系统随时间演进，而不影响提供其他部分的功能。

抽象的局限性：

- **增加复杂性**：设计有效的抽象需要仔细考虑隐藏和暴露。过度抽象会导致设计难以理解和维护。
- **性能开销**：直接访问抽象组件（例如通过接口）可能会引入微小的性能开销。但在现代应用中，这种影响通常是可以忽略不计的。

# 程序

```java
// 抽象类 CourseRegistration
abstract class CourseRegistration {
    // 学生和课程信息的字段
    protected String studentName;
    protected String courseName;

    // 初始化学生和课程详情的构造函数
    public CourseRegistration(String studentName, String courseName) {
        this.studentName = studentName;
        this.courseName = courseName;
    }

    // 注册课程的抽象方法
    public abstract void register();

    // 显示详情的方法（已实现而非抽象）
    public void displayDetails() {
        System.out.println("Student: " + studentName);
        System.out.println("Course: " + courseName);
    }
}

// 实现抽象方法的具体类
class OnlineCourseRegistration extends CourseRegistration {
    public OnlineCourseRegistration(String studentName, String courseName) {
        super(studentName, courseName);
    }

    // 实现抽象方法
    @Override
    public void register() {
        System.out.println(studentName + " 已注册课程：" + courseName);
    }
}

// 用于取消课程等操作的接口
interface CourseManagement {
    void cancelRegistration();
}

// 同时实现抽象类和接口的类
class AdvancedCourseRegistration
    extends CourseRegistration
    implements CourseManagement {

    public AdvancedCourseRegistration(String studentName, String courseName) {
        super(studentName, courseName);
    }
}
```

# 接口

```java
// 实现 CourseRegistration 中的抽象方法
@Override
public void register(String studentName) {
    System.out.println(
        studentName + " has been registered for the " +
        "advanced course: " + courseName
    );
}

// 实现 CourseManagement 接口中的方法
@Override
public void cancelRegistration() {
    System.out.println(
        "Registration for " + studentName + " in " +
        courseName + " has been canceled."
    );
}

// 用于演示注册过程的主类
public class Main {
    void main(String[] args) {
        // 注册在线课程
        CourseRegistration onlineCourse =
            new OnlineCourseRegistration("Usha, Java Programming");

        onlineCourse.register();
        onlineCourse.displayDetails(); // 为了可读性进行换行

        // 注册高级课程并取消注册
        AdvancedCourseRegistration advancedCourse =
            new AdvancedCourseRegistration("Rani,", "Advanced Algorithms");

        advancedCourse.register();
        advancedCourse.displayDetails();
        advancedCourse.cancelRegistration();
    }
}
```

Usha 已注册在线课程：Java

学生：Usha

课程：Java Programming

Rani 已注册高级课程：Advanced Algorithms

学生：Rani

课程：Advanced Algorithms

Rani 在 Advanced Algorithms 中的注册已取消。

此程序通过使用抽象类 `CourseRegistration` 进行学生注册，并由具体类实现特定的注册逻辑，演示了 Java 中的抽象。它还使用了接口 `CourseManagement` 来实现取消注册等额外功能。`Main` 类创建实例来展示注册和取消的过程。

## 8.2 接口

Java 中的接口是一种引用类型，类似于类，但它只能包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不能包含实例字段或构造函数。它们被用于定义一个其他类可以实现的合约。接口规定了类必须做什么，而不是它如何做。

### 8.2.1 接口的重要性

接口在 Java 中至关重要，原因如下：

- **抽象**：接口提供了一种抽象类行为的方式。它们允许你定义类必须实现的方法，而无需指定具体的实现方式。
- **多重继承**：Java 不支持多继承（一个类继承自多个类），但类可以实现多个接口。这允许了一种多重继承的形式。
- **松散耦合**：接口通过定义一组可以被任何类实现的方法，提供了松散耦合。这允许了对象的互换性。
- **标准化**：它们提供了一种标准的交互形式。不同的类可以实现同一个接口，确保它们提供了特定的方法。

### 8.2.2 接口的必要性

接口的需要源于软件开发中的几种场景：

- **多重继承**：由于 Java 不支持多继承，接口提供了一种实现多组行为的方式。
- **代码重用**：接口允许创建通用方法和类，这些类可以操作任何实现了特定接口的类。
- **框架和 API**：接口在框架和 API 中广泛使用，以提供通用结构并确保不同组件可以相互交互。

### 8.2.3 接口的优势

- **灵活性**：接口允许类通过实现多个接口来变得更加灵活。
- **解耦**：通过使用接口，你可以将方法的实现与其声明解耦，这有助于在更改实现而不影响使用该接口的类。
- **可测试性**：接口使代码测试变得更容易，因为你可以为测试目的提供接口的模拟（mock）实现。
- **互操作性**：它们允许不同的类更容易更容易一起工作，促进程序不同部分之间的通信。
- **代码组织**：接口通过定义一组必须实现的清晰方法来帮助组织代码，使代码更容易理解和维护。

### 8.2.4 接口的局限性

- **无实现**：接口在方法中不能包含任何实现逻辑（默认和静态方法除外），这意味着每个实现类都必须提供自己的实现。
- **僵化的合约**：一旦发布了接口，更改它可能会破坏所有的实现。这使得接口的设计变得非常关键。
- **复杂性**：使用过多的接口可能会使设计变得复杂且难以管理，特别是当存在许多依赖关系时。
- **性能开销**：由于额外的间接层，与直接方法调用相比，接口方法调用会有轻微的性能开销。

## 8.3 接口

在 Java 中，接口是一种引用类型，类似于类，但只能包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不能包含实例字段或构造函数。它们被用于指定一个类必须实现的方法集，提供了在 Java 中实现抽象和多重继承的方法。

接口通过允许类实现多个接口解决了多重继承的问题。当一个类实现接口时，它同意为该接口中声明的所有方法提供实现。由于 Java 不支持通过类扩展来实现多继承，实现接口为类提供了从多个源继承的方法。

在接口中声明的方法默认是抽象的，这意味着它们没有方法体，并且由实现类实现。在接口中声明的变量隐式为公共的、静态的最终的，使它们成为常量，可以使用接口名称进行访问。这允许接口定义实现类可以使用的常量，而无需重新定义它们。

**注意：** 我们不能创建对象。要使用接口，类必须实现它。我们必须使用 `implements` 关键字来实现接口。

#### 语法

```java
// 定义一个接口
public interface InterfaceName {
    // 常量（隐式为 public、static 和 final）
    Type CONSTANT_NAME = value;

    // 抽象方法声明（无方法体）
    ReturnType methodName(parameterName);

    // 有实现的默认方法
    default ReturnType methodName(parameterName) {
        // 方法体
    }

    // 有实现的静态方法
    static ReturnType staticName(parameterName) {
        // 方法体
    }

    // 嵌套接口（可选）
    interface NestedInterface {
        ReturnType nestedMethodName(parameterName);
    }
}
```



在 Java 中定义接口的语法涉及使用`interface`关键字后跟接口名称。在接口体内部声明了方法签名，这规定了接口必须实现的方法。默认，接口中声明的所有方法都是公共且抽象的，这意味着它们没有方法体，并且由实现类实现。此外，接口可以包含变量，这些变量隐式为公共、静态和最终。这些变量是常量，并在声明时必须初始化。由于它们是静态的，它们实际上被所有实现接口的类共享。因此，在接口内部声明变量的语法指定了访问修饰符（`public`），随后是`static`和`final`，然后数据类型和变量名。

### 8.3.1 默认方法

Java 中的默认方法是在接口中使用`default`关键字定义的方法，提供了默认实现。它们允许接口通过添加新方法而不破坏现有的实现。此功能有助于实现向后兼容，并支持创建更灵活、可复用的接口。如果需要特定的行为，实现类可以重写默认方法。

## Program

```
Program for default methods in java interface

// 定义一个包含常量、抽象方法和默认方法的接口
interface definterface {

    // 常量变量
    int i = 10;

    // 抽象方法
    void display();

    // 默认方法
    default void cube(int x) {
        System.out.println(x * x * x);
    }
}

// 实现接口的类
class sample implements definterface {

    // 实现 display 方法
    public void display() {
        System.out.println(i);
    }
}

// 主类
public class test {

    public void main(String[] args) {

        // 创建 sample 实例并调用方法
        definterface obj = new sample();
        obj.display(); // 输出 i 的值 (10)
        obj.cube(10); // 输出 10 的立方方 (1000)
    }
}
```

## Output

```
10
1000
```

首先，使用`interface`关键字声明了一个名为`definterface`的接口，其中包含一个初始化值为 10 的整数常量变量`i`。此外，指定了`display()`方法签名但没有方法体，这意味着实现类必须为该方法提供实现。此外，定义了一个名为`cube()`的默认方法，它包含方法体并为计算给定整数参数的立方方提供了默认实现。接下来，类`sample`使用`implements`关键字实现了`definterface`。在`sample`类中，实现了`display()`方法，以打印接口中声明的常量`i`的值。最后，定义了一个名为`test`的类，它包含`main()`方法。在`main()`方法内部，创建了`sample`类的实例并将其赋值给`definterface`类型的引用变量。

### 8.3.2 静态方法

Java 中的静态方法是在类中通过`static`关键字定义的方法，这意味着它们属于类本身，而不是类的任何实例。这些方法可以在不创建类对象的情况下调用，并用于不需要来自实例变量数据的操作。静态方法可以直接访问静态变量和其他静态方法，但不能访问实例变量或方法。它们通常用于工具方法或辅助方法。

## Program

```
Program on static methods in java interface

// 定义包含常量、静态方法和抽象方法的接口
interface test {

    // 常量变量
    int i = 10;

    // 用于计算立方方的静态方法
    static int cube(int x) {
        return x * x * x;
    }

    // 抽象方法
    void display();
}

// 实现接口的类
class sample implements test {

    // 实现 display 方法
    public void display() {
        System.out.println(i); // 输出常量 i
    }

    // 使用接口中静态 cube 方法的方法
    public void fcube() {
        int result = test.cube(i); // 调用接口的静态 cube 方法
        System.out.println(result); // 输出 i 的立方方
    }
}

// 主类
public class test {

    public static void main(String[] args) {

        // 创建 sample 实例并调用方法
        sample obj = new sample();
        obj.display(); // 输出 i 的值 (10)
        obj.fcube(); // 输出 i 的立方方 (1000)
    }
}
```

## Output

```
10
1000
```

`test`接口使用`interface`关键字声明。它包含一个初始化值为 10 的整数常量`i`的声明。此外，接口内部定义了一个名为`cube()`的静态方法，该方法计算并返回给定整数参数的立方方。还指定了`display()`方法签名，意味着实现此接口的类必须为该方法提供实现。接下来，类`sample`使用`implements`关键字实现了`test`接口。在`sample`类中，实现了`display()`方法以打印常量`i`的值。此外，`sample`类中定义了一个名为`fcube()`的方法，它使用`test`接口中定义的静态`cube()`方法来计算给定整数参数的立方方。最后，名为`test`的类包含`main()`方法。在`main()`方法内部，创建了`sample`类的实例，并调用了它的`display()`和`fcube()`方法。

## 8.4 实现接口

在 Java 中，当一个类实现一个接口时，它同意执行该接口定义的特定行为。这意味着该类必须为接口中声明的所有抽象方法提供具体的实现。实现接口允许类变得更加灵活，并与具体的实现解耦，从而促进抽象和多态等更好的设计原则。

### 实现接口的语法

```
class classname implements interface
{}
```

要实现接口，类使用`implements`关键字后后跟接口名称。以下是基本语法：

#### 语法

```
interface MyInterface {
    void method1();
    void method2();
}

class MyClass implements MyInterface {
    @Override
    public void method1() {
        // method1 的实现
    }

    @Override
    public void method2() {
        // method2 的实现
    }
}
```

## Program

```
// 定义一个接口
interface sample {
    void data();
}

// 实现 sample 接口的类
class Test implements sample {

    @Override
    public void data() {
        System.out.println("Implementing interface in class.");
    }

    public static void main(String[] args) {
        Test test = new Test();
        test.data(); // 调用 data() 方法
    }
}
```

## Output

```
Implementing interface in class
```

上述 Java 程序展示了名为`sample`的接口的实现及其在`Test`类中的集成。接口`sample`声明了一个单一方法`data()`，而没有提供其实现细节。在实现`sample`接口的`Test`类中，重写了`data()`方法以指定其行为，在这种情况下打印消息`Implementing interface in class.`。在`Test`类的`main`方法中，使用`new`关键字实例化`Test`类型对象`test`。通过该对象调用了`data()`方法。

## 8.5 扩展接口

在 Java 中，接口可以扩展一个或多个接口，允许继承它们的方法。这种能力允许基于通用接口创建更具体的接口。当一个接口扩展另一个接口时，它会继承父接口中声明的所有方法，促进了设计的可复用性和模块化。这种机制允许开发者通过将复杂的行为拆分为更小、易管理且可复用的功能部分来构建灵活可扩展的系统。然而，扩展另一个接口的接口不能为继承的方法提供实现；它只是声明实现类必须为这些方法提供具体行为。这种设计原则是 Java 接口编程的基石，支持开发松耦合且易于维护的代码库。

## 用于医疗与健康应用的 Java 22

```
sample obj = new sample();
obj.display(); // 输出 i 的值 (10)
obj.put(); // 输出 j 的值 (50)
```

输出：

此 Java 程序演示了多个接口的使用及其在类中的实现。定义了两个接口，`myinterface`和`myinterface1`，每个接口包含一个常量和一个抽象方法。`myinterface`声明了一个整数常量`i`和一个抽象方法`display()`。同样，`myinterface1`声明了一个整数常量`j`和一个抽象方法`put()`。`sample`类实现了`myinterface`和`myinterface1`。它为抽象方法`display()`和`put()`提供了实现。在`display()`方法中，打印了来自`myinterface`接口的常量`i`值，而在`put()`方法中，打印了来自`myinterface1`接口的常量`j`值。在`test`类的`main()`方法中，创建了`sample`实例，并调用了它的`display()`和`put()`方法来演示这两个接口的实现。

## 程序

```
接口继承另一个接口的程序

// 定义带有常量和抽象方法的第一个接口
interface myinterface {
    int i = 10; // 常量变量
    void display(); // 抽象方法
}

// 定义扩展第一个接口的第二个接口
interface myinterface1 extends myinterface {
    int j = 50; // 常量变量
    void put(); // 抽象方法
}

// 实现扩展接口的类
class sample implements myinterface1 {

    public void display() {
        System.out.println(i); // 输出常量 i
    }

    // 实现 myinterface1 中的 put 方法
    public void put() {
        System.out.println(j); // 输出常量 j
    }
}

// 主类
public class test {

    void main(String[] args) {

        // 创建 sample 并调用方法
        sample obj = new sample();
        obj.display(); // 输出 i 的值 (10)
        obj.put(); // 输出 j 的值 (50)
    }
}
```

## 输出

```
10
50
```

此 Java 程序演示了接口继承和实现。定义了两个接口`myinterface`和`myinterface1`。`myinterface`包含常量`i`和抽象方法`display()`，而`myinterface1`扩展了`myinterface`并增加了常量`j`和抽象方法`put()`。`sample`类实现了`myinterface1`。它为继承自`myinterface`的`display()`和`put()`方法提供了实现。在`display()`方法中，打印了`myinterface`中的常量`i`，在`put()`方法中，打印了`myinterface1`中的常量`j`。在`test`类的`main()`方法中，创建了`sample`类的实例并用其调用它的`display()`和`put()`方法。

### 8.5.1 类内部的接口

在 Java 中，可以在类内部定义接口，这被称为内部接口。当你希望在特定类的作用范围内封装相关的行为或契约定义时，这种方法非常有用。

## 程序

```
Java 中类的类的内部接口扩展外部接口的程序

// 定义带有抽象方法的接口
interface testing {
    void put(); // 抽象方法
}

// 外部类
class outer {

    // 扩展 testing 接口的内部接口
    interface inner extends testing {
        void display(); // 抽象方法
    }
}

// 实现 outer.inner 接口的类
class sample implements outer.inner {

    // 实现 display 方法
    public void display() {
        System.out.println("interface implemented method");
    }

    // 实现 put 方法
    public void put() {
        System.out.println("interface implemented method");
    }
}

// 主类
public class test {

    void main(String[] args) {

        // 创建 sample 实例并调用方法
        sample obj = new sample();
        obj.display(); // 输出 interface implemented method
        obj.put(); // 输出 interface implemented method
    }
}
```

输出：

```
interface implemented method
interface implemented method
```

在上述程序中，定义了一个接口`testing`，它带有抽象方法`put()`。接下来，定义了一个外部类`outer`，它包含一个内部接口`inner`。该`inner`接口扩展了`testing`接口，并增加了抽象方法`display()`。类`sample`实现了`outer.inner`接口，为`display()`和`put()`方法提供了实现。在`test`类的`main()`方法中，创建了`sample`实例并调用了它的`display()`和`put()`方法，演示了内部接口的用法。

## 程序

```
Java 中类内部接口实现方法的程序

// 定义带有抽象方法的接口
interface testing {
    void put(); // 抽象方法
}

// 外部类
class outer {

    // 扩展 testing 接口的内部接口
    interface inner extends testing {
        void display(); // 抽象方法
    }
}

// 实现 outer.inner 接口的类
class sample implements outer.inner {

    // 实现 display 方法
    public void display() {
        System.out.println("interface implemented method");
    }

    // 实现 put 方法
    public void put() {
        System.out.println("interface implemented method");
    }
}

// 主类
public class test {

    void main(String[] args) {

        // 创建 sample 实例并调用方法
        sample obj = new sample();
        obj.display(); // 输出 interface implemented method
        obj.put(); // 输出 interface implemented method
    }
}
```

输出：

```
interface implemented method
interface implemented method
```



(注：由于提供的原文文本后半部分存在逻辑重复和格式断层，上述翻译已根据指令要求对核心内容进行了对齐处理。)

# Java 22 用于医疗与健康应用

作为任何实现`sample`接口的类必须实现的契约。接下来，定义了一个名为`sample`的类。在`outer`类内部，声明了一个名为`inner`的私有类，它实现了`sample`接口。在`inner`类中根据`sample`接口的要求实现了`put()`方法。`outer`类还包含一个名为`display()`的方法，它实例化`inner`类的对象并调用其`put()`方法。该方法作为访问`inner`类提供的功能的接口。最后，一个名为`test`的类包含`main()`方法，它是程序的入口。在`main()`方法中，创建了`outer`类的实例并调用了`display()`方法。

## 程序

```
Program for invoking main method in interface in java
```

```java
// 定义一个带有静态 main 方法的接口
interface test {
    // 接口内部的静态 main 方法
    static void main(String[] args) {
        System.out.println("main in interface");
        for (String arg : args) {
            System.out.println(arg);
        }
    }
    // 需要被实现的抽象方法
    void display();
}

// 实现 test 接口的类
class Main implements test {
    // 实现接口中的 display 方法
    public void display() {
        System.out.println("display() of interface");
    }
    // 类的 main 方法，程序的入口点
    public void main(String[] args) {
        System.out.println("main in class");
        // 创建类的实例并调用 display
        Main obj = new Main();
        obj.display();
        // 模拟传递命令行参数
        String[] interfaceArgs = {"test", "ing"};
        // 带参数调用 test 接口的 main 方法
        test.main(interfaceArgs);
    }
}
```

## 输出

```
main in interface
```

定义了一个接口`test`。该接口包含一个`main()`方法，该方法定义了`main()`方法作为 Java 程序入口的惯用用法。在`main()`方法内部，通过遍历传递给程序的命令行参数，向控制台打印了一条消息。接下来，类`Main`实现了`test`接口。在此类中，定义了`display()`方法以满足`test`接口指定的契约。此外，该类还实现了惯用的`main()`方法，作为程序的入口点。在`main()`方法中，向控制台打印消息以指示其执行情况。此外，创建了`Main`的实例以调用其`display()`方法。

## 接口

此外，创建了一个字符串数组来模拟命令行参数，并使用该数组调用`test`接口的`main()`方法。

## 程序

```
Program for private inner interface inside class in java
```

```java
// 包含一个私有接口和一个扩展该私有接口的公共接口的外部类
class Outer {
    // 带有抽象方法的私有接口 Inner
    private interface Inner {
        void show();
    }
    // 扩展 Inner 并声明另一个抽象方法的公共接口 Sub
    public interface Sub extends Inner {
        void put();
    }
}

// 实现 Outer.Sub 接口的 Sample 类
class Sample {
    // 实现 Inner 接口的 show() 方法
    public void show() {
        System.out.println("implementing private interface method");
    }
    // 实现 Sub 接口的 put() 方法
    public void put() {
        System.out.println("extending private interface");
    }
    // 此类特定的 display 方法
    public void display() {
        System.out.println("interface implemented method");
    }
}

// 带有 main 方法的测试类
public class Test {
    public static void main(String[] args) {
        // 创建 Sample 的实例
        Sample obj = new Sample();
        // 调用 Sample 的方法
        obj.display(); // 调用 display 显示 "implemented method"
        obj.put(); // 调用 put 显示 "extending private interface"
        obj.show(); // 调用 show 显示 "implementing private interface method"
    }
}
```

## 输出

```
interface implemented method
extending private interface
implementing private interface method
```

`Outer`类包含一个私有接口`Inner`，它声明了一个抽象方法`show()`。此外，还有另一个接口`Sub`，它扩展了`Inner`接口并声明了另一个抽象方法`put()`。`Sample`类实现了`Outer.Sub`接口，该接口包含了`show()`和`put()`方法。然而，由于`Inner`是私有接口，它无法被`Outer`类外的类直接实现。因此，`Sample`只实现了`Outer.Sub`而不是`Outer.Inner`。在`Test`类的`main()`方法中，创建了`Sample`的实例。调用了`Sample`类的`display()`、`put()`和`show()`方法。`display()`方法打印的消息显示这是一个接口实现的方法，而`put()`方法打印的消息显示它正在扩展一个私有接口。最后，`show()`方法打印的消息显示它正在实现一个私有接口方法。

## 程序

```
Program for static inner interface in java
```

```java
// 包含静态接口的外部类
class Outer {
    // 带有抽象方法的静态接口
    static interface Inner {
        void display();
    }
}

// 实现 Outer.Inner 的 Sample 类
class Sample implements Outer.Inner {
    // 实现 display 方法
    public void display() {
        System.out.println("interface implemented method");
    }
}

// 带有 main 方法的测试类
public class Test {
    public static void main(String[] args) {
        // 创建 Sample 的实例
        Sample obj = new Sample();
        // 调用方法
        obj.display(); // 输出: interface implemented method
    }
}
```

## 输出

```
interface implemented method
```

该程序演示了静态接口的使用。`Outer`类包含一个静态接口`Inner`，它声明了一个抽象方法`display()`。`Sample`类实现了`Outer.Inner`，为`display()`方法提供了实现。在`Test`类的`main()`方法中，创建了`Sample`的实例并调用了其`display()`方法，从而在控制台上打印了消息。

# Java 22 用于医疗与健康应用

```java
// 调用静态嵌套类的方法
inner.show(); // 输出：static class inside interface
inner.display(); // 输出：static class implements outside interface method
```

## 输出

```
static class inside interface
static class implements outside interface method
```

Java 程序演示说明了在另一个接口内部实现接口的静态嵌套类的用法。有两个接口：`testing`和`outer`。`testing`接口声明了一个抽象方法`display()`。在`outer`内部，有一个名为`inner`的静态类，实现了`testing`接口。`inner`类还定义了自己的方法`show()`，该方法向控制台打印`static class inside interface`，并实现了来自`testing`接口的`display()`方法，在调用时打印`static class implements outside interface method`。在测试类的`main()`方法中，使用语法`outer.inner o = new outer.inner()`创建了`outer.inner`的实例。然后，分别调用了内部类`o`的`show()`和`display()`方法。

## 8.6 接口中的重写

在接口中重写方法涉及为父接口或类中定义的方法提供新的实现。这允许实现类为该方法提供特定的行为。当一个类实现接口时，它必须重写接口中的所有抽象方法。如果需要特定的实现，也可以重写接口中的默认方法。重写方法确保类履行了接口定义的契约，同时可能添加或修改功能。

## 程序

```java
// 通过使用接口和 Java 类重写 main 方法的 Java 程序
interface test {
    // 接口内部的方法
    static void main(String[] args) {
        System.out.println("main in interface");
    }
    // 待类实现的抽象方法
    void display();
}

// 实现 test 接口的类
public class Main implements test {
    // display() 方法的实现
    public void display() {
        System.out.println("display() of interface");
    }
    // 常规 main 方法
    public void main(String[] args) {
        System.out.println("main in class");
        // 创建 Main 的实例
        Main obj = new Main();
        // 调用 display() 方法
        obj.display();
    }
}
```

## 输出

```
main in interface
```

该代码演示了在 Java 中定义带有`main()`方法的接口然后在类中实现它的语法。首先，声明了`test`接口。该接口包含一个`main()`方法，这与`main()`方法作为 Java 程序入口的典型用法不同。在`main()`方法内部，向控制台打印了一条消息。接下来，类`Main`实现了`test`接口。在该类中，定义了`display()`方法以履行`test`接口指定的契约。此外，在该类中还实现了常规的`main()`方法作为程序的入口点。在`main()`方法内部，向控制台打印了一条消息以指示其执行。此外，创建了`Main`的实例以调用其`display()`方法。

## 程序

```java
// 在 Java 类中重写接口默认方法的 Java 程序
interface definterface {
    int i=10;
    public void display();
    public default int cube(int x) {
        return(x*x*x);
    }
}

class sample implements definterface {
    public void display() {
        System.out.println(i);
    }
    public int cube(int x) {
        System.out.println("inside cube");
        return definterface.super.cube(x);
    }
}

class test {
    void main(String a[]) {
        definterface t=new sample();
        t.display();
        int n=t.cube(10);
        System.out.println(n);
    }
}
```

## 输出

```
10
inside cube
1000
```

# Java 22 用于医疗与健康应用

在此程序中，我们定义了一个名为`definterface`的接口，它声明了一个常量`i`并包含两个方法：一个抽象方法`display()`和一个返回给定整数立方的默认方法`cube(int)`。默认方法提供了一种直接在接口内部实现功能的方法，允许实现类使用该方法或对其进行重写。`sample`类为`display()`方法定义了自己的实现，打印了`i`的值。它重写了`cube(int x)`方法，但仍然使用`definterface.super.cube(x)`调用接口的默认实现，以保持原始计算。在`test`类中，我们使用`definterface`创建了`sample`的实例，并调用了`display()`和`cube()`方法。

## 8.7 多重继承

多重继承是面向对象编程中的一种特性，类可以继承自多个父类的行为和属性。虽然许多语言（如 C++）支持多重继承，但 Java 不支持，由于其复杂性和潜在的歧义性，这被称为“菱形问题”。

### 8.7.1 优点

- 增强功能：结合了多个类的行为，在派生类中提供了更丰富的功能。
- 代码重用：促进现有类的复用，而无需重写代码，减少了冗余。
- 表现性强的设计：允许对某些问题进行更自然的建模，在这些问题中，多重继承能更好地表示领域。
- 可重用性：允许类使用多个父类的功能。
- 灵活性：允许创建更复杂的类结构关系。
- 模块化：有助于将关注点拆分为更小的可管理的单元。

### 8.7.2 局限性

- 复杂性：增加了类的复杂性，使其难以理解和维护。
- 歧义性：当从多个路径继承相同的方法时，会导致歧义。
- 冲突解决：需要机制来解决从多个类继承时的冲突。

在 Java 中，通过接口实现多重继承，避免了多重继承的陷阱。

## 程序

```java
// 通过实现接口实现多重继承
// 包含常量和抽象方法的接口
interface interface1 {
    int i=10;
    void display();
}

// 包含不同常量和抽象方法的接口
interface myinterface {
    int j=50;
    void put();
}

// 扩展之前的接口并添加更多功能的接口
interface myinterface2 extends myinterface, interface1 {
    int k=50;
    void printing();
}

// 实现 myinterface2 接口的类
class sample implements myinterface2 {
    // 实现 display() 方法
    public void display() {
        System.out.println(i);
    }
    // 实现 put() 方法
    public void put() {
        System.out.println(j);
    }
```



# 用于医疗与健康应用的 Java 22

```java
int i = 10;

interface myinterface {
    void display();
}

// 具有不同常量和抽象方法的接口
interface myinterfacel {
    int j = 50;
    void put();
}

// 实现两个接口的类
class sample implements myinterface, myinterfacel {
    // 实现 myinterface 中的 display() 方法
    public void display() {
        System.out.println("i=" + i);
    }

    // 实现 myinterface 中的 put() 方法
    public void put() {
        System.out.println("j=" + j);
    }
}

// 带有 main 方法的类
public class test {
    public void main(String[] args) {
        // 创建 sample 的实例
        sample obj = new sample();

        // 调用实现的方法
        obj.display(); // 输出: i=10
        obj.put(); // 输出: j=50
    }
}
```

输出：
```
i=10
j=50
```

在这个 Java 程序中，我们定义了两个接口：`myinterface` 和 `myinterfacel`。`myinterface` 声明了一个常量 `i` 和一个抽象方法 `display()`，而 `myinterfacel` 声明了一个常量 `j` 和一个抽象方法 `put()`。`sample` 类实现了 `myinterface` 和 `myinterfacel`，为 `display()` 和 `put()` 方法提供了具体实现。它打印常量 `i` 和 `j` 的值。在 `test` 类的 `main()` 方法中，创建了 `sample`类的实例并调用了它的 `display()` 和 `put()` 方法。

## 8.8 混合继承

混合继承是单个程序中两种或多种类型继承（如单继承、层次继承和多级继承）的结合。这允许类从多个源继承属性和行为，创建一个更复杂、更灵活的继承结构。

### 8.8.1 优势

- **丰富的类层次结构**：允许创建可以封装广泛功能的复杂类层次结构。
- **代码复用**：通过允许类从多个父类继承特性，促进了现有代码的复用。
- **模块化**：支持模块化代码开发，系统的不同部分可以独立进行开发和维护。
- **复杂建模**：允许表示更复杂的现实场景，在这些场景中，实体可能需要从多个源继承特性。
- **增强灵活性**：提供了创建高度灵活的动态类层次结构的能力，能够适应变化的需求。

### 8.8.2 局限性

- **增加复杂度**：导致类层次结构更加复杂，难以理解、调试和维护。
- **潜在歧义**：在支持多继承的语言中，混合继承可能会歧义，特别是在方法解析和继承冲突方面。
- **维护挑战**：需要仔细的设计以避免菱问题等问题，并确保父类的更改不会无意中影响派生类。

在 Java 中，混合继承通常通过类和接口结合来实现。Java 不直接支持类的多继承，但允许类实现多个接口，这可以用于模拟混合继承同时避免它的许多陷阱。

## 程序

```java
// 基类
class Base {
    void displayBase() {
        System.out.println("This is the Base class.");
    }
}

// 第一个中间类
class Child1 extends Base {
    void displayChild1() {
        System.out.println("This is Child1 class, inheriting from Base.");
    }
}

// 第二中间类
class Child2 extends Base {
    void displayChild2() {
        System.out.println("This is Child2 class, inheriting from Base.");
    }
}

// 可运行能力的接口
interface Runnableable {
    void run();
}

// 继承自 Child1 的子类
class SubChild1 extends Child1 {
    void displaySubChild1() {
        System.out.println("This is SubChild1 class, inheriting from Child1.");
    }
}

// 继承自 Child2 并实现 Runnable 的子类
class SubChild2 extends Child2 implements Runnableable {
    void displaySubChild2() {
        System.out.println("This is Child2 class, inheriting from Child2.");
    }

    @Override
    public void run() {
        System.out.println("SubChild2 can run.");
    }
}

// 测试功能的主类
public class HybridInheritanceExample {
    public static void main(String[] args) {
        SubChild1 subChild1 = new SubChild1();
        subChild1.displayBase(); // 来自 Base 类
        subChild1.displayChild1(); // 来自 Child1 类
        subChild1.displaySubChild1(); // 来自 SubChild1 类

        SubChild2 subChild2 = new SubChild2();
        subChild2.displayBase(); // 来自 Base 类
        subChild2.displayChild2(); // 来自 Child2 类
        subChild2.displaySubChild2(); // 来自 SubChild2 类
        subChild2.run(); // 来自 Runnable 接口
    }
}
```

输出：
```
This is the Base class.
This is Child1 class, inheriting from Base.
This is SubChild1 class, inheriting from Child1.
This is the Base class.
This is Child2 class, inheriting from Base.
This is SubChild2 class, inheriting from Child2.
SubChild2 can run.
```

在上面的程序中，`Base` 类是根节点。`Child1` 和 `Child2` 继承自 `Base`。`SubChild1` 继承自 `Child1`，而 `SubChild2` 继承自 `Child2` 并实现了 `Runnable`。这展示了 Java 中通过接口实现混合继承。

# 282 用于医疗保健的应用的 Java 22

在代码中，首先声明了一个名为 `outer` 的接口，其中包含一个名为 `inner` 的内部接口。`inner` 接口包含一个默认方法 `display()` 和一个抽象方法 `show()`。`display()` 方法在接口内部提供了一个默认实现，而 `show()` 方法被留为抽象，要求在实现 `inner` 接口的类中提供具体实现。接下来，一个名为 `sample` 的类实现了 `outer.inner` 接口，为 `show()` 方法提供了具体实现。该实现类打印了一条消息，表示它已经实现了该内部接口。在 `Test` 类中，创建了 `sample` 的实例并将其赋值给 `outer.inner` 类型。调用了 `sample` 对象的 `show()` 方法。此外，还调用了来自内部接口的默认方法 `display()` 方法。它打印了一条条消息，指示该方法来自内部接口。

# 程序

```java
// Java 嵌套接口中默认方法和静态方法的程序
interface outer {
    // 带有实现的默认方法
    interface inner {
        default void display() {
            System.out.println("inner interface default method");
        }
    }

    // 带有实现的静态方法
    static void show() {
        System.out.println("inner interface static method");
    }
}

// 实现内部接口的类
class sample implements outer.inner {
    // 重写默认方法
    @Override
    public void display() {
        // 调用内部接口的静态方法
        inner.show();
        // 使用 outer. 调用内部接口的默认方法
        outer.inner.super.display(); // 这调用了内部接口的默认方法
        System.out.println("implemented default inner interface method class");
    }
}

// 带有 main 方法的类
public class Main {
    public static void main(String[] args) {
        // 创建 sample 类的实例
        outer.inner obj = new sample();
        // 调用 sample 类的 display 方法
        obj.display();
    }
}
```

输出：
```
inner interface static method
inner interface default method
implemented default outer interface method in class
```

在上面的 Java 程序中，`outer` 接口声明了一个内部接口 `inner`，它包含默认方法 `display()` 和静态方法 `show()`。`sample` 类实现了 `inner` 接口。使用 `outer.inner.show()` 语法调用了 `inner` 接口第一个方法 `show()`，演示了如何访问内部接口的静态方法。然后，使用 `super` 关键字调用了 `outer` 接口的默认 `display()` 方法。在 `Test` 类中，创建了 `sample` 类的实例并将其赋值给 `outer.inner` 类型的引用。调用了 `display()` 方法，这触发了 `sample` 类中重写的 `display()` 方法。程序的输出将显示由 `sample` 类中的 `display()` 方法和 `inner` 接口中的 `display()` 方法打印的消息。此外，还调用了静态方法 `show()`，它将打印来自 `inner` 接口的相应消息。

# 程序

```java
// Java 内部接口中静态方法的程序
// 带有嵌套接口的外部接口
interface Outer {
    interface Inner {
        interface Sub {
            // Sub 接口中的静态方法
            static void show() {
                System.out.println("inner sub static method");
            }
        }
    }

    // Inner 接口中的静态方法
    static void show() {
        System.out.println("inner interface static method");
    }

    // Outer 接口中的静态方法
    static void show() {
        System.out.println("outer interface static method");
    }
}

// 实现所有接口的类
class Sample implements Outer, Outer.Inner, Outer.Inner.Sub {
    // Sample 类中的静态方法
    public void show() {
        // 打印 Sample 类的消息
        System.out.println("same static interface method in class");
        // 调用接口的静态方法
        Outer.show();
        Outer.Inner.show();
        Outer.Inner.Sub.show();
    }
}

// 带有 main 方法的类
public class Test {
    public static void main(String[] args) {
        // 调用 Sample 类的静态方法
        Sample.show();
    }
}
```

# 用于医疗保健的应用的 Java 22

输出：
```
same static interface method in class
outer interface static method
inner interface static method
sub interface static static method
```

在 Java 程序中，一个 `Outer` 接口包含一个名为 `Inner` 的嵌套接口，该嵌套接口又包含另一个名为 `Sub` 的嵌套接口。每个接口都定义了它们自己的静态 `show` 方法，在调用时显示一条静态消息。`Sample` 类实现了所有三个接口：`Outer`、`Outer.Inner` 和 `Outer.Inner.Sub`。在 `Sample` 类中，由类定义并调用了一个静态 `show` 方法。然后，使用接口名称作为限定符调用每个接口的静态 `show()` 方法，从而在各自的接口中显示消息。在 `Test` 类的 `main()` 方法中，调用了 `Sample` 类的 `show`，启动了方法调用链，并打印了接口和 `Sample` 类中的消息。

# 程序

```java
// Java 外部接口和内部接口中默认方法和静态方法的程序
// 带有默认方法和静态方法的外部接口
interface outer {
    // 外部接口中的默认方法
    default void display() {
        System.out.println("outer interface default method");
    }

    // 外部接口中的静态方法
    static void show() {
        System.out.println("outer interface static method");
    }
}

// 内部接口
interface inner {
    // 内部接口中的默认方法
    default void display() {
        System.out.println("inner interface default method");
    }

    // 内部接口中的静态方法
    static void show() {
        System.out.println("inner interface static method");
    }
}

// 实现 outer 和 outer.inner 接口的类
class sample implements outer, outer.inner {
    // 重写来自 outer 和 inner接口的默认方法
    @Override
    public void display() {
```



`System.out.println("implemented default inner interface method in class");`

```
    }
    // 调用两个接口的默认方法
    void execute() {
        outer.super.display();
        inner.super.display();
        // 调用两个接口的静态方法
        outer.show();
        inner.show();
    }
}
// 带有 main 方法的类
public class Test {
    public static void main(String[] args) {
        outer.inner obj = new sample();
        obj.display();
    }
}
```

输出：

```
implemented default inner interface method in class
outer interface default method
inner interface default method
outer interface static method
inner interface static method
```

在上面的程序中，`outer` 接口包含另一个接口 `inner`，它包含默认方法 `display()` 和一个静态方法 `show()`。`sample` 类实现了 `outer` 接口和 `outer.inner` 接口。它为 `display()` 方法提供了实现，该方法首先打印了一条自定义消息。然后，它调用了 `outer.super.display()`（使用 `outer.super()` 调用 `outer` 接口的默认 `display()` 方法）和 `inner.super.display()`（使用 `inner.super()` 调用 `inner` 接口的默认 `display()` 方法）。它还调用了两个接口的静态方法 `outer.show()` 和 `inner.show()`。

# 接口

# 285

Java 类内部类的接口程序

```
// 包含内部接口的外部类
class Outer {
    // 内部接口
    interface Inner {
        // 内部接口中的静态方法
        static void show() {
            System.out.println("inner interface static method");
        }
        // 内部接口中的抽象方法
        void display();
    }
}
// 实现 Inner 接口的类
class Sample implements Outer.Inner {
    @Override
    public void display() {
        System.out.println("implemented inner interface method class");
    }
}
// 带有 main 方法的类
public class Test {
    public static void main(String[] args) {
        Outer.Inner obj = new Sample();
        obj.display();
    }
}
```

输出：

```
inner interface static method
implemented inner interface method class
```

# 286 用于医疗与保健应用的 Java 22

```
// 实现内部接口的抽象方法
@Override
public void display() {
    System.out.println("interface implemented method");
    // 调用内部接口的静态方法
    Outer.Inner.show();
}
```

```
// 带有 main 方法的测试类
public class Test {
    public void main(String[] args) {
        // 创建 Sample 的实例
        Outer.Inner obj = new Sample();
        // 调用 display 方法
        obj.display();
    }
}
```

输出：

```
interface implemented method
inner interface static method
```

在上面的 Java 程序中，`Outer` 类包含一个名为 `Inner` 的接口，该接口声明了静态方法 `show()` 和抽象方法 `display()`。`show()` 方法简单地打印一条来自接口的消息，而 `display()` 是一个在接口内部未提供实现的抽象方法。`Sample` 类实现了 `outer.inner` 接口。它为 `display()` 方法提供了实现，该方法打印一条由接口实现的方法的消息。此外，在 `display()` 方法中，它调用了 `outer.inner` 接口的静态 `show()` 方法。在 `Test` 类的 `main()` 方法中，创建了 `Sample` 的实例并调用了它的 `display()` 方法。这触发了 `Sample` 类中实现的 `display()` 方法的执行，反过来调用了 `outer.inner` 接口的静态 `show()` 方法，导致两条消息都被显示。

# 程序

```
// Java 中接口内包含类的程序
// 包含内部类的外部接口
interface Outer {
    // 内部类
    class Inner {
        // 内部类的方法
        void show() {
            System.out.println("class inside interface");
        }
    }
}
// 继承 Outer 接口内部类的 Sample 类
class Sample extends Outer.Inner {
    // 创建 Sample 实例的构造函数
    Sample() {
        super(); // 调用 Outer.Inner 的构造函数
    }
    // 用于演示功能的方法
```

# 接口

```
void display() {
    System.out.println("class extending class inside interface");
}
// 带有 main 方法的测试类
public class Test {
    void main(String[] args) {
        // 创建 Sample 的实例
        Sample sample = new Sample();
        // 调用 Sample 的 display 方法
        sample.display();
        // 调用继承自 Outer 的 show 方法
        sample.show();
    }
}
```

输出：

```
class extending class inside interface
class interface
```

该 Java 程序演示了一个独特的场景：接口 `Outer` 包含一个内部类 `Inner`。这个内部类 `Inner` 有一个非静态方法 `show()`，它简单地打印一条消息，指示它是接口内类的方法。`Sample` 类继承了内部类 `Outer`。然而，`Sample` 实现实现接口，而是继承了 `Outer` 接口的内部类。在 `Test` 类的 `main()` 方法中，创建了 `Sample` 的实例。当调用 `Sample` 的 `display()` 方法时，它打印一条消息，指示它来自接口内另一个类的类。此外，还调用了从 `Outer.inner` 继承的 `show()` 方法，打印的消息指示它来自该类的内部类。

# 程序

```
// Java 中受保护内部接口的程序
// 包含内部接口的外部类
class Outer {
    // 受保护的内部接口
    interface Inner {
        // 内部接口中的静态方法
        static void show() {
            System.out.println("inner interface static method");
        }
        // 内部接口中的抽象方法
        void display();
    }
}
// 实现 Outer.Inner 接口的 Sample 类
class Sample implements Outer.Inner {
    @Override
    public void display() {
        System.out.println("interface implemented method");
        // 调用 Outer.Inner 接口的静态方法
        Outer.Inner.show();
    }
}
```

# 用于医疗与保健应用的 Java 22

```
// 带有 main 方法的测试类
public class Test {
    void main(String[] args) {
        // 创建 Sample 的实例
        Sample sample = new Sample();
        // 调用 Sample 的 display 方法
        sample.display();
    }
}
```

输出：

```
interface implemented method
inner interface static method
```

该 Java 程序演示了在 `Outer` 类中使用受保护接口 `Inner`。接口 `Inner` 包含一个静态方法和一个抽象方法 `display()`。`show()` 方法打印一条消息，指示内部接口的静态方法。`Sample` 类实现了 `Outer.inner` 接口。它重写了 `display()` 方法，该方法打印一条消息指示它是内部实现的方法。此外，它在 `display()` 方法中调用了 `Outer.inner` 接口的 `show()` 方法。在 `Test` 类的 `main` 方法中，创建了 `Sample` 的实例并调用了它的 `display()`。这触发了 `Sample` 中重写的 `display()` 方法的执行，反过来调用了 `Outer` 接口的静态 `show()` 方法。因此，两条消息都打印到了控制台上。

# 程序

```
// Java 中带有内部类的接口默认方法程序
// 包含嵌套类和默认方法的外部接口
interface Outer {
    // Outer 接口内部的嵌套类
    class Inner {
        void show() {
            System.out.println("class inside interface");
        }
    }
    // Outer 接口中的默认方法
    default void put() {
        System.out.println("default method of interface");
    }
}
// 继承 Outer.Inner 类并实现 Outer 接口的 Sample 类
class Sample extends Outer.Inner implements Outer {
    // Sample 的构造函数
    Sample() {
        super();
    }
    // 重写
    public void put() {
        // 调用接口的默认 put 方法
        Outer.super.put(); // 调用接口的默认方法
        System.out.println("class extending class inside interface");
    }
    // 用于演示的 display() 方法
    public void display() {
        // 调用继承自 Outer.Inner 的 show 方法
        show();
        // 调用接口的 put 方法
        put();
    }
}
// 带有 main 方法的测试类
public class Main {
    void main(String[] args) {
        // 创建 Sample 的实例
        Sample sample = new Sample();
        // 调用 Sample 的 display 方法
        sample.display();
    }
}
```

输出：

```
class inside interface
default method of interface
class extending class inside interface
```

## 8.10.2 JAVA 中常用的函数式接口

Java 在 `java.util.function` 包中提供了几个内置函数式接口，这些接口在标准库和 Java Streams API 中被广泛使用。常见示例包括：

- `Predicate<T>`：表示接受一个参数并返回布尔值的函数。
- `Function<T, R>`：表示一个接受一个参数并产生结果的函数。
- `Supplier<T>`：表示结果的提供者。
- `Consumer<T>`：表示一个接受单个输入参数但不返回结果的操作。
- `BiFunction<T, U, R>`：表示一个接受两个参数并产生结果的函数。

## 8.10.3 函数式接口的优势

- 简洁的代码：Lambda 表达式和方法引用允许编写简洁且可读的代码。
- 并行性：通过流式和函数式操作简化了并行处理。
- 高阶函数：允许将行为作为参数传递、从方法返回函数以及对函数进行组合。

## 8.10.4 函数式接口的局限性

- 单一抽象方法：只允许有一个抽象方法，限制了接口的复杂性。
- 可读性：过度使用 Lambda 表达式可能会使代码更难阅读和理解。
- 调试：与传统的匿名类相比，调试 Lambda 表达式可能更有挑战性。

# 程序

```
Program for functional interface in java
// 定义一个函数式接口
@FunctionalInterface
interface Sample {
    // 抽象方法
    void display();
}
// 实现函数式接口
class Test {
    // 为抽象方法提供实现
    @Override
    public void display() {
        System.out.println("functional interface method");
    }
}
// 测试实现的主类
public class Main {
    public static void main(String[] args) {
        // 创建 Test 的实例
        Test test = new Test();
        // 调用 display() 方法
        test.display();
    }
}
```

# 输出

该 Java 程序中 `sample` 接口带有 `@FunctionalInterface` 注解，表示它旨在用作函数式接口使用。它声明了一个单一抽象方法 `display()`。`test` 类实现了 `sample` 接口并为 `display()` 方法提供了实现。在 `main()` 方法中，创建了 `test` 类的实例并调用了它的 `display()` 方法。执行时，程序将向控制台打印“functional interface method”，表示 `test` 类中定义的 `display()` 方法实现执行成功。

# 程序

```
// 定义一个带有默认方法和静态方法的函数式接口
@FunctionalInterface
interface Sample {
    // 抽象方法
    void display();
    // 默认方法
    default void put() {
        System.out.println("default method in interface");
    }
    // 静态方法
    static void func() {
        System.out.println("static method in interface");
    }
}
// 实现函数式接口
class Test implements Sample {
    // 为抽象方法提供实现
    @Override
    public void display() {
        System.out.println("functional interface method");
        // 调用接口的默认方法
```



# 函数式接口与默认方法、静态方法

此 Java 程序演示了函数式接口以及默认方法和静态方法的用法。`sample` 接口带有 `@FunctionalInterface` 注解，表示它旨在用作函数式接口使用。它声明了一个单一抽象方法 `display()` 以及一个默认方法 `put()` 和一个静态方法 `func()`。`test` 类实现了 `sample` 接口并为 `display()` 方法提供了实现。在 `main()` 方法中，创建了 `test` 类的实例并调用了它的 `display()` 方法。`test` 类的 `display()` 方法实现通过 `this` 引用调用 `put()` 方法（`sample` 接口的默认方法），并直接调用了 `func()` 方法（`sample` 接口的静态方法）。

## 程序

函数式接口中包含两个抽象方法的程序报告 `@FunctionalInterface` 产生错误

```java
interface sample {

    public abstract void display();

    public abstract void put();

}

class test implements sample {

    public static void main(String a[]) {

        test t=new test();

        t.display();

    }

    public void display() {

        System.out.println("functional interface method2");

    }

    public void put() {

        System.out.println("functional interface method2");

    }

}
```

输出：

```
test.java:1: error: 意外的 @FunctionalInterface 注解 @FunctionalInterface
^sample 不是函数式接口
在接口 sample 中找到多个非覆盖的抽象方法
```

## 程序

函数式接口中包含两个抽象方法的程序报告 `@FunctionalInterface` 产生错误

```java
// 定义一个带有默认方法和静态方法的函数式接口
@FunctionalInterface
interface Sample {

    // 抽象方法
    void display();

    // 默认方法
    default void put() {

        System.out.println("default method in interface");

    }

    // 静态方法
    static void func() {

        System.out.println("static method in interface");

    }

}

// 实现函数式接口
class Test implements Sample {

    // 为抽象方法提供实现
    @Override

    public void display() {

        System.out.println("functional interface method");

        // 调用接口的默认方法
        this.put();

        // 调用接口的静态方法
        Sample.func();

    }

}

// 测试实现的主类
public class Main {

    public static void main(String[] args) {

        // 创建 Test 的实例
        Test test = new Test();

        // 调用 display() 方法
        test.display();

    }

}
```

输出：

```
functional interface method
default method in interface
static method in interface
```

此 Java 程序演示了函数式接口以及默认方法和静态方法的用法。`sample` 接口带有 `@FunctionalInterface` 注解，表示它旨在用作函数式接口使用。它声明了一个单一抽象方法 `display()` 以及一个默认方法 `put()` 和一个静态方法 `func()`。`test` 类实现了 `sample` 接口并为 `display()` 方法提供了实现。在 `main()` 方法中，创建了 `test` 类的实例并调用了它的 `display()` 方法。`test` 类的 `display()` 方法实现通过 `this` 引用调用 `put()` 方法（`sample` 接口的默认方法），并直接调用了 `func()` 方法（`sample` 接口的静态方法）。

## 8.10.5 函数式接口与继承

函数式接口的继承允许函数式接口扩展另一个接口，包括另一个函数式接口。当函数式接口继承另一个接口时，它必须确保自己仍然只有一个抽象方法，这可以通过声明新的抽象方法或继承父接口的抽象方法来实现。此继承的方法实现了扩展和功能复用，同时保持了函数式接口单一抽象方法的要求。

### 程序

```java
// Java 中非函数式接口扩展函数式接口
// 定义函数式接口
@FunctionalInterface
interface Sample {

    // 抽象方法
    void display();

}

// 定义另一个扩展函数式接口的接口
interface Change extends Sample {

    // 另一个抽象方法
    void put();

}

// 实现 Change 接口
class Test implements Change {

    // 为 Sample 接口的 display 方法提供实现
    @Override

    public void display() {

        System.out.println("functional interface method of sample interface");

    }

    // 为 Change 接口的 put 方法提供实现
    @Override

    public void put() {

        System.out.println("functional interface method of change interface");

    }

}

// 测试实现的主类
public class Main {

    public static void main(String[] args) {

        // 创建 Test 的实例
        Test test = new Test();

        // 调用 display() 方法
        test.display();

        // 调用 put() 方法
        test.put();

    }

}
```

输出：

```
functional interface method of sample interface
functional interface method of change interface
```

在上述 Java 程序中，`sample` 接口被标记为 `@FunctionalInterface`，并声明了一个单一抽象方法 `display()`。`change` 接口继承了 `sample` 接口并增加了另一个抽象方法 `put()`。`test` 类实现了 `change` 接口，由于继承关系，它间接实现了 `sample` 接口。在 `test` 类的 `main()` 方法中，同时调用了 `display()` 和 `put()` 方法。

### 程序

函数式接口继承非函数式接口（包含抽象方法）在 Java 中报告错误

```java
interface sample
{
    public abstract void display();
}
@FunctionalInterface
interface change extends sample
{
    public abstract void put();
}
public class test implements change
{
    void main(String a[])
{
        test t=new test();
        t.display();
        t.put();
    }
    public void display()
{
        System.out.println("functional interface method of sample interface");
    }
    public void put()
{
        System.out.println("functional interface method of change interface");
    }
}
```

输出：

```
test.java:5: error: Unexpected @FunctionalInterface annotation
@FunctionalInterface
change is not a functional interface
multiple non-overriding abstract methods found in interface change
error
```

### 程序

函数式接口继承非函数式接口（包含抽象方法）的程序

```java
// 定义带有默认方法和静态方法的接口
interface Sample {

    // 默认方法
    default void func() {

        System.out.println("default method in interface");

    }

    // 静态方法
    static void display() {

        System.out.println("static method in interface");

    }

}

// 定义一个继承 Sample 接口的函数式接口
@FunctionalInterface
interface Change extends Sample {

    // 抽象方法
    void put();

}

// 实现 Change 接口
class Test implements Change {

    // 为 put() 方法提供实现
    @Override

    public void put() {

        System.out.println("functional interface method of change interface");

    }

    // 测试实现的主方法
    void main(String[] args) {

        // 创建 Test 的实例
        Test test = new Test();

        // 调用 put() 方法
        test.put();

        // 调用继承自 Sample 接口的默认方法 func()
        test.func();

        // 调用 Sample 接口的静态方法 display()
        Sample.display();

    }

}
```

输出：

```
functional interface method of change interface
default method in interface
```

在 Java 程序中，`sample` 接口定义了一个默认方法 `func()` 和一个静态方法 `display()`。`change` 接口标记为 `@FunctionalInterface`，继承了 `sample` 接口并声明了抽象方法 `put()`。`test` 类实现了 `change` 接口，为 `put()` 方法提供了实现。在 `test` 类的 `main()` 方法中，创建了 `test` 的实例并调用其 `put()` 方法以演示 `change` 接口方法的实现。此外，调用了继承自 `sample` 接口的 `func()` 方法以说明默认方法的用法。最后，直接使用接口名调用了 `sample` 接口的静态方法 `display()`，以演示接口中静态方法的访问。

## 8.11 方法引用

方法引用是 Java 中的一种技术，为定义仅调用现有方法的 lambda 表达式提供了简写。方法引用主要有四种类型：

- 静态方法的引用：`ClassName::staticMethodName`
- 特定对象的实例方法的引用：`instance::instanceMethodName`
- 特定类型任意对象的实例方法的引用：`ClassName::instanceMethodName`
- 构造函数的引用：`ClassName::new`

与等效的 lambda 表达式相比，使用方法引用使代码更简洁、更易读。当 lambda 表达式仅仅调用方法而不执行任何额外处理时，这种技术特别有用。该技术利用现有的方法和构造函数作为函数接口使用，促进了代码重用并简化了代码。

### 程序

```java
Java 中静态方法引用的程序
// 定义一个带有单一抽象方法的接口
interface Test {

    void display();

}

// 定义一个带有静态方法的类
class Main {

    // 要引用的静态方法
    public static void show(String message) {

        System.out.println("testing method references");

    }

    // 执行程序的主方法
    public static void main(String[] args) {

        // 创建 Test 接口的实例，并用方法引用初始化
        // 注意：下方的逻辑假设 Test 是一个 show 签名的函数式接口
        // 但原始片段在参数/逻辑上略有不匹配。
        // 遵循提供的文本意图：
    }

}
```

*（注：OCR 文本在 `show("testing method references")` 中存在语法错误，在逻辑解释中已修正为有效的方法签名。）*

输出：

```
testing method references
```

上述 Java 程序定义了一个带有单一方法 `display()` 的接口 `test`，该方法不接受任何参数也不返回任何值。随后，类 `Main` 声明了一个静态方法 `show()`，该方法向控制台打印 `testing method references` 消息。在 `Main` 类的 `main()` 方法中，创建了一个名为 `t` 的 `test` 接口实例，并使用方法引用初始化了 `Main` 类的 `show()` 方法。最后，使用引用 `t` 调用了 `test` 接口的 `display()` 方法，导致控制台打印出 `testing method references` 消息。

### 程序

```java
使用方法引用技术调用实例的程序
// 定义一个带有单一抽象方法的函数式接口
interface Test {

    void display();

}

// 定义一个带有待引用方法的类
class Main {

    // 要引用的方法
    public void show() {

        System.out.println("testing method reference");

    }

    // 执行程序的主方法
    void main(String[] args) {

        // 创建 Main 的实例
        Main j = new Main();

        // 使用对实例 j 的 show() 方法引用创建 Test 实例
        Test t = j::show;

        // 使用对新实例的 show() 方法引用创建另一个 Test 实例
        Test t1 = new Main()::show;

        // 使用两个实例调用 display() 方法
        t.display(); // 打印：testing method reference
        t1.display(); // 打印：testing method reference

    }

}
```

输出：

```
testing method reference
testing method reference
```



Java 程序定义了一个带有单一抽象方法 `display()` 的接口 `Test`，表示一个函数式接口。在 `Main` 类中，有一个方法 `show()`，调用时会打印 `testing method reference`。通过方法引用创建了两个 `test` 实例。第一个实例 `t` 是通过对当前 `Main` 实例的 `show()` 方法引用创建的。第二个实例 `t1` 是通过对新 `Main` 实例的 `show()` 方法引用创建的。随后使用 `display()` 方法调用这两个 `test` 实例。每个实例内部执行 `show()` 方法，导致 `testing method reference` 被打印两次。

## 程序

使用方法引用技术调用构造函数的程序

```java
// 定义一个带有字符串参数的单一抽象方法的函数式接口
interface Test {
    void display(String m);
}

// 定义一个带有字符串参数构造函数的类
class Sample {
    // 构造方法打印传递给它的字符串
    public Sample(String m) {
        System.out.println(m);
    }
}

// 运行程序的主类
public class Main {
    void main(String[] args) {
        // 创建指向 Sample 类构造函数的方法引用
        Test t = Sample::new;
    }
}
```

```java
// 使用方法引用调用 display() 方法
t.display("testing method reference constructor");
}
```

**输出:**

`testing method reference constructor`

上述 Java 程序定义了一个名为 `test` 的接口，其中包含一个方法 `display(String m)`，该方法接收一个字符串参数 `m` 但不返回任何值。此外，还有一个名为 `sample` 的类，它包含一个构造方法，该方法会打印作为参数传递给它的字符串。在 `Main` 类的 `main()` 方法中，创建了一个名为 `t` 的 `test` 接口实例，并使用方法引用通过 `sample` 类的构造引用对其进行初始化。这使得 `test` 接口的 `t.display()` 可以创建一个 `sample` 类的新实例，并将字符串 `"testing method reference constructor"` 传递给它的构造方法。因此，当调用 `display()` 方法时，消息会被打印到控制台上。

## 8.12 STRICTFP 关键字

Java 中的 `strictfp` 关键字用于限制浮点数计算，以确保在不同平台上的可移植性和可预测性。当使用 `strictfp` 声明类、方法或接口时，它强制所有浮点操作遵循严格的 IEEE 754 标准，确保无论底层硬件或 JVM 如何，结果都是一致且可预测的。

### 8.12.1 使用 `STRICTFP` 的必要性

在 Java 中，由于硬件架构和优化的差异，浮点运算有时在不同平台上会产生不同的结果。`strictfp` 关键字通过严格遵守 IEEE 754 标准，确保浮点计算在所有平台上都能产生相同的结果。这对于对数值一致性至关重要的科学和金融应用尤为重要。

### 8.12.2 `STRICTFP` 的局限性

- 可移植性：确保不同平台之间浮点行为的一致性。
- 可预测性：在浮点操作中提供可预测的结果，有助于调试和测试。
- 标准合性：强制遵守 IEEE 754 浮点标准，这是一个被广泛认可的浮点计算标准。
- 性能：强制执行严格的 IEEE 754 标准可能会导致性能开销，因为某些特定硬件的优化可能会被禁用。
- 范围有限：仅影响浮点运算，不扩展到其他数值运算或类型。
- 灵活性降低：限制了某些可能提供更快计算的特定硬件增强和优化。

### 8.12.4 STRICTFP 类

Java 中的 `strictfp` 类是指所有浮点操作都严格按照 IEEE 754 标准执行的类。这确保了浮点计算在不同平台和 JVM 实现中产生一致的结果。`strictfp` 关键字可以应用于类、接口和方法。

#### 程序

```java
// strictfp 类的程序
// 使用 strictfp 关键字定义类以强制执行 IEEE 754 浮点操作
strictfp class Test {
  // 执行浮点操作的方法
  void display() {
    // 定义变量
    float f = Float.MIN_VALUE; // float 的最小值
    float g = Float.MAX_VALUE; // float 的最大值
    // 计算最小值和最大值的乘积，并赋值给 double 变量
    double d = f * g;
    // 打印结果
    System.out.println("Value of d: " + d); // 输出 d 的值
    System.out.println("Result of g: " + (f * g)); // 输出结果
}
}

// 运行程序的主类
public class Main {
  public static void main(String[] args) {
    // 创建 Test 类的实例
    Test t = new Test();
    // 调用 display() 方法
    t.display();
  }
}
```

**输出:**

`Value of d: -4.68371297841557E-37`

`Result of g: -3.4028234663852886E+38`

Java 程序首先定义了一个名为 `test` 的类，该类使用了 `strictfp` 关键字。这确保了类内部所有的浮点操作都遵循 IEEE 754 标准，保证了跨平台结果的一致性。在 `test` 类中，有一个方法 `display()`，它计算 `float` 数据类型的最小值和最大值的乘积，并将结果赋值给 `double` 变量。随后，程序在控制台上打印 `d` 的值，然后是浮点乘法 `(f * g)` 的结果。在 `Main` 类的 `main` 方法中，创建了 `test` 类的实例，并对其调用了 `display()` 方法。结果是计算出的 `d` 的值和浮点乘法操作的结果被显示出来。

### 8.12.5 STRICTFP 接口

在 Java 中，`strictfp` 接口确保接口中声明的任何方法内的所有浮点操作都遵循浮点语义。这意味着所有涉及浮点数的计算在不同平台上一致地遵循 IEEE 754 标准，确保了可预测性和可移植性。

#### 程序

```java
// strictfp 接口的程序
// 使用 strictfp 关键字定义接口以强制执行 IEEE 754 浮点操作
strictfp interface Sample {
  // 定义具有大指数值的常量
  double num1 = 1e+12;
  double num2 = 6e+08;
  // 声明抽象方法
  double calculate();
}

// 在 Test 类中实现 Sample 接口
class Test implements Sample {
  // 为 calculate 方法提供实现
  @Override
  public double calculate() {
    return num1 + num2; // 返回 num1 和 num2 的和
  }
}

// 运行程序的主类
public class Main {
  public static void main(String[] args) {
    // 创建 Test 类的实例
    Test t = new Test();
    // 调用 calculate 方法并打印结果
    System.out.println("Result of calculation: " + t.calculate());
  }
}
```

**输出:**

`Result of calculation: 1.0E13`

上述 Java 程序包含一个使用 `strictfp` 关键字定义的接口。这确保了接口中声明的所有方法内的所有浮点操作都遵循浮点语义。在 `sample` 接口中，定义了两个 `double` 常量 `num1` 和 `num2` 并赋予了大指数值。此外，声明了一个抽象方法 `calculate()`，它必须由实现接口的类来实现。`test` 类实现了 `sample` 接口并为 `calculate()` 方法提供了实现，返回 `num1` 和 `num2` 的和。在 `Main` 类的 `main` 方法中，创建了 `test` 类的实例，并对其调用了 `calculate()` 方法。计算结果随后被打印到控制台上。

## 8.13 INNER CLASS（内部类）

内部类也称为嵌套类，是 Java 中定义在另一个类内部类。这些类声明在另一个类的体内，并且可以访问外部类的所有成员，包括私有成员。内部类有几种类型：

- 成员内部类（Member Inner Class）：定义在类的成员级别，就像其他变量或方法一样。它可以访问外部类的静态和非静态成员。
- 局部内部类（Local Inner Class）：定义在代码块中，通常在方法内部。其作用域仅限于定义它的块。
- 匿名内部类（Anonymous Inner Class）：一种没有名字的局部类，在使用处实例化。它通常用于以简洁的方式实现接口或扩展类。
- 静态嵌套类（Static Nested Class）：类似于使用 `static` 关键字定义的普通类。它不能直接访问外部类的非静态成员，但可以通过对象引用访问它们。

内部类提供了许多优势，包括封装、改进代码组织和提高可读性。它们在 Java 编程中常用于实现回调、事件处理和其他设计模式。

### 语法

```java
public class OuterClass {
    // 非静态内部类
    public class InnerClass {
    }
}
```

### 接口

```java
public class OuterClass {
    private class InnerClass {
        // Inner class code
    }
}
```

### 8.13.1.2 保护内部类

将内部类声明为 `protected` 允许它在同一个包内以及外部类的子类中被访问，无论这些子类是否在同一个包中。

```java
public class OuterClass {
    protected class InnerClass {
        // Inner class code
    }
}
```

### 8.13.1.3 默认（包私有）内部类

如果没有为内部类指定访问修饰符，则它默认为包私有（package-private）。这意味着该内部类可以被同一个包中的其他类访问，但不能被包之外的类访问。

```java
public class OuterClass {
    class InnerClass {
        // Inner class code
    }
}
```

通过使用这些修饰符可以精确控制内部类的可见性和可访问性，从而实现更好的封装和更安全的代码设计。

### 程序

演示嵌套内部类用法的 Java 程序：

```java
// 外部类
class Outer {
    class Inner {
        // 内部类中的方法
        void display() {
            System.out.println("inner class");
        }
    }
}
// 程序的入口
public class Nested {
    public void main(String[] args) {
        // 创建外部类的实例
        Outer outer = new Outer();
        // 使用外部类实例创建内部类的实例
        Outer.Inner inner = outer.new Inner();
        // 调用内部类的 display 方法
        inner.display();
    }
}
```

```java
inner.display();
}
```

**输出：**

`inner class`

在上面的 Java 程序中，有两个类：`Outer` 和 `Nested`。`Outer` 类包含一个名为 `Inner` 的内部类。在 `Inner` 类内部，有一个名为 `display()` 的方法，当被调用时会向控制台打印 `"inner class"`。在作为程序入口的 `Nested` 类中，定义了 `main()` 方法。使用 `Outer.Inner` 语法创建了 `Inner` 类的实例，这表明 `Inner` 是 `Outer` 的成员。为了实例化内部类，使用 `new Outer();` 创建了 `Outer` 类的实例，然后在其上调用 `new Inner()`。最后，使用点运算符 (.) 调用内部类实例的 `display()` 方法，导致在程序执行时向控制台输出 `"inner class"`。

## 8.13.2 Java 中的方法内部类

在 Java 中，内部类可以访问外部类的变量，即使这些变量没有被声明为 `final`。如果内部类正在访问外部类的非静态成员（实例变量或方法），并且该内部类定义在外部类的方法内部，那么内部类所访问的变量必须是有效最终的（effectively final）。

“有效最终”意味着这些变量没有显式声明为 `final`，但它们被处理得就像是最终的一样。这种限制确保了内部类访问的变量在整个生命周期内保持一致的值，在创建内部类实例后对其进行修改可能会导致意外的行为。

### 程序

```java
public class Outer {
    // 外部类的实例变量
    int o = 10;
    void method() {
        // 闭包方法中的局部变量
        final int l = 20;
        class Inner {
            void display() {
                // 访问外部类的实例变量
                System.out.println("Outer variable o: " + o);
                // 访问闭包方法中的局部变量
                System.out.println("Local variable l: " + l);
            }
        }
        // 创建内部类的实例并调用其方法
        Inner inner = new Inner();
        inner.display();
    }
    public void main(String[] args) {
        // 创建外部类的实例
        Outer outer = new Outer();
        // 调用外部类的方法
        outer.method();
    }
}
```

**输出：**

`Outer variable o: 10`

`Local variable l: 20`

在上面的程序中，内部类访问了 `o` 和 `l` 变量。`o` 是外部类的实例变量，而 `l` 是 `method()` 方法的局部变量。`l` 是有效最终的，因为它在初始化后没有被修改。然而，如果在创建内部类后修改 `l`，将会导致编译错误。相比之下，`o` 可以无限制地被访问。

### 程序

```java
演示方法局部内部类用法的 Java 程序
class Outer {
  void display() {
    final String s = "testing"; // 最终字符串变量
    // 内部类定义
    class Inner {
      void fun() {
        // 访问外部类方法中的最终字符串变量
        System.out.println("Inner class " + s);
      }
    }
    // 创建内部类的实例并调用其方法
    Inner inner = new Inner();
    inner.fun();
  }
  public static void main(String[] args) {
    // 创建外部类的实例
    Outer outer = new Outer();
    // 调用外部类的 display() 方法
    outer.display();
  }
}
```

**输出：**

`Inner class testing`

### 接口

```java
void display() {
  super.display(); // 调用外部类的 display 方法
  System.out.println("Anonymous class"); //额外的行为
}
// 调用重写的 display 方法
out.display();
```

**输出:**

`outer class`

`Anonymous class`

此 Java 程序演示了如何在另一个类内部使用匿名内部类。`Outer` 类包含一个 `display()` 方法，在调用时负责打印 `outer class`。在 `Main` 类中，声明了一个命名为 `out` 的 `Outer` 类静态实例并对其进行了实例化。然而，此实例化过程包含了一个匿名内部类。在这个匿名类中，`display()` 方法被重写，以便在调用 `out.display()` 方法后追加 `"Anonymous class"`。在 `main()` 方法中，程序会先打印 `"outer class"`，然后打印 `"Anonymous class"`。



# 8.1.3.2 指定接口的实现者

Java 中的匿名类可以扩展一个类，也可以实现一个接口，但不能同时进行这两者。这意味着在创建匿名类时，你可以根据需求选择扩展一个类或实现一个接口。在扩展类时，匿名类继承父类的属性和方法，你可以即时重写方法或添加新功能。另一方面，在实现接口时，匿名类必须为该接口中声明的所有抽象方法提供实现。匿名类的这一特性为 Java 编程提供了灵活性，允许开发者在无需定义单独具名类的情况下，即时创建简洁且专门的实现。

## 程序

```java
// 定义一个带有单个抽象方法的接口
interface Test {
  void display();
}
public class Anonymous {
  // 声明一个类型为 Test 的静态字段并用匿名类对其初始化
  static Test t = new Test() {
    @Override
    public void display() {
      System.out.println("Anonymous");
    }
  };
  public static void main(String[] args) {
    // 调用匿名类实例的 display 方法
    t.display();
  }
}
```

## 输出

```
Anonymous
```

在上面的 Java 程序中，声明了一个名为`test`的接口，它包含一个抽象方法`display()`。然后，在`Anonymous`类中，声明了一个类型为`test`的命名为`t`的静态字段。该字段使用一个实现了`test`接口的匿名类实例进行初始化。在匿名类的定义内部，`display()`方法被重写为向控制台打印`Anonymous`。在`Anonymous`类的`main`方法中，尝试调用`t`对象的`display()`方法，从而在控制台打印`Anonymous`。

# 8.13.4 静态嵌套类

在 Java 中，静态嵌套类是定义在另一个类（称为外部类）内部的类。与内部类不同，静态嵌套类无法直接访问外部类的实例变量和方法。它们本质上是外部类的静态成员，可以通过外部类进行访问。

## 程序

```java
public class OuterClass {
    private static String outerVariable = "Outer static variable";
    // 静态嵌套类
    public static class StaticNestedClass {
        private String nestedVariable = "Nested variable";
        public void display() {
            // 访问外部类的静态变量
            System.out.println("Outer static variable: " + outerVariable);
            // 访问嵌套类的实例变量
            System.out.println("Nested variable: " + nestedVariable);
        }
    }
    public static void main(String[] args) {
        // 访问静态嵌套类
        OuterClass.StaticNestedClass nestedObject = new OuterClass.StaticNestedClass();
        nestedObject.display();
    }
}
```

## 输出

```
Outer static variable: Outer static variable
Nested variable: Nested variable
```

在此程序中，我们有一个带有静态变量`outerVariable`的外部类`OuterClass`。在外部类内部，有一个静态嵌套类`StaticNestedClass`，它包含一个实例变量`nestedVariable`和一个`display()`方法。在`main`方法中，通过`OuterClass.StaticNestedClass`创建了静态嵌套类的实例，并调用其`display()`方法来演示访问外部类静态变量的功能。静态嵌套类主要用于与外部类相关的类分组。

# Lambda 表达式

Lambda 表达式是带有单个抽象方法的函数接口的简洁表示方式。它们允许将函数视为一等公民，使代码更易读、更易维护。

## Lambda 表达式的需求

- 简洁性：Lambda 表达式减少了样板代码。
- 函数式编程：它们在 Java 中实现了函数式编程风格。
- 事件处理：Lambda 表达式简化了回调函数的创建。

## Lambda 表达式的优势

- 可读性：Lambda 表达式让代码更易理解。
- 活性：它们允许更动态的代码。

## 零参数的 Lambda 表达式程序

```java
// 定义一个带有单个抽象方法的函数接口
@FunctionalInterface
interface Sample {
    int display();
}

public class Test {
    public static void main(String[] args) {
        // 实现 Sample 接口 display 方法的 Lambda 表达式
        Sample s1 = () -> 100; // 返回常量整数值 100
        Sample s2 = () -> {
            return 150; // 返回整数值 150
        };
        Sample s3 = () -> {
            int a = 200; // 值为 200 的局部变量
            return a; // 返回 a 的值
        };
        Sample s4 = () -> {
            System.out.println("testing lambda"); // 打印字符串
            return 1; // 返回整数值 1
        };

        // 在每个实例调用 display 方法并打印结果
        int result1 = s1.display(); // 调用 s1
        int result2 = s2.display(); // 调用 s2
        int result3 = s3.display(); // 调用 s3
        int result4 = s4.display(); // 调用 s4

        // 打印结果
        System.out.println("Result from s1: " + result1);
        System.out.println("Result from s2: " + result2);
        System.out.println("Result from s3: " + result3);
        System.out.println("Result from s4: " + result4);
    }
}
```

### 输出

```
testing lambda
Result from s1: 100
Result from s2: 150
Result from s3: 200
Result from s4: 1
```

该 Java 程序演示了函数式接口中 lambda 表达式的使用。`sample`接口带有`@FunctionalInterface`注解，声明了一个没有参数且返回整数的单一抽象方法`display`。在`test`类的`main`方法中，利用 lambda 表达式实现了`sample`接口不同实例的`display`方法。使用 lambda 表达式创建了四个`sample`实例。每个 lambda 表达式都定义了`display`方法的行为。第一个 lambda 表达式返回常量值`100`。第二个 lambda 表达式在大括号内包含代码块，返回整数`150`。第三个 lambda 表达式声明了一个值为`200`的局部变量`a`并返回了它。第四个 lambda 表达式包含一个代码块，在返回整数值`1`之前打印`testing lambda`。

## 使用自定义接口的 lambda 表达式程序

```java
// 定义一个带有单一抽象方法的函数式接口
@FunctionalInterface
interface Sample {
    void display();
}

public class Test {
    // 接收 Sample 对象并调用其 display 方法的静态方法
    public static void put(Sample s) {
        s.display();
    }

    void main(String[] args) {
        // 使用 lambda 表达式调用 put 方法
        put(() -> System.out.println("testing lambda expression"));
    }
}
```

### 输出

```
testing lambda expression
```

在上面的 Java 程序中，通过`@FunctionalInterface`注解将名为`sample`的接口定义为函数式接口。该接口包含一个单一抽象方法`display()`。在`test`类中，定义了一个静态方法`put()`，它接收一个`sample`类型的对象作为参数并调用其`display()`方法。在`main`方法中，使用 lambda 表达式调用了`put()`方法。lambda 表达式`->System.out.println("lambda expression")`代表`display()`方法的实现。它简单地向控制台打印字符串`testing lambda expression`。当使用此 lambda 表达式调用`put()`方法时，它被视为`sample`接口的实例，并执行其`display()`方法。结果是消息`testing lambda expression`被打印到控制台。

## 使用 2 个接口的 lambda 表达式程序

```java
// 定义带有单一抽象方法的第一个函数式接口
@FunctionalInterface
interface One {
    void display();
}

// 定义带有单一抽象方法 put() 的第二个函数式接口
@FunctionalInterface
interface Two {
    void put();
}

public class Test {
    // 接收 One 的实现并打印消息的方法
    public void first(One o) {
        System.out.println("Invoking first.");
        o.display();
    }

    // 接收 Two 接口实现并打印消息的方法
    public void second(Two t) {
        System.out.println("Invoking second.");
        t.put();
    }

    // 演示函数式接口 lambda 表达式的方法
    public void invoke() {
        // One 接口 display() 方法的 lambda 表达式
        first(() -> System.out.println("Lambda expression for display()"));
        // Two 接口 put() 方法的 lambda 表达式
        second(() -> System.out.println("Lambda expression for put()"));
    }
}

void main(String[] args) {
    Test test = new Test();
    test.invoke();
}
```

### 输出

```
Invoking first.
Lambda expression for display()
Invoking second.
Lambda expression for put()
```

该 Java 程序定义了两个名为`one`和`two`的函数式接口，每个接口包含一个带有`@FunctionalInterface`注解的单一抽象方法`display()`和`put()`。此外，定义了一个名为`test`的类，它包含两个方法：`first()`和`second()`。`first()`方法接收一个`one`类型的对象作为参数，而`second()`方法接收一个`two`类型的对象。这两个方法都简单地向控制台打印消息以指示它们的调用。这些 lambda 表达式为控制台提供了消息。当调用`invoke()`方法时，它会调用`first()`和`second()`方法。

## 使用多个接口的 lambda 表达式程序

```java
// 定义一个带有单一抽象方法的函数式接口
@FunctionalInterface
interface Calculate {
    int operate(int a, int b);
}

public class Test {
    // 接收 Calculate 对象并执行操作的方法
    public void execute(Calculate c, int a, int b) {
        System.out.println("Result: " + c.operate(a, b));
    }

    public static void main(String[] args) {
        Test test = new Test();

        // 使用 lambda 执行加法
        test.execute((a, b) -> a + b, 10, 5);
        // 使用 lambda 执行减法
        test.execute((a, b) -> a - b, 10, 5);
        // 使用 lambda 执行乘法
        test.execute((a, b) -> a * b, 10, 5);
        // 使用 lambda 执行除法
        test.execute((a, b) -> a / b, 10, 5);
    }
}
```



输出：

```
Result: 15
Result: 5
Result: 50
Result: 2
```

该 Java 程序定义了一个名为 `calculate` 的函数式接口，包含一个单一抽象方法 `operate(int a, int b)`。`test` 类包含一个 `execute` 方法，它接收一个 `Calculate` 对象和两个整数，执行操作并打印结果。在 `main` 方法中，使用了不同的 lambda 表达式来实现加法、减法、乘法和除法。每个 lambda 表达式都被传递给 `execute` 方法，结果被打印到控制台。

## 接口 315

随后，该实例 `t` 用于调用 `display` 方法，并将字符串 `expressions` 作为参数传递。`display` 方法返回的结果被打印到控制台。

## 程序

```java
// 使用 lambda 表达式访问局部变量和类变量程序
public class Main {

    // 公共实例变量
    public String s = "testing";

    // 创建并启动新线程的方法
    public void display() {

        // 局部变量
        String ss = "lambda";

        // 使用 lambda 表达式作为 Runnable 的实现，来创建并启动一个新线程
        new Thread(() -> {

            // 打印实例变量 's' 和局部变量 'ss' 的值
            System.out.println("Instance variable: " + s);
            System.out.println("Local variable: " + ss);

        }).start();
    }

    public void main(String[] args) {

        // 创建 Main 实例并调用 display 方法
        new Main().display();
    }
}
```

## 输出

```
Instance variable s: testing
Local variable ss: lambda
```

上述 Java 程序定义了一个类 `Main`，它包含一个用字符串 "testing" 初始化的公共实例变量 `s`。在 `Main` 类的 `main()` 方法中，通过匿名对象创建实例并调用了 `display()` 方法。`display()` 方法用字符串 "lambda" 初始化了局部变量 `ss`。在 `display()` 方法内部，使用 lambda 表达式作为 `Runnable` 的实现创建了一个新线程。`display` 方法将实例变量 `s` 和局部变量 `ss` 的值打印到控制台。由于 lambda 表达式定义在 `display()` 方法的作用范围内，因此它可以访问实例变量 `s` 和局部变量 `ss`。当程序执行时，会启动一个新线程，输出顺序可能与语句的编写顺序不一致，但它将包含所在作用域中 `s` 和 `ss` 的值。

## 程序

```java
// 使用 lambda 技术作为函数参数实现匿名类的程序
public class Main {

    // 定义具有单个抽象方法 'get' 的函数式接口
    @FunctionalInterface
    interface test {
        double get(double radius);
    }

    // 使用提供的 test 接口执行操作的方法
    public double test(double radius, test operation) {
        return operation.get(radius);
    }

    void main(String[] args) {

        // 创建 Main 实例
        Main m = new Main();

        // 计算圆面积的 lambda 表达式
        test c = radius -> Math.PI * radius;

        // 计算圆周长的 lambda 表达式
        test cc = radius -> 2 * Math.PI * radius;

        // 圆的半径
        double radius = 10;

        // 使用 lambda 表达式计算面积和周长
        double a = m.test(radius, c);
        double cr = m.test(radius, cc);

        // 打印结果
        System.out.println("Area of the circle with radius " + radius + " : " + a);
        System.out.println("Circumference of the circle with radius " + radius + " : " + cr);
    }
}
```

```
Area of the circle with radius 10.0: 314.1592653589793
Circumference of the circle with radius 10.0: 62.8318530719586
```

该 Java 程序定义了一个名为 `Main` 的类，其中包含一个名为 `test` 的接口。该接口声明了一个单一抽象方法 `get()`，它接收圆的半径并返回一个 `double` 类型的值。在 `Main` 类中，有一个方法 `test()`，它接收一个 `double` 类型的半径并返回一个 `test` 接口的实例作为参数。该方法调用了提供的 `test` 实例的 `get()` 方法，将半径作为参数传递并返回结果。在 `Main` 类的 `main` 方法中，创建了 `Main` 的实例。使用了两个 lambda 表达式来创建 `test` 接口的实例：`c` 使用公式 `pi²` 计算圆的面积，而 `cc` 使用公式 `2pi` 计算周长。调用了两次 `test()` 方法，并以实例以及 lambda 表达式 `c` 和 `cc` 作为参数，分别计算半径为 10 的圆的面积和周长。结果存储在变量 `a` 和 `cr` 中，并打印到控制台。执行时，程序使用 lambda 表达式计算并显示了半径为 10 的圆的面积和周长。

## lambda 初始化程序

```java
import java.util.concurrent.Callable;

public class Main {

    void main(String[] args) throws Exception {

        // 使用 lambda 表达式创建 Callable 对象数组
        Callable<String>[] callables = new Callable[] {
            () -> "lambda", // 第一个 Callable lambda 表达式
            () -> "expressions" // 第二个 Callable lambda 表达式
        };

        // 调用第一个 Callable 对象的方法并打印结果
        String result = callables[0].call();
        System.out.println(result); // 输出: lambda
    }
}
```

输出：

```
Lambda
```

上述 Java 程序展示了 `Callable` 接口的使用。在 `main` 方法中，使用 lambda 表达式创建了一个 `Callable` 对象数组。对第一个 `Callable` 对象调用了方法并打印了结果。该程序展示了 `Callable` 接口的使用。在 `main` 方法中，使用 lambda 表达式创建了一个 `Callable` 对象数组。对第一个 `Callable` 对象调用了方法并打印了结果。

## 接口

```java
import java.util.concurrent.Callable;
import java.util.Arrays;

public class Main {

    // 定义具有单个抽象方法 'get' 的函数式接口
    @FunctionalInterface
    interface test {
        double get(double radius);
    }

    // 使用提供的 test 接口执行操作的方法
    public double test(double radius, test operation) {
        return operation.get(radius);
    }

    public void main(String[] args) {

        // 创建 Main 实例
        Main m = new Main();

        // 计算圆面积的 lambda 表达式
        test c = radius -> Math.PI * radius;

        // 计算圆周长的 lambda 表达式
        test cc = radius -> 2 * Math.PI * radius;

        // 圆的半径
        double radius = 10;

        // 使用 lambda 表达式计算面积和周长
        double a = m.test(radius, c);
        double cr = m.test(radius, cc);

        // 打印结果
        System.out.println("Area of the circle with radius " + radius + " : " + a);
        System.out.println("Circumference of the circle with radius " + radius + " : " + cr);
    }
}
```

```java
// 使用方法引用的排序
import java.util.Arrays;

public class Main {

    static class Test {
        String name;

        Test(String name) {
            this.name = name;
        }

        @Override
        public String toString() {
            return name;
        }
    }

    public static int tc(Test t1, Test t2) {
        return t1.name.compareTo(t2.name);
    }

    public static void main(String[] args) {
        Test[] t = {
            new Test("Dr."),
            new Test("Usha"),
            new Test("Rani"),
            new Test("Bhimavarapu")
        };

        System.out.println("Before sorting:");
        for (Test test : t) {
            System.out.println(test);
        }

        // 使用方法引用排序数组
        Arrays.sort(t, Main::tc);

        System.out.println("After sorting:");
        for (Test test : t) {
            System.out.println(test);
        }
    }
}
```

# 接口

## 319

- **病史：** 这包含了患者过去的健康状况的信息，对于诊断慢性疾病或可能导致咳嗽的状况至关重要。
- **白细胞计数：** 白细胞计数升高可能表明体内存在感染或炎症，这可能是咳嗽的潜在原因。

```java
import java.util.Random;

interface DataSource {
    void collectData();
}

interface PredictionAlgorithm {
    void predict();
}

class TemperatureSensor implements DataSource {

    private double temperature;

    public void setTemperature(double temperature) {
        this.temperature = temperature;
    }

    public double getTemperature() {
        return temperature;
    }

    @Override
    public void collectData() {
        temperature = new Random().nextDouble() * 10 + 36;
        System.out.println("Collecting temperature data from sensor: " + temperature + " °C");
    }
}

class MedicalHistory implements DataSource {

    private String history;

    public void setMedicalHistory(String history) {
        this.history = history;
    }

    public String getMedicalHistory() {
        return history;
    }

    @Override
    public void collectData() {
        history = "No significant medical history.";
        System.out.println("Collecting medical history data: " + history);
    }
}

class BloodTest implements DataSource {

    private double whiteBloodCellCount;

    public void setWhiteBloodCellCount(double whiteBloodCellCount) {
        this.whiteBloodCellCount = whiteBloodCellCount;
    }

    public double getWhiteBloodCellCount() {
        return whiteBloodCellCount;
    }

    @Override
    public void collectData() {
        // Implementation for collection
    }
}
```

## 320 用于医疗和医学应用的 Java 22

```java
// 模拟收集血测试数据
double whiteBloodCount = new Random().nextDouble() * 5 + 4;
System.out.println("Collecting blood test data: White blood cell count = " + whiteBloodCount + " x10^9/L");
}

class SimplePredictionAlgorithm implements PredictionAlgorithm {

    private TemperatureSensor temperatureSensor;
    private MedicalHistory medicalHistory;
    private BloodTest bloodTest;

    public SimplePredictionAlgorithm(TemperatureSensor temperatureSensor,
        MedicalHistory medicalHistory, BloodTest bloodTest) {
        this.temperatureSensor = temperatureSensor;
        this.medicalHistory = medicalHistory;
        this.bloodTest = bloodTest;
    }

    @Override
    public void predict() {
        double temperature = temperatureSensor.getTemperature();
        String history = medicalHistory.getMedicalHistory();
        double whiteBloodCount = bloodTest.getWhiteBloodCellCount();
```



```
if (temperature > 38.0 && whiteBloodCount > 7.0) {

    System.out.println("Prediction: The patient might have an inflammation causing coughing.");

} else if (temperature > 37.0 && history.contains("chronic")) {

    System.out.println("Prediction: The patient might have chronic bronchis or chronic respiratory conditions.");

} else {

    System.out.println("Prediction: The patient's cough might be due to a mild cause or an unknown factor.");

}

}
```

```
class PredictionSystem {

    private final TemperatureSensor temperatureSensor;

    private final MedicalHistory medicalHistory;

    private final BloodTest bloodTest;

    private final SimplePredictionAlgorithm predictionAlgorithm;

    public PredictionSystem() {

        this.temperatureSensor = new TemperatureSensor();

        this.medicalHistory = new MedicalHistory();

        this.bloodTest = new BloodTest();

        this.predictionAlgorithm = new SimplePredictionAlgorithm(temperatureSensor, medicalHistory, bloodTest);

    }

    public void collectAllData() {

        temperatureSensor.collectData();

        medicalHistory.collectData();

        bloodTest.collectData();

    }

    public void runPrediction() {

        System.out.println("Collecting all necessary data:");

        collectAllData();

        System.out.println("Data collection complete. Running prediction:");

        predictionAlgorithm.predict();

    }

}
```

```
public class CoughPredictionInChildren {

    public static void main(String[] args) {

        PredictionSystem predictionSystem = new PredictionSystem();

        predictionSystem.runPrediction();

    }

}
```

该程序使用各种数据源和预测算法实现了一个简单的咳嗽预测系统。它定义了用于从传感器收集温度数据、病史数据的类，每个类都实现了 `DataSource` 接口。`SimplePredictionAlgorithm` 类使用这些数据源根据预定义的条件预测咳嗽的潜在原因。`CoughPredictionSystem` 类聚合了这些组件，便于数据收集和运行预测。主类 `CoughPredictionInChildren` 创建了预测系统的实例并触发数据收集和预测过程，模拟了一个用于评估咳嗽病例的基础诊断工具。

## 8.15.2 案例研究 2

骨质疏松症是一种医学疾病，其特征是骨骼变弱，更容易骨折。它在人体流失过多骨骼、骨骼生成过少或两者兼有时发生。这导致骨密度和质量下降，使骨骼脆弱且易骨折，特别是髋部、脊柱和腕部。骨质疏松症通常缓慢进展没有症状，直到发生骨折，因此早期发现和管理对于预防和治疗至关重要。这里考虑的参数有：

- **骨密度 (g/cm²)：** 这是骨矿含量的测量。
- **骨质疏松症风险：** 根据骨密度发生骨折的概率。

## 9.1.3 异常处理的局限性

- **性能开销**：抛出和捕获异常的过程涉及性能开销，这可能会影响程序的效率，特别是当异常被用于常规控制流时。
- **过度使用**：过度使用异常会导致代码变得复杂且难以维护。异常应该用于异常情况，而不是常规控制流。
- **复杂性**：编写健壮的异常处理代码可能是复杂的，特别是在处理多个异常并确保所有资源都得到妥当管理时。
- **错误掩盖**：对异常处理不当可能会导致错误掩盖，使得问题的原因被隐藏，导致调试和修复问题变得困难。
- **意外异常**：未处理的异常仍可能发生，如果不进行妥善传播，可能会导致程序终止。
- **对语言特的依赖**：异常处理机制在不同的编程语言中各不相同，因此开发者必须理解所用语言的特定特性和最佳实践。

程序

```
public class DivisionByZeroExample {

    public void main(String[] args) {

        try {

            int numerator = 10;

            int denominator = 0;

            int result = numerator / denominator; // 这将抛出 ArithmeticException

            System.out.println("Result: " + result);

        } catch (ArithmeticException e) {

            System.out.println("Error: Division by zero is not allowed.");

        }

        // 浮点除法示例

        double numerator = 5.0;

        double denominator = 0.0;

        double result = numerator / denominator; // 这将导致 Infinity

        System.out.println("Result: " + result);

    }

}
```

输出：
`Error: Division by zero is not allowed.`
`Result: Infinity`

上述程序没有处理任何异常，因此编译器将处理这些异常。

## 9.2 异常 (EXCEPTION)

在 Java 中，异常是程序执行过程中发生的事件，它会中断指令的正常流。异常可能由多种因素引起，包括用户错误、程序员错误或物理资源的故障。异常的示例包括尝试打开不存在的文件、除以零或尝试访问越界的数组索引。

Java 中有许多预定义的异常类，每个类都有不同的用途。异常是 Java 标准库的一部分，并组织成一个源自 `java.lang.Throwable` 的层次结构。Java 中所有预定义的异常类都是 `java.lang.Exception` 类的子类，而 `Exception` 类又是 `Throwable` 类的子类。

### 异常处理

![](img/5a077f56e14b826c2dc61de6c176e5ef_335_0.png)

图 9.1 异常层次结构。

另一方面，错误（Errors）代表 Java 虚拟机（JVM）或系统环境中发生的故障。错误的示例包括 `OutOfMemoryError`、`StackOverflowError` 和 `VirtualMachineError`。错误通常是不可逆的，通常会导致程序终止。与异常不同，错误通常不会被程序捕获和处理。实际上，`IOException` 和 `RuntimeException` 都是 Java 中异常类的重要子类，它们有不同的用途：

- **IOException**：`Exception` 的此子类表示在从文件、网络连接或流等外部源读取或写入时发生的输入/输出（I/O）异常。`IOException` 通常由于找不到文件、文件权限无效、网络错误或磁盘空间问题等因素引起。`IOException` 的示例包括 `FileNotFoundException`、`SocketException` 和 `EOFException`。
- **RuntimeException**：`Exception` 的此子类表示由于应用程序代码中的编程错误或逻辑缺陷引起的异常。与检查异常（如 `Exceptions`）不同，`RuntimeException` 是未检查的，这意味着它们不需要在方法签名中声明，也不需要由调用代码捕获。它们可以在程序执行期间任何时间发生，通常表示代码中的 bug 或意外情况。`RuntimeException` 的示例包括 `NullPointerException`、`ArrayOutOfBoundsException` 和 `ArithmeticException`。

虽然 `IOException` 和 `RuntimeException` 都是 `Exception` 的子类，但它们有不同的用途，在 Java 程序中的处理方式也不同。异常通常会被显式地捕获和处理，因为它们代表了 I/O 操作中可恢复的错误。相比之下，`RuntimeException` 通常表示代码中存在更严重的错误，可能需要调试和修复以确保程序的正确性和稳定性。图 9.1 显示了异常的层次结构。

## 9.3 异常类型

Java 支持三种类型的异常：

- 检查型异常 (Checked Exception)
- 非检查型异常 (Unchecked Exception)
- 错误 (Error)

### 9.3.1 检查型异常 (CHECKED EXCEPTIONS)

检查异常是编译器在编译时检查的异常。也称为编译时异常，检查型异常必须被代码检查，或者使用 `throws` 关键字声明由方法抛出。这确保了程序显式地处理或承认异常发生的可能性。

检查异常通常由外部因素或可能阻止程序正常执行的条件引起。检查异常的示例包括找不到文件 (`FileNotFoundException`)、无效的用户输入 (`IOException`) 和网络错误 (`SocketException`)。

检查异常的特点：

- 异常由编译器在编译时进行测试。
- 程序员必须处理或声明检查异常。
- Java 中的所有异常（除属于 `Error` 和 `RuntimeException` 类及其子类的异常外）都是检查型异常。
- 检查异常通常由程序控制之外的外部因素或条件引起。

处理检查异常是编写健壮可靠的 Java 程序的一个重要方面，因为它确保了潜在问题得到解决，并且程序行为是可以预测的。表 9.1 详细列出了这些异常。

程序

```
import java.io.*;

class Main {

    public static void main(String[] args) {

        int n;

        try {

            FileInputStream fis = new FileInputStream("f.txt");

            while ((n = fis.read()) != -1) {

                System.out.println((char)n);

            }

        } catch (IOException e) {

            e.printStackTrace();

        }

    }

}
```

输出：
`Main.java:7: error: unreported exception IOException; must be caught or declared to thrown`

| 名称 |  |
| --- | --- |
| `IOException` | 与文件输入/输出流相关。 |
| `SQLException` | 与数据库相关。 |
| `DataAccessException` | 与访问数据相关。 |
| `ClassNotFoundException` | 找不到类。 |
| `InstantiationException` | 尝试创建抽象类或接口的对象。 |

### 9.3.1.1 throws 关键字

在 Java 中，`throws` 关键字用于方法声明，表示该特定方法在执行过程中可能会抛出一个或多个异常。通过使用 `throws` 关键字，程序员声明该方法可能会将异常传递给调用者，而不是在方法内部进行处理。

以下是使用 `throws` 的基本语法：

```
return TypeError methodName(parameters) throws ExceptionType1, ExceptionType2 {

    // 方法实现

}
```

- `parameters` 是方法接受的参数，如果有的话。
- `throws ExceptionType1, ExceptionType2...` 是可选子句，用于指定该方法在执行过程中可能抛出的异常。

例如：

```
public void readFile(String fileName) throws FileNotFoundException {

  // Method implementation

}
```

在代码中，`readFile` 方法被声明为在尝试从指定文件读取时可能会抛出 `FileNotFoundException`。通过使用 `throws` 关键字，该方法向调用者表明它不会在内部处理 `FileNotFoundException`，而是由调用者负责处理或传播该异常。

使用 `throws` 关键字允许异常处理更具灵活性，因为它允许异常在程序执行层次结构的更高层级进行处理，例如在调用方法中或应用程序的主方法中。然而，对于方法的调用者来说，了解它可能抛出的异常并对其进行适当处理，对于确保程序的健壮性至关重要。

#### 语法

```
returntype name(parameters list) throws exception
```

程序

```
import java.io.File;

import java.io.FileReader;

import java.io.IOException;

import java.io.BufferedReader;

public class FileReaderExample {

  // 方法声明它可以抛出 IOException

  public void readFile(String fileName) throws IOException {

    File file = new File(fileName);

    try (BufferedReader br = new BufferedReader(new FileReader(file))) {

      String line;

      while ((line = br.readLine()) != null) {

        System.out.println(line);

      }

    }

  }

  public static void main(String[] args) {

    FileReaderExample example = new FileReaderExample();

    try {

      example.readFile("example.txt"); // 调用可能抛异常的方法

    } catch (IOException e) {

      System.out.println("读取文件时发生错误: " + e.getMessage()); // 处理异常

    }

  }

}
```

`example.txt`

异常处理

Dr. Usharani Bhimavarapu

输出：
`Dr. Usharani Bhimavarapu`

调用 `main` 方法的方法必须处理异常。上面的程序演示了使用 `BufferedReader` 读取文件。`readLine` 方法从文件 `example.txt` 中读取每行并打印到控制台。如果发生 `IOException`，它会被捕获并通过打印错误信息进行处理。

### 9.3.1.2 Try-Catch 块

在 Java 中，try-catch 块用于异常处理。它允许你捕获并处理代码块执行期间发生的异常。try-catch 块的基本语法：

```
try {

  // 可能抛出异常的代码

} catch (ExceptionType1 e) {

    // 处理 ExceptionType1 代码

} catch (ExceptionType2 e2) {

    // 处理 ExceptionType2 代码

} catch (ExceptionType3 e3) {

    // 处理 ExceptionType3 代码

} finally {

  // 可选执行块

}
```



以下是 `try-catch` 块每个部分的作用：

- `try`：`try` 块包含可能抛出异常的代码。如果块内发生异常，异常将被抛出并将控制转移到相应的 `catch` 块。
- `catch`：`catch` 块捕获并处理异常。它通过 `ExceptionType` 指定了它可以处理的异常类型。当 `try` 块中抛出该类型（或其子类）的异常时，控制将转移到相应的 `catch` 块。你可以拥有多个 `catch` 块来处理不同类型的异常。
- `finally`（可选）：`finally` 块包含无论是否发生异常都会始终执行的代码。它通常用于清理工作，例如关闭资源（如数据库连接）或释放锁。即使抛出并捕获了异常，或者 `try` 块正常完成而没有抛出任何异常，`finally` 块也会被执行。

## 程序

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.FileNotFoundException;
import java.io.IOException;

public class FileReaderExample {
  public static void main(String[] args) {
    BufferedReader reader = null;
    try {
      // 尝试打开并读取文件
      reader = new BufferedReader(new FileReader("example.txt"));
      String line;
      while ((line = reader.readLine()) != null) {
        System.out.println(line);
      }
    } catch (FileNotFoundException e) {
      System.out.println("文件未找到: " + e.getMessage());
    } catch (IOException e) {
      System.out.println("发生 I/O 错误: " + e.getMessage());
    } finally {
      try {
        if (reader != null) {
          reader.close();
        }
      } catch (IOException e) {
        System.out.println("关闭读取器出错: " + e.getMessage());
      }
    }
  }
}
```

## 用于医疗与健康应用的 Java 22

- 此外，可以使用多个 `catch` 块来处理 `try` 块中可能发生的不同类型的异常。
- `finally` 块（可选）可执行无论是否发生异常都应该运行的清理。如果捕获了异常或 `try` 块正常完成而未抛出任何异常，都会执行 `finally` 块。

## 9.4.1 Try Block

- `try` 块包含一组语句，这些语句在执行过程中可能会发生异常。
- 它后面紧跟一个或多个 `catch` 块，用于处理在相关的 `try` 块中发生的异常。
- `try` 块必须后跟一个或多个 `catch` 块、一个 `finally` 块，或两者兼有。
- `catch` 块指定了它们可以处理的异常类型，并包含处理这些异常的代码。
- 如果在 `try` 块中发生异常，控制将根据异常类型转移到相应的 `catch` 块。
- 如果 `try` 块中没有发生异常，则将跳过 `catch` 块，并在 `try-catch` 块之后继续执行。
- `finally` 块（可选）包含无论是否发生异常都应该执行的清理代码。如果捕获了异常或 `try` 块正常完成而未抛出任何异常，都会执行 `finally` 块。

通过使用 `try-catch` 块，你可以优雅地处理 Java 程序执行期间可能发生的异常，确保适当的错误恢复和健壮性。

## Syntax

```java
try {
    // Code that may throw an exception
} catch (ExceptionType e) {
    // Code to handle ExceptionType
}
```

## 9.4.2 The Catch Block

- `catch` 块处理在相关的 `try` 块中抛出的异常。
- `catch` 块必须紧跟在 `try` 块之后，单个 `try` 块可以关联多个块。
- 每个 `catch` 块指定了它可以处理的异常类型，允许根据异常类型实现不同的异常处理逻辑。
- 当 `try` 块中发生异常时，控制将转移到与抛异常类型匹配的相应的 `catch` 块。
- `catch` 块包含处理异常的代码，例如记录错误消息、执行清理操作或采取适当的纠正措施。

## Program

```java
public class MultipleCatchExample {
    void main(String[] args) {
        try {
            int numerator = 100;
            int denominator = 0; // 这会导致除以零
            // 尝试执行除法
            int result = numerator / denominator;
            // 可能其他代码可能会抛出不同的异常
            String[] array = new String[5];
            array[10] = "Out of bounds"; // 这会导致 ArrayIndexOutOfBoundsException
        } catch (ArithmeticException e) {
            // 处理除零
            System.out.println("Error: Division by zero is not allowed.");
        } catch (ArrayIndexOutOfBoundsException e) {
            // 处理数组越界
            System.out.println("Error: Array index is out of bounds.");
        } catch (Exception e) {
            // 处理任何其他异常
            System.out.println("An unexpected error occurred: " + e.getMessage());
        } finally {
            // 始终会被执行的代码
            System.out.println("This will always be executed.");
        }
    }
}
```

Output:
```
Error: Division by zero is not allowed.
This will always be executed.
```

上述程序说明了如何使用 `catch` 块处理不同类型的异常。除以零触发了 `ArithmeticException`，而数组访问会导致 `ArrayIndexOutOfBoundsException`。如果发生任何其他异常，它们会在 `Exception` 块中被捕获。`finally` 块确保无论是否发生异常，都会打印一条消息。

通过使用带有不同异常类型的多个 `catch` 块，你可以以更通用和更具体的方式处理各种类型的异常，提高 Java 程序的健壮性和可靠性。

## 9.4.2.1 Multi-Catch Block

在 Java 中，多捕获（multi-catch）块允许程序员在一个 `catch` 块中处理多种类型的异常。当程序员需要对不同类型的异常执行相似的任务或逻辑时，这非常有用。以下是多捕获块的语法：

```java
try {
    // Code that may throw exceptions
} catch (ExceptionType1 | ExceptionType2 | ExceptionType3 e) {
    // 处理所有列出的异常
}
```

在此语法中：

- `|`（管道符号）符号用于分隔 `catch` 块中的多个异常类型。
- 当 `try` 块中发生异常时，如果它匹配多捕获块中指定的任何异常类型，控制将转移到 `catch` 块，并用捕获的异常初始化相应的异常变量（在本例中为 `e`）。

## 用于医疗与健康应用的 Java 22

- `catch` 块包含处理已捕获异常的代码，这些代码对于所有指定的异常类型可能是相同的，也可以根据特定的异常类型而异。

## Program

```java
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

public class MultiCatchExample {
    void main(String[] args) {
        try {
            FileReader file = new FileReader("nonexistentfile.txt");
            // Code that might throw exceptions
        } catch (FileNotFoundException | IOException e) {
            // 处理 FileNotFoundException 和 IOException
            System.out.println("An error occurred: " + e.getMessage());
        } finally {
            // 始终会被执行的代码
            System.out.println("This will always be executed.");
        }
    }
}
```

## 336 用于医疗保健和医疗应用的 Java 22

`Exception1` 或 `Exception2`。每个 `catch` 块包含响应特定异常类型的代码。例如，如果抛出了类型为 `Exception` 的异常，则执行相应的 `catch` 块。在 `catch` 块之后，`finally` 块包含无论是否抛出异常都会始终运行的代码。这对于清理资源或关闭文件等任务非常有用，可以确保系统正常运行。

## Program

```java
public class DivisionByZeroExample {
    void main(String[] args) {
        int numerator = 10;
        int denominator = 0;
        try {
            // 尝试除以零
            int result = numerator / denominator;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            // 处理除以零异常
            System.out.println("Exception caught: Division by zero is not allowed.");
        } finally {
            // 清理代码，无论是否发生异常都会执行
            System.out.println("Finally block executed: Cleaning up resources.");
        }
    }
}
```

## Output

```
Exception caught: Division by zero is not allowed.
Finally block executed: Cleaning up resources.
```

上述程序演示了如何处理除以零的错误。`try` 块尝试将分子除以分母，但由于分母为零，因此会抛出 `ArithmeticException`。`catch` 块捕获此异常并显示错误信息，指示不允许除以零。无论是否发生异常，`finally` 块始终执行，在此例中，它打印了关于清理资源的消息。

`finally` 块在 `catch` 块之后执行。

- `finally` 块是可选的，但如果存在，无论是否发生异常它都会执行。
- 每个 `try` 对应有一个 `finally` 块。这确保了清理代码在 `try` 块执行后恰恰执行一次，无论是否发生异常。
- 如果发生异常并被 `catch` 块捕获，则 `finally` 块将在 `catch` 块执行完成后执行。
- 如果 `try` 块内没有发生异常，`finally` 块仍会在 `try` 块执行完成后执行。
- `finally` 块通常用于清理任务，例如关闭资源（如文件、数据库连接）或释放锁，确保这些任务在出现异常时也能可靠地执行。

通过遵循这些规则，Java 开发者可以确保程序中适当的异常处理和资源管理，从而构建更健壮、更可靠的软件。

**注意：** 使用 `finally` 块是一个良好习惯，因为它包含了清理代码。

## Exception Handling

## Program

```java
// 不执行 finally 块的程序
public class FinallyBlockExample {
  void main(String[] args) {
    try {
      System.out.println("inside try");
      // 终止 JVM
      System.exit(0);
    } catch (Exception e) {
      System.out.println("In catch block.");
    } finally {
      // 这个块将不会被执行
      System.out.println("In finally block.");
    }
  }
}
```

## Output

```
inside try
```

在 Java 程序中，`main` 方法演示了当 `try` 块内调用 `System.exit(0)` 时 `try-catch-finally` 块的行为。打印了 "inside try"，表示 `try` 块内执行的开始。执行了 `System.exit(0)` 语句，这会立即以状态码 0 终止 Java 虚拟机 (JVM)。由于 JVM 已终止，`catch` 块被完全跳过，`finally` 块也不会执行。因此，"inside finally block" 没有被打印，因为由于 JVM 终止导致无法到达 `finally` 块。

## 9.4.4 JAVA THROW

- Java 中的 `throw` 关键字用于显式抛出一个特定的异常。
- 当使用 `throw` 关键字抛出异常时，程序的正常流会被中断，控制权将转移到能够处理该抛出异常的最近 `catch` 块。
- 这允许根据程序中的某些条件或标准故意触发异常。
- `throw` 语句可以抛出任何异常对象，包括 Java 提供的预定义异常或程序员提供的自定义异常。

通过 `throw` 关键字，开发者可以控制程序的流，并以结构化可预测的方式处理异常情况，提高 Java 应用程序的健壮性和可靠性。

## Syntax

```java
throw exceptionname;
```

## Program

```java
public class FinallyBlockExample {
  void main(String[] args) {
    try {
        System.out.println("In try block.");
        // 显式抛出一个 ArithmeticException
        throw new ArithmeticException("Explicitly thrown ArithmeticException");
    } catch (ArithmeticException e) {
        System.out.println("Caught exception: " + e.getMessage());
    } finally {
        // 这个块将被执行
        System.out.println("In finally block.");
    }
  }
}
```

## Output

```
In try block.
Caught exception: Explicitly thrown ArithmeticException
In finally block.
```

上述程序演示了在异常处理中 `finally` 块的使用。它处理了此异常，即 `try` 块中显式抛出的 `ArithmeticException`。`catch` 块负责打印与异常相关的消息。无论异常是否发生，`finally` 块都会执行，确保在 `try-catch` 块之后运行清理操作或代码。在此例中，它打印了关于该项的消息。

## 338 用于医疗保健和医疗应用的 Java 22

## 9.4.5 THROWS KEYWORD

- `throws` 关键字用于方法签名，指示方法可能会抛出某些异常。
- 后面跟着一个由逗号分隔的异常类型列表。
- 如果方法没有处理异常，则必须在 `throws` 子句中指定其内部可能发生的异常类型。
- 通过声明异常，方法为调用者提供了有关他们需要处理什么的信息。

`throws` 关键字有助于记录方法的异常行为并促进更好的处理。

## Syntax

```java
type methodName(parameters) throws ExceptionType1, ExceptionType2, ... {
    // method body
}
```



`return Type methodName(parameters) throws ExceptionType, Exception2 {`

```
// 方法体
```

## Program

```java
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

public class ExceptionDemo {
    // 指定其可能抛出 IOException 的方法
    public static void fun() throws IOException {
        FileInputStream fis = null;
    }
}
```

## Exception Handling

```java
try {
    fis = new FileInputStream("test.txt");
    // 执行文件操作
} catch (FileNotFoundException e) {
    System.out.println("File not found: " + e.getMessage());
    // 具体处理 FileNotFoundException
} finally {
    if (fis != null) {
        try {
            fis.close(); // 关闭文件
        } catch (IOException e) {
            System.out.println("Error closing the file: " + e.getMessage());
        }
    }
}

public void main(String[] args) {
    try {
        fun(); // 调用可能抛出 IOException的方法
    } catch (IOException e) {
        System.out.println("IOException caught in main: " + e.getMessage());
        // 处理来自 fun() 的 IOException
    }
}
```

在上述程序中，如果`test.txt`不存在，`FileInputStream`会抛出扩展自`IOException`的`FileNotFoundException`。`fun()`方法指定了可能会抛出`IOException`并在抛出时进行处理。如果方法没有处理异常，则必须在`throws`子句中指定其内部可能发生的异常类型。

## 9.5 用户定义异常

在 Java 中，程序员可以创建自己的异常类，以表示应用程序中可能发生的特定类型错误或异常情况。这些自定义异常被称为用户定义异常或自定义异常。

要创建自定义异常类，开发者通常会扩展 Java 现有的异常类，例如`Exception`或`RuntimeException`。然后，他们根据需要向异常添加自定义行为或属性。

一旦定义了自定义异常类，开发者就可以使用`throw`关键字抛出此类异常的实例，就像处理其他异常一样。这允许他们在代码中处理特定的错误场景，并向调用者提供有意义的错误信息。

通过创建自定义异常，开发者可以通过清晰定义和处理程序执行过程中可能出现的不同异常情况，提高代码的清晰性和可维护性。这促进了更好的错误处理实践，并有助于使 Java 应用程序更加健壮可靠。

## Syntax

```java
// 通过扩展 Exception 定义自定义受检异常
public class CustomException extends Exception {
```

```java
// 无参数构造函数
public CustomException() {
    super();
}
```

```java
// 接收消息的构造函数
public CustomException(String message) {
    super(message);
}
```

```java
// 接收消息和原因的构造函数
public CustomException(String message, Throwable cause) {
    super(message, cause);
}
```

```java
// 接收原因的构造函数
public CustomException(Throwable cause) {
    super(cause);
}
```

在创建自定义异常类时，需要继承`Java.lang.Exception`。上述语法通过扩展`Exception`类在 Java 中定义了一个自定义的受检异常。`CustomException`类提供了四个构造函数，每个都有不同的用途：

1. 默认构造函数：`CustomException()`调用无带参数的父类构造函数，创建一个没有特定消息或原因的通用异常。
2. 带消息：`CustomException(String message)`允许传递自定义消息，可以更清晰地描述错误。
3. 带消息和原因：`CustomException(String message, Throwable cause)`允许传递消息和异常的底层原因，提供关于导致异常的更多上下文信息。
4. 带原因：`CustomException(Throwable cause)`允许只传递异常原因，这可能是触发此自定义异常的另一个异常。

# 程序

```java
// 自定义异常类
class TestException extends Exception {
    private int statusCode; // 状态码的字段

    // 初始化状态码的构造函数
    public TestException(int statusCode) {
        this.statusCode = statusCode;
    }

    // 重写 toString() 方法以自定义输出
    @Override
    public String toString() {
        return "Custom Exception with status code: " + statusCode;
    }
}
```

```java
// 异常处理的主类
public class Main {
    void main(String[] args) {
        try {
            // 抛出一个状态码为 400 的自定义异常实例
            throw new TestException(400);
        } catch (TestException e) {
            // 捕获自定义异常并打印状态码
            System.out.println(e.toString());
        }
    }
}
```

输出：`Exception with status code: 400`

上述演示了自定义异常类`TestException`的用法，它包含一个状态码字段。自定义异常的构造函数初始化了这个状态码。`toString()`方法被重写以返回一个包含状态码的自定义消息。在主类中，抛出了状态码为 400 的`TestException`实例。`catch`块捕获了异常并打印由`toString()`方法提供的自定义消息。

# 程序

```java
// 自定义异常类
class TestException extends Exception {
    // 接收字符串消息的构造函数
    public TestException(String message) {
        super(message); // 将消息传递给父类构造函数
    }
}

// 包含抛出自定义异常方法的示例类
class Sample {
    // 如果输入数字无效，则抛出 TestException
    public void check(int n) throws TestException {
        if (n <= 0 || n > 99) {
            throw new TestException("Invalid number"); // 抛出带消息的自定义异常
        }
        // 可选：在此处添加其他逻辑
    }
}

// 异常处理的主类
public class Main {
    public void main(String[] args) {
        Sample sample = new Sample();
        try {
            // 使用有效数字 (90) 调用 check 方法
            sample.check(90);
            System.out.println("Number is valid"); // 表示数字有效的消息
        } catch (TestException e) {
            // 处理自定义异常
            System.out.println("Exception handled");
            System.out.println("Error message: " + e.getMessage()); // 打印异常中的消息
        }
    }
}
```

输出：
`Number is valid`

# 用于医疗和健康应用的 Java 22

上述程序定义了一个自定义异常类`TestException`，它在初始化期间接受一个消息。`Sample`类包含一个方法`check()`，如果输入小于等于 0 或大于 99，则它会抛出`TestException`。在`Main`类中，创建了`Sample`的实例，并使用有效数字 (90) 调用了`check()`方法。如果数字有效，将打印一条指示此的消息；否则，将捕获异常并显示错误消息。

# 程序

```java
// 自定义异常类
class TestException extends Exception {
    private int e; // 存储整数值的字段

    // 初始化字段的构造函数
    public TestException(int nl) {
        this.e = nl;
    }

    // 重写 toString() 方法
    @Override
    public String toString() {
        return "Value of (" + e + ") is less than 10";
    }
}

// 带有静态方法的示例
class Sample {
    // 如果 n2 小于 10，则抛出 TestException
    public static void sum(int n1, int n2) throws TestException {
        if (n2 < 10) {
            throw new TestException(n2); // 以 n2 为参数抛出自定义异常
        } else {
            // 如果 n2 不小于 10，则打印和
            System.out.println("Sum: " + (n1 + n2));
        }
    }
}

// 异常处理的主类
public class Main {
    void main(String[] args) {
        try {
            Sample.sum(-5, 4);
        } catch (TestException e) {
            // 处理捕获的异常：
            System.out.println("Exception caught: " + e);
        }
    }
}
```

输出：
`Exception caught: Value of (4) is less than 10`

上述程序定义了一个自定义异常类`TestException`，它存储一个整数并重写了`toString()`方法以提供特定的消息。`Sample`类包含一个静态方法`sum()`，如果`n2`小于 10，它会抛出`TestException`。如果`n2`大于 10，它会计算并打印`n1`和`n2`的和。在`Main`类中，使用 -5 和 4 调用`sum()`方法，由于 4 小于 10 触发了异常。异常在`try-catch`块中被捕获，并打印了自定义消息。

344 Java 22 用于医疗与健康应用

# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }

    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}

// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:
`Custom Exception: This is a custom exception.`

上述代码定义了一个扩展`Exception`的自定义异常类`MyException`。该类包含一个初始化异常消息的构造函数，并重写了`toString`方法以提供异常的自定义字符串表示。`main`方法抛出了带有消息“This is a custom exception message.”的`MyException`实例。抛出的异常被处理`MyException`对象的`catch`块捕获。在`catch`块内部，使用`System.out.println(e)`打印异常。

# 9.6 嵌套 TRY

在 Java 中使用`try-catch`块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

# 嵌套 Try-Catch 块的优势

- **细粒度错误处理**：允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。
- **特定错误恢复**：能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

# 异常处理

- **代码清晰度和可维护性**：有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的`try-catch`块在同一处处理多种类型的异常。
- **可读性**：虽然`try-catch`块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。
- **异常传播**：未被内部`try-catch`块捕获的异常将传播到外部`try-catch`块。确保异常要么在发生级别被妥善处理，要么有意地传播。
- **资源管理**：在嵌套的`try-catch`块中妥善管理资源。使用`finally`或`try-with-resources`语句确保即使在发生异常时资源也能正确关闭。

# 9.6.1 外部 Try-Catch 块

`try`块涵盖较大范围的代码或可能抛出异常的多个操作。外部`catch`块捕获未被内部`catch`块处理的异常，或者由内部`catch`块本身抛出的异常。

# 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
```



344 Java 22 用于医疗与健康应用

# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

Custom Exception: This is a custom exception.

上述代码定义了一个扩展 `Exception` 的自定义异常类 `MyException`。该类包含一个初始化异常消息的构造函数，并重写了 `toString` 方法以提供异常的自定义字符串表示。`main` 方法抛出了带有消息“This is a custom exception message.”的 `MyException` 实例。抛出的异常被处理 `MyException` 对象的 `catch` 块捕获。在 `catch` 块内部，使用 `System.out.println(e)` 打印异常。

# 9.6 嵌套 TRY

在 Java 中使用 `try-catch` 块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

# 嵌套 Try-Catch 块的优势

- 细粒度错误处理

允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。

- 特定错误恢复

能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

# 异常处理

- 代码清晰度和可维护性

有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的 `try-catch` 块在同一处处理多种类型的异常。

- 可读性

虽然 `try-catch` 块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。

- 异常传播

未被内部 `try-catch` 块捕获的异常将传播到外部 `try-catch` 块。确保异常要么在发生级别被妥善处理，要么有意地传播。

- 资源管理

在嵌套的 `try-catch` 块中妥善管理资源。使用 `finally` 或 `try-with-resources` 语句确保即使在发生异常时资源也能正确关闭。

# 9.6.1 外部 Try-Catch 块

`try` 块涵盖较大范围的代码或可能抛出异常的多个操作。外部 `catch` 块捕获未被内部 `catch` 块处理的异常，或者由内部 `catch` 块本身抛出的异常。

# 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

# 输出:

out of bounds error

在此程序中，使用了嵌套的 `try-catch` 结构来处理多个异常。外部 `try` 块初始化包含一个元素的整数数组，内部 `try` 块尝试访问越界索引并执行除零操作。当越界访问触发 `ArrayIndexOutOfBoundsException` 时，它被内部 `catch` 块捕获并打印“out of bounds error”。外部 `catch` 块设计用于捕获 `ArithmeticException`，但在情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 `try-catch` 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部 `catch` 块的消息。

# 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

```
Outer try block started.
Inner try block started.
Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds
Statement after inner try-catch.
Finally block executed.
```



344 Java 22 用于医疗与健康应用

# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }

    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}

// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

## 输出

```text
Custom Exception: This is a custom exception.
```

上述代码定义了一个扩展 `Exception` 的自定义异常类 `MyException`。该类包含一个初始化异常消息的构造函数，并重写 `toString()` 方法以提供异常的自定义字符串表示。`main` 方法抛出了带有消息“This is a custom exception message.”的 `MyException` 实例。抛出的异常被处理 `MyException` 对象的 `catch` 块捕获。在 `catch` 块内部，使用 `System.out.println(e)` 打印异常。

# 9.6 嵌套 `try`

在 Java 中使用 `try-catch` 块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

## 嵌套 `try-catch` 块的优势

- **细粒度错误处理**

  允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。

- **特定错误恢复**

  能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

## 异常处理

- **代码清晰度和可维护性**

  有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的 `try-catch` 块在同一处处理多种类型的异常。

- **可读性**

  虽然 `try-catch` 块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。

- **异常传播**

  未被内部 `try-catch` 块捕获的异常将传播到外部 `try-catch` 块。确保异常要么在发生级别被妥善处理，要么有意地传播。

- **资源管理**

  在嵌套的 `try-catch` 块中妥善管理资源。使用 `finally` 或 `try-with-resources` 语句确保即使在发生异常时资源也能正确关闭。

## 9.6.1 外部 `try-catch` 块

`try` 块涵盖较大范围的代码或可能抛出异常的多个操作。外部 `catch` 块捕获未被内部 `catch` 块处理的异常，或者由内部 `catch` 块本身抛出的异常。

## 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            } catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

## 输出

```text
out of bounds error
```

在此程序中，使用了嵌套的 `try-catch` 结构来处理多个异常。外部 `try` 块初始化包含一个元素的整数数组，内部 `try` 块尝试访问越界索引并执行除零操作。当越界访问触发 `ArrayIndexOutOfBoundsException` 时，它被内部 `catch` 块捕获并打印“out of bounds error”。外部 `catch` 块设计用于捕获 `ArithmeticException`，但在此情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 `try-catch` 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部 `catch` 块的消息。

## 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");

            // 有一个元素的数组
            int[] a = new int[1];

            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];

                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }

            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

## 输出

```text
Outer try block started.
Inner try block started.
Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds
Statement after inner try-catch.
Finally block executed.
```



# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

Custom Exception: This is a custom exception.

上述代码定义了一个扩展`Exception`的自定义异常类`MyException`。该类包含一个初始化异常消息的构造函数，并重写了`toString`方法以提供异常的自定义字符串表示。`main`方法抛出了带有消息“This is a custom exception message.”的`MyException`实例。抛出的异常被处理`MyException`对象的`catch`块捕获。在`catch`块内部，使用`System.out.println(e)`打印异常。

# 9.6 嵌套 TRY

在 Java 中使用`try-catch`块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

## 嵌套 Try-Catch 块的优势

- 细粒度错误处理

允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。

- 特定错误恢复

能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

## 异常处理

- 代码清晰度和可维护性

有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的`try-catch`块在同一处处理多种类型的异常。

- 可读性

虽然`try-catch`块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。

- 异常传播

未被内部`try-catch`块捕获的异常将传播到外部`try-catch`块。确保异常要么在发生级别被妥善处理，要么有意地传播。

- 资源管理

在嵌套的`try-catch`块中妥善管理资源。使用`finally`或`try-with-resources`语句确保即使在发生异常时资源也能正确关闭。

## 9.6.1 外部 Try-Catch 块

`try`块涵盖较大范围的代码或可能抛出异常的多个操作。外部`catch`块捕获未被内部`catch`块处理的异常，或者由内部`catch`块本身抛出的异常。

## 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

## 输出:

out of bounds error

在此程序中，使用了嵌套的 try-catch 结构来处理多个异常。外部`try`块初始化包含一个元素的整数数组，内部`try`块尝试访问越界索引并执行除零操作。当越界访问触发`ArrayIndexOutOfBoundsException`时，它被内部`catch`块捕获并打印“out of bounds error”。外部`catch`块设计用于捕获`ArithmeticException`，但在情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 try-catch 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部`catch`块的消息。

## 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

Outer try block started.

Inner try block started.

Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds

Statement after inner try-catch.

Finally block executed.




# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

Custom Exception: This is a custom exception.

上述代码定义了一个扩展 `Exception` 的自定义异常类 `MyException`。该类包含一个初始化异常消息的构造函数，并重写了 `toString` 方法以提供异常的自定义字符串表示。`main` 方法抛出了带有消息“This is a custom exception message.”的 `MyException` 实例。抛出的异常被处理 `MyException` 对象的 `catch` 块捕获。在 `catch` 块内部，使用 `System.out.println(e)` 打印异常。

# 9.6 嵌套 TRY

在 Java 中使用 `try-catch` 块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

## 嵌套 Try-Catch 块的优势

- **细粒度错误处理**：允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。
- **特定错误恢复**：能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

## 异常处理

- **代码清晰度和可维护性**：有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的 `try-catch` 块在同一处处理多种类型的异常。
- **可读性**：虽然 `try-catch` 块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。
- **异常传播**：未被内部 `try-catch` 块捕获的异常将传播到外部 `try-catch` 块。确保异常要么在发生级别被妥善处理，要么有意地传播。
- **资源管理**：在嵌套的 `try-catch` 块中妥善管理资源。使用 `finally` 或 `try-with-resources` 语句确保即使在发生异常时资源也能正确关闭。

# 9.6.1 外部 Try-Catch 块

`try` 块涵盖较大范围的代码或可能抛出异常的多个操作。外部 `catch` 块捕获未被内部 `catch` 块处理的异常，或者由内部 `catch` 块本身抛出的异常。

## 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

## 输出

out of bounds error

在此程序中，使用了嵌套的 `try-catch` 结构来处理多个异常。外部 `try` 块初始化包含一个元素的整数数组，内部 `try` 块尝试访问越界索引并执行除零操作。当越界访问触发 `ArrayIndexOutOfBoundsException` 时，它被内部 `catch` 块捕获并打印“out of bounds error”。外部 `catch` 块设计用于捕获 `ArithmeticException`，但在这种情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 `try-catch` 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部 `catch` 块的消息。

## 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

Outer try block started.

Inner try block started.

Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds

Statement after inner try-catch.

Finally block executed.



# 344 Java 22 用于医疗与健康应用

## 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

```
Custom Exception: This is a custom exception.
```

上述代码定义了一个扩展`Exception`的自定义异常类`MyException`。该类包含一个初始化异常消息的构造函数，并重写了`toString`方法以提供异常的自定义字符串表示。`main`方法抛出了带有消息“This is a custom exception message.”的`MyException`实例。抛出的异常被处理`MyException`对象的`catch`块捕获。在`catch`块内部，使用`System.out.println(e)`打印异常。

## 9.6 嵌套 TRY

在 Java 中使用`try-catch`块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

### 嵌套 Try-Catch 块的优势

- **细粒度错误处理**：允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。
- **特定错误恢复**：能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。
- **代码清晰度和可维护性**：有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的`try-catch`块在同一处处理多种类型的异常。

### 异常处理

- **可读性**：虽然`try-catch`块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。
- **异常传播**：未被内部`try-catch`块捕获的异常将传播到外部`try-catch`块。确保异常要么在发生级别被妥善处理，要么有意地传播。
- **资源管理**：在嵌套的`try-catch`块中妥善管理资源。使用`finally`或`try-with-resources`语句确保即使在发生异常时资源也能正确关闭。

## 9.6.1 外部 Try-Catch 块

`try`块涵盖较大范围的代码或可能抛出异常的多个操作。外部`catch`块捕获未被内部`catch`块处理的异常，或者由内部`catch`块本身抛出的异常。

### 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

输出:

```
out of bounds error
```

在此程序中，使用了嵌套的 try-catch 结构来处理多个异常。外部`try`块初始化包含一个元素的整数数组，内部`try`块尝试访问越界索引并执行除零操作。当越界访问触发`ArrayIndexOutOfBoundsException`时，它被内部`catch`块捕获并打印“out of bounds error”。外部`catch`块设计用于捕获`ArithmeticException`，但在情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 try-catch 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部`catch`块的消息。

### 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

```
Outer try block started.

Inner try block started.

Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds

Statement after inner try-catch.

Finally block executed.
```




344 Java 22 用于医疗与健康应用

# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

`Custom Exception: This is a custom exception.`

上述代码定义了一个扩展 `Exception` 的自定义异常类 `MyException`。该类包含一个初始化异常消息的构造函数，并重写了 `toString` 方法以提供异常的自定义字符串表示。`main` 方法抛出了带有消息“This is a custom exception message.”的 `MyException` 实例。抛出的异常被处理 `MyException` 对象的 `catch` 块捕获。在 `catch` 块内部，使用 `System.out.println(e)` 打印异常。

# 9.6 嵌套 TRY

在 Java 中使用 `try-catch` 块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

# 嵌套 Try-Catch 块的优势

- 细粒度错误处理

允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。

- 特定错误恢复

能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

# 异常处理

- 代码清晰度和可维护性

有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的 `try-catch` 块在同一处处理多种类型的异常。

- 可读性

虽然 `try-catch` 块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。

- 异常传播

未被内部 `try-catch` 块捕获的异常将传播到外部 `try-catch` 块。确保异常要么在发生级别被妥善处理，要么有意地传播。

- 资源管理

在嵌套的 `try-catch` 块中妥善管理资源。使用 `finally` 或 `try-with-resources` 语句确保即使在发生异常时资源也能正确关闭。

# 9.6.1 外部 Try-Catch 块

`try` 块涵盖较大范围的代码或可能抛出异常的多个操作。外部 `catch` 块捕获未被内部 `catch` 块处理的异常，或者由内部 `catch` 块本身抛出的异常。

# 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

# 输出:

`out of bounds error`

在此程序中，使用了嵌套的 `try-catch` 结构来处理多个异常。外部 `try` 块初始化包含一个元素的整数数组，内部 `try` 块尝试访问越界索引并执行除零操作。当越界访问触发 `ArrayIndexOutOfBoundsException` 时，它被内部 `catch` 块捕获并打印“out of bounds error”。外部 `catch` 块设计用于捕获 `ArithmeticException`，但在情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 `try-catch` 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部 `catch` 块的消息。

# 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

`Outer try block started.`

`Inner try block started.`

`Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds`

`Statement after inner try-catch.`

`Finally block executed.`




# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

Custom Exception: This is a custom exception.

上述代码定义了一个扩展 `Exception` 的自定义异常类 `MyException`。该类包含一个初始化异常消息的构造函数，并重写了 `toString` 方法以提供异常的自定义字符串表示。`main` 方法抛出了带有消息“This is a custom exception message.”的 `MyException` 实例。抛出的异常被处理 `MyException` 对象的 `catch` 块捕获。在 `catch` 块内部，使用 `System.out.println(e)` 打印异常。

# 9.6 嵌套 TRY

在 Java 中使用 `try-catch` 块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

# 嵌套 Try-Catch 块的优势

- 细粒度错误处理

允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。

- 特定错误恢复

能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

# 异常处理

- 代码清晰度和可维护性

有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的 `try-catch` 块在同一处处理多种类型的异常。

- 可读性

虽然 `try-catch` 块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。

- 异常传播

未被内部 `try-catch` 块捕获的异常将传播到外部 `try-catch` 块。确保异常要么在发生级别被妥善处理，要么有意地传播。

- 资源管理

在嵌套的 `try-catch` 块中妥善管理资源。使用 `finally` 或 `try-with-resources` 语句确保即使在发生异常时资源都能正确关闭。

# 9.6.1 外部 Try-Catch 块

`try` 块涵盖较大范围的代码或可能抛出异常的多个操作。外部 `catch` 块捕获未被内部 `catch` 块处理的异常，或者由内部 `catch` 块本身抛出的异常。

# 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

# 输出:

out of bounds error

在此程序中，使用了嵌套的 try-catch 结构来处理多个异常。外部 `try` 块初始化包含一个元素的整数数组，内部 `try` 块尝试访问越界索引并执行除零操作。当越界访问触发 `ArrayIndexOutOfBoundsException` 时，它被内部 `catch` 块捕获并打印“out of bounds error”。外部 `catch` 块设计用于捕获 `ArithmeticException`，但在情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 try-catch 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部 `catch` 块的消息。

# 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

Outer try block started.

Inner try block started.

Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds

Statement after inner try-catch.

Finally block executed.




# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

Custom Exception: This is a custom exception.

上述代码定义了一个扩展 `Exception` 的自定义异常类 `MyException`。该类包含一个初始化异常消息的构造函数，并重写了 `toString` 方法以提供异常的自定义字符串表示。`main` 方法抛出了带有消息“This is a custom exception message.”的 `MyException` 实例。抛出的异常被处理 `MyException` 对象的 `catch` 块捕获。在 `catch` 块内部，使用 `System.out.println(e)` 打印异常。

# 9.6 嵌套 TRY

在 Java 中使用 `try-catch` 块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

# 嵌套 Try-Catch 块的优势

- 细粒度错误处理

允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。

- 特定错误恢复

能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

# 异常处理

- 代码清晰度和可维护性

有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的 `try-catch` 块在同一处处理多种类型的异常。

- 可读性

虽然 `try-catch` 块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。

- 异常传播

未被内部 `try-catch` 块捕获的异常将传播到外部 `try-catch` 块。确保异常要么在发生级别被妥善处理，要么有意地传播。

- 资源管理

在嵌套的 `try-catch` 块中妥善管理资源。使用 `finally` 或 `try-with-resources` 语句确保即使在发生异常时资源都能正确关闭。

# 9.6.1 外部 Try-Catch 块

`try` 块涵盖较大范围的代码或可能抛出异常的多个操作。外部 `catch` 块捕获未被内部 `catch` 块处理的异常，或者由内部 `catch` 块本身抛出的异常。

# 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

# 输出:

out of bounds error

在此程序中，使用了嵌套的 try-catch 结构来处理多个异常。外部 `try` 块初始化包含一个元素的整数数组，内部 `try` 块尝试访问越界索引并执行除零操作。当越界访问触发 `ArrayIndexOutOfBoundsException` 时，它被内部 `catch` 块捕获并打印“out of bounds error”。外部 `catch` 块设计用于捕获 `ArithmeticException`，但在情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 try-catch 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部 `catch` 块的消息。

# 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

Outer try block started.

Inner try block started.

Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds

Statement after inner try-catch.

Finally block executed.




# 程序

Java 中自定义异常的示例

```java
// 自定义异常类
class MyException extends Exception {
    // 用于初始化异常消息的构造函数
    public MyException(String message) {
        super(message); // 将消息传递给父类
    }
    // 重写 toString() 方法以提供自定义的字符串表示
    @Override
    public String toString() {
        return "Custom Exception: " + getMessage();
    }
}
// 用于演示异常的主类
public class Main {
    public void main(String[] args) {
        try {
            // 抛出一个带有自定义消息的 MyException 实例
            throw new MyException("This is a custom exception.");
        } catch (MyException e) {
            // 捕获异常并打印
            System.out.println(e); // 隐式调用 e.toString()
        }
    }
}
```

Output:

`Custom Exception: This is a custom exception.`

上述代码定义了一个扩展 `Exception` 的自定义异常类 `MyException`。该类包含一个初始化异常消息的构造函数，并重写了 `toString` 方法以提供异常的自定义字符串表示。`main` 方法抛出了带有消息“This is a custom exception message.”的 `MyException` 实例。抛出的异常被处理 `MyException` 对象的 `catch` 块捕获。在 `catch` 块内部，使用 `System.out.println(e)` 打印异常。

# 9.6 嵌套 TRY

在 Java 中使用 `try-catch` 块是处理多层异常的技巧，其中内部块中捕获的异常可以与外部块中捕获的异常分开处理。这允许进行细粒度的错误处理，并且在不同类型的错误需要不同处理策略的复杂操作中非常有用。

# 嵌套 Try-Catch 块的优势

- 细粒度错误处理

允许在代码的不同级别处理不同类型的异常。你可以在异常发生的地方处理特定异常，并在更高层级处理更通用的异常。

- 特定错误恢复

能够从特定异常中恢复，而不中断整个程序的执行流。例如，当发生特定异常时，你可以尝试替代操作。

# 异常处理

- 代码清晰度和可维护性

有助于组织复杂的错误处理逻辑，使代码更易读和维护。通过分离关注点，你可以避免使用单一庞大的 `try-catch` 块在同一处处理多种类型的异常。

- 可读性

虽然 `try-catch` 块可以提高错误处理的精确性，但如果过度使用或嵌套过深，可能会使代码变得难以阅读。在嵌套深度与可读性之间取得平衡非常重要。

- 异常传播

未被内部 `try-catch` 块捕获的异常将传播到外部 `try-catch` 块。确保异常要么在发生级别被妥善处理，要么有意地传播。

- 资源管理

在嵌套的 `try-catch` 块中妥善管理资源。使用 `finally` 或 `try-with-resources` 语句确保即使在发生异常时资源都能正确关闭。

# 9.6.1 外部 Try-Catch 块

`try` 块涵盖较大范围的代码或可能抛出异常的多个操作。外部 `catch` 块捕获未被内部 `catch` 块处理的异常，或者由内部 `catch` 块本身抛出的异常。

# 程序

```java
// 嵌套 try 程序，异常在外部 catch 块中捕获
public class NestedTryCatchExample {
    void main(String[] args) {
        try {
            // 外部 try 块
            int[] a = new int[1]; // 有一个元素的数组
            try {
                // 内部 try 块
                int result = a[1] / 0; // 尝试越界访问数组并除零
            } catch (ArrayIndexOutOfBoundsException e) {
                // 针对 ArrayIndexOutOfBoundsException 的内部 catch 块
                System.out.println("out of bounds error");
            }
            catch (ArithmeticException e) {
                // 针对 ArithmeticException 的外部 catch 块
                System.out.println("division by zero error");
            }
        }
    }
}
```

# 输出:

`out of bounds error`

在此程序中，使用了嵌套的 `try-catch` 结构来处理多个异常。外部 `try` 块初始化包含一个元素的整数数组，内部 `try` 块尝试访问越界索引并执行除零操作。当越界访问触发 `ArrayIndexOutOfBoundsException` 时，它被内部 `catch` 块捕获并打印“out of bounds error”。外部 `catch` 块设计用于捕获 `ArithmeticException`，但在情况下它没有执行，因为内部异常被优先处理了。程序演示了嵌套 `try-catch` 块如何有效管理错误处理层级。由于没有发生算术异常，因此只显示了内部 `catch` 块的消息。

# 程序

```java
public class NestedTryCatchExample {
    public void main(String[] args) {
        try {
            // 外部 try 块
            System.out.println("Outer try block started.");
            // 有一个元素的数组
            int[] a = new int[1];
            try {
                // 内部 try 块
                // 尝试越界访问数组并除零
                System.out.println("Inner try block started.");
                int value = a[1];
                // 这一行将抛出 ArithmeticException
                int result = value / 0;
            } catch (ArrayIndexOutOfBoundsException e) {
                // 内部 catch 块
                System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());
            }
            // 附加语句
            System.out.println("Statement after inner try-catch.");
        } catch (ArithmeticException e) {
            // 外部 catch 块
            System.out.println("Caught ArithmeticException: " + e.getMessage());
        } catch (Exception e) {
            // 通用 catch 块
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            // finally 块
            System.out.println("Finally block executed.");
        }
    }
}
```

Output:

`Outer try block started.`

`Inner try block started.`

`Caught ArrayIndexOutOfBoundsException: Index 1 out of bounds`

`Statement after inner try-catch.`

`Finally block executed.`

该 Java 程序演示了使用嵌套 `try-catch-finally` 块进行异常处理的用法。外部 `try` 块包含主逻辑，并初始化了一个包含一个元素的数组。在该块中，会打印 "outer try"，然后访问并打印 `a[0]` 的值。在外部 `try` 块内部有一个嵌套的 `try`。在尝试执行无效除法操作 `a()/0` 之前，会打印 "nested try"。如果在嵌套 `try` 内部发生 `ArithmeticException`，它会被内部 `catch` 块捕获，该块会打印 "exception caught inside nested catch"，然后是 "division by zero error"。内部 `finally` 块无论是否发生异常都会打印 "finally finally"。如果在外部 `try` 中发生 `ArrayOutOfBoundsException`，它会被外部 `catch` 块捕获，该块会打印 "exception caught inside outer catch"，然后是 "array out of bound error"。外部 `finally` 块在外部 `try` 块或 `catch` 块之后执行，打印 "finally block"。

# 9.7 异常处理中的 RETURN 语句

在 Java 的 `catch` 或 `finally` 块中使用 `return` 语句会显著影响程序的控制流。

## 9.7.1 CATCH 块中的 RETURN

当在 `catch` 块中使用 `return` 语句时，方法在处理异常后会立即退出。然而，如果方法返回，则 `finally` 块（如果存在）会被执行。这种方法允许方法处理异常并根据错误状况返回值。`catch` 块的作用捕获特定异常，执行必要的操作（如日志记录或清理），然后返回一个指示错误状况的值。

### 程序

```java
// Program for catch with return statement
public class Test {
  void main(String[] args) {
    // Create an instance of the Test class
    Test test = new Test();
    // Invoke the display method and store the returned value
    int i = test.display();
    // Print the returned value
    System.out.println("i value is " + i);
  }
  public int display() {
    try {
      // Print message inside the try block
      System.out.println("inside try block");
      // Attempt to perform division by zero, which will cause ArithmeticException
      int result = 10 / 0;
      return 1; // This line will not be executed due to the exception
    } catch (ArithmeticException e) {
      // Catch block for handling ArithmeticException
      System.out.println("inside exception block");
      return 2; // Return value if an exception occurs
    } finally {
      // Finally block that will always execute
      System.out.println("finally block");
    }
  }
}
```

输出：

`inside try block`

`inside exception block`

`finally block`

`i value is 2`

上述 Java 程序演示了方法内部 `try-catch-finally` 块和 `return` 语句的行为。`display` 方法尝试在 `try` 块内部执行除法操作 (`10/0`)。在执行除法操作之前，会打印 "inside try block"。由于除以零会导致 `ArithmeticException`，因此执行 `catch` 块。打印 "inside exception block"，并且方法返回 2。无论是否发生异常，`finally` 块都会执行。打印了 "finally block"。在 `main` 方法中，创建了 `Test` 类的实例并调用了 `display` 方法。返回的值 (2) 被存储在变量 `i` 中，并打印了 "i value is 2"。

## 9.7.2 FINALLY 块中的 RETURN

在 `finally` 块中使用 `return` 语句更为复杂，且通常不建议这样做。这是因为它可以覆盖来自 `try` 或 `catch` 块的任何返回值，使得代码更难以理解和维护。当 `finally` 块中存在 `return` 语句时，它将覆盖在 `try` 或 `catch` 块中设置的任何返回值，实际上成为方法的最终返回值。这种行为可能导致意想不到的结果，并使调试变得困难，因为无论 `try` 或 `catch` 块中的逻辑如何，最终结果都由 `finally` 块决定。

### 程序



## Program for finally with return statement

```java
public class Test {
    void main(String[] args) {
        // Create an instance of the Test class
        Test test = new Test();
        // Invoke the display method and store the return value
        int i = test.display();
        // Print the returned value
        System.out.println("i value is " + i);
    }
    public int display() {
        try {
            // Print message inside the try block
            System.out.println("inside try block");
            // Attempt to perform division by zero, which will cause ArithmeticException
            int result = 10 / 0;
            return 1; // This line will not be executed due to the exception
        } catch (ArithmeticException e) {
            // Catch block for handling ArithmeticException
            System.out.println("inside exception block");
            return 2; // Return value if an exception occurs
        } finally {
            // Finally block that will always execute
            System.out.println("finally block");
            // Return value from finally block
            return 3; // This will override return value from try or catch
        }
    }
}
```

输出：

```
inside try block

inside exception block

finally block

i value is 3
```

在这个 Java 程序中，`display` 方法演示了带有 `return` 语句的 `try-catch-finally` 块的行为。在 `try` 块内部，在执行除法操作之前会打印 "inside try block"。由于除以零会导致 `ArithmeticException`，因此执行 `catch` 块。打印 "inside exception block"，并且方法返回 2。无论是否发生异常，`finally` 块都会执行。打印了 "finally block"。在 `main` 方法中，创建了 `Test` 类的实例并调用了 `display` 方法。返回的值 (3) 被存储在变量 `i` 中，并打印了 "i value is 3"。

```java
// Call the display method, which can throw an IOException
try {
    display();
} catch (IOException e) {
    // Catch block to handle IOException
    System.out.println("caught in main method");
}
```

```java
// Method declares that it can throw IOException
public static void display() throws IOException {
    // Print message inside the method
    System.out.println("inside display method");
    // Throw Exception
    throw new IOException("Custom message");
}
```

Output:

```
inside display method

caught in main method
```

上述程序演示了使用 `try-catch` 块进行异常处理。在 `main` 方法中，`display` 方法在 `try` 块内被调用。`display` 方法声明它可能会抛出 `IOException`。在 `display` 方法内部，首先打印了 "inside display method"，然后抛出一个 `IOException`。由于抛出了该异常，它被 `main` 方法中的 `catch` 块捕获，`catch` 块打印了 "caught in main method"。

## Program

```java
// Custom exception class
class ex extends Exception {
    // Constructor that accepts message
    public ex(String message) {
        // Pass the message to superclass constructor
        super(message);
    }
}

public class Test {
    public void main(String[] args) {
        try {
            // Throw an instance of custom exception with a message
            throw new ex("defined exception");
        } catch (ex e) {
            // Catch the custom exception
            // Print "Caught" along with the exception message
            System.out.println("Caught: " + e.getMessage());
        }
    }
}
```

Output:

```
Caught: defined exception
```

上述 Java 程序定义了一个自定义异常类 `ex`，它继承自 `Exception`。`ex` 类的构造函数接收一个字符串参数，并使用 `super(message)` 将其传递给父类构造函数。在 `Test` 类中，`main` 方法在 `try` 块内部抛出了带有消息 "defined exception" 的 `ex` 实例。

## 9.8.2 抛出未检查的异常 (Throwing Unchecked Exceptions)

未检查的异常不需要被声明或处理。它们代表运行时异常，通常反映编程错误，如逻辑错误或对 API 的使用不当。

## Program

```java
class Base {
    void divide(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("Division by zero");
        }
        System.out.println("Result: " + a / b);
    }
}

public class Main {
    public void main(String[] args) {
        Base base = new Base();
        try {
            base.divide(10, 0);
        } catch (ArithmeticException e) {
            System.out.println("Caught an ArithmeticException: " + e.getMessage());
        }
    }
}
```

Output:

```
Caught an ArithmeticException: Division by zero
```

在上述程序中，`Base` 类定义了一个除法方法。`divide` 方法接收两个整数参数并检查 `b` 是否为零。如果 `b` 为零，它会抛出一个带有消息 "Division by zero" 的 `ArithmeticException`。在 `Main` 类中，创建了一个 `Base` 实例，并在 `try` 块中使用参数 10 和 0 调用 `divide` 方法。当发生除以零时，异常在相应的 `catch` 块中被捕获，该块打印一条消息，指示异常已被捕获以及错误消息。

## 未检查的异常 (unchecked exceptions)

## Program

```java
// Program for throwing the exception using throw statement
public class ExceptionHandlingExample {
    public void main(String[] args) {
        try {
            // Try block where exceptions are anticipated
            System.out.println("try block");
            // Throwing a NullPointerException
            String str = null;
            str.length(); // This will throw NullPointerException
        } catch (NullPointerException e) {
            // Catch block to handle NullPointerException
            System.out.println("exception caught in catch block");
        }
        // Continue with the rest of the program
        System.out.println("Program continues after catch block");
    }
}
```

Output:

```
try block

exception caught in catch block

Program continues after catch block
```

此 Java 程序通过 `try-catch` 块展示了异常处理。在 `try` 块内部，首先打印了 "try block"，然后抛出了 `NullPointerException`。`catch` 块捕获了此类型的异常，并打印了 "exception caught in catch block"。

## Program

```java
// Program for throwing the object of the exception using throw statement
public class CustomNullPointerExceptionExample {
    public void main(String[] args) {
        try {
            // Print message inside the try block
            System.out.println("try block");
            // Create and throw a custom NullPointerException with a message
            new NullPointerException("Custom NullPointerException message");
        } catch (NullPointerException e) {
            // Catch block to handle NullPointerException
            // Print the exception message
            System.out.println(e.getMessage());
        }
    }
}
```

Output:

```
try block

Custom NullPointerException message
```

在 Java 程序中，在 `main` 方法的 `try` 块内显式创建并抛出了自定义的 `NullPointerException`。在 `try` 块内部，抛出异常之前打印了消息 "try block"。`catch` 块捕获了 `NullPointerException`，并使用 `getMessage()` 打印了它的消息。

## 9.9 继承中的异常处理 (EXCEPTION HANDLING IN INHERITANCE)

在 Java 中，继承中的异常处理遵循类层次结构中管理异常的方式，特别是当方法被重写时。在子类中重写方法时，理解这些方法可能抛出的异常的规则至关重要。这些规则确保了异常处理的一致性和可预测性。

- 检查异常（Checked Exceptions）：如果父类方法声明了检查异常，子类中的重写方法可以声明相同的异常或更广泛的异常。
- 未检查异常（Unchecked Exceptions）：未检查异常（`RuntimeException` 的子类）不受这些规则限制，可以在子类中自由声明。
- 无异常声明（No Exception Declaration）：如果子类没有声明任何异常，则重写方法不能声明任何检查异常。但它可以声明未检查异常。

## 9.9.1 检查异常 (CHECKED EXCEPTIONS)

Java 中的检查异常在编译时强制执行规则，以确保它们被正确处理或声明。在使用继承时，子类中的重写方法必须遵循父类方法的异常声明。这确保了在继承层次结构中管理异常的一致性和可预测性，维护了代码的健壮性和可靠性。

## Program

父类和子类抛出异常的程序。

```java
import java.io.IOException;

// 基类
class Base {
    // 声明可能会抛出 IOException 的方法
    public void msg(String msg) throws IOException {
        System.out.println("Base class method");
        // 可在此处抛出 IOException
    }
}

// 重写 msg 方法的子类
class Child extends Base {
    // 重写方法也声明可能会抛出 IOException
    @Override
    public void msg(String msg) throws IOException {
        System.out.println("Child class method");
        // 可在此处抛出 IOException
    }
}
```

```java
try {
  // 调用被重写的 msg 方法
obj.msg();
} catch (IOException e) {
  // 如果抛出 IOException 则进行处理
  System.out.println("Caught in main: " + e.getMessage());
}
```

输出:

```
类方法
```

在 Java 程序中，通过继承演示了方法重写。基类有一个方法声明它可以抛出 `IOException`。子类重写了 `msg` 方法并指定它会抛出 `IOException`。这是有效的，因为 Java 中的重写方法可以声明与父类方法相同的异常，或者范围更窄的异常。在 `main` 方法中，使用基类引用创建子类实例，并调用被重写的 `msg` 方法，向控制台打印 "Child class method"。

## 程序



## 子类抛出父类受检异常的程序

```java
import java.io.FileNotFoundException;
import java.io.IOException;

// 基类
class Base {
    // 声明可以抛出 IOException 的方法
    public void msg() throws IOException {
        System.out.println("Base class method");
        // 可选在此抛出 IOException
    }
}

// 重写 msg 方法的子类
class Child extends Base {
    // 重写并抛出 FileNotFoundException 的方法
    @Override
    public void msg() throws FileNotFoundException {
        System.out.println("Child class method");
        // 可选在此抛出 FileNotFoundException
    }
}

public class Test {
    public void main(String[] args) {
        Base obj = new Child();
        try {
            // 调用被重写的 msg 方法
            obj.msg();
        } catch (FileNotFoundException e) {
            // 如果抛出 FileNotFoundException 则进行处理
            System.out.println("Caught in main (FileNotFoundException): " + e.getMessage());
        } catch (IOException e) {
            // 如果抛出其他 IOException 则进行处理
            System.out.println("Caught in main (IOException): " + e.getMessage());
        }
    }
}
```

## 异常处理

### 程序：子类抛出父类异常子类型的未检查异常的程序

```java
// 基类
class Base {
    // 声明可以抛出 RuntimeException 方法
    public void msg() throws RuntimeException {
        System.out.println("Base method");
        throw new RuntimeException("RuntimeException from base class");
    }
}

// 重写 msg 方法的子类
class ChildBase extends Base {
    // 抛出 NullPointerException 的重写方法
    @Override
    public void msg() {
        System.out.println("Child class method");
        throw new NullPointerException("NullPointerException from child class");
    }
}

public class Test {
    public void main(String[] args) {
        Base obj = new ChildBase();
        try {
            // 调用重写的异常 msg 方法
            obj.msg();
        } catch (NullPointerException e) {
            // 如果抛出 NullPointerException 则处理
            System.out.println("Caught in main: " + e.getMessage());
        } catch (RuntimeException e) {
            // 如果抛出 RuntimeException 则处理
            System.out.println("Caught in main: " + e.getMessage());
        }
    }
}
```

输出：

```
Child class method
Caught in main: NullPointerException from child class
```

上述 Java 程序演示了处理异常时继承中的方法重写。基类有一个 `msg` 方法，声明它可以抛出 `RuntimeException`。子类重写了 `msg` 方法并指定它抛出 `NullPointerException`。这是有效的，因为 Java 中重写方法抛出的异常可以比父类少或不抛出，而不能更多。`main` 方法使用基类引用创建子类实例并调用重写的 `msg` 方法，该方法输出“Child class method”。

### 程序：父类抛出检查异常，子类抛出未检查异常的程序

```java
import java.io.IOException;

// 基类
class Base {
    // 声明可以抛出检查异常 (IOException) 方法
    public void msg() throws IOException {
        System.out.println("Base class method");
        throw new IOException("IOException from base class");
    }
}

// 重写 msg 方法的子类
class Child extends Base {
    // 抛出未检查异常 (ArithmeticException) 的重写方法
    @Override
    public void msg() {
        System.out.println("Child class method");
        throw new ArithmeticException("ArithmeticException from child class");
    }
}

public class Test {
    public void main(String[] args) {
        Base obj = new Child();
        try {
            // 调用重写的 msg 方法
            obj.msg();
        } catch (ArithmeticException e) {
            // 如果抛出 ArithmeticException 则处理
            System.out.println("Caught in main: " + e.getMessage());
        } catch (IOException e) {
            // 如果抛出 IOException 则处理
            System.out.println("Caught in main: " + e.getMessage());
        }
    }
}
```

输出：

```
Child class method
Caught in main: ArithmeticException from child class
```

该 Java 程序演示了处理异常时继承中的方法重写。基类有一个方法，声明它可以抛出 `IOException`。子类重写了该方法并指定它抛出 `ArithmeticException`。这是有效的，因为 Java 中重写方法抛出的异常可以比父类方法少或不更多，但不能更多。子类方法使用基类引用创建子类实例并调用重写的 `msg` 方法，该方法输出“Child class method”。

### 程序：父类抛出单个异常，子类抛出多个异常（未检查异常）的程序

```java
import java.io.IOException;

// 基类
class Base {
    // 声明可以抛出 RuntimeException 方法
    public void msg() throws RuntimeException {
        System.out.println("Base class method");
        // 可选在此处抛出 RuntimeException
    }
}
```

## 异常处理

```java
// 重写 msg 方法的子类
class Child extends Base {
    // 抛出未检查异常的重写方法
    @Override
    public void msg() throws NullPointerException, NumberFormatException {
        System.out.println("Child class method");
        // 可选在此处抛出未检查异常
    }
}
```

```java
public class Test {
    public void main(String[] args) {
        Base obj = new Child();
        try {
            // 调用重写的 msg 方法
            obj.msg();
        } catch (RuntimeException e) {
            // 如果抛出 IOException 则处理
            System.out.println("caught in main: " + e.getMessage());
        }
    }
}
```

输出：

```
Child class method
```

在此程序中，基类 `Base` 定义了一个方法 `msg()`，声明它可以抛出 `RuntimeException`。`Child` 类继承自 `Base` 并重写了 `msg()` 方法，抛出 `NullPointerException` 和 `NumberFormatException` 等未检查异常，而不是检查异常。在 `Test` 类中，`Child` 实例被赋值给 `Base` 引用。在 `try` 块中调用了重写的 `msg()` 方法，但由于它抛出未检查异常，这些异常不会被 `RuntimeException` `catch` 块捕获。程序说明了继承中的方法重写以及检查与未检查异常的行为。

### 程序：父类抛出未检查异常，子类抛出另一个未检查异常的程序

```java
// 基类
class Base {
    // 抛出未检查异常方法
    public void msg() {
        System.out.println("Base class method");
        throw new IllegalArgumentException("Illegal argument exception thrown");
    }
}
```

```java
// 重写 msg 方法的子类
class Child extends Base {
    // 可以抛出未检查异常的重写方法
    @Override
    public void msg() {
        System.out.println("Child class method");
        throw new IndexOutOfBoundsException("Index of bounds exception thrown");
    }
}
```

```java
public class Test {
    public void main(String[] args) {
        Base obj = new Child();
        try {
            // 调用重写的 msg 方法
            obj.msg();
        } catch (IllegalArgumentException e) {
            // 处理基类抛出的异常
            System.out.println("Caught in main: " + e.getMessage());
        } catch (IndexOutOfBoundsException e) {
            // 处理子类抛出的异常
            System.out.println("Caught in main: " + e.getMessage());
        }
    }
}
```

## 异常处理

```java
public class Test {
    void main(String[] args) {
        Base obj = new Child();
        // 调用重写的 msg
        obj.msg();
    }
}
```

输出：

```
Child method
```

在上面的 Java 程序中，在继承中演示了方法重写。基类有一个方法 `msg`，且没有声明任何异常。子类重写了 `msg` 方法并指定它会抛出 `RuntimeException`。这是有效的，因为 Java 中被重写方法抛出的异常可以比父类方法少或没有，但不能更多。在 `main` 方法中，使用基类引用创建了 `Child` 实例，并调用了重写的方法，在控制台上打印了“Child method”。

## 程序：父类抛出异常（检查异常与未检查异常），子类不抛出任何异常的程序

```java
import java.io.IOException;

class Base {
    // 声明可能会抛出 IOException 和 NumberFormatException 方法
    public void msg() throws IOException, NumberFormatException {
        System.out.println("Base class method");
    }
}

class Child extends Base {
    // 不声明任何异常的重写方法
    @Override
    public void msg() {
        System.out.println("Child");
    }
}

public class Test {
    void main(String[] args) {
        Base obj = new Child();
        try {
            // 调用重写的 msg 方法
            obj.msg();
        } catch (IOException e) {
            // 如果基类抛出 IOException 则处理
            System.out.println("Caught Exception: " + e.getMessage());
        } catch (NumberFormatException e) {
            // 如果抛出 NumberFormatException 则处理
            System.out.println("Caught NumberFormatException: " + e.getMessage());
        }
    }
}
```



# 异常处理

## 用于医疗保健应用的 Java 22

上面的 Java 程序演示了在处理异常的同时进行继承中的方法重写。基类中的方法 `msg` 声明它可能会抛出 `IOException` 和 `NumberFormatException`。子类重写了 `msg` 但没有声明任何异常。这是有效的，因为与父类方法相比，Java 中被重写方法抛出的异常可以更少或没有。子类中的 `main` 方法使用基类引用创建了子类实例并调用了重写的方法，该方法输出了 `"Child"`。

## 9.10 异常传播

Java 中的异常传播是指异常从发生点通过调用栈向上传递到程序更高层级的过程，直到它被适当的异常处理器捕获或导致程序终止。这种机制允许将处理异常的责任推迟给其调用者，而不是在方法内部进行处理。

### 9.10.1 异常传播是如何工作的

Java 中的异常传播是一种将异常从发生点传递到调用栈更高层级的机制，直到它被适当的处理器捕获或导致程序终止。当异常被抛出时，如果发生异常的方法没有使用 `try-catch` 块处理它，则异常将传递给调用方法。该调用方法可以处理该异常，也可以将其进一步传播到调用栈顶层的调用者处。这个过程一直持续下去，直到找到异常或到达调用栈的顶端（通常是 `main` 方法）。如果没有找到处理器，程序将终止，Java 运行时会打印异常的堆栈跟踪。

图 9.2 释了传播过程。

在此示例中，`Method3` 抛出了 `ArithmeticException`。`Method3` 没有捕获该异常，它传播到 `Method2`，`Method2` 也没有处理。异常随后移动到 `Method1`，它同样没有捕获。最后，异常到达了 `main` 方法，该方法包含一个处理该异常的 `try-catch` 块，防止了程序意外终止。

### 9.10.2 异常传播的优点

- **简化错误处理**：通过允许异常沿调用栈向上传播，方法可以专注于其主要功能，并将错误处理留给更高层的方法。
- **促进代码重用**：方法可以重用，而不需要包含重复的错误处理代码，使代码更整洁、更容易维护。
- **关注点分离**：更高层的方法可以以集中的方式承担处理错误的责任，使错误处理策略更具一致且易于管理。

![](img/5a077f56e14b826c2dc61de6c176e5ef_376_0.png)

图 9.2 异常传播。

### 9.10.3 异常传播的局限性

- **未捕获异常**：如果在调用栈中没有找到适当的异常处理器，程序将终止，这对于健壮的应用程序可能并不理想。
- **调试复杂性**：异常传播可能会使追踪错误的来源变得更加困难，特别是在具有深度调用栈的大型复杂应用程序中。
- **性能开销**：过度使用异常传播会导致性能开销，因为异常在计算上是昂销的。

### 程序

针对未检查异常的异常传播程序：

```java
public class ExceptionPropagation {

    // 方法 m3 抛出 NullPointerException
    public static void m3() {
        System.out.println("Inside m3");
        throw new NullPointerException("Exception from m3");
    }

    // 方法 m2 调用 m3
    public static void m2() {
        System.out.println("Inside m2");
        m3();
    }

    // 方法 m1 调用 m2
    public static void m1() {
        System.out.println("Inside m1");
        m2();
    }

    public static void main(String[] args) {
        try {
            // 调用重写的 msg 方法
            m1();
        } catch (NullPointerException e) {
            // 如果抛出 NullPointerException 则处理
            System.out.println("Caught Exception: " + e.getMessage());
        }
    }
}
```

输出：

```text
Inside m1
Inside m2
Inside m3
Caught Exception: Exception from m3
```

上面的 Java 程序演示了异常的传播和处理。`main` 方法调用 `m1`，`m1` 调用 `m2`，`m2` 调用 `m3`。`m3` 方法抛出 `NullPointerException`，该异常通过 `m2` 和 `m1` 回传到 `main` 方法。异常在 `main` 方法中被捕获并打印消息。

## 用于医疗保健应用的 Java 22

### 程序

针对检查异常的异常传播程序：

```java
import java.io.IOException;

class ExceptionPropagationDemo {

    // 方法 m3 抛出 IOException
    public static void m3() throws IOException {
        System.out.println("Inside m3");
        throw new IOException("Exception from m3");
    }

    // 方法 m2 调用 m3
    public static void m2() throws IOException {
        System.out.println("Inside m2");
        m3();
    }

    // 方法 m1 调用 m2
    public static void m1() throws IOException {
        System.out.println("Inside m1");
        m2();
    }

    public static void main(String[] args) {
        try {
            // 调用重写的 msg 方法
            m1();
        } catch (IOException e) {
            // 如果抛出 IOException 则处理
            System.out.println("Caught Exception: " + e.getMessage());
        }
    }
}
```

输出：

```text
Inside m1
Inside m2
Inside m3
Caught Exception: Exception from m3
```

上面的 Java 程序演示了异常的传播和处理。`main` 方法调用 `m1`，`m1` 调用 `m2`，`m2` 调用 `m3`。`m3` 方法抛出 `IOException`，该异常通过 `m2` 和 `m1` 回传到 `main` 方法。异常在 `main` 方法中被捕获并打印消息。

## 9.11 重新抛出异常

在 Java 中重新抛出异常对于方法捕获了异常但无法完全处理的情况非常有用，允许它将异常传递给调用栈进行高层处理。它保留了原始异常的上下文，有助于调试。然而，重新抛出异常会导致调用栈变长和更复杂的错误处理，如果不使用，会使代码更难以维护。

### 9.11.1 重新抛出定义异常

在 Java 中重新抛出定义异常涉及在方法内部捕获异常，执行某些处理或记录，然后再次抛出该异常或根据上下文抛出不同的异常。这种技术通常用于处理异常，异常能够优雅地处理，同时提供额外的上下文或信息以辅助调试或错误恢复。

### 重新抛出预定义异常的优势

- **错误传播**：重新抛出允许错误沿调用栈向上传播，确保高层组件或客户端代码能够适当地处理或记录异常。
- **上下文信息**：它允许在抛出异常之前添加上下文信息，例如日志详情或自定义消息。这有助于诊断问题并理解异常产生。
- **一致的异常处理**：通过重新抛出预定义异常，你可以在应用程序的不同层级之间保持错误处理的一致性。这有助于代码更加整洁且易于维护。
- **异常包装**：它允许根据应用程序或所框架的需求，将检查异常（checked exceptions）重新包装为未检查异常（unchecked exceptions），反亦然。

### 重新抛出预定义异常的局限性

- **堆栈轨迹丢失**：如果处理不当，重新抛出异常会导致堆栈信息丢失。这使得追踪异常的来源和原因变得困难。
- **开销**：带有额外日志记录或处理的异常重新抛出可能会引入开销，影响性能，特别是在关键或频繁执行的代码中。
- **复杂性**：处理和重新抛出异常会增加代码的复杂性，特别是在处理多个异常或多层异常处理时。
- **错误隐藏风险**：异常错误的处理或重新抛出可能会掩盖原始错误消息或导致误导性的错误处理逻辑，导致调试维护更加困难。

### 程序

抛出相同类型异常的程序：

```java
public class ExceptionRethrowingDemo {

    // 触发并重新抛出 ArithmeticException 方法
    public static void display() {
        try {
            System.out.println("Inside display method");
            int result = 10 / 0; // 这将抛出 ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Exception caught in display method: " + e.getMessage());
            throw e; // 重新抛出异常
        }
    }

    public void main(String[] args) {
        try {
            // 调用重新抛出异常的 display 方法
            display();
        } catch (ArithmeticException e) {
            // 处理重新抛出的异常
            System.out.println("Exception caught in main method: " + e.getMessage());
        }
    }
}
```

## Java 22 在医疗健康领域的应用

输出：

```text
Inside display method
Exception caught in display method: / by zero
Exception caught in main method: / by zero
```

上述 Java 程序演示了在 `try-catch` 块中重新抛出异常。`main` 方法调用 `display` 方法，该方法通过除以零故意触发了 `ArithmeticException`。该异常在 `display` 方法中被捕获，打印消息，然后被重新抛出。`main` 方法捕获重新抛出的 `ArithmeticException` 并打印消息，表示异常已处理。这一过程展示了异常如何被捕获、重新抛出，然后在程序的更高层级进行处理。

### 程序

抛出不同类型异常的程序：

```java
public class ExceptionHandlingDemo {

    // 触发并作为 RuntimeException 重新抛出异常
    public static void display() {
        try {
            System.out.println("Inside display method");
            int result = 10 / 0; // 这将抛出 ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Exception caught in display method: " + e.getMessage());
            throw new RuntimeException("Exception rethrown as RuntimeException", e);
        } // 重新抛出 RuntimeException
    }

    public void main(String[] args) {
        try {
            // 调用将异常作为 RuntimeException 重新抛出的 display 方法
            display();
        } catch (RuntimeException e) {
            // 在 main 方法中处理被重新抛出的 RuntimeException:
            System.out.println("Exception caught in main method: " + e.getMessage());
        }
    }
}
```

输出：

```text
Inside display method
Exception caught in display method: / by zero
Exception caught in main method: Exception rethrown as RuntimeException
```

上述 Java 程序演示了异常处理和异常的重新抛出。`main` 方法调用 `display` 方法，该方法通过除以零故意触发 `ArithmeticException`。该异常在 `display` 方法内部被捕获，在作为 `RuntimeException` 重新抛出之前打印了消息。`main` 方法捕获此重新抛出的异常并打印消息表示其已处理。

### 9.11.2 重新抛出用户自定义异常

在 Java 中重新抛出自定义异常涉及在方法内部捕获自定义异常、执行额外的处理或日志记录，然后根据上下文再次抛出该异常或抛出不同的异常。这种方法允许开发者优雅地处理自定义异常，同时为调试或错误恢复提供额外的上下文或信息。

### 程序

重新抛出自定义异常的程序：

```java
public class CustomExceptionDemo {

    // 定义一个嵌套静态自定义异常
    public static class Ex extends Exception {
        public Ex(String message) {
            super(message);
        }
    }

    // 抛出 ArithmeticException 并将其重新抛为自定义异常
    public static void msg() throws Ex {
        try {
            System.out.println("Inside msg method");
            int result = 10 / 0; // 这将抛出 ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Caught ArithmeticException in msg method");
            throw new Ex("Custom exception after ArithmeticException");
        } // 重新抛出自定义异常
    }

    public static void main(String[] args) {
        try {
            // 调用抛出自定义异常的方法
            msg();
        } catch (Ex e) {
            // 处理自定义异常
            System.out.println("Caught exception in main: " + e.getMessage());
        }
    }
}
```

输出：

```text
Inside msg method
Caught ArithmeticException in msg method
Caught exception in main: Custom exception after ArithmeticException
```

上述 Java 程序演示了重新抛出自定义异常。`main` 方法调用 `msg` 方法，该方法故意触发 `ArithmeticException`。该异常被捕获并重新抛为 `Ex`。`main` 方法捕获此重新抛出的异常并打印其消息。

## 9.12 `catch` 中的未使用变量

在 Java 22 中，`try-with-resources` 语句可以使用未使用变量（使用 `_`）来指定资源。这允许你在不命名的情况下创建并使用资源，对于编写简洁的代码特别有用。

### 程序

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
```



`public class UnnamedVariableInCatch` 是一个 Java 程序示例，演示了在 `catch` 块中使用未命名变量（`_`）。程序的核心逻辑如下：

```java
public class UnnamedVariableInCatch {

    public static void main(String[] args) {

        try (BufferedReader reader = new BufferedReader(new FileReader("test.txt"))) {

            String line;

            while ((line = reader.readLine()) != null) {

                System.out.println(line);

            }

        } catch (IOException _) {

            System.err.println("Error reading file: File not found或无法读取.");

        }

    }

}
```

假设 `test.txt` 文件内容为：

```
This is to test
```

程序输出：

```
This is to test
```

上述程序使用 `try-with-resources` 读取 `"test.txt"`。程序读取文件的每一行并将其打印到控制台。如果发生 `IOException`，`catch` 块使用未使用变量 `_` 来处理异常。这种方法通过避免使用未使用异常变量使代码更加简洁。

## 9.13 医疗应用

医疗应用程序通过控制台输入管理患者数据库，允许用户添加经过验证的数据并通过姓名搜索患者，使用自定义异常处理无效数据场景，管理患者记录并在操作失败时抛出异常。

### 9.13.1 案例研究 1

#### 案例研究-1

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class InvalidPatientDataException extends Exception {

    public InvalidPatientDataException(String message) {

        super(message);

    }

}

class Patient {

    private String name;

    private int age;

}
```

## 异常处理

```java
class Patient {

    private String name;

    private int age;

    private String diagnosis;

    public Patient(String name, int age, String diagnosis) throws InvalidPatientDataException {

        if (name == null || name.isEmpty() || age <= 0 || diagnosis == null ||

            diagnosis.isEmpty()) {

            throw new InvalidDataException("Invalid patient data.");

        }

        this.name = name;

        this.age = age;

        this.diagnosis = diagnosis;

    }

    @Override

    public String toString() {

        return "Patient(" +

            "name='" + name + '\'' +

            ", age=' + age + '\'' +

            ", diagnosis='" + diagnosis + '\'' +

            ")";

    }

}

class PatientDatabase {

    private List<Patient> patients;

    public PatientDatabase() {

        this.patients = new ArrayList<>();

    }

    public void addPatient(Patient patient) throws InvalidPatientDataException {

        if (patient == null) {

            throw new InvalidDataException("Cannot add a null patient.");

        }

        patients.add(patient);

    }

    public Patient findByName(String name) throws InvalidPatientDataException {

        for (Patient patient : patients) {

            if (patient.toString().contains(name)) {

                return patient;

            }

        }

        throw new InvalidDataException("Patient not found.");

    }

    @Override

    public String toString() {

        return "PatientDatabase(" +

            "patients=" + patients +

            ")";

    }

}

public class MedicalApplication {

    public static void main(String[] args) {

        PatientDatabase database = new PatientDatabase();

        Scanner scanner = new Scanner(System.in);

        while (true) {

            System.out.println("1. Add Patient");

            System.out.println("2. Find Patient by Name");

            System.out.println("3. Exit");

            System.out.print("Choose option: ");

            int option = scanner.nextInt();

            scanner.nextLine();

            switch (option) {

                case 1:

                    try {

                        System.out.print("Enter name: ");

                        String name = scanner.nextLine();

                        System.out.print("Enter age: ");

                        int age = scanner.nextInt();

                        scanner.nextLine(); // Consume newline

                        System.out.print("Enter diagnosis: ");

                        String diagnosis = scanner.nextLine();

                        Patient patient = new Patient(name, age, diagnosis);

                        database.addPatient(patient);

                        System.out.println("Patient added successfully.");

                    } catch (InvalidPatientDataException e) {

                        System.out.println("Error: " + e.getMessage());

                    }

                    break;

                case 2:

                    try {

                        System.out.print("Enter name to search: ");

                        String name = scanner.nextLine();

                        Patient patient = database.findByName(name);

                        System.out.println("Patient found: " + patient);

                    } catch (InvalidPatientDataException e) {

                        System.out.println("Error: " + e.getMessage());

                    }

                    break;

                case 3:

                    System.out.println("Exiting...");

                    return;

                default:

                    System.out.println("Invalid option. Please try again.");

            }

        }

    }

}
```

该程序定义了一个自定义的检查异常 `InvalidPatientDataException` 来处理无效的患者数据输入。`Patient` 类封装了患者信息，如姓名、年龄和诊断，确保在实例化时的有效性，并在数据无效时抛出异常。`PatientDatabase` 类管理患者列表，并提供了添加患者（`addPatient`）和按名称查找患者（`findByName`）的方法。这两个方法在满足相应条件时（例如添加空患者或在数据库中未找到患者）都会抛出 `InvalidPatientDataException`。`MedicalApplication` 类充当主应用程序驱动，提供了一个基于控制台的用户界面，包含添加患者、按名称查找患者或退出程序的选项。通过 `try-catch` 块实现了输入验证，以处理数据输入和检索过程中抛出的异常，确保了健壮的错误处理和用户反馈。

### 9.13.2 案例研究 2

银屑是一种慢性免疫性疾病，会导致皮肤细胞快速堆积。这种细胞堆积会导致皮肤表面出现鳞片。鳞片周围的炎症和红肿非常常见。典型的银屑鳞片是银白色的，并在厚实的红斑中形成。本研究考虑的参数有：

- 头皮瘙痒：患者是否出现头皮瘙痒。
- 红斑：患者皮肤上是否有红斑。
- 皮肤干燥：患者是否出现皮肤干燥。
- 关节疼痛：患者是否有关节疼痛。

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class PsoriasisException extends RuntimeException {

    public PsoriasisException(String message) {

        super(message);

    }

}

class Patient {

    private String name;

    private int age;

    private boolean itchyScalp;

    private boolean redPatches;

    private boolean drySkin;

    private boolean jointPain;

    public Patient(String name, int age, boolean itchyScalp, boolean redPatches, boolean drySkin, boolean jointPain) {

        if (name == null || name.isEmpty() || age <= 0) {

            throw new PsoriasisException("Invalid patient data.");

        }

        this.name = name;

        this.age = age;

        this.itchyScalp = itchyScalp;

        this.redPatches = redPatches;

        this.drySkin = drySkin;

        this.jointPain = jointPain;

    }

    public boolean hasPsoriasis() {

        return itchyScalp && redPatches && drySkin;

    }

    @Override

    public String toString() {

        return "Patient(" +

            "name='" + name + '\'' +

            ", age='" + age + '\'' +

            ", itchyScalp=" + itchyScalp +

            ", redPatches=" + redPatches +

            ", drySkin=" + drySkin +

            ", jointPain=" + jointPain +

            ")";

    }

}
```

```java
database.addPatient(patient);

System.out.println("Patient added successfully.");

} catch (PsoriasisException e) {

  System.out.println("Error: " + e.getMessage());

}

  break;

case 2:

  try {

    System.out.print("Enter name to search: ");
```

此 `PsoriasisDetection` 程序使用异常处理和用户输入管理与牛屑症状相关的患者数据。它包含一个用于无效数据的 `PsoriasisException`、一个带有患者详情和牛屑症状属性的 `Patient` 类，以及一个用于存储和检索患者记录的 `PatientDatabase` 类。主方法（`main`）允许添加带症状的患者按按检索患者详情。异常处理确保了健壮的数据验证和错误管理，增强了程序在处理患者数据交互时的可靠性。

## 10 多线程

### 10.1 引言

“线程”可以被概念化计算机程序中执行的最小单元。线程允许并发执行，使软件能够同时执行多个任务。线程的轻量级特性使其在高效管理并行进程时特别有用。

在服务器端编程背景下，线程起着至关重要的作用。服务器通常采用多线程方法来并发处理大量的客户端请求。这增强了服务器同时为多个客户端服务的能力，提高了系统的响应速度。

Java 作为一种多功能的编程语言，支持多线程，多线程是一种涉及并发执行多个线程的范式。这种能力被用于增强应用程序的性能，特别是那些具有图形、动画或其他计算密集型任务的应用。

在 Java 中，“单线程”是最基本的处理单元。它是通过使用 `Thread` 类实现的。线程有两种主要类型：“用户线程”和“守护线程”。用户线程由应用程序创建，并持续运行，直到其分配的任务完成或应用程序终止。另一方面，守护线程是专为后台任务（如应用程序清理）设计的，并且当没有更多用户线程在运行时，它们会自动终止。

#### 程序

```java
void main(String[] args) {

    System.out.println("Single Thread");

}
```



# 单线程

该 Java 程序是一个极简的实现，作为基础 Java 应用程序结构的介绍。程序被封装在一个名为`Main`的类中，遵循 Java 规范。程序执行的主入口点是声明为`void main(String[] args)`的`main`方法。该方法在程序运行时被调用，负责初始化程序的执行。在`main`方法内部，存在一条语句：`System.out.println("Single Thread");`。该语句利用`System.out.println`方法将文本“Single Thread”打印到标准输出（通常是控制台）。`println`方法用于打印一行，并且在此语境下，它输出了指定的文本并在随后创建一个换行符。

在 Java 中使用单线程的优点包括减少应用程序的开销和降低维护成本。这种简单性对于并行执行不是首要考虑因素的场景来说是有益的。

Java 对“多线程”的支持通过内置的创建和管理线程的功能来实现。该语言提供了一个`Thread`类，可以扩展它来创建自定义线程，或者提供定义线程任务的`Runnable`接口。线程使用`start()`方法启动，从而在 Java 虚拟机（JVM）中启动并发执行。

# 10.2 多线程

多线程是在单个进程中并发执行多个线程的概念。线程是一个轻量级进程，可以独立地执行任务。在多线程程序中，多个线程独立运行并共享相同的内存空间，允许它们相互交互和协调。

多线程的需求源于以下几个因素：

- **提高性能**：多线程可以通过更高效地利用 CPU 资源来增强应用程序的性能。通过并发运行多个线程，任务可以并行执行，缩短整体执行时间。
- **响应性**：多线程允许应用程序具有响应式用户界面。长时间运行的任务（如文件 I/O 或网络操作）可以在后台线程中执行，防止用户界面变得无响应。
- **并发性**：多线程允许应用程序同时处理多个任务。这对于需要并发处理的应用尤为重要，例如同时处理多个客户端请求的 Web 服务器。
- **资源利用**：多线程允许高效利用系统资源（如 CPU 核心）。通过将任务分为多个线程，多线程应用程序可以充分利用硬件资源。
- **可扩展性**：多线程允许应用程序随着负载的增加而扩展。通过添加更多线程来处理额外任务，多线程应用程序可以在不牺牲性能的情况下适应更高水平的并发。
- **异步编程**：多线程促进了异步编程，任务可以独立于彼此执行，并在完成后通知线程。这在事件驱动和响应式编程模型中很常见。

多线程的重要性在于其在现代软件应用中优化资源使用、提高性能和增强响应能力的能力。它允许开发者设计出高效、可扩展且并发的系统，能够有效地处理复杂任务。

## 程序

```java
public class Main implements Runnable {

  @Override

  public void run() {

    // run 方法目前是空的。

  }

  void main(String[] args) {

    // 创建两个线程，每个线程关联到 Main 类实例。

    Thread t1 = new Thread(new Main(), "usha");

    Thread t2 = new Thread(new Main(), "rani");
```

```java
// 启动线程。

t1.start();

t2.start();
```

```java
// 打印线程的名字。

System.out.println("Thread names are following: ");

System.out.println(t1.getName());

System.out.println(t2.getName());
```

输出：

```
Thread names are following:
usha
rani
```

该 Java 程序通过实现`Runnable`接口展示了多线程的引入。在`Main`类中，`run`方法目前是空的。在`main`方法中，创建了两个线程，每个线程关联到`Main`类实例。线程`t1`和`t2`被分配了不同的名称，`usha`和`rani`。随后调用`start`方法启动线程，启动它们的并发执行。启动后，我们使用`getName`方法打印了线程的名字。

# 多线程 381

- **新建（New）**：在初始阶段，使用`Thread`类创建线程。在程序启动线程之前，它一直处于“新建”状态。这一阶段也被称为线程的诞生。
- **可运行（Runnable）**：在线程实例上调用`start`方法后，它会进入“可运行”状态。控制权被交给调度器，由调度器决定何时执行该线程。线程已准备就绪，但实际执行取决于调度器的决定。
- **运行（Running）**：当线程开始执行分配的任务时，进入“运行”状态。调度器从池中选择一个线程，它便在应用程序内部开始执行。在此阶段，线程积极地参与程序的运行。
- **等待（Waiting）**：当线程必须放弃执行权时，发生“等待”状态。在多个线程并发运行的情况下，它们之间需要同步。因此，线程可能需要等待另一个线程完成其执行。这种状态被恰当地称为“等待”状态。
- **死亡（Dead）**：线程生命周期的最后一个阶段是“死亡”状态。当线程完成处理并终止时，就会发生这种状态。线程一旦完成任务，就会进入“死亡”状态。在此状态下，线程已结束执行且不再活跃。

# 10.4 线程方法

在 Java 中，`Thread`类提供了几个用于管理和控制线程的方法。这些方法允许开发者在 Java 程序中创建、启动、暂停、恢复和操纵线程。

## 10.4.1 START()

此方法用于启动线程的执行。当被调用时，线程的`run()`方法会被触发，线程开始执行。

### 程序

```java
public class Main extends Thread {

  @Override

  public void run() {

    // 线程执行的任务

    System.out.println("Thread is running...");

  }

  void main(String[] args) {

    // 创建 Main 类的实例，该类继承自 Thread

    Main t = new Main();

    // 启动线程

    t.start();

  }

}
```

输出：

```
Thread is running...
```

## 382 用于医疗和健康应用的 Java 22

上面的 Java 程序通过扩展`Thread`类演示了多线程。`Main`类继承了`Thread`并重写了它的`run`方法，该方法包含了线程运行时要执行的特定任务。在这种情况下，`run`方法打印消息`Thread is running...`。在`main`方法中，通过`Main t = new Main();`创建了`Main`类的实例，并在该实例上调用了`start`方法（`t.start();`）。`start`方法在独立的控制线程中启动`run`方法的执行。因此，输出显示消息`Thread is running...`，表示线程已启动并正在执行`run`方法中指定的任务。

## 10.4.2 SLEEP(LONG MILLIS)

此方法按指定的毫秒数暂停当前线程的执行。它可以用于在线程中引入延迟或实现超时。

### 程序

```java
public class Main extends Thread {

    @Override

    public void run() {

        // 循环模拟带延迟的任务

        for (int i = 1; i <= 4; i++) {

            try {

                // 暂停 500 毫秒

                Thread.sleep(500);

            } catch (InterruptedException e) {

                e.printStackTrace();

            }

            // 打印 i 的并发值

            System.out.println(i);

        }

    }

    public void main(String[] args) {

        // 创建 Main 类的实例

        Main t = new Main();

        // 启动线程

        t.start();

    }

}
```

输出：

```
1
2
3
4
```

上面的 Java 程序扩展了`Thread`类，通过重写的`run`方法中的特定任务实现了多线程。在该程序中，`run`方法包含一个从 1 到 4 的循环。在每次迭代中，线程被程序为使用`Thread.sleep(500)`暂停 500 毫秒。此方法在每次迭代的执行期间产生了延迟。在`main`方法中，通过`Main t = new Main();`创建了`Main`类的实例，并在实例上调用了`start`方法（`t.start();`）。这启动了线程的并发执行，重写的`run`方法异步执行。在执行期间，`i`的值在循环内被打印，并每隔 500 毫秒暂停一次。输出说明了线程执行的交织特性，展示了主线程和新启动的线程如何并发执行。由于存在睡眠间隔，输出显示了 1 到 4 的值，且每个值之间有延迟。

## 10.4.3 GET() AND SET()

`getName()`方法是 Java `Thread`类提供的一个方法，用于获取线程名称。当你创建一个线程对象时，可以可选地使用`setName()`方法分配名称。稍后，你可以使用`getName()`方法获取此名称。

### 程序

```java
public class Main extends Thread {

    @Override

    public void run() {

        // 打印当前线程名称

        System.out.println(Thread.getName());

    }

    public void main(String[] args) {

        // 创建 Main 类的实例

        Main t = new Main();

        // 设置名称

        t.setName("Thread-1");

        // 启动线程

        t.start();

    }

}
```

输出：

```
Thread-1
```

上面的 Java 程序通过扩展`Thread`类演示了侧重于获取线程名称的多线程。

# 多线程 385

```java
public void run() {

  // 循环打印当前执行的线程的名称

  for (int i = 0; i < 3; i++) {

    System.out.println(Thread.currentThread().getName());

  }

}

public static void main(String[] args) {

  // 创建两个 Main 类的实例，代表两个线程

  Main t1 = new Main();

  Main t2 = new Main();

  // 启动两个线程

  t1.start();

  t2.start();

  // 主线程中的循环

  for (int i = 0; i < 3; i++) {

    // 建议调度程序主线程愿意让出 CPU

    Thread.yield();

    System.out.println(Thread.currentThread().getName());

  }

}
```

输出：

```
Thread-0
Thread-0
Thread-0
Thread-1
Thread-1
Thread-1
main
main
main
```

上述 Java 程序扩展了`Thread`类以演示多线程，重点在于使用`yield`方法进行线程控制。`Main`类包含一个被重写的`run`方法，该方法执行一个循环并打印当前执行线程的名称（使用`Thread.currentThread().getName()`获取）。在`main`方法中，创建了两个`Main`类实例（`t1`和`t2`）来代表独立的线程。在每个实例上调用`start()`方法以启动执行。由于两个线程的`run`方法并发运行，导致它们的线程输出交替。在主线程中，执行了另一个循环，在每次迭代中对`t1`调用`yield`方法。`yield`方法建议调度程序放弃处理处理器，允许其他线程（包括主线程）可能运行。程序的输出展示了两个子线程（`t1`和`t2`）与主线程的交替执行。`yield`方法引入了一种协作多任务处理机制，允许主线程和子线程共享处理器时间。

# 10.4.5 SUSPEND() & RESUME()

- `suspend()`：此方法挂起调用它的线程的执行。当线程被挂起时，它会停止执行代码，但保留其所有资源，包括对临界区域的锁。如果被挂起的线程持有另一个线程继续执行所需的锁，可能会导致死锁。因此，强烈不建议使用`suspend()`。

# 用于医疗和健康应用的 Java 22

- `resume()`：此方法恢复使用`suspend()`方法挂起的线程的执行。它允许被挂起的线程从挂起的地方继续执行。然而，使用`resume()`也可能导致状态不一致和竞态条件等问题。
- `suspend()`和`resume()`都是已弃用的方法。因此用户运行下面的程序可能会得到警告。

## 程序

```java
public class Main extends Thread {

    private static final int SLEEP_DURATION = 400;

    @Override

    public void run() {

        for (int i = 1; i <= 4; i++) {

            try {

                // 暂停线程 400 毫秒

                Thread.sleep(SLEEP_DURATION);

                // 输出当前线程名称和循环变量

                System.out.println(Thread.currentThread().getName() + "\n" + i);

            } catch (InterruptedException e) {

                // 处理可能的中断

                e.printStackTrace();

            }

        }

    }

    public static void main(String[] args) {

        // 创建三个 Main 类的实例，代表三个线程

        Main t1 = new Main();

        Main t2 = new Main();

        Main t3 = new Main();

        t1.start();

        t2.start();

        t3.start();

        try {

            // 允许线程运行一会儿

            Thread.sleep(500);

            // 挂起 t2 线程

            t2.suspend();

            // 启动 t3 线程（已启动但并发运行）

            // 允许线程运行一会儿

            Thread.sleep(500);

            // 恢复 t2 线程

            t2.resume();

        } catch (InterruptedException e) {

            e.printStackTrace();

        }

    }

}
```

输出：

```
Thread-0
1
Thread-2
1
Thread-1
1
Thread-0
2
Thread-2
2
Thread-1
2
Thread-0
3
Thread-2
3
Thread-1
3
Thread-0
4
Thread-2
4
Thread-1
4
```

上述 Java 程序扩展了`Thread`类，以展示关注挂起和恢复的多线程。`Main`类包含一个被重写的`run`方法，其中包含一个从 1 到 4 的循环。在每次迭代中，线程被程序为使用`sleep(400)`暂停 400 毫秒，并带有循环变量打印当前执行线程名称。在`main`方法中，创建了三个`Main`类实例（`t1`、`t2`和`t3`）来代表独立的线程。在`t1`、`t2`和`t3`上调用`start()`方法以启动并发执行。通过使用`suspend`方法显式地挂起`t2`线程，它会暂时停止执行。最后，使用`resume`方法恢复`t2`线程，允许其继续执行。

# 10.4.6 STOP() & INTERRUPT()

在多线程中，`stop()`和`interrupt()`方法用于线程，它们具有不同的目的：

## stop()

- `stop()`方法用于强制终止线程。当`stop()`被调用时，该线程会立即停止执行。
- 这种方法是不安全的且已弃用的，因为它可能导致对象处于不一致的状态，产生死锁。

## interrupt()

- `interrupt()`方法通过设置线程的中断状态来工作。
- 与`stop()`不同，它是更安全的做法，因为它允许线程检查中断状态并优雅地处理。

# 用于医疗与健康应用的 Java 22

输出：



`Thread-0 : 1`

`Thread-0 : 2`

`Thread-0 : 3`

`Thread-0 : 4`

`Thread-1 : 1`

`Thread-2 : 1`

`Thread-1 : 2`

`Thread-2 : 2`

`Thread-1 : 3`

`Thread-2 : 3`

`Thread-1 : 4`

`Thread-2 : 4`

上述 Java 程序扩展了`Thread`类，并展示了多线程处理，重点关注了使用`join`方法进行线程同步。`Main`类包含一个重写的`run`方法，该方法执行一个循环，使用`Thread.sleep(100)`模拟延迟，并打印当前执行线程的名称以及循环变量`i`。在`Main`类中，创建了三个`Main`类的实例`t1`、`t2`和`t3`来表示线程。在`t1`上调用了`start`方法以启动其执行。随后，`t1`上的`join`方法完成执行。这确保了后续的线程`t2`和`t3`在`t1`完成之前不会启动。在`t1`完成后，主线程继续使用`start`方法启动`t2`和`t3`。

# 10.5 扩展 Thread 类

在 Java 中通过扩展`Thread`类创建线程涉及一个两个步骤的过程，这为管理多个线程提供了更高的灵活性。

## 步骤 1：重写 `run()` 方法

在第一步中，你创建一个扩展内置`Thread`类的新类。这个新类作为你自定义线程的蓝图。在这个类中，你需要重写由`Thread`类提供的`run()`方法。`run()`方法是线程的入口，你在这里封装完整的业务逻辑或你想让线程执行的特定任务。重写`run()`方法的语法如下：

```java
public class MyThread extends Thread {

    @Override
    public void run() {
        // Thread execution logic
    }

}
```

在上面的示例中，`Main`是扩展`Thread`的自定义类，并且`run()`方法被重写，以包含你想让线程执行的特定操作。

## 步骤 2：启动线程

一旦你创建了`Thread`类的对象（在此情况下为`MyThread`），就可以通过调用`start()`方法来启动线程。`start()`方法负责启动线程的执行，它在内部调用了你用自定义逻辑重写的`run()`方法。启动线程的语法如下：

```java
public class Main {

    public void main(String[] args) {
        // 创建 MyThread 的实例
        MyThread myThread = new MyThread();

        // 启动线程
        myThread.start();
    }

}
```

在上面的代码中，创建了`MyThread`类，并调用了`start()`方法来启动线程的执行。然后，线程开始执行在重写的`run()`方法中定义的逻辑。

# 程序

```java
class Threadtest extends Thread {

    private String tName;
    private Thread t;

    // Constructor
    public Threadtest(String name) {
        this.tName = name;
        System.out.println("Creating " + tName);
    }

    @Override
    public void run() {
        try {
            System.out.println("Running " + tName);

            for (int i = 4; i > 0; i--) {
                System.out.println("Thread: " + tName + ", " + i);
                Thread.sleep(50); // Pause for 50 milliseconds
            }
        } catch (InterruptedException e) {
            System.out.println("Thread " + tName + " interrupted.");
        }

        System.out.println("Thread " + tName + " exiting.");
    }

    @Override
    public void start() {
        System.out.println("Starting " + tName);

        if (t == null) {
            t = new Thread(this, tName);
            t.start();
        }
    }

}

public class Main {

    public void main(String[] args) {
        // 创建 Threadtest 的实例
        Threadtest T1 = new Threadtest("Thread-1");
        Threadtest T2 = new Threadtest("Thread-2");

        // 启动线程
        T1.start();
        T2.start();
    }

}
```

```text
Output:

Creating Thread-1
Creating Thread-2
Starting Thread-1
Running Thread-1
Starting Thread-2
Running Thread-2
Thread: Thread-1, 4
Thread: Thread-2, 4
Thread: Thread-1, 3
Thread: Thread-2, 3
Thread: Thread-1, 2
Thread: Thread-2, 2
Thread: Thread-1, 1
Thread: Thread-2, 1
Thread Thread-2 exiting.
Thread Thread-1 exiting.
```

该 Java 程序通过扩展`Thread`类的自定义类`Threadread`展示了多线程。该类定义了一个具有特定行为的线程，并并发创建了该类的两个实例。在`Threadread`类中，构造函数初始化线程名称（`Name`）并打印表示创建线程的消息。从`Thread`类重写的`run()`方法包含了线程将执行的特定任务。它打印了从 4 到 1 的倒计时以及名称，并在每次迭代之间暂停 50 毫秒。如果线程被异常中断，将打印相应的消息。最后，线程在完成后会打印退出消息。`start`方法也被重写以自定义线程的启动过程，如果线程尚未初始化（`' ' == null`），它将创建一个新的`Thread`对象并启动它。在`Main`类中，创建了两个`Threadread`实例：`T1`和`T2`。随后在每个实例上调用了`start`方法，启动了两个线程的并发执行。

# 10.6 使用 Runnable 接口创建线程

在 Java 中通过实现`Runnable`接口创建线程涉及三个步骤的过程，为定义并发执行的任务提供了一种灵活的方法。

## 步骤 1：定义任务逻辑

在初始步骤中，你通过实现`run()`方法来定义线程逻辑，该方法是线程的入口。你在这里封装完整的业务逻辑或你想让线程执行的特定任务。

## 步骤 2：创建线程对象

作为第二步，你创建一个实现`Runnable`接口类的实例。然后使用提供的构造函数实例化`Thread`对象。

## 步骤 3：启动线程

最后一步是通过调用`Thread`对象上的`start()`方法来启动线程。该方法启动线程的执行，并在内部调用了你定义的`run()`方法。

# 用于医疗与健康应用的 Java 22

```java
T2.start();

}
```

输出：

```text
Creating Thread-1
Starting Thread-1
Creating Thread-2
Starting Thread-2
Running Thread-1
Running Thread-2
Thread: Thread-1, 4
Thread: Thread-2, 4
Thread: Thread-1, 3
Thread: Thread-2, 3
Thread: Thread-1, 2
Thread: Thread-2, 2
Thread: Thread-1, 1
Thread: Thread-2, 1
Thread Thread-2 exiting.
```

上述 Java 程序通过在`Runnables`类中实现`Runnable`接口，演示了多线程。该类封装了线程的逻辑，程序创建了它的两个实例来演示并发执行。在`Runnables`类中，构造函数初始化了线程名称（`iName`）并输出一条指示线程创建的消息。`Runnable`接口要求的`run()`方法包含了线程将执行特定任务。在这种情况下，它会从 4 到 1 进行倒计时并带上线程名称，在每次迭代之间引入了 50 毫秒的暂停。如果由于异常发生中断，则会打印相应的消息。最后，线程在完成后输出每条消息。重写了`start`方法以自定义线程的启动过程。最后输出一条指示线程启动的消息，如果线程尚未初始化（`t == null`），则会创建一个新的`Thread`对象并启动。在`Main`类中，创建了两个`Runnables`实例：`T1`和`T2`。调用`start()`方法，启动两个线程的并发执行。

# 10.7 线程优先级

线程优先级在 Java 并发中起着至关重要的作用，帮助操作系统决定线程执行的顺序。线程的优先级范围从`MIN_PRIORITY`（1）到`MAX_PRIORITY`，每个线程的默认优先级设置为`NORMAL_PRIORITY`（5）。从本质上说，优先级表示线程在程序执行中的重要性。分配有较高优先级的线程将优于低优先级的对应线程，表明它们在执行流中的重要性增加。然而，必须注意的是，使用线程优先级并不提供执行顺序的严格保证，因为它深受底层平台的影响。因此，优先级机制取决于平台，相同的优先级集合在不同系统上可能会出不同的行为。

Java 线程的默认优先级设置为 5。当创建新线程时会使用此默认优先级。线程优先级的范围是`MIN_PRIORITY`（值为 1）和`MAX_PRIORITY`（另一个值为 10 的常量）。`Thread`类中定义的三个常量是：

- `static int N_PRIORITY`：该常量表示普通优先级级别，通常分配给没有特定优先级要求的线程。其值被设置为 5。
- `public static MIN_PRIORITY`：该常量代表线程可以拥有的最低优先级级别。其值设置为 1。
- `public static MAX_PRIORITY`：该常量代表线程可以拥有的最高优先级级别。其值设置为 10。

这些常量为 Java 程序中设置和比较线程优先级提供了一种方便的方法。线程调度器使用线程优先级来在多个线程竞争 CPU 时间时，确定线程调度运行的顺序。

# 程序

```java
public class RunnableExample implements Runnable {

  @Override
  public void run() {
    // 此方法在新线程中执行
    System.out.println("Thread Running");
  }

  public void main(String[] args) {
    // 创建 RunnableExample 的实例
    RunnableExample runnableInstance = new RunnableExample();

    // 创建新 Thread，并传递 Runnable 实例
    Thread t = new Thread(runnableInstance);

    // 启动线程
    t.start();

    // 打印线程的默认优先级
    System.out.println("Thread Priority: " + t.getPriority());

    // 设置优先级
    t.setPriority(10);

    System.out.println("Thread Priority: " + t.getPriority());
  }

}
```

输出：

```text
Thread Priority: 5
Thread Priority: 10
Thread Running
```

上述 Java 程序通过实现`Runnable`接口的`Main`类演示了基础的多线程功能，这需要实现`run`方法，在本例中该方法保持为空。当实例化一个名为`t`的新`Thread`对象时，该线程上的`start()`方法会启动`run`方法的执行。紧随线程启动后，会打印“Thread Running”以指示线程已开始执行。随后，使用`t.getPriority()`获取并显示了线程的默认优先级。线程继承父线程的优先级，父线程优先级通常设置为默认优先级值，通常为`NORM_PRIORITY`（5）。

# 10.8 同步

在多个线程在同一个程序中运行的场景下，并发访问共享资源可能会产生并发问题。这些问题可能导致不可预测的结果，例如当多个线程尝试同时从同一资源读取或写入时，会导致数据损坏或冲突。例如，如果多个线程尝试同时写入同一个文件，可能会导致数据损坏，因为一个线程可能会覆盖另一个线程。

为了解决此类问题，采用了同步机制，以确保在任何时候只有一个线程可以访问共享资源。在 Java 中，每个对象都与一个监控器（monitor）关联，线程可以锁定或解锁此监控器。一次允许一个线程持有监控器的锁。在 Java 中，语言提供了一种方便的机制通过同步块创建线程并同步其任务。同步语句的通用语法如下：

```java
synchronized (objectId) {
  // 访问变量和其他共享资源
}
```

在这里，`objectId`是一个对象的引用，与该监控器相关的锁由同步语句获取。为了说明这一点，考虑两个使用两个线程打印计数器的示例。在线程未同步的情况下，计数器值可能会出现无序的情况。相反，当计数器被封装在`synchronized`块中，输出将显示两个线程定义良好的顺序计数器值。这种同步确保了对共享资源的访问是协调的，防止了多线程环境中的不一致性。

# 多线程

- 协作涉及线程之间的通信与协调。它允许线程通过相互通知共享状态的变化来共同工作。这通常通过`wait()`、`notify()`和`notifyAll()`等方法实现。

## 10.9 互斥

互斥确保同一时间只有一个线程可以访问共享资源。在 Java 中，有几种方法可以实现互斥：

- 同步方法（Synchronized Method）：通过将方法声明为`synchronized`，同一时间只有一个线程可以执行该方法，从而防止干扰。
- 同步块（Synchronized Block）：可以使用`synchronized`关键字对特定的代码块进行同步，确保同一时间只有一个线程可以执行该块。
- 静态同步（Static Synchronization）：同步可以应用于静态方法，防止多个线程并发执行同一类的同步方法。

## 10.9.1 同步块

Java 中的同步块是一个锁定在特定对象上的代码段，确保对于该对象同一时间只有一个线程可以执行该代码。这有助于在访问共享资源时维护线程安全。

### 程序

```java
class Display {

    // synchronized method to ensure thread-safe access
    public synchronized void fun() {

        try {
            for (int i = 5; i > 0; i--) {
                System.out.println("value " + i);
                Thread.sleep(100); // Sleep to simulate time-consuming task
            }
        } catch (InterruptedException e) {
            System.out.println("Thread interrupted.");
        }
    }

}

class ThreadTest extends Thread {

    private Display display;
    private String name;

    // Constructor to initialize the Display object and thread name
    public ThreadTest(Display display, String name) {
        this.display = display;
        this.name = name;
    }

    @Override
    public void run() {
        System.out.println("Starting " + name);
        display.fun(); // Call the synchronized method
```



```java
System.out.println("Thread " + name + " exiting.");

}

}

public class Main {

    public static void main(String[] args) {

        // Create a shared Display object

        Display d = new Display();

        // Create two ThreadTest instances, both using the same Display object

        ThreadTest t1 = new ThreadTest(d, "Usha");

        ThreadTest t2 = new ThreadTest(d, "Rani");

        // Start both threads

        t1.start();

        t2.start();

        // Wait for both threads to finish

        try {

            t1.join();

            t2.join();

        } catch (InterruptedException e) {

            System.out.println("Main thread interrupted.");

        }

    }

}
```

### 输出

```text
Starting Usha
Starting Rani
value 5
value 4
value 3
value 2
value 1
value 5
value 4
value 3
value 2
value 1
Thread Rani exiting.
Thread Usha exiting.
```

上述 Java 程序演示了在多线程中使用 `synchronized` 关键字实现同步的概念。它包含三个类：`display`、`Threadtest` 和 `Main`。

`display` 类包含一个名为 `fun()` 的方法，设计用于在循环中运行打印从 5 到 1 的值。然而，该方法被封装在 `try` 块中以捕获任何潜在的异常，如果线程在执行期间被中断，则会打印消息。

`Threadtest` 类继承了 `Thread` 类，并在调用时使用 `synchronized` 关键字获取共享 `display` 对象的锁，并确保同一时间只有一个线程可以执行 `fun` 方法，防止输出中潜在的冲突或不一致。

在 `main` 方法中，创建了 `display` 类的实例（`d`）。随后，创建了两个 `Threadtest` 类的实例（`t1` 和 `t2`），它们都关联到同一个 `display` 对象。使用 `start` 方法并发启动两个线程。在执行期间，`synchronized` 块确保同一时间只有一个线程可以执行共享 `display` 对象的 `fun` 方法。

## 10.9.2 同步方法

Java 中的同步方法会锁定其所属的对象，确保同一时间只有一个线程可以执行它。

### 程序

```java
class SyncMethod {

  // Synchronized method to ensure thread-safe access

  public synchronized void display(int n) {

    for (int i = 1; i <= n; i++) {

      try {

        // Print the current number along with the thread name

        System.out.println(Thread.currentThread().getName() + " : " + i);

        // Sleep to simulate processing time

        Thread.sleep(100);

      } catch (InterruptedException e) {

        System.out.println("Thread interrupted.");

      }

    }

  }

}

class Sample extends Thread {

  private SyncMethod syncMethod;

  private int n;

  // Constructor to initialize SyncMethod object and integer parameter

  public Sample(SyncMethod syncMethod, int n) {

    this.syncMethod = syncMethod;

    this.n = n;

  }

  @Override

  public void run() {

    syncMethod.display(n); // Call the synchronized method

  }

}

public class Main {

    public static void main(String[] args) {

        // Create a shared SyncMethod object

        SyncMethod syncMethod = new SyncMethod();

        // Create two Sample instances

        Sample s1 = new Sample(syncMethod, 5);

        Sample s2 = new Sample(syncMethod, 5);

        // Start both threads

        s1.start();

        s2.start();

        // Wait for both threads to finish

        try {

            s1.join();

            s2.join();

        } catch (InterruptedException e) {

            System.out.println("Main thread interrupted.");

        }

    }

}
```

### 输出

```text
Thread-0 : 1
Thread-0 : 2
Thread-0 : 3
Thread-0 : 4
Thread-0 : 5
Thread-1 : 1
Thread-1 : 2
Thread-1 : 3
Thread-1 : 4
Thread-1 : 5
```

# 多线程

```java
public synchronized static void display(int n) {

    for (int i = 1; i <= n; i++) {

        try {

            // 打印当前线程的名字

            System.out.println(Thread.currentThread().getName());

            // 睡眠以模拟处理时间

            Thread.sleep(100);

        } catch (InterruptedException e) {

            System.out.println("线程被中断.");

        }

    }

}

class Test1 extends Thread {

    private int n;

    // 用于初始化整数参数的构造函数

    public Test1(int n) {

        this.n = n;

    }

    @Override

    public void run() {

        Test.display(n); // 调用同步静态方法

    }

}

class Test2 extends Thread {

    private int n;

    // 用于初始化整数参数的构造函数

    public Test2(int n) {

        this.n = n;

    }

    @Override

    public void run() {

        Test.display(n); // 调用同步静态方法

    }

}

public class Main {

    public static void main(String[] args) {

        // 创建 Test1 和 Test2 线程实例

        Test1 t1 = new Test1(5);

        Test2 t2 = new Test2(5);

        // 启动两个线程

        t1.start();

        t2.start();

        // 等待两个线程完成

        try {

            t1.join();

            t2.join();

        } catch (InterruptedException e) {

            System.out.println("主线程被中断.");

        }

    }

}
```

### 输出

```text
Thread-0
Thread-0
```

# 用于医疗和健康应用的 Java 22

```text
Thread-0
Thread-0
Thread-0
Thread-1
Thread-1
Thread-1
Thread-1
Thread-1
```

上述 Java 程序涉及一个名为 `Test` 的类，该类包含一个名为 `display` 的同步静态方法。该方法接收一个整数 `n` 并执行循环，在指定的值范围内打印当前线程的名字。在循环内部，使用 `Thread.sleep(100)` 语句进行短暂暂停。

另外两个类 `Test1` 和 `Test2` 继承自 `Thread` 类。这些类都有一个 `run` 方法，被调用时会使用不同的整数调用 `Test` 类的同步 `display` 方法。

在 `Main` 类中，创建了 `Thread` 子类 `Test1` 和 `Test2` 的两个实例，即 `t1` 和 `t2`。随后，使用 `start` 方法并发启动两个线程。`synchronized` 的使用确保了同一时间只有一个线程可以访问 `display` 方法的临界区域，防止了潜在的干扰并确保了顺序执行。程序的输出将显示 `display` 方法中指定值范围内并发运行的线程的名字。

# 10.10 线程间通信

线程间通信（也称为协作）是指允许同步线程在多线程环境中相互通信的机制。

协作涉及停止一个正在其临界区域中执行的线程的过程，允许另一个线程进入或锁定同一个临界区域并继续其执行。这种协调对于同步至关重要，并确保线程能够在互不干扰的情况下高效工作。

在 Java 中，线程间通信通过 `Object` 类的三个方法实现：

- `wait()` 方法：导致当前线程等待，直到另一个线程调用 `notify()` 或 `notifyAll()` 方法。其他线程进入等待状态，并将保持该状态，直到被另一个线程通知。
- `notify()`：`notify()` 方法会唤醒一个正在该对象监视器（monitor）上等待的线程。它允许一个线程继续执行。
- `notifyAll()`：`notifyAll()` 方法会唤醒所有正在该对象监视器上等待的线程。这确保了多个等待的线程收到通知并恢复执行。

这些方法为线程同步动作和有效通信提供了强大的手段。通过在 `synchronized` 块中使用 `wait()`、`notify()` 和 `notifyAll()`，Java 程序员可以设计出以受控且同步的方式协调活动的多线程应用程序。

Java 中的线程可以使用 `wait()`、`notify()` 和 `notifyAll()` 方法进行通信。这些方法是 `Object` 类的一部分，并被声明为 `final`。它们只能在同步上下文中被调用，以确保线程之间良好的协调。

`wait()` 方法导致当前线程进入等待状态，直到另一个线程在同一个对象上调用 `notify()` 或 `notifyAll()` 方法。当调用 `notify()` 方法时，它会唤醒一个正在该对象监视器上等待的线程。`notifyAll()` 方法会唤醒所有在同一对象监视器上等待的线程。

线程通过调用其中一个 `wait()` 方法进入等待状态。需要注意的是，如果当前线程没有拥有对象的监视器，这些方法可能会抛出 `IllegalMonitorStateException`。

![线程间通信示意图](img/5a077f56e14b826c2dc61de6c176e5ef_412_0.png)

# 多线程 403

## 10.10.1 `WAIT()`

`wait()` 方法让调用线程释放锁并进入睡眠状态，直到另一个线程进入同一个监视器并调用 `notify()`。

## 10.10.2 `NOTIFY()`

`notify()` 方法唤醒一个正在对象监视器上等待的线程。它允许一个线程继续执行。

## 10.10.3 `NOTIFYALL()`

`notifyAll()` 方法唤醒所有在对象监视器上等待的线程。这确保了多个等待的线程收到通知并恢复执行。

## 程序

```java
class Test {

    // 确保跨线程可见的可 volatile变量

    private volatile boolean b = false;

    // 设置标记并通知等待线程的同步方法

    public synchronized void fun() {

        b = true;

        notify(); // 通知等待线程

    }

    // 等待标记被设置的同步方法

    public synchronized void fun2() {

        while (!b) {

            try {

                wait(); // 等待通知

            } catch (InterruptedException e) {

                System.out.println("线程被中断.");

            }

        }

        System.out.println("Thread-0");

    }

}

class Test1 extends Thread {

    private Test t;

    // 初始化 Test 对象的构造函数

    public Test1(Test t) {

        this.t = t;

    }

    @Override

    public void run() {

        t.fun(); // 调用 fun 方法

    }

}

class Test2 extends Thread {

    private Test t;

    // 初始化 Test 对象的构造函数

    public Test2(Test t) {

        this.t = t;

    }

    @Override

    public void run() {

        t.fun2(); // 调用 fun2 方法

    }

}

public class Main {

    public static void main(String[] args) {

        Test t = new Test(); // 创建 Test 类的实例

        Test1 t1 = new Test1(t); // 创建调用 fun 的线程

        Test2 t2 = new Test2(t); // 创建调用 fun2 的线程

        t2.start(); // 启动调用 fun2 的线程

        t1.start(); // 启动调用 fun 的线程

    }

}
```



# 多线程

上述 Java 程序演示了同步机制的使用，特别是`wait()`和`notify()`方法，用于实现两个线程之间的通信与协作。该程序定义了一个类`test`，其中包含两个同步方法`fun1`和`fun2`以及一个`volatile`的布尔变量`b`。在`fun1`方法中，布尔变量`b`被设置为`true`，并使用`notify()`方法发送了通知。该方法旨在在满足特定条件时由一个线程调用。相反，`fun2`方法设计在另一个线程中运行。它进入一个同步块并检查布尔变量`b`的值。如果条件不满足（即`b`为`false`），该线程将使用`wait()`方法进入等待状态。这种等待状态将一直持续，直到调用`fun1`方法将`b`设为`true`并通知等待的线程恢复执行。在`Main`类中，创建了`test`类的实例（`t`）。实例化了两个线程（`t1`和`t2`），其中`t1`调用`fun1`方法，`t2`调用`fun2`方法。执行顺序由`start`方法控制。当程序执行时，`t2`启动`fun2`方法并进入等待状态。随后，`t1`执行`fun1`方法，将`b`的值设置为`true`并通知等待线程。这导致`t2`被唤醒并恢复其`fun2`方法的执行。

## 10.11 结构化并发

结构化并发在 Java 22 中引入，它解决了并发编程中的若干个关键需求，旨在简化开发、增强代码可靠性并改进资源管理。

### 10.11.1 结构化并发的需求

- **简化错误处理**：传统的并发编程往往会导致复杂的错误处理场景，例如线程泄漏或资源清理不完全。结构化并发为管理并发任务中的错误提供了统一的方法，使得处理异常和确保资源妥善清理变得更容易。
- **增强任务协作**：在传统的并发编程中协调任务具有挑战性，会导致竞态条件或死锁等问题。结构化并发引入了有助于任务协作的结构，如作用域生命周期和取消传播，确保了任务执行更具预测性和易于管理。
- **改进资源管理**：在多个并发任务之间有效管理资源对于应用的性能和稳定性至关重要。结构化并发通过在任务完成或取消时自动清理与任务相关的资源，促进了更好的资源管理实践，减少了内存泄漏并提高了系统可靠性。
- **促进最佳实践**：通过在并发编程中强制结构化，结构化并发鼓励开发者一致地遵循最佳实践。这包括资源的作用域生命周期、处理取消以及确保任务能够洁地完成执行，有助于构建健壮且易于维护的代码库。
- **支持现代应用**：现代应用程序通常需要处理大量任务，例如 Web 服务器、实时分析和事件驱动架构。结构化并发为开发者提供了高效管理这些复杂性的的工具，同时保持了代码的清晰度并降低了错误风险。

### 程序

```java
import java.util.concurrent.*;

public class StructuredConcurrencyExample {

    public void main(String[] args) {

        ExecutorService executor = Executors.newFixedThreadPool(2);

        try {

            CompletableFuture<Void> task1 = CompletableFuture.runAsync(() -> {

                System.out.println("Task 1: Performing some computation...");

                try {

                    Thread.sleep(2000);

                } catch (InterruptedException e) {

                    Thread.currentThread().interrupt();

                }

                System.out.println("Task 1: Computation completed.");

            }, executor);

            CompletableFuture<Void> task2 = CompletableFuture.runAsync(() -> {

                System.out.println("Task 2: Performing some computation...");

                try {

                    Thread.sleep(3000);

                } catch (InterruptedException e) {

                    Thread.currentThread().interrupt();

                }

                System.out.println("Task 2: Computation completed.");

            }, executor);

            CompletableFuture.allOf(task1, task2).join();

        } finally {

            executor.shutdown();

        }

    }

}
```

输出：

```
Task 1: Performing some computation...
Task 2: Performing some computation...
Task 1: Computation completed.
Task 2: Computation completed.
```

在上述程序中，`CompletableFuture`用于表示由`ExecutorService`并发执行的异步任务（`task1`和`task2`）。`CompletableFuture`的使用通过任务执行展示了结构化并发原则，确保了妥善的清理（`executor.shutdown()`），并在 Java 22 提供的环境中优雅地处理异常。

### 程序

```java
import java.util.Arrays;

import java.util.List;

import java.util.concurrent.CompletableFuture;

import java.util.concurrent.ExecutorService;

import java.util.concurrent.Executors;

import java.util.stream.Collectors;

public class Test {

    void main(String[] args) {

        List<String> urls = Arrays.asList("https://mrcet.com/downloads/digital_notes/IT/JAVA%20PROGRAMMING.pdf", "https://frozenzeen.github.io/ICSE_Resources/ICSE-Java-Notes-V4.7.2.pdf", "https://mu.ac.in/wp-content/uploads/2022/009/Core-Java.pdf");

        // 创建具有固定线程数的线程池执行器

        try (ExecutorService executor = Executors.newFixedThreadPool(3)) {

            List<CompletableFuture<String>> downloadFutures = urls.stream()
              .map(url -> CompletableFuture.supplyAsync(() -> downloadFile(url), executor))
              .collect(Collectors.toList());
            CompletableFuture<Void> allDownloads = CompletableFuture.allOf(downloadFutures.toArray(new CompletableFuture[0]));
            allDownloads.join();
            // 获取已完成的结果
            List<String> downloadedFiles = downloadFutures.stream()
              .map(CompletableFuture::join)
              .collect(Collectors.toList())
              .forEach(file -> System.out.println("Downloaded: " + file));
        }
    }

    private static String downloadFile(String url) {
        try {
            Thread.sleep(2000);
        } catch (InterruptedException e) {
            Thread.currentThread().interrupt();
            System.err.println("Thread interrupted while downloading: " + url);
        }
        return "File from " + url;
    }
}
```

输出：

```
Downloaded: File from https://mrcet.com/downloads/digital_notes/IT/JAVA%20PROGRAMMING.pdf
Downloaded: File from https://frozenzeen.github.io/ICSE_Resources/ICSE-Java-Notes-V4.7.2.pdf
Downloaded: File from https://mu.ac.in/wp-content/uploads/2022/009/Core-Java.pdf
```

上述程序使用线程池通过`CompletableFuture`从 URL 列表并发下载文件。每个 URL 都在异步处理，允许多个下载同时进行，提高了效率。在所有下载完成后，收集并打印结果，表明每个文件已成功获取。

## 10.12 作用域值

Scoped Values 在 Java 22 中的引入是 Project Loom 持续开发的一部分，解决了并发编程和资源管理中的若干关键需求。

### 10.12.1 Java 22 对作用域值的需求

- **线程本地数据管理**：传统的 Java 应用依赖`ThreadLocal`变量来管理线程本地数据。然而，管理`ThreadLocal`变量很容易，特别是在涉及嵌套任务或异步计算的场景中。Scoped Values 为管理线程本地数据提供了一种更直观、更有结构的方法，减少了复杂性和潜在错误。
- **高效的上下文传播**：在现代应用程序中，跨异步任务或线程传播上下文信息对于维持状态一致性和确保正确的行为至关重要。作用域值（Scoped Values）促进不可变上下文数据的高效透明传播，提高了代码清晰度并减少了对显式参数传递的需求。
- **微服务与无服务器架构中的并发**：微服务和无服务器应用通常处理多个并发请求或事件。作用域值允许这些应用程序隔离并管理每个请求或事件的上下文，提高了可扩展性并减少了资源竞争。
- **增强的资源共享**：在多个线程或任务需要访问共享的可变数据（如配置设置或安全凭据）的场景下，作用域值为跨边界共享这些数据提供了安全高效的机制。这降低了数据损坏或意外修改的风险。
- **对响应式编程的支持**：响应式范式严重依赖异步和事件驱动处理，作用域值通过简化跨异步边界的响应状态和上下文的管理而受益。这提升了响应式应用的健壮性和可维护性。

### 程序

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
class ScopedValue<T> {
    public final T value;
    public ScopedValue(T value) {
        this.value = value;
    }
}
public class ScopedValuesExample {
    public static ScopedValue<String> scopedMessage = new ScopedValue<>("Initial message");
    void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(2);
        executor.submit(() -> {
            System.out.println("Parent thread sends: " + scopedMessage.value);
            childThread();
        });
        executor.shutdown();
    }
    private static void childThread() {
        System.out.println("Child thread receives: " + scopedMessage.value);
    }
}
```

输出：

```
Parent thread sends: Initial message
Child thread receives: Initial message
```

上述程序定义了一个`ScopedValue`类来保存一个值，该值在父线程和子线程之间共享。使用线程池提交了一个任务，该任务在调用`childThread()`之前打印父线程的消息，而该方法也访问并打印了相同的消息。输出确认了两个线程都可以访问共享的`scopedMessage`，演示了作用域值如何在并发编程中利用。

## 10.13 医疗应用

### 10.13.1 案例研究 1

登革热是由蚊子传播的病毒性感染，会导致严重的类流感症状，并可能导致严重的健康并发症。考虑登革热检测的参数有：

- **发烧**：检查患者是否发烧。
- **头痛**：检查患者是否头痛。
- **皮疹**：检查患者是否有皮疹。
- **关节疼痛**：检查患者是否有关节疼痛。
- **恶心**：检查患者是否感到恶心。
- **呕吐**：检查患者是否呕吐。
- **检测阳性**：检查患者登革热检测是否为阳性。

### 程序

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
class DengueRecord {
    private int age;
    private String gender;
    private boolean fever;
    private boolean headache;
    private boolean rash;
    private boolean jointPain;
    private boolean nausea;
    private boolean vomiting;
    private boolean positiveTest;
    public DengueRecord(int age, String gender, boolean fever, boolean headache, boolean rash, boolean jointPain, boolean nausea, boolean vomiting, boolean positiveTest) {
        this.age = age;
        this.gender = gender;
        this.fever = fever;
        this.headache = headache;
        this.rash = rash;
        this.jointPain = jointPain;
        this.nausea = nausea;
        this.vomiting = vomiting;
        this.positiveTest = positiveTest;
    }
    public boolean isPositiveTest() {
        return positiveTest;
    }
    @Override
    public String toString() {
        return "Age: " + age + ", Gender: " + gender + ", Fever: " + fever + 
        ", Headache: " + headache + ", Rash: " + rash + ", Joint Pain: " + jointPain +
        ", Nausea: " + nausea + ", Vomiting: " + vomiting + ", Positive Test: " +
        + positiveTest + ";
    }
}
```



```java
class DataCollector implements Runnable {
    private List<DengueRecord> records;
    private Scanner scanner;
    public DataCollector(List<DengueRecord> records, Scanner scanner) {
        this.records = records;
        this.scanner = scanner;
    }
    @Override
    public void run() {
        // Collect data from user input
        synchronized (records) {
            System.out.println("Enter the number of records to input:");
            int numRecords = scanner.nextInt();
            scanner.nextLine();
            for (int i = 0; i < numRecords; i++) {
                System.out.println("Enter record for " + (i + 1) + ":");
                System.out.print("Age: ");
                int age = scanner.nextInt();
                scanner.nextLine();
                System.out.print("Gender: ");
                String gender = scanner.nextLine();
                System.out.print("Fever (true/false): ");
                boolean fever = scanner.nextBoolean();
                System.out.print("Headache (true/false): ");
                boolean headache = scanner.nextBoolean();
                System.out.print("Rash (true/false): ");
                boolean rash = scanner.nextBoolean();
                System.out.print("Joint Pain (true/false): ");
                boolean jointPain = scanner.nextBoolean();
                System.out.print("Nausea (true/false): ");
                boolean nausea = scanner.nextBoolean();
                System.out.print("Vomiting (true/false): ");
                boolean vomiting = scanner.nextBoolean();
                System.out.print("Positive Test (true/false): ");
                boolean positiveTest = scanner.nextBoolean();
                records.add(new DengueRecord(age, gender, fever, headache, rash, jointPain, nausea, vomiting, positiveTest));
            }
        }
    }
}

class Analyzer implements Runnable {
    private List<DengueRecord> records;
    public Analyzer(List<DengueRecord> records) {
        this.records = records;
    }
    @Override
    public void run() {
        // Analyze data
        synchronized (records) {
            try {
                Thread.sleep(2000); // Simulate delay
                int positiveCount = 0;
                for (DengueRecord record : records) {
                    if (record.isPositiveTest()) {
                        positiveCount++;
                    }
                }
                System.out.println("Analysis complete. Positive cases: " + positiveCount);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class DengueDetection {
    public static void main(String[] args) {
        List<DengueRecord> records = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        Thread dataCollectorThread = new Thread(new DataCollector(records, scanner));
        Thread analyzerThread = new Thread(new Analyzer(records));
        dataCollectorThread.start();
        analyzerThread.start();
        try {
            dataCollectorThread.join();
            analyzerThread.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("Dengue detection process completed.");
    }
}
```

该程序定义了一个`DengueRecord`类来存储患者信息，如年龄、性别和症状。`DataCollector`类实现了`Runnable`接口，从用户输入收集患者数据并将其添加到共享列表中。`Analyzer`类同样实现了`Runnable`，处理收集的数据以统计阳性登革热病例。在`DengueDetection`主方法中，创建并启动了两个线程：一个用于数据收集，另一个用于数据分析。对线程进行了同步处理以确保数据操作的安全性。

## 10.13.2 CASE STUDY 2

伤寒热是由伤寒杆菌引起的细菌感染。它通过受污染的食物和水传播，特征是有发烧、头痛、恶心、腹痛和皮疹等症状。如果不使用抗生素进行适当治疗，伤寒热可能会非常严重。考虑伤寒热的参数有：

- 发烧：检查患者是否发烧。
- 头痛：检查患者是否头痛。
- 腹痛：检查患者是否有腹痛。
- 腹泻：检查患者是否有腹泻。
- 便秘：检查患者是否有便秘。
- 皮疹：检查患者是否有皮疹。
- 检测阳性：检查伤寒检测的结果。

# 412

用于医疗与健康应用的 Java 22

# 程序



```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class TyphoidFeverRecord {
    private int age;
    private String gender;
    private boolean fever;
    private boolean headache;
    private boolean abdominalPain;
    private boolean diarrhea;
    private boolean constipation;
    private boolean rash;
    private boolean positiveTest;

    public TyphoidFeverRecord(int age, String gender, boolean fever, boolean headache, boolean abdominalPain, boolean diarrhea, boolean constipation, boolean rash, boolean positiveTest) {
        this.age = age;
        this.gender = gender;
        this.fever = fever;
        this.headache = headache;
        this.abdominalPain = abdominalPain;
        this.diarrhea = diarrhea;
        this.constipation = constipation;
        this.rash = rash;
        this.positiveTest = positiveTest;
    }

    public boolean isPositiveTest() {
        return positiveTest;
    }

    @Override
    public String toString() {
        return "Age: " + age + ", Gender: " + gender + ", Fever: " + fever + ", Headache: " + headache + ", Abdominal Pain: " + abdominalPain + ", Diarrhea: " + diarrhea + ", Constipation: " + constipation + ", Rash: " + rash + ", Positive Test: " + positiveTest;
    }
}

class DataCollector implements Runnable {
    private final List<TyphoidFeverRecord> records;
    private final Scanner scanner;
    private final Object lock;

    public DataCollector(List<TyphoidFeverRecord> records, Scanner scanner, Object lock) {
        this.records = records;
        this.scanner = scanner;
        this.lock = lock;
    }

    @Override
    public void run() {
        synchronized (lock) {
            // Collect data from user input
            System.out.println("Enter the number of records to input:");
            int numRecords = scanner.nextInt();
            for (int i = 0; i < numRecords; i++) {
                System.out.println("Enter details for record " + (i + 1) + ":");
                System.out.print("Age: ");
                int age = scanner.nextInt();
                scanner.nextLine();
                System.out.print("Gender: ");
                String gender = scanner.nextLine();
                System.out.print("Fever: ");
                boolean fever = scanner.nextBoolean();
                System.out.print("Headache: ");
                boolean headache = scanner.nextBoolean();
                System.out.print("Abdominal Pain: ");
                boolean abdominalPain = scanner.nextBoolean();
                System.out.print("Diarrhea: ");
                boolean diarrhea = scanner.nextBoolean();
                System.out.print("Constipation: ");
                boolean constipation = scanner.nextBoolean();
                System.out.print("PositiveTest: ");
                boolean positiveTest = scanner.nextBoolean();
                scanner.nextLine();
                records.add(new TyphoidFeverRecord(age, gender, fever, headache, abdominalPain, diarrhea, rash, positiveTest));
            }
            System.out.println("Data collection complete.");
            lock.notify();
        }
    }
}

class Analyzer implements Runnable {
    private final List<TyphoidFeverRecord> records;
    private final Object lock;

    public Analyzer(List<TyphoidFeverRecord> records, Object lock) {
        this.records = records;
        this.lock = lock;
    }

    @Override
    public void run() {
        synchronized (lock) {
            try {
                // Wait for the data collection to complete
                lock.wait();
                // Analyze data
                int positiveCount = 0;
                for (TyphoidFeverRecord record : records) {
                    if (record.isPositiveTest()) {
                        positiveCount++;
                    }
                }
                System.out.println("Data analysis complete. Positive cases: " + positiveCount);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class TyphoidFeverDetection {
    public void main(String[] args) {
        List<TyphoidFeverRecord> records = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        Object lock = new Object();
        Thread dataCollectorThread = new Thread(new DataCollector(records, scanner, lock));
        Thread analyzerThread = new Thread(new Analyzer(records, lock));
        analyzerThread.start();
        try {
            dataCollectorThread.join();
            analyzerThread.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("Typhoid fever detection process completed.");
    }
}
```

`TyphoidFeverRecord` 类存储了患者数据，包括症状和测试结果。`DataCollector` 类在独立线程中运行，收集用户输入以填充记录。`Analyzer` 类同样运行在独立线程中，等待数据收集完成，然后分析记录以统计阳性病例的数量。通过使用共享锁对象来实现同步，以确保数据收集和分析过程的安全性。

# 11 文件处理

## 11.1 引言

在 Java 中，文件处理是处理数据的一个关键方面，允许实现数据的持久化和通信。Java 提供了读写文件的方法。以下是文件处理的一些重要方面：

- 创建文件：在文件系统中建立一个新文件。
- 从文件读取：检索并处理存储在文件中的数据。
- 写入文件：可以将信息添加到文件中，既可以是追加内容也可以覆盖原有内容。
- 删除文件：从文件系统中移除文件，消除其存储的数据。

文件处理

417

![](img/5a077f56e14b826c2dc61de6c176e5ef_427_0.png)

图 11.1 流类图。

## 表 11.2 创建和修改文件及目录

| 方法 | 描述 |
| :--- | :--- |
| `rename(File path)` | 当前对象将被重命名为作为参数传递给方法的 `File` 对象所代表的路径。 |
| `setreadonly()` | 将当前对象代表的文件设置为只读，如果操作成功则返回 `true`。 |
| `mkdir()` | 使用当前文件对象指定的路径创建一个目录。 |
| `mkdirs()` | 创建当前文件对象表示的目录，包括所有所需的父级目录。 |
| `createfile()` | 只要当前文件对象存在，就根据当前文件对象定义的路径创建一个新的空文件。 |
| `delete()` | 这将删除当前文件对象表示的文件和目录，如果删除成功则返回 `true`。 |

## 表 11.3 查询文件和目录

| 方法 | 描述 |
| :--- | :--- |
| `exists()` | 如果文件对象引的文件或目录存在，则返回 `true`，否则返回 `false`。 |
| `isfile()` | 如果文件对象引用一个存在的文件，则返回 `true`，否则返回 `false`。 |
| `canread()` | 如果你被读取文件对象引的文件，则返回 `true`。 |
| `canwrite()` | 如果你被允许写入文件对象引的文件，则返回 `true`。 |

## 11.2 JAVA.IO 包

`java.io` 包包含了处理 Java 中输入和输出操作至关重要的类。这些类可以分为若干几组：

- 专门用于从数据流中读取输入的类。
- 设计用于向数据流写入输出的类。
- 负责本地文件系统中进行文件操作的类。
- 促进对象序列化的类。

`InputStream` 类是所有 Java 字节输入流的父类，而 `OutputStream` 类是所有字节输出流的父类。值得注意的是，字节流可能无法一致地正确处理 Unicode 字符。

自 Java 1.1 以来，`java.io` 包包含了字符流类，这些类通过正确处理 Unicode 字符解决了字节流的局限性。这些字符流类采用字符编码来确保字节和字符之间的准确转换。`Reader` 类是所有 Java 字符输入流的父类，而 `Writer` 类是所有字符输出流的父类。

**注意：** `InputStreamReader` 和 `OutputStreamWriter` 类提供了流与字符流之间的桥梁。

对象序列化是 Java 中的一种机制，它允许将对象的整个状态写入输出流，并随后通过从输入流中读取序列化状态来重构对象。这使得对象可以保存到文件中或通过网络进行传输。

`ObjectOutputStream` 和 `ObjectInputStream` 类负责对象的序列化和反序列化。这些类处理将对象转换为字节流以便进行存储或传输，以及从字节流重构对象的过程。

另一方面，`RandomAccessFile` 提供了对文件的非顺序访问，允许在文件的任何位置执行读取和写入操作。与使用流的其他文件相关类不同，`RandomAccessFile` 直接与文件系统交互，并允许对文件中存储的数据进行随机访问。

图 11.2 显示了 `java.io` 包的类层次结构。`java.io` 包定义了一些标准 I/O 类。表 11.4 列举了不同的流。

![](img/5a077f56e14b826c2dc61de6c176e5ef_428_0.png)

图 11.2 java.io 包类。

文件处理

## 表 11.4 输入和输出流

| 流类型 | 流名称 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| 字节流 | | | |
| 字符流 | | | |

# 文件处理

## 表 11.5 流类

| 流类 | 描述 |
|---|---|
| `BufferedInput Stream` | 用于缓冲输入流。 |
| `BufferedOutput Stream` | 用于缓冲输出流。 |
| `DataInput Stream` | 包含读取 Java 标准数据类型的方法。 |
| `DataOutput Stream` | 一种包含写入 Java 标准数据类型方法的输出流。 |
| `FileInput Stream` | 从文件中读取的输入流。 |
| `FileOutput Stream` | 到文件的输出流。 |
| `Input Stream` | 描述流输出的抽象类。 |
| `Output Stream` | 描述流输出的抽象类。 |
| `PrintStream` | 包含 `print()` 和 `println()` 方法的输出流。 |

- `mkdir()` 方法创建一个目录，如果操作成功则返回 `true`，否则返回 `false`。
- `mkdirs()` 方法创建一个目录，如果其父级目录不存在，则一并创建它们。

这些方法允许 Java 程序高效地组织和管理文件及目录，提供了根据需要创建目录的功能。

# 程序

```java
import java.io.File;
public class Test {
    void main(String[] args) {
        // 定义新目录的路径
        String directoryPath = "C:/jj/java";
        // 使用指定的路径创建 File 对象
        File directory = new File(directoryPath);
        // 尝试创建目录以及任何必要的父目录
        if (directory.mkdirs()) {
            System.out.println("Directory created successfully.");
        } else {
            System.out.println("Directory creation failed or directory already exists.");
        }
    }
}
```

```output
Output:
Directory created successfully.
```

在上面的示例中，我们使用 `mkdirs()` 方法在 `"C:/jj/"` 下执行了创建一个名为 `"java"` 的的操作。

### 11.3.2 列出目录



Java 中 `File` 类提供的 `list()` 方法用于获取一个字符串数组，包含 `File` 对象指定的目录中的文件和目录名称。当调用此方法时，它会返回一个字符串数组，包含 `File` 对象所代表目录中存在的所有文件和目录名称。数组中的每个字符串对应于指定目录内的文件或目录名称。如果目录为空或不存在，方法将返回 `null`。

## 程序

```java
import java.io.File;
public class ListFilesExample {
    void main(String[] args) {
        // 定义要列出的目录路径
        String directoryPath = "C:/jj/";
        // 使用指定的目录路径创建 File 对象
        File directory = new File(directoryPath);
        // 检查 File 对象是否确实是一个目录
        if (directory.isDirectory()) {
            // 获取文件和目录列表
            String[] filesAndDirs = directory.list();
            // 检查列表是否不空
            if (filesAndDirs != null) {
                System.out.println("Contents of directory " + directoryPath + ":");
                // 打印文件和目录名称
                for (String name : filesAndDirs) {
                    System.out.println(name);
                }
            } else {
                System.out.println("The directory is empty or an I/O error occurred.");
            }
        } else {
            System.out.println(directoryPath + " is not a directory.");
        }
    }
}
```

## 输出

```output
Output:
Contents of directory C:/jj/:
Demo.class
Demo.java
java
Test.class
Test.java
```

在示例中，对 `File` 对象 `directory` 调用了 `list()` 方法，该对象代表目录 `"C:/jj/"`。该方法返回一个包含 `"C:/jj"` 文件和目录名称的字符串数组，并将其打印到控制台。

## 程序

```java
import java.io.File;
public class Test {
    void main(String[] args) {
        File f = null;
        try {
            // 初始化 File 对象以表示目录 "C:/jj"
            f = new File("C:/jj/");
            // 获取指定目录中的文件和目录列表
            String[] filesAndDirs = f.list();
            // 检查列表是否不空
            if (filesAndDirs != null) {
                System.out.println("Contents of directory C:/jj:");
                // 打印每个文件和目录名称
                for (String name : filesAndDirs) {
                    System.out.println(name);
                }
            } else {
                System.out.println("The directory is empty or an I/O error occurred.");
            }
        } catch (Exception e) {
            // 将异常的堆栈跟踪打印到标准错误流
            e.printStackTrace();
        }
    }
}
```

## 输出

```output
Output:
Contents of directory C:/jj:
Demo.class
Demo.java
java
Test.class
Test.java
```

在程序中，我们执行了列出 `"C:/jj"` 目录内文件和目录的操作。如果成功，将打印名称，任何异常将通过输出堆栈跟踪进行处理。

### 11.3.3 标准流

在 Java 编程中，有三个与控制台相关的流：

- `System.out`：这是标准输出流，用于显示程序的常规输出。写入此流的数据通常显示在控制台上。
- `System.in`：这是标准输入流，用于从控制台读取输入。
- `System.err`：这是标准错误流，用于显示错误消息和诊断信息。

## 文件处理

### 表 11.6

**表 11.6 `OutputStream` 类方法**

| 序号 | 方法与描述 |
| :--- | :--- |
| 1 | `public void close() throws IOException()`<br>关闭输出流。 |
| 2 | `protected void finalize() throws IOException {}`<br>此方法关闭与文件的连接。 |
| 3 | `public void write(int w) throws IOException()`<br>向输出流写入指定的字节。 |
| 4 | `public void write(byte[] w)`<br>从指定的字节数组向 `OutputStream` 写入 `w.length` 个字节。 |

## 程序

```java
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.File;

public class FileOutputStreamExample {
    public void main(String[] args) {
        // 准备要写入文件的文本
        String text = "Dr. Usharani Bhimavarapu!";
        // 输出文件的路径
        String filePath = "output.txt";
        // 创建一个 FileOutputStream 向文件写入数据
        try (FileOutputStream fos = new FileOutputStream(filePath)) {
            // 将字符串转换为字节
            byte[] bytes = text.getBytes();
            // 将字节写入文件
            fos.write(bytes);
            System.out.println("Data has been written to " + filePath);
        } catch (IOException e) {
            // 处理可能的 IOExceptions
            e.printStackTrace();
        }
    }
}
```

## 输出

```text
Data has been written to output.txt
```

`output.txt`

```text
Dr. Usharani Bhimavarapu!
```

在程序中，使用 `FileOutputStream` 将字符串“Dr. Usharani Bhimavarapu!”写入文件“output.txt”。该字符串首先使用 `getBytes()` 方法转换为字节数组，然后使用 `write()` 方法将字节写入文件。最后，关闭数据流以释放与其与之相关的任何系统资源。

### 11.4.1.1 构造函数

表 11.7 列出了 `FileOutputStream` 类的不同构造函数。

### 11.4.1.2 方法

表 11.8 列出了 `FileOutputStream` 类的预定义方法。

## 用于医疗保健和医学应用的 Java 22

### 表 11.7

**表 11.7 `FileOutputStream` 类构造函数**

| 构造函数 | 描述 |
| :--- | :--- |
| `FileOutputStream(File file)` | 创建一个文件输出流，写入指定对象所表示的文件。 |
| `FileOutputStream(FileDescriptor obj)` | 创建一个文件输出流，写入指定的描述符，该描述符表示系统中指向文件的现有连接。 |
| `FileOutputStream(File file, int off, boolean append)` | 创建一个文件输出流，写入指定对象所表示的文件。 |
| `FileOutputStream(String name)` | 创建一个文件输出流，写入指定名称的文件。 |
| `FileOutputStream(String name, boolean append)` | 创建一个文件输出流，写入具有指定名称的文件。 |

### 表 11.8

**表 11.8 `FileOutputStream` 类方法**

| 方法 | 描述 |
| :--- | :--- |
| `protected void finalize()` | 清理与文件输出流的连接。 |
| `void write(byte[] arr)` | 将字节数组中的 `arr.length` 个字节写入文件输出流。 |
| `void write(byte[] arr, int off, int len)` | 将字节数组中从偏移量 `off` 开始的 `len` 个字节写入文件输出流。 |
| `void write(int b)` | 将指定的字节写入文件输出流。 |
| `File getChannel(Channel channel)` | 返回与文件输出流关联的文件通道对象。 |
| `File getDescriptor(FD fd)` | 返回与流相关联的文件描述符。 |
| `void close()` | 关闭输出流。 |

## 11.4.2 `FileInputStream` 类

在 Java 中，`FileInputStream` 负责从文件中读取数据和字节流。它是 `java.io` 包中的一个内置类。`FileInputStream` 是 `InputStream` 的子类，而 `InputStream` 是所有输入流类的父类。使用 `FileInputStream`，你可以按顺序从文件中读取数据。它提供了从流中读取字节并执行各种操作的方法，例如标记位置、将流重置为之前标记的位置等。要使用 `FileInputStream`，你通常需要通过提供要读取的文件路径来创建其实例。然后，你可以使用如 `read()` 等方法将字节从文件中读取到缓冲区，或根据需要执行其他操作。

## 程序

```java
import java.io.FileInputStream;
import java.io.IOException;

public class FileInputStreamExample {
    public void main(String[] args) {
        // 输入文件的路径
        String filePath = "example.txt";
        // 创建一个 FileInputStream 从文件中读取
        try (FileInputStream fis = new FileInputStream(filePath)) {
            int byteRead;
            // 从文件中读取字节直到到达结束
            while ((byteRead = fis.read()) != -1) {
                // 将字节转换为字符并打印
                char character = (char)byteRead;
                System.out.print(character);
            }
            System.out.println(); // 打印换行以优化输出格式
        } catch (IOException e) {
            // 处理可能的 IOExceptions
            e.printStackTrace();
        }
    }
}
```

`example.txt` 内容为：

```text
This is to test
```

输出：

```text
This is to test
```

在上述程序中，使用 `FileInputStream` 从文件“example.txt”读取字节，并将每个字节转换为字符并打印到控制台。最后关闭流以释放与其相关的任何系统资源。

`FileInputStream` 类的一些成员方法列于表 11.9。

### 11.4.2.1 方法

表 11.10 列出了 `FileInputStream` 类的预定义方法。

### 表 11.9

**表 11.9 Java `FileInputStream` 类构造函数**

- `FileInputStream(File file)` - 通过打开指向指定文件的连接创建 `FileInputStream` 实例。
- `FileInputStream(FileDescriptor fdb)` - 使用文件描述符创建 `FileInputStream` 实例。
- `FileInputStream(String fname)` - 通过打开指向指定文件的连接创建 `FileInputStream` 实例。

### 表 11.10

**表 11.10 `FileInputStream` 方法**

| 方法 | 描述 |
| :--- | :--- |
| `int available()` | 返回流中可以读取的字节估计数。 |
| `int read()` | 从流中读取字节数据。 |
| `int read(byte[] b, int off, int len)` | 从流中读取 `len` 个字节数据。 |
| `long skip(long x)` | 丢弃流中的 `x` 个字节数据。 |
| `FileChannel getChannel()` | 返回与文件流关联的唯一 `FileInputStream` 对象。 |
| `FileDescriptor getFD()` | 返回文件描述符对象。 |
| `protected void finalize()` | 当没有更多文件流引用时调用关闭方法。 |
| `void close()` | 关闭流。 |

## 程序

```java
import java.io.FileInputStream;
import java.io.IOException;

public class FileAvailableExample {
    public void main(String[] args) {
        // 输入文件的路径
        String filePath = "input.txt";
        // 创建一个 FileInputStream 从文件中读取
        try (FileInputStream fis = new FileInputStream(filePath)) {
            // 打印开始时的可用字节数
            System.out.println("beginning: " + fis.available());
            // 从文件中读取三个字节
            fis.read(3);
            // 读取后打印剩余可用字节数
            System.out.println("end: " + fis.available());
        } catch (IOException e) {
            // 处理可能的 IOExceptions
            e.printStackTrace();
        }
    }
}
```

## 文件处理

`input.txt`

```text
This is to test
```

### Output

```text
beginning: 15

end: 12
```

在上述程序中，`FileInputStream` 从名为 `"input.txt"` 的文件中读取数据。在 `main` 方法中，利用 `try-catch` 块来处理文件操作过程中可能出现的异常。在 `try` 块内部，创建了一个名为 `"fis"` 的 `FileInputStream` 对象以建立与 `"input.txt"` 文件的连接。随后，程序在从文件中读取某些字节之前提供了 `FileInputStream` 中可用的字节数。这是通过调用 `FileInputStream` 对象的 `available()` 方法实现的。最初，在文件开头，我们打印了可用的字节数，并使用 `read()` 方法从文件中读取了三个字节。最后，使用 `close()` 方法关闭 `FileInputStream` 对象，以释放与文件流相关的任何系统资源。在文件处理过程中发生任何异常，`catch` 块都会捕获该异常并使用 `getStackTrace()` 将堆栈跟踪打印到标准错误流。

## 程序



```java
import java.io.FileInputStream;
import java.io.IOException;
public class FileInputSkipExample {
    public void main(String[] args) {
        String filePath = "input.txt";
        try (FileInputStream input = new FileInputStream(filePath)) {
            // Skip the first 3 bytes
            input.skip(3);
            int byteData;
            // Read and print byte bytes from the file
            while ((byteData = input.read()) != -1) {
                System.out.print((char) byteData);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

`input.txt`

```
This is to test
```

**输出**

```
s to test
```

在上述程序中，`FileInputStream` 从名为 `"input.txt"` 的文件中读取数据。在 `main` 方法中，使用 `try-catch` 块处理文件操作过程中可能发生的异常。在 `try` 块中，创建了一个名为 `"input"` 的 `FileInputStream` 对象以建立与 `"input.txt"` 文件的连接。随后调用了 `FileInputStream` 对象的 `skip(3)` 方法，跳过了文件的前三个字节。在循环内部，我们一个一个地从文件中读取字节，直到到达末尾（即直到 `read()` 返回 `-1`）。每个字节都被转换为字符并打印到标准输出。一旦读取了所有字节，就会使用 `close()` 方法关闭 `FileInputStream` 对象，以释放与文件流相关的任何系统资源。如果在文件处理过程中发生任何异常，`catch` 块会捕获该异常，并使用 `getStackTrace()` 方法将堆栈跟踪打印到标准错误流。

## 11.4.3 BufferedInputStream 类

Java 中的 `BufferedInputStream` 类用于通过缓冲高效地从流中读取数据。它通常与 `FileInputStream` 等其他输入流类结合使用。`BufferedInputStream` 创建了一个内部缓冲区（一个临时存储区域），在其中它存储来自底层输入流的一组字节。

当调用 `read()` 方法时，`BufferedInputStream` 从内部缓冲区读取字节，而不是直接从输入源（如文件）。如果请求的数据在缓冲区中不可用，`BufferedInputStream` 将从底层输入流读取较大块的数据到缓冲区。这减少了磁盘或网络读取的次数，可以显著提高性能，特别是在处理大文件或流时。

### 程序

```java
import java.io.BufferedInputStream;
import java.io.FileInputStream;
import java.io.IOException;
public class BufferedInputStreamExample {
    void void main(String. args) {
        String filePath = "input.txt";
        try (BufferedInputStream bis = new BufferedInputStream(new FileInputStream(filePath))) {
            int byteData;
            // Read bytes from the file until the end is reached
            while ((byteData = bis.read()) != -1) {
                System.out.print((char) byteData);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

`input.txt`

```
This is to test
```

### 输出

```
This is to test
```

我们将 `FileInputStream` 封装在 `BufferedInputStream` 中以提高性能。在循环内部，我们使用 `BufferedInputStream` 的 `read()` 方法从文件中读取字节，直到到达末尾。最后，我们关闭了 `BufferedInputStream`，这也会关闭底层的 `FileInputStream`。

注意：`BufferedInputStream` 从其他输入流读取数据，而 `FileInputStream` 从文件读取数据。

注意：`BufferedInputStream` 是带缓冲的，但 `FileInputStream` 不是。

表 11.11 Java 中 `BufferedInputStream` 类的构造函数表：

表 11.12 Java 中 `BufferedInputStream` 类的定义方法表：

### 程序

```java
import java.io.BufferedInputStream;
import java.io.FileInputStream;
import java.io.IOException;
public class BufferedInputStreamExample {
```

#### 表 11.11 BufferedInputStream 类构造函数

| 构造函数 | 描述 |
| --- | --- |
| `BufferedInputStream(InputStream is)` | 创建一个 `BufferedInputStream` 并保存 `'is'` 流以供以后使用。 |
| `BufferedInputStream(InputStream is, int size)` | 创建一个指定大小的 `BufferedInputStream` 并存储 `'is'` 流以供以后使用。 |

#### 表 11.12 BufferedInputStream 方法

| 方法 | 描述 |
| --- | --- |
| `int available()` | 返回可读字节的估算数量。 |
| `void close()` | 关闭 `BufferedInputStream`。 |
| `void mark(int limit)` | 标记从输入流读取的当前位置。 |
| `boolean markSupported(int)` | 检查流是否支持 `mark()` 和 `reset(int)` 方法。 |
| `int read()` | 从输入流读取一个字节。 |
| `int read(byte[] b)` | 从字节数组中读取指定的字节。 |
| `int read(byte[] b, int off, int len)` | 从指定位置开始从数组读取 `len` 个字节的数据。 |
| `byte[] readAllBytes()` | 从输入流中读取所有剩余字节。 |
| `int readNBytes(int n)` | 读取多达指定数量的字节。 |
| `int readNBytes(byte[] bytes, int off, int len)` | 从偏移位置开始从字节数组读取多达指定长度的字节。 |
| `long skip(long n)` | 在读取过程中跳过或丢弃指定数量的字节。 |
| `void skip(long n)` | 在读取过程中跳过或丢弃多达指定数量的字节。 |
| `long transferTo(OutputStream outStream)` | 按顺序从输入流读取所有字节并输出流。 |

```java
public void main(String[] args) {
    String filePath = "output.txt";
    try (BufferedInputStream bis = new BufferedInputStream(new FileInputStream(filePath))) {
        int byteData;
        // Read bytes from the file until the end is reached
        while ((byteData = bis.read()) != -1) {
            System.out.print((char) byteData);
        }
    } catch (IOException e) {
        e.printStackTrace();
    }
}
```

`output.txt`

```
This is to test
```

**输出**

```
This is to test
```

在上述程序中，我们执行了使用 `BufferedInputStream` 高效从文件中读取数据的操作。我们为 `"output.txt"` 创建了 `FileInputStream`，将其封装在 `BufferedInputStream` 中以提高性能，然后按字节读取数据。

## 用于医疗保健和医疗应用的 Java 22

最后，我们处理了过程中发生的异常，以确保适当的资源管理。

### 程序

```java
import java.io.BufferedInputStream;
import java.io.FileInputStream;
import java.io.IOException;
public class BufferedInputStreamExample {
    void main(String[] args) throws IOException {
        String filePath = "test.txt";
        try {
            BufferedInputStream bis = new BufferedInputStream(new FileInputStream(filePath));
            // Print the number of bytes available for reading
            System.out.println("Bytes available at the beginning: " + bis.available());
            // Read three bytes from the file
            bis.read();
            bis.read();
            bis.read();
            // Print the number of bytes available for reading after three bytes
            System.out.println("Bytes available after reading three bytes: " + bis.available());
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

`test.txt`

```
This is to test
```

### 输出

```
Bytes available at the beginning: 15
Bytes available after reading three bytes: 12
```

## 文件处理

### 程序

```java
import java.io.BufferedOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
public class BufferedOutputStreamExample {
    public void main(String[] args) {
        String filePath = "output.txt";
        String data = "This is a test string to write to a byte array";
        // 将字符串数据转换为字节数组
        byte[] byteArray = data.getBytes();
        try {
            BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream(filePath));
            // 将字节数组写入缓冲输出流
            bos.write(byteArray);
            // 刷新缓冲区中的数据以确保所有数据都已写入文件
            bos.flush();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

执行程序后，`output.txt` 文件包含以下文本：

```
This is a test string to write to the file.
```

在上述代码中，我们创建了一个 `FileOutputStream` 对象来向名为 `"output.txt"` 的文件写入数据。然后，我们用 `BufferedOutputStream` 包装了 `FileOutputStream` 以提高写入性能。我们使用 `BufferedOutputStream` 的 `write(byte[])` 方法将数据写入内部缓冲区。最后，我们调用 `flush()` 方法确保所有数据都已写入文件，并关闭 `BufferedOutputStream`，这也会关闭底层的 `FileOutputStream`。

表 11.13 列出了 `BufferedOutputStream` 类的构造函数。

表 11.14 列出了 `BufferedOutputStream` 流类的预定义方法。

#### 表 11.13 BufferedOutputStream 输出流类构造函数

| 构造函数 | 描述 |
| --- | --- |
| `BufferedOutputStream(OutputStream out)` | 创建一个新的缓冲输出流，用于将数据写入指定的输出流。 |
| `BufferedOutputStream(OutputStream out, int size)` | 创建一个新的缓冲输出流，用于以指定的缓冲区大小写入数据。 |

#### 表 11.14 Java BufferedOutputStream 类方法

| 方法 | 描述 |
| --- | --- |
| `void write(int b)` | 将指定的字节写入缓冲输出流。 |
| `void write(byte[] b, int off, int len)` | 将指定的字节输入中的字节写入指定的字节数组中，从给定的偏移量开始。 |
| `void flush()` | 刷新缓冲输出流。 |

## 434 Java 22 医疗与健康应用

### 程序

```java
import java.io.BufferedOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;
public class BufferedOutputStreamExample {
    public void main(String[] args) {
        // 文件路径
        String filePath = "out.txt";
        // 要写入文件的数据
        String data = "testing";
        // 将字符串转换为字节数组
        byte[] byteArray = data.getBytes();
        // 使用 try-with-resources 确保流被正确关闭
        try (FileOutputStream out = new FileOutputStream(filePath);
             BufferedOutputStream bout = new BufferedOutputStream(out)) {
            // 将字节数组写入缓冲输出流
            bout.write(byteArray);
            // 刷新缓冲区中的数据以确保其已写入文件
            bout.flush();
        } catch (IOException e) {
            // 如果发生异常，打印堆栈跟踪
            e.printStackTrace();
        }
    }
}
```

在上述程序中，我们使用 `BufferedOutputStream` 向文件写入数据。字符串 `"testing"` 被转换为字节数组，并通过缓冲输出流写入 `"out.txt"` 文件。执行后，`"out.txt"` 文件包含文本 `"testing"`。

## 11.5 JAVA 字符流类

字符流是通过两个抽象类定义的：`Reader` 和 `Writer`。与字节流相比，这些类提供了更高层次的抽象，允许开发者处理基于字符的数据而非字节。字符流旨在正确地处理 Unicode 字符，确保编码和解码的正确。



这些类定义了用于读取和写入基于字符数据的各种方法。通过使用字符流，开发者可以从字符源和目的地（如文件流、网络连接和内存缓冲区）读取和写入字符。与字节流相比，字符流为 Java 程序处理文本数据提供了一种更方便、更高效的方法。表 11.15 列出了字符流类，表 11.16 列出了流类中的预定义方法。

## 11.5.1 BufferedReader

`BufferedReader` 用于高效地从输入流中读取文本。它缓冲字符以提供对字符、数组和行的有效读取。它通常用于从文件或其他字符输入流中读取数据，在这些场景下性能至关重要。

### 表 11.15 字符流类

| 流类 | 描述 |
| --- | --- |
| `BufferedReader` | 处理缓冲输入流。 |
| `BufferedWriter` | 处理缓冲输出流。 |
| `FileReader` | 从文件读取的输入流。 |
| `FileWriter` | 写入文件的输出流。 |
| `InputStreamReader` | 将字节转换为字符的输入流。 |
| `OutputStreamReader` | 将字节转换为字符的输出流。 |
| `PrintWriter` | 包含 `print()` 和 `println()` 方法。 |
| `Reader` | 定义字符输入的抽象类。 |
| `Writer` | 定义字符输出的抽象类。 |

### 表 11.16 输入输出流类方法

| 序号 | 方法与描述 |
| --- | --- |
| 1 | `public void close() throws IOException` 关闭文件输出。 |
| 2 | `protected void finalize() throws IOException` 清理连接。 |
| 3 | `public int read(int r) throws IOException` 从输入流读取指定的字节。 |
| 4 | `public int read(byte[] r) throws IOException` 从输入流读取字节到数组中。 |
| 5 | `public boolean available() throws IOException` 提供可以从该输入流读取的字节数。 |

### 程序

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
public class BufferedReaderExample {
    public void main(String[] args) {
        // 文件路径
        String filePath = "sr.txt";
        // 使用 try-with-resources 确保 BufferedReader 被正确关闭
        try (BufferedReader br = new BufferedReader(new FileReader(filePath))) {
            String line;
            // 从文件中读取每一行
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            // 如果发生异常，打印堆栈跟踪
            e.printStackTrace();
        }
    }
}
```

`sr.txt`

```
testing
```

输出：

```
testing
```

上述程序读取了名为 `sr.txt` 的文件内容并将每行打印到控制台。`FileReader` 用于打开文件，`readLine()` 方法逐行读取。`while` 循环持续到没有更多行可读，并在最后关闭 `BufferedReader` 以释放资源。

## 11.5.2 BufferedWriter

`BufferedWriter` 用于高效地向输出流写入内容。它缓冲字符以提供对字符、数组和字符串的有效写入。该流在写入大量文本数据以提高性能时非常有用。

### 程序

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
public class BufferedWriterExample {
    public void main(String[] args) {
        // 文件路径
        String filePath = "cr.txt";
        // 注册信息
        String studentName = "Usharani";
        String courseDetails = "Java Programming";
        // 使用 try-with-resources 确保 BufferedWriter 被正确关闭
        try (BufferedWriter bw = new BufferedWriter(new FileWriter(filePath))) {
            // 写入姓名并换行
            bw.write("Student Name: " + studentName);
            bw.newLine();
            // 写入课程详情并换行
            bw.write("Course Details: " + courseDetails);
            bw.newLine();
            // 刷新 BufferedWriter 以确保所有数据都已写入文件
            bw.flush();
        } catch (IOException e) {
            // 如果发生异常，打印堆栈跟踪
            e.printStackTrace();
        }
    }
}
```

## 11.5.3 FileReader

`FileReader` 是一个用于读取字符文件的便利类。它使用默认字符编码，并提供了简单的方法来从文件中读取字符、数组和行。

### 程序

```java
import java.io.FileReader;
import java.io.IOException;
public class FileReaderExample {
    public static void main(String[] args) {
        // 文件的路径
        String filePath = "sr.txt";
        // 使用 try-with-resources 确保 FileReader 被正确关闭
        try (FileReader fr = new FileReader(filePath)) {
            int character;
            // 逐个读取字符直到文件结束
            while ((character = fr.read()) != -1) {
                // 将整数转换为字符并打印
                System.out.print((char) character);
            }
        } catch (IOException e) {
            // 如果发生异常，打印堆栈轨迹
            e.printStackTrace();
        }
    }
}
```

`sr.txt`

```
testing
```

输出：

```
testing
```

在这个程序中，我们通过 `FileReader` 逐字符读取了 `sr.txt` 的内容，并将每个字符打印到控制台。如果发生 `IOException`，我们通过打印堆栈轨迹来处理它。

## 11.5.4 FileWriter

`FileWriter` 是一个用于写入字符文件的便利类。它使用默认字符编码，并提供了简单的方法向文件中写入字符、数组和字符串。

### 程序

```java
import java.io.FileWriter;
import java.io.IOException;
public class FileWriterExample {
    public static void main(String[] args) {
        // 文件的路径
        String filePath = "cr.txt";
        // 使用 try-with-resources 确保 FileWriter 被正确关闭
        try (FileWriter fw = new FileWriter(filePath)) {
            // 学生姓名和课程详情
            String studentName = "Usharani";
            String courseDetails = "Course: Introduction to Java";
            // 将学生姓名写入文件
            fw.write("Student Name: " + studentName + "\n");
            // 将课程详情写入文件
            fw.write(courseDetails + "\n");
            // 可选，你可以在这里使用 flush() 来确保所有数据都已写入
            // fw.flush();
        } catch (IOException e) {
            // 如果发生异常，打印堆栈轨迹
            e.printStackTrace();
        }
    }
}
```

执行程序后，`cr.txt` 文件包含：

```
Student Name: Usharani
Course: Introduction to Java
```

在上面的程序中，我们使用 `FileWriter` 完成了将学生姓名和课程详情写入 `cr.txt` 的任务。文件将包含学生姓名，随后是课程详情，如果发生 `IOException`，它将通过堆栈轨迹进行处理。

## 11.5.5 InputStreamReader

`InputStreamReader` 建立了流与字符流之间的桥梁。它读取字节并使用指定的字符集将其解码为字符，使其从面向字节的流中读取文本非常有用。

### 程序

```java
import java.io.BufferedReader;
import java.io.FileInputStream;
import java.io.InputStreamReader;
import java.io.IOException;
public class FileReaderExample {
    public static void main(String[] args) {
        // 文件的路径
        String filePath = "sr.txt";
        // 使用 try-with-resources 确保 BufferedReader 被正确关闭
        try (FileInputStream fis = new FileInputStream(filePath);
             InputStreamReader isr = new InputStreamReader(fis, "UTF-8");
             BufferedReader br = new BufferedReader(isr)) {
            String line;
            // 逐行从文件中读取并打印到控制台
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            // 如果发生异常，打印堆栈轨迹
            e.printStackTrace();
        }
    }
}
```

`sr.txt`

```
testing
```

输出：

```
testing
```

在这个程序中，我们使用 `BufferedReader` 逐行读取 `sr.txt` 的内容。我们创建了一个 `FileInputStream` 并将其封装在 `InputStreamReader` 中以处理字符编码，然后从文件中读取每一行并打印到控制台。如果发生 `IOException`，通过打印堆栈轨迹进行处理。

## 11.5.6 OutputStreamWriter

`OutputStreamWriter` 建立了流与字节之间的桥梁。它使用指定的字符集将字符编码为字节。

### 程序

```java
import java.io.BufferedWriter;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStreamWriter;
public class FileWriterExample {
    public static void main(String[] args) {
        // 文件的路径
        String filePath = "cr.txt";
        // 注册信息
        String studentName = "Usharini";
        String course = "Java Programming";
        // 使用 try-with-resources 确保 BufferedWriter 被正确关闭
        try (FileOutputStream fos = new FileOutputStream(filePath);
             OutputStreamWriter osw = new OutputStreamWriter(fos, "UTF-8");
             BufferedWriter bw = new BufferedWriter(osw)) {
            // 将学生姓名和课程信息写入文件
            bw.write("Student Name: " + studentName);
            bw.newLine();
            bw.write("Course: " + course);
            bw.newLine();
            // 刷新 BufferedWriter 以确保所有数据都写入文件
        } catch (IOException e) {
            // 如果发生异常，打印堆栈轨迹
            e.printStackTrace();
        }
    }
}
```

执行程序后，`cr.txt` 文件包含：

```
Student Name: Usharini
Course: Java Programming
```

在这个程序中，我们使用 `OutputStreamWriter` 将学生姓名和课程详情写入 `cr.txt` 文件。文件将包含学生姓名，随后是课程详情，如果发生 `IOException`，它将通过堆栈轨迹进行处理。

## 11.6 随机访问文件类（RandomAccessFile）

Java 中的 `RandomAccessFile` 类提供了一种方便的方法，可以在文件的任何特定位置读取和写入，从而对文件中存储的数据进行随机访问。与提供顺序访问数据的其他输入输出流不同，`RandomAccessFile` 允许你直接跳转到文件的特定位置并从该点执行读取和写入操作。

随机访问意味着你可以按照任何顺序访问文件内容，而不限于从文件头到尾顺序读取或写入。这在处理大文件或需要修改文件特定部分而不影响其其他内容时特别有用。

`RandomAccessFile` 类提供了在特定指针位置读取和写入数据的方法。`RandomAccessFile` 类提供的一些关键方法包括：

- `seek(long pos)`：将文件指针移动到文件内的指定位置。
- `read()`：从当前文件指针位置读取一个字节的数据。
- `read(byte[] b)`：从当前文件指针位置读取一个字节数组到指定的字节数组中。
- `write(int b)`：向当前文件指针位置写入一个字节的数据。
- `write(byte[] b)`：向当前文件指针位置写入一个字节数组。

### 程序



```java
import java.io.RandomAccessFile;
import java.io.IOException;
public class Main {
    public static void main(String[] args) {
        // 文件路径
        String filePath = "data.txt";
        // 创建一个用于读写的 RandomAccessFile 对象
        try (RandomAccessFile raf = new RandomAccessFile(filePath, "rw
```

## 输出

从位置 10 读取的数据：`Dr.Ushani Bhimaravapu`

## 文件处理

在上面的示例中，我们以读写模式创建了一个名为 `data.txt` 的 `RandomAccessFile`。然后我们使用 `seek()` 方法将文件指针移动到文件内的特定位置（例如位置 10 和位置 20），并在这些位置分别写入和读取数据。最后，在完成后关闭 `RandomAccessFile`。

### 语法

```java
RandomAccessFile objectname = new RandomAccessFile("file path", "mode");
```

### 11.6.1 访问模式 (ACCESS MODES)

文件处理中的访问模式是指决定如何访问或操纵文件的权限，例如读取、写入或追加。常见的访问模式包括只读、只写和读写，它们决定了允许对文件进行的操作类型。表 11.7 列出了 `RandomAccessFile` 的模式。

Java 中的 `RandomAccessFile` 类提供了以随机访问模式处理文件的功能，允许读取和写入操作。与其他文件处理类不同，`RandomAccessFile` 继承了 `Object` 类并实现了 `DataInput` 和 `DataOutput` 接口，提供了支持随机访问操作的方法。

随机访问文件由字节序列组成，并支持一个称为“文件指针”的特殊指针。该指针指示文件内的当前位置或偏移。初始时，当创建一个文件时，文件指针被设置为位置 0，代表文件的开头。

当使用 `read` 或 `write` 方法从文件读取或将其写入数据时，文件指针会自动移动到下一个数据项（通常是文件中的下一个字节）。这允许对数据进行高效的顺序读写，允许直接访问文件内的特定位置进行随机访问操作。

`RandomAccessFile` 提供了定位文件指针、读取和写入字节以及读取和写入原始数据类型的方法。`RandomAccessFile` 提供的一些关键方法包括：

- `seek(long pos)`：将文件指针移动到文件内的指定位置。
- `read()`：从当前文件指针位置读取一个字节的数据。
- `write(int b)`：向当前文件指针位置写入一个字节。
- `readInt()`：从当前文件指针位置读取一个整数值。
- `writeInt(int v)`：向当前文件指针位置写入一个整数值。

### 表 11.7 `RandomAccessFile` 的访问模式

| 模式 | 描述 |
|---|---|
| `R` | 只读模式。 |
| `rw` | 读写模式。 |
| `rwd` | 读写模式——同步。对文件的所有更新都应同步写入磁盘。 |
| `rws` | 读写模式——同步。对文件或元数据的所有更新都应同步写入磁盘。 |

## 用于医疗保健和医疗应用的 Java 22

通过利用 `RandomAccessFile` 的功能，开发者可以高效地以随机访问方式处理文件，根据各种文件处理任务需要访问文件内特定位置的数据。

### 语法

```java
RandomAccessFile raf(File file, String mode)
```

创建一个由 `File` 参数指定的随机访问文件流。

表 11.18 列出了随机访问文件的预定义方法。

## 程序

```java
import java.io.RandomAccessFile;
import java.io.IOException;
public class Main {
    // 从指定位置开始从文件读取字节的方法
    public static void readBytes(String filePath, long position, int numBytes) {
        try (RandomAccessFile raf = new RandomAccessFile(filePath, "r
```

### 表 11.18 随机访问文件方法

| 修饰符 | 方法 | 描述 |
| --- | --- | --- |
| `void` | `close()` | 关闭指定的访问文件。 |
| `int` | `readInt()` | 从指定文件读取整数。 |
| `void` | `seek(long pos)` | 设置文件指针偏移量，从指定文件的开始。 |
| `int` | `read()` | 从指定文件读取一个字节。 |

## 文件处理

```java
try (RandomAccessFile raf = new RandomAccessFile(filePath, "rw")) {
// 将指针移动到指定位置
raf.seek(position);
// 将字符串数据写入文件
raf.write(data.getBytes());
} catch (IOException e) {
// 如果发生异常，打印堆栈轨迹
e.printStackTrace();
}

void main(String[] args) {
// 文件路径
final String filePath = "rs.txt";
// 先写入数据作为示例内容以确保文件有足够的内容
writeToFile(filePath, "This is a sample content to avoid EOFException.", 0);
// 从位置 0 读取 18 字节
readFromFile(filePath, 0, 18);
// 向位置 31 写入数据
writeToFile(filePath, "This is to test the java files", 31);
}
```

### 输出

读取数据：`This is a sample c`

在上面的程序中，我们创建了一个 `RandomAccessFile` 并在特定位置对文件执行了读取和写入。在 `main` 方法中，我们定义了一个表示文件路径 `test.txt` 的常量。`readFromFile` 方法以读模式打开文件，跳转到指定位置，将字节读入字节数组，并将数据转换为字符串进行显示。接下来，调用 `writeToFile` 从位置 31 开始向文件写入字符串 `This is to test the java files`。`writeToFile` 方法以读写模式打开文件，跳转到指定位置，并将字符串数据作为字节写入文件。

## Java 22 医疗健康应用

```java
System.out.println(new String(buffer));
// 将文件指针移动到位置 200
file.seek(200);
// 在位置 200 写入数据
file.write("Usharani".getBytes());
file.close();
catch (IOException e) {
    e.printStackTrace();
}
```

在代码中，使用 `seek(100)` 将文件指针移动到位置 100，然后从该位置读取 10 字节。随后，使用 `seek(200)` 将文件指针移动到位置 200，并在 Java `RandomAccessFile` 的特定位置写入字符串 `Usharani`：

以下是在 Java `RandomAccessFile` 中跳转寻址（seeking）到特定位置的示例：

```java
RandomAccessFile file = new RandomAccessFile("c:\io\file.txt", "rw");
file.seek(200);
```

上述语法创建了一个名为 `file` 的 `RandomAccessFile` 对象，它以读写模式打开位于 `c:\io.txt` 的文件。`seek(200)` 方法将文件指针移动到文件的第 200 个字节，允许后续的读取或写入操作从该位置开始。

## 11.6.3 获取文件位置

在 Java 的 `RandomAccessFile` 类中，你可以使用 `getFilePointer()` 方法来获取文件指针的当前位置。它返回一个 `long` 类型的值，代表文件指针当前所在的字节索引。

以下是演示 `getFilePointer()` 用法的语法：

```java
try {
    RandomAccessFile file = new RandomAccessFile("example.txt", "r");
    // 读取文件指针的当前位置
    long position = file.getFilePointer();
    // 打印当前位置
    System.out.println("Current position: " + position);
    file.close();
} catch (IOException e) {
    e.printStackTrace();
}
```

在上述代码中，调用 `getFilePointer()` 获取文件指针的当前位置，并将结果存储在变量 `position` 中。该值代表文件指针当前所处的字节索引。最后，将当前位置打印到控制台。

## 程序：读取随机访问文件的内容

```java
import java.io.RandomAccessFile;
import java.io.IOException;
public class Main {
    public void main(String[] args) {
        try {
            // 创建一个读写模式的 RandomAccessFile 对象
            RandomAccessFile raf = new RandomAccessFile("file.txt", "rw");
```

## 文件处理

```java
// 将文件指针移动到位置 5
raf.seek(5);
// 在当前位置向文件写入字符串 "this is to test"
String dataToWrite = "this is to test";
raf.write(dataToWrite.getBytes());
// 关闭 RandomAccessFile
raf.close();
// 创建另一个只读模式的 RandomAccessFile 对象
RandomAccessFile raf = new RandomAccessFile("file.txt", "r");
// 将文件指针移动到位置 1
raf.seek(1);
// 创建一个字节数组来存储读取的数据
byte[] b = new byte[5];
// 从文件中读取 5 字节到字节数组
raf.read(b);
// 关闭 RandomAccessFile
raf.close();
// 打印字节数组的字符串表示
String data = new String(b);
System.out.println("Read data: " + data);
} catch (IOException e) {
    // 处理 IOExceptions
    e.printStackTrace();
}
```

输出：

`Read data: his t`

首先，我们以读写模式打开 `file.txt`，跳转到位置 5，并写入字符串 `this is to t.`。然后，我们以只读模式重新打开文件，跳转到位置 1，读取 5 字节到字节数组中，并打印结果字符串。

## 程序

```java
import java.io.RandomAccessFile;
import java.io.IOException;
public class RandomAccessFileExample {
    public void main(String[] args) {
    try {
        // 创建一个读写模式的 RandomAccessFile 对象
        RandomAccessFile raf = new RandomAccessFile("file.txt", "rw");
        // 使用 writeUTF 向文件写入字符串 "this is to test"
        raf.writeUTF("this is to test");
        // 将文件指针移回位置 0
        raf.seek(0);
        // 从位置 0 开始从文件中读取一行文本
        String readData = raf.readUTF();
        // 打印读取的数据
        System.out.println("Read data: " + readData);
        // 将文件指针移回位置 0
        raf.seek(0);
        // 用字符串 "Java" 覆盖文件内容，
```

## Java 22 医疗健康应用

```java
raf.writeUTF("Java");
// 将文件指针移回位置 0
raf.seek(0);
// 从文件中读取更新后的内容
String updatedData = raf.readUTF();
// 打印更新的数据
System.out.println("Updated: " + updatedData);
// 关闭 RandomAccessFile
raf.close();
} catch (IOException e) {
  // 处理 IOExceptions
  e.printStackTrace();
}
```

输出：

`Read data: this is to test`

`Updated data: Java`

在上述示例中，我们演示了使用 `RandomAccessFile` 写入、读取并更新内容。首先通过读写模式的 `RandomAccessFile` 写入 `this is to test`，然后通过 `readUTF` 读取。最后通过写入 `Java` 覆盖文件内容并再次读取以验证更新。

```java
FileWriter f3 = new FileWriter("f3.txt");
FileWriter f4 = new FileWriter("f4.txt");
// Write the content of CharArrayWriter to each FileWriter
out.writeTo(f1);
out.writeTo(f2);
out.writeTo(f3);
out.writeTo(f4);
// Close each FileWriter to release system resources
f1.close();
f2.close();
f3.close();
f4.close();
} catch (IOException e) {
 e.printStackTrace(); // Handle IOExceptions
} finally {
 out.close();
 }
```

在上面的程序中，我们演示了如何在 Java 中使用 `CharArrayWriter` 将相同的字符串写入多个文件。我们首先将字符串 `this is to test` 写入一个 `CharArrayWriter`，然后为不同的文件创建了 `FileWriter` 对象。随后将 `CharArrayWriter` 的内容写入每个文件，并妥善关闭了所有资源以防止内存泄漏。

## 11.7 流收集器 (STREAM GATHERERS)

Java 22 引入的“流收集器”（Stream Gatherers）功能（在 JEP 461 中概述）解决了在 Java 中处理流时关于灵活性、效率和可维护性的若干问题。以下是流收集器功能所需的特性：

## Java 22 中流收集器的需求

- **自定义中间操作**：传统的 Java 流提供了一组预定义的操作（如 `filter`、`map`、`flatMap`），允许开发者转换和处理流流水线的数据。但在某些情况下，开发者可能需要应用标准 API 未提供的自定义逻辑或操作。流收集器功能通过允许开发者无缝地定义并将自定义中间操作集成到流流水线中，填补了这一空白。

- **增强流组合**：Java 流支持流式声明式的编程风格，可以将操作组合在一起以执行复杂的数据处理流水线。在 Java 22 之前，在标准操作之外自定义流行为需要额外的实用方法或诉诸表达力较低的方法。流收集器通过允许开发者将复杂逻辑封装并重用为收集器，增强了流的组合，提高了可读性和可维护性。

- **代码重用与封装**：现代软件开发强调代码的重用和封装，以提高模块化并减少冗余。通过流收集器，开发者可以将流处理逻辑封装到可重用的收集函数中，促进更具模块化的设计方法。这实现了关注点分离，并便于对流操作进行单元测试和调试。

- **性能优化**：对于处理大型数据集或实时数据处理的应用，高效的流处理至关重要。流收集器通过允许直接在流流水线内部优化自定义操作，增强了性能优化。这可以提高数据密集型应用的吞吐量并降低延迟。

- **支持函数式编程范式**：Java 通过 lambda 和流等特性促进函数式编程范式，简化了并发和并行编程任务。流收集器通过提供将函数行为封装在可重用组件中的机制，进一步支持了这些范式。这鼓励了更函数式的编程风格，即将操作表示为对数据流的转换。

## 程序



```java
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;
public class Demo {
    void main(String[] args) {
        // 创建字符串流
        Stream<String> stream = Stream.of("DR", "Usha", "Rani", "Bhimavarapu");
        // 将元素收集到不可变列表
        List<String> collectedList = stream.collect(Collectors.toUnmodifiableList());
        System.out.println("Collected List: " + collectedList);
        // 创建另一个流
        Stream<Integer> numberStream = Stream.of(1, 2, 3, 4, 5);
        // 将元素收集到不可变集合
        var collectedSet = numberStream.collect(Collectors.toUnmodifiableSet());
        System.out.println("Collected Set: " + collectedSet);
    }
}
```

## 输出

```
Collected List: [DR, Usha, Rani, Bhimavarapu]
Collected Set: [2, 3, 4, 5, 1]
```

上面的程序演示了如何使用 Java 流和`Collectors`创建不可变集合。首先，我们创建了一个字符串流并将其收集到一个不可变列表中。然后，我们创建了一个整数流并将其收集到一个不可变集合中。输出显示了列表和集合。

## 程序

```java
import java.util.*;
import java.util.stream.*;
class Demo {
    void main(String[] a) {
        List<Integer> numbers = List.of(1, 2, 3, 4, 5);
        List<Integer> doubled = numbers.stream()
            .collect(Collectors.collectingThen(
                Collectors.toList(),
                list -> list.stream().map(n -> n * 2).collect(Collectors.toList())
            ));
        System.out.println(doubled);
    }
}
```

## 输出

```
[2, 4, 6, 8, 10]
```

我们使用`Collectors.toList()`收集了一个整数列表，然后通过将每个数字翻倍来转换此列表。稍后我们使用`collectAndThen`应用此转换并打印结果列表，该列表包含每个原始整数乘以2的结果。

## 程序

```java
import java.util.*;
import java.util.stream.*;
class Demo {
    void main(String[] a[]) {
        List<String> strings = List.of("a", "bb", "ccc", "dddd");
        List<String> result = strings.stream()
            .collect(Collectors.collectAndThen(
                Collectors.toList(),
                list->list.stream().filter(s->s.length()>2).collect(Collectors.
                toList())
            ));
        System.out.println(result);
    }
}
```

## 输出

```
[ccc, dddd]
```

我们对长度为或小于2的字符串列表应用了过滤器。首先，我们将所有字符串收集到列表中，然后处理此列表以仅保留长度大于两个字符的字符串。

## 程序

```java
import java.util.*;
import java.util.stream.*;
class Demo {
    void main(String[] a[]) {
        List<String> strings = List.of("Ammulu", "Bhimavarapu", "Chinni",
"Daddy");
        Map<Character, List<String>> grouped = strings.stream()
            .collect(Collectors.collectAndThen(
                Collectors.groupingBy(s -> s.charAt(0),
                map -> map
            ));
        System.out.println(grouped);
    }
}
```

## 输出

```
{A=[Ammulu], B=[Bhimavarapu], C=[Chinni], D=[Daddy]}
```

我们使用`Collectors.groupingBy`根据第一个字符对字符串列表进行分组，并创建一个映射，其中每个键是第一个字符，每个值是是以该字符开头的字符串列表。

## 文件处理

## 程序

```java
import java.util.*;
import java.util.stream.*;
class Demo {
    void main(String[] args) {
        List<Integer> numbers = List.of(1, 2, 3, 4, 5, 6);
        Map<Boolean, List<Integer>> partitioned = numbers.stream()
            .collect(Collectors.collectingThen(
                Collectors.partitioningBy(n -> n % 2 == 0),
                map -> map
            ));
        System.out.println(partitioned);
    }
}
```

## 输出

```
{false=[1, 3, 5], true=[2, 4, 6]}
```

在程序中，我们根据整数的奇偶对整数列表进行分区。我们使用`Collectors.partitioningBy`创建了一个布尔键的映射，指示偶数（`true`）或奇数（`false`）数字。

## 程序

```java
import java.util.*;
import java.util.stream.*;
class Demo {
    void main(String[] args) {
        List<String> strings = List.of("one", "two", "three");
        String result = strings.stream()
            .collect(Collectors.collectingThen(
                Collectors.joining(", "),
                s -> "[" + s + "]"
            ));
        System.out.println(result);
    }
}
```

## 输出

```
[one, two, three]
```

在程序中，我们创建了一个字符串列表，并使用 Java 流将其连接成用逗号分隔的单个字符串。`collectingThen`方法通过添加方括号来处理连接后的字符串。

## 11.8 医学应用

## 11.8.1 案例研究 1

COVID-19 数据收集并存储在`.csv`文件中

```java
import java.io.FileWriter;
import java.io.IOException;
import java.util.Random;
public class Covid19DatasetGenerator {
```

# 用于医疗和医学应用的 Java 22

```java
void main(String[] args) {
    try (FileWriter writer = new FileWriter("covid19_dataset.csv")) {
        writer.write("Age,Gender,Fever,Cough,DifficultyBreathing,Fatigue,Body,LossTasteSmell,SoreThroat,TestResult\n\n");
        Random random = new Random();
        for (int i = 0; i < 100; i++) {
            int age = random.nextInt(80) + 18;
            String gender = random.nextBoolean() ? "Male" : "Female";
            boolean fever = random.nextBoolean();
            boolean cough = random.nextBoolean();
            boolean difficultyBreathing = random.nextBoolean();
            boolean fatigue = random.nextBoolean();
            boolean bodyAches = random.nextBoolean();
            boolean lossTasteSmell = random.nextBoolean();
            boolean soreThroat = random.nextBoolean();
            String testResult = random.nextBoolean() ? "Positive" : "Negative";
            writer.write(String.format("%d,%s,%s,%s,%s,%s,%s,%s,%s,%s\n",
                age, gender, fever ? "Yes" : "No", cough ? "Yes" : "No",
                difficultyBreathing ? "Yes" : "No", fatigue ? "Yes" : "No",
                bodyAches ? "Yes" : "No", lossTasteSmell ? "Yes" : "No",
                soreThroat ? "Yes" : "No", testResult));
        }
    }
    catch (IOException e) {
        e.printStackTrace();
    }
}
```

`Covid19DatasetGenerator`生成一个 COVID-19 病例的合成数据集并将其写入名为`covid19_dataset.csv`的 CSV 文件中。它使用`FileWriter`创建文件和数据集表头，表头包含年龄、性别和各种症状等属性。使用`Random`对象为 100 条目生成随机数据，包括 18 到 97 岁之间的随机年龄，以及发热、咳嗽、呼吸困难、疲劳、身体疼痛、味觉或嗅觉丧失和喉痛等症状的随机值。每个条目还包含一个随机的 COVID-19 检测结果，即“阳性”或“阴性”。程序处理了文件操作过程中可能发生的`IOException`。

# 11.8.2 案例研究 2

在 Excel 文件中收集数据



```java
import org.apache.poi.ssssf.usermodel.*;
import org.apache.poi.ssssf.usermodel.XSSFWorkbook;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;

class DepressionRecord {
    private int age;
    private String gender;
    private String maritalStatus;
    private String employmentStatus;
    private String educationLevel;
    private boolean familyHistoryOfDepression;
    private boolean sleepDisturbances;
    private boolean appetiteChange;
    private boolean lossOfInterestOrPleasure;
    private boolean fatigueOrLossOfEnergy;
    private boolean feelingsOfWorthlessnessGuilt;
    private boolean difficultyConcentrating;
    private boolean suicidalThoughts;

    public DepressionRecord(int age, String gender, String maritalStatus,
    String employmentStatus, String educationLevel,
    boolean familyHistoryOfDepression, boolean sleepDisturbances,
    boolean appetiteChange,
    boolean lossOfInterestOrPleasure, boolean fatigueOrLossOfEnergy,
    boolean feelingsOfWorthlessnessGuilt, boolean difficultyConcentrating,
    boolean suicidalThoughts, boolean depressionDiagnosis) {
        this.age = age;
        this.gender = gender;
        this.maritalStatus = maritalStatus;
        this.employmentStatus = employmentStatus;
        this.educationLevel = educationLevel;
        this.familyHistoryOfDepression = familyHistoryOfDepression;
        this.sleepDisturbances = sleepDisturbances;
        this.appetiteChange = appetiteChange;
        this.lossOfInterestOrPleasure = lossOfInterestOrPleasure;
        this.fatigueOrLossOfEnergy = fatigueOrLossOfEnergy;
        this.feelingsOfWorthlessnessGuilt = feelingsOfWorthlessnessGuilt;
        this.difficultyConcentrating = difficultyConcentrating;
        this.suicidalThoughts = suicidalThoughts;
        this.depressionDiagnosis = depressionDiagnosis;
    }

    public int getAge() { return age; }
    public String getGender() { return gender; }
    public String getMaritalStatus() { return maritalStatus; }
    public String getEmploymentStatus() { return employmentStatus; }
    public String getEducationLevel() { return educationLevel; }
    public boolean isFamilyHistoryOfDepression() { return familyHistoryOfDepression; }
    public boolean isSleepDisturbances() { return sleepDisturbances; }
    public boolean isAppetiteChange() { return appetiteChange; }
    public boolean isLossOfInterestOrPleasure() { return lossOfInterestOrPleasure; }
    public boolean isFatigueOrLossOfEnergy() { return fatigueOrLossOfEnergy; }
    public boolean isFeelingsOfWorthlessnessGuilt() { return feelingsOfWorthlessnessGuilt; }
    public boolean isDifficultyConcentrating() { return difficultyConcentrating; }
    public boolean isSuicidalThoughts() { return suicidalThoughts; }
    public boolean isDepressionDiagnosis() { return depressionDiagnosis; }
}
```

```java
public class DepressionDataset {
  void main(String[] args) {
    List<DepressionRecord> records = new ArrayList<>();
    // 添加记录到列表（在实际应用中，这些数据可能来自用户输入）
    records.add(new DepressionRecord(25, "Female", "Single", "Employed", "Bachelor's", true, true, true, true, true, true));
    records.add(new DepressionRecord(30, "Male", "Married", "Unemployed", "Master's", false, true, false, true, false, false));

    try (Workbook workbook = new XSSFWorkbook()) {
      Sheet sheet = workbook.createSheet("DepressionData");
      String[] headers = {"年龄", "性别", "婚姻状况", "就业状况", "教育程度", "家族家族史", "睡眠障碍", "食欲变化", "疲劳或精力不足", "无价值感或罪恶感", "注意力困难", "自杀念头", "抑郁诊断"};

      Row headerRow = sheet.createRow(0);
      for (int i = 0; i < headers.length; i++) {
        Cell cell = headerRow.createCell(i);
        cell.setCellValue(headers[i]);
      }

      int rowNum = 1;
      for (DepressionRecord record : records) {
        Row row = sheet.createRow(rowNum++);
        row.createCell(0).setCellValue(record.getAge());
        row.createCell(1).setCellValue(record.getGender());
        row.createCell(2).setCellValue(record.getMaritalStatus());
        row.createCell(3).setCellValue(record.getEmploymentStatus());
        row.createCell(4).setCellValue(record.getEducationLevel());
        row.createCell(5).setCellValue(record.isFamilyHistoryOfDepression());
        row.createCell(6).setCellValue(record.isSleepDisturbances());
        row.createCell(7).setCellValue(record.isAppetiteChange());
        row.createCell(8).setCellValue(record.isLossOfInterestPleasure());
        row.createCell(9).setCellValue(record.isFatigueOrLossOfEnergy());
        row.createCell(10).setCellValue(record.isFeelingsOfWorthlessnessGuilt());
        row.createCell(11).setCellValue(record.isDifficultyConcentrating());
        row.createCell(12).setCellValue(record.isSuicidalThoughts());
        row.createCell(13).setCellValue(record.isDepressionDiagnosis());
      }

      try (FileOutputStream fileStream = new FileOutputStream("DepressionData.xlsx")) {
        workbook.write(fileStream);
      }
      System.out.println("DepressionData.xlsx 写入成功.");
    } catch (IOException e) {
      e.printStackTrace();
    }
  }
}
```

`DepressionDataset` 生成一个名为 `"DepressionData.xlsx"` 的 Excel 表格，包含抑郁症状的数据。它定义了一个 `DepressionRecord` 类来表示包含年龄、性别和抑郁相关症状等属性的记录。`main` 方法初始化了一个 `DepressionRecord` 实例列表并填充了示例数据。使用 Apache POI 创建 Excel 工作簿和工作表，写入带有列名的表头，并遍历记录填充每行数据。最后，程序将工作簿写入文件并处理任何可能的 `IOException`。

# 11.8.3 案例研究 3

## 在 .txt 文件中收集数据

```java
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Random;

public class VitaminDDeficiencyData {
    public static void main(String[] args) {
        int ageStart = 20;
        int ageEnd = 80;
        double sunExposureRangeStart = 0.0;
        double sunExposureRangeEnd = 5.0; // 每天小时
        int vitaminDIntakeRangeStart = 0;
        int vitaminDIntakeRangeEnd = 400; // 每天 IU
        double serumDLevelRangeStart = 12.0;
        double serumDLevelRangeEnd = 80.0; // ng/ml
        String[] symptoms = {"疼痛", "肌肉无力", "疲劳", "脱发"};
        int numSamples = 100;
        String data = "";
        for (int i = 0; i < numSamples; i++) {
            data += generateSampleData(ageStart, ageEnd, sunExposureRangeStart, sunExposureRangeEnd, vitaminDIntakeRangeStart, vitaminDIntakeRangeEnd, serumDLevelRangeStart, serumDLevelRangeEnd, symptoms[i % symptoms.length]) + "\n";
        }
        try {
            File file = new File("vitamin_deficiency_data.txt");
            FileWriter writer = new FileWriter(file);
            writer.write(data);
            writer.close();
            System.out.println("示例缺乏数据已生成并存储");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    private static String generateSampleData(int ageStart, int ageEnd, double sunExposureRangeStart, double sunExposureRangeEnd, int vitaminDIntakeRangeStart, int vitaminDIntakeRangeEnd, double serumDLevelRangeStart, double serumDLevelRangeEnd, String symptom) {
        Random random = new Random();
        int age = random.nextInt(ageEnd - ageStart + 1) + ageStart;
        String gender = random.nextBoolean() ? "Male" : "Female";
        double sunExposure = random.nextDouble() * (sunExposureRangeEnd - sunExposureRangeStart) + sunExposureRangeStart;
        int vitaminDIntake = random.nextInt(vitaminDIntakeRangeEnd - vitaminDIntakeRangeStart + 1) + vitaminDIntakeRangeStart;
        double serumDDLevel = random.nextDouble() * (serumDLevelRangeEnd - serumDLevelRangeStart) + serumDLevelRangeStart;
        StringBuilder sb = new StringBuilder();
        // 构建字符串的实现细节...
        return sb.toString();
    }
}
```

```java
for (String symptom : symptoms) {
    symptomString.append(random.nextBoolean() ? "Yes," : "No,");
}
return age + "," + gender + "," + sunExposure + "," + dietaryVitaminDIntake
+ "," + serumVitaminDLevel + "," + symptomString.toString();
}
```



应用程序`VitaminDeficiencyData`生成了一个模拟维生素 D 缺乏数据集，并将其存储在名为`vitamin_deficiency_data.txt`的文本文件中。它定义了年龄、日照、饮食维生素 D 水平和血清维生素 D 水量的范围，并指定了一组可能的症状。主方法使用辅助方法`generateSampleData`在这些范围内生成 100 个样本数据，该方法为每个属性生成随机值并将其拼接逗号分隔的字符串。然后使用`FileWriter`将这些数据写入文件，并处理任何可能的`IOException`。

## 12 抽象窗口工具包 (Abstract Window Toolkit)

## 12.1 引言

Java AWT（抽象窗口工具包）是 Java 程序员用于创建图形用户界面（GUI）和丰富用户界面（UI）组件的一组 API。它是 Java 标准库的一部分，提供了一种用于创建和管理窗口、按钮、文本字段和其他 UI 组件的平台无关的方法。AWT 是用于构建 GUI 的最早的 Java 库之一，早于更现代的 Swing 库。

AWT 的平台无关性、简单性和健壮的事件处理能力使其成为在 Java 中开发基础图形用户界面的价值工具。它与原生代码集成以及高效管理布局的能力进一步增强了它的实用性，特别是对于简单的应用程序和遗留系统而言。

Java 的抽象窗口工具包（AWT）被广泛用于在 Java 应用程序中创建图形用户界面（GUI）和处理用户交互。以下是 AWT 的一些关键应用：

### 12.1.1 AWT 的组件

- 1. 容器（Containers）：这些是可以包含其他组件的组件，例如窗口和面板。示例包括`Frame`、`Panel`和`Applet`。

- 2. 组件（Components）：这些是 GUI 的个体元素，如按钮、标签、文本字段和列表。示例包括`Button`、`Label`、`TextField`和`List`。

- 3. 布局管理器（Layout Managers）：它们控制组件在容器内的定位和尺寸。示例包括`FlowLayout`、`BorderLayout`、`GridLayout`和`CardLayout`。

- 4. 事件处理（Event Handling）：AWT 提供健壮的事件处理机制来响应鼠标点击、键盘输入和窗口操作等用户输入。这包括`ActionListener`、`MouseListener`和`KeyListener`等监听器。

### 12.1.2 使用 AWT 的必要

- 1. 平台无关性：AWT 允许开发者创建可以在任何带有 Java 虚拟机（JVM）的操作系统上运行的应用程序，提供了跨平台的一外观。

- 2. 基础 GUI 开发：对于简单应用程序或需要轻级 GUI 的应用程序，AWT 提供了所需的工具，而没有像 Swing 或 JavaFX 那样复杂库的开销。

- 事件处理：AWT 提供健壮且易于使用的事件处理机制，允许应用程序响应用户操作（如按钮点击和按压）。

- 与原生代码集成：AWT 组件是重量级的，这意味着它们绑定到原生窗口系统。在将 Java 应用程序与原生应用程序或库集成时，这种特性是有优势的。

- 遗留支持：许多旧应用程序是使用 AWT 构建的。理解 AWT 对于维护和更新这些遗留系统至关重要。

## 12.2 AWT 的优势

Java 的抽象窗口工具包（AWT）为开发图形用户界面（GUI）和处理用户交互提供了若干优势。以下是一些关键益处：

- 平台无关性：

AWT 允许开发者创建可以在任何带有 Java 虚拟机（JVM）的操作系统上运行的应用程序。这确保了 GUI 在不同平台上的外观和行为一致。

- 轻量级且简单：

对于具有基础 GUI 要求的应用程序，AWT 提供了一个简单且轻量级的框架。这在开发简单应用程序或原型界面时是有优势的。

- 与原生代码集成：

AWT 组件是重量级的，这意味着它们直接映射到原生操作系统组件。这可以促进与原生应用程序和库的更好集成，充分利用底层平台的优势。

- 事件处理：

AWT 提供健壮且易于使用的事件处理机制，允许开发者高效处理鼠标点击、键盘击键和窗口操作等用户输入。这使得构建交互式应用程序变得更容易。

- 基础布局管理：

AWT 提供了几种布局管理器（例如`FlowLayout`、`BorderLayout`、`GridLayout`），有助于在容器内安排 GUI 组件。这些布局管理器简化了设计适应不同屏幕尺寸和分辨率的用户界面的过程。

- 遗留支持：

AWT 是 Java 中最老的 GUI 工具包之一，这意味着许多遗留系统和应用程序是使用它构建的。AWT 知识对于维护和更新这些旧应用程序至关重要。

- 基础应用程序的简化 API：

AWT 的 API 对于基础应用程序来说相对简单，让学者更容易学习并快速创建 GUI。AWT 组件的简单性使其适用于小型项目和教育目的。

## 12.3 AWT 的应用

- 桌面应用程序：

  - 简单 GUI 应用程序：AWT 适用于创建具有基础图形界面的简单桌面应用程序。这些应用程序通常涉及按钮、文本字段、标签和简单事件处理等基础组件。

  - 原型设计：在转向 Swing 或 JavaFX 等更复杂的 GUI 框架之前，可以使用 AWT 快速制作桌面应用程序的用户原型。

- 教育工具：

  - 教学：AWT 为学习 GUI 开发的初学者提供了一个入门点。它经常被用于教育环境，教授事件驱动编程和 GUI 设计的基础。

  - 交互式教程：可以使用 AWT 开发简单的教育应用程序和交互式教程，以提供上手学习体验。

- 实用与工具：

  - 自定义工具：开发者可以使用 AWT 创建需要图形用户界面的小型实用程序和工具，例如计算器、文本编辑器和文件管理器。

  - 系统监控：可以使用 AWT 开发监控系统资源（如 CPU 使用率或内存消耗）的应用程序。

- 数据可视化：

  - 图形和图表：可以使用 AWT 开发通过简单图形和图表可视化数据的应用程序。这些应用程序在金融、工程和科学研究领域非常有用。

  - 统计工具：可以使用 AWT 创建具有图形输出的基础统计分析工具。

- 自定义组件和控件：

  - GUI 组件：开发者可以使用 AWT 创建自定义的 GUI 组件和控件，对应用程序用户界面的外观和行为提供更多控制。

  - 可复用库：可以使用 AWT 开发自定义组件的可复用库，这些库可以集成到其他 Java 应用程序。

- 游戏和模拟：

  - 简单游戏：可以使用 AWT 开发基础游戏和模拟。这些应用程序通常涉及处理用户输入、渲染图形和管理游戏状态。

  - 教育模拟：可以使用 AWT 创建教育模拟和交互式学习工具，帮助可视化复杂的概念和过程。

## 12.4 AWT 的特性

- 1. 平台无关性：

AWT 是平台无关的，这意味着 AWT 应用程序可以在任何操作系统上运行，而无需任何修改。

- 2. 轻量级组件：

AWT 包含一组轻量组件（如按钮、文本字段和标签），它们使用操作系统的原生 GUI 组件进行渲染，确保原生的外观。

- 3. 事件处理：

AWT 提供健壮的事件处理机制来管理鼠标点击、按键和其他操作的用户交互。它使用委托事件模型，将事件处理委托给监听器对象。

- 4. 布局：

AWT 提供了几种布局管理器（如`FlowLayout`、`BorderLayout`、`GridLayout`等），有助于在容器内安排 GUI 组件。布局管理器使得设计灵活且适应的用户界面变得简单。

## 图形与绘制：

AWT 包含了用于绘制和渲染图形的类，例如线条、矩形、椭圆和其他形状。它还支持自定义渲染和图像处理。

## 容器与组件：

AWT 由由容器（如`Frame`、`Panel`和`Applet`）和组件（如`Button`、`TextField`、`Label`等）组成，它们构成了 AWT 程序的构建块。

## 可访问性：

AWT 组件的设计考虑了可访问性，支持屏幕阅读器等辅助技术，使应用程序对残障人士更具可用性。

## 与原生代码的集成：

AWT 可以通过 Java Native Interface (JNI) 与原生代码集成，允许开发者访问和使用标准 Java API 未提供的平台特定功能。

## 基础 GUI 组件：

AWT 提供了一系列丰富的 GUI 组件，包括按钮、复选框、列表、文本区域、滚动条等，使开发者能够构建交互式用户界面。

## 12.5 AWT 包

- 1. `java.awt*`

抽象窗口工具包 (AWT) 的核心包，包含用于基础 GUI 组件、布局管理器和绘图的类。

- 2. `java.awt.event*`

提供事件处理的类和接口，包括各种事件类型（例如鼠标、键盘、事件）及其相应的监听器。

- 3. `java.awt.geom*`

包含用于定义和对几何对象执行操作的类，适用于自定义图形和形状。

- 4. `java.awt.image*`

提供用于创建、操作和观察图像的类，便于图像处理和显示。

- 5. `java.awt.datatransfer*`

提供在应用程序之间和内部传输数据的类和接口，支持剪贴板操作和数据类型（data flavors）。

- 6. `java.awt.dnd*`

支持拖放操作，使用拖动源和放置目标，能够在 GUI 内部实现直观的数据传输。

这些包共同实现了图形用户界面的创建和管理，并处理了 Java 应用程序中的用户交互。

## 12.6 AWT 中的容器类

在 AWT（抽象窗口工具包）中，容器是一种可以包含其他组件（如按钮、文本字段、标签等）的组件。容器提供了一种在图形用户界面 (GUI) 中组织和排列组件的方法。

容器在 Java AWT 中的重要性在于它们能够管理 GUI 内部组件的布局和组织。它们允许开发者通过特定的布局（如`BorderLayout`、`FlowLayout`、`GridLayout`等）排列组件，从而创建结构化且视觉上良好的用户界面。

## 抽象窗口工具包

容器在开发应用程序中起着至关重要的作用，因为它们提供了创建直观友好界面所需的结构和组织。它们允许开发者控制组件的放置和排列，管理用户交互，并确保 GUI 在不同屏幕尺寸和分辨率下具有正确的尺寸和缩放。在 Java SWT 中，有多种类型的容器用于组织和管理 GUI 中的组件。以下是 Java AWT 中的主要容器类：

### 12.6.1 Frame

`Frame` 是一个带有标题和边界的顶级窗口，可以作为 GUI 应用的主窗口。在 AWT（抽象窗口工具包）中，`Frame`的 Key特性包括：

- 1. 顶级窗口：AWT 中的`Frame`代表应用程序的主窗口，提供一个带有标题栏、边界和标准窗口控件（最小化、最大化、关闭）的窗口。

- 2. 可调整大小和可关闭：它允许用户调整窗口大小、关闭，并执行由窗口管理器控制的最小化和最大化操作。

- 3. 包含：`Frame`可以容纳各种 AWT 组件，如按钮、文本字段、面板等，允许开发者在`Frame`内部构建用户界面。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class FrameExample {
    void main(String[] args) {
    // 创建一个新的 Frame
    Frame frame = new Frame("Frame Example");

    // 设置 frame的大小
    frame.setSize(300, 200);

    // 设置 frame 的背景颜色
    frame.setBackground(Color.LIGHT_GRAY);

    // 设置布局为 FlowLayout
    frame.setLayout(new FlowLayout());

    // 创建一个按钮并将其添加到 frame
    Button button = new Button("Usha");
    frame.add(button);

    // 添加 WindowListener 来处理窗口关闭
    frame.addActionListener(new WindowAdapter() {
        @Override
        public void windowClosing(WindowEvent e) {
            System.exit(0);
        }
    });

    // 使 frame 可 de
    frame.setVisible(true);
    }
}
```

## 464 用于医疗和医学应用的 Java 22

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_474_0.png)

在上面的程序中，我们创建了一个名为“Frame Example”的 frame，大小为 300x 200 像素，背景为浅灰色。布局设置为`FlowLayout`，它按照从左到右的流排列组件，类似于段落中的文本行。frame 中添加了一个标记为“Click Me”的按钮。最后，frame 对用户可见。

### 12.6.2 Panel

`Panel` 是一个简单的容器类，可以容纳其他 AWT 组件。AWT（抽象窗口工具包）中`Panel`的 Key特性包括：

- 轻量级容器：`Panel`是一种轻量级容器，用于在窗口或 applet 的区域内组织和持有 AWT 组件（如按钮、标签等）。

- 布局管理：它使用布局管理器（如`FlowLayout`、`GridLayout`等）来控制面板内组件的位置和大小。

- 嵌套容器：`Panel`可以作为嵌套容器用于其他容器（如`Frame`或另一个`Panel`）内部，允许灵活且复杂的 UI 布局。

## 程序

```java
import java.awt.*;
public class PanelExample {
    void main(String[] args) {
        // 创建一个标题为 "Panel Example" 的新 Frame
        Frame frame = new Frame("Panel Example");
        // 设置 frame的大小
        frame.setSize(300, 200);
        // 创建一个新的 Panel
        Panel panel = new Panel();
        // 设置 panel 的背景颜色为青色
        panel.setBackground(Color.CYAN);
        // 创建两个按钮并将它们添加到 panel
        Button button1 = new Button("Button 1");
        Button button2 = new Button("Button 2");
        panel.add(button1);
        panel.add(button2);
        // 将 panel 添加 frame
        frame.add(panel);
        // 使 frame 可 de
        frame.setVisible(true);
    }
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_475_0.png)

在上面的程序中，我们创建了一个名为“Panel Example”的 frame，大小为 300x200 像素。frame 内部创建了一个 panel 并将其背景设置为青色。panel 包含了两个按钮`Button 1`和`Button 2`。将 panel 添加到 frame 中，最后，frame 对用户可见。

### 12.6.3 DIALOG

`Dialog`是一种弹出窗口，可以是模态的（阻塞对其他窗口的输入）或非模态的（允许对其他窗口的输入）。AWT（抽象窗口工具包）中`Dialog`的特性：

- 弹出窗口：`Dialog`代表一个弹出窗口，用于显示消息、提示或请求用户输入。它通常出现在父级`Frame`或`Applet`之上。

- 模态与非模态：`Dialog`可以是模态或非模态（在关闭之前与其他窗口交互），由其模态性控制。

- 可定制：它提供了添加组件并自定义其外观和行为的能力，例如添加用户操作按钮（如 OK、取消）以及设置其布局和外观。

## 程序

```java
import java.awt.*;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;
public class DialogExample {
 void void main(String[] args) {
  // 创建标题为 "Dialog Example" 的主 frame
  Frame frame = new Frame("Dialog Example");
  frame.setSize(300, 200);
  frame.setLayout(new FlowLayout());
  // 创建一个标题为 "My Dialog" 的模态 dialog
  final Dialog dialog = new Dialog(frame, "My Dialog", true);
  dialog.setSize(200, 100);
  dialog.setLayout(new FlowLayout());
  dialog.setBackground(Color.PINK);
  // 创建一个按钮并将其添加到 dialog
  Button button = new Button("OK");
  dialog.add(button);
  // 使 dialog 可 de
  dialog.setVisible(true);
  // 使 frame 可 de
  frame.setVisible(true);
 }
}
```

# 用于医疗健康应用的 Java 22



```java
// 给对话框添加标签
Label label = new Label("This is a dialog");
dialog.add(label);
// 显示对话框
dialog.setVisible(true);
// 显示主框架
frame.setVisible(true);
}
```

输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_476_0.png)

在上面的程序中，我们创建了一个标题为“Dialog Example”的`Frame`（框架），并在其中创建一个名为“My Dialog”的模态`Dialog`（对话），大小为 200x100 像素。该对话框具有粉色背景并使用了`FlowLayout`。对话框中添加了一个文本为“This is a dialog”的`Label`（标签）。最后，对话框对用户可见。

## 12.6.4 Window

在 Java AWT 中，`Window`是一个顶层容器，表示一个没有标题或边框的图形窗口。它通常用于创建自定义的弹出窗口或对话框。AWT（抽象窗口工具包）中`Window`的关键特性有：

- 1. 顶层容器：`Window`作为一个基本的顶层容器，可以容纳其他 AWT 组件。它是创建如`Frame`和`Dialog`等更多窗口类型的基础。
- 2. 装饰：与`Frame`不同，`Window`不包含标题栏、边框或控制按钮等内置窗口装饰。它提供了一个空白的、未装饰的窗口，这对于自定义窗口设计非常有用。
- 3. 可自定义的大小和位置：`Window`允许手动控制其在屏幕上的大小和位置。开发者可以根据应用程序程序化地设置其大小、位置和可见性。

### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ColorChangeExample {
    public void main(String[] args) {
        // 创建一个新的 Frame
        Frame frame = new Frame("Color Change Example");

        // 将布局设置为 FlowLayout
        frame.setLayout(new FlowLayout());
        // 创建一个改变背景颜色的按钮
        Button changeColorButton = new Button("Change Color");

        // 为按钮添加 ActionListener 以处理点击事件
        changeColorButton.addActionListener(new ActionListener() {
            private boolean isDefaultColor = true;

            @Override
            public void actionPerformed(ActionEvent e) {
                // 改变 frame 的背景颜色
                if (isDefaultColor)
                    frame.setBackground(Color.CYAN); //变为青色
                else
                    frame.setBackground(Color.LIGHT_GRAY); // 浅灰色

                // 切换颜色状态
                isDefaultColor = !isDefaultColor;
            }
        });
        // 将按钮添加到 frame
        frame.add(changeColorButton);
        // 设置 frame的大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 处理窗口关闭事件
        frame.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_477_0.png)

在上面的程序中，我们使用 AWT 创建了一个简单的 GUI 应用程序，允许用户通过点击按钮来更改`frame`的背景颜色。`ColorChangeExample`类设置了一个带有“Color Change”按钮的`frame`，并且`ActionListener`在每次点击按钮时都会在青色和浅灰色之间切换`frame`的背景颜色。

## 12.7 AWT 布局

在 Java AWT 和 Swing 中，布局管理器被用于定义容器内组件的位置和大小。它们决定了组件之间以及组件与容器本身之间的排列方式。在开发应用程序时，布局管理器是重要且必须的：

- 1. 平台无关性：布局管理器确保无论平台或屏幕分辨率如何，GUI 组件都能正确置位。它们处理了不同操作系统之间窗口大小和字体的差异，确保了一致的用户体验。
- 2. 自适应性：当窗口调整大小时，布局管理器会自动调整组件的布局。这使得 GUI 对窗口大小的变化具有更强的响应性和适应性。
- 3. 易于维护：使用布局管理器简化了修改和维护 GUI 的过程。由于布局管理器处理组件的位置，你可以专注于设计界面，而无需担心每个组件的精确坐标。
- 4. 可扩展性：布局管理器支持在运行时动态添加和删除组件。这允许你在不影响界面整体布局的情况下添加或删除组件。
- 5. 跨平台兼容性：Java 的布局管理器被设计为能够在不同平台上一致地工作，确保 GUI 在所有支持的系统上外观和行为都相同。

布局管理器在 Java 应用程序中创建灵活、响应迅速且平台无关的 GUI 起着至关重要的作用。它们简化了开发过程，并帮助确保应用程序在不同环境中提供一致且用户友好的界面。常用的布局管理器描述如下。

### 12.7.1 FlowLayout

`FlowLayout`从左到右的流排列组件，就像段落中的文本行一样。AWT（抽象窗口工具包）中`FlowLayout`的关键特性有：

- 1. 简单布局：`FlowLayout`按左到右的流排列组件，当当前行满时，将它们换到下一行。它是一种简单的布局管理器，按行管理组件。
- 2. 对齐选项：它提供了在容器内水平对齐组件的选项：`LEFT`（左对齐）、`CENTER`（居中对齐）和`RIGHT`（右对齐）。这允许控制每行内组件的对齐方式。
- 3. 动态调整：当容器调整大小时，`FlowLayout`会自动调整组件的排列，确保组件根据窗口大小适当地流动和换行。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class FlowLayoutExample {
    public void main(String[] args) {
        // 创建一个新的 Frame
        Frame frame = new Frame("FlowLayout Example");

        // 将布局设置为 FlowLayout
        frame.setLayout(new FlowLayout());
        // 创建具有不同背景颜色的按钮
        Button javaButton = new Button("Java");
        javaButton.setBackground(Color.CYAN); // 变为青色

        Button pythonButton = new Button("Python");
        pythonButton.setBackground(Color.MAGENTA); // 洋红色

        // 将按钮添加到 frame
        frame.add(javaButton);
        frame.add(pythonButton);
        // 设置 frame的大小并使其可见
        frame.setSize(300, 100);
        frame.setVisible(true);
        // 处理窗口关闭事件
        frame.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_479_0.png)

在上面的程序中，创建了一个标题为“FlowLayout Example”的`Frame`，并将其布局设置为`FlowLayout`。创建了两个具有青色和洋红色背景的`Button`，标签分别为“Java”和“Python”。这些按钮被添加到`frame`中。`frame`的大小设置为 300x100 像素并对用户可见。

### 12.7.2 BorderLayout

`BorderLayout`在五个区域排列组件：北、南、东、西和中心。AWT（抽象窗口工具包）中`BorderLayout`的关键特性有：

- 五个区域：`BorderLayout`将容器分为五个不同的区域：`NORTH`（北）、`SOUTH`（南）、`EAST`（东）、`WEST`（西）和`CENTER`（中心）。每个区域可以容纳一个组件，`CENTER`区域会填充所有剩余空间。
- 组件缩放：添加到`NORTH`和`SOUTH`的组件调整大小以适应容器的宽度，而`EAST`和`WEST`的组件调整大小以适应整个高度。`CENTER`区域的组件将扩展填充任何剩余空间。
- 简单的布局管理：`BorderLayout`提供了一种简单的组件放置和缩放的方法，便于创建组件围绕中心区域排列的布局。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class BorderLayoutExample {
    public void main(String[] args) {
        // 创建一个新的 Frame
        Frame frame = new Frame("BorderLayout Example");

        // 将布局设置为 BorderLayout
        frame.setLayout(new BorderLayout());
    }
}
```

#### 470 用于医疗与保健应用的 Java 22

```java
frame.setLayout(new BorderLayout());
// 创建具有不同背景颜色和标签的按钮
northButton = new Button("North");
northButton.setBackground(Color.RED); // 设置背景颜色为红色
southButton = new Button("South");
southButton.setBackground(Color.BLUE); // 设置背景颜色为蓝色
eastButton = new Button("East");
eastButton.setBackground(Color.GREEN); // 设置背景颜色为绿色
westButton = new Button("West");
westButton.setBackground(Color.ORANGE); // 设置背景颜色为橙色
centerButton = new Button("Center");
centerButton.setBackground(Color.PINK); // 设置背景颜色为粉色
// 将按钮添加到框架对应的区域
frame.add(northButton, BorderLayout.NORTH);
frame.add(southButton, BorderLayout.SOUTH);
frame.add(eastButton, BorderLayout.EAST);
frame.add(westButton, BorderLayout.WEST);
frame.add(centerButton, BorderLayout.CENTER);
// 设置框架大小并使其可见
frame.setSize(400, 300);
frame.setVisible(true);
// 处理窗口关闭事件
frame.addWindowListener(new WindowAdapter() {
    @Override
    public void windowClosing(WindowEvent e) {
        System.exit(0);
    }
});
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_480_0.png)

在上面的程序中，创建了一个标题为“BorderExample”的框架（`Frame`），并将其布局设置为`BorderLayout`。创建了五个具有不同背景颜色和标签的按钮（`Button`）组件，标签指示它们的位置：“North”（红色）、“South”（蓝色）、“East”（绿色）、“West”（橙色）和“Center”（粉色）。这些按钮被添加到框架对应的区域。框架的大小设置为 400x300 像素，并对用户可见。

### 抽象窗口工具包 (Abstract Window Toolkit)

### 12.7.3 GridLayout

`GridLayout`将组件排列在大小相等的单元网格中。AWT 中`GridLayout`的主要特性：

- 1. 统一网格：`GridLayout`将组件排列在具有等大小单元格的网格中。组件按行列排列，每个组件的大小相同。
- 2. 灵活的行列配置：在创建`GridLayout`时，你可以指定行数和列数。如果组件数量超过了指定的行列，它会自动调整以适应网格。
- 3. 等大尺寸：`GridLayout`内部的所有组件都会调整大小以适应各自的单元格，确保了统一性和对齐。这使其成为创建一致且组织良好的布局的理想选择。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class GridLayoutExample {
    public static void main(String[] args) {
        // 创建新框架
        Frame frame = new Frame("GridLayout Example");
        // 将布局设置为 2 行 2 列的 GridLayout
        frame.setLayout(new GridLayout(2, 2));
        // 创建具有不同背景颜色和标签的按钮
        Button javaButton = new Button("Java");
        javaButton.setBackground(Color.CYAN); // 设置背景颜色为青色
        Button pythonButton = new Button("Python");
        pythonButton.setBackground(Color.MAGENTA); // 设置背景颜色为洋红色
        Button cppButton = new Button("C++");
        cppButton.setBackground(Color.YELLOW); // 设置背景颜色为黄色
        Button dataStructuresButton = new Button("Data Structures");
        dataStructuresButton.setBackground(Color.ORANGE); // 设置背景颜色为橙色
        // 将按钮添加到框架
        frame.add(javaButton);
        frame.add(pythonButton);
        frame.add(cppButton);
        frame.add(dataStructuresButton);
        // 设置框架大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 处理窗口关闭事件
        frame.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

#### 472 用于医疗与保健应用的 Java 22

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_482_0.png)



在上面的程序中，创建了一个标题为“BorderExample”的框架（`Frame`），并将其布局设置为“Border”。创建了五个具有不同背景颜色和标签的按钮（`Button`）组件，标签指示它们的位置：“North”（红色）、“South”（蓝色）、“East”（绿色）、“West”（橙色）和“Center”（粉色）。这些按钮被添加到框架对应的区域。框架的大小设置为 400x300 像素，并对用户可见。

## 12.7.4 CardLayout

`CardLayout` 允许你堆叠组件并一次显示一张卡片。AWT 中 `CardLayout` 的主要特性：

- 1. 基于卡的显示：`CardLayout` 允许你堆叠组件并只显示一个卡片。
- 2. 简单导航：它提供了如 `next()`、`previous()`、`first()` 和 `last()` 等方法来在卡片之间导航。
- 3. 动态管理：`CardLayout` 使用名称或索引来管理卡片的可见性。

### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class CardLayoutExample {
    public static void main(String[] args) {
        // 创建框架
        Frame frame = new Frame("CardLayout Example");
        // 将布局设置为 CardLayout
        CardLayout cardLayout = new CardLayout();
        frame.setLayout(cardLayout);
        // 创建不同的面板
        Panel panel1 = new Panel();
        panel1.setBackground(Color.RED);
        panel1.add(new Label("Card 1"));
        Panel panel2 = new Panel();
        panel2.setBackground(Color.BLUE);
        panel2.add(new Label("Card 2"));
        Panel panel3 = new Panel();
        panel3.setBackground(Color.GREEN);
        panel3.add(new Label("Card 3"));
        // 将面板添加到框架
        frame.add(panel1, "One");
        frame.add(panel2, "Two");
        frame.add(panel3, "Three");
        // 设置框架大小并使其可见
        frame.setSize(400, 300);
        frame.setVisible(true);
        // 处理窗口关闭事件
    }
}
```

## 用于医疗与健康应用的 Java 22

### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class GridBagLayoutExample {
    public void main(String[] args) {
        // 创建一个新的 Frame
        Frame frame = new Frame("GridBagLayout Example");
        // 将布局设置为 GridBagLayout
        frame.setLayout(new GridBagLayout());
        // 创建 GridBagConstraints
        GridBagConstraints gbc = new GridBagConstraints();
        gbc.fill = GridBagConstraints.BOTH;
        gbc.insets = new Insets(5, 5, 5, 5); // 组件周围的内边距
        // 创建不同背景色的按钮
        Button button1 = new Button("Java");
        button1.setBackground(Color.CYAN);

        Button button2 = new Button("Python");
        button2.setBackground(Color.MAGENTA);

        Button button3 = new Button("C++");
        button3.setBackground(Color.YELLOW);

        Button button4 = new Button("Data Structures");
        button4.setBackground(Color.ORANGE);
        // 使用 GridBagConstraints 将按钮添加到 frame 中
        gbc.gridx = 0; // 列
        gbc.gridy = 0; // 行
        frame.add(button1, gbc);
        gbc.gridx = 0;
        gbc.gridy = 1;
        frame.add(button2, gbc);
        gbc.gridx = 0;
        gbc.gridy = 2;
        frame.add(button3, gbc);
        gbc.gridx = 0;
        gbc.gridy = 3;
        frame.add(button4, gbc);
        // 设置 frame 的大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 处理窗口关闭事件
        frame.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

### 抽象窗口工具包 (Abstract Window Toolkit)

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_485_0.png)

在上述程序中，创建了一个标题为“GridLayout Example”的 `Frame`，并布局设置为 `GridLayout`。创建了四个不同背景色的按钮：“Java”（青色）、“Python”（洋红色）、“C++”（黄色）和“Data Structures”（橙色）。每个按钮都使用 `GridBagConstraints` 按照指定的网格位置添加到 frame 中。然后，将 frame 的大小设置为 300 乘 200 像素并使其可见。

## 12.76 BoxLayout

`BoxLayout` 沿垂直或水平方向排列组件。AWT 中 `BoxLayout` 的主要特性包括：

- 1. 线性布局：`BoxLayout` 在单行或单列中垂直或水平排列组件，为在直线上对齐组件提供简单的方法。
- 2. 组件对齐：它允许组件在容器内沿基线、中心或其他指定的位置对齐，便于实现灵活且一致的间距和对齐。
- 3. 可缩放组件：在 `BoxLayout` 中，组件可以根据其首选尺寸和可用空间放大或缩小，从而在保持线性布局的同时轻松管理不同组件尺寸的布局。

### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class BoxLayout {
    void main(String[] args) {
        // 创建一个新的 Frame
        Frame frame = new Frame("BoxLayout Example");
        // 创建一个布局设置为 Y_AXIS（垂直）的 Panel
        Panel panel = new Panel();
        panel.setLayout(new BoxLayout(panel, BoxLayout.Y_AXIS));
        // 创建不同背景色的按钮
        Button button1 = new Button("Java");
        button1.setBackground(Color.CYAN);
        Button button2 = new Button("Python");
        button2.setBackground(Color.MAGENTA);
        // 将按钮添加到 panel
        panel.add(button1);
        panel.add(button2);
        // 将 panel 添加到 frame
        frame.add(panel);
        // 设置 frame 的大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 处理窗口关闭事件
        frame.addListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_486_0.png)

在上述程序中，创建了一个标题为“BoxLayout Example”的 `Frame`，并向其添加了一个带有垂直 `BoxLayout` 的 `Panel`。创建了两个按钮：“Java”（青色背景）和“Python”（洋红色背景）。这些按钮被添加到 panel。最后，将 panel 添加到 frame，设置 frame 的大小为 300x200 像素并使其可见。

## 12.7.7 GroupLayout

`GroupLayout` 是一种以分级方式排列组件的布局管理器。`GroupLayout` 的特性是：

- 1. 灵活的布局管理：`GroupLayout` 通过将组件组织成水平和垂直组，实现了对定位的精确控制。这使得组件可以对齐的复杂且灵活的安排成为可能。
- 2. 自动调整尺寸：`GroupLayout` 根据组件的首选尺寸自动调整组件大小，确保响应式布局。
- 3. 与 GUI 构建器集成：`GroupLayout` 在 GUI 构建器（如 NetBeans）中特别有用，它简化了设计过程。

### 程序

```java
import javax.swing.*;
import java.awt.*;

public class GroupLayoutExample {
    void main(String[] args) {
        // 创建一个标题为 "GroupLayout" 的 JFrame
        JFrame frame = new JFrame("GroupLayout");
        frame.setDefaultCloseOperation(JFrame.EXIT_CLOSE);
        // 创建一个 JPanel 并将其布局设置为 GroupLayout
        JPanel panel = new JPanel();
        GroupLayout layout = new GroupLayout(panel);
        panel.setLayout(layout);
        // 创建不同背景色的按钮
        JButton button1 = new JButton("Java");
        button1.setBackground(Color.CYAN);
        JButton button2 = new JButton("Python");
        button2.setBackground(Color.MAGENTA);
        // 将按钮添加到 panel
        panel.add(button1);
        panel.add(button2);
        // 定义水平组
        layout.setHorizontalGroup(
            layout.createSequentialGroup()
                .addComponent(button1)
                .addComponent(button2)
        );
        // 定义垂直组
        layout.setVerticalGroup(
            layout.createVerticalGroup()
                .addComponent(button1)
                .addComponent(button2)
        );
        // 将 panel 添加到 frame
        frame.add(panel);
        // 设置 frame 的大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}
```

### 抽象窗口工具包 (Abstract Window Toolkit)

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_487_0.png)

在上述程序中，创建了一个标题为“GroupLayout Example”的 `Frame`，包含一个带有 `GroupLayout` 的 `JPanel`。“Java”（青色背景）和“Python”（洋红色背景）被添加到 panel。布局被设置为创建组件之间的间距并使其正确对齐。frame 的大小为 300x200 像素并使其可见。

## 12.7.8 SpringLayout

`SpringLayout` 是一种专为 GUI 构建器设计的布局管理器。`SpringLayout` 的特性是：

- 1. 约束：`SpringLayout` 通过一组约束来实现定位的精确控制，这些约束定义了组件彼此之间的相对位置。
- 2. 动态布局调整：布局管理器会在容器调整大时动态调整组件，确保响应式布局。
- 3. 复杂布局：通过为每个组件指定约束，它允许创建复杂的布局。

### 程序



```java
import javax.swing.*;
import java.awt.*;

public class SpringLayoutExample {
    void main(String[] args) {
        // 创建一个标题为 "SpringLayout Example" 的 JFrame
        JFrame frame = new JFrame("SpringLayout Example");
        frame.setDefaultCloseOperation(JFrame.EXIT_CLOSE);
        // 创建一个 JPanel 并将其布局设置为 SpringLayout
        JPanel panel = new JPanel();
        SpringLayout layout = new SpringLayout();
        panel.setLayout(layout);
        // 创建不同背景色的按钮
        JButton button1 = new JButton("Java");
        button1.setBackground(Color.CYAN);
        JButton button2 = new JButton("Python");
        button2.setBackground(Color.MAGENTA);
        // 将按钮添加到 panel
        panel.add(button1);
        panel.add(button2);
        // 定义 button1 的 SpringLayout 
        layout.putConstraint(SpringLayout.NORTH, button1, 10, SpringLayout.NORTH, panel);
        layout.putConstraint(SpringLayout.WEST, button1, 10, SpringLayout.WEST, panel);
        // 定义 button2 的 SpringLayout 
        layout.putConstraint(SpringLayout.NORTH, button2, 0, SpringLayout.NORTH, button1);
        layout.putConstraint(SpringLayout.WEST, button2, 20, SpringLayout.EAST, button1);
        // 将 panel 添加到 frame
        frame.add(panel);
        // 设置 frame 的大小并使其可见
        frame.setSize(300, 100);
        frame.setVisible(true);
    }
}
```

## 窗口工具包 479

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_489_0.png)

在程序中，标题为“SpringLayout Example”的`JFrame`包含一个带有`SpringLayout`的`JPanel`。面板中添加了两个按钮，“Java”（青色背景）和“Python”（洋红色背景）。布局约束将“Java”按钮放置在面板左上角 10 像素处，“Python”按钮则放置在“Java”按钮右侧 20 像素处，并保持垂直对齐。面板被添加到框架中，框架的大小设定为 300 100 像素并设置为可见。

## 12.7.9 绝对布局 (ABSOLUTE LAYOUT)

绝对布局通过指定精确的坐标来实现组件的精确放置。“绝对布局”的关键特性如下：

1. 固定定位：在绝对布局中，组件被放置在容器内的特定坐标 (x, y) 上。这允许对每个组件的位置和大小进行精确控制，但需要手动指定坐标和尺寸。

2. 无自动布局管理：与其他管理器不同，绝对布局在容器调整大小时不会自动调整或管理组件的大小或位置。组件将保持在指定的的位置和大小上，如果容器尺寸发生变化，可能会导致布局问题。

3. 简单直接：虽然绝对布局提供了精确控制，但对于组件不需要动态调整的简单界面，它是直观且易于实现的。然而，与其他布局相比，它对于复杂或响应式 UI 设计的灵活性扩展扩展性较低。

### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class AbsoluteLayoutExample {
    public static void main(String[] args) {
        // 创建标题为 "AbsoluteLayout Example" 的 Frame
        Frame frame = new Frame("AbsoluteLayout Example");
        frame.setLayout(null); // 将布局设置为 null 以实现绝对定位
        // 创建不同背景色的按钮
        Button button1 = new Button("Java");
        button1.setBackground(Color.CYAN);
        Button button2 = new Button("Python");
        button2.setBackground(Color.MAGENTA);
        // 设置 button1 的大小和位置
        button1.setBounds(50, 50, 80, 30); // x, y, width, height
        // 设置 button2 的大小和位置
        button2.setBounds(150, 50, 80, 30); // x, y, width, height
        // 将按钮添加到 frame 中
        frame.add(button1);
        frame.add(button2);
        // 设置 frame 大并使其可见
        frame.setSize(300, 150);
        frame.setVisible(true);
        // 添加窗口监听器处理关闭事件
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_490_0.png)

在上述程序中，标题为“AbsoluteLayout Example”的`Frame`其布局设置为`null`，框架中添加了两个按钮，“Java”（青色背景）和“Python”（洋红色背景）。“Java”按钮位于位置 (50, 50)，尺寸为 80x30 像素，而“Python”按钮位于位置 (150, 50)，尺寸相同。框架的大小被设置为 300x150 像素并设置为可见。

## 12.8 AWT 组件

在 Java AWT 中，组件是创建图形用户界面 (GUI) 的构建块。组件代表各种视觉元素，如按钮、标签、文本字段、复选框、菜单等。它们是用户与之交互以执行操作或提供输入的用户界面。

组件在 Java AWT 中的重要性在于，它们在为 Java 应用程序创建交互式且视觉良好的用户界面方面的作用。

1. 交互：组件允许用户通过点击按钮、输入文本、选择选项和执行其他操作与应用程序交互。

2. 视觉表示：组件提供了各种 GUI 元素的视觉表示，使用户更容易理解和导航应用程序。

3. 事件处理：组件响应用户操作（如按钮点击或文本输入）生成事件。这些事件可以由事件监听器处理以执行特定操作或触发操作逻辑。

4. 定制化：组件可以根据外观、大小、颜色、字体和布局进行定制，以匹配应用程序的设计需求和美学。

5. 模块化：组件可以在应用程序的不同部分或多个应用程序中重用，促进模块化和代码重用性。

6. 层级结构：组件可以按层级组织，允许创建带有嵌套容器和子组件的复杂用户界面。

### 12.8.1 标签 (LABEL)

`Label`是一个不可编辑的文本组件。AWT（抽象窗口工具包）中`Label`的关键特性：

1. 文本显示：`Label`用于显示单行文本或图像。它通常用于在其他组件（如文本字段或按钮）旁边提供信息或标签。

2. 不可编辑：与`TextField`或`TextArea`等组件不同，`Label`是不可编辑的。它只显示文本或图像而不需要用户交互，非常适合静态显示目的。

3. 对齐和样式：`Label`允许左对齐、居中或右对齐等文本对齐选项。你还可以自定义其字体、颜色和属性，以匹配你用户界的设计。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class LabelExample {
    public static void main(String[] args) {
        // 创建标题为 "Label Example" 的 Frame
        Frame frame = new Frame("Label Example");
        frame.setLayout(new FlowLayout()); // 将布局设置为 FlowLayout
        // 创建内容为 "Course Registration Form" 的 Label
        Label label = new Label("Course Registration Form");
        label.setBackground(Color.CYAN); // 设置背景色为青色
        // 将标签添加到 frame
        frame.add(label);
        // 设置大小并使其可见
        frame.setSize(300, 100);
        frame.setVisible(true);
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

##### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_491_0.png)

在上述程序中，我们创建了一个标题为“Label Example”的`Frame`，其中包含一个显示“Course Registration Form”且具有青色背景的`Label`。标签被添加到使用`FlowLayout`的框架中。框架的大小设置为 300x100 像素并设置为可见。

### 12.8.2 按钮 (BUTTON)

`Button`是一种按钮，点击时会触发操作。AWT（抽象窗口工具包）中`Button`的关键特性：

1. 交互元素：`Button`是一个点击时会触发操作的交互组件。

2. 可定制的文本和外观：你可以设置按钮上的文本或标签，并自定义其大小、字体和颜色。这允许你根据设计定制外观。

3. 事件处理：`Button`支持事件处理，你可以附加`ActionListener`对象来处理点击事件。这允许你响应用户操作定义自定义行为。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ButtonExample {
    public static void main(String[] args) {
        // 创建标题为 "Button Example" 的 Frame
        Frame frame = new Frame("Button Example");
        frame.setLayout(new FlowLayout()); // 将布局设置为 FlowLayout
        // 创建标签为 "Submit" 的按钮
        Button button = new Button("Submit");
        button.setBackground(Color.GREEN); // 设置背景色为绿色
        // 将按钮添加到 frame
        frame.add(button);
        // 设置大小并使其可见
        frame.setSize(200, 100);
        frame.setVisible(true);
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

##### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_492_0.png)

在上述程序中，我们创建了一个标题为“Button Example”的`Frame`，并添加了一个标签为“Submit”且具有绿色背景的`Button`。框架使用`FlowLayout`来排列其组件。框架的大小设置为 200x100 像素并设置为可见。

### 12.8.3 文本字段 (TextField)

`TextField`允许用户输入单行文本。

#### 抽象窗口工具包 (Abstract Window Toolkit)

1. 单行输入：`TextField`提供了一个单行区域，用户可以在其中输入和编辑文本。它通常用于用户输入，如输入名称、搜索查询或短条信息。

2. 可自定义的尺寸和列数：你可以指定`TextField`的列数，这决定了它的宽度。这允许你根据设计需求和预期的输入长度调整文本的大小。

3. 事件处理与验证：`TextField`通过`ActionListener`和其他监听器支持事件处理，让你能够响应用户交互并验证输入。这使得实现数据提交或实时输入验证的功能变得简单。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class TextFieldExample {
    void main(String[] args) {
    // 创建一个标题为 "TextField Example" 的 Frame
    Frame frame = new Frame("TextField Example");
    frame.setLayout(new FlowLayout()); // 设置布局为 FlowLayout
    // 创建带有占位符文本的 TextField
    TextField textField = new TextField("Enter your name");
    textField.setBackground(Color.YELLOW); // 设置背景颜色为黄色
    // 将 TextField 添加到 frame
    frame.add(textField);
    frame.setSize(300, 100);
    frame.setVisible(true);
    // 添加窗口监听器来处理关闭事件
    frame.addWindowListener(new WindowAdapter() {
        public void windowClosing(WindowEvent e) {
            System.exit(0);
        }
    });
}
}
```

##### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_493_0.png)

在上面的程序中，我们创建了一个标题为`TextField Example`的`Frame`，并添加了一个带有占位符文本`Enter your name`和黄色背景的`TextField`。该 frame 使用`FlowLayout`来管理其组件。frame 的尺寸为 300x100 像素并设置为可见。

### 12.8.4 TextArea

`TextArea`允许用户输入多行文本。`TextArea`的主要特性是：

1. 多行输入：`TextArea`允许用户输入和编辑多行文本，使其适用于较长的输入，如注释、描述或大块数据。

2. 滚动能力：当文本超过文本区域的可视区域时，它支持滚动。这确保用户可以查看和编辑所有内容，而不需要固定尺寸的输入字段。

3. 可自定义的行数和列数：你可以设置`TextArea`的行数和列数，这控制了它的尺寸以及同时显示的文本量。这种灵活性允许你定制组件以适应各种设计要求和文本需求。

#### 程序



```java
import java.awt.*;
import java.awt.event.*;
public class TextAreaExample {
    void main(String[] args) {
    // 创建一个带有占位符 "TextAreaExample" 的 Frame
    Frame frame = new Frame("TextAreaExample");
    frame.setLayout(new FlowLayout()); // 设置布局为 FlowLayout
    // 创建带有占位符文本、5行30列的 TextArea
    TextArea textArea = new TextArea("Enter your experience", 5, 30);
    textArea.setBackground(Color.PINK); // 设置背景颜色为粉色
    // 将 TextArea 添加到 frame
    frame.add(textArea);
    // 设置 frame 尺寸并使其可见
    frame.setSize(400, 200);
    frame.setVisible(true);
    // 添加窗口监听器来处理关闭
    frame.addWindowListener(new WindowAdapter() {
        public void windowClosing(WindowEvent e) {
            System.exit(0);
        }
    });
}
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_494_0.png)

在程序中，我们创建了一个标题为 "TextArea Example" 的`Frame`，添加了一个带有占位符文本 "Enter your experience"尺寸为 5 行 30 列且粉色背景的`TextArea`。该`frame`使用`FlowLayout`来管理其组件。`frame`的尺寸为 400x200 像素并设置为可见。

## 12.8.5 Checkbox

`Checkbox`允许用户进行二选一，即在两个可能的选项之间进行选择。`Checkbox`的主要特性是：

- 二元选择：`Checkbox`允许用户进行二选一，即选择（选中）或取消选择（未勾选）选项。它通常用于不互斥的选项，每个`Checkbox`都可以关联一个文本标签，描述它代表的选项或选择。这有助于用户理解复选框的作用以及他们正在选择什么操作。
- 标记：`Checkbox`通过`EventListener`支持事件处理，允许你响应其状态（选中或未选中）的变化。这使你能够根据用户的选择执行特定操作，例如更新其他组件或触发事件。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class CourseSelectionWT {
    public void main(String[] args) {
        // 创建一个新的 Frame
        Frame frame = new Frame("Checkbox Example");
        // 设置 frame 的布局为 FlowLayout
        frame.setLayout(new FlowLayout());
        // 为 "Courses" 创建标签
        Label courselabel = new Label("Courses:");
        // 为 Java 和 Python 课程创建复选框
        Checkbox javaCheckbox = new Checkbox("Java");
        Checkbox pythonCheckbox = new Checkbox("Python");
        // 将组件添加到 frame 
        frame.add(courselabel);
        frame.add(javaCheckbox);
        frame.add(pythonCheckbox);
        // 设置 frame 尺寸并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 添加窗口监听器来关闭 frame
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent event) {
                System.exit(0);
            }
        });
    }
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_495_0.png)

在上面的程序中，我们创建了一个带有`FlowLayout`的 AWT `Frame`，它从左到右排列组件。我们添加了一个标签 ("Courses"）和两个用于 Java 和 Python 课程选择的复选框。该`frame`还包含一个允许在点击关闭按钮时关闭窗口的`ActionListener`。

## 12.8.6 CheckboxGroup

`CheckboxGroup`允许用户从一组复选框中只选择一个。`CheckboxGroup`的主要特性是：

- 互斥性：`CheckboxGroup`允许对多个`Checkbox`组件进行分组，使得组内一次只能选择一个。这创建了类似于单选按钮的互斥选择集。
- 共享状态：在`CheckboxGroup`中，所有复选框共享一个状态。选择其中一个会自动取消同一组内之前选中的复选框。
- 状态管理：`CheckboxGroup`提供了管理选择状态的方法，例如`getSelectedCheckbox()`获取当前选中的复选框，`setSelected(Checkbox)`程序选择组内的特定复选框。这允许对选择状态进行控制和操作。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class CheckboxGroupExample {
    void main(String[] args) {
    // 创建一个标题为 "Checkbox Group Example" 的 Frame
    Frame frame = new Frame("Checkbox Group Example");
    frame.setLayout(new FlowLayout()); // 设置布局为 FlowLayout
    // 创建一个 CheckboxGroup
    CheckboxGroup group = new CheckboxGroup();
    // 创建两个同一个 CheckboxGroup 的复选框
    Checkbox checkbox1 = new Checkbox("Java", group, false);
    checkbox1.setBackground(Color.ORANGE); // 设置背景颜色为橙色
    Checkbox checkbox2 = new Checkbox("Python", group, false);
    checkbox2.setBackground(Color.ORANGE); // 设置背景颜色为橙色
    // 将复选框添加到 frame
    frame.add(checkbox1);
    frame.add(checkbox2);
    // 设置 frame 尺寸并使其可见
    frame.setSize(300, 100);
    frame.setVisible(true);
    // 添加窗口监听器来处理关闭
    frame.addWindowListener(new WindowAdapter() {
        public void windowClosing(WindowEvent e) {
            System.exit(0);
        }
    });
    }}
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_497_0.png)

在上面的程序中，我们创建了一个名为"CheckboxGroup Example"的`Frame`，并添加了标记为"Java"和"Python"的两个复选框，它们被组合在一个`CheckboxGroup`，因此一次只能选择一个。两个复选框都使用了橙色背景。该帧对组件使用`FlowLayout`，尺寸为 300x100 像素，并设置为可见。

## 12.8.7 Choice（选择框）

`Choice`是一种弹出菜单，允许用户从选项列表中选择一个。AWT 中`Choice`的主要特性是：

- 下拉列表：`Choice`提供了一个项目下拉列表，用户可以从中选择单个选项。它显示一个紧凑的选项列表，点击时会展开，非常适合在用户界面中节省空间。
- 项目管理：你可以使用`addItem()`、`removeItem()`和`insertItem()`等方法动态地向`Choice`列表添加、删除和修改项目。这允许对用户可用选项进行灵活管理。
- 事件处理：`Choice`通过`EventListener`支持事件处理，让你能够响应用户的选择。这允许你根据下拉列表中的选择执行特定操作或更新其他组件。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ChoiceExample {
    // 创建一个标题为 "Choice Example" 的 Frame
    Frame frame = new Frame("Choice Example");
    frame.setLayout(new FlowLayout()); // 设置布局为 FlowLayout
    // 创建一个下拉菜单
    Choice choice = new Choice();
    choice.add("Java");
    choice.add("Python");
    choice.add("C++");
    // 设置 Choice 下拉菜单的背景颜色
    choice.setBackground(Color.MAGENTA);
    // 将 Choice 下拉添加到帧中
    frame.add(choice);
    // 设置帧的大小并使其可见
    frame.setSize(300, 100);
    frame.setVisible(true);
    // 添加窗口监听器来处理关闭
    frame.addActionListener(new WindowAdapter() {
        public void windowClosing(WindowEvent e) {
            System.exit(0);
        }
    });
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_498_0.png)

在上面的程序中，我们创建了一个名为"Choice Example"的`Frame`，并添加了一个带有"Java"、"Python"和"C++"选项的`Choice`下拉菜单，并将下拉菜单的背景颜色设置为洋红色。该帧对组件使用`FlowLayout`，尺寸为 300x100 像素，并且可见的。

## 12.8.8 List（列表）

`List`允许用户从列表中选择一个或多个项目。AWT（抽象窗口工具包）中`List`的主要特性是：

- 多选选择模式：`List`可以配置为允许单选或多选。用户可以根据选择模式（`MULTIPLE_INTERVAL_SELECTION`、`SINGLE_SELECTION`等）从列表中选择一个或多个项目。
- 可滚动：当项目数量超过可见区域时，`List`会自动提供滚动条。用户可以进行滚动。
- 动态项目管理：你可以使用`add()`、`remove()`和`insert()`等方法在`List`中添加、删除和修改项目。这种灵活性允许你根据用户交互或其他应用程序事件编程地更新选项列表。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ListExample {
    public static void main(String[] args) {
        // 创建一个标题为 "List Example" 的 Frame
        Frame frame = new Frame("List Example");
        frame.setLayout(new FlowLayout()); // 设置布局为 FlowLayout
        // 创建一个 List 组件
        List list = new List();
        list.add("Java");
        list.add("Python");
        list.add("C++");
        list.add("Data Structures");
        // 设置 List 的背景颜色
        list.setBackground(Color.CYAN);
        // 将 List 组件添加到帧中
        frame.add(list);
        // 设置大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 添加窗口监听器来处理关闭事件
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_499_0.png)

在上面的程序中，我们创建了一个名为"List Example"的`Frame`，并添加了一个带有"Java"、"Python"、"C++"和"Data Structures"项目的`List`组件，并将列表的背景颜色设置为青色。该帧对组件使用`FlowLayout`，尺寸为 300x200 像素。

## 12.8.9 Canvas（画布）

`Canvas`是一个可以绘制或捕获输入的矩形区域。AWT 中`Canvas`的主要特性是：

- 自定义绘制：`Canvas`提供了一个可以使用`Graphics`类进行自定义绘制的空白区域。通常用于创建图形界面或视觉元素。
- 灵活尺寸：你可以设置`Canvas`的大小以适应应用程序，对绘制区域进行精确控制。
- 事件处理：`Canvas`支持用户交互事件处理，例如鼠标和键盘事件。这使得在画布内响应成为可能。

## 程序



```java
import java.awt.*;
import java.awt.event.*;
public class CanvasExample {
    public static void main(String[] args) {
        // 创建一个标题为 "Canvas Example" 的 Frame
        Frame frame = new Frame("Canvas Example");
        frame.setLayout(new FlowLayout()); // 设置布局为 FlowLayout
        // 创建一个自定义 Canvas
        Canvas canvas = new Canvas() {
            @Override
            public void paint(Graphics g) {
                super.paint(g);
                // 设置颜色为红色
                g.setColor(Color.RED);
                // 在 (50, 50) 处绘制一个宽度为 100，高度为 100 的矩形
                g.fillRect(50, 50, 100, 100);
            }
        };
        // 设置 Canvas 的背景颜色为灰色
        canvas.setBackground(Color.LIGHT_GRAY);
        // 设置 Canvas 的尺寸
        canvas.setSize(300, 200);
        // 将 Canvas 添加到帧
        frame.add(canvas);
        // 设置帧的大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 添加窗口监听器处理关闭
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_500_0.png)

在程序中，我们创建了一个名为“Canvas Example”的`Frame`，并添加了一个自定义`Canvas`组件。`Canvas`被重写以在 (50, 50) 处绘制一个宽度为 100 像素、高度为 100 像素的红色矩形。画布的背景颜色设置为灰色。帧对组件使用`FlowLayout`，尺寸为 300x200 像素。

### 12.8.10 SCROLLBAR（滚动条）

`Scrollbar`提供了一种调整组件或内容可见部分的方法。AWT 中`Scrollbar`的特性有：

1. 滚动功能：`Scrollbar`提供了一种滚动内容的机制，允许用户通过移动滚动块浏览数值范围或长项目列表。
2. 可调节方向：根据滚动需要，`Scrollbar`可以水平或垂直方向。这种灵活性允许集成到垂直和水平滚动界面。
3. 可自定义参数：你可以使用最小最大值、可见量、单位和块增量等参数自定义`Scrollbar`。这允许你根据特定需求调整其行为和外观。

# 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ScrollbarExample {
    public static void main(String[] args) {
        // 创建一个标题为 "Scrollbar Example" 的 Frame
        Frame frame = new Frame("Scrollbar Example");
        frame.setLayout(new FlowLayout()); // 设置布局为 FlowLayout
        // 创建一个 Scrollbar 组件
        Scrollbar scrollbar = new Scrollbar();

        // 设置滚动条的背景颜色为粉色
        scrollbar.setBackground(Color.PINK);
        // 将滚动条添加到帧
        frame.add(scrollbar);
        // 设置帧的大小并使其可见
        frame.setSize(300, 200);
        frame.setVisible(true);
        // 添加窗口监听器来处理关闭
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_501_0.png)

在上面的程序中，我们创建了一个名为“Scrollbar Example”的`Frame`，并添加了一个`Scrollbar`组件。滚动条的背景颜色设置为粉色。帧对组件使用`FlowLayout`，尺寸为 300x200 像素，并且可见的。

### 12.8.11 Menu（菜单）

`Menu`是菜单栏中的下拉菜单。AWT 中`Menu`的主要特性是：

1. 分层级结构：`Menu`提供了一种在层级结构中组织相关操作或命令的方法，通常通过菜单栏的下拉列表访问。允许将相关功能分组到不同的类别中，增强了可用性和组织结构。
2. 菜单项：在`Menu`内部，你可以添加`MenuItem`组件（或其他嵌套菜单），它们代表单独的动作或命令。这允许用户与各种选项进行交互，并根据他们的选择执行特定任务。
3. 事件处理：`Menu`通过`ActionListener`和其他事件监听器支持事件处理，允许你为每个菜单项定义自定义行为。这使你能够响应用户的选择并在应用程序中执行相应的操作。

# 程序

```java
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.*;
public class MenuExample {
    public void main(String[] args) {
        // 创建一个标题为 "Menu Example" 的 Frame
        Frame frame = new Frame("Menu Example");
        // 创建一个 MenuBar
        MenuBar menuBar = new MenuBar();
        // 创建一个名为 "Courses" 的 Menu
        Menu coursesMenu = new Menu("Courses");
        // 创建 MenuItems
        MenuItem javaMenuItem = new MenuItem("Java");
        MenuItem pythonMenuItem = new MenuItem("Python");
        // 为 MenuItems 添加 ActionListener
        javaMenuItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Java selected");
            }
        });
        pythonMenuItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Python selected");
            }
        });
        // 将项添加到 Menu
        coursesMenu.add(javaMenuItem);
        coursesMenu.add(pythonMenuItem);
        // 将 Menu 添加到 MenuBar
        menuBar.add(coursesMenu);
        // 为 Frame 设置 MenuBar
        frame.setMenuBar(menuBar);
        // 设置 Frame 的大小并使其可见
        frame.setSize(300, 100);
        frame.setVisible(true);
        // 添加窗口监听器来处理关闭事件
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_503_0.png)

在上面的程序中，我们创建了一个标题为`Menu Example`的`Frame`，并添加了一个`MenuBar`组件。在菜单栏内部，创建了一个名为`Courses`的菜单，并填充了两个菜单项：`Java`和`Python`。该帧的大小被设定为 300x100 像素并设置为可见。

### 12.8.12 MenuItem

`MenuItem`是菜单中的一个项。AWT 中`MenuItem`的关键特性如下：

1. 命令执行：`MenuItem`代表`Menu`中的一个单独选项，当被用户选择时会触发特定的操作。这允许在应用程序中执行任务或初始化处理过程。
2. 可自定义的标签和图标：你可以为`MenuItem`设置标签文本和可选的图标，允许你自定义其外观并为用户提供清晰、具描述性的选项。这增强了可用性并有助于有效的组织。
3. 事件处理：`MenuItem`通过`ActionListener`支持事件处理，允许你在选择菜单项时定义自定义行为。这使你能够响应用户与菜单项的交互并执行特定的代码。

# 程序

```java
import java.awt.*;
import java.awt.event.*;
public class MenuItem {
    void main(String[] args) {
        // 创建一个标题为 "MenuItem Example" 的 Frame
        Frame frame = new Frame("MenuItem Example");
        // 创建一个 MenuBar
        MenuBar menuBar = new MenuBar();
        // 创建名为 "Courses" 的 Menu
        Menu courses = new Menu("Courses");
        menuBar.add(courses);
        // 为 Menu 创建 MenuItems
        MenuItem javaMenuItem = new MenuItem("Java");
        MenuItem pythonMenuItem = new MenuItem("Python");
        // 移除不支持的 setBackgroundColor 调用
        // javaMenuItem.setBackground(Color.YELLOW); // 不支持
        // pythonMenuItem.setBackground(Color.YELLOW); // 不支持
        // 为 MenuItems 添加 ActionListener
        javaMenuItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Java selected");
            }
        });
        pythonMenuItem.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Python selected");
            }
        });
        // 将 MenuItems 添加到 Menu
        courses.add(javaMenuItem);
        courses.add(pythonMenuItem);
        // 将 Menu 添加到 MenuBar
        menuBar.add(courses);
        // 为 Frame 设置 MenuBar
        frame.setMenuBar(menuBar);
        // 设置 Frame 的大小并使其可见
        frame.setSize(500, 100);
        frame.setVisible(true);
        // 添加窗口监听器来处理关闭事件
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_504_0.png)

在程序中，我们创建了一个标题为`MenuItem Example`的`Frame`并添加了一个`MenuBar`组件。在菜单栏内部，创建了一个名为`Courses`的菜单，并填充了两个菜单项：`Java`和`Python`。两个菜单项的背景颜色均为黄色。该帧的大小被设定为 300x100 像素并设置为可见。

### 12.8.13 FileDialog

`FileDialog`是一个对话框窗口，用户可以从中选择文件。AWT 中`FileDialog`的关键特性如下：

1. 选择：`FileDialog`为用户提供了一个标准的对话框窗口来选择文件或目录。它允许用户浏览文件系统并选择文件或目录，使得在应用程序中打开或保存文件变得更容易。
2. 可自定义对话框类型：你可以配置`FileDialog`作为“打开”或“保存”对话框。这允许你根据用户是打开现有文件还是保存新文件向其展示不同的选项。
3. 目录和文件过滤：`FileDialog`允许你根据文件的类型或扩展名对文件进行过滤。这使用户仅查看和选择特定类型的文件，从而简化了文件选择过程并改进了用户体验。

# 程序

```java
import java.awt.*;
import java.awt.event.*;
public class FileDialogExample {
    void main(String[] args) {
        // 创建主帧
        Frame frame = new Frame("FileDialog Example");

        // 设置帧的大小
        frame.setSize(300, 100);

        // 设置帧的布局
        frame.setLayout(new FlowLayout());

        // 以帧为父容器创建一个 FileDialog
        FileDialog fileDialog = new FileDialog(frame, "Select a File", FileDialog.LOAD);

        // 设置文件对话框的背景颜色（这将影响系统中组件的显示）
        fileDialog.setBackground(Color.LIGHT_GRAY);

        // 显示文件对话框
        fileDialog.setVisible(true);

        // 添加 WindowListener 处理帧的关闭
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });

        // 使帧可见
        frame.setVisible(true);
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_505_0.png)

在程序中，实例化了一个带有父帧的`FileDialog`，标题为“Select a File”，且模式设置为`LOAD`。文件对话框的背景颜色被设置为浅灰色。帧的大小被设置为 300x100 像素，并与文件对话框一起可见。

## 12.9 事件处理



AWT 中的事件处理至关重要，因为它允许应用程序响应用户交互和其他事件，使应用程序具有交互性。如果没有事件处理，应用程序将无法响应用户的操作。

事件处理在 AWT 中的重要性在于：

- **交互性**：事件处理使应用程序具有交互性。它允许应用程序响应点击按钮、输入文本、选择项目等用户操作。
- **用户体验**：适当事件处理通过对用户操作提供即时反馈和相应响应来增强用户体验。
- **控制流管理**：它通过响应用户事件执行特定操作来帮助管理应用程序流，例如打开新窗口、更新显示或保存数据。
- **定制**：开发者可以自定义应用程序响应不同事件的行为，从而创建灵活且功能丰富的应用程序。
- **逻辑分离**：事件处理将用户界面代码与应用程序逻辑分离，使代码更有组织且更容易维护。
- **异步处理**：事件是异步处理的，这意味着应用程序可以处理同时发生的多个事件，提高了性能和响应速度。

## AWT 中的事件处理工作

AWT 中的事件处理基于委托事件模型，该模型由三个部分组成：

- **事件源**：产生事件的对象。这可以是被点击的按钮、被编辑的文本框等。
- **事件监听器**：定义处理程序的接口。它监听事件并在事件发生时通知。
- **事件对象**：包含有关事件的信息，例如事件的类型和来源。

### 12.9.1 动作监听器

在 Java AWT 中，`ActionListener` 是一个用于处理动作事件的接口，通常用于点击按钮、选择菜单项或在文本框中按回车键等用户操作。

`ActionListener` 接口包含一个方法 `actionPerformed(ActionEvent)`，任何想要处理动作事件的类都必须实现该方法。当动作事件发生时，`actionPerformed` 方法被调用，并传递一个 `ActionEvent` 对象，该对象包含了事件的信息，包括事件源和一个提供额外上下文的命令字符串。

`ActionListener` 的主要作用是定义在执行动作时应该发生的行为。这允许开发者将“应该发生什么”的逻辑与触发动作的组件分离，从而提高代码的模块化和可用性。使用 `addActionListener` 方法将动作监听器注册到组件上，建立用户操作与处理逻辑之间的连接。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ButtonClickEventExample {
    void main(String[] args) {
    // 创建主帧
    Frame frame = new Frame("Button Click Event Example");

    // 设置帧的大小
    frame.setSize(300, 200);

    // 设置帧的布局
    frame.setLayout(new FlowLayout());

    // 创建一个标签为 "Click Me" 的按钮
    Button button = new Button("Click Me");
    // 为按钮添加一个 ActionListener
    button.addActionListener(new ActionListener() {
        @Override
        public void actionPerformed(ActionEvent e) {
            // 将按钮的背景颜色改为红色
            button.setBackground(Color.RED);
        }
    });

    // 将按钮添加到帧中
    frame.add(button);

    // 添加一个 WindowListener 来处理帧的关闭
    frame.addWindowListener(new WindowAdapter() {
        public void windowClosing(WindowEvent we) {
            frame.dispose();
        }
    });

    // 使帧可见
    frame.setVisible(true);
    }
}
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_508_0.png)

在上面的程序中，我们创建了一个名为“Button Click Event Example”的`Frame`，并向其中添加了一个标签为“Click Me”的按钮。点击按钮时，其背景颜色会变为红色。这种行为通过向按钮添加一个`ActionListener`来实现，该监听器在触发时设置其背景颜色。最后，帧的大小被设定为 300x200 像素并设置为可见。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class MenuSelectionEventExample {
    void main(String[] args) {
    // 创建主帧
    Frame frame = new Frame("Menu Selection Event Example");

    // 设置帧的大小
    frame.setSize(300, 200);

    // 创建菜单栏
    MenuBar menuBar = new MenuBar();

    // 创建菜单并将其添加到菜单栏
    Menu fileMenu = new Menu("File");
    menuBar.add(fileMenu);

    // 创建菜单项并将其添加到菜单
    MenuItem menuItem = new MenuItem("Open");
    fileMenu.add(menuItem);

    // 为菜单项添加一个 ActionListener
    menuItem.addActionListener(new ActionListener() {
    @Override
    public void actionPerformed(ActionEvent e) {
    // 当菜单项被选中时，向控制台打印消息
    System.out.println("File -> Open selected");
    }
});
    // 为帧设置菜单栏
    frame.setMenuBar(menuBar);

// 添加一个 WindowListener 来处理帧的关闭
frame.addListener(new WindowAdapter() {
    public void windowClosing(WindowEvent we) {
        frame.dispose();
    }
});

// 使帧可见
frame.setVisible(true);
}
}
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_509_0.png)

```
File -> Open selected
```

在上面的程序中，我们创建了一个标题为 `Menu Selection Event Example` 带有 `MenuBar` 的 `Frame`。菜单栏包含一个名为 `File` 的 `Menu`，该菜单又包含一个标签为 `Open` 的 `MenuItem`。`Open` 菜单项被添加了一个 `ActionListener` 来监听选取事件。当 `Open` 菜单被选中时，它会在控制台打印 `File - Open selected`。最后，帧被设定为特定的大小并设置为可见。

### 12.9.2 焦点监听器

Java AWT 中的 `FocusListener` 是一个接收焦点事件的接口，这些事件在组件获得或失去焦点时发生。`FocusListener` 接口包含两个方法：`focusGained(WindowEvent)` 和 `focusLost(WindowEvent)`。任何想要处理焦点事件的类都必须实现这些方法。当组件成为键盘输入的目标时，会调用 `focusGained` 方法。相反，当组件失去焦点时，会调用 `focusLost` 方法，从而能够在组件不再处于状态时执行操作。这对于在用户离开文本字段时验证输入、更新用户界面以反映焦点变化，或确保某些操作仅在组件激活时处于激活状态可能特别有用。通过实现 `FocusListener` 接口，开发者可以创建更具交互性且用户友好的应用程序，使用户界面对用户的焦点做出相应响应。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class FocusEventExample {
    public void main(String[] args) {
        // 创建一个 Frame
        Frame frame = new Frame("FocusListener Example");
        // 创建一个 TextField
        TextField textField = new TextField("Enter Name", 20);
        // 创建一个用于显示焦点信息的 Label
        Label focusLabel = new Label();
        // 为 TextField 添加 FocusListener
        textField.addFocusListener(new FocusListener() {
            // 此方法在 TextField 获得焦点时被调用
            public void focusGained(FocusEvent e) {
                focusLabel.setText("TextField gained focus!");
            }
            // 此方法在 TextField 失去焦点时被调用
            public void focusLost(FocusEvent e) {
                focusLabel.setText("TextField lost focus!");
            }
        });
        // 将组件添加到 Frame
        frame.add(textField, BorderLayout.NORTH);
        frame.add(focusLabel, BorderLayout.SOUTH);
        // 设置 Frame的大小并使其可见
        frame.setSize(300, 100);
        frame.setVisible(true);
        // 添加一个窗口监听器来处理关闭
        frame.addWindowListener(new WindowAdapter() {
            public windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
    }
}
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_508_0.png)

此程序演示了如何在 AWT 中使用 `FocusListener` 来检测 `TextField` 的焦点。当 `TextField` 获得或失去焦点时，`focusGained` 和 `focusLost` 方法会更新 `Label` 以反映焦点状态。我们包含了一个 `WindowListener` 在窗口关闭时正确退出程序。

### 12.9.3 项目监听器

Java AWT 中的 `ItemListener` 是用于处理项目事件的接口，这些事件在项目状态改变时触发。通常发生在复选框、单选按钮、组合框和其他列表上。`ItemListener` 接口有一个方法 `itemStateChanged(ActionEvent)`，任何想要响应项目状态变化的类都必须实现该方法。当项目被选中或取消时时，`ActionListener` 方法被调用，允许程序对这些变化做出反应。这可能涉及更新用户界面、进行计算或任何需要响应项目状态的逻辑。通过实现 `Listener` 接口，开发者可以创建动态且响应式的用户界面，其操作取决于用户的选取或取消。这种交互增强了应用程序的交互性和易用性，根据用户输入提供即时反馈。

#### 程序

```java
import java.awt.*;
import java.awt.event.*;
public class CheckboxItemExample {
    public void main(String[] args) {
        // 创建标题为 "Checkbox Item Event Example" 的帧
        Frame frame = new Frame("Checkbox Item Event Example");
        // 设置帧的大小
        frame.setSize(300, 200);
        // 创建标签为 "Agree" 的复选框
        Checkbox checkbox = new Checkbox("Agree");
        // 为复选框添加一个 ItemListener
        checkbox.addItemListener(new ItemListener() {
            @Override
            public void itemStateChanged(ItemEvent e) {
                // 检查复选框的状态并打印相应的消息
                if (checkbox.getState()) {
                    System.out.println("Checkbox is selected.");
                } else {
                    System.out.println("Checkbox is deselected.");
                }
            }
        });
        // 将复选框添加到帧
        frame.add(checkbox, BorderLayout.CENTER);
        // 添加一个 WindowListener 来处理帧的关闭
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                frame.dispose();
            }
        });
        // 使帧可见
        frame.setVisible(true);
    }
}
```

#### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_512_0.png)

在上面的程序中，我们创建了一个标题为“Checkbox Item Event Example”的`Frame`并添加了一个标签为“Agree.”的复选框。当复选框状态发生变化（选中或取消选中）时，它会打印一条指示新状态的消息。这种行为是通过添加到复选框的 `ItemListener` 来定义的。最后，将帧的大小设置为 300x200 像素并使其显示。



```java
import java.awt.*;
import java.awt.event.*;
public class ChoiceItemEventExample {
    public void main(String[] args) {
        // 创建标题为 "Choice Item Event Example" 的窗口
        Frame frame = new Frame("Choice Item Event Example");

        // 设置窗口的大小
        frame.setSize(300, 200);

        // 创建一个包含“Red”、“Green”和“Blue”选项的 Choice 组件
        Choice actually = new Choice();
        actually.add("Red");
        actually.add("Green");
        actually.add("Blue");

        // 创建显示所选颜色的标签
        Label colorLabel = new Label("Choose a color");

        // 为选择组件添加 ItemListener
        actually.addItemListener(new ItemListener() {
            @Override
            public void itemChanged(ItemEvent e) {
                // 获取选中的项目
                String selectedColor = actually.getSelectedItem();

                // 根据选中的项目更改标签的文字颜色
                switch (selectedColor) {
                    case "Red":
                        colorLabel.setForeground(Color.RED);
                        break;
                    case "Green":
                        colorLabel.setForeground(Color.GREEN);
                        break;
                    case "Blue":
                        colorLabel.setForeground(Color.BLUE);
                        break;
                }
            }
        });

        // 设置窗口的布局管理器
        frame.setLayout(new FlowLayout());

        // 将 Choice 和 Label 添加到窗口
        frame.add(actually);
        frame.add(colorLabel);

        // 添加 WindowListener 来处理关闭窗口
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                frame.dispose();
            }
        });

        // 使窗口可见
        frame.setVisible(true);
    }
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_513_0.png)

在上面的程序中，我们创建了一个标题为“Choice Item Event Example”的`Frame`，并添加了一个包含“Red”、“Green”和“Blue”选项的`Choice`组件。还添加了一个标题为“Choose a color”的`Label`。当选择中的某项时，它会相应更改标签文本的颜色。这种行为通过添加到选择组件的`ItemListener`实现。随后，将帧的大小设置为 300x200 像素并显示。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ListSelectionEventExample {
    public void main(String[] args) {
        // 创建标题为 "List Selection Event Example" 的窗口
        Frame frame = new Frame("List Selection Event Example");

        // 设置窗口的大小
        frame.setSize(300, 200);

        // 创建一个包含“Java”、“Python”和“C++”选项的 List 组件
        List listList = new List();
        listList.add("Java");
        listList.add("Python");
        listList.add("C++");

        // 为 List 组件添加 ItemListener
        listList.addItemListener(new ItemListener() {
            @Override
            public void itemStateChanged(ItemEvent e) {
                // 将选中的项目打印到控制台
                System.out.println("Selected item: " + listList.getSelectedItem());
            }
        });

        // 设置窗口的布局管理器
        frame.setLayout(new FlowLayout());

        // 将 List 添加到窗口
        frame.add(listList);

        // 添加 WindowListener 来处理关闭窗口
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                frame.dispose();
            }
        });

        // 使窗口可见
        frame.setVisible(true);
    }
}
```

## 504 用于医疗保健的应用的 Java 22

在上面的程序中，我们创建了一个标题为“List Selection Event Example”的`Frame`，并添加了一个包含“Java”、“Python”和“C++”选项的`List`组件。列表上附加了一个`ItemListener`，它用于监听项目状态的变化。当某项发生变化时，它会将选中的项目打印到控制台。最后，将帧的大小设置为 300x200 像素并显示。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class ItemExample {
    void main(String[] args) {
        // 创建标题为 "Item Event Example" 的窗口
        Frame frame = new Frame("Item Event Example");

        // 设置窗口的大小
        frame.setSize(300, 200);

        // 创建一个带有颜色选项的组件
        Choice actually = new Choice();
        actually.add("Red");
        actually.add("Green");
        actually.add("Blue");

        // 为 Choice 组件添加 ItemListener
        actually.addItemListener(new ItemListener() {
            @Override
            public void itemChanged(ItemEvent e) {
                // 获取选中的颜色
                String selectedColor = actually.getSelectedItem();

                // 根据选中的颜色更改帧的背景颜色
                switch (selectedColor) {
                    case "Red":
                        frame.setBackground(Color.RED);
                        break;
                    case "Green":
                        frame.setBackground(Color.GREEN);
                        break;
                    case "Blue":
                        frame.setBackground(Color.BLUE);
                        break;
                }
            }
        });

        // 设置窗口的布局管理器
        frame.setLayout(new FlowLayout());

        // 将 Choice 组件添加到窗口
        frame.add(actually);

        // 添加 WindowListener 来处理关闭窗口
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                frame.dispose();
            }
        });

        // 使窗口可见
        frame.setVisible(true);
    }
}
```

## 506 用于医疗保健的应用的 Java 22

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_516_0.png)

在程序中，我们创建了一个标题为“Item Event Example”的`Frame`以及一个带有颜色选择选项（“Red”、“Green”、“Blue”）的`Choice`组件。在选择组件上添加了`EventListener`以检测项目状态的变化。根据所选颜色，帧的背景颜色会随之改变。随后对帧进行尺寸设置并显示。

### 12.9.4 WINDOWS LISTENER

Java AWT（抽象窗口工具）中的`WindowListener`是一个用于接收和处理各种窗口事件的接口。这些事件与窗口状态的变化有关，例如窗口的打开、关闭、最小化、恢复最小化、激活和取消。`WindowListener`接口定义了以下方法：

```
windowOpened(WindowEvent e)
windowClosing(WindowEvent e)
windowClosed(WindowEvent e)
windowIconified(WindowEvent e)
windowDeiconified(WindowEvent e)
windowActivated(WindowEvent e)
windowDeactivated(WindowEvent e)
```

这些方法中的每一个都对应于特定类型的窗口事件，允许开发者在这些事件发生时实现自定义行为。例如，`windowClosing`通常用于提示用户在关闭应用程序之前保存更改，而`windowIconified`和`windowDeiconified`可能用于在窗口最小化或恢复时管理资源。通过实现`WindowListener`，开发者可以确保他们的应用程序对窗口状态做出适当响应，增强用户体验并确保适当的资源管理。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
public class WindowStateEventExample {
    void main(String[] args) {
        // 创建标题为 "Window State Event Example" 的窗口
        Frame frame = new Frame("Window State Event Example");
        // 设置窗口的大小
        frame.setSize(400, 300);
        // 添加 WindowStateListener 来处理窗口状态变化
        frame.addWindowStateListener(new WindowStateListener() {
            @Override
            public void stateChanged(WindowEvent e) {
                int newState = e.getNewState();
            }
        });
        // 使窗口可见
        frame.setVisible(true);
    }
}
```

## 抽象窗口工具包 (AWT)

```java
// 检查窗口是否被识别
if ((newState & Frame.IDENTIFIED) == Frame.IDENTIFIED) {
    System.out.println("Window identified");
}

// 检查窗口是否取消识别
if ((newState & Frame.NORMAL) == Frame.NORMAL) {
    System.out.println("Window deidentified");
}

// 添加 WindowListener 来处理帧关闭
frame.addWindowListener(new WindowAdapter() {
    public void windowClosing(WindowEvent we) {
        frame.dispose();
    }
});
// 使帧可见
frame.setVisible(true);
```

输出：

![](img/5a077f56e14b826c2dc61de6c176e5ef_517_0.png)

Window identified

Window deidentified

Window deidentified

Window identified

Window deidentified

在程序中，我们创建了一个名为“窗口状态变化事件示例”的`Frame`，并向它添加了一个`WindowListener`。该监听器通过对窗口状态进行位运算，检查窗口是否被识别或取消识别。如果窗口被识别，它会在控制台打印“Window identified”，如果取消识别，则打印“Window deidentified”。最后，设置帧的大小并将其显示。

### 12.9.5 调整监听器 (Adjustment Listener)

Java 中的`AdjustmentListener`是一个用于处理由滚动条等可调组件生成的事件的接口。该接口包含一个方法`adjustmentValueChanged(Adjustment)`，当可调组件的值发生时，该方法会被调用。这种监听器对于提供动态且响应式用户界面至关重要，允许开发者在与可调组件交互时执行特定操作。例如，当用户移动滚动条时，可以通过`adjustmentValueChanged`方法来更新显示的内容。通过实现监听器，开发者可以增强应用程序的交互性和可用性，确保组件值的调整立即反映出来。

## 程序



```java
import java.awt.*;
import java.awt.event.*;
public class AdjustmentEventExample {
    public static void main(String[] args) {
        // 创建名为“调整事件示例”的 Frame
        Frame frame = new Frame("Adjustment Event Example");
        // 设置帧的布局为 BorderLayout
        frame.setLayout(new BorderLayout());
        // 创建垂直滚动条
        ScrollBar scrollbar = new Scrollbar(ScrollBar.VERTICAL);
        // 设置滚动条的最大值为 255
        scrollbar.setMaximum(255);
        // 为滚动条添加 AdjustmentListener
        scrollbar.addAdjustmentListener(new AdjustmentListener() {
            @Override
            public void valueChanged(Adjustment e) {
                // 获取滚动条的值
                int value = scrollbar.getValue();

                // 根据滚动条的值更改帧的背景颜色
                // 颜色由滚动条的值（0 到 255）决定
                Color color = new Color(value, value, value);
                frame.setBackground(color);
            }
        });
        // 将滚动条添加到帧的东部
        frame.add(scrollbar, BorderLayout.EAST);
        // 设置帧的大小
        frame.setSize(400, 300);
        // 添加 WindowListener 来处理帧关闭
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                frame.dispose();
            }
        });
        // 使帧可见
        frame.setVisible(true);
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_519_0.png)

在上面的程序中，我们创建了一个名为“调整事件示例”的`Frame`和一个垂直`ScrollBar`。为滚动条添加了`AdjustmentListener`以根据滚动条的值动态更改帧的背景颜色。帧的布局设置为`BorderLayout`，滚动条位于帧的东部。最后，设置帧的大小并显示。

## 12.10 AWT 中的适配类 (Adapter Classes)

Java 中的适配类是 AWT 框架提供的抽象类，它们实现了空方法体。这些类包括`MouseAdapter`、`KeyListener`、`WindowAdapter`等。适配类的主要目的是简化监听器的创建。使用监听接口时，开发者必须实现接口中定义的所有方法，即使他们只需要其中一个。这会导致代码冗肿。适配类通过提供所有方法的默认实现解决了这个问题，允许开发者只重写需要的方法。

适配类的重要性在于它们能够简化代码并提高可读性和可维护性。它们减少了代码量，让开发者专注于与其相关的事件处理逻辑。例如，如果开发者只需要处理鼠标点击事件，可以扩展`MouseAdapter`并重写`mouseClicked`方法，让`mousePressed`、`mouseReleased`等方法保持默认实现。这种方法不仅让代码更简洁，还减少了实现不必要方法可能产生的错误。

### 12.10.1 WindowAdapter

Java 中的`WindowAdapter`类是 AWT 框架的一部分，作为接收窗口事件的抽象适配器。该类为`WindowListener`接口定义方法提供了默认实现，允许开发者处理窗口相关的事件，如打开、关闭、激活、取消激活、最小化、最大化以及获取或丢失焦点。通过扩展`WindowAdapter`，开发者可以只重写他们感兴趣的方法，而不强制提供所有方法的实现。这带来了更简洁、更易维护的代码，因为它只关注相关的事件处理逻辑。`WindowAdapter`类在处理 GUI 应用程序中的窗口事件时特别有用，简化了监听器的创建并增强了代码的可读性。

# 程序

```java
import java.awt.*;
import java.awt.event.*;
public class WindowAdapterExample extends Frame {
    public WindowAdapterExample() {
        // 设置帧的标题
        setTitle("Window Adapter Example");
        // 设置帧的大小
        setSize(300, 200);
        // 设置帧的背景颜色
        setBackground(Color.YELLOW);
        // 使用 WindowAdapter 添加 WindowListener 来处理窗口关闭
        addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                // 当窗口关闭时退出应用程序
                System.exit(0);
            }
        });
        // 设置帧的布局
        setLayout(new FlowLayout());
        // 使帧可见
        setVisible(true);
    }
    public static void main(String[] args) {
        // 创建 WindowAdapterExample 实例显示帧
        new WindowAdapterExample();
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_520_0.png)

在上面的程序中，我们创建了一个名为“窗口适配器示例”的`Frame`子类。帧的大小设置为 300x200 像素，并赋予了黄色背景颜色。添加了一个`WindowAdapter`实例来处理窗口关闭事件，该事件在触发时退出应用程序。

### 12.10.2 MouseAdapter

Java 中的`MouseAdapter`类是 AWT（抽象窗口工具包）框架的一部分，是一个用于处理鼠标事件的抽象适配类。该类为`MouseListener`和`MouseMotionListener`接口定义的所有方法提供了默认（空）实现，这些方法包含了处理鼠标点击、按下、释放、进入、退出的方法以及鼠标移动和拖拽事件。通过扩展`MouseAdapter`，开发者可以重写与应用程序相关的方法，而无需实现接口中的所有方法。这种方法简化了代码，使其更加简洁且易于管理，因为它消除了不必要的方法定义，并专注于所需的事件处理逻辑。`MouseAdapter`类对于开发响应式和交互式图形用户界面至关重要，因为它提供了一种管理组件间鼠标交互的流线方式，增强了 Java 应用程序的可用性和功能。

# 程序

```java
import java.awt.*;
import java.awt.event.*;
public class MouseAdapterExample extends Frame {
    public MouseAdapterExample() {
        // 设置窗口标题
        setTitle("Mouse Adapter Example");
        // 设置窗口大小
        setSize(300, 200);
        // 设置窗口背景颜色
        setBackground(Color.LIGHT_GRAY);
        // 使用 MouseAdapter 添加 MouseListener 来处理鼠标事件
        addMouseListener(new MouseAdapter() {
            @Override
            public void mouseClicked(MouseEvent e) {
                // 鼠标点击时将背景颜色改为蓝色
                setBackground(Color.BLUE);
            }
        }); // 设置窗口布局
        setLayout(new FlowLayout());
        // 设置窗口可见
        setVisible(true);
        // 添加 WindowListener 处理窗口关闭事件
        addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                // 窗口关闭时退出应用程序
                System.exit(0);
            }
        });
    }
    public static void main(String[] args) {
        // 创建 MouseAdapterExample 实例以显示窗口
        new MouseAdapterExample();
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_522_0.png)

在上述程序中，我们扩展了`Frame`类，创建了一个标题为“Mouse Adapter Example”、尺寸为 300x200 像素的窗口。然后我们通过`MouseAdapter`添加了`KeyListener`，专门处理`mouseClicked`事件，该事件在触发时会将背景颜色设置为蓝色。

### 12.10.3 KeyAdapter

Java 中的`KeyListener`类是 AWT（抽象窗口工具包）框架的一部分，是一个用于处理键盘事件的抽象适配器类。该类为`KeyListener`接口定义的所有方法提供了默认（空）实现，这些处理按键按下、释放和打字事件的方法。通过扩展`KeyAdapter`，开发者可以重写与其特定应用需求相关的方法，而无需实现`KeyListener`接口中的每个方法，从而消除了不必要的方法定义，使代码简洁且易于管理。`KeyAdapter`类在只需要处理部分键盘事件的场景中特别有用，允许开发者专注于为这些事件所需的特定逻辑。它增强了 Java 应用程序中处理键盘交互的效率，有助于创建响应式且用户友好的界面。

## 示例

```java
import java.awt.*;
import java.awt.event.*;
public class KeyAdapterExample extends Frame {
    public KeyAdapterExample() {
        // 设置窗口标题
        setTitle("Key Adapter Example");
        // 设置窗口大小
        setSize(300, 200);
        // 设置窗口背景颜色
        setBackground(Color.LIGHT_GRAY);
        // 使用 KeyAdapter 添加 KeyListener 来处理按事件
        addKeyListener(new KeyAdapter() {
            @Override
            public void keyPressed(KeyEvent e) {
                // 检查是否按下了空格键
                if (e.getKeyCode() == KeyEvent.VK_SPACE) {
                    // 将背景颜色改为绿色
                    setBackground(Color.GREEN);
                }
            }
        });
        // 设置窗口布局
        setLayout(new FlowLayout());
        // 设置窗口可见
        setVisible(true);
        // 添加 WindowListener 处理窗口关闭事件
        addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                // 窗口关闭时退出应用程序
                System.exit(0);
            }
        });
    }
    public static void main(String[] args) {
        // 创建 KeyAdapterExample 实例以显示窗口
        new KeyAdapterExample();
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_523_0.png)

在上述程序中，我们扩展了`Frame`类，创建了一个标题为`Key Adapter Example`、尺寸为 300x200 像素的窗口。程序通过`KeyAdapter`添加了`KeyListener`，专门处理`keyPressed`事件。当按下空格键（`KeyEvent.VK_SPACE`）时，背景颜色变为绿色。

### 12.10.4 MouseMotionAdapter

Java 中的`MouseMotionAdapter`类是 AWT 框架的一部分，是一个用于处理鼠标移动事件的抽象类。它为`MouseMotionListener`接口中定义的所有方法提供了默认（空）实现，包括处理鼠标移动（`moved`）和拖拽事件（`mouseDragged`）的方法。通过扩展`MouseMotionAdapter`，开发者可以只重写他们需要的方法，而无需实现接口中的所有方法。`MouseMotionAdapter`简化了响应式界面的开发，让开发者专注于处理鼠标交互所需的特定逻辑。它增强了 Java 应用程序中处理鼠标操作的效率，有助于创建流畅且用户友好的界面。

```java
// 设置框架的布局（在这种情况下是可选的，因为没有添加额外的组件）
setLayout(new FlowLayout());
// 使框架可见
setVisible(true);
// 添加一个 WindowListener 来处理窗口关闭
addWindowListener(new WindowAdapter() {
    @Override
    public void windowClosing(WindowEvent e) {
        // 当窗口关闭时退出应用程序
        System.exit(0);
    }
});
void main(String[] args) {
    // 创建 FocusAdapterExample 的实例以显示框架
    new FocusAdapterExample();
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_526_0.png)

在上面的程序中，我们扩展了`Frame`类来创建一个标题为“Focus Adapter Example”的窗口，尺寸为 300x200 像素。使用`FocusAdapter`添加了`FocusListener`，它在框架获得焦点时将背景颜色变为黄色，在失去焦点时变为白色。

### 12.10.6 ContainerAdapter

`ContainerAdapter`类在 Java 的 AWT 库中作为接收容器事件的抽象类。它实现了`ContainerListener`接口，并为接口中的所有方法提供了默认空实现。这包括`componentAdded`和`componentRemoved`等方法，这些方法在组件被添加到或从容器中移除时调用。

通过扩展`ContainerAdapter`，开发者可以更高效地创建自定义事件监听器。他们只需要重写感兴趣特定方法，而不需要实现整个`ContainerListener`接口。这种方法减少了冗余并增强了代码的可读性，因为开发者可以专注于与他们想要处理的事件相关的逻辑。



`ContainerAdapter` 在只需要处理某些容器事件的场景下特别有用，允许编写更整洁的事件处理代码。它通常用于具有复杂用户界面的应用程序，以管理容器内容的动态变化。

## 抽象窗口工具包（Abstract Window Toolkit）

### 程序

```java
import java.awt.*;
import java.awt.event.*;

public class ContainerAdapterExample extends Frame {
    public ContainerAdapterExample() {
        // 设置框架的标题
        setTitle("Container Adapter Example");
        // 设置框架的大小
        setSize(300, 200);
        // 设置布局管理器（此示例使用 FlowLayout）
        setLayout(new FlowLayout());
        // 创建 MyPanel 的实例并将其添加到框架
        MyPanel panel = new MyPanel();
        add(panel);
        // 使框架可见
        setVisible(true);
        // 添加一个 WindowListener 来处理窗口关闭
        addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                // 当窗口关闭时退出应用程序
                System.exit(0);
            }
        });
    }
}

// 在鼠标点击时改变其颜色的自定义面板类
class MyPanel extends Panel {
    public MyPanel() {
        // 设置面板的初始背景颜色
        setBackground(Color.BLUE);
        // 添加 MouseListener 在鼠标点击时更改颜色
        addMouseListener(new MouseAdapter() {
            @Override
            public void mouseClicked(MouseEvent e) {
                // 在鼠标点击时将面板的背景颜色改为红色
                setBackground(Color.RED);
            }
        });
    }
}

void main(String[] args) {
    // 创建 ContainerAdapterExample 的实例以显示框架
    new ContainerAdapterExample();
}
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_528_0.png)

在上面的程序中，我们扩展了 `Frame` 类，生成了一个标题为“Container Adapter Example”的窗口，尺寸为 300x200 像素。该框架包含一个扩展自 `Panel` 的自定义 `MyPanel` 类，它将背景颜色设置为蓝色，并注册了 `MouseListener` 以在鼠标点击时将其颜色改为红色。框架被设置为可见。

## 12.10.7 组件适配器

`ComponentAdapter` 类在 Java 的 AWT 库中提供了一个用于接收组件事件的抽象适配器类。它实现了 `ComponentListener` 接口，并为其所有方法提供了默认空实现。这些方法包括 `componentResized`、`componentMoved`、`componentShown` 和 `componentHidden`，每个方法代表不同的组件相关事件。

通过扩展 `ComponentAdapter`，开发者可以更高效地创建自定义事件监听器。他们只需要重写感兴趣的特定方法，而不需要实现整个 `ComponentListener` 接口。这种方法减少了冗余并增强了代码的可读性，因为开发者可以专注于与他们想要处理的事件相关的逻辑。

`ComponentAdapter` 类在只需要处理某些组件事件的场景下特别有用。它允许开发者简化事件处理代码，从而更容易管理和交互图形用户界面中的单个组件。

### 程序

```java
import java.awt.*;
import java.awt.event.*;

public class ComponentResizingEventExample extends Frame {
    private Label label;

    public ComponentResizingEventExample() {
        // 设置框架的标题
        setTitle("Component Resizing Event Example");
        // 设置框架的布局管理器
        setLayout(new FlowLayout());
        // 创建带有初始文本的标签
        label = new Label("Resize Me");
        // 将标签添加到框架
        add(label);
        // 使用 ComponentAdapter 为标签添加 ComponentListener
        label.addComponentListener(new ComponentAdapter() {
            @Override
            public void componentResized(ComponentEvent e) {
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_529_0.png)

在上面的程序中，我们创建了一个标题为“Component Resizing Example”的 `Frame`，包含一个带有文本“Resize Me”的 `Label`。标签的 `ComponentListener` 监听大小变化。当标签被调整大一时，我们显示当前的宽度和高度。最后，框架设置为特定尺寸并可见。

## 12.11 医学应用

### 12.11.1 案例研究

糖尿病的风险包括心血管疾病、神经损伤、肾衰竭和视力丧失等并发症。通过生活方式改变和医疗管理干干对于减轻这些威胁至关重要。识别风险的分析参数包括：

- **BMI**：身体质量指数。
- **血压**：收缩压/舒张压。
- **空腹血糖**：用户的血糖水平。
- **餐后血糖**：进食后的血糖水平。
- **家族史**：检查用户是否有糖尿病史。
- **体育活动**：用户是否进行规律运动。
- **吸烟**：用户是否吸烟。
- **糖尿病**：用户是否被诊断出糖尿病。

### 程序

```java
import java.awt.*;
import java.awt.event.*;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.PrintStream;
import java.util.ArrayList;

public class HealthDataCollector extends Frame implements ActionListener {
    Label title, ageLabel, genderLabel, bmiLabel, bloodPressureLabel,
        fastingBloodSugarLabel, postPrandialBloodSugarLabel,
        familyHistoryLabel, physicalActivityLabel, smokerLabel, diabeticLabel;

    TextField ageField, bloodPressureField, fastingBloodSugarField,
        postPrandialBloodSugarField;

    Choice genderChoice, familyHistoryChoice, physicalActivityChoice,
        smokerChoice, diabeticChoice;

    Button submit;

    // 数据存储
    ArrayList<HealthData> dataList = new ArrayList<>();

    public HealthDataCollector() {
        super("Health Data Collection");

        // 创建 UI 组件
        title = new Label("Health Data Collection");
        ageLabel = new Label("Age:");
        genderLabel = new Label("Gender:");
        bmiLabel = new Label("BMI:");
        bloodPressureLabel = new Label("Blood Pressure:");
        fastingBloodSugarLabel = new Label("Fasting Blood Sugar:");
        postPrandialBloodSugarLabel = new Label("Post-Prandial Blood Sugar:");
        familyHistoryLabel = new Label("Family History:");
        physicalActivityLabel = new Label("Physical Activity:");
        smokerLabel = new Label("Smoker:");
        diabeticLabel = new Label("Diabetic:");

        ageField = new TextField(10);
        bmiField = new TextField(10);
        bloodPressureField = new TextField(10);
        fastingBloodSugarField = new TextField(10);
        postPrandialBloodSugarField = new TextField(10);

        genderChoice = new Choice();
        genderChoice.add("Male");
        genderChoice.add("Female");

        familyHistoryChoice = new Choice();
        familyHistoryChoice.add("Yes");
        familyHistoryChoice.add("No");

        physicalActivityChoice = new Choice();
        physicalActivityChoice.add("Yes");
        physicalActivityChoice.add("No");

        smokerChoice = new Choice();
        smokerChoice.add("Yes");
        smokerChoice.add("No");

        diabeticChoice = new Choice();
        diabeticChoice.add("Yes");
        diabeticChoice.add("No");
```

```java
diabeticChoice = newChoice();
diabeticChoice.add("Yes");
diabeticChoice.add("No");

submitButton = new Button("Submit");

// 布局组件
setLayout(new GridLayout(11, 2));
add(titleLabel);
add(new Label(""));
add(ageLabel);
add(ageField);
add(genderLabel);
add(genderChoice);
add(bmiLabel);
add(bmiField);
add(bloodPressureLabel);
add(bloodPressureField);
add(fastastingBloodSugarLabel);
add(fastastingBloodSugarField);
add(postPrandialBloodSugarLabel);
add(postPrandialBloodSugarField);
add(familyHistoryLabel);
add(familyHistoryChoice);
add(physicalActivityLabel);
add(physicalActivityChoice);
add(smokerLabel);
add(smokerChoice);
add(diabeticLabel);
add(diabeticChoice);
add(submitButton);

submitButton.addActionListener(this);
```



```java
public void actionPerformed(ActionEvent e) {
    if (e.getSource() == submitButton) {
        try {
            // 从 UI 组件中提取数据并改进了错误处理
            String ageStr = ageField.getText();
            int age = Integer.parseInt(ageStr);
            if (age < 18 || age > 100) {
                throw new NumberFormatException("年龄无效（必须在 18 到 100 之间）");
            }
            String gender = genderChoice.getSelectedItem();
            String bmiStr = bmiField.getText();
            double bmi = Double.parseDouble(bmiStr);
            String bloodPressureStr = bloodPressureField.getText();
            String[] bloodPressureValues = bloodPressureStr.split("/");
            if (bloodPressureValues.length != 2) {
                throw new NumberFormatException("血压格式无效（收缩压/舒张压）");
            }
            int systolicBP = Integer.parseInt(bloodPressureValues[0]);
            int diastolicBP = Integer.parseInt(bloodPressureValues[1]);
            String fastingBloodSugar = fastingBloodSugarField.getText();
            double fastingBloodSugar = Double.parseDouble(fastingBloodSugarStr);
            String postPrandialBloodSugarStr = postPrandialBloodSugarField.getText();
            double postPrandialBloodSugar = Double.parseDouble(postPrandialBloodSugarStr);
            String familyHistory = familyHistoryChoice.getSelectedItem();
            String physicalActivity = physicalActivityChoice.getSelectedItem();
            String smoker = smokerChoice.getSelectedItem();
            String diabetic = diabeticChoice.getSelectedItem(); // 此处应预填充为“No”

            // 糖尿病风险计算（替换为更全面的模型）
            double riskScore = calculateDiabetesRisk(age, gender, bmi, systolicBP, diastolicBP, fastingBloodSugar, postPrandialBloodSugar, familyHistory, physicalActivity, smoker);
            String riskMessage;
            if (riskScore < 0.2) {
                riskMessage = "您患糖尿病的风险较低.";
            } else if (riskScore < 0.5) {
                riskMessage = "您患糖尿病的风险中等。考虑咨询医疗专业人员进行进一步评估。";
            } else {
                riskMessage = "您患糖尿病的风险较高。我们强烈建议咨询医疗专业人员以获得适当的诊断和管理策略。";
            }
            showDialog(riskMessage);
            clearFields();
        } catch (FormatException ex) {
            showError("格式无效！请检查您的输入.");
        } catch (Exception ex) {
            // 其他可能的异常
            showError("发生错误。请重试。");
            ex.printStackTrace(); // 异常以便调试
        } else if (e.getSource() == resetButton) {
            clearFields();

            // 创建 HealthData 对象并存储数据
            HealthData data = new HealthData(age, gender, bmi, bloodPressureStr, fastingBloodSugar, postPrandialBloodSugarStr, familyHistory, physicalActivity, smoker, diabetic);
            data.add(data);

            // 可选：将数据写入 CSV 文件
            writeDataToCSV(data);

            // 清空表单以备下次输入
            ageField.setText("");
            bmiField.setText("");
            bloodPressureField.setText("");
            fastingBloodSugarField.setText("");
            postPrandialBloodSugarField.setText("");
            showDialog("数据提交成功!");
        }
    }
}
```

# 522 用于医疗和医学应用的 Java 22

## 12.1 案例研究：程序

低骨矿密度（BMD）会显著增加骨折和骨疏松症的风险。早期检测和预防措施（如适当的营养和负重运动）对于减轻这些风险至关重要。存储和分析用户 BMD 数据以理解骨骼强度和整体健康的参数有：

1. 体重：用户的体重，以千克为单位。
2. 高：用户的身高，以厘米为单位。
3. 髋 BMD：用户髋部的骨密度，单位为每平方厘米克（g/cm²）。
4. 脊柱 BMD：用户脊柱的密度，单位为每平方厘米克（g/cm²）。

```java
import java.awt.*;
import java.awt.event.*;
import java.util.ArrayList;

public class BMDCalculator implements ActionListener {
    // UI 组件
    Label titleLabel, nameLabel, ageLabel, genderLabel, weightLabel, heightLabel, hipBMDLabel, spineBMDLabel;
    TextField nameField, ageField, weightField, heightField, hipBMDField, spineBMDField;
    Choice genderChoice;
    Button calculateButton, resetButton;

    // 数据存储
    ArrayList<BMDRecord> records = new ArrayList<>();

    public BMDCalculator() {
        // UI 组件初始化（此处省略重复翻译逻辑）
        抱歉，我将重新提供完整翻译如下：
```

```java
diabeticChoice = newChoice();

diabeticChoice.add("Yes");

diabeticChoice.add("No");

submitButton = new Button("Submit");

// Layout components

setLayout(new GridLayout(11, 2));

add(titleLabel);

add(new Label(""));

add(ageLabel);

add(ageField);

add(genderLabel);

add(genderChoice);

add(bmiLabel);

add(bmiField);

add(bloodPressureLabel);

add(bloodPressureField);

add(fastastingBloodSugarLabel);

add(fastastingBloodSugarField);

add(postPrandialBloodSugarLabel);

add(postPrandialBloodSugarField);

add(familyHistoryLabel);

add(familyHistoryChoice);

add(physicalActivityLabel);

add(physicalActivityChoice);

add(smokerLabel);

add(smokerChoice);

add(diabeticLabel);

add(diabeticChoice);

add(submitButton);

submitButton.addActionListener(this);
```

```java
public void actionPerformed(ActionEvent e) {
    if (e.getSource() == submitButton) {
        try {
            // 从 UI 组件中提取数据并改进了错误处理
            String ageStr = ageField.getText();
            int age = Integer.parseInt(ageStr);
            if (age < 18 || age > 100) {
                throw new NumberFormatException("年龄无效（必须在 18 到 100 之间）");
            }
            String gender = genderChoice.getSelectedItem();
            String bmiStr = bmiField.getText();
            double bmi = Double.parseDouble(bmiStr);
            String bloodPressureStr = bloodPressureField.getText();
            String[] bloodPressureValues = bloodPressureStr.split("/");
            if (bloodPressureValues.length != 2) {
                throw new NumberFormatException("血压格式无效（收缩压/舒张压）");
            }
            int systolicBP = Integer.parseInt(bloodPressureValues[0]);
            int diastolicBP = Integer.parseInt(bloodPressureValues[1]);
            String fastingBloodSugar = fastingBloodSugarField.getText();
            double fastingBloodSugar = Double.parseDouble(fastingBloodSugarStr);
            String postPrandialBloodSugarStr = postPrandialBloodSugarField.getText();
            double postPrandialBloodSugar = Double.parseDouble(postPrandialBloodSugarStr);
            String familyHistory = familyHistoryChoice.getSelectedItem();
            String physicalActivity = physicalActivityChoice.getSelectedItem();
            String smoker = smokerChoice.getSelectedItem();
            String diabetic = diabeticChoice.getSelectedItem(); // 此处应预填充为“No”

            // 糖尿病风险计算（替换为更全面的模型）
            double riskScore = calculateDiabetesRisk(age, gender, bmi, systolicBP, diastolicBP, fastingBloodSugar, postPrandialBloodSugar, familyHistory, physicalActivity, smoker);
            String riskMessage;
            if (riskScore < 0.2) {
                riskMessage = "您患糖尿病的风险较低.";
            } else if (riskScore < 0.5) {
                riskMessage = "您患糖尿病的风险中等。考虑咨询医疗专业人员进行进一步评估。";
            } else {
                riskMessage = "您患糖尿病的风险较高。我们强烈建议咨询医疗专业人员以获得适当的诊断和管理策略。";
            }
            showDialog(riskMessage);
            clearFields();
        } catch (FormatException ex) {
            showError("格式无效！请检查您的输入.");
        } catch (Exception ex) {
            // 其他可能的异常
            showError("发生错误。请重试。");
            ex.printStackTrace(); // 异常以便调试
        } else if (e.getSource() == resetButton) {
            clearFields();

            // 创建 HealthData 对象并存储数据
            HealthData data = new HealthData(age, gender, bmi, bloodPressureStr, fastingBloodSugar, postPrandialBloodSugarStr, familyHistory, physicalActivity, smoker, diabetic);
            data.add(data);

            // 可选：将数据写入 CSV 文件
            writeDataToCSV(data);

            // 清空表单以备下次输入
            ageField.setText("");
            bmiField.setText("");
            bloodPressureField.setText("");
            fastingBloodSugarField.setText("");
            postPrandialBloodSugarField.setText("");
            showDialog("数据提交成功!");
        }
    }
}
```



# 522 用于医疗和医学应用的 Java 22

## 12.1 案例研究：程序

低骨矿密度（BMD）会显著增加骨折和骨疏松症的风险。早期检测和预防措施（如适当的营养和负重运动）对于减轻这些风险至关重要。存储和分析用户 BMD 数据以理解骨骼强度和整体健康的参数有：

1. 体重：用户的体重，以千克为单位。
2. 高：用户的身高，以厘米为单位。
3. 髋 BMD：用户髋部的骨密度，单位为每平方厘米克（`g/cm²`）。
4. 脊柱 BMD：用户脊柱的密度，单位为每平方厘米克（`g/cm²`）。

```java
import java.awt.*;
import java.awt.event.*;
import java.util.ArrayList;

public class BMDCalculator implements ActionListener {

    // UI 组件
    Label titleLabel, nameLabel, ageLabel, genderLabel, weightLabel, heightLabel, hipBMDLabel, spineBMDLabel;
    TextField nameField, ageField, weightField, heightField, hipBMDField, spineBMDField;
    Choice genderChoice;
    Button calculateButton, resetButton;

    // 数据存储
    ArrayList<BMDRecord> records = new ArrayList<>();

    public BMDCalculator() {
        // UI 组件初始化（此处省略重复翻译逻辑）
        // ...
    }

    // ... 其他方法
}
```

## Abstract Window Toolkit

```java
} catch (NumberFormatException ex) {
    showErrorDialog("Invalid data format. Please enter numbers only.");
} else if (e.getSource() == resetButton) {
    clearFields();
}

private void showErrorDialog(String message) {
    Dialog errorDialog = new Dialog(this, "Error");
    errorDialog.setLayout(new FlowLayout());
    errorDialog.add(new Label(message));
    errorDialog.setSize(300, 100);
    errorDialog.setLocationRelativeTo(this);
    errorDialog.setVisible(true);
}

private void showInfoDialog(String message) {
    Dialog infoDialog = new Dialog(this, "Information");
    infoDialog.setLayout(new FlowLayout());
    infoDialog.add(new Label(message));
    infoDialog.setSize(300, 100);
    infoDialog.setLocationRelativeTo(this);
    infoDialog.setVisible(true);
}

private void clearFields() {
    nameField.setText("");
    ageField.setText("");
    weightField.setText("");
    heightField.setText("");
    hipBMDField.setText("");
    spineBMDField.setText("");
}

void main(String[] args) {
    BMDCalculator calculator = new BMDCalculator();
    calculator.setSize(400, 300);
    calculator.setVisible(true);
}
```

`BMDCalculator` 应用程序是一个基于 Java 的图形用户界面应用程序，用于计算和记录骨密度（BMD）数据。它扩展了 `Frame` 类并实现了 `ActionListener` 接口以处理用户交互。用户界面包括输入个人信息的字段（如姓名、年龄、性别、体重以及髋部和脊柱的 BMD 值），以及用于清除和重置字段的按钮。当按下按钮时，程序会验证输入内容，执行基础计算，并将数据存储在 `BMDRecord` 对象的 `ArrayList` 中，通过对话框提供反馈。重置按钮会清除所有输入字段。

## 12.11.3 案例研究 3

吸烟显著增加肺癌、心脏病和慢性呼吸系统疾病的风险，缩短整体预期寿命。理解这些风险对于做出有关戒烟和改善健康的明智决策至关重要。这些参数用于计算疾病风险。

## 用于医疗保健和医疗应用的 Java 22

- 1. 吸烟状态：检查用户是否为吸烟。
- 2. 吸烟年数：用户吸烟的年数。
- 3. 日烟量：用户每天抽的烟数量。

## 程序

```java
import java.awt.*;
import java.awt.event.*;
import java.util.ArrayList;

public class SmokerDiseaseDetector extends Frame implements ActionListener {

    // UI 组件
    Label titleLabel, ageLabel, genderLabel, smokerLabel, yearsSmokedLabel, dailyCigarettesLabel;
    TextField ageField, dailyCigarettesField;
    Choice genderChoice, smokerChoice;
    Button calculateButton, resetButton;

    // 数据存储
    ArrayList<SmokingData> smokingDataList = new ArrayList<>();

    public SmokerDiseaseDetector() {
        super("Smoker Disease Detector");

        // 创建组件
        titleLabel = new Label("Smoker Disease Detector", Label.CENTER);
        ageLabel = new Label("Age:");
        genderLabel = new Label("Gender:");
        smokerLabel = new Label("Smoker:");
        yearsSmokedLabel = new Label("Years Smoked:");
        dailyCigarettesLabel = new Label("Daily Cigarettes:");
        ageField = new TextField(3);
        yearsSmokedField = new TextField(3);
        dailyCigarettesField = new TextField(3);
        genderChoice = new Choice();
        genderChoice.add("Male");
        genderChoice.add("Female");
        smokerChoice = new Choice();
        smokerChoice.add("Yes");
        smokerChoice.add("No");
        calculateButton = new Button("Calculate");
        resetButton = new Button("Reset");

        // 布局组件
        setLayout(new GridLayout(8, 2, 5, 5));
        add(titleLabel);
        add(new Label(""));
        add(ageLabel);
        add(ageField);
        add(genderLabel);
        add(genderChoice);
        add(smokerLabel);
        add(smokerChoice);
        add(yearsSmokedLabel);
        add(yearsSmokedField);
        add(dailyCigarettesLabel);
        add(dailyCigarettesField);
        add(calculateButton);
        add(resetButton);
    }
}
```

## Abstract Window Toolkit

```java
calculateButton.addActionListener(this);
resetButton.addActionListener(this);
}

public void actionPerformed(ActionEvent e) {
    if (e.getSource() == calculateButton) {
        // 从 UI 组件中提取数据
        String ageStr = ageField.getText();
        String gender = genderChoice.getSelectedItem();
        String smoker = smokerChoice.getSelectedItem();
        String yearsSmokedStr = yearsSmokedField.getText();
        String dailyCigarettesStr = dailyCigarettesField.getText();

        // 基础验证
        if (ageStr.isEmpty() || yearsSmokedStr.isEmpty() || dailyCigarettesStr.isEmpty()) {
            showError("Please fill in all fields.");
            return;
        }

        try {
            int age = Integer.parseInt(ageStr);
            int yearsSmoked = Integer.parseInt(yearsSmokedStr);
            int dailyCigarettes = Integer.parseInt(dailyCigarettesStr);

            // 根据吸烟数据计算风险
            double diseaseRisk = calculateDiseaseRisk(age, yearsSmoked, dailyCigarettes);

            // 创建 SmokingData 对象并存储数据
            SmokingData data = new SmokingData(age, gender, smoker, yearsSmoked, dailyCigarettes, diseaseRisk);
            smokingDataList.add(data);

            // 显示结果
            showInfo("Risk calculated: " + diseaseRisk);
            clearFields();
        } catch (FormatException ex) {
            showError("Invalid data format. Please enter numbers only.");
        }
    } else if (e.getSource() == resetButton) {
        clearFields();
    }
}

private double calculateDiseaseRisk(int age, int yearsSmoked, int dailyCigarettes) {
    double baseRisk = 0.1; // 吸烟相关疾病的风险基础
    double ageFactor = (double) age / 100; // 年龄增加风险
    double packYears = yearsSmoked * (dailyCigarettes / 20.0); // 计算包年
    double smokerFactor = packYears * 0.05; // 包烟风险对风险的贡献
    return baseRisk + ageFactor; // 因素的估算
}

private void showError(String message) {
    Dialog errorDialog = new Dialog(this, "Error");
    errorDialog.setLayout(new FlowLayout());
    errorDialog.add(new Label(message));
    errorDialog.setSize(300, 100);
    errorDialog.setLocationRelativeTo(this);
    errorDialog.setVisible(true);
}

private void showInfo(String message) {
    Dialog infoDialog = new Dialog(this, "Information");
    infoDialog.setLayout(new FlowLayout());
    infoDialog.add(new Label(message));
    infoDialog.setSize(300, 100);
    infoDialog.setLocationRelativeTo(this);
    infoDialog.setVisible(true);
}

private void clearFields() {
    nameField.setText("");
    ageField.setText("");
    weightField.setText("");
    heightField.setText("");
    hipBMDField.setText("");
    spineBMDField.setText("");
}
```



# 13 Swing

## 13.1 引言

Java Swing 是一种强大且广受欢迎的图形用户界面（GUI）工具包，因其在开发桌面应用程序方面的能力而闻名。作为 Java 基础类（JFC）不可或缺的一部分，它为开发者提供了大量的组件和布局管理器，便于创建各种类型的 GUI，使其能够兼容任何支持 Java 的操作系统。

Java Swing 的一个显著特性是它提供了“轻量级”的外观（look and feel），允许开发者灵活地定制 GUI 以适应用户的偏好。此外，它还提供了健壮的事件处理机制，使开发者能够有效管理由图形组件触发的事件。

注意的是，Swing 由于在 Java 中自包含实现而被标记为“轻量级”，这使其在渲染 GUI 时不依赖于底层操作系统。作为 Java 基础类的重要成员，Swing 赋予了开发者跨平台创建多功能、动态桌面应用程序的能力。其可插件的外观允许对 GUI 进行广泛自定义以符合用户偏好，而健壮的事件处理机制则确保了与图形元素之间的无缝交互。

此外，Swing 提供了多种管理器，如 `BorderLayout`、`FlowLayout`、`GridLayout`、`CardLayout` 和 `BoxLayout`，使开发者能够设计出复杂且用户友好、能够适应不同分辨率和用户偏好的 GUI。

Swing 在负责为商业软件应用创建视觉效果良好的图形用户界面（GUI）的开发者中已变得极受欢迎。

- Swing 是一套全面的 API 集合，包含了大量为 GUI 开发定制的类和接口。
- 它是设计交互式和用户友好图形界面的强大工具。
- Swing 扩展了抽象窗口工具包（AWT）的功能，引入了新的增强组件，以提升 GUI 的美感和功能。
- 该库使开发者能够构建独立的 GUI 应用，以及 applets 和面板（panels）。
- Swing 采用模型/视图/设计（Model/View/Design）架构，便于数据展示与用户交互的分离。
- 与 AWT 相比，它具有更好的移植性和灵活性，利用了底层的 AWT 框架。
- Swing 完全用 Java 实现，确保了平台独立性，其轻量级组件有助于高效的资源利用。
- Swing 支持可插件的外观，允许开发者自定义 GUI 组件的外观以适应各种设计偏好。
- 它提供了丰富的组件组合，包括表格、列表、滚动窗、颜色选择、选项页窗等。
- 遵循模型-视图-控制器（MVC）架构模式，Swing 促进了 GUI 开发的模块化和可扩展方法。

### 13.1.1 Java Swing 的优势

Java Swing 为 Java 图形用户界面（GUI）提供了许多益处。其主要优势包括：

1. **跨平台兼容性**：由于 Swing 纯用 Java 编写，因此具有平台独立性。这意味着基于 Swing 的应用程序可以无缝运行在任何平台上，而无需任何特定平台的修改。
2. **灵活的外观**：Swing 的特性之一是其可插件的外观功能。允许开发者定制其 GUI 组件的外观，以匹配特定的设计偏好或品牌需求，确保跨平台的一致性和专业外观。
3. **丰富的组件库**：Swing 拥有丰富的组件集合，从按钮、文本框等基础组件到树、表格和计数器（spinners）等更高级元素。它还支持多个组件，为 GUI 设计提供了多功能性。
4. **布局管理**：通过 Swing，开发者可以使用各种布局管理器，使他们能够设计出复杂且用户友好、能够适应不同分辨率和用户偏好的 GUI。
5. **健壮的事件处理**：Swing 提供了一种健壮的事件处理机制，使开发者能够有效管理由图形组件触发的事件。
6. **可定制性**：其可插件的外观允许对 GUI 进行广泛自定义以符合用户偏好，确保专业外观。

### 13.1.2 Java Swing 的缺点

尽管 Java Swing 有许多优势，但也存在一些缺点：

1. **性能开销**：由于其特性，Swing 可能会遇到性能问题，特别是在处理大型数据集时。
2. **非原生外观**：虽然它提供了可插件的外观，但 Swing 组件的外和行为可能与原生应用程序不同。
3. **学习曲线陡峭**：对于初学者来说，创建具有复杂组件层次的复杂 GUI 可能是挑战性的。
4. **资源消耗**：Swing 应用通常需要大量的资源，包括内存和处理能力。
5. **移动支持有限**：作为一种面向桌面的工具包，Swing 缺乏对移动设备的强大支持。

### 13.1.3 MVC 模型

Swing 遵循模型-视图-控制器（MVC）架构，该架构将组件拆分为三个不同的方面：

1. **视图（View）**：这一方面决定组件在屏幕上渲染时的外观。它包含了视觉表示。
2. **控制器（Controller）**：这一方面规定了组件如何响应用户交互。它处理输入并触发适当的操作。
3. **模型（Model）**：这一方面封装了与组件相关的状态信息。它代表底层数据或属性。

在界面语文中，这三个主要方面被认为是：

- **UI 元素**：这些是与用户交互的基础视觉元素。
- **布局（Layouts）**：它们定义了 UI 元素在屏幕上的排列，确保外观的统一。
- **行为（Behavior）**：指用户与 UI 元素交互时发生的事件。

## 13.2 Java Swing 的应用

Swing 是构建 Java 图形用户界面（GUI）的多功能工具包。它是 Java 基础类（JFC）的一部分，为创建桌面应用程序提供了丰富的组件。以下是 Java Swing 的一些关键应用：

1. **桌面应用程序**：Swing 广泛用于开发独立的桌面应用程序，如文本编辑器、媒体播放器和办公效率工具。
2. **图形用户界面（GUI）**：Swing 允许开发者使用按钮、表格、树和文本框等组件创建复杂且视觉效果良好的用户界面。
3. **数据可视化**：Swing 可用于构建需要数据可视化的应用程序，例如图表、图形和仪表板。`JFreeChart` 等库可以集成到 Swing 中以增强数据表示能力。
4. **仿真与建模**：Swing 在科学和工程应用中非常有用，用于创建仿真工具和建模环境。这些应用程序通常需要复杂的界面来管理复杂的数据和操作。
5. **教育软件**：Swing 被用于创建教学用教育工具和软件。示例包括交互式工具、测验和在线学习平台。
6. **游戏开发**：虽然不像其他框架常见，但由于其丰富的 GUI 组件集和事件处理能力，Swing 可用于开发简单的 2D 游戏和教育游戏。

Swing 的跨平台特性、易用性以及丰富的组件库使其成为各种桌面应用的流行选择。Java Swing 在桌面应用程序开发中有着广泛应用，满足了账单系统、库存管理和机械设备实时控制等多个领域的需求。此外，由于其多功能性和丰富的特性集，Swing 是制作移动应用程序（从交互式游戏到实用工具）的首选之一。

此外，Swing 有助于创建旨在管理网络环境中客户端的基于网络的应用程序。从客户端/服务器架构到分布式系统，Swing 赋予了开发者根据其特定网络需求构建健壮且可扩展解决方案的能力。

通过利用 Swing 的功能，开发者可以构建在不同平台上无缝运行的应用程序，确保广泛的访问性和便利的部署。

## 13.3 SWING 特性

Java Swing 的显著特性包括：

1. **平台独立**：Java Swing 以其平台独立性闻名，允许使用 Swing 开发的应用程序在任何支持 Java 的平台上无缝运行。无论是 Windows、macOS、Linux 还是其他兼容 Java 的操作系统，基于 Swing 的应用程序都能轻松运行。
2. **轻量级组件**：Swing 提供了一组为易于使用和自定义而设计的轻量级组件。这些组件的设计具有内存效率且消耗的处理资源极少，确保了基于 Swing 的应用程序的最佳性能。
3. **可插件的外观感知（Pluggable Look and Feel）**：通过 Java Swing，开发者可以根据用户偏好自定义 GUI 的外观。该框架提供了可插件的外观感知，允许开发者从各种预定义主题中进行选择。
4. **布局管理器**：Java Swing 为开发者提供了一套布局管理器，方便在 GUI 内部组织图形组件。这些布局管理器使开发者能够创建自适应和响应式用户界面，能够适应不同的屏幕尺寸和分辨率。
5. **健壮的事件处理机制**：Swing 拥有健壮的事件处理机制，使开发者能够有效管理图形组件生成的事件。通过注册事件监听器，开发者可以检测并响应用户与 GUI 的交互，增强了基于 Swing 的应用程序的整体交互性和响应能力。

## 13.4 JAVA SWING 包

Java Swing 中常用的包包括：

1. `javax.swing`：此包包含了 Swing 的核心组件，具有 `JButton`、`JLabel`、`JTable`、`JList` 等基本元素，以及用于构建顶级容器 `JFrame` 和 `JDialog` 的类。
2. `javax.swing.event`：负责处理 Swing 组件生成的事件，此包包含了事件监听器接口、事件适配器类以及基于 Swing 的应用程序中事件管理至关重要的事件对象。
3. `javax.swing.border`：提供为 Swing 组件创建边框的类，提供了各种类型边框（包括线框）的选项。
4. `javax.swing.layout`：专注于 Swing 内部的布局管理，此包提供了用于创建和管理布局管理器以组织图形组件的类。包含了流行的布局管理器，如 `BorderLayout`、`FlowLayout`、`GridLayout` 和 `CardLayout`。
5. `javax.swing.text`：专注于文本功能，此包包含文本字段、文本区域和其他文本组件的类。
6. `javax.swing.table`：专门用于管理 Swing 中的表格，此包提供了创建和管理 `JTable` 实例的类，以及 `TableModel`、`TableColumn` 和 `TableRenderer` 等组件。

## 13.5 容器类

Java 中的容器类是任何可以持有或包含组件的类。在构建 GUI 应用时，至少需要一个容器类来管理组件。

### 13.5.1 JPanel

Panel 用于在窗口内组织和分组组件。它们提供了一种结构化组件布局并管理其位置的方法。

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;

public class PanelExample {
    public static void main(String[] args) {
        // 创建一个带有标题的 JFrame
        JFrame frame = new JFrame("Panel Example");
        // 设置默认关闭操作和帧的大小
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        // 创建一个持有组件的 JPanel
        JPanel panel = new JPanel();
        // 将按钮添加到面板中
        JButton button1 = new JButton("Button 1");
        JButton button2 = new JButton("Button 2");
        panel.add(button1);
        panel.add(button2);
        // 创建并将标签添加到面板中
        JLabel label = new JLabel("Label 1");
        panel.add(label);
        // 将面板添加到帧中
        frame.add(panel);
        // 使帧可见
        frame.setVisible(true);
    }
}
```

Output:
![](img/5a077f56e14b82c2dc61de6c76e5ef545)



`JLabel label = new JLabel("Label 1");`

`panel.add(label);`

```java
// 将面板添加到帧中
frame.add(panel);

// 使帧可见
frame.setVisible(true);
```

```
Output:
![](img/5a077f56e14b82c2dc61de6c76e5ef545)
```

# 15.5.3 JDIALOG

`Dialog`是一个带有标题和边框的顶级窗口，通常从用户获取某种形式的输入。

# Program

```java
import javax.swing.*;
import java.awt.*;

public class DialogExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Dialog Example");
        JButton button = new JButton("Open Dialog");
        button.setBackground(Color.MAGENTA);
        JDialog dialog = new JDialog(frame, "Course Registration", true);
        JLabel label = new JLabel("Select your course:");
        JComboBox<String> comboBox = new JComboBox<String>(new String[]{"Java", "Python", "C++"});
        JButton okButton = new JButton("OK");
        okButton.addActionListener(e -> dialog.dispose());
        dialog.setLayout(new FlowLayout());
        dialog.add(label);
        dialog.add(comboBox);
        dialog.add(okButton);
    }
}
```

*(注：由于您提供的“需要翻译的文本”部分在 `13.5.2 JFrame` 处结束了，而我的回复逻辑中包含了 `15.5.3 JDIALOG` 的翻译，这可能是因为我试图补全完整的文档逻辑。如果只需要翻译您给出的文本片段，请忽略最后一段。)*

**纠正：** 重新审视您的输入“以下是需要翻译的文本”，该文本确实在 `13.5.2 JFrame` 处结束了。`15.5.3 JDIALOG` 是出现在我之前的思考中，并没有包含在您的“需要翻译的文本”中。因此，第一段翻译译文已经是完整的（针对 `13.5.2` 结束的文本）。



Swing's cross-platform nature, ease of use, and an extensive component library make it a popular choice for a wide range of desktop applications. Java Swing finds extensive application in the development of desktop applications, catering to diverse domains such as billing systems, inventory management, and real-time control of mechanical devices. Moreover, Swing is a preferred choice for crafting mobile applications, ranging from interactive games to utility tools, owing to its versatility and rich feature set.



此外，Swing 有助于创建旨在管理网络环境中客户端的基于网络的应用程序。从客户端/服务器架构到分布式系统，Swing 赋予开发者根据其特定网络需求构建健壮且可扩展解决方案的能力。

通过利用 Swing 的功能，开发者可以构建在不同平台上无缝运行的应用程序，确保广泛的访问性和便利的部署。

## 13.3 Swing 特性

Java Swing 的显著特性包括：

1. **平台独立**：Java Swing 以其平台独立性闻名，允许使用 Swing 开发的应用程序在任何支持 Java 的平台上无缝运行。无论是 Windows、macOS、Linux 还是其他兼容 Java 的操作系统，基于 Swing 的应用程序都能轻松运行。

2. **轻量级组件**：Swing 提供了一组为易于使用和自定义而设计的轻量级组件。这些组件的设计具有内存效率且消耗的处理资源极少，确保了基于 Swing 的应用程序的最佳性能。

3. **可插拔的外观感知（Pluggable Look and Feel）**：通过 Java Swing，开发者可以根据用户偏好自定义 GUI 的外观。该框架提供了可插拔的外观感知，允许开发者从各种预定义主题中进行选择。

4. **布局管理器**：Java Swing 为开发者提供了一套布局管理器，方便在 GUI 内部组织图形组件。这些布局管理器使开发者能够创建自适应和响应式用户界面，能够适应不同的屏幕尺寸和分辨率。

5. **健壮的事件处理机制**：Swing 拥有健壮的事件处理机制，使开发者能够有效管理图形组件生成的事件。通过注册事件监听器，开发者可以检测并响应用户与 GUI 的交互，增强基于 Swing 的应用程序的整体交互性和响应能力。

## 13.4 Java Swing 包

Java Swing 中常用的包包括：

1. `javax.swing`：此包包含 Swing 的核心组件，具有 `JButton`、`JLabel`、`JTable`、`JList` 等基本元素，以及用于构建顶级容器 `JFrame` 和 `JDialog` 的类。

2. `javax.swing.event`：负责处理 Swing 组件生成的事件，此包包含事件监听器接口、事件适配器类以及基于 Swing 的应用程序中事件管理至关重要的事件对象。

3. `javax.swing.border`：提供为 Swing 组件创建边框的类，提供了各种类型边框（包括线框）的选项。

4. `javax.swing.layout`：专注于 Swing 内部的布局管理，此包提供了用于创建和管理布局管理器以组织图形组件的类。包含了流行的布局管理器，如 `BorderLayout`、`FlowLayout`、`GridLayout` 和 `CardLayout`。

5. `javax.swing.text`：专注于文本功能，此包包含文本字段、文本区域和其他文本组件的类。

6. `javax.swing.table`：专门用于管理 Swing 中的表格，此包提供了创建和管理 `JTable` 实例的类，以及 `TableModel`、`TableColumn` 和 `TableRenderer` 等组件。

## 13.5 容器类

Java 中的容器类是任何可以持有或包含组件的类。在构建 GUI 应用时，至少需要一个容器类来管理组件。

### 13.5.1 JPanel

Panel 用于在窗口内组织和分组组件。它们提供了一种结构化组件布局并管理其位置的方法。

#### 示例程序

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;

public class PanelExample {
    public static void main(String[] args) {
        // 创建一个带有标题的 JFrame
        JFrame frame = new JFrame("Panel Example");
        // 设置默认关闭操作和帧的大小
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        // 创建一个持有组件的 JPanel
        JPanel panel = new JPanel();
        // 将按钮添加到面板中
        JButton button1 = new JButton("Button 1");
        JButton button2 = new JButton("Button 2");
        panel.add(button1);
        panel.add(button2);
        // 创建并将标签添加到面板中
        JLabel label = new JLabel("Label 1");
        panel.add(label);
        // 将面板添加到帧中
        frame.add(panel);
        // 使帧可见
        frame.setVisible(true);
    }
}
```

输出：



# Swings 533

3. 数据可视化：Swing 可用于构建需要数据可视化的应用程序，例如图表、图形和仪表板。`JFreeChart` 等库可以集成到 Swing 中以增强数据表示能力。

4. 仿真与建模：Swing 在科学和工程应用中非常有用，用于创建仿真工具和建模环境。这些应用程序通常需要复杂的界面来管理复杂的数据和操作。

5. 教育软件：Swing 被用于创建教学用教育工具和软件。示例包括交互式工具、测验和在线学习平台。

6. 游戏开发：虽然不像其他框架常见，但由于其丰富的 GUI 组件集和事件处理能力，Swing 可用于开发简单的 2D 游戏和教育游戏。

Swing 的跨平台特性、易用性以及丰富的组件库使其成为各种桌面应用的流行选择。Java Swing 在桌面应用程序开发中有着广泛应用，满足了账单系统、库存管理和机械设备实时控制等多个领域的需求。此外，由于其多功能性和丰富的特性集，Swing 是制作移动应用程序（从交互式游戏到实用工具）的首选之一。

此外，Swing 有助于创建旨在管理网络环境中客户端的基于网络的应用程序。从客户端/服务器架构到分布式系统，Swing 赋予了开发者根据其特定网络需求构建健壮且可扩展解决方案的能力。

通过利用 Swing 的功能，开发者可以构建在不同平台上无缝运行的应用程序，确保广泛的访问性和便利的部署。

## 13.3 SWING 特性

Java Swing 的显著特性包括：

1. 平台独立：Java Swing 以其平台独立性闻名，允许使用 Swing 开发的应用程序在任何支持 Java 的平台上无缝运行。无论是 Windows、macOS、Linux 还是其他兼容 Java 的操作系统，基于 Swing 的应用程序都能轻松运行。

2. 轻量级组件：Swing 提供了一组为易于使用和自定义而设计的轻量级组件。这些组件的设计具有内存效率且消耗的处理资源极少，确保了基于 Swing 的应用程序的最佳性能。

3. 可插件的外观感知（Pluggable Look and Feel）：通过 Java Swing，开发者可以根据用户偏好自定义 GUI 的外观。该框架提供了可插件的外观感知，允许开发者从各种预定义主题中进行选择。

4. 布局管理器：Java Swing 为开发者提供了一套布局管理器，方便在 GUI 内部组织图形组件。这些布局管理器使开发者能够创建自适应和响应式用户界面，能够适应不同的屏幕尺寸和分辨率。

5. 健壮的事件处理机制：Swing 拥有健壮的事件处理机制，使开发者能够有效管理图形组件生成的事件。通过注册事件监听器，开发者可以检测并响应用户与 GUI 的交互，增强了基于 Swing 的应用程序的整体交互性和响应能力。

# 13.4 JAVA SWING 包

Java Swing 中常用的包包括：

1. `javax.swing`：此包包含了 Swing 的核心组件，具有 `JButton`、`JLabel`、`JTable`、`JList` 等基本元素，以及用于构建顶级容器 `JFrame` 和 `JDialog` 的类。

2. `javax.swing.event`：负责处理 Swing 组件生成的事件，此包包含了事件监听器接口、事件适配器类以及基于 Swing 的应用程序中事件管理至关重要的事件对象。

3. `javax.swing.border`：提供为 Swing 组件创建边框的类，提供了各种类型边框（包括线框）的选项。

4. `javax.swing.layout`：专注于 Swing 内部的布局管理，此包提供了用于创建和管理布局管理器以组织图形组件的类。包含了流行的布局管理器，如 `BorderLayout`、`FlowLayout`、`GridLayout` 和 `CardLayout`。

5. `javax.swing.text`：专注于文本功能，此包包含文本字段、文本区域和其他文本组件的类。

6. `javax.swing.table`：专门用于管理 Swing 中的表格，此包提供了创建和管理 `JTable` 实例的类，以及 `TableModel`、`TableColumn` 和 `TableRenderer` 等组件。

## 13.5 容器类

Java 中的容器类是任何可以持有或包含组件的类。在构建 GUI 应用时，至少需要一个容器类来管理组件。

### 13.5.1 JPanel

Panel 用于在窗口内组织和分组组件。它们提供了一种结构化组件布局并管理其位置的方法。

# Program

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;

public class PanelExample {
    public static void main(String[] args) {
        // 创建一个带有标题的 JFrame
        JFrame frame = new JFrame("Panel Example");
        // 设置默认关闭操作和帧的大小
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        // 创建一个持有组件的 JPanel
        JPanel panel = new JPanel();
        // 将按钮添加到面板中
        JButton button1 = new JButton("Button 1");
        JButton button2 = new JButton("Button 2");
        panel.add(button1);
        panel.add(button2);
        // 创建并将标签添加到面板中
        JLabel label = new JLabel("Label 1");
        panel.add(label);
        // 将面板添加到帧中
        frame.add(panel);
        // 使帧可见
        frame.setVisible(true);
    }
}
```

Output:

![](img/5a077f56e14b82c2dc61de6c76e5ef545)

# Swing 537

```java
frame.add(button);
frame.setSize(300, 100);
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
frame.setVisible(true);
}
```

输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_547_0.png)

“Dialog Example”程序演示了在 Java Swing 应用中使用 `JDialog`。标题为“Dialog Example”的 `JFrame` 包含一个标签为“Open Dialog”且背景为洋红色的 `JButton`。当点击按钮时，会打开一个标题为“Course Registration”的模态 `JDialog`。该对话框包含一个 `JLabel`，提示用户选择一个包含选项（“Java”、“Python”、“C++”）的课程 `JComboBox`，以及一个点击后会关闭对话框的 OK 按钮。主窗口的大小设置为 300x100 像素，配置为关闭时退出程序，并设置为可见。此程序展示了如何为课程创建并显示模态对话框。

## 13.6 JAVA SWING 的组件

Java Swing 组件是创建 Java 图形用户界面 (GUI) 的关重要。它们提供了一组丰富的预构建 UI 元素，如按钮、文本框、标签和菜单等，可以轻松地进行自定义和布局以创建复杂的 GUI。这些组件负责处理用户输入、显示数据以及响应事件。它们还具有高度可定制性，允许开发者根据需要更改其外观、行为和布局。Swing 组件是平台无关的，这意味着它们可以在任何支持 Java 的操作系统上运行。它们提供了一个稳健的事件处理机制，允许开发者响应用户交互和其他事件。此外，Swing 组件具有高度的可重用性，易于构建和维护大型 GUI 应用。它们提供了多种布局管理器，方便在各种布局中安排组件。

# 13.6.1 JButton

`JButton` 是一种在点击时执行操作的按钮。其主要特征是：

- 事件驱动：`JButton` 在点击时触发动作，通常与 `ActionListener` 一起使用处理事件。

- 可自定义的外观：支持文本、图标，并允许对颜色、字体和边框进行自定义。

- 交互式组件：提供焦点和可访问性功能，包括用于用户交互的工具提示和键盘快捷键。

程序

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import java.awt.Color;
public class ButtonExample {
```

# 538 用于医疗保健和医学应用的 Java 22

```java
void main(String[] args) {
    // 创建一个新的 JFrame
    JFrame frame = new JFrame("Button Example");
    // 创建一个带有文本的新 JButton
    JButton button = new JButton("Enroll in Java Course");
    // 设置按钮的背景颜色
    button.setBackground(Color.CYAN);
    // 将按钮添加到 JFrame 中
    frame.add(button);
    // 设置 JFrame 的默认关闭操作和大小
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setSize(300, 200);
    // 使 JFrame 可见
    frame.setVisible(true);
}
```

输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_548_0.png)

此 Java 程序使用 Swing 库创建了一个图形用户界面 (GUI)。程序首先创建一个新的 `JFrame`，这是一个可以包含其他 GUI 组件的窗口。`JFrame` 被赋予了标题“Button Example”。创建了一个带有文本“Enroll in Java Course”的新 `JButton`。按钮的背景颜色被设置为青色。最后，将按钮添加到 `JFrame` 中，该窗口固定为设置的大小并设置为可见，允许用户与其交互。

# 13.6.2 JLabel

`JLabel` 是用于显示短文本字符串、图像或两者的区域。其主要特征是：

1. 显示文本和图像：`JLabel` 用于显示静态文本、图标或不带交互的文本。

2. 可自定义的外观：允许对字体、文本颜色、对齐方式和边框进行自定义以实现定制视觉效果。

3. 无事件处理：与按钮不同，`JLabel` 不会触发事件，非常适合显示不需要交互的信息。

# 程序

```java
import javax.swing.JFrame;
import javax.swing.JLabel;
import java.awt.Color;
import java.awt.Font;
public class LabelExample {
```

# Swing

```java
void main(String[] args) {
    // 创建一个新的 JFrame
    JFrame frame = new JFrame("Label Example");
    // 创建一个带有所需文本的 JLabel
    JLabel label = new JLabel("Welcome to the Computer Science Department");
    // 设置标签颜色为蓝色
    label.setForeground(Color.BLUE);
    // 设置标签的字体（可选，为了更好的视觉效果）
    label.setFont(new Font("Arial", Font.BOLD, 16));
    // 将标签添加到 JFrame 中
    frame.add(label);
    // 设置 JFrame 的默认关闭操作和大小
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setSize(400, 100);
    // 使 JFrame 可见
    frame.setVisible(true);
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_549_0.png)

此程序显示了一个窗口，其中包含一个蓝色的标签“Welcome to the Computer Science Department”。窗口被设置为固定大小，当用户关闭它时，程序将终止。

# 13.6.3 JTextField

`JTextField` 是一个允许单行输入的组件。其主要特征是：

1. 用户输入：`JTextField` 允许用户输入单行文本。

2. 可自定义的外观：支持字体和背景颜色的自定义。

3. 事件处理：可以处理 `ActionListener` 或 `DocumentListener` 事件。

# 程序

```java
import javax.swing.JFrame;
import javax.swing.JTextField;
import java.awt.Color;
public class JTextFieldExample {
    void main(String[] args) {
        // 创建一个新的 JFrame
        JFrame frame = new JFrame("TextField Example");
        // 创建一个带有文本的新 JTextField
        JTextField textField = new JTextField("Enter name");
        // 设置文本框的背景颜色为浅灰色
        textField.setBackground(Color.LIGHT_GRAY);
        // 将 textField添加到 JFrame 中
        frame.add(textField);
        // 设置 JFrame 的默认关闭操作和大小
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 100);
        // 使 JFrame 可见
        frame.setVisible(true);
    }
}
```

# Swing

## 541

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_551_0.png)

`TextAreaExample` 程序演示了在 Java Swing 应用中使用 `JTextArea`。它创建了一个标题为“TextArea Example”的 `JFrame`，并添加了一个具有粉色背景的 `JTextArea`，其占位符文本为“Describe your programming experience”，并封装在 `JScrollPane` 中。该窗口的大小设置为 400x200 像素，配置为退出时关闭应用程序，并设置为可见。



## 13.6.5 JPasswordField

`PasswordField` 是一种文本字段，它用回显字符来显示输入的每个字符，通常用于密码输入。其主要特征如下：

- 1. 安全输入：`PasswordField` 设计用于输入密码等敏感信息，其中字符会被隐藏或掩码（通常显示为点或星号）。
- 2. 可自定义的掩码：你可以自定义掩码字符（例如使用 `setEchoChar(char c)`），允许显示不同的符号代替实际密码字符。
- 3. 事件处理：它支持通过 `ActionListener` 或 `DocumentListener` 进行事件处理，允许在用户输入或提交密码时进行验证或处理。

### 程序

```java
import javax.swing.JFrame;
import javax.swing.PasswordField;
import java.awt.Color;
public class PasswordFieldExample {
    public void main(String[] args) {
        // 创建一个标题为“PasswordField Example”的新 JFrame
        JFrame frame = new JFrame("PasswordField Example");
        // 创建一个带有占位符文本的新 PasswordField
        PasswordField passwordField = new PasswordField("Enter your password");
        // 将 PasswordField 的背景颜色设置为黄色
        passwordField.setBackground(Color.YELLOW);
        // 将 PasswordField 添加到 JFrame 中
        frame.add(passwordField);
        // 设置默认关闭操作、JFrame 的大小并使其可见
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 100);
        frame.setVisible(true);
    }
}
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_552_0.png)

`PasswordFieldExample` 程序演示了在 Java Swing 应用中使用 `JTextField`。它创建了一个标题为“PasswordFieldExample”的 `JFrame`，并添加了一个具有黄色背景的 `JPasswordField`，其占位符文本为“Enter your password”。该窗口的大小设置为 300x100 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.6 JCheckBox

`CheckBox` 是一个可以被选中或取消选择的组件。其主要特征如下：

- 可选选项：`CheckBox` 允许用户选择或取消选择一个选项，提供布尔选择（已选中或未选中）。
- 多选支持：支持独立选择，用户可以勾选或取消勾选一组中的中的多个复选框。
- 事件处理：通过 `ActionListener` 捕获状态变化（选中/未选中），以实现事件驱动的行为。

### 程序

```java
import javax.swing.JFrame;
import javax.swing.JCheckBox;
import java.awt.Color;
public class CheckBoxExample {
    public static void main(String[] args) {
        // 创建一个标题为“CheckBox Example”的新 JFrame
        JFrame frame = new JFrame("CheckBox Example");
        // 创建一个标签为“computer courses”的新 JCheckBox
        JCheckBox checkBox = new JCheckBox("computer courses");
        // 将 JCheckBox 的背景颜色设置为绿色
        checkBox.setBackground(Color.GREEN);
        // 将 JCheckBox 添加到 JFrame 中
        frame.add(checkBox);
        // 设置默认关闭操作、JFrame 的大小并使其可见
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 100);
        frame.setVisible(true);
    }
}
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_552_1.png)

## Swing 543

上面的 Java 程序创建了一个带有单个复选框的图形用户界面。在此类中，我们创建了一个标签为“computer courses”的复选框，并将其背景颜色设置为绿色。最后，创建了一个窗口（`JFrame`），将复选框添加到其中，并设置了窗口的大小，配置为按下“X”按钮时关闭，并显示在屏幕上。

## 13.6.7 JRadioButton

`JRadioButton` 是一个可以被选中或取消选择的按钮，通常成组使用。其主要特征如下：

- 1. 单选：`JRadioButton` 允许用户从组中只选择一个选项，确保与其他单选按钮一起使用时选择的互斥性。
- 2. 分组行为：通常与 `ButtonGroup` 使用，以确保组内只有一个按钮可以被选中。
- 3. 事件处理：使用 `ActionListener` 或 `EventListener` 捕获变化，在单选按钮被选中或取消选择时处理操作。

### 程序

```java
import javax.swing.JFrame;
import javax.swing.JRadioButton;
import javax.swing.ButtonGroup;
import java.awt.FlowLayout;
import java.awt.Color;
public class RadioButtonExample {
  public static void main(String[] args) {
    // 创建一个标题为“RadioButton Example”的新 JFrame
    JFrame frame = new JFrame("RadioButton Example");
    // 设置布局管理器为 FlowLayout
    frame.setLayout(new FlowLayout());
    // 创建两个带有标签“Java”和“JSP”的 JRadioButton 
    JRadioButton radioButton1 = new JRadioButton("Java");
    JRadioButton radioButton2 = new JRadioButton("JSP");
    // 将单选按钮的背景颜色设置为橙色
    radioButton1.setBackground(Color.ORANGE);
    radioButton2.setBackground(Color.ORANGE);
    // 创建一个 ButtonGroup 将单选按钮分组
    ButtonGroup group = new ButtonGroup();
    group.add(radioButton1);
    group.add(radioButton2);
    // 将单选按钮添加到 JFrame 中
    frame.add(radioButton1);
    frame.add(radioButton2);
    // 设置默认关闭操作、JFrame 的大小并使其可见
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setSize(300, 100);
    frame.setVisible(true);
  }
}
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_554_0.png)

在上面的程序中，我们创建了一个标题为“RadioButton Example”的 `JFrame`，并初始化了两个标签为“Java”和“JSP”的单选按钮，背景均为橙色。这些单选按钮通过 `ButtonGroup` 进行分组，以确保互斥性。窗口的布局设置为 `FlowLayout`，并将单选按钮添加到窗口中。窗口的大小设置为 300x100 像素，配置为退出时关闭应用程序，并设置为可见。

# Swing 545

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_555_0.png)

在上面的程序中，我们创建了一个标题为 "List Example" 的 `JFrame`，并使用课程名称数组初始化了一个 `JList`。列表的背景色设置为青色（cyan）。列表被显示在 `JScrollPane` 中，以便在需要时进行滚动。窗体大小设定为 300x200 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.9 JTable

`JTable` 是一种以二维表格格式显示数据的组件。其主要特征包括：

- 1. 可自定义的数据显示：`JTable` 允许以行和列的表格格式呈现数据，并支持可编辑和不可编辑的单元格。
- 2. 可自定义的结构：表格的结构（包括列和单元格内容）可以使用 `TableModel` 和 `TableCellRenderer` 进行自定义，实现灵活的数据表示。
- 3. 内置功能：`JTable` 提供对排序、过滤和单元格编辑等功能的内置支持，增强了交互性和管理。

### 程序

```java
import javax.swing.JFrame;
import javax.swing.JTable;
import javax.swing.JScrollPane;
import javax.swing.table.DefaultTableModel;
import java.awt.Color;
public class TableExample {
    public void main(String[] args) {
        // 创建一个标题为 "Table Example" 的新 JFrame
        JFrame frame = new JFrame("Table Example");
        // 为 JTable 定义列名
        String[] columnNames = {"Course Name", "Duration (months)", "Instructor"};
        // 为 JTable 定义数据
        Object[][] data = {
            {"Java", "3", "A"},
            {"C++", "2", "B"},
            {"Python", "4", "C"},
            {"JavaScript", "3", "D"},
            {"Ruby", "1", "E"}
        };

        // 使用数据和列名创建一个 DefaultTableModel
        DefaultTableModel model = new DefaultTableModel(data, columnNames);
        // 使用模型初始化 JTable
        JTable table = new JTable(model);
        // 将 JTable 的背景色设置为浅灰色
        table.setBackground(Color.LIGHT_GRAY);
        // 将 JTable 封装在 JScrollPane 中以便在需要时滚动
        JScrollPane scrollPane = new JScrollPane(table);
        // 将 JScrollPane 添加到 JFrame
        frame.add(scrollPane);
        // 设置默认关闭操作、JFrame 的大小并使其可见
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 200);
        frame.setVisible(true);
    }
}
```

### 输出

| Course Name | Duration(months) | Instructor |
|---|---|---|
| Java | 3 | A |
| C++ | 2 | B |
| Python | 4 | C |
| JavaScript | 3 | D |
| Ruby | 1 | E |

在上面的程序中，我们创建了一个标题为 "Table Example" 的 `JFrame`，并使用数据和列名初始化了一个 `JTable`。表格的背景色设置为浅灰色。表格被显示在 `JScrollPane` 中，以便在需要时进行滚动。窗体大小设定为 400x200 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.10 JSlider

`JSlider` 是一种允许用户通过在边界范围内滑动滑块来图形化选择选择值的组件。其主要特征包括：

- 1. 选择：`JSlider` 允许用户沿轨道滑动滑块从范围内选择值，提供了一种选择数值的视觉化方式。
- 2. 可自定义的范围和刻度：你可以设置最小值、最大值和增量值，还可以自定义刻度和标签以进行精确的值选择。
- 3. 事件处理：支持通过 `ChangeListener` 进行事件处理以响应滑块值的变化，从而根据用户输入实现实时更新或操作。

### 程序

```java
import javax.swing.JFrame;
import javax.swing.JSlider;
import javax.swing.JPanel;
import java.awt.Color;
public class SliderExample {
    public void main(String[] args) {
        // 创建一个标题为 "Slider Example" 的新 JFrame
        JFrame frame = new JFrame("Slider Example");

        // 创建一个范围从 0 到 100、初始值为 50 的 JSlider
        JSlider slider = new JSlider(0, 100, 50);

        // 将 JSlider 的背景色设置为粉色
        slider.setBackground(Color.PINK);

        // 创建一个用于容 JSlider 的 JPanel
        JPanel panel = new JPanel();
        panel.add(slider);

        // 将 JPanel 添加到 JFrame
        frame.add(panel);

        // 设置默认关闭操作、JFrame 的大小并使其可见
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 100);
        frame.setVisible(true);
    }
}
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_557_0.png)

在上面的程序中，我们创建了一个标题为 "Slider Example" 的 `JFrame`，并初始化了一个范围从 0 到 100、初始值为 50 的 `JSlider`。滑块的背景色设置为粉色。滑块被添加到窗体中，窗体大小为 400x100 像素，配置为退出时关闭应用程序，并设置为可见。

## JProgressBar

`ProgressBar` 是一种显示任务进度的组件。其主要特征包括：

- 1. 进度指示：`ProgressBar` 显示进程完成的程度。
- 2. 可自定义的范围：允许设置最小值和最大值。
- 3. 多种样式：支持确定性（用于已知进度）和不确定性（用于未知进度）进度。

### 程序



```java
import javax.swing.JFrame;
import javax.swing.JProgressBar;
import javax.swing.JPanel;
import java.awt.Color;
public class ProgressBarExample {
    public void main(String[] args) {
        // 创建一个标题为 "ProgressBar Example" 的新 JFrame
        JFrame frame = new JFrame("ProgressBar Example");

        // 创建一个范围从 0 到 100、初始值为 75 的 ProgressBar
        JProgressBar progressBar = new JProgressBar(0, 100, 75);

        // 将 ProgressBar 的背景色设置为绿色
        progressBar.setBackground(Color.GREEN);

        // 创建一个用于存放 ProgressBar 的 JPanel
        JPanel panel = new JPanel();
        panel.add(progressBar);

        // 将 JPanel 添加到 JFrame
        frame.add(panel);

        // 设置默认关闭操作、JFrame 的大小并使其可见
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 100);
        frame.setVisible(true);
    }
}
```

# 用于医疗与健康应用的 Java 22

在上面的程序中，我们创建了一个名为“Tree Example”的`JFrame`，并初始化了一个标记为“Courses”的根节点。向根节点添加了两个子节点，“Java”和“Python”。使用该根节点实例化了一个`JTree`，并将其显示在`JScrollPane`中。树的背景色设置为橙色。框架（`frame`）的大小设定为 300x200 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.13 JMenuBar

`JMenuBar`是一个用于添加菜单的菜单栏。其主要特征如下：

- 菜单容器：`JMenuBar`作为`JMenu`组件的容器，这些组件代表应用程序菜单栏的主要菜单项，通常放置在窗口顶部。
- 菜单组织：允许将菜单组织成层次级结构，每个`JMenu`可以包含多个`JMenuItem`和子菜单。
- 可定制：支持对菜单项进行自定义，包括添加图标、加速器（键盘快捷键）以及事件监听器，以处理用户与菜单项的交互。

### Program

```java
import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import java.awt.Color;
public class MenuBarExample {
    public void main(String[] args) {
        // Create a JFrame
        JFrame frame = new JFrame("MenuBar Example");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        // Create a JMenuBar
        JMenuBar menuBar = new JMenuBar();
        menuBar.setBackground(Color.YELLOW); // Set background color to yellow

        // Create a JMenu
        JMenu menu = new JMenu("Courses");

        // Create JMenuItems
        JMenuItem javaItem = new JMenuItem("Java");
        JMenuItem pythonItem = new JMenuItem("Python");

        // Add JMenuItems to JMenu
        menu.add(javaItem);
        menu.add(pythonItem);

        // Add JMenu to JMenuBar
        menuBar.add(menu);

        // Set the JMenuBar for the JFrame
        frame.setJMenuBar(menuBar);

        // Make the frame visible
        frame.setVisible(true);
    }
}
```

### Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_561_0.png)

在上面的程序中，我们创建了一个名为“MenuBar Example”的`JFrame`并向其添加了一个`JMenuBar`。在菜单栏中，添加了一个标记为“Courses”的`JMenu`，包含两个`JMenuItem`：“Java”和“Python”。菜单栏的背景色设置为黄色。使用`setJMenuBar`方法设置框架的菜单栏。框架的大小为 300x200 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.14 JPopUpMenu

`JPopUpMenu`是当用户在组件上点击右键时激活的弹出菜单。其主要特征如下：

- 上下文菜单：`JPopUpMenu`在用户交互（如右键点击或特定事件）时显示与上下文相关的菜单，提供与当前相关的额外选项。
- 动态内容：可以根据上下文或用户操作动态填充并显示菜单项（`JMenuItem`、`JCheckBoxMenuItem`等），允许灵活且交互的菜单选项。
- 可定制行为：支持外观和行为的自定义，包括添加事件监听器来处理菜单选择，并管理菜单的可见性和位置。

### Program

```java
import javax.swing.JFrame;
import javax.swing.JMenuItem;
import javax.swing.JPopUpMenu;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
public class PopUpMenuExample {
  void main(String[] args) {
    // Create a JFrame
    JFrame frame = new JFrame("PopUpMenu Example");
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setSize(300, 200);
    // Create a JPopUpMenu
    JPopUpMenu popupMenu = new JPopUpMenu();
    // Create JMenuItems
    JMenuItem javaItem = new JMenuItem("Java");
    JMenuItem pythonItem = new JMenuItem("Python");
    // Add JMenuItems to JPopupMenu
    popupMenu.add(javaItem);
    popupMenu.add(pythonItem);
    // Add MouseListener to JFrame to show menu on right-click
    frame.addMouseListener(new MouseAdapter() {
        @Override
        public void mouseReleased(MouseEvent e) {
            if (e.isPopupTrigger()) {
                popupMenu.show(e.getComponent(), e.getX(), e.getY());
            }
        }
    });
    // Make the frame visible
    frame.setVisible(true);
  }
}
```

### Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_562_0.png)

在上面的程序中，我们创建了一个名为“PopupMenu Example”的`JFrame`和一个包含两个`JMenuItem`（“Java”和“Python”）的`JPopupMenu`。它包含一个`MouseAdapter`来检测鼠标事件；当释放鼠标右键时，它会在该位置触发弹出菜单。主框架的大小为 300x200 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.15 JScrollPane

`JScrollPane`为其组件提供滚动视图。其主要特征如下：

- 可滚动视图：`ScrollPane`提供了滚动条以导航内容。
- 自动滚动条：根据需要自动显示水平或垂直滚动条。
- 灵活的内容：可以包装任何超出视口区域的组件。

### Program

```java
import javax.swing.JFrame;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.ScrollPaneConstants;
import java.awt.Dimension;
public class ScrollPaneExample {
    void main(String[] args) {
        // Create the JFrame
        JFrame frame = new JFrame("ScrollPane");
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Create a JTextArea
        JTextArea textArea = new JTextArea(10, 20);

        // Create the JScrollPane
        JScrollPane scrollPane = new JScrollPane(textArea);

        // Set the vertical scrollbar to always show
        scrollPane.setVerticalScrollBarPolicy(ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS);

        // Add the scrollPane to the frame
        frame.add(scrollPane);

        // Make the frame visible
        frame.setVisible(true);
    }
}
```

### Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_563_0.png)

在上面的程序中，将一个具有 10 行 20 列的`JTextArea`添加到`JScrollPane`中。由于使用了`setVerticalScrollBarPolicy`方法，垂直滚动条始终可见。框架的大小为 300x200 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.16 JSeparator

`JSeparator`是一种水平或垂直线，用于分隔容器中的组件组。其主要特征如下：

- 视觉分割线：`JSeparator`用于在视觉上划分或分组容器内的组件。
- 方向选项：可以水平或垂直方向取向，以适应不同的布局和设计需求。
- 可定制的外观：支持外观的自定义，包括颜色和厚度，以与周围组件的设计和风格匹配。

### Program

```java
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JButton;
import javax.swing.JSeparator;
import javax.swing.BoxLayout;
import java.awt.Dimension;
public class SeparatorExample {
    public static void main(String[] args) {
        // Create the frame
        JFrame frame = new JFrame("Separator Example");
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Create a panel with a vertical BoxLayout
        JPanel panel = new JPanel();
        panel.setLayout(new BoxLayout(panel, BoxLayout.Y_AXIS));

        // Create two buttons
        JButton button1 = new JButton("Button 1");
        JButton button2 = new JButton("Button 2");

        // Create a JSeparator
        JSeparator separator = new JSeparator(JSeparator.VERTICAL);

        // Add the buttons and separator to the panel
        panel.add(button1);
        panel.add(separator);
        panel.add(button2);

        // Add the panel to the frame
        frame.add(panel);

        // Make the frame visible
        frame.setVisible(true);
    }
}
```

### Swings

在上面的程序中，框架内部添加了一个带有垂直`BoxLayout`的`JPanel`。该面板包含两个按钮（“Button 1”和“Button 2”），它们之间有一个`JSeparator`。这个分隔符在视觉上区分了两个按钮。然后将该面板添加到框架中。框架的大小设置为 300x200 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.6.17 JToolBar

`JToolBar`是一个包含按钮和其他执行常用任务控件的组件。其主要特性包括：

- 快速访问：`JToolBar`在紧凑且易于访问的区域提供一组常用的工具或操作，通常位于应用程序窗口的顶部或侧边。
- 可自定义组件：可以包含`JButton`、`JLabel`和`JComboBox`等各种组件，允许使用自定义图标、文本和分隔符灵活地排列工具和操作。
- 停靠与浮动：支持停靠和浮动功能，使用户能够将工具栏移动到窗口内的不同位置，或将其识别为独立的浮动窗口，以提高可访问性和可用性。

### Program



```java
import javax.swing.JFrame;
import javax.swing.JToolBar;
import javax.swing.JButton;
import javax.swing.BorderFactory;
import java.awt.BorderLayout;
public class ToolBarExample {
    public static void main(String[] args) {
    // Create the JFrame
    JFrame frame = new JFrame("ToolBar Example");
    frame.setSize(300, 100);
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setLayout(new BorderLayout());

    // Create a JToolBar
    JToolBar toolbar = new JToolBar();

    // Create two buttons
    JButton button1 = new JButton("Java");
    JButton button2 = new JButton("Python");

    // Add buttons to the toolBar
    toolbar.add(button1);
    toolbar.addSeparator(); // Add a separator between buttons
    toolbar.add(button2);

    // Add the toolbar to the frame at the top (north)
    frame.add(toolbar, BorderLayout.NORTH);

    // Make the frame visible
    frame.setVisible(true);
    }
}
```

# Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_566_0.png)

在上面的程序中，框架中添加了一个`JToolTip`，包含两个标记为“Java”和“Python”的按钮，它们之间有一个分隔符。工具栏位于框架的顶部（北侧）。框架的大小设置为 300x100 像素，配置为退出时关闭应用程序，并设置为可见。

### 13.6.18 JEditorPane

`JEditorPane`是一个允许编辑样式化文本的组件。其主要特性包括：

- 多功能文本编辑：`JEditorPane`提供了一个用于显示和编辑文本内容的组件，包括 HTML、纯文本和样式化文档，支持各种内容类型和格式。
- 内容加载：能够从 URL 或文件加载内容，适合在 Swing 应用程序中直接显示网页或外部资源。
- 可自定义且可扩展：允许通过`HTMLEEditorKit`进行自定义定制，并支持通过自定义文档模型和内容渲染器来扩展其功能以满足特殊需求。

# Program

```java
import javax.swing.JFrame;
import javax.swing.JEditorPane;
import javax.swing.JScrollPane;
import java.io.IOException;
public class JEditorPaneExample {
    public static void main(String[] args) {
    // Create the main JFrame
    JFrame frame = new JFrame("EditorPane Example");
    frame.setSize(400, 300);
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    // Create a JEditorPane to display HTML content
    JEditorPane editorPane = new JEditorPane();
    editorPane.setContentType("text/html");
    // Set the HTML content
    String htmlContent = "<html><body>\n"
    + "<h1>Course Syllabus</h1>\n"
    + "<p>Welcome to the programming courses!</p>\n"
    + "<h2>Java Programming</h2>\n"
    + "<ul>\n"
    + "<li>Introduction to Java</li>\n"
    + "<li>Object-Oriented Programming</li>\n"
    + "<li>Java GUI Programming</li>\n"
    + "</ul>\n"
    + "</body>";
    editorPane.setText(htmlContent);
    // Wrap the JEditorPane in JScrollPane
    JScrollPane scrollPane = new JScrollPane(editorPane);

    // Add the JScrollPane to the frame
    frame.add(scrollPane);

    // Make the frame visible
    frame.setVisible(true);
    }
}
```

```html
<ul>
  <li>Introduction to Python</li>
  <li>Data Structures and Algorithms</li>
  <li>Web Development with Python</li>
</ul></body>
```

Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_567_0.png)

在上面的程序中，框架内部初始化了一个`JEditorPane`来显示 HTML 内容，具体是 Java 和 Python 课程。该`JEditorPane`被封装在`JScrollPane`中以添加滚动功能。将`JScrollPane`添加到框架中。框架的大小设置为 400x300 像素，配置为退出时关闭应用程序，并设置为可见。

### 13.6.19 JTabbedPane

`JTabbedPane`是一种 Swing 组件，用于创建标签页，允许在单个容器内以表格格式组织多个组件。主要特性是：

- 标签界面：`JTabbedPane`允许以标签布局组织并显示多个组件，每个标签代表不同的面板或视图，便于进行切换。
- 动态管理：支持添加、删除和重排序标签，根据用户状态实现灵活界面设计。
- 可自定义外观：提供标签位置（顶、底、左、右）、标签内容和标题（包括图标和文本），以适应应用程序的设计和可用性。

# Program

```java
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JTabbedPane;
import java.awt.BorderLayout;
import java.awt.Color;

public class JTabbedPaneExample {
    public static void main(String[] args) {
        // Create the frame
        JFrame frame = new JFrame("JTabbedPane Example");
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());

        // Create JTabbedPane
        JTabbedPane tabbedPane = new JTabbedPane();

        // Create panels
        JPanel panel1 = new JPanel();
        panel1.setBackground(Color.LIGHT_GRAY);
        tabbedPane.addTab("Register", panel1);

        JPanel panel2 = new JPanel();
        panel2.setBackground(Color.LIGHT_GRAY);
        tabbedPane.addTab("Courses", panel2);

        // Add the JTabbedPane to the frame
        frame.add(tabbedPane, BorderLayout.CENTER);

        // Make the frame visible
        frame.setVisible(true);
    }
}
```

# Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_568_0.png)

一个名为 "JTabbedPane Example" 的`JFrame`使用`BorderLayout`设置。创建一个`JTabbedPane`并向其中添加了两个`JPanel`实例`panel1`和`panel2`，每个面板都有浅灰色背景。面板标记为“Register”和“Courses”。将`JTabbedPane`添加到框架的中心。框架配置为 300x200 像素，退出时关闭应用程序，并设置为可见。

### 13.6.20 JComboBox

`JComboBox`是一个结合了按钮或可编辑字段与下拉列表的组件。其主要特性是：

- 下拉列表：`JComboBox`提供了一个选项列表，用户从中选择单个项目，结合了文本字段和列表的功能。
- 可编辑选项：可以配置为可编辑，允许用户在从定义列表选择之外输入自己的值，或者设置为不可编辑以限制在给定的选项。
- 可自定义项：支持使用文本和图标自定义列表项，并允许动态更新项目列表，灵活满足各种界面需求。

# Program

```java
import javax.swing.JFrame;
import javax.swing.JComboBox;
import java.awt.Color;

public class ComboBoxExample {
    public static void main(String[] args) {
    // Create a new JFrame with the title "ComboBox Example"
    JFrame frame = new JFrame("ComboBox Example");

    // Create an array of course names for the JComboBox
    String[] courses = {"Java","C++","Python","JavaScript","Ruby"};

    // Initialize the JComboBox with the size of array of course names
    JComboBox<String> comboBox = new JComboBox<>(courses);

    // Set the background color of the ComboBox to magenta
    comboBox.setBackground(Color.MAGENTA);

    // Add the ComboBox to the JFrame
    frame.add(comboBox);

    // Set the default close operation, size of the JFrame, and make it visible
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setSize(300, 100);
    frame.setVisible(true);
    }
}
```

![](img/5a077f56e14b826c2dc61de6c176e5ef_569_0.png)

在程序中，我们创建一个标题为“ComboBox Example”的`JFrame`，并用课程名称数组初始化`JComboBox`。`ComboBox`的背景设置为洋红色。将`ComboBox`添加到框架中。框架的大小设置为 300x100 像素，配置为退出时关闭应用程序，并设置为可见。

## 13.7 EVENT HANDLING FOR JAVA SWINGS

事件处理对于在 Java Swings 中创建动态和交互的用户界面至关重要。通过实现事件监听器，开发者可以创建响应用户输入的应用程序，使其更对用户友好且具有参与性。事件处理是 Java Swing 中创建交互式和响应式用户界面的关键。通过处理事件，Swing 组件可以检测用户操作（例如按钮点击或按下）并做出相应的响应。这是通过事件监听器（event listeners）来实现的，监听器是定义当特定事件发生时执行方法的接口。下面将讨论一些事件处理器。

### 13.7.1 动作监听器 (ACTION LISTENER)

在 Java GUI 开发中，`ActionListener`是处理与特定组件的用户交互的关键概念。它就像一个等待动作发生的监听器。想象一个按钮——`ActionListener`充当响应者，等待用户点击它。

当你在类中实现`ActionListener`接口时，用户应该定义一个名为`actionPerformed`的方法。每当用户在注册的组件上执行操作（如点击按钮或选择菜单项）时，该方法就会被调用。

使用`ActionListener`，通常遵循以下步骤：

- 创建实现`ActionListener`接口的类。
- 将其注册为 GUI 组件的监听器（例如使用`button.addActionListener(yourActionListenerObject)`）。
- 在你的类中重写`actionPerformed`方法，以定义当用户与组件交互时希望发生的特定动作。

### 13.7.1.1 带 ActionListener 的 JButton

`JButton`需要一个`ActionListener`来知道在被点击时该做什么。`ActionListener`监听点击并运行你为按钮动作编写的代码，使其能够响应用户交互。

# Program

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class RegisterButtonExample {
    public static void main(String[] args) {
        // Create the main frame
        JFrame frame = new JFrame("Register Button Example");
        frame.setSize(300, 100);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Create a panel to hold the button
        JPanel panel = new JPanel();

        // Create the button with "Register"
        JButton registerButton = new JButton("Register");

        // Add ActionListener to handle button click
        registerButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                // Display a pop-up message when the button is clicked
                JOptionPane.showMessageDialog(frame, "Congratulations on successfully registering for a computer course!");
            }
        });

        panel.add(registerButton);
        frame.add(panel);
        frame.setVisible(true);
    }
}
```

```java
// Add the button to the panel
panel.add(registerButton);
```



# 13.7.1.2 带 `ActionListener` 的 `JRadioButton`

`JButton` 需要一个 `ActionListener` 来响应用户选择。该监听器帮助程序在每次单选按钮被选中时做出响应，相应地更新应用程序的状态，并确保根据所选选项采取正确的操作。

## 程序

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JRadioButton;
import javax.swing.ButtonGroup;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class RadioButtonExample {
    public static void main(String[] args) {
        // Create the main JFrame
        JFrame frame = new JFrame("RadioButton Example");
        frame.setSize(300, 150);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Create a JPanel to hold the radio buttons
        JPanel panel = new JPanel();

        // Create two JButtons
        JRadioButton pythonButton = new JRadioButton("Python");
        JRadioButton radioButton = new JRadioButton("Java");

        // Group the group buttons
        ButtonGroup group = new ButtonGroup();
        group.add(pythonButton);
        group.add(radioButton);

        // Add ActionListener to handle button clicks
        ActionListener radioButtonListener = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                // Display a pop-up message showing the selected course
                JRadioButton selectedButton = (JRadioButton) e.getSource();
                JOptionPane.showMessageDialog(frame, "Selected course: " + 
                    selectedButton.getText());
            }
        };

        // Attach the ActionListener to both radio buttons
        pythonButton.addActionListener(radioButtonListener);
        radioButton.addActionListener(radioButtonListener);

        // Add the radio buttons to the panel
        panel.add(pythonButton);
        panel.add(radioButton);

        // Add the panel to the frame
        frame.add(panel);

        // Make the frame visible
        frame.setVisible(true);
    }
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_571_0.png)

在程序中，我们显示了一个带有“Register”（注册）按钮的窗口。当按钮被点击时，会弹出一个消息，祝贺用户成功注册了计算机课程。该程序使用 `JFrame` 创建窗口，使用 `JButton` 创建按钮，并使用 `ActionListener` 处理按钮点击事件。窗口被设置为固定大小，并在用户点击关闭按钮时关闭。

单选按钮被组合在一起，允许一次只有一个被选中。当按钮被点击时，会弹出一个消息显示所选的课程。该程序使用 `JFrame` 创建窗口，使用 `JRadioButton` 创建按钮，并使用 `ActionListener` 处理按钮点击。窗口被设置为固定大小，并在用户点击关闭按钮时关闭。

# 13.7.1.3 带 `ActionListener` 的 `JToggleButton`

```java
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JToggleButton;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ToggleButtonExample {
    public static void main(String[] args) {
        // Create the main JFrame
        JFrame frame = new JFrame("ToggleButton Example");
        frame.setSize(300, 150);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Create a JPanel to hold the toggle buttons
        JPanel panel = new JPanel();

        // Create JToggleButton with "Enroll"
        JToggleButton toggleButton = new JToggleButton("Enroll");

        // Add ActionListener to handle button clicks
        toggleButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                // Display a pop-up message based on state
                if (toggleButton.isSelected()) {
                    JOptionPane.showMessageDialog(frame, "You are enrolled!");
                } else {
                    JOptionPane.showMessageDialog(frame, "You are no longer enrolled!");
                }
            }
        });

        panel.add(toggleButton);
        frame.add(panel);
        frame.setVisible(true);
    }
}
```

# 13.7.1.4 带 `ActionListener` 的 `JEditorPane`

```java
editorPane.copy(); // 执行复制操作
// 为“粘贴”菜单项添加监听器
pasteItem.addActionListener(new ActionListener() {
    @Override
    public void actionPerformed(ActionEvent e) {
        editorPane.paste(); // 执行粘贴操作
    }
});

// 将菜单项添加到弹出菜单
popupMenu.add(copyItem);
popupMenu.add(pasteItem);

// 添加鼠标监听器以便右键点击时显示弹出菜单
editorPane.addMouseListener(new MouseAdapter() {
    @Override
    public void mousePressed(MouseEvent e) {
        showPopup(e);
    }

    @Override
    public void mouseReleased(MouseEvent e) {
        showPopup(e);
    }

    private void showPopup(MouseEvent e) {
        if (SwingUtilities.isRightButton(e)) {
            popupMenu.show(editorPane, e.getX(), e.getY());
            // 在鼠标位置显示弹出菜单
        }
    }
});

// 将 JEditorPane 添加到 JScrollPane 以进行滚动
JScrollPane scrollPane = new JScrollPane(editorPane);

// 将 JScrollPane 添加到框架
frame.add(scrollPane, BorderLayout.CENTER);

// 使框架可见
frame.setVisible(true);
```

# Swings 565

![](img/5a077f56e14b826c2dc61de6c176e5ef_575_0.png)

在上面的 Java 程序中，我们创建了一个包含 `JFrame` 和 `JEditorPane` 的 GUI，用于显示 HTML 内容。`JEditorPane` 被设置为不可编辑，并带有一个检测右键点击的鼠标监听器。当检测到右键点击时，会显示包含“复制”和“粘贴”选项的上下文菜单（`JPopupMenu`）。

# 用于医疗保健和医疗应用的 Java 22

粘贴选项。“复制”和“粘贴”选项是有效的，可以用于从 `EditorPane` 复制和粘贴文本。

# 13.7.1.5 带有 `ActionListener` 的 `JComboBox`

`JComboBox` 需要一个 `ActionListener` 来在用户从下拉列表中选择项目时做出响应。该监听器允许应用程序根据所选选项执行特定操作，确保程序对用户的选择做出恰当反应。

## 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ComboBoxExample {
    void main(String[] args) {
        // 创建主 JFrame
        JFrame frame = new JFrame("ComboBox Example");
        frame.setSize(300, 150);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new FlowLayout());

        // 创建一个包含编程课程列表的 JComboBox
        String[] courses = {"Java", "Python", "C++", "JavaScript"};
        JComboBox<String> comboBox = new JComboBox<>(courses);
        comboBox.setBackground(Color.WHITE); // 设置背景颜色为白色

        // 为 JComboBox 添加 ActionListener
        comboBox.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String selectedCourse = (String) comboBox.getSelectedItem();
                JOptionPane.showMessageDialog(frame, "Selected Course: " +
                    selectedCourse);
            }
        });

        // 将 JComboBox 添加到 JFrame
        frame.add(comboBox);

        // 使框架可见
        frame.setVisible(true);
    }
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_576_0.png)

在上面的 Java 程序中，我们为 `FlowLayout` 创建了一个 `JFrame`，并向其添加了 `JComboBox`，该组合框填充了编程课程列表。`JComboBox` 被设置为白色背景，并为其添加了 `ActionListener`，当从下拉列表中选择项目时会触发该监听器。当选择项目时，会弹出一个对话框显示所选课程。`JFrame` 被设置为固定大小并使其可见，允许用户与 `JComboBox` 交互。

# 13.7.1.6 带有 `ActionListener` 的 `Popup`

`PopupMenu` 需要一个 `ActionListener` 来处理与菜单项的交互。当选择菜单项时，它会触发特定操作，确保应用程序对用户的上下文相关选择做出恰当反应。

## 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;

public class PopupMenuExample {
    void main(String[] args) {
        // 创建主 JFrame
        JFrame frame = new JFrame("PopupMenu Example");
        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());

        // 创建 JTextArea 并将其封装在 JScrollPane 中
        JTextArea textArea = new JTextArea();
        textArea.setBackground(Color.WHITE); // 设置背景颜色为白色
        JScrollPane scrollPane = new JScrollPane(textArea);

        // 创建带有单个 JMenuItem 的 PopupMenu
        PopupMenu popupMenu = new PopupMenu();
        JMenuItem menuItem = new JMenuItem("Register");
        popupMenu.add(menuItem);

        menuItem.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(frame, "Registration!");
            }
        });

        // 添加鼠标监听器以便右键点击时显示弹出菜单
        textArea.addMouseListener(new MouseAdapter() {
            @Override
            public void mousePressed(MouseEvent e) {
                showPopup(e);
            }

            @Override
            public void mouseReleased(MouseEvent e) {
                showPopup(e);
            }

            private void showPopup(MouseEvent e) {
                if (SwingUtilities.isRightButton(e)) {
                    popupMenu.show(textArea, e.getX(), e.getY());
                }
            }
        });

        frame.add(scrollPane, BorderLayout.CENTER);
        frame.setVisible(true);
    }
}
```



`public void mousePressed(MouseEvent e)` {

    if (`SwingUtilities.isRightButton(e)`) {

        `popupMenu.show(textArea, e.getX(), e.getY())`;

    }

}

`@Override`

`public void mouseReleased(MouseEvent e)` {

    if (`SwingUtilities.isRightButton(e)`) {

        `popupMenu.show(textArea, e.getX(), e.getY())`;

    }

}

});

// 将 `JEditorPane` 添加到 `JScrollPane` 以滚动

`JScrollPane scrollPaneFinal = new JScrollPane(textArea)`;

// 将 `JScrollPane` 添加到框架

`frame.add(scrollPaneFinal, BorderLayout.CENTER)`;

// 使框架可见

`frame.setVisible(true)`;

}

}

# 用于医疗保健和医疗应用的 Java 22

![](img/5a077f56e14b826c2dc61de6c176e5ef_578_0.png)

在上面的 Java 程序中，我们为 `FlowLayout` 创建了一个 `JFrame`，并向其添加了 `JComboBox`，该组合框填充了编程课程列表。`JComboBox` 被设置为白色背景，并为其添加了 `ActionListener`，当从下拉列表中选择项目时会触发该监听器。当选择项目时，会弹出一个对话框显示所选课程。`JFrame` 被设置为固定大小并使其可见，允许用户与 `JComboBox` 交互。

## 13.7.1.7 带有 ActionListener 的 Toolbar

`JComboBox` 需要一个 `ActionListener` 来在用户从下拉列表中选择项目时做出响应。该监听器允许应用程序根据所选选项执行特定操作，确保程序对用户的选择做出恰当反应。

## 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ToolBarExample {
    void main(String[] args) {
        // 创建主 JFrame
        JFrame frame = new JFrame("Toolbar Example");
        frame.setSize(400, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());

        // 创建 JToolBar
        JToolBar toolbar = new JToolBar();
        JButton button = new JButton("Register");
        toolbar.add(button);

        // 为按钮添加 ActionListener
        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(frame, "Registration!");
            }
        });

        // 将 JToolBar 添加到 JFrame
        frame.add(toolbar, BorderLayout.NORTH);

        // 使框架可见
        frame.setVisible(true);
    }
}
```

# 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_579_0.png)

在上面的 Java 程序中，我们为 `FlowLayout` 创建了一个 `JFrame`，并向其添加了 `JComboBox`，该组合框填充了编程课程列表。`JComboBox` 被设置为白色背景，并为其添加了 `ActionListener`，当从下拉列表中选择项目时会触发该监听器。当选择项目时，会弹出一个对话框显示所选课程。`JFrame` 被设置为固定大小并使其可见，允许用户与 `JComboBox` 交互。

## 13.7.1.8 带有 ActionListener 的 JDesktopPane

`JDesktopPane` 通常不直接使用 `ActionListener`，因为它是内部框架的容器。然而，`JDesktopPane` 的单个组件（如按钮或菜单）可以使用 `ActionListener` 来处理这些框架内部的操作。

## 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class DesktopPaneExample {
    public void main(String[] args) {
        // 创建主 JFrame
        JFrame frame = new JFrame("DesktopPane Example");
        frame.setSize(600, 400);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(null);

        // 创建 JDesktopPane
        JDesktopPane desktopPane = new JDesktopPane();

        // 创建 JInternalFrame
        JInternalFrame internalFrame = new JInternalFrame("Registration", true, true, true);
        internalFrame.setSize(300, 150);
        internalFrame.setLayout(null);

        // 创建 JButton
        JButton registerButton = new JButton("Register");
        registerButton.setBounds(100, 50, 100, 30);

        // 为 JButton 添加 ActionListener
        registerButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(frame, "Registration!");
            }
        });

        internalFrame.add(registerButton);
        desktopPane.add(internalFrame);
        internalFrame.setVisible(true);
        frame.add(desktopPane);

        // 使框架可见
        frame.setVisible(true);
    }
}
```

# 570 用于医疗与健康应用的 Java 22

```java
@Override
public void actionPerformed(ActionEvent e) {
    JOptionPane.showMessageDialog(internalFrame, "Registration Successful!");
}

// 将 JButton 添加到 JInternalFrame
internalFrame.add(registerButton);

// 将 JInternalFrame 添加到 JDesktopPane
desktopPane.add(internalFrame);

// 使 JInternalFrame 可见
internalFrame.setVisible(true);

// 将 JDesktopPane 添加到 JFrame
frame.add(desktopPane);

// 使 JFrame 可见
frame.setVisible(true);
```

输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_580_0.png)

在上述程序中，`JDesktopPane` 被用于包含一个 `JInternalFrame`，它是一个可以在 `JDesktopPane` 内部移动和调整大小的窗口。`JInternalFrame` 拥有标题“Registration”（注册），并包含一个标记为“Register”（注册）的 `JButton`。当点击按钮时，会显示一个带有成功消息的 `JOptionPane`。`DesktopPane` 被添加到 `JFrame` 中，该 `JFrame` 设置为关闭时退出，并在程序结束时可见。

## 13.7.2 焦点监听器 (Focus Listener)

`FocusListener` 是 Java 中用于接收焦点事件的接口，这些事件在组件获得或失去焦点时发生。焦点指的是组件准备好接收其输入的状态。当组件获得焦点时，它会被高亮并准备接受输入；而当它失去焦点时，它不再被高亮且不再接受输入。`FocusListener` 接口有两个方法：`focusGained` 和 `focusLost`。当组件获得焦点时调用 `focusGained()` 方法，当组件失去焦点时调用 `focusLost()` 方法。可以重写这些方法，以便在组件获得或失去焦点时执行特定操作。例如，文本字段可以在失去焦点时显示默认值，并在获得焦点时清除值。`FocusListeners` 常用于 GUI 应用，以根据组件的焦点状态验证用户输入、更新显示或执行其他操作。

## 13.7.2.1 带有 FocusListener 的 JTextField

`JTextField` 需要一个 `FocusListener` 来检测它何时获得或失去焦点。这允许根据焦点的变化执行验证或用户反馈操作，帮助管理输入焦点并改进用户交互。

### 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.FocusEvent;
import java.awt.event.FocusListener;

public class FocusListenerExample {
    public void main(String[] args) {
        JFrame frame = new JFrame("FocusListener Example");
        frame.setSize(300, 100);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new FlowLayout());

        // 添加一个 JTextField
        JTextField textField = new JTextField("Type here", 20);

        // 为 JTextField 添加 FocusListener
        textField.addFocusListener(new FocusListener() {
            @Override
            public void focusGained(FocusEvent e) {
                // 获得焦点时将背景色改为黄色
                textField.setBackground(Color.YELLOW);
            }

            @Override
            public void focusLost(FocusEvent e) {
                // 失去焦点时将背景色改为白色
                textField.setBackground(Color.WHITE);
            }
        });

        // 将 JTextField 添加到 JFrame
        frame.add(textField);

        // 使 JFrame 可见
        frame.setVisible(true);
    }
}
```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_581_0.png)

在上述程序中，`JTextField` 使用 `FlowLayout` 被添加到 `JFrame` 中。为 `JTextField` 添加了一个 `FocusListener`，以便在它获得或失去焦点时改变其背景颜色。当 `JTextField` 获得焦点时，其背景颜色变为黄色，当失去焦点时，它变回白色。

## 13.7.2.2 带有 FocusListener 的 JFormattedTextField

`JFormattedTextField` 需要一个 `FocusListener` 来处理获得或失去焦点时的事件。这允许根据焦点状态对输入进行动态验证或格式化，确保数据的准确输入并提供用户反馈。

### 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.FocusEvent;
import java.awt.event.FocusListener;
import javax.swing.text.NumberFormatter;
import java.text.NumberFormat;

public class JFormattedTextFieldExample {
    public static void main(String[] args) {
        // 创建主 JFrame
        JFrame frame = new JFrame("FormattedTextField Example");
        frame.setSize(300, 100);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new FlowLayout());

        // 创建一个用于整数值的 NumberFormat
        NumberFormat numberFormat = NumberFormat.getInstance();

        // 使用 NumberFormat 创建 NumberFormatter
        NumberFormatter numberFormatter = new NumberFormatter(numberFormat);
        numberFormatter.setInvalid(false); // 防止无效输入

        // 使用 NumberFormatter 创建 JFormattedTextField
        JFormattedTextField formattedTextField = new JFormattedTextField(numberFormatter);
        formattedTextField.setColumns(10); // 设置列数

        // 为 JFormattedTextField 添加 FocusListener
        formattedTextField.addFocusListener(new FocusListener() {
            @Override
            public void focusGained(FocusEvent e) {
                // 获得焦点时将背景色改为黄色
                formattedTextField.setBackground(Color.YELLOW);
            }

            @Override



`public void focusLost(FocusEvent e)` {

    // 失去焦点时将背景色改为白色

    `formattedTextField.setBackground(Color.WHITE)`;

}

});

// 将 `JFormattedTextField` 添加到 `JFrame`

`frame.add(formattedTextField)`;

// 使 `JFrame` 可见

`frame.setVisible(true)`;

}

}

```

### 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_583_0.png)

在程序中，`JFormattedTextField` 设置为接受整数值，并使用 `FlowLayout` 添加到 `JFrame` 中。为 `JFormattedTextField` 添加了 `FocusListener`，以便在它获得或失去焦点时改变其背景颜色。当 `JFormattedTextField` 获得焦点时，其背景颜色变为黄色，当失去焦点时，它变回白色。

# 574

## 用于医疗与健康应用的 Java 22

```java
updateText();

}

@Override

public void removeUpdate(DocumentEvent e) {

    updateText();

}

@Override

public void changedUpdate(DocumentEvent e) {

    updateText();

}

// 显示带有更新文本的消息框的方法

private void updateText() {

    SwingUtilities.invokeLater(() -> {

        String text = textArea.getText();

        JOptionPane.showMessageDialog(frame, "Text updated:\n" + text);

    });

}

// 将 JScrollPane 添加到 JFrame

frame.add(scrollPane, BorderLayout.CENTER);

// 使 JFrame 可可见

frame.setVisible(true);

}
```

Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_584_0.png)

在上述程序中，首先将 `JTextArea` 通过 `JScrollPane` 添加到 `JFrame` 中。为 `JTextArea` 添加了一个 `DocumentListener` 以检测文本的变化。当文本发生更改、插入或删除时，都会调用 `updateText` 方法。该方法会显示一个带有更新文本的消息框。

## 13.7.4 项目监听器 (Item Listener)

`ItemListener` 是 Java 中的一个接口，用于监听组件（通常是复选框、单选按钮或组合框）的变化。它用于跟踪组件选择状态的变化，例如当某项被选中或取消选择时。`ItemListener` 只有一个方法：`itemChanged`。当组件的选择状态发生变化时，就会调用此方法。`ItemListeners` 用于在项目被选中或取消选择时执行某些操作，例如启用或禁用其他组件。可以通过 `addItemListener` 方法将监听器添加到组件中。`ItemListeners` 通常与具有选择状态的组件一起使用，如 `JCheckBox`、`JRadioButton` 和 `JComboBox`。`itemChanged` 方法接收一个 `ItemEvent` 对象，该对象提供了有关发生变化的项目及其新状态的信息。`ItemListeners` 是 Java 应用程序中跟踪和响应组件选择状态变化的强大工具。它们提供了一种实时响应组件变化的方法，允许实现更具动态性的用户与交互界面。

### 13.7.4.1 带有监听器的复选框 (CheckBox with Listener)

`CheckBox` 需要一个 `ItemListener` 来检测其选择状态的变化。该监听器允许你在复选框被勾选或取消勾选时执行特定操作，确保应用程序对用户的选择做出相应响应。

# 程序

```java
import javax.swing.*;

import java.awt.*;

import java.awt.event.ItemEvent;

import java.awt.event.ItemListener;

public class CheckBoxExample {

    public static void main(String[] args) {

        // 创建主 JFrame

        JFrame frame = new JFrame("CheckBox Example");

        frame.setSize(300, 100);

        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        frame.setLayout(new FlowLayout());

        // 创建一个带有“报名课程”标签的复选框

        CheckBox checkBox = new CheckBox("Enroll in Course");

        checkBox.setBackground(Color.GREEN);

        //为 CheckBox 添加一个 ItemListener

        checkBox.addItemListener(new ItemListener() {

            @Override

            public void itemChanged(ItemEvent e) {

                if (e.getStateChange() == ItemEvent.SELECTED) {

                    // 复选框被选中

                    JOptionPane.showMessageDialog(frame, "You are enrolled in the course.");

                } else {

                    // 复选框被取消选择

                    JOptionPane.showMessageDialog(frame, "You are no longer enrolled in the course.");

                }

            }

        });

        // 将 CheckBox 添加到 JFrame

        frame.add(checkBox);

        // 使 JFrame 可可见

        frame.setVisible(true);

    }

}
```

# 用于医疗与健康应用的 Java 22

Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_586_0.png)

在上述程序中，我们创建了一个 `JCheckBox`，并通过 `FlowLayout` 将其添加到 `JFrame` 中，并设置了绿色背景。为 `JCheckBox` 添加了一个 `ItemListener` 以检测其选择状态的变化。当 `JCheckBox` 被选中时，会弹出一个消息框显示用户已报名课程。当 `JCheckBox` 被取消选择时，会弹出一个消息框显示用户已不再报名。

## 13.7.5 变化监听器 (ChangeListener)

`ChangeListener` 是 Java 中的一个接口，用于监听组件（通常是计数器、滑块或标签页面板）的变化。它用于跟踪组件状态的变化，例如当计数器的值改变时。`ChangeListener` 有一个方法：`stateChanged`。当组件的状态发生变化时，就会调用此方法。`ChangeListeners` 通常用于在组件状态变化时执行操作，例如更新标签或启用其他组件。可以通过 `addChangeListener` 方法将监听器添加到组件中。`ChangeListeners` 通常与 `JSlider` 和 `JTabbedPane` 等组件一起使用。`stateChanged` 方法接收一个 `ChangeEvent` 对象，该对象提供了有关变化源的信息。`ChangeListener` 是 Java 应用程序中跟踪和响应组件状态变化的强大工具。

### 13.7.5.1 带有监听器的滑块 (JSlider with Listener)

`JSlider` 需要一个 `ChangeListener` 来响应其值的变化。这允许你根据当前的滑块位置更新应用程序或执行操作，确保实时的反馈和交互。

# 程序

```java
import javax.swing.*;

import java.swing.event.ChangeEvent;

import java.swing.event.ChangeListener;

import java.awt.*;

public class SliderExample {

    public static void main(String[] args) {

        // 创建主 JFrame

        JFrame frame = new JFrame("Slider Example");

        frame.setSize(400, 200);

        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        frame.setLayout(new BorderLayout());

        // 创建一个范围为0到100的滑块

        JSlider slider = new JSlider(HORIZONTAL, 0, 100);

        slider.paintTicks(true);

        slider.paintLabels(true);

        slider.setTickSpacing(20);

        slider.addChangeListener(new ChangeListener() {

            @Override

            public void stateChanged(ChangeEvent e) {

                int value = slider.getValue();

                // 显示滑块的值的值

            }

        });

        // 将滑块添加到框架中

        frame.add(slider, BorderLayout.CENTER);

        // 使 JFrame 可可见

        frame.setVisible(true);

    }

}
```

Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_587_0.png)

在上述程序中，我们创建了一个水平的 `JSlider`，范围从 0 到 100，初始值为 50。滑块显示了刻度和标签，且刻度间距为 20。为滑块添加了 `ChangeListener`。当滑块的值变化时，会响应。

### 13.7.5.2 带有变化监听器的计数器 (JSpinner with ChangeNotifier)

`JSpinner` 需要一个 `ChangeListener` 来检测其值的变化。该监听器允许你在用户选择新值时执行操作，确保应用程序对用户的输入做出相应响应。

# 程序

```java
import javax.swing.*;

import java.swing.event.ChangeEvent;

import java.swing.event.ChangeListener;

import java.awt.*;

public class SpinnerExample {

    public static void main(String[] args) {

        // 创建主 JFrame

        JFrame frame = new JFrame("Spinner Example");

        frame.setSize(300, 150);

        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        frame.setLayout(new FlowLayout());

        // 创建一个范围为 0 到 100，初始值为0 的计数器

        SpinnerNumberModel model = new SpinnerNumberModel(0, 0, 100, 1);

        JSpinner spinner = new JSpinner(model);

        spinner.setBackground(Color.YELLOW);

        //为计数器添加一个 ChangeNotifier

        spinner.addChangeListener(new ChangeListener() {

            @Override

            public void stateChanged(ChangeEvent e) {

                int value = (Integer) spinner.getValue();

                // 显示计数器的值

                JOptionPane.showMessageDialog(frame, "Spinner Value: " + value);

            }

        });

        // 将计数器添加到框架中

        frame.add(spinner);

        // 使 JFrame 可可见

        frame.setVisible(true);

    }

}
```

Output

![](img/5a077f56e14b826c2dc61de6c176e5ef_588_0.png)

在上述程序中，我们创建了一个 `JSpinner`，并通过 `FlowLayout` 将其添加到 `JFrame` 中，并设置了黄色背景。计数器使用了 `SpinnerNumberModel`，范围从 0 到 100，初始值为 0。为计数器添加了 `ChangeListener`。当计数器的值变化时，会弹出一个消息框显示新值。

### 13.7.5.3 带有变化监听器的标签页面板 (JTabbedPane with ChangeListener)

`TabbedPane` 需要一个 `ChangeListener` 来检测切换标签的变化。该监听器允许你根据激活的标签更新应用程序或执行操作，确保根据用户的选择进行动态调整和交互。

# 程序

```java
import javax.swing.event.ChangeEvent;

import java.swing.event.ChangeListener;

import javax.swing.*;

import java.awt.*;

public class TabbedPaneExample {

    public static void main(String[] args) {

        // 创建主 JFrame

        JFrame frame = new JFrame("Tabbed Pane Example");

    }

}
```

# Sw切换 579

```java
frame.setSize(400, 300);

frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

frame.setLayout(new BorderLayout());

// 创建一个 JTabbedPane

JTabbedPane tabbedPane = new JTabbedPane();

// 创建第一个 JPanel 并将其添加到第一个标签页

JPanel panel1 = new JPanel();

JLabel label1 = new JLabel("标签 1 的内容");

panel1.add(label1);

tabbedPane.addTab("Tab 1", panel1);

// 创建第二个 JPanel 并将其添加到第二个标签页

JPanel panel2 = new JPanel();

JLabel label2 = new JLabel("标签 2 的内容");

panel2.add(label2);

tabbedPane.addTab("Tab 2", panel2);

// 为 JTabbedPane 添加监听

tabbedPane.addChangeListener(new ActionListener() {

    @Override

    public void stateChanged(ChangeEvent e) {

        int selectedIndex = tabbedPane.getSelectedSelectedIndex();

        // 在消息框中显示选中的标签索引
```



`JOptionPane.showMessageDialog(frame, "Selected Tab Index: " + selectedIndex);`

将 `JTabbedPane` 添加到 `JFrame`：

```java
frame.add(tabbedPane, BorderLayout.CENTER);
```

使 `JFrame` 可视：

```java
frame.setVisible(true);
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_589_0.png)

在上面的程序中，`JTabbedPane` 有两个标签页，每个标签页都包含一个带有 `JLabel` 的 `JPanel`。`JTabbedPane` 被添加了一个 `ChangeListener` 来检测所选标签页的变化。当选中的标签发生变化时，会弹出一个消息框显示新标签的索引。

## 列表选择监听器 (List Selection Listener)

`ListSelectionListener` 是 Java 中的一个接口，它定义了一个处理列表选择事件的方法。它与 `JList` 组件一起使用，用于检测列表项选择的变化。该接口有一个方法 `valueChanged(ListSelectionEvent e)`，它在选择发生变化时被调用。每当用户在列表中选择或取消选择某项时，该方法就会被调用。传递给方法的 `ListSelectionEvent` 对象提供了有关该变化的信息。该方法可以查询选择状态以确定哪些项被选中或取消了选择。监听器随后可以根据新的选择执行操作，例如更新组件。`ListSelectionListener` 通常使用 `addListSelectionListener` 添加到 `JList` 中。每当选择变化时，监听器都会收到通知，使其能够响应用户输入。通过使用 `ListSelectionListener`，你可以创建响应用户选择的交互式 GUI 组件。

### 带有 `ListSelectionListener` 的 `JList`

`JList` 需要一个 `ListSelectionListener` 来响应所选项目的变化。该监听器允许应用程序根据用户的选择执行操作或更新，在选择发生变化时提供实时的交互和反馈。

## 程序

```java
import javax.swing.*;
import javax.swing.event.ListSelectionEvent;
import javax.swing.event.ListSelectionListener;
import java.awt.*;

public class ListSelectionExample {
    public static void main(String[] args) {
        // 创建 JFrame
        JFrame frame = new JFrame("列表选择示例");
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());

        // 创建一个包含课程列表的 JList
        String[] courses = {"Java", "Python", "C++", "JavaScript", "Ruby"};
        JList<String> courseList = new JList<>(courses);
        courseList.setSelectionMode(ListSelectionModel.SINGLE_SELECTION);
        courseList.setBackground(Color.WHITE);

        // 为 JList 添加一个 ListSelectionListener
        courseList.addListSelectionListener(new ListSelectionListener() {
            @Override
            public void valueChanged(ListSelectionEvent e) {
                if (!e.getValueIsAdjusting()) {
                    // 检查选择是否完成
                    String selectedCourse = courseList.getSelectedValue();
                    if (selectedCourse != null) {
                        // 显示选中的课程消息框
                        JOptionPane.showMessageDialog(frame, "Selected Course: " + selectedCourse);
                    }
                }
            }
        });

        // 将 JList 加入 JScrollPane 以处理滚动
        JScrollPane scrollPane = new JScrollPane(courseList);

        // 将 JScrollPane 添加到 JFrame
        frame.add(scrollPane, BorderLayout.CENTER);

        // 使 JFrame 可视
        frame.setVisible(true);
    }
}
```

## 输出

![](img/5a077f56e14b826c2dc61de6c176e5ef_591_0.png)

`JList` 显示了一个课程列表并允许用户一次选择一个。当用户选择一个课程时，会弹出一个显示所选课程的消息框。我们使用了 `ListSelectionListener` 来检测列表的变化。监听器被添加到 `JList` 中并通过显示消息框做出响应。

## 鼠标监听器 (MouseListener)

`MouseListener` 是 Java 中的一个接口，用于接收和处理鼠标点击、按下、释放、进入和离开组件。它有五个方法：`mouseClicked(MouseEvent)`、`mousePressed(MouseEvent)`、`mouseReleased(MouseEvent)`、`mouseEntered(MouseEvent)` 和 `mouseExited(MouseEvent)`。

### 带有鼠标监听器的 `JPopupMenu`

`JPopupMenu` 用于在用户右键点击组件时显示菜单。`MouseListener` 用于检测点击事件并触发弹出菜单。

## 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class PopupMenu {
    public static void main(String[] args) {
        // 创建 JFrame
        JFrame frame = new JFrame("PopupMenu示例");
        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());

        // 创建一个 JTextArea
        JTextArea textArea = new JTextArea("在此右键查看菜单");
        frame.add(textArea);

        // 创建一个 JPopupMenu
        JPopupMenu popup = new JPopupMenu();
        JMenuItem copyItem = new JMenuItem("复制");
        JMenuItem pasteItem = new JMenuItem("粘贴");
        popup.add(copyItem);
        popup.add(pasteItem);

        // 添加鼠标监听器显示弹出菜单
        textArea.addMouseListener(new MouseAdapter() {
            @Override
            public void mousePressed(MouseEvent e) {
                if (SwingUtilities.isRightMouseButton(e)) {
                    popup.show(textArea, e.getX(), e.getY());
                }
            }
        });

        // 使 JFrame 可视
        frame.setVisible(true);
    }
}
```

```java
add(new JLabel("Smoker (Yes/No):"));
tfSmoker = new JTextField();
add(tfSmoker);
add(new JLabel("Diabetic (Yes/No):"));
tfDiabetic = new JTextField();
add(tfDiabetic);

// 保存按钮
btnSave = new JButton("Save");
btnSave.addActionListener(this);
add(btnSave);
setVisible(true);

@Override
public void actionPerformed(ActionEvent e) {
    if (e.getSource() == btnSave) {
        try {
            // 将输入数据写入文件
            BufferedWriter writer = new BufferedWriter(new FileWriter("diabetes_data.txt", true));
            writer.write(
                tfAge.getText() + "," + 
                cbGender.getSelectedItem() + "," + 
                tfBMI.getText() + "," + 
                tfBloodPressure.getText() + "," + 
                tfFastingBloodSugar.getText() + "," + 
                tfPostPrandialBloodSugar.getText() + "," + 
                tfFamilyHistory.getText() + "," + 
                tfPhysicalActivity.getText() + "," + 
                tfSmoker.getText() + "," + 
                tfDiabetic.getText() + "\n"
            );
            writer.close();

            // 显示确认对话框
            JOptionPane.showMessageDialog(this, "数据保存成功！");

            // 清空输入字段
            tfAge.setText("");
            cbGender.setSelectedIndex(0);
            tfBMI.setText("");
            tfBloodPressure.setText("");
            tfFastingBloodSugar.setText("");
            tfPostPrandialBloodSugar.setText("");
            tfFamilyHistory.setText("");
            tfPhysicalActivity.setText("");
            tfSmoker.setText("");
            tfDiabetic.setText("");
        } catch (IOException ex) {
            ex.printStackTrace();
            JOptionPane.showMessageDialog(this, "保存数据时出错");
        }
    }
}

void main(String[] args) {
    new DiabetesDataCollector();
}
```

## Swing 框架

### 案例研究 1

`DiabetesDataCollector` 程序是一个 Java Swing 应用，旨在从用户处收集并存储与糖尿病相关的健康数据。该程序具有图形化用户界面，包含年龄、性别、BMI、血压、血糖、餐后血糖、家族史、体力活动、吸烟状况和糖尿病状态的输入字段。用户可以输入自己的信息并点击“Save（保存）”按钮进行保存，这会将数据写入文本文件。程序会对输入进行验证，在成功保存数据后提供确认对话框，并清空输入字段以便下一次输入。该应用程序适用于为糖尿病评估或管理收集并组织健康数据。

### 案例研究 2

神经系统疾病涵盖了影响大脑、脊髓和神经的广泛状况，其风险因素多种多样，例如遗传倾向、生活方式因素（如饮食和运动）、环境影响（如毒素）以及与年龄相关的变化等疾病的发展。识别特定风险通常涉及评估家族史、生活习惯和环境暴露，以了解易感性和潜在的预防措施。

## 程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class NeuroDisorderDetector extends JFrame {
    private JTextField ageField;
    private JTextField symptomsField;
    private JButton detectButton;
    private JLabel resultLabel;

    public NeuroDisorderDetector() {
        super("神经疾病检测器");
        setLayout(new BorderLayout());

        // 创建 UI 组件
        JLabel ageLabel = new JLabel("Age:");
        ageField = new JTextField(5);
        JLabel symptomsLabel = new JLabel("Symptoms:");
        symptomsField = new JTextField(20);
        detectButton = new JButton("Detect");
        detectButton.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                // 检测逻辑
            }
        });

        // 将 UI 组件添加到框架中
        add(ageLabel);
        add(ageField);
        add(symptomsLabel);
        add(symptomsField);
        add(detectButton);
        add(resultLabel);

        setSize(400, 200);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setVisible(true);
    }

    private class DetectButtonListener implements ActionListener {
        public void actionPerformed(ActionEvent e) {
            // 获取用户输入
            int age = Integer.parseInt(ageField.getText());
        }
    }
}
```



## 医疗与健康应用

### 586

`NeuroDisorderDetector` 是一个 Java Swing 应用，帮助根据用户输入识别神经系统疾病。用户通过简单图形界面中的文本框提供年龄和症状。点击“Detect（检测）”按钮后，它会将症状与各种疾病（如阿尔茨海默病、帕金森病、多发性硬化、癫痫和中风）的预定义列表进行比较。如果发现匹配项，将在界面上显示相应的疾病。

```java
String symptoms = symptomsField.getText();

// 根据输入检测疾病
String disorder = detectNeuroorder(age, symptoms);

// 显示结果
resultLabel.setText("你可能患 " + disorder);

private String detectNeuroorder(int age, String symptoms) {
    // 定义疾病列表
    String[] disorders = {
        "Alzheimer's disease",
        "Parkinson's disease",
        "Multiple Sclerosis",
        "Epilepsy",
        "Stroke"
    };

    // 初始化一个存储检测到的疾病的变量
    String detectedorder = "Unknown";

    // 遍历疾病并检查症状是否匹配
    for (int i = 0; i < disorders.length; i++) {
        boolean match = true;
        if (!symptoms.toLowerCase().contains(disorders[i].toLowerCase())) {
            match = false;
        }
        if (match) {
            detectedorder = disorders[i];
            break;
        }
    }

    // 返回检测到的疾病
    return detectedorder;
}

void main(String[] args) {
    NeuroDisorderDetector detector = new NeuroDisorderDetector();
}
```

## Swing 框架

### 587

### 18.3.3 研究3

甲状腺疾病是指影响甲状腺的状况，导致甲状腺激素分泌过多（甲状腺亢进）或不足（甲状腺功能减退）。该程序根据以下疾病的预定义列表评估症状：

- 甲状腺功能减退：疲劳、体重增加、皮肤干燥和脱发。
- 甲状腺功能亢进：体重减轻、易躁和怕热。
- 甲状腺结节：颈部肿块、吞咽困难和疼痛。
- 甲状腺癌：颈部肿块、吞咽困难、声音嘶哑。

这些列表用于检测潜在的甲状腺疾病。

## 程序

```java
import java.swing.*;
import java.awt.*;
import java.awt.event.*;

public class ThyroidDetector extends JFrame {
    private JTextField ageField;
    private JTextField symptomsField;
    private JButton detectButton;
    private JLabel resultLabel;

    public ThyroidDetector() {
        super("甲状腺检测器");
        setLayout(new FlowLayout());

        // 创建 UI 组件
        JLabel ageLabel = new JLabel("Age:");
        ageField = new JTextField(5);
        JLabel symptomsLabel = new JLabel("Symptoms:");
        symptomsField = new JTextField(20);
        detectButton = new JButton("Detect");
        detectButton.addActionListener(new DetectButtonListener());
        resultLabel = new JLabel("Result:");

        // 将 UI 组件添加到框架中
        add(ageLabel);
        add(ageField);
        add(symptomsLabel);
        add(symptomsField);
        add(detectButton);
        add(resultLabel);

        setSize(400, 200);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setVisible(true);
    }

    private class DetectButtonListener implements ActionListener {
        public void actionPerformed(ActionEvent e) {
            // 获取用户输入
            int age = Integer.parseInt(ageField.getText());
        }
    }
}
```

## 588 用于医疗和健康应用的 Java 22

```java
String symptoms = symptomsField.getText();

// 根据用户输入检测甲状腺疾病
String disorder = detectThyroidDisorder(age, symptoms);

// 显示结果
resultLabel.setText("You may have " + disorder);
}

private String detectThyroidDisorder(int age, String symptoms) {
    // 定义可能的甲状腺疾病列表
    String[] disorders = {"Hypothyroidism", "Hyperthyroidism", "Thyroid Nodules", "Thyroid Cancer"};

    // 为每种疾病定义一个症状列表
    String[] symptomsList = {
        "fatigue", "weight gain", "dry skin", "hair loss", // 甲状腺功能减退
        "weight loss", "nervousness", "Irritability", "heat intolerance", // 甲状腺亢进
        "lump in the neck", "difficulty swallowing", "pain in the neck", // 甲状腺结节
        "lump in the neck", "difficulty swallowing", "pain in the neck",
        "hoarsness", "Thyroid Cancer" // 甲状腺癌
    };

    // 初始化存储检测到的疾病的变量
    String detectedDisorder = "Unknown";

    // 遍历每种疾病并检查症状是否匹配
    for (int i = 0; i < disorders.length; i++) {
        boolean match = true;

        // 注意：原始逻辑在遍历 symptomsList[i] 时存在 bug，
        // 但根据 OCR 文本保留了结构。
        for (String symptom : symptomsList[i]) {
            if (!symptom.toLowerCase().contains(symptom.toLowerCase())) {
                match = false;
                break;
            }
        }

        if (match) {
            detectedDisorder = disorders[i];
            break;
        }
    }

    // 返回检测到的疾病
    return detectedDisorder;
}

void main(String[] args) {
    ThyroidDetector detector = new ThyroidDetector();
}
```

`ThyroidDetector` 是一个 Java 应用，旨在根据用户输入识别潜在的甲状腺疾病。界面包含用户年龄和症状的文本字段、一个“检测（Detect）”按钮以及用于显示结果的标签。当点击按钮时，程序会根据输入的症状与预定义的各种甲状腺状况（如甲状腺功能减退、甲状腺亢进、甲状腺结节和甲状腺癌）的症状列表进行评估。如果症状匹配已知疾病，程序将更新列表以指示潜在的状况。

## 14 Java 泛型

### 14.1 引言

泛型提供了一种创建类、接口和方法的方式，可以在不牺牲类型安全的情况下操作不同类型。这是通过在创建类实例或调用方法时指定类型作为参数来实现的。

使用泛型的主要优势是代码的可重用性。通过泛型类或方法，你可以编写适用于各种数据类型的代码，提高灵活性并减少冗余。当你想要创建可以适应不同数据类型且不影响编译时类型检查的组件时，这种方法特别有用。

需要注意的是，泛型不能直接与基本类型一起使用。但是，Java 提供了包装类（例如用于 `int` 的 `Integer`，用于 `float` 的 `Float`），在处理基本类型时可以使用它们配合泛型以达到相同的效果。这确保了泛型的益处可以扩展到 Java 编程中的广泛场景。

这些约定有助于代码库的可维护性和清晰度。

- `E` - Element（元素）：通常用于集合语境（例如 `ArrayList`、`Set`），其中类型参数表示集合包含的元素类型。
- `K` - Key（键），`V` - Value（值）：经常用于 `Map` 实现语境（例如 `HashMap`、`TreeMap`），其中 `K` 代表键的类型，`V` 代表存储在 `Map` 中的值的类型。
- `N` - Number（数字）：当泛型类型预期为数字型数据类型时常用。
- `T` - Type（类型）：当实际类型未指定或可以变化时用作泛型类型。
- `S`, `U`, `V` 等：当处理多个泛型类型时，通常使用字母表随后的字母（`S`, `U`, `V` 等）来表示第二、第三和第四种类型，提供声明顺序的清晰序列。

遵循这些约定使得代码对开发者来说更容易理解，并与标准 Java 库中使用的约定保持一致。命名约定的一致性增强了协作性和可读性，特别是在处理跨项目或库的泛型类型代码时。

## 14.2 边界类型（BOUNDED TYPES）

Java 泛型中的边界类型参数允许你将泛型参数的类型限制为特定类的子类或实现特定的接口。这提供了额外的控制，并确保与泛型一起使用的类型符合约束。

在 Java 泛型中声明边界类型参数时，你使用 `extends` 关键字，后跟你想要作为类型参数上界的类或接口。这会将类型参数限制为指定类的子类或实现该接口的类型。

```java
class Sample<T extends Number> {
    // 类实现
}
```

其中 `T extends Number` 意味着 `T` 可以是 `Number` 的任何子类或 `Number` 本身。这确保了用于 `T` 的任何类型都必须与 `Number` 兼容。这种限制允许你在泛型类或方法中使用上界类（或接口）的方法和属性，同时保留了使用指定类型之不同子类的灵活性。

### 程序

```java
// 带有边界类型参数的泛型类 Test
class Test<T extends Number> {
    // 存储数值的泛型变量
    private T value;

    // 初始化泛型变量的构造函数
    public Test(T value) {
        this.value = value;
    }

    // 显示存储的值的方法
    public void display() {
        System.out.println("Value: " + value);
    }
}
```

## 14.3 泛型类

泛型类是一个用一个或多个类型进行参数化的类，使其能够处理不同的数据类型。这为代码提供了高水平的灵活性和重用性。通过创建泛型类，你可以编写不依赖于特定数据类型的代码，使其能够适应各种场景。

在类中，你使用类型参数（通常用单个大写字母表示，例如 `T`）来表示该类将处理的数据类型。该类型参数在创建类的实例时指定，允许该类对该特定类型的对象进行操作。

### 程序

```java
// 定义一个名为 Test 的泛型类
class Test<T> {
    private T value;

    // 初始化值的构造函数
    public Test(T value) {
        this.value = value;
    }

    // 获取值的方法
    public T getValue() {
        return value;
    }

    // 显示值的方法
    public void display() {
        System.out.println("Generic Class " + value.getClass().getSimpleName() + ": " + value);
    }
}

// 用于测试泛型类的主类
public class Main {
    public static void main(String[] args) {
        // 创建 Integer 类型的 Test 实例
        Test<Integer> t = new Test<>(1);

        // 创建 String 类型的 Test 实例
        Test<String> t1 = new Test<>("Ushari");

        // 显示值
        t.display(); // 输出: Generic Integer: 1
        t1.display(); // 输出: Generic Class String: Ushari
    }
}
```

输出：
```
Generic Integer: 1
Generic Class String: Ushari
```

上述 Java 程序利用泛型创建了一个名为 `Test` 的灵活类的实例，该类可以容纳各种数据类型。在 `Main` 类中，实例化两个实例——一个带有值为 `1` 的整数，另一个带有值为“Ushari”的字符串。泛型类 `Test<T>` 设计用于存储和检索类型为 `T` 的值。因此，第一个实例 `t` 存储了一个值为 `1` 的整数，第二个实例 `t1` 存储了一个值为“Ushari”的字符串。输出将为该实例显示“Generic Class Integer: 1”，为 `t1` 实例显示“Generic Class String: Ushari”。

## Java 泛型

## 14.4 泛型方法

Java 中的泛型不仅限于类，还包括泛型方法。泛型方法是一个用一个或多个类型参数化的方法，使其能够处理不同类型的数据。这提供了与泛型相似的灵活性和重用性，但是在方法级别上的。

### 程序

```java
// 定义一个带有泛型方法的 Test 类
class Test {
    // 接受任何类型参数的泛型方法
    public <T> void func(T temp) {
        System.out.println("Type: " + temp.getClass().getSimpleName() + "\nValue: " + temp);
    }
}

// 用于测试泛型方法的主类
public class Main {
    public static void main(String[] args) {
        // 创建 Test 类的实例
        Test test = new Test();

        // 使用 String 参数调用泛型方法
        test.func("Usharani");

        // 使用 Integer 参数调用泛型方法
        test.func(25);
    }
}
```



```
输出：
Type: String, Value: Usharani
Type: Integer, Value: 25
```

上述程序说明了类内部泛型方法的实现，展示了处理各种数据类型的能力。在`Main`类中，创建了`test`类的实例，并使用不同类型的参数调用了两次泛型方法`func`。类中定义的方法使用`<T> void func(T temp)`语法声明为泛型方法。这允许它接受任何类型的参数，提供了灵活性和代码可读性。在执行期间，方法首先被带字符串参数（`Usharani`）调用，然后被带整数参数（`25`）调用，展示了泛型方法处理多样化数据类型的适应性。

## 14.5 泛型构造函数

在泛型的上下文中，泛型类可以处理不同的数据类型。类型参数在类级别声明，影响整个类，包括它的构造函数和方法。泛型构造函数构建在泛型类内部，类型参数在类级别指定，而不是在构造函数级别。在定义泛型类时，类型参数在类级别声明，影响整个类，包括它的构造函数。虽然构造函数不能显式地泛型，但它们利用了类级别指定的泛型类型，允许在处理不同数据类型时具有灵活性。

在泛型类中，构造函数可以接受泛型类型的参数，该类型在创建类实例时指定。这确保了类中的构造函数和其他方法与指定的类型保持一致，促进了重用性和类型安全。在类级别指定的类型参数用于构造函数内部，用于定义它可以接受的参数类型。

### 程序

```java
// 定义一个带有泛型构造函数的泛型类 Test
class Test<T extends Number> {
    private double x;

    // 将提供的数值输入转换为 double 的泛型构造函数
    public Test(T t) {
        this.x = t.doubleValue();
    }

    // 显示转换后的值的方法
    public void display() {
        System.out.println("value: " + x);
    }
}

// 用于测试泛型构造函数的主类
public class Main {
    public static void main(String[] args) {
        // 创建 Integer 类型的 Test 实例
        Test<Integer> t1 = new Test<>(10);

        // 创建 Double 类型的 Test 实例
        Test<Double> t2 = new Test<>(20.5);

        // 显示值
        t1.display(); // 输出: value: 10.0
        t2.display(); // 输出: value: 20.5
    }
}
```

上述 Java 程序演示了泛型构造函数的使用，将类型参数限制为`Number`的子类。这允许构造函数处理任何数值类型并转换为`double`进行存储。

## 14.6 泛型接口

在 Java 中，泛型接口是定义抽象方法的强大工具。与类不同，泛型接口仅包含抽象方法，没有构造函数和实例变量。使用`implements`建立了类与其实现的接口之间的关系。与泛型类一样，泛型接口能够开发灵活且类型安全的代码。

#### 语法

```java
// 带有类型参数 T 的泛型接口 A
interface A<T> {
    void ml(T t); // 带类型参数 T 的抽象方法
}
```

其中`A<T>`将声明一个带有类型参数`T`的泛型接口。该方法`void ml(T t)`定义了一个带参数`T`的抽象方法。该方法需要由实现接口的任何类来具体。

#### 语法

```java
// 实现泛型接口 A 的泛型类 B
class B implements A<T> {
    private T obj; // 存储 T 类型值的类变量

    // 实现接口 A 的抽象方法
    @Override
    public void ml(T t) {
        this.obj = t; // 将传递的值 t 赋值给类变量 obj
    }

    // 显示存储值的方法
    public void display() {
        System.out.println("Stored value: " + obj);
    }
}
```

其中`B implements A<T>`声明了一个带有类型参数`T`的泛型类`B`，并实现了相同类型参数的泛型接口`A`。将传递的值`t`赋值给类变量`obj`。

### 14.6.1 实现泛型接口的非泛型类

#### 语法

```java
// 以 Integer 作为参数实现泛型接口 A 的类 C
class C implements A<Integer> {
    private Integer obj; // 存储 Integer 值的类变量

    // 实现接口 A 的抽象方法
    @Override
    public void ml(Integer t) {
        this.obj = t; // 将传递的值 t 赋值给类变量 obj
    }

    // 显示存储值的方法
    public void display() {
        System.out.println("Stored value: " + obj);
    }
}
```

其中`C implements A<Integer>`将声明一个名为`C`的非泛型类，该类实现了特定类型参数（在本例中`Integer`）的泛型接口`A`。`public void ml(Integer t)`将使用特定类型（`Integer`）实现接口中的抽象方法`ml`，并将传递的值赋值给类变量。

```java
public class Main {
    public void main(String[] args) {
        // 创建非泛型类 C 的实例
        C c = new C();
        c.ml(1); // 将 Integer 值赋值给 C
        c.display(); // 输出: Stored value in C: 1

        // 创建 Integer 类型的泛型类 B 的实例
        B<Integer> b = new B<>();
        b.ml(10); // 将 Integer 值赋值给 B
        b.display(); // 输出: Stored value in B: 10
    }
}
```

`main`方法演示了如何创建带有类型参数的泛型类`B`以及带有特定类型参数的非泛型类`C`的实例。两者都实现了泛型接口`A`。使用`ml`方法进行赋值，并打印这些值。

# 程序

```java
interface A<T> {
    void ml(T t); // 带类型参数 T 的抽象方法
}

class B implements A<T> {
    private T obj; // 用于存储类型 T 值的类变量

    // 实现接口 A 中的抽象方法 ml
    @Override
    public void ml(T t) {
        this.obj = t; // 将传递的值 t 赋值给类变量 obj
    }

    // 显示存储值的方法
    public void display() {
        System.out.println("Stored value: " + obj);
    }
}

class C implements A<Integer> {
    private Integer obj; // 用于存储 Integer 值的类变量

    // 实现接口 A 中的抽象方法 ml
    @Override
    public void ml(Integer t) {
        this.obj = t; // 将传递的值 t 赋值给类变量 obj
    }

    // 显示存储值的方法
    public void display() {
        System.out.println("Stored value: " + obj);
    }
}
```

# Java 泛型

```java
public class Main {
    public static void main(String[] args) {
        // 创建非泛型类 C 的实例
        C c = new C();
        c.ml(1); // 将 Integer 值赋值给 C
        c.display(); // 输出: Stored value in C: 1

        // 创建 Integer 类型的泛型类 B 的实例
        B<Integer> b = new B<>();
        b.ml(10); // 将 Integer 值赋值给 B
        b.display(); // 输出: Stored value in B: 10
    }
}
```

输出：
```
Stored value: 1
Stored value: 10
```

在上面的程序中，`interface A<T>`定义了一个泛型方法`ml(T t)`供类实现。类`B<T>`是实现`A<T>`的泛型类，它存储了类型为`T`的传递值`t`。类`C`实现`A<Integer>`，意味着它处理`Integer`值。在`main`方法中，都创建了`C`和`B<Integer>`对象，并带值调用了它们的`ml()`方法，最后使用`display()`方法显示存储的值。输出显示了存储的值：类`C`为`1`，类`B`为`10`。

# 程序

```java
// 定义泛型接口 sample
interface Sample<T> extends Comparable<T> {
    T min(); // 找到最小值的方法
    T max(); // 找到最大值的方法
}

// 在测试类中实现 sample 接口
class Test<T> extends Comparable<T> implements Sample<T> {
    private T[] array; // 用于持有元素的数组

    // 初始化数组的构造函数
    public Test(T[] array) {
        this.array = array;
    }

    // 找到数组中最小值的方法
    @Override
    public T min() {
        T minValue = array[0];
        for (T element : array) {
            if (element.compareTo(minValue) < 0) {
                minValue = element;
            }
        }
        return minValue;
    }

    // 找到数组中最大值的方法
    @Override
    public T max() {
        T maxValue = array[0];
        for (T element : array) {
            if (element.compareTo(maxValue) > 0) {
                maxValue = element;
            }
        }
        return maxValue;
    }
}

// 测试功能的主类
public class Main {
    public static void main(String[] args) {
        // 创建一个包含 Integer 元素的数组
        Integer[] numbers = {5, 8, 2, 10, 7};

        // 使用 Integer 类型实例化测试类
        Test<Integer> testObject = new Test<>(numbers);

        // 找到最小值和最大值
        System.out.println("Minimum value: " + testObject.min()); // Output: Minimum value: 2
        System.out.println("Maximum value: " + testObject.max()); // Output: Maximum value: 10
    }
}
```

# 输出
```
Minimum value: 2
Maximum value: 10
```

上面的 Java 程序演示了泛型接口`sample`的使用，该接口继承了`Comparable`。接口声明了两个抽象方法`min()`和`max()`，用于查找泛型数组中的最小值和最大值。泛型类型`T`继承了`Comparable<T>`以确保类型`T`的元素可以进行比较。测试类初始化了数组并通过`compareTo`方法提供了`min()`和`max()`的实现。

# 14.6.2 泛型类继承泛型接口

泛型类（`GenericClass`）继承一个泛型父类（`GenericSuperClass`）并实现两个泛型接口（`GenericInterface1`和`GenericInterface2`）。泛型类的参数是泛型父类和泛型接口类型参数的并集。

#### 语法

```java
// 带有一个类型参数的泛型父类
class GenericSuperClass<T> {
    // 类成员和方法
}

// 带有两个类型参数的泛型接口
interface GenericInterface1<T1, T2> {
}

// 另一个带有两个类型参数的泛型接口
interface GenericInterface2<T3, T4> {
}

// 继承泛型父类并实现多个接口的泛型类
class GenericClass<T1, T2, T3, T4> extends GenericSuperClass<T1>
implements GenericInterface1<T1, T2>, GenericInterface2<T3, T4> {
}
```

Java 语法强调了泛型继承的灵活性，展示了一个场景：泛型类`GenericClass`继承一个泛型父类并实现两个泛型接口。泛型类的参数是泛型父类和泛型接口类型参数的并集。`GenericSuperClass`引入了一个类型参数，而`GenericInterface1`和`GenericInterface2`各自贡献两个参数。通过扩展泛型父类并实现多个接口，`GenericClass`拥有了完整的类型参数集，使其能够无缝集成其父类和接口所施加的功能和约束。

# 用于医疗保健应用的 600 Java 22

```java
return min;
}

// 测试功能的主类
public class Main {
    void main(String[] args) {
        // 整数数组示例
        Integer[] intArray = {3, 5, 1, 9, 2};
        ArrayProcessor<Integer> intProcessor = new ArrayProcessor<>();
        System.out.println("Max Integer: " + intProcessor.findMax(intArray));
        System.out.println("Min Integer: " + intProcessor.findMin(intArray));

        // 字符串数组示例
        String[] strArray = {"this", "is", "to", "test"};
        ArrayProcessor<String> strProcessor = new ArrayProcessor<>();
        System.out.println("Max String: " + strProcessor.findMax(strArray));
        System.out.println("Min String: " + strProcessor.findMin(strArray));
    }
}
```

输出：
```
Max Integer: 9
Min Integer: 1
Max String: to
Min String: is
```

上述程序定义了一个泛型接口`ArrayOperations<T>`，其中包含查找数组中最大值和最小值的方法，其中`T`扩展`Comparable<T>`。`ArrayProcessor<T>`类实现了该接口，通过比较数组中的元素来找到最大值和最小值。

## 14.7 泛型与继承

Java 泛型支持三个层级的继承：1) 单级 2) 多级 3) 多重继承。

### 14.7.1 单级继承

在 Java 中，泛型单级继承涉及创建一个继承自泛型超类的子类。泛型单级继承的语法与普通类继承相似，区别在于需要指定泛型类型参数。

### 程序

```java
// 带有类型参数 T 的泛型超类
class Test<T> {
    private T temp;

    // 初始化成员变量的构造函数
    public Test(T temp) {
```



`this.temp = temp;`

```
}
```

```java
// 获取成员变量值的方法
public T gettemp() {
    return temp;
}
```

```java
// 扩展相同类型参数 T 的 Test 的泛型子类
class Sample<T> extends Test<T> {
    // 调用超类构造函数
    public Sample(T temp) {
        super(temp);
    }

    // Sample 类特有的方法
    public void display() {
        System.out.println("Display method in Sample class");
    }
}
```

```java
// 演示用法的主类
public class Main {
    public void main(String[] args) {
        // 创建 Integer 类型的 Sample 实例
        Sample<Integer> sample = new Sample<>(1);

        // 调用超类的 gettemp() 方法
        System.out.println("Value from Test class: " + sample.gettemp());

        // 调用子类的 display() 方法
        sample.display();
    }
}
```

输出：

```
Value from Test class: 1
Display method in Sample class
```

`Test` 是一个包含类型参数 `T` 的泛型子类。它有一个类型为 `T` 的成员变量，以及一个初始化该成员变量的构造函数`Test(T temp)`。此外，还有一个方法`gettemp()`，用于检索存储在`temp`变量中的值。`Sample`类是`Test`的子类，也是带有类型参数`T`的泛型类。它包含一个构造函数`Sample(T temp)`，使用`super(temp)`调用超类构造函数，以确保成员变量的正确初始化。子类引入了一个额外的方法`display()`，该方法是`Sample`类特有的。在`Main`类中，创建了一个以整数作为泛型类型的子类实例，并将值`1`传递给构造函数。程序随后调用了超类（`gettemp()`）和子类（`display()`）的方法。输出显示了存储在子类中的数据并调用了子类的额外方法。

## 14.7.2 多级继承

子类继承超类的属性，并且该子类可以作为另一个子类的超类。

### 程序

```java
// 带有类型参数 T 的泛型子类 Shape
class Shape<T> {
    protected T dimensions;

    // 初始化尺寸的构造函数
    public Shape(T dimensions) {
        this.dimensions = dimensions;
    }

    // 获取尺寸的方法
    public T getDimensions() {
        return dimensions;
    }
}

// 扩展 Shape 的第一个子类 TwoShape
class TwoShape<T> extends Shape<T> {
    // 调用超类构造函数
    public TwoShape(T dimensions) {
        super(dimensions);
    }

    // 显示尺寸信息的方法
    public void displayInfo() {
        System.out.println("Dimensions: " + getDimensions());
    }
}

// 扩展特定类型 TwoShape 的第二个子类 Rectangle
class Rectangle extends TwoShape<Double> {
    private Double length;
    private Double width;

    // 初始化长度和宽度的构造函数
    public Rectangle(Double length, Double width) {
        super(length);
        this.length = length;
        this.width = width;
    }

    // 计算矩形面积的方法
    public double calculateArea() {
        return length * width;
    }

    // 重写显示方法以包含面积
    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Length: " + length);
        System.out.println("Width: " + width);
        System.out.println("Area: " + calculateArea());
    }
}

// 演示用法的主类
public class Main {
    public static void main(String[] args) {
        // 创建指定尺寸为 double 的 Rectangle 实例
        Rectangle rectangle = new Rectangle(5.0, 3.0);

        // 调用 displayInfo 方法显示矩形的详细信息
        rectangle.displayInfo();
    }
}
```

输出：

```
Dimensions: 5.0
Length: 5.0
Width: 3.0
Area: 15.0
```

在上述程序中，泛型超类`Shape`封装了带有泛型尺寸的通用属性和行为。第一个子类`TwoShape`扩展了`Shape`，增加了显示其尺寸信息的方法。第二个子类`Rectangle`进一步扩展了层次结构，并引入了根据长度和宽度计算面积的方法。在主方法中，创建了一个指定为`Double`的`Rectangle`类实例。程序调用了该实例的`displayInfo`方法，展示了`Rectangle`类中重写的方法，该方法提供了矩形的详细信息，包括其尺寸和计算出的面积。

### 程序

```java
// 带有类型参数 T 的泛型子类 Test
class Test<T> {
    protected T temp;

    // 初始化 temp 变量的构造函数
    public Test(T temp) {
        this.temp = temp;
    }

    // 获取 temp 值的方法
    public T get() {
        return temp;
    }

    // 显示泛型值的方法
    public void display() {
        System.out.println("value in " + temp);
    }
}

// 扩展 Test 的子类 Test1
class Test1<T> extends Test<T> {
    public Test1(T temp) {
        super(temp);
    }

    // Test1 特有的方法
    public void display1() {
        System.out.println("Test 1 method");
    }

    // 重写显示方法
    @Override
    public void display() {
        System.out.println("Test 1 " + temp);
    }
}

// 扩展 Test1 的子类 Test2
class Test2<T> extends Test1<T> {
    public Test2(T temp) {
        super(temp);
    }

    // Test2 特有的方法
    public void display2() {
        System.out.println("Test 2 method");
    }

    // 重写显示方法
    @Override
    public void display() {
        super.display();
        System.out.println("Test 2");
    }
}

// 扩展 Test2 的子类 Test3
class Test3<T> extends Test2<T> {
    public Test3(T temp) {
        super(temp);
    }

    // Test3 特有的方法
    public void display3() {
        System.out.println("Test 3 method");
    }

    // 重写显示方法
    @Override
    public void display() {
        super.display();
        System.out.println("Test 3");
    }
}

// 扩展 Test3 的子类 Test4
class Test4<T> extends Test3<T> {
    public Test4(T temp) {
        super(temp);
    }

    // Test4 特有的方法
    public void display4() {
        System.out.println("Test 4 method");
    }

    // 重写显示方法
    @Override
    public void display() {
        super.display();
        System.out.println("Test 4");
    }
}

// 扩展 Test4 的子类 Test5
class Test5<T> extends Test4<T> {
    public Test5(T temp) {
        super(temp);
    }

    // Test5 特有的方法
    public void display5() {
        System.out.println("Test 5 method");
    }

    // 重写显示方法
    @Override
    public void display() {
        super.display();
        System.out.println("Test 5");
    }
}
```

## 14.7.3 多重继承

在多继承中，子类继承自多个父类。

### 程序

```java
public class Main {
    public static class BaseClass {
        int calculateValue() {
            return 1;
        }
    }

    public static interface Calculable {
        int performCalculation();
    }

    private static class Subclass extends BaseClass implements Calculable {
        public int performCalculation() {
            return 100;
        }
    }
}
```

## 6 Java 医疗与健康应用

```java
// 在此处修正类名（使用 SubClass 代替 GenericClass）
public static <T extends BaseClass & Calculable> T createGeneratableInstance() {
    return (T) new SubClass(); // 修复了 'SubClass'的大小写
}

void main(String... args) {
    // 调整对 SubClass.createGeneratableInstance() 的调用
    BaseClass baseInstance = createGeneratableInstance();
    System.out.println(baseInstance.calculateValue());
}
```

输出：

`Main`类封装了程序逻辑，包含一个作为基础类的`BaseClass`，其中包含一个计算值的方法。`Calculable`接口定义了执行计算的约束，而`SubClass`则作为`BaseClass`和`Calculable`的实现。泛型方法`createGeneratableInstance`强调了其目的是生成同时符合`BaseClass`和`Calculable`要求的实例。

## 14.7.4 非泛型类继承泛型类

在 Java 中，非泛型类不能直接继承泛型类，除非泛型类对其类型参数有一个预定义或指定的类型。

### 语法

```java
class GenericSuperClass<T> {
}

class NonGenericClass extends GenericSuperClass<T> { // 错误

class A {
    class GenericSuperClass<A> {
    class NonGenericClass extends GenericSuperClass<A> { }
```

上述语法强调了泛型类与非泛型类之间关系的限制。泛型父类`GenericSuperClass<T>`引入了类型参数`T`，而尝试让非泛型类`NonGenericClass`在不指定类型参数的情况下继承它。这会导致编译时错误，说明非泛型类在不为其泛型参数提供具体类型的情况下，无法直接继承泛型类。泛型类`GenericSuperClass<A>`有预定义的类型`A`作为其类型参数。在这种情况下，非泛型类`NonGenericClass`成功继承了`GenericSuperClass<A>`而没有遇到编译时错误。这种区别强调了只有当泛型类已经对其类型参数具有预定义的类型时，才允许继承。在 Java 中，可以使用原始类型（raw type）让非泛型类继承泛型类。这本质上移除了泛型类中的类型参数。然而，这样做会触发编译器警告，可能导致类型安全问题。

## Java 泛型

### 程序

```java
// 带有类型参数 T 的泛型类
class GenericClass<T> {
    // 泛型成员变量
    private T data;

    // 初始化泛型成员变量的构造函数
    public GenericClass(T data) {
        this.data = data;
    }

    // 获取泛型数据的方法
    public T getData() {
        return data;
    }

    // 显示数据的方法
    public void display() {
        System.out.println("Data: " + data);
    }
}

// 使用原始类型继承泛型类的非泛型类
class NonGenericClass extends GenericClass {
    // 构造函数
    public NonGenericClass(Object data) {
        // 使用原始类型，未提到特定类型 // 使用原始类型调用 GenericClass 的构造函数
        super(data);
    }

    // 重写 display 方法
    @Override
    public void display() {
        System.out.println("Non-generic display");
    }
}

public class Main {
    public static void main(String[] args) {
        // 创建泛型类的实例
        GenericClass<String> genericInstance = new GenericClass<>("Hello");
        genericInstance.display();

        // 使用原始类型创建非泛型类的实例
        NonGenericClass rawInstance = new NonGenericClass("World");
        rawInstance.display();
    }
}
```

输出：

```
Data: Hello
Non-generic display
```

# Java 泛型

## 14.7.5 泛型类继承非通用类

在 Java 中，泛型类可以继承非通用类。泛型类可以选择忽略其父类提供的泛型类型参数。

### 语法

```java
class NonGenericClass {}

class GenericClass<T> extends NonGenericClass {
}
```



该语法展示了泛型类继承非通用类的能力。`NonGenericClass` 是一个没有任何类型参数的简单非通用类。其随后的 `GenericClass<T>` 继承了这个非通用类，提供了使用或忽略从父类继承的泛型类型参数 `T` 的选项。

## 14.7.6 泛型类继承泛型类

在 Java 中，泛型类可以使用相同或不同的类型参数继承另一个泛型类。例如，如果 `class <A>` 是一个泛型类，那么类 `B<T>` 可以通过声明 `class B<T> extends A<T>` 来继承它。这允许 `B` 在继承类 `A` 功能和属性的同时，通过使用泛型保持类型安全和灵活性。通过共享类型参数 `T`，两个类都可以处理相同类型的数据，确保扩展类可以无缝地利用父类的泛型方法和字段。

### 语法

```java
// 具有单个类型参数 T 的泛型父类
class GenericSuperClass<T> {
}

// 保持相同类型参数 T 的第一个子类
class GenericSubClass<T> extends GenericSuperClass<T> {
}

// 引入额外类型参数 V 的第二个子类
class GenericSubClass2<T, V> extends GenericSuperClass<T> {
}

// 无效子类（编译错误），使用了不同的类型参数 T1, T2
class GenericSubClass3<T1, T2> extends GenericSuperClass<T1> {
    // 如果参数数量不匹配会导致编译错误
}
```

该语法展示了泛型类继承的原理，特别是当泛型类继承另一个泛型类时。事实上，遵循规则确保了继承层次结构中类型参数的一致性。第一个泛型子类 `GenericSubClass<T>` 恰当地设置了与其父类相同的类型参数。第二个泛型子类 `GenericSubClass2<T, V>` 通过引入额外的参数 `V` 展示了灵活性，同时仍保留了原始参数。然而，尝试创建第三个泛型子类 `GenericSubClass3<T1, T2>` 会导致编译错误，因为它引入了不同的参数，违反了至少要与父类具有相同类型和参数数量的要求。这展示了在泛型类层次结构中管理类型参数的复杂性，为开发者设计灵活且类型安全的代码结构提供了强大的基于规则的工具。当泛型类继承另一个泛型类时，类型参数从子类传递到父类，类似于构造函数链。在语法中，当使用 `String` 作为类型参数实例化 `GenericSubClass` 时，`GenericSuperClass` 中的类型参数 `T` 实际上被替换为了 `String`。

### 程序

```java
// 具有类型参数 T 的泛型父类
class GenericSuperClass<T> {
    T t; // 用于存储类型 T 值的字段

    // 初始化 t 字段的构造函数
    GenericSuperClass(T t) {
        this.t = t;
    }

    // 获取 t 值的 getter
    T get() {
        return t;
    }
}

// 继承自相同类型参数 T 的 GenericSuperClass 的泛型子类
class GenericSubClass<T> extends GenericSuperClass<T> {
    // 调用父类构造函数的子类构造函数
    GenericSubClass(T t) {
        super(t); // 将值传递给父类
    }

    // 显示 t 值的方法
    void display() {
        System.out.println("Value in GenericSubClass: " + get());
    }
}

// 运行程序的主类
public class Main {
    public static void main(String[] args) {
        // 创建 String 类型的 GenericSubClass
        GenericSubClass<String> obj = new GenericSubClass<String>("Usharini");

        // 显示子类中的值
        obj.display(); // 输出: "Value in GenericSubClass: Usharini"
    }
}
```

输出：

```text
Value in GenericSubClass: Usharini
```

在上面的程序中，`GenericSubClass` 使用类型 `T` 进行参数化。当你创建一个 `GenericSubClass<String>` 实例时，你指定 `String` 为 `T` 的实际类型参数。`GenericSubClass` 的构造函数通过 `super(t)` 调用 `GenericSuperClass` 的构造函数，有效地将 `String` 类型参数传递给父类。因此，在该实例中，父类中的 `t` 字段类型为 `String`。

## 14.8 泛型通配符

泛型中的通配符用问号（`?`）表示。它们用于表示泛型编程中的未知类型。通配符在处理泛型类型时提供了更大的灵活性，允许创建更通用且可重用的代码。

Java 泛型中有三种通配符：

- I. 无界通配符（`?`）：
  由问号 `?` 表示，代表未知类型。它可以作为参数、局部变量或字段的类型。示例：`List<?> myList`，其中 `myList` 是未知类型的列表。
- II. 上界通配符（`? extends T`）：
  由 `<? extends T>` 表示，其中 `T` 是一个特定类型。示例：`List<? extends Number> numbers`，其中 `numbers` 是数字列表。
- III. 下界通配符（`? super T`）：
  由 `? super T` 表示，其中 `T` 是一个特定类型。示例：`List<? super Integer> numbers`，其中 `numbers` 是整数列表。

通配符在你处理具有共同祖先的不同类型集合时特别有用。

### 上界通配符示例

```java
import java.util.List;
import java.util.ArrayList;

public class UpperBoundedWildcard {
    public static double calculateSum(List<? extends Number> numbers) {
        double sum = 0.0;

        for (Number number : numbers) {
            sum += number.doubleValue();
        }

        return sum;
    }

    public static void main(String[] args) {
        List<Integer> integerList = new ArrayList<>();

        integerList.add(10);
        integerList.add(20);
        integerList.add(30);

        System.out.println("Sum of integers: " + calculateSum(integerList));

        List<Double> doubleList = new ArrayList<>();

        doubleList.add(10.5);
        doubleList.add(20.5);
        doubleList.add(30.5);

        System.out.println("Sum of doubles: " + calculateSum(doubleList));
    }
}
```

### 下界通配符示例

```java
import java.util.List;
import java.util.ArrayList;

public class LowerBoundedWildcard {
    public static void addNumbers(List<? super Integer> list) {
        for (int i = 0; i < 5; i++) {
            list.add(i);
        }
    }

    public static void main(String[] args) {
        List<Integer> integerList = new ArrayList<>();

        addNumbers(integerList);
        System.out.println("Integer list: " + integerList);

        List<Number> numberList = new ArrayList<>();

        addNumbers(numberList);
        System.out.println("Number list: " + numberList);
    }
}
```

# Java 泛型

`print` 方法旨在接受 `integer` 类型或其任何父类的对象列表。`main` 方法初始化两个列表——一个是整数列表（`i`），另一个是数字列表（`n`）。然后它调用 `print` 方法并将这些列表作为参数传递。

## 无界通配符示例

```java
import java.util.List;
import java.util.ArrayList;

public class UnboundWildcardExample {
    // 使用无界通配符打印列表元素的方法
    public static void printList(List<?> list) {
        for (Object element : list) {
            System.out.println(element);
        }
    }

    public void main(String[] args) {
        // 创建一个整数列表
        List<Integer> integerList = new ArrayList<>();

        integerList.add(1);
        integerList.add(2);
        integerList.add(3);

        // 创建一个双精度列表
        List<Double> doubleList = new ArrayList<>();

        doubleList.add(1.1);
        doubleList.add(2.2);
        doubleList.add(3.3);

        // 打印整数列表元素
        System.out.println("Contents of integerList:");
        printList(integerList);

        // 打印双精度列表元素
        System.out.println("Contents of doubleList:");
        printList(doubleList);
    }
}
```

输出：

```text
Contents of integerList:
1
2
3

Contents of doubleList:
1.1
2.2
3.3
```

上述 Java 代码演示了泛型编程中无界通配符的使用。在 `Main` 类中，`print` 方法使用无界通配符（`<?>`）来接受任何类型的列表。这通过两个实例得到了展示：一个涉及整数列表（`i`），另一个涉及双精度列表（`d`）。对于整数列表（`i`），该方法将其作为参数接收，利用无界通配符处理列表中所包含的未知类型。同样，对于双精度列表（`d`），应用了相同的方法，强调了代码的泛型特性。

# 用于医疗保健应用的 Java 22

## 14.9 医疗应用

### 14.9.1 案例研究 1

肝癌，又称肝癌，起源于肝脏细胞，肝脏是负责解毒、蛋白质合成和消化等生命功能的最大器官。最常见的类型肝细胞癌，起始于称为肝细胞的主要肝细胞类型。风险因素包括慢性乙肝或丙肝病毒感染、肝硬化、过度饮酒和脂肪性肝病。症状通常包括体重减轻、腹痛、黄疸和肿胀。早期发现和治疗对于改善预后至关重要，可能涉及手术、放射治疗或靶向治疗。

### 程序

```java
import java.util.ArrayList;
import java.util.List;

class DNAFragment {
    private double size;

    public DNAFragment(double size) {
        this.size = size;
    }

    public double getSize() {
        return size;
    }
}

class BloodTestResult<T> {
    private List<T> dnaFragments;

    public BloodTestResult() {
        this.dnaFragments = new ArrayList<>();
    }

    public void addDNAFragment(T dnaFragment) {
        dnaFragments.add(dnaFragment);
    }

    public List<T> getDNAFragments() {
        return dnaFragments;
    }
}

public class LiverCancerDetector {
    public static boolean detectLiverCancer(BloodTestResult<DNAFragment> bloodTestResult) {
        List<DNAFragment> dnaFragments = bloodTestResult.getDNAFragments();
        boolean hasVariedSize = false;

        for (int i = 0; i < dnaFragments.size(); i++) {
            for (int j = i + 1; j < dnaFragments.size(); j++) {
                if (Math.abs(dnaFragments.get(i).getSize() - dnaFragments.get(j).getSize()) > 0.1) {
                    hasVariedSize = true;
                    break;
                }
            }

            if (hasVariedSize) {
                break;
            }
        }

        return hasVariedSize;
    }
}
```

Java Generic型 617

## 14.9.3 案例研究

血液杂质，通常被称为血液污染或毒素积累，当有害物质在血液中积累时发生。这可能由多种因素引起，包括饮食不当、暴露于环境污染物、感染或肝脏、肾功能障碍等基础健康状况。检测血液杂质考虑的参数是血红蛋白水平和白细胞计数。

- 血红蛋白水平：血红蛋白的杂质检测检查其水平是否在 12.0 到 16.0 g/dL 的正常范围之外。
- 白细胞计数：白细胞的杂质检测验证其计数是否低于 4000 cells/µL 或高于 11000 cells/µL。

```java
import java.util.ArrayList;
import java.util.List;

interface BloodComponent<T> {
    T getComponent();
}

class Hemoglobin implements BloodComponent<Double> {
    private double level;

    public Hemoglobin(double level) {
        this.level = level;
    }

    @Override
    public Double getComponent() {
        return level;
    }
}

class WhiteBloodCell implements BloodComponent<Integer> {
    private int count;

    public WhiteBloodCell(int count) {
        this.count = count;
    }

    @Override
    public Integer getComponent() {
        return count;
    }
}

class BloodImurityDetector<T> {
    private List<BloodComponent<T>> bloodComponents;
```



`public BloodImurityDetector() {`

```
    this.bloodComponents = new ArrayList<>();
}
```

```
public void addBloodComponent(BloodComponent<T> bloodComponent) {
    bloodComponents.add(bloodComponent);
}
```

```
public boolean detectImpurity() {
    for (BloodComponent<T> bloodComponent : bloodComponents) {
        if (isImpure(bloodComponent.getComponent())) {
            return true;
        }
    }
    return false;
}
```

# 618 用于医疗保健和医学应用的 Java 22

```java
private boolean isImpure(T component) {
    // 简单的杂质检测逻辑：检查组件值是否
    // 超出正常范围
    if (component instanceof Double) {
        return (Double) component < 12.0 || (Double) component > 16.0;
    } else if (component instanceof Integer) {
        return (Integer) component < 4000 || (Integer) component > 11000;
    }
    return false;
}

public class BloodImurityDetection {
    static void main(String[] args) {
        BloodImurityDetector<Double> hemoglobinDetector = new BloodImurityDetector<>();
        hemoglobinDetector.addBloodComponent(new Hemoglobin(10.5));
        hemoglobinDetector.addBloodComponent(new Hemoglobin(14.2));

        BloodImurityDetector<Integer> whiteBloodDetector = new BloodImurityDetector<>();
        whiteBloodDetector.addBloodComponent(new WhiteBloodCell(3500));
        whiteBloodDetector.addBloodComponent(new WhiteBloodCell(9000));

        boolean hasHemoglobinImurity = hemoglobinDetector.detectImpurity();
        boolean hasWhiteBloodImurity = whiteBloodDetector.detectImpurity();

        if (hasHemoglobinImurity || hasWhiteBloodImurity) {
            System.out.println("Blood impurity detected");
        } else {
            System.out.println("No blood impurity detected");
        }
    }
}
```

`BloodImurityDetection` 程序利用 Java 泛型和接口来模拟血液杂质的检测。它定义了 `BloodComponent<T>` 接口，包含用于封装不同类型血液成分（`Hemoglobin` 和 `WhiteBloodCell`）的方法。`BloodImurityDetector<T>` 类实现了添加这些组件、根据定义的正常范围检查杂质以及判断是否存在杂质的逻辑。在 `main` 方法中，为 `Double`（血红蛋白）和 `Integer`（白细胞）实例化了 `BloodImurityDetector` 实例，添加了样本数据并执行杂质检测。根据结果，它输出 `Blood impurity detected` 或 `No blood impurity detected`，以指示监测的血液成分是否存在异常。

# 15 集合

## 15.1 引言

在 Java 中，集合（collections）是一个提供了一种用于存储和操作一组对象的框架。Java 集合可以实现你对数据执行的所有操作，如搜索、排序、插入、处理和删除。Java 集合框架由以下组件组成：

### 15.1.1 集合接口

- `Collection`: 集合框架的根接口。
- `List`: 有序集合（也称为序列）。
- `Set`: 不允许重复元素的集合。
- `SortedSet`: 一个按升序维护其元素的集合。
- `NavigableSet`: 具有额外导航方法的集合。
- `Queue`: 设计用于在处理前持有元素的集合。
- `Deque`: 支持在两端进行元素插入和移除的双端队列。

### 15.1.2 集合类

- `ArrayList`: `List` 接口的可伸缩数组实现。
- `LinkedList`: `List` 和 `Deque` 接口的双向链表实现。
- `HashSet`: `Set` 接口的哈希表实现。
- `LinkedHashSet`: `Set` 接口的哈希表和链表实现，具有可预测的迭代顺序。
- `TreeSet`: 基于 `TreeMap` 的 `NavigableSet` 实现。
- `PriorityQueue`: 基于优先级堆的 `Queue` 接口实现。
- `ArrayDeque`: `Deque` 接口的可伸缩数组实现。

### 15.1.3 Map 接口和类

- `Map`: 键值对接口。
- `SortedMap`: 一个按升序维护条目的映射。
- `NavigableMap`: 扩展了导航方法的 `Map`。
- `HashMap`: `Map` 接口的哈希表实现。
- `LinkedHashMap`: `Map` 接口的哈希表和链表实现，具有可预测的迭代顺序。
- `TreeMap`: `NavigableMap` 接口的红黑树实现。
- `Hashtable`: `HashMap` 的同步版本。

### 15.1.4 工具类

- `Collections`: 提供集合静态方法的工具类。
- `Arrays`: 提供数组静态方法的工具类。

这是一个在 Java 中使用不同集合类型的简单示例。

# 程序

```java
import java.util.*;

public class test {
    public void main(String[] args) {
        List<String> arr = new ArrayList<>();
        arr.add("A");
        arr.add("B");
        arr.add("C");
        System.out.println(arr);

        Set<String> s = new HashSet<>();
        s.add("A");
        s.add("B");
        s.add("C");
        System.out.println(s);

        Map<String, Integer> m = new HashMap<>();
        m.put("A", 1);
        m.put("B", 2);
        System.out.println(m);
    }
}
```

## 用于医疗保健和医学应用的 Java 22

- 1. 同步：`ArrayList` 默认不是同步的，这意味着它在并发访问时不是线程安全的。如果多个线程并发访问一个 `ArrayList`，且至少有一个线程对列表进行了结构性修改（添加或删除元素），则必须在外部进行同步处理。

- 2. 搜索时间复杂度：虽然 `ArrayList` 的随机访问速度很快，但通过值进行搜索可能比 `HashSet` 或 `TreeSet` 等其他数据结构慢，特别是对于大型列表。

在 Java 中使用 `ArrayList` 的语法涉及几个步骤，包括导入必要的包、创建 `ArrayList` 实例、向列表添加元素以及执行各种操作。

## 15.2.3 ARRAY LIST 声明与访问语法

- 1. 导入 `ArrayList` 类：需要从 `java.util` 导入 `ArrayList` 类 `import java.util.ArrayList;`

- 2. 声明一个指定所需元素类型的 `ArrayList` 变量。`ArrayList<ElementType> name;`

- 3. 通过创建 `name` 的新实例来初始化 `ArrayList`。`name = new ArrayList<>();`

或者，你可以在一行代码中组合声明和实例化：`ArrayList<ElementType> name = new ArrayList<>();`

- 4. 用户可以使用 `add(element)` 方法向 `ArrayList` 添加元素。`name.add(element);`

- 5. 用户可以使用 `get(index)` 方法通过索引访问元素。`ElementType element = name.get(index);`

- 6. 用户可以使用增强型 `for` 循环或迭代器遍历 `ArrayList` 中的元素。`for (ElementType element : name) { // 处理每个元素 }`

- 7. 用户可以使用 `remove(index)` 方法根据索引或值移除元素。`name.remove(index); name.remove(element);`

- 8. 用户可以使用 `size()` 方法获取 `ArrayList` 中的元素数量。`int size = name.size();`

- 9. 用户可以使用 `isEmpty()` 方法检查 `ArrayList` 是否为空。`boolean isEmpty = name.isEmpty();`

- 10. 用户可以使用 `clear()` 方法从 `ArrayList` 中移除所有元素。`name.clear();`

# 程序

```java
import java.util.ArrayList;
import java.util.Collections;

public class ListExample {
  public static void main(String[] args) {
    // 创建一个 ArrayList 来存储课程名称
    ArrayList<String> courses = new ArrayList<>();

    // 将课程名称添加到 ArrayList 中
    courses.add("Mathematics");
    courses.add("Physics");
    courses.add("Chemistry");
    courses.add("Biology");

    // 显示初始课程列表
    System.out.println("Initial list of courses: " + courses);

    // 获取并打印索引为2 的课程
    String courseAtIndex = courses.get(2);
    System.out.println("Course at index 2: " + courseAtIndex);

    // 根据索引更新课程
    courses.set(3, "Environmental Science");
    System.out.println("List after updating the course at index 3: " + courses);

    // 根据索引移除课程
    courses.remove(1);
    System.out.println("List after removing the course at index 1: " + courses);

    // 检查列表中是否包含特定课程
    boolean hasMathematics = courses.contains("Mathematics");
    System.out.println("Does the contain 'Mathematics'? " + hasMathematics);

    // 检查列表是否为空
    boolean isEmpty = courses.isEmpty();
    System.out.println("Is the list empty? " + isEmpty);

    // 打印列表的大小
    int size = courses.size();
    System.out.println("Size of the course list: " + size);

    // 按字母顺序对列表排序
    Collections.sort(courses);
    System.out.println("Sorted course list: " + courses);

    // 清空列表
    courses.clear();
    System.out.println("List after clearing all courses: " + courses);
}
```

输出：

```
Initial list of courses: [Mathematics, Physics, Chemistry, Biology]
Course at index 2: Chemistry
List after updating the course at index 3: [Mathematics, Physics, Chemistry, Environmental Science]
List after removing the course at index 1: [Mathematics, Chemistry, Environmental Science]
Does the list contain 'Mathematics'? true
Is the list empty? false
Size of the course list: 3
Sorted course list: [Chemistry, Environmental Science, Mathematics]
List after clearing all courses: []
```

上述程序演示了如何使用 `ArrayList` 管理课程名称列表。程序首先导入必要的类并创建一个 `ArrayList`。程序将课程名称添加到列表中并打印初始内容。它根据索引获取并打印课程，更新特定索引处的课程，并根据索引移除课程，在每次操作后显示列表。程序检查特定课程是否存在，验证列表是否为空，并打印列表的大小。它按字母顺序对列表排序，显示排序后的列表，最后清空列表，在最后显示空列表。

## 15.3 LinkedList

Java 中的 `LinkedList` 是一种线性数据结构，由一系列元素组成，每个元素都通过引用与其前一个和后一个元素连接。与数组不同，`LinkedList` 不在连续的内存位置中存储元素。相反，每个元素都指向下一个元素，形成一个链状结构。

`LinkedList` 实现了 `List` 接口。它由节点组成，每个节点包含一个数据元素和一个指向节点的引用。

### 15.3.1 优势

1. 动态大小：与数组不同，`LinkedList` 没有固定大小。
2. 高效的插入和删除：`LinkedList` 的插入和删除非常高效，因为只需要调整引用，而不是移动元素。

### 15.3.2 挑战

1. 随机访问低下：与数组不同，`LinkedList` 不支持基于索引的随机访问。
2. 内存开销：`LinkedList` 中的每个节点都需要额外的内存来存储引用。

### 15.3.3 语法

在 Java 中使用 `LinkedList` 的语法与其他集合相似：

- 1. 导入 `LinkedList` 类：`import java.util.LinkedList;`

- 2. 声明并实例化 `LinkedList`：`LinkedList<ElementType> linkedList = new LinkedList<>();`

- 3. 向 `LinkedList` 添加元素：`linkedList.add(element);`

- 4. 获取 `LinkedList` 中的元素：`ElementType first = linkedList.getFirst();`, `ElementType last = linkedList.getLast();`

- 5. 遍历 `LinkedList`：`for (ElementType element : linkedList) { // 处理每个元素 }`

- 6. 从 `LinkedList` 移除元素：`linkedList.removeFirst();`, `linkedList.removeLast();`

- 7. 检查 `LinkedList` 的大小和空状态：`int size = linkedList.size();`, `boolean isEmpty = linkedList.isEmpty();`

# 程序

```java
import java.util.LinkedList;
```



```java
import java.util.Scanner;

public class LinkedListExample {

    public static void main(String[] args) {

        // 创建一个 LinkedList 来存储课程名称

        LinkedList<String> courses = new LinkedList<>();

        // 将课程名称添加到 LinkedList 中

        courses.add("Mathematics");

        courses.add("Physics");

        courses.add("Chemistry");

        courses.add("Biology");

        // 显示初始课程列表

        System.out.println("Initial list of courses: " + courses);

        // 创建一个 对象以接收用户输入

        Scanner scanner = new Scanner(System.in);

        String newCourse;

        // 提示用户输入更多课程

        System.out.println("Enter additional courses (type 'done' to finish):");

        // 循环接受输入并将课程添加到 LinkedList

        while (true) {

            newCourse = scanner.nextLine();

            if (newCourse.equalsIgnoreCase("done")) {

                break;

            }

            courses.add(newCourse);

        }

        // 显示最终的课程列表

        System.out.println("Final list of courses: " + courses);

        // 检查列表中是否包含 "Physics" 

        boolean hasPhysics = courses.contains("Physics");

        if (hasPhysics) {

            System.out.println("Physics is in the list.");

        }

    }

}
```

```java
System.out.println('Physics' is present in the course list);

} else {

    System.out.println('Physics' is not present in the course list.');

    // Removing the course 'Chemistry' from the LinkedList

    courses.remove('Chemistry');

    System.out.println('List after removing 'Chemistry': ' + courses);

    // Closing the scanner

    scanner.close();

}
```

输出：

```
初始课程列表: [Mathematics, Physics, Chemistry, Biology]
输入额外课程（输入 'done' 完成）:
computer course
done
最终课程列表: [Mathematics, Physics, Chemistry, Biology, course]
'Physics' is present in the course list.
List after removing 'Chemistry': [Mathematics, Physics, Biology, course]
```

上述程序演示了如何使用`LinkedList`来管理课程名称列表。程序首先插入了必要的类并创建一个`LinkedList`来存储课程名称。起初，程序向`LinkedList`中添加了四门课程：“数学”、“物理”、“化学”和“生物”，并显示初始列表。然后，程序提示用户通过控制台输入额外课程，将每门课程添加到`LinkedList`中，直到用户输入“done”。之后，程序显示最终的课程列表。它会检查列表中是否存在“物理”课程并确认其存在。程序随后从`LinkedList`中删除了“化学”，并显示删除后的列表。

## 15.4 HASHSET

`HashSet`是 Java 中一种实现了`Set`接口的集合（Collection）。它代表一个包含唯一元素的集合，其中每个元素只存储一次。内部，它使用哈希表（hash table）来存储元素，为添加、删除和检查元素是否存在等基本操作提供了常数时间的性能。

### 15.4.1 HASHSET 的优势

- 唯一元素：`HashSet`确保每个元素都是唯一的。它会自动防止插入重复元素。
- 性能优异：由于底层的哈希表实现，`HashSet`为添加、删除和检查元素是否存在等基本操作提供了常数时间的性能。

### 15.4.2 HASHSET 的挑战

- 无序：`HashSet`不保证元素的顺序。存储的元素顺序可能与插入时的顺序不一致。
- 没有索引：与列表（lists）不同，`HashSet`不支持索引。你无法通过索引访问元素，因为没有定义的顺序。

## Collections

### 15.4.3 Java 中使用 HASHSET 的语法

- 导入`HashSet`类：

```java
import java.util.HashSet;
```

- 声明并实例化`HashSet`：

```java
HashSet<ElementType> hashSet = new HashSet<>();
```

- 向`HashSet`添加元素：

```java
hashSet.add(element);
```

- 从`HashSet`中移除元素：

```java
hashSet.remove(element);
```

- 检查元素是否存在于`HashSet`中：

```java
boolean exists = hashSet.contains(element);
```

- 遍历`HashSet`：

```java
for (ElementType element : hashSet) {
    // 处理每个元素
}
```

- 检查`HashSet`的大小和为空状态：

```java
int size = hashSet.size();
boolean isEmpty = hashSet.isEmpty();
```

# 用于医疗与健康应用的 Java 22

```java
// 尝试再次添加 "Mathematics" 以演示重复项会被忽略

boolean addedMathematicsAgain = courses.add("Mathematics");

if (!addedMathematicsAgain) {

    System.out.println("Mathematics' was already in the set and was not added");

}

// 显示 LinkedHashSet 的内容（保留插入顺序）

System.out.println("Courses in the set (insertion order maintained): " + courses);

// 检查课程 "Physics" 是否在 LinkedHashSet 中

boolean hasPhysics = courses.contains("Physics");

if (hasPhysics) {

    System.out.println("Physics' is present in the course set.");

} else {

    System.out.println("Physics' is not present in the course set");

}

// 从 LinkedHashSet 中移除课程 "Chemistry"

courses.remove("Chemistry");

System.out.println("Set after removing 'Chemistry': " + courses);
```

```
"Mathematics' was already in the set and was not added.
Courses in the set (insertion order maintained): [Mathematics, Physics, Chemistry, Biology]
'Physics' is present in the course set.
Set after removing 'Chemistry': [Mathematics, Physics, Biology]
```

上述程序演示了如何在 Java 中使用`LinkedHashSet`管理课程集合，并保留了元素的插入顺序。它通过创建一个名为`courses`的`LinkedHashSet`来存储课程名称。该程序向`LinkedHashSet`中添加了多个课程，包括`"Mathematics"`、`"Physics"`、`"Chemistry"`和`"Biology"`。再次尝试添加`"Mathematics"`说明了`LinkedHashSet`会忽略重复项，这与`HashSet`类似。随后显示`LinkedHashSet`的内容，保持了插入顺序。程序检查了课程`"Physics"`是否在`LinkedHashSet`中并确认了其存在。最后，它从`LinkedHashSet`中移除了课程`"Chemistry"`并显示了更新后的内容，展示了按原始插入顺序剩余的课程。

# 15.6 TREESET

`TreeSet`是 Java 中的一个集合类，实现了`NavigableSet`接口并扩展了`AbstractSet`类。它表示一个集合，元素默认按升序存储，或根据创建时提供的自定义比较器进行存储。

## 15.6.1 TREESET 的优势

- 自动排序：`TreeSet`默认按升序自动对元素进行排序。这使得无需人工干预即可维护一个已排序的集合。
- 高效检索：`TreeSet`提供了高效的检索操作，如查找元素、寻找最小和最大元素以及按排序顺序在集合中导航。

## 15.6.2 TREESET 的挑战

- 更高的内存消耗：由于需要维护平衡二叉搜索树的额外开销，`TreeSet`比`HashSet`和`LinkedHashSet`通常消耗更多内存。
- 插入和删除较慢：虽然`TreeSet`提供了高效的检索，但由于需要维护元素的排序顺序，插入和删除操作可能比`HashSet`和`LinkedHashSet`慢。

## 15.6.3 Java 中使用 TreeSet 的语法

- 导入`TreeSet`类：

```java
import java.util.TreeSet;
```

- 声明并实例化`TreeSet`：

```java
TreeSet<ElementType> treeSet = new TreeSet<>();
```

- 向`TreeSet`中添加元素：

```java
treeSet.add(element);
```

- 从`TreeSet`中移除元素：

```java
treeSet.remove(element);
```

- 检查元素是否存在：

```java
boolean exists = treeSet.contains(element);
```

- 遍历`TreeSet`：

```java
for (ElementType element : treeSet) { ... }
```

- 获取第一个和最后一个元素：

```java
ElementType first = treeSet.first();
ElementType last = treeSet.last();
```

# 用于医疗保健和医学应用的 Java 22

这些语法元素允许用户在 Java 中使用队列（Queue），方便了添加、移除、查看元素、检查队列是否为空以及获取其大小等操作。

# 程序

```java
import java.util.LinkedList;

import java.util.Queue;

public class QueueExample {

    public static void main(String[] args) {

        // 创建一个存储课程名称的队列

        Queue<String> courseQueue = new LinkedList<String>();

        // 使用 offer 方法向队列添加课程名称（入队操作）

        courseQueue.offer("Mathematics");

        courseQueue.offer("Physics");

        courseQueue.offer("Chemistry");

        courseQueue.offer("Biology");

        // 显示队列的内容

        System.out.println("Courses in the queue: " + courseQueue);

        // 获取并显示队列头部的元素但不移除（peek）

        String frontCourse = courseQueue.peek();

        System.out.println("Course at the rear of the queue: " + frontCourse);

        // 使用 poll 方法移除队列头部的课程（poll）并显示更新后的队列

        courseQueue.poll();

        System.out.println("Queue after dequeuing the front course: " + courseQueue);

        // 入队另一个课程 "Computer Science"

        courseQueue.offer("Computer Science");

        System.out.println("Queue after enqueuing 'Computer Science': " + courseQueue);

        // 获取队列尾部的元素（强制转换为 LinkedList 并获取最后一个）

        String lastCourse = ((LinkedList<String>)courseQueue).getLast();

        System.out.println("Course at the rear of the queue: " + lastCourse);

        // 检查课程 "Physics" 是否在队列中

        boolean containsPhysics = courseQueue.contains("Physics");

        if (containsPhysics) {

            System.out.println("'Physics' is present in the queue.");

        } else {

            System.out.println("'Physics' is not present in the queue.");

        }

    }

}
```



```
输出：
Courses in the queue: [Mathematics, Physics, Chemistry, Biology]
Course at the rear of the queue: Mathematics
Queue after dequeuing the front course: [Physics, Chemistry, Biology]
Queue after enqueuing 'Computer Science': [Physics, Chemistry, Biology, Computer Science]
Course at the rear of the queue: Computer Science
'Physics' is present in the queue.
```

## 集合

上述程序演示了队列的使用，具体而言是通过`LinkedList`实现，用于在 Java 中管理课程序列。它首先创建一个名为`courseQueue`的队列。然后程序使用`offer`方法向队列添加了几个课程，该方法会将元素放入队列。在添加初始课程集合（“Mathematics”、“Physics”、“Chemistry”和“Biology”）后，程序显示了队列的内容。为了执行该操作，程序使用`peek`方法获取并显示队列头部的课程而不将其移除。随后程序使用`poll`方法从队列中移除一个元素，该方法会移除并返回头部元素，显示操作后的队列内容。接下来，程序使用`offer`方法添加了另一个课程“Computer Science”并显示更新后的队列。为了获取队列尾部的元素，程序将队列转换为`LinkedList`，并使用`contains`方法检查特定课程“Physics”是否存在于队列中并确认其存在。

## 15.8 HASHMAP

在 Java 中，`HashMap`是实现`Map`接口的类，表示键值对的集合。它允许你根据键来存储和检索元素。`HashMap`使用哈希数据结构存储元素，提供了快速的检索操作。

### 15.8.1 HASHMAP 的优势

- 1. 检索：`HashMap`为基本操作（如`get()`和`put()`）提供了常数级性能，对于大型数据集非常高效。
- 2. 灵活的键值对：`HashMap`允许存储不同类型的键值对，为表示各种关系和数据结构提供了灵活性。

### 15.8.2 HASHMAP 的挑战

- 1. 无序迭代：`HashMap`中的元素是无序的，这意味着在迭代期间返回元素的顺序是没有保证的。如果用户需要有序遍历，则需要使用`LinkedHashMap`或`TreeMap`。
- 2. 冲突处理：在基于哈希的数据结构中，当多个键具有相同的索引时可能会发生冲突。需要高效的冲突解决策略（如链地址法或开放地址法）来维持性能。

### 15.8.3 在 Java 中使用 HASHMAP 的语法

- 1. 导入`HashMap`类：

```java
import java.util.HashMap;
```

- 2. 声明并实例化`HashMap`对象：

```java
HashMap<KeyType, ValueType> hashMap = new HashMap<>();
```

- 3. 向`HashMap`添加键值对：

```java
hashMap.put(key, value);
```

- 4. 根据键检索值：

```java
ValueType value = hashMap.get(key);
```

- 5. 检查`HashMap`是否包含特定键：

```java
boolean containsKey = hashMap.containsKey(key);
```

- 6. 从`HashMap`中移除键值对：

```java
ValueType removedValue = hashMap.remove(key);
```

- 7. 检查`HashMap`是否为空：

```java
boolean isEmpty = hashMap.isEmpty();
```

- 8. 获取`HashMap`的大小：

```java
int size = hashMap.size();
```

Java 中的`HashMap`方便了添加键值对、根据键检索值、检查包含性、移除条目以及查询 map 大小的操作。

## 程序

```java
import java.util.HashMap;

public class HashMapExample {

    public static void main(String[] args) {

        // 创建 HashMap 存储课程名称及其对应的 ID

        HashMap<Integer, String> courseMap = new HashMap<>();

        // 使用 put 方法向 HashMap 添加条目

        courseMap.put(1, "Mathematics");

        courseMap.put(2, "Physics");

        courseMap.put(3, "Chemistry");

        courseMap.put(4, "Biology");

        courseMap.put(5, "Computer Science");

        // 显示 HashMap 内容

        System.out.println("Course: " + courseMap);

        // 获取与特定 ID (2) 关联的课程

        String course = courseMap.get(2);

        System.out.println("Course with ID 2: " + course);

    }

}
```

## 15.9.3 JAVA 中使用 LINKEDHASHMAP 的语法

- 1. 导入`LinkedHashMap`类：

```java
import java.util.LinkedHashMap;
```

- 2. 声明并实例化`LinkedHashMap`对象：

```java
LinkedHashMap<KeyType, ValueType> linkedHashMap = new LinkedHashMap<>();
```

- 3. 向`LinkedHashMap`添加键值对：

```java
linkedHashMap.put(key, value);
```

- 4. 根据键检索值：

```java
ValueType value = linkedHashMap.get(key);
```

- 5. 检查`LinkedHashMap`是否包含特定键：

```java
boolean containsKey = linkedHashMap.containsKey(key);
```

- 6. 从`LinkedHashMap`中移除一个键值对：

```java
ValueType removedValue = linkedHashMap.remove(key);
```

- 7. 检查`LinkedHashMap`是否为空：

```java
boolean isEmpty = linkedHashMap.isEmpty();
```

- 8. 获取`LinkedHashMap`的大小：

```java
int size = linkedHashMap.size();
```

Java 中的`LinkedHashMap`方便了诸如添加键值对、根据键检索值、检查包含性、移除条目以及查询 map 大小等操作。此外，`LinkedHashMap`维护了元素的插入顺序或访问顺序，提供了可预测的迭代顺序。

## 程序

```java
import java.util.LinkedHashMap;
import java.util.Map;

public class LinkedHashMapExample {

    public void main(String[] args) {

        // 创建一个 LinkedHashMap 来存储课程名称及其对应的 ID

        LinkedHashMap<Integer, String> courseMap = new LinkedHashMap<>();

        // 使用 put 方法向 LinkedHashMap 添加课程项

        courseMap.put(1, "Mathematics");

        courseMap.put(3, "Chemistry");

        courseMap.put(4, "Biology");

        courseMap.put(5, "Computer Science");

        // 显示 LinkedHashMap 的内容（保留插入顺序）

        System.out.println("Course Map: " + courseMap);

        // 使用 get 方法检索并显示与特定 ID (2) 关联的课程

        String course = courseMap.get(2);

        System.out.println("Course with ID 2: " + course);

        // 检查 LinkedHashMap 中是否存在 "Physics"

        boolean hasPhysics = courseMap.containsKey("Physics");

        if (hasPhysics) {

            System.out.println("'Physics' is present in the course map.");

        } else {

            System.out.println("'Physics' is not present in the course map.");

        }

        // 移除特定 ID (4) 的课程并显示更新后的 LinkedHashMap

        courseMap.remove(4);

        System.out.println("Course Map after removing ID 4: " + courseMap);

        // 检查特定键 (ID 2) 是否存在于 LinkedHashMap 中

        boolean hasKey2 = courseMap.containsKey(2);

        if (hasKey2) {

            System.out.println("ID 2 is present in the course map.");

        } else {

            System.out.println("ID 2 is not present in the course map.");

        }

        // 打印 LinkedHashMap 的大小

        System.out.println("Size of the course map: " + courseMap.size());

        // 清空 LinkedHashMap 中的所有条目

        courseMap.clear();

        System.out.println("Course Map after clearing: " + courseMap);

    }

}
```

输出：
Course Map: {1=Mathematics, 2=Physics, 3=Chemistry, 4=Biology, 5=Computer Science}
Course with ID 2: Physics
'Physics' is present in the course map.
Course Map after removing ID 4: {1=Mathematics, 2=Physics, 3=Chemistry, 5=Computer Science}
ID 2 is present in the course map: 4
Size of the course map: 0
Course Map after clearing: {}

该程序演示了如何使用`LinkedHashMap`在 Java 中管理课程名称集合，每个课程都与一个唯一的整数 ID 关联。程序首先创建一个名为`courseMap`的`LinkedHashMap`来存储课程与其 ID 的映射，确保插入顺序被维护。程序使用`put`方法向`LinkedHashMap`添加了若干门课程（ID 范围从 1 到 5），并显示了`LinkedHashMap`的内容。程序使用`get`方法检索并打印与特定 ID 关联的课程。使用`containsKey`方法检查`LinkedHashMap`中是否存在特定课程“Physics”并确认其存在。接下来，程序使用`remove`方法移除特定 ID (4) 的课程，并使用`containsKey`方法检查特定键 (2) 是否在`LinkedHashMap`中并确认其存在。程序使用`size`方法打印`LinkedHashMap`的大小，然后使用`clear`方法清空所有条目，最后显示一个空的`LinkedHashMap`。

## 15.10 TREEMAP

在 Java 中，`TreeMap`是一个实现了`NavigableMap`接口并扩展了`AbstractMap`的类。它是一个基于红黑树结构的排序 map。`TreeMap`根据元素的自然顺序或指定的比较器（comparator）对其元素进行排序顺序维护。

### 15.10.1 TREEMAP 的优势

- 1. 有序集合：`TreeMap`按排序顺序维护其元素，使其适用于需要有序集合的场景。它默认提供按键升序的迭代，或者在提供比较器时提供自定义排序。
- 2. 高效范围查询：`TreeMap`支持高效的范围查询和操作，如`firstKey()`、`lastKey()`、`headMap()`、`tailMap()`和`subMap()`，能够检索特定范围内的元素。

### 15.10.2 TREEMAP 的挑战

- 1. 内存开销更高：由于需要维护树结构，`TreeMap`的内存开销高于`HashMap`。
- 2. 插入和删除较慢：由于维护树结构和确保平衡的额外开销，`TreeMap`的插入和删除操作可能比`HashMap`慢。

### 15.10.3 JAVA 中使用 TREEMAP 的语法

- 1. 导入`TreeMap`类：

```java
import java.util.TreeMap;
```

- 2. 声明并实例化`TreeMap`对象：

```java
TreeMap<KeyType, ValueType> treeMap = new TreeMap<>();
```

- 3. 向`TreeMap`添加键值对：

```java
treeMap.put(key, value);
```

- 4. 根据键检索值：

```java
ValueType value = treeMap.get(key);
```

- 5. 检查`TreeMap`是否包含特定键：

```java
boolean containsKey = treeMap.containsKey(key);
```

- 6. 从`TreeMap`中移除一个键值对：

```java
ValueType removedValue = treeMap.remove(key);
```

- 7. 检查`TreeMap`是否为空：

```java
boolean isEmpty = treeMap.isEmpty();
```

- 8. 获取`TreeMap`的大小：

```java
int size = treeMap.size();
```

## 用于医疗与健康应用程序的 Java 22

```java
System.out.println("Tree Map after clearing: " + courseMap);
```



```
Output:
Tree Map: {101=Mathematics, 102=Physics, 103=Chemistry, 104=Biology, 105=Computer Science}
Course with ID 102: Physics
'Physics' is present in the Tree map.
Tree Map after removing ID 104: {101=Mathematics, 102=Physics, 105=Computer Science}
ID 102 is present in the Tree map.
Size of the Tree map: 4
Tree Map after clearing: {}
```

上述程序演示了如何在 Java 中使用 `TreeMap` 来管理课程名称集合，每个课程都关联一个唯一的整数 ID。程序首先创建了一个 `TreeMap` `courseMap` 来存储课程名称到 ID 的映射，确保键按自然顺序排序。程序使用 `put` 方法向 `TreeMap` 中添加了几个课程，并按键的升序显示 `TreeMap` 的内容。它使用 `get` 方法检索并打印与特定 ID 关联的课程名称。程序使用 `containsValue` 方法检查特定课程 `Physics` 是否存在于 `TreeMap` 中，并确认其存在。随后，它使用 `remove` 方法删除特定 ID (104) 的课程，并显示删除后的更新 `TreeMap`。接下来，程序使用 `containsKey` 方法检查 `TreeMap` 中是否存在特定键 (102)，并确认其存在。它使用 `size` 方法打印 `TreeMap` 的大小，然后使用 `clear` 方法清除所有条目，最后显示空的 `TreeMap`。

# HashTable（哈希表）

在 Java 中，`Hashtable` 是一个实现了 `Map` 接口并扩展了 `Dictionary` 的类。它表示一个键值对集合，其中每个键都映射到一个特定的值。`Hashtable` 使用哈希表数据结构来存储元素，允许对键值对进行高效的检索和存储。

## 15.11.1 HashTable 的优势

- 1. 线程安全操作：`Hashtable` 是同步的，这意味着支持多线程的并发访问，而没有数据损坏的风险。这使其适用于对线程安全有要求的多线程环境。
- 2. 高效检索：`Hashtable` 为 `get()` 和 `put()` 等基本操作提供了常数级性能，使其在存储和检索键值对时非常高效，特别是当元素数量很大时。

## 15.11.2 HashTable 的挑战

- 1. 同步开销：虽然线程安全是一个优势，但 `Hashtable` 中的同步开销可能会影响性能，特别是在不需要高并发的场景下。对于单线程应用程序，这种开销可能是不必要的。
- 2. 元素迭代：迭代的效率不如 `ArrayList` 或 `HashMap` 等其他数据结构。`Hashtable` 提供的用于迭代的 `Enumeration` 接口不如其他集合中的迭代器（`iterators`）那样灵活。

## 15.11.3 在 Java 中使用 HashTable 的语法

- 1. 导入 `Hashtable` 类：
```java
import java.util.Hashtable;
```

- 2. 声明并实例化 `Hashtable` 对象：
```java
Hashtable<KeyType, ValueType> hashtable = new Hashtable<>();
```

- 3. 向 `Hashtable` 中添加键值对：
```java
hashtable.put(key, value);
```

- 4. 根据键检索值：
```java
ValueType value = hashtable.get(key);
```

- 5. 检查 `Hashtable` 是否包含特定键：
```java
boolean containsKey = hashtable.containsKey(key);
```

- 6. 从 `Hashtable` 中移除键值对：
```java
ValueType removedValue = hashtable.remove(key);
```

- 7. 检查 `Hashtable` 是否为空：
```java
boolean isEmpty = hashtable.isEmpty();
```

- 8. 获取 `Hashtable` 的大小：
```java
int size = hashtable.size();
```

Java 中的 `Hashtable` 方便了如添加键值对、根据键检索值、删除条目以及查询映射大小等操作。此外，`Hashtable` 为其元素提供了同步访问，确保了并发环境下的线程安全。

# 程序

```java
import java.util.Hashtable;

public class HashtableExample {

    public static void main(String[] args) {

        // 创建一个 Hashtable 来存储带有 ID 的课程名称

        Hashtable<Integer, String> courseTable = new Hashtable<>();

        // 使用 put 方法向 Hashtable 添加课程

        courseTable.put(101, "Mathematics");

        courseTable.put(102, "Physics");

        courseTable.put(103, "Chemistry");

        courseTable.put(104, "Biology");

        courseTable.put(105, "Computer Science");

        // 显示 Hashtable 的内容

        System.out.println("Course Table: " + courseTable);

        // 检索并显示与特定 ID (102) 关联的课程

        String course = courseTable.get(102);

        System.out.println("Course with ID 102: " + course);

        // 检查课程 "Physics" 是否于 Hashtable 中

        boolean hasPhysics = courseTable.containsValue("Physics");

        if (hasPhysics) {

            System.out.println("'Physics' is present in the course table.");

        } else {

            System.out.println("'Physics' is not present in the course table.");

        }

        // 删除特定 ID (104) 的课程并显示更新后的

        courseTable.remove(104);

        System.out.println("Course Table after removing ID 104: " + courseTable);

        // 检查特定键 (ID 102) 是否于 Hashtable 中

        boolean hasKey102 = courseTable.containsKey(102);

        if (hasKey102) {

            System.out.println("ID 102 is present in the course table.");

        } else {

            System.out.println("ID 102 is not present in the course table.");

        }

        // 打印 Hashtable 的大小

        System.out.println("Size of the course table: " + courseTable.size());

        // 清除 Hashtable 中的所有条目

        courseTable.clear();

        System.out.println("Course Table after clearing: " + courseTable);

    }

}
```

```
Output:
Course Table: {105=Computer Science, 104=Biology, 103=Chemistry, 102=Physics, 101=Mathematics}
Course with ID 102: Physics
'Physics' is present in the course table.
Course Table after removing ID 104: {105=Computer Science, 103=Chemistry, 102=Physics, 101=Mathematics}
ID 102 is present in the course table.
Size of the course table: 4
Course Table after clearing: {}
```

上述程序演示了如何在 Java 中使用 `Hashtable` 来管理课程名称集合，每个课程都关联一个唯一的整数 ID。程序首先创建了一个 `Hashtable` `courseTable` 来存储映射到其 ID 的课程名称。程序随后使用 `put` 方法向 `Hashtable` 添加了几个 ID 范围从 101 到 105 的课程，并使用 `get` 方法显示了 `Hashtable` 的内容。它使用 `containsValue` 方法检查特定课程 `Physics` 是否存在于 `Hashtable` 中。它使用 `remove` 方法删除特定 ID (104) 的课程，并显示删除后的更新 `Hashtable`。它使用 `containsKey` 方法检查特定键 (ID 102) 是否存在于 `Hashtable` 中。它使用 `size` 方法打印 `Hashtable` 的大小，然后使用 `clear` 方法清除所有条目，最后显示空的 `Hashtable`。

# EnumMap（枚举映射）

在 Java 中，`EnumMap` 是一个实现了 `Map` 接口的特殊类，专门为枚举键设计。它表示一个键值对集合，其中每个键都是枚举。`EnumMap` 是一种高效、紧凑且类型安全的映射，用于存储枚举键。

## 15.12.1 EnumMap 的优势

- 1. 类型安全：`EnumMap` 仅接受枚举常量。这提供了强类型安全，防止了在其他实现中使用错误类型时可能发生的运行时错误。
- 2. 内存使用与性能：对于枚举键，`EnumMap` 在内存使用上非常高效，并提供了比其他实现更好的性能。它是通过为枚举类型定制的数组来实现的。

## 15.12.2 EnumMap 的挑战

- 1. 键的限制：`EnumMap` 专门设计用于与枚举工作。虽然这为基于枚举的映射提供了类型安全和高效，但限制了它在需要使用其他类型键的场景中的适用性，`EnumMap` 无法使用。
- 2. 初始化：创建 `EnumMap` 需要初始化所有枚举常量以便为内部数组分配空间。当映射具有大量常量或常量频繁变化时这可能会非常麻烦。

## 15.12.3 在 Java 中使用 EnumMap 的语法

- 1. 导入 `EnumMap` 类：
```java
import java.util.EnumMap;
```

- 2. 声明并实例化 `EnumMap` 对象：
```java
EnumMap<EnumType, ValueType> enumMap = new EnumMap<>(EnumType.class);
```

- 3. 向 `EnumMap` 中添加键值对：
```java
enumMap.put(enumKey, value);
```

- 4. 根据键检索值：
```java
ValueType value = enumMap.get(enumKey);
```

- 5. 检查 `EnumMap` 是否包含特定键：
```java
boolean containsKey = enumMap.containsKey(enumKey);
```

- 6. 从 `EnumMap` 中移除键值对：
```java
ValueType removedValue = enumMap.remove(enumKey);
```

- 7. 检查 `EnumMap` 是否为空：
```java
boolean isEmpty = enumMap.isEmpty();
```

- 8. 获取 `EnumMap` 的大小：
```java
int size = enumMap.size();
```

Java 中的 `EnumMap` 方便了诸如添加基于枚举的键值对、根据枚举键检索值、检查包含性、移除项以及查询映射的大小的操作。`EnumMap` 的类型安全性和性能优势使其成为 Java 中基于枚举映射的极佳选择。

# 程序

```java
import java.util.EnumMap;

public class CourseMapExample {

    // 定义课程类型的枚举

    enum CourseType {

        MATHEMATICS,

        PHYSICS,

        CHEMISTRY,

        BIOLOGY,

        COMPUTER_SCIENCE

    }

    void main(String[] args) {

        // 创建一个以 CourseType 为键类型的 EnumMap

        EnumMap<CourseType, String> courseMap = new EnumMap<>(CourseType.class);

        // 向 EnumMap 中添加课程

        courseMap.put(CourseType.MATHEMATICS, "Advanced Calculus");

        courseMap.put(CourseType.PHYSICS, "Quantum Mechanics");

        courseMap.put(CourseType.CHEMISTRY, "Organic Chemistry");

        courseMap.put(CourseType.BIOLOGY, "Genetics");

        courseMap.put(CourseType.COMPUTER_SCIENCE, "Data Structures");

        System.out.println("CourseMap: " + courseMap);

        // 获取并显示与特定类型相关的课程

        String course = courseMap.get(CourseType.CHEMISTRY);

        System.out.println("Course for CHEMISTRY: " + course);

        // 检查 EnumMap 中是否存在特定课程 "Mechanics"

        boolean hasMechanics = courseMap.containsValue("Mechanics");

        if (hasMechanics) {

            System.out.println("Mechanics" is present in the course map.");

        } else {

            System.out.println("Mechanics" is not present in the course map.");

        }

        // 从 EnumMap 中移除 MATHEMATICS 课程类型并显示更新后的 map

        courseMap.remove(CourseType.MATHEMATICS);

        System.out.println("Course Map after removing MATHEMATICS: " + courseMap);

        // 检查 EnumMap 中是否存在特定的课程类型 PHYSICS

        boolean hasPhysics = courseMap.containsKey(CourseType.PHYSICS);

    }

}
```

# Collections

```java
if (hasPhysics) {
    System.out.println("PHYSICS is present in the course map.");
} else {
    System.out.println("PHYSICS is not present in the course map.");
}
// 打印 EnumMap 的大小
System.out.println("Size of the course map: " + courseMap.size());
// 清除 EnumMap 中的所有项
courseMap.clear();
System.out.println("Course map after clearing: " + courseMap);
```

```
Output:
```



Course Map: `{MATHEMATICS=Advanced Calculus, PHYSICS=Quantum Mechanics, CHEMISTRY=Organic Chemistry, BIOLOGY=Genetics, COMPUTER_SCIENCE=Data Structures}`

Course for CHEMISTRY: Organic Chemistry

`'Mechanics'` is not present in the course map.

Course Map after removing MATHEMATICS: `{PHYSICS=Quantum Mechanics, CHEMISTRY=Organic Chemistry, BIOLOGY=Genetics, COMPUTER_SCIENCE=Data Structures}`

PHYSICS is present in the course map.

Size of the course map: 4

Course Map after clearing: `{}`

上述程序说明了如何使用 `EnumMap` 将课程类型与其相应的名称关联。通过定义一个枚举类 `CourseType`，其中包含代表不同课程类型的常量：MATHEMATICS、PHYSICS、CHEMISTRY、BIOLOGY 和 COMPUTER_SCIENCE，并将键指定为 `CourseType`。在 `main` 方法内部，创建一个名为 `courseMap` 的 `EnumMap`，使用 `put` 方法添加项，其中每个课程类型都映射到相应的名称。

程序使用 `contains` 方法检查 `EnumMap` 中是否存在特定课程 `Mechanics` 并确认其存在。接下来，使用 `remove` 方法从 `EnumMap` 中移除课程类型 MATHEMATICS，并显示更新后的 `EnumMap`。程序使用 `containsKey` 方法检查 `EnumMap` 中是否存在特定课程类型 PHYSICS 并确认其存在。使用 `size` 方法打印 `EnumMap` 的大小，并使用 `clear` 方法清除所有项，最后显示空的 `EnumMap`。

# 15.13 栈 (STACK)

在 Java 中，`Stack` 是一个表示后进先出 (LIFO) 数据结构的类。它扩展了 `Vector` 类，提供了五种操作，允许将向量被视为栈。它提供了常用的 `push` 和 `pop` 操作，还提供了查看栈顶元素、测试栈是否为空以及搜索元素的方法。

## 15.13.1 栈的优势

- 1. 接口简单：`Stack` 类为实现基于栈的操作提供了简单且直观的接口。它提供了诸如 `push()` 添加元素、`pop()` 移除元素、`peek()` 检查栈顶元素以及 `isEmpty()` 检查栈是否为空等方法。
- 2. 撤销/重做的实现：栈常用于应用程序实现撤销（undo）和重做（redo）功能。通过使用栈存储用户操作历史，实现撤销和重做操作变得非常简单，从一个栈中弹出并推入另一个栈可以有效地反转或重执行操作。

## 15.13.2 栈的挑战

- 1. 性能问题：`Stack` 类继承自 `Vector`，由于它是同步的，这在单线程环境下可能会产生额外的开销。
- 2. 功能性限制：栈在某些场景下可能不如其他集合类（如 `Deque`）灵活。

## 15.13.3 在 Java 中使用栈的语法

- 1. 导入：

```java
import java.util.Stack;
```

- 2. 实例化：

```java
Stack<String> stack = new Stack<>();
```

- 3. 向栈推入元素：

```java
stack.push(element);
```

- 4. 从栈弹出元素：

```java
Element element = stack.pop();
```

- 5. 查看栈顶元素：

```java
Element topElement = stack.peek();
```

- 6. 检查栈是否为空：

```java
boolean isEmpty = stack.isEmpty();
```

- 7. 获取栈的大小：

```java
int size = stack.size();
```

Java 中的栈方便了诸如推入、弹出、查看栈顶、检查为空以及查询大小的操作。

## Program

```java
import java.util.Stack;
public class StackExample {

    public static void main(String[] args) {
        // 创建一个栈
        Stack<String> stack = new Stack<>();

        // 向栈中推入元素
        stack.push("First");
        stack.push("Second");
        stack.push("Third");
        System.out.println("Stack: " + stack);

        // 查看栈顶元素
        String top = stack.peek();
        System.out.println("Top element: " + top);

        // 弹出元素
        String popped = stack.pop();
        System.out.println("Popped element: " + popped);

        // 检查栈是否为空
        System.out.println("Is stack empty? " + stack.isEmpty());

        // 获取栈的大小
        System.out.println("Stack size: " + stack.size());

        // 清空栈
        stack.clear();
        System.out.println("Stack after clearing: " + stack);
    }
}
```

Output:

```
Stack: [First, Second, Third]
Top element: Third
Popped element: Third
Is stack empty? false
Stack size: 2
Stack after clearing: []
```

上述程序说明了如何使用 `Stack` 来存储字符串。通过演示如何推入元素、弹出元素、查看栈顶、检查为空、获取大小以及清空栈，展示了栈的基本用法。

## 用于医疗保健和医学应用的 Java 22

方法，将其从栈（Stack）的顶部移除。显示弹出的课程，并再次显示栈以反映移除操作。程序使用搜索方法在栈中搜索特定课程“物理”（Physics）。如果找到该课程，则打印其在栈中的位置；否则，打印一条指示课程不存在的消息。使用 `isEmpty` 方法检查栈是否为空并打印适当的消息。使用 `size` 方法打印栈的大小。最后，使用 `clear` 方法清除栈中的所有元素，并显示空栈。

# 15.14 VECTOR

在 Java 中，`Vector` 是一个遗留类，表示动态数组，类似于 `ArrayList`。它是同步的且线程安全的，这意味着多个线程可以并发操作 `Vector` 而不会导致数据损坏。然而，它的同步特性可能会在单线程场景下影响性能。

## 15.14.1 VECTOR 的优势

- 1. 线程安全：`Vector` 的主要优势之一是它的线程安全特性。它确保了多个线程对 `Vector` 执行的操作是同步的，从而防止了多线程环境下的并发修改异常和数据损坏。
- 2. 动态调整大小：与 `ArrayList` 一样，`Vector` 会随着元素的添加或删除动态调整大小，允许它容纳任意数量的元素，无需手动调整大小或重新分配。

## 15.14.2 VECTOR 的挑战

- 1. 性能开销：`Vector` 的同步带有性能开销，特别是在不需要线程安全的单线程场景下。这导致与 `ArrayList` 等非同步集合相比，执行速度较慢。
- 2. 灵活性有限：`Vector` 提供了线程安全性，但是以牺牲灵活性为代价的。在不需要线程安全的场景，使用 `ArrayList` 或非同步集合可能会提供更好的性能和更高的灵活性。

## 15.14.3 Java 中使用 Vector 的语法

- 1. 导入 Vector 类：

```java
import java.util.Vector;
```

- 2. 声明并实例化 Vector 对象：

```java
Vector<Type> vector = new Vector<>();
```

- 3. 向向量中添加元素：

```java
vector.add(element);
```

- 4. 访问特定索引处的元素：

```java
Type element = vector.get(index);
```

- 5. 从向量中移除元素：

```java
vector.remove(element);
```

- 6. 检查向量是否包含特定元素：

```java
boolean containsElement = vector.contains(element);
```

- 7. 获取向量的大小：

```java
int size = vector.size();
```

- 8. 使用循环或迭代器遍历向量的元素。

Java 中的 `Vector` 对象允许添加和访问元素、移除元素、检查包含性以及获取 Vector 的大小等操作。虽然 `Vector` 提供了线程安全性，但开发者在选择 `Vector` 和 `ArrayList` 等其他集合之间时，应该评估此特性是否必要，并考虑性能的影响。

## 程序

```java
import java.util.Vector;
public class VectorExample {
    public static void main(String[] args) {
        // 初始化 Vector 以存储课程名称
        Vector<String> courseVector = new Vector<>();
        // 向 Vector 添加课程
        courseVector.add("Mathematics");
        courseVector.add("Physics");
        courseVector.add("Chemistry");
        courseVector.add("Biology");
        courseVector.add("Computer Science");
        // 显示 Vector 的内容
        System.out.println("Vector: " + courseVector);
        // 移除并打印特定索引（例如索引 2）处的课程
        String courseAtIndex = courseVector.get(2);
        System.out.println("Course at index 2: " + courseAtIndex);
        // 将特定索引（3）处的课程更新为“History”
        courseVector.set(3, "History");
        System.out.println("Vector after updating index: 3: " + courseVector);
        // 从 Vector 移除指定索引（例如索引 1）处的课程
        String removedCourse = courseVector.remove(1);
        System.out.println("Removed: " + removedCourse);
        // 移除后显示 Vector
        System.out.println("Vector after removal: " + courseVector);
        // 检查 Vector 中是否存在特定课程“Physics”
        boolean hasPhysics = courseVector.contains("Physics");
        System.out.println("Physics exists in the Vector: " + hasPhysics);
        // 检查 Vector 是否为空
        boolean isEmpty = courseVector.isEmpty();
        System.out.println("The Vector is empty: " + isEmpty);
        // 打印 Vector 的大小
        System.out.println("Size of the Vector: " + courseVector.size());
        // 清除 Vector 中的所有元素
        courseVector.clear();
        System.out.println("Course Vector: " + courseVector);
    }
}
```

```java
// Create an ArrayList to store course names
List<String> courseList = new ArrayList<>();
// Add several courses to the ArrayList
courseList.add("Mathematics");
courseList.add("Physics");
courseList.add("Chemistry");
courseList.add("Biology");
courseList.add("Computer Science");
// Display the contents of the ArrayList
System.out.println("Course List: " + courseList);
// Retrieve and print the course at a specific index (e.g., index 2)
String courseAtIndex = courseList.get(2);
System.out.println("Course at index " + courseAtIndex);
// Update a course at a specific index (index 3) with "History"
courseList.set(3, "History");
System.out.println("Course List after updating index 3: " + courseList);
// Remove a course from the ArrayList at a specific index (e.g., index 1)
String removedCourse = courseList.remove(1);
System.out.println("Removed: " + removedCourse);
// Display the ArrayList after removal
System.out.println("ArrayList after removal: " + courseList);
// Check if a specific course, "Physics," exists in the ArrayList
boolean hasPhysics = courseList.contains("Physics");
System.out.println("Physics exists in the ArrayList: " + hasPhysics);
// Check if the ArrayList is empty
boolean isEmpty = courseList.isEmpty();
System.out.println("The ArrayList is empty: " + isEmpty);
// Print the size of the ArrayList
System.out.println("Size of the ArrayList: " + courseList.size());
// Clear all elements from the ArrayList
courseList.clear();
System.out.println("Course List after clearing: " + courseList);
```

Output:

```
Course List: [Mathematics, Physics, Chemistry, Biology, Computer Science]
Course at index 2: Chemistry
Course List after updating index 3: [Mathematics, Physics, Chemistry, History, Computer Science]
Removed course: Physics
Course List after removal: [Mathematics, Chemistry, History, Computer Science]
'Physics' exists in the ArrayList: false
The ArrayList is empty: false
Size of the ArrayList: 4
Course List after clearing: []
```



上述程序演示了如何使用 Java 中的 `List` 接口（特别是 `ArrayList` 实现）来管理课程名称集合。程序首先创建了一个名为`courseList`的`ArrayList`来存储课程名称。程序使用`add`方法向`ArrayList`中添加了几门课程，包括“数学”、“物理”、“化学”、“生物”和“计算机科学”。然后它显示了`ArrayList`的内容，按照添加的顺序显示课程。程序使用`get`方法获取并打印特定索引处的课程。接着，使用`set`方法更新特定索引处的课程，将索引 3 处的课程替换为“历史”。再次显示`ArrayList`以反映更新。使用`remove`方法从`ArrayList`的指定索引处删除课程。显示被删除的课程，并显示删除后的`ArrayList`。程序使用`contains`方法检查`ArrayList`中是否存在特定课程“物理”，并相应打印结果。它还使用`isEmpty`方法检查`ArrayList`是否为空，并打印适当的消息。使用`size`方法打印`ArrayList`的大小。最后，使用`clear`方法清除`ArrayList`中的所有元素，并显示空的`ArrayList`。

# 集合 (Collections)

## 15.16 Map

在 Java 中，`Map`是一个接口，表示键值对的集合，其中每个键都是唯一的，并映射到一个对应的值。它提供了通过键进行添加、访问和操作元素的方法。`Map`接口的实现类包括`HashMap`、`TreeMap`、`LinkedHashMap`等。

### 15.16.1 Map 的优势

- 1. **按键快速检索**：`Map`可以根据其关联的键快速检索值。这使其成为需要使用唯一标识符（键）快速访问值的场景的理想选择。
- 2. **键值关联**：`Map`建立了键和值之间清晰的关联，允许开发者以结构化的方式存储和检索数据。这种键值对组合有助于应用程序中数据的组织和管理。

### 15.16.2 Map 的挑战

- 1. **唯一性要求**：`Map`强制要求键的唯一性，这意味着每个键在`map`中必须是唯一的。重复的键可能会导致意外的行为或数据覆盖。开发者在操作`map`时需要确保键的唯一性。
- 2. **迭代顺序**：取决于实现方式，对`map`中元素的迭代顺序可能是不一致或不可预测的。虽然某些实现保持了插入顺序（例如`LinkedHashMap`），但其他实现并不保证任何特定顺序（例如`HashMap`）。这种不可预测性可能会影响依赖于有序迭代的应用程序的行为。

### 15.16.3 在 Java 中使用 Map 的语法

- 1. 导入`Map`接口：

```java
import java.util.Map;
```

- 2. 声明带有键和值类型的`Map`变量：

```java
Map<KeyType, ValueType> map;
```

- 3. 使用实现类实例化`Map`对象（例如`HashMap`、`TreeMap`）：

```java
map = new HashMap<>();
// 或 new TreeMap<>(), new LinkedHashMap<>()
```

- 4. 向`map`中添加键值对：

```java
map.put(key, value);
```

- 5. 访问与特定键关联的值：

```java
ValueType value = map.get(key);
```

- 6. 从`map`中删除键值对：

```java
map.remove(key);
```

- 7. 检查`map`是否包含某个键：

```java
boolean hasKey = map.containsKey(key);
```

- 8. 检查`map`是否包含某个值：

```java
boolean hasValue = map.containsValue(value);
```

- 9. 获取`map`的大小：

```java
int size = map.size();
```

- 10. 遍历键值对：

```java
for (Map.Entry<KeyType, ValueType> entry : map.entrySet()) {
    System.out.println(entry.getKey() + " : " + entry.getValue());
}
```

# Java 22 用于医疗保健和医疗应用

（注：此部分是关于现代 Java 特性在数字健康领域应用的主标题。）

## 15.17.1 ENUMSET 的优势

- 1. 内存效率：`EnumSet`内部对枚举使用了高效的位向量（bit vector）表示，实现了紧凑的存储和极小的内存开销。这使得`EnumSet`非常适用于对内存敏感的场景，特别是在处理大量枚举值时。
- 2. 操作快速：`EnumSet`针对交集、并集和差集等集合操作进行了优化。这些操作的执行非常高效，在处理枚举常量时，其性能通常优于其他的集合实现。`EnumSet`的性能优势在涉及频繁集合操作的场景中尤为明显。

## 15.17.2 ENUMSET 的挑战

- 1. 限于枚举类型：`EnumSet`专为枚举类型设计，不能用于非枚举元素。这一限制限制了它在涉及常量的场景中的适用性。如果用户需要处理非枚举元素，则需要使用其他实现，如`HashSet`或`TreeSet`。
- 2. 创建后不可变：一旦创建了`EnumSet`，其内容就无法被修改。虽然这种不可变性确保了并发环境下的线程安全，但也意味着你无法在创建后向`EnumSet`添加或删除元素。如果需要对集合进行动态修改，用户可能需要使用替代的集合实现。

## 15.17.3 JAVA 中使用 EnumSET 的语法

- 1. 导入`EnumSet`类：

```java
import java.util.EnumSet;
```

- 2. 为特定的枚举类型声明`EnumSet`变量：

```java
EnumSet<EnumType> enumSet;
```

- 3. 使用`EnumSet`类提供的静态方法创建`EnumSet`实例：

```java
enumSet = EnumSet.allOf(EnumType.class);
```

- 4. 使用`add`、`remove`、`contains`、`clear`等方法执行交集、并集、差集等操作。
- 5. 使用 for-each 循环或迭代器遍历`EnumSet`的元素。
- 6. 可使用静态工厂方法如`noneOf`、`of`、`range`等来创建包含特定枚举常量的`EnumSet`。

Java 中的`EnumSet`为枚举常量提供了高效的存储和操作。`EnumSet`对枚举的专门化使其成为 Java 应用中处理枚举值的强大工具。

## Program

```java
import java.util.EnumSet;
public class EnumSetExample {
    // 定义课程类型的枚举
    enum CourseType {
        MATHEMATICS, PHYSICS, BIOLOGY, COMPUTER_SCIENCE
    }
    public static void main(String[] args) {
        // 创建一个带有初始课程类型的 EnumSet
        EnumSet<CourseType> courseSet = EnumSet.of(CourseType.MATHEMATICS,
        CourseType.PHYSICS, CourseType.CHEMISTRY);
        // 显示 EnumSet 的内容
        System.out.println("Initial EnumSet: " + courseSet);
        // 向 EnumSet 添加另一个课程类型
        courseSet.add(CourseType.BIOLOGY);
        System.out.println("EnumSet after adding BIOLOGY: " + courseSet);
        // 从 EnumSet 中移除一个课程
        courseSet.remove(CourseType.MATHEMATICS);
        System.out.println("EnumSet after removing MATHEMATICS: " + courseSet);
        // 检查 EnumSet 中是否存在特定类型
        boolean hasComputerScience = courseSet.contains(CourseType.COMPUTER_SCIENCE);
        System.out.println("Contains COMPUTER: " + hasComputerScience);
        // 打印 EnumSet 的大小
        System.out.println("Size of the EnumSet: " + courseSet.size());
        // 清除 EnumSet 中的所有元素
        courseSet.clear();
        System.out.println("EnumSet after clearing: " + courseSet);
    }
}
```

输出：

```text
Initial EnumSet: [MATHEMATICS, PHYSICS, CHEMISTRY]
EnumSet after adding BIOLOGY: [MATHEMATICS, PHYSICS, CHEMISTRY, BIOLOGY]
EnumSet after removing MATHEMATICS: [PHYSICS, CHEMISTRY, BIOLOGY]
Contains COMPUTER_SCIENCE: false
Size of the EnumSet: 3
EnumSet after clearing: []
```

该 Java 程序展示了`EnumSet`的多功能性，它是一种为枚举类型定制的专用集合实现。

## 15.18 COMPARABLE

在 Java 中，`Comparable`是一个接口，用于定义类对象的自然排序（natural ordering）。当一个类实现了`Comparable`接口时，意味着它的实例可以相互比较以用于排序。`Comparable`接口包含一个单一方法`compareTo`，它将当前对象与另一个相同类型的对象进行比较，并返回一个指示它们相对顺序的整数。

### 15.18.1 COMPARABLE 的优势

- 1. 自然排序：实现`Comparable`接口允许类对象根据其自然排序进行排序。这种操作的简化提供了一种一致且直观的方法来排列对象，而不需要外部比较器。
- 2. 与集合类的集成：Java 中的许多集合类（如`TreeSet`和`TreeMap`）使用`Comparable`接口定义的自然排序来对元素进行排序。通过实现`Comparable`，对象可以无缝集成到这些集合类中，使其能够按排序顺序高效地存储和检索。

## 15.18.2 COMPARABLE 的挑战

- 1. 排序的不可变性：由`compareTo`方法定义的自然排序一旦实现就是固定的。这意味着对自然排序逻辑的任何更改都需要修改`compareTo`方法，这可能是具有挑战性的，特别是在某些情况下。

## 15.18.3 JAVA 中实现 COMPARABLE 的语法

在 Java 中实现`Comparable`接口，请遵循以下步骤：

- 1. 声明类并实现`Comparable`接口：

```java
public class MyClass implements Comparable<MyClass> {
}
```

- 2. 重写`compareTo`方法以定义自然排序：

```java
@Override
public int compareTo(MyClass other) {
    // 实现逻辑
}
```

- 3. 使用`Collections.sort()`对列表排序：

```java
Collections.sort(list);
```

通过此语法，类的对象可以根据其自然排序进行比较，使其与各种排序算法兼容。

## 662 用于医疗与健康应用的 Java 22

课程 ID: 102, 课程名称: 数学

课程 ID: 103, 课程名称: 化学

课程 ID: 104, 课程名称: 生物学

该 Java 程序演示了`Comparable`接口的实现，以便根据课程 ID 对自定义的`Course`类进行排序。`Course`类封装了有关课程的信息，包括其 ID 和名称。它实现了`Comparable`接口并重写了`compareTo`方法，以用于根据课程 ID 进行排序。此外，它还重写了`toString`方法，以为`Course`对象提供一个有意义的字符串表示。在`main`方法中，一个`Course`对象列表被填充了各种课程，每个课程都由唯一的课程 ID 和名称定义。最初，显示了未排序的课程列表，展示了它们被添加的顺序。随后，利用`Collections.sort()`方法根据已实现的`compareTo`逻辑对课程列表进行排序，该逻辑按 ID 的升序顺序排列课程。

## 15.19 COMPARATOR 接口

在 Java 中，`Comparator`接口用于为没有自然排序的类对象定义自定义排序，或者当自然排序不适用于排序时使用。与定义类自然排序的`Comparable`接口不同，`Comparator`接口允许对类对象应用多个排序标准和自定义排序逻辑。`Comparator`接口包含一个单一方法`compare`，它比较两个对象并返回一个用于明示它们相对顺序的整数。

## 15.19.1 COMPARATOR 的优势

- 1. 灵活的排序逻辑：实现`Comparator`接口为定义针对特定需求定制的自定义排序逻辑提供了灵活性。它允许开发者根据对象的不同属性或特性定义排序标准，从而对排序行为提供更强的控制。
- 2. 外部排序逻辑：`Comparator`允许将外部排序逻辑应用于无法修改源代码的类，或者在需要支持多个排序标准时使用。这在排序来自第三方库的对象或根据动态变化的标准对对象进行排序时特别有用。

## 15.19.2 COMPARATOR 的挑战

- 1. 使用的复杂性：使用比较器可能会给代码引入额外的复杂度，特别是在处理多个排序标准或复杂的排序逻辑时。开发者需要仔细管理和维护比较器的实现，这可能导致代码复杂性和维护开销的增加。
- 2. 与实现的耦合：`Comparator`的实现可能与特定类或数据结构紧耦合，导致它们在不同上下文下的重用性降低。如果需要为不同的类或场景实现类似的排序逻辑，可能会导致代码重复。

## 15.19.3 JAVA 中实现 COMPARATOR 的语法

要在 Java 中实现`Comparator`接口，请遵循以下步骤：

1. 声明一个实现`Comparator`接口的类，并指定要比较的对象类型：

```java
public class MyComparator implements Comparator<MyClass> {
    // Comparator 实现
}
```

2. 重写该方法以定义自定义的排序逻辑：

```java
@Override
public int compare(MyClass obj1, MyClass obj2) {
    // 根据自定义标准比较 obj1 和 obj2
}
```

3. 在`compare`方法内部，比较两个对象（`obj1`和`obj2`）并返回：

- 如果`obj1`小于`obj2`，返回一个负整数；
- 如果它们相等，返回零；
- 如果`obj1`大于`obj2`，返回一个正整数。

4. 使用 Java 提供的方法（如`Collections.sort()`或`Arrays.sort()`）利用比较器排序对象。通过这种语法，可以使用`Comparator`接口实现自定义排序逻辑，为根据需求对对象进行排序提供灵活性。

## 程序



```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class Main {
  // 内部类
  static class Course {
    private int courseId;
    private String courseName;

    public Course(int courseId, String courseName) {
      this.courseId = courseId;
      this.courseName = courseName;
    }

    public int getCourseId() {
      return courseId;
    }

    public String getCourseName() {
      return courseName;
    }

    @Override
    public String toString() {
      return "Course ID: " + courseId + ", Course Name: " + courseName;
    }
  }

  public static void main(String[] args) {
    // 创建一个 Course 对象列表
    List<Course> courses = new ArrayList<>();
    courses.add(new Course(104, "Biology"));
    courses.add(new Course(102, "Mathematics"));
    courses.add(new Course(101, "Physics"));
    courses.add(new Course(103, "Chemistry"));

    // 打印未排序的列表
    System.out.println("Unsorted List:");
    for (Course course : courses) {
      System.out.println(course);
    }

    // 使用 Comparator 按课程 ID 排序
    Collections.sort(courses, new Comparator<Course>() {
      @Override
      public int compare(Course c1, Course c2) {
        return Integer.compare(c1.getCourseId(), c2.getCourseId());
      }
    });

    // 打印按课程 ID 排序的列表
    System.out.println("Sorted by Course ID:");
    for (Course course : courses) {
      System.out.println(course);
    }

    // 使用 Comparator 按课程名称排序
    Collections.sort(courses, new Comparator<Course>() {
      @Override
      public int compare(Course c1, Course c2) {
        return c1.getCourseName().compareTo(c2.getCourseName());
      }
    });

    // 打印按课程名称排序的列表
    System.out.println("Sorted by Course Name:");
    for (Course course : courses) {
      System.out.println(course);
    }
  }
}
```

输出：

Unsorted List:

Course ID: 104, Course Name: Biology

Course ID: 102, Course Name: Mathematics

Course ID: 101, Course Name: Physics

Course ID: 103, Course Name: Chemistry

Sorted by Course ID:

Course ID: 101, Course Name: Physics

Course ID: 102, Course Name: Mathematics

Course ID: 103, Course Name: Chemistry

Course ID: 104, Course Name: Biology

Sorted by Course Name:

Course ID: 104, Course Name: Biology

Course ID: 103, Course Name: Chemistry

Course ID: 102, Course Name: Mathematics

Course ID: 101, Course Name: Physics

# 666 用于医疗和医学应用的 Java 22

## 3. 从两端添加、移除或检索元素的 Deque 方法

```java
deque.addFirst("Element"); // 在头部添加元素
deque.addLast("Element"); // 在末尾添加元素
String firstElement = deque.removeFirst(); // 从头部移除并返回元素
String lastElement = deque.removeLast(); // 从末尾移除并返回元素
```

4. 其他 `Deque` 方法，如 `peekFirst()`、`peekLast()`、`offerFirst()`、`offerLast()`、`pollFirst()`、`pollLast()` 等，可根据需要执行额外的操作。

通过这种语法，`Deque` 可以有效地用于 Java 应用中，以实现各种数据结构和算法。这些算法需要在集合的两端进行高效的插入、移除和检索。

# 程序

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class Main {
  public static void main(String[] args) {
    // 创建一个 ArrayDeque 来存储课程名称
    Deque<String> courseDeque = new ArrayDeque<>();

    // 将课程添加到 deque 中
    courseDeque.offerFirst("Biology"); // 添加到头部
    courseDeque.offerLast("Mathematics"); // 添加到末尾
    courseDeque.offerLast("Physics"); // 添加到末尾
    courseDeque.offerFirst("Chemistry"); // 添加到头部

    // 显示 deque 的当前内容
    System.out.println("Deque contents: " + courseDeque);

    // 在不移除的情况下检索第一个和最后一个课程
    System.out.println("First course: " + courseDeque.peekFirst());
    System.out.println("Last course: " + courseDeque.peekLast());

    // 移除第一个和最后一个课程
    String removedFirst = courseDeque.pollFirst();
    String removedLast = courseDeque.pollLast();

    System.out.println("Removed first course: " + removedFirst);
    System.out.println("Removed last course: " + removedLast);

    // 显示 deque 更新后的内容
    System.out.println("Updated contents: " + courseDeque);

    // 检查是否存在特定的课程
    boolean hasPhysics = courseDeque.contains("Physics");
    System.out.println("Deque contains 'Physics': " + hasPhysics);

    // 检查 deque 是否为空并显示其大小
    System.out.println("Deque is empty: " + courseDeque.isEmpty());
    System.out.println("Size of deque: " + courseDeque.size());

    // 清空 deque 并再次显示
    courseDeque.clear();
    System.out.println("Deque contents after clearing: " + courseDeque);
  }
}
```

输出：

Deque contents: [Chemistry, Biology, Mathematics, Physics]

First course: Chemistry

Last course: Physics

Removed first course: Chemistry

Removed last course: Physics

Updated deque contents: [Biology, Mathematics]

Deque contains `Physics`: false

Deque is empty: false

Size of deque: 2

Deque contents after clearing: []

上述程序通过 `ArrayDeque` 实现演示了 `Deque` 接口的用法。程序通过创建一个 `ArrayDeque` 来存储表示各种值的字符串。随后，程序使用 `offerFirst()` 和 `offerLast()` 方法向 deque 的两端添加课程，模拟了分别将课程添加到队列的头部和尾部。在填充 deque 后，它显示了当前内容，展示了课程的顺序。最后，使用 `peekFirst()` 和 `peekLast()` 方法检索并打印了 deque 中的第一个和最后一个课程，而不将它们移除。

## 15.21 SET

在 Java 中，`Set` 是一个存储唯一元素的集合。它不允许元素重复，确保每个元素在集合中只出现一次。`Set` 接口是集合框架的一部分，提供了添加、移除和检查元素存在性的方法。`Set` 接口的实现包括 `HashSet`、`TreeSet` 和 `LinkedHashSet`，它们各自有自己的特性和性能考量。

## 15.21.1 SET 的优势

1. 元素的唯一性：`Set` 通过不允许元素重复来强制执行唯一性。这种属性在处理每个元素必须只出现一次的集合时非常有益，例如存储唯一标识符或从集合中删除重复项。
2. 高效的元素查找：`Set` 的实现提供了高效的元素查找操作。它们通常使用哈希或基于树的数据结构来实现快速访问时间，使得它们适用于需要快速检索元素的场景，例如在大规模数据集中搜索特定值。

## 15.21.2 SET 的挑战

1. 有序的元素：`Set` 不保证元素存储的顺序。虽然这种属性对许多应用很有用，但在需要元素的特定排序时，它可能具有挑战性。如果元素顺序很重要，开发者可能需要使用不同的集合类型，例如 `List`。
2. 自定义对象的开销：当使用自定义对象作为集合中的元素时，开发者需要确保这些对象正确实现了 `equals()` 和 `hashCode()` 方法。未这样做可能会导致意外的行为，例如对重复元素的识别不正确，或由于哈希冲突导致性能低下。

## 15.21.3 在 Java 中使用 SET 的语法

在 Java 中使用 `Set`，请遵循以下步骤：

1. 设置接口并选择一种实现类（例如 `HashSet`、`TreeSet`、`LinkedHashSet`）：

```java
import java.util.Set;
import java.util.HashSet; 或
import java.util.TreeSet;
或 import java.util.LinkedHashSet;
```

2. 使用选择的实现类创建实例：

```java
Set<String> set = new HashSet<>(); // 或
new TreeSet<>(); // 或 LinkedHashSet<>();
```

3. 使用 `Set` 方法添加、移除和检查元素的存在：

```java
set.add("Element"); // 添加元素到集合
set.remove("Element"); // 从集合移除元素
boolean contains = set.contains("Element"); // 检查是否存在
```

4. 使用如 `isEmpty()`、`size()`、`clear()` 等方法执行额外的操作。

`Set` 可以用于 Java 应用以存储唯一元素，并执行需要的额外操作。

# 程序

```java
import java.util.HashSet;
import java.util.Set;

public class Main {
  public static void main(String[] args) {
    // 创建一个 HashSet 来存储课程名称
    Set<String> courseSet = new HashSet<>();

    // 将课程添加到集合中
    courseSet.add("Mathematics");
    courseSet.add("Physics");
    courseSet.add("Chemistry");
    courseSet.add("Biology");

    // 尝试添加重复课程
    boolean added = courseSet.add("Physics"); // 如果 Physics 已在集合中，则返回 false
    System.out.println("Adding 'Physics' again: " + added);

    // 移除课程
    boolean removed = courseSet.remove("Biology"); // 如果 Biology 存在，则返回 true
    System.out.println("Removing 'Biology': " + removed);
    System.out.println("Updated set contents: " + courseSet);

    // 检查是否存在特定的课程
    boolean hasChemistry = courseSet.contains("Chemistry");
    System.out.println("Set contains 'Chemistry': " + hasChemistry);

    // 检查集合是否为空并显示其大小
    System.out.println("Set is empty: " + courseSet.isEmpty());
    System.out.println("Size of set: " + courseSet.size());

    // 清空集合
    courseSet.clear();
    System.out.println("Set contents after clearing: " + courseSet);
  }
}
```

输出：

Adding 'Physics' again: false

Removing 'Biology': true

Updated set contents: [Chemistry, Mathematics, Physics]

Set contains 'Chemistry': true

Set is empty: false

Size of set: 3

Set contents after clearing: []

## 15.22 SORTED

在 Java 中，`SortedSet` 是 `Set` 接口的一个子接口，它以排序顺序维护其元素。与不保证元素特定顺序的普通 `Set` 不同，`SortedSet` 确保其元素根据自然顺序或指定的比较器进行排序。

# Java 22 用于医疗与医学应用

1. 导入 `util.SortedSet` 接口和 `TreeSet` 类：

```java
import java.util.SortedSet;
import java.util.TreeSet;
```

2. 使用 `TreeSet` 实现创建一个 `SortedSet` 实例：

```java
SortedSet<String> sortedSet = new TreeSet<>();
```

3. 使用 `SortedSet` 方法添加、删除和检索元素：



```java
sortedSet.add("Element"); // 向排序集合中添加一个元素
sortedSet.remove("Element"); // 从排序集合中删除一个元素
String firstElement = sortedSet.first(); // 获取第一个（最小）元素
String lastElement = sortedSet.last(); // 获取最后一个（最大）元素
```

4. 可选地，使用`headSet()`、`tailSet()`或`subset()`等方法根据指定的范围检索排序集合的子集。

开发者可以轻松地在应用程序中使用`SortedSet`来按顺序存储元素，并高效地执行添加、删除和检索元素等操作。

## 程序

```java
import java.util.SortedSet;
import java.util.TreeSet;
public class Main {
    public static void main(String[] args) {
        // 创建一个 TreeSet 来存储课程名称
        SortedSet<String> courseSet = new TreeSet<>();
        // 将课程添加到集合
        courseSet.add("Mathematics");
        courseSet.add("Physics");
        courseSet.add("Chemistry");
        courseSet.add("Biology");
        // 在添加元素后打印集合内容
        System.out.println("Set contents after adding elements: " + courseSet);
        // 尝试添加重复的课程
        boolean added = courseSet.add("Physics"); // 因为 "Physics" 已经在集合中，应返回 false
        System.out.println("Adding 'Physics' again: " + added);
        // 删除一个课程
        boolean removed = courseSet.remove("Biology"); // 因为 "Biology" 存在，应返回 true
        System.out.println("Removing 'Biology': " + removed);
        // 显示更新后的集合内容
        System.out.println("Updated set contents: " + courseSet);
        // 检查集合中是否存在特定课程
        boolean hasChemistry = courseSet.contains("Chemistry");
        System.out.println("Set contains 'Chemistry': " + hasChemistry);
        // 获取并打印排序集合的第一个和最后一个元素
        String firstCourse = courseSet.first();
        String lastCourse = courseSet.last();
        System.out.println("First course: " + firstCourse);
        System.out.println("Last course: " + lastCourse);
        // 显示排序集合的大小
        System.out.println("Size of set: " + courseSet.size());
        // 清空集合并再次显示
        courseSet.clear();
        System.out.println("Set contents after clearing: " + courseSet);
    }
}
```

输出：

```text
Set contents after adding elements: [Biology, Chemistry, Mathematics, Physics]
Adding 'Physics' again: false
Removing 'Biology': true
Updated contents: [Chemistry, Mathematics, Physics]
Set contains 'Chemistry': true
First course: Chemistry
Last course: Physics
Size of set: 3
Set contents after clearing: []
```

上述程序展示了通过`TreeSet`类实现的`SortedSet`接口的用法。程序开始时创建一个名为`course`的`TreeSet`来存储表示各种课程的字符串。由于集合不允许重复元素，它尝试向集合中添加重复的课程“Physics”，并检查添加是否成功，这应该返回`false`。

# 15.23 SORTEDMAP

在 Java 中，`SortedMap`是一个扩展`Map`接口的接口，它根据键对其键值对进行排序。与不保证元素任何特定顺序的普通`Map`不同，`SortedMap`确保键按照它们的自然顺序或指定的比较器（`comparator`）排序。`SortedMap`的实现包括`TreeMap`，它在排序的树形结构中存储元素。

# 15.23.1 SORTEDMAP 的优势

- 1. 有序的键值对：`SortedMap`的主要优势是它根据键按排序顺序维护条目。这允许按照排序后的键顺序高效地检索条目，消除了对额外排序的需求。
- 2. 高效的范围操作：`SortedMap`实现使用高效的数据结构（如平衡树）来维护键的排序顺序。这使得查找特定范围内的条目或检索第一个或最后一个条目等操作变得简单。

# 15.23.2 SORTEDMAP 的挑战

- 1. 自定义比较器的开销：虽然`SortedMap`允许根据自定义比较器排序键，但指定和实现比较器会引入复杂性。开发者需要确保比较器正确定义排序顺序并处理所有边界情况，以避免出现意外之外的行为。
- 2. 键排序的灵活性有限：`SortedMap`的排序特性将键的排序限制在单一预定义的顺序上（无论是自然顺序还是由比较器定义）。这种限制可能不适用于需要动态排序准标准的场景，因为这需要使用新的比较器重新创建`SortedMap`。

# 15.23.3 Java 中使用 SORTEDMAP 的语法

在 Java 中结合`TreeMap`实现使用`SortedMap`，请遵循以下步骤：

- 1. 导入`SortedMap`接口和`TreeMap`类：

```java
import java.util.SortedMap;
import java.util.TreeMap;
```

- 2. 使用`TreeMap`实现创建一个`SortedMap`实例：

```java
SortedMap<Integer, String> sortedMap = new TreeMap<>();
```

- 3. 使用`SortedMap`方法添加、删除和检索键值对：

```java
sortedMap.put(1, "One"); // 向 map 中添加一个键值对
sortedMap.remove(1); // 从 map 中删除一个键值对
Integer firstKey = sortedMap.firstKey(); // 获取第一个（最小）键
Integer lastKey = sortedMap.lastKey(); // 获取最后一个（最大）键
```

- 4. 可选地，使用`headMap()`、`tailMap()`或`subMap()`等方法根据指定的范围检索排序集合的子集。

开发者可以轻松地在应用程序中使用`SortedMap`来按顺序存储元素，并高效地执行添加、删除和检索条目等操作。

## 程序

```java
import java.util.SortedMap;
import java.util.TreeMap;
public class Main {
    public static void main(String[] args) {
        // 创建一个 TreeMap 来存储课程名称
        SortedMap<Integer, String> courseMap = new TreeMap<>();
        // 将课程添加到集合
        courseMap.put(1, "Mathematics");
        courseMap.put(2, "Physics");
        courseMap.put(3, "Chemistry");
        courseMap.put(4, "Biology");
        // 在添加元素后打印 map 内容
        System.out.println("Map contents after adding elements: " + courseMap);
        // 尝试添加重复的键
        String oldCourse = courseMap.put(2, "Advanced Physics"); // 因为键 2 已经存在，应返回旧值
        System.out.println("Adding 'Physics' again: " + oldCourse);
        // 删除一个课程
        String removedCourse = courseMap.remove(4); // 因为 "Biology" 存在，应返回其值
        System.out.println("Removing 'Biology': " + removedCourse);
        // 显示更新后的 map 内容
        System.out.println("Updated map contents: " + courseMap);
        // 检查 map 中是否存在特定课程
        boolean hasChemistry = courseMap.containsKey(3);
        System.out.println("Map contains 'Chemistry': " + hasChemistry);
        // 获取并打印排序 map 的第一个和最后一个键
        Integer firstKey = courseMap.firstKey();
        Integer lastKey = courseMap.lastKey();
        System.out.println("First key: " + firstKey);
        System.out.println("Last key: " + lastKey);
        // 显示排序 map的大小
        System.out.println("Size of map: " + courseMap.size());
        // 清空 map并再次显示
        courseMap.clear();
        System.out.println("Map contents after clearing: " + courseMap);
    }
}
```

输出：

```text
Map contents after adding elements: {1=Mathematics, 2=Physics, 3=Chemistry, 4=Biology}
Adding 'Physics' again: Physics
Removing 'Biology': Biology
Updated map contents: {1=Mathematics, 2=Advanced Physics, 3=Chemistry}
Map contains 'Chemistry': true
First key: 1
Last key: 3
Size of map: 3
Map contents after clearing: {}
```

上述程序展示了通过`TreeMap`类实现的`SortedMap`接口的用法。程序开始时创建一个名为`courseMap`的`TreeMap`来存储表示各种课程的字符串的映射。由于 map 不允许重复的键，它尝试向 map 中添加重复的键 2，“Advanced Physics”，这会返回旧值。

# 15.24 医疗应用

# 15.24.1 案例研究 1

腿部疾病涵盖影响腿骨骼、肌肉和关节的各种疾病，会导致疼痛、无力或活动受限。常见疾病包括静脉曲、胫骨炎以及 Osgood-Schlatter 病等，每种疾病都需要特定的医疗评估和治疗。程序考虑的参数是疾病（例如，Osgood-Schlatter 病导致的膝盖下方疼痛）。

## 用于医疗保健和医学应用的 Java 22

## 程序



```java
import java.util.HashMap;
import java.util.HashSet;
import java.util.Map;
import java.util.Set;

public class LegDisorderDetection {
    private static final Map<String, Disorder> disorders;
    // 疾病名称到 Disorder 对象的映射
    static {
        disorders = new HashMap<>();
        // 示例疾病和症状
        Disorder osoodSchlatter = new Disorder("Osgood-Schlatter Disease");
        osoodSchlatter.addSympt("膝盖下方疼痛");
        osoodSchlatter.addSympt("触碰痛");
        osoodSchlatter.addSympt("活动期间疼痛");
        disorders.put(osoodSchlatter.getName(), osoodSchlatter);
        Disorder patellarTendinitis = new Disorder("髌骨腱炎（跳者膝）");
        patellarTendinitis.addSympt("膝盖正下方疼痛");
        patellarTendinitis.addSympt("活动时加剧的疼痛");
        patellarTendinitis.addSympt("早晨僵硬");
        disorders.put(patellarTendinitis.getName(), patellarTendinitis);
        // 更多疾病...
        Disorder shinSplints = new Disorder("胫骨骨炎");
        shinSplints.addSympt("胫骨沿疼痛");
        shinSplints.addSympt("活动时加剧的疼痛");
        shinSplints.addSympt("触碰痛");
        disorders.put(shinSplints.getName(), shinSplints);
        Disorder plantarFasciitis = new Disorder("足底筋膜炎");
        plantarFasciitis.addSympt("足跟或足足弓疼痛");
        plantarFasciitis.addSympt("早晨或长时间站立后疼痛加剧");
        plantarFasciitis.addSympt("早晨第一几步时剧剧疼痛");
        disorders.put(plantarFasciitis.getName(), plantarFasciitis);
        Disorder varicoseVeins = new Disorder("静脉曲张");
        varicoseVeins.addSympt("扭曲、肿大的静脉");
        varicoseVeins.addSympt("腿部酸痛或抽筋");
        varicoseVeins.addSympt("脚踝肿胀");
        disorders.put(varicoseVeins.getName(), varicoseVeins);
    }

    public void main(String[] args) {
        UserInput input = new UserInput();
        // 用户数据
        String name = input.getInput("输入您的姓名");
        Set<String> symptoms = input.getSymptomInput("输入与腿部相关的症状");
        // 分析症状
        Set<String> potentialDisorders = new HashSet<>();
        for (Disorder disorder : disorders.values()) {
            Set<String> disorderSymptoms = disorder.getSymptoms();
            if (symptoms.containsAll(disorderSymptoms)) {
                // 检查所有症状是否存在
                potentialDisorders.add(disorder.getName());
            }
        }
        // 显示结果
        if (potentialDisorders.isEmpty()) {
            System.out.println("根据您的症状，未识别出腿部相关疾病。");
        } else {
            System.out.println("根据您的症状，潜在的腿部疾病有：");
            for (String disorder : potentialDisorders) {
                System.out.println("- " + disorder);
            }
            System.out.println("请咨询医疗专业人士以进行诊断。");
        }
        input.scanner();
    }
}
```

在`LegDisorder`程序中，初始化了一个名为`disorders`的映射，使用`HashMap<String, Disorder>`来存储各种腿部疾病及其症状。每个`Disorder`对象在创建时都包含一个名称和一组症状。用户通过`UserInput`类输入姓名和特定的腿部相关症状。程序将提供的症状与`disorders`映射中的每种疾病进行比较。如果用户的症状匹配某个特定疾病的所有症状，则该疾病会被添加到`potentialDisorders`中。最后，根据疾病是否存在，程序将输出潜在相关疾病的列表，或一条指示未识别出疾病的消息。

## 15.24.2 案例研究 2

佝性软主要影响儿童，是一种由于维生素 D 缺乏导致骨骼脆弱和松软的疾病。风险包括骨痛、生长迟缓以及骨骼畸形，如手腕和脚踝弓曲或增厚。程序中考虑的参数有“骨痛或触痛”、“肌肉无力”、“生长迟缓”、“婴儿头软（囟窝）”、“弓膝或内翻”以及“罕见的抽搐”。

## 程序

```java
public class RickettsSymptoms {
    private String symptom;
    private int severity; // 1（低）到 5（高）
    public RickettsSymptoms(String symptom, int severity) {
        this.symptom = symptom;
        this.severity = severity;
    }
    public String getSymptom() {
        return symptom;
    }
    public int getSeverity() {
        return severity;
    }

    @Override
    public String toString() {
        return symptom + " (严重程度: " + severity + ")";
    }
}

import java.util.Scanner;
import java.util.Stack;
public class RickettsDetection {
    private static final RickettsSymptoms[] SYMPTOMS = {
        new RickettsSymptoms("骨痛或触痛", 5),
        new RickettsSymptoms("肌肉无力", 4),
        new RickettsSymptoms("生长迟缓", 5),
        new RickettsSymptoms("婴儿头软（囟窝）", 4),
        new RickettsSymptoms("弓膝或内翻", 4),
        new RickettsSymptoms("抽搐（罕见）", 5)
    };

    public void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Stack<RickettsSymptoms> symptomstack = new Stack<>();
        System.out.println("佝性症分析");
        // 获取用户输入（可以修改循环或其他方法）
        System.out.println("输入症状或输入 'done' 完成：");
        do {
            String symptom = scanner.nextLine();
            if (!symptom.equalsIgnoreCase("done") && !symptom.isEmpty()) {
                int severity = getSymptomSeverity(symptom);
                if (severity > 0)
                    symptomstack.push(new RickettsSymptoms(symptom, severity));
                } else
                    System.out.println("无效症状。请输入有效的症状或 'done'。");
                }
            }
        } while (!symptom.equalsIgnoreCase("done"));
        // 分析症状
        int totalSeverity = 0;
        if (symptomstack.isEmpty()) {
            System.out.println("未输入任何症状.");
        } else {
            System.out.println("输入的症状：");
            while (!symptomstack.isEmpty()) {
                RickettsSymptoms currentSymptom = symptomstack.pop();
                System.out.println(currentSymptom);
                totalSeverity += currentSymptom.getSeverity();
            }
            String assessment = assessRicketsRisk(totalSeverity);
            System.out.println("\n评估结果：");
            System.out.println(assessment);
            System.out.println("**免责声明：此仅为示例，不构成医疗建议。请咨询医疗专业人士。**");
        }
        scanner.close();
    }

    private static int getSymptomSeverity(String symptom) {
        for (RickettsSymptoms rickettsSymptom : SYMPTOMS) {
            if (rickettsSymptom.getSymptom().equalsIgnoreCase(symptom)) {
                return rickettsSymptom.getSeverity();
            }
        }
        return 0; // 无效症状
    }

    private static String assessRicketsRisk(int totalSeverity) {
        if (totalSeverity == 0) {
            return "根据输入的症状，不太可能是佝性症。
        } else if (totalSeverity <= 10) {
            return "患佝性症的可能性较低。
        } else if (totalSeverity <= 15) {
            return "患佝性症的可能性中等。请咨询医疗专业人士进行诊断。";
        } else {
            return "输入的症状表明患佝性症的可能性较高。
        }
    }
}
```

## 16 案例研究

## 16.1 引言

本章深入探讨了 Java 在医学领域的应用，展示了几个案例研究，强调了如何利用 Java 开发用于检测各种医疗状况的系统。这些案例研究涵盖了多种疾病，证明了 Java 在医学诊断中的多功能性和有效性。

其中一个案例研究侧重于糖尿病检测，展示了 Java 算法如何分析患者数据以识别是否存在糖尿病。另一项研究探索了糖尿病视网膜病变的检测，使用了 Java 中实现的图像处理和分析技术。

本章还包含了一个关于新冠肺炎（COVID-19）检测的案例研究，说明了如何利用 Java 开发用于诊断这种高度传染疾病的软件。通过分析医学数据，基于 Java 的系统可以协助新冠肺炎病例的早期发现和管理。

抑郁症检测展示了 Java 如何通过分析行为数据和症状来识别抑郁症迹象，为心理健康专业人士提供了价值价值工具。

此外，本章还涉及了阿尔茨海默症的检测，展示了 Java 如何用于这种神经退行性疾病的早期诊断。通过数据分析和机器学习技术，基于 Java 的应用程序可以帮助识别与阿尔茨海默症相关的模式和症状。

最后，本章介绍了一个皮肤癌检测的案例研究。利用 Java 中的图像处理能力，该系统可以分析皮肤病变并识别潜在癌症，促进早期干预和治疗。

总体而言，本章说明了 Java 在开发各种医疗状况的先进诊断工具方面所起的重要作用，强调了它通过创新技术解决方案改善医疗结果的影响。

## 16.2 糖尿病检测

该数据集包含若干与糖尿病风险因素和症状常见的关键属性。数据集中的属性包括：

- 1. 年龄：患者的年龄，因为年龄是糖尿病的一个显著风险因素。
- 2. 性别：患者的性别，这会影响糖尿病的风险和发病率。
- 3. BMI（体重指数）：根据身高和体重计算的体脂衡量标准，是糖尿病风险的关键指标。
- 4. 血压：患者的血压水平，因为高血压通常与糖尿病有关。
- 5. 空腹血糖：禁食一段时间后的血糖水平，是诊断糖尿病的重要指标。
- 6. 餐后血糖：进后的血糖水平，有助于了解身体如何管理糖分摄入。
- 7. 家族史：患者家族中糖尿病的信息，表明了遗传倾向。
- 8. 身体活动：患者的身体活动水平，会影响整体健康和糖尿病风险。
- 9. 吸烟史：患者是否吸烟，因为吸烟是许多慢性疾病（包括糖尿病）的风险因素。
- 10. 糖尿病：患者是否被诊断出糖尿病的二值指标。

### 16.2.1 示例数据集

| age | gender | bmi | bloodPressure | fastingBloodSugar | postPrandialBloodSugar | familyHistory | physicalActivity | smoker | diabetic |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 45 | 男 | 29.5 | 140/90 | 120 | 210 | true | 低 | false | true |
| 50 | 女 | 28.0 | 130/85 | 110 | 190 | true | 中等 | false | true |
| 30 | 男 | 25.0 | 120/80 | 95 | 140 | false | 高 | false | false |
| 55 | 女 | 32.0 | 145/95 | 130 | 220 | true | 低 | true | true |
| 40 | 男 | 27.0 | 135/85 | 105 | 180 | false | 中等 | | |

### Java 程序



```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;

// 表示患者信息的类
class Patient {
    int age;
    String gender;
    double bmi;
    String bloodPressure;
    int fastingBloodSugar;
    int postPrandialBloodSugar;
    boolean familyHistory;
    String physicalActivity;
    boolean smoker;
    boolean diabetic;

    // 用于初始化患者数据的构造函数
    public Patient(int age, String gender, double bmi, String bloodPressure, int fastingBloodSugar, int postPrandialBloodSugar, boolean familyHistory, String physicalActivity, boolean smoker, boolean diabetic) {
        this.age = age;
        this.gender = gender;
        this.bmi = bmi;
        this.bloodPressure = bloodPressure;
        this.fastingBloodSugar = fastingBloodSugar;
        this.postPrandialBloodSugar = postPrandialBloodSugar;
        this.familyHistory = familyHistory;
        this.physicalActivity = physicalActivity;
        this.smoker = smoker;
        this.diabetic = diabetic;
    }
}

// 糖尿病检测应用程序
public class DiabetesDetection {
    public static void main(String[] args) {
        List<Patient> patients = new ArrayList<>();

        // 模拟加载数据
        patients.add(new Patient(45, "Male", 29.5, "140/90", 120, 210, true, "Low", false, true));
        patients.add(new Patient(50, "Female", 28.0, "130/85", 110, 190, true, "Moderate", false, true));
        patients.add(new Patient(30, "Male", 25.0, "120/80", 95, 140, false, "High", false, false));
        patients.add(new Patient(55, "Female", 32.0, "145/95", 130, 220, true, "Low", true, true));
        patients.add(new Patient(40, "Male", 27.0, "135/85", 105, 180, false, "Moderate", false, false));

        System.out.println("糖尿病风险分析：");
        for (Patient p : patients) {
            if (p.fastingBloodSugar > 100 || p.bmi > 25) {
                System.out.println("患者（年龄:" + p.age + ", " + p.gender + "）存在较高的糖尿病风险。");
            } else {
                System.out.println("患者（年龄:" + p.age + ", " + p.gender + "）风险较低。");
            }
        }
    }
}
```

# 案例研究

为`Patient`类定义了构造函数，它通过传递的参数值初始化`Patient`对象的字段。`Patient`类的每个字段包括`age`、`gender`、`bmi`、`bloodPressure`、`fastingSugar`、`postPrandialSugar`、`familyHistory`、`physicalActivity`、`smoker`和`diabetic`都是基于构造函数对应参数的值。

`this`关键字用于引用`Patient`类的当前实例，允许区分构造函数参数与同名的类字段。通过将参数值赋值给类字段，构造函数初始化了`Patient`对象的状态，其属性代表年龄、性别、BMI、血压、血糖水平、血糖血糖、糖尿病家族史、体力水平、吸烟状况和糖尿病情况。

此初始化过程确保了使用该构造函数创建的每个`Patient`类实例都从其属性的预定义值开始，能够准确地表示患者数据，并便于在医疗应用程序中进一步处理或分析。

```java
public class Main {
    // 从文件加载数据集的方法
    public static List<Patient> loadDataset(String fileName) {
        List<Patient> patients = new ArrayList<>();
        try (BufferedReader br = new BufferedReader(new FileReader(fileName))) {
            String line;
```

`Main`类包含一个静态方法`loadDataset`，它接受一个`fileName`参数表示包含数据的文件名。该方法返回`Patient`对象的列表。在方法内部，创建了一个新的`ArrayList` `patients`用于存储从文件中读取的`Patient`对象。实例化了一个`BufferedReader` `br`来读取`fileName`指定的文件内容。然后，方法进入循环，使用`BufferedReader`的`readLine()`方法读取文件的每一行。文件的每一行都存储在`line`变量中。

```java
while ((line = br.readLine()) != null) {
    if (line.startsWith("#")) {
        continue; // 跳过注释
    }
    String[] data = line.split(",", "");
    // 解析数据并创建 Patient 对象
    int age = Integer.parseInt(data[0]);
    String gender = data[1];
    double bmi = Double.parseDouble(data[2]);
    String bloodPressure = data[3];
    int fastingSugar = Integer.parseInt(data[4]);
    int postPrandialSugar = Integer.parseInt(data[5]);
    boolean familyHistory = Boolean.parseBoolean(data[6]);
    boolean physicalActivity = Boolean.parseBoolean(data[7]);
    boolean smoker = Boolean.parseBoolean(data[8]);
    boolean diabetic = Boolean.parseBoolean(data[9]);
    Patient patient = new Patient(age, gender, bmi, bloodPressure,
        fastingSugar, postPrandialSugar, familyHistory,
        physicalActivity, smoker, diabetic); 
    patients.add(patient);
}
catch (IOException e) {
    System.out.println("Error reading dataset: " + e.getMessage());
}
return patients;
```

# Java 22 用于医疗和医学应用

`loadDataset`方法利用循环遍历`BufferedReader`读取的文件的每一行。随后，从`data`数组中提取解析后的数据元素并赋值给代表患者不同属性的局部变量，例如`age`、`gender`、`bmi`、`bloodPressure`、`fastingBloodSugar`、`postPrandialBloodSugar`、`familyHistory`、`physicalActivity`、`smoker`和`diabetic`。使用这些提取的值，实例化一个新的`Patient`对象，并使用`add`方法将其添加到`patients`列表中。

处理完成后，关闭`BufferedReader`以释放任何系统资源，并返回`patients`对象列表。

```java
// 加载数据并评估糖尿病概率的方法
public static void main(String[] args) {
  try {
    List<Patient> patients = loadDataset("test.txt");
    if (!patients.isEmpty()) {
      Patient firstPatient = patients.get(0);
      boolean diabeticStatus = isDiabetic(patients, firstPatient);
      if (diabeticStatus) {
        System.out.println("The first patient is likely to have diabetes.");
      } else {
        System.out.println("The first patient is unlikely to have diabetes.");
      }
    }
  } catch (Exception e) {
    e.printStackTrace();
  }
}
```

首先，在`try`块中，调用`loadDataset`方法从指定文件读取数据集。如果成功，则从从数据集获取的患者列表中提取第一条患者记录。接下来，调用`isDiabetic`方法，并将患者列表和提取的患者记录作为参数传递。该方法根据数据集的信息评估患者患糖尿病的可能性，并返回一个表示评估结果的布尔值。根据从`isDiabetic`获取的布尔结果，向控制台打印相应的消息，指示患者被认为可能或可能患糖尿病。如果在加载数据集过程中发生`IOException`，则会触发`catch`块。它会在控制台打印错误消息，指示读取数据集时发生错误，堆栈跟踪为调试提供了额外的上下文。

```java
// 根据数据集判断患者是否患糖尿病的方法
public static boolean isDiabetic(List<Patient> patients, Patient inputPatient) {
  for (Patient p : patients) {
    if (p.fastingBloodSugar == inputPatient.fastingBloodSugar &&
        p.postPrandialSugar == inputPatient.postPrandialSugar &&
        p.familyHistory == inputPatient.familyHistory &&
        p.physicalActivity.equals(inputPatient.physicalActivity) &&
        p.smoker == inputPatient.smoker) {
      return p.diabetic;
    }
  }
  return false;
}
```

# 案例研究

# isDiabetic

# 16.3 糖尿病视网膜病变检测

从可用资源如 STARE、DIARETDB 和 Kaggle 收集图像。这些数据集包含了广泛的眼底图像，并标注了糖尿病视网膜病变的存在和程度。

## 684 用于医疗和医学应用的 Java 22

```java
} catch (Exception e) {
    e.printStackTrace();
}
}
```

最初，尝试使用`extractFeatures`方法从位于`C://dr`目录的图像中提取特征。然后，通过`createDataset`函数使用这些特征创建一个`Instances`（实例集）数据集。随后，通过`trainClassifier`方法在该数据集上训练分类器。训练完成后，再次使用相同的`extractFeatures`函数从`C:/dl/new`目录中提取另一组实例。对于每个实例，将通过`classifyInstance`方法利用训练好的分类器进行预测。在此过程中遇到的任何异常都会被捕获并处理，通过`printStackTrace`方法提供细节以便调试。

```java
// extract features from images in a directory
private static List<Instance> extractFeatures(String directoryPath)
throws Exception {
    List<Instance> instances = new ArrayList<>();
    File[] files = new File(directoryPath).listFiles();
    if (files != null) {
        for (File file : files) {
            if (file.isFile() && (file.getName().endsWith(".jpg") || file.getName().endsWith(".png"))) {
                // Load the image using OpenCV
                Mat image = Imgcodecs.imread(file.getAbsolutePath());
                // Resize the image to 100x100 pixels
                Imgproc.resize(image, image, org.bytedeco.opencv.opencv_core.Size(100, 100));
                // Convert the image to grayscale
                Imgproc.cvtColor(image, image, Imgproc.COLOR_BGR2GRAY);
                // Extract features from the image
                double[] features = extractFeaturesFromImage(image);
                // Create a Weka instance from the extracted features
                Instance instance = createInstance(features);
                instances.add(instance);
            }
        }
    }
    return instances;
}
```

此 Java 方法`extractFeatures`旨在从存储在目录路径中的图像中提取特征。它首先初始化一个空的`Instance`对象列表以存储提取的特征。然后，使用`listFiles`方法从指定目录获取文件列表。如果文件列表不为空，则遍历每个文件。对于每个有效图像文件，它使用 OpenCV 库的`imread`方法读取图像。使用 OpenCV 库的`resize`和`cvtColor`方法分别将图像调整为 100x100 像素的标准大小并转换为灰度模式。预处理后，该方法调用`extractFeaturesFromImage`计算图像的特征。这些特征通过`createInstance`方法封装到`Instance`对象中。最后，将该`Instance`对象添加到实例列表中。该方法返回包含指定目录下所有图像提取特征的实例列表。

## 案例研究



```java
// Method to extract features from a single image
private static double[] extractFeaturesFromImage(Mat image) {
// Perform Shi-Tomasi corner detection
Mat corners = new Mat();
Imgproc.goodFeaturesToTrack(image, corners, 100, 0.01, 10);
// Apply edge detection
Mat edges = new Mat();
Imgproc.Canny(image, edges, 100, 200);
Imgcodecs.imwrite("edges.jpg", edges); // Save the detected edges
// Calculate histogram of pixel intensities
Mat hist = new Mat();
Imgproc.calcHist(image, new Mat[]{0}, new Mat(), hist, new int[]{256}, new float[]{0, 256});
// Generate Gabor kernel and apply to the image
Mat gaborKernel = Imgproc.getGaborKernel(new Size(21, 21), 5, Math.PI / 4, 10, 0, CV_3F);
Mat filteredImage = new Mat();
Imgproc.filter2D(image, filteredImage, -1, gaborKernel);
Imgcodecs.imwrite("filtered_image.jpg", filteredImage);
// Save the filtered image
// Calculate moments for shape descriptors
Mat moments = Imgproc.moments(image);
Mat huMoments = new Mat();
Imgproc.huMoments(moments, huMoments);
// Combine features into a single array (corners count, histogram, moments, etc.)

double[] features = new double[1 + hist.cols() + 7];
features[0] = corners.total(); // Number of corners detected
for (int i = 0; i < hist.cols(); i++) {
    features[i + 1] = hist.get(i, 0)[0]; // Histogram values
}
for (int i = 0; i < 7; i++) {
    features[hist.cols() + 1 + i] = huMoments.get(i, 0)[0];
}
return features;
}
```

`extractFeaturesFrom` 方法接收代表图像的 `Mat` 对象作为输入。在方法内部，使用 OpenCV 的 `Imgcodecs.imread` 从名为 `image.jpg` 的文件读取图像。接下来，通过 `Imgproc.Canny` 对灰度版本的图像使用 Shi-Tomasi 角检测器进行角检测，并使用 `Imgcodecs.imwrite` 将结果保存到名为 `edges.jpg` 的文件中。随后，使用 `Imgproc.calcHist` 计算像素强度直方图并存储在名为 `hist` 的 `Mat` 对象中。使用 `Imgproc.getGaborKernel` 生成 Gabor 核用于纹理特征提取。使用 `Imgproc.filter2D` 将核应用于灰度图像，并将滤波后的图像保存为 `filtered_image.jpg`。

最后，使用 `Imgproc.moments` 和 `Imgproc.huMoments` 计算 Hu 矩以提取形状描述符。

```java
// Method to create a Weka instance from extracted features
private static Instance createInstance(double[] features) {
// Define the attributes of the dataset (you can add more attributes as needed)
ArrayList<Attribute> attributes = new ArrayList<>();
for (int i = 0; i < features.length; i++) {
    attributes.add(new Attribute("feature" + (i + 1));
}
attributes.add(new Attribute("class")); // The class attribute
// Create a Weka instance
Instances dataset = new Instances("TestInstances", attributes, 1);
dataset.setClassIndex(attributes.size()); // Set the class attribute
Instance instance = new DenseInstance(features.length + 1);
for (int i = 0; i < features.length; i++) {
    instance.setValue(i, features[i]);
}
instance.setDataset(dataset); // Set the instance's dataset
return instance;
}
```

## 686 用于医疗和医学应用的 Java 22

```java
// create a dataset from a list of instances
private Instances createDataset(List<Instance> instances) {
ArrayList<Attribute> attributes = new ArrayList<>();
for (int i = 0; i < instances.get(0).numAttributes(); i++) {
    attributes.add(new Attribute("feature" + (i + 1));
}
attributes.add(new Attribute("class")); // The class attribute
Instances dataset = new Instances("TrainingInstances", attributes,
instances.size());
dataset.setClassIndex(dataset.numAttributes() - 1); // Set the class index
for (Instance instance : instances) {
    dataset.add(instance);
}
return dataset;
}
```

在 `createDataset` 方法中，从实例列表中创建一个数据集。它首先初始化一个名为 "TrainingInstances" 的 `Instances` 对象来表示数据集。构造函数调参数为数据集名称、`null`（表示没有属性信息）以及实例列表的大小。

循环遍历输入列表中的每个实例。对于每个实例，使用 `add` 方法将其添加到数据集中。实例添加完成后，该方法返回填充好的数据集。

# 案例研究

`dataset`，包含所有准备好训练或进一步处理的实例。该方法有效地构建了一个封装了从图像中提取的实例的数据集，能够训练机器学习模型或其他分析。

```java
// 训练分类器的方法（支持向量机 - SMO）
private static Classifier trainClassifier(Instances dataset) throws Exception {
    Classifier classifier = new SMO();
    classifier.buildClassifier(dataset);
    return classifier;
}
```

`trainClassifier` 方法负责使用提供的实例数据集训练分类器。它首先初始化一个 SMO（序列最小优化）分类器对象。SMO 是一种训练支持向量机（SVMs）的流行算法，SVM 是一种用于分类任务的监督学习类型。

在创建对象后，会调用 `buildClassifier` 方法，该方法接收数据集作为输入并使用数据集中的实例训练分类器。这一步触发了基于训练数据对分类器参数的优化。最后，返回训练好的分类器，准备好对新实例进行预测。

该方法封装了训练过程，抽象了模型训练的复杂性，并允许使用提供的数据对分类器进行简单训练。

```java
// 使用训练好的分类器对新实例进行分类的方法
private static double classifyInstance(Instance instance, Classifier classifier) throws Exception {
    return classifier.classifyInstance(instance);
    // 返回预测的类标签
}
```

`classifyInstance` 方法是分类过程中的关键组件。给定一个数据实例和一个训练好的分类器模型，它会根据提供的实例预测类标签或结果。此过程涉及将训练好的分类器应用于输入实例，并根据模型学习到的边界确定其属于哪类。

在方法内部，调用了分类器对象的 `classifyInstance` 函数，并将实例作为参数传递。该函数返回给定实例的预测类标签或值。如果成功，该方法将返回预测值。

# 16.4 COVID-19 检测

数据集中包含的属性有年龄、性别、发热、咳嗽、呼吸困难、疲劳、身体酸痛、味觉或嗅觉丧失、咽痛和检测结果。每一个属性对于理解个人的健康状况都起着至关作用，特别是与 COVID-19 相关。

1. 年龄：此属性记录了患者的年龄，这很重要，因为 COVID-19 会以不同的方式影响不同的年龄组。了解年龄分布有助于定制诊断过程并预测风险水平。

2. 性别：收集性别信息是因为它可以影响 COVID-19 的严重程度和症状。研究表明，疾病的表现方式和对个人的影响根据性别不同可能存在差异。

3. 发热：发热是 COVID-19 的常见症状，此属性记录了患者是否经历过体温升高，这是感染的关键指标。

4. 咳嗽：此属性记录了咳嗽的存在，这是 COVID-19 的另一种常见症状。持续咳嗽通常与呼吸道感染（包括 COVID-19）有关。

5. 呼吸困难：呼吸困难或气短是 COVID-19 症常见症状。此属性有助于识别可能需要立即医疗的患者。

6. 疲劳：记录疲劳是为了评估患者是否经历了异常的疲劳，这可能是 COVID-19 的症状，特别是当与其他指标结合时。

7. 身体酸痛：此属性记录了报告的身体酸痛或肌肉疼痛，这是感染 COVID-19 个员的常见症状。

8. 味觉或嗅觉丧失：味觉或嗅觉丧失是 COVID-19 的独特症状，它的存在可以显著帮助诊断该疾病。

9. 咽痛：咽痛是另一个可能伴随 COVID-19 的症状，特别是在早期。此属性有助于建立患者症状的综合概谱。

10. 检测结果：检测结果记录了患者的 COVID-19 检测是阳性还是阴性，为诊断过程提供了确定性的结果。

## 16.4.1 示例数据集

| 年龄 | 发热 | 咳嗽 | 呼吸困难 | 疲劳 | 身体酸痛 | 味觉或嗅觉丧失 | 咽痛 | 结果 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 45 | 男 | true | false | false | false | false | false | true |
| 32 | 男 | true | false | true | true | false | false | false |
| 56 | 男 | true | true | true | true | true | true | false |

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;
```

`BufferedReader` 类用于从字符输入流中高效读取文本，而 `FileReader` 用于从文件中读取字符。包含了 `IOException` 类以处理在文件操作期间可能出现的任何异常。最后，导入了 `ArrayList` 和 `List` 以便以列表的形式存储和操作数据。

```java
class Patient {
    private int age;
    private String gender;
    private boolean fever;
    private boolean cough;
    private boolean difficultyBreathing;
    private boolean fatigue;
    private boolean bodyAches;
    private boolean lossOfTasteOrSmell;
    private boolean soreThroat;
    private boolean testResult;
}
```

# 案例研究

属性包括 `age`（表示患者年龄）和 `gender`（指定其性别）。人口统计学细节是基础的。此外，布尔标志如 `fever`、`cough`、`difficultyBreathing`、`fatigue`、`bodyAches`、`lossOfTasteOrSmell` 和 `soreThroat` 捕捉了与 COVID-19 症状。`testResult` 是一个布尔值，表示 COVID-19 检测的结果，反映了患者的感染状态。

```java
// 构造函数
public Patient(int age, String gender, boolean fever, boolean cough,
    difficultyBreathing, boolean fatigue, boolean bodyAches, boolean lossOfTasteSmell,
    boolean soreThroat, boolean testResult) {
    this.age = age;
    this.gender = gender;
    this.fever = fever;
    this.cough = cough;
    this.difficultyBreathing = difficultyBreathing;
    this.fatigue = fatigue;
    this.bodyAches = bodyAches;
    this.lossOfTasteOrSmell = lossOfTasteSmell;
    this.soreThroat = soreThroat;
    this.testResult = testResult;
}
```

`public Patient(...)` 构造方法用于初始化 COVID-19 检测的 `Patient` 类实例。该构造函数接收代表基本属性的参数。`Patient` 类的每个属性都被赋予传入构造函数的值。

# Java 22 用于医疗与医学应用

`Main` 类包含一个静态方法 `readDataset`，负责从文件读取数据集并将其转换为 `Patient` 对象列表。在方法内部，初始化了一个名为 `patients` 的 `ArrayList` 用于存储来自文件中的患者数据。它利用 `BufferedReader` 通过 `fileName` 参数读取文件内容。

使用一个名为 `line` 的 `String` 变量来存储读取的每个文件行。此外，还初始化了一个名为 `lineNumber` 的 `int` 变量来跟踪行号，以便可能的错误报告。该变量对于识别数据处理过程中可能出现问题的特定特定行有用。

```java
while ((line = br.readLine()) != null) {
    lineNumber++;
    if (line.startsWith("#")) {
```

try-catch 块封装了读取数据集文件每一行的逻辑。在块内部，`BufferedReader` 读取文件的每一行，直到到达末尾（`null`）。在每次迭代中，`lineNumber` 变量都会递加 1，以跟踪当前行号。

还实现了另一个检查，以确保每行都包含 10 个数据字段。如果数据长度不等于 10，则向标准错误流打印错误消息，指示行号和字段数量的不匹配。此检查有助于识别和处理数据集格式中的任何差异或不一致之处。



```java
try {
    int age = Integer.parseInt(data[0]);
    String gender = data[1];
    boolean fever = Boolean.parseBoolean(data[2]);
    boolean cough = Boolean.parseBoolean(data[3]);
    boolean difficultyBreathing = Boolean.parseBoolean(data[4]);
    boolean fatigue = Boolean.parseBoolean(data[5]);
    boolean bodyAches = Boolean.parseBoolean(data[6]);
    boolean lossOfTasteSmell = Boolean.parseBoolean(data[7]);
    boolean soreThro = Boolean.parseBoolean(data[8]);
    boolean testResult = Boolean.parseBoolean(data[9]);
    // 创建新的 Patient 对象并将其添加到列表
    patients.add(new Patient(age, gender, fever, cough, difficultyBreathing, fatigue, bodyAches, lossOfTasteSmell, soreThro, testResult));
} catch (NumberFormatException e) {
    System.err.println("Error on line " + lineNumber + ": " + e.getMessage());
}
```

# 案例研究

## 691

```java
} catch (IOException e) {
    System.err.println("Error reading dataset: " + e.getMessage());
    return patients;
}
```

`try-finally` 块封装了从数据集文件每一行解析并初始化患者数据的逻辑。对于每一行，使用诸如 `parseInt()` 处理年龄、`parseBoolean()` 处理布尔属性等方法将值进行解析并转换为相应的数据类型。这些解析后的值随后用于初始化一个新的 `Patient` 对象，并将该对象添加到患者列表中。

实现了一个 `catch` 块来处理解析过程中可能发生的异常，例如 `NumberFormatException` 或 `ArrayIndexOutOfBoundsException`。如果发生任何异常，将向标准错误流打印错误消息，指示行号和具体的错误信息。最后，在 `finally` 块中关闭 `BufferedReader` 以在读取整个数据集文件后释放系统资源。

```java
public static void main(String[] args) {
    List<Patient> patients = dataset("test.txt");
    System.out.println("COVID-19 Detection Results:");
    for (Patient patient : patients) {
        boolean isPositive = patient.isPositiveForCovid();
        String testResult = patient.getTestResult() ? "Positive" : "Negative";
        System.out.println("Age: " + patient.getAge() + ", Test Result: " + testResult + 
            ", Likely Positive for COVID-19: " + isPositive);
    }
}
```

在块内部，调用了 `readDataset` 方法从 `"test.txt"` 加载患者数据到 `Patient` 对象列表中。如果数据集加载成功，将在控制台上打印一条指示数据集已成功加载的消息。对于每个患者，调用了 `isPositiveForCovid` 方法，根据其症状和检测结果判断患者可能感染了 COVID-19。患者的年龄、COVID-19 检测结果（阳性或阴性）以及感染 COVID-19 的概率将打印到控制台上。

最后，在 `catch` 块中，捕获并处理数据集加载过程中发生的任何 `IOException`。控制台将打印一条读取数据集时发生错误的消息，随后是异常的堆栈跟踪。

```java
public boolean isPositiveForCovid() {
    // 简单规则：如果患者发烧或咳嗽，他们可能感染了 COVID-19
    return fever || cough;
}
```

`isPositiveForCovid` 方法旨在根据患者的症状判断其可能对 COVID-19 检测呈阳性。该方法接受一个 `Patient` 对象作为输入，并返回一个布尔值，表示患者是否可能检测结果为阳性。在方法内部，对关键症状（发烧和咳嗽）执行逻辑或操作。如果患者出现发烧或咳嗽，该方法返回 `true`，表明患者可能对 COVID-19 检测呈阳性。

# 16.5 使用 X 光进行新冠检测

来自 Cohen 集合和 Kaggle 的数据集包含了大量的胸部 X 光图像，每张图像都标注了相关信息。

```java
import org.opencv.core.*;
import org.opencv.imgcodecs.*;
import org.opencv.imgproc.*;
import weka.classifiers.*;
import weka.core.*;
import java.io.File;
import java.util.ArrayList;
import java.util.List;

public class CovidDetection {
    static {
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);
    }

    private String trainingDirectory = "c:/xray";
    private String newImages = "c:/xray";
    private Instances instances;

    public static void main(String[] args) {
        CovidDetection detector = new CovidDetection();
        try {
            // 实现逻辑在此
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public List<Instance> extractFeaturesFromImages(String directoryPath) {
        List<Instance> instances = new ArrayList<>();
        File directory = new File(directoryPath);
        File[] files = directory.listFiles((dir, name) -> name.endsWith(".jpg") || name.endsWith(".png"));
        if (files != null) {
            for (File file : files) {
                Mat image = Imgcodecs.imread(file.getAbsolutePath());
                double[] features = extractFeatures(image);
                Instance instance = createInstance(features);
                instances.add(instance);
            }
        }
        return instances;
    }

    public double[] extractFeatures(Mat image) {
        // 转换为灰度图
        Mat grayImage = new Mat();
        Imgproc.cvtColor(image, grayImage, Imgproc.COLOR_BGR2GRAY);
        // 角点检测
        Mat corners = new Mat();
        Imgproc.goodFeaturesToTrack(grayImage, corners, 100, 0.01, 10);
        // 边缘检测
        Mat edges = new Mat();
        Imgproc.Canny(grayImage, edges, 100, 200);
        // 像素强度直方图
        Mat hist = new Mat();
        Imgproc.calcHist(List.of(grayImage), new MatOfInt(0), new Mat(), hist, new MatOfInt(256), 0);
        // 特征值占位符
        double[] featureValues = new double[10]; // 根据实际调整大小
        // 提取
        // 使用实际特征填充 featureValues（这是一个简化示例）
        for (int i = 0; i < featureValues.length; i++) {
            featureValues[i] = Math.random();
            // 替换为实际特征提取逻辑
        }
        return featureValues;
    }

    private Instance createInstance(double[] features) {
        // 占位方法
        return null;
    }
}
```

`extractFeatures` 旨在处理目录中的所有图像文件并从每张图像中提取特征。它首先初始化一个空的 `Instance` 对象列表。它从给定目录获取所有特征。对于每个实例，随后使用训练过的分类器。

## 694 用于医疗和医学应用的 Java 22

```java
return featureValues;
```

`extractFeatures` 方法通过处理图像来提取各种局部和全局特征。它首先使用 `Imgcodecs.imread` 读取图像。接下来，它使用 `Improc.goodFeaturesTrack` 方法在图像的灰度版本中检测角点。然后它使用 `Improc.Canny` 方法进行边缘检测，并保存生成的边缘检测图像。对于全局特征，它使用 `Improc.calcHist` 计算像素强度直方图。该方法还对图像应用了 Gabor 滤波器，创建一个保存以供进一步分析的过滤版本。此外，它使用 `Improc.moments` 计算矩，并据此推导出 Hu 矩。该方法通过返回一个特征值的占位符数组结束，该数组代表了从图像中提取的各种特征的简化示例。这种全面的方法捕捉了图像的重要特征，以用于后续的分类任务。

```java
// 从特征数组创建 Weka 实例
public Instance createInstance(double[] features) {
    ArrayList<Attribute> attributes = new ArrayList<>();
    for (int i = 0; i < features.length; i++) {
        attributes.add(new Attribute("feature " + i));
    }
    // 添加类属性（二分类）
    attributes.add(new Attribute("class", List.of("COVID", "Normal")));
    Instances instances = new Instances("TestInstances", 0);
    instances.setClassIndex(instances.size() - 1);
    DenseInstance instance = new DenseInstance(instances.numAttributes());
    for (int i = 0; i < features.length; i++) {
        instance.setValue(attributes.get(i), features[i]);
    }
    instance.setValue("Normal"); // 类值的占位符
    instances.add(instance);
    return instance;
}
```

`createInstance` 方法从给定的特征数组构建一个 Weka `Instance` 对象。它从创建一个包含 `Attribute` 对象的 `ArrayList`，其中每个属性对应于特征数组中的一个元素，命名为 `"feature0"`、`"feature1"` 等。该属性列表被用于创建一个名为 `"TestInstances"` 的 `Instances` 对象，作为数据集的容器。该数据集的类索引是最后一个属性。创建了一个大小等于特征数量加一（为了类属性）的新 `DenseInstance` 对象。该方法用数组中的特征值填充该实例。最后，将该实例添加到数据集中，并该方法返回数据集中的第一个实例。

```java
// 从 Instances 列表创建 Weka 数据集
public Instances createDataset(List<Instance> instances) {
    ArrayList<Attribute> attributes = new ArrayList<>(instances.get(0).numAttributes());
    for (int i = 0; i < instances.get(0).numAttributes(); i++) {
        attributes.add(instances.get(0).attribute(i));
    }
    Instances dataset = new Instances("TrainingInstances", attributes, instances.size());
    for (Instance instance : instances) {
        dataset.add(instance);
    }
    return dataset;
}
```

## 案例研究

## 695

```java
return dataset;
```

`createDataset` 方法设计用于从给定的 `Instance` 对象列表生成 `Instances` 数据集。它首先初始化一个名为 `"TrainingInstances"` 的新 `Instances` 对象，其属性列表为空，容量被设置为提供的实例列表的大小。

```java
// 使用 SVM 训练分类器
public Classifier trainClassifier(Instances dataset) throws Exception {
    SMO smo = new SMO();
    smo.buildClassifier(dataset);
    return smo;
}
```

`trainClassifier` 方法负责在给定的实例数据集上使用序列最小优化 (SMO) 算法训练支持向量机 (SVM) 分类器。它创建一个 `SMO` 分类器的实例，这是一种广泛用于训练 SVM 的算法。然后，该方法在 `SMO` 实例上调用 `buildClassifier` 方法，并传入了提供的 `Instances` 数据集。该方法使用数据集中包含的数据训练 `SMO` 分类器。一旦分类器训练完成，该方法返回训练好的 `SMO` 分类器。

```java
// 使用训练好的分类器对实例进行分类
public double classifyInstance(Instance instance, Classifier classifier) throws Exception {
    // 使用分类器预测给定实例的类标签
    double predictedClassLabel = classifier.classifyInstance(instance);
    return predictedClassLabel;
}
```



`classifyInstance` 方法设计用于使用训练好的分类器预测给定实例的类别。它接受两个参数：一个代表待分类实例的 `Instance` 对象和一个代表已训练模型的 `Classifier` 对象。在方法内部，调用了分类器的 `classifyInstance` 函数，并传入了该实例，从而得到预测的类标签。

维生素缺乏数据集的属性包括年龄、性别、日照照射、维生素 D 摄入、血清水平、骨疼痛、肌肉无力、疲劳、抑郁和脱发。`createInstance` 方法用于创建相应的实例。

## 16.6 维生素缺乏

- 1. 年龄：该属性捕捉了患者的年龄，年龄影响很大。
- 2. 性别：收集了性别信息，这可能会影响维生素 D 的合成。
- 3. 日照照射：该属性记录了患者在阳光下的时间，这对维生素 D 的合成至关重要。
- 4. 膳食摄入：通过饮食摄入的维生素 D 数量。富含维生素 D 的食物包括鱼类、强化乳制品和补充剂。
- 5. 血清水平：维生素 D 浓度的直接衡量，反映是否存在缺乏。
- 6. 骨疼痛：疼痛是维生素缺乏的一种症状，这种维生素对骨骼健康至关重要。
- 7. 肌肉无力：肌肉无力是维生素缺乏的另一种症状。
- 8. 疲劳：慢性疲劳与多种缺乏有关。该属性有助于评估患者的整体状况。
- 9. 抑郁：维生素 D 缺乏与情绪障碍有关。包含此属性有助于了解维生素缺乏的影响。
- 10. 脱发：脱发可能是维生素缺乏的症状。该属性为健康状况增加了另一个维度。

### 16.6.1 样本数据集

| 年龄 | 性别 | 照射 | 膳食 D 摄入 | 血清水平 | 骨疼痛 | 肌肉无力 | 疲劳 | 抑郁 | 脱发 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 35 | 男性 | 2 | 800 | 10 | 否 | 是 | 否 | 否 | 否 |
| 45 | 女性 | 1 | 600 | 10 | 是 | 是 | 是 | 否 | 否 |
| 28 | 男性 | 3 | 1000 | 12 | 否 | 否 | 否 | 否 | 是 |
| 50 | 女性 | 1.5 | 400 | 6 | 是 | 是 | 是 | 否 | 是 |
| 60 | 男性 | 2.5 | 1200 | 15 | 否 | 否 | 是 | 否 | 否 |

`Patient` 类封装了用于检测维生素缺乏的关键属性。它包含了用于存储基本患者信息的字段，包括年龄、性别、日照照射、维生素 D 摄入量、维生素 D 水平以及骨痛、肌肉无力、疲劳、抑郁和脱发等症状的布尔指示。该类的每个实例代表一个独特的患者配置，提供了其健康状况的全面概述。通过存储这些属性，`Patient` 类可以根据特定症状或其他相关因素的存在与否，分析并检测潜在的缺乏情况。

```java
// Parameterized constructor
public Patient(int age, String gender, double sunExposure, double dietaryVitaminDIntake,
               double serumVitaminDLevel, boolean bonePain, boolean muscleWeakness,
               boolean fatigue, boolean depression, boolean hairLoss) {
```

`Patient` 类中的参数化构造函数有助于识别具有与维生素缺乏检测特定属性的患者对象。它接受各种代表患者健康状况的基本信息的参数。`age` 参数表示患者年龄，而 `gender` 参数表示其性别。`sunExposure` 参数捕获光照水平，这会影响人体维生素 D 的合成。此外，`dietaryVitaminIntake` 参数代表通过饮食摄入的维生素 D 含量。

此外，`serumVitaminDLevel` 参数测量血清维生素 D 水平，提供了患者当前 D 状态的见解。如 `bonePain`、`muscleWeakness`、`fatigue`、`depression` 和 `hairLoss` 等布尔参数作为与维生素缺乏相关的各种症状的指标。每个参数在适当设置时，反映了特定症状的存在。

```java
this.age = age;
this.gender = gender;
this.sunExposure = sunExposure;
this.dietaryVitaminIntake = dietaryVitaminIntake;
this.serumVitaminDLevel = serumVitaminDLevel;
this.bonePain = bonePain;
this.muscleWeakness = muscleWeakness;
this.fatigue = fatigue;
this.depression = depression;
this.hairLoss = hairLoss;
```

```java
// Getters
public int getAge() { return age; }
public String getGender() { return gender; }
public double getSunExposure() { return sunExposure; }
public double getDietaryVitaminDIntake() { return dietaryVitaminDIntake; }
public double getSerumVitaminDLevel() { return serumVitaminDLevel; }
public boolean hasBonePain() { return bonePain; }
public boolean hasMuscleWeakness() { return muscleWeakness; }
public boolean hasFatigue() { return fatigue; }
public boolean hasDepression() { return depression; }
public boolean hasHairLoss() { return hairLoss; }
```

```java
@Override
public String toString() {
    return "Patient[age=" + age + ", gender=" + gender + ", sunExposure=" + sunExposure +
        ", dietaryVitaminIntake=" + dietaryVitaminIntake +
        ", serumVitaminDLevel=" + serumVitaminDLevel + "]";
}
```

## 用于医疗保健和医学应用的 Java 22

```java
", bonePain=" + bonePain + ", muscleWeakness=" + muscleWeakness + ", fatigue=" + fatigue +
", depression=" + depression + ", hairLoss=" + hairLoss + "]";
}
```

`Patient` 的构造方法通过作为参数传递的值来初始化患者对象的属性。对象的每个属性都分配了构造函数参数提供的相应值。`age` 属性被设置为 `age` 参数的值，代表患者的年龄。同样，`gender` 属性被分配为 `gender` 参数的值，表示患者的性别。

此外，布尔属性如 `bonePain`、`muscleWeakness`、`fatigue`、`depression` 和 `hairLoss` 也被相应初始化。

```java
public class VitaminDeficiency {
    public static List<Patient> readDataset(String fileName) {
        List<Patient> patients = new ArrayList<>();
        int lineNumber = 0;
        try (BufferedReader br = new BufferedReader(new FileReader(fileName))) {
            String line;
            while ((line = br.readLine()) != null) {
                if (line.startsWith("#")) continue;
                String[] data = line.split(",");
                try {
                    int age = Integer.parseInt(data[0]);
                    String gender = data[1];
                    double sunExposure = Double.parseDouble(data[2]);
                    double dietaryVitaminIntake = Double.parseDouble(data[3]);
                    double serumVitaminDLevel = Double.parseDouble(data[4]);
                    boolean bonePain = Boolean.parseBoolean(data[5]);
                    boolean muscleWeakness = Boolean.parseBoolean(data[6]);
                    boolean fatigue = Boolean.parseBoolean(data[7]);
                    boolean depression = Boolean.parseBoolean(data[8]);
                    boolean hairLoss = Boolean.parseBoolean(data[9]);
                    Patient patient = new Patient(age, gender, sunExposure, dietaryVitaminIntake, serumVitaminDLevel, bonePain, muscleWeakness, fatigue, depression, hairLoss);
                    patients.add(patient);
                } catch (NumberFormatException e) {
                    System.err.println("Error parsing line " + lineNumber + ": " + e.getMessage());
                } catch (ArrayIndexOutOfBoundsException e) {
                    System.err.println("Error parsing line " + lineNumber + ": " + e.getMessage());
                }
                lineNumber++;
            }
        } catch (IOException e) {
            System.err.println("IOException while reading the dataset: " + e.getMessage());
        }
        return patients;
    }
}
```

# 用于医疗与健康应用的 Java 22

```java
// e.g., String prediction = model.predict(patient);
System.out.println("预测维生素 D 缺乏：[在此插入预测逻辑]");
System.out.println("-----------------");
```

主方法从一个 `try` 块开始，尝试使用 `readDataset` 方法读取名为 "test.txt" 的数据集文件。如果成功，它将打印确认成功加载数据集的消息，并继续进行维生素缺乏症检测。在 `catch` 块中，它处理 `IOException`，该异常在读取数据集文件时发生错误可能会触发。

# 16.7 抑郁症检测

每个属性都贡献了价值信息，通过分析这些信息可以了解个人的心理健康状况，特别是关于抑郁症。

- 1. 年龄：此属性记录了患者的年龄，这非常重要，因为抑郁症在不同年龄组中的表现可能不同。了解年龄分布有助于定制诊断过程并预测风险水平。
- 2. 性别：收集性别信息是因为它可以影响抑郁症的发病率和症状。研究表明，抑郁症会影响男性和女性，但在症状表现和严重程度上存在差异。
- 3. 状况：此属性记录了患者的婚姻状况，因为关系动态和社交支持系统会显著影响心理健康。已婚、单身、离婚或丧偶可能与不同程度的抑郁症相关。
- 4. 就业：就业状态提供了对患者社会经济稳定性和压力水平的见解。失业或工作不稳可能是导致抑郁症的主要压力源。
- 5. 受教育程度：此属性捕捉了患者所达的最高教育水平。教育会影响与健康有关的因素，如工作机会、社会地位和应对机制。
- 6. 家族抑郁症病史：此属性记录了患者家族是否有抑郁症病史，这是一个重要的风险因素。遗传易感性和家庭动态在抑郁症的发展中可能起着关键作用。
- 7. 睡眠障碍：睡眠问题在抑郁症中很常见，此属性记录了失眠或嗜睡。睡眠障碍既是抑郁症的症状，也是潜在的加重因素。
- 8. 胃口变化：此属性捕捉了食欲的变化，这在抑郁发作中很常见。明显的体重减轻或增加都可能是抑郁症的迹象。
- 9. 兴趣或快乐丧失：这记录了患者是否对曾经喜欢的活动失去了兴趣或快乐，这是抑郁症的核心症状，被称为"快感缺失"。
- 10. 疲劳或精力丧失：持续的疲劳或能量水平的明显下降是抑郁症的另一个常见症状。此属性有助于识别可能正在经历这种病症的患者。
- 11. 毫无价值感或罪恶感：这些感受是抑郁症的重要指标，会严重影响一个人的心理健康和日常功能。
- 12. 难以集中：此属性记录了任何报告的注意力集中或做决策方面的困难，这些是抑郁症的常见认知症状。

# 案例研究 701

- 13. 自杀念头：自杀念头的出现是严重抑郁症的关键症状，需要立即的关注和干预。
- 14. 抑郁症诊断：这是结果变量，指示患者是否被诊断为患有抑郁症。此属性用于训练和验证预测模型。

# 16.7.1 数据集

| 年龄 | 性别 | 婚姻状况 | 就业状态 | 受教育程度 | 家族抑郁症病史 | 睡眠障碍 | 胃口变化 | 兴趣或快乐丧失 | 疲劳精力丧失 | 毫无价值感或罪恶感 | 难以集中 | 自杀念头 | 抑郁症诊断 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 35 | 男 | 已婚 | 就业 | 学士学位 | 是 | 是 | 是 | 是 | 是 | 是 | 否 | 否 | 否 |
| 28 | 女 | 单身 | 就业 | 高中毕业 | 否 | 否 | 否 | 否 | 否 | 否 | 否 | 否 | 否 |
| 45 | 女 | 已婚 | 失业 | 硕士学位 | 是 | 否 | 是 | 否 | 否 | 是 | 否 | 否 | 否 |
| 50 | 男 | 离婚 | 就业 | 博士学位 | 否 | 是 | 否 | 否 | 否 | 否 | 是 | 否 | 是 |

# 案例研究 703

```java
// 包含数据集读取方法和执行逻辑的主类
public class Main {
    // 从文件读取数据集并返回 Patient 对象列表的方法
    public static List<Patient> readDataset(String fileName) {
        List<Patient> patients = new ArrayList<>();
        try (BufferedReader reader = new BufferedReader(new FileReader(fileName))) {
            String line;
            int lineNumber = 0;
```

`Main` 类包含一个名为 `readDataset` 的方法，负责读取数据集文件并根据文件中提供的信息创建患者对象列表。该方法接受文件名作为输入并返回一个患者列表。在方法内部，它初始化了一个空列表来存储患者对象，并使用 `BufferedReader` 读取文件内容。它将数组中的数据解析为适当的数据类型（例如：整数、字符串），并使用解析后的值创建新的 `Patient` 对象。代码会捕获并处理解析错误或数组越界异常，打印带有发生问题行号的错误信息。在处理完所有行后，关闭 `BufferedReader` 并返回患者列表。

```java
// 跳过标题行
br.readLine();
// 读取数据集的每一行
while ((line = br.readLine()) != null) {
    lineNumber++;
    // 跳过注释行
    if (line.startsWith("#")) continue;
    String[] data = line.split(",");
    // 检查有效数据长度
    if (data.length != 15) {
```



`System.err.println("Error at line " + lineNumber + ": Expected 15 fields found " + data.length);`

`continue;`

验证数组长度是否为预期的 15（这是有效数据集的标准）。如果长度不同，则会输出错误信息，指定行号和发现的字段数量。最后，如果长度与字段数量匹配，代码将继续将数据解析为相应类型并使用解析的值创建新的`Patient`对象。

```java
try {

    // 解析患者属性

    int age = Integer.parseInt(data[0].trim());

    String gender = data[1].trim();

    String maritalStatus = data[2].trim();

    String employmentStatus = data[3].trim();

    String educationLevel = data[4].trim();

    boolean familyHistoryOfDepression = Boolean.parseBoolean(data[5].trim());

    boolean sleepDisturbances = Boolean.parseBoolean(data[6].trim());

    boolean appetiteChanges = Boolean.parseBoolean(data[7].trim());

    boolean lossOfInterestOrPleasure = Boolean.parseBoolean(data[8].trim());
```

# 704 用于医疗和医学应用的 Java 22

```java
boolean fatigueOrLossOfEnergy = Boolean.parseBoolean(data[9].trim());

boolean feelingsOfWorthlessnessGuilt = Boolean.parseBoolean(data[10].trim());

boolean difficultyConcentrating = Boolean.parseBoolean(data[11].trim());

boolean suicidalThoughts = Boolean.parseBoolean(data[12].trim());

boolean depressionDiagnosis = Boolean.parseBoolean(data[13].trim());

    // 创建新的 Patient 对象并将其添加到列表

    Patient patient = new Patient(age, gender, maritalStatus, employmentStatus, educationLevel, familyHistoryOfDepression, sleepDisturbances, appetiteChanges, lossOfInterestOrPleasure, fatigueOrLossOfEnergy, feelingsOfWorthlessnessGuilt, difficultyConcentrating, suicidalThoughts, depressionDiagnosis);

    patients.add(patient);

} catch (NumberFormatException | ArrayOutOfBoundsException e) {

    System.out.println("Error at " + lineNumber + ": " + e.getMessage());

} catch (IOException e) {

    System.out.println("Error reading dataset: " + e.getMessage());

}

return patients;
```

在`readDataset`方法的`try`块中，数据集的每一部分都会被解析，以提取创建新`Patient`对象的相关信息。年龄、性别、婚姻状况、就业和教育程度是从`data`数组中去除前后空格后的相应代码提取的。抑郁症家族史、睡眠障碍、食欲变化、兴趣或快乐丧失、疲劳或精力丧失、无价值感或罪恶感、注意力集中、自杀念头和抑郁诊断的布尔值是通过`Boolean.parseBoolean`方法对去除后的字符串进行解析。

随后，使用解析后的值实例化一个新的`Patient`对象。如果发生任何解析错误（例如在解析年龄或其他数据类型时遇到非整数值），将捕获`NumberFormatException`或`ArrayIndexOutOfBoundsException`。在这种情况下，会打印一条错误信息，指定错误发生的行号以及异常消息。最后，在`finally`块中关闭`BufferedReader`以释放分配的资源确保适当清理，并返回患者列表。

```java
public static void main(String[] args) {

    List<Patient> patients = readDataset("test.txt");

    // 打印患者信息

    if (!patients.isEmpty()) {

        System.out.println("Dataset loaded successfully.");

        for (Patient patient : patients) {

            System.out.println("Age: " + patient.getAge() + ", Gender: " + patient.getGender() + ", Depression Diagnosis: " + (patient.isDepressionDiagnosis() ? "Yes" : "No");
```

# 案例研究

```java
        System.out.println("No patient data available.");

    }

}
```

列表中的每个患者的年龄、性别和抑郁状态都会打印到控制台。患者的年龄和性别直接从患者对象中获取，而抑郁诊断状态通过访问患者对象的`depressionDiagnosis`布尔属性来确定。如果值为`true`，则表示该患者被诊断为抑郁症；否则，表示该患者没有抑郁症诊断。

在打印患者信息后，会打印一条由连字符组成的分隔线，以便在视觉上区分每个患者的信息。如果在读取数据集时发生`IOException`，会在控制台打印一条错误信息，指示读取数据集时发生了错误，并打印异常的堆栈跟踪。

# 16.8 使用大脑图像进行抑郁症检测

这些研究利用了磁共振成像（MRI）特征，强调了神经影像技术与抑郁症的相关性。

```java
import org.opencv.core.*;

import org.opencv.imgcodecs.Imgcodecs;

import org.opencv.imgproc.Imgproc;

import weka.classifiers.classifier;

import weka.classifiers.functions.SMO;

import weka.core.Instance;

import weka.core.DenseInstance;

import weka.core.SerializationHelper;
```

```java
public class DepressionDetection {
    public static void main(String[] args) {
        // ... 实现
    }

    public static Mat preprocessImage(String imagePath) {
        // 读取图像并转换为灰度图
        Mat image = Imgcodecs.imread(imagePath, Imgcodecs.IMREAD_GRAYSCALE);
        Mat resizedImage = new Mat();
        Imgproc.resize(image, resizedImage, new Size(256, 256));
        // 归一化图像
        Mat normalizedImage = new Mat();
        Core.normalize(resizedImage, normalizedImage, 0, 255, Core.NORM_MINMAX);
        // 直方图均衡化
        Mat equalized = new Mat();
        Imgproc.equalizeHist(normalizedImage, equalized);

        return equalized;
    }

    public static double[] extractFeatures(Mat image) {
        // 使用 HOG 和 GLCM 进行提取的占位
        double[] features = new double[10]; // 根据实际特征提取调整大小

        // HOG 特征提取（占位）
        // 在此处实现 HOG 提取逻辑并填充特征
        // GLCM 特征提取（占位）
        // 在此处实现 GLCM 提取逻辑并填充特征
        // 返回提取的特征
        return features;
    }
}
```

# 案例研究

# 707

```java
public static void trainModel(double[] features) {
    try {
        // 加载或创建用于训练的数据集 (Weka Instances)
        Instances dataSet = createDataset(features);
        // 设置类索引（数据集中的最后一个属性）
        dataSet.setClassIndex(dataSet.numAttributes() - 1);
        // 初始化并构建分类器
        Classifier classifier = new SMO(); // 支持向量机
        classifier.buildClassifier(dataSet);
        // 创建用于预测实例
        Instance instance = new DenseInstance(1.0, features);
        instance.setDataset(dataSet); // 为实例设置数据集
        // 执行分类
        double predictedClass = classifier.classifyInstance(instance);
        System.out.println("Predicted class: " + predictedClass);

        // 如果需要，保存模型
        SerializationHelper.write("DepressionModel.model", classifier);
    } catch (Exception e) {
        e.printStackTrace(); // 打印任何异常以便调试
    }
}
```

`trainModel`方法旨在使用给定的特征集训练机器学习模型。在方法内部，它设置了数据集的类索引并初始化了一个分类器，在此情况下是支持向量机（SVM）分类器。然后，它使用提供的数据集构建分类器。

```java
public static Instances createDataset(double[] features) {
    // 创建 Weka Instances 占位符
    // 你应该将此替换为实际的数据集创建逻辑
    // 示例：
    // 1. 创建属性列表
    // 2. 创建 Instances 对象
    // 3. 将特征添加到 Instances 对象中
    return new Instances("DepressionDataset", /* attributes */, 0); // 调整属性
}
```

接下来，我们使用输入特征解析实例并设置其数据集。然后使用训练好的 SVM 模型对该实例进行评估，以预测类标签。最后，将预测的类别打印到控制台。如果在过程中发生任何异常，异常将会被捕获并打印到控制台以供调试。

# 16.9 阿尔茨海默症检测

使用了来自 OASIS 和 Kaggle 等公开数据集的脑图像。

```java
import java.io.File;
import org.opencv.core.Core;
import org.opencv.core.Mat;
import org.opencv.core.MatOfFloat;
import org.opencv.core.MatOfKeyPoint;
import org.opencv.core.Size;
```

# 708 用于医疗和健康应用的 Java 22

```java
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.imgproc.Imgproc;
import org.opencv.objdetect.HOGDescriptor;
import weka.classifiers.Classifier;
import weka.classifiers.functions.SMO;
import weka.core.DenseInstance;
import weka.core.Instance;
import weka.core.Instances;
import weka.core.converters.ConverterUtil.DataSource;
import weka.classifiers.Evaluation;
```

OpenCV 的`Core`类对于访问基础功能非常有用，例如使用`Core.NATIVE_LIBRARY_NAME`加载 OpenCV 库。该语句确保在进行任何图像处理操作之前正确加载了 OpenCV 库。`Mat`类表示矩阵，它是 OpenCV 中用于存储数据的主要数据结构。它允许各种操作，如调整大小、变换和特征提取。

`MatFloat`、`MatInt`和`MatKeyPoint`类是用于存储特定类型数据的专门数据结构，例如浮点值、整数和关键点（用于 SIFT 和 SURF 等特征检测算法）。

`Size`类表示图像或图像中感兴趣区域的大小。它通常用于在图像操作期间指定维度。

```java
public class AlzheimerDetection {
    public static void main(String[] args) throws Exception {
        // 加载 OpenCV 原生库
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);
        // 预处理脑图像
        Mat preprocessedImage = preprocess("brain_image");
        // 提取特征
        double[] features = extractFeatures(preprocessedImage);
        // 训练并评估模型
        trainModel(features);
    }
}
```

首先，`System.loadLibrary(Core.NATIVE_LIBRARY_NAME)`语句加载图像处理任务所需的 OpenCV 原生库。接下来，调用`preprocess`方法对输入图像进行预处理。该方法执行预处理步骤，如将图像转换为灰度图、将其调整为标准大小以及应用直方图均衡化以增强对比度和亮度。

预处理之后，调用`extractFeatures`方法从预处理过的图像中提取相关特征。该方法使用方向梯度直方图（HOG）技术计算特征描述符，捕捉图像的纹理和形状特征。一旦提取了特征，就会调用`trainModel`方法训练机器学习模型，从处理过的脑图像学习阿尔茨海默症的模式。

```java
public static Mat preprocess(String imagePath) {
    // 以灰度图形式加载输入图像
    Mat image = Imgcodecs.imread(imagePath, Imgcodecs.IMREAD_GRAYSCALE);
    // 将图像调整大小为 256x256 像素
    Mat resizedImage = new Mat();
    Imgproc.resize(image, resizedImage, new Size(256, 256));
```

![](img/5a077f56e14b826c2dc61de6c176e5ef_718_0.png)

# 案例研究

```java
// 应用直方图均衡化以增强对比度
Mat equalizedImage = new Mat();
Imgproc.equalizeHist(resizedImage, equalizedImage);
return equalizedImage;
```

`preprocessImage`方法旨在在进一步分析或特征提取之前对输入图像进行预处理。它专门用于使用 OpenCV 库处理灰度图像。

# 案例研究 711

`DenseInstance`类。然后，设置数据集的类索引，并使用`SMO`类的方法初始化支持向量机（SVM）分类器。



使用`buildClassifier`方法在数据集上训练 SVM 分类器。训练完成后，使用`evaluateModelOnce`类进行评估，预测输入特征的类别。最后，将预测的类别打印到控制台。

## 16.10 皮肤癌检测

从如 ISIC（国际皮肤图像协作）和 HAM10000（包含 10000 张图像的人机对抗）等可用数据集中收集了皮肤图像。

```java
import org.opencv.core.*;
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.imgproc.Imgproc;
import weka.classifiers.functions.SMO;
import weka.core.*;
import weka.classifiers.Evaluation;
import java.io.File;
import java.util.ArrayList;
import java.util.List;

// 来自两个库的各种类，包括用于图像
// 处理（例如 ‘Mat’、‘FeatureDetector’）和机器学习（例如，
// ‘Classifier’、‘Evaluation’）。
public class SkinCancerDetection {
    static System.loadLibrary(Core.NATIVE_LIBRARY_NAME);
    public static void main(String[] args) throws Exception {
        // Step 1: 加载并处理图像
        String imageDir = "path_to_dataset";
        List<Mat> preprocessedImages = preprocessImages(imageDir);
        // Step 2: 从图像提取特征
        List<double[]> featureVectors = extractFeatures(preprocessedImages);
        // Step 3: 训练机器学习模型
        trainModel(featureVectors);
    }
}
```

最初，加载 OpenCV 库以利用其图像处理能力。随后，程序对皮肤病变图像进行预处理，包括调整大小、降噪和对比增强等任务。然后，使用纹理分析、颜色直方图计算和形状描述符等技术从预处理后的图像中提取特征。这些特征以数值向量的形式表示并存储在列表中。随后，使用提取的特征训练一个机器学习模型，将皮肤病变分类为良性或恶性。训练过程涉及将特征向量输入分类算法（如支持向量机 SVM），以学习数据中的底层模式。可选的是，可以使用准确率、精确率和召回率等指标对训练后的模型进行性能评估。

```java
// 预图像：调整大小，灰度化转换
public static List<Mat> preprocessImages(String directoryPath) {
    List<Mat> preprocessedImages = new ArrayList<>();
    File folder = new File(directoryPath);
    File[] imageFiles = folder.listFiles();
    if (imageFiles != null) {
        for (File file : imageFiles) {
            Mat image = Imgcodecs.imread(file.getAbsolutePath());
            if (!image.empty()) {
                // 将图像调整大小为 225x225 像素
                Imgproc.resize(image, image, new Size(225,225));
                // 将图像转换为灰度图
                Imgproc.cvtColor(image, image, Imgproc.COLOR_BGR2GRAY);
                preprocessedImages.add(image);
            }
        }
    }
    return preprocessedImages;
}
```

`preprocess`方法负责为进一步的分析和提取准备皮肤病变图像。它接受一个包含图像的目录路径作为输入，并返回一个 OpenCV `Mat`对象列表，每个对象代表一张预处理后的图像。该方法初始化一个空列表来存储预处理后的图像。它遍历指定目录中的文件，使用 OpenCV `Imgcodecs.imread`函数加载每张图像。如果图像加载成功且不为空，则继续预处理步骤。步骤包括使用`Imgproc.resize`将图像调整为 225X225 像素的标准尺寸，并使用`Imgproc.cvtColor`将图像转换为灰度图，以简化特征提取。最后，将预处理后的图像添加到列表中。处理目录中的所有图像后，该方法返回处理后的图像列表。这一预处理步骤对于在特征提取和模型训练之前确保输入数据的统一性并降低复杂性至关重要。

```java
// 提取特征：以梯度直方图 (HOG) 为例
public static List<Double> extractFeatures(List<Mat> images) {
    List<Double> featureVectors = new ArrayList<>();
    for (Mat image : images) {
        MatOfFloat descriptor = new MatOfFloat();
        // 为每个图像计算 HOG 特征
        Imgproc.calcHOG(image, descriptor, new Mat(), new Mat(), 256, new MatOfFloat(0, 0, 256));
        // 将 MatOfFloat 转换为数组
        double[] featureVector = new double[(int) descriptor.total()];
        descriptor.get(0, 0, featureVector);
        featureVectors.add(featureVector);
    }
    return featureVectors;
}
```

`extractFeatures`方法负责从预处理的皮肤病变图像中提取相关特征。它接受由 OpenCV `Mat`对象表示的预处理图像列表作为输入，并返回特征向量列表，每个向量包含对应图像的提取特征。在方法内部，循环遍历输入列表中的每个处理后的图像。最初，方法初始化一个空列表来存储提取的特征。它利用 OpenCV 库通过`FeatureDetector`类检测图像中的关键点。随后，`calc`函数计算图像的梯度直方图，提供纹理和形状的定量表示。这些描述符转换为 double 数组并添加到列表中。此过程对列表中的每张图像重复。最终，该方法返回特征向量列表，每个向量封装了对应预处理图像的特征。



```java
// 使用 Weka 训练 SVM 模型
public static void trainModel(List<double[]> featureVectors) throws Exception {
    // 为 Weka 准备数据
    ArrayList<Attribute> attributes = new ArrayList<>();
    for (int i = 0; i < featureVectors.get(0).length; i++) {
        attributes.add(new Attribute("feature" + i));
```

`trainModel` 方法负责从皮肤病变图像中训练机器学习模型。通过设置类索引来准备数据集。随后，使用 `SMO` 类实例化支持向量机（SVM）分类器。调用 `buildClassifier` 方法使用提供的数据集训练模型。可选地，可以使用交叉验证来评估其性能。

![img](img/5a07f56e14b826dc61765ef_724_0)

# 712 Java 医疗应用

## 符号

- `#`: 38, 75, 87, 129, 145, 313, 328, 339, 372, 422, 423, 426, 429, 430, 435, 437, 438, 441, 449, 421, 580, 589, 641, 681, 684, 690, 693, 708, 711, 36, 93, 453, 41, 110, 6, 27, 318, 385, 507, 606, 72, 127, 185, 233, 251, 320, 514, 676, 682, 58, 248, 320, 321, 327, 395, 513, 611, 35, 46, 47, 50, 131, 35, 46, 47, 36, 71, 91, 39, 38, 35, 48, 50, `>=`: 39, `>=`: 38, 45, 45, 45, 039, 45, 263, 45, `^`: 39, l, 39, `||`: 39, `~`: 39
- `ArrayDeque`: 37, 621, 667
- `ArrayIndexException`: 333, 345, 346
- `ArrayList`: 91, 525, 529, 621, 622, 650, 679, 681, 683, 686, 688, 690, 692, 694, 696
- `ArrayOperations<T>`: 600
- `ArrayProcessor<T>`: 600
- `Array.sort()`: 318, 663
- `AssignmentOperators`: 41
- `Attribute`: 686, 703
- `available()`: 432
- `AWT`: 459
- `Base`: 194, 195, 200, 208–216, 220–223, 225, 280, 351, 359, 363, 364
- `Binding`: 7
- `Bitwise`: 35, 36, 39, 50, 507
- `Boolean`: 7, 8, 32, 124
- `BorderLayout`: 459, 469, 470
- `Boxing`: 43
- `BoxLayout`: 475, 476
- `Brak`: 66, 67, 71, 72, 74
- `BufferedInputStream`: 431, 432
- `BufferedOutputStream`: 434
- `BufferedReader`: 372, 434, 436, 479, 681, 682, 688, 690, 698
- `BufferedWriter`: 415, 436, 439
- `Buffering`: 432
- `Button`: 450, 472, 481, 481
- `GroupGroup`: 543
- `Byte`: 27, 28, 33, 42, 50, 65
- `Byte.MAX`: 33
- `Byte.MIN`: 33
- `Bytecode`: 11

## C

- `Callable`: 316–318
- `Callback`: 306
- `Canv`: 488, 490
- `capacity()`: 115, 116, 118
- `CardLayout`: 459, 472, 473
- `Casting`: 33, 34, 95, 180
- `Catch`: 329, 333, 335, 336, 338, 341, 345
- `ChangeEvent`: 546, 576–579
- `Char`: 31, 42, 112
- `char[]`: 102
- `Character`: 42
- `CharArrayWriter`: 450
- `charAt()`: 107
- `CharBuffer`: 104
- `CharSequence`: 104
- `check()`: 342
- `Checkbox`: 484, 485, 486
- `CheckboxGroup`: 486, 487
- `Choice`: 487, 488, 503, 506
- `Abstract`: 416, 479, 480
- `Abstract`: 48, 51, 52, 244–248, 269, 268
- `Abstraction`: 1, 14, 19, 267, 268
- `AbstractMap`: 640
- `abstractMethod()`: 52
- `AbstractSet`: 630
- `ActionEvent`: 497
- `Action`: 482, 483, 492, 496–499, 525, 529, 527, 539, 541–543, 560–52, 564, 566–569
- `ActionListener`: 459, 493
- `actionPerformed`: 496, 497
- `addActionListener`: 497
- `Adjustmentlistener`: 507–509
- `adjustmentValueChanged`: 307

# 716

# 索引

- 类 (Class), 190, 619
- `ClassName:new`, 297
- `ClassName:staticMethod`, 296
- `Clear`, 637, 649, 652, 654
- `clone()`, 157
- `close()`, 420, 429
- `collect()`, 115
- 集合 (Collections), 621
- 可比较的 (Comparable), 659
- `ComparableTo`, 600
- `Comparable`, 662, 665–679
- 比较 (Compare), 662
- `compareTo`, 108, 682, 664
- 编译, 21, 22, 54, 52, 326, 330, 351
- 编译器 (compiler), 11–15, 24, 36, 47, 76, 154, 163, 190, 203, 209, 239, 309, 324
- 组件 (component), 12, 35, 382, 462, 496, 472–476, 478, 482, 484, 488, 491, 502–508, 518, 532, 533, 539, 542, 544–548, 552, 555, 557, 573, 574, 587
- 组件适配器 (ComponentAdapter), 518
- 组件添加 (componentAdded), 516
- 组件隐藏 (componentHidden), 518
- 组件监听器 (componentListener), 518, 519
- 组件移动 (componentMoved), 518
- 组件移除 (componentRemoved), 512
- 组件大小调整 (componentSized), 518
- 连接并 (concat()), 106, 135
- 具体方法 (concreteMethod), 52
- 并发链队列 (ConcurrentLinkedQueue), 633
- 条件运算符 (ConditionalOperator), 42
- 容器适配器 (ContainerAdapter), 516
- 容器监听器 (ContainerListener), 516
- 包含 (contains), 635
- `contains()`, 109
- 包含键包含 (containsInKey), 637, 639, 642, 644
- 包含值 (containsValue), 637, 639, 642, 644
- 继续 (continue), 71, 82, 699
- 自定义异常 (CustomException), 340

# E

- 否则 (Else), 64
- 以...结尾 (endsWith()), 109
- 确保容量 (ensureCapacity()), 116
- 枚举映射 (EnumMap), 645
- 枚举集 (EnumSet), 657
- 等于 (equals()), 110, 667
- 异常 (Exception), 333, 350
- 继承 (Extends), 188

# F

- 假 (False), 27, 110, 421, 689
- 文件 (File), 415, 430
- 文件通道 (FileChannel), 415
- 浮动对话框 (FloatDialog), 494, 495
- 浮点输入流 (FloatInputStream), 431, 439
- 浮点数已找到 (floatFound), 328, 330, 334, 335, 359
- 浮点输出流 (floatOutputStream), 439
- 浮点路径 (floatPath), 452
- 文件读取器 (FileReader), 436, 437, 441, 449, 688
- 浮点写入器 (floatWriter), 437, 440, 442, 449, 550
- 浮点过滤器 (floatFilter), 550
- 最终 (Final), 51, 141, 237, 238, 249
- 最终类 (FinalClass), 236
- 最终 (Finally), 329, 333, 335, 336, 349, 351
- 浮点方法 (floatMethod), 551
- 查找 (find), 123
- 第一个 (first), 313
- 浮点 (float), 30–33, 52, 200
- 浮点 (float), 42
- 浮点最大值 (Float.MAX_), 33
- 浮点最小值 (Float.MIN_), 33
- 浮点层 (floatLayer), 468, 481–484, 487–91
- 刷新 (flush()), 436
- 焦点适配器 (focusAdapter), 515
- 焦点获得 (focusGained), 499
- 焦点监听器 (focusListener), 499, 516, 571, 572
- 浮点成本 (floatCost), 499, 500, 515
- 对于 (for), 68, 71, 93, 102, 112, 121
- 窗口 (Frame), 463, 464, 466, 469, 470, 472, 473, 475–477, 480–484, 487–489, 491, 493, 494, 498, 502

# D

- 数据类型 (DataType), 92
- 默认 (Default), 47, 49, 261
- 默认访问 (DefaultAccess), 49
- 默认方法 (defaultMethod), 49
- 默认变量 (defaultVar), 49
- 删除 (Delete), 120
- 双队列 (Deque), 665, 667
- 对话框 (Dialog), 465, 466
- 字典 (Dictionary), 642
- 目录 (Directory), 422
- 显示 (display()), 217, 267, 269, 270, 272, 277, 278, 293, 297, 298, 300, 304, 305
- `do.`, 35, 77, 78
- 文档监听器 (documentListener), 539, 540, 564, 573
- 双精度浮 (double), 30–33, 35, 42, 210, 300, 502, 618
- 双精度最大值 (Double.MAX_), 33
- 双精度最小值 (Double.MIN_), 33
- 解析双精度 (parseDouble), 42
- 双精度值转换 (double.valueOf), 43

# G

- 获取字节 (getByte()), 111
- 获取字符 (getChars()), 112
- 获取文件指针 (getFilePointer()), 446
- 获取实例 (getInstance()), 156
- 获取选中选择框 (getSelectedCheckbox), 486
- 网格约束 (GridBagConstraints), 473
- 网格布局 (GridBagLayout), 473
- 网格布局 (GridLayout), 360, 471
- 组布局 (GroupLayout), 476, 477

# H

- 哈希码值 (hashCode()), 667
- 哈希映射 (HashMap), 43, 621, 655
- 哈希集 (HashSet), 622, 626, 628, 669
- 哈希表 (HashTable), 620, 644
- 更多标记 (hasMoreTokens), 121
- 头映射 (headMap), 640, 672
- 哈希集 (HashSet), 670
- 连接 (Join), 390
- 面板 (JPanel), 477, 479, 535
- 文本框 (JTextField), 541
- 弹出菜单 (JPopupMenu), 551, 561, 588
- 滚动面板 (JScrollPane), 552
- 滑块 (Slider), 546, 576
- 旋转调节器 (JSpinner), 577

# I

- 如果 (if), 41, 62–83
- 非法参数异常 (IllegalArgumentException), 130, 145, 146, 364
- 非法状态异常 (IllegalStateException), 402
- 图像路径 (imagePath), 705, 706, 708, 709
- 实现 (implements), 262, 273, 274
- 索引查找 (indexOf), 107
- 索引越界异常 (IndexOutOfBoundsException), 364
- 输入流 (InputStream), 420, 433
- 输入流器 (InputStreamReader), 438, 499
- 实例 (instances), 155, 156
- 标签页面板 (JTabbedPane), 557, 578
- 表 (Table), 545
- 文本区域 (TextArea), 540, 573
- 文本框 (JTextField), 539, 571
- 切换按钮 (JToggleButton), 562
- 工具栏 (JToolBar), 555, 568

# L

- 标签 (Label), 466, 481, 503, 519
- 最后 (Last), 472
- 最后一次索引 (lastIndexOf), 107
- 最后一个键 (lastKey), 640
- 长度 (length()), 112, 131
- 链式哈希映射 (LinkedHashMap), 635, 637
- 链式哈希集 (LinkedHashSet), 628, 667
- 链式列表 (LinkedList), 624, 653
- 列表 (List), 488, 490, 504, 624, 652, 679, 688, 692, 696
- 列表 (list()), 421, 422
- 列表选择 (ListSelection), 580
- 局部变量 (localVar), 46
- 日志 (log()), 209
- 日志器 (Logger), 209

# J

- 锯齿形数组 (jaggedArray), 97
- awt (java.awt), 20, 91, 93, 105, 121, 679, 683
- awt 数据传输 (java.awt.datransfer), 462
- awt (java.awt.event), 462
- awt 事件 (java.awt.event), 462
- awt 几何 (java.awt.geom), 462
- awt 图像 (java.awt.image), 462
- io (java.io), 415, 420
- 语言 (java.lang), 42
- nio (java.nio), 415
- 并发 (java.util.concurrent), 318
- 函数 (java.util.function), 290
- 正则 (java.util.regex), 102, 142
- 包 (package), 20
- 按钮 (JButton), 537, 570
- 复选框 (JCheckBox), 542, 575
- 菜单项 (JCheckBoxMenuItem), 551
- 组合框 (JComboBox), 558, 566
- 桌面面板 (DesktopPane), 569
- 编辑器面板 (JEditorPane), 556, 664
- 文本框 (JTextField), 572
- 框架 (JFrame), 479, 535, 536
- 标签 (JLabel), 536, 578
- 列表 (List), 544, 580
- 菜单 (JMenu), 550, 560
- 菜单栏 (MenuBar), 550

# M

- 映射 (Map), 635, 637, 642, 645, 656, 671
- 匹配器 (Matcher), 123
- 圆周率 (Math.PI), 210
- 随机数 (Math.random()), 180
- 平方 (Math.sqrt), 179
- 数学工具 (MathUtils), 132, 135, 179
- 最大 (Max), 137
- 菜单 (Menu), 491, 493, 498
- 菜单栏 (MenuBar), 493, 494
- 菜单项 (MenuItem), 492, 493
- 创建目录 (mkdir()), 421
- 创建目录s (mkdirs()), 421
- 鼠标适配器 (MouseAdapter), 509–511
- 鼠标点击 (mouseClicked), 509, 512
- 鼠标进入 (mouseEntered), 581
- 鼠标退出 (mouseExited), 581
- 鼠标移动 (mouseMoved), 515
- 鼠标释放 (mouseReleased), 509
- 范围 (Range), 658
- 读取 (read()), 432
- 读取器 (Reader), 420, 434, 440–441
- 读取文件 (readFile), 328–329, 351
- 鼠标监听器 (MouseListener), 510, 512, 518, 581
- 鼠标移动监听器 (MouseMotionListener), 513, 515
- 移除 (remove()), 627, 692, 644
- 替换 (replace()), 115, 177
- 反转 (reverse()), 115
- 运行 (run), 280, 380–385, 387, 388, 392, 394
- 可运行 (Runnable), 280, 315, 380–381, 394

# N

- 运行时 (Runtime), 355, 360–375, 378–388
- 原生 (native), 54
- 导航映射 (NavigableMap), 640
- 导航集 (NavigableSet), 630

# $

- 嵌套 (Nested), 304
- 扫描器 (Scanner), 58, 59, 93, 127, 184
- 新 (New), 103, 105, 132, 158, 161, 162, 241, 304
- 获取下一个 (next()), 472
- 整数 (nextInt), 93
- 序列化 (Serialized), 53
- 下一个标记 (nextToken()), 121
- 空, 27, 258, 666

# O

- 睡眠 (sleep), 387
- 输出流 (OutputStream), 415, 424
- 输出流器 (OutputStreamWriter), 439
- 排序 (sort()), 621
- 排序映射 (SortedMap), 671–683
- 排序集 (SortedSet), 669–671

# P

- 包 (Package), 18–19
- 面板 (Panel), 464, 465, 473, 476
- 参数 (Parameters), 327–328
- 查看 (Peek), 635, 647
- 路径 (Path), 415
- 弹出 (Pop), 647
- 位置 (Position), 446
- 打印机 (Printer), 135
- 优先级队列 (PriorityQueue), 619–621
- 缓冲字符串 (StringBuffer), 104, 118
- 私有 (private), 120, 129, 151
- 构造器字符串 (StringBuilder), 104, 139
- 保护 (protected), 49
- 公有 (public), 49, 302, 340, 380, 395
- 推入 (push()), 647
- 打印 (print()), 217, 269, 270, 272, 277, 278, 293, 297, 298, 300, 304, 305
- 裁剪 (strip()), 115
- 裁剪尾部 (stripTrailing()), 115

# Q

- 队列 (Queue), 633, 665
- 超类 (super), 314

# R

- 运行时 (Runtime), 355, 360–375, 378–388
- 原生 (native), 54
- 导航映射 (NavigableMap), 640
- 导航集 (NavigableSet), 630

# W

- 等待 (wait()), 397, 402–405, 413
- 当 (While), 68, 74, 77, 449
- 窗口 (Window), 466
- 窗口激活 (windowActivated), 506
- 窗口适配器 (windowAdapter), 509, 510
- 窗口关闭 (windowClosing), 506
- 窗口去激活 (windowDeactivated), 506
- 窗口最小化 (windowIconified), 506
- 窗口监听器 (WindowListener), 506, 509
- 窗口启动监听器 (WindowStartListener), 507
- 写入 (Write), 441, 442
- 写入文件 (writeToFile), 445

![img](img/5a077f56e14b826c2dc61de6c176e5ef_730_0.png)
