

# Java 并发、实时与分布式编程：线程、RTSJ 与 RMI（计算机科学聚焦）

![封面](img/cover.jpg)

# 引言

本书是实时和分布式并发计算的介绍，使用 `Java` 面向对象语言作为描述算法的辅助工具。它特别描述了 `Java` 中线程之间的同步机制（协作与竞争）以及数据共享机制（内部类、静态类型变量）。随后，我们讨论了 `Java` 在实时应用中的使用。随之，书中还介绍了 `RTSJ`（Java 实时规范）。最后，书中还包含了对分布式计算的介绍。我们特别关注使用 `TCP Sockets` 的低级通信以及使用 `Java RMI`（远程方法调用）中间件的高级通信。书中还包含一个附录，其中包含与本书主题相关的实际应用练习。掌握 `Java` 语言知识是正确理解本书的前提。

# 1 Java 线程简介

## 1.1 进程与线程

操作系统负责为进程分配必要的资源（内存、处理时间、输入/输出），并确保它们之间互不干扰（隔离）[TAN 01]。

这一原理在以下示例中得到了说明，在两个不同的类中定义了变量 `a`。当执行这两个类时，为该变量分配的两个内存区域完全隔离的。

![image](img/fig1-1.jpg)

**图 1.1.** 进程间的隔离

大多数操作系统提供了以下两者的区分：

* 重量级进程：据推彼此之间是完全分离的。

* 轻量级进程（线程）：共享同一个内存空间（以及其他资源）。

定义 1.– 线程是一段能够与其他进程并行执行的代码流。线程并非同时执行，而是使用共享时间，这就是为什么线程始终给其他线程执行的机会至关重要。

下面的图表显示了四个不同线程的执行时间和延迟时间。

![image](img/fig1-2.jpg)

**图 1.2.** 四个不同线程的执行时间和延迟时间

## 1.2 并发计算

并发编程语言必须允许允许：

* 创建线程；

* 线程之间共享数据；

* 线程间的同步：根据以下两个模型控制任务执行顺序：

    * 竞争同步：当多个线程使用同一个资源时。此时，必须有一套互斥机制以避免进程相互干扰。

    * 协作同步：当一个线程等待另一个线程执行完毕后才开始自己的执行时。

## 1.3 线程创建

在 `Java` 中创建线程有两种方式：

* 继承自 `java.lang.Thread` 的类：

    * `java.lang.Thread` 实现了 `Runnable` 类。

    * `Thread` 扩展 `Object` 并实现了 `Runnable` 公共类。

    * `Thread` 类必须实现 `run()` 方法。

    * 子类继承 `run()` 方法。

* 实现 `Runnable` 接口的类：

    * 该类必须实现 `run()` 方法。

现在问题出现了：我们应该选择哪种方案？

* 方法 1：子类 `Thread`：

    * 当对一个不继承其他类的类（自治类）进行并行化时。

    * 注意：`java` 中的简单继承。

    * 使用 `extends Thread` 或 `implements Runnable` 均可。

* 方法 2：实现 `Runnable`：

    * 当强制要求使用父类时。

    * 示例，涉及 applet 的情况：

      `public class MyThreadApplet extends Applet implements Runnable { }`

    * 仅实现 `Runnable` 是有效的。

让我们来看代码：

* 方法 1：子类 `Thread`

```
class A extends Thread {
A ( ) {…} // 构造函数
…
public void run ( ) {
… // Thread 执行的内容
}
}
A p1 = new A( ); // 创建线程 p1
p1.start(); // 启动线程并执行 p1.run()
```

* 方法 2：实现 `Runnable` 的类

```
class B implements Runnable {
B ( ) { …} // 构造函数
…
public void run() {
… // Thread 执行的内容
}
}
B p = new B( );
Thread p2 = new Thread(p);
…
p2.start(); // 启动线程并执行 p.run()
```

## 1.4 线程类型

存在两种类型的线程：

* 用户线程：这种类型线程的活动是有时间限制的，意味着其场景是一个一定时间后结束的过程。只要有用户线程在执行，`JVM` 就会一直运行。

* 守护线程：只要程序运行，就在后台执行的线程。守护线程仅用于服务用户线程。如果只剩下守护线程，`JVM` 将停止。

示例：编辑器中的语法高亮、垃圾回收器 (`DestroyJavaVM`) 等等。

* `Thread` 类中的 `public final boolean isDaemon()` 用于确定线程类型。

* `Thread` 类的 `public final void setDaemon (boolean)` 表示该线程将是为守护线程（默认为用户线程）。

* 它必须在使用 `start()` 命令启动线程之前调用。

* 在构造函数中使用 `setDaemon`。

示例：在后台运行的时钟线程。

```
Clock class extends Thread {
public () { setDaemon(true); }
public void run () {
while (true) {
try{Thread.sleep(3000);} catch (InterruptedException e) {}
System.out.println("time");
}
}
public static void main(String args[]){
Clock p1 = new Clock();
p1.start();
}
```

## 1.5 单任务与多任务

为了说明多任务，让我们先从介绍单任务开始。在下面的示例中，`Parrot0.java` 与主程序 `ChatAndParrot0.java` 以单任务对话：

```
class ChatAndParrot0 {
public static void main(String[]) {
Parrot0 parrot = new Parrot0("coco",4);
blabla();
parrot.run();
try {Thread.sleep(1000);}
} catch (InterruptedException e) {
System.out.println(e.getMessage())); System.exit(1); }
}
private static void blabla() {
System.out.println("blabla");
}

class Parrot0 {
private String cri = null;
private int fois = 0;
public Parrot0 (String s, int i) {
cri = s;
fois = i;
}
public void run () {
for (int n=0; n<fois; n++) {
try {Thread.sleep(1000);} catch (InterruptedException e) {System.exit(1); }
System.out.println(cri);
}
}
```

执行上述代码的结果如下：

* blabla

* blabla

* coco

* coco

* coco

* blabla

* blabla

没什么特别的，主程序说话，传递给鹦的 run，执行以三个 blabla 结束。要执行多任务，需要对上述代码进行修改。我们将通过不同的方式来实现。

* 扩展 `Thread` 类：

```
class ChatAndParrot2{
public static void main(String args[]) {
Parrot2 parrot = new Parrot2("coco",10);
parrot.start();
for (int n=0; n<10; n++) {
try {Thread.sleep(1000);}
catch (InterruptedException e) { }
blabla();
}
}
private static void blabla() {
System.out.println("blabla");
}

class Parrot2 extends Thread{
private String cri = null;
private int fois = 0;
public Parrot2 (String s, int i) {
cri = s;
fois = i;
}
public void run ( ){
for (int n=0; n<fois; n++) {
try {Thread.sleep(1000);}
catch (InterruptedException e) { }
System.out.println(cri);
}
}
}
```

执行之前的代码结果如下：

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

* – 实现 `Runnable` 接口：

```java
class ChatAndLaunchTheParrot1{
  public static void main(String args[]) {
Parrot1 objectParrot = new Parrot1 ("coco",10);
  Thread ThreadParrot = new Thread (objectParrot);
  ThreadParrot.start();
  for (int n=0; n<10; n++) {
   try {
     Thread.sleep(1000);
   }
   catch(InterruptedException e) { }
   blabla();
  }
  }
  private static void blabla() {
  System.out.println("blabla");
  }
}
class Parrot1 implements Runnable {
  private String cri = null;
  private int fois = 0;
  public Parrot1 (String s, int i) {
  cri = s;
  fois = i;
  }
  public void run (){
  for (int n=0; n<fois; n++) {
   try {
     Thread.sleep(1000);
   }
   catch(InterruptedException e) { }
   System.out.println (cri);
  }
  }
}
```

执行之前的代码结果如下：

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

blabla

coco

coco

* – `run()` 是需要重定义的方法，用以放置 `Thread` 的功能。

* – `start()` 是一个允许 `Thread` 初始化并因此执行 `run` 的方法。它做的只是初始化 `Thread` 并（不阻塞调用线程 `Thread`）不等待 `run` 执行完毕。

* – 它立即返回到调用线程 `Thread` 的执行。`Thread` 的 `run` 方法与其他 `Threads` 同时执行（多任务）。

* – `start()` 允许 `Thread` 开始，但并不一定立即。下面的示例模拟了使用线程的竞赛。该想法是模拟两个名为 `Jean` 和 `Paul` 的人之间的 1000 米赛。由于需要让他们并发运行，因此每一个人将由一个 `thread` 来接。

以下程序创建了一个继承 `Thread` 的通用 `Runner` 类。

```java
class Runner extends Thread {
public Runner (String str) {
 super(str);
}
public void run() {
  // Value i 在通过第 n 个百米时增加
  for (int i =1; i<=10; i++) {
System.out.println(i*100 + " m : " + getName());
 try {
sleep((int)(Math.random() * 1000));
  } catch (InterruptedException e) {}
  } // end for
  System.out.println( getName()+ " finishes ! ");
}// end run
} // end class
```

测试类 `Race` 负责创建 `Runner` 实例并使用 `start()` 在比赛中启动它们。

```java
class Race {
  public static void main (String[] args) {
 System.out.println("Passing: ");
 Runner Jean = new Runner ("Jean");
 Runner Paul = new Runner ("Paul");
 Jean.start();
 Paul.start();
  }
}
```

执行此代码结果如下：

Passing:

100 m : Jean

100 m : Paul

200 m : Jean

200 m : Paul

300 m : Paul

300 m : Jean

400 m : Jean

500 m : Jean

600 m : Jean

400 m : Paul

700 m : Jean

500 m : Paul

600 m : Paul

800 m : Jean

900 m : Jean

1000 m : Jean

700 m : Paul

Jean finishes!

800 m : Paul

900 m : Paul

1000 m : Paul

Paul finishes!

## 1.6 线程的不同状态

线程可以处于以下四种状态之一：

* – 新（New）：包括从创建（通过构造函数）一直到调用其 `start()` 方法之间的所有时刻。

* – 可运行（Runnable）：在调用 `start` 方法之后立即。

* – 阻塞（Blocked）：代表线程等待的时刻，例如当它被 `sleep(long)` 方法挂起时，该方法会暂停线程在指定时间内执行。

* – 终止（Terminated）：当其 `run()` 方法结束时。

线程的状态可以通过调用其 `getState()` 方法来指定。

## 1.7 线程的生命周期

线程的生命周期说明它可以：

* – 新（New）：包括从创建（通过构造函数）一直到调用其 `start()` 方法之间的所有时刻。

* – 可运行（Runnable）：在调用 `start` 方法之后立即。

* – 阻塞（Blocked）：代表线程等待的时刻，例如当它被 `sleep(long)` 方法挂起时，该方法会暂停线程在指定时间内执行。

* – 终止（Terminated）：当其 `run()` 方法结束时。

线程的状态可以通过调用其 `getState()` 方法来指定。

```java
public class InfernalRace1 {
  public static void main(String[] args){
  Runner A = new Runner("A");
  Runner B = new Runner("B");
  A.start();
  B.start();
} // end main
} // end class InfernalRace1

class Runner extends Thread {
 String nom;
 public Runner(String name) {
  super(name);
  this.name = name;
}
  public void run() {
        long PedalStroke = 0;
    while (PedalStroke < 5000000) {
      PedalStroke++;
      if ((PedalStroke % 500000) == 0) {
System.out.println("Runner " + name + " performs " + PedalStroke + " pedal strokes.");
        } // end if
      } // end while
}// end run
}// end class Runner
```

### 执行：

Runner A 执行了 500000 次踏踏。

Runner B 执行了 500000 次踏踏。

Runner B 执行了 1000000 次踏踏。

Runner A 执行了 1000000 次踏踏。

Runner B 执行了 1500000 次踏踏。

Runner A 执行了 1500000 次踏踏。

Runner A 执行了 2000000 次踏踏。

Runner B 执行了 2000000 次踏踏。




Runner A 执行了 2500000 次踏踏。

Runner B 执行了 2500000 次踏踏。

Runner A 执行了 3000000 次踏踏。

Runner B 执行了 3000000 次踏踏。

Runner A 执行了 3500000 次踏踏。

Runner B 执行了 3500000 次踏踏。

Runner A 执行了 4000000 次踏踏。

Runner B 执行了 4000000 次踏踏。

Runner A 执行了 4500000 次踏踏。

Runner B 执行了 4500000 次踏踏。

Runner A 执行了 5000000 次踏踏。

Runner B 执行了 5000000 次踏踏。

**结论。** Java 并不要求系统进行“时间分片”：即给具有相同优先级的线程分配相同的时间。

### 1.8.3 线程之间的优先级

`setPriority` 方法设置不同线程之间的优先级级别。该值必须在最小值 `MIN_PRIORITY` 和最大值 `MAX_PRIORITY` 之间。

以下代码说明了线程之间优先级的的作用：

```java
public class InfernalRace2 {
  public static void main(String[] args) {
  Runner A = new Runner("A"); Runner B = new Runner("B");
A.setPriority(Thread.MAX_PRIORITY);
B.setPriority(Thread.MIN_PRIORITY);
System.out.println("Thread Runner " + A.name + " has priority = " + A.getPriority());
System.out.println("Thread Runner " + B.name + " has priority = " + B.getPriority());
  A.start(); B.start();
  }
}
class Runner extends Thread {
 String name
 public Runner(String name) {
  super(name);
  this.name = name;
 }
  public void run() {
  long PedalStroke = 0;
  while (PedalStroke < 5000000) {
    PedalStroke++;
    if ((PedalStroke % 500000) == 0) {
      System.out.println("Runner " + name + " performs " +
PedalStroke + " pedal strokes.");
    }
}
}
}
```

### 执行：

* Thread Runner A 的优先级 = 10

* Thread Runner B 的优先级 = 1

* Runner A 执行了 500000 次踏踏。

* Runner A 执行了 1000000 次踏踏。

* Runner A 执行了 1500000 次踏踏。

* Runner A 执行了 2000000 次踏踏。

* Runner A 执行了 2500000 次踏踏。

* Runner A 执行了 3000000 次踏踏。

* Runner A 执行了 3500000 次踏踏。

* Runner A 执行了 4000000 次踏踏。

* Runner A 执行了 4500000 次踏踏。

* Runner A 执行了 5000000 次踏踏。

* Runner B 执行了 500000 次踏踏。

* Runner B 执行了 1000000 次踏踏。

* Runner B 执行了 1500000 次踏踏。

* Runner B 执行了 2000000 次踏踏。

* Runner B 执行了 2500000 次踏踏。

* Runner B 执行了 3000000 次踏踏。

* Runner B 执行了 3500000 次踏踏。

* Runner B 执行了 4000000 次踏踏。

* Runner B 执行了 4500000 次踏踏。

* Runner B 执行了 5000000 次踏踏。

Thread A 先访问了 CPU，因为它具有最高优先级。Thread B 在最后执行，因为它具有最低优先级。优先级允许我们定义线程之间的执行顺序。

* 线程之间的优先级：方法 `setPriority(int)`。

* 线程的优先级范围在 1 到 10 之间。

* 使用三个常量表示界限值。

* 值越高，线程访问处理器的优先级越高。

* `MIN_PRIORITY`：最低优先级 (1)。

* `NORM_PRIORITY`：普通优先级 (5)。

* `MAX_PRIORITY`：最高优先级 (10)。

* 新线程默认分配为普通优先级。

## 1.9 编写任务：Timer 和 TimerTask

在接下来的章节中，我们希望在初始延迟后程序化任务（例如在特定时间后启动的情况），或者在一定的延迟后周期性地执行任务（软件情况）。

### 1.9.1 通过指定初始延迟

以下代码在 4 秒后启动一次任务。

```java
import java.util.Scanner;
import java.util.TimerTask;
import java.util.Timer;
class InitiateTheParrot11{
public static void main(String args[]) {
  Parrot11 parrot = new Parrot11("coco", 3);
  Timer timer = new Timer();
  timer.schedule(parrot, 4000);
  String response="yes";
  do {
   System.out.println("blabla");
   System.out.println("blabla");
   System.out.println("would you like the parrot to continue? (y/n)");
   response =new Scanner(System.in).nextLine();
  } while (response.equals("y"));
  timer.cancel();
 }

import java.util.TimerTask;
class Parrot11 extends TimerTask {
 private String cri = null;
 private int fois = 0;
 public Parrot11(String s, int i) {
  cri = s;
  fois = i;
 }
 public void repeter() {
  System.out.println(cri);
 }
 public void run() {
  for (int i = 0; i < fois; i++) {
    repeter();
  }
}
```

### 执行：

blabla

blabla

would you like the parrot to continue? (y/n)

y

blabla

blabla

would you like the parrot to continue? (y/n)

n

`TimerTask` 的定义如下：

* `public abstract class TimerTask implements Runnable`。

* `TimerTask` 是一个实现了 `Runnable` 的抽象类，我们需要继承 `TimerTask` 类并重写 `run()` 方法来编写要执行的任务。

* `run()` 是 `TimerTask` 中唯一的抽象方法。

* `Timer` 开始任务的执行。

* `Timer` 对应一个顺序执行任务的线程。

* `schedule(task, long milliseconds)` 通过指定初始延迟来安排任务。

* `cancel()` 方法停止 `Timer` 的调度。

### 1.9.2 带有初始延迟和周期性

```java
import java.util.Scanner;
import java.util.TimerTask;
import java.util.Timer;
class InitializeTheParrot11{
public static void main(String args[]) {
  Parrot11 parrot = new Parrot11("coco", 3);
  Timer timer = new Timer();
  timer.schedule(parrot, 3000, 2000);
  String response="yes";
  do {
   System.out.println("blabla");
   System.out.println("blabla");
   System.out.println("would you like the parrot to continue? (y/n)");
   response =new Scanner(System.in).nextLine();
  } while (response.equals("y"));
  timer.cancel();
 }
}

import java.util.TimerTask;
class Parrot11 extends TimerTask {
 private String cri = null;
 private int fois = 0;
 public Parrot11(String s, int i) {
  cri = s;
  fois = i;
 }
 public void repeter() {
  System.out.println(cri);
 }
 public void run() {
  for (int i = 0; i < fois; i++) {
    repeter();
  }
 }
}
```

`schedule(task, long delay, long period)` 在延迟后安排任务进行周期性执行：时间以毫秒为单位。

### 执行：

blabla

blabla

would you like the parrot to continue? (y/n)

y

coco

coco

coco

coco

coco

ncoco coco

任务在 3 秒后启动，每隔 2 秒周期执行一次。

在下面的示例中，有两个写入者（`EcrivainA` 和 `EcrivainB`）：其中一个会写 `ABC` 10 次，另一个会写 `XYZ` 10 次。每个单词（`ABC` 或 `XYZ`）都将逐字母地写入，并在每个单词的最后一个字母后换行。

以下代码代表了这种场景：¹

![images](img/f0027-01.jpg)

执行结果：

AXBYC

ABZ

XC

AYZ

XBC

AYBC

AZ

XBC

AYBC

AZ

XBC

ABYZ

XC

AYBC

AZ

XBC

Ecrivain de ABC a fini

YZ

XYZ

XYZ

XYZ

Ecrivain de XYZ a fini

两个写入者之间存在并发，这就是我们获得上述执行结果的原因。使用 `Thread` 类的 `join()` 方法，我们可以同步这两个线程。`EcrivainB` 将在 `EcrivainA` 后启动（见后续 `Prog55.java`）。

`join()` 之后的代码将在 `join()` 之前的代码执行完毕后执行。

这种同步被称为“终止同步”。

```java
public class Prog55 {
  public static void main (String argv[]) {
  Ecrivain EcrivainA, EcrivainB;
  EcrivainA = new Ecrivain ("ABC");
  EcrivainB = new Ecrivain ("XYZ");
  EcrivainA.start();
  try {
    EcrivainA.join();
  }
  catch(InterruptedException e) {
    System.out.println(e.getMessage());
    System.exit(1);
  }
  EcrivainB.start();
  }
}
```

执行结果：

ABC

ABC

ABC

ABC

ABC

ABC

ABC

ABC

ABC

ABC

Ecrivain de ABC a fini

XYZ

XYZ

XYZ

XYZ

XYZ

XYZ

XYZ

XYZ

XYZ

XYZ

Ecrivain de XYZ a fini

## 2.2. 互斥中的资源：synchronized 修饰符

选取以下代码：`print` 方法逐字母显示单词，并在最后一个字母处换行。写入者通过一个打印机进行写入。

两个写入者现在都在访问同一个打印机。它们都在“挤占”打印机的 `text` 变量（`imprimeur*`）。整个内容仍然不可读（见下文执行结果）。

![images](img/f0030-01.jpg)

执行结果：

AXYYZ

Z

AXYYZ

Z

AXYYZ

AC

XYYZ

Z

XABBC

C

AXYYZ

Z

AXYYZ

Z

XABBC

C

XABBC

C

XABBC

C

Ecrivain de XYZ a fini

C

Ecrivain de ABC a fini

使用 `synchronized` 是解决这个问题的必不可少的，如下代码所示：

![images](img/f0032-01.jpg)

`synchronized` 在 `print` 方法上定义了一个锁或互斥：一次最多有一个线程可以执行该方法。

这种新的执行结果如下：

执行结果：

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XYZ

ABC

XEcrivain de ABC a fini

YZ

Ecrivain de XYZ a fini

写入者在执行方法时拥有该方法的锁。锁将连接到下一次迭代，因此第二个写入者将接管显示它的文本，以此类直到执行结束。

## 2.3. 共享变量：内部类

在下文中，我们将讨论线程之间的变量共享。以下代码展示了一个使用场景：

![images](img/f0033-01.jpg)

`Perroquet20` 类位于 `PerroquetsMatheux20` 类内部，使用 `join` 方法是为了避免在两个线程终止之前显示计数器的值。

由于 Java 的可见性规则，变量 `compteur`（计数器）对于 `Perroquet20` 类可见/可用，因此对于两个线程对象 `perroquetA` 和 `perroquetB` 均可见；然而，`Perroquet20` 的实例变量 `cri` 和 `fois`（叫声和次数）的数量与 `Perroquet20` 的实例数量相同。因此，两个线程访问的是共享/公共变量空间。

这与进程不同，每个进程都有自己清晰勾勒的工作空间，与其他进程隔离。

执行结果：

coco 1

bonjour 2

bonjour 3

coco 4

bonjour 5

coco 6

bonjour 7

bonjour 8

bonjour 9

coco 10

bonjour 11

coco 12

bonjour 13

coco 14

coco 15

bonjour 16

coco 17

bonjour 18

coco 19

coco 20

compteur = 21

## 2.4. 互斥的问题

为了说明互斥的问题，我们将位于 `Perroquet20` 类中的 `counter++` 令替换为其等效操作：`value = counter + 1` 和 `counter = value`（`valeur*`）。

两个鹦鹉（`perroquet`）线程交替工作：一个线程在执行其 `repeter` 方法途中可能会暂停，以便线程控制器允许另一个线程执行（在 `Perroquet21` 类中的两个新指令之间睡眠）。

![images](img/f0035-01.jpg)

执行结果：

coco 1

bonjour 1

coco 2

coco 3

bonjour 3

coco 4

bonjour 4

coco 5

bonjour 5

coco 6

bonjour 7

coco 7

bonjour 8

coco 8

bonjour 9

coco 9

coco 10

bonjour 10

bonjour 11

`counter` 是共享的，但 `value` 对于每个线程是不同的。

## 2.5. 同步块

在下文中，我们将讨论线程之间的变量共享。以下代码展示了一个使用场景：

![images](img/f0033-01.jpg)

（注：此处由于原文文本存在大量重复和混乱，已根据逻辑结构进行整合翻译）

![images](img/f0041-01.jpg)

执行结果如下图所示。

`Plus1` 是一个使用互斥的方法，它为每个拥有该方法锁的线程将 `val` 增加一个单位。

![images](img/f0042-01.jpg)

*   – 在 Java 中，每个对象都拥有一个监视器（monitor），它可以保护临界区域。它确保只有一个线程线程可以执行由监视器保护的临界区域，

*   – `synchronized (object) { instr }` 与对象关联监视器。

*   – `synchronized void Method(){…}` 与方法关联监视器。

*   – 在执行同步块时，该对象会被锁定。



在 Java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。中，每个对象还拥有一个等待队列。

![images](img/f0043-01.jpg)

## 2.7 共享变量：类变量

在接下来的章节中，我们将展示一个线程协作的示例（老师与学生）。我们有一位老师正在教学生新单词。

学生必须重复每个单词三次，甚至更多。

![image](img/fig2-3.jpg)

**图 2.3.** 消费者/生产者示例。该图的彩色版本，请访问 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)

该示例的简单代码如下：

![images](img/f0044-01.jpg)

执行：

```
nouveau mot pour perroquet ? (sinon non)
bla
nouveau mot pour perroquet? (sinon non)
coco bla
coco bla
coco bla
jaco bla
jaco bla
jaco bla
blu
nouveau mot pour perroquet ? (sinon non)
coco blu
coco blu
coco blu
blo
coco blu
coco blu
coco blu
coco blu
coco blu
coco blu
nouveau mot pour perroquet ? (sinon non)
jaco blo
jaco blo
jaco blo
jaco blo
jaco blo
…..
```

一个静态变量`mot`（称为类变量）被两个鹦鹉线程共享，它们必须学习它然后重复它。之后，主线程进入另一个单词（`mot`）。

起初，他们必须通过循环等待第一个单词，如果教授提供新单词太快，两只鹦鹉可能会“跳过”一些！

目标：避免教授和鹦鹉学生之间存在等待机制：学生等待新单词（*nouveau mot*）来学习，教授在教单词时，必须等待学生有时间学习并重复它，然后再教下一个新单词。

## 2.8 线程间的同步

### 2.8.1 Wait 和 notifyAll

在接下来的代码中，我们创建了一个名为`attheboard`的对象，供生产者和消费者共享。该对象必须有两个方法：第一个由消费者使用（`learn`），第二个由生产者使用（`teach`）。

![images](img/f0046-01.jpg)

执行：

```
nouveau mot pour perroquet ? (sinon non)
master
nouveau mot pour perroquet ? (sinon non)
coco master
coco master
coco master
jaco master
jaco master
jaco master
RSD
coco RSD
coco RSD
coco RSD
jaco RSD
jaco RSD
jaco RSD
nouveau mot pour perroquet ? (sinon non)
no
```

- `wait` 和 `notifyAll` 方法定义在`java.lang.Object`类中，因此被所有类继承（包括`notify`）。

- `wait`方法暂停（阻塞）线程的执行，直到满足某个条件。条件的满足通过另一个线程使用`notify`或`notifyAll`方法来信号。

- 当使用`synchronized`方法调用`wait`方法时，在执行暂停的同时，调用该方法的对象的锁会被释放。一旦条件出现，线程将等待获取锁并继续执行。

- 注意这里`sleep`和`wait`之间的区别：

  - `sleep`阻塞执行但线程保持锁（结束其执行）；

  - `wait`阻塞执行但释放锁（另一个线程可以执行临界区域）。

### 2.8.2 Wait 和 notify

在接下来的代码中，与之前相比，我们将`notifyAll`替换为了`notify`：

![images](img/f0048-01.jpg)

执行：

```
coco bonjour
coco bonjour
coco bonjour
RSD
coco RSD
coco RSD
coco RSD
nouveau mot pour perroquet ? (sinon non)
encore
jaco encore
jaco encore
nouveau mot pour perroquet ? (sinon non)
bizarre
coco bizarre
coco bizarre
nouveau mot pour perroquet ? (sinon non)
```

`notify`释放一个等待线程。`notify()`每次唤醒一个线程（不是基于 FIFO 机制）。

第二个生产者消费者示例所示。它展示了用户在车站等待巴士；巴士到达并将用户装上车。

![images](img/f0050-01.jpg)

```java
class BusSimple {
    public static void main(String args[]) {
        Station BusStation = new Station();
        Usager[] u = {new Usager("A", BusStation), new Usager("B", BusStation),
                      new Usager("C", BusStation), new Usager("D", BusStation),
                      new Usager("E", BusStation)};
        Bus b = new Bus(BusStation);
        b.start();
        for (int i = 0; i < u.length; i++) {
            u[i].start();
        }
    }
}

class Station {
    private int count = 0;
    public synchronized void charger(String name) {
        while (count == 5) wait();
        count++;
        System.out.println(name + " arrives");
        notifyAll();
    }
    public synchronized void attendre() {
        while (count == 0) wait();
        count--;
        System.out.println("Bus departs");
        notifyAll();
    }
}

class Usager extends Thread {
    private String name;
    private Station station;
    public Usager(String name, Station station) {
        this.name = name;
        this.station = station;
    }
    public void run() {
        for (int i = 0; i < 3; i++) {
            station.charger(name);
            try { sleep(1000); } catch (InterruptedException e) {}
        }
    }
}

class Bus extends Thread {
    private Station station;
    public Bus(Station station) {
        this.station = station;
    }
    public void run() {
        while (true) {
            station.attendre();
            try { sleep(2000); } catch (InterruptedException e) {}
        }
    }
}
```

共享对象是`BusStation`；它包含两个方法。一个由生产者使用（`charger`），另一个由消费者使用（`attendre`）。

执行：

```
C arrives
E arrives
A arrives
D arrives
Bus departs
C arrives
E arrives
A arrives
D arrives
Bus departs
C arrives
E arrives
A arrives
D arrives
Bus departs
C arrives
E arrives
A arrives
D arrives
Bus departs
C arrives
E arrives
A arrives...
```

## 2.9 经典的生产者-消费者模式

我们将讨论单生产者单消费者情况下的经典模式。

这里使用的示例是教授教学生。学生必须重复每个单词三次。

![image](img/fig2-4.jpg)

**图 2.4.** 消费者/生产者模式。该图的彩色版本，请访问 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)

该示例的代码如下：

![images](img/f0052-01.jpg)

执行：

```
nouveau mot pour perroquet ?
Speak
nouveau mot pour perroquet ?
coco Speak
coco Speak
coco Speak
House
nouveau mot pour perroquet ?
coco House
coco House
coco House
Bonjour
nouveau mot pour perroquet ?
coco Hello
coco Hello
coco Hello
Chat
coco Chat
coco Chat
coco Chat
```

- 问题被解决了，只有一个老师和一只鹦鹉，一个等待另一个：

  - 鹦鹉等待学习新单词。

  - 老师等待鹦鹉阅读和重复单词。

- 这种经典模式被称为生产者-消费者：

- 两个函数必须同步以便：

  - 消费者等待直到没有可消费的内容。

  - `while (motAuTableau == null)`

  - 生产者在消费者未准备好消费时等待。

  - `while (motAuTableau != null)`

![images](img/f0053-01.jpg)

也可以存在具有多个生产者和多个消费者的模型。其中一个示例如下：

- `生产者`线程产生数据并放入消息队列。

- `消费者`线程从队列中提取数据。

- 生产者和消费者不能同时访问队列（临界区域）。

![images](img/f0054-01.jpg)

该模型的可能实现将相对于消息队列的同步。

- 生产者：

  - 当队列满时：阻塞；

  - 当有可用空间时：取消阻塞。

- 消费者：

  - 当队列为空时：阻塞；

  - 当队列中有数据时：取消阻塞。

## 2.10 Java 中的信号量 (Semaphore)

定义.– 信号量是一种高级对象，有助于管理对共享资源的并发访问，它最多允许 N 个并发访问。

示例：

- 管理一个具有 N 个车位的停车场的进出；

- 管理如医生诊所、美发店、保险公司等处拥有 N 张可用椅子的候诊室。

### 2.10.1 Java 1.5 之前

信号量对象封装了一个完整的和两个原子操作：递增操作和递减操作。`P`方法包含等待（wait），而`V`方法包含通知（notify）。

一个用于实现信号量的可能类如下：

![images](img/f0055-01.jpg)

每个想要访问临界区的线程都必须使用`P`方法，随后它将减少计数器变量的值。

在前四个线程访问后，在第五个线程想要访问临界区的情况下，临界区的内容和计数器的值将如下：

![images](img/f0056-01.jpg)

如果 T4 退出临界区，它必须使用`V`方法（递增计数并通知）。

![images](img/f0056-02.jpg)

由于 T5 是唯一被等待阻塞的线程，它将在收到来自 T4 的通知后进入临界区。

![images](img/f0057-01.jpg)

在所有线程都退出临界区后，临界区的状态和计数器的值如下：

![images](img/f0057-02.jpg)

### 2.10.2 Java 1.5 之后

Java 1.5 版本及其所在的包`java.util.concurrent`（以及其所有的子包）提供了高级同步工具。

- 操作`P`（`acquire()`）：递减计数器；如果计数器为负，则在等待可以进行递减操作时阻塞。

- 操作`V`（`release()`）：递增计数器；如果计数器为负或为空，则发送通知。

- 我们可以将信号量视为一组芯片，具有两种操作：

  - 取走一个芯片，或者在必要时等待直到有可用的芯片；

  - `acquire()`，通常带有等待；

  - 放回一个芯片；

  - `release()`，通常带有通知。

- 一个信号量有一个芯片，它与锁非常相似。

以下示例是使用信号量管理停车场。类参数`Semaphore`表示停车场的大小。

![images](img/f0058-01.jpg)

执行过程：

```
Thread 2 is not in the parking lot
Thread 3 is not in the parking lot
Thread 4 is not in the parking lot
Thread 0 is not in the parking lot
Thread 1 is not in the parking lot
Thread 1 enters the parking lot
Thread 2 enters the parking lot
Thread 3 enters the parking lot
Thread 1 exits the parking lot
Thread 0 enters the parking lot
Thread 0 exits the parking lot
Thread 4 enters the parking lot
Thread 2 exits the parking lot
Thread 4 exits the parking lot
Thread 3 exits the parking lot
```

通过将之前代码中的指令`Semaphore sem = new Semaphore(3)`替换为`Semaphore sem = new Semaphore(1)`，我们获得了以下执行结果：

```
Thread 2 is not in the parking lot
Thread 3 is not in the parking lot
Thread 4 is not in the parking lot
Thread 0 is not in the parking lot
Thread 1 is not in the parking lot
Thread 0 enters the parking lot
Thread 0 exits the parking lot
Thread 4 enters the parking lot
Thread 4 exits the parking lot
Thread 1 enters the parking lot
Thread 1 exits the parking lot
Thread 3 enters the parking lot
Thread 3 exits the parking lot
Thread 2 enters the parking lot
Thread 2 exits the parking lot
```

# 3 实时系统与实时 Java

## 3.1 实时系统

### 3.1.1 定义

实时系统与其他系统的区别在于，它们在某些情况下考虑了时间相关的限制，在这些情况下，遵守时间延迟与结果的准确性同样重要；换句话说，系统不仅必须交付准确的结果，还必须在给定的时间限制内交付结果。

在实时计算中，系统的正确行为不仅取决于逻辑处理结果，还取决于产生结果的时间 [STA 88]。

示例：

- ATM 机不能花费 5 分钟来交付现金。

- 雷达不能花费 2 秒来做出反应。

- ABS 系统获取信息不能超过 150 毫秒，反应不能超过 1 秒（ABS 指汽车上使用的防锁制动系统，防止车轮在剧烈制动下锁死）。

### 3.1.2 实时操作系统的示例

- Windows CE（Windows Embedded Compact），通常称为 WinCE，是 Windows 用于车载系统和其他极简系统（例如用于手持电脑）的变体。

- LynxOS 是一种基于 UNIX 平台的实时操作系统。

- LynxWorks 是主要用于车载应用的实时操作系统。

### 3.1.3 实时系统的类型

- 软实时（Flexible real-time）：

  - 系统接受数据处理的波动。

  - 惩罚不是灾难性的。

  - 这些系统接受半秒（500 ms）甚至一秒的延迟。

  示例：多媒体系统，如果几张图片没有显示，不会危及系统运行。



## 3.1.3 实时系统的类型

- **硬实时（Firm real-time）**：
  - 在可接受的延迟内响应至关重要。
  - 截止日期后的结果无用。
  - 示例：金融交易等。

- **硬实时（Hard real-time）**：
  - 系统在延迟内的响应至关重要。
  - 缺乏响应是灾难性的。
  - 示例：空中交通管制、核反应堆控制等。

## 3.1.4 架构

- **单任务架构（Monotask architecture）**：
  - 单任务的实时系统很容易定义。它只需无限重复以下任务列表：
    - 等待刺激。
    - 根据刺激做出反应。
  - 示例：自动雷达。

- **多任务架构（Multitask architecture）**：
  - 每个任务都可以由一个线程执行。资源可以由临界区保护。临界区的长度影响系统的响应时间。
  - 示例：入侵检测系统（IDS），它实时执行各种任务，包括：
    - 互联网流量分析；
    - 识别参与攻击的 IP；
    - 防火墙重配置；
    - 警报的可视化通知：在一个或多个控制台上显示警报。

## 3.1.5 带优先级的任务调度

优先级有助于组织任务。优先级值越高，任务访问处理器的优先级越高。优先级可以是动态的或静态的。

在实时系统中，任务通常不会被低优先级任务阻塞。

- 考虑两个线程 `T1` 和 `T2`。
- `T1` 具有高优先级（例如 10），`T2` 具有低优先级（例如 1）。
- 启动这两个线程后，`T1` 必须在 `T2` 之前执行。
- 在某处，`T1` 被阻塞（例如通过 `wait()`），`T2` 运行进入临界区。
- `T1` 解阻塞并尝试获取锁。
- `T2` 没有被调度且没有释放锁。
- `T2` 在 `T1` 之前执行。
- 优先级反转管理会导致灾难性的影响。
- 事实上，由于缺乏优先级反转的管理意味着高优先级任务无法执行，可能无法对紧急情况做出反应。
- 示例：核反应堆的紧急停止指令会被低优先级的指令阻塞。

没有一种可以完全避免优先级反转的简单解决方案。尽管如此，可以通过某些措施来限制这些风险。特别是，可以仅允许具有相似优先级的线程访问临界区域。

提出了两种解决方案：

- **优先级上限（Priority ceiling）**：
  - **优先级上限协议（PCP）**：这包括为每个资源关联一个优先级上限。该资源的优先级定义为可以使用该资源的任务中的优先级加 1。调度器将此优先级传递给访问该资源的每个任务。当任务完成对资源的使用后，其优先级恢复到原始值。

- **优先级继承（Priority inheritance）**：
  - **优先级继承协议（PIP）**：当任务 `T2`（高优先级）在访问资源 `R` 时被阻塞，被阻塞的任务 `T1`（低优先级）继承 `T2` 的优先级。`T1` 使用继承来的优先级，直到 `R` 被释放，届时它将重新获得获取该资源之前的优先级。

## 3.2 实时环境中的 Java

Java 最初是为车载设备设计的。但 Java 很快开始被用于 Web 应用程序（Applet）。随后，Java 被用于以下应用：

- 经典的 `J2SE`（`Java 2 标准版`）用于客户端工作站（`JVM` 经典，`HotSpot`）。
- 业务级 `J2EE`（`Java 2 企业版`）用于业务应用开发（`HotSpot`）。
- 精版的 `J2ME`（`Java 2 微型版`）用于移动系统，如个人助手平板电脑和手机（经典 `JVM`、`Kilo VM`（`KVM`）、`Card VM`（内置在打印芯片上的 `JVM`））。

请注意，这里的语言并非为实时设计，原因如下：

- 缺乏调度方面的专业知识；
- Windows 在管理线程间优先级方面存在困难；
- 对于 `notify()` 或 `notifyAll()`，对所选线程没有规定，不一定是先入先出（FIFO）；
- 它是 Java 少数不具备移动性的功能之一；
- 垃圾回收器（`GC`）存在问题；
- `GC` 可以在任何时间执行；
- `GC` 可能持续特定的时长；
- `GC` 无法被抢占；
- `GC` 会抢占任何线程。

### 3.2.1 RTSJ（Java 实时规范）

这是一个关于扩展 `JVM` 实时功能（`JVM RTSJ`）的提案 [JAV 17a]。

规范由来自多家公司（Sun、`IBM`、`QNX`、`Nel` 等）的专家小组完成。

限制条件：

- 与现有程序兼容：任何非实时 Java 应用程序都可以在 `JVM RTSJ` 上运行。
- 无语法扩展。
- 无硬件或电力的前提要求。
- 可预测的执行时间。
- 粒度：纳秒。64 位（ms）+ 32 位（ns）。

`RTSJ` 在以下领域改进了 Java 实时编程：

- 内存管理。
- 时钟和时间管理。
- 调度和“可调度”对象。
- 实时线程。
- 异步事件和定时器的管理。
- 同步和资源共享。
- 新增的包 `javax.realtime` [JAV 17b]。
- 三个接口。
- 47 个类。
- 15 个异常。
- 4 个错误。

`RTSJ`：线程

- 一个接口：
  - `Schedulable`：可以被调度的对象，自 `java.lang.Runnable`。
  - `public interface Schedulable extends java.lang.Runnable`。
- 两个新类：
  - `RealtimeThread`。
  - `public class RealtimeThread extends java.lang.Thread implements Schedulable`。
  - 可以访问堆。优先级低于 `GC`（`DestroyJavaVM`）。
  - `NoHeapRealtimeThread`。
  - `public class NoHeapRealtimeThread extends RealtimeThread`。
  - 它的优先级高于 `GC`。在 `ScopedMemory` 内工作，该线程内的对象被分配到该内存中。

`ScopedMemory` 具有以下特性：

- 其生命周期与占用它的实时线程一致。
- 不由垃圾回收器管理。
- 对象可以在 `ScopedMemory` 内分配（而不是在 `HeapMemory` 中）。
- 对象在作用域结束时释放。
- `NoHeapRealtimeThread` 无法访问堆（`Heap`）。
- 因此，`NoHeapRealtimeThread` 不会被垃圾回收器阻塞。

优先级的组织方式如下：

`Thread` < `RealtimeThread` < `Garbage Collector` < `NoHeapRealtimeThread`。

### 3.2.2 实现

以下是研究的三种实现：

- **参考实现：RI**。
  - 面向研究，旨在证明 Java 实时探索的可行性。由 `TimeSys` 公司实施 [TIM 17]。也存在于 `Linux/x86` 版本。

其代码的执行如图所示：

![image](img/fig3-1.jpg)

**图 3.1.** *参考实现*

- **开源实现：jRate**。

`jRate` 是一个由 Angelo Corsaro 运行 [UCI 17] 的大学项目（加州州尔文大学）。

`jRate` 由以下部分组成：

- Java。
- `C++`（`CNI`）。
- `JNI`（Java Native 接口）。
- `JVM` 通过 `C++`。
- `jRate`。
- `C++`。
- `jRate`。
- `GC`。
- `GCC`。

- **私有实现：JamaicaVM**。

这是由 `AICAS` 公司针对航空航天、汽车和工业机器人领域的商业化解决方案。它拥有实时 `GC`。下图展示了其实现方案：

![image](img/fig3-2.jpg)

**图 3.2.** *JamaicaVM 的实现*

# 4 Java 分布式编程

## 4.1 分布式应用的定义

应用程序分为若干单元。

- 每个单元位于不同的机器上。
- 每个单元可以在不同的系统上执行。
- 每个单元可以使用不同的语言编写。

![image](img/fig4-1.jpg)

**图 4.1.** *单体应用与分布式应用的对比。该图的彩色版本请参阅 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)*

## 4.2 分布式应用中的通信

### 4.2.1 底层通信：套接字（socket）

#### 4.2.1.1 定义

网络套接字是一种允许进程在同一台机器或跨网络进行通信和同步的模型。

套接字是由伯克大学于 1986 年开发的。

对于 Java 而言，`java.net` 包中的 `Socket` 类出现在 `J2SE 1.4`（2002 年 2 月 6 日），用于实现套接字。

#### 4.2.1.2 通信模式

- 连接模式（类似于电话通信），使用 `TCP` 协议。在这种通信模式下，两个进程之间建立了持久的连接，因此每个数据包不再需要目的地址。
- 非连接模式（类似于邮件通信），使用 `UDP` 协议。这种模式需要为每个数据包指定目的地的地址，且不需要确认接收。

通信需要两个套接字（socket）：为网络上通信的两个程序各提供一个。

- 客户端一个 socket。
- 服务端一个 socket（服务器端有一个用于连接的第二个 socket）。

所使用的 IP 通信模式（`UDP` 或 `TCP`）对应于 socket 的类型。

在下一节中，我们将重点关注 `TCP` socket。

在 Java 中，每个 `Socket` 类的实例都与一个 `InputStream` 类的对象（用于读取套接字）和一个来自 `OutputStream` 类的对象（用于写入套接字）关联。

- 服务器将使用两种类型的 socket。
- 第一种称为**连接套接字**，用于等待客户端。
- 在 Java 中，可以通过简单实例化 `java.net` 包中的 `ServerSocket` 类的对象来创建连接套接字。
- 示例：`ServerSocket conn = new ServerSocket(10080)`。
- 第二种称为**通信套接字**，用于与客户端对话。
- 一旦创建了连接套接字，我们将让它等待客户端并获取允许其与客户端对话的通信套接字。
- `Socket comm = conn.accept()`。
- 我们可以使用与该 socket 关联的输入和输出流与客户端进行通信。

- `ServerSocket(numberPort)`：在此端口号上创建一个 `ServerSocket` 对象。
- `accept()`：等待来自慢客户端机器的连接。当客户端机器到达连接请求时，会创建一个 socket 连接到服务器。这将是阻塞方法 `accept()` 返回的对象。
- `ServerSocket(numberPort, int backlog)`：在此端口号上创建一个 `ServerSocket` 对象，并带有一个大小由 `backlog` 指定的连接队列。
- 当队列满满时，连接请求将被拒绝，并导致客户端侧抛出异常。默认情况下，该大小为 50。

常用方法：

- `accept()`：等待来自客户端机器的连接。
- `close()`：关闭 `ServerSocket` 以及通过其 `accept` 方法获取的任何正在运行的 socket。
- `isClosed()`：指示套接字是否已关闭。
- `getLocalPort()`：返回本地端口号。
- `InetAddress getInetAddress()`：返回服务器地址。`InetAddress` 代表一个 IP 地址以及可能的机器名称。
- `getHostName()`：返回存储在 `InetAddress` 类型对象中的主机名，形式为字符串链。
- `getHostAddress()`：返回存储在 `InetAddress` 类型对象中的 IP 地址，形式为字符串链。
- `getByName(String host)`：根据参数中的名称返回 IP（`InetAddress` 对象）。

以下代码的目的是找到作为参数传递的机器名对应的 IP 地址：

```java
import java.net.*;
public class ResolveName{
  public static void main(String[ ] args){
    InetAddress adresse;
    try{
      adresse=InetAddress.getByName("localhost");
      System.out.println(adresse.getHostAddress());
      adresse=InetAddress.getByName("www.facebook.com");
      System.out.println(adresse.getHostAddress());
      System.out.println(adresse);
    }catch(UnknownHostException e) { }
  }
}
```

执行结果：

```
127.0.0.1
31.13.75.36
[www.facebook.com/31.13.75.36](http://www.facebook.com/31.13.75.36)
```

与服务器不同，客户端只使用一个单一 socket：通信套接字。

- 连接到服务器并获取通信套接字。
- `Socket comm = new Socket ("localhost", 10080)`。
- `Socket` 构造函数在客户端侧是一个阻塞方法。

然后可以使用与该 socket 关联的输入和输出流与服务器进行通信。

- 有九个构造函数，其中两个被认为已弃用，因此有七个函数，包括：
  - `Socket(String host, int port)`。
  - `Socket(InetAddress address, int port)`。
  - 使用 IP：`InetAdress`。

常用方法：

- `close()`：正确关闭套接字，并可能抛出 `UnknownHostException` 异常。
- `getOutputStream()`：为 socket 返回一个 `OutputStream`。
- `getInputStream()`：为 socket 返回一个 `InputStream`。
- `getPort()`：返回 socket 连接的远程端口号。
- `InetAddress getInetAddress()`：返回远程机器的地址。
- `isClosed()`：指示套接字是否已关闭。
- `isConnected()`：返回 socket 连接的状态。
- `connect(SocketAddress adresseSocket)`：将服务器连接到 socket。
- `connect(SocketAddress adresseSocket, int timeout)`：以毫秒为单位的超时值将 socket 连接到服务器。
- 如果延迟过期，则抛出 `SocketTimeoutException`。
- `SocketAddress` 是一个抽象类。
- `InetSocketAddress` 继承自 `SocketAddress`，是一个表示 `InetAddress` 和端口的类。
- `InetSocketAddress(InetAddress ina, int port)`。
- `InetSocketAddress(String hostName, int port)`。

以下代码通过 `connect` 创建带有超时的 socket：

```java
Socket sock = null;
try {
  int port = XYZ;
  int timeOut = 3000;
  SocketAddress sockAddr = new InetSocketAddress("host", port);
  sock = new Socket(); // 构造函数不连接。
  sock.connect(sockAddr, timeOut); // 延迟为毫秒，所以 3 秒。
} catch (UnknownHostException e) {
} catch (SocketTimeoutException e) {
}
```

连接请求阻塞直到连接建立或超时过期；如果延迟过期，将抛出 `SocketTimeoutException`。

### 4.2.3 示例

在下面，我们展示了一个与 TCP socket 通信的简单示例：

- 客户端向服务器发送消息。
- 服务器确认并请求下一个单词。
- 要断开连接，客户端发送单词“no”。

![image](img/fig4-2.jpg)

**图 4.2.** *与 Socket 通信的示例。彩色版本请查看 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)*

服务端代码如下：



```java
import java.net.*;
import java.io.*;
class ServerEcho {
  public static void main(String args[]) {
    ServerSocket server = null;
    try {
      server = new ServerSocket(7777); // 连接套接字
      while (true) {
        Socket sock = server.accept(); // 等待
        System.out.println("connected");
        PrintWriter sockOut = new PrintWriter(sock.getOutputStream(), true);
        BufferedReader sockIn = new BufferedReader(new
        InputStreamReader(sock.getInputStream()));
        String recu;
        while ((recu = sockIn.readLine()) != null) {
          System.out.println("recu:"+recu);
          sockOut.println("next? ");
        } //end while
        sockOut.close();
        sock.close();
      } //end while (true)
    } catch (IOException e) {
      try {server.close();}
      catch (IOException e2) {}
    } // end 第一个 catch
  } // end main
} // end class
```

![image](img/fig4-3.jpg)

**图 4.3.** 与 Socket 通信的示意图。彩色版本请查看 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)

客户端代码如下：

```java
import java.io.*;
import java.net.*;
import java.util.Scanner;
public class ClientEcho {
  public static void main(String[] args) throws IOException {
  Socket sock = null;
  PrintWriter sockOut = null;
  BufferedReader sockIn = null;
  try{sock = new Socket("localhost", 7777); // the communication socket.
    sockOut = new PrintWriter(sock.getOutputStream(), true); //force write
    sockIn = new BufferedReader(new InputStreamReader(sock.getInputStream()));
  } catch (UnknownHostException e) {
    System.err.println("host unreachable: localhost");
    System.exit(1);
  } catch (IOException e) {
    System.err.println("cannot connect to: localhost");
    System.exit(1);
  }
  System.out.println("press any key to close");
  Scanner scan = new Scanner(System.in);
  String message = scan.next().toLowerCase();
  while (! message.equals("no")) {
    sockOut.println(message);
    String recu = sockIn.readLine();
    System.out.println("server -> client:" + recu);
    message = scan.next().toLowerCase();
  }
  sockOut.close();
  sockIn.close();
  sock.close();
  }
}
```

执行过程如下：

- 在服务器端：

  `connected`

  `received: hello`

  `received: bye`

- 客户端：

  `press any key to close`

  `hello`

  `server -> client: next ?`

  `bye`

  `server -> client: next ?`

  `no`

注意，对于字符，Java 语言使用了基于 16 位 Unicode 编码的`char`类型。网络传输是基于 8 位字节（byte）的。

因此，Java 的通信方法基于字节传输的。

- 将`String`转换为`bytes[ ]`：

  - `String chaine = "ABCD";`

  - `byte[ ] message=chaine.getBytes();`

- 将`byte[ ]`转换为`String`：

  - `chaine = new String(message);`

#### 4.2.1.4. 直接向 socket 流写入数据

以下代码允许直接向 socket 流写入数据：

```java
OutputStream sockOut = socket.getOutputStream();
// 获取 socket 的写入输出流。
// 我们直接使用它写入新字节。
byte[ ] buffer = new byte[1024];
buffer = "ABCD".getBytes();
try {
 sockOut.write(buffer);
// write(buffer) 写入缓冲区中的所有字节。
sockOut.flush();
 // flush() 应该强制将缓冲区内容写入流中（float）。
// 不会等待缓冲区填充。
 sockOut.write(buffer, 0, 2);
// write(buffer, pos, nbre) 从指定的位置 (pos) 
// 写入数量（nbre）的字节。
} catch (IOException e) {}
```

`write`和`flush`可能会引发特定的`IOException`，即尝试向已关闭的流写入数据。

在接下来的段落中，我们将通过通过单个字符链传输各种数据。

```java
try {
  OutputStream sockOut = socket.getOutputStream();
  byte[ ] buffer = new byte[1024];
  String envoi = "chain String"+" "+(-1234)+" "+12.34+" "+true;
  buffer = envoi.getBytes();
  sockOut.write(buffer, 0, envoi.length());
  sockOut.flush();
} catch (IOException e) {}
```

#### 4.2.1.5. 直接读取 socket 流

以下代码允许直接读取 socket 流：

```java
InputStream sockIn = socket.getInputStream();
// 获取 socket 的读取输入流。
byte[ ] buffer = new byte[1024];
int read;
try {
  read = sockIn.read(buffer);
// 读取流并将其存入缓冲区。返回读取的字节数。
System.out.write(buffer, 0, lu);
// 在标准输出上显示缓冲区。
} catch (IOException e) {}
```

流的结束可能是正常的（关闭写入），也可能是意外的（写入过程结束端断开）。

读取操作可能会引发`IOException`。

#### 4.2.1.6. 高级读写

`DataOutputStream`使得在所有系统上写入任何 Java 原始类型成为可能。

以下代码以已知格式向 socket 写入数据：

```java
DataOutputStream sockDataOut = null;
try {
sockDataOut = new DataOutputStream(socket.getOutputStream());
sockDataOut.writeByte(6); //写入数字的第一个字节。
sockDataOut.writeChar('c'); // 写入前两个字节对应的字符。
 sockDataOut.writeBoolean(true); // 在一个字节上写入布尔值。
sockDataOut.writeInt(-1234); // 在四个字节上写入数字。
 sockDataOut.writeDouble(12.34); // 在八字节上写入双精度浮数。
 sockDataOut.flush(); // 如果存在缓冲区，应该强制将缓冲区内容写入流。
 sockDataOut.writeUTF("chaine String"); // 写入字符串。
} catch (IOException e) {}
```

在所有系统上读取任何 Java 原始类型需要使用`DataInputStream`。

从 socket 中以已知格式读取数据：

```java
DataInputStream sockDataIn = null;
try {
sockDataIn = new DataInputStream(socket.getInputStream());
byte b = sockDataIn.readByte(); // 读取数字的第一个字节。
char c = sockDataIn.readChar(); // 读取前两个字节对应的字符。
boolean bool = sockDataIn.readBoolean(); // 从一个字节上读取布尔值。
int i = sockDataIn.readInt(); // 在四个字节上读取数字。
double d = sockDataIn.readDouble(); // 在八字节上读取双精度浮数。
String s = sockDataIn.readUTF(); // 读取字符串。
} catch (IOException e) {}
```

流的关闭可能是正常的（关闭写入），也可能是意外的。

向 socket 写入文本：

```java
PrintWriter sockOut = new PrintWriter(socket.getOutputStream()));
sockOut.print("chaine String");
sockOut.print(1234);
sockOut.print(12.34);
sockOut.println(true);
```

- 创建连接到`OutputStream`的`PrintWriter`。

- 我们可以使用`print`或`println`写入文本。

- 没有任何方法会引发`Exceptions`。

以下代码允许用户逐行读取 socket：

```java
try{
BufferedReader sockReader = new BufferedReader(new InputStreamReader
(socket.getInputStream())))
String line;
while ((line = sockReader.readLine()) != null)
System.out.println(line);
```

- 创建连接到`InputStream`的`BufferedReader`。

- 我们可以使用`readLine()`读取字符链。

- `readLine()`返回行，如果到达末尾则返回`null`。

#### 4.2.1.7. 通过 socket 传输对象

在接下来的段落中，我们将讨论通过 socket 传输对象。

示例：客户端连接到服务器查询学生的专业和成绩。

- 服务器端存储了一个学生表。

- 客户端连接到服务器并想要获取学生的。

- 客户端必须将学生姓名发送给服务器。

- 服务器读取姓名，确认接收，遍历查找学生并最后保存对象。

- 该对象通过 socket 发送给客户端。

- 客户端读取对象（恢复）。

- 客户端显示对象的特征。

- 通过网络传输的对象必须是序列化的。

```java
import java.io.Serializable;
public class Student implements Serializable{
String name;
String major;
int moy;
Student (String name, String major, int moy) {
���this.name = name;
```�this.major = major;

```�this.moy = moy;
}
String getNom() {
���return name;
}
public String toString() {
���return "Student: "+name+" "+major+" : "+moy;
�}
}
```

`Student`类在客户端和服务器之间共享¹。

![images](img/f0085-01.jpg)![images](img/f0086-01.jpg)

执行：

服务器端：

connected

received: A

客户端：

server -> client: Student: A GL: 13

#### 4.2.1.8. Java applet 与服务器通过 socket 的通信

以下执行显示了 applet 与服务器通过 socket 的通信：

![image](img/fig4-4.jpg)

**图 4.4.** 使用 Sockets 的 applet 与服务器之间的通信。该图的彩色版本请参阅 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)

服务器的实现如下：

```java
import java.io.*;
import java.net.*;
import java.util.*;
public class NetServer {
  public static void main(String[] args) {
    try{
        ServerSocket serverSocket = new ServerSocket(8765);
        Socket clientSocket = serverSocket.accept();
        BufferedReader in = new BufferedReader(new
          InputStreamReader(clientSocket.getInputStream()));
        PrintWriter out = new
          PrintWriter(clientSocket.getOutputStream(), true);
        while (true) {
          Integer numb = new Integer(in.readLine());
          System.out.println("recu: " + numb.intValue());
          out.println(numb.intValue()+1);
        }
    }catch(IOException ex){System.err.println(ex);}
  }
}
```

客户端的实现如下：



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;
import java.io.*;
import java.net.*;

public class NetApplet extends Applet implements ActionListener {
  TextField numbField;
  Label display;
  Socket socket;

  public void init() {
    try {
      socket = new Socket("localhost", 8765);
    } catch (UnknownHostException e) {
      System.out.println("Unknown host");
    } catch (IOException e) {
      System.out.println("IO Exception");
    }

    numbField = new TextField(6);
    add(numbField);

    Button button = new Button("Send");
    add(button);
    button.addActionListener(this);

    display = new Label("Pas de nombre");
    add(display);
  }

  public void actionPerformed(ActionEvent e) {
    int numb = 0;
    String numbStr = null;
    BufferedReader in = null;
    PrintWriter out = null;

    String actionCommand = e.getActionCommand(); // know the source of the event

    if (e.getSource() instanceof Button)
      if (actionCommand.equals("Send")) {
        try {
          numb = Integer.parseInt(numbField.getText());
        } catch (NumberFormatException ex) {
          System.out.println("Number Format Exception");
        }

        try {
          in = new BufferedReader(
              new InputStreamReader(socket.getInputStream()));
          out = new PrintWriter(socket.getOutputStream(), true);
        } catch (IOException ex) {
          System.out.println("IO Exception");
        }

        out.println(numb);

        try {
          numbStr = in.readLine();
        } catch (IOException ex) {
          System.out.println("Applet receive failed:");
        }

        display.setText(numbStr);
      }
  }
}
```

## 4.2.2 高级通信：中间件

这些是提供复杂服务的层。这些层是使用`TCP/UDP`层创建的。例如：从远程实体的方法调用。

- 中间件是一个中间层（软件层），它位于网络通信基础设施和分布式应用程序元素之间。

![image/fig4-5.jpg]

**图 4.5.** 中间件在网络中的位置。该图的彩色版本请参阅 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)。

- 分布式环境（大部分）基于`RPC`（远程过程调用）。
- 这种机制以请求/响应模式工作。
- 客户端发出请求（请求服务）。
- 服务器随后处理请求并最终向客户端返回响应。

`RPC`具有以下特征：

- 过程化编程，因此不是面向对象的。
- 参数和返回值是基本类型。
- 没有“远程引用”。

随后，中间件以以下方式演进：

- `JAVA RMI`（远程方法调用）。单语言、跨平台：从`JVM`到`JVM`。
- `CORBA`（通用对象请求代理）。多语言、跨平台。
- 微软的`DCOM`（分布式组件模型）。多语言，用于分布式软件组件之间的通信。

在接下来的章节中，我们将重点关注 Java RMI。

![image/fig4-6.jpg]

**图 4.6.** RPC 操作。该图的彩色版本请参阅 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)。

### 4.2.2.1 RMI 简介

`RMI`允许 Java 虚拟机进行通信，无论它们是在同一台机器上还是两台不同的机器上。`java.rmi`：集成`JDK 1.1`及更高版本（自 1997 年起）的 API。

为了让客户端访问远程服务，必须将其注册表中。RMI 注册表被称为`rmireistry`，它包含一个哈希表，键是名称，值是远程对象。

![image/fig4-7.jpg]

**图 4.7.** `rmireistry`

RMI 应用的工作原理如下：

- 服务器创建对象并将其保存在注册表中。
- 这允许客户端定位远程对象并获取其引用。
- 当客户端想要调用远程方法时，它在`rmireistry`中查找对象并获取指向该对象的引用（一个存根/stub）。
- 客户端通过新获取的引用调用远程对象的方法。
- 存根（stub）是远程对象的代理（本地代表），它通过网络调用远程对象的方法。
- 这种机制确保了调用的透明性。

![image/fig4-8.jpg]

**图 4.8.** RMI 应用的操作。该图的彩色版本请参阅 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)。

图 4.9 代表远程方法调用的阶段。

### 4.2.2.2 RMI 架构

图 4.10 代表 RMI 架构。

![image/fig4-9.jpg]

**图 4.9.** 远程方法调用的阶段。该图的彩色版本请参阅 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)。

![image/fig4-10.jpg]

**图 4.10.** RMI 架构。该图的彩色版本请参阅 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)。

- 第一层：存根/骨架（stub/skeleton）。
  - 存根（stub）：对象的本地代表。
    - 通过将远程调用传输到引用对象层（RRL），与远程`JVM`建立。
    - 装配参数以便传输到远程`JVM`。
  - 骨架（skeleton）：用于定位分布式对象。
    - 拆分远程方法的参数。
    - 调用请求的方法。
    - 对返回调用者的结果（返回值或异常）进行装配。
- 备注：自 Java 2（1998 年）起，不再需要骨架。
- 所有的远程对象共享一个类似的通用骨架类。
- 此外，直到 J2SE 5.0 版本（2004 年），在保存到 RMI 注册之前，需要一个名为`RMIC`（Java RMI 编译器）的存根编译器来生成存根/骨架。
- 现在，可以动态生成它们（不再需要使用`RMIC`）。
- 第二层：`RRL`（对象引用层）。
  - 通过查询`rmiregistry`获取远端对象的引用。
  - `rmiregistry`运行在每个托管远端对象的机器上。
  - 每个`JVM`只有一个`rmiregistry`。
  - `rmiregistry`默认在端口`1099`上接受服务请求。
- 第三层：`transport`。
  - 使用`TCP/IP`之上的通信协议。
  - 在方法调用期间，存根（stub）将调用传输到`RRL`层，后者将请求传输到`TCP/IP`之上`RMI`的`transport`层，并通过向上到达调用远端对象的骨架（skeleton）来传输请求。
  - 默认，`RMI`在端口`1099`上使用`JRMP`（Java 远程方法协议）协议。这是一个用于调用远程方法的协议。
    - `JRMP`是`RMI`的通信协议，仅用于用 Java 编写的应用之间。
    - 原始版本。
    - 集成在语言中。
    - 使用简单。
  - 从 Java 2 开始，为了兼容`CORBA`，客户端和服务器之间的通信可以使用`IIOP`（互联网对象 ORB 协议）协议进行。
    - 较新版本。
    - 兼容`CORBA`。
    - 实现难度更大。

在这种情况下，需要`javax.rmi`宏包。

### 4.2.2.3 部署 RMI

部署`RMI`需要使用多个包：

- `java.rmi.Naming`
- `java.rmi.Remote`
- `java.rmi.RemoteException`
- `java.rmi.server.UnicastRemoteObject`
- `java.rmi.registry.LocateRegistry`
- `java.rmi.NotBoundException`

`java.rmi.Naming`：是一个最终类：`public final class Naming extends Object`。

- 服务器可以使用`bind()`（或`rebind()`）方法记录远端对象。
- `static void bind (String name, Remote obj) throws AlreadyBoundException, MalformedURLException, RemoteException.`
- `static void rebind (String name, Remote obj) throws RemoteException, MalformedURLException.`
- 注意：如果对象在注册表中已以相同的名称记录（两个不同对象使用相同名称），则`bind()`会抛出异常。

`Remote`是一个用于设计远端对象的接口。

- 客户端将通过`lookup()`方法找到该对象。
- `static Remote lookup (String name) throws NotBoundException, MalformedURLException, RemoteException`

以下步骤将部署`RMI`：

- 服务端：
  - 定义一个包含可以远程调用的方法的接口（该接口与客户端共享）。
  - 编写实现该接口的类。
  - 编写一个类（服务器），该类将实例化对象，并在向`RMI`注册表中为其命名的同时对其进行记录。
- 客户端：
  - 根据名称获取其远端对象的引用。
  - 通过该引用调用方法。

要部署`RMI`，请按照下面提供的步骤操作。

#### 客户端和服务器之间的共享接口

该接口必须扩展`java.rmi.Remote`。

```java
import java.rmi.Remote;
import java.rmi.RemoteException;

public interface Hello extends Remote {
    public String Bonjour() throws RemoteException;
}
```

- `Remote`是一个没有方法的接口。
- 实现了`Hello`接口的对象是一个支持对其方法进行远程访问的对象。
- 所有方法必须抛出`RemoteException`。

![image](img/fig4-11.jpg)

**图 4.11.** 部署 RMI。需该图的彩色版本，请访问 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)。

#### 在服务端实现该接口的类

```java
import java.rmi.RemoteException;
import java.rmi.server.UnicastRemoteObject;

public class HelloImpl extends UnicastRemoteObject implements Hello {
  public HelloImpl() throws RemoteException {
  }

  public String Bonjour() throws RemoteException {
    return "Bonjour tous le monde !";
  }
}
```

- 它必须实现`Hello`接口。
- 它必须扩展`UnicastRemoteObject`。
- `Unicast`：远端对象在单台机器上存在唯一的副本。
- 它可以实现接口中之外的方法，但这些方法将无法被远程访问。
- 构造函数抛出`RemoteException`。
- 因此，用户必须编写一个。

#### 实现服务器

```java
import java.net.MalformedURLException;
import java.rmi.Naming;
import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;

public class HelloServer {
  public static void main(String[] args) {
    try {
      LocateRegistry.createRegistry(1099);
    } catch (RemoteException e) {
      System.err.println("rmiregistry already on this port");
      System.exit(1);
    }

    Hello hello;

    try {
      hello = new HelloImpl();
      Naming.rebind("rmi://localhost:1099/Hello", hello);
    } catch (RemoteException e) {
      System.err.println("server appears to down");
      System.exit(4);
    } catch (MalformedURLException e) {
      System.err.println("URL incorrect");
      System.exit(1);
    }
  }
}
```

```java
import java.rmi.*;
import java.rmi.server.*;
import java.rmi.registry.*;

public class HelloServer extends UnicastRemoteObject implements Hello {
  public HelloServer() throws RemoteException {
  }

  public int multi(int a, int b) throws RemoteException {
    return a * b;
  }

  public static void main(String[] args) {
    try {
      LocateRegistry.createRegistry(1099);
    } catch (RemoteException e1) {
      System.err.println("rmiregistry is already launched on this port");
      System.exit(1);
    }

    try {
      HelloServer objet = new HelloServer();
      Naming.rebind("badr", object);
      System.out.println("Server ready");
    } catch (Exception e) {
      System.err.println("Error: " + e.getMessage());
    }
  }
}
```

### 关于 `bind` 和 `rebind` 的几点说明

以下代码是正确的：

```java
HelloServer object = new HelloServer();
Naming.rebind("badr", object);
Naming.rebind("badr1", object);
```

可以为同一个对象设置多个名称：无论使用`bind`还是`rebind`均如此。

以下代码产生异常：

```java
HelloServer object = new HelloServer();
HelloServer object1 = new HelloServer();
Naming.bind("badr", object);
Naming.bind("badr", object1);
```



以下代码是正确的：

```java
HelloServer object = new HelloServer();
HelloServer object1 = new HelloServer();
Naming.rebind("badr",object);
Naming.rebind("badr",object1);
```

它使用`rebind`时可以工作，因为它是重新保存；`badr`只指向`object1`。

### 实现客户端

```java
import java.rmi.*;
public class HelloClient {
public static void main(String[] args) {
try {
  Hello reference = (Hello)Naming.lookup("badr");
  int resultat = reference.multi(5,12);
  System.out.println("The multiplication is: " + result); }
catch(Exception e) { System.err.println("Error: " + e.getMessage()); }
}
}
```

#### 执行结果

- 服务端：`Server ready`。
- 客户端：`The multiplication is 60`。

以下类用于生成注册表：

- `public final class LocateRegistry extends Object`。
- 用于在`java.rmi.registry`包中生成`rmiregistry`的类。
- `createRegistry`方法：
  - `static Registry createRegistry (int port)`：创建注册表。
  - `LocateRegistry.createRegistry(1099)`：在端口`1099`上创建注册表。
  - `createRegistry`是一个返回`Registry`的静态方法。
  - `public interface Registry extends Remote`。
  - 位于`java.rmi.registry`包中。
  - `LocateRegistry.createRegistry(1099)`：创建一个远程注册表（`rmiregistry`）。
- `getRegistry`方法：
  - 返回一个指向远程注册表的引用。
  - 各种签名：
    - `static Registry getRegistry()`。
    - `static Registry getRegistry(int port)`。
    - `static Registry getRegistry(String host)`。
    - `static Registry getRegistry(String host, int port)`。
    - `static Registry getRegistry(String host, int port, RMIClientSocketFactory csf)`。

应用示例：

```java
String [ ] NamesSaved = LocateRegistry.getRegistry("localhost",
1099).list();
```

`list()`：`Registry`接口的方法，返回注册表中记录的名称列表。

### 4.2.2.4 RMI 中的参数交换

通过 Java RMI 交换的参数必须是：

- 原生类型：`int`、`short`、`double`、`boolean`……，还有`String`。
- `Serializable`对象。
- `Remote`对象。

原生类型按值（拷贝）传输。

`Serializable`对象被序列化、传输，然后被反序列化（按值传输）。

`Remote`对象以远程引用的形式传输。

#### 原生类型

以下代码代表服务端上`multi`方法的实现：

```java
public int multi (int a, int b) throws RemoteException {
    return a * b;
}
```

客户端上的方法调用如下：

```java
try {
  Hello reference = (Hello)Naming.lookup("badr");
  int result = reference.multi(5,12);
  System.out.println("The multiplication is: " + result);
}catch(Exception e) { System.err.println("Error: " + e.getMessage()); }
```

在前面的例中，调用是按值执行的。

#### 传输 Serializable 对象

示例：我们希望使用一个数据服务器来存储一组 2D 坐标，用以描述平面上某数量车辆的位置。

该服务器必须包含以下功能：

- 创建一个新位置并为其分配一个名称。
- 对位置的读取访问。
- 对位置数量的访问。
- 服务器必须实现一个`hashtable`。
- 在`java`中，`Hashtable`类是`java.util`中的类。

图 4.12 `rmiregistry`。在我们的案例中：

- 键是位置名称。
- 值是 2D 坐标。
- `Serializable`类必须实现。

```java
import java.io.Serializable;
public class Point implements Serializable {
  public float x;
  public float y;
  public Point(float xx,float yy) {
    x = xx;
    y = yy;
  }
  public String toString() {
  return("+x+", "+y+") ;
  }
}
```

服务端的实现：

```java
import java.rmi.*;
import java.rmi.server.*;
import java.rmi.registry.*;
import java.util.Hashtable;

public class Serveur extends UnicastRemoteObject implements Position {
  private Hashtable h;
  public Serveur() throws RemoteException {
    h = new Hashtable();
  }
  public void insererTable(Point p, String nom) throws RemoteException {
    h.put(nom,p);
  }
  public Point position(String nom) throws RemoteException {
    return (Point) h.get(nom);
  }
  public int nombreles() throws RemoteException {
    return h.size();
  }
  public static void main(String[] args) {
    try {
      LocateRegistry.createRegistry(1099);
    } catch (RemoteException e1) {
      System.err.println("rmiregistry is already launched on this port");
      System.exit(1);
    }
    try {
      Serveur ib = new Serveur();
      Naming.rebind("Data",ib);
      System.out.println("Ready");
    } catch (Exception e) {
      System.err.println("Error: " + e.getMessage());
    }
  }
}
```

`Position`接口：

```java
import java.rmi.*;
public interface Position extends Remote {
  void insererTable(Point p, String nom) throws RemoteException;
  Point position(String nom) throws RemoteException;
  int nombreles() throws RemoteException;
}
```

客户端的实现：

```java
import java.rmi.*;
public class Client {
  public static void main(String[] args) {
    try {
      Position b =(Position) Naming.lookup("Data");
      System.out.println(b.nombreles());
      b.insererTable(new Point(11,5),"P0");
      b.insererTable(new Point(14,9),"P1");
      System.out.println(b.nombreles());
      System.out.println(b.position("P0"));
      System.out.println(b.position("P1"));
    } catch (Exception e) {
      System.out.println(e) ;
    }
  }
}
```

问题发生在`Point`类型对象的传输上，该对象必须是`Serializable`（序列化的）。

### 传输远程对象：RMI 多线程服务器（聊天室）

- 每个客户端都是一个线程，并有三种可能的动作：加入、说话或离开。
- 服务器现在必须维护一个分布式对象列表（`Remote`）。
- 使用`synchronized`来保证数据的一致性。
- 客户端的操作必须显示给其他客户端。
- 使用`Jframe`（Swing）实现线程。

#### 第一个客户端

![images](img/f0111-01.jpg)

#### 第二个客户端

![images](img/f0111-02.jpg)

#### 第三个客户端

![images](img/f0112-01.jpg)

当第三个客户端断开连接时，第一个客户端应该看到此内容：

![images](img/f0112-02.jpg)

第二个客户端如下：

![images](img/f0113-01.jpg)

```java
import java.rmi.*;
public interface ChatInterface extends Remote {
  public void rejoindre (Notify n) throws RemoteException;
  public void parler (Notify n, String s) throws RemoteException;
  public void laisser (Notify n) throws RemoteException;
}
import java.rmi.*;
public interface Notify extends Remote { // Notify 指向客户端
  public String getName() throws RemoteException;
  public void setName(String s) throws RemoteException;
  public void joinMessage (String name) throws RemoteException;
  public void sendMessage (String name, String message) throws RemoteException;
  public void exitMessage (String name) throws RemoteException;
} // name 是客户端的名字。
```

#### 服务器端

```java
public class Serveur extends UnicastRemoteObject implements ChatInterface { 
private Collection<Notify> threadList = new ArrayList<Notify>();
  public Serveur() throws RemoteException {}
public synchronized void join (Notify n) throws RemoteException {
threadList.add(n);
// 遍历列表
for (Iterator i = threadList.iterator();i.hasNext(); ) {
Notify client = (Notify)i.next(); // 从列表中获取元素
client.joinMessage(n.getName());
               }
  }
…
…
```

`Collection`是由`ArrayList`实现的接口。

`iterator()`是`Collection`的一个方法，返回表上的`Iterator`（`Iterator`是一个用于指定表上迭代器的接口）。`hasNext()`和`next()`是`Iterator`的方法。

实现`Notify`的类部分：

![images](img/f0114-01.jpg)

### 4.2.2.5 RMI 中的安全管理

在下载代码时，安全性非常重要（执行来自远程服务器的代码可能是危险的）。能够从远程传输可执行代码在理论上是一个安全漏洞。在本地传输代码时，没有安全问题。

- **解决方案：**
  - 实现一个“安全管理器”（security manager）。

- **Java 中的通用解决方案：**
  - 使用`java.lang.SecurityManager`（自`Object`）。
  - 这允许指定访问文件等权限。

- **针对 RMI 的特定解决方案：**
  - 使用`java.rmi.RMISecurityManager`。
  - `public class RMISecurityManager extends SecurityManager`。

使用 RMI，有两种管理安全性的方法：

- 使用`SecurityManager`的子类代替`RMISecurityManager`。

```java
public class SecurityManagerOu extends SecurityManager{
public void checkPermission(Permission perm) { }
```

- 将`RMISecurityManager`结合（从 Java 2 开始）描述权限的文件：`java.policy`。`java.policy`文件定义了安全策略以指定授权的操作。

路径位于`C:\Program Files (x86)\Java\jdk1.8.0_25\jre\lib\security`。

`java.policy`的内容示例：

```java
grant {
permission java.security.AllPermission;
};
```

它允许所有方法调用（无安全策略）。

```java
grant {
permission java.net.SocketPermission "*:1024-6535", "connect,accept";
permission java.net.SocketPermission "*:80", "connect";
permission java.io.FilePermission "C:\\temp\\m2d.txt", "read";
permission java.io.FilePermission "C:\\temp\\test.exe ", "read, write,delete,execute";
};
```

它允许所有 RMI 客户端在 1024 到 6535 端口建立套接连接，并连接到所有机器上的默认服务器（80 端口）。它还定义了与文件相关的权限。

要安装安全管理器，执行以下代码：`System.setSecurityManager(new SecurityManager())`。

示例：

```java
public static void main (String args[]) { // 服务器
System.setSecurityManager (new SecurityManager ()) ;
try {
LocateRegistry.createRegistry(1099);
} catch (RemoteException e) {
System.err.println("rmiregistry is already launched on this port");
System.exit(1);
}
```

使用`java.policy`：

```bash
$ javac Server.java
$ java -Djava.security.policy=java.policy Server
```

我们也可以在 TLS 下使用 RMI：



传输层安全（`TLS`），以前称为安全套接层（`SSL`），是一种安全协议。能够远程传输可执行代码在理论上是一个安全漏洞。在本地传输代码时，没有安全问题。

**目标：**

-我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。客户端身份验证。
- 可选的身份验证。
- 数据的机密性。
- 数据的完整性。
- 数据的会话。
- 数据的授权。
- 数据的传输层。
- `TLS` 传输。
- 自 Java 5.0 以后。
- 数据的加密版本。
- `JSSE` 扩展。
- `JSSE` API。
- `JSSE` 类分组。

![image](img/fig-13)

图 13. 带 `TLS` 的 `RMI`。

- `TLS` 传输。
- 传输层。

# 目标：增加动态性

在这种情况下，每个元素（客户端或服务器）都可以不区别地胜任两种角色（同时作为客户端和服务器）。

服务器对客户端的调用被称为回调（callbacks）。

- 由于服务器并不知道此类方法的实现方式，且由于其执行时间可能很长，因此回调通常被实现为异步操作。
- 服务器避免了通过同步调用对其他客户端造成惩罚。
- 同步调用 → 阻塞执行以等待结果。
- 回调是一种机制，允许在 `RMI` 中引入异步性，而 `RMI` 的调用在本质上是同步且阻塞的。
- 异步方法始终是 `void` 类型（不返回结果）。
- 发调用的程序不需要立即获得结果；否则，它将被阻塞。
- 在 Java 中，方法通常都是同步的，但线程的 `start()` 方法除外。
- `start()` 不阻塞调用线程。
- 客户端将回调对象（远程对象）作为参数传递给服务器。
- 客户端留出其坐标以便后续进行回调。
- 第一个接口：`ServerInterface`（服务器端实现）。
- 服务器在对象上执行异步调用。
- 必须由一个线程执行回调。
- 第二个接口：`InterfaceCallback`（客户端端实现）。

![image](img/fig4-14.jpg)

**图 4.14.** `RMI` 中的回调。如需图片的彩色版本，请访问 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)

为了执行回调，我们需要以下六个类：

![image](img/fig4-15.jpg)

**图 4.15.** 回调所需的类。如需该彩色彩色版本，请访问 [www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)

`InterfaceCalback.java`：包含回调方法的接口。该接口由 `Callback.java` 实现。

该接口的示例如下：

```java
import java.rmi.Remote ;
import java.rmi.RemoteException ;
public interface InterfaceCallback extends Remote {
  public void doCallback () throws RemoteException ;
}
```

在客户端实现的是该回调方法的接口。

`Callback.java`：实现回调方法的类。该类仅在客户端可用，用于实现回调方法。

```java
import java.rmi.RemoteException ;
import java.rmi.server.UnicastRemoteObject ;
public class Callback extends UnicastRemoteObject implements
InterfaceCallback {
public Callback ( ) throws RemoteException {}
public void doCallback () throws RemoteException {
  System.out.println ("Bonjour tous le monde") ;
}
}
```

`Servant.java`：启动回调方法的线程。

```java
import java.rmi.*;
public class Servant extends Thread {
private InterfaceCallback obj ;
public Servant (InterfaceCallback obj) {
this.obj = obj ;
}
public void run ( ) { // 在独立线程中执行
try {Thread.sleep (3000) ; } catch ( InterruptedException e ) { }
try {obj.doCallback () ; // 执行回调，调用客户端的方法
}
catch (RemoteException e ) {
  System.err.println ("Return call failed: " + e ) ;
}
}
}
```

`InterfaceServer.java`：包含服务器用于回调客户端方法的接口，该方法的参数是需要被回调的对象。此接口由 `Server.java` 实现。

```java
import java.rmi.Remote;
import java.rmi.RemoteException;
public interface InterfaceServeur extends Remote {
  public void callMeBack (InterfaceCallback obj) throws RemoteException
;
}
```

`callMeBack` 方法由客户端使用。

`Client.java`：创建对象并将其传递给服务器（调用服务器端实现的 `InterfaceServer` 方法）。

实现一个可被回调的经典 `RMI`：

```java
import java.rmi.Naming ;
public class Client {
public static void main( String [ ] args ) throws Exception {
Callback obj = new Callback ( ) ; // 创建回调对象
InterfaceServeur serv= (InterfaceServeur) Naming.lookup ("Server");
System.out.println ("Starting call");
serv.callMeBack (obj) ; // 调用请求
}
}
```

`Server.java`：实现回调客户端的方法，通过传递上一个线程接收到的对象来实现。

```java
import java.rmi.Naming;
import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.server.UnicastRemoteObject;
public class Server extends UnicastRemoteObject implements
InterfaceServer {
public Server ( ) throws RemoteException { }
public void callMeBack (InterfaceCallback obj) throws RemoteException {
Servant servant = new Servant (obj) ; // 创建线程
servant.start ( ) ; // 初始化线程
}
public static void main( String [ ] args ) throws Exception {
try {LocateRegistry.createRegistry(1099);} catch (RemoteException e1) {
    System.err.println("rmiregistry is already ready"); }
Server serv = new Server ( )
Naming.bind ("Server", serv) ;
}
```

执行结果：

服务器端：就绪。

客户端端：启动中。

Hello。

## 4.2 `RMI` 中的垃圾回收

- 困难：远程。
- 目标：防止引用丢失。在 `RMI` 中：通过以下机制管理：

    - *引用计数*：对象的客户端数量。
        - 每次传输 +1。
        - 每次结束 -1。
    - *租约 (Lease)*：对对象的保留限制时间。
        - 默认为 600000 毫秒（10 分钟），可通过属性 `java.dgc.leaseValue` 修改。
        - 程序时修改：`-Ddgc.leaseValue=20000`。

### 练习 1：线程的生命周期

考虑以下代码：

```java
class Parrot4 extends Thread{
  private String cri = null;
  private int fois = 0;
  public Parrot4 (String s, int i) {
    cri = s;
    fois = i;
  }
  public void run() {
    System.out.println("Thread parrot:" + Thread.currentThread().getName());
    for (int n=0; n<fois; n++) {
      try { Thread.sleep(1000); }
      catch(InterruptedException e) { }
      System.out.println(cri);
    }
  }
}
```

```java
class ChatAndLaunchParrot{
  public static void main(String args[]) {
    Parrot4 parrot = new Parrot4("coco",5);
    parrot.start();
    System.out.println("Thread chatty : " + Thread.currentThread().getName());
    for (int n=0; n<15; n++) {
      try { Thread.sleep(1000); }
      catch(InterruptedException e) { }
      System.out.print("Thread parrot isAlive: "+ parrot.isAlive() + "\t");
      blabla();
    }
  }
  private static void blabla() {
    System.out.println("blabla");
  }
}
```

问题：启动上述程序的执行。

主线程的名称是什么？默认给另一个线程命什么名称？`isAlive()` 方法的作用是什么？*提示*：类方法 `currentThread()` 返回 `Thread` 对象的指针并调用该方法。

### 练习 2：不同线程的属性

考虑以下两个类：

```java
class Parrot5 extends Thread {
  private String cri = null;
  private int fois = 0;
  public Parrot5(String s, int i) {
    super("parrot");
    cri = s;
    fois = i;
  }
  public void run(){
    afficheThreads();
    for (int n=0; n<fois; n++) {
      try { Thread.sleep(1000); }
      catch(InterruptedException e) { }
      System.out.println(cri) 
    }
    afficheThreads(); }
  private void afficheThreads() {
    Thread[] tabThread = new Thread[Thread.activeCount()];
    int nbrThread = Thread.enumerate(tabThread);
    for (int i = 0; i < nbrThread ; i++)
      System.out.println(i + "-ieme Thread: " + tabThread[i].getName());
  }
}
```

```java
class ChatAndLaunchParrot5 {
  public static void main(String args[]) {
    Thread.currentThread().setName("chatty");
    Parrot5 parrot = new Parrot5("coco",15);
    parrot.start();
    for (int n=0; n<5; n++) {
      try { Thread.sleep(1000); }
      catch(InterruptedException e) { }
      blabla();
    }
  }
  private static void blabla() {
    System.out.println("blabla");
  }
}
```

提示：方法 `setName(String name)` 允许为线程命名。`Thread` 构造器提供了如下方式进行命名的可能：`Thread (String name)`。

类方法 `activeCount()` 返回调用线程组中活跃线程的数量。

类方法 `enumerates(Thread[] table)` 在给定的表中存储调用线程组及其子组中活跃线程的引用。它返回获取到的活跃线程数量。

问题：启动上述程序的执行。

过程 `displayThreads()` 在 `run()` 方法的循环之前之后各都会被调用。

循环之前的活跃线程为：

编号 0 线程: chatty

第 1 个线程: parrot

循环结束后，它们变成了：

编号 0 线程: parrot

第 1 个线程: DestroyJavaVM

解释这一结果，`DestroyJavaVM` 是什么？

### 练习 3：并行的四个计数器

本练习的目标是创建四个并行执行的计数器。

每个“计数器”都有一个名称（例如 Toto），并从 1 计数到 10。它在每个数字之间会随机暂停（例如 0 到 5000 毫秒）。每个计数器显示一个数字（例如 Toto 将显示 "Toto: 3"）；当计数完成时，`n` 显示一条诸如“Toto 已完成计数到 10”的消息。

计数器类拥有一个单一属性，即 `String` 类型的计数器的名称。

编写计数器类并通过启动 4 个计数到 10 的计数器对其进行测试。观察哪一个先完成（四个计数器分别命名为 Tata, Titi, Toto, Tutu）。

制作两个版本：一个是使用 `Thread` 子类创建线程，另一个是使用实现 `Runnable` 的独立类实例创建线程。

### 练习 4：互斥锁中的资源

考虑以下三个 java 类：

```java
public class Printer1 {
  private String text;
  public Printer1() {
    text="";
  }
  public void print(String t) {
    text=t;
    for (int j=0; j<text.length()-1; j++) {
      System.out.print(text.charAt(j));
      try { Thread.sleep(100);} }
      catch (InterruptedException e) {};
    } // end for
    System.out.println(text.charAt(text.length()-1));
  }
}
```

```java
public class Prog56 {
  public static void main (String argv[]) {
    Writer2 writerA, writerB;
    Printer1 print= new Printer1();
    writerA = new Writer2("ABC", print);
    writerB = new Writer2("XYZ", print);
    writerA.start();
    writerB.start();
  }
}
```

```java
public class Writer2 extends Thread {
  private String text;
  private Printer1 print;
  public Writer2(String t, Printer1 i) {
    print=i;
    text=t;
  }

  public void run() {
    for (int i=0; i<10; i++) {
      print.print(text);
      try { sleep((long)(Math.random() * 100)); }
      catch (InterruptedException e) {}
    } // end for
    System.out.println("writer of "+text+" has finished");
  }
}
```

- 在 `Printer1` 类中，描述 `print` 方法的行为。
- 描述类型为 `Writer2` 的线程（`run()` 方法）。



- 启动`Prog56`的执行。为什么结果是不可读的？

- 在`Printer1`类中将`print`方法的签名更改为`public void print(String t)`并重新执行`Prog56`。

- `synchronized`的作用是什么？

### 练习 5：编写一个带有初始延迟和周期性的任务

我们希望教一个学生 7 的乘法表，因此我们想编写一个任务，每 4 秒显示一次 7 的乘法表，且初始延迟为 2 秒。结果如下形式所示：

你仍然想学习乘法表吗？(y/n) 7 的乘法表是：

1 * 7 = 7

2 * 7 = 14

3 * 7 = 21

4 * 7 = 28

5 * 7 = 35

6 * 7 = 42

7 * 7 = 49

8 * 7 = 56

9 * 7 = 63

10 * 7 = 70

提示：任何非“y”的回答都会取消程序。

### 练习 6：共享变量：内部类

考虑以下两个类（`Parrot0`类被称为内部类，因为它位于`MathsParrots0`类内部），并且只有一个名为`MathsParrots0.java`的文件。

```java
public class MathsParrots0{
  private int counter;
  public static void main(String args[]) {
    new MathsParrots0();
  }
  public MathsParrots0() {
    counter = 1;
    Parrot20 parrotA = new Parrot20("coco", 10);
    Parrot20 parrotB = new Parrot20("hello", 10);
    parrotA.start();
    parrotB.start();
    try {
      parrotA.join();
      parrotB.join();
    } catch (InterruptedException e) { }
    System.out.println("counter = "+counter);
  }

  class Parrot20 extends Thread {
    private String cri = null;
    private int fois = 0;
    public Parrot20(String s, int i) {
      cri = s;
      fois = i;
    }
    public void repeat() {
      String repeat = cri + " " + counter;
      System.out.println(repeat);
      counter++;
      try { Thread.sleep((int)(Math.random() * 1000)); }
      catch (InterruptedException e) { }
    }
    public void run(){
      for (int n=0; n<fois; n++) repeat();
    }
  }
}
```

- 启动并检查执行情况。

- 提示：`join()`用于在线程结束前显示`counter`的值。由于 Java 的可见性规则，`counter`变量对于`Parrot20`类是可见，因此对于`parrotA`和`parrotB`线程也是可见的。这两个线程访问一个共享空间，而不是进程拥有自己独立的工作空间。

- 复用竞赛示例来模拟 A, B, C, D, E 五个跑步者的竞赛，并显示每个跑步者的排名。

执行示例：

- A 第一到达

- B 第二到达

- D 第三到达

- ……

### 练习 7：共享变量：全局变量（静态/static）

在开始之前：在 Java 中，每个字母可以通过`char`类型进行编码，该类型也有整数值。测试并检查以下代码：

```java
System.out.println('A');
System.out.println('A'+0);
System.out.println('A'+1);
System.out.println((char)('A' + 0));
System.out.println((char)('A' + 1));
System.out.println("显示字母表：");
for (int i = 0; i < 26; i++) {
  System.out.print((char)('A' + i)+" ");
}
```

- 复用竞赛示例来模拟 A, B, C, D, E 五个跑步者的竞赛，并显示每个跑步者的排名。你应该使用循环来启动五个线程。

执行示例：

- A 第一到达

- B 第二到达

- D 第三到达

- ……

- 模拟四个线程 A, B, C 和 D，它们分别计算 4、5、6 和 7 的阶乘。如果终止的顺序是 A, B, C 和 D，你还应该显示：

  1. A 非常快

  2. B 很快

  3. C 中等

  4. D 慢

### 练习 8：线程同步

本练习处理银行账户并发访问（通用资源共享）的问题。对于以下`Counter`类，其`Nulloperation`方法旨在将级别保持在 0。

```java
public class Counter {
  private int balance = 0;
  public void operationNulle(int sum) {
    balance += sum;
    System.out.print(" add " + sum);
  balance -= sum;
    System.out.println(" remove " + sum);
  }
  public int getBalance() {
    return balance;
  }
}
```

考虑以下包含`Operation`线程和主线程的类：

```java
public class Operation extends Thread {
  private Counter Counter;
  public Operation(String nom, Counter Counter) {
        super(name);
  this.Counter = Counter;
  }
public void run() {
        while (true) {
    int i = (int) (Math.random() * 1001);
    String nom = getName();
    System.out.println(" I am thread:" +name);
    Counter.operationNulle(i);
    int balance = Counter.getBalance();
    if (balance!= 0) {
      System.out.println(" I am thread " + name + ":balance=" +
      balance);
      System.exit(1);
    }
  }
  }
public static void main(String[] args) {
  Counter Counter = new Counter();
  for (int i = 0; i < 3; i++) {
    Operation operation = new Operation("A" + i, Counter);
    operation.start();
  }
}
```

检查代码并执行`Operation`类。

确定一个出现的问题：`operationNull`应该让`Counter`保持不变（0），但过了一会儿后发生了变化。请解释原因。

修改代码以防止此问题。

### 练习 9：applet 与线程

applet 是一个小型 Java 程序，旨在通过浏览器下载并执行。一旦编译完成，applet 必须在`html`文件中调用。然后，`html`文件将在浏览器或`appletviewer`工具中可视化。

将以下代码复制到名为`Prog11.java`的文件中：

```java
import java.awt.Graphics ;
import java.applet.Applet;
public class Prog11 extends Applet {
  public void paint (Graphics g) {
  g.drawLine(10, 30, 200, 30);
  g.drawRect (20, 40, 100, 50);
  g.drawOval (140, 40, 50, 50);
  g.drawString ("hello!", 10, 120);
  }
}
```

我们的类继承自`Applet`：简单使用`Graphics`类重新定义`paint`方法。

将以下代码复制到标题为`drawing.html`的文件中：

```html
<html><body><applet code="Prog11.class" width=350 height=150></applet></body></html>
```

执行`drawing.html`（直接点击文件），或使用命令行`appletviewer drawing.html`。你也可以在 Netbeans 下执行`Prog11.java`。对于浏览器，只需确保 java 插件存在。

解释`paint`中的不同方法。

考虑以下类：

```java
import java.util.concurrent.Semaphore;
class Process2 extends Thread{
  private int id;
  private Semaphore sem;
  public Process2(int i, Semaphore s) {
    id = i;
    sem = s;
  }
  private void busy()
  {try{sleep((int)(Math.random()*1000));}
  catch (InterruptedException e){}
  private void noncritical() {
    System.out.println("Thread " + id + "is not in the critical section");
    busy();
  }
  private void critical() {
    System.out.println("Thread " + id + "enters the critical section");
    busy();
    System.out.println("Thread " + id + "exits the critical section");
  }
  public void run() {
    noncritical();
    try {
      sem.acquire();
    } catch (InterruptedException e){ }
    critical();
    sem.release();
  }
  public static void main(String[] args) {
  Semaphore sem = new Semaphore(1);
  Process2[] p = new Process2[4];
  for (int i = 0; i < 3; i++) {
    p[i] = new Process2(i, sem);
    p[i].start();
  }
}
```

### 练习 10：使用信号量的并发访问

考虑以下类：

```java
public class CounterThread extends Applet implements Runnable {
  Thread t;
  int Count;
  public void init() {
  Count=0;
  t=new Thread(this); // t 必须接受对象作为参数
  t.start();
  }
  public void run() {
  while (Count < 20) {
    Count++;
    repaint();
    try {Thread.sleep(100); } catch (InterruptedException e) {}
  }
  public void paint(Graphics g) {
  g.drawString(Integer.toString(Count),10,10);
  System.out.println("Count="+Count);
  }
}
```

执行 applet 并检查结果。

可以用不同的方式声明`CounterThread`类吗？为什么？

可以将这个传递给`Thread`构造函数吗？为什么？

将之前的代码加速十倍且不停止。

此变量必须在类`Car`（代表`Car`行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car`类），后者的特征是一个整数型*数量*`i`和一个*信号量*`s`。

### 练习 13：哲学家晚餐

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和`Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然，还要确保没有相互阻塞现象。

### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java`和`Consumer.java`。

`Producer`和`Consumer`共享一个类型为`B`的对象`b`。



### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {
private Object [ ] buffer;
private int taille ;
private int prem, der, nbObj;
public B (int t) {
taille = t;
buffer = new Object [taille];
prem = 0;
der = 0;
nbObj = 0;
}
public synchronized void depose (Object obj) {
while (cond1) try {wait ();}catch ( InterruptedException e) {}
buffer [der] = obj;
der = (der + 1) % size;
nbObj = nbObj + 1;
notify ();
}
public synchronized Object collected () {
while (cond2) try {wait ();}catch ( InterruptedException e) {}
Object obj = buffer [prem];
buffer [prem] = null;
prem = (prem + 1) % size;
nbObj = nbObj - 1;
notify ();
return (obj);
}
} // end B

class Producer implements Runnable {
private B b;
private int val;
public Producer (B b) {this.b = b;}
public void run () {
while (true) {
b.putsdown (new Integer (val));
System.out.println (Thread.currentThread ().getName () +"has put down" +
val);
val ++;
try {Thread.sleep ((int)( Math.random ()*100));}catch ( Interrupted
Exception e) {}
}
}}// end run
}//endProducer

class Consumer implements Runnable {
private B b;
public Consumer (B b) {this.b = b;}
public void run () {
Integer val;
while (true) {
val = (Integer) b.preleve();
System.out.println ( Thread.currentThread ().getName () +"collected" + val );
try {Thread.sleep ((int)( Math.random ()*300));}catch ( InterruptedException Exception e) {}
}
}// end run
}// end Consumer
```

* – 通过给出 `cond1` 和 `cond2` 来完善类 `B` 的代码。

* – 在 `putsdown` 方法中，指令 `der = (der + 1) % size` 的作用是什么？

* – 根据上一个问题，用于类型 `B` 对象的 `buffer` 的类型是什么？

* – 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型*数量* `i` 和一个*信号量* `s`。

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和 `Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然的，还要确保没有相互阻塞现象。



### 练习 13：哲学家进餐问题

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和 `Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然的，还要确保没有相互阻塞现象。

### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {
private Object [ ] buffer;
private int taille ;
private int prem, der, nbObj;
public B (int t) {
taille = t;
buffer = new Object [taille];
prem = 0;
der = 0;
nbObj = 0;
}
public synchronized void depose (Object obj) {
while (cond1) try {wait ();}catch ( InterruptedException e) {}
buffer [der] = obj;
der = (der + 1) % size;
nbObj = nbObj + 1;
notify ();
}
public synchronized Object collected () {
while (cond2) try {wait ();}catch ( InterruptedException e) {}
Object obj = buffer [prem];
buffer [prem] = null;
prem = (prem + 1) % size;
nbObj = nbObj - 1;
notify ();
return (obj);
}
} // end B

class Producer implements Runnable {
private B b;
private int val;
public Producer (B b) {this.b = b;}
public void run () {
while (true) {
b.putsdown (new Integer (val));
System.out.println (Thread.currentThread ().getName () +"has put down" +
val);
val ++;
try {Thread.sleep ((int)( Math.random ()*100));}catch ( Interrupted
Exception e) {}
}
}}// end run
}//endProducer

class Consumer implements Runnable {
private B b;
public Consumer (B b) {this.b = b;}
public void run () {
Integer val;
while (true) {
val = (Integer) b.preleve();
System.out.println ( Thread.currentThread ().getName () +"collected" + val );
try {Thread.sleep ((int)( Math.random ()*300));}catch ( InterruptedException Exception e) {}
}
}// end run
}// end Consumer
```

* – 通过给出 `cond1` 和 `cond2` 来完善类 `B` 的代码。

* – 在 `putsdown` 方法中，指令 `der = (der + 1) % size` 的作用是什么？

* – 根据上一个问题，用于类型 `B` 对象的 `buffer` 的类型是什么？

* – 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型*数量* `i` 和一个*信号量* `s`。



### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {
    private Object[] buffer;
    private int taille;
    private int prem, der, nbObj;

    public B(int t) {
        taille = t;
        buffer = new Object[taille];
        prem = 0;
        der = 0;
        nbObj = 0;
    }

    public synchronized void depose(Object obj) {
        while (cond1) try { wait(); } catch (InterruptedException e) {}
        buffer[der] = obj;
        der = (der + 1) % size;
        nbObj = nbObj + 1;
        notify();
    }

    public synchronized Object collected() {
        while (cond2) try { wait(); } catch (InterruptedException e) {}
        Object obj = buffer[prem];
        buffer[prem] = null;
        prem = (prem + 1) % size;
        nbObj = nbObj - 1;
        notify();
        return (obj);
    }
} // end B

class Producer implements Runnable {
    private B b;
    private int val;

    public Producer(B b) { this.b = b; }

    public void run() {
        while (true) {
            b.putsdown(new Integer(val));
            System.out.println(Thread.currentThread().getName() + "has put down" + val);
            val++;
            try { Thread.sleep((int)(Math.random() * 100)); } catch (InterruptedException e) {}
        }
    }
} // end run
// end Producer

class Consumer implements Runnable {
    private B b;

    public Consumer(B b) { this.b = b; }

    public void run() {
        Integer val;
        while (true) {
            val = (Integer) b.preleve();
            System.out.println(Thread.currentThread().getName() + "collected" + val);
            try { Thread.sleep((int)(Math.random() * 300)); } catch (InterruptedException e) {}
        }
    }
} // end run
// end Consumer
```

* – 通过给出 `cond1` 和 `cond2` 来完善类 `B` 的代码。

* – 在 `putsdown` 方法中，指令 `der = (der + 1) % size` 的作用是什么？

* – 根据上一个问题，用于类型 `B` 对象的 `buffer` 的类型是什么？

* – 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型*数量* `i` 和一个*信号量* `s`。

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和 `Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然的，还要确保没有相互阻塞现象。



– 上上上一个，` ``` ` 的类型 `B` 对象的 `buffer` 的类型是什么？

- 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：

`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型数量 `i` 和一个信号量 `s`。

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

- 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 `"main"` 方法等）和 `Philo`（对应于哲学家活动的线程）。

#### 执行示例

```text
Philo0 is thinking

Philo2 is thinking

Philo1 is thinking

Philo3 is thinking

Philo4 is thinking

Philo4 wants to eat

Philo4 is eating

Philo0 wants to eat

Philo3 wants to eat

Philo1 wants to eat

Philo1 is eating

Philo2 wants to eat

Philo4 has finished eating

Philo3 is eating

Philo4 is thinking

Philo1 has finished eating

Philo1 is thinking

Philo0 is eating

Philo4 wants to eat

Philo1 wants to eat

Philo3 has finished eating

Philo3 is thinking

Philo2 is eating

Philo0 has finished eating

Philo0 is thinking

Philo4 is eating

…
```

- 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然，还要确保没有相互阻塞现象。

### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {

    private Object[] buffer;

    private int taille;

    private int prem, der, nbObj;

    public B(int t) {
        taille = t;

        buffer = new Object[taille];

        prem = 0;

        der = 0;

        nbObj = 0;
    }

    public synchronized void depose(Object obj) {
        while (cond1)
            try {
                wait();
            } catch (InterruptedException e) {
            }

        buffer[der] = obj;

        der = (der + 1) % size;

        nbObj = nbObj + 1;

        notify();
    }

    public synchronized Object collected() {
        while (cond2)
            try {
                wait();
            } catch (InterruptedException e) {
            }

        Object obj = buffer[prem];

        buffer[prem] = null;

        prem = (prem + 1) % size;

        nbObj = nbObj - 1;

        notify();

        return obj;
    }
} // end B

class Producer implements Runnable {

    private B b;

    private int val;

    public Producer(B b) {
        this.b = b;
    }

    public void run() {
        while (true) {
            b.putsdown(new Integer(val));

            System.out.println(
                Thread.currentThread().getName() + "has put down" + val
            );

            val++;

            try {
                Thread.sleep((int) (Math.random() * 100));
            } catch (InterruptedException e) {
            }
        }
    }
} // end run

} // end Producer

class Consumer implements Runnable {

    private B b;

    public Consumer(B b) {
        this.b = b;
    }

    public void run() {
        Integer val;

        while (true) {
            val = (Integer) b.preleve();

            System.out.println(
                Thread.currentThread().getName() + "collected" + val
            );

            try {
                Thread.sleep((int) (Math.random() * 300));
            } catch (InterruptedException Exception e) {
            }
        }
    } // end run
} // end Consumer
```

- 通过给出 `cond1` 和 `cond2` 来完善类 `B` 的代码。

- 在 `putsdown` 方法中，指令 `der = (der + 1) % size` 的作用是什么？

- 根据上一个问题，用于类型 `B` 对象的 `buffer` 的类型是什么？

- 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：

`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型数量 `i` 和一个信号量 `s`。

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

- 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 `"main"` 方法等）和 `Philo`（对应于哲学家活动的线程）。

#### 执行示例

```text
Philo0 is thinking

Philo2 is thinking

Philo1 is thinking

Philo3 is thinking

Philo4 is thinking

Philo4 wants to eat

Philo4 is eating

Philo0 wants to eat

Philo3 wants to eat

Philo1 wants to eat

Philo1 is eating

Philo2 wants to eat

Philo4 has finished eating

Philo3 is eating

Philo4 is thinking

Philo1 has finished eating

Philo1 is thinking

Philo0 is eating

Philo4 wants to eat

Philo1 wants to eat

Philo3 has finished eating

Philo3 is thinking

Philo2 is eating

Philo0 has finished eating

Philo0 is thinking

Philo4 is eating

…
```

- 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然，还要确保没有相互阻塞现象。

### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {

    private Object[] buffer;

    private int taille;

    private int prem, der, nbObj;

    public B(int t) {
        taille = t;

        buffer = new Object[taille];
```



### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {
    private Object[] buffer;
    private int taille;
    private int prem, der, nbObj;

    public B(int t) {
        taille = t;
        buffer = new Object[taille];
        prem = 0;
        der = 0;
        nbObj = 0;
    }

    public synchronized void depose(Object obj) {
        while (cond1) try { wait(); } catch (InterruptedException e) {}
        buffer[der] = obj;
        der = (der + 1) % size;
        nbObj = nbObj + 1;
        notify();
    }

    public synchronized Object collected() {
        while (cond2) try { wait(); } catch (InterruptedException e) {}
        Object obj = buffer[prem];
        buffer[prem] = null;
        prem = (prem + 1) % size;
        nbObj = nbObj - 1;
        notify();
        return (obj);
    }
} // end B

class Producer implements Runnable {
    private B b;
    private int val;

    public Producer(B b) { this.b = b; }

    public void run() {
        while (true) {
            b.putsdown(new Integer(val));
            System.out.println(Thread.currentThread().getName() + "has put down" + val);
            val++;
            try { Thread.sleep((int)(Math.random() * 100)); } catch (InterruptedException e) {}
        }
    }
} // end run

// end Producer

class Consumer implements Runnable {
    private B b;

    public Consumer(B b) { this.b = b; }

    public void run() {
        Integer val;
        while (true) {
            val = (Integer) b.preleve();
            System.out.println(Thread.currentThread().getName() + "collected" + val);
            try { Thread.sleep((int)(Math.random() * 300)); } catch (InterruptedException e) {}
        }
    }
} // end run

// end Consumer
```

* – 通过给出 `cond1` 和 `cond2` 来完善类 `B` 的代码。
* – 在 `putsdown` 方法中，指令 `der = (der + 1) % size` 的作用是什么？
* – 根据上一个问题，用于类型 `B` 对象的 `buffer` 的类型是什么？
* – 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型*数量* `i` 和一个*信号量* `s`。

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和 `Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然的，还要确保没有相互阻塞现象。



### 练习 13：哲学家晚餐

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和 `Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然的，还要确保没有相互阻塞现象。

### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {
    private Object[] buffer;
    private int taille;
    private int prem, der, nbObj;

    public B(int t) {
        taille = t;
        buffer = new Object[taille];
        prem = 0;
        der = 0;
        nbObj = 0;
    }

    public synchronized void depose(Object obj) {
        while (cond1) try { wait(); } catch (InterruptedException e) {}
        buffer[der] = obj;
        der = (der + 1) % size;
        nbObj = nbObj + 1;
        notify();
    }

    public synchronized Object collected() {
        while (cond2) try { wait(); } catch (InterruptedException e) {}
        Object obj = buffer[prem];
        buffer[prem] = null;
        prem = (prem + 1) % size;
        nbObj = nbObj - 1;
        notify();
        return (obj);
    }
} // end B

class Producer implements Runnable {
    private B b;
    private int val;

    public Producer(B b) { this.b = b; }

    public void run() {
        while (true) {
            b.putsdown(new Integer(val));
            System.out.println(Thread.currentThread().getName() + "has put down" + val);
            val++;
            try { Thread.sleep((int)(Math.random() * 100)); } catch (InterruptedException e) {}
        }
    }
} // end Producer

class Consumer implements Runnable {
    private B b;

    public Consumer(B b) { this.b = b; }

    public void run() {
        Integer val;
        while (true) {
            val = (Integer) b.preleve();
            System.out.println(Thread.currentThread().getName() + "collected" + val);
            try { Thread.sleep((int)(Math.random() * 300)); } catch (InterruptedException e) {}
        }
    }
} // end Consumer
```

* – 通过给出 `cond1` 和 `cond2` 来完善类 `B` 的代码。

* – 在 `putsdown` 方法中，指令 `der = (der + 1) % size` 的作用是什么？

* – 根据上一个问题，用于类型 `B` 对象的 `buffer` 的类型是什么？

* – 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型*数量* `i` 和一个*信号量* `s`。



此变量必须在类`Car`（代表`Car`行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car`类），后者的特征是一个整数型*数量*`i`和一个*信号量*`s`。

### 练习 13：哲学家晚餐

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和`Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然的，还要确保没有相互阻塞现象。

### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java`和`Consumer.java`。

`Producer`和`Consumer`共享一个类型为`B`的对象`b`。

```java
class B {
    private Object[] buffer;
    private int taille;
    private int prem, der, nbObj;

    public B(int t) {
        taille = t;
        buffer = new Object[taille];
        prem = 0;
        der = 0;
        nbObj = 0;
    }

    public synchronized void depose(Object obj) {
        while (cond1) try { wait(); } catch (InterruptedException e) {}
        buffer[der] = obj;
        der = (der + 1) % taille;
        nbObj = nbObj + 1;
        notify();
    }

    public synchronized Object collected() {
        while (cond2) try { wait(); } catch (InterruptedException e) {}
        Object obj = buffer[prem];
        buffer[prem] = null;
        prem = (prem + 1) % taille;
        nbObj = nbObj - 1;
        notify();
        return (obj);
    }
} // end B

class Producer implements Runnable {
    private B b;
    private int val;

    public Producer(B b) {
        this.b = b;
    }

    public void run() {
        while (true) {
            b.depose(new Integer(val));
            System.out.println(Thread.currentThread().getName() + " has put down " + val);
            val++;
            try {
                Thread.sleep((int)(Math.random() * 100));
            } catch (InterruptedException e) {}
        }
    }
} // end Producer

class Consumer implements Runnable {
    private B b;

    public Consumer(B b) {
        this.b = b;
    }

    public void run() {
        Integer val;
        while (true) {
            val = (Integer) b.collected();
            System.out.println(Thread.currentThread().getName() + " collected " + val);
            try {
                Thread.sleep((int)(Math.random() * 300));
            } catch (InterruptedException e) {}
        }
    }
} // end Consumer
```

* – 通过给出`cond1`和`cond2`来完善类`B`的代码。

* – 在`depose`方法中，指令`der = (der + 1) % taille`的作用是什么？

* – 根据上一个问题，用于类型`B`对象的`buffer`的类型是什么？

* – 编写类`Primary.java`，该类启动两个类型为`Producer`的线程`P`和一个类型为`Consumer`的线程`C`。线程`P`的名称必须是`P`，线程`C`的名称必须是`C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类`Car`（代表`Car`行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car`类），后者的特征是一个整数型*数量*`i`和一个*信号量*`s`。



### 练习 13：哲学家晚餐

这是一个非常经典的问题 [DIJ 70]。五位哲学家重聚在一起执行两项主要活动：思考和进食。每位哲学家随机花费一段时间进行思考，在可能的情况下在随机一段时间内进食，然后回到思考状态。当一个哲学家请求吃饭时，有一盘意大利面在等待。这五盘意大利面摆放在圆桌周围，如下图所示：

![images](img/f0143-01.jpg)

为了让哲学家能吃他的意大利面，需要两把叉子：他自己的（右侧的那把）和他左侧邻居的。自然地，如果其中一个邻居正在吃饭，哲学家就不能吃饭，必须等待一根或两把叉子释放。

该问题的解决方案必须尽可能优化：一个想吃但无法吃的哲学家必须等待轮到，而不应无谓地消耗 CPU 时间。

每位哲学家执行若干次循环：思考、请求食物、进食。

我们自然无法看到两个相邻的哲学家同时在吃饭。

一个线程可能会发现自己在不确定的时间内被拒绝访问资源。这时被称为该线程处于饥饿状态。哲学家在饥饿状态下，在规定时间内无法进食。然而，当所有哲学家试图同时拿叉子时，会出现一种相互阻塞（inter-blocking）的情况。

* – 使用 Java 编写一个解决方案，该方案使用两个类：`Dinner`（包含 "main" 方法等）和 `Philo`（对应于哲学家活动的线程）。

执行示例：

```
Philo0 is thinking
Philo2 is thinking
Philo1 is thinking
Philo3 is thinking
Philo4 is thinking
Philo4 wants to eat
Philo4 is eating
Philo0 wants to eat
Philo3 wants to eat
Philo1 wants to eat
Philo1 is eating
Philo2 wants to eat
Philo4 has finished eating
Philo3 is eating
Philo4 is thinking
Philo1 has finished eating
Philo1 is thinking
Philo0 is eating
Philo4 wants to eat
Philo1 wants to eat
Philo3 has finished eating
Philo3 is thinking
Philo2 is eating
Philo0 has finished eating
Philo0 is thinking
Philo4 is eating
…
```

* – 在测试期间，确保没有两个相邻的哲学家同时在吃饭，并且没有饥饿现象，当然的，还要确保没有相互阻塞现象。

### 练习 14：生产者/消费者

考虑以下三个 Java 类：`B.java`、`Producer.java` 和 `Consumer.java`。

`Producer` 和 `Consumer` 共享一个类型为 `B` 的对象 `b`。

```java
class B {

private Object [ ] buffer;

private int taille ;

private int prem, der, nbObj;

public B (int t) {

taille = t;

buffer = new Object [taille];

prem = 0;

der = 0;

nbObj = 0;

}

public synchronized void depose (Object obj) {

while (cond1) try {wait ();}catch ( InterruptedException e) {}

buffer [der] = obj;

der = (der + 1) % size;

nbObj = nbObj + 1;

notify ();

}

public synchronized Object collected () {

while (cond2) try {wait ();}catch ( InterruptedException e) {}

Object obj = buffer [prem];

buffer [prem] = null;

prem = (prem + 1) % size;

nbObj = nbObj - 1;

notify ();

return (obj);

}

} // end B

class Producer implements Runnable {

private B b;

private int val;

public Producer (B b) {this.b = b;}

public void run () {

while (true) {

b.putsdown (new Integer (val));

System.out.println (Thread.currentThread ().getName () +"has put down" +

val);

val ++;

try {Thread.sleep ((int)( Math.random ()*100));}catch ( Interrupted

Exception e) {}

}

}}// end run

}//endProducer

class Consumer implements Runnable {

private B b;

public Consumer (B b) {this.b = b;}

public void run () {

Integer val;

while (true) {

val = (Integer) b.preleve();

System.out.println ( Thread.currentThread ().getName () +"collected" + val );

try {Thread.sleep ((int)( Math.random ()*300));}catch ( InterruptedException Exception e) {}

}

}// end run

}// end Consumer
```

* – 通过给出 `cond1` 和 `cond2` 来完善类 `B` 的代码。

* – 在 `putsdown` 方法中，指令 `der = (der + 1) % size` 的作用是什么？

* – 根据上一个问题，用于类型 `B` 对象的 `buffer` 的类型是什么？

* – 编写类 `Primary.java`，该类启动两个类型为 `Producer` 的线程 `P` 和一个类型为 `Consumer` 的线程 `C`。线程 `P` 的名称必须是 `P`，线程 `C` 的名称必须是 `C`。共享缓冲区的大小为 4。

### 练习 15：线程同步

此变量必须在类 `Car`（代表 `Car` 行为的线程）中按如下声明：`static int cont=N;`

在此练习中需要一个单一的类（`Car` 类），后者的特征是一个整数型*数量* `i` 和一个*信号量* `s`。

### 练习 19：applet 与 TCP 套接

创建以下客户端/服务器模型：

![images](img/f0151-01.jpg)

*该图的彩色版本请参阅 [`www.iste.co.uk/benmammar/java.zip](http://www.iste.co.uk/benmammar/java.zip)*

改进客户端的 HMI（人机界面）和服务器端的处理逻辑，以执行经典的银行操作：

- 打开一个新的 `Counter`；
- 给已知的 `Counter` 增加金额；
- 从已知的 `Counter` 中取款；
- 显示已知 `Counter` 的账户持有人姓名和余额；
- 在已知账户持有人姓名时显示 `Counter` 编号；
- 显示所有 `Counters` 余额的平均值；
- 显示 `Counter` 列表。

### 练习 20：使用 TCP 套接字的算术运算

在此练习中，`ADD`、`MUL`、`DIV` 和 `SUB` 分别对应加、乘、除、减操作。

你的目标是使用 TCP 套接字创建一个客户端/服务器应用程序。

客户端向服务器发送两个操作数以及要执行的操作（三者均以单个字符串链的形式），服务器返回操作结果。例如，如果客户端向服务器发送：

- `ADD 6 1`，服务器将返回 `7`。
- `MUL 10 88`，后者将返回 `880`。
- `SOUS 5 9`，服务器将返回 `-4`。
- `DIV 9 8`，服务器将返回 `1.125`。（实除）。
- `PARIS 6 7`，服务器将返回 `hhhhh error`。

### 练习 21：使用 TCP 套接字的乘法表

- 使用 Java TCP 套接字创建客户端/服务器模型：客户端向服务器发送一个整数（例如 `4`），后者返回该整数的乘法表。

例如，客户端需要显示：4 的乘法表：

```
0 4 8 12 16 20 24 28 32 36 40
```

- 现在你的客户端必须发送一个整数表，即 `{1, 6, 8, 9, 13, 10}`。
- 服务器必须返回仅包含偶数的子表（`{6, 8, 10}`）。

### 练习 22：TCP 套接字的低级操作

使用低级 TCP 套接字操作（`OutputStream` 的 `write` 和 `InputStream` 的 `read`）编写一个客户端/服务器模型，客户端向服务器发送包含两个单词的句子（例如 `PARIS MADRID`）。

服务器将通过同一个句子展开，但分为两行（每个单词占一行）。

在此示例中，服务器将返回：

```
PARIS
MADRID
```

### 练习 23：使用 RMI 处理字符串链

- 使用 Java RMI 编写一个远程方法来计算单词的反转。为此，我们需要编写客户端和服务器之间的共享接口、客户端实现和服务器实现。
- 添加第二个远程方法，返回该单词开头四个字符的子字符串。
- 添加第三个远程方法，判断该单词是否为回文。

### 练习 24：使用 RMI 的斐波那契数列

斐波那契数列是一个整数序列，每个数字都是前两个数字之和。它通常从 1 开始，前几个数字为：1, 1, 2, 3, 5, 8, 13, 21 等。

使用 Java RMI 编写一个参数为数字 `n` 的远程方法，并返回该序列的前 `n` 个整数。例如，向服务器发送 `5`，后者将返回以下字符串链：`1, 1, 2, 3, 5`。

### 练习 25：使用 RMI 的蝴蝶结

使用 Java RMI 编写一个远程方法，接收一个奇数长度的字符串链（你必须对单词长度进行测试），并以蝴蝶结形状显示它。例如：

```
h o
he lo
hello
he lo
h o
```



### 练习 26：使用 RMI 的注册服务

我们希望实现一个注册服务，记录名称和电话号码，并允许用户使用名称访问它们。该注册必须能够通过 RMI 远程访问。我们认为名称和号码都是字符串链。

- 定义一个符合这些规范的 RMI 接口。
- 开发实现该接口的服务器对象。
- 开发一个查询上述服务器对象的客户端。

# 参考文献

1. [AIC 17] AICAS，可用地址：[`http://www.aicas.com/`](http://www.aicas.com/), 2017.
2. [DIJ 71] DIJKSTRA E.W., “Hierarchical ordering of sequential processes” in BRINCH HANSEN P. (ed.), *The Origin of Concurrent Programming*, Springer.
3. [TAN 01] TANENUM A., *Modern Operating Systems*, 2nd ed., Prentice-Hall, 2001.
4. [TIM 17] TIMESYS，可用地址：[`http://www.timesys.com/`](http://www.timesys.com/), 2017.
5. [UCI 17] UNIVERSITY OF CALIFORNIA, Irvine,可用地址：[`http://www.uci.edu/`](http://www.uci.edu/), 2017.

## 2014

BARBIER Franck, RECOUSSINE Jean-Luc
*COBOL 软件现代化：从原理到基于 BLU AGE 方法实现*

CHEN Ken
*基于仿真与分析的性能评估及其在计算机网络的应用*

CLERC Maurice
*优化中的引导随机性（元启发算法集 – 第 1 卷）*

DURAND Nicolas, GIANAZZA David, GOTTELAND Jean-Baptiste, ALLIOT Jean-Marc
*空中交通管理的元启发算法（元启发算法集 – 第 2 卷）*

MAGOULÈS Frédéric, ROUX François-Xavier, HOUZEAUX Guillaume
*并行科学计算*

MUNEESAWANG Paisarn, YAMMEN Suchart
*硬盘行业的视觉检测技术*

BOULANGER Jean-Louis
*应用于工业复杂系统的形式化方法*

BOULANGER Jean-Louis
*复杂系统的形式化方法：B 方法实现*

GARDI Frédéric, BENOIST Thierry, DARLAY Julien, ESTELLON Bertrand, MEGEL Romain
*基于局部搜索的数学规划求解器*

KRICHEN Saoussen, CHAOUACHI Jouhaina
*图相关的优化与决策支持系统*

LARRIEU Nicolas, VARET Antoine
*航空电子系统软件的快速原型：面向复杂系统认证的模型方法*

OUSSALAH Mourad Chabane
*软件架构 1*
*软件架构 2*

PASCHOS Vangelis Th
*组合优化 – 3 卷本，第 2 版
组合优化的概念 – 第 1 卷，第 2 版
问题与新方法 – 第 2 卷，第 2 版
组合优化的应用 – 第 3 卷，第 2 版*

QUESNEL Flavien
*大规模虚拟化基础设施调度：走向协作管理*

RIGO Michel
*形式语言、自动机与数系统 1：词组合学导论*
*形式语言、自动机与数系统 2：可识别性与可判定性的应用*

SAINT-DIZIER Patrick
*音乐修辞：基础与标注方案*

TOUATI Sid, DE DINECHIN Benoit
*高级后端优化*

## 2013

ANDRÉ Etienne, SOULAT Romain
*逆向方法：实时嵌入式系统的参数化验证*

BOULANGER Jean-Louis
*基于软件设备的安全管理*

DELAHAYE Daniel, PUECHMOREL Stéphane
*空中交通建模与优化*

FRANCOPOULO Gil
*LMF — 词标记框架*

GHÉDIRA Khaled
*约束满足问题*

ROCHANGE Christine, UHRIG Sascha, SAINRAT Pascal
*时间可预测架构*

WAHBI Mohamed
*分布式约束满足问题的算法与排序启发式算法*

ZELM Martin *et al*.
*企业互操作性*

## 2012

ARBOLEDA Hugo, ROYER Jean-Claude
*模型驱动与软件产品线工程*

BLANCHET Gérard, DUPOUY Bertrand
*计算机体系*

BOULANGER Jean-Louis
*形式化方法的工业应用：形式化验证*

BOULANGER Jean-Louis
*形式化方法：从模型到代码的工业应用*

CALVARY Gaëlle, DELOT Thierry, SÈDES Florence, TIGLI Jean-Yves
*计算机科学与环境智能*

MAHOUT Vincent
*汇编语言编程：ARM Cortex-M3 2.0：组织、创新与领域*

MARLET Renaud
*程序专门化*

SOTO Maria, SEVAUX Marc, ROSSI André, LAURENT Johann
*嵌入式系统中的内存分配问题：优化方法*

## 2011

BICHOT Charles-Edmond, SIARRY Patrick
*图划分*

BOULANGER Jean-Louis
*软件静态分析：抽象解释*

CAFERRA Ricardo
*计算机科学与人工智能的逻辑学*

HOMES Bernard
*软件测试基础*

KORDON Fabrice, HADDAD Serge, PAUTET Laurent, PETRUCCI Laure
*分布式系统：设计与算法*

KORDON Fabrice, HADDAD Serge, PAUTET Laurent, PETRUCCI Laure
*分布式系统中的模型与分析*

LORCA Xavier
*基于树的图划分约束*

TRUCHET Charlotte, ASSAYAG Gerard
*音乐中的约束规划*

VICAT-BLANC PRIMET Pascale *et al*.
*计算网络：从集群到云计算*

## 2010

AUDIBERT Pierre
*信息学与计算机科学数学*

BABAU Jean-Philippe *et al*.
*2009 年分布式实时嵌入式系统的模型驱动工程*

BOULANGER Jean-Louis
*计算机架构安全*

MONMARCHE Nicolas *et al*.
*人工蚂蚁*

PANETTO Hervé, BOUDJLIDA Nacer
*2010 年企业软件与应用互操作性*

SIGAUD Olivier *et al*.
*人工智能中的马尔可夫决策过程*

SOLNON Christine
*蚁群优化与约束规划*

AUBRUN Christophe, SIMON Daniel, SONG Ye-Qiong *et al*.
*可靠网络控制系统的协同设计方法*

## 2009

FOURNIER Jean-Claude
*图论及其应用*

GUEDON Jeanpierre
*Mojette 变换 / 理论与应用*

JARD Claude, ROUX Olivier
*嵌入式系统通信 / 设计与设计*

LECOUTRE Christophe
*约束网络：技术与算法的简化目标*

## 2008

BANÂTRE Michel, MARRÓN Pedro José, OLLERO Hannibal, WOLITZ Adam
*协作嵌入式系统与无线传感器网络*

MERZ Stephan, NAVET Nicolas
*实时系统的建模与验证*

PASCHOS Vangelis Th
*组合优化与理论计算机科学：接口与展望*

WALDNER Jean-Baptiste
*纳米计算机与群体智能*

## 2007

BENHAMOU Frédéric, JUSSIEN Narendra, O’SULLIVAN Barry
*约束规划的趋势*

JUSSIEN Narendra
*数独从 A 到 Z*

## 2006

BABAU Jean-Philippe *et al*.
*从 MDD 概念到实验与插图 – DRES 2006*

HABRIAS Henri, FRAPPIER Marc
*软件规范方法*

MURAT Cecile, PASCHOS Vangelis Th
*图上的概率组合优化*

PANETTO Hervé, BOUDJLIDA Nacer
*2006 年企业软件与应用互操作性 / IFAC-IFIP I-ESA’2006*

## 2005

GÉRARD Sébastien *et al*.
*分布式实时嵌入式系统的模型驱动工程*

PANETTO Hervé
*2005 年企业软件与应用互操作性*
