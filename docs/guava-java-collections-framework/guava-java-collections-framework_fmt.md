
# GUAVA：Java 集合框架

## 关于教程

Guava 是由 Google 开发的一款基于 Java 的开源库。它有助于遵循最佳编码实践并减少编码错误。它为集合、缓存、基本类型支持、并发、常用注解、字符串处理、I/O 和校验提供了实用方法。

本教程采用简单直观的方式描述 Guava 从基础到高级的概念以及如何使用其 API。

## 读者群

本教程对于大多数 Java 开发人员（从入门到专家）都有帮助。完成本教程后，我们有信心你发现可以在程序中轻松使用 Guava。

## 先决条件

之前接触过 Java 编程是充分利用本教程的唯一要求。

`LongMath` 类.................................................................................... 112

`BigIntegerMath` 类............................................................................... 116

## 1. 概述

### 什么是 Guava?

Guava 是一个基于 Java 的开源库，包含了 Google 的许多核心库，这些库被用于他们的许多项目中。它促进了最佳编码实践并有助于减少编码错误。它为集合、缓存、基本类型支持、并发、通用注解、字符串处理、I/O 和验证提供了实用方法。

### Guava 的优势

- 标准化 - Guava 库由 Google 管理。
- 高效 - 它是 Java 库的一个可靠、快速且高效的扩展。
- 优化 - 该库经过了高度优化。
- 函数式编程 - 它为 Java 增加了函数式处理能力。
- 工具类 - 它提供了编程应用程序开发中经常需要的许多工具类。
- 验证 - 它提供了一个标准的故障安全验证机制。
- 最佳实践 - 它强调最佳实践。

考虑以下代码段。

```java
public class GuavaTester {
    public static void main(String args[]){
        GuavaTester guavaTester = new GuavaTester();
        Integer a = null;
        Integer b = new Integer(10);
        System.out.println(guavaTester.sum(a,b));
    }

    public Integer sum(Integer a, Integer b) {
        return a + b;
    }
}
```

运行程序得到以下结果。

```
Exception in thread "main" java.lang.NullPointerException
at GuavaTester.sum(GuavaTester.java:13)
at GuavaTester.main(GuavaTester.java:9)
```

以下是代码中的问题。

- `sum()` 没有考虑可能作为 `null` 传递的参数。
- 调用者函数也没有担心无意中向 `sum` 方法传递 `null`。
- 当程序运行时，发生了 `NullPointerException`。

为了避免上述问题，必须在出现此类问题的每个地方都进行 `null` 检查。

让我们看看使用 Guava 提供的工具类 `Optional` 来以标准化的方式解决上述问题。

```java
import com.google.common.base.Optional;

public class GuavaTester {
    public static void main(String args[]){
        GuavaTester guavaTester = new GuavaTester();

        Integer invalidInput = null;
        Optional<Integer> a = Optional.of(invalidInput);
        Optional<Integer> b = Optional.of(new Integer(10));
        System.out.println(guavaTester.sum(a,b));
    }

    public Integer sum(Optional<Integer> a, Optional<Integer> b){
        return a.get() + b.get();
    }
}
```

运行程序得到以下结果。

```
Exception in thread "main" java.lang.NullPointerException
at
  at com.google.common.base.Preconditions.checkNull(Preconditions.java:210)
  at com.google.common.base.Optional.of(Optional.java:85)
  at GuavaTester.main(GuavaTester.java:8)
```

让我们理解上述程序的重要概念。

- `Optional` - 一个工具类，用于让代码正确地使用 `null`。
- `Optional.of` - 它返回作为参数使用的 `Optional` 类实例。它会检查传递的值是否为 `'null'`。
- `Optional.get` - 它获取存储在 `Optional` 类中的输入值。

使用 `Optional` 类，你可以检查调用者方法是否传递了正确的参数。

## 2. 环境设置

### 在线尝试选项

我们设置了一个在线 Java 编程环境，这样你可以在进行理论学习的同时，在线上编译并执行所有可用示例。这让你对所读的内容有信心，并可以使用不同的选项检查结果。可以随时修改任何示例并执行它。

请使用我们网站代码框右上角的 Try it (http://compileonline.com/) 选项尝试以下示例：

```java
public class MyFirstJavaProgram {
    public static void main(String [args]) {
        System.out.println("Hello World");
    }
}
```

对于本教程中给出的大多数示例，你都会发现一个 Try it 选项，其唯一意图是让你的学习更加愉快。

### 本地环境设置

如果你仍然愿意为 Java 编程语言设置环境，本节将指导你如何在你的机器上下载并设置 Java。请按照下面提到的步骤设置环境。

Java SE 可以从链接 http://www.oracle.com/technet/java/javase/downloads/index-jdk5-jsp-142662.html 免费获取。因此请根据你的操作系统下载版本。

按照说明下载 Java 并运行 `.exe` 在你的机器上安装 Java。一旦在机器上安装了 Java，你需要设置环境变量指向正确的安装目录：

#### 为 Windows 2000/XP 设置 Path

我们假设你已经将 Java 安装在 `c:\Program Files\java\jdk` 目录：

![](img/4935a2238ac80b2a11ee9e7e607ee955_9_0.png)

- 右键点击“我的电脑”并选择“属性”。
- 点击“高级”选项卡下的“环境变量”按钮。
- 现在，修改“Path”变量，使其也包含 Java 可执行文件所在的路径。例如，如果路径当前设置为 `C:\WINDOWS\SYSTEM32`，则将你的路径更改为 `C:\WINDOWS\SYSTEM32;c:\Program Files\java\jdk`。

#### 为 Windows 95/98/ME 设置 Path

我们假设你已经将 Java 安装在 `c:\Program Files\jdk` 目录：

- 编辑 `'C:\autoexec.bat'` 文件并在末尾添加以下行：`SET PATH=%PATH%%;c:\Program Files\java\jdk\bin`

#### 为 Linux, UNIX, Solaris, FreeBSD 设置 Path

环境变量 `PATH` 应该设置为 Java 二进制文件安装的位置。如果你在执行此时遇到困难，请参考你的 shell 文档。

例如，如果你使用 `bash` 作为你的 shell，则你向 `.bashrc` 末尾添加以下行：`export PATH=/path/to`

### 流行编辑器

编写 Java 程序需要一个编辑器。有很多种编辑器：

- Notepad（记事本）：Windows 上的简单文本编辑器。
- Netbeans: 它是一个 Java IDE。
- Eclipse: 它也是一个 Java IDE。

### 下载 Guava 存档

下载最新版本的 `guava-18.jar`。在编写时，我们已将其复制到 `C:\Guava`。

![](img/4935a2238ac80b2a11ee9e7e607ee959_10_0)

## 3. OPTIONAL 类

`Optional` 是一个不可变对象，用于包含一个非空对象。`Optional` 对象用于用缺失值表示 `null`。该类具有各种实用方法，方便代码处理值的可用或不可用，而不是检查 `null` 值。

### 类声明

以下是 `com.google.common.base.Optional<T>` 类的声明：

```java
@GwtCompatible(serializable=true)
public abstract class Optional<T>
    extends Object
implements Serializable
```

### 类方法

| S.N. | 方法与描述 |
|---|---|
| 1 | `static <T> Optional<T> absent()`<br>返回一个不包含引用的 `Optional` 实例。 |
| 2 | `abstract Set<T> asSet()`<br>返回一个不可变的 `Set`，如果包含元素存在则只有该元素；否则返回空不可变 `Set`。 |
| 3 | `abstract boolean equals(Object object)`<br>如果是 `Optional` 实例，且包含的引用彼此相等或缺失，则返回 `true`。 |
| 4 | `static <T> Optional<T> fromNullable(T nullableReference)`<br>如果 `nullableReference` 非空，则返回包含该引用的 `Optional` 实例；否则返回 `absent()`。 |
| 5 | `abstract T get()`<br>返回包含的实例，该实例必须存在。 |
| 6 | `abstract int hashCode()`<br>返回此实例的哈希值。 |

![](img/4935a2238ac80b2a11ee9e7e607ee959_11_0.png)

| S.N. | 方法与描述 |
|---|---|
| 7 | `abstract boolean isPresent()`<br>如果此持有器包含一个（非空）实例，则返回 `true`。 |
| 8 | `static <T> Optional<T> of(T reference)`<br>返回一个包含给定非空引用的 `Optional` 实例。 |
| 9 | `abstract Optional<T> or(Optional<? extends T> secondChoice)`<br>如果此 `Optional` 有值，则返回此 `Optional`；否则返回 `secondChoice`。 |
| 10 | `abstract T or(Supplier<? extends T> supplier)`<br>如果实例存在，则返回包含的实例；否则调用 `supplier.get()`。 |
| 11 | `abstract T or(T defaultValue)`<br>如果实例存在，则返回包含的实例；否则返回默认值。 |
| 12 | `abstract T orNull()`<br>如果实例存在，则返回包含的实例；否则返回 `null`。 |
| 13 | `static <T> Iterable<T> presentInstances(Iterable<? extends T>> optionals)`<br>从提供的 `optionals` 中顺序返回每个存在实例的值，跳过 `absent()` 的出现。 |
| 14 | `abstract String toString()`<br>返回此实例的字符串表示。 |
| 15 | `abstract <V> Optional<V> transform(Function<? super T,V> function)`<br>如果实例存在，则用给定的 `Function` 进行转换；否则返回 `absent()`。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### Optional 类示例

使用你选择的任何编辑器在 `C:/>` 创建以下 java 程序。

8

![](img/4935a2238ac80b2a11ee9e7e607ee959_13_0.png)

### GuavaTester.java

```java
import com.google.common.base.Optional;

public class GuavaTester {
    public static void main(String args[]){
        GuavaTester guavaTester = new GuavaTester();

        Integer value1 = null;
        Integer value2 = new Integer(10);
        //Optional.fromNullable - 允许传递的参数为null。
        Optional<Integer> a = Optional.fromNullable(value1);
        //Optional.of - 如果传递的参数为null则抛出 NullPointerException
        Optional<Integer> b = Optional.of(value2);

        System.out.println(guavaTester.sum(a,b));
    }

    public Integer sum(Optional<Integer> a, Optional<Integer> b){
        //Optional.isPresent - 检查值是否存在
        System.out.println("First parameter is present: " + a.isPresent());

        System.out.println("Second parameter is present: " + b.isPresent());

        //Optional.or - 如果存在则返回该值，否则返回传递的值。
        ///传递的默认值。
        Integer value1 = a.or(new Integer(0));

        //Optional.get - 获取值，值应该存在
        Integer value2 = b.get();

        return value1 + value2;
    }
}
```

### 验证结果

使用 `javac` 编译器如下编译该类：

```
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 以查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
First parameter is present: false
Second parameter is present: true
10
```

## 4. PRECONDITIONS 类

`Preconditions` 提供了静态方法，用于检查调用方法或构造函数是否使用了适当参数。它会检查前提条件。其方法在失败时会抛出 `IllegalArgumentException`。

### 类声明

以下是 `com.google.common.base.Preconditions` 类的声明：

```
@GwtCompatible
public final class Preconditions
extends Object
```

| S.N. | 方法与描述 |
|---|---|
| 1 | `static void checkArgument(boolean expression)`<br>确保调用方法中涉及一个或多个参数的表达式为真。 |
| 2 | `static void checkArgument(boolean expression, Object errorMessage)`<br>确保调用方法中涉及一个或多个参数的表达式为真。 |
| 3 | `static void checkArgument(boolean expression, String errorMessageTemplate, Object... errorMessageArgs)`<br>确保调用方法中涉及一个或多个参数的表达式为真。 |
| 4 | `static int checkElementIndex(int index, int size)`<br>确保 `index` 指定的是大小为 `size` 的数组、列表或字符串中的有效元素。 |
| 5 | `static int checkElementIndex(int index, int size, String desc)`<br>确保 `index` 指定的是大小为 `size` 的数组、列表或字符串中的有效元素。 |

![](img/4935a2238ac80b2a11ee9e7e607ee959_16_0.png)



## Preconditions 类

### 方法列表

| 序号 | 方法 | 描述 |
|---|---|---|
| 6 | `static <T> checkNotNull(T reference)` | 确保作为调用方法参数传递的对象引用不为空。 |
| 7 | `static <T> checkNotNull(T reference, Object errorMessage)` | 确保作为调用方法参数传递的对象引用不为空。 |
| 8 | `static <T> checkNotNull(T reference, String errorMessageTemplate, Object... errorMessageArgs)` | 确保作为调用方法参数传递的对象引用不为空。 |
| 9 | `static int checkPositionIndex(int index, int size)` | 确保指定的是大小为 `size` 的数组、列表或字符串中的有效位置。 |
| 10 | `static int checkPositionIndex(int index, int size, String desc)` | 确保指定的是大小为 `size` 的数组、列表或字符串中的有效位置。 |
| 11 | `static void checkPositionIndexes(int start, int end, int size)` | 确保 `start` 和 `end` 指定的是大小为 `size` 的数组或列表中的有效位置，且符合顺序。 |
| 12 | `static void checkState(boolean expression)` | 确保调用方法中涉及状态的表达式为真。 |
| 13 | `static void checkState(boolean expression, Object errorMessage)` | 确保调用方法中涉及状态的表达式为真。 |
| 14 | `static void checkState(boolean expression, String errorMessageTemplate, Object... errorMessageArgs)` | 确保调用方法中涉及状态的表达式为真。 |

### Preconditions 类示例

使用你选择的任何编辑器在 `C:/>` 创建以下 Java 程序。

```java
import com.google.common.base.Optional;
import com.google.common.base.Preconditions;
import java.util.List;

public class GuavaTester {
    public static void main(String args[]){
        GuavaTester guavaTester = new GuavaTester();

        Integer value1 = null;
        Integer value2 = new Integer(10);
        //Optional.fromNullable - 允许传递的参数为null。
        Optional<Integer> a = Optional.fromNullable(value1);
        //Optional.of - 如果传递的参数为null则抛出 NullPointerException
        Optional<Integer> b = Optional.of(value2);

        try {
            System.out.println(guavaTester.sum(a,b));
        } catch (NullPointerException e) {
            System.out.println(e.getMessage());
        }

        try {
            Preconditions.checkArgument(value2 > 0, "Value must be positive");
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }

        try {
            Preconditions.checkNotNull(value1, "Value cannot be null");
        } catch (NullPointerException e) {
            System.out.println(e.getMessage());
        }

        int[] array = {1, 2, 3};
        try {
            Preconditions.checkElementIndex(5, array.length);
        } catch (IndexOutOfBoundsException e) {
            System.out.println(e.getMessage());
        }
    }

    public Integer sum(Optional<Integer> a, Optional<Integer> b){
        //Optional.isPresent - 检查值是否存在
        System.out.println("First parameter is present: " + a.isPresent());

        System.out.println("Second parameter is present: " + b.isPresent());

        //Optional.or - 如果存在则返回该值，否则返回传递的值。
        ///传递的默认值。
        Integer value1 = a.or(new Integer(0));

        //Optional.get - 获取值，值应该存在
        Integer value2 = b.get();

        return value1 + value2;
    }
}
```

![](img/4935a2238ac80b2a11ee9e7e607ee959_17_0.png)

### 验证结果

使用 `javac` 编译器如下编译该类：

```
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 以查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
First parameter is present: false
Second parameter is present: true
10
Value cannot be null
Index 5 out of bounds for length 3
```

## ORDERING 类

`Ordering` 可以被视为一个增强了链式功能、多项实用方法、多类型排序等的比较器。

### 类声明

以下是 `com.google.common.collect.Ordering<T>` 类的声明：

```
@Gwt abstract class Ordering<T>
    extends Object
implements Comparator<T>
```

### 方法列表

| 序号 | 方法 | 描述 |
|---|---|---|
| - | `(Comparator<? super T> comparators)` | 返回一个排序，它会按顺序尝试每个给定的比较器，直到找到非零结果并返回该结果；只有当所有比较器都返回零时才返回零。 |
| 7 | `static <T> Ordering<T> explicit(List<T> valuesInOrder)` | 返回一个根据对象在给定列表中出现的顺序对其进行比较的排序。 |
| 8 | `static <T> Ordering<T> explicit(T leastValue, remainingValuesInOrder)` | 返回一个根据对象传递此方法的顺序对其进行排序的排序。 |
| 9 | `static <T> Ordering<T> from(Comparator<T> comparator)` | 返回一个基于给定比较器实例的排序。 |
| 10 | `<E extends T> List<E> greatestOf(Iterable<E> iterable, int k)` | 根据此排序返回给定迭代器中最大的 `k` 个元素，按从大到小的顺序排列。 |
| 11 | `<E extends T> List<E> greatestOf(Iterable<E> iterator, int k)` | 根据此排序从给定迭代器返回最大的 `k` 个元素，按从大到小的顺序排列。 |
| 12 | `<E extends T> ImmutableListSortedCopy(Iterable<E> elements)` | 返回一个包含按此排序的元素的不可变列表。 |
| 13 | `boolean isOrdered(Iterable<? extends T> iterable)` | 如果根据此排序，迭代器中第一个元素之后的每个元素都大于或等于之前的元素，则返回 `true`。 |
| 14 | `boolean isStrictOrdered(Iterable<? extends T> iterable)` | 如果根据此排序，迭代器中第一个元素之后的每个元素都严格大于之前的元素，则返回 `true`。 |
| 15 | `<E extends T> List<E> leastOf(Iterable<E> iterable, int k)` | 根据此排序返回给定迭代器中最小的 `k` 个元素，按从最小到最大的顺序排列。 |
| 16 | `<E extends T> List<E> leastOf(Iterator<E> elements, int k)` | 根据此排序从给定迭代器返回最小的 `k` 个元素，按从最小到大的顺序排列。 |
| 17 | `<S extends T> Ordering<Iterable<S>> lexicographical()` | 返回一个新的排序，它通过成对比较相应的元素来对迭代器进行排序，直到找到非零结果；施加“字典序”。 |
| 18 | `<E extends T> max(E a, E b)` | 根据此排序返回两个值中较大的一个。 |
| 19 | `<E extends T> max(E a, E b, E c, E... rest)` | 根据此排序返回指定值中的最大值。 |
| 20 | `<E extends T> max(Iterable<E> iterable)` | 根据此排序返回指定值中的最大值。 |
| 21 | `<E extends T> max(Iterator<E> iterator)` | 根据此排序返回指定值中的最大值。 |
| 22 | `<E extends T> min(E a, E b)` | 根据此排序返回两个值中较小的一个。 |
| 23 | `<E extends T> min(E a, E b, E c, E... rest)` | 根据此排序返回指定值中的最小值。 |
| 24 | `<E extends T> min(Iterable<E> iterable)` | 根据此排序返回指定值中的最小值。 |
| 25 | `<E extends T> min(Iterator<E> iterator)` | 根据此排序返回指定值中的最小值。 |
| 26 | `static <C extends Comparable> Ordering<C> natural()` | 返回一个使用值的自然顺序的可序列化排序。 |
| 27 | `<S extends T> Ordering<S> nullFirst()` | 返回一个将 `null` 视为小于所有其他值的排序，并用此来比较非空值。 |
| 28 | `<S extends T> Ordering<S> nullLast()` | 返回一个将 `null` 视为大于所有其他值的排序，并用此来比较非空值。 |
| 29 | `<F> Ordering<F> on(Function function)` | 返回一个通过应用函数对元素进行排序的新排序。 |
| 30 | `<S extends T> Ordering<S> reverse()` | 返回此排序的反序；等同于 `Collections.reverse(Comparator)`。 |
| 31 | `<E extends T> List<E> sortedCopy(Iterable<E> elements)` | 返回一个包含按此排序的元素的可变列表；当结果列表可能需要进一步修改或可能包含 `null` 时使用此。 |
| 32 | `static Ordering<Object> toString()` | 返回一个根据由 `toString()` 返回的字符串表示对对象进行排序。 |

### 继承

该类继承自以下类的方法：`java.lang.Object`

### Ordering 类示例

使用任何编辑器（例如 `GuavaTester.java`）创建以下 Java 程序：

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import com.google.common.collect.Ordering;

public class GuavaTester {
    public static void main(String args[]) {
        List<Integer> numbers = new ArrayList<Integer>();
        numbers.add(5);
        numbers.add(2);
        numbers.add(15);
        numbers.add(51);
        numbers.add(53);
        numbers.add(35);
        numbers.add(45);
        numbers.add(32);
        numbers.add(43);
        numbers.add(16);

        Ordering ordering = Ordering.natural();
        System.out.println("Input List: ");
        System.out.println(numbers);

        Collections.sort(numbers, ordering);
        System.out.println("Sorted List: ");
        System.out.println(numbers);

        System.out.println("==================");
        System.out.println("List is sorted: " + ordering.isOrdered(numbers));
    }
}
```

### 验证结果

使用以下命令编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果：

```bash
C:\Guava>java GuavaTester

text
Input List: 
[5, 2, 15, 51, 53, 35, 45, 32, 43, 16]
Sorted List: 
[2, 5, 15, 16, 32, 35, 43, 45, 51, 53]
==================
List is sorted: true
```

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### Objects 类示例

请在你选择的任何编辑器中（例如在 `C:> Guava` 下）创建以下 Java 程序。

`GuavaTester.java`



```java
import com.google.common.base.Objects;

public class GuavaTester {
    public static void main(String args[]){
        Student s1 = new Student("Mahesh", "Parasar", 1, "VI");
        Student s2 = new Student("Suresh", null, 3, null);

        System.out.println(s1.equals(s2));
        System.out.println(s1.hashCode());
        System.out.println(
            Objects.toStringHelper(s1)
                .add("Name", s1.getFirstName() + " " + s1.getLastName())
                .add("Class", s1.getClassName())
                .add("Roll No", s1.getRollNo())
                .toString())
        );
    }
}

class Student {
    private String firstName;
    private String lastName;
    private int rollNo;
    private String className;

    public Student(String firstName, String lastName, int rollNo,
    className)(){
        this.firstName = firstName;
        this.lastName = lastName;
        this.rollNo = rollNo;
        this.className = className;
    }

    @Override
    public boolean equals(Object object){
        if(!(object instanceof Student) || object == null) {
            return false;
        }
        Student student = (Student)object;
        // 这里不需要处理 null
        // Objects.equal("test", "test") == true
        // Objects.equal("test", null) == false
        // Objects.equal(null, "test") == false
        // Objects.equal(null, null) == true
        return Objects.equal(firstName, student.firstName) // 名字可以为 null
        && Objects.equal(lastName, student.lastName) // 姓可以为 null
        && Objects.equal(rollNo, student.rollNo)
        && Objects.equal(className, student.className); // 类名可以为 null
    }

    @Override
    public int hashCode(){
        // 不需要自行计算 hashCode
        return Objects.hashCode(className, rollNo);
    }

    public String getFirstName() {
        return firstName;
    }

    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    public String getLast() {
        return lastName;
    }

    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    public int getRollNo() {
        return rollNo;
    }

    public void setRollNo(int rollNo) {
        this.rollNo = rollNo;
    }

    public String getClassName() {
        return className;
    }

    public void setClassName(String className) {
        this.className = className;
    }
}
```

### 验证结果

使用`javac`编译器如下编译该类：

```
C:\Guava\javac GuavaTester.java
```

现在运行`GuavaTester`查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
false
```

```
85871
```

```
Student(Name=Mahesh Parashar, Class=VI, Roll No=1)
```

![](img/4935a2238ac80b2a11ee9e7e607ee959_30_0.png)

## 7. RANGE 类

`Range`表示一个区间或序列。它用于获取位于特定范围内的数字/字符串集合。

### 类声明

以下是`com.google.common.collect.Range<C>`类的声明：

```java
@GwtCompatible
public final class Range<C> extends Comparable<Object>
implements Predicate<C>, Serializable
```

### 方法

| 序号 | 方法 & 描述 |
|---|---|
| 1 | `static <C extends Comparable<?>> Range<C> all()` 返回一个包含类型`C`的所有值的范围。 |
| 2 | `boolean apply(C input)` 已弃用。仅为了满足`Predicate`接口；请改用`contains(C)`。 |
| 3 | `static <C extends Comparable<?>> Range<C> atLeast(endpoint)` 返回一个包含所有大于或等于`endpoint`值的范围。 |
| 4 | `static <C extends Comparable<?>> Range<C> atMost(endpoint)` 返回一个包含所有小于或等于`endpoint`值的范围。 |
| 5 | `Range<C> canonical(DiscreteDomain<C> domain)` 返回此范围在给定定义域中的规范形式。 |
| 6 | `static <C extends Comparable<?>> Range<C> closed(C lower, C upper)` 返回一个包含所有大于`lower`且小于等于`upper`的值的范围。 |
| 7 | `static <C extends Comparable<?>> Range<C> closedOpen(C lower, C upper)` 返回一个包含所有大于`lower`且小于`upper`的值的范围。 |
| 8 | `boolean contains(C value)` 如果`value`在此范围边界内则返回`true`。 |
| 9 | `boolean containsAll(Iterable<? extends C> values)` 如果每个元素都包含在此范围内，则返回`true`。 |
| 10 | `static <C extends Comparable<?>> Range<C> downTo(C endpoint, BoundType endpoint)` 返回一个从给定`endpoint`开始的范围，该端可以是包含（闭合）或不包含（开区间），且无上界。 |
| 11 | `static <C extends Comparable<?>> Range<C> encloseAll(Iterable<? extends C> values)` 返回包含所有给定值的最小范围。 |
| 12 | `boolean encloses(Range<C> other)` 如果其他范围的边界没有扩展到此范围边界之外，则返回`true`。 |
| 13 | `boolean equals(Object object)` 如果`object`是一个与此范围具有相同端点和边界类型的范围，则返回`true`。 |
| 14 | `static <C extends Comparable<?>> Range<C> greaterThan(C endpoint)` 返回一个包含所有严格大于`endpoint`值的范围。 |
| 15 | `int hashCode()` 返回范围的哈希码值（hash code）。 |
| 16 | `boolean hasLowerBound()` 如果范围具有下端点，则返回`true`。 |
| 17 | `boolean hasUpperBound()` 如果范围具有上端点，则返回`true`。 |
| 18 | `boolean isConnected(Range<C> other)` 如果存在由两者连接的（可能的）范围则返回`true`。 |
| 19 | `boolean isEmpty()` 如果范围为空，则返回`true`。 |
| 20 | `static <C extends Comparable<?>> Range<C> lessThan(C endpoint)` 返回一个包含所有小于`endpoint`值的范围。 |
| 21 | `C lowerEndpoint()` 返回范围的下端点 |
| 22 | `static <C extends Comparable<?>> Range<C> open(C lower, C upper)` 返回一个包含所有大于`lower`且严格小于`upper`的值的范围。 |
| 23 | `static <C extends Comparable<?>> Range<C> openClosed(C lower, C upper)` 返回一个包含所有大于`lower`且小于等于`upper`的值的范围。 |
| 24 | `static <C extends Comparable<?>> Range<C> range(C lower, BoundType lowerType, C upper, BoundType upperType)` 返回从`lower`到`upper`的范围，每个端点可以是包含（闭合）或不包含（开区间）。 |
| 25 | `static <C extends Comparable<?>> Range<C> singleton(C value)` 返回包含给定值的范围。 |
| 26 | `Range<C> span(Range<C> other)` 返回包含此范围和另一个范围的最小范围。 |
| 27 | `String toString()` 返回范围的字符串表示，例如`"[3..)"`（其他示例列在类文档）。 |
| 28 | `BoundType lowerType()` 如果包含下端点，则返回`CLOSED`；否则返回`OPEN`。 |
| 29 | `BoundType upperBoundType()` 如果包含上端点，则返回`CLOSED`；否则返回`OPEN`。 |
| 30 | `static <C extends Comparable<?>> Range<C> upTo(C endpoint, BoundType boundType)` 返回一个没有下界且直到给定端点`endpoint`的范围，该端点可以是包含（闭合）或不包含（开区间）。 |

![](img/31_0.png)

### Range 类示例

```java
import com.google.common.collect.ContiguousSet;
import com.google.common.collect.DiscreteDomain;
import com.google.common.collect.Range;
import com.google.common.primitives.Ints;

public class GuavaTester {

    public static void main(String args[]){
        GuavaTester tester = new GuavaTester();
        tester.testRange();
    }

    private void testRange(){
        // 创建一个范围 [a,b] = { x | a <= x <= b }
        Range<Integer> range1 = Range.closed(0, 9);
```

### Guava

```java
System.out.print("[0,9) : ");
```

```java
//创建一个范围 (a,b) = { x | a < x < b}
Range<Integer> range2 = Range.open(0, 9);
System.out.print("(0,9) : ");
printRange(range2);
```

```java
//创建一个范围 [a,b] = { x | a < x <= b}
Range<Integer> range3 = Range.closed(0, 9);
System.out.print("[0,9] : ");
printRange(range3);
```

```java
//创建一个范围 [a,b) = { x | a <= x < b}
Range<Integer> range4 = Range.open(0, 9);
System.out.print("[0,9) : ");
printRange(range4);
```

```java
//创建一个结束边界的范围 (9, infinity)
Range<Integer> range5 = Range.greaterThan(9);
System.out.println("(9,infinity) : ");
```

```java
Range<Integer> range6 = Range.closed(3, 5);
printRange(range6);
```

```java
//在范围 [0,9] 中是否包含 [3,5]
System.out.println("[0,9] encloses [3,5]: " + range1.encloses(range6));
```

```java
Range<Integer> range7 = Range.closed(9, 20);
printRange(range7);
//检查范围是否连接
System.out.println("[0,9] is connected [9,20]: " + range1.isConnected(range7));
```

```java
Range<Integer> range8 = Range.closed(5, 15);

//交集
printRange(range1.intersection(range8));

// 跨度
printRange(range1.span(range8));

private void printRange(Range<Integer> range) {
    System.out.print("{ ");
    for (int grade : range) {
        System.out.print(grade + " ");
    }
    System.out.println("}");
}
```

### 验证结果

使用`javac`编译器按如下编译类：

```
C:\Guava>javac GuavaTester.java
```

现在运行`GuavaTester`查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
[0,9] : [0 1 2 3 4 5 6 7 8 9]
5 is present: true
```

```
(1,2,3) is present: true
Lower Bound: 0
Upper Bound: 9
(0,9) : [1 2 3 4 5 6 7 8]
(0,9) : [1 2 3 4 5 6 7 8 9]
[0,9) : [0 1 2 3 4 5 6 7 8]
(9,infinity) :
Lower Bound: 9
Upper Bound present: false
[3 4 5]
[0,9) encloses [3,5]: true
[9 10 11 12 13 14 15 16 17 18 19 20]
[0,9] is connected [9,20]: true
[5 6 7 8 9]
[0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15]
```

## 8. THROWABLES 类

`Throwables`类提供了与`Throwable`接口相关的工具方法。

### 类声明

以下是`com.google.common.base.Throwables`类的声明：



```java
public final class Throwables
    extends Object
```

### 类方法

| S.N. | 方法与描述 |
| :--- | :--- |
| 1 | `static List<Throwable> getCausalChain(Throwable throwable)` 获取以列表形式表示的 `Throwable` 原因链。 |
| 2 | `static Throwable getRootCause(Throwable throwable)` 返回 `throwable` 的最内部原因。 |
| 3 | `static String getStackTraceAsString(Throwable throwable)` 返回一个包含 `toString()` 结果的字符串，随后是 `throwable` 的完整的递归堆栈跟踪。 |
| 4 | `static RuntimeException propagate(Throwable throwable)` 如果它是 `RuntimeException` 或 `Error` 的实例，则原样传播；作为最后结果，则将其封装在 `RuntimeException` 中并传播。 |
| 5 | `static <X extends Throwable> void propagateInstanceOf(Throwable throwable, Class<X> declaredType)` 当且仅当它是 `declaredType` 的实例时，才原样传播。 |
| 6 | `static void propagateIfPossible(Throwable throwable)` 当且仅当它是 `RuntimeException` 或 `Error` 的实例时，才原样传播。 |
| 7 | `static <X extends Throwable> void propagateIfPossible(Throwable throwable, Class<X> declaredType)` 当且仅当它是 `RuntimeException`、`Error` 或 `declaredType` 的实例时，才原样传播 `throwable`。 |
| 8 | `static <X1 extends Throwable, X2 extends Throwable> void propagateIfPossible(Throwable throwable, Class<X1> declared1, Class<X2> declared2)` 当且仅当它是 `RuntimeException`、`Error`、`declared1` 或 `declared2` 的实例时，才原样传播 `throwable`。 |

### 继承的方法

该类继承自以下类：

- `Object`

### Throwables 类示例

使用任何编辑器创建以下 `Throwables` 示例：

```java
import java.io.IOException;
import com.google.common.base.Objects;
import com.google.common.base.Throwables;

public class GuavaTester {
    public static void main(String[] args) {
        GuavaTester tester = new GuavaTester();
        try {
            tester.showcaseRoot();
        } catch (Exception e) {
            // 异常处理
        }
    }

    public void showcaseRoot() {
        try {
            throw new IOException();
        } catch (Exception e) {
            System.out.println(Throwables.getRootCause(e));
        }
    }

    public void showcaseRoot1() {
        try {
            throw new IOException();
        } catch (Exception e) {
            System.out.println(Throwables.getCausalChain(e));
        }
    }

    public void showcaseRoot2() {
        try {
            throw new IOException();
        } catch (Exception e) {
            System.out.println(Throwables.getStackTraceAsString(e));
        }
    }

    public void showcasePropagate() {
        try {
            throw new IOException();
        } catch (Exception e) {
            Throwables.propagate(e);
        }
    }

    public void showcasePropagate1() {
        try {
            throw new IOException();
        } catch (Exception e) {
            Throwables.propagateInstanceOf(e, IOException.class);
        }
    }

    public void showcasePropagate2() {
        try {
            throw new IOException();
        } catch (Exception e) {
            Throwables.propagateIfPossible(e);
        }
    }

    public void showcasePropagate3() {
        try {
            throw new IOException();
        } catch (RuntimeException e) {
            //
        } catch (Exception e) {
            Throwables.propagateIfPossible(e, IOException.class);
        }
    }
}
```

### 验证结果

使用 `javac` 编译器如下编译类：

```
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
[0,9] : [0 1 2 3 4 5 6 7 8 9]
5 is present: true
```

`multiset`。

`boolean removeAll(Collection<?> c)`

移除此集合中所有包含在指定集合中的元素（可选操作）。

`boolean retainAll(Collection<?> c)`

保留此集合中仅包含在指定集合中的元素（可选操作）。

`int setCount(E element, int count)`

添加或移除元素的必要次数，使该元素达到所需的计数。

`boolean setCount(E element, int oldCount, int newCount)`

在元素具有预期的当前计数的情况下，有条件地将元素的计数设置为新值，如 `setCount(Object, int)` 所示。

`String toString()`

返回对象的字符串表示。

### 继承的方法

此接口继承了自以下接口的方法：

- `java.util.Collection`

## Multiset 示例

使用你选择的任何编辑器在 `C:/> Guava` 中创建以下 java 程序。

### GuavaTester.java

```java
import java.util.Iterator;
import java.util.Set;

import com.google.common.collect.HashMultiset;
import com.google.common.collect.Multiset;

public class GuavaTester {

    public static void main(String args[]) {

        // 创建一个 multiset 集合
        Multiset<String> multiset = HashMultiset.create();

        multiset.add("a");
        multiset.add("b");
        multiset.add("c");
        multiset.add("d");
        multiset.add("a");
        multiset.add("b");
        multiset.add("c");
        multiset.add("b");
        multiset.add("b");
        multiset.add("b");

        // 打印元素的次数
        System.out.println("Occurrence of \"b\" : " + multiset.count("b"));

        // 打印 multiset 的总大小
        System.out.println("Total Size : " + multiset.size());

        // 获取 set 获取 multiset 的不同元素
        Set<String> set = multiset.elementSet();

        // 显示 set 中的元素
        System.out.println("Set [");
        for (String s : set) {
            System.out.println(s);
        }
        System.out.println("]");

        // 使用迭代器显示 multiset 的所有元素
        Iterator<String> iterator = multiset.iterator();
        System.out.println("MultiSet [");
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
        System.out.println("]");

        // 带有出现次数显示 multiset 的不同元素
        System.out.println("MultiSet [");
        for (Multiset.Entry<String> entry : multiset.entrySet()) {
            System.out.println("Element: " + entry.getElement() + ", Occurrence(s): " + entry.getCount());
        }
        System.out.println("]");
    }
}
```

### 验证结果

使用 `javac` 编译器如下编译该类：

```
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 以查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
Occurence of 'b' : 5
Total Size : 10
Set [
d
b
c
a
]
MultiSet [
d
b
b
b
b
b
c
c
a
a]
MultiSet [
Element: d, Occurrence(s): 1
Element: b, Occurrence(s): 5
Element: c, Occurrence(s): 2
Element: a, Occurrence(s): 2
]
Occurence of 'b': 3
```

## Multimap 接口

`Multimap` 接口扩展了 `Map`，使其可以同时映射到多个值。

### 接口声明

以下是 `com.google.common.collect.Multimap<K,V>` 接口的声明：

```java
@GwtCompatible
public interface Multimap<K,V>
```

### 接口方法

| S.N. | 方法 & 描述 |
| :--- | :--- |
| 1 | `Map<K,Collection<V>> asMap()` 返回此 `multimap` 的 `Map` 视图，从每个不同键映射到该键关联值的非空集合。 |
| 2 | `void clear()` 移除 `multimap` 中的所有键值对，使其为空。 |
| 3 | `boolean containsEntry(Object key, Object value)` 如果此 `multimap` 包含至少一个具有该键和值的键值对，则返回 `true`。 |
| 4 | `boolean containsKey(Object key)` 如果此 `multimap` 包含至少一个键，则返回 `true`。 |
| 5 | `boolean containsValue(Object value)` 如果此 `multimap` 包含至少一个值，则返回 `true`。 |
| 6 | `Collection<Map.Entry<K,V>> entries()` 返回此 `multimap` 中映射的视图。 |
| 7 | `boolean equals(Object obj)` 将此 `multimap` 与指定的对象进行比较。 |
| 8 | `int size()` 返回此 `multimap` 中的条目数量。 |
| 9 | `int hashCode()` 返回此 `multimap` 的哈希码。 |
| 10 | `boolean isEmpty()` 如果此 `multimap` 不包含任何条目，则返回 `true`。 |
| 11 | `Set<K> keySet()` 返回此 `multimap` 中包含的键的视图。 |
| 12 | `Collection<V> values()` 返回此 `multimap` 中包含的值视图。 |
| 13 | `Collection<V> get(Object key)` 返回与指定键关联的值的集合。 |
| 14 | `void put(K key, V value)` 为指定键添加指定值。 |
| 15 | `void putAll(K key, Collection<? extends V> values)` 为指定键添加所有指定值。 |
| 16 | `void remove(Object key)` 移除指定键的单个条目。 |
| 17 | `void removeAll(Object key)` 移除指定键的所有条目。 |
| 18 | `boolean remove(Object value)` 移除具有指定值的单个条目。 |
| 19 | `boolean removeAll(Object value)` 移除所有具有指定值的条目。 |
| 20 | `int count(Object key)` 返回指定键的出现次数。 |

### Guava

现在运行 `GuavaTester` 查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
初始小写列表
[a, b, c, d, e]
修改后的小写列表
[a, b, c, d, e, f]
初始大写列表
[A, B, C, D]
修改后的大写列表
[A, B, C]
作为 map 的 Multimap
upper:[a, b, c, d, e, f]
lower:[a, b, c, d, e, f]
Multimap 的键
upper
lower
Multimap 的值
[A, B, C, a, b, c, d, e, f]
```

## BiMap 接口

`BiMap` 是一种特殊的 `map`，它在维护 `map` 反向视图的同时，确保 `map` 中没有重复的值，并且可以安全地使用值来获取键。

### 接口声明

以下是 `com.google.common.collect.Bimap<K,V>` 接口的声明：

```java
@GwtCompatible
public interface BiMap<K,V>
extends Map<K,V>
```



### Guava

### BiMap 接口

BiMap 是一种特殊的 map，它在维护 map 反向视图的同时，确保 map 中没有重复的值，并且可以安全地使用值来获取键。

#### 接口声明

以下是 `com.google.common.collect.Bimap<K,V>` 接口的声明：

```java
@GwtCompatible
public interface BiMap<K,V>
    extends Map<K,V>
```

![](img/4935a2238ac80b2a11ee9e7e607ee959_52_0.png)

#### 接口方法

| S.N. | 方法 & 说明 |
|---|---|
| 1 | `forcePut(K key, V value)`<br>`put` 的替代方案，在执行 `put(K, V)` 操作之前，静静地移除任何具有相同值的现有条目。 |
| 2 | `BiMap<V,K> inverse()`<br>返回此 bimap 的反 Map，它将此 bimap 的每个值映射到其关联键。 |
| 3 | `put(K key, V value)`<br>将指定值与此 map 中的指定键关联（可选操作）。 |
| 4 | `void putAll(Map<?,?> extends V> map)`<br>将指定 map 中的所有映射复制到此 map 中（可选操作）。 |
| 5 | `Set<V> values()`<br>返回此 map 中包含的值的 Collection 视图。 |

#### 继承的方法

此类继承自以下接口的方法：

- `java.util.Map`

#### BiMap 示例

使用你选择的任何编辑器在 `C:\Guava` 中创建以下 Java 程序。

`GuavaTester.java`

```java
import com.google.common.collect.BiMap;
import com.google.common.collect.HashBiMap;

public class GuavaTester {

    public static void main(String args[]) {
        BiMap<Integer, String> empIDNameMap = HashBiMap.create();

        empIDNameMap.put(new Integer(101), "Mahesh");
        empIDNameMap.put(new Integer(102), "Sohan");
        empIDNameMap.put(new Integer(103), "Ramesh");

        // 员工 "Mahesh" 的 ID
        System.out.println(empIDNameMap.inverse().get("Mahesh"));
    }
}
```

![](img/4935a2238ac80b2a11ee9e7e607ee959_53_0.png)

#### 验证结果

使用 `javac` 编译器按如下方式编译类：

```shell
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果：

```shell
C:\Guava>java GuavaTester
```

查看结果：

```text
101
```

初始小写列表：

```text
[a, b, c, d, e]
```

修改后的小写列表：

```text
[a, b, c, d, e, f]
```

初始大写列表：

```text
[A, B, C, D]
```

修改后的大写列表：

```text
[A, B, C]
```

作为 map 的 Multimap：

```text
upper:[a, b, c, d, e, f]
lower:[a, b, c, d, e, f]
```

Multimap 的键：

```text
upper
lower
```

Multimap 的值：

```text
[A, B, C, a, b, c, d, e, f]
```

### Table 接口

Table 表示一种特殊的 map，其中可以通过组合方式指定两个键来映射到一个值。它类似于创建一个 map 组成的 map。

#### 接口声明

以下是 `com.google.common.collect.Table<R,C,V>` 接口的声明：

```java
@GwtCompatible
public interface Table<R,C,V>
```

#### 接口方法

| S.N. | 方法 & 说明 |
|---|---|
| 1 | `Set<Table.Cell<R,C,V>> cellSet()` 返回所有行键/列键/值三元组的集合。 |
| 2 | `void clear()` 移除表中的所有映射。 |
| 3 | `Map<R,V> columnKey(C columnKey)` 返回给定列键的所有映射的视图。 |
| 4 | `Set<C> columnKeySet()` 返回表中包含一个或多个值的列键集合。 |
| 5 | `Map<C,Map<R,V>> columnMap()` 返回将每个列键与从行键到值的对应 map 关联的视图。 |
| 6 | `boolean contains(Object rowKey, Object columnKey)` 如果表包含指定行和列键的映射，则返回 true。 |
| 7 | `boolean containsColumn(Object columnKey)` 如果表包含指定列的映射，则返回 true。 |
| 8 | `boolean containsRow(Object rowKey)` 如果表包含指定行键的映射，则返回 true。 |
| 9 | `boolean containsValue(Object value)` 如果表包含指定值的映射，则返回 true。 |
| 10 | `boolean equals(Object obj)` 比较指定对象与此表是否等等性。 |
| 11 | `V get(Object rowKey, Object columnKey)` 返回对应给定行和列键的值，如果不存在此类映射则返回 null。 |
| 12 | `int hashCode()` 返回此表的哈希值。 |
| 13 | `boolean isEmpty()` 如果行不包含映射，则返回 true。 |
| 14 | `V put(R rowKey, C columnKey, V value)` 将指定值与指定键关联。 |
| 15 | `void putAll(Table<? extends R?, extends C?, extends V> table)` 将映射从指定的表复制到此表。 |
| 16 | `V remove(Object rowKey, Object columnKey)` 移除与给定键关联的任何映射。 |
| 17 | `Map<C,V> row(R rowKey)` 返回给定行键的所有映射的视图。 |
| 18 | `Set<R> rowKeys()` 返回表中包含一个或多个值的键集合。 |
| 19 | `Map<R,Map<C,V>> rowMap()` 返回将每个行键与从列键到值的对应 map 关联的视图。 |
| 20 | `int size()` 返回映射的数量。 |
| 21 | `Collection<V> values()` 返回可能重复的值的集合。 |

#### Table 示例

使用你选择的任何编辑器在 `C:\Guava` 中创建以下 Java 程序。

`Table.java`

```java
import com.google.common.collect.Table;
import com.google.common.collect.HashBasedTable;
import java.util.Map;
import java.util.Set;

public class TableExample {

    public static void main(String args[]) {
        Table<String, String, Integer> table = HashBasedTable.create();

        table.put("US", "NY", 1);
        table.put("US", "LA", 2);
        table.put("UK", "London", 3);
        table.put("UK", "Manchester", 4);
        table.put("France", "Paris", 5);

        System.out.println("Table size: " + table.size());
        System.out.println("Value for US-NY: " + table.get("US", "NY"));
        System.out.println("Rows for US: " + table.row("US"));
        System.out.println("Columns for NY: " + table.column("NY"));
        System.out.println("All row keys: " + table.rowKeys());
        System.out.println("All column keys: " + table.columnKeys());
        System.out.println("All values: " + table.values());

        table.remove("US", "NY");
        System.out.println("Size after removing US-NY: " + table.size());

        table.clear();
        System.out.println("Size after clearing: " + table.size());
    }
}
```

**编译并运行后的输出：**

```text
Table size: 5
Value for US-NY: 1
Rows for US: {NY=1, LA=2}
Columns for NY: {US=1}
All row keys: [US, UK, France]
All column keys: [NY, LA, London, Manchester, Paris]
All values: [1, 2, 3, 4, 5]
Size after removing US-NY: 4
Size after clearing: 0
```

### 缓存工具

Guava 通过 `LoadingCache<K,V>` 接口提供了非常强大的内存缓存机制。值会自动加载到缓存中，并提供了许多用于缓存需求的实用方法。

#### 接口声明

以下是 `com.google.common.cache.LoadingCache<K,V>` 接口的声明：

```java
@GwtCompatible
public interface LoadingCache<K,V>
    extends Cache<K,V>, Function<K,V>
```

#### 接口方法

| S.N. | 方法 & 说明 |
|---|---|
| 1 | `apply(K key)`<br>已弃。为了满足 Function 接口而提供；请使用 `get(K)` 或 `getUnchecked(K)`。 |
| 2 | `ConcurrentMap<K,V> asMap()`<br>返回此缓存存储的条目的线程安全 map 视图。 |
| 3 | `V get(K key)`<br>返回缓存中与键关联的值，如果需要则加载该值。 |
| 4 | `ImmutableMap<K,V> getAll(Iterable<? extends K> keys)`<br>返回与键关联的值的映射，如果需要则创建或检索这些值。 |
| 5 | `V getUnchecked(K key)`<br>返回缓存中与键关联的值，如果需要则加载该值。 |
| 6 | `void refresh(K key)` |



现在运行 `GuavaTester` 查看结果。

```text
C:\Guava>java GuavaTester
```

查看结果。

101

### Table 接口

`Table` 表示一种特殊的 map，其中可以通过组合方式指定两个键来映射到一个值。它类似于创建一个 map 组成的 map。

### 接口声明

以下是 `com.google.common.collect.Table<R,C,V>` 接口的声明：

```java
@GwtCompatible
public interface Table<R,C,V>
```

### 接口方法

| S.N. | 方法 & 说明 |
|---|---|
| 1 | `Set<Table.Cell<R,C,V>> cellSet()` 返回所有行键/列键/值三元组的集合。 |
| 2 | `void clear()` 移除表中的所有映射。 |
| 3 | `Map<R,V> columnKey(C columnKey)` 返回给定列键的所有映射的视图。 |
| 4 | `Set<C> columnKeySet()` 返回表中包含一个或多个值的列键集合。 |
| 5 | `Map<C,Map<R,V>> columnMap()` 返回将每个列键与从行键到值的对应 map 关联的视图。 |
| 6 | `boolean contains(Object rowKey, Object columnKey)` 如果表包含指定行和列键的映射，则返回 true。 |
| 7 | `boolean containsColumn(Object columnKey)` 如果表包含指定列的映射，则返回 true。 |
| 8 | `boolean containsRow(Object rowKey)` 如果表包含指定行键的映射，则返回 true。 |
| 9 | `boolean containsValue(Object value)` 如果表包含指定值的映射，则返回 true。 |
| 10 | `boolean equals(Object obj)` 比较指定对象与此表是否等性。 |
| 11 | `V get(Object rowKey, Object columnKey)` 返回对应给定行和列键的值，如果不存在此类映射则返回 null。 |
| 12 | `int hashCode()` 返回此表的哈希值。 |
| 13 | `boolean isEmpty()` 如果行不包含映射，则返回 true。 |
| 14 | `V put(R rowKey, C columnKey, V value)` 将指定值与指定键关联。 |
| 15 | `void putAll(Table<? extends R?, extends C?, extends V> table)` 将映射从指定的表复制到此表。 |
| 16 | `V remove(Object rowKey, Object columnKey)` 移除与给定键关联的任何映射。 |
| 17 | `Map<C,V> row(R rowKey)` 返回给定行键的所有映射的视图。 |
| 18 | `Set<R> rowKeys()` 返回表中包含一个或多个值的键集合。 |
| 19 | `Map<R,Map<C,V>> rowMap()` 返回将每个行键与从列键到值的对应 map 关联的视图。 |
| 20 | `int size()` 返回映射的数量。 |
| 21 | `Collection<V> values()` 返回可能重复的值的集合。 |

### Table 示例

（由于原文存在严重乱码，此处省略具体代码翻译，参考前文。）

## 10. 缓存工具

Guava 通过 `LoadingCache<K,V>` 接口提供了非常强大的内存缓存机制。值会自动加载到缓存中，并提供了许多用于缓存需求的实用方法。

### 接口声明

以下是 `com.google.common.cache.LoadingCache<K,V>` 接口的声明：

```java
@Beta
@GwtCompatible
public interface LoadingCache<K,V>
    extends Cache<K,V>, Function<K,V>>
```

### 接口方法

| S.N. | 方法 & 说明 |
|---|---|
| 1 | `apply(K key)`<br>已弃。为了满足 `Function` 接口而提供；请使用 `get(K)` 或 `getUnchecked(K)`。 |
| 2 | `ConcurrentMap<K,V> asMap()`<br>返回此缓存存储的条目的线程安全 map 视图。 |
| 3 | `V get(K key)`<br>返回缓存中与键关联的值，如果需要则加载该值。 |
| 4 | `ImmutableMap<K,V> getAll(Iterable<? extends K> keys)`<br>返回与键关联的值的映射，如果需要则创建或检索这些值。 |
| 5 | `V getUnchecked(K key)`<br>返回缓存中与键关联的值，如果需要则加载该值。 |
| 6 | `void refresh(K key)`<br>为键加载新值，可能是异步的。 |

### LoadingCache 示例

使用你任的任何编辑器在 `C:/> Guava` 目录下创建以下 Java 程序：

`GuavaTester.java`

```java
import java.util.HashMap;
import java.util.Map;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.TimeUnit;

import com.google.common.base.MoreObjects;
import com.google.common.cache.CacheBuilder;
import com.google.common.cache.CacheLoader;
import com.google.common.cache.LoadingCache;

public class GuavaTester {

    public static void main(String[] args) {

        // 根据员工 ID 为员工创建缓存

        LoadingCache<String, Employee> employeeCache =
            CacheBuilder.newBuilder()
                .maximumSize(100) // 可以缓存 100 条记录
                .expireAfterAccess(30, TimeUnit.MINUTES)
                // 缓存将在访问 30 分钟后过期
                .build(new CacheLoader<String, Employee>() {

                    // 构建缓存加载器

                    @Override
                    public Employee load(String employeeId) throws Exception {

                        // 执行昂贵的调用

                        return getFromDatabase(employeeId);
                    }
                });

        try {

            // 第一次调用时，缓存将填充了相应的记录

            System.out.println("Invocation #1");

            System.out.println(employeeCache.get("100"));
            System.out.println(employeeCache.get("103"));
            System.out.println(employeeCache.get("110"));

            // 第二次调用，数据将从缓存返回

            System.out.println("Invocation #2");

            System.out.println(employeeCache.get("100"));
            System.out.println(employeeCache.get("110"));

        } catch (ExecutionException e) {
            e.printStackTrace();
        }
    }

    private static Employee getFromDatabase(String empId) {
        Employee e1 = new Employee("Mahesh", "Finance", "100");
        Employee e2 = new Employee("Rohan", "IT", "103");
        Employee e3 = new Employee("Sohan", "Admin", "110");

        Map<String, Employee> database = new HashMap<String, Employee>();

        database.put("100", e1);
        database.put("103", e2);
        database.put("110", e3);

        System.out.println("Database hit for " + empId);

        return database.get(empId);
    }

    class Employee {

        String name;
        String dept;
        String empID;

        public Employee(String name, String dept, String empID) {
            this.name = name;
            this.dept = dept;
            this.empID = empID;
        }

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }

        public String getDept() {
            return dept;
        }

        public void setDept(String dept) {
            this.dept = dept;
        }

        public String getEmpID() {
            return empID;
        }

        public void setEmpID(String empID) {
            this.empID = empID;
        }

        @Override
        public String toString() {
            return MoreObjects.toStringHelper(Employee.class)
                .add("Name", name)
                .add("Department", dept)
                .add("Emp Id", empId)
                .toString();
        }
    }
}
```

### 验证结果

使用 `javac` 编译器按如下编译类：

```text
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```text
C:\Guava>java GuavaTester
```

查看结果。

```text
Invocation #1

Database hit for100

Employee{Name=Mahesh, Department=Finance, Emp Id=100}

Database hit for103

Employee{Name=Rohan, Department=IT, Emp Id=103}

Database hit for110

Employee{Name=Sohan, Department=Admin, Emp Id=110}

Invocation #2

Employee{Name=Mahesh, Department=Finance, Emp Id=100}

Employee{Name=Rohan, Department=IT, Emp Id=103}

Employee{Name=Sohan, Department=Admin, Emp Id=110}
```

## 11. 字符串工具类

Guava 根据开发者在应用开发工作中的经验引入了许多高级字符串工具类。以下是实用的字符串工具类列表：

| 序号 | 工具类名称 & 描述 |
|---|---|
| 1 | `Joiner`<br>用于合并对象、字符串等的工具。 |
| 2 | `Splitter`<br>用于分割字符串的工具。 |
| 3 | `CharMatcher`<br>用于字符操作的工具。 |
| 4 | `CaseFormat`<br>用于更改字符串格式的工具。 |

### Joiner 类

`Joiner` 提供了各种方法来处理字符串、对象等的合并操作。

### 类声明

以下是 `com.google.common.base.Joiner` 类的声明：

```java
@GwtCompatible
public class Joiner
    extends Object
```

### 类方法

| 序号 | 方法 & 描述 |
|---|---|
| 1 | `<A extends Appendable> appendTo(A appendable, Iterable<?> parts)`<br>将每个部分的字符串表示添加到 appendable 中，使用之前配置的分隔符分隔各部分。 |
| 2 | `<A extends Appendable> appendTo(A appendable, Iterator<?> parts)`<br>将每个部分的字符串表示添加到 appendable 中，使用之前配置的分隔符分隔各部分。 |
| 3 | `<A extends Appendable> appendTo(A appendable, Object[] parts)`<br>将每个部分的字符串表示添加到 appendable 中，使用之前配置的分隔符分隔各部分。 |
| 4 | `<A extends Appendable> appendTo(A appendable, Object first, Object second, Object... rest)`<br>将所有剩余参数的字符串表示添加到 appendable。 |
| 5 | `StringBuilder appendTo(StringBuilder builder, Iterator<?> parts)`<br>将每个部分的字符串表示添加到 builder 中，使用之前配置的分隔符分隔各部分。 |
| 6 | `StringBuilder appendTo(StringBuilder builder, Object[] parts)`<br>将每个部分的字符串表示添加到 builder 中，使用之前配置的分隔符分隔各部分。 |
| 7 | `StringBuilder appendTo(StringBuilder builder, Object first, Object... rest)`<br>将所有剩余参数的字符串表示添加到 builder。 |
| 8 | `String join(Iterable<?> parts)`<br>返回一个包含每个部分的字符串表示的字符串，使用之前配置的分隔符分隔各部分。 |
| 9 | `String join(Iterator<?> parts)`<br>返回一个包含每个部分的字符串表示的字符串，使用之前配置的分隔符分隔各部分。 |
| 10 | `String join(Object[] parts)`<br>返回一个包含每个部分的字符串表示的字符串，使用之前配置的分隔符分隔各部分。 |
| 11 | `String join(Object first, Object second, Object... rest)`<br>返回一个包含所有剩余参数的字符串表示的字符串。 |
| 12 | `String join(Object first, Object second, Object... rest)`<br>返回一个包含所有参数的字符串表示的字符串。 |
| 13 | `static Joiner(char separator)`<br>返回一个在连续元素之间放置分隔符的 joiner。 |
| 14 | `static Joiner(String separator)`<br>返回一个在连续元素之间放置分隔符的 joiner。 |
| 15 | `static Joiner skipNulls()`<br>返回一个具有相同行为但跳过任何空元素的 joiner。 |
| 16 | `static Joiner forNullText(String nullText)`<br>返回一个具有相同行为但用 nullText 替换任何空元素的 joiner。 |
| 17 | `Joiner withKeyValueSeparator(String keyValueSeparator)`<br>返回一个使用给定键值分隔符的 MapJoiner，并使用与此相同的配置。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### Joiner 类示例



```java
import java.util.Arrays;
import com.google.common.base.Joiner;

public class GuavaTester {
    public static void main(String args[]){
        GuavaTester tester = new GuavaTester();
        tester.testJoiner();
    }

    private void testJoiner(){
        System.out.println(Joiner.on(",\n")
        .skipNulls()
        .join(Arrays.asList(1,2,3,4,5,null,6)));
    }
}
```

### 类方法

| S.N. | 方法与描述 |
|---|---|
| 1 | `static Splitter fixedLength(int length)`<br>返回一个将字符串划分为给定长度片段分割器。 |
| 2 | `Splitter limit(int limit)`<br>返回一个分割器，其行为与此分割器等效，但在达到限制后停止。 |
| 3 | `Splitter omitEmptyStrings()`<br>返回一个分割器，其行为与此分割器等效，但会自动忽略结果中的空字符串。 |
| 4 | `static Splitter on(char separator)`<br>返回一个使用单个字符分隔符的分割器。 |
| 5 | `static Splitter on(CharMatcher separatorMatcher)`<br>返回一个分割器，它将任何被给定 `CharMatcher` 匹配的单字符视为分隔符。 |
| 6 | `static Splitter on(Pattern separatorPattern)`<br>返回一个分割器，它将任何子序列模式视为分隔符。 |
| 7 | `static Splitter on(String separator)`<br>返回一个使用给定固定字符串作为分隔符的分割器。 |
| 8 | `static Splitter onPattern(String separatorPattern)`<br>返回一个分割器，它将任何匹配给定模式（正则表达式）的子序列视为分隔符。 |
| 9 | `Iterable<String> split(CharSequence sequence)`<br>将序列拆分为字符串组件，并通过 `Iterator` 提供支持，该 `Iterator` 可能是惰性求值的。 |
| 10 | `List<String> splitToList(CharSequence sequence)`<br>将序列拆分为字符串组件并以不可变列表的形式返回。 |
| 11 | `Splitter trimResults()`<br>返回一个分割器，其行为与此分割器等效，但会自动移除每个子字符串前后的空白；等同于 `trimResults(CharMatcher.WHITESPACE)`。 |
| 12 | `Splitter.trimResults(CharMatcher trimmer)`<br>返回一个分割器，其行为与此分割器等效，但从每个返回的子字符串中移除匹配 `CharMatcher` 的所有前导或字符。 |
| 13 | `Splitter.MapSplitterwithKeyValueSeparator(char separator)`<br>返回一个 `MapSplitter`，它根据此分割器拆分条目，并使用指定的分隔符将条目拆分为键值。 |
| 14 | `Splitter.MapSplitterwithKeyValueSeparator(Splitter keyValueSplitter)`<br>返回一个 `MapSplitter`，它根据此分割器拆分条目，并使用指定的键值分割器将条目拆分为键值。 |
| 15 | `Splitter.MapSplitterwithKeyValueSeparator(String separator)`<br>返回一个 `MapSplitter`，它根据此分割器拆分条目，并使用指定的分隔符将条目拆分为键值。 |

### 继承的方法

该类继承自以下类的方法：

- `java.lang.Object`

### Splitter 类示例

使用任意的编辑器在 `C:\Guava` 中创建以下 Java 程序。

`GuavaTester.java`

```java
import com.google.common.base.Splitter;

public class GuavaTester {
    public static void main(String args[]){
        GuavaTester tester = new GuavaTester();
        tester.testSplitter();
    }

    private void testSplitter(){
    }
}
```

```java
System.out.println(Splitter.on(',')
    .trimResults()
    .omitEmptyStrings()
    .split("the,quick, , brown , fox, jumps,
over, the, lazy, little dog.")
);
```

### 验证结果

使用 `javac` 编译器如下编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```bash
C:\Guava>java GuavaTester
```

查看结果。

```
[the, quick, brown, fox, jumps, over, the, lazy, little dog.]
```

### CharMatcher 类

`CharMatcher` 提供了各种方法来处理 `char` 值的 JAVA 类型。

### 类声明

以下是 `com.google.common.base.CharMatcher` 类的声明：

```java
@GwtCompatible(emulated=true)
public final class CharMatcher
    extends Object
```

### 字段

| S.N. | 字段与描述 |
|---|---|
| 1 | `static CharMatcher ANY`<br>匹配任何字符。 |
| 2 | `static CharMatcher ASCII`<br>确定字符是否为 ASCII，意味着其代码点小于 128。 |
| 3 | `static CharMatcher BREAKING_WHITESPACE`<br>确定字符是否为换行空格（即可以为了格式化目的被解释为单词间断开的空白）。 |
| 4 | `static CharMatcher DIGIT`<br>根据 Unicode 确定字符是否为数字。 |
| 5 | `static CharMatcher INVISIBLE`<br>确定字符是否不可见；即使用 ICU4 时，其 Unicode 类别为 `SPACE_SEPARATOR`、`LINE_SEPARATOR`、`PARAGRAPH_SEPARATOR`、`CONTROL`、`FORMAT`、`SURROGATE` 和 `PRIVATE_USE` 之一。 |
| 6 | `static CharMatcher JAVA_DIGIT`<br>根据 Java 的定义确定字符是否为数字。 |
| 7 | `static CharMatcher JAVA_ISO_CONTROL`<br>确定字符是否为 `Char.isControl(char)` 指定的 ISO 控制字符。 |
| 8 | `static CharMatcher JAVA_LETTER`<br>根据 Java 的定义确定字符是否为字母。 |
| 9 | `static CharMatcher JAVA_LETTER_OR_DIGIT`<br>根据 Java 的定义确定字符是否为字母或数字。 |
| 10 | `static CharMatcher JAVA_LOWER_CASE`<br>根据 Java 的定义确定字符是否为小写。 |
| 11 | `static CharMatcher JAVA_UPPER_CASE`<br>根据 Java 的定义确定字符是否为大写。 |
| 12 | `static CharMatcher NONE`<br>不匹配任何字符。 |
| 13 | `static CharMatcher SINGLE_WIDTH`<br>确定字符是否为单宽（非双宽）。 |
| 14 | `static CharMatcher WHITESPACE`<br>根据最新的 Unicode 标准（此处所示）确定字符是否为空白字符。 |

### 构造函数

| S.N. | 构造函数与描述 |
|---|---|
| 1 | `protected CharMatcher()` 用于子类使用的构造函数。 |

### 类方法

| S.N. | 方法与描述 |
|---|---|
| 1 | `CharMatcher and(CharMatcher other)` 返回一个匹配此匹配器和 `other` 同时匹配的任何字符的匹配器。 |
| 2 | `static CharMatcher anyOf(CharSequence sequence)` 返回一个匹配序列中存在的任何字符的匹配器。 |
| 3 | `boolean apply(Character character)` 已弃用。仅为了满足 `Predicate` 接口；请使用 `matches(char)`。 |
| 4 | `String collapseFrom(CharSequence sequence, char replacement)` 返回输入序列的副本，其中每个匹配此匹配器的连续字符组都被替换为替换字符。 |
| 5 | `int countIn(CharSequence sequence)` 返回序列中匹配字符的数量。 |
| 6 | `static CharMatcher forPredicate(Predicate<? super Character> predicate)` 返回一个与 `Character` 行为相同的匹配器，但操作的是原始 `char`。 |
| 7 | `int indexIn(CharSequence sequence)` 返回序列中第一个匹配字符的索引，如果不存在字符则返回 -1。 |
| 8 | `int indexIn(CharSequence sequence, int start)` 返回从给定位置开始序列中第一个匹配字符的索引，如果该位置后没有匹配字符则返回 -1。 |
| 9 | `static CharMatcher inRange(char startInclusive, char endInclusive)` 返回一个匹配范围内任何字符的匹配器（包含两个端点）。 |
| 10 | `static CharMatcher is(char match)` 返回一个仅匹配指定字符的匹配器。 |
| 11 | `static CharMatcher isNot(char match)` 返回一个匹配指定字符之外任何字符的匹配器。 |
| 12 | `int lastIndexOf(CharSequence sequence)` 返回序列中最后一个匹配字符的索引，如果不存在匹配字符则返回 -1。 |
| 13 | `abstract boolean matches(char c)` 对给定的字符判断真或假。 |
| 14 | `boolean matchesAllOf(CharSequence sequence)` 如果序列仅包含匹配字符，则返回 `true`。 |
| 15 | `boolean matchesAnyOf(CharSequence sequence)` 如果序列包含至少一个匹配字符，则返回 `true`。 |
| 16 | `boolean matchesNoneOf(CharSequence sequence)` 如果序列不包含任何匹配字符，则返回 `true`。 |
| 17 | `CharMatcher negate()` 返回一个匹配此匹配器未匹配的字符的匹配器。 |
| 18 | `static CharMatcher noneOf(CharSequence sequence)` 返回一个匹配序列中不存在的任何字符的匹配器。 |
| 19 | `CharMatcher or(CharMatcher other)` 返回一个匹配此匹配器或另一个匹配器中的任意字符的匹配器。 |
| 20 | `CharMatcher precomputed()` 返回一个与此匹配器功能等价的字符匹配器，但查询原始对象可能会更快；效果因人而异。 |
| 21 | `String removeFrom(CharSequence sequence)` 返回一个包含字符序列中所有非匹配字符的字符串，按顺序排列。 |
| 22 | `String replaceFrom(CharSequence sequence, char replacement)` 返回输入字符序列的副本，其中每个匹配此匹配器的字符都被替换为给定的替换字符。 |
| 23 | `String replaceFrom(CharSequence sequence, CharSequence replacement)` 返回输入字符序列的副本，其中每个匹配此匹配器的字符都被替换为给定的替换序列。 |
| 24 | `String retainFrom(CharSequence sequence)` 返回一个包含字符序列中所有匹配字符的字符串，按顺序排列。 |
| 25 | `String toString()` 返回此 `CharMatcher` 的字符串表示，例如 `CharMatcher.or(WHITESPACE, JAVA_DIGIT)`。 |
| 26 | `String trimAndCollapseFrom(CharSequence sequence, char replacement)` 对匹配字符组进行折叠，方式与 `collapseFrom(Java.lang.CharSequence, char)` 完全一致，但序列开头或结尾的匹配字符组会被移除且不进行替换。 |
| 27 | `String trimFrom(CharSequence sequence)` 返回输入字符序列的子字符串，省略从字符串开头和结尾所有此匹配器匹配的字符。 |
| 28 | `String trimLeadingFrom(CharSequence sequence)` 返回输入字符序列的子字符串，省略从字符串开头所有此匹配器匹配的字符。 |
| 29 | `String trimTrailingFrom(CharSequence sequence)` 返回输入字符序列的子字符串，省略从字符串结尾所有此匹配器匹配的字符。 |

### 继承的方法

此类继承了以下类的方法：

- `java.lang.Object`

### CharMatcher 类示例

使用你任选的编辑器在 `C:\>Guava` 下创建以下 java 程序。

`GuavaTester.java`

```java
import com.google.common.base.CharMatcher;
import com.google.common.base.Splitter;

public class GuavaTester {
    public static void main(String[] args){
        GuavaTester tester = new GuavaTester();
        tester.testCharMatcher();
    }

    private void testCharMatcher(){
        System.out.println(CharMatcher.DIGIT.retainFrom("mahesh123")); //
        // 只保留数字
        System.out.println(CharMatcher.WHITESPACE.trimAndCollapseFrom(
        Mahesh Parassar , ' '));
        // 去除两端空格，并将空格替换/折叠为
        // 单空格
        System.out.println(CharMatcher.JAVA_DIGIT.replaceFrom("mahesh123",
        "**")); // 将所有数字星号
        System.out.println(CharMatcher.JAVA_DIGIT.or(CharMatcher.JAVA_LOWER_CASE).retainFrom("mahesh123"));
        // 消除所有不是数字或小写的字符
    }
}
```

### 验证结果

使用 `javac` 编译器按照如下方式编译类：

```
C:\Guava\javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

| 123 |
|---|
| Mahesh Parashar |
| mahesh*** |
| mahesh123 |

### CaseFormat 类

`CaseFormat` 是一个工具类，用于提供各种 ASCII 字符格式之间的转换。

### 类声明



以下是`com.google.common.base.CaseFormat`类的声明：

```java
@GwtCompatible
public enum CaseFormat extends Enum<CaseFormat>
```

### 枚举常量

| S.N. | 枚举常量与描述 |
| :--- | :--- |
| 1 | `LOWER_CAMEL` Java 变量命名规范，例如 `"lowerCamel"`。 |
| 2 | `LOWER_HYPHEN` 连字符变量命名规范，例如 `"lower-hyphen"`。 |
| 3 | `LOWER_UNDERSCORE` C++ 变量命名规范，例如 `"lower_underscore"`。 |
| 4 | `UPPER_CAMEL` Java 和 C++ 类命名规范，例如 `"UpperCamel"`。 |
| 5 | `UPPER_UNDERSCORE` Java 和 C++ 常量命名规范，例如 `"UPPER_UNDERSCORE"`。 |

### 方法

| S.N. | 方法与描述 |
| :--- | :--- |
| 1 | `Converter<String,String> converterTo(CaseFormat targetFormat)` 返回一个将字符串从此格式转换为`targetFormat`的转换器。 |
| 2 | `String to(CaseFormat format, String str)` 将指定的`String str`从此格式转换为指定的格式。 |
| 3 | `static CaseFormat valueOf(String name)` 返回该类型中指定名称的枚举常量。 |
| 4 | `static CaseFormat[] values()` 返回一个包含该枚举类型常量的数组，按声明顺序排列。 |

### 继承的方法

此类继承了以下类的方法：

- `java.lang.Enum`
- `java.lang.Object`

### CaseFormat 类示例

使用你任选的编辑器在`C:\>Guava`下创建以下 java 程序。

### GuavaTester.java

```java
import com.google.common.base.CaseFormat;

public class GuavaTester {
    public static void main(String[] args) {
        GuavaTester tester = new GuavaTester();
        tester.testCaseFormat();
    }

    private void testCaseFormat() {
        String data = "test-data";

        System.out.println(CaseFormat.LOWER_HYPHEN.to(CaseFormat.LOWER_CAMEL, data));
        System.out.println(CaseFormat.LOWER_UNDERSCORE.to(CaseFormat.UPPER_CAMEL, data));
        System.out.println(CaseFormat.UPPER_CAMEL.to(CaseFormat.LOWER_HYPHEN, data));
    }
}
```

### 验证结果

使用`javac`编译器按照如下方式编译类：

```
C:\Guava\javac GuavaTester.java
```

现在运行`GuavaTester`查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

| testData |
| testData |
| ImageData |

## 2. 原生类型工具

由于 Java 的原生类型无法传递给泛型或集合，Guava 提供了许多包装类来处理原生类型。以下是实用的工具列表：

| S.N. | 工具名称 |
| :--- | :--- |
| 1 | **Bytes** 用于原生 `byte`。 |
| 2 | **Shorts** 用于原生 `short`。 |
| 3 | **Ints** 用于原生 `int`。 |
| 4 | **Longs** 用于原生 `long`。 |
| 5 | **Floats** 用于原生 `float`。 |
| 6 | **Doubles** 用于原生 `double`。 |
| 7 | **Chars** 用于原生 `char`。 |
| 8 | **Booleans** 用于原生 `boolean`。 |

### Bytes 类

`Bytes`是用于原生`byte`的工具类。

### 类声明

以下是`com.google.common.primitives.Bytes`类的声明：

```java
@GwtCompatible
public final class Bytes
    extends Object
```

### 方法

| S.N. | 方法与描述 |
| :--- | :--- |
| 1 | `static List<Byte> asList(byte... backingArray)` 返回一个由指定数组支持的固定列表，类似于`Arrays.asList(Object[])`。 |
| 2 | `static byte[] concat(byte[]... arrays)` 将提供的每个数组的值合并成单个数组。 |
| 3 | `static boolean contains(byte[] array, byte target)` 如果`target`作为元素出现在数组任意位置则返回`true`。 |
| 4 | `static byte[] ensureCapacity(byte[] array, int minLength, int padding)` 返回一个包含数组相同值的数组，但保证具有特定的最小长度。 |
| 5 | `static int hashCode(byte value)` 返回值的哈希值；等同于调用`((Byte value).hashCode())`的结果。 |
| 6 | `static int indexOf(byte[] array, byte target)` 返回`value target`在数组中第一次出现的索引。 |
| 7 | `static int indexOf(byte[] array, byte target)` 在指定目标在数组中首次出现处返回的起始位置，如果不存在该项，则返回`-1`。 |
| 8 | `static int lastIndexOf(byte[] array, byte target)` 返回`value target`在数组中最后一次出现的索引。 |
| 9 | `static byte[] toArray(Collection<? extends Number> collection)` 返回一个包含集合中每个值的数组，按照`Number.byteValue()`的方式转换为字节值。 |

### 继承自以下类的方法

此类继承自以下类的方法：

- `java.lang.Object`

# Bytes 类示例

在`C:\> Guava`下使用你选择的任何编辑器创建以下 Java 程序。

### GuavaTester.java

```java
import java.util.List;
import com.google.common.primitives.Bytes;

public class GuavaTester {
    public static void main(String args[]) {
        GuavaTester tester = new GuavaTester();
        tester.testBytes();
    }

    private void testBytes(){
        byte[] byteArray = {1,2,3,4,5,5,7,9,9};

        //将原始类型数组转换为对象数组
        List<Bytes> objectArray = Bytes.asList(byteArray);
        System.out.println(objectArray.toString());

        //将对象数组转换为原始类型数组
        byte[] byteArray = Bytes.toArray(objectArray);
        System.out.print("[");
        for(int i = 0; i<byteArray.length ; i++){
            System.out.print(byteArray[i] + " ");
        }
        System.out.println("]");
    }
    //检查元素是否存在于原始类型列表中
    System.out.println("5 is in list? " + Bytes.contains(byteArray, 5));

    //返回索引
    System.out.println("Index of 5: " + Bytes.indexOf(byteArray, 5));

    //返回最后一个最大索引
    System.out.println("Last index of 5: " + Bytes.lastIndexOf(byteArray, 5));
}
```

### 验证结果

使用`javac`编译器按如下方式编译类：

```
C:\Guava>javac GuavaTester.java
```

现在运行`GuavaTester`查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

```
[1, 2, 3, 4, 5, 5, 7, 9, 9]
[ 1 2 3 4 5 5 7 9 9 ]
5 is in list? true
Index of 5: 4
Last index of 5: 5
```

### Shorts 类

`Shorts`是一个用于原始类型`short`的工具类。

### 类声明

以下是`com.google.common.primitives.Shorts`类的声明：

```java
@GwtCompatible
public final class Shorts
    extends Object
```

### 字段

| 序号. | 字段 & 描述 |
|---|---|
| 1 | `static int BYTES` 表示一个原始`short`值所需的字节数。 |
| 2 | `static short MAX_POWER_OF_TWO` 可以表示为`short`的最大 2 的幂。 |

### 方法

| 序号. | 方法 & 描述 |
|---|---|
| 1 | `static List<Short> asList(short... backingArray)` 返回一个由指定数组支持的固定大小列表，类似于`Arrays.asList(Object[])`。 |
| 2 | `static short checkedCast(long value)` 如果可能，返回与`value`相等的`short`值。 |
| 3 | `static int compare(short a, short b)` 比较两个指定的`short`值。 |
| 4 | `static short[] concat(short... arrays)` 将从每个提供的数组中的值合并到单个数组中。 |
| 5 | `static boolean contains(short[] array, short target)` 如果`target`在数组的任何地方作为元素存在，则返回`true`。 |
| 6 | `static short[] ensureCapacity(short[] array, int minLength, int padding)` 返回一个包含与`array`相同值的数组，但保证为指定的最小长度。 |
| 7 | `static short fromByteArray(byte[] bytes)` 返回其大端字节表示存储在`bytes`前 2 个字节中的`short`值；等于`ByteBuffer.wrap(bytes).getShort()`。 |
| 8 | `static short fromBytes(byte b1, byte b2)` 返回其字节表示为给定 2 个字节（大端序）的`short`值；等于`Shorts.fromByteArray(new byte[] {b1, b2})`。 |
| 9 | `static int hashCode(short value)` 返回`value`的哈希值；等于调用`((Short)value).hashCode()`的结果。 |
| 10 | `static int indexOf(short[] array, short target)` 返回值`target`在数组中首次出现的索引。 |
| 11 | `static int indexOfOf(short[] array, short[] target)` 返回指定`target`在数组中第一次出现时的起始位置，如果没有此类出现，则返回`-1`。 |
| 12 | `static String join(String separator, short... array)` 返回一个包含由分隔符隔的`short`值的字符串。 |
| 13 | `static int lastIndexOf(short[] array, short target)` 返回值`target`在数组中最后一次出现的索引。 |
| 14 | `static Comparator<short[]> lexicographicalComparator()` 返回一个字典比较两个`short`数组的比较器。 |
| 15 | `static short max(short... array)` 返回数组中存在的最大值。 |
| 16 | `static short min(short... array)` 返回数组中存在的最小值。 |
| 17 | `static short saturatedCast(long value)` 返回在数值上距离`value`最近的`short`。 |
| 18 | `static Converter<String,Short> stringConverter()` 返回一个可序列化的转换器对象，使用`Short.decode(java.lang.String)`和`Short.toString()`在字符串和`short`之间进行转换。 |
| 19 | `static short[] toArray(Collection<? extends Number> collection)` 返回一个包含`collection`中每个值的数组，按照`Number.shortValue()`的方式转换为`short`。 |
| 20 | `static byte[] toByteArray(short value)` 在 2 元素字节数组中返回`value`的大端表示；等于`ByteBuffer.allocate(2).putShort(value).array()`。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### Shorts 类示例

在`C:\> Guava`下使用你选择的任何编辑器创建以下 Java 程序。

### GuavaTester.java

```java
import java.util.List;
import com.google.common.primitives.Shorts;

public class GuavaTester {

    public static void main(String args[]) {
        GuavaTester tester = new GuavaTester();
        tester.testShorts();
    }

    private void testShorts(){
        short[] shortArray = {1,2,3,4,5,6,7,8,9};

        //将原始类型数组转换为对象数组
        List<Short> objectArray = Shorts.asList(shortArray);
        System.out.println(objectArray.toString());

        //将对象数组转换为原始类型数组
        short[] shortArray = Shorts.toArray(objectArray);
        System.out.print("[ ");
        for(int i = 0; i< shortArray.length; i++) {
            System.out.print(shortArray[i] + " ");
        }
        System.out.println("]");
        short data = 5;
        //检查元素是否存在于原始类型列表中
        System.out.println("5 is in list? " + Shorts.contains(shortArray, data));

        //返回最小值
        System.out.println("Min: " + Shorts.min(shortArray));

        //返回最大值
        System.out.println("Max: " + Shorts.max(shortArray));
    }
}
```

### 验证结果

使用`javac`编译器按如下方式编译类：

```
C:\Guava>javac GuavaTester.java
```

现在运行`GuavaTester`查看结果。

```
C:\Guava>java GuavaTester
```



查看结果。

```
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[ 1 2 3 4 5 6 7 8 9 ]
5 is in list? true
Min: 1
Max: 9
```

## Guava

| 序号 | 方法与描述 |
|---|---|
| 4 | `static int[] concat(int[]... arrays)` 返回从每个提供的数组合并成一个单个数组的值。 |
| 5 | `static boolean contains(int[] array, int target)` 如果 `target` 于数组中的任何位置，则返回 `true`。 |
| 6 | `static int[] ensureCapacity(int[] array, int minLength, int padding)` 返回一个包含与 `array` 相同值的数组，但保证达到指定的最小长度。 |
| 7 | `static int fromByteArray(byte[] bytes)` 返回其大端字节表示存储在 `bytes` 前 4 个字节中的 `int` 值；等于 `ByteBuffer.wrap(bytes).getInt()`。 |
| 8 | `static int fromBytes(byte b1, byte b2, byte b3, byte b4)` 返回由给定的 4 个字节按大端字节顺序表示的 `int` 值；等于 `Ints.toByteArray(new byte[] {b1, b2, b3, b4})`。 |
| 9 | `static int hashCode(int value)` 返回 `value` 的哈希值；等于调用 `((Integer)value).hashCode()` 的结果。 |
| 10 | `static int indexOf(int[] array, int target)` 返回值 `target` 在数组中首次出现的索引。 |
| 11 | `static int indexOf(int[] array, int[] target)` 返回指定的 `target` 在数组中首次出现的起始位置，如果没有此类出现，则返回 `-1`。 |
| 12 | `static String join(String separator, int... array)` 返回一个包含由 `separator` 分隔的提供的 `int` 的字符串。 |
| 13 | `static int lastIndexOf(int[] array, int target)` 返回值 `target` 在数组中最后一次出现的索引。 |
| 14 | `static Comparator<int[]> lexicographicalComparator()` 返回一个按字典序比较两个数组的比较器。 |
| 15 | `static int max(int... array)` 返回数组中存在的最大值。 |
| 16 | `static int min(int... array)` 返回数组中存在的最小值。 |
| 17 | `static int saturatedCast(long value)` 返回数值上最接近 `value` 的值。 |
| 18 | `static Converter<String,Integer> stringConverter()` 返回一个序列化对象，使用 `Integer.decode(java.lang.String)` 和 `Integer.toString()` 转换字符串和整数。 |
| 19 | `static int[] toArray(Collection<? extends Number> collection)` 返回一个包含 `collection` 中每个值的数组，这些值转换为 `Number.intValue()` 的 `int` 值。 |
| 20 | `static byte[] toByteArray(int value)` 返回 `value` 在 4 元素字节数组中的大端字节表示；等于 `ByteBuffer.allocate(4).putInt(value).array()`。 |
| 21 | `static int tryParse(String string)` 将指定的字符串解析为有符号的小整数值。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

## 类的类示例

使用你选择的任何编辑器在 `C:\Guava` 中创建以下 Java 程序。

### GuavaTester.java

```java
import java.util.List;

import com.google.common.primitives.Ints;

public class GuavaTester {

    public static void main(String[] args[]){
        GuavaTester tester = new GuavaTester();
    }
}
```

```java
tester.testInts();

private void testInts(){
    int[] intArray = {1,2,3,4,5,6,7,8,9};

    // 将基本类型数组转换为对象数组
    List<Integer> objectArray = Ints.asList(intArray);
    System.out.println(objectArray.toString());

    // 将对象数组转换为基本类型数组
    intArray = Ints.toArray(objectArray);
    System.out.print(" ");
    for(int i = 0; i < intArray.length; i++){
        System.out.print(intArray[i] + " ");
    }
    System.out.println(" ");
}
```

### 验证结果

使用 `javac` 编译器按如下方式编译该类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```bash
C:\Guava>java GuavaTester
```

查看结果。

```
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[ 1 2 3 4 5 6 7 8 9 ]
5 is in list? true
Min: 1
Max: 9
0 0 78 32
```

## Longs 类

`Longs` 是一个用于基本类型 `long` 的工具类。

### 类声明

遵循 `com.google.common.primitives.Longs` 类的声明：

```java
@GwtCompatible
public final class Longs
extends Object
```

### 字段

| 序号 | 字段与描述 |
|---|---|
| 1 | `static int BYTES` 表示一个基本类型 `long` 值所需的字节数。 |
| 2 | `static long MAX_POWER_OF_TWO` 能够表示为 `long` 的最大 2 的幂。 |

### 方法

| 序号 | 方法与描述 |
|---|---|
| 1 | `static List<Long> asList(long... backingArray)` 返回一个由指定数组支持的固定大小列表，类似于 `Arrays.Object[]`。 |
| 2 | `static int compare(long a, long b)` 比较两个指定的 `long` 值。 |
| 3 | `static long[] concat(long[]... arrays)` 返回从每个提供的数组合并成一个单个数组的值。 |
| 4 | `static boolean contains(long[] array, long target)` 如果 `target` 是数组中的任何元素，则返回 `true`。 |
| 5 | `static long[] ensureCapacity(long[] array, int minLength, int padding)` 返回一个包含与 `array` 相同值的数组，但保证达到指定的最小长度。 |
| 6 | `static long fromByteArray(byte[] bytes)` 返回其大端字节表示存储在 `bytes` 前 8 个字节中的 `long` 值；等于 `ByteBuffer.wrap(bytes).getLong()`。 |
| 7 | `static long fromBytes(byte b1, byte b2, byte b3, byte b4, byte b5, byte b6, byte b7, byte b8)` 返回由给定的 8 个字节按大端字节顺序表示的 `long` 值；等于 `Long.fromByteArray(new byte[] {b1, b2, b3, b4, b5, b6, b7, b8})`。 |
| 8 | `static int hashCode(long value)` 返回 `value` 的哈希值；等于调用 `((Integer)value).hashCode()` 的结果。 |
| 9 | `static int indexOf(long[] array, long target)` 返回值 `target` 在数组中首次出现的索引。 |
| 10 | `static int indexOf(long[] array, long[] target)` 返回指定的 `target` 在数组中首次出现的起始位置，如果没有此类出现，则返回 `-1`。 |

```java
// get the byte array from an integer
byte[] byteArray = Longs.toByteArray(20000);
for(int i = 0; i < byteArray.length ; i++) {
    System.out.print(byteArray[i] + " ");
}
```

### 验证结果

使用 `javac` 编译器按照如下编译该类：

```
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```
C:\Guava>java GuavaTester
```

查看结果。

- `[1, 2, 3, 4, 5, 6, 7, 8, 9]`

```
[ 1 2 3 4 5 6 7 8 9 ]

5 is in list? true

Min: 1

Max: 9

0 0 0 0 0 0 78 32
```

## Floats 类

`Floats` 是一个用于基本类型 `float` 的工具类。

### 类声明

遵循 `com.google.common.primitives.Floats` 类的声明：

```java
@GwtCompatible(emulated=true)

public final class Floats

extends Object
```

### Guava - 字段

| 序号 | 字段与描述 |
|---|---|
| 1 | `static int BYTES`<br>表示一个基本类型 `float` 值所需的字节数。 |

### Guava - 方法

| 序号 | 方法与描述 |
|---|---|
| 1 | `static List<Float> asList(float... backingArray)`<br>返回一个由所指定数组支持的固定大小列表，类似于 `Arrays.asList([])`。 |
| 2 | `static int compare(float a, float b)`<br>使用 `Float.compare(float,float)` 比较两个指定的 `float` 值。 |
| 3 | `static float[] concat(float[] arrays)`<br>返回从每个提供的数组中的值合并后的单个数组。 |
| 4 | `static boolean contains(float[] array, float target)`<br>如果 `target` 作为元素出现在数组的任何位置，则返回 `true`。 |
| 5 | `static float[] ensureCapacity(float[] array, int minLength, int padding)`<br>返回一个包含与数组相同值的数组，但保证长度为指定的最小长度。 |
| 6 | `static int hashCode(float value)`<br>返回值的哈希值；等于调用 `((Float)value).hashCode()` 的结果。 |
| 7 | `static int indexOfOf(float[] array, float target)`<br>返回目标值在数组中首次出现的索引。 |
| 8 | `static int indexOfOf(float[] array, float[] target)`<br>返回指定的 `target` 在数组中第一次出现的起始位置，如果没有这样的出现情况，则返回 `-1`。 |
| 9 | `static boolean isFinite(float value)`<br>如果 `value` 代表一个实数，则返回 `true`。 |
| 10 | `static String join(String separator, float... array)`<br>返回一个包含提供的 `float` 值的字符串，这些值按照 `Float.toString(float)` 转换为字符串，并用分隔符分隔。 |
| 11 | `static int lastIndexOf(float[] array, float target)`<br>返回值 `target` 在数组中最后一次出现的索引。 |
| 12 | `static Comparator<float[]> lexicographicalComparator()`<br>返回一个按字典顺序比较两个数组的比较器。 |
| 13 | `static float max(float... array)`<br>返回数组中的最大值，使用与 `Math.min(float, float)` 相同的比较规则。 |
| 14 | `static float min(float... array)`<br>返回数组中的最小值，使用与 `Math.min(float, float)` 相同的比较规则。 |
| 15 | `static Converter<String, Float> stringConverter()`<br>返回一个可序列化的转换对象，使用 `Float.valueOf(java.lang.String)` 和 `Float.toString()` 在字符串和 `float` 之间转换。 |
| 16 | `static float[] toArray(Collection<? extends Number> collection)`<br>返回一个包含 `collection` 中每个值的数组，按照 `Number.valueOf()` 的方式转换为 `float` 值。 |
| 17 | `static Float tryParse(String string)`<br>将指定的字符串解析为单精度浮点数。 |

### 继承的方法

该类继承自以下类的方法：

- `java.lang.Object`

### Floats 类示例

使用您选择的任何编辑器在 `C:\Guava` 下创建以下 Java 程序。

**GuavaTester.java**

```java
import java.util.List;

import com.google.common.primitives.Floats;

public class GuavaTester {

    public static void main(String args[]){

        GuavaTester tester = new GuavaTester();

        tester.testFloats();

    }

    private void testFloats(){

        float[] floatArray = {1.0f, 2.0f, 3.0f, 4.0f, 5.0f, 6.0f, 7.0f, 8.0f, 9.0f};

        // 将基本类型数组转换为对象数组

        List<Float> objectArray = Floats.asList(floatArray);

        System.out.println(objectArray.toString());

        // 将对象数组转换回基本类型

        float[] result = Floats.toArray(objectArray);

        for (float f : result) {

            System.out.print(f + " ");

        }

        // 检查元素是否存在于列表中

        System.out.println("5 is in list? " + Floats.contains(floatArray, 5.0f));

        // 寻找最小和值

        System.out.println("Min: " + Floats.min(floatArray));

        System.out.println("Max: " + Floats.max(floatArray));

    }

}
```

```java
import com.google.common.primitives.Doubles;

public class GuavaTester {
```



```java
public static void main(String args[]) {
    GuavaTester tester = new GuavaTester();
    tester.testDoubles();
}

private void testDoubles() {
    double[] doubleArray = {1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0};

    // convert array of primitives to array of objects
    List<Double> objectArray = Doubles.asList(doubleArray);
    System.out.println(objectArray.toString());

    // convert array of objects to array of primitives
    doubleArray = Doubles.toArray(objectArray, "{");
    System.out.print("{ ");

    for (int i = 0; i < doubleArray.length; i++) {
        System.out.print(doubleArray[i] + " ");
    }

    System.out.println("}");

    // check if element is present in the list of primitives or not
    System.out.println("5.0 is in list? " + Doubles.contains(doubleArray, 5.0f));

    // return the index of element
    System.out.println("5.0 position in list " + Doubles.indexOf(doubleArray, 5.0f));

    // Returns the minimum
    System.out.println("Min: " + Doubles.min(doubleArray));

    // Returns the maximum
    System.out.println("Max: " + Doubles.max(doubleArray));
}
```

## 验证结果

使用 `javac` 编译器编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果：

```bash
C:\Guava>java GuavaTester
```

查看结果：

```
[1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0]

[ 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 ]

5.0 is in list? true

5.0 position in list 4

Min: 1.0

Max: 9.0
```

## `Chars` 类

`Chars` 是一个用于基本类型 `char` 的工具类。

### 类声明

以下是 `com.google.common.primitives.Chars` 类的声明：

```java
@GwtCompatible(emulated = true)
public final class Chars extends Object
```

## Guava

### 字段

| S.N. | 字段 & 描述 |
|---|---|
| 1 | `static int BYTES`<br>表示一个基本 `char` 值所需的字节数。 |

### 方法

| S.N. | 方法 & 描述 |
|---|---|
| 1 | `static List<Character> asList(char... backingArray)`<br>返回由指定数组支持的固定大小列表，类似于 `Arrays.asList(Object[])`。 |
| 2 | `static char checkedCast(long value)`<br>如果可能，返回等于 `value` 的 `char` 值。 |
| 3 | `static int compare(char a, char b)`<br>比较两个指定的 `char` 值。 |
| 4 | `static char[] concat(char... arrays)`<br>返回来自每个提供的数组中的值合并后的单个数组。 |
| 5 | `static boolean contains(char[] array, char target)`<br>如果 `target` 作为元素出现在数组的任何位置，则返回 `true`。 |
| 6 | `static char[] ensureCapacity(char[] array, int minLength, int padding)`<br>返回一个包含 `array` 相同值的数组，但保证具有指定的最小长度。 |
| 7 | `static char fromByteArray(byte[] bytes)`<br>返回其大端序表示存储在 `bytes` 前 2 个字节中的 `char` 值；等于 `ByteBuffer.wrap(bytes).getChar()`。 |
| 8 | `static char fromByteBytes(byte b1, byte b2)`<br>返回其字节表示为给定 2 个字节（大端序）的 `char` 值；等于 `Chars.fromByteArray(new byte[] {b1, b2})`。 |
| 9 | `static int hashCode(char value)`<br>返回 `value` 的哈希值；等于调用相关方法的结果。 |
| 10 | `static int indexOf(char[] array, char target)`<br>返回 `target` 在数组中首次出现的索引。 |
| 11 | `static int indexOf(char[] array, char[] target)`<br>返回指定 `target` 在数组中首次出现的起始位置，如果没有此类出现则返回 `-1`。 |
| 12 | `static String join(String separator, char... array)`<br>返回一个包含由分隔符隔开的 `char` 值的字符串。 |
| 13 | `static int lastIndexOf(char[] array, char target)`<br>返回 `target` 在数组中最后一次出现的索引。 |
| 14 | `static Comparator<char[]> lexicographicalComparator()`<br>返回一个按字典顺序比较两个数组的比较器。 |
| 15 | `static char max(char... array)`<br>返回数组中最大的值。 |
| 16 | `static char min(char... array)`<br>返回数组中最小的值。 |
| 17 | `static char saturatedCast(long value)`<br>返回在数值上最接近 `value` 的 `char`。 |
| 18 | `static char[] toArray(Collection<Character> collection)`<br>将 `Character` 实例的集合拷贝到新的基本 `char` 值数组中。 |
| 19 | `static byte[] toByteArray(char value)`<br>返回 `value` 在 2 元素字节数组中的大端序表示；等于 `ByteBuffer.allocate(2).putChar(value).array()`。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

## `Chars` 类示例

使用任意编辑器创建以下 Java 程序，例如 `C:/Guava`。

`GuavaTester.java`

```java
import java.util.List;

import com.google.common.primitives.Chars;

public class GuavaTester {
    public static void main(String args) {
        GuavaTester tester = new GuavaTester();
        tester.testDoubles();
    }

    private void testDoubles() {
        double[] doubleArray = {1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0};

        // convert array of primitives to array of objects
        List<Double> objectArray = Doubles.asList(doubleArray);
        System.out.println(objectArray.toString());

        // convert array of objects to array of primitives
        doubleArray = Doubles.toArray(objectArray, "{");
        System.out.print("{ ");

        for (int i = 0; i < doubleArray.length; i++) {
            System.out.print(doubleArray[i] + " ");
        }

        System.out.println("}");

        // check if element is present in the list of primitives or not
        System.out.println("5.0 is in list? " + Doubles.contains(doubleArray, 5.0f));

        // return the index of element
        System.out.println("5.0 position in list " + Doubles.indexOf(doubleArray, 5.0f));

        // Returns the minimum
        System.out.println("Min: " + Doubles.min(doubleArray));

        // Returns the maximum
        System.out.println("Max: " + Doubles.max(doubleArray));
    }
}
```

## 验证结果

使用 `javac` 编译器编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果：

```bash
C:\Guava>java GuavaTester
```

查看结果：

```
[1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0]

[ 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 ]

5.0 is in list? true

5.0 position in list 4

Min: 1.0

Max: 9.0
```

## `Chars` 类

`Chars` 是一个用于基本类型 `char` 的工具类。

### 类声明

以下是 `com.google.common.primitives.Chars` 类的声明：

```java
@GwtCompatible(emulated = true)
public final class Chars extends Object
```

## Guava

### 字段

| S.N. | 字段 & 描述 |
|---|---|
| 1 | `static int BYTES`<br>表示一个基本 `char` 值所需的字节数。 |

### 方法

| S.N. | 方法 & 描述 |
|---|---|
| 1 | `static List<Character> asList(char... backingArray)`<br>返回由指定数组支持的固定大小列表，类似于 `Arrays.asList(Object[])`。 |
| 2 | `static char checkedCast(long value)`<br>如果可能，返回等于 `value` 的 `char` 值。 |
| 3 | `static int compare(char a, char b)`<br>比较两个指定的 `char` 值。 |
| 4 | `static char[] concat(char... arrays)`<br>返回来自每个提供的数组中的值合并后的单个数组。 |
| 5 | `static boolean contains(char[] array, char target)`<br>如果 `target` 作为元素出现在数组的任何位置，则返回 `true`。 |
| 6 | `static char[] ensureCapacity(char[] array, int minLength, int padding)`<br>返回一个包含 `array` 相同值的数组，但保证具有指定的最小长度。 |
| 7 | `static char fromByteArray(byte[] bytes)`<br>返回其大端序表示存储在 `bytes` 前 2 个字节中的 `char` 值；等于 `ByteBuffer.wrap(bytes).getChar()`。 |
| 8 | `static char fromByteBytes(byte b1, byte b2)`<br>返回其字节表示为给定 2 个字节（大端序）的 `char` 值；等于 `Chars.fromByteArray(new byte[] {b1, b2})`。 |
| 9 | `static int hashCode(char value)`<br>返回 `value` 的哈希值；等于调用相关方法的结果。 |
| 10 | `static int indexOf(char[] array, char target)`<br>返回 `target` 在数组中首次出现的索引。 |
| 11 | `static int indexOf(char[] array, char[] target)`<br>返回指定 `target` 在数组中首次出现的起始位置，如果没有此类出现则返回 `-1`。 |
| 12 | `static String join(String separator, char... array)`<br>返回一个包含由分隔符隔开的 `char` 值的字符串。 |
| 13 | `static int lastIndexOf(char[] array, char target)`<br>返回 `target` 在数组中最后一次出现的索引。 |
| 14 | `static Comparator<char[]> lexicographicalComparator()`<br>返回一个按字典顺序比较两个数组的比较器。 |
| 15 | `static char max(char... array)`<br>返回数组中最大的值。 |
| 16 | `static char min(char... array)`<br>返回数组中最小的值。 |
| 17 | `static char saturatedCast(long value)`<br>返回在数值上最接近 `value` 的 `char`。 |
| 18 | `static char[] toArray(Collection<Character> collection)`<br>将 `Character` 实例的集合拷贝到新的基本 `char` 值数组中。 |
| 19 | `static byte[] toByteArray(char value)`<br>返回 `value` 在 2 元素字节数组中的大端序表示；等于 `ByteBuffer.allocate(2).putChar(value).array()`。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

## `Chars` 类示例

使用任意编辑器创建以下 Java 程序，例如 `C:/Guava`。

`GuavaTester.java`

```java
import java.util.List;

import com.google.common.primitives.Chars;

public class GuavaTester {
    public static void main(String args) {
        GuavaTester tester = new GuavaTester();
        tester.testDoubles();
    }

    private void testDoubles() {
        double[] doubleArray = {1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0};

        // convert array of primitives to array of objects
        List<Double> objectArray = Doubles.asList(doubleArray);
        System.out.println(objectArray.toString());
```



### Guava 示例

使用你任的任何编辑器创建以下 Java 程序，例如 `C:/Guava`。

`GuavaTester.java`

```java
import java.util.List;
import com.google.common.primitives.Doubles;

public class GuavaTester {
    public static void main(String args) {
        GuavaTester tester = new GuavaTester();
        tester.testDoubles();
    }

    private void testDoubles() {
        double[] doubleArray = {1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0};

        // convert array of primitives to array of objects
        List<Double> objectArray = Doubles.asList(doubleArray);
        System.out.println(objectArray.toString());

        // convert array of objects to array of primitives
        doubleArray = Doubles.toArray(objectArray, "{");
        System.out.print("{ ");
        for (int i = 0; i < doubleArray.length; i++) {
            System.out.print(doubleArray[i] + " ");
        }
        System.out.println("}");

        // check if element is present in the list of primitives or not
        System.out.println("5.0 is in list? " + Doubles.contains(doubleArray, 5.0f));

        // return the index of element
        System.out.println("5.0 position in list " + Doubles.indexOf(doubleArray, 5.0f));

        // Returns the minimum
        System.out.println("Min: " + Doubles.min(doubleArray));

        // Returns the maximum
        System.out.println("Max: " + Doubles.max(doubleArray));
    }
}
```

### 验证结果

使用 `javac` 编译器编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```bash
C:\Guava>java GuavaTester
```

查看结果。

```
[1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0]
[ 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 ]
5.0 is in list? true
5.0 position in list 4
Min: 1.0
Max: 9.0
```

### Chars 类

`Chars` 是一个用于基本类型 `char` 的工具类。

### 类声明

以下是 `com.google.common.primitives.Chars` 类的声明：

```java
@GwtCompatible(emulated=true)
public final class Chars
extends Object
```

### 字段

| S.N. | 字段 & 描述 |
|---|---|
| 1 | `static int BYTES` 表示一个基本 `char` 值所需的字节数。 |

### 方法

| S.N. | 方法 & 描述 |
|---|---|
| 1 | `static List<Character> asList(char... backingArray)` 返回由指定数组支持的固定大小列表，类似于 `Arrays.asList(Object[])`。 |
| 2 | `static char checkedCast(long value)` 如果可能，返回等于 `value` 的 `char` 值。 |
| 3 | `static int compare(char a, char b)` 比较两个指定的 `char` 值。 |
| 4 | `static char[] concat(char... arrays)` 返回来自每个提供的数组中的值合并后的单个数组。 |
| 5 | `static boolean contains(char[] array, char target)` 如果 `target` 作为元素出现在数组的任何位置，则返回 `true`。 |
| 6 | `static char[] ensureCapacity(char[] array, int minLength, int padding)` 返回一个包含 `array` 相同值的数组，但保证具有指定的最小长度。 |
| 7 | `static char fromByteArray(byte[] bytes)` 返回其大端序表示存储在 `bytes` 前 2 个字节中的 `char` 值；等于 `ByteBuffer.wrap(bytes).getChar()`。 |
| 8 | `static char fromByteBytes(byte b1, byte b2)` 返回其字节表示为给定 2 个字节（大端序）的 `char` 值；等于 `Chars.fromByteArray(new byte[] {b1, b2})`。 |
| 9 | `static int hashCode(char value)` 返回 `value` 的哈希值；等于调用 `((Character)value).hashCode()` 的结果。 |
| 10 | `static int indexOf(char[] array, char target)` 返回 `value target` 在数组中首次出现的索引。 |
| 11 | `static int indexOf(char[] array, char[] target)` 返回指定 `target` 在数组中首次出现的起始位置，如果没有此类出现则返回 `-1`。 |
| 12 | `static String join(String separator, char... array)` 返回一个包含由分隔符隔开的 `char` 值的字符串。 |
| 13 | `static int lastIndexOf(char[] array, char target)` 返回 `value target` 在数组中最后一次出现的索引。 |
| 14 | `static Comparator<char[]> lexicographicalComparator()` 返回一个按字典顺序比较两个数组的比较器。 |
| 15 | `static char max(char... array)` 返回数组中最大的值。 |
| 16 | `static char min(char... array)` 返回数组中最小的值。 |
| 17 | `static char saturatedCast(long value)` 返回在数值上最接近 `value` 的 `char`。 |
| 18 | `static char[] toArray(Collection<Character> collection)` 将 `Character` 实例的集合拷贝到新的基本 `char` 值数组中。 |
| 19 | `static byte[] toByteArray(char value)` 返回 `value` 在 2 元素字节数组中的大端序表示；等于 `ByteBuffer.allocate(2).putChar(value).array()`。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### Chars 类示例

使用你任的任何编辑器创建以下 Java 程序，例如 `C:/Guava`。

`GuavaTester.java`

```java
import java.util.List;
import com.google.common.primitives.Chars;

public class GuavaTester {
    public static void main(String args) {
        GuavaTester tester = new GuavaTester();
        tester.testChars();
    }

    private void testChars() {
        char[] charArray = {'a', 'b', 'c', 'd', 'e'};

        // convert array of primitives to array of objects
        List<Character> objectArray = Chars.asList(charArray);
        System.out.println(objectArray.toString());

        // convert array of objects to array of primitives
        charArray = Chars.toArray(objectArray);
        System.out.print("{ ");
        for (int i = 0; i < charArray.length; i++) {
            System.out.print(charArray[i] + " ");
        }
        System.out.println("}");

        // check if element is present in the list of primitives or not
        System.out.println("'c' is in list? " + Chars.contains(charArray, 'c'));

        // return the index of element
        System.out.println("'c' position in list " + Chars.indexOf(charArray, 'c'));

        // Returns the minimum
        System.out.println("Min: " + Chars.min(charArray));

        // Returns the maximum
        System.out.println("Max: " + Chars.max(charArray));
    }
}
```

### 验证结果

使用 `javac` 编译器编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```bash
C:\Guava>java GuavaTester
```

查看结果。

```
[a, b, c, d, e]
{ a b c d e }
'c' is in list? true
'c' position in list 2
Min: a
Max: e
```



`Doubles.contains(doubleArray, 5.0f)`；

返回元素的索引：

`System.out.println("5.0 position in list " + Doubles.indexOf(doubleArray, 5.0f))`；

返回最小值：

`System.out.println("Min: " + Doubles.min(doubleArray))`；

返回最大值：

`System.out.println("Max: " + Doubles.max(doubleArray))`。

### 验证结果

使用 `javac` 编译器编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果：

```bash
C:\Guava>java GuavaTester
```

查看结果：

```
[1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0]
[ 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 ]
5.0 is in list? true
5.0 position in list 4
Min: 1.0
Max: 9.0
```

### Chars 类

`Chars` 是一个用于基本类型 `char` 的工具类。

### 类声明

以下是 `com.google.common.primitives.Chars` 类的声明：

```java
@GwtCompatible(emulated=true)
public final class Chars
extends Object
```

### 字段

| S.N. | 字段 & 描述 |
|---|---|
| 1 | `static int BYTES`：表示一个基本 `char` 值所需的字节数。 |

### 方法

| S.N. | 方法 & 描述 |
|---|---|
| 1 | `static List<Character> asList(char... backingArray)`：返回由指定数组支持的固定大小列表，类似于 `Arrays.asList(Object[])`。 |
| 2 | `static char checkedCast(long value)`：如果可能，返回等于 `value` 的 `char` 值。 |
| 3 | `static int compare(char a, char b)`：比较两个指定的 `char` 值。 |
| 4 | `static char[] concat(char... arrays)`：返回来自每个提供的数组中的值合并后的单个数组。 |
| 5 | `static boolean contains(char[] array, char target)`：如果 `target` 作为元素出现在数组的任何位置，则返回 `true`。 |
| 6 | `static char[] ensureCapacity(char[] array, int minLength, int padding)`：返回一个包含 `array` 相同值的数组，但保证具有指定的最小长度。 |
| 7 | `static char fromByteArray(byte[] bytes)`：返回其大端序表示存储在 `bytes` 前 2 个字节中的 `char` 值；等于 `ByteBuffer.wrap(bytes).getChar()`。 |
| 8 | `static char fromByteBytes(byte b1, byte b2)`：返回其字节表示为给定 2 个字节（大端序）的 `char` 值；等于 `Chars.fromByteArray(new byte[] {b1, b2})`。 |
| 9 | `static int hashCode(char value)`：返回 `value` 的哈希值；等于调用 `((Character)value).hashCode()` 的结果。 |
| 10 | `static int indexOf(char[] array, char target)`：返回 `value target` 在数组中首次出现的索引。 |
| 11 | `static int indexOf(char[] array, char[] target)`：返回指定 `target` 在数组中首次出现的起始位置，如果没有此类出现则返回 `-1`。 |
| 12 | `static String join(String separator, char... array)`：返回一个包含由分隔符隔开的 `char` 值的字符串。 |
| 13 | `static int lastIndexOf(char[] array, char target)`：返回 `value target` 在数组中最后一次出现的索引。 |
| 14 | `static Comparator<char[]> lexicographicalComparator()`：返回一个按字典顺序比较两个数组的比较器。 |
| 15 | `static char max(char... array)`：返回数组中最大的值。 |
| 16 | `static char min(char... array)`：返回数组中最小的值。 |
| 17 | `static char saturatedCast(long value)`：返回在数值上最接近 `value` 的 `char`。 |
| 18 | `static char[] toArray(Collection<Character> collection)`：将 `Character` 实例的集合拷贝到新的基本 `char` 值数组中。 |
| 19 | `static byte[] toByteArray(char value)`：返回 `value` 在 2 元素字节数组中的大端序表示；等于 `ByteBuffer.allocate(2).putChar(value).array()`。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### Chars 类示例

使用你选择的任何编辑器创建以下 Java 程序，例如在 `C:/Guava` 目录下创建 `GuavaTester.java`：

```java
import java.util.List;
import com.google.common.primitives.Chars;

public class GuavaTester {
    public static void main(String args) {
        GuavaTester tester = new GuavaTester();
        tester.testDoubles();
    }

    private void testDoubles() {
        double[] doubleArray = {1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0};

        // 将基本类型数组转换为对象数组
        List<Double> objectArray = Doubles.asList(doubleArray);
        System.out.println(objectArray.toString());

        // 将对象数组转换为基本类型数组
        doubleArray = Doubles.toArray(objectArray, "{");
        System.out.print("{ ");
        for (int i = 0; i < doubleArray.length; i++) {
            System.out.print(doubleArray[i] + " ");
        }
        System.out.println("}");

        // 检查元素是否存在于基本类型数组列表中
        System.out.println("5.0 is in list? " + Doubles.contains(doubleArray, 5.0f));

        // 返回元素的索引
        System.out.println("5.0 position in list " + Doubles.indexOf(doubleArray, 5.0f));

        // 返回最小值
        System.out.println("Min: " + Doubles.min(doubleArray));

        // 返回最大值
        System.out.println("Max: " + Doubles.max(doubleArray));
    }
}
```

### Booleans 类

### 方法

| S.N. | 方法 & 描述 |
|---|---|
| 1 | `static List<Boolean> asList(boolean... backingArray)`：返回由指定数组支持的固定大小列表，类似于 `Arrays.asList(Object[])`。 |
| 2 | `static int compare(boolean a, boolean b)`：按照标准比较两个指定的布尔值（`false` 小于 `true`）。 |
| 3 | `static boolean[] concat(boolean[]... arrays)`：返回每个提供的数组中的值合并后的单个数组。 |
| 4 | `static boolean contains(boolean[] array, boolean target)`：如果 `target` 作为元素出现在数组的任何位置，则返回 `true`。 |
| 5 | `static int countTrue(boolean... values)`：返回 `true` 值的数量。 |
| 6 | `static boolean[] ensureCapacity(boolean[] array, int minLength, int padding)`：返回一个包含 `array` 相同值的数组，但保证具有指定的最小长度。 |
| 7 | `static int hashCode(boolean value)`：返回 `value` 的哈希值；等于调用 `((Boolean)value).hashCode()`。 |
| 8 | `static int indexOf(boolean[] array, boolean target)`：返回 `value target` 在数组中首次出现的索引。 |
| 9 | `static int indexOf(boolean[] array, boolean[] target)`：返回指定 `target` 在数组中首次出现的起始位置，如果没有此类出现则返回 `-1`。 |
| 10 | `static String join(String separator, boolean... array)`：返回一个包含由分隔符隔开的布尔值的字符串。 |
| 11 | `static Comparator<boolean[]> lexicographicalComparator()`：返回一个按字典顺序比较两个布尔数组的比较器。 |
| 12 | `static boolean[] toArray(Collection<Boolean> collection)`：将 `Boolean` 实例集合拷贝到新的基本类型 `boolean` 数组中。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### Booleans 类示例

请使用你选择的任何编辑器在 `C:\Guava` 中创建以下 Java 程序 `GuavaTester.java`：

```java
import java.util.List;
import com.google.common.primitives.Booleans;

public class GuavaTester {
    public static void main(String args[]) {
        GuavaTester tester = new GuavaTester();
        tester.testBooleans();
    }

    private void testBooleans() {
        boolean[] booleanArray = {true, true, false, true, true, false, false};

        // 将基本类型数组转换为对象数组
        List<Boolean> objectArray = Booleans.asList(booleanArray);
        System.out.println(objectArray.toString());

        // 将对象数组转换为基本类型数组
        booleanArray = Booleans.toArray(objectArray);
    }
}
```

```java
System.out.print("[ ");
for (int i = 0; i < booleanArray.length; i++) {
    System.out.print(booleanArray[i] + " ");
}
System.out.println("]");

// 检查元素是否存在于基本类型数组列表中
System.out.println("true is in list? " + Booleans.contains(booleanArray, true));

// 返回元素的第一个索引
System.out.println("True position in list " + Booleans.indexOf(booleanArray, true));

// 返回 true 值的计数
System.out.println("true occured: " + Booleans.countTrue());

// 返回比较结果
System.out.println("false Vs true: " + Booleans.compare(false, true));
System.out.println("true Vs false: " + Booleans.compare(false, false));
System.out.println("true Vs false: " + Booleans.compare(true, false));
System.out.println("true Vs true: " + Booleans.compare(true, true));
```

### 验证结果

使用 `javac` 编译器按如下方式编译类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果：

```bash
C:\Guava>java GuavaTester
```

查看结果：

```
[true, true, false, true, true, false, false]
[ true true false true true false false ]
true is in list? true
true position in list: 0
true occured: 0
false Vs true: -1
false Vs false: 0
true Vs false: 1
true Vs true: 0
```

## 13. 数学工具

Guava 提供了处理 `int`、`long` 和 `BigInteger` 的二项式数学相关工具类。以下是实用工具类列表：

| 序号 | 工具类名称与描述 |
|---|---|
| 1 | `IntMath`：针对 `int` 的数学工具类。 |
| 2 | `LongMath`：针对 `long` 的数学工具类。 |
| 3 | `BigIntegerMath`：针对 `BigInteger` 的数学工具类。 |

### IntMath 类

`IntMath` 提供了 `int` 的工具方法。

### 类声明

以下是 `com.google.common.math.IntMath` 类的声明：

```java
@GwtCompatible(emulated=true)
public final class IntMath
    extends Object
```

### 方法

| 序号 | 方法与描述 |
|---|---|
| 1 | `static int binomial(int n, int k)`：返回 `n` 取 `k`，也称为 `n` 和 `k` 的二项系数；如果结果无法放入 `int`，则返回 `Integer.MAX_VALUE`。 |
| 2 | `static int checkedAdd(int a, int b)`：返回 `a` 和 `b` 的和，只要不溢出。 |
| 3 | `static int checkedMultiply(int a, int b)`：返回 `a` 和 `b` 的乘积，只要不溢出。 |



## IntMath 类方法

| S.N. | 方法与描述 |
| --- | --- |
| 4 | `static int checkedPow(int b, int k)` — 返回 `b` 的 `k` 次方，只要溢出。 |
| 5 | `static int checkedSubtract(int a, int b)` — 返回 `a` 和 `b` 的差，只要溢出。 |
| 6 | `static int divide(int p, int q, RoundingMode mode)` — 返回 `p` 除以 `q` 的结果，使用指定的 `RoundingMode` 进行舍入。 |
| 7 | `static int factorial(int n)` — 返回前 `n` 个正整数的乘积；`n = 0` 时返回 `1`；如果结果无法放入 `int`，则返回 `Integer.MAX_VALUE`。 |
| 8 | `static int gcd(int a, int b)` — 返回 `a`, `b` 的最大公约数。 |
| 9 | `static boolean isPowerOfTwo(int x)` — 如果 `x` 是 2 的幂，则返回 `true`。 |
| 10 | `static int log10(int x, RoundingMode mode)` — 返回 `x` 的以 10 为底的数，根据指定的舍入模式进行舍入。 |
| 11 | `static int log2(int x, RoundingMode mode)` — 返回 `x` 的以 2 为底的数，根据指定的舍入模式进行舍入。 |
| 12 | `static int mean(int x, int y)` — 返回 `x`, `y` 的算术平均值。 |

## LongMath 类方法

| S.N. | 方法与描述 |
| --- | --- |
| 6 | `static long divide(long p, long q, RoundingMode mode)` — 返回 `p` 除以 `q` 的结果，使用指定的 `RoundingMode` 进行舍入。 |
| 7 | `static long factorial(int n)` — 返回 `n!`，即前 `n` 个整数的乘积；如果 `n = 0` 则返回 `1`；如果结果不适合 `long` 类型则返回 `Long.MAX_VALUE`。 |
| 8 | `static long gcd(long a, long b)` — 返回 `a`, `b` 的最大公约数。 |
| 9 | `static boolean isPowerTwo(long x)` — 如果 `x` 是 2 的幂则返回 `true`。 |
| 10 | `static int log10(long x, RoundingMode mode)` — 返回 `x` 的以 10 对数，根据指定的舍入模式进行舍入。 |
| 11 | `static int log2(long x, RoundingMode mode)` — 返回 `x` 的以 2 对数，根据指定的舍入模式进行舍入。 |
| 12 | `static long mean(long x, long y)` — 返回 `x` 和 `y` 的算术平均值，向负无穷方向。 |
| 13 | `static int mod(long x, int m)` — 返回 `x mod m`，一个小于 `m` 的非负值。 |
| 14 | `static long mod(long x, long m)` — 返回 `x mod m`，一个小于 `m` 的非负值。 |
| 15 | `static long pow(long b, int k)` — 返回 `b` 的 `k` 次方。 |
| 16 | `static long sqrt(long x, RoundingMode mode)` — 返回 `x` 的平方根，使用指定的舍入模式进行舍入。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### LongMath 类示例

使用你选择的任何编辑器创建以下 Java 程序，例如在 `C:/> Guava` 中创建：

### GuavaTester.java

```java
import java.math.RoundingMode;
import com.google.math.common.LongMath;

public class GuavaTester {

    public static void main(String args[]){
        GuavaTester tester = new GuavaTester();
        tester.testLongMath();
    }

    private void testLongMath(){
        try{
            System.out.println(LongMath.checkedAdd(Long.MAX_VALUE,
            Long.MAX_VALUE));
        }catch(ArithmeticException e){
            System.out.println("Error: " + e.getMessage());
        }

        System.out.println(LongMath.divide(100, 5,
            RoundingMode.UNNECESSARY));
        try{
            // 将抛出异常，因为 100 不能被 3 整除
            // 因此需要舍入，而
            // RoundingMode 被设置为为 UNNECESSARY
            System.out.println(LongMath.divide(100, 3,
            RoundingMode.UNNECESSARY));
        }catch(ArithmeticException e){
            System.out.println("Error: " + e.getMessage());
        }
        System.out.println("Log2(2): "+LongMath.log2(2,
            RoundingMode.HALF_EVEN));

        System.out.println("Log10(10): "+LongMath.log10(10,
            RoundingMode.HALF_EVEN));

        System.out.println("sqrt(100): "+LongMath.pow(10,2),
            RoundingMode.HALF_EVEN));

        System.out.println("gcd(100,50): "+LongMath.gcd(100,50));
        System.out.println("modulus(100,50): "+LongMath.mod(100,50));
        System.out.println("factorial(5): "+LongMath.factorial(5));
    }
}
```

### 验证结果

使用 `javac` 编译器如下所示编译该类：

```bash
C:\Guava>javac GuavaTester.java
```

现在运行 `GuavaTester` 查看结果。

```bash
C:\Guava>java GuavaTester
```

查看结果。

```text
Error: overflow
20
Error: mode was UNNECESSARY, but rounding was necessary
Log2(2): 1
Log10(10): 1
sqrt(100): 10
gcd(100,50): 50
modulus(100,50): 0
factorial(5): 120
```

## BigIntegerMath 类

`BigIntegerMath` 提供了 `BigInteger` 的工具方法。

### 类声明

以下是 `com.google.common.math.BigIntegerMath` 类的声明：

```java
@GwtCompatible(emulated=true)
public final class BigIntegerMath
    extends Object
```

### 方法

| S.N. | 方法与描述 |
| --- | --- |
| 1 | `static BigInteger binomial(int n, int k)` — 返回 `n` 选择 `k`，也称为 `n` 和 `k` 的二项系数，即 `n! / (k! (n - k)!)` |
| 2 | `static BigInteger divide(BigInteger p, BigInteger q, RoundingMode mode)` — 返回 `p` 除以 `q` 的结果，使用指定的 `RoundingMode`。 |
| 3 | `static BigInteger factorial(int n)` — 返回 `n!`，即前 `n` 个正整数的乘积；如果 `n==0` 则返回 `1`。 |
| 4 | `static boolean isPowerTwo(BigInteger x)` — 如果 `x` 是 2 的幂则返回 `true`。 |
| 5 | `static int log10(BigInteger x, RoundingMode mode)` — 返回 `x` 的以 10 对数，根据指定的舍入模式进行舍入。 |
| 6 | `static int log2(BigInteger x, RoundingMode mode)` — 返回 `x` 的以 2 对数，根据指定的舍入模式进行舍入。 |
| 7 | `static BigInteger sqrt(BigInteger x, RoundingMode mode)` — 返回 `x` 的平方根，使用指定的舍入模式进行舍入。 |

### 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

### BigIntegerMath 类示例

使用你选择的任何编辑器创建以下 Java 程序，例如在 `C:/> Guava` 中创建：

### GuavaTester.java

```java
import java.math.BigInteger;
import java.math.RoundingMode;

import com.google.common.math.BigIntegerMath;

public class GuavaTester {

    public static void main(String args[]){
        GuavaTester tester = new GuavaTester();
        tester.testBigInteger();
    }
    private void testBigInteger(){
        System.out.println(BigIntegerMath.divide(BigInteger.TEN, new BigInteger("2"), RoundingMode.UNNECESSARY));
        try{
            // 将抛出异常，因为 100 不能被 3 整除
            // 因此需要舍入，而
            // RoundingMode 被设置为为 UNNECESSARY
            System.out.println(BigIntegerMath.divide(BigInteger.TEN, new BigInteger("3"), RoundingMode.UNNECESSARY));
        }catch(ArithmeticException e){
            System.out.println("Error: " + e.getMessage());
        }
        System.out.println("Log2(2): "+BigIntegerMath.log2(new BigInteger("2"), RoundingMode.HALF_EVEN));

        System.out.println("Log10(10): "+BigIntegerMath.log10(BigInteger.TEN, RoundingMode.HALF_EVEN));

        System.out.println("sqrt(100): "+BigIntegerMath.sqrt(BigInteger.TEN).multiply(BigInteger.TEN), RoundingMode.HALF_EVEN));

        System.out.println("factorial(5): "+BigIntegerMath.factorial(5));
    }
}
```
