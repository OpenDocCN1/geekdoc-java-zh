
```java
import java.util.concurrent.atomic.*;
import java.util.stream.*;
public class TicketTaker {
    long ticketsSold;
    final AtomicInteger ticketsTaken;
    public TicketTaker() {
        ticketsSold = 0;
        ticketsTaken = new AtomicInteger(0);
    }
    public void performJob() {
        IntStream.iterate(1, p -> p+1)
            .parallel()
            .limit(100)
            .forEach(i -> ticketsTaken.getAndIncrement());
        IntStream.iterate(1, q -> q+1)
            .parallel()
            .limit(500)
            .forEach(i -> ++ticketsSold);
        System.out.print("ticketsTaken+" + " "+ticketsSold);
    }
    public static void main(String[] args) {
        new TicketTaker().performJob();
    }
}
```

- A. `TicketTaker` 构造函数无法编译。
- B. `performJob()` 方法无法编译。
- C. 类可以编译。
- D. 打印的第一个数字始终是 100。
- E. 打印的第二个数字始终是 500。
- F. 运行时抛出 `ConcurrentModificationException`。

### 9. 鉴于原始数组，假设每个语句都独立执行，以下有多少个 for 语句会导致运行时产生异常：

```java
var original = List.of(1,2,3,4,5);

var copy1 = new CopyOnWriteArrayList<Integer>(original);
for(Integer w : copy1)
    copy1.remove(w);

var copy2 = Collections.synchronizedList(original);
for(Integer w : copy2)
    copy2.remove(w);

var copy3 = new ArrayList<Integer>(original);
for(Integer w : copy3)
    copy3.remove(w);

var copy4 = new ConcurrentLinkedQueue<Integer>(original);
for(Integer w : copy4)
    copy4.remove(w);
```

- A. 零
- B. 一个
- C. 二
- D. 三
- E. 四
- F. 代码无法编译。

### 10. 填空：__________ 是 ________ 的一种特殊情况，即两个或多个活动线程尝试获取同一组锁但未成功。

- A. 死锁，活锁
- B. 死锁，资源饥饿
- C. 活锁，资源饥饿
- D. 资源饥饿，竞态条件
- E. 资源饥饿，活锁
- F. 以上都不是

### 11. 下一个程序的输出是什么？

```java
import java.util.stream.*;
public class Bull {
    void charge() {
        IntStream.range(1,6)
            .parallel()
            .forEach(System.out::print);
    }
    public static void main(String[] args) {
        var b = new Bull();
        b.charge();
    }
}
```

- A. 12345
- B. 54321
- C. 输出无法提前确定。
- D. 代码无法编译。
- E. 运行时抛出异常。
- F. 以上都不是。

### 12. 以下程序的输出是什么？

```java
public class TpsReport {
    public void submitReports() {
        var s = Executors.newCachedThreadPool();
        var bosses = s.submit(() -> System.out.print("1"));
        s.shutdown();
        System.out.print(bosses.get());
    }
    public static void main(String[] args) {
        new TpsReport().submitReports();
    }
}
```

- A. null
- B. 1
- C. 第 6 行无法编译。
- D. 第 8 行无法编译。
- E. 运行时抛出异常。

### 13. 以下哪些静态方法不存在于 `Executors` 类？（选择两个。）

- A. `newFixedScheduledThreadPool()`
- B. `newThreadPool()`
- C. `newFixedThreadPool(int)`
- D. `newSingleThreadExecutor()`
- E. `newSingleScheduledThreadPool(int)`
- F. `newSingleScheduledExecutor()`

### 14. 以下程序打印多少次 Ready？

```java
package parade;
import java.util.concurrent.*;
public class CartoonCat {
    private void await(CyclicBarrier c) {
        try {
            c.await();
        } catch (Exception e) {}
    }
    public void march(CyclicBarrier c) {
        var s = Executors.newSingleThreadExecutor();
        for(int i=0; i<2; i++) {
            s.execute(() -> await(c));
        }
        s.shutdown();
    }
    public static void main(String... strings) {
        new CartoonCat().march(new CyclicBarrier(4, () -> System.out.println("Ready")));
    }
}
```

- A. 零
- B. 一
- C. 三
- D. 代码无法编译。
- E. 运行时抛出异常。

### 15. 假设你需要一个线程执行器来为限制为五个线程的 `CyclicBarrier` 创建任务。你应该使用 `Executors` 中的哪个静态方法？

- A. `newSingleThreadExecutor()`
- B. `newSingleScheduledExecutor()`
- C. `newCachedThreadPool()`
- D. `newFixedThreadPool(2)`
- E. 以上都不是

### 16. 下图表示两个线程共享共同变量的读/写操作。每个线程首先从内存中读取变量的值，然后将变量的新值写回内存。哪幅图展示了正确的同步？

- A. ![img/e0249ee409e157651f03d8c59357695_374_0.png](https://example.com/path/to/img/e0249ee409e157651f03d8c59357695_374_0.png)
- B. ![img/e0249ee409e157651f03d8c59357695_375_0.png](https://example.com/path/to/img/e0249ee409e157651f03d8c59357695_375_0.png)
- C. ![img/e0249ee409e157651f03d8c59357695_376_0.png](https://example.com/path/to/img/e0249ee409e157651f03d8c59357695_376_0.png)
- D. ![img/e0249ee409e157651f03d8c59357695_377_0.png](https://example.com/path/to/img/e0249ee409e157651f03d8c59357695_377_0.png)

### 17. 下一个程序的输出是什么？（选择三个。）

```java
import java.util.concurrent.atomic.*;
import java.util.stream.*;
public class Circus {
    private static volatile int seal = 0;
    private static volatile int tiger = 0;
    private static AtomicInteger lion = new AtomicInteger(0);
    public static void main(String[] tent) {
        Stream.iterate(0, x -> x + 1)
            .parallel()
            .limit(100)
            .forEach(q -> {seal++; tiger++;
                lion.incrementAndGet();});
        System.out.println(seal + "," + tiger + "," + lion);
    }
}
```

- A. 打印的第一个数字可能小于 100。
- B. 打印的第一个数字始终是 100。
- C. 打印的第二个数字可能小于 100。
- D. 打印的第二个数字始终是 100。
- E. 打印的第三个数字可能小于 100。
- F. 打印的第三个数字始终是 100。

### 18. 下一个程序的输出是什么？

```java
import java.util.*;
import java.util.concurrent.*;
public class Race {
    ExecutorService service = Executors.newFixedThreadPool(8);
    public static int sleep() {
        try { Thread.sleep(1000); } catch (Exception e) {
            return 1;
        }
    }
    public void hare() {
        try {
            Callable<Integer> c = () -> sleep();
            final var r = List.of(c,c,c);
            var results = service.invokeAll(r);
            System.out.println("Hare won the race!");
        } catch (Exception e) {e.printStackTrace();}
    }
    public void tortoise() {
        try {
            Callable<Integer> c = () -> sleep();
            final var r = List.of(c,c,c);
            Integer result = service.invokeAny(r);
            System.out.println("Tortoise won the race!");
        } catch (Exception e) {e.printStackTrace();}
    }
    public static void main(String[] p) throws Exception {
        var race = new Race();
        race.service.execute(() -> race.hare());
        race.service.execute(() -> race.tortoise());
    }
}
```

- A. "Hare won the race!" 首先打印。
- B. "Tortoise won the race!" 首先打印。
- C. 代码无法编译。
- D. 代码在运行时无限挂起。
- E. 代码在运行时抛出异常。
- F. 输出无法提前确定。

### 19. 下列哪些并发集合是有排序的？（选择两个。）

- A. `ConcurrentSkipList`
- B. `ConcurrentSkipListSet`
- C. `CopyOnWriteArray`
- D. `ConcurrentSkipListMap`
- E. `ConcurrentLinkedBlockingQueue`
- F. `LinkedBlockingQueue`

### 20. 下一个程序的输出是什么？

- A. [Filing]
- B. [Filing]3.14159
- C. [Filing]null 3.14159
- D. `f1` 的声明无法编译。
- E. `f2` 的声明无法编译。
- F. 输出无法提前确定。

### 21. 假设 10 秒足够足够所有任务完成，关于以下程序的哪些陈述是正确的？（选择两个。）

```java
import java.util.concurrent.*;
import java.util.concurrent.atomic.*;
public class Clock {
    private AtomicLong bigHand = new AtomicLong(0);
    void incrementBy10() {
        bigHand.getAndSet(bigHand.get() + 10);
    }
    public static void main(String[] c) throws Exception {
        var smartwatch = new Clock();
        ExecutorService s = Executors.newCachedThreadPool();
        for(int i=0; i<100; i++) {
            s.submit(() -> smartwatch.incrementBy10()).get();
        }
        s.shutdown();
        s.awaitTermination(10, TimeUnit.SECONDS);
        System.out.println(smartwatch.bigHand.get());
    }
}
```

- A. 代码无法编译。
- B. `incrementBy10()` 方法是线程安全的。
- C. `incrementBy10()` 方法不是线程安全的。
- D. 每次执行输出都是 1000。
- E. 输出无法提前确定。
- F. 代码在运行时无限挂起。

### 22. 执行以下程序最可能的结果是？

```java
package jokes;
import java.util.concurrent.*;
public class Riddle {
    public void sleep() {
        try { Thread.sleep(5000); } catch (Exception e) {
    }
    public String getQuestion(Riddle r) {
        synchronized {
            sleep();
            if(r != null) r.getAnswer(null);
            return "How many programmers do it take " + to change a light bulb";
        }
    }
    public synchronized String getAnswer(Riddle r) {
        sleep();
        if(r != null) r.getAnswer(null);
        return "None, that's a hardware problem";
    }
    public static void main(String... unused) {
```
