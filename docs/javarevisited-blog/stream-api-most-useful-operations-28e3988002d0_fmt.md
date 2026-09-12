
# 流 API-最有用的操作

> 原文：<https://medium.com/javarevisited/stream-api-most-useful-operations-28e3988002d0?source=collection_archive---------0----------------------->

![](img/00e7941b5bdf7936ef36ae18925ee903.png)

`Stream` API 是 Java 8 的主要补充之一。可以将流定义为来自支持聚合操作的源的元素序列。源可以是向流提供数据的集合或数组。

流本身不是数据结构。它是应用于源的一组操作。它基本上有两种类型的操作：

[![](img/a04146fb87561f0d15aa721e303490e9.png)](https://javarevisited.blogspot.com/2020/04/top-5-courses-to-learn-java-collections-and-streams.html#axzz6nwXUSoGH)

*   **中级操作**——这些方法不会产生任何结果。它们通常接受函数接口作为参数，并且总是返回一个新的流。中间操作的一些例子有`filter()`、`map()`等。

*   **终端操作**——这些方法产生一些结果，例如`count()`、`collect()`等。

**流**操作进一步分类：

注意：我们将在整篇文章中使用这三个列表：

`employeeList`包含雇员的姓名、年龄、工资和国家。

`intList`有一些随机整数。

`stringList`有一些大写和小写的字符串。

[![](img/6adf6cbde91ca43bcb0e3acd53a1c683.png)](https://www.java67.com/2016/03/how-to-get-arraylist-from-stream-in-java8-example.html)![](img/e2e20482f9ece7106ba0d059e9d78e50.png)![](img/bab4c10a6ae960be2ba9f66f5a97b82b.png)

## 1. 过滤

过滤操作对给定的流进行过滤，并返回一个新的流，该流只包含下一个操作所需的那些元素。这是一个中间操作。

*   **过滤出年龄大于 30 的员工：**

```
employeeList.stream().filter(emp -> emp.getAge() >30).ForEach(System.out::println);
```

## 2. 切片

切片操作是中间操作，顾名思义，是用来切片流的。它包括`distinct()`、`limit()`、`skip()`。以这个`intList`为例：

*   **获取列表中不同值（列表有重复项）**：

```
intList.stream().distinct().forEach(System.out::println);
```

*   **限制返回的流最多只返回 n 个值**：

```
intList.stream().distinct().limit(3).forEach(System.out::println);
```

*   **跳过第 n（此处为其 2）个值**：

```
intList.stream().distinct().skip(2).forEach(System.out::println);
```

## 3. 映射

映射操作是转换一个流的元素并返回一个包含转换后的元素的新流的操作。`map()`和`flatMap()`是最常用的方法。例如：取`stringList`它以 String 为输入，

*   **以大写形式打印列表中的名称**：

```
stringList.stream().map(name -> name.toUpperCase()).forEach(System.out::println);
```

*   **要得到单词的长度，输入是一个字符串，输出是一个整数，我们用`mapToInt()`方法代替`map()`，它将返回`IntStream`而不是`Stream`。**

```
stringList.stream().mapToInt(name -> name.length()).forEach(System.out::println);
```

## 4. 匹配

匹配操作是终端操作，用于检查流中是否存在符合特定标准的元素。大多使用匹配的三种运算：`anyMatch()`、`allMatch()`、`noneMatch()`。考虑到`employeeList`，让我们看看不同的匹配操作：

*   **检查是否有人居住在特定国家：**

```
boolean Canadian = employeeList.stream().anyMatch(p -> p.getCountry().equals("加拿大"));
```

*   **检查所有人员是否都是特定国家的居民：**

```
boolean allIndian = employeeList.stream().allMatch(p -> p.getCountry().equals("印度"));
```

*   **检查是否所有人都不是某个国家的居民：**

```
boolean noneMexican = employeeList.stream().noneMatch(p -> p.getCountry().equals("墨西哥"));
```

## 5. 查找

查找操作是终端操作，用于获取匹配的元素，而不仅仅是验证它是否存在。流中有两个基本的查找操作，即`findAny()`、`findFirst()`。例如：

*   **筛选居住在印度的员工并获得第一个匹配项。**

```
Optional<Employee> person = employeeList.stream().filter(p -> p.getCountry().equals("印度")).findFirst();
```

`findAny()`的用法与`findFirst()`类似，但是在我们不关心返回哪个元素的情况下，比如并行流。如果我们在并行流中使用`findFirst()`方法，会非常慢。

## 6. 归约

归约流操作是将流归约为单个值的操作。当我们需要执行流缩减为单个值的操作时，例如，最大值、最小值、总和、乘积等。`sum()`、`min()`、`max()`、`count()`等。下面是一些归约运算的例子。`reduce()`明确要求您指定如何减少通过数据流的数据。

*   **计算所有员工工资的总和。**

```
Optional<Integer> totalSalary = employeeList.stream().map(p -> p.getSalary()).reduce((a, b) -> a + b);
```

*   使用`sum()`也可以找到上面的 sum，但是我们需要将流转换为`IntStream`，我们可以直接使用`sum()`。

```
int totalSal = employeeList.stream().mapToInt(p -> p.getSalary()).sum();
```

*   **同样地，当我们需要任何流中的最大或最小元素时，我们也可以使用`min()`、`max()`。**

```
Optional<Integer> max = intList.stream().max(Comparator.naturalOrder());
```

注意：如果流是一个自定义对象，我们也可以提供一个自定义比较器。

## 7. 收集

是终端方法。我们可以创建自己的**收集器**实现，也可以使用**收集器**类提供的预定义实现。`Collectors`有各种方法，比如—`toList()`、`toMap()`、`toSet()`、`collectingAndThen()`、`groupingBy()`、`partitioningBy()`、`minBy()`、`maxBy()`等。我们将通过将这些分为三类来详细研究这些问题：

### 收藏操作

1.  **`toList()`**——将流收集到列表中：

```
List<String> empName = employeeList.stream().map(emp -> emp.getName()).collect(Collectors.toList());
```

2.  **`toSet()`**——将流收集到 Set：

```
Set<String> empName = employeeList.stream().map(emp -> emp.getCountry()).collect(Collectors.toSet());
```

3.  **`toMap()`**——将流收集到 Map：

```
Map<String, Integer> nameMap = list.stream().collect(Collectors.toMap(s -> s, s -> s.length(), (s1, s2) -> s1));
```

**注意**：`toMap()`在列表有重复元素的情况下抛出异常，为了避免这种情况，使用上面提到的带有附加参数的实现来选择第一个有重复的元素（比如`s1, s2 -> s1`）。

4.  **`toCollection(Supplier<C> collectionFactory)`**——将输入元素收集到新集合中：

```
LinkedList<String> empName = employeeList.stream().map(emp -> emp.getName()).collect(Collectors.toCollection(LinkedList::new));
```

5.  **`collectingAndThen()`**——这个方法返回一个收集器，它将输入元素累积到给定的收集器中，然后执行一个附加的完成功能。例如：在这里使列表不可修改：

```
List<Employee> unmodifiedList = employeeList.stream().collect(Collectors.collectingAndThen(Collectors.toList(), Collections::unmodifiableList));
```

### 聚合操作

1.  **`counting()`**——获取员工数：

```
long count = employeeList.stream().filter(emp -> emp.getAge() > 30).collect(Collectors.counting());
```

2.  **`minBy()`**——获取最低工资的员工：

```
Optional<Employee> emp = employeeList.stream().collect(Collectors.minBy(Comparator.comparing(Employee::getSalary)));
```

3.  **`maxBy()`**——获取最高工资的员工：

```
Optional<Employee> employee = employeeList.stream().collect(Collectors.maxBy(Comparator.comparing(Employee::getSalary)));
```

4.  **`Collectors.summingInt(ToIntFunction mapper)`**——获取所有员工的工资总和：

```
int count = employeeList.stream().collect(Collectors.summingInt(emp -> emp.getSalary()));
```

5.  **`Collectors.averagingInt(ToIntFunction mapper)`**——获取所有员工的平均工资：

```
double avg = employeeList.stream().collect(Collectors.averagingInt(emp -> emp.getSalary()));
```

6.  **`joining()`**——将所有字符串连接起来，中间留有空间。

```
String joinedString = Stream.of("welcome", "to", "Java", "world").collect(Collectors.joining());
```

**注意**：我们也可以使用其他重载版本的连接方法，它们允许我们提供分隔符以及前缀和后缀字符串。

7.  **`summarizingInt(ToIntFunction mapper)`**——获取任意集合的汇总统计：

```
IntSummaryStatistics summarizingInt = employeeList.stream().collect(Collectors.summarizingInt(Employee::getSalary));
```

**注意**：输出将类似于——

```
IntSummaryStatistics { count = 6, sum=248000, min=23000, average=41333.333333, max=67000}
```

### 分组操作

分组操作是 streams 最重要的特性之一，因为它们可以帮助你在 2-3 行内完成一项任务，否则将需要大量编码。

**`groupingBy()`**——按国家对雇员进行分组：

```
Map<String, List<Employee>> empMap = employeeList.stream().collect(Collectors.groupingBy(Employee::getCountry));
```

**注意**：该方法有更多的使用案例，例如：

*   **如果我们需要得到一个映射，其中的关键字是国家的名称，值是该国所有雇员的工资总和：**

```
Map<String, Integer> empMap = employeeList.stream().collect(Collectors.groupingBy(Employee::getCountry, Collectors.summingInt(Employee::getSalary)));
```

*   **我们也可以用重载版本的`groupingBy()`将结果存储在 Set 而不是 list 中：**

```
Map<String, Set<Employee>> empMap = employeeList.stream().collect(Collectors.groupingBy(Employee::getCountry, Collectors.toSet()));
```

*   **如果我们需要对多个条件进行分组。然后我们可以提供另一个`groupingBy()`作为下游的，例如：通过两次使用`groupingBy()`方法按照国家和年龄对雇员进行分组。**

```
Map<String, Map<Integer, List<Employee>>> empMap = employeeList.stream().collect(Collectors.groupingBy(Employee::getCountry, Collectors.groupingBy(Employee::getAge)));
```

*   **如果我们需要得到一个映射，其中键是国家的名称，值是在那个国家有最高工资的雇员对象。**

```
Map<String, Optional<Employee>> empMap = employeeList.stream().collect(Collectors.groupingBy(Employee::getCountry, Collectors.maxBy(Comparator.comparingInt(Employee::getSalary))));
```

**`partitioningBy()`**：是用于根据给定的谓词对一个对象流（或一组元素）进行分区，并返回一个`Map<Boolean, List<T>>`。因为键是布尔值，所以它只接受真/假值。在 true 键下，我们将找到匹配给定谓词的元素。

*   **如果我们需要根据年龄对`employeeList`进行分区：**



`Map<Boolean, List<Employee>> empMap = employeeList.stream().collect(Collectors.partitioningBy(emp -> emp.getAge() > 30));`

这是一些非常有用的流方法。这些只是快速检查，需要一些更详细的练习。

参考：[Java Stream API](https://www.educative.io/courses/java-8-lambdas-stream-api-beyond)

谢谢！快乐学习:)
