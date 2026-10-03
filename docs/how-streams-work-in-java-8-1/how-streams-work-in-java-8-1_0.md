
# Java 8 流工作原理指南

## Java 8 Streams 简介

- Java 8 中的 Streams 与 Java 8 之前的 `InputStream` 或 `OutputStream` 完全不同
- Java 8 中的 Streams 是一种 Monad（单子器），这是函数式编程语言中的一个概念
- 函数式编程语言中的 Monad 本质上是一种表示定义为“步骤序列”计算的结构
- 在函数式编程语言中，具有 monad 结构的类型意味着可以链式操作，或将该类型的函数嵌套在一起
- Java 8 中的 Stream 允许你以声明的方式处理数据，并利用多核架构，而无需编写任何特定的代码
- Java 8 中的 Stream 有以下 5 个主要特征：
  - 元素的序列
  - 数据源
  - 聚合操作
  - 管道流操作 (Pipelining)
  - 自动迭代

## Java 8 中的 Streams 工作原理

- 如果你想完全理解 Java 8 中 Streams 是如何工作的，你应该熟悉 Lambda 表达式、函数式接口和方法引用
- Stream 操作分为中间操作和终端操作两类
  - **中间操作 (Intermediate Operations)**：这些操作将返回一个流，因此你可以链用多个中间操作而无需使用分号
  - **终端操作 (Terminal Operations)**：这些操作要么返回 void，要么返回一个非流的结果的结果

### 示例代码

```java
List<String> nameList = Arrays.asList("Van", "Nam", "Tuan", "Tien", "Hoang");

nameList.stream()
        .filter(name -> name.startsWith("T"))
        .map(String::toLowerCase)
        .sorted()
        .forEach(System.out::println);
```

**输出**

```
tien
tuan
```

### Notes

- 在上述示例中：
  - `filter()`、`map()` 和 `sorted()` 方法是中间操作
  - `forEach()` 方法是终端操作
- 在 Java 8 中，Stream 可以从各种数据源创建，特别是集合（Collections）
- Java 8 中的 `List` 和 `Set` 支持新方法，包括：
  - `stream()`：此方法用于创建顺序流
  - `parallelStream()`：此方法用于创建并行流，能够在多个线程上进行操作
- 在 `List` 对象上调用 `stream()` 方法将返回一个普通的流对象，但你不需要为了使用流而创建集合

### 示例

```java
Arrays.asList("Van01", "Van02", "Van03")
        .stream()
        .findFirst()
        .ifPresent(System.out::println);
```

**输出**

```
Van01
```

- 你可以使用 `Stream.of()` 从一组对象引用创建流

### 示例

```java
Stream.of("Lan01", "Lan02", "Lan03")
        .findFirst()
        .ifPresent(System.out::println);
```

**输出**

```
Lan01
```

## 如何在 Java 8 中过滤集合

- Java 8 提供了新功能来支持集合中元素过滤
- 你可以在 Java 8 中通过 `Stream` 类的 `filter()` 方法按照以下步骤过滤 `List`、`Set` 或 `Map` 等集合：
  - **步骤 01**：你需要通过调用 `stream()` 方法从集合获取 Stream
  - **步骤 02**：然后你可以使用 `filter()` 方法，该方法接受 `Predicate` 作为唯一参数

### Notes

- `filter()` 方法不会删除匹配 `predicate` 中给定条件的元素，而是 `filter()` 方法会在输出流中选择符合选择的元素
- `filter()` 方法定义在 `Stream` 类中。它接收一个 `Predicate` 对象，然后返回一个由原始流中符合给定 `Predicate` 的元素组成的流
- Java 8 中的 Streams 支持 `map()` 方法，该方法接受函数作为参数，将流中的元素投影到另一种形式
