
# Ada 语言原理 [IBFW91] 第 8 章包含了对参数传递模式的精彩讨论

Harbison [Har92, 第 6.2–6.3 节] 描述了 Modula-3 模式并将其与其他语言进行比较。Liskov 和 Gutau [LG86, p. 25] 可能将共享传递（call-by-sharing）对应于 Alonzo Church [Chu41] Lambda 函数中的参数传递，我们在 C-11.7 节中详细讨论了它。Thunk（节）最早由 Ingerman [Ing61] 描述。Fleck [Fc76] 讨论了使用调用参数编写交换程序时涉及的问题（例 9.10）。

Macaren [Mac77] 描述了 PL/I 中的异常处理。Ada 以及大多数现代语言的词法作用域替代方案很大借鉴了 Goodenough [Goo75] 的工作。Ada 的语义由 Luckham 和 Polak [LP80] 详尽描述。

> **John McCarthy (1927–2011)**，麻省理工学院和斯坦福大学长期教授，是人工智能领域的创始人之一。他在 1958 年引入了 Lisp，并对分时系统的早期开发以及使用数学逻辑推理计算机程序方面做出了贡献。他于 1971 年获得了 ACM 图灵奖。

Clu 的异常机制是一个有趣的历史先驱；细节可以在 Liskov 和 Snyder 的著作 [LS79] 中找到。Meyer [Mey92a] 讨论了 Eiffel 中的设计契约和异常处理。Friedman, Wand 和 Haynes [FWH01, Chaps. 8–9] 对 Scheme 中的延续传递风格（continuation-passing style）提供了很好的解释。

协程的早期描述出现在 Conway [Con63] 的工作中，他利用协程来表示编译的不同阶段。Bitwaterslide 等 [BDMN73] 为 Sim67 中使用协程进行仿真提供了教程性的介绍。仙人栈（Cactus stacks）至少追溯到 20 世纪 60 年代中期；Burroughs B6500 和 B7500 计算机直接在硬件支持 [HD68]。Murer 等人 [MOSS96] 讨论了 Sather 语言（Eiffel 的后代）中迭代器的实现。Von Behren 等人 [vCZ* 03] 描述了一个基于块的栈分配系统。

# 数据抽象与面向对象

**在第 3 章中，我们展示了数据抽象发展的几个阶段**，重点讨论了控制名称可见性的范围机制。我们从全局变量开始，其生命周期贯穿整个程序执行。接着我们增加了局部变量，其生命周期仅限于单个子程序的执行；嵌套作用域，允许子程序具有局部性；以及静态变量，其生命周期跨越执行过程，但名称仅在单个作用域内可见。随后是模块（modules），它们允许一组子程序共享一组静态变量；模块类型（module types），允许程序员实例化给定抽象的多个实例；以及类（classes），允许程序员定义一组相关的抽象。

普通模块鼓励一种“管理型”（manager）风格的编程，其中模块导出一个抽象类型。模块类型和类则允许模块本身成为抽象类型。这种区别在两个方面变得明显：首先，通常从管理模块中导出的创建和销毁例程被模块类型实例的创建和销毁所取代。其次，对特定模块中例程的调用取代了对期望导出类型作为参数的通用例程的调用。类在“模块即类型”的基础上增加了继承机制，这允许将新的抽象定义为现有抽象的细化或扩展；以及动态绑定，这允许抽象的新版本在期望旧版本的语境中使用时显示出新细化的行为。类的实例被称为对象；基于类的语言和编程技术被称为面向对象。¹

第 3 章介绍的数据抽象机制的步进式演进是组织思路的一种有效方法，但它并不能完全反映语言特征的历史演变。特别是，如果认为面向对象编程是作为模块的产物发展出来的，那是不准确的。

> 在之前的章节中，我们非正式地使用“对象”一词来指代几乎任何可以命名的东西。在本章中，我们仅用它来指代类的实例。

# 第 10 章 数据抽象与面向对象

事实上，面向对象编程的所有三个基本概念——封装、继承和动态方法绑定——都源于 Simula 编程语言，该语言是由挪威计算中心的 Ole-John Dahl 和 Kristen Nygaard 在 20 世纪 60 年代中期开发的。¹ 相比之下，与现代面向对象语言相比，Simula 在封装的数据隐藏部分表现较薄弱，而 Clu、Modula、Eiffel 以及相关语言在 20 世纪 70 年代这一领域做出了重要贡献。同时，继承和动态方法绑定的思想在 Smalltalk 在 20 世纪 70 年代被采用并完善。

Smalltalk 采用了一种独特的“基于消息”的模型，具有动态类型以及不寻常的术语和语法。动态类型导致实现相对较慢，并推迟了错误的报告。该语言还紧密集成到图形编程环境中，使其难以跨系统移植。由于这些原因，Smalltalk 的使用比人们预期的要少得多，但这对后续发展的影响巨大。Eiffel、C++、Ada 95、Fortran 2003、Java 和 C# 等语言代表了 Smalltalk 的继承和动态方法绑定与“主流”命令式语法和语义的高度整合。在另一种路径上，Objective-C 以相对纯粹且无格式的形式结合了 Smalltalk 风格的消息传递、动态类型与用于对象内操作的 C 语法。面向对象在函数式语言中也变得重要，例如 Common Lisp 对象系统（CLOS [Kee89;Ste90, Chap. 28]）以及 OCaml 的其他特性。

更多动态类型对象在 Python 和 Ruby 等语言中获得了新的流行，而静态类型对象则出现在 Scala 和 Go 等语言中。Swift 作为 Objective-C 的继承者，遵循了其前身（实际上是 OCaml）的模式，在原本静态类型的语言之上分层构建类型对象。

在 10.1 节中，我们提供了面向对象编程及其三个基本概念的概述。我们在 10.2 节中更详细地考虑封装和数据隐藏。我们在 10.3 节考虑面向对象和初始化，在 10.4 节考虑动态方法绑定。在 10.6 节（主要在辅助网站上）我们讨论了多继承，即根据多个已存在的类定义一个类。正如我们所看到的，多继承引入了一些棘手的语义和实现挑战。最后，在 10.7 节中，我们重新审视面向对象的定义，考虑语言在多大程度上可以将一切建模为对象。

> ¹ Nygaard（1912–2002）作为数学家、计算机语言先驱和社会活动家而广受赞誉。他的职业曾在挪威国防研究所、挪威运筹学会、挪威计算中心、奥胡斯大学和奥斯陆大学，以及各种劳工、政治和社会组织任职。Ole-John Dahl（1931–2002）也曾在挪威国防研究所任职，是挪威计算中心的创始成员，也是奥斯陆大学该系的创始人。Nygaard 和 Dahl 共同获得了 2001 年 ACM 图灵奖。

## 10.1 面向对象编程

我们的讨论大部分集中在 Smalltalk、Eiffel、C++ 和 Java，尽管我们也会提到许多其他语言。我们将在 14.4.4 节回到动态类型对象的主题。

面向对象编程可以看作是通过增强代码重用机会的一种尝试，即将新的抽象容易定义为现有抽象的扩展或细化。例如，首先考虑一个用双向链表实现的整数集合（我们稍后会考虑其他类型的集合）。示例 10.1 包含了我们集合元素的 C++ 代码。该示例采用了“模块-类”风格的抽象：每个元素都是 `list_node` 的独立对象。类包含了数据成员（`prev`、`next`、`head_node` 和 `val`）以及子程序成员（`predecessor`、`successor`、`insert_before` 和 `remove`）。子程序成员在许多面向对象语言中被称为方法；C++ 中的 `this` 关键字指的是当前执行方法的所属对象。在 Smalltalk 和 Objective-C 中，等效关键字是 `self`；在 Eiffel 中是 `current`。

假设已存在 `list_node` 类，我们可以这样定义整数列表：

```cpp
class list {
  list_node header;
public:
    // 不需要显式构造函数；
    // 隐式构造 'header' 即可
    int empty() {
      return header.singleton();
    }
  list_node* head() {
      return header.successor();
  }
  void append(list_node *new_node) {
    header.insert_before(new_node);
  }
  ~list() { // 析构函数
    if (!header.singleton()) {
      throw list_err("attempt to delete nonempty list");
    }
  }
};
```

为了创建一个空列表，可以写道：

```cpp
list* my_list_ptr = new list;
```

```cpp
class list_err {
// exception
public:
    const char *description;
    list_err(const char *s){description = s;}
};
```

```cpp
class list_node {
    list_node* prev;
    list_node* next;
    list_node* head_node;
public:
    int val;
    list_node() { // the actual data in a node
        prev = head_node; // point to self
        val = 0; // default value
    }
    list_node* predecessor() {
        if (prev == this || prev == head_node) return nullptr;
        return prev;
    }
    list_node* successor() {
        if (next == this || next == head_node) return nullptr;
        return next;
    }
    bool singleton() {
        return (prev == this);
    }
    void insert_before(list_node* new_node) {
        if (new_node->singleton())
            throw list_err("attempt to insert node already on list");
        prev->next = new_node;
        new_node->prev = prev;
        new_node->next = this;
        prev = new_node;
        new_node->head_node = head_node;
    }
    void remove() {
        if (singleton())
            throw list_err("attempt to remove node not currently on list");
        prev->next = next;
        next->prev = prev;
        prev = next = head_node; // point to self
    }
    ~list_node() { // destructor
        if (!singleton())
            throw new list_err("attempt to delete node still on list");
    }
};
```

图 10.1 一个 C++ 中用于列表节点的简单类。在这个示例中，我们想象了一个整数列表。

插入到列表中的记录创建方式非常相似：

```cpp
list_node* elem_ptr = new list_node;
```

在 C++ 中，人们可以简单地声明一个给定类的对象：

```cpp
list my_list;
list_node elem;
```

我们的列表类包含此类对象（头部）作为一个字段。当使用 `new` 创建时，对象被分配在堆上；当通过声明的扩展创建时，它被分配在静态或栈上，取决于生命周期（Eiffel 类将此类对象称为“展开对象”）。无论是在栈上还是堆上，对象的创建都会调用程序员指定的初始化路径，即构造函数。在 C++ 及其后代语言 Java 和 C# 中，构造函数的名称与类名本身相同。C++ 还允许程序员指定一个析构方法，该方法会在对象销毁时（通过程序员的显式操作或从其声明的子程序返回时）被自动调用。析构函数的名称同样是类的类名，但前面带有一个波浪号（`~`）。析构函数通常用于存储管理和错误检查。

### 内联（展开的）对象的声明

如果构造函数带有参数，则在声明内联对象或在堆上创建对象时，必须提供相应的参数。例如，假设我们的 `list_node` 构造函数被写为接收一个显式参数：

### 构造函数参数

```cpp
class list_node {
  ...
  list_node(int v) {
    prev = next = head_node = this;
    val = v;
  }
};
```

每个内联声明或对 `new` 的调用都需要提供一个值：

```cpp
list_node element1(0);      // 内联
list_node *e_ptr = new list_node(13); // 堆
```

正如我们在第 10.3.1 节看到的，C++ 实际上允许我们声明多个构造函数，并使用函数重载来区分它们：没有值的声明将调用无参数构造函数；带整数参数的声明将调用带参数构造函数。

### 公有成员

`list_node` 声明中的 `public` 标签将实现所需的成员与抽象的用户使用的成员分开。在第 3.3.4 节的术语中，出现在 `public` 标签之后的成员是从类导出的；出现在它之前的成员则不是。C++ 还提供了 `private` 标签，因此类的可见部分可以被列出（甚至可以穿插在）。在许多其他语言中，公共数据和子程序方法（字段和方法）必须单独标记（不需要显式列出）。在许多语言中——包括 C++——某些信息可以不在模块或类的初始声明，而在单独文件中提供。在我们的示例中，我们声明了 `list_node` 的公共方法但没有提供体：

### 没有定义的方法声明

```cpp
class list_node {
    list_node* prev;
    list_node* next;
    list_node* head_node;
public:
    int val;
    list_node();
    list_node* predecessor();
    list_node* successor();
    bool singleton();
    void insert_before(list_node* new_node);
    void remove();
    ~list_node();
};
```

这种简短的类声明可以放在 `.h` “头部”文件中，而方法分配到 `.cc` “实现”文件中。（C++ 分离编译的惯例类似于之前看到的 C 的。这里使用的后缀是 GNU 编译器所用的）。在 `.cc` 文件中，方法的头部必须使用 `::` 范围解析符来标识它所属的类：

### 单独的方法定义

```cpp
void list_node::insert_before(list_node* new_node) {
	if (new_node->singleton()) {
		throw new list_err("attempt to insert node already on list");
	}
	prev->next = new_node;
	new_node->prev = prev;
	new_node->next = this;
	prev = new_node;
	new_node->head_node = head_node;
}
```

### 微型子程序

面向对象的程序倾向于比普通程序进行更多的子程序调用，但子程序往往更短。在 Neumann 语言中通过直接访问记录字段完成许多工作在面向对象的语言中倾向于隐藏在对象方法内部。许多程序员认为声明公共字段是坏风格，因为这样做让抽象的用户直接访问内部表示，并使得在不更改用户代码的情况下无法更改该表示。可以说，我们将 `list_node` 的 `val` 变为一个属性，并带有 `get` 和 `set_val` 方法来读写它。

### C# 中的属性和索引器方法

```cpp
class list_node {
	...
	int val;
	// (小写 'v') 是私有的
	public int Val {
		get {
			return val;
		// get 访问器的存在是可选的
		// set 访问器意味着 Val 是属性
		}
		set {
			val = value;
		// value 是一个关键字：set 的参数
		}
	}
	...
};
```

`list_node` 类的用户可以通过（公有的）`Val` 属性访问（私有的）`val` 字段，就像它是一个字段一样：
