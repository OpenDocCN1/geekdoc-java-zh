
```java
package zoo;
import java.util.function.*;
public class TicketTaker {
    private static int AT_CAPACITY = 100;
    public int takeTicket(int currentCount,
        UnaryOperator<Integer> counter) {
        return counter.applyAsInt(currentCount);
    }
    public static void main(String[] theater) {
        final TicketTaker bob = new TicketTaker();
        final int oldCount = 50;
        final int newCount = bob.takeTicket(oldCount, t -> {
            if(t > AT_CAPACITY) {
              throw new RuntimeException(
                "Sorry, max has been reached"
              );
            }
            return t + 1;
        });
        System.out.print(newCount);
    }
}
```

## A. 50

## B. 51

+ C. 代码由于 lambda 表达式无法编译。

+ D. 代码由于其他原因无法编译。

+ E. 代码可以编译，但在运行时打印异常。

+ 31. 使用带有 collector 参数的 `collect()` 方法执行并行归约（parallel reduction）的三个要求是什么？（选择三个。）

+ A. Collector 参数被标记为 `concurrent`（并发）。

+ B. 流的元素实现了 `Comparable` 接口。

+ C. 流是并行的。

+ D. 流是安全的。

+ E. 流或 Collector 被标记为 `unordered`（无序）。

+ F. 流不是原始流（primitive stream）。

+ 32. 关于以下代码哪些是正确的？（选择两个。）

```java
27: public static void main(String[]) s {
28: Predicate dash = c -> c.startsWith("-");
29: System.out.println(dash.test("-"));
30:
31: Consumer clear = x -> System.out.println(x);
32: clear.accept("pink");
33:
34: Comparator<String> c = (String s, String t) -> 0;
35: System.out.println(c.compare("s", "t"));
36: }
```

A. 代码可以编译。

B. 一行无法编译。

C. 两行无法编译。

D. 三行无法编译。

E. 如果修复了任何无法编译的行，输出包含 pink。

F. 如果修复了任何无法编译的行，输出不包含 pink。

33. 哪个接口返回原始类型（primitive）？

+ A. BiPredicate

+ B. Supplier

+ C. LongFunction

+ D. UnaryOperator

+ E. DoublePredicate

+ F. 以上都不是

34. 给定以下代码，哪些 lambda 表达式是累加器（accumulator）的最佳选择？（选择两个）。

```java
import java.util.*;
import java.util.function.*;
class Accumulator {
    int i = 0;
    List<String> words = new ArrayList<>();
    public void test() {
        BiFunction<Integer,Integer,Integer> x = 
        List.of(1,2,3,4,5).stream()
        .reduce(0, (s1,s2)->s1+s2);
    }
}
```

A. (a,b)

B. (a,b) -> 5

C. (a,b)

E. (a,b) -> words.add("awesome")

F. (a,b) -> 0

35. 填充使两个方法产生相同的输出。

```java
private void longer(Optional<String> opt) {
    opt.map("run: " +).forEach(System.out::println);
}
private void shorter(Optional<String> opt) {)
```

A. isPresent

B. ifPresent

C. forEach

D. isPresent

E. 以上都不是

36. 使用方法引用重写这个 lambda

```java
() -> Math
```

A. Math

B. Math

C. ()

D. Math

E. 以上都不是

37. 哪种操作可以在流流水线中出现多次？

+ A. 源 (Origin)

B. 汇点 (Sink)

C. 源 (Source)

D. 中间操作 (Intermediate operation)

E. 终端操作 (Terminal operation)

38. 关于下列哪些是正确的？

```java
21: var list = List.of('c', 'b', 'a');
22: list.stream()
23: .sorted()
24: .findAny()
25: .forEach(System.out::println)
26: System.out.println(list.stream());
```

A. 两个流都保证打印 a。

B. 两个流都会打印 cba。

C. 只有一个流保证打印 a。

D. 只有一个流会打印 cbaba。

E. 代码无法编译。

39. 哪个函数接口进入空白处可以让类编译？

```java
package groceries;
import java.util.*;
import java.util.function.*;
public class Market {
    private static void checkPrices(List<Double> prices,
            scanner) {
        prices.forEach(scanner);
    }
    public static void main(String[] right) {
        List<Double> prices = List.of(1.2, 6.5, 3.0);
        checkPrices(prices,
        p -> {
            String result = p < 5 ? "Correct" : "Too high";
            System.out.println(result);
        });
    }
}
```

A. Consumer

B. Consumer<Integer>

C. DoubleConsumer

D. Supplier<Double>

E. 以上都不是

40. 下列哪个不是有效的 lambda 表达式？

A. (Integer j, k) -> 5

B. (p,q) -> p+q

C. (Integer x, Integer y) -> x*

D. (left,right) -> {return "null";};

E. 这些都是有效的。

41. 下一个程序的输出是什么？

```java
import java.util.*;
public class Concat {
    public String concat1(List<String> values) {
        return values.parallelStream()
            .reduce("a",
            (x,y)->x+y::concat);
    }
    public String concat2(List<String> values) {
        return values.parallelStream()
            .reduce((w, z)->z+w).get();
    }
    public static void main(String[] questions) {
        Concat c = new Concat();
        var list = List.of("Cat","Hat");
        String x = c.concat1(list);
        String y = c.concat2(list);
        System.out.print(x+" "+y);
    }
}
```

A. CatHatCat

+ B. aCataHat HatCat

+ C. 代码无法编译，因为 concat1() 中的流返回的是 Optional。

+ D. 代码由于其他原因无法编译。

+ E. 运行时会打印出一个异常。

+ F. 以上都不是。

+ 42. 在三个函数式接口中，哪一个与其他两个不等价？

+ A. BiFunction<Double, Double, Double>

+ B. BinaryOperator<Double>

+ C. DoubleFunction<Double>

+ D. 以上都不是。这三个都是等价。

+ 43. 给定以下代码段，应该进行哪些更改才能使 JVM 将此过程处理为当前归约（reduction）？（选择两个。）

```
var w = Stream.of("c", "a", "t")
  collect(HashSet::new, Set::add, Set::addAll);
  System.out.println(w);
```

+ A. 将 HashSet 替换为 LinkedHashSet。

+ B. 将流标记为并行流（parallel）。

+ C. 移除 collect 方法的第二个参数。

+ D. 移除 collect 方法的第三个参数。

+ E. 将 HashSet 替换为 ConcurrentSkipListSet。

+ F. 将流标记为无序（unordered）。

+ 44. 填充空白使得此代码输出三行：

```
var list = new ArrayList<String>();
list.add("Atlanta");
list.add("Chicago");
list.add("New York");
list.stream()
  .filter(
  ).forEach(System.out::println);
```

+ A. String::isEmpty

+ B. !String::isEmpty

+ C. String::!isEmpty

+ D. String::isNotEmpty

+ E. 以上都不是

+ 45. 下面内容的输出是什么？

```
var chars = Stream.generate(() -> 'a');
chars.filter(c -> c < 'b')
  .sorted()
  .findFirst()
  .ifPresent(System.out::print);
```

+ A. a

+ B. 代码成功运行但没有任何输出。

+ C. 代码未完成。

+ D. 以上都不是。

+ 46. 下一个代码段的预期输出是什么？

```
Stream.iterate(1, x -> x + 1)
  .limit(5)
  .skip(2)
  .peek(System.out::print)
  .collect(Collectors.toList())
  .forEach(System.out::print);
```

+ A. 无法编译。

+ B. 运行时抛出异常。

+ C. 运行时不打印任何输出。

+ D. 345345

+ E. 334455

+ F. 代码段的行为在……之前无法确定。

+ 47. 下一个程序的输出是什么？

```java
package ai;
import java.util.function.*;
public class Android {
    public void wakeUp(Supplier supplier) { // d1
        supplier.get();
    }
    public static void main(String[] electricSheep) {
        Android data = new Android();
        data.wakeUp(() -> System.out.print("Started!")); // d2
    }
}
```

+ A. Started!

+ B. 代码仅因为行 d1 而无法编译。

+ C. 代码仅因为行 d2 而无法编译。

+ D. 代码因为行 d1 和 d2 无法编译。

+ E. 代码由于其他原因无法编译。

+ 48. 填充空白使得代码打印 *8.0-8.0*（选择两个。）

```java
var ints = IntStream.of(6, 10);
var longs = ints.mapToLong(i -> i);
var first = longs.____;

var moreLongs = LongStream.of(6, 10);
var stats = moreLongs.summaryStatistics();
var second = stats.____;
System.out.println("*" + first + "-" + second + "*");
```

+ A. 第一个空白处 averageDouble()

+ B. 第一个空白处 average().getAsDouble()

+ C. 第一个空白处 getAverage().get()

+ D. 第二个空白处 average().getDouble()

+ E. 第二个空白处 average().get()

+ F. 第二个空白处 getAverage()

+ 49. 从 DoubleConsumer 开始向下填充，填写表格中缺失的值。

| 函数式接口 | 方法签名中的参数数量 |

|---|---|

| DoubleFunction | |

| IntFunction | |

| LongSupplier | |

| ObjDoubleConsumer | |n |

+ A. 0, 1, 1, 2

+ B. 0, 1, 0, 2

+ C. 0, 2, 1, 2

+ D. 1, 1, 0, 2

+ E. 1, 1, 1, 1

+ F. 以上都不是

+ 50. 从 DoubleConsumer 开始向下填充，填写表格中的值。对于以下选项，假设 R 是一个泛型。

| 函数式接口 | 返回类型 |

|---|---|

| DoubleConsumer | |

| IntFunction | |

| LongSupplier | |

| ObjDoubleConsumer | |n |

+ A. double, int, long, R

+ B. double, R, long, R

+ C. R, int, long, R

+ D. R, int, long, void

+ E. void, int, long, void

+ F. void, R, long, void

+ 51. 下一个程序的可能的输出是什么？

```java
package salvage;

import java.util.*;
import java.util.stream.*;
public record Car(String model, int year) {
    @Override
    public String toString() {return model; }

    public static void main(String[] args) {
        var cars = new ArrayList<Car>();
        cars.add(new Car("Mustang", 1966));
        cars.add(new Car("Thunderbird", 1967));
        cars.add(new Car("Escort", 1975));
        var map = cars
            .stream()
            .collect(Collectors.groupingBy(Car::year));
        System.out.print(map);
    }
}
```

+ A. 1975=[Escort], 1967=[Thunderbird], 1966=[Mustang]

+ B. {1975=[Escort], 1967=[Thunderbird], 1966=[Mustang]}

+ C. 代码无法编译。

+ D. 代码无限挂起。

+ E. 程序在运行时抛出异常。

+ F. 以上都不是。

+ 52. 这个代码输出多少行？
