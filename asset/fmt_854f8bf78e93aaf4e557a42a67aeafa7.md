
Properties 对象是一个持久的 `Hashtable`，它存储 `String` 的键-值对——假设你使用 `setProperty` 和 `getProperty` 来操作表，而不是使用继承的 `Properties` 方法和 `get`。通过“持久化”，我们的意思是 `Properties` 对象可以被写入输出流（可能是文件）并通过输入流读回。在 Java 之前的版本中，`Properties` 对象的常见用途是维护应用程序的配置数据或用户偏好。[注意：Preferences API（包 `java.util.prefs`）旨在替代这种特定的 `Properties` 类用法，但它超出了本书的范围。要了解更多信息，请访问 http://bit.ly/JavaPreferences。] `Properties` 类扩展了 `Hashtable<Object, Object>`。图 16.19 展示了 `Properties` 类的几种方法。

第 13 行创建一个没有默认属性的空 `Properties`。`Properties` 类提供了一个重载构造函数，接收一个包含默认值的 `Properties` 对象的引用。第 16 行和第 17 行调用 `setProperty` 来设置属性。

```java
import java.util.*;
import java.io.*;
// Fig. 16.19 PropertiesTest.java
// Demonstrates class of java.util.
import java.io.*;
import java.util.*;

public class PropertiesTest {
    public static void main(String[] args) {
        // empty table
        Properties table = new Properties();
        // setting properties
        table.setProperty("color", "blue");
        table.setProperty("width", "200");
        table.setProperty("height", "red");
        table.setProperty("background", "yellow");

        // check if value is in
        Object value = table.getProperty("color");
        if (value != null) {
            // value is
            System.out.println("color is " + value);
        } else {
            // is not in table
            System.out.println("color is not in table");
        }

        // replace property
        table.setProperty("width", "300");
        System.out.println("width is now " + table.getProperty("width"));

        // remove property
        table.remove("height");
        if (table.getProperty("height") == null) {
            System.out.println("height was removed");
        }

        // output property values
        System.out.println("All properties:");
        // output name/value pairs
        table.list();
        
        // save properties to a file
        try {
            FileOutputStream output = new FileOutputStream("props.dat");
            // save properties
            table.store(output, "Sample Properties");
            output.close();
        } catch (IOException e) {
            e.printStackTrace();
        }

        // load properties from a file
        try {
            // load contents of table
            FileInputStream input = new FileInputStream("props.dat");
            // load properties
            table.load(input);
            input.close();
            System.out.println("After loading properties");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

第 13 行创建一个没有默认属性的空 `Properties`。`Properties` 类提供了一个重载构造函数，接收一个包含默认值的 `Properties` 对象的引用。第 16 行和第 17 行调用 `setProperty` 来设置属性。

## 16 Generic Collections

第 54 行调用 `store` 方法将 `Properties` 对象的内容保存到作为第一个参数指定的输出流中（在本例中为 `FileOutputStream`）。第二个参数 `String` 类型，是写入文件的描述。`Properties` 方法 `list` 接受一个 `PrintStream` 参数，对于显示属性列表非常有用。

第 38 行调用 `Properties` `getProperty` 来定位与指定键关联的值。如果在此 `Properties` 对象中未找到该键，`getProperty` 将返回 `null`。该方法的重载版本接收第二个参数，当 `getProperty` 无法定位键时指定默认值。

第 72 行调用 `Properties` 的 `load` 方法，从 `InputStream` 恢复 `Properties` 对象的内容（在这种情况下是 `FileInputStream`）。第 86 行调用 `Properties` 的 `keySet` 以获取属性的 `Set`。由于 `Properties` 类将其内容存储为 `Objects`，因此返回的是一个引用的 `Set`。第 91 行通过将键传递给 `get` 方法获取属性的值。

## 16.13 同步集合 (Synchronized Collections)

在第 23 章中，我们将讨论多线程。除了 `Vector` 和 `Hashtable` 之外，框架中的集合在不需要多线程时默认是非同步的。然而，由于它们不同步，多个线程并发访问某个 `Collection` 可能会导致不确定结果或致命错误——正如我们在第 23 章中所演示的。为了防止潜在的线程问题，对于可能被多个线程访问的集合使用了包装器（synchronization wrappers）。包装器接收方法调用，添加线程同步（以防止对集合的并发访问），并将调用委托给被包装的集合。`Collections` API 提供了一组静态方法来包装同步版本的集合。同步包装器的方法头列如图 20.20 所示。有关这些方法的细节可以参阅 http://docs.oracle.com/javase/7/docs/api/util/Collections.html。这些方法接受一个泛型并返回该泛型的同步视图。例如，以下代码创建了一个 `String` 类型的同步 `List(list)`：

```java
List<String> list1 = new ArrayList<>();
List<String> list2 = Collections.synchronizedList(list1);
```

```java
public static method headers

<T> Collection<T> synchronizedCollection(Collection<T> c)
<List<T>> synchronizedList(List<T> aList)
<Set<T>> synchronizedSet(Set<T> s)
<SortedSet<T>> synchronizedSortedSet(SortedSet<T> s)
<K, V> synchronizedMap(Map<K, V> m)
<K, V> synchronizedSortedMap(SortedMap<K, V> m)
```

**图 16.20** | 同步包装器方法。

## 16.14 不修改集合 (Unmodifiable Collections)

`Collections` 提供了一组静态方法，为集合创建不可修改的包装器。不可修改包装器在尝试修改集合时会抛出 `UnsupportedOperationException`。在不可修改的集合中，存储在集合中的引用是不可修改的，但它们引用的对象是可以修改的，除非它们属于像 `String` 这样的不可变类。这些方法的方法头列如图 16.21 所示。有关这些方法的细节可以参阅 http://docs.oracle.com/java/7/docs/api/java/util/Collections.html。所有这些方法都接受一个泛型并返回该泛型的不可修改视图。例如，该代码创建了一个存储 `String` 对象的不可修改 `List (List2)`：

```java
List<String> list1 = new ArrayList<>();
List<String> list2 = Collections.unmodifiableList(list1);
```

![](img/6851b408bcf88c7702f7d951642252f8_765_0.png)

### public static method headers

```java
<T> unmodifiableCollection(Collection<T> c)
<List<T>> unmodifiableList(List<T> alist)
<Set<T>> unmodifiableSet(Set<T> s)
<SortedSet<T>> unmodifiableSortedSet(SortedSet<T> s)
<K, V> Map<K, V> unmodifiableMap(Map<K, V> m)
<K, V> SortedMap<K, V> unmodifiableSortedMap(SortedMap<K, V> m)
```

**图 16.21** 不修改包装器。

## 16.15 抽象实现 (Abstract Implementations)

集合框架提供了 `Collection` 接口的各种抽象实现，通过这些实现你可以快速地“填充”自定义集合。这些抽象实现包括一个名为 `AbstractCollection` 的轻量 `Collection` 实现、一个允许对元素进行类数组访问的 `List` 实现 `AbstractList`、一个名为 `AbstractMap` 且允许对元素进行顺序访问（从头到尾）的 `AbstractSequentialList`、一个名为 `AbstractSet` 的 `Set` 实现以及一个名为 `AbstractQueue` 的 `Queue` 实现。你可以在 http://docs.oracle.com/javase/7/docs/api/java/util/package-summary.html 更多关于这些类的信息。要编写自定义实现，你可以扩展最符合你需求的抽象实现，实现类的每个抽象方法，并根据需要重写该类的具体方法。

## 16.16 总结 (Wrap-Up)

本章介绍了 Java 集合框架。你学习了集合框架架构以及如何使用它以多态的方式对集合进行编程。你使用了 `ArrayList` 和 `LinkedList` 类，它们都实现了 `List` 接口。我们展示了 Java 用于管理栈和队列的内置接口和类。你使用了几个预定义方法来操作集合。你学习了如何使用 `Set` 接口和 `HashSet` 类来操作无序的唯一值集合。我们继续介绍集合，引入了 `SortedSet` 接口类 `TreeSet` 用来操作排序的唯一值集合。然后，你还学习了 Java 用于操作键-值对的接口和类——`Map`、`SortedMap`、`Hashtable`、`HashMap` 和 `TreeMap`。我们讨论了专门的 `Properties` 类，用于操作可以存储到文件并从文件检索的字符串键值对。最后，我们讨论了 `Collections` 类的静态方法，用于获取集合的不可修改和同步视图。关于集合框架的更多信息，请访问 http://docs.oracle.com/javase/7/docs/guides/col-。在第 17 章“Java 8 Lambdas 和 Streams”中，你将使用 Java SE 8 的 Lambdas 和 Streams。在第 23 章“并发”中，你将学习如何使用并发集合来提高系统性能。

## 总结 (Summary)

### 16.1 引言 (Introduction)

- 集合框架提供了并发数据结构。

### 16.2 概述 (Overview)

- 集合框架提供了操作集合的方法和接口。

### 16.3 类型包装类 (Type-Wrapper Classes)

- 类型包装类（如 `Integer`、`Double`）。

### 16.4 装箱与自动拆箱 (Boxinging and Unboxing)

- 自动装箱将基本类型转换为对象。

### 16.5 Collection 接口和类 (Interface and Class)

- `Collection` 接口提供了操作集合的方法。

### 16.6 Lists (列表)

- `List` 接口由 `ArrayList` 和 `LinkedList` 实现。

### 16.7 Collections (类)

- `Collections` 类提供了静态方法。

### 16.8 Stack 类 (Class)

- `Stack` 类继承 `Vector`。

### 16.9 PriorityQueue 和 Queue 接口 (Interface)

- `Queue` 接口扩展了 `Collection` 并提供了插入、移除和检查元素的操作。

### 16.10 Sets (集合)

- `Set` 是一个不包含重复元素的无序 `Collection`。

# 自测练习题 725

- `HashMap` 接收两个参数——键的类型和值的类型。

- `HashMap` 方法 `put` (717) 向 `HashMap` 中添加一个键-值对。方法 `get` (717) 定位与指定键关联的值。方法 `isEmpty` (718) 判断映射是否为空。

- `HashMap` 方法 `keySet` (718) 返回一个键的集合。`Map` 方法 `size` (718) 返回映射中键-值对的数量。

- 接口 `SortedMap` (714) 继承 `Map`，并表示按排序顺序维护其键的映射。类 `TreeMap` 实现 `SortedMap`。

# 第 16.2 节 Properties

- `Properties` 对象 (718) 是 `Hashtable` 的持久化子类。

- `Properties` 无参数构造函数创建一个 `Properties` 表。重载的构造函数创建一个包含默认值的 `Properties` 对象。

- `Properties` 方法 `setProperty` (718) 将其作为参数指定与其键关联的值。方法 `store` (720) 将 `Properties` 对象的内容保存到指定的 `outputStream`。方法 `load` (721) 从指定的 `inputStream` 恢复 `Properties` 对象的内容。

# 第 16.3 节 同步集合

- 用于集合框架的 `Collections` 是未同步的。对于可以被多个线程同时访问的集合，提供了同步包装器 (p. 721)。

# 第 16.14 节 不可修改集合

- 不可修改集合包装器 (p. 721) 如果尝试修改集合，将抛出 `UnsupportedOperationException` (p. 694)。

# 第 16.15 节 抽象实现

- 集合框架提供了集合接口的各种抽象实现，你可以从这些实现中快速构建自定义实现。

# 自测练习题

16.1 填空每个语句的空白：

- a) 一种 ________ 用于遍历集合，并可以在迭代期间从集合中删除元素。

- b) 在 `List` 中，可以使用元素的 ________ 访问元素。

- c) 假设 `Array` 包含 `Double` 对象。

- d) Java 类 ________ 和 ________ 提供了可以动态调整大小的类数组数据结构的能力。

- e) 如果你不指定容量，系统将 ________，每个额外的容量都需要 ________。

- f) 你可以使用一个 ________ 创建一个集合，该集合对他人只提供读取访问，而对你自己允许读写。

- g) 假设 `Array` 包含 `Double` 对象，当执行语句 "double number = array[0]; execute" 时，会发生 ________。

- h) `Collections` 算法 ________ 确定两个集合是否有共同元素。
