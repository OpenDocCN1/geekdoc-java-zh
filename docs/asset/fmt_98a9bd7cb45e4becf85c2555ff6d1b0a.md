
按部门划分员工人数：
IT has 3 employee(s)
Marketing has 2 employee(s)
Sales has 2 employee(s)

图 17.15 | 每个部门的员工人数。

## 17.6.7 累加和平均员工薪资

图 17.16 展示了 Stream 方法 `mapToDouble`（第 119、126 和 132 行），它将对象映射为 `double` 值并返回一个 `DoubleStream`。在此例中，我们将 `Employee` 对象映射到它们的薪资，这样我们就可以计算总和和平均值。`mapToDouble` 方法接收一个实现函数接口 `java.util.function.ToDoubleFunction` 的对象。该接口的 `applyAsDouble` 方法调用对象上的实例并返回一个 `double`。第 119、126 和 132 行分别向 `mapToDouble` 传递了实例方法引用 `Employee::getSalary`，该方法以 `double` 类型返回员工薪资。编译器将此方法引用转换为实现 `ToDoubleFunction` 接口的对象。

```java
// 使用 DoubleStream 方法累加员工薪资

System.out.printf("%nSum of Employees' salaries (via sum method): %.2f%n",
    list.stream()
        .mapToDouble(Employee::getSalary)
        .sum());

// 使用 Stream reduce 方法计算员工薪资总和

System.out.printf("%Sum of Employees' salaries (via reduce method): %.2f%n",
    list.stream()
        .mapToDouble(Employee::getSalary)
        .reduce(0, (value1, value2) -> value1 + value2));

// 使用 DoubleStream average 方法计算员工薪资平均值

System.out.printf("%Average of Employees' salaries: %.2f%n",
    list.stream()
        .mapToDouble(Employee::getSalary)
        .getAsDouble());

} // end main

} // end class ProcessingEmployees
```

员工薪资和（通过 sum 方法）：34524.67
员工薪资和（通过 reduce 方法）：34525.67
员工薪资平均值：4932.10

图 17.16 | 累加和平均员工薪资。

第 118–120 行创建了一个 `Stream<Employee>`，将其映射为 `DoubleStream`，然后调用 `DoubleStream` 方法计算员工薪资的总和。第 125–127 行也使用了员工薪资，但使用的是 `DoubleStream` 方法 `reduce` 而不是 `sum`——我们在第 17.3 节通过 `IntStreams` 引入了 `reduce` 方法。最后，第 131–134 行使用 `DoubleStream average` 计算员工薪资的平均值，如果 `DoubleStream` 不包含任何元素，它将返回一个 `OptionalDouble`。在此例中，我们知道流中的元素，因此只需调用 `OptionalDouble.getAsDouble()` 来获取结果。请记住，你还可以使用 `orElse` 来指定当在空 `DoubleStream` 上调用该方法而无法计算平均值时应该使用的值。

## 17.7 从文件创建 `Stream<String>`

图 17.17 使用 lambda 表达式总结文件中每个单词出现的次数，然后按字母顺序按字母分组显示单词摘要。这通常被称为索引（[http://en.wikipedia.org/wiki/Concordance_(publishing)]）。索引常用于分析出版作品。例如，William 和 Christopher Marlowe 的作品曾被用来质疑他们是否为同一个人。图 17.18 显示了程序的输出。图 17.17 的第 16 行创建了一个正则表达式 `Pattern`，我们将用它将文本行拆分为各个单独的单词。该 `Pattern` 代表一个或多个连续的空白字符。（我们在第 14.7 节中介绍了正则表达式。）

**图 17.17** | 统计文本文件中单词的出现次数。

| A | I | R |
|---|---|---|
| a: 2 | inputs: 1 | result: 1 |
| and: 3 | instruct: 1 | results: 2 |
| application: 2 | introduces: 1 | run: 1 |
| arithmetic: 1 | J | S |
| B: 1 | java: 1 | save: 1 |
| begin: 1 | jdk: 1 | screen: 1 |
| C: 1 | L | sum: 1 |
| calculates: 1 | last: 1 | T |
| calculations: 1 | later: 1 | that: 3 |

图 17.18 | 文本文件中单词出现次数的统计

## 17.8 生成随机值流

最后，为了显示单词及其按字母计数的摘要（即索引表），第 32–37 行向 Map 方法的 `forEach` 传递了一个 lambda 表达式。该 lambda（一个 `BiConsumer`）接收两个参数——letter 和 list，分别代表 `Character` 键和 `List` 值，对应于集合操作产生的 Map 中的每个键值值对。该 lambda 的体体包含两条语句，它必须被包括在花括号中。第 34 行的语句将键显示在一行。第 35–36 行的语句从 List 中获取 `Map.Entry<String, Long>`，它调用 Stream 的 `forEach` 来显示每个 Map 条目的键和值。

## 17.8 生成随机值流

在图 6.7 中，我们演示了投掷 6,000,000 次六面骰子，并使用外部迭代（for 循环）和一个确定要递增哪个计数器的 `switch` 语句来汇总每个面的出现频率。然后，我们使用执行外部迭代的语句显示了结果。在图 7.7 中，我们重新实现了图 6.7，将 `switch` 语句替换为一个递增数组中计数器的单语句——该版本的投掷仍然使用外部迭代来产生和汇总 6,000,000 次投掷，并显示结果。该示例的之前两个版本都使用了可变变量来控制外部迭代并汇总结果。图 17.9 使用一个完成所有操作的单语句，利用 lambda、流、内部迭代且不使用可变变量来投掷 6,000,000 次骰子、计算频率并显示结果。

```java
// Fig. 17.9 RandomIntStream.java

// 使用流投掷 6,000,000 次骰子

import java.security.SecureRandom;
import java.util.Map;
import java.util.function.Function;
import java.util.stream.IntStream;
import java.util.stream.Collectors;

public class RandomIntStream {

    public static void main(String[] args) {

        SecureRandom random = new SecureRandom();

        // roll a die 6,000,000 times and summarize the results

        System.out.printf("%-6d%s%n", "Face", "Frequency");

        random.ints(6000000, 1)
            .boxed()
            .collect(Collectors.groupingBy(Function.identity(),
                Collectors.counting()))
            .forEach((face, frequency) -> {
                System.out.printf("%-6d%d%n", face, frequency);
            });

    }

 // end class RandomIntStream

}
```
