
# 公共方法与动态绑定

公共方法提供了对象交互的唯一手段。对象的表示始于类型描述符的地址。类型描述符包含一个字典，将方法名映射到代码段。在运行时，Smalltalk 解释器在字典中执行查找操作以查看该方法是否可用。如果不可用，它会生成一个“消息未理解”（message not understood）——相当于 Lisp 中的类型冲突错误。Objective-C、Swift 和面向对象的脚本语言提供了类似的语义，并引导了类似的实现。动态方法比静态方法灵活得多，但在方法很小时会产生巨大的代价，并推迟错误的报告。

此外，间接的虚拟方法的开销通常阻止了子程序在编译时进行内联展开（in-line expansion）。当子程序很小且被频繁调用时，缺乏内联子程序可能会导致严重的性能问题。像 C 一样，C++ 尽可能避免运行时开销；因此，它将静态绑定作为默认，并严重依赖对象值变量，因为即使是虚拟方法也可以在编译时进行补丁。

# 10.4 对象闭包

我们已经注意到（在第 3.6.4 节和其他地方），对象闭包可以在面向对象的语言中使用，以实现与嵌套子程序语言中的子程序闭包大致相同的效果——即封装方法上下文以备日后执行。需要注意的是，这种机制依赖于其完全的通用性，即动态方法绑定。回示例 3.36 中的 `plus_x` 对象闭包，将其适配示例 9.23 的 `apply_to_A` 代码，并用通用格式编写：

## 示例 10.49 对象闭包中的虚拟方法

```cpp
template<typename T>
class un_op {
public:
    virtual T operator() (T i) const = 0;
};

class plus_x : public un_op<int> {
public:
    const int x;
    plus_x(int n) : x(n) {}
    virtual int operator() (int i) const { return i + x; }
};

void apply_to_A(const un_op<int>& f, int A[], int A_size) {
    int i;
    for (i = 0; i < A_size; i++) A[i] = f(A[i]);
}
```

```cpp
int A[10];
apply_to_A(plus_x(2), A, 10);
```

任何派生自 `un_op<int>` 的对象都可以传递给 `apply_to_A`。因为 `operator()` 是虚拟的，所以始终会调用“正确的”函数。

对于许多应用程序，一种特别实用的习惯是将方法及其参数封装在对象闭包中以备日后执行。例如，假设我们正在编写 C-9.5 节描述的离散事件仿真。

```cpp
class fn_call {
public:
    virtual void operator() = 0;
    void schedule_at(fn_call& fc, time t) {
        // ...
    }
    // ...
};
```

```cpp
class call_foo : public fn_call {
    int arg1;
    double arg2;
    char arg3;
public:
    call_foo(int a, double b, char c) : // 构造函数
        arg1(a), arg2(b), arg3(c) {
        // 只需要进行成员初始化
    }
    void operator() {
        foo(arg1, arg2, arg3);
    }
};
```

```cpp
call_foo cf(3, 3.14, 'x'); // 声明/构造函数调用
schedule_at(cf, now() + delay);
// 在未来的某个时间点，离散事件系统
// 将调用 cf.operator()，这将导致调用
// foo(3, 3.14, 'x');
```

**图 10.5 子程序指针和虚拟方法。** 类 `call_foo` 封装了一个子程序指针和要传递给子程序的值。它导出一个无参数的子程序，可用于触发封装的调用。

## 检查理解

- 31. 解释动态方法绑定和静态方法绑定的区别。
- 32. 为什么 C++ 默认使用静态方法绑定？
- 33. 总结动态绑定的基本论点。
- 34. Ada 95 中的类范围类型（class-wide type）是什么？
- 35. 解释动态方法绑定与多态性之间的联系。

# 第 10 章 数据抽象与面向对象

## 10.5 混入继承

在构建面向对象的系统时，通常很难设计出一个完美的继承树，使得每个类恰好有一个父类。猫可以是一种动物、宠物、家庭成员（`family_member`）或心爱对象（`object_of_affection`）。公司数据库中的一个组件（`widget`）可以是一个排序对象（`sortable_object`，从报告系统的角度）、图形对象（`graphable_object`，从窗口系统的角度）或存储对象（`storable_object`，从文件系统的角度）；我们如何只选择其中一个呢？

在通用情况下，我们可以允许一个类拥有任意数量的父类，每个父类都可以为它提供字段和方法（包括抽象和具体的）。这种“真”继承由多种语言提供，包括 C++、Eiffel、CLOS 和 Python；我们将在第 10.6 节中讨论它。遗憾的是，它在语言语义和运行时实现上都引入了相当复杂性。在实践中，一种更有限的机制，如混入继承（mix-in inheritance），通常就是我们需要的。

以我们的组件为例。很可能，报告系统并没有精确定义什么是组件；它只需要能够以某些特定的定义良好的方式来操作组件——例如，对它们进行排序。同样，窗口系统可能不需要为组件提供任何状态或功能；它只需要能够将它们显示在屏幕上。为了捕获这类需求，具有混入继承的语言允许程序员定义类必须提供的接口顺序。对于组件而言，报告系统可能定义一个 `sortable_object` 接口；窗口系统可能定义一个 `graphable_object` 接口；文件系统可能定义一个 `storable_object` 接口。任何一个接口都不会提供实际功能：组件类的设计者将需要提供适当的实现。

实际上——正如我们在第 10.4.2 节中所指出的——接口是一个只包含抽象方法的类——没有字段或方法体。因此，由于它只继承自一个“真实的”类，一个类可以“混入”任意数量的接口。如果子类的参数被声明为接口类型，那么任何实现（继承自）该接口的类都可以作为相应的实际参数传递。这些是在不需要共同祖先的情况下就可以合法传递的对象类。

近年来，混入已成为处理多重继承的一种常用方法——可以说是主导方法。尽管细节在不同语言之间不同，但接口出现在 Java、C#、Scala、Objective-C、Swift、Go、Ada 2005 和 Ruby 等语言中。

详细阐述我们的组件示例，假设我们已经得到了通用的 Java 代码，它可以根据某些文本字段对对象进行排序，在网络浏览器中显示对象的图形表示（根据需要进行隐藏和刷新），并在字典数据结构中按名称存储对象的引用。这些能力中的每一个都将由一个接口表示。

## 示例 10.51 接口的动机

## 示例 10.52 将接口混入派生类中

如果我们已经开发了一些复杂的组件对象类，通过将适当的接口混入派自组件的类中，我们可以利用这些通用代码，如图 10.6 所示。

### 10.5.1 实现

在像 Ruby、Objective-C 或 Swift 等使用动态方法查找的语言中，接口的方法可以实现该接口的任何类的字典中。在这种语境下，需要接口类型，通常的查找机制将找到适当的方法。在具有完全静态类型系统的语言中，期望方法指针位于已知的 vtable（虚函数表）偏移量处，则需要新的机制。挑战归结于对对象的多个视图的需求。

## 示例 10.3 混入继承的编译时实现

在图 10.6 中，方法字典插入了一个 `storable_object` 视图——一种查找参数的 `get_stored_name` 方法的方法。然而，`get_stored_name` 方法是由 `augmented_widget` 实现的，并将暴露此参数的增强型 vtable 视图——一种查找对象的字段和其他方法的方法。鉴于 `augmented_widget` 实现了三个接口，单一 vtable 无法扫描：它的条目同时是 `storable_object`、`graph_object` 和 `storable_object` 的第一项。

最常见的解决方案如图 10.7 所示，是在每个 `augmented_widget` 中插入三个额外的 vtable 指针——为每个实现的接口提供一个。对于每个接口视图，我们可以使用一个指针指向对象内部出现相应 vtable 指针的位置。该指针相对于对象起始位置的偏移量被称为“this 矫正”（this correction）它存储在 vtable 的开头。

假设我们想要调用 `dictionary.insert` 一个地址存储在 r1 中的 `augmented_widget w`。编译器知道 `w` 的 `storable_object` vtable 指针的 c 偏移量，将在传递给 `insert` 之前将 c 加到 r1 上。到目前为止良好。当 `insert` 调用 `storable_object.get_stored_name` 时会发生什么？假设 `w` 的 `storable_object` 视图可用在例如 r1 中，编译器将生成如下的代码：

```
r2 = +r1                -- vtable address
r3 = +r2                -- this correction
r3 += r1                -- address of w
call(r2+4)             -- method address
```

我们假设此矫正占据了 vtable 的前四个字节，且 `get_stored_name` 的地址紧随其后，位于表中的第一个常规槽位。我们还假设这应该是

```java
public class widget {...
}

interface sortable_object {
    String get_name();
    bool less_than(sortable_object o);
}

interface graphable_object {
    void display_at(Graphics g, int x, int y);
}

interface storable_object {
    String get_stored_name();
}

class named_widget extends widget implements sortable_object {
    public String name;
    public String get_name() {return name;}
    public bool less_than(sortable_object o) {
        return name.compareTo(o) < 0;
    }
}

class augmented_widget extends named_widget
    implements graphable_object, storable_object {
    public void display_at(Graphics g, int x, int y) {}
    public String get_stored_name() {return name;}
}

class sorted_list {
    public void insert(sortable_object o) {...}
    public sortable_object first() { ... }
}

class browser_window extends Frame {
    public void add_to_window(graphable_object o) {...}
}

class dictionary {
    public void insert(storable_object o) {...}
    public sortable_object lookup(String name) { ... }
}
```

图 10.6 Java 中的接口类。通过在 `named_widget` 中实现 `storable_object` 接口，并在 `augmented_widget` 中实现 `graphable_object` 和 `storable_object` 接口，我们获得了将这些类的传递给 `sorted_list.insert`、`browser_window.add_to_window` 和 `dictionary.insert` 的能力。

图 10.7 混入继承的实现。`augmented_widget` 对象包含四个 vtable 地址，一个用于类本身（如图10.3所示），三个用于实现的接口。传递给接口例的对象视图直接指向相关的 vtable 指针。vtable 开头有一个“this correction”偏移量，用于重新生成指向对象的指针。这比单继承所需的代码长。一旦执行，`augmented_widget.get_stored_name` 将以它预期的参数运行：指向 `augmented_widget` 对象的引用。

### 10.5.2 扩展

上述接口描述反映了 Java 的历史版本，漏掉了：除了抽象方法外，接口还可以定义静态（常量）字段。由于这些字段永远不会改变，它们不会引入运行时复杂性或开销——编译器可以有效地在它们使用的地方将其展开。

从 Java 8 开始，接口还扩展到允许静态和默认方法，这些方法带有方法体——接口的声明。静态方法像静态最终字段一样，没有引入实现复杂性：它不需要访问对象字段，因此关于传递什么没有歧义——没有参数。默认方法稍微复杂一点。它们旨在供任何没有重写的类使用。这种约定对于库维护者来说非常有价值；它允许向现有的库接口中添加方法，而不会破坏现有的用户代码，否则用户代码将不得不更新继承该接口的任何类以实现新方法。

## 示例 10.54 默认方法的用法

假设例如，我们正在参与一个本地化项目，目标是将某些现有代码适配多种语言和文化。在图 10.6 的代码中，我们可能希望为 `storable_object` 接口添加一个新的 `get_local_name` 方法。通过一个对 `storable_object` 的引用，更新后的用户代码就可以调用此方法而不是 `get_stored_name`，以获取适用于本地上下文的字符串。一个继承自 `storable_object` 的具体类作为本地化项目的一部分已经更新，它可能会提供其自己的 `get_local_name` 实现。那么那些尚未更新（或可能永远不会更新）的类呢？它们可以利用默认方法回退到某种通用机制：

```java
default String get_local_name() {
    return backup_translation(get_stored_name());
}
```

对于默认方法，每个继承自 `storable_object` 的具体类都需要重新编译，但其源代码可以保持不变。由于方法是在接口声明内部定义的，它只能看到接口本身的方法和（静态）字段（以及来自周围作用域的任何可见名称）。特别地，它无法访问继承该接口的类的其他成员，因此任何一个对象的对象都不会让它找到这些成员。同时，该方法确实需要访问对象特定的虚表（vtable）。在我们的 `storable_object` 示例中，默认的 `get_local_name` 必须能够找到并调用由具体类定义的 `get_stored_name` 版本。实现此点的通常方法依赖于微小的转发例程：对于每个继承自 `storable_object` 并需要默认代码的类，编译器会生成一个静态的、C 特有的路由，该路由接收具体类特定的参数，补回常规调用序列刚刚丢弃的上下文，并将指向虚表指针的指针传递给默认方法。

## 示例 10.55 默认方法的实现

事实证明，Scala 编程语言提供了默认方法的等效实现，其混入（mix-ins）被称为特征（traits）。事实上，特征不仅支持默认方法，还支持可变字段。Scala 编译器并没有提供一个使这些字段可直接访问的视图，而是为每个继承自特征的具体类生成了一对隐藏的访问器方法，这些方法类似于 C# 的属性（示例 10.7）。对访问方法的引用随后被包含在接口特定的虚表中，在虚表中可以被默认方法调用。在任何未提供特征字段实现的类中，编译器都会创建一个新的私有字段供访问方法使用。

## 10.6 真正的多重继承

如第 10.5 节所述，混入继承允许指定必须由继承类提供的功能，或者供该类的对象在给定的上下文中使用。至关重要的一点是，接口在大多数情况下并不提供该功能。即使是默认方法，也主要用于协调对继承类所提供的功能访问。

有时，从多个基类继承真实的功能是很有用的。假设例如，我们的管理系统需要跟踪每个系统用户的信息，而大学为每个学生都提供了 `person` 和 `system_user` 类型。那么，从 `person` 和 `system_user` 派生出 `student` 可能是理想的。在 C++ 中我们可以说

## 示例 10.56 派自两个基类

```cpp
class student : public person, system_user { }
```

现在一个 `student` 类的对象将拥有 `person` 和 `system_user` 的所有字段和方法。Eiffel 中的声明是类似的：

```eiffel
class student
inherit
    person, system_user
feature
```
