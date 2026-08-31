

# Java 中的 `for-each` 循环

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-for-each-loop>

## 1. 概观

在本教程中，我们将讨论 Java 中的 `for-each` 循环及其语法、工作原理和代码示例。最后，我们会了解它的优点和缺点。

## 2. 简单的 `for` 循环

**Java 中简单的 [`for` 循环](/web/20221127213044/https://www.baeldung.com/java-for-loop)本质上有三个部分——初始化、`boolean` 条件和步骤：**

```java
for (initialization; boolean-condition; step) {
    statement;
}
```

它从一个循环变量的初始化开始，然后是一个 `boolean` 表达式。如果条件为 `true`，则执行循环中的语句，并递增或递减循环变量。否则，它终止循环。

这种模式使它有点复杂，难以阅读。此外，如果我们没有正确地编写条件，总是有机会进入一个无限循环。

## 3. `for-each` 循环

Java 5 中引入了 `for-each` 循环。**我们也称之为增强型 `for` 循环。**

这是一种替代的遍历技术，专门用于遍历数组或集合。值得注意的是，它还使用了 `for` 关键字。然而，我们没有使用循环计数器变量，而是分配一个与数组或集合类型相同的变量。

**名字 `for-each` 表示数组或集合中的每个元素都会被一个接一个地遍历。**

### 3.1. 语法

`for-each` 循环由循环变量的声明组成，后跟冒号（`:`），再后跟数组或集合的名称：

```java
for (data_type var_name : array | collection) {
    // code
}
```

### 3.2. 工作原理

对于每次迭代，`for-each` 循环获取集合中的每个元素，并将其存储在一个循环变量中。因此，它会为数组或集合中的每个元素执行写在循环体中的代码。

最重要的是，遍历一直进行到数组或集合中的最后一个元素。

### 3.3. 示例

让我们看一个使用 `for-each` 循环遍历数组的例子：

```java
int numbers[] = { 1, 2, 3, 4, 5 };

for (int number : numbers) {
    System.out.print(number + " ");
}
```

这里，`for-each` 循环逐个遍历数组 `numbers` 中的每个元素，直到结束。**因此，没有必要使用索引来访问数组元素。**

现在，让我们看一些使用 `for-each` 循环遍历各种集合的例子。

先看一个 `List`：

```java
String[] wordsArray = { "Java ", "is ", "great!" };
List<String> wordsList = Arrays.asList(wordsArray);

for (String word : wordsList) {
    System.out.print(word + " ");
}
```

类似地，我们可以遍历一个 `Set` 中的所有元素：

```java
Set<String> wordsSet = new HashSet();
wordsSet.addAll(wordsList);

for (String word : wordsSet) {
    System.out.print(word + " ");
}
```

此外，我们还可以使用 `for-each` 循环来遍历 `Map<K, V>`：

```java
Map<Integer, String> map = new HashMap<>();
map.put(1, "Java");
map.put(2, "is");
map.put(3, "great!");

for (Entry<Integer, String> entry : map.entrySet()) {
    System.out.println(
      "number: " + entry.getKey() +
      " - " +
      "Word: " + entry.getValue());
}
```

同样，我们可以使用 `for-each` 循环来遍历 Java 中的各种其他数据结构。

**然而，如果数组或集合是 `null`，它会抛出一个 `NullPointerException`：**

```java
int[] numbers = null;
for (int number : numbers) {
    System.out.print(number + " ");
}
```

上面的代码会抛出一个 `NullPointerException`：

```java
Exception in thread "main" java.lang.NullPointerException
    at com.baeldung.core.controlstructures.loops.ForEachLoop.traverseArray(ForEachLoop.java:63)
    ..
```

**因此，在将数组或集合传递给 `for-each` 循环之前，我们必须检查它是否为 `null`。**

如果数组或集合为空，那么 `for-each` 循环根本不会执行。

### 3.4. 利弊

`for-each` 循环是 Java 5 中引入的重要特性之一。然而，它也有自己的优点和缺点。

`for-each` 循环的好处是：

- 它帮助我们避免编程错误。
- 它使代码精确且易读。
- 更容易实现。
- 它避免了进入无限循环的可能性。

**由于这些好处，我们更喜欢使用 `for-each` 循环而不是 `for` 循环，尤其是在处理数组或集合时。**

`for-each` 循环的缺点是：

- 当遍历每个元素时，我们不能跳过某个元素。
- 不可能以相反的顺序进行遍历。
- 如果我们使用 `for-each` 循环，就不能修改数组。
- 不可能跟踪索引。
- 它会带来一些循环性能开销。

## 4. 结论

在本文中，我们探索了 Java 中的 `for-each` 循环及其语法、工作原理和示例。最后，我们了解了它的优点和缺点。

和往常一样，这些示例的代码可以在 GitHub [上找到。](https://web.archive.org/web/20221127213044/https://github.com/eugenp/tutorials/tree/master/core-java-modules/core-java-lang-syntax-2)

