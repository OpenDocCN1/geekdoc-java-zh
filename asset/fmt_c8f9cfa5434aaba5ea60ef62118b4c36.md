
```java
var r1 = new Riddle();
var r2 = new Riddle();
var s = Executors.newFixedThreadPool(2);
s.submit(() -> r1.getQuestion(r2));
s.execute(() -> r2.getAnswer(r1));
s.shutdown();
```

- A. 运行时产生死锁。
- B. 运行时产生活锁。
- C. 程序成功完成。
- D. 代码无法编译。
- E. 代码在运行时无限挂起。
- F. 输出无法提前确定。

### 23. 哪个 `ScheduledExecutorService` 方法会导致两个线程同时执行同一个动作？

- A. `scheduleAtFixedDelay()`
- B. `scheduleAtFixedRate()`
- C. `scheduleWithFixedDelay()`
- D. `scheduleAtSameRate()`
- E. `scheduleWithRate()`
- F. 以上皆非

## 24. 下一个程序的输出是什么？

```java
package java.util.concurrent.*;

public class Athlete {

    int stroke = 0;

    public synchronized void swimming() {
        stroke++;
    }

    private int getStroke() {
        synchronized(this) { return stroke; }
    }

    public static void main(String... laps) {
        ExecutorService s = Executors.newFixedThreadPool(10);
        Athlete a = new Athlete();
        for(int i=0; i<1000; i++) {
            s.execute(() -> a.swimming());
        }
        s.shutdown();
        System.out.print(a.getStroke());
    }
}
```

- A. 运行时产生死锁。
- B. 运行时产生活锁。
- C. 1000
- D. 代码无法编译。
- E. 在运行之前结果未知，因为 `stroke` 不是以线程安全的方式写入的，写入可能会丢失。
- F. 以上皆非。

## 25. 下列哪项可能由竞态条件（race condition）引起？

- A. 线程被永久拒绝访问某种资源
- B. 程序无限挂起
- C. 一个 `int` 变量错误地报告操作执行的次数
- D. 两个线程积极地尝试重启一个保证以相同结束的进程
- E. 两个线程无休止地等待

## 26. 关于以下内容的哪个陈述是正确的？

```java
package my;

import java.util.*;

public class ThreadSafe {

    private List<Integer> data = new ArrayList<>();

    public synchronized void add(int value) {
        data.add(value);
    }

    public int getValue(int index) {
        return data.get(index);
    }

    public int size() {
        synchronized(this) {
            return data.size();
        }
    }
}
```

- A. 代码编译且是安全的。
- B. 代码编译但不是安全的。
- C. 因为 `size()` 方法代码无法编译。
- D. 因为 `getValue()` 方法代码无法编译。
- E. 因为某种原因代码无法编译。
- F. 以上不是。

## 27. 两个方法在填充 `print2()` 时与 `print1()` 产生相同的输出？假设 10 秒足够完成所有任务。

```java
public static void print1(AtomicInteger counter) {
    System.out.println(counter.incrementAndGet());
}

public static void print2(AtomicInteger counter) {
    System.out.println(counter.decrementAndGet());
}
```

- A. `decrementAndGet()`
- B. `incrementAndGet()`
- C. 两个都是
- D. 两个都不是

## 28. 多次执行以下程序的输出是什么？

```java
package bears;

import java.util.*;

public class Bounce {

    public static void main(String... args) {
        List<Integer> list = new ArrayList<>();
        ExecutorService s = Executors.newFixedThreadPool(2);
        for(int i=0; i<4; i++) {
            s.execute(() -> {
                synchronized (list) {
                    list.add(i);
                }
            });
        }
        s.shutdown();
        s.awaitTermination(10, TimeUnit.SECONDS);
        System.out.println(list);
    }
}
```

- A. 只有第一个流是相同的。
- B. 只有前两个流是相同的。
- C. 只有前三个流是相同的。
- D. 所有流都是相同的。
- E. 没有任何流输出是相同的。
- F. 以上不是。

## 29. 以下代码中有多少行包含编译错误？

```java
11: ScheduledExecutorService t = Executors
12: newThreadScheduledExecutor();
13: Future result = t.execute(System.out::println);
14: t.invokeAll(null);
15: t.scheduleFixedRate(() -> {return;}, 5, TimeUnit.MINUTES);
```

- A. 一
- B. 一
- C. 二
- D. 三
- E. 以上不是

## 30. 以下程序运行时打印多少次 W？

```java
package crew;

import java.util.concurrent.*;
import java.util.stream.*;

public class Boat {

    private void waitFinished(CyclicBarrier c) {
        try {
            c.await();
            System.out.print("W");
        } catch (Exception e) {}
    }

    public void row(ExecutorService s) {
        var cb = new CyclicBarrier(5);
        IntStream.iterate(1, i -> i+1)
            .limit(12)
            .forEach(i -> s.submit(() -> waitFinished(cb)));
    }

    public static void main(String[] args) {
        ExecutorService service = null;
        try {
            service = Executors.newCachedThreadPool();
            new Boat().row(service);
        } finally {
            service.shutdown();
        }
    }
}
```

- A. 零。
- B. 十。
- C. 十二。
- D. 代码无法编译。
- E. 输出无法提前确定。
- F. 以上不是。

## 31. 使用上一个问题的 boat 类，程序的最终状态是什么？

- A. 程序在运行时产生异常。
- B. 程序成功终止。
- C. 因为没有关闭 `ExecutorService`，程序无限挂起。
- D. 程序在运行时挂起。
- E. 以上不是。

## 32. 给定以下代码片段，关于 p1 和 p2 行打印值的哪个陈述是正确的？

```java
var db = Collections.synchronizedList(new ArrayList<>{});
IntStream.range(1,6)
  .parallel()
  .map(i -> { db.add(i); return i;})
  .forEachOrdered(System.out::print); // p1
System.out.println(db.forEach(System.out::print)); // p2
```

- A. 它们总是相同的。
- B. 它们有时是相同的。
- C. 它们从不相同。
- D. 代码无法编译。
- E. 该代码将在运行时抛出 `ConcurrentModificationException`。
- F. 以上都不是。

## 33. 给定以下程序，`TV Time` 预计会被打印多少次？假设程序创建的每个任务都有 10 秒的时间足够执行。

```java
import java.util.concurrent.*;
import java.util.concurrent.locks.*;

public class Television {

    private static Lock myTurn = new ReentrantLock();

    public void watch() {
        try {
            if (myTurn.lock(5, TimeUnit.SECONDS)) {
                System.out.println("TV Time");
                myTurn.unlock();
            }
        } catch (InterruptedException e) {}
    }

    public static void main(String[] args) throws Exception {
        var newTv = new Television();
        for (int i = 0; i < 3; i++) {
            new Thread(() -> newTv.watch()).start();
        }
        Thread.sleep(10*1000);
    }
}
```

- A. 一次。
- B. 三次。
- C. 代码无法编译。
- D. 代码在运行时无限挂起。
- E. 代码在运行时抛出异常。
- F. 输出结果无法提前确定。

## 34. 给定原始数组，假设每个语句都是独立执行的，以下语句中有多少个会在运行时进入无限循环？

```java
var original = new ArrayList<Integer>(List.of(1,2,3));
```

```java
var copy1 = new ArrayList<Integer>(original);
for(Integer q : copy1)
    copy1.add(1);
```

```java
var copy2 = new CopyOnWriteArrayList<Integer>(original);
for(Integer q : copy2)
    copy2.add(2);
```

```java
var copy3 = new LinkedBlockingQueue<Integer>(original);
for(Integer q : copy3)
    copy3.offer(3);
```

```java
var copy4 = Collections.synchronizedList(original);
for(Integer q : copy4)
    copy4.add(4);
```

- A. 0
- B. 一个
- C. 两个
- D. 三
- E. 四
- F. 代码无法编译。

## 35. 哪一个 `ExecutorService` 方法保证所有正在运行的任务都以有序的方式停止？

- A. `shutdown()`
- B. `shutdownNow()`
- C. `halt()`
- D. `shutdownAndTerminate()`
- E. 以上都不是

## 36. 假设 10 秒时间足够所有任务完成，以下程序的输出是什么？

```java
import java.util.concurrent.*;

public class Bank {

  static int cookies = 0;

  public synchronized void deposit(int amount) {
    cookies += amount;
  }

  public synchronized void withdrawal(int amount) {
    cookies -= amount;
  }

  public static void main(String[] args) throws Exception {
    var teller = Executors.newScheduledThreadPool(50);
    Bank bank = new Bank();
    for(int i=0; i<25; i++) {
      teller.submit(() -> bank.deposit(5));
      teller.submit(() -> bank.withdrawal(5));
    }
    teller.shutdown();
    teller.awaitTermination(10, TimeUnit.SECONDS);
    System.out.print(bank.cookies);
  }
}
```

- A. 0
- B. 125
- C. -125
- D. 代码无法编译。
- E. 结果在运行之前未知。
- F. 抛出了异常。

## 37. 以下程序的输出输出什么？

```java
import java.util.*;

public class SearchList<T> {

  private List<T> data;
  private boolean foundMatch = false;

  public SearchList(List<T> list) {
    this.data = list;
  }

  public void exists(T v,int start, int end) {
    if(end-start==0) {
    } else if(end-start==1) {
      foundMatch = foundMatch ||
      v.equals(data.get(start));
    } else {
      final int middle = start + (end-start)/2;
      new Thread(() -> exists(v,start,middle)).run();
      new Thread(() -> exists(v,middle,end)).run();
    }
  }

  public static void main(String[] args) throws Exception {
    List<Integer> data = List.of(1,2,3,4,5,6);
    SearchList<Integer> t = new SearchList<Integer>(data);
    t.exists(5, 0, data.size());
    System.out.print(t.foundMatch);
  }
}
```

- A. true
- B. false
- C. 代码无法编译。
- D. 结果在运行之前未知。
- E. 抛出了异常。
- F. 以上都不是。

## 38. 给定以下代码段，关于在 q1 和 q2 行打印的值，哪个陈是正确的？

```java
```
