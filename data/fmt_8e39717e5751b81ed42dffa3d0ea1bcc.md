
`print` 方法（图 21.23 的第 127–146 行）首先判断列表是否为空（第 129–133 行）。如果是，`print` 显示一条指示列表为空的消息并将 `current` 返回给调用方法。否则，`print` 输出列表的数据。第 126 行创建 `ListNode current` 并用 `firstNode` 初始化。当 `current` 不为 `null` 时，第 141 行输出 `current` 的字符串表示。第 142 行通过将引用 `current.nextNode` 的值赋值给 `current` 来移动到列表下一个节点。这种打印算法对于栈和队列是相同的。

## 21.4.10 创建自己的包

众所周知，包有助于分组相关的类型。例如，你可能会有一个用于应用程序的包，另一个用于数据。此外，包可以帮助防止命名冲突。本节介绍了如何创建和使用包，例如：

### 声明可重用的类

在类被导入到多个程序之前，必须被放在包中。创建可用的类的步骤如下：

- 声明一个或多个公共类型（类、枚举）。
- 选择一个唯一的包名并在源文件中添加包声明。
- 编译类型以便将它们放在相应的目录。
- 在程序中导入可重用的类型并使用它们。

我们将详细讨论这些步骤。

# 第21章 自定义泛型数据结构

## 全限定名

包名是全限定名的一部分，因此类 `List` 的名称实际上是 `com.deitel.datastructures.List`。你可以在程序中使用这个全限定名，也可以导入该类并在程序中使用其简单名（类名本身——`List`）。如果另一个包也包含一个 `List` 类，可以使用全限定名来区分程序中的不同类，并防止名称冲突（也称为命名冲突）。

### 步骤 3：编译类型

第 3 步是编译类以便将其存储在适当的包中。当编译包含包声明的 Java 文件时，生成的类文件被放置在由声明指定的目录中。`com.deitel.datastructures` 包中的类被放置在目录 `com/deitel/datastructures` 中。

包声明中的名称指定了包中类的精确位置。`javac` 命令行选项 `-d` 会导致编译器根据包声明创建目录。该选项还指定了包名中的顶层目录应该放置在系统的哪个位置——你可以为该位置指定相对路径或绝对路径。例如，命令

```
javac -d . List.java EmptyListException.java
```

指定我们的包名中的第一个目录（`com`）应该放在当前目录中。前一个命令中 `-d` 之后的点 (`.`) 代表 Windows、UNIX、Linux 和 Mac OS 操作系统（以及其他几个）上的当前目录。同样，命令

```
javac -d .. List.java EmptyListException.java
```

指定我们的包名中的第一个目录（`com`）应该放在父目录中——我们对本章中所有的可重用类都执行了此操作。现在你使用 `-d` 选项编译，包目录包含了 `ListNode.class`、`List.class` 和 `EmptyListException.class` 文件。

### 步骤 4：从你的包导入类型

一旦类型被编译到包中，就可以被导入（第 4 步）。类 `ListTest` 位于默认包中，因为它的 `.java` 文件不包含包声明。由于类 `ListTest` 与 `List` 以及 `EmptyListException` 位于不同的包中，你必须导入这些类以便 `ListTest` 使用它们（图 21.5 的第 3–4 行），或者你必须在 `ListTest` 类中所有使用 `List` 和 `EmptyListException` 的地方使用全限定名。例如，图 21.5 的第 10 行可以写成：

```
List<com.deitel.datastructures.Integer> list = new com.deitel.datastructures.List<>();
```

## 单类型导入 vs. 类型的按需导入声明

图 21.5 的第 3–4 行是单类型导入声明——它们每个指定一个要导入的类。当源码文件使用一个包中的多个类时，你可以使用形式如下的按需类型导入来导入这些类：

```
import packagename.*;
```

它在末尾使用星号 (`*`) 来通知编译器 `packagename` 包中的所有公类都可以在包含该导入语句的文件中使用。只有那些在执行时被使用的类会被加载。之前的 `import` 允许你使用 `packagename` 包中任何类型的简单名。在整本书中，我们提供单类型导入声明作为文档的一种，向你展示每个程序中具体使用了哪些类型。

## 常见编程错误 21.1

使用声明 `import java.*;` 会导致编译错误。你必须指定想要从哪个完整包名导入类。

## 错误预防提示 21.1

使用单类型导入声明通过只导入你在代码中实际使用的类型来避免命名冲突。

## 编译程序时指定类路径

编译 `ListTest` 时，`javac` 必须找到 `List` 和 `ListExtension` 的 `.class` 文件，以确保 `ListTest` 使用正确的编译器。编译器开始搜索一个名为类加载器的特殊对象来定位它需要的类。类加载器开始搜索绑定到 JDK 的 Java 类。然后它搜索可选包。Java 提供了一种扩展机制，允许为了开发和执行目的将（可选的）包添加到 Java 中。如果在标准 Java 类或扩展类中找不到该类，类加载器将搜索类路径——一个包含每个类型的目录或存档列表。每个目录或存档文件之间通过目录分隔符隔开——在 UNIX/Linux/Mac OS 上是冒号 (`:`)，在 Windows 上是分号 (`;`)。存档文件是包含其他文件目录的单个文件，通常采用压缩格式。例如，你的程序使用的标准类包含在 `rt.jar` 存档中，它是随 JDK 安装的。存档文件通常以 `.jar` 或 `.zip` 文件扩展名结尾。

默认情况下，类路径只包含当前目录。然而，可以通过以下方式修改类路径：

1. 向 `javac` 编译器提供 `-classpath` 选项
2. 设置 `CLASSPATH` 环境变量（一个你定义并由操作系统维护的特殊变量，程序可以在指定位置搜索类）。

如果你在不指定 `-classpath` 选项的情况下编译 `ListTest.java`，如下所示：

```
javac ListTest.java
```

类加载器假设 `ListTest` 程序使用的额外包位于当前目录中。正如我们提到的，我们将包放在了父目录中，以便本章中的其他程序可以使用。要编译 `ListTest.java`，请使用命令：

```
javac -classpath .. ListTest.java
```

在 UNIX/Linux/Mac OS 上，使用命令：

```
javac -classpath .. ListTest.java
```

在 Windows 上，类路径中的 `..` 允许类加载器定位 `com.deitel.datastructures` 的内容。

## 指定类路径执行程序

当你执行程序时，JVM 必须能够定位类的 `.class` 文件。与编译器一样，JVM 使用类加载器，它首先搜索标准类和扩展类，然后搜索类路径（默认是当前目录）。可以通过 `-classpath` 或 `-cp` 命令行选项显式指定类路径，后跟目录或存档列表。如果必须从当前目录加载类，请确保在类路径中包含点 (`.`) 以指定当前目录。执行 `ListTest` 程序，使用以下命令：

```
java -classpath .. ListTest
```

有关类路径的更多信息，请访问 `docs.oracle.com/javase/7/docs/technotes/tools/index.html#general`。

> **注意**：通常，使用编译器的 `-classpath` 选项而不是 `CLASSPATH` 环境变量来指定程序的类路径是更好的做法。这使得程序拥有自己的类路径。

> **注意**：使用 `CLASSPATH` 环境变量指定类路径会导致使用相同包不同程序的出现微妙且难以定位的错误。

# 21.5 栈

栈是一种受限列表——新节点只能在栈顶添加到栈或从栈中移除。因此，栈被称为后进先出（LIFO）数据结构。底端节点的 `link` 成员设置为 `null`——表示栈的底部。栈并不要求实现为链表——它可以使用数组来实现。

操作栈的主要方法是 `push`（推送）和 `pop`（弹出），它们分别向栈顶添加新节点和从栈顶移除一个节点。`pop` 方法还会返回被弹出节点的数据。

栈有许多有趣的应用。例如，当程序调用方法时，方法必须知道如何返回到调用者，调用方法的返回地址会被推入程序执行栈（在第 6.6 节中讨论）。如果发生了一系列调用，连续的返回地址将按照“先进后出”的顺序推入栈中，以便每个方法都能返回到其调用者。栈支持递归方法的方式与处理传统的递归方法相同。

程序执行栈还包含程序执行期间每个方法局部变量的内存空间。当方法返回到其调用者时，该方法的局部变量会从栈中弹出，程序将不再感知这些变量。如果局部变量是一个引用，且它所引用的对象没有其他变量引用它，则该对象可以被垃圾回收。

编译器使用栈来求算算术表达式并生成处理它们的机器语言代码。本章的练习探索了栈的若干应用，包括使用它们来开发完整的编译器。`java.util` 包包含了 `Stack` 类（第 16 章），用于实现和操作在程序执行期间动态增长和收缩的栈。

在本节中，我们利用列表与栈之间的紧密关系，通过重用 21.3 节的 `List` 类来实现一个栈。我们展示了两种不同的可用性形式。首先，我们通过组合一个指向 `List` 对象的引用作为私有实例变量，实现了一个性能完全相同的类。本章中的栈和队列数据结构被实现存储任何类型对象的引用，以鼓励进一步的可用性。

### 继承自 List 的类

21.10 和 21.11 创建并操作了一个扩展自 21.3 节中 `List` 类的栈。我们希望栈拥有 `push`、`pop`、`isEmpty` 和 `print` 方法。本质上讲，它们就是 `List` 的方法 `insertAtFront`、`removeFromFront`、`isEmpty` 和 `print`。当然，`List` 公共接口类中的所有方法也是子类 `StackInheritance` 的公共方法。`StackInheritance` 的每个方法都会调用相应的 `List` 方法——例如，方法 `push` 调用 `insertAtFront`，方法 `pop` 调用 `removeFromFront`。`StackInheritance` 的客户端可以调用 `isEmpty` 和 `print` 方法，因为它们继承自 `List`。`StackInheritance` 类声明在 `detail1.datastructures` 包中（第 3 行）供参考。`StackInheritance` 没有实现 `List`——这些类在同一个包中。

`StackInheritance` 的测试 `main` 方法（图 21.11）创建了 `StackInheritance` 类的对象 `stack`（第 10 行）。程序将整数推入栈中（第 13、15、17 和 19 行）。这里使用了自动装箱将 `Integer` 对象插入数据结构。第 27–32 行在无限 `while` 循环中从栈中弹出对象。如果在空栈上调用 `pop`，该方法将抛出 `EmptyListException`。在这种情况下，程序显示异常的堆栈跟踪，它显示了异常发生时程序执行栈上的方法。程序使用 `print` 方法（继承自 `List`）输出栈的内容。

```java
// Fig. 21.10: StackInheritance.java
// StackInheritance 继承自 List 类。
package com.deitel.datastructures;

public class StackInheritance<T> extends List<T> {
    // 构造函数
    public StackInheritance() {
        super("stack");
    }

    // 将对象添加到栈
    public void push(T object) {
        insertAtFront(object);
    }

    // 从栈中移除对象
    public T pop() throws EmptyListException {
        return removeFromFront();
    }
} // 类结束 StackInheritance
```

**图 21.10** | StackInheritance 继承自 List 类。

```java
// Fig. 21.11: StackInheritanceTest.java
// 栈操作程序。
import com.deitel.datastructures.StackInheritance;
import com.deitel.datastructures.EmptyListException;

public class StackInheritanceTest {
    public static void main(String[] args) {
        StackInheritance<Integer> stack = new StackInheritance<>();

        // 使用 push 方法
        stack.push(-1);
        stack.print();
        stack.push(0);
        stack.print();
        stack.push(1);
        stack.print();
        stack.push(5);
        stack.print();

        // 从栈中移除项
        try {
            int removedItem;
            while (true) {
                removedItem = stack.pop();
                System.out.printf("%d popped%n", removedItem);
            }
        } catch (EmptyListException emptyList) {
            System.out.println("stack is empty");
            emptyList.printStackTrace();
        }
    }
}
```

**图 21.11** | 栈操作程序。

输出：

```
-1 popped
0 popped
1 popped
5 popped
com.deitel.datastructures.EmptyListException: stack is empty
	at com.deitel.datastructures.List.removeFromFront(List.java:81)
	at com.deitel.datastructures.StackInheritance.pop(StackInheritance.java:22)
	at StackInheritanceTest.main(StackInheritanceTest.java:29)
```

### 通过组合而非继承形成栈类

实现栈类的一种方法是使用类组合。图 21.12 在 `Stack` 类声明中使用私有的 `List`（第 7 行）。组合使我们能够隐藏不在接口中的 `List` 方法。我们提供了所需的公共接口方法。将每个栈方法实现为对方法的调用被称为委托——栈调用相应的 `List` 方法。具体而言，`StackComposition` 委托了 `insertAtFront`、`removeFromFront` 和 `isEmpty` 的调用。在本示例中，我们没有显示 `StackCompositionTest`，因为唯一的区别是栈的类型从 `StackInheritance` 变为 `StackComposition`（第 3 和 10 行）。
