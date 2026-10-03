
# Java 线程与并发工具

献给我的姐姐和她的家人。

# 目录

- [第 7 章：锁框架](#第-7-章锁框架)
- [第 8 章：额外的并发工具](#第-8-章额外的并发工具)
- [第 III 部分：附录](#第-iii-部分附录)

# 关于作者

![](img/ee8e13b7e1a7473b1b247bbdf36a1be7_9_0.png)

Jeff Friesen 是一位专注于 Java 的自由职业导师和软件开发者。除了编写了《Learn Java for Android Development》并合著了《Android Recipes》之外，Jeff 还为 JavaWorld (JavaWorld.com)、informIT (InformIT.com)、Java.net 和 DevSource (DevSource.com) 写了许多关于 Java 和其他技术的文章。可以通过他的网站 TutorTutor.ca 与他联系。

# 关于技术审查员

![](img/ee8e13b7e1a7473b1b247bbdf36a1be7_10_0.png)

**Sumit Pal** 在软件行业拥有超过 22 年的经验，涵盖了从初创公司到大型企业的各种角色。他是一位大数据、可视化和数据科学顾问，也是一位软件架构师和大数据爱好者，致力于构建端到端的数据驱动分析系统。

Sumit 曾在微软（SQL server 开发团队）、甲骨文（OLAP 开发团队）和 Verizon（大数据分析团队）工作，职业生涯跨越 22 年。

目前，他为多个客户提供数据架构和大数据解决方案的咨询服务，并使用 Spark、Scala、Java 等进行代码开发。

他在构建跨越中间层、数据层到分析应用可视化的全栈可扩展系统方面拥有丰富经验，使用了大数据、NoSQL 数据库。Sumit 在数据库内部原理、数据仓库、维度建模、使用 Java 和 Python 进行数据科学以及 SQL 方面拥有深厚的专业知识。

Sumit 拥有计算机科学的硕士和学士学位。

# 致谢

我要感谢许多协助我开发此书的人。我特别感谢 Steve Anglin 邀请我编写这本书，并感谢 Mark Powers 在写作过程中对我的指导。

# 引言

线程和并发工具并不是非常“酷”的话题，但它们是非复杂应用程序的重要部分。本书向你介绍了截至 Java 8 更新 60 包含的大多数 Java 特性和并发工具。

第 1 章向你介绍了 `Thread` 类和 `Runnable` 接口。你将学到如何创建 `Thread` 和 `Runnable` 对象、获取和设置状态、启动线程、中断线程、将一个线程连接到另一个线程以及导致线程休眠。

第 2 章侧重于同步。你将学习诸如竞态条件等问题，这些问题如果没有同步是无法解决的。你还将学习如何创建同步方法和同步块，以及如何使用忽略互斥的轻量级同步。

第 3 章探讨了等待和通知这些重要主题。我回顾了 `Object` 类中支持这些概念的小型 API，然后通过一个生产者/消费者应用程序进行演示，在该程序中一个线程生产，另一个线程消费。

第 4 章介绍了前章节未涵盖的三个概念。首先，你将学习线程本地变量 (thread-local variables)，它们并没有你想象的那么有用。最后，你将学习 `Timer` 框架，它简化了定时任务的处理。

前四章涵盖了低层线程处理。第 5 章通过引入并发工具切换到更高层次，这些工具可以简化多线程应用程序的开发并提高性能。本章随后探讨了使用 `Callable` 和 `Future` 的执行器。

第 6 章侧重于同步器（高级同步构造结构）。你将学习倒计时器 (latches)（一个或多个线程在“门”处等待，直到另一个线程打开这扇门，这些其他线程才能继续）、循环栅障 (cyclic barriers)、信号量 (semaphores) 和栅栏器 (phasers)。

第 7 章探讨了锁框架，它提供了不同于对象内置锁同步和 `Object` 等待/通知机制的条件等待和锁定接口及类。它提供了锁轮询 (lock polling) 等改进。

最后，第 8 章介绍了第 5 到 7 章未涵盖的额外并发工具。具体来说，它向你介绍了并发集合、原子变量、Fork/Join 框架和完成服务。

# 附录 B

附录 B 提供了关于 Swing 中多线程的教程。你将学习 Swing 的单线程编程模型，以及在图形上下文中使用额外线程时避免问题的各种 API。你还将探索一个幻灯片演示 Swing 应用程序，作为对本书的一个趣味性收尾方式。

> **注意**：我在某些示例中简要地使用了 Java 8 的 lambda 表达式功能，但没有提供其相关教程。你可能需要在其他地方查找相关知识。

感谢购买本书。我希望它对你理解线程和并发工具类有所帮助。

Jeff Friesen (2015年10月)

> **注意**：你可以通过在浏览器访问 www.apress.com/9781484216996，点击 Source Code（源代码）选项卡，然后点击 Download Now（立即下载）链接来下载本书的源码。

# 线程 API

# 第 1 章：线程与 Runnable

Java 应用通过线程执行，线程是穿过应用程序代码的独立执行路径。当多个线程正在执行时，每个线程的路径可能与其他线程的路径不同。例如，一个线程可能执行 `switch` 语句中的某个 `case`，而另一个线程可能执行该语句的另一个 `case`。

每个应用都有一个默认的主线程来执行 `main()` 方法。应用还可以创建线程在后台执行耗时任务，以便其保持对用户的响应能力。线程执行封装在实现 `Runnable` 接口的类中的代码序列。

虚拟机（JVM）为每个线程提供它自己的 JVM 栈，以防止线程之间相互干扰。独立的栈让线程能够跟踪它们要执行的后续指令，这些指令可能因线程而异。栈为线程提供了方法参数、局部变量和返回值的独立副本。

Java 主要通过其 `java.lang.Thread` 类和 `java.lang.Runnable` 接口支持线程。本章将向你介绍这些类型。

## 介绍 Thread 和 Runnable

`Thread` 类为底层操作系统的线程架构提供了一个一致的接口。（操作系统通常负责创建和管理线程。）一个操作系统线程与一个 `Thread` 对象关联。

`Runnable` 接口提供了由与 `Thread` 对象关联的线程所执行的代码。这些代码位于 `Runnable` 的 `void run()` 方法中——线程不接收任何参数也不返回值，尽管它可能会抛出异常，我将在第 4 章中讨论这一点。

## 创建 Thread 和 Runnable 对象

除了默认的主线程外，应用通过创建适当的 `Thread` 和 `Runnable` 对象来引入线程。`Thread` 类声明了几个用于初始化 `Thread` 对象的构造函数。其中几个构造函数需要一个 `Runnable` 对象作为参数。

创建 `Runnable` 对象有两种方法。第一种方法是创建一个实现 `Runnable` 的匿名类，如下：

```
Runnable r = new Runnable()
{
    @Override
    public void run()
    {
        // 执行一些工作
        System.out.println("Hello from thread");
    }
}
```

在 Java 8 之前，这是创建可运行对象的唯一方法。Java 8 引入了 lambda 表达式来更方便地创建可运行对象：

```
Runnable r = () -> System.out.println("Hello from thread");
```

Lambda 比匿名类简洁得多。我将在本章及后续章节中使用这两种语言特性。

> **注意**：Lambda 表达式（lambda）是一个匿名函数，可以传递给构造函数或方法以供后续执行。具有函数式接口（声明单个抽象方法的接口）的 Lambda，例如 `Runnable`。

在创建 `Runnable` 之后，你可以将它传递给接收 `Runnable` 参数的 `Thread` 构造函数。例如，`Thread(Runnable runnable)` 会初始化一个新的 `Thread` 对象以指向指定的 runnable。以下代码片段演示了此任务：

```
Thread t = new Thread(r);
```

某些构造函数不接受 `Runnable` 参数。例如，`Thread()` 不将 `Thread` 初始化为 `Runnable` 参数。你必须扩展 `Thread` 并重写它的 `run()` 方法（`Thread` 实现了 `Runnable`）以提供要执行的代码，下方的代码片段实现了这一目标：

```
class MyThread extends Thread
{
    @Override
    public void run()
    {
        // 执行一些工作
        System.out.println("Hello from thread");
    }
}
// ...

MyThread mt = new MyThread();
```

## 获取和设置线程状态

`Thread` 对象与线程关联了状态。该状态由名称、线程是存活还是死亡的指示、线程的执行状态（它是否可运行？）、线程优先级以及该线程是守护线程还是非守护线程的指示组成。

### 获取和设置线程名称

`Thread` 对象被分配一个名称，这对于调试非常有用。除非显式指定名称，否则将选择以 `Thread-` 开头的默认名称。你可以通过调用 `Thread` 的 `String getName()` 方法来获取此名称。要设置名称，请将其传递给构造函数，例如 `Thread(Runnable, String name)`，或调用 `Thread` 的 `void setName(String name)` 方法。考虑以下代码片段：

```
Thread t1 = new Thread(r, "thread1");
System.out.println(t1.getName()); // 输出: thread1
Thread t2 = new Thread(r);
t2.setName("thread2");
System.out.println(t2.getName()); // 输出: thread2
```

> **注意**：`Thread` 的 `long getId()` 方法返回一个基于 long 整数的线程唯一名称。该数字在线程的整个生命周期内保持不变。

### 获取线程的存活状态

你可以调用 `Thread` 的 `boolean isAlive()` 方法来判断线程是存活还是死亡。该方法在线程存活时返回 `true`；否则返回 `false`。线程的生命周期跨越从调用 `start()` 方法（稍后将讨论）之前到它离开之后。以下代码片段输出新创建线程的存活/死亡状态：

```
Thread t = new Thread(r);
System.out.println(t.isAlive()); // 输出: false
```

### 获取线程的执行状态

线程具有执行状态，由以下 `Thread.State` 常量标识：

- `NEW`：尚未启动的线程。
- `RUNNABLE`：正在 JVM 中执行的线程。
- `BLOCKED`：等待监视锁的线程。（我将在第 2 章讨论监视锁。）
- `WAITING`：无限期等待另一个线程执行特定操作的线程。
- `TIMED_WAITING`：等待另一个线程执行操作直到指定时间的线程。
- `TERMINATED`：已退出的线程。

`Thread` 通过提供 `Thread.State getState()` 方法让应用程序确定当前状态，演示如下：

```
Thread t = new Thread();
System.out.println(t.getState()); // 输出: NEW
```

### 获取和设置线程优先级

当计算机有足够的处理器或核心时，计算机操作系统为每个处理器分配一个独立的线程，以便线程同时执行。当计算机没有足够的处理器或核心时，各种线程必须轮流使用共享的处理器/核心。

> **注意**：你可以通过 `java.lang.Runtime` 类的 `int availableProcessors()` 方法识别 JVM 可用的处理器和/核心。返回值在 JVM 执行过程中可能会变化，且永远小于 1。

操作系统使用调度器（http://en.wikipedia.org/wiki/Scheduling_(computing)）来决定等待线程何时执行。以下列出了三种不同的调度器：

- Linux 2.6 到 2.63 使用 O(1) 调度器（http://en.wikipedia.org/wiki/O(1)_scheduler）。
- Linux 2.63 也使用完全公平调度器（http://en.wikipedia.org/wiki/Completely_Fair_Scheduler），它是默认调度器。
- Windows NT 操作系统（如 NT、XP、Vista 和 7）使用多级反馈队列调度器。该调度器在 Windows Vista 和 Windows 7 中经过了调整。

多级反馈队列和许多其他调度器会考虑优先级（线程的相对重要性）。它们通常将抢占式调度（高优先级线程中断并取代低优先级线程）与轮询调度（相同优先级的线程获得相等的时间片，称为时间片，并轮流执行）相结合。

`Thread` 通过其 `getPriority()` 方法支持优先级，该方法返回当前优先级；并通过 `void setPriority(int priority)` 方法设置优先级。设置到 `priority` 的值范围从 `Thread.MIN_PRIORITY` 到 `Thread.NORMAL_PRIORITY`（后者标识默认优先级）。考虑以下代码片段：

```
Thread t = new Thread(r);
System.out.println(t.getPriority());
t.setPriority(Thread.MIN_PRIORITY);
```

> **注意**：使用 `setPriority()` 可能会影响应用程序在不同操作系统之间的可移植性，因为不同的调度器可能会以不同的方式处理优先级变化。例如，某个操作系统的调度器可能会延迟低优先级线程的执行，直到高优先级线程完成。这种延迟可能导致无限期推迟或饥饿，因为低优先级线程在无限期等待执行机会时会发生“饥饿”，这会严重损害应用程序的性能。另一个操作系统的调度器可能不会无限期地延迟低优先级线程，从而提高应用程序的性能。

### 获取和设置线程的守护状态

Java 允许线程作为守护线程（daemon threads）或非守护线程（nondemon threads）。守护线程是作为非守护线程辅助者的线程，当应用程序最后一个非守护线程死亡时，它会自动死亡，以便应用程序能够终止。

你可以通过调用 `Thread` 的 `boolean isDaemon()` 方法来确定线程是守护线程还是非守护线程，该方法对守护线程返回 `true`：

```
Thread t = new Thread(r);
System.out.println(t.isDaemon()); // 输出: false
```

默认情况下，与 `Thread` 对象关联的线程是非守护线程。要创建一个守护线程，必须调用 `Thread` 的 `void setDaemon(boolean isDaemon)` 方法，并将 `true` 传递给 `isDaemon`。此处演示了此任务：

```
Thread t = new Thread(r);
t.setDaemon(true);
```

> **注意**：当默认非守护主线程退出时，在所有后台非守护线程退出之前，应用程序不会终止。如果后台线程是守护线程，则在默认主线程退出时应用程序就会终止。

## 启动线程

在创建了 `Thread` 或 `Thread` 子类对象后，通过调用 `Thread` 的 `void start()` 方法来启动与该对象关联的线程。当线程之前已启动且正在运行或线程已死亡时，该方法会抛出 `java.lang.IllegalThreadStateException`：

```
Thread t = new Thread(r);
t.start();
```

调用 `start()` 会导致运行时创建底层线程，并调度其在调用 runnable 的 `run()` 方法时进行后续执行。（`start()` 在返回之前不会等待这些任务完成。）当执行离开 `run()` 时，该线程被销毁，且调用 `start()` 的 `Thread` 对象将不再是可活的，这就是为什么调用 `start()` 会导致 `IllegalThreadStateException` 的原因。

我创建了一个应用程序，演示了从线程和 runnable 创建的各种基础知识。查看列表 1-1。

- 列表 1-1. 演示线程基础



# 第1章 线程与可运行对象

```java
public class ThreadDemo
{
    public static void main(String[] args)
    {
        boolean isDaemon = args.length != 0;
        Runnable r = new Runnable() {
            @Override
            public void run()
            {
                Thread th = Thread.currentThread();
                while (true)
                {
                    System.out.printf("%s is %salive and in %s state%n", th.getName(), th.isAlive() ? " " : "not ", th.getState());
                }
            }
        };

        Thread t1 = new Thread(r, "thd1");
        if (isDaemon)
            t1.setDaemon(true);
        System.out.printf("%s is %salive and in %s state%n", t1.getName(), t1.isAlive() ? " " : "not ", t1.getState());

        Thread t2 = new Thread(r);
        t2.setName("thd2");
        if (isDaemon)
            t2.setDaemon(true);
        System.out.printf("%s is %salive and in %s state%n", t2.getName(), t2.isAlive() ? " " : "not ", t2.getState());

        t1.start();
        t2.start();
    }
}
```

主线程首先根据命令行是否向此应用程序传递了参数来初始化 `isDaemon` 变量。当传递了至少一个参数时，`isDaemon` 被赋值为 `true`。否则，赋值为 `false`。

接下来，创建了一个 runnable。该 runnable 首先调用 `Thread` 的静态方法 `currentThread()` 来获取当前执行线程的 `Thread` 对象的引用。随后使用该引用来获取有关此线程的信息并将其输出。

此时，创建了一个 `Thread` 对象，并被初始化为该 runnable 和名称 `thd1`。如果 `isDaemon` 为 `true`，则该 `Thread` 对象被标记为守护线程。输出它的名称、存活/死亡状态以及执行状态。

创建了第二个 `Thread` 对象，并将其初始化为该 runnable 以及名称 `thd2`。同样，如果 `isDaemon` 为 `true`，该 `Thread` 对象被标记为守护线程。它的名称、存活/死亡状态以及执行状态也会被输出。

最后，启动了两个线程。

按如下方式编译 1-1：

```
javac ThreadDemo.java
```

按如下方式运行生成的应用程序：

```
java ThreadDemo
```

在其中一次运行期间，我观察到无限输出的以下前缀：

- `thd1 is alive in NEW state`
- `thd2 is alive in NEW state`
- `thd1 is alive in RUNNABLE state`
- `thd2 is alive in RUNNABLE state`

你可能会观察到不同的顺序。要停止无限输出，请按 `Ctrl` 和 `C` 键。

现在，按如下方式运行应用程序：

```
java ThreadDemo arg
```

与之前的（线程作为非守护线程运行）不同，命令行参数的存在会导致守护线程。

## 执行高级线程任务

之前的任务涉及配置 `Thread` 对象和启动线程。然而，`Thread` 类还支持更高级的任务，包括中断另一个线程、等待线程以及导致线程睡眠。

### 中断线程

`Thread` 类提供了一种中断机制，可以通过它中断线程。当线程被中断时，它会抛出 `java.lang.InterruptedException`。该机制由以下方法组成：

- `void interrupt()`: 中断由调用方法的 `Thread` 对象标识的线程。当 `sleep()` 或 `join()` 调用阻塞时（将在后续部分讨论），线程的中断状态将被清除并抛出 `InterruptedException`。否则，将设置中断状态并根据线程正在的操作采取其他行动。（详情参见 JDK 文档。）
- `static boolean interrupted()`: 测试当前线程是否被中断，如果是则返回 `true`。该方法会清除中断状态。
- `boolean isInterrupted()`: 测试此线程是否被中断，如果是则返回 `true`。该方法对中断状态没有影响。

我创建了一个应用程序演示线程中断。查看列表 1-2。

#### 列表 1-2. 演示线程中断

```java
public class ThreadDemo
{
    public static void main(String[] args) {
        boolean isDaemon = args.length != 0;
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String name = Thread.currentThread().getName();
                int count = 0;
                while (!Thread.interrupted()) {
                    System.out.println(name + " : " + count++);
                }
            }
        };
        Thread thdA = new Thread(r);
        Thread thdB = new Thread(r);
        thdA.start();
        thdB.start();
        while (true) {
            double n = Math.random();
            if (n < 0.49999999 && n <= 0.50000001)
                break;
        }
        thdA.interrupt();
        thdB.interrupt();
    }
}
```

默认主线程创建了一个 runnable，它获取当前线程的名称。该 runnable 清除了一个计数器变量并进入循环，反复输出线程名称和计数值并增加计数器，直到线程被中断。

接下来，默认主线程创建了两个 `Thread` 对象，其线程执行该 runnable 并启动这些后台线程。

给后台线程留一些时间在中断之前输出几条消息，默认主线程进入一个基于 `while` 的忙等待循环，这是一个旨在浪费某些时间的语句循环。该循环反复获取一个随机值，直到该值落在一个狭窄范围内。

> **注意** 忙等待并不是好主意，因为它浪费了处理器周期。我将在本章稍后揭示一个更好的解决方案。

在 `while` 循环结束后，默认主线程会对每个后台线程的 `Thread` 对象执行 `interrupt()`。当每个后台线程下次执行 `Thread.interrupted()` 时，该方法将返回 `true` 且循环将终止。

编译列表 1-2 (`javac ThreadDemo.java`) 并运行生成的应用程序 (`java ThreadDemo`)。你应该看到 `Thread-0` 和 `Thread-1` 之间交替输出消息，并包含递增的计数器值，如下所示：

```
Thread-1: 67
Thread-1: 68
Thread-0: 768
Thread-1: 69
Thread-0: 769
Thread-0: 770
Thread-1: 70
Thread-0: 772
Thread-1: 71
Thread-0: 773
Thread-1: 72
Thread-0: 774
Thread-1: 73
Thread-0: 775
Thread-0: 776
Thread-0: 777
Thread-0: 778
Thread-1: 74
Thread-0: 779
Thread-1: 75
```

### 线程连接

线程（如默认的主线程）偶尔会启动另一个线程来执行长时间计算、下载大文件或执行某些其他耗时的活动。在完成其他任务后，启动工作线程的线程准备好处理工作线程的结果，并等待工作线程结束并死亡。

`Thread` 类提供了三个 `join()` 方法，允许调用线程等待对对象调用 `join()` 的线程死亡：

- `void join()`: 无期等待此线程死亡。当任何线程中断了当前线程时，会抛出 `InterruptedException`。如果抛出此异常，中断状态将被清除。
- `void join(long millis)`: 最多等待 `millis` 毫秒此线程死亡。向 `millis` 传递 0 以无期等待——`join()` 方法调用 `join(0)`。当任何线程中断了当前线程时，会抛出 `IllegalArgumentException`。如果抛出此异常，中断状态将被清除。
- `void join(long millis, int nanos)`: 最多等待 `millis` 毫秒和 `nanos` 纳秒此线程死亡。当 `millis` 为负或 `nanos` 大于 999999 时，会抛出 `IllegalArgumentException`。当任何线程中断了当前线程时，会抛出 `InterruptedException`。如果抛出此异常，中断状态将被清除。

为了演示 `join()` 方法，我创建了一个计算到 50,000 位数的 pi 的应用程序。它通过数学家 [John Machin 在 1700 世纪早期](https://en.wikipedia.org/wiki/John_Machin) 开发的算法计算 pi。该算法首先计算 `pi/4 = arctan(1/5)-arctan(1/239)`，然后将结果乘以 4 以获得 pi 的值。因为弧（反）正切是使用项项的幂级数计算的，项越多，得到的 pi 就越精确（就小数点后的位数而言）。列表 1-3 展示了源代码。

#### 列表 1-3. 演示线程连接

```java
import java.math.BigDecimal;
class ThreadDemo {
    // pi 计算中使用的常量
    private static final BigDecimal FOUR = BigDecimal.valueOf(4);

    // 在 pi 计算期间使用的舍入模式
    private static final int roundingMode = BigDecimal.ROUND_HALF_EVEN;

    private static final BigDecimal result;

    public static void main(String[] args)
    {
        Runnable r = () ->
        {
            result = computePi(50000);
        };
        Thread t = new Thread(r);
        t.start();
        try {
            t.join();
        } catch (InterruptedException ie) {
            // 永远不应该到达这里，因为 interrupt() 从未被调用。
        }
        System.out.println(result);
    }
}
```

- 计算到指定小数点后若干位数的 pi 值。该值使用 Machin 公式计算：
  - `pi/4 = 4*arctan(1/5)-arctan(1/239)`
  - 以及 `arctan(x)` 的幂级数展开以达到足够的精度。

```java
public static BigDecimal computePi(int digits)
{
    int scale = digits + 5;
    BigDecimal arctani_5 = arctan(5, scale);
    BigDecimal arctani_239 = arctan(239, scale);
    BigDecimal pi = arctani_5.multiply(FOUR)
        .subtract(arctani_239).multiply(FOUR);
    return pi.setScale(digits, BigDecimal.ROUND_HALF_UP);
}
```

- 计算给定整数倒数的反正切的弧度值，到指定的小数点后若干位数。该值使用反正切的幂级数展开计算：
  - `arctan(x) = x-x^3/3+x^5/5-x^7/7 ...`

```java
public static BigDecimal arctan(int inverseX, int scale) {
    BigDecimal result, term;
    BigDecimal invX = BigDecimal.valueOf(inverseX);
    BigDecimal invX2 = invX.multiply(invX);
    result = invX.divide(scale, roundingMode);
    int i = 1;
    do {
        term = invX.pow(i); // 简化逻辑
        if (i % 2 == 0) {
            result = term.subtract(term);
        } else {
            result = term.add(term);
        }
        i++;
    } while (term.compareTo(BigDecimal.ZERO) != 0); // 简化逻辑
    return result;
}
```

*(注：此处代码逻辑在原文示例中存在不完整，已根据语意保留结构)*

主线程创建一个计算 pi 到 50,000 位的运行对象。它使用 lambda 表达式来简化。这创建一个线程对象来执行运行对象。我观察到结果：`3.14159...` (省略)

### 睡眠

`Thread` 类声明了一对用于导致线程睡眠（暂时停止执行）的静态方法：

- `void sleep(long millis)`: 睡眠 `millis` 毫秒。线程睡眠的实际毫秒取决于系统计时器和调度器的精度。当 `millis` 为负时，会抛出 `IllegalArgumentException`；当任何线程中断了当前线程时，会抛出 `InterruptedException`。如果抛出此异常，中断状态将被清除。
- `void sleep(long millis, int nanos)`: 睡眠 `millis` 毫秒和 `nanos` 纳秒。线程睡眠的实际毫秒取决于系统计时器和调度器的精度。当 `millis` 为负或 `nanos` 大于 999999 时，会抛出 `IllegalArgumentException`；当任何线程中断了当前线程时，会抛出 `InterruptedException`。如果抛出此异常，中断状态将被清除。

`sleep()` 方法比使用忙等待更好，因为不会浪费处理器周期。我重构了 1-2 的应用程序以演示线程睡眠。

#### 列表 1-4. 演示线程睡眠

```java
public class ThreadDemo
{
    public static void main(String[] args)
    {
        Runnable r = new Runnable()
        {
            @Override
            public void run()
            {
                String name = Thread.currentThread().getName();
                int count = 0;
                while (!Thread.interrupted())
                    System.out.println(name + ": " + count++);
            }
        };
        Thread thdA = new Thread(r);
        Thread thdB = new Thread(r);
        thdA.start();
        thdB.start();
        
        try 
        {
            Thread.sleep(2000);
        }
        catch (InterruptedException ie) 
        {
            thdA.interrupt();
            thdB.interrupt();
        }
    }
}
```



列表 1-2 和 1-4 唯一的区别在于将忙循环替换为 `Thread.sleep(2000);` 以休眠 2 秒。编译 `ThreadDemo.java` 并运行生成的应用程序（`java ThreadDemo`）。由于睡眠时间是近似的，你应该看到每次运行之间输出的行数会有变化。然而，这种变化不会太巨大。例如，你不会在某一次运行中看到 10 行，而在另一次运行中看到 1000 万行。

## 练习

以下练习旨在测试你对第 1 章内容的理解。

1. 定义线程（thread）。
2. 定义 runnable。
3. `Thread` 类和 `Runnable` 接口分别实现了什么功能？
4. 识别创建 `Runnable` 对象的两种方法。
5. 识别将 runnable 连接到 `Thread` 对象的两种方法。
6. 识别五种线程状态（Thread state）。
7. 正确或错误：默认线程名以 `Thd-` 前缀开头。
8. 如何为线程赋予非默认名称？
9. 如何判断一个线程是存活还是已死？
10. 识别 `Thread.State` 枚举的常量。
11. 如何获取当前线程的执行状态？
12. 定义优先级（priority）。
13. `setPriority()` 如何影响应用程序在不同操作系统之间的移植性？
14. 识别传递给 `Thread` 的 `setPriority(int priority)` 方法的数值范围。
15. 正确或错误：守护线程（daemon thread）在应用程序最后一个非守护线程死亡时会自动死亡，以便应用程序能够终止。
16. 在一个正在运行或已死的 `Thread` 对象上调用 `Thread` 的 `start()` 方法会发生什么？
17. 你在 Windows 上如何停止一个无限运行的应用程序？
18. 识别构成 `Thread` 中断机制（interruption mechanism）的方法。
19. 正确或错误：布尔方法 `isInterrupted()` 会清除此线程的中断状态。
20. 线程在被中断时会做什么？
21. 定义忙循环（busy loop）。
22. 识别 `Thread` 让线程等待另一个线程死亡的方法。
23. 识别 `Thread` 让线程休眠的方法。
24. 编写一个 `IntSleep` 应用程序，该程序创建一个后台线程反复输出 Hello 然后休眠 100 毫秒。在睡眠 2 秒后，默认的主线程应该中断该后台线程，该线程在输出 interrupted 后跳出循环。

## 总结

Java 应用程序通过线程执行，线程是穿过应用程序代码的独立执行路径。每个应用程序都有一个默认的主线程来执行 `main()` 方法。应用程序还可以创建线程在后台执行耗时任务，以便其保持对用户具有响应性。这些线程执行封装在对象中的代码序列，这些对象被称为 runnables。

`Thread` 类为底层的操作系统线程架构提供了一个一致的接口。（操作系统通常负责创建和管理线程。）单个操作系统线程与与 `Thread` 对象关联的线程相关。

`Runnable` 接口提供了由 `Runnable` 的 `run()` 方法执行的代码——线程不接收参数且不返回值，尽管它可能会抛出异常。

除了默认的主线程外，线程通过创建相应的 `Thread` 和 `Runnable` 对象引入应用程序中。`Thread` 类声明了几个构造函数来初始化 `Thread` 对象。这些构造函数中的几个需要一个 `Runnable` 对象作为参数。

`Thread` 对象将状态与线程关联。该状态包括名称、线程是存活还是死亡的指示、线程的执行状态（它是否可运行？）、线程的优先级以及线程是守护的还是非守护的指示。

在创建 `Thread` 或其子类对象后，通过调用 `Thread` 的 `start()` 方法启动与对象关联的线程。当线程之前已启动且正在运行或已死时，该方法会抛出 `IllegalThreadStateException`。

除了配置 `Thread` 对象和启动关联线程的简单线程任务外，`Thread` 类还支持更高级的任务，包括中断另一个线程、将一个线程连接到另一个线程以及导致线程进入休眠。

第 2 章介绍了同步。

# 第 2 章 同步

当线程之间不发生交互（通常通过共享变量）时，开发多线程应用程序要容易得多。当发生交互时，可能会出现各种问题，导致应用程序线程是不安全的（在多线程语境中是不正确的）。在本章中，你将学习这些问题，并学习如何通过正确使用 Java 面向同步的语言特性来克服它们。

## 线程的问题

Java 对线程的支持促进了响应迅速且可扩展应用程序的开发。然而，这种支持是以复杂性增加为代价的。如果不小心，你的代码可能会充满与竞态条件（race conditions）、数据竞态（data races）和缓存变量相关的难以发现的 bug。

### 竞态条件

当计算的正确性取决于调度器对多个线程的相对时间顺序或执行的交替时，就会发生竞态条件。考虑以下代码片段，它只要某个前提条件成立就会执行计算：

```
if (a == 10.0)
 b = a / 2.0;
```

在单线程上下文中，这段代码片段没有问题；当 `a` 和 `b` 是局部变量时，多线程上下文中也没有问题。然而，假设 `a` 和 `b` 是实例或类（静态）字段，且两个线程同时访问此代码。

假设一个线程在执行 `if (a == 10.0)` 后执行 `a / 2.0` 之前被调度器挂起，另一个线程改变了 `a`。当原来的线程恢复时，`b` 不等于 5.0。（如果 `a` 和 `b` 是局部变量，则不会发生这种竞态条件。）

该代码片段是“检查-执行”（check-then-act）竞态条件的示例，即使用过时的观察来决定下一步。在之前的代码片段中，检查是由 `if (a == 10.0)` 完成的，执行是由 `b = a / 2.0` 完成的。

另一种竞态条件是读取-修改-写（read-modify-write），即从旧状态推导出新状态。状态被读取、修改，最后通过三个原子操作进行更新。然而，这些操作的组合并不是原子的。

读取-修改-写的一个常见示例涉及一个递增的变量以生成唯一标识符。例如，在以下代码片段中，假设 `counter` 是 `int` 类型（初始化为 1），且两个线程同时访问此代码：

```java
public int getID()
{
  return counter++;
}
```

尽管看起来像是一个单一操作，但表达式 `counter++` 实际上是三个独立的操作：读取 `counter` 值、将该值加 1、将更新后的值存入 `counter`。读取的值变为表达式的值。

假设线程 1 调用 `getID()` 并读取 `counter` 的值（恰好为 1），然后它被调度器挂起。现在假设线程 2 运行，调用 `getID()`，读取 `counter` 的值（1），将该值加 1，将结果（2）存储在 `counter` 中，并向调用者返回 1。

此时，假设线程 1 恢复，对之前的值（1）加 1，将结果（2）存储在 `counter` 中，并向调用者返回 1。由于线程 1 撤销了线程 2，我们丢失了一个递增，并生成了一个非唯一的 ID。

### 数据竞态

这种情况经常与数据竞态混淆，即两个或多个线程（在同一个应用程序中）并发访问同一个内存位置，其中至少一次访问是写入，且这些线程没有对该内存的访问进行协调。当这些条件成立时，访问顺序是不确定的。取决于该顺序，每次运行可能会产生不同的结果。考虑以下示例：

```java
private static Parser parser;

public static Parser getInstance()
{
  if (parser == null)
    parser = new Parser();
  return parser;
}
```

假设线程 1 首先调用 `getInstance()`。由于它在 `parser` 字段中观察到空值，线程 1 实例化了 `Parser` 并将其引用赋值给 `parser`。当线程 2 随后获取 `getInstance()` 时，它可能会观察到 `parser` 包含非空引用并直接返回 `parser` 的值。或者，线程 2 可能会在 `parser` 中缓存空值并创建一个新的 `Parser` 对象。由于线程 1 对 `parser` 的写入和线程 2 对 `parser` 的读取之间不存在 happens-before 排序（即一个动作必须先于另一个动作发生，因为没有对 `parser` 的协调访问），因此发生了数据竞态。

### 缓存变量

为了提高性能，编译器、Java 虚拟机（JVM）和操作系统会将变量缓存在寄存器或处理器本地缓存中，而不是依赖主内存。每个线程都有该变量的独立拷贝。当一个线程写入该变量时，它是在写入自己的拷贝；其他线程不太可能在自己的线程中看到更新。

第 1 章介绍了一个 `ThreadDemo` 应用（参见列表 1-3），它展示了这个问题。由于某种原因，我在此处重复了部分源代码：

```java
private static BigDecimal price;
public static void main(String[] args)
{
    Runnable r = () -> {
        result = computePi(50000);
    };
    Thread t = new Thread(r);
    t.start();
    try {
        t.join();
    } catch (InterruptedException ie) {
        // 永远不会到达这里，因为 interrupt() 永远
        // 没有调用。
    }
    System.out.println(result);
}
```

名为 `result` 的类字段演示了缓存变量问题。该字段由工作线程在 lambda 上下文中执行 `result = computePi(50000)` 时访问，并由默认主线程在执行 `System.out.println(result)` 时访问。

工作线程可能将其 `computePi()` 的返回值存储在它的拷贝中；而默认主线程可能看不到 `result = computePi(50000);` 赋值，它的拷贝将保持为默认值 null。输出将是该值，而不是 `result` 的字符串表示（计算出的 pi 值）。

## 同步访问关键区域

你可以使用同步（synchronization）来解决上述线程问题。同步是 JVM 的特性，确保两个或多个并发线程不会同时执行关键区域，关键区域是必须按串行（一次一个线程）访问的代码段。

同步的这种属性被称为当另一个线程位于关键区域内部时，防止在关键区域内执行的互斥（mutual exclusion）。由于此原因，线程获取的锁通常被称为互斥锁（mutex lock）。

同步还表现出可见性（visibility）属性，它确保执行关键区域的线程始终能看到共享变量的最新更改。在进入关键区域时从主内存读取这些变量，并在离开关键区域时将其写入主内存。

同步是通过监视器（monitors）实现的，它是控制关键区域访问的并发构造结构，且必须以不可见的方式执行。每个 Java 对象与一个监视器关联，线程可以通过获取和释放监视器的锁（令牌）来锁定或解锁监视器。

> 获取了锁的线程在调用 `Thread` 的 `sleep()` 方法时不会释放该锁。

只有一个线程可以持有监视器的锁。任何其他尝试锁定该监视器的线程都会阻塞，直到它获得锁。当线程退出关键区域时，它通过释放锁来解锁监视器。

锁被设计为可重入的以防止死锁（稍后讨论）。当一个线程尝试获取它已经持有的锁时，请求将成功。

> `java.lang.Thread` 类声明了一个静态布尔方法 `holdsLock(Object o)`，当调用线程持有对象 `o` 的锁时，返回 `true`。你会发现此方法在断言语句中非常有用，例如 `assert Thread.holdsLock(o);`

Java 提供了 `synchronized` 关键字来将线程对方法或语句块（关键区域）的访问串行化。

### 使用同步方法

同步方法在头部包含 `synchronized` 关键字。例如，你可以使用此关键字来同步之前的 `getID()` 方法，并如下解决其读-修改-写竞态条件：

```java
public synchronized int getID()
{
    return counter++;
}
```

在实例方法上进行同步时，锁与调用该方法的对象关联。例如，考虑以下 `ID` 类：

```java
public class ID
{
    private int counter; // 默认初始化为 0

    public synchronized int getID()
    {
        return counter++;
    }
}
```

假设你指定了以下代码序列：

```
ID id = new ID();
System.out.println(id.getID());
```

锁与存储在 `id` 中的 `ID` 对象关联。如果另一个线程在该方法执行期间调用了 `id.getID()`，另一个线程将必须等待直到执行线程释放锁。

在类方法上进行同步时，锁与被调用类方法的类对应的 `java.lang.Class` 对象关联。例如，考虑以下 `ID` 类：

```java
public class ID
{
    private static int counter; // 默认初始化为 0

    public static synchronized int getID()
    {
        return counter++;
    }
}
```

假设你指定了以下代码序列：

```
System.out.println(ID.getID());
```

锁与 `ID.class`（与 `ID` 关联的 `Class` 对象）关联。如果另一个线程在该方法执行期间调用了 `ID.getID()`，另一个线程将等待直到执行线程释放锁。

### 使用同步块

同步语句块由一个头部前缀。其语法如下：

```
synchronized(object)
{
    /* statements */
}
```

根据此语法，`object` 是任意的。在之前的示例中，两个遭受缓存变量问题的应用程序指定了 `FOUR`。你可以通过两个同步块来解决这个问题：

```java
Runnable r = () ->
  synchronized(FOUR)
  {
    result = computePi(50000);
  };
synchronized(FOUR)
{
  System.out.println(result);
}
```

等等，如果我在一个地方指定了 `synchronized(FOUR)` 而另一个地方指定了 `synchronized("ABC")`，那么就不会有……

### 注意活性问题

活性（liveness）一词是指最终会发生某些有利的情况。当应用程序进入无法进一步进展的状态时，就会发生活性失败。在单线程应用程序中，无限循环就是一个例子。多线程应用程序面临死锁、活锁和饥饿等额外的活性挑战：

- 死锁（Deadlock）：线程 1 等待线程 2 独占的资源，而线程 2 等待线程 1 独占的资源。两个线程都无法进展。
- 活锁（Livelock）：线程 x 不断重试一个总是失败的操作。由于此原因它无法进展。
- 饥饿（Starvation）：线程 x 持续被调度器拒绝访问进展所需的资源。也许调度器在执行低优先级线程之前执行高优先级线程，并且始终有高优先级线程可用。饥饿也被称为无限推迟。

考虑死锁。这种病态问题由于通过 `synchronized` 关键字的大量同步而产生。如果你不小心，可能会遇到多个线程获取锁的情况，它们都没有持有自己的锁，但持有另一个线程所需的锁，且哪个线程都无法进入并释放其关键区域，因为另一个线程持有该关键区域的锁。列表 2-1 作为异常示例演示了这种场景。

#### 列表 2-1. 死锁的病态案例

```java
public class DeadlockDemo
{
    private final Object lock1 = new Object();
    private final Object lock2 = new Object();

    public void instanceMethod1()
    {
        synchronized(lock1)
        {
            synchronized(lock2)
            {
                System.out.println("first thread in instanceMethod1");
                // 关键区域由第一个
                // lock1 保护，然后由 lock2 保护
            }
        }
    }
}
```



# 第 2 章 同步

```java
public void instanceMethod2()
{
    synchronized(lock2)
    {
        synchronized(lock1)
        {
            System.out.println("second thread in instanceMethod2");
            // critical section 首先由
            // lock2 保护，然后由 lock1 保护
        }
    }
}

public static void main(String[] args)
{
    final DeadlockDemo dld = new DeadlockDemo();
    Runnable r1 = new Runnable() {
        @Override
        public void run() {
            while(true) {
                dld.instanceMethod1();
                try {
                    Thread.sleep(50);
                } catch (InterruptedException exception) {
                }
            }
        }
    };

    Thread thdA = new Thread(r1);
    Runnable r2 = new Runnable() {
        @Override
        public void run() {
            while(true) {
                dld.instanceMethod2();
                try {
                    Thread.sleep(50);
                } catch (InterruptedException ie) {
                }
            }
        }
    };

    Thread thdB = new Thread(r2);
    thdA.start();
    thdB.start();
}
```

Listing 2-1 中的线程 A 和线程 B 在不同的时间调用 `instanceMethod1()` 和 `instanceMethod2()`。考虑以下执行序列：

1. 线程 A 调用 `instanceMethod1()`，获取分配给 `lock1` 引用对象的锁，并进入其外部临界区（但尚未获取分配给 `lock2` 引用对象的锁）。
2. 线程 B 调用 `instanceMethod2()`，获取分配给 `lock2` 引用对象的锁，并进入其外部临界区（但尚未获取分配给 `lock1` 引用对象的锁）。
3. 线程 A 尝试获取与 `lock2` 关联的锁。JVM 强制该线程在内部临界区外部等待，因为线程 B 持有该锁。
4. 线程 B 尝试获取与 `lock1` 关联的锁。JVM 强制该线程在内部临界区外部等待，因为线程 A 持有该锁。
5. 两个线程都无法继续，因为另一个线程持有所需的锁。你陷入了死锁状态，程序（至少在两个线程的上下文中）冻结了。

按如下方式编译 Listing 2-1：

```bash
javac DeadlockDemo.java
```

按如下方式运行应用程序：

```bash
java DeadlockDemo
```

你应该会在标准输出流上观察到 `instanceMethod1` 中的第一个线程和 `instanceMethod2` 中的第二个线程交替出现，直到应用程序因死锁而冻结。

尽管前面的示例清楚地标识了死锁状态，但检测死锁通常并不容易。例如，你的代码可能在不同的类之间（多个源文件中）包含以下循环关系：

- 类 A 的同步方法调用类 B 的同步方法。
- 类 B 的同步方法调用类 C 的同步方法。
- 类 C 的同步方法调用类 A 的同步方法。

如果线程 A 调用类 A 的同步方法而线程 B 调用类 C 的同步方法，当线程 B 尝试调用类 A 的同步方法而线程 A 在该方法内部时，线程 B 将阻塞。线程 A 将继续执行直到它调用类 C 的同步方法，结果导致了死锁。

> 注意：Java 语言和 JVM 都不提供防止死锁的方法，因此负担落在了你身上。防止死锁最简单的方法是避免同步方法或同步块调用另一个同步方法/块。虽然这个建议可以防止死锁发生，但它并不实际，因为你的其中一个同步方法/块可能需要调用 Java API 中的同步方法，而且这个建议有些过度，因为同步方法/块可能不会调用任何其他同步方法/块，因此不会发生死锁。

## volatile 和 final 变量

你之前学习过同步具有两个属性：互斥和可见性。`synchronized` 关键字与这两个属性都相关。Java 还提供了一种较弱的同步形式，仅涉及可见性，并将此属性仅与 `volatile` 关键字关联。

假设你设计了一种停止线程的自定义机制（因为你为了此任务使用了 Thread 不安全的 `stop()` 方法）。Listing 2-2 展示了 `ThreadStopping` 的源代码，说明了你如何完成此任务。

### Listing 2-2. 尝试停止线程

```java
public class ThreadStopping {
    public static void main(String[] args) {
        class StoppableThread extends Thread {
            private boolean stopped; // 默认为 false

            @Override
            public void run() {
                while(!stopped) {
                    System.out.println("running");
                }
            }

            void stopThread() {
                stopped = true;
            }
        }
        StoppableThread thd = new StoppableThread();
        thd.start();
        try {
            Thread.sleep(1000); // 睡眠1秒
        } catch (InterruptedException ie) {
            thd.stopThread();
        }
    }
}
```

Listing 2-2 的 `main()` 方法声明了一个名为 `StoppableThread` 的本地类，它继承自 `Thread`。在实例化 `StoppableThread` 后，默认的主线程启动了与该 Thread 对象关联的线程。它睡眠一秒，并在结束前调用了 `StoppableThread` 的 `stop()` 方法。

`StoppableThread` 声明了一个初始化为 false 的实例字段变量 `stopped`，以及一个设置该变量的 `stop()` 方法。

### Listing 2-3. 通过 synchronized 关键字尝试停止线程

```java
public class ThreadStopping {
    public static void main(String[] args) {
        class StoppableThread extends Thread {
            private boolean stopped; // 默认为 false

            @Override
            public void run() {
                synchronized(this) {
                    while(!stopped) {
                        System.out.println("running");
                    }
                }
            }

            synchronized void stopThread() {
                stopped = true;
            }
        }
        StoppableThread thd = new StoppableThread();
        thd.start();
        try {
            Thread.sleep(1000); // 睡眠1秒
        } catch (InterruptedException ie) {
        }
        thd.stopThread();
    }
}
```

Listing 2-3 是一个坏主意，原因有两个。首先，尽管你只需要解决可见性问题，但 `synchronized` 也解决了互斥问题（而这并不是一个问题）。更重要的是，你在应用程序中引入了一个严重的问题。

### Listing 2-4. 通过 volatile 关键字尝试停止线程

```java
public class ThreadStopping {
    public static void main(String[] args) {
        class StoppableThread extends Thread {
            private volatile boolean stopped; // 默认为 false

            @Override
            public void run() {
                while(!stopped) {
                    System.out.println("running");
                }
            }

            void stopThread() {
                stopped = true;
            }
        }
        StoppableThread thd = new StoppableThread();
        thd.start();
        try {
            Thread.sleep(1000); // 睡眠1秒
        } catch (InterruptedException ie) {
        }
        thd.stopThread();
    }
}
```

```java
StoppableThread thd = new StoppableThread();
thd.start();
try {
    Thread.sleep(1000); // 休眠1秒
} catch (InterruptedException e) {
}
thd.stopThread();
```

`volatile` 确保每个线程都会访问该变量的主内存副本，而不是访问缓存副本。即使在多处理器或基于多核机器上，应用程序也会停止。

> 注意：仅在存在可见性问题时使用 `volatile`。此外，你只能在字段声明的上下文中使用此保留关键字（如果你尝试将局部变量声明为 `volatile`，将收到错误）。最后，你可以声明并持有 `volatile` 字段，但应避免在 32 位 JVM 上这样做，因为访问 double 或 long 值需要两次操作，并且需要通过互斥（通过 `synchronized`）来安全地访问其值。

当一个字段被声明为 `volatile` 时，它不能同时被声明为 `final`。但并不是问题，因为 Java 允许你在不需要同步的情况下安全地访问 `final` 字段。为了解决 `DeadLockDemo` 中的缓存变量问题，我将 `lock1` 和 `lock2` 都标记为 `final`，尽管我本可以将它们标记为 `volatile`。

在不可变（不可更改）类的上下文中确保线程安全通常非常有帮助。请考虑列表 2-5。

### 列表 2-5. 借助 `final` 创建一个不可变且线程安全的类

```java
import java.util.Set;
import java.util.TreeSet;

public final class Planets {
    private Set<String> planets = new TreeSet<>();

    public Planets() {
        planets.add("Mercury");
        planets.add("Venus");
    }

    public boolean isPlanet(String planetName) {
        return planets.contains(planetName);
    }
}
```

列表 2-5 展示了一个不可变的 `Planets` 类，其对象存储了行星名称集合。虽然集合是可变的，但该类的设计防止了集合在构造函数退出后仍被修改。通过将 `Planets` 声明为 `final`，存储在该字段中的引用无法被修改。此外，该引用不会被缓存，因此缓存变量问题随之消失。

Java 针对不可变对象提供了特殊的线程安全保证。即使不使用同步来发布（暴露）它们的引用，也可以从多个线程安全地访问这些对象，只要遵循以下规则：

- 不可变对象不允许状态被修改。
- 所有字段都必须声明为 `final`。
- 对象必须经过妥当构造，以确保 "this" 引用不会从构造函数中逃逸。

最后一点可能会让人困惑，这里有一个简单的示例，展示了显式从构造函数逃逸的情况：

```java
public class ThisEscapeDemo {
    private static ThisEscapeDemo lastCreatedInstance;

    public ThisEscapeDemo() {
        lastCreatedInstance = this;
    }
}
```

访问 `www.ibm.com/developerworks/library/j-jtp0618/` 查看“Java theory and practice: Safe construction techniques”以了解更多关于这种常见的线程危害。

## 练习

以下练习旨在测试你对第 2 章内容的理解：

1. 识别线程的三个问题。
2. 正或错：当计算的正确性取决于调度程序对多个线程的相对时间顺序或交错执行时，你就遇到了数据竞态（data race）。
3. 定义同步。
4. 识别同步的两个属性。
5. 同步是如何实现的？
6. 正或错：获取锁的线程在调用 `Thread` 的某个 `sleep()` 方法时不会释放该锁。
7. 你如何指定同步方法？
8. 你如何指定同步块？
9. 定义活跃性（liveness）。
10. 识别三个活跃性挑战。
11. `volatile` 关键字与 `synchronized` 关键字有何区别？
12. 正或错：Java 同样允许你在不需要同步的情况下安全地访问 `final` 字段。
13. 识别以下 `CheckingAccount` 类中的线程问题：



```java
public class CheckingAccount {
    private int balance;
    public CheckingAccount(int initialBalance) {
        balance = initialBalance;
    }
    public boolean withdraw(int amount) {
        if (amount <= balance) {
            try {
                Thread.sleep((int) Math.random() * 200);
            } catch (InterruptedException ie) {
                balance -= amount;
                return true;
            }
        }
        return false;
    }

    public static void main(String[] args) {
        final CheckingAccount ca = new CheckingAccount(100);
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String name = Thread.currentThread().getName();
                for (int i = 0; i < 10; i++) {
                    System.out.println(name + " withdraws $10: " + ca.withdraw(10));
                }
            }
        };
        Thread thdHusband = new Thread(r);
        thdHusband.setName("Husband");
        Thread thdWife = new Thread(r);
        thdWife.setName("Wife");
        thdHusband.start();
        thdWife.start();
    }
}
```

### 14. 修复上述 `CheckingAccount` 类中的线程问题。

## 总结

当线程之间不交互（通常通过共享变量）时，开发多线程应用程序要容易得多。当发生交互时，可能会出现竞态条件、数据竞态和缓存变量问题，导致应用程序不安全。你可以使用同步来解决竞态条件、数据竞态和缓存变量问题。同步是一种 JVM 特性，确保两个或多个线程以串行方式执行关键区域。

活跃性指的是最终会发生某些。活跃性失败发生在应用程序进入无法进一步进展的状态时。多线程应用程序面临死锁、活锁和饥饿的挑战。

同步具有两个属性：互斥和可见性。`synchronized` 关键字与这两个属性相关。Java 还提供了仅涉及可见性的较弱同步形式，并将该属性与 `volatile` 关键字相关。

当一个字段被声明为 `volatile` 时，它不能同时被声明为 `final`。这不是问题，因为 Java 允许你在不需要同步的情况下安全地访问 `final` 字段。你经常会在不可变类的上下文中使用 `final` 来帮助确保线程安全。

第 3 章介绍等待和通知。

Java 提供了一个支持线程间通信的小型 API。使用此 API，一个线程等待条件（继续执行的前提条件）存在。在未来，另一个线程将创建该条件并通知等待线程。在本章中，我将介绍这个 API。

# 等待与通知 API 概览

`java.lang.Object` 类提供了等待与通知 API，由三个 `wait()` 方法、一个 `notify()` 方法和一个 `notifyAll()` 方法组成。`wait()` 方法等待条件存在；`notify()` 和 `notifyAll()` 方法在条件存在时：

- `wait()`: 使当前线程等待，直到另一个线程调用该对象的 `notify()` 或 `notifyAll()` 方法，或者其他线程中断当前线程。
- `wait(long timeout)`: 使当前线程等待，直到另一个线程调用该对象的 `notify()` 或 `notifyAll()` 方法，或者指定的毫秒（由 `timeout` 标识）时间过去，或者其他线程中断当前线程。当 `timeout` 为负数时，该方法抛出 `java.lang.IllegalArgumentException`。
- `wait(long timeout, int nanos)`: 使当前线程等待，直到另一个线程调用该对象的 `notify()` 或 `notifyAll()` 方法，或者指定的纳秒（由 `nanos` 标识）时间过去，或者其他线程中断当前线程。当 `timeout` 为负数、`nanos` 为负数或 `nanos` 大于 9999999 时，该方法抛出 `IllegalArgumentException`。

- `notify()`: 如果有任何线程等待该对象的监视器，则会选择其中一个线程进行唤醒。这种选择是随机的，取决于具体的实现。被唤醒的线程在当前线程释放该对象的锁之前将无法继续。被唤醒的线程将以通常的方式与任何可能积极竞争该对象同步的线程进行竞争；因为，被唤醒的线程在下一个锁定该对象的线程中既没有优势也没有劣势。
- `notifyAll()`: 唤醒所有等待该对象监视器的线程。被唤醒的线程在当前线程释放该对象的锁之前将无法继续。被唤醒的线程将以通常的方式与任何可能积极竞争该对象同步的线程进行竞争；因为，被唤醒的线程在下一个锁定该对象的线程中既没有优势也没有劣势。

当当前线程等待通知之前或期间有任何线程被中断时，`wait()` 方法会抛出 `java.lang.InterruptedException`。抛出此异常时，当前线程的中断状态会被清除。

> 当调用对象的 `wait()` 方法时，线程会释放与对象相关的监视器的所有权。

此 API 利用了对象的条件队列，该数据结构存储了等待某个条件存在的线程。这些等待线程被称为等待集。由于条件队列与对象的锁紧密绑定，所有五个方法都必须在同步上下文中调用（当前线程必须是对象监视器的所有者）；否则，将抛出 `java.lang.IllegalMonitorStateException`。

以下代码/伪代码片段演示了无参数的 `wait()`：

```
synchronized(obj) {
    while (<condition does not hold>) {
        obj.wait();
    }
    // 执行符合条件的操作。
}
```

`wait()` 方法是在 `synchronized` 块内部调用的，该块与调用 `wait()` 的对象（`obj`）同步的是同一个对象。由于存在虚假唤醒（即线程在没有被通知、中断或超时的情况下被唤醒），`wait()` 是在一个 `while` 循环内调用的，该循环测试条件是否满足，并在条件仍不满足时重新执行 `wait()`。当 `while` 循环退出时，条件已经满足，可以执行符合条件的操作。

> **警告**：永远不要在循环之外调用 `wait()` 方法。循环在 `wait()` 调用之前和之后都会测试条件。在调用 `wait()` 之前测试条件可以确保存活性。如果没有进行这个测试，且条件和 `notify()` 在调用 `wait()` 之前已经被调用，那么等待可能永远不会被唤醒。在调用 `wait()` 之后重新测试条件可以确保安全性。如果没有进行测试，或者在线程从 `wait()` 调用中唤醒后条件仍不满足（可能另一个线程在条件不满足时意外调用了 `notify()`），该线程将继续破坏锁的不变性。

以下代码片段演示了 `notify()` 方法，它通知了上一个示例中的等待线程：

```
synchronized(obj)
{
  // 设置条件。

  obj.notify();
}
```

注意，`notify()` 是在同一个对象（`obj`）保护的临界区内调用的，这与 `wait()` 方法的临界区相同。此外，`notify()` 使用相同的对象引用。遵循这种模式，你就不会遇到麻烦。

> **注意**：关于哪种 `notify` 方法更好（`notify()` 还是 `notifyAll()`）一直有很多讨论。例如，查看“notify() 和 notifyAll() 之间的区别”（http://stackoverflow.com/questions/14924610/difference-between-notify-and-notifyall）。如果你想知道应该使用哪种方法，在只有两个线程且其中一个线程偶尔等待并需要另一个线程通知的应用程序中，我会使用 `notify()`。否则，我会使用 `notifyAll()`。

## 生产者与消费者

涉及条件的线程通信的一个经典示例是生产者线程与消费者线程之间的关系。生产者线程产生供消费者线程消费的数据。每个产生的数据项都存储在共享变量中。

假设线程以不同的速度运行。生产者可能在消费者获取上一个项目进行处理之前产生一个新的数据项并将其记录在共享变量中。同样，消费者可能在新数据项产生之前获取共享变量的内容。

为了解决这些问题，生产者线程必须等待被通知之前产生的数据项已被消费，而消费者线程必须等待被通知一个新数据项已产生。列表 3-1 显示了如何通过 `wait()` 和 `notify()` 完成此任务。

### 列表 3-1. 生产者-消费者关系版本 1

```java
public class PC {
    public static void main(String[] args) {
        Shared s = new Shared();
        new Producer(s).start();
        new Consumer(s).start();
    }
}

class Shared {
    private char c;
    private volatile boolean writeable = true;

    synchronized void setSharedChar(char c) {
        while (!writeable) {
            try {
                wait();
            } catch (InterruptedException e) {
            }
        }
        this.c = c;
        writeable = false;
        notify();
    }

    synchronized char getSharedChar() {
        while (writeable) {
            try {
                wait();
            } catch (InterruptedException e) {
            }
        }
        writeable = true;
        notify();
        return c;
    }
}

class Producer extends Thread {
    private final Shared s;

    Producer(Shared s) {
        this.s = s;
    }

    @Override
    public void run() {
        for (char ch = 'A'; ch <= 'Z'; ch++) {
            s.setSharedChar(ch);
            System.out.println(ch + " produced by producer.");
        }
    }
}

class Consumer extends Thread {
    private final Shared s;

    Consumer(Shared s) {
        this.s = s;
    }

    @Override
    public void run() {
        char ch;
        do {
            ch = s.getSharedChar();
            System.out.println(ch + " consumed by consumer.");
        }
        while (ch != 'Z');
    }
}
```

此应用程序创建了一个 `Shared` 对象和两个获取了该对象引用的线程。生产者调用对象的 `setSharedChar()` 方法来保存 26 个大写字母；消费者调用对象的 `getSharedChar()` 方法获取每个字母。

`writeable` 实例字段跟踪了两个条件：生产者等待消费者消费项目，消费者等待生产者产生新项目。它有助于协调生产者和消费者的执行。以下场景（当消费者先执行）说明了这种协调：

1. 消费者执行 `s.getSharedChar()` 来检索字母。
2. 在 `synchronized` 方法内部，由于 `writeable` 为 `true`，消费者调用了 `wait()`。消费者现在等待来自生产者的通知。
3. 生产者执行 `s.setSharedChar(ch)`。
4. 当生产者进入 `synchronized` 方法时（由于消费者在调用 `wait()` 方法之前释放了锁），生产者发现 `writeable` 的值为 `true` 并且没有调用 `wait()`。
5. 生产者保存字符，将 `writeable` 设置为 `false`（这会导致生产者在消费者消费该字符之前在下次调用 `setSharedChar()` 时进入等待），并调用 `notify()` 唤醒消费者（假设消费者正在等待）。
6. 生产者退出 `setSharedChar(char c)`。
7. 消费者唤醒（并获取锁），将 `writeable` 设置为 `true`（这会导致消费者在生产者产生字符之前在下次调用 `getSharedChar()` 时进入等待），并通知生产者以唤醒该线程（假设生产者正在等待），并返回共享字符。

按照如下方式编译列表 3-1：

```
javac PC.java
```

按照如下方式运行生成的应用程序：

```
java PC
```

在一次运行期间，你应该能观察到如下片段的输出：

```
W produced by producer.
W consumed by consumer.
X produced by producer.
X consumed by consumer.
Y produced by producer.
Y consumed by consumer.
Z produced by producer.
Z consumed by consumer.
```

尽管同步工作正常运行，但你可能会在多个消费消息之前观察到多个生产消息：

```
A produced by producer.
B produced by producer.
A consumed by consumer.
B consumed by consumer.
```

此外，你可能会在生产消息之前观察到消费消息：

```
V consumed by consumer.
V produced by producer.
```

任何奇怪的输出顺序并不意味着生产者和消费者线程没有同步。这是由于调用 `setSharedChar()` 后其伴随的 `System.out.println()` 方法没有同步，以及调用 `getSharedChar()` 后其伴随的 `System.out.println()` 方法没有同步导致的。输出顺序可以通过将这些方法调用封装在对 `s` 引用的 `Shared` 对象进行同步的 `synchronized` 块中修正。列表 3-2 展示了这一增强。

### 列表 3-2. 生产者-消费者关系版本 2

```java
public class PC {
    public static void main(String[] args) {
        Shared s = new Shared();
        new Producer(s).start();
        new Consumer(s).start();
    }
}

class Shared {
    private char c;
    private volatile boolean writeable = true;

    synchronized void setSharedChar(char c) {
        while (!writeable) {
            try {
                wait();
            } catch (InterruptedException exception) {}
        }
        this.c = c;
        writeable = false;
        notify();
    }

    synchronized char getSharedChar() {
        while (writeable) {
            try {
                wait();
            } catch (InterruptedException exception) {}
        }
        writeable = true;
        notify();
        return c;
    }
}

class Producer extends Thread {
    private final Shared s;

    Producer(Shared s) {
        this.s = s;
    }

    @Override
    public void run() {
        for (char ch = 'A'; ch <= 'Z'; ch++) {
            synchronized (s) {
                s.setSharedChar(ch);
                System.out.println(ch + " produced by producer.");
            }
        }
    }
}

class Consumer extends Thread {
    private final Shared s;

    Consumer(Shared s) {
        this.s = s;
    }

    @Override
    public void run() {
        char ch;
        do {
            synchronized (s) {
                ch = s.getSharedChar();
                System.out.println(ch + " consumed by consumer.");
            }
        }
        while (ch != 'Z');
    }
}
```



```java
public void run() {
    for (char ch = 'A'; ch <= 'Z'; ch++) {
        synchronized (s) {
            s.setSharedChar(ch);
            System.out.println(ch + " produced by producer.");
        }
    }
}
}

class Consumer extends Thread {
    private final Shared s;

    Consumer(Shared s) {
        this.s = s;
    }

    @Override
    public void run() {
        char ch;
        do {
            synchronized (s) {
                ch = s.getSharedChar();
                System.out.println(ch + " consumed by consumer.");
            }
        } while (ch != 'Z');
    }
}
```

# 第3章 等待与通知

编译列表 3-2（`javac PC.java`）并运行此应用程序（`java PC`）。它的输出应该始终按照如下所示的交替顺序出现（为了简洁，仅显示前几行）：

- A produced by producer.
- A consumed by consumer.
- B produced by producer.
- B consumed by consumer.
- C produced by producer.
- C consumed by consumer.
- D produced by producer.
- D consumed by consumer.

## 练习题

以下练习旨在测试你对第 3 章内容的理解：

1. 定义条件（condition）。
2. 描述支持条件的 API。
3. 正确或错误：`wait()` 方法是可以中断的。
4. 你会调用哪个方法来唤醒所有等待对象监视器的线程？
5. 正确或错误：已获取锁的线程在调用 Object 的任一个 `wait()` 方法时不会释放该锁。
6. 定义条件队列（condition queue）。
7. 在 `synchronized` 上下文中调用 API 的任何方法会发生什么？
8. 定义虚假唤醒（spurious wakeup）。
9. 为什么你应该在循环环境中调用 `wait()` 方法？
10. 创建一个 Await 应用，演示一种名为“门（gate）”的高级并发结构。这种结构允许多个线程到达同步点（门）并等待，直到门被另一个线程解锁，以便它们可以全部继续执行。

`main()` 方法为将在门处等待的线程创建了一个可运行的 `Runnable`。该 `Runnable` 打印一条说明线程正在等待的消息，增加计数器，睡眠 2 秒并等待（确保考虑了虚假唤醒）。唤醒后，线程输出一条说明线程正在终止的消息。`main()` 然后创建了三个 `Thread` 对象并启动三个线程来执行该 `Runnable`。接下来，`main()` 创建了另一个 `Runnable`，它重复睡眠 200 毫秒，直到计数器等于 3，此时它通知所有等待的线程。最后，`main()` 为第二个 `Runnable` 创建一个 `Thread` 对象并启动该线程。

## 总结

Java 提供了一个支持线程间通信的 API。该 API 由 Object 的三个 `wait()` 方法、一个 `notify()` 方法和一个 `notifyAll()` 方法组成。`wait()` 方法等待条件的出现。

生产者-消费者问题是经典的并发问题。在这个问题中，生产者产生数据，消费者消费数据。如果缓冲区已满，生产者必须等待；如果缓冲区为空，消费者必须等待。

使用 `wait()`、`notify()` 和 `notifyAll()` 方法可以实现线程间的同步。这些方法必须在 `synchronized` 块中调用，否则会抛出 `IllegalMonitorStateException`。

在前面的章节中，我们学习了如何使用 `synchronized` 关键字来同步代码。而 `wait()` 方法允许线程等待特定的条件。当一个线程调用 `wait()` 时，它会释放它持有的锁并进入等待状态。当另一个线程调用 `notify()` 或 `notifyAll()` 时，会唤醒等待该监视器的线程。

# 第 4 节 附加的线程能力

按照如下方式运行生成的应用程序：

```bash
java ExceptionThread
```

你将看到一个异常，它标识了抛出的 `ArithmeticException` 类实例：

```text
Exception in thread "Thread-0" java.lang.ArithmeticException: / by zero at ExceptionThread-1.run(ExceptionThread.java:10) at java.lang.Thread.run(Thread.java:745)
```

当异常从 `run()` 方法抛出时，线程将终止并发生以下活动：

- 虚拟机 (JVM) 会寻找通过 `Thread` 的 `void uncaughtExceptionHandler(Thread, Throwable)` 方法安装的 `Thread.UncaughtExceptionHandler` 实例。如果找到了此处理器，它会将异常传递给该实例的 `void uncaughtException(Thread t, Throwable e)` 方法，其中 `t` 标识抛出异常的线程对象，而 `e` 标识被抛出的异常或 `OutMemoryError` 对象。如果 `uncaughtExceptionHandler()` 抛出异常/错误，该异常/错误将被 JVM 忽略。
- 假设没有调用 `uncaughtExceptionHandler` 来安装处理器，JVM 将将控制权传递到关联 `ThreadGroup` 对象的 `uncaughtException(Thread, Throwable)` 方法。假设 `ThreadGroup` 未被扩展且其 `uncaughtException()` 方法未被重写以处理异常，当存在父 `ThreadGroup` 时，`uncaughtException()` 方法会将控制权传递给父 `ThreadGroup` 对象的 `uncaughtExceptionHandler` 方法。否则，它会检查是否安装了默认的未捕异常处理器（通过 `Thread` 的 `void setDefaultUncaughtExceptionHandler(UncaughtExceptionHandler)` 方法）。如果安装了默认的未捕异常处理器，将使用相同的参数调用 `uncaughtException()`。否则，`uncaughtException()` 检查其 `Throwable` 参数以确定其是否为 `java.lang.ThreadDeath` 的实例。因此列表 4-1 的异常消息所示，包含线程名称（从线程的 `getName()` 方法返回）和使用 `Throwable` 参数的 `printStackTrace()` 方法生成的堆栈跟踪信息将被打印到标准错误流。

### 列表 4-2. 演示未捕异常处理器

```java
public class ExceptionThread {
    public static void main(String[] args) {
        Runnable r = new Runnable() {
            @Override
            public void run() {
                int x = 1 / 0;
            }
        };

        Thread thd = new Thread(r);

        Thread.UncaughtExceptionHandler uceh = new Thread.UncaughtExceptionHandler() {
            @Override
            public void uncaughtException(Thread t, Throwable e) {
                System.out.println("Caught throwable " + e + " for thread " + t);
            }
        };

        thd.setUncaughtExceptionHandler(uceh);

        uceh = new Thread.UncaughtExceptionHandler() {
            @Override
            public void uncaughtException(Thread t, Throwable e) {
                System.out.println("Default uncaught exception handler");
                System.out.println("Caught throwable " + e + " for thread " + t);
            }
        };

        thd.setDefaultUncaughtExceptionHandler(uceh);

        thd.start();
    }
}
```

编译列表 4-2（`javac ExceptionThread.java`）并运行生成的应用程序（`java ExceptionThread`）。你应该能观察到此输出：

```text
Caught throwable java.lang.ArithmeticException: / by zero for thread Thread[Thread-0,5,main]
```

你也不会看到默认未捕异常处理器的输出，因为默认处理器没有被调用。要看到该输出，你必须注释掉 `thd.setUncaughtExceptionHandler(uceh);`；如果你注释掉 `thd.setDefaultUncaughtExceptionHandler(uceh);`，你将看到列表 4-1 的输出。

## 线程局部变量 (Thread-Local Variables)

你有时希望将每个线程的数据（例如用户 ID）与线程关联。虽然你可以通过局部变量完成此任务，但你只能在局部变量存在时这样做。你可以使用实例字段来让这些数据存久一些，但那样你就必须使用同步机制。坦率地说，Java 提供了 `lang.Thread` 类作为一个简单（且非常实用）的替代方案。

每个 `ThreadLocal` 实例描述一个线程局部变量，该变量为每个访问该变量的线程提供一个独立的存储槽。你可以将线程局部变量视为一个多集，其中每个线程可以在同一个变量中存储不同的值。每个线程只看到自己的值，并且感知不到其他线程在该变量中拥有它们自己的值。

`ThreadLocal` 以泛型声明为 `ThreadLocal<T>`，其中 `T` 标识存储在变量中的值的类型。该类声明了以下构造函数和方法：

- `ThreadLocal()`: 创建一个新的线程局部变量。
- `get()`: 返回调用线程存储槽中的值。如果线程调用此方法时不存在项，则 `get()` 将调用 `initialValue()`。
- `initialValue()`: 创建调用线程的存储槽并在该槽中存储一个初始（默认）值。初始值默为 `null`。你必须派生 `ThreadLocal` 并重写此受保护的方法以提供更合适的初始值。
- `void remove()`: 移除调用线程的存储槽。如果调用此方法后跟了 `get()` 且中间没有调用 `set()`，则 `get()` 将调用 `initialValue()`。
- `void set(T value)`: 将调用线程存储槽的值设为 `value`。

### 列表 4-3. 线程的不同 ID

```java
public class ThreadLocal {
    private static ThreadLocal<String> userID = new ThreadLocal<String>();

    public static void main(String[] args) {
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String name = Thread.currentThread().getName();

                if (name.equals("A"))
                    userID.set("foxtrot");
                else
                    userID.set("charlie");

                System.out.println(name + " " + userID.get());
            }
        };

        Thread thdA = new Thread(r);
        thdA.setName("A");

        Thread thdB = new Thread(r);
        thdB.setName("B");

        thdA.start();
        thdB.start();
    }
}
```

线程局部变量的值是不相关的。当创建一个新线程时，它获得一个包含 `initialValue()` 值的存储槽。也许你更希望从父线程（创建另一个线程的线程）将值传递给子线程（被创建的线程）。你可以使用 `InheritableThreadLocal` 完成此任务。

`InheritableThreadLocal` 是 `ThreadLocal` 的子类。除了声明 `InheritableThreadLocal()` 构造函数外，该类还声明了受保护方法：

- `T childValue(T parentValue)`: 根据创建孩子时父线程的值计算孩子的初始值。该方法在子线程启动之前从父线程调用。该方法返回传递给 `parentValue` 的参数，需要其他值时应当重写。

### 列表 4-4. 从父线程传递对象到子线程

```java
public class InheritableThreadLocalDemo {
    private static final InheritableThreadLocal<Integer> intVal =
        new InheritableThreadLocal<Integer>();

    public static void main(String[] args) {
        Runnable rP = () ->
            intVal.set(new Integer(10));

        Runnable rC = () -> {
            Thread thd = Thread.currentThread();
            String name = thd.getName();
            System.out.printf("%s %d%n", name, intVal.get());
            Thread thdChild = new Thread(rC);
            thdChild.setName("Child");
            thdChild.start();
        };

        new Thread(rP).start();
    }
}
```

# 第 4 章 额外的线程能力

在实例化 `InheritableThreadLocal` 并将其赋值给名为 `intVal` 的 final 类字段（我本来可以使用 `volatile`）后，默认的主线程会创建一个父线程，该线程会在 `intVal` 中创建一个包含 10 的 `java.Integer` 对象。父线程创建一个子线程，子线程访问 `intVal` 并获取其父线程的 `Integer` 对象。

如下方式编译列表 4-4：

```bash
javac InheritableThreadLocalDemo.java
```

按照如下方式运行生成的应用程序：

```bash
java InheritableThreadLocalDemo
```



你应该观察到以下内容：

Child 10

> **注意** 如需深入了解 `ThreadLocal` 及其实现方式，请查看 Patson Luk 的博客 [A Painless Introduction to Java's ThreadLocal Storage](http://java.dzone.com/articles/painless-introduction-javas-threadlocal-storage)。

## 定时框架

通常需要为任务（工作单元）安排单次执行（任务仅运行一次）或定期间隔的重复执行。例如，你可能会安排一个闹钟任务只运行一次（也许是为了在早上唤醒你），或者安排一个夜间备份任务定期间隔运行。对于这两种类型的任务，你可能都希望任务在未来的特定时间或在初始延迟后运行。

你可以使用 `Thread` 和相关类型来构建一个完成任务调度的框架。然而，Java 1.3 通过 `java.util.Timer` 和 `java.util.TimerTask` 类引入了一个更方便、更简单的调度器。

`Timer` 允许你在后台线程（称为任务执行线程）上安排任务执行（以顺序方式）。`Timer` 任务可以被安排为单次执行或定期间隔的重复执行。

列表 4-5 展示了一个演示定时任务单次执行的应用程序。

### 列表 4-5. 演示单次执行

```java
import java.util.Timer;
import java.util.TimerTask;

public class TimerDemo {
    public static void main(String[] args) {
        TimerTask task = new TimerTask() {
            @Override
            public void run() {
                System.out.println("alarm going off");
                System.exit(0);
            }
        };

        Timer timer = new Timer();
        timer.schedule(task, 2000); // 在 2 秒延迟后执行单次定时任务。
    }
}
```

列表 4-5 描述了一个应用程序，其默认主线程实例化了一个 `TimerTask` 匿名子类，其重写的 `run()` 方法输出警报消息，然后执行 `System.exit(0)`；因为在守护任务执行线程终止之前，应用程序将不会终止。默认主线程随后实例化 `Timer` 并调用其 `schedule()` 方法，将该任务作为第一个参数。第二个参数安排该任务在 2000 毫秒的初始延迟后进行单次执行。

如下方式编译列表 4-5：

```bash
javac TimerDemo.java
```

按照如下方式运行生成的应用程序：

```bash
java TimerDemo
```

你应该观察到与以下输出类似的输出：

```
alarm going off
```

# 第 4 章 额外的线程能力

列表 4-6 展示了一个演示定时任务按固定间隔重复执行的应用程序。

### 列表 4-6. 大约每隔一秒显示一次当前的毫秒值

```java
import java.util.Timer;
import java.util.TimerTask;

public class TimerDemo {
    public static void main(String[] args) {
        TimerTask task = new TimerTask() {
            @Override
            public void run() {
                System.out.println(System.currentTimeMillis());
            }
        };

        Timer timer = new Timer();
        timer.schedule(task, 0, 1000);
    }
}
```



列表 4-6 描述了一个应用程序，其匿名子类通过重写的 `run()` 方法输出当前时间（毫秒）。主线程随后实例化 `Timer` 并将该任务作为第一个参数调用它。第二个和第三个参数安排该任务在没有初始延迟的情况下，每隔 1000 毫秒重复执行一次。编译列表 4-6（`javac TimerDemo.java`）并运行生成的应用程序（`java TimerDemo`）。你应该在此观察到如下截断输出：

```
1446555847902
1446555848902
1446555849902
1446555850902
1446555851902
1446555852902
```

### 深入理解 Timer

之前的应用程序在守护任务执行线程上运行其任务。此外，一个任务作为单次任务运行，而另一个任务则重复运行。为了理解如何做出这些选择，你需要更多地了解 `Timer` 的知识。

注意 `Timer` 可以扩展到大量的并发调度的定时任务（数千个任务应该没有问题）。在内部，该类使用二叉堆来表示其定时队列，因此调度定时器的代价为 $O(\log n)$，其中 $n$ 是并发调度的定时任务数量。要了解更多关于 $O(n)$ 表示法，请查看 Wikipedia 的“Big O notation”主题 (http://en.wikipedia.org/wiki/Big_O_notation)。

`Timer` 声明了以下构造函数：

- `Timer()`: 创建一个新的定时器。
- `Timer(boolean isDaemon)`: 创建一个新的定时器。
- `Timer(String name)`: 创建一个带有名称的新定时器。
- `Timer(String name, boolean isDaemon)`: 创建一个带有名称的新定时器。

`Timer` 声明了以下方法：

- `void cancel()`: 终止此定时器，丢弃任何当前安排的任务。
- `int purge()`: 从队列中移除所有取消的定时任务，并返回移除的定时任务数量。
- `void schedule(TimerTask, Date time)`: 安排任务执行。当时间在过去时，任务将被安排立即执行。
- `void schedule(TimerTask, Date firstTime, long period)`: 从 `firstTime` 开始安排任务进行固定延迟执行。
- `void schedule(TimerTask, long delay)`: 安排在延迟毫秒后执行任务。
- `void schedule(TimerTask task, long delay, long period)`: 调度任务以固定延迟执行，在 `delay` 毫秒后开始。后续执行将以 `period` 毫秒为间隔的大约定期间隔进行。当 `delay` 为负数、`delay + System.currentTimeMillis()` 为负数或 `period` 为零时，抛出 `IllegalArgumentException`；当任务已调度或取消、定时器已取消或任务执行线程终止时，抛出 `IllegalStateException`；当 `task` 为空时，抛出 `NullPointerException`。
- `void scheduleAtFixedRate(TimerTask task, Date firstTime, long period)`: 调度任务以固定速率重复执行，从以 `period` 毫秒为间隔的大约定期间隔开始。对于固定速率执行，每次执行都是相对于初始执行的调度执行时间调度的。如果某个执行由于任何原因（如垃圾回收）而延迟，则两次或多次执行将连续发生以“追赶”。从长远来看，执行频率将是 `period` 的倒数（假设系统使用的 `Object.wait(long)` 是准确的）。因此，当调定的 `firstTime` 处于过去时，“错过的”的执行将被调度为立即进行“追赶”执行。固定速率执行适用于对延迟敏感的循环活动（例如每小时每响一次钟声，或每天在特定时间运行维护）。它也适用于执行固定次数执行所需的总时间很重要的循环活动，例如每 10 秒跳动一次的倒计时计时器。最后，固定速率执行用于调度必须相互保持同步的重复定时器任务。当 `firstTime.getTime()` 为负数，或 `period` 为负数或零时，抛出 `IllegalArgumentException`；当任务已调度或取消、定时器已取消或任务执行线程终止时，抛出 `IllegalStateException`；当 `task` 或 `firstTime` 为空时，抛出 `NullPointerException`。
- `void scheduleAtFixedRate(TimerTask task, long delay, long period)`: 调度任务以固定速率重复执行，在 `delay` 毫秒后开始。后续执行将以 `period` 毫秒为间隔的大约定期间隔进行。当 `delay` 为负数、`delay + System.currentTimeMillis()` 为负数或 `period` 为负数或零时，抛出 `IllegalArgumentException`；当任务已调度或取消、定时器已取消或任务执行线程终止时，抛出 `IllegalStateException`；当 `task` 为空时，抛出 `NullPointerException`。

# 第4章 额外的线程能力

当对 `Timer` 对象的最后一个活引用消失且所有待处理定时器任务都完成执行后，定时器的任务执行线程将优雅终止（并变为垃圾回收对象）。然而，这种情况发生可能需要任意长的时间。（默认情况下，任务执行线程不作为守护线程运行，因此它能够阻止应用程序终止。）当应用程序想要快速终止定时器的任务执行线程时，应该调用 `Timer` 的 `cancel()`。

当定时器的任务执行线程意外终止时（例如，因为调用了它的 `stop()` 方法，你永远不要调用 `Thread` 的任何 `stop()` 方法，因为它们在本质上是不安全的），任何进一步在定时器上尝试调度定时器任务的尝试都会导致 `IllegalStateException`，就像调用了 `Timer` 的 `cancel()` 方法一样。

### 深入理解 TimerTask

定时器任务是抽象类 `TimerTask` 子类的实例，该类实现了 `Runnable` 接口。在子类 `TimerTask` 时，你需要重写 `run()` 方法以提供定时器任务的代码。

> 注意：定时器任务应该快速完成。当一个定时器任务完成时间过长时，它会“占用”定时器的任务执行线程，延迟后续定时器任务的执行，这可能导致这些任务在违规任务最终完成时“聚集”并连续快速执行。

你也可以在重写的定时器任务的 `run()` 方法内部调用以下方法：

- `cancel()`: 取消此定时器任务。当定时器任务已调度为单次执行且尚未运行，或者当未被调度时，它将永远不会运行。当定时器已调度为重复执行时，它将不再再次运行。（当发生此调用时定时器正在运行，定时器将运行到完成，但不再再次运行。）在重复定时器任务的 `run()` 中调用 `cancel()` 绝对保证该定时器任务不会再次运行；第二次及随后的调用没有影响。当此定时器任务被调度为单次执行且尚未运行，或者当此定时器任务被调度为重复执行时，该方法返回 `true`。当定时器任务被调度为单次执行且已经运行，或者当定时器任务已被取消时，它返回 `false`。（粗略来说，当该方法阻止了一个或多次调度执行的发生时，返回 `true`。）
- `long scheduledExecutionTime()`: 返回定时器任务最近一次实际执行的调度执行时间。（当在定时器执行过程中调用此方法时，返回值为当前正在进行的定时器任务执行的调度执行时间。）此方法通常从任务的 `run()` 中调用，以确定定时器任务的当前执行是否足够及时，以值得执行调定的活动。例如，你可以在 `run()` 的开头指定类似于 `if (System.currentTimeMillis()-scheduledExecutionTime() > MAX_TARDINESS) return;` 的代码，在定时器任务不及时时终止当前的定时器任务。此方法通常不与固定延迟执行的重复定时器任务结合使用，因为它们的调度执行时间允许随时间漂移，因此并不重要。`scheduledExecutionTime()` 返回此任务最近一次执行被调度发生的时间，格式为 `java.util.Date.getTime()` 返回的格式。当定时器尚未开始第一次执行时，返回值未定义。

## 练习题

以下练习旨在测试你对第4章内容的理解：

1. 定义线程组（thread group）。
2. 为什么你可能会使用线程组？
3. 为什么你应该避免使用线程组？
4. 为什么你应该注意线程组？
5. 定义线程本地变量（thread-local variable）。
6. 对错：当线程调用 `get()` 时，如果其存储槽中不存在项，该方法将调用 `initialValue()`。
7. 如何从父线程向子线程传递值？
8. 识别形成 Timer 框架的类。
9. 对：`Timer()` 创建一个新的定时器，其任务执行线程作为守护线程运行。
10. 定义固定延迟执行（fixed-delay execution）。
11. 调用哪些方法来调度固定延迟执行的任务？
12. 定义固定速率执行（fixed-rate execution）。
13. `Timer` 的 `cancel()` 方法与 `TimerTask` 的 `cancel()` 方法的区别是什么？
14. 创建一个来回移动的应用程序，使用 `Timer` 和 `TimerTask` 重复地让星号向前移动 20 步然后向后移动 20 步。星号通过 `out.print()` 输出。

# 第二部分

# 并发工具

## 第 5 章

## 并发工具与执行器

之前的四章重点关注了 Java 对线程的低级支持。本章将转向 Java 的高级线程支持，即并发工具（concurrency utilities）。可以将并发工具类比为使用高级编程语言编写应用程序，而将它的低级线程支持类比为使用汇编语言编写应用程序。在简要介绍这些工具之后，我将带你领览执行器（executors）。接下来的三章将涵盖各种并发工具的其他子集。

### 介绍并发工具

Java 的低级线程支持允许你创建多线程应用程序，与单线程程序相比，它们提供了更好的性能和响应能力。然而，这其中存在一些问题：

- 低级并发原语（如 `synchronized` 和 `wait()/notify()`）通常很难正确使用。不当使用这些原语会导致竞态条件、线程饥饿、死锁和其他危害，而这些问题难以检测和调试。
- 过度依赖 `synchronized` 原语可能导致性能问题，影响应用程序的可扩展性。对于像 Web 服务器这样的高线程应用程序来说，这是一个严重的问题。
- 开发者通常需要更高级的结构，如线程池和信号量。由于这些结构没有包含在 Java 的低级线程支持中，开发者被迫自己构建，而这是一项耗时且容易出错活动。

为了解决这些问题，Java 5 引入了并发工具，这是一个强大且可扩展的框架，包含了线程池和阻塞队列等高性能线程工具。该框架由以下包中的各种类型组成：

- `java.util.concurrent`：并发编程中经常使用的工具类型，例如执行器（executors）。
- `java.util.concurrent.atomic`：支持对单个变量进行无锁线程安全操作的工具类。
- `java.util.concurrent.locks`：在条件上进行锁定和等待的工具类型（允许线程挂起执行 [wait] 直到被其他线程通知某些状态现在可能为真的对象）。通过这些类型进行锁定和等待比通过 Java 基于监视器的同步和等待/通知机制性能更高、更灵活。

该框架还向 `java.lang.System` 类中引入了 `nanoTime()` 方法，它为 `Thread(new Runnable()).start();` 提供了一个纳秒级精度的时间源，用于进行相对时间测量。

并发工具可以分类为执行器（executors）、同步器（synchronizers）、锁定框架（locking framework）等。我将在下一节探讨执行器，并在后续章节中探讨其他类别。

### 探索执行器

Threads API 允许你通过 `new java.lang.Thread(new Runnable()).start();` 等表达式执行可运行任务。这些表达式将任务提交与任务的执行机制紧耦合（在当前线程运行、在新线程中运行，或从线程池[组]中随机选择的线程运行）。

> 任务是一个其类实现了 `java.lang.Runnable` 接口（可运行任务）或 `java.util.concurrent.Callable` 接口（可调用任务）的对象。我将在本章稍后介绍关于 `Callable` 的内容。

并发工具包含了执行器作为执行可运行任务的级线程表达式的高级替代。执行器是一个其类直接或间接实现 `java.util.concurrent.Executor` 接口的对象，它将任务提交与任务执行机制解耦。

**注意** 执行器框架使用接口来解耦任务提交与任务执行，这类似于集合框架（Collections Framework）使用核心接口将列表、集合、队列和映射与其实现解耦。解耦带来了灵活且易于维护的代码。

`Executor` 声明了一个单一的 `execute(Runnable runnable)` 方法，它在未来的某点执行名为 `runnable` 的任务。当 `runnable` 为 `null` 时，`execute()` 抛出 `java.lang.NullPointerException`；当无法执行 `runnable` 时抛出 `java.util.concurrent.RejectedExecutionException`。

**注意** 当执行器关闭且不想接受新任务时，可能会抛出 `RejectedExecutionException`。此外，当执行器没有足够的内存存储任务时，也会抛出此异常（可能执行器使用边界队列来存储任务，而队列已满——将在第 8 章讨论阻塞队列）。

以下示例显示了上述 `new Thread(new Runnable()).start();` 表达式 Executor 等形式：

```
Executor executor = ...; // 代表某些执行器的创建

executor.execute(new RunnableTask());
```



# 第 5 章 并发工具类与执行器

尽管 `Executor` 很容易使用，但该接口在各方面都有局限：

- `Executor` 专门关注 `Runnable`。由于 `Runnable` 的 `run()` 方法没有返回值，没有简单的方法让可运行任务向调用者返回结果。
- `Executor` 不提供跟踪正在执行的可运行任务进度的方法，也无法确定可运行任务何时完成执行。
- `Executor` 无法取消可运行任务集合。
- `Executor` 未提供让应用程序关闭执行器的方法（更不用说正确关闭执行器）。

这些局限性通过 `java.util.concurrent.ExecutorService` 接口得到了解决，它扩展了 `Executor`，其实现通常是线程池。表 5-1 描述了 `ExecutorService` 的方法。

### 表 5-1. ExecutorService 的方法

| 方法 | 说明 |
| --- | --- |
| `boolean awaitTermination(long timeout, TimeUnit unit)` | 阻塞（等待）直到在关闭请求后所有任务都完成、超时（以 unit 时间为测量）或当前线程被中断，以先发生者为准。当此执行器已终止时返回 `true`，在终止前返回 `false`。此方法在被中断时抛出 `java.lang.InterruptedException`。 |
| `<T> List<Future<T>> invokeAll(Collection<? extends Callable<T>> tasks)` | 执行 `tasks` 集合中的每个任务，并返回一个包含 `java.util.concurrent.Future` 实例 `java.util.List`。`Future` 实例（在本任务中稍后讨论）在所有任务完成（通过正常结束或抛出异常）时持有状态和结果。`Future` 列表的顺序与 `tasks` 迭代器返回的任务序列一致。此方法在等待时被中断时抛出 `InterruptedException`，未完成的任务将被取消；当集合中任何元素为 `null` 时抛出 `NullPointerException`；当任一任务无法调度执行时抛出 `RejectedExecutionException`。 |
| `<T> List<Future<T>> invokeAll(Collection<? extends Callable<T>> tasks, long timeout, TimeUnit unit)` | 执行 `tasks` 集合中的每个可调用任务，并返回一个 `Future` 实例列表，在所有任务完成（通过正常结束或抛出异常）或超时（以 unit 时间为测量）时持有状态和结果。未到期的任务将被取消。`Future` 列表的顺序与 `tasks` 迭代器返回的任务序列一致。此方法在等待时被中断时抛出 `InterruptedException`（未完成的任务将被取消）。当 `tasks`、其任一元素或 `unit` 为 `null` 时抛出 `NullPointerException`；当任一任务无法调度执行时抛出 `RejectedExecutionException`。 |
| `<T> T invokeAny(Collection<? extends Callable<T>> tasks)` | 执行给定的任务，如果有任何任务成功完成（换句话说，没有抛出异常），则返回任意一个成功完成的任务的结果。在正常返回或异常返回时，未完成的任务将被取消。此方法在等待期间被中断时抛出 `InterruptedException`；当任务或其任一元素为 `null` 时抛出 `NullPointerException`；当任务列表为空时抛出 `java.lang.IllegalArgumentException`；当没有任务成功完成时抛出 `java.util.concurrent.ExecutionException`；当没有任一个任务能无法被调度执行时，抛出 `RejectedException`。 |
| `<T> T invokeAny(Collection<? extends Callable<T>> tasks, long timeout, TimeUnit unit)` | 执行给定的任务，如果在超时（以时间单位衡量）发生之前有任何任务成功完成（未抛出异常），则返回任意一个成功完成的任务的结果——到期时未完成的任务将被取消。在正常返回或异常返回时，未完成的任务将被取消。此方法在等待期间被中断时抛出 `InterruptedException`；当任务、任一元素或 `unit` 为 `null` 时抛出 `NullPointerException`；当任务为空时抛出 `IllegalArgumentException`；当在任何任务成功完成之前超时时，抛出 `java.util.concurrent.TimeoutException`；当没有任务成功完成时抛出 `ExecutionException`；当没有任一个任务能无法被调度执行时，抛出 `RejectedException`。 |
| `boolean isShutdown()` | 当此执行器已关闭时，返回 `true`；否则返回 `false`。 |
| `boolean isTerminated()` | 当所有任务在关闭后已完成时，返回 `true`；否则返回 `false`。此方法在调用 `shutdown()` 或 `shutdownNow()` 之前永远不会返回 `true`。 |
| `void shutdown()` | 启动有序关闭，在其中之前提交的任务将执行执行，但不再接受新任务。在执行器关闭后调用此方法将产生任何影响。此方法不会等待之前提交的任务完成执行。在需要等待时请使用 `awaitTermination()`。 |
| `List<Runnable> shutdownNow()` | 尝试停止所有正在执行的任务，停止处理等待中的任务，并返回一个等待执行的任务列表。除了尽力尝试停止正在执行的任务外，没有其他保证。例如，典型的实现将通过 `Thread.interrupt()` 实现，因此任何未能响应的任务可能永远不会终止。 |
| `<T> Future<T> submit(Callable<T> task)` | 提交一个可调用的任务进行执行，并返回一个表示任务等待结果的 `Future` 实例。`Future` 实例的 `get()` 方法在任务成功完成后返回任务结果。当任务无法被调度执行时，抛出 `RejectedExecutionException`，当任务为 `null` 时抛出 `NullPointerException`。 |
| `Future<?> submit(Runnable task)` | 提交一个可运行的任务进行执行，并返回一个表示任务等待结果的 `Future` 实例。`Future` 实例的 `get()` 方法在任务成功完成后返回任务结果。当任务无法被调度执行时抛出 `RejectedExecutionException`，当任务为 `null` 时抛出 `NullPointerException`。 |
| `<T> Future<T> submit(Runnable task, T result)` | 提交一个可运行的任务进行执行，并返回一个 `Future` 实例，其 `get()` 方法在成功完成后返回 `result` 的值。当任务无法被调度执行时抛出 `RejectedExecutionException`，当任务为 `null` 时抛出 `NullPointerException`。 |

> **注 5-1** 指的是 `java.util.concurrent.TimeUnit`，这是一个表示不同粒度时间持续时间的枚举：天（`DAYS`）、小时（`HOURS`）、微秒（`MICROSECONDS`）、毫秒（`MILLISECONDS`）、秒（`SECONDS`）和纳秒（`NANOSECONDS`）。`TimeUnit` 声明了跨单位转换的方法（如 `toHours(long duration)`）以及在这些单位中执行计时和延迟操作（如 `sleep(long timeout)`）。

> **注 5-1** 还指的是可调用任务。与 `Runnable` 不同，`Runnable` 的 `run()` 方法不能返回值且不能抛出检查异常，而 `Callable<V>` 的 `call()` 方法可以返回值并可以抛出检查异常，因为它在声明时带有 `throws Exception` 子句。

最后，注 5-1 指的是 `Future` 接口，它表示异步计算的结果。该结果被称为 Future，是因为它在未来的某个时刻之前都是可用的。`Future` 的泛型类型为 `Future<V>`提供了取消任务、返回任务值以及确定任务是否完成的方法。表 5-2 描述了 `Future` 的方法。

### 表 5-2 Future 的方法

| 方法 | 描述 |
| --- | --- |
| `boolean cancel(boolean mayInterruptRunning)` | 尝试取消此任务的执行，并在任务取消时返回 `true`；否则返回 `false`（任务可能在调用 `cancel()` 之前已正常完成）。当任务已完成、已取消或其他其他原因无法取消时，取消失败。如果成功且此任务尚未启动，则任务将永远不会运行。如果任务已经启动，`mayInterruptRunning` 决定（`true`）或否（`false`）运行此任务的线程应该被中断以尝试停止任务。返回后，后续对 `isDone()` 的调用始终返回 `true`；当 `cancel()` 返回时，`isCancelled()` 始终返回 `true`。 |
| `V get()` | 等待任务完成并返回结果。当任务在调用此方法之前被取消时，抛出 `java.util.concurrent.CancellationException`；当任务抛出异常时抛出 `ExecutionException`；当当前线程在等待期间被中断时抛出 `InterruptedException`。 |
| `V get(long timeout, TimeUnit unit)` | 最多等待 `timeout`（由 `unit` 指定）单位任务完成并返回结果。当任务在调用此方法之前被取消时，抛出 `CancellationException`；当任务抛出异常时抛出 `ExecutionException`；当当前线程在等待期间被中断时抛出 `InterruptedException`；当在任何任务成功完成之前超时时，抛出 `TimeoutException`。 |
| `boolean isCancelled()` | 当任务在完成之前被取消时返回 `true`；否则返回 `false`。 |
| `boolean isDone()` | 当任务已完成时返回 `true`；否则返回 `false`。完成可能是由于正常终止、异常或取消。 |

假设你打算编写一个应用程序，其用户界面允许输入单词。用户输入单词后，应用程序会将该单词提交多个在线字典并获取每个字典的条目。随后向用户显示这些条目。

由于访问可能很慢，而且用户界面应该保持响应（可能你将“获取单词条目”任务加载到单独线程的执行器上）。以下示例使用 `ExecutorService`、`Callable` 和 `Future` 实现这一目标：

```java
ExecutorService executor = ...; // ... 代表执行器的创建

Future<String[]> taskFuture = 
executor.submit(new Callable<String[]>() {
    @Override
    public String[] call() {
        String[] entries = ...;
        // 访问在线字典
        // 使用搜索单词并填充
        // entries 条目。
        return entries;
    }
});
```

```java
// 执行某些操作。
String entries = taskFuture.get();
```

在以某种方式获取执行器后（稍后我们将学习方法），示例线程向执行器提交了一个可调用的任务。`submit()` 方法立即返回一个 `Future` 对象，用于控制任务执行并访问结果。

> **注意** `java.util.concurrent.ScheduledExecutorService` 接口扩展了 `ExecutorService`，描述允许调度任务在给定延迟后一次性或定期运行的执行器。

虽然你可以创建自己的 `Executor`、`ExecutorService` 和 `ScheduledExecutorService` 实现（例如类 `DirectExecutor implements Executor { @Override public void execute(Runnable r) { r.run(); } }` — 直接在调用线程上运行执行器），但有一个更简单的替代方案：`java.util.concurrent.Executors`。

> **提示** 如果你打算创建自己的 `ExecutorService` 实现，你会发现通过与 `java.util.concurrent.AbstractExecutorService` 和 `java.util.concurrent.FutureTask` 类工作将非常有帮助。

`Executors` 工具类声明了几个类方法，这些方法可以返回各种 `ExecutorService` 和 `ScheduledExecutorService` 实现（以及其他类型的实例）的实例。该类的静态方法完成了以下任务：

- 创建并返回一个配置了常用配置设置的 `ExecutorService` 实例。
- 创建并返回一个配置了常用配置设置的 `ScheduledExecutorService` 实例。
- 创建并返回一个“被封装的” `ExecutorService` 实例，该实例通过使特定于实现的方法不可用来禁用执行器服务的重新配置。
- 创建并返回一个 `java.util.concurrent.ThreadFactory` 实例（即实现 `ThreadFactory` 接口的类的实例），用于创建新的 `Thread` 对象。
- 将其他闭包形式转换为 `Callable` 实例，以便其在需要 `Callable` 参数的执行方法中使用（例如 `ExecutorService` 的 `submit(Callable)` 方法）。维基百科 http://en.wikipedia.org/wiki/Closure_(computer_science) 上的“Closure”（闭包）条目介绍了闭包这一主题。

例如，静态方法 `ExecutorService newFixedThreadPool(int nThreads)` 创建了一个使用固定数量线程并在共享无界队列上运行的池。最多有 `nThreads` 个线程正在处理任务。如果在所有线程都处于活动时提交了额外任务，这些任务将进入队列等待可用线程。

如果任何线程在执行器关闭之前因执行期间失败而终止，当需要执行后续任务时，一个新线程将取代它。池中的线程一直存在到执行器被显式关闭。当你向 `nThreads` 传递零或负值时，此方法会抛出 `IllegalArgumentException`。

> **注意** 线程池用于消除为每个提交的任务创建新线程的开销。线程的创建并不是廉价的，创建许多线程可能会严重影响应用的性能。

你通常会在文件和网络输入/输出上下文中使用 executors、runnables、callables 和 futures。执行耗时计算是你可以使用这些类型的另一个场景。例如，列表 5-1 在欧拉数 e (2.71828...) 的计算上下文中使用了执行器、callable 和 future。

### 列表 5-1. 计算欧拉数 e

```java
import java.math.BigDecimal;
import java.math.MathContext;
import java.math.RoundingMode;
import java.util.concurrent.Callable;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

public class CalculateE {
    final static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(1);
        Callable<BigDecimal> callable = new Callable<BigDecimal>() {
            @Override
            public BigDecimal call() {
                MathContext mc = new MathContext(100, RoundingMode.HALF_UP);
                BigDecimal result = BigDecimal.ZERO;
                for (int i = 0; i <= LASTITER; i++) {
                    BigDecimal factorial = factorial(new BigDecimal(i));
                    BigDecimal res = BigDecimal.ONE.divide(factorial, mc);
                    result = result.add(res);
                }
                return result;
            }
        };
    }
}
```

```java
public BigDecimal factorial(BigDecimal n) {
```



```java
if (n.equals(BigDecimal.ZERO))
    return BigDecimal.ONE;
else
    return n.multiply(factorial(n.subtract(BigDecimal.ONE)));
}

Future<BigDecimal> taskFuture = executor.submit(callable);

try {
    while (!taskFuture.isDone()) {
        System.out.println("waiting");
    }
    System.out.println(taskFuture.get());
} catch (ExecutionException ee) {
    System.out.println("task threw an exception");
    System.out.println(ee);
} catch (InterruptedException ie) {
    System.out.println("interrupted while waiting");
}

executor.shutdownNow();
```

执行 `main()` 的默认主线程首先通过 `Executors` 的 `newFixedThreadPool()` 方法获取一个执行器。然后它实例化了一个实现 `Callable` 接口的匿名类，并将此任务提交给执行器，接收一个 `Future` 作为响应。

提交任务后，线程通常会做一些其他工作，直到它需要任务的结果。我通过让主线程反复输出等待消息，直到 `Future` 的 `isDone()` 方法返回 `true` 来模拟这一点。（在实际应用程序中，我会避免这样做。）此时，主线程调用执行器的 `get()` 方法获取结果，然后将其输出。随后，主线程关闭了执行器。

> **警告** 在执行器完成后关闭它是非常重要的；否则应用程序可能不会结束。之前的执行器通过调用 `shutdownNow()` 完成了此任务。（你也可以使用 `shutdown()` 方法。）

`callable` 的 `call()` 方法通过评估数学幂级数 `e = 1 / 0! + 1 / 1! + 1 / 2! + ...` 来计算 `e`。该级数可以通过累加 `1 / n!` 来求值，其中 `n` 的范围从 0 到无穷大（代表阶乘）。

`call()` 实例化 `java.math.MathContext` 来封装精度（位数）和舍入模式。我选择 100 作为 `e` 的精度的上限，并选择 `HALF_UP` 作为舍入模式。

- 通过增加精度以及 `LASTITER` 的值，将级数转换为更精确的 `e` 的近似值。

`call()` 下初始化 `BigDecimal` 变量 `result` 为 `BigDecimal.ZERO`。然后进入一个循环，计算阶乘，将 `BigDecimal.ONE` 除以阶乘，并将结果加到 `result`。

`divide()` 将 `MathContext` 实例作为第二个参数提供舍入信息。（如果指定的精度导致了无法精确表示的小数，例如 `0.333333...`，将抛出 `java.ArithmeticException` 来通知调用者结果无法精确表示。）

按如下方式编译列表 5-1：

```bash
javac CalculateE.java
```

```bash
java CalculateE
```

你应该观察到类似于下面的输出（可能会看到更多消息）：

```
waiting
waiting
waiting
waiting
2.71821828459045707516047795848605061178979635210326989007350
```

以下练习旨在测试你对第 5 章内容的理解：

1. 什么是并发工具？
2. 并发工具类型存储在哪些包中？
3. 定义任务。
4. 定义执行器。
5. 识别 `Executor` 接口的局限性。
6. 如何克服 `Executor` 的局限性？
7. `Runnable` 的 `run()` 方法和 `Callable` 的 `call()` 方法之间有什么区别？
8. 对或否：你可以在 `Runnable` 的 `run()` 方法中抛出检查异常和运行时异常，但在 `Callable` 的 `call()` 方法中只能抛出运行时异常。
9. 定义 future。
10. 描述 `Executors` 类的 `newFixedThreadPool()` 方法。
11. 重构以下 `CountingThreads` 应用以使用 `Executors` 和 `ExecutorService`：

```java
public class CountingThreads
{
    public static void main(String[] args)
    {
        Runnable r = new Runnable()
        {
            @Override
            public void run()
            {
                String name = Thread.currentThread().getName();
                int count = 0;
                while (true)
                    System.out.println(name + ": " + count++);
            }
        };

        Thread thdA = new Thread(r);
        Thread thdB = new Thread(r);
        thdA.start();
        thdB.start();
    }
}
```

- 当你执行上一个练习中的 `CountingThreads` 时，你会看到通过如 `pool-1-thread-1` 等名称识别线程的输出。修改 `CountingThreads` 以便观察到名称 A 和 B。提示：你需要使用 `ThreadFactory`。

## 总结

Java 的低级线程能力允许你创建多线程应用程序，与其单线程程序相比，提供了更好的性能和响应速度。然而，影响应用程序扩展性的性能问题和其他问题导致 Java 5 引入了并发工具。

并发工具将各种类型组织成三个包：`java.util.concurrent`、`java.util.concurrent.atomic` 和 `java.util.concurrent.locks`。执行器、线程池、并发哈希表和其他高级并发构造的基本类型存储在 `java.util.concurrent` 中；支持在单个变量上进行无锁线程安全编程的类存储在 `java.util.concurrent.atomic` 中；用于锁和等待条件的类型存储在 `java.util.concurrent.locks` 中。

执行器将任务提交与任务执行机制解耦，由 `Executor`、`ExecutorService` 和 `ScheduledExecutorService` 接口描述。你通过调用 `Executors` 类的一个工具方法获取执行器。执行器与 `callables` 和 `futures` 相关联。

第 6 章介绍了同步器。

## 第 6 章

## 同步器

Java 提供了 `synchronized` 关键字来同步线程对关键区域的访问。由于很难正确编写基于 `synchronized` 的高级同步器（促进常见同步形式的类）的代码，因此这些同步器被包含在并发工具中。在本章中，我将向你介绍计数门、循环屏障、交换器、信号量和相位器同步器。

## 计数门 (Countdown Latches)

计数门使一个或多个线程等待，直到另一个线程打开大门，此时这些线程就可以继续。它由一个计数和操作（“导致线程等待直到计数减零”和“递减计数”）组成。

`java.util.concurrent.CountDownLatch` 实现了计数门同步器。你通过调用该类的 `CountDownLatch(int count)` 构造函数将 `CountDownLatch` 实例初始化为特定的计数，当传递给 `count` 的值为负数时，会抛出 `java.lang.IllegalArgumentException`。`CountDownLatch` 还提供了以下方法：

- `void await()`：强制调用线程等待直到计数减零，除非线程被中断，在这种情况下会抛出 `java.lang.InterruptedException`。当计数为零时，此方法立即返回。
- `boolean await(long timeout, TimeUnit unit)`：强制调用线程等待直到计数减零或指定的超时值（以时间单位为单位）过期，或者线程被中断，在这种情况下会抛出 `InterruptedException`。当计数为零时，此方法立即返回；当等待时间结束时返回 `false`。
- `void countDown()`：递减计数，当计数为零时释放所有等待的线程。当调用此方法时计数已为零，则什么都不会发生。
- `long getCount()`：返回当前计数。此方法对于测试和调试很有用。
- `toString()`：返回一个识别此门及其状态的字符串。状态（在括号中）包含字符串字面量 `"Count ="` 后跟当前计数。

你将使用计数门来确保线程在大约相同的时间启动。例如，查看代码清单 6-1。

### 代码清单 6-1. 使用计数门触发协调启动

```java
import java.util.concurrent.CountDownLatch;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class CountDownLatchDemo
{
    final static int THREADS = 3;

    public static void main(String[] args)
    {
        final CountDownLatch startSignal = new CountDownLatch(1);
        final CountDownLatch doneSignal = new CountDownLatch(THREADS);

        Runnable r = new Runnable() {
            @Override
            public void run() {
                try {
                    report("entered run()");
                    startSignal.await(); // 等到被告知 ...
                    report("doing work"); // ... 继续
                    Thread.sleep((int) (Math.random() * 1000));
                    doneSignal.countDown(); // 减少计数
                } catch (InterruptedException ie) {
                    System.err.println(ie);
                }
            }
        };

        void report(String s) {
            System.out.println(System.currentTimeMillis() +
                ": " + Thread.currentThread().getName() +
                ": " + s);
        }

        ExecutorService executor = Executors.newFixedThreadPool(THREADS);

        for (int i = 0; i < THREADS; i++) {
            executor.execute(r);
        }

        try {
            System.out.println("main thread doing something");
            Thread.sleep(1000); // 睡眠 1 秒
            startSignal.countDown(); // 让所有线程继续
            System.out.println("main thread doing something else");
            doneSignal.await(); // 等待所有线程完成
            executor.shutdownNow();
        } catch (InterruptedException ie) {
            System.err.println(ie);
        }
    }
}
```

计数门允许一个或多个线程等待其他线程中执行的一组操作完成。门用一个计数初始化，`await` 方法会阻塞直到由于多次调用 `countDown()` 导致计数减零。在上面的示例中，使用了两个门：`startSignal` 确保所有工作线程同时开始，`doneSignal` 确保主线程在关闭执行器之前等待所有工作完成。

## 循环屏障 (Cyclic Barriers)

循环屏障让一组线程等待彼此到达共同的屏障点。循环屏障对于涉及固定大小线程同步的应用程序非常有用，因为在等待线程释放后它可以重用。

`java.util.concurrent.CyclicBarrier` 类实现了循环屏障同步器。你通过调用该类的 `CyclicBarrier(int parties)` 构造函数将 `CyclicBarrier` 实例初始化为特定数量的参与者（为了共同目标的线程）。当传递给 `parties` 的值小于 1 时，此构造函数会抛出 `IllegalArgumentException`。

或者，你可以调用 `CyclicBarrier(int parties, Runnable barrierAction)` 以及在屏障触发时执行的 `barrierAction`。也就是说，当 `parties - 1` 个线程在等待且有一个额外的线程到达时，该到达的线程会执行 `barrierAction`，然后所有线程继续。这个可运行任务对于在任何线程继续之前更新共享状态非常有用。当传递给 `parties` 的值小于 1 时，此构造函数会抛出 `IllegalArgumentException`。（前一种构造函数会调用此构造函数并向 `barrierAction` 传递 `null`——屏障触发时不会执行任何可运行任务）。

`CyclicBarrier` 还提供了以下方法：

- `int await()`：强制调用线程等待，直到所有参与者在该循环屏障上调用了 `await()`。当调用线程或另一个等待线程被中断、另一个等待线程在等待时超时，或者另一个线程在该循环屏障上调用 `reset()` 时，调用线程也将停止等待。如果调用线程在进入时已处于中断状态或在等待期间被中断，此方法将抛出 `InterruptedException` 并清除调用线程的中断状态。当在任何线程等待时通过 `reset()` 重置屏障时，此方法将抛出 `java.util.concurrent.BrokenBarrierException`；或者当调用 `await()` 且有任何线程等待时，屏障损坏。如果任何线程在等待期间被中断，所有其他线程都会抛出 `BrokenBarrierException` 且屏障进入损坏状态。如果调用线程是最后一个到达的线程，且在构造函数中提供了非空的 `barrierAction`，则由调用线程执行该运行器，允许其他线程继续。此方法返回调用线程的到达索引，其中 `getParties()-1` 表示第一个到达的线程，0 表示最后一个到达的线程。
- `await(long timeout, TimeUnit unit)`：此方法等于前一个方法，允许你指定调用线程等待的时间。当线程等待的超时到达时，此方法将抛出 `java.util.concurrent.TimeoutException`。
- `getNumberWaiting()`：返回当前在屏障处等待的参与者数量。此方法对于调试和配合断言非常有用。
- `getParties()`：返回触发屏障所需的参与者数量。
- `boolean isBroken()`：如果自循环屏障构建以来或上次重置以来，有一个或多个参与者由于中断或超时跳出屏障，或者屏障动作因异常失败，则返回 `true`；否则返回 `false`。
- `void reset()`：将屏障重置为初始状态。如果当前有参与者在屏障处等待，它们将带有 `BrokenBarrierException` 返回。注意，执行由于其他原因导致的损坏重置可能非常复杂；线程需要通过其他方式重新同步并选择一种方式来执行剩余操作。因此，为后续使用创建一个新的屏障可能更好。

`CyclicBarrier` 在并行分解场景中非常有用，在这种场景下，一个耗时任务被分为若干子任务，每个子任务的结果被合并到任务的整体结果。`CyclicBarrier` 的 Javadoc 展示了在列表 6-2 中完成的示例代码。

### 列表 6-2. 使用 CyclicBarrier 将任务分解为子任务

```java
import java.util.concurrent.BrokenBarrierException;
```



import java.util.concurrent.CyclicBarrier;

public class CyclicBarrierDemo {

    public static void main(String[] args) {

        float[][] matrix = new float[3][3];

        int counter = 0;

        for (int row = 0; row < matrix.length; row++) {

            for (int col = 0; col < matrix[0].length; col++) {

                matrix[row][col] = counter++;

            }

        }

        dump(matrix);

        System.out.println();

        Solver solver = new Solver(matrix);

        System.out.println();

        dump(matrix);

    }

    static void dump(float[][] matrix) {

        for (int row = 0; row < matrix.length; row++) {

            for (int col = 0; col < matrix[0].length; col++) {

                System.out.print(matrix[row][col] + " ");

            }

            System.out.println();

        }

    }

}

class Solver {

    final int N;

    final float[][] data;

    final CyclicBarrier barrier;

    class Worker implements Runnable {

        int myRow;

        boolean done = false;

        Worker(int row) {

            myRow = row;

        }

        boolean done() {

            return done;

        }

        void processRow(int myRow) {

            System.out.println("Processing row: " + myRow);

            for (int i = 0; i < N; i++)

                data[myRow][i] *= 10;

            done = true;

        }

        @Override

        public void run() {

            while (!done()) {

                processRow(myRow);

                try {

                    barrier.await();

                } catch (InterruptedException ie) {

                    return;

                } catch (BrokenBarrierException bbe) {

                    return;

                }

            }

        }

    }

    public Solver(float[][] matrix) {

        data = matrix;

        N = matrix.length;

        barrier = new CyclicBarrier(N,

            new Runnable() {

                @Override

                public void run() {

                    mergeRows();

                }

            }));

        for (int i = 0; i < N; ++i)

            new Thread(new Worker(i)).start();

        waitUntilDone();

    }

    void mergeRows() {

        System.out.println("merging");

        synchronized ("abc") {

            "abc".notify();

        }

    }

    void waitUntilDone() {

        synchronized ("abc") {

            try {

                System.out.println("main thread waiting");

                "abc".wait();

                System.out.println("main thread notified");

            } catch (InterruptedException ie) {

                // handle

            }

        }

    }

}

```

```java

while (true) {

    addBuffer(currentBuffer);

    if (currentBuffer.isFull()) {

        System.out.println("filling thread wants to exchange");

        currentBuffer = exchanger.exchange(currentBuffer);

        System.out.println("filling thread receives exchange");

    }

}

catch (InterruptedException ie) {

    System.out.println("filling thread interrupted");

}

```

```java

void addBuffer(DataBuffer buffer) {

    String item = "NI" + count++;

    System.out.println("Adding: " + item);

    buffer.add(item);

}

```

```java

class EmptyingLoop implements Runnable {

    @Override

    public void run() {

        DataBuffer currentBuffer = initialFullBuffer;

        try {

            while (true) {

                takeFromBuffer(currentBuffer);

                if (currentBuffer.isEmpty()) {

                    System.out.println("emptying thread wants to " + "exchange");

                    currentBuffer = exchanger.exchange(currentBuffer);

                    System.out.println("emptying thread receives " + "exchange");

                }

            }

        } catch (InterruptedException ie) {

            System.out.println("emptying thread interrupted");

        }

    }

    void takeFromBuffer(DataBuffer buffer) {

        System.out.println("taking: " + buffer.remove());

    }

}

```

```java

new Thread(new EmptyingLoop()).start();

new Thread(new FillingLoop()).start();

class DataBuffer {

    private final static int MAXITEMS = 10;

    private final List<String> items = new ArrayList<>();

    DataBuffer() {

    }

    DataBuffer(String prefix) {

        for (int i = 0; i < MAXITEMS; i++) {

            String item = prefix + i;

            System.out.printf("Adding %s\n", item);

            items.add(item);

        }

    }

    synchronized void add(String s) {

        if (!isFull()) {

            items.add(s);

        }

    }

    synchronized boolean isEmpty() {

        return items.size() == 0;

    }

    synchronized boolean isFull() {

        return items.size() == MAXITEMS;

    }

    synchronized String remove() {

        if (!isEmpty())

            return items.remove(0);

        return null;

    }

}

```

# 第6章 同步器

## 信号量

信号量维护一组许可，用于限制访问受限资源的线程数量。尝试获取许可的线程在没有许可可用时会处于阻塞状态，直到其他线程释放一个许可。

> 当前值可以增加超过 1 的信号量称为计数信号量，而当前值只能为 0 或 1 的信号量称为二进制信号量或互斥锁（`mutexes`）。在任何情况下，当前值都不为负数。

`java.util.concurrent.Semaphore` 类实现了这种同步器，并将信号量概念化为维护一组许可的对象。你通过调用 `Semaphore(int permits)` 构造函数来初始化信号量，其中 `permits` 指定了可用许可的数量。生成的信号量的公平性策略设置为 `false`（不公平）。或者，你也可以调用 `Semaphore(int permits, boolean fair)` 构造函数将信号量的公平性设置设置为 `true`（公平）。

### 信号量与公平性

当公平性设置为 `false` 时，`Semaphore` 不保证线程获取许可的顺序。特别是，它允许“插队”（`barging`）——即，调用 `acquire()` 的线程可能会比已经在等待的线程先分配许可，只要新线程将自己置于那里。

`Semaphore` 还提供了以下方法：

- `void acquire(int permits)`: 从此信号量获取许可，阻塞直到许可可用或调用线程被中断。被中断时抛出 `InterruptedException`；当 `permits` 小于 0 时抛出 `IllegalArgumentException`。
- `void acquireInterruptibly()`: 获取许可，阻塞直到许可可用。
- `void acquireInterruptibly(int permits)`: 获取许可，阻塞直到许可可用。当 `permits` 小于 0 时抛出 `IllegalArgumentException`。
- `int availablePermits()`: 返回当前可用许可的数量。此方法用于调试和测试。
- `int drainPermits()`: 获取并返回所有立即可用的许可。
- `int getQueueLength()`: 返回等待许可的线程数的估计值。由于在方法遍历数据结构时线程数量可能会变化，返回的值仅为估计值。此方法用于监控系统状态，而不是同步控制。
- `boolean hasQueuedThreads()`: 查询是否有线程正在等待许可。由于取消可能随时发生，`true` 值并不保证任何线程都能获取许可。此方法主要用于监控系统状态。当存在其他线程时返回 `true`。
- `boolean isFair()`: 返回公平性设置（公平为 `true`，不公平为 `false`）。
- `void release()`: 释放一个许可并将其返回信号量。许可数增加一。如果有线程尝试获取许可，将选择一个线程并赋予刚刚释放的许可。该线程将被重新启用以进行调度。
- `void release(int permits)`: 释放许可并返回信号量。可用许可数增加 `permits`。如果有线程尝试获取许可，将选择一个并赋予刚刚释放的许可；否则，可用许可数满足该线程请求，该线程将被重新启用以进行调度；否则，线程将等待直到许可可用。如果在满足线程请求后仍有许可，当 `permits` 小于 0 时抛出 `IllegalArgumentException`。
- `String toString()`: 返回标识此信号量及其状态的字符串。状态位于括号内，包含字面量 "Permits =" 以及许可数量。
- `boolean tryAcquire()`: 从此信号量获取许可，但仅在调用时许可可用的情况下。获取许可时返回 `true`，否则立即返回 `false`。
- `boolean tryAcquire(int permits)`: 从此信号量获取许可，但仅在调用时许可可用时进行。获取许可时返回 `true`，否则立即返回 `false`。当 `permits` 小于 0 时抛出 `IllegalArgumentException`。
- `boolean tryAcquire(int permits, long timeout, TimeUnit unit)`: 与之前的方法类似，但当许可不可用时，调用线程会等待。等待在许可可用、超时或调用线程被中断时结束，在中断的情况下，会抛出 `InterruptedException`。
- `boolean tryAcquire(long timeout, TimeUnit unit)`: 类似于 `tryAcquire(int permits)`，但调用线程会等待直到许可可用。等待在许可可用、超时或调用线程被中断时结束，在中断的情况下，会抛出 `InterruptedException`。

## 列表 6–4。 使用计数信号量控制线程池的访问



```java
import java.util.concurrent.Executors;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Semaphore;

public class SemaphoreDemo {
    public static void main(String[] args) {
        final Pool pool = new Pool();
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String name = Thread.currentThread().getName();
                try {
                    while (true) {
                        String item;
                        System.out.println(name + " acquiring " + (item = pool.getItem()));
                        Thread.sleep(200 + (int)(Math.random() * 100));
                        System.out.println(name + " putting back " + item);
                        pool.putItem(item);
                    }
                } catch (InterruptedException ie) {
                    System.out.println(name + "interrupted");
                }
            }
        };
        ExecutorService[] executors =
            new ExecutorService[Pool.MAX_AVAILABLE + 1];
        for (int i = 0; i < executors.length; i++) {
            executors[i] = Executors.newSingleThreadExecutor();
            executors[i].execute(r);
        }
    }
}
```

```java
final class Pool {
    public static final int MAX_AVAILABLE = 10;

    private final Semaphore available = new Semaphore(MAX_AVAILABLE, true);

    private final String[] items;

    private final boolean[] used = new boolean[MAX_AVAILABLE];

    Pool() {
        items = new String[MAX_AVAILABLE];
        for (int i = 0; i < items.length; i++)
            items[i] = "I" + i;
    }

    String getItem() throws InterruptedException {
        available.acquire();
        return getNextAvailableItem();
    }

    void putItem(String item) {
        if (markAsUnused(item))
            available.release();
    }

    private synchronized String getNextAvailableItem() {
        for (int i = 0; i < MAX_AVAILABLE; ++i) {
            if (!used[i]) {
                used[i] = true;
                return items[i];
            }
        }
        return null; // not reached
    }

    private synchronized boolean markAsUnused(String item) {
        for (int i = 0; i < MAX_AVAILABLE; ++i) {
            if (item == items[i]) {
                if (used[i]) {
                    used[i] = false;
                    return true;
                } else {
                    return false;
                }
            }
        }
        return false;
    }
}
```

清单 6-4 的默认 `main()` 方法创建了一个资源池、一个反复获取和归还资源的 `Runnable` 以及一个执行器数组。每个执行器都被告知执行该运行时任务。

`Pool` 的 `getItem()` 和 `putItem(String item)` 方法获取并返回基于字符串的资源。在 `getItem()` 中获取项目之前，调用线程必须通过 `available.acquire()` 获取许可。在 `putItem()` 归还项目后，会通过 `available.release()` 释放许可。在 `getItem()` 中获取项目之前，调用线程必须通过 `available.acquire()` 获取许可。当线程完成时，调用 `putItem(String)` 将项目返回到池并释放许可。在 `getItem()` 中获取项目之前，通过 `synchronized` 保证了池的一致性。

编译清单 6-4：

```
javac SemaphoreDemo.java
```

运行生成的程序：

```
java SemaphoreDemo
```

你应该观察到类似下面的输出（顺序可能有所不同）：

- thread-1 acquiring I0
- thread-2 acquiring I1
- thread-3 acquiring I2
- thread-4 acquiring I3
- thread-5 acquiring I4
- thread-6 acquiring I5
- thread-7 acquiring I6
- thread-8 acquiring I7
- thread-9 acquiring I8
- thread-10 acquiring I9
- thread-1 putting back I0
- thread-2 putting back I1
- thread-3 putting back I2
- thread-4 putting back I3
- thread-5 putting back I4
- thread-6 putting back I5
- thread-7 putting back I6
- thread-8 putting back I7
- thread-9 putting back I8
- thread-10 putting back I9
- thread-1 interrupted
- thread-2 interrupted
- thread-3 interrupted
- thread-4 interrupted
- thread-5 interrupted
- thread-6 interrupted
- thread-7 interrupted
- thread-8 interrupted
- thread-9 interrupted
- thread-10 interrupted

## 第 6 章 同步器

### Phaser（同步器）

`Phaser` 是一种更灵活的屏障。与 `CyclicBarrier` 类似，它可以协调任意数量的线程。`java.util.concurrent.Phaser` 类在 javadoc 中有详细描述，这里指出几个构造函数和方法：

- `Phaser(int threads)` 构造函数创建一个初始阶段为 0 的 phaser。
- `register()` 方法在任何时间向 phaser 添加新线程。
- `arriveAndAwaitAdvance()` 方法：到达并等待其他线程到达，它返回阶段数。
- `arriveAndDeregister()` 方法：到达此 phaser 并从中注销。

阶段（phase）是 phaser 当前的状态。与协调固定数量线程的 `CyclicBarrier` 不同，`Phaser` 可以协调变量数量的线程。当最后一个线程到达时，阶段会推进到下一个。

**清单 6-5。** 使用 Phaser 控制针对变量数量的一次性操作

```java
import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.Executors;
import java.util.concurrent.Phaser;

public class PhaserDemo {
    public static void main(String[] args) {
        List<Runnable> tasks = new ArrayList<>();
        tasks.add(() -> System.out.printf("%s is running at %d%n",
            Thread.currentThread().getName(),
            System.currentTimeMillis()));
        runTasks(tasks);
    }

    static void runTasks(List<Runnable> tasks) {
        final Phaser ph = new Phaser(1); // "1" (注册自己)
        // 创建并启动线程
        for (final Runnable task : tasks) {
            ph.register();
            Runnable r = () -> {
                try {
                    Thread.sleep(50 + (int) (Math.random() * 300));
                } catch (InterruptedException ie) {
                    System.out.println("interrupted thread");
                }
                task.run();
            };
            ph.arriveAndAwaitAdvance(); // 等待...
            // 创建
            // 所有任务
            Executors.newSingleThreadExecutor().execute(r);
        }
        // 允许线程启动并注销自己
        ph.arriveAndDeregister();
    }
}
```

你应该观察到输出类似于以下（且应用程序不应结束——按 Ctrl+C 或等效按键结束应用程序）：

```
pool-1-thread-1 running at 1445806012709
pool-2-thread-1 running at 1445806012712
```

正如你对倒计时计数器（countdown latch）行为的预期，两个线程都在同一时间开始运行（由于 `Thread.sleep()` 的存在，线程可能会被延迟高达 349 毫秒）。

注释掉 `ph.arriveAndAwaitAdvance();` // 等待……并且你应该观察到线程在完全不同的时间启动，如下所示：

```
pool-2-thread-1 running at 1445806212870
pool-1-thread-1 running at 1445806213013
```

## 练习题

以下练习旨在测试你对第 6 章内容的理解：

1. 定义什么是同步器。
2. 描述倒计时计数器（countdown latch）的行为。
3. 当调用 `CountDownLatch` 的 `void countDown()` 方法且计数达到零时，会发生什么？
4. 描述循环屏障（cyclic barrier）的行为。
5. 对错：当 `CyclicBarrier` 的 `int await()` 方法在任何线程等待时重置屏障或在调用 `await()` 时屏障损坏时，返回 -1。
6. 描述交换器（exchanger）的行为。
7. `Exchanger` 的 `V exchange(V x)` 方法实现了什么？
8. 描述信号量（semaphore）的行为。
9. 识别两种类型的信号量。
10. 描述注册器（phaser）的行为。
11. `Phaser` 的 `register()` 方法返回什么？
12. 清单 3-2（在第 3 章）展示了一个增强的 PC 应用程序。重创建此应用程序，由 `Semaphore` 类处理同步。

## 总结

Java 提供了 `synchronized` 关键字来同步线程对临界区域的访问，因为很难正确编写基于 `synchronized` 的同步代码。高级同步器被包含在并发工具类中。

倒计时计数器（latch）导致一个或多个线程在“大门”处等待，直到另一个线程打开这扇门，此时这些线程就可以继续。它由一个计数以及“导致线程等待直到计数减零”和“递减计数”的操作组成。

循环屏障（cyclic barrier）允许一组线程等待彼此到达共同的屏障点。该同步器适用于涉及固定大小线程组的应用，这些线程偶尔需要相互等待。它是循环的，因为在等待的线程被释放后，它可以被重用。

交换器（exchanger）提供了一个同步点，线程可以在此处交换对象。每个线程在进入交换器的 `exchange()` 方法时提供某个对象，与一个伙伴线程匹配，并在返回时接收其伙伴的对象。

信号量（semaphore）维护一组许可，用以限制访问有限资源的线程数量。尝试获取许可的线程在没有可用许可时会被阻塞，直到其他某个线程释放许可。

`Phaser`（注册器）是一个更灵活的循环屏障。像循环屏障一样，`Phaser` 允许一组线程在屏障上等待；这些线程在最后一个线程到达后继续。`Phaser` 还提供了等同于屏障动作（barrier action）的功能。与协调固定数量线程的循环屏障不同，`Phaser` 可以协调数量数量的线程，线程可以随时注册。为了实现这一功能，`Phaser` 使用阶段（phases）和阶段数（phase numbers）。

第 7 章介绍了锁框架。

# 第 7 章 锁框架

`java.util.concurrent.locks` 包提供了一个由接口和类组成的框架，用于锁定和等待条件，这种方式与对象基于内置锁的同步以及 `java.lang.Object` 的 `wait/notification` 机制有所不同。并发工具类包含了锁框架，它通过提供锁轮询（lock polling）、超时等待等改进了内置同步和等待/通知机制。

## 同步化与低级锁

Java 支持同步，以便线程可以安全地更新共享变量，并确保线程的更新对其他线程可见。我们通过在方法或代码块上标记 `synchronized` 关键字来在代码中利用同步。这些代码序列被称为临界区域（critical sections）。Java 虚拟机（JVM）通过监视器（monitors）和 `monitorexit` JVM 指令支持同步。

每个 Java 对象都关联有一个监视器，这是一种互斥结构（允许只有一个线程在临界区域内执行），它可以防止多个线程并发执行临界区域。在线程进入临界区域之前，需要锁定监视器。如果监视器已被锁定，线程将阻塞，直到监视器解锁（由另一个线程离开临界区域）。

在多核/多处理器环境中，当线程锁定监视器时，存储在主内存中的共享变量会被读取到存储在线程工作内存（称为本地内存或缓存内存）中的变量副本中。此操作确保线程将使用这些变量的最新值而不是旧值，这被称为可见性（visibility）。线程继续使用其共享变量的副本进行工作。当线程离开临界区域并解锁监视器时，其共享变量副本中的值会被写回主内存，使得下一个进入临界区域的线程能够访问这些变量的最新值。（`volatile` 关键字仅解决可见性问题。）

锁框架包含了常用的 `Lock`、`ReentrantLock`、`Condition`、`ReadWriteLock` 和 `ReentrantReadWriteLock` 类型，我将在本章中探讨它们。我还会简要介绍 Java 8 引入的 `StampedLock` 类。

### Lock

`Lock` 接口提供了比通过监视器获取更具表达力的锁定操作。例如，当锁不可用时你可以立即退出获取尝试。该接口提供了以下方法：



# 第 7 章 锁框架

## Lock 接口方法

- `void lock()`：获取锁。当锁不可用时，调用线程被强制等待直到可用。

- `void lockInterruptibly()`：获取锁，除非调用线程被中断。当锁不可用时，调用线程被强制等待直到可用或线程被中断，这会导致该方法抛出 `java.lang.InterruptedException`。

- `Condition newCondition()`：返回一个绑定到此 `Lock` 实例的新 `Condition` 实例。当 `Lock` 类不支持时，该方法会抛出 `java.lang.UnsupportedOperationException`。

- `boolean tryLock()`：在调用此方法时可用时获取锁。获取锁时返回 `true`，未获取锁时返回 `false`。

- `boolean tryLock(long time, TimeUnit unit)`：在等待时间内（以 `java.util.concurrent.TimeUnit` 单位，如秒、毫秒等测量）且调用线程未被中断时可用获取锁。当锁不可用时，调用线程被强制等待直到在等待时间内可用或被中断，这会导致该方法返回 `true` 或 `false`。

- `void unlock()`：释放锁。

## 锁的获取与释放

获取的锁必须释放。在 `synchronized` 块和与对象相关的隐式监视器上下文中，锁的获取和释放是以块结构方式进行的。当获取多个锁时，它们以相反顺序释放，并且所有锁都在获取它们的相同作用域内释放。

在 `Lock` 实现上下文中，锁的获取和释放可以更灵活。例如，某些并发访问数据结构的算法需要使用“手递锁”（hand-over-hand）或“链锁”（chain locking）：你获取节点 A 的锁，然后是 B，释放 A 并获取 C，然后释放 B 并获取 D，以此类推。

`Lock` 接口的实现允许在不同的作用域内获取和释放锁，并允许以任何顺序获取和释放多个锁，从而使得这些技术成为可能。

这种灵活性的增加也带来了额外的责任。块结构化锁的缺失意味着消除了在 `synchronized` 方法和块中发生的锁的自动释放机制。因此，你通常应该采用以下获取和释放的惯用法：

```
Lock l = ...; // ... 是获取锁代码占位符
l.lock();
try {
    // 访问受此锁保护的资源
} catch (Exception ex) {
    // 恢复不变性
} finally {
    l.unlock();
}
```

这种惯用法确保了已获取的锁始终会被释放。

> **注意**：所有 `Lock` 实现都强制执行与内置监视器锁（monitor lock）相同的内存同步语义。

## ReentrantLock

你通过调用以下构造函数之一来初始化 `ReentrantLock`：

- `ReentrantLock()`：创建一个 `ReentrantLock` 实例。此构造函数等同于 `ReentrantLock(false)`。

- `ReentrantLock(boolean fair)`：创建一个具有特定公平策略的 `ReentrantLock` 实例。当此锁应使用公平排序策略时，传入 `true`：即在竞争情况下，锁将倾向于授予等待时间最长的线程访问权限。

`ReentrantLock` 实现了 `Lock` 的方法。然而，当调用线程未持有锁时，它的 `unlock()` 实现会抛出 `java.lang.IllegalMonitorStateException`。此外，`ReentrantLock` 还提供了自己的方法。例如，`boolean isFair()` 返回公平策略，`boolean isHeldByCurrentThread()` 在锁被当前线程持有时返回 `true`。列表 7-1 演示了 `ReentrantLock`。

### 列表 7-1. 使用 ReentrantLock 实现同步

```java
import java.util.concurrent.Executors;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.TimeUnit;
import java.util.concurrent.locks.ReentrantLock;

public class RLDemo {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(2);
        final ReentrantLock lock = new ReentrantLock();

        executor.execute(new Worker("ThreadA"));
        executor.execute(new Worker("ThreadB"));
        try {
            executor.awaitTermination(5, TimeUnit.SECONDS);
        } catch (InterruptedException ie) {
            ie.printStackTrace();
        }
        executor.shutdownNow();
    }

    static class Worker implements Runnable {
        private final String name;
        private final ReentrantLock lock;

        Worker(String name, ReentrantLock lock) {
            this.name = name;
            this.lock = lock;
        }

        @Override
        public void run() {
            lock.lock();
            try {
                if (lock.isHeldByCurrentThread()) {
                    System.out.printf("Thread %s entered critical section.%n", name);
                    System.out.printf("Thread %s performing work.%n", name);
                    try {
                        Thread.sleep(2000);
                    } catch (InterruptedException ie) {
                        ie.printStackTrace();
                    }
                    System.out.printf("Thread %s finished working.%n", name);
                }
            } finally {
                lock.unlock();
            }
        }
    }
}
```

列表 7-1 描述了一个应用程序，其默认主线程创建了一对工作线程，这些线程进入、模拟工作并离开临界区。它们使用 `ReentrantLock` 的 `lock()` 和 `unlock()` 方法来获取和释放重入锁。当线程调用 `lock()` 且锁不可用时，该线程将被禁用（无法调度），直到锁变得可用。

按照如下方式编译列表 7-1：

```
javac RLDemo.java
```

按照如下方式运行生成的程序：

```
java RLDemo
```

你应该发现输出类似于以下内容（消息顺序可能略有不同）：

```
ThreadA entered critical section.
ThreadA performing work.
ThreadA finished working.
ThreadB entered critical section.
ThreadB performing work.
ThreadB finished working.
```

## Condition

该接口将 `Object` 的等待和通知方法（`wait()`，`notifyAll()`）提取为不同的 `Condition` 对象，通过将它们与任意 `Lock` 实现结合，实现了每个对象拥有多个等待集（wait-sets）的效果。当 `Lock` 替代 `synchronized` 方法和块时，`Condition` 取代了 `Object` 的等待/通知方法。

> `Condition` 本质上与锁绑定。要为 `Lock` 实例获取 `Condition`，请使用 `Lock` 的 `newCondition()` 方法。

`Condition` 声明了以下方法：

- `await()`：强制调用线程等待，直到被信号或被中断。

- `boolean await(long time, TimeUnit unit)`：强制调用线程等待，直到被信号、中断，或者指定的等待时间到期。

- `long awaitNanos(long nanoTimeout)`：强制当前线程等待，直到被信号、中断，或者指定的等待时间到期。

- `void awaitInterruptibly()`：强制当前线程等待，直到被信号。

- `boolean awaitUntil(Date deadline)`：强制当前线程等待，直到被信号、中断，或者指定的截止日期到达。

- `void signal()`：唤醒一个线程。

- `void signalAll()`：唤醒所有线程。

### 列表 7-2. 使用 Locks 和 Conditions 实现同步

```java
import java.util.concurrent.locks.Condition;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class PC {
    public static void main(String[] args) {
        Shared s = new Shared();
        new Producer(s).start();
        new Consumer(s).start();
    }
}

class Shared {
    private char c;
    private volatile boolean available;
    private final Lock lock;
    private final Condition condition;

    Shared() {
        available = false;
        lock = new ReentrantLock();
        condition = lock.newCondition();
    }

    Lock getLock() {
        return lock;
    }

    char getSharedChar() {
        lock.lock();
        try {
            while (!available) {
                condition.await();
            }
        } catch (InterruptedException ie) {
            ie.printStackTrace();
        } finally {
            available = false;
            condition.signal();
            lock.unlock();
        }
        return c;
    }

    void setSharedChar(char c) {
        lock.lock();
        try {
            while (available) {
                condition.await();
            }
        } catch (InterruptedException ie) {
            ie.printStackTrace();
        } finally {
            this.c = c;
            available = true;
            condition.signal();
            lock.unlock();
        }
    }
}

class Producer extends Thread {
    private final Lock l;
    private final Shared s;

    Producer(Shared s) {
        this.s = s;
        l = s.getLock();
    }

    @Override
    public void run() {
        for (char ch = 'A'; ch <= 'Z'; ch++) {
            s.setSharedChar(ch);
            System.out.println(ch + " produced by producer.");
        }
    }
}

class Consumer extends Thread {
    private final Lock l;
    private final Shared s;

    Consumer(Shared s) {
        this.s = s;
        l = s.getLock();
    }

    @Override
    public void run() {
        char ch;
        do {
            ch = s.getSharedChar();
            System.out.println(ch + " consumed by consumer.");
        } while (ch != 'Z');
    }
}
```

按照如下方式编译列表 7-2：

```
javac PC.java
```

按照如下方式运行生成的应用程序：

```
java PC
```

你应该能够观察到与以下输出前缀相同的输出，这表示了步调同步（生产者线程在项被消费之前不会产生，消费者线程在项被产生之前不会消费）：

```
A produced by producer.
A consumed by consumer.
B produced by producer.
B consumed by consumer.
C produced by producer.
C consumed by consumer.
D produced by producer.
D consumed by consumer.
```

## ReadWriteLock

在某些情况下，数据的读取频率远高于修改频率。例如，你可能创建了一个单词定义的在线字典，许多线程会并发读取它，而单个线程可能会偶尔添加新定义或更新现有的定义。锁框架为这些情况提供了一种读写锁机制，它在读取时提供更高的并发性，在写入时提供独占访问的安全性。该机制基于 `ReadWriteLock` 接口。

`ReadWriteLock` 声明了以下方法：

- `Lock readLock()`：返回用于读取的锁。

- `Lock writeLock()`：返回用于写入的锁。

## ReentrantReadWriteLock

`ReadWriteLock` 由 `ReentrantReadWriteLock` 类实现，该类描述了与 `ReentrantLock` 具有相似语义的重入读写锁。

你可以通过调用以下任一构造函数来初始化 `ReentrantReadWriteLock` 实例：

- `ReentrantReadWriteLock()`：创建一个 `ReentrantReadWriteLock` 实例。此构造函数等同于 `ReentrantReadWriteLock(false)`。

- `ReentrantReadWriteLock(boolean fair)`：创建一个具有指定公平策略的 `ReentrantReadWriteLock` 实例。当此锁应使用公平排序策略时，向 `fair` 传递 `true`。

对于公平排序策略，当当前持有的锁释放时，等待时间最长的单个写线程将被分配锁；或者当有一组读者等待时间超过所有写线程时，该组读者将被分配读锁。

尝试获取公平读锁（非重入）的线程在写锁被持有或存在等待的写线程时将发生阻塞。在当前等待最久的写线程获取并释放写锁之前，该线程将不会获取读锁。如果写线程放弃了等待，导致一个或多个读者成为最长等待者，则这些读者将被分配读锁。

尝试获取公平写锁（非重入）的线程除非读锁和写锁都是空闲的（这意味着没有等待线程），否则将发生阻塞。（非阻塞的 `tryLock()` 方法不遵循此公平设置，并在可能的情况下会立即获取锁，无论是否存在等待线程。）

在实例化该类后，你通过以下方法来获取读锁和写锁：

- `ReentrantReadWriteLock.readLock()`：返回用于读取的锁。

- `ReentrantReadWriteLock.writeLock()`：返回用于写入的锁。



每个嵌套的 `ReadLock` 和 `WriteLock` 类都实现了 `Lock` 接口并声明了自己的方法。此外，`ReentrantReadWriteLock` 还声明了额外的方法，例如以下成对：

- `int getReadHoldCount()`: 返回调用线程持有锁的重入次数，当调用线程未持有读锁，则返回 0。读者线程对每个未与 `unlock` 操作匹配的动作都拥有一个持有计数。

- `int getWriteHoldCount()`: 返回调用线程持有锁的重入次数，当调用线程未持有写锁，则返回 0。写线程对每个未与 `unlock` 操作匹配的动作都拥有一个持有计数。

为了演示 `ReadWriteLock` 和 `ReentrantReadWriteLock`，列表 7-3 展示了一个应用程序，其中写线程产生一个单词/定义条目的字典，而读者线程不断随机访问条目并输出它们。

### 列表 7-3. 使用 ReadLock 满足字典应用程序的读写写线程

```java
import java.util.HashMap;
import java.util.Map;

import java.util.concurrent.Executors;
import java.util.concurrent.ExecutorService;

import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReadWriteLock;
import java.util.concurrent.locks.ReentrantReadWriteLock;

public class Dictionary {
    public static void main(String[] args) {
        final String[] words = {
            "hypocalcemia",
            "prolificity",
            "assidduous",
            "indefatigable",
            "castellan"
        };

        final String[] definitions = {
            "a deficiency of calcium in the blood",
            "unduly prolonged or drawn out",
            "showing great care, attention, and effort",
            "able to work or continue for a lengthy time without tiring",
            "the governor or warden of a castle or fort"
        };

        Map<String, String> dictionary = new HashMap<String, String>();

        ReadWriteLock rwl = new ReentrantReadWriteLock(true);
        final Lock rlock = rwl.readLock();
        final Lock wlock = rwl.writeLock();

        Runnable writer = () -> {
            for (int i = 0; i < words.length; i++) {
                wlock.lock();
                try {
                    dictionary.put(words[i], definitions[i]);
                    System.out.println("writer produced " + words[i]);
                } finally {
                    wlock.unlock();
                }
                try {
                    Thread.sleep((long) (Math.random() * 100));
                } catch (InterruptedException ie) {
                    System.err.println("writer interrupted");
                }
            }
        };

        Runnable reader = () -> {
            while (true) {
                rlock.lock();
                try {
                    int i = (int) (Math.random() * words.length);
                    String definition = dictionary.get(words[i]);
                    if (definition != null) {
                        System.out.println("reader consumed " + words[i] + ": " + definition);
                    }
                } finally {
                    rlock.unlock();
                }
                try {
                    Thread.sleep((long) (Math.random() * 100));
                } catch (InterruptedException ie) {
                    System.err.println("reader interrupted");
                    break;
                }
            }
        };

        ExecutorService executor = Executors.newFixedThreadPool(2);
        executor.execute(writer);
        executor.execute(reader);
    }
}
```

## 练习

以下练习旨在测试你对第 7 章内容的理解情况：

1. 定义 lock（锁）。

2. `Lock` 对象与线程进入临界区（通过 `synchronized` 关键字控制）时获得的内建锁（intrinsic locks）相比，最大的优势是什么？

3. 正或错：当调用线程未持有时，`ReentrantLock().unlock()` 会抛出 `IllegalMonitorStateException`。

4. 如何为特定的 `Lock` 实例获取一个用于 `Condition` 实例？

5. 正或错：`ReentrantReadWriteLock()` 创建的是具有公平排序策略的 `ReentrantReadWriteLock` 实例。

6. 定义 `StampedLock`。

7. `java.util.concurrent.locks` 包包含一个 `LockSupport` 类。`LockSupport` 的作用是什么？

8. 用使用 `ReentrantLock` 替 `synchronized` 的等效类替换以下 ID 类：

```java
public class ID {
    private static synchronized int counter; // 默认初始化为 0
    public static synchronized int getID() {
        int temp = counter + 1;
        try {
            Thread.sleep(1);
        } catch (InterruptedException ie) {
        }
        return counter = temp;
    }
}
```

## 总结

`java.util.concurrent.locks` 包提供了一个由接口和类组成的框架，用于锁定和等待条件，这种方式与基于对象内建锁的同步以及 `Object` 的 wait/notification（等待/通知）机制不同。并发工具类包含一个锁框架，它通过提供锁轮询（polling）、超时等待等功能改进了内建同步和等待/通知机制。

锁框架包含了常用的 `Lock`、`ReentrantLock`、`Condition`、`ReadWriteLock` 和 `ReentrantReadWriteLock` 类型，我在本章中探讨了这些类型。我还简要向你介绍了 Java 8 中引入的 `StampedLock` 类。

# 第 5 至第 7 章向你介绍了并发工具类、执行器（以及 callables 和 futures）、同步器和锁框架。在本章中，我通过介绍并发集合、原子变量、Fork/Join 框架和完成服务（completion services），完成了对并发工具类的全部介绍。

> 注意：由于时间限制，我未能涵盖 futures。如果你对这个主题感兴趣，我建议你查看 Tomasz Nurkiewicz 写的非常优秀的博客文章，标题为“Java 8: Definitive guide to CompletableFuture”，地址为 http://www.nurkiewicz.com/2013/05/java-8-definitive-guide-to.html。

# 并发集合

Java 集合框架（Collections Framework）提供了位于 `java.util` 包中的接口和类。接口包括 `List`、`Set` 和 `Map`；类包括 `ArrayList`、`TreeSet` 和 `HashMap`。

`ArrayList`、`TreeSet`、`HashMap` 以及其他实现这些接口的类都不是线程安全的。但你可以通过使用 `java.util.Collections` 类中的同步包装方法（synchronized wrapper methods）使它们变为线程安全。例如，你可以将一个 `ArrayList` 实例传递给 `Collections.synchronizedList()` 以获取 `ArrayList` 的线程安全变体。

尽管在多线程环境中经常需要它们来简化代码，但线程安全的集合存在几个问题：

- 在遍历可能在迭代期间被另一个线程修改的集合之前，必须获取锁。如果未获取锁且集合被修改，极可能会抛出 `java.util.ConcurrentModificationException`。因为集合框架类返回的是快速失败（fail-fast）迭代器，这些迭代器在迭代期间集合被修改时会抛出 `ConcurrentModificationException`。快速失败迭代器对于并发应用程序通常是不方便的。

- 当多个线程频繁访问同步集合时，性能会下降。这种性能问题最终影响应用程序的可扩展性。

并发工具类通过包含并发集合解决了这些问题，并发集合是存储在 `java.util.concurrent` 包中的、高性能且高度可扩展的集合型类型。其以集合为类的类返回弱一致（weakly-consistent）迭代器，这些迭代器具有以下属性：

- 在迭代开始后删除的元素如果尚未通过迭代器的 `next()` 方法返回，将不会被返回。

- 在迭代开始后添加的元素可能返回，也可能不返回。

- 在集合迭代期间，无论对集合进行了什么修改，没有任何元素会被返回多次一次。

以下列表列出了你在 `java.util.concurrent` 包中可以找到的一些并发集合类型的简短示例：

- `BlockingQueue` 是 `java.util.Queue` 的子接口，它还支持阻塞操作，即在获取元素之前等待队列非空，以及等待有空间存储元素。`ArrayBlockingQueue`、`DelayQueue`、`LinkedBlockingQueue`、`PriorityBlockingQueue` 和 `SynchronousQueue` 均直接实现了该接口。`LinkedDeque` 和 `LinkedTransferQueue` 实现了这些 `BlockingQueue` 子接口。

- `ConcurrentMap` 是 `java.util.Map` 的子接口，它声明了额外的不可拆分的 `putIfAbsent()`、`remove()` 和 `replace()` 方法。`ConcurrentHashMap` 类（`java.util.HashMap` 的并发等效类）、`ConcurrentNavigableMap` 类和 `ConcurrentSkipListMap` 类实现了这些。

# 第 8 章 额外的并发工具类

针对 `BlockingQueue`、`ArrayBlockingQueue` 以及其他并发集合类型的 Oracle Javadoc 将这些类型标识为集合框架的一部分。

## 使用 BlockingQueue 和 ArrayBlockingQueue

`BlockingQueue` 的 Javadoc 揭示了生产者-消费者应用的简单性，它比第 3 章中显示的等效实现（见 3-1）简单得多，因为它不需要处理同步问题。8-1 使用 `BlockingQueue` 及其 `ArrayBlockingQueue` 实现实现了高层生产者-消费者模型。

### 列表 8-1. 第 3 章 PC 的 BlockingQueue 等效实现

```java
import java.util.concurrent.ArrayBlockingQueue;
import java.util.concurrent.BlockingQueue;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class PC {
    public static void main(String[] args) {
        final BlockingQueue<Character> bq;
        bq = new ArrayBlockingQueue<>(26);
        final ExecutorService executor = Executors.newFixedThreadPool(2);
        Runnable producer = () -> {
            for (char ch = 'A'; ch <= 'Z'; ch++) {
                try {
                    bq.put(ch);
                    System.out.printf("%c produced by " +
                            "producer.%n", ch);
                } catch (InterruptedException ie) {
                }
            }
        };

        executor.execute(producer);
        Runnable consumer = () -> {
            char ch = '\0';
            do {
                try {
                    ch = bq.take();
                    System.out.printf("%c consumed by " + "consumer.%n", ch);
                } catch (InterruptedException ie) {
                }
            } while (ch != 'Z');
            executor.shutdownNow();
        };

        executor.execute(consumer);
    }
}
```

列表 8-1 分别使用 `BlockingQueue` 的 `put()` 和 `take()` 方法将对象放入阻塞队列和从阻塞队列中移除对象。`put()` 在没有空间放入对象时阻塞；`take()` 在队列为空时阻塞。

尽管 `BlockingQueue` 确保字符在产生之前不会被消费，但此应用程序的输出可能相反。例如，这里是某次运行的部分输出：

Y consumed by consumer.

Y produced by producer.

Z consumed by consumer.

Z produced by producer.

第 3 章的 PC 应用（列表 3-2）通过在 `setSharedChar()`/`System.out.` 周围引入额外的同步层解决了这种错误的输出顺序。第 7 章的 PC 应用（列表 7-2）通过将这些方法调用放在 `lock()` 和 `unlock()` 方法调用之间解决了这种错误的输出顺序。

### 学习 ConcurrentHashMap

`ConcurrentHashMap` 类的行为类似于 `HashMap`，但它的设计目标是为了在多线程上下文中工作，而不需要显式的同步。例如，你经常需要检查 map 是否包含某个特定值，当该值不存在时，你将该值放入 map：



```java
if (!map.containsKey("some string-based key"))
    map.put("some string-based key", "some string-based value");
```

尽管这段代码简单且看起来可以完成工作，但它并不是线程安全的。在调用 `map.containsKey()` 和 `map.put()` 之间，另一个线程可能会插入此条目，导致其被覆盖。为了修复这个竞态条件，你必须显式地同步这段代码，我在这里进行了演示：

```java
synchronized(map)
{
  if (!map.containsKey("some string-based key"))
    map.put("some string-based key", "some string-based value");
}
```

这种方法的问题在于，你在检查键是否存在以及键不存在时不向 map 中添加条目时，对整个 map 进行了读写操作锁定。当许多线程尝试访问 map 时，这种锁定会影响性能。

泛型 `ConcurrentHashMap<K, V>` 类通过提供 `V putAbsent(K key, V value)` 方法解决了这个问题，该方法在键不存在时向 map 引入键/值条目。该方法等同于以下代码片段，但提供了更好的性能：

```java
synchronized(map)
{
  if (!map.containsKey(key))
    return map.put(key, value)
  else
    return map.get(key);
}
```

使用 `putIfAbsent()`，之前的代码片段转换为下面的简单代码片段：

```java
map.putIfAbsent("some string-based key", "some string-based value");
```

## 第 8 章 额外的并发工具

注意 Java 8 通过增加 30 多个新方法改进了 `ConcurrentHashMap`，这些方法在很大程度上通过聚合操作支持 lambda 表达式和 Streams API。执行聚合操作的方法包括 `forEach()` 方法（`forEach()`, `forKey()`, `forValue()`, 和 `forEntry()`）、搜索方法（`search()`, `searchKeys()`, `searchValues()`, 和 `searchEntries()`）以及归约方法（`reduce()`, `reduceToDouble()`, `reduceLong()` 等）。还添加了一些杂项方法（如 `mappingCount` 和 `newkeySet()`）。由于 JDK 8 的出现，`ConcurrentHashMap`（以及基于它们构建的类）现在作为缓存更有用。缓存改进的变化包括为键计算值的方法，以及对扫描（并可能驱逐）条目的改进支持，以及对包含大量元素的 map 更好的支持。

## 原子变量

与对象监视器关联的内在锁在历史上一直性能不佳。尽管性能有所提高，但在创建 Web 服务器以及在显著线程竞争的情况下需要高扩展性和高性能的应用程序时，它们仍然会成为瓶颈。

许多研究致力于创建非阻塞算法，这些算法可以从根本上提高同步上下文的性能。这些算法提供了更高的扩展性，因为当多个线程争抢相同数据时，线程不会遭受死锁。此外，线程也不会遭受死锁和其他活跃性问题。

Java 5 通过引入 `java.util.concurrent.atomic` 包，提供了创建高效非阻塞算法的能力。根据该包的文档，`java.util.concurrent.atomic` 提供了一组类工具包，支持对单个变量进行无锁线程安全操作。

`java.util.concurrent.atomic` 包中的类扩展了 volatile 值、字段和数组元素的概念，使它们能够提供原子的条件更新，因此不需要外部同步。换句话说，你可以在不需要外部同步的情况下获得与 volatile 变量相关的内存语义以及互斥。

> 注意：原子（atomic）和不可分割（indivisible）这两个词被广泛认为是等价的，尽管我们可以分裂原子。

## 第 8 章 额外的并发工具

这里描述了位于 `java.util.concurrent.atomic` 中的一些类：

- `AtomicBoolean`: 可以被原子更新的布尔值。
- `AtomicInteger`: 可以被原子更新的 int 值。
- `AtomicIntegerArray`: 元素可以被原子更新的 int 数组。
- `AtomicLong`: 可以被原子更新的 long 值。
- `AtomicLongArray`: 元素可以被原子更新的 long 数组。
- `AtomicReference`: 可以被原子更新的引用。
- `AtomicReferenceArray`: 元素可以被原子更新的对象引用数组。

原子变量用于实现计数器、序列生成器（例如 `java.util.concurrent.ThreadLocalRandom`）以及在高线程竞争下不产生性能问题的情况下需要互斥的其他结构。例如，列表 8-2 中的 ID 类，其 `nextID()` 返回唯一的 long 整数标识符。

**Listing 8-2.** 通过 synchronized 以线程安全的方式返回唯一标识符

```java
class ID {
    private static volatile long nextID = 1;
    static synchronized long nextID() {
        return nextID++;
    }
}
```

尽管代码已经了适当的同步（并且考虑了可见性），但与 synchronized 关联的内在锁在严重的线程竞争下会损害性能。此外，可能会发生死锁等活跃性问题。列表 8-3 显示了如何通过用原子变量替换 synchronized 来避免这些问题。

## 第 8 章 额外的并发工具

**Listing 8-3.** 通过 AtomicLong 以线程安全的方式返回唯一 ID

```java
import java.util.concurrent.atomic.AtomicLong;

class ID {
    private static AtomicLong nextID = new AtomicLong(1);

    static long getNextID() {
        return nextID.getAndIncrement();
    }
}
```

在列表 8-3 中，我重构了 `nextID()` 以使用 `AtomicLong`。（注意：原始 OCR 在方法名上有拼写错误，已修正为 `getNextID`）。

> 注意：`java.util.concurrent.atomic` 包包含 `DoubleAccumulator`, `DoubleAdder`, `LongAccumulator` 和 `LongAdder`。

### 理解原子魔法

尽管你可能认为可以使用 volatile 作为同步方案，volatile 变量只能解决可见性问题。它们无法安全地实现互斥所需的原子读写序列。然而，有一种替代方案是并发工具所提供的性能提升。这种替代方案被称为比较交换（compare-and-swap，CAS）。

比较交换（CAS）是不可中断处理器特定指令的通用术语，它读取内存位置，将读取值与预期值进行比较，并在读取值匹配预期值时在内存位置中存储新值。现代处理器提供了 CAS 的变体。例如，Intel 处理器使用 cmpxchg 系列，而旧的 PowerPC 处理器提供加载链接（如 lx）和条件存储（如 stwcx）。

CAS 支持原子读写序列。你通常这样使用 CAS：

1. 从地址 A 读取 x。
2. 对 x 执行多集计算以得出新值 y。
3. 使用 CAS 将 A 从 x 改为 y。当 A 的值没有变化时，CAS 成功。

为了理解 CAS 的用处，请考虑列表 8-2 中的类，它返回一个唯一标识符。因为 CAS 类声明其 `nextID()` 是同步的，对监视器锁的过度竞争可能会延迟任何线程，并导致应用程序无法扩展。

`compareAndSwap()` 方法以原子方式执行以下序列：

```java
int readValue = value; // 获取存储的值。
if (readValue == expectedValue) // 如果存储的值未被修改 ...
value = newValue; // 修改为新值。
return readValue; // 返回可能更改之前的值。
```

列表 8-4 展示了 ID 的新版本，它使用 CAS 类以高效的方式获取唯一标识符。（忘记使用 JNI 的性能影响，并假设我们直接访问处理器特定的 CAS 指令。）

```java
class ID {
    private static AtomicLong nextID = new AtomicLong(1);

    static long getNextID() {
        return nextID.getAndIncrement();
    }
}
```

## 第 8 章 额外的并发工具

**Listing 8-4.** 通过 CAS 以线程安全的方式返回唯一 ID

```java
class ID {
    private static CAS value = new CAS(1);
    static long getNextID() {
        int curValue = value.getValue();
        while (value.compareAndSwap(curValue, curValue + 1) != curValue)
            curValue = value.getValue();
        return curValue - 1;
    }
}
```

ID 类封装了一个初始化为 int-1 的 CAS 实例，并声明了一个用于获取值的 `getNextID()` 方法。在获取到实例值后，`getNextID()` 会反复调用 `compareSwap()`，直到值没有被（由另一个线程）改变为止。该方法可以自由更改此值，然后返回之前的值。在不涉及锁的情况下，可以避免竞争以及过度的上下文切换。性能得到了提高，代码更具可扩展性。

作为 CAS 处理并发的一个示例，`java.util.locks.ReentrantLock` 此类在高线程竞争下提供了比 `synchronized` 顺序更好的性能。为了提高性能，`ReentrantLock` 的同步由抽象 `java.util.concurrent.locks.AbstractQueuedSynchronizer` 类的子类管理。反，该类利用了未公开的 `sun.misc.Unsafe` 类及其 `compareAndSwapInt()` CAS 方法。此外，它们提供了一个如下形式的方法：

原子变量也利用了 CAS。此外，它们提供了一个方法

```java
boolean compareAndSet(expectedValue, updateValue)
```

此方法（其参数类型在不同类之间有所差异）在变量当前持有 `expectedValue` 时原子性地将变量设置为 `updateValue`，成功时返回 true。

## Fork/Join 框架

代码始终有执行得更快的需求。在历史上，这种需求通过增加微处理器速度和/或支持多个处理器来满足。然而，大约在 2003 年，由于物理限制，微处理器速度停止了增长。为了补偿这一点，处理器制造商开始在其处理器中添加多个处理器核心，通过大规模并行来提高速度。

**注意** 并行是指通过多个处理器和核心的组合同时运行线程。相比之下，并发是并行的一种更通用形式，其中线程同时运行，或者通过上下文切换看起来同时运行，也称为虚拟并行。一些人进一步将并发描述为程序或操作系统的属性，而将并行描述为同时执行多个线程的运行时行为。

Java 通过其低级线程特性和高级并发特性（如线程池）支持并发。并发的问题在于它没有最大化地利用可用的处理器/核心资源。例如，假设你创建了一个排序算法，它将数组分为两半，分配两个线程分别排序每个部分，并在两个线程都完成后合并结果。

假设每个线程都运行在不同的处理器上。由于数组的每个部分可能发生不同的顺序元素，可能会出现一个线程在另一个线程之前完成，并在合并发生前进行等待。在这种情况下，处理器资源就被浪费了。

这个问题（以及代码冗长且难以阅读的相关问题）可以通过递归地将任务拆分为为子任务并合并结果来解决。这些子任务并行运行，并在恰约相同的时间完成（即使不是同一时刻），此时它们的结果被合并并向上堆栈传递给上一层子任务。这使得代码不再那么冗长，并且（通常）更容易理解。Java 提供了 Fork/Join 框架来实现这种场景。

Fork/Join 主要由一个特殊的执行器服务和一个线程池组成。执行器服务为框架提供一个任务，该任务被拆分成更小的任务，并从池中被分叉（由不同的线程执行）。任务会等待直到（其子任务完成）。

Fork/Join 使用“工作窃取”（work stealing）来最小化线程竞争和开销。线程池中的每个工作线程都有自己的双端工作队列，并向该队列推送新任务。如果队列为空，工作线程尝试从另一个队列的尾部获取任务。窃取并不频繁，因为工作线程按后进先出（LIFO）顺序将任务放入队列，而且随着问题被分解子问题，工作项的大小会变得更小。你首先将任务交给一个中心工作线程，它不断将其分成更小的任务。最终，所有工作线程在极少同步的情况下都有事。

Fork/Join 主要由 `java.util.concurrent` 包中的 `ForkJoinPool`、`ForkJoinTask`、`ForkJoinWorkerThread`、`RecursiveAction`、`RecursiveTask` 和 `CountedCompleter` 组成：

- `ForkJoinPool` 是一个用于 ForkJoinTasks 的 `java.util.ExecutorService` 实现。`ForkJoinPool` 实例为非 ForkJoinTask 客户端的提交提供了入口，并提供管理和监控操作。
- `ForkJoinTask` 是在 ForkJoinPool 上下文中运行的任务的抽象类。`ForkJoinTask` 实例是一个类似于线程的实体，比普通线程轻得多。少量的实际任务在 ForkJoinPool 中）就可以托管海量的任务和子任务，代价是某些使用功能上的限制。
- `ForkJoinWorkerThread` 描述了由 ForkJoinPool 实例管理的任务，该任务执行 ForkJoinTasks。
- `RecursiveAction` 描述了一个没有结果的递归 ForkJoinTask。
- `RecursiveTask` 描述了一个带有结果的递归 ForkJoinTask。
- `CountedCompleter` 在被触发且没有剩余待处理操作时，通过一个完成操作（用于完成 fork/join 任务）来完成 ForkJoinTask。

Java 文档提供了基于 `RecursiveAction` 的任务（例如排序）和基于 `RecursiveTask` 的任务（例如计算）的示例。你也可以使用 `RecursiveAction` 来完成（任务）（请参见斐波那契数字）。

**Listing 8-5.** 用于表示二维矩阵的类

```java
public class Matrix {
    private int[][] matrix;

    public Matrix(int nrows, int ncols) {
        matrix = new int[nrows][ncols];
    }

    public int getRows() {
        return matrix.length;
    }

    public int getCols() {
        return matrix[0].length;
    }

    public int getValue(int row, int col) {
        return matrix[row][col];
    }

    public void setValue(int row, int col, int value) {
        matrix[row][col] = value;
    }
}
```

**Listing 8-6.** 通过标准算法相两个实例



# 第 8 章 额外的并发工具

```java
public class MatMult {
    public static void main(String[] args) {
        Matrix a = new Matrix(1, 3);
        a.setValue(0, 0, 1);
        a.setValue(0, 1, 2);
        a.setValue(0, 2, 3);

        Matrix b = new Matrix(3, 2);
        b.setValue(0, 0, 4);
        b.setValue(0, 1, 5);
        b.setValue(1, 0, 6);
        b.setValue(1, 1, 7);
        b.setValue(2, 0, 8);
        b.setValue(2, 1, 9);

        dump(a);
        dump(multiply(a, b));
    }

    public static void dump(Matrix m) {
        for (int i = 0; i < m.getRows(); i++) {
            for (int j = 0; j < m.getCols(); j++) {
                System.out.printf("%d ", m.getValue(i, j));
            }
            System.out.println();
        }
    }

    public static Matrix multiply(Matrix a, Matrix b) {
        if (a.getCols() != b.getRows())
            throw new IllegalArgumentException("行列不匹配");
        Matrix result = new Matrix(a.getRows(), b.getCols());
        for (int i = 0; i < a.getRows(); i++) {
            for (int j = 0; j < b.getCols(); j++) {
                for (int k = 0; k < a.getCols(); k++) {
                    result.setValue(i, j, a.getValue(i, k) * b.getValue(k, j));
                }
            }
        }
        return result;
    }
}
```

你应该观察到以下输出，它表示一个 1 行 3 列的矩阵乘以一个 3 行 2 列的矩阵，结果是一个 1 行 2 列的矩阵：

```
1 2 3

4 7

5 8

6 9

32 50
```

计算机科学家将此算法分类为 `O(n*n*n)`，读作“big-of-n-cubed”或“近似 n 的立方”。这种表示法是对算法性能的一种抽象分类方式（而不会纠结于微处理器速度等特定细节）。`O(n*n*n)` 的分类表示性能非常差，并且随着相乘矩阵尺寸的增加，这种性能会进一步恶化。

（在多处理器和多核平台上）通过将每个“行乘列”的乘法任务分配给独立的线程类实体，可以提高性能。

## 列表 8-7. 使用 Fork/Join 框架乘以两个矩阵实例

```java
import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.ForkJoinPool;
import java.util.concurrent.RecursiveAction;
```

```java
public class MatMult extends RecursiveAction {
    private final Matrix a, b, c;
    private final int row;

    public MatMult(Matrix a, Matrix b, Matrix c) {
        this(a, b, c, -1);
    }

    public MatMult(Matrix a, Matrix b, Matrix c, int row) {
        if (a.getCols() != b.getRows()) {
            throw new IllegalArgumentException("rows/columns mismatch");
        }
        this.a = a;
        this.b = b;
        this.c = c;
        this.row = row;
    }

    @Override
    public void compute() {
        if (row == -1) {
            List<MatMult> tasks = new ArrayList<>();
            for (int row = 0; row < a.getRows(); row++) {
                tasks.add(new MatMult(a, b, c, row));
            }
            invokeAll(tasks);
        } else {
            multiplyByColumn(a, b, c, row);
        }
    }

    public static void multiplyByColumn(Matrix a, Matrix b, Matrix c, int row) {
        for (int j = 0; j < b.getCols(); j++) {
            for (int k = 0; k < a.getCols(); k++) {
                c.setValue(row, j, a.getValue(row, k) * b.getValue(k, j));
            }
        }
    }

    public static void dump(Matrix m) {
        for (int i = 0; i < m.getRows(); i++) {
            for (int j = 0; j < m.getCols(); j++) {
                System.out.print(m.getValue(i, j) + " ");
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Matrix a = new Matrix(2, 3);
        a.setValue(0, 0, 1); // | 1 2 3 |
        a.setValue(0, 1, 2);
        a.setValue(0, 2, 3);
        a.setValue(1, 0, 4); // | 4 5 6 |
        a.setValue(1, 1, 5);
        a.setValue(1, 2, 6);
        dump(a);

        Matrix b = new Matrix(3, 2);
        b.setValue(0, 0, 7); // | 7 1 |
        b.setValue(1, 0, 8); // | 8 2 |
        b.setValue(2, 0, 9); // | 9 3 |
        b.setValue(0, 1, 1);
        b.setValue(1, 1, 2);
        b.setValue(2, 1, 3);
        dump(b);

        Matrix c = new Matrix(2, 2);
        ForkJoinPool pool = new ForkJoinPool();
        pool.invoke(new MatMult(a, b, c));
        dump(c);
    }
}
```

列表 8-7 展示了一个扩展 `RecursiveAction` 的 `MatMult` 类。为了完成有意义的工作，重写了 `RecursiveAction` 的 `compute()` 方法。

> **注意** `compute()` 通常用于递归地将任务分解为多个任务，我选择了以不同的方式处理乘法（为了简洁简单）。

在创建了矩阵 `a` 和 `b` 后，列表 8-7 的 `main()` 方法创建了矩阵 `c` 并实例化 `ForkJoinPool`。然后 `MatMult` 将这三个实例作为参数传递给 `MatMult(Matrix a, Matrix b, Matrix c)` 构造函数，并调用 `ForkJoinPool` 的 `invoke(ForkJoinTask<T> task)` 来启动初始任务。该方法会阻塞直到初始任务及其所有的子任务完成。

## 列表 8-8. 使用完成服务计算欧拉常数

```java
import java.util.concurrent.Callable;
import java.util.concurrent.CompletionService;
import java.util.concurrent.ExecutorCompletionService;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.math.BigDecimal;
import java.math.MathContext;
import java.math.RoundingMode;

public class CSDemo {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(2);
        CompletionService<BigDecimal> completionService = new ExecutorCompletionService<>(executor);

        completionService.submit(new CalculateE(10000));
        completionService.submit(new CalculateE(20000));

        try {
            for (int i = 0; i < 2; i++) {
                System.out.println(completionService.take().get());
            }
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            executor.shutdown();
        }
    }
}

class CalculateE implements Callable<BigDecimal> {
    private final int lastIter;

    public CalculateE(int lastIter) {
        this.lastIter = lastIter;
    }

    @Override
    public BigDecimal call() {
        MathContext mc = new MathContext(lastIter, RoundingMode.HALF_EVEN);
        BigDecimal e = BigDecimal.ONE;
        BigDecimal factorial = BigDecimal.ONE;
        for (int i = 1; i <= lastIter; i++) {
            factorial = factorial.multiply(new BigDecimal(i), mc);
            e = e.add(BigDecimal.ONE.divide(factorial, mc), mc);
        }
        return e;
    }
}
```

按照如下方式编译列表 8-8：

```
javac CSDemo.java
```

按照如下方式运行生成的程序：

```
java CSDemo
```

你应该能够观察到以下输出：

```
2.718218405289404507050160477958486050611789769635251032699800735004065222504250
48334123058879344245741700393450642711
2.71821840528940452365028647135269962497757270409699955749969667262272240663035
3547595332675154481911560094421052668856548476919630224877034499111770684812212638245
913600326751544819115600944210522668856548476919630224877034499111770684812212638245
6648350055041522848631435248419288157726885316753774985226904478800233296655744980953
29786118495171199184146050
```

> **注意** 如果你好奇执行服务和完成服务之间的区别，请考虑：使用执行服务时，编写完提交任务的代码后，你需要编写代码来高效地检索任务结果。而使用完成服务，这项工作几乎是自动化的。观察这些构造的另一种方式是：执行服务为任务提供了一个输入队列和工作线程，而完成服务为任务提供了一个输入队列、工作线程以及一个用于存储任务结果的输出队列。

## 练习题

以下练习题旨在测试你对第 8 章内容的理解：

1. 识别线程安全集合的两个问题。
2. 定义并发集合。
3. 什么是弱一致性迭代器（`weakly-consistent iterator`）？
4. 描述 `BlockingQueue` 接口。
5. 描述 `ConcurrentMap` 接口。
6. 描述 `ArrayBlockingQueue` 和 `LinkedBlockingQueue` `BlockingQueue` 实现类。
7. 判断对/错：面向并发的集合类型属于集合框架（Collections Framework）。
8. 描述 `ConcurrentHashMap` 类。
9. 使用 `ConcurrentHashMap`，如何检查 map 是否包含某个特定值，并在该值不存在时将该值放入 map 中？
10. 描述 `ExecutorService` 接口。
11. 描述 `CompletionService`。
12. 描述 `BlockingQueue` 接口。
13. 描述 `ConcurrentMap` 接口。
14. 描述 `ArrayBlockingQueue`。
15. 描述 `LinkedBlockingQueue`。
16. 描述 `ConcurrentLinkedQueue`。
17. 判断对/错：面向并发的集合类型属于集合框架。
18. 描述 `ConcurrentHashMap` 类。
19. 使用 `ConcurrentHashMap`，如何检查 map 是否包含某个特定值，并在该值不存在时将该值放入 map 中？
20. 描述 `ExecutorService` 接口。

## 总结

本章介绍了并发工具，包括 `ExecutorService`、`CompletionService`、`BlockingQueue` 和 `ConcurrentMap`。我们探索了如何使用这些工具来简化多线程编程并提高性能。我们还看到如何以安全的方式处理常见任务。

---

# 附录 A 练习答案

## 第 1 章：线程基础

22. `Thread` 允许线程等待另一个线程死亡的方法有 `void join()`、`void join(long millis)` 和 `void join(long millis, int nanos)`。

23. `Thread` 允许线程休眠的方法有 `void sleep(long millis)` 和 `void sleep(long millis, int nanos)`。

24. 列表 A-1 展示了第 1 章中调 `IntSleep` 应用。

### 列表 A-1. 中断睡眠的后台线程

```java
public class IntSleep {
    public static void main(String[] args) {
        Runnable r = new Runnable() {
            @Override
            public void run() {
                while (true) {
                    System.out.println("hello");
                    try {
                        Thread.sleep(100);
                    } catch (InterruptedException ie) {
                        System.out.println("interrupted");
                        break;
                    }
                }
            }
        };
        Thread t = new Thread(r);
        t.start();
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ie) {
            t.interrupt();
        }
    }
}
```

## 第 2 章：同步

1. 线程的三个问题是竞态条件、数据竞争和缓存变量。
2. 答案是错误的：当计算的正确性取决于调度器对多个线程的相对计时或交织时，就存在竞态条件。
3. 同步是一个 JVM 特性，确保两个或多个并发线程不会同时执行关键区域。
4. 同步的两个属性是互斥性和可见性。
5. 同步是通过监视器来实现的，监视器是用于控制对必须单独执行的临界区域访问的并发结构。每个 Java 对象都与一个监视器相关，线程可以通过获取和释放监视器的锁标记来锁定或解锁监视器。
6. 答案是正确的：获取锁的线程在调用 `Thread` 的某个 `sleep()` 方法时，不会释放该锁。
7. 你通过在方法头中包含 `synchronized` 关键字来指定同步方法。
9. 活跃性指的是最终会有有利的结果。
10. 三种活跃性类是死锁、活锁和饥饿（也称为无限推迟）。
11. `volatile` 关键字与 `synchronized` 的区别在于 `volatile` 只处理可见性，而 `synchronized` 处理互斥性和可见性。
12. 答案是正确的：Java 还允许你在不需要同步的情况下访问 `final` 字段。



- 13. `CheckingAccount` 类的线程问题是 `withdraw()` 方法中的“检查再执行”（check-then-act）竞态条件 `if (amount < balance)` 和 `balance -= amount;`（这会导致取出的金额超过可用金额），以及可能被缓存的 `balance` 字段。在多处理器/多核系统上，`balance` 字段可能会被缓存，取款线程可能不包含默认主线程在构造函数设置的初始余额。

- 14. 列表 A-2 展示了第 2 章中调用的 `CheckingAccount` 应用。

# 列表 A-2. 修复问题的检查账户

```java
public class CheckingAccount {
    private volatile int balance;

    public CheckingAccount(int initialBalance) {
        balance = initialBalance;
    }

    public synchronized boolean withdraw(int amount) {
        if (amount <= balance) {
            try {
                Thread.sleep((int) (Math.random() * 200));
            } catch (InterruptedException ie) {
                balance -= amount;
                return true;
            }
        }
        return false;
    }

    public static void main(String[] args) {
        final CheckingAccount ca = new CheckingAccount(100);
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String name = Thread.current().getName();
                for (int i = 0; i < 10; i++) {
                    System.out.println(name + " withdrawals $10: " + ca.withdraw(10));
                }
            }
        };
        Thread thdHusband = new Thread(r);
        thdHusband.setName("Husband");
        Thread thdWife = new Thread(r);
        thdWife.setName("Wife");
        thdHusband.start();
        thdWife.start();
    }
}
```

# 附录 A 练习答案

此应用使用 `volatile` 处理潜在的缓存问题，并使用 `synchronized` 处理互斥需求。

# 第 3 章：等待与通知

- 1. 条件是继续执行的前提条件。

- 2. 支持条件的 API 由 `Object` 的三个 `wait()` 方法、一个 `notify()` 方法和一个 `notifyAll()` 方法组成。`wait()` 方法等待条件存在；`notify()` 和 `notifyAll()` 方法在条件结束时通知线程。

- 4. 你调用 `notifyAll()` 方法来唤醒所有在对象监视器上等待的线程。

- 5. 答案是错误的：线程在调用 `Object` 的某个 `wait()` 方法时已获取了递归锁。

- 6. 条件队列（condition queue）是一个存储等待条件存在的线程的数据结构。

- 7. 当你在同步上下文之外调用任何 API 方法时，会抛出 `IllegalMonitorStateException`。

- 8. 虚假唤醒（spurious wakeup）是线程在未被通知或超时的情况下唤醒。

- 9. 你应该在循环中使用 `wait()` 方法来确保活跃性和安全性。

- 10. 列表 A-3 展示了调用的 Await 应用。使用 `wait()` 和 `notifyAll()` 创建高级并发结构

```java
// ... (代码继续)
r = new Runnable() {
    @Override
    public void run() {
        try {
            while (count < 3) {
                Thread.sleep(100);
                synchronized (lock) {
                    lock.notifyAll();
                }
            }
        } catch (InterruptedException ie) {
        }
    }
};
Thread thdA = new Thread(r, "thdA");
Thread thdB = new Thread(r, "thdB");
Thread thdC = new Thread(r, "thdC");
thdA.start();
thdB.start();
thdC.start();
System.out.printf("%s has woken up and is terminating%n", Thread.current().getName());
```

# 第 4 章：额外的线程能力

- 1. 线程组是一组线程。它由 `ThreadGroup` 类表示。

- 2. 你可能会使用线程组对其线程执行公共操作，以简化线程管理。

- 3. 你应该避免使用线程组，因为最有用的 `ThreadGroup` 方法已弃用，并且在获取线程计数和枚举线程之间存在“检查时间到使用时间”的竞态条件。

- 4. 你应该注意线程组，因为它们有助于处理线程执行时抛出的异常。

- 5. 线程本地变量（thread-local）为访问该变量的每个线程提供独立的存储。它由 `ThreadLocal` 类表示。

- 6. 答案是正确的：当调用线程调用 `get()` 时存储中不存在项，此方法将返回 `initialValue()`。

- 7. 你通过使用 `InheritableThreadLocal` 类将值从父线程传递给子线程。

- 8. 构建 `Timer` 框架的类有 `Timer` 和 `TimerTask`。

- 9. 答案是错误的：`Timer()` 创建一个新的定时器，作为非守护线程运行。

- 10. 在固定延迟执行中，每次执行都是相对于上一次执行的实际时间调度的。当执行由于任何原因（如垃圾回收）而延迟时，后续的执行也会被延迟。

- 11. 你调用 `schedule()` 方法来调度固定延迟执行的任务。

- 12. 在固定速率执行中，每次执行都是相对于初始执行的计划执行时间调度的。当执行由于任何原因（如垃圾回收）而延迟时，会连续发生两个或多个执行以“追赶”。

- 13. `Timer` 的 `cancel()` 方法与 `TimerTask` 的 `cancel()` 方法之间的区别如下：`Timer` 的 `cancel()` 方法会终止定时器并丢弃任何当前调度的定时器。相比之下，`TimerTask` 的 `cancel()` 方法仅取消调用它的定时器。

- 14. 列表 A-4 展示了第 4 章中提到的 `BackAndForth` 应用。

# 列表 A-4. 通过定时器反复来回移动星号

```java
import java.util.Timer;
import java.util.TimerTask;

public class BackAndForth {
    static enum Direction { FORWARDS, BACKWARDS }

    public static void main(String[] args) {
        TimerTask task = new TimerTask() {
            final static int MAXSTEPS = 20;

            volatile Direction direction = Direction.FORWARDS;
            volatile int steps = 0;

            @Override
            public void run() {
                switch (direction) {
                    case FORWARDS:
                        System.out.print("\b ");
                        System.out.print("*");
                        break;

                    case BACKWARDS:
                        System.out.print("\b ");
                        System.out.print("\b*");
                        break;
                }

                if (++steps == MAXSTEPS) {
                    direction = (direction == Direction.FORWARDS)
                            ? Direction.BACKWARDS
                            : Direction.FORWARDS;
                    steps = 0;
                }
            }
        };

        Timer timer = new Timer();
        timer.schedule(task, 0, 100);
    }
}
```

# 附录 A 练习答案

## 5: 并发工具与执行器

- 1. 并发工具类是一组类和接口的框架，克服了 Java 低级线程能力的问题。具体来说，低级并发原语（如 `synchronized` 和 `wait()/notify()`）通常难以正确使用，过度依赖同步原语会导致性能问题，从而影响应用程序的可扩展性，而且 Java 的低级线程能力中并不包含线程池和信号量等高级构造结构。

- 2. 存储并发工具类类型的包有 `java.util.concurrent`、`java.util.concurrent.atomic` 和 `java.util.concurrent.locks`。

- 3. 任务是一个实现了 `Runnable` 接口（可运行任务）或 `Callable` 接口（可调用任务）类的对象。

- 4. 执行器是一个其类直接或间接实现了 `Executor` 接口的对象，它将任务提交与任务执行机制解耦。

- 5. `Executor` 接口专门关注 `Runnable`，这意味着可运行任务没有方便的方法向其调用者返回结果（因为 `Runnable` 的 `run()` 方法没有返回值）；`Executor` 未提供跟踪执行可运行任务进度的方法、取消正在执行的可运行任务的方法，或确定可运行任务何时完成执行的方法；`Executor` 无法执行一组可运行任务；且 `Executor` 未提供让应用程序关闭执行器的方法（更不用说如何妥善地关闭执行器了）。

- 6. 通过提供 `ExecutorService` 接口克服了 `Executor` 的局限性。

- 7. `Runnable` 的 `run()` 方法与 `Callable` 的 `call()` 方法之间的区别如下：`run()` 不能返回值，而 `call()` 可以返回值；`run()` 不能抛出检查异常，而 `call()` 可以抛出检查异常。

- 8. 答案是否定的：你从 `Callable` 的 `call()` 方法中可以抛出检查异常和未检查异常，但从 `Runnable` 的 `run()` 方法中只能抛出未检查异常。

- 9. `Future` 是一个其类实现了 `Future` 接口的对象。它代表一个异步计算，并提供了取消任务、返回任务值以及判断任务是否已完成的方法。

- 10. `Executors` 类的 `newFixedThreadPool()` 方法创建一个线程池，该池使用固定数量的线程在共享的无界队列上操作。最多有 `nThreads` 个线程正在处理任务。当所有线程都活跃时提交了额外任务，它们将在队列中等待可用线程。如果任何线程在执行器关闭之前因为执行期间失败而终止，当需要执行后续任务时将有一个新线程取代其位置。池中的线程将一直存在到执行器被显式关闭为止。

- 11. 列表 A-5 展示了第 5 章中提到的 `CountingThreads` 应用。

# 列表 A-5. 基于执行器的计数线程

```java
import java.util.concurrent.Executors;
import java.util.concurrent.ExecutorService;

public class CountingThreads {
    public static void main(String[] args) {
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String name = Thread.currentThread().getName();
                int count = 0;
                while (true) {
                    System.out.println(name + ": " + count++);
                }
            }
        };
        ExecutorService es = Executors.newFixedThreadPool(2);
        es.submit(r);
        es.submit(r);
    }
}
```

- 12. 列表 A-6 展示了第 5 章中提到的带有自定义线程名的 `CountingThreads` 应用。

# 列表 A-6. 基于执行器的计数线程 A 和 B

```java
import java.util.concurrent.Executors;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.ThreadFactory;

public class CountingThreads {
    public static void main(String[] args) {
        Runnable r = new Runnable() {
            @Override
            public void run() {
                String name = Thread.currentThread().getName();
                int count = 0;
                while (true) {
                    System.out.println(name + ": " + count++);
                }
            }
        };
        ExecutorService es = Executors.newFixedThreadPool(2);
        es.submit(r);
        es.submit(r);
    }
}

class NamedThread implements ThreadFactory {
    private volatile String name;

    NamedThread(String name) {
        this.name = name;
    }

    @Override
    public Thread newThread(Runnable r) {
        return new Thread(r, name);
    }
}
```

# 附录 A 练习答案

## 6: 同步器

- 1. 同步器是一种方便同步的类。

- 2. `CountDownLatch` 导致一个或多个线程等待“门”等待，直到另一个线程打开这个门。它由计数和递减操作组成。当 `countDown()` 被调用且计数归零时，释放。

- 3. `CyclicBarrier` 允许一组线程在屏障等待。与协调固定数量线程的屏障不同，`Phaser` 可以协调任意数量的线程。为了实现这一点，`Phaser` 使用阶段（phases）和阶段号。

- 4. 答案是否定的：如果在等待期间屏障被重置，`CyclicBarrier.await()` 将抛出 `BrokenBarrierException`。

- 5. `Phaser` 是一个更灵活的屏障。像 `CyclicBarrier` 一样，`Phaser` 允许一组线程在屏障等待。

- 6. `Exchanger` 提供了一个线程可以交换对象的同步点。每个线程在进入交换器时呈现某个对象，接收对方的对象。

- 7. `Exchanger` 的 `exchange(V)` 方法等待另一个线程到达此交换点（除非调用线程被中断），然后将给的对象传递给它，并接收返回的对象。

- 8. 信号量维护一组许可以限制访问有限资源的线程数量。尝试获取无可用许可的线程将阻塞，直到某些线程释放许可。

- 9. 信号量的两种类型是计数信号量（当前值加 1）和二值信号量或互斥（当前值只能为 0 或 1）。



# 附录 A 练习答案

## 6: 同步器

+ 1. 同步器是一种方便同步的类。

+ 2. `CountDownLatch` 导致一个或多个线程等待“门”等待，直到另一个线程打开这个门。它由计数和递减操作组成。当 `count()` 被调用且计数归零时，释放。

+ 3. `CyclicBarrier` 允许一组线程在屏障等待。与协调固定数量线程的屏障不同，`Phaser` 可以协调任意数量的线程。为了实现这一点，`Phaser` 使用阶段（phases）和阶段号。

+ 4. 答案是否定的：如果在等待期间屏障被重置，`CyclicBarrier.await()` 将抛出 `BarrierException`。

+ 5. `Phaser` 是一个更灵活的屏障。像 `CyclicBarrier` 一样，`Phaser` 允许一组线程在屏障等待。

+ 6. `Exchanger` 提供了一个线程可以交换对象的同步点。每个线程在进入交换器时呈现某个对象，接收对方的对象。

+ 7. `Exchanger` 的 `exchange(V)` 方法等待另一个线程到达此交换点（除非调用线程被中断），然后将给的对象传递给它，并接收返回的对象。

+ 8. 信号量维护一组许可以限制访问有限资源的线程数量。尝试获取无可用许可的线程将阻塞，直到某些线程释放许可。

+ 9. 信号量的两种类型是计数信号量（当前值加 1）和二值信号量或互斥（当前值只能为 0 或 1）。

+ 10. `Phaser` 是一个更灵活的屏障。像 `CyclicBarrier` 一样，`Phaser` 允许一组线程在屏障等待。

+ 11. `Phaser` 的 `register()` 方法将阶段号返回给到达。如果此值为负，则该 phaser 终止，此时注册将没有影响。该值被称为到达阶段号。

+ 12. 列表 A-7 展示了第 6 章中提到的 PC 应用。

```java
import java.util.concurrent.Semaphore;

public class PC {
    public static void main(String[] args) {
        Shared s = new Shared();
        Semaphore semCon = new Semaphore(0);
        Semaphore semPro = new Semaphore(1);
        new Producer(s, semPro, semCon).start();
        new Consumer(s, semPro, semCon).start();
    }
}

class Shared {
    private char c;

    void setSharedChar(char c) {
        this.c = c;
    }

    char getSharedChar() {
        return c;
    }
}

class Producer extends Thread {
    private final Shared s;
    private final Semaphore semPro, semCon;

    Producer(Shared s, Semaphore semPro, Semaphore semCon) {
        this.s = s;
        this.semPro = semPro;
        this.semCon = semCon;
    }

    @Override
    public void run() {
        for (char ch = 'A'; ch <= 'Z'; ch++) {
            try {
                semPro.acquire();
            } catch (InterruptedException ie) {
            }
            s.setSharedChar(ch);
            System.out.println(ch + " produced by producer.");
            semCon.release();
        }
    }
}

class Consumer extends Thread {
    private final Shared s;
    private final Semaphore semPro, semCon;

    Consumer(Shared s, Semaphore semPro, Semaphore semCon) {
        this.s = s;
        this.semPro = semPro;
        this.semCon = semCon;
    }

    @Override
    public void run() {
        char ch;
        do {
            try {
                semCon.acquire();
            } catch (InterruptedException ie) {
            }
            ch = s.getSharedChar();
            System.out.println(ch + " consumed by consumer.");
            semPro.release();
        } while (ch != 'Z');
    }
}
```

# 第 7 章：锁框架



- 1. 锁（Lock）是实现 `Lock` 接口的类实例，它提供了比 `synchronized` 关键字更广泛的锁操作。Lock 还可以通过关联的 `Condition` 对象支持等待/通知机制。

- 2. Lock 对象相比于线程进入临界区域（由 `synchronized` 关键字控制）时获取的内置锁（intrinsic locks），最大的优势在于它们能够退出获取锁的尝试。

- 3. 答案是正确的：当调用线程未持有锁时，ReentrantLock 的 `unlock()` 方法会抛出 `IllegalMonitorStateException`。

- 4. 你通过调用 Lock 的 `newCondition()` 方法获取一个用于特定 Lock 实例的 `Condition` 实例。

- 5. 答案是错误的：`ReentrantReadWriteLock()` 创建的 ReentrantReadWriteLock 实例没有公平排序策略。

- 6. `StampedLock` 是 JDK 8 引入的，是一种基于能力的锁，具有三种控制读写访问模式。它以类似于 ReentrantReadWriteLock 的方式区分了排斥锁和非排斥锁，但同时也支持乐观读，这是 ReentrantReadWriteLock 不支持的。

- 7. `LockSupport` 的目的是为创建锁和其他同步类提供基本的线程阻塞原语。

- 8. 列表 A-8 展示了第 7 章中 ID 类。

### 列表 A-8. 基于 ReentrantLock 的 ID 生成器

```java
import java.util.concurrent.locks.ReentrantLock;

public class ID {
    private static int counter; // 默认初始化为 0

    private final static ReentrantLock lock = new ReentrantLock();

    public static int getID() {
        lock.lock();
        try {
            int temp = counter + 1;
            try {
                Thread.sleep(1);
            } catch (InterruptedException ie) {
            }
            return counter = temp;
        } finally {
            lock.unlock();
        }
    }
}
```

## 第 8 章：额外的线程安全集合

- 1. 并发集合的两个问题是可能抛出 `ConcurrentModificationException` 对象以及性能低下。在遍历可能在迭代期间被另一个线程修改的集合之前，必须获取锁。如果未获取锁且集合被修改，则极有可能抛出 `ConcurrentModificationException`。此外，当从多个线程频繁访问同步化集合时，性能会受到影响。

- 2. 并发集合（concurrent collection）是存储在 `java.util.concurrent` 包中的具有并发性能且高度可扩展的集合面向类型。

- 3. 弱一致性迭代器（weakly-consistent iterator）具有以下属性的迭代器：

    - 在迭代开始后删除的元素不会被迭代器的 `next()` 方法返回。

    - 在迭代开始后添加的元素可能返回，也可能不返回。

    - 在遍历集合期间，无论对集合进行了什么修改，任何元素都不会被多次返回一次。

- 4. `BlockingQueue` 是 `java.util.Queue` 的子接口，它还支持阻塞操作：在检索元素之前等待队列变为非空，在存储元素之前等待队列有可用空间。

- 5. `ConcurrentMap` 是 `java.util.Map` 的子接口，它声明了额外的 `putIfAbsent()`、`remove()` 和 `replace()` 方法。

- 6. `ArrayBlockingQueue` 是一个由数组支持的有界阻塞队列。`LinkedBlockingQueue` 是基于链式节点的可选边界队列。

- 7. 答案是正确的：面向并发的集合类型是集合框架（Collections Framework）的一部分。

- 8. `ConcurrentHashMap` 的行为类似于 `HashMap`，但设计为可以在没有显式同步的情况下在多线程环境中工作。

- 9. 使用 `ConcurrentHashMap`，你可以调用它的 `putIfAbsent()` 方法来检查映射是否包含特定值，并在该值不存在。

- 10. 原子变量（atomic variable）是支持原子操作的类实例。

- 11. `AtomicInteger` 是一个对 int 提供原子类的类。

- 12. 答案是错误的：`volatile` 不支持原子读-写序列。

- 13. 比较交换（compare-and-swap）指令用于性能提升。

- 14. Fork/Join 框架由特殊的执行器和线程池组成。

- 15. 组成 Fork/Join 的主要类型有 `ForkJoinPool`、`ForkJoinThread`、`RecursiveAction`、`RecursiveTask` 和 `Counted`。

- 16. 要通过 `RecursiveAction` 完成工作，你需要重写它的 `compute()` 方法。

- 17. 完成服务是一种实现，将任务生产与结果消费解耦。

- 18. 你可以调用 `poll()` 方法轮询任务，或使用阻塞 `take()` 方法等待任务完成。

## 附录 A 练习答案

- 19. 你通过 `ExecutorCompletionService<V>` 使用完成服务，它实现了 `CompletionService<V>` 并通过提供的执行器执行任务。

- 20. `int ++counter;` 的原子变量等价实现如下：

  ```java
  AtomicInteger counter = new AtomicInteger(0);
  int total = counter.incrementAndGet();
  ```

  `int counter--;` 的原子变量等价实现如下：

  ```java
  AtomicInteger counter = new AtomicInteger(0);
  int total = counter.getAndDecrement();
  ```

# 附录 B Swing 中的多线程

Swing 是一个用于创建 Java 程序图形界面的平台无关、基于模型视图控制的 GUI 工具包。在本附录中，我探讨了 Swing 的线程架构，然后在使用额外线程时通过 Swing API 避免问题。最后，我展示了一个基于 Swing 的幻灯片应用程序作为附录内容的重要示例，并作为结束本书的一种趣味方式。

> **注意** 我假设你对 Swing API 有一些经验。

## 单线程编程模型

Swing 遵循单线程编程模型。它被设计为单线程，而不是多线程图形工具包已被证明不可避免会导致死锁和竞态条件。要了解更多这些问题，请查看“为什么 Swing 是单线程的？”博客 http://code1.com/java/concurrency/GUI-Applications/why-are-Single-threaded/

用于渲染图形和处理事件的线程被称为事件派发线程（EDT）。EDT 处理来自底层抽象窗口工具包（AWT）队列的事件并调用 GUI 组件（如按钮）事件监听器，这些监听器在此线程上处理事件。组件在 EDT 上重绘自己（响应 paint 方法调用，导致 `paintComponent()`、`paintBorder()` 和 `paintChildren()` 方法调用）。

在使用代码与 EDT 交互时要小心，以确保你的 Swing 应用程序正常运行。有两个规则需要记住：

- 始终在 EDT 上创建 Swing GUI。
- 永远不要延迟 EDT。

Swing 是单线程的，其结果之一是你只能在 EDT（事件分发线程）上创建 Swing 应用程序的 GUI。在任何其他线程上创建此 GUI 都是错误的，包括运行 Java 应用程序 `main()` 方法的默认主线程。

大多数 Swing 对象（例如 `javax.swing.JFrame`，它描述了带有窗口、菜单栏和边框的 GUI 顶层“框架 (frame)”）都不是线程安全的。从多个线程访问这些对象会带来线程干扰和/或不一致性错误的风险：

- **线程干扰（Thread interference）：** 两个线程在操作相同数据时正在执行两个不同的操作。例如，一个线程读取一个 `long` 计数器变量，而另一个线程在更新该变量。由于在 32 位机器上读取或写入一个 `long` 类型需要两次读取/写入访问，可能出现读取线程读取了该变量当前值的部分内容，然后写入线程更新了变量的其余部分，紧接着读取线程又读取了错误的值。

- **内存不一致性错误（Memory inconsistency errors）：** 运行在不同处理器或处理器核心上的两个或多个线程对相同数据拥有不一致的值。例如，在一个处理器上写入或更新一个计数器变量，然后在另一个处理器上写入或读取该变量。然而，由于使用了缓存机制来提高性能，两个线程都没有访问主内存中变量的单份拷贝。每个线程都从本地内存（缓存）访问其各自的变量拷贝。

当 GUI 不在 EDT 上创建时，这些问题是如何发生的呢？John Zakowski 在他的 JavaWorld 文章 [Swing threading-and-the-event-dispatch thread-(www.javaaworld.com/article/2077754/core-java/swing-threading-and-the-event-dispatch-thread) 中演示了这种场景。

Zukowski 提供了一个向框架窗口组件添加容器监听器（container listener）的示例。当组件被添加到框架或从框架中移除时，监听器方法会被调用。他演示了在默认主线程实现框架（realized）之前，在监听器方法中运行 EDT 代码。

注意：被实现（realized）意味着组件的 `paint()` 方法已经过调用，或者可能会被调用。通过在此容器组件上调用 `setVisible(true)`、`show()` 或 `pack()` 中的任意一个，框架窗口会被实现。框架窗口被实现后，它包含的所有组件也随之实现。实现组件的另一种方法是将其添加到已经 set 的容器中。

当 EDT 开始在监听器方法中运行，而默认主线程继续初始化 GUI 时，组件可能由默认主线程创建并被 EDT 访问。EDT 可能会在组件存在之前尝试访问它们；因此这样做可能会导致应用程序崩溃。

即使 GUI 不是在 EDT 上创建的，如果 EDT 在默认主线程创建组件之前尝试访问它们，也可能导致应用程序崩溃。示例 B-1 展示了由于缓存，EDT 在监听器方法中无法访问组件时可能出现的 `NullPointerException` 异常。该示例展示了 Swing 线程中的问题。

### 列表 B-1. Swing 线程问题示例

```java
import java.io.InputStream;
import java.io.IOException;
import java.net.URL;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.JTextField;
import java.awt.BorderLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.EventQueue;

public class ViewPage {
    public static void main(String[] args) {
        Runnable r = () -> {
            final JFrame frame = new JFrame("View Page");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            JPanel panel = new JPanel();
            panel.add(new JLabel("Enter URL"));
            final JTextField txtURL = new JTextField(40);
            panel.add(txtURL);
            frame.getContentPane().add(panel, BorderLayout.NORTH);
            final JTextArea txtHTML = new JTextArea(10, 40);
            frame.getContentPane().add(new JScrollPane(txtHTML), BorderLayout.CENTER);

            ActionListener al = (ae) -> {
                InputStream is = null;
                try {
                    URL url = new URL(txtURL.getText());
                    is = url.openStream();
                    StringBuilder sb = new StringBuilder();
                    int b;
                    while ((b = is.read()) != -1) {
                        sb.append((char) b);
                    }
                    txtHTML.setText(sb.toString());
                } catch (IOException ioe) {
                    txtHTML.setText(ioe.getMessage());
                } finally {
                    txtHTML.setCaretPosition(0);
                    if (is != null) {
                        try {
                            is.close();
                        } catch (IOException ioe) {
                        }
                    }
                }
            };
            txtURL.addActionListener(al);
            frame.pack();
            frame.setVisible(true);
        };
        EventQueue.invokeLater(r);
    }
}
```

列表 B-2 了一个问题，但我们仍然必须防止事件调度线程（EDT）被延迟。我们通过创建一个工作线程来读取页面，并使用 `invokeAndWait()` 在 EDT 上更新可滚动文本区域的页面来解决这个问题。请查看列表 B-3。

### 列表 B-3. 在非延迟 EDT 上构建 HTML 查看器 Swing 应用 GUI

```java
import java.awt.BorderLayout;
import java.awt.Dimension;
import java.awt.EventQueue;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.InputStream;
import java.io.IOException;
import java.lang.reflect.InvocationTargetException;
import java.net.URL;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.JTextField;

public class ViewPage {
    public static void main(String[] args) {
        Runnable r = () -> {
            final JFrame frame = new JFrame("View Page");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            JPanel panel = new JPanel();
            panel.add(new JLabel("Enter URL"));
            final JTextField txtURL = new JTextField(40);
            panel.add(txtURL);
            frame.getContentPane().add(panel, BorderLayout.NORTH);
            final JTextArea txtHTML = new JTextArea(10, 40);
            frame.getContentPane().add(new JScrollPane(txtHTML), BorderLayout.CENTER);

            ActionListener al = (ae) -> {
                new Thread(() -> {
                    InputStream is = null;
                    try {
                        URL url = new URL(txtURL.getText());
                        is = url.openStream();
                        StringBuilder sb = new StringBuilder();
                        int b;
                        while ((b = is.read()) != -1) {
                            sb.append((char) b);
                        }
                        final String content = sb.toString();
                        try {
                            EventQueue.invokeAndWait(() -> txtHTML.setText(content));
                        } catch (InvocationTargetException | InterruptedException e) {
                            e.printStackTrace();
                        }
                    } catch (IOException ioe) {
                        EventQueue.invokeLater(() -> txtHTML.setText(ioe.getMessage()));
                    } finally {
                        EventQueue.invokeLater(() -> txtHTML.setCaretPosition(0));
                        if (is != null) {
                            try {
                                is.close();
                            } catch (IOException ioe) {
                            }
                        }
                    }
                }).start();
            };
            txtURL.addActionListener(al);
            frame.pack();
            frame.setVisible(true);
        };
        EventQueue.invokeLater(r);
    }
}
```



```java
frame.getContentPane().add(txtHTML, BorderLayout.NORTH);

final JTextArea txtHTML = new JTextArea(10, 40);

frame.getContentPane().add(new JScrollPane(txtHTML), BorderLayout.CENTER);

ActionListener al = (ae) -> {

    txtURL.setEnabled(false);

    Runnable worker = () -> {

        InputStream is = null;

        try {

            URL url = new URL(txtURL.getText());

            is = url.openStream();

            final StringBuilder sb = new StringBuilder();

            int b;

            while ((b = is.read()) != -1) {

                sb.append((char)b);

            }

            Runnable r1 = () -> {

                txtHTML.setText(sb.toString());

                txtURL.setEnabled(true);

            };

            EventQueue.invokeAndWait(r1);

        } catch (InterruptedException ae) {

        } catch (InvocationTargetException ite) {

        } catch (final IOException ioe) {

            Runnable r1 = () -> {

                txtHTML.setText(ioe.getMessage());

                txtURL.setEnabled(true);

            };

            try {

                EventQueue.invokeAndWait(r1);

            } catch (InterruptedException ie) {

            } catch (InvocationTargetException ite) {

            }

            finally {

                Runnable r1 = () -> {

                    txtHTML.setCaretPosition(0);

                    txtURL.setEnabled(true);

                };

                try {

                    EventQueue.invokeAndWait(r1);

                } catch (InterruptedException ie) {

                } catch (InvocationTargetException ite) {

                }

            }

        }

        if (is != null)

            try {

                is.close();

            } catch (IOException ioe) {

            }

    };

    new Thread(worker).start();

};

txtURL.addActionListener(al);

frame.pack();

frame.setVisible(true);

};

EventQueue.invokeLater(r);

}
```

# 附录 B Swing 中的多线程

`SwingWorker` 提供了一个抽象类，用于处理耗时任务（如读取 URL 内容），并减少了代码的冗余。你必须继承该类并重写一个或多个方法来完成实际工作。`SwingWorker` 的泛型为 `SwingWorker<T, V>`。参数 T 和 V 分别标识返回类型和中间类型。

`SwingWorker` 还有两个你必须了解的方法。首先，`execute()` 将 `SwingWorker` 对象调度到工作线程上执行。其次，`get()` 在必要时会等待 `doInBackground()` 完成，然后返回最终结果。

> **注意** `SwingWorker` 的 `get()` 方法在尝试获取从 `doInBackground()` 返回的对象时如果发生异常，会抛出一个 `ExecutionException` 实例。它也可能抛出 `InterruptedException`。

列表 B-4 展示了使用 `Worker` 代替 `invokeAndWait()` 的最终 ViewPage 应用的源代码。

```java
{

    private final String url;

    GetHTML(String url) {

        this.url = url;

    }

    @Override

    public StringBuilder doInBackground() {

        StringBuilder sb = new StringBuilder();

        InputStream is = null;

        try {

            URL url = new URL(this.url);

            is = url.openStream();

            int b;

            while ((b = is.read()) != -1) {

                sb.append((char) b);

            }

            return sb;

        } catch (IOException ioe) {

            sb.setLength(0);

            sb.append(ioe.getMessage());

            return sb;

        } finally {

            if (is != null) {

                try {

                    is.close();

                } catch (IOException ioe) {

                }

            }

        }

    }

}
```

# 附录 B Swing 中的线程

```java
@Override

public void done() {

    try {

        StringBuilder sb = get();

        txtHTML.setText(sb.toString());

        txtHTML.setCaretPosition(0);

    } catch (ExecutionException ee) {

        txtHTML.setText(ee.getMessage());

    } catch (InterruptedException ie) {

        txtHTML.setText("Interrupted");

    }

    txtURL.setEnabled(true);

}

new GetHTML(txtURL.getText()).execute();

txtURL.addActionListener(al);

frame.pack();

frame.setVisible(true);

EventQueue.invokeLater(r);
```

这个最终版本的 ViewPage 依赖于 `GetHTML`，它是一个在动作监听器 lambda 表达式体内声明的本地 `SwingWorker` 子类，用于在线程中读取网页（以保持用户界面的响应），并在 EDT（当 Swing 代码可以执行时）使用 HTML 更新用户界面。

当 lambda 表达式运行时（用户在文本框中输入 URL 后按下回车键），它会使用文本框的内容实例化 `GetHTML`（不会从工作线程中直接访问文本框，因为 Swing 是单线程的），并调用 `SwingWorker` 的 `execute()` 方法。

`execute()` 会导致在工作线程上调用 `GetHTML` 重写的 `doInBackground` 方法，该方法向一个 `java.lang.StringBuilder` 对象填充 HTML/错误文本并返回该对象。EDT 会调用重写的 `done()` 方法，该方法通过调用 `SwingWorker` 的 `get()` 方法访问 `StringBuilder` 对象并将这些内容填充到文本区域。

### Timer (计时器)

Swing 提供了 `javax.swing.Timer` 类（作为计时器框架——第4章的简化版本），用于在 EDT 上定期执行 Swing 代码。它在初始延迟后向已注册的监听器触发动作事件，此后反复触发，事件之间由延迟分隔。

调用 `Timer(int delay, ActionListener listener)` 构造函数来创建一个具有初始延迟和事件间隔延迟（毫秒）的计时器，并将初始动作监听器（可能为 null）作为每个延迟发送的事件的目标。

`delay` 值既用作初始延迟也用作事件间隔延迟。你也可以通过调用 `void setInitialDelay(int initialDelay)` 和 `void setDelay(int delay)` 方法分别设置这些值。

- **注意** 使用带有 `false` 参数的调用 Timer 的 `setRepeats(boolean flag)` 方法，以指示计时器仅发送单个动作事件。

调用 `addActionListener(ActionListener listener)` 添加另一个监听器，调用 `removeActionListener(ActionListener listener)` 移除之前注册的动作监听器。调用 `ActionListener[] getActionListeners()` 获取所有注册的监听器。

新创建的计时器处于停止状态。要启动计时器，请调用其 `void start()`。相反，你可以调用 `void stop()` 来终止计时器。你可能还想调用 `boolean isRunning()` 来确定计时器是否正在运行。

列表 B-5 展示了一个 Counter 应用程序的源代码，该程序创建一个计时器通过标签不断显示运行的计数。

### 列表 B-5. 启动与停止计数

```java
import java.awt.EventQueue;

import java.awt.FlowLayout;

import java.awt.event.ActionListener;

import javax.swing.JButton;

import javax.swing.JFrame;

import javax.swing.JLabel;

import javax.swing.JPanel;

import javax.swing.Timer;

public class Counter extends JFrame

{

    int count;

    public Counter(String title)

    {

        super(title);

        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel pnl = new JPanel();

        ((FlowLayout)pnl.getLayout()).setHgap(20);

        final JLabel lblCount = new JLabel("");

        pnl.add(lblCount);

        final JButton btnStartStop = new JButton("Start");

        ActionListener al = (ae) ->

        {

            count++;

            lblCount.setText(count + " ");

        };

        final Timer timer = new Timer(30, al);

        al = (ae) ->

        {

            if (btnStartStop.getText().equals("Start"))

            {

                btnStartStop.setText("Stop");

                timer.stop();

            }

            else

            {

                btnStartStop.setText("Start");

                timer.stop();

            }

        };

        btnStartStop.addActionListener(al);

        pnl.add(btnStartStop);

        setContentPane(pnl);

        setSize(300, 80);

        setVisible(true);

    }

    public static void main(String[] args)

    {

        EventQueue.invokeLater(() -> new Counter("Counter"));

    }

}
```

# 附录 B Swing 中的多线程

```java
@Override

public void paint(Graphics g) {

    int w = getWidth();

    int h = getHeight();

    g.drawImage(bi, Slide.WIDTH <= w ? (w - Slide.WIDTH) / 2 : 0, Slide.HEIGHT <= h ? (h - Slide.HEIGHT) / 2 : 0, null);

}
```

```java
class Slide {

    private static int WIDTH, HEIGHT;

    private static int TEXTBOX_WIDTH, TEXTBOX_HEIGHT, TEXTBOX_X, TEXTBOX_Y;

    private BufferedImage bi;

    private String text;

    private static Font font;

    private Slide(BufferedImage bi, String text) {

        this.bi = bi;

        this.text = text;

        font = new Font("Arial", Font.BOLD, 20);

    }

    static BufferedImage blend(Slide slide1, Slide slide2, float weight) {

        BufferedImage bi1 = slide1.getBufferedImage();
```



```java
BufferedImage bi2 = (slide2 != null) ? slide2.getBufferedImage() : null;

BufferedImage bi3 = new BufferedImage(Slide.WIDTH, Slide.HEIGHT, BufferedImage.TYPE_INT_RGB);

Graphics2D g2d = bi.createGraphics();

g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, weight));

g2d.drawImage(bi1, 0, 0, null);

g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 1.0 - weight));

g2d.drawImage(bi2, 0, 0, null);

g2d.setColor(Color.BLACK);

g2d.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIASING);

g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 0.5f));

g2d.fillRect(TEXTBOX_X, TEXTBOX_Y, TEXTBOX_WIDTH, TEXTBOX_HEIGHT);

g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, weight));

g2d.setColor(Color.WHITE);

g2d.setFont(font);

FontMetrics fm = g2d.getFontMetrics();

g2d.drawString(slide1.getText(), TEXTBOX_X + (TEXTBOX_WIDTH - fm.stringWidth(slide1.getText())) / 2, TEXTBOX_Y + TEXTBOX_HEIGHT / 2 + fm.getHeight() / 4);

g2d.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, 1.0 - weight));

if (slide2 != null) {

    g2d.drawString(slide2.getText(), TEXTBOX_X + (TEXTBOX_WIDTH - fm.stringWidth(slide2.getText())) / 2, TEXTBOX_Y + TEXTBOX_HEIGHT / 2 + fm.getHeight() / 4);

}

g2d.dispose();

return bi3;

}

BufferedImage getBufferedImage() {

    return bi;

}

String getText() {

    return text;

}

static List<Slide> loadSlides(String imagesPath) throws IOException {

    File imagesPath = new File(imagesPath);

    if (!imagesPath.isDirectory()) {

        throw new IOException(imagesPath + " identifies a file");

    }

    List<Slide> slides = new ArrayList<>();

    try (FileReader fr = new FileReader(imagesPath + "/index");

         BufferedReader br = new BufferedReader(fr)) {

        String line;

        while ((line = br.readLine()) != null) {

            String[] parts = line.split(",");

            File file = new File(imagesPath + "/" + parts[0] + ".jpg");

            System.out.println(file);

            BufferedImage bi = ImageIO.read(file);

            if (WIDTH == 0) {

                WIDTH = bi.getWidth();

            }

            HEIGHT = bi.getHeight();

            TEXTBOX_WIDTH = WIDTH / 2 + 10;

            TEXTBOX_HEIGHT = HEIGHT / 10;

            TEXTBOX_Y = HEIGHT - TEXTBOX_HEIGHT - 5;

            TEXTBOX_X = (WIDTH - TEXTBOX_WIDTH) / 2;

            slides.add(new Slide(bi, parts[1]));

        }

    }

    if (slides.size() < 2) {

        throw new IOException("at least one image must be loaded");

    }

    return slides;

}

}

public class SlideShow {

    public static void main(String[] args) throws IOException {

        if (args.length != 1) {

            System.err.println("usage: java SlideShow ssdir");

            return;

        }

        List<Slide> slides = Slide.loadSlides(args[0]);

        final Screen screen = new Screen(Slide.WIDTH, Slide.HEIGHT);

        final Projector p = new Projector(slides, screen);

        Runnable r = () -> {

            final JFrame f = new JFrame("Slide Show");

            WindowAdapter wa = new WindowAdapter() {

                @Override

                public void windowClosing(WindowEvent event) {

                    p.stop();

                    f.dispose();

                }

            };

            f.addWindowListener(wa);

            f.setContentPane(screen);

            f.pack();

            f.setVisible(true);

            p.start();

        };

        EventQueue.invokeLater(r);

    }

}
```

# 附录 B Swing 中的多线程

`blend()` 方法提取与幻灯片相关的图像，并根据 `weight` 决定的量进行混合（`weight` 必须在 0.0 到 1.0 之间）。`weight` 的值越高，`slide1` 的图像对结果图像的贡献越大。混合图像后，`blend()` 在混合后的图像上混合一对文本。`java.awt.AlphaComposite` 类被用于处理每次混合。

我设计 `blend()` 方法是为了处理 `slide2` 为 `null` 的特殊情况。这发生在 `Projector` 的 `start()` 方法开头，它执行 `s.drawImage(slide.get(0), null, 1.0)` 来显示第一张幻灯片——此时还没有过渡。

`loadSlides()` 方法在由方法字符串参数标识的目录中查找名为 `index` 的文件，并根据该文本的内容创建 `Slide` 列表——你可以选择与存储在目录中的图像顺序不同的显示顺序。每行组织为文件名后跟一个逗号，后面是文本描述（例如 `earth, Terzan System`）。指定文件名时，你需要指定文件扩展名；`loadSlides()` 硬编码为 `.jpg`。

`SlideShow` 类声明了一个执行此应用程序的方法。该方法首先验证是否指定标识幻灯片目录（包含 `index` 和 JPEG 文件的目录）的命令行参数。然后调用 `loadSlides()` 从目录加载并索引所有幻灯片。`loadSlides()` 在无法加载图像或图像数量少于 2 时抛出 `java.io.IOException`。毕竟，少于两张图像如何创建幻灯片演示呢？

`main()` 创建了一个用于显示幻灯片图像的 `Screen` 组件。它将每个幻灯片的宽度高度（实际上是每个幻灯片图像的宽度高度）传递给 `Screen` 的构造函数，从而确保屏幕足够显示这些幻灯片。所有幻灯片图像必须具有相同的宽高，尽管我没有在 `loadSlides()` 中强制执行这一要求。

最后一个需要创建的重要模型对象是投影器（projector），`main()` 通过将 `loadSlides()` 返回的 `List<Slide>` 对象和之前创建的 `Screen` 对象传递给 `Projector` 的构造函数完成了此任务。

`main()` 的最后一个任务是在 EDT（事件调度线程）上构建 GUI。这会将内容面板设置为 `Screen` 对象，并调用 `Projector` 的 `void start()` 方法开始幻灯片演示。它还创建了一个窗口监听器，当用户尝试关闭窗口时调用 `Projector` 的 `void stop()` 方法。窗口将被销毁。

`Projector` 负责管理幻灯片。主定时器对象负责将投影器推进到下一张幻灯片，而子定时器对象（每次主定时器触发动作事件时都会创建一个）负责从当前显示的幻灯片图像过渡到下一张图像（通过 `blend()` 帮助）。

每个定时器实例都运行在 EDT 上。重要的是，主定时器在子定时器运行时不要执行定时器任务。如果不遵循这一规则，幻灯片的执行将发生故障。我选择主定时器任务连续执行之间的周期为 3000 毫秒，子定时器任务连续执行之间为 10 毫秒，它运行 100 次，总计约为 1000 毫秒。当子定时器任务完成时，它会停止自己。

如下方式编译列表 B-6：

```bash
javac SlideShow.java
```

假设使用 Windows 操作系统，如下所示运行生成的应用程序：

```bash
java SlideShow ..\ss
```



# 附录 B Swing 中的多线程

最后一个需要创建的重要模型对象是投影器（projector），`main()` 通过将 `loadSlides()` 返回的 `List<Slide>` 对象和之前创建的 `Screen` 对象传递给 `Projector` 的构造函数完成了此任务。

`main()` 的最后一个任务是在 EDT（事件调度线程）上构建 GUI。这会将内容面板设置为 `Screen` 对象，并调用 `Projector` 的 `void start()` 方法开始幻灯片演示。它还创建了一个窗口监听器，当用户尝试关闭窗口时调用 `Projector` 的 `void stop()` 方法。窗口将被销毁。

`Projector` 负责管理幻灯片。主定时器对象负责将投影器推进到下一张幻灯片，而子定时器对象（每次主定时器触发动作事件时都会创建一个）负责从当前显示的幻灯片图像过渡到下一张图像（通过 `blend()` 帮助）。

每个定时器实例都运行在 EDT 上。重要的是，主定时器在子定时器运行时不要执行定时器任务。如果不遵循这一规则，幻灯片的执行将发生故障。我选择主定时器任务连续执行之间的周期为 3000 毫秒，子定时器任务连续执行之间为 10 毫秒，它运行 100 次，总计约为 1000 毫秒。当子定时器任务完成时，它会停止自己。

如下方式编译列表 B-6：

```bash
javac SlideShow.java
```

假设使用 Windows 操作系统，如下所示运行生成的应用程序：

```bash
java SlideShow ..\ss
```

`ss` 标识示例太阳系幻灯片演示（包含在本书的代码中），位于当前目录的父目录。

图 B-3 显示了生成的 GUI。

![](img/ee8e13b7e1a7473b1b247bbdf36a1be7_201_0.png)

**图 B-3.** SlideShow 将幻灯片的文本水平居中在幻灯片的底部附近

# 索引

# A

- `ArrayBlockingQueue`, 127-128
- 子变量, 131
- `AtomicLong`, 132
- 减少竞争技术, 132
- 计数器和序列生成器, 131
- `nextID()`, 131
- 内置锁, 131
- `java.util.concurrent.atomic` 包, 130
- 非阻塞算法, 130
- 同步, 130
- 线程安全操作, 130–131

- 完成服务
- `CSDemo.main()` 方法, 144
- 欧拉数, 142-143
- `ExecutorCompletionService`, 142
- `Future<V>.get()` 方法, 142
- `java.util.concurrent.CompletionService<V>` 接口, 142
- `java.util.concurrent.Executor.poll()` 方法, 142
- `submit()` 方法, 142

- 并发实用类
- 高级结构, 69
- `java.util.concurrent`, 70
- `java.util.concurrent.atomic`, 70, 82, 130
- `java.util.concurrent.locks`, 70, 113
- 低层并发原语, 69
- `nanoTime()`, 70
- 线程池和集合, 70

- 并发集合
- `BlockingQueue`, 126, 166
- `ConcurrentMap`, 126
- `java.util.concurrent` 包, 126
- `synchronized` 包装方法, 125
- 线程安全集合, 126
- 弱一致性迭代器, 126

- `ConcurrentHashMap`, 129–130
- `ConcurrentMap` 子接口, 166
- `Condition` 接口, 112, 164
- 竞争同步, 132

- 倒计数器 (Countdown latch)
- `boolean await(long timeout, TimeUnit unit)`, 83
- `doneSignal.countDown()` 方法, 85–86

# B

- `BlockingQueue` 和 `ArrayBlockingQueue`, 127-128
- 接口, 166
- 生产者-消费者应用, 127
- `put()` 和 `get()` 方法, 128
- 接口, 126

# C

- 缓存变量
- `computePut()`, 23
- 处理器锁缓存, 23

- 比较并交换 (CAS) 原子方法
- `int getValue()`, 133
- 原子级读写序列, 133
- 原子子变量类, 134
- `getID()` 方法, 133–134
- Java 原生接口 (JNI), 133
- `java.util.concurrent.locks.ReentrantLock`, 134

# 索引 (续)

- 倒计数器 (续)
- `java.util.concurrent.CountDownLatch` 类, 83
- `startSignal.await()` 方法, 85
- 触发线程, 84-85
- `void await()`, 83
- `void countDown()`, 83

- 计数信号器, 96

- 循环屏障 (Cyclic barrier)
- `await()`, 91
- `barrierAction`, 86
- `boolean isBroken()`, 87
- 构造函数, 90
- 固定大小分区, 86
- `IllegalArgumentException`, 86
- `await(long timeout, TimeUnit unit)`, 87
- `getWaitingTime()`, 87
- `getParties()`, 87
- `java.util.concurrent.CyclicBarrier` 类, 86
- 并行分解, 87-90
- `void reset()`, 87

# E

- 事件调度线程 (EDT)
- 窗口监听器, 170
- 规则, 169

- 交换器 (Exchanger)
- 缓存变量, 95
- 弱一致性迭代器, 126
- `java.util.concurrent.Exchanger<V>`, 92
- 欧拉数, 142-143
- 交换方法, 92

- 执行器方法, 75
- `IllegalAccessException`, 77
- 接口, 71
- `java.lang.ArithmeticException`, 80
- `java.util.concurrent.BigDecimal` value, 80
- `java.util.concurrent.Executor` 接口, 70
- `java.util.concurrent.ExecutorService` 接口, 71
- `java.util.concurrent.TimeUnit`, 74
- `newThreadPool()` 方法, 79
- `new.lang.Thread`, 70
- `RejectedExecutionException`, 71
- `ScheduledExecutorService` 实现类, 46
- `submit()` 方法, 76
- 任务池, 77

- `ExecutorService`
- 实现类, 72-74, 77
- `Future` 的方法, 75
- `IllegalAccessException`, 77
- 接口, 71
- `java.lang.ArithmeticException`, 80
- `java.util.concurrent.BigDecimal` value, 80
- `java.util.concurrent.Executor` 接口, 70
- `java.util.concurrent.ExecutorService` 接口, 71
- `java.util.concurrent.TimeUnit`, 74
- `newThreadPool()` 方法, 79
- `new.lang.Thread`, 70
- `RejectedExecutionException`, 71
- `ScheduledExecutorService` 实现类, 46
- `submit()` 方法, 76
- 任务池, 77

# D

- 守护线程 (Daemon thread), 1
- 死锁 (Deadlock), 27

# F

- Fork/Join 框架
- 执行器服务和线程池, 135
- `ForkJoinPool`, 141
- `ForkJoinTask`, 141
- `ForkJoinWorker`, 136
- `java.util.concurrent.ForkJoinPool`, 141
- 并行分解, 87-90
- `void reset()`, 87



`ss` 标识示例太阳系幻灯片演示（包含在本书的代码中），位于当前目录的父目录。

图 B-3 显示了生成的 GUI。

![](img/ee8e13b7e1a7473b1b247bbdf36a1be7_201_0.png)

**图 B-3.** SlideShow 将幻灯片的文本水平居中在幻灯片的底部附近

193

# 索引

# A

- `ArrayBlockingQueue`, 127-128
- 原子变量, 131
- `AtomicLong`, 132
- 减少竞争技术, 132
- 计数器和序列生成器, 131
- `nextID()`, 131
- 内置锁, 131
- `java.util.concurrent.atomic` 包, 130
- 非阻塞算法, 130
- 同步, 130
- 线程安全操作, 130–131

- 完成服务
- `CSDemo'main()` 方法, 144
- 欧拉数, 142-143
- `ExecutorCompletionService`, 142
- `Future<V>get()` 方法, 142
- `java.util.concurrent.CompletionService<V>` 接口, 142
- `java.util.concurrent.Executorpoll()` 方法, 142
- `submit()` 方法, 142
- 并发实用类
- 高级结构, 69
- `java.util.concurrent`, 70
- `java.util.concurrent.atomic`, 70, 82, 130
- `java.util.concurrent.locks`, 70, 113
- 低层并发原语, 69
- `nanoTime()`, 70
- 线程池和集合, 70
- 并发集合
- `BlockingQueue`, 126, 166
- `ConcurrentMap`, 126
- `java.util.concurrent.package`, 126
- `synchronized` 包装方法, 125
- 线程安全集合, 126
- 弱一致性迭代器, 126
- `ConcurrentHashMap`, 129–130
- `ConcurrentMap` 子接口, 166
- `Condition` 接口, 112, 164
- 竞争同步, 132
- 倒计数器 (Countdown latch)
- `boolean await(long timeout, TimeUnit unit)`, 83
- `doneSignal's countDown()` 方法, 85–86

# B

- `BlockingQueue` 和 `ArrayBlockingQueue`, 127-128
- 接口, 166
- 生产者-消费者应用, 127
- `put()` 和 `get()` 方法, 128
- 接口, 126

# C

- 缓存变量
- `computePut()`, 23
- 处理器锁缓存, 23
- 比较并交换 (CAS) 原子方法
- `int getValue()`, 133
- 原子级读写序列, 133
- 原子变量类, 134
- `getID()` 方法, 133–134
- Java 原生接口 [JNI], 133
- `java.util.concurrent.locks.ReentrantLock`, 134

# 索引

- 倒计数器 (续)
- `java.util.concurrent.CountDownLatch` 类, 83
- `startSignal's await` 方法, 85
- 触发线程, 84-85
- `void await()`, 83
- `void countDown()`, 83
- 计数信号器, 96
- 循环屏障 (Cyclic barrier)
- `await()`, 91
- `barrierAction`, 86
- `boolean is`, 87
- 构造函数, 90
- 固定大小分区, 86
- `IllegalArgumentException`, 86
- `await(long timeout, TimeUnit unit)`, 87
- `getWaitingTime()`, 87
- `getParties()`, 87
- `java.util.concurrent.CyclicBarrier` 类, 86
- 并行分解, 87-90
- `void reset()`, 87
- `ExecutorService`
- 实现类, 72-74, 77
- `future's` 方法, 75
- `IllegalAccessException`, 77
- 接口, 71
- `java.lang.ArithmeticException`, 80
- `java.util.concurrent.BigDecimal value`, 80
- `java.util.concurrent.Executor` 接口, 70
- `java.util.concurrent.ExecutorService` 接口, 71
- `java.util.concurrent.TimeUnit`, 74
- `newThreadPool()` 方法, 79
- `new.lang.Thread`, 70
- `RejectedExecutionException`, 71
- `ScheduledExecutorService` 实现类, 46
- `submit()` 方法, 76
- 任务池, 77

# D

- 守护线程 (Daemon thread), 1
- 死锁 (Deadlock), 27

# F

- Fork/Join 框架
- 执行器服务和线程池, 135
- `ForkJoinPool`, 141
- `ForkJoinTask`, 141
- `ForkJoinWorker`, 136
- `java.util.concurrent.ForkJoinPool`, 141
- 并行分解, 87-90
- `void reset()`, 87

# E

- 事件调度线程 (EDT)
- 窗口监听器, 170
- 规则, 169
- 交换器 (Exchanger)
- 缓存变量, 95
- 弱一致性迭代器, 126
- `java.util.concurrent.Exchanger<V>`, 92
- 欧拉数, 142-143
- 交换方法, 92
- 执行器方法, 75
- `IllegalAccessException`, 77
- 接口, 71
- `java.lang.ArithmeticException`, 80
- `java.util.concurrent.BigDecimal value`, 80

*(注：由于原始文本中存在大量重复，以上翻译已根据逻辑结构进行了去重处理，以确保输出文档的专业性和可读性。)*

# T, U

- 任务执行线程, 58
- 存活/死亡状态，5, 9
- 调用 `start()`, 8
- 命令行, 9
- 执行, 5
- 反馈队列, 6
- Java 应用, 3
- 名称（赋值）, 5
- 幂级, 13
- 抢占式调度, 6
- 处理器/核心, 6
- `Runnable` 接口, 3
- 调度器, 6
- `setPriority(int priority)` 方法, 7
- `sleep`, 16
- 栈, 3
- `start method()`, 5
- Windows 7 操作系统, 10

### 线程能力
- 局部变量。线程本地变量 (Thread-Local variables)
- 定时器：见 Thread
- 定时框架, 58-60

### TimerTask
- `boolean cancel()`, 64
- `long scheduledExecutionTime()`, 65

### Thread 类
- 中断机制, 10
- 信号量, 162
- `sleep` 方法, 152

### 线程组
- `activeCount()`, 52
- `enumerate()` 方法, 52
- 处理异常, 52
- `int activeCount()` 方法, 52
- `java.lang.ArithmeticException` 对象, 52
- `java.lang.ThreadGroup` 类, 51
- JDK 文档, 51
- JVM, 53
- `setDefaultUncaughtExceptionHandler()` 方法, 54
- `setUncaughtExceptionHandler()`, 53-54
- `static void setDefaultUncaughtExceptionHandler_Handler`, 53
- 对象的 `uncaughtException()` 方法, 53
- `uncaughtException()`, 53
- 未捕获异常处理器, 54
- `void resume()`, 51
- `void stop()`, 51
- `void suspend()`, 51

- `Thread.interrupt()`, 12

### 线程本地变量 (Thread-Local variables)
- 构造函数与方法类, 55
- `final` 类字段, 58
- `InheritableThreadLocal`, 57
- `initialValue()` 的值, 57
- `java.lang.Thread` 类, 55
- 多线程变量, 55
- 父线程到子线程, 57
- `TValue(TParent)`, 57
- `ThreadLocal<T>`, 55
- 用户 ID, 56
- 线程池, 77
- 线程安全计数器, 133
- `Thread.getState()` 方法, 6

### Timer 构造函数
- `Timer()`, 61
- `Timer(boolean Daemon)`, 61
- `Timer(String name)`, 61
- `Timer(String name, boolean isDaemon)`, 61

### 方法
- `void cancel()`, 61
- `int purge()`, 61
- `void scheduleAtFixedRate(Timer task, Date first, long period)`, 63
- `void scheduleAtFixedRate(Timer task, long delay, long period)`, 52
- `void schedule(Timer task, Date first, long period)`, 62
- `void schedule(Timer task, long delay)`, 62
- `void schedule(Timer task, long delay, long period)`, 63
- 比例尺, 61
- `stop()` 方法, 64
- 任务执行线程, 64

### 基于 Timer 的幻灯片
- `blend()` 方法, 19
- 定义，幻灯片, 185
- 描述, 185–187, 189–190
- `loadSlides()` 方法, 191
- 输出视图, 193
- 投影仪, 191-192
- 屏幕, 191
- 幻灯片, 191
- Timer框架
- 闹钟任务, 58
- 当前毫秒值, 60
- Java 1.3, 58
- 单次执行, 58-59
- `schedule()` 方法, 59-60
- `System.exit(0)`, 59
- 任务执行线程, 58
- 任务调度, 58
- `TimerTask` 匿名子类, 60
- `Timer` 任务, 64

# V

- `void join()`, 13
- `void join(long millis, int nanos)`, 13
- `Volatile` 关键字, 30

# W, X, Y, Z

- 等待-通知 API
- `void notify()`, 40
- `void notifyAll()`, 40
- `void wait()`, 39
- `void wait(long timeout)`, 39
- `void wait(long timeout, int nanos)`, 39
- 基于 Windows NT 的操作系统, 6
- 工作线程, 12
