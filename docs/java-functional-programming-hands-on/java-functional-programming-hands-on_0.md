
# Java 函数式编程 实用指南

![](img/image_rsrc11N.jpg)

## 第一版

## 献辞

本书献给我亲爱的祖父，他坚定不移的支持和无尽的爱每天激励着我。您出现在我的生命中是一份幸运，您的记忆将被永远珍藏。

献给我的家人，感谢你们在这段旅程中的耐心、鼓励和理解。你们对我的信任是我最大的动力。

献给我的导师 Biplab Roy，他是 Calibo India Pvt Ltd 的高级工程主管，他的指导和引导塑造了我的观点，激发了我对这一主题的热情。

献给我忠实的读者和支持者，你们对我工作的热情是驱动力，我对你们的信任和鼓励深表感谢。

献给所有相信知识具有改变生活的力量，本书献给你们。愿它能带来灵感、洞察和积极的变化。

诚挚地感谢，

## 关于作者

你好，科技客们！我是 AK Ray，一名资深软件专业人士，深爱钻研 Java 最佳实践，并对函数式编程有浓厚兴趣。

我在软件行业拥有超过 10 年的实战经验，特别是在研发部门的核心产品开发方面，并且我获得了阿尔伯塔大学的软件设计与架构认证。我有幸参与过许多项目，每一个项目都证明了 Java 的强大。但在代码之外，我还培养了探索函数式编程范式优雅性与效率的热情。

我的编程之旅始于 2014 年初。Java 凭借其健壮性和多功能，迅速成为我的首选语言。随着时间的推移，我深入研究了迷人的函数式编程领域，在那里我发现了 lambda 表达式、流（`streams`）和不可变性（`immutability`）的美。

我热衷于培养 Java 爱好者和函数式编程爱好者的社区。让我们联系并继续对话：

邮箱：`akr.technolab@gmail.com`

LinkedIn：`https://www.linkedin.com/in/amitesh-kumar-ray-9366b7143/`

练习代码：GIT 链接在书末提供

衷心感谢你们选择与我一起探索 Java 函数式编程的世界。你们的支持和热情驱动了我分享知识的决心，并为其他开发者提供了在 Java 生态系统中脱颖而出所需的工具。

祝未来的代码不仅功能强大，而且优雅优雅！

诚挚的问候，

## 如何创建 Stream？

### `Stream` 是一个可以流水线化的元素序列。

- 它支持顺序操作和并行操作。
- 它是 Java 8 作为 Java Streams API 的一部分引入的，位于 `java.util.stream` 包下。
- `Streams` 用于以函数式和声明式方式处理数据序列，例如集合（如列表、集合、映射）或其他数据源。
- 创建并行 `Stream` 将根据可用处理器的数量创建相同数量的并行 `Streams`。这是它的默认行为，但你可以根据需要进行更改。

创建 `Stream` 最常见的用例是从集合对象创建 `Stream`。假设你有一个包含 1 万条记录的 `Employee List`，我们需要对它执行某些操作，如排序、过滤、数据转换逻辑、数据分组、数据分区或其他我们在批量数据上想要执行的操作。

![](img/image_rsrc11P.jpg)

从 Employee 集合创建 Stream：步骤：

1. 创建 `Employee` 的 `List`
2. 从 `Employee` 的 `List` 创建 `Stream`

`Employee.java` `EmployeeUtil`：我们将在此类中获取示例中的 `Employee List`。

![](img/image_rsrc11R.jpg)

从 Employee 对象列表创建 Stream：

注意 - 你的 `Stream` 可以是顺序的或并行的

![](img/image_rsrc11S.jpg)

`Stream` 甚至可以从原始类型/`Strings` 创建：

![](img/image_rsrc11T.jpg)

使用 `Stream Builder` 创建 Stream

![](img/image_rsrc11U.jpg)

![](img/image_rsrc11V.jpg)

打印 Stream：

![](img/image_rsrc11W.jpg)

![](img/image_rsrc11X.jpg)

让我们看看 Stream 操作的一些示例。Stream 支持两种操作：

1. 中间操作 (Intermediate Operation)
2. 终端操作 (Terminal Operation)

![](img/image_rsrc11Y.jpg)

理解下面的图：

![](img/image_rsrc120.jpg)

![](img/image_rsrc121.jpg)

### 过滤数据

![](img/image_rsrc11P.jpg)

`filter(p)` 是 Stream 的一个方法，接受一个 `Predicate` 类型的输入。

![](img/image_rsrc122.jpg)

`Predicate` 是一个函数接口，接受任何类型的输入并返回布尔值。

![](img/image_rsrc123.jpg)

过滤城市为 Bangalore 的员工。你可以单独编写 `Predicate` 并将其传递给 `filter()` 方法。

![](img/image_rsrc124.jpg)

打印 1 到 10 之间的数字

![](img/image_rsrc125.jpg)

注意你可以根据需要调用多个 `Predicate`，或者根据需要合并逻辑。使用 `negate()` 或更改你的 `Predicate` 逻辑以获取反向结果。

![](img/image_rsrc126.jpg)

![](img/image_rsrc127.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc128.jpg)

### 在 Stream 上使用 `map(f)` 进行数据转换

注意，简单来说 `map(f)` 用于将数据从类型 X 映射到任何结果 Y。

根据上面的示例，你将 `Employee Object` 映射到了 `NAME`。它接受一个执行转换逻辑的函数。

![](img/image_rsrc129.jpg)

![](img/image_rsrc12A.jpg)

![](img/image_rsrc12B.jpg)

![](img/image_rsrc11P.jpg)

获取每个 `Employee` 的双倍薪水

![](img/image_rsrc12C.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc12D.jpg)

![](img/image_rsrc11P.jpg)

薪水大于 160,000 的 `Employee Name` 列表

![](img/image_rsrc12E.jpg)

![](img/image_rsrc11P.jpg)

从列表中查找去重名称

![](img/image_rsrc12F.jpg)

这里采取了相同的需求来查找去重的员工。

### 去重 (Distinct)

有多种方法可以获取唯一数据的结果，但在这里我们使用 `distinct()` 方法。

正如我们所看到的，上面的示例中只需调用 `distinct()` 方法即可，但如果你想对任何自定义类执行相同的操作，你必须重写 `hashcode()` 和 `equals(Object o)` 方法的行为。

`String` 类已经提供了这些方法的实现，因此我们不需要显式地这样做。

![](img/image_rsrc12G.jpg)

![](img/image_rsrc12H.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc12J.jpg)

### 注意事项

- 注意：你可以使用 `Employee Record` 代替 `Employee` 类，这样你就不需要为 `hashcode()` 和 `equals(Object o)` 方法提供实现，因为 JAVA 默认会处理它们。

![](img/image_rsrc12K.jpg)

- 或者你甚至可以使用 Lombok 库，通过注解来处理 getter/setter、hashcode 和 equals 方法。https://projectlombok.org/#

### 获取唯一结果

你甚至可以不使用 `distinct()` 方法就获得相同的结果，我们只需要将结果收集到 `SET` 中，因为 `SET` 不允许重复项，所以重复条目会被排除。

![](img/image_rsrc11P.jpg)

查找无任何重复的唯一员工结果

![](img/image_rsrc12M.jpg)

## 使用 Stream 进行排序

![](img/image_rsrc11P.jpg)

使用 Stream 对数字列表排序

![](img/image_rsrc12N.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc12P.jpg)

![](img/image_rsrc11P.jpg)

使用 Stream 对字符串元素排序。

![](img/image_rsrc12R.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc12S.jpg)

让我们来看看如何像在真实场景中那样处理自定义类对象。

假设我们有一个包含 1 万条员工数据的 `List`，并且你想要按员工姓名升序对它们进行排序。

![](img/image_rsrc11P.jpg)

按员工姓名升序排序员工列表输入数据：

![](img/image_rsrc12T.jpg)

我们可以使用这个工具类来获取示例中的员工记录。

这里我们使用 `Record` 代替 `class`。

![](img/image_rsrc12U.jpg)

![](img/image_rsrc12V.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc12W.jpg)

![](img/image_rsrc11P.jpg)

按员工姓名降序排序员工列表

![](img/image_rsrc12X.jpg)

结果：示例：按名称、城市和职位升序列出员工数据，其中薪水>160,000

![](img/image_rsrc12Y.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

查找薪水>160,000 时按名称排序的员工姓名

![](img/image_rsrc12Z.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

查找员工薪水列表，当薪水>160,000 时薪水翻倍

![](img/image_rsrc130.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

## Stream 操作

### 为什么要使用 `peek(Consumer c)` 方法？

我们使用这个方法是为了调试目的，当我们想要打印字符串元素时。

![](img/image_rsrc131.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc132.jpg)

如你所见，我们在数据映射之前之后打印了 Stream 元素。

### 如何限制 Stream 元素？

你可以使用 `limit(long l)` 方法来限制 Stream 元素。

![](img/image_rsrc133.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc134.jpg)

![](img/image_rsrc11P.jpg)

使用 Stream 从列表中找到最大数

![](img/image_rsrc135.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc136.jpg)

![](img/image_rsrc11P.jpg)

从员工列表中找到薪水最高的员工。

![](img/image_rsrc137.jpg)

结果：

![](img/image_rsrc11P.jpg)

从员工列表中查找城市为 Bangalore 的员工最低薪水

![](img/image_rsrc138.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

### 为什么要使用 `flatmap(Function f)` 方法？

`flatmap(function f)` 类似于 `map(function f)`，用于平化 Stream 的数据。

假设 Stream 包含 `List` 的 `List` 或 `List` 的 `Array`，我们可以简单将其平化为 `List`。

![](img/image_rsrc139.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc13A.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

获取不同部门的合并总人数

![](img/image_rsrc13B.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

使用 Stream 查找整数平均值

![](img/image_rsrc13C.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc13D.jpg)

## GroupBy 语句

![](img/image_rsrc11P.jpg)

从员工列表中查找员工姓名

![](img/image_rsrc13E.jpg)

![](img/image_rsrc11P.jpg)

按员工姓名分组员工列表

![](img/image_rsrc13F.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc13G.jpg)

![](img/image_rsrc11P.jpg)

按城市后按部门分组员工数据

![](img/image_rsrc13H.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc13J.jpg)

![](img/image_rsrc11P.jpg)

查找每个城市的平均薪水。

![](img/image_rsrc11V.jpg)

![](img/image_rsrc13K.jpg)

![](img/image_rsrc11P.jpg)

查找每个城市最高薪水的员工

![](img/image_rsrc13M.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

查找每个城市最低薪水的员工

![](img/image_rsrc13N.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

查找每个城市的员工人数

![](img/image_rsrc13P.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

查找每个城市的薪水总和

![](img/image_rsrc13R.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

查找每个城市的最小、最大和平均薪水

![](img/image_rsrc13S.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc13T.jpg)

![](img/image_rsrc11P.jpg)

分组员工数据并从结果中移除城市。如下，我们按城市分组了数据，Map 中已有城市，所以我们不想看到城市值。

groupBy 的默认结果：

![](img/image_rsrc13U.jpg)

预期结果：

![](img/image_rsrc13V.jpg)

如你所见，Map 值中未包含城市。我们有 `groupBy(..)` 的不同重载方法，如下。

`groupBy(..)` 重载方法：

![](img/image_rsrc13W.jpg)

你可能想要对 `groupBy` 数据执行一些额外操作，可以使用这些重载方法完成任务

![](img/image_rsrc13X.jpg)

![](img/image_rsrc13Y.jpg)

![](img/image_rsrc11V.jpg)

如上面的示例所示，我们使用了 `groupBy(..)` 的第二个重载方法，并将 `Collector` 传递给 `groupBy(..)`。这种用例在实际应用中会遇到。如此处所示，我们将结果收集到 `MAP`，但如果我想将最终结果收集到 `TreeMap` 或 `Hashtable` 或其他 `Map` 实现中呢？

![](img/image_rsrc13Z.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc11P.jpg)

按城市分组员工数据并将最终数据收集到 `TreeMap` 以进行排序

![](img/image_rsrc140.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc141.jpg)

注意：如果我想将职位数据保留在 `TreeMap` 中，意味着期望类型为 `TreeMap<String,TreeMap<String,List<EmployeeRecord>>>`

![](img/image_rsrc11P.jpg)

按城市分组员工数据并将最终数据收集到 `TreeMap` 以进行排序

![](img/image_rsrc142.jpg)

![](img/image_rsrc11V.jpg)

![](img/image_rsrc143.jpg)

注意：此处所示，我们通过多个字段分组并在不同级别将结果收集到 `TreeMap`，以便获取排序格式的结果。你可以在不同类型的数据上应用类似的用例。

![](img/image_rsrc11P.jpg)

你有一个学生列表，每个学生选了多门课程，每门课程都有分数。按学生姓名和课程分组学生数据，以便姓名和课程按升序排列，提高用户界面的可读性。

`StudentRecors.java`



# StudentRecordUtil.java：获取学生列表

此处我们使用了 `Record` 查找每个学生分数最高的科目、查找每个学生的平均分、查找每个学生得到的总分、查找总分最高的优异者。

### 为什么要使用 `groupingByConcurrent(..)`？

`groupBy(..)` 和 `groupingByConcurrent(..)` 之间有什么区别？

演示：使用并发版本的 `groupBy(..)`

## 数据分区

- 它根据布尔值函数将 Stream 中的元素划分为两组。
- 分区操作返回一个 `Map`，其键为布尔值（true 和 false）。

查找分数超过 80% 的 `Student` 列表

## 函数式接口 (FunctionalInterface)

### Java 中的 `Functional Interface` 是什么？我们如何使用它？

一些最常用的 `Functional Interfaces`：

### 使用 FunctionalInterface 将数字乘以 2

### 检查数字是否为偶数 (`EVEN`)

### 什么是 `UnaryOperator`？

`UnaryOperator` 是一个 `FunctionalInterface`，它接受类型为 `X` 的输入并提供相同类型的输出。它与 `Function` 相同，返回与输入类型相同的 `Result`。

```
100
```

### 什么是 `BinaryOperator`？

它是一个 `Functional Interface`，接受 2 个输入（相同类型）并提供相同类型的 `Output`。

```
33
```

### 什么是 `Consumer`？

```
你提供的：10
```

### 什么是 `Supplier`

`Supplier` 演示

简单来说，我们可以说，它在不接受任何输入的情况下提供值。

### 如何创建 `Thread`？

```
Thread 正在运行……
```

### 什么是 `Lambda Expression`？

请参考以下关于 Java 函数式编程的书籍。

我专门为 Java 函数式编程编写了这本书，其中我讨论了 `Stream`、`Lambda Expression`、`Method Reference` 以及其他特性，从初学者水平到专家水平都有。

![](img/image_rsrc158.jpg)

https://www.amazon.in/Java-Functional-Programming-industry-practices-ebook/dp/B0CHTV3TWR/ref=tmm_kin_swatch_0?_encoding=UTF8&dib_tag=se&dib=eyJ2IjoiMSJ9.LTBpL1aLeOJTflVVRJLD_qjU1hUQlPs1TDeXVqKNqqkNTLoganQLNlsBM3R6CQ4znU4cxPIOgaHH65Q4w0A8Z7Wwz3DuDVF5dySqfYAIwxGQ2lHoWkzOgYTBkJhlsJ2tDaipRuO_Cu8-oRukNLrpJNDxfAUBr2YtJtaZPv8_3lhlCRJSkTgx8FI2eX5w75WT0w8CS-lM_wnEa8QDnKzivV8sj3247KOswDu3-VgfjI.tMkuKJR3Un8fd6uUKoQlXQWBnPyv0tAW7O_WOtClYp0&qid=1715674856&sr=8-3

## 方法引用 (Method Reference)

你如何使用 `Method Reference` 将方法调用引用到另一个方法上

### Java 中的 `default` 方法是什么？我们可以在 `Interface` 中提供方法实现吗？

`default` 方法作为接口的一个新特性被引入。`default` 方法允许接口具有带有实现的方法。

**这些方法被标记为 `default` 关键字，并提供了向接口添加新方法的方法。**

#### 在 `Interface` 中添加 `default` 方法

我们可以在 `Interface` 中添加 `private` 方法吗

你可以在 `Interface` 中使用 `static` 方法吗

### 计算 `List` 中 `Integers` 的平均值

### 从 `list` 中找到最大 (`MAX`) 数字

### 给定一个整数列表，编写一个 Java 程序过滤掉偶数，将剩余的奇数翻倍，然后返回所有结果数字的和。

## 什么是 `var`？

`var` 是一个接受类型为 `X` 的输入并提供相同类型输出的 `FunctionalInterface`（注：此处指变量）。它与返回与输入类型相同的 `Result` 的 `Function` 相同。

```
100
```

### 什么是 `BinaryOperator`？

它是接受 2 个输入（相同类型）并提供相同类型 `Output` 的 `Functional Interface`。

```
33
```

### 什么是 `Consumer`？

```
你提供的：10
```

### 什么是 `Supplier`

`Supplier` 演示

简单来说，我们可以说，它在不接受任何输入的情况下提供值。

### 如何创建 `Thread`？

```
Thread 正在运行……
```

### 什么是 `Lambda Expression`？

请参考以下关于 Java 函数式编程的书籍。

我专门为 Java 函数式编程编写了这本书，其中我讨论了 `Stream`、`Lambda Expression`、`Method Reference` 以及其他特性，从非常基础的水平到专家水平都有。

![](img/image_rsrc158.jpg)



# Java 函数式编程核心概念

## 方法引用 (Method Reference)

### 如何使用 `Method Reference` 将方法调用引用到另一个方法上

### Java 中的 `default` 方法是什么？我们可以在 `Interface` 中提供方法实现吗？

`default` 方法作为接口的一个新特性被引入。`default` 方法允许接口具有带有实现的方法。

这些方法被标记为 `default` 关键字，并提供了向接口添加新方法的方法。

#### 在 `Interface` 中添加 `default` 方法

### 我们可以在 `Interface` 中添加 `private` 方法吗

### 你可以在 `Interface` 中使用 `static` 方法吗

### 计算 `List` 中 `Integers` 的平均值

### 从 `list` 中找到最大 (`MAX`) 数字

### 给定一个整数列表，编写一个 Java 程序过滤掉偶数，将剩余的奇数翻倍，然后返回所有结果数字的和。

## 什么是 `var`？

> **注意**：此处 `var` 指代函数式接口概念，非 Java 10+ 局部变量类型推断关键字。

`var` 是一个接受类型为 `X` 的输入并提供相同类型的输出的 `FunctionalInterface`。它与返回与输入类型相同的 `Result` 的 `Function` 相同。

**示例输出：**
```
100
```

## 什么是 `BinaryOperator`？

它是接受 2 个输入（相同类型）并提供相同类型 `Output` 的 `Functional Interface`。

**示例输出：**
```
33
```

## 什么是 `Consumer`？

**示例输出：**
```
你提供的：10
```

## 什么是 `Supplier`？

### `Supplier` 演示

简单来说，我们可以说，它在不接受任何输入的情况下提供值。

## 如何创建 `Thread`？

**示例输出：**
```
Thread 正在运行……
```

## 什么是 `Lambda Expression`？

## 参考书籍

我专门为 Java 函数式编程编写了这本书，其中我讨论了 `Stream`、`Lambda Expression`、`Method Reference` 以及其他特性，从非常基础的水平到专家水平都有。

**书籍链接：**
https://www.amazon.in/Java-Functional-Programming-industry-practices-ebook/dp/B0CHTV3TWR/ref=tmm_kin_swatch_0?_encoding=UTF8&dib_tag=se&dib=eyJ2IjoiMSJ9.LTBpL1aLeOJTflVVRJLD_qjU1hUQlPs1TDeXVqKNqqkNTLoganQLNlsBM3R6CQ4znU4cxPIOgaHH65Q4w0A8Z7Wwz3DuDVF5dySqfYAIwxGQ2lHoWkzOgYTBkJhlsJ2tDaipRuO_Cu8-oRukNLrpJNDxfAUBr2YtJtaZPv8_3lhlCRJSkTgx8FI2eX5w75WT0w8CS-lM_wnEa8QDnKzivV8sj3247KOswDu3-VgfjI.tMkuKJR3Un8fd6uUKoQlXQWBnPyv0tAW7O_WOtClYp0&qid=1715674856&sr=8-3



# Java 函数式编程核心概念

## 方法引用 (Method Reference)

你如何使用 `Method Reference` 将方法调用引用到另一个方法上？

### Java 中的 `default` 方法是什么？我们可以在 `Interface` 中提供方法实现吗？

`default` 方法作为接口的一个新特性被引入。`default` 方法允许接口具有实现的方法。

这些方法被标记为 `default` 关键字，并提供了向接口添加新方法的方法。

#### 在 `Interface` 中添加 `default` 方法

我们可以在 `Interface` 中添加 `private` 方法吗？

你可以在 `Interface` 中使用 `static` 方法吗？

### 计算 `List` 中 `Integers` 的平均值

### 从 `list` 中找到最大 (`MAX`) 数字

### 给定一个整数列表，编写一个 Java 程序过滤掉偶数，将剩余的奇数翻倍，然后返回所有结果数字的和。

## 什么是 `var`？

`var` 是一个接受类型为 `X` 的输入并提供相同类型的输出的 `FunctionalInterface`（注：此处指变量）。它与返回与输入类型相同的 `Result` 的 `Function` 相同。

100

## 什么是 `BinaryOperator`？

它是接受 2 个输入（相同类型）并提供相同类型 `Output` 的 `Functional Interface`。

33

## 什么是 `Consumer`？

你提供的：10

## 什么是 `Supplier`

`Supplier` 演示：简单来说，我们可以说，它在不接受任何输入的情况下提供值。

## 如何创建 `Thread`？

`Thread` 正在运行……

## 什么是 `Lambda Expression`？

## 参考书籍

请参考以下关于 Java 函数式编程的书籍。

我专门为 Java 函数式编程编写了这本书，其中我讨论了 `Stream`、`Lambda Expression`、`Method Reference` 以及其他特性，从非常基础的水平到专家水平都有。

书籍链接：https://www.amazon.in/Java-Functional-Programming-industry-practices-ebook/dp/B0CHTV3TWR/ref=tmm_kin_swatch_0?_encoding=UTF8&dib_tag=se&dib=eyJ2IjoiMSJ9.LTBpL1aLeOJTflVVRJLD_qjU1hUQlPs1TDeXVqKNqqkNTLoganQLNlsBM3R6CQ4znU4cxPIOgaHH65Q4w0A8Z7Wwz3DuDVF5dySqfYAIwxGQ2lHoWkzOgYTBkJhlsJ2tDaipRuO_Cu8-oRukNLrpJNDxfAUBr2YtJtaZPv8_3lhlCRJSkTgx8FI2eX5w75WT0w8CS-lM_wnEa8QDnKzivV8sj3247KOswDu3-VgfjI.tMkuKJR3Un8fd6uUKoQlXQWBnPyv0tAW7O_WOtClYp0&qid=1715674856&sr=8-3



# 方法引用 (Method Reference)

你如何使用 `Method Reference` 将方法调用引用到另一个方法上？

## Java 中的 `default` 方法是什么？我们可以在 `Interface` 中提供方法实现吗？

`default` 方法作为接口的一个新特性被引入。`default` 方法允许接口具有实现的方法。

这些方法被标记为 `default` 关键字，并提供了向接口添加新方法的方法。

### 在 `Interface` 中添加 `default` 方法

我们可以在 `Interface` 中添加 `private` 方法吗？

你可以在 `Interface` 中使用 `static` 方法吗？

### 计算 `List` 中 `Integers` 的平均值

### 从 `list` 中找到最大 (`MAX`) 数字

### 给定一个整数列表，编写一个 Java 程序过滤掉偶数，将剩余的奇数翻倍，然后返回所有结果数字的和。

## 什么是 `var`？

`var` 是一个接受类型为 `X` 的输入并提供相同类型的输出的 `FunctionalInterface`（注：此处指变量）。它与返回与输入类型相同的 `Result` 的 `Function` 相同。

(注：此处为翻译逻辑，原文中在不同段落重复了关于 `var` 的定义描述，此处已按原文结构进行翻译)

## 什么是 `BinaryOperator`？

它是接受 2 个输入（相同类型）并提供相同类型 `Output` 的 `Functional Interface`。

## 什么是 `Consumer`？

你提供的：10

## 什么是 `Supplier`？

`Supplier` 演示：简单来说，我们可以说，它在不接受任何输入的情况下提供值。

## 如何创建 `Thread`？

`Thread` 正在运行……

## 什么是 `Lambda Expression`？

请参考以下关于 Java 函数式编程的书籍。

我专门为 Java 函数式编程编写了这本书，其中我讨论了 `Stream`、`Lambda Expression`、`Method Reference` 以及其他特性，从非常基础的水平到专家水平都有。

https://www.amazon.in/Java-Functional-Programming-industry-practices-ebook/dp/B0CHTV3TWR/ref=tmm_kin_swatch_0?_encoding=UTF8&dib_tag=se&dib=eyJ2IjoiMSJ9.LTBpL1aLeOJTflVVRJLD_qjU1hUQlPs1TDeXVqKNqqkNTLoganQLNlsBM3R6CQ4znU4cxPIOgaHH65Q4w0A8Z7Wwz3DuDVF5dySqfYAIwxGQ2lHoWkzOgYTBkJhlsJ2tDaipRuO_Cu8-oRukNLrpJNDxfAUBr2YtJtaZPv8_3lhlCRJSkTgx8FI2eX5w75WT0w8CS-lM_wnEa8QDnKzivV8sj3247KOswDu3-VgfjI.tMkuKJR3Un8fd6uUKoQlXQWBnPyv0tAW7O_WOtClYp0&qid=1715674856&sr=8-3

# 如何在 Java 中创建线程？

使用 `Thread` 类

## 什么是虚拟线程？

如何创建虚拟线程？

你好

创建 10K 普通线程和虚拟线程并检查所耗时间。

创建 10K 虚拟线程。

## 什么是有序集合（Sequenced Collection）？

有序集合演示

我们如何从有序集合中获取反向集合数据？

从有序集合中移除第一个/最后一个元素

向有序集合的末尾和开头添加元素

### 什么是结构化并发？

解释结构化并发的示例代码

# 示例代码

```
https://github.com/playwithjavaDOTin/Functional-Java-Practice.git
```

# 作者简介

```
https://www.amazon.in/stores/Amitesh-Kumar-Ray/author/B0CJ5TLKFW?ref=ap_rdr&isDrIntegrated=true&shoppingPortalEnabled=true
```
